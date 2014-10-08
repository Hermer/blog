Delphi 常用String函数
==============
引入帮助库uses StrUtils;

首部 function AnsiResemblesText(const AText, AOther: string): Boolean; 
$[StrUtils.pas
功能 返回两个字符串是否相似
说明 ANSI(American National Standards Institute)美国国家标准协会;不区分大小写
参考 function StrUtils.SoundexProc; var StrUtils.AnsiResemblesProc
例子 CheckBox1.Checked := AnsiResemblesText(Edit1.Text, Edit2.Text);				            
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiContainsText(const AText, ASubText: string): Boolean; 
$[StrUtils.pas
功能 返回字符串AText是否包含子串ASubText
说明 不区分大小写
参考 function StrUtils.AnsiUppercase; function StrUtils.AnsiPos
例子 CheckBox1.Checked := AnsiContainsText(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function AnsiStartsText(const ASubText, AText: string): Boolean; 
$[StrUtils.pas
功能 返回字符串AText是否以子串ASubText开头
说明 不区分大小写
参考 function Windows.CompareString
例子 CheckBox1.Checked := AnsiStartsText(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function AnsiEndsText(const ASubText, AText: string): Boolean; 
$[StrUtils.pas
功能 返回字符串AText是否以子串ASubText结尾
说明 不区分大小写
参考 function Windows.CompareString
例子 CheckBox1.Checked := AnsiEndsText(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function AnsiReplaceText(const AText, AFromText, AToText: string): 
string; $[StrUtils.pas
功能 返回字符串AText中用子串AFromText替换成子串AToText的结果
说明 不区分大小写
参考 function SysUtils.StringReplace; type SysUtils.TReplaceFlags
例子 Edit4.Text := AnsiReplaceText(Edit1.Text, Edit2.Text, Edit3.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function AnsiMatchText(const AText: string; const AValues: array of 
string): Boolean; $[StrUtils.pas
功能 返回字符串数组AValues中是否包含字符串AText
说明 不区分大小写
参考 function StrUtils.AnsiIndexText
例子 CheckBox1.Checked := AnsiMatchText(Edit1.Text, ['a1', 'a2', 'a3', 
'a4']);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function AnsiIndexText(const AText: string; const AValues: array of 
string): Integer; $[StrUtils.pas
功能 返回字符串AText在字符串数组AValues中的位置
说明 不区分大小写;如果不包含则返回-1
参考 function SysUtils.AnsiSameText
例子 SpinEdit1.Value := AnsiIndexText(Edit1.Text, ['a1', 'a2', 'a3', 'a4']);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function AnsiContainsStr(const AText, ASubText: string): Boolean; 
$[StrUtils.pas
功能 返回字符串AText是否包含子串ASubText
说明 区分大小写
参考 function StrUtils.AnsiPos
例子 CheckBox1.Checked := AnsiContainsStr(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiStartsStr(const ASubText, AText: string): Boolean; 
$[StrUtils.pas
功能 返回字符串AText是否以子串ASubText开头
说明 区分大小写
参考 function SysUtils.AnsiSameStr
例子 CheckBox1.Checked := AnsiStartsStr(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function AnsiEndsStr(const ASubText, AText: string): Boolean; 
$[StrUtils.pas
功能 返回字符串AText是否以子串ASubText结尾
说明 区分大小写
参考 function SysUtils.AnsiSameStr
例子 CheckBox1.Checked := AnsiEndsStr(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function AnsiReplaceStr(const AText, AFromText, AToText: string): 
string; $[StrUtils.pas
功能 返回字符串AText中用子串AFromText替换成子串AToText的结果
说明 区分大小写
参考 function SysUtils.StringReplace; type SysUtils.TReplaceFlags
例子 Edit4.Text := AnsiReplaceStr(Edit1.Text, Edit2.Text, Edit3.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function AnsiMatchStr(const AText: string; const AValues: array of 
string): Boolean; $[StrUtils.pas
功能 返回字符串数组AValues中是否包含字符串AText
说明 区分大小写
参考 function StrUtils.AnsiIndexStr
例子 CheckBox1.Checked := AnsiMatchStr(Edit1.Text, ['a1', 'a2', 'a3', 
'a4']);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function AnsiIndexStr(const AText: string; const AValues: array of 
string): Integer; $[StrUtils.pas
功能 返回字符串AText在字符串数组AValues中的位置
说明 区分大小写
参考 function SysUtils.AnsiSameStr
例子 SpinEdit1.Value := AnsiIndexStr(Edit1.Text, ['a1', 'a2', 'a3', 'a4']);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function DupeString(const AText: string; ACount: Integer): string; 
$[StrUtils.pas
功能 返回字符串AText的ACount个复本
说明 当ACount为0时返回''
参考 function System.SetLength
例子 Edit3.Text := DupeString(Edit1.Text, SpinEdit1.Value);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function ReverseString(const AText: string): string; $[StrUtils.pas
功能 返回字符串AText的反序
说明 ReverseString('1234') = '4321'
参考 function System.SetLength
例子 Edit3.Text := ReverseString(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function StuffString(const AText: string; AStart, ALength: Cardinal; 
const ASubText: string): string; $[StrUtils.pas
功能 返回嵌套字符串
说明 AStart:嵌套开始位置;ALength:嵌套长度;StuffString('abcd', 2, 0, '12') = 'a12bcd'
参考 function System.Copy
例子 Edit3.Text := StuffString(Edit1.Text, SpinEdit1.Value, SpinEdit2.Value, 
Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function RandomFrom(const AValues: array of string): string; overload; 
$[StrUtils.pas
功能 随机返回字符串数组AValues中的一个元素
说明 之前建议执行Randomize
参考 function System.Random
例子 Randomize; Edit3.Text := RandomFrom(['a1', 'a2', 'a3', 'a4']);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function IfThen(AValue: Boolean; const ATrue: string; AFalse: string = 
''): string; overload; $[StrUtils.pas
功能 返回指定的逻辑字符串
说明 IfThen(True, '是', '否') = '是';IfThen(False, '是', '否') = '否'
参考 <NULL>
例子 Edit3.Text := IfThen(CheckBox1.Checked, Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function LeftStr(const AText: string; const ACount: Integer): string; 
$[StrUtils.pas
功能 返回字符串AText左边的ACount个字符
说明 LeftStr('123456', 3) = '123'
参考 function System.Copy
例子 Edit3.Text := LeftStr(Edit1.Text, SpinEdit1.Value);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function RightStr(const AText: string; const ACount: Integer): string; 
$[StrUtils.pas
功能 返回字符串AText右边的ACount个字符
说明 RightStr('123456', 3) = '456'
参考 function System.Copy
例子 Edit3.Text := RightStr(Edit1.Text, SpinEdit1.Value);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function MidStr(const AText: string; const AStart, ACount: Integer): 
string; $[StrUtils.pas
功能 返回字符串AText从AStart开始的ACount个字符
说明 其实就是Copy
参考 function System.Copy
例子 Edit3.Text := MidStr(Edit1.Text, SpinEdit1.Value, SpinEdit2.Value);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function SearchBuf(Buf: PChar; BufLen: Integer; SelStart, SelLength: 
Integer; SearchString: String; Options: TStringSearchOptions = [soDown]): 
PChar; $[StrUtils.pas
功能 返回第一个搜索到的指针位置
说明 这函数常用于文本中搜索字符串
参考 <NULL>
例子 
///////Begin SearchBuf
function SearchEdit(EditControl: TCustomEdit; const SearchString: String;
SearchOptions: TStringSearchOptions; FindFirst: Boolean = False): Boolean;
var
Buffer, P: PChar;
Size: Word;
begin
Result := False;
if (Length(SearchString) = 0) then Exit;
Size := EditControl.GetTextLen;
if (Size = 0) then Exit;
Buffer := StrAlloc(Size + 1);
try
EditControl.GetTextBuf(Buffer, Size + 1);
P := SearchBuf(Buffer, Size, EditControl.SelStart, EditControl.SelLength,
SearchString, SearchOptions);
if P <> nil then begin
EditControl.SelStart := P - Buffer;
EditControl.SelLength := Length(SearchString);
Result := True;
end;
finally
StrDispose(Buffer);
end;
end;

procedure TForm1.Button1Click(Sender: TObject);
var
SearchOptions: TStringSearchOptions;
begin
SearchOptions := [];
if CheckBox1.Checked then
Include(SearchOptions, soDown);
if CheckBox2.Checked then
Include(SearchOptions, soMatchCase);
if CheckBox3.Checked then
Include(SearchOptions, soWholeWord);
SearchEdit(Memo1, Edit1.Text, SearchOptions);
Memo1.SetFocus;
end;
///////End SearchBuf
━━━━━━━━━━━━━━━━━━━━━ 
首部 function Soundex(const AText: string; ALength: TSoundexLength = 4): 
string; $[StrUtils.pas
功能 返回探测字符串
说明 根据探测法(Soundex)可以找到相进的字符串;http://www.nara.gov/genealogy/coding.html
参考 <NULL>
例子 Edit2.Text := Soundex(Edit1.Text, SpinEdit1.Value);
━━━━━━━━━━━━━━━━━━━━━
首部 function SoundexInt(const AText: string; ALength: TSoundexIntLength = 
4): Integer; $[StrUtils.pas
功能 返回探测整数
说明 ALength的值越大解码准确率越高
参考 <NULL>
例子 SpinEdit2.Value := SoundexInt(Edit1.Text, SpinEdit1.Value);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function DecodeSoundexInt(AValue: Integer): string; $[StrUtils.pas
功能 返回探测整数的解码
说明 DecodeSoundexInt(SoundexInt('hello')) 相当于 Soundex('hello')
参考 <NULL>
例子 Edit2.Text := DecodeSoundexInt(SpinEdit2.Value);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function SoundexWord(const AText: string): Word; $[StrUtils.pas
功能 返回探测文字数值
说明 没有参数ALength已经固定为4
参考 <NULL>
例子 SpinEdit2.Value := SoundexWord(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function DecodeSoundexWord(AValue: Word): string; $[StrUtils.pas
功能 返回探测文字数值的解码
说明 DecodeSoundexWord(SoundexWord('hello')) 相当于 Soundex('hello')
参考 <NULL>
例子 Edit2.Text := DecodeSoundexWord(SpinEdit2.Value);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function SoundexSimilar(const AText, AOther: string; ALength: 
TSoundexLength = 4): Boolean; $[StrUtils.pas
功能 返回两个字符串的探测字符串是否相同
说明 Result := Soundex(AText, ALength) = Soundex(AOther, ALength)
参考 <NULL>
例子 CheckBox1.Checked := SoundexSimilar(Edit1.Text, Edit2.Text, 
SpinEdit1.Value);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function SoundexCompare(const AText, AOther: string; ALength: 
TSoundexLength = 4): Integer; $[StrUtils.pas
功能 返回比较两个字符串的探测字符串的结果
说明 Result := AnsiCompareStr(Soundex(AText, ALength), Soundex(AOther, 
ALength))
参考 function SysUtils.AnsiCompareStr
例子 SpinEdit2.Value := SoundexCompare(Edit1.Text, Edit2.Text, 
SpinEdit1.Value);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function SoundexProc(const AText, AOther: string): Boolean; 
$[StrUtils.pas
功能 调用SoundexSimilar返回两个字符串的探测字符串是否相同
说明 系统变量AnsiResemblesProc的默认值
参考 function StrUtils.AnsiResemblesText
例子 [var AnsiResemblesProc: TCompareTextProc = SoundexProc;]
━━━━━━━━━━━━━━━━━━━━━
首部 function NewStr(const S: string): PString; deprecated; $[SysUtils.pas
功能 返回一个新的字符串指针地址
说明 字符串S为空时返回NullStr
参考 procedure System.New
例子 
////////Begin NewStr,DisposeStr
procedure TForm1.Button1Click(Sender: TObject);
var
P: PString;
begin
P := NewStr(Edit1.Text);
Edit2.Text := P^;
DisposeStr(P);
end;
////////End NewStr,DisposeStr
━━━━━━━━━━━━━━━━━━━━━ 
首部 procedure DisposeStr(P: PString); deprecated; $[SysUtils.pas
功能 释放字符串指针P资源
说明 配合函数NewStr使用
参考 procedure System.Dispose
例子 <如上参见,如下参见>
━━━━━━━━━━━━━━━━━━━━━ 
首部 procedure AssignStr(var P: PString; const S: string); deprecated; 
$[SysUtils.pas
功能 将字符串S更新给字符串指针P
说明 更新值时会释放以前字符串指针的资源
参考 function SysUtils.NewStr;function SysUtils.DisposeStr
例子 
////////Begin AssignStr
procedure TForm1.Button1Click(Sender: TObject);
var
P: PString;
begin
P := nil;
AssignStr(P, Edit1.Text);
Edit2.Text := P^;
DisposeStr(P);
end;
////////End AssignStr
━━━━━━━━━━━━━━━━━━━━━ 
首部 procedure AppendStr(var Dest: string; const S: string); deprecated; 
$[SysUtils.pas
功能 在字符串Dest后追加字符串S
说明 相当于Dest := Dest + S;Delphi6已经不建议使用
参考 <NULL>
例子 
////////Begin AppendStr
procedure TForm1.Button1Click(Sender: TObject);
var
S: string;
begin
S := Edit2.Text;
AppendStr(S, Edit1.Text);
Edit2.Text := S;
end;
////////End AppendStr
━━━━━━━━━━━━━━━━━━━━━ 
首部 function UpperCase(const S: string): string; $[SysUtils.pas
功能 返回字符串S的大写形式
说明 非小写字符不处理
参考 procedure System.SetLength
例子 Edit2.Text := UpperCase(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function LowerCase(const S: string): string; $[SysUtils.pas
功能 返回字符串S的小写形式
说明 非大写字符不处理
参考 procedure System.SetLength
例子 Edit2.Text := LowerCase(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function CompareStr(const S1, S2: string): Integer; $[SysUtils.pas
功能 返回比较两个字符
说明 当S1>S2返回值>0;当S1<S2返回值<0;当S1=S2返回值=0;区分大小写
参考 <NULL>
例子 SpinEdit1.Value := CompareStr(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function CompareMem(P1, P2: Pointer; Length: Integer): Boolean; 
assembler; $[SysUtils.pas
功能 返回比较两个内存指针
说明 CompareMem(PChar('12a'), PChar('12c'), 2)=True;CompareMem(PChar('12a'), 
PChar('12c'), 3)=False
参考 <NULL>
例子 CheckBox1.Checked := CompareMem(Self, Form1, 8);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function CompareText(const S1, S2: string): Integer; $[SysUtils.pas
功能 返回比较两个字符串
说明 不区分大小写
参考 <NULL>
例子 SpinEdit1.Value := CompareText(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function SameText(const S1, S2: string): Boolean; $[SysUtils.pas
功能 返回两个字符串是否相等
说明 不区分大小写
参考 <NULL>
例子 CheckBox1.Checked := SameText(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function AnsiUpperCase(const S: string): string; $[SysUtils.pas
功能 返回字符串S的大写形式
说明 ANSI(American National Standards Institute)美国国家标准协会;非小写的字符不变
参考 function Windows.CharUpperBuff
例子 Edit2.Text := AnsiUpperCase(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiLowerCase(const S: string): string; $[SysUtils.pas
功能 返回字符串S的小写形式
说明 非大写字符不处理
参考 function Windows.CharLowerBuff
例子 Edit2.Text := AnsiLowerCase(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiCompareStr(const S1, S2: string): Integer; $[SysUtils.pas
功能 反回比较两个字符串
说明 当S1>S2返回值>0;当S1<S2返回值<0;当S1=S2返回值=0;区分大小写
参考 function Windows.CompareString
例子 SpinEdit1.Value := AnsiCompareStr(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiSameStr(const S1, S2: string): Boolean; $[SysUtils.pas
功能 返回两个字符串是否相等
说明 区分大小写
参考 function SysUtils.AnsiCompareStr
例子 CheckBox1.Checked := AnsiSameStr(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiCompareText(const S1, S2: string): Integer; $[SysUtils.pas
功能 反回比较两个字符串
说明 当S1>S2返回值>0;当S1<S2返回值<0;当S1=S2返回值=0;不区分大小写
参考 function Windows.CompareString
例子 SpinEdit1.Value := AnsiCompareText(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiSameText(const S1, S2: string): Boolean; $[SysUtils.pas
功能 返回两个字符串是否相等
说明 不区分大小写
参考 function SysUtils.AnsiCompareText
例子 CheckBox1.Checked := AnsiSameText(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiStrComp(S1, S2: PChar): Integer; $[SysUtils.pas
功能 返回比较两个指针字符串
说明 当S1>S2返回值>0;当S1<S2返回值<0;当S1=S2返回值=0;区分大小写
参考 function System.CompareString
例子 SpinEdit1.Value := AnsiStrComp(PChar(Edit1.Text), PChar(Edit2.Text))
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiStrIComp(S1, S2: PChar): Integer; $[SysUtils.pas
功能 返回比较两个指针字符串
说明 当S1>S2返回值>0;当S1<S2返回值<0;当S1=S2返回值=0;不区分大小写;Ignore(忽略)
参考 function Windows.CompareString
例子 SpinEdit1.Value := AnsiStrIComp(PChar(Edit1.Text), PChar(Edit2.Text))
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiStrLComp(S1, S2: PChar; MaxLen: Cardinal): Integer; 
$[SysUtils.pas
功能 返回比较两个指针字符串指定长度
说明 当S1>S2返回值>0;当S1<S2返回值<0;当S1=S2返回值=0;区分大小写;Length(长度)
参考 function Windows.CompareString
例子 SpinEdit1.Value := AnsiStrLComp(PChar(Edit1.Text), PChar(Edit2.Text), 
SpinEdit2.Value)
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiStrLIComp(S1, S2: PChar; MaxLen: Cardinal): Integer; 
$[SysUtils.pas
功能 返回比较两个指针字符串指定长度
说明 当S1>S2返回值>0;当S1<S2返回值<0;当S1=S2返回值=0;不区分大小写
参考 function Windows.CompareString
例子 SpinEdit1.Value := AnsiStrLIComp(PChar(Edit1.Text), PChar(Edit2.Text), 
SpinEdit2.Value)
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiStrLower(Str: PChar): PChar; $[SysUtils.pas
功能 返回指针字符串小写形式
说明 非大写字符不处理
参考 function Windows.CharLower
例子 Edit2.Text := AnsiStrLower(PChar(Edit1.Text));
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiStrUpper(Str: PChar): PChar; $[SysUtils.pas
功能 返回指针字符串大写形式
说明 非小写字符不处理
参考 function Windows.CharUpper
例子 Edit2.Text := AnsiStrUpper(PChar(Edit1.Text));
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiLastChar(const S: string): PChar; $[SysUtils.pas
功能 返回字符串S的最后一个指针字符
说明 当字符串S为空串则返回空指针
参考 function SysUtils.ByteType
例子 Edit2.Text := AnsiLastChar(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiStrLastChar(P: PChar): PChar; $[SysUtils.pas
功能 返回指针字符串P的最后一个指针字符
说明 当字符串P为空空指针则返回空指针
参考 function SysUtils.ByteType
例子 Edit2.Text := AnsiLastChar(PChar(Edit1.Text));
━━━━━━━━━━━━━━━━━━━━━ 
首部 function WideUpperCase(const S: WideString): WideString; $[SysUtils.pas
功能 返回双字节字符串的大写形式
说明 WideChar双字节字符
参考 function Windows.CharUpperBuffW
例子 Edit2.Text := WideUpperCase(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function WideLowerCase(const S: WideString): WideString; $[SysUtils.pas
功能 返回双字节字符串的小写形式
说明 我怎么就测试不出来呢
参考 function Windows.CharLowerBuffW
例子 Edit2.Text := WideLowerCase(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function WideCompareStr(const S1, S2: WideString): Integer; 
$[SysUtils.pas
功能 返回比较两个双字节字符串
说明 当S1>S2返回值>0;当S1<S2返回值<0;当S1=S2返回值=0;区分大小写
参考 function Windows.CompareStringW
例子 SpinEdit1.Value := WideCompareStr(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function WideSameStr(const S1, S2: WideString): Boolean; $[SysUtils.pas
功能 返回两个双字节字符串是否相同
说明 区分大小写
参考 function SysUtils.WideCompareStr
例子 CheckBox1.Checked := WideSameStr(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function WideCompareText(const S1, S2: WideString): Integer; 
$[SysUtils.pas
功能 返回比较两个双字节字符串
说明 当S1>S2返回值>0;当S1<S2返回值<0;当S1=S2返回值=0;不区分大小写
参考 function Windows.CompareStringW
例子 SpinEdit1.Value := WideCompareText(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function WideSameText(const S1, S2: WideString): Boolean; 
$[SysUtils.pas
功能 返回两个双字节字符串是否相同
说明 不区分大小写
参考 function SysUtils.WideCompareText
例子 CheckBox1.Checked := WideSameText(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function Trim(const S: string): string; overload; $[SysUtils.pas
首部 function Trim(const S: WideString): WideString; overload; 
$[SysUtils.pas
功能 返回除去字符串S左右不可见字符
说明 小于#32的字符看作不可见字符
参考 function System.Copy
例子 Edit2.Text := Trim(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function TrimLeft(const S: string): string; overload; $[SysUtils.pas
首部 function TrimLeft(const S: WideString): WideString; overload; 
$[SysUtils.pas
功能 返回除去字符串S左边不可见字符
说明 小于#32的字符看作不可见字符
参考 function System.Copy
例子 Edit2.Text := TrimLeft(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function TrimRight(const S: string): string; overload; $[SysUtils.pas
首部 function TrimRight(const S: WideString): WideString; overload; 
$[SysUtils.pas
功能 返回除去字符串S右边不可见字符
说明 小于#32的字符看作不可见字符
参考 function System.Copy
例子 Edit2.Text := TrimRight(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function QuotedStr(const S: string): string; $[SysUtils.pas
功能 返回字符串S在pascal中的表现形式
说明 单引号中的一个单引号将转成两个
参考 procedure System.Insert
例子 Edit2.Text := QuotedStr(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiQuotedStr(const S: string; Quote: Char): string; 
$[SysUtils.pas
功能 返回字符串S以字符Quote为引号的表现形式
说明 AnsiQuotedStr('hello"world', 
'@')='@hello"world@';AnsiQuotedStr('hello"world', '"')='"hello""world"'
参考 function SysUtils.AnsiStrScan
例子 Edit2.Text := AnsiQuotedStr(Edit1.Text, '"');
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiExtractQuotedStr(var Src: PChar; Quote: Char): string; 
$[SysUtils.pas
功能 返回以字符Quote为引号的表现形式原形
说明 表现形式非法时Src不变否则为空
参考 function SysUtils.AnsiStrScan
例子
///////Begin AnsiExtractQuotedStr
procedure TForm1.Button1Click(Sender: TObject);
var
P: PChar;
begin
P := PChar(Edit1.Text);
Edit2.Text := AnsiExtractQuotedStr(P, '"');
Edit3.Text := P;
end;
///////End AnsiExtractQuotedStr
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiDequotedStr(const S: string; AQuote: Char): string; 
$[SysUtils.pas
功能 返回以字符AQuote为引号的表现形式原形
说明 表现形式非法时则返回S
参考 function SysUtils.AnsiExtractQuotedStr
例子 Edit2.Text := AnsiDequotedStr(Edit1.Text, '"');
━━━━━━━━━━━━━━━━━━━━━
首部 function AdjustLineBreaks(const S: string; Style: TTextLineBreakStyle = 
{$IFDEF LINUX} tlbsLF {$ENDIF} {$IFDEF MSWINDOWS} tlbsCRLF {$ENDIF}): 
string; $[SysUtils.pas
功能 返回将给定字符串的行分隔符调整为CR/LF序列
说明 
AdjustLineBreaks('1'#13'2'#13)='1'#13#10'2'#13#10;AdjustLineBreaks('1'#10'2'#10)='1'#13#10'2'#13#10
参考 function SysUtils.StrNextChar
例子 <NULL>
━━━━━━━━━━━━━━━━━━━━━
首部 function IsValidIdent(const Ident: string): Boolean; $[SysUtils.pas
功能 返回字符串Ident是否是正确的标识符
说明 标识符::字母|下划线[字母|下划线|数字]...
参考 <NULL>
例子 CheckBox1.Checked := IsValidIdent(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function IntToStr(Value: Integer): string; overload; $[SysUtils.pas
首部 function IntToStr(Value: Int64): string; overload; $[SysUtils.pas
功能 返回整数Value转换成字符串
说明 Format('%d', [Value])
参考 function SysUtils.FmtStr
例子 Edit2.Text := IntToStr(SpinEdit1.Value);
━━━━━━━━━━━━━━━━━━━━━
首部 function IntToHex(Value: Integer; Digits: Integer): string; overload; 
$[SysUtils.pas
首部 function IntToHex(Value: Int64; Digits: Integer): string; overload; 
$[SysUtils.pas
功能 返回整数Value转换成十六进制表现结果;Format('%.*x', [Digits, Value])
说明 参数Digits指定字符最小宽度;最小宽度不足时将用0填充
参考 function SysUtils.FmtStr
例子 Edit2.Text := IntToHex(SpinEdit1.Value, SpinEdit2.Value);
━━━━━━━━━━━━━━━━━━━━━
首部 function StrToInt(const S: string): Integer; $[SysUtils.pas
功能 返回字符串S转换成整数
说明 字符串非整数表达时将引起异常
参考 procedure System.Val
例子 SpinEdit1.Value := StrToInt(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function StrToIntDef(const S: string; Default: Integer): Integer; 
$[SysUtils.pas
功能 返回字符串S转换成整数
说明 字符串非整数表达时则返回默认值Default
参考 procedure System.Val
例子 SpinEdit1.Value := StrToIntDef(Edit1.Text, 0);
━━━━━━━━━━━━━━━━━━━━━
首部 function TryStrToInt(const S: string; out Value: Integer): Boolean; 
$[SysUtils.pas
功能 返回字符串S转换成整数Value是否成功
说明 字符串非整数表达时返回False并且Value将输出为0
参考 procedure System.Val
例子
///////Begin TryStrToInt
procedure TForm1.Button1Click(Sender: TObject);
var
I: Integer;
begin
CheckBox1.Checked := TryStrToInt(Edit1.Text, I);
SpinEdit1.Value := I;
end;
///////End TryStrToInt
━━━━━━━━━━━━━━━━━━━━━
首部 function StrToInt64(const S: string): Int64; $[SysUtils.pas
功能 返回字符串S转换成六十四位整数
说明 字符串非六十四位整数表达时将引起异常
参考 procedure System.Val
例子 SpinEdit1.Value := StrToInt64(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function StrToInt64Def(const S: string; const Default: Int64): Int64; 
$[SysUtils.pas
功能 返回字符串S转换成六十四位整数
说明 字符串非六十四位整数表达时则返回默认值Default
参考 procedure System.Val
例子 SpinEdit1.Value := StrToInt64Def(Edit1.Text, 0);
━━━━━━━━━━━━━━━━━━━━━
首部 function TryStrToInt64(const S: string; out Value: Int64): Boolean; 
$[SysUtils.pas
功能 返回字符串S转换成六十四位整数Value是否成功
说明 字符串非六十四位整数表达时返回False并且Value将输出为0
参考 procedure System.Val
例子
///////Begin TryStrToInt64
procedure TForm1.Button1Click(Sender: TObject);
var
I: Int64;
begin
CheckBox1.Checked := TryStrToInt64(Edit1.Text, I);
SpinEdit1.Value := I;
end;
///////End TryStrToInt64
━━━━━━━━━━━━━━━━━━━━━
首部 function StrToBool(const S: string): Boolean; $[SysUtils.pas
功能 返回字符串S转换成逻辑值
说明 字符非逻辑表达时将引起异常
参考 function SysUtils.TryStrToBool
例子 CheckBox1.Checked := StrToBool(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function StrToBoolDef(const S: string; const Default: Boolean): 
Boolean; $[SysUtils.pas
功能 返回字符串S转换成逻辑值
说明 字符非逻辑表达时则返回默认值Default
参考 function SysUtils.TryStrToBool
例子 CheckBox1.Checked := StrToBoolDef(Edit1.Text, False);
━━━━━━━━━━━━━━━━━━━━━
首部 function TryStrToBool(const S: string; out Value: Boolean): Boolean; 
$[SysUtils.pas
功能 返回字符串S转换成逻辑值Value是否成功
说明 [注意]0为假非0为真;不是'True'和'False';Delphi6 Bug 如下修正
参考 function SysUtils.AnsiSameText;var SysUtils.TrueBoolStrs;var 
SysUtils.FalseBoolStrs
例子
///////Begin TryStrToBool
procedure TForm1.Button1Click(Sender: TObject);
var
B: Boolean;
begin
SetLength(TrueBoolStrs, 2);
SetLength(FalseBoolStrs, 2);
TrueBoolStrs[0] := 'True';
FalseBoolStrs[0] := 'False';
TrueBoolStrs[1] := 'Yes';
FalseBoolStrs[1] := 'No';
CheckBox1.Checked := TryStrToBool(Edit1.Text, B);
CheckBox2.Checked := B;
end;
///////End TryStrToBool
附加
///////Begin TryStrToBool
function TryStrToBool(const S: string; out Value: Boolean): Boolean;
function CompareWith(const aArray: array of string): Boolean;
var
I: Integer;
begin
Result := False;
for I := Low(aArray) to High(aArray) do
if AnsiSameText(S, aArray[I]) then
begin
Result := True;
Break;
end;
end;
var
LResult: Extended;
begin
Result := TryStrToFloat(S, LResult);
if Result then
Value := LResult <> 0
else
begin
Result := True; //修正处
VerifyBoolStrArray;
if CompareWith(TrueBoolStrs) then
Value := True
else if CompareWith(FalseBoolStrs) then
Value := False
else
Result := False;
end;
end;
///////End TryStrToBool
━━━━━━━━━━━━━━━━━━━━━
首部 function BoolToStr(B: Boolean; UseBoolStrs: Boolean = False): string; 
$[SysUtils.pas
功能 返回逻辑值B转换成字符串
说明 BoolToStr(False, False)='0';BoolToStr(False, True)='-1'
参考 var SysUtils.TrueBoolStrs;var SysUtils.FalseBoolStrs
例子 Edit1.Text := BoolToStr(CheckBox1.Checked, CheckBox2.Checked);
━━━━━━━━━━━━━━━━━━━━━
首部 function LoadStr(Ident: Integer): string; $[SysUtils.pas
功能 返回根据标识Ident的字符串资源
说明 字符串资源是指程序的内部资源
参考 function SysUtils.FindStringResource
例子 Edit2.Text := LoadStr(StrToIntDef(Edit1.Text, 0));
━━━━━━━━━━━━━━━━━━━━━
首部 function FmtLoadStr(Ident: Integer; const Args: array of const): 
string; $[SysUtils.pas
功能 返回格式化的字符串资源
说明 字符串资源是指程序的内部资源
参考 function SysUtils.FmtStr;function SysUtils.FindStringResource
例子 <NULL>;
━━━━━━━━━━━━━━━━━━━━━
首部 function StrLen(const Str: PChar): Cardinal; $[SysUtils.pas
功能 返回指针字符串的长度
说明 当指针字符串Str为nil时将触发异常
参考 <NULL>
例子 SpinEdit2.Value := StrLen(PChar(Edit1.Text));
━━━━━━━━━━━━━━━━━━━━━
首部 function StrEnd(const Str: PChar): PChar; $[SysUtils.pas
功能 返回指针字符串的结尾
说明 当指针字符串Str为nil时将触发异常
参考 <NULL>
例子 Edit2.Text := StrEnd(PChar(Edit1.Text)) - SpinEdit1.Value;
━━━━━━━━━━━━━━━━━━━━━
首部 function StrMove(Dest: PChar; const Source: PChar; Count: Cardinal): 
PChar; $[SysUtils.pas
功能 返回将指针字符串Source指定内存数量Count复制覆盖到指针字符串Dest中
说明 Dest没有分配资源将触发异常s
参考 function System.Move
例子
///////Begin StrMove
procedure TForm1.Button1Click(Sender: TObject);
var
vBuffer: PChar;
begin
vBuffer := '0123456789';
StrMove(vBuffer, PChar(Edit1.Text), SpinEdit1.Value);
Edit2.Text := vBuffer;
end;
///////End StrMove
━━━━━━━━━━━━━━━━━━━━━
首部 function StrCopy(Dest: PChar; const Source: PChar): PChar; 
$[SysUtils.pas
功能 返回将指针字符串Source复制到指针字符串Dest中
说明 Dest应已经分配足够的空间非则将触发异常
参考 <NULL>
例子
///////Begin StrCopy
procedure TForm1.Button1Click(Sender: TObject);
var
vBuffer: PChar;
begin
GetMem(vBuffer, Length(Edit1.Text) + 1);
StrCopy(vBuffer, PChar(Edit1.Text));
Edit2.Text := vBuffer;
FreeMem(vBuffer);
end;
///////End StrCopy
━━━━━━━━━━━━━━━━━━━━━
首部 function StrECopy(Dest:PChar; const Source: PChar): PChar; 
$[SysUtils.pas
功能 返回将指针字符串Source复制到指针字符串Dest中的结尾
说明 可以连接指针字符串
参考 <NULL>
例子
///////Begin StrECopy
procedure TForm1.Button1Click(Sender: TObject);
var
vBuffer: array[0..255] of Char;
begin
StrECopy(StrECopy(vBuffer, PChar(Edit1.Text)), PChar(Edit2.Text));
Edit3.Text := vBuffer;
end;
///////End StrECopy
━━━━━━━━━━━━━━━━━━━━━
首部 function StrLCopy(Dest: PChar; const Source: PChar; MaxLen: Cardinal): 
PChar; $[SysUtils.pas
功能 返回将指针字符串Source指定长度MaxLen复制到指针字符串Dest中
说明 Dest应已经分配足够的空间非则将触发异常
参考 <NULL>
例子
///////Begin StrLCopy
procedure TForm1.Button1Click(Sender: TObject);
var
vBuffer: array[0..255] of Char;
begin
StrLCopy(vBuffer, PChar(Edit1.Text), SpinEdit1.Value);
Edit2.Text := vBuffer;
end;
///////End StrLCopy
━━━━━━━━━━━━━━━━━━━━━
首部 function StrPCopy(Dest: PChar; const Source: string): PChar; 
$[SysUtils.pas
功能 返回将指针字符串Source复制到指针字符串Dest中
说明 StrLCopy(Dest, PChar(Source), Length(Source))
参考 function SysUtils.StrLCopy
例子
///////Begin StrPCopy
procedure TForm1.Button1Click(Sender: TObject);
var
vBuffer: array[0..255] of Char;
begin
StrPCopy(vBuffer, PChar(Edit1.Text));
Edit2.Text := vBuffer;
end;
///////End StrPCopy
━━━━━━━━━━━━━━━━━━━━━
首部 function StrPLCopy(Dest: PChar; const Source: string; MaxLen: 
Cardinal): PChar; $[SysUtils.pas
功能 返回将字符串Source指定长度MaxLen复制到指针字符串Dest中
说明 StrLCopy(Dest, PChar(Source), MaxLen)
参考 function SysUtils.StrLCopy
例子
///////Begin StrPLCopy
procedure TForm1.Button1Click(Sender: TObject);
var
vBuffer: array[0..255] of Char;
begin
StrPLCopy(vBuffer, Edit1.Text, SpinEdit1.Value);
Edit2.Text := vBuffer;
end;
///////End StrPLCopy
━━━━━━━━━━━━━━━━━━━━━
首部 function StrCat(Dest: PChar; const Source: PChar): PChar; 
$[SysUtils.pas
功能 返回连接指针字符串Dest和指针字符串Source
说明 StrCopy(StrEnd(Dest), Source)
参考 function SysUntils.StrCopy
例子
///////Begin StrCat
procedure TForm1.Button1Click(Sender: TObject);
var
vBuffer: array[0..255] of Char;
begin
StrPCopy(vBuffer, Edit1.Text);
StrCat(vBuffer, PChar(Edit2.Text));
Edit3.Text := vBuffer;
end;
///////End StrCat
━━━━━━━━━━━━━━━━━━━━━
首部 function StrLCat(Dest: PChar; const Source: PChar; MaxLen: Cardinal): 
PChar; $[SysUtils.pas
功能 返回连接指针字符串Dest和指针字符串Source
说明 [注意]MaxLen指定连接后的最大长度不是指针字符串Source的长度
参考 <NULL>
例子
///////Begin StrLCat
procedure TForm1.Button1Click(Sender: TObject);
var
vBuffer: array[0..255] of Char;
begin
StrPCopy(vBuffer, Edit1.Text);
StrLCat(vBuffer, PChar(Edit2.Text), SpinEdit1.Value);
Edit3.Text := vBuffer;
end;
///////End StrLCat
━━━━━━━━━━━━━━━━━━━━━
首部 function StrComp(const Str1, Str2: PChar): Integer; $[SysUtils.pas
功能 返回比较两个指针字符串
说明 当S1>S2返回值>0;当S1<S2返回值<0;当S1=S2返回值=0;区分大小写;[注意]返回第一个出现不同字符的差异
参考 <NULL>
例子 SpinEdit1.Value := StrComp(PChar(Edit1.Text), PChar(Edit2.Text));
━━━━━━━━━━━━━━━━━━━━━
首部 function StrIComp(const Str1, Str2: PChar): Integer; $[SysUtils.pas
功能 返回比较两个指针字符串
说明 当S1>S2返回值>0;当S1<S2返回值<0;当S1=S2返回值=0;不区分大小写;[注意]返回第一个出现不同字符的差异
参考 <NULL>
例子 SpinEdit1.Value := StrIComp(PChar(Edit1.Text), PChar(Edit2.Text));
━━━━━━━━━━━━━━━━━━━━━
首部 function StrLComp(const Str1, Str2: PChar; MaxLen: Cardinal): Integer; 
$[SysUtils.pas
功能 返回比较两个指针字符串指定长度
说明 当S1>S2返回值>0;当S1<S2返回值<0;当S1=S2返回值=0;区分大小写;Length(长度);[注意]返回第一个出现不同字符的差异
参考 <NULL>
例子 SpinEdit1.Value := StrLComp(PChar(Edit1.Text), PChar(Edit2.Text), 
SpinEdit2.Value)
━━━━━━━━━━━━━━━━━━━━━
首部 function StrLIComp(const Str1, Str2: PChar; MaxLen: Cardinal): Integer; 
$[SysUtils.pas
功能 返回比较两个指针字符串指定长度
说明 当S1>S2返回值>0;当S1<S2返回值<0;当S1=S2返回值=0;不区分大小写;[注意]返回第一个出现不同字符的差异
参考 <NULL>
例子 SpinEdit1.Value := StrLIComp(PChar(Edit1.Text), PChar(Edit2.Text), 
SpinEdit2.Value)
━━━━━━━━━━━━━━━━━━━━━
首部 function StrScan(const Str: PChar; Chr: Char): PChar; $[SysUtils.pas
功能 返回在指针字符串Str搜索字符Chr第一个出现的地址
说明 没有找到则返回空指针
参考 <NULL>
例子 Edit2.Text := StrScan(PChar(Edit1.Text), '*');
━━━━━━━━━━━━━━━━━━━━━
首部 function StrRScan(const Str: PChar; Chr: Char): PChar; $[SysUtils.pas
功能 返回在指针字符串Str搜索字符Chr最后一个出现的地址
说明 没有找到则返回空指针
参考 <NULL>
例子 Edit2.Text := StrRScan(PChar(Edit1.Text), '*');
━━━━━━━━━━━━━━━━━━━━━
首部 function StrPos(const Str1, Str2: PChar): PChar; $[SysUtils.pas
功能 返回指针字符串Str2在Str1中第一个出现的地址
说明 没有找到则返回空指针;StrPos('12345', '3') = '345'
参考 <NULL>
例子 Edit3.Text := StrPos(PChar(Edit1.Text), PChar(Edit2.Text));
━━━━━━━━━━━━━━━━━━━━━ 
首部 function StrUpper(Str: PChar): PChar; $[SysUtils.pas
功能 返回指针字符串Str大写
说明 非小写字符不处理
参考 <NULL>
例子 Edit1.Text := StrUpper(PChar(Edit2.Text));
━━━━━━━━━━━━━━━━━━━━━
首部 function StrLower(Str: PChar): PChar; $[SysUtils.pas
功能 返回指针字符串Str小写
说明 非大写字符不处理
参考 <NULL>
例子 Edit1.Text := StrLower(PChar(Edit2.Text)); 
━━━━━━━━━━━━━━━━━━━━━ 
首部 function StrPas(const Str: PChar): string; $[SysUtils.pas
功能 返回指针字符串Str转换成字符串
说明 也可以直接赋值
参考 <NULL>
例子 Edit1.Text := StrPas(PChar(Edit2.Text));
━━━━━━━━━━━━━━━━━━━━━
首部 function StrAlloc(Size: Cardinal): PChar; $[SysUtils.pas
功能 返回分配指定空间的内存资源给指针字符串
说明 空间的大小也将保存;用StrDispose才能全部释放
参考 function System.GetMem
例子
///////Begin StrAlloc
procedure TForm1.Button1Click(Sender: TObject);
var
P: PChar;
begin
P := StrAlloc(SpinEdit1.Value);
ShowMessage(IntToStr(StrLen(P)));
Dec(P, SizeOf(Cardinal));
ShowMessage(IntToStr(Cardinal(Pointer(P)^)));
Inc(P, SizeOf(Cardinal));
StrDispose(P);
end;
///////End StrAlloc

━━━━━━━━━━━━━━━━━━━━━
首部 function StrBufSize(const Str: PChar): Cardinal; $[SysUtils.pas
功能 返回通过函数StrAlloc分配的缓冲区大小
说明 出现异常情况则返回不可预知的结果
参考 function System.SizeOf
例子 SpinEdit1.Value := StrBufSize(StrAlloc(SpinEdit2.Value));
━━━━━━━━━━━━━━━━━━━━━
首部 function StrNew(const Str: PChar): PChar; $[SysUtils.pas
功能 返回复制一个新的指针字符串
说明 如果Str为nil则返回nil
参考 function SysUtils.StrLen;function SysUtils.StrMove;function 
SysUtils.StrAlloc
例子
///////Begin StrNew,StrDispose
procedure TForm1.Button1Click(Sender: TObject);
var
P: PChar;
begin
P := StrNew(PChar(Edit1.Text));
ShowMessage(P);
StrDispose(P);
end;
///////End StrNew,StrDispose
━━━━━━━━━━━━━━━━━━━━━
首部 procedure StrDispose(Str: PChar); $[SysUtils.pas
功能 释放指针字符串Str内存资源
说明 如果Str为nil则不作任何处理;并且释放空间大小信息
参考 function System.Dec;function System.SizeOf;function System.FreeMem
例子 <参见StrNew>
━━━━━━━━━━━━━━━━━━━━━
首部 function Format(const Format: string; const Args: array of const): 
string; $[SysUtils.pas
功能 返回按指定方式格式化一个数组常量的字符形式
说明 这个函数是我在Delphi中用得最多的函数，现在就列举几个例子给你个直观的理解
"%" [索引 ":"] ["-"] [宽度] ["." 摘要] 类型
Format('x=%d', [12]); //'x=12' //最普通
Format('x=%3d', [12]); //'x= 12' //指定宽度
Format('x=%f', [12.0]); //'x=12.00' //浮点数
Format('x=%.3f', [12.0]); //'x=12.000' //指定小数
Format('x=%.*f', [5, 12.0]); //'x=12.00000' //动态配置
Format('x=%.5d', [12]); //'x=00012' //前面补充0
Format('x=%.5x', [12]); //'x=0000C' //十六进制
Format('x=%1:d%0:d', [12, 13]); //'x=1312' //使用索引
Format('x=%p', [nil]); //'x=00000000' //指针
Format('x=%1.1e', [12.0]); //'x=1.2E+001' //科学记数法
Format('x=%%', []); //'x=%' //得到"%"
S := Format('%s%d', [S, I]); //S := S + StrToInt(I); //连接字符串
参考 proceduer SysUtils.FmtStr
例子 Edit1.Text := Format(Edit2.Text, [StrToFloatDef(Edit.3.Text, 0)]);
━━━━━━━━━━━━━━━━━━━━━
首部 procedure FmtStr(var Result: string; const Format: string; const Args: 
array of const); $[SysUtils.pas
功能 按指定方式格式化一个数组常量的字符形式返回
说明 <参见Format>
参考 function SysUtils.FormatBuf;function System.Length;function 
System.SetLength
例子 <参见Format>
━━━━━━━━━━━━━━━━━━━━━
首部 function StrFmt(Buffer, Format: PChar; const Args: array of const): 
PChar; $[SysUtils.pas
功能 返回按指定方式格式化一个数组常量的字符指针形式
说明 如果Buffer和Format其中只要有一个为nil则返回nil
参考 function SysUtils.FormatBuf
例子 <参见Format>
━━━━━━━━━━━━━━━━━━━━━
首部 function StrLFmt(Buffer: PChar; MaxBufLen: Cardinal; Format: PChar; 
const Args: array of const): PChar; $[SysUtils.pas
功能 返回按指定方式和长度格式化一个数组常量的字符指针形式
说明 StrLFmt(vBuffer, 6, '%d|12345', [1024]) = '1024|1';
参考 function SysUtils.FormatBuf
例子 <参见Format>
━━━━━━━━━━━━━━━━━━━━━
首部 function FormatBuf(var Buffer; BufLen: Cardinal; const Format; FmtLen: 
Cardinal; const Args: array of const): Cardinal; $[SysUtils.pas
功能 返回按指定方式格式化一个数组常量到缓冲区Buffer中
说明 <NULL>
参考 <NULL>
例子 <参见Format>
━━━━━━━━━━━━━━━━━━━━━
首部 function WideFormat(const Format: WideString; const Args: array of 
const): WideString; $[SysUtils.pas
功能 返回按指定方式格式化一个数组常量的多字节字符形式
说明 <NULL>
参考 procedure SysUtils.WideFmtStr
例子 <参见Format>
━━━━━━━━━━━━━━━━━━━━━
首部 procedure WideFmtStr(var Result: WideString; const Format: WideString; 
const Args: array of const); $[SysUtils.pas
功能 按指定方式格式化一个数组常量的多字节字符形式返回
说明 <NULL>
参考 function SysUtils.WideFormatBuf
例子 <参见Format>
━━━━━━━━━━━━━━━━━━━━━
首部 function WideFormatBuf(var Buffer; BufLen: Cardinal; const Format; 
FmtLen: Cardinal; const Args: array of const): Cardinal; $[SysUtils.pas
功能 返回按指定方式格式化一个数组常量到缓冲区Buffer中
说明 <NULL>
参考 <NULL>
例子 <参见Format>
━━━━━━━━━━━━━━━━━━━━━
首部 function FloatToStr(Value: Extended): string; $[SysUtils.pas
功能 返回浮点数Value转换成字符串
说明 当浮点数大等于1E15将采用科学记数法
参考 function SysUtils.FloatToText
例子 Edit1.Text := FloatToStr(Now);
━━━━━━━━━━━━━━━━━━━━━
首部 function CurrToStr(Value: Currency): string; $[SysUtils.pas
功能 返回货币数Value转换成字符串
说明 货币数只保留四位小数
参考 function SysUtils.FloatToText
例子 Edit1.Text := CurrToStr(Now);
━━━━━━━━━━━━━━━━━━━━━
首部 function FloatToCurr(const Value: Extended): Currency; $[SysUtils.pas
功能 返回浮点数Value转换成货币数
说明 如果浮点数Value超出范围则将触发异常
参考 const SysUtiles.MinCurrency;const SysUtiles.MaxCurrency
例子 Edit1.Text := CurrToStr(FloatToCurr(Now));
━━━━━━━━━━━━━━━━━━━━━
首部 function FloatToStrF(Value: Extended; Format: TFloatFormat; Precision, 
Digits: Integer): string; $[SysUtils.pas
功能 返回浮点数以指定格式转换成字符串
说明 Precision指定精度;Digits指定小数宽度
参考 function SysUtils.FloatToText
例子
///////Begin FloatToStrF
procedure TForm1.Button1Click(Sender: TObject);
begin
Memo1.Lines.Values['ffGeneral'] := FloatToStrF(StrToFloatDef(Edit1.Text, 
0),
ffGeneral, SpinEdit1.Value, SpinEdit2.Value);
Memo1.Lines.Values['ffExponent'] := FloatToStrF(StrToFloatDef(Edit1.Text, 
0),
ffExponent, SpinEdit1.Value, SpinEdit2.Value);
Memo1.Lines.Values['ffFixed'] := FloatToStrF(StrToFloatDef(Edit1.Text, 0),
ffFixed, SpinEdit1.Value, SpinEdit2.Value);
Memo1.Lines.Values['ffNumber'] := FloatToStrF(StrToFloatDef(Edit1.Text, 
0),
ffNumber, SpinEdit1.Value, SpinEdit2.Value);
Memo1.Lines.Values['ffCurrency'] := FloatToStrF(StrToFloatDef(Edit1.Text, 
0),
ffCurrency, SpinEdit1.Value, SpinEdit2.Value);
end;
///////End FloatToStrF
━━━━━━━━━━━━━━━━━━━━━
首部 function CurrToStrF(Value: Currency; Format: TFloatFormat; Digits: 
Integer): string; $[SysUtils.pas
功能 返回货币类型以指定格式转换成字符串
说明 Digits指定小数宽度
参考 function SysUtils.FloatToText
例子
///////Begin CurrToStrF
procedure TForm1.Button1Click(Sender: TObject);
begin
Memo1.Lines.Values['ffGeneral'] := CurrToStrF(StrToCurrDef(Edit1.Text, 0),
ffGeneral, SpinEdit1.Value);
Memo1.Lines.Values['ffExponent'] := CurrToStrF(StrToCurrDef(Edit1.Text, 
0),
ffExponent, SpinEdit1.Value);
Memo1.Lines.Values['ffFixed'] := CurrToStrF(StrToCurrDef(Edit1.Text, 0),
ffFixed, SpinEdit1.Value);
Memo1.Lines.Values['ffNumber'] := CurrToStrF(StrToCurrDef(Edit1.Text, 0),
ffNumber, SpinEdit1.Value);
Memo1.Lines.Values['ffCurrency'] := CurrToStrF(StrToCurrDef(Edit1.Text, 
0),
ffCurrency, SpinEdit1.Value);
end;
///////End CurrToStrF
━━━━━━━━━━━━━━━━━━━━━
首部 function FloatToText(BufferArg: PChar; const Value; ValueType: 
TFloatValue; Format: TFloatFormat; Precision, Digits: Integer): Integer; 
$[SysUtils.pas
功能 返回浮点数以指定格式转换成指针字符串的内存大小
说明 Precision指定精度;Digits指定小数宽度
参考 <NULL>
例子
///////Begin FloatToText
procedure TForm1.Button1Click(Sender: TObject);
var
vBuffer: array[0..255] of Char;
E: Extended;
begin
E := StrToFloatDef(Edit1.Text, 0);
SpinEdit3.Value := FloatToText(vBuffer, E,
fvExtended, ffNumber, SpinEdit1.Value, SpinEdit2.Value);
Edit2.Text := Copy(vBuffer, 1, SpinEdit3.Value);
end;
///////End FloatToText(
━━━━━━━━━━━━━━━━━━━━━
首部 function FormatFloat(const Format: string; Value: Extended): string; 
$[SysUtils.pas
功能 返回浮点数类型以指定格式字符串Format转换成字符串
说明 FormatFloat(',.00', 1234567890) = '1,234,567,890.00'
参考 function SysUtils.FloatToTextFmt
例子 Edit1.Text := FormatFloat(Edit2.Text, StrToFloatDef(Edit3.Text, 0));
━━━━━━━━━━━━━━━━━━━━━
首部 function FormatCurr(const Format: string; Value: Currency): string; 
$[SysUtils.pas
功能 返回货币类型以指定格式字符串Format转换成字符串
说明 FormatCurr(',.00', 1234567890) = '1,234,567,890.00'
参考 function SysUtils.FloatToTextFmt
例子 Edit1.Text := FormatCurr(Edit2.Text, StrToCurrDef(Edit3.Text, 0));
━━━━━━━━━━━━━━━━━━━━━
首部 function FloatToTextFmt(Buf: PChar; const Value; ValueType: 
TFloatValue; Format: PChar): Integer; $[SysUtils.pas
功能 返回浮点数以指定格式字符串Format转换成指针字符串的内存大小
说明 ValueType指定无类型参数Value的类型
参考 <NULL>
例子
///////Begin FloatToTextFmt
procedure TForm1.Button1Click(Sender: TObject);
var
vBuffer: array[0..255] of Char;
E: Extended;
begin
E := StrToFloatDef(Edit1.Text, 0);
SpinEdit1.Value := FloatToTextFmt(vBuffer, E,
fvExtended, PChar(Edit2.Text));
Edit3.Text := Copy(vBuffer, 1, SpinEdit1.Value);
end;
///////End FloatToTextFmt
━━━━━━━━━━━━━━━━━━━━━
首部 function StrToFloat(const S: string): Extended; $[SysUtils.pas
功能 返回字符串S转换成浮点数
说明 字符串非浮点数表达时将引起异常
参考 function SysUtils.TextToFloat
例子 var E: Extended; begin E := StrToFloat(Edit1.Text); end;
━━━━━━━━━━━━━━━━━━━━━
首部 function StrToFloatDef(const S: string; const Default: Extended): 
Extended; $[SysUtils.pas
功能 返回字符串S转换成浮点数
说明 字符串非浮点数表达时则返回默认值Default
参考 function SysUtils.TextToFloat
例子 var E: Extended; begin E := StrToFloatDef(Edit1.Text, 0); end;
━━━━━━━━━━━━━━━━━━━━━
首部 function TryStrToFloat(const S: string; out Value: Extended): Boolean; 
overload; $[SysUtils.pas
首部 function TryStrToFloat(const S: string; out Value: Single): Boolean; 
overload; $[SysUtils.pas
首部 function TryStrToFloat(const S: string; out Value: Double): Boolean; 
overload; $[SysUtils.pas
功能 返回字符串S转换成浮点数Value是否成功
说明 字符串非浮点数表达时返回False并且Value将输出为不确定的值
参考 function SysUtils.TextToFloat
例子
///////Begin TryStrToFloat
procedure TForm1.Button1Click(Sender: TObject);
var
E: Extended;
begin
CheckBox1.Checked := TryStrToFloat(Edit1.Text, E);
Edit2.Text := FormatFloat('', E);
end;
///////End TryStrToFloat
━━━━━━━━━━━━━━━━━━━━━
首部 function StrToCurr(const S: string): Currency; $[SysUtils.pas
功能 返回字符串S转换成货币数
说明 字符串非货币数表达时将引起异常
参考 function SysUtils.TextToFloat
例子 var C: Currency; begin C := StrToCurr(Edit1.Text); end;
━━━━━━━━━━━━━━━━━━━━━
首部 function StrToCurrDef(const S: string; const Default: Currency): 
Currency; $[SysUtils.pas
功能 返回字符串S转换成货币数
说明 字符串非货币数表达时则返回默认值Default
参考 function SysUtils.TextToFloat
例子 var C: Currency; begin C := StrToCurrDef(Edit1.Text, 0); end;
━━━━━━━━━━━━━━━━━━━━━
首部 function TryStrToCurr(const S: string; out Value: Currency): Boolean; 
$[SysUtils.pas
功能 返回字符串S转换成货币数Value是否成功
说明 字符串非货币数表达时返回False并且Value将输出为不确定的值
参考 function SysUtils.TextToFloat
例子
///////Begin TryStrToCurr
procedure TForm1.Button1Click(Sender: TObject);
var
C: Currency;
begin
CheckBox1.Checked := TryStrToCurr(Edit1.Text, C);
Edit2.Text := FormatCurr('', C);
end;
///////End TryStrToCurr
━━━━━━━━━━━━━━━━━━━━━
首部 function TextToFloat(Buffer: PChar; var Value; ValueType: TFloatValue): 
Boolean; $[SysUtils.pas
功能 返回将指针字符串Buffer转换成无类型变量Value
说明 ValueType指定无类型参数Value的类型
参考 <NULL>
例子
///////Begin TextToFloat
procedure TForm1.Button1Click(Sender: TObject);
var
E: Extended;
begin
CheckBox1.Checked := TextToFloat(PChar(Edit1.Text), E,
fvExtended);
Edit2.Text := FormatFloat('', E);
end;
///////End TextToFloat
━━━━━━━━━━━━━━━━━━━━━
首部 function DateToStr(const DateTime: TDateTime): string; $[SysUtils.pas
功能 返回日期DateTime转换成字符串
说明 转换格式由系统变量ShortDateFormat控制
参考 function SysUtils.DateTimeToString;var SysUtils.ShortDateFormat
例子 Edit1.Text := DateToStr(Date);
━━━━━━━━━━━━━━━━━━━━━
首部 function TimeToStr(const DateTime: TDateTime): string; $[SysUtils.pas
功能 返回时间DateTime转换成字符串
说明 转换格式由系统变量LongTimeFormat控制
参考 function SysUtils.DateTimeToString;var SysUtils.LongTimeFormat
例子 Edit1.Text := TimeToStr(Date);
━━━━━━━━━━━━━━━━━━━━━
首部 function DateTimeToStr(const DateTime: TDateTime): string; 
$[SysUtils.pas
功能 返回日期时间DateTime转换成字符串
说明 转换格式由系统变量ShortDateFormat和LongTimeFormat控制
参考 function SysUtils.DateTimeToString
例子 Edit1.Text := DateTimeToStr(Now);
━━━━━━━━━━━━━━━━━━━━━
首部 function StrToDate(const S: string): TDateTime; $[SysUtils.pas
功能 返回字符串S转换成日期
说明 字符非日期表达时将引起异常
参考 function SysUtils.TryStrToDate
例子 DateTimePicker1.Date := StrToDate(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function StrToDateDef(const S: string; const Default: TDateTime): 
TDateTime; $[SysUtils.pas
功能 返回字符串S转换成日期
说明 字符非日期表达时则返回默认值Default
参考 function SysUtils.TryStrToDate
例子 DateTimePicker1.Date := StrToDateDef(Edit1.Text, Date);
━━━━━━━━━━━━━━━━━━━━━
首部 function TryStrToDate(const S: string; out Value: TDateTime): Boolean; 
$[SysUtils.pas
功能 返回字符串S转换成日期Value是否成功
说明 字符非日期表达时返回False并且Value将输出为0
参考 <NULL>
例子
///////Begin TryStrToDate
procedure TForm1.Button1Click(Sender: TObject);
var
vDateTime: TDateTime;
begin
CheckBox1.Checked := TryStrToDate(Edit1.Text, vDateTime);
DateTimePicker1.Date := vDateTime;
end;
///////End TryStrToDate
━━━━━━━━━━━━━━━━━━━━━
首部 function StrToTime(const S: string): TDateTime; $[SysUtils.pas
功能 返回字符串S转换成时间
说明 字符非时间表达时将引起异常
参考 function SysUtils.TryStrToTime
例子 DateTimePicker1.Time := StrToTime(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function StrToTimeDef(const S: string; const Default: TDateTime): 
TDateTime; $[SysUtils.pas
功能 返回字符串S转换成时间
说明 字符非时间表达时则返回默认值Default
参考 function SysUtils.TryStrToTime
例子 DateTimePicker1.Time := StrToTimeDef(Edit1.Text, Time);
━━━━━━━━━━━━━━━━━━━━━
首部 function TryStrToTime(const S: string; out Value: TDateTime): Boolean; 
$[SysUtils.pas
功能 返回字符串S转换成时间Value是否成功
说明 字符非时间表达时返回False并且Value将输出为0
参考 <NULL>
例子
///////Begin TryStrToTime
procedure TForm1.Button1Click(Sender: TObject);
var
vDateTime: TDateTime;
begin
CheckBox1.Checked := TryStrToTime(Edit1.Text, vDateTime);
DateTimePicker1.Time := vDateTime;
end;
///////End TryStrToTime
━━━━━━━━━━━━━━━━━━━━━
首部 function StrToDateTime(const S: string): TDateTime; $[SysUtils.pas
功能 返回字符串S转换成日期时间
说明 字符非日期时间表达时将引起异常
参考 function SysUtils.TryStrToDateTime
例子 Edit1.Text := DateTimeToStr(StrToDateTime(Edit2.Text));
━━━━━━━━━━━━━━━━━━━━━
首部 function StrToDateTimeDef(const S: string; const Default: TDateTime): 
TDateTime; $[SysUtils.pas
功能 返回字符串S转换成日期时间
说明 字符非日期时间表达时则返回默认值Default
参考 function SysUtils.TryStrToDateTime
例子 Edit1.Text := DateTimeToStr(StrToDateTimeDef(Edit2.Text, Now));
━━━━━━━━━━━━━━━━━━━━━
首部 function TryStrToDateTime(const S: string; out Value: TDateTime): 
Boolean; $[SysUtils.pas
功能 返回字符串S转换成日期时间Value是否成功
说明 字符非日期时间表达时返回False并且Value将输出为0
参考 <NULL>
例子
///////Begin TryStrToDateTime
procedure TForm1.Button1Click(Sender: TObject);
var
vDateTime: TDateTime;
begin
CheckBox1.Checked := TryStrToDateTime(Edit1.Text, vDateTime);
Edit2.Text := DateTimeToStr(vDateTime);
end;
///////End TryStrToDateTime
━━━━━━━━━━━━━━━━━━━━━
首部 procedure DateTimeToString(var Result: string; const Format: string; 
DateTime: TDateTime); $[SysUtils.pas
功能 用指定的格式Format来格式化日期时间DateTime并返回到字符串Result中
说明 <参见FormatDateTime>
参考 function System.SetString
例子 <参见FormatDateTime>
━━━━━━━━━━━━━━━━━━━━━
首部 function GetLocaleStr(Locale, LocaleType: Integer; const Default: 
string): string; platform; $[SysUtils.pas
功能 返回当前系统指定参数的字符串值
说明 GetLocaleStr(GetThreadLocale, LOCALE_SLANGUAGE, '') = '中文(中国)'
参考 function Windows.GetLocaleInfo
例子 Edit1.Text := GetLocaleStr(GetThreadLocale, SpinEdit1.Value, '<NULL>');
━━━━━━━━━━━━━━━━━━━━━
首部 function GetLocaleChar(Locale, LocaleType: Integer; Default: Char): 
Char; platform; $[SysUtils.pas
功能 返回当前系统指定参数的字符值
说明 GetLocaleChar(GetThreadLocale, LOCALE_STHOUSAND, #0) = ','
参考 function Windows.GetLocaleInfo
例子 Edit1.Text := GetLocaleChar(GetThreadLocale, LOCALE_SLANGUAGE, #0);
━━━━━━━━━━━━━━━━━━━━━
首部 function ByteType(const S: string; Index: Integer): TMbcsByteType; 
$[SysUtils.pas
功能 返回字符串S位置Index上的字符在MBCS中类型
说明 多字节字符系统:Multi-Byte Character System (MBCS)
参考 var SysUtils.SysLocale
例子 SpinEdit1.Value := Ord(ByteType(Edit1.Text, SpinEdit2.Value));
━━━━━━━━━━━━━━━━━━━━━
首部 function StrByteType(Str: PChar; Index: Cardinal): TMbcsByteType; 
$[SysUtils.pas
功能 返回指针字符串Str位置Index上的字符在MBCS中类型
说明 Index从0开始
参考 var SysUtils.SysLocale
例子 SpinEdit1.Value := Ord(StrByteType(PChar(Edit1.Text), 
SpinEdit2.Value));
━━━━━━━━━━━━━━━━━━━━━
首部 function ByteToCharLen(const S: string; MaxLen: Integer): Integer; 
$[SysUtils.pas
功能 返回字符串S中有多少个多字节字符
说明 MaxLen指定处理字符个数
参考 function SysUtils.ByteToCharIndex
例子 SpinEdit1.Value := ByteToCharLen(Edit1.Text, SpinEdit2.Value);
━━━━━━━━━━━━━━━━━━━━━
首部 function CharToByteLen(const S: string; MaxLen: Integer): Integer; 
$[SysUtils.pas
功能 返回字符串S中有多少个字符
说明 MaxLen指定处理多字节字符个数
参考 var SysUtils.SysLocale
例子 SpinEdit1.Value := CharToByteLen(Edit1.Text, SpinEdit2.Value);
━━━━━━━━━━━━━━━━━━━━━
首部 function ByteToCharIndex(const S: string; Index: Integer): Integer; 
$[SysUtils.pas
功能 返回字符位置对应的多字节字符位置
说明 ByteToCharIndex('你好', 2) = 1;ByteToCharIndex('你好', 3) = 2
参考 function SysUtils.NextCharIndex
例子 SpinEdit1.Value := ByteToCharIndex(Edit1.Text, SpinEdit2.Value);
━━━━━━━━━━━━━━━━━━━━━
首部 function CharToByteIndex(const S: string; Index: Integer): Integer; 
$[SysUtils.pas
功能 返回多字节字符位置对应的字符起始位置
说明 CharToByteIndex('你好', 1) = 1;CharToByteIndex('你好', 2) = 3
参考 function System.Length
例子 SpinEdit1.Value := CharToByteIndex(Edit1.Text, SpinEdit2.Value);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function StrCharLength(const Str: PChar): Integer; $[SysUtils.pas
功能 返回第一个字符的宽度
说明 参数为空则返回0
参考 function Windows.CharNext
例子 SpinEdit1.Value := StrCharLength(PChar(Edit1.Text));
━━━━━━━━━━━━━━━━━━━━━
首部 function StrNextChar(const Str: PChar): PChar; $[SysUtils.pas
功能 返回字符指针Str的下一个字符指针
说明 StrNextChar('1234') = '234';
参考 function Windows.CharNext
例子 Edit2.Text := StrNextChar(PChar(Edit1.Text));
━━━━━━━━━━━━━━━━━━━━━
首部 function CharLength(const S: String; Index: Integer): Integer; 
$[SysUtils.pas
功能 返回字符串中指定位置的字符宽度
说明 CharLength('English汉', 1) = 1;CharLength('English汉', 8) = 2
参考 function System.Assert;function SysUtils.StrCharLength
例子 SpinEdit1.Value := CharLength(Edit1.Text, SpinEdit2.Value);
━━━━━━━━━━━━━━━━━━━━━
首部 function NextCharIndex(const S: String; Index: Integer): Integer; 
$[SysUtils.pas
功能 返回下一个字符的位置
说明 CharLength('你好', 1) = 3;CharLength('你好', 3) = 5
参考 function System.Assert;function SysUtils.StrCharLength
例子 SpinEdit1.Value := NextCharIndex(Edit1.Text, SpinEdit2.Value);
━━━━━━━━━━━━━━━━━━━━━
首部 function IsPathDelimiter(const S: string; Index: Integer): Boolean; 
$[SysUtils.pas
功能 返回字符串S中指定位置Index上是否是一个路径分隔符
说明 IsPathDelimiter('C:/Windows', 3) = True
参考 const SysUtils.PathDelim;function SysUtils.ByteType
例子 CheckBox1.Checked := IsPathDelimiter(Edit1.Text, SpinEdit1.Value);
━━━━━━━━━━━━━━━━━━━━━
首部 function IsDelimiter(const Delimiters, S: string; Index: Integer): 
Boolean; $[SysUtils.pas
功能 返回字符串S中指定位置Index上是否是一个分隔符Delimiters
说明 IsDelimiter('@', 'wjhu111@21cn.com', 8) = True
参考 function SysUtils.ByteType
例子 CheckBox1.Checked := IsDelimiter(Edit1.Text, Edit2.Text, 
SpinEdit1.Value);
━━━━━━━━━━━━━━━━━━━━━
首部 function IncludeTrailingPathDelimiter(const S: string): string; 
$[SysUtils.pas
功能 返回包括最后路径分隔符
说明 最后一个字符是路径分隔符则不变;否则加上一个路径分隔符返回
参考 function SysUtils.IsPathDelimiter;function System.Length
例子 Edit1.Text := IncludeTrailingPathDelimiter(Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function IncludeTrailingBackslash(const S: string): string; platform; 
$[SysUtils.pas
功能 返回包括最后斜线
说明 Result := IncludeTrailingPathDelimiter(S);
参考 function SysUtils.IncludeTrailingPathDelimiter
例子 Edit1.Text := IncludeTrailingBackslash(Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function ExcludeTrailingPathDelimiter(const S: string): string; 
$[SysUtils.pas
功能 返回排除最后路径分隔符
说明 最后一个字符不是路径分隔符则不变;否则减去最后的路径分隔符返回
参考 function SysUtils.IsPathDelimiter;function System.Length;function 
System.SetLength
例子 Edit1.Text := ExcludeTrailingPathDelimiter(Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function ExcludeTrailingBackslash(const S: string): string; platform; 
$[SysUtils.pas
功能 返回排除最后斜线
说明 Result := ExcludeTrailingPathDelimiter(S)
参考 function SysUtils.ExcludeTrailingPathDelimiter
例子 Edit1.Text := ExcludeTrailingBackslash(Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function LastDelimiter(const Delimiters, S: string): Integer; 
$[SysUtils.pas
功能 返回最后一个分隔符的位置
说明 LastDelimiter('.', 'kingron.myetang.com') = 16
参考 function SysUtils.StrScan;function SysUtils.ByteType
例子 SpinEdit1.Value := LastDelimiter(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function AnsiCompareFileName(const S1, S2: string): Integer; 
$[SysUtils.pas
功能 返回比较两个文件名
说明 当S1>S2返回值>0;当S1<S2返回值<0;当S1=S2返回值=0;区分大小写
参考 function SysUtils.AnsiCompareStr
例子 SpinEdit1.Value := AnsiCompareFileName(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function SameFileName(const S1, S2: string): Boolean; $[SysUtils.pas
功能 返回两个文件名是否相等
说明 区分大小写
参考 function SysUtils.AnsiCompareFileName
例子 CheckBox1.Checked := SameFileName(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiLowerCaseFileName(const S: string): string; $[SysUtils.pas
功能 返回小写文件名
说明 在非多字节字符系统上相当于AnsiLowerCase
参考 function SysUtils.AnsiLowerCase
例子 Edit2.Text := AnsiLowerCaseFileName(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiUpperCaseFileName(const S: string): string; $[SysUtils.pas
功能 返回大写文件名
说明 在非多字节字符系统上相当于AnsiUpperCase
参考 function SysUtils.AnsiUpperCase
例子 Edit2.Text := AnsiUpperCaseFileName(Edit1.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function AnsiPos(const Substr, S: string): Integer; $[SysUtils.pas
功能 返回子串Substr在字符中第一次出现的位置
说明 不存在则返回0
参考 SysUtils.AnsiStrPos
例子 SpinEdit1.Value := AnsiPos(Edit1.Text, Edit2.Text);
━━━━━━━━━━━━━━━━━━━━━ 
首部 function AnsiStrPos(Str, SubStr: PChar): PChar; $[SysUtils.pas
功能 返回指针子串Substr在指针字符中第一次出现的指针位置
说明 不存在则返回nil
参考 function SysUtils.StrByteType
例子 Edit3.Text := AnsiStrPos(PChar(Edit1.Text), PChar(Edit2.Text));
━━━━━━━━━━━━━━━━━━━━━ 
首部 function AnsiStrRScan(Str: PChar; Chr: Char): PChar; $[SysUtils.pas
功能 返回在指针字符串Str搜索字符Chr最后一个出现的地址
说明 支持多字节字符系统;AnsiStrRScan('kingron.myetang.com', '.') = '.com'
参考 function SysUtils.AnsiStrScan
例子 Edit2.Text := AnsiStrScan(PChar(Edit1.Text), '.');
━━━━━━━━━━━━━━━━━━━━━
首部 function AnsiStrScan(Str: PChar; Chr: Char): PChar; $[SysUtils.pas
功能 返回在指针字符串Str搜索字符Chr第一个出现的地址
说明 支持多字节字符系统;AnsiStrRScan('kingron.myetang.com', '.') = '.myetang.com'
参考 function SysUtils.StrScan
例子 Edit2.Text := AnsiStrScan(PChar(Edit1.Text), '.');
━━━━━━━━━━━━━━━━━━━━━
首部 function StringReplace(const S, OldPattern, NewPattern: string; Flags: 
TReplaceFlags): string; $[SysUtils.pas
功能 返回替换后的字符串
说明 rfReplaceAll为替换全部内容;rfIgnoreCase为忽略大小写
参考 function SysUtils.AnsiUpperCase;function SysUtils.AnsiPos;function 
System.Copy
例子
///////Begin StringReplace
procedure TForm1.Button1Click(Sender: TObject);
begin
Memo1.Lines.Values['[]'] :=
StringReplace(Edit1.Text, Edit2.Text, Edit3.Text, []);
Memo1.Lines.Values['[rfReplaceAll]'] :=
StringReplace(Edit1.Text, Edit2.Text, Edit3.Text, [rfReplaceAll]);
Memo1.Lines.Values['[rfIgnoreCase]'] :=
StringReplace(Edit1.Text, Edit2.Text, Edit3.Text, [rfIgnoreCase]);
Memo1.Lines.Values['[rfReplaceAll, rfIgnoreCase]'] :=
StringReplace(Edit1.Text, Edit2.Text, Edit3.Text, [rfReplaceAll, 
rfIgnoreCase]);
end;
///////End StringReplace
━━━━━━━━━━━━━━━━━━━━━
首部 function StringToGUID(const S: string): TGUID; $[SysUtils.pas
功能 返回字符串S转换成全局标识
说明 如果字符串非法将触发异常
参考 fuction Windows.Succeeded
例子 Edit2.Text := GUIDToString(StringToGUID(Edit1.Text));
━━━━━━━━━━━━━━━━━━━━━
首部 function GUIDToString(const GUID: TGUID): string; $[SysUtils.pas
功能 返回全局标识GUID转换成字符串
说明 <NULL>
参考 fuction Windows.Succeeded
例子 Edit2.Text := GUIDToString(StringToGUID(Edit1.Text));
━━━━━━━━━━━━━━━━━━━━━  