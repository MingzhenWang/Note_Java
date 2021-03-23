<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [第3章 Java的基本程序设计结构](#%E7%AC%AC3%E7%AB%A0-java%E7%9A%84%E5%9F%BA%E6%9C%AC%E7%A8%8B%E5%BA%8F%E8%AE%BE%E8%AE%A1%E7%BB%93%E6%9E%84)
  - [3.1 一个简单的Java应用程序](#31-%E4%B8%80%E4%B8%AA%E7%AE%80%E5%8D%95%E7%9A%84java%E5%BA%94%E7%94%A8%E7%A8%8B%E5%BA%8F)
  - [3.2 注释](#32-%E6%B3%A8%E9%87%8A)
  - [3.3 数据类型](#33-%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B)
    - [3.3.1 整型](#331-%E6%95%B4%E5%9E%8B)
    - [3.3.2 浮点类型](#332-%E6%B5%AE%E7%82%B9%E7%B1%BB%E5%9E%8B)
    - [3.3.3 char类型](#333-char%E7%B1%BB%E5%9E%8B)
    - [3.3.4 Unicode和char类型](#334-unicode%E5%92%8Cchar%E7%B1%BB%E5%9E%8B)
    - [3.3.5 boolean类型](#335-boolean%E7%B1%BB%E5%9E%8B)
  - [3.4 变量](#34-%E5%8F%98%E9%87%8F)
    - [3.4.1 变量初始化](#341-%E5%8F%98%E9%87%8F%E5%88%9D%E5%A7%8B%E5%8C%96)
    - [3.4.2 常量](#342-%E5%B8%B8%E9%87%8F)
  - [3.5 运算符](#35-%E8%BF%90%E7%AE%97%E7%AC%A6)
    - [3.5.1 数学函数与常量](#351-%E6%95%B0%E5%AD%A6%E5%87%BD%E6%95%B0%E4%B8%8E%E5%B8%B8%E9%87%8F)
    - [3.5.2 数值类型之间的转换](#352-%E6%95%B0%E5%80%BC%E7%B1%BB%E5%9E%8B%E4%B9%8B%E9%97%B4%E7%9A%84%E8%BD%AC%E6%8D%A2)
    - [3.5.3 强制类型转换](#353-%E5%BC%BA%E5%88%B6%E7%B1%BB%E5%9E%8B%E8%BD%AC%E6%8D%A2)
    - [3.5.4 结合赋值和运算符](#354-%E7%BB%93%E5%90%88%E8%B5%8B%E5%80%BC%E5%92%8C%E8%BF%90%E7%AE%97%E7%AC%A6)
    - [3.5.5 自增与自减运算符](#355-%E8%87%AA%E5%A2%9E%E4%B8%8E%E8%87%AA%E5%87%8F%E8%BF%90%E7%AE%97%E7%AC%A6)
    - [3.5.6 关系和boolean运算符</span>](#356-%E5%85%B3%E7%B3%BB%E5%92%8Cboolean%E8%BF%90%E7%AE%97%E7%AC%A6span)
    - [3.5.7 位运算符](#357-%E4%BD%8D%E8%BF%90%E7%AE%97%E7%AC%A6)
    - [3.5.8 括号与运算符级别](#358-%E6%8B%AC%E5%8F%B7%E4%B8%8E%E8%BF%90%E7%AE%97%E7%AC%A6%E7%BA%A7%E5%88%AB)
    - [3.5.9 枚举类型](#359-%E6%9E%9A%E4%B8%BE%E7%B1%BB%E5%9E%8B)
    - [3.6 字符串](#36-%E5%AD%97%E7%AC%A6%E4%B8%B2)
    - [3.6.1 子串](#361-%E5%AD%90%E4%B8%B2)
    - [3.6.2 拼接](#362-%E6%8B%BC%E6%8E%A5)
    - [3.6.3 不可变字符串](#363-%E4%B8%8D%E5%8F%AF%E5%8F%98%E5%AD%97%E7%AC%A6%E4%B8%B2)
    - [3.6.4 检测字符串是否相等](#364-%E6%A3%80%E6%B5%8B%E5%AD%97%E7%AC%A6%E4%B8%B2%E6%98%AF%E5%90%A6%E7%9B%B8%E7%AD%89)
    - [3.6.5 空串与Null串](#365-%E7%A9%BA%E4%B8%B2%E4%B8%8Enull%E4%B8%B2)
    - [3.6.6 码点与代码单元](#366-%E7%A0%81%E7%82%B9%E4%B8%8E%E4%BB%A3%E7%A0%81%E5%8D%95%E5%85%83)
    - [3.6.7 String API](#367-string-api)
    - [3.6.8 阅读联机文档](#368-%E9%98%85%E8%AF%BB%E8%81%94%E6%9C%BA%E6%96%87%E6%A1%A3)
    - [3.6.9 构建字符串](#369-%E6%9E%84%E5%BB%BA%E5%AD%97%E7%AC%A6%E4%B8%B2)
  - [3.7 输入输出](#37-%E8%BE%93%E5%85%A5%E8%BE%93%E5%87%BA)
    - [3.7.1 读取输入](#371-%E8%AF%BB%E5%8F%96%E8%BE%93%E5%85%A5)
    - [3.7.3 文件输入与输出](#373-%E6%96%87%E4%BB%B6%E8%BE%93%E5%85%A5%E4%B8%8E%E8%BE%93%E5%87%BA)
    - [3.8 控制流程](#38-%E6%8E%A7%E5%88%B6%E6%B5%81%E7%A8%8B)
    - [3.8.1 块作用域](#381-%E5%9D%97%E4%BD%9C%E7%94%A8%E5%9F%9F)
    - [3.8.2 条件语句](#382-%E6%9D%A1%E4%BB%B6%E8%AF%AD%E5%8F%A5)
    - [3.8.3 循环](#383-%E5%BE%AA%E7%8E%AF)
    - [3.8.4 确定循环](#384-%E7%A1%AE%E5%AE%9A%E5%BE%AA%E7%8E%AF)
    - [3.8.5 多重选择：switch语句](#385-%E5%A4%9A%E9%87%8D%E9%80%89%E6%8B%A9switch%E8%AF%AD%E5%8F%A5)
    - [3.8.6 中断控制流程语句](#386-%E4%B8%AD%E6%96%AD%E6%8E%A7%E5%88%B6%E6%B5%81%E7%A8%8B%E8%AF%AD%E5%8F%A5)
    - [3.9 大数值](#39-%E5%A4%A7%E6%95%B0%E5%80%BC)
    - [3.10 数组](#310-%E6%95%B0%E7%BB%84)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## 第3章 Java的基本程序设计结构

### 3.1 一个简单的Java应用程序


**类名标准的命名规范**：
* **类名**是以**大写字母开头**，如果名字由多个单词组成，每个单词的第一个字母都应该大写（**骆驼命名法**）。

源文件的文件名必须与公共类名相同，并使用.java作为扩展名

### 3.2 注释

Java中有三种注释
* **单行注释**
  * `//` 
* **多行注释**
  * `/* */`（不能嵌套）
* **文档注释**
  * 以`/*`开头、以`*/`结束，可以用来自动地生成文档，如下所示：
	```java
	/**
	* This is the first sample 
	* @version
	* @author
	*/
	```

### 3.3 数据类型

Java是一种**强类型语言**，**必须为每一个变量声明一种类型**;
Java中一共有8种基本类型：
* 4种整型：**int、short、long、byte**
* 2种浮点类型：**float、double**
* 1种用于表示Unicode编码的字符单元的字符类型**char**
* 1种用于表示真值的**boolean**类型。

#### 3.3.1 整型
用于表示没有小数部分的数值，允许是负数，Java提供了4种整型
|类型|存储需求|取值范围|
-|-|-
**int**|4字节|-2147483648 ~ 2147483647（正好超过20亿）
**short**|2字节|-32768 ~ 32767
**long**|8字节|-9223372036854775808 ~ 9223372036854775807
**byte**|1字节|-128 ~ 127，2的8次方，正负分隔
* 长整型有一个后缀L或l(如4000000000L)
* 十六进制有一个前缀0x或0X
* 八进制有一个前缀0
* 从Java7开始，加上前缀0b或者0B表示二进制。
* 从Java7开始，可以为数字字面量加下划线_，如1_000_000表示一百万，易读，java编译器会去除这些下划线。

#### 3.3.2 浮点类型
浮点类型用于表示有小数部分的数值，Java中有两种浮点类型：
|类型|存储需求|取值范围|后缀|
-|-|-|-
float|4字节|大约 ±3.40282347E+38F（有效位数为6~7位）|f、F
double|8字节|大约±1.79769313486231570E+308（有效位数为15位）|无、D、d

* double表示的数值精度是float类型的两倍（双精度数值），绝大部分应用程序使用double类型，float的精度很难满足需求。
* 当需要单精度的库或者存储大量数据时，才会使用float类型。

**可以用十六进制表示浮点数值**
* 例如，

所有浮点数组的计算都遵循IEEE754规范，
下面是用于表示溢出和出错情况的三个特殊的浮点数值：
**正无穷大、负无穷大、NaN（不是一个数字）**

**例如**：
* 一个正整数除以0的结果是正无穷大
* 0/0或者负数的平方根的结果是NaN
* 常量**Double.POSITIVE_INFINITY、Double.NEGATIVE_INFINITY和Double.NaN**(以及相应的Float类型对应的常量)分别表示3个特殊的浮点数值，可以用**Double.IsNaN**(X)来判断X是否等于Double.NaN

* **浮点数值不适合无法接受舍入误差的金融计算**，2.0-1.1的结果是0.899999999999999，不是0.9
因为浮点数值采用二进制表示，二进制无法精确地表示1/10，就像十进制无法精确地表示1/3。
* float和double只能用来做科学计算或者是工程计算，在商业计算中我们要用**java.math.BigDecimal**。使用BigDecimal并且一定要用String来构造。

#### 3.3.3 char类型
**char类型原本用于表示单个字符，现在有些Unicode字符可以用一个char值描述，另一些Unicode字符需要两个char值**

char类型的字面量值要用单引号括起来，'A'表示编码值65对应的字符常量；
char类型的值可以表示为十六进制值，其范围从\u0000到\Uffff。
除了转义序列\u之外，还有一些用于表示特殊字符的转义序列

![](/001-Java核心技术_卷一/Pictures/3001.png)

>备注：转义是当由于技术等原因、无法直接在代码中写出所要的字符时采用的，以多个字符的有序组合来表示原本需要的字符的手段，而转义序列（escape sequence）指在转义时使用的有序字符组合。采用转义序列的原因有很多。比如，显然不能直接把 CRLF 或 HT 这样的字符输入为字符常量，因为键盘上的回车键或制表键只完成自己该做的工作：在源代码文件中换行或跳到下一个制表位置。

#### 3.3.4 Unicode和char类型
>要想弄清char类型，必须了解Unicode编码机制，Unicode打破了传统字符编码机制的限制，解决了不同编码标准的冲突。
##### Unicode编码的发展
* **20世纪80年代初**，人们认为两个字节的代码宽度足够对世界上各种语言的所有字符进行编码，并有足够的空间留给未来扩展。
* **1991年发布了Unicode1.0**，当时仅占用65536个代码值中不到一半的部分。
在设计Java时决定采用16位的Unicode字符集，这样会比使用8位字符集的程序设计语言有很大改进。
* **经过一段时间的发展**，Unicode字符超过了65536个字符，主要原因是增加了大量的汉语、日语和德语中的表意文字。
现在16位的char类型已经不能满足所有Unicode字符的需要了。

**Java语言解决这个问题的基本方法**：
从Java SE 5.0开始
**码点（code point）**：指一个编码表中的某个字符对应的代码值，在Unicode标准中，码点采用**十六进制**书写，并加上**前缀U+**，例如U+0041就是拉丁字母A的码点。
* **Unicode的码点可以分为17个代码级别（code plane）**
  * 第一个代码级别称为基本的多语言级别（basic multilingual plane），码点从U+0000到U+FFFF，其中包括经典的Unicode代码；其余的16个级别码点从U+1000到U+10FFFF，其中包括一些辅助字符（supplementary character）。
* **UTF-16编码采用不同长度的编码表示所有Unicode码点**
  * 在基本的多语言级别中，每个字符用16位表示，通常被称为代码单元（code unit）；而辅助字符采用一对连续的代码单元进行编码。这样构成的编码值落入基本的多语言级别中空闲的2048字节内，通常被称为替代区域（surrogate area）【U+D800 ~ U+DBFF用于第一个代码单元，U+DC00~U+DFFF用于第二个代码单元】，这样设计我们可以迅速判断一个代码单元是一个字符的编码还是一个辅助字符的第一或第二部分。
例如，数学符号八元数集，码点为U+1D546，编码为两个代码单元，U+D835和U+DD46

在Java中，char类型描述了UTF-16编码中的一个代码单元。

强烈建议不要在程序中使用char类型，除非确实需要处理UTF-16代码单元。
最好将字符串作为抽象数据类型处理


#### 3.3.5 boolean类型
布尔类型有两个值：false、true，用来判定逻辑条件，布尔值和整型之间不能相互转换。

### 3.4 变量
在Java中，每个变量都有一个类型（type）；
* 变量名必须是一个**字母开头由字母或数字构成的序列**，
* Java中字母和数字的范围更大
  * **字母**：大小写英文字母、下划线及美元符号'$'，或者某种语言中表示字母的任何Unicode字符。
  * 数字包括0-9以及在某种语言中表示数字的Unicode字符。
* 变量中所有的字符都是有意义的，并且大小写敏感，长度基本没有限制。
* 不能使用Java保留字作为变量名，可以在一行中声明多个变量（int i,j;）

>提示：可以用Character类的isJavaIdentifierStart和isJavaIdentifierPart方法来检查，哪些Unicode中的字符属于Java中的字母。

>提示：尽管'$'是一个合法的Java字符，但是不要在自己的代码中使用，它只用在Java编译器或者其他工具生成的名字中。


#### 3.4.1 变量初始化
声明一个变量之后，必须用赋值语句对变量显式初始化

#### 3.4.2 常量
在Java中，使用关键字**final**指示**常量**
* 例如：**final double CM_PER_INCH = 2.54;**
* 关键字final表示这个常量**只能被赋值一次**，一旦被赋值之后，就不能更改了，习惯上，常量名使用全大写。

**类常量**：可以在一个类的多个方法中使用的常量
* 可以使用关键字**static final**设置一个类常量：
  * **public static final double CM_PER_INCH = 2.54;**
* 类常量定义于main方法的外部

>注意：const是Java保留的关键字，但目前并没有使用

### 3.5 运算符
在Java中，使用算术运算符+ - * / 。
* 当参与运算的两个操作数都是整数时，表示**整数除法**；否则表示**浮点数除法**。
* 整数的求余操作（取模），用%表示。
例如：15/2等于7、15%2等于1、15.0/2等于7.5

>注意：整数被0除将会产生一个异常，浮点数被0除将会到得无穷大或者NaN结果

#### 3.5.1 数学函数与常量
在Math类中包含了各种各样的数学函数：
1. **计算平方根**，使用**sqrt方法**
   * double y = Math.sqrt(x);

2. 在Java中没有**幂运算**，需要使用Math类的**pow方法**
   * double y = Math.pow(x,a);
   * 将y的值设置为x的a次幂。pow方法有两个double类型的参数，其返回结果也是**double**类型

3. **floorMod方法**的目的是解决有关整数余数的问题
   * 考虑n%2，如果n是偶数，结果为0；如果n是奇数，结果为1；如果n为负数，结果为-1，最早制定的规则有问题，因为欧几里得规则规定，余数总是要大于等于0
   * 例如：计算调整一个时钟的位置
![](/001-Java核心技术_卷一/Pictures/3501.png)
floorMod简化了这个问题：floormod(position + adjustment , 12)总会得到0~11之间的数（负除数结果依然是负数）

4. 三角函数

![](/001-Java核心技术_卷一/Pictures/3502.png)

5. Java还提供了两个用于表示**π和e常量**的近似值：
**Math.PI**
**Math.E**

> 注意：源文件顶部加上，import static java.lang.*;  即可在使用方法时，省略Math类名

#### 3.5.2 数值类型之间的转换

数值类型之间的合法转换如下图所示：

![](/001-Java核心技术_卷一/Pictures/3503.png)

实心箭头：表示无信息丢失的转换；虚箭头：表示可能有精度损失的转换。
例如
```java
int n = 123456789;
float f = n; //f=1.23456792E8
```

**为什么int转float会有精度丢失**
>答：int的存储结构是：一个符号位 31个指数位;
>float的存储结构是1个符号位，8个指数位，23个尾数。
>实际上尾数确定了浮点数的精度，而数的大小主要是靠指数位，尾数只有23位，加上省略的那一位便是24位，float只能有24位来确定精度，而int是32位。

当使用上面两个数值进行二元操作时，n是整数，f是浮点数，先要将两个操作数转换为同一类型，然后再计算

* 如果两个操作数有一个是double类型，另一个操作数就会转换成double类型
* 否则，如果其中有一个是float类型，另一个操作数就会转成成float类型
* 否则，如果其中有一个是long类型，另一个操作数就会转成成long类型
* 否则，如果其中有一个是int类型，另一个操作数就会转成成int类型

#### 3.5.3 强制类型转换

int类型会自动转换为double类型，但是，有时候，需要将double转换为int，此时我们使用强类型转换（cast），但是可能会丢失一些信息。

* 例如：double x = 9.997;int n = (int)x; //此时n的值是9
>强制类型转换通过截断小数部分将浮点值转换为整型。

如果想对浮点数进行舍入运算，以便得到最接近的整数，需要使用**Math.round**方法
* 例如：double x = 9.997;int n = (int)Math.round(x); //此时n的值是10

在调用round方法时，仍然需要使用强制类型转换(int)，因为round方法返回的结果是long类型，由于存在信息丢失的可能性，只有使用显示的强制类型转换才能将long类型转换为int类型。

#### 3.5.4 结合赋值和运算符
可以在赋值中使用二元运算符，x += 4
注意：如果运算符得到一个值，其类型与左侧操作数的类型不同，就会发生强制类型转换
例如：如果x是int类型，x += 3.5; 是合法的，
```java
x += 3.5;
x=(int)(x+3.5);
```
#### 3.5.5 自增与自减运算符
++n，先加一，在表达式中
n++，后加一，在表达式中

#### 3.5.6 关系和boolean运算符</span>
**关系运算符**：==、!=、<、>、<=、>=
**逻辑运算符**：&&（与）、||（或）、!（非）
**三元操作符**：?:  若条件为true，就为第一个表达式的值，负责计算称为第二个表达式的值。
>condition ? expression1 :expression2

#### 3.5.7 位运算符
* 位运算符操作数只能是整型和字符型数据。
  * 处理整数类型时，可以直接对组成整型数值的各个位完成操作，这意味着可以使用掩码技术得到整数中的各个位，
* 位移运算符包括：
&（按位与）、|（按位或）、^（按位异或）、~（取反）
这些运算符按位模式处理。
* 例如，如果n是一个整数变量，而且用二进制表示的n从右边数第四位为1，则
int fourthBitFromRight = (n & 0b1000) / 0b1000;
会返回1，否则会返回0。利用&并结合使用适当的2的幂，可以把其他位掩掉，而只保留其中一位。


#### 3.5.8 括号与运算符级别
* 如果不使用圆括号，就按照给出的运算符优先级次序进行计算。
* 同一个级别的运算符按照**从左到右**的次序进行计算（除了**右结合运算符**）。
  * 例如，+=是右结合运算符，所以 a += b += c 等价于 a += (b += c)

#### 3.5.9 枚举类型
* 如果变量的取值只在一个有限的集合内，我们可以自定义枚举类型，枚举类型包含有限个命名的值（0或m个）
```java
enum Size{SMALL, MEDIUM, LARGE, EXTRA_LARGE};
//现在，可以声明这种类型的变量：
Size s = Size.MEDIUM;
```
* Size类型的变量只能存储这个类型声明中给定的某个枚举值，或者NULL值
  * NULL值表示这个变量没有设置任何值。

详细介绍在第5章。

#### 3.6 字符串
* 从概念上将，Java字符串就是Unicode字符序列
>例如；串"Java\u2122"由5个Unicode字符J、a、v、a和™ 组成。

* Java没有内置的字符串类型，而是在标准Java类库中提供了一个**预定义类**，**叫String**。
* 每个用双引号括起来的字符串都是**String类的一个实例**。

#### 3.6.1 子串
String类的substring方法可以从一个较大的字符串提取出一个子串
>substring(m, n)  m表示起始位置（**包含**），n表示终止位置（**不包括**）

例如：
```java
String greeting = "Hello";
String s = greeting.substring(0,3); //从0开始，0,1,2，
```
#### 3.6.2 拼接
* Java语言允许使用+号拼接两个字符串
* 当将**一个字符串与一个非字符串的拼接时**，**后者被转换成字符串**（第五章中可以看到，任何一个Java都可以转换成字符串）：
例如：
```java
int age = 13;
String rating = "PG"+ age；//rating为"PG13"
```
如果需要把多个字符串放在一起，用一个定界符分隔，可以使用静态join方法：
```java
String all  = String.Join("/", "S", "M", "L", "XL"); //all结果为 "S/M/L/XL"
```
#### 3.6.3 不可变字符串
* String类没有提供用于修改字符串的方法
* 如果想修改字符串变量的内容，可以做如下操作：首先提取需要的字符，然后再拼接上替换的字符串：
```java
greeting = greeting.substring(0,3) + "p!";
```
* 由于**不能修改Java字符串中的字符**，所以在Java文档中将String类对象称为**不可变字符串**。
* 字符串"Hello"永远包含字符H、e、l、l和o的代码单元序列，而不能修改其中任何一个字符。我们可以修改字符串变量greeting，让它引用另外一个字符串。

**这样做似乎降低效率，但是不可变字符串有一个优点**：
* **编译器可以让字符串共享**

>各种字符串存放在公共的存储池中，字符串变量指向存储池中相应的位置，如果复制一个字符串变量，原始字符串与复制的字符串共享相同的字符。

>Java的设计者认为，共享带来的效率远胜于提取、拼接字符串所带来的低效率。

#### 3.6.4 检测字符串是否相等
**equls方法**
>检测两个字符串是否相等

```java
s.equals(t)
"Hello".equals(greeting) 
```
>如果字符串s与字符串t相等，则返回true，否则返回false。
>s与t可以是字符串变量，也可以是字符串字面量。

>**字面量**：由字母、数字等构成的字符串或者数值，它只能作为右值出现，所谓右值是指等号右边的值，如：int a=123这里的a为左值，123为右值。


**equalsIgnoreCase方法**
>检测两个字符串是否相等，而不区分大小写
```java
"Hello".equalsIgnoreCase("hello")
```
* **不要使用==运算符检测两个字符串是否相等！**
  * ==运算符只能确定两个字符串是否放在同一位置

>如果虚拟机始终将相同的字符串共享，就可以使用==运算符检测是否相等，但实际上，只有字符串常量是共享的，而+或substring等操作产生的结果并不是共享的。

#### 3.6.5 空串与Null串
空串`""`是长度为0的字符串，检查一个字符串是否为空：
```java
If(str.lenghth() == 0)
或
If(str.equals(""))
```
>空串是一个Java对象，有自己的串长度（0）和内容（空）。

String变量还可以存放null，检查一个字符串是否为null:
```java
If(str==null)
```
>null，表示目前没有任何对象与该变量关联,首先要检查一个字符串是否为null，否则会报错

#### 3.6.6 码点与代码单元
* Java字符串由char值序列组成
* char数据类型是一个**采用UTF-16编码**表示**Unicode码点的代码单元**。
* 大多数的常用Unicode字符使用一个代码单元就可以表示，而辅助字符需要一对代码单元表示

length方法返回采用UTF-16编码表示的**给定字符串所需要的代码单元数量**：
```java
String greeting = "Hello";
int n = greeting.length();//is 5
```
要想得到实际的长度，即码点数量，可以调用：
```java
int cpCount = greeting.codePointCount(0,greeting.length());
```
调用s.charAt(n)将返回位置n的代码单元，n介于0~s.length() -1之间，例如：

```java
String greeting = "Hello";
char first = greeting.charAt(0);//first is h
char last = greeting.charAt(4);//last is o
```

得到第i个码点，应该使用下列语句
```java
int index = greeting.offsetByCodePoints(0,i);//得到码点的位置
int cp = greeting.codePointAt(index);//得到对应的Unicode码点
```

如果想要遍历一个字符串，并且依次查看每一个码点，可以使用下列语句
```java
int cp = sentence.codePointAt(i);
if(Character.isSupplementaryCodePoint(cp)) i+=2;
else i++;
```
>用于确定指定字符(Unicode代码点)是否在补充字符范围内；如果指定的代码点在MIN_SUPPLEMENTARY_CODE_POINT和MAX_CODE_POINT(含)之间，则此方法返回true，否则返回false。

可以使用下列语句实现回退操作：
```java
i--;
if(Character.isSurrogate(sentence.charAt(i))) i--;
int cp = sentence.codePointAt(i);
```
这样操作很麻烦，更容易的方法是使用codePoints方法，它会生成一个int值的流，每个int值对应一个码点。
可以将它转换为一个数组，再完成遍历
```java
int[] codePoints = str.codePoints().toArray();
```
反之，要将一个码点数组转换为一个字符串，可以使用构造函数：
```java
String str = new String(codePoints,0,codePoints.length);
```

#### 3.6.7 String API
Java的String类包含了50多种方法，绝大多数都很有用，下列的API注释汇总了一部分最常用的方法

* java.lang.string 1.0，如果某个方法是在这个版本之后添加的， 就会给出一个单独的版本号。
```java
char charAt(int index)
	返回给定的代码单元。除非对底层的代码单元感兴趣，否则不需要调用这个方法
int codePointAt(int index) 5.0
	返回从给定位置开始的码点
int offsetByCodePoints(int startIndex, int cpCount) 5.0
	返回从startIndex 代码点开始， 位移cpCount 后的码点索引*
int compareTo(String other)
	按照字典顺序， 如果字符串位于other 之前， 返回一个负数；如果字符串位于other 之后，返回一个正数； 如果两个字符串相等，返回0。
IntStream codePoints() 8
	将这个字符串的码点作为一个流返回。调用toArray将它们放在一个数组中。
new String(int[] codePoints, int offset, int count) 5.0
	用数组中从offset开始的count个码点构造一个字符串。
boolean equals(0bject other)
	如果字符串与other相等，返回true。
boolean equalsIgnoreCase(String other)
	如果字符串与other 相等（忽略大小写)，返回true。
boolean startsWith(String prefix)
boolean endsWith(String suffix)
	如果字符串以suffix 开头或结尾，则返回true。
int indexOf (String str)
int indexOf (String str,int fromIndex)
int indexOf (int cp)
int indexOf (int cp, int fromlndex)
	返回与字符串str或代码点cp 匹配的第一个子串的开始位置。这个位置从索引0或fromlndex开始计算。如果在原始始串中不存在str，返回-1。
int lastIndexOf (String str)
int lastIndexOf (String str,int fromIndex)
int lastIndexOf (int cp)
int lastIndexOf (int cp,int fromIndex)
	返回与字符串str或代码点cp匹配的最后一个子串的开始位置。这个位置从原始串尾端或fromlndex 开始计算。
int length()
	返回字符串的长度。
int codePointCount (int startIndex,int endIndex) 5.0
	返回startlndex和endludex-l 之间的代码点数量。没有配成对的代用字符将计入代码点。
String replace(CharSequence oldString,CharSequence newString)
	返回一个新字符串。这个字符串用newString 代替原始字符串中所有的oldString。可以用String或StringBuilder对象作为CharSequence参数。
String substring(int beginIndex)
String substring(int beginIndex,int endIndex)
	返回一个新字符串。这个字符串包含原始字符串中从beginIndex到串尾或endIndex-1的所有代码单元。
String toLowerCase()
String toUpperCase()
	返回一个新字符串。这个字符串将原始字符串中的大写字母改为小写，或者将原始字符串中的所有小写字母改成了大写字母。
String trim()
	返回一个新字符串。这个字符串将删除了原始字符串头部和尾部的空格。
String join(CharSequence delimiter,CharSequence . .. elements) 8
	返回一个新字符串，用给定的定界符连接所有元素。

注释：在API注释中，有一些CharSequence类型的参数。这是一种接口类型，所有字符串都属于这个接口。
```

#### 3.6.8 阅读联机文档

标准库中有几千个类，方法数量更多，要记住所有的方法和类不太可能，因此要学会使用在线API文档
官方API网址：https://www.oracle.com/technetwork/java/api-141528.html

#### 3.6.9 构建字符串

有时候，需要由较短的字符串构建字符串，例如，按键或来自文件中的单词。
* 采用字符串连接的方式效率较低，每次连接字符串，都会构建一个新的String对象，**耗时且浪费空间**。
* 使用**StringBuilder类**可以避免这个问题，用法如下：
```java
StringBuilder builder = new StringBuilder();//首先建立一个空的字符串构建器
builder.append(ch);//附加一个字符
builder.append(str);//附加一个字符串
```
在需要构建字符串时，调用toString方法，将得到一个String对象，其中包含了构建器中的字符序列
```java
String completedString = builder.toString();
```
>注释：在JDK5.0 中引入StringBuilder 类。这个类的前身是StringBuffer , 其效率稍有些低， 但允许采用多线程的方式执行添加或删除字符的操作。如果所有字符串在一个单线程中编辑（通常都是这样)，则应该用StringBuilder 替代它。这两个类的API是相同的。

下面的API注释包含了StringBuilder类中的重要方法：

```java
API：java.lang.StringBuilder 5.0

StringBuilder()
	构造一个空的字符串构建器。
int length()
	返回构建器或缓冲器中的代码单元数量。
StringBuilder append(String str)
	追加一个字符串并返回this。
StringBuilder append(char c)
	追加一个代码单元并返回this。
StringBuilder appendCodePoint(int cp)
	追加一个代码点，并将其转换为一个或两个代码单元并返回this。
void setCharAt(int i,char c)
	将第i个代码单元设置为c。
StringBuilder insert(int offset,String str)
	在offset位置插入一个字符串并返回this。
StringBuilder insert(int offset,Char c)
	在offset 位置插入一个代码单元并返回this。
StringBuilder delete(int startindex,int endlndex)
	删除偏移量从startindex 到-endlndex-1 的代码单元并返回this。
String toString()
	返回一个与构建器或缓冲器内容相同的字符串
```

### 3.7 输入输出
#### 3.7.1 读取输入
* 调用**System.out.println**，即可打印输出到“标准输出流”（控制台窗口）
* 如何读取“标准输入流”System.in
  * 首先需要构造一个Scanner对象，并与“标准输入流”System.in关联。
  * 之后可以使用Scanner类的各种方法实现输入操作。

>Scanner类定义在java.util包中，当使用的类不是定义在基本java.lang包中时，一定要使用import指示字将相应的包加载进来。
```java
Import java.util.*

Scanner in = new Scanner(System.in);
System.out.print("What's your name?");
String name = in.nextLine();//输入一行，读取一行的输入
String firstName = in.next();//读取一个单词，以空白符作为分隔符
System.out.print("How old are you?");
int age = in.nextInt();//读取一个整数，读取下一个浮点数-nextDouble()
```
>注释： 因为输入是可见的， 所以Scanner 类不适用于从控制台读取密码。Java SE 6 特别引入了Console 类实现这个目的。要想读取一个密码， 可以采用下列代码：
```java
Console cons = System.console();
String username = cons.readLine("User name: ")；
char[] passwd = cons.readPassword("Password:");
```
* 为了安全起见， 返回的密码存放在一维字符数组中， 而不是字符串中。
* 在对密码进行处理之后， 应该马上用一个填充值覆盖数组元素（数组处理将在3.10 节介绍）。
* 采用Console 对象处理输入不如采用Scanner 方便。每次只能读取一行输入， 而没有能够读取一个单词或一个数值的方法。

```java
API-java.util.Scanner 5.0

Scanner (InputStream in)
	用给定的输人流创建一个Scanner 对象。
String nextLine()
	读取输入的下一行内容。
String next()
	读取输入的下一个单词（以空格作为分隔符)。
int nextInt()
double nextDouble()
	读取并转换下一个表示整数或浮点数的字符序列。
boolean hasNext()
	检测输入中是否还有其他单词。
boolean hasNextInt()
boolean hasNextDouble()
	检测是否还有表示整数或浮点数的下一个字符序列。

API-java.lang.System 1.0

static Console console() 6
	如果有可能进行交互操作，就通过控制台窗口为交互的用户返回一个Console 对象，否则返回null。对于任何一个通过控制台窗口启动的程序， 都可使用Console对象。否则， 其可用性将与所使用的系统有关。

API-java.io.Console 6

static char[] readPassword(String prompt, Object...args)
static String readLine(String prompt, Object...args)
	显示字符串prompt 并且读取用户输入，直到输入行结束。args 参数可以用来提供输入格式。有关这部分内容将在下一节中介绍。
```

#### 3.7.2 格式化输出

可以使用System.out.print(x)将数值x输出到控制台。这条命令将以x对应的数据类型所允许的最大非0数字位数打印输出x.

Java SE 5.0 沿用了C语言函数库中的printf方法，例如：
```java
System.out.printf("%8.2f", x);  //可以用8个字符的宽度和小数点后两个字符的精度打印x。
```

**解释：**
1. 每一个以%字符开始的格式说明符都用相应的参数替换。
2. 格式说明符尾部的转换符将指示被格式化的数值类型：f表示浮点数，s表示字符串、d表示十进制整数。表3-5列出了所有转换符。
3. 还可以给出控制格式化输出的各种标志，表3-6给出了所有的标志，可以使用多个分隔符拼在一起。

![](/001-Java核心技术_卷一/Pictures/3701.png)

>注释：可以使用s转换符格式化任意的对象。
对于实现了Formattable几口的对象都将调用formatTo方法，否则将调用toString方法，它可以将对象转换为字符串

* 可以使用静态的String.format 方法创建一个格式化的字符串， 而不打印输出：
```java
String message = String.format ("Hello, %s. Next year , you'll be %d", name , age);
```

![](/001-Java核心技术_卷一/Pictures/3702.png)


**基于完整性的考虑，下面简略地介绍printf方法中日期与时间的格式化选项。**
* **在新代码中，应该使用卷II中第6章介绍的java.time包的方法**。旧的代码中，会有Date类和相关的格式化选项。
* 格式包括两个字母，**以`t`开始**，以表3-7中的任意字母结束。例如：
```java
System.out.printf("%tc", new Date());//打印格式： Mon Feb 09 18:05:19 PST 2015
```
![](/001-Java核心技术_卷一/Pictures/3703.png)

![](/001-Java核心技术_卷一/Pictures/3704.png)


从表3-7 可以看到， 某些格式只给出了指定日期的部分信息。例如，只有日期或月份。如果需要多次对日期操作才能实现对每一部分进行格式化，这种方式太繁琐。

* 可以采用一个格式化的字符串指出要被格式化的参数索引。
* 索引必须紧跟在`%`后面， 并以`$`终止。

```java
System.out.printf("%1$s %2$tB %2$te, %2$tY","Due date:", new Date());

打印
Due date：February 9,2005
```


* 还可以选择使用`<` 标志。它指示前面格式说明中的参数将被再次使用。也就是说，下列语句将产生与前面语句同样的输出结果：
```java
System.out.printf ("%s %tB %<te, %<tY","Due date:" , new Date());
```
>注意：**参数索引从1开始，而不是从0开始**。%1$ 对第一个参数格式化。

语法图如下：

![](/001-Java核心技术_卷一/Pictures/3705.png)

#### 3.7.3 文件输入与输出

**1.文件读取**
如果想要对文件进行读取，就需要一个用File对象构造一个Scanner对象
```java
Scanner in = new Scanner(Paths.get(myfile.txt),"UTF-8");
```
>**注意**：如果文件中包含反斜杠，就需要在反斜杠前再加一个额外的反斜杠

**2.文件写入**
写入文件需要构造一个PrintWriter对象。在构造器中，只需要提供文件名：
```java
//如果文件不存在，创建该文件
PrintWriter out = new PrintWriter("myfile.txt","UTF-8");
```

可以像输出到System.out一样使用print、printf及println命令**覆盖式**添加
```java
PrintWriter out = new PrintWriter("myfile.txt","UTF-8");
out.print("nihao");
out.close();
```
>当指定一个相对文件名时， 例如， “myfile.txt”，“mydirectory/myfile.txt” 或“ ../myfile.txt”，文件位于**Java虚拟机启动路径**的相对位置。

>如果在命令行下启动程序，启动路径就是命令解释器的当前路径。

>如果使用IDE，启动路径将由IDE控制，可以使用如下方式找到路径的位置：
```java
String dir = System.getProperty("myfile.txt");
```

* 如果用一个不存在的文件构造一个Scanner, 或者用一个不能被创建的文件名构造一个PrintWriter,那么就会发生异常。
* Java 编译器认为这些异常比“ 被零除” 异常更严重。现在，应该告知编译器： 已经知道有可能出现“ 输入/输出” 异常。
* 这需要在main 方法中用throws 子句标记， 如下所示：
```java
public static void main(String[] args) throws IOException
{
    Scanner in = new Scanner(Paths.get("myfile.txt"), "UTF-8");
}
```

* 当采用命令行方式启动一个程序时， 可以利用Shell的重定向语法将任意文件关联到System.in 和System.out，这样， 就不必担心处理IOException 异常了。
```java
java MyProg < myfile.txt > output.txt
```


```java
API java.util.Scanner 5.0

Scanner(File f)
	构造一个从给定文件读取数据的Scanner。
Scanner(String data)
	构造一个从给定字符串读取数据的Scanner。

API java.io.PrintWriter 1.1

PrintWriter(String fileName)
	构造一个将数据写入文件的PrintWriter。文件名由参数指定。

API java.nio.file.Paths 7

static Path get(String pathname)
	根据给定的路径名构造一个Path。
```

### 3.8 控制流程

#### 3.8.1 块作用域

**块（block）**：即复合语句，是指由一对大括号括起来的若干条简单的Java语句。
**块确定了变量的作用域**，一个块可以嵌套在另一个块中，但不能在嵌套的两个块中声明同名的变量。

#### 3.8.2 条件语句

在Java中，条件语句的格式如下所示，**else与最邻近的 If 构成一组**
```java
if(condition) statement
if(condition) statement1 else statement2
if(condition) statement1 else if statement2 else statement3
```
#### 3.8.3 循环

当条件为true时，while循环执行一个语句块，一般格式如下：
```java
//while循环语句首先检测循环条件，循环体中的代码有可能不被执行
while(condition) statement
```


如果希望循环体至少执行一次，应该使用do/while，格式如下：
```java
//这种循环语句先执行语句，再检查循环条件
do statement while(condition);
```


#### 3.8.4 确定循环

for循环语句是支持迭代的一种通用结构，利用每次迭代后更新的计数器或类似的变量来控制迭代次数。
* 第一部分，用于对计数器的初始化
* 第二部分，给出每次新一轮循环执行前要检测的循环条件
* 第三部分，指示如何更新计数器

**for循环语句是while循环的一种简化形式**

#### 3.8.5 多重选择：switch语句

* 在处理多个选项时，使用`if/else`结构会有些笨拙且效率不高，此时可以使用`switch`语句
* switch语句将从与选项值相匹配的case标签处执行直到遇到break语句，或者执行到switch语句的结束处为止。
* 如果没有想匹配的case标签，而有default语句，就执行这个子句。
```java
Scanner in = new Scanner(System.in);
int choice = in.nextInt();
switch(choice)
{
    case 1:
    statements;
    break;
    case 2:
    sattements;
    break;
    default:
    statements;
    break;
}
```
**case标签的类型：**
* 类型为char、byte、short或int的常量表达式；
* 枚举常量；
* 从Java SE7开始，支持字符串字面量。

#### 3.8.6 中断控制流程语句

尽管Java的设计者将goto作为保留字，但实际并没有打算使用它。
Java设计者在Java语言中增加了一条带标签的break，以支持这种程序设计风格。

**1、带标签的break语句**

* 用于**跳出多重嵌套**的循环语句
* **标签**必须放在希望跳出的**最外层循环之前**，并且必须**紧跟一个冒号**。
```java
Scanner in = new Scanner(System.in);
int n;
read_data:
while(..)
{
    for(...)
    {
        System.out.print("Enter a number >=0: ");
        n = in.nextInt();
        if(n<0)
            break read_data; 
    }
}
//跳出标签后立即执行如下的语句
if(n < 0)
{
    ...
}
```

可以将标签应用到任何语句中，比如if语句或块语句中
```java
label:
{
    ...
    if(condition) break label;
    ...
}
//jump here when the break statement executes
```
**2、continue语句**
continue语句将控制转移到最内层循环的首部。例如：
```java
//如果n<0，则continue语句越过当前循环体的剩余部分，立即跳转到循环首部
Scanner in = new Scanner(System.in);
while(sum < goal)
{
    System.out.print("Enter a number: ");
    n = in.nextInt();
    if(n<0) continue;
    sum += n;
}
```
如果将continue语句用于for循环中，就可以跳转到for循环的“更新部分”
```java
//如果n<0,则continue语句跳到count++语句
for(count =1; count<=100;count++)
{
    System.out.print("Enter a number, -1 to quit: ");
    n = in.nextInt();
    if(n<0) continue;
    sum += n;
}
```
**还有一种带标签的continue，将跳转到与标签匹配的循环首部**。
* 带标签的break是跳出循环到标签处而继续进行程序后边的语句
* 带标签的continue是直接进行标签处的下一次循环。

### 3.9 大数值

如果基本的整数和浮点数精度不能够满足需求，可以使用**java.math**中包含的两个类：* `BigInteger`和`BigDecimal`，这两个类可以处理包含任意长度数字序列的数值。

* **BigInteger类**实现了**任意精度的整数运算**
* **BigDecimal类**实现了**任意精度的浮点数运算**


```java
//使用静态的valueOf方法可以将普通的数值转换为大数值
BigInteger a = BigInteger.valueOf(100);

//不能使用算术运算符处理大数值，需要使用类中的add和multiply方法
BigInteger c = a.add(b);
BigInteger d = c.multipy(b.add(BigInteger.valueOf(2)));//d=c*(b+2)

```

>**注释**：Java没有提供运算符重载功能，java设计者**为字符串的连接重载了+运算符**，但没有重载其他运算符，也没有给Java程序员在自己的类中重载运算符的机会。

```java
API java.math.BigInteger 1.1
	BigInteger add(BigInteger other)
	BigInteger subtract(BigInteger other)
	BigInteger multiply(BigInteger other)
	BigInteger divide(BigInteger other)
	BigInteger mod(BigInteger other)
		返回这个大整数与另一个大整数other的和、差、积、商以及余数
	int compareTo(BigInteger other)
		如果这个大整数与另一个大整数other相等，返回0；如果这个大整数小于另一个大整数other，返回负数；否则返回正数
	static BigInteger valueOf(long x)
		返回值等于x的大整数

API java.math.BigDecimal 1.1
	BigDecimal add(BigDecimal other)
	BigDecimal subtract(BigDecimal other)
	BigDecimal multiply(BigDecimal other)
	BigDecimal divide(BigDecimal other RoundingMode mode) 5.0
		返回值这个大实数与另一个大实数other的和、差、积、商。
		要想计算商，必须给出舍入方式（round mode），RoundingMode.HALF_UP是四舍五入方式，其他方式请查看API文档
	int compareTo(BigDecimal other)
		如果这个大实数与另一个大实数other相等，返回0；如果这个大实数小于另一个大实数other，返回负数；否则返回正数
	static BigDecimal valueOf(long x)
	static BigDecimal valueOf(long x, int scale)
		返回值为x或x/10scale的一个大实数。sacle用于指定小数点后位数
```

### 3.10 数组

数组是一种数据结构，用来存储同一类型值的集合，通过一个整型下标可以访问数组中的每一个值。


在声明数组变量时，需要指出**数组类型**（数据元素类型紧跟[]）和**数组变量**的名字：
```java
//声明整型数组
int[] a;//int a[];
//初始化创建数组
int[] a = new int[100];//创建一个可以存储100个整数的数组，数组的下标从0-99
```
**初始值**
* 创建一个数字数组，所有元素初始化为0；
* 创建一个Boolean数组，元素初始化为false；
* 对象数组的元素初始化为null值，表示这些数组还未存放任何对象（String）

数组一旦创建，大小不可变，如果需要在运行过程中扩展数组的大小，应该使用另一种数据结构--数组列表（array list）
获取数组中元素的个数：array.length


#### 3.10.1 for each循环
Java中有一种很强的循环结构，可以用来依次处理数组中的每个元素（其他类型的元素集合亦可），而不用指定下标。
这种增强型的for循环格式如下：
for(variable: collection) statement

定义一个变量用于暂存集合中的每一个元素，并执行相应的语句。
collection必须是一个数组或者是一个实现了Iterable接口的类对象（例如ArrayList）
//打印数组a的每一个元素
for(int element:a)
{
    System.out.println(element);
}

提示：有个更简单的打印数组中所有值的方法，调用Arrays类的toString方法，返回一个包含数组元素的字符串，这些元素被放置在括号内并用逗号分隔，例如 “[1,2,3,4]”


#### 3.10.2 数组初始化以及匿名数组
在Java中，提供了一种创建数组对象并赋予初始值的简化书写形式：
int[] smallPrimes = {2,3,4,5,7,13};

甚至还可以初始化一个匿名的数组：
new int[] {13,17,23,29,31,37}

这种表示法将创建一个新数组，并利用括号中提供的值进行初始化，数组的大小就是初始值的个数。
使用这种语法形式可以在不创建新变量的情况下重新初始化一个数组。例如：
smallPrimes = new int[] {13,17,23,29,31,37};

简写形式如下：
int anonymous = {13,17,23,29,31,37};
smallPrimes = anonymous;

注释：在Java中吗，数组长度允许为0。例如结果为数组的方法，结果为空，可以用长度为0的数组表示：
new elementType[0]//长度为0与null不同

#### 3.10.3 数组拷贝
在Java中，允许将一个数组变量拷贝给另一个数组变量，这时，两个变量将引用同一个数组。

如果希望将一个数组的所有值拷贝到一个新的数组中，就要使用Arrays类的copyOf方法：
int[] copiedLuckyNumbers = Arrays.copyOf(luckyNumbers,luckyNumbers.length);
第二个参数是新数组的长度。这个方法通常用来增加数组的大小：
luckyNumbers = Arrays.copyOf(luckyNumbers,2*luckyNumbers.lenght);

如果数组元素是数值型，多余的元素将被赋值0；
如果数组元素是布尔型，则将赋值false；
相反，如果长度小于原始数组的长度，则只拷贝最前面的数据元素。

#### 3.10.4 命令行参数
每一个Java程序都有一个带String args[]参数的main方法。
这个参数表明main方法将接受一个字符串数组，也就是命令行参数。

	• 在启动Java应用程序时可以一次性地向应用程序中传递0~多个参数----命令行参数
	• 命令行参数使用格式： java ClassName  lisa  "bily"  "Mr Brown“
	• 由参数args接收   空格将参数分开  若参数包含空格，用双引号引起来

#### 3.10.5 数组排序
要想对数值型数组进行排序，可以使用Arrays类中的sort方法，
这个方法使用了优化的快速排序算法，对于大多数集合来说效率比较高
int[] a = new int[1000];
...
Arrays.sort(a);

Math.random()方法将返回一个0到1之间（含0不含1）的随机浮点数，用整数n乘以这个浮点数，就可以得到0到n-1之间的一个随机数。

API java.util.Arrays 1.2
	• static String toString(type[] a) 5.0
		○ 返回包含a中数据元素的字符串，这些数据元素被放在括号内，并用逗号分隔。
		○ 参数：a，类型为int、long、short、char、byte、boolean、float或double的数组
	• static type copyOf(type[] a, int length) 6
	• static type copyOfRange(type[] a,int start,int end) 6
		○ 返回与a类型相同的一个数组，其长度为length或者end-start，数组元素为a的值
		○ 参数：a，类型为int、long、short、char、byte、boolean、float或double的数组
		start，起始下表，包含这个值
		end，终止下标（不包含这个值）。这个值可能大于length，这种情况下，结果为0或false；
		length，拷贝的数据元素长度。如果length值大于a.length，结果为0或false;否则，数组中只有前面length个数据元素的拷贝值。
	• static int binarySearch(type[] a, type v)
	• static int binarySearch(type[] a, int start, int end, type v) 6
		○ 采用二分查找值v。如果查找成功，则返回相应的下标值；否则返回一个负数值r。-r-1是为保持a有序v应插入的位置。
		○ 参数：a，类型为int、long、short、char、byte、boolean、float或double的有序数组
			start，起始下标（包含这个值）。
			end，终止下标（不包含这个值）。
			v，同a的数据元素类型相同的值。
	• static void fill(type[] a, type v)
		○ 将数组的所有数据元素值设置为v。
		○ 参数：a，类型为int、long、short、char、byte、boolean、float或double的数组。
			v，与a数据元素类型相同的一个值。
	• static boolean equals(type[] a, type[] b)
		○ 如果两个数组大小相同，并且下标相同的元素都对应相等，返回true。
		○ 参数：a、b，类型为int类型为int、long、short、char、byte、boolean、float或double的数组。


#### 3.10.6 多维数组
多维数组将使用多个下标访问数组元素，它适用于表示表格或更加复杂的排列形式。
声明二维数组：double[][] balances;
初始化二维数组：balances = new double[NYEARS][NRATES];

若知道数组元素，可以使用简化的形式对多维数组进行初始化：
int[][] magicSquare = 
{
    {16,3,2,13},
    {5,10,11,8},
    {9,6,7,12},
    {4,15,11,1}
};
数组初始化后，可以利用两个方括号访问每个元素，例如，balances[i][j]

注释：for each循环语句不能自动处理二维数组的每一个元素。它按照行（一维数组）进行处理。
要想访问二维数组的所有元素，需要使用两个嵌套的循环：
for(double[] row:a)
{
    for(double value:row)
    {
        do something with value
    }
}

提示：要快速打印一个二维数组的数据元素列表，可以调用：
System.out.printlb(Arrays.deepToString(a));
输出格式为：
[[16,3,2,13],[5,10,11,8],[9,6,7,12],[4,15,14,1]]

#### 3.10.7 不规则数组

Java实际上没有多维数组，只有一维数组。多维数组被解释为“数组的数组”。


在前面的示例中，balances数组实际上是一个包含10个元素的数组，而每个元素又是一个由6个浮点数组成的数组。



表达式balances[i]引用第i个子数组，也就是二维表的第i行。它本身也是一个数组，balances[i][j]引用和这个数组的第j项。

由于可以单独地存取数组的某一行，所以可以让两行交换。
double[] temp = balances[i];
balances[i] = balances[i+1];
balances[i+1] = temp;

还可以方便地构造出一个“不规则“数组，即数组的每一行有不同的长度。

要创建一个不规则数组，首先需要分配一个具有所含行数的数组。
int[][] odds = new int[NMAX+1][];

接下来，分配这些行：
for(int n = 0;n <= NMAX;n++)
{
    odds[n] = new int[n+1];
}

在分配了数组之后，假定没有超出边界，就可以采用通常的方式访问其中的元素。
for(int n = 0;n < odds.length;n++)
{
    for(int k = 0;k < odds[n].length;k++)
    {
        //compute lotteryOdds
        ...
        odds[n][k] = lotteryOdds;
    }
}
