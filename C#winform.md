C#
===

winform
---

###CLR FCL IL
CLR是公共语言运行时，Common Language Runtime)和Java虚拟机一样也是一个运行时环境，它负责资源管理（内存分配和垃圾收集），并保证应用和底层操作系统之间必要的分离。

.net框架中包括有一组.net框架类库（Framework Class Library,简称FCL）程序集，其中含 有几千个类型的定义，每个类型都提供了某种功能。

IL称为(interpretative language 解释语言)。

assembly, 这里把它翻译为配件, 以示和组件(Component)加以区别。

####（CLR-Via-C#） 类型基础
CLR要求每个类型最终都派生自System.Object
Object提供的公共方法：
* Equals: 如果两个对象具有相同的值，就返回true
* GetHashCode: 返回对象的哈希码
* ToString：默认返回类型的完整名称（this.GetType().FullName）
* GetType: 返回从type派生的一个实例

object的protected方法：
* MemberwiseClone:这个非虚方法创建类型的新实例，并将新对象的实例字段设与* this的字段完全一致
* Finalize:在垃圾回收器判断对象应该作为垃圾回收之后。在对象的内存被实际回收之前，会调用这个虚方法。需要在回收内存钱执行清理工作的类型，应该重写该方法。

所有对象都需要使用new操作符。
类型转换异常 InvalidCastException。

####is和as
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

----------

C#入门经典
===

OOR:面向对象编程技术
CTS(Common Type System):通用类型系统
CLR(Common Language Runtime):公共语言运行库

CIL(Common Intermediate Language):通用中间语言
JIT(Just-In-Time)编译器

GAC(Global Assembly Cache):全局程序集缓存

