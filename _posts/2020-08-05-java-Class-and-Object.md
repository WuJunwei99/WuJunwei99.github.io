---
layout: post
title: "Java类与成员类"
date: 2020-08-05 10:45:21 +0800
categories: notes
tags: java
img: https://s1.ax1x.com/2020/07/12/U1oQN4.png
---
面向过程与面向对象；类与对象；类的成员之属性和方法

## 面向过程与面向对象

### 面向过程(POP) 与 面向对象(OOP)

二者都是一种思想，面向对象是相对于面向过程而言的。面向过程，强调的是功能行为，以函数为最小单位，考虑怎么做。面向对象，将功能封装进对象，强调具备了功能的对象，以类/对象为最小单位，考虑谁来做。

面向对象更加强调运用人类在日常的思维逻辑中采用的思想方法与原则，如抽象、分类、继承、聚合、多态等。

### 三大特征

封装、继承、多态

### 面向对象的思想概述

程序员从面向过程的执行者转化成了面向对象的指挥者

面向对象分析方法分析问题的思路和步骤：

1. 根据问题需要，选择问题所针对的现实世界中的实体。 
2. 从实体中寻找解决问题相关的属性和功能，这些属性和功能就形成了概念世界中的类。
3. 把抽象的实体用计算机语言进行描述，形成计算机世界中类的定义。即借助某种程序语言，把类构造成计算机能够识别和处理的数据结构。
4. 将类实例化成计算机世界中的对象。对象是计算机世界中解决问题的最终工具

## 类与对象

### 思想概述

**类**(Class)和**对象**(Object)是面向对象的核心概念。

* 类是对一类事物的描述，是**抽象**的、概念上的定义
* 对象是**实际存在**的该类事物的每个个体，因而也称为**实例**(instance)。

可以理解为：类 = 抽象概念的人；对象 = 实实在在的某个人

面向对象程序设计的重点是**类的设计**

类的设计，其实就是**类的成员的设计**

### Java类及类的成员

常见的类的成员有：

* 属 性：对应类中的成员变量
* 行 为：对应类中的成员方法

Field = 属性 = 成员变量，Method = (成员)方法 = 函数

### 创建Java自定义类

1. 定义类（考虑修饰符、类名）
2. 编写类的属性（考虑修饰符、属性类型、属性名、初始化值）
3. 编写类的方法（考虑修饰符、返回值类型、方法名、形参等）

## 对象的创建和使用

创建对象语法： 类名 对象名 = new 类名();

使用“对象名.对象成员”的方式访问对象成员（包括属性和方法）

