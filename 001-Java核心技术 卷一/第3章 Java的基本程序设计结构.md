## 第3章 Java的基本程序设计结构
#### 目录
##### [3.1 一个简单的Java应用程序](#anchor31)
##### [3.2 注释](#anchor32)
##### [3.3 数据类型](#anchor33)
###### &ensp;&ensp;[3.3.1 整型](#anchor331)
###### &ensp;&ensp;[3.3.2 浮点类型](#anchor332)
###### &ensp;&ensp;[3.3.3 char类型](#anchor333)
###### &ensp;&ensp;[3.3.4 Unicode和char类型](#anchor334)
###### &ensp;&ensp;[3.3.5 boolean类型](#anchor335)
##### [3.4 变量](#anchor34)
###### &ensp;&ensp;[3.4.1 变量初始化](#anchor341)
###### &ensp;&ensp;[3.4.2 常量](#anchor342)
##### [3.5 运算符](#anchor35)
###### &ensp;&ensp;[3.5.1 数学函数与常量](#anchor351)
###### &ensp;&ensp;[3.5.2 数值类型之间的转换](#anchor352)
###### &ensp;&ensp;[3.5.3 强制类型转换](#anchor353)
###### &ensp;&ensp;[3.5.4 结合赋值和运算符](#anchor354)
###### &ensp;&ensp;[3.5.5 自增与自减运算符](#anchor355)
###### &ensp;&ensp;[3.5.6 关系和boolean运算符](#anchor356)
###### &ensp;&ensp;[3.5.7 位运算符](#anchor357)
###### &ensp;&ensp;[3.5.8 括号与运算符级别](#anchor358)
###### &ensp;&ensp;[3.5.9 枚举类型](#anchor359)
##### [3.6 字符串](#anchor36)
###### &ensp;&ensp;[3.6.1 子串](#anchor361)
###### &ensp;&ensp;[3.6.2 拼接](#anchor362)
###### &ensp;&ensp;[3.6.3 不可变字符串](#anchor363)
###### &ensp;&ensp;[3.6.4 检测字符串是否相等](#anchor364)
###### &ensp;&ensp;[3.6.5 空串与Null串](#anchor365)
###### &ensp;&ensp;[3.6.6 码点与代码单元](#anchor366)
###### &ensp;&ensp;[3.6.7 String API](#anchor367)
###### &ensp;&ensp;[3.6.8 阅读联机文档](#anchor368)
###### &ensp;&ensp;[3.6.9 构建字符串](#anchor369)
##### [3.7 输入输出](#anchor37)
###### &ensp;&ensp;[3.7.1 读取输入](#anchor371)
###### &ensp;&ensp;[3.7.2 格式化输出](#anchor372)
###### &ensp;&ensp;[3.7.3 文件输入与输出](#anchor373)

### <span id="anchor31">3.1 一个简单的Java应用程序</span>

**类名标准的命名规范**：
* 类名是以大写字母开头
* 如果名字由多个单词组成，每个单词的第一个字母都应该大写，骆驼命名法。

源文件的文件名必须与公共类名相同，并使用.java作为扩展名

### <span id="anchor32">3.2 注释</span>

Java中有三种注释，// 和 /* */（不能嵌套）
第三种注释以/**开头、以*/结束，可以用来自动地生成文档，如下所示：
```java
/**
* This is the first sample 
* @version
* @author
*/
```

### <span id="anchor33">3.3 数据类型</span>

Java是一种**强类型语言**，**必须为每一个变量声明一种类型**;
Java中一共有8种基本类型：
* 4种整型：**int、short、long、byte**
* 2种浮点类型：**float、double**
* 1种用于表示Unicode编码的字符单元的字符类型**char**
* 一种用于表示真值的**boolean**类型。

#### <span id="anchor331">3.3.1 整型</span>
用于表示没有小数部分的数值，允许是负数，Java提供了4种整型
|类型|存储需求|取值范围|
-|-|-
**int**|4字节|2147483648 ~ 2147483647（正好超过20亿）
**short**|2字节|32768 ~ 32767
**long**|8字节|9223372036854775808 ~ 9223372036854775807
**byte**|1字节|128 ~ 127，2的8次方，正负分隔
* 长整型有一个后缀L或l(如4000000000L)
* 十六进制有一个前缀0x或0X
* 八进制有一个前缀0
* 从Java7开始，加上前缀0b或者0B表示二进制。
* 从Java7开始，可以为数字字面量加下划线_,如1_000_000表示一百万，易读，java编译器会去除这些下划线。

