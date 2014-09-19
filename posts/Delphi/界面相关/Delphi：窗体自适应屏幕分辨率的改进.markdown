Delphi：窗体自适应屏幕分辨率的改进
===============================

前言
----

在窗体依据屏幕分辨率自适应调整尺度方面，昨天的工作可以说是一个突破点。昨天的工作找到了长期以来我的原有方案的问题所在，这是非常关键的。但是昨天晚上的解决方案并不完美，今天的这个才是比较完美的解决版。

先补充说明一下这个问题的重要性。这本来只是一个很小的技术问题，但在现有的Windows软件开发过程中，这个问题非常常见。一些非常著名的商业化软件，也会发现这方面的问题。Delphi的IDE本身在不同屏幕分辨率的机器上运行时，有些界面也会出现变形和控件找不到的情况；Adobe是家软件大公司，他的PDF编辑器在不同屏幕分辨率的机器上运行时，也会出现按钮不见或者被吃掉一半的情况。

因此，这实际上是软件开发过程中一个小的但又常常让人烦恼的顽疾。

昨天的解决方案中，有一点有所忽略。也就是，由于容器中的控件的位置和尺寸会随着容器尺寸的改变而改变，那么，容器尺寸的改变应该发生在其所包含的控件尺寸调整之前。但是，我并不清楚，一个容器里面到底嵌套了多少级，到底存在多少容器和控件，也不清楚容器中组件的排列方式。昨天的方案在这个地方带有点尝试性，似乎是倒着顺序去调整控件的尺寸，出来的窗体就会比较合理，而顺着序改则会调整不好。这个经验是很久以前试出来的，昨天没有改所以忘了说。

是怎样的实现原理？
----

今天的方案是是首先利用递归方法做第一次遍历，一层一层地搜索，直到把所有的控件搜索完毕。搜索过程中将每个控件的原始坐标保存起来。然后按照同样的方式做第二次遍历，利用保存的原始坐标数据计算新的坐标数据。由于搜索是从顶层容器依次往下的，因此先修改的是容器的尺度，然后才修改容器内部控件的尺度，这样明确保证了控件尺度的调整在其宿主容器尺寸调整之后，也就不会再受其宿主容器尺度改变的影响。最后对窗体中所有组件做遍历，修改字体大小。

我该怎么去修改？
-------------

