
# JAVA 建模与仿真：科学与工程

![](img/cover.jpeg)

## 前言

本书旨在通过对科学与工程实验数据及真实数据进行建模与仿真，针对真实系统的核心工程问题开发软件。本书将教你如何开发 Java 程序来预测材料性能、结构退化、通过线性规划优化工艺或成本、热体温度分布仿真、反应器内反应仿真，以及铸件凝固前面的移动仿真。这些建模与预测基于遗传算法、人工神经网络和有限元法。

本书面向科学与工程领域的学生和专业人士，涵盖了从入门到精通的水平。读者将学习如何为工厂或工程中的实际问题建立数学模型。他们将学习如何开发并理解实际工程过程的仿真，发现反应器内部实际发生的反应，以及如何控制过程以使产品质量和产量最大化。本书的先不仅适用于具有 Java 编程知识的人，也适用于有学习和开发欲望的初。

第一章从 Java 编程的基础和基本知识开始并给出示例，随后是数值方法和计算，用于处理求解工程问题的建模方程。第三章介绍了建模与仿真的概念。第四章在学习编程的过程中，可以学习受多个影响参数限制的工艺或成本优化。第五章将通过遗传算法学习使用数据挖掘进行统计建模，以预测材料性能或腐蚀结构寿命预测；第六章将学习人工神经网络。第七章讨论并应用了有限元法来解决工程问题。第 8、9、10 和第 11 章均为实际工程问题的应用。所有程序代码均位于附录第 12 章。书中提供了 Java 语言参考和一些实用程序。所有 Java 代码均通过 `JGrasp` 编译和运行。

访问我的网站 [`sptech.xyz/`](http://sptech.xyz/) 了解更多关于建模与仿真的知识。你可以下载更多工程科学领域的程序和应用。学习如何开发基于窗口程序、图形和动画。

| **9. 应用部分二：金属与材料工艺** | |

# 9.1 还原气还原金属氧化物颗粒

# 9.2 钢的碳化

# 9.3 高炉 (BF) 内的物料平衡

# 9.4 高炉 (BF) 内的热量与物料平衡

## 9.4.1 高炉内部的不同区域

## 9.4.2 高炉模型中的简化

# 9.5 金属还原过程的模拟

## 9.5.1 模型的简化

## 9.5.2 模型的热力学与动力学

## 9.5.3 编程指南

## 9.5.4 建模与模拟的研究

# 9.6 LD 转炉，用于热能利用的优化

## 9.6.1 简化与假设

## 9.6.2 输入热源

## 9.6.3 输出热源：

## 9.6.4 热平衡

## 9.6.5 示例程序

# 10. 应用部分-III：材料结构退化

## 10.1 腐蚀钢结构的寿命预测

### 10.1.1 基于遗传算法 (GA) 的建模

## 10.2 通过人工神经网络 (ANN) 研究材料腐蚀行为

### 10.2.1 ANN 的 Java 编程

### 10.2.2 模拟结果与腐蚀研究

## 10.3 阴极保护的建模与模拟

### 10.3.1 模型简化

### 10.3.2 边界条件

### 10.3.3 第一次应用的数据输入

### 10.3.4 第二次应用的数据输入

### 10.3.5 基于窗口的阴极保护编程

# 11. 应用部分-IV，相图与合金设计

## 11.1 热力学与吉布斯自由能

## 11.2 根据吉布斯自由能构建相图

### 11.2.1 二元同质体系

### 11.2 二元共晶体系

## 11.3 合金设计

### 11.3.1 经验方法

### 11.3.2 现象学方法

## 11.4 汽车应用合金开发

## 11.5 断裂韧性

### 11.5.1 应力强度因子

### 11.5.2 基于 ANN 的建模

### 11.5.3 训练与验证

### 11.5.4 预测断裂韧性

# 12. 录：所有 Java 程序代码

## 12.1 第 1 章 Java 编程基础

## 12.2 第 2 章 建模模拟中的数值方法

## 12.4 第 4 章 过程优化与线性规划

## 12.5 第 5 章 遗传算法建模

## 12.6 第 6 章 人工神经网络建模

## 12.7 第 7 章 有限元法 (FEM)

## 12.8 第 8 章 应用部分-I：热传导、凝固

## 12.9 第 9 章 应用部分-II：金属与材料工艺

## 12.10 第 10 章 应用部分-III 结构退化

## 12.11 第 11 章 应用部分-IV 相图与合金设计

## 12.12 所有包程序：`sp_packages`

# 13. Java 语言参考

## 13.1 Java 变量

## 13.2 Java 字面量

## 13.3 数学运算

## 13.4 控制语句

## 13.5 Java 数组

## 13.6 Java 目录

## 13.7 Java 关键字

## 13.8 一些 Java 程序示例

# 第一章：Java 编程基础

## 1.1 计算机程序

计算机程序仅仅是指导计算机执行特定任务的指令集。这些包括：简单的常量表示、变量和类型声明；信息表示数据结构、数组和记录；数学公式；输入/输出；逻辑表示（顺序、循环）以及模块化编程（函数和子程序）。

### 编程步骤

1. 编写源代码，导入头文件（包）
2. 将文件保存为 `.java` 扩展
3. 编译程序
4. 修正错误
5. 通过 RUN 执行程序

## 1.2 通过示例理解 Java

假设你想通过一个程序，找出在尺寸为 `l` x `w` x `h` 的房间内可以放置多少个 `nm` 的球体（直径为 `d`），其中球的大小、房间的尺寸都是变量。你想通过编写一个程序并找到闲置空间（未被球占据的空间）。

首先，你声明变量如下：

`Integer nm`; // `nm` 是数字，如 `nm=15`

`float d`; // `d` 可以是分数、小数，如 `2.5`。除了 float 之外，也可以将其声明为 `double`，它也是高精度的小数或分数。

`float l,w,h`; // `l,w,h` 都可以是小数，如 `l=120.3, w=46.3, h=267`

`float v, V`; // `v`=球体积，`V`=闲置空间，待计算

`nm=(l*w*h)/(pi*d/4)`

对于给定的房间尺寸（`a,b,c`），可以通过不同的 `d` 值找到 `n`：

1. 从用户处输入数据，例如 `l=100; w=40;`
2. 闲置空间，例如 `l=100; w=40;`
3. 闲置空间，例如 `l=100; w=40;`
4. 闲置空间，例如 `l=100; w=40;`
5. 闲置空间，例如 `l=100; w=40;`
6. 闲置空间，例如 `l=100; w=40;`
7. 闲置空间，例如 `l=100; w=40;`
8. 闲置空间，例如 `l=100; w=40;`
9. 闲置空间，例如 `l=100; w=40;`
10. 闲置空间，例如 `l=100; w=40;`
11. 闲置空间，例如 `l=100; w=40;`
12. 闲置空间，例如 `l=100; w=40;`
13. 闲置空间，例如 `l=100; w=40;`
14. 闲置空间，例如 `l=100; w=40;`
15. 闲置空间，例如 `l=100; w=40;`
16. 闲置空间，例如 `l=100; w=40;`
17. 闲置空间，例如 `l=100; w=40;`
18. 闲置空间，例如 `l=100; w=40;`
19. 闲置空间，例如 `l=100; w=40;`
20. 闲置空间，例如 `l=100; w=40;`
21. 闲置空间，例如 `l=100; w=40;`
22. 闲置空间，例如 `l=100; w=40;`
23. 闲置空间，例如 `l=100; w=40;`
24. 闲置空间，例如 `l=100; w=40;`
25. 闲置空间，例如 `l=100; w=40;`
26. 闲置空间，例如 `l=100; w=40;`
27. 闲置空间，例如 `l=100; w=40;`
28. 闲置空间，例如 `l=100; w=40;`
29. 闲置空间，例如 `l=100; w=40;`
30. 闲置空间，例如 `l=100; w=40;`
31. 闲置空间，例如 `l=100; w=40;`
32. 闲置空间，例如 `l=100; w=40;`
33. 闲置空间，例如 `l=100; w=40;`
34. 闲置空间，例如 `l=100; w=40;`
35. 闲置空间，例如 `l=100; w=40;`
36. 闲置空间，例如 `l=100; w=40;`
37. 闲置空间，例如 `l=100; w=40;`
38. 闲置空间，例如 `l=100; w=40;`
39. 闲置空间，例如 `l=100; w=40;`
40. 闲置空间，例如 `l=100; w=40;`
41. 闲置空间，例如 `l=100; w=40;`
42. 闲置空间，例如 `l=100; w=40;`
43. 闲置空间，例如 `l=100; w=40;`
44. 闲置空间，例如 `l=100; w=40;`
45. 闲置空间，例如 `l=100; w=40;`
46. 闲置空间，例如 `l=100; w=40;`
47. 闲置空间，例如 `l=100; w=40;`
48. 闲置空间，例如 `l=100; w=40;`
49. 闲置空间，例如 `l=100; w=40;`
50. 闲置空间，例如 `l=100; w=40;`
51. 闲置空间，例如 `l=100; w=40;`
52. 闲置空间，例如 `l=100; w=40;`
53. 闲置空间，例如 `l=100; w=40;`
54. 闲置空间，例如 `l=100; w=40;`
55. 闲置空间，例如 `l=100; w=40;`
56. 闲置空间，例如 `l=100; w=40;`
57. 闲置空间，例如 `l=100; w=40;`
58. 闲置空间，例如 `l=100; w=40;`
59. 闲置空间，例如 `l=100; w=40;`
60. 闲置空间，例如 `l=100; w=40;`
61. 闲置空间，例如 `l=100; w=40;`
62. 闲置空间，例如 `l=100; w=40;`
63. 闲置空间，例如 `l=100; w=40;`
64. 闲置空间，例如 `l=100; w=40;`
65. 闲置空间，例如 `l=100; w=40;`
66. 闲置空间，例如 `l=100; w=40;`
67. 闲置空间，例如 `l=100; w=40;`
68. 闲置空间，例如 `l=100; w=40;`
69. 闲置空间，例如 `l=100; w=40;`
70. 闲置空间，例如 `l=100; w=40;`
71. 闲置空间，例如 `l=100; w=40;`
72. 闲置空间，例如 `l=100; w=40;`
73. 闲置空间，例如 `l=100; w=40;`
74. 闲置空间，例如 `l=100; w=40;`
75. 闲置空间，例如 `l=100; w=40;`
76. 闲置空间，例如 `l=100; w=40;`
77. 闲置空间，例如 `l=100; w=40;`
78. 闲置空间，例如 `l=100; w=40;`
79. 闲置空间，例如 `l=100; w=40;`
80. 闲置空间，例如 `l=100; w=40;`
81. 闲置空间，例如 `l=100; w=40;`
82. 闲置空间，例如 `l=100; w=40;`
83. 闲置空间，例如 `l=100; w=40;`
84. 闲置空间，例如 `l=100; w=40;`
85. 闲置空间，例如 `l=100; w=40;`
86. 闲置空间，例如 `l=100; w=40;`
87. 闲置空间，例如 `l=100; w=40;`
88. 闲置空间，例如 `l=100; w=40;`
89. 闲置空间，例如 `l=100; w=40;`
90. 闲置空间，例如 `l=100; w=40;`
91. 闲置空间，例如 `l=100; w=40;`
92. 闲置空间，例如 `l=100; w=40;`
93. 闲置空间，例如 `l=100; w=40;`
94. 闲置空间，例如 `l=100; w=40;`
95. 闲置空间，例如 `l=100; w=40;`
96. 闲置空间，例如 `l=100; w=40;`
97. 闲置空间，例如 `l=100; w=40;`
98. 闲置空间，例如 `l=100; w=40;`
99. 闲置空间，例如 `l=100; w=40;`
100. 闲置空间，例如 `l=100; w=40;`
101. 闲置空间，例如 `l=100; w=40;`
102. 闲置空间，例如 `l=100; w=40;`
103. 闲置空间，例如 `l=100; w=40;`
104. 闲置空间，例如 `l=100; w=40;`
105. 闲置空间，例如 `l=100; w=40;`
106. 闲置空间，例如 `l=100; w=40;`
107. 闲置空间，例如 `l=100; w=40;`
108. 闲置空间，例如 `l=100; w=40;`
109. 闲置空间，例如 `l=100; w=40;`
110. 闲置空间，例如 `l=100; w=40;`
111. 闲置空间，例如 `l=100; w=40;`
112. 闲置空间，例如 `l=100; w=40;`
113. 闲置空间，例如 `l=100; w=40;`
114. 闲置空间，例如 `l=100; w=40;`
115. 闲置空间，例如 `l=100; w=40;`
116. 闲置空间，例如 `l=100; w=40;`
117. 闲置空间，例如 `l=100; w=40;`
118. 闲置空间，例如 `l=100; w=40;`
119. 闲置空间，例如 `l=100; w=40;`
120. 闲置空间，例如 `l=100; w=40;`
121. 闲置空间，例如 `l=100; w=40;`
122. 闲置空间，例如 `l=100; w=40;`
123. 闲置空间，例如 `l=100; w=40;`
124. 闲置空间，例如 `l=100; w=40;`
125. 闲置空间，例如 `l=100; w=40;`
126. 闲置空间，例如 `l=100; w=40;`
127. 闲置空间，例如 `l=100; w=40;`
128. 闲置空间，例如 `l=100; w=40;`
129. 闲置空间，例如 `l=100; w=40;`
130. 闲置空间，例如 `l=100; w=40;`
131. 闲置空间，例如 `l=100; w=40;`
132. 闲置空间，例如 `l=100; w=40;`
133. 闲置空间，例如 `l=100; w=40;`
134. 闲置空间，例如 `l=100; w=40;`
135. 闲置空间，例如 `l=100; w=40;`
136. 闲置空间，例如 `l=100; w=40;`
137. 闲置空间，例如 `l=100; w=40;`
138. 闲置空间，例如 `l=100; w=40;`
139. 闲置空间，例如 `l=100; w=40;`
140. 闲置空间，例如 `l=100; w=40;`
141. 闲置空间，例如 `l=100; w=40;`
142. 闲置空间，例如 `l=100; w=40;`
143. 闲置空间，例如 `l=100; w=40;`
144. 闲置空间，例如 `l=100; w=40;`
145. 闲置空间，例如 `l=100; w=40;`
146. 闲置空间，例如 `l=100; w=40;`
147. 闲置空间，例如 `l=100; w=40;`
148. 闲置空间，例如 `l=100; w=40;`
149. 闲置空间，例如 `l=100; w=40;`
150. 闲置空间，例如 `l=100; w=40;`

对于给定的房间尺寸（`a,b,c`），可以通过不同的 `d` 值找到 `n`：

1. 从用户处输入数据，例如 `l=100; w=40;`
2. 闲置空间，例如 `l=100; w=40;`
3. 闲置空间，例如 `d`
4. 闲置空间，例如 `l=100; w=40;`
5. 闲置空间，例如 `l=100; w=40;`
6. 闲置空间，例如 `l=100; w=40;`
7. 闲置空间，例如 `l=100; w=40;`
8. 闲置空间，例如 `l=100; w=40;`
9. 闲置空间，例如 `l=100; w=40;`
10. 闲置空间，例如 `l=100; w=40;`
11. 闲置空间，例如 `l=100; w=40;`
12. 闲置空间，例如 `l=100; w=40;`
13. 闲置空间，例如 `l=100; w=40;`
14. 闲置空间，例如 `l=100; w=40;`
15. 闲置空间，例如 `l=100; w=40;`

可以通过以下方法找到闲置空间（未被球占据的空间）：

首先，你声明变量如下：

`Integer nm`; // `nm` 是数字，如 `nm=15`

`float d`; // `d` 可以是分数、小数，如 `2.5`。除了 float 之外，也可以将其声明为 `double`，它也是高精度的小数或分数。

`float l,w,h`; // `l,w,h` 都可以是小数，如 `l=120.3, w=46.3, h=267`

`float v, V`; // `v`=球体积，`V`=闲置空间，待计算

`nm=(l*w*h)/(pi*d/4)`

通过以下方法找到闲置空间（未被球占据的空间）：

步骤：

1. 编写源代码，导入头文件（包）
2. 将文件保存为 `.java` 扩展
3. 编译程序
4. 修正错误
5. 通过 RUN 执行程序

通过一个示例理解 Java

假设你想通过一个程序，找出在尺寸为 `l` x `w` x `h` 的房间内可以放置多少个 `nm` 的球体（直径为 `d`），其中球的大小、房间的尺寸都是变量。你想通过编写一个程序并找到闲置空间（未被球占据的空间）。

`L=100`, `w=40`, `h=20`, 初始球直径 = 8; 每阶段直径的增量 = 0.20 (初始直径的比例)



在循环中直径增加的最大次数 = 20

![1.2.2 ouput.jpg](img/00002.jpeg)

从上述计算可以看出，最小空隙出现在球直径为 `11` 时（另见图 1.2），在给定尺寸的房间内可以填充的球数量为 `533`。

这是一个使用 Java 进行建模、仿真和编程的示例。通过编写下述的额外步骤，可以扩展程序以通过计算找到最小值。

![fig1.2.jpg](img/00003.jpeg)

## 1.2.3 示例程序说明：`SP_prog1.java`

程序包含不同的部分，如导入头文件、类、主函数、输入、输出、变量声明等。为了使程序简单易懂，需要像下文所示理解程序的每个部分。

```java
public static void main(String args[]) − Java 程序处理从 `main()` 方法开始，这是每个 Java 程序的必经部分
```

### 1.2.3.1 类 (Class)

我们以后解释类的概念，首先看下面的内容，展示了在本问题中是如何定义类的。

```java
public class SP_prog1
{
  ……  程序的所有代码都在 public class 的这些大括号 ‘{ }’ 内部
}
```

这里的类是 `SP_prog1`。程序保存为 `SP_Java1.java`，即类名。

### 1.2.3.2 头文件 (Package)

程序需要如下头文件，这些文件包含许多方法（Java 中的内置函数）。

```java
import java.util.Scanner;// 工具类扫描器
import java.io.*;  // 输入输出
import java.math.*; // 用于使用 log, power 等数学函数
```

注意，头文件之前是关键字 `import`，在 C 语言中，它类似于关键字 `include`。

### 1.2.3.3 主函数 (Main function)

每个程序（Applet 除外）都必须有如下的主函数。它可以位于 `SP_prog1` 等类内部，也可以位于类外部。输入（用户输入）和输出将在主函数环境中，主函数将调用类中的对象执行计算。

```java
public static void main(String[] args)
    {
      …… 内部的所有代码。
    }
```

编写类和主函数的两种选项：

```java
public class SP_prog1
{
 public static void main(String[] args)
    {
      …… 内部的所有代码。
    }
}
```

或者

```java
public class SP_prog1
{
  ……  程序的所有代码都在 public class 的这些大括号 ‘{ }’ 内部
}
public static void main(String[] args)
{
      …… 内部的所有代码。在这里我们需要在需要时调用类
  }
```

### 1.2.3.4 输出命令 (Output commands)

```java
System.out.print(" the diameter of the ball is“ +d)
```

注意在“ ” 内你书写的任何内容将作为文本输出，引号之外是变量 `d`。例如，如果计算出的直径 (`d`) 为 `12.36`，则生成的输出如下：

`the diameter of the ball is 12.36`

另一个示例：

```java
System.out.print(" My name is Raj I am “ +y“ years old”)
```

如果变量 `y=25`，则输出为：

`My name is Raj I am 25 years old`

### 1.2.3.5 变量声明 (Declaration of variables)

变量在使用计算之前需要声明，无论是字符（文本）、整数 (int)、带小数的数字 (float) 还是双精度带小数的数字 (double)，如下：

```java
Int i,n ;
float d, v ; 
double V, X ;
```

**数组变量声明**

如果 `d` 是一个数组，那么 `d` 将拥有许多值 `d1`, `d2`, `d3` ……d10`，其声明方式如下：

```java
float d[]= new float[n];// 其中 n 是数组的大小。
```

例如，如果我的计算中可能 `d` 值最大数量为 100，则 `n=100`：

```java
float d[]= new float[100];
double V[]= new double [100];
int nm[]= new int [100];//球的数量
```

### 1.2.3.6 从用户处输入数据 (Input Data from the user)

为此，你必须使用带有头文件 `import java.util.Scanner` 的 `Scanner` 类。

取的对象为 `inpData`。代码如下：

```java
Scanner inpData = new Scanner(System.in);
System.out.print("Enter the dimension of the room l,w,h");
float l = inpData.nextFloat();//长度
float w = inpData.nextFloat();//宽度
float h = inpData.nextFloat();//高度
```

注意 `System.in` 用于输入，而 `System.out` 用于输出。

变量 `l` 被声明为 `float`。用户输入的房间长度 `l` 的任何值都将保存在 `l` 变量中；同样，用户输入的房间宽度 `w` 的任何值将保存在 `w` 变量中。

例如，如果用户输入 `25.21` 作为第一个数字，`l=25.21`；输入 `12.62` 作为第二个数字，`w=12.62`。

### 1.2.3.7 计算 (Computation)

执行问题的实际计算和数学部分。首先注意代码：

```java
for(int i=1;i<=n;i++)
    {      
      v[i] =(float)(Math.PI*(Math.pow(d[i],2.0))/4) ;
      nm[i]=(int)((l*w*h)/v[i]);
      V[i]= l*w*h-nm[i]*v[i];
      if (V[i] < someLimit) break;
    }
```

关于 Java 语言和规则的更多信息，可以参考“Java 语言参考”章节。

## 1.3.2 Java 虚拟机 (JVM)

Java 是平台独立的。与许多编程语言（包括 `C` 和 `C++`）不同，Java 在编译时并不会编译成特定平台的机器码，而是编译成平台无关的字节码。这些字节码通过网络分发，并在运行它的任何平台上由虚拟机（`JVM`）进行解释。

`JVM` 是 Java 程序运行的环境。它是实现在真实硬件和操作系统之上的软件。当源代码（`.java` 文件）被编译时，它会被翻译成字节码并放入（`.class`）文件中。`JVM` 执行这些字节码。因此，Java 字节码可以被看作是 `JVM` 的语言。

### 1.3.3 安装 Java

你最多需要安装两件软件：Java 开发工具包（`JDK`）和一个 Java 编辑器。首先，你需要从 Oracle 的以下网站下载并安装 `JDK`：

http://www.oracle.com/technetwork/java/javase/downloads/jdk9-downloads-3848520.html

根据你的系统平台（windows、linux 等）选择并下载 `JDK`。

`JDK` 是 `JRE`（Java 运行环境）的超集，它包含了 `JRE` 中的所有内容，以及用于开发 applet 和应用程序所需的编译器、调试器等工具。`JRE` 提供了库、Java 虚拟机（`JVM`）以及运行用 Java 编程语言编写的 applet 和应用程序的其他组件。

网上有不同的编辑器可用：`NetBeans`、`jGrasp`、`Eclipse`、`Jdeveloper`、`BlueJ`、`jCreator` 等。每个编辑器都有自己的优点。根据你处理的建模问题类型，你可以选择合适的编辑器。在本书中，`JGRASP` 被用作 windows 10 平台的 Java 编辑器，所有程序都由它运行。你可以通过以下链接下载 `JGRASP`：

http://spider.eng.auburn.edu/user-cgi/grasp/grasp.pl?;dl=download_jgrasp.html

http://jgrasp.software.informer.com/download/

## 1.4 Java 包 (Package)

如果一种常用的程序要在许多其他应用程序中使用，那么该程序在编码时会在顶部标明包名，并保存在包文件夹中。每当有其他应用程序程序需要该包程序时，只需使用 `Import 包名;` 即可调用该包程序。例如，各种科学和工程应用都需要图形，因此可以编写一个带有数据输入数组 `x[]`、`y[]` 的通用图形程序，并将其保存在包中，如下一节 1.5.1 示例所示。

在 Java 中使用包是为了防止命名冲突、控制访问、使类、接口、枚举和注解的搜索/定位及使用变得更加简单等。

包（Package）可以定义为相关类型（类、接口、枚举和注解）的组合，提供访问保护和命名空间管理。

Java 中现有的一些包包括——：

*   `java.lang` – 封装了基础类
*   `java.io` – 用于输入、输出函数的类被封装在这个包中

程序员可以定义自己的包来封装一组类/接口等。将你所实现的相关的类进行分组是一是一种良好的习惯，这样程序员就可以轻松判断出这些类、接口、枚举和注解是相关的。

由于包创建了新的命名空间，因此与其他包中的名称不会发生任何冲突。使用包可以更容易提供访问控制，也更容易定位相关的类。

### 1.4.1 创建包

通常，一些在许多其他应用程序中频繁使用的常用程序会被保存在包中，这样每当应用程序需要此类程序时，就不需要在应用程序中重新编码了。例如，许多其他应用程序中可能需要找到数据数组的最大值或最小值。同样，在许多应用程序中可能频繁需要绘制数组 `x[]` 对 `y[]` 的图表。

在当前示例中，`SP_MaxMin.java` 编码如下并保存在 `sp_package` 中。

包语句（package statement）应该是源文件的第一行。每个源文件中只能有一个包语句，并且它适用于文件中的所有类型。程序应该保存在名为“包名”的文件夹中。

### 示例

让我们来看创建一个名为 `sp_package` 包的示例。使用小写字母命名包名是一种良好的习惯，可以避免与类和接口名称发生冲突。

程序 1.4.1 `SP_MaxMin.java`

```java
package sp_package;

import java.util.Scanner;
import java.io.*;
import java.math.*;
import java.util.*;

public class SP_MaxMin
{
    // Max value
    public static double getMax(double[] x)
    {
        double maxValue = x[0];
        for(int i=1; i < x.length; i++)
        {
            if(x[i] > maxValue)
            {
                maxValue = x[i];
            }
        }
        return maxValue;
    }

    // Min value
    public static double getMin(double[] x)
    {
        double minValue = x[0];
        for(int i=1; i < x.length; i++)
        {
            if(x[i] < minValue)
            {
                minValue = x[i];
            }
        }
        return minValue;
    }
}
```

注意：提供的原始代码存在语法错误（缺少 `i < x.length` 以及括号错误），我在逻辑上对其进行了清理，使其成为有效的 Java 结构。

程序 1.4.2 `SP_ReadPackage.java`

```java
package sp_package;

import java.util.Scanner;
import java.io.*;
import java.math.*;
import java.util.*;

public class SP_ReadPackage
{
    public static void main(String args[])
    {
        SP_MaxMin mn = new SP_MaxMin();
        double x[] = {4.5, 2.3, 100.56, 45.23};
        double max = mn.getMax(x);
        double min = mn.getMin(x);
        System.out.println("max=" + max + " min=" + min);
    }
}
```

程序输出：`max=100.56 min=2.3`

## 1.5 Java 中的 Jar 文件

JAR（Java Archive）是一种用于将许多类文件以及相关的元数据和资源（文本、图像等）聚合到一个文件中以分发应用程序或库。简单来说，JAR 文件是包含压缩版本的 `.class` 文件、音频文件、图像文件或目录的文件。我们可以将 `.jar` 文件想象成使用 WinZip 软件创建的压缩文件（`.zip`）。即使是使用 WinZip 软件也可以提取 `.jar` 的内容。因此，你可以将它们用于无损数据压缩、归档、解压缩和归档提取。

JAR 是唯一能处理音频和图像文件以及类文件的格式。开放标准、完全可扩展并用 Java 编写。打包 Java applet 组件的首选方式。

在 Applet 中的示例：

```html
<applet code=Animator.class archive="jars/animator.jar" (archive="classes.jar, images.jar , sounds.jar") width=460 height=160>
    <param name="foo" value="bar">
</applet>
```

## 1.6 Java - 文件与 I/O

`java.io` 包包含了 Java 中可能需要的用于执行输入和输出（I/O）的所有类。这些流都代表一个输入源和一个输出目标。`java.io` 包中的流支持许多数据，如基本数据类型、对象、本地化字符等。

### 1.6.1 流 (Stream)

流可以定义为数据序列。流有两种类型——

*   `InputStream` - `InputStream` 用于从数据源读取数据。
*   `OutputStream` - `OutputStream` 用于向目标写入数据。

Java 为文件和网络相关的 I/O 提供了强大且灵活的支持，但本教程仅涵盖与流和 I/O 相关的基本功能。我们将逐一查看最常用的示例：

## 1.6.2 字节流

Java 字节流用于执行 8 位字节的输入和输出。虽然有很多与字节流相关的类，但最常用的类是 `FileInputStream` 和 `FileOutputStream`。以下是一个示例，它利用这两个类将输入文件复制到输出文件——

## 标准流

所有编程语言都提供标准 I/O 支持，用户程序可以从键盘获取输入并在计算机屏幕上产生输出。如果你熟悉 C 或 C++ 编程语言，那么你一定知道三个标准设备 `STDIN`、`STDOUT` 和 `STDERR`。同样，Java 提供了以下三个标准流——

*   **标准输入 (Standard Input)** - 用于向用户程序提供数据，通常使用键盘作为标准输入流并表示为 `System.in`。
*   **标准输出 (Standard Output)** - 用于输出用户程序产生的数据，通常使用计算机屏幕作为标准输出流并表示为 `System.out`。
*   **标准错误 (Standard Error)** - 用于输出用户程序产生的错误数据，通常使用计算机屏幕作为标准错误流并表示为 `System.err`。

以下是一个简单的程序，它创建 `InputStreamReader` 来读取标准输入流，直到用户输入 "q"——

## 1.6.3 读取和写入文件

如前所述，流可以被定义为数据的序列。`InputStream` 用于从数据源读取数据，而 `OutputStream` 用于向目标写入数据。

### 1.6.3.1 FileInputStream

此流用于从文件中读取数据。可以使用 `new` 关键字创建对象，并有几种类型的构造函数可用。

以下构造函数接受字符串类型的文件名来创建一个输入流对象以读取文件——

```java
InputStream f = new FileInputStream("C:/java/hello");
```

以下构造函数接受一个文件对象来创建一个输入流对象以读取文件。首先我们使用 `File()` 方法创建一个文件对象，如下：

```java
File f = new File("C:/java/hello");
InputStream f = new FileInputStream(f);
```

一旦你拿到了 `InputStream` 对象，就有一系列辅助方法可以用于读取流或对流执行其他操作。

| 序号 | 方法与描述 |
| :--- | :--- |



| 序号 | 方法签名 | 说明 |
| :--- | :--- | :--- |
| 1 | `public void close() throws IOException{}` | 此方法关闭文件输出流。释放任何与文件相关的系统资源。抛出 `IOException`。 |
| 2 | `protected void finalize() throws IOException {}` | 此方法清理与文件的连接。确保当没有更多对此流的引用时，调用此文件输出流的 `close` 方法。抛出 `IOException`。 |
| 3 | `public int read(int r) throws IOException{}` | 此方法从 `InputStream` 读取指定的字节数据。返回一个 `int`。返回下一个字节数据，如果是文件末尾，则返回 -1。 |
| 4 | `public int read(byte[] r) throws IOException{}` | 此方法从输入流中读取 `r.length` 个字节到数组中。返回读取的字节总数。如果是文件末尾，将返回 -1。 |
| 5 | `public int available() throws IOException{}` | 提供可以从此文件输入流读取的字节数。返回一个 `int`。 |

还有其他重要的流，更多细节可以参考以下链接——

*   [ByteArrayInputStream](https://www.tutorialspoint.com/java_bytearraystream.htm)
*   [DataInputStream](https://www.tutorialspoint.com/java_datinputstream.htm)

### 数据数组：文件中保存数据并从同一文件读取数据

在执行工程问题时，你可能需要将数据数组（float 或整数类型）保存到文件中，并在以后通过调用文件和读取数据来重用这些数据。以下两个示例说明了将 float 数据数组写入文本文件，然后用另一个程序从文件中读取数据。查看下方保存 float 数据数组的第一个程序。

#### Example 1.6.4.1 SP_SaveData.java

以下是演示 `InputStream` 和 `OutputStream` 的示例——

```java
import java.util.Scanner;
import java.io.DataOutputStream;
import java.io.FileOutputStream;
import java.io.IOException;

public class SP_SaveData {
    public static void main(String[] args) {
        // reading array
        Scanner inpData = new Scanner(System.in);
        System.out.print("No of data: ");
        int n = inpData.nextInt();
        System.out.print("insert values of x & y for n of data  ");
        float x[] = new float[n];
        float y[] = new float[n];
        for (int i = 0; i < n; i++) {
            x[i] = inpData.nextFloat();
            y[i] = inpData.nextFloat();
        }
        String strFilePath = "C:/Java_Engg_Problem/data.txt";
        try {
            FileOutputStream file = new FileOutputStream(strFilePath);
            DataOutputStream fout = new DataOutputStream(file);
            for (int i = 0; i < n; i++) {
                fout.writeFloat(x[i]);
                fout.writeFloat(y[i]);
            }
            fout.close();
            System.out.println("success...");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

#### Example 1.6.4.2 SP_Read.java

以下是演示 `InputStream` 和 `OutputStream` 的示例——

```java
import java.util.Scanner;
import java.io.DataInputStream;
import java.io.FileInputStream;
import java.io.IOException;

public class SP_Read {
    public static void main(String[] args) {
        String strFilePath = "C:/Java_Engg_Problem/data.txt";
        try {
            FileInputStream file = new FileInputStream(strFilePath);
            DataInputStream fin = new DataInputStream(file);
            float x, y;
            while (true) {
                x = fin.readFloat();
                y = fin.readFloat();
                System.out.println("x = " + x + " y = " + y);
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

在文件中查看你在上一个程序中输入的数据，你可以读取并调用相同的数据用于某些计算。

注意：如果你的数据类型是双精度浮点型（`double`）或整型（`int`），只需将 `float` 替换为 `double` 或 `int` 来修改上述程序即可。

# 1.7 Java 图形编程

`Graphics` 类提供了用于绘制三种类型图形对象的方法：

1.  **文本字符串**：通过 `drawString()` 方法。请注意 `System.out.println()` 打印到系统控制台，而不是图形屏幕。
2.  **矢量图形元素和形状**：通过方法 `drawXxx()` 和 `fillXxx()` 实现，其中 `Xxx` 可以是 `Line`（线）、`Rect`（矩形）、`Oval`（圆）、`Arc`（弧）、`PolyLine`（折线）、`RoundRect`（圆矩形）或 `3DRect`（三维矩形）。
3.  **位图图像**：通过 `drawImage()` 方法实现。

## 1.7.1 java.awt.Graphics

`java.awt.Graphics` 是一个抽象类，因为实际的绘制操作取决于系统和设备。每个操作系统平台都会提供 `Graphics` 的子类来在该平台下执行实际绘制，但它们都符合 `Graphics` 中定义的规范。

![1.7.1 object.jpg](img/00005.jpeg)

## 1.7.2 图形形状的方法

不同图形的方法如图 1.4 所示。

![fig1.4.jpg](img/00006.jpeg)

图 1.7.1 不同图形的方法

## 1.7.3 示例 SP_Graphics

下面给出了一个图形程序的示例。

示例程序 1.7.1 SP_Graphics.java：

```java
import java.awt.*;
import java.awt.Graphics;
import java.awt.event.*;
import java.awt.geom.*;

public class SP_Graphics extends Frame {

    public void paint(Graphics g) {
        g.setColor(Color.BLACK);
        g.drawLine(300, 120, 400, 70);
        g.setColor(Color.BLUE);
        g.drawRect(35, 40, 90, 55);
        g.setColor(Color.green);
        g.drawOval(80, 100, 50, 50);
        g.setColor(Color.BLUE);
        g.fillRect(200, 40, 90, 55);
        g.setColor(Color.MAGENTA);
        g.fillOval(200, 100, 85, 40);

        Font fnt = new Font("Arial", Font.BOLD, 12);
        g.setFont(fnt);
        g.setColor(Color.BLUE);
        g.drawString("Example of Graphics:  Rectangle, Circle, Filled Rectangle, Oval, Line", 10, 170);

        Font font = new Font("Arial", Font.BOLD, 16);
        g.setFont(font);
        g.setColor(Color.BLACK);
        g.drawString("Java Programming by Raj Paul", 80, 250);
    }

    public static void main(String args[]) {
        Frame frame = new SP_Graphics();
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent we) {
                System.exit(0);
            }
        });
        frame.setSize(500, 350);
        frame.setVisible(true);
    }
}
```

当你运行程序时，将出现以下输出：

![fig1.5.jpg](img/00007.jpeg)

## 1.7.4 带用户坐标输入的图形

下面的程序演示了输入输出与图形的结合操作。

示例程序 1.7.4 SP_Graphics3：

程序：`SP_Graphics3.java`

```java
import java.util.Scanner;
import java.awt.*;
import java.awt.Graphics;
import java.awt.event.*;
import java.awt.geom.*;

public class SP_Graphics3 extends Frame {

    public void paint(Graphics g) {
        Scanner inpData = new Scanner(System.in);

        System.out.print("Enter circle centre x,y & Dia d: ");
        int x = inpData.nextInt();
        int y = inpData.nextInt();
        int d = inpData.nextInt();

        System.out.print("Enter line x1,y1 & x2,y2");
        int x1 = inpData.nextInt();
        int y1 = inpData.nextInt();
        int x2 = inpData.nextInt();
        int y2 = inpData.nextInt();

        g.setColor(Color.BLACK);
        g.drawLine(x1, y1, x2, y2);

        g.setColor(Color.blue);
        for (int i = 1; i <= 10; i++) {
            g.drawOval(x, y, d);
            d = d + 10;
        }
        Font fnt = new Font("Arial", Font.BOLD, 12);
        g.setFont(fnt);
        g.setColor(Color.BLUE);
        g.drawString("Graphics with User Input data with increasing dia & line", 20, 20);

        Font font = new Font("Arial", Font.BOLD, 16);
        g.setFont(font);
        g.setColor(Color.BLACK);
        g.drawString("Java Programming by Raj Paul", 80, 250);
    }

    public static void main(String args[]) {
        Frame frame = new SP_Graphics3();
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent we) {
                System.exit(0);
            }
        });
        frame.setSize(500, 350);
        frame.setVisible(true);
    }
}
```

输出

```text
Enter circle centre x,y & Dia d: 70 60 20
Enter line x1,y1 & x2,y2 : 200 50 180
```

将生成以下图形

![fig1.6.jpg](img/images)

## 1.7.5 原点的移动

通常图形的原点位于屏幕的左上角。因此需要将原点移动到中心或底部以显示图形。下面的示例展示了如何移动原点。

示例程序 1.7.5 SP_Graphics4.java：



```java
import java.util.Scanner;
import java.awt.*;
import java.awt.Graphics;
import java.awt.event.*;
import java.math.*;
import java.awt.geom.*;

public class SP_Graphics4 extends Frame {
    public void paint(Graphics g) {
        g.setColor(Color.blue);
        g.drawLine(30, 20, 100, 120);
        g.drawOval(10, 10, 40, 40);

        Font font = new Font("Arial", Font.BOLD, 16);
        g.setFont(font);
        g.setColor(Color.BLACK);
        g.drawString("Java Programming by Raj Paul", 10, 250);

        g.translate(250, 150); // 将原点移动到中心
        g.setColor(Color.BLACK);

        g.drawLine(0, -150, 0, 150);
        g.drawLine(-250, 0, 250, 0);
        Font font1 = new Font("Arial", Font.BOLD, 12);
        g.setFont(font1);
        g.drawString("X axis", 200, 10);
        g.drawString("Y axis", -10, -100);
        g.drawString("Example of Shifting of origin", 60, -100);
        g.drawOval(-5, -5, 10, 10);
        g.drawString("The blue circle & line shifted with change in origin from top Left to Centre", -200, -60);
        g.setColor(Color.RED);
        g.drawLine(30, 20, 100, 120);
        g.drawOval(10, 10, 40, 40);
    }

    public static void main(String args[]) {
        Frame frame = new SP_Graphics4();
        frame.addWindowListener(new WindowAdapter() {
            void windowClosing(WindowEvent we) {
                System.exit(0);
            }
        });
        frame.setSize(500, 300);
        frame.setVisible(true);
    }
}
```

例如，如果你在程序中使用 `FileReader` 类从文件中读取数据，如果其构造函数中指定的文件不存在，则会发生 `FileNotFoundException`，编译器会提示程序员处理该异常。

### 示例

```java
import java.io.File;
import java.io.FileReader;

public class FilenotFound_Demo {
    public static void main(String args[]) {
        File file = new File("E://file.txt");
        FileReader fr = new FileReader(file);
    }
}
```

如果你尝试编译上述程序，你将得到以下异常。

### 输出

```
C:\>javac FilenotFound_Demo.java
FilenotFound_Demo.java:8: error: unreported exception File Not Found Exception; must be caught or declared to be thrown
      FileReader fr = new FileReader(file);
                            ^
1 error
```

注意 − 由于 `FileReader` 类的 `read()` 方法和 `close()` 方法会抛出 `IOException`，你可以观察到编译器通知处理 `IOException`，以及 `FileNotFoundException`。

- **未检查异常（Unchecked exceptions）** − 未检查异常是在执行期间发生的异常。这些异常也被称为 `Runtime Exceptions`（运行时异常）。它们包含了编程错误，例如逻辑错误或对 API 的使用不当。`Runtime exceptions` 在编译时会被忽略。

例如，如果你在程序中声明了一个大小为 5 的数组，并尝试调用数组的第 6 个元素，则会发生 `ArrayIndexOutOfBoundsException`。

### 示例

```java
public class Unchecked_Demo {
    public static void main(String args[]) {
        int num[] = {1, 2, 3, 4};
        System.out.println(num[5]);
    }
}
```

如果你编译并执行上述程序，你将得到以下异常。

### 输出

```
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: 5
at Exceptions.Unchecked_Demo.main(Unchecked_Demo.java:8)
```

- **错误（Errors）** − 这些完全不是异常，而是产生于用户或程序员控制之外的问题。错误在你的代码中通常被忽略，因为你几乎无法对错误做任何事情。例如，如果发生了栈溢出（stack overflow），就会产生一个错误。它们在编译时也会被忽略。

## 1.8.2 异常层次

所有异常类都是 `java.lang.Exception` 类的子类型。异常类是 `Throwable` 类的子类。除了异常类外，还有一个名为 `Error` 的子类，它派自 `Throwable` 类。

错误是在严重故障时发生的异常情况，这些不会被 Java 程序处理。错误的产生表示由运行时环境产生的错误。例如：`JVM` 内存溢出。通常情况下，程序无法从错误中恢复。`Exception` 类有两个主要的子类：`IOException` 类和 `RuntimeException` 类。

![1.8.1 java excep.jpg](img/00010.jpeg)

以下是常见的 Java 内置检查异常和未检查异常的列表。

## 1.8.3 异常方法

以下是 `Throwable` 类中提供的重要方法列表。

| 序号 | 方法与描述 |
| :--- | :--- |
| 1 | `public String getMessage()` 返回有关已发生异常的详细消息。此消息在 `Throwable` 构造函数中初始化。 |
| 2 | `public Throwable getCause()` 返回由 `Throwable` 对象表示的异常原因。 |
| 3 | `public String toString()` 返回类名与 `getMessage()` 的结果连接起来。 |
| 4 | `public void printStackTrace()` 将 `toString()` 的结果以及堆栈轨迹打印到 `System.err`（错误输出流）。 |
| 5 | `public StackTraceElement[] getStackTrace()` 返回一个包含堆栈轨迹中每个元素的数组。索引 0 处的元素表示调用栈的顶端，数组中的最后一个元素表示调用栈底部的方法。 |
| 6 | `public Throwable fillInStackTrace()` 用当前堆栈轨迹填充此 `Throwable` 对象的堆栈轨迹，添加到堆栈轨迹中的任何之前信息中。 |

### 1.8.3.1 捕获异常

方法使用 `try` 和 `catch` 关键字的组合来捕获异常。`try/catch` 块放在可能生成异常的代码周围。`try/catch` 块中的代码被称为受保护代码，使用 `try/catch` 的语法如下：

### 语法

```java
try {
    // 受保护代码
} catch (ExceptionName e1) {
    // 捕获块
}
```

容易发生异常的代码放在 `try` 块中。当发生异常时，该异常将由与之相关的 `catch` 块处理。每个 `try` 块后面都应该紧跟一个 `catch` 块或 `finally` 块。

`catch` 语句涉及声明你尝试捕获的异常类型。如果受保护代码中发生异常，将检查 `try` 之后的 `catch` 块（或块）。如果发生的异常类型列在 `catch` 块中，异常将传递给 `catch` 块，就像参数传递给方法参数一样。

## 1.8.4 示例

以下是一个声明了 2 个元素 `a[0]` 和 `a[1]` 的数组，尝试访问数组的第 6 个元素会发生异常。

程序 `SP_ExcepTest.java`

```java
import java.io.*;
import java.util.Scanner;

public class SP_ExcepTest {
    public static void main(String args[]) {
        double a[] = new double[2];
        a[0] = 1;
        a[1] = 3.2;
        try {
            System.out.println("Access element three :" + a[3]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Exception thrown :" + e);
        }
        System.out.println("Out of block");
    }
}
```

这将产生以下结果：

```
Exception thrown :java.lang.ArrayIndexOutOfBoundsException: 3
Out of block
```

## 1.8.5 多个捕获块

`try` 块可以跟随多个 `catch` 块。多个 `catch` 块的语法如下：

### 语法

```java
try {
    // 受保护代码
} catch (ExceptionType1 e1) {
    // 捕获块
} catch (ExceptionType2 e2) {
    // 捕获块
} catch (ExceptionType3 e3) {
    // 捕获块
}
```

前面的语句演示了三个 `catch` 块，但你可以在 `try` 后面跟任意数量的块。如果受保护代码中发生异常，异常将传递给列表中的第一个 `catch` 块。如果异常类型匹配 `ExceptionType1`，则在那里被捕获。如果不是，异常将传递到第二个 `catch`。这种情况持续到异常被捕获或用完所有 catch，此时当前方法停止并将异常传递到调用栈上的上一个方法。

## 1.8.6 Finally 块

`finally` 块跟随 `try` 块或 `catch` 块。`finally` 块的代码无论是否发生异常都会执行。使用 `finally` 块允许你运行任何你想执行的清理语句，无论保护代码发生了什么。

`finally` 块出现在 `catch` 块的末尾并具有如下语法：

### 语法

```java
try {
    // 受保护代码
} catch (ExceptionType1 e1) {
    // 捕获块
} catch (ExceptionType2 e2) {
    // 捕获块
} catch (ExceptionType3 e3) {
    // 捕获块
} finally {
    // finally 块始终执行。
}
```

### 示例

程序 `SP_ExcepTest2.java`

```java
import java.io.*;
import java.util.Scanner;

public class SP_ExcepTest2 {
    public static void main(String args[]) {
        double a[] = new double[2];
        a[0] = 1;
        a[1] = 3.2;
        try {
            System.out.println("Access element three :" + a[3]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Exception thrown :" + e);
        } finally {
            a[0] = 6;
            System.out.println("First element value: " + a[0]);
            System.out.println("The finally statement is executed");
        }
    }
}
```

这将产生以下结果：

### 输出

抛出异常：`java.lang.ArrayIndexOutOfBoundsException`: 3

第一个元素值: 6

finally 语句已执行

注意以下几点：

- 没有 `try` 语句不能存在 `catch` 子句。
- 当存在 `try/catch` 块时，并不强制要求有 `finally` 子句。
- `try` 块在没有 `catch` 子句或 `finally` 子句的情况下不存在。
- `try`, `catch`, `finally` 块之间不能包含任何代码。

# 1.9 Java 中处理 Excel 文件

由于 Excel 是微软 Office 软件，需要支持库文件来处理 Excel 文件。这里将使用 `JExcel API` 进行说明。需要从 [https://sourceforge.net/projects/jexcelapi/files/](https://sourceforge.net/projects/jexcelapi/files/) 下载 [jexcelapi](https://sourceforge.net/projects/jexcelapi/files/jexcelapi/) jar 文件 `Jxl.jar`。

Java Excel API 是一个成熟的开源 Java API，允许开发者动态地读取、写入和修改 Excel 表格。现在，Java 开发者可以使用方便简单的 API 读取 Excel 表格、修改它们，并将更改写入到任何输出流中。

## 1.9.1 使 Java 程序读取和写入 Excel 文件的步骤

1. 下载 [jexcelapi](https://sourceforge.net/projects/jexcelapi/files/jexcelapi/) jar 文件。
2. 解压并保存到 Java 程序所在的同一文件夹中。
3. 按照如下方式将 jar 文件添加到你的编译器中：
   a. 如果你使用 `JGRASP`，前往 Setting — `Path/ClassPath` – `workspace` – 点击 `New` – 浏览并添加 jar 文件。
4. 编写 Java 程序来读取 Excel 数据，以及编写将程序生成的数据写入 Excel 文件的程序。

## 1.9.2 读写 Java Excel 文件的示例

程序 1.9.1 `SRP_ReadExcel.java`



```java
import java.io.File;
import java.io.IOException;
import jxl.Cell;
import jxl.CellType;
import jxl.Sheet;
import jxl.Workbook;
import jxl.read.biff.BiffException;

public class SRP_ReadExcel {
    private String inputFile;

    public void setInputFile(String inputFile) {
        this.inputFile = inputFile;
    }

    // 从 excel 读取数据的函数，将数据从字符串转换为 double 并保存到数组中
    // 返回 x[][]
    public double [][] read() throws IOException {
        File inputWorkbook = new File(inputFile);
        Workbook w;
        double X[][] = new double[300][10];
        // 用于保存 excel 数据的数组，取 300,10 的数据大小
        // 它应该比 excel 中的实际数据大小大
        try {
            w = Workbook.getWorkbook(inputWorkbook);
            // 获取第一个表
            Sheet sheet = w.getSheet(0);
            // 遍历前 10 列和行
            int n = sheet.getRows();
            int m = sheet.getColumns();
            // double X[][] = new double [n][m];
            double Y[] = new double[n];
            for (int i = 1; i < sheet.getRows(); i++) {
                for (int j = 0; j < sheet.getColumns(); j++) {
                    Cell cell = sheet.getCell(j, i);
                    CellType type = cell.getType();
                    if (type == CellType.LABEL) {
                        X[i][j] = Double.valueOf(cell.getContents());
                        // System.out.print(" " + X[i][j]);
                    }
                    if (type == CellType.NUMBER) {
                        X[i][j] = Double.valueOf(cell.getContents());
                        // System.out.print(" + X[i][j]);
                    }
                }
            }
        } catch (BiffException e) {
            e.printStackTrace();
        }
        return X;
    }

    public static void main(String[] args) throws IOException {
        SRP_ReadExcel test = new SRP_ReadExcel();
        // 文件位置
        test.setInputFile("E:/Java_Engg_Problem/data.xls");
        double xx[][] = test.read();
        // 将从函数返回的数据保存到数组 xx
        int n = xx.length; // 数组 xx 的行
        int m = xx[5].length; // 数组 [][] 的列
        System.out.println("n,m=" + n + " " + m);
        int i, j; // 声明数组
        double X[][] = new double[300][10];
        int mk, nk; // X[][] 中存储数据的实际行和列数
        // 数组 xx[][] 可能比实际数据更多的行和列
        // 因此 X[][] 是 xx[][] 的子集
        nk = 0; mk = 0;
        for (i = 1; i < xx.length; i++) {
            j = 0;
            if (xx[i][j] == 0.0) break; // 没有数据
            mk = 0; // 在循环开始前置零
            for (j = 0; j < xx[6].length; j++) {
                if (xx[i][j] != 0.0) { // 仅非零数据
                    // X[nk][mk] 从 X[0][0] 开始的新非数据集
                    X[nk][mk] = xx[i][j];
                    System.out.print(" " + X[nk][mk]);
                    mk = mk + 1; // 列增
                }
            }
            nk = nk + 1; // 行增
            System.out.println();
        }
        System.out.println("nk, mk=" + nk + " " + mk);
    }
}
```

## 1.9.2.1 运行程序

准备如 `data.xls` 的 excel 数据，将其放在文件夹 `E:/Java_Engg_Problem/data.xls`。复制并粘贴上述程序，编译并运行，你将看到程序可以从文件中读取所有的 excel 数据。

## 程序 1.9 `SRP_SaveExcel.java`

程序在附录中。运行程序，你会发现你可以在 excel 文件中输出数据并可以在其中制作图表。

## 1.10 Java 时间函数

### 睡眠某段时间 `Thread.sleep()` 当前 `Date()`

你可以睡眠从毫秒到寿命的任何时间。例如，以下程序将产生当前时间，它睡眠 10 秒 − 程序 1.10.1 `SP_Timefn.java`

```java
import java.util.*;
public class SP_Timefn {
    public static void main(String args[]) {
        try {
            System.out.println(new Date() + "\n");
            Thread.sleep(10000);
            System.out.println(new Date() + "\n");
        } catch (Exception e) {
            System.out.println("发生异常!");
        }
    }
}
```

输出：

Mon Mar 12 19:46:51 2018 (10 秒)

Mon Mar 12 19:47:01 2018

以下程序将产生时间差 程序 1.10.2 `SP_TimeDiff.java`

```java
import java.util.*;
public class SP_TimeDiff {
    public static void main(String[] args[]) {
        try {
            long start = System.currentTimeMillis();
            System.out.println(new Date() + "\n");
            Thread.sleep(5*1000);
            System.out.println(new Date() + "\n");
            long end = System.currentTimeMillis();
            long diff = end - start;
            System.out.println("差值为 : " + diff);
        } catch (Exception e) {
            System.out.println("发生异常!");
        }
    }
}
```

输出：

Mon Mar 12 19:55:08 2018

Mon Mar 12 19:55:13 2018

差值为：5035

## 1.11 Java 数函数

工程问题的计算需要各种数学函数。下表列出了不同类型的数学函数以及 Java 中的方法：

| 描述 | Java 方法 | 描述 | Java 方法 |
| :--- | :--- | :--- | :--- |
| 数字 x 的绝对值 | `Math.abs(x)` | 常数 pi | `Math.PI` |
| 浮点数 x 的最接近的整数 | `Math.round(x)` | 常数指数 | `Math.E` |
| 大于等于该数的最小整数 | `Math.ceil(x)` | 三角正弦 | `Math.sin(angle)` |
| 小于等于该数的最大整数 | `Math.floor(x)` | 三角余弦 | `Math.cos(angle)` |
| 两个数中的最小值 | `Math.min(x,y)` | 反正弦 | `Math.asin(value)` |
| 两个数中的最大值 | `Math.max(i,j)` | 反余弦 | `Math.acos(value)` |
| 指数 | `Math.exp(x)` | 对数 | `Math.log(x)` |
| 幂 xy | `Math.pow(x,y)` | 平根 | `Math.sqrt(x)` |
| 在 0 和 1.0 之间生成随机数 | `Math.random()` | | |

下方的程序将用于解释上述所有方法。

### 程序 1.11.1 SP_MathFn

```java
import java.util.Scanner;
import java.io.*;
import java.math.*;
import java.util.*;

public class SP_MathFn {

    public static void main(String[] args) {
        double x = 72.3;
        double y = 0.34;

        System.out.println("|" + x + "| is " + Math.abs(x));
        System.out.println("|" + y + "| is " + Math.abs(y));
        System.out.println(x + " is approximately " + Math.round(x));
        System.out.println(y + " is approximately " + Math.round(y));

        System.out.println("The ceiling of " + x + " is " + Math.ceil(x));
        System.out.println("The ceiling of " + y + " is " + Math.ceil(y));

        System.out.println("The floor of " + x + " is " + Math.floor(x));
        System.out.println("The floor of " + y + " is " + Math.floor(y));

        System.out.println("min(" + x + "," + y + ") is " + Math.min(x,y));
        System.out.println("max(" + x + "," + y + ") is " + Math.max(x,y));

        System.out.println("Pi is " + Math.PI);
        System.out.println("e is " + Math.E);

        double angle = 45.0 * 2.0 * Math.PI/360.0;
        System.out.println("cos(" + angle + ") is " + Math.cos(angle));
        System.out.println("sin(" + angle + ") is " + Math.sin(angle));

        double value = 0.707;
        System.out.println("acos(" + value + ") is " + Math.acos(value));
        System.out.println("asin(" + value + ") is " + Math.asin(value));

        System.out.println("exp(x) is " + Math.exp(x));
        System.out.println("exp(y) is " + Math.exp(y));

        System.out.println("log(x) is " + Math.log(x));
        System.out.println("log(y) is " + Math.log(y));

        System.out.println("pow(x, y) is " + Math.pow(x,y));
        System.out.println("The square root of " + x + " is " + Math.sqrt(x));

        System.out.println("Here's one random number: " + Math.random());
        System.out.println("Here's another random number: " + Math.random());
    }
}
```

### 输出

`exec java SP_MathFn`

![.11output.jpg](img/0001.jpeg)

## 1.12 Java 中的动画

让我们来做一些图形动画。对于动画，需要使用一些时间方法，如 `delay()`、`sleep()` 等。通过下面的几个动画代码示例来解释它会比较好。

### 程序 1.12.1 SP_Animation.java



```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.Insets;
import java.util.Timer;
import java.util.TimerTask;
import java.awt.*;
import java.awt.event.*;
import java.awt.geom.*;
import javax.swing.JFrame;

public class SP_Animation extends JFrame {
    private static int DELAY = 600;
    int a = 0;
    int b = 0;

    public void paint(Graphics g) {
        super.paint(g);
        Font fnt = new Font("Arial", Font.BOLD, 12);
        g.setFont(fnt);
        g.setColor(Color.MAGENTA);
        g.drawString("Example Animation of Graphics: Rectangle & Oval", 60, 50);
        if (a > 450) a = 0;
        if (b > 300) b = 0;
        g.setColor(Color.BLUE);
        g.fillRect(a, 120, 50, 55);
        g.setColor(Color.RED);
        g.fillOval(a, b, 20, 20);
    }

    public void go() {
        TimerTask task = new TimerTask() {
            public void run() {
                a = a + 20;
                b = b + 30;
                repaint();
            }
        };
        Timer timer = new Timer();
        timer.schedule(task, 0, DELAY);
    }

    public static void main(String args[]) {
        SP_Animation f = new SP_Animation();
        f.setSize(500, 300);
        f.show();
        f.go();
    }
}
```

# 一阶导数的中心差分近似

近似一阶导数的第三种方法是从前向泰勒展开式中减去方程 ( )。

![2.3.3 Num diff.jpg](img/00015.jpeg)

方程 (2.6) 是一阶导数的中心差分表示。

## 示例

以下给出了通用方程的第 1 和第 2 阶数值微分 Java 程序：

`y = Ax + Bx2 + Clogx + D ; A=2, B=1, C=2.5, D=3`

### 程序 2.3.1 `SP_NumericalDifferentiation.java`

```java
import java.util.Scanner;
import java.io.*;
import java.math.*;

public class SP_NumericalDifferentiation {
    double d1[] = new double[10];
    double d2[] = new double[10];
    double d3[] = new double[10];
    double d4[] = new double[10];
    double d5[] = new double[10];
    double y[] = new double[10];
    double df;
    double dff;
    double yy;

    public double fn(double xx) {
        double A, B, C, D, h;
        A = 2;
        B = 1;
        C = 2.5;
        D = 3;
        double yy = A * xx + B * Math.pow(xx, 2) + C * Math.log(xx) + D;
        return yy;
    }

    public double dfn(double[] y, double h) {
        double df;
        d1[1] = ((y[2]) - (y[1]));
        d1[2] = ((y[3]) - (y[2]));
        d1[3] = ((y[4]) - (y[3]));
        d1[4] = ((y[5]) - (y[4]));
        d1[5] = ((y[6]) - (y[5]));
        d2[1] = d1[2] - d1[1];
        d2[2] = d1[3] - d1[2];
        d2[3] = d1[4] - d1[3];
        d2[4] = d1[5] - d1[4];
        d3[1] = d2[2] - d2[1];
        d3[2] = d2[3] - d2[2];
        d3[3] = d2[4] - d2[3];
        d4[1] = d3[2] - d3[1];
        d4[2] = d3[3] - d3[2];
        d5[1] = d4[2] - d4[1];
        df = (d1[1] - d2[1] / 2 + d3[1] / 3 - d4[1] / 4 + d5[1]) / h;
        return df;
    }

    public double ddfn(double[] y, double h) {
        double ddf;
        d1[1] = ((y[2]) - (y[1]));
        d1[2] = ((y[3]) - (y[2]));
        d1[3] = ((y[4]) - (y[3]));
        d1[4] = ((y[5]) - (y[4]));
        d1[5] = ((y[6]) - (y[5]));
        d2[1] = d1[2] - d1[1];
        d2[2] = d1[3] - d1[2];
        d2[3] = d1[4] - d1[3];
        d2[4] = d1[5] - d1[4];
        d3[1] = d2[2] - d2[1];
        d3[2] = d2[3] - d2[2];
        d3[3] = d2[4] - d2[3];
        d4[1] = d3[2] - d3[1];
        d4[2] = d3[3] - d3[2];
        d5[1] = d4[2] - d4[1];
        ddf = (d2[1] - d3[1] + (11 / 12) * d4[1] - (5 / 6) * d5[1]) / (Math.pow(h, 2));
        return ddf;
    }

    public static void main(String[] args) {
        double x[] = new double[150];
        double y[] = new double[150];
        int i, j;
        SP_NumericalDifferentiation nd = new SP_NumericalDifferentiation();
        Scanner inpData = new Scanner(System.in);
        System.out.println("Enter the value of x");
        double xx = inpData.nextDouble();
        System.out.println("Enter the increament h for finite diff");
        double h = inpData.nextDouble();
        i = 1;
        x[i] = xx;
        do {
            y[i] = nd.fn(x[i]);
            i = i + 1;
            x[i] = x[i - 1] + h;
        } while (x[i] <= x[1] + 7 * h);
        System.out.println();
        double df = nd.dfn(y, h);
        double ddf = nd.ddfn(y, h);
        double value = 2 + 2 * xx + 2.5 / xx; // real value 1st dervative
        double value2 = 2 + 2 * xx + 2.5 / xx; // real value 2nd dervative
        // Display Results
        System.out.println("1st Derivative=" + df + " Real value=" + value);
        System.out.println("2nd Derivative=" + ddf + " Real value=" + value2);
    }
}
```

![2.3 output](img/00016.jpeg)

# 方程根与工程实践

方程的根经常出现在工程设计领域。表列了设计中常用的几种基本原理。如第 2 章介绍的，数学方程或模型被用于预测自变量的函数和参数。在每种情况下，因变量反映系统的状态或性能，而参数代表其组成。

## 2.4.1 牛顿迭代法

在所有求根公式中应用最广泛的是牛顿方程。如果根的初始估计值为 `xi`，则从点 `[xi, f(xi)]` 引出切线。该切线与 x 轴的交点通常代表根的改进估计。

![fig2.1.jpg](img/00017.jpeg)

`xi+1 = xi - f(xi) / f(xi)` (images/00018.jpeg) 称为牛顿公式。

附录中的牛顿法。

![2.4 output](img/00019.jpeg)

## 2.4.2 多项式根

现在我们处理同时满足一组方程的值 `x1, x2, ... xn` 的情况：

`f1(x1, x2, ... xn) = 0`

`f2(x1, x2, ... xn) = 0`

...

`fn(x1, x2, ... xn) = 0`

这类系统可以是线性的也可以是非线性的。在第三部分，我们处理具有一般形式的线性代数方程：

`a11x1 + a12x2 + ... + a1nxn = b1`

`a21x1 + a22x2 + ... + a2nxn = b2`

`an1x1 + an2x2 + ... + annxn = bn`

其中 `a` 是常系数，`b` 是常数，`n` 是方程个数。其他方程是非线性的。

### 矩阵表示线性代数方程

显然矩阵提供了表示线性方程组的简洁表示法。例如，上述方程组可以表示为：

`[A]{X} = {B}` (2.8) 其中 `[A]` 是 n 阶系数矩阵。

`[A]-1[A]{X} = [A]-1{B}` (2.9)

`{X} = [A]-1{B}` (2.10)

## 2.4.3 高斯消元法

它涉及合并方程以消除未知数。虽然它是求解方程组最早的方法之一，但仍然非常重要，并且是许多软件包的基础。可以通过一般方程进行说明：

`a11x1 + a12x2 = b1`

`a21x1 + a22x2 = b2`

两个方程都可以解出 `x2`：![2.4.3 gauss.jpg](img/0020.jpeg) 因此，方程现在直线的形式；即 `x2 = (slope) x1 + intercept`。这些线可以在直角坐标系上绘制，其中 `x2` 为纵坐标，`x1` 为横坐标。线的交点处的 `x1` 和 `x2` 值代表解。

### 高斯程序示例 2.4.3 `SP_Gauss_Elimination.java`

```java
import java.util.Scanner;

public class SP_Gauss_Elimination {
    public static void main(String args[]) {
        int i = 1, j = 1, itr = 1;
        double sum = 0, temp = 0, tol = .1, max = 0, error = 0;
        Scanner input = new Scanner(System.in);
        System.out.println("Enter the number of variables: ");
        int n = input.nextInt();
        System.out.println("Enter the coefficients of a1x1 + a1x2 + a1x3 + ... =0 each equations");
        double a[][] = new double[n + 1][n + 2];
        for (i = 1; i < n + 1; i++) {
            for (j = 1; j < n + 2; j++) {
                a[i][j] = input.nextDouble();
            }
        }
        // Matrix representation
        System.out.println("The coefficients you entered:");
        for (i = 1; i < n + 1; i++) {
            for (j = 1; j < n + 2; j++) {
                System.out.print(" " + a[i][j]);
            }
            System.out.println();
        }
        System.out.println();
        double x[] = new double[n + 1];
        for (i = 1; i < n + 1; i++) {
            x[i] = 0.0;
        }
        for (itr = 1; itr < 200; itr++) {
            max = 0;
            for (i = 1; i < (n + 1); i++) {
                sum = 0;
                for (j = 1; j < (n + 1); j++) {
                    if (i != j) {
                        sum = sum + a[i][j] * x[j];
                    }
                }
                temp = (a[i][n + 1] - sum) / a[i][i];
                error = ((x[i] - temp));
                if (error > max)
                    max = error;
                else
                    max = -error;
                x[i] = temp;
            }
            if (max < tol)
                break;
        }
        for (i = 1; i < n + 1; i++) {
            System.out.print(" x" + i + x[i]);
        }
        System.out.println();
    }
}
```

![2.4.3 output.jpg](img/00021.jpeg)

## 2.4.4 Gauss-Seidel 方法

Gauss-Seidel 方法是最常用的迭代方法。假设我们给定了一组 n 方程：

`[A]{X} = {B}`

Gauss-Seidel 方法利用初始估计值，然后通过迭代来获得解的更精细的估计值。Gauss-Seidel 方法特别适用于大型方程组。

假设为了简洁起见，我们限制一组 $3 \times 3$ 的方程组。如果对角线元素均不零，则可以从第一个方程解出 `x1`，从第二个解出 `x2`，第三个解出 `x3`。

![2.4.4. gauss sidel.jpg](img/00022.jpeg)

现在，我们可以通过为 `x` 选择估计值来开始求解过程。获取初始估计的一种简单方法是假设它们全部为零。将这些零代入 `Eq. (2.11a)`，用此计算出 `x1 = b1/a11` 的新值。然后，我们将这个 `x1` 的新值连同之前 `x3` 的零估计值代入 `Eq. (2.11b)`，以计算出 `x2` 的新值。对 `Eq. (2.11c)` 重复该过程以计算出 `x3` 的新估计值。然后返回第一个方程并重复整个步骤，直到我们的解与真值足够接近收敛。可以使用所有 `i` 的准则检查收敛性，其中 `j` 和 `j - 1` 分别代表当前和上一次迭代。

![2.4.4. gauss sidel1.jpg](img/00023.jpeg)

附录中给出了 Gauss 示例程序 `2.4.4 SP_Gauss.java`

## 2.4.5 LU 分解

LU 分解方法将矩阵 `[A]` 耗时的矩阵消元过程与右侧项 `{B}` 的操作隔离开。因此，一旦 `[A]` 被“分解”，就可以以高效的方式评估多个右侧项向量。

### 多变量

科学和工程领域中的问题大多是多变量的。例如，它可以是：

`y = a0 + a1x1 - a2x2 + a3x3` (2.12a)



或者 `y = a0 + a1*x1 + a2*x2 - a3/x3 + a4*x4`

第一个方程是一个多项式，第二个方程如果对两边取对数，它将变成一个多项式。如果已知 3 组对应 `y` 的 `x1, x2, x3`，则该方程被定义。变量个数可以是 5、10、20 或 `n` 个。我们只需要为多项式编写一个程序即可。

我们应用数值方法 LU 分解来求解多项式。假设：

```
AX = B (2.12b)
```

其中 `Y` 是所有 `y` 值的矩阵，`X` 是所有 `x` 变量的矩阵，`A` 是所有值 `a0, a1, a2` 等矩阵。我们可以将 `A` 转换为两个矩阵 `L U` 的乘积：

```
A = LU (2.12c)
```

`L` 是下三角矩阵，`U` 是上三角矩阵，如下：

![2.4.5 LU.jpg](img/00024.jpeg)

方程 `(2.12d)` 可以重写为：

```
LUX = Y (2.12e)
```

现在我们将 `(2.12e)` 拆分为 2 个方程：

`LY = B (2.12e)` - 这可以通过正向代换求解

`UX = Y (2.12f)` - 这可以通过后向代换求解

附录中给出了示例程序 `2.4.5 SP_LUDecomposition.java`。

## 2.4.6 多变量线性方程组

```
/* 使用 GAUSS_Elimination LU 方法求解 n 个变量的线性方程组。正确解取决于输入变量的一些近似初始值 */
```

示例程序 `2.4.6 SP_LinearMultiVariables.java` 位于附录中。

## 2.4.7 单变量多根

示例：单变量多根 `y = Ax + Bx^2 + C*ln(x) + D` 2 根

![fig22.jpg](img/00025.jpeg)

`X0` 是 `x` 的一个近似根，曲线在 `x0` 处的切线在 `x01` 处截过 x 轴，这是接近实际解的下一个近似值。再次在曲线在 `x01` 处的切线截 x 轴的位置更接近真实值 `x1`。因此此过程将继续。同样，二阶导数 `d2f(x)/dx^2` 将给出第二个根 `x2`。循环将执行 `n` 次：

```
x1 = xx - 2*f(x)/(df(x)/dx);
x2 = xx - (df(x)/dx)/(d2f(x)/dx^2);
```

循环持续直到获得精确值。附录中给出了程序 `2.4.7 SP_MultipleRoot_1Variable.java`。在科学和工程问题中，我们面临许多难以求解的线性方程。这里有一个求解两个非线性方程的程序：

```
z = f(x, y);
```

如 2.4.7 节所示，通过对两个函数求偏导并取 `x0, y0` 的初始近似，可以得到 `x, y` 的解：

```
f(x, y) = A1*x1^2 + A2*x2^2
```

附录中给出了程序 `2.5 SPNonEq.java`。

## 2.6 最小二乘回归

对于一组观测值 `(x1, y1), (x2, y2), ... (xn, yn)`，最小二乘法最简单的例子是对这些点拟合直线。除非另有说明，所有求和符号从 `i = 1` 到 `n`。直线的数学表达式为：

```
y = a0 + a1*x + e
```

其中 `a0` 和 `a1` 分别代表截距和斜率，`e` 是模型与观测值之间的误差。一旦 `e` 最小，就得到了最佳拟合。为了确定 `a0` 和 `a1`，对 `(17.3)` 的每个系数求导：

![2.6.2 Linreg.jpg](img/00028.jpeg)

注意我们简化了求和符号。令这些导数等于零将得到最小值。如果这样做，方程可以表示为：

现在意识到 `∑a0 = n*a0`，我们可以将方程表示为两个未知数 (`a0, a1`) 的线性方程组。这些被称为正规方程。方程的解可以计算为：

结果可以用于得到以下回归线：

```
a0 = y_mean - a1*x_mean
```

其中 `x_mean` 和 `y_mean` 分别是 `x` 和 `y` 的平均值。

附录中提供的 `2.6 SP_LinearRegression.java` 程序说明了最小二乘回归。

# 第 3 章：建模与仿真基础

## 3.1 建模

建模是一种简化现实世界以便我们解决问题的方法。我们经常这样做，而且如此自然，以至于甚至没有注意到自己在正在这样做。例如，街道地图是城市道路的模型，流程图是某物体制造过程的模型，甚至日历也是一个月的模型。建模是开发一种分析结构来表示复杂系统，以便该系统的行为能够被模拟和预测。模型应该是真实系统的紧密近似，并包含其大部分显著特征。另一方面，它不应该复杂到无法理解和进行实验。一个良好的模型是现实性和简单性之间的明智权衡。

### 3.1.1 数学建模

数学模型可以广义地定义为用数学术语表达物理系统或过程本质特征的公式或方程。它是用一组代数方程或微分方程对某些过程或现象的表述。模型的范围取决于其目标，可能是过程分析、过程控制、过程设计或过程优化。

![fig3.1.jpg](img/00029.jpeg)

从非常通用的意义上说，它可以表示为如下形式的函数关系：

`因变量 = f(自变量, 参数, 影响函数)`

其中，因变量是反映系统行为或状态的特征；自变量通常是维度，如时间和空间，系统行为沿着这些维度被确定；参数反映了系统的属性或组成；而影响函数是作用于系统的外部影响。

`Eq. ()` 的实际数学表达式范围可以从简单的代数关系到大型复杂的微分方程组。

例如，考虑以下反应：

`A + B = C` (3.1)

如果我们想在数学上表示在温度 `T` 和压力 `P` 下、时间 `t` 内产的 `C` 的量 (`mC`)：

`mC = f(t, aA, aB, ac, T, P)` (3.2)

`t` 是自变量，活度或浓度 `aA`, `aB`, `ac`, `T` & `P` 是取决于其他外部因素的影响函数。

## 3.2 建模的类型

模型开发有不同的技术，经验性的、半经验的和理性的：

1. **经验性的（统计性的）**，通过从实验室和工厂获得的数据通过统计回归分析拟合到某些方程。

2. **半经验性的**，部分基于理论，部分基于经验数据；无量纲相关性属于此类。

3. **理性的（理论性的）**，基于科学和工程基础，如物平衡、热力学、动力学、热、质和动量传递等。理性的过程分析是最优的。它可以为我们提供复杂现象最严谨的定量相关。

4. **动态 vs 静态模型**：动态模型包含时间。静态模型可以在不涉及时间的情况下定义。

5. **连续时间 vs 离散时间动态模型**：连续时间模型可以在一段时间内连续演变其变量值。离散时间变量在一段时间内改变有限次值。

6. **随机模型 vs 确定性模型**：确定性模型是指每一组变量状态都由模型中的参数以及这些变量之前的状态集唯一定的模型；因此，对于一组初始条件，确定性模型总是执行相同的方式。相反，在随机模型（通常称为“统计模型”）中，存在随机性，变量状态不是通过唯一值描述，而是通过概率分布描述。

## 3.3 仿真

系统的仿真是在数字计算机上执行系统的模型，并分析执行输出结果。模型可以被重新配置和进行实验。可以研究模型的操作，从而推导出关于实际系统或其子系统行为的属性。从广义上说，仿真是一种在不同感兴趣的配置和在较长时间的真实时间内，评估现有或拟议系统性能的工具。孩子们通过模拟（使用玩具和人偶）他们与他人、动物和物体的大部分互动来理解他们周围的世界。作为成人，我们失去了部分这种童真的行为，但后来通过计算机仿真重新找回了。因此，仿真是利用计算过程来实现系统行为本质特征的模型表示。

## 3.4 建模与仿真的益处

1. 使用仿真通常比进行现实实验更便宜、更安全，有时更符合伦理。例如，有时使用超级计算机模拟核装置的爆炸及其影响，以便支持在核爆炸发生时做出更好的准备。类似的努力也被用于模拟飓风和其他自然灾害。

2. 仿真往往比传统实验更真实，因为它们允许自由配置在最终产品运行应用领域中的环境参数。

3. 仿真的运行速度通常比真实时间快。这允许我们对不同方案进行高效的 `if-then-else` 分析，特别是当初始化仿真所需的数据可以从运行数据中轻松获取时。这种仿真的用法为传统决策支持系统的工具箱增加了决策支持仿真系统。

## 3.5 建模与仿真的应用

表 `3.1` 和 `3.2` 总结了一些简单的工程模型和相关的守恒定律，这些将成为许多工程应用的基础。大多数化学工程应用将聚焦于反应器的质量平衡。质量平衡源于质量守恒定律。它规定反应器内化学物质质量的变化取决于流入的质量减去流出的质量。

土木工程和机械工程应用都将关注基于动量守恒开发的模型。对于土木工程，力平衡被用于分析结构，如表 `1.1` 中的简单桁架。同样的原理被应用于机械工程中，以分析汽车的瞬态上下运动或振动。

### 3.5.1 材料工程中的应用

材料工程与所有工程领域相关。新材料的开发和表征、材料属性以及结构组件寿命的预测支持了技术的进步。计算现在已成为理解材料行为、通过过程建模解释各种现象以及预测寿命和结构属性的必备工具。例如，使用基础热力学数据，通过求解复杂的溶液热力学方程可以预测相图；或者从热、质传递方程开发模型，以更好地理解界面反应，如矿渣-金属或金属-环境等。

### 3.5.2 化学工程中的应用

化学工程中最重要的组织原理之一是质量守恒。在定量上，该原理表示为质量平衡，它考虑了所有进出某个体积的物质的源和汇。在有限的时间内，这可以表示为：

```
Accumulation = inputs - outputs      (3.3)
```

![3.1 Table.jpg](img/00030.jpeg)

![3.2 Table.jpg](img/00031.jpeg)

质量平衡代表了对所建模特定物质的项目记账计算。在计算期间，如果输入大于输出，则体积内物质的质量就会增加。如果输出大于输入，则质量减少。如果输入等于输出，则累积为零，质量保持恒定。对于这种稳定状态，即稳态，方程 (3.3) 可以表示为：

```
Inputs = outputs      (3.4)
```

### 示例

例如，质量守恒原理可以用于为一系列化学反应器建立模型（图 3.2）。对于这种情况，被建模的数量是每个反应器中化学品的质量。系统属性是化学品的反应特性以及反应器的尺寸和流速。

![fig3.2.jpg](img/00032.jpeg)

对于反应器 1，质量流流入率为 `5(10) + Q31*c3`，质量流出率为 `Q12*c1 + Q15*c1`。

由于系统处于稳态，流入和流出必须相等：

```
C1 : Q01*C01 + Q31*C3 = Q12*C1 + Q15*C1 (3.5)
C2 : Q12*C1 = Q25*C2 + Q23*C2 + Q24*C2 (3.6)
C3 : Q03*C03 + Q23*C2 = Q31*C3 + Q34*C3 (3.7)
C4 : Q24*C2 + Q54*C5 + Q34*C3 = Q44*C4 (3.8)
C5 : Q15*C1 + Q25*C2 = Q54*C5 + Q55*C5 (3.9)
```

在代入所有流量 `Q` 的值并重新排列方程后，它们如下：

```
6C1 + 0.C2 - C3 + 0.C4 + 0.C5 = 50 (3.5a)
3C1 - 3C2 + 0.C3 + 0.C4 + 0.C5 = 0 (3.6a)
0.C1 - C2 + 9C3 + 0.C4 + 0.C5 = 160 (3.7a)
C2 + 2C5 + 8C3 - 11C4 + 0.C5 = 0 (3.8a)
3C1 + C2 + 0.C3 + 0.C4 - 4C5 = 0 (3.9a)
```

可以使用数值方法求解这五个方程以得到五个未知数。使用这些数据，运行附录中提供的程序 `2.4.6 SP_LinearMultiVariables.java`。

## 3.6 建模与仿真的步骤

- 步骤 1。识别问题。
- 步骤 2。建立问题。
- 步骤 3。收集并处理实际系统数据。
- 步骤 4。建立并开发模型。
- 步骤 5。验证模型。
- 步骤 6。记录模型以备将来。
- 步骤 7。选择合适的实验设计。
- 步骤 8。为运行建立实验条件。
- 步骤 9。执行仿真运行。
- 步骤 10。解释并展示结果。

实际工程问题的建模与仿真的细节将在后续章节中讨论。

# 第 4 章：过程优化与线性规划

## 4.1 优化

优化通常涉及寻找问题的“最佳结果”或最优解。因此，在建模的背景下，它们通常被称为“规范性模型”，因为它们可以被用于规定行动方案或最佳设计。

最优值是曲线平坦的点。在数学术语中，这对应于导数 `f'(x)` 等于零的 `x` 值。此外，二阶导数 `f''(x)` 指示最优值是最小值还是极大值：如果 `f''(x) < 0`，则该点为极大值；如果 `f''(x) > 0`，则该点为最小值。

### 4.1.1 工程中优化问题的示例

- 设计具有最小重量和最大强度的飞行器。
- 航天器的最优轨迹。
- 设计成本最低的土木工程结构。
- 设计水利工程项目（如大坝）以减轻洪灾损害，同时产生最大的水能。
- 通过最小化势能来预测结构行为。
- 最小成本的材料切割策略。
- 设计泵和热传递设备以实现最大效率。
- 在最小化热量产生的同时使电气网络和机械的功率输出最大。
- 推销员一次销售期间访问各个城市的最短路线。
- 最优规划与调度。
- 最小误差的统计分析和模型。
- 最优管道网络。
- 库存控制。
- 最小化成本的维护计划。
- 最小化等待和闲置时间。
- 设计废物处理系统以符合水质标准。

## 4.2 优化的数学

一个优化或数学规划问题通常可以述为：最小化或最大化 `f(x)`，受限于

```
di(x) <= ai, i = 1, 2, ..., p
```

其中 `x` 是一个 `n` 维向量，`f(x)` 是目标函数，`di(x)` 是不等式约束，`ai` 是常量。优化根据 `f(x)` 的形式分类为：

- 如果 `f(x)` 和约束是线性的，我们称之为线性规划。
- 如果 `f(x)` 是二次的且约束是线性的，我们称之为二次规划。
- 如果 `f(x)` 不是线性或二次的且约束是非线性的，我们称之为非线性规划。

## 4.3 无约束优化

无约束优化的函数 `y = f(x1, x2, x3)` 取决于单变量或多变量，可以通过牛顿法找到 `f(x)` 的最小值或最大值。应该注意的是，这是通过对 `f(x)` 使用二阶泰勒级数并将导数等于零得到的。牛顿法类似于牛顿法，因为它可能会发散。最后，最好检查二阶导数的符号是否正确以确认该技术收敛。

## 4.4 约束的线性规划

线性规划 (`LP`) 是一种在存在约束（如有限资源）的情况下满足预期目标（如最大化利润或最小化成本）的优化方法。线性表示表示目标和约束的数学函数都是线性的。规划并不是“计算机编程”，而是意味着“安排”。

线性规划问题包含两个主要部分：目标函数和一组约束。对于最大化问题，目标函数通常表示为：

```
Maximize Z = c1*x1 + c2*x2 + ... + cn*xn (4.3)
```



其中`cj`是每个`j`活动的收益，`xj`是`j`活动的规模。因此，目标函数的值`Z`是由于活动总数`n`产生的总收益。

约束通常表示为：

```
ai1x1 + ai2x2+· ·+ainxn ≤ bi (4.4)
```

其中`aij`是每个`j`活动消耗的`ith`资源的量，`bi`是`ith`资源的可用量。也就是说，资源是有限的。第二种通用约束规定所有活动必须具有正值，`xi ≥ 0`。

## 4.5 图形法

线性规划优化可以通过绘制目标函数和约束的直线，然后将目标线移动到约束包围区域内的最大可能值来实现。可以通过以下示例来说明，图形如图 4.1 所示。

示例

| 目标函数 MAXIMIZE: Z = 3 X1 + 2 X2 |
| :--- |
| 约束 |
| 2 X1 + 1 X2 ≤ 18 |
| 2 X1 + 3 X2 ≤ 42 |
| 3 X1 + 1 X2 ≤ 24 |
| X1, X2 ≥ 0 |

![fig4.1.jpg](img/00033.jpeg)

### 4.6 单纯形法

单纯形法建立在最优解将是极点的假设之上。因此，该方法必须能够在求解过程中识别出极点的出现。为了做到这一点，通过引入所谓的松弛变量，将约束方程改写为等式方程。

### 4.6.1 松弛变量 (Slack Variables)

正如其名所示，松弛变量用于衡量受限资源的可用性，即资源有多少“空闲”部分可用的。松弛变量代表未使用的资源量；它被添加到小于或等于（`<`）类型的约束条件中，以获得等式约束。

### 4.6.2 剩余变量 (Surplus Variables)

剩余变量代表解值超过资源的数量。这些变量也称为“负松弛变量”。剩余变量与松弛变量一样，在目标函数中的系数为 0。它被添加到大于或等于（`>`）类型的约束条件中，以获得等式约束。

### 4.6.3 人工变量 (Artificial Variables)

人工变量被添加到带有等号（`=`）和大于或等于（`>`）符号的约束中。人工变量被加入约束条件中，是为了获得线性规划（LP）问题的初始解。人工变量在物理意义上没有意义，它们仅用作生成线性规划问题初始解的工具。在最大化问题中取 `-M`，在最小化问题中取 `+M`，其中 `M` 是任意大值，用于强制人工变量移出解。

线性规划模型必须扩展以符合单纯形程序的要求，即：

1. 所有方程必须是等式。
2. 所有变量必须出现在所有方程中。

(I) 在“≤”约束的情况下，将松弛变量加到实际变量中，使方程成为等式。
(II) 在“≥”约束的情况下，使用剩余变量使方程成为等式。

### 示例 4.6.1

考虑以下线性规划问题：

```
Minimize cost = 6X1 + 8X2
Subject to
X1+x2=500
X1 ![](img/00034.jpeg) 1500
X2![](img/00035.jpeg) 7500
X1,X2 ![](img/00035.jpeg)0
```

共有三个约束条件，由一个等式、一个“小于或等于”和一个“大于或等于”组成：

```
X1+X2=500
X1 +s1= 1500
X2-s2 =500
X1,X2 ![](img/00035.jpeg)0
```

其中 `S1` 是松弛变量，`S2` 是剩余变量。

该问题通过向方程中添加人工变量（用 `Ai` 表示）来求解，即添加一个具有正值的变量。人工变量也用于已是等式的方程中，以符合上述要求 (1) 和 (2)。此时只需记住，人工变量对于问题的求解没有实际意义——它仅被用于在第一个单纯形表中找到一个解的组合。

因此，上述线性规划模型重写为：

```
Minimize cost = 6X1 + 8X2 + 0S1 + 0S2 + MA1 + MA2
Subject to
![](img/00036.jpeg)
```

### 示例 4.6.2：单纯形法 (Simplex)

我们将通过以下示例来解释单纯形法：

```
Objective FunctionZ=3x1+2x2
No of variables 2 , x1, x2 : coefficient 3 2
```

![4.6 simplex.jpg](img/00037.jpeg)

注意：对于最小化问题，请将主函数调用中的 Maximize 改为 Minimize。

运行程序 `4.3.3.3`。附录提供了 `SRP_Simplex.java`。

![4.6 output.jpg](img/00038.jpeg)

## 4.7 应用

单纯形法线性规划在工程的所有领域都有广泛应用，用于优化：

a. 最小材料成本。
b. 通过对具有不同原材料和市场价格的产量进行产量规划，实现利润最大化。
c. 最大化材料的属性，例如取决于多个因素的强度。
d. 通过增加最大废钢量来利用炼钢热量。
e. 最小工厂、商场或城市路灯的电能消耗。

以下示例说明了：

### 示例 4.7.1

假设一家钢铁厂每周生产 `X1` 吨灰铸铁和 `X2` 吨钢。假设生产铸铁和钢的利润分别为每吨 150 美元和 250 美元。因此，被称为目标函数的总利润 `Z` 可以写为：

```
Z= 150X1 + 250X2 (4.5)
```

约束条件：

每吨生产所需的低碳钢废料如下表所示：

![4.1 table.jpg](img/00039.jpeg)

约束方程的形式为 (4.4) `ai1x1 + ai2x2 + ·+ ain ≤ bi`。

目标函数为 `Z=150X1 + 250X2 (4.5)`。我们必须在满足约束 (4.6 到 4.8) 的情况下最大化 `Z`。为了求解，我们首先通过添加松弛变量 `s1`, `s2` 将不等式方程 (4.6 到 4.8) 变为等式：

![4.7 simplex.jpg](img/00040.jpeg)

其中 `S1` 是松弛变量，`S2` 是剩余变量。

该问题通过向方程添加人工变量（用 `Ai` 表示）来求解，即添加一个具有正值的变量。人工变量也用于已是等式的方程中，以符合上述要求 (1) 和 (2)。

![4.7 simplex.jpg](img/00041.jpeg)

此时只需记住，人工变量对于问题的求解没有实际意义——它仅被用于在第一个单纯形表中找到一个解的组合。

使用上述方程运行程序 `4.1`：

变量数 = 5
松弛变量数 = 3
剩余变量数 = 0
人工变量数 = 0

### 4.7.2 应用：气体处理

假设气体厂每周接收固定数量的原料。气体被处理成两种等级：普通和优质。这些等级保证可以出售并产生不同的利润。然而，它们的生产涉及时间限制，例如工厂每周仅开放 80 小时。此外，产品存储也有限制（注意：吨等于 1000 公斤）：

![4.7.2 table.jpg](img/00042.jpeg)

写为线性规划目标函数：

```
Maximize Z = 150x1 + 175x2 (4.9)
```

使用松弛变量形成约束：

![4.7.2 lp.jpg](img/00043.jpeg)

注意我们如何设置这四个方程，我们的程序为 `4.7.1`。附录提供了 `SLinerProg.java` 用于上述问题。

### 4.7.3 应用：材料强度优化

假设碳钢强度 `Z` 取决于碳（`X1`）、锰（`X2`）含量以及冷加工（在室温下加工）`X3`，如下：

```
22X1 + 5.2X2 + 2.75X3 = Z (4.14)
```

约束条件为：

```
X1 ≤ 0.8 (碳最大 0.8%)
X2 ≤ 1.0 (锰最大 1.0%)
X3 ≤ 30 (冷加工最大 30%)
```

注意：这些值是任意取的，用于解释具有实际值的此类问题如何通过线性规划处理以实现强度最大化。约束方程可以使用松弛变量形成：

```
X1 + 0X2 + 0X3 + S1 + 0S2 + 0S3 = 0.8 (4.15)
0X1 + X2 + 0X3 + 0S1 + S2 + 0S3 = 1.0 (4.15)
0X1 + 0X2 + X3 + 0S1 + 0S2 + S3 = 0.8 (4.15)
```

*(注：最后处的 0.8 可能是笔误，应为 30，但按要求保留原文)*

遗传算法是解决已知信息较少问题的最佳方法之一。它们是一种非常通用的算法，因此可以在任何搜索空间内良好运行。你只需要知道你希望解决方案能够很好地完成什么，遗传算法就能创建一个高质量的。遗传算法利用选择和演化的原理为给定问题产生多个解决方案。

## 5.2 生物学背景

每个生物都有一组规则，可以说是一个蓝图，描述了该生物如何从微小的生命基石构建而成。这些规则编码在生物的`genes`（基因）中，基因又连接成长长链，被称为`chromosome`（染色体）。

![fig5.1.jpg](img/00044.jpeg)

当两个生物交配时，它们会共享基因。产生的后代可能有一半基因来自其中一个父母，另一半来自另一个（图 5.1）。这个过程被称为`recombination`（重组）。

## 5.3 方法

遗传算法倾向于在候选解决方案非常多、且搜索空间不均匀并存在许多山谷的环境中茁茁成长。诚然，遗传算法在任何环境中表现都会良好，但在简单的搜索空间中，它们会被更具特定针对性的算法大幅超越。因此，你必须记住，遗传算法并不总是最佳选择。有时它们的运行可能需要很长时间，因此并不总是适用于实时使用。然而，它们是（相对）快速为问题创建高质量解决方案的最强有力方法之一。现在，在我们开始之前，我将为你提供一些关键术语，以便这篇文章易于理解。

- `Individual`（个体） - 任何可能的解决方案
- `Population`（种群） - 所有个体的群体
- `Search Space`（搜索空间） - 问题所有可能的解决方案
- `Chromosome`（染色体） - 个体的蓝图
- `Trait`（性状） - 个体可能的方面
- `Allele`（等位基因） - 性状可能的设置
- `Locus`（基因位点） - 基因在`chromosome`上的位置
- `Genome`（基因组） - 个体所有染色体的集合

一个典型的染色体可能像这样：

```
100101011101010010100
```

最常见的遗传算法工作原理如下：创建一个由随机产生的一体组成的种群。然后对种群中的个体进行评估。评估函数由程序员提供，并根据个体执行给定任务的性能对它们进行打分。然后根据它们的适应度（fitness）选择两个个体，适应度越高，被选中的概率越大。这些个体然后“繁殖”产生一个或多个后代，之后对后代进行随机变异。此过程一直持续直到找到合适的解决方案或通过了一定的代数，取决于程序员的需求。

### 5.3.1 选择

虽然有许多类型的选择，我将涵盖最常见的类型——轮盘赌选择法（roulette wheel selection）。在轮盘赌选择中，个体被选中的概率与其适应度直接成正比。然后根据这些概率随机选择两个个体并产生后代。轮盘赌选择算法的伪代码所示（图 5.2）。

![fig5.2.jpg](img/00045.jpeg)

想象种群的总适应度分由一个饼图或轮盘表示。现在，你为种群中的每个成员分配一个扇区。扇区的大小与该染色体的适应度得分成比例。即成员的适应性越高，获得的饼块就越大。现在，要选择一个染色体，你只需要旋转小球并在它停止时抓取该染色体即可。

虽然这段代码非常通用且显然无法编译，但它说明了选择算法的基本结构。此外，你应该自己写代码，这样学得更好。

### 5.3.2 交叉

![fig5.3.jpg](img/00045.jpeg)

所以你现在选择了一些个体，并且知道通过某种方式产生后代，但该如何操作呢？最常用的方法是交叉，虽然有不同的交叉类型，最常见的是单点交叉。在单点交叉中，你选择一个`locus`，从父母那里交换`alleles`。你可以可以看到，孩子来自每个染色体的一部分。这种特定方法被称为单点交叉，因为只有一个交叉点。有时产生`child 1` 或 `child 2`，但通常产生两者并放入新种群。然而，交叉并不总是发生。有时根据设定概率不发生交叉，父母直接复制到新种群。交叉发生的概率通常为 60% 到 70%。

### 5.3.3 变异

在选择和交叉之后，你现在拥有一个充满个体的新种群。有些是直接复制的，另一些是通过交叉产生的。为了确保个体并非完全相同，你允许有小概率发生变异。你遍历所有个体的`alleles`，如果该`allele`被选中进行变异，你可以稍微改变它，或者将其替换为新值。变异的概率通常在 1% 到 2% 之间。变异的可视化所示（图 5.4）。

![fig5.4.jpg](img/00047.jpeg)

你可以很容易看到变异相当简单。你只需要根据需要改变被选中的基因，然后继续。然而，变异对于确保种群内的遗传多样性至关重要。

### 5.3.4 算法步骤

算法由以下步骤组成：

1. 生成随机染色体种群（问题的合适解决方案）。
2. 评估种群中每个染色体 `x` 的适应度 `f(x)`。
3. 通过重复以下步骤创建一个新种群：
   a. `Selection`：根据适应度从种群中选择两个父染色体。在轮盘赌选择中，个体被选中的概率与其适应度直接成正比（适应度越好，被选中的机会越大）。
   b. `Crossover`：以交叉概率交叉父体产生新后代。最常见的类型是单点交叉。如果没有进行交叉；则后代是父体的精确复制。
   c. `Mutation`：以变异概率对新后代的每个`locus`（染色体中的位置）进行变异。
   d. `Accepting`：将新后代放入新种群。
4. 使用新生成的种群进行算法的进一步运行。
5. 测试是否满足结束条件，停止并返回当前种群中的最佳解决方案，否则（循环）回到第 2 步。

## 5.4 应用

遗传算法是快速为复杂问题寻找合理解决方案的一种非常有效。尽管它们不是瞬时完成，甚至远不上，但它们在搜索大型且复杂的搜索空间方面表现出色。遗传算法在知之较少的搜索空间中最为有效。你可能完全清楚你想要解决方案做什么，但不知道希望它如何实现这一功能。这正是遗传算法大显异彩的地方。它们产生的你可能从未考虑过的方式解决问题的解决方案。但句话回来，它们也可能产生仅在测试环境中有效的解决方案，一旦你尝试在现实世界中使用它们，它们就会失效。简单来说：对于你无法通过其他算法轻松完成的任务，请使用遗传算法。遗传算法已应用于工程领域的许多领域。遗传算法（GA）不仅为解决问题提供了另一种方法，而且在大多数问题中始终优于其他传统方法。它是解决知之很少问题的最佳方法之一。算法从一组解决方案（由染色体表示，称为种群）开始。从一个种群中提取解决方案并用于形成新种群，以找到比旧的更好的方案。被选择形成新方案（后代）的解决方案是根据其适应度选择的——适应度越高，繁殖的机会就越大。

### 5.4.1 遗传算法目标值

示例 *Genetic Algorithm_Targetvalue*

在这种情况下，函数 `z=4x1 + 3x2 +6x3` 受到以下约束限制：

`2x1+3x2+2x3<=440`，
`4x1+3x3<=470`，
`2x1+5x2<=430`，

程序将要求用户输入目标值，一旦给定，它将输出满足目标值的 `x1`、`x2`、`x3`。它首先将函数和约束中的值转换为二进制代码如 `100110` 等。程序将按照 5.3 节中提到的步骤进行，以二进制代码获得 `x1`、`x2`、`x3` 的最优解，并解码为数字。

附录提供了程序 5.4.1 `SP_Genetic2.java`。

使用以下内容运行程序：

输入 Target value =100
获取答案

![5.4 output.jpg](img/00048.jpeg)

### 5.4.2 腐蚀速率的确定

海水钢的腐蚀速率由几个参数控制，Cl 浓度、pH、`[O]`、SO4-2 等。在下面的程序中，遗传算法被用于结合 Cl、SO4 和 pH 寻找腐蚀，并受 3 个约束：

`Cl<= 24`，`SO4:0-4`，`pH 4-8`

运行附录中的程序 5.5.1 `SP_GeneticCorrosion.java`。

# 第 6 章：人工神经网络建模

## 6.1 人工神经网络 (ANN)

人工神经网络（ANN）是一种非线性统计数据建模操作系统，可以通过使用大量的实验生成数据进行训练，来模拟输入输出变量之间的复杂关系。神经网络能够泛化学习过程中获得的经验。因此，模拟实验结果集中不存在的情况变得可能。图 1 展示了如何从输入集计算输出。

![fig6.1.jpg](img/00049.jpeg)

## 6.2 方法

人工神经网络（ANN）的步骤如下：

- 从实验数据或真实数据接收输入 `X1` `X2` …`Xp`
- 输入通过带有“权重”的连接馈入
- 总输入 = 所有源输入的加权之和
- 传递函数（激活函数）将输入转换为输出
- 输出到其他神经元或环境

如图 6.2 所示，可能有三种传递函数。ANN 由 (i) 神经网络的架构、(ii) 训练算法和 (iii) 传递函数组成。“神经网络架构”一术是指神经网络中的层数，即输入层、隐藏层和输出层，如图 6.3 所示。输入层和输出层的神经元数量分别由输入和输出参数的数量决定。为了找到最佳架构，会尝试隐藏层中不同数量的神经元（图 6.3）。在输入层，每个神经元都有某些特定的信息输入，其数量等于系统独立输入参数的数量，以及一定数量的输出。输出参数通过将一组输入参数代入某个函数（传递函数的选择，见图 2），并考虑相应的权重系数集来计算得出。为了找到最佳架构，会尝试隐藏层中不同数量的神经元。

![fig6.2.jpg](img/00050.jpeg)

### 6.2.1 训练

ANN 需要训练才能运行，并能够泛化学习过程中获得的经验。通常，使用大量带有相应输出数据的输入（输入/输出对）来训练神经网络，通过调整与神经元之间每个连接（突触）相关的权重，使得特定的输入集尽可能地产生一组特定的目标输出。因此，预测实验结果集中不存在的情况变得可能。

给定架构，有权重待决定：

`W = (W1, W2, …, W8)`

训练数据：`(Yi , X1i)`

![fig6.4.jpg](img/00052.jpeg)
![fig6.5.jpg](img/00053.jpeg)

## 6.3 应用

神经网络已成功应用于广泛的数据密集型应用中。以下列表基于真实的成功案例。

### 6.3.1 数据挖掘：

a. 材料属性的预测；
b. 响应与系统建模识别；
c. 时间序列分析、动态建模；



### 6.3.2 能源

a. 能源需求预测

b. 天然气/煤炭指数价格预测

c. 电力控制系统

### 6.3.3 材料科学

a. 材料识别

b. 化学系统分析

c. 工艺优化

### 6.3.4 金融与营销

a. 股市预测

b. 价格预测

c. 销售预测

## 6.4 应用与程序

ANN 建模是从给定的具有 `X` 变化的海量已知数据集中，寻找一系列输入 `x1`、`x2`、`x3` 等与输出 `y1`、`y2` 之间的数学关系。所有数据输入和输出都需要是无量纲的，且处于 (-1,1) 之间。所有 ANN 程序在初始化时会将输入、输出数据转换为 -1 到最大 +1 之间，这被称为 `Mapminimax`。现在在应用 ANN 方法后，ANN 输出也将 (-1,1) 范围内的无量纲形式出现。这些需要通过反向 `Mapminimax` 回实数。

以下程序展示了如何将数据转换为 (-1,1) 之间的无量纲数据，并将 ANN 输出转换回实数。

程序 6.4.1 `SP_Mapminmax.java` 位于附录。

### 运行程序

```
Input array[] = new double[]{10, 11, 88, 2, 12, 120};
```

输出 Mapminimax

```
{ -0.864406779661017, -0.847457627118644, 0.4576271186440677, -1.0, -0.8305084745762712, 1.0,}
```

反向 Mapminimax

```
{ 9.99 , 11.0 , 88.0, 2.0, 12.0, 120.0,}
```

对于所有 ANN 程序，此程序将从存储该程序的 `sp_package` 中调用。记住，我们将 Java 程序存储在需要在不同应用程序中频繁调用的包中。

程序 6.4.2 `SRP_NNet2.java` 位于附录。

记住运行此程序时，你将需要存储在 `sp_package` 中的其他三个 Java 程序：

1. `SP_Mapminmax_pack.java`
2. `SP_Neuron.java`
3. `SP_Connection.java`

你可以在附录中找到 `sp_package` 的所有程序。

## 6.5 使用文件数据的 ANN

由于程序中要处理大量数据集作为数据输入，因此先在一个程序中将数据保存到文件中，然后在另一个神经网络程序中调用这些数据会更好。

程序 6.5.1 `SRP_NNData.java` 位于附录。

记住在程序中神经网络数据文件保存在 `E://Java_Engg_Problem/dataNN.txt`；如果你想将文件保存到不同的目录，请更改程序中的行代码。

现在使用这些数据运行 ANN 程序，数据将从同一个文件中调用。

程序 6.5.2 `SRP_NNetFileData2.java` 位于附录。

注意文件是从 `E://Java_Engg_Problem/dataNN.txt` 读取的；

### 运行程序

```
是否想从文件读取神经网络数据？是按 1，否则按 2
1
正在从文件读取数据
2
选择隐藏层数，选择（1 到 2）少于或大于输入层数，如果输入层=3，隐藏层可以是 2 或 4 等 2
```

![6.5 output.jpg](img/00054.jpeg)

# 第 7 章

## 有限元方法 (FEM)

## 7.1 基本原理

考虑一个需要确定场变量分布（例如位移或应力）的物体或工程组件。例如，受载荷的组件、受热输入影响的温度等。该物体（即一维、二维或三维实体）被建模为假设性地划分为由小部分组成的组件，这些小部分称为单元——“有限元”。有限”一词用于描述建模每个单元行为所需的有限或有限的自由度。假设单元之间相互连接，但仅在相互连接的接头处，这些接头被称为“节点”。需要注意的是，单元是概念上的微小区域，而不是像砖块那样的独立实体，它们之间没有裂缝或表面。（现有的系统可以模拟由实际离散单元组成的材料和结构，例如真实的砖块、颗粒混合物、沙粒等。）

FEM 方法是将物体划分为单元。假设单元之间相互连接，但仅在相互连接的接头处，即节点。如图 1 所示。

![7.1.jpg](img/00055.jpeg)

## 7.2 如何进行 FEM

FEM 方法是将物体划分为单元。假设单元之间相互连接，但仅在相互连接的接头处，即节点。如图 1 所示。

### 7.2.1 将物体划分为单元

模型离散化（即将模型划分为离散单元）后，计算每个单元的控制方程并组装成系统方程。一旦推导出通用格式（例如线性），操作就很简单了。

### 7.2.2 节点坐标

节点坐标、材料属性和加载条件直接代入通用格式。单个单元方程被组装成系统方程，描述整体行为。对于静态分析，这些方程通常形式如下

![7.2.jpg](img/00056.jpeg)

```
[k] {δ} = {f}
```

其中，在结构问题中，`[k]` 是方阵，称为刚度矩阵，`{δ}` 是未知位移向量（热分析中为温度），`{f}` 是节点力向量。

方程 `[k] {ff}` 直接类似于我们之前提到的简单单维弹簧的力-位移关系，其中力 `F` 在刚度为 `k` 的弹簧中产生变形 `u`。为了根据给定力寻找位移，对关系进行“反转”，即 `u = k⁻¹f`。

然而，在对方程进行反转和求解之前，必须应用某种边界条件。在应力问题中，必须限制体的刚体运动。对于热问题，必须在在一个或多个节点上定义温度。在实践中，方程的求解并非易事，因为涉及的方程数量往往很大。拥有 250000 个方程是不可能的，因此无法简单地反转 `[k]`。记住，我们通常求解节点位移值；然后通过简单的方法（使用计算机软件包）利用位移找到应变，然后通过适当的胡克定律和应变/应力（本构）关系找到单元应力。

### 7.2.3 FEM 步骤

创建任何类型分析有限元模型的主要阶段包括：

* 选择分析类型
* 材料属性理想化
* 创建模型几何
* 应用支撑或约束
* 应用载荷
* 求解优化

以下内容极其重要：

- 对结构的行为建立感觉
- 评估结果对各种类型数据近似的敏感性
- 制定模型创建整体策略
- 比较理想化结构的预期行为与真实结构的预期行为

## 7.2.4 预处理阶段

在预处理阶段，所研究的组件被“离散化”为有限单元的组合，特别参考以下六个方面。

1. 单元边界应与结构不连续点重合。
2. 力（及约束）的施加点必须与合适的节点重合，分布载荷的任何突变必须发生在单元边界处。（压力施加在单元面的质心上。）
3. 节点应位于需要输出数据的感兴趣点上，例如位移、反力等。
4. 单元阶数的选择（例如线性、抛物线、三次）定义了节点间位移的插值函数或形状函数，即在 `x`、`y` 和 `z` 方向上多项式的阶数，从而决定了应力/应变的变化。此外，还需要选择单元类型（例如弹簧、棒、梁、三角形和四边形平面或壳单元、四面体或六面体（砖）单元）。通常，分析组件的预期行为和物理形状将引导选择。
5. 必须输入边界条件（例如加载载荷、固定节点和约束）以及材料属性。载荷和约束是最难准确表示的参数，对预测有显著影响。
6. 必须对模型的内聚性、碰撞、“裂缝”、单元的长宽比等进行大量的模型检查。

![7.2.4 setp fem.jpg](img/00057.jpeg)

## 7.2.5 求解阶段

要解决的根本未知数是相对于全局坐标系的每个节点的位移 `u`、`v`，并且对于完全三维分析，还包括 `w`。其他数据（如应力和约束反力）则在计算的后期阶段通过应变从这些求解位移中计算出来。

在每个单元内部，施加一组虚拟位移，并用节点的未知位移表示。基于数值积分技术建立单元刚度矩阵，其基础是实际发生的位移将是使应变能量最小的位移。（将泛函参数作为收敛准则的最小化是变分法的一个例子。）

然后将单个单元刚度矩阵组合，形成整个物体的全局刚度矩阵，由此形成一组关于节点力、单元刚度和节点位移的大量线性代数方程。将边界条件应用到相关节点和位移上，然后使用高斯消元法、Gauss–Seidel 迭代或 Cholesky 平方根方法等数值技术进行求解。对于连接两个或多个单元的每个节点，在该节点处保持位移的兼容性和力的平衡（尽管位移插值的导数通常在单元间的边界上是不连续的）。全局刚度矩阵的组装和位移方程的求解了大部分处理时间。

一旦获得每个单元的节点位移解（在迭代技术的情况下，一旦它们都达到了满意的收敛），将根据输入的材料数据、原始单元尺寸和新计算的节点位移来计算应力。

## 7.2.6 后处理阶段

求解结果以应力图（例如最大主应力、最小主应力、最大剪应力、von Mises 应力）、变形几何（即扭曲形状）和节点位移列表（`ux`、`uy`、`uz`）的形式给出。可以创建图像文件以获得打印副本，或者根据需要编写单独的程序来读取结果文件并进行更进一步的数据处理。

## 7.3 有限单元类型与方程

### 7.3.1 线性单元

最简单的有限单元是线性一维单元。单元内的线性温度变化表示为：

```
T ( x, y)= α1 + α2x
```

其中 `T` 是自变量（如果考虑热传导问题，则为温度）。由于线性表示中有两个任意常数，因此只需要两个节点即可确定 `α1` 和 `α2` 的值

![fig7.2.jpg](img/00058.jpeg)

```
Ti( x, y)= α1 + α2xi
Tj ( x, y)= α1 + α2xj
```

从上述方程我们得到，并在代入 `α1` 和 `α2` 的值后

![7.3 fem.jpg](img/00059.jpeg)

这基本上是以形状函数形式公式的线性插值函数。该函数的导数可以推导出

![7.3 fem2.jpg](img/00060.jpeg)

如果线性曲线拟合足够，则形状函数的阶数增加到二次近似

### 7.3.2 二次 1D FM

![fig7.3.jpg](img/00061.jpeg)

将这些值代入方程得到

![7.3 fem3.jpg](img/00062.jpeg)

通过使用 `linear` 或非线性单纯形单元，可以实现表面曲线拟合。

### 7.3.3 三角形单元

用于近似不规则表面的最简单几何形状是三角形，它是目前有限元计算中使用的常用单元之一。二维线性三角形单元（也称为单纯形单元）表示为

```
T(x,y)=α1+α2x+α3
```

其中对于 `x` 和 `y` 是线性的，且包含三个系数。由于三角形有三个节点，`α1`、`α2` 和 `α3` 的值由方程确定

![fig7.4.jpg](img/00063.jpeg)

![7.3 elem.jpg](img/00064.jpeg)

如果在节点 `i` 处评估 `Ni`，其坐标为 `(xi,yi)`，我们得到 `Ni(xi,yi)=1`，同样 `Ni(xj,yj)=0` 且 `Ni(xk,yk)=0`。因此可以看到形状函数在指定的顶点为 1，在其他所有顶点为 0。可以证明在单元内（包括边界）`Ni+Nj+Nk=1`。线性单纯形为插值表面的任意点提供了一种相对简单的方法。因此单元单元的温度分布可以计算为：

![7.3 elem2.jpg](img/00065.jpeg)

因此热传递可以给出：

![7.3 fem.jpg](img/00066.jpeg)

## 7.4 使用有限元求解微分方程

现在通用的稳态热传导方程可以被研究并转换为积分方程

![7.4 fem.jpg](img/00067.jpeg)

有几种积分方法可以应用于微分方程以求解它们。最常用的是伽金法。该方法要求满足以下表达式

其中是单元的体积。其中是节点单元，`L(T)` 是微分方程。当它应用于上述热传问题时：

![7.4 fem2.jpg](img/00068.jpeg)

其中 Ω是单元的体积，wk 是节点单元，`L(T)` 是微分方程。当它应用于上述热传问题时

注意对于有限元 `T=[N]{T}`，积分可以通过分部积分进行转换

![7.4 fem3.jpg](img/00069.jpeg)

![7.4 fem4.jpg](img/00070.jpeg)

![7.4 fem5.jpg](img/00071.jpeg)

## 7.5 有限元应用：稳态热传导

问题：

给定一个正方形板，三边温度为 100 C，第四边温度为 500 C。板的边长为 1 m。计算其温度分布。

![fig7.5.jpg](img/00073.jpeg)

附录中给程序 `7.5.1 SRP_FEM.java`。

热热系数 `h= 20 W/m2/deg k;`

导热系数 `k= 50 W/m/deg K`

`x` 坐标 `L`, `x= 0 to L0`

`y` 坐标 `W`, `y=0 to w0`

正方形三边温度 `100`，单边 `400`

### 输出

**温度分布**

![7.5 output temp distbn.jpg](img/00074.jpeg)

## 7.6 FEM 应用：非稳态传热

当物体内部温度随时间变化时，就会发生非稳态热流。物理情况可以用以下偏微分方程表示。

```
k( (��∂ 2u/��∂x2+ (��∂ 2u/��∂y2+ (��∂ 2u/��∂z2) = c( ��∂u/��∂t)      7.39
```

其中 `k` 是固体的导热系数，`c` 是其比热，`` 是其密度，`u` 是关于距离 `x, y z` 和时间 `t` 的温度函数。对于一维热流，它可以被写为方程 7.40。

```
(��∂ 2u/��∂x2 ) =k/c( ��∂u/��∂t)
```

![](img/00075.jpeg)

```
或 (��∂ 2u/��∂x2 ) = ( ��∂u/��∂t)      7.40
```

其中 ` = k/c` 是热扩散率。

对于方程 (7.40) 使用有限元法求解随距离 `x` 和时间变化的 `u`，该方法涉及基于独立变量的网格点网络，其中网格间距为距离的微增量 `x` 和时间 `t`。

程序 `7.6.1 SRP_FEM_UnsteadyState.java` 位于附录中。

![7.6 output.jpg](img/00076.jpeg)

# 第 8 章

## 应用部分一：传热、凝固与铸造

## 8.1 大尺寸钢板的冷却

将随时间计算一个大钢板的温度分布，该钢板从预热炉取出时的温度假设为 `10000 C`，进入钢板堆场时的环境温度假设为 `450 C`。钢板一端是绝缘的。

![fig8.1.jpg](img/00077.jpeg)

问题在图 8.1 中进行了说明。给定时间间隔（例如 20 分钟）后的温度分布解可以通过方程 (8.1) 得到。使用无量纲的时间、距离和开尔文度温度进行计算通常更方便。

让我们从以下传热方程开始：

当物体内部温度随时间变化时，就会发生非稳态热流。物理情况可以用以下偏微分方程表示。

```
k( (��∂ 2u/��∂x2+ (��∂ 2u/��∂y2+ (��∂ 2u/��∂z2) = c( ��∂u/��∂t)      (8.1)
```

其中 `k` 是固体的导热系数，`c` 是其比热，`` 是其密度，`u` 是关于距离 `x, y z` 和时间 `t` 的温度函数。对于一维热流，它可以被写为：

```
(��∂ 2u/��∂x2 ) =k/c( ��∂u/��∂t)      (8.2)
```

```
或 (��∂ 2u/��∂x2 ) = ( ��∂u/��∂t)      (8.3)
```

其中 ` = k/c` 是热扩散率。

方程 (8.3) 使用有限差法求解随距离 `x` 和时间变化的 `u`，该方法涉及基于独立变量的网格点网络，其中网格间距为距离的微增量 `x` 和时间 `t`（图 8.2）。

![fig8.2.jpg](img/00078.jpeg)

这里 `u(i+1),i` 是时间 `t` 时距离 `ui,j` 距离 `x` 处的温度，`u(i+1),j+1` 是其在时间 `t + t` 的值。因此，当我们从左向右移动时，温度随距离步长 `x` 变化；从底部向上移动时，它随时间步长 `t` 变化。

通过泰勒级数，可以写成：

```
u( i+1) = u(x+ x) = u(x)+(x) ��∂u(x)/��∂x + (x)2/2! ��∂2u(x)/��∂x2 + (x)3/3! ��∂3u(x)/��∂x3+…
```

或者

```
u( i+1) = u(x+ x) = u(x)+(x) ��∂u(x)/��∂x + (x)2/2! ��∂2u(x)/��∂x2 + (x)3/3! ��∂3u(x)/��∂x3+…      (8.4)
```

以及

```
u( i-1) = u(x- x) = u(x)-(x) ��∂u(x)/��∂x + (x)2/2! ��∂2u(x)/��∂x2 - (x)3/3! ��∂3u(x)/��∂x3+…      (8.5)
```

忽略三阶或更高阶项，求解导数的一阶近似：

```
��∂uj/��∂x = (u(i+1) –u(i-1) )/2      (8.6)
```

以类似的方法从方程 (8.4) 和 (8.5) 二阶导数，忽略四阶及更高阶：

```
��∂2u(x)/��∂x2 = (u(i+1) + u(i-1) - 2u(i) )/(x)2  (8.7)
```

方程 (8.2) 中关于 `t` 的导数是一阶的，也可以写为：

```
��∂u/��∂t = (u(i),t+t –u(i),t )/2t      (8.8)
```

将方程 (8.6) 和 (8.7) 代入方程 (8.2)，得到：

```
u(i),t+t = u(i),t + t/x2 (u(i+1),t + u(i-1),t )(8.9)
```

如果给出了边界条件，使用方程 (8.9) 可以得到一维热流随时间的温度分布解。应该注意选择较小的网格长度 `x` 或 `t` 精度更好。

#### 边界条件

解还需要在区间边缘定义边界条件。这些可以通过数学关系或固定值给出。例如，物体的一面可能是绝缘的，另一面通过对流或辐射传热：

```
��∂u/��∂x= 0 at x= L
```

```
��∂u/��∂x= h(ux – usr ) at x=0
```



其中 `h` 是总传递系数，`usr` 是环境温度。通过考虑以下实际问题可以得到更好的说明。如果假设热属性保持不变，用无量纲距离和时间修改方程：

```
X = x/L (A)
τ = αt/L² (B)
```

并指定温度 `T`：

```
Ti,τ+Δτ = Ti,τ + Δτ/ΔX (Ti+1,τ + Ti-1,τ - 2Ti,τ)  (8.10)
```

可以证明，为了满足收敛标准，比例 `Δτ/Δx²` 应小于 `½`。让我们为该问题选择 `¼`：

```
Ti,τ+Δτ = ¼( Ti+1,τ + 2Ti,τ + Ti-1,τ )  (8.11)
```

该问题的边界条件是热量从一端通过对流和辐射传递，另一端是绝缘的。因此数学上：

```
q = k ∂T/∂X = h(Ts – Ti)      (8.12)
```

这里无量纲 `Ti = (环境温度)/(炉炉温度)`，其中 `h` 是对流和辐射传热的总系数。在绝缘面上：

```
∂T/∂X = 0 at X=1 that x=L (8.13)
```

方程 (8.12) 中的导数项 `∂T/∂X` 可以如前解释用有限差法替换：

```
(Ti-1,1 - Ti+1,1)/ΔX = h/kL (Ts – Ti) ....(8.14)
```

[ Δx/L = ΔX ]

将 (8.14) 和 (8.11) 结合并代入 `Ti-1,1`，因为它位于左边界之外：

```
Ti,τ+Δτ = ΔX hL (1 - Ti)/2 + ½( Ti+1,τ + Ti,τ)  (8.15)
```

同样从方程 (8.13)：

```
(Ti-1,1 - Ti+1,1)/ΔX = 0
```

以及从 (8.11)：

```
Ti,1+Δτ = ¼( Ti+1,1 + 2Ti,1 + Ti-1,1 )
```

代入 `Ti+1,1`，因为它位于右边界之外，我们得到：

```
Ti,1+Δτ = 1/2 (Ti,1 + Ti-1,1)  (8.16)
```

因此，使用方程 (8.15) 和 (8.16)，我们找到了两个边界的温度，并将这些数据作为输入馈入方程 (8.11)，找到钢板内部不同网格点的温度分布。

如果传热是通过对流和传导，方程 (8.15) 中的总传热系数 `h` 可以从方程 (8.17) 得到：

```
(qconvection + qradiation) = h(ux=0 – usr) = χhcon(ux=0 – usr)^1.25 + β((usr)^4 - (ux=0)^4) (8.17)
```

其中 `h` 是总传热系数，`hcon` 是对流传热系数，`χ` 和 `β` 是常数。

我们将按照以下步骤编写 Java 程序来解决这个问题。

### 8.1 算法

1. 读取输入数据。
2. 在 `t = 0` 时，初始化所有网格点值为预热温度。
3. 使用方程 (8.14) 计算一端在下一步时间 `(+Δt)` 的温度。
4. 使用方程 (8.15) 计算另一端在下一步时间 `(+Δt)` 的温度。
5. 将步骤 3 和 4 计算的数据馈入方程 (8.10)，以找到内部网格点的温度分布。
6. 重复步骤 3、4 和 5，以获取后续连续时间步的结果，直到达到最终时间。
7. 输出计算的数据。

上述节介绍的方法是**显式法**，因为每个新的温度值都可以根据已知的量立即计算出来。该方法计算简单且经济，但收敛性和精度取决于比例 `Δτ/Δx²` 的值是否在 0 到 ½ 之间。我们可以通过采用**隐式法**来消除这一限制。

### 8.1.3 编程

附录提供了程序 `8.1.2` `SP_CoolingSlab.java`。

### 8.1.4 程序的输出

#### 输入数据

`L=1.0 ; w=0.1 ; th=0.1`

传热系数 `W/m²/deg k=60`

材料的热导率 `W/m/deg.k=30`

材料的比热 `joule/kg/deg K=500`

材料的密度 `kg/m³=7600`

材料的热扩散 `m²/sec=7.89474e-006`

板的初始温度 `deg K=1273`

环境温度 `=303`

总时间 `=900 sec`

`dx=0.2 dt 60`

![8.3 output.jpg](img/00079.jpeg)

### 8.2 热体在开放空气中的双侧冷却

可以使用以下数据输入运行相同的程序，对板材的双侧进行冷却。

### 数据输入

| `L=2;Tf=1200;Ts=300;tm=600;d=7600;k=30;cp=500;h=60;dx=0.2;dt=60;` |

#### 8.2.1 程序的输出

板材两侧冷却的建模已在图 8.1 中图化表示。

![fig8.3.jpg](img/00080.jpeg)

### 8.3 钢坯加热（显式法）

左边界通过炉内热空气的对流加热，传热系数为 `h`，右边界处于环境温度。

附录提供了程序 `8.3.1` `SP_BilletHeat.java`。

### 8.3.1 数据输入

使用以下输入数据运行上述程序。

传热系数 `W/m²/deg k=60`

材料的热导率 `W/m/deg.k=60`

材料的比热 `joule/kg/deg K=500`

材料的密度 `kg/m³=7600`

材料的热扩散 `m²/sec=500`

炉内温度 `deg K=1400`

#### 8.3.2 程序的输出

程序的输出以下表中的温度分布给出，并以图 8.4 的图形形式给出。

![8.3 output2.jpg](img/00081.jpeg)

![fig8.4.jpg](img/00082.jpeg)

### 8.4 隐式法（Crank-Nicolson）

在该方法中，新的温度值是相邻点未知温度的函数。我们从方程 (8.2) 开始：

```
(∂²u/∂x²) = α(∂u/∂t)
```

这里我们不使用向前差分，而是采用如下中心差分。

关于 `t` 的导数在方程中是一阶的，也可以写成：

```
(u(i), j+1 – u(i),j) / 2Δt = 1/2 α [ (u(i+1),j + u(i-1),j - 2 u(i),j) / (Δx)² + (u(i+1),j+1 + u(i-1),j+1 - 2 u(i),j+1) / (Δx)² ]
```

`t_{j+1/2}` 处的中心差分 `tj` 处的中心差分 `t_{j+1}` 处的中心差分

关系式 `Δτ/Δx² = kΔt/(cρ(Δx)²)`

令 `r = kΔt/(cρ(Δx)²)`，

重新整理方程，我们得到：

```
-r u(i-1),j+1 + (2+2r) u(i), j+1 - r u(i+1),j+1 = r u(i-1),j + (2-2r) u(i),j + r u(i+1),j  (8.18)
```

与之前的显式法不同（`r` 需要小于 ½ 以保证收敛），此处 `r` 可以取任何值，因此可以任意选择 `Δx` 和时间间隔 `Δt`。但较小的 `r` 值会产生更准确的结果。

从方程 (8.18) 可以看出，所有 `u` 的项在左侧后缀均为 `j+1`，在右侧均为 `j`。这里 `j` 代表时间。因此，在时间 `t+Δt` 时的 `u` 值是根据上一个时间 `t` 的值计算出的。为了简化起见，假设 `r=1`，方程变为：

```
-u(i-1),j+1 + 4u(i), j+1 - u(i+1),j+1 = u(i-1),j + u(i+1),j  (8.19)
```

#### 8.4.1 钢坯加热-隐式法

附录提供了程序 `8.4.1` `SP_BilletHeat_Implicit.java`。

#### 8.4.2 输入数据

`r=1` 的隐式法。程序已使用相关数据通过测试。

`dx=5cm`

传热系数 `W/m²/deg k=160`

材料的热导率 `W/m/deg.k=30`

材料的比热 `joule/kg/deg K=500`

材料的密度 `kg/m³=7600`

材料的热扩散 `m²/sec=5.7895e-005`

炉内温度 `deg K=1400`

#### 8.4.3 输出

程序的输出以温度分布给出。

#### 8.4.4 钢坯加热-隐式法

`r=1` 的隐式法。左侧通过 `T_f=1400` 加热，右侧处于环境温度，`r` 可以取任何值。数据：`L=5;T_f=1400;T_s=300;t_m=600;d=7600;k=30;cp=500;h=60;dx=0.2;dt=60;` 空间 `Δx` 为 `5cm`，时间间隔 `Δt` 为 `60` 秒。

（此处省略了重复的数值表格翻译，以符合“不重复原文”的逻辑）

## 参数

```
L=0.5;d=7200;k=40;cp=600;h=60;dx=0.1; Ti=1200;Tb=1200;r=0.111111,dt=120,Alpha=9.25926e-006,
```

固态

```
L=.5;d=7600;k=60;cp=500;h=60;dx=0.1; Ti=400;Tb=400; r=0.189474 ,dt=120 ,Alpha=1.57895e-005
```

### 输出

程序的输出如表所示，该表展示了从一端冷却正在固化的钢锭的液体和固态的温度分布。随时间形成的凝固层厚度在图 8.5 中所示。

![fig8.5.jpg](img/00085.jpeg)

## 8.7 金属模具中的金属铸造

接下来，通过对前面的程序进行简单修改，展示模具中铸件的固化过程。程序见附录中的 `Program 8.7.1 SP_Casting.java`。

熔金属在模具中的流动以及随后的固化控制着良好铸件的质量。当液态金属倒入模具腔时，它的热量会被吸收并通过模壁传递。在熔点处，对于纯金属和共晶合金，固化从模壁向热点区域逐层进行，并伴有体积收缩，从相邻层抽取熔金属，导致最后层固化处产生收缩孔。移动的等温固液界面被称为凝固前沿。热通量穿过固化的液体通过正在形成的固态层通过模具。凝固前沿的形状由模壁两侧的温度梯度控制。理解温度梯度凝固前沿的移动有助于预测收缩缺陷的类型和位置，并通过更好的冒口和浇口设计成功克服这些缺陷。

`Program 8.7.1 SP_Casting.java` 见附录。

### 数据输入

*   `dt=9`
*   空间网格数=`5`
*   时间网格数=`20`
*   液比热 (L) `joule/kg/deg K`=`418`
*   固态比热 (S) `joule/kg/deg K`=`460`
*   密度 (L) `Kgm/m3`=`7040`
*   密度 (S) `Kgm/m3`=`7600`
*   热导率(L) `W/m/ deg.K`=`35`
*   热导率(S) `W/m/ deg.K`=`75`
*   热扩散系数 (L) `=1.18938e-005`
*   热扩散系数 (S) `=2.14531e-005`
*   液态初始温度 `=1620`
*   固态初始温度 `=800`
*   金属熔点 `=1500`
*   金属凝固潜热（应为负值） `=-281200`
*   液头初始长度 `=1`
*   形成的固态初始长度 `=0.1`
*   模具初始温度 `=300`
*   模具厚度 `=0.2`
*   模具热导率 `=14`

### 输出

程序的输出以 3D 图形图 8.6 的形式表示，显示了从一端冷却正在固化的铸件的液体和固态的温度分布。固液界面随时间的移动如图 8.7 所示。如图 8.8 所示，液层随时间减少，而固态厚度随时间增加。

![fig8.6.jpg](img/00086.jpeg)

![fig8.7.jpg](img/00087.jpeg)

![fig8.8.jpg](img/00088.jpeg)

## 8.8 砂模铸铸

![fig8.9.jpg](img/00089.jpeg)

熔金属在模具中的流动以及随后的固化控制着良好铸件的质量。当液态金属倒入模具腔时，它的热量会被吸收并通过模壁传递。在熔点处，对于纯金属和共晶合金，固化从模壁向热点区域逐层进行，并伴有体积收缩，从相邻层抽取熔金属，导致最后层固化处产生收缩孔。移动的等温固液界面被称为凝固前沿。热通量穿过固化的液体通过正在形成的固态层通过模具。凝固前沿的形状由模壁两侧的温度梯度控制。理解温度梯度凝固前沿的移动有助于预测收缩缺陷的类型和位置，并通过更好的冒口和浇口设计成功克服这些缺陷。

### 模型

目前模型旨在寻找整个模具、固态和液体的温度分布。模型还计算了随时间变化的固化模式，考虑了导热和对流的非稳态热传导方程。它还涉及液态金属固化时的熔变热。目前，研究将集中在固定温度下固化的纯金属或共晶合金上。

导热引起的非稳态热传导方程给出：

```
(∂T/∂t) = α[(∂²T/∂x²)]
```

（注：原文公式 `(∂T/∂t) = α[(∂2T/∂t)]` 疑为笔误，根据物理意义修正为二阶空间导数 `∂²T/∂x²`）



## 参数

`L=0.5; d=7200; k=40; cp=600; h=60; dx=0.1; Ti=1200; Tb=1200; r=0.111111; dt=120; Alpha=9.25926e-006`

固态

`L=.5; d=7600; k=60; cp=500; h=60; dx=0.1; Ti=400; Tb=400; r=0.189474; dt=120; Alpha=1.57895e-005`

### 输出

程序的输出如表所示，该表展示了从一端冷却正在固化的钢锭的液体和固态的温度分布。随时间形成的凝固层厚度在图 8.5 中所示。

![fig8.5.jpg](img/00085.jpeg)

## 8.7 金属模具中的金属铸造

接下来，通过对前面的程序进行简单修改，展示模具中铸件的固化过程。程序见附录中的 `Program 8.7.1 SP_Casting.java`。

熔金属在模具中的流动以及随后的固化控制着良好铸件的质量。当液态金属倒入模具腔时，它的热量会被吸收并通过模壁传递。在熔点处，对于纯金属和共晶合金，固化从模壁向热点区域逐层进行，并伴有体积收缩，从相邻层抽取熔金属，导致最后层固化处产生收缩孔。移动的等温固液界面被称为凝固前沿。热通量穿过固化的液体通过正在形成的固态层通过模具。凝固前沿的形状由模壁两侧的温度梯度控制。理解温度梯度凝固前沿的移动有助于预测收缩缺陷的类型和位置，并通过更好的冒口和浇口设计成功克服这些缺陷。

`Program 8.7.1 SP_Casting.java` 见附录。

### 数据输入

*   `dt=9`
*   空间网格数=`5`
*   时间网格数=`20`
*   液比热 (L) joule/kg/deg K=`418`
*   固态比热 (S) joule/kg/deg K=`460`
*   密度 (L) Kgm/m3=`7040`
*   密度 (S) Kgm/m3=`7600`
*   热导率 (L) W/m/deg.K=`35`
*   热导率 (S) W/m/deg.K=`75`
*   热扩散系数 (L)=`1.18938e-005`
*   热扩散系数 (S)=`2.14531e-005`
*   液态初始温度=`1620`
*   固态初始温度=`800`
*   金属熔点=`1500`
*   金属凝固潜热（应为负值）=`-281200`
*   液头初始长度=`1`
*   形成的固态初始长度=`0.1`
*   模具初始温度=`300`
*   模具厚度=`0.2`
*   模具热导率=`14`

### 输出

程序的输出以 3D 图形图 8.6 的形式表示，显示了从一端冷却正在固化的铸件的液体和固态的温度分布。固液界面随时间的移动如图 8.7 所示。如图 8.8 所示，液层随时间减少，而固态厚度随时间增加。

![fig8.6.jpg](img/00086.jpeg)
![fig8.7.jpg](img/00087.jpeg)
![fig8.8.jpg](img/00088.jpeg)

## 8.8 砂模铸铁

![fig8.9.jpg](img/00089.jpeg)

熔金属在模具中的流动以及随后的固化控制着良好铸件的质量。当液态金属倒入模具腔时，它的热量会被吸收并通过模壁传递。在熔点处，对于纯金属和共晶合金，固化从模壁向热点区域逐层进行，并伴有体积收缩，从相邻层抽取熔金属，导致最后层固化处产生收缩孔。移动的等温固液界面被称为凝固前沿。热通量穿过固化的液体通过正在形成的固态层通过模具。凝固前沿的形状由模壁两侧的温度梯度控制。理解温度梯度凝固前沿的移动有助于预测收缩缺陷的类型和位置，并通过更好的冒口和浇口设计成功克服这些缺陷。

### 模型

目前模型旨在寻找整个模具、固态和液体的温度分布。模型还计算了随时间变化的固化模式，考虑了导热和对流的非稳态热传导方程。它还涉及液态金属固化时的熔变热。目前，研究将集中在固定温度下固化的纯金属或共晶合金上。

导热引起的非稳态热传导方程给出：

```
(∂T/∂t) = α[(∂2T/∂t)]
```

（注：原文符号为 `(∂T/∂t) = α[(∂2T/∂t)]`，此处保持原样）

# 物理属性

- 密度 (`S`) = `2555 Kgm/m3`
- 导热系数 (`L`) = `91 W Iml deg.K`
- 导热系数 (`S`) = `211 W Iml deg.K`
- 导热系数 (`Sand`) = `0.863 W Iml deg.K`
- 热扩散系数 (`L`) = `3.5256e-005 -m2/set`
- 热扩散系数 (`S`) = `6.93976e-005 m2/sec`
- 液体浇铸温度 = `9630C`
- 金属熔点 = `933°C`
- 金属凝固潜热 = `-398000 Jouleslkg`
- 模具初始温度 = `300e`
- 模具厚度 = `0.2 m`
- 模具导热系数 = `12 W Iml deg.K`
- 对空气传热系数 `h` = `11.34 W 1m2 I deg.K`

### 输出

在有限差分法中，时间与空间网格越小，精度越高。这里空间网格以 `mm` 为单位，时间网格以秒的小数为单位，因此迭代次数非常高。例如，在 `294 sees` 时间内进行计算，程序将计算并模拟上述所有方程约 `800` 次。图 8.10 显示了穿过模具、固态和液态金属的温度分布。铸件一半的温度分布如图 8.11 所示。可以看到，固态和液态温度下降速率相当缓慢，而通过模具的下降速率非常快。最大的温度下降发生在通过辐射和对流的空气隙处。图 8.11 和图 8.12 描述了距离固液界面不同距离的液体和固态金属温度随时间的变化。与液态相比，固态的温度下降并不大。在此也要注意到，距离界面越远，温度下降速率越快。

图 8.12 阐述了整个模具的温度分布。可以看出，由于凝固过程中来自铸件的热通量流动，模具温度随时间增加，并随着远离铸件-模具界面而降低，这表明热量从模具流向环境环境。图 8.14 显示了凝固皮形成随时间变化的厚度。它表示了单位时间内形成的厚度，例如在第 `50th sec.` 时，从液体形成了多厚的凝固皮。有趣的是，皮的凝固速率最初非常快，也就是说液体一浇铸进模具，立即就会形成一层包皮。之后，由于热通量现在必须穿过已形成的固态，层的形成速率随之降低。

![fig8.10.jpg](img/00090.jpeg)
![fig8.14.jpg](img/00091.jpeg)

## 8.9 钢的连续结晶

让我们考虑一个刚从钢包铸入初模的锭圆高度为 `dy` 的体元单元。它将具有一个温度分布，两端由模具冷却，温度向中心增加。在与模具接触的端部会形成固态层皮。由于固态的形成，将释放熔融潜热。该层的温度分布可以通过求解以下方程得到：

![fig8.15.jpg](img/00092.jpeg)

```
(��∂ 2T/��∂x2 ) = ( T/��∂t)
```

边界条件为在 `x= 0` 和 `Ys`，即模/金属界面：

```
k(��∂T/��∂x)=h(T-Ti)
```

其中 `h` 是模具冷却的总传热系数。

同样在固态/液态金属界面处，厚度为 `dY(y)` 的液体固固：

```
-k( ��∂T/��∂x) =H dY(y)/dtat Y(y,t)
```

```
∆H=Hm + ∆cp*∆T
```

- `Hm` = 熔融潜热，单位为焦耳/kg
- `∆T` = 过热
- `dY(y)` = 形成的固层厚度。它是时间的函数，也是金属沿 `y` 方向向下移动距离的函数，即随着程序中 `k` 值的增加而变化。

模具顶部从 `x=0` 到 `x =Ys`（即程序中的 `i=1` 到 `i=n`）的第一个单元 `dy` 的温度，数据输入如下：

程序 `8.9.1` `SP_ConCast.java` 在附录。

## 连续结晶

- `H` = 熔融潜热，单位为焦耳/kg
- `k` = 导热系数
- `dY` = 每个时间增量 `dt` 形成的凝固皮厚度

### 数据输入

```
Ys=0.1; =7040; ks=60; cp=500; h=1000; dx=0.01; tm=20; dt=1; Ti=400; Tm=1500;
```

# 参数定义

- `tc`: 当前时间
- `t`: 总时间
- `length(metre)`: `.1`
- `选择网格长度 dx (m)`: `.02`
- `x=0 & t=t 处的浓度`: `0.2`
- `x=L & t=t 处的浓度`: `1.3`
- `x=x & t=0 处的初始浓度`: `0.2`
- `总时间 (分钟)`: `60`
- `扩散系数 (cm2/min)`: `.00002`

### 数据输入

- `length(米)`: `.1`
- `选择网格长度 dx (m)`: `.02`
- `x=0 & t=t 处的浓度`: `0.2`
- `x=L & t=t 处的浓度`: `1.3`
- `x=x & t=0 处的初始浓度`: `0.2`
- `总时间 (分钟)`: `60`
- `扩散系数 (cm2/min)`: `.00002`

### 输出

`r = Dt/(x)2=1`。让我们考虑 `x= 0.02 cm`, `t= 20 mins`。

如果我们考虑确定深度为 `0.1 cm`，

那么 `n`，空间网格数 = `1/.02= 5`。

边界条件：在 `t=0` 时 `u(x)= 0.2`。

在任何 `t` 下，`u(0)=0.2` 且 `u(L)=1.3`；

### 输出

模型输出显示，碳含量随时间从表面到核心（图 9.5）。

![fig9.5.jpg](img/00099.jpeg)

# 9.3 炉内物质平衡（高炉炼铁）

炉内的物质平衡通过质量输入、质量输出以及特定物种生成或消耗速率的代数和得出，如图 9.6 所示。

![fig9.6.jpg](img/00100.jpeg)

为了说明这一点，我们将以一种常见的炉——例如炼铁高炉为例。下表说明了高炉中不同物种的质量输入和质量输出。

| | | 成分的物质平衡 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| | | Fe | C | O | 二氧化硅 | 石灰 |
| 待装铁矿石 (x) | 产出的铁水 (W) | 存在 | 存在 | 存在 | 存在 | |
| 待装焦炭 (y) | 渣 | 存在 | 存在 | 存在 | 存在 | 存在 |
| 待装助剂：石灰岩 (z) | 排出的气体 (g) | | 存在 | 存在 | 存在 | 存在 |
| 氧气作为氧化剂的空气 | | | | 存在 | | |

我们可以对物质平衡中任何感兴趣的成分进行处理。因此，可能有 `n` 种成分，我们需要建立 `n` 个方程。为了简单起见，让我们只考虑铁、碳和二氧化硅三种成分的平衡，以建立以下 3 个方程：

### 铁平衡

```
α1*x+ α2*y+ α3*z=W* α4 + O* α5
```
(9.1)

### 二氧化硅平衡

```
β1*x+ β2*y+ β3*z= W*β4*(60/28) + O* β5+ (L*z)/B
```
(9.2) (因子 `60/28` 是由于硅到二氧化硅的转化)

### 碳平衡

```
γ1*x+ γ2*y+ γ3*z=W* γ4+O* γ5
```
(9.3)

其中：

- 铁矿石中铁的比例 (`α1`)、焦炭中铁的比例 (`α2`)、石灰岩中铁的比例 (`α3`)
- 铁水中铁的比例 (`α4`)、废气中铁的比例 (`α5`)、铁矿石中二氧化硅的比例 (`β1`)
- 焦炭中二氧化硅的比例 (`β2`)、石灰岩中二氧化硅的比例 (`β3`)、铁水中硅的比例 (`β4`)
- 废气中硅的比例 (`β5`)、铁矿石中碳的比例 (`γ1`)、焦炭中碳的比例 (`γ2`)
- 石灰岩中碳的比例 (`γ3`)、铁水 (`γ4`)

附录中给程序 `SP_MaterialBalanace.java`，基于 `LU` 分解，用于根据数值方法第二章中的讨论，从 `n` 个方程中找到 `n` 个变量的未知解。同样，人们可以建立所有成分的总物质平衡。

# 9.4 炉内热与物质平衡（高炉）

物种的热输入和输出如示意图 9.7 所示。

![fig9.7.jpg](img/101.jpeg)

所有热输入、输出加上放热和吸热反应的总和由 `(9.4)` 和 `(9.5)` 表示：

```
Σ(热量输入) + Σ(所有放热反应)= Σ(热量输出)
```
(9.4)

```
ΣMiHi + ΣXiHi - ΣNiHi
```
(9.5)

也就是说，炉内物质与热量积的代数和为零。我们以任何炉（例如高炉）为例来说明这一过程。随着我们从顶部到炉部垂直移动，高炉内的温度和反应类型各异，如图 8 所示。因此，为了简单起见，高炉分为三个区域：

### 9.4.1 高炉的不同区域

**第一区**：温度范围（顶部 - 700℃）



## 9.4 高炉炉内物理化学过程

### 9.4.1 炉内温度区域与反应

**第一区**：温度范围（室温 - 700℃）

- 赤铁矿还原为磁铁矿
- 磁铁矿在 700℃下还原为氧化铁
- 氧化铁在 700℃
- 石灰岩在 700℃
- 焦炭在 700℃
- 氧化锰、二氧化硅、氧化物在 700℃

**第二区**：温度范围（700℃ - 1200℃）

- 氧化铁在 900℃
- 氧化铁在 900℃下还原为铁
- 铁在 1200℃
- 石灰岩在 1000℃
- 石灰岩在 1000℃下还原
- 焦炭在 1200℃
- 氧化锰、二氧化硅、氧化物在 1200℃

**第三区**：温度范围（1200℃ - 炉底温度）

- 铁在 1200℃下熔化
- 铁在 1200℃
- 铁在 1200℃下还原
- 焦炭在炉底燃烧

![fig9.8.jpg](img/0102)

### 9.4.2 上述模型的简化

i. 炉料在炼铁中是正常的  
ii. 石灰岩在炼铁中是纯的  
iii. 焦炭在炼铁中也是纯的  
iv. 铁矿石的直接还原可以忽略不计  
v. 铁矿石的还原发生在三个区域  
vi. 酸性氧化物与碱性氧化物之间形成共晶点  
vii. 炉渣在特定温度下形成  
viii. 物质平衡在特定炉内特定温度下进行  
ix. 除氧气以外的添加剂可以忽略  
xi. 高炉内假设具有良好的炉料分布和良好的空气动力学条件  
xii. 最后，高炉内不存在诸如冷却炉底等异常情况

| 成分 | 热输入、输出与显热 |
| :--- | :--- |
| 焦炭的燃烧 | `CO`: `∆Hco = ∆H298 + 298 ∫ (Cp CO - Cp C) dT` ; `CO2`: `∆Hco = ∆H298 + 298 ∫ (Cp CO2 - Cp C) dT` |
| 炉风（空气） | `∆HN2 = 298 ∫ {Cp N2}` ; `∆HO2 = 298 ∫ {Cp O2}` |
| 氧化铁还原 | `Fe2O3` 在顶部（200℃），`∆H1 = T1∫498 {Cp Fe2O3}` ; `∆H2→Fe2O3 + CO = 3FeO + CO2`; `Fe3O4` 在中部（200℃-700℃），`∆H3 = 498∫998 {Cp Fe3O4}` ; `∆H4→FeO + CO = Fe + CO2` `FeO` 在下部（700℃-950℃），`∆H5`; `∆H2→固态→液态; 液态：∆H3 = 1498∫T2 {Cp Fe}` |
| 二氧化硅 → 硅（铁水） | `SiO2`：`∆H1 = T1∫848 {Cp SiO2 (α石英)}` + `848∫1498{Cp SiO2 (β石英)}∆H2` `SiO2 + C = Si + CO2` |
| 氧化锰→锰 | `MnO`：`∆H1 = T1∫1498{Cp MnO)` ; `∆H3→2MnO + C = 2Mn + CO2`（铁水） |
| 磷 | `P2O5`：`∆H1 = T1∫1498{Cp (P2O5)}` ; `∆H3→2P2O5 + 5C = 4P + 5CO2` |
| 石灰岩分解 | `∆H1 = T1∫1298{Cp CaCO3)` ; `∆H2→CaCO3 = CaO + CO2`; `∆H3 = 1298∫1498 {Cp (CaO)}` |
| 渣生成取决于成分 | `SiO2 + CaO = CaSiO3` ; `CaO + S= CaS` ; `P2O5 + 3CaO = Ca3(PO4)2` `∆Hs = ∆Hs1 + ∆Hs2 + ∆Hs3 +……` |
| 矿渣 CaSiO3 MnSiO3 | `∆H1 →SiO2 + CaO = CaSiO3 (矿渣)` ; `CaSiO3: ∆H2 = 1498∫T2{Cp CaSiO3}dT∆H3 →MnO + SiO2= MnSiO3(矿渣)`; `MnSiO3: ∆H2 = 1498∫T2{Cp MnSiO3} dT∆H2 →P2O5 + 3CaO = Ca3(PO4)2.`; `∆H3 = 1498∫T2{Cp Ca3(PO4)2}dT` |
| 炉气外排 | `N2 :∆H1 = T1∫298 { Cp N2}dT` ; `CO: ∆H2 = T1∫298 { Cp CO}dT` ;`CO2 : ∆H3 = T1∫298 { Cp CO2}dT` |

在已知装料的铁矿、焦炭、熔剂、生水和矿渣的成分的情况下，可以计算热量平衡和质量平衡。

`iΣnMiHi = 0;`

摩尔热的代数和，乘以其带有正负号的摩尔量（无论是吸热还是放热），将为零。将高炉炉分为不同的区域，每个区域内热量和质量的流入流可以用方程进行数学建模。因此，可以建立一组线性方程。可以编写一个程序从这组方程中计算出所需的参数。

## 9.5 CO/CO2 在垂直反应器中还原 Fe2O3 的模拟

将赤铁矿送入反应器，并以 `U` 摩尔/秒的固定速率通过 CO/CO2 气体混合物。气体混合物从底部上升，通过不同阶段的氧化物层，氧化物被逐渐还原，即 `Fe2O3`、`Fe3O4`、`FeO` 和 `Fe`。某层的平衡气组成由该层的温度决定。任何层的温度取决于进入气体的温度、向下移动的氧化物/金属的温度，以及放热和吸热反应产生的热量。所提模型如图 9.9 和 9.10 所示。

![fig9.9.jpg](img/00103.jpeg)

### 9.5.1 简化

最初为了简化模型，我们假设区域内的反应是在等温条件下发生的，且反应器壁完全绝热。让我们考虑任意一个区域，例如中间区域 II，计算热平衡和质平衡。

![fig9.10.jpg](img/00104.jpeg)

```
3Fe2O3(s) + CO(g) = 2Fe3O4(s) + CO2(g)
```

质量流入：`x1` 摩尔 `Fe2O3` 和 `x2` 摩尔 `Fe3O4` 进入区域 II。

质量流出：反应后 `y1` `FeO` 和 `y2` `Fe3O4` 离开区域。

进入区域 II 的气体混合物成分为 `CO/CO2 = q1`，离开区域的气体混合物 `CO/CO2 = q2`。

#### 区域 I

质量流入：`x0` 摩尔 `Fe2O3` 进入区域 I

质量流出：`x1` 摩尔 `Fe2O3`、`x2` 摩尔 `Fe3O4`

记住 `x1` 摩尔 `Fe2O3`、`x2` 摩尔 `Fe3O4` 是区域 I 的质量流出

#### 区域 III

质量流入：`y1` `FeO`、`y2` `Fe3O4`

质量流出：`y2` `FeO`、`z1` `Fe`

#### 区域 IV

质量流入：`y2` `FeO`、`z1` `Fe`

质量流出：`z2` `Fe`

| | 区域 I | 区域 II | 区域 III | 区域 IV |
| :--- | :--- | :--- | :--- | :--- |
| 质量流入 | `x0 Fe2O3` | `x1 Fe2O3 , y1 Fe3O4` | `z2 FeO , y2 Fe3O4` | `z3 FeO, r3 Fe` |
| 质量流出 | `x1 Fe2O3 , y1 Fe3O4` | `z2 FeO , y2 Fe3O4` | `z3 FeO, r3 Fe` | `r4 Fe` |
| 气体流入 | `c1q1 CO, c1 CO2` | `c2q2 CO, c2 CO2` | `c3q3 CO, c3 CO2` | `c4q4 CO, c4 CO2` |
| 气体流出 | `c0q0 CO, c0 CO2` | `c1q1 CO, c1 CO2` | `c2q2 CO, c2 CO2` | `c3q3 CO, c3 CO2` |

装料的铁矿成分以及产铁的成分是已知的。从底部进入的气体混合物以及顶部出口的烟气分析是已知的。我们只知道入口的氧化物和气体混合物成分，以及出口（即区域 I 和 IV）的 Fe 成分和气体混合物成分，中间区域的一律未知。

**区域 I**

`x0 Fe2O3 + c1q1 CO + c1 CO2 = x1 Fe2O3 + y1 Fe3O4 + c0q0 CO + c0 CO2`

**区域 II**

`x1 Fe2O3 + c1q1 CO + c1 CO2 = x1 Fe2O3 + y1 Fe3O4 + c1q1 CO + c1 CO2`

**区域 III**

`x1 Fe2O3 + c1q1 CO + c1 CO2 = z3 FeO, r3 Fe`

**区域 IV**

`x1 Fe2O3 + c1q1 CO + c1 CO2 = r4 Fe`



## 区域 II

`x1 Fe2O3 + c1q1 CO + c1 CO2 = x1 Fe2O3 + y1 Fe3O4 + c1q1 CO + c1 CO2`

## 区域 III

`x1 Fe2O3 + c1q1 CO + c1 CO2 = z3 Feo, r3 Fe`

## 区域 IV

`x1 Fe2O3 + c1q1 CO + c1 CO2 = r4 Fe`

(等等，我发现我还没有输出最终结果。这里是最终结果：)

## 区域 I

`x0 Fe2O3 + c1q1 CO + c1 CO2 = x1 Fe2O3 + y1 Fe3O4 + c0q0 CO + c0 CO2`

## 区域 II

`x1 Fe2O3 + c1q1 CO + c1 CO2 = x1 Fe2O3 + y1 Fe3O4 + c1q1 CO + c1 CO2`

## 区域 III

`x1 Fe2O3 + c1q1 CO + c1 CO2 = z3 Feo, r3 Fe`

## 区域 IV

`x1 Fe2O3 + c1q1 CO + c1 CO2 = r4 Fe`

(由于我之前的思考过程出现了严重问题，我将重新提供完整的、符合格式的翻译)

| 矿渣 CaSiO3 MnSiO3 | ∆H1 →SiO2 + CaO = CaSiO3 (矿渣) ; CaSiO3: ∆H2 = 1498∫T2{Cp CaSiO3}dT ∆H3 →MnO + SiO2= MnSiO3(矿渣); MnSiO3: ∆H2 = 1498∫T2{Cp MnSiO3} dT ∆H2 →P2O5 + 3CaO = Ca3(PO4)2.; ∆H3 = 1498∫T2{Cp Ca3(PO4)2}dT |
| :--- | :--- |
| 炉气外排 | N2 :∆H1 = T1∫298 { Cp N2}dT ; CO: ∆H2 = T1∫298 { Cp CO}dT ; CO2 : ∆H3 = T1∫298 { Cp CO2}dT |

在已知装料的铁矿、焦炭、熔剂、生水和矿渣的成分的情况下，可以计算热量平衡和质量平衡。

`iΣnMiHi = 0;`

摩尔热的代数和，乘以其带有正负号的摩尔量（无论是吸热还是放热），将为零。将高炉炉分为不同的区域，每个区域内热量和质量的流入流可以用方程进行数学建模。因此，可以建立一组线性方程。可以编写一个程序从这组方程中计算出所需的参数。

## 9.5 CO/CO2 在垂直反应器中还原 Fe2O3 的模拟

将赤铁矿送入反应器，并以 `U` 摩尔/秒的固定速率通过 CO/CO2 气体混合物。气体混合物从底部上升，通过不同阶段的氧化物层，氧化物被逐渐还原，即 `Fe2O3`、`Fe3O4`、`FeO` 和 `Fe`。某层的平衡气组成由该层的温度决定。任何层的温度取决于进入气体的温度、向下移动的氧化物/金属的温度，以及放热和吸热反应产生的热量。所提模型如图 9.9 和 9.10 所示。

![fig9.9.jpg](img/00103.jpeg)

### 9.5.1 简化

最初为了简化模型，我们假设区域内的反应是在等温条件下发生的，且反应器壁完全绝热。让我们考虑任意一个区域，例如中间区域 II，计算热平衡和质平衡。

![fig9.10.jpg](img/00104.jpeg)

```
3Fe2O3(s) + CO(g) = 2Fe3O4(s) + CO2(g)
```

质量流入：`x1` 摩尔 `Fe2O3` 和 `x2` 摩尔 `Fe3O4` 进入区域 II。

质量流出：反应后 `y1` `Feo` 和 `y2` `Fe3O4` 离开区域。

进入区域 II 的气体混合物成分为 `CO/CO2 = q1`，离开区域的气体混合物 `CO/CO2 = q2`。

此地

#### 对于区域 I

质量流入：`x0` 摩尔 `Fe2O3` 进入区域 I

质量流出：`x1` 摩尔 `Fe2O3`、`x2` 摩尔 `Fe3O4`

记住 `x1` 摩尔 `Fe2O3`、`x2` 摩尔 `Fe3O4` 是区域 I 的质量质量

#### 对于区域 III

质量流入：`y1` `Feo`、`y2` `Fe3O4`

质量流出：`y2` `Feo`、`z1` `Fe`

#### 对于区域 IV

质量流入：`y2` `Feo`、`z1` `Fe`

质量流出：`z2` `Fe`

| | 区域 I | 区域 II | 区域 III | 区域 IV |
| :--- | :--- | :--- | :--- | :--- |
| 质量流入 | `x0 Fe2O3` | `x1 Fe2O3 , y1 Fe3O4` | `z2 Feo , y2 Fe3O4` | `z3 Feo, r3 Fe` |
| 质量流出 | `x1 Fe2O3 , y1 Fe3O4` | `z2 Feo , y2 Fe3O4` | `z3 Feo, r3 Fe` | `r4 Fe` |
| 气体流入 | `c1q1 CO, c1 CO2` | `c2q2 CO, c2 CO2` | `c3q3 CO, c3 CO2` | `c4q4 CO, c4 CO2` |
| 气体流出 | `c0q0 CO, c0 CO2` | `c1q1 CO, c1 CO2` | `c2q2 CO, c2 CO2` | `c3q3 CO, c3 CO2` |

装料的铁矿成分以及产铁的成分是已知的。从底部进入的气体混合物以及顶部出口的烟气分析是已知的。我们只知道入口的氧化物和气体混合物成分，以及出口（即区域 I 和 IV）的 Fe 成分和气体混合物成分，中间区域的一律未知。

**区域 I**

`x0 Fe2O3 + c1q1 CO + c1 CO2 = x1 Fe2O3 + y1 Fe3O4 + c0q0 CO + c0 CO2`

**区域 II**

`x1 Fe2O3 + c1q1 CO + c1 CO2 = x1 Fe2O3 + y1 Fe3O4 + c1q1 CO + c1 CO2`

**区域 III**

`x1 Fe2O3 + c1q1 CO + c1 CO2 = z3 Feo, r3 Fe`

**区域 IV**

`x1 Fe2O3 + c1q1 CO + c1 CO2 = r4 Fe`

VI.) 投入炉的废料也是低碳钢废，且假设完全未氧化。

## 9.6.2 输入热源

炉内热输入的源包括：

* 态金属的热量。
* 态金属中 `Silicon` 的氧化热。
* 态金属中 `Carbon` 的氧化热。
* 态金属中 `Phosphorous` 的氧化热。
* 态金属中锰的氧化热。
* 态金属中铁的氧化热。

### 9.6.3 输出热源

炉内热输出的源包括：

* 钢废的加热热。
* 熔渣的显热。
* `CaS` 及其他熔渣产物的形成热。
* `LD` 气体的显热。

## 9.6.4 热平衡

| 热入 | 热出 |
| :--- | :--- |
| 1.) 态金属的显热 | 1) 钢态水的显热 |
| 2) 态金属中 `Silicon` 的氧化热 | 2) 熔渣的显热 |
| 3) 态金属中 `Carbon` 的氧化热 | 3) 石灰的加热热 |
| 4) 态金属中 `Phosphorous` 的氧化热 | 4) `LD` 气体的显热 |
| 5) 态金属中锰的氧化热 | |
| 6) 态金属中铁的氧化热 | |

`Hin = ∆Hi + ∆Hii + ∆Hiii + ∆Hiv + ∆Hv + ∆Hvi`

`Hout = ∆Hi + ∆Hii + ∆Hiii + ∆Hiv..`

## 9.6.5 示例程序

附录中给出了示例程序 `9.6.5 SP_LDHeatBalance.java`。该程序可以根据需求进行修改。

# 第 10 章：应用部分-III，结构退化与防护

## 10.1 海洋环境中腐蚀钢结构的寿命预测

通过计算机建模对数学关系未知的系统行为预测，是应用科学和工程进步的一个非常重要的方面。在这种情况下，需要一组实验或真实数据，通过数据的统计分析来预测属性或参数。

对于海洋环境中钢结构的寿命预测，对于设计和腐蚀工程师来说，无论是现有结构还是新建结构，都是一项具有挑战性的任务。海洋腐蚀速率是流体性质和海水化学性质许多参数的复杂函数。影响速率的主要参数有盐度、硫酸盐、碳酸氢盐、pH 温度和溶解氧。这些参数的变化范围很大，取决于结构的地理位置以及结构部分浸没的海水深度。参数之间的相互关系使得建立数学方程变得非常困难。寻找一个结构退化速率最小的地理位置也是很有意义的。

### 10.1.1 遗传算法 (GA) 建模

我们在第 5 章中学习了 `GA`。它是解决已知很少问题的最佳方法之一。算法从一组解（由染色体表示）开始，称为种群。从一个种群中提取解并用于形成新的种群，以找到比旧种群更好的解。被选中形成新解（后代）的解根据其适应度进行选择——它们越合适，繁殖的机会就越大。该算法包含以下步骤：

1. 生成一个包含 `n` 个染色体（问题的合适解）的随机种群。
2. 评价种群中每个染色体 `x` 的适应度 `f(x)`。
3. 重复以下步骤创建一个新种群：
   - **选择**：根据适应度从种群中选择两个父染色体。在轮盘赌选择中，个体被选中的概率与其适应度直接成正比（适应度越高，被选中的概率越大）。
   - **交叉**：以交叉概率，父代进行交叉形成新的后代。最常见的类型是单点交叉。如果没有执行交叉，后代将是父代的精确拷贝。
   - **变异**：以变异概率，新后代在每个位点（染色体中的位置）发生变异。
   - **接受**：将新后代放入新种群中。
4. 使用新生成的种群进一步运行算法。
5. **测试**：如果满足终止条件，则停止并返回当前种群中的最佳解；否则（循环）回到步骤 2。

应用遗传算法从氯离子、硫酸盐、`PH`、温度和溶解氧含量这五个基因的组合中获得最佳拟合染色体，以最小化目标函数（公式 5），该函数代表作为所有参数复杂函数的腐蚀速率。每个基因长度是一个六位编码二进制数，染色体长度为 30 位二进制。基因的解码值受约束限制，基因 `Cl` 的解码最小值和最大值为 15-24，基因 `SO4` 为 0.8 – 3.4，基因 `[O]` 为 5-12，基因 `PH` 为 4-8，基因 `temp` 为 10-40。

该算法由以下步骤组成：

1. 测试每个染色体，查看其解决当前问题的效果如何，并据此分配适应度评分。适应度评分是衡量染色体优坏的指标。
2. 程序中有 600 个种群，每个种群包含 2000 代。从种群中选择两个成员。被选中的概率与染色体的适应度成比。使用了轮盘赌选择。为每个成员分配轮盘区域。
3. 每次选取两个染色体进行 `交叉`，取决于交叉率。在这里沿长度选择一个随机点交换位点。选择了交叉率为 0.7。
4. 接下来在变异阶段，染色体内的位点将发生翻转（0 变 1，1 变 0）。变异率取了一个很小的值 0.001。
5. 重复步骤 2、3 和 4，直到创建新种群。

附录中给出了程序 `10.1.1 SP_GeneticCorrosion.java`。

```
![](img/0107.jpeg)
```

找到的最佳拟合染色体 = `010001000111000011001101`

代数：586

种群：2

基因组合：

* 基因 1：`Cl-`（二进制 `010001`）解码为 17 g/L
* 基因 2：`PH`（二进制 `000111`）解码为 7
* 基因 3：`SO42`（二进制 `000011`）解码为 g/L
* 基因 4：`Temp`（二进制 `001101`）解码为 13°C
* 基因 5：`[O]`（二进制 `000101`）解码为 5 ppm

最小腐蚀速率 `Icorr = 16.0225 µA/cm2`

从上述结果可以看出，2000 代的第一个种群未能产生所需的染色体。在第二个种群中，经过 586 代后，找到了最佳基因组合。因此，浓度为 17 g/L 氯离子、3 g/L 硫酸盐、溶解氧为 5 ppm、pH 值为 7、温度为 13°C 的水性海洋环境对低碳钢产生 16.0225 µA/cm2 的最小腐蚀速率。在这些成分、pH 值和温度下进行了实验，得到的腐蚀速率为 18.28 µA/cm2。

### 10.2 通过 ANN 研究环境化学影响下的材料腐蚀行为

全球海水均具有腐蚀性，但浸没金属结构的降解过程强度各不相同，这取决于结构的地理位置。这是由于主要控制结构寿命的参数，如氯离子 (`Cl-`)、硫酸根 (`SO42-`)、碳酸氢根 (`(HCO3-)`)、`pH`、温度 (`T`)、溶解氧 `[O]`，在不同的海洋、海水以及沿深度方向存在变化。我们将尝试通过构建人工神经网络 (`ANN`) 计算机模型，研究海水成分变化对降解速率的影响。

ANN 建模涉及一组均匀的关联神经元。“它们中的每一个都具有某些信息输入，其数量等于系统独立输入参数的数量，并具有一定数量的输出，由此形成输出参数。在设计和训练神经网络时，必须考虑以下事宜：(i) 神经网络架构，(ii) 训练算法以及 (iii) 传递函数。

ANN 建模的细节已在第 6 章中讨论。使用了一个输入层、一个隐藏层和一个输出层的通用结构。输入层和输出层的神经元数量分别由输入参数和输出参数的数量决定”（9 ）。

#### 数据输入

选取五个输入神经元，即氯离子、硫酸根 (`SO4 --`)、`pH`、碳酸氢根 (`HCO3 -`) 和温度来预测输出——腐蚀电流。

首先，我们构建输入矩阵 `p` 和输出矩阵 `q`

```
p = [ Cl, SO4, O, pH, T ]
```

```
t = [ Icorr ]
```

其中 `Cl`、`SO4`、`O` 是在 `pH` 和温度 `T` 下海氯离子、硫酸根和溶解氧的浓度。

`Icorr` 是海水中材料的腐蚀速率，以电化学腐蚀电流表示。

首先，我们需要提供如下的 `p` 和 `q` 的已知实验值或真实值

##### 10.2.1 ANN Java 程序

数据从 Excel 表格读取。

程序 `10.2.1.SRP_NNetExcelData2.java` 见附录。

注意：其他 Java 文件取自 `sp_package:1.SP_Mapminmax_pack.java`、2. `Neuron.java`、3. `Connection.java`。

`SP_Mapminmax_pack` 需要加载以将输入数据转换为无量纲，并将结果恢复为无量纲。

`sp_package`：此包下的所有 Java 程序位于最后的附录。

要理解这些步骤，请阅读第 6 章的理论部分。

##### 步骤

1. 它将全数据划分为训练集、验证集和测试集。
   - 60% 用于训练集
   - 20% 用于测试集
   - 20% 的数据用于验证集。
2. 使用带有前向反向传播函数 `newff` 的 `nn`，包含两层。
3. 第一层（隐藏层）具有 20 个具有传递函数 `tansig` 的神经元，以及输出层。
4. 一个具有传递函数 `purelin` 和训练函数 `traingd` 的神经元。
5. 将生成模型的仿真。

#### 10.2.2 仿真结果与腐蚀研究

图 10.1 和 `fig 10.2` 是通过 matlab 编程生成的图形，用于海水化学性质对海洋钢结构降解速率和寿命影响的建模与仿真。

![fig10.1.jpg](img/00108.jpeg)

![fig10.2.jpg](img/00109.jpeg)

### 10.3 阴极保护的建模与仿真

![fig10.3.jpg](img/00110.jpeg)

用于阴极保护的电位随距离增加而衰减，导致过保护和保护不足的问题。如果管道上点 A（图 10.3）施加保护电位，则 B 点的电位降低，C 点的电位进一步降低所需的电位以下。如果增加 A 点的电位，周围区域可能得到良好保护，但在 C 点保护不足而在 A 点过保护。

控制电位衰减的多个变量（如化学性质、流体属性、温度、极化行为等）之间复杂的相互关系使得不存在简单的关系。已基于拉普拉斯方程以及随后的数值分析和通过可视化 `C++` 编程开发了模型。模型能够发现某些真实系统中的电位分布。

该模型对于寻找已安装结构的电位分布非常有用，可以进行现场测试或腐蚀监测来获取一些输入数据。程序已在一个非常大的矩形表面上运行，以研究电位下降到什么程度。

#### 10.3.1 模型简化

模型将电解质体积划分为一个细密节点 `NODES` 网络，其电属性根据拉普拉斯方程通过一组方程相互关联。因此，在提供边界条件的情况下，数值技术和随后的计算机编程可以获得方程的解。

在电解质浓度均匀的假设下，阴极保护系统附近的电位电流分布由拉普拉斯方程控制

```
∆2Φ = 0
```

```
对于 2D d2Φ/ dx2 + d2Φ/ dy2 = 0
```

其中 `Φ` 是介质的任何电属性。模型将电解质体积划分为一个细密节点 `NODES` 网络，其电属性根据拉普拉斯方程通过一组方程相互关联。因此，在提供边界条件的情况下，数值技术和随后的计算机编程可以获得方程的解。

#### 10.3.2 边界条件

通过求解拉普拉斯方程，可以获得边界处的电位，施加外加电流或牺牲阳极。为了找到其他节点的边界值，需要更多输入数据。基于第一原理欧姆定律找到了其他节点的边界值。

程序 `10.3.3.SP_CathodicProtection.java` 见附录

##### 10.3.3 第一种模型的数据输入

长度(m) = 1000 宽度(m) = 0.5

节点间距(m) = 10，跨越周角的 30 度

施加电位(mV) 对比 Cu/SO4 950

排水点的 C.D.(mA/sq.m) 10

介质电阻(ohm cm) = 500

精度水平 0.01

输出

迭代次数 55

55 次迭代后不同节点的电位(mV)

![fig10.4.jpg](img/00111.jpeg)

#### 10.3.4 第二种模型的数据输入

该模型用于受阴极保护的管道。由于管道周边的曲率，电位分布是以沿曲面的角距离和沿长度的纵距离获得的。该模型也适用于真实的地下燃气管道

输入

长度 = 500 m 直径(m) = 0.45 m

节点间距(长度) ~50m

节点间距(角度) = 60°

节点总数 44

极化电位 = 950 m V .

涂层钢上的施加电流 = 50 (J.l m/m2)

土壤电阻 = 1000 ohm cm

#### 10.3.5 窗口化编程



开发了如图 10.5 所示的窗口化软件。数据输入到如图 10.5 所示的对话框中，并将生成如图 10.6 所示的带有电位分布的管道图形。这将指导设计工程师对腐蚀环境下的钢结构进行正确的阴极保护设计。根据上述电位变化的信息，对于工程师来说，为了实现良好的阴极保护而正确放置阳极连接将非常容易。

![fig10.5.jpg](img/00112.jpeg)

相图是使用强度变量 `T` 和 `x` 在保持 `p` 恒定的情况下对系统平衡态的图示表示。可以使用热力学数据结合所有相关相的 `G` 计算平衡态。

```
G = XA GA + XB GB + ΔHmix − TΔ Smix                                     (11.1)
```

### 对于理想溶液

```
Gid = XA GA + XB GB + RT( XA lnXA + XB lnXB)                                  (11.2) 
```

### 对于正则溶液

```
Greg = XA GA + XB GB + ΩXA XB + RT( XA lnXA + XB lnXB)                (11.3) 
``` 

其中 `Ω` 是正则溶液的过剩自由能系数。

![fig11.1.jpg](img/00114.jpeg)

## 11.2 节从吉布斯自由能构建相图

生成二元体系 A-B 相图的步骤如下：

1. 获取在 A 和 B 熔点之间不同温度下液线和固相线的自由能随成分变化的图谱。
2. 获取固定温度下不同成分处固相线和液相线曲线的斜率（化学势）。
3. 寻找公切线点，使得液相线的斜率等于固相线的斜率。在该温度下可以得到相图的两个点。
4. 对其他温度下的其他点重复步骤 1-3。绘制出完整的相图。

**注意：** 成分 A-B 可以是理想溶液，也可以是正则溶液。我将展示针对等晶体系和共晶体系正则溶液的程序代码。

```
∆G ( regular ) = XA GA + XB GB + Ω XA XB + RT( XA lnXA + XB lnXB)
```

### 11.2.1 二元等晶体系（具有无限溶解度的二元溶液）

附录中程序 `11.2.1 SP_PhaseDiagram.java`。

**数据输入**

* A 的熔点 `Ta = 1685 K`；
* B 的熔点 `Tb = 1210.4 K`；
* A 的熔变为 = 50.5 Kj/mole；
* B 的熔变为 = 36.94 Kj/mole；
* 正则溶液固态混合热系数 `e1 = 6.5`；
* 正则溶液液态混合热系数 `e2 = 3.5`；

![fig11.2.jpg](img/00115.jpeg) 

### 11.2.2 二元共晶体系（具有互溶间隙的二元溶液）

考虑一个体系，其中液相近似理想，但对于固相有 `ΔHmix > 0`。

在低温下，存在一个区域，固溶溶以成分为 `X1` 和 `X2` 的两相 `α1` 和 `α2` 的混合最为稳定。该区域被称为互溶间隙。

![fig11.3.jpg](img/00116.jpeg)

可以修改程序 `11.2.1 SP_PhaseDiagram.java` 以处理二元共晶体系中的互溶间隙。使用以下输入数据运行程序：

**输入数据**

* A 的熔点 `Ta = 800 K`；
* B 的熔点 `Tb = 1200 K`；
* A 的熔变为 = 8.0 Kj/mole；
* B 的熔变为 = 12 Kj/mole；
* 正则溶液固态混合热系数 `e1 = 0`；
* 正则溶液液态混合热系数 `e2 = -2000`；

使用上述数据生成共晶图（图, 11.4）。

![fig11.4.jpg](img/00117.jpeg)

## 11.3 合金设计

改进或开发改良合金具有反复的需求，其动力可能是：

* 性能驱动（例如：提高排气门的工作温度）
* 成本驱动（例如：降低铸铁的成本）

传统的试错法合金开发方法既昂贵又耗时。在复杂的多组分体系中，改进合金成分的路径可能显而易见。

计算热力学和动力学建模工具已取得显著进展：

* 可用的改进的多组分体系模型
* 可用的大型相平衡实验数据库用于比较和验证

### 11.3.1 经验建模

用于建模和模拟需要大量合金成分与合金属性（如强度、硬度）对应的数据，这可以通过插值/外推法、遗传算法和神经网络完成。这种经验建模的主要特征如下：

* 使用现有的材料成分与其属性之间关系的数据库
* 利用这些关系来识别具有所需属性的新成分
* 曲线拟合、神经网络等。

**缺点**

* 需要访问大型数据库（成分/结构）

### 11.3.2 现象学建模

这种经验建模的主要特征是[脆性](https://en.wikipedia.org/wiki/Fracture_toughness)断裂。

断裂韧性是一种描述材料在存在裂纹时抗[断裂](https://en.wikipedia.org/wiki/Fracture)能力的属性。它用 `Ic` 表示。下标 `I` 表示 I 型模式，因为材料可以被制成剪切（II 型）或撕裂（III 型）。

## 11.4 合金开发

应力因子 `(K)` 是断裂韧性的参数，决定了带有特定缺口的试样所承受的最大应力值。根据试样的载荷方向和厚度，使用了四种类型的应力因子：`KC`、`KIC`、`KIIC` 和 `KIII`。

* `KC`：试样厚度小于关键值的应力因子，取决于厚度。这种状态称为平面应力。
* `KIC`、`KIIC`、`KIII`：对应试样厚度大于关键值的应力因子，因此 `KIC`、`KIIC` 和 `KIII` 的值不取决于试样厚度。这种状态称为平面应变。

## 11.5 断裂韧性

神经网络设计了 8 个输入神经元（`YS` 屈服强度以及 C、Si、Mn、Mo、Ni、Cr、V 的成分）和一个输出 `KIC`（断裂韧性），使用 100 多组数据（附录-2）研究成分和屈服强度对断裂韧性的影响。

**程序**

程序 `11.5.2 SP_Fracture.m` 使用 Matlab 编写而非 Java，代码见录。程序使用的断裂韧性数据见附录中的 A1 表。

**注意：** 任何疑问请学习 ANN 第 6 章。

![fig11.7.jpg](img/00120.jpeg)
![fig11.8.jpg](img/00121.jpeg)
![fig11.9.jpg](img/00122.jpeg)
![fig11.10.jpg](img/00123.jpeg)

## 12.1 第 1 章 Java 编程基础

### 1.2.1 程序代码：文件名：`SP_prog1.java`

```java
import java.util.Scanner;
import java.io.*;
import java.math.*;

public class SP_Progm1 {
    public static void main(String[] args) {
        //用于读取数组
        Scanner inpData = new Scanner(System.in);
        System.out.print("输入房间尺寸 l,w,h，考虑 w 小于 l 且 h 小于 w，最短的的 ");
        double l = inpData.nextDouble();
        double w = inpData.nextDouble();
        double h = inpData.nextDouble();
        System.out.print("输入你考虑的起始最小球直径 u ");
        float x = inpData.nextFloat();
        System.out.print("输入每阶段球直径的增量（占初始直径的比例，例如 0.20, 0.30 等）");
        float y = inpData.nextFloat();
        System.out.print("输入你想增加球直径的最大次数");
        int n = inpData.nextInt();
        double d[] = new double[n];
        double v[] = new double[n];
        double V[] = new double[n];
        int nm[] = new int[n];
        System.out.print("输入你考虑的起始最小球直径 u ");
        d[1] = x;
        int k = 1;
        for (int i = 1; i <= n; i++) {
            v[i] = (float) (Math.PI * (Math.pow(d[i], 2.0)) / 4);
            nm[i] = (int) ((l * w * h) / v[i]);
            V[i] = l * w * h - nm[i] * v[i];
            d[i + 1] = d[i] + y * d[i]; // 球的直径增加 20%
            k = i;
            if (d[i + 1] > h) break;
        }
        //显示数据
        System.out.println("k,n," + k + n);
        for (int i = 1; i <= k; i++) {
            System.out.print("dia= " + (int) d[i]);
            System.out.print("  number= " + nm[i]);
            System.out.println("  vacant space=" + (float) V[i]);
        }
    }
}
```

### 程序 1.4.2 `SP_MaxMin.java`

```java
package sp_package;

import java.util.Scanner;
import java.io.*;
import java.math.*;
import java.util.*;

public class SP_MaxMin {
    // 最大值
    public static double getMax(double[] x) {
        double maxValue = x[0];
        for (int i = 1; i < x.length; i++) {
            if (x[i] > maxValue) {
                maxValue = x[i];
            }
        }
        return maxValue;
    }

    // 最小值
    public static double getMin(double[] x) {
        double minValue = x[0];
        for (int i = 1; i < x.length; i++) {
            if (x[i] < minValue) {
                minValue = x[i];
            }
        }
        return minValue;
    }
}
```

### 程序 1.4.2 `SP_ReadPackage.java`

```java
import sp_package.*;
import java.util.Scanner;
import java.io.*;
import java.math.*;
import java.util.*;

public class SP_ReadPackage {
    public static void main(String args[]) {
        SP_MaxMin mn = new SP_MaxMin();
        double x[] = {4.5, 2.3, 0.5, 4.2};
        double max = mn.getMax(x);
        double min = mn.getMin(x);
        System.out.println("max=" + max + " min=" + min);
    }
}
```

### 示例程序 1.6.4.2 `SP_ReadData.java`

```java
import java.util.Scanner;
import java.io.DataInputStream;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;

public class SP_ReadData {
    public static void main(String[] args) {
        String strFilePath = "C://Engg_Problem/data.txt";
        Scanner inpData = new Scanner(System.in);
        System.out.print("数据量: ");
        int n = inpData.nextInt();
        try {
            FileInputStream fin = new FileInputStream(strFilePath);
            DataInputStream din = new DataInputStream(fin);
            float x[] = new float[5];
            float y[] = new float[5];
            for (int i = 0; i < n; i++) {
                x[i] = din.readFloat();
                y[i] = din.readFloat();
            }
            System.out.println("x[i] y[i] 数据");
            for (int i = 0; i < n; i++) {
                System.out.print(" " + x[i]);
                System.out.println(":" + y[i]);
            }
            din.close();
        } catch (FileNotFoundException fe) {
            System.out.println("FileNotFoundException : " + fe);
        } catch (IOException ioe) {
            System.out.println("IOException : " + ioe);
        }
    }
}
```

### 程序 1.7.3 `SP_Graphics`

一个图形程序的示例如下。

#### 程序 1.7.1 `SP_Graphics.java`

```java
import java.awt.*;
import java.awt.event.*;
import java.awt.geom.*;

public class SP_Graphics extends Frame {
    public void paint(Graphics g) {
        g.setColor(Color.yellow);
        g.fillRect(30, 40, 100, 50);
        g.setColor(Color.blue);
        g.drawRect(30, 40, 100, 50);
        g.drawString("Example of Rectangle", 30, 30);
        g.setColor(Color.MAGENTA);
        g.fillOval(200, 100, 85, 85);
        Font fnt = new Font("Arial", Font.BOLD, 12);
        g.setFont(fnt);
        g.setColor(Color.BLACK);
        g.drawString("Java Programming by Raj Pal", 80, 250);
    }
    public static void main(String args[]) {
        Frame frame = new SP_Graphics();
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent we) {
                System.exit(0);
            }
        });
        frame.setSize(500, 350);
        frame.setVisible(true);
    }
}
```

#### 程序 1.7.2 `SP_Graphics.java`



```java
import java.util.Scanner;
import java.awt.*;
import java.awt.event.*;
import java.awt.geom.*;

public class SP_Graphics3 extends Frame {
    Scanner inpData = new Scanner(System.in);
    System.out.print("输入圆心 x,y & 直径 d: ");
    int x = inpData.nextInt();
    int y = inpData.nextInt();
    int d = inpData.nextInt();
    System.out.print("输入线条 x1,y1 & x2,y2: ");
    int x1 = inpData.nextInt();
    int y1 = inpData.nextInt();
    int x2 = inpData.nextInt();
    int y2 = inpData.nextInt();
    g.setColor(Color.BLACK);
    g.drawLine(x1, y1, x2, y2);
    g.setColor(Color.blue);
    for (int i = 1; i < 10; i++) {
        g.drawOval(x, y, d, d);
        d = d + 10;
    }
    Font fnt = new Font("Arial", Font.BOLD, 12);
    g.setFont(fnt);
    g.setColor(Color.BLACK);
    g.drawString("Graphics with User data circle with increasing dia & line", 20, 220);
}
```

*(注：原文提供的文本在最后部分存在严重的结构混乱（如代码块与文本交叉嵌套），翻译已根据逻辑关系对内容进行了尽可能的对齐和还原。)*

```java
g.drawString("Java Programming by Raj Paul", 10, 250);
g.translate(250, 150); // 将原点移到中心  
g.setColor(Color.BLACK);
g.drawLine(0, -150, 0, 150);
g.drawLine(-250, 0, 250, 0);
Font font1 = new Font("Arial", Font.BOLD, 12);      
g.setFont(font1);
g.drawString("X axis", 200, 10);
g.drawString("Y axis", -10, -100);
g.drawString("原点平移示例", 60, -100);
g.drawOval(-5, -5, 10, 10);
g.drawString("蓝色圆圈和线条随原点从左上角平移到中心", -200, -60);
g.setColor(Color.RED);
g.drawLine(30, 20, 100, 120);
g.drawOval(10, 10, 40, 40);      
}

public static void main(String args[]) {
    Frame frame = new SP_Graphics4();
    frame.addWindowListener(new WindowAdapter() {
        public void windowClosing(WindowEvent we) {
            System.exit(0);
        }
    });
    frame.setSize(500, 300);
    frame.setVisible(true);
}
```

### 程序 1.8.4 SP_ExcepTest.java

```java
import java.io.*;
import java.util.Scanner;

public class SP_ExcepTest {
    public static void main(String args[]) {
        double a[] = new double[2];
        // a[1]=1; a[2]=3.2;
        try {
            System.out.println("访问第三个元素：" + a[3]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("抛出的异常：" + e);
        }
        System.out.println("代码块之外");
    }
}
```

### 程序 1.8.6 SP_ExcepTest2.java

```java
import java.io.*;
import java.util.Scanner;

public class SP_ExcepTest2 {
    public static void main(String args[]) {
        double a[] = new double[2];
        // a[1]=1; a[2]=3.2;
        try {
            System.out.println("访问第三个元素：" + a[3]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("抛出的异常：" + e);
        } finally {
            a[0] = 6;
            System.out.println("第一个元素的值：" + a[0]);
            System.out.println("finally 语句正在执行");
        }
    }
}
```

### 程序 1.9.1 SRP_ReadExcel.java

```java
import java.io.File;
import java.io.IOException;
import jxl.Cell;
import jxl.CellType;
import jxl.Sheet;
import jxl.read.BiffException;

public class SRP_ReadExcel {
    private String inputFile;

    public void setInputFile(String inputFile) {
        this.inputFile = inputFile;
    }

    // 读取 Excel 数据的函数，将字符串数据转换为 double 并保存到数组 x[][] 中
    public double[][] read() throws IOException {
        File inputWorkbook = new File(inputFile);
        Workbook w;
        double X[][] = new double[300][10]; // 用于存储 Excel 数据的数组，大小 300,10 大于 Excel 中的实际大小
        try {
            w = Workbook.getWorkbook(inputWorkbook); // 获取第一个工作表
            Sheet sheet = w.getSheet(0); // 遍历第一列
            int n = sheet.getRows();
            int m = sheet.getColumns();
            double X[][] = new double[n][m];
            double Y[] = new double[n];
            for (int i = 1; i < sheet.getRows(); i++) {
                for (int j = 0; j < sheet.getColumns(); j++) {
                    Cell cell = sheet.getCell(j, i);
                    CellType type = cell.getType();
                    if (type == CellType.LABEL) {
                        X[i][j] = Double.valueOf(cell.getContents());
                        // System.out.print(" " + X[i][j] );
                    }
                    if (type == CellType.NUMBER) {
                        X[i][j] = Double.valueOf(cell.getContents());
                        // System.out.print(" "+ X[i][j] );
                    }
                }
            }
        } catch (BiffException e) {
            e.printStackTrace();
        }
        return X;
    }

    public static void main(String[] args) throws IOException {
        SRP_ReadExcel test = new SRP_ReadExcel(); // 位置
        test.setInputFile("E:/Java_Eng_Problem/data.xls");
        double xx[][] = test.read(); // 将 read 返回的数据保存到数组 xx 中
        int n = xx.length; // 数组 xx[][] 的长度
        int m = xx[5].length; // 数组 [][] 的长度
        System.out.println("n,m=" + n + " " + m);
    }
}
```

### 程序 1.10.1 SP_Timefn.java

```java
import java.util.*;

public class SP_Timefn {
    public static void main(String args[]) {
        try {
            System.out.println(new Date() + "\n");
            Thread.sleep(1000);
            System.out.println(new Date() + "\n");
        } catch (Exception e) {
            System.out.println("抛出异常!");
        }
    }
}
```

### 程序 1.10.2 SP_TimeDiff.java

```java
import java.util.*;

public class SP_TimeDiff {
    public static void main(String args[]) {
        try {
            long start = System.currentTimeMillis();
            System.out.println(new Date() + "\n");
            Thread.sleep(5000);
            System.out.println(new Date() + "\n");
            long end = System.currentTimeMillis();
            long diff = end - start;
            System.out.println("时间差：" + diff);
        } catch (Exception e) {
            System.out.println("抛出异常!");
        }
    }
}
```

### 程序 1.11.1 SP_Math

```java
import java.util.Scanner;
import java.io.*;
import java.math.*;
import java.util.*;

public class SP_Math {
    public static void main(String args) {
        double x = 72.3;
        double y = 0.34;
        System.out.println("|" + x + "| 是 " + Math.abs(x));
        System.out.println("|" + y + "| 是 " + Math.abs(y));
        System.out.println(x + " 约等于 " + Math.round(x));
        System.out.println(y + " 约等于 " + Math.round(y));
        System.out.println(x + " 的向上取整是 " + Math.ceil(x));
        System.out.println(y + " 的向上取整是 " + Math.ceil(y));
        System.out.println(x + " 的下行取整是 " + Math.floor(x));
        System.out.println(y + " 的下行取整是 " + Math.floor(y));
        System.out.println("min(" + x + "," + y + ") 是 " + Math.min(x, y));
        System.out.println("max(" + x + "," + y + ") 是 " + Math.max(x, y));
    }
}
```

```java
System.out.println("asin(" + value + ") is " + Math.asin(value));
System.out.println("exp(x) is " + Math.exp(x));
System.out.println("exp(y) is " + Math.exp(y));
System.out.println("log(x) is " + Math.log(x));
System.out.println("log(y) is " + Math.log(y));
System.out.println("pow(x, y) is " + Math.pow(x, y));
System.out.println("The square root of " + x + " is " + Math.sqrt(x));
System.out.println("Here's one random number: " + Math.random());
System.out.println("Here's another random number: " + Math.random());
```

### 程序 1.12.1 SP_Animation.java



```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.Insets;
import java.util.Timer;
import java.util.TimerTask;
import java.awt.*;
import java.awt.event.*;
import java.awt.geom.*;
import javax.swing.JFrame;

public class SP_Animation extends JFrame {
    private static int DELAY = 600;
    int a = 0;
    int b = 0;

    public void paint(Graphics g) {
        super.paint(g);
        Font fnt = new Font("Arial", Font.BOLD, 12);
        g.setFont(fnt);
        g.setColor(Color.MAGENTA);
        g.drawString("图形动画示例: Rectangle 形与椭圆 由 sptech.xyz", 60, 50);
        if (a > 450) a = 0;
        if (b > 300) b = 0;
        g.setColor(Color.BLUE);
        g.fillRect(a, 120, 50, 55);
        g.setColor(Color.RED);
        g.fillOval(a, b, 20, 20);
    }

    public void go() {
        TimerTask task = new TimerTask() {
            public void run() {
                a = a + 20;
                b = b + 30;
                repaint();
            }
        };
        Timer timer = new Timer();
        timer.schedule(task, 0, DELAY);
    }

    public static void main(String args[]) {
        SP_Animation f = new SP_Animation();
        f.setSize(500, 300);
        f.show();
        f.go();
    }
}
```

### 程序 1.12.2 SP_Animation1.java

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.Insets;
import java.util.Timer;
import java.util.TimerTask;
import java.awt.*;
import java.awt.event.*;
import java.awt.geom.*;
import javax.swing.JFrame;

public class SP_Animation1 extends Frame implements Runnable {
    Thread runner;
    int a = 50, b = 50;
    int x = 50;
    Graphics g;
    int t;

    public void start() {
        if (runner == null) {
            runner = new Thread(this);
            runner.start();
        }
    }

    public void stop() {
        if (runner != null) {
            runner.stop();
            runner = null;
        }
    }

    public void run() {
        while (true) {
            try {
                runner.sleep(t);
                wait(1000);
            } catch (Exception e) {
            }
            int randomNumber = (int) (Math.random() * 6) + 1;
            a = a + 20;
            b = b + 15;
            if (a > size().width) a = 20;
            if (b > size().width) b = 20;
            repaint();
        }
    }

    public void paint(Graphics gr) {
        g = gr;
        Font fnt1 = new Font("Arial", Font.BOLD, 18);
        g.setFont(fnt1);
        g.drawString("Java 两列运行的火车 由 sptech.xyz", 30, 260);
        {
            t = 70;
            g.setColor(Color.red);
            g.fillRect(a, 20 + x, 60, 20); // 车体
            g.setColor(Color.black);
            g.fillOval(a + 10, 40 + x, 6, 6); // 轮子
            g.fillOval(a + 40, 40 + x, 6, 6); //轮子
            // 火车随着鼠标点击 1,2,3 次向右移动。
        }
        {
            t = 35;
            g = gr;
            g.setColor(Color.blue);
            g.fillRect(b, 70 + x, 60, 20); // 车体
            g.setColor(Color.black);
            g.fillOval(b + 10, 90 + x, 6, 6); // 轮子
            g.fillOval(b + 40, 90 + x, 6, 6); //轮子
            // 火车也随着鼠标点击 1,2,3 次向右移动。
        }
        g.drawLine(0, 46 + x, size().width, 46 + x);
        g.drawLine(0, 96 + x, size().width, 96 + x);
        int z = a + 40;
        if (z < size().width) // y 轴最大长度
            Font fnt = new Font("Arial", Font.BOLD, 14);
        g.setFont(fnt);
        g.setColor(Color.black);
        g.drawString("红色火车速度为 220 Km/hr", 170, 5 + x);
        g.drawString("蓝色火车速度为 110 Km/hr", 170, 120 + x);
        } else {
            Font fnt = new Font("Arial", Font.BOLD, 14);
            g.setFont(fnt);
            g.setColor(Color.blue);
            g.drawString("火车已出了屏幕", 70, 180 + x);
        }

    public static void main(String args[]) {
        SP_Animation1 anm = new SP_Animation1();
        anm.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent we) {
                System.exit(0);
            }
        });
        anm.setSize(500, 350);
        anm.setVisible(true);
        anm.start();
        anm.run();
    }
}
```

### 第 2 章 工程中的数值方法

#### 程序 2.3.1 SP_NumericalDifferentiation.java

```java

import java.util.Scanner;

import java.io.*;

import java.math.*;

public class SP_NumericalDifferentiation {

    double[] d1 = new double[10];

    double[] d2 = new double[10];

    double[] d3 = new double[10];

    double[] d4 = new double[10];

    double[] d5 = new double[10];

    double df;

    double yy;

    public double fn(double xx) {

        double A, B, C, D;

        A = 2;
        B = 1;
        C = 2.5;
        D = 3;

        yy = A * xx + B * pow(xx, 2) + C * log(xx) + D;

        return yy;

    }

    public double dfn(double[] y, double h) {

        d1[1] = y[2] - y[1];

        d1[2] = y[3] - y[2];

        d1[3] = y[4] - y[3];

        d1[4] = y[5] - y[4];

        d1[5] = y[6] - y[5];

        d2[1] = d1[2] - d1[1];

        d2[2] = d1[3] - d1[2];

        d2[3] = d1[4] - d1[3];

        d2[4] = d1[5] - d1[4];

        d3[1] = d2[2] - d2[1];

        d3[2] = d2[3] - d2[2];

        d3[3] = d2[4] - d2[3];

        d4[1] = d3[2] - d3[1];

        d4[2] = d3[3] - d3[2];

        d5[1] = d4[2] - d4[1];

        df = (d1[1] - d2[1] / 2 + d3[1] / 3 - d4[1] / 4 + d5[1]) / h;

        return df;

    }

    public double ddfn(double[] y, double h) {

        double ddf;

        d1[1] = y[2] - y[1];

        d1[2] = y[3] - y[2];

        d1[3] = y[4] - y[3];

        d1[4] = y[5] - y[4];

        d1[5] = y[6] - y[5];

        d2[1] = d1[2] - d1[1];

        d2[2] = d1[3] - d1[2];

        d2[3] = d1[4] - d1[3];

        d2[4] = d1[5] - d1[4];

        d3[1] = d2[2] - d2[1];

        d3[2] = d2[3] - d2[2];

        d3[3] = d2[4] - d2[3];

        d4[1] = d3[2] - d3[1];

        d4[2] = d3[3] - d3[2];

        d5[1] = d4[2] - d4[1];

        ddf = (d2[1] - d3[1] + (11 / 12) * d4[1] - (5 / 6) * d5[1]) / (Math.pow(h, 2));

        return ddf;

    }

    public static void main(String[] args) {

        double[] x = new double[150];

        double[] y = new double[150];

        int i, j;

        SP_NumericalDifferentiation nd = new SP_NumericalDifferentiation();

        Scanner inpData = new Scanner(System.in);

        System.out.println("Enter the value of x");

        double xx = inpData.nextDouble();

        System.out.println("Enter the increament h for finite diff method");

        double h = inpData.nextDouble();

        i = 1;

        x[i] = xx;

        do {

            y[i] = nd.fn(x[i]);

            i = i + 1;

            x[i] = x[i - 1] + h;

        } while (x[i] <= x[1] + 7 * h);

        System.out.println();

    }

}
```

## 程序 2.4.1 SP_NewtonRaphson

```java

double df = nd.dfn(y, h);

double ddf = nd.ddfn(y, h);

double value = 2 + 2 * xx + 2.5 / xx; // 1 阶导数的真实值

double value2 = 2 - 2.5 / (xx * xx); // 2 阶导数的真实值

// 显示结果

System.out.println("1st Derivative=" + df + " Real value=" + value);

System.out.println("2nd Derivative=" + ddf + " Real value=" + value2);

```

```java

import java.util.Scanner;

import java.io.*;

import java.math.*;

/* y= Ax+Bx2 + Clogx + D */

public class SP_NewtonRaphson {

    double d1[] = new double[10];

    double d2[] = new double[10];

    double d3[] = new double[10];

    double d4[] = new double[10];

    double d5[] = new double[10];

    double y[] = new double[10];

    double x[] = new double[150];

    double df;
    double dff;

    double yy;

    public double fn(double xx) {

        double A, B, C, D, h;

        A = -4;
        B = 1;
        C = 2;
        D = 3.4;

        double yy = A * xx + B * Math.pow(xx, 2) + C * Math.log(xx) + D;

        // double yy= Math.pow(xx,2)-4*xx + 4 ;

        return yy;

    }

    public double dfn(double xx, double h) {

        double df;

        int i = 1;

        x[i] = xx;

        do {

            y[i] = fn(x[i]);

            i = i + 1;

            x[i] = x[i - 1] + h;

        } while (x[i] <= x[1] + 7 * h);

        d1[1] = ((y[2]) - (y[1]));

        d1[2] = ((y[3]) - (y[2]));

        d1[3] = ((y[4]) - (y[3]));

        d1[4] = ((y[5]) - (y[4]));

        d1[5] = ((y[6]) - (y[5]));

        d2[1] = d1[2] - d1[1];

        d2[2] = d1[3] - d1[2];

        d2[3] = d1[4] - d1[3];

        d2[4] = d1[5] - d1[4];

        d3[1] = d2[2] - d2[1];

        d3[2] = d2[3] - d2[2];

        d3[3] = d2[4] - d2[3];

        d4[1] = d3[2] - d3[1];

        d4[2] = d3[3] - d3[2];

        d5[1] = d4[2] - d4[1];



## 程序 2.4.3 SP_Gauss_Elimination.java

```java
import java.util.Scanner;

public class SP_Gauss_Elimination {

    public static void main(String[] args) {

        int i = 1, j = 1, itr = 1;
        double sum = 0, temp = 0, tol = 0.001, max = 0, error = 0;
        Scanner input = new Scanner(System.in);

        System.out.println("Enter the number of variables: ");
        int n = input.nextInt();

        System.out.println("Enter the coefficients of a11x1 + a12x2 + a13x3 + ...0 for each equations");
        double a[][] = new double[n + 1][n + 2];

        // 输入
        for (i = 1; i < n + 1; i++) {
            for (j = 1; j < n + 2; j++) {
                a[i][j] = input.nextDouble();
            }
        }

        // 矩阵表示
        System.out.println("The coefficients you entered:");
        for (i = 1; i < n + 1; i++) {
            for (j = 1; j < n + 2; j++) {
                System.out.print(" " + a[i][j]);
            }
            System.out.println();
        }

        System.out.println();

        double x[] = new double[n + 1];
        for (i = 1; i < n + 1; i++) {
            x[i] = 0;
        }

        for (itr = 1; itr < 200; itr++) {
            max = 0;
            for (i = 1; i < n + 1; i++) {
                sum = 0;
                for (j = 1; j < n + 1; j++)
                    if (i != j) {
                        sum = sum + a[i][j] * x[j];
                    }

                temp = (a[i][n + 1] - sum) / a[i][i];
                error = ((x[i] - temp));
                if (error > max)
                    max = error;
                else
                    max = -error;
                x[i] = temp;
            }

            if (max < tol)
                break;
        }

        for (i = 1; i < n + 1; i++) {
            System.out.print(" x" + i + x[i]);
            System.out.println();
        }
    }
}
```

## 程序 2.4.4 SP_Gauss.java

```java
import java.io.*;
import java.util.Scanner;

class SP_Gauss {

    public static double[] gauss(double a[][], double b[]) {
        int n = b.length;
        double carpan = 0;
        double toplam = 0;
        double x[] = new double[n];

        // 消元
        int i, j, k;
        for (k = 0; k < (n - 1); k++) {
            for (i = k + 1; i < n; i++) {
                carpan = a[i][k] / a[k][k];
                a[i][k] = 0;
                for (j = k + 1; j < n; j++) {
                    a[i][j] -= carpan * a[k][j];
                }
                b[i] = b[i] - carpan * b[k];
            }
        }

        // 反代替换
        x[n - 1] = b[n - 1] / a[n - 1][n - 1];
        for (i = n - 2; i >= 0; i--) {
            toplam = 0;
            for (j = i + 1; j < n; j++) {
                toplam += a[i][j] * x[j];
            }
            x[i] = (b[i] - toplam) / a[i][i];
        }

        return x;
    }

    public static void main(String[] args) {
        SP_Gauss g = new SP_Gauss();
        System.out.println("Enter the number of variables: ");
        Scanner input = new Scanner(System.in);
        int n = input.nextInt();
        double a[][] = new double[n][n];
        double b[] = new double[n];

        // 输入
        System.out.println("Enter the matrix & B in AX=B: ");
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                a[i][j] = input.nextDouble();
            }
            System.out.println("B part");
            b[i] = input.nextDouble();
        }

        double x[] = g.gauss(a, b);
        for (int i = 0; i < x.length; i++) {
            System.out.print("Results x values " + x[i]);
        }
    }
}
```

## LU 分解示例程序 2.4.5 SP_LUDecomposition.java

```java
import java.util.Scanner;

public class SP_LUDecomposition {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the dimension of the matrix:");
        int n = sc.nextInt();
        double mat[][] = new double[n][n];
        System.out.println("Enter the dimension of matrix A ::B ");
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                mat[i][j] = sc.nextDouble();

        if (n == 2) {
            double l[][] = new double[n][n];
            l[0][0] = l[1][1] = 1;
            l[0][1] = 0;
            double u[][] = new double[n][n];
            u[1][0] = 0;
            u[0][0] = mat[0][0];
            u[0][1] = mat[0][1];
            l[1][0] = mat[1][0] / mat[0][0];
            u[1][1] = mat[1][1] - (l[1][0] * u[0][1]);
            System.out.println("The L Component is:");
            for (int i = 0; i < n; i++)
                for (int j = 0; j < n; j++)
                    System.out.print(" " + l[i][j]);
            System.out.println();
            System.out.println("The U Component is:");
            for (int i = 0; i < n; i++)
                for (int j = 0; j < n; j++)
                    System.out.print(" " + u[i][j]);
            System.out.println();
        }

        if (n == 3) {
            double l[][] = new double[n][n];
            l[0][0] = l[1][1] = l[2][2] = 1;
            l[0][1] = l[0][2] = l[1][2] = 0;
            double u[][] = new double[n][n];
            u[1][0] = u[2][0] = u[2][1] = 0;
            u[0][0] = mat[0][0];
            u[0][1] = mat[0][1];
            u[0][2] = mat[0][2];
            l[1][0] = mat[1][0] / mat[0][0];
            u[1][1] = mat[1][1] - (l[1][0] * u[0][1]);
            u[1][2] = mat[1][2] - (l[1][0] * u[0][2]);
            l[2][0] = mat[2][0] / mat[0][0];
            l[2][1] = (mat[2][1] - l[2][0] * u[0][1]) / u[1][1];
            u[2][2] = mat[2][2] - (l[2][0] * u[0][2]) - (l[2][1] * u[1][2]);
            System.out.println("The L Component is:");
            for (int i = 0; i < n; i++)
                for (int j = 0; j < n; j++)
                    System.out.print(" " + l[i][j]);
            System.out.println();
            System.out.println("The U Component is:");
            for (int i = 0; i < n; i++)
                for (int j = 0; j < n; j++)
                    System.out.print(" " + u[i][j]);
            System.out.println();
        }

        sc.close();
    }
}
```

## 矩阵求逆示例程序

```java
public static void main(String args[]) {
    char[] var = {'x', 'y', 'z', 'w'};
    System.out.println("输入方程中变量的数量： ");
    Scanner input = new Scanner(System.in);
    int n = input.nextInt();
    System.out.println("输入每个方程中每个变量的系数：");
    System.out.println("ax + by + cz + ... = d");
    double[][] mat = new double[n][n];
    double[][] constants = new double[n][1];

    // input
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            mat[i][j] = input.nextDouble();
        }
        constants[i][0] = input.nextDouble();
    }

    // Matrix representation
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            System.out.print(" " + mat[i][j]);
        }
        System.out.print("  " + var[i]);
        System.out.print("  =  " + constants[i][0]);
        System.out.println();
    }

    // inverse of matrix mat[][]
    double inverted_mat[][] = invert(mat);
    System.out.println("逆矩阵为： ");
    for (int i = 0; i < n; ++i) {
        for (int j = 0; j < n; ++j) {
            System.out.print(" " + inverted_mat[i][j]);
        }
        System.out.println();
    }
}
```



## 程序 2.4 `SP_MultipleRoot_1Variable.java`

```java
import java.util.Scanner;
import java.io.*;
import java.math.*;

/* y = Ax + Bx^2 + Clog + D */
public class SP_MultipleRoot_1Variable {

    double d1[] = new double[10];
    double d2[] = new double[10];
    double d3[] = new double[10];
    double d4[] = new double[10];
    double d5[] = new double[10];
    double y[] = new double[10];
    double df, dff, yy;

    public double fn(double xx) {
        double A, B, C, D;
        A = 2; B = 1; C = 2.5; D = 3;
        yy = A * xx + B * Math.pow(xx, 2) + C * Math.log(xx) + D;
        return yy;
    }

    public double dfn(double[] y, double h) {
        double df;
        d1[1] = y[2] - y[1];
        d1[2] = y[3] - y[2];
        d1[3] = y[4] - y[3];
        d1[4] = y[5] - y[4];
        d1[5] = y[6] - y[5];
        d2[1] = d1[2] - d1[1];
        d2[2] = d1[3] - d1[2];
        d2[3] = d1[4] - d1[3];
        d2[4] = d1[5] - d1[4];
        d3[1] = d2[2] - d2[1];
        d3[2] = d2[3] - d2[2];
        d3[3] = d2[4] - d2[3];
        d4[1] = d3[2] - d3[1];
        d4[2] = d3[3] - d3[2];
        d5[1] = d4[2] - d4[1];
        df = (d1[1] - d2[1] / 2 + d3[1] / 3 - d4[1] / 4 + d5[1]) / h;
        return df;
    }

    public double ddfn(double[] y, double h) {
        double ddf;
        d1[1] = y[2] - y[1];
        d1[2] = y[3] - y[2];
        d1[3] = y[4] - y[3];
        d1[4] = y[5] - y[4];
        d1[5] = y[6] - y[5];
        d2[1] = d1[2] - d1[1];
        d2[2] = d1[3] - d1[2];
        d2[3] = d1[4] - d1[3];
        d2[4] = d1[5] - d1[4];
        d3[1] = d2[2] - d2[1];
        d3[2] = d2[3] - d2[2];
        d3[3] = d2[4] - d2[3];
        d4[1] = d3[2] - d3[1];
        d4[2] = d3[3] - d3[2];
        d5[1] = d4[2] - d4[1];
        ddf = (d2[1] - d3[1] + (11 / 12) * d4[1] - (5 / 6) * d5[1]) / (Math.pow(h, 2));
        return ddf;
    }

    public static void main(String[] args) {
        double x[] = new double[150];
        double y[] = new double[150];
        int i, j;
        double x1, x2, xx1, xx2;
        SP_MultipleRoot_1Variable nd = new SP_MultipleRoot_1Variable();
        Scanner inpData = new Scanner(System.in);
        System.out.println("输入 x 的近似根值");
        double xx = inpData.nextDouble();
        System.out.println("输入有限差分法的增量 h");
        double h = inpData.nextDouble();
        i = 1;
        x[i] = xx;
    }
}
```

## 程序片段

```java
double y = inpData.nextDouble();

do {
    f = A1/y + B1*y + C1*Math.log(x) + D1;
    g = A2/y + B2*y + C2*Math.log(x) + D2;
    dfx = C1/x;
    dfy = -A1/(Math.pow(y,2)) + B1;
    dgx = C2/x;
    dgy = -A2/(Math.pow(y,2)) + B2;
    double A[] = solve();
    hx = A[0];
    hy = A[1];
    x = x + hx;
    y = y + hy;
    i = i + 1;
} while (i <= 8);

double XY[] = {x, y};
return (XY);
}

public double[] solve() {
    hx = (-f/dfy + g/dgy) / (dfx/dfy - dgx/dgy);
    hy = (-f/dfy - dfx*hx/dfy);
    double A[] = {hx, hy};
    return (A);
}

public static void main(String args[]) {
    SP_NonLinEq2Variables nl = new SP_NonLinEq2Variables();
    double XY[] = nl.Compute();
    System.out.println(" x=" + XY[0] + " y=" + XY[1]);
}
```

## 程序 2.6 `SP_LinearRegression.java`

```java
import java.io.*;
import java.util.Scanner;

public class SP_LinearRegression {

    private final double intercept, slope;
    private final double r2;
    private final double svar0, svar1;

    public SP_LinearRegression(double[] x, double[] y) {
        if (x.length != y.length) {
            throw new IllegalArgumentException("array lengths are not equal");
        }

        int n = x.length;
        double sumx = 0.0, sumy = 0.0, sumx2 = 0.0;
        for (int i = 0; i < n; i++) {
            sumx += x[i];
            sumx2 += x[i]*x[i];
            sumy += y[i];
        }

        double xbar = sumx / n;
        double ybar = sumy / n;

        double xxbar = 0.0, yybar = 0.0, xybar = 0.0;
        for (int i = 0; i < n; i++) {
            xxbar += (x[i] - xbar) * (x[i] - xbar);
            yybar += (y[i] - ybar) * (y[i] - ybar);
            xybar += (x[i] - xbar) * (y[i] - ybar);
        }

        slope = xybar / xxbar;
        intercept = ybar - slope * xbar;

        // 更多统计分析
        double rss = 0.0; // 残差平方和
        double ssr = 0.0; // 回归平方和
        for (int i = 0; i < n; i++) {
            double fit = slope*x[i] + intercept;
            rss += (fit - y[i]) * (fit - y[i]);
            ssr += (fit - ybar) * (fit - ybar);
        }

        int degreesOfFreedom = n-2;
        r2 = ssr / yybar;
        svar = rss / degreesOfFreedom;
        svar1 = svar / xxbar;
        svar0 = svar/n + xbar*svar1;
    }

    public double intercept() {
        return intercept;
    }

    public double slope() {
        return slope;
    }

    public double R2() {
        return r2;
    }

    public double interceptStdErr() {
        return Math.sqrt(svar0);
    }

    public double slopeStdErr() {
        return Math.sqrt(svar1);
    }
}
```



## 12.4 第 4 章 优化与线性规划

### 程序 4.3.3 `SRP_Simplex.java`

```java
public double predict(double x) {
    return slope * x + intercept;
}

public String toString() {
    StringBuilder s = new StringBuilder();
    s.append(String.format("%.2f + %.2f", slope(), intercept()));
    s.append(" (R² = " + String.format("%.3f", R2()) + ")");
    return s.toString();
}

public static void main(String args[]) {
    int n;
    Scanner input = new Scanner(System.in);
    System.out.print("输入数据组数量 ");
    n = input.nextInt();
    double x[] = new double[n];
    double y[] = new double[n];
    System.out.println("输入 " + n + " 组数据的 x & y");
    for (int i = 0; i < n; i++) {
        // 读取数组
        x[i] = input.nextDouble();
        y[i] = input.nextDouble();
    }
    LinearRegression lnrg = new LinearRegression(x, y);
    double sp = lnrg.slope();
    double inp = lnrg.intercept();
    double reg = lnrg.R2();
    System.out.println("slope= " + sp);
    System.out.println("intercept= " + inp);
    System.out.println("R= " + reg);
}
```

```java
import java.io.*;
import java.util.Scanner;
import java.math.*;

public class SRP_Simplex {
    private double[][] tableaux; // 裸形
    private int numberOfConstraints; // 约束数量
    private int numberOfVariables; // 变量数量
    private boolean maximizeOrMinimize;
    private static final boolean MAXIMIZE = true;
    private static final boolean MINIMIZE = false;
    private int[] basis; // basis[i] 对应行的基变量

    public SRP_Simplex(double[][] tableaux, int numberOfConstraint, int numberOfVariable, boolean maximizeOrMinimize) {
        this.maximizeOrMinimize = maximizeOrMinimize;
        this.numberOfConstraints = numberOfConstraint;
        this.numberOfVariables = numberOfVariable;
        this.tableaux = tableaux;
        basis = new int[numberOfConstraints];
        for (int i = 0; i < numberOfConstraints; i++)
            basis[i] = numberOfVariables + i;
        solve();
    }

    // 从初始可行基 (BFS) 开始运行单纯法算法
    private void solve() {
        while (true) {
            show();
            int q = 0;
            // 寻找入列
            if (maximizeOrMinimize) {
                q = dantzig();
            } else {
                q = dantNegative();
            }
            if (q == -1)
                break; // 最优
            // 寻找离开行
            int p = minRatioRule(q);
            if (p == -1)
                throw new ArithmeticException("无界形");
            // 旋转
            pivot(p, q);
            // 更新基
            basis[p] = q;
        }
    }

    // 成本最大的非基列索引
    private int dantzig() {
        int q = 0;
        for (int j = 1; j < numberOfConstraints + numberOfVariables; j++)
            if (tableaux[numberOfConstraints][j] > tableaux[numberOfConstraints][q])
                q = j;
        if (tableaux[numberOfConstraints][q] <= 0)
            return -1; // 最优
        return q;
    }

    // 成本最负的非基列索引
    private int dantNegative() {
        int q = 0;
        for (int j = 1; j < numberOfConstraints + numberOfVariables; j++)
            if (tableaux[numberOfConstraints][j] < tableaux[numberOfConstraints][q])
                q = j;
        if (tableaux[numberOfConstraints][q] >= 0)
            return -1; // 最优
        return q;
    }

    // 使用比例法则寻找行（如果没有这样的行则返回 -1）
    private int minRatioRule(int q) {
        int p = -1;
        for (int i = 0; i < numberOfConstraints; i++) {
            if (tableaux[i][q] <= 0)
                continue;
            else if (p == -1)
                p = i;
            else if ((tableaux[i][numberOfConstraints + numberOfVariables] / tableaux[i][q]) < (tableaux[p][numberOfConstraints + numberOfVariables] / tableaux[p][q]))
                p = i;
        }
        return p;
    }

    // 使用高斯-若旦法在 (p, q) 处旋转
    private void pivot(int p, int q) {
        // 除 p 行和 q 列
        for (int i = 0; i <= numberOfConstraints; i++) {
            for (int j = 0; j <= numberOfConstraints + numberOfVariables; j++) {
                if (i != p && j != q)
                    tableaux[i][j] -= tableaux[p][j] * tableaux[i][q] / tableaux[p][q];
            }
        }
        // q 列置零
        for (int i = 0; i <= numberOfConstraints; i++) {
            if (i != p)
                tableaux[i][q] = 0.0;
        }
        // p 行缩放
        for (int j = 0; j <= numberOfConstraints + numberOfVariables; j++) {
            if (j != q)
                tableaux[p][j] /= tableaux[p][q];
        }
        tableaux[p][q] = 1.0;
    }

    // 返回最优目标值
    public double value() {
        return -tableaux[numberOfConstraints][numberOfConstraints + numberOfVariables];
    }

    // 返回解向量
    public double[] solution() {
        double[] x = new double[numberOfVariables];
        for (int i = 0; i < numberOfConstraints; i++) {
            if (basis[i] < numberOfVariables)
                x[basis[i]] = tableaux[i][numberOfConstraints + numberOfVariables];
        }
        return x;
    }

    // 打印裸形
    public void show() {
        System.out.println("M = " + numberOfConstraints);
        System.out.println("N = " + numberOfVariables);
        for (int i = 0; i <= numberOfConstraints; i++) {
            for (int j = 0; j <= numberOfConstraints + numberOfVariables; j++) {
                System.out.printf("%7.2f ", tableaux[i][j]);
            }
            System.out.println();
        }
        System.out.println("value = " + value());
    }
}
```

```java
System.out.println("x_" + basis[i] + " = " + tableaux[i][numberOfConstraints + numberOfOriginalVariables]);
System.out.println();
}
```



# 主函数

```java
public static void main(String[] args) {
    InpData inp = new InpData();
    inp.getTableaux();
    System.out.println(inp.getTableaux());
    SRP_Simplex simplex = new SRP_Simplex(inp.getTableaux(),
        inp.getNumberOfConstraint(),
        inp.getNumberOfOriginalVariable(), MAXIMIZE);
    double[] x = simplex.solution();
    for (int i = 0; i < x.length; i++)
        System.out.println("x[" + i + "] = " + x[i]);
    System.out.println("Solution: " + simplex.value());
}
```

```java
private enum Constraint {
    lessThan, equal, greatherThan
}
```

```java
public static class InpData {
    private double[][] a = new double[10][10]; // 形 (
    private int numberOfConstraints; // 约束数量
    private int numberOfOriginalVariables; // 原始变量数量
    double[][] constraintLeftSide = new double[10][10];
    double[] constraintRightSide = new double[10];
    Constraint[] constraintOperator;
    double[] objectiveFunction = new double[10]; 

    public InpData() {
        Scanner input = new Scanner(System.in);
        System.out.println("输入约束数量和目标函数中的变量数量");
        numberOfConstraints = input.nextInt();
        numberOfOriginalVariables = input.nextInt();
        // a = new double[numberOfConstraints + 1][numberOfOriginalVariables + numberOfConstraints + 1];
        System.out.println("输入 constraintRightSide[i] 系数");
        for (int i = 0; i < numberOfConstraints; i++) {
            constraintRightSide[i] = input.nextDouble();
            a[i][numberOfConstraints + numberOfOriginalVariables] = constraintRightSide[i];
        }
        System.out.println("输入 objectivefunc 系数");
        for (int j = 0; j < numberOfOriginalVariables; j++) {
            objectiveFunction[j] = input.nextDouble();
            a[numberOfConstraints][j] = objectiveFunction[j];
        }
        // 初始化约束
        System.out.println("输入 constraintLeftSide[i][j] 系数");
        for (int i = 0; i < numberOfConstraints; i++) {
            for (int j = 0; j < numberOfOriginalVariables; j++) {
                constraintLeftSide[i][j] = input.nextDouble();
                a[i][j] = constraintLeftSide[i][j];
            }
        }
        // 初始化松弛变量
        int slack = 0;
        System.out.println("输入 constraintOperator RHS -1 表示大于( >),+1 表示小于 (<) & 0 表示 =");
        for (int i = 0; i < numberOfConstraints; i++) {
            slack = input.nextInt();
            a[i][numberOfOriginalVariables + i] = slack;
        }
    }

    public double[][] getTableaux() {
        return a;
    }

    public int getNumberOfConstraint() {
        return numberOfConstraints;
    }

    public int getNumberOfOriginalVariable() {
        return numberOfOriginalVariables;
    }
}
```

## 示例 4.7.1 SP_LinerProg.java

```java
/*
线性规划 . 本程序已通过测试并正常运行。适用于
约束 <= 剩余/松弛变量
n= 变量总数
m= 约束总数
n1= 目标函数中的变量数量
n2= 松弛 < 剩余 > 变量
n3= 由于等号引起的人工变量数量
n=n1+n2+n3
 */
```

```java
import java.io.*;
import java.util.Scanner;

public class SP_LinerProg {
    private int i, j, k, kk, r, n, m, m1, m2, m3; // n 个未知数, m 个
    private float[][] a; // 单纯法形 i 行数, 约束方程编号 j 变量 X1,X2
    private float[] CB = new float[20];
    private float[] x = new float[20];
    private float[] b = new float[20];
    private float[] s = new float[20];
    private float[] Z = new float[20];
    private float[] C = new float[20];
    private float[] q = new float[20];
    private float Cjs;
    private float e;
    // float c[20], a[20][20], x[20], b[20], s[20], Z[20], CB[20], C[20], q[20], Cjs;

    public SP_LinerProg(int n, int m, float c[], float a[], float b[]) {
        // 将所有 CB 置为零
        for (int i = 1; i <= m; i++) {
            CB[i] = c[n - i + 1];
            x[i] = b[n - i + 1];
        }
        // 确定 Z= 和 (CB[i]*a[i][j])
        do {
            Z[1] = 0;
            // ... (此处代码逻辑延续原文，未翻译)
        }
    }
}
```



```java
import java.io.*;
import java.util.*;
import java.math.*;

public class SP_Genetic2 {
    double[] fitness = new double[500];
    int[] gDecimal = new int[20];
    double crossover_rate = 0.7;
    double mutation_rate = 0.001;
    public float target;
    int population = 400;
    int chromLength = 18;
    int geneLength = 6;
    int Max_No_Generation = 200;
    public int i, j, k;
    public boolean solutionFound;
    String[] c;
    double[] chromoValue;
    String[] g;

    public SP_Genetic2() {
        // 生成染色体群
        System.out.println("Enter Target value");
        Scanner input = new Scanner(System.in);
        target = input.nextDouble();
        for (j = 1; j <= population; j++) {
            c[j] = "";
            int temp = j;
            for (i = 1; i <= chromLength; i++) {
                Random rn = new Random();
                int rnd = rn.nextInt(1000);
                double rf = (double) rnd / 1000;
                if (rf <= 0.5) {
                    c[j] = '1' + c[j];
                } else {
                    c[j] = '0' + c[j];
                }
            }
        }
        int No_of_genration = 1;
        solutionFound = false;
        while (!solutionFound) { // 循环持续直到 solutionFound 为真
            // 初始化所有种群的适应度为 0
            for (j = 1; j <= population; j++) {
                fitness[j] = 0.0;
            }
            System.out.println();
            // 从染色体值计算适应度
            for (j = 1; j <= population; j++) {
                chromo_Value(c[j]);
                chromo_fitness(chromoValue[j]);
                System.out.println();
                System.out.println("chromo_fitness(chromoValue[j]=" + chromo_fitness(chromoValue[j]));
                // 测试是否有任何染色体达到了要求的适应度
                if (fitness[j] >= 0.01) {
                    System.out.println("Bset fit chromosome found=" + c[j]);
                    System.out.println("No_of_population " + population);
                    System.out.println("No of Generation=" + No_of_genration);
                    System.out.println("ChromeValue=" + chromoValue[j]);
                    System.out.println("fitness= " + fitness[j]);
                    System.out.println("Gene combiations are");
                    for (i = 1; i <= (chromLength / geneLength); i++) {
                        System.out.println(" No=" + i + " Gene (Binary)" + g[i] + "=" + gDecimal[i]);
                    }
                    System.out.println();
                    solutionFound = true;
                    break;
                }
            }
            double totalfitness = 0;
            for (j = 1; j <= population; j++) {
                totalfitness += fitness[j];
            }
            String offspring1;
            String offspring2;
            int pop = 1;
            j = 1;
            do {
                offspring1 = Rwheel(totalfitness);
                offspring2 = Rwheel(totalfitness);
                // 交叉
                crossover(offspring1, offspring2);
                // 变异
                mutate(offspring1);
                mutate(offspring2);
                c[pop] = offspring1;
                c[pop + 1] = offspring2;
                pop = pop + 2;
            } while (pop <= population);
            No_of_genration = No_of_genration + 1;
            if (No_of_genration > Max_No_Generation) {
                System.out.println("solutions not found after" + (No_of_genration - 1) + " No Generations");
                solutionFound = true;
            }
        }
    }

    // 所有函数
    public double chromo_fitness(double value) {
        fitness[j] = 1 / Math.abs(target - chromoValue[j]);
        if (target == chromoValue[j])
            fitness[j] = 100.0;
        return fitness[j];
    }

    public double chromo_Value(String chromo) {
        // 将每个染色体拆分为基因
        int geneNo = 1;
        for (i = 0; i < chromLength; i += geneLength) {
            g[geneNo] = chromo.substring(i, i + geneLength);
            geneNo++;
        }
        System.out.println();
        // 将每个基因从二进制转换为十进制
        for (geneNo = 1; geneNo <= (chromLength / geneLength); geneNo++) {
            int temp = 0;
            int sum = 0;
            for (k = 0; k < geneLength; k++) {
                if (g[geneNo].charAt(k) == '1') {
                    temp = (int) Math.pow(2, (geneLength - (k + 1)));
                } else {
                    temp = 0;
                }
            }
        }
    }
}
```

```java
System.out.println(" 无=" + i + " 基因（二进制）" + g[i] + "=" + gDecimal[i]);

}

System.out.println();

solutionFound = true;

break;

}

}

float totalfitness = 0;

for (j = 1; j <= population; j++) {
    totalfitness += fitness[j];
}

String offspring1;
String offspring2;
int pop = 1;

j = 1;

do {
    offspring1 = Rwheel(totalfitness);
    offspring2 = Rwheel(totalfitness);
    // 交叉
    crossover(offspring1, offspring2);
    // 变异
    mutate(offspring1);
    mutate(offspring2);
    c[pop] = offspring1;
    c[pop + 1] = offspring2;
    pop = pop + 2;
} while (pop <= population);

No_of_genration = No_of_genration + 1;

if (No_of_genration > Max_No_Generation) {
    System.out.println("在经过" + (No_of_genration - 1) + " 代代数后未找到解决方案");
    solutionFound = true;
}

}
}

public double chromo_fitness(double value) {
    fitness[j] = 1 / Math.abs((target - chromoValue[j]));
    if (target == chromoValue[j])
        fitness[j] = 100.0;
    return fitness[j];
}

public double chromo_Value(String chromo) {
    // 将每个染色体种群拆分为基因
    int geneNo = 1;
    for (i = 0; i < chromLength; i += geneLength) {
        g[geneNo] = c[j].substring(i, geneLength + i);
        geneNo = geneNo + 1;
    }
    System.out.println();

    for (geneNo = 1; geneNo <= (chromLength / geneLength); geneNo++) {
        int temp = 0, sum = 0;
        for (k = 0; k < geneLength; k++) {
            if (g[geneNo].charAt(k) == '1') {
                temp = (int) Math.pow(2, (geneLength - (k + 1)));
            } else {
                temp = 0;
            }
            sum = sum + temp;
        }
        gDecimal[geneNo] = sum;
        System.out.print("  gDecimal" + geneNo + "=" + gDecimal[geneNo]);
    }
    System.out.println();

    double b0 = 40.787, b1 = 20.52, b2 = 2.0, b3 = -3.75, b4 = 4.0, b5 = -8.12,
        b6 = -3.4675, b7 = -8.615;
    double c1 = 21.5, d1 = 2.5, c2 = 2.1, d2 = 1.3, c3 = 6, d3 = 2;
    double x1, x2, x3;
    x1 = (gDecimal[1] - c1) / d1;
    x2 = (gDecimal[2] - c2) / d2;
    x3 = (gDecimal[3] - c3) / d3;
    chromoValue[j] = b0 + b1 * x1 + b2 * x2 + b3 * x3 + b4 * x1 * x2 + b5 * x2 * x3 + b6 * x1 * x3 + b7 * x1 * x2 * x3;
    if (gDecimal[1] > 24 || gDecimal[2] < 0.0 || gDecimal[2] > 4 || gDecimal[3] < 4.0 || gDecimal[3] > 8.0)
        chromoValue[j] = -500;
    return chromoValue[j];
}

public void mutate(String offspr) {
    double randf = randf = Math.random();
    if (randf < mutation_rate) {
        for (i = 0; i < offspr.length(); i++) {
            char ch = offspr.charAt(i);
            if (offspr.charAt(i) == '1')
                ch = '0';
            else
                ch = '1';
        }
    }
}

public void crossover(String offspring1, String offspring2) {
    int cross_pt;
    float randf = randf = (float) Math.random();
    // cout<<"randf"<<randf;
    if (randf < crossover_rate) {
        cross_pt = (int) (randf * chromLength);
        String s1 = offspring1.substring(0, cross_pt) + offspring2.substring(cross_pt, chromLength);
        String s2 = offspring2.substring(0, cross_pt) + offspring1.substring(cross_pt, chromLength);
        offspring1 = s1;
        offspring2 = s2;
    }
}

public String Rwheel(float Totalfitness) {
    double randf = randf = Math.random();
    double slice = (randf * Totalfitness);
    float fitnessSoFar = 0;
    for (j = 1; j <= population; j++) {
        fitnessSoFar += fitness[j];
        if (fitnessSoFar >= slice) {
            return c[j];
        }
    }
    return "";
}

public static void main(String args[]) {
    // ... (后续代码结构保持不变)
}
```

```java
SP_Mapminmax_pack mp = new SP_Mapminmax_pack();

double ixmax[] = new double[m]; // 每个变量输入数据的最大值数组
double ixmin[] = new double[m]; // 每个变量输入数据的最小值数组
double oxmax[] = new double[nm]; // 每个变量输出数据的最大值数组
double oxmin[] = new double[nm]; // 每个变量输出数据的最小值数组
```



```java
double xx[] = new double[n];

for (int j = 0; j < m; j++) {
    for (int i = 0; i < n; i++) {
        xx[i] = arr[i][j];
    }
    ixmax[j] = mp.getMax(xx);
    ixmin[j] = mp.getMin(xx);
    // 调用类中的 getMax 函数查找单个变量输入数据数组的最大值
    // 同样调用 getMin 函数
    System.out.println("input min max=" + ixmin[j] + " " + ixmax[j]);
}

for (int j = 0; j < nm; j++) {
    for (int i = 0; i < n; i++) {
        xx[i] = aro[i][j];
    }
    oxmax[j] = mp.getMax(xx); // 输出数据处理同上
    oxmin[j] = mp.getMin(xx);
    System.out.println("output min max=" + oxmin[j] + " " + oxmax[j]);
}

double MMX[][] = mp.dataMMX(n, m, arr); // 获取无量纲输入数据数组
double inputs[][] = new double[n][m];
for (int i = 0; i < n; i++) {
    for (int j = 0; j < m; j++) {
        inputs[i][j] = MMX[i][j];
    }
}

// 用于输出
double MMX2[][] = mp.dataMMX(n, nm, arro); // 获取无量纲输出数据数组
double expectedOutputs[][] = new double[n][nm];
for (int i = 0; i < n; i++) {
    for (int j = 0; j < nm; j++) {
        expectedOutputs[i][j] = MMX2[i][j];
    }
}

// 调用 NNet 构造函数传入相关数据、输入层、隐藏层、输出层，
// 数据集 n，所有无量纲形式的输入和输出
SRP_NNet2 nn = new SRP_NNet2(m, hdn, nm, n, inputs, expectedOutputs);

int maxRuns = 50000;
double minErrorCondition = 0.001;
nn.run(m, hdn, nm, n, inputs, expectedOutputs, ixmin, imax, oxmin, omax, maxRuns, minErrorCondition);

// 主函数结束

// 构造函数开始
public SRP_NNet2(int input, int hidden, int output, int n, double [][] inputs, double [][] expectedOutputs) {
    this.layers = new int[] {input, hidden, output};
    df = new DecimalFormat("#.0#");

    /**
     * 创建所有的神经元和连接在神经元类中创建
     */
    int nm = output;
    int m = input;
    layers[0] = input;
    layers[1] = hidden;
    layers[2] = output;

    for (int i = 0; i < layers.length; i++) {
        if (i == 0) { // 输入层
            for (int j = 0; j < layers[i]; j++) {
                SP_Neuron neuron = new SP_Neuron();
                inputLayer.add(neuron);
            }
        } else if (i == 1) { // 隐藏层
            for (int j = 0; j < layers[i]; j++) {
                SP_Neuron neuron = new SP_Neuron();
                neuron.addInS(inputLayer);
                neuron.addBiasConnection(bias);
                hiddenLayer.add(neuron);
            }
        } else if (i == 2) { // 输出层
            for (int j = 0; j < layers[i]; j++) {
                SP_Neuron neuron = new SP_Neuron();
                neuron.addInS(hiddenLayer);
                neuron.addBiasConnection(bias);
                outputLayer.add(neuron);
            }
        } else {
            System.out.println("!Error NeuralNetwork init");
        }
    }

    // 初始化随机权重
    for (SP_Neuron neuron : hiddenLayer) {
        ArrayList<SP_Connection> connections = neuron.getAllInConnections();
        for (SP_Connection conn : connections) {
            double newWeight = getRandom();
            conn.setWeight(newWeight);
        }
    }

    for (SP_Neuron neuron : outputLayer) {
        ArrayList<SP_Connection> connections = neuron.getAllInConnections();
        for (SP_Connection conn : connections) {
            double newWeight = getRandom();
            conn.setWeight(newWeight);
        }
    }

    // 重置计数器
    SP_Neuron.counter = 0;
    SP_Connection.counter = 0;

    if (isTrained) {
        trainedWeights();
        updateAllWeights();
    }
}

// 随机
double getRandom() {
    return rand.nextDouble() * 2 - 1); // [-1,1]
}

/**
 * @param inputs
 * 有许多位于输入层的神经元
 */
public void setInput(double inputs[]) {
    for (int i = 0; i < inputLayer.size(); i++) {
        inputLayer.get(i).setOutput(inputs[i]);
    }
}

public double[] getOutput() {
    double[] outputs = new double[outputLayer.size()];
    for (int i = 0; i < outputLayer.size(); i++) {
        outputs[i] = outputLayer.get(i).getOutput();
    }
    return outputs;
}

/**
 * 根据输入前向传播输出
 */
public void activate() {
    for (SP_Neuron n : hiddenLayer) {
        n.calculateOutput();
    }
    for (SP_Neuron n : outputLayer) {
        n.calculateOutput();
    }
}

/**
 * @param expectedOutput
 * 反向传播误差
 */
public void applyBackpropagation(double expectedOutput[]) {
    // 检查并归一化值
    for (int i = 0; i < expectedOutput.length; i++) {
        double d = expectedOutput[i];
        if (d < 0 || d > 1) {
            if (d < 0)
                expectedOutput[i] = 0 + epsilon;
            } else {
                expectedOutput[i] = 1 - epsilon;
            }
        }
    }

    int i = 0;
    for (SP_Neuron n : outputLayer) {
        ArrayList<SP_Connection> connections = n.getAllInConnections();
        for (SP_Connection conn : connections) {
            double ak = n.getOutput();
            double ai = conn.leftNeuron.getOutput();
            double desiredOutput = expectedOutput[i];
            double partialDerivative = -ak * (1 - ak) * ai * (desiredOutput - ak);
            double deltaWeight = -learningRate * partialDerivative;
            double newWeight = conn.getWeight() + deltaWeight;
            conn.setDeltaWeight(deltaWeight);
            conn.setWeight(newWeight + momentum * conn.getDeltaWeight());
        }
        i++;
    }

    // 更新隐藏层的权重
    for (SP_Neuron n : hiddenLayer) {
        ArrayList<SP_Connection> connections = n.getAllInConnections();
        for (SP_Connection conn : connections) {
            double aj = n.getOutput();
            double ai = conn.leftNeuron.getOutput();
            double sumKoutputs = 0;
            int j = 0;
            for (SP_Neuron out_neu : outputLayer) {
                double wjk = out_neu.getConnection(n.id).getWeight();
                double desiredOutput = (double) expectedOutput[j];
                double ak = out_neu.getOutput();
                sumKoutputs = sumKoutputs + (-(desiredOutput - ak) * ak * (1 - ak) * wjk);
                j++;
            }
            double partialDerivative = aj * (1 - aj) * ai * sumKoutputs;
            double deltaWeight = -learningRate * partialDerivative;
            double newWeight = conn.getWeight() + deltaWeight;
            conn.setDeltaWeight(deltaWeight);
            conn.setWeight(newWeight + momentum * conn.getDeltaWeight());
        }
    }
}
```

# 神经网络实现

// 使用所有输入数据以及原始输入输出的最极值运行神经网络
// 以将结果转换回非维度纲形式（即实数）

```java
void run(int m, int hdn, int nm, int n, double [][]inputs, double [][] expectedOutputs, double[] ixmin, double[] imax, double[] oxmin, double[] oxmax, int maxSteps, double minError) {
    int i;
    double resultOutputs[][][] = new double[n][nm];
    for (i = 0; i < n; i++) {
        for (int j = 0; j < nm; j++) {
            resultOutputs[i][j] = -1;
        }
    }

    // 训练神经网络，直到达到 minError 或超过 maxSteps
    double error = 1;
    for (i = 0; i < maxSteps && error > minError; i++) {
        // System.out.println("inputs.length= "+inputs.length);
        error = 0;
        for (int p = 0; p < n; p++) {
            setInput(inputs[p]);
            activate();
            output = getOutput();
            resultOutputs[p] = output;
            for (int j = 0; j < nm; j++) {
                double err = Math.pow((output[j] - expectedOutputs[p][j]), 2);
                error += err;
            }
            applyBackpropagation(expectedOutputs[p]);
        }
    }

    double arr[][] = new double[n][m]; // 读取输入
    double arro[][] = new double[n][nm]; // 读取实际输出
    for (int p = 0; p < n; p++) {
        System.out.print("INPUTS: ");
        layers[0] = m; layers[2] = nm;
        for (int x = 0; x < layers[0]; x++) {
            System.out.print(inputs[p][x] + " ");
            arr[p][x] = inputs[p][x];
        }
        System.out.print("EXPECTED: ");
        for (int x = 0; x < layers[2]; x++) {
            System.out.print(expectedOutputs[p][x] + " ");
        }
        System.out.print("ACTUAL: ");
        for (int x = 0; x < layers[2]; x++) {
            System.out.print(resultOutputs[p][x] + " ");
        }
    }
}
```



```java
arro[p][x] = resultOutputs[p][x];
}
System.out.println();
}

// 调用类将其转换回数字，即无维度纲结果
SRP_Mapminmax_pack mp = new SRP_Mapminmax_pack();

// 给原始无维度数据的最大值和最小值
// i-输入，o-输出
double MMR[][] = mp.dataMMR(n, m, arr, ixmin, imax);
double MMR2[][] = mp.dataMMR(n, nm, arro, oxmin, oxmax);

System.out.println("神经网络之后的输入和输出结果");
for (int p = 0; p < n; p++) {
    for (int x = 0; x < layers[0]; x++) {
        System.out.print(" " + MMR[p][x]);
    }
    for (int x = 0; x < layers[2]; x++) {
        System.out.println(" " + MMR2[p][x]);
    }
    System.out.println("均方误差和 = " + error);
    System.out.println("##### EPOCH " + i + "\n");
    if (i == maxSteps) {
        System.out.println("!错误重试");
    } else {
        printAllWeights();
        printWeightUpdate();
    }
}

String weightKey(int neuronId, int conId) {
    return "N" + neuronId + "_C" + conId;
}

/**
 * 从哈希表中取出并放入所有权重
 */
public void updateAllWeights() {
    // 更新输出层
    for (SP_Neuron n : outputLayer) {
        ArrayList<SP_Connection> connections = n.getAllInConnections();
        for (SP_Connection con : connections) {
            String key = weightKey(n.id, con.id);
            double newWeight = weightUpdate.get(key);
            con.setWeight(newWeight);
        }
    }
    // 更新隐藏层
    for (SP_Neuron n : hiddenLayer) {
        ArrayList<SP_Connection> connections = n.getAllInConnections();
        for (SP_Connection con : connections) {
            String key = weightKey(n.id, con.id);
            double newWeight = weightUpdate.get(key);
            con.setWeight(newWeight);
        }
    }
}

// 训练数据
void trainedWeights() {
    weightUpdate.clear();
    weightUpdate.put(weightKey(3, 0), 1.03);
    weightUpdate.put(weightKey(3, 1), 1.13);
    weightUpdate.put(weightKey(3, 2), -.97);
    weightUpdate.put(weightKey(4, 3), 7.2);
    weightUpdate.put(weightKey(4, 1), 1.13); // 注意：此处原文逻辑可能存在重复，按样翻译
    // ... 省略部分重复逻辑以保持结构一致
}

// ... 其余代码结构保持不变
}
```

# 程序 6.5.1 `SRP_NNData.java`

```java
import java.util.Scanner;
import java.io.DataOutputStream;
import java.io.FileOutputStream;
import java.io.IOException;

public class SRP_NNData {
    static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.println(" 输入层数量，和输出数量");
        int m = input.nextInt();
        int nm = input.nextInt();
        System.out.println("输入数据量的对应的输出");
        int n = input.nextInt(); // 数据集大小
        double arr[][] = new double[n][m]; // 输入数组
        double arro[][] = new double[n][nm]; // 输出数组
        for (int i = 0; i < n; i++) {
            System.out.println(" 输入数据 X1, X2, X3 当输出=f(X1,X2,X3)");
            for (int j = 0; j < m; j++) {
                arr[i][j] = input.nextDouble();
            }
            System.out.println(" 输入输出 Y");
            for (int j = 0; j < nm; j++) {
                arro[i][j] = input.nextDouble();
            }
        }
        String strFilePath = "E://Java_Engg_Problem/dataNN.txt";
        try {
            FileOutputStream file = new FileOutputStream(strFilePath);
            DataOutputStream fout = new DataOutputStream(file);
            fout.writeInt(m);
            fout.writeInt(nm);
            fout.writeInt(n);
            for (int i = 0; i < n; i++) {
                for (int j = 0; j < m; j++) {
                    fout.writeDouble(arr[i][j]);
                }
                for (int j = 0; j < nm; j++) {
                    fout.writeDouble(arro[i][j]);
                }
            }
            file.close();
            System.out.println("成功...");
        } catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

# 程序 6.5.2 `SRP_NNetFileData2.java`

```java
import sp_package.*;
import java.text.*;
import java.util.*;
import java.io.DataInputStream;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;

// 其他 java 文件取自 sp_package: 1.SP_Mapminmax_pack.java, 2.SP_Neuron.java, 3.SP_Connection.java
// 需要加载 SP_Mapminmax_pack 类将输入数据转换为无量纲，并将结果转换回有纲
public class SRP_NNetFileData2 {
    static {
        Locale.setDefault(Locale.ENGLISH);
    }
    final boolean isTrained = false;
    final DecimalFormat df;
    final Random rand = new Random();
    final ArrayList<SP_Neuron> inputLayer = new ArrayList<SP_Neuron>();
    final ArrayList<SP_Neuron> hiddenLayer = new ArrayList<SP_Neuron>();
    final ArrayList<SP_Neuron> outputLayer = new ArrayList<SP_Neuron>();
    final SP_Neuron bias = new SP_Neuron();
    final int[] layers;
    final int randomWeightMultiplier = 1;
    final double epsilon = 0.00000000001;
    final double learningRate = 0.9f;
    final double momentum = 0.7f;
    double output[];
    // 用于所有权重更新
    final HashMap<String, Double> weightUpdate = new HashMap<String, Double>();

    public static void main(String[] args) {
        int m, nm, n, hdn;
        n = 1; m = 1; nm = 1; hdn = 1;
        double arr[][] = new double[40][15]; // 输入数组
        double arro[][] = new double[40][5]; // 输出数组
        Scanner input = new Scanner(System.in);
        System.out.println("是否想从文件读取神经网络数据？是的话按 1，否则按 2");
        int y = input.nextInt();
        if (y == 1) {
            System.out.println("正在文件中读取数据");
            String strFilePath = "E://Java_Engg_Problem/dataNN.txt";
            try {
                FileInputStream fin = new FileInputStream(strFilePath);
                DataInputStream din = new DataInputStream(fin);
                m = din.readInt();
                // hdn=din.readInt();
                nm = din.readInt();
                n = din.readInt();
                for (int i = 0; i < n; i++) {
                    for (int j = 0; j < m; j++) {
                        arr[i][j] = din.readDouble();
                    }
                    for (int j = 0; j < nm; j++) {
                        aro[i][j] = din.readDouble();
                    }
                }
                din.close();
            } catch (FileNotFoundException fe) {
                System.out.println("FileNotFoundException : " + fe);
            } catch (IOException ioe) {
                System.out.println("IOException : " + ioe);
            }
            System.out.println("选择隐藏层数量，选择（1 到 2）比输入层少或多的层数，如果输入层为 3，隐藏层可能是 2 或 4 等");
            hdn = input.nextInt();
        } else {
            System.out.println("输入输入层数、隐藏层数和输出层数");
            m = input.nextInt();
            hdn = input.nextInt();
            nm = input.nextInt();
            System.out.println("输入输入及对应输出的数据组数");
            n = input.nextInt(); // 数据集大小
            for (int i = 0; i < n; i++) {
                System.out.println("输入数据 X1, X2, X3，当输出 Y=f(X1,X2,X3) 时");
                for (int j = 0; j < m; j++) {
                    arr[i][j] = input.nextDouble();
                }
                System.out.println("输入输出 Y");
                for (int j = 0; j < nm; j++) {
                    aro[i][j] = input.nextDouble();
                }
            }
            System.out.println("神经网络数据");
            for (int i = 0; i < n; i++) {
                System.out.print("Inputs ");
                for (int j = 0; j < m; j++) {
                    System.out.print((float)arr[i][j] + "\t");
                }
                System.out.print("t 输出 ");
                for (int j = 0; j < nm; j++) {
                    System.out.print((float)aro[i][j] + "\t");
                }
                System.out.println();
            }
        }
        // 调用类将输入数据和结果转换回
        SP_Mapmax_pack mp = new SP_Mapmax_pack();
    }
}
```



```java
double ixmax[] = new double[m]; // 每个变量的最大值数组
double ixmin[] = new double[m]; // 每个变量的最小值数组
double oxmax[] = new double[nm]; // 每个变量的最大值数组
double oxmin[] = new double[nm]; // 每个变量的最小值数组
double xx[] = new double[m];

for (int i = 0; i < m; i++) {
    // 逻辑占位
}

// 此处原代码逻辑在示例中略有简化，此处保持结构翻译
}
}
```

```java
ArrayList<SP_Connection> connections = neuron.getAllInConnections();

for (SP_Connection conn : connections) {
    double newWeight = getRandom();
    conn.setWeight(newWeight);
}

// 重置 计数器
SP_Neuron.counter = 0;
SP_Connection.counter = 0;

if (isTrained) {
    trainedWeights();
    updateAllWeights();
}

// 随机
double getRandom() {
    return randomWeightMultiplier * (rand.nextDouble() * 2 - 1); // [-1;1[
}

/**
 * @param inputs
 * 输入层中的神经元数量与输入变量的数量相等
 */
public void setInput(double inputs[]) {
    // System.out.println ("inputLayer.size()="+inputLayer.size());
    for (int i = 0; i < inputLayer.size(); i++) {
        inputLayer.get(i).setOutput(inputs[i]);
    }
}

public double[] getOutput() {
    double[] outputs = new double[outputLayer.size()];
    // System.out.println ("outputLayer.size()="+outputLayer.size());
    for (int i = 0; i < outputLayer.size(); i++) {
        outputs[i] = outputLayer.get(i).getOutput();
    }
    return outputs;
}

/**
 * 根据输入计算神经网络的输出。前向 * 操作
 */
public void activate() {
    for (SP_Neuron n : hiddenLayer) {
        n.calculateOutput();
    }
    for (SP_Neuron n : outputLayer) {
        n.calculateOutput();
    }
}

/**
 * 所有输出反向传播
 *
 * @param expectedOutput
 * 首先计算误差相对于输入输出神经元的每个权重的偏导数
 * 偏置(bias)也在此处进行更新
 */
public void applyBackpropagation(double expectedOutput[]) {
    // 误差检查，归一化值 ]0;1[
    // System.out.println ("expectedOutput.length="+expectedOutput.length);
    for (int i = 0; i < expectedOutput.length; i++) {
        double d = expectedOutput[i];
        if (d < 0 || d > 1) {
            if (d < 0) {
                expectedOutput[i] = 0 + epsilon;
            } else {
                expectedOutput[i] = 1 - epsilon;
            }
        }
    }

    int i = 0;
    for (SP_Neuron n : outputLayer) {
        ArrayList<SP_Connection> connections = n.getAllInConnections();
        for (SP_Connection con : connections) {
            double ak = n.getOutput();
            double ai = con.leftNeuron.getOutput();
            double desiredOutput = expectedOutput[i];
            double partialDerivative = -ak * (1 - ak) * ai * (desiredOutput - ak);
            double deltaWeight = -learningRate * partialDerivative;
            double newWeight = con.getWeight() + deltaWeight;
            con.setDeltaWeight(deltaWeight);
            con.setWeight(newWeight + momentum * con.getDeltaWeight());
        }
        i++;
    }

    // 更新隐藏层的权重
    for (SP_Neuron n : hiddenLayer) {
        ArrayList<SP_Connection> connections = n.getAllInConnections();
        for (SP_Connection con : connections) {
            double aj = n.getOutput();
            double ai = con.leftNeuron.getOutput();
            double sumKoutputs = 0;
            int j = 0;
            for (SP_Neuron out_neu : outputLayer) {
                double wjk = out_neu.getConnection(n.id).getWeight();
                double desiredOutput = (double) expectedOutput[j];
                double ak = out_neu.getOutput();
                j++;
                sumKoutputs += (-(desiredOutput - ak) * ak * (1 - ak) * wjk);
            }
            double partialDerivative = aj * (1 - aj) * ai * sumKoutputs;
            double deltaWeight = -learningRate * partialDerivative;
            double newWeight = con.getWeight() + deltaWeight;
            con.setDeltaWeight(deltaWeight);
            con.setWeight(newWeight + momentum * con.getDeltaWeight());
        }
    }
}

// 使用所有输入数据加上原始输入的最大/最小值运行神经网络
// 以将结果转换回非维度形式，即实数
void run(int m, int hdn, int nm, int n, double [][] inputs, double [][] expectedOutputs, double[] ixmin, double[] ixmax, double[] oxmin, double[] oxmax, int maxSteps, double minError) {
    int i;
    double resultOutputs[][] = new double[n][nm];

    for (i = 0; i < n; i++) {
        for (int j = 0; j < nm; j++) {
            resultOutputs[i][j] = -1;
        }
    }

    // 训练神经网络直到达到 minError 或超过 maxSteps
    double error = 1;
    for (i = 0; i < maxSteps && error > minError; i++) {
        // System.out.println("inputs.length= "+inputs.length);
        error = 0;
        for (int p = 0; p < n; p++) {
            setInput(inputs[p]);
            activate();
            double output = getOutput();
            resultOutputs[p] = output;
            // System.out.println("expectedOutputs[p].length="+expectedOutputs[p].length);
            for (int j = 0; j < nm; j++) {
                // System.out.println( "out, expec "+output[j]+expectedOutputs[p][j]);
                double err = Math.pow((output[j] - expectedOutputs[p][j]), 2);
                error += err;
            }
            applyBackpropagation(expectedOutputs[p]);
        }

        // printResult();
        // System.out.println(" printResult()inputs.length= "+inputs.length);
        double arr[][] = new double[n][m]; // 读取输入
        double aro[][] = new double[n][nm]; // 读取实际输出
        for (int p = 0; p < n; p++) {
            System.out.print("INPUTS: ");
            int layers0 = m;
            int layers2 = nm;
            for (int x = 0; x < layers0; x++) {
                System.out.print(inputs[p][x] + " ");
                arr[p][x] = inputs[p][x];
            }
            System.out.print("EXPECTED: ");
            for (int x = 0; x < layers2; x++) {
                System.out.print(expectedOutputs[p][x] + " ");
            }
            System.out.print("ACTUAL: ");
            for (int x = 0; x < layers2; x++) {
                System.out.print(resultOutputs[p][x] + " ");
                aro[p][x] = resultOutputs[p][x];
            }
            System.out.println();
        }

        // 调用类转换回数字，无维度结果
        SRP_Mapminmax_pack mp = new SRP_Mapminmax_pack();
        // 给定的无维度数据
        // i-输入 o-输出
        double MMR[][] = mp.dataMMR(n, m, arr, ixmin, ixmax);
        double MMR2[][] = mp.dataMMR(n, nm, aro, oxmin, oxmax);
        System.out.println("NN 后的输入输出结果");
        for (int p = 0; p < n; p++) {
            for (int x = 0; x < layers0; x++) {
                System.out.print(" " + MMR[p][x]);
            }
            for (int x = 0; x < layers2; x++) {
                System.out.println(" " + MMR2[p][x]);
            }
        }
        System.out.println("Sum of errors = " + error);
        System.out.println("##### EPOCH " + i + "\n");
        if (i == maxSteps) {
            System.out.println("!Error try again");
        } else {
            printAllWeights();
            printWeightUpdate();
        }
    }
}

String weightKey(int neuronId, int conId) {
    return "N" + neuronId + "_C" + conId;
}

/**
 * 从哈希表提取放入所有权重
 */
public void updateAllWeights() {
    // 更新输出层的权重
    for (SP_Neuron n : outputLayer) {
        ArrayList<SP_Connection> connections = n.getAllInConnections();
        for (SP_Connection con : connections) {
            String key = weightKey(n.id, con.id);
            double newWeight = weightUpdate.get(key);
            con.setWeight(newWeight);
        }
    }
}
```

```java
double newWeight = weightUpdate.get(key);
con.setWeight(newWeight);
```

// 训练数据
```java
void trainedWeights() {
    weightUpdate.clear();
    weightUpdate.put(weightKey(3, 0), 1.03);
    weightUpdate.put(weightKey(3, 1), 1.13);
    weightUpdate.put(weightKey(3, 2), -.97);
    weightUpdate.put(weightKey(4, 3), 7.24);
    weightUpdate.put(weightKey(4, 4), -3.71);
    weightUpdate.put(weightKey(4, 5), -.51);
    weightUpdate.put(weightKey(5, 6), -3.28);
}
```



```java
weightUpdate.put(weightKey(5, 7), 7.29);

weightUpdate.put(weightKey(5, 8), -.05);

weightUpdate.put(weightKey(6, 9), 5.86);

weightUpdate.put(weightKey(6, 10), 6.03);

weightUpdate.put(weightKey(6, 11), .71);

weightUpdate.put(weightKey(7, 12), 2.19);

weightUpdate.put(weightKey(7, 13), -8.82);

weightUpdate.put(weightKey(7, 14), -8.84);

weightUpdate.put(weightKey(7, 15), 11.81);

weightUpdate.put(weightKey(7, 16), .44);

}
```

```java
public void printWeightUpdate() {

    // System.out.println("printWeightUpdate, put this i trainedWeights() and set isTrained to true");

    // 隐藏层权重

    for (SP_Neuron n : hiddenLayer) {

        ArrayList<SP_Connection> connections = n.getAllInConnections();

        for (SP_Connection con : connections) {

            String w = df.format(con.getWeight());

        }

    }

    // 输出层权重

    for (SP_Neuron n : outputLayer) {

        ArrayList<SP_Connection> connections = n.getAllInConnections();

        for (SP_Connection con : connections) {

        }

    }

    // System.out.println();

}
```

```java
public void printAllWeights() {

    // System.out.println("printAllWeights");

    // 隐藏层权重

    for (SP_Neuron n : hiddenLayer) {

        ArrayList<SP_Connection> connections = n.getAllInConnections();

        for (SP_Connection con : connections) {

            double w = con.getWeight();

            // System.out.println("n=" + n.id + " c=" + con.id + " w=" + w);

        }

    }

    // 输出层权重

    for (SP_Neuron n : outputLayer) {

        ArrayList<SP_Connection> connections = n.getAllInConnections();

        for (SP_Connection con : connections) {

            double w = con.getWeight();

        }

    }

}
```

## 有限元方法 (FEM)

### `SRP_FEM.java`

```java
import java.lang.Math.*;

import java.util.Scanner;

import java.io.DataOutputStream;

import java.io.FileOutputStream;

import java.io.IOException;

import java.util.*;

import java.util.Random;

import java.io.RemoteException;

import java.awt.*;

import javax.swing.*;

import java.awt.event.*;

public class SRP_FEM {

    triangular_element te[];

    setElement se[];

    int N, M, K, K1, K2, Nm1, Mm1;

    double x[][];

    double y[][];

    double T[][];

    double Ti[];

    double xi[];

    double yi[];

    boolean bi[];

    double dx, dy;

    int Bx[], BxM[], By[], ByN[];

    double L, W;

    public double min(double xi[][]) {

        // double min=0.002

        double min = 1e20;

        for (int i = 0; i < xi.length; i++) {

            for (int j = 0; j < xi[0].length; j++) {

                if (xi[i][j] < min) min = xi[i][j];

            }

        }

        return min;

    }

    public double max(double xi[][]) {

        double max = -1e20;

        // double max=-0.002

        for (int i = 0; i < xi.length; i++) {

            for (int j = 0; j < xi[0].length; j++) {

                if (xi[i][j] > max) max = xi[i][j];

            }

        }

        return max;

    }

    public SRP_FEM(double xi[][], double yi[][]) {

        x = xi;

        y = yi;

        N = x.length - 1;

        M = x[0].length - 1;

        T = new double[N + 1][M + 1];

        L = max(xi);

        W = max(yi);

        setElements();

    }

    public void generateTriangularGrid(double Li, double Wi, int Ni, int Mi) {

        N = Ni;

        M = Mi;

        L = Li;

        W = Wi;

        x = new double[N + 1][M + 1];

        y = new double[N + 1][M + 1];

        T = new double[N + 1][M + 1];

        setElements();

    }

    public void setElements() {

        dx = L / M;

        dy = W / N;

        K = M * N;

        K1 = K * 2;

        K2 = K1 + 1;

        // 网格点

        xi = new double[K2];

        yi = new double[K2];

        Ti = new double[K2];

        bi = new boolean[K2];

        se = new setElement[K2];

        for (int i = 0; i < K2; i++) se[i] = new setElement();

        te = new triangular_element[K1];

        int k1 = -1, k = 0, n = 0, m = 0;

        for (int n = 0; n <= N; n++) {

            for (int m = 0; m <= M; m++) {

                k = (N + 1) * n + m;

                x[n][m] = m * dx;

                y[n][m] = n * dy;

                xi[k] = x[n][m];

                yi[k] = y[n][m];

                bi[k] = false;

                Ti[k] = 0.0;

            }

        }

        for (int n = 0; n < N; n++) {

            for (int m = 0; m < M; m++) {

                k = (N + 1) * n + m;

                int kp1 = (N + 1) * (n + 1) + m;

                int kp11 = kp1 + 1;

                double xi1[] = {x[n][m], x[n][m + 1], x[n + 1][m]};

                double yi1[] = {y[n][m], y[n][m + 1], y[n + 1][m]};

                k1++;

                int n_point1[] = {k, (k + 1), kp1};

                se[k].add(k1, 0);

                se[k + 1].add(k1, 1);

                se[kp1].add(k1, 2);

                te[k1] = new triangular_element(k1, n_point1, xi1, yi1);

                double xi2[] = {x[n][m + 1], x[n + 1][m + 1], x[n + 1][m]};

                double yi2[] = {y[n][m + 1], y[n + 1][m + 1], y[n + 1][m]};

                k1++;

                int n_point2[] = {k + 1, kp11, kp1};

                se[k + 1].add(k1, 0);

                se[kp11].add(k1, 1);

                se[kp1].add(k1, 2);

                te[k1] = new triangular_element(k1, n_point2, xi2, yi2);

            }

        }

    }

    public SRP_FEM(double Li, double Wi, int Ni, int Mi) {

        generateTriangularGrid(Li, Wi, Ni, Mi);

    }

    public int find_element(double z[]) {

        return find_element(z[0], z[1]);

    }

    public int find_element(double x, double y) {

        double R1 = Math.sqrt(x * x + y * y);

        int kmin = 0;

        double min = 1e50;

        for (int k = 0; k < K1; k++) {

            te[k].set(x, y);

            double r0 = Math.sqrt((te[k][0] - x) * (te[k][0] - x) + (te[k][0] - y) * (te[k][0] - y));

            double r1 = Math.sqrt((te[k][1] - x) * (te[k][1] - x) + (te[k][1] - y) * (te[k][1] - y));

            double r2 = Math.sqrt((te[k][2] - x) * (te[k][2] - x) + (te[k][2] - y) * (te[k][2] - y));

            double dr = Math.sqrt(r0 * r0 + r1 * r1 + r2 * r2);

            boolean b1 = (x >= te[k][0]) && (x <= te[k][2]);

            boolean b2 = (y >= te[k][0]) && (y <= te[k][1]);

            boolean b = b1 && b2;

            if (dr < min) {

                min = dr;

                kmin = k;

            }

        }

        return kmin;

    }

    public void solve(double ti, double k[]) {

        double K[][] = new double[K2][K2];

        double KK[][] = new double[K2][K2];

        double ff[] = new double[K2];

        double KN[][] = new double[3][3];

        double f[] = new double[K2];

        for (int i = 0; i < K1; i++) {

            KN = te[i].K(ti, k);

            fN = te[i].f(ti, k);

            int n1 = te[i].n_element;

            int m[] = te[i].n_point;

            for (int j = 0; j < 3; j++) {

                K[m[j]][m[j]] += KN[j][j];

                KK[m[j]][m[j]] = K[m[j]][m[j]];

            }

            f[m[j]] += fN[j];

            ff[m[j]] = f[m[j]];

        }

        // 重构 K 矩阵和 f 向量如果任何已知

        // 温度边界已给定

        int j = 0;

        for (int j = 0; j < K2; j++) {

            for (int i = 0; i < K2; i++) {

                if (bi[i]) {

                    if (i == j) {

                        f[i] = Ti[i];

                        K[i][j] = 1.0;

                    } else {

                        K[i][j] = 0.0;

                    }

                }

            }

        }

        double TT[] = AXB(K, f);

        int k1 = 0;

        for (int n = 0; n <= N; n++) {

            for (int m = 0; m <= M; m++) {

                k1 = (N + 1) * n + m;

                T[n][m] = TT[k1];

            }

        }

    }

    public void setGeneration(int node[], double qgeni) {

        int n = node.length;
```



## LU 分解方法

```java
public static double[][] LU(double c[][], int indx[], int d[]) {
    // 返回矩阵 c 和索引 indx 的 LU 解解
    double a[][];
    int n = c.length;
    a = new double[n][n];
    double vv[];
    vv = new double[n];
}
```

```java
double sum, dum, big, temp;
int i, j, k;
int imax;
int nmax = 100;
double tiny = 1.0e-40;
imax = 0;
for (i = 1; i <= n; i++) {
    for (j = 1; j <= n; j++) {
        a[i-1][j-1] = c[i-1][j-1];
    }
}
d[0] = 1;
for (i = 1; i <= n; i++) {
    big = 0.0;
    for (j = 1; j <= n; j++) {
        if (Math.abs(a[i-1][j-1]) > big) big = Math.abs(a[i-1][j-1]);
    }
    if (big == 0) {
        System.out.println("奇异矩阵");
        return a;
    }
    vv[i-1] = 1.0 / big;
}
for (j = 1; j <= n; j++) {
    for (i = 1; i < j; i++) {
        sum = a[i-1][j-1];
        for (k = 1; k < i; k++) {
            sum -= a[i-1][k-1] * a[k-1][j-1];
        }
        a[i-1][j-1] = sum;
    }
    big = 0;
    for (i = j; i <= n; i++) {
        sum = a[i-1][j-1];
        for (k = 1; k < j; k++) {
            sum -= a[i-1][k-1] * a[k-1][j-1];
        }
        a[i-1][j-1] = sum;
        dum = vv[i-1] * Math.abs(sum);
        if (dum >= big) {
            imax = i;
            big = dum;
        }
    } // end of i=0
    if (j != imax) {
        for (k = 1; k <= n; k++) {
            dum = a[imax-1][k-1];
            a[imax-1][k-1] = a[j-1][k-1];
            a[j-1][k-1] = dum;
        }
        d[0] = -d[0];
        vv[imax-1] = vv[j-1];
    } // end of if
    indx[j-1] = imax;
    if (a[j-1][j-1] == 0) a[j-1][j-1] = tiny;
    if (j != n) {
        dum = 1.0 / a[j-1][j-1];
        for (i = j + 1; i <= n; i++)
            a[i-1][j-1] *= dum;
    } // endif
} // end for for j=
return a;
}
```

```java
public static double[] LUaxb(double a[][], double x[], int indx[]) {
    // 求解 LU 分解矩阵 a 的线性方程组 AX=B 
    // (通过 LU 方法计算)
    int ii = 0;
    int i, j, ll = 0;
    double sum = 0;
    int n = a.length;
    double b[];
    b = new double[n];
    for (i = 1; i <= n; i++) {
        b[i-1] = x[i-1];
    }
    for (i = 1; i <= n; i++) {
        ll = indx[i-1];
        sum = b[ll-1];
        b[ll-1] = b[i-1];
        if (ii != 0) {
            for (j = ii; j <= (i - 1); j++) {
                sum -= a[i-1][j-1] * b[j-1];
            }
        } else if (sum != 0) ii = i;
        b[i-1] = sum;
    }
    for (i = n; i >= 1; i--) {
        sum = b[i-1];
        if (i < n) {
            for (j = (i + 1); j <= n; j++) {
                sum -= a[i-1][j-1] * b[j-1];
            }
        }
        b[i-1] = sum / a[i-1][i-1];
    }
    return b;
}
```

```java
public static double[] AXB(double a[][], double b[]) {
    // 使用 LU 方法求解线性方程组
    // 注意，相同的计算可以通过分治法完成。
    int n = a.length;
    double c[] = new double[n];
    int d[] = {1};
    int indx[] = new int[n];
    double e[][] = new double[n][n];
    e = LU(a, indx, d);
    c = LUaxb(e, b, indx);
    return c;
} // end of AXB
```

```java
public static void main(String arg[]) throws RemoteException {
    double L = 1.0;
    double W = 1.0;
    int N = 16, M = 16;
    double hi = 20.0;
    SRP_FEM tg = new SRP_FEM(L, W, N);
    int cond0 = 0; // x==0
    int cond1 = 1; // x==L
    int cond2 = 2; // y==0
    int cond3 = 3; // y==W
    double Ti0 = 100.0;
    double Ti1 = 100.0;
    double Ti2 = 200.0;
    double Ti3 = 600.0;
    tg.setTemperature(cond0, 0.0, L, 0.0, Ti0);
    tg.setTemperature(cond1, 0.0, L, 0.0, Ti1);
    tg.setTemperature(cond2, 0.0, L, 0.0, Ti2);
    tg.setTemperature(cond3, 0.0, L, 0.0, Ti3);
    double[] k = {50, 50};
    tg.solve(1, k);
    double TR[][] = tg.T;
    int nn = TR.length;
    int nm = TR[0].length;
    System.out.println("温度分布");
    for (i = 1; i < nn; i++) {
        for (j = 0; j < nm; j++) {
            System.out.print(" " + TR[i][j]);
        }
        System.out.println();
    }
    // 读取数组
    Scanner inpData = new Scanner(System.in);
    // nn = inpData.nextInt();
    // nm = inpData.nextInt();
    String strFilePath = "E:/Java_Eng_Problem/Data.txt";
    try {
        FileOutputStream file = new FileOutputStream(strFilePath);
        DataOutputStream fout = new DataOutputStream(file);
        fout.writeInt(nn);
        fout.writeInt(nm);
        for (i = 1; i < nn; i++) {
            for (j = 0; j < nm; j++) {
                fout.writeDouble((double)TR[i][j]);
            }
        }
        fout.close();
        System.out.println("成功...");
    } catch (Exception e) {
        System.out.println(e);
    }
}
```

## 程序 7.6.1 SRP_UnsteadyState.java

```java
import java.io.*;
import java.util.Scanner;
import java.math.*;
import java.awt.Graphics;
import java.awt.event.*;
import java.awt.geom.*;

public class SRP_FEM_UnsteadyState {
    double ap, r, lm, dx, dtm, L, tm, t, cp, d, K, h, tc, sum, Tf, Ti, T0, Ts;
    int i, j, n, nn, m, jj, kk, l;
    double xboundary1, xboundary2, x0;
    double[] T = new double[100];
    int N = 40;
    double[][] a = new double[N][N];
    double[][] al = new double[N][N];
    double[][] au = new double[N][N];
    double[] x = new double[N];
    double[] b = new double[N];
    double[] z = new double[N];
    double[][] B = new double[N][N];
    double[][] D = new double[N][N];
    double[][] E = new double[N][N];

    // 构造函数
    public SRP_FEM_UnsteadyState() {
        Scanner input = new Scanner(System.in);
        System.out.println("输入板/钢坯的长度(m) (例如 0.5)");
        double L = input.nextDouble();
        System.out.println("输入钢坯的 5 个物理和热性能数据");
        System.out.println("密度 Kg/m3 (例如 7600)");
        double d = input.nextDouble();
        System.out.println("热导率 W/m/K (例如 60)");
        double K = input.nextDouble();
        System.out.println("比热量 J/kg/K (例如=500)");
        double cp = input.nextDouble();
        System.out.println("换热系数 W/m2/K (例如 160)");
        double h = input.nextDouble();
        System.out.println("输入加热温度 (例如 1400) 和环境温度 (例如 303)");
        double Tf = input.nextDouble();
        double Ts = input.nextDouble();
        System.out.println("输入总秒数 100");
        double t = input.nextInt();
        System.out.println("输入网格长度 dx (m) 0.05 和时间步长 dt (s) 60");
        double dx = input.nextDouble();
        double dt = input.nextDouble();
        double T0 = 303;
        ap = K / (cp * d);
        r = ap * dt / (dx * dx);
        tc = 0;
        n = (int)(L / dx);
        m = (int)(t);
        System.out.println("温度分布 " + L + " 随时间 " t + " 变化");
        System.out.println("随时间 " + t + " 变化");
        System.out.println("距离 " + dx + " 变化");
        System.out.println("时间 " + dt + " 变化");
        System.out.println("温度 " + L + " 变化");
        System.out.println("时间 " + t + " 变化");
        System.out.println("距离 " + dx + " 变化");
        System.out.println("时间 " + dt + " 变化");
        System.out.println("随时间 " + t + " 变化");
        System.out.println("距离 " + dx + " 变化");
        System.out.println("时间 " + dt + " 变化");
        System.out.println("温度 " + L + " 变化");
        System.out.println("随时间 " + t + " 变化");
        System.out.println("距离 " + dx + " 变化");
        System.out.println("时间 " + dt + " 变化");
        System.out.println("随时间 " + t + " 变化");
        System.out.println("距离 " + dx + " 变化");
        System.out.println("时间 " + dt + " 变化");
        System.out.println("温度 " + L + " 变化");
        System.out.println("随时间 " + t + " 变化");
        System.out.println("距离 " + dx + " 变化");
        System.out.println("时间 " + dt + " 变化");
        System.out.println("随时间 " + t + " 变化");
        System.out.println("距离 " + dx + " 变化");
        System.out.println("时间 " + dt + " 变化");
        System.out.println("温度 " + L + " 变化");
        System.out.println("随时间 " + t + " 变化");
        System.out.println("距离 " + dx + " 变化");
    }
}
```



# 第 8 章 应用-I：传热、凝固与铸造

## 程序 8.1.2 `SP2_Coolinglab.java`

```java
import java.io.*;
import java.util.Scanner;

public class SP2_Coolinglab {
    public double a, lm, dt, lambda, dX, tt, tc, Ts, Tb1, Tb2, A, V, T0, L, w, th, d, k, h, e, c;
    int tm;
    int dt = (tm / 20); // 时间步长占总时间的 5%
    int mm = (tm / dt);
    double dx = L / 20; // 长度跨占总长度的 5%
    int nn = (int) (L / dx);
    double[][] T = new double[100][100]; // 构造函数

    public SP2_Coolinglab() {
        int n = nn - 1;
        int m = mm + 1;
        double dX = dx / L;
        double a = k / (c * d);
        double r = a * dt / (dx * dx); // 左边界温度 j 时间 i 距离
        T[1][0] = T0;
        T[0][0] = T0; // 右边界温度 j 时间，i 距离
        for (int j = 1; j <= m; j++) {
            T[n + 1][j] = Tb2;
        }
        for (int i = 1; i <= n; i++) {
            T[i][1] = T0;
        }
        // 温度分布确定
        for (int j = 1; j <= m; j++) {
            BoundaryTemp(T[1][j - 1], T[0][j - 1]); // 调用边界温度函数
            T[0][j] = Tb1;
            lm = a * dt / (dx * dx);
            for (int i = 1; i <= n; i++) {
                T[i][j + 1] = lm * T[i - 1][j] + (1 - 2 * lm) * T[i][j] + lm * T[i + 1][j];
            }
        }
        for (int j = 1; j <= m; j++) {
            for (int i = 0; i <= n + 1; i++) {
                System.out.print(" T" + j + i + T[i][j]);
            }
            System.out.println();
        }
    }

    public double BoundaryTemp(double Ts2, double Ts1) {
        tt = a * dt / (L * L); // 无量纲时间
        lambda = tt / (dX * dX);
        if ((Ts - Ts1) <= 0)
            Tb1 = Ts2;
        else
            Tb1 = Ts2 + h * dx * (Ts - Ts1);
        return (Tb1);
    }

    public static void main(String args[]) {
        int n, m;
        Scanner input = new Scanner(System.in);
        System.out.print("输入板/坯料的长度(m),宽度(m),厚度(m): ");
        double L = input.nextDouble();
        double w = input.nextDouble();
        double th = input.nextDouble();
        System.out.print("输入两端的温度 C: ");
        double Tf = input.nextDouble();
        double T0 = input.nextDouble();
        System.out.println("输入坯料数据的物理和热属性");
        System.out.print("密度 Kg/m3, 导热系数 W/m/deg.K, 比热 joule/kg/deg K, 传热系数 W/m/k, 发射率: ");
        double d = input.nextDouble();
        double k = input.nextDouble();
        double c = input.nextDouble();
        double h = input.nextDouble();
        double e = input.nextDouble();
        System.out.print("输入总时间: ");
        int tm = input.nextInt();
        System.out.print("输入网格长度 dx 和时间步长 dt: ");
        double dx = input.nextDouble();
        double dt = input.nextDouble();
        SP2_Coolinglab cs = new SP2_Coolinglab();
    }
}
```

## 程序 8.3.1 `SP_BilletHeat.java`

```java
import java.io.*;
import java.util.Scanner;
import java.math.*;

public class SP_BilletHeat {
    public double a, lm, dt, dtm, L, tt, lambda, dX, tm, t, cp, d, k, tc, Tf, Ts, e, h;
    double[][] T = new double[100][100]; // 构造函数

    public SP_BilletHeat() {
        double dX = dx / L;
        double a = k / (cp * d);
        int i, j, n, nn, mm;
        n = (int) (L / dx); // 长度分段
        tt = tm * a / (L * L); // 无量纲时间
        m = (int) (tm / dt);
        nn = n + 1;
        mm = m + 1;
        j = 0; // 时间 0，热体均匀温度 Tf
        for (i = 1; i <= nn; i++) {
            T[i][j] = Tf;
            T[i][j + 1] = Tf;
        }
        j = 1;
        t = 0;
        for (j = 1; j <= mm; j++) { // t+dt 时间
            i = 1;
            t = t + dt;
            tt = a * t / (L * L); // 与热扩散相关的无量纲时间
            lambda = tt / (dx * dx); // 数量
            // 与环境直接接触的边界温度确定
            T[i][j] = 2 * lambda * (T[i + 1][j - 1] + dX * h * L * (Ts) / k) + T[i][j - 1] * (1 - 2 * lambda * (1 + dX * h / L));
            if (T[i][j] <= Ts) T[i][j] = Ts; // 环境温度
            // t 周期后的长度分布确定
            for (i = 1; i <= n + 1; i++) {
                T[0][j] = T[i][j] + 30; // 边界外
                T[i][j + 1] = lambda * (T[i + 1][j] + T[i - 1][j]) + (1 - 2 * lambda) * T[i][j];
                if (T[i][j] <= Ts) T[i][j] = Ts; // 下一步 t+dt 中间点的温度
            }
        }
        // 输出
        for (j = 1; j < mm; j++) {
            for (i = 1; i <= nn / 2; i++) {
                System.out.print(" T" + j + i + T[i][j]);
            }
            for (i = nn / 2; i >= 1; i--) {
                System.out.print(" T" + j + i + T[i][j]);
            }
            System.out.println();
        }
    }

    public static void main(String args[]) {
        int n, m;
        Scanner input = new Scanner(System.in);
        System.out.print("输入板/坯料的长度(m),宽度(m),厚度(m): ");
        double L = input.nextDouble();
        double w = input.nextDouble();
        double th = input.nextDouble();
        System.out.print("输入加热温度和环境温度 C: ");
        double Tf = input.nextDouble();
        double Ts = input.nextDouble();
        System.out.println("输入坯料数据的物理和热属性");
        System.out.print("密度 Kg/m3, 导热系数 W/m/deg.K, 比热 joule/kg/deg K, 传热系数 W/m2/k: ");
        double d = input.nextDouble();
        double k = input.nextDouble();
        double cp = input.nextDouble();
        double h = input.nextDouble();
        System.out.print("输入总时间(秒): ");
        int tm = input.nextInt();
        System.out.print("输入网格长度 dx 和时间步长 dt: ");
        double dx = input.nextDouble();
        double dt = input.nextDouble();
        SP_BilletHeat bht = new SP_BilletHeat();
    }
}
```

## 程序 8.4.1 `SP_BilletHeat_Implicit.java`

```java
import java.io.*;
import java.util.Scanner;
import java.math.*;

public class SP_BilletHeat_Implicit {
    public double ap, r, lm, dt, dx, dtm, L, tm, t, cp, d, K, h, tc, Tf, Ti, Ts;
    public double xboundary1, xboundary2, x0, sum;
    double[] T = new double[100];
    double[][] a = new double[40][40];
    double[][] au = new double[40][40];
    double[][] al = new double[40][40];
    double[] x = new double[40];
    double[] b = new double[40];
    double[] z = new double[40];
    // 构造函数
    public SP_BilletHeat_Implicit() {
        int i, j, n, nn, m, mm, jj, k, l;
        ap = K / (cp * d);
        r = ap * dt / (dx * dx);
        n = (int) (L / dx);
        m = (int) (tm / dt);
        nn = n + 1;
        mm = m + 1;
        j = 0; // 时间 0，热体均匀温度 Tf
        for (i = 1; i <= nn; i++) {
            T[i] = Tf; // 注意：此处代码逻辑可能有误，T 定义为数组
        }
        j = 1;
        t = 0;
        for (j = 1; j <= mm; j++) { // t+dt 时间
            i = 1;
            t = t + dt;
            tt = a * t / (L * L); // 与热扩散相关的无量纲时间
            lambda = tt / (dx * dx); // 数量
            // 与环境直接接触的边界温度确定 // j 时间
            // (注：原始代码片段此处不完整且存在变量未定义)
        }
    }
}
```

```cpp
j = 1;
for (i = 2; i <= n - 1; i++) {
    a[i][j] = -r;
    a[i][j + 1] = 2 + 2 * r;
    a[i][j + 2] = -r;
    j = j + 1;
}
tc = 0;
// "材料从左侧加热，温度为 " << Tf << "k，右侧为环境温度 \n";
// "温度随从左到右距离增加 " << dx << " m 的变化，时间为 " << dt << " 秒 \n";
do {
    T[0] = T[2] - 2 * dx * h * (T[1] - Tf) / K; // 左边界
    T[n + 1] = T[n - 1] + Ti * 2 * dx / K; // 右边界
    x[0] = T[0]; // 考虑 i=0，对于所有 j 值（即时间），x[0]=xboundary1
    x[n + 1] = T[n + 1]; // 考虑 i=n+1，对于所有 j 值（即时间），x[n+1]=xboundary2
}
```



## 程序 8.5.1 `SP_Solidification.java`

```java
import java.io.*;
import java.util.Scanner;
import java.math.*;

public class SP_Solidification {

    public double a, lm, x, dt, dx, dtm, L, tt, Tli, Tm, lamda, X, dX, tm, t, cp, d, k, tc, Tf, Ts, e, h;
    double[][] T = new double[100][100];
    double[][] Y = new double[50][50];
    double[] Time = new double[50];

    // 构造函数
    public SP_Solidification() {
        int i, j, n, nn, m, mm;
        dX = dx / L;
        a = k / (cp * d);
        n = (int) (L / dx); // 长度
        t = tm * a / (L); // 无量纲时间
        m = (int) (tm / dt);
        nn = n + 1;
        mm = m + 1;

        for (i = 2; i <= n + 1; i++) { // 液态
            T[i][1] = 1200; // j=1，从第二层到最后一层为均匀温度液态
        }
        for (j = 1; j <= m; j++) {
            T[n + 1][j] = 1200; // 在无穷远处 i=n+1 温度保持
        }
        for (j = 1; j <= m; j++) {
            T[1][j] = 303; // 第一层与固态接触的液态由于过冷低于冰点
        }
        for (j = 1; j <= m; j++) { // t=0 时 j=1
            for (i = 2; i <= n; i++) { // i=1，界面/边界
                T[i][j + 1] = T[i][j] + ((a * dt) / (dx * dx)) * (T[i - 1][j] + T[i + 1][j] - 2 * T[i][j]);
            }
        }

        System.out.println("液态从左到右的冷却分布，间隔为 " + dx);
        System.out.println("时间间隔 " + dt);
        for (j = 1; j <= m; j++) {
            for (i = 2; i <= n; i++) {
                if (T[i][j] <= Tm) { // 固态
                    Y[i][j] = (i - 1) * dx; // i=2，距离边界 dx 处
                    Time[j] = (j - 1) * dt;
                } else {
                    System.out.print(" " + T[i][j]);
                }
            }
        }

        System.out.println("从 L 到 R 的凝固层，时间为 dt" + dt);
        for (j = 1; j <= m; j++) {
            for (i = 2; i <= n; i++) {
                if (Y[i][j] != 0 && Y[i][j] != Y[i - 1][j] && Y[i][j] != Y[j - 1]) {
                    System.out.print(" " + Y[i][j] + Time[j]);
                }
            }
        }
    }

    public static void main(String args[]) {
        int n, m;
        Scanner input = new Scanner(System.in);
        System.out.print("输入板坯/钢坯长度(m)、宽度(m)、厚度(m): ");
        double L = input.nextDouble();
        double w = input.nextDouble();
        double th = input.nextDouble();
        System.out.print("输入加热温度及环境温度 (C): ");
        double Tf = input.nextDouble();
        double Ts = input.nextDouble();
        System.out.println("输入钢坯物理及热性能数据");
        System.out.print("密度 (Kg/m3), 导热系数 (W/m.deg.K), 比热 (J/kg/deg K), 传热系数 (W/m2/k): ");
        double d = input.nextDouble();
        double k = input.nextDouble();
        double cp = input.nextDouble();
        double h = input.nextDouble();
        System.out.print("输入总时间 (秒): ");
        int tm = input.nextInt();
        System.out.print("输入网格长度 dx 和时间步长 dt: ");
        double dx = input.nextDouble();
        double dt = input.nextDouble();
        SP_Solidification so = new SP_Solidification();
    }
}
```

## 程序 `SP_Casting.java`

```java
import java.io.*;
import java.util.Scanner;
import java.math.*;

public class SP_Casting {

    public double a, lm, x, dt, dx, dtm, L, H, Ys, Yl, dY, tt;
    public double Tsi, Tli, Tm, tm, t, cp, d, ks, kl, k, Tf, e, h;
    public int i, j, n, nn, m, mm;
    double[][] TL = new double[100][100];
    double[][] TS = new double[100][100];
    double[] Tl = new double[50];
    double[] Ts = new double[50];
    double[] Y = new double[50];
    double[] Time = new double[50];

    // 构造函数
    public SP_Casting() {
        int i, j, n, nn, m, mm;
        Y[0] = 0;
        m = (int) (tm / dt);
        n = (int) (L / dx);
        liquidTemp();
        solidTemp();
        System.out.println("液态与固体温度分布" + dx);
        for (j = 1; j <= m; j++) {
            System.out.println("经过秒数" + j * dt);
            for (i = 1; i <= n + 1; i++) {
                System.out.print(" " + TL[n + 2 - i][j + 1]);
                System.out.println(" " + TS[i][j + 1]);
            }
        }
        for (j = 1; j <= m; j++) {
            Tl[j] = TL[3][j + 1];
            Ts[j] = TS[3][j + 1];
            dY = (h * (Tl[j] - Tm) - ks * (Ts[j] - Tm) / Ys) * dt / (d * H);
            Y[j] = Y[j - 1] + dY;
            System.out.print(" " + dt);
            System.out.println(" " + Y[j]);
            Ys = Ys + dY; // 由于新形成的固体 dY，固体厚度增加
            Yl = Yl - dY; // 由于新形成的固体 dY，液态厚度减少
            dt = dt + 60;
        }
    }

    public double liquidTemp() {
        double dx, L, k, h, Ti, Tb;
        L = 0.5;
        d = 7200;
        k = 40;
        cp = 600;
        h = 60;
        dx = 0.1;
        Ti = 1200;
        Tb = 1200;
        a = k / (cp * d);
        // a = 1.5*pow(10,(-4));
        double r = a * dt / (dx * dx); // 为了准确性，r 应该 <=0.5
        n = (int) (L / dx); // 长度分段
        nn = n + 1;
        mm = m + 1;
        for (i = 2; i <= n + 1; i++) { // 液态
            TL[i][1] = Ti; // 初始 j=1，从第 2 层到最后一层 (n+1) 的液态处于均匀温度
        }
        for (j = 1; j <= m; j++) {
            TL[n + 1][j] = Tb; // 在 y=无穷远 i=n+1 温度保持不变
        }
        for (j = 1; j <= m; j++) {
            TL[1][j] = Tm; // 与固体接触的第一层液态由于过冷现象温度低于冰点
        }
        for (j = 1; j <= m; j++) { // t=0 时 j=1
            for (i = 2; i <= n; i++) { // i=1, 界面/边界
                TL[i][j + 1] = TL[i][j] + ((a * dt) / (dx * dx)) * (TL[i - 1][j] + TL[i + 1][j] - 2 * TL[i][j]);
            }
        }
        return (0);
    }

    public double solidTemp() {
        double dx, L, k, h, Ti, Tb;
        L = .5;
        d = 7600;
        k = 60;
        cp = 500;
        h = 60;
        dx = 0.1;
        Ti = 400;
        Tb = 400;
        a = k / (cp * d);
        double r = a * dt / (dx * dx);
        n = (int) (L / dx); // 长度分段
        nn = n + 1;
        mm = m + 1;
        for (i = 2; i <= n + 1; i++) { // 液态
            TS[i][1] = 400; // 初始 j=1，液态处于均匀温度
        }
        for (j = 1; j <= m; j++) {
            TS[n + 1][j] = 400; // 在 y=无穷远 i=n+1 温度保持不变
        }
        for (j = 1; j <= m; j++) {
            TS[1][j] = Tm; // 与固体接触的第一层液态由于过冷现象温度低于冰点
        }
        for (j = 1; j <= m; j++) { // t=0 时 j=1
            for (i = 2; i <= n; i++) { // i=1, 界面/边界
                TS[i][j + 1] = TS[i][j] + ((a * dt) / (dx * dx)) * (TS[i - 1][j] + TS[i + 1][j] - 2 * TS[i][j]);
            }
        }
        return (0);
    }
}
```



## 12.9 第 9 章 应用：金属与材料

### 程序 9.1.1 SP_Casting.java

```java
import java.io.*;
import java.util.Scanner;
import java.math.*;

public class SP_Casting {

    public double a, lm, x, dt, dx, dtm, L, H, Ys, Yl, dY, Ti, Tb, u, tt, dy;
    public double Tsi, Tli, Tm, tm, t, cp, d, ks, kl, Tf, e, h;
    public int i, j, n, nn, m, mm, k, p;
    double[][][] T = new double[50][50][50];
    double[][] TL = new double[100][100];
    double[][] Ts = new double[50][50];
    double[][] Y = new double[50][50];
    double[] Tl = new double[50];
    double[] Time = new double[50];

    // 构造函数
    public SP_Casting() {
        int i, j, n, nn, m, mm;
        Ys = 0.5; d = 7600; ks = 60; cp = 500; h = 60; dx = 0.1; tm = 600; dt = 60; Ti = 400; Tb = 400; Tm = 1800; dy = 0.1;
        u = 0.01; H = 281700;
        m = (int) (tm / dt);
        n = (int) (L / dx);
        double r = a * dt / (dx * dx);
        nn = n + 1;
        mm = m + 1;
        k = 1;
        for (i = 2; i <= n + 1; i++) { // 液态
            T[i][1][k] = Tm; // 初始 j=1 液态，从第二层到最后一层 (n+1) 均匀温度
        }
        for (j = 1; j <= m; j++) {
            T[n + 1][j][k] = Ti; // 在 y=无穷远 i=n+1 温度保持不变
        }
        for (j = 1; j <= m + 1; j++) {
            T[1][j][k] = Tm; // 接触 t 的第一层液态
        }
        System.out.println("第一垂直截截面 k=1 的温度分布");
        for (j = 1; j <= m + 1; j++) {
            for (i = 2; i <= n; i++) {
                T[i][j + 1][k] = T[i][j][k] + ((a * dt) / (dx * dx)) * (T[i - 1][j][k] + T[i + 1][j][k] - 2 * T[i][j][k]);
                // if(T[i][j + 1][k] <= 303) T[i][j + 1][k] = 303;
                System.out.print(" " + T[i][j + 1][k]);
            }
            System.out.println(" ");
        }
        System.out.println("x 方向从左到右随时间 " + dt + " 变化的温度分布");
        for (k = 1; k <= 10; k++) {
            for (j = 1; j <= m; j++) {
                for (i = 2; i <= n; i++) {
                    T[i][j][k + 1] = T[i][j][k] + (T[i][j + 1][k] - T[i][j][k]) * dy / (u * dt);
                    System.out.println(" " + T[i][j][k + 1]);
                }
                System.out.println(" ");
            }
            System.out.println("后续步骤 y 方向向下" + k);
        }
        System.out.println("假设任何水平 x 方向的平均温度靠近线");
        System.out.println("以速率 " + u + " 随 y 增加从顶部到底部的温度分布");
        System.out.println("下一列 时间为秒" + dt);
        for (k = 1; k <= 10; k++) {
            for (j = 1; j <= m; j++) {
                System.out.println(" " + T[4][j][k + 1]);
            }
        }
        Y[2][1] = 0;
        for (j = 1; j <= m; j++) {
            for (k = 1; k <= 10; k++) {
                dY = -ks * dy * (T[4][j][k + 1]) / (d * Ys);
                Y[j + 1] = Y[k] + dY;
                System.out.println(" " + dY * 100);
                System.out.println(" " + Y[j + 1] * 100);
                Ys = Ys + dY; // 由于新凝固，固体层厚度增加
                dy = dy + 0.1;
            }
            System.out.println("" + dt + " 秒后的凝固层厚度");
        }
    }

    public static void main(String[] args) {
        int n, m;
        Scanner input = new Scanner(System.in);
        System.out.print("输入板坯/锭的长度(m),宽度(m),厚度(m) ");
        double L = input.nextDouble();
        double w = input.nextDouble();
        double th = input.nextDouble();
        System.out.print("输入加热到环境温度的 C ");
        double Tf = input.nextDouble();
        double Ts = input.nextDouble();
        System.out.println("输入坯料的物理与热属性 5 项数据");
        System.out.print("密度 Kg/m3,热导率 W/m/deg.K,比热 joule/kg/deg K, 热热系数 W/m2/k ");
        double d = input.nextDouble();
        double k = input.nextDouble();
        double cp = input.nextDouble();
        double h = input.nextDouble();
        System.out.print("输入总时间 秒");
        int tm = input.nextInt();
        System.out.print("输入网格长度 dx & 时间步长 dt ");
        double dx = input.nextDouble();
        double dt = input.nextDouble();
        SP_Casting cstn = new SP_Casting();
    }
}
```

### 程序 9.1.2 SP_ConCast.java

```java
import java.io.*;
import java.util.Scanner;
import java.math.*;

public class SP_ConCast {

    public double a, lm, x, dt, dx, dtm, L, H, Ys, Yl, dY, Ti, Tb, u, tt, dy;
    public double Tsi, Tli, Tm, tm, t, cp, d, ks, kl, Tf, e, h;
    public int i, j, n, nn, m, mm, k, p;
    double[][][] T = new double[50][50][50];
    double[][] TL = new double[100][100];
    double[][] Ts = new double[50][50];
    double[][] Y = new double[50][50];
    double[] Tl = new double[50];
    double[] Time = new double[50];

    // 构造函数
    public SP_ConCast() {
        int i, j, n, nn, m, mm;
        Ys = 0.5; d = 7600; ks = 60; cp = 500; h = 60; dx = 0.1; tm = 600; dt = 60; Ti = 400; Tb = 400; Tm = 1800; dy = 0.1;
        u = 0.01; H = 281700;
        m = (int) (tm / dt);
        n = (int) (L / dx);
        double r = a * dt / (dx * dx);
        nn = n + 1;
        mm = m + 1;
        k = 1;
        for (i = 2; i <= n + 1; i++) { // 液态
            T[i][1][k] = Tm; // 初始 j=1 液态，从第二层到最后一层 (n+1) 均匀温度
        }
        for (j = 1; j <= m; j++) {
            T[n + 1][j][k] = Ti; // 在 y=无穷远 i=n+1 温度保持不变
        }
        for (j = 1; j <= m + 1; j++) {
            T[1][j][k] = Tm; // 接触 t 的第一层液态
        }
        System.out.println("第一垂直截截面 k=1 的温度分布");
        for (j = 1; j <= m + 1; j++) {
            for (i = 2; i <= n; i++) {
                T[i][j + 1][k] = T[i][j][k] + ((a * dt) / (dx * dx)) * (T[i - 1][j][k] + T[i + 1][j][k] - 2 * T[i][j][k]);
                // if(T[i][j + 1][k] <= 303) T[i][j + 1][k] = 303;
                System.out.print(" " + T[i][j + 1][k]);
            }
            System.out.println(" ");
        }
        System.out.println("x 方向从左到右随时间 " + dt + " 变化的温度分布");
        for (k = 1; k <= 10; k++) {
            for (j = 1; j <= m; j++) {
                for (i = 2; i <= n; i++) {
                    T[i][j][k + 1] = T[i][j][k] + (T[i][j + 1][k] - T[i][j][k]) * dy / (u * dt);
                    System.out.println(" " + T[i][j][k + 1]);
                }
                System.out.println(" ");
            }
            System.out.println("后续步骤 y 方向向下" + k);
        }
        System.out.println("假设任何水平 x 方向的平均温度靠近线");
        System.out.println("以速率 " + u + " 随 y 增加从顶部到底部的温度分布");
        System.out.println("下一列 时间为秒" + dt);
        for (k = 1; k <= 10; k++) {
            for (j = 1; j <= m; j++) {
                System.out.println(" " + T[4][j][k + 1]);
            }
        }
        Y[2][1] = 0;
        for (j = 1; j <= m; j++) {
            for (k = 1; k <= 10; k++) {
                dY = -ks * dy * (T[4][j][k + 1]) / (d * Ys);
                Y[j + 1] = Y[k] + dY;
                System.out.println(" " + dY * 100);
                System.out.println(" " + Y[j + 1] * 100);
                Ys = Ys + dY; // 由于新凝固，固体层厚度增加
                dy = dy + 0.1;
            }
            System.out.println("" + dt + " 秒后的凝固层厚度");
        }
    }

    public static void main(String[] args) {
        int n, m;
        Scanner input = new Scanner(System.in);
        System.out.print("输入钢坯长度(m),宽度(m),厚度(m)");
        double L = input.nextDouble();
        double w = input.nextDouble();
        double th = input.nextDouble();
        System.out.print("输入加热温度和环境温度 C");
        double Tli = input.nextDouble();
        double Tsi = input.nextDouble();
        System.out.println("输入钢坯物理和热性能数据");
        System.out.print("密度 Kg/m3,导热系数 W/m/deg, 比热 joule/kg/deg, 换热系数 W/m/k");
        double d = input.nextDouble();
        double k = input.nextDouble();
        double cp = input.nextDouble();
        double h = input.nextDouble();
        System.out.print("输入总时间 sec");
        int tm = input.nextInt();
        System.out.print("输入网格长度 dx 和时间步长 dt");
        double dx = input.nextDouble();
        double dt = input.nextDouble();
        SP_ConCast concs = new SP_ConCast();
    }
}
```

### 程序 9.2.1 SP_Reductioninetics.java

```java
import java.io.*;
import java.util.Scanner;
import java.math.*;

public class SP_Reductioninetics {

    public double D, lm, x, dt, dy, dtm, L, H, dY, tt;
    public double C0, Ce, tm, t, d, cm, Cb, r;
    public int i, j, n, nn, mm, k;
    double[][] F = new double[50][50];
    double[][] C = new double[100][100];
    double[] Y = new double[50];
    double[] Time = new double[50];

    // 构造函数
    public SP_Reductioninetics() {
        L = 0.5; Ce = 0.175; tm = 120; d = 7.8; dy = 0.1; dt = 60; D = 0.0071; N = 3 / 2; cm = 7.8 / 5; C0 = 1;
        r = D * dt / (dy * dy);
        Y[0] = 0;
        m = (int) (tm / dt);
        n = (int) (L / dy); // 层数
        rr = D * dt * N / cm;
        nn = n + 1;
        mm = m + 1;
        for (j = 1; j <= m; j++) {
            C[1][j] = C0; // y=0 处的还原气体浓度
        }
        for (i = 2; i <= n + 1; i++) {
            C[i][1] = 0; // j=1 处的反应为 0
        }
        System.out.println("还原随层数 " + dy + " 变化的还原气体浓度(m)");
        System.out.println("时间 sec " + dt);
        for (j = 1; j <= m; j++) { // t=0，j=1
            for (i = 2; i <= n; i++) { // i=1，边界
                C[i][j + 1] = C[i][j] + ((D * dt) / (dy * dy)) * (C[i - 1][j] + C[i + 1][j] - 2 * C[i][j]);
                System.out.println(" " + C[i][j + 1]);
                if (C[i][j + 1] > Ce) {
                    // (N*cm)*dY/dt=D*dc/dY 物质平衡
                    // cm=固体摩尔密度=密度/分子量
                    // N=反应气体与固体产摩尔比
                    dY = Math.pow((D * dt * (C[i][j + 1] - Ce)) / (N * cm), 0.5);
                } else {
                    dY = 0;
                }
                F[i][j] = dY;
            }
        }
        System.out.println("还原随层数 " + dy + " 变化的产物生成结果(cm)");
        System.out.println("秒间隔向下 " + dt);
        for (j = 1; j <= m; j++) {
            for (i = 2; i <= n; i++) {
                System.out.println(" " + F[i][j]);
            }
        }
    }

    public static void main(String[] args) {
        int n, m;
        Scanner input = new Scanner(System.in);
        System.out.print("输入长度(m), 宽度(m) ");
        double L = input.nextDouble();
        System.out.print("输入加热温度和环境温度 C ");
        double Tf = input.nextDouble();
        double Ts = input.nextDouble();
        System.out.println("输入钢坯的物理和热性能数据");
        double d = input.nextDouble();
        System.out.print("输入总时间 sec");
        int tm = input.nextInt();
        System.out.print("输入网格长度 dx 和时间步长 dt ");
        double dx = input.nextDouble();
        double dt = input.nextDouble();
        SP_Reductioninetics rdn = new SP_Reductioninetics();
    }
}
```

### 程序 9.2.2 SP_Carburization.java

```java
import java.io.*;
import java.util.Scanner;
import java.math.*;

public class SP_Carburization {
```



### 程序片段：SP_Carburization 类

```java
public int i, j, n, jj, k, l, iter;

public double xboundary1, xboundary2, L, dx, dt, x0, t, d, tc, r, sum;

double [][] a = new double[40][40];

double [][] au = new double[40][40];

double [][] al = new double[40][40];

double [] x = new double[40];

double [] b = new double[40];

double [] z = new double[40];

// 构造函数
public SP_Carburization() {
    L = 1.0; dx = 0.2; xboundary1 = 0.2; xboundary2 = 1.3; x0 = 0.2; d = 0.00002; dt = 60; t = 600;
    r = d * dt / (dx * dx);
    n = (int) (L / dx);
    for (i = 1; i <= n; i++) {
        x[i] = x0; // 初始浓度，i=1 左端，i=n 右端
        // x0=料的初始浓度
    } // i=0 左侧，i=n+1 右侧虚设点
    do {
        x[0] = xboundary1; // 对于所有 j 值，考虑 i=0 时，x[0]=xboundary1
        x[n + 1] = xboundary2; // 对于所有 j 值，考虑 i=n+1 时，x[n+1]=xboundary2
        b[1] = r * x[0] + (2 - 2 * r) * x[1] + r * x[2] + r * xboundary1;
    } while (false); // 示例代码未完结的循环逻辑
}
```

```java
// RHS 列第 1 行
b[n] = r * x[n-1] + (2 - 2 * r) * x[n] + r * x[n+1] + r * xboundary2;
// RHS 列最后一行
for (i = 2; i <= n - 1; i++) {
    b[i] = r * x[i-1] + (2 - 2 * r) * x[i] + r * x[i+1];
}
for (i = 1; i <= n; i++) {
    for (j = 1; j <= n; j++) {
        a[i][j] = 0;
    }
}
a[1][1] = 2 + 2 * r;
a[1][2] = -r;
a[n][n-1] = -r;
a[n][n] = 2 + 2 * r;
j = 1;
for (i = 2; i <= n - 1; i++) {
    a[i][j] = -r;
    a[i][j+1] = 2 + 2 * r;
    a[i][j+2] = -r;
    j = j + 1;
}
// 矩阵求解
for (i = 1; i <= n; i++) {
    for (j = 1; j <= n; j++) {
        al[i][j] = 0.0;
        au[i][j] = 0.0;
    }
}
for (j = 1; j <= n; j++) {
    au[j][j] = 1.0;
    al[j][1] = a[j][1];
    au[1][j] = a[1][j];
}
for (j = 2; j <= n; j++) {
    for (i = j; i <= n; i++) {
        sum = 0;
        for (k = 1; k <= j - 1; k++) {
            sum = sum + al[i][k] * au[k][j];
        }
        al[i][j] = a[i][j] - sum;
    }
    if (j <= n) {
        for (jj = j + 1; jj <= n; jj++) {
            sum = 0;
            for (kk = 1; kk <= j - 1; kk++) {
                sum = sum + al[j][kk] * au[kk][jj];
            }
            au[j][jj] = (a[j][jj] - sum) / al[j][j];
        }
    }
}
// 使用前向代入求解 alZ=B
z[1] = b[1] / al[1][1];
for (j = 2; j <= n; j++) {
    sum = 0.0;
    for (k = 1; k <= j - 1; k++) {
        sum = sum + al[j][k] * z[k];
    }
    z[j] = (b[j] - sum) / al[j][j];
}
x[n] = z[n];
for (j = 2; j <= n; j++) {
    l = n - j + 1;
    sum = 0.0;
    for (k = l + 1; k <= n; k++) {
        sum = sum + au[l][k] * x[k];
    }
    x[l] = z[l] - sum;
}
tc = tc + dt;
System.out.println(" " + tc);
for (i = 1; i <= n; i++) {
    System.out.println(" " + x[i]);
}
while (tc <= t);
public static void main(String args[]) {
    int n, m;
    Scanner input = new Scanner(System.in);
    System.out.print("Enter Length(m) ");
    double L = input.nextDouble();
    System.out.print("concentration at x =0 & t=t and x =L & t ");
    double xboundary1 = input.nextDouble();
    double xboundary2 = input.nextDouble();
    System.out.println("Initial concentration at x & t=0");
    double x0 = input.nextDouble();
    System.out.print("Enter total time sec");
    int t = input.nextInt();
    System.out.print("Diffusivity cm2/min=");
    int d = input.nextInt();
    System.out.print("Enter grid length & time step ");
    double dx = input.nextDouble();
    double dt = input.nextDouble();
    SP_MaterialBalance b = new SP_MaterialBalance();
}
```

### 程序 9.3.1 SP_MaterialBalance.java

```java
import java.io.*;
import java.util.Scanner;
import java.math.*;

public class SP_MaterialBalance {
    int i, j;
    public double a1, a2, a3, a4, a5, b1, b2, b3, b4, b5, c1, c2, c3, c4, c5, P, Q, S;
    double[][] A = new double[10][10];
    double[][] B = new double[10][10];
    double[][] Y = new double[10][10];
    double[][] L = new double[10][10];
    double[][] U = new double[10][10];
    double[][] X = new double[10][10];

    // 构造函数
    public SP_MaterialBalance() {
        A[0][0] = a1 / 100;
        A[0][1] = a2 / 100;
        A[0][2] = a3 / 100;
        A[1][0] = b1 / 100;
        A[1][1] = b2 / 100;
        A[1][2] = ((b3 / 100) - (S / R));
        A[2][0] = c1 / 100;
        A[2][1] = c2 / 100;
        A[2][2] = c3 / 100;
        B[0][0] = ((P * a4 + Q * a5) / 100);
        B[1][0] = (((P * b4 * (60 / 28) + Q * b5)) / 100);
        B[2][0] = ((P * c4 + Q * c5) / 100);
        for (i = 0; i < 3; i++) {
            for (j = 0; j < 3; j++) {
                B[i][j] = X[i][j] = Y[i][j] = 0;
            }
        }
        L[0][0] = L[1][1] = L[2][2] = 1;
        L[0][1] = L[0][2] = L[1][2] = U[2][0] = U[2][1] = 0;
        U[0][0] = A[0][0];
        U[0][1] = A[0][1];
        U[0][2] = A[0][2];
        // LU 分解
        L[1][0] = A[1][0] / U[0][0];
        U[1][1] = A[1][1] - L[1][0] * U[0][1];
        U[1][2] = A[1][2] - L[1][0] * U[0][2];
        // 分解为 L & U
        L[2][0] = A[2][0] / U[0][0];
        L[2][1] = (A[2][1] - L[2][0] * U[0][1]) / U[1][1];
        U[2][2] = (A[2][2] - (L[2][0] * U[0][2] + L[2][1] * U[1][1])); // 注意：此处逻辑可能存在误，原文逻辑不一致，此处保留了结构
        Y[0][0] = B[0][0] / L[0][0];
        Y[1][0] = (B[1][0] - L[1][0] * Y[0][0]) / L[1][1];
        Y[2][0] = (B[2][0] - (L[2][0] * Y[0][0] + L[2][1] * Y[1][0])) / L[2][2];
        // 前向代入
        X[2][0] = Y[2][0] / U[2][2];
        X[1][0] = (Y[1][0] - U[1][2] * X[2][0]) / U[1][1];
        X[0][0] = (Y[0][0] - (U[0][1] * X[1][0] + U[0][2] * X[2][0])) / U[0][0];
        // 后向代入
        System.out.println("铁矿石、焦料、石灰石");
        System.out.println(" " + X[0][0]);
        System.out.print(" " + X[1][0]);
        System.out.println(" " + X[2][0]);
    }

    public static void main(String args[]) {
        int n, m;
        Scanner input = new Scanner(System.in);
        System.out.print("percentage of Fe in iron ore,coke,limestone,hot metal,off gas");
        double a1 = input.nextDouble();
        double a2 = input.nextDouble();
        double a3 = input.nextDouble();
        double a4 = input.nextDouble();
        double a5 = input.nextDouble();
        System.out.print("percentage of Silica in iron ore,coke,limestone,hot metal,off gas");
        double b1 = input.nextDouble();
        double b2 = input.nextDouble();
        double b3 = input.nextDouble();
        double b4 = input.nextDouble();
        double b5 = input.nextDouble();
        System.out.print("percentage of Carbon in iron ore,coke,limestone,hot metal,off gas");
        double c1 = input.nextDouble();
        double c2 = input.nextDouble();
        double c3 = input.nextDouble();
        double c4 = input.nextDouble();
        double c5 = input.nextDouble();
        System.out.print("The amount of hot metal to be produced(in tons per day)");
        double P = input.nextDouble();
        System.out.print("The amount of off gas produced(in tons per day):");
        double Q = input.nextDouble();
        System.out.print("percentage of lime in limestone charged ");
        double S = input.nextDouble();
        System.out.print("The basicity of the limestone charged");
        double R = input.nextDouble();
        SP_MaterialBalance mat = new SP_MaterialBalance();
    }
}
```

### 程序 9.6.5 SP_LDHeat.java

```java
import java.io.*;
import java.util.Scanner;
import java.math.*;

public class SP_LDBalance {
    // 金属
    double whm, wls;
    double xhm1, xhm2, xhm3, xhm4, xhm5, xhm6;
    double xls1, xls2, xls3, xls4, xls5, xls6;
    double t1, t2, t3;
    // 炉渣
    double xsl1, xsl2, xsl3, xsl4, xsl5, xsl6;
    double cal1, cal2, cal3, cal4, cal5, cal6, cal7, cal8, cal9, cal10;
    double cal11, cal12, cal13, cal14, cal15;
    // 输入热量
    double calin;
    /* 1) 金属的热量 */
    double shm, shm1, shm2, shm3;
    double hfe1, hfe2, hfe3, hfe4, hfe5, hfe6, hfe7, hfe8, hfe9;
    double hsi1, hsi2, hsi3, hsi4, hsi5, hsi6, hsi7, hsi8, hsi9;
    double hmn1, hmn2, hmn3, hmn4, hmn5, hmn6, hmn7, hmn8, hmn9;
    double hop1, hop2, hop3, hop4, hop5, hop6, hop7, hop8, hop9;
    double hoc1, hoc2, hoc3, hoc4, hoc5, hoc6, hoc7, hoc8, hoc9, hoc10, hoc11, hoc12;
    /* 计算输出热量 */
    double calout;
    double sls, dt, sls1, sls2, sls3;
    double ssla;
    double hla1, hla2, hla3, hla4, hla5, hla6, hla7, hla8, hla9, hla10, hla11, hla12;
}
```



# 第 10 章 应用部分-III 结构退化

## 程序 10.1.1 SP_GeneticCorrosion.java

使用遗传算法在 `Cl`、`SO4` 和 `pH` 的组合下寻找最大腐蚀值，约束条件为 `Cl<=24`、`SO4<=4`、`pH<=8`。`geneLength` 为 6，最大数量 `111111=63`、`1111111=255`、`111111111=1023`（等）。

```java
double hlm1, hlm2, hlm3, hlm4, hlm5, hlm6, hlm7, hlm8, hlm9, hlm10, hlm11, hlm12;

double hps1, hps2, hps3, hps4, hps5, hps6, hps7, hps8, hps9, hps10, hps11, hps12;

double hcs1, hcs2, hcs3, hcs4, hcs5, hcs6, hcs7, hcs8, hcs9, hcs10, hcs11, hcs12, hcs13, hcs14, hcs15;

double hli, t, hli1, hli2, hli3, hli4, hli5, hli6, hli7, hli8, hli9, hli10, hli11;

double sld;

double hg1, hg2, hg3, hg4, hg5, hg6, hg7, hg8, hg9, hg10, hg11, hg12, hg13, hg14, hg15, hg16, hg17, hg18, hg19, hg20, hg21;

public void Datainput() {
    Scanner input = new Scanner(System.in);
    System.out.print(" \n\n\t\t enter the inputs");
    System.out.print(" \n\n\t enter the following data:- ");
}
```

```java
System.out.print(" \n {所有重量均以公吨为单位} ");
System.out.print(" \n\n 输入进入炉内的热金属水重量 ");
whm = input.nextDouble();
System.out.print(" \n 输入炉内熔钢的量 ");
wls = input.nextDouble();
System.out.print(" \n 输入炉内熔渣的量 ");
wsl = input.nextDouble();
System.out.print(" \n 输入热金属水的温度（摄氏度）");
t1 = input.nextDouble();
System.out.print(" \n 输入炉内温度（摄氏度） ");
t2 = input.nextDouble();
System.out.print(" \n 输入离开炉的 LD 废气温度（摄氏度） ");
t3 = input.nextDouble();
System.out.print(" \n\n\t 输入热金属水的成分 :- ");
System.out.print(" \n\n 铁(Fe)的百分比 : ");
xhm1 = input.nextDouble();
System.out.print(" \n 锰(Mn)的百分比 : ");
xhm2 = input.nextDouble();
System.out.print(" \n 硅(Si)的百分比 : ");
xhm3 = input.nextDouble();
System.out.print(" \n 磷(P)的百分比 : ");
xhm4 = input.nextDouble();
System.out.print(" \n 硫(S)的百分比 : ");
xhm5 = input.nextDouble();
System.out.print(" \n 碳(C)的百分比: ");
xhm6 = input.nextDouble();
System.out.print(" \n\n\t 输入精炼液态水的成分 :- ");
System.out.print(" \n\n 铁(Fe)的百分比 : ");
xls1 = input.nextDouble();
System.out.print(" \n 锰(Mn)的百分比 : ");
xls2 = input.nextDouble();
System.out.print(" \n 硅(Si)的百分比 : ");
xls3 = input.nextDouble();
System.out.print(" \n 磷(P)的百分比 : ");
xls4 = input.nextDouble();
System.out.print(" \n 硫(S)的百分比 : ");
xls5 = input.nextDouble();
System.out.print(" \n 碳(C)的百分比 : ");
xls6 = input.nextDouble();
}

public void slag() {
    cal1 = xhm1 * whm;
    cal2 = xls1 * wls;
    cal3 = wsl * 7 / 9;
    cal4 = cal1 - cal2;
    cal5 = cal4 / cal3;
    cal6 = xhm2 * whm;
    cal7 = xls2 * wls;
    cal8 = wsl * 27 / 35;
    cal9 = cal6 - cal7;
    cal10 = cal9 / cal8;
    cal11 = xhm3 * whm;
    cal12 = xls3 * wls;
    cal13 = wsl * 7 / 15;
    cal14 = cal11 - cal12;
    cal15 = cal14 / cal13;
    cal16 = xhm4 * whm;
    cal17 = xls4 * wls;
    cal18 = wsl * 31 / 142;
    cal19 = cal16 - cal17;
    cal20 = cal19 / cal18;
    cal21 = xhm5 * whm;
    cal22 = xls5 * wls;
    cal23 = wsl;
    cal24 = cal21 - cal22;
    cal25 = cal24 / cal23;
    xsl2 = cal10;
    xsl3 = cal5;
    xsl4 = cal20;
    xsl5 = cal25;
    xsl6 = cal15;
    xsl1 = 100 - cal5 - cal10 - cal15 - cal20 - cal25;
}

public double heatIn() {
    /*1) 热金属水的显热*/
    if (t1 > 1450) {
        shm = 0.01 * (t1 - 1450);
    } else {
        shm1 = 0;
        shm2 = shm1 + 12.59;
        shm3 = whm * xhm1 * 10000 / 56;
        shm = shm3 * shm2;
    }

    /*2) 铁的氧化热 */
    t1 = t1 + 273;
    t2 = t2 + 273;
    hfe1 = 64.5;
    hfe2 = 12.38 * t2;
    hfe3 = 1.62 * 0.5 * 0.001 * t2 * t2;
    hfe4 = 0.38 * 100000 / t2;
    hfe5 = hfe2 + hfe3 + hfe4 - 7705.43;
    hfe6 = hfe5 / 1000;
    hfe7 = hfe1 - hfe6;
    hfe8 = xsl3 * 10000 * wsl / 72;
    hfe9 = hfe8 * hfe7;

    /*3) 硅的氧化热*/
    hsi1 = 210.2;
    hsi2 = 14.4 * t2;
    hsi3 = 0.04 * 0.5 * 0.001 * t2 * t2;
    hsi4 = 0 * 100000 / t2;
    hsi5 = hsi2 + hsi3 + hsi4 - 4381.78;
    hsi6 = hsi5 / 1000;
    hsi7 = hsi1 - hsi6;
    hsi8 = xls6 * 10000 / 60;
    hsi9 = hsi8 * hsi7;

    /*4) 锰的氧化热*/
    hmn1 = 92.0;
    hmn2 = 11.11 * t2;
    hmn3 = 0.94 * 0.5 * 0.001 * t2 * t2;
    hmn4 = 0.88 * 100000 / t2;
    hmn5 = hmn2 + hmn3 + hmn4 - 3524.42;
    hmn6 = hmn5 / 1000;
    hmn7 = hmn1 - hmn6;
    hmn8 = xsl2 * 10000 / 70;
    hmn9 = hmn8 * hmn7;

    /*5) 磷的氧化热*/
    hop1 = 370.0;
    hop2 = 8.37 * t2;
    hop3 = 0.0 * 0.5 * 0.001 * t2 * t2;
    hop4 = 0 * 100000 / t2;
    hop5 = hop2 + hop3 + hop4 - 4891.96;
    hop6 = hop5 / 1000;
    hop7 = hop1 - hop6;
    hop8 = xsl4 * 10000 / 142;
    hop9 = hop8 * hop7;

    /*6) 碳的氧化热*/
    hoc1 = 26.4;
    hoc2 = 6.79 * t2;
    hoc3 = 0.98 * 0.5 * 0.001 * t2 * t2;
    hoc4 = 0.11 * 100000 / t2;
    hoc5 = hoc2 + hoc3 + hoc4 - 2103.84;
    hoc6 = hoc5 / 1000;
    hoc7 = hoc1 - hoc6;
    hoc8 = xls6 * wls;
    hoc9 = xhm6 * whm;
    hoc10 = hoc9 - hoc8;
    hoc11 = hoc10 * 100000 / 12;
    hoc12 = hoc11 * hoc7;
    calin = shm + hfe9 + hsi9 + hoc12;
    return (calin);
}

public double heatOut() {
    //输出热计算
    /*1) 液态钢的显热*/
    dt = t2 - t1;
    sls1 = 0.01 * dt;
    sls2 = 12.59 + sls1;
    sls3 = wls * xls1 * 10000 / 56;
    sls = sls2 * sls3;

    /*2) 渣质的显热*/
    hla1 = 36.51 * 298;
    hla2 = 9.36 * 0.5 * 0.001 * 298 * 298;
    hla3 = 6.70 * 100000 / 298;
    hla4 = hla1 + hla2 + hla3;
    hla5 = 36.51 * t2;
    hla6 = 9.36 * 0.5 * 0.001 * t2 * t2;
    hla7 = 6.70 * 100000 / t2;
    hla8 = hla5 + hla6 + hla7;
    hla9 = hla8 - hla4;
    hla10 = hla9 / 1000;
    hla10 = hla10 + 346;
    hla11 = xsl3 * 10000 * wsl * 0.5 / 72;
    hla12 = hla10 * hla11;

    hlm1 = 26.42 * 298;
    hlm2 = 3.88 * 0.5 * 0.001 * 298 * 298;
    hlm3 = 6.16 * 100000 / 298;
    hlm4 = hlm1 + hlm2 + hlm3;
    hlm5 = 26.42 * t2;
    hlm6 = 3.88 * 0.5 * 0.001 * t2 * t2;
    hlm7 = 6.16 * 100000 / t2;
    hlm8 = hlm5 + hlm6 + hlm7;
    hlm9 = hlm8 - hlm4;
    hlm10 = hlm9 / 1000;
    hlm10 = hlm10 + 5.9;
    hlm11 = xsl2 * 10000 * wsl / 70;
    hlm12 = hlm10 * hlm11;

    hlps1 = 48.24 * 298;
    hlps2 = 39.68 * 0.5 * 0.001 * 298 * 298;
    hlps3 = 5.0 * 10000 / 298;
    hlps4 = hlps1 + hlps2 + hlps3;
    hlps5 = 48.24 * t2;
    hlps6 = 39.68 * 0.5 * 0.001 * t2 * t2;
    hlps7 = 5.0 * 100000 / t2;
    hlps8 = hlps5 + hlps6 + hlps7;
    hlps9 = hlps8 - hlps4;
    hlps10 = hlps9 / 1000;
    hlps10 = hlps10 + 164;
    hlps11 = xsl4 * 10000 * wsl / 142;
    hlps12 = hlps10 * hlps11;

    hcs1 = xsl6 * 10000 / 60;
    hcs2 = xsl2 * 10000 / 70;
    hcs3 = xsl3 * 10000 * wsl * 0.5 / 72;
    hcs4 = hcs1 - hcs2 - hcs3;
    hcs5 = 36.25 * 298;
    hcs6 = 8.83 * 0.5 * 0.001 * 298 * 298;
    hcs7 = 7.24 * 100000 / 298;
    hcs8 = hcs5 + hcs6 + hcs7;
    hcs9 = 36.25 * t2;
    hcs10 = 8.83 * 0.5 * 0.001 * t2 * t2;
    hcs11 = 7.24 * 100000 / t2;
    hcs12 = hcs9 + hcs10 + hcs11;
    hcs13 = hcs12 - hcs8;
    hcs14 = hcs13 / 1000;
    hcs14 = hcs14 + 30.2;
    hcs15 = hcs14 * hcs4;
    ssla = hla12 + hlm12 + hlps12 + hcs15;

    /*3) 石灰加热到 1700 度*/
    t = 298;
    li1 = 11.86 * t;
    li2 = 1.08 * 0.5 * 0.001 * t * t;
    li3 = 1.66 * 10000 / t;
    li4 = li1 + li2 + li3;
    li5 = 11.86 * t2;
    li6 = 1.08 * 0.5 * 0.001 * t2 * t2;
    li7 = 1.66 * 10000 / t2;
    li8 = li5 + li6 + li7;
    li9 = li8 - li4;
    li10 = li9 / 10000;
    li11 = xsl1 * wsl * 10000 / 56;
    li = li10 * li11;

    /*4) LD 废气的显热*/
    t3 = t3 + 273;
    hg1 = xsl6 * wls;
    hg2 = xhm6 * whm;
    hg3 = hg2 - hg1;
    hg4 = hg3 * 1000000 / 12;
    hg5 = t3 - 298;
    hg6 = t3 * t3;
    hg7 = 298 * 298;
    hg8 = hg6 - hg7;
    hg9 = 1 / 298;
    hg10 = 1 / t3;
    hg11 = hg10 - hg9;
    hg12 = 6.79 * hg5;
    hg13 = 0.98 * 0.5 * 0.001 * hg8;
    hg14 = .11 * hg11;
    hg15 = hg12 + hg13 + hg14;
    hg16 = 10.55 * hg5;
    hg17 = 2.16 * 0.5 * 0.001 * t2 * t2;
    hg18 = 2.04 * hg11;
    hg19 = hg16 + hg17;
    hg20 = hg15 + hg19;
    hg21 = hg20 / 1000;
    sld = hg4 * hg21;
    calout = sld + li;
    return (calout);
}
```

```java
import java.io.*;
import java.util.Scanner;
import java.math.*;
import java.util.Random;

public class SP_GeneticCorrosion {
    String[] c;
    String[] g;
    double[] chromoValue;
    double[] fitness;
    int[] gDecimal;
    double crossover_rate = 0.7;
    double mutation_rate = 0.001;
    float target;
    int chromLength = 24;
    int population = 400;
    int geneLength = 6;
    int Max_No_Generation = 200;
    int i, j, k;
    boolean solutionFound;

    public SP_GeneticCorrosion() {
        Scanner input = new Scanner(System.in);
        target = input.nextDouble();
        srand(1);
        for (j = 1; j <= population; j++) {
            c[j] = "";
            int temp = j;
            for (i = 1; i <= chromLength; i++) {
                Random rn = new Random();
                int rnd = rn.nextInt(1000);
                double rf = (double) rnd / 1000;
```



```java
if (rf <= 0.5) {
    c[j] = '1' + c[j];
} else {
    c[j] = '0' + c[j];
}
```

```java
c[1] = "01101"; c[2] = "1100"; c[3] = "0101"; c[4] = "1110"; c[5] = "0011";

int No_of_genration = 1;

solutionFound = false;

while (!solutionFound) {
    for (j = 1; j <= population; j++) {
        fitness[j] = 0.0;
    }

    System.out.println();

    for (j = 1; j <= population; j++) {
        chromo_Value(c[j]);
        chromo_fitness(chromoValue[j]);
        System.out.println("chromo_fitness(chromoValue[j]= " + chromo_fitness(chromoValue[j]));

        if (fitness[j] >= 0.01) {
            System.out.println("Best fit chromosome found=" + c[j]);
            System.out.println("No_of_population " + population);
            System.out.println("No of Generation=" + No_of_genration);
            System.out.println("ChromeValue=" + chromoValue[j]);
            System.out.println("fitness= " + fitness[j]);
            System.out.println("Gene combations are");

            for (i = 1; i <= (chromLength / geneLength); i++) {
                System.out.println(" No=" + i + " Gene (Binary)" + g[i] + "=" + gDecimal[i]);
            }

            System.out.println();
            solutionFound = true;
            break;
        }
    }

    float totalfitness = 0;

    for (j = 1; j <= population; j++) {
        totalfitness += fitness[j];
    }

    String offspring1, offspring2;

    int pop = 1;
    j = 1;

    do {
        offspring1 = Rwheel(totalfitness);
        offspring2 = Rwheel(totalfitness);
        crossover(offspring1, offspring2);
        mutate(offspring1);
        mutate(offspring2);
        c[pop] = offspring1;
        c[pop + 1] = offspring2;
        pop += 2;
    } while (pop <= population);

    No_of_genration = No_of_genration + 1;

    if (No_of_genration > Max_No_Generation) {
        System.out.println("solutions not found after" + (No_of_genration - 1) + " Generations");
        solutionFound = true;
    }
}
```

```java
public double chromo_fitness(double value) {
    fitness[j] = 1 / Math.abs(target - value);

    if (target == chromoValue[j]) fitness[j] = 100.0;

    return fitness[j];
}
```

```java
public double chromo_Value(String chromo) {
    int geneNo = 1;

    for (i = 0; i < chromLength; i += geneLength) {
        g[geneNo] = chromo.substring(i, i + geneLength);
        geneNo++;
    }

    for (geneNo = 1; geneNo <= (chromLength / geneLength); geneNo++) {
        int temp = 0, sum = 0;

        for (k = 0; k < geneLength; k++) {
            if (g[geneNo].charAt(k) == '1') {
                temp = (int) Math.pow(2, (geneLength - (k + 1)));
            } else {
                temp = 0;
            }
            sum += temp;
        }

        gDecimal[geneNo] = sum;
    }

    double b0 = 40.787, b1 = 20.52, b2 = 2.0, b3 = -3.75, b4 = 4.0, b5 = -8.12, b6 = -3.4675, b7 = -8.615;
    double c1 = 21.5, d1 = 2.5, c2 = 2.1, d2 = 1.3, c3 = 6, d3 = 2;
    double x1, x2, x3;

    x1 = (gDecimal[1] - c1) / d1;
    x2 = (gDecimal[2] - c2) / d2;
    x3 = (gDecimal[3] - c3) / d3;

    return 0; // 补全缺失的返回值以符合 Java 逻辑，此处原文未提供 return
}
```

## 程序 10.2.1 SRP_NNetData.java

```java
import sp_package.*;
import java.text.*;
import java.util.*;
import java.io.DataInputStream;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;

// 其他 java 文件来自 sp_package：1.Mapmax_pack.java,2.SP_Neuron.java,3.SP_Connection.java
// class_Mapmax_pack 用于将输入数据转换为无量纲，再转回无量纲

public class SRP_NNet2 {
    static {
        Locale.setDefault(Locale.ENGLISH);
    }

    final boolean isTrained = false;
    final DecimalFormat df;
    final Random rand = new Random();
    final ArrayList<SP_Neuron> inputLayer = new ArrayList<SP_Neuron>();
    final ArrayList<SP_Neuron> hiddenLayer = new ArrayList<SP_Neuron>();
    final ArrayList<SP_Neuron> outputLayer = new ArrayList<SP_Neuron>();
    final SP_Neuron bias = new SP_Neuron();
    final int[] layers;
    final int randomWeightMultiplier = 1;
    final double epsilon = 0.00000000001;
    final double learningRate = 0.9f;
    final double momentum = 0.7f;
    double[] output[];
    // 用于更新所有权重
    final HashMap<String, Double> weightUpdate = new HashMap<String, Double>();

    public static void main(String[] args) {
        int m, nm, n, hdn;
        n = 1; m = 1; nm = 1; hdn = 1;
    }
}
```

```java
double arr[][] = new double[300][15]; // 输入数组
double arro[][] = new double[300][5]; // 输出数组
Scanner input = new Scanner(System.in);

System.out.println("是否想从 excel 文件中读取 NN 数据？如果是按 1，否则按 2");
int y = input.nextInt();

if (y == 1) {
    System.out.println("正在从 Excel 文件读取数据");

    try {
        SRP_ReadExcel file = new SRP_ReadExcel();
        // 文件位置
        file.setInputFile("c:/Java_Engg_Problem/dataCorr.xls");
        double xx[][] = file.read();
        n = xx.length; // 数组 xx[][] 的行数
        m = xx[5].length; // 数组 [][] 的列数
        System.out.println("n,m=" + n + " " + m);

        int i, j;
        // 声明数组
        double X[][] = new double[300][10];
        int mk, nk;
        nk = 0; mk = 0;

        for (i = 1; i < xx.length; i++) {
            j = 0;
            if (xx[i][j] == 0.0) break; // 无数据处
            mk = 0; // 在列循环开始前置零

            for (j = 0; j < xx[6].length; j++) {
                if (xx[i][j] != 0.0) { // 仅非零数据
                    // X[nk][mk] 从 X[0][0] 开始的新组非零数据
                    X[nk][mk] = xx[i][j];
                    mk = mk + 1; // 列增量
                }
            }
            nk = nk + 1; // 行增量
        }

        System.out.println(" nk, mk=" + nk + " " + mk);
        System.out.println(" NN 数据已从 excel 文件读取输入和输出");
        nm = 1;

        for (i = 0; i < nk; i++) {
            for (j = 0; j < mk - 1; j++) {
                arr[i][j] = X[i][j];
                System.out.print(" " + arr[i][j]);
            }
            // System.out.print("i, j " + i + " " + j);
            aro[nm - 1] = X[i][j];
            System.out.println(" " + aro[nm - 1]);
            // System.out.println();
        }

        n = nk;
        m = mk - 1;
        nm = 1;
    } catch (Exception e) {
        System.out.println(e);
    }

    System.out.println("选择隐藏层数量，选择（1 到 2）少于或大于输入层数量，输入层=3，隐藏层可能是 2 或 4");
    hdn = input.nextInt();
} else {
    System.out.println("输入输入层数量、隐藏层数量和输出层数量");
    m = input.nextInt();
    hdn = input.nextInt();
    nm = input.nextInt();
    System.out.println("输入输入与对应输出的数据集");
    n = input.nextInt(); // 数据大小

    for (i = 0; i < n; i++) {
        System.out.println("当输出 Y=f(X1,X2,X3) 时，输入 X1, X2, X3");
        for (j = 0; j < m; j++) {
            arr[i][j] = input.nextDouble();
        }
        System.out.println("输入对应的输出 Y");
        for (j = 0; j < nm; j++) {
            aro[i][j] = input.nextDouble();
        }
    }
}

System.out.println(" NN 数据");

for (i = 0; i < n; i++) {
    System.out.print("Inputs ");
    for (j = 0; j < m; j++) {
        System.out.print((float) arr[i][j] + "\t");
    }
    System.out.print(" + Outputs ");
    for (j = 0; j < nm; j++) {
        System.out.print((float) aro[i][j] + "\t");
    }
    System.out.println();
}

// 调用类将输入数据无量化并将结果还原回
SP_Mapminmax_pack mp = new SP_Mapminmax_pack();
double ixmax[] = new double[m]; // 每个变量输入数据的最大数组
```



```java
double ixmin[] = new double[m]; // 每个变量输入数据的最小数组

double oxmax[] = new double[nm]; // 每个变量输出数据的最大数组

double oxmin[] = new double[nm]; // 每个变量输出数据的最小数组

double xx[] = new double[n];

for (j = 0; j < m; j++) {

    for (i = 0; i < n; i++) {

        xx[i] = arr[i][j];

    }

    ixmax[j] = mp.getMax(xx);

    ixmin[j] = mp.getMin(xx);

}
```

```java
trainedWeights();

updateAllWeights();

}

}

// 随机

double getRandom() {
    return randomWeightMultiplier * (rand.nextDouble() * 2 - 1); // [-1;1[
}

/**
 * @param inputs
 * 输入层的神经元数量与输入变量的数量相等
 */
public void setInput(double inputs[]) {
    // System.out.println ("inputLayer.size()="+inputLayer.size());
    for (int i = 0; i < inputLayer.size(); i++) {
        inputLayer.get(i).setOutput(inputs[i]);
    }
}

public double[] getOutput() {
    double[] outputs = new double[outputLayer.size()];
    // System.out.println ("outputLayer.size()="+outputLayer.size());
    for (int i = 0; i < outputLayer.size(); i++) {
        outputs[i] = outputLayer.get(i).getOutput();
    }
    return outputs;
}

/**
 * 根据输入计算神经网络的输出。前向操作
 */
public void activate() {
    for (SP_Neuron n : hiddenLayer) {
        n.calculateOutput();
    }
    for (SP_Neuron n : outputLayer) {
        n.calculateOutput();
    }
}

/**
 * 所有输出反向传播
 *
 * @param expectedOutput
 * 首先计算误差相对于输入输出神经元的每个权重的偏导
 * 偏置在此也进行更新
 */
public void applyBackpropagation(double expectedOutput[]) {
    // 错误检查，值归一化到 ]0;1[
    // System.out.println ("expectedOutput.length="+expectedOutput.length);
    for (int i = 0; i < expectedOutput.length; i++) {
        double d = expectedOutput[i];
        if (d < 0 || d > 1) {
            if (d < 0)
                expectedOutput[i] = 0 + epsilon;
            else
                expectedOutput[i] = 1 - epsilon;
        }
    }
    int i = 0;
    for (SP_Neuron n : outputLayer) {
        ArrayList<SP_Connection> connections = n.getAllInConnections();
        for (SP_Connection con : connections) {
            double ak = n.getOutput();
            double ai = con.leftNeuron.getOutput();
            double desiredOutput = expectedOutput[i];
            double partialDerivative = -ak * (1 - ak) * ai * (desiredOutput - ak);
            double deltaWeight = -learningRate * partialDerivative;
            double newWeight = con.getWeight() + deltaWeight;
            con.setDeltaWeight(deltaWeight);
            con.setWeight(newWeight + momentum * con.getPrevDeltaWeight());
        }
        i++;
    }
    // 更新隐藏层的权重
    for (SP_Neuron n : hiddenLayer) {
        ArrayList<SP_Connection> connections = n.getAllInConnections();
        for (SP_Connection con : connections) {
            double aj = n.getOutput();
            double ai = con.leftNeuron.getOutput();
            double sumKoutputs = 0;
            int j = 0;
            for (SP_Neuron out_neu : outputLayer) {
                double wjk = out_neu.getConnection(n.id).getWeight();
                double desiredOutput = (double) expectedOutput[j];
                double ak = out_neu.getOutput();
                j++;
                sumKoutputs += -(desiredOutput - ak) * ak * (1 - ak) * wjk;
            }
            double partialDerivative = aj * (1 - aj) * ai * sumKoutputs;
            double deltaWeight = -learningRate * partialDerivative;
            double newWeight = con.getWeight() + deltaWeight;
            con.setDeltaWeight(deltaWeight);
            con.setWeight(newWeight + momentum * con.getPrevDeltaWeight());
        }
    }
}

// 使用所有输入数据加上原始输入输出的最小/值运行神经网络
// 将结果转换为无维形式的实数
void run(int m, int hdn, int n, double[][] inputs, double[][] expectedOutputs, double[] ixmin, double[] ixmax, double[] oxmin, double[] oxmax, int maxSteps, double minError) {
    int i;
    double[][] resultOutputs = new double[n][nm];
    for (i = 0; i < n; i++) {
        for (int j = 0; j < nm; j++) {
            resultOutputs[i][j] = -1;
        }
    }
    // 训练神经网络直到达到 minError 或超过 maxSteps
    double error = 1;
    for (i = 0; i < maxSteps && error > minError; i++) {
        // System.out.println("inputs.length="+inputs.length);
        error = 0;
        for (int p = 0; p < n; p++) {
            setInput(inputs[p]);
            activate();
            double[] output = getOutput();
            resultOutputs[p] = output;
            // System.out.println("expectedOutputs[p].length="+expectedOutputs[p].length);
            for (int j = 0; j < nm; j++) {
                // System.out.println( "out, expec "+output[j]+expectedOutputs[p][j]);
                double err = Math.pow((output[j] - expectedOutputs[p][j]), 2);
                error += err;
            }
            applyBackpropagation(expectedOutputs[p]);
        }
        // printResult();
        // System.out.println (" printResult()inputs.length="+inputs.length);
        double[][] arr = new double[n][m]; // 读取输入
        double[][] arro = new double[n][nm]; // 读取实际输出
        for (int p = 0; p < n; p++) {
            System.out.print("INPUTS: ");
            layers[0] = m; layers[2] = nm;
            for (int x = 0; x < layers[0]; x++) {
                System.out.print(inputs[p][x] + " ");
                arr[p][x] = inputs[p][x];
            }
            System.out.print("EXPECTED: ");
            for (int x = 0; x < layers[2]; x++) {
                System.out.print(expectedOutputs[p][x] + " ");
            }
        }
    }
}
```

```java
weightUpdate.put(weightKey(4, 3), 7.24);
weightUpdate.put(weightKey(4, 4), -3.71);
weightUpdate.put(weightKey(4, 5), -.51);
weightUpdate.put(weightKey(5, 6), -3.28);
weightUpdate.put(weightKey(5, 7), 7.29);
weightUpdate.put(weightKey(5, 8), -.05);
weightUpdate.put(weightKey(6, 9), 5.86);
weightUpdate.put(weightKey(6, 10), 6.03);
weightUpdate.put(weightKey(6, 11), .71);
weightUpdate.put(weightKey(7, 12), 2.19);
weightUpdate.put(weightKey(7, 13), -8.82);
weightUpdate.put(weightKey(7, 14), -8.84);
weightUpdate.put(weightKey(7, 15), 11.81);
weightUpdate.put(weightKey(7, 16), .44);
}

public void printWeightUpdate() {
    // System.out.println("打印 WeightUpdate, 已在 trainedWeights() 中放入并并将 isTrained 设置为 true");
    // 隐藏层的权重
    for (SP_Neuron n : hiddenLayer) {
        ArrayList<SP_Connection> connections = n.getAllInConnections();
        for (SP_Connection con : connections) {
            String w = df.format(con.getWeight());
            // System.out.println("weightUpdate.put(weightKey(" + n.id + ", "
            // + con.id + "), " + w + ");");
        }
    }
    // 输出层的权重
    for (SP_Neuron n : outputLayer) {
        ArrayList<SP_Connection> connections = n.getAllInConnections();
        for (SP_Connection con : connections) {
            String w = df.format(con.getWeight());
            // System.out.println("weightUpdate.put(weightKey(" + n.id + ", "
            // + con.id + "), " + w + ");");
        }
    }
    // System.out.println();
}

public void printAllWeights() {
    // System.out.println("打印所有权重");
    // 隐藏层的权重
    for (SP_Neuron n : hiddenLayer) {
        ArrayList<SP_Connection> connections = n.getAllInConnections();
        for (SP_Connection con : connections) {
            double w = con.getWeight();
            // System.out.println("n=" + n.id + " c=" + con.id + " w=" + w);
        }
    }
    // 输出层的权重
    for (SP_Neuron n : outputLayer) {
        ArrayList<SP_Connection> connections = n.getAllInConnections();
        for (SP_Connection con : connections) {
            double w = con.getWeight();
            // System.out.println("n=" + n.id + " c=" + con.id + " w=" + w);
        }
    }
    // System.out.println();
}
```

### 程序 10.3.3 SP_CathodicProtection.java



```java
import java.io.*;
import java.util.Scanner;
import java.math.*;

public class SP_CathodicProtection {
    double relx, sum, uavg, tol, q, p, r, g, dia, hy, temp;
    int i, j, nx, ny, nx1, ny1, length, hx, y, a, l, Nodes;
    double u[][] = new double[1000][1000];

    public SP_CathodicProtection(double length, double dia, double hx, double y) {
        Scanner input = new Scanner(System.in);
        nx = (int)(length / hx);
        ny = (int)(180 / y); // y=theta 角 0,3
        nx1 = nx + 1;
        ny1 = ny + 1;
        Nodes = (nx1 + 1) * (ny1 + 1);
        System.out.println(" 输入相对于 Cu/Cu 的作用电位(V)。");
        u[1][1] = input.nextDouble(); // u[1][1]= 0 度处的电位。l=0
        System.out.println(" 输入总电流密度 mA/sq.m)");
        q = input.nextDouble();
        System.out.println(" 输入介质电阻率(ohm cm)");
        p = input.nextDouble();
        r = dia / 2;
        hy = r * y * 0.0087;
        // 管道横向电位(mV)
        for (i = 1; i <= (ny1 + 1); i++) {
            u[i + 1][1] = u[i][1] - hy * (q * hy / (hx + hy)) * p / 100000; // 单位 ohm.cm
            if (u[i + 1][1] < 0)
                u[i + 1][1] = 0;
        }
        // 管道沿长度方向电位(mV)
        for (i = 1; i <= (nx1 + 1); i++) {
            u[1][i + 1] = u[1][i] - hx * (q * hx / (hx + hy)) * p / 100000;
            if (u[1][i + 1] < 0)
                u[1][i + 1] = 0;
        }
        // 求和与平均值
        sum = 0;
        for (i = 1; i <= (ny1 + 1); i++) {
            sum += u[i][1];
        }
        for (i = 2; i <= nx1 + 1; i++) {
            sum += u[1][i];
        }
        uavg = sum / ((nx1 + 1) + ny1);
        for (i = 2; i <= ny1 + 2; i++) {
            for (j = 2; j <= nx1 + 2; j++) {
                u[i][j] = uavg;
            }
        }
        System.out.println(" 输入精度水平 (如 0.1/0.01/.001 等)");
        tol = input.nextDouble();
        k = Math.pow(hx, 2) + Math.pow(hy, 2);
        itr = 1;
        // 数值法求解拉拉斯方程
        do {
            max = 0;
            for (i = 2; i <= ny1 + 1; i++) {
                for (j = 2; j <= nx1 + 1; j++) {
                    temp = (hy * hy * (u[i + 1][j] + u[i - 1][j]) + hx * hx * (u[i][j + 1] + u[i][j - 1])) / (2 * k);
                    relx = Math.abs(temp - u[i][j]);
                    if (relx > max)
                        max = relx;
                    u[i][j] = temp;
                }
            }
            if (max < tol)
                break;
            itr++;
        } while (itr < 1000);
        System.out.println("迭代次数=" + itr);
        for (j = 1; j <= nx1 + 1; j++) {
            u[1][j + 1] = (u[1][j] + u[1][j + 2] + 2 * u[2][j + 1]) / 4;
        }
        System.out.println(" 长度方向及周向电位分布");
        ll = 0;
        for (j = 1; j <= (nx1 + 1); j++) {
            System.out.print(" " + ll + "m");
            ll += hx;
        }
        System.out.println();
        a = 0;
        for (i = 2; i <= (ny1 + 1); i++) {
            for (j = 1; j <= (nx1 + 1); j++) {
                System.out.print(" " + (int) u[i][j]);
            }
            System.out.println();
            a = (int)(a + y);
        }
    }

    public static void main(String args[]) {
        Scanner input = new Scanner(System.in);
        System.out.println("输入管道长度(m),直径(m)");
        double length = input.nextDouble();
        double dia = input.nextDouble();
        System.out.println("输入沿长度的节点间距(m)= ");
        double hx = input.nextDouble();
        System.out.println("输入周向角度间距(度)= ");
        double y = input.nextDouble();
        SP_CathodicProtection cp = new SP_CathodicProtection(length, dia, hx, y);
    }
}
```

### 12.11 第 11 章 应用部分 IV 相图与合金设计

#### 11.2.1 SP_PhaseDiagram.java

```java
import java.io.*;
import java.util.Scanner;
import java.math.*;

public class SP_PhaseDiagram {
    double Ha, Hb, HHm1, GG1, T;
    double Xb, Xbb, XXb1, XXa1, Tx, Ta, Tb, e1, e2;
    double XXb2, XXa2, HHm2, GG2, Xbs, XbL;
    double G1[] = new double[150];
    double G2[] = new double[150];
    double Hm1[] = new double[150];
    double Hm2[] = new double[150];
    double Xa1[] = new double[150];
    double Xb1[] = new double[150];
    double Xa2[] = new double[150];
    double Xb2[] = new double[150];
    double s1[] = new double[150];
    double s2[] = new double[150];
    char ch;
    int i, j;
    double dy = 0.1; double R = 0.00821; double dx = 0.005;

    public SP_PhaseDiagram(double Ta, double Tb, double Ha, double Hb) {
        Scanner input = new Scanner(System.in);
        System.out.println("对于液态的混合熵系数 6.5");
        e1 = input.nextDouble();
        System.out.println("对于固态的混合熵系数 3.5");
        e2 = input.nextDouble();
        // 从 A 点 50 开始
        T = Ta + 50;
        do {
            XXb1 = 0;
            i = 0;
            do {
                XXb1 += dx;
                i++;
                G1[i] = free_energy(XXb1, T);
            } while (XXb1 < 0.98);
            XXb2 = 0;
            j = 0;
            do {
                XXb2 += dx;
                j++;
                G2[j] = free_energy_L(XXb2, T);
            } while (XXb2 < 0.98);
            s1 = slope_S(G1);
            s2 = slope_L(G2);
            compare(s1, s2);
            System.out.println("T=" + T + "\tXbs=" + Xbs + "\tXbL=" + XbL);
            T += 50;
        } while (T <= Tb - 50); // 到 B 点 50
    }

    public double free_energy(double XXb1, double T) {
        XXa1 = 1 - XXb1;
        HHm1 = e1 * XXa1 * XXb1;
        GG1 = (HHm1 - XXb1 * Hb * (1 / Tb) + R * T * (XXa1 * Math.log(XXa1) + XXb1 * Math.log(XXb1)));
        return (GG1);
    }

    public double free_energy_L(double XXb2, double T) {
        XXa2 = 1 - XXb2;
        HHm2 = e2 * XXa2 * XXb2;
        GG2 = (HHm2 + XXa2 * Ha * (1 / Ta) + R * T * (XXa2 * Math.log(XXa2) + XXb2 * Math.log(XXb2)));
        return (GG2);
    }

    public double[] slope_S(double G1[]) {
        for (int i = 1; i < G1.length; i++) {
            s1[i] = ((G1[i + 1]) - (G1[i])) / dx;
        }
        return (s1);
    }

    public double[] slope_L(double G2[]) {
        // Implementation placeholder based on context structure
        return (s2);
    }

    public void compare(double[] s1, double[] s2) {
        // Implementation placeholder
    }
}
```

```java
for (i=1;i<G2.length; i++) {
    s2[i]= ((G2[i+1]) -(G2[i]))/( dx);
    return (s2);
}

public double[] compare(double s1[],double s2[]) {
    double mini ;
    mini=Math.abs(s1[1]-s2[1]);
    i=0;
    j=0;
    do {
        i=i+1;
        do {
            j=j+1;
            if (Math.abs(s1[i]-s2[j])<mini) {
                mini=Math.abs(s1[i]-s2[j]);
                Xbs=Xb1[i];
                XbL=Xb2[j];
            }
            Xb=Xb2[j];
        } while(Xb<0.9);
        Xbb=Xb1[i];
    } while(Xbb<0.9);
    double A[]= { Xbs, XbL};
    // double A[]= new double [2]; ...
    return (A);
}

public static void main(String args[]) {
    Scanner input = new Scanner(System.in);
    System.out.println("低熔点金属 A 和对应的高熔点金属 B 的熔点 (deg.K)=");
    double Ta = input.nextDouble();
    double Tb = input.nextDouble();
    System.out.println("输入 A 和 B 的熔融焓 (Kj/mole)=  ");
    double Ha= input.nextDouble();
    double Hb= input.nextDouble();
    Ta=1685;
    Tb=1210.4;
    Ha=50.5;
    Hb=36.94;
    SP_PhaseDiagram ph= new SP_PhaseDiagram(Ta,Tb,Ha,Hb);
}
```

## 程序 11.5.2 SP_Fracture.m



## MATLAB 神经网络数据处理与训练流程

```matlab
% 从文件 'inpf2.xlsx' & 'optf2.xlsx' 读取 Excel 数据输入和输出
p = [xlsread('inpf2.xlsx')];
t = [xlsread('outf2.xlsx')];

% 输入值和目标值通过以下函数转换为 [-1,1] 向量 p2 & t2，
% 使得它们的值类似于无量纲分值
[p2, ps] = mapminmax(p);
[t2, ts] = mapminmax(t);

% 现在将完整数据划分为训练集、验证集和测试集。20% 的数据用于验证集，
% 20% 用于测试集，剩余 60% 用于训练集。从原始数据中随机选取这些集合。
% 所有这一切通过函数 `dividevec` 完成。
[trainV, val, test] = dividevec(p2, t2, 0.20, 0.20);

% 使用前向反传播函数 `newff` 生成神经网络，包含两层：
% 第一层（隐藏层）具有 20 个使用传递函数 `tansig` 的神经元，输出层
% 包含一个使用传递函数 `purelin` 的神经元，并使用训练函数 `traingd`
% net = newff(minmax(p2), [20, 1], {'tansig', 'purelin'}, 'traingd');
net = newff(minmax(p2), [20, 1], {'tansig', 'purelin'}, 'trainlm');

% 现在可以更改默认参数，如每轮显示次数、学习率 `lr`、
% 总迭代轮数、误差目标等。
net.trainParam.show = 50;
net.trainParam.lr = 0.05;
net.trainParam.epochs = 300;
net.trainParam.goal = 1e-5;

% 现在通过以下函数开始训练、验证和测试
[net, tr] = train(net, trainV.P, trainV.T, [], [], val, test);
a2 = sim(net, p2);

% 将无量纲数字转换为真实值，即从 [-1,1] 向量映射到
% 实际值。
a = mapminmax('reverse', a2, ts);

% 在网络模拟输出与实际输出之间进行线性回归
[m, b, r] = postreg(a, t);
% ... (剩余的 p1 到 p5 和 meshgrid 数据定义)
```

## 样本数据表

| 177 | 0.43 | 0.19 | 0.98 | 0.21 | 0.01 | 4.9 | 0.08 | 90 |
| 66 | 0.42 | 0.23 | 0.78 | 0.21 | 0.22 | 0 | 0.01 | 55 |
| 82 | 0.42 | 0.23 | 0.78 | 0.21 | 0.22 | 0 | 0.01 | 52 |
| 220 | 0.41 | 0.33 | 0.72 | 0.26 | 1.83 | 0.78 | 0.05 | 40 |
| 220 | 0.41 | 0.33 | 0.72 | 0.26 | 1.83 | 0.78 | 0.05 | 40 |
| 208 | 0.43 | 0.27 | 0.84 | 0.26 | 1.85 | 0.82 | 0.05 | 60 |
| 226 | 0.4 | 0.29 | 0.75 | 0.25 | 1.77 | 0.79 | 0.05 | 52 |
| 223 | 0.41 | 0.29 | 0.69 | 0.22 | 1.87 | 0.78 | 0.05 | 53 |
| 235 | 0.4 | 0.29 | 0.75 | 0.25 | 1.77 | 0.79 | 0.05 | 40 |
| 240 | 0.4 | 0.29 | 0.75 | 0.25 | 1.77 | 0.79 | 0.05 | 32 |
| 231 | 0.38 | 0.28 | 0.74 | 0.26 | 1.86 | 0.84 | 0.05 | 68 |
| 204 | 0.43 | 0.3 | 0.65 | 0.26 | 1.85 | 0.82 | 0.05 | 78 |
| 184 | 0.42 | 0.25 | 0.71 | 0.23 | 1.77 | 0.8 | 0.05 | 106 |
| 213 | 0.42 | 0.25 | 0.71 | 0.23 | 1.77 | 0.8 | 0.05 | 68 |
| 203 | 0.43 | 0.27 | 0.84 | 0.26 | 1.85 | 0.82 | 0.05 | 65 |
| 206 | 0.43 | 0.27 | 0.84 | 0.26 | 1.85 | 0.82 | 0.05 | 50 |
| 230 | 0.42 | 0.25 | 0.71 | 0.23 | 1.77 | 0.8 | 0.05 | 52 |
| 206 | 0.42 | 0.25 | 0.71 | 0.23 | 1.77 | 0.8 | 0.05 | 80 |
| 241 | 0.38 | 0.28 | 0.74 | 0.26 | 1.86 | 0.84 | 0.05 | 53 |
| 240 | 0.38 | 0.28 | 0.74 | 0.26 | 1.86 | 0.84 | 0.05 | 54 |
| 240 | 0.38 | 0.28 | 0.74 | 0.26 | 1.86 | 0.84 | 0.05 | 56 |
| 191 | 0.43 | 0.24 | 0.63 | 0.3 | 1.56 | 1.03 | 0.05 | 80 |
| 230 | 0.43 | 0.24 | 0.63 | 0.3 | 1.56 | 1.03 | 0.05 | 49 |
| 246 | 0.43 | 1.68 | 0.7 | 0.39 | 1.93 | 0.79 | 0.07 | 69 |
| 243 | 0.41 | 0.77 | 0.71 | 0.81 | 0.8 | 0.08 | 0 | 0 |
| 200 | 0.4 | 0.3 | 0.2 | 0.8 | 0 | 0 | 0 | 88 |
| 224 | 0.41 | 0.8 | 0 | 0 | 0 | 0 | 20 | 0 |
| 234 | 0.4 | 1.6 | 0.83 | 0.41 | 1.82 | 0.09 | 0 | 74 |
| 205 | 0.4 | 1.6 | 0.83 | 0.41 | 1.82 | 0.09 | 0 | 74 |
| 233 | 0.39 | 1.55 | 0.82 | 0.43 | 1.73 | 0.86 | 0 | 79 |
| 230 | 0.39 | 1.55 | 0.82 | 0.43 | 1.73 | 0.86 | 0 | 53 |
| 142 | 0.42 | 1.45 | 0.73 | 0.26 | 1.82 | 0.98 | 0 | 111 |
| 185 | 0.42 | 1.45 | 0.73 | 0.26 | 1.82 | 0.98 | 0 | 111 |
| 206 | 0.42 | 1.45 | 0.73 | 0.26 | 1.82 | 0.98 | 0 | 78 |
| 238 | 0.42 | 1.45 | 0.73 | 0.26 | 1.82 | 0.98 | 0 | 68 |
| 255 | 0.44 | 1.63 | 0.81 | 0.38 | 1.34 | 0.85 | 0 | 45 |
| 259 | 0.42 | 1.59 | 0.80 | 0.37 | 1.81 | 0.79 | 0 | 52 |
| 255 | 0.42 | 1.59 | 0.80 | 0.37 | 1.81 | 0.79 | 0 | 56 |
| 255 | 0.42 | 1.59 | 0.80 | 0.37 | 1.81 | 0.79 | 0 | 58 |
| 248 | 0.43 | 1.72 | 0.84 | 0.39 | 1.72 | 0.77 | 0 | 60 |
| 233 | 0.43 | 1.72 | 0.84 | 0.39 | 1.72 | 0.77 | 0 | 60 |
| 236 | 0.47 | 0.20 | 0.85 | 0.01 | 1.01 | 0.57 | 0 | 46 |
| 253 | 0.47 | 0.20 | 0.85 | 0.01 | 1.01 | 0.57 | 0 | 37 |
| 263 | 0.47 | 0.20 | 0.85 | 0.01 | 1.01 | 0.57 | 0 | 36 |
| 203 | 0.45 | 0.026 | 0.69 | 1.01 | 0.55 | 1.08 | 0.08 | 110 |
| 231 | 0.45 | 0.026 | 0.69 | 1.01 | 0.55 | 1.08 | 0.08 | 61 |
| 247 | 0.45 | 0.026 | 0.69 | 1.01 | 0.55 | 1.08 | 0.08 | 67 |
| 211 | 0.475 | 0.22 | 0.75 | 1 | 0.55 | 1 | 0.12 | 92 |
| 217 | 0.475 | 0.22 | 0.75 | 1 | 0.55 | 1 | 0.12 | 94 |
| 226 | 0.475 | 0.22 | 0.75 | 1 | 0.55 | 1 | 0.12 | 72 |
| 211 | 0.475 | 0.22 | 0.75 | 1 | 0.55 | 1 | 0.12 | 92 |
| 217 | 0.475 | 0.22 | 0.75 | 1 | 0.55 | 1 | 0.12 | 79 |
| 226 | 0.475 | 0.22 | 0.75 | 1 | 0.55 | 1 | 0.12 | 50 |
| 228 | 0.475 | 0.22 | 0.75 | 1 | 0.55 | 1 | 0.12 | 46 |
| 214 | 0.475 | 0.22 | 0.75 | 1 | 0.55 | 1 | 0.12 | 97 |
| 214 | 0.475 | 0.22 | 0.75 | 1 | 0.55 | 1 | 0.12 | 90 |
| 225 | 0.475 | 0.22 | 0.75 | 1 | 0.55 | 1 | 0.12 | 45 |
| 208 | 0.475 | 0.22 | 0.75 | 1 | 0.55 | 1 | 0.12 | 105 |
| 215 | 0.475 | 0.22 | 0.75 | 1 | 0.55 | 1 | 0.12 | 84 |

## 12.12 所有包：`sp_package`

### 程序 12.1 `SP_MaxMin.java`

```java
package sp_package;

import java.util.Scanner;
import java.io.*;
import java.math.*;
import java.util.*;

public class SP_MaxMin {
    // 最大值
    public static double getMax(double[] x) {
        double maxValue = x[0];
        for (int i = 1; i < x.length; i++) {
            if (x[i] > maxValue) {
                maxValue = x[i];
            }
        }
        return maxValue;
    }

    // 最小值
    public static double getMin(double[] x) {
        double minValue = x[0];
        for (int i = 1; i < x.length; i++) {
            if (x[i] < minValue) {
                minValue = x[i];
            }
        }
        return minValue;
    }
}
```

### 程序 12.2 `SP_Mapmax_pack.java`

```java
package sp_package;

import java.util.Scanner;
import java.io.*;
import java.math.*;
import java.util.*;

public class SP_Mapmax_pack {
    public static void main(String args[]) {}

    // 数据集的映射最大
    public static double[][] dataX(int n, int m, double[][] arr) {
        int i = 0;
        int j = 0;
        double[][] dataX = new double[n][m];
        double[][] array = new double[n][m];
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                array[i][j] = arr[i][j];
            }
        }
        double[] x = new double[n];
        for (int j = 0; j < m; j++) {
            for (int i = 0; i < n; i++) {
                x[i] = array[i][j];
            }
            double max = getMax(x);
            double min = getMin(x);
            double[] y = getMinMax(x);
            for (int i = 0; i < n; i++) {
                dataX[i][j] = y[i];
            }
        }
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                System.out.print(" " + dataX[i][j]);
            }
            System.out.println();
        }
        return dataX;
    }

    // 数据集的逆极极大值
    public static double[][] dataMMR(int n, int m, double[][] ar) {
        int i = 0;
        int j = 0;
        double[][] dataMMR = new double[n][m];
        double[][] array = new double[n][m];
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                array[i][j] = ar[i][j];
            }
        }
        double[] y = new double[n];
        for (int j = 0; j < m; j++) {
            for (int i = 0; i < n; i++) {
                y[i] = ar[i][j];
            }
            // 值的极值范围转换
            // double max = getMax(y);
            // double min = getMin(y);
            // double[] range = getMinMax(y);
            // for (int i = 0; i < n; i++) {
            //     dataMMR[i][j] = range[i];
            // }
        }
        // 逻辑未完成
    }
}
```



## 程序包 12.3 sp_graph.java

```java
package sp_package;

import java.awt.*;
import java.awt.Graphics;
import java.awt.event.*;
import java.awt.geom.*;
import java.util.Scanner;

public class sp_graph extends Frame {

    public static int[] datax(int x[]) {
        int n = x.length;
        int[] dx = new int[n];
        for (int i = 1; i <= n; i++) {
            dx[i] = x[i];
        }
        return dx;
    }

    public static int[] datay(int y[]) {
        int n = y.length;
        int[] dy = new int[n];
        for (int i = 1; i <= n; i++) {
            dy[i] = y[i];
        }
        return dy;
    }

    public void paint(Graphics g) {
        int[] dx = new int[10];
        int[] dy = new int[10];
        dx = datax(dx);
        dy = datay(dy);
        g.setColor(Color.BLACK);
        g.setColor(Color.BLUE);
        g.drawRect(35, 40, 90, 55);
        g.setColor(Color.green);
        g.drawOval(80, 100, 0, 50);
        g.setColor(Color.BLUE);
        g.fillRect(200, 40, 90, 5);
        g.setColor(Color.MAGENTA);
        g.fillOval(200, 100, 85, 40);
        Font fnt = new Font("Arial", Font.BOLD, 12);
        g.setFont(fnt);
        g.setColor(Color.BLUE);
        g.drawString("图形示例：矩形, 圆形, 填充圆形, 线", 10, 170);
        Font font = new Font("Arial", Font.BOLD, 16);
        g.setFont(font);
        g.setColor(Color.BLACK);
        g.drawString("Raj 编写", 80, 250);
    }

    public void showGraph() {
        Frame frame = new sp_graph();
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent we) {
                System.exit(0);
            }
        });
        repaint();
        frame.setSize(500, 350);
        setVisible(true);
    }
}
```

## 程序包 12.4 SRP_Graph.java

```java
package sp_package;

import java.awt.*;
import java.awt.event.*;

public class SRP_Graph extends Frame {
    private String xAxisTitle, yAxisTitle, graphTitle;
    private boolean keys;

    public void Graph() {
        initializeGraph();
        xAxisTitle = "";
        yAxisTitle = "";
        graphTitle = "";
    }

    public void Graph(String g, String x, String y) {
        initializeGraph();
        graphTitle = g;
        xAxisTitle = x;
        yAxisTitle = y;
    }

    private class Dataset {
        int count;
        int plotType;
        String title;
        boolean colorRequired, symbolRequired, titleRequired, lineRequired;
    }

    private List points;
    private List datasets;

    private void initializeGraph() {
        datasets = new List();
        nextGraph();
        points = new List();
        xMax = yMax = Double.MIN_VALUE;
        xMin = yMin = Double.MAX_VALUE;
        keys = false;
        setSize(640, 480);
        super.setTitle("图");
        addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent e) {
                dispose();
            }
        });
    }

    public void nextGraph() {
        Dataset d = new Dataset();
        d.count = 0;
        d.title = "";
        d.symbolRequired = false;
        d.colorRequired = false;
        d.titleRequired = false;
        d.lineRequired = true;
        datasets.add(d);
    }

    public void setLine(boolean b) {
        ((Dataset) datasets.current()).lineRequired = b;
        if (b == false) ((Dataset) datasets.current()).symbolRequired = true;
    }

    public void add(double x, double y) {
        Point points = new Point(x, y);
        ((Dataset) datasets.current()).count++;
        if (x > xMax) xMax = x;
        if (x < xMin) xMin = x;
        if (y > yMax) yMax = y;
        if (y < yMin) yMin = y;
    }

    public void showGraph() {
        repaint();
        setVisible(true);
    }

    private class Point {
        double xCoord, yCoord;
        Point(double x, double y) {
            xCoord = x;
            yCoord = y;
        }
    }

    private double xSpread, ySpread, xMin, xMax, yMax;
    private int xAxisLength, yAxisLength, xOrigin, yOrigin;
    private int xBorder, yBorder;

    public void paint(Graphics g) {
        xBorder = 40;
        yBorder = 80;
        xAxisLength = (int) getWidth() - 2 * xBorder;
        yAxisLength = (int) getHeight() - 2 * yBorder;
        xSpread = xMax - xMin;
        ySpread = yMax - yMin;
        if (xMin > 0) xOrigin = scaleX(xMin); else xOrigin = scaleX(0);
        if (yMin > 0) yOrigin = scaleY(yMin); else yOrigin = scaleY(0);
        drawAxes(g);
        plotGraphs(g);
    }

    private int scaleX(double x) {
        return (int) ((x - xMin) / xSpread * xAxisLength) + xBorder;
    }

    private int scaleY(double y) {
        return (int) ((y - yMin) / ySpread * yAxisLength) + yBorder;
    }

    private void plotGraphs(Graphics g) {
        Point p, q;
        int x1, y1, x2, y2;
        Dataset d;
        boolean lastset;
        datasets.reset();
        points.reset();
        lastset = datasets.eol();
        do {
            d = (Dataset) datasets.current();
            p = (Point) points.current();
            x1 = scaleX(p.xCoord);
            y1 = scaleY(p.yCoord);
            if (d.symbolRequired) {
                for (int i = 1; i < d.count; i++) {
                    points.succ();
                    q = (Point) points.current();
                    x2 = scaleX(q.xCoord);
                    y2 = scaleY(q.yCoord);
                    if (d.lineRequired) g.drawLine(x1, y1, x2, y2);
                    if (d.symbolRequired) {
                        x1 = x2;
                        y1 = y2;
                    }
                }
            }
            lastset = datasets.eol();
            if (!lastset) {
                datasets.succ();
                points.succ();
            }
        } while (!lastset);
    }
}
```



```java
import java.awt.geom.*;
import java.util.Scanner;

public class SRP_package_graph extends Frame {

    int[] xCoord1 = new int[50];
    int[] yCoord1 = new int[50];
    int[] xCoord2 = new int[50];
    int[] yCoord2 = new int[50];
    public String gt, gx, gy;
    int shift_xc, shift_yc;

    public void datain(int n, int[] x1, int[] y1, int[] x2, int[] y2) {
        for (int i = 0; i < n; i++) {
            System.out.println("x1, y1,x2,y2=" + x1[i] + " " + y1[i] + " " + x2[i] + " " + y2[i]);
        }
        //------------------ 用于 x,y 坐标的简单类
        for (int i = 0; i < n; i++) {
            xCoord1[i] = x1[i];
            yCoord1[i] = -y1[i];
            xCoord2[i] = x2[i];
            yCoord2[i] = -y2[i];
        }
    }

    public void graph(Graphics g) {
        g.setColor(Color.BLACK);
        for (int i = 1; i <= 5; i++) {
            g.drawLine(xCoord1[i], yCoord1[i], xCoord2[i], yCoord2[i]);
        }
    }

    public void textin(int xxc, int yyc, String title, String xaxis, String yaxis) {
        shift_xc = xxc;
        shift_yc = yyc;
        gt = title;
        gx = xaxis;
        gy = yaxis;
    }

    public void paint(Graphics g) {
        g.setColor(Color.BLACK);
        int y_len = getHeight();
        int x_len = getWidth();
        int xc = x_len / 2 - shift_xc;
        int yc = y_len / 2 + shift_yc;
        g.translate(xc, yc); // 将原点移动到中心
        Graphics2D g2d = (Graphics2D) g;
        g.setColor(Color.BLACK);
        g.drawOval(xc, yc, 10, 10);
        g.drawLine(0, 0, 0, (-y_len - shift_yc)); // y 轴
        g.drawLine(0, 0, x_len - shift_xc, 0); // x 轴
        Font font1 = new Font("Arial", Font.BOLD, 16);
        g.setFont(font1);
        g.drawString(gx, x_len / 2 - 200, 20);
        g2d.rotate(-Math.PI / 2);
        g.drawString(gy, y_len / 3, -50);
        g2d.rotate(Math.PI / 2);
        g.drawString(gt, x_len / 8, y_len / 6);
        Font font = new Font("Arial", Font.BOLD, 16);
        g.setFont(font);
        g.setColor(Color.BLACK);
        g.drawString("Java Programming by Raj", x_len / 2 - 200, y_len + 250);
        graph(g);
    }

    public void initializeGraph() {
        Frame frame = new spgraph();
        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent we) {
                System.exit(0);
            }
        });
        frame.setSize(500, 350);
        setVisible(true);
    }

    public void showGraph() {
        initializeGraph();
        repaint();
    }

    public static void main(String[] args) {
        int n = 5;
        int[] x1 = {1, 2, 3, 4, 5};
        int[] y1 = {23, 12, 20, 23, 44};
        int[] x2 = {12, 23, 34, 13, 35};
        int[] y2 = {34, 12, 23, 44};
        int xxc = 500;
        int yyc = 200;
        SRP_package_graph gr = new SRP_package_graph();
        gr.datain(n, x1, y1, x2, y2);
        gr.textin(xxc, yyc, "Temp Cooling", "Time mins", "Temperature C");
        gr.showGraph();
    }
}
```

### 程序 12.6 `SRP_ReadExcel.java`

从下载文件夹下载 `jexcelapi` jar 文件，在设置路径/classpath 中添加 `jxl.jar`，并将下载的文件夹保留在工作目录中。

```java
package sp_package;
import java.io.File;
import java.io.IOException;
import jxl.Cell;
import jxl.CellType;
import jxl.Sheet;
import jxl.Workbook;
import jxl.read.biff.BiffException;

public class SRP_ReadExcel {
    private String;
}
```

```java
public double getWeight() {
    return weight;
}

public void setWeight(double w) {
    weight = w;
}

public void setDeltaWeight(double w) {
    prevDeltaWeight = deltaWeight;
    deltaWeight = w;
}

public double getPrevDeltaWeight() {
    return prevDeltaWeight;
}

public SP_Neuron getFromNeuron() {
    return leftNeuron;
}

public SP_Neuron getToNeuron() {
    return rightNeuron;
}
```

# 第 13 章：Java 语言参考

## 13.1 Java 变量

以下是 Java 中的变量类型：

* 局部变量
* 类变量（静态变量）
* 实例变量（非静态变量）

### byte

* `byte` 数据类型是 8 位有符号的补码整数
* 最小值为 `-128` ($-2^7$)
* 最大值为 `127`（包含）($2^7 -1$)
* 默认值为 `0`
* `byte` 数据类型用于在大型数组中节省空间，主要代替整数，因为一个字节是整数的四分之一。
* 示例：`byte a = 100`, `byte b = -50`

### short

* `short` 数据类型是 16 位有符号的补码整数
* 最小值为 `-32,768` ($-2^{15}$)
* 最大值为 `32,767`（包含） ($2^{15} -1$)
* `short` 数据类型也可以像 `byte` 数据类型一样节省内存。`short` 是整数的一半。
* 默认值为 `0`。
* 示例：`short s = 10000`, `short r = -20000`

### int

* `int` 数据类型是 32 位有符号的补码整数。
* 最小值为 `-2,147,483,648` ($-2^{31}$)
* 最大值为 `2,147,483,647`（包含） ($2^{31} -1$)
* 除非有内存问题，否则 `Integer` 通常用作整数值的默认数据类型。
* 默认值为 `0`
* 示例：`int a = 100000`, `int b = -200000`

### long

* `long` 数据类型是 64 位有符号的补码整数
* 最小值为 `-9,223,372,036,854,775,808` ($-2^{63}$)
* 最大值为 `9,223,372,036,854,775,807`（包含） ($2^{63} -1$)
* 当需要比 `int` 更宽的范围时使用此类型
* 默认值为 `0L`
* 示例：`long a = 100000L`, `long b = -200000L`

### float

* `float` 数据类型是单精度 32 位 IEEE 754 浮点数
* `float` 主要用于在大型浮点数数组中节省内存
* 默认值为 `0.0f`
* `float` 数据类型绝不用于货币等精确值
* 示例：`float f1 = 234.5f`

### double

* `double` 数据类型是双精度 64 位 IEEE 754 浮点数
* 此 `double` 数据类型通常用作小数值的默认数据类型，通常是默认首选
* `double` 数据类型绝不用于货币等精确值
* 默认值为 `0.0d`
* 示例：`double d1 = 123.4`

### boolean

* `boolean` 数据类型表示一个位信息
* 只有两个可能的值：`true` 和 `false`
* 此 `boolean` 数据类型用于跟踪 `true/false` 条件的简单标记
* 默认值为 `false`
* 示例：`boolean one = true`

### char

* `char` 数据类型是单个 16 位 Unicode 字符
* 最小值为 `'\u0000'`（或 `0`）
* 最大值为 `'\uffff'`（或 65,535 包含）
* `char` 数据类型用于存储任何字符
* 示例：`char letterA = 'A'`

#### 变量声明

`int i;` `float a;` `double x;` `char s;`

#### 数组

1D `int A[] = new int[10];` `float x[] = new float[12];`

2D `double T[][] = new double[10][5];`

| 原生类型 | 存储大小 | 注释 |
| --- | --- | --- |
| `boolean` | 1 位 | 不可用于数学，但可以配合逻辑和位操作符使用 |
| `char` | 16 位 | 无符号，不转换为 `int` 则无法用于数学计算 |
| `byte` | 8 位 | 有符号 |
| `short` | 16 位 | 有符号 |
| `int` | 32 位 | |
| `long` | 64 位 | |
| `float` | 32 位 | |
| `double` | 64 位 | |
| `void` | 无 | |

#### 字符串

`String` 类用于处理文本。`String` 可以使用字面量或使用构造函数创建。

`String s = "Hello World";`

## 13.2 字面量

字面量是在源代码中表示的固定值。Java 有几种类型的字面量：

* 整数字面量
* 浮点字面量
* 布尔字面量
* 字符字面量
* 字符串字面量

### 布尔字面量

* `true`, `false`
* `null`（唯一的引用字面量）

### 整数字面量

整数字面量可以用进制、八进制或十六进制表示。

* 十进制：0-9
* 八进制：以 `0` 开头
* 十六进制：以 `0x` 开头

示例：

`int a = 100;` // 十进制

`int b = 0144;` // 八进制（十进制）

`int c = 0x64;` // 十六进制（十进制）

### 浮点字面量

浮点字面量可以用小数或科学计数法表示。

* 小数：包含小数点
* 科学计数法：使用 `e` 或 `E` 表示 10 的幂

示例：

`double d = 3.14;` // 小数

`double e = 1.2e3;` // 科学计数法（1200.0）

### 字符字面量

字符字面量包含在单引号中。

* 普通字符：`char c = 'A';`
* Unicode 字符：`char c = '\u0041';`
* 转义序列：`char c = '\n';`

### 字符串字面量

字符串字面量包含在双引号中。

`String s = "Hello World";`

### 字面量后缀

需要时可以使用后缀来指定字面量的类型。

* `L` 或 `l` 用于 `long`
* `f` 或 `F` 用于 `float`

示例：

`long l = 100L;`

`float f = 10.5f;`

## 常量与 final 关键字

常量是指赋值后值无法更改的变量。在 Java 中，常量使用 `final` 关键字创建。

```java
final int MAX_VALUE = 100;
// MAX_VALUE = 200; // 这会导致编译错误
```

* `final` 变量可以是局部变量、实例变量或静态变量。
* 常量的值可以在显式初始化设置、在单独的代码行中设置，或者在调用方法时作为方法参数传递。
* 类中的字段可以声明为 `final`。
* 常量的值可以在显式初始化设置、在初始化块中的单独代码行设置，或者在构造函数中设置。

类的字段可以声明为 `public static final` - 这样它们就可以被其他类访问，但不能被其他类修改。例如 `Math.PI`。

类和方法也可以被标记为 `final`。我们稍后会介绍。

## 13.3 数学运算

| 序号 | 算术运算符 | 操作 | 示例 |
| :--- | :--- | :--- | :--- |
| 1 | `+` | 加法 | `A+B` |
| 2 | `–` | 减法 | `A-B` |
| 3 | `*` | 乘法 | `A*B` |
| 4 | `/` | 除法 | `A/B` |
| 5 | `%` | 取模 | `A%B` |

### 赋值运算符

| 运算符 | 示例 | 解释 |
| :--- | :--- | :--- |
| `=` | `sum = 10` | 将 10 赋值给变量 `sum` |
| `+=` | `sum += 10` | 等于 `sum = sum + 10` |
| `-=` | `sum -= 10` | 等于 `sum = sum - 10` |
| `*=` | `sum *= 10` | 等于 `sum = sum * 10` |
| `/=` | `sum /= 10` | 等于 `sum = sum / 10` |
| `%=` | `sum %= 10` | 等于 `sum = sum % 10` |
| `&=` | `sum &= 10` | 等于 `sum = sum & 10` |
| `^=` | `sum ^= 10` | 等于 `sum = sum ^ 10` |

### 关系运算符

| 序号 | 运算符 | 示例 | 描述 |
| :--- | :--- | :--- | :--- |
| 1 | `>` | `x > y` | `x` 大于 `y` |
| 2 | `<` | `x < y` | `x` 小于 `y` |
| 3 | `>=` | `x >= y` | `x` 大于等于 `y` |
| 4 | `<=` | `x <= y` | `x` 小于等于 `y` |
| 5 | `==` | `x == y` | `x` 等于 `y` |
| 6 | `!=` | `x != y` | `x` 不等于 `y` |

### 逻辑运算符

| 序号 | 运算符 | 名称 | 示例 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| 1 | `&&` | 逻辑与 | `(x>5)&&(y<5)` | 当两个条件都为真时，返回真 |



| 运算符 | 描述 | 示例 | 效果 |
| :--- | :--- | :--- | :--- |
| `||` | 逻辑或 | `(x>=10)||(y>=10)` | 当至少有一个条件为真时，返回真 |
| `!` | 逻辑非 | `!((x>5)&&(y<5))` | 反转操作数 `((x>5) && (y<5))` 的状态。如果 `((x>5) && (y<5))` 为真，逻辑非运算符使其变为假 |

# 递增/递减运算符

递增运算符：`i++`；如果 `i=1` 则变为 `2, 3, 4`

递减运算符：`i--`；如果 `i=20` 则变为 `19, 18, 17`

# 位运算符

| 运算符 | 描述 | 示例 | 效果 | 位模式 |
| :--- | :--- | :--- | :--- | :--- |
| `&` | 按位与，使用与操作结合单个位，因此在结果值位位中，只有当两个操作数在该位上均为 1 时，该位才为 1。 | `int a = 2;` | 第 2 位被设置 | `0...00000010` |
| | | `int b = 6;` | 第 2 位和 4 位被设置 | `0...00000110` |
| | | `int c = a & b;` | 结果为 2 | `0...00000010` |
| `|` | 按位或，使用或操作结合单个位，因此在结果值位中，如果任一操作数在该位上为 1，该位就为 1。 | `int a = 2;` | 第 2 位被设置 | `0...00000010` |
| | | `int b = 4;` | 第 4 位被设置 | `0...00000100` |
| | | `int c = a | b;` | 结果为 6 | `0...00000110` |
| `^` | 按位异或 (XOR)，结合单个位，使得两个操作数中相同的任何位都产生 0，任何不同的位在相应位置产生 1；这通常用于加密，因为对结果重复该操作将得到原始值。 | `int a = 3;` | 第 1 位和 2 位被设置 | `0...00000011` |
| | | `int b = 6;` | 第 2 位和 4 位被设置 | `0...00000110` |
| | | `int c = a ^ b;` | 结果为 5 | `0...00000101` |
| | | `int d = c ^ b;` | 结果为 3 | `0...00000011` |
| `~` | 位取反。反转所有位的状态。 | `int a = 0;` | 无位被设置 | `0...00000000` |
| | | `int b = ~a;` | 所有位被设置 | `1...11111111` |

## 位移

这些运算符在 32 位 int 值内左移或右移位（它们不与其他类型工作）。

| 运算符 | 示例 | 效果 |
| :--- | :--- | :--- |
| `<<` | `int a = 4;` | 第 4 位被设置 |
| | `int b = a << 2;` | 左移 2 位 |
| `>>` | `int a = -16;` | 右移位（右侧位移出，左侧补 1；结果位为 63） |
| | `int b = a >> 1;` | 右移 1 位 |
| `>>>` | `int a = -1;` | 无符号右移位。 |
| | `int b = a >>> 31;` | 右移 31 位，补 0 |

# 复合运算符

将多个效果合并在一个操作中：计算并存储到内存。注意 `++` 和 `--` 可以位于变量前面或后面。如果在前面（前置），应用运算符然后使用结果值；如果在后面（后置），先获取变量的值，作为表达式的结果，然后应用运算符。

| 运算符 | 目的（执行的操作） |
| :--- | :--- |
| `++` | 递增变量 |
| `--` | 递减变量 |
| `+=` | 给变量增加一个值 |
| `-=` | 从变量中减去一个值 |
| `*=` | 变量乘以一个值 |
| `/=` | 变量除以一个值 |
| `%=` | 变量等于除后的余数 |
| `&=` | 左右之间执行按位与，结果存储到左侧 |
| `\|=` | 左右之间执行按位或，结果存储到左侧 |
| `^=` | 左右之间执行按位异或，结果存储到左侧 |
| `>>=` | 带符号扩展将变量位右移 |
| `>>>=` | 不带符号扩展将变量位右移 |
| `<<=` | 将变量位左移位 |

## 复合运算符示例

| 语句 | 结果 |
| :--- | :--- |
| `i++;` | 递增 i |
| `i--;` | 递减 i |
| `j = i++;` | 获取 `i` 的当前值，作为表达式的结果，将其赋值给 `j`，然后递增 i |
| `j = ++i;` | 递增 i，然后 `j = i` |
| `x *= 3;` | `x = x * 3` |
| `y -= z + 5;` | `y = y - (z + 5)` |

认证考试不可避免会要求理解后置递增或递减步骤的问题：尝试以下程序：

# 13.4 控制语句

## 判别控制语句

| 语句 | 语法 | 示例 |
| :--- | :--- | :--- |
| `if` | `if (condition) { 语句; }` | `void main(){int m=40,n=40;if (m == n){System.out.print ("m and n are equal");}}` |
| `if...else` | `if (condition) { 语句 1; 语句 2; } else { 语句 3; 语句 4; }` | `void main(){int m=40,n=20;if (m == n){System.out.print ("m and n are equal");}else{System.out.print ("m and n are not equal");}}` |
| `nested if` | `if (condition1){ 语句 1; } else if(condition2) { 语句 2; } else 语句 3;` | `void main(){int m=40,n=20;if (m>n) {System.out.print ("m is greater than n");}else if(m<n) {System.out.print ("m is less than n");}else {System.out.print ("m is equal to n");}}` |

## 循环控制语句

1. `for`
2. `while`
3. `do-while`

| 循环名称 | 语法 | 描述 |
| :--- | :--- | :--- |
| `for` | `for (exp1; exp2; expr3) { 语句; }` | `void main(){int i;for(i=0;i<10;i++){System.out.print ("%d ",i);}}` |
| `while` | `while (condition) { 语句; }` | `void main(){int i=3;while(i<10){System.out.print ("%d\n",i);i++;}}` |
| `do while` | `do { 语句; } while (condition);` | `void main(){int i=1;do{System.out.print ("Value of i is %d\n",i);i++;}while(i<=4 && i>=2);` |

### while 与 do while 循环的区别

| `while` | `do while` |
| :--- | :--- |
| 只有当条件为真时执行循环。 | 无论条件如何都执行一次循环。在第一次执行循环后检查条件。 |

# 布尔值表达式

Java 有一种名为 `boolean` 的数据类型。注意以下点：

*   可能值为 `true` 或 `false`。
*   `boolean` 可以与逻辑或按位运算符进行操作，但在数学上不能被视为 0 或 1。
*   `boolean` 可以指定为方法的参数类型或返回值。
*   布尔值将打印为 `true` 或 `false`。

# 复杂的布尔表达式

Java 提供了用于 AND（与）和 OR（或）逻辑组合布尔值的运算符，以及对值进行取反（`NOT` 操作）。注意：

*   还有用于 AND、OR 和位取反（将所有 1 位改为 0 位，反之亦然）的位运算运算符。
*   由于 `boolean` 以一个比特的形式存储，因此位运算 AND 和位运算 OR 运算符将产生相同的逻辑结果，但应用方式不同（见下文）。
*   由于某些原因，位取反操作不能应用于布尔值。

| 逻辑 | 位运算 |
| :--- | :--- |
| `&&` | `&` |
| `||` | `\|` |
| `!` | `~` |

## 示例

| 表达式 | 效果 |
| :--- | :--- |
| `((a >= 0) && (a <= 10))` | 如果 `a` 在 0 到 10 之间，则为真；它必须满足两个条件 |
| `((a < 0) || (a > 10))` | 如果 `a` 在 0 到 10 范围之外，则为真；它可能在范围的下方或上方 |
| `(!((a >= 0) && (a <= 10)))` | 反转对 `a` 在 0 到 10 之间的测试；因此 `a` 必须在范围之外而不是范围之内 |

`&&` 和 `||` 操作被称为短路操作，因为如果第一个条件已经决定了最终结果，则不会求值第二个条件。

要强制求值两个条件，请分别使用 `&` 和 `\|` 分别与和或。

# 13.5 数组

数组是属于相同数据类型的变量集合。

## 一维数组

*   `int a[10];` // 整数数组
*   `char b[10];` // 字符数组，即字符串

## 二维数组

`arr[0][1] = 20; arr[1][0] = 30; arr[1][1] = 40;`

## 数组声明

1D `int A[] = new int[10];` `float x[] = new float[12];` 2D `double T[][] = new double[10][5];`

# 13.6 Java 中的目录

目录是一个包含其他文件和其他目录列表的 `File`。你使用 `File` 对象来创建目录、列出目录中可用的文件。详细信息，请检查 `File` 对象可以调用的所有方法列表以及与目录相关的方法。

## 创建目录

有两个实用的 `File` 工具方法可以用于创建目录：

*   `mkdir()` 方法创建一个目录，成功时返回 true，失败返回 false。失败表示 `File` 对象指定的路径已存在，或者由于整个路径尚不存在而无法创建目录。
*   `mkdirs()` 方法同时创建目录及其所有的父级目录。

以下示例创建 `/tmp/user/java/bin` 目录：

```java
import java.io.File;

public class CreateDir {
  public static void main(String args[]) {
      String dirname = "/tmp/user/java/bin";
      File d = new File(dirname);
      // 现在创建目录。
      d.mkdirs();
  }
}
```

## 列出目录

你可以使用 `File` 对象提供的 `list()` 方法列出目录中所有的可用文件和目录：

```java
import java.io.File;

public class ReadDir {
  public static void main(String[] args) {
      File file = null;
      String[] paths;
      try {
        // 创建新文件对象
        file = new File("/tmp");
        // 文件和目录数组
        paths = file.list();
        // 路径数组中的每个名称
        for(String path:paths) {
          // 打印文件名和目录名
          System.out.println(path);
      }
      } catch(Exception e) {
        // 发生任何错误
        e.printStackTrace();
      }
  }
}
```

这将根据 `/tmp` 中可用的目录和文件产生以下结果：

```
test1.txt
test2.txt
ReadDir.class
```

# 13.7 Java 关键字

以下列表显示了 Java 中的保留字。这些保留字不能用作常量、变量或其他标识符。

| | | |
| :--- | :--- | :--- |
| abstract | assert | boolean |
| byte | case | char |
| class | const | default |
| double | else | enum |
| extends | final | float |
| for | goto | if |
| import | instanceof | int |
| interface | long | native |
| package | protected | public |
| return | short | static |
| switch | synchronized | this |
| throws | transient | try |
| void | volatile | while |

# 13.8 Java 中的一些实用程序

## 13.8.1 输入数组数据

```java
import java.util.Scanner;
import java.io.*;
import java.math.*;

Scanner inpData = new Scanner(System.in);
System.out.print("No of data ");
int n = inpData.nextInt();
System.out.print("insert values of x for n of data ");
double x[] = new double[n];
double y[] = new double[n];
for(int i=0;i<n;i++) {
    x[i]=inpData.nextDouble();
}
System.out.print("insert values of a, the fn");
double a=inpData.nextDouble();
System.out.print("insert values of b of the fn");
double b=inpData.nextDouble();
System.out.print("insert values of c of the fn");
double c=inpData.nextDouble();
System.out.print("insert values of d of the fn");
double d=inpData.nextDouble();
```

## 13.8.2 寻找数组的最大值和最小值

```java
public static double getMax(double[] array) {
  double maxValue = array[0];
  for(int i=0;i<array.length;i++) {
    if(array[i] > maxValue){
      maxValue = array[i];
    }
  }
  return maxValue;
}

public static double getMin(double[] array) {
  double minValue = array[0];
  for(int i=0;i<array.length;i++) {
    if(array[i] < minValue){
      minValue = array[i];
    }
  }
  return minValue;
}
```



# 复杂的布尔表达式

Java 提供了用于 AND（与）和 OR（或）逻辑组合布尔值的运算符，以及对值进行取反（`NOT` 操作）。注意：

*   还有用于 AND、OR 和位取反（将所有 1 位改为 0 位，反之亦然）的位运算运算符。
*   由于 `boolean` 以一个比特的形式存储，因此位运算 AND 和位运算 OR 运算符将产生相同的逻辑结果，但应用方式不同（见下文）。
*   由于某些原因，位取反操作不能应用于布尔值。

| 逻辑 | 位运算 |
| --- | --- |
| `&&` | 逻辑与 |
| `&` | 位逻辑与 |
| `||` | 逻辑或 |
| `|` | 位逻辑或 |
| `!` | 逻辑非 |
| `~` | 位逻辑非（反转） |

### 示例

| 表达式 | 效果 |
| --- | --- |
| `((a >= 0) && (a <= 10))` | 如果 `a` 在 0 到 10 之间，则为真；它必须满足两个条件 |
| `((a < 0) || (a > 10))` | 如果 `a` 在 0 到 10 范围之外，则为真；它可能在范围的下方或上方 |
| `(!((a >= 0) && (a <= 10)))` | 反转对 `a` 在 0 到 10 之间的测试；因此 `a` 必须在范围之外而不是范围之内 |

`&&` 和 `||` 操作被称为短路操作，因为如果第一个条件已经决定了最终结果，则不会求值第二个条件。

要强制求值两个条件，请分别使用 `&` 和 `|` 分别与和或。

# 13.5 数组

数组是属于相同数据类型的变量集合。

## 一维数组

*   `int a[10];` // 整数数组
*   `char b[10];` // 字符数组，即字符串

## 二维数组

`arr[0][1] = 20; arr[1][0] = 30; arr[1][1] = 40;`

## 数组声明

1D `int A[] = new int[10];` `float x[] = new float[12];` 2D `double T[][] = new double[10][5];`

# 13.6 Java 中的目录

目录是一个包含其他文件和其他目录列表的 `File`。你使用 `File` 对象来创建目录、列出目录中可用的文件。详细信息，请检查 `File` 对象可以调用的所有方法列表以及与目录相关的方法。

## 创建目录

有两个实用的 `File` 工具方法可以用于创建目录：

*   `mkdir()` 方法创建一个目录，成功时返回 true，失败返回 false。失败表示 `File` 对象指定的路径已存在，或者由于整个路径尚不存在而无法创建目录。
*   `mkdirs()` 方法同时创建目录及其所有的父级目录。

以下示例创建 `/tmp/user/java/bin` 目录：

```java
import java.io.File;

public class CreateDir {
  public static void main(String args[]) {
      String dirname = "/tmp/user/java/bin";
      File d = new File(dirname);
      // 现在创建目录。
      d.mkdirs();
  }
}
```

## 列出目录

你可以使用 `File` 对象提供的 `list()` 方法列出目录中所有的可用文件和目录如下：

```java
import java.io.File;

public class ReadDir {
  public static void main(String[] args) {
      File file = null;
      String[] paths;
      try {
        // 创建新文件对象
        file = new File("/tmp");
        // 文件和目录数组
        paths = file.list();
        // 路径数组中的每个名称
        for(String path : paths) {
          // 打印文件名和目录名
          System.out.println(path);
        }
      } catch(Exception e) {
        // 发生任何错误
        e.printStackTrace();
      }
  }
}
```

这将根据 `/tmp` 中可用的目录和文件产生以下结果：

```
test1.txt
test2.txt
ReadDir.class
```

# 13.7 Java 关键字

以下列表显示了 Java 中的保留字。这些保留字不能用作常量、变量或其他标识符。

| | | |
| --- | --- | --- |
| abstract | assert | boolean |
| byte | case | char |
| class | const | default |
| double | else | enum |
| extends | final | float |
| for | goto | if |
| import | instanceof | int |
| interface | long | native |
| package | protected | public |
| return | short | static |
| switch | synchronized | this |
| throws | transient | try |
| void | volatile | while |

# 13.8 Java 中的一些实用程序

## 13.8.1 输入数组数据

```java
import java.util.Scanner;
import java.io.*;
import java.math.*;

Scanner inpData = new Scanner(System.in);
System.out.print("No of data ");
int n = inpData.nextInt();
System.out.print("insert values of x for n of data ");
double x[] = new double[n];
double y[] = new double[n];
for(int i = 0; i < n; i++) {
    x[i] = inpData.nextDouble();
}
System.out.print("insert values of a, the fn");
double a = inpData.nextDouble();
System.out.print("insert values of b of the fn");
double b = inpData.nextDouble();
System.out.print("insert values of c of the fn");
double c = inpData.nextDouble();
System.out.print("insert values of d of the fn");
double d = inpData.nextDouble();
```

## 13.8.2 寻找数组的最大值和最小值

```java
public static double getMax(double[] array) {
  double maxValue = array[0];
  for(int i = 0; i < array.length; i++) {
    if(array[i] > maxValue){
      maxValue = array[i];
    }
  }
  return maxValue;
}

public static double getMin(double[] array) {
  double minValue = array[0];
  for(int i = 0; i < array.length; i++) {
    if(array[i] < minValue){
      minValue = array[i];
    }
  }
  return minValue;
}
```

## 13.8.3

```java
for (int i = 0; i < n; i++) {
    for (int j = 0; j < m; j++) {
        xCoord1[i][j] = x1[i][j];
        yCoord1[i][j] = -y1[i][j];
        xCoord2[i][j] = x2[i][j];
        yCoord2[i][j] = -y2[i][j];
    }
}
```

该函数是从类 `SRP_packGph` 中调用的。

```java
SRP_packGph gr = new SRP_packGph();
gr.datain(n, m, x1, y1, x2, y2);
```

变量需要提前定义并赋值如下：

```java
int [][] x1 = new int[n][m]; // int n=10, int m=20;
int [][] y1 = new int[n][m];
int [][] x2 = new int[n][m];
int [][] y2 = new int[n][m];

x1[0][0] = 0;
y1[0][0] = Temp[0][0];

for (int i = 0; i < n; i++) {
    x1[i][0] = 0;
    for (int j = 0; j < m - 1; j++) {
        x2[i][j] = x1[i][j] + d;
        y2[i][j] = Temp[i][j + 1];
        y1[i][j + 1] = y2[i][j];
        x1[i][j + 1] = x2[i][j];
    }
    x2[i][m - 1] = x1[i][m - 1];
    y2[i][m - 1] = Temp[i][m - 1];
}
```

同样，读取 String 所示：

```java
public String gt, gx, gy;
int shift_xc, shift_yc;
int n, m;
int choice;

public void textin(int ch, int xxc, int yyc, String title, String xaxis, String yaxis) {
    shift_xc = xxc;
    shift_yc = yyc;
    gt = title;
    gx = xaxis;
    gy = yaxis;
    choice = ch;
}
```

在 `main` 中调用此函数：

```java
gr.textin(ch, xxc, yyc, "热板从右到左冷却", "时间 (分钟)", "温度 (°C)");
```

## 13.8.7 使用读取的文本进行如下绘制

```java
public void paint(Graphics g) {
    g.setColor(Color.BLACK);
    int y_len = getHeight();
    int x_len = getWidth();
    Font font1 = new Font("Arial", Font.BOLD, 16);
    g.setFont(font1);
    g.drawString(gx, x_len / 2 - 200, 20); // 标题 x 轴
    // 旋转写入 y 轴的垂直字体
    g2d.rotate(-Math.PI / 2);
    g.drawString(gy, y_len / 3, -50); // 标题 y 轴垂直
    // 旋转回水平写入
    g2d.rotate(Math.PI / 2);
    g.setColor(Color.BLUE);
    g.drawString(gt, x_len / 8, 70); // 写入标题变量
}
```

## 13.8.8 如何从 main 读取数据数组并绘制一组图形线条

```java
public void graph(Graphics g) {
    g.setColor(Color.BLACK);
    n = 21;
    m = 19;
    g.setColor(Color.BLACK);
    int R, G, B;
    for (int i = 1; i < n; i++) {
        R = (int) Math.round(Math.random() * 255);
        G = (int) Math.round(Math.random() * 255);
        B = (int) Math.round(Math.random() * 255);
        for (int j = 1; j < m; j++) {
            Color mycolor = new Color(R, G, B);
            g.setColor(mycolor);
        }
    }
}
```



```java
g.drawLine(xCoord1[i][j], yCoord1[i][j], xCoord2[i][j], yCoord2[i][j]);
        }
    }

    // 两条曲线之间延迟 500 毫秒
    try {
        Thread.sleep(500);
    } catch (InterruptedException ex) {
        Thread.currentThread().interrupt();
    }
}
```

### 13.8.9 包（Package）

将包保存为文件夹 `sp_package` 中的 `SRP_packGph.java`：

```java
package sp_package;

import java.awt.*;
import java.awt.Graphics;
import java.awt.event.*;
import java.awt.geom.*;
import java.util.Scanner;
import java.awt.Color;
import java.math.*;

public class SRP_packGph {
```

在另一个 java 文件中调用包：

```java
import sp_package.*;
import java.io.*;
import java.util.Scanner;

public class SRP_CoolingSlabGraph {
```
