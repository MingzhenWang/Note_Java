## 第6章 接口、lambda表达式与内部类


* 到目前为止，已经学习了Java面向对象程序设计的全部基本知识。
* 本章将开始介绍几种常用的高级技术。这些内容可能不太容易理解，但一定要掌握它们， 以便完善自己的Java 工具箱。

**接口（ interface) 技术**：主要用来描述类具有什么功能，而并不给出每个功能的具体实现。
* 一个类可以实现（ implement) —个或多个接口，并在需要接口的地方， 随时使用实现了相应接口的对象。

**lambdba表达式**：这是一种表示可以在将来某个时间点执行的代码块的简洁方法。
* 使用lambda 表达式，可以用一种精巧而简洁的方式表示使用回调或变量行为的代码。

**内部类（ inner class) 机制**。理论上讲，内部类有些复杂
* 内部类定义在另外一个类的内部， 其中的方法可以访问包含它们的外部类的域
* 内部类技术主要用于设计具有相互协作关系的类集合。

**代理（proxy)**：这是一种实现任意接口的对象。代理是一种非常专业的构造工具，它可以用来构建系统级的工具。（如果是第一次学习这本书， 可以先跳过这个部分）

### 6.1 接口

#### 6.1.1 接口概念

* 在Java中，**接口不是类，而是对类的一组需求描述**，这些类要遵从接口描述的统一格式进行定义。

>示例：Arrays类中的sort方法承诺可以对对象数组进行排序，但要求满足下列前提：对象所属的类必须实现了Comparable接口。
```java
//下面是Comparable接口的代码：
public interface Comparable
{
    int compareTo(Object other);
}
```
>这意味着，任何实现Comparable接口的类都需要包含compareTo方法，并且这个方法的参数必须是一个Object对象，返回一个整型数值。

>注释： 在JavaSE 5.0 中，Comparable 接口已经改进为泛型类型。
public interface Comparable<T>
{
    int compareTo(T other);//parameter has type T
}
例如，在实现Comparable<Employee> 接口的类中， 必须提供下列方法
int compareTo(Employee other)
还可以使用不带类型参数的“ 原始” Comparable 类型。这样一来， compareTo 方法就有一个Object 类型的参数， 必须手动将compareTo 方法的这个参数强制转换为所希望的类型,， 稍后我们就会做这个工作， 所以不用担心同时出现两个新概念。

**接口中所有的方法都自动地属于public，因此在接口中声明方法时，不必提供关键字public**

**接口中还有一个没有明确说明的附加要求**：
>在调用x.compareTo(y) 的时候，这个compareTo 方法必须确实比较两个对象的内容，并返回比较的结果。当x 小于y 时，返回一个负数；当x 等于y 时，返回0；否则返回一个正数。

**接口可以包含多个方法，可以定义常量**

**2、接口不能提供哪些功能**：
* 接口绝不能含有实例域 
* 在JavaSE 8 之前， 也不能在接口中实现方法。（Java8中这些方法不能引用实例域，接口没有实例。）

**可以将接口看成没有实例域的抽象类**：因为提供实例域和方法实现的任务应该由实现接口的那个类来完成。

**为了让类实现一个接口，需要使用implements关键字**，通常需要下面两个步骤：
* 将类声明为实现给定的接口
* 对接口中的所有方法进行定义

>现在， 假设希望使用Arrays 类的sort 方法对Employee 对象数组进行排序， Employee 类就必须实现Comparable 接口。

>使用了静态Double.compare 方法，如果第一个参数小于第二个参数，它会返回一个负值；如果二者相等则返回0；否则返回一个正值。
```java
class Employee implements Comparable
{
    public int compareTo(Object otherObject)
    {
        Employee other = (Employee) otherObject;
        return Double.compare(salary, other.salary);
    }
}
```


>**警告**：在实现接口时， 必须把方法声明为public；否则， 编译器将认为这个方法的访问属性是包可见性（即类的默认访问属性），之后编译器就会给出试图提供更严格的访问权限的警告信息。

可以优化写法，为泛型Comparable接口提供一个类型参数：
```java
class Employee implements Comparable<Employee>
{
    public int compareTo(Employee otherObject)
    {
        //Employee other = (Employee) otherObject;
        //去除类型转换
        return Double.compare(salary, other.salary);
    }
}
```

**为什么不能在Employee 类直接提供一个compareTo 方法，而必须实现Comparable 接口呢？**

* Java 程序设计语言是一种强类型（ strongly typed) 语言。在调用方法的时候，编译器将会检查这个方法是否存在。

在sort 方法中可能存在下面这样的语句：
```java
if(a[i].compareTo(a[j]) > 0)
{
    // rearrange a[i] and a[j]
    ...
}
```

>为此， 编译器必须确认a[i]—定有compareTo 方法。如果a 是一个Comparable 对象的数组， 就可以确保拥有compareTo 方法，因为每个实现Comparable 接口的类都必须提供这个方法的定义。