#### <span id="anchor332">3.3.2 浮点类型</span>
浮点类型用于表示有小数部分的数值，Java中有两种浮点类型：
|类型|存储需求|取值范围|后缀|
-|-|-|-
float|4字节|大约 ±3.40282347E+38F（有效位数为6~7位）|f、F
double|8字节|大约±1.79769313486231570E+308（有效位数为15位）|无、D、d

double表示的数值精度是float类型的两倍（双精度数值），绝大部分应用程序使用double类型，float的精度很难满足需求。
当需要单精度的库或者存储大量数据时，才会使用float类型。

**可以用十六进制表示浮点数值**

所有浮点数组的计算都遵循IEEE754规范，
下面是用于表示溢出和出错情况的三个特殊的浮点数值：
**正无穷大、负无穷大、NaN（不是一个数字）**

**例如**：
* 一个正整数除以0的结果是正无穷大
* 0/0或者负数的平方根的结果是NaN
* 常量**Double.POSITIVE_INFINITY、Double.NEGATIVE_INFINITY和Double.NaN**(以及相应的Float类型对应的常量)分别表示3个特殊的浮点数值，可以用**Double.IsNaN**(X)来判断X是否等于Double.NaN

**浮点数值不适合无法接受舍入误差的金融计算**，2.0-1.1的结果是0.899999999999999，不是0.9
因为浮点数值采用二进制表示，二进制无法精确地表示1/10，就像十进制无法精确地表示1/3。
float和double只能用来做科学计算或者是工程计算，在商业计算中我们要用**java.math.BigDecimal**。使用BigDecimal并且一定要用String来构造。

#### <span id="anchor333">3.3.3 char类型</span>
**char类型原本用于表示单个字符，现在有些Unicode字符可以用一个char值描述，另一些Unicode字符需要两个char值**

char类型的字面量值要用单引号括起来，'A'表示编码值65对应的字符常量；
char类型的值可以表示为十六进制值，其范围从\u0000到\Uffff。
除了转义序列\u之外，还有一些用于表示特殊字符的转义序列

![](/Java/001-Java核心技术%20卷一/Pictures/3001.png)

>备注：转义是当由于技术等原因、无法直接在代码中写出所要的字符时采用的，以多个字符的有序组合来表示原本需要的字符的手段，而转义序列（escape sequence）指在转义时使用的有序字符组合。采用转义序列的原因有很多。比如，显然不能直接把 CRLF 或 HT 这样的字符输入为字符常量，因为键盘上的回车键或制表键只完成自己该做的工作：在源代码文件中换行或跳到下一个制表位置。

#### <span id="anchor334">3.3.4 Unicode和char类型</span>
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


#### <span id="anchor335">3.3.5 boolean类型</span>
布尔类型有两个值：false、true，用来判定逻辑条件，布尔值和整型之间不能相互转换。

### <span id="anchor34">3.4 变量</span>
在Java中，每个变量都有一个类型（type）；
* 变量名必须是一个**字母开头由字母或数字构成的序列**，
* Java中字母和数字的范围更大
  * **字母**：大小写英文字母、下划线及美元符号'$'，或者某种语言中表示字母的任何Unicode字符。
  * 数字包括0-9以及在某种语言中表示数字的Unicode字符。
* 变量中所有的字符都是有意义的，并且大小写敏感，长度基本没有限制。
* 不能使用Java保留字作为变量名，可以在一行中声明多个变量（int i,j;）

>提示：可以用Character类的isJavaIdentifierStart和isJavaIdentifierPart方法来检查，哪些Unicode中的字符属于Java中的字母。

>提示：尽管'$'是一个合法的Java字符，但是不要在自己的代码中使用，它只用在Java编译器或者其他工具生成的名字中。


#### <span id="341">3.4.1 变量初始化</span>
声明一个变量之后，必须用赋值语句对变量显式初始化

#### <span id="anchor342">3.4.2 常量</span>
在Java中，使用关键字**final**指示**常量**
* 例如：**final double CM_PER_INCH = 2.54;**
* 关键字final表示这个常量**只能被赋值一次**，一旦被赋值之后，就不能更改了，习惯上，常量名使用全大写。

**类常量**：可以在一个类的多个方法中使用的常量
* 可以使用关键字**static final**设置一个类常量：
  * **public static final double CM_PER_INCH = 2.54;**

>注意：const是Java保留的关键字，但目前并没有使用

