
# Java 计算机科学 AP 考试指南

模拟考试贡献者：Roger Frank, Judith Hromcik, Gary Litvin, Dave Wittry

## 马萨诸塞州安德弗尔菲利普斯学院

模拟考试贡献者：

- Roger Frank
Ponderosa High School，科罗拉多州帕克尔

- Judith Hromcik
Arlington High School，德克萨斯州阿灵林顿

- Gary Litvin
Skylight Publishing，马萨诸塞州安德弗尔

- Dave Wittry
台北美国学校（台湾）

2 3 4 5 6 7 8 9 10 12 11 10 09 08

## 美国于美国

前言 vii

如何使用本书 xi

# 第 1 章 考试格式、评分与技巧 1

- 1.1. 考试格式与材料 1
- 1.2. Java 子集 2
- 1.3. 评分 5
- 1.4. A 还是 AB？ 6
- 1.5 考试技巧 8

# 第 2 章 Java 特性，第一部分 11

- 2.1. 算术、关系和逻辑运算符 11
- 2.2. 条件语句与循环 20
- 2.3. 字符串 28
- 2.4. `Integer` 和 `Double` 类 32
- 2.5. 数组 33
- 2.6. `ArrayList` 类 39

# 第 3 章 Java 特性，第二部分 43

- 3.1. 类 43
- 3.2. 方法 47
- 3.3. 随机数 55
- 3.4. 输入与输出 58
- 3.5. 异常 60

# 第 4 章 程序设计与 OOP 概念 65

- 4.1. 计算机系统 65
- 4.2. 程序设计与开发方法论 65
- 4.3. 继承 67
- 4.4. 类层次结构 71
- 4.5. 多态 74
- 4.6. 接口 77
- 4.7. “设计”题 82

# 第 5 章 算法 87

- 5.1. 迭代 87
- 5.2. 顺序查找与二分查找 95
- 5.3. 选择排序与插入排序 98
- 5.4. 递归 100
- 5.5. 归并排序与快速排序 105
- 5.6. 数据组织题 108

# 第 6 章 AB 主题：链表、栈、队列、树等 113

- 6.1. 概述 113
- 6.2. 列表 115
- 6.3. 栈与队列 125
- 6.4. 集合与映射 129
- 6.5. 二叉树 132
- 6.6. 哈希算法 141
- 6.7. 优先队列、堆与堆排序 143
- 6.8. Big-Oh 分析 146

# 第 7 章 GridWorld 案例研究 151

- 7.1. 引言 151
- 7.2. `Location` 类 155
- 7.3. `Actor` 类 159
- 7.4. 虫、花朵与岩石 163
- 7.5. 昆虫 165
- 7.6. GridWorld 实现 169
- 7.7. 技巧 174

# 第 8 章 往年自由回答题的解析答案 177

# 模拟考试 179

# 答案与解析 331

# 索引 365

# viii 前言

要涵盖的内容非常多，本书的目标并非从零开始教你一切。对于这一点，你需要一本完整的教材。大多数参加考试的学生都在学校里修了 AP 科学课程。本书的目标是：

- 描述考试格式和要求
- 描述 Java 子集
- 对已知知识进行有效复习，重点关注难题和常见错误
- 帮助你识别并填补知识漏洞
- 提供模拟考试题及其答案和解析

计算机科学的 AP 考试是纸笔考试。虽然你需要一台带有 Java 的计算机来学习编程和实现算法，但本书不需要使用计算机。事实上，在进行练习时最好不要使用计算机，这样你就可以习惯考试的形式和环境。语法的正确性是这里的重点。编译器通常可以帮助检查的小错误（如漏掉分号或大括号）可能不会影响你的考试分数。你只需要计算机来访问 AP Central 和我们的网站获取最新更新和往年自由回答题解答。

第 1 章解释了格式、所需材料以及考试的 Java 子集，并提供了关于评分和考试技巧的信息。第 2 章和第 3 章涵盖考试所需的 Java 元素。第 4 章涉及 OOP 题。第 5 章涉及算法。第 6 章复习额外的 AB 考试类型：列表、栈、队列、树等。第 7 章回顾 GridWorld 案例研究。复习章节包含模拟单选题，并对所有错答案给出详细解释。第 8 章实际上位于本书配套网站 `http://www.skylit.com/prepared/`。它提供了往年考试的解析。书末有五套模拟题——三套 A 和两套 AB，没有重叠——随后是答案和解析。

祝你好运！

除了提供模拟题外，Gary Litvin 还通过与作者紧密合作并编辑所有示例题和模拟题，帮助了这本书成为现实。他还创建并维护了这本书的配套网站。

我们诚挚地感谢 Roger Frank 和 Dave Wittry。他们不仅贡献了模拟题，还对整本书草稿进行了非常详尽的审查，并提出了许多修改和改进建议。

我们感谢圣博纳文大学的 David Levine，他提出了许多重要的改进建议，帮助我们发现了技术上和风格上的错误，并指出了《准备好了》（Be Prepared）第一版中需要澄清的问题。

我们感谢许多老师和学生，他们提醒我们注意了本书早期版本中的几处错误。

我们特别感谢 Margaret Litvin，她通过细致且周全的编辑让这本书更易读。

最后，我们感谢美国童子军团允许我们在书名中引用他们的座右号。

# 作者简介

**Maria Litvin** 自 1987 年以来一直在马萨诸塞州安德弗弗的菲利普斯学院（Phillips Academy）教授计算机科学和数学。她是 AP 计算机科学考试阅卷员和题目负责人，并作为大学理事（The College Board）的顾问为高中计算机科学教师提供 AP 培训。Maria 曾获得 1999 年西门子新英地区数学、科学与技术先进奖以及 2003 年 RadioSh 国家教师奖。在加入菲利普斯学院之前，Maria 在波士顿大学教授计算机科学。Maria 是《C++ for Prepared》的作者，以及《C++ for You+: An Introduction to Programming and Computer Science》的合著者，这本书已成为 AP 计算机科学课程的高中教材之一。最近，Mary 和 Gary Litvin 合著了《Java Methods》和《Java Methods AB & AB: Object-Oriented Programming and Data Structures》（Skylight Publishing, 2006）。

**Roger Frank** 自 1992 年以来一直在科罗拉多州的庞德罗萨高中（Ponderosa High School）教授 AP 计算机科学和数学。Roger 在 2002 年至 2004 年担任 AP 计算机科学考试阅卷员。在从事教学之前，Roger 曾在业界工作，曾担任数字设备公司（Digital Equipment Corporation）、国际医疗公司（International Medical Corporation）、洛斯阿拉莫斯实验室（Los Alamos Laboratory）的硬件工程经理和国家技术总监，拥有电子与计算机工程学士学位、MBA 学位和数学硕士。

**Judy Hromcek** 是德克萨斯州阿灵顿市阿灵顿高中（Arlington High School）的 AP 计算机科学教师。Judy 在 2001 年至 2005 年担任 AP 计算机科学开发委员会成员，曾担任阅卷员，目前是 AP 计算机科学考试阅卷的题目负责人。自1995 年以来她一直是大学理事会的顾问，主持过多次计算机科学暑期学校。Judy 获得了2000年大学理事会西南地区计算机科学特别认可奖。她在德克萨斯大学阿灵顿分校获得数学学士学位和教育教学（数学与计算机科学）硕士学位。

**Gary Litvin** 是《C++ for You+》和《Java Methods》的合著者。Gary 在软件开发的多个领域工作过，包括人工智能、模式识别、计算机图形和神经网络。作为 Skyl Software, Inc. 的创始人，他开发了 SKYLIGHTS/GX，这是 C 和 C++ 最早的视觉编程工具之一。Gary 领导了多项先进产品的开发，包括触摸屏开发工具、OCR 和手写识别系统以及信用卡欺诈检测软件。

**Dave Wyatt** 曾在加利福尼亚州富尔特顿高中（Troy High School）教授过科学、数学和技术的各种计算机科学课程。他在创新计算机科学课程的开发和教学方面发挥了作用，这为 Troy取得了巨大的成功。过去三年，大学理事认为 Troy 是“帮助广泛的人群获得 AP 计算机科学 A 和 AB 的大学水平掌握”的世界领先教师。1999-2005 年间，他是 AP 计算机科学考试的阅卷员。Dave 在伊利诺伊州莱克森林学院获得计算机科学/数学学士学位，并在南伊利诺伊州立大学获得计算机科学硕士学位。Dave 于 2005 年搬到台湾，现在于台北美国学校教授 AP 计算机科学和数学。

# 如何使用本书

复习章节中的多选题通过框内的数字进行标记：

- 1

它们的答案由 ⬠ 和 ⬮ 隔开。

仅与 AB 考试相关的注释由 ⌈ 和 ⌋ 隔开。例如：

> AB 考试还包括标准数据结构：链表、栈、队列和树。 ⌋

配套网站

```
http://www.skylit.com/beprepared/
```

是书中不可缺的一部分。它包含了历届考试开放答题的注释答案、最新的案例研究信息以及相关链接。GridWorld 案例研究将在 2008 年首次使用，并将保留多年。请查看本书的网站获取最新信息，并确保你拥有《准备好了》的最新版本。

> 我们的模拟题可能比实际考试更难，因此如果花费时间更多，请不要慌。我们在许多开放答题中包含了三个部分，而实际考试题可能只有两个部分。

过去，A 级和 AB 考试共享一或两道开放答题。我们的 A 和 AB 模拟题不重叠，但我们 A 考试中的所有题目对 AB 考试来说也很有练习价值。同样，我们 AB 考试中的许多题目只需要 A 级材料。

# 第 1 章 考试格式、评分与技巧

## 1.1. 考试格式与材料

考试分为两个部分。图 1-1 显示了 AP 科学考试的格式。第一部分由 40 道选择题组成，总时间为1 小时 15 分钟。第二部分由开放答题组成，总时间 1 小时 45 分钟。

|  | 时间 |
| :--- | :--- |
| 第一部分：选择题 | 1 小时 15 分 |
| 第二部分：开放答题 | 1 小时 45 分 |
| 总计 | 3 小时 |

选择题部分是通用计算机科学术语、程序设计决策、Java 语法特定元素、类属性、Java 代码片段逻辑分析以及与案例相关的混合。

在过去的考试中，学生并没有被要求编写完整的程序。通常他们被要求根据给定的头部编写构造函数或方法。目的第二部分通常引用第一部分实现的类或方法，但每个部分是独立评分的，即使你的 (a) 部分不正确，也能获得 (b) 部分的满分。(c) 部分可能会对你的实现提问，或者要求你编写一个使用 (a) 和/或 (b) 部分的新方法。

开放答题通常包括一个“设计”题，你被要求设计一个小型类，然后编写它或其片段，或用于问题的其他部分。你的设计将根据类功能的合理性、方法和变量命名的合理性与其他标准进行评分。

一个开放答题基于案例研究。它可能要求你扩展案例研究类并编写一个新方法或重写现有方法。

## 1.2. Java 子集

开发委员会定义了一个在考试中测试的限制性 Java 子集。子集的目的是让 AP 计算机科学计划关注通用概念而非 Java 的细节，并限制范围，特别是与 Java 特性相关的材料。该子集在大学理事的《高级汉语计算机科学课程说明》中有描述；我们提供了本书网站链接 `http://www.skylit.com/beprepared/`。AB “超集”还定义了 `ListNode` 和 `TreeNode` 类（见第 6 章）。

子集包含什么？实际上包含很多内容。

- `boolean`, `int`, 和 `double` 原始数据类型。`(int)` 和 `(double)` 强制类型转换。
其他原始数据类型（包括 `char`）不包含在该子集中，在考试中应尽量避免。

- 赋值运算符 (`=`)，算术运算符 (`+`, `-`, `*`, `%`), 增/减运算符 (`++`, `--`)，复合赋值运算符 (`+=`, `-=`, `*=`, `%`), 关系运算符 (`<`, `>`, `>=`, `!=`) 以及逻辑运算符 (`&&`, `||`)。仅使用 `++` 和 `--` 的后置形式 (`x++` 或 `x--`)，不要在表达式中使用它们。

- 用于字符串拼接的 `+` 和 `--` 运算符。`String` 的 `compareTo`、`equals`、`length`、`substring` 和 `indexOf(String s)` 方法。字面量字符串中的 `\n`、`\\` 和转义序列。

- `System.out.print`; `System.out.println`;

- 一维数组、`array.length`、对象数组、初始化数组如 `int[] x = {1,2,3};`。

- `if-else`, `for` (包括 "each" `for`), `while`, `return`。但不包含 `do-while` 和 `switch`。

- 类。`new` 运算符，`public` 和 `private` 方法，`static` 方法，`static` `final` 变量（常量），重载方法，`null`。所有实例变量均为 `private`。默认初始化规则不在该子集中，考试中也不会出现。

- 继承，接口和抽象类，`extends`，`implements`。在子类中调用父类的构造函数（如 `super(...)`）。在子类中调用父类方法（如 `super.method(...)`）。将此对象传递给方法（如 `otherObject.method(this)`）。

- `NullPointerException`, `ArrayOutOfBoundsException`, `ArithmeticException`, `IllegalArgumentException`, `ClassCastException`。

- 库类和方法：

  - `String`: `length()`, `substring(...)`, `indexOf(String s)`
  - `Integer`: `Integer(int x)`, `intValue()`
  - `Double`: `Double(double x)`, `doubleValue()`
  - `Math`: `abs(double x)`, `pow(double base, double exp)`, `sqrt(double x)`, `random()`
  - `Random`: `nextInt(int n)`, `nextDouble()`

还要理解所有对象的 `toString` 方法，`Comparable<T>` 接口以及 `String`、`Integer` 和 `Double` 的 `compareTo` 和 `equals`。

- `ArrayList<E>`（见第 2.6 节）。

# 第 1 章 ~考试格式、评分标准及技巧

## A 考试：

以上所有内容，外你应该能够：

- 编写抛出异常的代码，例如 `throw new NoSuchElementException();` `throw new IllegalArgumentException();`。
- 设计并实现接口、抽象类、子类。
- 使用集合接口和类的小部分方法：`List<E>`, `ArrayList<E>`, `LinkedList<E>`, `Iterator<E>`, `ListIterator<E>`, `Stack<E>`, `Queue<E>`, `PriorityQueue<E>`, `Set<E>`, `TreeSet<E>`, `HashSet<E>`, `Map<K, V>`, `TreeMap<K, V>`, `HashMap<K, V>`。

> 如果你在简答题中必须超出该子集，你可能误解了题目，并且让问题变得比实际上更复杂。

不属于 AP 子集且应避免的内容包括以下：

- Java 语法禁忌，例如 `? :` 三元运算符和“逗号”运算符
- 表达式中的 `++` 和 `--`（例如 `a[i++]`）
- 除 `boolean`, `int` 和 `double` 外的原始数据类型（`char` 不在子集中）
- 所有位运算逻辑运算符

同样不在子集中且不会测试的：

- `switch` 语句、`do-while` 循环、循环中的 `continue`
- `++` 和 `--` 运算符的前置形式 (`++k`, `--k`)
- 库类（如 `StringBuffer`, `Arrays`, `DecimalFormat` 等），除非在子集中被明确列出
- 检错型异常（checked exceptions）和 `try-catch-finally` 语句
- `System.in` 和 `Scanner`；除 `System.out.print` 和 `System.out.println` 之外的任何输入输出
- `enum` 数据类型

## 1.3. 评分

考试按 1 到 5 分的分值进行评分。5 分和 4 分分别被称为“极优秀”（extremely well qualified）和“优秀”（well qualified），通常会获得为计算机科学 AP 考试提供学分或分班的大学的认可。3 分“合格”（qualified），特别是在 A 考试中，某些大学可能不予承认学分或分班。2 分“可能合格”（possibly qualified）和 1 分“不建议”（no recommendation）将无法获得大学学分或分班。

表 1-1 显示了 2004 年 A 和 AB 考试的统计数据和分数分布。2004 年，有 13,834 名考生参加 A 考试，5,807 名考生参加 AB 考试。

| | 计算机科学 A | | 计算机科学 AB | |
|---|---|---|---|---|
| | 人数 | % | 人数 | % |
| 学生 | 13,834 | 100.0 | 5,807 | 100.0 |
| 分数： | 5 | 2,572 | 18.6 | 1,574 | 27.1 |
| | 4 | 3,270 | 23.6 | 1,058 | 18.2 |



| | 计算机科学 A | | 计算机科学 AB | |
|---|---:|---:|---:|---:|
| | 人数 | % | 人数 | % |
| 学生 | 13,834 | 100.0 | 5,807 | 100.0 |
| 分数： | 5 | 2,572 | 18.6 | 1,574 | 27.1 |
| | 4 | 3,270 | 23.6 | 1,058 | 18.2 |
| | 3 | 2,102 | 15.2 | 1,020 | 17.6 |
| | 2 | 1,309 | 9.5 | 702 | 12.1 |
| | 1 | 4,581 | 33.1 | 1,453 | 25.0 |
| 3 分或以上 | 7,944 | 57.4 | 3,652 | 57.4 |

表 1-1 2004 年 A 和 AB 考试的公布统计数据和分数分布。2004 年，有 13,834 名考生参加 A 考试，5,807 名考生参加 AB 考试。

## 1.3 评分

考试按 1 到 5 分的分值进行评分。5 分和 4 分分别被称为“极优秀”（extremely well qualified）和“优秀”（well qualified），通常会获得为计算机科学 AP 考试提供学分或分班的大学的认可。3 分“合格”（qualified），特别是在 A 考试中，某些大学可能不予承认学分或分班。2 分“可能合格”（possibly qualified）和 1 分“不建议”（no recommendation）将无法获得大学学分或分班。

表 1-1 显示了 2004 年 A 和 AB 考试的统计数据和分数分布。2004 年，有 13,834 名考生参加 A 考试，5,807 名考生参加 AB 考试。

| | 计算机科学 A | | 计算机科学 AB | |
|---|---:|---:|---:|---:|
| | 人数 | % | 人数 | % |
| 学生 | 13,834 | 100.0 | 5,807 | 100.0 |
| 分数： | 5 | 2,572 | 18.6 | 1,574 | 27.1 |
| | 4 | 3,270 | 23.6 | 1,058 | 18.2 |
| | 3 | 2,102 | 15.2 | 1,020 | 17.6 |
| | 2 | 1,309 | 9.5 | 702 | 12.1 |
| | 1 | 4,581 | 33.1 | 1,453 | 25.0 |
| 3 分或以上 | 7,944 | 57.4 | 3,652 | 57.4 |

## 1.4 AB 或 A？

表 1-1 显示出很大比例的 AB 考生获得了 5 分。对于 A 考试，这种加权方式取决于选择题和简答题。

```java
totalScore = MC_coeff * countCorrect + FR_coeff * count;
```

## 1.5 答题技巧

有些事情是显而易见的：

- 如果你花时间读了一道选择题，但决定跳过所有选项，请再多花十秒钟。你可能在没有察觉的情况下已经排除了一两个错误答案。
- 如果一个公共段落提到了一组问题，而你花时间阅读了它，请尝试该组中的每一个问题。
- 在跳转到题目中包含的代码之前，务必阅读题目。

关于回答开放性题，有几点重要的需要了解。

> 记住，所有开放性题的权重都是相等。不要假设第一题是最简单的，最后一题是最难的。

简而言之：保持整洁、直接和专业；考虑到你的阅卷老师；不要显风头。

具体来说：

1. 保持在 AP Java 子集范围内。
2. 记住你代码的优雅性并不加分。通常情况下，暴力法（brute-force approach）是最好的。你可能会浪费大量时间编写复杂的、非标准的代码，并在此过程中自欺欺，或者误导你的阅卷老师——毕竟，他们也是人。没有人会在计算机上测试你的代码。
3. 你代码的卓越效率并不加分，除非题目中明确说明了所需的 Big-Oh 复杂度。
4. 记住题目的 (b) 和 (c) 部分与之前的部分独立评分，而且实际上可能更容易：部分 (a) 可能要求你写一个方法，而部分 (b) 或部分 (c) 可能仅要求你使用它。

   在部分 (a) 中指定的方法在后续部分被调用是常见现象。尽管这样做，即使你的部分 (a) 是错误的或留了空白。不要在后面的部分中重新实现先几个部分的代码——这样做会浪费宝贵的时间并可能导致丢分。

5. “良好思考”的片段是有加分的。你可能不知道整个解决方案，但如果你已经阅读并理解了题目，尽管写下一些可能为你赢得部分分的代码片段。但不要花费太多时间即兴编写错误的代码。
6. 不要浪费时间擦掉大部分工作。相反，用一笔整洁的横线划掉你的工作，但那要在你有替代品之后。如果你没有时间重做，即使答案是错误的，也不要划掉它。代码错误不会被扣分，你会因此获得部分分。阅卷老师被指示不要阅读你任何划掉的代码。但如果你写了两个解决方案，务必划掉其中一个：否则页面上的第一个会被评分。
7. 快速阅读关于方法头部的注释——它们通常以更正式的方式陈述任务，有时会给出提示。假设所有前提条件已满足——不要在你的代码中进行不必要的检查。
8. 一个常见的错误是忘记在非 `void` 方法中写 `return` 语句。确保返回的值与指定的类型匹配。
9. 不要忽略题目描述中的任何提示。如果为某个方法建议了某种算法（如“你可以使用以下算法”），不要反抗，直接做就好！如果描述说“你可以使用辅助方法”，请务必编写并使用一个：很有可能在没有辅助方法的情况下构解决方案要困难得多。
10. 记住，阅卷老师在每年六月的马拉松式评分期间，会连续地批改大量试卷。写得尽可能整洁。给代码留出空间（不要省纸）。
11. 始终正确地缩进你的代码。这有助于你和你的阅卷老师。如果你漏掉了一个大括号但代码缩进正确，阅卷老师（与 Java 编译器相比）可能会接受它。同样，如果你将每个语句单独放在一行，遗忘的分号可能不会被视为过错。
12. 遵循 Java 命名风格：所有方法、变量和参数的名称都以小写字母开头。为变量使用有意义但不冗长的名称。`count` 可能比 `a` 好；`sum` 可能比 `temp` 好；`row`、`col` 可能比 `i`、`j` 好。`k` 比 `loopControlVariable` 好。如果题目包含带有名称的代码示例，请在适当的情况下相同的名称。
13. 不要费心写注释；它们不加分，你会浪费宝贵的时间。偶尔你可以写一个非常简短的注释，说明你后续代码片段的意图。例如：

```java
// 找到第一个空座位：
...
```

14. 不要担心导入——假设所有必要的库类已导入。
15. 严格按照规范和前提条件编写代码。避免多余的“点缀”——你会丢分。除非专门要求，否则永远不要在解决方案中添加 `System.out.print`/`System.out.println`。
16. 在适当的情况下使用递归：通常在处理二叉树的方法中；否则如果被特别要求或特别有诱惑力。
17. 不要试图抓住出题者的歧义之处：没有人会听你的辩解，你会浪费时间。相反，尝试快速理解意图并写下你的答案。
18. 在时间结束之前不要放弃。利用你所有的时间并继续尝试。测试会在你还没意识到之前就结束。

以上所有内容，外你应该能够：

- 编写抛出异常的代码，例如 `throw new NoSuchElementException();`、`throw new IllegalArgumentException();`。
- 设计并实现接口、抽象类、子类。
- 使用集合接口和类的小部分方法：`List<E>`、`ArrayList<E>`、`LinkedList<E>`、`Iterator<E>`、`ListIterator<E>`、`Stack<E>`、`Queue<E>`、`PriorityQueue<E>`、`Set<E>`、`TreeSet<E>`、`HashSet<E>`、`Map<K, V>`、`TreeMap<K, V>`、`HashMap<K, V>`。

> 如果你在简答题中必须超出该子集，你可能误解了题目，并且让问题变得比实际上更复杂。

不属于 AP 子集且应避免的内容包括以下：

- Java 语法禁忌，例如 `? :` 三元运算符和“逗号”运算符。
- 表达式中的 `++` 和 `--`（例如 `a[i++]`）。
- 除 `boolean`、`int` 和 `double` 外的原始数据类型（`char` 不在子集中）。
- 所有位运算逻辑运算符。

同样不在子集且不会测试的：

- `switch` 语句、`do-while` 循环、循环中的 `continue`。
- `++` 和 `--` 运算符的前置形式（`++k`、`--k`）。
- 库类（如 `StringBuffer`、`Arrays`、`DecimalFormat` 等），除非在子集中被明确列出。
- 检错型异常（checked exceptions）和 `try-catch-finally` 语句。
- `System.in` 和 `Scanner`；除 `System.out.print` 和 `System.out.println` 之外的任何输入输出。
- `enum` 数据类型。

# 第 2 章 Java 特性，第一部分

## 2.1 变量；算术、关系和逻辑运算符

子集中包含的原始数据类型包括 `boolean`、`int` 和 `double`。在 Java 中，`int` 始终占用 4 个字节。`double` 占用 8 个字节，且范围巨大，但其精度约为 15 位数字。

在部分 (a) 中指定的方法在后续部分被调用是常见现象。尽管这样做，即使你的部分 (a) 是错误的或留了空白。不要在后面的部分中重新实现先几个部分的代码——这样做会浪费宝贵的时间并可能导致丢分。

（注：原文中 2.1 的 OCR 文本有严重损坏/重复；我提取了提供的核心信息）。

### 变量；算术、关系和逻辑运算符

这道题给了我们一个复习关于数据类型知识的机会。

A 是错误的：符号常量与变量没有太大区别。区别在于常量包含 `final` 关键字。类常量通常声明为静态变量。例如：

```java
public static final double PI = 3.14159265358973;
```

B 是正确的。虽然实数在程序中以十进制法表示，但 Java 编译器会将它们转换为一种特殊的浮点格式，占用 8 个字节且便于计算。

C 是错误的。数据类型本身并不决定变量的存储位置。它在内存中的位置取决于变量的使用位置及其分配方式：它是方法中的局部变量还是类的实例变量。

D 是正确的。有时不同类型的参数可能会被提升为方法预期的类型（例如，当你对 `int x` 调用 `Math.sqrt(x)` 时，`int` 可以提升为 `double`）。但情况并非总是如此（例如，`double` 无法替代 `String`）。答案是 D。

E 也是错误的。在 Java 中，你可以写 `a / b`，尽管 `a` 和 `b` 都是 `int` 类型。结果被截断为整数。

### 算术运算符

> 关于 Java 算术运算符最重要的记忆点是，结果的数据类型（甚至是每个中间结果）与操作数的数据类型相同。特别是，一个整数除以另一个整数的结果会被截断为整数。

例如：

```java
int n = 3;
double result;
result = (n + 1) * n / 2; // result 为 6.0
result = (n / 2) * (n + 1); // result 为 4.0
result = (1 / 2) * n * (n + 1); // result 为 0.0
```

为了避免截断，你必须注意数据类型，并且有时需要使用转换运算符。例如：

```java
int a, b;
double ratio;
ratio = (double) a / b; // 或者 a / (double) b;
// 但不是 ratio = (double) (a / b) ——这种转换应用得太晚了！
```

如果操作数之一是 `double`，则不需要对另一个进行强制转换——它会自动提升为 `double`。例如：

```java
double x;
int factor = 3;
x = 2.0 / factor; // 正确的结果：x = .6666...
```

下列表达式中哪一个的结果不为 0.4？

- (A) `(int) 4.5 / (double) 10`
- (B) `(double) (4 / 10)`
- (C) `4.0 / 10`
- (D) `4 / 10.0`
- (E) `(double) 4 / (double) 10`

> 在 B 中，转换为 `double` 的转换应用得太晚——在比例被截断为 0 之后——所以结果为 0。答案是 B。

在现实世界中，我们必须担心不同数据类型的 `n` 的范围。例如，一个用 `int` 计算 `n` 阶乘的方法可能会对于较小的 `n` 导致结果溢出。

> 对于 AP 考试，你必须意识到什么是溢出，但不需要担心具体的限制。

### 取模除法

`%`（取模除法）运算符通常应用于两个整数：它计算第一个操作数除以第二个操作数时的余数。

例如：

```java
int r;
r = 17 % 3; // r 被设置为 2
r = 8 % 2;  // r 被设置为 0
r = 4 % 5;  // r 被设置为 4
```

### 复合赋值、++ 和 --

复合赋值运算符有 `+=`、`-=`、`*=`、`/=` 和 `%=`。`x += y` 等同于 `x = x + y`。其他操作遵循相同的模式。

Java 中有两种形式的 `++` 和 `--` 运算符。前缀形式在变量的值用于表达式的其他部分之前增（或减）变量；后缀形式在之后增（或减）它。

> AP 开发委员会不建议在表达式中使用 `++` 和 `--`。请仅在单独的语句中使用 `++` 和 `--`。

例如：

```java
while (i <= n) {
    sum += i++;
    i++;
}

while (i <= n) {
    sum += i;
    i++;
}
```

如果你正确使用，在表达式中使用 `++` 或 `--` 不会让你丢分，但它们也不会获得任何加分。

> 在适当的地方不自增、自减或复合赋值运算符是一种糟糕的风格。

例如：



```
for (int i = 0; i < n; i == i + 1) {
    count = count + 1;
    sum = sum + a[i];
} for (int i = 0; i < n; i++) {
    count++;
    sum += a[i];
}
```

再次，这不会产生惩罚，但看起来很丑。

算术表达式太简单了，无法单独测试。你可能会在与逻辑、迭代、递归等结合的问题中遇到它们。

### 关系运算符

在子集中，关系运算符 `!=`、`<`、`<=` 将应用于`ints`和`doubles`。记住“等于”用`==`表示（不要与赋值运算符`=`混淆）。要清晰地写出来。`a != b`等同于`!(a == b)`，但`!=`在风格上更好。

> `==`和`!=`运算符也可以应用于任何对象，但它们的含义与你可能预想的不同：它们比较的是两个对象的地址。只有当两个变量引用的是完全相同的对象时，`==`的结果才为真。你很少关心这一点：你可能只是想比较两个对象的内容，例如两个字符串。这时，你需要使用`equals`或`compareTo`方法。

例如：

```java
if (str.equals("Stop")) ...
```

另一方面，当你需要将对象与`null`进行比较时，必须使用`==`或`!=`。

`null`是Java的保留字，代表一个值为0的引用。它被用来指示变量当前没有引用任何有效对象。例如：

```java
if (str != null && str.equals("Stop")) ...
// str != null 避免了空指针异常 -- 不能调用 null 的方法
```

## 2.1 变量；算术、关系和逻辑运算符

你也可以写成

```java
if ("Stop".equals(str)) ...
```

这之所以有效，是因为`"Stop"`不是`null`；即使`str`是`null`，它也能工作。

### 逻辑运算符

逻辑运算符`&&`、`||`和`!`通常应用于布尔值和表达式。例如：

```java
boolean found = false;
while (i >= 0 && !found)
{
boolean found = false;
while (i >= 0 && found)
}
```

不要写成

```java
while (... && found)
```

这可以运行，但是冗余的。

假设`x`、`y`和`z`是整数变量，下列逻辑表达式中哪些是等价的，即对于`x`、`y`、`z`的所有取值，它们具有相同的值？

- I. `x == y && x != z || (x == z)`

- II. `x == y || x == z && (x != z)`

- III. `x == y != (x == z)`

(A) I 和 II

(B) II 和 III

(C) I 和 III

(D) I， II， 和 III

(E) 三者均不是

III 是答案的关键：所有三个表达式都说明了两个等式`x == y`或`x == z`中恰好有一个为真。I 表示要么第一个真而第二个不是，要么第二个真而第一个不是。II 表示两个中一个是真的，一个是假的。III 仅仅说明它们有值。所有三者归结为相同的结果。答案是D。

### 德摩根定律

考试可能包含关于德摩根定律的问题：

- `!(a && b)`等同于`!a || !b`

- `!(a || b)`等同于`!a && !b`

表达式`!((x <= y) && (y > 5))`等同于以下哪一个？

- (A) `(x <= y) && (y > 5)`

- (B) `(x <= y) || !(y > 5)`

- (C) `!(x <= y) || (y > 5)`

- (D) `!(x <= y) && (y <= 5)`

- (E) `(x > y) && (y <= 5)`

使用德摩根定律可以：

```
!(x > y) || (y <= 5)
```

答案是D。

### 短路逻辑

关于逻辑运算符`&&`和`||`，一个重要的点是短路求值。如果第一个操作数的值足以确定结果，那么第二个操作数就不会被计算。考虑以下代码：

```java
int x = 0, y = 3;
String op = "/";

if (op.equals("/") && x != 0) {
    System.out.println("OK");
} else {
    System.out.println("Failed");
}
```

关于这段代码，下列哪种陈述正确？

- (A) `String`和`int`变量混合会导致编译错误。

- (B) 会产生运行时除零错误。

- (C) 代码将编译通过并执行；输出为`OK`。

- (D) 代码将编译通过并执行；输出为`Failed`。

- (E) 代码将编译通过并执行；没有输出。

> A 和 E 只是填充答案。由于`x`等于0，条件不成立，所以不会崩溃或执行。在Java中，一旦`x != 0`失败，后续的`y/x > 2`就不会被计算。

## 2.2 条件语句和循环

你可以使用简化的缩进处理`if-else-if`语句。

例如：

```
if (score >= 70)
grade = 5;
else if (score >= 60)
grade = 4;
...
else
grade = 1;
```

但对于嵌套的`if`，不要忘记大括号和正确的缩进。例如：

```java
if (exam.equals("A"))
{
    if (score >= 60)
    grade = 5;
    else if...
    ...
}
else if (exam.equals("B"))
{
    if (score >= 70)
    grade = 5;
    else if...
    ...
}
```

## 2.2 条件语句与循环

考虑以下代码段，其中`m`是一个`int`类型的变量：

```java
if (m > 0)
{
    if ((1000 / m) % 2 == 0)
        System.out.println("even");
    else
        System.out.println("odd");
}
else
    System.out.println("not positive");
```

以下哪些代码段与上方代码等价（即无论`m`的值如何，产生的输出都与上方相同）？

- I. `if (m <= 0)`

    `System.out.println("not positive");`

    `else if ((1000 / m) % 2 == 0)`

        `System.out.println("even");`

    `else`

        `System.out.println("odd");`

- II. `if (m > 0 && (1000 / m) % 2 == 0)`

    `System.out.println("even");`

    `else if (m <= 0)`

        `System.out.println("not positive");`

    `else`

        `System.out.println("odd");`

- III. `if ((1000 / m) % 2 == 0)`

{

    `if (m < 0)`

        `System.out.println("not positive");`

    `else`

        `System.out.println("even");`

}

`else`

{

    `if (m <= 0)`

        `System.out.println("not positive");`

    `else`

        `System.out.println("odd");`

}

- (A) 仅 I

(B) 仅 II

(C) I 和 II

(D) II 和 III

(E) I、II 和 III

代码段 I 实际上可以重新格式化：

```java
if (m <= 0) {
    System.out.println("not positive");
} else {
    if ((1000 / m) % 2 == 0) {
        System.out.println("even");
    } else {
        System.out.println("odd");
    }
}
```

所以它与给定的代码段相同，只是条件取反了并交换了`if`和`else`的位置。代码段 II 重构了顺序，但结果相同。为了验证这一点，我们尝试了`m <= 0`和`(1000 / m) % 2 == 0`的不同真/假组合。代码段 III 同样可行，但它有一个陷阱：当`m`等于0时，它不起作用。答案是C。

## for 和 while 循环

`for`循环，

```java
for (initialize; condition; change) {
    // 执行某些操作
}
```

等于`while`循环：

```java
initialize;
while (condition) {
    // 执行某些操作
    change;
}
```

`change`可以意味着控制循环的变量值的任何变化，例如索引或计数器的增加或递减。

在某些情况下，`for`循环更短且更符合习惯。它们不应该被歧视。例如：

| `i = 0; while (i < a.length) { sum += a[i]; i++; }` | `for (i = 0; i < a.length; i++) { sum += a[i]; }` |

| :--- | :--- |

在`for`循环或`while`循环中，条件在循环开始时求值，如果条件为假，程序就不会进入循环。因此，如果条件在最开始为假，循环体可能会被完全跳过。

考虑以下方法：

```java
public int fun1(int n) {
    int product = 1;
    int k;
    for (k = 2; k <= n; k++) {
        product *= k;
    }
    return product;
}
public int fun2(int n) {
    int product = 1;
    int k = 2;
    while (k <= n) {
        product *= k++;
    }
    return product;
}
```

对于哪些整数值`n`，`fun1(n)`和`fun2(n)`返回相同的结果？

- (A) 仅`n > 1`

(B) 仅`n < 1`

(C) 仅`n == 1`

(D) 仅`n >= 1`

(E) 任意`n`

这里的最佳方法是纯形式的：由于`fun1`中`for`循环的初始化、条件和递增与`fun2`中使用的`while`循环相同，这两个方法是等价的。答案是E。

## JAVA 特性

考虑以下代码段：

```java
while (x > y)
{
    x--;
    y++;
    System.out.print(x - y);
}
```

假设`x`和`y`是`int`变量，其值满足`0 ≤ x ≤ 2`和`0 ≤ y ≤ 2`。以下哪个描述了所有输出的集合？

- (A) `0`

(B) `-1`, `1`

(C) `-1`, `-2`

(D) `0`, `-1`, `-2`

(E) `0`, `-1`, `-1`, `-2`

如果`x ≤ y`，则永远进入`while`循环，可能的输出有`(0,0)`，`(0,1)`，`(0,2)`，`(1,1)`，`(1,2)`。如果`x > y`，则进入循环，在循环结束后我们有`x ≤ y`，所以`x - y`不可能是正数。答案是D。

## OOB（越界错误）

在编写循环时，要小心“差一错误”（off-by-one errors，即OOB）。

假设`isPrime`定义如下：

```java
public static boolean isPrime(int p) {
    if (p < 2) return false;
    for (int i = 2; i * i <= p; i++) {
        if (p % i == 0) return false;
    }
    return true;
}
```

以下哪些代码段正确计算了从2到`n`的数字和？

```java
int n = 101;
int sum = 0;
```

- (A)

```java
while (n > 1) {
    if (isPrime(n)) {
        sum += n;
    }
    n--;
}
```

- (B)

```java
while (n >= 2) {
    if (isPrime(n)) {
        sum += n;
    }
    n--;
}
```

- (C)

```java
for (int i = 2; i < n; i++) {
    if (isPrime(i)) {
        sum += i;
    }
}
```

- (D)

```java
for (int i = 2; i <= n; i++) {
    if (isPrime(i)) {
        sum += i;
    }
}
```

- (E)

```java
for (int i = n; i >= 2; i--) {
    if (isPrime(i)) {
        sum += i;
    }
}
```

# 第 2 章 ~ Java 特性，第一部分

如果你坚持使用布尔标志位，你需要格外小心：

```
// 如果列表中的所有值都不同，返回 true，否则返回 false
public boolean allDifferent(int[] list)
{
    int i, j;
    boolean foundDuplicates = false;

    for (i = 0; i < list.length; i++) {
        for (j = i + 1; j < list.length; j++) {
            if (list[i] == list[j]) {
                foundDuplicates = true;
                break;
            }
        }
    }
    return !foundDuplicates;
}
```

`continue`语句不在AP子集中，应该避免使用。

## 2.3 字符串 (Strings)

在Java中，字符串是`String`类型的对象，和其他类型的对象一样，`String`变量持有的是对字符串的引用（地址）。字符串是不可变的；任何字符串方法都不能改变字符串。赋值语句

```
str1 = str2;
```

将`str2`的引用复制到`str1`中，因此它们都指向同一个内存位置。

字面量是双引号内的字符字符串。字面量可以包含“转义序列”`\n`（换行）、`\"`（双引号）和`\\`（反斜杠）。例如，

```
System.out.print("Hello\n");
```

产生的效果等同于

```
System.out.println("Hello");
```

`String`类支持使用`+`和`+=`运算符来拼接字符串。

> `String`是Java中唯一支持对其对象使用运算符的特殊语法的类。

## 2.3 ~ 字符串

运算符

```
s1 += s2;
```

将`s2`追加到`s1`之后。实际上，它通过拼接`s1`和`s2`创建了一个新字符串，并让`s1`指向它。它等同于

```
s1 = s1 + s2;
```

以下代码段的输出是什么？

```
String str1 = "Happy ";
String str2 = str1;
str2 += "New Year !";
str2.substring(6);
System.out.println(str2);
```

- (A) `Happy New Year!`

- (B) `Happy New Year!`

- (C) `Happy New Year New Year!`

- (D) `Happy New Year! Happy New Year!`

- (E) `Happy New Year! Happy Happy`

> 在`str2 = str1`之后，`str2`指向包含`"Happy "`的相同内存位置。但在`str2 += "New Year!"`之后，这些变量指向了不同的内容；`str1`保持为`"Happy "`（字符串是不可变的），而`str2`变成了`"Happy New Year !"`。`str2.substring(6)`没有改变`str2` —— 它调用了方法但没有使用返回值（这是一个常见的学者错误：再次，字符串是不可变的）。答案是B。

### String 方法

子集中包含的`String`方法有：

```
int length()
boolean equals(String other)
int compareTo(String other)
String substring(int from)
String substring(int from, int to)
int indexOf(String s)
```

始终使用方法来比较一个字符串和另一个字符串。应用于两个字符串的`==`和`!=`运算符比较的是它们的地址，而不是值。

`str1.equals(str2)`仅当`str1`和`str2`具有相同的值（即由相同的字符）时返回`true`。



`str1.compareTo(str2)` 如果 `str1` 大于 `str2`（字典序），则返回正数；如果它们相等则返回零；如果 `str1` 小于 `str2` 则返回负数。

`str.substring(from)` 返回从 `from` 位置开始到末的字符串，而 `str.substring(from, to)` 返回从 `from` 位置开始到但不包含 `to` 位置的字符串（返回的子字符串长度为 `to - from`）。

`str.indexOf(s)` 返回 `s` 在 `str` 中首次出现的索引，如果没有则返回 -1。

考虑以下方法：

```java
public String process(String msg, String delim)
{
    int pos = msg.indexOf(delim);
    while (pos >= 0)
    {
        msg = msg.substring(0, pos) + ""
             + msg.substring(pos + delim.length());
        pos = msg.indexOf(delim);
    }
    return msg;
}
```

以下代码段的输出是什么？

```java
String rhyme = "Twinkle\ntinkle star";
String rhyme2 = process(rhyme, "\n");
System.out.println(rhyme + "\n" + rhyme2);
```

- (A) little star

Twinkle twinkle little star

- (B) little star

Twinkle

twinkle

little star

- (C) little star

Twinkle winkle itle tar

- (D) Twinkle

twinkle

little star

Twinkle twinkle

little star

- (E) Twinkle

twinkle

little star

```java
在 `process` 接收并处理字符串的副本。该方法产生了
```

Twinkle

twinkle

little star

```

## 2.5. 数组 (Arrays)

声明和创建一维数组有两种方法：

```java
someType a = new someType[ size ];
someType[] b = { value0, value1, ..., value_n-1};
```

例如：

```java
double[] samples = new double[100];
int[] numbers = {1, 2, 3};
String[] cities = {"Atlanta", "Boston", "Cincinnati", "Dallas"};
```

第一种声明了一个大小为 100 的双精度浮数组。其元素会被赋值（零），但这一事实不在 AP 子集中。第二种声明创建了一个大小为 3 的整数数组，并元素初始化为 1、2 和 3。第三种声明并初始化了一个包含四个给定字符串的数组。

## 34 第 2 章 ~ JAVA 特性，第 1 部分

我们可以通过 `a[i]` 引用 `a` 的元素，其中 `a` 是数组名，`i` 是索引（下标），它可以是一个整数常量、变量或表达式。

索引从 0 开始。

`a.length` 指的是数组的大小。（在数组中，`length` 不是一个方法，而是作为一个实例变量起作用，因此没有圆括号）`a[a.length - 1]` 指的是数组的最后一个元素。

一旦创建了数组，其大小就无法改变。扩展数组的唯一方法是创建一个更大的数组，并将原数组的内容复制到新数组中。旧数组会被丢弃（或者更准确地说，由一个名为“垃圾收集”的过程进行回收）。例如：

```java
int[] a = new int[100];
...
int[] temp = new int[a.length * 2];
for (int i = 0; i < a.length; i++) {
    temp[i] = a[i];
}
a = temp; // 重新赋值给新数组；旧数组被丢弃
```

如果 `a` 和 `b` 是数组，`a = b` 并不会将 `b` 中的元素复制到 `a` 中：它重新赋值了 `b` 的引用，使得 `a` 和 `b` 都指向同一个数组。

以下方法反转字符串数组元素的顺序：

```java
public void reverse(String[] words) {
    int i = 0, j = words.length - 1;
    String temp;
    while (i < j) {
        temp = words[i]; words[i] = words[j]; words[j] = temp;
        i++;
        j--;
    }
}
```

Java 虚拟机（运行时解释器）检查数组索引是否在 0 到 `array.length - 1` 的范围内。如果索引值无效，解释器会"抛出" `ArrayOutOfBoundsException` —— 报告运行时错误、出错程序语句的行号以及导致该错误的方法的堆栈轨迹。

异常是运行时错误，而不是编译时错误。

编译器无法捕获程序执行期间某些情况引起的错误，例如用作数组索引的变量其值超出了适当范围。

## 考虑以下方法：

```java
// 如果 counts[0], ... counts[n-1] 中没有两个元素的数值相同
// 或者是连续整数，则返回 true；否则返回 false
// 前提条件：counts 包含 n 个值，n > 1
public boolean isSparse(int[] counts, int n)
{
    int j, k, diff;
}
```

以下哪些代码段可以替换 `{}` 以使得 `isSparse` 方法按预期工作？

- I. `for (j = 0; j < n; j++)`
    `for (k = j + 1; k < n; k++)`
        `diff = counts[j] - counts[k];`
        `if (diff >= -1 && diff <= 1)`
            `return false;`

- II. `for (j = 1; j < n; j++)`
    `for (k = 0; k < j; k++)`
        `diff = counts[j] - counts[k];`
        `if (diff >= -1 && diff <= 1)`
            `return false;`

- III. `for (j = 0; j < n; j++)`
    `for (k = 1; k < n; k++)`
        `diff = counts[j] - counts[k];`
        `if (Math.abs(diff) <= 1)`
            `return false;`

- (A) 仅 I
- (B) 仅 II
- (C) 仅 I 和 II
- (D) 仅 I 和 III
- (E) I、II 和 III

注意，在此题中，`counts` 的所有 `counts.length` 个元素并没有被使用，只是前 `n` 个。它们的下标范围从 0 到 `n-1`。前提条件指出 `n>1`，因此不需要担心空数组或仅有一个元素的数组。观察每个代码段中的内部循环，可以快速看出它们是正常工作的。区别在于循环的设置方式；更具体地说，索引的限制不同。在段 I 中，外层循环从列表中的第一个项目开始；内部循环将其与后续每个项目进行比较。在段 II 中，外层循环从列表中的第二个项目开始；内部循环与之前的每个项目进行比较。这两者都是正确的，并且在类似的算法中非常标准。这消除了 A、B 和 D。段 III 起初看起来无害，但有一个陷阱：内部循环没有为 `k` 设置依赖于 `j` 的限制，因此当 `j` 大于 0 时，`k` 可能会取与 `j` 相同的值（例如 `j=1, k=1`）。当方法实际上是在比较项目与其自身时，错误地检测到了 `counts` 中的值。

假设方法 `int sign(int x)` 在 `x` 为正时返回 1，`x` 为负时返回 -1，`x` 为 0 时返回 0。

```java
int[] nums = {-2, -1, 0, 1, 2};
```

在执行以下代码后，`nums` 元素的值是多少？

```java
int k;
for (k = 0; k < nums.length; k++) {
    nums[k] = sign(nums[k]);
    nums[k] += sign(nums[k]);
}
```

- (A) -2
- (B) -2, -1, 0, 1, 2
- (C) -2, -2, 0, 1, 2
- (D) -2, -2, 0, 2, 2
- (E) -2, -2, 0, 2, 4

*计算过程：*

*k=0: `nums[0]` = `sign(-2)`=-1; -1+`sign(-1)`=-2*

*k=1: `nums[1]` = `sign(-1)`=-1; -1+`sign(-1)`=-2*

*k=2: `nums[2]` = `sign(0)`=0; 0+`sign(0)`=0*

*k=3: `nums[3]` = `sign(1)`=1; 1+`sign(1)`=2*

*k=4: `nums[4]` = `sign(2)`=1; 1+`sign(2)`=2*

结果应为 -2, -2, 0, 2, 2。因此正确答案是 (D)。



## 34 第 2 章 ~ JAVA 特性，第 1 部分

我们可以通过`a[i]`引用`a`的元素，其中`a`是数组名，`i`是索引（下标），它可以是一个整数常量、变量或表达式。

索引从 0 开始。

`a.length`指的是数组的大小。（在数组中，`length`不是一个方法，而是作为一个实例变量起作用，因此没有圆括号）`a[a.length - 1]`指的是数组的最后一个元素。

一旦创建了数组，其大小就无法改变。扩展数组的唯一方法是创建一个更大的数组，并将原数组的内容复制到新数组中。旧数组会被丢弃（或者更准确地说，由一个名为“垃圾收集”的过程进行回收）。例如：

```
int[] a = new int[100];
...
int[] temp = new int[a.length * 2];
for (int i = 0; i < a.length; i++) {
    temp[i] = a[i];
}
a = temp; // 重新赋值给新数组；旧数组被丢弃
```

如果`a`和`b`是数组，`a = b`并不会将`b`中的元素复制到`a`中：它重新赋值了`b`的引用，使得`a`和`b`都指向同一个数组。

以下方法反转字符串数组元素的顺序：

```java
public void reverse(String[] words) {
    int i = 0, j = words.length - 1;
    String temp;
    while (i < j) {
        temp = words[i]; words[i] = words[j]; words[j] = temp;
        i++;
        j--;
    }
}
```

Java 虚拟机（运行时解释器）检查数组索引是否在 0 到`array.length - 1`的范围内。如果索引值无效，解释器会“抛出”`ArrayOutOfBoundsException` —— 报告运行时错误、出错程序语句的行号以及导致该错误的方法的堆栈轨迹。

异常是运行时错误，而不是编译时错误。

编译器无法捕获程序执行期间某些情况引起的错误，例如用作数组索引的变量其值超出了适当范围。

## 考虑以下方法：

```java
// 如果 counts[0], ... counts[n-1] 中没有两个元素的数值相同
// 或者是连续整数；则返回 true；否则返回 false
// 前提条件：counts 包含 n 个值，n > 1
public boolean isSparse(int[] counts, int n)
{
    int j, k, diff;
}
```

以下哪些代码段可以替换`{}`以使得`isSparse`方法按预期工作？

- I. `for (j = 0; j < n; j++)`
    `for (k = j + 1; k < n; k++)`
        `diff = counts[j] - counts[k];`
        `if (diff >= -1 && diff <= 1)`
            `return false;`

- II. `for (j = 1; j < n; j++)`
    `for (k = 0; k < j; k++)`
        `diff = counts[j] - counts[k];`
        `if (diff >= -1 && diff <= 1)`
            `return false;`

- III. `for (j = 0; j < n; j++)`
    `for (k = 1; k < n; k++)`
        `diff = counts[j] - counts[k];`
        `if (Math.abs(diff) <= 1)`
            `return false;`

- (A) 仅 I
- (B) 仅 II
- (C) 仅 I 和 II
- (D) 仅 I 和 III
- (E) I、II 和 III

注意，在此题中，`counts`的所有`counts.length`个元素并没有被使用，只是前`n`个。它们的下标范围从 0 到`n-1`。前提条件指出`n>1`，因此不需要担心空数组或仅有一个元素的数组。观察每个代码段中的内部循环，可以快速看出它们是正常工作的。区别在于循环的设置方式；更具体地说，索引的限制不同。在段 I 中，外层循环从列表中的第一个项目开始；内部循环将其与后续每个项目进行比较。在段 II 中，外层循环从列表中的第二个项目开始；内部循环与之前的每个项目进行比较。这两者都是正确的，并且在相似的算法中非常标准。这消除了 A、B 和 D。段 III 起初看起来无害，但它有一个陷阱：内部循环没有为`k`设置依赖于`j`的限制，因此当`j`大于 0 时，`k`可能会取与`j`相同的值（例如`j=1, k=1`）。方法在实际上是在比较项目与其自身时，错误地检测到了`counts`中的值。

假设方法`int sign(int x)`在`x`为正时返回 1，`x`为负时返回 -1，`x`为 0 时返回 0。

```java
int[] nums = {-2, -1, 0, 1, 2};
```

在执行以下代码后，`nums`元素的值是多少？

```java
int k;
for (k = 0; k < nums.length; k++) {
    nums[k] = sign(nums[k]);
    nums[k] += sign(nums[k]);
}
```

- (A) -2
- (B) -2, -1, 0, 1, 2
- (C) -2, -2, 0, 1, 2
- (D) -2, -2, 0, 2, 2
- (E) -2, -2, 0, 2, 4

## 40 第 2 章 ~ JAVA 特性，第一

`ArrayList`提供了获取和设置特定元素值、在列表末尾添加值、删除值以及在指定位置插入值的方法。与标准数组一样，索引从 0 开始。

当`ArrayList`空间用尽时，会自动调整大小。`ArrayList`的“无参数”构造函数（即不接受参数的构造函数）分配一个默认初始容量大小为 0 的数组（不存储任何值）。随着值的添加，其数量可能会超过当前容量。此时容量会翻倍，分配新数组，将旧值复制到新数组中，并丢弃旧数组。这一切都在后台完成——你不需要担心任何这些事情。

AP 子集包含了`ArrayList<E>`的以下方法：

| 方法 | 说明 |
| :--- | :--- |
| `size()` | 返回列表中当前存储的值的数量 |
| `boolean add(E x)` | 在列表末尾添加`x`；返回布尔值 |
| `E get(int index)` | 返回存储在索引处的值 |
| `E set(int index, E x)` | 将索引处的元素值设置为`x`；返回旧值 |
| `E remove(int index)` | 删除索引处的值并将后续值向列表开头移动；返回存储在索引处的值 |
| `void add(int index, E x)` | 在索引处插入`x`，将索引处存储的值以及所有后续值向列表末尾移动 |

`add`和`remove`方法会适当调整`ArrayList`的大小。带有索引参数的方法会检查索引是否在有效范围（0 到`size() - 1`之间）内，如果索引不在该范围内，则“抛出”`IndexOutOfBoundsException`。

由于编译器知道`ArrayList`中存储的是什么类型的对象，它会自动将从列表中获取的值强制转换为相应的类型。例如：

```
ArrayList<Fish> list = new ArrayList<Fish>();
Fish f = list.get(i);
```

## 下面代码段的输出是什么？

```
ArrayList<String> list = new ArrayList<String>();
list.add("A");
list.add("B");
list.add("C");
list.add("D");
list.add("E");
for (int k = 1; k <= 3; k++) {
    list.remove(1);
}
for (int k = 1; k <= 3; k++) {
    list.add(1, "*");
}
for (String word : list) {
    System.out.print(word + " *");
}
```

- (A) A C D E * * *
- (B) A * * * E
- (C) A * * B D E
- (D) A E * * *
- (E) IndexOutOfBoundsException

这个问题并没有看起来那么复杂。首先，我们创建一个空列表并向其中添加五个值："A", "B", "C", "D", "E"。然后我们三次删除索引为 1 的值。这是第二个元素，每次删除它时，后续的值都会向左移动一个位置。"A" 和 "E" 留了下来。然后我们插入三个星号。注意，我们始终在索引 1 处插入。第一次插入后，我们得到 "A", "*", "B", "E"。第二次插入后我们得到 "A", "*", "*", "E"。第三次插入产生 "A", "*", "*", "*", "E"。第三个循环（"for" 循环）遍历整个列表并打印这些值。答案是 C。

# 第 3 章 Java 特性，第二部分

### 3.1. 类

Java 程序由类组成。“类”一术语指的是对象的类别。

你应该了解以下概念和术语：

- 类私有和公开（`public`）字段和方法
- 对象的封装和信息隐藏
- 类的实例 类的客户端
- 构造函数 访问器
- `new`操作符 修饰符 静态方法
- 垃圾回收 `public static final`字段（常量）
- 实例变量或字段

属于特定类的对象称为该类的实例，创建对象的过程被称为实例化。

类的定义包括了构造函数、方法和数据字段。构造函数描述了如何创建该类的对象；方法描述了该类的对象可以做什么；数据字段（也称为实例变量或简单的字段）描述了对象的属性——对象的当前状态。

## 构造函数

构造函数描述了创建类对象的方式以及初始化对象的实例变量的方法。

> 所有的构造函数的名称都与类相同。构造函数没有返回数据类型，甚至`void`也没有。

构造函数可以接受参数来帮助定义新对象。不接受参数的构造函数被称为“无参数”构造函数。

> “参数”（parameter）一术语通常与“参数”（argument，如数学中的函数参数）互换使用，特别是当它指的是传递给构造函数或方法的实际值时。

因此有了如“无参数”构造函数、`IllegalArgumentException`或`main(String[]) args`等用法。课程描述似乎倾向于使用“parameter”，但偶尔也会使用“argument”，我们也是如此。

使用`new`操作符创建新对象。例如，假设你定义了一个`School`类：

```
public class School
{
  // constructor
  public School() { }
}
```

那么你可以创建一个`School`对象：

```
School s = new School();
```

如果一个类有一个实例变量`name`和`num`：

```java
public class School
{
  private String name;
  private int num;
  public School(String name, int num) {
    name = name;
    num = num;
  }
}
```

## 44 第 3 章 ~ JAVA 特性，第二部分

### 3.1 ~ 类

在 AP 子集中，构造函数总是公开（`public`）的。在面向对象编程（OOP）中，常见的做法（AP 考试的要求）是将所有实例变量设为私有（`private`）。私有字段和方法向客户端隐藏类的实现细节。这个概念被称为封装。通常情况下，向客户端类提供尽可能少的信息是一个主意。例如，如果一个方法只在该类内部使用，则应该被设为私有。

## 访问器和修饰符

由于所有实例变量都是私有的，在客户端类无法直接访问。通常提供特殊的公开方法，称为访问器（accessors），返回实例变量的值。例如：

```
public class School
{
    public String getName()
    {
        return name;
    }
}
```

访问器的名称通常以 "get" 开头。访问器可以使用任何名称，但以 "get" 开头更容易记忆。访问器不会改变状态。

设置实例变量新值的公开方法称为修饰符（modifier）。修饰符的名称通常以 "set" 开头。例如：

```
public class School
{
    public void setName(String nm)
    {
        name = nm;
    }
}
```

“访问器”和“修饰符”的定义是非正式的——一个类可以有一个方法在设置实例变量的新值的同时，同时返回（例如）旧值。

考虑以下类：

```
public class Clock {
    private int hours;
    private int mins;
    public Clock(int h, int m) {
        hours = h;
        mins = m;
    }
    // 将此钟向前移动一分钟
    public void move() {
        < missing code >
    }
    public void set(int h, int m) {
        hours = h;
        mins = m;
        normalize();
    }
    private void normalize() {
        while (mins >= 60) {
            mins -= 60;
            hours++;
        }
        hours = hours % 12;
    }
}
```



## 3.2 方法

以下哪些可以替换 `move` 方法中的 `<missing code>`？

- I. `this = new Clock(hours, mins + 1);`
- II. `mins++;`  
  `normalize();`
- III. `set(hours, mins + 1);`

- (A) 仅 I
- (B) 仅 II
- (C) 仅 I 和 II
- (D) 仅 II 和 III
- (E) I、II 和 III

选项 I 是错误的：它尝试用一个新对象替换它，而不是修改当前对象，这会导致语法错误。另外两个选项是可以接受的：在同一个类内部访问私有实例变量和调用公共方法是可以的。答案是 D。

注意，在 `Clock` 的构造函数中添加对 `normalize` 的调用会更好，以确保即使 `mins >= 60`，时钟也能被正确设置。或者，如果参数不合理，构造函数可以抛出 `IllegalArgumentException`。

## 静态（类）变量和方法

有时，一个属性属于整个类，而不是该类的单个对象（实例）。此类属性由类变量（class variables）表示，并由关键字 `static` 标识。在 AP 子集中，静态变量始终是 `public final` 变量（常量）。例如：

```java
public class School {

  public static final int highestGrade = 12;

}
```

类还可能拥有静态方法——即不涉及类的任何特定实例或不访问实例变量的方法。例如，Java 库类 `Math` 具有静态方法 `abs`、`sqrt`、`random`。为了方便起见，它还包含了 `public static final` 变量 `Math.PI`（代表 π，圆周长与直径的比率）和 `Math.E`（代表 e，自然对数的底）。静态方法的调用和静态常量的访问使用点符号法，并以类名作为前缀。例如：

```java
double volume = 4.0 / 3.0 * Math.PI * Math.pow(r, 3);
```

## 3.2 方法

在 Java 中，所有方法都属于类。Java 的通用风格是所有方法名都以小写字母开头。

实例方法针对特定的对象进行调用；调用时使用对象名和点 `.` 作为前缀，例如 `obj.someMethod(...)`。如果从同一个对象的另一个方法调用该方法，则不需要前缀，直接写 `some(...)` 即可。类（静态）方法属于整个类，使用类名加点作为前缀进行调用。例如：`Math.sqrt(...)`。

## 第 3 章 ~ JAVA 特性，第 2 部分

方法接收特定数量、特定数据类型的参数。从 Java 5.0 开始，方法可以定义为变数量参数，如 `System.out.printf()`；然而，此功能不在 AP 子集中。某些方法不接受任何参数。方法可以包含一个完整的表达式作为参数；该表达式会先求值，然后结果传递给方法。表达式可以包含对其他方法的调用。例如：

```java
double x, y;

x = Math.sqrt(Math.abs(2*y - 1));
```

方法通常返回一个指定数据类型的值，但 `void` 方法不返回任何值。返回类型在方法签名中指定。返回值在 `return` 语句中指定。

> 在方法内部从 `System` 读取方法参数的新值被认为是一个“严重错误”（-1 分）。  
> 在方法内部将返回值打印到 `System`（当未被要求时）是一个轻微错误（-1/2 分），且如果非 `void` 方法缺少了必需的 `return` 语句，则是一个额外错误。

例如：

```java
// 返回从 1 到 n 的所有整数之和

// 前条件: n >= 1

public int addNumbers(int n)

{

  int k;

  int sum = 0;

  n = System.in.read();

  for (k = 1; k <= n; k++) {

    sum += k;

  }

  System.out.println(sum);

  return sum;

}
```

回 `Math` 的静态方法 `min` 返回两个整数中较小的值。如果 `a`、`b`、`c` 是整数变量，以下哪种描述最符合具有以下语句的行为？

```java
m = Math.min(Math.min(a, c), Math.min(b));
```

- (A) 语句有语法错误，无法编译。
- (B) 程序将进入死循环。
- (C) `a` 将获得 `b` 的值；`b` 将获得 `c` 的值；`m` 将获得 `a`、`b` 的值。
- (D) `m` 被赋值为 `a`、`b`、`c` 的值。
- (E) 以上都不是

任何适当类型的方法调用都可以用于更大的表达式，或作为方法的参数。上述代码基本上等同于：

```java
int temp1 = Math.min(a, c);

int temp2 = Math.min(b, c);

m = Math.min(temp1, temp2);
```

所以 `m` 得到了三。答案是 D。

## 基本类型参数

> 在 Java 中，基本类型按值传递。当参数按值传递时，方法操作的是该变量的副本，因此无法改变原始值。

考虑以下方法：

```java
public void fun(int a, int b) {

    a += b;

    b += a;

}
```

以下代码的输出是什么？

```java
int x = 3, y = 5;

fun(x, y);

System.out.println(x + " " + y);
```

- (A) 3 5
- (B) 3 8
- (C) 3 13
- (D) 8 8
- (E) 8 13

`x` 和 `y` 是 `int`，所以它们按值传递给 `fun`。`fun` 内部发生了什么并不重要，因为在方法调用后 `x` 和 `y` 没有改变。答案是 A。

## 传递的对象

> 所有对象都按引用传递给方法。当变量按值获得对象时，它实际上持有对象的引用。同样，当对象传递给方法时，方法接收的是对象的地址，并可能会改变原始对象。通常对象的所有实例变量都是私有的，因此要更改对象，方法必须调用对象的方法。

但注意 `String`、`Integer` 和 `Double` 类表示不可变对象。尽管这些对象按引用传递给方法，代码也无法改变它们。例如，在 Java 中没有方法可以写：

```java
// 将 s 转换为大写

public void toUpperCase(String s)

{

    ...

}
```

因为方法没有办法传递它的字符串。对于不可变对象，方法创建并返回具有所需属性的新对象：

```java
// 返回转换为大写的 s

public String toUpperCase(String s)

{

    ...

}
```

## 别名（Aliasing）

一个更复杂的概念是别名。通常理解它是好的，但不太出现在考试中。以下解释是给好奇读者的。

假设我们有一个 `Point` 类表示平面上的一个点。考虑以下方法：

```java
// point2 接收 point1 绕原点逆时针旋转90 度的坐标

public void rotate90(Point point1, Point point2)

{

    point2.setY(point1.getX());

    point2.setX(-point1.getY());

}
```

在这个示例中，`rotate90` 接收两个 `Point` 对象作为参数。像所有对象一样，它们按引用传递给方法。注意这里的 `Point` 对象不是不可变的，因为它有 `setX` 和 `setY` 方法。代码看起来是将 `point2` 的坐标设置为从 `point1` 坐标获得的新值。然而，假设你调用 `rotate90(point, point)` 来相应地改变 `point` 的坐标。编译器不会阻止你这样做，但结果将不如你预期。

在方法内部，`point1` 和 `point2` 实际上指向 `point`。第一条语句将 `point` 的 `y` 设置为 `x`，`y` 的原始值将丢失。如果 `point` 的坐标是 `x = 3, y = 5`，你得到的不是预期的 `x = -5, y = 3`，而是 `x = -3, y = 3`。这种类型的错误被称为别名错误。

在 Java 中，别名只有当参数是对象且它们是可变的（或当参数是数组且方法从一个数组移动到另一个数组时）才会发生。在这个示例中，让 `rotate90` 返回新值更安全，如下：

```java
public Point rotate90 (Point point)

{

    return new Point(point.getX(), -point.getY());

}
```

## `return`

非 `void` 方法必须使用 `return` 语句返回指定类型的值。`return` 适用于任何表达式，而不只是变量。例如：

```java
return (-b + Math.sqrt(b*b - 4*a*c)) / (2*a);
```

经常被忽略的事实是，布尔方法可以返回布尔表达式的值。例如，你可以直接写：

```java
return x >= a && x <= b;
```

而不是冗余且冗长的：

```java
if (x >= a && x <= b)

    return true;

else

    return false;
```

方法可以使用 `return`（在 `if` 或 `else` 内部）提前退出，但在方法末尾不需要 `return`。

## 返回对象

方法的返回类型可以是一个类，方法可以返回该类的对象。通常在方法中创建一个新对象并从它返回。例如：

```java
public String getFullName(String firstName, String lastName)

{

    return firstName + " " + lastName;

}
```

返回类型为类的方法也可以返回 `null`（一个值为零的引用，表示它不引用任何有效对象）。例如：

```java
public String getAddress(String name)

{

    for (int i = 0; i < listOfNames.length; i++) {

        if (listOfNames[i].equals(name))

            return listOfAddresses[i];

    }

    return null; // 未找到

}
```

如果一个方法返回 `ArrayList`，请编写完整的 `ArrayList`，包括在尖括号中的元素类型，作为方法的返回类型。例如：

```java
public ArrayList<Integer> getCourseNumbers()

{

    ArrayList<Integer> courseNumbers = new ArrayList<Integer>();

    ...

    return courseNumbers;

}
```

## 方法重载

在同一个类中，具有相同名称但参数数量或类型不同的方法被称为重载方法。不同类型参数的顺序也很重要。

> 编译器将重载方法视为不同的方法。它根据参数的数量和类型来确定调用哪一个。

例如，`String` 类有两个形式的 `substring` 方法：

```java
String substring(int from)

String substring(int from, int to)
```

如果你调用 `"Happy".substring(2)`，将调用第一个重载方法；但如果你调用 `"Happy".substring(1, 3)`，将调用第二个重载方法。另一个重载的例子是 `Math.abs(x)`，它有不同版本的静态方法 `abs`，包括 `abs(int)` 和 `abs(double)`。`System.out.print(x)` 对于所有基本数据类型都有与 `String` 和 `Object` 相同的重载版本。

`ArrayList` 类有两个重载方法：`add(x)`，它将 `x` 添加到列表末尾；以及 `add(index, x)`，它在指定的索引插入 `x`。

重载方法基本上是一种风格技巧。你可以为方法的不同形式赋予不同的名称，但将很难记住它们。重载方法不需要具有相同的返回类型，但它们通常是相同的，因为它们执行的是相似的任务。仅凭返回类型无法区分重载方法。

> 类的所有构造函数都具有相同的名称，因此根据定义，它们是重载的，并且在参数的数量和/或类型上必须不同。

考虑以下类声明：

```java
public class Date {

  public Date()

    { <代码未显示 }

  public Date(String monthName, int day, int year)

    { <代码未显示 }

  public void setState(int month, int day, int year)

    { <代码未显示 }

  { 字段和其他方法未显示 }

}
```

考虑 `Date` 类，使其在声明该类型的变量时能够根据月份（给定月份名称或数字）、日期和年份信息进行初始化，并在以后使用 `setState` 方法设置它们的值。例如，代码应该定义并初始化三个 `Date` 变量：

```java
Date d1 = new Date();

d1.setState("May", 11, 2006);

Date d2 = new Date("June", 30, 2010);

Date d3 = new Date(6, 30, 2010);
```

以下描述描述了应该存在的额外功能？

- (A) 一个具有三个 `int` 参数的 `setState` 重载版本
- (B) 一个具有一个 `String` 和两个 `int` 参数的 `setState` 重载版本
- (C) 一个具有三个 `int` 参数的构造函数
- (D) 一个具有三个 `int` 参数的 `setState` 重载版本和一个具有三个 `int` 参数的构造函数
- (E) 一个具有一个 `String` 和两个 `int` 参数的 `setState` 重载版本，和一个具有三个 `int` 参数的构造函数

## 3.2 方法 55

这是一个冗长但简单的问题。只需将声明与提供的类特征相匹配：

```java
Date d1 = new Date();                     ✔ Date()

Date d2 = new Date("June", 30, 2010);     ✔ Date(String, int, int)

Date d3 = new Date(6, 30, 2010);          Date(int, int, int)

d1.setDate("May", 11, 2004);              void setDate(String, int, int)

                                         ✔ voidDate(String, int, int);
```

正如我们看到的，缺失的是一个具有两个 `int` 参数的构造函数以及一个具有一个 `String` 和两个 `int` 参数的 `setState` 版本。答案是 E。

问题 20-22 涉及以下 `int` 部分定义：

```java
public class TicketSales {

    public TicketSales(String movieName) { < 代码未显示 >

    // 设置给定周的票房收入

    // 前提条件: 1 <= week <= 52

    public void setWeekSales(int week, double dollars) {

        < 代码未显示 >

    }

    // 查找并返回销售最好的周

    private int findBestWeek() { < 代码未显示 }

    < 其他方法未显示>

    private String name;

    private double[] sales;

        // sales[0], ..., sales[51] 存储 52 周的销售总额

}
```



`findBestWeek` 方法被声明为 `private` 是因为

- (A) `findBestWeek` 不打算供类的客户端使用。
- (B) `findBestWeek` 仅供类的客户端使用。
- (C) 处理数组类型私有实例变量的方法不能是 `public` 的。
- (D) 返回值的方法不能是 `public`。
- (E) 返回值的方法不能。

## 56 第 3 章 特性

这是另一个语法问题。`TicketSales` 的变量 `movie` 定义在类外部，在客户端中。这个问题中的关键词是 "sets"。它表示调用了一个方法（修饰符），而从客户端调用方法的方法是使用点操作符法。（此外，A 假设有一个两个参数的构造函数；B 和 D 看起来是调用了不存在的方法；E 忘记提到 `movie`。）答案是 C。

给定声明：

`TicketSales movie = new Random("Monsters, Inc.");`

以下哪个语句设置了周？

- (A) `movie = TicketSales(3);`
- (B) `setWeekSales(movie, 3);`
- (C) `movie.setWeekSales(3);`
- (D) `movie(setWeekSales(3));`
- (E) `setWeekSales(3);`

## 3.3 随机数

随机数模拟了计算机程序中的几率。例如，如果你想模拟掷骰子，你需要获得一个从 1 到 6 之间的数字（这些值中任何一个出现的概率相同）。“随机”并不是真正的随机——它们的序列是使用特定公式生成的——但它们对于许多应用已经足够。Java 提供了一个库类 `java.util`，它有生成“下一个”随机整数或“下一个”随机浮点数的方法。这些方法不是静态的——你需要创建一个 `Random` 对象并调用它的 `nextInt` 和 `nextDouble` 方法。`nextInt()` 返回从 0（包含）到 1（不包含）的浮点数。例如：

```
private static Random generator = new Random();

...

int numPoints = generator.nextInt(6) + 1;

// 将 numPoints 设置为 1 到 6 的随机数

double xCoord = generator.nextDouble(); // 设置 xCoord 和 yCoord

double yCoord = generator.nextDouble(); // 随机数

// 0 < xCoord < 1; 0 < yCoord < 1
```

`nextInt` 和 `nextDouble` 在 `Random` 中不是静态的，而是取决于特定的 `Random` 实例。

如果你使用 `Random` 的无参构造函数创建 `Random` 对象，它会启动一个独特的序列。随机数生成器使用初始值（称为“种子”）作为起点。无参构造函数使用一个很可能产生独特随机数序列的值为生成器设置种子。（`Random` 有另一个接受种子参数的构造函数，但该构造函数不在 AP 子集中。）

# 第 3 章 ~ Java 特性，第 2 部分

下列代码段所有可能的输出列表是哪个？

```
Random g = new Random();

String memo = "MEMO";

System.out.print("" + memo.substring(g.nextInt(3), g.nextInt(3) + 2)

                                     + "");");
```

- [ME], [EM]
- [ME], [EM], [MO]
- [EM], [MO], [O], []
- [I], [M], [ME], [EM], [MO]
- [E], [M], [E], [ME], [EM], [MO], [MEM], [EMO], [MEM]

对 `g.nextInt(3)` 的调用看起来相同，但它们返回不同的值——随机数序列中的两个连续值。`memo.substring` 的 "from" 参数可以是 0、1 或 2，而 "to" 参数可以是 2、3 或 4。这些 `from/to` 值的任何组合都会产生一个有效的子字符串（包括 `substring(2,2)`，它返回一个空字符串）。答案是

![](img/e320d34bf6b289b099c4a1d8b2b5ab9c_71_0.png)

在 Java 程序中获取数字另一种方法是使用 `Math.random` 方法。它返回一个从 0（包含）到 1（不包含）的随机 double。在许多情况下，这比 `Random` 类更容易使用。要获取从 0 到 n-1 的随机整数：

```
int r = (int) (n * Math.random());
```

# 3.4. 输入与输出

AP 子集不包含任何用于数据输入的类或方法。特别是，`Scanner` 类不在 AP 子集中。如果问题涉及用户输入，可能会表述为：

```
double x = < 调用一个读取浮点数的方法 >
```

或者

```
int x = IO.read(); // 读取用户输入
```

输出受限于 `System.out.print` 和 `System.out.println` 调用。

你不需要担心数字的格式。Java 会使用默认格式将传递给 `System.out` 或 `System.out.println` 的 `int` 或 `double` 值转换为字符串。从 Java 5.0 开始，可以使用 `System.out.printf`，这是一个具有可变参数的新方法，可以更精确地输出一个或多个数字和字符串。`printf` 不在 AP 子集中。

# 3.4 ~ 输入与输出 59

你可以将任何对象传递给 `System.out.print`、`System.out.println` 或 `System.out.printf`。这些方法通过调用其对象的 `toString` 方法来处理对象。`Integer` 和 `Double` 类定义了合理的 `toString` 方法。如果你正在设计一个类，提供一个合理的 `toString` 方法是一个好主意。例如：

```
public class Fraction

{

    public String toString() {

        return num + "/" + denom;

    }

}
```

否则，你的类将继承自 `Object` 的通用的 `toString` 方法，该方法返回对象的类名，后面是对象的地址。

> `System.out.print` 和 `System.out.println` 方法接受一个参数。

如果你需要打印多个内容，请使用 `+` 运算符拼接字符串（或使用 `printf` 方法）。你也可以拼接字符串与 `int` 或 `double`：后者将被转换为字符串。例如：

```
System.out.println(3 + " hours " + "15 " + " minutes.");
```

显示的结果将是

3 hours 15 minutes.

你也可以拼接字符串和对象：将调用对象的 `toString` 方法将将其转换为字符串。例如：

```
int n = 3, d = 4;

Fraction f = new Fraction(n, d);

System.out.println(f + " " + (double)n / (double)d);
```

显示的结果将是

3/4 = 0.75

只需注意不要对两个数字或除字符串外的两个对象应用 `+` 运算符：对于前者，数字将相加而不是拼接；对于后者将导致语法错误。

# 3.5. 异常

异常是运行时事件，用于指示程序中的异常状态。某些运行时错误（例如无效的用户输入或尝试读取文件末尾之外）被认为是可以的。`try-catch-finally` 语法允许程序员捕获并处理异常，并让程序恢复。这种类型的异常被称为受检异常（checked exception）。

受检异常和 `try-catch` 语句不在 AP 子集中。

其他错误（例如数组索引越界或尝试调用不存在的对象的方法）被认为是致命的：程序显示带有错误发生位置信息的错误消息，然后退出。这种类型的异常被称为未检异常（unchecked exception）。

在 Java 中，异常是一个对象。Java 库实现了许多类型的异常，如果有必要，你可以从库类中的一个派生你自己的异常类。对于 AP CS 考试，你应该你会遇到 `ArithmeticException`、`IndexOutOfBoundsException`、`NullPointerException`、`IllegalArgumentException` 和 `ClassCastException`。

我们说程序“抛出”（throws）一个异常。当发生算术错误（例如整数除以零）时，会抛出 `ArithmeticException`。（你可能期望 `Math.sqrt(x)` 在 x 为负时抛出 `ArithmeticException`，但它并不会。Java 的异常处理有时是不一致的。）

`IndexOutOfBoundsException` 异常自言易明：当数组索引为负或大于 `array.length - 1` 时抛出。

`NullPointerException` 是当你忘记初始化对象变量或尝试调用其方法时抛出的。例如：

```java
public class MyClass {

    private String name; // name 被设置为 null

    int n = name.length(); // 如果 name 未初始化，该语句将抛出 NullPointerException

}
```

另一个示例：

```
public class Dice

{

    private Random gen; // gen 被设置为 null

    int n = gen.nextInt(6); // 如果在此处没有初始化 gen = new Random(); 

                             //

}
```

第三个示例：

```
Integer[] a = new Integer[10];

int x = a[0].intValue(); // 如果 a[0] 为 null，将抛出 NullPointerException
```

`ClassCastException` 是当你尝试将对象转换为它不所属的类类型时抛出的。例如：

```java
ArrayList<Object> list = new ArrayList<>();

list.add("12356");

Double x = (Double)list.get(0); // 将字符串 "12356" 转换为 Double
```

# 抛出自定义异常

有时你需要“抛出”你自己的异常。例如，你正在实现队列的 `remove` 方法。当队列为空时，你的方法应该做什么？抛出 `NoSuchElementException`。

`throw` 是 Java 关键字。使用它的语法是

```
throw < exception >;
```

例如：

```java
if (items.size() == 0)

    throw new NoSuchElementException();
```

如果对象未准备好调用方法，抛出 `IllegalStateException`。例如：

```java
public void stop ()

{

    if (!isMoving())

        throw new IllegalStateException(); // 显示消息并退出

    speed = 0;

    ...

}
```

# 题

你的代码不需要显式抛出 `ArithmeticException`、`NullPointerException`、`ClassCastException` 或 `ArrayIndexOutOfBoundsException` —— 当触发条件发生时 Java 会自动处理。

考虑以下类：

```java
public class TestSample {

    private ArrayList<Integer> samples;

    public TestSample(int n) {

        for (int k = 0; k < n; k++) {

            samples.add(k);

        }

    }

    public double getBestRatio() {

        double maxRatio = samples.get(1).intValue() / samples.get(0).intValue();

        for (int k = 1; k < samples.size() - 1; k++) {

            double ratio = samples.get(k+1).intValue() / samples.get(k).intValue();

            if (ratio > maxRatio) {

                maxRatio = ratio;

            }

        }

        return maxRatio;

    }

}
```

以下代码段的结果是哪个？

```
TestSample t = new TestSample(1);

System.out.println(t.getBestRatio());
```

- (A) `NullPointerException`
- (B) `ArithmeticException`
- (C) `IndexOfOutOfBoundsException`
- (D) `ClassCastException`
- (E) `Infinity`

## 3.5 ~ 异常

幸运的是我们不需要看 `getBestRatio` 方法。程序员忘记了初始化 `samples` 并在构造函数中调用了它的 `add` 方法。答案是 A。

现在假设我们在构造函数的顶部加上：

```
samples = new ArrayList<Integer>();
```

会发生什么？`getBestRatio` 会调用 `samples.get(1)`，但我们只向 `samples` 添加了一个值。答案将是 C，`IndexOutOfBoundsException`。

现在假设我们将：

```
TestSample t = new TestSample(1);
```

改为：

```
TestSample t = new TestSample(2);
```

那时会发生什么？答案将是 B，`ArithmeticException`，因为我们会发生整数除以 0 的情况。

实际上，程序员可能想写：

```
double maxRatio = (double)samples.get(1).intValue() /

samples.get(0).intValue();
```



如果我们将这个结果加到一个`double`中会发生什么？我们仍然期望浮点除以 0 会产生`ArithmeticException`，但 Java 实际上会打印“Infinity”。答案是 E（但你不需要知道这一点）。

注意，由于自动装箱（autoboxing），数字和对象在需要时会自动正确转换为`Integer`，因此不会发生`ClassCastException`。

# 第 4 章 程序设计与 OOP 概念

## 4.1 计算机系统

你现在可能已经意识到典型的计算机系统硬件至少有一个处理器（即 CPU）、一些 RAM（随机访问存储器）、辅助存储设备（如磁磁盘、CD-ROM 驱动器、软磁盘驱动器等）以及外围设备（调制解调器、打印机、声卡和扬声器、鼠标或其他指针设备等）。

你可能也接触过操作系统，控制计算机系统的软件。Linux、Windows XP 和 OS X 都是操作系统的示例。编译器也是一种软件。它检查用高级编程语言编写的程序的语法并将其翻译成代码。在 Java 中，编译器将源代码（程序文本）翻译成与机器无关的字节码——Java 虚拟机（JVM）的指令。虚拟机充当运行时解释器，在特定的计算机上读取并执行相应的指令。调试器是一个程序，可以帮助你以控制的方式运行和测试程序，并发现其中的错误（“bugs”）。编辑器、编译器、解释器、调试器和其他软件开发工具可以组合在一个名为 IDE（集成开发环境）的软件包中，具有 GUI（图形用户界面）。

系统可靠性、安全性以及与计算机使用相关的法律和伦理问题在 AP 考试指南并没有明确定义。关于这些主题的问题将相当通用。

## 4.2 程序设计与开发方法论

计算机科学试图强调解决问题，而不是仅仅用特定语言进行编程或使用特定的硬件平台。与通用软件设计和开发方法论相关的考试主题强调过程化和功能化分解，以及代码的可重用。这些主题在面向对象的设计和开发背景下讨论。以下是相关术语的简要词表：

- 规范（Specifications）——详细描述软件应该完成什么，以及它应该如何行为以及与用户交互。规范可以是针对整个系统、一个模块甚至是某个类或方法。

- 面向对象编程（OOP）——一种编程方法，基于将程序设计成一个由类层次排列的相互作用对象的世界，并使用封装和多态。

- 自顶向下设计（Top-down design）——一种设计方法，在其中定义程序的整体结构，列出高层类及其相互作用，然后精化每个类的设计，识别子任务和较小的类或方法。然后你精化子任务、单个方法等的设计。

- 自顶向下开发（Top-down development）——与自顶向下设计类似：你首先列出高层类和方法。这些方法可能会调用尚未实现的底层方法。你可以通过用“存根”（stubs——空或极大简化的占位符）替换未编码的低层方法来编译并有时测试代码的高层部分。

- 数据结构（Data structure）——一种组织数据的方法结合访问和操作数据的方法。例如，一个带有检索和更改元素值的方法或运算符的二维数组是一种可能用于表示表格的数据结构。

- 封装和信息隐藏（Encapsulation and information hiding）——将仅在类内部使用的实例变量和辅助方法设为私有（private）的做法。类的客户端可以通过其公共构造函数和方法使用该类。

- 过程化抽象（Procedural abstraction）——对过程的描述，它不依赖于特定的硬件平台、特定的数据类型或其他细节。如 Java 等高级编程语言已经通过将程序员与特定硬件平台隔离来确保某种程度的过程化抽象。算法甚至更加抽象。可以使用伪代码、流程图或独立于任何特定编程语言的工具进行描述。

- 可重用代码（Reusable code）——经过调试和测试的库、类或代码片段，具有某种通用性，并准备在其他项目中重用。使用代码可以缩短软件开发项目。

- 团队开发（Team development）——像 Java 等语言允许你将项目分成不同的部分并分配给不同的开发人员。封装和信息隐藏通过限制开发者之间的交互来促进团队开发。

- 用户界面（User interface）——程序与用户交互的行为：屏幕、菜单、命令、图形等。

## 4.3 继承（INHERITANCE）

是非常通用的概念，很难出测试这些概念深度理解的选题或简答题。在过去的考试中，设计和实现题限于特定的数据结构和算法，有时会使用这些术语。考试可能会包含一个设计类简答题，要求你设计一个小类，然后使用它的某些特性（见 4.7 节）。

### 4.3 继承

继承允许程序员声明一个类扩展另一个类，继承其特性。在 Java 术语中，子类扩展（extends）父类。`extends` 是 Java 的保留字。例如：

![](e320d34bf6b28b09c4a1db2b5ab9c.png)

继承实现了对象之间的 IS-A 关系：子类类型的对象是一个（也是）父类的对象）。高中是一种学校。`HighSchool` 对象 IS-A（一种）`School` 对象。技术上，这意味着在你的程序中，当需要父类对象时，可以使用子类对象。例如：

```
School sch = new HighSchool(...);
```

如果类中的构造函数或方法扩展了要传递的 `School` 类型参数，你可以使用 `HighSchool` 类型的参数调用它。子类对象继承父类的数据类型。

在 Java 中，一个类只能直接扩展一个父类——类没有多重继承。但多个子类可以从同一个父类派生：

```
public class HighSchool extends School ...
public class ElementarySchool extends School ...
public class DrivingSchool extends School ...
```

继承的 IS-A 关系不与对象之间的 HAS-A 关系混淆。X 有“一个”Y 仅仅意味着 Y 是 X 中的一个数据字段（实例变量）。例如，你可能会说 `HighSchool` 有一个`MarchingBand`（行进乐队），但 `HighSchool` 不是一个`MarchingBand`。

## 子类方法

子类继承其父类的所有公共方法，你可以在子类中调用这些方法而无需使用“点前缀”。例如，如果 `School` 有一个方法：

```java
public String getName() { ... }
```

那么 `HighSchool` 的 `registerForAP` 方法可以直接调用它：

```java
public class HighSchool extends School
{
  public void registerForAP()
  {
    String registrationForm = getName() + ...;
  }
  ...
}
```

`HighSchool` 的客户端也可以对任何 `HighSchool` 对象调用`getName`：

```java
HighSchool hs = new HighSchool(...);
String name = hs.getName();
```

子类可以添加自己的方法。它还可以通过提供与其签名完全相同的版本（相同的名称、返回类型以及参数的数量和类型）来重写（重新定义）父类的方法。例如，`School` 可能有一个`toString` 方法，而 `HighSchool` 的 `toString` 可能会对其进行重写。

有时，可能需要从子类显式地调用父类的公共（或受保护）方法。这是通过使用`super.`前缀实现的。例如：

```java
public class HighSchool extends School
{
  public String toString()
  {
    return super.toString() + collegeAcceptance() + ...;
  }
}
```

父类的私有方法在子类中是不可用的。

## 子类构造函数

构造函数是不继承的：子类必须提供自己的构造函数。

子类的构造函数可以使用`super`关键字显式地调用父类的构造函数。例如：

```java
public class School {
    private String name;
    private int numStudents;

    public School(String nm, int num) {
        name = nm;
        numStudents = num;
    }
}

public class ElementarySchool extends School {
    private int highestGrade;

    public ElementarySchool(String nm, int num, int grade) {
        super(nm, num); // 调用 School 的构造函数
        highestGrade = grade;
    }
}
```

如果使用了`super`，它必须是子类构造函数的第一个语句。

## 子类变量

子类继承父类的所有的（静态）变量和实例变量。然而，实例变量通常是私有的（在 AP 子集中始终是私有的）。

> 父类的私有变量在子类中无法直接访问。因此，你可能完全忘记了它们是被继承的——相反，请使用公共访问器和修饰符来获取设置父类实例变量的值。

父类的公共 final 常量（`public static final`变量）可以在任何地方直接访问。

子类可以添加自己的静态变量或实例变量。例如，上面的`ElementarySchool` 类是 `School` 的子类，它添加了一个实例变量：

```java
private int highestGrade;
```

考虑以下部分定义：

```java
public class MailingList {
    private ArrayList<String> people;
    public MailingList() { people = new ArrayList<String>(); }
    public void add(String name) { people.add(name); }
    public ArrayList<String> getPeople() { return people; }
}

public class Subscribers extends MailingList
{
    public Subscribers() { super(); }
    // 返回 people 中名字的数量
    private int size()
    {
        return <expression>;
    }
    // 其他未显示的方法>
}
```

在 `Subscribers` 类的 `size` 方法中，以下哪个选项可以替换`<expression>` 以使该方法按预期工作？

- (A) `super.size();`
- (B) `people.size();`
- (C) `super.people.size();`
- (D) `getPeople().size();`
- (E) 以上均非

## 4.4 类层次结构

`MailingList` 类拥有一个`ArrayList<String> people` 作为实例变量，但实例变量通常是私有的（在 AP 子集中始终是私有的）。

（此处由于原文 4.4 节之后的内容存在大量乱码和重复单词，无法提供有效的语义翻译，建议检查源文本的完整性。）

## 74 第 4 章 程序设计与 OOP 概念

以下哪些声明是有效的？

- I. `Account acct = new BankAccount(10.00);`
- II. `CheckingAccount acct = new BankAccount(10.00);`
- III. `BankAccount acct = new CheckingAccount("Amy", 10.00);`

(A) I 和 II  
(B) 仅 II 和 III  
(C) I 和 III  
(D) I、II 且 III  
(E) 三者均不是

选项 I 似乎是错误的，因为抽象类 `Account` 不能被实例化。但实际上，我们并没有实例化 `Account` —— 我们正在实例化 `BankAccount`，并将新创建的 `BankAccount` 对象赋值给 `Account` 变量。由于 `BankAccount` **是一个** (IS-A(n)) `Account`，我们只需要确保 `BankAccount` 拥有一个接受一个`double`参数的构造函数（它确实有）。选项 I 和 III 作为一组显然是有问题的：要么 `BankAccount` **是一个** `CheckingAccount`，要么 `CheckingAccount` **是一个** `BankAccount`，但两者不可兼得。`CheckingAccount` 继承自 `BankAccount`，所以选项 III 是可以的（同样，前提是 `CheckingAccount` 拥有一个接受`String`和`double`参数的构造函数）。答案是 C。

## 4.5 多态

多态是一种确保为伪装成更通用类型的对象调用正确方法的机制。在上面的示例中，如果执行：

```java
double volume = solids[0].Volume();
```

编译器不知道`solids[0]` 是球体（`Sphere`）还是立方体（`Cube`）。调用哪个`getVolume` 方法的决定被推到了运行时。在 Java 的实现中，每个对象都持有一个指向其方法入口表的指针；因此，对象本身“知道”自己是什么类型的对象。这种技术被称为动态方法绑定——调用哪个方法是在运行时决定的，而不是在编译时。

多态是在语言中实现的；你所做的只需要理解并正确地使用它。

多态发挥作用的一种常见情况是当不同类型的对象混合在一个数组或列表中时，如上面的示例所示。这段代码

```java
for (Solid solid : solids)
    totalVolume += solid.getVolume();
```

无论`solids` 数组中存储了什么`Solids`，这段代码都能工作，因为会为数组中的每个元素调用相应的`getVolume` 方法。即使`solids` 数组中存储了多个不同的`Solids`，情况也是如此。

多态另一种情况是方法接收一个更通用类型的参数，而客户端类向该方法传递一个更具体的类型参数。例如，`System.out.print` 方法的重载版本之一接受`Object` 类型作为参数。该方法的实现如下：

```java
public void print(Object x)
{
    if (x != null)
        print(x.toString());
    else
        print("null");
}
```

该方法适用于任何具有合理`toString` 方法的对象类型`x`（包括`Integer`、`Double` 等）。多态确保了为每个类型的`x` 调用了正确的`toString`。

## 76 第 4 章 程序设计与 OOP 概念

给定：

```java
public class Person {
    private String name;
    Person(String nm) { name = nm; }
    public String getName() { return name; }
    public String toString() { return getName(); }
}

public class OldLady extends Person {
    private int age;
    public OldLady(String nm, int yrs) { super(name); age = yrs; }
    public String getName() { return "Mrs. " + super.getName(); }
    public int getAge() { return age; }
}
```

以下语句的输出是什么？

```java
Person p = new OldLady("Robinson", 92);
System.out.println(p + " " + ((OldLady)p).getAge());
```



(A) Mrs. Robinson, 92  
(B) Robinson, 92  
(C) Robinson  
(D) ClassCastException  
(E) 由于无限递归导致无输出

在这个问题中，我们必须恢复一个复杂的事件序列：

1. 变量`p`被伪装成`Person`类型，但它实际上是一个`OldLady`。
2. `p + " "`调用了`p`的`toString`方法。`OldLady`继承了`Person`的`toString`，因此调用了`Person`的`toString`。
3. `toString`调用`getName`方法。调用哪一个？这是最关键的点。`Person`和`OldLady`都有`getName`方法，由于多态性，将调用`OldLady`的`getName`（尽管我们是在内部调用的）。
4. ...（后续逻辑略）

## 4.6. 接口

在 Java 中，接口比抽象类更抽象。接口没有构造函数或实例变量，只有方法。所有方法都是`public`的。例如：

```java
public interface Fillable {

    void fill(int x);

    int getCurrentAmount();

    int getMaximumCapacity();

}
```

`compareTo`接收一个类型为`T`的参数——通常假设该参数属于实现`Comparable<T>`的同一个类。例如：

```java
public class Flight implements Comparable<Flight>

    ...

    public int compareTo(Flight other)

    {

        return getDepartureTime() - other.getDepartureTime();

    }
```

`String`、`Integer`和`Double`都实现了`Comparable`，但它们实现的方式自然不同。`String`按字典顺序进行比较。比较是区分大小写的，所有大写字母都在所有小写字母之前。`Integer`和`Double`对象按照其数值像通常方式进行比较。

`Comparable<T>`接口没有指定`equals`方法，实现`Comparable<T>`的类不需要`equals`方法即可编译。但重写从`Object`继承的`equals`方法并使其与`compareTo`保持一致更好，避免以后可能出现的错误。例如：

```java
public boolean equals(Object x)

{

    return x instanceof Flight && compareTo((Flight)x) == 0;

}
```

布尔运算符`instanceof`不在 AP 子集中。

注意，你的`equals`方法的参数类型应该是`Object`，这样你的`equals`才能真正重写了`Object`的`equals`。如果你计划将你的类对象存储在 Java 集合（如`HashSet`）中，这一点尤为重要。

## 第 4 章 程序设计与 OOP 概念

考虑以下类：

```java
public class Fraction implements Comparable<Fraction>

{

    private int num, denom;

    public int getNum() { return num; }

    public int getDenom() { return denom; }

    public double doubleValue() { return (double)num / denom; }

    < 其他未显示的构造函数和方法 >
```

以下哪项能够恰当实现`Comparable<Fraction>`接口要求的`compareTo`方法？

- I. `public int compareTo(Object other)`
{
    Fraction f = (Fraction)other;
    return getNum() * f.getDenom() -
    getDenom() * f.getNum();
}

- II. `public int compareTo(Fraction other)`
{
    double x = doubleValue();
    double y = other.doubleValue();
    if (x < y)
        return -1;
    else if (x > y)
        return 1;
    else
        return 0;
}

- III. `public int compareTo(Fraction other)`
{
    return (int)doubleValue() - other.doubleValue();
}

- (A) 仅 I
- (B) 仅 II
- (C) I 和 II
- (D) II 和 III
- (E) I、II 和 III

## 4.6 ~ 接口 81

选项 I 在实际考试中会有问题。首先，它假设学生知道如何计算分数减法，这不能被理所当然。其次，它在可能的算术溢出方面存在歧义：我们假设分数的分子和分母足够小，以至于它们的积不会超出`int`范围吗？幸运的是我们可以消除这一点，因为`compareTo`方法定义是错误的：参数必须是`Fraction`，而不是`Object`。如果我们在那里放入`Object`，编译器将显示一条晦涩的错误信息“Fraction 必须声明为抽象”（未定义`compareTo(Fraction)`）。选项 II 是可行的，尽管它提供了比较的截断结果：`compareTo`只能返回 0、1 或 -1。记住，比较结果的符号才真正重要。选项 III 满足了形式要求，但相差“极小比例”的分数将被视为相等的。这不符合算术方法中`compareTo`的本意。如果像这样的问题恰好漏掉了考试编辑，我们会说答案是 B。

以下代码段的输出是什么？

```java
Comparable<Integer> x = new Integer(123); // 第 1 行

System.out.println(x.compareTo("123")); // 第 2 行
```

- (A) 0
- (B) 正整数
- (C) 第 1 行语法错误
- (D) 第 2 行语法错误
- (E) 一个 ClassCastException

这里有三个独立的问题。首先，在第 1 行，我们将一个`Integer`对象赋值给`Comparable<Integer>`类型的变量。是的，因为`Integer`类实现了`Comparable<Integer>`。其次，在第 2 行，我们将一个字符串传递给`x`的`compareTo`方法。这可以吗？不，从 Java 5.0 开始，`compareTo`的参数类型是被比较对象的类型，在本例中为`Integer`。因此编译器不会允许带有`String`参数的`compareTo`调用。答案是 D。

## 4.7. “设计”题

考试的开放回答部分可能包含一个“设计”题。这种类型的题目要求你设计但不实现一个表示给定情况或模型的简单类。这是题目的“设计”部分。其他部分可能要求你实现一个方法或构造函数，或者编写一些客户端类的代码，该类使用了你所设计的类中的某些构造函数或方法。

> 注意，你被要求在设计部分实现你的类，只需要设计它。如果不被要求这样做，为你的类编写代码将是极大的时间浪费。

设计一个类意味着指定它的构造函数及其参数、公共（可能的私有）方法以及字段（公共静态常量和私有实例变量）。

> 在 AP 考试背景下，所有实例变量都应该声明为私有。

在编写设计部分时，注意以下几点：

- 使用合理的缩进，并在语句之间留出足够的间距。
- 不要包含注释——它们不是必须的。
- 为你的类、方法、参数和字段选择有意义的名字。
- 类名以大写字母开头；方法、参数和实例变量名以小写字母开头。
- 将所有实例变量设为私有，并将它们分组放在类的顶部。
- 将所有构造函数和公共方法放在前面。
- 将此类内部使用的辅助方法设为私有。
- 除了指定的构造函数外，提供一个带参数的无参构造函数可能是好主意。
- 为所有方法指定适当的返回类型。记住构造函数没有返回类型，即使是`void`也没有。

## 4.7 ~ 设计”题

- 根据题目要求提供公共“访问器”（accessor）方法。访问器返回相应数据字段的值。访问器名称可以以“get”开头。例如：

```java
public double getBalance() { ... }
```

- 根据题目要求提供“修改器”（modifier）方法。修改器设置一个或多个数据字段的值。修改器名称可以以“set”或“make”开头。例如：

```java
public void makeDeposit(double amount) { ... }
```

- 将所有访问器归一组，所有修改器归一组，以使类定义更具可读性。

再次，除非要求这样做，否则不要在设计中编写任何代码。

部分 (b) 可能要求你编写客户端类的代码片段，它使用了你在 (a) 部分设计的类。在回答此类问题时，特别注意以下几点：

字体 调用 (a) 部分类的构造函数和公共方法时，参数的数量和类型要与 (a) 部分编写的内容一致。利用此机会检查 (a) 部分的定义。
- 不要在客户端类中直接引用 (a) 部分类的私有实例变量；而是调用访问器和修改器。
- 在客户端类中允许（通常也是）重用与 (a) 部分方法参数相同的变量名称。例如，如果你在 (a) 部分中写了：

```java
public void makeDeposit(double amount) { ... }
```

那么在 (b) 部分你可以写道：

```java
double amount = ...;

...

account.makeDeposit(amount);
```

## 示例题

世界人口协会跟踪不同国家或“人口区”的人口趋势。每个人口区由其名称、人口增长率和按年龄划分的人口数量表描述。年龄范围从0（一岁以下）到某个最大年龄。

## 第 4 章 ~ 程序设计与 OOP 概念

当程序中创建一个新的人口区时，它会接收一个名称和一个按年龄划分的人口数量列表。它还可能接收一个增长率参数。如果没有提供，则增长率将设置为 1.0（不增长）。

对人口区的操作包括以下内容：

- 获取区域名称
- 获取区域的增长率
- 设置新的增长率
- 获取总人口数
- 获取给定年龄以下的人口数
- 调整分布以模拟人口的一年增长（通过一个包含增长率因子的公式计算出的新值来填充“零”槽位）。

这个简化的模型没有考虑不同年龄段的死亡情况。它简单地假设超过按年龄数组中最大年龄的人会立即死亡。

人口区在程序中将由一个名为`PopulationZone`的类表示。另一个类`Demographics`将存储一个人口区列表，例如世界上所有的国家。

- 为`PopulationZone`编写一个类定义，在其构造函数和方法的函数体中只填入“...”。在编写此定义时，你必须：
- 为方法、数据字段和参数选择合适的名称；
- 在适当的地方使用重载方法；
- 提供上述指定的功能；
- 使数据表示与上述规范一致；
- 做出符合信息隐藏原则的设计决策。

不需要注释，但如果需要可以使用注释。

**不要** 编写`PopulationZone`类构造函数或方法的实现代码。

(b) 考虑下面部分指定的`Demographics`类。

```java
public class Demographics

{

    private ArrayList<PopulationZone> countries;

    public double teenRatio(PopulationZone z)

    {

      < Code not shown>

    }

    public String findMostTeens()

    {

      < Code not shown>

    }

}
```

编写一个`teenRatio`方法，计算并返回给定人口区中青少年（13 至 19 岁）人数占总人口的比例。在编写`teenRatio`时，你可以使用你在第 (a) 部分中指定的`PopulationZone`类的任何方法。假设这些方法按照指定的方式工作，无论你在 (a) 部分写了什么。

完成下方的`teenRatio`方法。

```java
// 返回 z 中所有青少年（13 至 19 岁）

// 占总人口的比例

public double teenRatio(PopulationZone z)
```

(c) 编写`Demographics`类的`findMostTeens`方法。该方法返回`countries`列表中青少年占总人口比例最高的国家名称（在两个或多个人口区的青少年比例完全相同的罕见情况下，该方法返回其中任何一个）。在编写此方法时，你可以使用第 (a) 部分的类和第 (b) 部分的方法，并假设它们按照指定的方式工作，无论你在那些部分写了什么。

完成下方的`findMostTeens`方法。

```java
// 从 countries 列表中返回青少年占总人口比例

// 最高的国家；

// 如果多个国家具有相同的最高比例，返回

// 其中任意一个的名称

public String findMostTeens()
```

## 第 4 章 ~ 程序设计与 OOP 概念

(a) 

```java
public class PopulationZone

{

    private String name;

    private double growthRate;

    private int[] countsByAge;

    public PopulationZone() { ... }

    public PopulationZone(String nm, int[] countsByAge) { ... }

    public PopulationZone(String nm, int[] counts, double rate) { ... }

    public String getName() { ... }

    public double getGrowthRate() { ... }

    public int getPopulation() { ... }

    public int getPopulation(int ageLimit) { ... }

    public void setGrowthRate(double rate) { ... }

    public void ageByOneYear() { ... }

}
```

(b)

```java
public double teenRatio(PopulationZone z)

{

    return (double) (z.getPopulation(20) - z.getPopulation(13))

           / z.getPopulation();

}
```

(c)

```java
public String findMostTeens()

{

    int kMax = 0;

    for (int k = 1; k < countries.size(); k++) {

        if (teenRatio(countries.get(k)) > teenRatio(countries.get(kMax))) {

            kMax = k;

        }

    }

    return countries.get(kMax).getName();

}
```

## 第 5 章. 算法

### 5.1. 迭代

大多数编程语言都提供了迭代控制，例如`while`和`for`循环。简单循环适用于对数字范围或一维数组、链表中的元素进行迭代（即重复执行相同操作）。`for`循环是遍历一维数组的一种方便且地道的方式：

```java
for (int k = 0; k < a.length; k++) {

    System.out.println(a[k]); // 你对每个元素需要执行任何操作

}
```

或者

```java
for (T x : a) {

    System.out.println(x);

}
```

其中 T 是元素的数据类型。处理二维数组时，你通常需要嵌套循环。以下代码遍历二维数组`m`：

```java
int r, c, nRows = m.length, nCols = m[0].length;

for (r = 0; r < nRows; r++) {

    for (c = 0; c < nCols; c++) {

        System.out.println(m[r][c]); // 或你需要的任何操作

    }

}
```

注意，如果循环只有一个语句，大括号是可选的：

```java
for (i = 1; i < n; i++)

    for (j = 0; j < i; j++)

        if (a[i] == a[j])

            count++;
```

在“三角形”嵌套循环中，外层循环$i$从 1 运行到$n-1$，内层循环$j$从 0 运行到$i$。在上面的示例中，内层循环在$i = 1, ..., n-1$时运行$i$次，因此比较的总数为$1 + 2 + ... + (n-1) = \frac{n(n-1)}{2}$。

AB 资料包含了链表遍历。`for`循环也可以用于此：

```java
ListNode head;

...



```java
for (ListNode p = head; p != null; p = p.getNext()) {
    System.out.println(p.getValue());
}
```

库类 `ArrayList` 和 `LinkedList` 支持迭代器（见第 6.2 节）。`List` 有一个方法 `iterator` 返回一个 `Iterator` 对象。使用 `while` 循环配合迭代器遍历列表是方便的：

```java
LinkedList<String> list = new LinkedList<>();

...

Iterator<String> iter = list.iterator();

while (iter.hasNext()) {
    String s = iter.next();

    ...
}
```

但“for each”循环让它变得更加简单：

```java
LinkedList<String> list = new LinkedList<>();

...

for (String s : list) {
    ...
}
```

## 最大值和最小值

使用循环的一个常见示例是在数组中找到最大值或最小值（或其位置）：

```java
// 返回 maxValue，使得对于任何 0 <= k <= n-1，maxValue >= a[k]
// 并且对于某些 k，maxValue = a[k]
// 前置条件：数组持有值 a[0], ..., a[n-1]; n >= 1

public double max(double[] a, int n) {
    double maxValue = a[0];
    int k;

    for (k = 1; k < n; k++) {
        if (a[k] > maxValue) {
            maxValue = a[k];
        }
    }

    return maxValue;
}
```

考虑以下方法：

```java
public int mysteryMax(int[] a) {
    int sum, m = 0;

    for (int i = 0; i < a.length; i++) {
        sum = 0;

        for (int k = i; k < a.length; k++) {
            sum += a[k];

            if (sum > m) {
                m = sum;
            }
        }
    }

    return m;
}
```

如果 `a` 包含 `-1, -3, 2, -3, 1`，`mysteryMax(a)` 将返回什么值？

- (A) -2
- (B) -1
- (C) 1
- (D) 2
- (E) 3

该方法返回 `a` 中连续元素的最大和（如果所有值均为负则返回 0）。答案是 E。

考虑以下方法：

```java
// 返回任意两个元素的最大和
// 前置条件：n >= 2; a[0] 到 a[n-1] 已填充了值

public double maxSum(double[] a, int n) {
    <code>
}
```

哪些代码段可以替换 `<code>` 以使方法按照指定的方式工作？

I. 

```java
double max = a[0] + a[1];

for (int i = 1; i < n; i++) {
    for (int j = 0; j < i; j++) {
        if (a[i] + a[j] > max) {
            max = a[i] + a[j];
        }
    }
}

return max;
```

II.

```java
double max1 = a[0], max2 = a[0];

for (int i = 1; i < n; i++) {
    if (a[i] > max1) {
        max1 = a[i];
    }
}

for (int i = 1; i != n; i++) {
    if (a[i] != max1 && a[i] > max2) {
        max2 = a[i];
    }
}

return max1 + max2;
```

III.

```java
double max1 = a[0], max2 = a[1];

if (a[1] > a[0]) {
    max1 = a[1];
    max2 = a[0];
}

for (int i = 2; i < n; i++) {
    if (a[i] > max1) {
        max2 = max1;
        max1 = a[i];
    } else if (a[i] > max2) {
        max2 = a[i];
    }
}

return max1 + max2;
```

### 5.1 ~ 迭代 91

- (A) 仅 I
- (B) 仅 II
- (C) I 和 II
- (D) I 和 III
- (E) I、II 和 III

对于一个问题来说，这些代码非常多，因此我们需要关注关键点。部分 I 效率较低但最直观：使用三层嵌套循环生成所有不同元素对的和，并选择其中最大的一个。

部分 II 基于一个不同的想法：通过对数组进行两次独立的遍历，分别找到最大值和紧随次大值。但它有两个问题：首先，如果最大值变成了 `a[0]`，第二个循环将永远不会更新 `max2`。其次，如果最大值在数组中出现一次以上，它将会失败。方法描述说明该方法寻找的是两个不同元素的最大和，但这些元素的值可能相同。

为了使这种方法生效，需要进行几处微调：

```java
int iMax1 = 0, iMax2 = 0;

for (int i = 1; i < n; i++) {
    if (a[i] > a[iMax1]) {
        iMax1 = i;
    }
}

if (iMax1 == 0) {
    iMax2 = 1;
}

for (int i = 1; i < n; i++) {
    if (i != iMax1 && a[i] > a[iMax2]) {
        iMax2 = i;
    }
}

return a[iMax1] + a[iMax2];
```

在部分 III 中，我们在一次扫描中同时找到最大和次大元素。注意当我们发现另一个值更大的元素时，最大元素是如何变成次大元素的。它运行良好。答案是 D。

## 按序插入

许多应用（包括插入排序）都要求你在向排序数组中插入一个值，同时保持顺序：

```java
// 将 a[k], ..., a[n-1] 适当地移动到
// a[k-1], ..., a[n] 并将新值插入 a[k]，以
// 保持升序顺序

// 前提条件：a[0] <= a[1] <= ... <= a[n-1]; n < a.length

void insertInOrder(int a[], int n, int newValue) {
    // 将值向右移动一位，直到找到
    // 插入的位置：

    int k = n;

    while (k > 0 && a[k-1] > newValue) {
        a[k] = a[k-1];
        k--;
    }

    a[k] = newValue;
}
```

在上面的代码中，我们将数组中的值向右移动一位创建一个空位，然后将新值插入到生成的空位中。注意，移动必须从尾开始，这样每个移动的值都被放在空位中，而不会覆盖任何数据（图 5-1）。

**图 5-1.** 在排序数组中间插入新值

考虑一个数组 `a` 包含 `n` 个升序排列的整数值（`n < a.length`）。以下哪个代码段正确地将 `newValue` 插入 `a` 中并保持升序？

I.

```java
for (int k = n; k > 0; k--) {
    if (a[k-1] <= newValue) {
        a[k] = newValue;
        k = 0;
    } else {
        a[k] = a[k-1];
    }
}
```

II.

```java
int k = n;

while (k > 0 && a[k-1] > newValue) {
    a[k] = a[k-1];
    k--;
}

a[k] = newValue;
```

III.

```java
int k = 0;

while (k < n && a[k] < newValue) {
    k++;
}

for (int j = n-1; j >= k; j--) {
    a[j+1] = a[j];
}

a[k] = newValue;
```

- (A) 仅 I
- (B) 仅 II
- (C) 仅 III
- (D) I 和 II
- (E) II 和 III

当你必须判断此类代码是否正确时，请检查边界条件：如果你必须在数组的最开头或最末尾插入值，代码是否仍然有效？

例如，部分 I 看起来很好——与上面描述的 `insertInOrder` 方法类似。但如果 `newValue` 小于数组中的所有值，则什么都没有被插入。部分 II 等同于上面的 `insertInOrder` 代码。部分 III 使用了更具步骤化的方法：首先找到插入位置，移动该位置之上的值，然后插入。在部分 III 中，只需检查此代码在 `newValue` 为最小值和最大值时是否有效即可——这意味着没有陷阱。答案是 E。

## 循环不变性

AB 考试考生应该熟悉循环不变性的概念。循环不变性是关于循环的断言，它与循环的目的有关，并且在循环的每次迭代之前和之后都成立。这个断言通常表示为循环中变量之间的关系。

循环不变性用于形式化地推理程序并证明其正确性，而无需跟踪循环中的所有迭代。如果你能确定断言在第一次迭代之前为真，并且对于任何迭代，如果断言在迭代之前为真则在迭代之后仍然为真，那么你的断言就是循环不变性。如果不是，你仍然可以毫不困难地回答关于循环不变性的问题。

考虑以下代码段：

```java
int count = 0;
int n = n;
int k = 2;

while (k <= n) {
    if (isPrime(k)) {
        count++;
    }

    k++;
}
```

以下哪些是上述代码的循环不变性？

- I. `k` 是质数
- II. `n` 是质数
- III. `count` 等于 `k`

- (A) 仅 I
- (B) 仅 II
- (C) 仅 III
- (D) I 和 II
- (E) II 和 III

部分 I 不是循环不变性，因为 `k` 在循环中改变。部分 II 不是循环不变性，因为 `n` 是常数。部分 III 不是循环不变性，因为 `count` 并不等于 `k`。（此处，重新审视逻辑，似乎题目选项设计特定，但根据标准算法题逻辑，通常考察的是满足循环条件的断言。根据文意，此处应为逻辑推导。）

## 5.2 乱码文本与翻译错误

注：此处原文文本似乎乱码，已根据逻辑重整理。

注：原文最后部分存在大量重复和乱码，通常考察的是在循环前后成立的断言。

## 5.2 顺序搜索与二分搜索

```java
// 返回 target 的索引，如果不在数组中则返回 -1
// 前提：数组已排序

int sequentialSearch(int a[], int n, int target) {
    for (int i = 0; i < n; i++) {
        if (a[i] == target) {
            return i;
        }
    }

    return -1;
}
```

二分搜索是排序数组查找 `target` 更快的方法：

```java
int binarySearch(int[] a, int n, int target) {
    int left = 0;
    int right = n - 1;
    int middle;

    while (left <= right) {
        middle = (left + right) / 2;

        if (target == a[middle]) {
            return middle;
        } else if (target < a[middle]) {
            right = middle - 1; // 继续搜索左侧
        } else {
            left = middle + 1; // 继续搜索右侧
        }
    }

    return -1;
}
```

在 `2^k - 1` 个元素的数组中，二分搜索最多需要 `k` 次迭代。换句话说，在 `n` 个元素的数组中，二分搜索需要 `log n` 次迭代。因此，在 1,000,000 个元素的数组中，只需要 20 次迭代。相比之下，顺序搜索在 `n` 个元素的数组中平均需要 `n/2` 次迭代，在最坏的情况下可能需要 `n` 次。

假设有两个程序，一个使用二分搜索，另一个使用顺序搜索，在包含 30 个元素的排序数组中找到随机目标值所需（平均）时间相同。在 1000 个元素的数组上，二分搜索程序比顺序搜索程序快多少？

- (A) 2 倍
- (B) 10 倍
- (C) 16 倍
- (D) 33 倍
- (E) 50 倍

二分搜索对于 30 个元素需要 5 次迭代（`32 = 2^5`），对于 1024 个元素需要 10 次迭代（`1024 = 2^10`）。所以二分搜索在 1000 元素数组上的运行时间大约是 30 元素数组的 2 倍。顺序搜索大约运行 33 倍（`1000 ≈ 30 * 33`）。在 1000 个元素上，二分搜索快了 `33 / 2 = 16.5` 倍。答案是 C。

## 5.2 顺序查找与二分查找

电子邮件地址是一个由字母数字字符、一个或多个“点”以及一个“@”组成的字符串。最后一个点之后的短子字符串被称为域名后缀。例如，在 `jane.lee@math.bestacad.org` 中，“org”就是后缀。以下哪些方法可以找到后缀的起始位置？

- I. 改进后的顺序查找，我们扫描整个数组并记录给定字符最后一次出现的位置。
- II. 改进后的顺序查找，从数组末尾开始向前进行。
- III. 改进后的二分查找，其中每个字母数字字符被视为 `'0'`，点和 `@` 被视为 `'1'`。
- (A) 仅限 I
- (B) 仅限 II
- (C) 仅限 III
- (D) I 和 II
- (E) II 和 III

该任务基本上是找到字符串中的最后一个点。方法 I 不是最高效的，但它是可行的：

```java
for (int k = 0; k < email.length(); k++) {
    if (email.charAt(k) == '.') {
        dotPos = k;
    }
}

// Characters, charAt, and char constants are not in the AP subset

return dotPos;
```

方法 II 运行快一点：

```java
for (int k = email.length() - 1; k >= 0; k--) {
    if (email.charAt(k) == '.') {
        return k;
    }
}
```

方法 III 的描述试图用一个与二分查找没有关系的二进制系统来误导你。后者在这里不起作用，因为字符串没有经过排序，且点散布在字母数字字符之间。答案是 D。

## 5.3 选择排序与插入排序

排序意味着根据项目的值或作为项目部分的某些键值，将项目列表按升序或降序排列。排序算法通常讨论表示为数组的列表。在 AB 考试中，排序题可能涉及链表、队列或优先队列。

**选择排序和插入排序被称为二次阶级排序，因为它们使用了两个直观的嵌套循环，且所需的比较次数大约与 `n^2` 成正比。**

### 选择排序

在选择排序中，我们让 `k` 从 `n` 迭代到 2：我们找到前 `k` 个元素中最大的一个，并将其与第 `k` 个元素交换。

```java
// sorts values in an ascending order
// precondition: array contains a[0], ..., a[n-1] (n >= 1)

public void selectionSort(int[] a, int n) {
    int maxPos;

    for (int k = n; k >= 2; k--) {
        maxPos = 0;

        for (int i = 1; i < k; i++) {
            if (a[i] > a[maxPos]) {
                maxPos = i;
            }
        }

        // Swap a[maxPos], a[k-1]

        int temp = a[maxPos];
        a[maxPos] = a[k-1];
        a[k-1] = temp;
    }
}
```

在上述方法中，内部循环运行 `k - 1` 次，对于 `k = n, n - 1, ..., 2`。

**选择排序中的总比较次数总是相同的：**

`(n - 1) + (n - 2) + ... + 1 = n(n - 1) / 2`

在选择排序的另一种变体中，我们找到元素 `a[k], ..., a[n-1]` 中最小的，并将其与 `a[k]` 交换（对于 `k = 0, ..., n - 2`）。

### 插入排序

在插入排序中，我们让 `k` 从 2 迭代到 `n`。我们保持前 `k - 1` 个元素有序，并将第 `k` 个元素插入到它所属的位置：

```java
// sorts n values in a in ascending order
// precondition: array contains a[0], ..., a[n-1] (n >= 1)
```



`public void insertionSort(int[] a, int n)`

```
{
    for (int k = 2; k <= n; k++) {
        int temp = a[k-1];
        int i;
        for (i = k-1; i > 0; i--) {
            if (a[i] <= temp)
                break;
            else
                a[i] = a[i-1];
        }
        a[i] = temp;
    }
}
```

在插入排序这个版本中，如果数组已经排序，内部循环只需运行一次比较，我们立即退出。此时该方法总共需要 `n-1` 次比较。这是最好情况：该方法不是以二次时间执行，而是以线性时间执行。

这种插入排序实现的最坏情况是数组按倒序排列的。这时，内部循环运行 `k-1` 次，整个方法所需的比较次数与选择排序一样多：

`1+2+...+(n-1) = n(n-1)/2`

平均情况大约是该数字的一半，仍然大约与 `n^2` 成正比。

上述方法只是选择排序和插入排序实现的示例。可能的其他变体。

考虑升序排序数组元素的任务。以下哪些陈述是正确的？

- I. 选择排序所需的比较次数总是比插入排序多。
- II. 插入排序所需的比较次数总是比选择排序多。
- III. 插入排序平均比较次数比选择排序多。
- (A) 仅限 I
- (B) 仅限 II
- (C) 仅限 III
- (D) I 和 II
- (E) II 和 III

答案是 C。

## 5.4. 递归

你可能觉得递归愉快或困难，取决于你的口味。这种方法调用自身——这就是递归。关于它注意两点。第一，如果 `n <= 0`，方法什么都不做。递归方法的退出（可能是在没有递归调用之后）被称为基准情况（或停止情况）。在这个方法中，基准情况什么都不做。第二，当方法调用自身时，它使用的参数比原始参数小。参数必须变化，通常是朝着基准情况的方向减少，以便递归在某处终止。

与其尝试展开并跟踪该方法中的所有递归调用，不如先更正式地对其属性进行推理。该方法打印一些数字，后面跟着相同数量的。当调用 `n=4` 时，方法立即打印一行包含 4 个减号和 4 个加号的行。但不是全部：在打印第一行后，方法调用了 `mystery(3)`，它必须以较小的规模执行 `mystery(4)` 所做。

## 38

考虑以下方法：

```java
public void mystery(int n)
{
  if (n <= 0)
    return;
  for (int i = 0; i < n; i++) {
    System.out.print("-");
  }
  for (int i = 0; i < n; i++) {
    System.out.print("+");
  }
  System.out.println();
  mystery(n-1); // 递归调用
}
```

当调用 `mystery(4)` 时，输出是什么？

- (A) ----
- (B) ---++++, ---++++, ---++++
- (C) --++, ---+++, ---++++
- (D) -+, --++, ---+++, ---++++
- (E) --++++, --+++, --++, -+

## 5.4 ~ 递归

这个问题稍微棘手，但 D 和 E 仍然是唯一可能的答案：

(D)
(E)
--+  ++++
---  ---++
+++  --+
++++  -

我们必须选择 D，因为 `mystery(4)` 最后执行的操作是打印 `----`。

（如果你更倾向于数学，可以按照如下方式进行推理。`mystery(4)` 打印一个向上或向下的三角形。让我们猜一下这个方法的通用行为：例如，“`mystery(n)` 打印一个有 `n` 行且向上的三角形”。假设这对于 `n=3` 是正确的。`mystery(4)` 首先在递归调用中打印一个有 3 行的三角形，然后添加最长的第四行。我们的假设符合这一点，所以答案应该是 D。）

考虑以下方法：

```java
void mysteryMix(String str)
{
    int len = str.length();
    if (len >= 3) {
        mysteryMix(str.substring(0, len / 3));
        System.out.print(str.substring(len / 3, 2*len / 3));
        mysteryMix(str.substring(2*len / 3));
    }
}
```

调用 `mysteryMix("la-la-la!")` 时的输出是什么？

- (A) la-la-la!
- (B) ala-a
- (C) la-la-la-l
- (D) lla-l
- (E) a-la-a

许多 AP 题目混合了不相关的学科。这道难题测试了递归和字符串。我们从一个包含九个字符的字符串开始，但立即递归地调用 `mysteryMix` 处理一个三个字符的字符串。因此，我们需要看看调用 `mysteryMix("xyz")` 时首先发生了什么。该调用打印了中间字符 "y"，并且当 `len=3` 时，另外两个递归调用什么都没做。返回到原始九个字符字符串时也没有任何额外操作。两个递归调用各打印了一个字符，而 `System.out.print` 打印了三个字符，因此输出必须五个字符。这排除了 A、C 和 E。打印的第一个字符是字符串三分之一部分的中间字符，即 "a"。答案是 B。

## 二分查找的递归实现

二分查找算法的描述本质上是递归的，可以很容易用递归实现。

考虑以下不完整的二分查找递归实现：

```java
// 返回等于 target 的元素的位置，或者返回 -1，
// 如果 target 不在值 a[left], ..., a[right] 中
// 前提：数组包含从 a[left] 到 a[right] 的值，且按升序排序
public int binarySearch(int a, int left, int right, int target)
{
    int targetPos = -1;
    int middle;
    < statement 1>
    middle = (left + right) / 2;
    if (target == a[middle])
        < statement 2>
    else if (target < a[middle])
        targetPos = binarySearch(a, left, middle - 1, target);
    else
        targetPos = binarySearch(a, middle + 1, right, target);
}
return targetPos;
```

以下哪项可以替换 `<statement 1>` 和 `<statement 2>`，使得 `binarySearch` 方法按预期工作？

| `<statement 1>` | `<statement 2>` |
|---|---|
| (A) `while (left <=)` | `return targetPos;` |
| (B) `while (left <=)` | `return middle;` |
| (C) `while (left <)` | `targetPos = middle;` |
| (D) `if (left <=)` | `targetPos = middle;` |
| (E) `if (left <)` | `return middle;` |

在 `while` 和 `if` 之间选择，这是一个递归解决方案，递归取代了迭代。这排除了 A、B 和 C。在 D 和 E 选项中，Statement 2 是可行的，但 E 中的 Statement 1 遗漏了 `left == right` 的情况。答案是 D。

## 5.5 ~ 归排序 [以及快速排序]

[ AB 考试非常经常包含关于二叉树的简答题，因此你必须熟悉处理二叉树的递归方法。在考试的时间限制下，以任何其他方式处理它们都是不实际的。二叉树将在第 6 章中复习。 ]

## 5.5. 归排序 [以及快速排序]

归并排序和快速排序是两种基于“分治法”原则的递归排序算法。两种算法平均需要 `n log n` 次比较，而平方级排序需要 `n^2` 次比较。这种差异对于大型数组来说可能非常显著。例如，对于 1024 个元素，归并排序和快速排序的运行速度比选择排序和插入排序快 100 倍。

## 归并排序

归并排序的思想简单：将数组分为两个大致相等的部分；（递归）排序每个部分，然后将它们合并成一个排序后的数组（图 5-2）。归并排序通常需要一个临时数组在将它们合并回原始空间之前存放那两个已排序的部分。

将数组分为两半：

```
A: 1 7 4 9:3 5 8 6 2
```

（递归地）排序每个部分并复制到 temp 中：

```
temp: 1 4 7 9:2 3 5 6 8
```

将两个部分中的元素按升序合并回数组中：

```
temp: 1 4 7 9:2 3 5 6 8
A: 1 7 4 9:3 5 8 6 2
```

（图 5-2. 归并排序）

## 5 ~ 算法

考虑以下归并排序的实现：

```java
// 将 a[n1]...a[n2] 升序排序
// 前提：n1 <= n2 < length
public void sort(int[] a, int left, int right) {
    if (left >= right)
        return;
    int middle = (left + right) / 2;
    sort(a, left, middle);
    sort(a, middle + 1, right);
    // merge
```

*(注：这里的 OCR 文本有些混乱，我将根据标准的归并排序逻辑进行整理翻译)*

以下是归并排序的实现：

```java
// 将 a[n1]...a[n2] 升序排序
// 前提：n1 <= n2 < length
public void sort(int[] a, int left, int right) {
    if (left >= right)
        return;
    int middle = (left + right) / 2;
    sort(a, left, middle);
    sort(a, middle + 1, right);
    // merge
```



实际上，根据提供的文本：“归并排序的实现... a[n1]...a[n2]...”

以下哪种属性会让包含 1000 个元素的数组在`quickSort(a, 0, 999)`达到最佳时间？

- (A) 当`a[0]`, ..., `a[999]`已经是升序排列的
- (B) 当`a[0]`, ..., `a[999]`降序排列
- (C) 当`a[0]`是`[0, ..., a[999]]`的中位数，且剩下的 999 个元素按升序排列
- (D) 当`a[999]`是`[0, ..., a[999]]`的中位数，且剩下的 999 个元素按升序排列
- (E) 当`a[0]`, ..., `a[999]`是随机排列的

## 快速排序

快速排序没有那么直观，但它确实有效。它的工作原理如下：选择一个“基准”元素。重排数组中的所有元素，使得基准将数组分为两个。基准左侧的所有元素应该小于等于它。基准右侧的所有元素应该大于等于它。递归排序每个部分。

归并排序和快速排序是两种基于“分治法”原则的递归排序算法。两种算法平均需要`n log n`次比较，而平方级排序需要`n^2`次比较。这种差异对于大型数组来说可能非常显著。例如，对于 1024 个元素，归并排序和快速排序的运行速度比选择排序和插入排序快 100 倍。平均而言，它比归并排序快一点，但它不需要额外的存储空间。

AB 考试也涵盖了堆排序，该内容将在第 6.7 节中讨论。

## 5.6. 数据组织问题

AP CS 考试可能包含关于针对特定任务表示数据的合适方式的选择题。以下是几个 A 级此类问题的示例。AB 级考生拥有更丰富的标准数据结构工具箱——列表、二维数组、树、哈希表、映射等。这些内容将在第 6 章中讨论。

考虑设计一种表示电子邮件服务器系统中订阅者信息的数据结构。除了其他属性外，订阅者有一个 ID 和未读新消息数量。所有有未读邮件的订阅者信息将存储在一个`Subscriber`对象的数组中。考虑两种可能的实现：

- 方法 A：以任意顺序存储数组项。
- 方法 B：按订阅者 ID 的排序顺序存储数组。

考虑以下操作：

- 操作 1：增加指定 ID 订阅者的消息数量。
- 操作 2：向订阅者列表添加一个具有给定消息数量的新订阅者。

以下叙述哪是正确的？

(A) 使用方法 A 实现操作 1 和操作 2 的效率都比方法 B 高。
(B) 使用方法 B 实现操作 1 和操作 2 的效率都比方法 A 高。
(C) 使用方法 A 实现操作 1 的效率更高；使用方法 B 实现操作 2 的效率更高。
(D) 使用方法 B 实现操作 1 的效率更高；使用方法 A 实现操作 2 的效率更高。
(E) 使用任何方法实现操作 1 和操作 2 的效率都一样。

这类问题可能测试你的阅读理解能力，但从实际技术难度来说，它们并没有超出常识太多。这确实有助于你很好理解各种数据结构以及它们在不同算法中的用法。在这里，我们需要在数组中查找具有给定键（订阅者 ID）的元素，以及向数组中插入新值。想到的相关思路是顺序查找和二分查找、顺序插入值以及在末尾插入。

你可能想记一个小表，以防在方法和操作之间混淆；然后勾选相应的方框（哪种更快）：

| A: 随机 | B: 排序 |
|---|---|
| 1. 增加消息数 — “查找” | |
| 2. 添加订阅者 — “插入” | ✓ |

显然，如果你需要担心顺序，将订阅者添加到排序后的数组中将比直接将其甩在随机数组的末尾要费得多。单此这一点就排除了选项 B、C 和 E。（不要试图得太聪明，认为如果数组不够大你可能需要重新分配并复制数组。这不是这道题的重点）

在排序数组中查找一个值更容易吗？当然了。如果你记得可以在排序数组上使用二分查找，那太好了。但即使你不知道，这也是一个很好的猜测。数组是排序的这一事实可能对搜索操作没有坏处。这排除了 A。答案是 D。

## 第 5 章 ~算法

第 45-46 题涉及以下信息：

College Board 在`K`天（`K >= 14`）内对`N`科目（`N >= 34`）进行 AP 考试。每个科目仅在一天提供。科目由 1 到`N`的整数表示。对于一个跟踪考试日程的应用正在考虑两种不同的设计：

设计 1：

考试日程信息存储在一个一维整数数组中。对于`K`天中的每一天，都有一个条目代表该天的考试数量，随后跟是该天提供的科目列表。例如，如果第一天有科目 29 和 31 的两门考试，而第二天没有考试，数组将以 2, 29, 31, 0, 开始。

设计 2：

日程表示为一个布尔值数组，包含`N`组，每组包含`K`个值。第`n`组中第`k`个元素的`true`值表示第`n`个科目在第`k`天提供。

关于在 Java 中实现这两种设计的空间需求，以下叙述哪是正确的？

(A) 设计 1 需要更少的空间。
(B) 设计 2 需要更少的空间。
(C) 哪种设计需要更多空间取决于`N`的值。
(D) 哪种设计需要更多空间取决于`K`的值。
(E) 哪种设计需要更多空间取决于特定平台上表示布尔和整数值所需的字节数。

参见第 46 题的解答。

## 5.6 ~ 数据组织问题

## 111

假设选择了设计 2，并且该方法以高效的方式实现：

给定一个 1 到`N`之间的科目编号和一个 1 到`K`之间的日期，如果给定的科目在指定的日期提供，该方法返回 true，否则返回 false。

以下叙述哪是正确的？

(A) 方法中花费的平均时间与`N`成正比。
(B) 方法中花费的平均时间与`K`成正比。
(C) 方法中花费的平均时间与科目总数（`N`乘以`K`）成正比。
(D) 方法中花费的平均时间与考试数量成正比。
(E) 方法中花费的时间取决于`N`或`K`，也不取决于考试的分布。

> 上述两个问题比较了相同数据的空间和时间需求（设计 1 是列表，设计 2 是查找表）。如果你从未听过查找表的术语，你也可以推理出来。

在第 45 题中，设计 1 的空间需求是`K+N`个整数；设计 2 的空间需求是`N * K`个布尔值。在 Java 中，一个整数占用四个字节，而布尔值可能占用一个字节。答案是 A。

在第 46 题中，你必须知道可以直接访问数组的任何元素，`table[i]`。这种属性被称为随机访问，它是数组的核心。如果第`n`个科目在第`k`天提供，则`table[(n-1)*K + (k-1)]`为 true。（这里，`table`应该是二维数组，但这些不属于 A 子集。）答案是 E。

# 114 第 6 章 ~ AB 话题：链表、栈、队列、树等等。

| 接口 | 目的 | 实现 |
|---|---|---|
| `java.util.List<E>` | 类型为`E`的对象列表，`x0, ..., x-1`，可以通过索引访问；可以包含重复值。 | 作为一个数组实现：`java.util.ArrayList<E>` 作为一个链表实现：`java.util.LinkedList<E>` |
| 未为栈提供接口 | 用于处理嵌套结构或分支过程中的临时存储；项按 LIFO（后进先出）方式访问（使用`push`和`pop`方法）。 | `java.util.Stack<E>` |
| `java.util.Queue<E>` | 用于按到达顺序处理项或事件的临时存储；项按 FIFO（先入后出）方式访问（使用`add`和`remove`方法）。 | 作为一个链表实现：`java.util.LinkedList<E>` |
| `java.util.Set<E>` | 类型为`E`的对象集合；不允许重复值；有一种方法可以判断给定值是否在集合中（`contains`方法）。 | 作为二叉搜索树实现：`java.util.TreeSet<E>` 作为哈希表实现：`java.util.HashSet<E>` |
| `java.util.Map<K, V>` | 键值对集合：每对都有一个键（类型为`K`）和一个与之关联的值（类型为`V`）；键形成一个集合（不允许重复键）；有方法添加新对并获取与键关联的值（`put`和`get`方法）。 | 作为二叉搜索树实现：`java.util.TreeMap<K, V>` 作为哈希表实现：`java.util.HashMap<K, V>` |
| `java.util.PriorityQueue<E>` | 用于按“优先级”或排名检索项（使用`add`和`remove`方法）。 | 作为一个堆实现：`java.util.PriorityQueue<E>` |

表 6-1 AP CS AB 考试中的集合及其实现

## 6.2 列表 (LISTS)

你应该能够以自实现的方式操作链表和二叉树，使用开发委员会提供的`ListNode`和`TreeNode`类，并对堆有通用的理解——堆是一种用于实现优先级队列的特殊二叉树。

第 6.8 节回顾了算法的 Big-Oh 分析，这也是必修考点。

## 6.2. 列表 (Lists)

列表是按顺序排列的项的集合。我们只考虑持有对象（而不是 int 或 double）的列表。如果你想持有整数或双精度浮点数，请使用包装类（`Integer`或`Double`）的对象。列表可以包含重复的值（相同的对象，`obj1 == obj2`，或“等值”的对象，`obj1.equals(obj2)`）。列表的元素可以通过索引访问。索引从 0 开始。

`java.util.List<E>`是一个描述列表方法的库接口。尖括号中的`E`是“类型参数”：它指定了存储在列表中的对象类型。在程序中，`E`被替换为特定类型的对象。例如，我们可以有一个`List<String>`或`List<Integer>`。AP 考试子集包含`List<E>`的以下方法：

```java
int size(); // 返回项的数量

boolean contains(E x);                   // 在列表中是否存在

void add(int index, E x);               // 在列表末尾添加 x

E get(int index);                       // 在索引处插入 x

E set(int index, E x);                  // 将索引处的元素设为 x

E remove(int index);                    // 设置旧值

E remove(int index);                    // 移除索引处的项

Iterator<E> iterator();                 // 返回其迭代器

ListIterator<E> listIterator();        // 返回一个迭代器
                                         // (迭代器将在下文中讨论)
```

请注意 Java 列表的以下属性：

- 列表持有对对象的引用（即，对象的地址）。
- 同一个对象可以被多次插入到列表中，并属于多个列表。
- 通常情况下，如果一个对象被插入到列表中，它可以被修改；然而，`Strings`、`Integers`、`Doubles`是不可变对象，不能被修改。
- 索引会检查有效范围，从 0 到`list.size() - 1`；在适当的实现中，如果传入无效索引参数将抛出`IndexOutOfBoundsException`异常。
- `add(index, x)`和`remove(index)`会适当调整所有位于添加或删除项之后的项的索引，并调整列表的大小。

以下代码段的输出是什么？

```java
List<String> items = ... < 创建一个空列表>

items.add("One");

items.add("Two");

items.add("Three");

items.add("Four");

for (int i = 0; i < items.size(); i++) {

    System.out.print(items.remove(i) + " ");

}

System.out.println();
```

- (A) 空行
(B) One Two Three Four
(C) One Two Three
(D) One Three
(E) IndexOfBoundsException

`OutOfBoundsException`不可能，因为`i`永远不会为负，且在每次迭代中`i < items.size()`都成立。一定会有输出，因为当`i = 0`时会打印 "One"。技巧在于在第一次迭代之后，索引被调整了："Two"变成了索引 0 处的项，“Three"变为 1 处，“Four"变为 2 处，而`i`变成了 1。所以第二个输出值是 "Three"。在第二次迭代后，迭代器变为 2。答案是 D。

## java.util.ArrayList<E>

我们已经在第 2.6 节介绍过 ArrayList。这里我们在集合框架的背景下再次简要查看它。

`ArrayList<E>`使用数组实现了`List<E>`接口。它提供了对列表元素的直接访问，`get`和`set`方法非常高效。ArrayList 的无参构造函数分配一个初始容量并设置为 0（随着值的添加，数量可能会超过容量）。当容量不足时，会分配一个新的数组，将旧值复制进去并丢弃旧数组。这一切会自动发生。

`add(index, x)`和`remove(index)`对于 ArrayList 是低效的，因为它们需要向右或向左移动所有元素。`java.util.LinkedList<E>`通过重新连接提供了更高效的方法来插入或删除项。

`java.util.LinkedList<E>`对于双向链表有一些额外的方法：

```java
void addFirst(E x);           // 在开头添加 x

void addLast(E x);             // 在末尾添加 x

E getFirst();                  // 返回第一项

E getLast();                   // 返回最后一项

E removeFirst();               // 移除第一项
                                并其值

E removeLast();                // 移除最后一项
                                返回其值
```

这些方法包含在 AP 考试子集中。

## 列表遍历和迭代器

使用索引对列表遍历——

```java
for (i = 0; i < list.size(); i++)

{

  Object obj = list.get(i);

}
```

——适用于 ArrayList 和 LinkedList，但对于 LinkedList 是低效的。更好的方法是使用“增强”迭代器。

迭代器是与列表关联的对象。迭代器维护列表中的当前位置，并提供一个检查是否有更多可用值的方法和一个返回下一个值的方法。AP 子集包含了列表的两种迭代器：`java.util.Iterator<E>`和`java.util.ListIterator<E>`。`List<E>`接口指定了`iterator`和`listIterator`方法，分别返回列表的`Iterator<E>`对象和`ListIterator<E>`对象。

你可以将迭代器想象成位于列表中两个元素之间的“光标”或“光标”。当创建一个迭代器时

`Iterator<E>`接口规定了三个方法：

```java
boolean hasNext(); // 如果有更多可供此迭代器访问的项，则返回 true

E next(); // 返回下一个项

void remove(); // 从列表中删除上一次
// 调用 "next" 返回的项
```

API 子集中附加的`ListIterator<E>`方法有：

```java
void add (E x); // 在当前位置插入 x
//（但在“光标”之前）

void set (E x); // 将 x 设置为上一次
// 调用 next 返回的元素
```

一种使用迭代器和 while 循环遍历列表的方便惯用法：

```java
List<String> list = new LinkedList<String>();

...

Iterator<String> it = list.iterator();

while (it.hasNext()) {

  String s = it.next();

  ...
```

迭代器对于实现为`ArrayList`和`LinkedList`的列表来说效率是相同的，因此当列表的确切类型未知时，它们是遍历列表的首选方法。

"for each" 循环仅仅是创建迭代器并遍历列表（或任何其他集合）的快捷方式，当你不需要调用`add`、`set`或`remove`方法时。例如：

```java
for (Double x : list) {

  System.out.println(x);

}
```

等同于

```java
Iterator<Double> it = list.iterator();

while (it.hasNext()) {

  System.out.println(it.next());

}
```



> 当你需要从头到尾遍历列表而不添加或删除列表项时，请使用“for each”循环。

# 第 6 章 ~ AB 主题：链表、栈、队列、树等

下列哪些代码段以 O(n) 时间（即时间与 n 大成正比）计算 `LinkedList<Integer> counts` 中所有值的和，其中 n = `counts.size()`？

I.

```java
int sum = 0;
for (Integer x : counts)
    sum += x.intValue();
```

II.

```java
int sum = 0;
for (int i = 0; i < counts.size(); i++)
    sum += counts.get(i).intValue();
```

III.

```java
int sum = 0;
for (int i = counts.size() - 1; i >= 0; i--)
    sum += counts.get(i).intValue();
```

- (A) 仅 I
- (B) 仅 II
- (C) I 和 II
- (D) II 和 III
- (E) I、II 和 III

正如我们所见，段 I 中的“for”循环使用迭代器按顺序访问列表的元素。从一个元素到下一个元素需要常数时间，整个循环的总时间与列表的长度成正比。在段 II 和 III 中，`counts.get(i)` 所花费的时间取决于 i，每次当我们需要从链表的头部或尾部开始并追踪第 i 个节点时。平均而言，`counts.get(i)` 需要的时间与 n 成正比，且段 II 和 III 中 for 循环的总时间都与 n² 成正比。答案是 A。

## 6.2 ~ 列表

考虑以下方法：

```java
// 从列表中移除重复值

// 前提条件：列表包含按字母顺序排列的字符串

public void removeDuplicates(List<String> list)
{
    ListIterator<String> it = list.listIterator();
    String prev = null, current;

    while (it.hasNext()) {
        <statement1>;
        if (current.equals(prev)) {
            <statement2>;
        }
        prev = current;
    }
}
```

以下哪些是 `<statement1>` 和 `<statement2>` 的适当替换项，使该方法按说明工作？

| | `<statement1>` | `<statement2>` |
| :--- | :--- | :--- |
| (A) | `current = it.next()` | `it.remove(i)` |
| (B) | `int i = it.next()` | `list.remove(i)` |
| (C) | `int i = it.next().intValue()` | `list.remove(i)` |
| (D) | `current = it.next()` | `list.remove(it)` |
| (E) | `it = it.next()` | `list.remove(it)` |

> 这是一个语法错误。`it.next()` 返回列表中的下一个对象；它不是列表的索引。通常，使用列表的 `add` 或 `remove` 方法是错误的，因为迭代器可能会不同步——你应该坚持调用迭代器的方法。答案是。

注意，在上面的示例中，我们可以使用 `Iterator` 而不是 `ListIterator`，因为我们没有调用迭代器的 `add` 或 `set` 方法。

# 链表：自己实现

在你开始构建链表之前，你需要一种表示列表节点的方法。AP 开发委员会提供了一个 `ListNode` 类，以确保考试题目能够以一致的方式表述和回答。

```java
public class ListNode
{
    private Object value;
    private ListNode next;

    // 构造函数：
    public ListNode(Object value, ListNode initNext) {
        value = value;
        next = initNext;
    }

    public Object getValue() { return value; }

    public ListNode getNext() { return next; }

    public void setValue(Object newValue) { value = newValue; }

    public void setNext(ListNode initNext) { next = initNext; }
}
```

`getNext` 方法返回指向下一个节点的链接。假设 `head` 指向列表的第一个节点。以下代码将遍历列表并打印所有值：

```java
for (ListNode node = head; node != null; node = node.getNext())
    System.out.println(node.getValue());
```

> 注意，`ListNode` 不是泛型类；它持有 `Object`。你需要将 `ListNode` 持有的值转换回其类型。例如：

```java
ListNode node = new ListNode("Z", null);
```

# 问题 50-51 使用以下类

```java
public class Student {
    public Student(String name, double gpa) { <code>
}
```

假设 `studentList` 指向一个学生列表，下列哪些代码段为名为“Lobachevsky”、GPA 为 3.7 的学生分配一个新节点，并将其添加到列表开头？

- (A) `studentList = new Student("Lobachevsky", 3.7), studentList);`
- (B) `studentList = new ListNode("Lobachevsky", 3.7), studentList);`
- (C) `studentList = new ListNode(new Student("Lobachevsky", 3.7), studentList);`
- (D) `x = new Student("Lobachevsky", 3.7); studentList.setValue(x);`
- (E) `x = new Student("Lobachevsky", 3.7); ListNode node = new ListNode(x, null); studentList.setNext(node);`

> A 混淆了两种类型的对象：`Student` 和 `Node`。`ListNode` 持有 `Student`，但它不是 `Student`。B 犯了类似的错误：`ListNode` 持有整个 `Student` 对象，而不是它的字段。D 替换了第一个节点的值（如果列表为空则抛出 `NullPointerException`）——而不是创建一个新节点。E 要么抛出异常，要么切断第一个节点并连接新节点。新列表将有两个节点；其余节点将丢失。C 首先创建一个给定名称 GPA 的 `Student` 对象，然后创建一个持有该学生并指向列表旧头部的节点，这实际上是将新节点添加到列表头部。答案是 C。

# 第 6 章 ~ AB 主题：链表、栈、队列、树等

考虑一个将给定学生添加到列表末尾并返回列表的方法：

```java
// 将学生添加到列表末尾并返回新列表

// 前提条件：list 为空或指向学生列表

public ListNode insert(ListNode list, Student student)
{
    ListNode tail = list;
    <code>
    return list;
}
```

以下哪些代码段可以替换 `<code>` 以使 `insert` 方法按预期工作？

I.

```java
if (list == null)
{
    list = new ListNode(student, null);
}
else
{
    while (tail.getNext() != null)
    {
        tail = tail.getNext();
    }
    tail = new ListNode(student, null);
}
```

II.

```java
while (tail != null && tail.getNext() != null)
{
    tail = tail.getNext();
    if (tail == null)
        list = new ListNode(student, null);
}
else
    tail.setNext(new ListNode(student, null));
```

III.

```java
ListNode newNode = new ListNode(student, null);
if (tail == null)
{
    while (tail.getNext() != null)
    {
        tail = tail.getNext();
    }
    tail.setNext(newNode);
}
else
    list = newNode;
```

- (A) 仅 I
- (B) 仅 II
- (C) I 和 II
- (D) II 和 III
- (E) I、II 和 III

对于典型的单选题来说，这些代码太长了，但它给了我们回顾一些常见错误的机会。

片段 I 看起来可能很直观，但最后一条语句有一个错误：它将局部变量 `tail` 设置为新节点，而不是通过调用 `tail.setNext(new ListNode(student, null))` 将 `tail` 的下一个链接中的 `null` 替换为新节点。

## 片段 II 中的条件

```java
tail != null && tail.getNext() != null
```

起看起来很可疑，但由于短路求值，它是有效的。如果 `studentList` 在开始时为空，则 `tail` 为 `null` 并执行 `while` 循环。否则，`tail` 会不断移动，直到指向列表的最后一个节点。接下来的 `if-else` 语句正确地将 `tail` 的下一个或 `studentList` 设置为新节点。因此，片段 II 是可以工作的。

片段 III 采用了分步的方法：它先分配一个新节点，然后将其附加到列表中。它是有效的，也许这种方法实际上更简洁。答案是 D。

片段 III 的分步方法可能对回答简答题有所帮助。每个完成的步骤通常都会得分，即使你不知道其余部分，你可能也可以为某些步骤（如分配节点）编写代码。

## 6.3 ~ 栈和队列

### 栈（Stacks）

栈是一种实现后进先出（LIFO）存储方法的存储结构。栈由两个操作控制：`push` 将项目置于栈顶，`pop` 移除并返回栈顶项目。栈用于理顺层级嵌套结构和分支过程。

# 第 6 章 126 页 ~ AP 主题：链表、栈、队列、树等

来自 `java.util` 包的 `Stack<E>` 类实现了栈的功能。（按照惯例，`E` 代表存储在栈上的对象类型，例如 `Stack<String>`。）该类有一个无参构造函数，可以创建一个空栈。AP 子集包含了 `Stack<E>` 的以下方法：

```java
boolean isEmpty(); // 如果此栈为空则返回 true

push(E x); // 将 x 添加到此栈的顶部

pop(); // 移除并返回栈顶项目

peek(); // 返回栈顶项目而不将其从栈中移除
```

![](img/e320d34bf6b289b099c4a1d8b2b5ab9c_139_0.png)

以下代码段的输出结果是什么？

```java
Stack<Integer> s1 = new Stack<Integer>();

s1.push(new Integer(1));
s1.push(new Integer(2));

Stack<Integer> s2 = new Stack<Integer>();

s2.push(new Integer(3));
s2.push(new Integer(4));
s2.push(new Integer(5));

Stack<Integer> s3 = new Stack<Integer>();

while (!s1.isEmpty() && !s2.isEmpty()) {
    s3.push(s1.pop());
    s3.push(s2.pop());
}

while (!s3.isEmpty()) {
    System.out.print(s3.pop() + " ");
}
```

- (A) 4 2 3 1
- (B) 2 5 1 4
- (C) 4 1 5 2
- (D) 5 2 4 1 3
- (E) 2 3 1 4 5

这个问题并不像看起来那么困难。`s1` 顶部是 2，所以 2 先被推入 `s3` 并最终位于 `s3` 的底部。因此，2 将是最后一个打印的数字。答案是 C。

### 队列（Queues）

队列是一种实现先入先出（FIFO）存储方法的存储结构。队列由两个操作控制：`add` 将项目添加到队列尾，`remove` 移除并返回队列前面的项目。队列用于按照到达顺序处理事件。

Java 5.0 的 `java.util` 包拥有接口 `Queue<E>`，其在 AP 子集中包含以下方法：

```java
boolean isEmpty(); // 如果此队列为空则返回 true；否则返回 false

boolean add(E x); // 将 x 添加到此队列；返回 true

E remove(); // 移除并返回队列中的第一个项目

E peek(); // 返回第一个项目而不从队列中移除
```

注意 `java.util` 包中的一个不一致之处：`Stack<E>` 是一个类而 `Queue<E>` 是一个接口。编写以下代码是错误的：

```java
Queue<String> q = new Queue<String>(); // 语法错误
```

因为你不能实例化接口。实现 `Queue<E>` 接口的 `java.util` 类之一是 `LinkedList<E>`。例如，你可以写：

```java
Queue<String> q = new LinkedList<String>();
```

这条语句表示我们打算使用新构建的列表作为队列。`LinkedList` 中的 `add` 方法的作用相当于 `addLast`。`remove` 方法的作用相当于 `removeFirst()`，而 `peek` 方法的作用类似于 `getFirst`。

考虑以下方法：

```java
public void parse(String expr) {
    Stack<Integer> stk = new Stack<Integer>();
    Queue<String> q = new LinkedList<String>();

    for (int k = 0; k < expr.length(); k++) {
        String kth = expr.substring(k, k + 1);

        if (kth.equals("(")) {
            stk.push(k);
        } else if (kth.equals(")")) {
            if (stk.isEmpty()) {
                System.out.println("**** error ****");
                return;
            }

            int j = ((Integer) stk.pop()).intValue();
            q.add(expr.substring(j + 1, k));
        }
    }

    if (!stk.isEmpty()) {
        System.out.println("**** error ****");
    } else {
        while (!q.isEmpty()) {
            System.out.println(q.remove());
        }
    }
}
```



调用`parse("Consider ((a+b))")`的输出是什么？

- (A) `a+b`
- (B) `Consider ((a+b))`
- (C) `(a+b)`
- (D) Syntax error

这个例子比典型的单选题要长，但它允许我们在更真实的设置下回顾栈和队列。在这个方法中，栈用于理顺带括号的表达式，队列用于存储子表达式。一旦发现左括号，就会将其位置保存在栈中；当发现右括号时，从栈中弹出并将之间的字符串添加到队列。使用栈确保了左右括号是匹配的对。结束时栈必须为空；否则将报告语法错误。

在这个例子中，`expr`是`"Consider ((a+b))"`。括号匹配，所以 E 不是正确答案。有四对匹配的括号，所以 D 不是正确答案。输出必须包含四行，如 A 和 C。内部表达式更接近栈顶，因此它们会被先入并打印。答案是 A。

## 6.4 Sets 和 Maps

### `java.util.Set<E>`

从 Java 5.0 开始，`Set`存储指定数据类型的对象。在 Java 5.0 规范中，字母`E`用作集合中元素的占位符。`E`可以是任何定义的类。`java.util.Set<E>`接口在 AP 子集中的方法有：

```java
int size();

// 返回集合中的元素数量

boolean add(E x);

// 将 x 添加到集合

boolean contains(E x);

// 如果集合包含 x 则返回 true

boolean remove(E x);

// 从集合中移除 x

// 返回此集合的 Iterator
```

严格来说，`Set<E>`的`contains`和`remove`方法中的参数在 Java API 中被指定为`Object`而不是`E`。我们认为这不幸且具有危险，因为如果调用的参数不是`E`的实例，这些方法对`TreeSet`会抛出`ClassCastException`。这就是为什么我们使用`E`而不是`Object`。

> 集合的元素没有索引。由迭代器返回的`Iterator`根据特定实现的顺序遍历元素。

数学集合包含唯一的值。然而，在 Java 中什么是“唯一”（不相等）的值并不是一个简单的问题：它取决于具体的实现。`java.util`提供了两个实现`Set<E>`的类：使用二叉树的`TreeSet<E>`和使用哈希表的`HashSet<E>`。这些数据结构将在 6.5 和 6.6 中详细讨论。

通常，放入`TreeSet`的对象被假设是`Comparable`的，`TreeSet`使用它们的`compareTo`方法进行比较（除非向`TreeSet`的构造函数提供比较器，这不在 AP 子集范围内）。如果`x.compareTo(y)`返回 0，则`x`被认为与`y`“相等”。

- 迭代器按升序返回`TreeSet`的值。

`HashSet`不假设其元素是`Comparable`的；它使用`hashCode`方法和`equals`方法来判断两个对象是否相等。因此，放入`HashSet`的对象需要可用的`hashCode`方法。

- 迭代器以任意顺序返回`HashSet`的值。

### `java.util.Map<K,V>`

`Map`存储对象对：`(key, value)`并建立了键与键关联的值之间的关系。键形成一个集合，因此它们都是不同的。每个键只关联一个值。然而，不同的键可以映射到相同的值。当我们知道键时，Map 提供了一种查找值的方便方法。例如，电话公司的客户数据库可能会以电话号码为键在 Map 中保留记录。

## 6.4 集合与映射（Maps）

从 Java 5.0 开始，`Map<K, V>`存储了指定数据类型的对象对。在 Java 5.0 API 规范中，字母 K 和 V 分别用作键（key）和值（value）数据类型的占位符。K 和 V 可以是任何定义类的名称。API 子集中的`java.util.Map<K, V>`接口方法：

```java
int size();                          // 返回键的数量

V put(K key, V value);               // 在 map 中
                                     // 将值与键关联
                                     // （返回与键关联的旧值，
                                     // 如果键不在 map 中，则返回 null）

V get(K key);                        // 返回与键关联的
                                     // 值，如果键不在
                                     // map 中则返回 null

boolean containsKey(K key);          // 如果键在键集
                                     // 中则返回 true

V remove(K key);                     // 从 map 中删除；返回
                                     // 之前与键关联的
                                     // 值，或 null

Set<K> keySet();                     // 返回所有键的集合
```

对于集合（Sets），`Map<K, V>`中`get`、`containsKey`和`remove`方法的参数在 Java API 中被指定为`Object`，而不是 K。这种设计是不一致的（与`put`相比）且具有潜在危险的，因为如果用 K 实例以外的参数进行调用，这些方法会导致`TreeMap`抛出`ClassCastException`。

`java.util`提供了两个实现`Map<K, V>`的类：`TreeMap<K, V>`（它使用二叉搜索树作为键）和`HashMap<K, V>`（它使用哈希表作为键）。

要遍历 map，你需要获取所有键的集合并遍历该集合。例如：

```java
Map<Integer, String> map = new TreeMap<Integer, String>();

map.put(..);

...

for (Integer key : map.keySet()) {
    System.out.println(key + " => " + map.get(key));
}
```

或者，使用迭代器（iterator）：

```java
Map<Integer, String> map = new TreeMap<Integer, String>();

map.put(..);

...

Iterator<Integer> it = map.keySet().iterator();

while (it.hasNext()) {
    Integer key = it.next();
    System.out.println(key + " => " + map.get(key));
}
```

课程选课数据库存储了学生在特定学期选课的信息。它必须能够快速执行两项任务：确定特定学生是否注册了某门课程，以及生成该课程所有学生的列表。以下哪种数据组织方法最适合这些任务？

- (A) 使用学生作为键、与键关联的某个值的 map
- (B) 使用课程作为键、与键关联的某个作为值的 map
- (C) 一个布尔值二维数组，行对应课程，列对应学生；如果课程和学生交点处的元素代表该学生正在修读该课程，则设置为 true
- (D) 使用课程作为键的 map；与键关联的值是修读该课程的所有学生的集合
- (E) 使用学生作为键的 map；与键关联的值是所有修读该学生的列表

注意集合和列表在 Java 中是对象，因此选项 D 和 E 是完全可能的。一个学生可以修多门课程，多个学生可以修同一门课程，因此 A 和 B 的映射行不通。C 中的表格方法如果保持学生排序并使用二分查找来找到恰当的行和列，则可能是行的。尽管如此，如果使用非 K 实例的参数调用，这些方法可能会导致`TreeMap`的`ClassCastException`。

## 二叉树

考虑以下`isEqual`方法的不完整实现，该方法用于比较两棵树：

```java
// 如果 root1 和 root2 指向的树具有相同的形状
// 且对应的节点包含相同的信息，则返回 true；
// 否则，返回 false

public boolean isEqual(TreeNode root1, TreeNode root2)
{
    if (root1 == null && root2 == null) {
        return true;
    } else if (root1 == null || root2 == null) {
        return false;
    } else {
        return < expression >;
    }
}
```

考虑以下`<expression>`的两种替换方案：

1. “前序”：

```java
root1.getValue().equals(root2.getValue()) &&
isEqual(root1.getLeft(), root2.getLeft()) &&
isEqual(root1.getRight(), root2.getRight())
```

2. “后序”：

```java
isEqual(root1.getLeft(), root2.getLeft()) &&
isEqual(root1.getRight(), root2.getRight()) &&
root1.getValue().equals(root2.getValue())
```

假设`root1`和`root2`指向以下树：

```text
root1               root2

    Atlanta             Atlanta

    /    \               /    \

Boston Cincinnati     Cincinnati

    /    \             /

Denver Zapata         Denver

                    Zapata
```

当调用`isEqual(root1, root2)`时，在这两种实现中`String`的`equals`将执行多少次？

| 前序 | 后序 |
| --- | --- |
| (A) 1 | 0 |
| (B) 3 | 2 |
| (C) 3 | 1 |
| (D) 4 | 1 |
| (E) 4 | 4 |

这不是一个简单的问题，因为你必须用正确的方法来处理。你还需要考虑短路求值。前序实现会比较对应位置的所有节点，从根节点开始，然后是左子树和右子树；只要可能就一直比较。因此，它会验证“Atlanta”、“Boston”、“Cincinnati”和“Denver”的匹配。这消除了 A、B 和 C。在后序子实现中，我们只比较左、右子树匹配的对应位置的节点。这里只有一个这样的节点“Boston”（一个叶子节点）。答案是 D。

考虑以下方法的不完整实现：

```java
// 返回一个包含两个元素的数组：info[0] 设置为树中
// 所有匹配 target 的节点总数；info[1] 设置为
// 从根节点到这些节点的路径长度之和
// 前置条件：root 指向二叉树的根节点

public int[] totalPaths(TreeNode root, Object target)

int[] info = new int[2]; // 默认情况下 info[0] = 0; info[1] = 0;

if (root != null) {
    int[] infoLeft = totalPaths(root.getLeft(), target);
    int[] infoRight = totalPaths(root.getRight(), target);

    int count, pathsSum;

    // 缺失的代码

    info[0] = count;
    info[1] = pathsSum;
    return info;
}
```

以下哪个代码段可以完成该方法使其按指定工作？

### 片段 I

```java
count = infoLeft[0] + infoRight[0];

if (root.getValue().equals(target))
{
    count++;
}

pathsSum = infoLeft[1] + infoRight[1] + 2;
```

### 片段 II

```java
count = infoLeft[0] + infoRight[0];

if (root.getValue().equals(target))
{
    count++;
}

pathsSum = infoLeft[1] + infoLeft[0] + infoRight[0];
```

### 片段 III

```java
count = 0;

pathsSum = 0;

if (infoLeft[0] > 0)
{
    count += infoLeft[0];

    pathsSum += (infoLeft[1] + infoLeft[0]);
}

if (infoRight[0] > 0)
{
    count += infoRight[0];

    pathsSum += (infoRight[1] + infoRight[0]);
}

if (root.getValue().equals(target))
{
    count++;
}
```

- (A) 仅 I
- (B) 仅 II
- (C) 仅 III
- (D) I 和 II
- (E) II 和 III

> 你可能会被要求在考试的简答题编写类似`totalPaths`方法。

在此方法中，递归步骤返回的值必须经过调整以适应顶层。我们找到了从根节点的左孩子开始的所有路径的长度和，但现在这些路径必须扩展到根节点。因此，我们需要将每条路径的长度加 1，可以通过将匹配节点数`infoLeft[0]`加到路径总长度`infoLeft[1]`中来实现。我们对右子树执行同样的操作。因此：

```java
pathsSum = infoLeft[1] + infoLeft[0] + infoRight[1] + infoRight[0];
```

片段 I 应该被拒绝，因为它无论子树中是否找到不匹配节点，都会为`pathsSum`增加 2；它失败了。片段 II 和 III 在`info[0]`为 0 时是有效的。因此，答案是 E。

为了解决冲突，`HashSet`和`HashMap`依赖于`equals`方法。（回想一下`TreeSet`依赖于`compareTo`方法。）为了让`HashSet`和`TreeSet`能够一致地处理其元素，`compareTo`、`equals`和`hashCode`这三个方法必须相互一致：

```java
x.compareTo(y) == 0 当且当仅当 x.equals(y) == true;

如果 x.equals(y)，则 x.hashCode() == y.hashCode()
```



类`SSN`有一个数据字段`String ssn`，表示一个九位安全数字的字符串。方法`getDigit(k)`返回该数字的第`k`位十进制数字，返回值为`int`。以下哪个代码作为`SSN hashCode`方法最合适？

- (A) `return ssn.hashCode();`
- (B) `return 100 * ssn.hashCode();`
- (C) `Random gen = new Random(); return gen.nextInt(1000) * ssn.hashCode();`
- (D) `int sum = 0; for (int i = 0; i < ssn.length(); i++) { sum += getDigit(i); } return sum;`
- (E) `int sum = 0; Random gen = new Random(); for (int i = 0; i < ssn.length(); i++) { sum += gen.nextInt(100) * getDigit(i); } return sum;`

一个`hashCode`方法似乎对对象执行某些“随机”操作，但在计算中使用随机数是一个坏主意，因为该方法必须是可预测的：它对同一个对象必须始终返回相同的结果。选项`C`和`E`测试了你对这一点的理解。选项`B`产生的哈希码太稀疏：它们可能只落在`100`的倍数上。在`D`中，所有可能结果的范围从`0`到`81`——不足以相信编写`String`类的专家知道自己在做什么。答案是`A`。

## 6.7. 优先级队列、堆和堆排序

优先级队列是一种存储结构，允许你根据项目的优先级或排序来检索项目。优先级队列由两个操作控制：*add*（添加）一个项目和 *remove*（移除并返回优先级最高的项目）。优先级队列用于按优先级处理事件（消息、订单）。优先级队列可以包含多个相同优先级的项目。

`java.util.PriorityQueue<E>`类实现了`Queue<E>`接口，因此添加和检索值的方法名称与普通队列相同：

```
boolean isNotEmpty();          // 如果队列为空返回 true；否则返回 false
boolean add(E x);              // 将 x 添加到队列中；如果成功则返回 true
E remove();                    // 移除并返回第一个（即优先级最高的）项目
E peek();                      // 返回优先级最高的项目，但不从队列中移除
```

> 然而，从优先级队列中检索值的顺序不是按照它们的到达顺序，而是按照它们的优先级顺序。

`PriorityQueue<E>`类假设优先级队列持有`Comparable<E>`对象（否则，必须向构造函数提供一个比较器作为参数——这在`AP`子集中未包含）。按照约定，优先级值是最小的。如果两个值具有相同的优先级，则任意打破平局。

`PriorityQueue<E>`类将优先级队列实现为堆。

- 堆是一个具有两个额外属性的二叉树：
  1. 完全性——除了最底层外，每一层都满了节点。最后一层在右侧可能缺少节点。
  2. 排序——每个节点都小于或等于其左、右子树中的所有节点。

例如：

![堆示例](img/e320d34bf6b289b099c4a1d8b2b5ab9c_157_0.png)

在堆中找到最小节点很容易——它位于根节点。

完全性属性允许我们将堆存储在数组中。节点只需按照从上到下、从左到右扫描所有层的顺序存储。在`Java`实现中，让数组的第一个元素未使用非常方便，因为在处理堆的算法中，将堆的根放在索引为`1`的数组元素中更容易操作。例如，上面的树可以存储为：

```
<empty> A D E X L R
```

在这种方案中，`a[1]`是根节点。如果`a[i]`是一个节点，其父节点在`a[i/2]`中找到，其左、右孩子在`a[2*i]`和`a[2*i+1]`中找到。在堆实现中，`remove`移除根并返回其值。通过移动叶子节点（即最右侧节点）到根部来修复堆。（注：此处文本似乎有重复，遵循逻辑流）。

## 6.8. Big-O 分析

在之前的章节中，我们多次提到“比较次数大约与`n²`成正比”或“运行时间大致与`log n`成正比”。“大约”或“大致”到底意味着什么？`Big-O`为增长阶的概念提供了一个正式的定义和符号。

准确的“`Big-O`”定义可以在许多书中找到。这里我们只给出一个实用的规则：

> 如果我们有两个函数`f(n)`和`g(n)`，并且当`n`无限增大时，比例`f(n)/g(n)`趋于一个正系数，那么我们可以说`f`和`g`具有相同的增长阶，我们可以写道：

```
f(n) = O(g(n))
```

增长阶定义忽略常数因子：对于常数`k > 0`，`f(n) = O(k * f(n))`。

在算法分析中，整数`n`定义了任务的大小：要排序元素的数量；列表或集合中的节点数等。算法的时间空间需求可以用`O(f(n))`表示。我们使用标准的参考函数来比较它们的增长率。常见的参考函数有：

| (常数) | `n log n` | (`n log n`) |
| --- | --- | --- |
| `log n` (对数) | `n²` (二次) | |
| `n` (线性) | | |

如果`f(n)`是次数为`k`的多项式，那么`f(n) = O(n^k)`。

例如：

```
(n-1) = n²/2 - n/2 = O(n²)
```

我们通常关注的是运行时间。表`6-2`显示了之前讨论过的某些常用算法的`Big-Oh`要求。该表假设算法是以优化方式实现的，并允许平均`Big-Oh`性能。可能存在`Big-Oh`不同的最好情况和最坏情况。表`6-3`显示了常用算法的平均、最好情况和最坏情况。最坏情况假设算法运行在处理时间最长的数据集上。

还有一些经验法则，你必须谨慎使用它们。

- 如果一个算法使用单循环，它要么是对于简单的顺序处理的`O(n)`，要么是对于分治法的`O(log n)`。
- 如果一个算法使用嵌套循环，它要么是对于正方形进行简单顺序迭代的`O(n²)`，要么是带有分治组件的算法的`O(n log n)`。`AP`课程中专门命名的“`n log n`”算法只有归并排序（`Mergesort`）、快速排序（`Quicksort`）和堆排序（`Heapsort`）。

| Big-Oh | 算法 |
| :--- | :--- |
| `O(1)` — “常数” | - 在数组末尾添加元素<br>- 在链表头部或双向链表尾部添加节点<br>- 栈的推弹出操作<br>- 队列的添加和删除操作<br>- 哈希表中的检索/插入 |
| `O(log n)` — “对数级” | - 排序数组中的二分查找<br>- 二叉搜索树中的查找和插入<br>- 堆中的检索/插入 |
| `O(n)` — “线性” | - 数组中的顺序查找<br>- 具有`n`个节点的列表或树的遍历<br>- 计算`n`个元素的和或乘积 |
| `O(n log n)` — “n-log-n” | - 归并排序<br>- 快速排序<br>- 堆排序 |
| `O(n²)` — “二次方” | - 选择排序和插入排序<br>- `n × n`二维数组的遍历<br>- 采用“三角形”嵌套循环的算法 |

表`6-2` 常用算法的`Big-Oh`示例

| 最好情况 | 平均情况 | 最坏情况 |
| :--- | :--- | :--- |
| 顺序查找 | `O(1)` — 立即找到 | `O(n)` — 在中间找到 | `O(n)` |
| 二分查找 | `O(1)` — 立即找到 | `O(log n)` | `O(log n)` |
| 哈希表查找 | `O(1)` — 立即找到 | `O(1)` — 小且固定长度的桶 | `O(n)` — 所有值都集中在少数桶中 |
| 二叉搜索树查找 | `O(1)` — 立即找到 | `O(log n)` | `O(n)` — 树退化为近似列表 |
| 选择排序 | `O(n²)` | `O(n²)` | `O(n²)` |
| 插入排序 | `O(n)` — 数组已排序 | `O(n²)` | `O(n²)` |
| 归并排序 | `O(n)` — 数组已排序时的优化版本 | `O(n log n)` | `O(n log n)` |
| 快速排序 | `O(n log n)` | `O(n log n)` | `O(n²)` — 基准始终选择在远离中位数的地方，因为数组已排序且选择第一个元素作为基准 |
| 堆排序 | `O(n log n)` | `O(n log n)` | `O(n log n)` |
| 向堆中插入值 | `O(1)` — 该值是堆中最大的 | `O(log n)` | `O(log n)` |

表`6-3` 最好、平均和最坏情况`Big-Oh`

以下方法消除了链表中的连续重复节点。例如，`A→B→B→A`变成`A→B→C→A`。

```java
public void skipDuplicates(ListNode head) {
    ListNode p = head;
    ListNode p2;
    while (p != null) {
        p2 = p.getNext();
        while (p2 != null && p2.getValue().equals(p.getValue())) {
            p2 = p2.getNext();
        }
        p.setNext(p2);
        p = p.getNext();
    }
}
```

对于具有`n`个节点的列表，以下哪项最好描述了`skipDuplicates`的最好情况和最坏情况运行时间？

| 最坏情况 | 最好情况 |
| --- | --- |
| (A) | `O(1)`  `O(n)` |
| (B) | `O(n)`  `O(n)` |
| (C) | `O(1)`  `O(n²)` |
| (D) | `O(n)`  `O(n²)` |
| (E) | `O(n²)`  `O(n²)` |

> **答案：B.**
> 无论“最好情况”如何，该方法都要检查列表的每个节点。运行时间不可能是常数；因此`A`和`C`是错误的。当所有节点都不同时，存在一种情况，在这种情况下，内部循环不会跳过，我们得到对列表的简单遍历。该情况下的运行时间是`O(n)`，所以`E`不是正确答案。我们剩下`B`和`D`。当所有节点都相同时，每个节点只被访问一次。经验法是：它有嵌套循环，所以你可能认为最坏情况是`O(n²)`。但该方法消除了连续重复值，而不是所有的重复值。技巧是：外部循环并不一定跳转到下一个节点，而是可以跳过所有重复节点。当所有节点都相同时，每个节点只被访问一次。我们警告过要谨慎使用经验法则，不是吗？答案是`B`。

# 第 7 章 GridWorld 案例研究

## 7.1 引言

`GridWorld`案例研究是专为`AP`计算机科学课程开发的教学工具。过去，考试有六道多选题和一道开放简答题。

该案例研究涉及一个在二维网格中操作各种“生物”的大型程序。案例研究材料包含（40页）。

## 7.2. Location 类与 Grid 接口

### Location

`Location`对象代表二维网格上的一个`(row, col)`位置（使用整数坐标）。

`Location`类有一个构造函数：

```java
public Location(int row, int col)
```

以及两个访问器方法：

```java
public int getRow()              // 返回此位置的行
public int getCol()              // 返回此位置的列
```

> `Location`对象是不可变的：一旦创建，`Location`对象就无法更改。

`Location`实现了`Comparable`接口，并提供了一个`compareTo`方法，该方法按行比较位置，如果相等，则按列比较。`Location`还重写了`Object`的`equals`方法，其方式与`compareTo`保持一致。[它与`hashCode`方法也保持一致]

`Location`的`toString`将位置转换为字符串：

```java
public String toString() 
{
    return "" + getRow() + ", " + getCol() + "";
}
```

`Location`类有助于处理网格上的方向。它定义了八个公共常量：

```java
public static final int NORTH = 0;
public static final int NORTHEAST = 45;
public static final int EAST = 90;
public static final int SOUTHEAST = 135;
public static final int SOUTH = 180;
public static final int SOUTHWEST = 225;
public static final int WEST = 270;
public static final int NORTHWEST = 315;
```

代表指南针方向（以度表示）。

行号从北向南增加。列号从西向东增加。

另外七个常量表示转向：

```java
public static final int LEFT = -90;
public static final int RIGHT = 90;
public static final int HALF_LEFT = -45;
public static final int HALF_RIGHT = 45;
public static final int FULL_CIRCLE = 360;
public static final int HALF_CIRCLE = 180;
public static final int AHEAD = 0;
```

在代码中，使用数字（`-360`, `180`, `0`等）可能比使用`Location.FULL_CIRCLE`, `Location.HALF_CIRCLE`, `Location.AHEAD`更容易。

`Location`的`getLocation(int dir)`返回在指南针方向上与此位置相邻的位置。角触碰的位置被认为是相邻的。

`Location`的`getDirectionToward(Location other)`方法返回从此位置到另一个位置的指南针方向（度表示）。例如：

```java
Location loc1 = new Location(3, 7);
Location loc2 = loc1.getAdjacent(Location.SOUTHWEST);
int dir = loc1.getDirectionToward(loc2);
```

将`loc2`设置为`(4, 6)`，并将`dir`设置为`225`（即`Location.SOUTHWEST`）。

### Grid

`Grid<E>`接口表示一个可以存放类型为`E`的对象的二维网格。`GridWorld`使用`Grid<Actor>`来持有是`Actor`的对象（即`Actor`类或`Actor`的任何子类或后代类的对象）。

> 在`GridWorld`中，网格中的给定位置只能居住一个`actor`。

该接口将网格的具体实现与`GridWorld`的其他类隔离开来。

一个网格可以实现为二维数组（如`BoundedGrid`所示），但也可以通过其他方式实现。「只有`AB`考试涉及`Grid`的具体实现。」

`Grid<E>`接口如图`7-3`所示。它有十一个方法，大致分为两类：“通用”网格方法和“局部邻域”方法。



`public interface Grid<E>` 定义了通用网格的接口，包含以下方法：

- 通用网格方法：
  - `int numRows()`：返回边界网格的行数；无界网格返回 -1。
  - `int numCols()`：返回边界网格的列数；无界网格返回 -1。
  - `boolean isValid(Location loc)`：如果 `loc` 在此网格中有效则返回 true（无界网格中始终为 true）。
  - `E get(Location loc)`：返回 `loc` 处的对象，如果 `loc` 为空则返回 null。
  - `E put(Location loc, E obj)`：将 `obj` 置于 `loc` 并返回 `loc` 原先的对象（如果 `loc` 为空则返回 null）。
  - `E remove(Location loc)`：移除 `loc` 处的对象并返回该对象（如果 `loc` 为空则返回 null）。
  - `ArrayList<Location> getOccupiedLocations()`：返回网格中所有被占据的位置列表。

- “局部邻域”方法：
  - `ArrayList<Location> getValidAdjacentLocations(Location loc)`：返回与 `loc` 相邻的所有有效位置列表。
  - `ArrayList<Location> getEmptyAdjacentLocations(Location loc)`：返回与 `loc` 相邻的所有有效空位置列表。
  - `ArrayList<Location> getOccupiedAdjacentLocations(Location loc)`：返回与 `loc` 相邻的所有被占据位置列表。
  - `ArrayList<E> getNeighbors(Location loc)`：返回 `loc` 相邻位置的所有对象列表。

图 7-3. `Grid<E>` 接口。

### GRID 研究

除了 `isValid` 外，所有以 `Location` 为参数的 `Grid<E>` 方法都假设 `loc` 是网格中的有效位置。`put` 方法还假设 `obj` 不为空。考虑以下方法：

```
public boolean areNeighbors(Grid<E> grid, Location loc1, Location loc2) {
    // 如果 loc1 和 loc2 在 grid 中是邻居则返回 true，
    // 否则返回 false。
    return expression;
}
```

以下哪些替换项可以使该方法正常工作？

I. `loc1.getAdjacent(loc2) == loc2`

II. `loc1.getDirectionToward(loc2).equals(loc2)`

III. `grid.getNeighbors(loc1).contains(loc2)`

(A) 仅 I

(B) 仅 II

(C) 仅 III

(D) I 和 II

I 和 II 的思路是先获取 `loc1` 到 `loc2` 的方向，然后创建...

## 7.3. Actor 类

`Actor` 类作为不同类型“昆虫”、“花”、“石头”、“生物”等类的基类。`Actor` 不是抽象类，你可以创建该类的对象。然而，类型为 `Actor` 的对象并不有趣：当被要求执行时，它只是旋转 180 度。

`Actor` 对象有四个属性：颜色、位置、方向和网格。

actor 一时属于一个网格；其 `grid` 属性指向该网格，如果不在任何网格中则为 null。

`Actor` 类有一个无参数的构造函数。该构造函数将 actor 的颜色设置为 `Color.BLUE`，将方向设置为 0 (`Location.NORTH`)，并将位置和网格设置为 null。

`Actor` 类拥有这些属性的四个访问器和两个修改器：

```
public Color getColor()
public Location getLocation()
public int getDirection()
public Grid<Actor> getGrid()
```

```
public void setColor(Color newColor)
public void setColor(int newDirection)
```

它还有一个 `toString` 方法：

```
public String toString()
```

不直接设置 `grid`。而是使用 `putInGrid` 和 `removeFromGrid` 方法，因为网格和 actor 都必须通知更改：

```
public void putInGrid(Grid<Actor> gr, Location loc)
// 将此 actor 置于 grid 的 loc 处。
// 前提：actor 不在 grid 中；
// loc 是 grid 中的有效位置。
```

```
public void removeFromGrid()
// 将此 actor 从其网格中移除。
// 前提：actor 在一个网格中。
```

`Actor` 的 `moveTo` 方法：

```
public void moveTo(Location newLocation)
```

# 160 第 7 章 ~ 网格世界案例研究

- 将 actor 的当前位置设置为 `loc`，但它功能更多：它首先会从 `loc` 移除当前的占用者（如果有的话）。

最后，actor 拥有 `act` 方法。`Actor` 的 `act` 方法执行某些操作是为了显示某些动作：它将 actor 旋转 180 度。

> `Actor` 的 `act` 方法通常在 `Actor` 的子类中重写。

63

假设新位置是空的，以下哪个代码段将使 `Actor` 向南移动一个单位？

I. `Location loc = andy.getLocation();`

`loc.setRow(loc.getRow() + 1);`

II. `loc = andy.getLocation();`

`Location newLoc = new Location(loc.getRow() + 1, loc.getCol());`

`andy.moveTo(newLoc);`

III. `loc = andy.getLocation();`

`andy.moveTo(loc.getAdjacentLocation(Location.SOUTH));`

(A) 仅 I

(B) 仅 II

(C) 仅 III

(D) I 和 II

(E) II 和 III

选项 I 是没有意义的，因为 `Location` 对象是不可变的；`Location` 没有 `setTo` 方法。当 actor 在网格中改变位置时，它必须通知网格发生了这一变化，并可能移除新位置的当前占用者。为了强调这一点，对应的方法是 `moveTo` 而不是 `setLocation`。以下语句

```
Location newLoc = new Location(loc.getRow() + 1, loc.getCol());
andy.moveTo(newLoc);
```

有效，但

```
andy.moveTo(loc.getAdjacentLocation(Location.SOUTH));
```

更好，因为它更抽象：它不依赖于网格中指南针方向到行和列的知识。答案是 C。

# 7.3~Actor 类 161

64

假设类 `Checker` 定义如下：

```
public class Checker extends Actor {
    public Checker (Color color) {
        setColor(color);
    }
}
```

另一个类 `CheckerBoard` 实现了 `Grid<Actor>`。考虑第三个类 `CheckersGame` 中的以下方法：

```
// 如果棋子可以在 dir 方向上“跳过”一个
// 反颜色的棋子，则执行跳跃并返回 true；否则返回 false。
public boolean jump(int dir, Location loc, int dir) {
    if (dir % 4 != 0 || dir % 90 == 0) // 只允许对角线跳转
        return false;
    if (!board.isValid(loc))
        return false;
    Location loc2 = loc.getAdjacentLocation(dir);
    if (!board.isValid(loc2) || board.get(loc2) == null)
        return false;
    Location loc3 = loc2.getAdjacentLocation(dir);
    if (!board.isValid(loc3) || board.get(loc3) != null)
        return false;
    Checker chk = (Checker)board.get(loc);
    Checker chk2 = (Checker)board.get(loc2);
    if (chk.getColor().equals(chk2.getColor()))
        return false;
    // loc2 被反颜色的棋子占据；
    // loc3 是空的；
    // chk 从 loc 移动到 loc3；loc2 被清空：
    // <缺失的语句>
    return true;
}
```

以下哪个替换 `<缺失的语句>` 的选项将使此方法按预期工作？

# 162 第 7 章 ~ 网格世界案例研究

(A) `chk.moveTo(loc3);`

(B) `board.remove(loc);`

`chk.moveTo(loc3);`

`board.remove(loc2);`

(C) `chk.moveTo(loc3);`

`board.remove(loc2);`

(D) `chk.moveTo(loc3);`

`chk2.removeSelfFromGrid();`

(E) `board.remove(loc2);`

`board.remove(loc);`

`Checker chk3 = new Checker(chk.getColor());`

`board.put(loc3, chk3);`

这个问题对于一个典型的多选择考试题来说有点长了。我们在这里使用它是为了练习 GridWorld 类型代码以及使用低级 GridWorld 类。我们可以用它来展示 GridWorld 设置的通用性和可重用性：编写一个跳棋游戏。

选项 A 和 D 尝试将 `chk` 从 `loc` 移动到 `loc3`，而选项 E 尝试移除 `chk` 并在 `loc3` 创建一个相同的对象。后者可能可行，但它不符合 GridWorld 的精神，而且你需要使用 `chk.removeSelfFromGrid(...)` 和 `chk.putSelfInGrid(...)`。

选项 A 忘记从 `loc2` 移除棋子。在选项 B 中，在 `board.remove(loc)` 之后 `moveTo` 会抛出异常，`chk` 不在网格中了。选项 C 错误地使用了 `board` 的 `remove` 方法，而不是 `chk.removeSelfFromGrid()`。选项 E 有相同的问题：它使用了 `board` 的 `put` 和 `remove`。答案是 D。

> 永远不应该直接使用 `Grid` 的 `put` 和 `remove` 方法——而应该使用 `Actor` 的 `putSelfInGrid` 和 `removeSelfFromGrid`。

否则，actor 将不知道它被放入了网格中。

# 7.4. 虫子、花和石头

`Bug`、`Flower` 和 `Rock` 类是 `Actor` 的子类。

`Rock` 是三者中最简单的。它有两个构造函数：无参数构造函数创建一个岩石，`Rock(Color)` 构造函数创建一个给定颜色的岩石。`Flower` 类与 `Rock` 类似，但它的默认颜色是粉红色。`Bug` 类更有趣，它有三个方法：`canMove`、`move` 和 `turn`。

`Bug` 的 `act` 方法如下：

```
public void act() {
    if (canMove()) {
        move();
    } else {
        turn();
    }
}
```

`Bug` 在位置有效且为空时尝试向前移动：

```
public boolean canMove() {
    Grid<Actor> gr = getGrid();
    if (gr == null)
        return false;
    Location loc = getLocation();
    Location next = loc.getAdjacentLocation(Location.SOUTH);
    if (gr.isValid(next) && gr.get(next) == null)
        return true;
    return false;
}
```

此方法使用 `instanceof` 运算符来检查邻居是否为花朵：

```
public boolean canMove() {
    Grid<Actor> gr = getGrid();
    if (gr == null)
        return false;
    Location loc = getLocation();
    Location next = loc.getAdjacentLocation(Location.SOUTH);
    if (gr.isValid(next)) {
        Actor neighbor = gr.get(next);
        if (neighbor instanceof Flower)
            return true;
    }
    return false;
}
```

# 164 第 7 章 ~ 网格世界案例研究

`move` 方法移动此 `Bug` 并在位置放置一朵花：

```
public void move() {
    Grid<Actor> gr = getGrid();
    if (gr == null)
        return;

    Location loc = getLocation();
    Location next = loc.getAdjacentLocation(Location.SOUTH);

    if (gr.isValid(next)) {
        moveTo(next);
    } else
        removeSelfFromGrid();
    }
}
```

`turn` 方法顺时针旋转 45 度：

```
public void turn() {
    setDirection(getDirection() + 45);
}
```

> `Bug` 类的目的是提供一个扩展基类的示例。

仔细研究其代码。`CircleBug`、`SpiralBug`、`ZBug` 和 `DancingBug`。

假设我们要定义 `Bug` 的子类 `PredatorBug`。`PredatorBug` 可以移动到被另一个占据的位置并“吃掉”它。否则，`PredatorBug` 的行为像普通的 `Bug`。哪些方法中哪些方法？

(A) 仅 `act`

(B) 仅 `canMove`

(C) 仅 `move`

(D) `act` 和 `move`

(E) `canMove` 和 `move`

答案是 B。

# 7.5. 棋子

`Critter` 是一种以更复杂的方式与其他 actor 交互的 actor。`Critters` 在案例研究的第 4 部分引入。

`Critter` 类设计用于棋子层次结构的基类。`Critter` 的 `act` 方法涉及五个步骤：

- 获取要交互的 actor 列表；
- 处理列表中的 actor；
- 获取 critter 下一步移动的位置列表；
- 从步骤 3 获取的列表中选择一个位置；
- 移动到选定的位置。

每个步骤都通过单独的方法完成，因此 critter 的 `act` 方法调用五个方法，我们将称为“服务”方法。它看起来如下：



```java
public void act() {
    if (getGrid() == null)
        return;

    // 步骤 1:
    ArrayList<Actor> actors = getActors();

    // 步骤 2:
    processActors(actors);

    // 步骤 3:
    ArrayList<Location> moveLocs = getMoveLocations();

    // 步骤 4:
    Location loc = selectMoveLocation(moveLocs);

    // 步骤 5:
    makeMove(loc);
}
```

在 `Critter` 类本身中，服务方法 `getActors`、`processActors`、`getMoveLocations`、`selectMoveLocation` 和 `makeMove` 非常简单：

- `getActors` 返回该 `critter` 邻位置所有 `actor` 的列表；
- `processActors` “吃掉”（从网格中移除）该列表中所有的 `actor`，但岩石和其他 `critters`；
- `getMoveLocations` 返回所有空相邻位置的列表（包括被 `processActors` 清空的位置）；
- 如果由 `getMoveLocations` 返回的列表不为空，`selectMoveLocation` 会从该列表中随机选择一个位置；否则返回此 `Critter` 的当前位置；
- `makeMove` 通过调用其 `moveTo` 方法将此 `Critter` 移动到选定的位置。

> AP 考试可能会要求你对 `Critter` 的子类进行推理或编写代码。

`Critter` 是一种先处理某些 `actor` 然后再移动的 `actor`。案例研究叙述提到：“在 `Critter` 子类中重写 `act` 方法通常不是一个好主意。”

> 不要在这 `Critter` 子类中重写 `act` 方法。相反，请重写五个服务方法中的一个或多个。

`Critter` 的设置非常灵活，你可以通过重写五个服务方法中的一个或多个来实现许多不同的行为。你应该始终尝试尽可能少地重写这些方法。你应该在适当的情况下调用父类的方法，以避免代码重复。由于多态，`Critter` 的 `act` 方法将调用 `Critter` 子类正确的服务方法。

## 7.5 CRITTERS（生物）

`Bee`（蜜蜂）是一种如下如下运行的 `actor`。首先，蜜蜂会让所有相邻位置上的 `Flowers`（花朵）亮起颜色。之后，蜜蜂移动到包含花的随机相邻位置；或者，如果没有找到相邻的花，则移动到随机选择的空相邻位置。如果没有地方可以去，蜜蜂将停留在当前位置。如果蜜蜂移动到一朵花上，它会保存那朵花并在离开该位置时恢复它。以下哪种是实现 `Bee` 类的最佳方法？

- (A) 将 `Bee` 实现为 `Actor` 的子类，重写 `act` 方法
- (B) 将 `Bee` 实现为 `Bug` 的子类，重写 `act` 和 `moveTo` 方法
- (C) 将 `Bee` 实现为 `Critter` 的子类，重写 `act` 和 `moveTo` 方法
- (D) 将 `Bee` 实现为 `Critter` 的子类，重写 `processActors`、`getMoveLocations` 和 `makeMove` 方法
- (E) 将 `Bee` 实现为 `Critter` 的子类，重写 `getActors`、`processActors`、`getMoveLocations`、`selectMoveLocation` 和 `makeMove` 方法

`Bee` 对其他 `actor` 执行了某些操作，因此它属于“critters”这一大类。虽然可以从 `Actor` 直接派生 `Bee`（选项 A），但在 `Critter` 类已经存在的情况下，这样做会产生重复代码。也可以从 `Bug` 派生 `Bee`（选项 B），但这会破坏 `GridWorld` 整洁的层次结构。`Bug` 以特定的方式移动，最好让它保持原。通过从 `Bug` 派生 `Bee`，我们无法使用 `Bug` 的任何代码。

我们现在剩下三个关于“critter”的选项。选项 C 是完全不可接受的：我们从不重写 `Actor` 低级的 `moveTo`，而且通常不重写 `Critter` 的 `act` 方法。问题在于：重写 `processActors`、`getMoveLocations` 和 `makeMove`（选项 D）是否足以满足 `Bee` 的功能，还是说我们需要重写 `Critter` 的所有五个服务方法（选项 E）？注意，`Critter` 的 `getActors` 返回相邻位置所有 `actor` 的列表，然后 `processActors` 决定“吃掉”哪一个。`Bee` 可以以类似的方式工作：它可以使用 `Critter` 的 `getActors` 并让它的 `processActors` 测试邻居中哪些花并亮它们的颜色。

`getMoveLocations` 可以返回所有相邻花的列表，或者如果邻居没有花，则返回所有空相邻位置的列表。不需要更改 `Critter` 的 `selectMoveLocation`，它只是从列表中随机选择一个位置。`Bee` 的 `makeMove` 方法可以处理保存和/或恢复蜜蜂“落到”的花，如有必要，调用 `super.makeMove()` 来移动。选项 E 是多此一举。答案是 D。

## Critter 的子类

案例研究提供了两个 `Critter` 子类的示例：`ChameleonCritter` 和 `CrabCritter`。`ChameleonCritter` 的代码可能会出现在 AP 考试中。`CrabCritter` 只是一个例子，但我们建议你仔细学习。

`ChameleonCritter` 类没有构造方法——它默认使用 `Critter` 的无参构造方法。`ChameleonCritter` 重写了 `Critter` 五个服务方法中的两个：`processActors` 和 `makeMove`。`processActors` 随机选择一个邻居并将颜色赋值给 `ChameleonCritter`。

```java
public void processActors(ArrayList<Actor> actors) {
    int n = actors.size();
    if (n == 0)
        return;

    int r = (int)(Math.random() * n);

    Actor other = actors.get(r);
    setColor(other.getColor());
}
```

注意这种从列表中随机选择对象的惯用写法：

```java
int n = list.size();
if (n == 0)
    return;
int r = (int)(Math.random() * n);
Object x = list.get(r);
```

`ChameleonCritter` 的 `makeMove` 方法将此 `ChameleonCritter` 的方向设置为移动的方向，然后像普通的 `Critter` 一样移动。

```java
public void makeMove(Location loc) {
    setDirection(getLocation().getDirectionToward(loc));
    super.makeMove(loc);
}
```

## 7.6 – AB 主题：网格实现（GRID IMPLEMENTATIONS）

假设我们想创建一个行为像 `Critter` 一样的 `Butterfly`（蝴蝶），但它改变相邻位置的花的颜色。如果周围有多朵花，蝴蝶随机选择其中任意一个；如果周围没有花，则什么都不做。以下哪种是实现 `Butterfly` 的最佳方式？

- (A) 从 `Critter` 派生 `Butterfly`，重写 `act` 和 `makeMove` 方法
- (B) 从 `Critter` 派生 `Butterfly`，重写 `processNeighbors` 和 `makeMove` 方法
- (C) 从 `Critter` 派生 `Butterfly`，重写 `act` 方法
- (D) 从 `Critter` 派生 `Butterfly`，重写 `getActors` 方法
- (E) 从 `Critter` 派生 `Butterfly`，重写 `getNeighbors` 方法

由于蝴蝶的运行方式与 `Critter` 相似，它应该从 `Critter` 派生类。蝴蝶可以重写 `Critter` 的 `getActors` 方法来只包含列表中的花。或者，蝴蝶可以重写 `Critter` 的 `processActors` 方法来随机选择数量。但不需要两个都重写。答案是 D。

### 7.6 主题：网格实现

本节的所有内容对于 AB 考试都是必要的。

案例研究第 5 部分讨论了网格两种实现：`BoundedGrid<E>` 类使用二维数组实现 `Grid`；`UnboundedGrid<E>` 类使用 `HashMap<Location, E>` 实现 `Grid`。

每种实现都有其优缺点。在有界网格中，我们可以直接访问位置的对象，并且很容易找到邻居。另一方面，无界网格可以随意增大，空位置不会浪费内存，而且将所有对象放入列表效率更高，因为不需要扫描所有的行列。

`BoundedGrid` 和 `UnboundedGrid` 都扩展抽象类 `AbstractGrid`（图 7-4）。

```
« interface »
Grid<E>
||
AbstractGrid<E>
/      \
BoundedGrid<E>   UnboundedGrid<E>
```

图 7-4。`Grid` 接口及其实现。

`AbstractGrid` 使用四个“局部邻域”`Grid` 方法——`getValidLocations`、`getEmptyAdjacentLocations`、`getOccupiedAdjacentLocations` 和 `getNeighbors` 使用“通用”网格方法，如 `isValid` 和 `get`。例如：

```java
public ArrayList<Location> getValidLocations(Location loc) {
    ArrayList<Location> locs = new ArrayList<Location>();
    int d = Location.NORTH;
    for (int i = 0; i < Location.FULL_CIRCLE / Location.HALF_RIGHT; i++) {
        Location neighborLoc = loc.getAdjacentLocation(d);
        if (isValid(neighborLoc)) {
            locs.add(neighborLoc);
            d = d + Location.HALF_RIGHT;
        }
    }
    return locs;
}
```

该方法的精简版本为：

```java
public ArrayList<Location> getValidLocations(Location loc) {
    ArrayList<Location> locs = new ArrayList<Location>();
    for (int d = 0; d < 360; d += 45) {
        Location neighborLoc = loc.getAdjacentLocation(d);
        if (isValid(neighborLoc)) {
            locs.add(neighborLoc);
        }
    }
    return locs;
}
```

`AbstractGrid` 将剩余的七个“通用网格”方法——`numRows`、`numCols`、`isValid`、`get`、`put`、`remove` 和 `getOccupiedLocations` 抽象化（见第 157 页的图 7-3）。`BoundedGrid` 和 `UnboundedGrid` 实现这些方法。

## BoundedGrid

在 `BoundedGrid<E>` 类中，对象存储在一个二维数组中：

```java
private Object[] occupantArray;
```

空位置为空。`BoundedGrid` 的构造函数根据正数量的行和列分配 `occupantArray`；元素默认填充为 `null`。对于 `BoundedGrid` 中的有效位置，该位置的行和列必须在以下范围内：`0 <= row < getNumRows()`；`0 <= col < getNumCols()`。在 Java 中，它看起来如下：

```java
public boolean isValid(Location loc)
{
    return 0 <= loc.getRow() && loc.getRow() < getNumRows()
        && 0 <= loc.getCol() && loc.getCol() < getNumCols();
}
```

Java 不支持泛型数组，因此 `occupantArray` 是一个 `Object` 数组；在 `get` 方法中使用类型转换将元素转换为类型 `E`（这会导致不可避免的警告）：

```java
public E get(Location loc)
{
    if (!isValid(loc))
        throw new IllegalArgumentException("Location " + loc
            + is not valid");
    return (E) occupantArray[loc.getRow()][loc.getCol()];
        // 转换到 (E) 会导致警告
}
```

边界网格实现在访问、添加和删除元素方面非常高效：`get`、`put` 和 `remove` 方法的时间复杂度（大 O 表示）为 `O(1)`。然而，要获取所有占用位置的列表，你需要扫描整个 `occupantArray`：

```java
public ArrayList<Location> getOccupiedLocations() {
    ArrayList<Location> a = new ArrayList<Location>();
    
    for (int r = 0; r < getNumRows(); r++) {
        for (int c = 0; c < getNumCols(); c++) {
            Location loc = new Location(r, c);
            if (get(loc) != null) {
                a.add(loc);
            }
        }
    }
    return a;
}
```

该方法的时间复杂度为 `O(rows * cols)`。空间复杂度也是如此。如果一个大网格只包含几个 `Actor`，可能会浪费大量的时间空间。

## UnboundedGrid

在 `UnboundedGrid<E>` 类中，对象存储在 `HashMap` 中，使用位置作为键：

```java
private Map<Location, E> occupantMap;

public UnboundedGrid() {
    occupantMap = new HashMap<Location, E>();
}
```

在 `UnboundedGrid` 中，`getNumRows` 和 `getNumCols` 方法返回 `-1`；`isAlways` 返回 `true`。

`get`、`put` 和 `remove` 方法直接翻译为 `HashMap` 的 `get`、`put` 和 `remove`。

```java
public E get(Location loc) {
    if (loc == null) {
        throw new NullPointerException("loc == null");
    }
    return occupantMap.get(loc);
}
```

回想 `HashMap` 中 `get`、`put` 和 `remove` 方法的平均时间复杂度（大 O 表示）为 `O(1)`。

要获取所有占用位置的列表，你需要遍历 `occupantMap` 的键：

```java
public ArrayList<Location> getOccupiedLocations() {
    ArrayList<Location> a = new ArrayList<Location>();
    for (Location loc : occupantMap.keySet()) {
        a.add(loc);
    }
    return a;
}
```

（快捷方法是

```java
public ArrayList<Location> getOccupiedLocations() {
    return new ArrayList<Location>(occupantMap.keySet());
}
```

但是这个 `ArrayList` 的构造函数不在 AP 子集中。）

## 效率考虑

表 7-2 列出了 `BoundedGrid` 和 `UnboundedGrid` 实现中网格方法的平均时间复杂度。在 `BoundedGrid` 中，最佳、平均和最坏访问时间相同，它们不取决于网格中对象的数量。`isValid`、`get`、`put` 和 `remove` 的时间复杂度为 `O(1)`。在 `UnboundedGrid` 中，这些方法的平均时间复杂度也是 `O(1)`。然而，`get`、`put` 和 `remove` 的最坏运行时间取决于任何哈希表典型的波动。例如，`put` 方法可能需要重新分配表并重新哈希元素。在这种情况下，大 O 变为 `O(n)`，但这种情况并不经常发生。

| 方法 | BoundedGrid | UnboundedGrid |
|---|---|---|



## 7.7 案例分析技巧

要成功回答 GridWorld 案例，你需要熟悉 `Location` 和 API。对于考试，仔细观察 `Bug`、`Critter` 以及 `AbstractGrid`、`BoundedGrid` 和 `UnboundedGrid` 类。

单选题可能侧重于概念：为什么做这些决策、替代方案、某些方法的功能、继承和多态如何工作等。不要慌，如果你读过案例分析，这些都是常识。

## 7.7 案例分析题提示

简答题要求你编写代码的变体。这里的关键是在案例手册中找到相似的代码段并进行调整。不要从零开始编写。注意以下几：

- `equals` vs `==`：比较位置使用 `equals`；比较 `Actor` 使用 `==`。

- `ArrayList` vs 数组：网格方法 `getOccupiedLocations`、`getValidAdjacentLocations`、`getEmptyAdjacentLocations` 返回 `ArrayList<Location>`；都不返回 `Actor`。在这些列表上使用 `.get(i)`，而不是 `[i]`。

- 调用正确类的方法。例如，`getAdjacentLocation(int direction)` 和 `getDirectionToward(Location target)` 在 `Location` 中而不是 `Grid` 中；`getValidAdjacentLocations(Location loc)` 在 `Grid` 中。

- 使用 `actor` 的 `getLocation` 和 `getGrid` 方法获取其位置和网格。

- 使用 `actor` 的 `putSelfInGrid` 方法将 `actor` 放入网格的给定位置。使用 `actor` 的 `removeSelfFromGrid` 方法从网格中移除。

- 要更改 `actor` 的方向，使用 `setDirection(getDirection() + ...)`。例如，要反转方向，编写 `setDirection(getDirection() + 180);`。

- `private`：访问私有实例字段是错误的。请使用访问器方法。例如：

```java
GridActor gr = getGrid();
Location loc = getLocation();

Flower flower = new Flower(getColor());
flower.putSelfInGrid(gr, loc);
```

注意 `Bug` `Critter` 有实例字段，除了从 `Actor` 继承的字段（在 `Actor` 中是私有的）。

- 除了动手操作计算机外，在练习案例分析题时，也可以做一些纸笔练习。在案例分析叙述中使用使用的附录 C 和 E（对于 AB 考试还包括 D 和 F），以熟悉格式：你在考试中收到的材料将与其相似。

## 第 8 章 历年自由作答题解析答案

本章材料位于我们的网站上：

```
http://www.skylit.com/beprepred/fr.html
```

该页面包含了近几年自由作答题的链接以及每个问题的解析答案。

## 模拟测试卷 A-1

计算机科学 A

第一部分

时间 — 1 小时 15 分钟

题目数量 — 40

占总分百分比 — 50%

- 1. 考虑以下方法：

```java
public void reduce(int[] arr, int len)
{
    for (int i = 0; i < len; i++)
    {
        arr[i]--;
    }
    len--;
}
```

- 下列代码段的输出是什么？

```java
int[] counts = {3, 2, 1, 0, 0, 0};
int len = 3;
reduce(counts, len);
for (int k : counts)
{
    System.out.print(k + " ");
}
System.out.println(len);
```

- (A) 0 1 2 2

(B) 0 1 2 3 4 5 3

(C) 2 1 0 0 0 2

(D) 2 1 0 0 0 3

(E) 3 2 1 0 0 0 3

- 2. 下列哪个陈述会导致语法错误？

- (A) `String x = "123";`

(B) `Integer x = "123";`

(C) `Object x = "123";`

(D) `Comparable x = "123";`

(E) 以上所有内容均可编译且无错误。

- 3. 下列代码段在编译并执行后的结果是什么？

```
int m = 4, n = 5;
double d = Math.sqrt((m + n)/2);
System.out.println(d);
```

- (A) 语法错误 "sqrt(double) in java.lang.Math cannot be applied to int"

(B) 显示 1.5

(C) 显示 2.0

(D) 显示 2.121302435596424

(E) `ClassCastException`

- 4. 假设我们有一个编译好的 Java 类 `Fun.class`，但我们没有它的源代码。我们发现一条语句

```
Fun fun = new Fun(100);
```

编译后无错误。下列哪个陈述如果能够正确编译，将能够让我们确信 `Fun` 实现了 `Comparable<Fun>`？

- (A) `Comparable<Fun> c = fun;`

(B) `System.out.print(fun.compareTo(0));`

(C) `System.out.print(fun.compareTo(fun));`

(D) `System.out.print(fun.compareTo(new Fun(99)));`

(E) 以上都不是

- 5. 在执行以下代码段后，`product` 的值是多少？

```
int[] factors = {2, 3, 4, 7, 2, 5};
int product = 1;
for (int i = 1; i < factors.length; i += 2)
{
    product *= (factors[i] % factors[i - 1]);
}
```

- (A) 0

(B) 1

(C) 2

(D) 3

(E) 5

- 6. 给定 `x` 为 `true`，`y` 为 `true`，`z` 为 `false`，下列哪个表达式的求结果为 `false`？

- (A) `(x && y) || z`

(B) `x || (y) && z`

(C) `y || (x && z)`

(D) `x || (y && z)`

(E) `x && (y || z)`

- 7. 考虑以下方法：

```
public String encrypt(String word)
{
    int pos = word.length() / 2;
    if (pos >= 1)
    {
        word = encrypt(word.substring(pos)) + 
        encrypt(word.substring(0, pos));
    }
    return word;
}
```

`encrypt("SECRET")` 返回的字符串内容是什么？

- (A) TERCES

(B) TSECRE

(C) RETSEC

(D) CESTER

(E) ETRE

- 8. 下列代码段的输出是什么？

```java
String url = "http://www.usa.gov";
int pos = url.indexOf("http://");
if (pos >= 0)
{
    System.out.println("<" + url.substring(0, pos) + ">");
}
else
{
    System.out.println("not found");
}
```

- (A) >

(B) <www.usa.gov

(C) <http://www.usa.gov>

(D) not found

(E) `IndexOutOfBoundsException`

- 9. 在乡村集会上，奖项颁给最重的猪。参赛的有超过 5000 只猪，它们的记录存储在数组中。下列哪种寻找重猪记录的方法效率最高？

- (A) 选择排序 (`Selection Sort`)

(B) 选择排序终止五次

(C) 插入排序 (`Insertion Sort`)

(D) 插入排序终止五次

(E) 合并排序 (`Mergesort`)

- 10. 假设定义了以下三个类，每个类都有“无参数”构造函数（不带参数的构造函数）：

```
public class Vehicle {...}
public class Car extends Vehicle {...}
public class Buick extends Car {...}
```

下列哪个不是合法语句？

- (A) `Vehicle vehicle = new Car();`

(B) `Vehicle vehicle = new Buick();`

(C) `Car car = new Buick();`

(D) `Car car = new Vehicle();`

(E)

- 11. 考虑以下方法：

```
// 返回数字 d 出现的次数
// 前提：n 和 d 为非负
private int findDigit(int n, int d)
int count = 0;
<statement1>
while (n > 0) {
    if (n % 10 == d) {
        count++;
    }
    <statement2>
}
return count;
```

下列哪项可以替换 `<statement1>` 和 `<statement2>` 使 `findDigit` 符合要求？

- `<statement1>` `<statement2>`

(A) `if (n == 0) return 1;` `n /= 10;`

(B) `if (n == 0) return 1;` `d *= 10;`

(C) `if (d == 0) count++;` `n -= 10;`

(D) `if (n == 0) return 0;` `n *= 10;`

(E) `if (n == 0) d == 0) count++;` `n /= 10;`

- 12. 当实践信息隐藏时，下列哪个任务会变得更容易？

- I. 为类实现关系

- II. 对项目中某个类的实现进行修改

- III. 为同一项目的项目的程序员编写规范

- (A) 仅 I

(B) 仅 II

(C) I 和 II

(D) II 和 III

(E) I、II 和 III

- 13. 下列两个版本的 `search` 方法都旨在 `ArrayList` 包含目标值时返回 `true`，否则返回 `false`。

版本 1：

```
public boolean search(ArrayList<Object> list, Object target)
{
    for (int k = 0; k < list.size(); k++)
    {
        if (target.equals(list(k)))
            return true;
    }
    return false;
}
```

版本 2：

```java
public boolean search(ArrayList<Object> list, Object target)
{
    boolean found = false;
    for (int k = 0; k < list.size(); k++)
    {
        if (target.equals(list(k)))
            found = true;
    }
    return found;
}
```

关于 `search` 的两个版本，下列哪个陈述是正确的？

- (A) 只有版本 1 符合预期。

(B) 只有版本 2 符合预期。

(C) 两个都符合预期；版本 1 通常比版本 2 高效。

(D) 两个都符合预期；版本 2 通常比版本 1 高效。

(E) 两个都符合预期；两个都是高效的。

- 问题 14-15 参考以下合并排序的实现：

```
public class Mergesort{
    // 返回一个包含值的数组
    // arr[m], arr[m+1], ... arr[n] 升序排列
    // 前提 0 <= m <= n
    public static int[] sort(int[] arr, int m, int n) {
        int[] result = new int[n - m + 1];
        if (m == n) {
            result[0] = arr[m];
        } else {
            int mid = (n + m) / 2;
            int[] result1 = sort(arr, m, mid);
            int[] result2 = sort(arr, mid + 1, n);
            result = merge(result1, result2);
        }
        return result;
    }
    // 按升序合并 arr1 和 arr2 并返回数组
    private static int[] merge(int[] result1, int[] result2) {
        /* 实现所示 */
    }
}
```

- 14. 如果 `int[] arr` 包含八个值并调用 `Mergesort(arr, 0, 7)`，`Mergesort` 的 `merge` 方法总会被调用多少次？

(A) 1

(B) 3

(C) 7

(D) 8

(E) 15

- 15. 如果 `Mergesort(arr, 0, 999)` 平均需要 40 ms，且 `Mergesort.merge(arr1, arr2)` 平均需要 `0.01*(arr1.length + arr2.length)`，那么 `Mergesort(arr, 0, 999)` 的平均运行时间是多少？

- (A) 50 ms

(B) 100 ms

(C) 160 ms

(D) 170 ms

(E) 180 ms

问题 18-21 涉及抽象类 `House` 及其子类 `HouseForSale`：

```
public abstract class House implements Comparable<House>
{
    private int mySize;

    public House(int size) { mySize = size; }
    public int getSize() { return mySize; }
    public void setSize(int size) { mySize = size; }

    public int compareTo(House other)
    {
        return getSize() - other.getSize();
    }

    public abstract int getPrice();
}

public class HouseForSale extends House
{
    private int myPrice;

    public HouseForSale(int size, int price)
    {
        // ... 缺失的语句
        myPrice = price;
    }

    public int getPrice() { return myPrice; }

    public int compareTo(House other)
    {
        return getPrice() - ((HouseForSale)other).getPrice();
    }

    // ... 其他构造函数、方法和字段
    // 未显示
```

18. 下列哪项是 `HouseForSale` 构造函数中 `< 缺失的语句 >` 最合适的替换项？

- (A) `mySize = size;`

(B) `setSize(size);`

(C) `super.setSize(size);`

(D) `super(size);`



- (E) `super = new House(size);`

19. 假设程序员在编写`HouseSale`时不小心在类中写错了`"compareTo"`。当他尝试编译并运行该类以及客户端类中的以下语句时，会发生什么？

```
House house1 = new HouseSale(2000, 129000);
House house2 = new HouseSale(1800, 149000);
System.out.println(house1.compareTo(house2));
```

- (A) `HouseFor`类中出现语法错误`"undefined compareTo"`
- (B) 语法错误`"HouseSale should be declared abstract"`
- (C) 代码编译无错误并显示`200`。
- (D) 代码编译无错误但生成了`NoSuchMethodException`。
- (E) 代码编译无错误但生成了`ClassCastException`。

20. 如果类`House`和`HouseSale`编译没有问题，下列哪种声明将导致语法错误？

- (A) `House[] houses = new House[2];`
- (B) `HouseSale[] houses = {new House(2000), new House(1800)};`
- (C) `House[] houses = {new HouseSale(2000, 129000), new HouseSale(1800, 149000)};`
- (D) `Comparable[] houses = {new HouseSale(2000, 129000), new HouseSale(1800, 149000)};`
- (E) `HouseSale[] houses = {new HouseSale(2000, 129000), new HouseSale(1800, 149000)}`

21. 下列哪项是在`HouseSale`中定义`getSize`的最合适方法？

- (A) `public int getSize() { return mySize; }`
- (B) `public int getSize() { return super.mySize; }`
- (C) `public int getSize() { return super(mySize); }`
- (D) `public int getSize() { return super.getSize(); }`
- (E) 没有必要定义，因为`House`中已经写了相同的代码。

22. 二分搜索算法设计用于处理按升序排列的数组。在数组未排序的情况下，在下列哪种情况下算法会找到给定的目标值？

- I. 数组有奇数个元素，且目标值恰好位于数组的中间。
- II. 数组部分排序：数组左侧三分之一的值全部按升序排列，且目标值位于其中。
- III. 数组部分排序：目标左侧的所有值都小于目标值，目标右侧的所有值都大于目标值。

- (A) 仅 I
- (B) I 和 II
- (C) I 和 III
- (D) II 和 III
- (E) I、II 和 III

23. 考虑以下方法：

```
private double compute(int x, int y)
{
    double r = 0;

    if (!(y == 0 || x / y <= 2))
        r = 1 / ((x - 2*y) * (2*x - y));

    return r;
}
```

对于下列哪些`x`和`y`值，`compute(x, y)`会抛出异常？

- (A) `x = 0, y = 0`
- (B) `x = 1, y = 2`
- (C) `x = 2, y = 1`
- (D) `x = 3, y = 5`
- (E) 以上均不是

问题 24-29 涉及`GridWorld`案例研究的代码。

24. 如果网格中`Bug`正前方直接有一块岩石（`Rock`），`Bug`会如何表现？

- (A) `Bug`从网格中移除。
- (B) `Bug`保持其当前状态——不采取行动。
- (C) 岩石被移除，`Bug`向前移动，并在原来的位置留下一朵新花（`Flower`）。
- (D) `Bug`转向 180 度。
- (E) `Bug`向右转 45 度。

25. 考虑以下`Bug`的子类：

```
public class SpinningBug extends Bug {
    public void act() {
        super.act();
        turn();
    }
    public void turn() {
        setDirection(getDirection() - 90);
    }
}
```

如果将`SpinningBug`放入网格，它会如何操作？

- (A) `SpinningBug`会抛出移动异常，因为`move`方法未定义。
- (B) 像普通`Bug`一样操作，然后向左转 90 度。
- (C) 如果可以移动，它会向前移动，然后向左。
- (D) 如果可以移动，它会向前移动，然后向左转 45 度。
- (E) 向左。

26. 下列哪些代码段可以通过编译？

```
I. Actor a = new Actor();
   a.setColor(RED);

II. Actor a = new Bug(GREEN);

III. Actor a = new();
   a(BLUE);
```

- (A) 仅 I
- (B) 仅 II
- (C) I 和 II
- (D) II 和 III
- (E) I、II 和 III

27. 当首次创建一个`Critter`对象时，它的初始颜色和方向是什么？

- (A) 蓝色和北
- (B) 红色和北
- (C) 蓝色和随机
- (D) 随机

28. 下列哪项不是多态的示例？

- (A) 为`Rocks`、`Flowers`和`Critters`调用`act`方法
- (B) `Bug`的方法继承自`Critter`
- (C) `Critter`的方法继承自`Grid`
- (D) `Bug`的方法调用`Grid`
- (E) 以上所有

29. 考虑以下类：

```
public class IntGrid extends BoundedGrid<Integer>
{
    // 未显示构造函数

    // 将所有位置的对象加 1
    public void increment()
    {
        < missing code >
    }
}
```

下列哪些代码段可以替换`< missing code >`使该方法工作？

- (A) `for (Location loc : getOccupiedLocations())`

  {

    `Integer i = get(loc);`

    `put(loc, new Integer(i.intValue() + 1));`

  }

- (B) `for (Location loc : grid.getOccupiedLocations())`

  {

    `Integer i = get(loc);`

    `i.setValue(i.intValue() + 1);`

  }

- (C) `for (Location loc : getOccupiedLocations())`

  {

    `Integer i = get(loc);`

    `i.setValue(i.intValue() + 1);`

    `put(loc, i);`

  }

- (D) `for (Location loc : getOccupiedLocations())`

    `put(loc, new Integer(get(loc).intValue() + 1));`

- (E) `for (Location loc : grid.getOccupiedLocations())`

    `put(loc, new Integer(get(loc).intValue() + 1));`

30. 在正边形中，对角线长度与边长度之比等于黄金分割（定义为`1+\sqrt5}/2≈1.618`）。考虑以下表示正边形的类：

```
public class Pentagon {
    public static final double goldenRatio = (1 + Math.sqrt(5.0)) / 2;
    private double side;

    public Pentagon(double x) {
        side = x;
    }

    public double getDiagonalLength() {
        return side * goldenRatio;
    }
}
```

下列哪些代码段可以无错误编译并显示边长为`3.0`的正边形的对角线长度？

I. `System.out.println(3/2 * (1 + Math.sqrt(5.0)));`

II. `System.out.println(3.0 * Pentagon.goldenRatio);`

III. `Pentagon p = new Pentagon(3); System.out.println(p.getDiagonalLength());`

- (A) 仅 I
- (B) 仅 II
- (C) 仅 III
- (D) I 和 II
- (E) II 和 III

31. 假设程序员编写了一个对整数数组插入插入的方法。该方法没有前提条件。下列哪项不是该方法的有效测试？

- (A) 长度为 5 的随机值数组
- (B) 长度为 5 且按升序排列的数组
- (C) 空数组（长度为 0）
- (D) 长度为 1 的数组
- (E) 以上所有都是有效测试。

32. 考虑以下`ArrayList<String>`代码段，其中缺少一个`"for"`循环：

```
ArrayList<String> letters = new ArrayList<String>();

letters.add("A");
letters.add("B");
letters.add("C");

missing "for" loop
System.out.println(letters);
```

假设执行上述代码段时，显示结果

`[A*, B*, C*]`

下列哪一组可以替换`<missing "for" loop>`?

- I. `for (int i = 0; i < letters.size(); i++)`

   `letters.set(i, letters.get(i) + "*");`

- II. `for (int i = 0; i < letters.size(); i++)`

   `String s = letters.get(i);`

   `s = s + "*";`

- III. `for (String s : letters)`

   `s = s + "*";`

- (A) 仅 I
- (B) 仅 II
- (C) I 和 II
- (D) II 和 III
- (E) I, II 和 III

33. 如果类`C`实现了接口`I`且没有无参构造函数（不接受任何参数的构造函数），下列哪个陈述会导致语法错误？

- (A) `C x = new C();`
- (B) `I x = new C();`
- (C) `C[] x = new C[10];`
- (D) `I[] x = new I[10];`
- (E) 以上全部编译均无错误。

# 194 模拟考试 – A-1

34. 考虑以下方法：

```
public void printNumbers(int n)
{
    for (int i = 1; i <= n - 1; i++)
        printNumbers(i);
    System.out.print(n + " ");
}
```

调用`printNumbers(3)`时的输出是什么？

- (A) `1 2`
- (B) `1 2 3`
- (C) `1 1 2 3`
- (D) `1 2 1 2 3`
- (E) `1 2 1 2 3`

35. 考虑两种不同的数据结构设计，用于存储棒球运动员在一个赛季中击出的全垒打总数。有`n`个运动员（`n > 1000`），每个总数的范围在 0 到 80 之间。

设计 A：使用长度为 81 的数组。数组的每个索引对应一个全垒打数量，数组的每个元素是某个列表的引用，该列表包含击出该数量全垒打的运动员姓名。

设计 B：使用长度为`n`的数组，使得数组的每个元素对应一个运动员。数组的每个元素都是一个代表运动员的对象，持有其姓名和击出的全垒打数量。数组的元素按运动员姓名的字母顺序排序。

该数据结构将用于支持三个操作：

操作 1：打印所有击出超过 50 次全垒打的运动员的姓名。

操作 2：给定运动员的名字，查找该运动员的全垒打总数。

操作 3：给定两个运动员的名字，确定他们击出的全垒打数量是否相同。

这三个操作中，哪一个使用设计 A 比使用设计 B 执行更高效？

- (A) 仅操作 1
- (B) 仅操作 2
- (C) 仅操作 3
- (D) 操作 1 和 2
- (E) 操作 2 和 3

36. 考虑以下类：

```
public class NumList
{
    private ArrayList<Integer> list;

    public NumList() { list = new ArrayList<Integer>(); }
    public void add(int value) { /* 实现未显示 */ }
    public void remove(int value)
    { /* 实现未显示 */ }
    public void shuffle() { /* 实现未显示 */ }
    public String toString() { /* 实现未显示 */ }
}
```

假设我们计划通过编写构造函数和其他方法来实现`NumList`类。哪一组方法可以方便地被优先开发和测试？

- (A) `add`和`toString`
- (B) `toString`和`remove`
- (C) `add`和`remove`
- (D) `shuffle`和`remove`
- (E) `add`和`shuffle`

37. 假设类`C`有一个私有的`int` data 字段`value`：

```
public class C
{
    private int value;
    // ... 其他字段、构造函数和方法未显示
}
```

假设我们有一个方法

```java
public static int compare(C x, C y)
{ return x.value - y.value; }
```

并且我们需要为它找到“家”：将其放入某个类中。我们应该将此方法放在哪里才能使其无错误地编译？

- (A) 仅放入`C`
- (B) 仅放入`C`或`C`的任何子类
- (C) 仅放入`C`或`C`的任何父类
- (D) 放入任何类
- (E) 无论将其放在哪个类中，此方法始终会导致语法错误。

38. 考虑以下类：

```
public class ArrayProcessor
{
    public static void run(int[] arr)
    {
        for (int i = 0; i < arr.length; i++) {
            for (int j = arr.length - 1; j > i; j--) {
                if (arr[j] < arr[i]) {
                    swap(arr, i, j);
                }
            }
        }
    }

    private static void swap(int[] arr, int i, int j)
    {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }
}
```

执行以下代码时，`ArrayProcessor`的`swap`方法将被调用多少次？

```
int[] counts = {1, 2, 3, 4, 5};
ArrayProcessor.run(counts);
```

- (A) 1
- (B) 5
- (C) 15
- (D) 30
- (E) 35

问题 39–40 参考一个包含以下类的项目：

```
public class OrderItem
{
    private String itemName;
    private int price, quantity;

    public OrderItem(String name, int pr, int qty)
    { itemName = name; price = pr; quantity = qty; }

    public int getPrice()
    // ... 其他构造函数和方法未显示
}

public class Order
{
    private ArrayList<OrderItem> items;

    public Order() { items = new ArrayList<OrderItem>(); }

    public int getTotal()
    {
        int total = 0;
        for (OrderItem item : items)
        {
            total += item.getPrice();
        }
        return total;
    }

    public void add(OrderItem item) { items.add(item); }
}
```

项目设计者指示程序员将代码修改如下：

```
public interface Priced
{
    int getPrice();
}
```



将其引入项目，并在`Order`类中将`OrderItem`替换为`Priced`。这里应用了什么设计原则，什么 Java 特性使得修改后的代码可行？

- (A) 封装和多态
- (B) 抽象和封装
- (C) 抽象和多态
- (D) 消息隐藏和封装
- (E) 信息隐藏和 Java

## 198 模拟考试

### 40. 下列哪些是进行此更改的良好理由？

I. 在未来的某个版本中，`Order`对象的`items`列表可能会持有`OrderItem`的子类。

II. 在未来的某个版本中，`items`列表可以混合不同类型的`Priced`对象。

III. `Order`类可以重用到处理不同类型`Priced`的其他项目中。

- (A) 仅 I
- (B) 仅 II
- (C) I 和 II
- (D) II 和 III
- (E) I, II 和 III

### (b)

编写`MazeBug`类的`moveLeft`方法。该方法让昆虫向左旋转 90 度，然后向前移动到相邻位置，并在之前占据的位置放置一朵花。换句话说，`MazeBug`向左转后，移动方式与普通的`Bug`一样。

在下方完成`moveLeft`方法。

```java
// 向左旋转 90 度，然后像普通
// 一样移动
public void moveLeft()
```

### (c)

编写`canMoveLeft`方法。当昆虫的相邻位置有效且不包含岩石，而其左后方的对角线位置无效或包含岩石时，`MazeBug`就可以左转。例如，如果昆虫面向东方，则北侧的相邻位置应该是空的（或有花），而西北侧的相邻位置应该有岩石（或无效），这样昆虫才能向左转。下图说明了这样的情况：

![](img/e320d34bf6b289b099c4a1d8b2b5ab9c_214_0.png)

在下方完成`canMoveLeft`方法。

```java
// 如果此昆虫位于墙壁左转的
// 处，即此昆虫左侧的相邻
// 位置有效且为空或有花，
// 而其左后方的对角线相邻
// 位置无效或有岩石；
// 否则返回 false
public boolean canMoveLeft()
```

### (d)

`MazeBug`重写了`Bug`的`act`方法。你是否是否需要在`MazeBug`中重写`Bug`的任何其他方法以使`MazeBug`按规范工作？如果是，请写下所需的方法。

## 202 模拟考试题 ~ A-1

### 2.

本题涉及学校校车运输系统类的设计与实现。在该系统中，`Student`对象代表某所学校的一名学生。学生有一个名字和地址，分别用街道名称（字符串）和该街道上的门牌号表示：

```java
public class Student {
    // 未显示数据字段和构造函数

    // 返回此学生的姓名
    private String getName() { /* 实现未显示 */ }

    // 返回该学生居住的街道
    private String getStreet() { /* 实现未显示 */ }

    // 返回该学生所在街道的门牌号
    private int getNumber() { /* 实现未显示 */ }

    // 返回一个表示此学生的格式字符串
    // 姓名：门牌号 街道
    // 例如，
    // Maria Litvin: 15 River St
    public String toString() { /* 实现未显示 */ }

    // 如果此学生和其他学生住在同一条街道，
    // 返回他们门牌号差的绝对值；
    // 否则返回 99999
    // 前提条件：other 不为空
    public int distance(Student other) { /* 在部分 (a) 中实现 */ }
}
```

`SchoolBus`对象代表一条校车路线，包含一个分配给该校车的学生列表。`SchoolBus`类有一个构造函数，用于创建一个具有指定座数的校车；其方法`getNumStudents`返回当前分配给该校车的学生人数，`isFull`指明该校车是否有空位，以及其他处理学生列表的方法。你将在部分 (b) 中设计并实现此类类。

`SchoolTransport`处理某所学校的校车分配。它拥有一个`SchoolBus`对象的`ArrayList`，以及一个将新学生录入该学校运输系统的方法。新学生会被添加到已经载有来自同一街道且离新学生最近的校车上：

```java
public class SchoolTransport {
    private ArrayList<SchoolBus> buses;
    // 表示该学校所有校车路线的列表

    // 在所有校车中寻找尚未满
    // 且距离学生最近的校车
    //（根据 Student 对象定义的距离）；
    // 如果找到，则将学生添加到同一辆校车并返回 true；
    // 否则返回 false
    public boolean enroll(Student student) {
        /* 在部分 (c) 中实现 */
    }
    // ... 未显示的构造函数和其他方法
}
```

#### (a)

编写`Student`类的`distance`方法。如果此学生与另一学生住在同一条街道，则`distance`返回他们门牌号差的绝对值；否则返回 99999。

在下方完成`distance`方法。

```java
// 如果此学生和另一学生住在同一条街道，
// 返回他们门牌号差的绝对值；
// 否则返回 99999
// 前提条件：other 不为空
public int distance(Student other)
```

#### (b)

编写一个`SchoolBus`类，代表一条校车路线并持有在该校车上的学生列表。在编写此类类时：

- 使用`Student`对象的`ArrayList`来持有该校车上的学生列表；
- 为数据字段使用合适的名称；
- 实现一个接受一个参数的构造函数，参数为该校车的可用总座位；
- 实现以下公共方法：

```java
int getNumStudents()           返回当前在该校车列表
                              上的学生人数

boolean isFull()               如果该校车没有更多空
                                座，则返回 true；否则返回 false

Student getStudent(i)          返回该校车第 i 个位置的
                              学生

boolean add(Student student)   如果有空位，则将学生添加到
                              校车列表并返回 true；
                              否则返回 false

void printOut()                将该校车上的学生
                              逐行显示，格式与 Student
                              方法一致
```

例如，以下代码段：

```java
SchoolBus bus = new SchoolBus(3);
boolean result;
result = bus.add(new Student("Dave", "High St", 27));
System.out.println(result + " " + bus.isFull());
result = bus.add(new Student("Roger", "Elm St", 3));
System.out.println(result + " " + bus.isFull());
result = bus.add(new Student("Judy", "High St", 124));
System.out.println(result + " " + bus.isFull());
result = bus.add(new Student("Maria", "River St", 15));
System.out.println(result + " " + bus.isFull());
bus.printOut();
```

输出：

```text
true false
true false
true true
false true
Dave: 27 High St
Roger: 3 Elm St
Judy: 124 High St
```

#### (c)

编写`SchoolTransport`的`enroll`方法。该方法尝试寻找学生。在所有未满的校车中，寻找已录入且距离新学生最近的学生（根据`distance`方法定义的距离最小）。如果找到了这样的学生，方法将新学生放在同一辆校车上并返回`true`。否则，方法返回`false`，表示校车安排决策交给学校交通管理器。

在下方完成`enroll`方法。

```java
// 在所有校车中寻找尚未满
// 且距离学生最近的校车
//（根据 Student 对象定义的距离）；
// 如果找到，则将学生添加到同一辆校车并返回 true；
// 否则返回 false
boolean enroll(Student student)
```

### 3.

下图显示了用于计算不同类型邮件邮资的类的简化分层次结构。

![](img/e320d34bf6b289b099c4a1d8b2b5ab9c_219_0.png)

`Mail`和`PriorityMail`类所示。`Mail`是一个抽象类：

```java
public abstract class Mail
{
    public abstract double calculatePostage();

    // 返回格式化为 2 位小数的
    // 邮资
    public String toString()
    {
        DecimalFormat money = new DecimalFormat("0.00");
        return money.format(calculatePostage());
    }
}
```

`PriorityMail`有一个接受两个参数的构造函数：邮件的重量（磅）和递送区域。它还有一个根据重量和区域计算邮资的方法：

```java
public class PriorityMail extends Mail {
    private double weight;
    // 这封邮件的重量（单位：磅）

    private int zone;
    // 这封邮件的配送区域

    // 前提: 1 <= zone <= 8
    public PriorityMail(double lbs, int z) {
        weight = lbs;
        zone = z;
    }
}
```

```java
// 返回通过优先邮件邮寄这封邮件的费用：
// 一磅以下邮寄到任何区域费用为 $4.05；
// 超过 1 磅的每磅或不足一磅增加 $0.80 * zone
public double calculatePostage() {
    /* 未显示实现部分 */
}
```

`FlatRateEnv`代表优先邮件平信信封（flat-envelope），而`FlatBox`对象代表优先邮件固定费率箱（flat-rate box）。这两项服务无论实际重量和配送区域如何都提供固定费率。

#### (a)

编写与上述继承层次结构对应的`FlatRateEnv`和`FlatBox`类的完整定义。在每个类中，请提供一个无参构造函数（不带参数的构造函数）。邮寄固定费率优先邮件信封（无论其实际重量和区域）的费用与邮寄位于 1 区域的一磅优先邮件的费用相同。固定费率优先邮件箱的费用是固定费率信封的两倍。例如，如果你有：

```java
Mail piece1 = new PriorityMail(1.0, 1);
Mail piece2 = new FlatRateEnv();
Mail piece3 = new FlatRateBox();
```

并且：

```java
System.out.println(piece1);
```

显示：

```text
4.05
```

那么：

```java
System.out.println(piece2 + " " + piece3);
```

应该显示：

```text
4.05 8.10
```

为了获得满分，你必须重用提供的方法，并避免实例变量和方法的重复。

## 208 模拟考试 ~ A-1

#### (b)

在本题的这部分，你需要编写一个`InsuredMail`类的完整定义。

美国邮政局为不同类型的邮件提供保险。保险费用仅取决于发送者购买的保险金额，而不取决于特定的邮件类型。如果为代表不同类型的邮件的每个类都添加保险选项，将太繁琐了。相反，我们可以创建一个“包装”类，帮助我们计算所有类型邮件件的总成本（包括保险费）。`InsuredMail`就是这样一个类。它有些不寻常，因为它既继承了`Mail`，又有一个类型为`Mail`的实例变量。`InsuredMail`的构造函数将该实例变量设置为一个`Mail`对象，该对象作为参数传递给构造函数。传递给构造函数的第二个参数是保险金额（美元）：

```java
public InsuredMail(Mail piece, int amount)
```

`InsuredMail`的`calculatePostage`方法返回邮件件的普通邮资（由`InsuredMail`对象的实例变量`piece`表示）与保险费之和。后者仅取决于保险金额：每 100 美元或任何不足 100 美元的保险金额费用为 $0.50。例如：

```java
System.out.println(piece);
```

显示：

```text
4.05
```

然后：

```java
Mail insured = new InsuredMail(piece, 350);
System.out.println(insured);
```

应该显示：

```text
6.05
```

即 4.05 + 4 * 0.50。

编写一个`InsuredMail`类的完整定义。

### 4.

此题涉及的任务是在给定列表中找到出现频率最高的值。例如，我们取一个文本（表示为单词列表），并找到一个在该文本中出现次数比任何其他单词都频繁的单词。我们将使用`ArrayList<String>`来表示单词列表。假设下面讨论的所有方法都属于同一个类。

#### (a)

编写一个`countHits`方法，统计给定单词在单词列表中出现的次数并返回该计数。

在下方完成`countHits`方法。

```java
// 返回 word 在 text 中出现的次数
public static int countHits(ArrayList<String> text, String word)
```

#### (b)

编写一个`mostFrequent`方法，返回在单词列表中出现频率最高的单词。如果列表中存在多个单词的出现次数与最高频率单词相同（均为最大），你必须在适当的地方调用部分 (a) 中的`countHits`方法。假设`countHits`按照说明工作，无论你在对 (a) 部分的解决方案中写了什么。

```java
// 返回在 text 中出现频率最高的单词
// 如果多个单词在 text 中的出现频率相同，
// 则返回它们中的任意一个
public static String mostFrequent(ArrayList<String> text)
```

#### (c)

当你调用在 (b) 部分编写的`mostFrequent(text)`方法时，字符串比较的总共执行了几次？用`n = text.size()`表示你的答案。假设`countHits(list, word)`执行`list.size()`次字符串比较，无论你在部分 (a) 中写了什么。

#### (d)

事实证明，在特殊情况下，存在一种寻找列表中最高频单词的更高效的算法，即最高频单词在列表中出现的次数超过`n/2`次，其中`n = text.size()`。该算法工作如下：

1. 如果`n <= 2`，返回列表中的第一个值。
2. 如果`n`是奇数，测试该单词在列表中出现的次数。如果次数超过`n/2`，则找到了该单词。
3. 将列表配对。现在创建一个新列表：对于每一对相同的单词，将其加入新列表。注意，由于`countHits`按照说明工作，为了避免代码重复，请编写一个实现上述算法的`mostFrequent`方法。假设`countHits`按照说明工作。

## 9.

下列哪项不是在程序中使用注释的良好理由？

- (A) 记录程序员的姓名和最后修改日期
- (B) 记录方法正确运行所需的条件
- (C) 记录类的方法是私有的（private）
- (D) 描述方法的参数
- (E) 解释一段复杂的代码

## 10.

下面代码段执行的结果是什么？

```java
ArrayList<String> xyz = new ArrayList<String>();
xyz.add("X");
xyz.add("Y");
xyz.add("Z");

int count = 0;
for (String s1 : xyz) {
    for (String s2 : xyz) {
        if (s1.equals(s2)) {
            count++;
        }
    }
}
System.out.print(count);
```

- (A) 语法错误
- (B) 显示 0
- (C) 显示 1
- (D) 显示 3
- (E) 空指针异常（`NullPointerException`）

## 11.

关于 Java 的平台无关性，下列哪些是正确的？

I. `int`变量使用的字节数在任何计算机上都是相同的。

II. Java 源代码被编译成字节码，这些字节码可以在任何安装了 Java 虚拟机（JVM）的计算机上运行。

III. 无论 Java 程序运行在哪个平台，算术运算中的溢出发生在相同的值。

- (A) 仅 I



- (B) 仅 II
- (C) I 和 II
- (D) II 和 III
- (E) I、II 和 III

## 12. 假设有一个类 `Particle` 定义了以下变量：

```java
public class Particle {
    public static final int START_POS = 100;
    private double velocity;

    /* 其他未显示的代码 */
}
```

下列哪项是正确的？

- (A) `velocity` 可以作为参数传递给 `Particle` 的方法，但 `START_POS` 不行。
- (B) Java 语法规则不允许我们使用 `START_POS` 代替 `START_POS`。
- (C) 在 `Particle` 的某个方法中使用语句`double pos = START_POS + velocity;`将导致语法错误。
- (D) Java 语法规则不允许我们将 `velocity` 设置为 public（公共）。
- (E) 在 `Particle` 的某个方法中使用语句`START_POS += velocity;`将导致语法错误。

## 13. 下面代码段的输出是什么？

```java
String s = "ban";
ArrayList<String> words = new ArrayList<String>();
words.add(s);
words.add(s.substring(1));
words.add(s.substring(1,2));
String w = "";
for (int k = 0; k < words.size(); k++) {
    w += words.get(k);
}
System.out.print(w.indexOf("an"));
```

- (A) 1
- (B) 2
- (C) 3
- (D) ana
- (E) banana

## 14. 考虑以下代码段，其目的是在 `int[] a` 中查找整数值 `targetValue` 的位置：

```java
int i = 0, position;
while (a[i] != targetValue)
{
    i++;
}
position = i;
```

这段代码在什么时候有效？

- (A) 仅当 `0 <= targetValue < a.length` 时
- (B) 仅当 `targetValue == a[0]` 时
- (C) 仅当对于某个 `i（0 <= i < a.length）`，满足 `targetValue == a[i]` 时
- (D) 仅当对于任何 `i（0 <= i < a.length）`，`targetValue` 均 != `a[i]` 时
- (E) 始终有效

## 15. 给定两个 `String` 变量 `str1` 和 `str2`，下列哪个条件正确地测试了 `str1` 的值大于或等于 `str2` 的值（按字典序）？

- (A) `str1.compareTo(str2) == true`
- (B) `str1.compareTo(str2) >= 0`
- (C) `str1 >= str2`
- (D) `str1.equals(str2) || str1.compareTo(str2) == 1`
- (E) `str1.length() > str2.length() || str1 >= str2`

## 问题 16-17 参考下面的 `smile` 方法：

```java
public static void smile(int n) {
    if (n == 0)
        return;
    for (int k = 1; k <= n; k++)
        System.out.print("smile!");
    smile(n-1);
}
```

### 16. 调用 `smile(4)` 时，输出是什么？

- (A) smile!
- (B) smile!smile!
- (C) smile!smile!smile!
- (D) smile!smile!smile!smile!
- (E) smile!smile!smile!smile!smile!smile!smile!smile!smile!

### 17. 调用 `smile(4)` 时，`smile` 实际上被调用了多少（包括初始调用）？

- (A) 2
- (B) 3
- (C) 4
- (D) 5
- (E) 10

## 18. 考虑 `ClassX` 中的以下方法：

```java
private int modXY(int x, int y)
{
    r = x / y;
    return x % y;
}
```

如果 `ClassX` 编译无错误，下列哪个说法正确？

- I. `modXY` 有副作用，因为 `r` 不是局部变量。
- II. `r` 必须是实例变量（instance variable）。
- III. `r` 的类型必须是 `double`。

- (A) 仅 I
- (B) 仅 II
- (C) 仅 III
- (D) I 和 II
- (E) 无

## 19. 下面代码段的输出是什么？

```java
double pi = 3.14159;
int r = 100;
int area = (int) (Math.pow(r, 2));
System.out.println(area);
```

- (A) 30000
- (B) 31415
- (C) 1459
- (E) 取决于特定系统

## 20. 考虑以下三个代码段：

### I.

```java
int i = 1;
while (i <= 10)
{
    System.out.print(i + " ");
    i += 2;
}
```

### II.

```java
for (int i = 0; i < 5; i++)
{
    System.out.print(2*i + " ");
}
```

### III.

```java
for (int i = 0; i < 10; i++)
{
    i++;
    System.out.print(i + " ");
}
```

三个代码段中哪些产生相同的输出？

- (A) 仅 I 和 II
- (B) 仅 II 和 III
- (C) 仅 I 和 III
- (D) I、II 和 III
- (E) 三者都不同

## 21. `Salsa` 和 `Swing` 实现 `Dance`。如果调用 `perform(new Salsa());` 和 `perform(new Swing());` 都是有效的，下列哪些可以作为 `perform(s)` 的定义？

### I. 两个方法：

```java
public void perform(Salsa dance) { /* 代码未显示 */ }
public void perform(Swing dance) { /* 代码未显示 */ }
```

### II.

```java
public void perform(Dance dance) { /* 代码未显示 */ }
```

### III.

```java
public void perform(Object dance) { /* 代码未显示 */ }
```

- (A) 仅 I
- (B) 仅 II
- (C) 仅 I 和 II
- (D) 仅 II 和 III
- (E) I、II 和 III

## 22. 考虑以下类定义：

```java
public class Country {
    public String toString() { return "Country"; }
}

public class Brazil extends Country {
    public String toString() { return "Brazil"; }
}
```

下面代码段的输出是什么？

```java
Country country1 = new Country();
Country country2 = new Brazil();
System.out.print(country1 + " " + country2 + " ");
country1 = country2;
System.out.print(country1);
```

- (A) Country Country Brazil
- (B) Country Country Brazil
- (C) Country Brazil Country
- (D) Brazil Brazil Brazil
- (E) Brazil Brazil Brazil

## 23. 考虑以下缺少两个的方法：

```java
// 返回 前 n 个元素中所有正奇数的和
// 前提条件：1 < n <= arr.length
public static int addPositiveOddValues(int[] arr, int n)
{
    int sum = 0;
    <statement1>
    <statement2>
        sum += arr[i];
    }
    return sum;
}
```

下列哪些是 `<statement1>` 和 `<statement2>` 的适当替换，使得方法按照说明工作？

- (A) `for (int i = 1; i < n; i += 2) if (arr[i] > 0)`
- (B) `for (int i = 0; i < n; i++) if (arr[i] > 0 && arr[i] % 2 != 0)`
- (C) `for (int i = 1; i <= n; i += 2) if (arr[i] > 0)`
- (D) `for (int i = 0; i <= n; i++) if (arr[i] % 2 != 0)`
- (E) 以上都不是

## 24-29. 参考 GridWorld 研究的代码。

### 24. 如果网格中正有一个 `Flower`，`Bug` 如何表现？

- (A) `Bug` 从网格中移除。
- (B) `Bug` 保持当前状态——不采取行动。
- (C) `Flower` 被移除，`Bug` 向前移动，并在旧位置放置一个新 `Flower`。
- (D) `Bug` 旋转 180 度。
- (E) `Bug` 向右旋转 45 度。

### 25. 考虑以下方法：

```java
// 如果 bug 前方的位置包含 Rock，则返回 true；
// 否则返回 false。
public boolean locInFront(Bug bug) {
    GridActor gr = bug.get();
    if (gr == null)
        return false;
    Location loc = bug.getLocation();
    Location next = <expression1>;
    if (!gr.isValid(next))
        return false;
    return <expression2>;
}
```

下列哪些可以替换 `<expression1>` 和 `<expression2>`，使方法按照说明工作？

- (A) `<expression1>`: `loc.getAdjacentLocation(Location.AHEAD)`

  `<expression2>`: `gr.get(next).equals(Rock)`

- (B) `<expression1>`: `loc.getLocationToward(Location.AHEAD)`

  `<expression2>`: `gr.get(next).equals(Rock)`

- (C) `<expression1>`: `loc.getLocationToward(bug.getDirection())`

  `<expression2>`: `gr.get(next).equals(Rock)`

- (D) `<expression1>`: `loc.getAdjacentLocation(Location.AHEAD)`

  `<expression2>`: `gr.get(next) instanceof Rock`

- (E) `<expression1>`: `loc.getAdjacentLocation(bug.getDirection())`

  `<expression2>`: `gr.get(next) instanceof Rock`

### 26. 假设 `grid` 和 `location` 是 `Actor` 类中的实例字段。在 `Actor` 的 `putSelfInGrid` 方法中：

```java
public void putSelfInGrid(Grid<Actor> gr, Location loc)
{
    if (gr != null)
        throw new IllegalStateException(
            "This actor is already contained in a grid.");

    < missing code >
    grid = gr;
    location = loc;
}
```

以下哪项可以替换 `<missing code>`？

### I.

```java
Actor actor = gr.get(loc);

if (actor != null)
    actor.removeSelfFromGrid();

gr.put(loc, this);
```

### II.

```java
gr.remove(loc);
gr.put(loc, this);
```

### III.

```java
gr.put(loc, this);
```

- (A) 仅 I
- (B) 仅 II
- (C) I 和 II
- (D) II 和 III
- (E) I、II 和 III

### 27. 假设我们将 `Actor` 类中的 `act` 方法替换为空方法（只有大括号，没有代码），并从 `Rock` 中删除 `act` 方法。这会对 `BugRunner` 程序产生什么影响？

- (A) 程序将像以前一样运行，没有任何变化。
- (B) 程序将像以前一样运行，但如果将 `Actor` 对象添加到网格，它们将不会翻。
- (C) `Rock` 类将无法编译。
- (D) `Bug` 可能会移动到被 `Rock` 占据的区域。
- (E) `Critter` 的 `processActors` 方法将不再按照说明工作。

### 28. 更改 `Critter` 类的设计，将 `getActors` 的调用从 `act` 移动到 `processActors`：

```java
public void act() {
    if (getGrid() == null) {
        return;
    }
    processActors();
    ...
}
public void processActors() {
    ArrayList<Actor> actors = getActors();
    for (Actor a : actors) {
        ...
    }
}
```

新设计与原始设计相比如何？

- (A) 新设计违反了封装性。
- (B) 新设计比原始设计灵活性低，某些重写了 `getActors` 和 `processActors` 的 `Critter` 子类现在也必须重写 `act`。
- (C) 新设计比原始设计灵活性低，因为在原始设计中，`Critter` 的子类可以只重写 `getActors` 方法，而在新设计中是不可能的。
- (D) 新设计比原始设计灵活性低，因为在原始设计中，`Critter` 子类的方法可以调用 `super.getActors`，而在新设计中这行不通。
- (E) 新设计与原始设计一样灵活，并且可能更经济，因为它可能消除了在 `Critter` 的某些子类中重写 `getActors` 的需求。

### 29. 假设 `RockChameleonCritter` 的“行为”与 `ChameleonCritter` 完全一样，但它会将颜色更改为随机选择的紧相邻 `Rock` 的颜色。如果它的邻居中没有岩，则 `RockChameleonCritter` 的颜色保持不变。以下哪种实现 `RockChameleonCritter` 类的方法可行？

### I. 从 `Critter` 派生 `RockChameleonCritter` 并重写 `processActors` 和 `makeMove` 方法

### II. 从 `ChameleonCritter` 派生 `RockChameleonCritter` 并仅重写 `processActors` 方法

### III. 从 `ChameleonCritter` 派生 `RockChameleonCritter` 并仅重写 `getActors` 方法

- (A) 仅 I
- (B) 仅 II
- (C) I 和 II
- (D) II 和 III
- (E) I、II 和 III

## 问题 30-32

问题 30-32 涉及对用于目录系统实现中使用的类和对象的推理。`BookInfo` 类对象表示特定书籍的信息，`LibraryBook` 类对象表示图书馆书架上书籍的副本：



# 计算机科学练习题 A-1

## 题目 30 - 37

### 题目 30

```java
public class BookInfo
{
    private String title;
    private String author;
    private int numPages;

    // ... 未省略构造函数

    public String toString() {
        return title + " " + author;
    }

    public String getTitle() { return title; }
    public int getNumPages() { return numPages; }
}

public class LibraryBook
{
    private BookInfo info;
    private int numCopies; // 书架上的副本数量

    // ... 未省略构造函数

    public int getNumCopies() { return numCopies; }
    public void setNumCopies(int num) {
        numCopies = num;
    }
    public BookInfo getInfo() { return info; }

    // 如果书架上有副本，则减少
    // 剩余的副本数量并返回 true；
    // 否则返回 false
    public boolean checkOut() { /* 代码省略 */ }
}
```

30. 如果 `catalog` 在客户端类中声明为：

```java
LibraryBook[] catalog;
```

以下哪条语句将正确显示目录中第三本书的由作者的标题？

I. `System.out.println(catalog[2]);`  
II. `System.out.println(catalog[2].getInfo());`  
III. `System.out.println(catalog[2].getInfo().toString());`

- (A) 仅 I  
- (B) 仅 II  
- (C) I 和 II  
- (D) I 和 III  
- (E) I, II 和 III  

### 题目 31

以下哪段代码段将正确完成 `Library` 类的 `checkout()` 方法？

I.  
```java
if (getNumCopies() == 0)
    return false;
else {
    setNumCopies(getNumCopies() - 1);
    return true;
}
```

II.  
```java
int n = getNumCopies();
if (n == 0)
    return false;
else {
    setNumCopies(n - 1);
    return true;
}
```

III.  
```java
if (numCopies == 0)
    return false;
else {
    numCopies--;
    return true;
}
```

- (A) 仅 I  
- (B) 仅 II  
- (C) I 和 II  
- (D) I 和 III  
- (E) I, II, 和 III  

### 题目 32

考虑来自 `LibraryBook` 另一个类的以下方法：

```java
// 返回书架上
// catalog 中书籍的总页数
public int totalPages(LibraryBook[] catalog) {
    int count = 0;
    for (LibraryBook bk : catalog) {
        <statement>
    }
    return count;
}
```

以下哪项对 `<statement>` 的替换可以完成该方法？

- (A) `count += bk.numCopies * bk.info.numPages;`  
- (B) `count += bk.getNumCopies() * bk.getInfo().getNumPages();`  
- (C) `count += bk.numCopies * bk.getInfo().numPages();`  
- (D) `count += bk.getNumCopies() * bk.info().getNumPages();`  
- (E) 以上都不是  

### 题目 33

以下方法旨在从 `ArrayList<Integer> list` 中删除值小于零的元素：

```java
public void removeNegatives(ArrayList<Integer> list) {
    int i = 0, n = list.size();

    while (i < n) {
        if (list.get(i) < 0) {
            list.remove(i);
            n--;
        }
        i++;
    }
}
```

该方法适用于哪些 `Integer` 列表？

- (A) 仅空列表  
- (B) 所有包含连续负值的列表  
- (C) 所有负值出现在正值之前的列表  
- (D) 所有正值出现在负值之前的列表  
- (E) 所有列表  

### 题目 34

考虑以下接口和类：

```java
public interface Student
{
    double getGPA();
    int getSemesterUnits();
}

public class FullTimeStudent
    implements Student, Comparable<Student> {
    < required methods>
}
```

为了成功编译 `FullTimeStudent` 类，开发者必须实现的最小方法集是？

- (A) 不需要实现方法  
- (B) `getGPA()`, `getSemesterUnits()`  
- (C) `getGPA()`, `getSemesterUnits()`, `compareTo(Student s)`  
- (D) `getGPA()`, `getSemesterUnits()`, `equals(Student s)`, `toString()`  
- (E) `getGPA()`, `getSemesterUnits()`, `compareTo(Student s)`, `equals(Student s)`, `toString()`  

### 题目 35

以下哪项最能描述方法 `propertyX` 的返回值？

```java
// 前提：v.length >= 2
public boolean propertyX(int[] v) {
    boolean flag = false;
    for (int i = 0; i < v.length - 1; i++) {
        flag = flag || (v[i] == v[i+1]);
    }
    return flag;
}
```

- (A) 如果 `v` 是升序排列的，则返回 `true`，否则返回 `false`  
- (B) 如果 `v` 是降序排列的，则返回 `true`，否则返回 `false`  
- (C) 如果 `v` 有两个相邻元素相同，则返回 `true`，否则返回 `false`  
- (D) 如果 `v` 有两个元素相同，则返回 `true`，否则返回 `false`  
- (E) 如果 `v` 中的所有元素都不同，则返回 `true`，否则返回 `false`  

### 题目 36

考虑以下方法：

```java
// 返回目标值在
// 数组 a 中的位置，如果没有找到则返回 -1
// 前提：a[0] ... a.length-1]
// 是升序排列的
public static int search(int[] a, int target) {
    int first = 0;
    int middle;
    int last = a.length - 1;

    while (first <= last) {
        middle = (first + last) / 2;
        if (target == a[middle])
            return middle;
        else if (target < a[middle])
            last = middle;
        else
            first = middle;
    }
    return -1;
}
```

该方法在某些情况下无法预期工作。如果数组有五个值为 `3` `4` `35` `42` `51` 的元素，以下哪个 `target` 值会导致该方法失效？

- (A) `3`  
- (B) `4`  
- (C) `35`  
- (D) `42`  
- (E) `51`  

### 题目 37

Brad 从库类 `JPanel` 派生了自己的类。`JPanel` 的 `paintComponent` 方法在面板中显示空白图片。Brad 重新定义了 `JPanel` 的 `paintComponent` 以显示他自己的图片。Brad 的类无错误地编译，但当他运行程序时，在这种情况下哪种假设可能是正确的？

- (A) Brad 在方法名中漏掉了 "`paintComponent`"。  
- (B) Brad 为他的 `paintComponent` 方法指定了错误的返回类型。  
- (C) Brad 为其 `paintComponent` 方法中的参数选择了错误的类型。  
- (D) Brad 为他的 `paintComponent` 方法指定了两个参数，而 `JPanel` 的 `paintComponent` 只需要一个参数。  
- (E) Brad 的 `paintComponent` 代码中存在逻辑错误，导致无法生成图片。

## 题目 38 - 40

问题 38-40 参考了以下 `SortX` 类：

```java
public class SortX {
    public static void sort(String[] items) {
        int n = items.length;
        while (n > 1) {
            sortHelper(items, n - 1);
            n--;
        }
    }
    private static void sortHelper(String[] items, int first, int last) {
        int m = last;
        for (int k = 0; k < last; k++) {
            if (items[k].compareTo(items[m]) > 0) {
                m = k;
            }
        }
        String temp = items[m];
        items[m] = items[last];
        items[last] = temp;
    }
}
```

### 题目 38

`sort` 方法实现的排序算法描述为：

- (A) 选择排序 (Selection Sort)  
- (B) 插入排序 (Insertion Sort)  
- (C) 快速排序 (Quicksort)  
- (D) 合并排序 (Mergesort)  
- (E) 错误的算法实现

### 题目 39

假设 `names` 是一个字符串对象数组：

```java
String[] names = {"Dan", "Alice", "Claire", "Evan", "Boris"};
```

如果 `SortX.sort(names)` 运行 `while` 循环两次后，`names` 中值的顺序是：

- (A) `"Boris"`, `"Alice"`, `"Claire"`, `"Dan"`  
- (B) `"Alice"`, `"Claire"`, `"Boris"`, `"Dan"`  
- (C) `"Alice"`, `"Boris"`, `"Claire"`, `"Dan"`  
- (D) `"Alice"`, `"Claire"`, `"Dan"`, `"Boris"`  
- (E) 以上均不是

### 题目 40

如果 `items` 包含五个值并调用了 `SortX.sort(items)`，`items[k].compareTo(items[m])` 被调用了多少次？

- (A) `5`  
- (B) `10`  
- (C) `15`  
- (D) `25`  
- (E) 取决于 `items` 中的值

# 计算机科学练习题 A-2

## SECTION II

时间 — 1 小时  
题目数量 — 4  
总分占比 — 50%

一个停车场由多个层组成，每层都有许多停车位。停车场管理程序跟踪停车场内停放车辆的数量，并帮助查找指定 ID 的车辆。考虑此程序中使用的三个 Java 类：

```java
public class Car
{
    // 返回 Car 的 id
    public String getID() { /* 未实现 */ }

    // ... 私有数据、构造函数和其他方法
    // 未实现
}
```

`ParkingLevel` 类代表停车场的一层。停车位从 0 开始连续编号。

```java
public class ParkingLevel
{
    // 返回该层的停车位数量
    public int numSpaces() /* 未实现 */;

    // 返回停在 spaceNum 位置的车辆，或者如果该位置为空则返回 null
    public Car getCar(int spaceNum) /* 未实现 */;

    // 返回最小可用空位编号，如果层已满则返回 -1
    public int findEmptySpace() /* 未实现 */;

    // 将该层的 spaceNum 位置标记为被 Car v 占用；如果 v == null 则将该位置标记为空
    // 前提条件：spaceNum 是空的
    public void setCar(int spaceNum, Car v) /* 未实现 */;

    // ... 私有数据、构造函数和其他方法
    // 未实现
}
```

`ParkingLevel` 对象跟踪车位内停放的车辆以及空位。`ParkingGarage` 类跟踪停车场所有的层。它使用 `ParkingLevel` 对象数组存储层的信息。

```java
public class ParkingGarage {
    private int totalCars;
    // 停车场中的车辆总数

    private ParkingLevel[] levels;
    // 每个元素对应停车场的一层

    public boolean isFull() {
        // 如果停车场内任何层都没有空位，返回 true；否则返回 false
        /* 在部分 (a) 实现 */
    }

    public boolean isCarParked(String id) {
        // 如果停车场内已有该 ID 的车辆，返回 true；否则返回 false
        /* 已实现 */
    }

    public boolean parkCar(Car v) {
        // 如果停车场未满且内没有相同 ID 的车辆，
        // 将 v 停入停车场，更新停车场内车辆数量并返回 true；
        // 否则返回 false。
    }

    public Car removeCar(String id) {
        // 如果找到了指定 ID 的车辆，移除该车辆，
        // 更新停车场内车辆数量并返回该车辆；
        // 否则返回 null
        /* 在部分 ( ) 实现 */
    }

    // ... 私有数据、构造函数和其他方法
    // 未实现
}
```

### (a) 编写 `ParkingGarage` 的 `isFull` 方法

如果停车场内任何层都没有空位，则返回 `true`；否则返回 `false`。在下方完成 `isFull`：

```java
// 如果停车场内任何层都没有空位，返回 true；否则返回 false
public boolean isFull()
```

### (b) 编写 `ParkingGarage` 的 `parkCar` 方法

如果停车场未满且内没有相同 ID 的车辆，将 `v` 停入停车场，更新停车场内车辆数量并返回 `true`；否则返回 `false`。在下方完成 `parkCar`：

```java
// 如果停车场未满且内没有相同 ID 的车辆，
// 将 v 停入停车场，更新停车场内车辆数量
// 并返回 true；否则，方法返回 false
public boolean parkCar(Car v)
```

### (c) 编写 `ParkingGarage` 的 `removeCar` 方法

如果找到了指定 ID 的车辆，移除该车辆，更新停车场内车辆数量并返回该车辆；否则返回 `null`。在下方完成 `removeCar`：

```java
// 如果找到了指定 ID 的车辆，移除
// 该车辆，更新停车场内车辆数量
// 并返回该车辆；否则，
// 方法返回 null
public Car removeCar(String id)
```

### (d) 编写 `HTMLProcessor` 类的 `removeAllTags` 方法

该方法仅处理 HTML 标签的一个集：它假设给定文本仅包含完整的简单标签，例如 `<a>` 和 `</a>` 或 `<cite>` 和 `</cite>`，其中结束标签与对应的起始标签的区别在于 `<` 之后有一个 "/"字符。结束标签必须在起始标签之后。该方法返回删除所有标签后的文本（如果没有找到标签，则返回原始文本）。然而，如果标签不匹配（在起始标签后没有找到结束标签），该方法应返回字符串 `"Error"`。你可以假设 `remove` 和 `findFirstTag` 方法按照规范工作，无论你在第 (a) 和 (b) 部分写了什么内容。

在下方完成 `removeAllTags` 方法：

```java
// 返回删除所有标签后的文本；
// 如果标签不匹配，返回 "Error"
public String removeAllTags(String text)
```



```java
// 如果 text 中的所有 HTML 标签都是成对的开启-闭合
// 对，则返回一个删除了 text 中所有标签的新文本字符串；
// 如果 text 没有标签，返回原始字符串；
// 如果标签不匹配，返回 "Error"
// 前提条件：text 是 HTML 文本段，可能包含
// 完整的 HTML 标签
public static String removeAllTags(String text)
```

# 236 模拟考试 ~ A-2

3. 本题涉及对 GridWorld 案例研究的代码进行推理。考试的一部分提供了代码的副本。

在第 (a) 部分，你将设计一个`Dahlia`类，它是`Flower`类的子类。在第 (b) 和 (c) 部分，你将实现`Dahlia`的构造函数和`act`方法。`Dahlia`最初表现像普通的`Flower`，但在某一点成熟后，它会产生新`Dahlia`的种子并死亡。它可以有不同的颜色。特定颜色的`Dahlia`产生的种子随后会“生长”成相同色的`Dahlia`。你对`Dahlia`类的实现必须使得`Flower`类实现细节的任何更改（例如默认颜色或颜色加深公式）都能自动应用于`Dahlia`，而无需更改其源代码。

- (a) 将`Dahlia`类设计为`Flower`的子类。为构造函数和方法定义必要的实例字段和写入器——**不要**在题目的此部分实现它们。`Dahlia`跟踪它的年龄（调用`act`方法的次数）。它在构造时还会保存其初始颜色，以便将颜色传递给它的种子。提供以下功能：

  - 用于存储`Dahlia`年龄和初始颜色的实例字段。

  - 两个构造函数，类似于`Flower`的构造函数（将在第 (b) 部分实现）。

  - `act`方法（将在第 (c) 部分实现）。

  - 确保你的设计符合封装和代码复用的原则。

画出`Dahlia`类的草图，包括字段以及构造函数和方法的头部。你**不需要**编写任何 import 语句。

- (b) 为`Dahlia`类编写两个构造函数。使用“无参数”构造函数（不接受参数的构造函数）的`Dahlia`应该获得与`Flower`默认相同的相同的。（假设你不知道颜色在`Flower`中是如何定义的。）接受一个`Color`类型参数的构造函数将该`Dahlia`的初始颜色设置为给定颜色。两个`Dahlia`构造函数都应该确保初始颜色存储在后续用于生成种子的实例字段中。

- (c) 编写`Dahlia`类的`act`方法。在前的前几个“周”（前三次调用`act`），`Dahlia`表现像普通的`Flower`。`Dahlia`产生三个种子并尝试将它们每一个放入网格中。然后它死亡。`Dahlia`尝试将每个种子（一个`DahliaSeedObject`）放置在随机选择的位置。如果该位置被任何其他角色（之前放置的种子）占用，则尝试是徒劳的，种子不会被放置。假设`DahliaSeed`类已提供，并且它有一个构造函数，接受颜色作为参数。`Dahlia`应该将它的初始颜色传递给该构造函数。

4. 考虑代表学生参加 AP 考试的`APExam`类：

```java
public class APExam {
    private String subject;
    // 考试科目名称

    private int grade;
    // 考试成绩：从 1 到 5

    public APExam(String subj, int gr) {
        subject = subj;
        grade = gr;
    }

    public String getSubject() { return subject; }
    public int getGrade() { return grade; }
}
```

`APStudent`类代表学生参与 AP 计划的情况。一个`APStudent`对象持有学生的姓名和该学生参加的所有 AP 考试的列表。考试列表由`ArrayList<APExam>`表示。该类应该有一个构造函数，接受学生姓名作为参数，并将考试列表初始化为空列表。该类提供了访问姓名和考试列表的访问器方法，一个向列表添加 AP 考试的方法，以及一个返回学生在所有考试中平均分的方法。

(a) 为`APStudent`编写一个类定义，仅在其构造函数和方法的体部写写“`...`”。在编写此定义时，你必须：

- 为方法、数据字段和参数选择合适的名称；

- 提供上述指定的功能；

- 使数据表示与上述规范一致；

- 做出符合信息隐藏原则的设计决策。

不需要编写注释，但如果需要，可以使用注释。

**不要**编写`APStudent`类构造函数或方法的实现代码。

(b) 大学理事会（College Board）为成绩在 3 分或以上的学生颁发 AP Scholar 奖。大学理事会还为在四门考试中均为 3 分或以上且所有考试平均分至少 3.25 分的学生颁发 AP Scholar with Honor 奖。

| 最低成绩 | AP Scholar | AP Scholar with Honor |

| :--- | :--- | :--- |

| 考试数量 | 3 | 4 |

| 所有考试平均分 | 3 | 3.25 |

编写`APSolar`类的完整定义，作为`APStudent`的子类。`APSolar`具有相同的特征。它应该有一个接受一个参数（姓名的构造函数。`APSolar`类还有一个`getLevel`方法，返回学生获得的等级：0 代表无奖，1 代表 AP Scholar，2 代表 AP Scholar with Honor。你可以假设你在 (a) 部分设计的`APStudent`的方法按照规范工作。

(c) 假设`APStats`类跟踪考试统计。编写`APStats`的`getStats`方法，接受一个`APSolar`对象列表并计算无奖、AP Scholar 和 AP Scholar with Honor 的比例。例如，如果列表包含 10 个学生，其中 6 人无奖，3 人是 AP Scholar，1 人是 AP Scholar with Honor，则`getStats`返回一个包含 60.0、30.0 和 10.0 的数组。在编写`getStats`时，假设 (a) 和 (b) 部分的类按照规范工作。

在下方完成`getStats`方法。

```java
// 返回一个长度为 3 的数组；
// percents[0], percents[1] 和 percents[2] 分别设置为
// 列表中无奖、AP Scholar 和 AP Scholar with Honor 学生的百分比
// 前提条件：list.size() > 0
public static double getStats(ArrayList<APScholar> list)
```

A-3 计算机科学 A

第一部分

时间 — 1 小时 15 分钟

题目数量 — 40

占总分百分比 — 50%

+ 1. 下面程序段的输出是什么？

```java
int num = 5;
while (num >= 0)
{
num -= 2;
}
System.out.print(num);
```

(A) -2

(B) -1

(C) 0

(D) 2

(E) 21

+ 2. 假设 x 和 y 是 int 变量，表达式

`!(x > y && y <= 0)`

等价于以下哪一个？

(A) `!(x <= y) || (y > 0)`

(B) `x > y && y <= 0`

(C) `x <= y || y > 0`

(D) `x > y || y < 0`

(E) `x <= y && y <= 0`

3. 下列哪项描述了以下方法的返回值？

```
// 前提条件：amt 代表正值的美元值
// 和分值（例如，1.15 代表
// 1美元15美分）
private int process(double amt)
{
    return (int)amt * 100 + 0.5) % 100;
}
```

- (A) amt 中的分分部分

- (B) amt 中的整数美元数量

- (C) 转换为分后的 amt

- (D) 四舍五入到最近整数的 amt

- (E) 截断到最近整数的 amt

4. 下面代码段的输出是什么？

```
int sum = 0, d = -1;
for (int count = 10; count > 0; count--)
{
    sum += d;
    if (d > 0)
        d++;
    else
        d--;
    d = -d;
}
System.out.println(sum);
```

- (A) 0

- (B) 5

- (C) -5

- (D) 10

- (E) -10

5. 下面代码段应该计算并显示 1 + 2 + . . + 20:

```
int count = 0, sum = 0;
while (count < 20)
{
    sum += count;
}
System.out.println(sum);
```

哪种陈述最能描述结果：

- (A) 显示的总和将是正确的。

- (B) 显示的总和将小 20。

- (C) 输出将是数字 0。

- (D) 输出将是数字 20。

- (E) 将没有输出，因为程序进入了死循环。

6. 考虑以下类：

```
public class Rectangle implements Comparable<Rectangle>
{
    private int width, height;

    public Rectangle(int w, int h) { width = w; height = h; }
    public int getHeight() { return height; }
    public int getWidth() { return width; }
    public int getArea() { return width * height; }

    // ... 其他未显示的方法
}
```

假设该类实现了`Comparable<Rectangle>`接口，其方式是根据面积比较`Rectangle`对象：面积较小的矩形被认为较小。必须提供哪一个`compareTo`方法？

- (A)

```
public boolean compareTo(int area)
{
    return getArea() < area;
}
```

- (B)

```
public int compareTo(int area)
{
    return getArea() - area;
}
```

- (C)

```
public int compareTo(Object other)
{
    return getArea() - other.getArea();
}
```

- (D)

```java
public boolean compareTo(Rectangle other)
{
    return getArea() < other.getArea();
}
```

- (E)

```java
public int compareTo(Rectangle other)
{
    return getArea() - other.getArea();
}
```

7. 下列哪一个布尔表达式正确地实现了两个 String 对象 str1 和 str2 的相等性比较，并且当仅当 str1 和 str2 持有相同值时结果为真？

I. `str1 == str2`

II. `str1.equals(str2)`

III. `str1.compareTo(str2) == 0`

- (A) 仅 I

- (B) 仅 II

- (C) I 和 II

- (D) II 和 III

- (E) I, II, 和 III

8. 下面代码段的输出是什么？

```
int a = 3;
int b = 4;
int c = 0;

if (a == b && b/c == 1) {
    c = a * b;
}
else {
    c = a + b * c;
    System.out.println(c);
}
```

- (A) 运行时除以零

- (B) 0

- (C) 3

- (D) 6

- (E) 12

9. 关于重载方法的以下陈述中哪项是错误的？

- (A) 重载方法必须全都是公有的或全是私有的。

- (B) 重载方法定义在同一个类中并具有相同的名称。

- (C) 重载方法可以具有相同数量的参数。

- (D) 其中重载方法可以不带参数。

- (E) 重载方法不能仅根据为参数选择的名称进行区分。

## 10. 考虑以下类：

```
public class Sphere {
    public static final double pi = 3.14159;
    public static double volume(int r) {
        return 4 / 3 * pi * Math.pow(r, 3);
    }
}
```

关于这段代码的以下陈述哪项是正确的？

- (A) 该类无法编译，因为没有定义构造函数。

- (B) 该类无法编译，因为 pi 不能声明为 public。

- (C) 该类无法编译，因为 volume 方法被声明为 static。

- (D) `Math.pow(r, 3)`不能使用，因为 r 是 int。

- (E) 该类编译无错误，但 volume 方法返回的值比预期值小得多。

## 11. 考虑以下方法：

```
// 前提条件：a != null; a.length > 0
private static void doIt(double[] a) {
    double temp;
    for (int k = 0; k < a.length / 2; k++) {
        temp = a[k];
        a[a.length - 1 - k] = temp;
    }
}
```

下列哪项最能描述该方法的任务？

- (A) 升序排序数组

- (B) 降序排序数组

- (C) 交换数组的第一个元素和最后一个元素

- (D) 反转数组的顺序

- (E) 以上任务均正确实现。

 12. 考虑以下方法：

```
public String filter(String str, String pattern)
{
    int pos = str.indexOf(pattern);
    if (pos == -1)
        return str;
    else
        return str.substring(0, pos);
}
```

`System.out.println(filter("papaya", "aya"));`输出是什么？

- (A) p

- (B) ya

- (C) aya

13. 考虑以下代码段：

```
int n = 0;
while (n >= 2) {
    n = n / 2;
}
System.out.println(n);
```

下列哪项是输出？

- (A) 0

- (B) -1

- (C) 0, 1

14. 下列哪些测试建议是不好的？

- (A) 测试可能的值。

- (B) 测试大型程序时，单独测试。

- (C) 如果可能，使用自动化测试。

- (D) 设计尽可能多的测试数据。

- (E) 测试边界以检查“差一”错误。

15. Whitney 程序员编写了以下方法，旨在生成 "2 4 6 "：

```
public void cheer(int i)
    if (i != 8) {
        i = i + 2;
        cheer(i);
        System.out.print(i + " ");
    }
    else {
        System.out.print("!");
    }
```

然而，当她调用`cheer(0)`时，该方法不起。为了得到正确的 cheer，

- (A) 将第 1 行的`(i != 8)`替换为`(i <= 8)`

- (B) 将第 1 行的`(i != 8)`替换为`(i == 8)`

- (C) 将第 1 行的`(i != 8)`替换为`while (i != 8)`

- (D) 交换第 4 行和第 5 行

- (E) 将第 3 行移动到第 5 行

16. 调用以下方法时会显示什么？

```
public void splat(String s)
{
    if (s.length() < 8)
        splat(s + s);
    System.out.println(s);
}
```

- (A) **

- (B) ****

- (C) ******

- (D) ****** **

- (E) ****** ****

问题 17-18 指以下 sortX 方法：

```
public void sortX(int[] a) {
    for (int i = 1; i < a.length; i++) // 第 1 行
    {
        int current = a[i]; // 第 2 行
        int j = 0; // 第 3 行
        while (a[j] < current) {
            j++; // 第 5 行
            for (int k = i; k > j; k--) // 第 6 行
                a[k] = a[k-1]; // 第 7 行
            }
            a[j] = current; // 第 8 行
        }
    }
}
```

17. sortX 方法实现的排序算法最好描述为：

- (A) 选择排序

- (B) 插入排序

- (C) 快速排序



- (D) 合并排序
- (E) 排序算法实现错误

18. 给定

```
int[] a = {24, 16, 68, 56, 32};
```

当`sortX`的第 8 行语句执行第二次后，结果是什么？

- (A) `a`的值为 {16, 24, 68, 56, 32}
- (B) `a`的值为 {16, 24, 32, 56, 68}
- (C) `a`的值为 {24, 16, 32, 56, 68}
- (D) 代码在第 4 行抛出数组越界异常
- (E) 代码在第 8 行抛出数组越界异常

19. 考虑以下类：

```java
public class BuddyList {
    private ArrayList<String> buddies; // 包含伙伴的名称
    // ... 未省略的构造函数和其他方法和变量
    public ArrayList<String> getBuddies() { return buddies; }
}
```

如果在其他类中声明并初始化了`BuddyList myFriends`，那么作为`BuddyList`的客户端，以下哪项正确地将`myFriends`列表中第一个伙伴的名字赋值给`name`？

- I. `String name = myFriends.buddies[0];`
- II. `String name = myFriends.buddies.get(0);`
- III. `String name = myFriends.getBuddies().get(0);`

(A) 仅 I  
(B) 仅 II  
(C) 仅 III  
(D) I 和 II  
(E) II 和 III

20. `Playlist`类提供了一些允许你表示和操作曲目列表的方法，但你并不关心这些操作是如何工作的，或者列表是如何存储在内存中的。你只如何初始化和使用`Playlist`对象，并且无法直接访问`Playlist`类的实现或其私有数据字段。这是这是一个示例：

(A) 封装 (encapsulation)  
(B) 重写 (overriding)  
(C) 继承 (inheritance)  
(D) 多态 (polymorphism)  
(E) 方法重载 (method overloading)

21. 关于构造函数的以下陈述何不正确？

(A) 所有构造函数的名称必须与它们所在的类名相同。  
(B) 构造函数的返回类型必须声明为`void`。  
(C) 类可以有一个无参数的构造函数。  
(D) 当程序使用`new`运算符创建对象时，会调用构造函数。  
(E) 子类的构造函数可以使用 Java 留关键字`super`调用其父类的构造函数。

22. 考虑以下方法，该方法意图使用二分查找找到`target`在`ArrayList a`中的位置：

```java
public int findLocation(ArrayList<String> a, String target)
{
    int first = 0, last = a.size() - 1;
    while (first <= last){
        int middle = (first + last) / 2;
        int compResult = target.compareTo(a.get(middle));
        if (compResult == 0)
            return middle;
        if (compResult < 0)
            last = middle - 1;
        else
            first = middle + 1;
    }
    return -1;
}
```

如果该方法应用于一个未排序的列表，它可能会失败。对于以下哪个列表，`findLocation(a, "C")`返回 -1？

(A) "A", "B", "D", "C", "E", "F", "G"  
(B) "G", "E", "C", "D", "G", "B", "A"  
(C) "A", "C", "D", "G", "E", "B", "F"  
(D) "B", "A", "D", "C", "F", "E", "G"  
(E) "D", "F", "E", "A", "G", "C", "E"

问题 23 和 24 参考以下类：

```java
public class Sample
{
    private double[] amps;

    public Sample(int n) { < missing statements > }
    public double get(int k) { return amps[k]; }
}
```

### 23. 以下哪个代码段可以替换`Sample`构造函数中的`<missing statements>`，以便它初始化`amps`包含`n`个值，并用随机值`0.0 <= amps[i] < 1.0`填充它们？

(A)

```java
amps = new double[n];
```

(B)

```java
amps = new double[n];
for (int k = 0; k < n; k++)
amps[k] = new Random();
```

(C)

```java
amps = new double[n];
for (int k = 0; k < n; k++)
amps[k] = Random.nextDouble();
```

(D)

```java
amps = new double[n];
randGen = new Random();
for (int k = 0; k < n; k++)
amps[k] = randGen.nextDouble();
```

(E)

```java
amps = new Double[n];
randGen = new Random();
for (int k = 0; k < n; k++)
amps[k] = new Double(randGen.nextDouble());
```

### 24. 给出

```java
int size = 100;
sample = new Sample(size);
```

以下哪个语句将`s`中`amps`的最后一个值赋值给`x`？

(A)

```java
double x = s[99];
```

(B)

```java
double x = s.amps[amps.length - 1];
```

(C)

```java
double x = s.get(amps.length - 1);
```

(D)

```java
double x = s.get(size - 1);
```

(E)

```java
double x = s.get[s.length - 1];
```

### 25. 一个项目需要两个相关的类 X 和 Y。程序员决定提供一个抽象类 A，并让 X 和 Y 都派生自 A，而不是互相实现。对于这一决定，以下哪项**不是**一个合理的理由？

(A) 能够在 X 和 Y 中使用某些代码而不产生重复  
(B) 能够将类型 X 的对象转换为类型 Y  
(C) 能够将类型 X 或 Y 作为参数传递给 A 的同一个构造函数  
(D) 能够将 X 和 Y 两种类型放入同一个数组  
(E) 更容易实现另一个复用 A 类代码的类

26. 假设`ArrayList<Integer> numbers`和`ArrayList<String> names`创建如下：

```java
ArrayList<Integer> numbers = new ArrayList<Integer>();
Integer x = new Integer(1);
numbers.add(x);
numbers.add(x);

ArrayList<String> names = new ArrayList<String>();
names.add(0, "Anya");
names.add(0, "Ben");
names.add(0, "Cathy");
```

以下代码的结果是？

```java
for (Integer i : numbers) {
  names.remove(i.intValue());
}
for (String name : names) {
  System.out.print(name + " ");
}
```

(A) Cathy  
(B) Cathy Anya  
(C) Anya Cathy  
(D) IndexOutOfBoundsException  
(E) NoSuchElementException

27. 什么时候一个类必须声明为抽象类（abstract）？

(A) 当类没有构造函数时  
(B) 当类没有方法时  
(C) 当类没有公共或私有变量时  
(D) 当你需要派生另一个类时  
(E) 当类中声明了一个或多个抽象方法时

28. 考虑以下接口 TV 和类 MyTV：

```java
public interface TV {
    void tuneTo(String channel);
}

public class MyTV implements TV {
    private ArrayList<String> myChannels;

    public MyTV(ArrayList<String> channels) {
        /* implementation shown */
    }

    public void tuneTo(int k) {
        /* implementation shown */
    }

    public void tuneTo(int k, String name) {
        /* implementation shown */
    }
}
```

其中有一个或多个错误且无法正常编译。以下哪项最能描述编译器报错？

(A) TV 接口中的`tuneTo`缺少`public`关键字  
(B) MyTV 应该被声明为抽象类；它没有定义`tuneTo(String)`  
(C) MyTV 中`tuneTo`定义了多次  
(D) 在`tuneTo`方法中无法将`int`转换为`String`  
(E) 两个错误：(1) `tuneTo`定义了多次；(2) `tuneTo(int)`方法中无法将`int`转换为`String`

29. 考虑以下代码段：

```java
if (!somethingIsFalse()) {
    return false;
} else {
    return true;
}
```

以下哪种替换会产生相同的结果？

(A) `return true;`  
(B) `return false;`  
(C) `return !somethingIsFalse();`  
(D) `return somethingIsFalse();`  
(E) 以上均不是

30. 考虑以下类定义：

```java
public class Airplane
{
    private int fuel;

    public Airplane() { fuel = 0; }
    public Airplane(int g) { fuel = g; }

    public void addFuel() { fuel++; }
    public String toString() { return fuel + " "; }
}

public class Jet extends Airplane
{
    public Jet(int g) { super(2*g); }
}
```

编译并运行以下代码时的结果是什么？

```java
Airplane plane = new Airplane(4);
Airplane jet = new Jet(4);
System.out.print(plane);
plane.addFuel();
System.out.print(plane);
System.out.print(jet);
jet.addFuel();
System.out.print(jet);
```

(A) 对于`jet.addFuel()`语句报告语法错误 "undefined addFuel"  
(B) 尝试执行`jet.addFuel()`时发生运行时错误`ClassCastException`  
(C) 代码编译并运行无错误，输出为`4 5 5 6`  
(D) 代码编译并运行无错误，输出为`4 5 8 9`  
(E) 代码编译并运行无错误，输出为`8 9 9 10`

31. 程序员想要创建一个交换两个整数值的`swap`方法。以下三种表示值的方法以及对应的方法哪种成功交换了值？

- I. // a 和 b 是表示要交换值的 Integer 对象

```java
public static void swap(Integer a, Integer b)
{
    Integer temp = a; a = b; b = temp;
}
```

- II. // a[0] 和 a[1] 包含要交换的值

```java
public static void swap(int[] a)
{
    int temp = a[0]; a[0] = a[1]; a[1] = temp;
}
```

- III. // a[0] 和 b[0] 包含要交换的值

```java
public static void swap(int[] a, int[] b)
{
    int temp = a[0]; a[0] = b[0]; b[0] = temp;
}
```

(A) 仅 I  
(B) 仅 II  
(C) I 和 II  
(D) II 和 III  
(E) I、II, 和 III

32. 假设一个接口`Solid`指定了`getVolume()`方法。两个类`Cube`和`Pyramid`实现了`Solid`。哪种 Java 特使得以下代码段能够打印出金字塔和立方体的正确体积？

```java
Solid[] solids = new Solid[2];
solids[0] = new Cube(100);
solids[1] = new Pyramid(150, 100);
System.out.println("Cube: " + solids[0].getVolume());
System.out.println("Pyramid: " + solids[1].getVolume());
```

(A) 抽象  
(B) 封装  
(C) 多态  
(D) 平台无关性  
(E) 方法重载

# 模拟考试 ~ A-3

33. 考虑以下代码段：

```java
ArrayList<String> list = new ArrayList<String>();
list.add("One");
list.add("Two");
String[] msg = new String[2];
list.add(msg[0]);
< another statement>
```

关于`< another statement >`，以下选项中哪一个会导致`NullPointerException`？

- (A) `msg[0] = "Three"`
- (B) `msg[0] = list.get(list.size());`
- (C) `if ("!".equals(list.get(2))) msg[0] = "Three";`
- (D) `list.add(2, msg[0]);`
- (E) `msg[1] = msg[0].substring(0, 2);`

34. 一位程序员正尝试在`ArrayList`和标准一维数组之间选择表示表示数据。哪个陈述**不**正确？

- (A) `ArrayList`和标准数组都允许直接访问第 k 个元素。
- (B) 标准数组可以包含基本数据类型的元素，如`int`或`double`；`ArrayList`只能包含对象。
- (C) `ArrayList`可以同时包含不同类型的对象，例如`Integer`和`Double`。
- (D) `ArrayList`有一个方便的方法可以在中间指定的位置插入值。
- (E) 当值的数量超过其大时，`ArrayList`和标准数组都会自动扩展。

问题 35–40 涉及 GridWorld 案例中的代码。

35. 在以下哪些代码段可以编译通过且无错误？

```
I.
BoxBug bb = new BoxBug();
if (!bb.canMove())
bb.turn();

II.
BoxBug bb = new BoxBug(5);
bb.setColor(Color.BLUE);

III.
BoxBug bb = new BoxBug(Color.BLUE);
bb.move();
```

- (A) 仅 I
- (B) 仅 II
- (C) I 和 II
- (D) II 和 III
- (E) I, II, 和 III

36. 假设`loc1`和`loc2`是代表网格中有效位置的`Location`对象，以下哪个选项可以验证`loc2`在`loc1`的北边？

- (A) `Grid.get(loc1, loc2).equals(Location.NORTH)`
- (B) `loc1.getAdjacency(Location.NORTH).equals(loc2)`
- (C) `loc1.getDirectionToward(loc2) == Location.NORTH`
- (D) `loc1.getDirectionToward(loc2).equals(Location.NORTH)`
- (E) `loc1.getDirectionToward(loc2).equals(new Location(Location.NORTH, 0))`



37. 假设我们想创建一个 `Bug` 的变体，它的行为像普通 `Bug`，但在每次移动后都会向左或向右转。从编写的代码来说，以下哪种方法最经济？

- (A) 继承 `Actor` 并重写 `act` 方法
- (B) 继承 `Bug` 并重写 `move` 方法
- (C) 继承 `Bug` 并重写 `turn` 方法
- (D) 继承 `Bug` 并同时重写 `move` 和 `turn` 方法
- (E) 继承 `Bug` 并重写 `canMove` 方法

38. 下图显示了某些 `GridWorld` 类和接口之间的交互。从 A 到 B 的箭头表示 A 继承 B。箭头 `--->` 表示 A 使用 B；即 A 引用了类型为 B 的变量。可以在图中添加两个“使用”箭头以使其更准确。是哪两个？

- (A) `Bug` 使用 `Grid` 且使用 `Flower`
- (B) `Bug` 使用 `Flower` 且使用 `Rock`
- (C) `Bug` 使用 `Grid` 且使用 `Flower`
- (D) `Bug` 使用 `Grid` 且 `BoxBug` 使用 `Grid`
- (E) `Bug` 使用 `Grid` 且 `BoxBug` 使用 `Flower`

39. 给定

```java
Rock rock = new Rock();
```

并假设所有必要的 `import` 语句都存在，以下哪个陈述会导致语法错误？

- (A) `rock.moveTo(null);`
- (B) `rock.setDirection(0);`
- (C) `rock.setColor(Color.GRAY);`
- (D) `rock.setGrid(null);`
- (E) `Location gr = rock.getGrid();`

40. `Critter` 的哪个方法调用了 `select`？

- (A) `act`
- (B) `processMove`
- (C) `makeMove`
- (D) `moveTo`
- (E) 以上均非

# 模拟考试 A-3

计算机科学 A

第二部分

时间 — 1 小时 45 分

题目数量 — 4

占总分百分比 — 50

1. 下图显示了电话系统中使用的类层次结构：

`PhoneCall` 是一个抽象类。`PhoneCall` 对象持有有关通话时长（分钟）的信息，以及根据时长和费率计算通话总费用所需的方法。`PhoneCall` 的构造函数为通话分配一个唯一数字。`PhoneCall` 类不直接处理每分钟费率；相反，它依赖于层次结构中较低的具体类中定义的抽象方法 `getRate`。本地通话的费率在 `LocalCall` 的构造函数中定义。长途通话的费率设置为常量 6.0。优惠通话的费率是普通距离通话费率的一半。你的任务是编写 `PhoneCall`、`LongDistanceCall` 和 `ReducedRateCall` 类。在编写这些类时，你必须避免代码重复：这些类应尽可能重用层次结构中较高类的代码。

# 模拟考试 ~ A-3

`PhoneCall` 是一个抽象类。`PhoneCall` 对象持有有关通话时长（分钟）的信息，以及根据时长和费率计算通话总费用所需的方法。`PhoneCall` 的构造函数为通话分配一个唯一数字。`PhoneCall` 类不直接处理每分钟费率；相反，它依赖于层次结构中较低的具体类中定义的抽象方法 `getRate`。本地通话的费率在 `LocalCall` 的构造函数中定义。长途通话的费率设置为常量 6.0。优惠通话的费率是普通距离通话费率的一半。你的任务是编写 `PhoneCall`、`LongDistanceCall` 和 `ReducedRateCall` 类。在编写这些类时，你必须避免代码重复：这些类应尽可能重用层次结构中较高类的代码。

`PhoneCall` 类应该支持文本输出。例如，以下代码段：

```java
ArrayList<PhoneCall> calls = new ArrayList<>();
calls.add(new LocalCall(10));
calls.add(new LongDistanceCall(3));
for (PhoneCall call : calls) {
    System.out.println(call);
}
```

- Duration 10 Rate 2.5
- Duration 3 Rate 6

(a) 编写抽象类 `PhoneCall` 的完整定义。该类具有以下功能：

- 一个持有通话时长（分钟）的实例变量；
- 一个初始化变量为给定值的构造函数；
- 用于时长的访问器方法；
- 一个不接受参数并返回 `double` 类型每分钟费率的抽象方法；
- 一个根据时长和费率的乘积计算通话费用的 `toString` 方法，并按格式显示：

(b) 编写 `LongDistanceCall` 类。长途通话的费率设置为 6.0。提供必要的功能，使 `LongDistanceCall` 对象能够生成输出。例如，以下语句：

```java
System.out.println(new LongDistanceCall(10));
```

应输出为：

(c) 作为 `LongDistanceCall` 的子类编写 `ReducedRateCall`。优惠通话的费率是长途通话费率的一半。提供必要的功能，使 `ReducedRate` 对象能够生成输出。例如，以下语句：

```java
System.out.println(new ReducedRateCall(8));
```

应输出为：

中国历法将动物和元素与每年关联。有 12 种动物与连续年份关联，五种元素（木、火、土、金、水）结合“甲”或“乙”属性，形成十二年周期。下面的 `ChineseZodiac` 类定义了动物名称，并提供了根据年份获取描述的静态方法：

```java
public class ChineseZodiac {
    private static final int startYear = 1924;

    private static final String[] animals =
        {"rat", "ox", "tiger", "rabbit", "dragon", "snake",
        "horse", "sheep", "monkey", "chicken", "dog", "pig"};

    private static final String[] elements = 
        {"elder wood (fir)", "younger wood (bamboo)",
        "elder fire (burning wood)", "younger fire (lamp flame)",
        "elder earth (hill)", "younger earth (plain)",
        "elder metal (weapon)", "younger metal (kettle)",
        "elder water (wave)", "younger water (brook)"};

    // 返回格式为“动物，元素描述”的历法字符串
    // 前提条件：year >= startYear
    public static String toZodiacString(int year) {
        /* 在部分 (a) 中实现 */
    }
}
```

`startYear = 1924` 是“鼠”年和“甲木”元素年，如 `animals[0]` 和 `elements[0]` 的值所示。接的一年 1925 年是“牛”年和“乙木”元素，如 `animals[1]` 和 `elements[1]` 所示。注意，在过去的 60 年里有若干年是“龙”年，但只有一年是“龙”且是“甲土”。

公共类 `ChineseCalendar` 是 `ChineseZodiac` 类的客户端：

```java
public class ChineseCalendar {
    // 返回格式为“动物/非正式元素”的历法字符串
    // 前提条件：满足 ChineseZodiac 类中
    // toZodiacString 方法的前提
    public String shortZodiac(int year) {
        /* 在部分 (b) 中实现 */
    }

    public int getYear(int year, String animal, String element) {
        /* 在部分 (c) 中实现 */

        // ...构造函数、其他方法和实例变量
        // 未显示
    }
}
```

(a) 在 `ChineseZodiac` 类中编写方法 `toZodiacString`，该方法返回一个将给定年份动物名称与完整元素名称组合的字符串，用逗号和空格分隔。例如，`toZodiacString(1925)` 应该返回字符串：

```
"ox, younger wood (bamboo)"
```

完成下面的 `toZodiacString` 方法。

```java
// returns the zodiac string in the form
// "animal, element description" that corresponds to year
// precondition: year >= startYear
public static String toZodiacString(int year)
```

(b) 在 `ChineseCalendar` 类中编写方法 `shortZodiac`，`shortZodiac` 返回给定年份的“口语化”格式生肖字符串：一个包含动物名称和非正式元素名称的字符串（去除括号内容），用斜杠字符分隔。例如，`shortZodiac(1925)` 返回字符串：

```
"ox/bamboo"
```

假设 `ChineseZodiac` 类中的 `toZodiacString` 按照规范工作，无论你在部分 (a) 中写了什么年份。

完成下面的 `shortZodiac` 方法。

```java
// returns the zodiac string in the form
// "animal/informal element"
// year meets the precondition of the
// toZodiacString method of the
// ChineseZodiac class
public String shortZodiac(int year)
```

(c) 在 `ChineseCalendar` 类中编写方法 `getKey`。`getYear` 返回自指定年份以来，给定动物和元素（由其完整或非正式名称描述）首次出现的年份。例如，`getYear(1924, "ox", "younger wood (bamboo)")` 和 `getYear(1924, "ox", "bamboo")` 返回 1925。如果动物字符串或元素字符串无效，该方法应返回 0。部分 (a) 和 (b) 中描述的方法按照规范工作，无论你写了什么。

完成下面的 `getKey` 方法。

```java
// returns the year of the first occurrence of animal and
// element in the Chinese calendar, since start year
// (year included); returns 0 if such year is not found
// precondition: year meets the precondition of the
// toZodiacString method of the
// ChineseZodiac class
public int getKey(int year, String animal, String element)
```

3. 此题涉及对 `GridWorld` 案例研究代码的推理。考试的一部分提供了代码的副本。

`Bee`（蜜蜂）是一种与网格中的 `Clover`（三叶草）对象交互的 `Critter`（生物）。`Clover` 是一种可以授粉的 `Flower`（花）。下面是 `Clover` 类的部分代码：

```java
public class Clover extends Flower
{
    // 为这朵花授粉（通常由 Bee 调用）
    public void pollinate()
    /* code not shown */

    // 如果这朵花已被授粉，则返回 true；
    // 否则返回 false
    public boolean hasBeenPollinated()
    { /* code not shown {

    // 字段、构造函数和其他方法未显示
}
```

# 262 模拟考试 ~ A-3

一只 `Bee` 首先授粉所有相邻位置的 `Clover` 花，然后向最近的尚未被授粉的 `Clover` 移动。`Bee` 类的定义如下：

```java
public class Bee extends Critter
{
    // 创建一只黄蜂
    public Bee()
    {
        setColor(Color.YELLOW);
    }

    // 处理执行者；对它们之间所有的 Clover 对象进行授粉
    public void processActors(ArrayList<Actor> actors)
    {
        /* 将在部分 (a) 中实现 */
    }

    // 在 loc 和当前位置之间选择距离 
    // 未授粉的 Clover 最近的位置；
    // 如果多个位置到未授粉的 Clover 的距离
    // 相同，则返回其中任意一个；
    // 如果网格中没有任何未授粉的 Clover，
    public Location selectMoveLocation(ArrayList<Location> locs)
    {
        /* 将在部分 (b) 中实现 */
    }

    // 向 loc 转，然后像普通的 Critter 一样移动到 loc
    public void makeMove(Location loc)
    {
        /* 将在部分 (c) 中实现 */
    }

    // 返回 loc1 和 loc2 之间的距离
    // 前条件：loc1 != null 且 loc2 != null
    private int distance(Location loc1, Location loc2)
    {
        /* code not shown */
    }

    // 返回距离 loc 最近且尚未
    // 授粉的 Clover 的位置；
    // 如果网格不包含任何未授粉的 Clover，
    // 返回 null
    // 前条件：loc != null
    private Location findNearestClover(Location loc)
    {
        /* code not shown */
    }
}
```

(a) 编写 `processActors` 方法。该方法对传递它的 `actors` 列表中的每个 `Clover` 授粉。

完成下面的 `processActors` 方法。

```java
// 处理执行者；对它们之间所有的 Clover 对象进行授粉
public void processActors(ArrayList<Clover> actors)
```

(b) 编写 `selectMoveLocation` 方法。该方法获取当前位置加上网格中的所有位置，并在它们之间找到距离任何未授粉的 `Clover` 最近的位置。（如果有多个位置到未授粉的 `Clover` 的最小距离相同，可以选择其中任意一个。）如果网格中不包含未授粉的 `Clover`，`selectMoveLocation` 应该返回 `null`。完成下面的 `selectMoveLocation` 方法。

```java
// returns the location chosen among loc and the current
// location that is nearest to an unpollinated clover;
// if several locations are at the same distance
// from an unpollinated clover, returns any one of them;
// if the grid does not have any unpollinated clovers,
public Location selectMoveLocation(ArrayList<Location> locs)
```

(c) 编写 `makeMove` 方法。该方法向 `loc` 转，然后像普通的 `Critter` 一样移动到 `loc`，如部分 (c) 描述的那样（此处原文描述有误，已根据上下文逻辑翻译）。

```java
// turns towards loc, then moves into loc like a
// regular Critter
public void makeMove(Location loc)
```

（注：此处应为返回自指定年份以来，给定动物和元素（由其完整或非正式名称描述）首次出现的年份的逻辑描述。例如，`getYear(1924, "ox", "younger wood (bamboo)")` 和 `getYear(1924, "ox", "bamboo")` 返回 1925。如果动物字符串或元素字符串无效，该方法应返回 0。部分 (a) 和 (b) 中描述的方法按照规范工作，无论你写了什么。）

*纠正：原文文本在 (c) 处似乎发生了粘贴错误或重复，翻译时已根据逻辑结构进行了对齐。*

4. 此题涉及对 `GridWorld` 案例研究代码的推理。考试的一部分提供了代码的副本。



Bee 是一种与网格中的 Clover 对象交互的 Critter。Clover 是一种可以授粉的 Flower。下面是 `Clover` 类的部分代码：

```java
public class Clover extends Flower
{
    // 为这朵花授粉（通常由 Bee 调用）
    public void pollinate()
    /* code not shown */

    // 如果这朵花已被授粉，则返回 true；
    // 否则返回 false
    public boolean hasBeenPollinated()
    { /* code not shown */ }

    // 字段、构造函数和其他方法未显示
}
```

# 模拟考试 AB-1

计算机科学 AB 部分

时间 — 1 小时 15 分钟

题目数量 — 40

占总分百分比 — 50

1. 以下代码的输出是什么？

```java
int n = 12;
System.out.print(goFigure(n));
```

其中方法 `goFigure` 定义如下：

```java
public double goFigure(int n) {
    n = n % 7;
    return (double) (12 / n);
}
```

(A) 2

(B) 6

(C) 5

(D) 12

(E) 0

2. 如果 n 个元素以随机顺序存储在数组中，以下排序算法保证能在 O(n log n) 内运行？

I. 快速排序

II. 归并排序

III. 堆排序

(A) 仅 I

(B) 仅 II

(C) I 和 II

(D) II 和 III

(E) I, II, 和 III

3. 考虑以下方法：

```java
public void addes(List<Integer> list) {
    ListIterator<Integer> itr = list.listIterator();
    while (itr.hasNext()) {
        itr.add(new Integer(itr.next()));
    }
}
```

如果 `list` 包含值 0, 2, 4, 6（按此顺序），调用 `addes` 后结果是什么？

(A) `list` 包含 1, 0, 2, 4, 6

(B) `list` 包含 0, 1, 2, 4, 6

(C) `list` 包含 1, 0, 2, 4, 6

(D) 发生 `IllegalStateException`。

(E) 方法进入了死循环。

4. 考虑以下方法：

```java
public void mystery(int n) {
    for (int k = 1; k <= n; k++) {
        for (int j = n - 1; j > 0; j = j / 2) {
            guess(j);
        }
    }
}
```

假设 `guess` 总是以 O(1) 运行。以下哪项最能描述 `mystery(n)` 的运行时间？

(A) O(1)

(B) O(log n)

(C) O(n)

(D) O(n log n)

(E) O(n²)

5. 考虑以下方法：

```java
// 返回 list 中找到 searchVal 的索引；
// 否则返回 -1
public int binarySearch(ArrayList<String> list, String searchVal) {
    int first = 0, last = list.size() - 1;
    while (first <= last) {
        int mid = (first + last) / 2;
        if (searchVal.compareTo(list.get(mid)) < 0)
            last = mid - 1;
        else if (searchVal.compareTo(list.get(mid)) > 0)
            first = mid + 1;
        else
            return mid; // 语句 1
    }
    return -1; // 语句 2
}
```

我们想要修改此方法：如果 `searchVal` 不在列表中，我们希望 `binarySearch` 返回一个可以在保持列表排序的情况下插入它的位置。以下哪项可以用于语句 1 和语句 2？

| 语句 1 | 语句 2 |

| :--- | :--- |

| (A) `return mid;` | `return mid;` |

| (B) `return mid;` | `return first;` |

| (C) `return mid;` | `return last;` |

| (D) `return mid - 1;` | `return first;` |

| (E) `return mid - 1;` | `return last;` |

6. 假设将以下整数值插入到一个初始为空的搜索树（按如下顺序）：

22, 30, 16, 19, 28, 34, 51, 45, 32

在搜索一个不在该二叉树中的值时，最坏情况下将执行的整数比较的最大次数是多少？

(A) 2

(B) 3

(C) 4

(D) 5

(E) 6

```java
public void stackQueueFun(ArrayList<Integer> items) {
    Stack<Integer> s = new Stack<Integer>();
    Queue<Integer> q = new LinkedList<Integer>();

    Random randGen = new Random();
    for (Integer elem : items) {
        if (randGen.nextInt(2) == 0)
            q.add(elem);
        else
            s.push(elem);
    }

    int index = 0;
    while (!s.isEmpty()) {
        items.set(index, s.pop());
        index++;
    }

    while (!q.isEmpty()) {
        items.set(index, q.remove());
        index++;
    }
}
```

7. 考虑以下方法：

假设 `list items` 包含值 1, 2, 3, 4, 5, 6，并执行以下代码段：

`stackQueueFun(items);`

`System.out.println(items);`

以下输出哪个是不可能的？

(A) [1, 2, 3, 4, 5, 6]

(B) [6, 5, 4, 3, 2, 1]

(C) [3, 2, 1, 4, 5, 6]

(D) [5, 1, 3, 2, 4, 6]

(E) [6, 4, 3, 1, 2, 5]

8. 如果一个二叉树的所有层都满了节点，除了底部可以从左侧开始填充且没有间隙，则该树被称为“完全”的。关于无重复元素的完全二叉树，以下哪些说法是正确的？

I. 根节点必须是叶子节点或有两个孩子。

II. 包含最小值的节点必须是叶子节点。

III. 包含最大值的节点必须是叶子节点。

(A) 仅 I

(B) 仅 II

(C) I 和 II

(D) II 和 III

(E) I, II, 和 III

9. 考虑以下类：

```java
public class Tree {
    private TreeNode root;
    public Tree() { root = null; }
    public int mysteryCount() { return mysteryCount(root); }
    private int mysteryCount(TreeNode t) {
        if (t == null)
            return 0;
        else if (t.getLeft() == null && t.getRight() == null)
            return 0;
        else if (t.getLeft() == null)
            return 1 + mysteryCount(t.getRight());
        else
            return 1 + mysteryCount(t.getLeft()) + mysteryCount(t.getRight());
    }
}
```

假设实例化了一个 `Tree` 对象并向其添加了 items。`tree.mysteryCount()` 返回？

(A) 节点的总数

(B) 有父节点的数量

(C) 至少有一个节点的数量

(D) 只有一个节点的数量

(E) 有两个节点的数量

10. 以下方法 `insertDuplicates` 将每个元素的重复值插入列表：考虑此方法的两种替代实现：

实现 1:

```java
for (int j = 0; j < list.size(); j++) {
    list.add(list.get(j));
}
```

实现 2:

```java
ListIterator<Integer> itr = list.listIterator();
while (itr.hasNext()) {
    itr.add(itr.next());
}
```

以下哪些说法是正确的？

(A) 如果 `list` 是 `ArrayList`，实现 1 比 2 高效。

(B) 如果 `list` 是 `ArrayList`，实现 2 比 1 高效。

(C) 如果 `list` 是 `LinkedList`，实现 1 比 2 高效。

(D) 如果 `list` 是 `LinkedList`，实现 2 比 1 高效。

(E) 对于 `ArrayList` 和 `LinkedList`，两种实现效率相同。

11. 当 x 和 y 为布尔变量时，以下哪些表达式的结果为真？

I. `(x || y) && (!x && !y)`

II. `(x || y) && !(x && y)`

III. `(x && !y) || (!x && y)`

12. 第 12-13 题涉及以下方法：

```java
public void printVals(String[] items, int k) {
    if (k > 1) {
        printVals(items, k - 1);
        System.out.print(items[k] + " ");
        printVals(items, k - 2);
    }
}
```

假设执行了以下代码：

```java
String[] names = {"Pat", "Joe", "Ann", "Amy"};
printVals(names, names.length - 1);
```

12. 输出是什么？

(A) Ann Amy Amy

(B) Ann Amy Joe

(C) Ann Joe Amy

(D) Joe Ann Amy Pat

(E) Joe Amy Pat

13. 调用了多少次 `printVals`（包括原始调用）？

(A) 3

(B) 5

(C) 7

(D) 8

(E) 9

14. 需要编写一个用于哈希表的 `hash(String word)`。如果 `hash("lemon")` 返回 x

(A) x == 5（单词 "lemon" 的字母数）

(B) `hash("mango")` > x，因为按字母顺序 "lemon" 在 "mango" 之前

(C) `hash("melon")` == x，因为 "lemon" 和 "melon" 包含相同的字母

(D) 0 <= x < n/2，其中 n 是表中存储的最大单词数

(E) 以上都不是

15. 考虑以下不完整的类：

```java
public abstract class Animal
{
    public Animal() { /* 未显示 */ }
    public abstract void eat();
}

public class Bear extends Animal
{
    public Bear() { /* 未显示 */ }
    public void eat() { /* 未显示 */ }
}
```

以下哪些语句可以编译且无错误？

I. `Animal joe = new Animal();`

II. `Animal smokey = new Bear();`

III. `Bear teddy = new Animal();`

(A) 仅 I

(B) 仅 II

(C) I 和 II

(D) II 和 III

(E) I, II, 和 III

16. 考虑以下代码段：

```java
int n = <大正整数>
Set<Integer> set = ...; // 初始化为空集合
Random randGen = new Random();
for (int j = 0; j < n; j++)
    set.add(new Integer(randGen.nextInt(1000)));
```

当 `set` 分别为 `TreeSet` 或 `HashSet` 时，该代码段运行时间相对于 n 的 Big-Oh 复杂度多少？

| TreeSet | HashSet |

| :--- | :--- |

| (A) O(n) | O(n) |

| (B) O(n log n) | O(n) |

| (C) O(n log n) | O(n log n) |

| (D) O(n²) | O(n) |

| (E) O(n²) | O(n log n) |

17. 考虑以下方法：

```java
// returns the largest sum of two elements in amps
// precondition: amps.length >= 2; amps is filled with random
// values
public int addTopTwo(int[] amps)
{
    int k, k1 = 0, k2 = 1;
    for (k = 2; k < amps.length; k++)
    {
        if (amps[k] > amps[k1]) {
            k2 = k1;
            k1 = k;
        } else if (amps[k] > amps[k2]) {
            k2 = k;
        }
    }
    return amps[k1] + amps[k2];
}
```

以下哪个数组会导致 `addTopTwo` 返回错误的结果？

- (A) {1, 5, 4, 3, 2}

- (B) {2, 1, 3, 4, 5}

- (C) {1, 2, 3, 4, 5}

- (D) {5, 4, 3, 2, 1}

- (E) {5, 4}

18. 考虑以下方法：

```java
public int guess(int a, int b) {
    // 未显示
}
```

在执行以下代码段后，`num` 的值是多少？

```java
int num = (6 * 14) / guess(6, 14);
```

- (A) 6
- (B) 12
- (C) 14
- (D) 28
- (E) 42

19. 考虑以下类 `Athlete`：

```java
public class Athlete implements Comparable<Athlete>
{
    private int numMedals;
    public int getMedals() { return numMedals; }
    public int compareTo(Athlete other)
    {
        // return numMedals - other.numMedals;
        return getRank() - other.getRank();
    }
    // 构造函数和其他方法未显示
}
```

如你所见，程序员在 `compareTo` 代码中注释了对 `Athlete` 实例变量 `numMedals` 的直接引用，并用调用 `getRank` 方法取代了它们。这样做最有说服力的理由是什么？

- (A) 修正语法错误：由于是私有的，`numMedals` 或 `other.numMedals` 在方法代码中均无法直接访问
- (B) 修正语法错误：由于是私有的，`other.numMedals` 在方法代码中无法直接访问（为了一致性，用 `getRank()` 替换了 `numMedals`）
- (C) 避免以后可能的问题：如果 `other` 刚好是 `Athlete` 子类的对象，且该类在计算排名时没有使用 `numMedals`，则原始代码将失效
- (D) 提高运行效率
- (E) 实现更好的封装

20. 如果一只 Bug（昆虫）位于有边界网格的东北角且面向北，它会如何行动？

- (A) 昆虫向西转
- (B) 昆虫向南转
- (C) 昆虫向东北转
- (D) 昆虫向西北转
- (E) 昆虫从网格中移除

21. 考虑以下方法：

```java
// 将昆虫移动到西侧的相邻位置，
// 保持昆虫当前位置为空且昆虫方向不变。
// 前提条件：(1) 该 actor 包含在网格内
// (2) 西侧的相邻位置在该昆虫的网格中是有效且空的
public void moveWest(Bug bug) {
    Location loc = bug.getLocation();
```



`Location next = loc.getAdjacentLocation(Location.WEST);`

// 缺失代码

}

```

以下哪个代码段可以替换 `<缺失代码>` 以使该方法按说明要求工作？

- I. `bug.moveTo(next);`
II. `GridActor gr = bug.getGrid();`
`bug.removeSelfFromGrid();`
`bug.putInGrid(gr, next);`
III. `int dir = bug.getDirection();`
`bug.setDirection(Location.WEST);`
`bug.move();`
`bug.setDirection(dir);`

- (A) 仅 I
- (B) 仅 II
- (C) 仅 I 和 II
- (D) 仅 II 和 III
- (E) I, II, 和 III

22. 以下哪个代码段的值等于 `Grid<Actor> gr` 中相邻 `Location loc` 的被占用位置的数量？

```
I. `ArrayList<Location> neighbors =`
`gr.getOccupiedAdjacentLocations(loc);`
`int n = neighbors.size();`
```

```
II. `ArrayList<Actor> neighbors = gr.getNeighbors(loc);`
`int n = neighbors.size();`
```

```
III. `ArrayList<Location> neighbors =`
`gr.getValidAdjacentLocations(loc);`
`ArrayList<Location> emptyNeighbors =`
`gr.getEmptyAdjacentLocations(loc);`
`int n = neighbors.size() - emptyNeighbors.size();`
```

- (A) 仅 I
- (B) 仅 II
- (C) 仅 I 和 II
- (D) 仅 II 和 III
- (E) I, II, 和 III

23. 在 GridWorld 设计中，为什么不将 `Actor` 类设为抽象类，并将 `act` 方法设为抽象方法？

- (A) 实现 `Actor` 实例的多态
- (B) 能够重写该方法
- (C) 避免 `Actor` 子类中构造函数的代码重复
- (D) 避免 `Actor` 子类中方法的重复
- (E) 在 GridWorld 中创建 `Actor` 对象并探索它们的属性和行为

24. `Locust` 是 `Critter` 的子类。`Locust` 的行为类似于 `Bug`；每一步，如果它前面的位置为空或包含 `Flower`，它就移动到该位置；否则转 45 度。通过重写 `Critter` 的 `makeMove` 方法和两个方法来实现 `Locust`，以满足后置条件：

- (A) getters and `getMoveLocations`
- (B) `processActors` and `getMoveLocations`
- (C) getters and `selectMoveLocation`
- (D) `processActors` and `selectMoveLocation`
- (E) 以上任意一种均可重写使 `Locust` 工作

25. 考虑一种使用 `TreeMap<Location, Actor>` 的无边界网格新实现。新实现中 `getAdjacentLocations` 方法的时间复杂度（Big-Oh）是多少？

| | 原始 | 新 |
|---|---|---|
| (A) | O(1) | O(n) |
| (B) | O(1) | O(n) |
| (C) | O(n) | O(log n) |
| (D) | O(n) | O(n²) |
| (E) | O(n²) | O(n²)

26. 考虑以下方法：

```
public int locate(String str, String oneLetter)
{
    j = 0;
    while (j < str.length() &&
        str.substring(j, 1).compareTo(oneLetter) < 0)
    {
        j++;
    }
    return j;
}
```

当 `while` 循环结束时，以下哪个条件正确？

- (A) `j == str.length()`
- (B) `str.substring(j, 1) >= 0`
- (C) `j <= str.length() ||`
    `str.substring(j, 1).compareTo(oneLetter) > 0`
- (D) `j == str.length() &&`
    `str.substring(j, 1).compareTo(oneLetter) > 0`
- (E) `j == str.length() ||`
    `str.substring(j, 1).compareTo(oneLetter) >= 0`

27. 假设类 `Binky` 的 `equals` 和 `hashCode` 实现了 `Comparable<Binky>`。假设该类的对象需要放入 `HashSet<Binky>`。为了确保集合不包含重复对象，对于任意两个 `Binky` 对象 `bl1` 和 `bl2`，以下哪个条件正确？

- (A) 不需要额外条件；总是如此。
- (B) 如果 `bl1.compareTo(bl2)` 返回 0，则 `bl1.equals(bl2)` 必须返回 `true`。
- (C) 如果 `bl1.compareTo(2)` 返回 0，则 `bl1.hashCode()` 必须返回与 `bl2.hashCode()` 相同的值。
- (D) 如果 `bl1.equals(bl2)` 返回 `true`，则 `bl1.hashCode()` 必须返回与 `bl2.hashCode()` 相同的值。
- (E) 如果 `bl1.hashCode()` 返回与 `bl2.hashCode()` 相同的值，则 `bl1.equals(bl2)` 必须返回 `true`。

28. 考虑以下方法：

```java
public String crazy(String word)
{
    Stack<String> stk = new Stack<String>();
    String newWord = "";
    for (int j = 0; j < word.length(); j++)
        stk.push(word.substring(j));
    while (!stk.isEmpty())
        newWord = stk.pop() + newWord;
        if (!stk.isEmpty())
            word = word + stk.pop();
    }
    return newWord;
}
```

执行以下语句后，`word1` 和 `word2` 所指向的字符串的内容是什么？

```
String word1 = "about";
String word2 = crazy(word1);
```

| | word1 | word2 |
|---|---|---|
| (A) | "about" | "toutabout" |
| (B) | "about" | "outabout" |
| (C) | "about" | "outabout" |
| (D) | "aboutbout" | "aboutoutt" |
| (E) | "aboutbout" | "toutabout" |

29. 假设 `arr` 包含 127 个按升序排列的不同随机值，并使用最高效搜索算法查找目标值。当目标等于 `arr[39]` 时，将检查数组中的多少个元素？

- (A) 4
- (B) 5
- (C) 7
- (D) 63
- (E) 64

30. 执行以下代码段后的输出是什么？

```
Stack<String> s = new Stack<String>();
Queue<String> q = new LinkedList<String>();
s.push("C");
q.add("C");
s.push("B");
q.add("B");
s.push("*");
q.add("A");
q.add(s.pop());
q.add(s.pop());
s.push(q.remove());
s.push(q.remove());
System.out.println(s.peek() + " " + q.peek());
```

- (A) A B
- (B) A C
- (C) B A
- (D) B C
- (E) C C

31. 假设 `mat` 定义为

```
int[][] mat = new int[3][4];
```

如果 `mat` 初始包含

```
2 1 3 4
9 7 2 1
0 2 5 6
```

以下代码段的输出是什么？

```
for (int r = 1; r < mat.length; r++)
{
    for (int c = 1; c < mat[0].length; c++)
    {
        if ((r + c) % 2 == 0)
            mat[r][c] = 2 * mat[r - 1][c - 1] + c;
    }
}
System.out.println(mat[2][2]);
```

- (A) 16
- (B) 15
- (C) 12
- (D) 11
- (E) 5

32. 有些玩具是娃娃。有些玩具是电子玩具。有些玩具是电子娃娃。下列哪一组类和接口最能对这些关系建模？

```
(A)
public class Toy
public class Electronic extends Toy
public class Doll extends Toy
public class ElectronicDoll extends Electronic
```

```
(B)
public class Toy
public interface Electronic extends Toy
public class Doll extends Toy
public class ElectronicDoll extends Toy implements Electronic
```

```
(C)
public abstract class Toy
public abstract class Electronic extends Toy
public class Doll extends Toy
public class ElectronicDoll extends Doll implements Electronic
```

```
(D)
public abstract class Toy
public interface Electronic
public class Doll extends Toy
public class ElectronicDoll extends Doll implements Electronic
```

```
(E)
public interface Toy
public interface Electronic
public class Doll implements Toy
public class ElectronicDoll implements Toy, Electronic
```

33. 假设 `MyQueue` 实现了 `java.util.Queue<String>`。考虑以下其 `remove` 方法的代码：

```java
public String remove ()
{
    if (!isEmpty())
        return items.remove(0);
    else
        < missing statement>
}
```

下列哪项是替换 `< missing statement >` 最合适的替代方案？

- (A) `System.out.println("remove: NoElementException");`
- (B) `System.err.println("remove: NoElementException");`
- (C) `System.err.println("remove: " + NoElementException);`
- (D) `throw (new NoElementException());`
- (E) `throw new NoElementException();`

34. 考虑以下类：

```java
public class A {
    public A() {
        methodOne();
    }
    public void methodName() {
        System.out.print("A");
    }
}

public class B extends A {
    public B() {
        System.out.print("*");
    }
    public void methodName() {
        System.out.print("B");
    }
}
```

执行以下代码语句时，输出是什么？

`A obj = new B();`

- (A) *
- (B) *A
- (C) *B
- (D) A*
- (E) B*

35. 假设将 14 3 6 1 12 9 15 2 5 按此顺序加入最小堆（min-heap）中。下列哪个序列对应于该最小堆的后序遍历？

- (A) 14 2 6 1 12 9 15 2 5
- (B) 14 5 3 12 9 15 6 1
- (C) 14 5 3 2 12 9 6 15 1
- (D) 14 3 5 2 12 1 9 6 15
- (E) 14 12 5 3 2 9 15 6 1

# 284 模拟考试 ~ AB-1

36. 给定以下声明：

`Object obj = new String("This is a test!");`

下列哪个表达式可以在无错误的情况下通过编译？

- I. `System.out.println(obj.substring(2,7));`
- II. `if (obj.equals("This is a test!")) System.out.println("Yes");`
- III. `if (obj.compareTo("This is a test!") == 0) System.out.println("Yes");`

- (A) 仅 I
- (B) 仅 II
- (C) 仅 I 和 II
- (D) 仅 II 和 III
- (E) I, II, 和 III

37. 在 DVD 租赁店的库存中，项目由 `DVD` 类描述。每张 DVD 都属于一个类别（喜剧、剧情、动作等），并有一个唯一的整数编号。库存系统必须能够根据给定的项目编号快速添加或删除 DVD。此外，它应该能够按照项目顺序快速列出特定类别的所有 DVD。假设 `DVD` 类具有与项目编号匹配的适当 `equals`、`compareTo` 和 `hashCode` 方法，下列哪项描述了租赁店库存系统数据结构的最佳选择？

- (A) `TreeMap<Integer, DVD>`, 其中 key 为项目编号，value 为该编号的 DVD
- (B) `HashMap<Integer, DVD>`, 其中 key 为项目编号，value 为该编号的 DVD
- (C) `TreeMap<String, HashSet<DVD>>`, 其中 key 为类别，value 为该类别内所有 DVD 的集合
- (D) `TreeMap<String, TreeSet<DVD>>`, 其中 key 为类别，value 为该类别内所有 DVD 的集合
- (E) `HashMap<String, HashSet<DVD>>`, 其中 key 为类别，value 为该类别内所有 DVD 的集合

38. 如果一个二叉树有 17 个节点，其中最多有多少是叶子节点？

- (A) 1
- (B) 8
- (C) 9
- (D) 16
- (E) 17

39. 考虑以下类：

```java
public class Tree {
    private boolean evergreen;
    public Tree(boolean green)
    { evergreen = green; }
    public boolean isEvergreen()
    { return evergreen; }
}

public class LemonTree extends Tree {
    public LemonTree()
    { super(false); }
    public void growLeaves()
    { /* 实现如所示 */ }
}
```

给定 `Tree tree = new LemonTree();`，下列哪些语句可以编译？

- I. `if (tree.isEvergreen()) tree.growLeaves();`
- II. `tree.growLeaves();`
- III. `if (!tree.isEvergreen()) tree.growLeaves();`

- (A) 仅 I
- (B) 仅 II
- (C) 仅 I 和 II
- (D) 仅 II 和 III
- (E) I, II, 和 III

40. 考虑以下类：

```java
public class MyLinkedList {



`private ListNode front;`

`public MyLinkedList() { front = null; }`

`public void addLast(Object val) {`

`    if (front == null) {`

`        front = new ListNode(val);`

`    } else {`

`        <missing code>`

`    }`

`}`

`}`

`addLast` 方法将值添加到链表的末尾。下列代码段可以替换 `<missing code>` ？

- (A) `while (front != null) { front = front.getNext(); } front = new ListNode(val);`
- (B) `while (front.getNext() != null) { front = front.getNext(); } front = new ListNode(val);`
- (C) `ListNode p = front; while (front != null) { front = front.getNext(); } front = new ListNode(val);`
- (D) `ListNode p = front; while (front.getNext() != null) { front = front.getNext(); } front = new ListNode(val);`
- (E) `while (front != null) { front = new ListNode(val); } front;`

`combine` 方法接收两个列表并将它们合并为一个列表，该列表交替包含两个列表中的卡片。如果其中一个列表没有剩余卡片，则将另一个列表中的所有卡片复制到合并列表中。例如，如果 `list1` 包含 `[6 7 8 9]`，`list2` 包含 `[2 3 4 5]`，`combine` 返回一个包含 `[6 2 7 3 8 4 9 5]` 的列表。该方法不能分配任何新节点，且必须在 $O(n)$ 时间内运行，$n$ 是 `list1` 和 `list2` 中的节点总数。

```java
// 将 list1 和 list2 中的卡片合并为一个列表
// 从 list1 取一张卡片，下一张从 list2 取，
// 下一张再从 list1 取，以此类推；如果
// 其中一个列表中剩余卡片，则将另一个
// 列表的所有卡片复制到合并列表中；返回新列表第一个节点的引用
private ListNode combine(ListNode list1, ListNode list2)
```

(b) 要洗一副牌，只需将其拆分并合并若干次。`shuffle` 方法应该实现此过程。假设这些方法按照指定的方式工作，无论你在部分 (a) 和部分 (b) 的解答中写了什么。

```java
// 拆分此牌，然后将此牌的卡片列表
// 与牌中剩余的卡片合并；
// 此操作重复 numTimes 次
public void shuffle(int numTimes)
```

2. 本题涉及对代码的推理。提供了代码副本作为参考，该 `Twister` 是 `Actor` 的子类。`Twister` 始终留在它创建时的同一行：它每一步都会移动到相邻位置，随机选择向东或向西，概率相等。如果预期移动的位置包含另一个 actor，则该 actor 将被从网格中移除。如果预期移动的位置无效，`Twister` 将自己从网格中移除。在移动之前，`Twister` 会销毁其所在列中位于下方（南方）的所有 actor。以下是 `Twister` 类的部分定义：

```java
public class Twister extends Actor {

  public Twister() {
    setColor(Color.BLACK);
  }

  public void act() {
    destroy();
    move();
  }

  // 从网格中移除其所在列中
  // 位于 Twister 下方（南方）的所有 actor
  public void destroy() {
    /* 在部分 (a) 中实现 */
  }

  // 向东或向西移动 Twister，概率相等
  // 如果预期移动的位置包含另一个
  // actor，则该 actor 被从网格中移除；如果
  // 预期移动的位置无效，此
  // Twister 将从网格中移除
  public void move() {
    /* 在部分 (c) 中实现 */
  }
}
```

(a) 编写 `Twister` 类的 `destroy` 方法。该方法应该销毁（从网格中移除）所有与 `Twister` 在同一列且位于下方的 actor。

```java
// 从网格中移除其所在列中
// 位于 Twister 下方（南方）的所有 actor
public void destroy()
```

(b) 说明你在部分 (a) 中编写的 `destroy` 方法对于包含 $n$ 个 actor 的 $n \times n$ 有边界网格以及包含 $n$ 个 actor 的无边界网格的时间复杂度（大-O）。

| 有边界网格 | 无边界网格 |
| :--- | :--- |
| 是否设计设计不同的无边界网格结构并编写一个 `destroy` 方法，当每列的 actor 数量不超过 3 时能够在 $O(1)$ 时间内运行？ | 如果可以，请简要描述这种设计；如果不可以，请解释原因。 |

(c) 编写 `Twister` 类的 `move` 方法。`Twister` 移动到同一行的相邻位置，随机选择向东或向西，概率相等。如果预期移动的位置包含另一个 actor，则该 actor 被从网格中移除。如果预期移动的位置无效，`Twister` 将消失（从网格中移除自己）。

```java
// 向东或向西移动此 Twister，概率相等；
// 如果预期移动的位置包含另一个
// actor，则该 actor 被从网格中移除；如果
// 预期移动的位置无效，此
// Twister 将从网格中移除
public void move()
```

3. 在医院急诊室，患者按优先顺序接受治疗：危及生命的伤口或疾病将在轻伤或小病患者之前接受治疗。

考虑一种应用程序，该程序在患者进入急诊室时为每个患者分配一个优先级值。数值越小表示患者治疗的优先级越高。例如，如果患者 A 的优先级为 2 而患者 B 的优先级为 5，患者 A 将在 B 之前接受治疗。如果两个患者的优先级相同，他们应该按照到达急诊室的顺序接受治疗。

该应用程序使用了以下接口 `Patient` 和类 `EmergencyRoom`：

```java
public interface Patient {
    // 返回此患者的优先级；数字越小
    // 表示治疗优先级越高
    Integer getPriority();
}
```

```java
public class EmergencyRoom {
    private Map<Integer, LinkedList<Patient>> patientMap;
    // Integer 类型的优先级作为键；具有该
    // 优先级的患者列表作为关联值

    // 构建一个具有空 patientMap 的 EmergencyRoom
    public EmergencyRoom()
        /* 在部分 (a) 中完成 */

    // 返回 EmergencyWaiting 中的等待患者数量
    public int numPatientsWaiting()
        /* 未显示实现 */

    // 根据患者的优先级将 p 添加到相应的
    // 列表中；如果该优先级不存在，
    // 则添加到 patientMap
    public void admit(Patient p)
        /* 在部分 (b) 中完成 */

    // 移除并返回优先级最高的患者；
    // 如果移除患者导致列表为空，则从
    // patientMap 中移除该优先级；如果
    // EmergencyRoom 没有患者，返回 null
    public Patient nextPatient()
        /* 在部分 (c) 中实现 */

    // 其他方法和变量未显示
}
```

(a) 完成 `EmergencyRoom` 类的构造函数。

```java
// 构建一个空 patientMap 的 EmergencyRoom
public EmergencyRoom()
```

(b) 当患者进入急诊室时，将其添加到该优先级的关联列表中。如果不存在此类列表，`admit` 将创建它。

```java
// 根据优先级将 p 添加到相应的
// 列表中
public void admit(Patient p)
```

(c) `nextPatient` 方法移除并返回最高且在急诊室停留时间比相同优先级患者更长的患者。如果移除患者导致列表为空，则从 `patientMap` 中移除该优先级。为了获得全分，请实现此方法使其平均运行时间为 $O(\log n)$，$n$ 是不同优先级的数量。

```java
// 移除并返回优先级最高的患者
// 来自 EmergencyRoom；如果移除患者导致
// 列表为空，则从 patientMap 中移除
// 该优先级；如果 EmergencyRoom
// 没有患者，返回 null
public Patient nextPatient()
```

4. 考虑按层构建二叉树。每一层从左侧开始填充。当某层完全满时，将创建一个新层。假设将以下数据插入到初始空树中，顺序如下：

1 6 9 12 5 4 22 3

第一个值成为根；接下来两个值分别成为根的左孩子和右孩子。下一个项目 12 被插入到第三层的最左侧节点，依此类推。这产生了如下树：

假设二叉树由以下类表示：

```java
public class BinaryTree {
    private TreeNode root;
    // 持有此树根节点的引用

    // 从 items 中找到的值按层构建
    // 二叉树；如果 items.size() == 0 则
    // 构建一个空树 (root == null)
    public BinaryTree(List<Integer> items) {
        /* 在部分 (a) 中完成 */
    }

    // 返回 true，如果按层构建的此 BinaryTree
    // 为空或者是一个最小堆堆
    public boolean isMinHeap() {
        /* 在部分 (b) 中完成 */
    }
}
```

(a) 为 `BinaryTree` 类编写构造函数。以下算法使用一个 `TreeNode` 对象的队列，根据项列表逐层构建一个二叉树：

- 1. 从一个空树和一个空队列开始；
- 2. 从列表中取出下一个项，并创建一个包含该项的新型节点；
- 3. 如果队列为空，则将根节点（`root`）设置为新节点；
  否则，检查队列中的第一个节点 $t$：
  * 如果 $t$ 没有子节点，则将新节点作为 $t$ 的左节点添加
  * 如果 $t$ 有左节点但没有右节点，则将新节点作为 $t$ 的右节点添加
  从队列中移除 $t$；
- 4. 将新节点加入队列；
- 5. 只要列表中还有更多项，就重复步骤 2-4。

请在下方完成 `BinaryTree` 的构造函数。

```java
// 根据 items 中找到的值逐层构建二叉树；
// 如果 items.size() == 0，则构建一个空树 (root == null)
public BinaryTree(List<Integer> items) {
```

(b) 编写一个方法 `isMinHeap`，检查该按逐层构建的 `BinaryTree` 是否为最小堆（min-heap）。为了获得满分，你的方法应该在 O(n) 时间内运行，其中 $n$ 是树中的节点数量。在编写 `isMinHeap` 时，你可能会发现引入一个辅助方法很有用。请在下方完成 `isMinHeap` 方法。

```java
// 如果该逐层构建的 BinaryTree
// 为空或为最小堆，则返回 true
public boolean isMinHeap() {
```

# 模拟考试 AB-2

计算机科学 AB
第一部分

时间 — 1 小时 15 分钟
题目数量 — 40
 占总分百分比 — 50%

- 1. 考虑以下方法：
```java
public void change(double[] nums, int n)
{
    for (int k = 0; k < n; k++)
        nums[k] = 5.4;
    n = 2;
}
```

执行以下语句后，`samples` 和 `len` 中存储了什么？
```java
double[] samples = {1.0, 2.1, 3.2, 4.3};
int len = samples.length;
change(samples, len);
```

- (A) `samples` 包含 `5.4, 5.4, 5.4, 5.4`，且 `len` 为 4
- (B) `samples` 包含 `5.4, 5.4, 5.4, 5.4`，且 `len` 为 2
- (C) `samples` 包含 `1.0, 2.1, 3.2, 4.3`，且 `len` 为 4
- (D) `samples` 包含 `5.4, 5.4`，且 `len` 为 2
- (E) `samples` 包含 `1.0, 2.1`，且 `len` 为 2

- 2. 在 OOP 中，程序员通常将类组织成继承层次结构，而不是直接实现类。以下何哪项**不是**这样做的有效理由？

- (A) 继承层次结构顶部的抽象类可以很容易在项目中扩展，或在其他项目中被复用。
- (B) 超类的方法可以在其子类中复用，而无需重复代码。
- (C) 来自不同子类的对象可以作为参数传递给设计接收超类对象的方法。
- (D) 来自不同子类的对象可以存储在同一个数组中。
- (E) 以上都是使用继承层次结构的有效理由。

- 3. 考虑以下方法，该方法用于近似非负 `double` 的平方根：

```java
public double squareRoot(double x)
{
    double x1 = 1, x2 = x;
    while (Math.abs(x1 - x2) > 0.001)
    {
        x2 = (x1 + x2) / 2;
        x1 = x / x2;
    }
    return x2;
}
```

以下哪项最好描述了 `while` 循环的不变性（invariant）？

- (A) `x1` 乘以 `x2` 等于 `x`
- (B) `x` 是 `x1` 和 `x2` 的平均值
- (C) `x2` 是 `x` 和 `x1` 的平均值
- (D) `|x1 - x2|` 的绝对值小于或等于 0.001
- (E) `|x1 - x2|` 的绝对值大于 0.001

- 4. 以下代码的输出是什么？

```java
ArrayList<Integer> list = new ArrayList<Integer>();
for (int i = 1; i <= 8; i++)
{
    list.add(new Integer(i));
}
for (int i = 0; i < list.size(); i++)
{
    list.remove(i);
}
for (Integer x : list)
{
    System.out.print(x + " ");
}
```

- (A) `IndexOfOutOfBoundsException`
- (B) 无输出，因为结果列表为空
- (C) 1 3 5 7
- (D) 2 4 6 8
- (E) 1 2 3 4 5 6 7 8

- 5. 以下哪种算法在最坏情况下运行时间为 $O(n)$？

- (A) 快速排序 (Selection Sort)
- (B) 插入排序 (Insertion Sort)
- (C) 快速排序 (Quicksort)
- (D) 合并排序 (Mergesort)
- (E) 堆排序 (Heapsort)

- 6. 一项任务是检查成界符（如括号）是否匹配。在编写检查括号的方法时，以下哪种数据结构最适合临时保存位置？

- (A) 列表 (List)
- (B) 栈 (Stack)
- (C) 队列 (Queue)
- (D) 实现为二叉树的集合
- (E) 实现为二叉树的映射

7-8 题参考以下方法：

```java
private int product(int n)
{
    if (n <= 1)
        return 1;
    else
        return n;
}
```

7. 调用 `product(6)` 的结果是什么？

- (A) 1
- (B) 6
- (C) 12
- (D) 48
- (E) 72

8. 以下何哪项解释了该结果？

- (A) 逻辑错误
- (B) 递归调用溢出
- (C) 整数范围
- (D) 整数溢出
- (E) 计算精度丢失

9. 关于接口和抽象类，以下哪项述是正确的？

- (A) 如果抽象类没有方法，最好将其变为接口。
- (B) 抽象类不能继承类。
- (C) 抽象类不能实现接口。
- (D) 你可以声明抽象类的数组，但不能声明接口。
- (E) 方法可以接收接口类型，但不能接收抽象类型。

10. 一个二维数组 `image` 存储像素值。像素值范围从 0 到 255。考虑以下方法：

```java
```



`public int findMax(int[][] image) {`

```
    int[] count = new int[256];
    int i, iMax = 0;
    for (int r = 0; r < image.length; r++) {
        for (int c = 0; c < image[0].length; c++) {
            i = image[r][c];
            count[i]++;
        }
    }
    for (int i = 1; i < 256; i++) {
        if (count[i] > count[iMax])
            iMax = i;
    }
    return iMax;
}
```

该方法计算的是什么？

- (A) `image` 中和最大的列
- (B) `image` 中像素的最大值
- (C) `image` 中任意 256 行的和
- (D) `image` 中任意 256x256 区域
- (E) `image` 中频率值

11. UPC 用于识别商品。假设 `GroceryItem` 类有一个私有实例变量 `upc`，代表该商品的唯一 UPC：

```java
public class GroceryItem {
    private String upc;
    // ... 其他实例变量、构造函数和方法
    // 未显示
}
```

如果我们想将其放入 `HashSet` 中，以下哪项描述了必须定义的方法集？

- (A) `hashCode`
- (B) `equals`
- (C) `hashCode` and `equals`
- (D) `equals` and `getUPC`
- (E) `compareTo` and `equals`

12. 考虑设计一种用于跟踪缺勤的数据结构。正在考虑两种设计：

设计 A：一个 `HashMap`，其中 `Integer` 代表学日，关联的值是包含该日期缺勤学生的 `ArrayList`，按字母顺序排序。

设计 B：一个按学生 ID 比较的学生记录 `TreeSet`。每个记录包含学生的姓名和一个按日期升序排列的缺勤日期 `LinkedList`。

需要实现以下操作：

- 操作 1：按字母顺序列出所有全勤学生。
- 操作 2：列出所有缺勤人数超过平均缺勤人数 30% 的学日。

以下何哪项是正确的？

- (A) 操作 1 使用设计 A 更高效；操作 2 使用设计 B 更高效。
- (B) 操作 1 使用设计 B 更高效；操作 2 使用设计 A 更高效。
- (C) 操作 1 和操作 2 使用设计 A 都比使用设计 B 更高效。
- (D) 操作 1 和操作 2 使用设计 B 都比使用设计 A 更高效。
- (E) 操作 1 和操作 2 使用任何一种设计都效率相同。

# 302 模拟考试~AB-2

13. 下列哪项描述了以下方法的返回值：

```
// 前提条件：root 指向一个非空的
// 二叉搜索树；
// 左子树不为空且
// 右子树不为空
public Object findX(TreeNode root) {
    TreeNode node = root.getRoot();
    while (node.getRight() != null)
        node = node.getRight();
    return node.getValue();
}
```

- (A) 树中的最大值
- (B) 树中的最小值
- (C) 树的左子树中的最大值
- (D) 树的右子树最小值
- (E) 距离根最右侧节点存储的值

14. 考虑以下方法

```
public boolean isOneOfKind(String word) {
    int len = word.length();
    return len < 2 || (word.substring(0,1).equals(word.substring(len-1)) &&
        isOneOfKind(word.substring(1, len-1)));
}
```

对于以下三个字符串，哪个会让 `isOneOfKind` 返回 true：`aviva`, `"annetta"`, `"annabelle"`:

- (A) 仅 `"aviva"`
- (B) 仅 `"annetta"`
- (C) `"aviva"` 和 `"annetta"` 都是
- (D) 三者都是
- (E) 三者都不是

15. 假设方法 `findFirstPositive` 返回数组中第一个正数的位置（或断言不存在正数）。前提是数组不包含任何负值，且所有的零（如果有）都位于所有正数之前。该方法通过将数组元素与 0 进行比较来工作。如果 `T(n)` 是保证任何包含 `n` 个元素的数组都能得到正确结果的比较次数（即使在最坏情况下），那么在最优算法中，`T(10)` 是多少？

- (A) 4
- (B) 5
- (C) 8
- (D) 9
- (E) 10

问题 16-19 基于以下类 `Table`，该类被用于另一个类 `Restaurant`。一个 `Restaurant` 对象维护着一个 `Table` 对象的数组，并跟踪餐厅内桌位的占用情况。

```
public class Table
{
    private final int numChairs;
    private int numGuests;
    private List<MenuItem> orderedItems;

    public Table(int n)
    {
        numChairs = n;
        numGuests = 0;
        orderedItems = new LinkedList<MenuItem>();
    }

    // 返回此桌的座位容量
    public int getNumChairs() { return numChairs; }

    // 返回此桌的客人数量
    public int getNumGuests() { return numGuests; }

    // 返回已点菜列表
    public List<MenuItem> getOrder() { return orderedItems; }

    // 为此桌增加 n 个客人
    // 前提条件：numGuests + n <= numChairs
    public void addGuests(int n)
    {
        numGuests += n;
    }

    // 将点菜项放入 orderedItems 列表中
    // 前提条件：numGuests > 0
    public void placeOrder(List<MenuItem> items)
    {
        orderedItems = items;
    }

    // 清空此桌
    public void clear()
    {
        numGuests = 0;
        orderedItems = new LinkedList<MenuItem>();
    }

    // 返回 orderedItems 列表中所有项的费用
    public double getBillAmt()
    /* 实现代码未显示 */
}
```

# 304 模拟考试 ~ AB-2

16. 下列表达式可以正确引用 `Table` 类方法中的第一个点菜项（假设 `orderedItems.size() > 0`）？

- I. `orderedItems.getFirst();`
- II. `orderedItems.get(0);`
- III. `orderedItems.iterator().next();`

- (A) 仅 I
- (B) 仅 II
- (C) I 和 II
- (D) II 和 III
- (E) I, II, 和 III

17. `Restaurant` 类声明并使用了一个 `Table` 对象的数组：

```java
public class Restaurant {
    private Table[] tables;
    public int numTables() { return tables.length; }
    // ... 等
}
```

`Restaurant` 的设计者决定提供以下私有方法 `getTable`：

```
// 返回此餐厅中的第 k 张桌子
private Table getTable(int k)
/* 实现未显示 */
```

程序员被指示在 `Restaurant` 代码的其他地方，调用 `numTables` 和 `getTable`，而不是直接引用 `tables` 数组。下列哪项最能描述这一决定的有效合理理由？

- (A) 更好的运行时代码效率
- (B) 更容易将 `Table[]` 替换为另一种结构（例如 `ArrayList`），且对 `Restaurant` 其他部分代码的改动最小
- (C) 更容易修改 `Restaurant` 的实现而不而不改变其客户端类
- (D) 在 `Restaurant` 的子类中调用 `getTable` 的可能性
- (E) 在 `Restaurant` 的子类中覆盖 `getTable` 的可能性

# 模拟考试 ~ AB-2 305

18. 假设一名程序员决定编写并测试 `Table` 构造函数以及两个 `Table` 方法，暂时将其他方法留空。以下哪对方法组合最适合首先进行测试？

- (A) `getNumGuests` 和 `addGuests`
- (B) `getChairs` 和 `addGuests`
- (C) `getOrder` 和 `placeOrder`
- (D) `addGuests` 和 `clear`
- (E) `getGuests` 和 `BillAmt`

19. 下列哪项是 `Restaurant` 类中 `seatParty` 方法的 `<condition>` 和 `<missing statement>` 最合适的替换？

```
// 将客人安排在第一个桌
// 如果成功返回 true，如果没有空间返回 false
// 前提条件：0
public boolean seatParty(int numPeople)
{
    for (int k = 0; k < numTables(); k++) {
        Table t = getTable(k);
        if (<condition>)\
            <missing statement>;
            return true;
        }
    }
    return false;
}
```

- (A) `t.numGuests == 0`
- (B) `t.Chairs(t) >= numPeople`
- (C) `t.numGuests() == 0`
- (D) `t.numGuests() > 0`
- (E) `t.Chairs() >= numPeople`

问题 20-23 参考以下类：

```
public class Party
{
    private List<String> guests;

    public Party() { guests = null; }
    public Party(List<String> guests) { guests = guests; }
    public void setGuests(List<String> guests) { guests = guests; }
    public String toString() {
        /* 实现未显示 */
    }
}

public class BDayParty extends Party
{
    private String name;

    public BDayParty(String name, List<String> guests) {
        /* 实现未显示 */
    }

    public String getName() { return name; }
    // 其他方法未显示
}
```

20. 给定

```
List<String> guests = new LinkedList<String>();
gests.add("Alice");
gests.add("Ben");
gests.add("Candy");
```

下列声明哪个无效？

- (A) `Party[] celebrations = new Party[2];`
- (B) `Party[] celebrations = {new Party(guests), new Party()};`
- (C) `BDayParty[] celebrations = {new BDayParty("Malika", guests), new Party(guests)};`
- (D) `BDayParty[] celebrations = {new BDayParty("Lee", guests), new BDayParty("Henry", guests)};`
- (E) 以上均有效。

21. 下列哪个语句可以替换 `BDayParty` 构造函数中的 `<missing statement >`？

```
public BDayParty(String name, List guests)
{
    <missing statement >
    thisName = name;
}
```

- I. `theGuests = guests;`
- II. `super (guests);`
- III. `setGuests(guests);`

- (A) 仅 I
- (B) 仅 II
- (C) I 和 II
- (D) II 和 III
- (E) I, II, 和 III

22. 假设我们决定将 `Party` 类设为抽象类，并对其添加了以下方法：

```
public abstract String getOccasion();
public String getMessage() { return "Happy"; }
public String greetings() { return getMessage() + " "
    + getOccasion(); }
```

为了让以下代码显示，`BDayParty` 类必须覆盖的 `Party` 方法最小集合是：

```
BDayParty birthday = new BDayParty("Aaron", guests);
System.out.println(birthday.greetings());
```

Happy Birthday Aaron

- (A) 无
- (B) `getOccasion`
- (C) `getMessage`
- (D) `getOccasion` and `getMessage`
- (E) `getOccasion`, `getMessage`, and `greetings`

23. `Party` 的 `toString` 方法列出了 `Guests` 列表中的所有条目。程序员应该使用迭代器（`iterator`）还是在循环中使用 `get(i)` 方法来遍历列表？

- (A) `get(i)`，因为它的效率总是效率高的
- (B) `get(i)`，因为迭代器仅适用于链表（linked lists）
- (C) 使用迭代器，因为在传递给构造函数的 `List` 实现中可能无法提供 `get(i)` 方法
- (D) 使用迭代器，当 `Guests` 恰好是 `LinkedList` 时，迭代器的效率更高
- (E) 两种方法都可以，且对于所有列表来说效率都相等

24. 下列哪个二叉树的先序遍历（preorder traversal）产生 `APCS`，且后序遍历（postorder traversal）产生 `CPSA`？

| | (A) | (B) | (C) | (D) | (E) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| | A | A | A | A | A |
| | / \ | / \ | / \ | / \ | / \ |
| | C P | P S | P P | P C | P C |
| | / | / | / | S | S |
| | S | S | | |

25. 假设提供了一个空栈，一个“输入”队列包含数字 1 2 3 4 5 6，其中 1 在队列的最前面。数字从输入队列中一个一个地取出，并根据某些标准直接进入“输出”队列或推入栈中。当输入队列中的所有数字处理完毕后，所有数字都发送到同一个输出队列中。下列哪个输出队列**不**可能的？

- (A) 1 2 3 4 5 6
- (B) 3 6 1 2 4 5
- (C) 1 2 3 6 5 4
- (D) 2 4 6 5 3 1
- (E) 1 6 5 4 3 2

26. 考虑以下方法：

```java
public ListNode mince(ListNode head)
{
    ListNode r = null, p = null;
    while (head != null)
    {
        r = head.getNext();
        head.setNext(p);
        p = head;
        head = r;
    }
    return p;
}
```

如果 `head` 指向一个具有五个节点的链表的第一个节点，`A -> B -> C -> D -> E`，则 `mince(head)` 返回的是哪个列表？

- (A) `A -> B -> C -> D -> E`
- (B) `E`
- (C) `A -> B -> C -> D`
- (D) `A -> B -> C -> D -> E`
- (E) `E -> D -> C -> B -> A`

27. 考虑以下方法：

```java



`public boolean hasPropertyX(TreeNode root)`

```
{
    if (root == null)
        return false;
    TreeNode left = root.getLeft();
    TreeNode right = root.getRight();
    return (left == null && right != null) ||
        hasPropertyX(left) || hasPropertyX(right);
}
```

`hasPropertyX(root)` 返回 `true` 当且仅当以 `root` 为根的二叉树：

- (A) 具有非空的左右子树
- (B) 至少有一个有两个子节点的节点
- (C) 不为空且其根节点不是叶子节点
- (D) 不为空且每个节点要么是叶子节点要么有两个孩子
- (E) 是一棵满树（full tree）

## 310 模拟考试 ~ AB-2

28. 考虑以下类：

```java
public class A
{
    private int myNum;
    public A (int x) { myNum = x; }
    public int getNumber() { return myNum; }
    public String getLetters() { return "A"; }
    public String getMessage() {
        return getLetters() + "-" + getNumber();
    }
}

public class AB extends A
{
    public AB (int x) { super(x + 1); }
    public int getNumber() { return super.getNumber() + 1; }
    public String getLetters() { return "AB"; }
}
```

以下代码段的输出是什么？

```java
A test = new AB(0);
System.out.print(test.getMessage());
```

- (A) A-0
- (B) A-1
- (C) A-2
- (D) AB-1
- (E) AB-2

29. 优先级队列由最小堆（min-heap）实现并包含 `n` 个项目。下列哪项描述了 `peek`、`remove` 和 `add` 方法的平均运行时间？

| | peek | remove | add |
| :--- | :--- | :--- | :--- |
| (A) | `O(1)` | `O(1)` | `O(1)` |
| (B) | `O(1)` | `O(1)` | `O(log n)` |
| (C) | `O(1)` | `O(log n)` | `O(log n)` |
| (D) | `O(log n)` | `O(log n)` | `O(log n)` |
| (E) | `O(1)` | `O(n)` | `O(n)` |

30. 考虑以下方法，它对给定的 `String` 对象列表进行排序并返回一个排序后的列表：

```java
public static List<String> sort(List<String> list)
{
    if (list.size() < 2)
        return list;
    List<String> listA = new LinkedList<String>();
    List<String> listB = new LinkedList<String>();
    Iterator<String> iter = list.iterator();
    String x = iter.next();
    while (iter.hasNext()) {
        String y = iter.next();
        if (y.compareTo(x) <= 0)
            listA.add(y);
        else
            listB.add(y);
    }
    listA = sort(listA);
    listB = sort(listB);
    listA.add(x);
    for (String y : listB) {
        listA.add(y);
    }
    return listA;
}
```

使用了哪种排序算法？

- (A) 选择排序 (Selection Sort)
- (B) 插入排序 (Insertion Sort)
- (C) 合并排序 (Mergesort)
- (D) 快速排序 (Quicksort)
- (E) 堆排序 (Heapsort)

## 312 模拟考试 ~ AB-2

31. 一程序员正在为大型音乐商店设计 CD 数据库。CD 对象由唯一标识代码、乐队或表演者名称、发布日期、歌曲列表、库存数量和零售价格描述。商店经理必须能够获取特定乐队的所有 CD 列表，快速检查具有特定标识代码 CD 的价格和可用性，并找到包含特定歌曲的 CD。程序员正在考虑以下结构的组合：

- S1: 按标识代码升序排列的所有 CD 的链表（`LinkedList`）。
- S2: 以标识代码为键的 `HashMap`。
- S3: 以乐队/表演者名称为键的 `HashMap`。对于每个乐队，它按发布日期倒序排列所有 CD 的列表。
- S4: 所有 CD 的 `TreeSet`。CD 应该按乐队名称进行比较，如果相同，则按发布日期比较。
- S5: 以歌曲名为键的 `HashMap`，将歌曲与包含该歌曲的 ID 代码列表关联。

上述结构的组合适用于此应用？

- (A) S1, S3, 和 S5
- (B) S1, S4, 和 S5
- (C) S2, S3, 和 S5
- (D) S2, S3, 和 S4
- (E) S3 和 S5

32. 下列哪个二叉树代表（最小）堆（heap）？

- (A) 仅 I
- (B) 仅 II
- (C) I 和 II
- (D) I 和 III
- (E) 三者都不是

33. `HashMap` 的构造函数之一接受两个参数：初始容量（桶的数量）——表中存储项目数量与其当前容量的最大允许比例。当比例超过负载因子（load factor）时，容量会自动增加（通常翻倍）并进行重哈（rehashed）。如果我们计划在表中存储大约 3000 个项目，下列初始容量和负载因子的值哪个是合理的，会导致冲突过多、空间浪费过多且确保不发生重哈？

- (A) 1500 和 2.0
- (B) 3000 和 0.5
- (C) 4000 和 0.5
- (D) 5000 和 0.75
- (E) 30000 和 0.2

34. 以下代码段的输出是什么？

```java
Map<Integer, String> map = new TreeMap<Integer, String>();
map.put(new Integer(1), "A");
map.put(new Integer(1), "B");
map.put(new Integer(2), "B");
for (Integer key : map.keySet()) {
    System.out.print(map.get(key) + " ");
}
```

- (A) 1 2
- (B) 1 2
- (C) A B
- (D) B B
- (E) A B

## 314 模拟考试 ~ AB-2

问题 35-40 指的是 GridWorld 案例中的代码。

35. Pat 从一个空的 3x3 网格开始，并在其中创建了一个 `Bug`。在三步之后，下列哪种配置是不可能的？

- (A)
- (B)
- (C)
- (D)
- (E)

36. `JumpingBug` 是 `Bug` 的子类。`JumpingBug` 通常像普通 `Bug` 一样行动，偶尔以某种概率尝试向前跳两步。跳转的概率保存在实例字段 `probOfJumping` 中。`JumpingBug` 只有在可以移动时才会跳转。如果无法跳转，`JumpingBug` 像普通 `Bug` 一样行动。以下哪些 `JumpingBug` 实现方法有效？

I. 只重写 `Bug` 的 `act` 方法，如下：

```java
public void act()
{
    super.act();
    if (Math.random() < probOfJumping)
        move();
}
```

II. 只重写 `Bug` 的 `act` 方法，如下：

```java
public void act()
{
    if (canMove())
        move();
        if (Math.random() < probOfJumping && canMove())
            move();
    else
        turn();
}
```

III. 只重写 `Bug` 的 `move` 方法，如下：

```java
public void move()
{
    super.move();
    if (Math.random() < probOfJumping && canMove())
        super.move();
}
```

- (A) 仅 I
- (B) 仅 II
- (C) I 和 II
- (D) II 和 III
- (E) I, II, 和 III

37. 假设我们修改了 `Critter` 中的 `act` 和 `makeMove` 方法。我们将对 `getMoveLocations` 和 `selectLocation` 的调用放入 `makeMove` 中，而不是 `act` 中，如下：

```java
public void act() {
    if (getGrid() == null)
        return;
    ArrayList<Actor> actors = getActors();
    processActors(actors);
    // ArrayList<Location> moveLoc = getMoveLocations();
    // Location loc = selectMoveLocation(moveLoc);
    // makeMove(loc);
    makeMove();
}

// public void makeMove(Location loc)
public void makeMove() {
    ArrayList<Location> moveLocs = getMoveLocations();
    Location loc = selectMoveLocation(moveLocs);
    if (loc == null)
        removeSelfFromGrid();
    else
        moveTo(loc);
}
```

那么，所有重写了 `makeMove` 的 `Critter` 子类都需要修改。还有哪些 `Critter` 的子类需要修改？

- (A) 无需
- (B) 所有重写了 `getMoveLocations` 的子类
- (C) 所有重写了 `selectLocation` 的子类
- (D) 所有重写了 `getMoveLocations` 和 `selectLocation` 的子类
- (E) 所有重写了 `getMoveLocations` 或 `selectLocation`（或两者都）的子类

38. 有人对 GridWorld 代码进行了实验并对 `Location` 类进行了更改。代码仍然可以正确编译，但 `BugRunner` 在无边界网格中显示出意外之外的行为：如果一个 bug 面前有一块石头，它会“爬过石头”并在第二步出现在石头的另一侧，而不是在石头面前改变方向。该程序在边界网格中运行正常。`Location` 类中的以下哪种更改可能导致这种行为？

- (A) 删除了 `implements Comparable`
- (B) `NORTH` 的值从 0 变为了 180
- (C) `HALF_LEFT` 和 `HALF_RIGHT` 的值分别从 -45 变为 -90，从 45 变为 90
- (D) `compareTo` 方法被注释掉了
- (E) `hashCode` 方法被注释掉了

39. 一个毛毛虫（`Caterpillar`）演员具有 `Bug` 和 `Critter` 的特征。毛毛虫首先“吃掉”相邻位置上所有的花（身后位置除外），然后，如果可能，就向前移动到相邻位置并在后面留下一朵花。如果前面的位置被占用，毛毛虫将留在原地并向右转 45 度。毛毛虫可以实现为 `Bug` 的子类，也可以实现为 `Critter` 的子类。这两种实现分别大约需要多少行代码（不包括大括号、注释和导入语句）？

| extends Bug | extends Critter |
| :--- | :--- | :--- |
| (A) | 10 | 10 |
| (B) | 10 | 30 |
| (C) | 20 | 30 |
| (D) | 30 | 50 |
| (E) | 50 | 50 |

40. 考虑一种边界网格的替代设计，其中每行的数据被表示为该行所有 `Actor` 的链表（`LinkedList<Actor>`），按列顺序排序，且行存储在数组中（`LinkedList<Actor>[]`）。假设网格有 `n` 行 `n` 列并持有 `2n` 个 `Actor`。原始设计中 `getOccupiedLocations` 方法与替代设计最高效实现的时间复杂度（Big-Oh）分别是什么？

| 原始： | 替代： |
| :--- | :--- |
| (A) | `O(n)` | `O(n)` |
| (B) | `O(n²)` | `O(n)` |
| (C) | `O(n log n)` | `O(n²)` |
| (D) | `O(n²)` | `O(n log n)` |
| (E) | `O(n²)` | `O(n²)` |

## 模拟卷 AB

计算机科学 AB
第二部分

时间 — 1 小时 45 分钟
题目数量 — 4
占总分百分比 — 50

1. 本题涉及一个由圆盘组成的金字塔生产线模拟。圆盘由 `Disk` 类的对象表示。`Disk` 类有一个构造函数，接受一个 `int` 参数，即圆盘的半径。`Disk` 对象实现了 `Comparable` 接口：半径较小的圆盘被认为更小。`Tower` 创建了一个圆盘堆栈（`Tower` 类继承自 `java.util.Stack<Disk>` 类）。`Tower` 的无参数构造函数创建一个空塔。在这个应用程序中，所有的“塔”都是按大小顺序排列的圆盘“金字塔”。在“常规”金字塔中，圆盘的大小从上到下逐渐增大；在“倒置”金字塔中，大小则减小，如下所示：

“常规”金字塔
“倒置”金字塔

圆盘在生产线上到达，并由机器人组装成金字塔。生产线由一个包含 `Disk` 对象的 `Queue` 表示。机器人可以临时构建并持有一个倒置的圆盘金字塔，由 `Tower` 对象表示。当它发现无法在保持大小顺序的情况下添加另一个圆盘时，机器人会“翻转”它所持的金字塔并将其放入输出生产线，输出生产线同样由 `Queue` 表示。该输出队列包含由 `Tower` 对象表示的常规金字塔。该过程如下所示。

```java
import java.util.*;

public class ProductionLine
{
    private Queue<Disk> assemblyIn;
    private Queue<Tower> assemblyOut;
    private Tower robotArm;

    // 初始化此 ProductionLine，使得
    // assemblyIn 包含半径在 1 到 maxRadius 之间的
    // nDisks 个随机圆盘；assemblyOut
    // 初始化为空塔队列。
    // robotArm 初始化为空 Tower
    public ProductionLine(int nDisks, int maxRadius) {
        // ... 部分 (a)
    }

    // 翻转 robotArm 中的金字塔并将其添加到
    // assemblyOut 队列
    // 前提条件：robotArm 不为空且持有一个
    // 倒置金字塔。
    private void unloadRobot() {
        // ... 部分 (b)
    }

    // 处理 assemblyIn 中的圆盘；圆盘的
    // 处理如下：如果 robotArm 为空，或者下一个圆盘
    // 可以放在 robotArm 顶部并保持其倒置金字塔顺序，
    // 则该圆盘被 robotArm 拾起。否则，在处理完
    // 所有圆盘后，robotArm 也会卸载。
    // 前提条件：robotArm 为空；
    // assemblyLineOut 为空
    public void process() {
        // ... 部分 (c)
    }
}
```

2. 字典可以表示为一个映射（map），其中每个单词都对应其在另一种语言中的所有翻译。例如，在英语-西班牙语字典中，`holiday` 可能对应 {`fiesta`, `vacaciones`}；在西班牙语-英语字典中，`fiesta` 可能对应 {`holiday`, `party`, `celebration`, `feast`}。在字典映射中，单词是一个键（key），而其翻译集合是与该键关联的“值”（value）。假设字典实现为 `TreeMap`，且每个单词的翻译集合被实现为 `TreeSet`。

(a) 编写一个方法，接收一个字典并向其添加一个翻译。

补全下面的方法。

```java
// 如果 word 是键之一，则向其翻译集合中添加翻译；
```



// 否则为 `word` 创建新条目，
// 并将其与一个包含单个元素的集合（一个 `TreeSet`）关联，该翻译
// 前置条件: `dictionary != null`

```
public static void add(Map<String, Set<String>> dictionary,
    String word, String translation)
```

(b) 编写一个方法，接收一个字典并生成一个反向字典。反向字典使用与原始字典相同的结构，对于原始字典中的每个对 (`单词`, `翻译`)，在反向字典中有一个对应的反向对 (`翻译`, `单词`)。例如，如果你在英语-西班牙语字典中找到 `holiday -> fiesta`，你应该能够在其反向的西班牙语-英语字典中找到 `fiesta -> holiday`。你可以假设部分 (a) 中的 `add` 方法在同一个类中并按规范定义。

补全下面的 `reverse` 方法。

```java
// 并且满足以下属性：`word2` 在与 `word1` 关联的
// 翻译集合中，当且仅当 `word2` 在
// 原始字典与 `word2` 关联的翻译集合中。
// 前置条件: `dictionary != null`
// `dictionary` 为每个单词关联一个
// 翻译的 `TreeSet`。

public static Map<String, Set<String>>
    reverse(Map<String, Set<String>> dictionary)
```

---

# 324 模拟考试 ~ AB-2

3. 此题涉及对 `GridWorld` 案例研究代码的推理。代码的副本作为考试的一部分提供。

扫雷电脑游戏在一个二维单元格网格上进行。网格中的若干单元格隐藏了“地雷”。当玩家点击一个单元格时，其内容会被揭露：如果它包含地雷，游戏结束；否则，计算机会在单元格中显示相邻八个位置上的地雷总数。

使用以下类来表示网格中的单元格：

```java
public class MinesweeperCell {

    // 创建一个不包含地雷且
    // 被标记为关闭的单元格
    public MinesweeperCell()
    {
        /* 代码未显示 */
    }

    // 将此单元格标记为雷
    public void setMine()
    {
        /* 代码未显示 */
    }

    // 如果此单元格包含雷则返回 true
    public boolean isMine()
    {
        /* 代码未显示 */
    }

    // 将此单元格标记为打开
    public void open()
    {
        /* 代码未显示 */
    }

    // 如果此单元格已打开则返回 true
    public boolean isOpen()
    {
        /* 代码未显示 */
    }

    // 字段和其他方法未显示
}
```

`MinesweeperBoard` 类对游戏板进行建模。该类实现为 `BoundedGrid<MinesweeperCell>` 的子类。

`MinesweeperBoard` 类的部分定义如下：

```java
public class MinesweeperBoard
    extends BoundedGrid<MinesweeperCell>
{
    // 构建一个包含 10 个地雷的 9x9 网格；
    // 在每个网格位置放置一个新的 MinesweeperCell，
    // 然后在随机选择的位置放置 10 个地雷
    public MinesweeperBoard()
    {
        /* 将在部分 (a) 中实现 */
    }

    // 构建一个包含 nMines 个地雷的 nRows 行 nCols 列的网格；
    // 在每个网格位置放置一个新的 MinesweeperCell，
    // 然后在随机选择的位置放置 nMines 个地雷
    public MinesweeperBoard(int nRows, int nCols, int nMines)
    {
        /* 将在部分 (a) 中实现 */
    }

    // 返回 loc 周围的八个邻居中
    // 地雷的总数
    private int getMineCount(Location loc)
    {
        /* 将在部分 (b) 中实现 */
    }

    // 如果 loc 已经打开，返回 0；否则 loc 含有
    // 雷，返回 -1；否则打开 loc；
    // 如果 loc 邻居的地雷数量为 0，
    // 揭露其所有邻居，如果其中某些显示为 0，
    // 则揭露它们的邻居，以此类推；返回总数
    public int reveal(Location loc)
    {
        /* 将在部分 (c) 中实现 */
    }

    // 其他方法未显示
}
```

- (a) 编写 `MinesweeperBoard` 类的两个构造函数。创建一个包含 10 个地雷的 9x9 网格。第二个构造函数接收三个参数：网格的行和列维度以及要种植的地雷数量。使用一个私有辅助方法来避免两个构造函数中的代码重复。

补全构造函数和 `initialize` 方法。

```java
// 构建一个包含 10 个地雷的 9x9 网格；
// 在每个网格位置放置一个新的 MinesweeperCell，
// 然后在随机选择的位置放置 10 个地雷
public MinesweeperBoard()
```

```java
// 构建一个包含 nMines 个地雷的 nRows 行 nCols 列的网格；
// 在每个网格位置放置一个新的 MinesweeperCell，
// 然后在随机选择的位置放置 nMines 个地雷
public MinesweeperBoard(int nRows, int nCols, int nMines)
```

---

# 326 模拟考试 ~ AB-2

- (b) 编写 `getMineCount` 方法，返回给定位置周围八个邻居中的地雷数量。补全下面的方法。

```java
// 返回 loc 周围八个
// 邻居的地雷数
private int getMineCount(Location loc)
```

- (c) 在扫雷游戏中，每当玩家点击一个单元格且数量为 0 时，揭露其所有邻居，如果其中某些显示为 0，则揭露它们的邻居，以此类推；返回打开的区域总数。例如，下图显示了点击后的棋盘。

(image/320d34bf6289b0c4a1d8b2b59c339.png)

如果位置已打开，返回 0；如果位置包含雷，返回 -1；否则打开位置，找到其周围的地雷数量，以此类推。补全下面的 `reveal` 方法。

```java
// 如果 loc 已经打开，返回 0；否则 loc 含有
// 雷，返回 -1；否则打开 loc；
// 如果 loc 邻居的地雷数量为 0，
// 揭露其所有邻居...返回在此调用中位置的总数
public int reveal(Location loc)
```

---

# 328 模拟考试 ~ AB-2

4. 一个实验由多次投掷硬币，直到连续出现同一面。一组实验保存在二叉树中。正面和反面的序列表示为从根节点的路径：正面代表左，反面代表右。对于每次实验，构建（或回溯）一条路径并增加结束节点的值。例如，该实验对应于右所示的二叉树。

(image/320d34bf6289b0c4a1d8b2b59c341.png)

我们将代表投硬币的树称为“HT树”。我们将 `HT` 树的每个节点表示为具有 `Integer` 值的 `TreeNode`。

(a) 编写一个方法从非空 `HT` 树中提取统计数据。`getStats` 方法返回一个包含四个整数的数组：最长实验的投掷次数、实验的总数、所有实验中正面的总数以及所有实验中反面的总数。例如，对于上面的 `HT` 树，`getStats` 可以返回如下值的数组：`[5,6,11,8]`。注意 `getStats` 可以直接从树中提取这些统计数据，而无需重建实验组。例如，`stats[0]` 是树中最长路径的长度；`stats[1]` 是树中所有节点的值和，以此类推。按照下方完成 `getStats`。

```java
// 返回长度为 4 的数组 stats
// stats[0] = 最长实验的投掷次数
// stats[1] = 实验的总数
// stats[2] = 所有实验中正面的总数
// stats[3] = 所有实验中反面的总数
// 前置条件: root 指向非空
// “投硬币”树
public static int[] getStats(TreeNode root)
```

---

(b) 这部分涉及一个方法 `isHTree`，该方法用于验证给定的二叉树是否为 `HT` 树。记住，每个 `HT` 树的叶节点持有正值，其他节点持有零，且任何路径在相同方向上恰好终止两个链接。

`isHTree` 使用了一个重载的递归辅助方法，该方法接受一个额外的参数，描述最后一段（方向改变后）到为止经过的路径。到为止的路径用 `String` 表示。在开始时，路径为空。因此，`isHTree` 方法可以写如下：

```java
// returns true if root refers to the root of an HT tree;
// otherwise returns false
// precondition: root != null;
public static boolean isHTree(TreeNode root)
{
    return isHTree(root, "");
}
```

在随后的递归调用中，到为止为止的路径包含一个或两个描述路径的字母："L" 表示左分支，"R" 表示右分支。请完成下方所示的重载辅助方法 `isHTree`。

```java
// returns true if root is null or if this tree fits as
// a subtree in an HT tree, as described by path
// precondition: root is either null or refers to a
// subtree of a binary tree;
// path describes the path traveled to
// root after the last direction change --
// it can be an empty string, "L",
// "R", "LL", or "RR"
private static boolean isHTree(TreeNode root, String path)
```

---

# 答案与解析

# A-1

# 第一部分：单选题

```
+ 1. D  11. E  21. E  31. E
  2. B  12. D  22. C  32. A
  3. C  13. C  23. E  33. E
  4. A  14. C  24. E  34. C
  5. D  15. B  25. C  35. A
  6. B  16. E  26. E  36. A
  7. A  17. B  27. A  37. A
  8. A  18. D  28. B  38. B
  9. B  19. C  29. D  39. C
  10. D 20. B  30. E  40. D
```

# Notes：

- 1. `len` 是按值传递的。
- 4. `Fun` 可以有 `compareTo` 方法，但没有实现 `Comparable<Fun>`。
- 8. `url.substring(0,0)` 返回一个空字符串。
- 14. 每个 `act` 对内 4 次 + 每个四元组对内 2 次 + 顶层 1 次。
- 15. 40 + 40 对两部分进行排序 + 0.01 * 2000 = 20 用于合并。
- 19. 将调用父类的 `compareTo`，它返回大小差，2000 - 1800 = 200。
- 20. 不能将 `House` 赋值给 `HouseFor`。
- 23. 使用德·摩根定律并注意短路求值。
- 25. 当 `bug` 无法移动时，`act` 转了两次，因为 `super.act` 转向了它。它调用了 `SuperBug` 的 `turn`，而 `turn` 覆盖了 `Bug` 中的 `turn`。
- 27. `ChameleonCritter` 的默认无参构造函数调用 `Critter` 的默认无参构造函数，后者又调用了 `Actor` 的构造函数。
- 32. 在 II 和 III 中，修改了局部变量 `s`，但没有修改列表中对应的元素。
- 35. 对于操作 3，使用二分查找在排序后的列表中找到两个玩家（设计 B）所需的时间比在设计 1 中即使找到第一个玩家还要短。
- 40. 选项 I 已经有保证了。

---

# A-1

# 第二部分：简答题

**1. (a)**

```java
public boolean isValidGrid(){
    Grid<Actor> gr = getGrid();
    if (gr == null)
        return false;
    ArrayList<Location> occupiedLocs = gr.getOccupiedLocations();
    for (Location loc : occupiedLocs) {
        Actor a = gr.get(loc);
        if (!a instanceof Rock || (a instanceof Flower && a != this))
            return false;
    }
    return true;
}
```

**(b)**

```java
public void moveLeft(){
    setDirection(getDirection() + LEFT);
    move();
}
```

**Notes:**

- 或者：
```java
setDirection(getDirection() - 90);
```

**(c)**

```java
public boolean canLeft() {
    Grid<Actor> gr = getGrid();
    if (gr == null)
        return false;
    Location loc = getLocation();
    Location next = loc.getAdjacentLocation(getDirection() - 90);
    Location corner = loc.getAdjacentLocation(getDirection() - 35);
    return (gr.isValid(next) && !(gr.get(next) instanceof Rock)) || gr.get(corner) instanceof Rock;
}
```

**Notes:**

- 或者：
```java
Location next = loc.getAdjacentLocation(getDirection() + LEFT);
```

- 另一种解决方案：
```java
public boolean canLeft() {
    Grid<Actor> gr = getGrid();
    if (gr == null)
        return false;
    Location loc = getLocation();
    Location next = loc.getAdjacentLocation(getDirection() - 90);
    Location corner = loc.getAdjacentLocation(getDirection() - 35);
    if (!gr.isValid(next) || (gr.get(next) instanceof Rock))
        return false;
    if (gr.get(corner) instanceof Rock)
        return false;
    return true;
}
```

**(d)**

```java
public void turn() {
    super.turn();
}
```

---

# 答案与解析

# A-1

**2. (a)**

```java
public int distance(Student other) {
    if (this.equals(other))
        return Math.abs(getNumber() - other.getNumber());
    else
        return 99;
}
```

**(b)**

```java
public class SchoolBus {
    private int numSeats;
    private ArrayList<Student> students;

    public SchoolBus(int capacity) {
        numSeats = capacity;
        students = new ArrayList<Student>(capacity);
    }

    public int getNumStudents() { return students.size(); }
    public boolean isFull() { return getNumStudents() == numSeats; }
    public Student getStudent(int i) { return students.get(i); }
    public boolean add(Student student) {
        if (!isFull()) {
```



进入`/path/to/xxx`目录，找到`xxx.json`。

在表达式`cvar = avar + bvar`中，加法运算符（`+`）将`avar`与`bvar`相加，得到它们的和`cvar`

在`List.of(arg0, arg1, arg2)`中，`List`接口的工厂方法`of()`接受一系列的元素，返回包含它们的只读列表。

之后我们这样调用`cmd`命令：`cmd arg0 arg1 arg2`。

```
if (condVar > someVal) {console.log("xxx")}
```

---

```
students.add(student);

return true;

}

return false;

}

public void printOut() {

for (Student s : students)

System.out.println(s);

}

}
```

Notes:

+ 1. 或者：
```java
boolean enroll(Student student) {

int minDistance = 10000;

SchoolBus bestBus = null;

for (SchoolBus bus : buses) {

if (!bus.isFull()) {

for (int i = 0; i < bus.getNumStudents(); i++) {

int d = student.distance(bus.getStudent(i));

if (d < minDistance) {

minDistance = d;

bestBus = bus;

}

}

}

}

if (bestBus != null) {

bestBus.add(student);

return true;

}

return false;

}
```

# 答案与解析

# A-1

3. (a)

```java
public class FlatRateEnv extends PriorityMail {

public FlatRateEnv() { super(1.0, 1); }

}

public class FlatRateBox extends PriorityMail {

public FlatRateBox() { super(1.0, 1); }

}

public double calculatePostage() {

return 2 * super.calculatePostage();

}
```

(b)

```java
public class InsuredMail extends Mail {

private Mail piece;

private int amount;

public InsuredMail(Mail p, int amt) {

piece = p;

amount = amt;

}

public double calculatePostage() {

double insCost = 0.50 * ((amount + 99) / 100);

return piece.calculatePostage() + insCost;

}

}
```

Notes:

+ 1. 或者，稍微长一点但可能更直观：
```java
double insCost = 0;

int amt = amount;

while (amt > 0) {

insCost += 0.50;

amt -= 100;

}
```

+ 4. (a)

```java
public static int countHits(ArrayList<String> text, String word) {

int count = 0;

for (String s : text) {

if (word.equals(s))

count++;

}

return count;

}
```

+ (b)

```java
public static String mostFrequent(ArrayList<String> text) {

int maxCount = 0;

String freqWord = null;

for (String word : text) {

int count = countHits(text, word);

if (count > maxCount) {

maxCount = count;

freqWord = word;

}

}

return freqWord;

}
```

+ (c)

$n^2$

```java
public static String extraFrequent(ArrayList<String> text) {

int n = text.size();

if (n <= 2)

return text.get(0);

if (n % 2 != 0) {

String word = text.get(n - 1);

if (countHits(text, word) > n / 2)

return word;

}

ArrayList<String> newText = new ArrayList<String>();

for (int i = 0; i < n - 1; i += 2) {

if (text.get(i).equals(text.get(i + 1)))

newText.add(text.get(i));

}

return extraFrequent(newText);

}
```

# 答案与解析

# A-2

## 第一部分：多选题

- 1. A 11. E 21. E 31. E
- 2. D 12. E 22. D 32. D
- 3. B 13. A 23. B 33. B
- 4. A 14. C 24. C 34. C
- 5. A 15. B 25. E 35. C
- 6. C 16. E 26. A 36. E
- 7. A 17. D 27. B 37. B
- 8. C 18. A 28. E 38. A
- 9. C 19. B 29. E 39. A
- 10. D 20. D 30. D 40. B

## Notes：

- 31. 使用德·摩根定律（De Morgan's Laws）。
- 12. `START_POS` 被声明为 `final`。
- 13. 在 `for` 循环之后，`w` 的值为 "banana"。
- 19. 强制转换为 int 会向零方向截断 double 值。
- 20. 选项 III 中没有打印 10，这一点不太明显。
- 28. 例如，如果 `getGetors` 和 `processActors` 必须是空方法，在新的设计中你只需要重写 `processActors`。
- 29. 记住 `ChameleonCritter` 会转向移动的方向，所以如果你从 `Critter` 派生 `RockChameleonCritter`，你可以重写 `methodName`。你可以在 `getActors` 中只选择石头，也可以在 `processActors` 中只考虑石头。
- 30. `LibraryBook` 没有重写 `Object` 的 `toString`，所以 `i` 是错误的。
- 33. `list.remove(i)` 减少了之后所有的下标，`i++` 跳过了该值。
- 36. 代码进入了死循环。
- 37. 对于选项 B，编译器会报告错误。
- 39. 首先将 "Boris" 与 "Evan" 交换，然后将 "Boris" 与 "Dan" 交换。
- 40. 4+3+2+1 = 10

# A-2

## 第二部分：简答题

- 1. (a)

```java
public boolean isFull()

{

for (ParkingLevel level : levels)

{

if (level.isEmptySpace() != -1)

return false;

return true;

}

}
```

- (b)

```java
public boolean parkCar(Car v)

{

if (isFull() || isCarAlreadyParked(v.getID()))

return false;

for (ParkingLevel level : levels)

{

int spaceNum = level.findEmptySpace();

if (spaceNum != -1)

{

level.setCar(spaceNum, v);

totalCars++;

return true;

}

}

return false;

}
```

```java
public Car removeCar(String id)

{

for (ParkingLevel level : levels)

{

for (int spaceNum = 0; spaceNum < level.numSpaces(); spaceNum++)

{

Car car = level.getCar(spaceNum);

if (car != null && id.equals(car.getID()))

{

level.setCar(spaceNum, null);

totalCars--;

return car;

}

}

}

return null;

}
```

- 2. (a)

```java
public static String findFirstTag(String text)

{

int tagStart = text.indexOf("<");

if (tagStart != -1)

{

int tagEnd = text.indexOf(">");

return text.substring(tagStart, tagEnd + 1);

}

else

return null;

}
```

- (b)

```java
public static String remove(String text, String str)

{

int pos = text.indexOf(str);

if (pos != -1)

{

text = text.substring(0, pos) +

text.substring(pos + str.length());

}

return text;

}
```

- (c)

```java
public static String removeAllTags(String text)

{

String tag = findFirstTag(text);

while (tag != null)

{

String closingTag = "/" + tag.substring(1);

if (text.indexOf(closingTag) <= text.indexOf(tag))

throw new IllegalArgumentException();

text = remove(text, tag);

text = remove(text, closingTag);

tag = findFirstTag(text);

}

return text;

}
```

## Notes：

- 1. 不仅仅是 `remove(text, tag);`，因为 String 对象是不可变的。

- 3. (a)

```java
public class Dahlia extends Flower

{

private Color initColor;

private int age;

public Dahlia() {

...

}

public Dahlia(Color color) {

...

}

public void act() {

...

}

}
```

- (b)

```java
public Dahlia() {

initColor = getColor();

}

public Dahlia(Color color) {

super(color);

initColor = color;

}
```

## Notes：

- 1. 或者使用 `setColor(color);`

- (c)

```java
public void act()

{

age++;

if (age < 4) {

super.act();

} else {

Grid gr = getGrid();

ArrayList<Location> locs = gr.validLocations();

int n = locs.size();

if (n > 0) {

for (int k = 1; k <= 3; k++) {

int r = (int)(Math.random() * n);

Location loc = locs.get(r);

if (gr.get(loc) == null) {

Dahlia seed = new Dahlia(initColor);

seed.putInGrid(gr, loc);

}

}

}

}

}

removeFromGrid();
```

- 4. (a)

```java
public class Student

{

private String studentName;

public Student(String name) { ... }

public String getName() { ... }

public void setName(String name) { ... }

}
```

# 答案与解析

# A-3

## 第一部分：多选题

- 1. B 11. D 21. B 31. D
- 2. C 12. C 22. B 32. C
- 3. A 13. C 23. D 33. E
- 4. B 14. A 24. D 34. E
- 5. E 15. D 25. B 35. B
- 6. E 16. E 26. A 36. C
- 7. D 17. B 27. E 37. B
- 8. C 18. A 28. B 38. A
- 9. A 19. C 29. D 39. D
- 10. E 20. A 30. D 40. A

## Notes：

- 2. 使用德·摩根定律（De Morgan's Laws）。
- 5. `count++` 缺失了。
- 8. 短路求值。
- 10. 4/3 得 1。
- 12. `filter` 删除了 `str` 中所有的 `pattern`。
- 24. `s` 是一个数组（A）；`Sample` 是私有的（C）；`Sample` 没有公有字段（E）。
- 26. `numbers` 包含两个元素：值为 1 的 Integer 拷贝。`str` 删除了索引 1。
- 28. 两个方法的签名与 TV 接口不同。
- 31. “动态绑定”是实现多态的技术。MBS 倾向于这个术语。
- 33. `msg[0]` 未初始化（null）；无法调用它的方法。
- 35. `BoxBug` 只有一个构造函数，且接受一个 int 参数。
- 39. `Actor` 没有 `setGrid` 方法。

# A-3

## 第二部分：简答题

- 1. (a)

```java
public abstract class PhoneCall

{

private int duration;

public PhoneCall(int mins) { duration = mins; }

public int getDuration() { return duration; }

public abstract double getRate();
```



```java
private int getTotal() {
    return (int) (getDuration() * getRate() + .5);
}

public String toString() {
    return "Duration " + getDuration() + " Rate " + getRate()
        + " Total " + getTotal();
}
```

- (b)

```java
public class LongDistanceCall extends PhoneCall {
    public LongDistanceCall(int mins) {
        super(mins);
    }

    public double getRate() {
        return 6.0;
    }

    public String toString() {
        return super.toString() + " LD";
    }
}
```

```java
public class ReducedRateCall extends LongDistanceCall {
    public ReducedRateCall(int mins) {
        super(mins);
    }

    public double getRate() {
        return 0.5 * super.getRate();
    }

    public String toString() {
        return super.toString() + "RR";
    }
}
```

# 答案解析 ~ A-3 349

## 2. (a)

```java
public static String toZodiacString(int year) {
    return animals[(year - startYear) % 12] + ", "
        + elements[(year - startYear) % 10);
}
```

## 2. (b)

```java
public String shortZodiac(int year) {
    String z = ChineseZodiac.toZodiacString(year);
    String animal = z.substring(0, z.indexOf(","));
    String element = z.substring(z.indexOf(",")) + 1);
    return animal + "-" + element;
}
```

## 2. (c)

```java
public int getYear(int year, String animal, String element) {
    for (int y = year; y < year + 60; y++) {
        String z = ChineseZodiac.toZodiacString(y);

        if (z.indexOf(animal) != -1 && z.indexOf(element) != -1) {
            return y;
        }
    }

    return 0;
}
```

# 350 答案解析 ~ A-3

## 3. (a)

```java
public void processActors(ArrayList<Actor> actors) {
    for (Actor a : actors) {
        if (a instanceof Clover) {
            ((Clover) a).pollinate();
        }
    }
}
```

## 3. (b)

```java
public Location selectMoveLocation(ArrayList<Location> locs) {
    Location next = getLocation();
    Location cloverLoc = findNearestClover(next);

    if (cloverLoc == null) {
        return next;
    }

    int minDistance = distance(next, cloverLoc);

    for (Location loc : locs) {
        int d = distance(loc, findNearestClover(loc));

        if (d < minDistance) {
            minDistance = d;
            next = loc;
        }
    }

    return next;
}
```

## 3. (c)

```java
public void makeMove(Location loc) {
    setDirection(getLocation().getDirectionToward(loc));
    super.makeMove(loc);
}
```

# 4. (a)

```java
public DataPacket getBestPacket(double minIntelFactor) {
    DataPacket bestPacket = null;
    double bestIntelFactor = minIntelFactor;

    for (DataPacket packet : dataPackets) {
        double intelFactor = packet.getIntelFactor();

        if (intelFactor > bestIntelFactor) {
            bestIntelFactor = intelFactor;
            bestPacket = packet;
        }
    }

    return bestPacket;
}
```

## 4. (b)

```java
public int filterList(int minStrength, int minDuration) {
    int i = 0;
    int count = 0;

    while (i < dataPackets.size()) {
        DataPacket packet = dataPackets.get(i);

        if (packet.getStrength() < minStrength
                || packet.getDuration() < minDuration) {
            dataPackets.remove(i);
            count++;
        } else {
            i++;
        }
    }

    return count;
}
```

```java
public ArrayList<DataPacket> alienMessage(
        double minIntelFactor, int minStrength, int minDuration) {
    filterList(minStrength, minDuration);

    DataPacket bestPacket = getBestPacket(minIntelFactor);

    if (bestPacket == null) {
        return null;
    }

    ArrayList<DataPacket> msg = new ArrayList<DataPacket>();

    for (DataPacket packet : dataPackets) {
        if (packet.getSource().equals(bestPacket.getSource())
                && packet.getQuadrant() == bestPacket.getQuadrant()) {
            msg.add(packet);
        }
    }

    return msg;
}
```

# 答案与解析

## AB-1

### 第一部分：单选题

- 1. D　11. E　21. C　31. C
- 2. D　12. A　22. E　32. D
- 3. C　13. E　23. E　33. E
- 4. D　14. E　24. E　34. E
- 5. B　15. B　25. A　35. B
- 6. D　16. B　26. E　36. B
- 7. D　17. A　27. D　37. D
- 8. B　18. E　28. B　38. C
- 9. E　19. C　29. A　39. A
- 10. D　20. C　30. C　40. D

### 注意事项

1. 如果基准始终选择距离中位数很远，快速排序可能会退化为 `O(n^2)`。
2. 唯一的选择是在 B 和 C 之间。如果 `searchVal` 大于列表中的任何值，则 `first = list.size()`，这正是我们需要的。
3. 从根节点开始的最长路径是 22, 30, 34, 51, 45。
4. 必须先减，后增。
5. 在任何二叉搜索树（BST）中，最小节点没有左子节点。对于完全树，任何节点都有左子节点。
6. 唯一的选择是在 B 和 C 之间。如果 `searchVal` 大于列表中的任何值，则 `first = list.size()`，这正是我们需要的。
7. 从根节点的最长路径是 22, 30, 34, 51, 45。
8. 必须先减后增。
9. 在任何二叉搜索树（BST）中，最小节点没有左子节点。对于完全树，任何节点都有左子节点。
10. 唯一的选择是在 B 和 C 之间。如果 `searchVal` 大于列表中的任何值，则 `first = list.size()`，这正是我们需要的。

## 答案与解析

### AB-2

#### 第一部分：选择题

| 1. A | 11. C | 21. D | 31. C |
|---|---|---|---|
| 2. E | 12. B | 22. B | 32. E |
| 3. A | 13. C | 23. D | 33. D |
| 4. D | 14. A | 24. B | 34. D |
| 5. B | 15. A | 25. B | 35. D |
| 6. B | 16. D | 26. E | 36. D |
| 7. D | 17. B | 27. B | 37. A |
| 8. D | 18. A | 28. E | 38. E |
| 9. A | 19. C | 29. C | 39. B |
| 10. E | 20. C | 30. D | 40. B |

#### Note

- 14. 检查单词是否为回文。
- 15. 应用了二分查找。
- 16. 选项 I 无，因为 `orderedItems` 被声明为 `List` 而不是 `LinkedList`。
- 17. 注意 `getTable` 是私有的，所以它的使用只影响此类。
- 21. `theGuests` 在 `Party` 中是私有的。
- 25. 必须先升序，后降序。
- 26. 在这段代码中，我们反复将头节点从列表中取消并将其添加到新列表的头部。
- 32. I 和 II 都不是完全树。
- 35. 当虫子（bug）创建时，它指向北方。
- 36. 在 I 中，`act` 可能会转向虫子而不是移动它。`hashCode` 将默认使用 `Object` 的 `hashCode`，它会返回对象的地址。代码可能无法在 `map` 中找到与给定位置相等的位置，因为它会在错误的桶中查找。

### 第二部分：简答题

#### 1. (a)

```java
public ProductionLine(int nDisks, int maxRadius) {
    assemblyLineIn = new LinkedList<Disk>();

    for (int i = 1; i <= nDisks; i++) {
        int radius = (int) (Math.random() * maxRadius) + 1;
        assemblyLineIn.add(new Disk(radius));
    }

    robotArm = new Tower();
    assemblyLineOut = new LinkedList<Tower>();
}
```

#### 1. (b)

```java
private void unloadRobot() {
    Tower pyramid = new Tower();

    while (!robotArm.isEmpty()) {
        pyramid.push(robotArm.pop());
    }

    assemblyLineOut.add(pyramid);
}
```

#### 1. (c)

```java
public void process() {
    while (!assemblyLineIn.isEmpty()) {
        Disk disk = assemblyLineIn.remove();

        if (!robotArm.isEmpty()
                && disk.compareTo(robotArm.peek()) <= 0) {
            unloadRobot();
        }

        robotArm.push(disk);
    }

    if (!robotArm.isEmpty()) {
        unloadRobot();
    }
}
```

#### 2. (a)

```java
public static void add(Map<String, Set<String>> dictionary,
        String word, String translation) {
    if (dictionary.containsKey(word)) {
        dictionary.get(word).add(translation);
    } else {
        Set<String> translations = new TreeSet<String>();
        translations.add(translation);
        dictionary.put(word, translations);
    }
}
```

#### 2. (b)

```java
public static Map<String, Set<String>> reverse(
        Map<String, Set<String>> dictionary) {
    Map<String, Set<String>> reverseDictionary =
        new HashMap<String, Set<String>>();

    for (String word : dictionary.keySet()) {
        Set<String> translations = dictionary.get(word);

        for (String translation : translations) {
            add(reverseDictionary, translation, word);
        }
    }

    return reverseDictionary;
}
```

#### 3. (a)

```java
public MinesweeperBoard() {
    super(9, 9);
    initialize(10);
}

public MinesweeperBoard(int nRows, int nCols, int nMines) {
    super(nRows, nCols);
    initialize(nMines);
}

private void initialize(int nMines) {
    for (int r = 0; r < getNumRows(); r++) {
        for (int c = 0; c < getNumCols(); c++) {
            put(new Location(r, c), new MinesweeperCell());
        }
    }

    int count = 0;

    while (count < nMines) {
        Location loc = new Location(
            (int) (Math.random() * getNumRows()),
            (int) (Math.random() * getNumCols())
        );

        if (!get(loc).isMine()) {
            get(loc).setMine();
            count++;
        }
    }
}
```

#### 3. (b)

```java
private int getMineCount(Location loc) {
    int count = 0;

    for (MinesweeperCell neighbor : getNeighbors(loc)) {
        if (neighbor.isMine()) {
            count++;
        }
    }
}
```



- (c)

```java
public int reveal(Location loc)
{
    MinesweeperCell cell = get(loc);
    if (cell.isOpen())
        return 0;
    else if (cell.isMine())
        return -1;
    else {
        int mineCount = getMineCount(loc);
        cell.open();
        int count = 1;
        if (mineCount == 0) {
            ArrayList<Location> neighborLocs = getValidLocations(loc);
            for (Location nLoc : neighborLocs) {
                count += reveal(nLoc);
            }
        }
        return count;
    }
}
```

- 4. (a)

```java
public static int[] getStats(TreeNode root)
{
    int[] stats = {-1, 0, 0, 0};
    if (root == null) {
        return stats;
    }
    int[] leftStats = getStats(root.getLeft());
    int[] rightStats = getStats(root.getRoot());
    stats[0] = Math.max(leftStats[0], rightStats[0]) + 1;
    stats[1] = (Integer)root.getValue().intValue() + (leftStats[1] + rightStats[1]);
    stats[2] = leftStats[2] + rightStats[2];
    stats[3] = leftStats[3] + rightStats[3];
    return stats;
}
```

## Notes:

- 1. 尽管说是“非空树”，但递归调用必须处理 null。将空树的长度设置为 -1 是合理的。
- 2. `leftStats[1]` 是起始于叶子节点的数量。

- (b)

```java
private static boolean isHTree(TreeNode root, String path)
{
    if (root == null) {
        return true;
    }
    if (path.length() < 2) {
        String leftPath = "L", rightPath = "R";
        if (path.equals("L"))
            leftPath += "L";
        if (path.equals("R"))
            rightPath += "R";
        return ((Integer)root.getValue().intValue() == 0 &&
            isHTree(root.getLeft(), leftPath) &&
            isHTree(root.getRoot(), rightPath));
    } else if (path.length() == 2) {
        return ((Integer)root.getValue().intValue() > 0 &&
            root.getLeft() == null && root.getRoot() == null);
    }
}
```



## Notes:

- 必须是叶子。

## Index

- `-` 运算符, 15
- `%` 运算符, 15
- `&` 运算符, 20
- `\n`, 3
- `^` 运算符, 20
- `|` 运算符, 20
- `~` 运算符, 20
- `++` 运算符, 15
- `==` 和 `!=` 运算符, 16
- 用于对象, 16
- 数组, 33
- `index`, 34
- 长度, 34
- 一维, 33
- 方法返回, 37
- 下标, 34
- 遍历, 87
- 二维, 37
- 赋值运算符, 3
- 自动装箱, 33, 39
- 自动装箱, 33, 63
- `A` 子集, 3
- `AB` 子集, 4
- `Math` `abs` 方法, 35, 47
- 抽象类, 72
- 抽象方法, 72
- 访问器, 45, 83
- 递归基础情况, 102
- 准备好的网站, viii
- `Big-Oh`, 115, 146
- 二分查找, 95
- 递归, 104
- 二叉搜索树 (`BST`), 139
- 二叉树, 132
- 叶子节点, 132
- 根, 132
- 子树, 132
- 位逻辑运算符, 220
- 布尔数据类型, 11
- 布尔表达式, 72
- 边界条件, 93
- 循环中的 `break`, 27
- `BST` (二叉搜索树), 139
- 中序遍历, 139
- 字节码, 65
- `PriorityQueue<E>` 类中的 `add` 方法, 143
- `Queue<E>` 接口中的 `add` 方法, 127
- 别名, 51
- `AP` 中央, vii, 151
- `AP` 学分, 7
- `AP CS` 开发委员会, vii
- `AP Java` 子集, vii, 2
- 参数 (又称参数), 43
- 算术运算符, 13
- `ArithmeticException`, 3, 60
- `ArrayIndexOutOfBoundsException`, 3, 34, 60
- `ArrayList`, 3, 39, 116 方法, 40

## INDEX

- 案例研究, 15
- 强制转换运算符, 14
- 哈希表中的链法, 141
- 字符数据类型, 3
- 检查异常, 60
- 类, 43
- 抽象, 72
- 访问器, 45
- 类 (静态) 方法, 47
- 类 (静态) 变量, 47
- 客户端, 56
- 具体实现, 72
- 构造函数, 43
- 实现接口, 72
- 实例变量, 45
- 方法, 47
- 公有和私有字段, 44
- 类层级, 71
- 类方法, 47
- 类变量, 47
- `ClassCastException`, 61
- 类的客户端, 45, 56
- 集合, 113
- 哈希表中的冲突, 141
- 注, 10
- `Comparable<T>` 接口, 32, 78, 130
- `compareTo` 方法, 16, 78
- `String`, 30
- 编译器, 65

## 索引 367

- 字段 (`fields`), 43
- 最终变量 (`final variables`), 47
- 浮点数 (`floating-point numbers`), 13
- "for each" 循环, 3, 25, 41, 88, 118, 119
- 结合 2D 数组 (`with 2D arrays`), 39
- `for` 循环 (`for loop`), 3, 22
- 输出格式化 (`formatting output`), 58
- 简答题 (`free-response queries`), 1, 2
- 往年题 (`from past years`), 177
- 硬件 (`hardware`), 65
- `HAS-A` 关系 (`HAS-A relationship`), 67
- 哈希表 (`hash table`), 141
- `hashCode` 方法, 141
- 哈希算法 (`hashing`), 141
- `HashMap<K,V>` 类, 131, 141, 172
- `HashSet<E>` 类, 130, 141
- 堆排序 (`Heapsort`), 145
- 辅助方法 (`helper method`), 9
- 类的层次结构 (`hierarchy of classes`), 71
- 垃圾回收 (`garbage collection`), 34, 44
- 泛型集合 (`generic collections`), 39, 113
- 分数 (`grades`), 5
- 分格线 (`cut-off points`), 6
- 分布 (`distributions`), 5
- 图形用户界面 (`GUI`), 65
- `GridWorld` 案例研究 (`GridWorld case study`), 151
- `AbstractGrid` 类, 170
- `Actor` 类, 159
- 边界网格 (`bounded grid`), 156
- `BoundedGrid` 类, 171
- `Bug` 类, 163
- `ChameleonCritter` 类, 168
- 类与接口 (`classes and interfaces`), 154
- `Critter` 类, 165
- `Flower` 类, 163
- 网格实现 (`grid implementations`), 169
- `Grid` 接口 (`Grid interface`), 156
- 网格方法 (`Grid methods`), 157
- `Location` 类 (`Location class`), 155
- `Location` 类常量 (`Location class constants`), 151
- 包 (`packages`), 151
- `Rock` 类 (`Rock class`), 163
- `Actor` 的子类 (`subclasses of Actor`), 163
- `Critter` 的子类 (`subclasses of Critter`), 168
- 无边界网格 (`unbounded grid`), 156
- `UnboundedGrid` 类, 172
- `IDE` (集成开发环境), 65
- `if-else` 语句 (`if-else statement`), 3
- `if-else-if` 序列结构 (`if-else-if sequences`), 20
- `IllegalArgumentException`, 4, 40, 60
- `IllegalStateException`, 61
- 不变对象 (`immutable objects`), 51
- 实现接口 (`implementing an interface`), 77
- `implements` 关键字, 77
- 导入语句 (`import statements`), 10
- 增减运算符 (`increment and decrement operators`), 3, 15
- `String` 的 `indexOutOfBounds` 方法 (`indexOutOfBounds method of String`), 30
- 索引 (`indices`), 34
- 信息隐藏性 (`information hiding`), 45, 66
- 实例 (`instance`), 67
- 中序遍历 (`inorder traversal`), 134
- 向数组中插入一个值 (`inserting a value into an array`), 92
- 插入排序 (`Insertion Sort`), 99
- 类的实例 (`instance of class`), 43
- 实例变量 (`instance variables`), 43, 45
- 实例化 (`instantiation`), 43
- `int` 数据类型 (`int data type`), 11
- `Integer` 类, 32
- 集成开发环境 (`IDE`), 65
- `GUI` (图形用户界面), 65

## 索引 368

- 接口 (`interfaces`), 77
- 与多态 (`and polymorphism`), 78
- 作为数据类型 (`as data types`), 78
- 解释器 (`interpreter`), 65
- `Integer` 的 `intValue` 方法 (`intValue method of Integer`), 32
- 不变性 (`invariant`), 94
- `IS-A` 关系 (`IS-A relationship`), 67
- 迭代 (`iterations`), 87
- 迭代器 (`iterator`), 88
- `Iterator<E>` 接口, 118
- 映射 (`maps`), 130
- `Map<K, V>` 接口, 113, 131
- 映射遍历 (`map traversal`), 131
- `Math` 类, 47
- `Math.abs`, 35, 47, 53
- `Math.E`, 47
- `Math.min`, 49
- `Math.PI`, 47
- `Math.pow`, 47
- `Math.random`, 58
- `Math.sqrt`, 13, 47
- 数组中的最大值或最小值 (`maximum or minimum in an array`), 88
- Java 5.0, 25, 33, 39, 48, 78, 81, 113, 129, 131
- Java 子集 (`Java subset`), vii, viii, 2
- Java 虚拟机 (`Java Virtual Machine`), 65
- `java.util` 包, 57, 113
- 合并排序 (`Mergesort`), 105
- 方法 (`methods`)
- 命名规范 (`naming convention`), 47
- 重载的 (`overloaded`), 53
- 重写的 (`overriding`), 68
- 签名 (`signature`), 68
- `Math` 的 `min` 方法 (`min method of Math`), 49
- 修饰符 (`modifiers`), 45, 57, 83
- 模运算继承运算符 (`modulo inheritance operator`), 15
- 多重继承 (`multiple inheritance`), 67
- 多选题 (`multiple-choice questions`), 1
- 数组的长度 (`length of an array`), 34
- 子集中的类类 (`library classes in the subset`), 3
- 线性增长 (`linear growth`), 147
- 线性时间 (`linear time`), 99
- 链表 (`linked list`), 117
- 链表遍历 (`linked list traversal`), 88
- `LinkedList` 类, 117
- 列表 (`list`), 115
- `List` 接口 (`List interface`), 113, 115
- 列表遍历 (`List traversal`), 118
- `ListIterator<E>` 接口, 118
- `ListNode` 类, vi, 1, 115, 122
- 字面量字符串 (`literal strings`), 28
- 局部变量 (`local variables`), 11, 56
- 逻辑运算符 (`logical operators`), 3, 17
- 查找表 (`lookup table`), 111
- 循环不变性 (`loop invariant`), 94
- 循环 (`loops`), 87
- 命名规范 (`naming convention`), 82
- 自然排序 (`natural ordering`), 78
- 嵌套 `if` (`nested ifs`), 20
- 嵌套循环 (`nested loops`), 27, 88
- `new` 运算符, 3, 44
- `Random` 的 `nextDouble` 方法 (`nextDouble method of Random`), 57
- `Random` 的 `nextInt` 方法 (`nextInt method of Random`), 57
- `n-log n` 增长 (`n-log n growth`), 147
- 无参构造函数 (`no-args constructor`), 43, 82
- `NoSuchElementException`, 4
- `null`, 16, 53
- `NullPointerException`, 16, 60

## 索引 369

- `Object` 类, 71, 141
- 面向对象编程 (`OOP`), 66
- 不变的 (`immutable`), 51
- 传递方法 (`passed to methods`), 50
- 差一错误 (`off-by-one bugs (OBOBs)`), 24
- 一维数组 (`one-dimensional arrays`), 3, 33
- 操作系统 (`operating system`), 65
- 增长阶数 (`order of growth`), 146
- 输出格式化 (`output formatting`), 58
- 重载方法 (`overloaded methods`), 53
- 重写方法 (`overriding methods`), 68
- 平方级增长 (`quadratic growth`), 147
- 平方级排序 (`quadratic sorts`), 98
- 平方级时间 (`quadratic time`), 99
- `Queue<E>` 接口, 127
- 快速 (`Quick`), 1
- 快速排序 (`Quicksort`), 107
- 随机访问 (`random access`), 111
- `Random` 类, 57
- `Math` 的 `random` 方法 (`random method of Math`), 58
- 随机数 (`random numbers`), 57
- 随机存取 (`random-access memory (RAM)`), 65
- 递归 (`recursion`), 100
- 基类 (`base class`), 102
- 递归二分查找 (`recursive Binary Search`), 104
- 关系操作 (`relational operations`), 3, 16
- 参数 (`parameters`), 43
- 按值传递 (`by value`), 49
- 括号 (`parentheses of`), 19
- 简答题 (`free-response questions`), 177
- `PriorityQueue` 类中的 `peek` 方法 (`peek method in PriorityQueue class`), 143
- `Queue<E>` 接口中的 `peek` 方法 (`peek method in Queue<E> interface`), 127
- `Stack<E>` 类中的 `peek` 方法 (`peek method in Stack<E> class`), 126
- 外围设备 (`peripherals`), 65
- 多态 (`polymorphism`), 74, 78, 166
- `Stack<E>` 类中的 `pop` 方法 (`pop method in Stack<E> class`)
- 后序遍历 (`postorder traversal`), 134
- `Math` 的 `pow` 方法 (`pow method of Math`), 47
- 前序遍历 (`preorder traversal`), 134
- 原始数据类型 (`primitive data types`), 3, 11, 12, 49
- `printf` 方法, 58
- 优先级队列 (`priority queue`), 143
- `PriorityQueue<E>` 类, 143
- `private` 关键字, 68
- 私有变量 (`private variables`), 69
- 过程化抽象 (`procedural abstraction`), 65, 66
- 编程风格 (`programming style`), 82
- 公有字段和方法 (`public and private fields and methods`), 44
- `push` 和 `pop`, 125
- `Stack<E>` 类中的 `push` 和 `pop` 方法 (`push and pop methods in Stack<E> class`), 114, 126
- `PriorityQueue<E>` 类中的 `remove` 方法 (`remove method in PriorityQueue<E> class`), 143
- `Queue<E>` 接口中的 `remove` 方法 (`remove method in Queue<E> interface`), 127
- 循环中的返回 (`return in loops`), 27
- `return` 语句 (`return statement`), 3, 48, 52
- 可用代码 (`usable code`), 66
- 运行时错误 (`run-time errors`), 34, 60
- `Scanner` 类, 58
- 随机数生成器 (`seeding random generator`), 57
- 选择排序 (`Selection Sort`), 98
- 顺序查找 (`Sequential Search`), 95
- `Set<E>` 接口, 113, 129
- 短路求值 (`short-circuit evaluation`), 19, 20
- 方法签名 (`signature of a method`), 68
- `skylit.com/准备网站` (`skylit.com/prepared site`)
- 软件工具 (`software tools`), 65
- 排序 (`sorting`), 98
- 源代码 (`source code`), 65
- 规范 (`specifications`), 65
- `Math` 的 `sqrt` 方法 (`sqrt method of Math`), 13, 47
- `Stack<E>` 类, 113, 126
- `static` 关键字, 47
- `static` 方法和变量 (`static methods and variables`), 47
- `String` 类, 28
- `compareTo` 方法, 3
- `equals` 方法, 3
- `indexOf` 方法, 3
- `length` 方法, 3
- 方法 (`methods`), 29
- `String` 的 `substring` 方法 (`substring methods of String`), 30, 53
- 不变性 (`immutability`), 29
- `nub` 方法, 66
- 子类 (`subclass`), 67, 68
- 下标 (`subscripts`), 34
- 子集 (`subset`)
- `A` 考试 (`A exam`)
- `AB` 考试 (`AB exam`), 4
- 输入与输出 (`input and output`), 4
- 类类 (`library classes`), 3
- 原始数据类型 (`primitive data types`), 3
- `String` 方法, 3
- `super` 关键字, 3, 68, 69
- 父类 (`superclass`), 67
- `switch` 语句 (`switch statement`), 3, 4
- 符号常数 (`symbolic constants`), 12, 13
- `System.in`, 48
- `System.out`, 48, 58
- `System.out.print`, 59
- `System.out.printf`, 58
- `System.out.println`, 59
- 开发 (`development`), 66
- `this` 关键字, 3
- `throw` 关键字, 61
- 抛出异常 (`throwing an exception`), 4, 60, 61
- 自顶向下设计 (`top-down design`), 66
- 自顶向下开发 (`top-down development`), 66
- `toString` 方法, 59
- 遍历 (`traversal`)
- 链表的遍历 (`of a linked list`), 88
- 列表的遍历 (`of a list`), 118
- 数组的遍历 (`of an array`), 87
- 使用迭代器 (`using an iterator`), 119
- 树 (`tree`), 132
- 树遍历 (`tree traversal`), 134
- `TreeMap<K, V>` 类, 131, 139
- `TreeSet<E>` 类, 130, 139
- 三角形嵌套循环 (`triangular nested loops`), 88
- `try-catch` 语句 (`try-catch statements`), 60
- 二维数组 (`two-dimensional arrays`), 37
- 未检查异常 (`unchecked exceptions`), 60
- 用户界面 (`user interface`), 66
- `void` 方法 (`void methods`), 48
- `while` 循环 (`while loop`), 3, 22
- 包装类 (`wrapper classes`), 32, 115

## 其他计算机科学与微积分

Skylight Publishing 出版

- Java Methods A&B: 面向对象与数据结构, AP 版, ISBN 0-9727055-7-0
- 175 道 Java 多选题, ISBN 0-9727055-1-1
- 100 道 C++ 多选题, ISBN 0-9654853-0-7
- 准备好 AP 微积分考试 (Be Prepared for the AP Calculus Exam), ISBN 0-9727055-4
- 800 道微积分题 (800 Questions in Java), 0-9727055-5
- 准备好 AP 微积分考试 (Be Prepared for the AP Calculus Exam), ISBN 0-9727055-6
- 微积分解答 (800 Questions in Calculus), 0-9727055-D
- 微积分实验室学生包 (Calculus Labs Student Pack), 0-9727055-L
- 微积分实验室教师包 (Calculus Labs Teacher Pack), 0-9727055-T

http://www.skylit.com  
sales@skylit.com  
Toll free: 888-476-1940  
Fax: 978-475-1431

Skylight Publishing, 9 Bartlett Street, Suite 70, Andover, MA 01810
