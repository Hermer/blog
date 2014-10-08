delphi分屏显示
==============

TScreen和TMonitor.
这两者的区别在于TScreen代表的是一个虚拟的桌面,它可以拥有N个Monitor,也就是物理的显示器.

    //将一个窗体显示到指定的显示器上
    procedure SetWindowToMonitor(Form: TCustomForm; //你想操作的窗体
                                 MonitorIndex,      //你想要显示窗体的显示
                                                    //  器索引， 0为主显示
                                                    //  器，1为第二显示器
                                 Left, Top: Integer //窗体在显示器上的位置
                                );
    begin  
      if not Assigned(Form) then Exit;
      if MonitorIndex >= Screen.MonitorCount then Exit;
      with Screen do
      begin
        Inc(Left, Monitors[MonitorIndex].Left);
        Inc(Top, Monitors[MonitorIndex].Top);
      end;
      Form.SetBounds(Left, Top, Form.Width, Form.Height);
    end;