![](https://s1.ax1x.com/2020/08/08/aIXxqx.md.png)

![](https://s1.ax1x.com/2020/08/08/aIXvs1.md.png)

### 类的访问机制

在一个类中的访问机制：类中的方法可以直接访问类中的成员变量。 （例外static方法访问非static，编译不通过。）

在不同类中的访问机制：先创建要访问类的对象，再用对象访问类中定义的成员

### 对象的产生

![](https://s1.ax1x.com/2020/08/08/aIXjMR.md.png)

### 内存解析

![](https://s1.ax1x.com/2020/08/08/aIjpdK.md.png)

![](https://s1.ax1x.com/2020/08/08/aIjSZ6.md.png)

## 类的成员之属性

![](https://s1.ax1x.com/2020/08/08/aIj9IO.png)

![](https://s1.ax1x.com/2020/08/08/aIjiJe.png)

![](https://s1.ax1x.com/2020/08/08/aIjPiD.md.png)

### 成员变量vs局部变量的内存位置

![](https://s1.ax1x.com/2020/08/08/aIjFRH.md.png)

### 对象属性的默认初始化赋值

当一个对象被创建时，会对其中各种类型的成员变量自动进行初始化赋值。除了基本数据类型之外的变量类型都是引用类型，如上面的Person及前面讲过的数组。

![](https://s1.ax1x.com/2020/08/08/aIjkzd.png)

## 类的成员之方法

### 什么是方法(method、函数)

* 方法是类或对象行为特征的抽象，用来完成某个功能操作。在某些语言中也称为函数或过程。
* 将功能封装为方法的目的是，可以实现代码重用，简化代码
* Java里的方法不能独立存在，所有的方法必须定义在类里。

![](https://s1.ax1x.com/2020/08/08/aIjVsI.md.png)

![](https://s1.ax1x.com/2020/08/08/aIjEQA.md.png)

### 方法的调用

方法通过方法名被调用，且只有被调用才会执行。

注 意：

* 方法被调用一次，就会执行一次
* 没有具体返回值的情况，返回值类型用关键字void表示，那么方法体中可以不必使用return语句。如果使用，仅用来结束方法。
* 定义方法时，方法的结果应该返回给调用者，交由调用者处理。 
* 方法中只能调用方法或属性，不可以在方法内部定义方法

### 方法的重载

#### 概念

在同一个类中，允许存在一个以上的同名方法，只要它们的参数个数或者参数类型不同即可。

#### 特点

与返回值类型无关，只看参数列表，且参数列表必须不同。(参数个数或参数类型)。调用时，根据方法参数列表的不同来区别。

#### 示例

    //返回两个整数的和
    int add(int x,int y){return x+y;}
    //返回三个整数的和
    int add(int x,int y,int z){return x+y+z;}
    //返回两个小数的和
    double add(double x,double y){return x+y;}

![](https://s1.ax1x.com/2020/08/08/aIxK2Q.png)


### 可变个数的形参

JavaSE 5.0 中提供了Varargs(variable number of arguments)机制，允许直接定义能和多个实参相匹配的形参。从而，可以用一种更简单的方式，来传递个数可变的实参。

    //JDK 5.0以前：采用数组形参来定义方法，传入多个同一类型变量
    public static void test(int a ,String[] books);
    //JDK5.0：采用可变个数形参来定义方法，传入多个同一类型变量
    public static void test(int a ,String…books)

说明：

1. 声明格式：方法名(参数的类型名 ...参数名)
2. 可变参数：方法参数部分指定类型的参数个数是可变多个：0个，1个或多个
3. 可变个数形参的方法与同名的方法之间，彼此构成重载
4. 可变参数方法的使用与方法参数部分使用数组是一致的
5. 方法的参数部分有可变形参，需要放在形参声明的最后
6. 在一个方法的形参位置，最多只能声明一个可变个数

![]()

### 方法参数的值传递机制


方法，必须由其所在类或对象调用才有意义。若方法含有参数：

* 形参：方法声明时的参数
* 实参：方法调用时实际传给形参的参数值

Java里方法的参数传递方式只有一种：值传递。 即将实际参数值的副本（复制品）传入方法内，而参数本身不受影响。

#### 实参值的传入

* 形参是基本数据类型：将实参基本数据类型变量的“数据值”传递给形参
* 形参是引用数据类型：将实参引用数据类型变量的“地址值”传递给形参

![](https://s1.ax1x.com/2020/08/08/aIjmeP.md.png)

![](https://s1.ax1x.com/2020/08/08/aIjQJg.md.png)

![](https://s1.ax1x.com/2020/08/08/aIjuo8.png)

方法的参数传递示意图：

![](https://s1.ax1x.com/2020/08/08/aIjMFS.md.png)

![](https://s1.ax1x.com/2020/08/08/aIjlWQ.md.png)

### 递归(recursion)方法

递归方法：一个方法体内调用它自身。

方法递归包含了一种隐式的循环，它会重复执行某段代码，但这种重复执行无须循环控制。

递归一定要向已知方向递归，否则这种递归就变成了无穷递归，类似于死循环。

    //计算1-100之间所有自然数的和
    public int sum(int num){
    if(num == 1){
    return 1;
    }else{
    return num + sum(num - 1);
    } }