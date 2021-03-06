---
layout: post
title: "java 学习笔记（2）——变量与运算符"
date: 2020-07-11 19:56:41 +0800
categories: notes
tags: java
img: https://s1.ax1x.com/2020/07/12/U1oQN4.png
---
关键字和保留字；标识符；变 量；运算符；

## 关键字和保留字

### 关键字(keyword)的定义和特点

定义：被Java语言赋予了特殊含义，用做专门用途的字符串（单词）

特点：关键字中所有字母都为小写

[官方地址](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/_keywords.html)： https://docs.oracle.com/javase/tutorial/java/nutsandbolts/_keywords.html

![](https://s1.ax1x.com/2020/07/12/U1xgAI.md.png)

![](https://s1.ax1x.com/2020/07/12/U1xf9f.md.png)

Java保留字：现有Java版本尚未使用，但以后版本可能会作为关键字使
用。自己命名标识符时要避免使用这些保留字

goto 、const

## 标识符(Identifier)

**标识符**：Java 对各种变量、方法和类等要素命名时使用的字符序列称为标识符

技巧：凡是自己可以起名字的地方都叫标识符。


### 定义合法标识符规则

* 由26个英文字母大小写，0-9 ，_或 $ 组成
* 数字不可以开头。
* 不可以使用关键字和保留字，但能包含关键字和保留字
* Java中严格区分大小写，长度无限制
* 标识符不能包含空格。

### Java中的名称命名规范

Java中的名称命名规范:

1. 包名：多单词组成时所有字母都小写：xxxyyy
2. 类名、接口名：多单词组成时，所有单词的首字母大写：XxxYyyZzz
3. 变量名、方法名：多单词组成时，第一个单词首字母小写，第二个单词开始每个单词首字母大写：xxxYyy
4. 常量名：所有字母都大写。多单词时每个单词用下划线连接：XXX_YYY_ZZZ

注意1：在起名字时，为了提高阅读性，要尽量有意义，“见名知意”。

注意2：java采用unicode字符集，因此标识符也可以使用汉字声明，但是不建议使用

## 变量

#### 变量的概念

* 内存中的一个存储区域
* 该区域的数据可以在同一类型范围内不断变化
* 变量是程序中最基本的存储单元。包含变量类型、变量名和存储的值

#### 作用

用于在内存中保存数据

#### 使用变量注意

1. Java中每个变量必须先声明，后使用
2. 使用变量名来访问这块区域的数据
3. 变量的作用域：其定义所在的一对{ }内
4. 变量只有在其作用域内才有效
5. 同一个作用域内，不能定义重名的变量

#### 声明变量

语法：<数据类型> <变量名称>

例如：int var;

#### 变量的赋值

语法：<变量名称> = <值>

例如：var = 10;

#### 声明和赋值变量

语法： <数据类型> <变量名> = <初始化值>

例如：int var = 10;

#### 变量的分类

对于每一种数据都定义了明确的具体数据类型（强类型语言），在内存中分配了不同大小的内存空间。

![](https://s1.ax1x.com/2020/07/12/U1x2Nt.md.png)

对于每一种数据都定义了明确的具体数据类型（强类型语言），在内存中分配了不同大小的内存空间。

在方法体外，类体内声明的变量称为成员变量。

在方法体内部声明的变量称为局部变量。

![](https://s1.ax1x.com/2020/07/12/U1xR4P.png)

二者在初始化值方面的异同:

同：都有生命周期 异：局部变量除形参外，需显式初始化。

### 基本数据类型

#### 整数类型：byte、short、int、long

Java各整数类型有固定的表数范围和字段长度，不受具体OS的影响，以保
证java程序的可移植性

java的整型常量默认为 int 型，声明long型常量须后加‘l’或‘L’

java程序中变量通常声明为int型，除非不足以表示较大的数，才使用long

![](https://s1.ax1x.com/2020/07/12/U1x6HA.png)

bit: 计算机中的最小存储单位。byte:计算机中基本存储单元。

#### 浮点类型：float、double

与整数类型类似，Java 浮点类型也有固定的表数范围和字段长度，不受具体操作系统的影响。

浮点型常量有两种表示形式：

* 十进制数形式：如：5.12 512.0f .512 (必须有小数点）
* 科学计数法形式:如：5.12e2 512E2 100E-2

float:单精度，尾数可以精确到7位有效数字。很多情况下，精度很难满足需求。

double:双精度，精度是float的两倍。通常采用此类型

Java 的浮点型常量默认为double型，声明float型常量，须加‘f’或‘F’

![](https://s1.ax1x.com/2020/07/12/U1x4gS.png)

#### 字符类型：char

char 型数据用来表示通常意义上“字符”(2字节)

Java中的所有字符都使用Unicode编码，故一个字符可以存储一个字
母，一个汉字，或其他书面语的一个字符。

字符型变量的三种表现形式：

1. 字符常量是用单引号(‘ ’)括起来的单个字符。例如：char c1 = 'a'; char c2 '中'; char c3 = '9';
2. Java中还允许使用转义字符‘\’来将其后的字符转变为特殊字符型常量。
	* 例如：char c3 = ‘\n’; // '\n'表示换行符
3. 直接使用 Unicode 值来表示字符型常量：‘\uXXXX’。其中，XXXX代表一个十六进制整数。如：\u000a 表示 \n。

char类型是可以进行运算的。因为它都对应有Unicode码。

![](https://s1.ax1x.com/2020/07/12/U1xh38.png)

了解：**ASCII 码**

在计算机内部，所有数据都使用二进制表示。每一个二进制位（bit）有 0 和 1 两种状态，因此 8 个二进制位就可以组合出 256 种状态，这被称为一个字（byte）。一个字节一共可以用来表示 256 种不同的状态，每一个状态对应一个符号，就是 
256 个符号，从0000000 到 11111111。

ASCII码：上个世纪60年代，美国制定了一套字符编码，对英语字符与二进制位之间的关系，做了统一规定。这被称为ASCII码。ASCII码一共规定了128个字符的编码，比如空格“SPACE”是32（二进制00100000），大写的字母A是65（二进制01000001）。这128个符号（包括32个不能打印出来的控制符号），只占用了一个字节的后面7位，最前面的1位统一规定为0

缺点：

* 不能表示所有字符。 
* 相同的编码表示的字符不一样：比如，130在法语编码中代表了é，在希伯来语编码中却代表(ג) 了字母Gim


了解： **Unicode 编码**

乱码：世界上存在着多种编码方式，同一个二进制数字可以被解释成不同的符号。因
此，要想打开一个文本文件，就必须知道它的编码方式，否则用错误的编码方式解读，
就会出现乱码。

Unicode：一种编码，将世界上所有的符号都纳入其中。每一个符号都给予一个独一
无二的编码，使用 Unicode 没有乱码的问题。

Unicode 的缺点：Unicode 只规定了符号的二进制代码，却没有规定这个二进制代码
应该如何存储：无法区别 Unicode 和 ASCII：计算机无法区分三个字节表示一个符号
还是分别表示三个符号。另外，我们知道，英文字母只用一个字节表示就够了，如果
unicode统一规定，每个符号用三个或四个字节表示，那么每个英文字母前都必然有
二到三个字节是0，这对于存储空间来说是极大的浪费

了解： **UTF-8**

UTF-8 是在互联网上使用最广的一种 Unicode 的实现方式

UTF-8 是一种变长的编码方式。它可以使用 1-6 个字节表示一个符号，根据
不同的符号而变化字节长度

UTF-8的编码规则：

* 对于单字节的UTF-8编码，该字节的最高位为0，其余7位用来对字符进行编码（等同于ASCII码）。
* 对于多字节的UTF-8编码，如果编码包含 n 个字节，那么第一个字节的前 n 位为1，第一个字节的第 n+1 位为0，该字节的剩余各位用来对字符进行编码。在第一个字节之后的所有的字节，都是最高两位为"10"，其余6位用来对字符进行编码。

#### 布尔类型：boolean

boolean 类型用来判断逻辑条件，一般用于程序流程控制：

* if条件控制语句；
* while循环控制语句；
* do-while循环控制语句；
* for循环控制语句

boolean类型数据只允许取值true和false，无null。 

* 不可以使用0或非 0 的整数替代false和true，这点和C语言不同。
* Java虚拟机中没有任何供boolean值专用的字节码指令，Java语言表达所操作的
boolean值，在编译之后都使用java虚拟机中的int数据类型来代替：true用1表示，false用0表示

### 基本数据类型与变量间转换

自动类型转换：容量小的类型自动转换为容量大的数据类型。数据类型按容
量大小排序为：

![](https://s1.ax1x.com/2020/07/12/U1x5jg.png)

有多种类型的数据混合运算时，系统首先自动将所有数据转换成容量最大的
那种数据类型，然后再进行计算。

* byte,short,char之间不会相互转换，他们三者在计算时首先转换为int类型。
* boolean类型不能与其它数据类型运算。
* 当把任何基本数据类型的值和字符串(String)进行连接运算时(+)，基本数据类
型的值将自动转化为字符串(String)类型。

### 基本数据类型与String间的转换

字符串类型：String

* String不是基本数据类型，属于引用数据类型
* 使用方式与基本数据类型一致。例如：String str = “abcd”;
* 一个字符串可以串接另一个字符串，也可以直接串接其他类型的数据。例如：
    
    str = str + “xyz” ; 

    int n = 100;

    str = str + n;


练习：

    String str1 = 4; //判断对错：no
    String str2 = 3.5f + “”; //判断str2对错：yes
    System.out.println(str2); //输出：”3.5”
    System.out .println(3+4+“Hello!”); //输出：7Hello!
    System.out.println(“Hello!”+3+4); //输出：Hello!34
    System.out.println(‘a’+1+“Hello!”); //输出：98Hello!
    System.out.println(“Hello”+‘a’+1); //输出：Helloa1


### 强制类型转换

自动类型转换的逆过程，将容量大的数据类型转换为容量小的数据类型。使用时要加上强制转换符：()，但可能造成精度降低或溢出,格外要注意

通常，字符串不能直接转换为基本类型，但通过基本类型对应的包装类则可以实现把字符串转换成基本类型

String a = “43”; int i = Integer.parseInt(a);

boolean类型不可以转换为其它的数据类型

练习：

    short s = 5;
    s = s-2; //判断：no
    2） byte b = 3;
    b = b + 4; //判断：no
    b = (byte)(b+4); //判断：yes
    3）char c = ‘a’;
    int i = 5;
    float d = .314F;
    double result = c+i+d; //判断：yes
    4） byte b = 5;
    short s = 3;
    short t = s + b; //判断：no


### 进制间的转换

所有数字在计算机底层都以二进制形式存在。

对于整数，有四种表示方式：

* 二进制(binary)：0,1 ，满2进1.以0b或0B开头。
* 十进制(decimal)：0-9 ，满10进1。 八进制(octal)：0-7 ，满8进1. 以数字0开头表示。
* 十六进制(hex)：0-9及A-F，满16进1. 以0x或0X开头表示。此处的A-F不区分大小写。如：0x21AF +1= 0X21B0

![](https://s1.ax1x.com/2020/07/12/U1xouQ.png)

![](https://s1.ax1x.com/2020/07/12/U1xTBj.png)

#### 二进制

Java整数常量默认是int类型，当用二进制定义整数时，其第32位是符号位；
当是long类型时，二进制默认占64位，第64位是符号位

二进制的整数有如下三种形式：

* 原码：直接将一个数值换成二进制数。最高位是符号位
* 负数的反码：是对原码按位取反，只是最高位（符号位）确定为1。
* 负数的补码：其反码加1

为什么要使用原码、反码、补码表示形式呢？

计算机辨别“符号位”显然会让计算机的基础电路设计变得十分复杂! 于是人们想出了将符号位也参与运算的方法. 我们知道, 根据运算法则减去一个正数等于加上一个负数, 即: 1-1 = 1 + (-1) = 0 , 所以机器可以只有加法而没有减法, 这样计算机运算的设计就更简单了

![](https://s1.ax1x.com/2020/07/12/U1x7Hs.md.png)

![](https://s1.ax1x.com/2020/07/12/U1xXCV.md.png)

![](https://s1.ax1x.com/2020/07/12/U1xbEn.md.png)

## 运算符

运算符是一种特殊的符号，用以表示数据的运算、赋值和比较等。

* 算术运算符
* 赋值运算符
* 比较运算符（关系运算符）
* 逻辑运算符
* 位运算符
* 三元运算符

### 算术运算符

![](https://s1.ax1x.com/2020/07/12/U1xj3T.md.png)

算术运算符的注意问题:

* 如果对负数取模，可以把模数负号忽略不记，如：5%-2=1。 但被模数是负数则不可忽略。此外，取模运算的结果不一定总是整数
* 对于除号“/”，它的整数除和小数除是有区别的：整数之间做除法时，只保留整数部分而舍弃小数部分。 例如：int x=3510;x=x/1000*1000; x的结果是3000
* “+”除字符串相加功能外，还能把非字符串转换成字符串.例如:System.out.println(“5+5=”+5+5); //打印结果是5+5=55

### 赋值运算符

符号：= 

当“=”两侧数据类型不一致时，可以使用自动类型转换或使用强制
类型转换原则进行处理。 

支持连续赋值。

扩展赋值运算符： +=, -=, *=, /=, %=


    short s = 3; 
    s = s+2; ①
    s += 2; ② ①和②有什么区别？

short类型与int类型相加，short类型会自动提升成int，所以 s+2 的值为int类型，把int类型的值赋给short类型的 s 会损失精度，因此直接写 s=s+2 会报错，但是写成 s+=2 的话会默认进行自动的类型转换，把 s+2 的结果强转成了short（即使损失精度），所以不会报错

    int i = 1;
    i *= 0.1;
    System.out.println(i);//0
    i++;
    System.out.println(i);//1

思考3：
    
    int m = 2;
    int n = 3;
    n *= m++; 
    System.out.println("m=" + m);//3
    System.out.println("n=" + n)//6

思考4：

    int n = 10;
    n += (n++) + (++n);//10+10+12=32
    System.out.println(n);

### 比较运算符

![](https://s1.ax1x.com/2020/07/12/U1xqNq.md.png)

比较运算符的结果都是boolean型，也就是要么是true，要么是false

比较运算符“==”不能误写成“=” 

### 逻辑运算符

&—逻辑与 | —逻辑或 ！—逻辑非

&& —短路与 || —短路或 ^ —逻辑异或

![](https://s1.ax1x.com/2020/07/12/U1xL40.md.png)



逻辑运算符用于连接布尔型表达式，在Java中不可以写成3<x<6，应该写
成x>3 & x<6 。

“&”和“&&”的区别：

* 单&时，左边无论真假，右边都进行运算；
* 双&时，如果左边为真，右边参与运算，如果左边为假，那么右边不参与运算。

“|”和“||”的区别同理，||表示：当左边为真，右边不参与运算。

异或( ^ )与或( | )的不同之处是：当左右都为true时，结果为false。

理解：异或，追求的是“异”!

![](https://s1.ax1x.com/2020/07/12/U1xxvF.md.png)


### 位运算符

![](https://s1.ax1x.com/2020/07/12/U1xvgU.md.png)



位运算是直接对整数的二进制进行的运算

![](https://s1.ax1x.com/2020/07/12/U1zPER.png)

![](https://s1.ax1x.com/2020/07/12/U1zSu4.png)

![](https://s1.ax1x.com/2020/07/12/U1z9b9.png)

![](https://s1.ax1x.com/2020/07/12/U1zpDJ.md.png)


### 三元运算符

![](https://s1.ax1x.com/2020/07/12/U1ziU1.png)

![](https://s1.ax1x.com/2020/07/12/U1zF4x.md.png)