### <span id="anchor35">3.5 运算符</span>
在Java中，使用算术运算符+ - * / 。
* 当参与运算的两个操作数都是整数时，表示**整数除法**；否则表示**浮点数除法**。
* 整数的求余操作（取模），用%表示。
例如：15/2等于7、15%2等于1、15.0/2等于7.5

>注意：整数被0除将会产生一个异常，浮点数被0除将会到得无穷大或者NaN结果

#### <span id="anchor351">3.5.1 数学函数与常量</span>
在Math类中包含了各种各样的数学函数：
1. **计算平方根**，使用**sqrt方法**
   * double y = Math.sqrt(x);

2. 在Java中没有**幂运算**，需要使用Math类的**pow方法**
   * double y = Math.pow(x,a);
   * 将y的值设置为x的a次幂。pow方法有两个double类型的参数，其返回结果也是**double**类型

3. **floorMod方法**的目的是解决有关整数余数的问题
   * 考虑n%2，如果n是偶数，结果为0；如果n是奇数，结果为1；如果n为负数，结果为-1，最早制定的规则有问题，因为欧几里得规则规定，余数总是要大于等于0
   * 例如：计算调整一个时钟的位置
![](/Java/001-Java核心技术%20卷一/Pictures/3501.png)
floorMod简化了这个问题：floormod(position + adjustment , 12)总会得到0~11之间的数（负除数结果依然是负数）

4. 三角函数

![](/Java/001-Java核心技术%20卷一/Pictures/3502.png)

5. Java还提供了两个用于表示**π和e常量**的近似值：
**Math.PI**
**Math.E**

> 注意：源文件顶部加上，import static java.lang.*;  即可在使用方法时，省略Math类名

#### <span id="anchor352">3.5.2 数值类型之间的转换</span>

数值类型之间的合法转换如下图所示：

![](/Java/001-Java核心技术%20卷一/Pictures/3503.png)

实心箭头：表示无信息丢失的转换；虚箭头：表示可能有精度损失的转换。
例如int n = 123456789;
float f = n; //f=1.23456792E8

当使用上面两个数值进行二元操作时，n是整数，f是浮点数，先要将两个操作数转换为同一类型，然后再计算

* 如果两个操作数有一个是double类型，另一个操作数就会转换成double类型
* 否则，如果其中有一个是float类型，另一个操作数就会转成成float类型
* 否则，如果其中有一个是long类型，另一个操作数就会转成成long类型
* 否则，如果其中有一个是int类型，另一个操作数就会转成成int类型

#### <span id="anchor353">3.5.3 强制类型转换</span>

int类型会自动转换为double类型，但是，有时候，需要将double转换为int，此时我们使用强类型转换（cast），但是可能会丢失一些信息。

* 例如：double x = 9.997;int n = (int)x; //此时n的值是9
>强制类型转换通过截断小数部分将浮点值转换为整型。

如果想对浮点数进行舍入运算，以便得到最接近的整数，需要使用**Math.round**方法
* 例如：double x = 9.997;int n = (int)Math.round(x); //此时n的值是10

在调用round方法时，仍然需要使用强制类型转换(int)，因为round方法返回的结果是long类型，由于存在信息丢失的可能性，只有使用显示的强制类型转换才能将long类型转换为int类型。

#### <span id="anchor354">3.5.4 结合赋值和运算符</span>
可以在赋值中使用二元运算符，x += 4
注意：如果运算符得到一个值，其类型与左侧操作数的类型不同，就会发生强制类型转换
例如：如果x是int类型，x += 3.5; 是合法的，x=(int)(x+3.5);

#### <span id="anchor355">3.5.5 自增与自减运算符</span>
++n，先加一，在表达式中
n++，后加一，在表达式中

#### <span id="anchor356">3.5.6 关系和boolean运算符</span>
Java包含丰富的**关系运算符**：==、!=、<、>、<=、>=
**逻辑运算符**：&&（与）、||（或）、!（非）
**三元操作符**：?:  若条件为true，就为第一个表达式的值，负责计算称为第二个表达式的值。
>condition ? expression1 :expression2

#### <span id="anchor357">3.5.7 位运算符</span>
位运算符操作数只能是整型和字符型数据。
处理整数类型时，可以直接对组成整型数值的各个位完成操作，这意味着可以使用掩码技术得到整数中的各个位，
位移运算符包括：
&（按位与）、|（按位或）、^（按位异或）、~（取反）
这些运算符按位模式处理。
例如，如果n是一个整数变量，而且用二进制表示的n从右边数第四位为1，则
int fourthBitFromRight = (n & 0b1000) / 0b1000;
会返回1，否则会返回0。利用&并结合使用适当的2的幂，可以把其他位掩掉，而只保留其中一位。


