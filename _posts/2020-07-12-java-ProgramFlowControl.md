---
layout: post
title: "java 学习笔记（3）——程序流程控制"
date: 2020-07-12 11:26:35 +0800
categories: notes
tags: java
img: https://s1.ax1x.com/2020/07/12/U1oQN4.png
---
程序流程控制;顺序结构;分支结构;循环结构;嵌套循环

流程控制语句是用来控制程序中各语句执行顺序的语句，可以把语句组
合成能完成一定功能的小逻辑模块

其流程控制方式采用结构化程序设计中规定的三种基本流程结构，即：

* 顺序结构：程序从上到下逐行地执行，中间没有任何判断和跳转。
* 分支结构：根据条件，选择性地执行某段代码。
* 循环结构：根据循环条件，重复性的执行某段代码。


## 顺序结构

Java中定义成员变量时采用合法的前向引用

![](https://s1.ax1x.com/2020/07/12/U3IUPJ.md.png)

## 分支结构

### if-else结构

if语句三种格式：

![](https://s1.ax1x.com/2020/07/12/U3IaG9.md.png)

![](https://s1.ax1x.com/2020/07/12/U3Id2R.md.png)

#### 分支结构：if-else使用说明

1. 条件表达式必须是布尔表达式（关系表达式或逻辑表达式）、布尔变量
2. 语句块只有一条执行语句时，一对{}可以省略，但建议保留
3. if-else语句结构，根据需要可以嵌套使用
4. 当if-else结构是“多选一”时，最后的else是可选的，根据需要可以省略
5. 当多个条件是“互斥”关系时，条件判断语句及执行语句间顺序无所谓
当多个条件是“包含”关系时，“小上大下 / 子上父下”

### switch-case结构

![](https://s1.ax1x.com/2020/07/12/U3Iwx1.md.png)

#### switch语句有关规则

1. switch(表达式)中表达式的值必须是下述几种类型之一：byte，short，char，int，枚举 (jdk 5.0)，String (jdk 7.0)；
2. case子句中的值必须是常量，不能是变量名或不确定的表达式值；
3. 同一个switch语句，所有case子句中的常量值互不相同；
4. break语句用来在执行完一个case分支后使程序跳出switch语句块；如果没有break，程序会顺序执行到switch结尾
5. default子句是可任选的。同时，位置也是灵活的。当没有匹配的case时，
执行default

#### switch和if语句的对比

如果判断的具体数值不多，而且符合byte、short 、char、int、String、枚举等几
种类型。虽然两个语句都可以使用，建议使用swtich语句。因为效率稍高

其他情况：对区间判断，对结果为boolean类型判断，使用if，if的使用范围更广。
也就是说，使用switch-case的，都可以改写为if-else。反之不成立。

## 循环结构

在某些条件满足的情况下，反复执行特定代码的功能

#### 分类

* for循环
* while循环
* do-while循环

![](https://s1.ax1x.com/2020/07/12/U3IYaF.png)

#### 循环语句的四个组成部分

1. 初始化部分
2. 循环条件部分
3. 循环体部分
4. 迭代部分

### for循环

#### 语法格式

    for (①初始化部分; ②循环条件部分; ④迭代部分)｛
    	 ③循环体部分;
     ｝

执行过程

①-②-③-④-②-③-④-②-③-④-.....-②

**说明**

②循环条件部分为boolean类型表达式，当值为false时，退出循环

①初始化部分可以声明多个变量，但必须是同一个类型，用逗号分隔

④可以有多个变量更新，用逗号分隔

### while循环

#### 语法格式

①初始化部分

    while(②循环条件部分)｛
     	③循环体部分; ④迭代部分; 
    }

执行过程：

①-②-③-④-②-③-④-②-③-④-...-②

说明：

注意不要忘记声明④迭代部分。否则，循环将不能结束，变成死循环。 

for循环和while循环可以相互转换

### do-while循环

#### 语法格式

    ①初始化部分;
    do{
    ③循环体部分
    ④迭代部分
    }while(②循环条件部分)

执行过程：

①-③-④-②-③-④-②-③-④-...②

说明：

do-while循环**至少执行一次**循环体。

## 嵌套循环

嵌套循环(多重循环)

将一个循环放在另一个循环体内，就形成了嵌套循环。其中，for ,while ,do…while均可以作为外层循环或内层循环。

实质上，嵌套循环就是把内层循环当成外层循环的循环体。当只有内层循环的循环条件为false时，才会完全跳出内层循环，才可结束外层的当次循环，开始下一次的循环。

设外层循环次数为m次，内层为n次，则内层循环体实际上需要执行m*n次。

## 特殊关键字的使用break、continue

### break 语句

break语句用于终止某个语句块的执行

    { ……
    break;
    ……
    } 
    

break语句出现在多层嵌套的语句块中时，可以通过标签指明要终止的是哪一层语句块

    label1: { ……
    label2: 	{ ……
    label3: 		{ ……
    				break label2;
    				……
    				} 
    			} 
    		}


### continue 语句

* continue只能使用在循环结构中
* continue语句用于跳过其所在循环语句块的**一次**执行，继续下一次循环
* continue语句出现在多层嵌套的循环语句体中时，可以通过标签指明要跳过的是哪一层循环

continue语句用法举例

    public class ContinueTest {
    	public static void main(String args[]){
    		for (int i = 0; i < 100; i++) {
    			if (i%10==0)
    				continue;
    			System.out.println(i); 
    		} 
    	} 
    }

### 特殊流程控制语句

return：并非专门用于结束循环的，它的功能是结束一个方法。当一个方法执行到一个return语句时，这个方法将被结束。

与break和continue不同的是，return直接结束整个方法，不管这个return处于多少层循环之内

#### 说明

* break只能用于**switch语句**和**循环语句**中。
* continue 只能用于循环语句中。
* 二者功能类似，但continue是终止本次循环，break是终止本层循环。
* break、continue之后不能有其他的语句，因为程序永远不会执行其后的语句。
* 标号语句必须紧接在循环的头部。标号语句不能用在非循环语句的前面。
* 很多语言都有goto语句，goto语句可以随意将控制转移到程序中的任意一条
语句上，然后执行它。但使程序容易出错。Java中的break和continue是不同
于goto的