改进后的源代码如下，经过试验，效果非常完美，用法跟昨天的一样。


    unit uMyClassHelpers;
    {实现窗体自适应调整尺寸以适应不同屏幕分辩率的显示问题。
            陈小斌，2012年3月5日
    }

    interface
    Uses
      SysUtils,Windows,Classes,Graphics, Controls,Forms,Dialogs, Math,
      uMySysUtils;

    Const   //记录设计时的屏幕分辨率
      OriWidth=1366;
      OriHeight=768;

    Type

      TfmForm=Class(TForm)   //实现窗体屏幕分辨率的自动调整
      Private
        fScrResolutionRateW: Double;
        fScrResolutionRateH: Double;
        fIsFitDeviceDone: Boolean;
        procedure FitDeviceResolution;
      Protected
        Property IsFitDeviceDone:Boolean Read fIsFitDeviceDone;
        Property ScrResolutionRateH:Double Read fScrResolutionRateH;
        Property ScrResolutionRateW:Double Read fScrResolutionRateW;
      Public
        Constructor Create(AOwner: TComponent); Override;
      End;

      TfdForm=Class(TfmForm)   //增加对话框窗体的修改确认
      Protected
        fIsDlgChange:Boolean;
      Public
      Constructor Create(AOwner: TComponent); Override;
      Property IsDlgChange:Boolean Read fIsDlgChange default false;
     End;

    implementation

    constructor TfmForm.Create(AOwner: TComponent);
    begin
     Inherited Create(AOwner);
      fScrResolutionRateH:=1;
      fScrResolutionRateW:=1;
      Try
        if Not fIsFitDeviceDone then
        Begin
          FitDeviceResolution;
       fIsFitDeviceDone:=True;
        End;
      Except
      fIsFitDeviceDone:=False;
      End;
    end;

    procedure TfmForm.FitDeviceResolution;
    Var
      LocList:TList;
      LocFontRate:Double;
      LocFontSize:Integer;
      LocFont:TFont;
      locK:Integer;

    {计算尺度调整的基本参数}
      Procedure CalBasicScalePars;
      Begin
        try
          Self.Scaled:=False;
          fScrResolutionRateH:=screen.height/OriHeight;
          fScrResolutionRateW:=screen.Width/OriWidth;
          LocFontRate:=Min(fScrResolutionRateH,fScrResolutionRateW);
        except
          Raise;
        end;
      End;

    {保存原有坐标位置：利用递归法遍历各级容器里的控件，直到最后一级}
      Procedure ControlsPostoList(vCtl:TControl;vList:TList);
      Var
        locPRect:^TRect;
        i:Integer;
        locCtl:TControl;
      Begin
        try
          New(locPRect);
          locPRect^:=vCtl.BoundsRect;
          vList.Add(locPRect);
          If vCtl Is TWinControl Then
            For i:=0 to TWinControl(vCtl).ControlCount-1 Do
            begin
              locCtl:=TWinControl(vCtl).Controls[i];
              ControlsPosToList(locCtl,vList);
            end;
        except
          Raise;
        end;
      End;

    {计算新的坐标位置：利用递归法遍历各级容器里的控件，直到最后一层。
     计算坐标时先计算顶级容器级的，然后逐级递进}
      Procedure AdjustControlsScale(vCtl:TControl;vList:TList;Var vK:Integer);
      Var
        locOriRect,LocNewRect:TRect;
        i:Integer;
        locCtl:TControl;
      Begin
        try
          If vCtl.Align<>alClient Then
          Begin
            locOriRect:=TRect(vList.Items[vK]^);
            With locNewRect Do
            begin
               Left:=Round(locOriRect.Left*fScrResolutionRateW);
               Right:=Round(locOriRect.Right*fScrResolutionRateW);
               Top:=Round(locOriRect.Top*fScrResolutionRateH);
               Bottom:=Round(locOriRect.Bottom*fScrResolutionRateH);
               vCtl.SetBounds(Left,Top,Right-Left,Bottom-Top);
            end;
          End;
          Inc(vK);
          If vCtl Is TWinControl Then
            For i:=0 to TwinControl(vCtl).ControlCount-1 Do
            begin
              locCtl:=TWinControl(vCtl).Controls[i];
              AdjustControlsScale(locCtl,vList,vK);
            end;
        except
          Raise;
        end;
      End;

    {按照新的比例设计窗体中各组件的字体}
      Procedure AdjustComponentFont(vCmp:TComponent);
      Var
        i:Integer;
        locCmp:TComponent;
      Begin
        try
          For i:=vCmp.ComponentCount-1 Downto 0 Do
          Begin
            locCmp:=vCmp.Components[i];
            If PropertyExists(LocCmp,'FONT') Then
            Begin
              LocFont:=TFont(GetObjectProperty(LocCmp,'FONT'));
              LocFontSize := Round(LocFontRate*LocFont.Size);
              LocFont.Size:=LocFontSize;
            End;
          End;
        except
          Raise;
        end;
      End;

    {释放坐标位置指针和列表对象}
      Procedure FreeListItem(vList:TList);
      Var
        i:Integer;
      Begin
        For i:=0 to vList.Count-1 Do
          Dispose(vList.Items[i]);
        vList.Free;
      End;

    begin
      LocList:=TList.Create;
      Try
      Try
          if (Screen.width<>OriWidth)OR(Screen.Height<>OriHeight) then
          begin
            CalBasicScalePars;
            AdjustComponentFont(Self);
            ControlsPostoList(Self,locList);
            locK:=0;
            AdjustControlsScale(Self,locList,locK);

       End;
      Except on E:Exception Do
          Raise Exception.Create('进行屏幕分辨率自适应调整时出现错误'+E.Message);
      End;
      Finally
        FreeListItem(locList);
      End;
    end;


    { TfdForm }

    constructor TfdForm.Create(AOwner: TComponent);
    begin
      inherited;
      fIsDlgChange:=False;
    end;

    end.

上面包括两个类，一个是普通窗体类，一个是其子类对话框型窗体类。在实际应用过程中只要自己创建的窗体类继承自以上两个类中的一个，例如 TForm1 = class(TfdForm)，则不需添加任何源码，设计出窗体会自动调整其上控件的尺寸，以适应不同的屏幕分辨率。