#### <span id="anchor358">3.5.8 括号与运算符级别</span>
如果不使用圆括号，就按照给出的运算符优先级次序进行计算。
同一个级别的运算符按照**从左到右**的次序进行计算（除了**右结合运算符**）。
例如，+=是右结合运算符，所以 a += b += c 等价于 a += (b += c)

#### <span id="anchor359">3.5.9 枚举类型</span>
有时候，变量的取值只在一个有限的集合内，我们可以自定义枚举类型，枚举类型包含有限个命名的值（0或m个）
例如：enum Size{SMALL, MEDIUM, LARGE, EXTRA_LARGE};
现在，可以声明这种类型的变量：
Size s = Size.MEDIUM;
Size类型的变量只能存储这个类型声明中给定的某个枚举值，或者NULL值，NULL值表示这个变量没有设置任何值。
详细介绍在第5章。

#### <span id="anchor36">3.6 字符串</span>
从概念上将，Java字符串就是Unicode字符序列
>例如；串"Java\u2122"由5个Unicode字符J、a、v、a和™ 组成。

Java没有内置的字符串类型，而是在标准Java类库中提供了一个**预定义类**，**叫String**。
每个用双引号括起来的字符串都是**String类的一个实例**。

#### <span id="anchor361">3.6.1 子串</span>
String类的substring方法可以从一个较大的字符串提取出一个子串
>substring(m, n)  m表示起始位置（包含），n表示终止位置（不包括）

例如：
```java
String greeting = "Hello";
String s = greeting.substring(0,3); //从0开始，0,1,2，
```
#### <span id="anchor362">3.6.2 拼接</span>
Java语言允许使用+号拼接两个字符串
当将一个字符串与一个非字符串的拼接时，后者被转换成字符串（第五章中可以看到，任何一个Java都可以转换成字符串）：
例如：
```java
int age = 13;
String rating = "PG"+ age；//rating为"PG13"
```
如果需要把多个字符串放在一起，用一个定界符分隔，可以使用静态join方法：
```java
String all  = String.Join("/", "S", "M", "L", "XL"); //all结果为 "S/M/L/XL"
```
#### <span id="anchor363">3.6.3 不可变字符串</span>
String类没有提供用于修改字符串的方法，在Java中，如果想修改字符串变量的内容，可以做如下操作：
首先提取需要的字符，然后再拼接上替换的字符串：
```java
greeting = greeting.substring(0,3) + "p!";
```
由于**不能修改Java字符串中的字符**，所以在Java文档中将String类对象称为**不可变字符串**。
字符串"Hello"永远包含字符H、e、l、l和o的代码单元序列，而不能修改其中任何一个字符。我们可以修改字符串变量greeting，让它引用另外一个字符串。

**这样做似乎降低效率，但是不可变字符串有一个优点**：
* **编译器可以让字符串共享**

>各种字符串存放在公共的存储池中，字符串变量指向存储池中相应的位置，如果复制一个字符串变量，原始字符串与复制的字符串共享相同的字符。

>Java的设计者认为，共享带来的效率远胜于提取、拼接字符串所带来的低效率。

#### <span id="anchor364">3.6.4 检测字符串是否相等</span>
**equls方法**
>检测两个字符串是否相等

```java
s.equals(t)
"Hello".equals(greeting) 
```
>如果字符串s与字符串t相等，则返回true，否则返回false。
>s与t可以是字符串变量，也可以是字符串字面量：


**equalsIgnoreCase方法**
>检测两个字符串是否相等，而不区分大小写
```java
"Hello".equalsIgnoreCase("hello")
```
* 不要使用==运算符检测两个字符串是否相等！
  * ==运算符只能确定两个字符串是否放在同一位置

如果虚拟机始终将相同的字符串共享，就可以使用==运算符检测是否相等，但实际上，只有字符串常量是共享的，而+或substring等操作产生的结果并不是共享的。

#### <span id="anchor365">3.6.5 空串与Null串</span>
空串""是长度为0的字符串，检查一个字符串是否为空：
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

#### <span id="anchor366">3.6.6 码点与代码单元</span>
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

