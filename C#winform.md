C#
===

### CLR FCL IL
CLR是公共语言运行时，Common Language Runtime)和Java虚拟机一样也是一个运行时环境，它负责资源管理（内存分配和垃圾收集），并保证应用和底层操作系统之间必要的分离。

.net框架中包括有一组.net框架类库（Framework Class Library,简称FCL）程序集，其中含 有几千个类型的定义，每个类型都提供了某种功能。

IL称为(interpretative language 解释语言)。

assembly, 这里把它翻译为配件, 以示和组件(Component)加以区别。

#### (CLR-Via-C#) 类型基础
CLR要求每个类型最终都派生自System.Object
Object提供的公共方法：
* Equals：如果两个对象具有相同的值，就返回true
* GetHashCode: 返回对象的哈希码
* ToString：默认返回类型的完整名称（this.GetType().FullName）
* GetType: 返回从type派生的一个实例

object的protected方法：
* MemberwiseClone:这个非虚方法创建类型的新实例，并将新对象的实例字段设与this的字段完全一致
* Finalize:在垃圾回收器判断对象应该作为垃圾回收之后。在对象的内存被实际回收之前，会调用这个虚方法。需要在回收内存钱执行清理工作的类型，应该重写该方法。

所有对象都需要使用new操作符。
类型转换异常 InvalidCastException。

#### is和as
is检查一个对象是否兼容于指定的类型，返回Boolean值。注意is操作符永远不会抛异常。is操作符通常这样使用：
```c#
if（o is Employee）
{
  Employee e=(Employee)  0;
  //其他处理...  
}
```
在这段代码中，CLR实际会检查两次对象类型。这是一个相当常用的编程模式，所以C#专门提供了as操作符，目的简化这种代码的写法，同时提升其性能。
```c#
Employee e=o as Employee;
if（e!=null）
{
  //后续其他处理  
}
```
在这段代码中，CLR核实o是否兼容于Employee类型；如果是，as会返回对同一个对象的一个非null引用。如果不兼容，返回null。as操作符造成CLR只校验一次对象的类型。if语句只是检查e是否为null。

-------------------

关键字
---
abstract  抽象
sealed    禁止继承(类似java的final)
internal  内部的

-------------------

Winform
---
    Name
    Text
    Font
    Location
    Size
      MaximumSize
      MinumumSize
    
    Anchor
    Dock
```c#
void  MouseDown();
void  MouseMove();
void  MouseUp();
```

### Form
    AutoScaleMode                               // 窗口缩放
```c#
void    Load();
void    FormClosed();
void    FormClosing();
```

### Panel

### Label
    Alegn

### TextBox

### RichTextBox
```c#
void  Select(SelectionStart, SelectionLength);
void  ScrollToCaret();

void  TextChanged();
```

### Button

```c#
void  Click();
```

### CombBox
    Items
    DropDownStyle

    SelectedIndex
    SelectedItem

### CheckedListBox
    Items

    SelectedItem
    SelectedItems
```c#
void    SetItemChecked();
bool    GetItemChecked();

void    ItemCheck();
void    SelectedIndexChanged();
void    SelectedValuedChanged();
```

### NumericUpDown
    DecimalPlaces
    Increment
    Maximum
    Minimum

```c#
void    ValueChanged();
```

### DataGridView
    SelectionMode
    CellStyle
    VitualMode

    FirstDisplayedScrollingRowIndex
```c#
void CellValueNeeded();
void CellFormatting();
void Invalidate();
void InvalidateRow();
void InvalidateColumn();
void InvalidateCell();
```

### Chart
    Series
        Name
        LegendText
        ChartArea
        ChartType
        XValueType
    ChartAreas
        AxisX
            IsLabelAutoFit
        AxisY

### GroupBox

### StatusStrip
    RightToLeft

### FlowLayoutPanel

### DateTimePicker

### ProgressBar

### TrackBar

### FolderBrowerDialog
    Description
    RootFolder
    SelectedPath
    ShowNewFolderButton
```c#
DialogResult  ShowDialog();
```

### OpenFileDialog
    FileName
    Filter
    FilterIndex
    RestoreDirectory
```c#
DialogResult  ShowDialog();
```

### BackgroundWorker
    WorkerReportsProgress
```c#
void  DoWork();
void  ProgressChanged();
void  RunWorkerCompleted();
```

### Timer
    Interval

-------------------

C#入门经典
===

OOR:面向对象编程技术
CTS(Common Type System):通用类型系统
CLR(Common Language Runtime):公共语言运行库

CIL(Common Intermediate Language):通用中间语言
JIT(Just-In-Time)编译器

GAC(Global Assembly Cache):全局程序集缓存

GC(garbage collection):垃圾回收

OOP(Object-Oriented Programming):面向对象编程
UML(Universal Modeling Language):通用建模语言 

 类型

    sbyte   System.SByte
    byte    System.Byte
    short   System.Int16
    ushort  System.UInt16
    int     System.Int32
    uint    System.UInt32   u U
    long    System.Int64    l L
    ulong   System.UInt64   ul UL
    float   System.Single   f F
    double  System.Double   d D
    decimal System.Decimal  m M
    char    System.Char
    bool    System.Boolean
    string  System.String

占位符
```c#
Console.WriteLine("{0} {1}", myString, myInteger);
```

string.Trim()
string.Pad()
@字符串
```c#
"C:\\Temp\\MyDir\\MyFile.doc"
@"C:\Temp\MyDir\MyFile.doc"
```

溢出检查关键字
Solution Explorer->Properties->Build->Advanced->Check for arithmetic overflow/underflow

    checked
    unchecked

总进行溢出检查

    Convert.ToBoolean(val)
    Convert.ToByte(val)
    Convert.ToChar(val)
    Convert.ToDecimal(val)
    Convert.ToDouble(val)
    Convert.ToInt16(val)
    Convert.ToInt32(val)
    Convert.ToInt64(val)
    Convert.ToSByte(val)
    Convert.ToSingle(val)
    Convert.ToString(val)
    Convert.ToUInt16(val)
    Convert.ToUInt32(val)
    Convert.ToUInt64(val)

委托：存储函数引用的类型
delegate

Console.WriteLine()
Debug.Write()
Trace.Write()
Debug.WriteLine(<message>, <category>)
Trace.WriteLine(<message>, <category>)
<category>:<message>
Debug.WriteIf()
Trace.WriteIf()
Debug.WriteLineIf()
Trace.WriteLineIf()

事件

类
类库
结构是值类型

System.Object
```c#
Object()
~Object()     Finalize()
bool          Equals()
bool          ReferenceEquals()
string        ToString()
object        MemberwiseCline()
System.Type   GetType()
int           GetHashCode()
```

|:-:|
|ClassName|
|:-|
|+Name1:Type|
|-Name2:Type|
|+Func(Type name):Type|
+表示公有成员，-表示私有成员

IDisposable         Dispose()