```java
API java.lang.Comparable<T> 1.0
    int compareTo(T other)
        用这个对象与other进行比较。如果这个对象小于other则返回负值；如果相等则返回0； 否则返回正值。

API java.util.Arrays 1.2
    static void sort(Object[] a)
        使用mergesort算法对数组a中的元素进行排序。要求数组中的元素必须属于实现了Comparable接口的类，并且元素之间必须是可比较的。

API java.lang.lnteger 1.0
    static int compare(int x, int y) 7
        如果x < y 返回一个负整数；如果x 和y 相等，则返回0; 否则返回一个正整数。

API java.lang.Double 1.0
    static int compare(double x, double y) 1.4
        如果x < y 返回一个负数；如果x 和y 相等则返回0; 否则返回一个正数。
```
 
#### 6.1.2 接口特性

1、接口不是类，不能使用new运算符实例化一个接口
x = new Comparable(. . .); //ERROR

2、不能构造接口的对象，但可以声明接口的变量
Comparable x; //OK

接口变量必须引用实现了接口的类对象
x = new Employee(. . .); //OK provided Employee implements Comparable

3、使用instance 检查一个对象是否实现了某个特定的接口
如同使用instanceof 检查一个对象是否属于某个特定类一样， 也可以使用instance 检查一个对象是否实现了某个特定的接口：
if(anObject instanceof Comparable) { . . . }

4、接口可以被扩展
允许存在 多条 从具有较高通用性的接口 到 较高专用性的接口 的链。

例如， 假设有一个称为Moveable 的接口：
public interface Moveable
{
    void move(double x, double y);
}
然后， 可以以它为基础扩展一个叫做Powered 的接口：
public interface Powered extends Moveable
{
    double milesPerGallon();
}

5、接口不能包含实例域或静态方法，但可以包含常量
public interface Powered extends Moveable
{
    double milesPerGallon();
    double SPEED_LIMIT = 95;// a public static final constant
}

接口中的 方法被自动设置为public，接口中的域也被自动设置为public static final 

注释：可以将接口方法标记为public, 将域标记为public static final。但Java 语言规范却建议不要书写这些多余的关键字。

6、有些接口只定义了常量， 而没有定义方法。
例如， 在标准库中有一个SwingConstants就是这样一个接口， 其中只包含NORTH、SOUTH 和HORIZONTAL 等常量。任何实现
SwingConstants 接口的类都自动地继承了这些常量， 并可以在方法中直接地引用NORTH，而不必采用SwingConstants.NORTH 这样的繁琐书写形式。然而，这样应用接口似乎有点偏离了接口概念的初衷， 最好不要这样使用它。

7、尽管每个类只能够拥有一个超类， 但却可以实现多个接口
这就为定义类的行为提供了极大的灵活性。

例如，Java 程序设计语言有一个非常重要的内置接口， 称为Cloneable ( 将在6.2.3 节中给予详细的讨论)。 
如果某个类实现了这个Cloneable 接口，Object 类中的clone 方法就可以创建类对象的一个拷贝。如果希望自己设计的类拥有克隆和比较的能力， 只要实现这两个接口就可以了。使用逗号将实现的各个接口分隔开。
class Employee implements Cloneable,Comparable

#### 6.1.3 接口与抽象类

为什么Java 程序设计语言还要不辞辛苦地引入接口概念？ 为什么不将Comparable 直接设计成如下所示的抽象类？
abstract class Comparable // why not?
{
    public abstract int compareTo(Object other);
}
然后， Employee 类再直接扩展这个抽象类， 并提供compareTo 方法的实现：
class Employee extends Comparable // why not?
{
    public int compareTo(Object other) { . . . }
}

因为使用抽象类，每个类只能扩展于一个类
class Employee extends Person, Comparable // Error

但是每个类可以实现多个接口
class Employee extends Person implements Comparable // OK


注释：有些程序设计语言允许一个类有多个超类， 例如C++。我们将此特性称为多重继承( multiple inheritance)。 
而Java 的设计者选择了不支持多继承，其主要原因是多继承会让语言本身变得非常复杂（如同C++)，效率也会降低（如同Eiffel)
实际上， 接口可以提供多重继承的大多数好处，同时还能避免多重继承的复杂性和低效性。

#### 6.1.4 静态方法

在Java SE 8 中，允许在接口中增加静态方法。理论上讲，没有任何理由认为这是不合法的。只是这有违于将接口作为抽象规范的初衷。

目前为止（Java SE 8之前）， 通常的做法都是将静态方法放在伴随类中。在标准库中， 你会看到成对出现的接口和实用工具类， 如Collection/Collections 或Path/Paths。

下面来看Paths 类， 其中只包含两个工厂方法。可以由一个字符串序列构造一个文件或目录的路径， 如
Paths.get("jdk1.8.0", "jre", "bin");

在Java SE 8 中， 可以为Path 接口增加以下方法：
public interface Path
{
    public static Path get(String first, String... more) 
    {
        return Fi1eSystems.getDefault().getPath(first, more);
    }
}
这样一来， Paths 类就不再是必要的了。