#### <span id="anchor367">3.6.7 String API</span>
Java的String类包含了50多种方法，绝大多数都很有用，下列的API注释汇总了一部分最常用的方法

java.lang.string 1.0，如果某个方法是在这个版本之后添加的， 就会给出一个单独的版本号。
```java
char charAt(int index)
	返回给定的代码单元。出兑对底层的代码单元感兴趣，否则不需要调用这个方法
int codePointAt(int index) 5.0
	返回从给定位置开始的码点
int offsetByCodePoints(int startlndex, int cpCount) 5.0
	返回从startlndex 代码点开始， 位移cpCount 后的码点索引*
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
int indexOf (String str,int fromlndex)
int indexOf (int cp)
int indexOf (int cp, int fromlndex)
	返回与字符串str或代码点cp 匹配的第一个子串的开始位置。这个位置从索引0或fromlndex开始计算。如果在原始始串中不存在str，返回-1。
int lastIndexOf (String str)
int lastIndexOf (String str,int fromlndex)
int lastindexOf (int cp)
int lastindexOf (int cp,int fromlndex)
	返回与字符串str或代码点cp匹配的最后一个子串的开始位置。这个位置从原始串尾端或fromlndex 开始计算。
int length()
	返回字符串的长度。
int codePointCount (int startlndex,int endlndex) 5.0
	返回startlndex和endludex-l 之间的代码点数量。没有配成对的代用字符将计入代码点。
String replace(CharSequence oldString,CharSequence newString)
	返回一个新字符串。这个字符串用newString 代替原始字符串中所有的oldString。可以用String或StringBuilder对象作为CharSequence参数。
String substring(int beginlndex)
String substring(int beginlndex,int endlndex)
	返回一个新字符串。这个字符串包含原始字符串中从beginlndex到串尾或endlndex-1的所有代码单元。
String toLowerCase()
String toUpperCase()
	返回一个新字符串。这个字符串将原始字符串中的大写字母改为小写，或者将原始字符串中的所有小写字母改成了大写字母。
String trim()
	返回一个新字符串。这个字符串将删除了原始字符串头部和尾部的空格。
String join(CharSequence delimiter,CharSequence . .. elements) 8
	返回一个新字符串，用给定的定界符连接所有元素。

注释：在API注释中，有一些CharSequence类型的参数。这是一种接口类型，所有字符串都属于这个接口。
```

#### <span id="anchor368">3.6.8 阅读联机文档</span>

标准库中有几千个类，方法数量更多，要记住所有的方法和类不太可能，因此要学会使用在线API文档
官方API网址：https://www.oracle.com/technetwork/java/api-141528.html

#### <span id="anchor369">3.6.9 构建字符串</span>

有时候，需要由较短的字符串构建字符串，例如，按键或来自文件中的单词。
* 采用字符串连接的方式效率较低，每次连接字符串，都会构建一个新的String对象，**耗时且浪费空间**。
使用**StringBuilder类**可以避免这个问题，用法如下：
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

### <span id="anchor37">3.7 输入输出</span>
#### <span id="anchor371">3.7.1 读取输入</span>
调用**System.out.println**，即可打印输出到“标准输出流”（控制台窗口）
读取“标准输入流”System.in麻烦一些，首先需要构造一个Scanner对象，并与“标准输入流”System.in关联。
```java
Scanner in = new Scanner(System.in);
```
之后可以使用Scanner类的各种方法实现输入操作。

Scanner类定义在java.util包中，当使用的类不是定义在基本java.lang包中时，一定要使用import指示字将相应的包加载进来。
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
为了安全起见， 返回的密码存放在一维字符数组中， 而不是字符串中。在对密码进行处理之后， 应该马上用一个填充值覆盖数组元素（数组处理将在3.10 节介绍）。
采用Console 对象处理输入不如采用Scanner 方便。每次只能读取一行输入， 而没有能够读取一个单词或一个数值的方法。
```java
API-java.util.Scanner 5.0

Scanner (InputStream in)
	用给定的输人流创建一个Scanner 对象。
String nextLine()
	读取输入的下一行内容。
String next()
	读取输入的下一个单词（以空格作为分隔符)。
int nextlnt()
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
	显示字符串prompt 并且读取用户输入，直到输入行结束。args 参数可以用来提供输人格式。有关这部分内容将在下一节中介绍。
```

#### <span id="anchor372">3.7.2 格式化输出</span>

可以使用System.out.print(x)将数值x输出到控制台。这条命令将以x对应的数据类型所允许的最大非0数字位数打印输出x.

Java SE 5.0 沿用了C语言函数库中的printf方法，例如：
System.out.printf("%8.2f", x);  //可以用8个字符的宽度和小数点后两个字符的精度打印x。

解释：
1、每一个以%字符开始的格式说明符都用相应的参数替换。
2、格式说明符尾部的转换符将指示被格式化的数值类型：f表示浮点数，s表示字符串、d表示十进制整数。表3-5列出了所有转换符。
3、还可以给出控制格式化输出的各种标志，表3-6给出了所有的标志，可以使用多个分隔符拼在一起。

![](/Java/001-Java核心技术%20卷一/Pictures/3701.png)

注释：可以使用s转换符格式化任意的对象。
对于实现了Formattable几口的对象都将调用formatTo方法，否则将调用toString方法，它可以将对象转换为字符串
可以使用静态的String.format 方法创建一个格式化的字符串， 而不打印输出：
```java
String message = String.format ("Hello, %s. Next year , you'll be %d", name , age);
```

![](/Java/001-Java核心技术%20卷一/Pictures/3702.png)


基于完整性的考虑，下面简略地介绍printf方法中日期与时间的格式化选项。
在新代码中，应该使用卷II中第6章介绍的java.time包的方法。旧的代码中，会有Date类和相关的格式化选项。

格式包括两个字母，以t开始，以表3-7中的任意字母结束。例如：
```java
System.out.printf("%tc", new Date());//打印格式： Mon Feb 09 18:05:19 PST 2015
```
![](/Java/001-Java核心技术%20卷一/Pictures/3703.png)

![](/Java/001-Java核心技术%20卷一/Pictures/3704.png)


从表3-7 可以看到， 某些格式只给出了指定日期的部分信息。例如，只有日期或月份。如果需要多次对日期操作才能实现对每
一部分进行格式化，这种方式太繁琐。

为此，可以采用一个格式化的字符串指出要被格式化的参数索引。索引必须紧跟在 % 后面， 并以 $ 终止。
例如，System.out.printf("1$s %2$tB %2$te, %2$tY","Due date:", new Date())；
打印
Due date：February 9,2005

还可以选择使用< 标志。它指示前面格式说明中的参数将被再次使用。也就是说，下列语句将产生与前面语句同样的输出结果：
System.out.printf ("%s %tB %<te, %<tY","Due date:" , new Date());

注意：参数索引从1开始，而不是从0开始。%1$ 对第一个参数格式化。
语法图如下：

![](/Java/001-Java核心技术%20卷一/Pictures/3705.png)

#### <span id="anchor373">3.7.3 文件输入与输出</span>

文件读取
如果想要对文件进行读取，就需要一个用File对象构造一个Scanner对象
Scanner in = new Scanner(Paths.get(myfile.txt),"UTF-8");
如果文件中包含反斜杠，就需要在反斜杠前再加一个额外的反斜杠

文件写入
写入文件需要构造一个PrintWriter对象。在构造器中，只需要提供文件名：
PrintWriter out = new PrintWriter("myfile.txt","UTF-8");
如果文件不存在，创建该文件。可以像输出到System.out一样使用print、printf及println命令
覆盖式添加，而非追加。
PrintWriter out = new PrintWriter("myfile.txt","UTF-8");
out.print("nihao");
out.close();

注释：
当指定一个相对文件名时， 例如， “myfile.txt”，“mydirectory/myfile.txt” 或“ ../myfile.txt”，文件位于Java虚拟机启
动路径的相对位置。
如果在命令行下启动程序，启动路径就是命令解释器的当前路径。
如果使用IDE，启动路径将由IDE控制，可以使用如下方式找到路径的位置：
String dir = System.getProperty("myfile.txt");

如果用一个不存在的文件构造一个Scanner, 或者用一个不能被创建的文件名构造一个PrintWriter,那么就会发生异常。
Java 编译器认为这些异常比“ 被零除” 异常更严重。现在，应该告知编译器： 已经知道有可能出现“ 输入/输出” 异常。
这需要在main 方法中用throws 子句标记， 如下所示：
public static void main(String[] args) throws IOException
{
    Scanner in = new Scanner(Paths.get("myfile.txt"), "UTF-8");
}

当采用命令行方式启动一个程序时， 可以利用Shell 的重定向语法将任意文件关联到System.in 和System.out:
java MyProg < myfile.txt > output.txt
这样， 就不必担心处理IOException 异常了。

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