不过整个Java 库都以这种方式重构也是不太可能的， 但是实现你自己的接口时，不再需要为实用工具方法另外提供一个伴随类。


#### 6.1.5 默认方法

可以为接口方法提供一个默认实现。必须用default修饰符标记这样一个方法。

public interface Comparable<T>
{
    //by default, all elements are the same
    default int compareTo(T other) {return 0;}
}

Comparable的每一个实际实现都要覆盖这个方法。

在某些情况下，默认方法可能很有用，例如，在第11章会看到，如果希望在发生鼠标点击事件时得到通知，就要实现一个包含5个方法的接口：
public interface MouseListener
{
    void mouseClicked(MouseEvent event);
    void mousePressed(MouseEvent event);
    void mouseReleased(MouseEvent event);
    void mouseEntered(MouseEvent event);
    void mouseExited(MouseEvent event);
}

大多数情况下， 你只需要关心其中的1、2 个事件类型。
在Java SE 8 中， 可以把所有方法声明为默认方法， 这些默认方法什么也不做。
public interface MouseListener
{
    default void mouseClicked(MouseEvent event) {};
    default void mousePressed(MouseEvent event) {};
    default void mouseReleased(MouseEvent event) {};
    default void mouseEntered(MouseEvent event) {};
    default void mouseExited(MouseEvent event) {};
}

这样一来，实现这个接口的只需要为他们真正关心的事件覆盖相应的监听器。

默认方法可以调用任何其他方法。例如， Collection 接口可以定义一个便利方法，这样实现Collection 的程序员就不用操心实现isEmpty 方法了。
public interface Collection
{
    int size();//An abstract method
    default boolean isEmpty()
    {
        return size() == 0;
    }
}

注释： 在JavaAPI 中， 你会看到很多接口都有相应的伴随类，这个伴随类中实现了相应接口的部分或所有方法， 如CoUection/AbstractCollectkm 或MouseListener/MouseAdapter。在JavaSE 8 中， 这个技术已经过时。现在可以直接在接口中实现方法。

默认方法的一个重要用法是 “接口演化”（interface evolution)。
 以Collection 接口为例，这个接口作为Java 的一部分已经有很多年了。假设很久以前你提供了这样一个类：
public class Bag implements Collection
后来， 在JavaSE 8 中， 又为这个接口增加了一个stream 方法。

假设stream 方法不是一个默认方法。那么Bag 类将不能编译， 因为它没有实现这个新方法。
为接口增加一个非默认方法不能保证“ 源代码兼容”（source compatible）

不过， 假设不重新编译这个类， 而只是使用原先的一个包含这个类的JAR 文件。这个类仍能正常加载，尽管没有这个新方法。程序仍然可以正常构造Bag 实例， 不会有意外发生。( 为接口增加方法可以保证“ 二进制兼容”）。不过， 如果程序在一个Bag 实例上调用stream方法，就会出现一个AbstractMethodError。

将方法实现为一个默认方法就可以解决这两个问题。Bag 类又能正常编译了。另外如果没有重新编译而直接加载这个类， 并在一个Bag 实例上调用stream 方法， 将调用Collection.stream 方法。


#### 6.1.6 解决默认方法冲突
如果先在一个接口中将一个方法定义为默认方法， 然后又在超类或另一个接口中定义了同样的方法， 会发生什么情况？

java中规则如下：
	• 超类优先
		○ 如果超类提供了一个具体的方法，同名而且具有相同参数类型的默认方法会被忽略。
	• 接口冲突
		○ 如果一个超接口提供了一个默认方法， 另一个接口提供了一个同名而且参数类型（不论是否是默认参数）相同的方法， 必须在实现时覆盖这个方法来解决冲突。

超类优先原则

“类优先” 规则可以确保与Java SE 7 的兼容性。如果为一个接口增加默认方法，这对于有这个默认方法之前能正常工作的代码不会有任何影响。


如果有一个类同时实现了这两个接口会怎么样呢？
class Student implements Person, Named
{
    
}
类会继承Person 和Named 接口提供的两个不一致的getName 方法。此时，Java 编译器会报告一个错误，让程序员来解决这个二义性。只需要在Student 类中提供一个getName 方法。在这个方法中，可以选择两个冲突方法中的一个， 如下所示：
class Student implements Person, Named
{
    public String getName(){ return Person.super.getName();}
}

Java 设计者更强调一致性。两个接口如何冲突并不重要。
如果至少有一个接口提供了一个实现， 编译器就会报告错误， 而程序员就必须解决这个二义性。

注释：如果两个接口都没有为共享方法提供默认实现， 那么就与Java SE 8 之前的情况一样，这里不存在冲突。实现类可以有两个选择：实现这个方法， 或者干脆不实现。如果是后一种情况， 这个类本身就是抽象的。


### 6.2 接口示例


### 6.3 lambda表达式

### 6.4 内部类


### 6.5 代理

