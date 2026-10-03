
# Java 程序构建指南：回归基础方法

![](img/aea18896a4bced58de45f29f5a93f7b3_0_0.png)

![](img/aea18896a4bced58de45f29f5a93f7b3_1_0.png)

华盛顿大学

![](img/aea18896a4bced58de45f29f5a93f7b3_2_0.png)

## 前言

《构建 Java 程序》是一本为计算机科学入门课程设计的教科书。我们为广泛的学生群体编写了本书，而不仅仅是计算机科学专业的学生。在两年多半的时间里，这些材料在华盛顿大学的数千本科生中进行了课堂测试（其中大多数人不是计算机专业的学生）。

计算机科学入门课程在许多学校有着作为“挂科王”课程的历史，不及格率很高。但道格拉斯·亚当斯在《银河系漫游》中说：“不要慌”。只要学生循序渐进，就能掌握这些内容。

许多教师尝试了教授入门计算机科学的新方法。最显出的实验是“尽早引入对象”的方法。我们认为这些实验在很大程度上是失败的。虽然课程中的顶尖学生似乎很好地掌握了材料，但有一部分中间学生在对象概念上挣扎。

《构建 Java 程序》采用了一种“回归基础”的方法，强调早期学习过程化编程。我们从多年的经验了解到，许多科学家、工程师和其他人士都可以学习如何以过程化的方式编程。一旦我们建立了坚实的过程化技术基础，就会转向面向对象的编程。因此，课程结束时，学生将学习两种编程风格。

以下是《构建 Java 程序》所采用方法的一些关键特征：

- **尽早使用对象。** Java 提供了丰富的有用对象，允许学生使用传统的过程化编程技术编写有趣的程序。尽早且频繁地使用这些对象可以为以后定义它们提供便利过渡。
- **晚些定义对象。** 如果学生在尝试掌握基础编程技能的同时学习如何定义对象，他们可能会感到力不从心。我们先教基础知识，之后再教学生如何定义对象。
- **关注问题解决。** 许多教科书在引入新结构时侧重于语言细节。而我们关注的是问题解决。每个新结构可以解决哪些新问题？新手在此过程中可能会遇到哪些陷阱？使用新结构的最常见方法是什么？
- **强调算法思维。** 我们的过程化方法允许我们强调算法问题的解决：将大问题分解为较小的问题，使用伪代码完善算法，并努力应对挑战。
- **分层方法。** 在 Java 中编程涉及许多难以一次性学习的概念。如果你试图一次放置太多的卡牌，整个结构就会崩溃。我们层层层地教授新概念。
- **充分利用 Java 5。** 本书是针对 Java 5 时代编写的。我们充分利用了`Scanner`类、泛型、`for`循环以及装箱/拆箱。
- **案例研究。** 我们在每章结束时都有一个案例研究，向学生如何分阶段开发程序以及如何在开发过程中进行测试。
- **可选的图形补充。** 我们制作了一个自定义的`DrawingPanel`类，方便学生访问 Java 强大的图形功能。许多学生喜欢有机会创作复杂的图像，但书中这部分是完全可选的。

## 层与依赖关系

许多计算机科学入门书籍是以语言为导向的，但我们的早期章节分层。例如，Java 有许多控制结构需要掌握（包括`for`循环、`while`循环和`if/else`语句），许多书籍将这些控制结构包含在一个章节中。对于已经会编程的人来说，这可能是合理的，但对于正在学习编程的新手来说，这可能难以负担。我们发现，将这些控制结构分散在不同的章节中让学生一个学习，比尝试一次学习要有效得多。

下表显示了前六章分层方法是如何工作的：

以下是本书的依赖图：

![](img/aea18896a4bced58de45f29f5a93f7b3_7_0.png)

## 前言

## 辅助材料

我们为讲师和学生提供了丰富的辅助材料。所有自测练习的答案均附于附录 A。此外，学生可以在`www.aw-bc.com/cssupport`访问以下资源：

- 源代码
- 所有案例研究和其他完整程序示例的数据文件
- 第 3 章可选图形补充材料中使用的`DrawingPanel`类；其源代码

此外，随书附带的学生 CD 包含源代码以及大量的 Java 开发环境（完整列表请参阅 CD）。合格的讲师还可以访问以下资源：

- PowerPoint 幻灯片
- 编程练习和编程项目的解决方案
- 示例试卷
- 实验讲义材料
- 带有答案关键的额外编程练习

如需获取讲师资源，请联系您的 Addison-Wesley 销售代表或向`computing@aw.com`发送电子邮件。

![](img/aea18896a4bced58de45f29f5a93f7b3_8_0.png)

## My CodeMate – 您的专属助

Addison-Wesley 的 MyCodeMate 是一个针对本书的 Web 资源，提供教程帮助并对学生程序进行评估。书中的示例程序以及每章选定的练习和编程项目已集成到 MyCodeMate 中。使用该工具，学生可以在任何连接互联网的计算机上编写并编译程序，就如何继续以及如何处理编译器错误信息接收指导和反馈。讲师可以跟踪每个学生在书中练习和编程项目上的进度，也可以开发自己的项目。在购买新书并订购激活码时，将提供免费的 MyCodeMate 订阅。也可以在线购买订阅。更多信息请访问`www.mycodemate.com`，或联系您的校园 Addison-Wesley 代表。

## 致谢

首先，我们要感谢许多使用并对本书初稿提供反馈意见的学生和助教。没有他们的投入，我们就无法写出这本书。特别感谢 Helene Martin，她仔细审阅了这些章节的早期版本，寻找错误并找出需要改进的粗糙之处。

其次，我们要感谢华盛顿大学计算机科学与工程系的同事。全体教师共同决定尝试一下，聘佣了我们并给予了我们开发课程的自由。我们特别感谢 Hank Levy（现任主席）、David Notkin（前任主席）和 Richard Anderson（教育副主席）的无私支持。我们还要感谢 Steve Gribble 和 Carl Ebeling 对本书进行了课堂测试，并为我们提供了宝贵的反馈。

第三，我们要感谢人才横溢的评审员团队，他们在将一系列课堂笔记转化为正规教材的过程中指导了我们：

- Delroy A. Brinkerhoff, 韦伯州立大学
- Ed Brunjes, 米拉马社区学院
- Tom Coratina, 卡内基·梅隆大学
- H.E. Dunsmore, 普渡大学
- Mary Anne Egan, 西耶纳学院
- Ahmad Ghafarian, 乔治亚州立大学
- Raj Gill, 阿鲁德尔社区学院
- Michael Hosteller, 公园大学
- David Hovemeyer, 卡罗尔学院
- Chenglie, 弗吉尼亚理工学院
- Philip Ishen, 新墨西哥
- David Kamper, 东北伊利诺伊州大学
- Simon G. Koo, 圣地亚
- Evan Korth, 纽约大学
- Joan Krone, 丹尼森大学
- Eric Matson, 莱特州立大学
- Kathryn, 麦金尼大学
- Jerry Mead, 巴克内尔
- George Medel, 埃塞克斯社区学院
- John Neitzke, 特鲁门州立大学
- Richard Pattis, 卡内基·梅隆大学
- Frederick Pratter, 俄勒冈东部
- Roger Priebe, 德克萨斯州奥斯汀
- Delhu Q. Lamar 大学
- Amala Rajan, 米德塞斯大学
- Mike Scott, 德克萨斯州奥斯汀
- Tom Stokke, 北达科他
- Leigh Ann Taylor, Fox Lane 高中
- Scott, DePauw 大学
- Megan Thomas, 加州州立大学
- Jeanie Turner, Sayre 学校
- Tammy VanGrift, 波特兰
- Thomas Vanrunen, 惠顿学院
- Neal R. Wagner, 德克萨斯州安东诺
- Jiangping, 韦伯大学
- Yang Wang, 密苏里州立大学
- Stephen Weiss, 北卡罗来纳大学教堂分校
- Laurie Werner, 迈阿密大学
- Dianna Xu, 布莱恩学院
- Carol Zander, 华盛顿博瑟尔
- Rachel Head, Argos 出版社
- Nancy Kotary, Addison-Wesley
- Michelle Brown, "gets it"
- Jeff Holcomb, 承诺并交付了简单而优雅
- Maurene Goo, 照顾了细节
- Patty Mahtani, 维持了一切整体
- Matt Goldstein, 相信这一概念

## 功能演示

当第一批计算机被制造时，存储设备的尺寸有限，而且计算成本非常昂贵。现在，处理信息的计算机已经变得廉价；而且今天几乎每个人都能用上。

## 二进制数字

计算机使用二进制（binary）数字表示所有数据和信息。人类自然地使用十进制，这使得处理变得困难。对于计算机来说，二进制系统易于创建且可靠。事实证明这样更简单。

## 定义术语

关键术语从文中提取并定义，以便快速参考。

### 你知道吗？

`Hello, World!`“hello world”传统由 Brian Kernighan 和 Dennis Ritchie 开始，他们在 20 世纪 70 代发明了名为 C 的编程语言。他们 1978 年描述 C 语言的书中的第一个完整程序是“hello world”。从那以后，他们的书《C 语言》被亲切地称为“K & R”。

### 常见编程错误

#### 类名与文件名不匹配

如前所述，Java 要求程序的类名和文件名匹配。以`public class Hello`开头的程序必须存储在名为`Hello.java`的文件中。

如果你使用了错误的文件（例如保存为`WrongFileName.java`），你会收到这样的错误信息：

```text
FileName.java: class Hello is public, should be declared in a file named Hello.java
public class Hello {
error
```

然而，它需要被调用。这表明存在问题。

Chrome 是一个免费浏览器。

## 代码列表

书中到处都是代码列表。列表中的关键行会被高亮显示。关键字用彩色字体打印。在语法模板中，供程序员替换的占位符被`<括号>`包围并高亮显示。

尝试以下简单的 Java 程序：

```java
public class Hello {
   system.out.println("Hello world");
}
```

### “点踩”错误代码图标

偶尔出现。

Building Java 使用有缺陷或错误的代码来阐述常见的编程陷阱，这些陷阱经常让缺乏经验的程序员感到困惑。点踩符号表示相关的代码列表存在缺陷或在某种程度上存在问题。

这看起来相当不错，但它会在行末尾打印一个额外的空格，你必须稍微修改一下。这是一个经典的栅栏柱问题（fencepost problem）。

## 章节总结

- 比较可以对程序中的元素进行排序。
- 比较将元素序列转换为布尔值。
- Java 将程序翻译成一种称为 Java 字节码的特殊格式，使用称为 Java 运行时环境的特殊程序执行。

### 章节摘要

位于每章的末尾。

- 预处理器是引导算法的程序，用于开发和实现复杂问题。
- Java 将源代码转换为机器码，机器码是一组机器指令。

Java 程序员通常使用集成开发环境（IDE）完成工作。命令可能随环境而异，但相同的三步流程始终是：

1. 以 Java 类的形式输入程序。
2. 编译程序文件。
3. 运行编译后的程序版本。

### 自测题

#### 6.1 节：文件读取基础

1. 什么是文件？如何在 Java 中从文件中读取数据？
2. 下面行代码有什么问题？
3. 编写代码构造`Scanner`对象以读取与程序在同一文件夹下的输入文件`input.txt`。

#### 6.2 节：基于 Token 的处理

4. 下面行代码有什么问题？

```java
Scanner input = new Scanner(File("C:\temp\new files\test.dat"));
```

### 自测题

这些章末题为读者提供了评估对每节关键主题掌握情况的机会。所有自测题的答案可在书籍附录 A 中。

### 练习题

这些中等题目需要计算、分析或编写代码段，以及对章节内容有更深入的理解。所有练习的答案提供给教师。

1. 写一个比较程序，接受两个字符串，每行写一个，并在第一行中输出文本的反转字符串。你应该打印每行之间的差异。为了增加挑战性，尝试让你的代码即使两个字符串相同时也能运行（换句话说，它将向同一个文件写入双倍间隔的输出）。
2. 写一个合并排序算法，接受输入文件作为参数，并将文件的每一行输出到控制台，对所有超过 60 个字符的行进行换行。例如，如果一行包含72个字符，该方法应将其替换为两行：一行包含前 60 个字符，另一行包含最后 12 个字符。包含 217 个字符的行应换成四行，三三长度为 60。

### 编程项目

通过问题和练习挑战读者设计并实现 Java 程序。它们的难度各不相同，但通常比练习需要更多时间来完成。编程项目的示例答案提供给教师。

### 编程项目

1. 编写类来为购物列表建模。创建一个`Item`类，表示杂货的名称和价格，例如 3.50 美元的黄油。还要实现一个`Order`类，代表购物者的设备，用于以指定的数量购买指定的物品，例如盒装纸巾。编写一个方法来实现批量折扣物品，例如两盒纸巾 4 美元，这将使得 2 + 2 + 1 盒纸巾的订单费用为 4 + 4 + 3 美元。最后，实现一个`ShoppingCart`类，它在`ArrayList`中存储物品并允许添加、删除或搜索物品。购物车应该报告当前携带的所有物品订单的总价格。
2. 写一个程序来反转文件的行，并反转文件每行中单词的顺序。使用`ArrayList`存储它们。
3. 写一个家谱树程序。表示一个人，存储对母亲、父亲和任何孩子的引用。读取一个姓名文件以实例化每个`Person`的父子关系（你可能想创建一个代表你自己的家族树的文件）。在`ArrayList`中存储`Persons`列表。编写一个整体的主用户界面，允许输入名称并打印该人的母系和父系家谱。

## MyCodeMate

在线学习时，学生可以像教材一样查看、编译、运行和编辑编程题。寻找此 MyCodeMate 图标，订阅 MyCodeMate 即可查看编程项目。

```java
// 写一个完整的 java 程序，打印以下输出
// Hello
// World
// Universe
```

序言 iii

- 数字领域 4
- Java 编程环境 8
- 文件与文件对象 342
- 使用`Scanner`读取文件 335
- 文件的结构与输入消耗 341
- 6.3 基于行的处理 350
- `try/catch`语句 359
- 构造与遍历数组 376

# Java 入门

## 引言

### 1.1 计算基础

- 为什么要编程？
- 硬件与软件
- 数字领域
- 编程过程
- 为什么选择 Java？
- Java 编程环境

### 1.2 现在开始——Java

- 字符串字面量（`String`）
- `System.out.println`
- 转义序列
- 标识符与关键字
- 复杂示例：绘图！
- 注释与可读性

### 1.3 程序错误

- 语法错误
- 逻辑错误（Bugs）

### 1.4 过程化分解

- 静态方法
- 控制流
- 调用其他方法的方法
- 运行时错误示例

### 1.5 案例研究：绘图

- 结构化版本
- 无冗余的最终版本
- 执行流分析（等等，正文在后后）

计算机在我们的日常生活中无处不在，得益于互联网，我们可以获取无尽的信息。这些信息中是重要的新闻，如`cnn.com`上的头条新闻；另一些则更无意义：如果你担心昨晚认识的那个家伙是否会对女朋友出轨，你可能访问过`dontate.com`。计算机让我们与家人分享照片，并规划前往最近披萨店的路线。

许多现实世界的问题都是通过计算机解决的，其中有些并不像你桌上或笔记本上的那台。使用强大的计算机对人类基因组进行测序并搜索 DNA 模式。最近制造的汽车中装有计算机，监控每辆车辆的状态和运动。苹果的 iPod 等数字音乐播放器在其小外壳下实际上也是计算机。即使是 Roomba 扫地机器人也包含一个计算机，带有复杂的指令教它如何在清洁地板时避开家具。

但是什么让计算机成为计算机？计算器是计算机吗？拿着铅笔和电脑的人呢？接下来的几节将尝试回答这个问题，同时引导你将计算机纳入你的掌控之中。

## I.1 基础计算概念

Knuth 描述的是大多数计算机科学中通用的思维过程，这被称为算法思维。因此，我们学习编程并不是因为它是计算机科学最重要的方面，而是因为它是解释计算机科学家解决问题方法的最佳方式。

算法以计算机程序的形式表示，这正是本文的核心内容。但在我们学习如何编程之前，回顾一些关于计算机的基本概念将很有帮助。

## 硬件与软件

计算机是一种处理数据并执行被称为“程序”的指令列表的机器。

![](img/aea18896a4bced58de45f29f5a93f7b3_28_0.png)

计算机需要执行的一系列指令列表。

计算机与计算器等简单机器相比的一个关键特征是它的多功能性。同一台计算机可以根据其某一时刻运行的程序，执行许多不同的任务（玩游戏、计算所得税、与世界各地的计算机连接）。计算机不仅可以运行其已存在的程序，还可以运行甚至尚未编写的新程序。

构成计算机的物理部分统称为硬件。最重要的硬件之一是中央处理器，或 CPU。CPU 是计算机的“大脑”：它负责执行指令。同样重要的是计算机的内存（通常称为随机存存储器，或 RAM；因为计算机可以随时访问该内存的任何部分）。计算机使用内存来存储正在执行的程序及其数据。RAM 的容量有限，且在计算机关闭时不会保留其内容。因此，计算机通常使用硬盘作为更大的永久存储区域。

程序统称为软件。运行在计算机上的主要软件是它的操作系统。操作系统提供了一个许多程序可以同时运行的环境，并在这些程序与硬件及用户之间架起了桥梁。在操作系统内部运行的程序通常被称为应用程序。



当用户选择由操作系统运行某个程序时（例如，双击桌面上的程序图标），会发生几件事：该程序的指令从硬盘加载到计算机内存中，操作系统为该程序分配内存供其使用；程序的指令从内存传输到 CPU 并按顺序执行。

## 数字世界

在上一节中，我们看到计算机是一台可以编程的通用设备。你经常会听到人们根据其工作方式将现代计算机称为“数字计算机”。

> 数字
>
> 基于以离散间隔增加的数字，例如整数 0, 1, 2, 3 等。

因为计算机是数字化的，所以存储在计算机上的一切内容都是以整数序列的形式存储的。这包括每一个程序和每一个数据。例如，一个 MP3 文件仅仅是存储音频信息的长整数序列。今天我们习惯了数字音乐、数字图片和数字电影，但在 20 世纪 40 年代第一批计算机建成，以整数形式存储复杂数据的想法是非常不的。

计算机不仅是数字化的（将所有信息存储为整数），它们还是二进制的，这意味着它们以二进制形式存储整数。

> 二进制数
>
> 由 0 和 1 组成的数字，也称为二位。

人类通常使用十进制（base-10），这符合我们的生理结构（10 个手指和 10 只脚趾）。然而，在计算机的情况下，我们希望系统易于创建且非常可靠。事实证明，在二进制现象之上构建这些系统更为简单（例如，电路的开启或闭合，而不是使用 10 种不同的系统来区分（例如，10 种不同的电压水平））。

从数学角度来看，使用二进制数存储东西与使用十进制数一样容易。但由于构建一个使用二进制数的物理设备更容易，这正是计算机所使用的。

然而，这意味着不习惯使用计算机的人会发现它们的惯例很陌生。因此，花一点时间回顾二进制数的工作原理是值得的。在二进制中和十进制一样，你从 0 开始计数，但你用完数字的速度快得多。所以，在二进制中计数时，你说：

```text
0
1
```

就已经用完数字了。这就像在十进制中数到 9。当你用完数字后，就会进位到下一位。接两个二进制数是：

```text
10
11
```

再次，你用完数字了。这就像在十进制中数到 99。再次，你进位到下一位形成三位数数字 100。在二进制中，每当你看到一串 1（例如 111111），你就知道自己距离所有数字翻变为 0 并在前面加 1 只有一步之遥，就像在十进制中，当你看到像 999999 这样的数字时，你就知道自己距离所有数字变成 0 并在前面加 1 只有一步之遥。

下表展示了如何使用二进制数到十进制数字 8。

| 十进制 | 二进制 |
| --- | --- |
| 0 | 0 |
| 1 | 1 |
| 2 | 10 |
| 3 | 11 |
| 4 | 100 |
| 5 | 101 |
| 6 | 110 |
| 7 | 111 |
| 8 | 1000 |

## 1.1 基础计算概念

在 Java 语言中，没有任何东西可以存在于类之外。

### 类（Class）

代码单元是 Java 程序的构建构建块。

类的概念比这要丰富得多，当你在我们读到第 8 章时就会看到，但目前你只需要知道，你的每个 Java 程序都将存储在一个类中。

要实际执行 Java 类文件，你需要另一个能够执行 Java 字节码的程序。这些程序统称为 Java 运行时（Java runtimes），由 Sun 分发的标准环境被称为 Java 运行环境，简称 JRE。

### Java 运行时（Java Runtime）

执行编译后的 Java 类文件的程序。

大多数人的计算机上都有 Java 运行时，即使他们并不知道它的。例如，苹果的 Mac OS 包含一个 Java 运行时，许多 Windows 应用程序也会安装 Java 运行时。

## 为什么选择 Java？

当 Sun 微系统在 1995 年发布 Java 时，他们发布了一份名为“白皮书”的文档，描述他们新的编程语言。也许该文档中最重要的句子是这句话：

Java：一种简单、面向对象、精通网络、解释型、健壮、安全、架构中立、可移植、高性能、多线程的动态语言。

这句话涵盖了 Java 成为一门优秀的入门编程语言的许多原因。首先，Java 对于初学者来说相当容易学习，而且它拥抱面向对象编程，这种编写程序的风格在创建大型复杂软件方面已经非常成功。

Java 还包含了大量的预写软件，程序员可以利用这些软件来增强他们的程序。这些现成的软件组件通常被称为库（libraries）。例如，如果你想编写一个连接到互联网网站的程序，Java 包含一个库来为你简化连接。Java 还包含了用于绘制图形用户界面（GUI）、从数据库检索数据以及执行复杂的数学计算等许多方面的库。这些库统称为 Java 类库。

## Java 类库（Java Class Libraries）

Java 的预存代码集合为常见的编程问题提供了解决方案。

Java 类库的丰富性是 Java 成为流行语言的极其重要的因素之一。截至 1.5 版本，类库包含超过 3200 个条目。

使用 Java 的另一个原因是它拥有充满活力的程序员社区。有大量的在线文档和教程可以帮助程序员学习新技能。这些文档许多是由 Sun 编写的，包括一份关于 Java 类库的详细参考，称为 API 规范（API Specification）。“API”代表应用程序编程接口。

Java 极具平台无关性；与许多其他语言编写的程序不同，同一个 Java 程序可以在许多不同的操作系统上执行，例如 Windows、Linux 和 Mac OS。

Java 被广泛应用于研究和商业应用，这意味着在市场上存在大量针对熟练 Java 程序员的编程工作。在 Google 上搜索“Java jobs”这一短语示例返回了 124,000,000 条搜索结果。

## Java 编程环境

在开始编程之前，你必须熟悉你的计算机设置。每台计算机为程序开发提供不同的环境，但有一些共同元素值得关注。无论你使用什么环境，你都将遵循相同的三个基本步骤：

1. 以 Java 类的形式输入程序。
2. 编译程序文件。
3. 运行编译后的程序版本。

大多数计算机的基本存储单元是文件。每个文件都有一个名称。文件以扩展名结束，扩展名是文件名中点之后的部分。文件的扩展名指示文件中包含的数据类型。例如，扩展名为`.doc`的文件是 Microsoft Word 文档，扩展名为`.mp3`的文件是音频文件。

你创建的 Java 程序文件必须使用扩展名`.java`。当你编译 Java 程序时，生成的 Java 字节码存储在具有相同名称和扩展名`.class`的文件中。

大多数 Java 程序员使用所谓的集成开发环境（Integrated Development Environments，简称 IDEs），它们提供了一个用于创建、编辑、编译和执行程序文件的全合式环境。入门计算机科学课程中最流行的选择是 Eclipse、IntelliJ、BlueJ 和 Notepad。你的老师会告诉你你应该使用什么环境。

## 输入、编译和运行 Java 程序

在你的 IDE 中输入以下简单程序：

```java
public class Hello {
    public static void main(String[] args) {
        System.out.println("Hello, world!");
    }
}
```

现在不要担心这个程序的细节。我们将在下一节中探索它们。一旦你创建了程序文件，就移动到第 2 步并编译它。编译命令在每个开发环境中都会有不同，但过程是相同的（典型的命令是`compile`或`build`）。如果报告了任何错误，请回到编辑器修复它们，并再次编译程序。（我们将在本章稍后部分详细讨论错误。）

一旦你成功编译了程序，你就准备好移动到第 3 步：运行程序。再次，执行此操作的命令将随环境的不同，但过程是类似的（典型的命令是`run`）。

图 1.1 中的图表总结了创建一个名为`Hello.java`程序时将遵循的步骤。

在某些 IDE 中（最著名的是 Eclipse），前两个步骤是合并的。在这些环境中，编译过程是增量的；当你输入代码时，系统会警告你有错误。通常不需要正式要求此类环境编译你的程序，因为它在你输入时就已经正在编译了。

当你的程序执行时，它通常会与用户交互。图 1.1 中的图表总结了创建一个名为`Hello.java`程序时将遵循的步骤。

![控制台窗口](img/aea896a4bced58de45f29f3)

### 控制台窗口（Console Window）

一个 Java 程序与用户交互的特殊文本窗口。

控制台是一种经典的交互机制，计算机显示文本有时等待用户输入。这被称为*控制台*（console）或*终端*（terminal）交互。计算机打印到控制台的文本被称为输出（output）。用户输入的任何内容都被识别为输入（input）。

为了保持简单，本书中的大多数示例程序都涉及控制台交互。保持交互简单让你将注意力和精力放在编程的其他方面。对于感兴趣的人，第 14 章介绍了如何编写使用更多图形界面的程序。

## 1.2 现在——Java

是时候看一个完整的 Java 程序了。计算机科学中有一个传统，当你决定一门新语言时，应该从一个产生单行输出“Hello world!”的程序开始。“Hello world”传统被许多 Java 书作者打破了，因为用 Java 编写该程序既短又简单，我们将在这里使用它。

这是我们的“你好世界”程序：

```java
public class Hello {
    public static void main(String[] args) {
        System.out.println("Hello, world!");
    }
}
```

这定义了一个类`Hello`。（行号不是程序的一部分但作为辅助。）Sun 规定类名始终以大字母开头，这使其很容易识别。Java 要求类名和文件名匹配，因此此程序必须存储在名为`Hello.java`的文件中。你现在不需要理解这个程序的所有细节，但你需要理解它的基本结构。

记住，Java 代码的基本单元是类。每个程序都包含在 Java 类中。Java 类的基本形式如下：

```java
public class <name> {
    <method>
    <method>
    ...
    <method>
}
```

## 1.2 现在我们来看 Java

这种描述被称为“语法模板”（syntax template），因为它描述了 Java 构造的基本形式。Java 有一套规则来决定其合法的语法或文法。每当我们引入 Java 的新元素时，我们都会查看它的语法模板。按照惯例，我们使用小于号（`<`）和大于号（`>`）字符作为语法模板，表示需要填充的项（在这种情况下，是类名和方法名）。当我们在元素列表中编写`...`时，我们表示可以包含任意数量的元素。

类的第一行被称为类头（class header）。类头中的`public`单词表示该类供任何人使用。注意，程序代码被包含在大括号字符（`{ }`）中。这些字符在 Java 中用于将相关的代码分组。

## 分组字符（Grouping Characters）

Java 使用大括号字符`{`和`}`将相关的代码行分组。

在这种情况下，大括号表示其内部定义的所有内容都是这个公共类（public class）的一部分。

那么，大括号内部到底可以出现什么？类中可以包含什么？各种东西都有，但目前我们将范围限制在方法上。方法是 Java 中更最小的代码单元。一个方法代表要执行的单一操作或计算。

## 方法（Method）

代表特定操作或计算的程序。

简单的方法就像动词：它们命令计算机执行某些操作。至少，一个完整的程序需要一个特殊的方法，称为主方法（main method）。它具有以下语法：

```java
public static void main(String[] args) {
    <statement>;
    <statement>;
    <statement>;
}
```

正如类的第一行被称为类头一样，方法的的第一行被称为方法头（method header）。`main`方法的头部相当复杂。大多数人将其背诵为一种魔法咒语。你想打开阿里巴巴山巴巴洞穴的大门吗？你就说：“芝麻开，开门（Open sesame）”。你想创建一个可执行的 Java 程序吗？你得说：`public static void main(String[] args)`。一群 Java 学习者通过一个名为`publicstaticvoidmain.com`的网站来调侃这一点。

仅仅记忆魔法咒语永远是不满足的，特别是对于那些想要了解程序中发生一切事情的计算机科学家来说。但这是 Java 展示其丑陋一面的地方，你只能忍受它。像你这样的新程序员必须在不理解其工作原理的情况下学会使用它。幸运的是，当你读完这本书时，你将理解这段咒语的每一个部分。

注意，`main`方法有自己的一组大括号。它们再次用于分组，表示它们之间的所有内容都是`main`方法的一部分。大括号之间的行指定了执行程序时要执行的一系列动作。我们把这些称为程序的语句（statements）。就像你通过组合完整的句子来撰写散文一样，你通过组合语句来写成一个方法。

## 语句（Statement）

代表完整命令的可执行代码片段。

"hello world"程序只有一个语句语句，被称为`println`语句：

```java
System.out.println("Hello, world!");
```

注意，该语句以分号结尾。分号在 Java 中有特殊的用途；它用于终止语句，就像英语中的句号终止句子一样。

分号字符`;`在 Java 中用于终止语句。

在基础的"hello world"程序中，只有一个命令来产生一行输出，但请考虑以下变体（称为 Hello2），它在`main`方法中有四行代码要执行：

```java
public class Hello2 {
    public static void main(String[] args) {
        System.out.println("Hello, world!");
        System.out.println();
        System.out.println("This program produces four");
        System.out.println("lines of output.");
    }
}
```

注意`main`方法中有四个分号，分别位于四个`println`语句的末尾。按照它们出现的顺序从第一个到最后一个执行语句，因此 Hello2 程序产生了以下输出：

```text
Hello, world!

This program produces four lines of output.
```

让我们总结一下刚刚看过的不同层次：

- 一个 Java 程序存储在类（class）中。
- 在类内部你可以包含方法。至少，一个完整的程序要求你有一个名为`main`的特殊方法。
- 在像`main`这样的方法内部，你包含了一系列语句，每个语句都代表计算机执行的单一命令。

将左括号放在行末尾而不是单独占一行，可能看起来很奇怪。有些人会在程序中使用这种缩进风格。

```java
public class Hello {
    public static void main(String[] args) {
        System.out.println("Hello, world!");
    }
}
```

不同的人对大括号的位置会有不同的选择。我们使用的风格遵循 Sun 官方的 Java 编码规范，但另一种风格也有它的支持者。人们经常会激烈地争论某一种方法比另一种好得多，但这实际上是个人喜好的问题；每种选择都有优缺点。你的老师可能要求特定的风格；如果没有，你应该选择一种你感到熟悉的风格并一如一地使用。

现在你已经看到了结构的概览，让我们检查 Java 的细节之一。

在编写 Java 程序时（例如前面的"hello world"程序），你通常想在控制台窗口中包含一些字面文本。程序员传统上将文本称为字符串（strings），因为它是由字符序列组成的。Java 语言规范使用“字符串字面量”（string literals）一词。在 Java 中，你通过用双引号围绕字面文本来指定字符串字面量，例如：

```text
"This is a string."
```

以下不是有效的字符串字面量：

```text
'Bad stuff here.'
```

### 你知道吗？

#### Hello, World!

"hello world"由布莱恩·柯尼汉（Brian Kernighan）和丹尼斯·里奇（Dennis Ritchie）开始，他们在 20 世纪 70 年代发明了名为 C 的编程语言。他们在 1978 年写的描述该语言的书中的第一个完整程序是一个"hello world"程序。从那时起，柯尼汉、里奇以及他们的书籍《许可证》一直被亲切地称为"K & R"。许多主要的编程语言都借用了 C 的基本语法，以利用 C 的流行性并鼓励程序员切换。C++ 和 Java 都从 C 借用了大量的代码语法。

柯尼汉和里奇在括号放置位置和程序缩进方面也有独特的风格，这种风格被称为“K & R 风格”。这是 Sun 推荐的风格，也是我们使用的风格。

以下是有效的字符串字面量：

> "This is a quote even with 'these' inside."

字符串字面量不能跨越程序的行。以下是有效的字符串字面量：

> "This is really
>
> bad stuff here."

## `System.out.println`

正如你所看到的，Java 程序的`main`方法包含一组供计算机执行的语句。它们按顺序执行，从第一个语句开始，然后是第二个、第三个，以此类推，直到执行最后一个语句。简单且常用的语句之一是`System.out.println`，它用于产生一行输出。这是另一个你应该牢记于心的“魔法咒语”。截至本文写作，Google 列出了超过 6000 个网页提到了`System.out.println`。记住这个语句的关键是它用于产生发送到控制台窗口的输出行。

`println`语句的最简单形式是括号内没有任何内容，产生一个空行：

```java
System.out.println();
```

即使括号内没有放入任何内容，你也需要包含括号。注意行末的分号。Java 中的所有语句都必须以分号终止。

## 1.2 现在来学习 Java

此外，你使用`println`来输出一行文本。



```java
System.out.println("This line uses the println method.");
```

上述语句命令计算机产生以下输出行：

```text
This line uses the println method.
```

每个`println`语句都会产生一个不同的输出行。例如，如果你执行以下三个语句：

```java
System.out.println("This is the first line of output.");
```

```java
System.out.println();
```

```java
System.out.println("This is the third, below a blank line.");
```

则会随之产生以下三行输出（第二行是空的）：

```text
This is the first line of output.

This is the third, below a blank line.
```

## 转义序列

任何涉及文本引用的系统都会让你陷入某些困难的境地。例如，字符串字面量包含在引号内，那么你该如何在字符串字面量内部包含一个引号呢？字符串字面量不允许跨行，那么你如何在字符串字面量内部包含一个换行符呢？

解决方案是在字符串字面量中嵌入所谓的转义序列（escape sequences）。转义序列是用于表示特殊字符的两个字符序列。它们都以反斜杠字符（`\`）开头。下表列出了一些常见的转义序列。

| 序列 | 表示 |
| --- | --- |
| `t` | 制表符 |
| `\n` | 换行符 |
| `"` | 引号 |
| `\` | 反斜杠字符 |

记住，这些双字符序列中的每一个实际上只代表一个单独字符。例如，如果你执行以下语句：

```java
System.out.println("What \characters" does this \?");
```

你将得到以下输出：

```text
"What characters" does this \?
```

# 第一章 Java 编程简介

`println`中的字符串字面量有三个转义序列，每个长度两个字符，但它们产生一个单个字符输出。

虽然字符串字面量本身不能跨多行（即你不能在字符串字面量内部使用回车符来强制换行），但你可以使用`\n`转义序列在字符串中嵌入换行符。这导致了一个奇怪的情况：单个`println`语句可以产生多行输出。

例如：

```java
System.out.println("This produces 3 lines\nof output.");
```

你将得到以下输出：

```text
This
produces 3 lines
output.
```

`println`本身产生一行输出，但字符串字面量包含两个换行符，导致它被分成总共三行输出。要在不使用换行符的情况下产生相同的输出，你必须发出三个独立的`println`语句。

这是另一种往往根据喜好而变化的编程习惯。有些人（包括作者在内）认为阅读包含包含转义序列的字符串字面量很困难，但另一些人倾向于编写更少的代码行。再次，你应该自己决定何时何时使用换行转义序列。

## 标识符和关键字

用于命名 Java 程序组成部分的单词被称为标识符（identifiers）。标识符指定程序中类、方法或其他实体的名称。

赋值给程序中实体（如类或方法）的名称。

标识符必须以字母开头，可以跟随任意数量的字母或数字。以下都是合法的标识符：

```text
first
hiThere
numStudents
By4
```

Java 语言规范定义的字母集包含了下划线和美元符号（`_`和`$`），这意味着以下也是合法的标识符：

```text
two_plus_tw
__count
$2donuts
MAX_COUNT
```

以下是非合法的标识符：

```text
twottwo
hi there
hi-There
2by4
```

Java 有关于大小写的约定，程序员们遵循得相当一致。所有的类名都应该以大写字母开头，就像之前介绍的`Hello`方法类一样。在`main`方法中，方法名应该以小字母开头。1.2 现在：Java

当将几个单词组合成类或方法名时，将第一个单词之后的每个单词的首字母大写。在下一章我们将讨论常量，常量有另一种大小写方案：所有字母大写并用下划线分隔。这些不同的方案可能看起来是繁琐的限制，但在代码中使用一致的大小写可以让查看者快速识别各种代码元素。

例如，假设你打算将 "all my child-ren" 这些单词放入一个标识符中。结果将是：

- 类名使用`AllChildren`（每个单词大写开头）。
- 方法名使用`allChildren`（以小字母开头，后续单词大写）。
- 常量名使用`ALL_CHILDREN`（全大写，用下划线分隔；在第二章描述）。

Java 是大小写敏感的，标识符`class`、`Class`、`CLASS`和`cLAS`都是不同的。在阅读编译器的错误信息时请记住这一点。人们擅长理解你写的内容，即使你漏掉了单词或犯了小错误（如改变了单词的大小写）。然而，这些错误会导致 Java 编译器变得无从救于混乱。

不要犹豫使用长标识符。你的名称越具描述性，人们（包括你自己）阅读你的程序时就越容易。描述性的标识符值得花费输入时间，例如 Java 的`String`类就有一个名为`compareIgnoreCase`的方法。

注意，Java 有一组预定义的标识符称为关键字（keywords），它们被保留用于特定用途。当你阅读这里时，将学习许多关键字以及它们的用途。你只能按照它们的预期用途使用关键字。你必须小心在使用这些词定义自己的内容。例如，如果你使用`short`或`try`，这将导致问题。这是完整的关键字列表。

## Java 关键字

|  |  |  |  |
| --- | --- | --- | --- |
| `abstract` | `continue` | `for` | `switch` |
| `assert` | `default` | `goto` | `synchronized` |
| `boolean` | `do` | `if` | `this` |
| `break` | `double` | `import` | `throw` |
| `byte` | `else` | `instanceof` | `transient` |
| `case` | `enum` | `int` | `try` |
| `catch` | `extends` | `interface` | `void` |
| `char` | `final` | `long` | `volatile` |
| `class` | `finally` | `native` |  |
| `const` | `float` | `super` | `while` |

（注：`const`在 Java 中保留）

# 第一章 Java 编程简介

## 复杂示例：DrawFigures1

`println`语句可以绘制文本图形。考虑这个更复杂的示例。注意它使用了两个`println`语句来产生空行。

```java
public class DrawFigures1 {
    public static void main(String[] args) {
        System.out.println(" /\\");
        System.out.println(" / \\");
        System.out.println(" / /\\");
        System.out.println("  /  ");
        System.out.println(" / \\");
        System.out.println("\\");
        System.out.println("");
        System.out.println("      /      ");
        System.out.println("     /     ");
        System.out.println("    /    ");
        System.out.println("   / \");
        System.out.println("  /  ");
        System.out.println(" / ");
        System.out.println("");
        System.out.println("  /  ");
        System.out.println(" / /\\");
        System.out.println(" / \\");
        System.out.println("++------+");
        System.out.println("|      |");
        System.out.println("|      |");
        System.out.println("++------+");
        System.out.println("| United|");
        System.out.println("| States |");
        System.out.println("++------+");
        System.out.println("|      |");
        System.out.println("|      |");
        System.out.println("++------+");
        System.out.println("  /  ");
        System.out.println(" / /\\");
        System.out.println(" / \\");
    }
}
```

以下是它产生的输出。注意程序中包含了双反斜杠字符（`\\`），但输出是单反斜杠字符。这就是之前描述的转义序列的一个示例。

## 1.2 现在让我们——Java

## 注释与可读性

Java 是一种自由格式的语言。这意味着你可以根据意愿添加任意数量的空格和空行，只要在单词之间至少保留一个空格或其他标点符号即可。然而，你应该记住，程序的布局可以增强（或损害）其可读性。以下程序是合法的，但很难阅读：

```java
public class Ugly(public static void main(String[] args)
{System.out.println("How short I am!");}}
```

以下是一些可以遵循的简单规则，它们将使你的程序更具可读性：

- 将类头和方法方法头单独放在一行。
- 每行不要超过一个语句。
- 正确地对程序进行缩进。当出现左括号时，增加后续行的缩进；当出现右括号时，减少缩进。使用一致的空格数对大括号内的语句进行缩进（常见的做法是每层缩进四个空格）。
- 使用空行分隔程序的不同部分（例如方法）。

使用这些规则重写`Ugly`程序可以得到如下结果：

```java
public class Ugly {
  public static void main(String[] args) {
    System.out.println("How short I am!");
  }
}
```

## 第一章 Java 编程入门

编写良好的 Java 程序可以具有很可读性，但你通常希望包含一些不属于程序本身的解释。你可以通过在程序中放入名为“注释”的备注对程序进行标注。

## 注释

程序员为了解释其代码而包含的文本。编译器会忽略注释。

Java 中有两种注释形式。在第一种形式中，用斜杠加星号`/*`开启，用星号加斜杠`*/`关闭：

```java
/* this */
```

你不能在斜杠和星号之间放置空格：

```java
/*this is bad */
```

你可以在注释中放入几乎任何喜欢的文本，包括多行内容：

```java
/* Thaddeus Martin
* Assignment #1
* Instructor: Professor Walingford
* Grade: Bianca Montgomery */
```

你唯一不允许在注释中放入的是注释结束字符。以下内容是不合法的：

```java
/* This comment has an asterisk/slash /*/ in it,
which prematurely closes the comment. This is bad. */
```

Java 还提供了一种用于更短的单行注释的格式。你可以连续使用两个斜杠`//`表示当前行的剩余部分（两个斜杠右侧的所有内容）是注释。例如，你可以在语句之后添加注释：

```java
System.out.println("You win!"); // Good job!
```

或者你可以在单独的一行创建一个注释：

```java
// give an introduction to the user
System.out.println("Welcome to the game of blackjack.");
System.out.println();
System.out.println("Let me explain the rules.");
```

你甚至可以创建单行注释块：

```java
// Thaddeus Martin
// Assignment #1
// Instructor: Professor Walingford
// Grade: Bianca Montgomery
```

## 1.3 程序错误

有些人倾向于使用另一种形式来编写多行注释，但使用第二种形式更安全，因为你不需要忘记关闭注释。它还能让注释更加突出。这是另一种情况：除非老师或同事明确要求你使用特定的注释样式，否则你应该自己决定更倾向于哪种风格并保持一致。

不要将注释与打印语句的文本混淆。你的注释文本在程序执行时不会显示为输出。注释的作用仅是帮助读者检查和理解程序。

在每个类的开头包含注释以说明该类的功能是一个好主意。你可能还想包含关于你的信息、你正在修的课程、你的老师和/或评分员的名字、当前日期等。你还应该对每个方法进行注释，说明它的功能。

在更大、更复杂的程序中，以及由多个程序员查看或修改的程序中，注释会变得更有用。清晰的注释对于向他人（或在以后向你自己）解释你的程序在做什么以及为什么要这么做非常有帮助。

除了上述两种注释形式外，Java 还支持一种特殊的注释样式，称为 Javadoc 注释。它们的格式更复杂，但优点可以使用程序提取注释以生成适用于 Web 浏览器阅读的 HTML 文件。Javadoc 注释在高级编程中非常有用，并在附录 C 中进行了详细讨论。

## 1.3 程序错误

1949 年，计算领域的早期先驱 Maurice Wilkes 表达了一种至今仍然成立的感触：

> 我们一开始编程，就惊讶地发现，写出正确的程序并没有我们想象中那么容易。调试必须被发现。我清楚地记得那个时刻，我意识到从那以后，我生命的大部分都将花在寻找我自己程序中的错误上。

在你学习编程时，也必须面对这个现实。你会犯错，就像历史上的任何其他程序员一样；而且你需要策略来消除这些错误。幸运的是，计算机本身可以帮助完成部分工作。

在编写程序时，你会遇到三种类型的错误：

- **语法错误（Syntax errors）**：在你误用 Java 时发生。它们相当于编程中的“糟糕语法错误”，并由 Java 编译器捕获。
- **逻辑错误（Logic errors）**：在你编写的代码没有执行其预期的任务时发生。
- **运行时错误（Runtime errors）**：极其严重的逻辑错误，以至于 Java 停止你的程序执行。

# 第一章 Java 编程入门

## 语法错误

人类对语言中的细微错误往往很宽容。例如，我们可能觉得很奇怪，但当尤达大师（Master Yoda）说“你急于去面对他……很遗憾，你的训练还不完整。你还没有准备好。”时，我们通常能理解他的意思。

Java 编译器将少宽容得多。如果你的程序违反了任何 Java 语法规则，编译器在尝试将你的程序从 Java 翻译成字节码时报告语法错误。例如，如果你在程序中错放了一个分号，可能会让编译器进入混乱状态。编译器可能会报告几条错误信息，取决于它认为你的程序出了什么问题。

产生编译错误的程序无法执行。如果你将程序提交给编译器并报告了错误，你必须修复错误并重新提交程序给编译器。在你的程序没有编译错误之前，你无法继续进行。

某些开发环境（如 Eclipse）会在你编写程序时通过下划线标记语法错误来帮助你。这让你能够轻松地发现错误发生的具体位置。

如果你选择了错误的文件名，在开始编写程序之前就会引入错误。

### 常见编程错误

## 文件名与类名不匹配

如前，Java 要求程序的类名和文件名匹配。例如，以`public class Hello`开头的程序必须存储在名为`Hello.java`的文件中。

> 如果你使用了错误的文件（例如保存为`WrongFileName.java`），你会得到类似的错误信息：
>
> `WrongFileName.java: class Hello is public, should be declared in a file named Hello.java`

```java
public class Hello {
```

文件名只是第一道关卡。你的 Java 程序中可能存在许多其他错误。最常见的语法错误之一是漏掉单词。由于拼写问题，你可能会遇到标点错误，例如缺少分号。分号并不是你在编写程序时唯一可能忘记的。你也可能会忘记整个单词，例如某个所需的关键字。

编译器提供的错误信息可能并不有用。如果你不理解错误信息的内容，请查看下方的箭头标记`^`，它指向行中编译器感到混乱的位置。这可以帮助你精确定可能缺少关键字的位置。

# 第一章 Java 编程简介

## 常见的编程错误

### 单词拼写错误

Java（与大多数编程语言一样）对拼写非常挑剔。你需要正确拼写每个单词，包括正确的大小写。例如，假设你将 "hello world" 程序中的`println`语句替换为：

```java
System.out.println("Hello, world!");
```

当你尝试编译这个程序时，它会生成一条类似于下方的错误消息：



```text
Hello:3: cannot find symbol
symbol : method println(java.lang.String)
location: class java.io.println("Hello, world!");
```

输出的第一行表示错误发生在`Hello.java`文件的第 3 行，错误内容是编译器找不到某个符号（symbol）。第二行表示它找不到的符号是一个名为`println`的方法。这是因为没有这样的方法：该方法的名称应该是`println`。错误消息的形式可能会根据你拼错的单词而略有不同。例如，如果你忘记了将`System`单词大大写：

```java
system.out.println("Hello, world!");
```

你会得到以下错误消息：

```text
Hello:3: package system does not exist
system.out.println("Hello, world!");
^
+ 1 error
```

再次，第一行表示错误发生在`Hello.java`文件的第 3 行。不过，这里的错误略有不同，表示它找不到名为`system`的包。该错误消息的第二和第三行包含了原始代码行，并有一个箭头（caret）指向编译器感到困惑的地方。编译器错误并不总是非常清晰，但如果你留意箭头指向的位置，你就能很好地判断出错误发生的位置。

如果你仍然无法确定错误所在，可以尝试查看错误行号，并将该行的内容与其他程序中的相似行进行比较。你也可以请求其他人员（例如讲师或实验助教）检查你的程序。另一种常见的语法错误是忘记了闭合字符串字面量。

# 第一章 Java 编程导论

## 常见的编程错误

### 遗漏分号

所有的 Java 语句都必须以分号结束，但在语句末尾加上分号很容易的，如下面程序所示：

```java
public class MissingSemicolon {
    public static void main(String[] args) {
        System.out.println("A rose by any other name")
        System.out.println("would smell as sweet");
    }
}
```

在这种情况下，编译器产生的输出类似于下所示：

```text
MissingSemicolon.java:4: ':' expected
System.out.println("would smell as sweet");
1 error
```

编译器输出中奇怪的地方在于，它将第 4 行列为问题的原因，而不是实际上遗漏分号的第 3 行。这是因为编译器正在向前寻找分号，在它发现某个不是分号的内容之前，它不会感到恼火，而它在到达第 4 行时发现了这一点。遗憾的是，如这个案例所示，编译器错误消息并不总是引导你找到需要修复的正确行。

一个值得遵循的经验是：编译器报告的第一个错误是最需要关注的。其他的错误可能是第一个错误导致的。许多程序员甚至懒得去查看第一个错误之后的错误，因为修复第一个错误并重新编译可能会导致其他错误消失。

## 逻辑错误（Bug）

逻辑错误也被称为 bug。计算机程序员使用“bugridden”（满 bug 的）和“buggy”（多错误的）等词来描述编写得糟糕的程序，而从程序发现发现并消除 bug 的被称为调试（debugging）。

“bug”一词是一个古老的工程术语，早于计算机；早期的计算 bug 出现在硬件和软件中。计算领域的先驱格蕾丝·霍珀（Grace Hopper）海军上将对计算机编程背景下推广该术语的使用做出了很大贡献。她经常讲述 20 世纪 40 年代中期哈佛大学一组程序员的真实故事，他们发现程序有问题时，竟然在里面发现了一只被困的蛾子。

bug 的形式有很多。有时你的程序仅仅是表现不当。例如，它可能会产生错误的输出。其他时候，它会要求计算机执行某些明显错误的任务，此时你的程序会发生运行时错误（runtime error）并停止执行。在这种情况下，由于

# 1.4 过程化分解

## 常见的编程错误

### 遗漏必要的关键字

另一种常见的语法错误是在编译程序时忘记了必要的关键字，例如`static`或`class`。请对照教材中的示例双检你的程序，以确保你没有遗漏重要的关键字。

编译器会根据缺失哪个关键字给出不同的错误消息，但这些消息可能很难理解。例如，你可能写了一个名为`Bug4`的程序，在编写类头时忘记了关键字`class`。在这种情况下，编译器将提供以下错误消息：

```text
Bug4.java:1: 'class' or 'interface' expected
public Bug4 {
    error
```

然而，如果你在声明`main`方法时忘记了`void`，编译器会生成不同的错误消息：

```text
Bug5.java:2: invalid method declaration; return type required
public static void main(String[] args) {
    error
```

如果你对 Java 的知识有限，通常你看到的唯一逻辑错误类型就是由于错误的`println`或方法调用导致的程序输出错误。我们将在下一节查看一个运行时错误的示例。

# 1.4 过程化分解

C 语言的创建者之一布莱恩·柯宁（Brian Kernighan）曾说过：“控制复杂性是编程的本质。”人们对细节的能力有限。我们无法一次性解决复杂问题。相反，我们通过将问题分解为各个部分来组织问题。我们经常使用“分解”一词来描述这一原则。

> 分解：划分为可识别的部分，每个部分都比整体更简单。

在像 C 这样的过程化语言中，分解涉及将复杂任务划分为一组子任务。这是一种非常面向动作的方法，将整体动作分解为更小的动作。这种技术被称为过程化分解。

# 第一章 Java 编程导论

## 常见的编程错误

### 未关闭字符串字面量或注释

每个字符串字面量都必须有一个起始引号和一个结束引号，但很容易忘记写结束引号。例如，你可能会写成：

```java
System.out.println("Hello, world!");
```

这产生了两个不同的错误消息，尽管只有一个底层语法错误：

```text
Hello.java:3: unclosed string literal
System.out.println("Hello, world!");
```

```text
Hello.java:4: ') expected
/
```

在这种情况下，第一个错误消息非常清晰，箭头指向未关闭字符串字面量的开头。第二个错误消息是由第一个错误引起的。由于字符串字面量没有关闭，编译器没有注意到行尾的右括号和分号。

当你忘记通过编写`/*`来关闭多行注释时，会出现类似的问题，如下所示程序的第一行：

```java
/* 这是一个糟糕的程序。
public class Bad {
    public static void main(String[] args) {
        System.out.println("Hi there.");
    }
}
/* end of program */
```

前面的文件没有关闭；它是一段长注释。因为第一行的注释没有关闭，整个程序都被吞掉了。

幸运的是，许多 Java 编辑器会对程序部分着色以帮助你视觉识别。通常，如果你忘记关闭字符串字面量或注释，程序的其余部分会变成错误的颜色，这可以帮助你发现错误。

Java 的设计是为了一种不同的分解方法，这种方法更非面向对象。我们不再将问题视为一系列要执行的动作，而是将其视为一组相互作用的对象的集合。

作为一名计算机科学家，你应该熟悉这两种解决问题的方法，而本书花费了许多章节来掌握过程化方法的各个方面。只有当你彻底

# 1.4 过程化分解

一旦我们练习了过程化编程，就会把注意力重新回到对象分解和面向对象编程。

作为过程化分解的一个例子，考虑烤蛋糕的问题。你可以将此问题划分为以下子问题：

- 制作面糊。
- 烘焙蛋糕。
- 制作糖霜。
- 给蛋糕涂糖霜。

这四个任务中的每一个都有与其相关的细节。例如，为了制作面糊，你需要：

- 混合干原料。
- 搅拌奶油和糖。
- 打入鸡蛋。
- 拌入干原料。

因此，你将整体任务划分为子任务，并进一步划分为更小的子任务。最终，你将达到简单到不需要进一步解释的描述（即原始操作）。图 1.2 显示了这种分解的局部图。“制作蛋糕”是最高级别的操作。它由四个较低级的操作定义，称为“制作面糊”、“烘焙”、“制作糖霜”和“给蛋糕涂糖霜”。“制作面糊”操作由更低层次的操作定义，其他三个操作也是如此。我们使用旨在展示问题如何分解为子问题的图表。在这个图中，你也可以通过从左到右阅读来判断操作的顺序。这在大多数结构图中是不成立的。你通常需要参考程序本身。

处理问题的两种风格被称为自底而上和自顶而下。为了做一个蛋糕，你可能会从顶部开始并推理：“我可以通过先制作面糊，然后烘焙，制作糖霜，最后把糖霜涂在蛋糕上来制作蛋糕。我可以先这样制作面糊……”这是一个自顶而下的解决方案；它从最高级别开始向下进行。

自底而上的解决方案涉及此类推理：“我现在能做什么？我可以组合干原料。如果我搅拌了奶油和糖，然后打入鸡蛋，再拌入干原料，我就得到了一些奶油。如果我烘焙这些面糊，就会得到一个没有涂糖霜的蛋糕。如果我……”这是一个自底而上的解决方案，因为它从低级操作开始，并将它们组合成更高级的操作。

最后一个问题解决术语与编程过程有关。专业程序员分阶段开发程序。他们并不试图一次生成一个完整的运行程序，而是选择问题的某部分先进行实现。然后添加另一部分，再一部分，再一部分。整个程序缓慢地、一段一段构建起来。这个过程被称为迭代增强或逐步细化。

# 迭代增强

分阶段生成程序的过程，在每个阶段添加新功能。每个迭代步骤的一个特征是，你可以在继续之前对其进行测试，确保该部分工作正常。

现在，让我们考虑一种允许你迭代增强 Java 程序以改进其结构并减少冗的结构：静态方法。

# 静态方法

Java 是为对象设计的，在 Java 中编程通常涉及将问题分解为各种对象，每个对象都有执行特定任务的方法。你将在后面的章节中看到它是如何运作的，但现在，我们将探索过程化分解。这允许我们在讨论泛泛编程时，推迟检查 Java 的某些细节。

考虑以下程序，它在控制台上画两个框：

```java
public class DrawBoxes {
    public static void main(String[] args) {
        System.out.println("+----");
        System.out.println("|----|");
        System.out.println("|      |");
        System.out.println("+----+");
        System.out.println("+----");
    }
}
```

该程序运行正常，但用于画框的四行代码出现了两次。这种冗余出于几个原因是不利的。例如，你可能希望改变框的外观，在这种情况下你将必须进行两次编辑。此外，你可能想画额外的框，这将要求你输入额外的副本（或复制粘贴）冗余行。

一个更好的解决方案是创建一个 Java 命令来指定如何画框，并执行两次该命令。Java 没有“画框”的命令，但你可以创建一个。这种命名的命令被称为静态方法。

# 静态方法

一组被命名的 Java 语句块。

静态方法是过程化分解的单元。我们通常将一个类分解为几个方法，每个方法解决整体问题的某部分。例如，这里有一个画框的静态方法：

```java
public static void drawBox() {
    System.out.println("+----+----+");
    System.out.println("|      |");
    System.out.println("|      |");
    System.out.println("+----+----+");
}
```

你已经在之前的程序中见过过调用的静态方法。记得`main`方法具有如下形式：

```java
public static void main(String[] args) {
    <statement>;
    <statement>;
    ...
    <statement>;
}
```

你将编写静态方法具有相似的结构：

```java
public static void <name>() {
    <statement>;
    <statement>;
    ...
    <statement>;
}
```

第一行被称为方法头。现在你不需要完全理解此方法头每个部分的含义，但请记住方法头中单词的含义：

- `public`：表示此方法可以被你程序的所有部分使用。
- `static`：表示这是一个静态（过程化）方法。
- `void`：表示此方法执行，但不返回任何值。
- `<name>`：是方法的名称。
- `()`：指定发送到你的方法的值列表（在此例中为空空列表）。

# 1.4 过程化分解

## 控制流

静态方法最让人困惑的地方在于，带有静态方法的程序并不是从上到下顺序执行的。相反，每当程序遇到静态方法调用时，程序的执行会“跳转”到该静态方法，按顺序执行该方法中的每条语句，然后“跳转”回调用开始的地方并继续执行。程序中语句执行的顺序被称为程序的控制流。

## 控制流

按照 Java 程序语句执行的顺序。

让我们看看之前展示的`DrawBoxes2`程序的控制流。它有两个方法。第一个方法是熟悉的`main`方法，第二个是`drawBox`。和任何 Java 程序一样，执行从`main`方法开始：

```java
public static void main(String[] args) {
    drawBox();
    System.out.println();
    drawBox();
}
```

从某种意义上说，程序的执行是顺序的：`main`方法中列出的每个语句按从到后的顺序执行。

但这个`main`方法包含了两次对`drawBox`方法的调用。程序将执行三件事：执行`drawBox`，执行一个`println`，然后再次执行`drawBox`。

追踪控制流通常是有用的。下面的图捕捉了这样一个思想：你正在执行`main`方法，它涉及三个不同的步骤，其中两个步骤涉及执行`drawBox`方法：

```text
execute main method:
    execute drawBox method
    System.out.println();
    execute drawBox method
```

但当你要求 Java 执行`drawBox`方法时会发生什么？你将控制权转移到该方法及其每条语句，然后回到你之前离开的地方。因此，你可以扩展此图以显示当你对`drawBox`方法进行两次调用时发生了什么：

```text
execute main method:
    execute drawBox method:
    System.out.println("+------+");
    System.out.println("|      |");
    System.out.println("|      |");
    System.out.println("+------+");
```

`System.out.println()`：

execute drawBox method:

```java
System.out.println("|");
System.out.println("||");
System.out.println("-------");
```

控制权转移到`main`方法会导致它的四条`println`语句首先执行。接下来，你返回`main`方法并第二次执行它的`println`语句。然后你再次调用`drawBox`并第二次执行它的四条`println`语句。

结果是，你可以改为执行以下`main`方法：

```java
public static void main(String[] args) {
    System.out.println("-------");
    System.out.println("||");
    System.out.println("||");
    System.out.println("-------");
    System.out.println();
    System.out.println("-------");
    System.out.println("||");
    System.out.println("||");
    System.out.println("-------");
}
```

这个版本在控制流方面更简单，但另一个版本避免了多次出现相同`println`语句的冗余。它还对解决方案的提供了更好的理解。在原始版本中，可以清楚地看到名为`drawBox`的子任务执行了两次。虽然最后版本的`main`方法包含的代码行比`DrawBoxes2`程序少，但考虑一下如果你想在输出中添加第三个框会发生什么：在这里你必须再次添加所有五条必要的`println`语句，而在使用`drawBox`方法的程序中，你只需要添加一个`println`和第三次方法调用。

Java 允许你按喜欢的顺序定义方法。通常的做法是将`main`方法放在类中的第一个或最后一个方法。在本书中我们通常会将`main`放在前面，但如果交换顺序，程序的行为也是相同的。例如，以下修改后的`drawBoxes2`程序的行为完全相同：



```java
public class DrawBoxes3 {
    public static void drawBox() {
        System.out.println("-------");
        System.out.println("||");
        System.out.println("||");
        System.out.println("-------");
    }

    public static void main(String[] args) {
        drawBox();
        System.out.println();
        drawBox();
    }
}
```

## 1.4 过程化分解

`main` 方法始终是程序执行的起点。从这个起点，你可以确定其他方法的调用顺序。

### 调用其他方法

`main` 方法并不是你调用另一个方法的唯一地方。事实上，任何方法都可以调用任何其他方法。结果是控制流可能会变得相当复杂。

例如，考虑下面这段奇怪的短语“foo”、“bar”、“baz”和“mumble”，故意这样写，因为该程序并不是要有逻辑。

```java
public class FooBazMumble {
    public static void main(String[] args) {
        foo();
        bar();
    }

    public static void foo() {
        System.out.println("foo");
        mumble();
        System.out.println();
    }

    public static void bar() {
        System.out.println("bar");
        baz();
    }

    public static void baz() {
        System.out.println("baz");
        mumble();
    }

    public static void mumble() {
        System.out.println("mumble");
    }
}
```

# 第一章 Java 编程简介

我们还没有讨论过如何计算值或读取文件，但有一种方法可以让你“意外”地导致运行时错误。做到这一点的方法是编写一个调用它自身的静态方法。

如果你这样做，你的程序将停止运行，因为该方法将无限地不断调用自己，直到计算机耗尽内存。当这种情况发生时，程序会打印大量的输出行，并最终带有名为 `StackOverflow`（栈溢出）的错误消息停止执行。

```java
public class Infinite {
    public static void main(String[] args) {
        oops();
    }

    public static void oops() {
        System.out.println("Make it stop!");
        oops();
    }
}
```

这个格式错误的程序会产生以下输出（用“...”表示大段行）：

```text
Make it stop!

Make it stop!

Make it stop!

Make it stop!

Make it stop!

Make it stop!

Make it stop!

Make it stop!

Make it stop!

...

Make it stop!

Exception in thread "main" java.lang.StackOverflow

at sun.nio.cs.SingleByteEncoder.encodeArrayLoop(Unknown Source)

at sun.nio.cs.SingleByteEncoder.encodeLoop(Unknown Source)

at java.nio.charset.Charset.encode(Unknown Source)

at java.nio.charset.CharsetEncoder.implWrite(Unknown Source)

at java.nio.charset.CharsetEncoder.write(Unknown Source)

at java.io.OutputStreamWriter.write(Unknown Source)

at java.io.BufferedWriter.write(Unknown Source)

at java.io.PrintStream.newLine(Unknown Source)

at java.io.PrintStream.println(Unknown Source)

at Infinite.oops(Infinite.java:7)

at Infinite.oops(Infinite.java:8)

at Infinite.oops(Infinite.java:8)

at Infinite.oops(Infinite.java:8)

at ...
```

遗憾的是，运行时错误是你在编程时必须面对的事物。你必须仔细确保你的程序不仅能够成功编译，而且不包含任何导致运行时错误的 bug。捕获和修复运行时错误的常见方法是多次运行程序以测试其行为。

## 1.5 案例研究：DrawFigures

在本章的前面，你看到了一个名为 `drawFigures` 的程序，它产生了以下输出：

![](img/aea18896a4bced58de45f29f5a93f7b3_62_0.png)

它是通过在 `main` 方法中使用长序列的 `print` 语句实现的。在本节中，你将使用静态方法进行过程化分解，以捕捉结构并消除冗余。

### 结构化版本

如果你仔细观察输出，你会发现它存在一种结构，这种结构在程序结构中是理想的。输出被分为三个子图：菱形、X 形和火箭。

你可以通过将程序划分为静态方法来更好地标示程序的结构。由于有三个子图，你可以创建三个方法，每个子图一个方法。以下程序产生了与 `drawFigures` 相同的输出：

```java
1 public class DrawFigures {
2   public static void main(String[] args) {
3     drawDiamond();
4     drawX();
5     drawRocket();
6
7     public static void drawDiamond() {
8         System.out.println(" /");
9         System.out.println(" / / ");
10        System.out.println(" ");
11        System.out.println(" / / ");
12        System.out.println(" /");
13        System.out.println();
14    }
15
16    public static void drawX() {
17        System.out.println(" /");
18        System.out.println(" / /");
19        System.out.println(" / / ");
20        System.out.println(" / / ");
21        System.out.println(" ");
22        System.out.println(" /\ ");
23        System.out.println();
24    }
25
26    public static void drawRocket() {
27        System.out.println(" /");
28        System.out.println(" / ");
29        System.out.println(" / / ");
30        System.out.println("-------");
31        System.out.println("| | ");
32        System.out.println("| | ");
33        System.out.println("+----+");
34        System.out.println("|United|");
35        System.out.println("|States|");
36        System.out.println("+----+");
37        System.out.println("| | ");
38        System.out.println("| | ");
39        System.out.println("+----+");
40        System.out.println();
41        System.out.println(" /");
42        System.out.println(" / / ");
43    }
44}
```

程序出现在名为 `DrawFigures` 的类中，并在定义了四个静态方法。第一个静态方法是普通的 `main` 方法，它调用了三个方法。`main` 方法调用的三个方法在后面出现。

### 无冗余的最终版本

程序仍然可以改进。三个子图中的每一个都有独立的元素，其中某些元素出现在三个子图中的多个一个。以下是一组冗余的行，改进后的版本通过为每个子图添加一个方法来消除冗余。冗余的输出是菱形的顶部、底部以及火箭部分。这里是改进后的程序：

```java
public class DrawFigures {
    public static void main(String[] args) {
        drawDiamond();
        drawX();
        drawRocket();
    }

    public static void drawDiamond() {
        System.out.println(" /");
        System.out.println(" / / ");
        System.out.println(" ");
    }

    public static void drawTop() {
        System.out.println(" / / ");
        System.out.println(" /");
        System.out.println();
    }

    public static void drawBottom() {
        System.out.println(" / / ");
        System.out.println(" /");
        System.out.println();
    }

    public static void drawX() {
        System.out.println(" /");
        System.out.println(" / /");
        System.out.println(" / / ");
        System.out.println(" / / ");
        System.out.println(" ");
        System.out.println(" /\ ");
        System.out.println();
    }

    public static void drawRocket() {
        System.out.println(" /");
        System.out.println(" / ");
        System.out.println(" / / ");
        System.out.println("-------");
        System.out.println("| | ");
        System.out.println("| | ");
        System.out.println("+----+");
        System.out.println("|United|");
        System.out.println("|States|");
        System.out.println("+----+");
        System.out.println("| | ");
        System.out.println("| | ");
        System.out.println("+----+");
        System.out.println();
        System.out.println(" /");
        System.out.println(" / / ");
    }
}
```

程序出现在名为 `DrawFigures` 的类中，并在其中定义了四个静态方法。第一个静态方法是普通的 `main` 方法，它调用了三个方法。`main` 方法调用的三个方法在后面出现。

## 执行流分析

图 1 显示了静态方法调用哪些方法以及它们又调用了哪些静态方法。正如你看到的，该程序具有三层结构和两层分解。整个任务被拆分为三个子任务，每个子任务又有两个。

带有方法的程序控制流比没有方法的要复杂，但规则仍然相当简单。记住，当方法被调用时，计算机会执行该方法体内的语句。然后，跳转到方法调用后的后续语句。此外，记住计算机总是从 `main` 方法开始。

因此，在执行 `Figures` 程序时，计算机首先执行 `main` 方法。反之，它首先执行 `drawDiamond` 方法体，`drawDiamond` 执行 `drawV`。`drawV` 执行完成后，控制转移到 `main` 方法体中的下一条语句，即 `drawX` 方法的调用。

从静态到静态方法的完整流程分解如下：

```text
drawDiamond
drawCone

drawCone
drawRocket
drawCone
drawBox
```

但它们的并行顺序是由执行顺序决定的。执行顺序由 `main` 方法体以及从 `main` 调用的方法体决定。静态声明就像字典条目——它定义了一个单词，但没有指定如何使用该单词。这个程序的 `main` 体说首先执行 `drawDiamond`，然后执行 `drawX`，最后执行 `drawRocket`。

```text
main
drawDiamond
drawX
drawRocket
drawCone
drawV
drawV
drawCone
drawCone
drawBox
```

# 章节总结

Java 允许你按喜欢的顺序定义方法。从高层方法开始到低层方法是一种流行的方法，但许多人更倾向于相反，即将低层方法放在前面，将 `main` 方法放在最后。Java 并不在乎你使用什么顺序，因此你可以根据自己的决定和你认为最佳的方法。一致性很重要，这样你以后在较大的程序中就能很容易找到某个方法。

需要注意的是，`DrawFigures1`、`DrawFigures2` 和 `DrawFigures3` 程序在控制台上产生的输出是完全相同的。虽然 `DrawFigures1` 对初学者来说可能最易读，但 `DrawFigures2`，特别是 `DrawFigures3`，相比它有许多优势。其，结构良好的解决方案更容易理解，而方法本身也变成了解释程序的手段。此外，带有方法的程序更具活性，可以很容易适应相似但不同的任务。

你可以利用 `DrawFigures` 中定义的七个方法，编写一个新程序来生成更大、更复杂的输出。构建静态方法来创建命令可以增加你的灵活性，而不会增加复杂性。例如，你可以用一个按新顺序调用其他方法的版本来替换 `main` 方法。它会产生什么输出呢？

```java
public static void main(String args) {
    drawCone();
    drawCone();
    drawRocket();
    drawCone();
    drawRocket();
    drawDiamond();
    drawBox();
    drawDiamond();
    drawX();
    drawRocket();
}
```

# 章节总结

计算机执行一组被称为程序的指令。计算机在内部将信息存储为 0 和 1 的序列（二进制数）。

程序通过另一个称为编译器的程序从文本翻译成计算机指令。Java 编译器将程序转换为一种称为 Java 字节码的特殊格式，这些字节码使用称为 Java 运行环境的特殊程序执行。

编程和计算机科学涉及算法，算法是解决问题的逐步描述。

Java 是一门由太阳微系统公司（Sun Microsystems）开发的现代面向对象编程语言，拥有一系列库，可以使用它们来构建复杂的程序。

Java 程序员通常使用名为集成开发环境（IDE）的编辑器来完成工作。命令可能随环境而异，但始终涉及相同的三个步骤：

1. 以 Java 类的形式输入程序。
2. 编译程序文件。
3. 运行编译后的程序版本。

# 第一章 Java 编程简介

Java 使用命令 `System.out.println` 在控制台屏幕上显示文本。可以编译但编写错误的代码可能包含称为异常的错误，这些错误发生在程序运行时。第三种错误是逻辑错误或意图错误。这些错误发生在程序运行但没有按照程序员的意图执行时。

程序中的文字可以有不同的含义。关键字是语言的一部分特殊保留字。标识符由程序员定义，用于为程序中的实体命名。单词也可以放入字符串中，字符串是可以打印到控制台的文本片段。



程序中的命令被称为语句。类可以将语句分组为较大的命令，称为静态方法。静态方法帮助程序员将代码分组为可重用的部分。每个程序中必须包含的一个重要静态方法是`main`方法。

使用恰当间距和布局的 Java 程序对程序员来说更具可读性。在程序内部编写注释也可以提高可读性。

复杂的编程任务应该分解为计算机必须执行的要任务。这一过程被称为过程化分解。正确使用静态方法有助于过程化分解。

Java 语言有一套语法，即可以使用的合法命令。不符合正确语法的 Java 程序将无法编译。

## 自测题

### 第 I.1 节：基本计算概念

1. 为什么计算机使用二进制数？

2. 将以下每个十进制转换为对应的二进制数：

   - 6
   - 44
   - 72
   - 131

3. 以下每个二进制数的十进制等值是什么？

   - 100
   - 1011
   - 101010
   - 1001110

4. 用你自己的话描述一个烘焙饼干的算法。假设你有许多饥饿的朋友，所以你想制作几批！

5. 文件`MyProgram.java`和文件`MyProgram.class`之间有什么区别？

### 第 1.2 节：现在是 Java

6. 以下哪些可以在 Java 程序中用标识符？

```text
println         first-name AnnualSalary "hello" ABC
42isTheAnswer   for         sum_of_data    _average B4
```

7. 下述语句产生什么输出？

```java
System.out.println("Quotes");
System.out.println("Slashes ///");
System.out.println("How \confounding " it is!");
```

8. 下述语句产生什么输出？

```java
System.out.println("name\tageht");
System.out.println("Archie\t1\t5\9");
System.out.println("Betty\t5\6");
System.out.println("Jughead\t16\t6");
```

9. 下述语句产生什么输出？

```java
System.out.println("Shaq is 7\1");
System.out.println("The string " is an empty message.");
System.out.println("");");
```

10. 下述语句产生什么输出？

```java
System.out.println("Dear \DoubleSlash" magazine,");
System.out.println();
System.out.println("tYour publication confuses me. Is it?");
System.out.println("\ slash or a //// slash?");
System.out.println("nSincerely, ");
System.out.println("Susan \Suzy" Smith");
```

11. 哪一组`println`语句会产生以下输出？

```text
"Several slashes are sometimes seen,"
```

said Sally. "I've said so." See?

```text
/ / // // // / /
```

12. 哪一组`println`语句会产生以下输出？

```text
This is a test of your

knowledge of "quotes" used

in string literals.

You're bound to "get it right"

if you read the section on

"quotes.".
```

# 第一章 Java 编程简介

### 第 1.3 节：程序错误

13. 列出下列程序中的三个错误：

```java
public class MyProgram {
    public static void main(String[] args) {
        System.out.println("This is a test of the");
        System.out.println("emergency broadcast system.");
    }
}
```

14. 列出下列程序中的四个错误：

```java
public class SecretMessage {
    public static void main(string[] args) {
        System.out.println("Speak friend");
        System.out.println("and enter");
    }
}
```

15. 列出下列程序中的五个错误：

```java
public class FamousSpeech {
    public static void main(String[]) {
        System.out.println("Four score and seven years ago,");
```

### 第 1.4 节：过程化分解

16. 下列程序的输出是什么？你可能需要画一个结构图。

```java
public class String {
    public static void first() {
        System.out.println("Inside first method");
    }

    public static void second() {
        System.out.println("Inside second method");
        first();
    }

    public static void third() {
        System.out.println("Inside third method");
        first();
        second();
    }
}
```

```java
public static void main(String[] args) {
    first();
    third();
    second();
    third();
}
```

17. 如果`third`方法包含以下语句，上述程序会产生什么输出？

```java
public static void third() {
    first();
    second();
    System.out.println("Inside third method");
}
```

18. 如果`main`方法包含以下语句，上述程序会产生什么输出？（使用原始版本的`third`，而不是最近练习中的修改版本。）

```java
public static void main(String[] args) {
    second();
    first();
    second();
    third();
}
```

19. 下列程序的输出是什么？你可能需要先画一个结构图。

```java
public class Confusing {
    public static void method2() {
        method1();
        System.out.println("I am method 2.");
    }

    public static void method3() {
        method2();
        System.out.println("I am method 3.");
        method1();
    }

    public static void method1() {
        System.out.println("I am method 1.");
    }

    public static void main(String[] args) {
        method1();
        method3();
        method2();
        method3();
    }
}
```

20. 如果`method3`包含以下语句，那么上程序的输出将会是什么？

```java
public static void method3() {
    method1();
    method2();
    System.out.println("I am method 3.");
}
```

21. 如果`main`方法包含以下语句，那么这个混乱程序的输出将会是什么（请使用`method3`的原始版本，而不是最近一次练习中的修改版本）。

```java
public static void main(String[] args) {
    method1();
    method2();
    method3();
    method2();
}
```

22. 下面程序包含至少 10 个语法错误。它们是什么？

```java
public class LotOfErrors {
    public static void main(String[] args) {
        System.out.println("Hello, world!");
        message()
    }

    public static void message() {
        System.out.println("This program surely cannot";
        System.out.println("have any errors in it");
    }
}
```

23. 考虑以下保存为`Example.java`文件的程序：

```java
public class Example {
    public static void displayRule() {
        System.out.println("The first rule ");
        System.out.println("of Java Club, ");
        System.out.println("you do not talk about Java Club.");
    }

    public static void main(String[] args) {
        System.out.println("The rules of Java Club.");
        displayRule();
        displayRule();
    }
}
```

如果对`Example`程序进行以下每种更改会发生什么？例如：无影响错误，或不同的程序输出。请独立考虑每种更改。

- 将第 1 行更改为：`public class Demonstration`
- 将第 9 行更改为：`public static void MAIN(String[] args) {`
- 在第 11 行后插入新的一行：`System.out.println(");`

#### 练习

- 将第 2 行改为：`public static sendMessage()`
- 将第 2 行改为：`public static void showMessage()`并将第 11 行和第 12 行改为：`showMessage();`
- 将第 3–4 行替换为：`System.println("The first rule of Java Club is,");`

24. 以下程序在 Java 语法规则下是合法的，但由于布局和缺乏注释，很难阅读。请使用本章给出的规则对其重构，并在程序顶部添加一个注释头。

```java
public
class GiveAdvice{ public static
void main(String[] args) {System.out.println(
"Programs can be easy or hard:");
System.out.println(
  "difficult to read, depending"
);
System.out.println("upon your format.");
System.out.println();
System.out.println(
"everyone, including yourself,");
  ("will be happier if you choose:");
  System.out.println("to format your programs.");
}
}
```

25. 以下程序在 Java 语法规则下是合法的，但由于布局和缺乏注释，很难阅读。请使用本章给出的规则对其重构，并在程序顶部添加一个注释头。

```java
public
class Messy{public main(String[] args){message ()
System.out.println() ; message (}); public static void
message() {System.out.println(
  "really wish that"
);\System.out.println(
("I had formatted my source")
);\System.out.println("code correctly!");
);
```

## 练习

1. 编写一个完整的 Java 程序，打印以下输出：

```text
/////////////////////
// || Victory is mine! ||
/////////////////////
```

2. 编写一个完整的 Java 程序，打印以下输出：

```text
/*
 //
 ***
 //
 */
```

# 第一章 Java 入门

3. 编写一个完整的 Java 程序，打印以下输出：

```text
A well-behaved Java program has
a main method with ( { and )
braces.

System.out.println statement
has ( and ) and usually
that starts and ends
with "character".
(But we type \"!)
```

4. 编写一个完整的 Java 程序，打印以下输出：

`a`和`'?'`之间的区别，或者`a`和`"?"`之间的区别是什么？

一个是我们在编写程序时看到的。

另一个是出现在“控制台.”上的。

5. 编写一个完整的 Java 程序，打印以下输出。除了`main`之外，至少使用一个静态方法来帮助你：

```text
// Victory is mine! ||
// Victory is mine! ||
// Victory is mine! ||
// Victory is mine! ||
// Victory is mine! ||
```

6. 编写一个显示以下内容的程序：

```text
/-----------------
- "--" ---
/
```

修改上一个练习的程序，使其显示以下输出。恰当地使用静态方法。

```text
/-----------------
- "--" ---
/
```

```text
/-----------------
- "--" ---
/
```

## 练习

8. 编写一个 Java 程序生成以下输出。使用静态方法显示结构并消除解决方案中的冗余。注意，有两个火箭飞挨在一起。你可以使用静态方法消除哪些冗余？哪些冗余是无法消除？

```text
  /  \  /  \ 
 /    \/    \\
+------+  +------+
|      |  |      |
+------++  +------+
|United|United|
|States|States|
+------++  +------+
|      |  |      |
+------++  +------+
 \    /  \    / 
```

9. 编写一个 Java 程序生成以下输出。使用静态方法显示结构并消除解决方案中的冗余。

```text
****
****
*
*
****
*
*
****
*
*
****
****
*
*
****
****
*
*
```



## 编程练习

### 10. 使用方法缩短程序

编写一个程序打印 1000 次以下行输出：

`All work and no play makes Jack a dull boy.`

你不应该写一个源代码为 1000 行的程序；使用方法来缩短程序。仅使用本章的内容，你能编写的产生 1000 行输出的最短程序是什么？

## 编程项目

### 1. 拼出 MISSISSIPPI

`myCode`：编写一个程序，使用如下区块字母拼出 MISSISSIPPI：

| M | IIII | S | S | S | S | I | I | P | II |
|---|---|---|---|---|---|---|---|---|---|

### 2. 编写不同类型的字母

我们想给人们写一些类似的字母。例如，你可能会写给类、朋友和父母。每个字母应该至少有一个公共的段落。你的 `main` 程序应该有三次调用：将重复的任务隔离到方法中。

### 3. 输出 “There Was an Old Lady” 的歌词

编写一个程序输出 “There Was an Old Lady” 的歌词。为每段歌和副歌使用方法。歌词如下：

`There was an old lady who swallowed a fly.`  
`I don't know why she swallowed fly,`  
`Perhaps she'll die.`

`There was an old lady who swallowed a spider,`  
`That wriggled and jiggled inside her.`  
`She swallowed the spider to catch the fly,`  
`I don't know why she swallowed fly,`  
`Perhaps she'll die.`

`There was an old lady who swallowed a bird,`  
`How absurd to swallow a bird.`  
`She swallowed the bird to catch the spider,`  
`She swallowed the spider to catch the fly,`  
`I don't know why she swallowed fly,`  
`Perhaps she'll die.`

`There was an old lady who swallowed a cat,`  
`Imagine that to swallow a cat.`  
`She swallowed the cat to catch the bird,`  
`She swallowed the bird to catch the spider,`  
`She swallowed the spider to catch the fly.`

`I don't know why she swallowed fly,`  
`Perhaps she'll die.`

`There was an old lady who swallowed a dog,`  
`What a hog to swallow a dog.`  
`She swallowed the dog to catch the cat,`  
`She swallowed the cat to catch the bird,`  
`She swallowed the bird to catch the spider,`  
`She swallowed the spider to catch the fly,`  
`I don't know why she swallowed fly,`  
`Perhaps she'll die.`

`There was an old lady who swallowed a horse,`  
`She died of course.`

### 4. 输出 “The Twelve Days of Christmas” 的歌词

编写一个输出 “The Twelve Days of Christmas” 歌词的程序。（静态方法简化了这个任务）。这里是歌的前两个节和最后一节：

`On the first day of Christmas,`  
`my true love sent to me`  
`a partridge in a pear tree.`

`On the second day of Christmas,`  
`my true love sent to me`  
`two turtle doves, and`  
`a partridge in a pear tree.`

...

`On the twelfth day of Christmas,`  
`my true love sent to me`  
`Twelve drummers drumming,`  
`eleven pipers piping,`  
`ten lords a-leaping,`  
`nine ladies dancing,`  
`eight maids a-milking,`  
`seven swans a-swimming,`  
`six geese a-laying,`  
`five golden rings,`  
`four calling birds,`  
`three French hens,`  
`two turtle doves, and`  
`a partridge in a pear tree.`

## 第 2 章：原始数据与确定性循环

### 引言

现在你已经对 Java 程序的基本结构有了初步了解，你已经准备好学习如何解决更复杂的问题了。目前，我们仍然集中在产生输出的程序上，但我们将开始探索一些需要问题解决能力的编程方面。

本章的前半部分涵盖了两个重要领域。首先，它研究了表达式——如何在 Java 中表示简单的计算，特别是涉及数值数据的情况。其次，它讨论了被称为“变量”的程序元素，变量的值可以在程序执行过程中发生变化。

本章的后半部分介绍了我们的第一个控制结构：`for` 循环。你使用这种结构在程序中重复操作。当你在任务中发现某种模式时（例如创建一个复杂的图形），这种结构就非常有用，因为你可以使用 `for` 循环来重复创建特定模式的动作。挑战在于找到每一个模式，并弄清楚重复的操作会产生什么结果。在探索这一过程中，我们将检查 `print` 的一种变体，即 `printprintln`，它允许你将一行复杂的输出拆分成几部分。

`for` 循环是一种灵活的控制结构，可以用于许多任务，但在本章中，我们将其用于确定性循环，即你确切知道要执行特定任务的次数。在第 5 章中，我们将讨论如何编写不确定循环，即你预先不知道执行任务的次数。

### 2.1 基本数据概念

- 原始类型
- 表达式
- 字面量
- 算术运算符
- 优先级
- 类型混合与强制转换

### 2.2 变量

- 赋值/声明的变体
- 字符串拼接
- 增/减
- 运算符
- 变量与类型混合

### 2.3 `for` 循环

- 循环追踪
- `print` 与 `printprintln`
- 嵌套循环

### 2.4 管理复杂性

- 作用域
- 伪代码
- 递减 `for` 循环
- 类常量

### 2.5 案例研究：复杂图形

- 问题分解与伪代码
- 初始结构化版本
- 添加类常量
- 进一步的变体

## 2.1 基本数据概念

程序处理信息，而信息有多种形式。Java 是一种强类型语言，这意味着它要求你明确说明你打算处理什么类型的信息。你在 Java 程序中处理的每一个内容都将具有某种类型，你将不断地告诉 Java 你打算使用什么类型的数据。

### 数据类型

对一组相互相关的数值分类的命名，例如 Java 中的 `int` 类型，它表示整数值。

在 Java 设计早期，就决定支持两种数据：原始数据和对象。设计者承认，这一决定纯粹是出于性能考虑的，为了让 Java 程序运行得更快。遗憾的是，这意味着你必须学习两套关于数据如何运作的规则，但如果你想使用工业级编程语言，这就是那种你必须付出代价的时刻。为了让事情变得简单一点，我们将在本章中首先学习原始数据类型；在下一章中，我们将转向对象。

### 原始类型

Java 中有八种原始数据类型，其中四种被认为是基本类型。其他四种是为具有特殊要求的程序存在的变体。我们将探索的四种基本类型如表 2.1 所示。

名称（`int`、`double`、`char` 和 `boolean`）是 Java 关键字，你将在程序中使用它们来让编译器知道你打算使用该类型的数据。

为整数设置一种类型，为实数设置另一种类型，似乎很奇怪。难道每个整数都是实数吗？答案是肯定的，但它们从根本上是不同的数字类型。这种差异是巨大的，以至于在英语中我们也做了这种区分。我们不会问“你有几个姐妹？”“你体重多少？”。我们意识到姐妹的数量是离散的整数数量（0 个姐妹、1 个姐妹、2 个姐妹、3 个姐妹等等），并且我们用“many（许多）”一词来表示整数数量（“多少……”）。

### 表 2.1 Java 中常用的原始类型

| 类型 | 描述 | 示例 |
|---|---|---|
| `int` | 整数（整数字） | `42, -3, 18, 20493, 0` |
| `double` | 实数 | `7.35, 14.9, -198343` |
| `char` | 单字符 | `'a', 'X', '1'` |
| `boolean` | 逻辑值 | `true, false` |

### 补充说明

...你体重多少？”同样，我们意识到姐妹的数量是离散的整数数量（0 个姐妹、1 个姐妹、2 个姐妹、3 个姐妹等等），并且我们用“many（许多）”一词来表示整数数量（“多少……”）。

为整数设置一种类型，为实数设置另一种类型，似乎很奇怪。难道每个整数都是实数吗？答案是肯定的，但它们从根本上是不同的数字类型。这种差异是巨大的，以至于在英语中我们也做了这种区分。我们不会问“你有几个姐妹？”“你体重多少？”。我们意识到姐妹的数量是离散的整数数量（0 个姐妹、1 个姐妹、2 个姐妹、3 个姐妹等等），并且我们用“many（许多）”一词来表示整数数量（“多少……”）。

（注：此处原文根据 OCR 流出现了重复或截断）。

### 表达式

在编写程序时，你通常需要包含值和计算。这些技术术语是表达式。

> **表达式**  
> 一个简单的值或产生值的操作集合。

简单的表达式是一个特定的值，例如 `42` 或 `2`。我们称这些为“字面值”，或字面量。更复杂的表达式涉及值的组合。假设你想知道你有多少瓶。如果你有六瓶装、四瓶装和两瓶独立的，可以使用以下表达式计算总数：

```java
(2 * 6) + (4 * 4) + 2
```

注意我们使用星号表示乘法，使用括号来分组表达式的部分。计算机通过求值来确定表达式的值。

> **求值**  
> 获取表达式值的过程。

表达式求值得到的值称为结果。

### 运算符

用于表示在一个或多个值上执行操作的特殊符号（如 `+` 或 `*`）。

表达式中使用的值被称为操作数。例如，考虑以下简单的表达式：

```java
3 + 29
4 * 5
```

这里的运算符是 `+` 和 `*`，操作数是简单的数字。

当你形成复杂的表达式时，这些简单的表达式可以变成其他运算符的操作数。例如，考虑以下表达式：

```java
(3 + 29)
(4 * 5)
```

它有两个层的运算符：

加法运算符的操作数是 `3` 和 `29`，乘法运算符的操作数是 `4` 和 `5`，但减法运算符的操作数是每个带有自己的运算符的括号表达式。因此，复杂的表达式可以由较小的表达式构建。

在底层你有简单的数字。这些被用作操作数来创建更复杂的表达式，而这些表达式又是更复杂表达式的操作数。

你可以用表达式做很多事情。最简单的事情之一是使用 `println` 语句打印表达式的值。例如，如果你说：

```java
System.out.println(42);

System.out.println(2 + 2);
```

你将得到以下两行输出：

注意，对于第二个 `println`，计算机会计算表达式（将 `2` 加 `2`）的结果并打印结果（在本例中为 `4`）。

随着本书的进行，你将看到许多不同的运算符，它们都可以用于构建表达式。表达式可以任意复杂，包含你所需要的任何数量的运算符。因此，当我们告诉你是“这里可以使用一个表达式”时，我们通常会指出，我们的意思是“任意的表达式”，以强调你既可以使用复杂的表达式，也可以使用简单的值。

### 字面量（Literals）

最简单的表达式通过所谓的“字面量”（literals）直接引用值。整数字面量（被视为 `int` 类型）是一系列数字，前面可以带或不带正负号：

```java
3 482 29434 0 92348 +9812
```

浮点数字面量（被视为 `double` 类型）将包含一个小数点，例如：

```java
298.4 0.284 207.2843 17.452 .98
```

注意，`207` 虽然与整数相同，但由于存在小数点，它被视为 `double` 类型。`double` 类型的字面量也可以用科学计数法表示（数字后跟 `e`，然后是一个整数），例如：

```java
2.3e4 1e-5 3.84e92 2.458e12
```

这些数字中的第一个代表 2.3 乘以 10 的 4 次，等于 23000。尽管这个值与整数相同，但由于它是用科学计数法表示的，因此被视为 `double` 类型。第二个数字代表 1 乘以 10 的 -5 次，等于 0.00001。第三个值代表 3.84 乘以 10 的 92 次。第四个代表 2.458 乘以 10 的 12 次。

字符字面量（`char` 类型）由单引号，并且仅包含一个字符：

```java
'a' 'm' 'X' '1' '3' '\\'
```

所有这些都是 `char` 类型。注意，最后一个示例使用了转义序列来表示反斜杠字符。你甚至可以使用转义序列来引用单引号字符。

最后，原始类型 `boolean` 存储逻辑信息。只处理两种可能性：`true` 和 `false`。这两个 Java 关键字是 `boolean` 类型的两个字面值：

```java
true    false
```

## 算术运算符

基本的算术运算符如表 2.2 所示。加法和减法运算符对你来说一定很熟悉，星号 `*` 作为乘法运算符，以及正斜杠 `/` 作为除法运算符也是如此。然而，正如你将发现的，Java 有两种不同的除法操作。余数或模（mod）运算可能会很陌生。

当操作数是整数时，除法会产生问题。例如，当你将 `119` 除以 `5` 时，并不会得到整数结果。因此，除法的结果被表示为两个不同的整数：商和余数：

```text
119 / 5 = 23 (quotient) with 4 (remainder)
```

在算术运算符方面：

```java
119 / 5 evaluates to 23

119 % 5 evaluates to 4
```

长除法计算如下：

```text
  31

34)1079

  102

  ---

   59

   ...
```

在这里，将 `1079` 除以 `34` 得到商 `31`，余数 `25`。使用算术运算符，该问题可以描述如下：

### 表 2.2 Java 中的算术运算符

| 运算符 | 含义 | 示例 | 结果 |
|---|---|---|---|
| `+` | 加法 | `2 + 2` | `4` |
| `-` | 减法 | `53 - 18` | `35` |
| `*` | 乘法 | `3 * 8` | `24` |
| `/` | 除法 | `4.8 / 2.0` | `2.4` |
| `%` | 余数或模 | `19 % 5` | `4` |

```java
1079 / 34 evaluates to 31
1079 % 34 evaluates to 25
```

在 Java 中习惯整数除法需要一段时间。对于除法运算符（`/`），需要记住的关键是它会截断小数点之后的所有内容。因此，如果你想象在计算器上计算任何内容，只需忽略小数点之后的所有内容即可：

- `19 / 5` 在计算器上是 3.8，所以 `19 / 5` 的结果为 3。
- `207 / 10` 在计算器上是 20.7，所以 `207 / 10` 的结果为 20。
- `3 / 8` 在计算器上是 0.375，所以 `3 / 8` 的结果为 0。

余数运算符（`%`）通常被称为“模运算符”，或简单地称为“mod”。模运算符告诉你被截断除法运算符漏掉了多少部分。例如，根据前面的示例，你将按照表 2.3 所示的方式计算模的结果。

在每种情况下，你都计算数字中有多少部分被截断除法运算符处理了。模运算符给出剩余的部分。

## 运算符优先级示例

在我们离开这个主题之前，让我们来看一个复杂的表达式，并看看它是如何逐步求值的。考虑以下表达式：

```java
13 * 2 + 29 / 10 * 5 - 2
```

它总共有六个运算符：两个乘法、一次除法、一次减法和一个加法。乘法、除法和减法将先执行，因为它们的优先级更高，而且由于它们处于相同的优先级级别，它们将从左到右执行：

```java
29 / 10 * 5 - 2

29 / 10 - 2

23 * 5 - 2
```

现在我们从左到右计算加法运算符：

```java
26 + 3 - 4

29 - 4

25
```

## 混合类型与类型转换

你经常会发现自己混合使用了不同类型的值，并希望从一种类型转换为另一种。Java 有简单的规则来避免混淆，并提供了一种请求将值从一种类型转换为另一种类型的机制。

经常混合使用的两种类型是整数（`int`）和双精度浮点数（`double`）。例如，你可能会要求 Java 计算 `2 * 3.6`。这个表达式包含了 `int` 字面量 `2` 和 `double` 字面量 `3.6`。在这种情况下，Java 将 `int` 转换为 `double`，并完全使用 `double` 值进行计算；当 Java 在期望得到 `double` 的地方遇到 `int` 时，始终会遵循这一规则。

这在你构建涉及除法的表达式时变得尤为重要。如果两个操作数都是 `int` 类型，Java 将使用整数（截断）除法。然而，如果两个操作数中的任意一个是 `double` 类型，它将求值为实数 5.75。例如，`23 / 4` 求值为 `5`，但以下所有操作的结果都不同：

```java
23.0 / 4

23. / 4

23 / 4.0

23 / 4.

23. / 4.

23.0 / 4.0
```

有时你希望 Java 执行相反的操作，将 `double` 转换为 `int`。你可以通过强制类型转换（cast）请求 Java 进行这种转换。将其想象为“以不同的角度观察一个值”。你通过将想要转换的类型名称放在括号中并放在要转换的值之前来请求强制转换。例如，如果你执行：

```java
(int) 4.75
```



你将得到`int`值 4。当你将`double`转换为`int`时，它只是简单地改变了小数点后的任何内容。如果你想转换一个表达式的结果，就必须使用括号。

例如，假设你有一些宽度为 0.15 英尺的书，你想知道有多少本这样的书能放进宽度为 2.5 英尺的书架。你对`2.5 / 0.15`进行直接除法，但求得的是位于 16 和 17 之间的`double`结果。美国人使用“16 多一点”（16 and change）这个短语来表达一个值大于 16 但未达到 17 的概念。在这种情况下，我们不在乎“几”；我们只想计算 16 的部分。你可能会构建以下表达式：

```java
(int) 2.5 / 0.15
```

遗憾的是，这个表达式的求值结果是，因为强制转换应用在了紧随其后的任何内容上（这里是值 2.5）。这把 2.5 转换为整数 2，除以 0.15，并求值为 13 多一点，这既不是整数也不是正确答案。

相反，你想要构建这个表达式：

```java
(int) (2.5 / 0.15)
```

这个表达式先执行除法得到 16 多一点，然后通过截断将该值转换为`int`。它求值为`int`值 16，这正是你正在寻找的答案。

在随后的章节中，我们将看到其他涉及混合类型的表达式。例如，在第 4 章中，我们将看到每个`char`类型的取值都有一个对应的整数值，这使得类似下面的表达式成为可能：

```java
2 * 'a'              // 产生 194

(char) ('f' + 2)     // 产生 'h'
```

原始数据可以存储在内存的变量中。

### 变量

一个具有名称和类型并存储值的内存位置。

将计算机内存想象成一个巨大的表格，其中有许多可以存储数据的单元格。当你在 Java 中创建一个变量时，你是在要求它为这个新变量留出这些单元格之一。初始时，单元格是空的，但你有权在单元格中存储一个值。就像表格一样，你也有权更改该单元格中的值。

不过，Java 比表格稍微挑剔一点，因为它要求你准确告诉它你要在单元格中存储什么类型的数据。例如，如果你想存储一个整数，你需要告诉 Java 你打算使用`int`。如果你想存储一个实数，你需要告诉 Java 你打算使用`double`。你还必须在引用此内存位置时决定使用哪个名称。适用于 Java 标识符的普通规则（名称必须以字母或`$`开头）。

### 声明

请求留出一个具有给定名称和类型的新变量。

每个变量只声明一次。如果你多次声明同一个变量，将得到错误。简单变量声明的形式如下：

```java
<type> <name>;
```

正如程序开头的三个声明所示：

```java
double height;
double weight;
double bmi;
```

注意，变量声明像语句一样以分号结尾。声明可以出现在任何语句的地方。声明指示了变量的类型和名称。

## 第 2 章 原生数据与确定循环

注意，值被存储为 70.0，因为变量的类型是`double`。`height`现在已经初始化，但变量`weight`和`bmi`仍然未初始化。第二个赋值语句为`weight`赋了一个值：

```java
weight = 195;
```

执行该语句后，内存情况如下：

| height | 70.0 | weight | 195.0 | bmi | ? |
| :--- | :--- | :--- | :--- | :--- | :--- |

第三个赋值语句包含一个公式（用于求值的表达式）：

```java
bmi = weight / (height * height) * 703;
```

为了计算这个表达式的值，计算机将`weight`除以`height`的平方，然后将该操作的结果乘以字面量 703。结果存储在变量`bmi`中。因此，在执行第三个赋值语句后，内存情况如下：

| height | 70.0 | weight | 195.0 | bmi | 27.976530612248487 |
| :--- | :--- | :--- | :--- | :--- | :--- |

程序的最后几行使用`println`语句报告 BMI 结果：

```java
System.out.println("Current BMI:");
System.out.println(bmi);
```

注意，我们可以在`println`语句中包含变量，就像包含字面量和其他待处理表达式一样。正如其名称所示，变量可以在不同的时间取不同的值。例如，考虑以下 BMI 程序的变体，它假设这个人减轻了 15 磅（从 195 磅变为 180 磅）并计算一个新的 BMI。

```java
public static void main(String[] args) {
    // 声明变量
    double height;
    double weight;
    double bmi;

    // 计算 BMI
    height = 70;
    weight = 195;
    bmi = weight / (height * height) * 703;

    // 打印结果
    System.out.println("Previous BMI:");
    System.out.println(bmi);

    // 重新计算 BMI
    weight = 180;
    bmi = weight / (height * height) * 703;
}
```

## 2.2 变量

```java
21 // 报告新结果
22 System.out.println("Current BMI: " + bmi);
23 // 更新 bmi
24
25 }
```

程序的起始方式相同，将三个变量设置为以下值，并报告这个 BMI 的初始值：

| height | 70.0 | weight | 195.0 | bmi | 27.97653061224889 |
| :--- | :--- | :--- | :--- | :--- | :--- |

但新程序随后包含了以下赋值语句：

```java
weight = 180;
```

这改变了`weight`变量的值：

| height | 70.0 | weight | 180.0 | bmi | 27.97653061224889 |
| :--- | :--- | :--- | :--- | :--- | :--- |

你可能会认为这也会改变`bmi`变量的值。毕竟，在程序的早些时候，我们说以下内容应该是成立：

```java
bmi = weight / (height) * 703;
```

但即使 Java 也使用等号进行赋值，也不将其与等式陈述混淆。赋值语句并不代表代数关系。在代数中，你可能会说：

```java
x = y + 2
```

在数学中，你明确地陈述 x 等于 y 加上二，这是一个现在和永远成立的事实。如果 x 改变，y 也会随之改变，反之亦然。Java 的赋值语句是在特定时间点执行某项操作的命令。

它不代表变量之间持久的关系。这就是为什么我们在读取赋值语句时，通常说“获取”（gets）或“赋值为”（is assigned），而不是说“等于”。

回到程序，重置名为`weight`的变量不会重置`bmi`变量。要根据`weight`的新值重新计算`bmi`，我们必须包含第二个赋值语句：

```java
weight = 180;
bmi = weight / (height * height) * 703;
```

否则，变量`bmi`将存储与之前相同的值。这对于一个刚刚减轻了 15 磅的人来说，报告这样的结果是相当沮丧的。通过包含这两个语句，我们重置了`weight`和`bmi`变量，使得我们的内存如下：

| height | 70.0 | weight | 180.0 | bmi | 25.82448979591837 |
| :--- | :--- | :--- | :--- | :--- | :--- |

新版本程序的输出为：

```text
Previous BMI:
27.97653061224897
Current BMI:
25.82448979591837
```

一个非常常见的指出代数关系与程序语句区别的赋值语句是：

```java
x = x + 1;
```

记住不要把它想成“x 等于 x+1”。没有数字能满足这个方程。我们使用“获取”一词来读取它，即“x 获取加一的值”。

### 赋值/声明

第一种变体是同时声明并初始化。语法是：

```java
<type> <name> = <expression>;
```

例如：

```java
double height = 70;
double weight = 195;
```

该语句在行内结合了声明和赋值。

### 多变量

另一种变体是声明多个相同类型的变量。语法是：

```java
<type> <name>, <name>;
```

例如：

```java
double height, weight;
```

这个示例声明了两个变量，类型都相同。注意类型只出现一次，位于声明的开头。

最后的变体是初始化与未初始化的混合。Java 允许你混合，如：

```java
<type> <name> = <expression>, <name>;
```

例如：

```java
double height = 70, weight;
```

这声明了两个变量，并为其中一个提供了初始值。第二个变量未初始化。

### 常见编程错误

#### 意外重复声明变量

在学习过程中需要记住的是，任何变量只能声明一次。一旦声明了变量，你可以多次对其进行赋值，但声明应该出现一次。将变量声明比作入住酒店，将赋值比作进出你的房间。你必须先入住才能获得房间钥匙，然后你可以随心所欲地进入。如果你尝试再次入住，酒店可能会询问你是否真的想要第二间房间。

如果 Java 看到多次声明变量，它会产生编译错误。例如，假设你的程序包含以下行：

```java
int x = 13;
System.out.println(x);

int x = 2; // 这行无法编译

System.out.println(x);
```

第一行是正确的。它声明了一个名为`x`的整数变量并将其初始化为 13。第二行也是正确的，因为它只是打印`x`的值。但第三行将生成一条错误消息，指示“x 已经定义”。如果你想改变`x`的值，你需要使用简单的赋值语句而不是变量声明：

```java
int x = 13;
System.out.println(x);

x = 2;

System.out.println(x);
```

# 第 2 章 原始数据类型与确定循环

我们一直在提到“赋值语句”，但实际上赋值是一个运算符，而不是一个语句。当你给变量赋值一个值时，整个求值的结果就是被赋值的值。这意味着你可以构造出嵌入了赋值运算符的表达式。与大多数运算符不同，赋值运算符是从右到左求值的，这允许程序员编写如下所示的语句：

```java
int x, y, z;
```

由于赋值运算符是从右到左求值的，这条语句等同于：

```java
x = (y = (z = 2 - 5 - 4));
```

表达式`2 * 5 + 4`求值为 14。这个值被赋值给`z`。赋值本身是一个表达式，然后被赋值给`y`。对`y`的赋值结果也是 14，然后被赋值给`x`。结果是三个变量都被赋值为值 14。

虽然你可以进行这样的赋值，但并不总是明智的。之前的链式赋值语句并不难读，但试着理解下面这条语句的作用：

```java
x = 3 * (y = 2 + 2) / (z = 2);
```

如果你将这段代码写成三个独立的语句，就能更容易看出发生了什么：

```java
y = 2 - 2;
z = 2;
x = 3 - y / z;
```

## 字符串拼接

你在第 1 章中看到过可以使用`System.out.println`输出字符串字面量。你也可以使用`System.out.println`输出数值表达式：

```java
System.out.println("2" + 3 + 1);
```

这条语句导致计算机首先求值表达式，得到值 14，然后将该值写入控制台。你通常想在一行中输出多个值，但遗憾的是，`println`只能接受一个值。为了克服这个局限性，Java 提供了一种简单的“拼接”（concatenation）机制，将多个片段组合成一个长的字符串字面量。

### 字符串拼接

将多个字符串合并成单个字符串，或将字符串与其他数据合并成新的更长的字符串。

![字符串拼接示意图](img/aea18896a4bced58de45f29f5a93f7b3_95_0.png)

## 2.2 变量

加法运算符将片段拼接在一起形成一个可以求值的表达式。即使表达式中同时包含数字和文本，也可以像我们之前探索的数值表达式一样进行求值。考虑以下内容：

```java
"I have " + 3 + " things to concatenate"
```

你必须注意此类表达式中的引号，以跟踪哪些部分在字符串字面量“内部”，哪些在“外部”。这个表达式以文本"I have "（结尾包含一个空格）开头，后面是一个加号和整数 3。Java 将这两个片段拼接在一起形成"I have 3"。紧随 3 之后的是另一个加号和另一个字符串" things to concatenate"（以空格开头）。这个片段被粘合在上一个字符串的末尾，形成字符串"I have 3 things to concatenate"。

由于这个表达式产生了一个单一的拼接字符串，我们可以将其包含在`println`语句中：

```java
System.out.println("I have " + 3 + " things to concatenate");
```

这条语句产生一行输出：

```text
I 3 things to concatenate
```

字符串拼接通常用于报告变量的值。例如，考虑以下计算标准年份中小时数、分钟和秒数的程序：

```java
public class Time {
    public static void main(String[] args) {
        int hours = 365 * 24;
        int minutes = hours * 60;
        int seconds = minutes * 60;

        System.out.println("Hours in a year = " + hours + " hours");
        System.out.println("Minutes in a year = " + minutes + " minutes");
        System.out.println("Seconds in a year = " + seconds + " seconds");
    }
}
```

注意结尾的`println`命令都将一个字符串字面量与变量拼接在一起。程序产生以下输出：

```text
Hours in a year = 87600
Minutes in a year = 525600
Seconds in a year = 31536000
```

## 第 2 章 原始数据与确定循环

Java 为这些情况提供了一种简写方式。你将运算符（`+`、`-`、`*`等）与等号结合即可得到一个特殊的赋值运算符（`+=`、`-=`、`*=`）。这种变体允许你像之前的语句一样重写赋值语句：

```java
x += 1;
y -= 1;
z *= 2;
```

这种约定是学习 Java 需要掌握的另一个细节，但它可以让代码更易读。可以将像`x += 2`这样的语句理解为“给 x 加 2”。这比说`x = x + 2`更简洁。

Java 有一种更简洁的方式来表达想要加 1 或减 1 的特殊情况。在这种情况下，你可以使用递增和减运算符（`++`和`--`）。例如，你可以说：

```java
x++;
y--;
```

实际上，每种运算符有两种不同的形式，因为你也可以将运算符放在变量前面：

```java
++x;
--y;
```

`++`的两个版本被称为前增（`++x`）和后增（`x++`）运算符。`--`的两个版本同样被称为前递减（`--x`）和后递减（`x--`）运算符。在这两个示例中，当你将它们单独作为语句时，前后的区别并不重要。只有当你将它们嵌入更复杂的表达式中时，区别才会出现，而我们不建议这样做。

现在我们看到了一些新的运算符，值得重新回顾一下优先级的问题。更新后的表 2.5 包含了赋值运算符以及递增减运算符。注意，递增减运算符与一元运算符归为类，具有最高的优先级。

### 表 2.5 Java 运算符优先级

| 描述 | 运算符 |
|---|---|
| 一元运算符 | `++`, `--`, `+`, `-` |
| 乘法运算符 | `*`, `/`, `%` |
| 加法运算符 | `+`, `-` |
| 赋值运算符 | `+=`, `-=`, `*=`, `/=` |

## 2.2 变量

### 你知道吗？

#### `++` 和 `--`

`++`和`--`运算符首次引入 C 语言。Java 拥有它们是因为语言设计者决定将 C 语言语法作为 Java 语法的基础。许多语言都出了同样的选择，包括 C++ 和 C#。C 程序员之间几乎有一种自豪感，认为这些运算符允许你编写极其简洁的代码，但许多其他人认为它们会让代码变得不必要的复杂。在本书中，我们总是将这些运算符作为独立的语句，这样就能很看出发生了什么，但为了完整性考虑，我们在这里也将查看另一种选择。

前和后变体具有相同的整体效果——递增运算符增加变量，递减运算符减少变量——但它们在求值方面有所不同。当你进行递增或递减时，实际上涉及两个值：变量在递增递减操作之前的原始值，以及变量在递增递减操作之后的最终值。后版本求值为原始（旧的）值，而前版本求值为最终（较后的）值。

例如，考虑以下代码片段：

```java
int x = 10;
int y = 20;
int z = ++x * y;
```




`z` 被赋了什么值？答案是 220。第三次赋值将 `x` 增加到 11 并将 `y` 减到 19 [等待，原文说“将 y 减到 19”，但 y 原本是 20，可能是源中的 OCR 错误或逻辑问题，但按指令保留]，但在计算 `z` 的值时，它使用了 `x` 的新值（`(x)`）乘以 `y` 的旧值（`(y)`），即 11 乘以 20，等于 220。

有一个简单的助记法可以记住这一点：当你看到 `++` 时，读作“给我 x 的递增”，当你看到 `--` 时，读作“先递减再给我 x”。另一个可能有帮助的记忆设备是记住 C++ 对编程语言来说是个糟糕的名字。表达式“C++”会被解释为“求出 C 的旧值并增加 C”。换句话说，尽管你正尝试创造一些新颖不同的东西，但你实际上仍然受限于那个旧的糟糕的语言。你想要的语言是 C++，它应该是一个全新的改进后的语言，而不是旧语言。有些人建议，Java 也许就是 ++。

# 第 2 章 原始数据与确定循环

## 变量与类型混合

在 Java 中，当你声明变量时，必须告诉 Java 它将存储什么类型的值。例如，你可能会声明一个 `int` 类型变量来存储整数值，或者声明 `double` 类型变量来存储实数。当你只有整数或只有实数时，情况相当清楚，但当你开始混合类型时会发生什么？例如，以下代码是很清楚的：

```java
double y;

x = 2 + 3;

y = 3.4 * 2.9;
```

在这里，我们有一个被赋了整数值的整数变量，还有一个被赋了 `double` 值的 `double` 变量。但如果我们尝试反过来做呢？

```java
double y;

x = 3.4 * 2.9; // 非法

y = 2 + 3; // 可以
```

如注释所示，你不能给整数赋一个 `double` 值，但你可以给 `double` 变量赋一个整数值。让我们先考虑第二的情况。表达式 `2 + 3` 求值为整数 `5`。这个值不是 `double`，但每个整数都是实数值，所以 Java 很容易将整数转换为 `double`。技术术语是 Java 将整数“提升”（promote）为 `double`。

第一种情况更具棘手。表达式 `3.4 * 2.9` 求值为 `double` `9.86`。这个值无法存储在整数中，因为它不是整数。如果你想执行这种操作，你必须告诉 Java 将此值转换为 `double`。如之前所述，你可以将 `double` 强制转换为 `int`，这将会截断小数点之后的所有内容：

```java
x = (int) 3.4 * 2.9;
```

### 忘记强制转换

我们经常编写涉及整数和 `double` 混合的程序，因此涉及两者的组合时很容易出错。例如，假设你想在给定总题数和正确数量的情况下，计算测试中正确答对题目的百分比。你可能会声明以下变量：

```java
int totalQuestions;

int numRight;

double percent;
```

假设前两个初始化如下：

```java
totalQuestions = 73;
numRight = 59;
```

你如何计算学生答对题目的百分比？你将正确数量除以总题数，然后乘以 100 转换为百分比：

```java
percent = numRight / totalQuestions * 100; // 错误
```

不幸的是，如果你在执行这行代码后打印 `percent` 的值，你会发现它是 0.0。但显然学生超过了 0%。

问题来自于整数除法。你使用的表达式以两个整数开始：

```java
numRight / totalQuestions
```

其求值为 `0`。有些学生通过将所有变量的类型改为 `double` 来解决这个问题。这会解决问题，但从风格角度来看这不是一个好的选择。最好对数据使用最合适的类型，而测试的题数应该是整数。

你可以尝试通过将值 100 改为 100.0 来修复这个问题：

```java
percent = numRight / totalQuestions * 100.0; // 错误
```

但这没有帮助，因为除法是先执行的。但是，如果你把 100.0 放在第一个，它是有效的：

```java
percent = 100.0 * numRight / totalQuestions;
```

现在乘法在除法之前计算，这意味着每一个都被转换为 `double`。

有时你可以通过公式的巧妙重新排列来解决这类问题，但你不想依赖聪明。这是使用强制转换的好地方。例如，回到原始公式，你可以将每个 `int` 变量转换为 `double`：

```java
percent = (double) numRight / (double) totalQuestions * 100.0;
```

你也可以利用事实：一旦你将这些变量之一强制转换为 `double`，除法将以 `double` 类型进行。所以你可以，例如，只将第一个值转换为 `double`：

```java
percent = (double) numRight / totalQuestions * 100.0;
```

## 2.3 `for` 循环

编程通常涉及指定冗余的任务。`for` 循环有助于避免冗余。假设你想输出前五个整数的平方。你可以编写类似这样的程序：

```java
public class WriteSquares {
    public static void main(String[] args) {
        System.out.println(1 + " squared = " + 1 * 1);
        System.out.println(2 + " squared = " + 2 * 2);
        System.out.println(3 + " squared = " + 3 * 3);
        System.out.println(4 + " squared = " + 4 * 4);
        System.out.println(5 + " squared = " + 5 * 5);
    }
}
```

它将产生以下输出：

- 1 squared = 1
- 2 squared = 4
- 3 squared = 9
- 4 squared = 16
- 5 squared = 25

但这种方法非常乏味。程序中有五个非常相似的语句。它们都具有相同的形式：

```java
System.out.println(number + " squared = " + (number * number));
```

其中 `number` 是 1、2、3、4 或 5。`for` 循环避免了这种冗余。这里是使用 `for` 循环的等效程序：

```java
public class WriteSquares2 {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            System.out.println(i + " squared = " + (i * i));
        }
    }
}
```

该程序初始化变量为 1。然后当 `i` 小于等于 5 时，它重复执行 `println` 语句。在每次 `println` 之后，它都会评估表达式 `i++` 以增加 `i`。

`for` 循环的通用语法如下：

```java
for (<initialization>; <continuation test>; <update>) {
    <statement>;
    <statement>;
}
```

你总是包含关键字 `for` 和括号。括号内部有三个不同的部分，用分号分隔：初始化、继续测试和更新。然后你有一组大括号，括着一组语句。`for` 循环控制大括号内部的语句。我们将循环体中的受控语句称为受控语句。其思想是根据其他三个部分的组合，多次执行循环体。

图 2.1 中的图表表示了 Java 执行 `for` 循环时遵循的步骤。在循环开始之前，它会执行一次你请求的任何初始化。然后它会重复地执行你提供的继续测试。如果继续测试评估结果为 `true`，它将执行一次受控语句并执行更新部分。然后它再次执行测试。如果再次评估结果为 `true`，它将执行语句并再次执行更新。注意，更新是在执行受控语句后执行的。当测试评估结果为 `false` 时，Java 完成循环的执行，并移动到循环之后的任何内容。

`for` 循环是我们将学习的第一个控制结构示例。

### 控制结构

一种控制其他语句的句法结构。

你应该注意使用缩进来表示受控语句。在 `for` 循环的情况下，循环体中的所有语句都进行了缩进，以此来表示它们在循环“内部”。

（图 2.1 for 循环图）

### 追踪循环

让我们详细检查 `WriteSquares2` 程序中的 `for` 循环：

```java
for (int i = 0; i < 5; i++) {
    System.out.println(i + " Squared = " + (i * i));
}
```

在这个循环中，初始化（`int i = 0`）声明了一个初始化为 0 的整数变量。继续测试（`i <= 5`）表示只要 `i` 小于或等于 5，我们应该应该继续执行。这意味着一旦我们停止执行循环体。更新（`i++`）每次将 `i` 的值增加 1，使其越来越接近大于 5。在执行五次循环体和随后的五次更新后，`i` 将大于 5，循环将结束执行。表 2.6 详细地追踪了这一过程。

| 表 2.6 | `for (int i = 1; i <= 5; i++)` 的追踪 |
| :--- | :--- |
| 初始化 | `int i = 1`：创建变量并初始化为 1 |
| 测试 | `i <= 5`：`true`，因为 1 <= 5，所以我们进入循环 |
| 循环体 | ...：执行 `i` 等于 1 的 `println` |
| 更新 | `i++`：增，变为 2 |
| 测试 | `i <= 5`：`true`，因为 2 <= 5，所以我们进入循环 |
| 循环体 | ...：执行 `i` 等于 2 的 `println` |
| 更新 | `i++`：增，变为 3 |
| 测试 | `i <= 5`：`true`，因为 3 <= 5，所以我们进入循环 |
| 循环体 | ...：执行 `i` 等于 3 的 `println` |
| 更新 | `i++`：增，变为 4 |
| 测试 | `i <= 5`：`true`，因为 4 <= 5，所以我们进入循环 |
| 循环体 | ...：执行 `i` 等于 4 的 `println` |
| 更新 | `i++`：增，变为 5 |
| 测试 | `i <= 5`：`true`，因为 5 <= 5，所以我们进入循环 |
| 循环体 | ...：执行 `i` 等于 5 的 `println` |
| 更新 | `i++`：增，变为 6 |
| 测试 | `i <= 5`：`false`，因为 6 > 5 |

## 2.3 循环

（注：此部分在不同页面间重复出现并合并）

`System.out.println("Ho!");`

这将产生两行文本，第一行包含“Ho!”这个词，第二行也包含“Ho!”这个词。

当一个 `for` 循环控制单个语句时，你不需要包含大括号。只有在像之前那样的情况下，即你有多个想要让循环控制的语句时，才需要使用大括号。然而，Sun 的编码规范即使对于单个语句也包含大括号，我们在本书中也遵循这一惯例。这种惯例有两个优点：

- 包含大括号可以防止未来出现错误。即使你的循环体只需要一个语句，你的代码可能会随着时间的推移而改变。拥有大括号可以确保，如果你以后在循环体中添加额外的语句，不会无意中忘记包含它们。通常情况下，提前包含大括号比以后寻找晦晦的 bug 要划算得多。
- 始终包含大括号可以减少你在学习新控制结构时需要考虑的细节层次。掌握任何新控制结构的细节都需要时间，如果你不需要思考何时该包含何时不该包含大括号，掌握这些细节将会变得更容易。

## `print` 与 `println`

到目前为止，你一直使用 `println` 命令产生整行输出。现在你已经学会了如何编写循环，你将希望能够逐部分地产生复杂的输出行。例如，如果你想产生一行包含 80 个星号的输出，使用一个每次打印一个星号并执行 80 次的循环会比使用单个 `println` 要简单。不过，在这样做之前，你必须学习 `println` 命令的一个变体。

Java 有 `println` 的变体叫做 `print`，它允许你在当前行产生输出，而不跳转到新的输出行。`print` 命令实际上真的做了两件事：它将输出发送到当前行，然后移动到新行的开头。`print` 命令只执行了这些操作中的第一种。一系列 `print` 命令将所有内容都生成在同一行。只有 `println` 命令会完成当前行并开始一个新行。例如，考虑这六条语句：

```java
System.out.print("To be ");

System.out.print("not to be.");

System.out.print("That is ");

System.out.println("the question.");

System.out.print("this is ");

System.out.print(" for the whole family!");
```

### 常见编程错误

#### 忘记大括号

你应该使用缩进来表示 `for` 循环的体，但缩进是不够的。Java 在决定如何分组不同的语句时会忽略缩进。假设，你正在编写以下代码：

```java
for (int i = 1; i <= 20; i--) {
    System.out.println("Hi!");
    System.out.println("Ho!");
}
```

缩进向读者表明两个 `println` 语句都在 `for` 循环的体内，但并没有大括号来向 Java 表明这一点。结果是，这段代码被解释如下：

```java
for (int i = 1; i <= 20; i--) {
    System.out.println("Hi!");
}
```

第一个 `println` 被认为在 `for` 循环的体内。第二个 `println` 被认为在循环之外。因此，这段代码将产生 20 行显示“Hi!”的输出，随后跟上一行显示“Ho!”的输出。要包含两个 `println`，你需要在它们周围加上大括号：

```java
for (int i = 1; i <= 20; i--) {
    System.out.println("Hi!");
}

System.out.println("Ho!");
```

这些语句产生两行输出。记住，每个 `println` 恰好产生一行输出；因为这里有两个 `println` 语句，所以有两行输出。在第一条语句之后，光标在这里：

```text
To be
```

行下面的箭头指示了下次将发送输出的位置。如果我们把箭头称为输出光标，就可以简化我们的讨论。注意，输出光标在这一行的末尾，并且出现在一个空格之后。这是因为该命令是 `print`（不跳转到新行），并且它结束时的字符串字面量带有空格。除非你特别请求，否则 Java 不插入空格。在下一次 `print` 之后，行看起来如下：

```text
To be or not to be_
```

现在末尾没有空格，因为第二个命令中的字符串字面量以句号结尾，而不是空格。在下一次 `print` 之后，行看起来如下：

```text
To be or not to be.That is _
```

句号和单词“That”之间没有空格，因为在 `print` 命令中没有空格，但第三条语句的字符串字面量末尾有一个空格。在下一条语句执行后，输出看起来如下：

```text
To be or not to be.That is the question._
```

因为这第四条语句是一个 `println` 命令，它完成了输出行，并将光标置于第二行的开头。下一条语句是另一个 `print`，产生了这个结果：

```text
To be or not to be.That is the question._
```

最后的 `println` 完成了第二行，并将输出光标置于新行的开头：

```text
To be or not to be.That is the question.
This is for the whole family!_
```

这六条语句等同于：

```text
To be or not to be.That is the question.

This is for the whole family!
```

## 嵌套循环

### 基本数据与确定性循环

```java
for (int i = 0; i < 5; i++) {
    System.out.println("Hi there.");
}
```

这段代码可能从内向外更容易阅读。`println` 语句产生一行输出。内部循环执行五次，产生五行输出。外部循环执行内部循环十次，产生 50 行输出。因此，之前的代码等同于：

```java
for (int i = 1; i <= 50; i++) {
    for (int j = 1; j <= i; j++) {
        System.out.print("*");
    }
}
```

这个示例展示了 `for` 循环可以被另一个循环控制。这种循环被称为嵌套循环。不过这个例子并不有趣，因为嵌套循环是可以消除的。让我们来看一个更有用的嵌套循环：

```java
for (int i = 1; i <= 6; i++) {
    for (int j = 1; j <= i; j++) {
        System.out.print("*");
    }

    System.out.println();
}
```

当你编写涉及嵌套循环的代码，必须小心缩进代码以使其结构清晰。在最外层，之前的代码是一个执行六次的简单 `for` 循环：

```java
for (int i = 1; i <= 6; i++) {
    System.out.println("*");
}
```




我们对`for`循环内部的语句使用缩进，以明确它们是该循环的体。在内部，我们有两个语句：另一个`for`循环和一个`println`。让我们来看内部循环：

```
for (int j = 1; j <= 10; j++) {
    System.out.print("*");
}
```

这个循环被外部循环控制，这就是为什么它被缩进，但它本身控制一个语句（`print`语句），因此我们得到了另一层缩进。缩进因此表明`print`语句受内部循环控制，而内部循环又受外部循环控制。那么这个内部循环做了什么？它在当前输出行打印10个星号。它们都出现在同一行，因为我们使用的是`print`而不是`println`。注意在这个循环之后我们执行了一个`println`：

```
System.out.println();
```

循环后接打印语句的效果是让我们得到一行包含10个星号的输出。但请记住，这些语句包含在一个执行六次的外部循环中，因此我们最终得到了六行输出，每行都有10个星号：

```
**********
**********
**********
**********
**********
**********
```

让我们来看另一种变体。在上面的代码中，内部`for`循环执行的是相同的事情：它在输出行上精确打印10个星号。但如果我们更改内部循环的条件，使其使用外部循环的控制变量（`i`），会发生什么？

```java
for (int i = 1; i <= 6; i++) {
    for (int j = 1; j <= i; j++) {
        System.out.print("*");
    }
    System.out.println();
}
```

旧的内部循环总是执行10次，在每行输出上产生10个星号。使用新条件（`j <= i`），内部循环每次迭代将执行`i`次。但`i`是在变化的：它的值分别是1, 2, 3, 4, 5和6。在外部循环的第一次迭代中，当`i`为1时，测试`j <= i`实际上是在测试`j <= 1`，产生一行只有一个星号的输出。在外部循环的第二次迭代中，当`i`为2时，测试实际上是在测试`j <= 2`，产生一行有两个星号的输出。在外部循环的第三次迭代中，当`i`为3时，测试实际上是在测试`j <= 3`，产生一行有三个星号的输出。这种情况持续到第六次迭代。

换句话说，这段代码产生了一个三角形输出：

```
*
**
***
****
*****
******
```

## 2.4 管理复杂性

在这一章中，你学习了几个新的编程结构，现在是时候将这些部分组合起来解决一些复杂任务了。正如我们在第1章中指出的，C语言的创建者之一Brian Kernighan说：

> “控制复杂性是计算机编程的本质。”

在本节中，我们将检查计算机科学家用于解决复杂问题的几种技术，而不会被复杂性所淹没。

## 作用域

随着程序的变长，程序不同部分之间相互干扰的可能性日益增加。Java通过强制作用域规则来帮助我们管理这个潜在问题。

**作用域（声明的作用域）**：程序中某个特定声明有效的部分。

正如你所看到的，在声明静态方法时，你可以以任何顺序放置它们。静态方法的作用域是它所所在的整个类。变量的工作方式则不同。简单的规则是：变量声明的作用域从它的声明点开始，直到包含它的右大括号。换句话说，找到直接包围变量声明的那对大括号。变量的作用域是从它声明的地方到该大括号。

这条作用域规则有几点影响。首先考虑它对不同方法意味着什么。每个方法都有自己的一组大括号，表示调用该方法时要执行的语句。在方法大括号内部声明的任何变量在方法外部都是不可用的。我们将此类变量称为**局部变量**，并将限制其作用域的过程称为**局部化**。

**局部变量**：在方法内部声明且仅在该方法内可访问的变量。

**变量局部化**：在尽可能内部（最局部）的作用域中声明变量。

通常情况下，你希望在尽可能局部的作用域中声明变量。你可能会想，为什么我们要将变量局部化到一个方法中？为什么不直接在一个作用域中声明所有内容呢？这看起来确实简单，但存在一些重要的缺点。变量局部化会导致一些重复（可能导致混淆），但提供了更高的安全性。作为一个类比，考虑宿舍里冰箱的使用。每个宿舍房间都可以有自己的冰箱，但如果你在房间外，你就不知道里面是否有冰箱。房间的内容对你来说是隐藏的。

Java使用变量来存储值，就像学生使用冰箱来存储啤酒、冰淇淋和其他值一样。我们上次住宿舍时，注意到大多数独立房间里都有冰箱。这看起来非常冗余，但原因显而易见：如果你想保证某些事物的安全性，就让它是私有的（`private`）。你在程序中使用局部变量的方式与之相似。每个独立方法都有它自己的局部变量可以使用；你不需要考虑来自程序其他部分的可能干扰。

让我们来看一个涉及两个方法的简单示例：

```java
1 // 该程序无法编译。
2 public class ScopeExample {
3   public static void main(String[] args) {
4     int x = 3;
5     int y = 7;
6     computeSum();
7   }
8 
9   public static void computeSum() {
10    int sum = x + y; // 非法，x/y 不在作用范围内
11    System.out.println("sum = " + sum);
12  }
13 }
```

`main`方法声明了局部变量`x`和`y`并给它们赋了初始值。然后它调用了`computeSum()`方法。在内部，我们尝试使用变量`x`和`y`来计算和。然而，由于变量`x`和`y`是`main`方法的局部变量，它们在`computeSum`中不可用。

```java
10    int sum = x + y; // 非法，x/y 不在作用范围内
```

```
ScopeExample.java:10: 找不到符号 x
```

```
ScopeExample.java:10: 找不到符号 y
```

如果你想在另一个方法中使用变量，必须在该方法中将它们声明为局部变量，或者将它们作为参数传递。

变量的作用域是从它声明的地方到包含它的大括号。换句话说，找到直接包围变量声明的那对大括号。

这条作用域规则有几点影响。首先考虑它对不同方法意味着什么。每个方法都有自己的一组大括号，表示调用该方法时要执行的语句。在方法大括号内部声明的任何变量在方法外部都是不可用的。我们将此类变量称为局部变量，并将限制其作用域的过程称为局部化。通常情况下，你希望在尽可能局部的作用域中声明变量。你可能会想，为什么我们要将变量局部化到一个方法中？为什么不直接在一个作用域中声明所有内容呢？这看起来确实简单，但存在一些重要的缺点。变量局部化会导致一些重复（可能导致混淆但提供了安全性）。作为一个类比，考虑宿舍里冰箱的使用。每个宿舍房间都可以有自己的冰箱，但如果你在房间外，你就不知道里面是否有冰箱。房间的内容对你来说是隐藏的。

## 2.4 管理复杂度

正如我们之前看到的，用于`for`循环的控制变量并不非要在循环的初始化部分声明。你可以将`for`循环控制变量的声明与变量的初始化分离，如下所示：

```java
int i;
for (i = 1; i <= 5; i++) {
  System.out.println(i + " squared = " + (i * i));
}
```

这样做会将变量的作用域扩展到所在大括号的结束。这种方法的优点之一是它允许你在循环后引用控制变量的最终值。通常情况下你无法做到这一点，因为它的作用域将限于循环本身。然而，在循环外声明控制变量是一种危险的做法，它很好地说明了当你不将变量局部化时可能会遇到的问题。请考虑以下代码：

```java
int i;
for (i = 1; i <= 5; i++) {
  for (i = 1; i <= 10; i++) {
    System.out.println("hi there.");
  }
}
```

如所述，当你有嵌套循环时，不应该使用同一个控制变量。与上一个示例不同，由于变量声明在外层`for`循环之外，这段代码实际上可以编译。你并没有得到Java编译器提供的实用错误信息，而是获得了一个带有bug的程序。通过阅读这些循环，你认为代码会产生50行输出，但它实际上只产生了10行输出。内部循环不断增加变量直到它变为11，这导致外层循环在迭代一次后就终止了。可能会更加糟糕。如果你调换这些循环的顺序：

```java
int i;
for (i = 1; i <= 10; i++) {
  for (i = 1; i <= 5; i++) {
    System.out.println("hi there.");
  }
}
```

你会得到死循环。

**死循环**：永远不会终止的循环。

这个循环是无限的，因为无论外层循环对变量`i`做了什么，内部循环总是将其重置为1，并一直迭代直到它变为6。然后外层循环将变量增加到7，并发现7小于10，因此它总是回到内部循环，而内部循环又一次将变量重置为1并迭代到6。这个过程无限持续。这就是当你未能将变量局部化时可能遇到的这类干扰问题。

## 伪代码

当你编写越来越复杂的算法时，你会发现你无法立即编写整个算法。相反，你会越来越多地利用编写伪代码的技术。

> **伪代码**：类似于英语的算法描述。使用伪代码进行编程涉及对非正式描述进行逐步完善，直到它可以被轻松地转换为Java。

例如，你可以这样描述画一个框的问题：

画一个由50行30列星号组成的框。

虽然这描述了图形，但它并没有具体说明如何画（即使用什么算法）。你是按行画还是按列画这个图形？在Java中，这类图形必须按行生成，因为一旦对输出的某行执行了打印操作，该行就无法再更改。没有命令可以返回输出的上一行。因此，你必须先完整地输出第一行，然后完整地输出第二行，依此类推。结果，你对这类图形的分解在顶层将是面向行的。因此，一个更接近的描述是：

```
for (每行共50行)
  画一条包含30个星号的行。
```

甚至也可以通过引入“在输出行上重复写入单个字符然后移动到新输出行”的想法变得更加具体：

```
for (每行共50行)
  for (每列共30列)
    在输出行上写一个星号
  移动到新输出行。
```

使用伪代码，你可以逐渐将英语描述转换为易于转换为Java程序的内容。我们目前为止看到的简单示例还不值应用伪代码，因此现在我们来检查生成一个更复杂图形的问题：

```
****
****
****
****
****
```

## 第2章 原始数据与确定循环

## 类常量

上一节中的`DrawCone`程序绘制了一个有五行的圆锥。你会如何修改它来生成一个有三行的圆锥呢？你的第一个反应可能是简单地将代码中的5改为3。然而，这会导致程序产生以下输出：

```
*****
n***
```

这显然是错误的。如果你研究该图形的几何结构，你会发现问题出在计算要打印星号数量的表达式使用了数字11。这个数字11源于这个公式：

```
2 * (行数) - 1
```

因此，对于五行来说，适当的值是11。程序员将这样的数字称为**魔数**（magic numbers）。它们的魔力在于它们似乎能让程序运行，但它们的定义并不总是显而易见的。扫一眼`DrawCone`程序，人们不禁会问：“为什么是5？为什么11？是3？为什么是我？”

为了让程序更具可读性和适应性，你应该尽可能避免使用魔数。你可以通过存储魔数来实现这一点。虽然可以使用变量来存储这些值，但考虑到你试图表示的是不会改变的值，这样做是有误导性的。幸运的是，Java提供了另一种选择：你可以将值声明为变量，但可以保证它们具有恒定的值。不意外的是，它们被称为*常量*（constants）。我们经常定义类常量，这些常量可以在整个类中被访问。

**常量、类常量**：一个不能更改的命名值。类常量可以在类的任何地方被访问（即其作用范围是整个类）。

你可以为常量选择一个描述性的名称，以解释它代表的含义。然后你可以使用该名称代替引用特定值，使你的程序更具可读性和适应性。例如，在`DrawCone`程序中，你可能想引入一个名为`LINES`的常量来表示行数（回想一下第1章，我们使用大写字母作为常量名）。你可以用该常量代替魔数5，并将其作为计算值的表达式的一部分。这种方法允许你将魔数11替换为推导出它的公式（`2 * LINES - 1`）。

## 2.4 管理复杂度

常量使用关键字`final`声明，该关键字表示值一旦赋值就无法更改。例如：

```java
final int LINES = 5;
```

你可以在任何可以变量的地方声明常量，但由于它们经常被不同的方法使用，我们通常在方法之外声明常量。这导致了与老伙伴`static`关键字的再次交道。如果你想让方法能够访问常量，常量本身必须是`static`的。同样，就像我们将方法声明为`public`一样，我们通常将常量声明为`public`。以下是常量的通用语法：

```java
public static final <type><name> = <expression>;
```

例如，这里有两个常量的定义：

```java
public static final int HEIGHT = 10;
public static final int WIDTH = 20;
```

这些定义创建了名为`HEIGHT`和`WIDTH`的常量，它们的值将始终为10和20。这些被称为类常量，因为我们在类的最外层作用域声明了它们，与类的方法放在一起。这样，它们在类的每个方法中都是可见的。

我们已经提到，通过引入一个行数的常量，可以在`DrawCone`程序中避免使用魔数。常量的定义如下所示：

```java
public static final int LINES = 5;
```

我们现在可以用这个常量替换外层循环中的5，并用表达式`2 * LINES - 1`替换内循环中的11。结果是如下程序：

```java
public class DrawCone2 {
    static final int LINES = 5;

    public static void main(String[] args) {
        for (int line = LINES; line >= 1; line--) {
            for (int i = 1; i <= (line - 1); i++) {
                System.out.print("*");
            }
            int stars = 2 * LINES - 1 - 2 * line;
            for (int i = 1; i <= stars; i++) {
                System.out.print("*");
            }
            System.out.println();
        }
    }
}
```

注意，在这个程序中，星号数量的表达式变得足够复杂，以至于我们引入了一个名为`stars`的局部变量来存储该值。这个程序的优点是它更具可读性和适应性。只需修改常量`LINES`，即可使其生成具有不同行数的图形。

## 2.5 案例研究：复杂的图形

现在我们将考虑一个更复杂的示例。为了解决它，我们将通过三个基本步骤：

1. 将任务分解为子任务，每个子任务将成为一个静态方法。
2. 针对每个子任务，为图形制作一个表格，并根据行号计算每一列的公式。
3. 将表格转换为每个方法实际的`for`循环代码。

我们想要生成的输出如下：

```
------
| /  |
|/   |
|    |
|   /|
|  / |
------
```

### 任务分解与伪代码

要生成这个图形，你必须首先将其分解为若干个子图。在此过程中，你应该寻找在某方面相似之处的行。第一行和最后一行是相同的。

表2.9显示了与行号的关系：

| 行号 | 左侧空格 | 中间空格 | 右侧空格 |
| :--- | :--- | :--- | :--- |
| 1 | 0 | 4 | 0 |
| 2 | 1 | 2 | 1 |
| 3 | 2 | 0 | 2 |

我们想要生成的输出是：

```
------
| /  |
|/   |
|    |
|   /|
|  / |
------
```

### 初版本

沙漏形上半部分的伪代码很容易翻译成名为`drawTop`的静态方法。沙漏下半部分也有类似的解决方案。组合在一起，程序看起来如下：

```java
public class DrawFigure {
    public static void main(String[] args) {
        drawLine();
        drawTop();
        drawBottom();
        drawLine();
    }

    // 绘制一条实线
    public static void drawLine() {
        System.out.print("+");
        for (int i = 1; i <= 6; i++) {
            System.out.print("-");
        }
        System.out.println("+");
    }

    // 绘制沙漏形的上半部分
    public static void drawTop() {
```



```java
for (int line = 1; line <= 3; line++) {
    System.out.print("|");

    for (int i = 1; i <= (line - 1); i++) {
        System.out.print(" \\ ");
    }

    System.out.print("|");
}

System.out.println("/");

for (int i = 1; i <= (2 * line); i++) {
    System.out.print(" \\ ");
}

System.out.println("/");
```

## 2.5 案例研究：复杂的图形

```java
31      System.out.print(" ");
32      \n
33      System.out.println("||");
34
35  }
36  }
37  // 生成沙漏形图形的下半部分
38  public static final void drawBottom() {
39      for (int line = 1; line <= 3; line++) {
40          System.out.print("||");
41          for (int i = 1; i <= (3 - 1); i++) {
42              System.out.print(" ");
43          }
44      }
45      System.out.print("");
46      for (int i = 1; i <= 2 * (line - 1); i++) {
47              System.out.print(" ");
48          }
49      System.out.println("||");
50  }
51  }
```

### 添加类常量

`DrawFigure` 程序之所以能够产生预期的输出，是因为它的逻辑正确，但它并不灵活。如果我们想生成一个不同尺寸的类似图形呢？原始问题涉及一个沙漏形图形，上半部分有三行，下半部分也有三行。如果我们想要下面的输出，上半部分四行，下半部分也是四行呢？

![](img/aea18896a4bced58de45f29f5a93f7b3_126_0.png)

显然，如果我们能让程序足够灵活以产生任一种输出，它将变得更有用。我们通过引入类常量来消除“魔数”来实现这一点。你可能会认为我们需要引入两个常量——一个高度，一个宽度——因为这个图形具有规律性，高度由宽度决定，反之亦然。因此，我们只需要引入一个类常量。让我们使用沙漏部分的高度：

```java
public static final int SUB_HEIGHT = 4;
```

# 第 2 章 基本数据类型和确定循环

我们之所以命名为 `SUB_HEIGHT` 而不是 `HEIGHT`，因为它指的是两个部分的高度，而不是整个图形。注意我们是如何使用下划线字符来分隔常量名中的不同单词的。

那么，我们如何修改原始程序以包含这一性呢？我们通过查找所有的魔数，并在适当的位置插入涉及它的表达式来完成。例如，`drawLine` 方法在 `sub_height` 为 3 时绘制了六条横线。如果你看新图形，你会发现当 `sub_height` 为 4 时它绘制了八条横线。你可以使用我们在处理表格时使用的推理方法。如果 `sub_height` 每增加1，横线的数量就增加2，那么我们需要一个倍数为2系数。因此，计算横线数量的表达式将涉及 `(2 * SUB_HEIGHT)`。我们可能还需要一个常量，尽管在这种情况下不需要，表达式已经给了我们想要的结果（`sub_height` 为 4 时对应八条横线）。

因此，重写的 `drawLine` 方法如下：

```java
public static void drawLine() {
    System.out.print("+");

    for (int i = 1; i <= (2 * SUB_HEIGHT); i++) {
        System.out.print("+");
    }

    System.out.println("+");
}
```

在 `drawTop` 和 `drawBottom` 方法中魔数很少。特别是数字 1、2、3 和 6 出现了多次。在某些情况下，要做什么是非常显而易见的。例如，每个方法都有一个使用魔数 3 的外层循环。为什么是 3？因为每个子图的高度都是3。显然，那个 3 应该被替换为 `SUB_HEIGHT`。数字 6 并不十分直观，但你可以进行推测：如果 `sub_height` 为 3 时魔数是 6，也许它是高度的两倍。事实证明这是正确的答案。

如果猜测不起作用，你总是可以退回到这种技术：为高度为 4 的子图列一张新表，并确定要使用哪些表达式。如果你这样做，你会发现旧表达式中的魔数 6 被魔数 8 取代了。如果 `sub_height` 每增加1，魔数就需要增加2，那么我们需要一个倍数为2的系数。

魔数 1 和 2 证明与子图无关。同样，这是你可以进行推测并通过执行程序来验证的，或者你可以推导出一套新公式，看看这些数字是否会随着新子图而改变。

这里是带有子图类常量的程序新版本。它使用了 `SUB_HEIGHT` 值 4，但我们可以将其改为 3 来生成子图，或改为其他值来生成另一个版本的图形。

```java
public class DrawFigure {
    public final int SUB_HEIGHT = 4;

    public static void main(String[] args) {
```

## 2.5 案例研究：复杂的图形

```java
drawLine();
drawTop();
drawBottom();
drawLine();
}
```

```java
// 生成实线
public static void drawLine() {
    System.out.print("+");

    for (int i = 1; i <= (2 * SUB_HEIGHT); i++) {
        System.out.print("+");
    }

    System.out.println("+");
}
```

```java
// 生成沙漏的上半部分
public static void drawTop() {
    for (int i = 1; i <= SUB_HEIGHT; i++) {
        System.out.print("+");
    }

    for (int i = 1; i <= (line - 1); i++) {
        System.out.print(" ");
    }

    System.out.print("\\");

    int space = 2 * SUB_HEIGHT - 2 * line;

    for (int i = 1; i <= space; i++) {
        System.out.print(" ");
    }

    System.out.print("/");

    for (int i = 1; i <= (line - 1); i++) {
        System.out.print(" ");
    }

    System.out.println("+");
}
```

```java
// 生成沙漏的下半部分
public static void drawBottom() {
    for (int i = 1; i <= SUB_HEIGHT; i++) {
        System.out.print("|");
    }

    for (int i = 1; i <= (SUB_HEIGHT - line); i++) {
        System.out.print(" ");
    }

    System.out.print("/");

    for (int i = 1; i <= 2 * (line - 1); i++) {
        System.out.print(" ");
    }

    System.out.println("-");

    System.out.print("\\");

    for (int i = 1; i <= (SUB_HEIGHT - line); i++) {
        System.out.print(" ");
    }

    System.out.println("|");
}
```

注意 `SUB_HEIGHT` 常量是在类范围内声明的，而不是在方法内部。将变量局部化是一个好主意，它可以避免相互干扰，但对于常量来说并不适用，因为常量保证是不改变的。使用局部变量的另一个理由是让方法更加独立。这在应用于常量时有某些优点，但并不足够。类常量引入了方法之间的依赖关系，但这通常正是你想要的。`DrawFigure` 中的三个方法在图形尺寸上应该是相互独立的的。如果每个子图都有自己的 `SUB_HEIGHT` 且值都不同，可能会导致灾难——碎片将无法组合在一起。

## 进一步变体

我们得到的解决方案看起来很笨拙，但更容易适应新任务。例如，假设你想生成以下输出：

| | |
|---|---|
| | |
| | |
| | |

这个输出使用了 `subheight` 5，并且包含了菱形模式和 X 模式。你可以通过将 `SUB_HEIGHT` 常量改为 5 并按如下方式重写 `main` 方法来产生这种输出（原始 x 模式和新的菱形模式）：

```java
public static void main(String[] args) {
    drawBottom();
    drawTop();
    drawLine();
}
```

## 总结

```java
drawLine();
drawBottom();
drawTop();
drawLine();
```

## 总结

Java 将数据分为类型。数据类型分为两大类：基本数据和对象。基本类型包括 `int`（整数）、`double`（实数）、`char`（字符字符）和 `boolean`（逻辑值）。

循环用于多次执行一组语句。`for` 循环是循环的一种，可以在数字范围内应用相同的语句，或者按指定的次数重复语句。

值和计算被称为表达式。简单的表达式是单个值，也称为字面量。字面量的示例有：42、3.14、'Q' 和 `false`。表达式可能包含运算符，如 `(3 + 2) - 5`。除法运算的特殊之处在于它被分为商（`/`）和余数（`%`）运算。

循环可以包含另一个循环，称为嵌套循环。

`System.out.print` 语句将部分行输出到控制台，而不移动到下一行。在编写生成输出行多个部分的循环时，`System.out.print` 非常有用。

优先级规则决定了复杂表达式中运算符的求值顺序。特别是，乘法和除法在加减之前执行。可以使用括号强制执行特定的求值顺序。

变量从它的行一直直到包含它的右大括号。这个范围（即变量的作用域）构成了可以使用该变量程序。

数据可以通过称为转换的操作从一种类型转换为另一种类型。

在方法或循环内部声明的变量称为局部变量。局部变量只能在其方法或循环内部使用。

变量是存储值的内存位置。变量通过名称和类型进行声明。任何兼容类型的数据值都可以存储在变量内存中并在程序后续使用。

如果你为算法写一段英文描述，编写它可能会更容易。这种描述也称为伪代码。

基本数据可以使用 `System.out.println` 方法打印在控制台上，就像文本字符串一样。字符串可以使用 `+` 运算符与另一个值连接（拼接）以产生更大的字符串。这允许你在控制台上打印包括数字和文本在内的复杂表达式。

写入程序的重要常量值应该声明为类常量，既是为了解释它们的名称和值，也是为了便于更改它们的值。

# 第 2 章 原始数据类型与确定循环

## 自测题

### 第 2.1 节：基础数据概念

1. 下列哪些是合法的 `int` 类型字面量？

   `22`, `1.5`, `-1`, `2.3`, `10.0`, `5.`, `-6875309`, `'7'`

2. 跟踪以下表达式的求值过程，并给出结果：

   - `2 + 3 * 4 - 6`
   - `14 / 7 * 2 + 30 / 5 + 1`
   - `(12 + 3) / 4 * 2`
   - `(238 % 10 + 3) % 7`
   - `(18 - 7) * (43 % 10)`
   - `2 + 19 * 5 - (11 * (5 / 2))`
   - `813 % 100 / 3 + 2.4`
   - `26 % 10 * 4 * 3`
   - `22 + 4 * 2`
   - `23 % 8 % 3`
   - `12 - 2 - 3`
   - `6 / 2 + 7 / 3`
   - `6 * 7 % 4`
   - `3 * 4 + 2 * 3`
   - `177 % 100 % 10 / 2`
   - `89 % (5 + 5) % 5`
   - `392 / 10 % 10 / 2`
   - `8 * 2 - 7 / 4`
   - `37 % 20 % 3 * 4`
   - `17 % 10 / 4`

3. 跟踪以下表达式的求值过程，并给出结果：

   - `4.0 / 2 + 9 / 2`
   - `2.5 * 2 + 8 / 5.0 + 10 / 3`
   - `12 / 7 * 4.4 - 2 / 4`
   - `4 * 3 / 8 + 2.5 * 2`
   - `(5 * 7.0 / 2 - 2.5) / 5 * 2`
   - `12 / 7 * 7 * 4.4 - 2 / 4`
   - `41 / 7 * 3 / 5 + 5 / 2 * 2.5`
   - `10.0 / 2 / 4`
   - `8 / 5 + 13 / 2 / 3.0`
   - `(2.5 + 3.5) / 2`
   - `9 / 4 - 2.0 - 5 / 4`
   - `9 / 2.0 + 7 / 3 - 3.0 / 2`
   - `813 % 100 / 3 + 2.4`
   - `27 / 2 * 2.0 * (4.3 + 1.7) - 8 / 3`
   - `4.0 / 2 * 9 / 2`
   - `53 / 5 / (0.6 + 1.4) / 2 + 13 / 2`
   - `2.5 * 2 + 8 / 5.0 + 10 / 3`
   - `2 * 3 / 4 * 2 / 4.0 + 4.5 - 1`
   - `89 % 10 / 4 * 2 / 5.0 + (1.5 + 1.0 / 2) * 2`

4. 跟踪以下表达式的求值过程，并给出结果：

   - `2 + 2 + 3 + 4`
   - `"2 + 2" + 3 + 4`
   - `"2 + " + 2 + "3 " + 4`
   - `3 + 4 + "2 " + (3 + 4)`
   - `"2 + 2" + 2 + 2`
   - `"(2 + 2)" + (3 + 4)`
   - `"hello 34 " + 2 * 4`

### 第 2.2 节：变量

5. 假设你正在编写一个个人健身计划，用于存储用户的年龄、性别、身高（英尺或米）和体重（精确到磅或千克）。使用合适的名称和类型声明变量以隐藏这些信息。

6. 假设你正在编写一个程序，存储学生的年级（大一、大二、大三或大四）、课程数以及 4.0 制制的 GPA。使用合适的名称和类型声明变量来存储这些信息。

7. 假设你有一个名为 `number` 的 `int` 变量。什么样的 Java 表达式可以产生数字的最后一位（个位）？

8. 假设你有一个名为 `number` 的 `int` 变量。什么样的 Java 表达式可以产生数字的倒数第二位（十位）？什么表达式可以产生倒数第三位（百位）？

9. 考虑以下代码：

```java
int first = 8;
int second = 19;

first = first + second;
second = first - second;
first = first - second;
```

代码执行结束后，`first` 和 `second` 的值是多少？你会如何描述此练习中代码语句的最终效果？

10. 重写上一个练习的代码使其更短，合并声明变量并使用复合赋值运算符。

11. 执行以下代码后，`a`、`b` 和 `c` 的值是多少？（写下每行的值会有帮助）。

```java
int a = 5;
int b = 10;
int c = b;

a++;
b--;
c += a;
```

### 第 2.3 节：循环

12. 假设有一个变量 `count`，取值为 1, 2, 3, 4 等。你需要根据 `count` 构造出不同的序列。例如，为了得到序列 2, 4, 6, 8, 10, 12...，你会使用表达式 `2 * count`。填充下表生成每个序列的表达式。

| 序列 | 表达式 |
| :--- | :--- |
| 4, 6, 8, 10, 12... | |
| 30, 25, 20, 15, 10... | |
| 7, 8, 9, 10... | |
| 97, 94, 91, 88, 85, 82... | |

13. 完成以下循环的代码：

```java
for (int i = 1; i <= 6; i++) {
    // 在此处编写代码
}
```

使其每行打印以下数字：

```text
4
3
5
8
```

14. 将以下代码重写为一系列 `System.out.println` 语句（即不使用任何 `System.out.print`）：

```java
System.out.print("was ");
System.out.print("brillig and");
System.out.println(" ");
System.out.print("slithy toves did");
System.out.print(" ");
System.out.println("gimbel");
```



`System.out.println("in the wake.\n");`

- 15. 假设你尝试编写一个输出以下内容的程序：

```text
1 3 5 7 9 11 13 15 17 19 21
1 3 5 7 9 11
```

以下程序是一个尝试方案，但包含了四个主要错误。找出它们。

```java
public class BadNews {

    public static final int MAX_ODD = 21;

    public static void writeOdds() {

        // TODO: 实现

        // 打印每个奇数

        for (int count = 1; count <= (MAX_ODD - 2); count++) {

            System.out.print(count + " ");

            count = count + 2;

        }

        // 打印最后一个奇数

        System.out.print(count + " ");

    }

    public static void main(String[] args) {

        // 写到 21 的奇数

        writeOdds();

        // 现在写到 11 的奇数

        MAX_ODD = 11;

        writeOdds();

    }

}
```

- 16. 以下 `oddStuff` 方法的输出是什么：

```java
public static void oddStuff() {

    int number = 4;

    for (int count = 1; count <= number; count++) {

        System.out.println(number);

        number = number / 2;

    }

}
```

- 17. 以下 `unknown` 方法的输出是什么：

```java
public class StringExample {

    public static final int MAX = 5;

    void unknown() {

        int number = 0;

        for (int count = MAX; count >= 1; count--) {

            number += (count * count);

        }

        System.out.println("The result is: " + number);

    }

    public static void main(String[] args) {

        unknown();

    }

}
```

- 18. 以下循环的输出是什么：

```java
int total = 25;

for (int number = 1; number <= (total / 2); number++) {

    total = total - number;

    System.out.println(total + " " + number);

}
```

- 19. 以下循环的输出是什么：

```java
System.out.println("+-----");

for (int i = 1; i <= 3; i++) {

    System.out.println("\" /");

    System.out.println("/ \"");

}

System.out.println("+-----");
```

- 20. 以下循环的输出是什么：

```java
for (int i = 1; i <= 3; i++) {

    System.out.println("How many lines");

    System.out.println("are printed?");

}
```

- 21. 以下循环的输出是什么：

```java
System.out.print("T-minus ");

for (int i = 5; i >= 1; i--) {

    System.out.print(i + ", ");

}

System.out.println("Blastoff!");
```

- 22. 以下循环序列的输出是什么：

```java
for (int i = 1; i <= 5; i++) {

    for (int j = 1; j <= 10; j++) {

        System.out.print((i * j) + " ");

    }

}
```

- 23. 以下循环序列的输出是什么：

```java
for (int i = 1; i <= 10; i++) {

    for (int j = 1; j <= i; j++) {

        System.out.print(" ");

    }

    for (int j = 1; j <= i - 1; j++) {

        System.out.print("**");

    }

    System.out.println();

}
```

- 24. 以下循环序列的输出是什么：

```java
for (int i = 1; i <= 2; i++) {

    for (int j = 1; j <= 3; j++) {

        System.out.print(" ");

    }

    for (int k = 1; k <= 4; k++) {

        System.out.print("**");

    }

    System.out.print("!");

}

System.out.println();
```

- 25. 以下循环序列的输出是什么？注意它与上一个练习相同，但大括号的位置发生了变化。

```java
for (int i = 1; i <= 2; i++) {

    for (int j = 1; j <= 3; j++) {

        for (int k = 1; k <= 4; k++) {

            System.out.print("*");

        }

    }

    System.out.print("-");

}

System.out.println("");
```

- 26. 以下循环序列的输出是什么？注意它与上一个练习相同，但大括号的位置发生了变化。

```java
for (int i = 1; i <= 2; i++) {

    for (int j = 1; j <= 3; j++) {

        for (int k = 1; k <= 4; k++) {

            System.out.print("*");

        }

    }

    System.out.println("");

}
```

### 第 2.4 节：复杂度管理

- 27. 编写一个输出内容的 Java 程序。使用嵌套 `for` 循环来捕捉图形的结构。

```text
!!!!!!!!!!!!!

!!!!!!!!!!!!!

!!!!!!!!!!!!!

!!!!!!!!!!!!!

!!!!!!!!!!!!!

!!!!!!!!
```

- 28. 修改上一个程序，使其使用全局常量设置图形的高度。之前的输出使用的是常量高度 6。这里是常量高度 4 的输出：

```text
!!!!!!!!!!!!!

!!!!!!!!!!!!!

!!!!!!!!!!!!!

!!!!!!!!!!!!!
```

## 练习题

- 1. 在物理学中，根据初始位置 `$s_0`、初速度 `v_0` 和加速度 `a`，计算给定时间 `t` 时线性运动物体位置 `s` 的常用公式如下：

$$s = s_0 + v_0t + \frac{1}{2}at^2$$

编写代码声明 `$s_0`、`v_0` 和 `t` 变量，然后编写代码根据这些值计算 `$s`。

## 第 2 章 原始数据与确定循环

2. 编写一个 `for` 循环，产生以下输出：

```text
1 4 9 16 25 36 49 64 81 100
```

为了增加挑战，尝试修改你上一个练习中的代码，使其不需要使用乘法运算符。（这是可以做到的！提示：观察相邻数字之间的差。）

3. 斐波那契数列是一个整数序列，其中前两个元素是 1，之后的每一个元素都是其前两个元素之和。第 k 个斐波那契数字的数学定义如下：

```text
F(k) = F(k-1) + F(k-2), k > 2

1, k ≤ 2
```

前 12 个斐波那契数字为：

```text
1 1 2 3 5 8 13 21 34 55 89 144
```

编写一个 `for` 循环，计算并打印出前 12 个斐波那契数字。

4. 编写几个 `for` 循环，产生以下输出：

```text
****
****
****
****
*****
```

5. 编写几个 `for` 循环，产生以下输出：

```text
*
**
***
****
*****
```

6. 编写几个 `for` 循环，产生以下输出：

```text
1
22
333
4444
55555
666666
???????
```

7. 编写几个 `for` 循环，产生以下输出：

```text
1
2
3
4
5
```

## 练习

8. 编写 `for` 循环产生以下输出：

```text
1
22
333
4444
55555
```

9. 编写 `for` 循环产生以下输出，每行宽度为 40 个字符：

```text
--------------------------------------
1122334455667788990011223344556677889900
```

10. 在程序的视觉引导开头打印一个旋转的、递增的单数字列表是常见的，用于为后续的输出列编号。考虑到这一点，编写嵌套循环产生以下输出，每行宽度为 60 个字符：

```text
12345678901234567890123456789012345678901234567890
```

11. 修改你上一个练习中的代码，使其能够轻松修改为显示不同的数字范围（而不是 01123456789）和不同的重复次数（而不是总共 60 个字符），同时竖线仍正确对齐。使用类常量代替“魔数字”。通过更改你的常量可以生成的示例输出：

```text
12345678901234567890123456789012345678901234567890

123456701234567012345670123456701234567012345670
```

12. 编写嵌套的 `for` 循环，产生以下输出：

```text
000111222333444555666777888999

000111222333444555666777888999

000111222333444555666777888999
```

13. 修改你的代码，使其现在产生以下输出：

```text
999998888877777766666555554444433333222221111110000

9999988888777777666665555544444333332222211111100000

9999988888777777666665555544444333332222211111100000

9999988888777777666665555544444333332222211111100000

9999988888777777666665555544444333332222211111100000
```

14. 修改代码，使其现在产生以下输出：

```text
999999988888888777777766666655555444443333322222111111

999999988888888777777766666655555444443333322222111111
```

*（注：原文第 14 题最后两行似乎有微小差异，已按原文逻辑保留）*

## 3.1 参数

通过一个或多个参数而产生不同的任务。在 `writeSpaces` 方法中，参数是需要写入的空格数量。

以下是带有写入空格数量参数的 `writeSpaces` 定义：

```java
public static void writeSpaces(int number) {

    for (int i = 1; i <= number; i++) {

        System.out.print(" ");

    }

}
```

该参数出现在方法头中，位于名称之后，并在你到目前为止一直留空的括号内。`writeSpaces` 方法使用名为 `number`、类型为 `int` 的参数。正如前面提到的，你不能再通过它的名称来调用带参数的方法了：

```java
writeSpaces();
```

你现在必须输入如下内容：

```java
writeSpaces(10);
```

当进行此类调用时，值 `10` 被用于初始化参数 `number`。你可以认为这是信息从调用处流向方法：

![](img/aea18896a4bced58de45f29f5a93f7b3_144_0.png)

参数 `number` 是一个局部变量，但它的初始值来自调用。使用值 `10` 调用此方法等同于在 `writeSpaces` 方法的开头包含以下声明：

```java
int number = 10;
```

当然，这种机制比特定的变量声明更灵活，因为你可以改说：

```java
writeSpaces(20);
```

它的效果就好像你在方法开头写了：

```java
int number = 20;
```

你甚至可以在调用中使用整数表达式：

```java
writeSpaces(3 * 4 - 5);
```

# 第 3 章 参数与对象引论

在这种情况下，Java 会评估该表达式以得到值 `7`，然后调用 `writeSpaces`，将 `number` 初始化为 `7`。

计算机科学家广泛使用“参数（parameter）”一词，来同时指代出现在方法头中的内容（**形式参数**）以及出现在方法调用中的内容（**实际参数**）。

### 形式参数（Formal Parameter）

出现在方法头括号内的变量，用于泛化该方法的行为。

### 实际参数（Actual Parameter）

出现在方法调用括号内的特定值或表达式。

“形式参数”这一术语并没有很好地描述它的用途。更好的名称应该是“泛化参数（generalized parameter）”。在 `writeSpaces` 方法中，`number` 是出现在方法声明中的泛化参数。它是某些未指定值的占位符。出现在方法调用中的值是实际参数，因为每次调用都指示了一个要执行的特定任务。换句话说，每个调用都提供了一个实际值来填充占位符。

“参数（argument）”一词经常用作“parameter”的同义词，例如：“这些是我传递给这个方法的参数。”有些人倾向于将“argument”留给实际参数，而将“parameter”留给形式参数。

让我们来看一个你如何使用这个 `writeSpaces` 方法的示例。记住 `DrawFigure2` 程序中拥有以下名为 `drawTop` 的方法：

```java
// 产生沙漏图形的上半部分

public static void drawTop() {

    for (int i = 1; i <= SUB_HEIGHT; i++) {

        System.out.print("|");

        for (int i = 1; i <= (line - 1); i++) {

            System.out.print(" ");

        }

        System.out.print("");

        int spaces = 2 * SUB_HEIGHT - 2 * line;

        for (int i = 1; i <= spaces; i++) {

            System.out.print(" ");

        }

        System.out.print("/");

        for (int i = 1; i <= (line - 1); i++) {

            System.out.print(" ");

        }

        System.out.println("|");

    }

}
```

使用 `writeSpaces` 方法，你可以将其重写如下：

```java
public static void drawTop() {

    for (int line = 1; line <= SUB_HEIGHT; line++) {

        System.out.print("");

        writeSpaces(line - 1);

        System.out.print("");

        writeSpaces(2 * SUB_HEIGHT - 2 * line);

        System.out.print("/");

        writeSpaces(line - 1);

        System.out.println("");

    }

}
```



注意，`writeSpaces` 被调用了三次，每次都指定了所需的空格数量。你也可以类似地修改 `DrawFigure2` 程序中的 `drawBottom` 方法来简化它。

### 参数的机制

当 Java 执行方法调用时，它会初始化方法的参数。对于每个参数，它首先评估作为实际参数传递的表达式，然后使用结果来初始化由形式参数给出的名称的局部变量。让我们用一个例子来澄清这个过程：

## 第 3 章 参数与对象

### 常见编程错误

#### 混淆实参数与形式参数

许多学生在看到形式参数的声明时，错误地认为其语法与传递实参数的语法相同。在将变量传递给参数时写上其类型是一个常见的错误：

```java
writeSpaces(int spaces1); // 这样做不起作用
```

这种混淆是因为参数的类型是在方法的声明中编写的，如下：

```java
public static void writeSpaces(int number)
```

在声明变量或参数时必须编写类型，但在使用变量时（例如调用方法并将其作为实参数传递时），则不需要编写类型。实参数是声明，因此不应在它们之前编写类型：

```java
writeSpaces(spaces1); //这样好得多！
```

### 参数的局限性

我们看到参数可以为方法提供输入。但虽然你可以使用参数将值发送到方法，但不能使用参数从方法中获取值。

当设置参数时，会创建一个局部变量并将其初始化为作为实参数传递的值。最终效果是该局部变量是外部传入值的副本。由于它是局部变量，因此它无法影响方法外的任何变量。考虑以下示例程序：

```java
public class ParameterExample {

    public static void main(String[] args) {

        int x = 17;

        doubleNumber(x);

        System.out.println("x = " + x);

        System.out.println();

        int number = 42;

        doubleNumber(number);

        System.out.println("number = " + number);

    }

    public static void doubleNumber(int number) {

        System.out.println("Initial value = " + number);

        number *= 2;

        System.out.println("Final value = " + number);

    }

}
```

#### 3.1 参数

该程序首先声明并初始化名为`x`的整数变量，赋值为 17：

```
method main

x = 17
```

然后它调用方法`doubleNumber`，将`x`作为参数传递。`x`的值被用于初始化方法`doubleNumber`中的局部变量参数`number`：

```
method main

method doubleNumber

number 17
```

程序执行`doubleNumber`内部的语句。`doubleNumber`首先打印`number`的初始值（17）。然后将`number`翻倍：

```
method main

method doubleNumber

x = 17

number 34
```

注意，这对变量`x`没有产生影响。名为`number`的参数是`x`的副本，尽管它们的初始值相同，但改变`number`的值不会影响`x`。`doubleNumber`接着报告`number`的新值（34）。此时，`doubleNumber`完成执行，我们返回`main`方法：

```
method main

x = 17
```

`main`方法中的下一条语句报告`x`的值，即 17。然后它声明并初始化了一个变量`number`，赋值为 42：

```
method main

x = 17

number 42
```

接下来的语句再次调用`doubleNumber`，这次传递了`number`的值。这是一个奇怪的情况，因为参数的名字与`main`方法中的变量名相同，但 Java 并不在意。它总是为`doubleNumber`方法创建一个新的局部变量：

```
method main

method doubleNumber

x 17 number 42

x number 42
```

所以，此时有两个不同的名为`number`的变量，各位于一个方法中。现在又是再次执行`doubleNumber`的语句了。它首先报告`number`的值（42），然后将其翻倍：

```
method main

method doubleNumber

x 17 number 42

x number 84
```

再次注意，在`doubleNumber`内部将`number`翻倍对`main`方法中的原始变量`number`没有影响。它们是独立的变量。该方法报告`number`的新值（84）并返回`main`：

```
method main

x = 17 number 84
```

程序随后报告`number`的值并终止。因此，程序的整体输出如下：

- Initial value = 17
  Final value = 34
  x = 17

- Initial value = 42
  Final value = 84
  number = 42

对参数的局部操作不会改变方法外的这些变量。变量被复制这一事实是参数的一个重要方面。从好的方面来说，我们知道变量免受修改，因为参数是原始值的副本。从坏的来说，这意味着虽然参数允许我们将值发送到方法中，但它们不允许我们从方法中获取值。

### 多参数

到目前为止，我们对参数语法的讨论是非正式的。现在是时候更精确地写下声明带参数的静态方法时使用的语法了。如下：

```java
public static void method(<type><name>, ..., <type><name>) (

<statement or variable declaration>);
```

```java
<statement or variable declaration>;

...\<statement or variable declaration>;
```

此模板表明，我们可以在方法名后出现的括号内声明任意数量的参数。我们使用逗号来分隔不同的参数。作为带有多个参数方法的示例，让我们考虑`writeSpaces`。如果我们想使用一个字符和次数，头部将如下：

```java
public static void writeSpaces(char ch, int number)
```

如果我们想使用更多的参数，头部将看起来像这样：

```java
public static void writeSpaces(char ch, int number, int other1, int other2)
```

#### 3.1 参数

因此，你可能会发现使用每种技术的机会。基本规则是，当你只想在每次执行之间更改该值时，请使用类常量。如果你想在单次执行中使用不同的值，请使用参数。

## 方法重载（Overloading of Methods）

你通常会想要创建该方法的细微变体，并传递不同的参数。例如，你可能有一个`drawbox`方法，允许你指定特定的高度和宽度，但你可能也希望有一个版本可以绘制默认大小的矩形。换句话说，有时你想指定这些值：

```java
drawBox(8, 10);
```

而另时候，你只需要告诉它画一个具有标准高度和宽度的框：

```java
drawBox();
```

某些编程语言要求你为这些版本想不同的名称，例如`drawBox`和`drawDefaultBox`。正如你可以想象的，为每个变体想新名称会变得非常麻烦。幸运的是，Java 允许你拥有多个同名的方法，只要它们的参数不同。这被称为重载。重载的主要要求是你所定义的不同方法必须具有不同的方法签名。

> **方法签名（Method Signature）**  
> 方法名以及其参数的数量和类型。

> **方法重载（Method Overloading）**  
> 定义两个或多个同名但方法签名不同的方法的能力。

这两个`drawbox`版本显然具有不同的方法签名，因为一个有两个参数，而另一个是零参数。从对该方法的任何调用中都可以明显看出使用哪一个版本：如果你看到两个参数，就执行带有两个参数的版本；如果你看到零参数，就执行零参数的版本。

当重载涉及相同数量的参数时，情况变得复杂，但这事实证明是重载最有用的应用之一。例如，`println`实际上是一系列重载方法。我们可以通过传递`String`、`int`、`double`等来调用`println`。这种灵活性是通过一系列不同的方法来实现的，所有方法都接受一个参数：一个版本接受`String`，另一个版本接受`int`，另一个版本接受`double`，依此类推。显然，打印其中一种数据类型的数据与打印另一种数据相比，你执行的操作略有不同，这就是为什么拥有这些方法的不同版本是有用的。

## 第 3 章 参数与对象简介

### 3.2 返回值的方法

我们看过的最后几个方法是执行特定任务的动作导向型方法。你可以把它们想象成像是下发给某人的命令，例如“画一个矩形”或“画一个三角形”。参数允许这些命令更加灵活，例如“画一个 10 比 20 的矩形”。

你也将能够编写计算值的方法。这些方法更像是问题，例如“2.5 的平方根是多少？”或“2.3 的 4 次方是多少？”例如，考虑一个计算数字平方根的方法。

表面看起来，编写此类方法的方法似乎是接受一个`double`类型的参数，并将其平方根打印到控制台上。但你可能想将平方根作为更大表达式或计算的一部分，例如通过求解二次方程或计算 x/y 平面上点之间的距离。

一个更好的解决方案是使用平方根命令，将感兴趣的数字作为参数传递，并将其平方根作为结果返回给程序。然后你可以将该结果作为表达式的一部分、将其存储在变量中，或将其打印在控制台上。这样的命令是种被称为“返回值”的新类型方法。

> **返回（Return）**  
> 将一个值作为方法的结果发送出去，该值可以在你程序的表达式中使用。`void`方法不返回任何值。

如果你有这样一个方法，可以通过像下面的代码来请求 2.5 的平方根：

```java
// 假设你有一个名为 sqrt 的方法

double answer = sqrt(2.5);
```

`sqrt`方法有一个参数（要找到平方根的数字），但它也返回一个值（平方根）。实际参数 2.5“进入”方法，而平方根则出来。在前面的代码中，返回的结果存储在一个名为`answer`的变量中。

你可以通过查看方法头来判断一个方法是否返回结果。你到目前为止编写的所有方法都是`public static void`，例如：

```java
public static void drawTriangle(int height)
```

`void`词被称为方法的返回类型。  
`void`返回类型有点奇怪，因为正如该词暗示的，意味着方法不返回任何内容，而不是使用任何合法类型。因此，你可以编写返回`int`、`double`或任何其他类型的方法。在`sqrt`方法的情况下，你希望它返回一个`double`，因此你会如下写它的方法头：

```java
public static double sqrt(double n)
```

与前面的情况一样，`public static`之后的词是方法的返回类型：

```java
public static double sqrt(double n)

return type;
```

幸运的是，你实际上不需要专门写一个计算数字平方根的方法，因为 Java 有一个内置的。该方法包含在一个名为`Math`的类中，该类包含了许多常用的计算方法。因此，在我们讨论编写返回值方法的细节之前，让我们先探索`Math`类以及它提供的功能。

## Math 类

在第 1 章中，我们提到大量的数学函数统称为`Math`类，它们是可用的。`Math`类包含在一个类中，包含了许多常用的计算方法。因此，在我们讨论编写返回值方法的细节之前，让我们先探索`Math`类以及它提供的功能。

### 3.2 返回值的方法

表 3.2 Math 类中常用的静态方法

| 方法 | 描述 | 示例 |
|---|---|---|
| `abs` | 绝对值 | `Math.abs(-308)` 返回 308 |
| `ceil` | 向上值（向上取整） | `Math.ceil(2.13)` 返回 3.0 |
| `cos` | 余弦（弧度） | `Math.cos(Math.PI)` 返回 -1.0 |
| `exp` | 以 e 为底的指数 | `Math.exp(1)` 返回 2.718281824590455 |
| `floor` | 地板（向下取整） | `Math.floor(2.93)` 返回 2.0 |
| `log` | 以 e 为底的对数 | `Math.log(45, 4)` 返回 1.0 |
| `log10` | 以 10 为底的对数 | `Math.log10(1000)` 返回 3.0 |
| `max` | 两个值中的最大值 | `Math.max(45, 207)` 返回 207 |
| `min` | 两个值中的最小值 | `Math.min(3.8, 2.75)` 返回 2.75 |
| `pow` | 次方（通用幂运算） | `Math.pow(3, 4)` 返回 81.0 double k 使得 0.0 ≤ k < 1.0 |
| `sin` | 正弦（弧度） | `Math.sin(0)` 返回 0.0 |
| `sqrt` | 平方 | `Math.sqrt(2)` 返回 1.414213562730951 |
| `toDegrees` | 将弧度转换为角度 | `Math.toDegrees(Math.PI)` 返回 180.0 |
| `toRadians` | 将角度转换为弧度 | `Math.toRadians(270.0)` 返回 4.7123889038469 |

## 定义返回值的方法

你可以使用一种特殊的`return`语句来编写返回值的方法。例如，这里有一个方法接受以英尺为单位的距离并返回对应的英里数：

```java
public static double miles(double feet) {

    return feet / 5280.0;

}
```

`miles`方法可以在代码的`main`方法中如下所示使用：

```java
System.out.println("15000 feet is " + miles(15000) + " miles.");
```

再次注意，在方法头中，熟悉的`void`被单词`double`替换了。记住，当你声明一个返回值的方法时，你必须告诉 Java 它将返回什么类型的值。然后，我们可以再次更新静态方法的语法模板，以明确方法头包含一个返回类型（无返回值则用`void`）：

```java
public static <type> <name>(<type> <name>, ..., <type> <name> (

    <statement or variable declaration>;

    <statement or variable declaration>;

    ...

    <statement or variable declaration>;

)
```

`return`语句的语法为：

```java
return <expression>;
```

当 Java 遇到`return`语句时，它会计算给定的表达式并立即终止方法，返回从表达式中获得的值。由于这一点，在`return`语句之后放置任何其他语句都是不法的；`return`必须是方法中的最后一条语句。对于具有非`void`返回类型的 Java 方法，在没有返回语句的情况下终止也是一个错误。

上述规则有例外，你稍后会看到。例如，一个方法可以有多个`return`语句；这将在下一章出现，当我们讨论使用`if`和`if/else`语句进行条件执行时。

让我们看看另一个返回值的方法。三角形的勾股定理（如《魔法仙师》中的稻草人所说）规定直角三角形斜边的长度等于另外两条边平方和的平方根。如果你知道一个直角三角形两条边`a`和`b`的长度，并想找到第三条边`c`的长度，你可以这样计算：

```java
c = a^2 + b^2
```

假设你想打印两个直角三角形的斜边长度：一个的边长为 5 和 12，另一个边长为 3 和 4。你可以编写如下代码：

```java
double c1 = Math.sqrt(Math.pow(5, 2) + Math.pow(12, 2));

System.out.println("hypotenuse 1 = " + c1);

double c2 = Math.sqrt(Math.pow(3, 2) + Math.pow(4, 2));

System.out.println("hypotenuse 2 = " + c2);
```

前面的代码是正确的，但很难易读，如果你想包含更多内容，就得浪费时间。更好的解决方案是创建一个方法，根据给定的长度参数计算并返回斜边。这样的方法看起来像这样：

```java
public static double hypotenuse(double a, double b) {

    return Math.sqrt(Math.pow(a, 2) + Math.pow(b, 2));

}
```

此方法可以用于编写更简洁的`main`方法，如下所示：

```java
public class Triangles {

    public static void main(String[] args) {
```



```java我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。System.out.println("hypotenuse 1 = " + hypotenuse(5, 12));

System.out.println("hypotenuse 2 = " + hypotenuse(3, 4));

}
}
```

此外，一些程序员避免对低幂（如 2）使用`Math.pow`，而是手动进行乘法。使用那种方法，斜边的主体将使用：

```java
return Math.sqrt(a * a + b * b);
```

# 第 3 章 参数和对象

## 常见编程错误

### 忽略返回值

当你调用一个有返回值的方法时，预期是你会对返回的值进行某些处理。你可以打印它、将其存储在变量中或将其作为较大表达式的一部分。仅仅调用方法并忽略返回的值是合法的（但是不明智的）：

```java
miles(15000); // 什么也没做
```

然而，前面的调用并没有打印英里数，也没有产生任何可见效果。如果你想打印这个值，你必须包含一个打印语句：

```java
double vacation = miles(15000);

System.out.println("I drove " + vacation + " miles.");
```

修复后代码的更短形式如下：

```java
System.out.println("I drove " + miles(15000) + " miles.");
```

### Return 之后的语句

在`return`语句之后放置其他语句是非法的，因为这些语句永远无法执行。新程序员在尝试打印变量的值时经常这样做。假设你写了`hypotenuse`方法，但不小心写错了`Math.pow`的参数顺序，导致方法没有产生答案。你会通过打印返回的`c`来尝试调试。这里是错误的代码：

```java
// 尝试找到这个版本 hypotenuse 中的 bug

public static double hypotenuse(double a, double b) {

    double c = Math.sqrt(Math.pow(2, a) + Math.pow(2, b));

    return c;

    System.out.println(c); // 这不起行

}
```

编译器会抱怨`println`语句不可达的，因为它在`return`语句之后。编译错误输出看起来如下：

```text
Triangles.java:10: unreachable statement

System.out.println(c);
```

```text
Triangles.java:11: missing return statement
}
```

2 个错误

修复方法是将`println`语句移动到方法的早位置，在`return`语句之前：

```java
public static double hypotenuse(double a, double b) {

    double c = Math.sqrt(Math.pow(2, a) + Math.pow(2, b));

    System.out.println(c); // 更好

    return c;

}
```

## 3.3 使用对象

将数据和操作封装成一个实体是对象背后的核心思想。对象存储某些数据以及作用于这些数据的方法。

> **对象（Object）**  
> 包含状态（数据）和行为（方法）的编程实体。

正如我们在第一章中所说的，类是 Java 程序的类构建块。但类还有另一个用途：描述新类型的对象。

> **类（Class）**  
> 对象的类别或类型。

当这样使用类时，它就像是对象外观的蓝图。一旦你给 Java 提供了蓝图，你就可以要求它创建符合该蓝图的实际对象。我们有时将单个对象称为类的实例（instances）或对象（objects）。我们倾向于交替使用“实例”和“对象”这两个词。

这个概念在抽象情况下是理解的。为了帮助你掌握它的含义和工作原理，我们将查看几个不同的类。为了先关注基本概念，在本章中，我们将学习如何使用 Java 中已经存在的现有对象，但我们现在不会学习如何定义自己的新类型对象。在我们有足够练习使用对象之后，会在第 8 章再讨论这个问题。

使用对象与原始类型不同，因此我们将引入一些新的语法和概念。如果 Java 有一个统一的模型来使用所有类型的数据就很好，但它并没有。因此，如果你想理解你的程序如何运行，就必须学习两套规则：一套针对原始类型，一套针对对象。

## String 对象

字符串是 Java 中最有用且常用的对象类型之一，因此它们是一个很好的起点。不过，它们并不是最好的例子，因为有很多只适用于字符串的特殊规则。在下一节中，我们将查看更典型的对象。

字符串有一个特殊属性，即表示`String`对象的字面量（字符串字面量）。从第一章开始，我们就在`println`语句中使用它们。我们还没有讨论的是这些字面量值代表`String`类型的对象（`String`类的实例）。例如，就像你可以说：

```java
int x = 8;
```

你也可以说：

```java
String s = "hello";
```

你可以声明`String`类型的变量并使用赋值语句给这些变量赋值。你还可以编写涉及`String`表达式的代码：

```java
String s1 = "hello";

String s2 = "there";

String combined = s1 + " " + s2;
```

这段代码定义了两个`String`，每个代表一个单词，第三个`String`代表两个单词之间带空格的连接。你会注意到，`String`类型的首字母是大写的，正如 Java 中所有对象类型的名称一样，而原始类型（如`double`和`int`）不同。这些示例还没有显示`String`对象的任何特殊之处，但我们正在接近了。请记住，对象背后的思想是将基本操作包含数据本身，就像我们让汽车内置控制装置一样。存储在`String`中的数据是一个字符序列。你可能想在这个字符序列上执行各种操作。例如，你可能想知道`String`中有多少个字符。`String`对象有一个返回此信息的长度方法。

如果`length`方法是静态的，你会通过像这样的方式来调用它：

```java
length(s) // 这是不合法的
```

但在对对象执行操作时，你将使用不同的语法。对象存储数据和方法，因此报告`String`长度的方法实际上存在于`String`对象内部。要调用对象的方法，你会使用第一个变量名，后面跟着一个点，然后是方法名：

```java
s.length()
```

把它想象成是在与`String`对象对话。当你请求`s.length()`时，你是在说：“嘿，我正在和你说话。你的长度是多少？”当然，不同的`String`对象有不同的长度，所以当你与不同的对象通信时，你会得到不同的答案。

调用对象方法的通用语法如下：

```text
<variable>.<method name><expression>, <expression>, ..., <expression>
```

例如，假设你这样初始化两个`String`变量：

```java
String s1 = "hello";

String s2 = "how are you?";
```

你可以使用`println`来检查每个字符串的长度：

```java
System.out.println("Length of s1 = " + s1.length());

System.out.println("Length of s2 = " + s2.length());
```

这将产生以下输出：

```text
Length of s1 = 5

Length of s2 = 12
```

## 3.3 使用对象

你还想对`String`对象做什么？通过长度你可以算出字符串中有多少个字符，但获取单个字符本身呢？有几种方法可以实现这一点，但最常见方法之一是使用名为`charAt`的方法，它返回字符串中特定位置的字符。

这引出了我们关于如何在序列中指定位置的问题。显然，有一个第一个字符、第二个字符，以此类推，使用整数来引用特定位置是有意义的。我们将其称为索引（index）。

### 索引

用于指定值序列中位置的整数。Java 通常使用从零索引（以 0 作为第一个索引）。

考虑字符串`"hello"`。字符及其索引如下：

| Index | Character |
|---|---|
| 0 | h |
| 1 | e |
| 2 | l |
| 3 | l |
| 4 | o |

考虑字符串`"how are you?"`。字符及其索引如下：

| Index | Character |
|---|---|
| 0 | h |
| 1 | o |
| 2 | w |
| 3 | (space) |
| 4 | r |
| 5 | e |
| 6 | (space) |
| 7 | y |
| 8 | o |
| 9 | (space) |
| 10 | u |
| 11 | ? |

由于从零索引，第一个字符在索引 0，第二个字符在索引 1，以此类推。要获取特定位置的字符，你可以使用`charAt`方法：

```java
String s = "hello";

char c = s.charAt(0); // 'h'

char c2 = s.charAt(4); // 'o'
```

如果你尝试访问范围外的索引，Java 将抛出`StringIndexException`：

```java
s.charAt(5); // throws StringIndexException
```

你的程序将产生一个执行错误。同样，如果你在一个不存在的位置请求`charAt`，你的程序也将产生一个执行错误。这些错误被称为**异常**（exceptions）。

正如第 1 章提到的，异常是运行时错误。

> **异常**  
> 阻止程序继续正常执行的运行时错误。

我们说当遇到错误时，会“抛出”（thrown）一个异常。当异常被抛出时，Java 会检查你是否编写了代码来处理它。如果没有，程序执行将停止，你将看到所谓的“堆栈跟踪”（stack trace）或回溯轨迹（back trace）。堆栈跟踪按反序显示已调用过的一系列方法。在字符串索引无效的情况下，异常会在控制台上打印出如下所示的消息：

```text
Exception in thread "main"

java.lang.StringIndexOutOfBoundsException:

String index out of range: 13

at java.lang.String.substring(Unknown Source)

at ExampleProgram.main(ExampleProgram.java:3)
```

你可以将异常作为方法的参数。例如，以下程序使用`String`参数来消除一首流行儿童歌曲中的某些冗余：

```java
public class Bus {

    public static void main(String[] args) {

        verse("wheels", "go", "round and round");

        verse("wipers", "go", "swish, swish, swish");

        verse("horn", "go", "beep, beep, beep");

    }

    public static void verse(String item, String verb) {

        String sound;

        System.out.println("" + item + " on the bus " +

            verb + " " + sound + " ");

        System.out.println(sound + ",");

        System.out.println("The " + item + " on the bus " +

            verb + " " + sound + " ");

        System.out.println("All through the town.");

        System.out.println();

    }

}
```

它产生了以下输出：

```text
The wheels on the bus go round and round,
round and round,
round and round.
The wheels on the bus go round and round,
All through the town.

The wipers on the bus go swish, swish, swish,
swish, swish, swish.
The wipers on the bus go swish, swish, swish,
All through the town.

The horn on the bus goes beep, beep, beep,
beep, beep, beep,
beep, beep, beep.
The horn on the bus goes beep, beep, beep,
All through the town.
```

表 3.3 列出了你可以在`String`对象上调的一些最有用的方法。Java 中的`String`是**不可变的**（immutable），这意味着一旦它们被构造出来，它们的值就永远无法改变。

### 不可变对象

对象的值不能被改变。

字符串是不可变的但又有像`toUpperCase`和`toLowerCase`这样的方法，这似乎很奇怪。但如果你仔细阅读表中的描述，你会发现这些方法并没有改变给定的字符串对象：相反返回返回一个新的字符串。考虑以下代码：

| 表 3.3 String 对象的实用方法 | 方法 | 描述 | 示例（假设 s 为 "hello"） |
| :--- | :--- | :--- | :--- |
| `charAt(index)` | 获取特定索引处的字符 | `s.charAt(1)`返回`'e'` |
| `endsWith(text)` | 字符串是否以某些文本结尾 | `s.endsWith("llo")`返回`true` |
| `indexOf(text)` | 特定字符或字符串的索引（不存在则返回 -1） | `s.indexOf("o")`返回 4 |
| `length()` | 字符串中字符的数量 | `s.length()`返回 5 |
| `startsWith(text)` | 字符串是否以某些文本开头 | `s.startsWith("hi")`返回`false` |
| `substring(start, stop)` | 从 start 索引到 stop 索引之前的字符 | `s.substring(1, 3)`返回`"el"` |
| `toLowerCase()` | 全为小写字母的新字符串 | `s.toLowerCase()`返回`"hello"` |
| `toUpperCase()` | 全为大写字母的新字符串 | `s.toUpperCase()`返回`"HELLO"` |

```java
String s = "Hello María";

s.toUpperCase();

System.out.println(s);
```

你可能认为这会将字符串`s`转换为其大写对应的形式，但事实并非如此。第二行代码构造了一个新字符串，其值是`s`值的大写形式，但我们没有对这个新值进行任何操作。关键是将这个新字符串存储在不同的变量中，或者将变量`s`重新赋值指向新字符串：

```java
String s = "Hello María";

s = s.toUpperCase();

System.out.println(s);
```

此版本的代码会产生以下结果：

```text
HELLO MARIA
```

当你想要执行字符串比较且忽略涉及字母的大小写情况时，`toUpperCase`和`toLowerCase`方法特别有帮助。

## 点对象

String 是非常有用的对象，但创建和使用它们的规则与其他类型的对象规则并不完全匹配。我们现在来检查一种更典型的对象类型：`Point`。`Point`对象存储了二维空间中点的`(x, y)`坐标。这些坐标以整数形式表示，尽管也有存储使用浮点数表示点的变体。

String 是具有字面量（literal values）的特殊情况。对`Point`可以做的其他事情之一是：

> **构造函数**  
> 一个初始化对象的方法。

记住 Java 对象必须通过构造函数初始化。例如，你可以说：

```java
Point p = new Point(3, 8);
```

由于`Point`初始坐标为 (3, 8)，这个平移将`Point`变为 (2, 6)。因此，在这行代码之后，你可以说：

```java
p.translate(-1, -2);
```

对`Point`可以做的其他事情之一是使用点符号引用它的`x`和`y`值：

```java
int sum = p.x + p.y;

System.out.println("Sum of coordinates = " + sum);
```

你可以直接修改这些值，例如：

```java
p.x = 12;

p.y = 15;
```




| 表我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。3.4 `Point` 对象的实用方法 | 方法 | 描述 |
| :--- | :--- | :--- |
| `translate(dx, dy)` | 按给定量平移坐标 |
| `getLocation(x, y)` | 设置坐标为给定值 |
| `distance(p2)` | 返回此点到 `p2` 的距离 |

`Point` 类包含了一些实用方法。这里是一个完整的程序，构造了一个 `Point` 对象并平移了坐标，使用 `println` 语句在调用前后检查坐标：

```java
import java.awt.*;

public class PointExample {

    public static void main(String[] args) {

        Point p = new Point(3, 8);

        System.out.println("initially p = " + p + ");

        p.translate(-1, -2);

        System.out.println("after translating p = " + p + ");

    }

}
```

此代码产生以下输出：

```
initially p = java.awt.Point[x=3,y=8]

after translating p = java.awt.Point[x=2,y=6]
```

此类文件的开头没有任何新内容。记住 Java 有大量的类，它们被统称为 Java 类库。Java 提供了一个组织单元化的“包”（package）。相关的类被组合在单个包中。例如，`Point` 类存储在 `java.awt` 包中。除非包含导入语句，否则 Java 程序通常无法访问某个包。

我们之前还没有需要导入语句，因为 Java 会自动导入存储在 `java.lang` 包中的所有类。`java.lang` 包包括大多数 Java 程序可能会用到的基础类（例如，`System`、`String`、`Math`）。由于 Java 不会自动导入 `java.awt;`，你必须手动进行导入。

Java 允许你使用星号来导入包中的所有类：

```java
import java.awt.*;
```

但有些人更倾向于显式列出他们导入的每个类。`import` 声明允许你从一个包中只导入一个类，例如：

```java
import java.awt.Point;
```

问题在于，一旦你开始从某个包中导入一个类，你很可能也想导入其他类。为了保持简单，我们将在本书中使用星号形式的 `import`。

## 引用语义

对象在计算机内存中的存储方式与原始数据类型不同。例如，当我们声明一个整数变量时：

```java
int x = 8;
```

该变量存储的是实际数据。因此，我们绘制了类似下面的图片：

![](img/aea18896a4bced58de45f29f5a93f7b3_171_0.png)

对象的情况则不同。对于对象，变量并不存储实际数据。相反，数据存储在对象中，而变量存储指向对象存储位置的引用。因此，在内存中有两个元素：变量和对象。所以，当我们构造一个 `Point` 对象时：

```java
Point p = new Point(3, 8);
```

我们最终得到了如下：

如图所示，内存中存储了两个不同的值：`Point` 对象本身（显示在图的右侧），以及名为 `p` 的变量，它存储了指向 `Point` 对象的引用（在图中用箭头表示）。我们说 `p` 该对象。

可能需要一些时间来适应这不同的数据存储方法，但这些方法非常常见，以至于计算机科学家有专门的技术术语来描述它们。像 `int` 的原始类型系统被称为**值类型**（value types），这些类型通常被称为值类型。`Point` 以及其他对象的系统被称为**引用语义**（reference semantics），这些类型通常被称为**引用类型**（reference types）。

## 3.3 使用对象

### 值语义（值类型）

一种直接存储值且复制涉及创建值独立副本的系统。使用值语义的类型被称为值类型。

### 引用语义（引用类型）

一种存储指向值的引用且复制涉及复制引用的系统。使用引用语义的类型被称为引用类型。

我们需要一段时间来探索这种差异的所有影响。要记住的关键点是，当你处理对象时，你始终是在处理数据的引用，而不是数据本身。

到此时，你可能在想为什么 Java 有这两个不同的系统。Java 是为面向对象的编程设计的，因此要考虑的第一个问题是 Sun 公司为何决定对象应该具有引用语义。有两个原因：

- **效率**。对象可能是复杂的，这意味着它们可能会占用大量的内存。我们不希望必须复制此类对象，因为内存很快就会耗尽。例如，一个存储大量字符的 `String` 对象可能会占用大量的内存空间。但即使 `String` 对象非常大，它的引用也可以很小，就像即使是豪宅也有一个简单的街道地址一样。另一个类比，想想我们如何使用手机与人通信。手机可以很小且易于携带，因为手机号不占用多少空间。想象一下，如果不是随身携带手机号码，而是尝试随身携带真实的人，会有多大的不同！

- **共享**。通常情况下，仅仅拥有某物的副本是不够的。假设你的老师告诉班上所有的学生把试卷放在某个箱子里。想象一下，如果每个学生都制作一个盒子的拷贝会有无意义且混乱。明显的意图是让所有学生使用同一个盒子。通过引用语义，你可以对单个对象拥有多个引用，这允许程序的不同部分共享某个对象。

如果没有引用语义，Java 程序的编写将变得困难。为什么 Sun 公司也决定包含具有值语义的原始类型？原因主要是历史性的。Sun 公司想利用 C 和 C++ 的流行性（它们具有相似的类型），并确保 Java 程序运行得更快，这通过更传统的原始类型更容易实现。如果 Sun 今天有机会重新设计 Java，他们完全可能会弃弃原始类型，采用基于引用语义的一致对象模型。

## 多个对象

在上一节中，你学习了如何操作单个对象。考虑以下构造两个不同对象的代码行：

```java
Point p1 = new Point(3, 8);

Point p2 = new Point();
```

每个对象必须通过调用 `new` 分别构造。记住，我们称这些为该类的**实例**。第一次调用传递了 `Point` 的 x 和 y 坐标。第二次调用使用了一个不同的构造函数，它设置了不同的方法签名（零个参数而不是两个参数）。这个构造函数将 x 和 y 坐标设置为 0。这种零参数构造函数通常被称为**默认构造函数**。执行这些语句后，内存看起来像这样：

![](img/aea18896a4bced58de45f29f5a93f7b3_173_0.png)

为了强调变量和对象是分开存储的，请考虑如果你现在执行以下代码会发生什么：

```java
Point p3 = p2;
```

这声明了第三个变量。尽管你现在有了三个 `Point` 变量，但内存中只有两个对象：

![](img/aea18896a4bced58de45f29f5a93f7b3_173_1.png)

变量 `p2` 和 `p3` 指向同一个对象。这种情况在使用像 `int` 这样的值类型时不会出现。让我们看一个完整的程序来看看它是如何工作的：

```java
import java.awt.*;

public class PointExample {

    public static void main(String[] args) {

        // 声明并构造对象

        Point p1 = new Point(3, 8);

        Point p2 = new Point();

        Point p3 = p2;

        // 查看初始点状态

        System.out.println("p1 = " + p1);

        System.out.println("p2 = " + p2);

        System.out.println("p3 = " + p3);

        // 移动

        p1.translate(-1, -2);

        p2.translate(4, 8);

        p3.translate(2, 3);

        // 查看现在的点状态

        System.out.println("p1 = " + p1);

        System.out.println("p2 = " + p2);

        System.out.println("p3 = " + p3);

    }

}
```

该程序产生的输出可能会让你感到惊讶：

```
p1 = java.awt.Point[x=3,y=8]

p2 = java.awt.Point[x=0,y=0]

p3 = java.awt.Point[x=0,y=0]

p1 = java.awt.Point[x=2,y=6]

p2 = java.awt.Point[x=6,y=11]

p3 = java.awt.Point[x=6,y=11]
```

我们最终得到了坐标 (6, 11)，但原始程序中并没有 6 或 11。让我们看看这是如何发生的。使用变量 `p1` 的操作是直接的。变量 `p2` 和 `p3` 指向同一个对象。这个对象初始化为 (0, 0)。

### 对象作为方法的参数

考虑当你定义一个使用引用类型作为参数的静态方法时会发生什么：

```java
public static void manipulate(Point p) {

    p.translate(2, 3);

}
```

请记住，参数是调用时传入的内容的副本。对于像 `int` 等值类型，你对参数的任何更改对传递给方法的变量没有影响。对于对象来说，情况要复杂得多，因为它们具有引用语义。假设你定义了一个 `Point` 变量并将其传递给方法：

```java
Point test = new Point(6, 15);

manipulate(test);
```

该方法最终翻译了对象的坐标吗？答案是肯定的，尽管你使用的是一个创建副本的参数。请思考计算机内存中发生了什么。当你声明 `test` 变量时，会形成以下情况：

![](img/aea18896a4bced58de45f29f5a93f7b3_176_0.png)

当你调用 `manipulate` 方法时，Java 会创建变量 `test` 的副本并将其存储在参数 `p` 中。但变量 `test` 本身并不是一个对象：它存储的是指向一个对象的引用。因此，当你对它进行复制时，内存中会形成以下情况：

![](img/aea18896a4bced58de45f29f5a93f7b3_176_1.png)

你现在有两个指向同一个 `Point` 对象的变量。`p` 是一个副本并不重要，因为它与原始变量指向同一个对象。因此，使用 `p` 对 `translate` 的任何调用都会改变 `test` 所引用的对象。

还有另一种值得考虑的情况。假设你以以下方式编写了 `manipulate` 方法：

```java
public static void manipulate(Point p) {

  p.translate(2, 3);

  p = new Point(17, 45);

}
```

让我们详细查看此过程。当方法被调用时，变量 `p` 被设定为变量 `test` 的副本，这导致两个变量指向同一个 `Point` 对象：

![](img/aea18896a4bced58de45f29f5a93f7b3_176_2.png)

`p` 的坐标在 x 方向上平移了 2，在 y 方向上平移了 3，就像旧版本的方法一样：

![](img/aea18896a4bced58de45f29f5a93f7b3_177_0.png)

然后变量 `p` 被重置为一个具有不同坐标集的新 `Point` 对象。这会影响 `test` 变量吗？答案是不会。因为 `p` 是一个本地副本，改变它的值对 `test` 没有影响：

![](img/aea18896a4bced58de45f29f5a93f7b3_177_1.png)

核心点是，当你将对象作为参数传递时，你可以更改对象本身，但你不能更改指向对象的变量。

电话号码提供了一个很好的类比。假设你有一张纸，上面写着一个人的电话号码。这让你拥有拨打那个人的能力。你可以复制这张纸并把它给给一个朋友，这类似于将对象作为参数传递给方法时发生的情况。因为你手里有一张写有电话号码的纸，你仍然可以拨打那个电话。但你的朋友也有这个电话号码，所以朋友也可以拨打。

## 3.4 交互式程序

正如你所看到的，你可以通过调用 `System.out.println` 和 `System.out.print` 轻松地在控制台窗口产生输出。你还可以编写暂停并等待用户输入的程序。此类程序被称为交互式程序，用户输入的响应被称为控制台输入。

### 控制台输入

交互式程序等待输入时，用户输入的响应。

当你引用 `System.out` 时，你正在访问 `System` 类中一个名为标准输出流（简称为“standard”）的对象。Java 中有一个对应的标准输入对象名为 `System.in`，但它并不是为了控制台输入而设计的，`System.in` 在此用途上一直并不特别好用。幸运的是，我们有一种更的方法来读取控制台输入：`Scanner` 对象。

### `Scanner` 对象

从 1.5 版本开始，Java 有了一个 `Scanner` 类，简化了从控制台和文件的读取。它是 `java.util` 包的一部分，因此在使用 `Scanner` 的程序中，你必须记得包含以下导入声明：

```java
import java.util.*; // 用于 Scanner
```

要使用 `Scanner` 对象，你必须首先构造它。你可以通过传递一个输入流的引用来构造 `Scanner`。要从控制台窗口读取，请传递 `System.in`：

```java
Scanner console = new Scanner(System.in);
```

一旦构造完成，你就可以要求 `Scanner` 返回特定类型的值。可以使用许多都以 "next" 单词开头的方法来获取各种类型的值。表 3.5 列出了这些方法。

通常，你将使用变量来跟踪这些方法返回的值。例如，你可能会说：

```java
int n = console.nextInt();
```

对 `console` 对象的 `nextInt` 方法的调用会等待用户输入。每当计算机等待输入时，它就会暂停。你可以使用 `Scanner` 类通过 `nextLine` 方法逐行读取，换句话说，每当计算机等待输入时，它会等待按下回车键。`next` 方法是基于行的；它们读取单个元素。

## 3.5 `Scanner` 方法

| 方法 | 描述 |
| :--- | :--- |
| `next()` | 读取下一个标记为 `String` |
| `nextDouble()` | 读取下一个 `double` 值 |
| `nextInt()` | 读取下一个 `int` 值 |
| `nextLine()` | 读取下一行作为 `String` |

## 3.4 交互式程序

### 示例交互式程序

使用 `Scanner` 类，我们可以编写一个为用户执行有用计算的完整交互式程序。如果你发现买房子，你想知道月供是多少。以下是一个完整的程序，它询问贷款信息并打印款额：

```java
import java.util.*; // 用于 Scanner

public class Mortgage {

  public static void main(String[] args) {

    Scanner console = new Scanner(System.in);

    // 获取值

    System.out.println("此程序计算每月贷款还款。");

    System.out.print("贷款金额： ");

    double loan = console.nextDouble();

    System.out.print("贷款年限： ");

    int years = console.nextInt();

    System.out.print("利率： ");

    double rate = console.nextDouble();

    // 计算结果并报告

    int n = 12 + years;

    double c = rate / 12.0 / 100.0;

    double payment = loan * c * Math.pow(1 + c, n) / (Math.pow(1 + c, n) - 1);

    System.out.println("还款 = $" + (int) payment);

  }

}
```

以下是程序的示例执行（用户输入以加粗显示）：

- 贷款金额：**275000**
- 贷款年限：**30**
- 利率：**6.75**

还款 = $1783

第一条语句被称为提示（prompt），即向用户请求信息。我们使用不带 `println` 的 `print` 语句，以便用户可以在提示所在的同一行内输入值（即在提示的右侧）。第二条语句调用控制台的 `nextDouble` 方法，从用户处读取一个 `double` 类型的值。该值被存储在一个名为 `loan` 的变量中。这种“提示/读取”的模式在交互式程序中非常常见。

在提示输入值后，程序会计算几个值。计算住房贷款还款的公式涉及贷款金额（loan）、涉及的总月数（我们称之为 `n`）以及每月利率（我们称之为 `c`）。还款公式由以下方程给出：

```text
payment = loan * \frac{c(1 + c)^n}{(1 + c)^n - 1}
```




你会在程序中注意到我们使用了`Math.pow`方法进行幂运算，将此公式转换为 Java 表达式。

程序的最后一行打印每月还款。你可能认为我们会简单地写成：

```java
System.out.println("payment = $" + payment);
```

然而，因为金额存储在`double`类型的变量中，这会打印出数字的所有位数。例如，对于上面的日志，它会打印以下内容：

```text
payment = $1783.6447655625927
```

对于习惯了美元和分的人来说，这种输出看起来相当奇怪。为了这个简单的程序，可以很容易将`double`强制转换为`int`，仅报告还款的美元金额：

```java
System.out.println("payment = $" + (int)payment);
```

大多数试图计算住房贷款还款的人对几分钱并不感兴趣，因此这个程序仍然很有用。在下一节中，我们将学习如何将`double`保留两位小数。

# 3.5 案例研究：抛物线轨迹

现在时候用一个更复杂的示例来整合本章的内容了，这个示例将涉及参数、有返回值的方法、数学计算以及使用`Scanner`对象进行控制台输入。

物理学生经常被要求根据初始速度和相对于水平面的初始角度，来计算抛物体遵循的轨迹。

例如，抛物体可能是一个踢出的足球。给定地球引力，我们想要计算它遵循的路径。为了保持计算合理，我们将忽略空气阻力。

对于这类问题，我们可能想要回答几个问题：

- 抛物体何时到达最高点？
- 它达到了多高？
- 多久回到地面？
- 落地距离发射点有多远？

回答这些问题有多种方法。一种简单的方法是提供一个表格，逐步显示轨迹，标出 x 位置、y 位置和经过的时间。

为了制作这样一个表格，我们需要从用户那里获取三个值：初始速度、相对于水平面的角度，以及生成的表格中要包含的步数。我们可以要求输入米/秒或英尺/秒，但考虑到这是一个物理问题，我们将坚持使用公制并要求输入米。

我们还必须考虑如何指定角度。遗憾的是，大多数处理角度的 Java 方法要求的都是弧度（radians）而不是角度（degrees）。我们可以要求以弧度输入，但这对用户来说非常不方便，他们必须输入角度，然后使用内置方法`Math.toRadians`将转换为弧度。

因此，程序中的交互式控制台部分将如下：

```java
Scanner console = new Scanner(System.in);

System.out.print("velocity (meters/second): ");

double velocity = console.nextDouble();

System.out.print("angle (degrees): ");

double angle = Math.toRadians(console.nextDouble());

System.out.print("number of steps to display: ");

int steps = console.nextInt();
```

注意，对于速度和角度，我们调用了控制台对象的`nextDouble`方法，因为我们允许用户指定任何数字（包括带小数点的），但对于步数，我们调用了`nextInt`，因为表格中的行数需要是整数。

仔细观察这行代码：

```java
double angle = Math.toRadians(console.nextDouble());
```

一些初学者会写成两个独立的步骤：

```java
double angleInDegrees = console.nextDouble();

double angle = Math.toRadians(angleInDegrees);
```

两种方法都是可行且合理的，但请记住你不需要将此操作分为两个独立的步骤。你可以以更紧凑的格式写成单行代码。

一旦从用户那里获取了这些值，我们就可以开始轨迹表格的计算了。首先，我们需要计算速度的 x 分量相对于速度的 y 分量。根据物理学知识，我们知道这些可以如下计算：

```java
double xVelocity = Math.cos(angle);

double yVelocity = velocity * Math.sin(angle);
```

因为我们忽略了空气阻力的可能性，x 速度不会改变。然而，y 速度受到引力的影响。物理学告诉我们，在地球表面引力约为 9.8 m/s²。我们将其定义为一个常量：

```java
static final double GRAVITY = 9.8;
```

抛物体在时间 t 的位移可以使用以下公式计算：

```text
x = xVelocity * t;

y = yVelocity * t - 0.5 * GRAVITY * t * t;
```

我们可以使用循环计算每一步的这些值并显示出来：

```java
for (int i = 0; i <= steps; i++) {

    double t = i * totalTime / steps;

    double x = xVelocity * t;

    double y = yVelocity * t - 0.5 * GRAVITY * t * t;

    System.out.println("t = " + t + ", x = " + x + ", y = " + y);

}
```

# 第3章 参数与对象

```text
set all x, y, and t to 0

for (given number of steps) {

t += timeIncrement;

x += xIncrement;

y = yVelocity * t + 0.5 * ACCELERATION * t * t;

report step # round2(x), round2(y), round2(t)
```

如果表格中的值能够对齐就太好了。为了让数字对齐得整齐，我们必须使用格式化输出，我们将在第4章中讨论。现在，我们至少可以通过用制表符（tab characters）分隔它们让数字按列对齐。记住转义序列`\t`代表单个制表符。

如果我们要有一个带列的表格，那么为表格设置一个表头也是合理的。我们可能还想在表格中包含一行来显示初始条件，即 x、y 和时间都等于 0。因此，我们可以将伪代码扩展为以下 Java 代码：

```java
double x = 0.0;

double y = 0.0;

double t = 0.0;

System.out.println("step\ty\tt\ttime");

System.out.println("0\t0.0\t0.0\t0.0");

for (int i = 1; i <= steps; i++) {

t += timeIncrement;

x += xIncrement;

y = yVelocity * t + 0.5 * ACCELERATION * t * t;

System.out.println("\t" + i + "\t" + round2(x) + "\t" + "\t" + round2(t));

}
```

# 非结构化解决方案

我们可以将所有部分组合成一个完整的程序。让我们先看一个在`main`方法中包含大部分代码的非结构化版本。这个版本在开头还包含了一些新的`println`语句，向用户进行简要介绍：

```java
1 // 这个程序计算抛物体的轨迹。

2

3 import java.util.*; // 用于 Scanner

4

5 public class Project {

6 // 地球加速度常量，单位为米/秒^2

7 public static final double ACCELERATION = -9.81;

8

9

10 public static void main(String[] args) {

11 Scanner console = new Scanner(System.in);

12

13 System.out.println("This program computes the");

14 System.out.println("trajectory of a projectile given");

15 System.out.println("its initial velocity and its");

}
```

# 3.5 案例研究：抛物线轨迹

```java
System.out.println("angle relative to the");

System.out.println("horizontal.");

System.out.println("");

System.out.println("velocity (meters/second)? ");

double velocity = console.nextDouble();

System.out.println("angle (degrees)? ");

double angle = Math.toRadians(console.nextDouble());

System.out.println("number of steps to display? ");

int steps = console.nextInt();

System.out.println("");

double xVelocity = velocity * Math.cos(angle);

double yVelocity = velocity * Math.sin(angle);

double totalTime = -2.0 * yVelocity / ACCELERATION;

double timeIncrement = totalTime / steps;

double xIncrement = xVelocity * timeIncrement;

double x = 0.0;

double y = 0.0;

double t = 0.0;

System.out.println("step\ty\tt\time");

System.out.println("0\t0.0\t0.0\t0.0");

for (int i = 1; i <= steps; i++) {

t += timeIncrement;

x += xIncrement;

y = yVelocity * t + 0.5 * ACCELERATION * t * t;

System.out.println(i + " \t" + round2(x) + " \t" + 

    round2(y) + " \t" + round2(t));

}

public static double round2(double n) {

    return (int) (n * 100.0 + 0.5) / 100.0;

}
```

以下是程序的执行结果：

这个程序根据给定的初始速度和相对于水平面的角度计算抛物体的轨迹。

```text
velocity (meters/second)? 30
angle (degrees)? 50
number of steps to display? 10
```

| step | x | y | time |
|---|---:|---:|---:|
| 0 | 0.0 | 0.0 | 0.0 |
| 1 | 9.03 | 9.69 | 0.47 |
| 2 | 18.07 | 17.23 | 0.94 |
| 3 | 27.71 | 22.61 | 1.41 |
| 4 | 36.14 | 25.84 | 1.87 |
| 5 | 45.17 | 26.92 | 2.34 |
| 6 | 54.21 | 25.84 | 2.81 |
| 7 | 63.24 | 22.61 | 3.28 |
| 8 | 72.28 | 17.23 | 3.75 |
| 9 | 81.31 | 9.69 | 4.22 |
| 10 | 90.35 | 0.0 | 4.69 |

表格中的值能够对齐就太好了。为了让数字对齐得整齐，我们必须使用格式化输出，我们将在第4章中讨论。现在，我们至少可以通过用制表符（tab characters）分隔它们让数字按列对齐。记住转义序列`\t`代表单个制表符。

如果我们要有一个带列的表格，那么为表格设置一个表头也是合理的。我们可能还想在表格中包含一行来显示初始条件，即 x、y 和时间都等于 0。因此，我们可以将伪代码扩展为以下 Java 代码：

```java
double x = 0.0;

double y = 0.0;

double t = 0.0;

System.out.println("step\ty\tt\ttime");

System.out.println("0\t0.0\t0.0\t0.0");

for (int i = 1; i <= steps; i++) {

t += timeIncrement;

x += xIncrement;

y = yVelocity * t + 0.5 * ACCELERATION * t * t;

System.out.println("\t" + i + "\t" + round2(x) + "\t" + "\t" + round2(t));

}
```

# 非结构化解决方案

我们可以将所有部分组合成一个完整的程序。让我们先看一个在`main`方法中包含大部分代码的非结构化版本。这个版本在开头还包含了一些新的`println`语句，向用户进行简要介绍：

```java
1 // 这个程序计算抛物体的轨迹。

2

3 import java.util.*; // 用于 Scanner

4

5 public class Project {

6 // 地球加速度常量，单位为米/秒^2

7 public static final double ACCELERATION = -9.81;

8

9

10 public static void main(String[] args) {

11 Scanner console = new Scanner(System.in);

12

13 System.out.println("This program computes the");

14 System.out.println("trajectory of a projectile given");

15 System.out.println("its initial velocity and its");

}
```

# 3.5 案例研究：抛物线轨迹

```java
System.out.println("angle relative to the");

System.out.println("horizontal.");

System.out.println("");

System.out.println("velocity (meters/second)? ");

double velocity = console.nextDouble();

System.out.println("angle (degrees)? ");

double angle = Math.toRadians(console.nextDouble());

System.out.println("number of steps to display? ");

int steps = console.nextInt();

System.out.println("");

double xVelocity = velocity * Math.cos(angle);

double yVelocity = velocity * Math.sin(angle);

double totalTime = -2.0 * yVelocity / ACCELERATION;

double timeIncrement = totalTime / steps;

double xIncrement = xVelocity * timeIncrement;

double x = 0.0;

double y = 0.0;

double t = 0.0;

System.out.println("step\ty\tt\time");

System.out.println("0\t0.0\t0.0\t0.0");

for (int i = 1; i <= steps; i++) {

t += timeIncrement;

x += xIncrement;

y = yVelocity * t + 0.5 * ACCELERATION * t * t;

System.out.println(i + " \t" + round2(x) + " \t" + 

    round2(y) + " \t" + round2(t));

}

public static double round2(double n) {

    return (int) (n * 100.0 + 0.5) / 100.0;

}
```



以下是程序的执行结果：

这个程序根据给定的初始速度和相对于水平面的角度计算抛物体的轨迹。

```text
velocity (meters/second)? 30
angle (degrees)? 50
number of steps to display? 10
```

| step | x | y | time |
|---:|---:|---:|---:|
| 0 | 0.0 | 0.0 | 0.0 |
| 1 | 9.03 | 9.69 | 0.47 |
| 2 | 18.07 | 17.23 | 0.94 |
| 3 | 27.71 | 22.61 | 1.41 |
| 4 | 36.14 | 25.84 | 1.87 |
| 5 | 45.17 | 26.92 | 2.34 |
| 6 | 54.21 | 25.84 | 2.81 |
| 7 | 63.24 | 22.61 | 3.28 |
| 8 | 72.28 | 17.23 | 3.75 |
| 9 | 81.31 | 9.69 | 4.22 |
| 10 | 90.35 | 0.0 | 4.69 |

表格中的值能够对齐就太好了。为了让数字对齐得整齐，我们必须使用格式化输出，我们将在第4章中讨论。现在，我们至少可以通过用制表符（tab characters）分隔它们让数字按列对齐。记住转义序列 `\t` 代表单个制表符。

如果我们要有一个带列的表格，那么为表格设置一个表头也是合理的。我们可能还想在表格中包含一行来显示初始条件，即 `x`、`y` 和时间都等于 0。因此，我们可以将伪代码扩展为以下 Java 代码：

```java
double x = 0.0;
double y = 0.0;
double t = 0.0;

System.out.println("step\ty\tt\ttime");
System.out.println("0\t0.0\t0.0\t0.0");

for (int i = 1; i <= steps; i++) {
    t += timeIncrement;
    x += xIncrement;
    y = yVelocity * t + 0.5 * ACCELERATION * t * t;

    System.out.println("\t" + i + "\t" + round2(x) + "\t" + "\t" + round2(t));
}
```

## 非结构化解决方案

我们可以将所有部分组合成一个完整的程序。让我们先看一个在 `main` 方法中包含大部分代码的非结构化版本。这个版本在开头还包含了一些新的 `println` 语句，向用户进行简要介绍：

```java
1 // 这个程序计算抛物体的轨迹。

3 import java.util.*; // 用于 Scanner

5 public class Project {
6     // 地球加速度常量，单位为米/秒^2
7     public static final double ACCELERATION = -9.81;

10     public static void main(String[] args) {
11         Scanner console = new Scanner(System.in);

13         System.out.println("This program computes the");
14         System.out.println("trajectory of a projectile given");
15         System.out.println("its initial velocity and its");
    }
}
```

## 3.5 案例研究：抛物线轨迹

```java
System.out.println("angle relative to the");
System.out.println("horizontal.");
System.out.println("");

System.out.println("velocity (meters/second)? ");
double velocity = console.nextDouble();

System.out.println("angle (degrees)? ");
double angle = Math.toRadians(console.nextDouble());

System.out.println("number of steps to display? ");
int steps = console.nextInt();

System.out.println("");

double xVelocity = velocity * Math.cos(angle);
double yVelocity = velocity * Math.sin(angle);
double totalTime = -2.0 * yVelocity / ACCELERATION;
double timeIncrement = totalTime / steps;
double xIncrement = xVelocity * timeIncrement;

double x = 0.0;
double y = 0.0;
double t = 0.0;

System.out.println("step\ty\tt\time");
System.out.println("0\t0.0\t0.0\t0.0");

for (int i = 1; i <= steps; i++) {
    t += timeIncrement;
    x += xIncrement;
    y = yVelocity * t + 0.5 * ACCELERATION * t * t;

    System.out.println(i + " \t" + round2(x) + " \t" +
        round2(y) + " \t" + round2(t));
}

public static double round2(double n) {
    return (int) (n * 100.0 + 0.5) / 100.0;
}
```

以下是程序的执行结果：

这个程序根据给定的初始速度和相对于水平面的角度计算抛物体的轨迹。

```text
velocity (meters/second)? 30
angle (degrees)? 50
number of steps to display? 10
```

| step | x | y | time |
|---:|---:|---:|---:|
| 0 | 0.0 | 0.0 | 0.0 |
| 1 | 9.03 | 9.69 | 0.47 |
| 2 | 18.07 | 17.23 | 0.94 |
| 3 | 27.71 | 22.61 | 1.41 |
| 4 | 36.14 | 25.84 | 1.87 |
| 5 | 45.17 | 26.92 | 2.34 |
| 6 | 54.21 | 25.84 | 2.81 |
| 7 | 63.24 | 22.61 | 3.28 |
| 8 | 72.28 | 17.23 | 3.75 |
| 9 | 81.31 | 9.69 | 4.22 |
| 10 | 90.35 | 0.0 | 4.69 |

表格中的值能够对齐就太好了。为了让数字对齐得整齐，我们必须使用格式化输出，我们将在第4章中讨论。现在，我们至少可以通过用制表符（tab characters）分隔它们让数字按列对齐。记住转义序列 `\t` 代表单个制表符。

如果我们要有一个带列的表格，那么为表格设置一个表头也是合理的。我们可能还想在表格中包含一行来显示初始条件，即 `x`、`y` 和时间都等于 0。因此，我们可以将伪代码扩展为以下 Java 代码：

```java
double x = 0.0;
double y = 0.0;
double t = 0.0;

System.out.println("step\ty\tt\ttime");
System.out.println("0\t0.0\t0.0\t0.0");

for (int i = 1; i <= steps; i++) {
    t += timeIncrement;
    x += xIncrement;
    y = yVelocity * t + 0.5 * ACCELERATION * t * t;

    System.out.println("\t" + i + "\t" + round2(x) + "\t" + "\t" + round2(t));
}
```

## 非结构化解决方案

我们可以将所有部分组合成一个完整的程序。让我们先看一个在 `main` 方法中包含大部分代码的非结构化版本。这个版本在开头还包含了一些新的 `println` 语句，向用户进行简要介绍：

```java
1 // 这个程序计算抛物体的轨迹。

3 import java.util.*; // 用于 Scanner

5 public class Project {
6     // 地球加速度常量，单位为米/秒^2
7     public static final double ACCELERATION = -9.81;

10     public static void main(String[] args) {
11         Scanner console = new Scanner(System.in);

13         System.out.println("This program computes the");
14         System.out.println("trajectory of a projectile given");
15         System.out.println("its initial velocity and its");
    }
}
```

## 3.5 案例研究：抛物线轨迹

```java
System.out.println("angle relative to the");
System.out.println("horizontal.");
System.out.println("");

System.out.println("velocity (meters/second)? ");
double velocity = console.nextDouble();

System.out.println("angle (degrees)? ");
double angle = Math.toRadians(console.nextDouble());

System.out.println("number of steps to display? ");
int steps = console.nextInt();

System.out.println("");

double xVelocity = velocity * Math.cos(angle);
double yVelocity = velocity * Math.sin(angle);
double totalTime = -2.0 * yVelocity / ACCELERATION;
double timeIncrement = totalTime / steps;
double xIncrement = xVelocity * timeIncrement;

double x = 0.0;
double y = 0.0;
double t = 0.0;

System.out.println("step\ty\tt\time");
System.out.println("0\t0.0\t0.0\t0.0");

for (int i = 1; i <= steps; i++) {
    t += timeIncrement;
    x += xIncrement;
    y = yVelocity * t + 0.5 * ACCELERATION * t * t;

    System.out.println(i + " \t" + round2(x) + " \t" +
        round2(y) + " \t" + round2(t));
}

public static double round2(double n) {
    return (int) (n * 100.0 + 0.5) / 100.0;
}
```

以下是程序的执行结果：

这个程序根据给定的初始速度和相对于水平面的角度计算抛物体的轨迹。

```text
velocity (meters/second)? 30
angle (degrees)? 50
number of steps to display? 10
```

| step | x | y | time |
|---:|---:|---:|---:|
| 0 | 0.0 | 0.0 | 0.0 |
| 1 | 9.03 | 9.69 | 0.47 |
| 2 | 18.07 | 17.23 | 0.94 |
| 3 | 27.71 | 22.61 | 1.41 |
| 4 | 36.14 | 25.84 | 1.87 |
| 5 | 45.17 | 26.92 | 2.34 |
| 6 | 54.21 | 25.84 | 2.81 |
| 7 | 63.24 | 22.61 | 3.28 |
| 8 | 72.28 | 17.23 | 3.75 |
| 9 | 81.31 | 9.69 | 4.22 |
| 10 | 90.35 | 0.0 | 4.69 |

表格中的值能够对齐就太好了。为了让数字对齐得整齐，我们必须使用格式化输出，我们将在第4章中讨论。现在，我们至少可以通过用制表符（tab characters）分隔它们让数字按列对齐。记住转义序列 `\t` 代表单个制表符。

如果我们要有一个带列的表格，那么为表格设置一个表头也是合理的。我们可能还想在表格中包含一行来显示初始条件，即 `x`、`y` 和时间都等于 0。因此，我们可以将伪代码扩展为以下 Java 代码：

```java
double x = 0.0;
double y = 0.0;
double t = 0.0;

System.out.println("step\ty\tt\ttime");
System.out.println("0\t0.0\t0.0\t0.0");

for (int i = 1; i <= steps; i++) {
    t += timeIncrement;
    x += xIncrement;
    y = yVelocity * t + 0.5 * ACCELERATION * t * t;

    System.out.println("\t" + i + "\t" + round2(x) + "\t" + "\t" + round2(t));
}
```

## 非结构化解决方案

我们可以将所有部分组合成一个完整的程序。让我们先看一个在 `main` 方法中包含大部分代码的非结构化版本。这个版本在开头还包含了一些新的 `println` 语句，向用户进行简要介绍：

```java
1 // 这个程序计算抛物体的轨迹。

3 import java.util.*; // 用于 Scanner

5 public class Project {
6     // 地球加速度常量，单位为米/秒^2
7     public static final double ACCELERATION = -9.81;

10     public static void main(String[] args) {
11         Scanner console = new Scanner(System.in);

13         System.out.println("This program computes the");
14         System.out.println("trajectory of a projectile given");
15         System.out.println("its initial velocity and its");
    }
}
```

## 3.5 案例研究：抛物线轨迹

```java
System.out.println("angle relative to the");
System.out.println("horizontal.");
System.out.println("");

System.out.println("velocity (meters/second)? ");
double velocity = console.nextDouble();

System.out.println("angle (degrees)? ");
double angle = Math.toRadians(console.nextDouble());

System.out.println("number of steps to display? ");
int steps = console.nextInt();

System.out.println("");

double xVelocity = velocity * Math.cos(angle);
double yVelocity = velocity * Math.sin(angle);
double totalTime = -2.0 * yVelocity / ACCELERATION;
double timeIncrement = totalTime / steps;
double xIncrement = xVelocity * timeIncrement;

double x = 0.0;
double y = 0.0;
double t = 0.0;

System.out.println("step\ty\tt\time");
System.out.println("0\t0.0\t0.0\t0.0");

for (int i = 1; i <= steps; i++) {
    t += timeIncrement;
    x += xIncrement;
    y = yVelocity * t + 0.5 * ACCELERATION * t * t;

    System.out.println(i + " \t" + round2(x) + " \t" +
        round2(y) + " \t" + round2(t));
}

public static double round2(double n) {
    return (int) (n * 100.0 + 0.5) / 100.0;
}
```

以下是程序的执行结果：

这个程序根据给定的初始速度和相对于水平面的角度计算抛物体的轨迹。

```text
velocity (meters/second)? 30
angle (degrees)? 50
number of steps to display? 10
```

| step | x | y | time |
|---:|---:|---:|---:|
| 0 | 0.0 | 0.0 | 0.0 |
| 1 | 9.03 | 9.69 | 0.47 |
| 2 | 18.07 | 17.23 | 0.94 |
| 3 | 27.71 | 22.61 | 1.41 |
| 4 | 36.14 | 25.84 | 1.87 |
| 5 | 45.17 | 26.92 | 2.34 |
| 6 | 54.21 | 25.84 | 2.81 |
| 7 | 63.24 | 22.61 | 3.28 |
| 8 | 72.28 | 17.23 | 3.75 |
| 9 | 81.31 | 9.69 | 4.22 |
| 10 | 90.35 | 0.0 | 4.69 |

表格中的值能够对齐就太好了。为了让数字对齐得整齐，我们必须使用格式化输出，我们将在第4章中讨论。现在，我们至少可以通过用制表符（tab characters）分隔它们让数字按列对齐。记住转义序列 `\t` 代表单个制表符。

如果我们要有一个带列的表格，那么为表格设置一个表头也是合理的。我们可能还想在表格中包含一行来显示初始条件，即 `x`、`y` 和时间都等于 0。因此，我们可以将伪代码扩展为以下 Java 代码：

```java
double x = 0.0;
double y = 0.0;
double t = 0.0;

System.out.println("step\ty\tt\ttime");
System.out.println("0\t0.0\t0.0\t0.0");

for (int i = 1; i <= steps; i++) {
    t += timeIncrement;
    x += xIncrement;
    y = yVelocity * t + 0.5 * ACCELERATION * t * t;

    System.out.println("\t" + i + "\t" + round2(x) + "\t" + "\t" + round2(t));
}
```

## 非结构化解决方案

我们可以将所有部分组合成一个完整的程序。让我们先看一个在 `main` 方法中包含大部分代码的非结构化版本。这个版本在开头还包含了一些新的 `println` 语句，向用户进行简要介绍：

```java
1 // 这个程序计算抛物体的轨迹。

3 import java.util.*; // 用于 Scanner

5 public class Project {
6     // 地球加速度常量，单位为米/秒^2
7     public static final double ACCELERATION = -9.81;

10     public static void main(String[] args) {
11         Scanner console = new Scanner(System.in);

13         System.out.println("This program computes the");
14         System.out.println("trajectory of a projectile given");
15         System.out.println("its initial velocity and its");
    }
}
```

## 3.5 案例研究：抛物线轨迹

```java
System.out.println("angle relative to the");
System.out.println("horizontal.");
System.out.println("");

System.out.println("velocity (meters/second)? ");
double velocity = console.nextDouble();

System.out.println("angle (degrees)? ");
double angle = Math.toRadians(console.nextDouble());

System.out.println("number of steps to display? ");
int steps = console.nextInt();

System.out.println("");

double xVelocity = velocity * Math.cos(angle);
double yVelocity = velocity * Math.sin(angle);
double totalTime = -2.0 * yVelocity / ACCELERATION;
double timeIncrement = totalTime / steps;
double xIncrement = xVelocity * timeIncrement;

double x = 0.0;
double y = 0.0;
double t = 0.0;

System.out.println("step\ty\tt\time");
System.out.println("0\t0.0\t0.0\t0.0");

for (int i = 1; i <= steps; i++) {
    t += timeIncrement;
    x += xIncrement;
    y = yVelocity * t + 0.5 * ACCELERATION * t * t;

    System.out.println(i + " \t" + round2(x) + " \t" +
        round2(y) + " \t" + round2(t));
}

public static double round2(double n) {
    return (int) (n * 100.0 + 0.5) / 100.0;
}
```



# 3.5 案例研究：抛物线轨迹

我们可以将所有部分组合成一个完整的程序。让我们先看一个在`main`方法中包含大部分代码的非结构化版本。这个版本在开头还包含了一些新的`println`语句，向用户进行简要介绍：

```java
// 这个程序计算抛物体的轨迹。

import java.util.*; // 用于 Scanner

public class Project {
    // 地球加速度常量，单位为米/秒^2
    public static final double ACCELERATION = -9.81;

    public static void main(String[] args) {
        Scanner console = new Scanner(System.in);

        System.out.println("This program computes the");
        System.out.println("trajectory of a projectile given");
        System.out.println("its initial velocity and its");
        System.out.println("angle relative to the");
        System.out.println("horizontal.");
        System.out.println("");
        System.out.println("velocity (meters/second)? ");
        double velocity = console.nextDouble();
        System.out.println("angle (degrees)? ");
        double angle = Math.toRadians(console.nextDouble());
        System.out.println("number of steps to display? ");
        int steps = console.nextInt();
        System.out.println("");

        double xVelocity = velocity * Math.cos(angle);
        double yVelocity = velocity * Math.sin(angle);
        double totalTime = -2.0 * yVelocity / ACCELERATION;
        double timeIncrement = totalTime / steps;
        double xIncrement = xVelocity * timeIncrement;

        double x = 0.0;
        double y = 0.0;
        double t = 0.0;

        System.out.println("step\ty\tt\ttime");
        System.out.println("0\t0.0\t0.0\t0.0");

        for (int i = 1; i <= steps; i++) {
            t += timeIncrement;
            x += xIncrement;
            y = yVelocity * t + 0.5 * ACCELERATION * t * t;
            System.out.println(i + " \t" + round2(x) + " \t" + 
                round2(y) + " \t" + round2(t));
        }
    }

    public static double round2(double n) {
        return (int) (n * 100.0 + 0.5) / 100.0;
    }
}
```

以下是程序的执行结果：

这个程序根据给定的初始速度和相对于水平面的角度计算抛物体的轨迹。

```
velocity (meters/second)? 30
angle (degrees)? 50
number of steps to display? 10
```

| step | x | y | time |
|---|---|---|---|
| 0 | 0.0 | 0.0 | 0.0 |
| 1 | 9.03 | 9.69 | 0.47 |
| 2 | 18.07 | 17.23 | 0.94 |
| 3 | 27.71 | 22.61 | 1.41 |
| 4 | 36.14 | 25.84 | 1.87 |
| 5 | 45.17 | 26.92 | 2.34 |
| 6 | 54.21 | 25.84 | 2.81 |
| 7 | 63.24 | 22.61 | 3.28 |
| 8 | 72.28 | 17.23 | 3.75 |
| 9 | 81.31 | 9.69 | 4.22 |
| 10 | 90.35 | 0.0 | 4.69 |

表格中的值能够对齐就太好了。为了让数字对齐得整齐，我们必须使用格式化输出，我们将在第4章中讨论。现在，我们至少可以通过用制表符（tab characters）分隔它们让数字按列对齐。记住转义序列`\t`代表单个制表符。

如果我们我们要有一个带列的表格，那么为表格设置一个表头也是合理的。我们可能还想在表格中包含一行来显示初始条件，即`x`、`y`和时间都等于0。因此，我们可以将伪代码扩展为以下Java代码：

```java
double x = 0.0;
double y = 0.0;
double t = 0.0;

System.out.println("step\ty\tt\ttime");
System.out.println("0\t0.0\t0.0\t0.0");

for (int i = 1; i <= steps; i++) {
    t += timeIncrement;
    x += xIncrement;
    y = yVelocity * t + 0.5 * ACCELERATION * t * t;
    System.out.println("\t" + i + "\t" + round2(x) + "\t" + "\t" + round2(t));
}
```

# 非结构化解决方案

我们可以将所有部分组合成一个完整的程序。让我们先看一个在`main`方法中包含大部分代码的非结构化版本。这个版本在开头还包含了一些新的`println`语句，向用户进行简要介绍：

```java
// 这个程序计算抛物体的轨迹。

import java.util.*; // 用于 Scanner

public class Project {
    // 地球加速度常量，单位为米/秒^2
    public static final double ACCELERATION = -9.81;

    public static void main(String[] args) {
        Scanner console = new Scanner(System.in);

        System.out.println("This program computes the");
        System.out.println("trajectory of a projectile given");
        System.out.println("its initial velocity and its");
        System.out.println("angle relative to the");
        System.out.println("horizontal.");
        System.out.println("");
        System.out.println("velocity (meters/second)? ");
        double velocity = console.nextDouble();
        System.out.println("angle (degrees)? ");
        double angle = Math.toRadians(console.nextDouble());
        System.out.println("number of steps to display? ");
        int steps = console.nextInt();
        System.out.println("");

        double xVelocity = velocity * Math.cos(angle);
        double yVelocity = velocity * Math.sin(angle);
        double totalTime = -2.0 * yVelocity / ACCELERATION;
        double timeIncrement = totalTime / steps;
        double xIncrement = xVelocity * timeIncrement;

        double x = 0.0;
        double y = 0.0;
        double t = 0.0;

        System.out.println("step\ty\tt\ttime");
        System.out.println("0\t0.0\t0.0\t0.0");

        for (int i = 1; i <= steps; i++) {
            t += timeIncrement;
            x += xIncrement;
            y = yVelocity * t + 0.5 * ACCELERATION * t * t;
            System.out.println(i + " \t" + round2(x) + " \t" + 
                round2(y) + " \t" + round2(t));
        }
    }

    public static double round2(double n) {
        return (int) (n * 100.0 + 0.5) / 100.0;
    }
}
```

以下是程序的执行结果：

这个程序根据给定的初始速度和相对于水平面的角度计算抛物体的轨迹。

```
velocity (meters/second)? 30
angle (degrees)? 50
number of steps to display? 10
```

| step | x | y | time |
|---|---|---|---|
| 0 | 0.0 | 0.0 | 0.0 |
| 1 | 9.03 | 9.69 | 0.47 |
| 2 | 18.07 | 17.23 | 0.94 |
| 3 | 27.71 | 22.61 | 1.41 |
| 4 | 36.14 | 25.84 | 1.87 |
| 5 | 45.17 | 26.92 | 2.34 |
| 6 | 54.21 | 25.84 | 2.81 |
| 7 | 63.24 | 22.61 | 3.28 |
| 8 | 72.28 | 17.23 | 3.75 |
| 9 | 81.31 | 9.69 | 4.22 |
| 10 | 90.35 | 0.0 | 4.69 |

表格中的值能够对齐就太好了。为了让数字对齐得整齐，我们必须使用格式化输出，我们将在第4章中讨论。现在，我们至少可以通过用制表符（tab characters）分隔它们让数字按列对齐。记住转义序列`\t`代表单个制表符。

如果我们我们要有一个带列的表格，那么为表格设置一个表头也是合理的。我们可能还想在表格中包含一行来显示初始条件，即`x`、`y`和时间都等于0。因此，我们可以将伪代码扩展为以下Java代码：

```java
double x = 0.0;
double y = 0.0;
double t = 0.0;

System.out.println("step\ty\tt\ttime");
System.out.println("0\t0.0\t0.0\t0.0");

for (int i = 1; i <= steps; i++) {
    t += timeIncrement;
    x += xIncrement;
    y = yVelocity * t + 0.5 * ACCELERATION * t * t;
    System.out.println("\t" + i + "\t" + round2(x) + "\t" + "\t" + round2(t));
}
```



`t += timeIncrement;`

`x += xIncrement;`

`y = yVelocity * t + 0.5 * ACCELERATION * t * t;`

`System.out.println(i + " \t" + round2(x) + " \t" + round2(y) + " \t" + round2(t));`

`public static double round2(double n) { return (int) (n * 100.0 + 0.5) / 100.0; }`

以下是程序的执行结果：

这个程序根据给定的初始速度和相对于水平面的角度计算抛物体的轨迹。

```
velocity (meters/second)? 30
angle (degrees)? 50
number of steps to display? 10
```

| step | x | y | time |
|---|---|---|---|
| 0 | 0.0 | 0.0 | 0.0 |
| 1 | 9.03 | 9.69 | 0.47 |
| 2 | 18.07 | 17.23 | 0.94 |
| 3 | 27.71 | 22.61 | 1.41 |
| 4 | 36.14 | 25.84 | 1.87 |
| 5 | 45.17 | 26.92 | 2.34 |
| 6 | 54.21 | 25.84 | 2.81 |
| 7 | 63.24 | 22.61 | 3.28 |
| 8 | 72.28 | 17.23 | 3.75 |
| 9 | 81.31 | 9.69 | 4.22 |
| 10 | 90.35 | 0.0 | 4.69 |

表格中的值能够对齐就太好了。为了让数字对齐得整齐，我们必须使用格式化输出，我们将在第4章中讨论。现在，我们至少可以通过用制表符（tab characters）分隔它们让数字按列对齐。记住转义序列`\t`代表单个制表符。

如果我们我们要有一个带列的表格，那么为表格设置一个表头也是合理的。我们可能还想在表格中包含一行来显示初始条件，即`x`、`y`和时间都等于0。因此，我们可以将伪代码扩展为以下Java代码：

```java
double x = 0.0;
double y = 0.0;
double t = 0.0;
System.out.println("step\ty\tt\ttime");
System.out.println("0\t0.0\t0.0\t0.0");
for (int i = 1; i <= steps; i++) {
    t += timeIncrement;
    x += xIncrement;
    y = yVelocity * t + 0.5 * ACCELERATION * t * t;
    System.out.println("\t" + i + "\t" + round2(x) + "\t" + "\t" + round2(t));
}
```

## 自测题

某些程序是交互式的，并对用户的输入做出响应。这些程序应该向用户发送一条消息（也称为提示，prompt），请求用户输入。

Java有一个`Scanner`类可以从键盘读取输入。`Scanner`可以从输入源读取各种输入（也称为标记，tokens）。它可以一次读取一个标记，也可以一次性读取一整行。

## 自测题

### 第 3.1 节：参数

1. 以下代码的输出是什么？

```java
public class Odds {
    public static void main(String[] args) {
        printOdds(3);
        printOdds(17 / 2);
        int x = 25;
        printOdds(37 - x + 1);
    }

    public static void printOdds(int n) {
        for (int i = 1; i <= n; i++) {
            int odd = 2 * i - 1;
            System.out.print(odd + " ");
        }
        System.out.println();
    }
}
```

2. 下列程序的输出是什么？

```java
public class Weird {
    public static void main(String[] args) {
        int number = 8;
        halfTheFun(11);
        halfTheFun(2 - 3 + 8);
        halfTheFun(number);
        System.out.println("number = " + number);
    }

    public static void halfTheFun(int number) {
        for (int count = 1; count <= number; count++) {
            System.out.print(count + " ");
        }
        System.out.println();
    }
}
```

## 第 3 章 参数与对象简介

3. 下列程序的输出是什么？

```java
public class Params1 {
    public static void main(String[] args) {
        String one = "two";
        String two = "three";
        String three = "1";
        int number = 20;
        sentence(one, two, 3);
        sentence(two, three, 14);
        sentence(three, three, number + 1);
        sentence(three, two, 1);
        sentence("eight", three, number / 2);
    }

    public static void sentence(String three, String one, int number) {
        System.out.println(one + " " + three + " = " + " " + (number + 2));
    }
}
```

（注：原始 OCR 识别在打印语句中使用了 "times"，可能根据参数列表已更正为 "three"）

4. 下列程序的输出是什么？

```java
public class Mystery {
    public static void main(String[] args) {
        String whom = "her";
        String who = "him";
        String it = "who";
        String he = "it";
        String she = "whom";
        sentence(he, she, it);
        sentence(she, he, who);
        sentence(who, she, who);
        sentence(it, "stu", "boo");
        sentence(it, whom, who);
    }

    public static void sentence(String she, String who, String whom) {
        System.out.println(who + " " + whom + " and " + whom + " like " + she);
    }
}
```

5. 写一个名为`printStrings`的方法，接受一个`String`和重复次数作为参数，并按照指定的次数打印该`String`。例如调用：

```java
printStrings("abc", 5)
```

## 自测题

将打印以下输出：

6. `System.out.println`命令可以用于许多不同类型的值，例如整数或双浮点数。这种方法的术语是什么？

### 第 3.2 节：返回值的方法

7. 下列程序有什么错误？

```java
public class Temperature {
    public static void main(String[] args) {
        double temp = 98.6;
        double tempc = 0.0;
        ftoc(temp, tempc);
        System.out.println("Body in C is: " + tempc);
    }

    // 将华氏温度转换为摄氏度
    public static void ftoc(double temp, double tempc) {
        tempc = (temp - 32) * 5 / 9;
    }
}
```

8. 求以下表达式的值：

- `Math.abs(-1.6)`
- `Math.abs(2 + -4)`
- `Math.pow(6, 2)`
- `Math.pow(5 / 2, 6)`
- `Math.ceil(9.1)`
- `Math.ceil(115.8)`
- `Math.max(7, 4)`
- `Math.min(8, 3 + 2)`
- `Math.min(-2, -5)`
- `Math.sqrt(64)`
- `Math.sqrt(76 + 45)`
- `100 + Math.log10(100)`
- `13 + Math.abs(-7) - Math.pow(2, 3) + 5`
- `Math.sqrt(16) * Math.max(Math.abs(-5), Math.abs(-3))`
- `7 - 2 + Math.log10(100) + Math.pow(E, 5)`
- `Math.max(18 - 5 + Math.ceil(4 * 3))`

9. 下列程序的输出是什么？

```java
public class Mystery {
    public static void main(String[] args) {
        int x = 1, y = 2, z = 3;
        z = mystery(x, z, y);
        System.out.println("x = " + x + " y = " + y + " z = " + z);
        x = mystery(z, z, x);
        System.out.println("x = " + x + " y = " + y + " z = " + z);
    }

    public static int mystery(int z, int x, int y) {
        x = 2 * y + z;
        y = x - 1;
        System.out.println(x + " " + y);
        return x;
    }
}
```

10. 写一个接受三个整数并返回其中最小值的方法，例如调用`min(3, -2, 7)`返回 -2，而调用`min(19, 27, 6)`返回 6。使用`Math.min`编写你的解决方案。

11. 写一个名为`countQuarters`的方法，接受一个整数分作为参数，并返回对应的硬币数量。不要计算美元，因为那些是以钞形式发放的。例如`countQuarters(64)`返回 2，因为 2 个硬币是 50 分，还剩 14 分。`countQuarters(127)`返回 3，因为取去 12 美元后，剩余 78 分。

### 第 3.3 节：使用对象

12. 假设声明了以下变量：

```java
String str1 = "Q.E.D.";
String str2 = "Fortune";
String str3 = "Sirius Cybernetics"
```

求以下表达式的值：

- `str1.length()`
- `str2.length()`
- `str1.toLowerCase()`
- `str2.toUpperCase()`
- `str1.substring(2, 4)`
- `str2.substring(10, 14)`
- `str1.indexOf("D")`
- `str1.indexOf(". ")`
- `str2.indexOf("fortune")`
- `str3.indexOf("X")`
- `str2 + str3.charAt(17)`
- `str3.substring(9, str3.indexOf("e"))`
- `str3.substring(7, 12)`
- `str2.toLowerCase().substring(9, 13) + str3.substring(18, str3.length())`

13. 根据以下字符串：

```java
String quote = "Four score and seven years ago";
```

什么表达式产生新字符串 "SCORE"？什么表达式产生 "four years"？

## 自测题

14. 执行以下代码后，名为`p1`、`p2`和`p3`的点（Points）的 x 坐标分别是多少？

```java
Point p1 = new Point(17, 9);
Point p2 = new Point(4, -1);
Point p3 = p2;
p1.translate(3, 1);
p2.x = 50;
p3.translate(-4, 5);
```

15. 下列程序的输出是什么？

```java
import java.awt.*;

public class PointMystery {
    public static void main(String[] args) {
        Point p1 = new Point(5, 2);
        Point p2 = new Point(-3, 6);
        silly(p1);
        silly(p2);
        Point p3 = p1;
        silly(p3);
        System.out.println("(" + p1.x + ", " + p1.y + ")");
        System.out.println("(" + p2.x + ", " + p2.y + ")");
        System.out.println("(" + p3.x + ", " + p3.y + ")");
    }

    public static void silly(Point p) {
        int temp = p.x;
        p.x = p.y;
        p.y = temp;
    }
}
```

### 第 3.4 节：交互式程序

16. 在使用`Scanner`读取用户的程序中，如果用户输入以下行：

```
Hello there. 1 + 2 is 3 and 1.5 squared is 2.25!
```

会被分成多少个标记？`Scanner`可以合法地将每个标记读取为什么类型？

17. 给定以下代码片段：

```java
Scanner console = new Scanner(System.in);
System.out.print("How much money do you have? ");
double money = console.nextDouble();
```

描述用户输入以下每个值时发生的情况。如果代码运行成功，描述存储在变量`money`中的值。

- `34.50`
- `6`
- `25.00`
- 无

18. 编写 Java 代码从用户处读取一个整数，然后打印该数乘以 2。你可以假设用户输入有效的整数。

19. 编写 Java 代码，提示用户输入一个短语和重复次数，然后按照该次数打印该短语。以下与用户对话的示例：

```
What is your name? Robertson.
How many times should I repeat it? 3
```

```
His name is Robertson.
His name is Robertson.
His name is Robertson.
```

## 练习

1. 写一个名为`printNumbers`的方法，接受一个数字作为参数，并打印从 1 到最大的每个数字，用方括号括起来。例如，考虑以下调用：

```java
printNumbers(15);
printNumbers(5);
```

这些调用应该产生以下输出：

```
[1] [2] [3] [4] [5] [6] [7] [8] [9] [10] [11] [12] [13] [14] [15]
[1] [2] [3] [4] [5]
```

你可以假设传递给`printNumbers`的值大于 1。

2. 写一个名为`powersOf2`的方法，接受一个数字作为参数，并打印从 2^0 (1) 到最大幂的每个二次幂。例如，考虑以下调用：

```java
powersOf2(3);
powersOf2(10);
```

这些调用应该产生以下输出：

```
2 4 8
2 4 8 16 32 64 128 256 512 1024
```




你可以假设传递给 `powersOf2` 的值大于或等于 0。（`Math` 类可能帮助你解决这个问题。如果你使用它，你可能需要将其结果从 `double` 强制转换为 `int`，以免在输出的每个数字后面看到 `.0`。此外，你可以使用 `Math` 类编写这个程序吗？）

## 练习

### 3. `powersOfN`

写一个 `powersOfN` 方法，接受一个基和一个指数作为参数，并打印从基的第 1 次幂到最大幂的每个幂。例如，考虑以下调用：

```java
powersOfN(4, 3);
```

```java
printPowersOfN(5, 6);

printPowersOfN(-2, 8);
```

这些调用应该产生以下输出：

```text
1 14 64

5 25 125 625 3125 15625

1 -2 4 -8 16 32 64 -128 256
```

你可以假设传递给 `printPowersOfN` 的指数值大于或等于 0。（`Math` 类可能帮助你解决这个问题。如果你使用它，你可能需要将结果从 `double` 强制转换为 `int`，这样你的输出中每个数字后面就不会出现 `.0`。你可以在不使用 `Math` 类的情况下编写这个程序吗？）

### 4. `largerAbsVal`

写一个名为 `largerAbsVal` 的方法，它接受两个整数作为参数并返回两个绝对值中较大的一个。调用 `largerAbsVal(11, 2)` 将返回 11，调用 `largerAbsVal(4, -5)` 将返回 5。

### 5. `largerAbsVal` 的三参数变体

编写上一个练习中 `largerAbs` 方法的变体，它接受三个整数作为参数并返回它们三个绝对值中最大的一个。例如，调用 `largerAbsVal(7, -2, -11)` 将返回 11，调用 `largerAbsVal(-4, 5, 2)` 将返回 5。

### 6. `quadratic`

写一个名为 `quadratic` 的方法，用于求解二次方程并打印其结果。记住，二次方程是关于 `x` 的形式为 `ax² + bx + c = 0` 的多项式。求解二次方程的公式为：

$$
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$$

以下是一些示例及其根：

```text
x² - 7x + 12 = 0; x = 4, 3

x² + 3x - 2 = 0; x = -2, 1
```

你的方法应该接受 `a`、`b` 和 `c` 作为参数并打印方程的根。你可以假设方程有两个根，尽管在数学上这并不总是如此。

### 7. `padString`

写一个名为 `padString` 的方法，它接受两个参数：一个字符串和一个表示长度的整数。该方法应该用空格填充字符串，直到它的长度等于给定长度。

例如，`padString("hello", 8)` 应该返回 `"hello   "`。（这个方法在尝试水平打印行时有用。）

如果字符串的长度至少等于长度参数，你的方法应该返回原始字符串。例如，`padString("congratulations", 10)` 应返回 `"congratulations"`。

### 8. `verticalReverse`

写一个名为 `verticalReverse` 的方法，它接受一个字符串作为参数并反向打印字符串的每个字母。例如，调用 `verticalReverse("hello!")` 应该产生以下输出：

```text
h
e
y
```

### 9. `printReverse`

写一个名为 `printReverse` 的方法，它接受一个字符串作为参数并反向打印字符串的字符。例如，调用 `printReverse("hello!")` 应该打印 `"!olleH"`。如果传递空字符串，没有输出。

# 第 3 章 参数与对象

### 10. `swapPoints`

写一个名为 `swapPoints` 的方法，它接受两个 `Point` 对象作为参数并交换它们的值。考虑以下调用 `swapPoints` 的示例代码：

```java
Point p1 = new Point(5, 2);
Point p2 = new Point(-3, 6);

swapPoints(p1, p2);

System.out.println("(" + p1.x + ", " + p1.y + ")");
System.out.println("(" + p2.x + ", " + p2.y + ")");
```

上述代码产生的输出应该是：

```text
(-3, 6)

(5, 2)
```

### 11. 反向打印全名

写 Java 代码，提示用户输入全名，然后反向打印名字（例如，姓在前）。这里有一个与用户的交互示例：

```text
请输入全名：Sammy
你的名字反向是 Jankis
```

## 编程项目

1. 写一个输出圣诞树的程序。它应该有一个两个的方法：树的段数和每个段的高度。例如，这里显示的左树有三个高度为 4 的段，右树有两个高度为 5 的段：

2. 某银行提供 6.5% 的年利率。创建一个表格，显示在 25 年内将积累多少资金；假设初始投资为 `$1000`，并且每年存入 `$100`。你的表格应该指示每年的当前余额、利息和新余额。

3. 写一个程序，根据《圣诞十二夜》这首歌显示每天收到的礼物总数。

## 表格 3.6

| 天数 | 收到的礼物 | 总礼物数 |
| --- | --- | --- |
| 1 | 1 | 1 |
| 2 | 2 | 3 |
| 3 | 3 | 6 |
| 4 | 4 | 10 |
| 5 | 5 | 15 |
| 6 | 6 | 21 |
| 7 | 7 | 28 |
| 8 | 8 | 36 |
| 9 | 9 | 45 |
| 10 | 10 | 55 |
| 11 | 11 | 66 |
| 12 | 12 | 78 |

写一个程序，根据《圣诞十二夜》这首歌，如表格 3.6 所示显示每天收到的礼物总数。

写一个程序，计算地球上两点之间的距离。地球半径为 6371 km。使用余弦定理：

$$
d = r \cdot \arccos(\sin(\phi_1)\sin(\phi_2) + \cos(\phi_1)\cos(\phi_2)\cos(\Delta\lambda))
$$

其中 `φ₁`、`φ₂` 是纬度，`Δλ` 是经度差。你的程序应该接受纬度和经度并输出以公里为单位的距离。

# 补充 3G 图形（可选）

从这个位置开始，y 值增加。例如，假设你构造了一个宽度为 200 像素、高度为 100 像素的 `DrawingPanel`。左上角的坐标为 (0, 0)，右下角的坐标为 (199, 99)。

![坐标示意图](img/aea18896a4bced58de45f29f5a93f7b3_201_0.png)

(0, 0) (199, 99)

这起初可能会让人困惑，因为你可能习惯了 y 值向下移动而减小的坐标系。不过，你很快就会掌握它的。

# 绘制线条和形状

那么，你到底如何画东西呢？要绘制形状和线条，你不需要直接与 `DrawingPanel` 通信，而是与一个类型为 `Graphics` 的相关对象通信。将 `DrawingPanel` 想象成画布，将 `Graphics` 对象想象成画笔。`DrawingPanel` 类有一个名为 `getGraphics` 的方法，它返回其 `Graphics` 对象的引用。

最简单的绘制命令之一是 `drawLine`，它接受四个整数参数。例如：

```java
g.drawLine(<x1>, <y1>, <x2>, <y2>);
```

这会从点 (x1, y1) 绘制一条线到点 (x2, y2)。以下是一个将这些部分组合的示例程序：

```java
// 在 DrawingPanel 上画一条线。

import java.awt.*;

// for graphics

public class DrawLine {

    public static void main(String[] args) {

        // 创建绘制面板

        DrawingPanel panel = new DrawingPanel(200, 100);

        // 使用 Graphics 画笔在面板上画一条线

        Graphics g = panel.getGraphics();

        g.drawLine(25, 75, 175, 25);

    }

}
```

当你运行此程序时，会出现图 3.1 所示的窗口。它不像之前的章节那样是控制台上的文本，但我们将称为程序的“输出”。

（Java 可以运行在各种操作系统上。本章中图形输出的截图在外观上略有不同，以反映它们是在不同的环境下拍摄的。）

## 3G.1 图形介绍

![DrawLine 的输出](img/aea18896a4bced58de45f29f5a93f7b3_202_0.png)

图 3.1：`DrawLine` 的输出

`main` 方法中的第一个语句构造了一个宽度为 200、高度为 100 的 `DrawingPanel`。一旦构造完成，窗口就会出现在屏幕上。第二个语句从 (25, 75) 绘制一条线到 (175, 25)。第一个点在窗口的左下部分（从左侧偏移 25，从顶部向下偏移 75）。第二个点在右上角（从左侧偏移 175，从顶部向下偏移 25）。注意这几行代码：

```java
Graphics g = panel.getGraphics();
g.drawLine(25, 75, 175, 25);
```

你可能会奇怪为什么不能直接使用：

```java
panel.drawLine(25, 75, 175, 25); // 这是非法的
```

问题在于此程序中涉及两个不同的对象：`DrawingPanel` 本身（画布）和与面板关联的 `Graphics` 对象（画笔）。面板不知道如何画线；只有 `Graphics` 对象知道如何这样做。在给出命令时，必须小心确保你正在与正确的对象通信。

这可能会让人困惑，但在 Java 程序中这是很常见的现象。事实上，在一个典型的 Java 程序中，有数百（甚至数千）对象相互交互。这些交互与人与人的交互相似。如果你想安排会议：忙碌的高管可能会告诉你：“去和你的秘书谈这件事。”或者如果你在问困难的问题，某人可能会告诉你：“去找我的律师谈。”在这种情况下，`DrawingPanel` 不知道怎么画，所以如果它会说话，它会说：“去找我的 `Graphics` 对象谈。”

不将其存储在变量中直接使用 `Graphics` 对象也是合法的：

```java
panel.getGraphics().drawLine(25, 75, 175, 25); // 也是法的
```

但你通常想向 `Graphics` 对象发送多条命令，因此给它起个名字并存储在变量中更方便。

# 补充 3G 图形（可选）

让我们来看一个更复杂的例子：

```java
// 绘制三条线组成一个三角形。

import java.awt.*;

public class DrawLine2 {

    public static void main(String[] args) {

        DrawingPanel panel = new DrawingPanel(200, 100);

        // 在面板上画一个三角形

        Graphics g = panel.getGraphics();

        g.drawLine(25, 75, 100, 25);

        g.drawLine(100, 25, 175, 75);

        g.drawLine(25, 75, 175, 75);

    }

}
```

该程序绘制了三条不同的线形成一个三角形，如图 3.2 所示。线条绘制在三个点之间。在左下角有点 (25, 75)。在顶部中间有点 (100, 25)。在右下角有点 (175, 75)。各种 `drawLine` 调用连接了这三个点。

![三角形示意图](img/aea18896a4bced58de45f29f5a93f7b3_203_0.png)

`Graphics` 对象也有绘制特定形状的方法。例如，你可以使用 `drawRect` 方法绘制矩形：

```java
g.drawRect(<x>, <y>, <width>, <height>);
```




这绘制了一个左上角坐标为`(x, y)`，宽度和高度指定的矩形。另一个是你想画一个圆，或者更通用地说是一个椭圆。但如何指定它的位置和大小呢？这被称为圆或椭圆的“边界矩形”。Java 将绘制矩形内最大的椭圆：

```java
g.drawOval(<x>, <y>, <width>, <height>);
```

# 3G.1 图形介绍

绘制了左上角坐标为`(x, y)`的矩形内最大的椭圆。注意传递给`drawRect`和`drawOval`的前两个值是坐标，后两个值是宽度和高度。例如，这里有一个绘制两个矩形、两个椭圆的短程序：

```java
// 绘制几个形状。

import java.awt.*;

public class DrawShapes {

    public static void main(String[] args) {

        DrawingPanel panel = new DrawingPanel(200, 100);

        Graphics g = panel.getGraphics();

        g.drawRect(25, 50, 20, 20);

        g.drawOval(50, 25, 20, 20);

        g.drawOval(150, 50, 40, 20);

    }

}
```

图 3.3 显示了程序的输出。

![](img/aea18896a4bced58de45f29f5a93f7b3_204_0.png)

第一个矩形的左上角坐标为`(25, 50)`。它的宽度和高度均为 20，所以这是一个正方形。它的右下角坐标将`(45, 70)`，即比左上角的`(x, y)`坐标多 20。程序还绘制了一个左上角坐标为`(150, 10)`的矩形，宽度为 40，高度为 20（比它宽）。第一个椭圆的边界矩形左上角坐标为`(50, 25)`，宽度和高度均为 20。换句话说，是一个圆。第二个椭圆的边界矩形左上角坐标为`(150, 50)`，宽度为 40，高度为 20（是一个更宽的椭圆）。

有时你不想用特定颜色绘制形状的轮廓。`drawRect`和`drawOval`方法的变体可以完全实现这一点：绘制矩形或椭圆并用当前颜色填充（默认为黑色）。让我们把上程序中的两个调用改为“填充”操作：

# 补充 3G 图形（可选）

```java
// 绘制并填充几个形状。

import java.awt.*;

public static void main(String[] args) {

    DrawingPanel panel = new DrawingPanel(200, 100);

    Graphics g = panel.getGraphics();

    g.fillRect(50, 25, 20, 20);

    g.drawRect(150, 10, 40, 20);

    g.drawOval(50, 25, 20, 20);

    g.fillOval(150, 50, 40, 20);

}
```

现在我们得到了图 3.4 所示的输出。

![](img/aea18896a4bced58de45f29f5a93f7b3_205_0.png)

# 颜色

之前程序绘制的所有形状和线条都是黑色的，所有面板都有白色背景。这些是默认颜色，你可以根据需要更改面板的背景颜色，也可以根据需要多次更改`Graphics`对象所使用的颜色。要更改这些颜色，你使用`Color`类，它是`java.awt`包的一部分。

有许多预定义的颜色可以供引用。它们被定义为类常量（就像第 2 章中使用的常量一样）。这些常量的名称全部大写，且自俗易懂。要引用其中一个，你必须在它前面加上类名和点，例如`Color.GREEN`或`Color.BLUE`。预定义常量列在表 3 中。

如之前提到的，`DrawingPanel`对象有一个方法，可以更改覆盖整个面板的背景颜色：

```java
<panel>.setBackground(<color>);
```

同样，`Graphics`对象也有一个方法，可以更改形状和线条的绘制颜色：

```java
g.setColor(<color>);
```

## 3G.1 图形引论

| 表 3.8 颜色。 | | |
| :--- | :--- | :--- |
| `Color.BLACK` | `Color.GREEN` | `Color.RED` |
| `Color.BLUE` | `Color.LIGHT_GRAY` | `Color.WHITE` |
| `Color.CYAN` | `Color.MAGENTA` | `Color.YELLOW` |
| `Color.DARK_GRAY` | `Color.ORANGE` | |
| `Color.GRAY` | `Color.PINK` | |

调用`setColor`就像将画笔浸入不同颜色的油漆。从该点起，所有的绘制和填充都将使用指定的颜色进行。例如，这里是之前程序的另一个版本，它使用了颜色（浅蓝色）背景色，并用白色而不是黑色填充圆形和方形：

```java
// 使用不同的颜色绘制并填充形状。

import java.awt.*;

public class Shapes {

   public static void main(String[] args) {

     DrawingPanel panel = new DrawingPanel(200, 100);

     panel.setBackground(Color.CYAN);

     Graphics g = panel.getGraphics();

     g.drawRect(150, 10, 40, 20);

     g.drawOval(50, 25, 20, 20);

     g.setColor(Color.WHITE);

     g.fillOval(150, 50, 40, 20);

     g.fillRect(25, 50, 20, 20);

   }

}
```

它产生了图 3.5 所示的输出。

![](img/aea18896a4bced58de45f29f5a93f7b3_206_0.png)

## 补充 3G 图形（可选）

注意，你告诉面板设置背景颜色，而你告诉`Graphics`对象设置前景颜色。原因在于背景颜色是整个窗口的属性，而前景颜色只影响你随后绘制的特定形状。

同样注意，调用的顺序已经重新排列。两个绘制命令首先出现，然后是改变颜色为白色的`setColor`调用，然后是两个填充命令。这确保了绘制是在黑色内部进行的，而填充是用白色完成的。操作顺序在这些绘制程序中非常重要，因此你必须跟踪当前的颜色，以便在绘制或填充某些内容时提供新的命令。

在之前的每个示例中，我们为绘制和填充命令使用了简单的常量，但也可以使用表达式。例如，假设我们保持 200 像素宽、100 像素高的`drawingPanel`尺寸，并且想要产生一组四个矩形的对角线，从左上角延伸到右下角，每个矩形内部都有白色圆形。也就是说，我们想要产生图 3.6 所示的输出。

![](img/aea18896a4bced58de45f29f5a93f7b3_207_0.png)

200 的总宽度和 100 的总高度被分为四个矩形，这意味着它们的宽度都为 50 像素，高度为 25 像素。因此，四个矩形的宽度和高度值是相同的，但它们的左上角位置是不同的。第一个矩形的左上角在`(0, 0)`，第二个在`(50, 25)`，第三个在`(100, 50)`，第四个在`(150, 75)`。我们需要编写代码来生成这些不同的坐标。

这是一个使用循环的极佳地方。使用第 2 章中引入的技巧，我们可以创建一个表格并为坐标开发一个公式。在这种情况下，循环从 0 开始比从 1 开始更容易，这在绘制程序中通常是如此。以下是一个生成预期输出的良好尝试程序：

- 1 // 使用`for`循环绘制圆形（有缺陷的版本）

```java
import java.awt.*;
```

## 3G.1 图形引论

```java
public static void main(String[] args) {

    DrawingPanel panel = new DrawingPanel(200, 100);

    panel.setGradientPanel(Color.CYAN);

    Graphics g = panel.getGraphics();

    for (int i = 0; i < 4; i++) {

        g.drawRect(i * 50, i * 25, 50, 25);

        g.setColor(Color.WHITE);

        g.fillOval(i * 50, i * 25, 50, 25);

    }

}
```

它产生了图 3.7 所示的输出。

![](img/aea18896a4bced58de45f29f5a93f7b3_208_0.png)

坐标和大小是正确的，但颜色不是。我们得到的不是四个带有白色圆形的矩形，而是得到了一个黑色矩形和三个白色矩形。这是因为我们在循环内部只调用了一次`setColor`。初始颜色将设置为黑色，一旦我们调用`setColor`将颜色改为白色，随后的每个绘制和填充命令都将用白色完成。

还可以创建`Color`对象，而不是使用`Color`类提供的常量颜色。红、绿、蓝分量应该是 0 到 255 之间的整数值。值越高，颜色越深。在搜索引擎中搜索“RGB 表”可以找到常用颜色。以下程序演示了自定义颜色的使用，并产生了从黑色到白的渐变：

```java
// 从黑色到白的渐变

class DrawingGradient extends JPanel {

    static final int RECTS = 32;

    public static void main(String[] args) {

        DrawingPanel panel = new DrawingPanel(256, 256);

        panel.setBackground(new Color(255, 128, 0)); // 橙色

        Graphics g = panel.getGraphics();

        // 从左上到右下

        for (int i = 0; i < RECTS; i++) {

            int shift = i * 256 / RECTS;

            g.setColor(new Color(shift, shift, shift));

            g.fillRect(shift, shift, 20, 20);

        }

    }

}
```

产生了图 3.8 所示的输出。

![](img/aea18896a4bced58de45f29f5a93f7b3_210_png)

## 文字与字体

另一个值得提到的绘制命令可以用于在绘制中包含文本。`Graphics`对象的`drawString`方法：

```java
g.drawString(message, x, y);
```

绘制给定的字符串，其左下角位于坐标`(x, y)`。这与我们用于`DrawRect`的约定略有不同。我们指定了左上角的坐标。在这里我们指定了左下角的坐标。默认情况下，文字的高度约为 10 像素。以下是一个示例程序，使用循环绘制特定的字符串 10 次，每次向右缩进 5 像素，并从顶部移动 10 像素。

```java
1 // 多次绘制消息。

import java.awt.*;

public class DrawString1 {

    public static void main(String[] args) {

        DrawingPanel panel = new DrawingPanel(200, 100);

        panel.setBackground(Color.YELLOW);
```

## 补充 3G 图形（可选）

```java
10 Graphics = panel.getGraphics();

11 for (int i = 0; i < 10; i++) {

12     g.drawString("There is no place like home",

13     i * 5, 10 + i * 10);

14 }

15 

16 }
```

它产生了如图 3.9 所示的输出。

![](img/aea18896a4bced58de45f29f5a93f7b3_211_0.png)

如果你想更改屏幕文本绘制的样式或大小，可以使用`Graphics`对象的`setFont`方法：

```java
g.setFont(<font>);
```

这会更改绘制字符串时文本的大小和样式。`setFont`的参数是一个`Font`对象。`Font`对象通过传递三个参数来构造：作为字符串的字体名称、它的样式（如粗体或斜体）以及作为整数的尺寸。例如：

```java
new Font(<name>, <style>, <size>);
```

常见的字体样式（如粗体）在`Font`类中以常量形式实现。可用的常量和常用的字体名称如表 3.9 和 3.10 所示。

### 表 3.9 Font 类的常用常量

| 常量 | 显示 |
|---|---|
| `Font.BOLD` | 粗体文本 |
| `Font.ITALIC` | 斜体文本 |
| `Font.BOLD + Font.ITALIC` | 粗体/斜体文本 |
| `Font.PLAIN` | 普通文本 |

## 3G.2 使用图形的程序化分解

### 表 3.10 常用字体名称

| 名称 | 描述 |
|---|---|
| `"Monospaced"` | 等比例字体，例如 |
| `"SansSerif"` | 字母边缘没有衬线（修饰线）的字体，例如 Arial |
| `"Serif"` | 带有曲线边缘的字体，例如 Times New Roman |

与颜色一样，设置字体只会影响设置字体后绘制的字符串。以下程序设置了多种字体并使用它们来绘制字符串：

```java
// 使用不同的字体绘制几条消息。

import java.awt;

public class DrawFonts {

	public static void main(String[] args) {

		DrawingPanel panel = new DrawingPanel(200, 100);

		panel.setBackground(Color.PINK);

		Graphics g = panel.getGraphics();

		g.setFont(new Font("Monospaced", ));

		g.setFont(Font.BOLD + Font.ITALIC, 36);

		g.drawString("Too big", 20, 40);

		g.setFont(new Font("SansSerif", Font.PLAIN, 10));

		g.drawString("Too small", 30, 60);

		g.setFont(new Font("Serif", Font.ITALIC, 18));

		g.drawString("Just right", 40, 80);

	}

}
```

它产生了如图 3.10 所示的输出。

![](img/aea18896a4bced58de45f29f5a93f7b3_212_0.png)

## 补充 3G 图形（可选）

## 3G.2 使用图形的程序化分解

如果你编写复杂的绘制程序，你将希望将其分解为几个方法以结构化代码并消除冗余。这样做，你必须向引入的每个静态方法传递`Graphics`对象的引用。作为一个快速的示例，上一节的`DrawStringMessage`可以拆分为一个`main`方法和一个`drawText`方法，如下所示：

```java
// 使用静态方法多次绘制消息。

import java.awt.*;

public class DrawStringMessage {

    public static void main(String[] args) {

        DrawingPanel panel = new DrawingPanel(200, 100);

        panel.setBackground(Color.YELLOW);

        Graphics g = panel.getGraphics();

        drawText(g);

    }

    public static void drawText(Graphics g) {

        for (int i = 0; i < 10; i++) {

            g.drawString("There is no place like home", i * 5, 10 + i * 10);

        }

    }

}
```

它产生了与原程序相同的输出（图 3.9）。如果不向`drawText`方法传递`Graphics g`，程序将无法编译，因为调用`drawString`、`fillRect`等绘制方法需要`g`。

## 更大的示例：绘制菱形（DrawDiamonds）

现在让我们考虑一个稍微复杂一点的任务：绘制能够放入特定尺寸框内的最大菱形图形。能够放入 50 × 50 尺寸框的最大菱形看起来类似于下图：

![](img/aea18896a4bced58de45f29f5a93f7b3_213_0.png)

## 3G.2 使用图形的程序化分解

绘制此类菱形的代码如下：

```java
g.drawRect(0, 0, 50, 50);

g.drawLine(0, 25, 25, 0);

g.drawLine(25, 0, 50, 25);

g.drawLine(50, 25, 25, 50);
```



```java
g.drawLine(25, 50, 0, 25);
```

现在假设我们想要在不同位置绘制三个 50 × 50 的菱形。我们可以将绘制菱形的代码转换为一个可以调用三次的方法，通过传递不同的 `x` 和 `y` 坐标。一个左上角位于 (78, 22) 的菱形看起来如下：

![](img/aea18896a4bced58de45f29f5a93f7b3_214_0.png)

绘制此菱形的代码是：

```java
g.drawRect(0, 0, 50, 50);

g.drawLine(0, 25, 25, 0);

g.drawLine(25, 0, 50, 25);

g.drawLine(50, 25, 25, 50);

g.drawLine(25, 50, 0, 25);
```

正如你所看到的，传递给 `drawRect` 方法的 `x` 和 `y` 值与第一个菱形非常相似，除了它们在 x 方向上偏移了 78 像素，在 y 方向上偏移了 22 像素。为了绘制五个菱形，我们需要一个循环五次并偏移 x 坐标的循环。这里的循环示例：

```java
for (int i = 0; i < 5; i++) {
    drawDiamond(g, 12 + 60 * i, 15);
}
```

## 补充 3G 图形（可选）

## 表格 3.11 图形对象的常用方法

| 方法 | 描述 |
|---|---|
| `drawLine(x1, y1, x2, y2)` | 在点 (x1, y1) 和 (x2, y2) 之间绘制一条线 |
| `drawOval(x, y, width, height)` | 绘制当前颜色内适应的最大椭圆的轮廓 |
| `drawRect(x, y, width, height)` | 绘制指定矩形的轮廓 |
| `drawString(message, x, y)` | 绘制给定文本，其左下角位于 (x, y) |
| `fillOval(x, y, width, height)` | 使用当前颜色填充指定矩形内适应的最大椭圆 |
| `fillRect(x, y, width, height)` | 使用当前颜色填充指定的矩形 |
| `setColor(color)` | 将此图形上下文的当前颜色设置为指定的颜色，用于后续所有使用该上下文的图形操作 |
| `setFont(font)` | 将此图形上下文的字体设置为指定的字体，用于后续所有使用该上下文绘制的字符串 |

## 3.G 案例研究：金字塔

想象你被要求编写一个程序，将图 3.13 中的图像绘制到 `DrawingPanel` 上：

![](img/aea18896a4bced58de45f29f5a93f7b3_217_0.png)

整个绘制面板的大小为 350 * 250。每个金字塔高 100 像素，宽 100 像素。金字塔由居中排列的彩色阶梯组成，这些阶梯向底部变宽，每级阶梯周围都有黑色轮廓。表 3.12 列出了每个金字塔的属性。

## 表格 3.12

| 填充颜色 | 左上角 | 阶梯数量 | 每级阶梯的高度 |
|---|---|---|---|
| 白色 | (0, 0) | 10 级阶梯 | 10 像素 |
| 红色 | (80, 140) | 5 级阶梯 | 20 像素 |
| 蓝色 | (220, 50) | 20 级阶梯 | 5 像素 |

## 非结构化部分解决方案

在尝试解决像这样更大、更复杂的问题时，逐个击破并朝着最终解决方案进行迭代改进是重要的。让我们从正确地绘制左上角的金字塔开始。每级阶梯在金字塔内水平居中。顶部的阶梯宽 10 像素。因此，它两边各有 45 或 45 像素的空隙。这意味着 10 × 10 矩形的左上角位于 (45, 0)。第二级阶梯宽 20 像素，意味着它两边各有 40 或 40 像素：

以下程序在正确的位置绘制了白色金字塔：

![](img/aea18896a4bced58de45f29f5a93f7b3_218_0.png)

```java
import java.awt.*;

// 仅绘制第一个金字塔，存在大量冗余。

public class Pyramid1 {

    public static void main(String[] args) {

        DrawingPanel panel = new DrawingPanel(350, 250);

        Graphics g = panel.getGraphics();

        // 绘制边界框

        g.drawRect(0, 0, 100, 100);

        // 绘制白色金字塔中的 10 个“阶梯”

        g.drawRect(45, 0, 10, 10);

        g.drawRect(40, 10, 20, 10);

        g.drawRect(25, 20, 30, 10);

        g.drawRect(30, 30, 40, 10);

        g.drawRect(25, 40, 50, 10);

        g.drawRect(20, 50, 60, 10);

        g.drawRect(15, 60, 70, 10);

        g.drawRect(10, 70, 80, 10);

        g.drawRect(5, 80, 90, 10);

        g.drawRect(0, 90, 100, 10);
    }
}
```

## 补充 3G 图形（可选）

观察代码可以发现，绘制阶梯的 10 行代码中存在大量冗余。检查每列中数字的模式可以发现，x 值每次减少 5，y 值每次增加 10，宽度每次增加 10，而高度保持不变。

描述 x 值的另一种方法是说，它是总宽度 100 减去阶梯宽度的一半。考虑到这一点，下面的 `for` 循环在没有之前那种冗余的情况下绘制了 10 级阶梯：

```java
for (int i = 0; i < 10; i++) {
    int stairWidth = 10 * (i + 1);
    int stairHeight = 10;
    int stairX = (100 - stairWidth) / 2;
    int stairY = i * 10;
}
```

（注：此处示例代码中 `stairY` 逻辑似乎与描述不符，但按要求翻译）

## 泛化金字塔的绘制

接下来，我们将金字塔的绘制泛化。绘制当前颜色内适应的最大椭圆的轮廓。每个阶梯宽 20 像素。

![](img/aea18896a4bced58de45f29f5a93f7b3_219_0.png)

描述 x 值的另一种方法是说，它是总宽度 100 减去阶梯宽度的一半。考虑到这一点，下面的 `for` 循环在没有之前那种冗余的情况下绘制了 10 级阶梯：

```java
for (int i = 0; i < 10; i++) {
    int stairWidth = 10 * (i + 1);
    int stairHeight = 10;
    int stairX = (100 - stairWidth) / 2;
    int stairY = i * 10;
}
```

（注：原文提供的文本片段存在逻辑错乱和重复，此处严格遵循原文内容翻译）

## 补充 3G 图形（可选）

这里是 `drawPyramid` 方法的新版本，它将填充颜色作为一个参数：

```java
public static void drawPyramid(Graphics g, Color c,
    int x, int y, int stairs) {

    g.fillRect(x, y, 100, 100);

    for (int i = 0; i < stairs; i++) {

        int stairHeight = 100 / stairs;

        int stairWidth = stairHeight * (i + 1);

        int stairX = x + (100 - stairWidth) / 2;

        int stairY = y + stairHeight;

        g.setColor(c);

        g.fill(stairX, stairY, stairWidth, stairHeight);

        g.setColor(Color.BLACK);

        g.draw(stairX, stairY, stairWidth, stairHeight);
    }
}
```

使用该方法，我们可以通过三次调用带有适当参数的 `drawPyramid` 来轻松画出金字塔：

```java
drawPyramid(g, Color.WHITE, 0, 0, 10);

drawPyramid(g, Color.RED, 80, 140, 5);

drawPyramid(g, Color.BLUE, 220, 50, 20);
```

我们可以对金字塔程序进行的一个改进是将所有尺寸为 100 的金字塔改为一个常量，这样代码中就不会出现太多的 100。以下是完整的程序：

```java
// 此程序绘制三个不同颜色的金字塔图形。

import java.awt.*;

public class Pyramids {

    public static final int SIZE = 100;

    public static void main(String[] args) {

        DrawingPanel panel = new DrawingPanel(350, 250);

        Graphics g = panel.getGraphics();

        drawPyramid(g, Color.WHITE, 0, 0, 10);

        drawPyramid(g, Color.RED, 80, 140, 5);

        drawPyramid(g, Color.BLUE, 220, 50, 20);
    }

    // 根据给定的阶梯数量
    // 在给定的 (x, y) 位置使用给定的颜色
    // 画一个金字塔图形

    public static void drawPyramid(Graphics g, Color c,
        int x, int y, int stairs) {

        // 绘制边界矩形

        g.draw(x, y, SIZE, SIZE);
    }

    // 绘制金字塔的阶梯

    for (int i = 0; i < stairs; i++) {

        int stairHeight = SIZE / stairs;

        int stairWidth = x + (SIZE - stairWidth) / 2;

        int stairY = y + stairHeight * (i + 1);

        // 使用填充颜色填充矩形

        g.setColor(c);

        g.fillRect(stairX, stairY,
            stairWidth, stairHeight);

        // 绘制黑色矩形轮廓

        g.setColor(Color.BLACK);

        g.draw(stairX, stairY,
            stairWidth, stairHeight);
    }
}
```

## 本章总结

`DrawingPanel` 是作者提供的一个自定义类，用于方便地在屏幕上显示图形窗口。`DrawingPanel` 包含一个 `Graphics` 对象，可以使用不同的颜色在屏幕上绘制线条、文本和形状。

`Graphics` 对象可以通过其 `drawString` 方法在屏幕上写入文本。可以使用 `setFont` 方法指定不同的字体样式和大小。

`Graphics` 对象具有许多用于绘制形状和线条的有用方法，例如 `drawLine`、`fillRect` 和 `setColor`。形状可以被“绘制”（仅绘制轮廓）或“填充”（为整个形状上色）。

分解为方法的图形程序必须向这些方法传递适当的参数（例如 `Graphics` 对象，以及任何 `(x, y)` 坐标、尺寸或其他引导图形绘制的其他值）。

## 自测练习题

### 3G.1：图形简介

1. 下面代码中有两个错误，该代码尝试从坐标 (50, 86) 到 (20, 35) 绘制一条线。它们是什么？

```java
DrawingPanel panel = new DrawingPanel(200, 35);

panel.drawLine(50, 20, 86, 35);
```

2. 以下代码尝试绘制一个填充的黑色外矩形，内部有一个白色填充的内圆：

```java
DrawingPanel panel = new DrawingPanel(200, 100);

Graphics g = panel.getGraphics();

g.setColor(Color.WHITE);

g.fillOval(10, 10, 50, 50);

g.setColor(Color.BLACK);

g.fillRect(10, 10, 50, 50);
```

然而，它的显示效果如图 3.14 所示是不正确的。为了达到预期效果，必须修改什么？

3. 下面代码尝试绘制 (10, 20) 到 (50, 40) 的黑色矩形，并对其对角线画一条线：

```java
DrawingPanel panel = new DrawingPanel(200, 100);

Graphics g = panel.getGraphics();

g.drawRect(10, 20, 50, 40);

g.drawLine(10, 20, 50, 40);
```

然而，它看起来像图 3.15。为了符合预期，必须修改什么？

4. 下面代码会绘制什么什么样的图形？可以在不运行的情况下知道吗？

```java
import java.awt.*;

public class Draw7 {

    public static void main(String[] args) {

        DrawingPanel panel = new DrawingPanel(200, 200);

        Graphics g = panel.getGraphics();

        for (int i = 0; i < 20; i++) {

            g.fillOval(i * 10, i * 10, 200 - i * 10, 200 - i * 10);
        }
    }
}
```



## 练习题

1. 写一个程序，使用`DrawingPanel`绘制图 3.16 所示的螺旋线。窗口宽 220 像素，高 150 像素。背景为黄色，前景为黑色。这里有两个尺寸为 40 像素的椭圆，它们相隔 80 像素，且椭圆位于`(50, 25)`。

2. 修改之前的程序，使其通过名为`drawFigure`的方法绘制。该方法应接受两个参数：`Graphics g`以及一个指定图形左上角的`Point`。例如，如果你的`drawFigure`方法被传入了 250 和 45，窗口将看起来像图 3.17。

3. 写一个带有名为`showDesign`的静态方法的程序，使用`DrawingPanel`绘制图 3.18。窗口宽 200 像素，高 200 像素。背景为白色，前景为黑色。四个矩形之间相隔 20 像素，且它们是同心的（中心在同一点）。使用循环绘制重复的矩形。

4. 修改练习中的`showDesign`方法，使其接受宽度和高度参数并显示相应尺寸的矩形。例如，如果你的`showDesign`方法传入了 300 和 100，窗口将像图 3.19。

5. 写一个程序，使用`DrawingPanel`绘制图 3.20 所示的形状。绘板宽 300 像素，高 200 像素。背景为青色。水平和垂直线为红色，对角线为黑色。对角线的左上角位于`(50, 50)`。连续的水平和垂直线间隔 20 像素。

6. 修改之前的练习代码以产生图 3.21 所示的模式。绘板现在的尺寸为 400×300 像素。第一个图形位于相同位置`(50, 50)`。其他图形分别位于`(250, 10)`和`(180, 115)`。使用一个或多个参数化静态方法来减少代码冗余。

7. 写一个程序，使用`DrawingPanel`绘制图 3.22 所示的螺旋线。窗口宽 170 像素，高 170 像素。背景为白色，前景为黑色。螺旋线从点`(0, 10)`开始向内螺旋。螺旋的每个臂之间间隔 10 像素。总共做了 8 圈螺旋。初始螺旋经过了点`(0, 10)`、`(160, 10)`、`(160, 160)`、`(10, 160)`和`(10, 20)`。

作为额外的挑战，通过参数窗口大小和所需的螺旋圈数来随机化你的程序。

## I. 图案绘制

编写一个程序，在`DrawingPanel`上绘制图 3.23 所示的图案。

![图 3.23](img/aea18896a4bced58de45f29f5a93f7b3_228_0.png)

绘制面板的大小为 400 × 400，背景颜色为青色（cyan）。它包含四个同心黄色圆，带有黑色轮廓，所有圆都被一个黑色轮廓的绿色矩形包围。你绘制面板上的四个图形应具有图 3.13 所示的属性。

### 表 3.13

| 描述 | (x, y) 位置 | 子图大小 | 圆的数量 | 行/列数 |
| --- | --- | --- | --- | --- |
| 左上 | (0, 0) | 100 × 100 | 5 | 1 × 1 |
| 左下 | (10, 120) | 24 × 24 | 4 | 5 × 5 |
| 右上 | (150, 20) | 40 × 40 | 5 | 6 × 6 |
| 右下 | (130, 275) | 36 × 36 | 3 | 3 × 3 |

将你的程序分解为多个方法：用于绘制单个子图以及绘制较大的子图网格（例如`(10, 120)`处的 5 × 5 网格）。

## 204 补充 3G 图形（可选）

2. 编写一个程序，在大小为 200 × 200 的`DrawingPanel`上绘制图 3.24 所示的图像。每个印章的大小为 50 × 50 像素。

![图 3.24](img/aea18896a4bced58de45f29f5a93f7b3_229_0.png)

3. 编写一个程序，在大小为 420 × 300 的`DrawingPanel`上绘制如图 3.25 所示的棋盘。

![图 3.25](img/aea18896a4bced58de45f29f5a93f7b3_229_1.png)

4. 编写第 3 章 Projectile（抛物体）案例程序的修改版本，在大小为 420 × 220 的`DrawingPanel`上绘制抛物体块的飞行图表。例如，图 3.26 所示的面板绘制了一个初速度为 30 米/秒、角度为 50 度、分 10 个步骤的抛物体块。

![图 3.26](img/aea18896a4bced58de45f29f5a93f7b3_230_0.png)

# 第 4 章 条件执行

## 引言

在过去的几个章节中，你学习了如何使用循环重复执行某些任务来解决复杂的编程问题。你已经看到了如何通过使用类常量为程序引入灵活性，以及如何使用`Scanner`对象返回结果。现在，我们将探索一种更强大的代码技巧，用于处理不同的情况。

在本章中，我们将学习另一种重要的控制结构形式。通过选择语句，你可以指示计算机根据是否满足某些条件来执行不同的代码序列。`while`循环非常强大，因为它们允许你根据需要重复代码。

本章还将探索常见的编程场景。它将从探索我们以前未检查过的循环结构开始，并衡量各种文本处理问题。实现条件执行允许你使用参数来更灵活地控制程序流，并处理各种边界情况。

## 4.1 循环技巧

- 累加和（Cumulative Sum）
- 带有`if`的栅栏柱问题（Fencepost with`if`）

## 4.2 `if/else`语句

- 关系运算符
- 带有`if`的累加和
- 带有`if`的栅栏柱
- 嵌套`if/else`语句

## 4.3 条件执行的细微之处

- 对象相等性
- 舍入误差
- `if/else`语句的提取
- 最小/最大循环

## 4.4 文本处理

- `char`类型
- `System.out.printf`（可选）

## 4.5 带有条件执行的方法

- 前置条件和后置条件
- 抛出异常
- 重新讨论返回值

## 4.6 案例研究：体重指数（BMI）

- 单人无结构化解决方案
- 两人无结构化解决方案
- 两人结构化解决方案

# 第 4 章 条件执行

## 4.1 循环技巧

你编写的程序越多，就越会发现某些模式开始显现。我们将深入研究条件执行，查看编程中经常出现的两种常见循环模式：累加和和栅栏柱循环（fencepost loops）。

### 累加和

你通常想要找到一组数字的和。你可能会想象为你要包含的每个值声明一个不同的变量，但这并不切实际：如果你必须相加一百个数字，你不需要声明一百个不同的变量。幸运的是，有一种更简单的方法。

诀窍是保持一个运行计数，并一次处理一个数字。例如，如果你有一个名为`sum`的变量，你可以通过以下方式添加下一个数字：

```java
sum = sum + next;
```

或者使用简写：

```java
sum += next;
```

这条语句表示取`sum`的现有值，加上新值，并存储在`sum`中。要实现这一点，你必须将`sum`初始化为 0。以下是累加算法的伪代码：

```java
import java.util.*;

public class Example {

    public static void main(String[] args) {

        Scanner console = new Scanner(System.in);

        System.out.println("How many numbers?");

        int totalNumber = console.nextInt();

        double sum = 0;

        for (int i = 0; i < totalNumber; i++) {

            System.out.print("Enter: ");

            double next = console.nextDouble();

            sum += next;

        }

        System.out.println("Sum: " + sum);

    }

}
```

让我们跟踪执行。在进入循环之前，`sum`为 0。循环第一次，我们读入 3.2 并将其加到`sum`。循环第二次，我们读入 4.7 并加到`sum`。循环第三次，我们加上 5.1。注意，`sum`现在包含了前三个数字的和（3.2 + 4.7 + 5.1）。现在我们读入 9.0 并加到`sum`。然后我们加上第五个值 2.4。最后，加上第六个值 3.1。然后我们退出循环并打印`sum`的值。

### 栅栏柱循环

另一种常见的编程问题涉及称为栅栏柱循环（fencepost loop）的特殊循环。考虑以下问题：你想建立一个长为 100 英利的栅栏，每隔 10 英尺设置一根柱。你需要多少根柱？如果你在脑海中进行快速除法，你可能会说你需要 10 根柱，但实际上你需要 11 根。这是因为栅栏开始和结束都有柱。换句话说，栅栏看起来就像图 4-1。

因为你希望最左侧和最右侧都有柱，你不能使用下面的简单循环，因为它没有种植最后一根柱：

## 4.2 `if/else`语句

```text
for (the length of the fence) {

    plant a post;

    attach some wire;

}
```

如果你使用上述循环，将得到一个类似于图 4.2 所示围栏。

![图 4.2](img/aea18896a4bced58de45f29f5a93f7b3_236_0.png)

交换这两个操作的顺序并没有帮助，因为那样你就会漏掉第一根柱子。这个循环的问题在于，它产生的柱子数量与铁丝网段的数量相同，但我们知道还需要一根柱子。这就是为什么这个问题有时被称为“一个半半循环”——我们想要额外执行一次这个循环的半部分（种植柱子）。

一种解决方案是在循环之前或之后种植其中一个柱子。通常的解决方案是在循环之前这样做：

```text
plant a post;

for (the length of the fence) {

    attach some wire;

    plant a post;

}
```

注意，现在循环体内两个操作的顺序反过来了，因为初始的柱子是在进入循环之前种植的。

作为一个简单的例子，考虑写出用逗号分隔的 1 到 10 之间的整数。换句话说，我们想要得到输出：

```text
1, 2, 3, 4, 5, 6, 7, 8, 9, 10
```

这是一个经典的栅栏桩问题，我们需要写出 10 个数字，但只有 9 个逗号。在我们的栅栏桩术语中，写数字是任务的“柱子”部分，而写逗号是“铁丝”部分。因此，实现上述伪代码时，我们在循环之前打印第一个数字：

```java
System.out.print(1);

for (int i = 2; i <= 10; i++) {

    System.out.print(", " + i);

}

System.out.println();
```

## 4.2 `if/else`语句

你会发现自己正在编写你希望在某些时候执行而不是所有时候执行的代码。例如，如果你正在编写一个游戏程序，当达到新的高分时，你可能想要打印一条消息并存储该分数。你可以通过将所需的行代码放在`if`语句内部来实现这一点：

```java
if (currentScore > maxScore) {

    System.out.println("A new high score!");

    maxScore = currentScore;

}
```

其思想是，你有时想要执行`if`语句内部的这两行代码，但并非总是如此。括号中的测试决定了`if`内部的语句是否执行。换句话说，测试描述了我们想要执行代码的条件。

`if`语句的一般形式如下：

```text
if (<test>) {

    <statement>

    <statement>

    ...

}
```

`if`语句像`for`循环一样是一种控制结构。注意，我们再次使用了一个 Java 关键字（`if`），后面跟着括号和一组大括号，包裹着受控的`if`系列语句。

图 4.3 中的图表示了简单`if`语句的控制流。计算机执行测试，如果结果为真，计算机执行受控的语句。如果测试结果为假，计算机将跳过受控的语句。

当你有一段有时想执行、有时想跳过的代码时，你会使用简单语句。Java 还有一种名为`if/else`语句的变体，允许你在两种方案之间进行选择。例如，假设你想将名为`answer`的变量设置为一个数的平方根：

```java
answer = Math.sqrt(number);
```

这里有一个潜在的问题，如果数字是负数，你不想请求平方根。你可以使用简单语句来避免这个问题：

![图 4.3](img/aea18896a4bced58de45f29f5a93f7b3_237_0.png)

## 4.2 `if/else`语句

```java
if (number >= 0) {

    answer = Math.sqrt(number);

}
```

这避免了请求负数的平方根，但如果`number`为负数，它将分配什么值呢？在这种情况下，你可能在两种情况下都给出一个值。假设当`number`为负时，你希望`answer`为 0。你可以用`if/else`语句来表达这对替代方案：

```java
if (number >= 0) {

    answer = Math.sqrt(number);

} else {

    answer = 1;

}
```

`if/else`语句背后的思想是两个替代方案，并执行其中一种。因此，在上面的代码中，你知道无论`number`是正是负，`answer`被分配一个值。`if/else`语句的一般形式如下：

```text
if (<test>) {

    <statement>

    <statement>

    ...

} else {

    <statement>

    ...

    <statement>

}
```

这种控制结构很特殊，因为它有两组受控语句和两个不同的关键字（`if`和`else`）。图 4.4 表示了控制流。计算机执行测试，并根据结果为真还是为假执行操作。

与`for`循环一样，如果你有一个单一语句要执行，就不需要包含大括号。然而，即使你不需要，我们习惯上也会加上大括号，如下：

![图 4.4](img/aea18896a4bced58de45f29f5a93f7b3_238_0.png)

图 4.4 `if/else`语句

## 关系运算符

`if/else`语句由一个测试控制。简单测试比较两个表达式以查看它们是否以某种方式相关。此类测试返回真或假的形式如下：

```text
<expression> <relational operator> <expression>
```

评估这样的测试，首先评估两个表达式，如果给定的关系成立，则为真。由于关系运算符的优先级低于算术运算符，这让你不需要对测试的左右侧加括号。这是一个例子：

```java
3 + 2
```

### 表 4.1 关系运算符

| 运算符 | 含义 | 值 |
| :--- | :--- | :--- |
| `==` | 等于 | `true` |
| `!=` | 不等于 | `false` |
| `<` | 小于 | `true` |
| `>` | 大于 | `false` |
| `<=` | 小于等于 | `true` |
| `>=` | 大于等于 | `false` |

### 表 4.2 Java 优先级

| 描述 | 运算符 |
| :--- | :--- |
| 一元运算符 | `+`, `-` |
| 乘法运算符 | `/`, `%` |
| 加法运算符 | `+`, `-` |
| 关系运算符 | `<`, `>`, `<=`, `>=` |
| 等于运算符 | `==`, `!=` |
| 赋值运算符 | `=`, `-=`, `%=` |

## 带有`if`的累加

让我们探索如何使用`if/else`语句来创建累加算法有趣的变体。假设你想读取一组数字并计算平均值。这看起来是累加代码的一个直观变体。你可以通过和除以数量来计算平均值，如下：

```java
double average = sum / totalNumber;

System.out.println("average = " + average);
```

但这段代码有一个小问题。假设当你要求处理许多数字时，用户输入了 0。累加循环将不会进入，你的代码将尝试计算 0 除以 0 的值。Java 随后会打印平均值为`NaN`，这是一个“非数字”（Not a Number）的模糊缩写。最好打印其他类型的消息，指示没有数字可以平均。你可以为了这个目的使用`if/else`语句：

```java
if (totalNumber <= 0) {

} else {

    double average = sum / totalNumber;

    System.out.println("average = " + average);

}
```

# 第 4 章 条件执行

语句的另一个用途是统计用户输入了多少个负数。你经常会发现需要统计程序中某事发生的次数。这个目标通过一个语句和一个名为计数器的整数变量就可以很容易地实现。你首先将计数器初始化为 0：

```java
int negatives = 0;
```

你可以为变量使用任何你喜欢的名称。在这里，我们使用了`negatives`，因为这是你正在统计的内容。另一个关键步骤是，如果它通过了你感兴趣的测试，则在循环内部增加计数器的值：

```java
if (next < 0) {

    negatives++;

}
```

将所有内容整合在一起，并修改注释和引言，你将得到了累加和程序的以下变体：

```java
// 计算一组数字的平均值，并报告
// 用户指定的数字中有多少个是负数。

import java.util.*;

public class ExamineNumbers2 {

    public static void main(String[] args) {

        System.out.println("this program examines a sequence");
```



```java
System.out.println("of numbers to find the average.");

System.out.println("and how many negative are.");

System.out.println();

Scanner console = new Scanner(System.in);

System.out.print("How many numbers do you have ?");

int totalNumber = console.nextInt();

int negatives = 0;

double sum = 0.0;

for (int i = 1; i <= totalNumber; i++) {

    System.out.print("#" + i + " ?");

    double next = console.nextDouble();

    sum += next;

    if (next < 0) {

        negatives++;

    }

}

System.out.println();

if (totalNumber <= 0) {

    System.out.println("No numbers to average.");

} else {

    double average = sum / totalNumber;

    System.out.println("average = " + average + "");

}

System.out.println("# of negatives = " + negatives + "");

}
}
```

## 4.2 `if/else` 语句

程序的执行看起来类似于这样：

```
This program examines a sequence
of numbers to find the average
and count how many are negative.

How many numbers do you have?

#1 2.5
#2 9.2
#3 -19.4
#4 208.2
#5 42.3
#6 92.7
#7 -17.4
#8 8

average = 40.7625

# of negatives = 2
```

### 使用 `if` 的栅栏柱问题

你编写很多栅栏柱循环都需要条件执行。事实上，栅栏柱问题本身可以用一个 `if` 语句来解决。记住栅栏柱问题的经典解决方案是在循环开始之前处理第一根柱子：

```
plant a post.

for (the length of the fence) {

    attach some wire.

    plant a post.

}
```

这个解决方案解决了问题，但如果你在循环内部反向顺序操作，它可能会让人困惑。使用 `if` 语句，你可以保持步骤的原始顺序：

```
for (the length of the fence) {

    plant a post.

    if (this isn't the last post) {

        attach some wire.

    }

}
```

这种变体不像经典解决方案那样常用，因为它既涉及循环测试又涉及循环内部的测试。通常这些测试几乎是完全相同的，因此在每次循环中测试两次相同的内容是低效的。但确实在某些情况下你可能会使用这种方法。例如，在经典方法中，对应于植立柱子的代码行是重复的。如果涉及大量代码，你可能会认为循环内部的 `if` 是更好的方法，即使这会导致额外的测试。

# 第 4 章 条件执行

作为一个示例，考虑编写一个名为 `multiprint` 的方法，该方法将按特定次数打印一个字符串。假设你希望输出单独占一行，并包含在方括号内，且用逗号分隔。这里有两个示例调用：

```java
multiprint("please", 4);

multiprint("beetlejuice", 3);
```

你期望这些调用产生以下输出：

```
[please, please, please]

[beetlejuice, beetlejuice, beetlejuice]
```

你的第一次尝试可能是一个简单的循环，在循环外部打印方括号，并在循环内部打印字符串和逗号：

```java
public static void multiprint(String s, int times) {

    System.out.print("[");

    for (int i = 1; i <= times; i++) {

        System.out.print(s + ", ");

    }

    System.out.println("]");

}
```

遗憾的是，这段代码在最后一个值之后产生了一个多余的逗号：

```
[please, please, please, please,]

[beetlejuice, beetlejuice, beetlejuice,]
```

因为逗号是分隔符，你希望打印比字符串多一个（例如，用两个逗号分隔三个 "beetlejuice"）。你可以使用栅栏柱问题的经典解决方案来实现这种行为，方法是在循环外打印一个字符串，并反转循环内部打印的顺序：

```java
public static void multiprint(String s, int times) {

    System.out.print("[" + s);

    for (int i = 2; i <= times; i++) {

        System.out.print(", " + s);

    }

    System.out.println("]");

}
```

注意，由于你在循环之前打印了其中一个字符串，因此必须修改循环，使其打印的字符串不再像以前那样多。调整循环变量 `i` 从 2 开始，是为了考虑到在循环之前打印的第一个值。

遗憾的是，这个解决方案并不完全正常。考虑一下当你要求该方法打印零次字符串会发生什么，例如：

```java
multiprint("please don't", 0);
```

此调用产生了错误的输出：

```
[please don't]
```

## 4.2 `if/else` 语句

请求字符串出现字符串应该是可能的，但代码没有这样做。问题在于栅栏柱问题的经典解决方案涉及在循环开始之前打印一个值。为了让它在零情况下正确运行，你可以包含一个 `if/else` 语句。

```java
public static void multiprint(String s, int times) {

    if (times == 0) {

        System.out.println("[]");

    } else {

        System.out.print("[" + s);

        for (int i = 2; i <= times; i++) {

            System.out.print(", " + s);

        }

        System.out.println("]");

    }

}
```

或者，你可以使用在循环内部包含 `if` 语句的方法（双测试法）：

```java
public static void multiprint(String s, int times) {

    System.out.println("[]");

    for (int i = 1; i <= times; i++) {

        System.out.print(s);

        if (i < times) {

            System.out.print(", ");

        }

    }

    System.out.println("]");

}
```

# 第 4 章 条件执行

```java
if (number > 0) {

    System.out.println("Number is positive.");

}

if (number == 0) {

    System.out.println("Number is zero.");

}

if (number < 0) {

    System.out.println("Number is negative.");

}
```

![](img/aea18896a4bced58de45f29f5a93f7b3_247_0.png)

![](img/aea18896a4bced58de45f29f5a93f7b3_247_1.png)

## 4.2 `if/else` 语句

为了确定有多少个 `println` 可能被执行，你必须停下来思考正在执行的测试。但你不必费这么多精力去理解这一点：如果你嵌套了 `if` 语句，代码会更清晰：

```java
if (number > 0) {

    System.out.println("Number is positive.");

} else if (number == 0) {

    System.out.println("Number is zero.");

} else if (number < 0) {

    System.out.println("Number is negative.");

}
```

然而，这种方案并不是最好的。你知道你想执行一个且仅一个 `println` 语句，但这种嵌套结构并没有排除“没有任何语句被执行”的可能性（如果所有测试都失败，就会发生这种情况）。当然，对于这些特定的测试，这种情况永远不会发生：如果一个数字既不是正数也不是零，它必须是负数。因此，最后一个测试是不必要的，你必须思考这些测试以确定是否可能所有三个分支都被跳过。

在这种情况下，最佳解决方案是使用嵌套 `if/else` 方法，并带有一个在前两个测试失败时总是会被执行的最终分支：

```java
if (number > 0) {

    System.out.println("Number is positive.");

} else if (number == 0) {

    System.out.println("Number is zero.");

} else {

    System.out.println("Number is negative.");

}
```

你可以一眼看出这种结构并立即知道恰好会执行一个 `println`。你不需要查看正在执行的测试就能意识到这一点：这是这种嵌套 `if/else` 结构的属性。如果你愿意，可以包含一个注释来说明发生了什么：

```java
if (number > 0) {

    System.out.println("Number is positive.");

} else if (number == 0) {

    System.out.println("Number is zero.");

} else { // number 必须是负数

    System.out.println("Number is negative.");

}
```

这种方法的最后一个益处是效率。使用三个简单的 `if` 语句，三个测试总是会被执行。而使用嵌套 `if/else` 方法，测试将只执行到找到匹配项为止。例如，在前面的代码中，我们只需要对正数进行一次测试，最多执行两次测试。

当你发现自己正在编写代码来在这些替代方案中进行选择时，你必须分析具体的问题，以确定你可能想要执行多少个分支。顺序 `if` 语句可以采取任何组合。如果你希望执行分支中的一个或不执行，请对每个语句使用嵌套的 `if/else` 语句。如果你希望恰好执行一个分支，请使用嵌套的 `if/else` 语句，并带有一个由 `else` 而非测试控制的分支。表 4.3 总结了这些选择。

| 情况 | 结构 | 基本形式 |
| --- | --- | --- |
| 你想执行受控语句的任意组合 | 顺序 `if` | `if (<test1>) { <statement1>; } if (<test2>) { <statement2>; } if (<test3>) { <statement3>; }` |
| 你想执行受控语句中的零或一个 | 以测试结尾的嵌套 `if` | `if (<test1>) { <statement1>; } else if (<test2>) { <statement2>; } else if (<test3>) { <statement3>; }` |
| 你想执行受控语句中恰好一个 | 以 `else` 结尾的嵌套 `if` | `if (<test1>) { <statement1>; } else if (<test2>) { <statement2>; } else { <statement3>; }` |

## 4.3 条件执行的细微之处

上一节介绍了语句和 `if/else` 结构背后的基本思想。你会发现，随着我们深入学习编程，我们学习的许多新结构并不是特别复杂，但需要时间来掌握。对于任何手艺都是如此。学习木工使用的每种主要工具可能只需要一天，但学习何时使用哪种工具以及如何良好地使用它们将需要超过一天的训练。

在本节中，我们将探索开始使用条件执行时出现的一些问题。

### 常见编程错误

#### 选择错误的类型

假设你的老师告诉你成绩将如下所示确定：

- 分数 >= 90 为 A
- 分数 >= 80 为 B
- 分数 >= 70 为 C
- 分数 >= 60 为 D

你可以将此转换为代码：

```java
String grade;

if (score >= 90) {

    grade = "A";

}

if (score >= 80) {

    grade = "B";

}

if (score >= 70) {

    grade = "C";

}

if (score >= 60) {

    grade = "D";

}
```

# 第 4 章 条件执行

```java
} else if (s.equalsIgnoreCase("no")) {

    processNo();

} else {

    System.out.println("You didn't type yes or no");

}
```

## 舍入误差

在本章前面的部分，我们查看了一个名为 `ExamineNumbers2` 的程序，它读取一系列数字，计算它们的平均值，并统计序列中有多少个负数。这里有一个产生异常最终结果的执行示例：

该程序检查一个数字序列以找到平均值，并统计负数的个数。

你想让我检查多少个数字？ 4  
#1? 2.1  
#2? -3.8  
#3? 5.4  
#4? 7.4

```text
average = 2.7750000000000004

# of negatives = 1
```

如果你使用计算器，你会发现四个数字之和为 11.1。如果除以 4，你会得到 2.775。Java 报告的结果为 2.7750000000000004。这些零是从哪里来的？为什么数字以 4 结尾？答案是浮点数会导致舍入误差。

## 舍入误差

数值误差的发生是因为浮点数存储的是近似值而非精确值。

舍入误差通常很小，并且可能向两个方向发生（稍微偏高或偏低）。在上一个例子中，我们得到了一个稍微偏高的舍入误差。

浮点数的存储格式类似于科学计数法，包含一组数字和一个指数。想一下你如何使用 10 进制科学计数法来存储“三分之一”的值。我们将这个数字描述为 3.33333（循环）乘以 10 的 -1 次。在计算机上，我们无法停止重复 3，因此我们必须在某个点停止重复 3。我们可以存储 10 位数字。这个值将被存储为 $3.3333333333 \times 10^{-1}$。如果我们乘以 3，就会得到 1。相反，我们得到的是 $9.9999999999 \times 10^{-1}$（这等于 0.9999999999）。

你可能会奇怪，为什么上一个例子中数字在没有循环数字的情况下也会产生问题。你必须记住，计算机是以 2 进制存储数字的。2.1 和 5.4 这样的数字在 2 进制中看起来是简单的，但在存储为 2 进制时它们会有循环数字。

舍入误差会导致相当意外的结果。例如，考虑以下程序：

### 4.3 条件舍入的细微差别

```java
public class Roundoff {

    public static void main(String[] args) {

        double n = 1.0;

        for (int i = 1; i <= 10; i++) {

            n += 0.1;

            System.out.println(n);

        }

    }

}
```

这是一个经典的累加和，我们在每次循环中都给数字 `n` 加上 0.1。我们从 `n` 等于 1.0 开始，循环迭代 10 次，所以它应该打印 1.1、1.2、1.3 等数字。相反，它产生了以下输出：

```text
1.1000000000000001
1.2000000000000002
1.3000000000000003
1.4000000000000001
1.5000000000000002
1.6000000000000001
1.7000000000000002
1.8000000000000003
1.9000000000000001
```



# 2.0000000000000004

问题的产生是因为 0.1 无法在 2 进制中精确存储（它会产生一组循环数字，就像三分之一在 10 进制中一样）。每次循环时误差都会累积，这就是为什么舍入误差每次都会变得糟糕。

另一个例子是考虑累加一个美分、一个五美分、一个一角和一个二十五分的任务。如果我们使用 `int` 类型的变量，无论以什么顺序相加，都会得到精确的答案：

```java
int cents1 = 1 + 5 + 10 + 25;
int cents2 = 25 + 10 + 5 + 1;

System.out.println(cents1);
System.out.println(cents2);
```

这段代码的输出如下：

```text
41
41
```

无论顺序如何，这些数字相加始终等于 41 美分。但是，假设我们不将这些值视为整数美分，而是将它们看作美元的分数并存储为：

```java
double dollars1 = 0.01 + 0.05 + 0.10 + 0.25;
double dollars2 = 0.25 + 0.10 + 0.05 + 0.01;

System.out.println(dollars1);
System.out.println(dollars2);
```

这段代码的输出如下：

```text
0.4100000000000001
0.41000000000000003
```

原因是浮点数会导致舍入误差。

## `if/else` 语句的重构（因子提取）

假设你正在编写一个游戏程序，并想根据金额给出不同的建议。以下 `if/else` 结构：

```java
if (money < 500) {
    System.out.println("You have, " + money + " left. Danger low.");
} else if (money < 1000) {
    System.out.println("You have, " + money + " left. Somewhat low.");
} else {
    System.out.println("You have, " + money + " left. In good shape.");
}
```

这段代码是重复的，可以使用称为“重构（提取）”的技术来简化。使用这种简单的技术，你可以从 `if/else` 结构的不同分支中提取出公共代码段。这里有三个不同的分支，取决于 `money` 的值。首先编写每个分支中执行的系列操作，并对它们进行比较，如图 4.8 所示。

你可以提取这种结构的顶部和底部。如果你发现每个分支顶部的语句是相同的，就将其从分支部分中提取出来，并放在分支之前。同样，如果每个分支底部的语句是相同的，就将其从分支部分中提取出来，并放在分支之后。你可以提取这些分支中的顶部语句以及两个底部的语句，如图 4.9 所示。

因此，前面的代码可以简化为以下内容，它更加简洁：

```java
System.out.println("You have, " + money + " left.");

if (money < 500) {
    System.out.print("Dangerously low. Be carefully.");
} else if (money < 1000) {
    System.out.print("Somewhat low. Bet moderately.");
} else {
    System.out.print("In good shape. Bet liberally.");
}
```

图 4.8 重构前的 `if/else` 分支

# 第 4 章 条件执行

报告金额  
取决于金额

| 金额 < 500 | 500 <= 金额 < 1000 | 金额 >= 1000 |
|---|---|---|
| 警报金额过低 | 报告金额正常 | 报告金额良好 |

提示下注  
报告下注

图 4.9

## 最大值/最小值循环

你已经看到过如何计算一个数字序列的平均值。另一个常见的编程任务是跟踪序列中的最大值和最小值。例如，月球表面的平均温度在华氏零下 50 度左右，月球显然是不宜居住的。在月球上生活的更大挑战是，温度范围从华氏零下 240 度左右到华氏摄 250 度左右。

要计算一组值序列的最大值，你可以记录目前为止看到的最大值，并使用 `if` 语句在遇到比当前最大值更大的新值时更新最大值。这种方法可以用如下伪代码进行描述：

```text
max = first

while next != "next":
    if (next > max):
        max = next
```

初始化最大值并不像听起来那么简单。例如，新手经常将 `max` 初始化为 0。但如果你正在检查的数字序列完全由负数组成怎么办？例如，你可能需要找到这个序列的最大值：

```text
-84, -7, -14, -39, -410, -17, -9
```

答案是“0”并不是这个序列中的最大值，但如果你将 `max` 初始化为 0，它将被错误地报告为最大值。

这个问题有两个经典的解决方案。首先，如果你知道正在检查的数字范围，你就可以为 `max` 有一个合适的选择。在这种情况下，你可以将 `max` 设置为该范围内的最小值。这似乎是违背直觉的，因为正常值是大的，但其思想是将 `max` 设置为它可能出现的最小值，这样任何更大的值都会导致 `max` 重置为该值。例如，如果你知道之前的数字序列是华氏度，你就知道它们永远不会小于（约华氏零下 460 度），因此你可以将 `max` 初始化为该值。

第二种可能性是将 `max` 初始化为序列中的第一个值。这并不总是方便的，因为它意味着要在循环之外获取其中一个数字。将这两种可能性结合，伪代码变为：

```text
将 max 初始化为可能的最小值或第一个值

for (all numbers to examine):
    obtain "next"

    if (next > max):
        max = next
```

计算最小值的伪代码是其稍微变体：

```text
初始化 min 为可能的最大值或第一个值

for (all numbers to examine):
    obtain "next"

    if (next < min):
        min = next
```

为了让你更好地理解这一点，让我们用一个真实的问题来应用这段伪代码。在数学中，有一个未解决的问题涉及到所谓的“冰雹序列”（hailstone sequences）。它们之所以有这个名字，是因为它们具有经常以不可预测的模式升起又落下的特性，这与形成冰雹的过程相似。

冰雹序列是一个数字序列，其中每个值 `x` 后面跟着：

```text
(3x + 1), 如果 x 是奇数

x/2, 如果 x 是偶数
```

例如，如果你从 7 开始并构建长度为 10 的序列，你会得到：

```text
7, 22, 11, 34, 17, 52, 26, 13, 40, 20
```

在这个序列中，最大值和最小值分别是 52 和 7。如果你将其扩展到长度为 20 的序列，你会得到：

```text
7, 22, 11, 34, 17, 52, 26, 13, 40, 20, 10, 5, 16, 8, 4, 2, 1, 4, 2, 1
```

在这种情况下，最大值和最小值分别是 52 和 1。你会发现，一旦到达数字 1、2 或 4 中的任何一个数字，序列就会循环自身。人们推测所有整数最终都会到达 1，就像落到地上的冰雹一样。这是数学中一个未解决的问题。没有人能反驳它，但也没有人证明它。

让我们写一个方法，接受一个起始值和一个长度，并打印由该起始值形成的冰雹序列中获得的最大值和最小值。我们的方法看起来如下：

```java
public static void printHailstoneMin(int value, int length) {
    // 可以使用起始值来初始化 max 和 min
    int min = value;
    int max = value;

    // 我们需要一个循环来生成其他值。传递给我们的参数告诉我们要循环多少次，但我们不想执行 length 次；我们必须确保迭代次数比长度少一。将这个想法与 max/min 伪代码结合，我们知道循环将是这样：
    for (int i = 1; i < length; i++) {
        // 计算下一个数字
        if (value > max) {
            max = value;
        }

        if (value < min) {
            min = value;
        }
    }

    // 打印 max 和 min
    System.out.println("max " + max);
    System.out.println("min " + min);
}
```

## 4.4 文本处理

程序员经常面临需要创建、编辑、检查和格式化文本的问题。我们统称这些任务为文本处理。

在本节中，我们将详细查看 `char` 类型并引入一个新的命令 `System.out.printf`。这些对于文本处理非常有用。

### 格式化字符串

### `char` 类型

`char` 基本类型表示单个字符。如果你愿意，变量、参数和返回值可以是 `char`。`char` 类型的字面量通过放在单引号内表示，例如：

```java
char ch = 'A';
```

创建一个表示转义序列的 `char` 值，例如：

```java
char newline = '\n';
```

在上一节中我们讨论了 `String` 对象，它可以由许多字符组成。`char` 和 `String` 之间的区别是一个困扰许多初学编程者的微妙区别。为什么对于相似的数据要有两个类型？正如你可能猜到的，`char` 的存在主要是出于历史原因；它源于影响 Java 设计的旧语言如 C。

所以在有 `String` 的情况下，为什么还会使用 `char` 类型呢？使用 `char` 是必要的，因为 Java 的某些方法将其作为参数或返回类型。但在某些情况下，使用 `char` 比使用 `String` 更有用或更简单。

`char` 的值可以用简单的算术表达式和循环来覆盖字母范围。`char` 值还可以使用关系运算符（如 `<` 或 `==`）进行比较。`String` 则不具备这些能力。例如，下面的代码打印字母表的每个字母：

```java
// 输出 abcdefghijklmnopqrstuvwxyz
for (char letter = 'a'; letter <= 'z'; letter++) {
    System.out.print(letter);
}
```

`String` 和 `char` 类型之间的主要桥梁是 `String` 对象的 `charAt` 方法，它接受一个整数索引作为参数，并返回字符串中该索引处的字符。我们通过字符拆分字符串，或者遍历字符串来检查或更改每个字符。例如，下面的循环遍历包含非空格字符的 `String`：

```java
String phrase = "rain in Spain";
String noSpaces = "";

for (int i = 0; i < phrase.length(); i++) {
    char ch = phrase.charAt(i);

    if (ch != ' ') {
        noSpaces += ch;
    }
}

// noSpaces 在此处存储 "therainSpain"
```

## 4.4 文本处理

```java
System.out.print("Type a word: ");

String s = console.next();
int count = 0;

for (int i = 0; i < s.length(); i++) {
    char ch = s.charAt(i);

    if (Character.isLetter(ch)) {
        count++;
    }
}

System.out.println("Letters: " + count);
```

以下是程序的示例执行结果：

```text
Type a word: test123TEST
Letters: 8
```

每个字符都有一个对应的整数值。当 Java 需要 `int` 类型的值时，它愿意自动将 `char` 类型的值转换为 `int`。例如，考虑以下这个奇怪的表达式：

`+ * 'a'`

Java 在期望 `int` 的地方看到了一个 `char` 类型的值，但它乐意为你为你进行转换。结果显示，'a' 的整数值为 97，因此该表达式的结果为 194。

### 表 4.4 `Character` 类的实用方法

| 方法 | 描述 | 示例 |
|---|---|---|
| `getNumericValue(ch)` | 将类似于数字的字符转换为该数字 | `Character.getNumericValue('6')` returns 6 |
| `isDigit(ch)` | 字符是否为 '0' 到 '9' 的数字之一 | `Character.isDigit('X')` returns false |
| `isLetter(ch)` | 字符是否在 'a' 到 'z' 或 'A' 到 'Z' 范围内 | `Character.isLetter('f')` returns true |
| `isLowerCase(ch)` | 字符是否为小写 | `Character.isLowerCase('Q')` returns false |
| `isUpperCase(ch)` | 字符是否为大写字母 | `Character.isUpperCase('Q')` returns true |
| `toLowerCase(ch)` | 给定字母的小写形式 | `Character.toLowerCase('q')` returns 'q' |
| `toUpperCase(ch)` | 给定字母的大写形式 | `Character.toUpperCase('x')` returns 'X' |

## 第 4 章 条件执行

然而，Java 不会自动进行反方向的转换。这是因为从某种意义上说，`char` 类型是 `int` 类型的子集。每个 `char` 值都有一个对应的 `int`，但并不是每个 `int` 都有对应的 `char`。因此，虽然 Java 可以将 `char` 转换为 `int`，但它并不总是能将 `int` 转换为 `char`。所以，在这种情况下，Java 强制要求进行类型转换（cast）。这允许你构建如下所示表达式：

```java
(char) ('a' + 3)
```

括号内部包含一个 `char` 值和一个 `int` 值，Java 将 `char` 转换为 `int`（97），然后执行加法操作，得到值 100。随后，由于强制类型转换，该整数被转换为 `char` 值，从而产生字符 'd'（即序列中排在字符 'a' 之后三个位置的字符）。

## `System.out.printf`（可选）

我们已经使用了 `System.out.println` 和 `System.out.print` 进行控制台输出。还有第三种方法 `System.out.printf`，它比其他方法复杂一点，但我们可以使用一些有用的方法。`printf` 中的 "f" 代表 "formatted（格式化）"，意味着 `System.out.printf` 让你对输出打印的格式有更多的控制。

假设你想打印一个从 1x1 到 10x10 的乘法表。下面的代码打印了正确的数字，但看起来并不好看：

```java
for (int i = 1; i <= 10; i++) {
    for (int j = 1; j <= 10; j++) {
        System.out.printf("%d * %d = %d\n", i, j, i * j);
    }
}
```

输出如下。注意，数字并没有垂直对齐：

| 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|---|---|---|---|---|---|---|---|---|---|
| 2 | 4 | 6 | 8 | 10 | 12 | 14 | 16 | 18 | 20 |
| 3 | 6 | 9 | 12 | 15 | 18 | 21 | 24 | 27 | 30 |
| 4 | 8 | 12 | 16 | 20 | 24 | 28 | 32 | 36 | 40 |
| 5 | 10 | 15 | 20 | 25 | 30 | 35 | 40 | 45 | 50 |
| 6 | 12 | 18 | 24 | 30 | 36 | 42 | 48 | 54 | 60 |
| 7 | 14 | 21 | 28 | 35 | 42 | 49 | 56 | 63 | 70 |
| 8 | 16 | 24 | 32 | 40 | 48 | 56 | 64 | 72 | 80 |
| 9 | 18 | 27 | 36 | 45 | 54 | 63 | 72 | 81 | 90 |
| 10 | 20 | 30 | 40 | 50 | 60 | 70 | 80 | 90 | 100 |

使用制表符分隔数字会更好，但数字会自动左对齐，如下方的简短表格所示：

| 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|
| 2 | 4 | 6 | 8 | 10 |
| 3 | 6 | 9 | 12 | 15 |
| 4 | 8 | 12 | 16 | 20 |
| 5 | 10 | 15 | 20 | 25 |

## 4.4 文本处理

以下代码示例使用几种格式占符来打印前面的变量：

```java
System.out.printf("hello there\n");
System.out.printf("%d and y=%d\n", x, y);
System.out.printf("%5d\n", (grade + 5));
System.out.printf("%01d%6d\n", grade, x, y);
System.out.printf("%%.2f%10f\n", angle, angle);
```



```java
System.out.printf("%8s%12s%-8s\n", veggie, veggie, veggie);
```

该代码产生输出：

```text
x=38 and y= 152

9

186      38      152

87.42    87.4

carrot   carrot !
```

让我们运行乘法表示例。现在我们可以相对容易地打印出数字右对齐的表格。我们将数字在宽度为 5 的字段中右对齐：

```java
for (int i = 1; i <= 10; i++) {
    for (int j = 1; j <= 10; j++) {
        System.out.printf("%5d", i * j);
    }
    System.out.println();
}
```

### 表 4.5 常见格式占符

| 占符 | 结果 |
| --- | --- |
| `%d` | 整数 |
| `%8d` | 整数，右对齐，8 宽宽字段 |
| `%6d` | 整数，左对齐，6 宽宽字段 |
| `%f` | 浮点数 |
| `%12f` | 浮点数，右对齐，12 宽宽字段 |
| `%.2f` | 浮点数，四舍五入到最近的百分 |
| `%16.3f` | 浮点数，四舍五入到最近的千分，16 宽宽字段 |
| `%s` | 字符串 |
| `%8s` | 字符串，右对齐，8 宽宽字段 |
| `%9s` | 字符串，左对齐，9 宽宽字段 |

## 第 4 章 条件执行

它的代码产生以下输出：

| 1 | 2 | 4 |  | 8 |  | 10 |
| 2 |  |  |  | 16 |  | 20 |
| 3 |  |  |  | 21 | 24 | 27 | 30 |
| 4 |  | 12 | 16 | 20 | 24 | 32 | 36 | 40 |
| 5 |  | 10 |  | 20 | 25 | 30 | 35 | 40 | 45 | 50 |
| 6 |  | 18 |  | 24 | 30 | 36 | 42 | 48 | 54 | 60 |
| 7 |  | 14 |  | 28 | 35 | 42 | 49 | 56 | 63 | 70 |
| 8 |  | 16 |  | 24 | 40 | 48 | 64 | 72 | 80 |
| 9 |  | 18 |  | 36 | 44 | 55 | 63 | 2 | 90 |
| 10 |  | 20 | 30 | 40 | 50 | 70 | 80 | 100 |

事实上，如果你需要的话，做一个除法表也相对简单。我们将使用 `double` 类型，并指定小数点后有限的位数（三位）：

```java
for (int i = 1; i <= 5; i++) {
    for (int j = 1; j < 5; j++) {
        System.out.printf("%.3f", (double) i / j);
    }
    System.out.println();
}
```

此代码产生以下输出：

| 1.000 | 0.500 | 0.333 | 0.250 | 0.200 |
| 2.000 | 1.000 | 0.667 | 0.500 | 0.400 |
| 3.000 | 1.500 | 1.000 | 0.750 | 0.600 |
| 4.000 | 2.000 | 1.333 | 1.000 | 0.800 |
| 5.000 | 2.500 | 1.667 | 1.250 | 1.000 |

最后一个示例是，`printf` 可以轻松解决本章早些介绍的 Roundoff 程序中的问题。固定 `double` 值的精度可以确保它会被四舍五入，以避免 `double` 运算产生的微小舍入误差。以下是修复后的程序：

```java
// 使用 System.out.printf 修正舍入误差。

public class Roundoff2 {
    public static void main(String[] args) {
        double n = 1.0;
        for (int i = 1; i <= 10; i++) {
            n = i;
            System.out.printf("%.3f\n\n", n);
        }
    }
}
```

程序产生以下输出：

## 4.5 带有条件执行的方法

我们在第 3 章介绍了许多关于方法的知识，包括如何向方法传递值以及如何使用 `return` 语句让方法返回值。现在我们引入了条件执行，我们需要重新回顾这些问题，以便你有更深入的理解。

### 前置条件和后置条件

每当你编写一个方法时，都应该考虑该方法具体要做什么。你可以通过描述执行前必须满足的前置条件和执行完成后将满足的后置条件来描述方法的工作。

> **前置条件**
>
> 方法执行前必须满足的条件，以确保其能够执行任务。

> **后置条件**
>
> 方法执行完成后保证将满足的条件，前提是调用时前置条件是成立的。

例如，为了描述汽车上某人的工作……

### 抛出异常

我们已经见过几种可能会抛出异常的情况。例如，如果你请求 0!，程序会抛出异常，因为除以零是没有定义的。

```java
throw new IllegalArgumentException();
```

当然，你只想在先决条件失败时执行此操作，因此你需要将其放在 `if` 语句内部：

```java
if (n < 0) {
    throw new IllegalArgumentException();
}
```

在构造异常时还可以包含一些文本，这些文本会在异常抛出时显示：

```java
if (n < 0) {
    throw new IllegalArgumentException("negative n");
}
```

将前置/后置注释和异常代码整合进方法中，你定义如下：

```java
// pre : n >= 0
// post : 返回 n 的阶乘 (n!)

public static int factorial(int n) {
    if (n < 0) {
        throw new IllegalArgumentException("negative n");
    }

    int product = 1;
    for (int i = 2; i <= n; i++) {
        product *= i;
    }

    return product;
}
```

在抛出异常的 `if` 之后你不需要 `else`，因为当抛出异常时，它会停止方法的执行。因此，如果有人用负值 `n` 调用 `factorial` 方法，Java 将永远不会执行 `throw` 语句之后的代码。

你可以通过以下 `main` 方法来测试它：

```java
public static void main(String[] args) {
    System.out.println(factorial(1));
}
```

当你执行此程序时，它会停止并显示以下消息：

> Exception in thread "main" java.lang.IllegalArgumentException:  
> &nbsp;&nbsp;&nbsp;&nbsp;negative n  
> &nbsp;&nbsp;&nbsp;&nbsp;at Factorial2.factorial(Factorial2.java:8)  
> &nbsp;&nbsp;&nbsp;&nbsp;at Factorial2.main(Factorial2.java:3)

该消息表示程序 `Factorial2` 停止运行，因为它抛出了一个 `IllegalArgumentException`。系统随后向你显示了到达该位置的回溯堆栈。非法参数出现在 `Factorial` 类的第 8 行。它是由于 `Factorial` 类第 3 行的调用而导致的。这种信息对于调试程序中 Bug 所在非常有帮助。

抛出异常是防御性编程的一个示例。我们并不希望在编写的程序中出现 Bug，但我们毕竟是人，所以我们想要建立一种机制，在我们出错时提供反馈。测试传递给方法的值，并在当值不合适时抛出 `IllegalArgumentException` 是提供这种反馈的极佳方法。

## 重新回顾返回值

在第 3 章中，我们查看了一些返回返回值的简单计算方法的示例，例如这个将英尺转换为英里的方法：

```java
public static double miles(double feet) {
    return feet / 5280.0;
}
```

现在你已经学会了如何编写 `if/else` 语句，我们可以查看更多涉及返回值的有趣示例。例如，在本章稍早之前，我们看到 `Math` 类有一个 `max` 方法，它会返回两个值中的较大者。实际上，该方法有两个不同的版本，一个是寻找两个整数的最大值，另一个是寻找两个浮点数的最大值。记住这被称为重载。

让我们来编写一个返回两个整数中较大值的 `max` 方法版本。它的头部看起来如下：

```java
public static int max(int x, int y) {
}
```

我们想要根据哪个较大来返回 `x` 或 `y`。这是使用 `if/else` 结构的完美位置：

```java
public static int max(int x, int y) {
    if (x > y) {
        return x;
    } else {
        return y;
    }
}
```

这段代码首先测试 `x` 是否大于 `y`。如果是，它将通过返回 `x` 来执行第一个分支。如果不是，它通过返回 `y` 来执行 `else` 分支。尽管如此，有三种情况需要考虑：`x` 可能更大，`y` 可能更大，或者它们相等。当 `x` 和 `y` 相等并执行 `return` 语句时，前面的代码会执行 `else` 分支。

记住：当 Java 执行 `return` 语句时，方法就会停止执行。这就像一条“立即离开此方法”的命令。这意味着该方法也可以写成：

```java
public static int max(int x, int y) {
    if (x > y) {
        return x;
    }

    return y;
}
```

这个版本在行为上是等价的，因为 `if` 语句内部的 `return x` 语句会导致 Java 退出方法，而不会执行 `if` 之后的 `return y` 语句。反，如果我们没有进入 `if`；就会直接进行到紧随其后的语句（`return y`）。

在你自己的程序中选择第一种形式还是第二种取决于个人喜好。`if/else` 结构更清晰地表明方法正在两个选项之间进行选择，但有些人更倾向于另一种方案，因为它更短。遗憾的是，我们不能依靠 Sun 来打破这个僵局，因为 Java 源代码使用类似于“三元运算符”的东西解决了这个问题（这是 Java 的一个小细节，你可以通过搜索“Java ternary operator”来了解）。

另一个示例是考虑 `String` 类的 `indexOf` 方法。我们定义了一个存储 `String` 的变量 `s`：

`String s = "four score and seven years ago";`

我们可以编写如下的表达式来确定特定字符出现在字符串中的位置：

```java
int r = s.indexOf('r');
int v = s.indexOf('v');
```

这段代码将 `r` 设置为 3，因为那是 `'r'` 第一次出现的索引。将 `v` 设置为 17，因为那是 `'v'` 第一次出现的索引（注：原文此处逻辑描述似乎与代码逻辑有出入，已按原意翻译）。我们可以编写如下的表达式来确定特定字符在字符串中的出现位置（修正翻译逻辑）：

```java
int r = s.indexOf('r');
int v = s.indexOf('v');
```

（注：原文提供的文本在 `indexOf` 之后存在大量重复和逻辑混乱，以下翻译已基于上下文进行了对齐处理。）

```java
for (int i = 0; i < s.length(); i++) {
    if (s.charAt(i) == ch) {
        return i;
    }
}
```

为了细化这一点，我们必须思考位置 `i` 的字符是否是我们要找的那个。记住 `String` 对象有一个 `charAt` 方法，允许我们从字符串中提取单个字符。我们完善伪代码如下：

```java
for (int i = 0; i < s.length(); i++) {
    if (s.charAt(i) == ch) {
        return;
    }
}
```

为了完成这一点，我们必须思考当我们“找到了它”时该做什么。如果我们找到了字符，我们就有了答案：变量 `i` 的值。如果那就是我们要返回的答案，我们可以在那里放一个 `return` 语句：

```java
for (int i = 0; i < s.length(); i++) {
    if (s.charAt(i) == ch) {
        return i;
    }
}
```

如果我们没有找到该字符，我们想要返回某种特殊值来表示未找到字符。我们不能使用值 0，因为 0 是 String 的合法索引（第一个字符的索引）。因此，Java 的惯例是，如果没有找到该字符，则返回 -1。在 for 循环之后添加它非常简单：

```java
public static int indexOf(char ch, String s) {
    for (int i = 0; i < s.length(); i++) {
        if (s.charAt(i) == ch) {
            return i;
        }
    }

    return -1;
}
```

## 常见的编程错误

### 索引超出范围（StringIndex out of range）

很容易忘记长度为 $n$ 的 String 的最后一个索引实际上是 $n - 1$。忘记这个事实可能会导致你写出错误的文本处理循环，如下所示：

```java
// 这个版本的代码有一个错误！
// 测试条件应该是 i < s.length()

public static int indexOf(char ch, String s) {
    for (int i = 0; i <= s.length(); i++) {
        if (s.charAt(i) == ch) {
            return i;
        }
    }

    return -1;
}
```

如果循环运行超过 String 的结尾，程序将抛出异常。在最后一次循环中，变量 `i` 的值将等于 `s.length()`，这意味着当执行 `if` 语句时，会发生异常。错误信息类似于下面：

> Exception in thread "main"  
> java.lang.StringIndexOutOfBoundsException:  
> String index out of range: 11  
> at java.lang.String.charAt(Unknown Source)  
> at OutOfBoundsExample.indexOf(OutOfBoundsExample.java:9)  
> at OutOfBoundsExample.main(OutOfBoundsExample.java:4)

这个示例中的 bug 有趣的地方在于，只有当 String 不包含字符 `ch` 时，它才会发生。如果 String 中包含 `ch`，测试对于 `s` 的其中一个合法索引将为真，代码将返回该索引。只有当 `s` 中的所有字符都经过检查且未找到 `ch` 时，循环才会尝试其最后一次致命的运行。

我们没有对最后的返回语句 `-1` 进行测试，这似乎很奇怪；但请记住，for 循环会尝试 String 的每一个可能的索引来寻找字符。如果字符出现在 String 的任何地方，循环内部的返回语句将被执行，我们永远不会到达循环后的返回语句。到达循环后返回语句的唯一方法是发现该字符没有出现在给定的 String 中。

## 4.6 案例研究：体质量指数（BMI）

近年来，计算个人的体质量指数已成为一项热门任务。疾病控制与中心（CDC）在`http://www.cdc.gov/ncdph/dnpa/bmi/`建立了一个关于体质量指数的网站。正如该网站解释过的：

> 体质量指数（BMI）是根据人的体重和身高计算出的数值。BMI 为大多数人提供了体脂率的可靠指标，并用于筛选可能导致健康问题的体重类别。

此外，比较两个或多个个人的统计数据以进行“健身挑战”，或者比较同一个人的两组数字以了解如果人在减轻体重后 BMI 将如何变化，也变得越来越流行。在本节中，我们将编写一个程序，提示用户输入两个人的身高和体重，并报告这两个人的总体结果。以下是我们编写的程序的示例执行：

此程序读取两个人的数据并计算他们的体指数和体重状态。

```text
Enter next person's information:

height (in inches)? 73.5

weight (in pounds)? 230
```

```text
Enter next person's information:

height (in inches)? 41

weight (in pounds)? 220.5
```

```text
Person #1 body mass index = 29.930121708547368

overweight

Person #2 body mass index = 30.75014878000397

obese
```



在第 1 章中，我们引入了迭代增强的概念，即分阶段开发一个复杂的程序。每位专业程序员都使用这种技术，因此学习在你自己编写的程序中应用它非常重要。

在这种情况下，我们最终希望有一个程序能够向用户解释它的功能，并为两个不同的人计算 BMI 结果。我们还希望程序结构良好。但我们不需要一次性完成所有工作。事实上，如果我们尝试这样做，可能会被细节所淹没。在编写此程序时，我们将分为三个不同的阶段：

1. 首先，我们将写一个只为一个人计算结果的程序，不包含介绍。我们暂时不担心程序的结构。
2. 接下来，我们将写一个完整的程序，计算两个人的结果，包括介绍。同样，此时我们暂不担心程序的结构。
3. 最后，我们将整合出一个结构良好且完整的程序。

# 第 4 章 条件执行

## 无结构化解决方案

即使是程序的第一个版本也需要提示身高和体重。我们将使用`Scanner`对象从控制台读取数据：

```java
public static void main(String[] args) {
    Scanner console = new Scanner(System.in);

    System.out.println("Enter next person's information:");
    System.out.print("height (in inches)? ");
    double height = console.nextDouble();

    System.out.print("weight (in pounds)? ");
    double weight = console.nextDouble();

    // ... (其余代码)
}
```

但嵌套`if/else`使用什么测试条件？如果你仔细观察之前的表格，你会发现存在一些间隙。例如，如果你的 BMI 是 24.95 呢？它既不在 18.5 到 24.9 之间，也不在 25.0 到 29.9 之间。显然，CDC 想要他们的表格解读方式不同。它可能指的是 18.5–24.999999（循环），但这在表格中看起来很奇怪。事实上，如果你理解嵌套`if/else`语句，这种情况下嵌套`if/else`结构比 CDC 那样的表格更清晰地表达可能性：

## 表 4.6 根据 BMI 的体重状态

| BMI | 体重状态 |
| :--- | :--- |
| 低于 18.5 | 体轻 |
| 18.5–24.9 | 正常 |
| 25.0–29.9 | 超重 |
| 30.0 及以上 | 肥胖 |

# 第 4 章 条件执行

```java
if (bmi < 18.5) {
    System.out.println("underweight");
} else if (bmi < 25) {
    System.out.println("normal");
} else if (bmi < 30) {
    System.out.println("overweight");
} else if (bmi > 30) {
    System.out.println("obese");
}
```

因此，将这一切整合在一起，我们得到了一个完整的程序：

```java
import java.util.*;

public class BMI {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Enter next person's information:");
        System.out.print("height (in inches) : ");
        double height = scanner.nextDouble();

        System.out.print("weight (in pounds) : ");
        double weight = scanner.nextDouble();

        double bmi = weight / (height * height) * 703;

        System.out.println("Person #1 body mass index = " + bmi);

        if (bmi < 18.5) {
            System.out.println("underweight");
        } else if (bmi < 25) {
            System.out.println("normal");
        } else if (bmi < 30) {
            System.out.println("overweight");
        } else if (bmi > 30) {
            System.out.println("obese");
        }
    }
}
```

这里是程序的示例执行结果：

```text
Enter next person's information:
height (in inches) : 73.5
weight (in pounds) : 230

Person #1 body mass index = 29.93012108547368
overweight
```

# 双人非结构化解决方案

现在我们有了一个可以计算单人 BMI 和体重状态的程序，让我们将其扩展以处理两个不同的人。经验丰富的程序员可能会在尝试处理两组数据之前就开始为程序添加结构，但对于初学者来说，先考虑非结构化的解决方案通常会有帮助。

## 4.6 案例研究：身体质量指数（BMI）

为了让此程序处理两个个人，我们可以复制并粘贴大部分代码并进行微调。例如，对于第二个人，我们可以不再使用名为`height1`、`weight1`和`bmi1`的变量，而是使用变量`height2`、`weight2`和`bmi2`。

我们还必须小心按照正确的顺序执行每一步。观察示例执行，你会发现程序会先提示两个人的数据，然后报告两个人的结果。因此，我们不能简单地复制整个程序并粘贴第二份：我们必须重新排列顺序，让所有的提示先发生，所有的报告稍后发生。

我们还决定，通过进入这一阶段，我们将添加介绍部分的代码。这段代码应该出现在程序的开头，并应该包含一个空的`println`以产生一个空行，将介绍部分与其他用户交互分开。

将这些元素组合成一个完整的程序，我们得到了：

```java
1 // 此程序查找两个
2 // 个体的身体质量指数 (BMI)。
3
4 import java.util.*;
5
6 public class BMI {
    public static void main(String[] args) {
7     System.out.println("This program reads data for two");
8     System.out.println("people and computes their body");
9     System.out.println("mass index and weight status.");
10    System.out.println();
11
12    Scanner console = new Scanner(System.in);
13
14    System.out.println("Enter next person's information:");
15    System.out.println("height (in inches)?");
16    double height1 = console.nextDouble();
17    System.out.println("weight (in pounds)?");
18    double weight1 = console.nextDouble();
19    double bmi1 = weight1 * height1 / 703;
20    System.out.println();
21
22    System.out.println("Enter next person's information:");
23    System.out.println("height (in inches)?");
24    double height2 = console.nextDouble();
25    System.out.println("weight (in pounds)?");
26    double weight2 = console.nextDouble();
27    double bmi2 = weight2 * height2 / 703;
28    System.out.println();
29
30    System.out.println("Person 1 body mass index = " +
31    bmi1);
32    if (bmi1 < 18.5) {
33        System.out.println("underweight");
34    } else if (bmi1 < 25) {
35        System.out.println("normal");
36    } else if (bmi1 < 30) {
37        System.out.println("overweight");
39    else { // bmi >= 30
40        System.out.println("obese");
41    }
42
43    System.out.println("Person #2 body mass index: \n" +
44    bmi2);
45    if (bmi2 < 18.5) {
46        System.out.println("underweight");
47    } else if (bmi2 < 25) {
48        System.out.println("normal");
49    } else if (bmi2 < 30) {
50        System.out.println("overweight");
51    } else {
52        System.out.println("obese");
53    }
54}
```

这个程序可以编译并运行。然而，我们可以通过将代码移动到方法中消除冗余。仔细研究这种变化，这种技术对于初学者来说可能是挑战性的。在编写方法时，我们必须确保它返回 BMI 结果，以便我们以后访问。

# 双人结构化解决方案

让我们探索方法如何改进结构。当我们执行此操作，我们发现我们需要这样做。我们可以通过让方法返回值来修复这个问题：

```java
public static double getBMI(Scanner console) {
    System.out.println("Enter next person's information:");
    System.out.println("height (in inches)?");
    double height = console.nextDouble();

    System.out.println("weight (in pounds)?");
    double weight = console.nextDouble();

    double bmi = weight / (height * height) * 703;
    System.out.println();

    return bmi;
}
```

在`main`方法中，我们只需调用两次方法。因为每次调用返回一个需要记住的 BMI 结果，对于每次调用，我们必须将方法返回的结果存储在变量中：

```java
double bmi1 = getBMI(console);
double bmi2 = getBMI(console);
```

但`main`方法中还有另一个明显的冗余，即相同的嵌套`if/else`出现了两次。唯一的区别是我们在一种情况下使用变量`bmi1`，在另一种情况下使用变量`bmi2`。这可以通过参数轻松地泛化：

```java
public static void reportstatus(double bmi) {
    if (bmi < 18.5) {
        System.out.println("underweight");
    } else if (bmi < 25) {
        System.out.println("normal");
    } else if (bmi < 30) {
        System.out.println("overweight");
    } else {
        System.out.println("obese");
    }
}
```

# 第 4 章 条件执行

```java
System.out.println("obese");
```

通过这种方法，我们可以将`main`方法中的代码替换为两次调用：

```java
System.out.println("Person #1 body mass index = " + bmi);

reportStatus(bmi);

System.out.println("Person #2 body mass index = " + bmi2);

reportStatus(bmi);
```

这解决了程序中的冗余问题，但我们仍然可以使用静态方法来改进程序以标明结构。如果可能，最好保持`main`方法的短小，以反映程序的整体结构。该问题可以分解为三个阶段：介绍、计算 BMI 结果。我们已经有了一个计算 BMI 的方法，但还没有引入用于介绍和报告结果的方法。添加这些方法非常简单。

程序中还有另一个有意义要添加的方法。我们使用了一个来自 CDC 网站的公式，根据个人的身高和体重来计算 BMI。每当你发现自己正在编写一个公式时，引入一个专门的公式方法是一个好主意，这样它就易于识别并有一个明确的名称。

应用这些思想，我们得到了程序的以下版本：

```java
// 此程序查找两个个体的体重指数 (BMI)。

// 此变体包含了 main 之外的其他方法。

import java.util.*;

public class BMI3 {
    public static void main(String[] args) {
        giveIntro();

        Scanner console = new Scanner(System.in);

        double bmi = getBMI(console);
        double bmi2 = getBMI(console);

        reportResults(bmi, bmi2);
    }

    // 向用户介绍程序
    public static void giveIntro() {
        System.out.println("此程序读取两个：");
        System.out.println("人的数据并计算他们的体重:");
        System.out.println("质量指数和体重状态:");
        System.out.println("");
    }

    // 提示输入一个人的统计数据，返回 BMI
    public static double getBMI(Scanner console) {
        System.out.println("输入下一个人的信息:");
        System.out.print("身高（英寸）? ");

        double height = console.nextDouble();

        System.out.print("体重（磅）? ");

        double weight = console.nextDouble();

        double bmi = BMIFor(height, weight);

        System.out.println(bmi);

        return bmi;
    }
}
```

```java
// 此方法包含体重指数公式，
// 用于将身高（英寸）和体重
//（磅）转换为 BMI

public static double BMIFor(double height, double weight) {
    return weight / (height * height);
}
```

```java
// 报告整体 bmi 值和体重状态

public static void reportResults(double bmi1, double bmi2) {
    System.out.println("Person #1 body mass index = " + bmi1);
    reportStatus(bmi1);

    System.out.println("Person #2 body mass index = " + bmi2);
    reportStatus(bmi2);
}
```

```java
// 针对给定的 BMI 值报告体重状态

public static void reportStatus(double bmi) {
    if (bmi < 18.5) {



`System.out.println("underweight");`

`} else if (bmi < 25) {`

`System.out.println("normal");`

`} else if (bmi < 30) {`

`System.out.println("overweight");`

`} else { // bmi >= 30`

`System.out.println("obese");`

`}`

`}`

这种解决方案与无结构的解决方案具有相同的行为，但结构要好得多。无结构程序在某种意义上更简单，但如果我们想扩展程序或进行其他修改，结构化的解决方案更易维护。这些结构上的优势在短程序中并不重要，但随着程序变得越来越长越来越复杂，它们变得至关重要。

## 章总结

- 累加和循环声明一个变量并在循环内部增量地增加该变量的值。
- 栅栏后循环（`fencepost loop`）通过在循环开始前执行一次循环体的一部分来执行“循环一个半”的操作。

## 第 4 章 条件执行

你编写的 `if` 语句只有在满足条件时才会执行。`if/else` 语句允许你在条件满足时执行一段代码，而在不满足时执行另一段。条件是布尔表达式，可以使用关系运算符如 `<` 和 `!=` 来编写。

出现在 `if/else` 语句每个分支中的共同代码应该被提取出来，以免在代码中多次重复出现。

`if/else` 语句可以嵌套，以测试一系列条件，并根据哪个条件为真来执行相应的代码块。

`char` 类型表示文本的单个字符。`String` 中的每个字母在内部都存储为 `char` 值，你可以使用 `String` 的 `charAt` 方法通过索引访问这些字符。

测试基本数据类型是否相等的 `==` 运算符的行为方式与我们对对象的预期的不同，因此我们通过调用它们的 `equals` 方法来测试对象的相等性。*（注：此处原文为 "doesn't behave the way we would expect objects"，翻译保留了原文的逻辑微瑕，意为“不像我们对对象的预期的那样”）*。

`System.out.printf` 方法可以格式化文本。你可以指定复杂的格式字符串来控制打印值时的宽度、对齐方式和精度。

你可以在自己的代码中“抛出”（生成）异常。这在你的代码达到无法恢复的错误条件时非常有用，例如向方法传递了无效的参数值。

由于 `double` 类型无法精确存储所有值，在执行计算时可能会发生舍入误差（`smalloff errors`，原文应为 `rounding errors`）。通过为真实数值提供微小的容差，可以避免这些问题。

### 第 4.1 节：循环技巧

1. 尝试计算从 1 到给定最大值之和的代码有什么问题？描述如何修复它使其正常工作。

```java
public static int sum(int n) {
  int sum = 0;
  for (int i = 1; i <= n; i++) {
    sum += i;
  }
  return sum;
}
```

2. 尝试打印从 1 到给定最大值数字的代码有什么问题？描述如何修复它使其正常工作。

```java
for (int i = 1; i <= n; i++) {
  System.out.print(i + ", ");
}
System.out.println(n);
```

## 自测题

3. 编写代码通过读取输入产生乘积。

### 第 4 节：if/else 语句

4. 将以下英语语句翻译为 `if/else` 语句。假设变量 `x`、`y` 和 `z` 已声明。
- `z` 是奇数。
- `y` 大于 `x`。
- `x` 和 `y` 中有一个是偶数。
- `z` 是 `y` 的倍数。
- `z` 不是 0。
- `y` 的值比 `z` 大。
- `x` 和 `z` 符号相反。
- `z` 是非负数。

5. 给以下声明，以下表达式的结果是什么？

```java
int x = 4;
int y = -3;
int z = 4;
```

6. 考虑以下 Java 方法，它返回三个参数中有几个是奇数。

```java
public static int printNum(int n1, int n2, int n3) {
    int count = 0;
    if (n1 % 2 == 1) {
        count++;
    } else if (n2 % 2 == 1) {
        count++;
    } else if (n3 % 2 == 1) {
        count++;
    }
    System.out.println(count + " of 3 numbers are odd.");
}
```

在什么情况下该方法会打印正确答案，什么时候会打印错误答案？应该如何修改代码？你能想到在不使用 `if/else` 语句的情况下正确编写代码的方法？

7. 编写代码从用户处读取一个整数，如果是偶数则打印偶，否则打印奇。假设使用了逻辑错误。

8. 以下代码

```java
Scanner console = new Scanner(System.in);
System.out.print("Type a number: ");
int number = console.nextInt();
if (number % 2 == 0) {
    if (number % 3 == 0) {
        System.out.println("Divisible by 6.");
    }
}
```

检查前面的代码，并描述一种代码会打印关于输入数字的不符合事实描述的情况。解释原因。然后修正代码修复逻辑错误。

9. 尝试返回给定整数因数个数的代码有什么问题？描述如何修复代码使其正常工作。

```java
public static int countFactors(int n) {
    for (int i = 1; i <= n; i++) {
        if (n % i == 0) { // 因数
            return i;
        }
    }
}
```

### 第 4.3 节：条件执行的细微之处

10. 以下代码结构不好：

```java
int sum = 1000;
Scanner console = new Scanner(System.in);
System.out.print("Is your multiplied 1 or 2 times? ");
int times = console.nextInt();
if (times == 2) {
    System.out.print("And how many are you contributing? ");
    int donation = console.nextInt();
    sum = sum + donation;
    count++;
    total = total + donation;
}
if (times == 2) {
    System.out.print("And how many are you contributing? ");
    int donation = console.nextInt();
}
```

# 自检题

```java
sum = sum + 2 * donation;
count2++;
total = total + donation;
}
```

请重写这段代码使其具有更好的结构并避免冗余。为了简化起见，你可以假设用户总是输入 1 或 2。（如果用户输入其他数字，代码需要如何修改？）

- 11. 下面的控制台代码结构不佳：

```java
Scanner console = new Scanner(System.in);
System.out.print("How much will John be spending?");
double amount = console.nextDouble();
System.out.println(amount);
```

```java
int nullBills1 = (int) (amount / 20.0);
if (nullBills1 * 20.0 < amount) {
   nullBills1++;
}
```

```java
System.out.print("How much will Jane be spending?");
amount = console.nextDouble();
System.out.println(amount);
```

```java
int nullBills2 = (int) (amount / 20.0);
if (nullBills2 * 20.0 < amount) {
   nullBills2++;
}
```

```java
System.out.println("John needs " + nullBills1 + " bills");
System.out.println("Jane needs " + nullBills2 + " bills");
```

重写这段代码使其具有更好的结构并避免冗余。你可能希望引入一个方法来帮助处理重复代码。

- 12. 描述以下代码的问题：

```java
Scanner console = new Scanner(System.in);
System.out.print("What is your favorite color?");
String name = console.next();
if (name.equals("blue")) {
   System.out.println("Mine, too!");
}
```

- 13. 下面代码的输出是什么？

```java
Point p1 = new Point(3, -2);
Point p2 = new Point(3, -2);
```

```java
if (p1 == p2) {
   System.out.println("equal");
} else {
   System.out.println("non-equal");
}
```

# 第 4 章 条件执行

14. 下面代码的输出是什么？

```java
Point p1 = new Point(3, -2);
Point p2 = new Point(4, 0);
if (p1.equals(p2)) {
    System.out.println("first");
}
p2.translate(-1, -2);
if (p1.equals(p2)) {
    System.out.println("second");
}
p2.translate(2, 5);
if (p1.equals(p2)) {
    System.out.println("third");
}
p2 = new Point(5, -3);
p1.translate(1, 1);
if (p1.equals(p2)) {
    System.out.println("fourth");
}
```

15. 编写一段代码，读取颜色的简写描述并打印出对应的全称。接受的颜色名称为 `B`（蓝色）、`G`（绿色）和 `R`（红色）。如果用户输入 `B`、`G` 或 `R` 以外的字符，则打印错误信息。使你的程序不区分大小写，以便用户可以使用大写或小写字母。以下是一些执行示例：

```
What color do you want? B
You have chosen Blue.

What color do you want? G
You have chosen Green.

What color do you want? Bork
Unknown color: Bork
```

16. 编写一段代码，读取扑牌的简写描述并打印出对应的全称。扑牌的简写描述是点数（2 到 10，`J`、`Q`、`K` 或 `A`）后跟其花色（`C`、`D`、`H` 或 `S`）。你可以将简写扩展为"<点数> of <花色>"的形式。你可以假设用户输入是有效的。以下是两个执行示例：

```
Enter a card: 9 S
Nine of Spades

Enter a card: K C
King of Clubs
```

17. Java 中的这个表达式应该等于 6.8，但事实并不是。为什么会发生这种情况？

```java
0.2 + 1.2 + 2.2 + 3.2
```

# 自检题

18. 下面代码本打算打印一条消息，但实际上没有输出。描述一种修复代码的方法，以便预期的消息被打印出来。

```java
double gpa = 3.2;
if (gpa + 3 == 9.6) {
    System.out.println("You earned enough credits.");
}
```

## 4.4 节：文本处理

19. 下面程序产生的输出是什么？

```java
public class CharMyMystery {
    public static void printRange(char startLetter, char endLetter) {
        char letter = startLetter;
        for (; letter <= endLetter; letter++) {
            System.out.print(letter);
        }
        System.out.println();
    }

    public static void main(String[] args) {
        printRange('e', 'g');
        printRange('n', 's');
        printRange('z', 'a');
        printRange('q', 'r');
    }
}
```

20. 写一个 `if` 语句，用于测试字符串是否以大写字母开头。

21. 下面代码有什么问题？该代码尝试统计字符串中 `'e'` 的出现次数（不区分大小写）：

```java
int count = 0;
for (int i = 0; i < s.length(); i++) {
    if (s.charAt(i).toLowerCase() == 'e') {
        count++;
    }
}
```

22. 考虑一个名为 `name` 的字符串，它存储了一个人的全名（例如 `"Marla Singer"`）。写一个表达式，输出姓氏和首字母（例如 `"Singer, M."`）。

23. 写代码检查一个字符串，并确定其中有多少字母来自字母表的后半部分（`'n'` 到 `'z'`）。比较时包含 `'Z'` 在计数。

## 4.5 节：带条件执行的方法

24. 考虑一个 `printTriangle` 方法，它接受三个代表边长的整数参数，并打印它是什么三角形。三种类型是等边、等腰和不等。等边三角形三边相等，等腰三角形两边相等，但某些整数组合不能代表有效的三角形。这些值是什么？你会如何描述 `printTriangle` 方法的前先条件？

25. 考虑一个接受学生课程百分比整数的方法，返回 0.0（不及格）到 4.0（满分）之间的分数。该方法的前先条件是什么？

26. 下面方法尝试返回三个值的中间值，但包含逻辑错误。在什么情况下方法会返回错误结果？如何修复代码？

```java
public static int median3(int n1, int n2, int n3) {
  if (n1 < n2) {
    if (n2 < n3) {
      return n2;
    } else {
      return n3;
    }
  } else {
    if (n1 < n3) {
      return n1;
    } else {
      return n3;
    }
  }
}
```

27. 上一章有一个练习要求写一个 `quadratic` 方法，寻找方程 $ax^2 + bx + c = 0$ 的根。该方法传递了 $a, b, c$ 并应用了公式。在什么情况下该方法会失效？修改 `quadratic` 方法，通过抛出异常来拒绝无效的 $a, b, c$。（如果你没有完成之前的练习，只需编写方法头部和异常代码）。

## 练习

- 1. 写一个名为 `fractionsSum` 的方法，接受整数参数 $n$，并返回序列前 $n$ 项的 `double` 类型和：

$$\sum_{i=1}^{n} \frac{1}{i^2}$$

或者说序列：
$$\frac{1}{1^2} + \frac{1}{2^2} + \frac{1}{3^2} + \frac{1}{4^2} + \dots$$

你可以假设参数 $n$ 为非负。

- 2. 写一个名为 `printFractionSum` 的方法，接受整数参数 $N$，并在控制台打印序列的前 $n$ 项：

$$S_n =$$

`printFractionSum(1)` 应该打印：

```
1
```

`printFractionSum(5)` 应该打印：

```
1 + (1/2) + (1/4) + (1/8) + (1/16)
```



你可以假设参数`$N$`为非负。整行输出。

3. 写一个名为`repl`的方法，接受字符串和一个次数作为参数，并返回多次拼接后的字符串。例如，`repl("hello", 3)`应该返回`"hellohellohello"`。如果次数小于等于 0，则应返回空字符串。

4. 写一个名为`printFactors`的方法，接受整数作为参数，并使用边界后循环（fencepost loop）打印数字的因数，用空格和`"and"`分隔。例如，24 的因数应该打印为：

```
1 and 2 and 3 and 4 and 6 and 12 and 24
```

你可以假设数字参数的值大于 0，或者作为额外挑战，如果它为 0 或负数则抛出异常。

5. 写一个名为`printLetters`的方法，接受字符串作为参数，并使用边界后循环打印字符串的字母，用逗号分隔。例如，如果参数值为`"Rabbit"`，你的代码应该打印：

```
R, a, b, b, i, t
```

如果传递空字符串`("")`，你的方法不打印任何内容。

6. 写一个名为`pow`的方法，接受基数和指数作为参数，并返回基数的指定幂。例如，`pow(3, 4)`应该返回`3 * 3 * 3 * 3`，或 81。假设基数和指数都是负数。

7. 写代码要求用户输入数字，然后打印用户提供的所有数字中的最小和最大。你可以假设用户输入的读取个数大于 0。以下是一个执行示例：

```
How many numbers do you want to enter? 4
Number 1: 5
Number 2: 11
Number 3: -2
Number 4: 0
Smallest = -2
Largest = 11
```

## 第 4 章 条件执行

8. 写一个名为`range`的方法，接受两个整数作为参数，并打印这两个参数之间的数字序列，用方括号括起来。如果第一个参数小于第二个参数，则打印递增序列；否则打印递减序列。如果两个数字相同，则在方括号中打印该数字。以下是`printRange`的一些示例调用：

```
printRange(2, 7);
printRange(19, 11);
printRange(5, 5);
```

产生的输出应当是：

```
[2, 3, 4, 5, 6, 7]
[19, 18, 17, 16, 15, 14, 13, 11]
[5]
```

9. 写一段代码来计算学生的平均分。用户将输入一行包含学生姓名、然后是成绩数量、最后是整数成绩的数量。以下是两个对话示例：

```
Enter a student record: Maria 5 72 91 84 89 78
Maria's grade is 82.8

Enter a student record: Jordan 4 86 71 62 90
Jordan's grade is 77.25
```

例如，Maria 的分是 82.8，是因为她的平均分`(72 + 91 + 84 + 89 + 78) / 5`等于 82.8。

10. 写一个名为`triangleType`的方法，接受三个代表三角形边长的整数，并打印它是什么类型的三角形。三种类型为等边三角形、等腰三角形和不等三角形。等边三角形的三边长度相等，等腰三角形的两边长度相等，而不等三角形的三边长度均不同。以下是`printTriangleType`的示例调用：

```
triangleType(5, 7, 7);
TriangleType(6, 6, 6);
TriangleType(5, 7, 8);
TriangleType(2, 18, 2);
```

产生的输出应当是：

```
isosceles
equilateral
scalene
isosceles
```

11. 写一个名为`numUnique`的方法，接受三个整数作为参数，并返回这三个整数中唯一整数的数量。例如，调用`numUnique(7, 31, 7)`应该返回 2，因为参数代表两个不同的数字（数值 7 和 31）。相比之下，调用`numUnique(6, 6, 6)`应该返回 1，因为三个参数中只有一个唯一数字（数值 6）。

12. 写一个名为`average`的方法，接受两个整数作为参数，并返回这两个整数的平均值。

13. 修改你之前练习题中通过的方法

修改你在练习 8 中通过的`pow`方法，使其仅使用第一个参数，并能够正确处理负数。例如，调用`pow(24.0, 3)`应该返回`-4.0 * -4.0 * -40.0`，而调用`pow(4.0, 22)`返回`1/16`或`0.0625`。

## 编程项目

14. 写一个名为`getGrade`的方法，接受一个代表学生课程成绩的整数，并返回学生的数值成绩。成绩可以在 0.0（不及格）到 4.0（完美）之间。假设分数范围在 0 到 100 之间，并根据以下标准划分等级：

| 分数 | 成绩 |
| :--- | :--- |
| < 60 | 0.0 |
| 60-62 | 0.7 |
| 63 | 0.8 |
| 64 | 0.9 |
| 65 | 1.0 |
| 92 | 3.7 |
| 93 | 3.8 |
| 94 | 3.9 |
| >=95 | 4.9 |

为了增加挑战，如果用户传递的成绩低于 0 或高于 100，让你的方法抛出`IllegalArgumentException`。

15. 写 Java 代码提示输入一个数字，并显示输入的字符串是否为回文（例如，正反读都相同，如`"abba"`或`"racecar"`）。

为了增加挑战，使代码不区分大小写，这样像`"Abba"`和`"Madam"`等单词将被视为回文。

16. 写一个名为`swapPairs`的方法，接受一个字符串作为参数，并返回每对相邻字母反转后的字符串。如果字符串字母数为奇数，则最后一个字母保持不变。例如，调用`swapPairs("example")`应该返回`"xemalpe"`，而调用`swapPairs("hello there")`应该返回`"ehll ohtree"`。

17. 写一个名为`wordCount`的方法，接受一个字符串作为参数，并返回字符串中的单词数。单词是一个或多个空白字符的序列（除`' '`以外的任何字符）。例如，调用`wordCount("hello")`应该返回 1，调用`wordCount("how are you?")`应该返回 3，调用`wordCount("this string has wide spaces ")`应该返回 5，而调用`wordCount("")`应该返回 0。

## 编程项目

1. 写一个程序提示三角形边长并报告三条边。
2. 写一个程序提示一个数字并用罗马数字显示它。
3. 写一个程序提示日期（月、日、年）并报告该日期是星期几。知道 1601 年 1 月 1 日是星期一可能会有所帮助。

## 第 4 章 条件执行

4. 政府通过了一项新法律：收入的前 6000 元免税，接下来的 15000 元征税率为 10%，接下来的 30000 元征税率为 20%，剩余部分征税率为 30%。写一个交互式程序提示用户输入收入并报告相应的税额。

5. 写一个程序显示杨辉三角：

```
    1
   1 1
  1 2 1
 1 3 3 1
1 4 6 4 1
1 5 10 10 5 1
1 6 15 20 15 6 1
1 7 21 35 35 21 7 1
```

## 5.1 while 循环

当它小于或等于 200 时。表面上，使用`if`语句看起来很相似

```java
int number = 1;
if (number <= 200) {
    number--;
}
```

两者的区别在于`while`循环会执行多次，循环直到测试结果为假为止。如果`if`语句只执行翻倍语句，会导致测试结果等于 2。`while`循环会执行翻倍语句，直到测试结果为假，共执行八次赋值语句，将`number`设置为值 256（大于 200 的第一个 2 的幂）。这是一个包含两个语句的`while`循环：

```java
int number = 1;
while (number <= max) {
    System.out.println("Hi there");
    number++;
}
```

这个`while`循环与`for`循环几乎相同：

```java
for (int number = 1; number <= max; number++) {
    System.out.println("Hi there");
}
```

这两个循环之间唯一的区别是变量`number`的作用域。在`while`循环中，`number`定义在循环外部的作用域中。在`for`循环中，`number`定义在循环内部。

## 寻找最小因数的循环

假设你想找到一个数字除 1 以外的最小因数。表 5.1 给出了你所寻找内容的示例。以下是关于如何实现此点的伪代码描述：

```
divisor 开始于 2;
while (divisor 的当前值无效) {
    增加 divisor 值;
}
```

表 5.1 因子示例

| 数字 | 因子 | 最小因数 |
|---|---|--- |
| 10 | 2 5 | 2 |
| 15 | 3 5 | 3 |
| 25 | 5 5 | 5 |
| 31 | 31 | 31 |
| 77 | 7 11 | 7 |

## 第 5 章程序逻辑与无限循环

你不是从 1 开始，因为你寻找的是大于 1 的第一个因数。为了完善这段伪代码，你必须对什么使因数有效更加明确。一个数字的因数在数字被除以 1 时没有余数。你可以将其重写为：

```
divisor 开始于 2;
if (number/divisor 的余数不为 0) {
  增加 divisor 值;
}
```

这里是模运算符（mod）的用法，它给出整数除法的余数。下面的`while`循环执行了此任务：

```java
int divisor = 2;
while (number % divisor != 0) {
  divisor++;
}
```

在编写`while`循环时你无疑会遇到的问题之一是著名的无限循环。考虑以下代码：

```java
int number = 1;
while (number > 0) {
  number++;
}
```

因为`number`开始是一个正值且循环使其变得更大，循环将无限持续下去。在构建`while`循环时你必须小心，避免某些代码永远不会执行完毕的情况。每当你写一个`while`循环时，都应该考虑它何时以及如何结束执行。

## 哨兵循环（Sentinel Loops）

假设你想从用户读取一系列数字并计算它们的和。你可以预先询问用户读取多少个数字，正如我们在上一章所的那样，但这并不总是方便。如果用户有一组数字要输入怎么办？一种解决方法是选取特殊的输入值来指示输入的结束。我们称之为哨兵值。

> 哨兵
> 一个指示输入结束的特殊值。

例如，你可以告诉用户输入值 -1 来停止输入数字。但你如何组织代码来使用这个哨兵呢？通常，你需要执行以下操作：

```
sum = 0;
while (还没有看到哨兵) {
  提示并读取;
  将其加入和中。
}
```

## 5.1 while 循环

### 常见编程错误

无限循环
编写一个永不终止的`while`循环相对容易，会导致循环体无限重复。容易犯这种错误的原因之一是，`while`循环不像`for`循环那样在头部有一个更新步骤。正确的更新至关重要，因为它是最终导致循环测试失败所必需。

考虑以下代码，它尝试提示用户输入一个数字，并反复打印数字除以二的结果，直到达到 0 为止。第一次尝试无法编译：

```java
Scanner console = new Scanner(System.in);
System.out.print("Type a number: ");
// 此代码无法编译
while (number > 0) {
    int number = console.nextInt();
    System.out.println(number / 2);
}
```

上述代码的问题是，变量`number`需要在循环测试的作用域内，因此它不能定义在循环内部。一种修复此编译错误的错误尝试是将初始化行剪切并粘贴到循环外部：

```java
// 此代码有一个无限循环
int number = console.nextInt(); // 移动到循环外
while (number > 0) {
    System.out.println(number / 2);
}
```

这个版本有一个无限循环；如果进入了循环，没有任何更新。每当你写一个`while`循环时，都应该考虑它何时以及如何结束执行。这个版本有一个无限循环；如果进入了循环，没有任何更新。

## 随机数

程序本质本质上是可预测的。但我们可以产生看起来随机的值。

数值虽然源于可预测的算法，但模拟了随机选择的属性。此类值被称为*伪随机*（pseudorandom），因为它们是通过算法产生的。

Java 提供了多种获取伪随机数的机制。一种方案是使用`Math`类的`random`方法获取具有以下属性的值：

```
0.0 <= Math.random() < 1.0
```

该方法提供了一种快速获取数字的方法，你可以使用乘法改变范围。Java 还提供了一个名为`Random`的类，可以使用。它包含在`java.util`包中，所以你需要在程序开头包含导入声明来使用它。`Random`对象有许多与生成伪随机数相关的方法，见表 5.2。每当你调用这些方法之一，都会生成一个新的请求类型的随机数。

要创建随机，首先构造一个`Random`对象：

```java
Random r = new Random();
```

你可以调用你的`nextInt`方法并传递一个最大整数。返回的数字 0（包含）和最大值（不包含）之间。例如，如果你调用`nextInt(100)`，将得到一个 0 到 99 之间的数字。你可以给数字加 1，使范围变为 1 到 100。

让我们看一个简单的程序，在 1 到 10 之间选取数字直到出现特定的数字。我们将使用`Random`类来构造一个生成伪随机数的对象。

| 方法 | 说明 |
| --- | --- |
| nextInt() | -2³¹ 到 (2³¹-1) 之间的随机整数 |
| nextInt(max) | 0 到 (max) 之间的随机整数 |
| nextDouble() | 0.0（包含）到1.0（不包含）之间的随机实数 |
| nextBoolean() | true 或 false 的随机逻辑值 |

我们的循环应该像所示（其中 number 是用户请求生成的数值）：

```java
int result;
while (result != number) {
```

## 第 5 章 程序逻辑与无限循环

```java
result = r.nextInt(10) + 1; // 1-10 之间的随机数
System.out.println("next number = " + result);
```

注意，我们必须在`while`循环之外声明变量`result`，因为`result`出现在`while`的测试中。之前的代码方法是正确的，但 Java 不接受。该代码会生成错误消息，提示变量`result`可能未初始化。这是一个需要**“引导”（priming）**的循环示例。

## 引导循环

在循环之前初始化变量以“启动水泵”，并确保进入循环。

我们希望将`result`设置为一个能导致进入循环的值，值的大小并不重要，只要能进入循环即可。不过，我们要小心，不要将其设置为用户可能想要生成的值，尽管在这个程序中我们处理的是 1 到 10 之间的值，因此我们可以将`result`设置为像 -1 这样明显超出该数字范围的值。我们有时将其称为“虚假（dummy）”值，因为我们实际上并没有处理它。稍后我们将看到一种不需要这种引导的`while`循环变。以下是完整的解决方案：

```java
import java.util.*;

class Pick {
    public static void main(String[] args) {
        System.out.println("This program picks numbers from ");
        System.out.println("1 to 10 until a particular number comes up.");
        
        Scanner console = new Scanner(System.in);
        Random r = new Random();

        System.out.println("Pick a number between 1 and 10 --> ");
        int number = console.nextInt();

        int result = -1;
        int count = 0;
        while (result != number) {
            result = r.nextInt(10) + 1;
            System.out.println("next number = " + result);
            count++;
        }
        System.out.println("Your number came up after " + count + " times.");
    }
}
```

取决于`Random`对象返回的数字序列，它可能会很快选到指定的数字，在下面的示例执行中：

此程序从 1 到 10 随机选取数字，直到某个特定数字出现。



```text
Pick a number between 1 and 10 --> 2
next number = 7
next number = 8
next number = 2
Your number came up after 3 times
```

或者它可能需要一段时间才能选到数字，如下面的示例执行所示：

此程序从 1 到 10 随机选取数字，直到某个特定数字出现。

```text
Pick a number between 1 and 10 --> 10
next number = 9
next number = 7
next number = 7
next number = 5
next number = 8
next number = 8
next number = 1
next number = 1
next number = 9
next number = 7
next number = 10
Your number came up after 12 times
```

## 5.2 `boolean` 布尔类型

Georgeole 是一个如此出色的逻辑学家，以 Java 甚至用他的名字命名了一个数据类型。Java 的 `boolean` 类型用于描述逻辑上的真/假关系。`boolean` 是基本类型之一，类似于 `int`、`double` 和 `char`。

在不经意间，你已经使用过 `boolean` 了。我们常见的结构——`if/else` 语句、`for` 循环和 `while` 循环——都由指定测试的表达式控制。例如，以下表达式：

```java
number % 2 == 0
```

这是一个是否被 2 整除的测试。它也是一个布尔表达式。布尔表达式旨在捕捉“真”和“假”的概念，因此 `boolean` 类型域只有两个值：`true` 和 `false` 并不意外。`true` 和 `false` 是 Java 中的关键字。它们是 `boolean` 类型的字面量。所有布尔表达式在求值时都会返回这两个字面量之一。

为了更好地理解这一点，记住这些术语对于 `int` 类型的含义。`int` 字面量包括 0、1、2 等。因为这些是 `int` 类型字面量，你可以对它们进行如下操作：

```java
int number1 = 1;
int number2 = 0;
```

### 常见编程错误

#### 误用 `Random` 对象

每当在 `Random` 对象上调用 `nextInt` 方法时，它都会创建一个新的随机整数。在尝试产生受限的随机值（例如奇数）时，一些学生错误地写了这样的代码：

```java
// 此代码包含一个 bug
Random r = new Random();

if (r.nextInt() % 2 == 0) {
    System.out.println("Even number: " + r.nextInt());
} else {
    System.out.println("Odd number: " + r.nextInt());
}
```

上面的代码在很多情况下会失败，因为 `Random` 对象产生一个随机整数用于 `if/else` 测试，然后又产生另一个用于被执行的任何 `println` 语句。例如，如果测试必须从 `Random` 对象获取一个 47 的随机值：它会发现 47 % 2 不等于 0。

以下是正确的做法：

```java
Random r = new Random();
int val = r.nextInt();
if (val % 2 == 0) {
    System.out.println("Even number: " + val);
} else {
    System.out.println("Odd number: " + val);
}
```

## 5.2 `boolean` 类型

但你可以通过使用逻辑与（AND）更轻松地表达这一点：

```java
if (number >= 1 && number <= 10) {
    doSomething();
}
```

人们经常使用“and”（和）和“or”（或）这两个词，但 Java 只允许你在严格的逻辑意义上使用。注意不要编写像下面的代码：

```java
// 此代码无法编译
if (x = 1 || x = 3) {
    doSomething();
}
```

在英语中，我们会将其读为“x 等于 1 或 2”，这对我们来说是有意义的，但对 Java 来说不是。你可能还会想写成：

```java
// 此代码无法编译
if (1 <= x <= 10) {
    doSomethingElse();
}
```

在数学中，这个表达式是有意义的，用于测试 x 是否在 1 到 10 之间（包含边界）。然而，该表达式在 Java 中是不通的。

你只能使用逻辑与、逻辑或运算符来组合一系列布尔表达式。计算机不会理解你的意思。要表达“1 或 2 或 3”的 idea，请使用逻辑或（OR）组合三个不同的布尔表达式：

```java
if (x == 1 || x == 2 || x == 3) {
    doSomething();
}
```

现在要表达“包含 1 和 10”的想法，请使用逻辑与（AND）组合两个布尔表达式：

```java
if (1 <= x && x <= 10) {
    doSomethingElse();
}
```

现在我们已经引入了 AND、OR 和 NOT 逻辑运算符，是时候重新查看我们的优先级表了。NOT 运算符位于顶部，具有最高优先级。另外两个逻辑运算符的优先级较低，低于算术运算符和关系运算符，但高于赋值运算符。AND 运算符的优先级略高于 OR 运算符。表 5.4 包含了这些新运算符。

根据这些优先级规则，当评估如下所示表达式时：

# 第 5 章 程序逻辑与无限循环

## 表 5.4 Java 运算符优先级

| 描述 | 运算符 |
| --- | --- |
| 赋值运算符 | `=` |
| 乘法运算符 | `*`, `/`, `%` |
| 加法运算符 | `+` |
| 关系运算符 | `<`, `>`, `<=`, `>=` |
| 等于运算符 | `==`, `!=` |
| 逻辑与 | `&&` |
| 逻辑或 | `||` |
| 赋值运算符 | `+=`, `-=`, `*=`, `/=`, `%` |

```java
if (test1 || test2 && test3) {
  doSomething();
}
```

计算机将先计算 NOT，然后是 AND，最后是 OR。

# 短路求值（Short-Circuited Evaluation）

在本节中，我们将探索使用逻辑运算符解决复杂的编程任务，并引入这些运算符的一个重要属性。我们将编写一个名为 `firstWord` 的方法，它接受一个 `String` 作为参数并返回字符串中的第一个单词。为了简单起见，我们约定通过空格将字符串拆分成单个单词。如果字符串完全没有单词，该方法应返回一个空字符串。以下是一些示例调用：

| 方法调用 | 返回值 |
| --- | --- |
| `firstWord("four score and years")` | `"four"` |
| `firstWord("all-one-word-here")` | `"all-one-word-here"` |
| `firstWord("lots of space here")` | `"lots"` |
| `firstWord("")` | `""` |

记住我们可以调用 `substring` 方法从字符串中提取内容。我们向 `substring` 方法传递两个参数：字符串的起始索引和子字符串结束后的索引。如果字符串存储在变量 `s` 中，我们的任务基本上简化为以下步骤：

```text
set start 到单词的第一个索引
set stop 到单词之后的索引
return s.substring(start, stop);
```

作为初步估计，让我们假设起始索引为 0。这对于以空格开头的字符串将不起作用，但它允许我们关注伪代码中的第二步。考虑一个以“four score”开头的字符串。如果我们检查字符串的单个字符及其索引，会发现以下模式：

| [0] | [1] | [2] | [3] | [4] | [5] | [6] | [7] | [8] | [9] |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 'f' | 'o' | 'u' | 'r' | ' ' | 's' | 'c' | 'o' | 'p' | '' |

我们将 `start` 设置为 0，并希望将 `stop` 设置为紧邻第一个单词结束的索引。在这个例子中，找到的单词是 "four"，它从索引 0 延伸到 3。所以，如果我们希望变量 `stop` 位于目标子字符串的之后；我们需要将其设置为索引 4，即字符串中第一个空格的位置。

我们如何找到字符串中的第一个空格？我们使用 `while` 循环。我们只需从字符串开头开始循环，直到遇到空格为止：

```text
stop = 0;
while (索引 stop 处的字符不是空格) {
    stop++;
}
```

这很容易转换为 Java 代码。将其与我们为 0 的假设结合起来，我们得到：

```java
public static String firstWord(String s) {
    int start = 0;
    int stop = 1;
    while (s.charAt(stop) != ' ') {
        stop++;
    }
    return s.substring(start, stop);
}
```

并且永远不会评估第二个测试。这防止了异常的发生，因为我们从未测试过 `s.charAt(4)` 是否为空格。

这为我们提供了方法的第二个版本：

```java
public static String firstWord(String s) {
    int start = 0;
    int stop = 0;
    while (stop < s.length() && s.charAt(stop) != ' ') {
        stop++;
    }
    return s.substring(start, stop);
}
```

但记住，我们假设第一个单词是从位置 0 开始的。情况并不一定如此。例如，如果我们传递一个以几个空格开头的字符串，这个方法将返回一个空字符串。我们需要修改代码以跳过任何前导空格。实现这一目标需要另一个循环。作为初步估计，我们可以说：

```java
int start = 0;
while (s.charAt(start) != ' ') {
    start++;
}
```

这段代码对大多数字符串都有效，但在两个重要情况下会失败。循环测试假设我们会找到非空格字符。如果字符串完全由空格组成怎么办？在这种情况下，我们将直接运行字符串末尾，产生 `StringOutOfBoundsException`。如果字符串本身是空的呢？当我们询问 `s.charAt(0)` 时会立即得到错误，因为索引 0 处没有字符。

我们可以决定这些情况构成了错误。毕竟，如果没有单词，你如何返回第一个单词呢？所以，我们可以记录一个前置条件，即字符串至少包含一个非空格字符，如果不符合则抛出异常。另一种方法是在这些情况下返回空字符串。

为了处理字符串可能为空的情况，我们需要修改循环以包含对字符串长度的测试。如果我们在循环测试的末尾添加它，就会得到：

```java
int start = 0;
while (s.charAt(start) != ' ' && start < s.length()) {
    start++;
}
```

但这段代码具有我们之前看到的相同缺陷。它本应该防止 `start` 等于字符串长度时出现问题，但当这种情况发生时，在到达长度测试之前就会抛出 `StringOutOfBoundsException`。因此，这些测试也必须反转，以利用短路求值特性。

```java
int start = 0;
while (start < s.length() && s.charAt(start) == ' ') {
    start++;
}
```

结合我们之前的代码，我们必须更改 `stop` 的初始化。我们不再想从字符串的开始搜索。相反，我们需要将 `stop` 初始化为等于 `start`。将这些部分结合，我们得到了方法的以下版本：

```java
public static String firstWord(String s) {
    int start = 0;
    while (start < s.length() && s.charAt(start) == ' ') {
        start++;
    }

    int stop = start;
    while (stop < s.length() && s.charAt(stop) != ' ') {
        stop++;
    }

    return s.substring(start, stop);
}
```

这个版本在所有情况下都有效，跳过任何前导空格，并在没有单词可返回时返回空字符串。

## 布尔变量与标志

所有的 `if/else` 语句都由布尔测试控制。测试可以是布尔变量或布尔表达式。例如，考虑以下代码：

```java
if (number > 0) {
    System.out.println("positive");
} else {
    System.out.println("not positive");
}
```

它可以被重写为：

```java
boolean positive = (number > 0);
if (positive) {
    System.out.println("positive");
} else {
    System.out.println("not positive");
}
```

使用布尔变量增加了程序的可读性，因为它们允许你为测试命名。考虑你为约会程序生成的类型代码。你可能会有一些整数变量来描述一个人的属性：比如，用于存储体质的粗略估值（1-10 级）；`IQ` 用于存储智力；`income` 用于存储年总收入；以及其他用于跟踪亲密的朋友（`another` 是 `significant other` 的缩写）。给定这些变量来指定一个人的属性，你可以开发各种适用性测试；布尔变量极大提高了代码的可读性：

```java
boolean cute = (looks >= 9);
boolean smart = (IQ > 125);
boolean rich = (income == 100000);
boolean available = (anothers == 0);
boolean awesome = cute && smart && rich &&
```

你可能会发现使用一种特殊的布尔类型，称为标志（flag）。通常我们在循环内部使用标志来记录错误条件或信号完成完成。不同的标志测试不同的条件。作为一个类比，考虑游戏中的裁判，他监视特定的违规动作并在其发生时抛出旗帜。你有时会听到解员说：“比赛中有一个标志（违规判罚）。”

让我们在上一章看到的累加和代码中引入一个标志：

```java
double sum = 0.0;
for (int i = 1; i <= totalNumber; i++) {
  System.out.print("# " + i + " ? ");
  double next = console.nextDouble();
  sum += next;
}
System.out.println("sum = ");
```

假设我们想知道总和是否变成过负数。我们可以引入一个布尔标志来记录情况：

```java
double sum = 0.0;
boolean negative = false;
for (int i = 1; i <= totalNumber; i++) {
  System.out.print("# " + i + " ? ");
  double next = console.nextDouble();
  sum += next;
  if (sum < 0) {
    negative = true;
  }
}
System.out.println("sum = " + sum);
if (negative) {
  System.out.println("Sum went negative");
} else {
  System.out.println("Sum never negative");
}
```

## 布尔

1974 年，Robert Pirsig 通过他的书《禅与心智探索》开启了一场文化潮流。对于许多学者来说，需要一段时间才能适应布尔。学者经常编写过度复杂的布尔表达式，因为他们没有理解布尔值的简洁性。我们现在通过讨论类型来加入这一文化潮流。对于理解布尔的人来说，`if/else` 版本的方法看起来很奇怪：例如，假设你想写一个方法来判断一个数字是否为偶数。它接收一个 `int` 类型的值，如果是偶数则返回 `true`，如果不是则返回 `false`。因此，该方法看起来如下：

```java
public static boolean isEven(int n) {
```

你会如何编写这个方法的主体？你可以使用模运算符查看 `n` 除以 2 的余数是否为 0。如果 `(n % 2 == 0)`，你就知道这个数字是偶数。如果不是，你就知道它不是偶数（即奇数）。该方法有一个布尔返回类型，所以你想在 `n % 2` 为 0 时返回 `true` 值，在不是时返回 `false` 值。你可以这样写这个方法：

```java
public static boolean isEven(int n) {
  if (n % 2 == 0) {
    return true;
  } else {
    return false;
  }
}
```



这样做可行，但过于冗余。前面的代码评估了表达式`(n % 2 == 0)`。该表达式是布尔的，这意味着它的结果为`true`或`false`。`if/else`语句说在评估为`true`时返回`true`，在评估为`false`时返回`false`。但为什么要使用这种结构呢？如果方法在表达式评估为`true`时返回`true`，在表达式评估为`false`时返回`false`，你完全可以直接返回表达式的值：

```java
public static boolean isEven(int n) {
  return (n % 2 == 0);
}
```

甚至这个版本还可以进一步简化，因为括号并不是必要的（尽管它们让返回的内容变得更清晰）。这段代码测试`n % 2`是否等于 0 并返回结果（等于 0 时为`true`，不等于时为`false`）。将其类比为整数。对于理解布尔的人来说，`if/else`版本的方法看起来很奇怪：

## 5.2 布尔类型

```java
if (x == 1) {
  return x;
} else if (x == 2) {
  return 2;
} else if (x == 3) {
  return 3;
} else if (x == 4) {
  return x;
} else if (x == 5) {
  return 5;
}
```

如果你总是想返回`x`的值，为什么不直接说：

```java
return x;
```

当学生在使用布尔变量时，可能会出现类似的困惑。在上一节中，我们查看了累加算法的一种变体，该算法使用一个名为`negative`的布尔变量来跟踪和是否出现过负数。我们随后使用`if/else`语句打印报告结果的消息：

```java
if (negative) {
  System.out.println("Sum went negative");
} else {
  System.out.println("Sum never went negative");
}
```

一些初学者会这样写这段代码：

```java
if (negative == true) {
  System.out.println("Sum went negative");
} else {
  System.out.println("Sum never went negative");
}
```

这种比较是没有必要的，因为`if/else`语句期望括号中是一个类型为`boolean`的表达式。布尔变量本身已经是相应的类型了，所以我们不需要测试它是否等于`true`；它要么是`true`，要么不是（在这种情况下它就是`false`）。对于理解“禅宗”（Zen）的人来说，前面的测试看起来就像说下面的代码一样多此一举：

```java
if ((negative == true) == true) {
  ...
}
```

初学者还经常编写类似下面的测试：

```java
if (negative == false) {
  ...
}
```

这更有意义，因为测试确实在做一些有用的事情，即切换了布尔变量的含义（如果变量为`false`则求值为`true`，如果变量为`true`则求值为`false`）。但取反运算符的设计就是为了进行这种布尔值的翻转，因此这种测试最好的写法是：

```java
if (!negative) {
```

你应该习惯于将感叹号读作“非”（not），所以这个测试可以读作“如果不是`negative`”。对于理解布尔禅宗（Boolean Zen）的人来说，这比思考测试`negative`是否等于`false`是更简洁的表达方式。

### 5.3 用户错误

在上一章中，你学习了良好的编程习惯是考虑方法的条件，并在方法的注释中提到它们。你还学到，在某些情况下，如果违反了前提条件（preconditions），你的代码可能会抛出异常。

对于交互式程序，最简单的方法是假设用户会提供良好的输入。然后你可以记录你的前提条件，并在用户输入不符合预期时抛出异常。通常情况下，编写不对用户输入做假设的程序更好。例如，你已经看到如果用户输入错误类型的数据，`Scanner`对象可能会抛出异常。编写能够处理用户错误的程序更好。这样的程序被称为健壮的（robust）。

> 如果一个程序在面对非法数据时仍然能够执行，则称它是健壮的。

在本节中，我们将探索如何编写健壮的交互式程序。虽然你需要理解`Scanner`类的一些特殊功能，但你可以编写健壮的代码。

### Scanner 查看

`Scanner`类的方法允许你在读取值之前进行测试。换句话说，它允许你“三思而后行”（look before you leap）。对于`Scanner`类的每个“next”方法，都有一个对应的“has”方法，告诉你是否可以执行该操作。

例如，你通常想用`Scanner`读取一个`int`。但如果用户输入了`int`以外的内容怎么办？`Scanner`有一个名为`nextInt`的方法，可以告诉你是否可以读取一个`int`。为了确定这一点，`Scanner`对象会查看下一个标记（token），并看它是否可以被解释为整数。

我们倾向于认为某些字符代表特定类型的数据，但当我们读取它们时，它们可以以不同的方式解释。下面的程序将允许我们探索这个概念：

```java
import java.util.*;

public class ExamineInput {
    public static void main(String[] args) {
        System.out.println("This program examines the ways");
        System.out.println("a token can be read.");
        System.out.println();

        Scanner console = new Scanner(System.in);

        System.out.print("token? ");
        System.out.println("hasNextInt = " + 
            console.hasNextInt());
        System.out.println(" hasNextDouble = " + 
            console.hasNextDouble());
        System.out.println(" hasNext = " + console.hasNext());

    }
}
```

让我们来看几次示例执行。当我们输入标记 348 时，会发生什么：

```text
This program examines the ways
token can be read.

token? 348
hasNextInt = true
hasNextDouble = true
hasNext = true
```

如你所料，对`hasNext`的调用返回`true`，这意味着我们可以将此标记解释为整数。`Scanner`也会允许我们将此标记解释为`double`，所以`hasNextDouble`返回`true`。但注意，`hasNext()`也返回了`true`。这意味着我们可以调用`next`方法将此标记作为`String`读入。

这是另一次执行，这次针对标记 348.2：

```text
This program examines the ways
token can be read.

token? 348.2
hasNextInt = false
hasNextDouble = true
hasNext = true
```

最后，考虑针对标记 hello 的执行：

```text
This program examines the ways
token can be read.

token? hello
hasNextInt = false
hasNextDouble = false
hasNext = true
```

## 第 5 章 程序逻辑与无限循环

```java
do {
    <statement>;
    <statement>;
}
int number = 1;
do {
    number *= 2;
} while (number <= 200);
```

此循环产生的结果与相应的`while`循环相同，变量`number`翻倍，直到其值达到 256（这是大于 200 的第一个 2 的幂）。但与`while`循环不同，`do/while`循环始终至少执行一次其控制的语句。图 5.2 显示了`do/while`循环的控制流。

例如，假设你想模拟掷两个骰子，直到得到双数（两个骰子的数字相同）。写成`do/while`循环比写成`while`循环更容易，因为你知道在得到双数之前至少掷一次骰子。为了模拟掷骰子，你需要一个`Random`对象。

```java
Random r = new Random();
```

循环的基本结构应该是：每次循环时模拟掷两个骰子，直到返回的值相同为止。第一次尝试可能如下所示，但无法编译：

```java
// 正确的想法
do {
    int roll1 = r.nextInt(6) + 1;
    int roll2 = r.nextInt(6) + 1;
} while (roll1 != roll2);
```

### 5.4 无限循环变体

这段代码无法编译，报告了两个编译器错误：

```text
Doubles.java:9: cannot find symbol
symbol: variable roll1
location: class Doubles
    while (roll1 != roll2);
```

```text
Doubles.java:9: cannot find symbol
symbol: variable roll2
location: class Doubles
    while (roll1 != roll2);
```

### 2 个错误

编译器在抱怨它不认识在`do/while`测试中看到的变量`roll1`和`roll2`。这看起来很奇怪，因为它们紧挨在测试语句上方被声明了。问题出在作用域（scope）。记住，要确定变量声明的作用域，你需要寻找包含该声明的大括号。变量`roll1`和`roll2`声明在`do/while`循环的大括号内部，但`do/while`的测试语句位于这些大括号之外，这意味着它位于变量的作用域之外。

要解决这个问题，请将变量声明在外部作用域中，以便它们可以在`do/while`测试中使用。在循环内部为变量赋值（每次循环掷骰子），但在外部作用域中声明变量：

```java
int roll1, roll2; // 在外部作用域中声明变量
do {
    // 在内部作用域中为变量赋值
    roll1 = r.nextInt(6) + 1;
    roll2 = r.nextInt(6) + 1;
} while (roll1 != roll2);
```

这段代码正确地模拟了掷两个骰子直到得到双数的过程。你可以通过添加计数器并在每次循环时打印值来改进代码。这里是一个包含所有这些元素的完整程序：

```java
1 // 此程序模拟掷两个骰子，直到
2 // 出现双数（两个数字相同的骰子）。
3
4 import java.util.*;
5 public class Doubles {
6    public static void main(String[] args) {
7        Random r = new Random();
8        int count = 0;
9        int roll1, roll2;
10       do {
11           roll1 = r.nextInt(6) + 1;
12           roll2 = r.nextInt(6) + 1;
13           System.out.println("next " + roll1 + " and " + roll2 + 
14                   + " rolls");
15
16           count++;
17       } while (roll1 != roll2);
18       System.out.println("After " + count + 
19               + " rolls");
20   }
21   }
```

## 第 5 章 程序逻辑与无限循环

这是一个示例执行结果：

```text
next roll = 3, 5
next roll = 5, 4
next roll = 1, 2
next roll = 6, 2
next roll = 3, 1
next roll = 2, 4
next roll = 3, 3
```

掷 7 次后出现双数。

在许多编程问题中使用`do/while`循环是合适的。这些循环在交互式程序中通常很有用，因为你可能至少执行一次某些操作。例如，你可能有一个允许用户多次玩游戏的循环，但你可以很确定用户会想至少玩一次。同样，如果你在和用户玩猜数字游戏，你总是必须至少获取一次猜测。

我们之前就见过这样的情况，即该程序在 1 到 10 之间选取伪随机数，直到选出一个数字为止。因为必须选出一个数字，所以`do/while`循环是合适的。`while`循环版本需要在循环之前初始化变量。而在`do/while`版本中，我们不需要初始化它，因为我们知道循环至少执行一次：

```java
import java.util.*;
public class pick2 {
    public static void main(String[] args) {
        System.out.println("This program picks numbers from");
        System.out.println("1 to 10 until a particular");
        System.out.println("number comes up.");
        System.out.println();
        System.out.print("Pick a number between 1 and 10--> ");
        int number = console.nextInt();
        int result;
        int count = 0;
        do {
            result = r.nextInt(10) + 1;
            System.out.println("next number = " + result);
            count++;
        } while (result != 1);
        System.out.println("Your number came up after " + count + " times.");
    }
}
```

注意，一如既往，我们使用大括号将多个语句转换为一个块。你可能想将变量`result`的声明移动到`do/while`循环内部，但那不可行，因为它出现在循环测试中，而测试是在大括号之外。还要注意`do/while`循环末尾的分号。分号是该循环语法中强制要求的部分。

## `break`和“永远”循环（可选）

`while`循环的测试在循环顶部，而`do/while`循环的测试在循环底部。这应该会让你思考，将测试放在循环中间是否可能理想。Java 中有一种方法可以实现，尽管它需要一些看起来过时的代码。

Java 有一个特殊的语句`break`可以退出循环。你可以用它来跳出我们讨论过的任何循环（`while`、`for`）。带有`break`语句的循环很难理解，因此通常不建议使用`break`。但`break`有一个有趣的应用，可以形成一个测试发生在中间的循环。问题是，我们仍然需要选择标准的循环结构之一（`while`、`do/while`、`for`）。一种常见的选择是使用`while`循环形成无限循环：

```java
while (true) {
  <statement>;
  ...
  <statement>;
}
```

由于布尔字面量`true`始终求值为`true`，这个`while`循环似乎在无限执行。但你可以在循环中间通过`break`语句包含一个测试。这种技术对于强制退出问题很有用。

回想在本章前面，使用了以下代码来解决“循环和半”问题：

```java
int sum = 0;
System.out.print("next integer to quit?)");
while (number = console.nextInt()) {
  sum += number;
}
System.out.println("sum = " + sum);
```

提示和读取的代码出现了两次，一次在循环之前，一次在循环底部。使用带有`break`的`while`循环，我们可以消除这种冗余。

```java
Scanner scanner = new Scanner(System.in);

int sum = 0;
while (true) {
    System.out.print("next integer to quit?");
    number = scanner.nextInt();
    if (number == -1) {
        break;
    }
    sum += number;
}
System.out.println("sum = " + sum);
```



记住，`while` 循环并不是这个循环的真实测试。真正的测试出现在中间，当我们检查 `number` 是否等于 `-1` 时，如果是，我们就 `break`。将测试放在中间使得循环问题有了更简单的解决方案。

解决此问题的另一种方法是使用不包含通常初始化、测试和更新代码的 `for` 循环。`for` 仍然需要括号和分号，但其余部分可以是空的。这导致了以下奇怪的代码：

```java
Scanner console = new Scanner(System.in);

int sum = 0;
for (;;) {
    System.out.print("next integer to quit? ");
    number = console.nextInt();
    if (number == -1) {
        break;
    }
    sum += number;
}
System.out.println("sum = " + sum);
```

`for (;;)` 的效果与 `while (true)` 循环相同。换句话说，它通常是一个无限循环，但在这种情况下是可以的，因为真正的循环测试出现在中间，并带有 `break`。

人们对这种 `for` 循环版本要么喜欢要么讨厌，通常出于相同的原因。讨厌它的人说：“这看起来太奇怪了。”喜欢它的人说：“我很高兴它看起来很奇怪，因为它明确了真正的循环测试在别处。”有些人把 `for (;;)` 视为“永远”，并将这些称为“永远循环”。

## 5.5 断言与程序逻辑

逻辑学家关注被称为断言的陈述语句。

> **断言**
>
> 一个非真即假的陈述句。

以下都是断言：

- `2 + 2` 等于 4。
- 太阳比地球大。
- `x > 45`。
- 正在下雨。
- 西班牙的雨主要下在平原上。

### 你知道吗？

关于 `break` 和“无限”循环的争议在计算机科学界一直存在。一位名叫埃德格尔·迪克斯斯特（Edsger Dijkstra）的计算机科学家在 1968 年向一本计算机科学专业人士阅读的杂志写了一封标题为《有害的 goto》的信，引发了激烈的辩论。他反对当时流行的一种编程风格，那种风格高度依赖“go to”命令，这会导致计算机从一个执行点跳转到另一个执行点。这种编程风格被批评者称为“面条代码”，因为各种 `goto` 命令导致了控制流的极不可预测。

迪克斯斯特的信包含了对结构化编程的重要辩护。Java 已经成为主流的编程风格。Java、C 和 C++ 均派源于结构化编程方法。`break` 语句是一种特殊的“goto”，它允许你提前结束循环的执行。因此，它被一些人认为是过去“坏”编程的一部分。

许多人反对对结构化编程过于追求纯洁主义。例如，计算机科学家唐纳德·努斯（Donald Knuth）认为，对于像栅栏桩循环（fencepost loops）这种情况，使用 `break` 语句可以简化代码，因此是更好的选择。

一位名叫埃利特·索洛韦（Elliot Soloway）的计算机科学家在 1983 年发表了一项研究，他注意到新手更容易通过无限循环和 `break` 来学习解决栅栏桩问题。他的研究表明，大多数程序员在考虑退出条件时比考虑继续条件时更容易思考，而且无限循环对初学者来说更直观。

这个问题的双方都有热情的支持者，辩论已经持续了数十年，因此这种争议可能会无限持续下去。个人程序员必须自己决定是否喜欢这种方式。

以下内容不属于断言（第一个是问题，第二个是命令）：

- 你有多重？
- 送我回家。

某些断言的真假取决于上下文：

- `x = 45`；这取决于 `x`。
- 正在下雨；这取决于何时以及在何地。

你可以通过提供上下文来确定它们的真或假：

- `when = 13; x > 45`
- 1776 年 7 月 4 日，在费城，正在下雨。

当你编写出正确且高效的程序时，你必须学会对你的程序进行断言，并理解这些断言为真的上下文。如果你正试图从用户处获取一个非负数，你希望断言“数字是非负数”为真。如果你使用一个简单的提示，如下所示：

```java
System.out.print("Please give me a nonnegative number > ");
double number = console.nextDouble();
// 如果 number 是非负的？
```

用户仍然可以忽略你的请求并输入一个负数。事实上，用户经常输入你意料之外的值，这通常是因为他们困惑了。由于用户输入具有不确定性，这个特定的断言有时为真，有时为假。但程序后后的某些可能依赖于该断言为真。如果你要对该数字开平方，你必须确保该数字是非负的。否则，你可能会得到一个糟糕的结果。

使用循环，你可以保证数字是非负的：

```java
System.out.print("Please give me a nonnegative number-> ");
double number = console.nextDouble();
while (number < 0.0) {
    System.out.print("That is negative. Try again -> ");
    number = console.nextDouble();
}
// 在这里 number 是非负的吗？
```

你知道在循环结束后 `number` 将是非负的；否则，你不会退出循环。只要用户提供负值，你的程序就会留在循环中并继续提示输入。

这并不意味着 `number` 在循环后应该是非负的，而是意味着 `number` 将会是非负的。通过梳理程序的逻辑，你可以看到这是一个确定性。这是一个你确定的断言。如果需要，你甚至可以证明它。这样的断言被称为**可证明断言**。

## 可证明断言

在程序执行的某个特定点可以被证明为真的断言。

可证明断言有助于识别不必要的代码。考虑以下语句：

```java
int x = 0;
if (x == 0) {
    System.out.println("This is what I expect.");
} else {
    System.out.println("how can that be?");
}
```

`if/else` 结构并不是必要的。你知道赋值语句的作用，所以你知道它将 `x` 赋值为 0。测试 `x` 是否为 0 就像是在说：“在我继续之前，我要检查一下 `2 + 2` 是否等于 4。”因为这个 `if/else` 语句部分总是执行的，你可以证明这些代码的作用与之前的代码完全相同：

```java
int x = 0;
System.out.println("This is what I expect.");
```

这段代码更简单，因此更好。程序已经足够复杂，不需要添加不必要的代码。

## 对断言进行推理

对断言的关注源于计算机科学中一个名为程序验证的领域。

### 程序验证

> 计算机科学的一个领域，涉及对程序的形式属性进行推理，以证明程序的正确性。

例如，考虑简单 `if` 语句的属性：

```java
if (<test>) {
    // test 总是为真
}
```

只有在程序执行的该特定点必须为真时，才会进入 `if` 语句体。这就是为什么你可以对 `if/else` 语句中的真值得出类似的结论：

```java
if (<test>) {
    // test 总是为真
...
} else {
    // test 永远不为真
...}
```

以及关于 `while` 循环体内部真值的结论：

```java
while (<test>) {
    // test 总是为真
}
```

在循环的情况下，你可以得出更强的结论：知道只要测试求值为真，你就会不断回到循环。因此，你可以得出结论：在循环执行完成后，测试将不再为真：

```java
while (<test>) {
    // test 在这里总是为真
}
// test 在这里永远不为真
```

测试不可能在循环之后，因为如果它为真，循环体就会被再次执行。

这些关于 `if` 语句、`if/else` 语句和 `while` 循环属性的观察为证明循环断言提供了良好的开始。通常，证明断言需要对代码的实际作用进行更深入的分析。例如，假设你有一个 `int` 类型的变量 `x`，并执行了以下语句：

```java
if (x < 0) {
    // x < 0 总是为真
    x = 0;
}
// 但 x < 0 呢？
```

你通常无法在 `if` 语句后关于 `x` 是否小于 0 得出任何结论，但如果你考虑不同的情况：如果 `x` 在 `if` 之前大于或等于 0，那么在语句执行后它仍然将大于或等于 0。如果 `x` 在 `if` 之前小于 0，那么它将等于 `-x`。当 `x` 小于 0 时，`x` 大于 0。因此，在任何情况下，你都知道在 `if` 语句执行后，`x` 将大于或等于 0。

程序员在编写程序时自然地应用这种推理。程序验证研究人员正试图以形式化、可验证的方式进行这种推理。

## 详细断言示例

为了探索断言，让我们详细查看一段代码片段以及可能对该片段提出的一系列断言。考虑以下方法：

```java
public static void printCommonPrefix(int x, int y) {
    int z = 0;
    // 点 A
    while (x != y) {
        // 点 B
        z++;
        // 点 C
        if (x > y) {
            // 点 D
            x = x / 10;
        }
    } else {
        // Point E
        y = y / 10;
    }
    // Point C
    System.out.println("common prefix = " + x);
    System.out.println("digits discarded = " + z);
}
```

该方法寻找两个数字共同的最长前导数字序列。例如，数字 32845 和 32892943 都以前缀 328 开始。此方法将计算该前缀，并报告计算过程中丢弃的数字总数。

我们将在程序执行的各个点上，将各种断言识别为“真”、“永远为假”或“有时为真/有时为假”。注释指示了关注点。我们将考虑的断言有：

通常，计算机科学家使用数学符号编写表达式，例如 `z = 0`，但我们将使用 Java 赋值来将此等值断言与给变量赋值区分开来。

我们可以将答案记录在表格中，使用“始终”、“从不”或“有时”等词。因此，我们想要填充一个如下所示的表格：

| 断言 | `x > y` | `x == y` | `z == 0` |
|---|---|---|---|
| Point A |  |  |  |

让我们从点 A 开始。这似乎位于方法执行的开始。

```java
public static void printCommonPrefix(int x, int y) {
    int z = 0;
    // Point A
```

变量 `x` 和 `y` 是参数，它们的值从方法调用中获取。可能有很多情况，所以我们并不了解 `x` 和 `y` 取值的任何信息。因此，断言 `x > y` 可能为真，但并不一定为真。同样，断言 `x == y` 在点 A 可能是真也可能是假，取决于传递给方法的值，但它并不一定为真。然而，我们在点 A 之前将局部变量 `z` 初始化为 0，因此在执行的该点，断言 `z == 0` 始终为真。因此，我们可以如下所示填充表格的第一行：

| 断言 | `x > y` | `x == y` | `z == 0` |
|---|---|---|---|
| Point A | sometimes | sometimes | always |

点 B 出现在 `while` 循环内部：

```java
while (x != y) {
    // Point B
    z++;
}
```

只有进入循环才能到达点 B，这意味着循环测试的结果为真。这意味着在点 B，`x` 不等于 `y` 是成立的，因此在那个点，断言 `x == y` 永远不会为真。但我们不知道两个值中哪一个更大。因此，断言 `x > y` 有时为真，有时为假。

你可能认为断言 `z == 0` 在点 B 会为真，因为在到达点 B 之前我们刚处过点 A，但这不是正确的答案。记住，点 B 在 `while` 循环内部。在循环的第一次迭代中，我们在点 B 之前处于点 A，但在循环的后续迭代中不是。如果你看点 B 之后的代码行，你会发现它增加了 `z`。在循环内部对变量 `z` 没有其他修改。因此，每次执行循环时，`z` 都会增加 1。所以，在循环第一次通过时，点 A 的 `z` 为 0，但在第二次迭代时为 1，第三次迭代时为 2，以此类推。因此，在点 B，断言 `z == 0` 的正确答案是“有时为假”。所以，表格的第二行应该是这样的：

| 断言 | `x > y` | `x == y` | `z == 0` |
|---|---|---|---|
| Point B | sometimes | never | sometimes |

点 C 出现在变量 `z` 的自增之后。在点 B 和点 C 之间，`x` 和 `y` 的值没有变化，因此断言 `x > y` 和 `x == y` 在点 C 适用于相同的答案。断言 `z == 0` 在自增后永远不会为真，尽管 `z` 在循环开始前初始设为 0，且循环内部对该变量没有其他操作，但一旦它被增加，它就永远不再是 0。因此，我们可以如下填充点 C 的表格：

| 断言 | `x > y` | `x == y` | `z == 0` |
|---|---|---|---|
| Point C | sometimes | never | never |

点 D 和 E 是 `while` 循环内部 `if/else` 语句的一部分，因此我们可以将其作为一个整体处理。`if/else` 语句出现在点 C 之后：

```java
// Point C
if (x > y) {
    // Point D
    x = x / 10;
} else {
    // Point E
    y = y / 10;
}
```

在点 C 和点 D、E 之间没有变量被改变。发生的是 Java 执行了一个测试并向两个方向之一进行分支。`if/else` 测试 `x` 是否大于 `y`。如果测试为真，我们就进入点 D。如果不是，我们就进入点 E。因此，对于断言 `x > y`，我们知道在点 D 为真，在点 E 永远为假。

断言 `x == y` 稍微难一点。我们知道它在点 D 永远不可能为真，但在点 E 有可能吗？仅根据 `if/else` 测试，答案可能是肯定的。记住，在点 E，断言 `x == y` 可能真也可能假。对于断言 `z == 0`，我们知道它在点 D 或 E 永远为真，因为在点 B 处已经增加了，且 `if/else` 块中对 `z` 没有修改。因此，我们可以如下填充点 D 和 E 的表格：

| 断言 | `x > y` | `x == y` | `z == 0` |
|---|---|---|---|
| Point D | always | never | never |
| Point E | never | never | never |

在点 D、E 和点 F 之间 `z` 没有变化，所以我们直接从之前的列得出答案。因此我们如下填充点 F 的表格：

| 断言 | `x > y` | `x == y` | `z == 0` |
|---|---|---|---|
| Point F | sometimes | sometimes | never |

点 G 出现在 `while` 循环之后。

只有当 `x` 等于 `y` 时才能退出 `while` 循环。因此，在点 G 我们知道断言 `x == y` 始终为真。这意味着断言 `x > y` 可能成立。断言 `z == 0` 有点诡。在点 F 它从不成立，所以你可能认为在点 G 它永远不会为真。但在到达点 G 之前我们并不一定经过点 F。我们可能根本没有进入循环，在这种情况下，我们在点 G 之前直接处于点 A。在点 A，变量 `z` 等于 0。因此，该断言的正确答案是它在点 G 有时为假。我们表格的最后一行如下：

| 断言 | `x > y` | `x == y` | `z == 0` |
|---|---|---|---|
| Point G | never | always | sometimes |

将所有内容整合，我们将如下填充表格：

| 断言 | `x > y` | `x == y` | `z == 0` |
|---|---|---|---|
| Point A | sometimes | sometimes | always |
| Point B | sometimes | never | sometimes |
| Point C | sometimes | never | never |
| Point D | always | never | never |
| Point E | never | never | never |
| Point F | sometimes | sometimes | never |
| Point G | never | always | sometimes |

## Java `assert` 语句

断言的概念在软件从业人员中已非常流行，以至于许多编程语言提供了对断言测试的支持。Java 该语言从 1.4 版本开始支持测试断言。`assert` 语句的语法如下：

```java
assert <boolean> test;
```

例如：

```java
assert (x < 0);
```

这里包含括号是为了使布尔表达式更加清晰，但它们并不是必须的。

程序员在程序中构建断言，以便让计算机检查他们所有的假设是否正确。通常情况下，我们期望这些断言能够执行成功。当断言失败时，信号着问题的出现。这意味着程序员存在逻辑错误，导致假设无法成立。如果 `assert` 语句中的布尔测试求结果为 `false`，我们就称为断言失败。当断言失败时，程序会抛出一个异常并停止执行。

测试断言的开销可能很大，因此 Java 允许你控制启用或禁用此功能。你可以在开发和测试程序时启用断言检查，以确保其正常运行；当你确定程序运行良好并想要提高速度时，可以禁用它。默认情况下，断言检查是禁用的。



### 5.6 案例研究：NumberGuess

结合无限循环、检查用户错误的能力以及随机数生成，我们可以创建一个数字游戏：计算机想一个随机数，用户尝试猜中。让我们考虑一个具有以下规则的示例游戏。

计算机想一个随机两位数，但对玩家隐藏。我们将计算以 0 开头的数字，这里接受的数字范围是 00 到 99（包含）。玩家将尝试猜计算机的数字。如果玩家猜对了，程序将报告所需的猜测次数。

为了让游戏更有趣，计算机将为错误的猜测提供提示。具体来说，计算机会告诉玩家猜测的数字中有多少个数字出现在正确答案中。数字的顺序不影响匹配。

例如，如果正确答案是 57，而玩家猜的是 73，计算机将报告有一个匹配数字，因为答案包含一个 7。如果玩家下次猜的是 75，计算机将报告有两个匹配数字。此时，玩家就知道计算机的数字必须是 57，因为 57 是唯一一个包含 75 数字的两位数。

由于玩家将进行大量的控制台输入，他们可能会误输入错误的数字或非数字标记。我们希望猜数字游戏程序对用户输入错误具有良好的健壮性。

## 第 5 章 程序逻辑与无限循环

### 不带提示的初始版本

在之前的章节中，我们讨论过迭代增强的想法。由于这是一个极具挑战性的程序，我们将分阶段处理它。程序中最困难的部分之一是在玩家猜测错误时给他们提供正确的提示。

目前，我们只需编写一个游戏，在每次猜测时告诉玩家是正确还是错误，并在游戏结束后报告猜测次数。程序目前还不对用户输入错误具有健壮性；这一点以后可以添加。

为了简化游戏，我们不再让计算机选择随机数，而是将数字固定在一个已知值上，以便于测试代码。

由于不知道玩家需要多少次才能猜中数字，看起来可能会倾向于编写出匹配以下伪代码的代码：

```
// 存在缺陷的猜数字伪代码
当 (用户还没有猜中数字) {
    提示并读取一个猜测。
    报告猜测是正确的还是错误的。
}
```

但这段伪代码的问题在于，如果你从玩家那里还没有任何猜测值，就无法开始循环。以下代码无法编译，因为变量`guess`在循环开始时没有初始化：

```
// 这段代码无法编译
int numGuesses = 0;
int number = 42; // 计算机总是选择同一个数字
int guess;

while (guess != number) {
    System.out.print("Your guess ? ");
    guess = console.nextInt();
    numGuesses++;
    System.out.println("Incorrect.");
}
```

```java
System.out.println("You got it right in " + numGuesses + " times!");
```

我们可以尝试通过为`guess`变量赋初值（将其设置为正确数字以外的值）来解决上述代码的问题。然而，一个“一与半循环”（fencepost loop）解决方案效果更好。

事实证明，游戏的主猜测循环是一个桩节点循环，在每次错误猜测后，我们必须打印一条“错误”消息（以及稍后的提示）。对于`n`次猜测，有`n-1`个提示。以下是桩节点循环的通用伪代码：

```
插一根桩。
for (栅的长度) {
    连接一些线。
    插一根桩。
}
```

### 5.6 案例研究：NumberGuess

这个特定问题是一个使用`while`循环的无限桩节点循环。让我们使用更具体的伪代码。“桩”是猜测的提示，“线”是“错误”消息：

```
// 具体的猜测伪代码
想一个数字。
询问玩家的初始猜测。

while (猜测不是正确数字) {
    告知玩家猜测是错误的，
    询问另一个猜测。
}
```

报告所需的猜测次数。

这段伪代码引导我们写了以下 Java 程序。注意，目前计算机选择了 42：

```java
import java.util.*;

public class NumberGuess {
    public static void main(String[] args) {
        Scanner console = new Scanner(System.in);
        int number = 42; // 计算机总是选择同一个数字
        int guess;
        int numGuesses = 0;

        while (guess != number) {
            System.out.print("Your guess ? ");
            guess = console.nextInt();
            numGuesses++;
            System.out.println("Incorrect.");
        }

        System.out.println("You got it right in " + numGuesses + " times!");
    }
}
```

我们可以测试目前为止的初始程序。对话如下：

```
Your guess? 65
Incorrect.
Your guess? 12
Incorrect.
Your guess? 34
Incorrect.
Your guess? 42
You got it right in 4 times.
```

## 第 5 章 程序逻辑与无限循环

```java
29      guess = console.nextInt();
30      numGuesses++;
31  )

33      System.out.println("You got it right in " +
          numGuesses + " tries.");


37      // 报告关于猜测数字中有多少位数
      // 与正确数字匹配
      public static int matches(int number, int guess) {
          int numMatches = 0;

          if (guess % 10 == number / 10 ||
              guess % 10 == number % 10) {
              //
          }

          if (guess / 10 == guess % 10 &&
              (guess % 10 == number / 10 ||
              guess % 10 == number % 10)) {
              numMatches++;
          }

          return numMatches;
      }
```

以下是执行示例日志：

尝试猜我的两位数，我会告诉你你的数字中有多少位数出现在我的数字中。

你猜的？13

错误（提示：0 个数字匹配）

你猜的？26

错误（提示：0 个数字匹配）

你猜的？78

错误（提示：1 个数字匹配）

你猜的？79

错误（提示：1 个数字匹配）

你猜的？70

错误（提示：2 个数字匹配）

你猜的？07

你用了 6 次尝试猜中了。

## 最终健壮版本

我们将对程序做的最后一个重大变化是使其对无效的输入输入具有健壮性。我们可能会遇到两种类型的错误输入：

1. 非数字标记。
2. 在（0–99）范围之外的数字。

### 5.6 案例研究：NumberGuess

让我们逐一处理这些情况。回顾本章讨论的`getInput`方法，它会反复提示用户，直到输入整数：

```java
// 直到输入有效的数字
public static int getInput(Scanner console, String prompt) {
    System.out.print(prompt);
    while (!console.hasNextInt()) {
        console.next();
        System.out.println("Not an integer; try again.");
        System.out.print(prompt);
    }
    return console.nextInt();
}
```

我们可以使用`getInput`获取 0 到 99 之间的整数。我们会反复调用`getInput`，直到返回的整数在范围内：

```java
// 直到输入范围内的数字
public static int getGuess(Scanner console) {
    int guess = getInput(console, "Your guess: ");
    while (guess < 0 || guess >= 100) {
        System.out.println("Out of range; try again.");
        guess = getInput(console, "Your guess: ");
    }
    return guess;
}
```

现在，当我们在主程序中读取用户输入时，将调用`getGuess`。这种分离输入提示的方式有助于不计数无效输入。代码的版本如下：

```java
// 带有提示功能的两位数猜数字游戏
import java.util.*;

public class NumberGuess3 {
    public static void main(String[] args) {
        getInput();
        Scanner console = new Scanner(System.in);

        // 从 0 到 99 随机选择一个数字
        Random rand = new Random();
        int number = rand.nextInt(100);

        // 获取第一个猜测
        int guess = getGuess(console);
        int numGuesses = 1;

        // 反复给出提示直到猜中
        while (guess != number) {
            int numMatches = matches(number, guess);
            System.out.println("Incorrect (hint: " + numMatches + " digits correct))");
            guess = getGuess(console);
            numGuesses++;
        }

        System.out.println("You got it right in " +
            numGuesses + " tries.");
    }

    public static void giveIntro() {
        System.out.println("尝试猜我的两位数，");
        System.out.println("我会告诉你你的数字中有");
        System.out.println("多少位数出现在我的数字中");
        System.out.println("");
    }

    // 返回两个数字之间匹配的位数
    // 前提：number 和 guess 是两位数
    public static int matches(int number, int guess) {
        int numMatches = 0;
        if (guess / 10 == number / 10 ||
            guess % 10 == number % 10) {
            numMatches++;
        }
        return numMatches;
    }

    // 直到输入范围内的数字
    // 后提：guess 在 0 和 99 之间
    public static int getGuess(Scanner console) {
        int guess = getInput(console, "Your guess? ");
        while (guess < 0 || guess >= 100) {
            System.out.println("Out of range; try again.");
            guess = getInput(console, "Your guess? ");
        }
        return guess;
    }

    // 直到输入有效的数字
    public static int getInput(Scanner console, String prompt) {
        System.out.print(prompt);
        while (!console.hasNextInt()) {
            console.next();
            System.out.println("Not an integer; try again.");
            System.out.print(prompt);
        }
        return console.nextInt();
    }
}
```

## 本章总结

以下是一个执行日志，展示了新的输入健壮性：

尝试猜我的两位数，我会告诉你你的数字中有多少位数出现在我的数字中。

你猜的？13

错误（提示：0 个数字匹配）

你猜的？26

错误（提示：0 个数字匹配）

你猜的？78

错误（提示：1 个数字匹配）

你猜的？79

错误（提示：1 个数字匹配）

你猜的？70

错误（提示：2 个数字匹配）

你猜的？07

你用了 6 次尝试猜中了。

## 第 5 章 程序逻辑与无限循环

`boolean`基本类型表示逻辑值真或假。布尔表达式用于语句和循环。

`do-while`循环是`while`循环的变体，在循环体结束后执行循环测试。`do-while`循环保证至少执行一次循环体。

带有`&&`、`||`等逻辑运算符的复杂布尔测试是惰性求值的。如果从第一部分就能得出整体结果，后续部分将不会执行。这被称为短路求值。

可以写一个“无限”循环在循环体中间执行循环测试。无限循环有一个始终为真的测试，可以通过在循环体中编写特殊的`break`来退出。

布尔变量（有时称为“标志”）可以存储布尔值并用于循环测试。

断言是关于程序特定点的逻辑陈述。断言有助于证明关于程序执行的属性。两种实用的断言是前提和后提，它们是关于方法执行前后将真实的声明。

健壮的程序会检查用户输入的错误。通过在输入错误输入时循环并反复提示用户来实现更好的健壮性。`Scanner`类有`hasNextInt`可以用来“预读”有效输入。

## 自测练习

### 自测 5.1：while 循环

对于以下每个`while`循环，循环体将执行多少次？记住“零”、“无限”和“未知”都是合法答案。此外，每个代码案例的输出是什么？

```java
int x = 1;
while (x < 100) {
    System.out.print(x + " ");
    x += 10;
}

int max = 10;
while (max < 10) {
    System.out.println("count down: " + max);
    max--;
}

int x = 250;
while (x % 3 != 0) {
    System.out.println(x);
}

int x = 2;
while (x < 200) {
    System.out.print(x + " ");
    x *= x;
}
```

## 自检练习

- `String word = "a";`

  ```java
  while (word.length() < 10) {
      word = "b" + word + "b";
      System.out.println(word);
  }
  ```

- `int x = 100;`

  ```java
  while (x > 0) {
      System.out.println(x / 10);
      x = x / 2;
  }
  ```

2. 将以下每个`for`循环转换为等效的循环：

   - ```java
     for (int n = 1; n <= max; n++) {
         System.out.println(n);
     }
     ```

   - ```java
     int total = 25;

     for (int number = 1; number <= (total / 2); number++) {
         total = total - number;
         System.out.println(total + " " + number);
     }
     ```

   - ```java
     for (int i = 1; i <= 2; i++) {
         for (int j = 1; j <= 3; j++) {
             for (int k = 1; k <= 4; k++) {
                 System.out.print("*");
             }
             System.out.print("!");
         }
         System.out.println(")");
     }
     ```

   - ```java
     int number = 4;

     for (int count = 1; count <= number; count++) {
         System.out.println(number);
         number = number / 2;
     }
     ```

3. 考虑以下方法：



```java
public void mystery(int x) {
    int y = 1;
    int z = 0;
    while (2 * y <= x) {
        y *= 2;
        z++;
    }
    System.out.println(y + " " + z);
}
```

对于以下每个调用，请指示输出是什么：

- `mystery(1);`
- `mystery(6);`
- `mystery(19);`
- `mystery(39);`
- `mystery(74);`

## 第 5 章：程序逻辑与无限循环

### 4. 考虑以下方法

```java
public static void mystery(int x) {
    int y = 0;
    while (x % 2 == 0) {
        y++;
        x /= 2;
    }
    System.out.println(x + " " + y);
}
```

对于以下每个调用，请指示输出是什么：

- `mystery(19):`
- `mystery(42):`
- `mystery(48):`
- `mystery(40):`
- `mystery(64):`

### 5. 哨兵循环

编写一个哨兵循环，反复提示用户输入数字，一旦输入数字 `-1`，则显示输入的最大值和最小值。以下是一个示例对话：

```text
输入一个数字（输入 -1 停止）:5
输入一个数字（输入 -1 停止）:2
输入一个数字（输入 -1 停止）:17
输入一个数字（输入 -1 停止）:8
输入一个数字（输入 -1 停止）:-1
最大值为 17
最小值为 2
```

如果输入的第一个数字是 `-1`，则不应打印最大值或最小值。在这种情况下，对话看起来如下：

```text
输入一个数字（输入 -1 停止）:-1
```

### 6. `zeroDigits` 方法

编写一个名为 `zeroDigits` 的方法，接受一个整数并返回该数字中值为 `0` 的数字个数。例如，调用 `zeroDigits(5024036)` 应该返回 `2`，`zeroDigits(743)` 应该返回 `0`。调用 `zeroDigits(0)` 应该返回 `1`。

### 7. 打印奇位数

编写 Java 代码从用户读取一个整数，并按原始顺序打印数字所有的奇位数。这是一个示例对话：

```text
输入数字：8675309
7539860
```

### 8. 随机数范围

考虑以下代码。每个变量（`a`、`b`、`c`、`d` 和 `e`）可以具有什么取值范围？

```java
Random rand = new Random();
int a = rand.nextInt(100);
int b = rand.nextInt(20) + 50;
int c = rand.nextInt(20) + 50;
int d = rand.nextInt(100) - 20;
int e = rand.nextInt(10) * 4;
```

### 9. 生成随机整数

编写代码生成一个 0 到 100（包含边界）之间的随机整数。

### 10. 生成随机奇数

编写代码生成一个 50 到 99（包含边界）之间的随机奇数（不能被 2 整除）。

## 5.2 节：`boolean` 类型

### 11. 布尔表达式

给定以下变量声明：

```java
int x = 27;
int y = -1;
int z = 32;
boolean b = false;
```

以下每个布尔表达式的值分别是多少？

- `!b`
- `b || true`
- `(x > y) && (y > z)`
- `(x == y) && (x <= z)`
- `(x & 2 != 0) || 0 && b`
- `b && 4 != b`
- `b || !b`
- `(x < y) == b`
- `(x / 2 == 13) || b || (z * 3 == 96)`
- `(z < x) == false`
- `(x > 0) && (y < 0)`

### 12. `isVowel` 方法

编写一个名为 `isVowel` 的方法，接受一个字符，如果该字符是元音（a、e、i、o、u）则返回 `true`。额外挑战：使你的方法忽略大小写。

### 13. 检查质数

以下代码尝试检查一个数字并返回其是否为质数（即除 1 和自身外没有因子）。使用了一个名为 `prime` 的布尔标志。然而，由于逻辑未实现，方法并不总是返回正确答案。在什么情况下方法报告了错误？如何修改代码使其始终返回正确结果？

```java
public static boolean isPrime(int n) {
    boolean prime = true;
    for (int i = 2; i < n; i++) {
        if (n % i == 0) {
            prime = false;
        } else {
            prime = true;
        }
    }
    return prime;
}
```

### 14. 检查字符串是否包含字符

以下代码尝试检查一个字符串并返回它是否包含某个字母。使用了一个名为 `found` 的布尔标志。然而，由于逻辑未实现，方法并不总是返回正确答案。在什么情况下方法报告了错误？如何修改代码使其始终返回正确结果？

```java
public static boolean contains(String str, char ch) {
    boolean found = false;
    for (int i = 0; i < str.length(); i++) {
        if (str.charAt(i) == ch) {
            found = true;
        } else {
            found = false;
        }
    }
    return found;
}
```

### 15. 使用 Boolean 技巧改进方法

使用“Boolean 技巧”编写以下方法的改进版本，返回字符串开头和结尾是否为同一个字符。

```java
public static boolean startEnd(String str) {
    if (str.charAt(0) == str.charAt(str.length() - 1)) {
        return true;
    } else {
        return false;
    }
}
```

### 16. 使用 Boolean 技巧判断是否需要分币

使用“Boolean 技巧”编写以下方法的改进版本，返回给定的金额在找零时是否需要分：

```java
public static boolean hasPennies(int cents) {
    boolean nickelsOnly = (cents % 5 == 0);
    if (nickelsOnly == true) {
        return false;
    } else {
        return true;
    }
}
```

### 17. 考虑以下方法

```java
public static int mystery(int x, int y) {
    while (x != y) {
        if (x < y)
            y -= x;
        else
            x += y;
    }
    return x + y;
}
```

对于以下每个调用，指示返回了什么值：

- `mystery(3, 3)`
- `mystery(5, 3)`
- `mystery(2, 6)`
- `mystery(12, 18)`
- `mystery(30, 75)`

### 5.3 用户错误

### 18. 验证年龄和 GPA

以下代码对无效输入不健壮。描述如何修改代码，直到用户输入有效的年龄和 GPA。假设任何 `int` 都是合法的年龄，任何 `double` 都是合法的 GPA。

额外挑战：修改代码拒绝无效 GPA，例如小于 `0.0` 或大于 `4.0` 的数字。

```java
Scanner console = new Scanner(System.in);
System.out.print("输入年龄： ");
int age = console.nextInt();
System.out.print("输入 GPA： ");
double gpa = console.nextDouble();
```

### 19. 判断输入类型

考虑以下代码：

```java
Scanner console = new Scanner(System.in);
System.out.print("给我点东西！ ");
if (console.hasNextInt()) {
    int number = console.nextInt();
    System.out.println("你的 IQ 是 " + number);
} else if (console.hasNext()) {
    String token = console.next();
    System.out.println("你的名字是 " + token);
}
```

当用户输入以下值时，输出是什么？

- `Jane`
- `56`
- `56.2`

### 20. 判断整数或实数

编写一段代码，提示用户输入数字，然后根据数字是整数还是实数打印不同的消息。以下是示例对话：

```text
输入数字：42.5
你输入了实数 42.5

输入数字：3
你输入了整数 3
```

### 21. 计算三个整数的平均值

编写代码提示三个整数并计算它们的平均值。使你的代码对无效输入健壮。（你可能想使用本章讨论的 `getInt` 方法。）

## 5.4 无限循环变体

### 22. 分析 `do/while` 循环

对于每个 `do/while` 循环，循环体将执行多少次？记住“零”、“无限”和“未知”都是合法的答案。此外，在每种情况下代码的输出是什么？

```java
int x = 1;
do {
    System.out.print(x + " " + " ");
    x += 10;
} while (x < 100);

int max = 10;
do {
    System.out.println("倒计时: " + max);
    max--;
} while (max < 10);
```

```java
int x = 250;
do {
    System.out.println(x);
} while (x % 3 != 0);

int x = 100;
do {
    System.out.println(x);
    x /= 2;
} while (x % 2 == 0);

int x = 2;
do {
    System.out.print(x + " ");
    x *= x;
} while (x < 200);

String word = "a";
do {
    word = "b" + word + "b";
} while (word.length() < 10);
System.out.println(word);
```

### 23. 重复打印消息

编写一个 `do/while` 循环，反复打印消息直到用户让程序停止。`do/while` 是合适的，因为消息应该至少打印一次，即使用户在第一次消息后输入了 `n`。

```text
她在海边卖贝壳。

再次继续吗？y

她在海边卖她的贝壳。

再次继续吗？y

她在海边卖贝壳。

再次继续吗？n
```

### 24. 生成随机数直到超过 900

编写一个 `do/while` 循环，反复打印 0 到 1000 之间的随机数，直到打印出大于 900 的数字为止。每行输出都应该始终打印，即使第一个随机数大于 900。以下是示例执行：

```text
随机数：235
随机数：15
随机数：810
随机数：147
随机数：915
```

### 25. 使用 `break` 的无限循环

题目要求你编写一个哨兵循环，从控制台读取随机数，直到用户输入 `-1`，然后打印输入的最小值和最小值。重写这段代码以使用“永远”循环和 `break` 语句。以下是示例执行：

## 自测练习

```text
输入一个数字（或输入 -1 停止）：5
输入一个数字（或输入 -1 停止）：2
输入一个数字（或输入 -1 停止）：17
输入一个数字（或输入 -1 停止）：8
输入一个数字（或输入 -1 停止）：-1
最大值为 17
最小值为 2
```

## 第 5.5 节：断言与程序逻辑

### 26. 分析断言

识别以下代码中的各种断言，并判断它们在程序执行的不同点是始终为真、永远为假，还是有时为真/为假。注释指示了关注的点：

```java
public static int mystery(Scanner console, int x) {
    int y = console.nextInt();

    // 点 A
    while (y < x) {
        // 点 B
        if (y == 0) {
            count++;
            // 点 C
        }
        y = console.nextInt();
        // 点 D
    }

    // 点 E
    return count;
}
```

将每个点的每个断言分类为 `ALWAYS`（始终）、`NEVER`（永远）或 `SOMETIMES`（有时）：

|  | `y < x` | `y == 0` | `count > 0` |
|---|---|---|---|
| 点 A |  |  |  |
| 点 B |  |  |  |
| 点 C |  |  |  |
| 点 D |  |  |  |
| 点 E |  |  |  |

### 27. 分析随机数代码中的断言

识别以下代码中的各种断言，并判断它们在程序执行的不同点是始终为真、永远为假，还是有时为真/为假。注释指示了关注的点：

```java
public static int mystery(int n) {
    Random r = new Random();
    int a = r.nextInt(3) + 1;
    int b = 2;

    // 点 A
    while (n > b) {
      // 点 B
      b = b + a;

      if (a > 1) {
        // 点 C
        a = r.nextInt(b) + 1;
      } else {
        a = b + 1;

        // 点 D
      }

      // 点 E
      return n;
    }
}
```

将每个点的每个断言分类为 `ALWAYS`（始终）、`NEVER`（永远）或 `SOMETIMES`（有时）：

|  | `n > b` | `a > 1` | `b > a` |
|---|---|---|---|
| 点 A |  |  |  |
| 点 B |  |  |  |
| 点 C |  |  |  |
| 点 D |  |  |  |
| 点 E |  |  |  |

### 28. 分析相邻数字代码中的断言

识别以下代码中的各种断言，并判断它们在程序执行的不同点是始终为真、永远为假，还是有时为真/为假。注释指示了关注的点：

```java
public static int mystery(Scanner console) {
  int prev = 0;
  int count = 0;
  int next = console.nextInt();

  // 点 A
  while (next != 0) {
    // 点 B
    if (next == prev) {
      // 点 C
      count++;
    }
    prev = next;
    next = console.nextInt();
    // 点 D
  }

  // 点 E
  return count;
}
```

将每个点的每个断言分类为 `ALWAYS`、`NEVER` 或 `SOMETIMES`：

|  | `next == 0` | `prev == 0` | `next == prev` |
|---|---|---|---|
| 点 A |  |  |  |
| 点 B |  |  |  |
| 点 C |  |  |  |
| 点 D |  |  |  |
| 点 E |  |  |  |

## 练习

### 1. 输入姓名

写一个哨兵循环，反复提示用户输入姓名。一旦输入空行，显示所有输入过的姓名。例如：

```text
输入姓名（或输入空行停止-停止）：Marty
输入姓名（或输入空行停止）：Andrea
输入姓名（或输入空行停止）：Stuart
```

### 2. 计算数字平均值

写一个哨兵循环，反复提示用户输入数字。一旦输入小于 0 的数字，显示所有数字的平均值。以浮点数显示。例如：

```text
输入数字：7
输入数字：4
输入数字：16
平均值为 9.0
```

如果输入的数字是负数，不打印。例如：

```text
输入数字：-2
```

### 3. 遇到 0 时计算平均值

写一个哨兵循环，反复提示用户输入数字。一旦输入 `0`，打印所有数字的平均值。以双精度浮点数（`double`）显示。例如：

```text
输入数字：5
输入数字：9
7：0
```

### 4. 生成随机数字

写一个程序，打印 5 到 10 之间的随机数字，每行一个。例如：

```text
7
5
6
```

### 5. `makeGuesses` 方法

写一个名为 `makeGuesses` 的方法，产生 1 到 8 之间的随机数字，直到总和达到某个值。报告生成的次数。

### 6. 模拟掷骰子

写一个交互式程序，提示用户输入期望和，模拟掷骰子直到达到该和。例如：

```text
期望和：9
4
5
```

### 7. `gcd` 方法

写一个名为 `gcd` 的方法，接受两个整数并返回它们的公约数。

### 8. `showTodos` 方法

写一个名为 `showTodos` 的方法，显示给定整数的因数。例如：

```text
18：1, 2, 3, 6, 9
```

### 9. 转换为二进制或十六进制

写一个交互式程序，提示整数并以二进制显示。额外挑战：修改程序以十六进制形式显示。例如：

```text
输入数字：4
二进制是 100
```

### 10. `randomWalk` 方法

写一个名为 `randomWalk` 的方法，接受整数参数 `n` 并执行 `n` 步随机游走，报告游走过程中到达的最大位置。随机游走从位置 0 开始。在每一步中，以等概率增加或减少位置 1。输出如下：

```text
行走7步
最大位置 2
```

### 11. `season` 方法

写一个名为 `season` 的方法，接受代表月份和日的两个整数，返回相应的季节。假设月份是 1 到 12 之间的整数（1 代表 1 月，2 代表 2 月），日期是 1 到 31 之间的数字。

如果日期在 12 月到 3 月之间，返回 `"winter"`。如果在 3 月到 6 月之间，返回 `"spring"`。如果在 6 月到 9 月之间，返回 `"summer"`。如果在 9 月到 12 月之间，返回 `"fall"`。



### 12. 连续整数

写一个名为`consecutive`的方法，接受三个整数。如果它们是连续的则返回`true`；即这些数字可以排列为：假设某个整数`k`，参数值为`k`、`k + 1`和`k + 2`。如果整数不连续，则返回`false`。

注意顺序不重要；对于任何顺序的三个整数，都应返回相同的结果。

例如，调用`consecutive(1, 2, 3)`、`consecutive(3, 2, 4)`和`consecutive(-10, -8, -9)`返回`true`。调用`consecutive(3, 5, 7)`、`consecutive(1, 2, 2)`和`consecutive(7, 7, 9)`返回`false`。

### 13. 唯一整数

写一个名为`unique`的方法，接受三个整数并返回它们之间唯一整数的数量。

例如，调用`unique(18, 3, 4)`应该返回`3`，因为参数有三个不同的值。相比之下，调用`unique(6, 7, 6)`应该返回`2`，因为三个参数中只有两个唯一数字：`6`和`7`。

# 程序项目

1. 写一个交互式程序，从用户处读取行并将每行转换为“皮丁语”。皮丁语是将每个单词的初始辅音移到词尾，然后加上“ay”。以元音开头的单词末尾加上“ay”。例如，短语：

   ```
   The deepest shade of mushroom blue
   ```

   在皮丁语中的外观如下：

   ```
   e-theepest-day-shay-ay may ue-blay
   ```

   当用户输入空行时终止程序。

# 第 5 章 程序逻辑与无限循环

2. 编写一个反向猜字游戏（Hangman），用户心里想一个单词，计算机尝试猜出该单词的字母。用户告诉计算机该单词包含多少字母。

3. 编写一个与用户玩猜数字游戏的程序。程序应该生成一个 1 到某个最大值（例如 100）之间的随机数，然后反复提示用户猜数字。当用户猜错时，游戏应该提示用户正确答案是比猜的数字大还是小。一旦用户猜对数字，程序应该打印一条显示所需猜测次数的消息。

   考虑扩展此程序，使其能够进行多轮游戏，直到用户选择停止，并打印玩家总猜测次数和平均猜测数的统计数据。

4. 编写一个与用户玩反向猜数字游戏的程序。用户心里想一个 1 到 10 之间的数字，计算机通过猜随机数反复尝试猜测。计算机多次猜同一个随机数是允许的。游戏结束时，程序报告需要多少次猜测。这是一个示例输出：

   这个程序将让你（用户）选择一个 1 到 10 之间的数字，然后我（计算机）将尽力去猜它。

   ```
   Is it 8? (y/n) n
   Is it 7? (y/n) n
   Is it 5? (y/n) n
   Is it 17? (y/n) n
   Is it 8? (y/n) n
   Is it 17? (y/n) n
   Is it 9? (y/n) y
   ```

   我用了 7 次猜测猜中了你说的数字 9。

   为了增加挑战性，考虑让用户提示计算机正确数字是比计算机猜的数字大还是小。计算机应该根据提示调整其随机猜测的范围。

5. 编写一个玩多轮石头剪刀布的游戏。用户和计算机各将从三个物品中选择：石头（胜过剪刀）、布（胜过石头但输给剪刀）和剪刀（胜过布但输给石头）。如果玩家和计算机选择了同一个物品，则游戏为平局。

   该程序的扩展版本是为选择最佳物品编写不同的算法策略。计算机应该随机选择吗？它应该总是选择特定的物品或重复的模式吗？它应该统计对手选择各种物品的次数，并基于此历史制定策略吗？

# 第 6 章 文件处理

## 引言

在第 4 章中，我们讨论了如何构造`Scanner`对象从控制台读取输入。现在我们将学习如何构造`Scanner`来从文件、字符串、软件缓冲区读取输入，或者轻松地读取文本文件而不会遇到许多入门级问题。`Scanner`类使用与其他任何输入相同的文件或文本处理机制，因为异常处理对于初学者来说太高级了。

使用`Scanner`本身没有问题，但 Java 的设计并非如此，因此在没有异常处理解决方案的情况下，这会变得很有问题。由于我们还没有异常，我们用杂乱的代码来处理一些细节。对于设计了异常处理的 Java 来说，`Scanner`的读取仍然很笨拙。

在开始编写处理器之前，我们必须处理一些与 Java 异常相关的问题。记住，异常是停止程序执行的事件。在处理过程中，尝试打开一个不存在的文件或尝试读取文件结尾都会产生异常。

## 6.1 文件读取基础

- 数据，无处不在的数据
- 文件与文件对象
- 使用`Scanner`读取文件

## 6.2 基于标记的处理细节

- 文件的结构与输入的消耗
- `Scanner`参数
- 一个更复杂的输入文件

## 6.3 基于行的处理

字符串、`Scanner`与行/标记组合。

## 6.4 高级文件处理

- 输出文件
- `PrintStream`
- `try/catch`语句

## 6.5 案例研究：加权 GPA

## 6.1 文件读取基础

在本节中，我们将介绍与文件处理相关的最基础的问题。什么是文件？我们为什么要关心它们？Java 程序中最基本的技术是什么？一旦你掌握了这些，我们将进入更详细的内容。

### 数据，无处不在的数据

第一次人口普查在 1790 年迅速完成。从那时起，每十年就必须进行一次人口普查。随着人口的增长，这个过程变得越来越困难。到 1880 年，政府发现使用旧式的人工计数技术几乎无法在分配的 10 年内完成普查。因此，政府宣布了一项竞赛，让发明者提出可以加速这一过程的机器。

### 文件与文件对象

当你向计算机上存储数据时，你将其存储在：

```text
File: 信息的集合
```

每个文件都有一个名字。例如，如果你想从古登堡下载《哈姆莱特》，你可能会存储在计算机的

### 你知道吗？数据处理的起源

数据处理领域比计算机早了半个世纪。人们常说需要是发明之母，数据处理的出现是这一点的很好的例证。危机源于宪法第 1 条第 2 节的要求，该条款规定了每个州将在众议院获得多少席位。为了进行这种计算，宪法规定：“实际的人口统计应在国第一次会议后三年内，以及随后的每个十年任期内，按照法律规定的方式进行。”

## 第 6 章文件处理

### 表 6.1 常见文件扩展名

| 扩展名 | 说明 |
| --- | --- |
| `.txt` | 文本文件 |
| `.dat` | 数据文件 |
| `.out` | 输出源代码文件 |
| `.java` | Java 源代码文件 |
| `.class` | 编译后的 Java 字节码文件 |
| `.doc` | Microsoft Word 文件 |
| `.xls` | Microsoft Excel 文件 |
| `.pdf` | Adobe PDF 文档 |
| `.mp3` | 音频文件 |
| `.jpg` | 图像文件 |
| `.exe` | 可执行文件 |

要在 Java 程序内部访问一个文件，你需要构造一个表示该文件的内部对象。Java 类库包含一个名为`File`的类，它负责执行这一职责。

你通过传递文件名来构造`File`对象，例如：

```java
File f = new File("hamlet.txt");
```

一旦构造了该对象，你就可以调用许多方法来操作文件。例如，下面的程序调用了一个方法来判断文件是否存在、是否可以读取、其长度是多少（即文件中有多少个字符）以及它的绝对路径是什么（即它存储在计算机上的位置）：

```java
// 关于文件的某些基本信息。
// import java.io.*; // 用于 File
public class FileInfo {
    public static void main(String[] args) {
        File f = new File("hamlet.txt");
        System.out.println("exists returns " + f.exists());
        System.out.println("canRead returns " + f.canRead());
        System.out.println("length returns " + f.length());
        System.out.println("getAbsolutePath returns "
            + f.getAbsolutePath());
    }
}
```

注意，它包含了来自`java.io`包的导入，因为`File`类是该包的一部分。“io”（或 I/O）是科学专业人员使用的术语，意为“输入/输出”。

### 6.1 文件读取基础

#### 表 6.2 `File`对象的有用方法

| 方法 | 说明 |
| --- | --- |
| `delete()` | 删除指定的文件 |
| `exists()` | 该文件是否存在于系统 |
| `getAbsolutePath()` | 此文件所在的完整路径 |
| `getName()` | 此文件的名称（字符串），不带任何路径 |
| `isDirectory()` | 此文件是否代表系统上的目录/文件夹 |
| `isFile()` | 此文件是否代表系统上的文件（非文件夹） |
| `length()` | 此文件中的字符数 |
| `mkdir()` | 如果此文件代表的目录不存在，则创建该目录 |
| `renameTo(file)` | 将此文件的名称更改为给定的文件名 |

假设你将`hamlet.txt`文件存储在程序相同的目录中，当你运行程序时，你将得到如下输出：

```text
exists returns true
canRead returns true
length returns 191734
getAbsolutePath returns C:\data\hamlet.txt
```

6.2 列出了一些用于`File`对象的有用方法。

### 使用`Scanner`读取文件

我们从第 3 章开始一直使用的`Scanner`类非常灵活，因为`Scanner`对象可以连接到许多不同类型的输入（见图 6.1）。你可以将`Scanner`对象想象成一个水龙头，你可以将其连接到水流流经的管道上。水可以来自各种来源；例如，在家里，你会将水龙头连接到来自城市供水或井水的管道上；你也会在移动房屋和飞机等地方看到水龙头，那里的水源不同。

到目前为止，我们一直通过将`System.in`传递给`Scanner`控制台来构造它：

```java
Scanner console = new Scanner(System.in);
```

这指示计算机构造一个从控制台读取的`Scanner`（即为用户传递输入）。与其向构造函数传递`System.in`，你可以传递一个`File`对象：

```java
File f = new File("hamlet.txt");
Scanner input = new Scanner(f);
```

在这种情况下，变量`f`并不是必要的，所以我们可以将其缩短为：

```java
Scanner input = new Scanner(new File("hamlet.txt"));
```

这行代码或类似的代码将出现在你所有的文件处理程序中。当我们从控制台窗口读取时，我们将扫描器变量命名为`input`。将此变量命名为`input`是为了明确它将从一个输入文件中读取。当然，你可以为变量命名为任何名称，只要你在引用它时保持一致即可。

遗憾的是，当你尝试编译一个以这种方式构造`Scanner`的程序时，会遇到障碍。假设你写了一个`main`方法，开头如下打开一个`Scanner`：

```java
// 有缺陷的方法--无法编译
public static void main(String[] args) {
    Scanner input = new Scanner(new File("hamlet.txt"));
```

此程序无法编译。它会产生如下所示的消息：

```text
CountWords.java:8:
unreported exception java.io.FileNotFoundException:
must be caught or declared to be thrown
    Scanner input = new Scanner(new File("hamlet.txt"));
```

这个问题涉及异常，异常是在第 3 章首次引入的。请记住，异常是阻止程序继续正常执行的错误。在这种情况下，编译器担心它可能找不到`hamlet.txt`文件。如果发生了这种情况，它该怎么办呢？它将没有文件供读取，因此将没有办法继续执行其余的代码。

如果程序无法找到指定的输入文件，它将通过抛出所谓的`FileNotFoundException`来生成错误。这种特定的异常被称为**检查异常**（checked exception）。

### 检查异常

必须被捕获，或者在可能生成它的方法头中专门声明的异常。

由于`FileNotFoundException`是一个检查异常，你不能简单地忽略它。Java 提供了`try/catch`语句这种结构来处理此类错误。在本章的后面部分，你将看到如何使用这种结构，但现在你可以使用一种更高级但更简单的方法。Java 允许你避免处理此错误，只要你明确表示你没有在处理它。你只需要在`main`方法头中包含一个`throws`子句，明确说明你的方法可能会产生此异常。

### `throws`子句

用于声明一个方法将不会尝试处理特定类型的异常。

以下是修改`main`方法头以包含`throws`子句的方法，指示它可能会抛出`FileNotFoundException`。

```java
public static void main(String[] args) 
    throws FileNotFoundException {
    File f = new File("hamlet.txt");
    ...
```

## 6.2 基于标记的处理详述

### 常见编程错误

#### 忘记写`new File`

假设你没有以这种方式构造`Scanner`：

```java
Scanner input = new Scanner(new File("hamlet.txt"));
```

而是不小心忘记了包含`File`对象，写成了下面这行代码：

```java
Scanner input = new Scanner("hamlet.txt"); // 不对
```

这行代码看起来似乎是正确的，因为它提到了文件名，但它无法工作，因为没有包含`File`对象。

通常情况下，当你犯这种错误时，Java 会警告你执行了非法操作。但在这种情况下，你不会收到 Java 的任何警告。这是因为，正如你将在本章后面部分看到的，可以从一个字符串构造`Scanner`，在这种情况下，Java 会直接从字符串本身进行读取。

如果你在`CountWords`程序中犯了这个错误，你将得到以下输出：

```text
total words = 1
```

程序只会报告一个单词，因为字符串`"hamlet.txt"`在`Scanner`看来是一个单一的单词。因此，每当你构造一个本应该从输入文件中读取的`Scanner`时，确保你包含了对`new File`的调用，以构造一个合适的`File`对象。

### 6.2 基于标记的处理详述

现在我们已经介绍了读取输入文件的一些基本问题，让我们更详细地探索从文件中读取。处理文件的一种方法是逐标记（token by token）。

### 基于标记的处理

逐标记处理输入（即一次处理一个单词或一次处理一个数字）。

回想第 3 章，`Scanner`类主要的标记读取方法有：

- `nextInt`用于读取`int`值
- `nextDouble`用于读取`double`值
- `next`用于将下一个标记作为字符串（`String`）读取

## 第 6 章：文件处理

例如，你可能想创建一个名为`numbers.dat`的文件，内容如下：

```text
308.2 14.9 7.4
2.8
3.9 4.7 -15.4
2.8
```

你可以使用 Windows 机器上的记事本或 Macintosh 上的 TextEdit 等编辑器来创建这样的文件。然后，你可能会编写一个程序来处理这个输入文件并生成某种报告。例如，以下程序从文件中读取前五个数字并报告它们的总和：

```java
1 // 读取五个数字并报告其总和的程序。
2
3 import java.io.*;
4 import java.util.*;
5
6 public class ShowSum {
7     public static void main(String[] args)
8         throws FileNotFoundException {
9             Scanner input = new Scanner("numbers.dat");
10        double sum = 0.0;
11        for (int i = 1; i <= 5; i++) {
12            double next = input.nextDouble();
13            System.out.println("number " + i + " = " + next);
14            sum += next;
15        }
16        }
17        System.out.println("Sum = " + sum);
18    }
19}
```

这是第 4 章累加求的变体。记住，由于可能出现`FileNotFoundError`，你需要在`main`方法头中包含一个`throws`子句。程序产生以下输出：

```text
number 1 = 308.2
number 2 = 14.9
number 3 = 7.4
number 4 = 2.8
number 5 = 3.9
Sum = 337.2999999999999
```

注意，数字并没有报告总和为 337.2。这是舍入误差的另一个例子（在第 4 章也描述过）。

前面的程序从文件中恰好读取了五个数字。通常情况下，你会使用循环，只要还有更多数字可以读取就继续读取。`Scanner`类包含了一系列`hasNext`方法，它们与`next`方法相对应。在这种情况下，`nextDouble`被用于读取`double`类型的值，因此你可以使用`hasNext`来测试是否存在这样的值：



```java
// 读取一个数字输入文件并打印数字以及
// 它们的总和。
import java.io.*;
```

## 6.2 基于标记的处理详述

```java
import java.util.*;

public class ShowSum2 {
    public static void main(String[] args)
        throws FileNotFoundException {
        Scanner input = new Scanner(new File("numbers.dat"));

        double sum = 0.0;
        int count = 0;
        while (input.hasNextDouble()) {
            double next = input.nextDouble();
            count++;
            System.out.println("number " + count + " = " + next + "");
            sum += next;
        }
        System.out.println("Sum = " + sum);
    }
}
```

这个程序可以在包含任意数量数字的输入文件中运行。`numbers.dat` 恰好包含八个。这个版本的程序产生输出：

```
number 1 = 308.2
number 2 = 14.9
number 3 = 7.4
number 4 = 2.8
number 5 = 3.9
number 6 = 4.7
number 7 = -15.4
number 8 = 2.8
Sum = 329.299999999999
```

### 文件结构与输入消耗

我们将文件认为是二维的，但从计算机的角度来看，每个文件只是一维的字符序列。例如，考虑最后部分使用的 `numbers.dat`：

```
308.2 14.9 7.4
2.8
3.9 4.7 -15.4
2.8
```

我们认为这是一个带有六行文本且中间有两个空行的文件。然而，计算机查看的方式不同。当你在文件中输入文本并按下 Enter 键进入新行，这在文件中插入了“换行”字符。你知道可以使用转义序列 `\n` 来产生换行，可以用 `\n` 标记每行的结束：

```
308.2 14.9 7.4\n
2.8\n
```

## 第 6 章：文件处理

### 常见编程错误

#### 读取错误的标记

编写读取错误类型代码很容易。例如，`ShowSum1` 程序总是从输入文件 `numbers.dat` 读取五个 `double`。但假设输入文件中包含一些额外的文本：

```
308.2 14.9 7.4
2.8
hello
3.9 4.7
-15.4
```

文件的第一行包含三个可以正确读取的数字。但当它尝试读取第四个数字时，会发现文件的下一个标记是文本 `"hello"`。这个标记无法解释为 `double`，因此程序生成了异常：

```
number 1 = 308.2
number 2 = 14.9
number 3 = 7.4
Exception in thread "main" java.util.InputMismatchException
at java.util.Scanner.next(Scanner.java:819)
at java.util.Scanner.next(Scanner.java:1431)
at java.util.Scanner.nextDouble(Scanner.java:2335)
at ShowSum1.main(ShowSum1.java:13)
```

再次，值出现在列表的底部。最后一行指示异常发生在 `ShowSum1` 类的第 13 行。`Scanner` 类的其他行没有帮助。你之前看到过当你尝试读取文件末之外，`Scanner` 会抛出 `NoSuchElementException`。在这里，它抛出了 `InputMismatchException`。通过注意 `Scanner` 抛出的异常类型，你可以获得关于问题的更好反馈：

```
3.9 4.7 -15.4
2.8\n
```

一旦你标记了每行的结束，就不再需要使用二维表示。你可以将这些文本压缩为一维的字符序列：

```
308.2 14.9 7.4\n2.8\n3.9 4.7 -15.4\n2.8\n
```

从这个一维序列中，你可以重建文件的各个行。计算机查看文件的方式：它是一个特殊字符代表“换行”的一维字符序列。在某些系统（包括 Windows）上有不同的“换行”字符，我们将……

### 6.2 基于标记的处理详述

![](img/aea18896a4b58de45f29f5a93f7b3_368_0.png)

> 图 6.2 `Scanner` 将文件视为一维字符字符串并将其转换为一系列空白分隔的标记。

在这里使用 `\n` ——像 `Scanner` 这样的对象会处理这些差异，因此你通常可以忽略它们。（对于感兴趣的人，简单的解释是 Windows 机器以 `\r` 后跟 `\n` 结束每行。）在处理文件时，`scanner` 对象跟踪文件的当前位置。你可以将其视为文件的光标或指针。

- **输入光标**：指向输入文件中当前位置的指针。

当 `Scanner` 对象首次构造时，光标指向文件的开头。当你执行各种 `next` 操作时，光标会向前移动。最后部分的 `ShowSum2` 程序通过一系列 `nextDouble` 调用来处理文件。让我们花一点时间详细检查它是如何工作的。再次，当 `Scanner` 首次构造时，光标将位于文件的开头（用指向第一个字符的向上箭头指示）。

```
308.2 14.9 7.4\n2.8\n3.9 4.7 -15.4\n2.8\n
input
cursor
```

在第一次调用 `nextDouble` 之后，光标将位于第一行的中间，位于标记 `"308.2"` 之后。我们将此视为消耗输入。

```
308.2 14.9 7.4\n2.8\n3.9 4.7 -15.4\n2.8\n
input
cursor
```

- **消耗输入**：将输入光标向前移动过某些输入。

第一次调用 `nextDouble` 消耗输入文件中的文本 `"308.2"`，并将输入光标留在该标记后的第一个字符处。注意，这使得输入光标位于空格处。当第二次调用 `nextDouble` 时，`Scanner` 会跳过这个空格以获取下一个标记，然后消耗文本 `"14.9"` 并将光标留在随后的空格处：

# 第 6 章：文件处理

```
308.2 14.9 7.4
2.8

n3.9 4.7 -15.4
2.8
▲
input
cursor
```

如果输入为空，它会直接跳过空格并消耗文本 `"-"`。

```
308.2 14.9 7.4
2.8

n3.9 4.7 -15.4
2.8
▲
input
cursor
```

此时，输入光标位于输入第一行末尾的换行符处。第四次调用 `nextDouble` 会跳过这个换行符并消耗文本 `"2.8"`。

```
308.2 14.9 7.4
2.8

n3.9 4.7 -15.4
2.8
▲
input
cursor
```

在跳过第一个换行符时，输入光标已经移动到存储在输入第二行的数据中了。此时，输入光标位于输入第二行的末尾，因为它已经消耗了标记 `"2.8"`。当第五次调用 `nextDouble` 时，`Scanner` 发现了两个连续的换行符。这对 `Scanner` 来说并不是问题，因为它会跳过任何领先的空白字符（空格、制表符、换行符），直到找到实际的标记。因此，它跳过了这两个换行符并消耗了文本 `"3.9"`。

```
308.2 14.9 7.4
2.8

n3.9 4.7 -15.4
2.8
▲
input
cursor
```

此时，输入光标位于输入第五行的中间（第三行和第四行是空的）。程序继续以这种方式读取，消耗输入文件中的剩余数字。在读取标记 `"2.8"` 后，输入光标位于文件末尾的换行符处：

```
308.2 14.9 7.4
2.8

n3.9 4.7 -15.4
2.8
▲
input
cursor
```

如果你尝试再次调用 `nextDouble`，它将抛出 `NoSuchElementException`，因为没有剩余的标记可以读取了。但请记住，`Show2` 程序有一个 `while` 循环，在调用 `nextDouble` 之前会调用它。当你调用像 `nextDouble` 的方法时，`Scanner` 会向前查看文件以确定是否有下一个标记，以及它是否可以被解释为指定的类型（在本例中为 `double`）。因此，`Show2` 程序将继续执行，直到到达文件末尾或遇到无法解释为 `double` 的标记。

## 6.2 基于标记的处理的细节

当光标到达文件末尾的换行符时，它发现没有更多的双精度数值可以读取，并在调用 `hasNextDouble` 时返回 `false`。这停止了循环的执行并导致程序退出。

`Scanner` 对象设计用于正向处理文件。它们为查看输入文件提供了极大的灵活性，但不支持反向读取输入。没有“上一个”对应的方法，也没有将 `Scanner` 重置到输入开头的机制。

## Scanner 参数

初学者有时会惊讶，当 `Scanner` 作为参数传递给方法时，它的输入光标并不会重置到文件开头。例如，考虑以下 `ShowSum` 程序的变体。它有一个方法接收 `Scanner` 作为输入，以及一个指定要处理标记数量的整数：

```java
// 展示了作为方法参数的 Scanner，
// 它可以消耗任意数量的标记。
import java.io.*;
import java.util.*;

public class ShowSum {
    public static void main(String[] args)
    throws FileNotFoundException {
        Scanner input = new Scanner(new File("numbers.dat"));
        processTokens(input, 2);
        processTokens(input, 3);
        processTokens(input, 2);
    }

    public static void processTokens(Scanner input, int n) {
        double sum = 0.0;
        for (int i = 1; i <= n; i++) {
            double next = input.nextDouble();
            System.out.println("number = " + i + " = " + next);
            sum += next;
        }
        System.out.println("Sum = " + sum);
        System.out.println();
    }
}
```

`main` 方法创建了一个与 `numbers.dat` 文件绑定的 `Scanner` 对象。然后多次调用 `processTokens` 方法，指示要处理的标记数量。第一次调用指示方法处理两个标记。它在文件的前两个标记上操作，生成了如下输出：

```
number 1 = 308.2
number 2 = 14.9
Sum = 323.0999999999997
```

第二次调用该方法指示要处理三个标记。有些人期望该方法会处理文件的前三个标记，但事实并非如此。记住，`Scanner` 会跟踪它所在的位置。在第一次调用后，输入光标位于第二个标记的末尾。第二次调用处理文件中的下一个三个标记。

## 第 6 章：文件处理

注意，程序有两个不同的 `Scanner` 对象：一个用于通过控制台调用读取，另一个用于从文件读取。我们使用 `nextLine` 读取文件名，以获取用户输入的一整行内容。这允许用户输入包含空格的文件名。注意，尽管我们在提示用户输入文件名，但在 `main` 方法的头部中仍然需要 `throws FileNotFoundException`，因为并不一定存在名为该名称的文件。

如果我们让这个程序读取之前使用的 `numbers.dat` 文件，它将执行以下操作：

此程序将累加文件中的一系列数字。

```
number 1 = 308.2
number 2 = 14.9
number 3 = 7.4
number 4 = 2.8
number 5 = 3.9
number 6 = 4.7
number 7 = -15.4
number 8 = 2.8
Sum = 329.2999999999999
```

用户还可以指定完整的文件路径，例如：

此程序将累加文件中的一系列数字。

文件名是什么？ `C:\data\numbers.dat`

```
number 1 = 308.2
number 2 = 14.9
number 3 = 7.4
number 4 = 2.8
number 5 = 3.9
number 6 = 4.7
number 7 = -15.4
number 8 = 2.8
Sum = 329.2999999999999
```

注意，用户不需要输入两个反斜杠来获取单个反斜杠。读取用户输入的 `Scanner` 对象能够在无需转义序列的情况下读取它。

## 更复杂的输入文件

假设你有一个输入，其中包含了公司每位员工工作小时的信息。例如，它可能如下：

```text
Erica 7.5 8.5 10.25 8 8.5

Erin 10.5 11.5 12 11 10.75

Simone 8 8

Ryan 6.5 8 9.25 8

Kendall 2.5 3
```

## 6.2 基于标记的处理细节

其核心思想是你有一个每位员工工作小时的列表，你想找到每个人的工作总小时。你可以构建一个与此文件关联的 `Scanner` 对象来完成任务。当你开始编写更复杂的处理程序时，你会想要将程序分为多个方法，将代码分解为逻辑子任务。在这种情况下，你可以在 `main` 中打开文件，并编写一个单独的方法来处理文件。

大多数文件处理将涉及循环，因为你不知道文件中包含多少数据。根据正在处理的文件，需要不同的测试，但它们基本上都是关于 `Scanner` 类的各种 `hasNext*` 方法。你基本上是想说：“只要还有更多数据要处理，我们就继续读取。”

在这种情况下，你有一系列输入行，每行都以一个名字开头。对于这个程序，你可以假设名字是简单的，中间没有空格。这意味着你可以调用 `next` 方法读取每个名字。结果，`while` 循环测试涉及检查输入文件中是否还有另一个名字：

```java
while (input.hasNext()) {
    process next person.
}
```

那么，你如何处理每个人呢？你必须读取那个人的名字，然后读取那个人的小时列表。如果你查看示例输入文件，你会发现小时列表的长度并不总是相同的。例如，某些员工可能工作了五天，而另一些只工作了两或三天。这在输入文件中很常见，你可以使用嵌套循环来处理它。外层循环每次处理一个人，内层循环每次处理一个数字。任务是一个相当直接的累加和：

```java
double sum = 0.0;
while (input.hasNextDouble()) {
    sum += input.nextDouble();
}
```

将所有这些整合在一起，你得到了下面的完整程序：

```java
//1 此程序读取一个包含各种员工工作小时的输入文件
//2 并报告每个人的工作总小时。
3
4 import java.io.*;
5 import java.util.*;
6
7 public class HoursWorked {
8     public static void main(String[] args)
9         throws FileNotFoundException (
10        Scanner input = new Scanner(File("hours.dat"));
11        process(input);
12      )
13}
14    public static void process(Scanner input) {
15        while (input.hasNext()) {
16            String name = input.next();
17            double sum = 0.0;
18            while (input.hasNextDouble()) {
19                sum += input.nextDouble();
20            }
21            System.out.println("Total hours worked by " + name
                                 + " hours: " + sum);
22        }
23
    }
24}
```

注意，你在 `main` 方法的头中需要 `throws FileNotFoundException`。你不需要在 `process` 方法中包含它，因为打开文件的代码出现在 `main` 中。如果你将输入放入名为 `hours.dat` 的文件中并执行程序，你会得到如下结果：

```text
Total hours worked by Erica = 42.75

Total hours worked by Erin = 55.75

Total hours worked by Simone = 24.0

Total hours worked by Ryan = 31.75

Total hours worked by Kendall = 5.5
```

### 6.3 基于行的处理



到目前为止，我们查看的是按标记处理程序。然而，你经常会发现处理基于行的输入文件，每行输入代表单独处理的情况。这导致了另一种文件处理风格，称为基于行的处理。大多数文件处理涉及基于行和基于标记风格的结合，`Scanner` 类足够灵活，允许你编写包含两者的程序。

对于基于行的处理，你会使用 `Scanner` 对象的 `nextLine` 和 `hasNext` 方法。例如，这里有一个将输入文件转为大写的程序：

```java
// 读取文件并将其转换为大写。
import java.io.*;
import java.util.*;

public class EchoUppercase {
    public static void main(String[] args)
        throws FileNotFoundException {
            Scanner input = new Scanner(new File("poem.txt"));
            while (input.hasNextLine()) {
                String text = input.nextLine();
                System.out.println(text.toUpperCase());
            }
    }
```

该循环按行读取输入直到没有行。给定这个输入文件：

```text
My candle burns at both ends

It will not last the night

But, my foes, and my friends

It gives a lovely light.
```

产生了如下输出：

```text
MY CANDLE BURNS AT BOTH ENDS

IT WILL NOT LAST THE NIGHT

BUT, MY FOES, AND MY FRIENDS

IT GIVES A LOVELY LIGHT
```

注意，通过标记处理无法完成相同的任务。在这里，换行符是重要的，因为它们是诗的一部分。当你按标记读取文件时，你会丢失行内的空格，因为 `Scanner` 在读取标记时会跳过任何空白字符。该输入文件的最后一行缩进了，以明确它是诗的一部分。如果文件作为一系列标记被读取，该空格将会丢失。

## String 与行/标记组合

在上一节中，我们查看了一个名为 `HoursWorked` 的程序处理了以下数据：

```text
Erica 7.5 8.5 10.25 8 8.5

Erin 10.5 11.5 12 11 10.75

Simone 6.5 8 8

Ryan 6.5 8 9.25 8

Kendall 2.5 3
```

该数据是面向行的，但数据的这一方面没有整合到程序中。程序按标记的方式处理文件，但这并不总是有效。例如，考虑数据的一种细微变化，其中每行输入以员工 ID 开头，而不是只有名字：

```text
Erica 7.5 8.5 10.25 8 8.5

Erin 10.5 11.5 12 11 10.75

Simone 8 8 8

Ryan 6.5 8 9.25 8

Kendall 2.5 3
```

我修改的这些简单的更改需要对代码进行重大更改。记得程序有一个处理文件的方法：

```java
public static void process(Scanner input) {
    while (input.hasNext()) {
        String name = input.next();
        double sum = 0.0;
        while (input.hasNextDouble()) {
            sum += input.nextDouble();
        }
    }
    System.out.println("Total hours worked by " + name + " = " + sum);
}
```

假设你添加了一行代码读取员工 ID 并修改打印语句报告它：

```java
public static void process(Scanner input) {
    while (input.hasNext()) {
        int id = input.nextInt();
        String name = input.next();
        double sum = 0.0;
        while (input.hasNextDouble()) {
            sum += input.nextDouble();
        }
    }
    System.out.println("Total hours worked by " + name + " (id=" + id + ") = " + sum);
}
```

当你在新输入文件运行此版本的程序时，你会得到一个输出，然后抛出一个异常：

```text
Total worked by Erica (id=101) = 825.75

Exception in thread "main" java.util.InputMismatchException

at java.util.Scanner.throwFor(Scanner.java:819)

at java.util.Scanner.next(Scanner.java:1431)

at java.util.Scanner.nextInt(Scanner.java:2040)
```

程序正确读取了 Erica 的员工 ID 并在打印语句中报告了它，但随后崩溃了。此外，注意程序报告的 Erica 总工作小时为 825.75，而数字应该是 42.75。如果你计算报告的 825.75 小时和正确的 42.75 小时之间的差，你会发现它等于 783。那个数字出现在数据文件中：它是第二个员工的员工 ID。

### 6.3 基于行的处理

解决方案是以某种方式让程序在输入行的末尾停止读取。遗憾的是，使用基于标记（token）的方法没有简单方法可以做到。循环会询问 `Scanner` 是否下一个可读取的 `double` 类型值，而员工 ID 看起来像是一个可以读取的 `double`。你可能会尝试编写一个复杂的测试来寻找一个不是整数的 `double`，但即使这样做也不起作用，因为某些小时数是整数。

为了让这种方法生效，你需要编写一个更复杂的关注换行符的程序。程序必须一次读取一整行输入并对其进行处理。回想程序的 `main` 方法如下：

```java
public static void main(String[] args)
throws FileNotFoundException {
    Scanner input = new Scanner(new File("hours2.dat"));
    process(input);
}
```

如果你创建一个基于行的循环，你将得到类似这样的代码：

```java
public static void main(String[] args)
throws FileNotFoundException {
    Scanner input = new Scanner(new File("hours2.dat"));
    while (input.hasNext()) {
        String text = input.nextLine();
        processLine(text);
    }
}
```

按行读取文件可以保证你不会意外地合并两个员工的数据。这种方法的缺点是，你需要编写一个名为 `processLine` 的方法，接收一个 `String` 作为参数，并且你必须解析该 `String`。它包含了员工 ID，接着是员工姓名，然后是表示每天工作小时数的数字。换句话说，输入行是由几个部分（标记）组成的，你想要逐个处理这些部分。以基于标记的方式处理这些数据，比将其放在 `String` 中处理要容易得多。

幸运的是，有一种方便的方法可以做到。你可以构造一个独立的 `String`。记住，就像你可以将水龙头连接到不同的水源（房屋里连接到自来水或井水的水龙头，飞机上连接到水箱的水龙头），你也可以将 `Scanner` 连接到不同的输入源。你已经见过如何将其连接到控制台（`System.in`）和文件（传递一个 `File` 对象）。你也可以将其连接到单个 `String`。例如，这段代码：

```java
Scanner input = new Scanner("18.4 17.9 8.3 2.9");
```

构造了一个从 `String` 中获取输入并构造它的 `Scanner`。`Scanner` 拥有一个输入光标，就像连接到文件的 `Scanner` 一样。最初，输入光标位于 `String` 的第一个字符，当你从 `Scanner` 中读取标记时，它会向前移动。

### 从 String 读取标记的 Scanner 示例

```java
Scanner input = new Scanner("18.4 17.9 8.3 2.9");
double next = input.nextDouble();
System.out.println(next);
```

它产生了以下输出：

注意，它输出了四行输出，因为用于构造扫描仪的字符串中有四个数字。

当你有一个需要这种结合了基于行和基于标记处理方法的文件时，你可以使用一种稍微不同的方法：为输入文件的每一行都构造一个基于 `Scanner` 的 `Scanner`。通过这种方法，你将得到许多 `Scanner` 对象。你有一个 `Scanner` 对象来跟踪输入文件，并使用该 `Scanner` 读取输入的每一行输入。每当你从文件中读取一行文本时，你都会为该行输入构造一个微型 `Scanner`。你可以对这些微型 `Scanner` 对象使用基于标记的处理方法，因为每个都只包含单行数据。

这种基于行和基于标记处理的结合非常强大。你会发现自己可以使用这种方法并处理细微的变化，以处理各种输入文件。

在 `Hourworked` 程序中，每行输入都包含单个员工的信息。处理输入行涉及为该行创建一个 `Scanner`，然后以基于标记的方式读取它的各个部分（ID、姓名、小时数）。你可以将所有这些整合到程序的新版本中：

```java
public static void main(String[] args) throws FileNotFoundException {
    Scanner input = new Scanner(new File("hours2.dat"));
    while (input.hasNextLine()) {
        // ... 此处逻辑
    }
}
```

## 6.4 高级文件处理

```java
// 处理给定的 String (ID，姓名和工作小时数)
public static void processLine(String text) {
    Scanner data = new Scanner(text);
    int id = data.nextInt();
    String name = data.next();
    double hours = data.nextDouble();
    double sum = hours;
    System.out.println("Total hours worked by " + name + " (id#" + id + ") = " + sum);
}
```

注意，`main` 方法包含了从文件中读取条目的基于行的处理。每一行都会被传递给 `processLine` 方法。每当你调用 `processLine` 时，你都会为该行输入构造一个微型 `Scanner` 并进行基于标记的处理（调用 `nextInt` 和 `nextDouble` 方法）。

此版本的程序产生以下输出：

```text
Total hours worked (id#101) = 42.75

Total hours worked by Erin (id#783) = 55.75

Total hours worked by Simone (id#114) = 24.0

Total hours worked by Ryan (id#238) = 31.75

Total hours worked by Kendall (id#156) = 5.5
```

虽然这个版本的程序复杂一些，但它关注换行符。

## 6.4 高级文件处理

在本节中，我们将探索与文件处理相关的两个主题：生成文件和使用 `try/catch` 语句处理错误。

### 使用 PrintStream 输出

到目前为止，我们看到的所有程序通过调用 `System.out.print` 或 `System.out.println` 将输出发送到控制台。但就像你可以从文件读取输入一样，你也可以向文件写入输出。最简单的方法是利用你已有的知识。

如果你查看 Sun 的文档，你会发现 `System.out` 是一个存储 `PrintStream` 对象的变量。计划是拥有一个名为 `output` 的变量来存储你的 `PrintStream` 对象。如果你考虑关于 `System.out` 的一切知识，你对该做什么会有很好的想法，但对于这个程序，你将调用 `output.println` 而不是 `System.out`。

假设你想将输出发送到名为 `results.txt` 的文件。你可以这样构造 `PrintStream` 对象：

```java
PrintStream output = new PrintStream(new File("results.txt"));
```

如果 Java 无法创建文件，之前的行代码可能会产生异常。这种情况发生有很多原因：你可能没有写入该目录的权限，或者文件可能被另一个程序锁定。与创建基于文件的 `Scanner` 的代码一样，这行代码可能抛出 `FileNotFoundException`。这意味着 Java 要求你在方法中包含 `throws` 子句。

最初，文件是空的。它最终将包含你通过调用来产生的任何输出。

```java
public static void main(String[] args)
throws FileNotFoundException {
    PrintStream output =
    new PrintStream(new File("hello.txt"));
    output.println("Hello world.");
    output.println();
    output.println("This program produces four");
    output.println("lines of output");
}
```

当你运行这个新版本的程序时，发生了一件趣事。程序似乎没有做任何事情：控制台上完全没有出现输出。在这种情况下，输出被重定向到了一个文件中。在程序执行完成后，你可以打开名为 `hello.txt` 的文件，你会发现它包含以下内容：

```text
Hello world.

This program produces four

lines of output.
```

要点是，你已经学会对 `System.out` 执行的所有操作，也可以对绑定到文件的 `PrintStream` 对象执行。

你还可以编写接受以 `PrintStream` 对象作为参数的方法。例如，考虑修复一系列单词间距的任务。假设你有一行间距不规则的文本如下：

```text
new nation,  conceived  in  liberty
```

假设你想在打印这段文本时，每对单词之间恰好有一个空格：

```text
new nation, conceived in liberty
```

你如何做到这一点？假设你正在编写一个方法，传入一个用于回显 `String` 和一个用于发送输出的 `PrintStream` 对象：

```java
public static void echoFixed(String text, PrintStream output) {
}
```

你可以从 `String` 构建一个 `Scanner`，然后使用 `next` 方法一次读取一个单词。记得 `Scanner` 会忽略空白符，所以你只会得到单个单词，而没有它们之间所有的空格。在读取时，你需要将它们回显到 `PrintStream` 对象。这是第一次尝试：

```java
Scanner data = new Scanner(text);
while (data.hasNext()) {
    output.print(data.next());
}
```

这段代码在删除 `String` 中的长序列空格方面做得很好，但它做得过头：它消除了所有的空格。要在每对单词之间保留一个空格，你需要包含一些空格：

```java
Scanner data = new Scanner(text);
while (data.hasNext()) {
    output.print(data.next() + " ");
}
```

这最终看起来很不错，但它在行尾打印了一个额外的空格。为了删掉那个空格，使得空格真正只出现在每对单词之间，你必须对此进行微调。这是一个经典问题：你想打印的单词比你拥有的空格多一个。你可以使用典型的解决方案：在循环开始之前处理第一个单词，并交换循环内部其他操作的顺序（先打印空格再打印单词）：

```java
Scanner data = new Scanner(text);
output.print(data.next());
while (data.hasNext()) {
    output.print(" " + data.next());
}
```

这现在对几乎所有情况都有效，但通过包含在循环开始前回显第一个单词的“栅栏”操作，你引入了一个“存在第一个单词”的假设。如果 `String` 根本没有任何单词，这不会抛出异常。因此，你需要针对 `String` 不包含任何单词的情况进行测试。如果你还想生成完整的一行输出，还需要在打印完单个单词后调用 `println` 来完成该行的输出。将这些内容整合在一起，你得到了如下：



```java
public static void echo(String text, PrintStream output) {
    Scanner data = new Scanner(text);
    if (data.hasNext()) {
        output.print(data.next());
        while (data.hasNext()) {
            output.print(" " + data.next());
        }
        output.println("");
    }
}
```

你现在调用的是`output.print`和`output.println`，而不是调用`System.out.print`和`System.out.println`。这个方法的一个有趣之处是，它可以用于发送输出到输出头部，也可以用于发送输出到`System.out`。头部表示它适用于任何`PrintStream`，因此你可以调用它将输出发送到绑定到文件的`PrintStream`对象，或发送到`System.out`。

下面是一个使用该方法修复整个文本文件间距的完整程序。为了强调该方法的灵活性，程序将其输出同时发送到文件（`words2.txt`）和控制台。

## 6.4 高级处理

```java
// 此程序移除输入文件中的多余空格。
import java.io.*;
import java.util.*;

public class FileSpacing {
    public static void main(String[] args)
        throws FileNotFoundException {
        Scanner input = new Scanner(new File("words.txt"));
        PrintStream output =
            new PrintStream(new File("words2.txt"));
        while (input.hasNextLine()) {
            String text = input.nextLine();
            echoFixed(text, output);
            echoFixed(text, System.out);
        }
    }

    public static void echoFixed(String text,
        PrintStream output) {
        Scanner data = new Scanner(text);
        if (data.hasNext()) {
            output.print(data.next());
            while (data.hasNext()) {
                output.print(" " + data.next());
            }
            output.println("");
        }
    }
}
```

## 第 6 章 文件处理

名称并尝试打开该文件。如果`try`块中的代码再次失败，你将生成另一个错误消息并第三次通过循环。

现在，将此伪代码与之前的`try/catch`代码结合，修改错误消息，以明确用户获得了另一次输入合法名称的机会：

```java
Scanner input = null;
while (input == null) {
    System.out.print("What is the name of the input file?");
    String name = console.nextLine();
    input = new Scanner(new File(name));
} catch (FileNotFoundException e) {
    System.out.println("File not found." +
        "Please try again.");
}
```

此循环反复执行，直到`try`块内部对新`Scanner`的调用成功并赋予变量`input`一个非空值。这段代码可以包含在`main`方法中，尽管你必须为`console`构建一个`Scanner`才能提示用户输入文件名。

以下是`HoursWorked`程序的一个变体，它会提示文件名：

```java
// 提示文件名的 HoursWorked2 变体。
import java.io.*;
import java.util.*;

public class HoursWorked {
    public static void main(String[] args) {
        Scanner console = new Scanner(System.in);
        Scanner input = null;
        while (input == null) {
            System.out.print("input file name?");
            String name = console.nextLine();
            try {
                input = new Scanner(new File(name));
            } catch (FileNotFoundException e) {
                System.out.println("File not found." +
                    "Please try again.");
            }
        }
        while (input.hasNextLine()) {
            String text = input.nextLine();
            processLine(text);
        }
    }

    // 处理给定的 String (ID,名称和工时)
    public static void processLine(String text) {
        Scanner data = new Scanner(text);
        int id = data.nextInt();
        String name = data.next();
        double sum = 0.0;
        while (data.hasNextDouble()) {
            sum += data.nextDouble();
        }
        System.out.println("Total hours worked by " + name +
            " (id#" + id + ") " + sum);
    }
}
```

这意味着你不再需要在`main`方法的头中使用`throws FileNotFoundException`，因为你已经处理了潜在的异常。以下是执行日志，显示了当用户输入非法文件名后输入合法文件名时发生的情况：

```text
input name: ours2.dat
File not found. Please try again.
input name: hours2.txt
File not found. Please try again.
input name: data.txt
File not found. Please try again.
input name: file.dat
File not found. Please try again.
input name: hours2.dat
Total hours worked by Erica (id#101) = 42.75
Total hours worked by Erin (id#783) = 55.75
Total hours worked by Simon (id#114) = 24.0
Total hours worked by Ryan (id#238) = 31.75
Total hours worked by Kendall (id#156) = 5.5
```

这段打开文件的代码已经足够复杂，你可能想将其放入它的静态方法中。下面的最终变体包含一个名为`getInput`的方法，用于获取合法文件名并用其构建`Scanner`：

```java
// 在方法中打开文件文件的 HoursWorked3 变体。
import java.io.*;
import java.util.*;

public class HoursWorked4 {
    public static void main(String[] args) {
        Scanner console = new Scanner(System.in);
        Scanner input = getInput(console);
        while (input.hasNextLine()) {
            String text = input.nextLine();
            processLine(text);
        }
    }

    // 提示用户合法文件名，创建并返回
    // 到文件的 Scanner
    public static Scanner getInput(Scanner console) {
        Scanner result = null;
        while (result == null) {
            System.out.print("input file name?");
            String name = console.nextLine();
            try {
                result = new Scanner(new File(name));
            } catch (FileNotFoundException e) {
                System.out.println("File not found. " +
                    "Please try again.");
            }
        }
        return result;
    }

    // 处理给定的 String (ID,名称和工时)
    public static void processLine(String text) {
        Scanner data = new Scanner(text);
        int id = data.nextInt();
        String name = data.next();
        double sum = 0.0;
        while (data.hasNextDouble()) {
            sum += data.nextDouble();
        }
        System.out.println("Total hours worked by " + name +
            " (id=" + id + ") " + sum);
    }
}
```

### 6.4 高级文件处理

打开文件的代码相当标准，可以用于许多程序。请参考此模板代码。

## 模板代码

从一个程序到另一个程序往往相同的代码。`getInput`方法是你可以在不同文件处理程序可能使用的这类模板代码的良好示例。

### 6.5 案例研究：加权 GPA

`Worked`程序需要计算加权 GPA。计算加权 GPA 需要计算每个成绩的“质量分”。加权 GPA 通过总质量分除以总学分来计算，因此我们只需要累加总质量分、累加总学分，然后进行除法运算。这涉及到一系列累加求和任务，例如，输入文件可能如下所示：

| 姓名 | 学分 | 成绩 |
| --- | --- | --- |
| Erica Kane | 2.8 | 4.3 |
| Greenlee Smyth | 3.9 | 4.0 |
| Ryan Laveree | 4.0 | 3.9 |
| Adam Chandler | 3.0 | 3.2 |
| Adam Chandler, Jr | 4.0 | 1.5 |

质量分定义为学分乘以成绩。为了总学分，我们可以将其表示为伪代码：

```text
设置总学分数为 0;
设置总质量分数为 0;
while (有成绩需要处理) {
    下一个学分和下一个成绩;
    学分加到总学分;
    while (有下一个成绩) {
        成绩加到总质量分;
    }
}
跳转到 (总质量分) / (总学分);
```

通过结合`Scanner`对象，将其翻译成 Java 代码非常简单：

```java
double totalQualityPoints = 0.0;
double totalUnits = 0;
while (data.hasNextInt()) {
    int units = data.nextInt();
    double grade = data.nextDouble();
    totalUnits += units;
    totalQualityPoints += units * grade;
}
double gpa = totalQualityPoints / totalUnits;
```

由于`data`对象是从单行输入构建的，我们用此循环处理一个人的成绩。仍然存在一个潜在问题。如果没有成绩怎么办？有些学生退了所有课程。处理这种情况有几种方法，但让我们假设在没有成绩时使用 0.0 的 GPA 是合适的。进行此修正并将其放入方法中，我们将得到以下代码：

```java
public static double processGrades(Scanner data) {
    double totalQualityPoints = 0.0;
    double totalUnits = 0;
    while (data.hasNextInt()) {
        int units = data.nextInt();
        double grade = data.nextDouble();
        totalUnits += units;
        totalQualityPoints += units * grade;
    }
    if (totalUnits == 0) {
        return 0.0;
    } else {
        return totalQualityPoints / totalUnits;
    }
}
```

### 6.5 案例研究：加权 GPA

我们现在可以开始填充“处理该学生数据”的细节了。我们将调用刚刚编写的的方法来处理学生的成绩，将其转换为加权平均 GPA，然后打印结果：

```java
double gpa = processGrades(data);
System.out.println("GPA for " + name + " = " + gpa);
```

这本就完成程序，让我们再添加一个计算来计算最大和最小 GPA。我们可以在打印语句之后通过一些简单的`if`语句很容易地实现这一点：

```java
if (gpa > max) {
    max = gpa;
}
if (gpa < min) {
    min = gpa;
}
```

我们只需要将当前的`gpa`与我们认为的最大值和最小值进行比较，如果新值代表新的最大值或最小值，就重置这些值。但我们如何初始化这些变量呢？有两种可能的方法。一种方法是将`max`和`min`初始化为序列中的第一个值。但这会让我们的循环比现在复杂得多。第二种方法是将`max`设置为可能的最低值，并将`min`设置为最高值。这种方法并不总是可行，因为我们并不总是知道数值可能有多高有多低，但在 GPA 的情况下，我们知道它们会在 0.0 到 4.0 之间。因此，我们可以这样初始化变量：

```java
double max = 0.0;
double min = 4.0;
```

将`max`设置为 0.0 而将`min`设置为 4.0 似乎很奇怪，但这是因为我们打算在循环内部对它们重置。例如，如果第一个学生的 GPA 是 3.2，这将构造一个新的最大值（高于 0.0）和一个新的最小值（低于 4.0）。当然，可能所有学生的最终 GPA 都是 4.0，在这种情况下，我们选择 4.0 是恰当的。同样，所有学生的最终 GPA 都可能是 0.0，在这种情况下，我们选择的`max`为 0.0 也是恰当的。

将这一切整合在一起，我们得到了完整的程序：



```java
// 此程序读取一个包含系列学生 GPA 数据的输入文件
// 并报告每个学生的加权 GPA，
// 以及最大和最小 GPA。
import java.io.*;
import java.util.*;

public class Gpa {
  public static void main(String[] args)
    throws FileNotFoundException {
    Scanner input = new Scanner(new File("gpa.dat"));
    process(input);
  }

  static void process(Scanner input) {
    double max = 0.0;
    double min = 4.0;
    while (input.hasNextLine()) {
      String name = input.nextLine();
      String grades = input.nextLine();
      Scanner data = new Scanner(grades);
      double gpa = processGrades(data);
      System.out.println("GPA for " + name + ": " + gpa);

      if (gpa > max) {
        max = gpa;
      }
      if (gpa < min) {
        min = gpa;
      }
    }
    System.out.println();
    System.out.println("max GPA = " + max);
    System.out.println("min GPA = " + min);
  }

  public static double processGrades(Scanner data) {
    double totalQualityPoints = 0.0;
    double totalUnits = 0;
    while (data.hasNextInt()) {
      int units = data.nextInt();
      double grade = data.nextDouble();
      totalUnits += units;
      totalQualityPoints += units * grade;
    }
    if (totalUnits == 0) {
      return 0.0;
    } else {
      return totalQualityPoints / totalUnits;
    }
  }
}
```

再次，主方法在头部中抛出了 `FileNotFoundException`。假设提供的数据存放在名为 `gpa.data` 的文件中，该程序的执行结果如下：

```
GPA for Erica Kane = 3.3299999999999996
GPA for Greenlee Smythe = 3.9299999999999997
GPA for Ryan Laever = 3.6799999999999997
GPA for Adam Chandler = 2.9333333333333336
GPA for Adam Chandler, Jr = 1.7222222222222223
max GPA = 3.9299999999999997
min GPA = 1.7222222222222223
```

可以修改程序以将其输出发送到像 `gpa.out` 的文件中。这留作练习题。

## 第 6 章 文件处理

文件在 Java 中由 `File` 对象表示。`File` 类位于 `java.io` 包中。

`Scanner` 可以作为参数传递给方法，以读取文件的部分或全部，因为它们是对象，因此使用引用语义。

`Scanner` 可以从文件而不是从键盘读取输入。这是通过向 `Scanner` 的构造函数传递 `new File(filename)` 而不是键盘来实现。

名称可以指定为相对路径，也可以使用完整路径。

异常是必须被捕获或声明的。

文件是有结构化的，我们可以按行处理它们。

## 第 6 章总结

文件在 Java 中由 `File` 对象表示。`File` 类位于 `java.io` 包中。

`Scanner` 可以作为参数传递给方法，以读取文件的部分或全部，因为它们是对象，因此使用引用语义。

`Scanner` 可以从文件而不是从键盘读取输入。这是通过向 `Scanner` 的构造函数传递 `new File(filename)` 而不是键盘来实现。

名称可以指定为相对路径，也可以使用完整路径。

异常是必须被捕获或声明的。

文件是有结构化的，我们可以按行处理它们。

## 自测

### 6.1 节 文件读取

1. 什么是文件？

2. 如何从文件读取？

3. 下行代码错误在哪里？

   `Scanner input = new Scanner("test.dat");`

### 6.2 节 基于令牌的

4. 下行代码错误在哪里？

   `Scanner input = new Scanner(filename));`

### 6.3 节 基于行的

7. 对于接下来的几个问题，考虑一个名为 `readme.txt` 的文件，其内容如下：

```
6.7
此文件有
几行。

test
10 20
30 40
```

在 `readme.txt` 文件上运行以下代码的输出是什么？

```java
Scanner input = new Scanner(new File("readme.txt"));
int count = 0;
while (input.hasNextLine()) {
  System.out.println("input: " + input.nextLine());
  count++;
}
```

```java
System.out.println(count + " total");
```

8. 如果将 `hasNextLine()` 和 `nextLine()` 替换为 `hasNext()` 和 `next()`，上一个练习的输出是什么？

9. 如果将 `hasNextLine()` 和 `nextLine()` 替换为 `hasNextInt()` 和 `nextInt()`，输出是什么？如果替换为 `hasNextDouble()` 和 `nextDouble()` 呢？

10. 编写一个将自己打印到控制台的程序。如果存储在 `Example.java` 中，它将打开 `Example.java` 文件并将其内容打印到。

11. 编写一个程序提示用户输入文件名并将文件的内容打印到控制台。假设该文件存在。你可能希望将代码放在名为 `printFile` 的方法中。

### 6.4 节 高级文件处理

12. 使用什么对象向文件写入输出？该对象提供了哪些方法供你使用？

13. 编写代码将以下四行文本打印到名为 `message.txt` 的文件中：

```
Testing:
1, 2, 3.

这是我的输出文件。
```

14. 编写一段代码，提示用户输入文件名，直到用户输入一个系统上存在的文件名。你可能希望将此代码放在一个名为 `fileName` 的方法中，该方法将该文件名作为 `String` 返回。

15. 题目 11 要求你编写一段代码，提示用户输入文件名并将该文件的内容打印到控制台。修改你的代码，使其反复提示用户输入文件名，直到用户输入一个系统上存在的文件名。

## 练习题

- 1. 编写一个名为 `doubleSpace` 的方法，它接受两个代表文件名的 `String` 作为参数，并在第二个文件中写入第一个文件内容的双倍间距版本。你可以通过在输出的每行之间插入一个空行来实现。

为了增加挑战性，请尝试让你的代码在两个 `String` 相同的情况下也能工作（也就是说，让它将双倍间距的输出写回同一个文件）。

- 2. 编写一个名为 `wordwrap` 的方法，它接受一个代表输入文件的 `Scanner` 作为参数，并将文件的每一行输出到控制台，对所有超过 60 个字符的行进行自动换行。例如，如果一行包含 112 个字符，该方法应将其替换为两行：一行包含前 60 个字符，另一行包含最后 52 个字符。包含 217 个字符的行应被换行成四行：三行长度为 60，最后一行长度为 37。

- 3. 修改 `wordwrap` 方法，使其将新换行的文本输出回原始文件。（注意——不要在读取文件时向其输出！）此外，修改它使用类常量来表示最大行长度，而不是硬编码 60。

- 4. 修改 `wordwrap` 方法，使其仅对单词进行换行，永远不要切断单词。假设任何单词都是由空格分隔的标记，且长度均在 60字符以内。

- 5. 编写一个程序，提示用户输入文件名，然后读取该文件（假设其内容完全由整数组成），并打印数字的最小、最大、和、计数（文件中整数的数量）以及平均值。例如，如果文件 `input.dat` 有以下内容：

```
4 - 18
15 31
27
```

你的程序应该产生以下输出：

```
input file name? input.dat
Maximum = 31
Minimum = -2
Sum = 93
Count = 6
Average = 15.5
```

- 6. 修改前面的程序，使其在包含非整数标记的文件上也能工作。你的代码应该跳过任何不是整数的标记。例如，如果文件 `input2.dat` 有以下内容：

```
4 billy bob -18 2.54
15 31 NotANumber
true 'c': 27
```

你的程序应该产生与上一个练习相同的输出。

- 7. 编写一个名为 `collapseSpaces` 的方法，它接受一个代表输入文件的 `Scanner` 作为参数，然后读取并输出它，所有标记由单个空格分隔，将任何连续的空格合并为单个空格。也就是说，如果文件的一行包含以下文本：

`many spaces on this line!`

则文件的同一行应输出如下：

`many spaces on this line!`

- 9. 编写一个名为 `readEntireFile` 的方法，它接受一个代表输入文件的 `Scanner` 作为参数，然后读取并返回其内容作为 `String`。

编写一个名为 `stripHtmlTags` 的方法，它接受一个代表包含 HTML 标签文件的 `Scanner` 作为参数，然后读取移除所有 HTML 标签后的文件文本。标签是任何位于 `<` 和 `>` 之间的文本。例如，如果文件包含以下文本：

```html
<html>
<head>
<title>My web page</title>
</head>
<body>
<p>There are many pictures of my cat here,
as well as my very cool<b> blog page,
which contains <font color="red">awesome
stuff about my trip to Vegas.</p>

Here's my cat now:<img src="cat.jpg">
</body>
</html>
```

你的程序应该输出以下文本：

```
My web page 

There are many pictures of my cat here,

as well as my very cool blog page,

Which contains awesome

stuff about my trip to Vegas.

Here's my cat now:
```

你（你）假设该文件是一个格式良好的 HTML 文档，并且没有标签本身包含 `<` 或 `>` 字符。

- 10. 编写一个名为 `stripComments` 的方法，它接受一个代表包含 Java 程序的 `Scanner` 作为参数，然后读取该文件并打印移除所有注释后的文件文本。

注释是行中从 `//` 到行尾的任何文本，以及 `/*` 和 `*/` 之间的任何文本。例如，如果文件包含以下文本：

```java
import java.util.*;

/* My Program
by Suzy Student */

public class Program {
    public static void main(String[] args) {
        System.out.println("Hello, world!"); // // a println
    }

    public static /* Hello there */ void foo() {
        System.out.println("Goodbye!"); // // comment here
    }
} // */
```

你的程序应该输出以下文本：

```java
import java.util.*;

public class Program {
    public static void main(String[] args) {
        System.out.println("Hello, world!");
    }

    public static void foo() {
        System.out.println("Goodbye!");
    }
}
```

- 11. 编写一个名为 `collapseSpaces` 的方法，它接受一个代表输入文件的 `Scanner` 作为参数，然后读取并输出它，所有标记由单个空格分隔，将任何连续的空格合并为单个空格。也就是说，如果文件的一行包含以下文本：

`many spaces on this line!`

则文件的同一行应输出为：

`many spaces on this line!`

## 编程项目

- 1. 数单词很枯燥，但计算机可以帮助。编写一个程序统计论文中的单词数、行数字符（非空格）。假设论文是一个文本文件且单词由空格分隔。

- 2. 编写一个程序比较两个文件并打印它们的信息。例如，如果文件 `data1.txt` 具有以下内容，另一个文件 `data2.txt` 也存在，用户的对话可能如下：

```
Enter first file name: data1.txt
Enter second file name: data2.txt
Differences found:
Line 1:
Line 4:
```

- 3. 编写一个程序提示用户输入文件名，假设文件包含 Java 程序。你的程序应该读取文件并打印缩进的内容。当看到左括号 `{` 时增加四个缩进。当看到右括号 `}` 时减少四个缩进。你必须假设文件每行有一个左括号或右括号，且每个语句（如 `if`）都使用括号而不是省略。考虑使用常量表示缩进数（4）以便更改。

- 4. 编写一个程序读取婴儿名字流行程度文件。文件的每行存储一个名字，后跟代表该名字在每个年代流行程度的整数：1900、1910、1920 等。排名从 1（最流行）到 1000（最不流行），或者对于排名第 100 名的名字使用 0。以下是文件格式的示例：

```
Sally 0 0 0 0 0 0 0 0 0 886
Sam 58 69 99 131 168 236 380 407 408 466
Samantha 0 0 0 0 0 0 272 107 26 5 7
Samir 0 0 0 0 00 0 798
```

你的程序应该提示用户输入名字并搜索该文件名。如果找到了名字，显示屏幕上的数据。

该程序允许你搜索社会安全局的数据，查看自 1900 年以来特定名字的流行程度。

```
Name? Sam
Statistics on name "Sam"
1900: 58
1910: 69
1920: 99
1930: 131
```

# 第 7 章

## 数组

## 引言

文件的顺序性极大地限制了你可以轻松对它们进行的有趣操作的数量。我们目前为止所检查的算法都是顺序算法；即通过按顺序检查每个数据项一次来执行的算法。但还有一类完全不同的算法，当你可以多次以任意顺序访问数据项时，就可以执行它们。

本章将研究一种名为数组（array）的新对象，它提供了这种更灵活的访问方式。数组的概念并不复杂，但初学者可能需要一段时间才能才能学会数组的所有不同使用方法。本章从数组的通用性讨论开始，然后讨论常见的数组操作以及高级数组技术。

## 7.1 数组基础

- 数组的构造与遍历

- 访问数组

- 一个完整的数组程序

- 随机访问

- 数组与方法

- For-Each 循环

- 数组的初始化

- 数组的局限性

## 7.2 数组遍历算法

- 打印数组

- 搜索与替换

- 等等性测试

- 反转数组

## 7.3 高级数组技术

- 移动数组中的值

- 对象数组

- 命令行参数（可选）

## 7.4 多维数组（可选）

- 矩形二维维数组

- 锯齿数组

## 7.5 案例研究：工作小时数

- 版本 1：读取输入文件

- 版本 2：累加和

- 版本 3： 行和与列打印

## 第 7 章 数组

### 7.1 数组基础

数组是一种用于存储相同类型值序列的灵活结构。

**数组 (Array)**

持有多个相同类型值的结构。

存储在数组中的值称为元素（elements）。使用整数索引（index）访问单个元素。

**索引 (Index)**

表示值在数据结构中位置的整数。

作为一个类比，考虑邮政箱。信箱用数字编号，因此你可以使用“邮政箱 884 号”之类的描述来引用单个信箱。你已经有了使用索引来指示字符串内部位置的经验，例如调用 `charAt` 或 `substring` 等方法。与 `String` 索引一样，数组索引从 0 开始。这种约定被称为零基索引（zero-based indexing）。

#### 零基索引

Java 全局使用的一种编号方案，其中值序列的索引从 0 开始（元素 0、元素 1、元素 2 等以此此类推）。



索引从 1 而不是 0 开始似乎很自然，但有些人决定让 Java 使用与 C 和 C++ 相同的索引方案。

## 7.1 数组基础

### 数组的构造与遍历

假设你想存储一些不同的读数。你可以将它们存储在系列变量中：

```java
double temperature1;
double temperature2;
double temperature3;
```

如果你只有 3 个温度值，这不是一个坏方案，但假设你需要存储 300 个温度值。那么你需要一个更灵活的东西。你可以将温度存储在数组中。使用数组时，你首先需要为它声明一个变量，你必须知道使用什么类型。要表示你需要数组，请在类型后加上方括号。对于温度，你需要一个 `double` 类型的值序列，因此你使用类型 `double[]`。因此，你可以如下为数组声明变量：

```java
double[] temperature;
```

数组是对象，这意味着它们必须构造。仅仅声明变量不足以让对象存在。在这种情况下，你需要一个包含三个 `double` 值的数组，如下所示构造它：

```java
double[] temperature = new double[3];
```

这与你之前请求新对象时使用的语法略有不同。这是数组的特殊语法。注意，在左侧你不在方括号内放入任何内容，因为你正在描述一种类型。变量 `temperature` 可以引用任何 `double` 值的数组，无论它包含多少个元素。但在右侧，你必须提到具体的元素数量。声明和构造数组的通用语法如下：

```java
<element type>[] <name> = new <element type>[size];
```

你可以使用任何类型作为元素类型，尽管该语句的左右两侧必须匹配。例如，以下任何一种构造数组都是合法方法：

```java
int[] numbers = new int[10]; // 一个包含 10 个整数的数组
char[] letters = new char[20]; // 一个包含 20 个字符的数组
boolean[] flags = new boolean[5]; // 一个包含 5 个布尔值的数组
String[] names = new String[100]; // 一个包含 100 个字符串的数组
Point[] points = new Point[50]; // 一个包含 50 个 Point 的数组
```

在构造对象数组（如 `String` 数组或 `Point` 数组）时，适用某些特殊规则。

## 访问数组

正如上一节所过的，我们通过将引用数组的变量名与方括号内的整数表达式来引用数组元素：

```
<array variable><integer expression>
```

在这一语法描述中请注意，索引可以是任意的整数表达式。为了探索这一点，让我们看看如何访问整数数组中的特定值。假设我们构造了一个长度为 5 的数组，并用前五个整数填充它：

```java
int[] list = new int[5];
for (int i = 0; i < list.length; i++) {
    list[i] = 2 * i;
}
```

第一行代码声明了一个类型为 `int[]` 的变量 `list`，并使其指向一个长度为 5 的数组。数组元素被自动初始化为 0：

| [0] | [1] | [2] | [3] | [4] |
|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 0 |

然后代码使用标准的遍历循环用连续的奇数填充数组：

| [0] | [1] | [2] | [3] | [4] |
|---|---|---|---|---|
| 1 | 3 | 5 | 7 | 9 |

假设我们要报告列表中的第一个、中间和最后一个值。查看前面的图表，我们可以看到它们出现在索引 0、2 和 4 处，这意味着我们可以编写以下代码：

```java
// 适用于任何长度为 5 的数组
System.out.println("first = " + list[0]);
System.out.println("middle = " + list[2]);
System.out.println("last = " + list[4]);
```

当数组长度为 5 时，这段代码是起作用的，但假设我们更改了数组的长度。例如，如果数组长度为 10，这段代码将报告错误的值。我们需要修改它以包含 `list.length`，就像编写标准遍历循环时一样：

数组的第一个元素始终位于索引 0 处，因此不需要更改。你起初可能认为可以通过将 4 替换为 `list.length` 来修复第三行代码：

```java
// 不起作用
System.out.println("last = " + list[list.length]);
```

然而，这段代码不起作用。罪魁祸首是从零索引。在我们的示例中，当 `list.length` 为 5 时，最后一个值存储在索引 4 处。更通地说，最后一个值将在索引 `list.length - 1` 处。我们可以直接在打印语句中使用这个表达式：

```java
// 这个起作用
System.out.println("last = " + list[list.length - 1]);
```

注意，方括号内显示的是一个整数表达式（减法的结果）。找到中间值的一种简单方法是将长度减半：

```java
// 这样对吗？
System.out.println("middle = " + list[list.length / 2]);
```

当 `list.length` 为 5 时，该表达式求值为 2。但当 `list.length` 为 10 时呢？在这种情况下，表达式求结果为 5，我们将打印 `list[5]`。但当列表长度为偶数时，中间实际上有两个值，所以尚不清楚应该返回哪一个。对于长度为 10 的列表，这两个值将是 `list[4]` 和 `list[5]`。通常，前面的表达式对于长度为偶数的列表将始终返回中间两个值中的第二个。

如果我们想要获取两个值中的第一个，可以在除以 2 之前从长度减 1。这里是遵循此逻辑的完整打印语句：

```java
System.out.println("first = " + list[0]);
System.out.println("middle = " + list[(list.length - 1) / 2]);
System.out.println("last = " + list[list.length - 1]);
```

当你学习使用数组时，你会发现自己一直在好奇对正在访问的数组元素究竟能做什么。例如，对于名为 `list` 的整数数组，你对 `list[i]` 到底能做什么？答案是，你可以对 `list[i]` 执行任何你通常对任何 `int` 类型变量所可以执行的操作。例如，如果你有一个类型为 `int` 的变量 `x`，你知道你可以执行以下任何操作：

```java
x = 3;
x++;
x *= 2;
```

这意味着如果 `list` 是整数数组，你也可以对 `list[i]` 说同样的话：

```java
list[i] = 3;
list[i]++;
list[i] *= 2;
list[i]--;
```

从 Java 的角度来看，因为 `list` 被声明为类型 `int[]`，像 `list[i]` 这样的元素类型为 `int` 并可以以此处理。例如，为了递增数组中的每个值，你可以如下使用标准的遍历循环：

```java
for (int i = 0; i < list.length; i++) {
    list[i]++;
}
```

这段代码将增加数组中的每个值，将奇数数组转换为偶数数组。例如，长度为 5 的数组的合法索引是 0 到 4。任何小于 0 或大于 4 的数字都出了数组范围：

| [0] | [1] | [2] | [3] | [4] |
|---|---|---|---|---|
| 1 | 3 | 5 | 7 | 9 |

如果你尝试访问此类索引，Java 将抛出 `ArrayIndexOutOfBoundsException`。

### 一个完整的数组程序

```java
import java.util.*;

public class Temperature {
    public static void main(String[] args) {
        Scanner console = new Scanner(System.in);
        System.out.print("How many days?");
        int numDays = console.nextInt();
        int sum = 0;
        for (int i = 1; i <= numDays; i++) {
            System.out.print("Day " + i + " temp: ");
            int next = console.nextInt();
            sum += next;
        }
        double average = (double)sum / numDays;
        System.out.println("Average = " + average);
    }
}
```

### 你知道吗

### 缓冲区溢出

最早且仍然常见的安全问题来源之一是缓冲区溢出（也称为缓冲区越界）。缓冲区溢出类似于数组越界。当程序写入的数据超过为其留的缓冲区边界时就会发生。例如，你可能为 10 个字符的字符串 "James T Kirk" 分配了空间：

| J | a | m | e | s | T | K | i | r | k |
|---|---|---|---|---|---|---|---|---|---|

假设你告诉计算机用 "Jean Luc Picard" 覆盖这个缓冲区——如果你将所有这些字符写入缓冲区，你就“溢出”了三个字符：

| J | e | a | n | L | u | c | P | i | c | a | r | d |
|---|---|---|---|---|---|---|---|---|---|---|---|---|

Picard 名字的最后三个字母（"ard"）被写入缓冲区之外内存部分。这是一个非常危险的情况，因为它将覆盖那里已存在的任何数据。这就像一个粗鲁的学生从你手里夺走了三张纸，并擦掉了你在上面写过的任何内容。

当缓冲区溢出意外发生时，程序通常会处于某种错误状态。然而，当缓冲区溢出是由恶意程序故意执行时，它们特别危险。如果攻击者能够找出要覆盖的正确内存位置，攻击软件就可以接管你的计算机并指示它执行你没有要求的事情。

三个最著名的网络蠕虫都是基于缓冲区溢出的：1988 年的 Morris 蠕虫，以及 2003 年的 SQLSlam 蠕虫。

## 第7章 数组

这个程序运行得相当不错。这里是一个示例执行：

多少天？5

第1天的高温: 78

第2天的高温: 81

第3天的高温: 75

第4天的高温: 79

第5天的高温: 71

平均值 = 76.8

假设你想知道有多少天的气温高于平均水平。你可以尝试将其整合到循环中，但那样行不通。问题在于，在处理完所有数据之前，你无法计算出平均值。这意味着你需要对数据进行第二次遍历，以确定有多少天高于平均水平。你无法使用 `Scanner` 实现这一点，因为 `Scanner` 没有“重置”选项可以让你第二次查看数据。你必须提示用户再次输入温度数据，这就太愚蠢了。

幸运的是，你可以用数组来解决这个问题。当你读取数字并计算累加和时，可以填充一个存储温度的数组。然后你可以使用该数组对数据进行第二次遍历。

在在上一个示例中，你使用了 `double` 类型值的数组，但在这里你需要一个 `int` 类型值的数组。不要声明 `double[]` 类型的变量，而是声明一个 `int[]` 类型的变量。你正在询问用户包含多少天的温度，因此在读取完该信息后就可以构造数组：

```java
int numDays = console.nextInt();
int[] temps = new int[numDays];
```

旧的循环如下：

```java
for (int i = 0; i < numDays; i++) {
    System.out.print("Day " + (i + 1) + ": high temp: ");
    temps[i] = console.nextInt();
    sum += temps[i];
}
```

由于你使用了数组，你会希望将其更改为从 0 开始的循环，以匹配数组索引。但仅仅因为你在程序内部使用零基础索引，并不意味着你必须通过询问“第 0 天”高温来困扰用户。你可以修改 `println` 来提示第 (i + 1) 天。此外，你不再需要 `next` 变量，因为值将存储在数组中。因此，循环代码变为：

```java
for (int i = 0; i < numDays; i++) {
    System.out.print("Day " + (i + 1) + ": high temp: ");
    temps[i] = console.nextInt();
    sum += temps[i];
}
```

注意，我们现在正在测试索引是否严格小于 `numDays`。在完成循环完成后，你像之前一样计算平均值。然后你可以写一个循环，使用我们的标准遍历循环来统计有多少天高于平均水平。



```java
int count = 0;
for (int i = 0; i < temps.length; i++) {
    if (temps[i] > average) {
        count++;
```

在这个循环中，测试涉及 `temps.length`。你也可以测试变量是否小于 `numDays`；在这个程序中，这两种选择都是可行的，因为它们应该是相等的。

如果你将这些不同的代码片段组合起来并包含报告高于平均水平天数的代码，你将得到以下程序：

```java
// 读取一系列高温并报告
// 平均值以及高于平均水平的天数。
public class Temperature2 {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("How many days temperatures?\ ");
        int numDays = scanner.nextInt();
        int[] temps = new int[numDays];

        // 记录温度并寻找平均值
        int sum = 0;
        for (int i = 0; i < numDays; i++) {
            System.out.print("Day " + (i + 1) + ": high temp: ");
            temps[i] = scanner.nextInt();
        }
        double average = (double) sum / numDays;

        // 统计高于平均值的天数
        int count = 0;
        for (int i = 0; i < temps.length; i++) {
            if (temps[i] > average) {
                count++;
            }
        }

        // 报告结果
        System.out.println("Average = " + average + ");\n        System.out.println(count + " days above average: ");
    }
}
```

# 第7章 数组

这里是一个示例执行：

多少天的温度？9

第1天的高温: 75

第2天的高温: 78

第3天的高温: 85

第4天的高温: 71

第5天的高温: 69

第6天的高温: 82

第7天的高温: 74

第8天的高温: 80

第9天的高温: 87

平均值 = 77.88888888888889

5天高于平均水平

## 顺序访问

从第一个到最后一个按顺序方式处理值。

`Scanner`对象通常是你随机算法所需要的全部，因为它允许你从第一个到最后一个方式访问数据。但正如我们看到的，没有方法可以将`Scanner`重置回开头。我们刚刚看到的示例程序使用数组允许对数据进行第二次遍历，但本质上仍然是顺序方法，因为它涉及到对数据的两次正向遍历。数组是一种强大的数据结构，允许更复杂的访问，称为随机访问：

## 随机访问

以任何顺序处理值，并快速访问每个值。

数组可以提供随机访问，因为它作为连续的内存块被分配。计算机可以快速计算特定值存储的位置，因为它知道每个元素在内存中占用多少空间，并且知道它们在数组中是相邻的。

让我们探索一个随机访问很重要的问题。假设老师给出的评分范围是 0 到 4，老师想知道分数的分布情况。换句话说，老师想知道有多少个 0 分、1 分、2 分、3 分和 4 分。假设老师包含了如下分数的文件：

```
1 4 0 3 2 1
3 0 2 3 4 1
2 4 1 3 1
2 3 0 4 1
```

## 7.1 数组基础

## 常见编程错误

### 差一错误（Off-by-One Bug）

在将`Temperature`程序转换为使用数组的形式时，你将循环改为从索引 0 开始而不是 1。原始的循环是这样写的：

```java
for (int i = 1; i <= numDays; i++) {
    System.out.print("Day " + i + "'s temp: ");
    int next = console.nextInt();
    sum += next;
}
```

由于你将值存储到数组而不是读入名为`next`的变量，你用`temps[i]`替换了`next`：

```java
for (int i = 1; i <= numDays; i++) {
    System.out.print("Day " + i + "'s high temp: ");
    temps[i] = console.nextInt();
    sum += temps[i];
}
```

由于数组从 0 开始，你将循环边界改为从 0 开始并调整了打印语句。这些是你所做的修改：

```java
for (int i = 0; i <= numDays; i++) {
    System.out.print("Day " + (i + 1) + "'s high temp: ");
    temps[i] = console.nextInt();
    sum += temps[i];
}
```

这在运行时会产生错误。因为它多了一额外的数据并抛出了异常。如下执行所示：

多少天的温度？5

第1天的高温: 82

第2天的高温: 80

第3天的高温: 79

第4天的高温: 71

第5天的高温: 75

第6天的高温: 83

Exception in thread "main"

`java.lang.ArrayIndexOutOfBoundsException: 5`

`at Temperature2.main(Temperature2.java:18)`

问题在于，如果你让循环变量从 0 开始，你需要测试它严格小于所需的迭代次数。

# 第7章 数组

你将 1 改为 0 但留下了`<=`测试。这是一个经典的差一错误。修复方法是将边界改为严格小于：

```java
// 正确的边界
for (int i = 0; i < numDays; i++) {
    System.out.print("Day " + (i + 1) + ": high temp: ");
    temps[i] = console.nextInt();
    sum += temps[i];
}
```

老师可以手数分数，但使用计算机来计数要容易得多。你如何解决这个问题？首先，你意识到你正在执行独立的计数任务：你正在统计数字 0、1、2、3 和 4 出现的次数。你需要五个计数器来解决这个问题，这意味着数组是存储数据的极好方法。通常，每当你发现自己需要某种数据时，都应该考虑使用长度为 n 的数组。

```java
int[] count = new int[5];
```

这将分配一个五个整数的数组，并将每个初始化为 0：

| [0] | [1] | [2] | [3] | [4] |
|---|---|---|---|---|
| count | 0 | 0 | 0 | 0 |

如果你是从文件中读取，你需要一个`Scanner`和一个循环，直到没有更多可以读取的记录：

```java
Scanner input = new Scanner(new File("tally.dat"));
while (input.hasNextInt()) {
    int next = input.nextInt();
    // process next
}
```

为了完成这段代码，你需要确定如何处理每个值（0、1、2、3 或 4）。如果是 0，你就知道`next`将是五个值之一：你需要增加对应 0 的计数器，即`count[0]`；如果是 1，你想增加对应 1 的计数器，即`count[1]`，以此类推。我们一直以来使用嵌套的`if/else`语句来解决这类问题。

## 7.1 数组基础

```java
if (next == 0) {
    count[0]++;
} else if (next == 1) {
    count[1]++;
} else if (next == 2) {
    count[2]++;
} else if (next == 3) {
    count[3]++;
} else { // next == 4
    count[4]++;
}}
```

使用数组，你可以更直接地解决这个问题：

```java
count[next]++;
```

与嵌套的`if/else`结构相比，这行代码非常短，以至于你起初可能没有意识到它的作用是完全相同的。让我们精确模拟一下从文件中读取各种值时会发生什么。

当数组被构造时，所有的计数器都被初始化为 0：

| [0] | [1] | [2] | [3] | [4] |
|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 1 |

输入文件的第一个值是 1，所以程序将其读取到`next`中。然后它执行了这行代码：

```java
count[next]++;
```

因为`next`是 1，这行代码变成了：

```java
count[1]++;
```

所以索引 [1] 处的计数器加了：

| [0] | [1] | [2] | [3] | [4] |
|---|---|---|---|---|
| 0 | 1 | 0 | 0 | 1 |

然后从输入文件中读取了 4，这意味着`count[4]`增加了：

| [0] | [1] | [2] | [3] | [4] |
|---|---|---|---|---|
| 0 | 1 | 0 | 0 | 2 |

接着从输入文件中读取了另一个 1，这增加了`count[1]`：

| [0] | [1] | [2] | [3] | [4] |
|---|---|---|---|---|
| 0 | 2 | 0 | 0 | 2 |

然后从输入文件中读取了 0，这增加了`count[0]`：

| [0] | [1] | [2] | [3] | [4] |
|---|---|---|---|---|
| 1 | 2 | 0 | 0 | 2 |

# 第 7 章 数组

注意，在这一组简短的数据中，你从索引 1 跳到索引 4，然后回到索引 1，再到索引 0。程序继续以此方式执行，在从文件中读取值时在各个计数器之间跳转。这种在数据结构中跳转的能力就是所谓的**随机访问**（random access）。

处理完所有数据后，数组最终看起来如下所示：

![](img/aea18896a4bced58de45f29f5a93f7b3_415_0.png)

当这个循环执行完毕，你可以使用标准的遍历循环配合`println`来报告每个数的总数：

```java
for (int i = 0; i < count.length; i++) {
    System.out.println(i + " : " + count[i]);
}
```

如果你将这些内容整合在一起并为输出添加一个表头，你就得到了完整的程序：

```java
1 // 读取一系列值并报告每个值的
2 // 出现频率。
3
4 import java.io.*;
5 import java.util.*;
7 public class Tally {
8     public static void main(String[] args) 
9         throws FileNotFoundException {
10        Scanner input = new Scanner(new File("tally.dat"));
11        int[] count = new int[5];
12        while (input.hasNextInt()) {
13            int next = input.nextInt();
14            count[next]++;
15        }
16
17        System.out.println("Value\t\tOccurrences");
18        for (int i = 0; i < count.length; i++) {
19            System.out.println(i + "\t" + count[i]);
20        }
21    }
}
```

根据之前显示的示例输入文件，它产生了以下输出：

| Value | Occurrences |
|---|---|
| 0 | 5 |
| 1 | 9 |
| 2 | 6 |
| 3 | 9 |
| 4 | 11 |

要意识到，使用数组编写的程序比使用简单变量和`if/else`语句编写的程序要灵活得多。例如，假设你想调整此程序以处理分数范围从 0 到 100 的输入文件。你唯一需要做的更改就是分配一个更大的数组：

```java
int[] count = new int[101];
```

如果你用`if/else`方法来编写程序，你将需要添加 96 个新分支来适应新的值范围。使用数组解决方案，你只需要修改数组的总尺寸。注意，数组的大小比最高分大一个（101 而不是 100），因为数组是从 0 开始的，而且当 0 是可能的时，你在测试中实际上可以得到 101 个不同的分数。

## 数组与方法

你花了大量时间学习如何操作`int`和`double`类型的变量，因此你可能需要一段时间才能适应在操作数组时出现的差异。记住，基本数据类型`int`和`double`具有**值语义**（value semantics）。例如，在第 3 章中，我们遇到了以下意图将数值翻倍的方法：

```java
public static void doubleNumber(int number) {
    System.out.println("Initial value of number = " + number);
    number *= 2;
    System.out.println("Final value of number = " + number);
}
```

打印结果显示该方法成功地翻倍了局部变量`number`，但我们发现它并没有翻倍传入的变量。这是因为基本类型具有值语义。数组是对象，它们具有**引用语义**（reference semantics），这意味着数组存储的是引用，参数传递涉及的是引用。

为了更好地理解这一点，让我们来看一个特定的例子。在本章的前面，我们看到了构造奇数数组并递增的代码：

```java
int[] list = new int[5];
for (int i = 0; i < list.length; i++) {
    list[i] = 2 * i + 1;
}
```

当我们将递增循环移动到方法时会发生什么。我们需要数组作为参数。为了与原始数组区分，我们将`list`重命名为`data`。记住数组类型是`int[]`，所以方法写为：

```java
public static void incrementAll(int[] data) {
    for (int i = 0; i < data.length; i++) {
        data[i]++;
    }
}
```

你可能认为这个方法像`double`一样没有任何作用，或者认为我们必须返回数组以便更改被记住。但使用数组作为参数，这种方法实际上是有效的。我们可以用调用方法替换原始代码中的递增循环：

```java
int[] list = new int[5];
for (int i = 0; i < list.length; i++) {
    list[i] = 2 * i + 1;
}
incrementAll(list);
```

这段代码产生的结果与原始代码相同。让我们看看为什么它是有效的。执行`for`循环后，数组将包含奇数：

![](img/aea18896a4bced58de45f29f5a93f7b3_417_0.png)

我们调用`incrementAll`方法并将数组作为参数。此时我们看到了简单`int`的行为与数组行为之间的关键区别。实际上，我们制作了变量`list`的副本，但`list`本身并不是数组；它存储的是对数组的引用。因此，当我们复制该引用时，我们得到了指向同一个对象的两个引用：

![](img/aea18896a4bced58de45f29f5a93f7b3_417_1.png)

`data`和`list`都指向同一个对象；当我们通过`data[i]++`更改`data`时，我们改变的是`list`所指向的对象。所以当循环递增`data`的每个元素后，我们得到了结果：

![](img/aea18896a4bced58de45f29f5a93f7b3_417_3.png)

![](img/aea18896a4bced58de45f29f5a93f7b3_417_4.png)

此时，方法执行完毕，参数`data`消失了。我们回到原始代码，此时数组已经被方法修改了。从中得出的关键教训是，当我们传递数组作为参数时，该方法有能力更改数组的内容。我们不需要返回数组来实现这种变化。

## 7.1 数组基础

让我们重写`Tally`程序来演示带有方法和参数传递的完整数组。程序从构造`Scanner`和数组开始，它有两个循环：一个读取输入文件，一个报告结果。我们可以将每个循环放在自己的方法中。第一个循环从`Scanner`读取并将结果存储在数组中，因此它需要两个对象作为参数。第二个循环报告数组中的值，因此它需要数组作为参数。因此，方法可以重写为：



```java
public static void main(String[] args)
    throws FileNotFoundException {
    Scanner input = new Scanner(new File("tally.dat"));
    int[] count = new int[5];
    readData(input, count);
    reportResults(count);
}
```

要编写`readData`方法，我们只需要将文件处理循环移动到方法并提供适当的头：

```java
public static void readData(Scanner input, int[] count) {
    while (input.hasNextInt()) {
        int next = input.nextInt();
        count[i] = next;
    }
}
```

就像`incrementAll`方法一样，这个方法即使不返回数组也会更改数组。但这不是这种情况下的最佳方法。看起来`readData`方法要求你构造一个数组并将其作为参数传递。为什么`readData`不自己构造数组呢？那将简化方法的调用，特别是当我们多次调用它时。

如果`readData`要构造数组，它将必须返回它的引用。否则，只有方法将拥有新构造数组的引用。在当前形式下，`readData`方法假设数组已经构造，这就是为什么我们在`main`方法中写了两行代码：

```java
int[] count = new int[5];
readData(input, count);
```

如果方法要构造数组，它就不需要作为参数传递，但它必须由方法返回。因此，我们可以将`main`方法中的两行代码重写为一行：

```java
int[] count = readData(input);
```

并且我们可以重写`readData`方法使其构造并返回数组：

```java
public static int[] readData(Scanner input) {
    int[] count = new int[5];
    while (input.hasNextInt()) {
```

## 第7章 数组

```java
int next = input.nextInt();
count[next]++;

return count;
```

请密切注意此方法的头部。它不再将数组作为参数，而且它的返回类型是`int[]`而不是`void`。它还以一个返回语句结尾，返回它所构造的数组的引用。

如果我们结合这个新版本的方法与`reportResults`方法的实现，就会得到下面的完整程序：

```java
// 带有方法的 Tally 程序变体
import java.io.*;
import java.util.*;

public class Tally2 {
    public static void main(String[] args)
        throws FileNotFoundException {
        Scanner input = new Scanner(new File("tally.data"));
        int[] count = readData(input);
        reportResults(count);
    }

    public static int[] readData(Scanner input) {
        int[] count = new int[5];
        while (input.hasNextInt()) {
            int next = input.nextInt();
            count[next]++;
        }
        return count;
    }

    public static void reportResults(int[] count) {
        System.out.println("Value: " + count.length);
        for (int i = 0; i < count.length; i++) {
            System.out.println(i + "\t" + count[i]);
        }
    }
}
```

此版本产生的输出与原始版本相同。

## For-Each 循环

Java 5 引入了一种新的循环结构，简化了某些数组循环。它被称为增强型 for 循环，或者叫 for-each 循环。每当你想要检查数组中的每个值时，就可以使用它。例如，在`Temperature2`程序中，有一个名为`temps`的数组变量，并且包含如下代码：

```java
for (int i = 0; i < temps.length; i++) {
    if (temps[i] > average) {
        above++;
    }
}
```

### 7.1 数组基础

我们可以将其重写为 for-each 循环：

```java
for (int n : temps) {
    if (n > average) {
        above++;
    }
}
```

这个循环通常读作“对于 temps 中的每个 int...”。for-each 循环的基本语法格式为：

```java
for (<type> <name> : <array>) {
    <statement>
    <statement>
    ...
}
```

变量名本身并没有什么特殊之处，只要你在循环体中保持一致即可。例如，上一个循环可以使用变量`x`代替变量`n`来编写：

```java
for (int x : temps) {
    if (x > average) {
        above++;
    }
}
```

for-each 循环在你仅仅想按顺序检查每个值时最有用。在许多情况下，for-each 循环并不适用。例如，下面的循环将使名为`list`的数组中的每个值都翻倍：

```java
for (int i = 0; i < list.length; i++) {
    list[i] *= 2;
}
```

由于循环正在改变数组，因此你无法将其替换为 for-each 循环：

```java
for (int n : list) {
    n *= 2; // 只改变了 n，没有改变数组
}
```

正如注释所示，之前的循环在不改变数组元素的情况下翻倍了变量`n`。此外，在某些情况下，即使代码涉及按顺序检查每个数组元素，for-each 循环也不是最方便的。例如，考虑`Tally`程序中的循环：

```java
for (int i = 0; i < count.length; i++) {
    System.out.println(i + "\t" + count[i]);
}
```

可以使用 for-each 循环来替换数组访问：

```java
for (int n : count) {
    System.out.println(i + "\t" + n); // 这并不合法
}
```

然而，这会导致一个问题。我们想要打印`i`的值，但当我们将其转换为 for-each 循环时，已经消除了`i`。我们必须添加额外的代码来跟踪`i`的值，如下：

```java
// 合法但笨拙
int i = 0;
for (int n : count) {
    System.out.println(i + "\t" + n);
}
```

在这种情况下，for-each 循环并没有真正简化问题，原始版本可能更清晰。

## 数组初始化

Java 有一种特殊的语法，用于在你确切知道想放入什么内容时初始化数组。例如，你可以编写以下代码来初始化一个整数数组，以跟踪每月有多少天（“九月有30天...”），以及一个 String 数组以跟踪星期几的缩写：

```java
int[] daysIn = new int[12];
daysIn[0] = 31;
daysIn[1] = 28;
daysIn[2] = 31;
daysIn[3] = 30;
daysIn[4] = 31;
daysIn[5] = 30;
daysIn[6] = 31;
daysIn[7] = 31;
daysIn[8] = 31;
daysIn[9] = 30;
daysIn[10] = 31;
daysIn[11] = 30;

String[] dayNames = new String[7];
dayNames[0] = "Sunday";
dayNames[1] = "Monday";
dayNames[2] = "Tuesday";
dayNames[3] = "Wednesday";
dayNames[4] = "Thursday";
dayNames[5] = "Friday";
dayNames[6] = "Saturday";
```

或者使用更短的写法：

```java
int[] daysIn = {31, 28, 31, 30, 31, 30, 31, 31, 31, 30, 31, 30};
String[] dayNames = {"Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"};
```

## 数组的局限性

你应该意识到数组的某些局限性：

- 你无法改变数组的大小。因为数组是连续的内存块，要让它变大你需要构造新数组并从旧数组复制值。Java 提供了`ArrayList`来自动处理这一点。
- 你无法使用简单的测试来比较数组相等。由于数组是对象，如果你询问它们是否相等，你是在询问它们是否为同一个对象。
- 你无法使用简单的语句打印数组。

这些局限性自 Java 引入以来一直存在。多年来，Sun 引入了一些类来解决这些问题。`Arrays`类属于`java.util`包。

## 数组遍历算法

上一节介绍了两种处理数组的标准模式。第一种使用`int`类型的变量索引每个数组值：

```java
for (int i = 0; i < array.length; i++) {
    // 对 array[i] 执行操作
}
```

第二是 for-each 循环：

```java
for (<type> <name> : <array>) {
    // 对 name 执行语句
}
```

在本节中，我们将探索使用这些模式实现的一些常用算法。当然，并不是所有的操作都能通过这种方式实现——本节以一个需要修改标准版本的示例结束。

我们将每个操作实现为一个方法。Java 不允许直接编写数组代码，因此我们需要选择一个特定的类型。我们假设你正在操作一个整数数组。如果你正在编写处理不同类型的程序，你将根据你使用的类型修改代码。

## 打印数组

假设你有一个如下的整数数组：

| [0] | [1] | [2] | [3] | [4] | [5] | [6] |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 17 | -3 | 42 | 8 | 12 | 2 | 103 |

你会如何打印数组中的值呢？对于其他类型你可以使用`println`语句，例如：

```java
System.out.println(list);
```

遗憾的是，对于数组这会产生类似如下的奇怪输出：

```text
[I6caf43]
```

这种输出并不是很有用的，它没有告诉我们关于数组的内容。Java 以方法的形式提供了解决此问题的解决方案，该方法名为`Arrays.toString`。

### 7.2 数组遍历算法

`Arrays.toString`将数组转换为方便阅读的文本形式。你可以如下重写`println`以包含对`Arrays.toString`的调用：

```java
System.out.println(Arrays.toString(list));
```

这会产生如下输出：

```text
[17, -3, 42, 8, 12, 2, 103]
```

这是显示数组内容的一种合理方法，在很多情况下它是足够的。然而，对于那些你想要不同输出结果的情况，你可以编写自己的方法。

假设你想将每个数字单独打印一行。在这种情况下，你可以使用`for-each`循环，对每个值执行一次`println`：

```java
public static void print(int[] list) {
    for (int n : list) {
        System.out.println(n);
    }
}
```

然后你就可以使用变量`list`调用此方法：

```java
print(list);
```

这会产生如下输出：

```text
17
-3
42
12
2
103
```

在某些情况下，`for-each`循环可能无法得到你想要。例如，思考一下`Arrays.toString`方法是如何编写的。它产生一个由逗号分隔的值列表，这是一个经典的“栅栏问题”（fencepost problem）（例如，七个值由六个逗号分隔）。为了解决栅栏问题，你会使用索引循环而不是`for-each`循环，这样你就可以在循环之前打印第一个值：

```java
System.out.println(list[0]);
for (int i = 1; i < list.length; i++) {
    System.out.print(", " + list[i]);
}
System.out.println();
```

这里的`i`初始化为 1 而不是 0，因为`list[0]`在循环之前已经被打印了。这段代码对之前的示例数组会产生如下输出：

```text
17, -3, 42, 8, 12, 2, 103
```

## 第7章 数组

然而，这段代码仍然不，因为它假设存在一个`list[0]`可以打印。数组可能是空的（长度为 0），在这种情况下这段代码将生成`ArrayOutOfBoundsException`。以下是一个与`Arrays.toString`行为相同的方法版本。循环之前和之后的打印语句被了修改以包含方括号，并且针对空数组包含了一个特殊情况：

```java
public static void print(int[] list) {
    if (list.length == 0) {
        System.out.println("{}");
    } else {
        System.out.print("[" + list[0]);
        for (int i = 1; i < list.length; i++) {
            System.out.print(", " + list[i]);
        }
        System.out.println("]");
    }
}
```

## 搜索与替换

对于数组，你想搜索一个特定的值。例如，你可能想统计某个值在数组中出现了多少次。假设你有一个如下的`int`值数组：

| [0] | [1] | [2] | [3] | [4] | [5] | [6] |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 8 | 7 | 19 | 82 | 8 | 7 | 8 |

统计出现次数是最简单的搜索任务，因为你总是检查数组中的每个值，并且不需要更改数组的内容。你可以通过一个`for-each`循环来记录你所搜索的值的出现次数：

```java
public static int count(int[] list, int target) {
    int count = 0;
    for (int n : list) {
        if (n == target) {
            count++;
        }
    }
    return count;
}
```

给定此方法，你可以进行以下调用来确定列表中中有多少个 8：

```java
int number = count(list, 8);
```

对于示例数组，该调用会将`number`设置为 3，因为列表中出现了三次 8。如果你改用下述调用：

```java
int number = count(list, 2);
```

`number`将被设置为 0，因为列表中没有 2 出现。你可以通过编写一个返回列表中该值首次出现处索引的方法来实现这一点。有时你想知道某个东西在列表中的位置。你不知道确切会在哪里找到该值，你可以尝试用如下伪代码中的`while`循环：

```pseudocode
int i = 0;
while (我们还没有找到它) {
  i++;
}
```

然而，有一种更简单的方法。因为你正在编写一个返回值的方法，所以一旦找到匹配项，就可以返回相应的索引。这意味着你可以使用标准的遍历循环来解决这个问题：

```java
for (int i = 0; i < list.length; i++) {
  if (list[i] == target) {
    return i;
  }
}
```

记住`return`语句会终止方法，所以一旦找到目标值，你就会跳出此循环。但如果没有找到该值呢？如果你遍历了整个数组都没有发现匹配项，循环将结束而不返回值。Java 库中的约定是返回 -1 表示该值不在列表中。因此，你可以在循环后添加一个额外的`return`语句，它只会在目标值未找到时执行。将这些结合起来得到如下方法：



```java
public static int indexOf(int[] list, int target) {
  for (int i = 0; i < list.length; i++) {
    if (list[i] == target) {
      return i;
    }
  }
  return -1;
}
```

使用该方法，你可以进行以下调用来找到值 7 的第一次出现：

```java
int position = indexOf(list, 7);
```

对于示例数组，该调用会将`position`设置为 1，因为 7 第一次出现在索引 1 处。数组后面还有一个 7，位于索引 5，但这段代码一旦找到匹配项就会终止。如果你执行了如下调用：

```java
int position = indexOf(list, 42);
```

`position`将设置为 -1，因为列表中没有 42。作为一个变体，考虑将所有出现的值替换为某个值的问题。这与计数任务类似。你想遍历数组寻找某个值，并在找到时将其替换。你不能通过`for-each`循环实现这一点，因为改变变量对数组没有影响。使用标准的遍历：

```java
public static void replaceAll(int[] list, int target, int replacement) {
    for (int i = 0; i < list.length; i++) {
        if (list[i] == target) {
            list[i] = replacement;
        }
    }
}
```

注意，尽管方法更改了数组的内容，你不需要返回任何内容来实现这一点。在本节的开头，这些示例涉及`int[]`数组，如果你想操作不同类型的数组（例如如果是`double[]`），你就需要更改类型。但如果你有一个`String`数组，情况就不那么简单了。String 值需要调用`equals`方法而不是使用`==`。这是一个适用于`String`数组的`replaceAll`方法版本：

```java
public static void replaceAll(String[] list, String target, String replacement) {
    for (int i = 0; i < list.length; i++) {
        if (list[i].equals(target)) {
            list[i] = replacement;
        }
    }
}
```

## 测试相等性

由于数组是对象，测试它们的相等性比测试整数和双更复杂。考虑以下代码初始化两个数组对象来存储一组奇数，并将第三个数组变量指向第二个：

```java
int[] list1 = new int[5];
int[] list2 = new int[5];
for (int i = 0; i < list.length; i++) {
    list1[i] = 2 * i + 1;
    list2[i] = 2 * i + 1;
}
int[] list3 = list2;
```

代码的编写方式使得`list2`始终与`list1`相同的长度和值序列。执行这段代码后，内存看起来如下：

| [0] | [1] | [2] | [3] | [4] |
| :--- | :--- | :--- | :--- | :--- |
| 1 | 3 | 5 | 7 | 9 |

| [0] | [1] | [2] | [3] | [4] |
| :--- | :--- | :--- | :--- | :--- |
| 1 | 3 | 5 | 7 | 9 |

我们以前见过这种情况。我们有三个变量但只有两个对象。变量`list2`和`list3`都指向同一个数组对象。结果，如果我们询问`list2 == list3`，答案将是肯定的（表达式求值为`true`）。但如果我们询问`list1 == list2`，答案将是否定的（表达式求值为`false`）。

在编程中，某些时候你想知道两个变量是否指向完全相同的对象，你也会发现你想知道两个对象在值上是否等价。在这种情况下，两个数组被特意构建为匹配的，所以你可能想询问两个数组在值上是否相等。对于数组，这意味着它们具有相同的长度并存储相同的值序列。

`Arrays.equals`方法提供了这一功能。所以你可以如下写：

```java
if (Arrays.equals(list1, list2)) {
    System.out.println("The arrays are equal");
}
```

就像`Arrays.toString`方法一样，通常`Arrays.equals`方法就是你需要的。但有时你想要稍微的变体，所以值得探索如何自己编写该方法。

该方法将两个数组作为参数并返回一个指示两个数组是否相等的布尔值。因此，该方法看起来如下：

```java
public static boolean equals(int[] list1, int[] list2) {

}
```

当你坐下来写这样的方法时，你可能从定义相等性的角度来思考：“数组是等的，如果它们的长度相等并且存储相同的值序列。”但这并不是容易的方法。例如，你可以先测试长度是否相等，然后该做什么呢？

```java
public static boolean equals(int[] list1, int[] list2) {
    if (list1.length == list2.length) {
        // 我们该做什么？
    }

}
```

# 第 7 章 数组

如果你从相反的条件来考虑，这类方法通常会更容易编写：什么会导致两个数组不相等？与其测试长度是否相等，不如从测试长度是否不等开始。在这种情况下，你确切知道该做什么。如果长度不相等，你可以返回`false`，因为你知道这两个数组不相等：

```java
public static boolean equals(int[] list1, int[] list2) {
    if (list1.length != list2.length) {
        return false;
    }
}
```

如果你通过了`if`语句，你就知道数组的长度是相等的。这时，你想检查它们是否存储了相同的值序列。同样，要测试不等性而不是相等，如果存在差异则返回`false`：

```java
public static boolean equals(int[] list1, int[] list2) {
    if (list1.length != list2.length) {
        return false;
    }

    for (int i = 0; i < list1.length; i++) {
        if (list1[i] != list2[i]) {
            return false;
        }
    }
}
```

如果你通过了`for`循环，你就知道两个数组的长度相等，并且它们存储了完全相同的值序列。在这种情况下，你想返回值`true`来表示数组相等。这完成了该方法：

```java
public static boolean equals(int[] list1, int[] list2) {
    if (list1.length != list2.length) {
        return false;
    }

    for (int i = 0; i < list1.length; i++) {
        if (list1[i] != list2[i]) {
            return false;
        }
    }

    return true;
}
```

这是`equals`这类方法的常用模式：你测试两个对象可能不相等的所有方式，如果发现任何差异则返回`false`，最后你在最后返回`true`，这样如果通过了所有测试，两个对象就会被声明为相等。

## 7.2 数组遍历算法

### 反转数组

作为常用操作的最后一个示例，让我们考虑反转数组中存储元素顺序的任务。例如，假设你有一个数组，其中存储了以下值：

一种方法是创建一个新数组，并将第一个数组中的值反序存储到第二个数组中。虽然那种方法是合理的，但你应该在不构建第二个数组的情况下解决这个问题。另一种方法是将问题视为一系列的交换或切换（swaps）。例如，列表前面的值 3 和列表末尾的值 78 需要交换：

在交换了这对元素后，你可以交换下一对（索引为 1 和 4 的值）：

并继续交换，直到整个列表被反转。在我们查看反转代码之前，让我们先考虑交换两个值的通用问题。假设你有get两个整型变量`x`和`y`，值分别为 3 和 78：

```java
int x = 3;
int y = 78;
```

你将如何交换这些值呢？一种原始的方法是简单地向两个方向赋值：

```java
// 无法正常交换
x = y;
y = x;
```

遗憾的是，这并不起作用。你开始时的状态如下：

```java
x = 3; y = 78;
```

当执行第一条赋值语句时，你将`y`的值拷贝到`x`中：

| x | y |
| --- | --- |
| 78 | 78 |

你想让`x`最终等于 78，但如果你尝试用这种方式解决问题，你就丢失了`x`的旧值。第二条赋值语句将`x`的新值 78 拷贝回`y`，导致你的两个变量都等于 78。

标准的解决方案是引入一个临时变量，在你给`x`赋予新值时可以使用它来存储`x`的旧值。然后你可以从临时变量将`x`的旧值拷贝到`y`以完成交换：

```java
int temp = x;
x = y;
y = temp;
```

通过这段代码，你首先将`x`的旧值拷贝到`temp`：

| x | y | temp |
| --- | --- | --- |
| 3 | 78 | |

然后你将`y`的值放入`x`中：

| x | y | temp |
| --- | --- | --- |
| 78 | 78 | |

接下来，你将`x`的旧值从`temp`拷贝到`y`：

| x | y | temp |
| --- | --- | --- |
| 78 | 3 | 3 |

此时，你已成功交换了`x`和`y`的值，所以你不再需要`temp`了。

在某些语言中，你可以将其定义为一个交换方法，用于交换两个`int`值：

```java
// 这个方法将不起作用
public void swap(int x, int y) {
    int temp = x;
    x = y;
    y = temp;
}
```

正如你所看到的，这种方法在 Java 中不起作用，因为`x`和`y`是整数值的拷贝。由于数组是作为对象存储的，你可以编写该方法的变体，接收一个数组和两个索引，并交换这些索引处的值：

```java
public void swap(int[] list, int i, int j) {
    int temp = list[i];
    list[i] = list[j];
    list[j] = temp;
}
```

## 7.3 高级数组技术

在本这一节中，我们将讨论数组的一些高级用法，例如无法通过简单的遍历解决的算法。我们还将学习创建存储对象而不是原始值的数组。

### 移动数组中的值

你想移动数组中的一组值。例如，假设你有一个整数数组，其中存储了 (3, 8, 9, 7, 5) 序列，你想旋转这些值，使得列表前面的值移到最后，而其他值的顺序保持不变。换句话说，你想将 3 移最后，产生 (8, 9, 7, 5, 3)。让我们探索如何编写代码来执行该操作。

## 7.3 高级数组技术

假设你有一个类型为`int[]`的变量`list`，长度为 5，存储了值 (3, 8, 9, 7, 5);

![](img/aea18896a4bced58de45f29f5a93f7b3_434_0.png)

移位操作（shifting operation）与上一节讨论的交换操作（swap operation）类似，你会发现在这里使用临时变量也是很有用的。列表开头的 3 应该移动到末尾，而其他值应该向前旋转。你可以通过将列表开头的值（在本例中为 3）存储在局部变量中使任务变得更容易：

```java
int first = list[0];
```

在值安全妥存后，你现在需要将其他四个值移动一个位置：

![](img/aea18896a4bced58de45f29f5a93f7b3_434_1.png)

整个任务分解为四个不同的移位操作，每个操作都是一个简单的赋值语句：

```java
list[0] = list[1];
list[1] = list[2];
list[2] = list[3];
list[3] = list[4];
```

显然，你希望将其写成循环，而不是编写一系列单独的赋值语句。之前的每个语句形式如下：

```java
list[i] = list[i + 1];
```

你用当前存储在列表元素`[i + 1]`中的值替换列表元素`[i]`，从而使值向左移动。作为第一次尝试，你可以将此行代码放在遍历循环中：

```java
for (int i = 0; i < list.length; i++) {
    list[i] = list[i + 1];
}
```

这几乎正确答案，但它有一个差一错误（off-by-one bug）。该循环对于示例数组会执行五次，但你只想移动四个值（你希望在`i`等于 0、1、2 和 3 时进行赋值，而不是在`i`等于 4 时）。所以，这个循环执行多了一次。在循环迭代中，当`i`等于 4 时，它执行这行代码：

```java
list[i] = list[i + 1];
```

变为：

```java
list[4] = list[5];
```

并没有`list[5]`这个值，因为数组只有五个元素，索引为 0-4。因此这段代码会产生`ArrayOutOfBoundsException`。要修复这个问题，请修改循环使其提前停止：

```java
for (int i = 0; i < list.length - 1; i++) {
    list[i] = list[i + 1];
}
```

使用`(list.length - 1)`代替通常的`list.length`。你可以将此表达式中的减 1 理解为对赋值语句中加 1 的抵消。

当然，还有一个细节需要处理。在将值向左移动后，你为原本位于开头的值在列表末尾留出了空间（该当前存储在名为`first`的局部变量中）。循环执行后，你必须将值放在索引处：

```java
list[list.length - 1] = first;
```

将这一切整合到一个静态方法中，你得到：

```java
public static void rotateLeft(int[] list) {
    int first = list[0];
    for (int i = 0; i < list.length - 1; i++) {
        list[i] = list[i + 1];
    }
    list[list.length - 1] = first;
}
```

一个有趣的变体是将值向右旋转而不是向左旋转，这是逆向操作。在这种情况下，你想要将列表末尾的值带到开头，并将其余值向右移动。所以，如果名为`list`的变量初始存储了值 (5, 3, 8, 9, 7)，它将把 5 带到开头并存储这些值。

首先将要旋转的值存入临时变量中：

```java
int last = list[list.length - 1];
```

然后将其他值向右移动：

| 3 | 8 | 9 | 7 | 5 |
| --- | --- | --- | --- | --- |
| 3 | 3 | 8 | 9 | 7 |

在这种情况下，四个单独的赋值语句将是：

```java
list[1] = list[0];
list[2] = list[1];
list[3] = list[2];
list[4] = list[3];
```

或者更通用的写法：

```java
list[i] = list[i-1];
```

如果你将其放在标准的`for`循环中，你会得到：

```java
// 无法工作
for (int i = 0; i < list.length; i++) {
    list[i] = list[i-1];
}
```

这段代码有两个问题。首先，另一个差一错误。你想要执行的第一个赋值语句会将`list[1]`设置为`list[0]`的内容，但这个循环将`list[0]`设置为`list[-1]`。这会产生`ArrayIndexOutOfBoundsException`，因为没有`list[-1]`。你希望让`i`从 1 开始：

```java
// 仍然无法工作
for (int i = 1; i < list.length; i++) {
    list[i] = list[i-1];
}
```

然而，这也不行。它虽然避开了`ArrayIndexOutOfBoundsException`，但想想它做了什么。第一次循环将`list[1]`设置为`list[0]`中的值：

![](img/aea18896a4bced58de45f29f5a93f7b3_434_0.png)

![](img/aea18896a4bced58de45f29f5a93f7b3_434_1.png)

值 8 发生了什么？它被覆盖了。下一次循环将`list[2]`设置为`list[1]`：



`(img/aea18896a4bced58de45f29f5a93f7b3_434_2.png)` `(img/aea18896a4bced58de45f29f5a93f7b3_434_3.png)` 你可能会说：“等一下……`list[1]` 不是 3，而是 8。” 当你开始时，`list[1]` 是 8，但循环的第一次迭代将 8 替换为了 3，现在 3 被复制到了 9 所在的位置。循环就这样继续，将 3 放入数组的每个单元格。显然这不是你想要的。要让这段代码工作，必须反向运行循环（从右到左）。所以让我们回到起始状态：

| [0] | [1] | [2] | [3] | [4] |
|---|---|---|---|---|
| 3 | 8 | 9 | 7 | 5 |

我们将列表末尾的值存入局部变量中。这释放了数组的最后一个位置。现在，将 `list[4]` 设置为 `list[3]` 中的值：

| [0] | [1] | [2] | [3] | [4] |
|---|---|---|---|---|
| 3 | 8 | 9 | 7 | 7 |

这消除了末尾的 5，但该值安全地存储在局部变量中。一旦你执行了这次赋值，就释放了 `list[3]`，这意味着你现在可以将 `list[3]` 设置为 `list[2]` 中的值：

| [0] | [1] | [2] | [3] | [4] |
|---|---|---|---|---|
| 3 | 8 | 9 | 9 | 7 |

过程以这种方式继续，将 8 从索引 1 复制到索引 2，将 3 从索引 0 复制到索引 1，最后你得到：

| [0] | [1] | [2] | [3] | [4] |
|---|---|---|---|---|
| 3 | 3 | 8 | 9 | 7 |

此时，唯一剩下的工作是将存储在局部变量中的 5 放在列表开头：

| [0] | [1] | [2] | [3] | [4] |
|---|---|---|---|---|
| 5 | 3 | 8 | 9 | 7 |

你可以通过将 `i++` 初始化改为 `i--` 并测试来反转 `for` 循环。将这一切整合，你得到以下方法：

```java
public static void rotate(int[] list) {
    int last = list[list.length - 1];
    for (int i = list.length - 1; i > 0; i--) {
        list[i] = list[i - 1];
    }
    list[0] = last;
}
```

## 对象数组

我们目前看到的所有数组都存储了基本类型值（如简单的 `int` 值），但你可以拥有任何 Java 类型的数组。不过，对象数组的行为略不同，因为对象被存储为引用而不是数据值。构造对象数组通常有两个步骤的过程，因为你通常需要同时构造数组和单个对象。例如，考虑以下语句：

```java
Point[] points = new Point[3];
```

这声明了一个名为 `points` 的变量，它指向一个长度为 3 的数组，该数组存储对 `Point` 对象的引用。`new` 关键字并没有构造任何的 `Point` 对象。它构造了一个长度为 3 的数组，每个元素都可以存储对 `Point` 的引用。当 Java 构建数组时，会自动将这些数组元素初始化为类型的零值。所有引用类型的零值都是特殊值 `null`，它表示“没有对象”：

| [0] | [1] | [2] |
|---|---|---|
| points -> null | null | null |

真正的 `Point` 对象必须使用 `new` 关键字单独构造，如下：

```java
Point[] points = new Point[3];
points[0] = new Point(3, 7);
points[1] = new Point(4, 5);
points[2] = new Point(6, 2);
```

在执行这些行代码后，你将拥有由各个数组元素引用的单个 `Point` 对象：

| [0] | [1] | [2] |
|---|---|---|
| points -> x 3, y 7 | x 4, y 5 | x 6, y 2 |

注意，`new` 关键字需要在四个不同的地方，因为有四个对象需要构造：数组本身以及三个单独的 `Point` 对象。

## 第 7 章 数组

你也可以使用大括号符号来初始化数组；在这种情况下，你不需要 `new` 关键字来构造数组本身：

```java
Point[] points = {new Point(3, 7), new Point(4, 5),
                    new Point(6, 2)};
```

## 命令行参数

正如你从第 1 章开始看到的，每当你定义 `main` 方法时，都必须包含一个 `String[] args` 作为参数，这是一个 `String` 对象的数组。当在调用 Java 时，如果用户提供了所谓的“命令行参数”，Java 本身会初始化这个数组。例如，一个 Java 类 `DoSomething` 通常通过类似这样的命令从命令行界面启动：

```
java DoSomething
```

用户可以选择输入额外的参数，例如：

```
java DoSomething temperature.dat
```

在这种情况下，用户指定了两个额外的参数作为程序将使用的文件名（例如，输入文件和输出文件）。如果用户在启动 Java 时输入了这些额外参数，`main` 方法的 `String[]` 参数将被初始化长度为 2 的数组，存储这两个字符串：

## 7.4 多维数组（可选）

在前几节中的数组示例都涉及所谓的“一维数组”（单行或单列数据）。通常，你可能以多维的方式存储数据。例如，你可能想存储一个既有行又有列的二维数据网格。幸运的是，你可以形成任意维数的数组：

- `double`: 一个 `double`
- `double[]`: 一个一维 `double` 数组
- `double[][]`: 一个二维的 `double` 网格
- `double[][][]`: 一个三维的 `double` 集合

超过一维的数组被称为多维数组。

## 多维数组

数组的数组，通过多个整数访问其元素。

## 矩形二维数组

多维数组的用法是具有特定宽度和高度的二维数组。例如，假设你在三个不同的日期进行了一系列五次温度读取。你可以如下定义一个具有三行五列的二维数组：

```java
double[][] temps = new double[3][5];
```

注意，在该赋值语句的左侧和右侧，你都必须使用双方括号。在描述左侧类型时，你必须明确这不仅仅是一个一维值序列（类型为 `double[]`），而是一个二维值网格（类型为 `double[][]`）。在右侧构造数组时，你必须指定网格的维度。通常的惯例是先列出第一行，然后是列。生成的数组如下：

| | [0] | [1] | [2] | [3] | [4] |
|---|---|---|---|---|---|
| [0] | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 |
| [1] | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 |
| [2] | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 |

对于一维数组，值被初始化为 0.0，且行和列的索引都从 0 开始。一旦创建了这样的数组，你可以通过提供特定的行和列数（按此顺序）引用单个元素。例如，将第一行的第四个值设置为 99.3，将第三行的第一个值设置为 99.4，你可以说：

```java
temps[0][3] = 99.3; // 第一行的第四个值
temps[2][0] = 99.4; // 第三行的第一个值
```

执行这些行代码后，数组将如下所示：

| | [0] | [1] | [2] | [3] | [4] |
|---|---|---|---|---|---|
| [0] | 0.0 | 0.0 | 0.0 | 99.3 | 0.0 |
| [1] | 0.0 | 0.0 | 0.0 | 0.0 | 0.0 |
| [2] | 99.4 | 0.0 | 0.0 | 0.0 | 0.0 |

以分步骤的方式思考这是有帮助的，从数组名称开始。例如，如果你想引用第三行的第一个值，可以通过以下步骤获取：

- `temps`: 整个网格
- `temps[2]`: 整个第三行
- `temps[2][0]`: 第三行的第一个元素

你可以像传递一维数组一样将多维数组作为参数传递。不过你需要注意类型。要传递温度网格，你必须使用类型为 `double[][]` 的参数（带有两组方括号）。例如，这里有一个打印内容的方法：

```java
public static void print(double[][] grid) {
  for (int i = 0; i < grid.length; i++) {
    for (int j = 0; j < grid[i].length; j++) {
      System.out.print(grid[i][j] + " ");
    }
    System.out.println();
  }
}
```

（注：提供的 OCR 文本在后半部分包含大量重复和乱码部分。根据 Java 数组和帕斯卡三角形的上下文，以下文本已清理，以反映描述教材内容的逻辑流。）

## 7.4 多维数组（可选）

## 锯齿数组

锯齿数组是指每行元素数量不同的数组。观察三角形，你会发现第一行（行 0）有一个值，第二行（行 1）有两个值，依此类推。第 $i$ 行有 $(i + 1)$ 个值，因此我们对伪代码进行如下完善：

```java
for (int i = 0; i < triangle.length; i++) {
    triangle[i] = new int[i + 1];
    // 使用 triangle[i-1] 填充 triangle[i]
}
```

## 7.4 多维数组（可选）

| [0] | [1] | [2] | [3] | [4] |
|---|---|---|---|---|
| [5] | 1 | | | |
| [1] | 1 | | | |
| [2] | 1 | 2 | | |
| [3] | 1 | 3 | 3 | |
| [4] | 1 | 4 | 6 | 4 |
| [5] | 1 | 5 | 10 | 5 |

`(img/aea18896a4bced58de45f29f5a93f7b3_444_0.png)`

我们已经写了代码来填充每行开头和结尾的 1。现在，我们需要编写代码来填充中间的值。看第 5 行示例。列 1 中的值 5 存在于上一行列 0 和列 1 中值 1 和 4 之和。列 2 中的值 10 存在于上一行列 1 和列 2 值之和。

更通地说，这些中间值中的每一个都是上一行中紧邻正上方和正左方的两个值之和。在其他行中，对于列 `j`：

```
triangle[i][j] = (value above and left) + (value above);
```

我们可以通过使用适当的数组索引将其转换为实际代码：

```
triangle[i][j] = triangle[i-1][j] + triangle[i][j-1];
```

我们需要将此语句包含在一个 `for` 循环中，以便它能分配所有的中间值，从而允许我们将伪代码完成为实际代码：

```java
for (int i = 0; i < length; i++) {
  triangle[i] = new int[i + 1];
  triangle[i][0] = 1;
  for (int j = 1; j < i; j++) {
    triangle[i][j] = triangle[i-1][j] + triangle[i][j-1];
  }
}
```

如果我们将这段代码包含在一个方法中，并配合类似于之前描述的网格打印方法的打印方法，我们就得到了下面的程序：

```java
// 这个程序构建了一个锯齿状二维数组
// 它存储了帕斯卡三角形。它利用了这样一个事实：
// 每行开头和结尾的 1 之外的每个值都是
// 上一行两个值之和

public class PascalTriangle {
  public static void main(String[] args) {
    int[][] triangle = new int[n][];
    fillTriangle(triangle);
    print(triangle);
  }
```

## 第 7 章 数组

```java
static void fillIn(int[] triangle) {
    for (int i = 0; i < triangle.length; i++) {
        triangle[i] = new int[i + 1];
        triangle[i][0] = 1;
        triangle[i][i] = 1;
        for (int j = 1; j < i; j++) {
            triangle[i][j] = triangle[i - 1][j - 1] +
                triangle[i - 1][j];
        }
    }
}

public static void print(int[] triangle) {
    for (int i = 0; i < triangle.length; i++) {
        for (int j = 0; j < triangle[i].length; j++) {
            System.out.print(triangle[i][j] + " ");
        }
        System.out.println();
    }
}
```

它产生了以下输出：

```
1
1 2 1
1 3 3 1
1 4 6 4 1
1 5 10 10 5 1
1 6 15 20 15 6 1
1 7 21 35 35 21 7 1
1 8 28 56 70 56 28 8 1
1 9 36 84 126 126 84 36 9 1
1 10 45 120 210 252 210 120 45 10 1
```

### 7.5 案例研究：工作时长

让我们来看一个涉及使用数组的复杂程序。假设我们有一个输入文件，包含指示员工工作了多少小时的数据，输入文件的每一行表示不同周的工作时长。每周有七天，因此每行可能列出最多七个数字。我们通常认为周一是工作周的开始，所以假设每行先列出周一的工作时长，然后是周二的工作时长，以此类推，最后以周日的工作时长结束。我们允许行的数字少于七个，因为人可能并不总是工作七天。这里有一个我们称之为 `hours.txt` 的示例输入文件：

```
8 8 8 8
8 4 4 4
8 4 4 8
3 0 0 8 6 4 8
0 0 8
```

让我们写一个读取此输入文件并计算每行和每列总的程序。行的总和会告诉我们每周工作了多少小时。列的总和会告诉我们周一、周二等工作了多少小时。解决这个问题的一种方法是将所有数据存储在二维数组中并求和。然而，对于这个特定任务，我们不需要这种复杂的解决方案。我们必须逐行处理输入文件，因此在读取每行数据到数组后立即报告总和是合理的。在这种情况下，可以使用第二个数组来跟踪输入文件的每列累计和。这种方法等同于累加算法。基本方法如伪代码所示：

```
construct array for total;
for (each line of input file) {
  transfer the next line of data into an array;
  report the sum of the array;
}
print total.
```

我们将再次分阶段开发程序：

1. 将输入文件的每行读取到数组，打印每个数组以验证读取正确。
2. 将输入文件的每行读取到数组，汇总列。
3. 一个报告每行总和并以简单格式的完整程序。

## 版本 1：读取输入文件

在程序的第一个版本中，我们将编写读取每行数据到数组的基本文件处理代码。最终我们将必须处理这些数据，但现在只需打印数组以验证代码工作。`main` 方法可以很短，打开输入文件并调用方法来处理文件：

```java
public static void main(String[] args) throws FileNotFoundException {
    Scanner input = new Scanner(new File("hours.txt"));
    processFile(input);
}
```

这留下了编写 `processFile` 代码的任务。我们在第 6 章看到过，对于行方向的数据，通常可以使用以下文件处理代码模式：

```java
while (input.hasNextLine()) {
    String text = input.nextLine();
    processText(text);
}
```

对于这个版本的程序，处理涉及从字符串传输数据并打印数组。为了保持 `processFile` 短小，可以将传输代码放在单独的方法中，并使用 `Arrays.toString` 打印数组，这意味着 `process` 的主体变为：

```java
while (input.hasNextLine()) {
    String text = input.nextLine();
    int[] next = transferFrom(text);
    System.out.println(Arrays.toString(next));
}
```

`transferFrom` 方法接收一个字符串作为参数，并构造一个包含字符串数字的新数组。通常我们会从字符串创建一个 `Scanner` 以读取单个数字。每行输入最多有七个数字，但可能更少。因此，使用 `while` 循环来测试 `scanner` 是否还有剩余数字待读是合理的：



```text
construct Scanner and array.
while (the Scanner has a next int) {
    process next int from scanner;
}
```

在这种情况下，将输入中的下一个整数存储在数组中。这意味着我们需要一个每次循环加 1 的整数计数器：

```text
construct Scanner and array.
initialize i to 0;
while (the Scanner.hasNextInt()) {
    store data[i] = scanner.nextInt();
    increment i;
}
```

这很容易翻译成实际代码：

```java
Scanner data = new Scanner(text);
int[] result = new int[7];
int i = 0;
while (data.hasNextInt()) {
    result[i] = data.nextInt();
}
```

我们将这些部分组合在一起，得到了下面的程序：

```java
// 简单读取并回显程序的第一个版本
import java.io.*;
import java.util.*;

public class Hours {
    public static void main(String[] args) throws FileNotFoundException {
        Scanner input = new Scanner(new File("hours.txt"));
        processFile(input);
    }

    public static void processFile(Scanner input) {
        while (input.hasNextLine()) {
            String text = input.nextLine();
            int[] next = transferFrom(text);
            System.out.println(Arrays.toString(next));
        }
    }

    public static int[] transferFrom(String text) {
        Scanner data = new Scanner(text);
        int[] result = new int[7];
        int i = 0;
        while (data.hasNextInt()) {
            result[i] = data.nextInt();
            i++;
        }
        return result;
    }
}
```

程序产生了以下输出：

```text
[8, 8, 8, 8, 0, 0, 0]
[8, 4, 4, 4, 0, 0, 0]
[8, 4, 4, 8, 0, 0, 0]
[3, 0, 0, 8, 6, 4, 8]
[0, 0, 8, 0, 0, 0, 0]
```

# 第 7 章 数组

注意，这些输出内容都不会包含在程序的最终版本中。程序员经常在开发过程中包含此类输出，以帮助对开发中的程序进行调试。

## 版本 2：累加和

我们在这个版本的程序中想要做的主要更改是引入第二个数组，用于跟踪列总和。这意味着我们将扩展 `processFile` 方法的代码，它目前的形式如下：

```java
while (input.hasNext()) {
    String text = input.nextLine();
    int[] next = transferFrom(text);
    System.out.println(Arrays.toString(next));
}
```

我们需要在循环之前构造总数组（`total`），并在循环结束后打印它。在循环内部，我们希望将下一行数据加到总和中。为了保持该方法的简洁，我们可以引入另一个方法来执行加法操作：

```java
int[] total = new int[7];
while (input.hasNext()) {
    String text = input.nextLine();
    int[] next = transferFrom(text);
    addToTo(total, next);
}
System.out.println(Arrays.toString(total));
```

这个版本在循环内部打印总和，因为我们已经验证了单行数据已被正确读取到数组中。

此时值得注意的是，我们在程序中已经两次使用了数字 7 来构造这两个数组。这两个数组的长度相同是至关重要的，因此定义一个可以使用的类常量是有意义的：

```java
public static final int DAYS = 7; // 每周的天数
```

我们也可以在各种循环中使用这个常量，而不是使用通常的数组长度。

为了完成第二个版本的编写，我们必须编写 `addTo` 方法。我们将得到两个数组，一个包含总小时数，另一个包含下周的小时数。让我们考虑在处理示例输入文件中间的情况。输入的前三行如下所示：

```text
8 6 8 8
8 4 8 4 4
8 4 8 4 4
```

假设我们已经正确处理了前两行，并且刚刚读取了第三行进行处理。我们的两个数组看起来如下：

## 7.5 案例研究：工作小时数

| total | 16 | 12 | 16 | 12 | 16 | 4 |
|---|---:|---:|---:|---:|---:|---:|
|  | 8 | 4 | 4 | 8 | 0 | 0 |

如果我们能直接这样做就好了：

```java
total += next; // 无法编译
```

遗憾的是，我们不能对数组使用像 `+` 或 `+=` 的操作。然而，这些操作可以在简单整数上执行，而这些数组是由简单整数组成的。因此，我们基本上必须告诉计算机对单个数组元素执行七次不同的 `+=` 操作。这可以通过 `for` 循环轻松编写：

```java
public static void addTo(int[] total, int[] next) {
    for (int i = 0; i < DAYS; i++) {
        total[i] += next[i];
    }
}
```

所以，我们的第二个版本最终看起来如下：

```java
1 // 计算列和的程序第二个版本。
2
3 import java.io.*;
4 import java.util.*;
5
6 public class Hours2 {
7    public static final int DAYS = 7; // 每周的天数
8
9    public static void main(String[] args) throws FileNotFoundException {
10        Scanner input = new Scanner(new File("hours.txt"));
11        processFile(input);
12    }
13
14    public static void processFile(Scanner input) {
15        int[] total = new int[DAYS];
16        while (input.hasNextLine()) {
17            String line = input.nextLine();
18            int[] next = transferFrom(line);
19            addTo(total, next);
20        }
21        System.out.println(Arrays.toString(total));
22    }
23}
24
public static int[] transferFrom(String text) {
25        Scanner data = new Scanner(text);
26        int[] result = new int[DAYS];
27        int i = 0;
28        while (data.hasNextInt()) {
29            result[i] = data.nextInt();
30            i++;
31        }
32        return result;
33}
34
35 public static void addToTo(int[] total, int[] next) {
36        for (int i = 0; i < DAYS; i++) {
37            total[i] += next[i];
38        }
39}
```

这个版本产生以下单行输出：

```text
[43, 32, 36, 40, 34, 8, 8]
```

你可以使用计算器来验证这些是否是正确的列总和。这意味着我们准备好进入版本 3 了。

## 版本 3：行和与列打印

程序的内核部分已经写好。它能正确地读取输入文件的每一行到数组中，并使用第二个数组来跟踪列总和。在这个最终版本中，我们只是在完成输出的一些细微细节。我们想对现有代码进行两处更改：我们想报告每行的总和，并想以易读的方式打印列总和。为了保持 `processFile` 方法的简洁，我们可以像下面这样完成这些更改。`processFile` 方法的主体看起来如下：

```java
int[] total = new int[DAYS];
while (input.hasNextLine()) {
    String line = input.nextLine();
    int[] next = transferFrom(line);
    addTo(total, next);
}
System.out.println(Arrays.toString(total));
```

我们需要在循环内部添加对 `sum` 方法的调用，以报告总和。这如下：

```java
int[] total = new int[DAYS];
while (input.hasNextLine()) {
    String line = input.nextLine();
    int[] next = transferFrom(line);
    System.out.println("Total hours = " + sum(next));
    addTo(total, next);
}
```

# 章节总结

```java
59 )
60 // prints information about the totals including total
61 // hours for each day of the week and total hours overall
62 void print(int[] total) {
63 String[] dayNames = {"Mon", "Tue", "Wed", "Thu",
64 "Fri", "Sat", "Sun"};
65 for (int i = 0; i < DAYS; i++) {
66 System.out.println(dayNames[i] + " hours = " +
67 + total[i]);
68 }
69
70 System.out.println("Total hours = " + sum(total));
71
72 )
```

它产生如下输出：

```text
Total hours = 40
Total hours = 40
Total hours = 32
Total hours = 25
Total hours = 16
Total hours = 16
Total hours = 32
```

```text
Mon hours = 43
Tue hours = 32
Wed hours = 36
Thu hours = 40
Fri hours = 34
Sat hours = 8
Sun hours = 8
Total hours = 201
```

# 章节总结

数组是一个将多个相同类型的值或对象分组合在一个名称下的对象。每个值（即元素）都通过一个从 0 到数组长度减 1 的整数索引来访问。

数组元素还可以使用一种名为 `for` 循环的类型循环按顺序访问。

数组具有若干局限性，例如固定大小以及缺乏对 `==` 和 `println` 等操作的支持。为了执行这些操作，必须编写 `for` 循环来处理数组的每个元素。

尝试访问小于 0 或大于或等于数组长度的数组元素将导致程序崩溃并抛出 `ArrayIndexOutOfBoundsException` 异常。

常见的数组算法，例如打印数组或比较两个数组是否相等，是通过遍历元素并检查或修改每个元素来实现的。

数组通常使用循环遍历。数组的长度通过访问其 `length` 字段找到，因此遍历数组的循环可以处理从索引开始的……

# 第 7 章 数组

对象数组是对象的引用数组。

新声明并初始化的对象数组实际上在所有索引元素中存储 `null`，因此每个元素必须单独初始化或在循环中初始化以存储对象。

多维数组是数组的数组。这些通常用于存储二维数据，例如行和列中的数据，或二维空间中的 x/y 数据。

# 自测练习题

## 第 7.1 节：数组基础

1. 应该使用什么表达式来访问名为 `numbers` 的整数数组的第一个元素？假设 `numbers` 包含 10 个元素，应该使用什么表达式访问它的最后一个元素？无论其长度如何，应该使用什么表达式访问其最后一个元素？

2. 编写代码，创建一个名为 `data5` 的整数数组，内容如下：

![](img/aea18896a4bced58de45f29f5a93f7b3_455_0.png)

3. 编写代码，使用循环在数组中存储 -6 到 38 之间的所有奇数。使数组的大小恰好足够存储这些数字。

   尝试将你的代码泛化，使其适用于任何最小值和最大值，而不仅仅是 -6 和 38。

4. 执行以下代码后，数组 `numbers` 包含哪些元素？

```java
int[] numbers = new int[8];
numbers[0] = 4;
numbers[4] = 99;
numbers[7] = 2;
```

```java
int x = numbers[7];
numbers[x] = 44;
numbers[numbers[7]] = 11; // 使用 numbers[7] 作为索引
```

5. 以下代码有什么什么错误？

```java
int[] first = new int[2];
first[0] = 3;
first[1] = 7;
int[] second = new int[2];
second[0] = 3;
second[1] = 7;
```

```java
// 打印数组元素
System.out.println(first);
System.out.println(second);
```

```java
// 检查元素是否相同
if (first[0] == second[0]) {
    System.out.println("它们包含相同的元素.");
} else {
    System.out.println("元素是不同的.");
}
```

## 自测练习题

6. 编写一段代码，声明一个名为 `data` 的数组，元素为 7, -1, 13, 24 和 6。仅使用一个语句初始化数组。

7. 描述如何修改本节中的 Tally 程序，以支持 100,000,000 到 100,000,004 之间的分数，而不是 0 到 4 之间。（提示：你的数组长度不应该是一亿元素！）

8. 编写一段代码，检查整数数组并返回数组中的最大值。考虑将你的代码写入名为 `max` 的方法，该方法接受数组作为参数并返回最大值。假设数组至少包含一个元素。

9. 编写代码计算整数数组所有元素的平均值（算术平均值）。例如，如果数组包含 `[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`，则平均值应该是 5.5。你可能希望将此代码放入一个接受数组并返回值的 `average` 方法中。

## 第 7.2 节：数组遍历

10. 什么是数组遍历？编写 `for` 循环代码来处理名为 `data` 的五个整数数组，结果如下：

```text
element[0] 是 14
element[1] 是 5
element[2] 是 7
element[3] 是 25
```

泛化你的代码以适用于任何大小。

12. 编写反向打印数组的代码。考虑将你的代码放入名为 `Backwards` 的方法中。

13. 描述如何修改本节开发的方法以处理字符串而不是整数。

14. 编写一个名为 `less` 的方法，接受两个数组，如果第一个数组的元素小于第二个数组的对应元素，则返回 `true`。

15. 为什么方法有效？

16. 编写一个名为 `swapPairs` 的方法，接受整数数组并交换相邻元素。如果数组长度为奇数，最后一个元素保持不变。例如，`[20, 10, 30, 40]` 变为 `[10, 20, 40, 30]`。

## 第 7.3 节：高级技巧

17. 执行以下代码后，数组元素的值是什么？

```java
int[] numbers = {10, 20, 30, 40, 50, 60, 70, 80, 90, 100};
for (int i = 0; i < 9; i++) {
    numbers[i] += 1;
}
```

18. 执行以下代码后，数组元素的值是什么？

```java
int[] numbers = {10, 20, 30, 40, 50, 60, 70, 80, 90, 100};
for (int i = 1; i < 10; i++) {
    numbers[i] = numbers[i - 1];
}
```

19. 考虑以下方法：



```java
public static void mystery(int[] a, int[] b) {
    for (int i = 0; i < a.length; i++) {
        a[i] += b[b.length - 1];
    }
}
```

执行代码后，数组 `a1` 的元素值是什么？

```java
int[] a1 = {1, 3, 5, 7};
int[] a2 = {1, 4, 9, 16, 25};
mystery(a1, a2);
```

20. 考虑以下方法：

```java
public static void mystery2(int[] a, int[] b) {
    for (int i = 0; i < a.length; i++) {
        a[i] = a2 * i % b.length;
    }
}
```

执行代码后，数组 `a1` 的元素值是什么？

```java
int[] a1 = {2, 4, 6, 8, 10, 12, 14, 16};
int[] a2 = {1, 1, 2, 3, 5, 8, 13, 21};
```

21. 考虑以下方法：

```java
public static void mystery3(int[] data, int x, int y) {
    data[data[x]] = data[y];
    data[y] = x;
}
```

（注：原文中 `data[data][x]]` 为笔误，根据上下文修正为 `data[data[x]]`。）

执行以下代码后，数组 `numbers` 的元素值是什么？

```java
int[] numbers = {3, 7, 1, 0, 25, 4, 18, -1, 5};
mystery3(numbers, 3, 1);
mystery3(numbers, 5, 6);
mystery3(numbers, 8, 4);
```

22. 编写一段代码，计算字符串数组的平均字符串长度。例如，如果数组包含 `"belt"`、`"hat"`、`"jelly"`、`"bubble gum"`，则平均长度为 5.5。

## 练习

23. 编写代码，创建一个字符串数组作为其参数，并判断该数组是否为回文——即正读和反读的内容都相同。例如，数组 `("alpha", "beta", "gamma", "delta", "gamma", "beta", "alpha")` 就是一个回文。

## 第 7.4 节：多维数组（可选）

24. 假设声明了一个名为 `data` 的二维矩形整数数组，具有四行两列。编写一个循环来初始化 `data` 的第三行，存储 1 到 7 的数字。

25. 编写一段代码，构建一个 5 行 10 列的二维整数数组。用乘法表填充该数组，使得 `element[i][j]` 包含值 `i * j`。使用嵌套循环来构建该数组。

26. 假设声明了一个名为 `matrix` 的二维矩形整数数组，具有六行八列。编写一个循环，将第二列的内容复制到第五列。

27. 编写一段代码，构建一个二维整数数组，其每行的列数递增，使得第一行有一列，第二行两列，第三行三列，以此类推。数组元素应按从上到下、从左到右的顺序（也称为行优先）值增大。换句话说，数组的内容应该是：

- 1
- 2, 3
- 4, 5, 6
- 7, 8, 9, 10
- 11, 12, 13, 14, 15

使用 `for` 循环构建该数组。

## 练习

1. 编写一个名为 `indexOf` 的方法，接受一个整数数组和一个整数值作为参数，并返回该值在数组中出现的最后一个索引。如果没有找到该值，应返回 -1。例如，在数组 `{74, 85, 12, 99, 101, 85, 56}` 中，值 85 的最后一个索引是 5。

2. 编写一个名为 `countRange` 的方法，接受一个整数数组、一个最小值和一个最大值作为参数，并返回数组中落在最小最大值之间（包含边界）的元素个数。例如，在数组 `{14, 1, 22, 17, 36, 7, -43, 5}` 中，有四个元素落在 4 到 17 之间。

3. 编写一个名为 `copyAll` 的方法，接受两个整数数组作为参数，并将第一个数组的元素复制到第二个数组中。例如，考虑以下代码：

```java
int[] array1 = {2, 1, 4, 3, 6};
int[] array2 = new int[6];
copyAll(array1, array2);
```

在执行你的 `copyAll` 方法后，`array2` 的内容应该是 `{2, 1, 4, 3, 6, 5}`，与 `array1` 类似。

你可以假设第二个数组的元素至少与第一个数组一样多。

此外尝试该方法的变体，它只接受一个数组作为参数并返回复制后的数组。在方法内部，创建一个第二个数字数组来存放副本并返回它。

## 第 7 章 数组

4. 一个名为 `copyrange` 的方法接受两个数组 `a1` 和 `a2`、起始索引 `i1` 和 `i2` 以及长度 `l`，将 `a1` 从索引 `i1` 开始的前 `l` 个元素复制到 `array2` 的索引 `i2` 处。假设参数值是有效的，空间足够容纳数据等。

5. 一个名为 `mode` 的方法返回整数数组中出现频率最高的元素。假设数组至少有一个元素，且数组中的每个元素值都在 0 到 100 之间。如果出现频率相同，则选择较小的值。例如，如果传递的数组值为 `{27, 15, 5, 11, 27}`，你的方法应该返回 15。（提示：你可能想查看 `Tally` 程序或本章内容来获得解决思路。）

你能写出一个不依赖于值必须为 0 和 100 的方法版本吗？

6. 一个名为 `std` 的方法返回整数数组的标准差。标准差的计算方法是：取每个元素与平均值之差的和，除以元素个数减一，然后开根。就是简单！更简洁且符合数学表达的方式，数组 `a` 的标准差写为：

![](img/aea18896a4bced58de45f29f5a93f7b3_459_0.png)

例如，如果传递的值为 `{1, -2, 4, -9, 6, -16, -8, 25, -10}`，你的方法应该返回近似 11.237。

7. 一个名为 `kthLargest` 的方法接受整数 `k` 和一个数组 `a` 作为参数，并返回有 `k` 个元素大于或等于它的元素。如果 `k = 0`，返回最大的元素、第二大的元素，以此此类推。例如，如果传递的值为 `{74, 85, 102, 99, 101, 56, 84}` 且 `k` 为 2，你的方法应该返回 99，因为有两个元素。假设 `k` 小于数组长度。

8. 一个名为 `median` 的方法接受一个整数数组作为参数并返回中位数。如果数组元素个数为奇数，返回中间元素；如果是偶数，返回两个中间元素的平均值。例如，如果数组是 `{1, 3, 5, 7, 9}`，中位数是 5。（提示：你可能需要先对数组排序。）

9. 重写上一个练习中的 `median` 方法，使其无论数组大小如何都能工作。

10. 一个名为 `wordLengths` 的方法接受一个字符串作为参数。你的方法应该将字符串拆分为单词，统计每个单词字母并输出结果。例如，如果字符串是 `"hello world"`，输出应该是：

```text
5

5
```

## 编程项目

假设没有名为 `matrixadd` 的方法可以将一对二维整数数组作为参数，将数组视为二维的并进行相加，返回矩阵 A 和 B 的和，结果为矩阵 C，其中对于第 $i$ 行第 $j$ 列，$C_{ij} = A_{ij} + B_{ij}$。你可以假设数组的维度相同。

11. 一个名为 `equals` 的方法接受两个二维整数数组，如果数组包含相同的元素且顺序相同，则返回 `true`。如果数组长度不同，应返回 `false`。

1. Java 的 `int` 类型对整数存储的大小有限制。这种限制可以通过将整数表示为数字数组来绕过。编写一个交互式程序计算两个 50 位的整数。

2. 使用数组编写猜单词游戏（Hangman）。允许用户猜字母，并用数组表示哪些字母已被猜。

3. 编写一个程序与用户玩数独大师（Mastermind）游戏的变体。例如，程序可以使用伪随机数生成一个四位数。允许用户一直猜直到得到正确数字。应给用户提供提示，指示猜测中有多少数字正确且位置正确，以及多少数字正确但位置错误。

4. 编写一个程序为用户评分迈尔斯人格测试。该测试有 70 个问题，决定人的四个维度人格。每个问题有两个答案，分别为 `"A"` 和 `"B"`。答案组织成 10 组每组 7 个问题，模式如下：

- 每组第一个问题（问题 1、8、15、22 等）告诉人是内向还是外向。
- 接下来两个问题（问题 2 和 3、9 和 10、16 和 17、23 和 24 等）测试人是受感官还是直觉引导。
- 接下来两个问题（问题 4 和 5、11 和 12、18 和 19、25 和 26 等）测试人是否关注情感。
- 每组最后两个问题（问题 6 和 7、13 和 14、20 和 21、27 和 28 等）测试人是倾向于判断还是受感知引导。

## 第 7 章 数组

换句话说，如果我们将内向/外向性（I/E）视为维度 1，感觉/直觉（S/N）视为维度 2，思维/情感（T/F）视为维度 3，以及判断/感知（J/P）视为维度 4，那么问题到其对应维度的映射关系如下：

```text
1223344122334122334122334122334122334122334122334122334122334122334
BAAAAAAAAAABAAAAAAABAAAAAAABAAAAAAABAAAAAAABABAABABABAAAAAAABAAAAAAABAAAAABAAAAAAA
```

以下是名称和响应的部分示例输入文件：

- Betty Boop: `BAAAAAAAAAAAABAAAAAAABAAAAAAABAAAAAAABABAABABABAAAAAAABAAAAAAA`
- Snoopy: `AABBABBBABABABAAAAAAABBBABBAABAAABBAABBAABABAABABABABAABABABBAABABBABBBABBB`

如果某人在特定人格维度上的 B 响应少于 50%，则她在该维度上的类型应为其选项中的第一个。如果某人的 B 响应达到 50% 或以上，则她在该维度上的类型为第二个选项。你的程序应该输出每个人的姓名、每个维度的 A 和 B 响应数量、每个维度中 B 的百分比以及整体人格类型。以下应该是你的程序针对上述输入数据的输出结果：

- Betty Boop：

  `1A-9B 17A-3B 18A-2B 18A-2B`

  `[90%, 15%, 10%, 10%] = ISTJ`

- Snoopy：

  `7A-3B 11A-9B 14A-6B 6A-14B`

  `[30%, 45%, 30%, 70%] = ESTP`

5. 编写一个井棋游戏，使用二维数组表示棋盘。

# 第 8 章 类

## 引言

现在你已经掌握了 Java 过程化编程的基础知识，终于准备好探索 Java 的设计初衷了：面向对象编程。本章将介绍讨论对象时使用的基本术语，并向你展示如何声明自己的类来创建对象。

你将看到，对象是包含状态和行为的实体，可以作为大型程序的一部分。我们将讨论抽象和封装的概念，这将允许你在不理解其内部细节的情况下在高级层上使用对象。我们还将讨论设计新对象类的想法以及实现利用这些对象的程序。

## 8.1 面向对象编程概念

- 类与对象

### 8.2 对象状态：字段

### 8.3 对象行为：方法

- 隐式参数
- 修改器与访问器

### 8.4 对象初始化：构造函数

### 8.5 封装

- 私有字段
- 类不变性

### 8.6 更多实例方法

- `toString` 方法
- `equals` 方法
- `instanceof` 关键字

### 8.7 关键字 `this`

- 多构造函数

### 8.8 更多类

- 参与者（Participant）
- 时间跨度（TimeSpan）
- 更改内部实现

### 8.9 案例研究：设计一个股票类

- 面向对象设计启发式
- 股票字段与方法头
- 股票方法与构造函数的实现

## 8.1 面向对象编程概念

到目前为止，我们的重点大部分都在过程化分解上，即将复杂任务分解为较小的子任务。这是最老的编程风格，即使在 Java 这样的语言中，我们仍然使用过程化技术。但 Java 还提供了一种不同的编程方法，我们称之为面向对象编程。

### 面向对象编程（OOP）

将程序视为一组对象而不是一组动作来对其推理。

面向对象编程涉及对编程的特定视角，它有自己的术语。让我们先通过非编程示例来探索这些术语。回想第 3 章中对象的定义。

### 对象

一种包含状态和行为的编程实体。

要真正理解这个定义，你必须理解“状态”和“行为”这两个词。这些是面向对象编程中最基础的概念。让我们考虑我们称为收音机的类。收音机可以处于哪些不同的状态？它可以开启或关闭。它可以调谐到许多不同电台之一，并设置不同的音量。任何给收音机都必须“知道”自己处于什么状态，这意味着它必须在内部跟踪这些信息。我们将此类内部值的集合称为对象的状态。

### 状态

存储在对象中的一组值（内部数据）。

收音机的行为是什么？最明显的一点是，当它开启并调大音量时它会产生声音。但它还有其他涉及操作其内部状态的行为。我们可以开启或关闭收音机，改变电台或音量。我们还可以检查收音机现在设置在哪个电台。我们将这些操作的集合称为对象的行为。

### 行为

对象可以执行的一系列动作，通常会报告或修改其内部状态。

对象本身并不是完整的程序；它们是被赋予了不同角色和责任的组件。对象可以作为大型程序的一部分来解决问题。创建和使用对象的代码被称为客户端。

## 8.2 对象状态：字段

在这些章节中，我们将看到的类的主要组成部分有：

- 字段（存储在每个对象中的数据）
- 方法（每个对象可以执行的行为）
- 构造方法（用于使用 `new` 关键字构造对象的特殊方法）
- 封装（保护对象数据免受外部访问的干扰）

我们将通过创建 `Point` 类的四个主要版本来关注这些概念。第一个版本将为我们提供仅包含数据的 `Point` 对象。第二个版本将为对象添加行为。第三个版本将允许我们在任何初始位置构造 `Point`。第四个版本将封装每个 `Point` 的内部数据，防止意外的外部访问。只有 `Point` 类的第四个版本将按照正确的面向对象风格编写；其他版本将是不完整的，用于孤立地说明类的每个特性。

## 8.2 对象状态：字段

我们的 `Point` 类版本将仅包含状态。为了指定每个对象的状态，我们在类内部声明了称为字段（fields）的特殊变量。“字段”有许多同义词，源自其他编程语言和环境，例如“实例变量”（instance variable）、“数据成员”（data member）和“属性”（attribute）。

### 字段

对象内部的一个变量，构成其内部状态的一部分。

声明字段的语法与声明普通变量相同：一个类型后跟一个名称和一个分号。字段与变量的区别在于，它们是直接声明在类的 `(` 和 `)` 内部的。当我们声明一个字段时，我们是在说希望该类的每个对象内部都拥有该内容。

在之前的章节中，我们已经看到每个类都应该放在自己的文件中。我们 `Point` 类的第一个版本写在 `Point.java` 文件中，定义了字段。每个 `Point` 对象将包含两个字段（一个名为 `x` 的整数和一个名为 `y` 的整数）：

```java
// 一个 Point 对象表示了一对 (x, y) 坐标。
// 第一版本：仅包含状态。

public class Point {
    int x;
    int y;
}
```

尽管字段的语法让它们看起来像局部变量，但它们具有不同的属性。前面的代码并没有声明一对 `int` 变量 `x` 和 `y`。相反，它表示每个 `Point` 对象将包含它自己的名为 `x` 和 `y` 的字段。例如，如果我们创建了 100 个 `Point` 对象，我们在类的每个实例中将拥有 100 对 `x` 和 `y` 字段。

`Point` 类本身并不是一个可执行的 Java 程序；它只是定义了一个供客户端程序使用的新类。使用 `Point` 的客户端代码将是另一个类，我们将其存储在单独的文件中。客户端程序可以使用 `new` 关键字和空括号来创建 `Point` 对象，如下：

```java
Point origin = new Point();
```

当一个 `Point` 对象被构造时，它的字段会被赋予默认值 0，因此一个新的 `Point` 对象始终从原点 `(0,0)` 开始，除非它改变了 `x` 或 `y` 值。这是自动初始化的另一个例子，类似于数组元素被自动赋予默认值的方式。

以下是使用我们 `Point` 类客户端程序的第一个版本。代码保存在 `PointMain.java` 文件中，它应该与 `Point.java` 位于同一个文件夹或项目中，以便程序能够成功编译。



```java
// 一个处理 20 个点的程序
// 第一版本，用于配合仅包含状态的 Point 类
public class PointMain {
    public static void main(String[] args) {
        // 创建两个 Point 对象
        Point p1 = new Point();
        p1.x = 7;
        p1.y = 2;

        Point p2 = new Point();
        p2.x = 4;
        p2.y = 3;

        // 打印每个点及其到原点的距离
        System.out.println("p1 is (" + p1.x + ", " + p1.y + ")");
        double dist1 = Math.sqrt(p1.x * p1.x + p1.y * p1.y);
        System.out.println("distance from origin = " + dist1);

        System.out.println("p2 is (" + p2.x + ", " + p2.y + ")");
        double dist2 = Math.sqrt(p2.x * p2.x + p2.y * p2.y);
        System.out.println("distance from origin = " + dist2);
        System.out.println();

        // 将每个点移动到新位置
        p1.x += 11;
        p1.y += 6;
        p2.x += 1;
        p2.y += 7;

        // 再次打印点
        System.out.println("p1 is (" + p1.x + ", " + p1.y + ")");
        System.out.println("p2 is (" + p2.x + ", " + p2.y + ")");
    }
}
```

该代码产生了以下输出：

```text
p1 is (7, 2)
distance from origin = 7.2810988928051
p2 is (4, 3)
distance from origin = 5.0

p1 is (18, 8)
p2 is (5, 10)
```

客户端程序包含一些冗余，我们在接下来的章节中改进`Point`类时将消除它们。

我们最初的`Point`类本质上是作为两个`int`值组合到一个对象中的方法。这对于客户端程序来说有点用，但客户端可以使用原始类型来编写。我们的`Point`类没有行为，这有时被称为结构体（struct）。在接下来的章节中，我们将把`Point`类扩展为正规的。

## 8.3 对象行为：方法

我们的`Point`类第二个版本将包含状态和行为。`Point`类的第二个版本将包含状态。通过编写实例方法来描述对象的行为。

> **实例方法（Instance Method）**
>
> 对象内部的一个操作对象的方法。

在之前的章节中，我们知道实例方法是响应对象的响应。`Point`类的第二个版本将包含状态和行为。客户端方法通过手动调整来移动对象的`x`和`y`值：

```java
p1.x += 11;
p1.y += 6;
```

由于移动点是一个常见的操作，我们应该将其表示为方法。一个静态方法接受`Point`、`int dx`和`int dy`。它的代码看起来如下：

```java
// 在这种情况下静态方法不是一个好的选择
public static void translate(Point p, int dx, int dy) {
    p.x += dx;
    p.y += dy;
}
```

调用该静态方法看起来如下：

```java
translate(p1, 11, 6); // 调用静态方法
```

然而，静态方法并不是实现行为的最佳方式。使用对象编程最大的用处之一是将相关数据和行为放在一起。`Point`移动的能力与其`(x, y)`数据密切相关，因此最好在`Point`类中编写实例方法。

根据对对象的经验，我们可以使用“点符号”来调用实例方法：

```java
p1.translate(1, 6); // 调用实例方法
```

注意实例方法需要两个参数：`dx`和`dy`。客户端没有传递`Point`作为参数，因为调用开始时指示要移动哪个对象`p1`。通过这种方式，客户端正在向`p1`指向的对象发送移动消息。

实例方法头部没有静态方法头部中的`static`关键字，但它们包含了`public`关键字、方法的返回类型、名称以及方法接受的任何参数。这里是带有`translate`方法头部但未写体的`Point`类开头：

```java
public class Point {
    int x;
    int y;

    public void translate(int dx, int dy) {

    }
}
```

记住当我们在`Point`类中声明`translate`方法时，我们是在说每个`Point`对象都有该方法的拷贝。每个`Point`对象还拥有自己的`x`和`y`值。一个`Point`对象看起来如下：

```java
public void translate(int dx, int dy)
```

每当实例方法被调用时，都是在一个特定的对象上调用的。因此，当我们编写`translate`方法体时，我们将从接收消息的特定对象的角度考虑该代码：“客户端给了我`dx`和`dy`，并希望通过这些值改变我的`x`和`y`值。”本质上，我们需要编写匹配以下伪代码：

```text
向此对象的 x 值增加 dx;
向此对象的 y 值增加 dy;
```

## 对象字段与实例方法

此时需要了解的一点是，对象的实例方法可以引用它的字段（fields）。在之前的章节中，我们讨论过作用域（scope），即变量可见和使用的范围。变量的作用域是声明它的大括号集合。同样的规则也适用于字段：由于它们是在类内部声明的，因此它们的作用域是整个类。

这意味着`translate`方法可以直接引用字段`x`和`y`。例如，语句`x += 3;`将将`Point`对象的`x`增加3。

这里有一个调整`Point`对象位置的有效方法：

```java
public void translate(int dx, int dy) {
    x += dx;
    y += dy;
}
```

`translate`方法可以直接引用`x`和`y`而不需要更具体的说明它影响的是哪个对象，这看起来可能很奇怪。用一个非编程的类比，如果你正在开车并想让司机向左转，你会说：“左转”。虽然世界上有数百万辆汽车，但你并不需要指明你指的是哪辆车。这隐含了你指的是你正乘坐的这辆车。同样，在实例方法中，我们不需要指定正在使用哪个对象的`x`或`y`；因为这隐含了我们想要使用接收消息对象的字段。

这里是包含`translate`方法的完整`Point`类。Sun 的 Java 风格指南建议在类顶部声明字段，方法放在下方，但通常情况下，类的内容以任何顺序出现都是合法的。

```java
public class Point {
    int x;
    int y;

    // 按给定的量移动此点的位置
    public void translate(int dx, int dy) {
        x += dx;
        y += dy;
    }
}
```

实例方法的通用语法如下：

```java
public <type> <name>(<type> <name>, ..., <type> <name>) {
    <statement>;
    <statement>;
    ..
    <statement>;
}
```

像`translate`这样的方法是有用的，因为它们为我们的对象提供了有行为，让我们能够编写更有力、更简洁的客户端程序。手动调整`Point`对象的`x`和`y`值来移动它们是非常繁琐的，特别是在经常平移的大型客户端程序中。通过添加`translate`方法，我们提供了一种通过单一语句调整`Point`对象位置的简洁方法。

## 第 8 章 类

### 隐式参数

我们刚刚提到过，对象的方法可以引用它的字段。从代码的角度来看，这意味着实例方法的代码对它正在操作的对象有一个隐含的认知。这种认知有时被称为**隐式参数**（implicit parameter）。

> **隐式参数**
>
> 在实例方法执行期间被引用的对象。

让我们通过一个示例来具体演示实例方法是如何使用隐式参数的。首先，我们将编写一些客户端代码来构造两个`Point`对象并为它们设置初始位置：

```java
// 构建两个 Point 对象
Point p1 = new Point();
p1.x = 7;
p1.y = 2;
Point p2 = new Point();
p2.x = 4;
p2.y = 3;
```

在执行上述代码后，内存中变量和对象的图示如下。请记住，每个对象都有它们自己的`translate`方法副本：

![](img/aea18896a4bced58de45f29f5a93f7b3_471_0.png)

![](img/aea18896a4bced58de45f29f5a93f7b3_471_1.png)

现在我们将在每个对象上调用`translate`方法。首先平移`p1`。在这次调用期间，`p1`的`translate`方法接收了参数11和6。这里的隐式参数是`p1`对象，因此语句`x += dx`和`y += dy;`影响了`p1.x`和`p1.y`：

```java
p1.translate(11, 6);
```

![](img/aea18896a4bced58de45f29f5a93f7b3_472_0.png)

在第二次调用期间，执行了`p2`的`translate`方法，因此`translate`方法体中的代码行改变了`p2.x`和`p2.y`：

```java
p2.translate(1, 7);
```

![](img/aea18896a4bced58de45f29f5a93f7b3_472_1.png)

## 变异器和访问器

`translate`方法是变异器（mutator）的一个示例。

> **变异器（Mutator）**
>
> 一种修改对象内部状态的实例方法。

通常，变异器为对象的一个字段分配一个新值。回到例子，变异器就像打开关闭收音机、切换电台或调节音量的开关和旋钮。

变异器的名称以`set`开头是一个常见的惯例，例如`setID`或`setLevel`。通常变异器方法的返回类型为`void`。变异器通常接受参数，用于指定对象的新状态或修改其当前状态的增量。

实例方法的第二个重要类别被称为**访问器**（accessors）。

> **访问器（Accessor）**
>
> 一种提供对象信息但不对其进行修改的实例方法。

通常，访问器返回对象的某一个字段的值。例如，许多访问器的名称以`get`或`is`开头。注意访问器不会改变对象的状态。典型的访问器将具有非`void`返回类型。

`translate`方法是变异器的一个示例。变异器就像打开关闭收音机、切换电台或调节音量的开关和旋钮。

`translate`方法是变异器的一个示例。`translate`方法是变异器的一个示例。`translate`方法使用`x`和`y`的平方计算到原点的距离。

```java
// 返回到原点的距离
public double distanceFromOrigin() {
    return Math.sqrt(x * x + y * y);
}
```

生成的程序与之前相同但更短：

## 8.4 对象初始化：构造函数

一个处理 2D 点的程序。第二个版本，为类添加行为。

```java
// 创建 Point 对象
Point p1 = new Point();
p1.x = 7;
p1.y = 2;

Point p2 = new Point();
p2.x = 4;
p2.y = 3;

// 打印每个点及其到原点的距离
System.out.println("p1 is (" + p1.x + ", " + p1.y + ")");
System.out.println("distance from origin = " + p1.distanceFromOrigin());

System.out.println("p2 is (" + p2.x + ", " + p2.y + ")");
System.out.println("distance from origin = " + p2.distanceFromOrigin());

// 平移每个点到一个新位置
p1.translate(1, 6);
p2.translate(1, 7);

// 再次打印点
System.out.println("p1 is (" + p1.x + ", " + p1.y + ")");
System.out.println("p2 is (" + p2.x + ", " + p2.y + ")");
```

我们的`Point`类第三版本将包含在任何位置创建`Point`对象的能力。对象的初始状态通过编写称为**构造函数**的特殊方法来指定。

> **构造函数（Constructor）**
>
> 一种在创建新对象时初始化其状态的特殊方法。

现有客户端代码的一个拙劣方面是，需要三行代码来创建并初始化一个`Point`对象的状态：

```java
// 客户端需要三条语句来初始化一个 Point 对象
Point p1 = new Point();
p1.x = 7;
p1.y = 2;
```

记得在第3章中，我们能够通过一条语句创建具有初始位置的 Java Point 对象。我们是在构造对象时在括号中写入它们的初始`(x, y)`值来实现这一点的。

## 第 8 章 类

```java
Point p = new Point(10, 27); // 在 Java 的 Point 类中是合法的
```

这样的语句对于我们的`Point`类来说应该是合法的，尽管我们还没有编写任何代码来指定如何创建一个具有初始`(x, y)`位置的`Point`。我们可以通过在`Point`类中编写一个构造函数来指定这一点。构造函数是客户端使用`new`关键字创建新对象时执行的代码段。

构造函数的头部以关键字开头，后面跟着类名和任何参数。它看起来像一个方法的头部，但它的名称必须与类名匹配，且不能有返回类型。构造函数通常带有参数，用于指定对象的初始状态。我们`Point`类的构造函数将接受初始 x 和 y 值作为参数，并将它们存储到`Point`对象的 x 和 y 中：

```java
// 根据指定的 (x, y) 位置构造新点
public Point(int initialX, int initialY) {
    x = initialX;
    y = initialY;
}
```

就像实例方法一样，构造函数在特定的对象（使用`new`关键字创建的那个）上执行，并可以直接引用该对象的字段和方法。在这种情况下，我们将`initialX`和`initialY`参数值存储到新对象的`x`和`y`字段中。

既然我们正在探索构造函数，那么详细地思考创建对象的过程是有意义的。以下语句实际上执行了多个操作：

```java
Point p = new Point(1, 2);
```

它创建了一个名为`p`的`Point`引用，创建了一个新的`Point`对象，并在新创建的对象上调用`Point`构造函数，将1和2作为初始Y参数值传递。最后，它将新创建的对象赋值并存储在变量`p`中。

这是我们`Point`类第三版本的代码：

```java
// Point 对象表示一对 (x, y) 坐标。
// 第三个版本：带有构造函数的状态和行为
public class Point {
    int x;
    int y;

    // 根据指定的 (x, y) 位置构造新点
    public Point(int initialX, int initialY) {
        x = initialX;
        y = initialY;
    }

    // 返回此点与 (0, 0) 之间的距离
    public double distanceFromOrigin() {
        return Math.sqrt(x * x + y * y);
    }
```

## 8.4 对象初始化：构造函数

```java
// 按给定量移动此点的位置
public void translate(int dx, int dy) {
    x += dx;
    y += dy;
}
```

调用带有参数的构造函数类似于从工厂订购汽车：“我想要那辆带电动窗户和 CD 播放器的黄色车。”你可能不会指定汽车的每一个细节，例如它应该有四个轮子和大灯，但你确实指定了一些对你很重要的初始属性。构造函数的通用语法如下：

```java
public <type> <name>, ..., <type> <name> {
    <statement>;
    <statement>;
    ...
    <statement>
}
```

在添加构造函数后，我们的客户端代码变得更短、更简单，因为我们在一行中创建了它的`(x, y)`坐标：



```java
// 1 一个处理 2D 点的程序。
// 2 第三个版本，配合带有构造函数的 Point 类。

public class Main {
    public static void main(String[] args) {
        // 7 创建两个 Point 对象
        Point p1 = new Point(7, 2); // 调用构造函数
        Point p2 = new Point(4, 3); // 调用构造函数

        // 11 打印每个点及其它到原点的距离
        System.out.println("p1 is (" + p1.x + ", " + p1.y + ")\n");
        System.out.println("distance from origin = " + p1.distanceFromOrigin());

        System.out.println("p2 is (" + p2.x + ", " + p2.y + ")");
        System.out.println("distance from origin = " + p2.distanceFromOrigin());

        // 21 将每个点移动到新位置
        p1.translate(1, 6);
        p2.translate(1, 7);

        // 25 再次打印点
        System.out.println("p1 is (" + p1.x + ", " + p1.y + ")");
        System.out.println("p2 is (" + p2.x + ", " + p2.y + ")");
    }
}
```

当一个类没有构造函数时（如我们之前的`Point`类版本），Java 会自动提供一个没有参数的默认构造函数。

## 第8章 类

### 常见编程错误：在构造函数中使用`void`

许多程序员无意中在构造函数的头部中包含了`void`关键字，因为他们已经习惯了为每个方法编写返回类型：

```java
// 这段代码有一个 bug
public void Point(int initialX, int initialY) {
    x = initialX;
    y = initialY;
}
```

这实际上是一个非常棘手且恼人的 bug。构造函数不应该返回类型。当你写一个像`void`这样的返回类型时，你创建的不是构造函数，而是一个普通方法。这个错误很难发现，因为`Point.java`文件仍然可以编译。

当客户端尝试构造`Point`时，你会看到一个错误：

```text
Point.java:7: cannot find symbol
symbol: constructor Point(int,int)
Point p = new Point(7, 2);
```

这就是为什么之前构造`Point()`是合法的。默认构造函数会将所有字段初始化为零。然而，现在`new Point();`将无法编译。

在本章的后半部分，我们将编写额外的代码来恢复这种能力。

### 8.5 封装

### 常见编程错误：在构造函数中重新声明字段

构造函数的另一个常见 bug 是错误地通过编写类型来重新声明字段。这里有一个示例显示了：

```java
// 这个构造函数有一个 bug
public Point(int initialX, int initialY) {
    int x = initialX;
    int y = initialY;
}
```

上述代码的行为很奇怪。它可以成功编译，但当客户端构造`Point`对象时，无论传递给构造函数的参数值是什么，其初始坐标始终是 (0, 0)：

```java
// 这代码将打印 pl is (0, 0)
Point p = new Point(7, 2);
System.out.println("pl is (" + p.x + ", " + p.y + ")");
```

问题在于，我们没有将`initialX`和`initialY`存储在`Point`对象的`x`和`y`字段中，而是在`Point`构造函数内部声明了局部变量`x`和`y`。我们将`initialX`和`initialY`存储在这些局部变量中，这些变量在构造函数执行结束时会被丢。没有为`x`和`y`字段赋值，因此它们被初始化为 0。

如果你观察到构造函数似乎没有设置对象的字段，请仔细检查以确保你没有意外声明遮蔽字段的局部变量。关键是在给字段赋值时，不要在语句开头包含类型类型。

> **封装**
>
> 向对象的客户端隐藏对象的实现细节。

为了理解封装的概念，回顾非编程中收音机作为对象的类比。几乎每个人都知道如何使用收音机，但很少有人知道制造收音机或收音机内部的电路是如何工作的。收音机设计的益处在于我们不需要知道这些细节。

## 第8章 类

收音机的内部和外部视图。

![](img/aea18896a4bced58de45f29f5a93f7b3_479_0.png)

我们都理解收音机的基本属性（它的功能），但只有少数人理解收音机的内部细节（它是如何工作的）。这引出了对象外部视图与内部视图之间的一个重要二分法。从外部看，我们只看到这种行为。从内部看，我们看到为了实现该行为的内部状态（图 8.1）。

关注收音机的外部行为使我们能够轻松使用它，而忽略那些对我们并不重要的内部工作细节。这是计算机科学中一个重要概念，被称为**抽象**（abstraction）。

## 抽象

关注基本属性而非内部细节。

事实上，收音机（像大多数其他电子设备一样）有一个外壳或机箱，容纳了所有的电子元件，使我们从外面看不到它们。一组旋钮、按钮和显示器允许我们操作收音机，而无需处理使其使其运行的所有电路。事实上，你并不希望有人给你一个电线和电容器乱飞的全功能收音机，因为那会让收音机的界面变得极不易用。

当应用于编程时，从外部视图隐藏状态的概念被称为**封装**（encapsulation）。当一个对象被正确封装时，它的客户端无法直接访问或修改其内部工作，也无需这样做。只有类的实现者需要知道这些细节。封装提供比数据可以被直接访问的类更纯粹的抽象。

在之前的章节中，你已经利用了良好封装的对象所提供的抽象。例如，你使用过`Scanner`对象从控制台读取数据，而无需确切`Scanner`如何存储和分词输入数据；你使用过`Random`对象创建随机数，而无需确切随机数生成器使用什么算法。

但到目前，我们的`Point`类还没有被封装。我们构建了一个可以工作的收音机，但它的电线（`x`和`y`）仍然露在外。通过封装，我们将为`Point`对象加上一个外壳，这样客户端只需要使用对象的方法，而不是直接访问字段。

### 8.5 封装：私有字段

为了封装对象的字段，我们在每个字段声明的开头编写关键字`private`将其声明为私有。因此，我们`Point`类的字段声明如下：

```java
// Point 对象的封装字段
private int x;
private int y;
```

我们还没有展示字段的语法，因为我们想展示将字段设为私有的首选风格。声明封装字段的语法如下：

```java
private <type> <name>;
```

字段也可以带有初始值进行声明：

```java
private <type> <name> = <value>;
```

将字段声明为私有封装了对象的状态，就像收音机的外壳保护用户免受内部电线和电路的伤害一样。私有字段对`Point`类内部的所有代码（即`Point.java`文件内部）可见，但在其他任何地方都不可见。这意味着我们不能再在客户端代码中直接引用`Point`对象的`x`或`y`字段。以下客户端代码将无法成功编译：

```java
// 此客户端代码不适用于封装后的 Point 类
System.out.println("pl is (" + pl.x + ", " + pl.y + ")");
```

编译器会产生如下错误信息：

```text
PointMain.java:11: x has private access in Point
PointMain.java:11: y has private access in Point
```

为了保留客户端程序的功能，我们需要为客户端代码提供一种访问`Point`对象字段值的方法。我们将通过向`Point`类添加一些新的访问器方法（accessor methods）来实现。如果对象的字段值可能完全有用，通常会写一个返回该值的访问器。以下是提供访问`Point`对象`x`和`y`字段的方法：

```java
// 返回此点的 x 坐标
public int getX() {
    return x;
}
```

```java
// 返回此点的 y 坐标
public int getY() {
    return y;
}
```

打印`Point`对象`x`和`y`值的客户端代码必须更改为：

```java
// 此代码适用于我们封装后的 Point 类
System.out.println("pl " + pl.getX() + ", " + pl.getY() + "");
```

当我们说目标是封装这些字段时，这似乎似乎授予了对`Point`对象`x`和`y`字段的权限，但拥有像`getX`和`getY`这样的访问器实际上并没有违反对象的封装。访问器方法将字段值的副本返回给客户端，因此客户端可以查看`x`或`y`值，但没有方法更改它们。换句话说，这些访问器方法赋予了客户端对对象状态的只读访问。

封装我们的`Point`对象的另一个好处是，我们可以稍后更改`Point`类的内部结构，而无需修改客户端代码。例如，使用`r`和角度`theta`用极坐标来表示 2D 点是有用的。在这种表示法中，点的`(x, y)`坐标不是直接存储的，而是可以计算为`(r cos, r sin)`。由于类已经了封装，我们可以修改`getX`和`getY`方法，在内部使用`r`和`theta`。

封装`Point`类的一个缺点是客户端代码不再易于设置`x`和`y`值。为了方便，我们添加一个名为`setLocation`的新变器方法来同时设置`x`和`y`：

```java
// 设置 x 和 y 为给定值
public void setLocation(int newX, int newY) {
    x = newX;
    y = newY;
}
```

注意`Point`类现在在构造函数和`setLocation`之间存在冗余。两者的体体上都是设置`x`和`y`坐标。我们可以通过让构造函数调用`setLocation`来消除这种冗余：

```java
// 使用指定的 x 和 y 构建新点
public Point(int initialX, int initialY) {
    setLocation(initialX, initialY);
}
```

我们可以通过这种技术消除更多的冗余。翻译`Point`是在其位置加上`dx`和`dy`，因此我们可以修改`translate`方法来调用`setLocation`：

```java
// 按给定量移动此点
public void translate(int dx, int dy) {
    setLocation(x + dx, y + dy);
}
```

现在让我们来看一个整个类的正确语法模板。Sun 的 Java 风格指南建议将字段放在类的顶部，然后是构造函数，最后是方法：

```java
public class <name> {
    // 字段
    private <type> <name>;
    private <type> <name>;
    ..

    // 构造函数
    public <name>(<type> <name>, ..., <type> <name>) {
        <statement>;
        <statement>;
        ..
        <statement>;
    }

    // 方法
    public <type> <name>(<type> <name>, ..., <type> <name>) {
        <statement>;
        <statement>;
        ..
        <statement>;
    }
}
```

## 类不变性

封装对象的另一个好处是你可以对它们的状态放置约束。例如，假设我们想确保每个`Point`对象的`x`和`y`值均为非负。如果`Point`对象用于表示屏幕坐标（屏幕坐标从为负），这可能是非常有用的。适用于类的每个对象的属性被称为类不变性（class invariant）。

> **类不变性**
>
> 在对象的生命周期内有效的状态断言。

类不变性与第 4 章和第 5 章介绍的前提、后条件和断言有关。类不变性应该被视为类每个实例方法的隐含前提条件。类不变性还可能为构造函数和变器方法增加前提条件。

为了强制我们的类不变性，我们必须确保客户端不能创建具有负`x`或`y`值的`Point`对象。我们还必须确保客户端代码不会将`Point`移动到负`x`或`y`值，并在每次调用构造函数、`translate`方法或设置方法时都进行检查。

由于我们通过让构造函数和`translate`方法调用`setLocation`消除了冗余，我们实际上可以在单个`setLocation`方法中强制执行。

## 第 8 章 类

如果新的`x`或`y`值为负数，我们将抛出一个`IllegalArgumentException`来通知客户端错误：

```java
// sets point's (x, y) location to the given values
// pre: newX >= 0 && newY >= 0
public void setLocation(int newX, int newY) {
    if (newX < 0 || newY < 0) {
        throw new IllegalArgumentException();
    }

    x = newX;
    y = newY;
}
```

如果`Point`类没有被封装，我们就无法正确执行我们的类不变式。客户端代码可以通过直接设置`x`或`y`字段将`Point`对象的位置设置为负数。例如，这段恶意代码将成功地将`Point`对象的`x`值设置为 -1：

```java
// if our Point objects were not encapsulated,
// this client would violate the class invariant
Point pl = new Point(7, 2);
pl.x = -1;
System.out.println("Haha, I set its x value to " + pl.x);
```

通过封装，`Point`类对客户端如何使用`Point`对象有了更好的控制，使得误入的客户端无法违反我们的类不变式。我们现在可以确定，`Point`对象永远不会处于损坏状态。

这是我们`Point`类的第四个（完整）版本，包含了封装和我们的类不变式。由于所有设置`Point`对象位置的代码都调用了`setLocation`方法，我们只需要检查`x`和`y`值是否小于 0 即可：

```java
// A Point object represents a pair of (x, y) coordinates.
// Fourth version: encapsulated.
// Class invariant: x >= 0 && y >= 0.
public class Point {
    private int x;
    private int y;

    // constructs a new point with the given (x, y) location
    // pre: initialX >= 0 && initialY >= 0
    public Point(int initialX, int initialY) {
        x = initialX;
        y = initialY;
    }

    // returns the distance between this point and (0, 0)
    public double distanceFromOrigin() {
        return Math.sqrt(x * x + y * y);
    }

    // returns the x-coordinate of this point
    public int getX() {
        return x;
    }
}
```

### 8.5 封装

```java
// returns the y-coordinate of this point
public int getY() {
    return y;
}
```

```java
// sets this point's (x, y) location to the given values
// pre: newX >= 0 && newY >= 0
public void setState(int newX, int newY) {
    if (newX < 0 || newY < 0) {
        throw new IllegalArgumentException();
    }
    x = newX;
    y = newY;
}
```



```java
// shifts this point's location by the given amount
// pre: x + dx >= 0 && y + dy >= 0
public void translate(int dx, int dy) {
    setLocation(x + dx, y + dy);
}
```

这是我们客户端程序对应的版本：

```java
// A program that deals with 2D points.
// Fourth version, to accompany encapsulated Point class.
public class PointMain {
    public static void main(String[] args) {
        Point p1 = new Point(7, 2);
        Point p2 = new Point(4, 3);

        // print each point and its distance from the origin
        System.out.println("p1 is (" + p1.getX() + ", " + p1.getY() + ")");
        System.out.println("distance from origin = " + p1.distanceFromOrigin());

        System.out.println("p2 is (" + p2.getX() + ", " + p2.getY() + ")");
        System.out.println("distance from origin = " + p2.distanceFromOrigin());

        // translate each point to a new location
        p1.translate(1, 6);
        p2.translate(1, 7);

        // print the points again
        System.out.println("p1 is (" + p1.getX() + ", " + p1.getY() + ")");
        System.out.println("p2 is (" + p2.getX() + ", " + p2.getY() + ")");
    }
}
```

客户端现在实际上变得有些冗长了，因为它必须调用`Point`的`getX()`和`getY()`方法来打印其坐标。然而，客户端代码的这种适度不便是必要的，以保持我们`Point`对象的封装性和类不变式。

# 第 8 章 类

## 8.6 更多实例方法

在本节中，我们将为`Point`类添加一些特殊的实例方法，以便在客户端代码中使用更加简单、更方便。我们将编写一个方法来方便地打印`Point`对象，另一个方法来比较它们之间的相等性。

### `toString()`方法

Java 的设计者认为，所有类型的值与`String`操作是非常重要的。你已经看到可以将`String`与任何其他类型的值连接，例如基本类型`int`或对象。考虑以下代码：

```java
int i = 42;
String s = "hello";
Point p = new Point(7, 2);
```

### 编程错误：`toString()`方法中的`println`语句

由于`toString()`方法与打印密切相关，一些学生错误地认为可以在`toString()`方法中放置`println`语句，如下：

```java
// 这个 toString 方法是有缺陷的；
// 它应该返回字符串而不是打印它
public String toString() {
    System.out.println("" + x + ", " + y + "");
    return "";
}
```

理解`toString()`的关键点是，它并不直接打印任何内容；它返回一个字符串，客户端可以在`println`语句中使用。

事实上，许多良好的对象类完全不包含任何`println`语句。在类中包含`println`语句会将类与特定的输出风格绑定。例如，上面的代码将`Point`对象单独打印在一行，这使得该类不适用于不希望输出完全以这种方式显示的客户端（例如，一个希望在同一行打印多个`Point`对象的客户端）。

你可能会疑惑为什么 Java 的设计者选择使用`toString()`方法，而不是将对象输出到控制台的`print`方法。原因是`toString()`更通用。你可以使用`toString()`将对象输出到文件、显示在图形用户界面上，甚至通过网络发送文本。

无论两个不同的对象是否具有相同的状态，变量引用的都是同一个对象。考虑以下变量声明：

```java
Point p1 = new Point(7, 2);
Point p2 = new Point(7, 2);
Point p3 = p2;
```

下面的图表示了这些对象的状态以及引用它们的变量。注意，`p3`并不是对第三个对象的引用，而是对`p2`所引用对象的第二次引用。这意味着调用`translate()`方法也将反映在`p3`中：

![](img/aea18896a4bced58de45f29f5a93f7b3_488_0.png)

对于前面的`Point`对象，表达式`p1 == p2`的求值结果为`false`，因为`p1`和`p2`没有引用同一个对象。`p1`引用的对象与`p2`具有相同的状态，但它们具有不同的身份（identity）。然而，表达式`p2 == p3`的求值结果为`true`，因为`p2`和`p3`的是同一个对象。

在比较两个对象时，我们想知道对象是否具有相同的状态。为了执行这种比较，我们使用一个名为`equals()`的特殊方法。每个 Java 对象都包含一个实例方法，用它将自己与其他对象进行比较。上一节提到，没有方法的类会接收一个默认版本，该版本使用最保守的相等定义，如果两个对象具有相同的身份则认为它们相等。如果你想要不同于此的行为，你必须编写自己的`equals()`方法来替换默认行为。

适当的`equals()`方法会对两个对象的状态进行比较，如果状态相同则返回`true`。对于前面的`Point`对象，我们希望表达式`p1.equals(p2)`、`p1.equals(p3)`和`p2.equals(p3)`的求值结果为`true`，因为它们具有完全相同的`(x, y)`坐标。你可以想象一段客户端代码，它检查`Point`对象并返回它们是否具有相同的状态。如果`Point`对象具有相同的`x`和`y`字段，则它们具有相同的状态。因此，这样的代码可能如下：

```java
if (p1.equals(p2) && p1.getY() == p2.getY()) {
    return true;
} else {
    return false;
}
```

`equals()`功能实际上应该在`Point`类本身中实现，而不是在客户端代码中。与其拥有两个`Point``p1`和`p2`，该方法将第一个对象视为“参数”，并接受第二个对象作为参数。如果两个对象相等，则返回布尔值`true`。以下是`equals()`方法的一个初始实现，它存在缺陷：

```java
// 一个有缺陷的 equals 实现
public boolean equals(Point p2) {
    if (x == p2.getX() && y == p2.getY()) {
        return true;
    } else {
        return false;
    }
}
```

我们可以修正的初始缺陷是，前面的代码没有很好地利用第 5 章描述的“boolean”。回想起当你的代码使用`if/else`语句返回`true`或`false`的布尔值时，你可以直接返回`if`语句条件的值：

```java
return x == p2.getX() && y == p2.getY();
```

`equals()`方法直接访问`p2`的字段是合法的，因此我们可以轻松地进一步修改。私有字段对整个类可见，包括该同类的其他对象，因此一个`Point`对象检查另一个对象的字段是合法的：

```java
return x == p2.x && y == p2.y;
```

有些程序员即使面对其他`Point`对象也尊重封装性，因此不会进行上述更改。为了与其他 Java 类保持一致，我们还必须对`equals()`方法的头部进行更改。`equals()`方法的参数类型不应该是`Point`。该方法必须接受一个类型为`Object`的参数：

```java
public boolean equals(Object o) {
```

`Object`类型变量可以引用任何对象，这意味着任何对象都可以作为参数传递给`equals()`方法。因此，我们可以将`Point`对象与任何类型的对象进行比较，而不仅仅是其他`Point`。例如，类似`p.equals("hello")`的表达式现在是合法的。在这种情况下，`equals()`方法应该返回`false`，因为参数不是`Point`。如果两个对象相等，`equals()`方法应返回`true`。由于`equals()`方法可以直接访问`p2`的字段，因此我们可以轻松地进一步修改：

```java
// 当两个 Point 具有相同的 (x, y) 值时返回 true
public boolean equals(Object o) {
    Point other = (Point) o;
    return x == other.x && y == other.y;
}
```

### `instanceof`关键字

通过将`equals()`方法更改为`Object`类型，我们允许传递`Point`。然而，当客户端传递非`Point`对象时，我们的方法运行并不正常。客户端代码中类似`p.equals("hello")`的表达式将产生如下运行时异常：

```text
Exception in "main"
java.lang.ClassCastException: java.lang.String
at Point.equals(Point.java:25)
at PointMain.main(PointMain.java:25)
```

异常发生是因为将`String`转换为`Point`，因为这些不是兼容的类型。为了防止异常，我们的`equals()`方法需要检查参数的类型，如果不是`Point`则返回`false`。下面的伪代码显示了这种模式：

```java
public boolean equals(Object o) {
    if (o 是一个 Point 对象) {
        比较 x 和 y 值；
    } else {
        return false; // 不是 Point 对象
    }
}
```

有一个运算符`instanceof`，用于测试变量是否引用给定类型的对象。`instanceof`测试是一个二元表达式，采用以下形式并产生布尔结果：

```text
<expression> instanceof <type>
```

表 8.1 列出了使用`instanceof`的示例，给定以下变量：

```java
String s = "carrot"
Point p = new Point(8, 1);
```

#### 表 8.1 示例`instanceof`表达式

| 表达式 | 结果 |
|---|---|
| `s instanceof String` | `true` |
| `s instanceof Point` | `false` |
| `p instanceof String` | `false` |
| `p instanceof Point` | `true` |
| `"hello" instanceof String` | `true` |
| `null instanceof Point` | `false` |

通过空格分隔的操作数不需要括号、点或任何其他符号。左侧的操作数通常是一个变量，右侧的操作数是你想要测试的类名。

在我们的方法中，必须检查参数以判断它是否是一个`Point`对象。以下代码使用`instanceof`关键字来正确实现`equals()`方法：

```java
// 返回 o 是否指向与此 Point 对象 具有相同 (x, y)
// 坐标的 Point
public boolean equals(Object o) {
    if (o instanceof Point) {
        Point other = (Point) o;
        return x == other.x && y == other.y;
    } else { // 不是一个 Point 对象
        return false;
    }
}
```

你可能认为`instanceof`测试允许我们移除下方的类型转换。毕竟，`instanceof`测试确保了只有在`o`确实指向一个`Point`对象时才会进行比较。然而，编译器无法移除类型转换，如果没有它，代码将无法编译。

`instanceof`操作符的一个很好的用处是，当`o`为`null`时，它会返回`false`。因此，如果客户端代码包含类似`equals(null)`的表达式，它将正确地返回`false`，而不是抛出`NullPointerException`。

许多类都实现了像我们这样的`equals()`方法，因此之前的许多`equals()`代码可以重用于样板代码。这是一个构造良好的`equals()`方法的模板。`instanceof`测试和类型转换可能是你在编写任何`equals()`方法时都想要做的两件事：

```java
public boolean equals(Object o) {
    if (o instanceof <type>) {
        <type> other = (<type>) o;
        // 比较数据并返回结果。
    } else {
        return false;
    }
}
```

这是我们`Point`类的第五版本，包含了`toString()`和`equals()`方法：

```java
// 一个 Point 对象表示一对 (x, y) 坐标。
// 第五版本：toString 和 equals。
// 类不不变性：x >= 0 && y >= 0。
public class Point {
    private int x;
    private int y;

    // 使用给定的 (x, y) 位置构造新点
    // 前置：initialX >= 0 && initialY >= 0
    public Point(int initialX, int initialY) {
        setLocation(initialX, initialY);
    }

    // 返回此点到 (0, 0) 的距离
    public double distanceOrigin() {
        return Math.sqrt(x * x + y * y);
    }

    // 返回 o 是否指向与此 Point 具有相同 (x, y)
    // 坐标的 Point
    public boolean equals(Object o) {
        if (o instanceof Point) {
            Point other = (Point) o;
            return x == other.x && y == other.y;
        } else {
            return false;
        }
    }

    // 返回此点的 x 坐标
    public int getX() {
        return x;
    }

    // 返回此点的 y 坐标
    public int getY() {
        return y;
    }

    // 将此点的 (x, y) 位置设置为给定的值
    // 前置：newX >= 0 && newY >= 0
    public void setLocation(int newX, int newY) {
        if (newX < 0 || newY < 0) {
            throw new IllegalArgumentException();
        }
        x = newX;
        y = newY;
    }

    // 返回此点的字符串表示
    public String toString() {
        return "(" + x + ", " + y + ")";
    }

    // 按给定的距离移动此点的位置
    // 前置：x + dx >= 0 && y + dy >= 0
    public void translate(int dx, int dy) {
        setLocation(x + dx, y + dy);
    }
}
```

这是客户端程序的最终版本，它现在在打印`Point`对象时利用了`toString()`方法：

## 8.7 `this`关键字



```java
// 一个处理 2 维点的程序。
// 第五版本，配合带有 toString 方法的 Point 类使用。
public class PointMain {
    public static void main(String[] args) {
        // 创建两个 Point 对象
        Point p1 = new Point(7, 2);
        Point p2 = new Point(4, 3);

        // 打印每个点及其到原点的距离
        System.out.println("p1 is " + p1);
        System.out.println("distance from origin = " + p1.distanceOrigin());

        System.out.println("p2 is " + p2);
        System.out.println("distance from origin = " + p2.distanceOrigin());

        // 将每个点移动到新位置
        p1.translate(1, 6);
        p2.translate(1, 7);

        // 再次打印这些点
        System.out.println("p1 is " + p1);
        System.out.println("p2 is " + p2);
    }
}
```

当我们讨论方法时，提到过对象的实例方法可以引用其他方法和字段，因为实例方法代码知道它正在操作哪个对象。`this` 关键字的一个常见用法是处理变量遮蔽（shadowed variables）。正如之前描述，当一个字段被另一个同名的变量遮蔽时，就会发生遮蔽。

在本节中，我们将探索 `this` 关键字背后的机制。Java 的设计者决定允许这种行为，以便参数名称可以与其相关的字段匹配。例如，以下是我们的 `setCount` 方法的一个合法的头部，尽管我们的字段也叫 `x` 和 `y`：

在大多数情况下，Java 通常会认为该表达式解释为字段。然而，如果存在参数或局部变量 `x`，当你只写 `x` 时它将转而使用它。但是，如果你写 `this.x`，则字段 `x` 将始终被使用。

当然，你可以通过为参数和局部变量命名与字段不同的名称来避免这种情况。然而，某些程序员倾向于让变量与其相关的字段具有相同的名称，因为这可以避免他们去拼接如 `initialX` 或 `newY` 这样独立的参数名称。

## 第 8 章 类

### 多重构造函数

一个类可以有多个构造函数，为客户端提供创建该类实例对象的多种方式。每个构造函数必须具有不同的签名（即参数的数量和类型）。

我们现有的 `Point` 构造函数需要两个参数（`Point` 对象的初始 `x` 和 `y` 坐标）：

```java
// 根据给定的 (x, y) 位置创建一个新点
// pre: x >= 0 && y >= 0
public Point(int x, int y) {
    setLocation(x, y);
}
```

`Point` 类的初始版本没有构造函数。在这种情况下，Java 会提供一个无参数的默认构造函数，将字段初始化为 0。当我们添加了两个参数的构造函数时，我们就失去了默认构造函数。这很遗憾，因为它为构建原点的 `Point` 提供了更短的写法。我们可以通过向类中添加第二个无参数构造函数来恢复这种能力。我们的新构造函数可能像这样：

```java
// 创建位置为 (0, 0) 的 Point 对象
public Point() {
    x = 0;
    y = 0;
}
```

为了消除冗余，我们本可以在构造函数体中手动调用 `setLocation(0, x, y)`。现在可以用两种方式构造 `Point` 了：

```java
Point p1 = new Point(5, -2); // (5, -2)
Point p2 = new Point(); // (0, 0)
```

回到购买汽车的非编程示例，你可以想象某些客户想指定他们新汽车的许多细节（例如，“我想要一辆带金色装饰条的黄色 Civic。”），而其他客户则想指定更多细节并接收默认选项实例。多个构造函数为客户端在请求你的类的新对象时提供了类似的灵活性。

注意，两个构造函数执行的操作相似：唯一的区别在于 `x` 和 `y` 字段接收到的初始值不同。另一种说法是，新构造函数可以用旧的构造函数来表示。下面两行的效果相同：

```java
Point p1 = new Point(); // 在 (0, 0) 构造 Point
Point p2 = new Point(0, 0); // 在 (0, 0) 构造 Point
```

在具有多重构造函数的类中，一种常见的编程范式是让一个构造函数包含真正的初始化代码，并让所有其他构造函数调用它。

## 8.7 `this` 关键字

这意味着每个创建的对象都通过一条公共代码路径，这对于随后的测试和调试非常有用。一个构造函数调用另一个构造函数的语法是编写关键字 `this`，后面跟括号，写上要传递给另一个构造函数的参数：

```java
this(<expression>, <expression>, ..., <expression>);
```

这实际上只是方法调用的正常语法，不同于我们在通常放置方法名的地方使用了特殊关键字。在我们的案例中，我们想传递参数值 0 和 0 来初始化每个字段：

```java
// 在原点 (0, 0) 处构造一个新点
public Point() {
    this(0, 0); // 调用 Point(int, int) 构造函数
}
```

下面的图描绘了一个构造函数调用另一个构造函数的行为。注意 `this` 关键字在我们的代码中有多种用法，既用于调用构造函数，也用于在 `setLocation` 方法中引用字段：

```java
public Point() {
    this(0, 0);
}
```

```java
public Point(int x, int y) {
    setLocation(x, y);
}
```

```java
public void setLocation(int x, int y) {
    this.x = x;
    this.y = y;
}
```

这是我们 `Point` 类的最终版本，整合了本节中的所有更改。该版本的类在构造函数和 `setLocation` 方法中使用了关键字 `this`：

```java
1  // 一个 Point 对象表示一对 (x, y) 坐标。
2  // 第六版本：多重构造函数和 this 关键字。
3  // 类不变性：x >= 0 && y >= 0。
4
5  public class Point {
6      private int x;
7      private int y;
8
9      // 在原点 (0, 0) 处构造一个新点
10     public Point() {
11         this(0, 0); // 调用 Point(int, int) 构造函数
12     }
13
14     // 根据给定的 (x, y) 位置创建一个新点
15     // pre: x >= 0 && y >= 0
16     public Point(int x, int y) {
17         setLocation(x, y);
18     }
19
20     // 返回此 Point 与 (0, 0) 之间的距离
21     public double distanceFromOrigin() {
22         return Math.sqrt(x * x + y * y);
23     }
24
25     // 返回 o 是否指向与此点具有相同 (x, y)
26     // 坐标的点
27     public boolean equals(Object o) {
28         if (o instanceof Point) {
29             Point other = (Point) o;
30             return x == other.x && y == other.y;
31         } else { // 不是 Point 对象
32             return false;
33         }
34     }
35
36     // 返回此点的 x 坐标
37     public int getX() {
38         return x;
39     }
40
41     // 返回此点的 y 坐标
42     public int getY() {
43         return y;
44     }
45
46     // 将给定的值设置此点的 (x, y) 位置
47     // pre: x >= 0 && y >= 0
48     public void setLocation(int x, int y) {
49         if (x < 0 || y < 0) {
50             throw new IllegalArgumentException();
51         }
52         this.x = x;
53         this.y = y;
54     }
55
56     // 返回此点的字符串表示
57     public String toString() {
58         return "(" + x + ", " + y + ")";
59     }
60
61     // 按给定量平移此点
62     // pre: x >= 0 && y >= 0
63     public void translate(int dx, int dy) {
64         x += dx;
65         y += dy;
66     }
67 }
```

## 8.8 更多类

由于 `Point` 类没有提供修改器（例如 `setName` 或 `setWeight`），`Point` 对象的状态在构造后无法被修改。这种对象被称为不可变对象。

### 不可变对象

状态无法被修改的对象。

不提供修改器似乎具有限制性，但不可变对象有一些优点。不可变性有助于类的作者确保对类定义的条件或不变性的遵守。此外，拥有不可变对象的客户端可以将其作为参数传递给任何其他代码，而不必担心代码会修改对象。

编写类时的一个黄金法则是不提供任何没有明确用途的功能。对于修改器方法来说尤其如此。如果客户端程序可能需要给定的修改器，那么提供它更好。修改 `Participant` 对象的一种变通方法是丢弃它并创建一个带有新信息的新对象。由于 `Participant` 对象保留的状态很少，因此这不是一个非常昂贵的操作。

我们有时将小型对象称为轻量级对象。许多轻量级对象为了简单而被制成不可变。

可以在使类对象不可变的同时，保留看似修改对象的操作。不可变对象最著名的例子是 `String` 类。正如第 3 章所讨论的，`String` 一创建就无法修改。任何更改 `String` 的操作（如 `toLowerCase()`）实际上都会返回一个新的 `String`。记住在修改 `String` 时，你必须将 `String` 重新赋值给它的变量，例如：

```java
str = str.toUpperCase();
```

我们可以让 `Point` 类变为不可变的（immutable），在修改状态的操作上返回新对象。例如，它的 `translate` 方法将在翻译后的位置创建一个新的 `Point` 对象，而不是调整现有点的 `x` 和 `y` 值：

```java
// 针对不可变 Point 类的可能的 translate 方法
public Point translate(int dx, int dy) {
    return new Point(x + dx, y + dy);
}
```

使用 `Point` 对象的客户端代码需要微调以使用新的不可变 `Point` 类。任何对类似修改器（mutator-like）方法的调用都必须通过将结果重新赋值给同一个变量来存储结果。例如，我们 `PointMain` 客户端中翻译点 `p1` 的调用将更改为如下：

```java
p1 = p1.translate(11, 6);
```

将 `Point` 类变为不可变将留作为一个练习题。

## `TimeSpan`

考虑一个测量或处理已时间间隔的程序，例如调度器、电视录制机或航空公司飞行系统。在这样的程序中，一个表示已时间跨度的对象是一个非常有用的抽象。

让我们写一个名为 `TimeSpan` 的类，其中每个 `TimeSpan` 对象代表一个小时和分钟的间隔。例如，我们可以构造一个表示 6 小时 15 分钟间隔的 `TimeSpan`。我们只表示小时分钟，忽略天或秒等更大或更小的单位。

由于我们表示的是小时和分钟的间隔，将这两个数量处理为类中的字段似乎是自然而：

```java
// 表示已过的小时和分钟跨度
public class TimeSpan {
    private int hours;
    private int minutes;
}
```

`TimeSpan` 对象的构造函数将接受小时和分钟作为参数，并将值存储在对象的字段中。然而，存在一个潜在的问题：对于等于 60 或更大的分钟值，我们该怎么办？是否允许客户端程序构造一个表示 0 小时 157 分钟的 `TimeSpan` 对象？这种数量更自然的表示方式是 2 小时 37 分钟。

让我们做个决定：只存储分钟小于 60 的 `TimeSpan`。如果用户尝试构造一个分钟超过 60 的 `TimeSpan` 对象，我们将多余的分钟转换为小时。你可能想用 `if/else` 语句或循环来处理大于 60 的分钟，但有一种更简单的方法。记住，对于像 157 这样的大量分钟数，除以 60 会产生小时（2），使用 `%` 运算符对 60 会产生剩余的分钟（37）。字段实际上应该存储小时参数加上除以 60 的分钟参数；而分钟字段应该存储剩余的分钟。

以下代码实现了构造函数。我们假设前提条件是不输入负值（例如 12 分钟）：

```java
// TimeSpan 构造器的初始版本
// pre: hours >= 0 && minutes >= 0
public TimeSpan(int hours, int minutes) {
    this.hours = hours + minutes / 60;
    this.minutes = minutes % 60;
}
```

我们将设计决策表示为类不变性（class invariant），即每个 `TimeSpan` 对象字段的值始终小于 60。

`TimeSpan` 对象的一个有用行为是能够向跨度中添加更多小时和分钟。航空公司调度程序可能会用此来添加两次航班的经过时间，以确定乘客行程的总旅行时间。让我们将此行为实现为一个名为 `add` 的方法，该方法接受小时和分钟参数。这里是该方法的初始（错误的）版本：

```java
// add 方法的错误版本
// pre: hours >= 0 && minutes >= 0
public void add(int hours, int minutes) {
    this.hours += hours;
    this.minutes += minutes;
}
```

上述代码的问题是，它允许客户端违反我们的类不变性。如果客户端传递一个足够大的分钟值，使得总分钟大于 60，则分钟字段可能会有一个无效值。例如，如果在 1 小时 30 分钟的跨度上增加 45 分钟，结果将是 1 小时 75 分钟。我们必须在 `add` 方法的末编写代码来处理大于 60 的分钟。以下代码实现了该行为：

```java
// 将给定间隔添加到此时间跨度
// pre: hours >= 0 && minutes >= 0
public void add(int hours, int minutes) {
    this.hours += hours;
    this.minutes += minutes;
}
```

```java
// 将每 60 分钟转换为一小时
this.hours += this.minutes / 60;
this.minutes = this.minutes % 60;
```

代码现在必须两个地方解决大于 60 的分钟值问题，但在一个地方解决这个问题，比在整个类中冗余地检查它要好。一个更优雅的解决方案是让构造函数将字段初始化为 0，然后调用 `add` 方法：

```java
// 使用给定间隔构造时间跨度
// pre: hours >= 0 && minutes >= 0
public TimeSpan(int hours, int minutes) {
    this.hours = 0;
    this.minutes = 0;
    add(hours, minutes);
}
```

（字段本就会初始化为 0，但许多程序员更倾向于为了清晰而进行初始化。）

由于我们的 `add` 方法是一个修改器，`TimeSpan` 对象不是不可变的。如果我们想让 `TimeSpan` 变为不可变，我们可以返回一个新的 `TimeSpan` 而不是修改当前的。`TimeSpan` 的另一个有用操作是能够打印它们。正如在本章中所见，为了使对象可打印，我们可以写一个 `toString` 方法：

```java
// 返回此时间跨度的字符串，例如 "6h15m"
public String toString() {
    return hours + "h" + minutes + "m";
}
```

可能还需要比较 `TimeSpan` 对象以判断它们是否相等。首先我们必须进行 `instanceof` 测试，如果成功，我们必须将参数转换为 `TimeSpan`。



```java
// 如果 o 是表示相同小时
// 分钟的 TimeSpan 对象则返回 true
public boolean equals(Object o) {
    if (o instanceof TimeSpan) {
        TimeSpan other = (TimeSpan) o;
        return hours == other.hours &&
               minutes == other.minutes;
    } else { 不是 TimeSpan 对象
        return false;
    }
}
```

以下是完整的`TimeSpan`代码：

```java
public class TimeSpan {
    private int hours;
    private int minutes;

    // 使用给定间隔构造时间跨度
    // pre: hours >= 0 && minutes >= 0
    public TimeSpan(int hours, int minutes) {
        this.hours = 0;
        this.minutes = 0;
        add(hours, minutes);
    }

    // 将给定间隔添加到此时间跨度
    // pre: hours >= 0 && minutes >= 0
    public void add(int hours, int minutes) {
        this.hours += hours;
        this.minutes += minutes;
    }

    // 将每 60 分钟转换为一小时
    this.hours += this.minutes / 60;
    this.minutes %= 60;

    // 如果 o 是表示相同小时
    // 分钟的 TimeSpan 对象则返回 true
    public boolean equals(Object o) {
        if (o instanceof TimeSpan) {
            TimeSpan other = (TimeSpan) o;
            return hours == other.hours &&
                   minutes == other.minutes;
        } else {
            return false;
        }
    }

    // 返回此时间跨度的字符串，例如 "6h15m"
    public String toString() {
        return hours + "h" + minutes + "m";
    }
}
```

```java
// 表示已过的小时和分钟跨度。

// 类不变性：minutes < 60
```

## 更改内部实现

某些可能并不显而易见的一点是，对于我们的`TimeSpan`的内部表示，客户端希望将时间看作小时和分钟，但`TimeSpan`对象并不需要用那两个数据字段来存储时间。事实上，如果我们简单地存储总分钟数，`TimeSpan`的代码将变得简单得多。我们可以通过向总数添加 60 分钟来将每个小时吸收进去：

## 8.8 更多类

```java
// 仅使用总分钟数的另一种实现方式
public class TimeSpan {
    private int totalMinutes;
}
```

记住，封装允许我们在不更改任何客户端代码的情况下更改类的内部实现。我们可以使用总分钟数来实现相同的`add`、`toString`和`equals`行为。我们将对代码进行修改以适应新的表示形式。

例如，`add`方法需要将小时和分钟合并，并将它们都存入`totalMinutes`。我们将小时乘以 60：

```java
// 将给定的间隔添加到此时间跨度中
// pre: hours >= 0 && minutes >= 0
public void add(int hours, int minutes) {
    totalMinutes += 60 * hours + minutes;
}
```

构造函数、`toString`和`equals`方法也需要微小的修改以适应我们的新表示形式。这里是使用总分钟数而不是小时和分钟实现的完整类：

```java
// 表示经过的小时和分钟跨度。
// 仅使用总分钟数的另一种实现方式。
public class TimeSpan {
    private int totalMinutes;

    // 使用给定的间隔构造时间跨度
    // pre: hours >= 0 && minutes >= 0
    public TimeSpan(int hours, int minutes) {
        totalMinutes = 60 * hours + minutes;
    }

    // 将给定的间隔添加到此时间跨度中
    // pre: hours >= 0 && minutes >= 0
    public void add(int hours, int minutes) {
        totalMinutes += 60 * hours + minutes;
    }

    // 返回 o 是否代表与此 TimeSpan 对象相同的小时和分钟数的 TimeSpan
    public boolean equals(Object o) {
        if (o instanceof TimeSpan) {
            TimeSpan other = (TimeSpan) o;
            return totalMinutes == other.totalMinutes;
        } else {
            return false;
        }
    }

    // 返回此时间跨度的字符串，例如 "6h15m"
    public String toString() {
        return (totalMinutes / 60) + "h " +
                (totalMinutes % 60) + "m";
    }
}
```

这种新的内部表示法的主要优势是代码更短、更简单。我们不需要将时间间隔拆分为两部分，也不需要担心分钟值变得过大。封装使我们能够进行这样的设计更改而无需担心客户端程序会崩溃。客户端将看到该版本的类的相同行为。

## 8.9 案例研究：设计股票类

到目前为止，我们已经写了几个类，但还没有讨论过如何设计一个类，或者如何将一个编程问题拆分为多个类。在本节中，我们将研究一个较大的编程问题，并设计一个类和客户端来解决它。我们将创建一个`stock`类和一个客户端程序，用于比较用户购买的股票的性能。

考虑编写一个财务记录来记录两只股票的股份并报告哪只利润最大的任务。投资者可能在不同的时间和价格下购买过同一只股票。与程序的交互看起来如下：

第一只股票的代码：AM2N

你进行了几次购买？2

1: 多少股，每股价格是多少？50 35.06

2: 多少股，每股价格是多少？25 38.52

今天的每股价格是多少？37.29

净利润/亏损：$80.75

第二只股票的代码：INC

你进行了几次购买？3

1: 多少股，每股价格是多少？15 16.50

2: 多少股，每股价格是多少？10 18.09

3: 多少股，每股价格是多少？20 17.15

今天的每股价格是多少？17.82

净利润/亏损：$29.75

AM2N 的利润高于 INTC。

程序必须执行若干操作：提示用户输入、报告利润等。客户端程序可以执行所有这些操作，并可以使用现有类型（如`double`和`String`）跟踪财务数据。然而，我们记得在本章开始时讨论了面向对象的推理。对于复杂的程序，从它可能解决的相关对象的角度来思考通常是有用的，而不是将所有行为放在客户端程序中。在这个特定的程序中，我们必须执行若干涉及跟踪特定股票购买情况的计算，因此将购买信息存储在对象中将很有用。

## 8.9 案例研究：设计 Stock 类

一种可能的设计是创建一个`Purchase`类，记录对某只股票单次购买的信息。例如，如果用户指定进行了三次购买，则会构造三个对象。然而，更有用的抽象是持有关于某只股票所有购买的整体信息。投资者可能会多次购买同一只股票，因此如果能有一种简单的方法将这些股份及其总成本累积到单个对象中将是好的。

因此，不是使用`Purchase`类，而是每个`Stock`对象将跟踪投资者对某只股票的累计股份，并提供利润/亏损信息。我们的`Stock`类将位于名为`Stock.java`的文件中，而客户端程序本身将位于名为`Main.java`的独立文件中。

## 面向对象设计启发式

我们现在面临着决定`Stock`类内容的重要任务。为了做到这一点，让我们看看应该包含什么：

- 用户提示每只股票的代码。信息必须存储在某处。
- 用户提示每只股票的购买次数。
- 从控制台读取每次购买（股份和每股价格）。信息必须存储在某处。
- 计算每只股票的利润/亏损。
- 打印每只股票的利润/亏损。
- 比较两个利润/亏损，并打印关于哪只股票表现更好。

我们可能会诱惑我们将这些责任的大部分或全部放在`Stock`类中。在编写类时的一个关键想法是它们应该具有内聚性。

## 内聚性

类代码的延伸程度代表一个抽象。

追求高内聚是一个面向对象的设计启发式，即在设计面向对象的程序时遵循的法则或准则。将所有责任放在`Stock`类中不会表示一个清晰的抽象。我们想要表示的抽象是某只股票的累计购买。

我们需要提示用户信息并打印消息，但这是特定客户端程序的。其他程序可能希望在不使用这些消息或提示的情况下跟踪购买。如果`Stock`类处理提示和打印，它将与此客户端程序紧密交织，无法重用。

通常情况下，我们希望减少类之间不必要的依赖。面向对象程序中类之间的依赖构成了耦合。

## 耦合

避免不必要的耦合是面向对象编程中常用的第二个启发式。避免这种问题的设计有时被称为松耦合。

让我们现在根据启发式划分一些责任。由于`StockMain`客户端程序执行控制台 I/O，它应该处理此处列出的责任：

# StockMain

- 提示每只股票的代码。
- 提示每只股票的购买次数。
- 从控制台读取每次购买（股份和每股价格）。
- 打印每只股票的利润/亏损。
- 比较两个利润/亏损并打印关于哪只股票表现更好的消息。

如果`StockMain`客户端程序执行控制台 I/O，那么它似乎也应该由它存储有关每次股票购买的信息（即股份数量和支付价格）。但我们的`Stock`对象应该包含计算股票总利润/亏损的功能，它将需要所有购买数据来完成。这引导我们走向第三个设计启发式：相关数据和行为应该在同一个地方。根据此，我们可以写出`Stock`类的责任：

# Stock

- 存储股票代码。
- 存储投资者对该股票购买的累计信息。
- 记录对股票的购买。
- 计算股票的总利润/亏损。

在设计大型面向对象程序时，许多软件工程师会在类似于本节所示的索引卡上编写信息。每张卡片被称为 CRC 卡，因为它列出了类（Class）、责任（Responsibilities）以及任何协作者（与其耦合的其它类）。

## 8.9 案例研究：设计股票类

以下列表总结了本节讨论的设计启发式：

- 类应该是高内聚的，只表示一个抽象。
- 类应该避免不必要的耦合。
- 相关的数据和行为应该在同一个类中。

请注意，我们在开始设计时考虑的是责任，而不是指定字段，这与我们在开发`Point`类时所做的那样。我们在`Point`类的演进中是从字段开始的，因为与点相关的数据比与多次股票购买相关的数据要明显得多。此外，字段在概念上也比实例方法更简单。

### 股票字段和方法头

在本节中，我们将为`Stock`对象实现其行为应使用的方法名和签名做出设计。我们将根据此设计来确定实现该行为需要哪些字段。

我们决定`Stock`对象应该允许客户端记录购买情况并请求总利润或亏损。这些任务中的每一个都可以表示述一个方法。记录购买可以表示为名为`purchase`的方法。获取总利润或亏损可以表示为名为`getProfit`的方法。

`purchase`方法应该记录单次购买的信息。一次购买由购买的股数（整数）和每股价格（可以包含带有美元和分数的实数）组成，我们的`purchase`方法应该接受两个参数：一个用于购买股数的`int`和一个用于每股价格的`double`。该方法可以使用`void`返回类型，因为在记录完每次购买后不需要返回任何内容：

```java
public void purchase(int shares, double pricePerShare) {
```

`getProfit`需要返回在对该股票的所有累计购买中获得的利润或亏损金额。考虑一位对某只股票进行了以下三次购买的投资者：

- 购买 #1：20 股 * $10/股 = $200 成本
- 购买 #2：20 股 * $30/股 = $600 成本
- 购买 #3：10 股 * $20/股 = $200 成本
- 总计 50 股，$1000 成本

今天的每股价格为 $22.00，该投资者 50 股股票的当前市场价值为 (50 * 22) 或 $1100。由于投资者支付了 $1000 购买这些股票，而它们现在价值 $1100，因此投资者获得了 (1100 - 1000) 或 $100 的利润。利润的通用公式如下：

```text
profit = ((total shares) * (current share price)) - (total cost)
```

## 第 8 章 类

此计算所需的总股数和总成本是来自该股票所有已购买记录的累计信息。这意味着在每次调用`purchase`方法时，都需要存储信息，以便稍后在`getProfit`方法中使用。这里的一个关键观察是，我们不需要存储每次购买的股数、每股价格和成本：我们只需要存储到目前为止购买的总股数的累计和，以及获取这些花费的总金额，以获取这些值。

我们计算利润所需的第三个值是当前股价。我们可以选择也将此字段设在`Stock`类中，但股价是一个经常变化的动态值。我们在单次调用`getProfit`方法时使用它，但下一次调用可能在之后的某个日期，那时每股价格已经发生了变化。

这引导我们走向另一个设计启发式：字段应该代表对对象具有核心重要性的值以及在多个方法中使用的值。添加过多的字段会改变类，并可能导致代码更难读。如果一个值在类中的一个方法中使用，最好让它成为该方法的参数而不是字段。我们将股价设为`getProfit`方法的参数。

```java
public double getProfit(double currentPrice) {
```

我们尚未讨论的状态之一是，每个类都有一个符号，例如"AMZN"。我们将符号作为`String`字段存储在每个`Stock`对象中。以下是我们目前为止`Stock`类的骨架：

```java
// 不完全的 Stock 类
class Stock {
    private String symbol;
    private int totalShares;
    private double totalCost;

    public double getProfit(double currentPrice) {

    }

    public void purchase(int shares, double pricePerShare) {

    }
}
```

### 股票方法和构造函数的实现

现在我们已经决定了`Stock`的一些状态和行为，让我们思考如何构造`Stock`对象。客户端程序需要能够创建两个`Stock`并记录它们的购买情况。

编写一个接受三个参数的构造函数（符号、购买总股数和总成本）可能是很有吸引力的。但我们的`Stock`对象是购买的累加器，我们可能希望在记录初始购买之前创建新的`Stock`对象。让我们设计类，仅要求符号作为参数，并将其他字段初始化为 0：

## 8.9 案例研究：设计股票类

```java
// 初始化一个没有购买股票的新 Stock
public Stock(String theSymbol) {
    symbol = theSymbol;
    totalShares = 0;
    totalCost = 0.0;
}
```

当构造函数接受对象作为参数时（例如`String` theSymbol），检查该参数的值以确保它不为`null`可能是合理的。处理这种情况的一种方法是抛出一个异常。Sun 建议在创建`Stock`对象时如果符号为`null`则抛出`NullPointerException`。我们可以通过在构造函数开头插入以下代码来实现：

```java
if (theSymbol == null) {
    throw new NullPointerException();
}
```

现在编写`purchase`方法体。记录购买是将股数加到总股数中，并将每股价格加到总成本中。这是实现此点的`purchase`方法代码：

```java
// 以给定的价格记录购买
public void purchase(int shares, double pricePerShare) {
    totalShares += shares;
    totalCost += pricePerShare;
}
```

与构造函数一样，检查传入的参数以确保它们是有效的。在这种情况下，股数和价格必须为负。为了执行此测试，我们可以插入：

```java
if (shares < 0 || pricePerShare < 0) {
    throw new IllegalArgumentException();
}
```



接下来编写`getProfit`方法体。如之前所述，股票的利润等于其市场价值减去成本。我们可以使用`totalShares`和`totalCost`字段以及`currentPrice`参数来实现此公式：

```java
// 根据每股价格返回该股票的利润或亏损
public double getProfit(double currentPrice) {
    return totalShares * currentPrice - totalCost;
}
```

注意，代码不需要括号，因为乘法的优先级高于减法。与其他方法一样，我们应该检查非法参数值。在这种情况下，我们不允许每股价格为负数。为了确保这一点，我们可以在方法开头放置以下代码：

```java
if (currentPrice < 0.0) {
    throw new IllegalArgumentException();
}
```

在我们写完`Stock`的所有字段、构造函数和方法后，它应该是这样的：

```java
// Stock 对象代表股票的购买
class Stock {
    private String symbol; // 股票符号，例如 "YHO"
    private int totalShares; // 总股数
    private double totalCost; // 所有股票的总成本

    // 初始化一个没有购买股票的新 Stock
    // 前提：symbol != null
    public Stock(String symbol) {
        if (symbol == null) {
            throw new NullPointerException();
        }
        symbol = symbol;
        totalShares = 0;
        totalCost = 0;
    }

    // 根据每股价格返回该股票的利润或亏损
    // 前提：currentPrice >= 0.0
    public double getProfit(double currentPrice) {
        if (currentPrice < 0.0) {
            throw new IllegalArgumentException();
        }
        double marketValue = totalShares * currentPrice;
        return marketValue - totalCost;
    }

    // 以给定的价格记录购买
    // 前提：shares >= 0 && pricePerShare >= 0.0
    public void purchase(int shares, double pricePerShare) {
        if (shares < 0 || pricePerShare < 0.0) {
            throw new IllegalArgumentException();
        }
        totalShares += shares;
        totalCost += shares * pricePerShare;
    }
}
```

## 8.9 案例研究：设计一个 Stock 类

使用`Stock`类的客户端代码编写如下：

```java
1 // 该程序跟踪用户对两只股票的购买情况，
2 // 计算并报告哪只股票利润更高。
3
import java.util.*;

public class Stock {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // 第一只股票
        System.out.print("First stock's symbol: ");
        String symbol1 = scanner.next();
        Stock stock1 = new Stock(symbol1);
        double profit1 = makePurchases(stock1, scanner);

        // 第二只股票
        System.out.print("Second stock's symbol: ");
        String symbol2 = scanner.next();
        Stock stock2 = new Stock(symbol2);
        double profit2 = makePurchases(stock2, scanner);

        // 报告哪只股票赚得更多
        if (profit1 > profit2) {
            System.out.println(symbol1 + " was more " + "profitable than " + symbol2 + ".");
        } else if (profit2 > profit1) {
            System.out.println(symbol2 + " was more " + "profitable than " + symbol1 + ".");
        } else {
            System.out.println(symbol1 + " and " + symbol2 + " are equally profitable.");
        }
    }

    // 购买股票并返回利润
    public static double makePurchases(Stock currentStock, Scanner console) {
        System.out.print("How many purchases did you make? ");
        int numPurchases = console.nextInt();

        // 询问每次购买的情况
        for (int i = 1; i < numPurchases; i++) {
            System.out.print(" " + "many shares, at what price per share? ");
            int numShares = console.nextInt();
            double pricePerShare = console.nextDouble();

            // 要求 Stock 对象记录这次购买
            currentStock.purchase(numShares, pricePerShare);
        }

        // 使用 Stock 对象计算利润
        System.out.print("What is today's price per share? ");
        double currentPrice = console.nextDouble();
        double profit = currentStock.getProfit(currentPrice);
        System.out.println("Net profit/loss: " + profit);
        System.out.println();
        return profit;
    }
}
```

我们的`Stock`对象中还可以包含其他有用的方法。例如，为`Stock`的数据（代码、股份数量等）实现访问器（accessors），以及实现一个能够让`Stock`对象易于打印的`toString`方法，这些将是有帮助的。我们甚至可以添加第二个构造函数，用于接受初始股份数和成本。这些功能留给你在练习中实现。

## 第 8 章 类

## 第 8 章总结

面向对象编程是一种不同的程序编写哲学，它关注程序中的节点或实体，而不是程序的动词或动作。在面向对象编程中，对象的状态和行为被分组到对象中，对象之间相互进行通信。

使用`new`关键字。你可以在类中指定多个构造函数；如果未指定，Java 会提供一个默认构造函数。

类是新类型对象的蓝图，规定了对象的数据和行为。可以请求类来构建许多该类型的对象（也称为“实例”）。

通常，一个对象即使不知道其他对象工作的所有细节，也可以与其他对象通信。这一原则被称为抽象（abstraction）。大多数对象保护其内部数据免受意外修改，这被称为封装（encapsulation）。你可以通过使用`private`修饰符声明字段来实现封装，防止其他类直接修改它们的值。

每个对象的数据使用特殊的变量字段（fields）来指定。

对象方法分为两类：访问器（accessors）和修改器（mutators）。访问器（如`get`方法）提供对象的信息；修改器则允许修改对象的状态（例如`Point`对象的`translate`方法）。

对象的行为通过实例方法（instance methods）来指定。

类可以被请求构建许多该类型的对象（也称为“实例”）。

类可以定义一个特殊方法称为构造函数，用于创建并初始化状态。为了让对象易于打印，编写一个`toString`方法。为了测试对象的相等性，编写一个`equals`方法。

## 自测题

`this`关键字可以引用自身。一个在构造后状态不可更改的对象被称为不可变对象（immutable object）。

## 8.1 节 面向对象概念

- 1. 面向对象编程与过程化编程的区别。

- 2. 什么是对象？

- 3. 什么是类？

- 4. 想象你在创建一个像计算器那样的设备。它可能有什么？

## 8.2 节 对象状态

- 5. 字段（field）和参数（parameter）的区别是什么？

- 6. 创建一个表示名、姓和中间字母的类。

## 8.3 节 对象行为

- 7. 访问器和修改器的区别是什么？

- 8. 在你的`Point`类中添加以下方法：

```java
public double distance(Point other)
```

- 9. 访问器的命名规范是什么？

## 8.4 节 初始化

- 10. 什么是构造函数？它与其他方法有何不同？

- 11. 下述构造函数有两个主要问题：

```java
public Point(int initialX, int initialY) {
    int x = initialX;
    int y = initialY;
}
```

- 12. 为`Name`类添加一个构造函数，接受名、中间字母和姓作为参数，并初始化`Name`对象的状态。

## 8.5 节 封装

- 13. 什么是抽象？对象如何提供抽象？

- 14. `public`和`private`关键字的区别是什么？哪些项应该是私有的？

- 15. 当字段设为私有时，客户端程序无法直接看到它们。如何允许类读取这些字段而不允许客户端更改？

- 16. 在`Point`类中添加名为`setName`和`setTo`方法，允许客户端更改 Point 对象的 x 和 y 坐标。

## 8.6 节 实例方法

- 18. 如何编写一个可以方便打印在控制台上的类？

- 19. 使用`==`操作符操作对象有什么潜在问题？如何指定一种比较类对象相等的方法？

- 20. `java.awt`包中的`Point`类有一个`toString`方法，返回如下格式的字符串：

```
java.awt.Point(x=7,y=2)
```

在你的`Point`类中写一个修改后的`toString`方法，返回这种格式的结果。

- 21. 为`Name`类编写`toString`和`equals`方法。`toString`方法应返回类似 "John Q. Public" 的字符串。如果两个`Name`有相同的名、姓和中间字母，则`equals`方法应返回`true`。

## 8.7 节 this 关键字

- 22. `this`关键字的含义是什么？描述关键字的三种使用方式。

- 23. 为`Point`类添加一个构造函数，接受另一个`Point`作为参数，并将此新 Point 初始化相同的 (x, y) 值。在你的解决方案中使用`this`关键字。

## 练习

为你的`Name`类添加名为`firstName`、`middleInitial`和`setName`方法。参数与你的字段相同，并在解决方案中使用`this`关键字。

# 第 8.8 节：类

- 25. 什么是不可变对象？使用不可变对象有什么好处？

- 26. （在回答此问题之前你必须完成自检题 24。）你的`Name`类是不可变的吗？为什么是或不是？你在之前的几个问题中开发了`Name`。它在之前的任何版本中是不可变的吗？

- 27. 封装是如何允许你更改类的内部实现的？

- 28. 为`Participant`类添加`toString`和`equals`方法。`toString`方法应返回一个类似于 "John Doe (height=70.0 weight=195.0)" 的字符串。如果两个参与者的姓名和身高相同，`equals`方法应返回`true`。

# 第 8.9 节：案例研究：设计 Stock 类

- 29. 什么是内聚性？如何判断一个类是否具有内聚性？

- 30. 为什么我们没有将控制台 I/O 代码放入`Stock`类中？

- 31. 为`Stock`类添加访问器方法（accessor methods），以返回股票代码、总股数和总成本。

## 练习

- 1. 为`Point`类添加以下方法：

```java
public int manhattanDistance(Point other)
```

返回当前`Point`对象与给定的另一个`Point`对象之间的“曼哈顿距离”。曼哈顿距离指的是如果只能通过水平或垂直移动来旅行，两个地点之间的距离，例如在曼哈顿街道上开车。在我们的案例中，曼哈顿距离是坐标差绝对值之和；换句话说，两点之间 x 轴差加上 y 轴差。

- 2. 为`Point`类添加以下方法：

```java
public boolean isVertical(Point other)
```

如果给定的`Point`与此`Point`垂直对齐（即它们的 x 坐标相同），则返回`true`。

- 3. 为`Point`类添加以下方法：

```java
public double slope(Point other)
```

返回连接此`Point`和另一个`Point`的直线斜率。使用公式`(y2-y1) / (x2-x1)`来确定两点`(x1, y1)`和`(x2, y2)`之间的斜率。注意，此公式对于 x 相同的点失效，因此在这种情况下抛出`IllegalArgumentException`。

- 4. 为`Point`类添加以下方法：

```java
public boolean isCollinear(Point p1, Point p2)
```

判断此`Point`是否与另外两个`Point`共线。如果可以用一条直线连接它们，则这些点是共线的。两个基本例子是具有相同 x 或 y 坐标的三个点。更一般的情况可以通过计算每对点之间的斜率，并检查该斜率对于所有点对是否相同来确定。使用公式`(y2 - y1)/(x2 - x1)`来确定两点`(x1, y1)`和`(x2, y2)`之间的斜率。（注意，此公式对于 x 相同的点失效，因此在你的代码中必须对其进行特殊处理。）

由于 Java 的`double`类型是不精确的，在比较斜率值之前，将所有斜率值保留到小数点后四位的合理精度。

- 5. 写一个`Point`类的不可变版本。注意，任何修改操作应该返回新的`Point`对象。

- 6. 为`TimeSpan`类添加以下方法：

```java
public void add(TimeSpan span)
给此时间跨加上给定的时间。
public void subtract(TimeSpan span)
从此时间跨中减去给定的时间。
public void scale(int factor)
按给定的因子缩放此时间跨。例如，1 小时 45 分钟乘以 2 等于 3 小时 30 分钟。
```

- 7. 为`Stock`类添加以下方法：

```java
public void clear()
将此`Stock`的购买股数和总成本重置为 0。
```

- 8. 为`Stock`类添加以下方法：

```java
public boolean equals(Object o)
如果给定的对象是与此对象具有相同代码、购买股数和总成本的`Stock`对象，则返回`true`。
```

- 9. 写一个名为`Line`的类，表示两个`Point`之间的线段。你的`Line`对象应该具有以下方法：

```java
public Line(Point p1, Point p2)
构造一个包含给定两个`Point`的新`Line`。
public Point getP1()
返回此`Line`的第一个端点。
public Point getP2()
返回此`Line`的第二个端点。
```

```java
public String toString()
```

返回此 Line 的字符串表示，例如 "(22, 3), (4, 7)"

- 10. 为你的`Line`类添加以下方法：

```java
public double getSlope()
```



返回此 `Line` 的斜率。点 `(x1, y1)` 和 `(x2, y2)` 之间直线的斜率等于 `(y2 - y1) / (x2 - x1)`。如果 `x2 == x1`，分母为零且斜率未定义，因此你可以抛出一个异常。

- 11. 为你的 `Line` 类添加以下方法：

```java
public Line(int x1, int y1, int x2, int y2)
```

构造一个包含这两个点的新 `Line`。

- 12. 为你的 `Line` 类添加以下方法：

```java
public boolean equals(Object o)
```

判断给对象对象是具有相同端点的 `Line`。

- 13. 为你的 `Line` 类添加以下方法：

```java
public boolean isCollinear(Point p)
```

如果给定的 `Point` 与此 `Line` 共线，则返回 true。

# 第 8 章 类

```java
public int getHeight()
```

返回此矩形的高度。

```java
public int getWidth()
```

返回此矩形的宽度。

```java
public int getX()
```

返回此矩形的 x 坐标。

```java
public int getY()
```

返回此矩形的 y 坐标。

```java
public String toString()
```

返回此矩形的字符串表示，例如 `"Rectangle[x=1,y=2,width=3,height=4]"`。

- 15. 为你的 `Rectangle` 类添加以下方法：

```java
public boolean equals(Object o)
```

判断给对象对象是与此矩形具有相同 `(x, y)` 坐标、宽度和高度的矩形。

- 16. 为你的 `Rectangle` 类添加以下构造函数：

```java
public Rectangle(Point p, int width, int height)
```

构造一个左上角由给定 `Point` 指定且具有给定宽度高度的新矩形。

- 17. 为你的 `Rectangle` 类添加以下方法：

```java
public boolean contains(int x, int y)
```

```java
public boolean contains(Point p)
```

判断给定的点或坐标是否位于此矩形的范围内。

- 18. 为你的 `Rectangle` 类添加以下方法：

```java
public Rectangle union(Rectangle rect)
```

返回一个新矩形，表示包含此矩形和另一个矩形的紧凑边界框的区域。

```java
public Rectangle intersection(Rectangle rect)
```

返回一个新矩形，表示完全包含此矩形和另一个矩形的最大矩形区域。如果矩形完全不相交，则返回一个宽度和高度均为 0 的矩形。

## 编程项目

- 1. 写一个名为 `RationalNumber` 的类，表示具有整数分子和分母的分数。`RationalNumber` 对象应该具有以下方法：

```java
public RationalNumber(int numerator, int denominator)
```

构造一个表示比例（分子/分母）的有理数。分母不能为 0，因此如果传入 0，则抛出 `IllegalArgumentException`。

```java
public RationalNumber()
```

构造一个有理数。

```java
public boolean equals(Object o)
```

判断该有理数是否与给定的对象相等。两个有理数的分子和分母相同时，它们被认为是相等。

```java
public int getDenominator()
```

返回该有理数的分母；例如，比例为 3/5 时，返回 5。

```java
public int getNumerator()
```

返回该有理数的分子；例如，比例为 3/5 时，返回 3。

```java
public String toString()
```

返回该有理数的字符串表示，例如 `"3/5"`。一个额外的挑战是为 `RationalNumber` 类实现加法、减法、乘法和除法。

- 2. 编写一个 `Date` 类，表示年、月、日。`Date` 对象应该具有以下方法：

```java
public Date(int year, int month, int day)
```

构造一个 `Date` 对象。

```java
public void addDays(int days)
```

将该 `Date` 对象向前增加指定的天数。

```java
public void addWeeks(int weeks)
```

将该 `Date` 对象向前增加指定的周数。

```java
public int daysTo(Date other)
```

返回该日期与另一个 `Date` 对象之间的天数差。

```java
public boolean equals(Object o)
```

判断两个 `Date` 对象是否表示相同的日期。

```java
public int getData()
```

返回该 `Date` 的日期值；例如，2006-7-22 返回 22。

```java
public int getMonth()
```

返回该 `Date` 的月份；例如，2006-7-22 返回 7。

```java
public int getYear()
```

返回该 `Date` 的年份；例如，2006-7-22 返回 2006。

```java
public boolean isLeapYear()
```

如果该 `Date` 的年份是闰年，则返回 true。闰年每四年一次，但 100 的倍数不是 400 的倍数除外。例如，1956、1844、1600 和 2000 是闰年；1983 和 2002 不是。

```java
public String toString()
```

以年/月/日的格式返回该日期的字符串，例如 `"2006/7/22"`。

- 3. 一个名为 `GroceryList` 类表示购物列表，另一个名为 `GroceryItemOrder` 的类表示购买特定物品请求（例如：四盒饼干）。

`GroceryList` 类应该使用数组字段来存储购物项目，并跟踪其大小（到目前为止的项目数量）。假设购物列表不会超过 10 个项目。`GroceryList` 对象应该具有以下方法：

```java
public GroceryList()
```

构造一个新的空的购物列表。

```java
public void add(GroceryItemOrder item)
```

如果列表未满（即少于 10 个项目），则将给定的订单订单添加到列表中。

```java
public double getTotalCost()
```

返回列表中所有购物订单的总成本。

`GroceryItemOrder` 类应该存储物品数量和单价。`GroceryItemOrder` 对象应该具有以下方法：

```java
public GroceryItemOrder(String name, int quantity, double pricePerUnit)
```

构造一个物品订单，以购买指定名称、指定数量且单价为给定的物品。

```java
public double getCost()
```

返回该物品在指定数量下的总成本。例如，单价为 2.30 的四盒饼干总成本为 9.20。

```java
public void setQuantity(int quantity)
```

设置该购物物品的数量为给定的值。

# 第 9 章

## 继承与接口

## 引言

在本章中，我们将探索 Java 语言提供的帮助你编写更好结构解决方案的两个最重要的技术。继承允许你在类之间共享代码以减少冗余，并允许你以相同的方式处理不同的类。接口允许你以相同的方式处理多个不同的类。

在小型示例中很难看出继承和接口的用处，但在更大的项目中，它们是无价之。事实上，我们将看到继承和接口如何帮助我们在像 Java 库那样的规模上创建结构化代码。

### 9.1 继承基础

#### 非编程层级结构

当你开始考虑继承时，你能够识别程序中不同对象和类之间的相似之处。让我们先从一个非编程的示例开始：公司员工的层级结构。

想象有一家大公司，雇佣了几类员工：律师、总秘书、法务秘书和营销人员。公司有一系列关于休假、病假、医疗福利、反骚扰规定等规则。公司的每个部门也有自己的一些规则；例如，律师申请休假时使用的表格可能与秘书不同。

想象所有员工都参加了一场共同的入职培训，在培训中学习通用规则。每位员工都会收到一份 20 页的这些规则手册进行阅读。一群混合的员工可以一起参加培训：律师、秘书和营销人员都坐在同一个培训小组中。

结束后，员工回到各自的部门，接受针对该部门特定规则的培训。每位员工都会收到一份只有两到三页的较短手册，涵盖该部门的特定规则。某些规则被添加到通用的 20 页手册中，另一些被替换。例如，可能某类员工有三周休假而不是两周，可能某类员工使用粉色表格申请请假，而不是 20 页手册中列出的黄色表格。每类员工都有自己的具有独特长度和内容的子手册，如图 9.1 所示。

另一种解决方案是给每位员工一本大手册，其中包含适用的通用规则和所属部门的规则。例如，律师有一份 22 页的手册，秘书有一份 21 页的手册，营销人员有一份 23 页的手册。事实上，这种合并甚至可以节省几页纸。那么，公司为什么要费劲为每位员工准备两本手册呢？

主要问题是冗余和维护。22 页的律师手册包含了大量与 21 页秘书手册相同的文本。如果某条通用规则发生变化，所有的手册都必须单独更新，这是一个冗味的过程。在许多手册上进行相同的更改也容易出错，因为很容易在其中一个副本中进行了修改，却忘记在另一份中修改。

较短、更具体的手册也有实际的吸引力。想要了解所有律师特定规则的人只需阅读 2 页的律师手册即可，而无需在 22 页的律师手册中反复搜寻以发现差异。

这里有两个核心思想：

- 1. 能够指定一组适用于许多小组的宽泛规则（20 页手册）是有用的。
- 2. 能够指定一组针对特定小组的较小规则，并能够替换宽泛规则中的某些规则（例如“使用粉色表格代替黄色表格”）也是有用的。

关于这些类别需要注意的一个重要点是，它们是层次化的。例如，每位法务秘书都是秘书，每位营销人员都是员工。在紧急情况下，你可以要求法务秘书在短期内担任标准秘书工作，因为法务秘书就是秘书。我们把这种连接称为“是一个”关系（is-a-relationship）。

> **是一个关系 (Is-a Relationship)**

两个类别之间的层级连接，其中一种类型可以被视为另一种类型的专门版本。

“是一个”关系类似于角色的概念。法务秘书可以承担秘书的角色和员工的角色。子类别的成员可以增加或更改更大部分类的行为。例如，法务秘书在秘书角色中增加了填写法律简报的能力，并可能会改变听写记录的方式。

当将这些概念应用于编程时，每组员工都可以表示作一个类。不同的员工组代表了一组通过“是一个”关系连接的相关的类。我们把这样的类集合称为继承。

### 继承层次结构

对象类之间的一组层次级关系。

正如你将看到的，继承层次结构在 Java 中被广泛用于将相关的对象类分组，并在它们之间重用代码。

### 扩展类

上一节介绍了层级结构的非编程示例。但作为练习，我们可以编写短小的 Java 类来表示这些职业类别。代码会有点笨拙，但将说明一些重要的概念。让我们假设我们对员工有以下规则：

- 员工每周工作 40 小时。
- 员工年薪为 40,000 美元，营销人员除外，他们的年薪 50,000 美元。
- 员工每年有两周带薪假，律师除外，他们有三周假期。
- 员工使用黄色表格申请休假，律师除外，他们使用特殊的粉色表格。
- 每种类型的员工都有独特的行为：律师知道如何起诉，营销人员知道如何广告，秘书知道听写。

让我们写一个类来表示所有员工的共同行为。（把这比作 20 页的员工手册。）我们将编写名为 `showSalary`、`showVacation` 和 `applyVacation` 的方法来表示这些行为。为了保持简单，每个方法将只打印一个短字符串，例如 40,000 美元的薪水和休假的黄色表格。我们暂时不声明任何字段。以下是 `Employee` 类的代码：

```java
// 一个表示普通员工的类。
public class Employee {
    public void applyVacation() {
        System.out.println("Use the yellow form.");
    }

    public void showHours() {
        System.out.println("I work 40 hours per week.");
    }

    public void showSalary() {
        System.out.println("My salary is $40,000.");
    }

    public void showVacation() {
        System.out.println("I receive 2 weeks vacation.");
    }
}
```

现在，让我们考虑实现 `Secretary` 子类别。如上一节所述，每位 `Secretary` 都是 `Employee`，他们应该保留 `Employee` 拥有的能力。秘书还有一个额外的能力：听写的能力。如果我们把 `Secretary` 写 true 独立的类，它的代码将无法优雅地反映这种关系。我们将被迫重复来自 `Employee` 的所有相同方法。这里是冗余的类：

```java
// 一个表示秘书的冗余类。
public class Secretary {
    public void applyVacation() {
        System.out.println("Use the yellow form.");
    }

    public void showHours() {
        System.out.println("I work 40 hours per week.");
    }

    public void showSalary() {
        System.out.println("My salary is $40,000.");
    }

    public void showVacation() {
        System.out.println("I receive 2 weeks vacation.");
    }

    // 这是唯一增加的行为
    public void takeDictation() {
        System.out.println("I know how to take dictation.");
    }
}
```

`Secretary` 类特有的代码只有其 `takeDictation` 方法。我们真正想要写的是：

```java
public class Secretary {
    // 复制来自 Employee 类的所有方法。

    // 这是唯一增加的行为
    public void takeDictation() {
        System.out.println("I know how to take dictation.");
    }
}
```

### 子类

子类通过 `extends` 关键字继承父类，因为它不仅收敛了父类的状态和行为，还可以添加自己的新状态和行为。子类还可以根据需要将继承的行为替换为新行为，我们将在下一节中讨论这一点。

一个 Java 类只能有一个父类：它无法扩展超过一个类。这被称为单继承。另一方面，一个父类可以有许多子类继承它。

要将一个类声明为另一个类的子类，请在子类头部的末尾放置 `extends` 关键字，后紧跟父类名。通用语法如下：

```java
public class <class name> extends <superclass> {
}
```

我们可以重写 `Secretary` 类以继承 `Employee` 类。这将创建一个关系，使得每个 `Secretary` 都是一个 `Employee`。`Secretary` 对象将继承 `applyForVacation`、`showHours` 和 `showVacation` 方法的副本，因此我们不需要在 `Secretary` 类中编写这些方法。这将消除冗余。

子类添加父类中不存在的新行为是合法且符合预期的。我们之前提到，秘书增加了一种其他员工不具备的能力：速记的能力。我们可以将此功能添加到我们原本为空的 `Secretary` 类中。以下是完整的 `Secretary` 类：

```java
// 代表秘书的类。
public class Secretary extends Employee {
    public void takeDictation() {
        System.out.println("I know how to take dictation.");
    }
}
```

这个新版本的 `Secretary` 类行为与之前显示的较长的类相同。相比于那份两页纸的专门手册，这个类只显示了特定职位类特有的内容。在这种情况下，很容易看出，我们系统中秘书的独特行为是速记。

以下客户端代码可以在我们新的 `Secretary` 类上运行：



```java
public class EmployeeMain {
    public static void main(String[] args) {
        System.out.println("Employee:");
        Employee employee = new Employee();
        employee.applyForVacation();
        employee.showHours();
        employee.showSalary();
        employee.showVacation();
        System.out.println("");
    }
}
```

```java
10  System.out.println("Secretary:");
11  Secretary employee2 = new Secretary();
12  employee2.applyForVacation();
13  employee2.showHours();
14  employee2.showSalary();
15  employee2.showVacation();
16  employee2.takeDictation();
17  }
18)
```

该代码将产生以下输出：

Employee:

Use the yellow vacation form.

I work 40 hours per week.

My salary is $40,000.

I receive 2 weeks vacation.

Secretary:

Use the yellow vacation form.

I work 40 hours per week.

My salary is $40,000.

I receive 2 weeks vacation.

I how to take dictation.

注意，前四个方法对两个对象产生了相同的输出，因为`Secretary`从`Employee`继承了这些行为。`Secretary`输出的第五行反映了`takeDictation`方法的新扩展行为。

## 方法重写

我们可以在所有其他类型的`Employee`中使用继承，使`Lawyer`和`Marketer`类成为`Employee`的子类。虽然`Secretary`类仅仅是在标准的`Employee`行为基础上增加了行为，但`Lawyer`和`Marketer`类还需要用自己的行为替换一些标准的`Employee`行为。律师有三周休假，并使用粉色表格申请请假。营销人员的薪水为$50,000，而不是$40,000。

通过在子类中编写相关方法的新版本来替换父类行为是合法的。子类中的新版本将替换从`Employee`继承的版本。这种替换父类行为的思想被称为重写（overriding）。

## 重写（Override）

实现一个方法的新版本以替换本应从父类继承的代码。

重写不需要特殊的语法。要重写一个方法，只需在子类中编写你想要替换的方法即可。不需要特殊的语法，但方法的名字和签名必须与父类中的方法完全匹配。

### 9.1 继承基础

以下是继承`Employee`并重写相关方法的`Lawyer`和`Marketer`类。

```java
// 代表律师的类。
public class Lawyer extends Employee {
    public void applyForVacation() {
        System.out.println("Use the pink vacation form.");
    }

    public void showVacation() {
        System.out.println("I receive 3 weeks vacation.");
    }

    public void sue() {
        System.out.println("I'll see you in court!");
    }
}
```

```java
// 代表营销人员的类。
public class Marketer extends Employee {
    public void advertise() {
        System.out.println("Act now, while supplies last!");
    }

    public void showSalary() {
        System.out.println("My salary is $50,000.");
    }
}
```

以下客户端程序使用了我们的`Lawyer`和`Marketer`类：

```java
public class EmployeeMain{
    public static void main(String[] args) {
        System.out.println("Lawyer:");
        Employee employee = new Lawyer();
        employee.applyForVacation();
        employee.showHours();
        employee.showSalary();
        employee.showVacation();
        employee.sue();

        System.out.println("Marketer:");
        Marketer employee2 = new Marketer();
        employee2.applyForVacation();
        employee2.showHours();
        employee2.showSalary();
        employee2.showVacation();
        employee2.advertise();
    }
}
```

该程序产生以下输出：

Lawyer:

Use the pink vacation form.

I work 40 hours per week.

My salary is $40,000.

I receive 3 weeks vacation.

I'll see you in court!

Marketer:

Use the yellow vacation form.

I work 40 hours per week.

My salary is $50,000.

I receive 2 weeks vacation.

Act now, while supplies last!

## 第9章 继承与接口

### 多态性

继承类的一个有趣且奇怪的点是，允许父类类型的变量引用其任一个子类的对象。例如，以下是合法的赋值语句：

```java
Employee employee = new Lawyer();
```

在学习基本类型时，我们看到过一种类型的变量可以存储另一种类型的值（例如，`int`值可以存储在`double`变量中）。在这些情况下，发生了类型转换；`int`值在赋值时被自动转换为`double`。

当子类被存储在父类中时，没有发生这种转换。由`employee`引用的对象实际上是一个`Lawyer`，而不是`Employee`对象。如果我们对它调用方法，它的表现就像一个`Lawyer`对象一样。例如，调用：

```java
employee.applyForVacation();
```

产生了以下输出，这是`Lawyer`的行为：

Use the pink vacation form.

这种变量引用子类的能力是面向对象编程中最核心的思想之一。它允许我们编写灵活的代码，以相同的方式与多种类型的对象交互。例如，一个接受`Employee`作为参数、返回`Employee`或创建`Employee`对象数组的方法。在任何这些情况下，我们都可以替换`Secretary`、`Lawyer`或其他`Employee`的子类对象，且代码仍然可以运行。

更重要的是，代码会根据所使用的对象类型而实际不同，因为每个子类都重写并改变了来自父类的某些行为。这种允许相同代码应用于不同类型对象的重要能力被称为多态性（polymorphism）。

### 9.1 继承基础

#### 多态

允许同一段代码用于多种类型的对象，并根据所用对象的实际类型表现出不同的行为。

这里是一个示例测试文件，它以多态的方式将`Employee`对象作为参数传递给静态方法：

```java
public class EmployeeMain3 {
    public static void main(String[] args) {
        Employee empl = new Employee();
        Lawyer law = new Lawyer();
        Marketer mark = new Marketer();
        Secretary sec = new Secretary();

        printInfo(empl);
        printInfo(law);
        printInfo(mark);
        printInfo(sec);
    }

    public static void printInfo(Employee employee) {
        employee.applyForVacation();
        employee.showHours();
        employee.showSalary();
        employee.showVacation();
        System.out.println();
    }
}
```

注意，该静态方法允许我们传递许多不同类型的`Employee`作为参数，并且会根据传递的类型不同产生不同的行为。多态赋予了我们这种灵活性。程序产生如下输出：

使用黄色请假单。

我每周工作40小时。

我的薪水是$40,000。

我有2周的假。

使用粉色请假单。

我每周工作40小时。

我的薪水是$50,000。

我有2周的假。

使用黄色请假单。

我每周工作40小时。

我的薪水是$50,000。

我有2周的假。

使用黄色请假单。

我每周工作40小时。

我的薪水是$40,000。

我有2周的假。

“polymorphism”（多态）一词源于希腊语单词“poly”和“morph”，分别意味着“许多”和“形式”。`printInfo`方法中的代码行具有多态性，因为它们的行为会根据传递作为参数的员工类型而呈现出多种形式。

## 第9章 继承与接口

程序在实际运行之前并不知道该调用`applyVacation`还是`showSalary`。当程序运行到对象方法的调用时，它会检查实际对象以确定调用哪个方法。多年来，这种机制有许多名称，例如后期绑定（late binding）、虚绑定（virtual binding）和分发（dispatch）。

当通过父类的引用向对象发送消息时，只有调用父类中已知的方法才是合。例如，以下代码将无法编译，因为`Employee`类没有`advertise`方法：

```java
// 无法编译
public static void badStuff(Employee e) {
    e.advertise();
}
```

编译器不允许这段代码通过，因为变量`e`在理论上可以指向一个`Employee`对象，也可以指向任何`Employee`子类的对象。实际对象并不保证具有`advertise`方法。

### 9.2 多态的机制

继承和多态为程序中引入了一些复杂的复杂机制和行为。掌握这些机制的一种有效方法是进行练习，解释具有继承关系的程序的行为。这些练习的主要目标是帮助你详细理解 Java 程序执行了哪些内容。

上一节开发的`EmployeeMain3`程序可以作为继承层次结构的模板。通过观察这个模板，可以对实例层级结构提出一个通用问题：按照类的层级关系，如果我们创建了几个不同类型的对象，并在它们上调用各种方法，会产生什么行为？

为了在这种类型的问题中实现多态，我们将被检查的对象存储在一个数组中。在`Employee`层次结构中，将`Lawyer`、`Secretary`或任何其他`Employee`子类的对象作为`Employee[]`元素是合法的。

以下程序产生与上一节的`EmployeeMain3`程序相同的输出：

```java
public class EmployeeMain4 {
    public static void main(String[] args) {
        Employee[] employees = (new Employee(), new Lawyer(),
        new Manager(), new Secretary());

        // 打印每个员工的信息
        for (int i = 0; i < employees.length; i++) {
            employees[i].applyVacation();
            employees[i].showHours();
            employees[i].showSalary();
            employees[i].showVacation();
            System.out.println();
        }
    }
}
```

如果你不理解继承，你可能推断出关于类名层次以及现实世界中员工之间关系的一些信息。所以，让我们这个练习更进一步：我们不再使用具有描述性的类名，而是使用字母，这样就必须阅读代码才能确定类的关系和行为。

假设定义了以下类：

```java
public class A {
    public void method1() {
        System.out.println("A 1");
    }
    
    public void method2() {
        System.out.println("A 2");
    }
    
    public String toString() {
        return "A";
    }
}
```

```java
public class B extends A {
    public void method2() {
        System.out.println("B 2");
    }
}
```

```java
public class C extends A {
    public void method1() {
        System.out.println("C 1");
    }
    public String toString() {
        return "C";
    }
}
```

```java
public class D extends C {
    public void method2() {
        System.out.println("D 2");
    }
}
```

考虑以下使用这些类的客户端代码。它利用了每个类都继承 A（无论是直接还是间接）这一事实，因此当你对数组元素调用方法时，你应该观察到多态性：

```java
public class ABCD {
    public static void main(String[] args) {
        A[] elements = {new A(), new B(), new C(), new D()};
        for (int i = 0; i < elements.length; i++) {
            elements[i].method1();
            elements[i].method2();
            System.out.println();
        }
    }
}
```

## 多态代码绘图

要确定上一节中多态程序的输出，你必须确定当每个类型被打印时会发生什么。开始的方法是为每个类型画一个框列出方法，并用箭头将子类连接到父类（这种图是常用的 UML 类图的简化）。

现在，通过将方法的输出写在名称旁来增强图表。不仅为每个类中定义的方法填充输出，还要为类继承的方法填充。从填充 A 类的方法输出开始。产生的输出是“A 1”。当有人对 A 对象调用`method1`时，产生的输出是“A 1”。当有人对 A 对象调用`method2`时，产生的输出是“A 2”。当有人使用`toString`打印对象时，产生的输出是“A”。将此输出填充在图 9.3 的图表中。

接下来，看 B 类。B 继承 A 的所有行为，但它重写了`method2`输出以显示“B 2”。这意味着你可以以与 A 输出相同的方式在图 9.4 中填充 B 输出，将“A 2”替换为“B 2”。

第三，看 C 类。C 也继承 A 的所有行为，但它重写了`method1`输出以显示“C 1”，并重写了`toString`方法以显示“C”。因此，你图中 c 输出的第二行与 A 输出相同，但你将把第一行的“A 1”替换为“C 1”，并将第三行的“A”替换为“C”，如图 9.5 所示。

以类似的方式处理 d 类。d 继承 c 的所有行为，但它重写了`method2`输出以显示“D 2”。遵循这一模式，你将得到图 9.6 的最终图表。

## 第9章 继承与接口

图 9.6 具有方法输出的 A、B、C 和 D 类

实现此点的另一种方法是为每个类型的方法创建一个行为表格，如表 9.1 所示，将每个类型水平排列，将每个方法名垂直排列。

# 表 9.1 每个类的方法方法输出

| | A | B | C | D |



|---|---|---|---|---|
| toString | A | A | C | C |
| method1 | A 1 | A 1 | C 1 | C 1 |
| method2 | A 2 | B 2 | A 2 | D 2 |

一旦你创建了图表或表格，就可以确定代码的输出。该数组包含一个 A 对象、一个 B 对象、一个 C 对象和一个 D 对象。对于这些中的每一个对象，它都会先打印 `toString` 输出，然后调用 `method1`，接着调用 `method2`，最后打印一个空行。当在对象上调用方法时，你可以通过图表或表格查找该类型该方法的输出。例如，你会发现 A 对象（数组的元素 0）上这些方法的输出如下：

- A
- A 1
- A 2

通过这种方式对所有四个类型使用表格/图表，你将获得练习题的完整输出：

- A
- A 1
- A 2

A

A 1

B 2

C

C 1

A 2

C

C 1

D 2

### 9.3 与父类的交互

之前节中的类演示了方法的继承，但现在你可能想要编写更有意义的类，使用带有字段、方法和构造函数的继承。这些子类需要与它们从父类继承的状态和行为进行更复杂的交互。为了向你展示如何正确执行这种交互，我们需要引入一个名为 `super` 的新关键字。

## 继承的字段

在上一章的案例中，我们构建了一个 `Stock` 类来代表购买的特定股票股份。以下是该类的代码，为了本节，通过删除对非法参数的测试对其进行了缩减：

```java
// 一个 Stock 对象代表股票股份的购买
public class Stock {
    private String symbol;
    private int totalShares;
    private double totalCost;

    // 初始化一个新的没有购买股份的 Stock
    public Stock(String symbol) {
        symbol = symbol;
        totalShares = 0;
        totalCost = 0.0;
    }

    // 返回此股票赚取的总利润或亏损
    public double getProfit(double currentPrice) {
        double marketValue = totalShares * currentPrice;
        return marketValue - totalCost;
    }

    // 记录以给定价格购买的股份
    public void purchase(int shares, double pricePerShare) {
        totalShares += shares;
        totalCost += shares * pricePerShare;
    }
}
```

现在，让我们想象你想创建一个支付股股的股票对象类型。股利是公司向其股东支付的利润分配。股东收到的金额与拥有的股份成正比。并不是所有股票都会支付股利，因此你不想直接将此功能添加到 `Stock` 类中。相反，创建一个名为 `DividendStock` 的新类，继承自 `Stock` 并添加这种行为。

每个 `DividendStock` 对象将从 `Stock` 父类继承 `symbol`、`totalShares` 和 `totalCost`。你只需添加一个字段来记录支付的股利金额即可：

```java
public class DividendStock extends Stock {
    private double dividends; // 股利金额

    ...
```

使用 `dividends` 字段，你可以在 `DividendStock` 类中编写一个方法，允许股东接收每股股利。你的第一个想法可能是编写类似下面的代码，但它无法通过编译：

```java
// 这段代码无法编译
public void payDividend(double amountPerShare) {
    dividends += amountPerShare * totalShares;
}
```

`DividendStock` 无法访问它继承的 `totalShares` 字段，因为 `totalShares` 在 `Stock` 中被声明为 `private`。子类不能直接引用在其父类中声明的 `private` 字段，因此你将得到类似下方的编译器错误：

> DividendStock.java:17: totalShares has private access in Stock

解决方案是使用与这些字段相关的访问器（accessor）或变异器（mutator）来访问或更改它们的值。`Stock` 类没有为 `totalShares` 字段提供公共访问器方法，但你现在可以向 `Stock` 类添加 `getTotalShares` 方法：

```java
// 返回此股票购买的总股份数
public int getTotalShares() {
    return totalShares;
}
```

这里是使用 `Stock` 中的 `getTotalShares` 方法修正后的 `payDividend` 方法版本：

```java
// 记录每股给定金额的股利
public void payDividend(double amountPerShare) {
    dividends += amountPerShare * getTotalShares();
}
```

`DividendStock` 子类允许调用公共的 `getTotalShares` 方法，因此代码运行正常。

## 9.3. 调用父类的构造函数

与其他行为不同，构造函数是不被继承的。你必须为 `DividendStock` 类编写自己的构造函数，当你这样做时，无法访问 `private` 字段的问题就会出现。

`DividendStock` 构造函数应该接受与 `Stock symbol` 相同的参数。它应该具有与 `Stock` 构造函数相同的行为，但还要将 `dividends` 字段初始化为 0.0。以下构造函数的实现似乎是一个不错的开始，但它与 `Stock` 的构造函数是冗余的，且无法成功编译：

```java
// 这种构造函数无法编译
public DividendStock(String symbol) {
    symbol = symbol;
    totalShares = 0;
    totalCost = 0.0;
    dividends = 0.0;
}
```

编译器产生了四个错误：一个是针对尝试访问继承字段行，另一个是关于缺失 `Stock()` 构造器的消息。

> DividendStock.java:5: cannot find symbol

> : constructor Stock()

> location: class Stock

> DividendStock.java:6: symbol has private access in Stock

> DividendStock.java:7: totalShares has private access in Stock

> DividendStock.java:8: totalCost has private access in Stock

第一个问题是，尽管 `DividendStock` 包含了继承自 `symbol`、`totalShares` 和 `totalCost`，但由于它们被声明为 `private`，无法直接引用。第二个问题——缺失 `Stock()` 构造函数是微妙且令人困惑的。子类的构造函数必须调用父类的构造函数。如果不指定这样做，编译器会假设 `Stock` 有一个无参数的 `Stock()` 并尝试通过它来初始化数据。（遗憾错误信息没有更具启发性。）

解决该问题的办法是显式调用接受 `String` 作为参数的 `Stock` 构造函数。Java 使用 `super` 关键字让子类引用父类的行为。要调用父类的构造函数，写下 `super` 关键字，后面跟着构造函数的参数：

`super(<expression>);`

在 `DividendStock` 构造函数的情况下，以下代码解决了问题。使用 `super` 关键字调用父类构造函数，传递相同的 `symbol` 值。这将初始化 `symbol`、`totalShares` 和 `totalCost`。然后将 `dividends` 设置为 0.0：

```java
// 构建一个新的给定符号的股利股票
// 没有购买股份
public DividendStock(String symbol) {
    super(symbol); // 调用 Stock 构造函数
    dividends = 0.0;
}
```

对父类构造函数的调用必须是子类构造函数的第一个语句。如果你反转 `DividendStock` 构造函数的语句顺序，在调用 `super` 之前设置 `dividends`，你将得到如下编译器错误：

```java
// 调用 super 必须是构造函数的第一个语句
dividends = 0.0;
super(symbol); // 调用 Stock 构造函数
```

这里是目前为止的 `DividendStock` 类。该类尚未完成，因为你还没有实现支付股利的行为：

- 一个 `DividendStock` 对象代表一种支付股利的股票购买。
- `public class DividendStock extends Stock {`
- `private double dividends; // 支付的股利金额`
- 构建一个新的给定符号的股利股票
- 没有购买股份
- `public DividendStock(String symbol) {`
- `super(symbol); // 调用 Stock 构造函数`
- `this.dividends = 0.0;`

## 调用重写的方法

为了实现股利支付，首先编写一个名为 `payDividend` 的方法，它接收每股股利金额，并将正确的金额添加到 `DividendStock` 的 `dividends` 字段中。每股金额应与持股数相乘：

```java
// 记录每股给定金额的股利
public void payDividend(double amountPerShare) {
    dividends += amountPerShare * getTotalShares();
}
```

记录的股利支付应被视为股东的利润。`DividendStock` 对象的总利润等于来自

### 9.3 与父类交互

股票价格加上任何股利。其计算方式为：股票的市值乘以当前价格，减去股票的总成本，加上已支付的股利金额。

注意，在前面的代码中，你不需要使用 `super.getTotalShares`。只有在访问父类中重写的方法或构造函数时，才需要使用 `super` 关键字。`DividendStock` 没有重写 `getTotalShares` 方法，因此你可以不使用 `super` 关键字调用它。

由于 `DividendStock` 对象的利润与普通 `Stock` 对象的完全不同，你应该在 `DividendStock` 类中重写 `getProfit` 方法来实现这种行为。一个错误的尝试可能如下所示：

```java
// 此代码无法编译
public double getProfit(double currentValue) {
    double oldValue = totalShares * currentValue;
    return oldValue - totalCost + dividends;
}
```

前面的代码有两个问题。首先，你不能直接引用在 `Stock` 中声明的字段。为了解决这个问题，你可以为每个字段添加访问器方法。第二个问题是代码是冗余的：它重复了之前展示的 `Stock.getProfit` 方法中的每个功能。唯一的新行为是将股利加入总数。

为了消除这种冗余，你可以让 `DividendStock` 的 `getProfit` 方法在计算过程中调用 `Stock` 的 `getProfit` 方法。然而，由于两个方法同名，你必须通过显式告诉编译器你想调用 `Stock` 的版本来消除歧义。同样，你使用 `super` 关键字这样做。

使用 `super` 关键字调用重写方法的语法为：

```java
super.<method name>(<expression>, <expression>, ..., <expression>)
```

下面是修正后的代码，它可以编译并消除了冗余：

```java
// 返回此只股票获得的总利润或亏损
// 包括从股利中利润
public double getProfit(double currentValue) {
    return super.getProfit(currentValue) + dividends;
}
```

这里是完整的 `DividendStock` 类：

```java
// DividendStock 对象代表一个同时也支付股利的
// 股票购买。
public class DividendStock extends Stock {
    private double dividends; // 已支付股利的金额

    // 使用给定的符号构造新的股利股
    // 且未购买股票
    public DividendStock(String theSymbol) {
        super(theSymbol); // 调用 Stock 构造函数
        dividends = 0.0;

    // 返回此只股票获得的总利润或亏损，
    // 包括从股利中利润
    public double getProfit(double currentPrice) {
        return super.getProfit(currentPrice) + dividends;
    }

    // 记录每股给定金额的股利
    public void paidDividend(double amountShare) {
        dividends += amountShare * getTotalShares();
    }
}
```

可以拥有具有多层继承和重写的更深层次继承体系。然而，`super` 关键字只能向上访问一级到最近被重写的方法版本。连续使用多次 `super` 是不法的：你不能进行像 `super.getProfit` 这样的调用。如果你需要解决方案，将通过使用不同的方法名来寻找通变方法。

## 另一个示例：`MeteredPoint`（计点）

让我们考虑扩展一个类，例如编写一个处理人在 2D 空间移动的程序，比如测量人数步数的计步器程序、用于推销员跟踪城市访问销售的应用程序或一个游戏。在编写程序时，拥有一个代表人的位置以及一个总旅行距离的类将是非常用的。

在第 8 章中，我们写了一个 `Point` 类来表示 2D 空间中的一个点。你可以将 `Point` 类扩展为一个名为 `MeteredPoint` 的新类，它添加了 `totalDistance` 测量：

```java
// MeteredPoint 对象代表一个计算
// 移动总距离的点。
public class MeteredPoint extends Point {
    private double totalDistance;
```

`MeteredPoint` 的构造函数需要设置 `x` 和 `y` 字段，就像 `Point` 构造函数所的那样。但 `MeteredPoint` 添加了一个 `totalDistance` 字段，也必须进行设置。调用 `super(x, y)` 设置前两个字段。第三个字段 `totalDistance` 初始化为 0.0。

```java
// 使用给定坐标构造新点
public MeteredPoint(int x, int y) {
    super(x, y);
    totalDistance = 0.0;
}
```

### 9.3 与父类交互

你需要为 `MeteredPoint` 添加的主要行为是每当 `Point` 移动时累加移动距离。坦率地说，`Point` 类中调整点位置的每个代码（包括构造函数和 `translate` 方法）都会调用 `getLocation` 方法。因此，`MeteredPoint` 可以重写 `getLocation` 并添加代码计算点移动了多远。你可以使用勾股定理计算距离并将其添加到 `totalDistance` 中：

```java
public void setLocation(int x, int y) {
    // 累加从旧位置到新位置的移动距离
    int dx = x - getX();
    int dy = y - getY();
    totalDistance += Math.sqrt(dx * dx + dy * dy);
}
```

你必须调用 `getX` 和 `getY` 来检查坐标，因为这些字段在 `Point` 类中是私有的。累加距离后，你必须设置位置。由于这些字段在 `Point` 类中是私有的，设置字段的正确方法是调用父类的版本：

```java
super.setLocation(x, y);
```

在 `getLocation` 方法的最后这样做很重要，这样你就能知道它已经旅行了多远。这里是 `MeteredPoint` 的完整代码：



```java
// MeteredPoint 对象代表一个计算
// 移动总距离的点。
public class MeteredPoint extends Point {
    private double totalDistance;

    // 使用给定坐标构造新点
    public MeteredPoint(int x, int y) {
        super(x, y);
        totalDistance = 0.0;
    }

    // 返回此点的总距离
    public double getTotalDistance() {
        return totalDistance;
    }

    // 将此 MeteredPoint 对象的位置设置为
    // 给定的坐标并累加移动距离
    public void setLocation(int x, int y) {
        // 累加从旧位置到新位置的移动距离
        int dx = x - getX();
        int dy = y - getY();
        totalDistance += Math.sqrt(dx * dx + dy * dy);
        super.setLocation(x, y);
    }
}
```

# 第 9 章 继承与接口

## Object 类

存在一个 `Object` 类，作为所有 Java 类的终极父类，即使那些在头部没有显式声明父类的类。头部中没有 `extends` 类的类在编译时被处理为其头部写着 `Object`。（你可以可选地在类头部写 `extends Object`，但这不是必要的，也不是常见的风格。）

`Object` 类包含了所有对象共有的方法。表 9.2 总结了 `Object` 类的方法。注意，某些方法不是公共的，因此无法从外部调用。

### 表 9.2 Object 类的方法

| 方法 | 描述 |
|---|---|
| `clone()` | 创建并返回对象的副本（不是公共方法） |
| `equals(obj)` | 表示另一个对象是否与对象相等 |
| `finalize()` | Java 在对象销毁时自动调用（不是公共方法） |
| `getClass()` | 返回对象类型的信息 |
| `hashCode()` | 返回与对象相关的数字；用于某些数据结构 |
| `toString()` | 以字符串形式返回对象的状态 |
| `notify(), notifyAll()` | 用于多线程编程的高级方法 |

## 9.4 继承与设计

在第 8 章中我们提到，如果类中没有 `toString` 方法，对象将无法正常打印。例如，我们的 `Point` 类默认打印 `Point@119c082`，是因为我们在 `Point` 类中继承了 `Object` 类中默认的 `toString` 方法。`Object` 类提供了一个通用的 `toString` 输出，适用于每个类：类名后跟着关于对象的内部数值信息。当我们编写自己的 `toString` 方法时，覆盖了这一默认行为。

`equals` 方法在 `Object` 类中也有默认实现。默认的 `equals` 方法只有在两个对象确实是同一个对象时才认为它们相等。当我们编写 `equals` 方法时，我们覆盖了这一行为，使得两个对象具有相同状态时也被认为相等。

在程序中引用 `Object` 类有时是有用的。例如，如果你想写一个可以接受任何对象作为参数的方法，可以声明一个 `Object` 类型的参数：

```java
//此方法可以接受任何对象作为参数
public static void myMethod(Object o) {
```

当然，由于你的参数可以是任何内容，你只允许在该对象上调用 `Object` 类的方法，如 `toString` 或 `getClass`。拥有返回类型为 `Object` 的方法也是合法的。

`Object` 类在 Java 类库中被广泛使用。例如，`PrintStream` 类（`System.out` 的实例）的 `println` 方法接受 `Object` 类型的参数，这允许你将任何对象打印到控制台。

继承影响了你在设计面向对象的编程解决方案时应该使用的思维方式。你应该意识到类与类之间的相似性，并可以通过继承关系和层次结构来捕捉这些相似性。Java 类库的设计者遵循了这些原则，正如我们在本节检查图形子类时看到的。

然而，在某些情况下，使用继承似乎是一个很好的选择，但结果却很糟糕。误用继承可能会引入一些陷阱和问题，我们现在来检查这些问题。

### 继承的误用：Point3D

假设你想编写一个处理三维空间点的程序，例如 3D 游戏、渲染程序或模拟。`Point3D` 类对于存储此类程序中的对象位置将非常有用。

这似乎是一个可以使用继承来扩展现有代码功能的用。许多程序员可能会倾向于扩展 `Point3D` 并简单为 z 坐标添加新代码。这里是继承 `Point` 的最小 `Point3D` 类的快速实现：

```java
// Point3D 对象表示一个 (x, y, z) 位置。
// 这不是一个好的设计。
public class Point3D extends Point {
    private int z;

    // 使用给定的坐标构造一个新的 Point3D
    public Point3D(int x, int y, int z) {
        super(x, y);
        this.z = z;
    }

    // 返回此 Point3D 的 z 坐标
    public int getZ() {
        return this.z;
    }
}
```

从表面上看，这似乎是一个合理的实现。然而，考虑 `Point` 类中定义的 `equals` 方法。它比较两个 `Point` 对象的 x 坐标和 y 坐标，如果满足以下条件则返回 true：

```java
// 返回 o 是否指向与此 Point 具有相同
// (x, y) 坐标的 Point
public boolean equals(Object o) {
    if (o instanceof Point) {
        Point other = (Point) o;
        return x == other.x && y == other.y;
    } else {
        return false;
    }
}
```

你可能也想为 `Point3D` 类编写 `equals` 方法。如果两个 `Point3D` 对象具有相同的 x、y、z 坐标，则它们是相等的。以下是一个正确但在风格上不尽如意的 `equals` 的实现：

```java
// 缺陷版本
public boolean equals(Object o) {
    if (o instanceof Point3D) {
        Point3D p = (Point3D) o;
        return getX() == p.getX() && getY() == p.getY() && z == p.z;
    } else {
        return false;
    }
}
```

上述代码在许多情况下可以正确编译和运行，但当你在比较 `Point` 对象和 `Point3D` 对象时，会发生一个微妙的问题。`Point` 类的 `equals` 方法测试参数是否是 `Point` 的实例，如果不是则返回 false。然而，事实证明 `instanceof` 运算符不仅在变量指向该类型时返回 true，当它指向任何子类时也会返回 true。

考虑 `Point` 类 `equals` 方法中的以下测试：

```java
if (o instanceof Point) {

}
```

如果 `o` 指向 `Point` 对象或 `Point3D` 对象，该测试将评估为 true。`instanceof` 运算符可以被看作是一个“是一个一个”测试，询问变量是否指向可以胜任 `Point` 角色的任何类型。相比之下，`Point3D` 的 `equals` 方法测试参数是否是 `Point3D` 的实例，如果不是则拒绝它。`Point` 不能承担 `Point3D` 的角色（并不是每个 `Point` 都是 `Point3D`），因此如果参数是 `Point` 类型，方法将返回 false。

因此，在 `Point` 和 `Point3D` 对象混合的情况下，`equals` 的行为是不对称的。下面的客户端代码演示了这个问题：

```java
Point p = new Point(12, 7);
Point3D p3d = new Point3D(12, 7, 11);
System.out.println("p.equals(p3d) is " + p.equals(p3d));
System.out.println("p3d.equals(p) is " + p3d.equals(p));
```

该代码产生了以下输出。第一个测试为 true，因为 `Point` 可以接受 `Point3D`，但第二个测试为 false，因为 `Point3D` 不能接受 `Point` 作为其参数：

```
p.equals(p3d) is true
p3d.equals(p) is false
```

这是一个问题，因为 `equals` 方法的合约要求它是对称的。如果你为 `Point3D` 添加更多行为（例如 `setLocation` 方法），可能会遇到其他问题。适当的对象设计会说，在这种情况下 `Point3D` 不应该继承 `Point`，最好从头编写 `Point3D`。

### “是一个”与“有一个”关系

在不使用继承的情况下连接对象的方法。考虑编写 `Circle` 类的任务，每个 `Circle` 对象由中心点和一个半径定义。可能会想让 `Circle` 继承 `Point` 并添加半径字段。然而，在你的类无法替代另一个类的情况下，这是一个糟糕的选择。正如非编程类比所示，大多数人一生中都需要法律服务，但大多数人会选择请律师而不是自己成为律师。

下面的代码提供了 `Circle` 类的可能的初始实现：

```java
// 表示圆形形状
public class Circle {
    private Point center;
    private double radius;

    // 使用给定的半径构造一个新的圆
    public Circle(Point center, double radius) {
        this.center = center;
        this.radius = radius;
    }

    // 返回此圆的面积
    public double getArea() {
        return Math.PI * radius * radius;
    }
}
```

这种设计将 `Circle` 对象呈现为一个单一清晰的抽象，并防止了 `Circle` 和 `Point` 对象的混杂。

### Graphics2D（可选）

继承在 Java 类库中广泛存在。一个著名的例子是 2D 图形的绘制。在第 3 章关于图形的补充材料中，我们引入了一种可以在窗口上绘制形状和线条的笔。当 Java 的设计者想要额外的图形功能时，他们将 `Graphics` 类扩展为更强大的 `Graphics2D` 类。这是继承最常用用法之一的良好示例：扩展并复用现有强大对象的功能。

## 9.4 继承与设计

### 表 9.3 Graphics2D 对象的常用方法

| 方法 | 说明 |
|---|---|
| `rotate(angle)` | 以原点为中心，按弧度角旋转后续绘制的项 |
| `scale(sx, sy)` | 通过给定的因子调整后续绘制的任何项目的大小（10 表示大小相等） |
| `shear(shx, shy)` | 给后续绘制的任何项目添加斜切 |
| `translate(dx, dy)` | 在当前坐标系中通过 (dx, dy) 移动原点 |

为什么 Sun 没有向现有的 `Graphics` 类添加新方法呢？`Graphics` 类已经工作正常，因此 Sun 认为认为对它进行不必要的“手术”并非最佳选择。John Vlissides 是著名的“四人帮”软件工程师团队的一员，他这样描述了这一理念：“我以前见过，而且我还要再说一遍：一个标志——如果说不是良好面向对象设计的标志，那就是你可以通过添加代码而不是通过修补代码来修改和扩展系统。简而言之，变化是自适应的。”

让 `Graphics2D` 扩展可以保留兼容性。向后兼容性是指新代码在无需修改的情况下能够与旧代码正常工作的能力。保持 `Graphics` 不变确保了所有程序都能正常工作，同时又为新程序提供了使用新 `Graphics2D` 功能的选择。

Sun 对 `Graphics2D` 的文档对该类的描述如下：“此 `Graphics2D` 类扩展了 `Graphics` 类，提供了对几何形状、坐标变换、颜色管理和文本布局更精细的控制。它是 Java 平台上用于渲染二维形状、文本和图像的基础类。”具体来说，`Graphics2D` 在你绘图时添加了执行变换（如缩放和旋转）的能力。这些能力可以可以在屏幕上产生一些有趣且有趣的图像。

如果你使用了第 3 章图形辅助材料中的 `DrawingPanel` 类，你之前可能编写过类似下面的语句来访问面板的 `Graphics` 对象：

```java
Graphics g = panel.getGraphics();
```

实际上，`getGraphics` 并没有完全返回一个 `Graphics` 对象，而是一个 `Graphics2D` 对象。然而，由于多态性，你的程序将其视为 `Graphics` 对象是合法的，因为每个 `Graphics2D` 对象都“是” `Graphics` 对象。要将其作为 `Graphics2D` 对象使用，只需说：

```java
Graphics2D g2 = panel.getGraphics();
```

表 9.3 列出了 `Graphics2D` 的一些额外方法。

下面的程序演示了 `Graphics2D`。`rotate` 方法的参数是以弧度为单位的旋转角，而不是度。与其记忆度与弧度之间的转换，我们可以使用 `Math` 类中名为 `toRadians` 的静态方法，它可以将度值转换为相应的弧度值：

```java
// 使用 Graphics2D 绘制旋转正方形的图片。

import java.awt.*;

public class FancyPicture {
    public static void main(String[] args) {
        DrawingPanel panel = new DrawingPanel();
        Graphics g2 = panel.getGraphics();
        g2.translate(100, 120);
        g2.fillRect(-5, -5, 10, 10);

        for (int i = 0; i < 12; i++) {
            g2.setColor(Color.BLUE);
            g2.fillRect(20, 20, 20, 20);
            g2.setColor(Color.BLACK);
            g2.drawString("-", 1, 20, 20);
            g2.rotate(Math.toRadians(30));
            g2.scale(1.1, 1.1);
        }
    }
}
```

图 9.7 显示了程序的输出：

![](img/aea18896a4bced58de45f29f5a93f7b3_555_0.png)

## 9.5 接口

继承是一个非常有用的工具，因为它实现了多态性和代码共享，但它确实有几处局限性。由于 Java 使用单继承，一个类只能扩展一个父类。这使得无法使用继承来为共享多个特征的类建立多个“是一个...”关系，例如一个既是兼职人员又是秘书的员工。在某些情况下，你想要继承和多态性但不希望共享代码，在这种情况下，继承并不是完成任务的工具。

最后，Java 提供了一种名为接口（interface）的结构，它可以在不共享代码的情况下，表示多个类之间的共同超类型。

### 接口

一组类可以承诺实现的方法集合，允许你在代码中以类似的方式处理这些类。

接口类似于类，但它只包含不带体的方法头。类可以实现（implement）一个接口，这意味着该类承诺提供接口中声明的所有方法的具体实现。实现接口的类与接口之间形成了“是一个...”的关系。在一个由多个类实现某个接口的系统中，可以编写多态代码，来处理来自任何实现该接口的类的对象。

接口的一个非编程类比是“认证”。一个人可以获得教师、护士、会计师或医生的认证。要做到这一点，该人必须证明自己具备了这些职业成员所要求的某些能力。雇主会聘佣任何获得适当认证的人，并知道那人能够履行某些工作职责。接口充当了某种认证，类可以通过实现接口中描述的所有行为来满足该认证。代码可以依赖接口具有某些行为。

接口还用于定义对象可以扮演的角色；例如，`Rectangle` 可以实现 `comparable` 接口以表示对象可以进行比较，或者 `Point` 类可以实现 `Cloneable` 接口以表示对象可以复制。

### 形状类的接口

由于这些类之间没有共享代码，我们不应该创建一个公共父类来表示它们的关系。Java 使用单继承，我们在这里不想使用继承。更好的解决方案是编写一个名为 `Shape` 的接口，表示所有形状的功能：获取面积和周长的能力。我们的各种形状类将实现这个接口。

要编写接口，我们需要创建一个与接口同名的文件；例如，我们的 `Shape` 接口存储在 `Shape.java` 中。我们给接口一个头部，用 `interface` 关键字替换 `class`：

```java
public interface Shape {
```



在接口内部，我们编写想要包含的方法头，但不使用大括号编写方法体，只需在每个头部结尾放置一个分号。我们不指定如何实现方法。相反，我们要求任何想要成为形状类的类必须实现这些方法。事实上，接口包含方法体是非法的；接口只能包含方法头部和类常量。

下面是`Shape`接口的完整代码。它声明形状具有计算`double`类型面积和周长的方法：

```java
// 形状类的通用接口。
public interface Shape {
    public double getArea();
    public double getPerimeter();
}
```

### 抽象方法

接口的方法有时被称为抽象方法，因为我们只声明了它们的名称和签名；没有指定它们将如何实现。抽象方法表示了类在实现接口时承诺实现的行为。

表 9.4 每种形状的面积和周长：

| 矩形 | 圆形 | 三角形 |
|---|---|---|
| 面积 | `w*h` | `πr²` | `√(s-a)(s-b)(s-c)` |

![三种形状](img/aea18896a4bced58de45f29f5a93f7b3_556_0.png)

图 9.8 三种形状。

### 9.5 接口

在接口的方法头部上写`public`关键字是可选的。我们选择包含`public`关键字是为了使接口中的声明与类中方法实现的头部匹配。我们用于声明接口的通用语法如下：

```java
public interface <name> {
    public <type> <name>(<name>, <type>, ..., <type> <name>);
    public <type> <name>(<type> <name>, ..., <type> <name>);

    public <type> <name>(<type> <name>, ..., <type> <name>);
}
```

虽然父类和接口看起来相似，但接口不能实例化。在我们的情况下，任何尝试创建新`Shape()`的代码都无法编译。然而，创建`Shape`类型变量是合法的，它可以引用任何实现了`Shape`接口的对象，我们将稍后探讨这一点。

### 实现`Shape`接口

现在我们已经写了一个`Shape`接口，想要将各种形状类与其连接起来。要通过“是一个”（is-a）关系将类连接到我们的接口，我们必须做两件事：

1. 声明该类“实现”（implements）了接口。
2. 在类中实现接口的每个方法。

声明一个类实现接口的通用语法如下：

```java
public class <name> implements <interface> {
}
```

我们必须修改各种形状类的头部，以指示它们实现了`Shape`接口中的所有方法。例如，`Rectangle.java`文件的开头应该如下所示：

```java
public class Rectangle implements Shape {
}
```

当我们声称我们的`Rectangle`类实现了`Shape`时，我们承诺`Rectangle`类将包含`getArea`和`getPerimeter`方法的实现。如果一个类声称实现`Shape`但没有合适的`getArea`或`getPerimeter`方法，它将无法编译。例如，如果我们让`Rectangle`类的体为空并对其进行编译，编译器将给出如下错误：

```text
Rectangle.java:2: Rectangle is not abstract and does not override abstract method getPerimeter()
```

```java
public class Rectangle implements Shape {
    int error
}
```

解决方案是在我们的`Rectangle`类中实现`getArea`和`getPerimeter`方法。我们将通过宽度和高度来定义一个`Rectangle`对象。由于矩形的面积等于其宽度乘以高度，我们将通过相乘其字段来实现`getArea`方法。然后我们将使用周长公式`2 * (w + h)`。这里是实现`Shape`接口的完整`Rectangle`类：

```java
// 表示矩形形状。
public class Rectangle implements Shape {
    private double width;
    private double height;

    // 使用给定尺寸构造新矩形
    public Rectangle(double width, double height) {
        this.width = width;
        this.height = height;
    }

    // 返回此矩形的面积
    public double getArea() {
        return width * height;
    }

    // 返回此矩形的周长
    public double getPerimeter() {
        return 2.0 * (width + height);
    }
}
```

其他形状类也以类似的方式实现。我们将定义一个`Circle`对象具有一个名为`radius`的字段。（我们将放弃本章早在`Circle`类中使用的中心`Point`对象，因为我们在这里不需要它。）我们可以通过将π乘以半径平方来确定面积。为了找到周长，我们将使用方程`2 * π * r`。注意`Rectangle`和`Circle`之间没有公共代码，因此没有必要使用继承。这里是`Circle`类：

```java
// 表示圆形形状。
public class Circle implements Shape {
    private double radius;

    // 使用给定半径构造新圆
    public Circle(double radius) {
        this.radius = radius;
    }

    // 返回此圆的面积
    public double getArea() {
        return Math.PI * radius * radius;
    }

    // 返回此圆的周长
    public double getPerimeter() {
        return 2.0 * Math.PI * radius;
    }
}
```

最后，我们将通过三角形的三边长度`a`、`b`和`c`来指定三角形的形状。三角形的周长仅仅是三边长度之和。`getArea`方法有点复杂，但有一个非常有用的几何公式叫做海伦公式（Heron's formula），它将边长为`a`、`b`、`c`的三角形面积与值`s`（三角形周长的一半）联系起来。

```math
area = \sqrt{s(s-a)(s-b)(s-c)} where s = \frac{a+b+c}{2}
```

这里是`Triangle`类的完整版本：

```java
// 表示三角形形状。
public class Triangle implements Shape {
    private double a;
    private double b;
    private double c;

    // 使用给定边长构造新三角形
    public Triangle(double a, double b, double c) {
        this.a = a;
        this.b = b;
        this.c = c;
    }

    // 使用海伦公式返回此三角形的面积
    public double getArea() {
        double s = (a + b + c) / 2.0;
        return Math.sqrt(s * (s - a) * (s - b) * (s - c));
    }

    // 返回此三角形的周长
    public double getPerimeter() {
        return a + b + c;
    }
}
```

### 接口的作用

接口的主要益处是我们可以使用多态。我们可以创建一个`Shape`数组，将`Shape`作为参数传递，从方法返回`Shape`等。以下程序使用了`Shape`：

```java
// 展示多态。
public class Shapes {
    public static void main(String[] args) {
        Shape[] shapes = new Shape[3];
        shapes[0] = new Rectangle(1, 2);
        shapes[1] = new Circle(2);
        shapes[2] = new Triangle(3, 4, 5);

        for (int i = 0; i < shapes.length; i++) {
            System.out.println("area=" + shapes[i].getArea()
                    + ", perimeter=" + shapes[i].getPerimeter());
        }
    }
}
```

实现接口的类形成了一个类型。图 9.9 显示了我们的类型。它的方法使用了斜体来强调它们是抽象的。

## 第 9 章 继承与接口

| `Circle` | `Rectangle` | `Triangle` |
|---|---|---|
| `radius` | `width` | `a` |
|  | `height` | `b` |
|  |  | `c` |
| `getArea()` | `getArea()` | `getArea()` |
| `getPerimeter()` | `getPerimeter()` | `getPerimeter()` |

## 9.6 案例研究：设计金融类的层次结构

随着你编写更大、更复杂的程序，你会有更多的类以及更多使用继承和接口的机会。练习设计合理的类型层次结构是非常重要的，这样将来你就能通过将问题拆分为良好的类来解决问题。

在设计面向对象的系统时，你应该问自己以下问题：

- 我应该写哪些类？
- 客户端希望这些对象每个具有什么行为？
- 为了实现这种行为，对象需要存储哪些数据？
- 这些类之间有关系吗？如果是，这种关系的本质是什么？

对这些问题给出良好的答案，加上对必要的 Java 语法的良好掌握，是设计面向对象系统的良好开始。这种过程被称为面向对象设计。

### 面向对象设计（OOD）

将程序或系统建模为一组协作对象的集合，并使用类层次结构通过一组类来实现。

让我们考虑收集个人财务投资信息的问题。在本章和上一章中，我们已经探索了`Stock`（股票）示例，以及用于处理派发股息股票的`DividendStock`（股息股）。但股票不是投资者在财务投资组合中可能拥有的资产类型。其他投资可能包括共同基金、房地产或现金。

如何设计一个投资组合系统？你会编写哪些新类型的对象？请花一点时间考虑这个问题。接下来我们将讨论一个示例设计。

### 设计类

每种类型的资产都应该有自己的类。我们已经有了上一章的`Stock`类以及本章前面的`DividendStock`子类，我们可以添加如`MutualFund`（共同基金）和`Cash`（现金）之类的类。这些类型中的每个对象将代表该类型的单项投资；例如，一个`MutualFund`对象将代表对共同基金的购买，而一个`Cash`对象将代表用户投资组合中的一笔资金。可用类型如图 9.0 所示。这些类型对象中需要哪些数据和行为？请花时间考虑一下。

每种类型的资产都具有某些共同行为：每种资产都应该能够计算其当前市场价值以及利润或亏损（如果有）。不过，不同资产类型的这些值的计算方式也不同。例如，股票的市场价值是购买的总股数乘以每股当前价格，而现金则恰好等于自身的金额。

在数据方面，我们之前决定`Stock`对象应该存储股票代码、购买的股数、所有股票支付的总成本以及股票的当前价格。`DividendStock`还需要存储派付的股息金额。`MutualFund`对象应该存储与`Stock`对象相同的数据，但共同基金可以持有部分份额。`Cash`只需要存储自身的金额。图 9.1 更新了我们的类型图以反映这些数据和行为。

图 9.10 财务类：

| `Stock` | `DividendStock` | `MutualFund` | `Cash` |
|---|---|---|---|
| `symbol` | `symbol` | `symbol` | `account` |
| `totalShare` | `totalShare` | `totalShare: double` | `getMarketValue()` |
| `totalCost` | `totalCost` | `totalCost` |  |
| `currentPrice` | `currentPrice` | `currentPrice` |  |
| `getMarketValue()` | `dividends` | `getMarketValue()` |  |
| `getProfit()` | `getMarketValue()` | `getProfit()` |  |

图 9.1 具有状态和行为的财务类。

资产类型之间有关系吗？因此，也许我们希望在数组中存储和共享个人的资产投资组合。由于它们共享相似的功能，能够以相同的方式对待任何资产将非常方便。例如，每种资产都有市场价值，因此如果能够计算投资者投资组合中所有资产的总市场价值而不必担心每种资产的具体类型，将很好。

一个障碍是不同资产计算其市场价值的方式不同。股票的价值基于当前股价，而现金的市场价值始终等于其金额。这意味着我们应该使用接口来表示“资产”的概念，并且之前列出的每个类都实现了资产接口。我们的接口将要求所有资产都有获取市场价值和利润的方法。接口是一种表达方式：“认为自认为是资产的类必须具有`getMarketValue`和`getProfit`方法。”我们的财务资产接口将保存在名为`Asset.java`的文件中，看起来如下：

```java
// 代表投资者持有的财务资产。
public interface Asset {
    // 资产价值多少
    public double getMarketValue();

    // 在此资产上赚了多少钱
    public double getProfit();
}
```

我们将通过实现`Asset`接口来让各种类证明它们是资产。例如，让我们看看`Cash`类。在之前的`Cash`图中没有写`getProfit`方法，因为现金的价值实际上不会改变，因此它没有利润。为了指示这一点，我们可以为`Cash`写一个返回`0.0`的`getProfit`方法。`Cash`类如下：

```java
// 一个 Cash 对象代表投资者持有的金额资金。
public class Cash implements Asset {
    private double amount; // 持有的金额

    // 构造给定金额的现金投资
    public Cash(double amount) {
        this.amount = amount;
    }

    // 返回此现金投资的市场价值，
    // 等于现金金额
    public double getMarketValue() {
        return amount;
    }

    // 因为现金是固定资产，它永远没有任何利润
    public double getProfit() {
        return 0;
    }

    // 将投资的现金金额设置为给定值
    public void setAmount(double amount) {
        this.amount = amount;
    }
}
```

正如本章前面讨论，`DividendStock`与`Stock`非常相似，但它增加了一个股息字段。其他类型呢？`MutualFund`和`Cash`也需要实现。让我们看看如何构建这种层次结构。

每种类型的资产都具有某些共同行为：每种资产都应该能够计算其当前市场价值以及利润或亏损（如果有）。不过，不同资产类型的这些值的计算方式也不同。例如，股票的市场价值是购买的总股数乘以每股当前价格，而现金则恰好等于自身的金额。

在数据方面，我们之前决定`Stock`对象应该存储股票代码、购买的股数、所有股票支付的总成本以及股票的当前价格。`DividendStock`还需要存储派付的股息金额。`MutualFund`对象应该存储与`Stock`对象相同的数据，但共同基金可以持有部分份额。`Cash`只需要存储自身的金额。图 9.1 更新了我们的类型图以反映这些数据和行为。

### 9.6 案例研究：设计金融类的层次结构

```java
public double getMarketValue() {
    return totalShares * getCurrentPrice();
}

// 返回购买的总股数
public int getTotalShares() {
    return totalShares;
}

// 返回此股票赚取的利润
public double getProfit() {
    return getMarketValue() - getTotalCost();
}

// 记录购买指定数量的股份
// 以指定的每股价格购买股票
public void purchase(int shares, double pricePerShare) {
    totalShares += shares;
    addCost(shares * pricePerShare);
}
```



`MutualFund` 类接受了类似的处理，但股份数使用的是 `double` 类型（这两个类之间高度冗余：我们将在下一节中改进它们）：

```java
// MutualFund 对象代表一个基金资产
// 初始版本。
public class MutualFund extends Asset implements Asset {
    private double totalShares;

// 使用指定的代码和每股价格
// 构建一个新的基金投资
public MutualFund(String symbol, double currentPrice) {
    super(symbol, currentPrice);
    totalShares = 0.0;
}

// 返回此基金的市值，
// 即股数乘以每股价格
public double getMarketValue() {
    return totalShares * getCurrentPrice();
}

// 返回此基金的股数
public double getTotalShares() {
    return totalShares;
}

// 返回此基金赚取的利润
public double getProfit() {
    return getMarketValue() - getTotalCost();
}

// 按照指定价格记录购买指定的股份
public void purchase(double shares, double pricePerShare) {
    totalShares += shares;
    addCost(shares * pricePerShare);
    }
}
```

`DividendStock` 给普通的 `Stock` 增加了股息支付金额，这会影响它的市场价值。我们不需要在 `DividendStock` 中重写 `getProfit` 方法，因为 `DividendStock` 已经继承了一个具有如下体的 `getProfit` 方法：

```java
return getMarketValue() - getTotalCost();
```

注意 `getProfit()` 的主体调用了 `getMarketValue()`。`DividendStock` 重写了 `getMarketValue` 方法，一个方便的副作用是，任何其他调用 `getMarketValue` 的方法（如 `getProfit`）也会表现得不同。这是由于多态性；由于 `getMarketValue` 被重写了，`getProfit` 调用了该方法的新版本。由于股息被加上市值中，利润将通过股息被正确计算。

以下代码实现了 `DividendStock` 类：

```java
// DividendStock 对象代表一种支付股息
// 的股票购买；
public class DividendStock extends Stock {
    private double dividends; // 支付的股息金额

    // 使用指定的代码构建新的股息股票
    // 且股份
    public DividendStock(String symbol, double currentPrice) {
        super(symbol, currentPrice); // 调用 Stock 构造函数
        dividends = 0.0;
    }

    // 返回此 DividendStock 的市值，即
    // 普通股票的市值加上任何股息
    public double getMarketValue() {
        return super.getMarketValue() + dividends;
    }

    // 记录每股指定金额的股息
    public void payDividend(double amountPerShare) {
        dividends += amountPerShare * getTotalShares();
    }
}
```

## 抽象类

到目前为止，我们编写了类（状态和行为的具体实现）以及接口（行为的完全抽象声明）。存在一种介于这两个极端情况之间的实体，它允许我们定义一些具体的状态和行为，同时留下一些抽象内容而不定义具体的方法体。这样的实体被称为抽象类。

### 抽象类

一种不能被实例化的 Java 类，而是作为父类用以持有公共代码并声明抽象行为。

你可能已经注意到上一节中 `Stock` 和 `MutualFund` 代码之间存在大量冗余。例如，`getMarketValue` 和 `getProfit` 方法虽然代码完全相同，但它们不能移动到 `ShareAsset` 父类中，因为它们依赖于股数，而股数在每个子类中都是不同的。理想情况下，我们应该以某种方式消除这种冗余。

我们目前的 `ShareAsset` 类也存在一个问题。`ShareAsset` 并不是一个人可以购买的资产类型；它只是一个需要在我们的代码中表示的概念。让人们实际上尝试构造一个 `ShareAsset` 对象是不理想的——我们写这个类是为了消除冗余，而不是为了让客户端实例化它。

我们可以通过将 `ShareAsset` 类指定为抽象类来解决这些问题。在类的头部中编写 `abstract` 将从两个方面修改该类。首先，该类变得不可实例化，因此客户端代码将不允许使用 `new` 关键字构造该类型的对象。其次，该类允许声明没有方法体的抽象方法。然而，与接口不同，抽象类还可以声明字段并实现带有体的方法，因此 `ShareAsset` 类可以保留其现有的代码语法。声明抽象类的语法是：

```java
public abstract class <name> {
    ...
}
```

因此，我们新的 `ShareAsset` 类头部将是：

```java
public abstract class ShareAsset {
    ...
}
```

现在，尝试创建 `ShareAsset` 对象将产生如下的编译器的错误：

```java
ShareAsset is abstract; cannot be instantiated
ShareAsset asset = new ShareAsset("MSFT", 27.46);
// 1 error
```

实际上，本章之前引入的 `Employee` 类也应该是一个抽象类。我们并不特别希望客户端代码构造 `Employee` 对象。没有人仅仅是一个员工；`Employee` 类只是代表一个待扩展的通用类别。

如果需要，允许抽象类实现接口。与其要求 `ShareAsset` 的子类都实现 `Asset` 接口，我们可以指定 `ShareAsset` 实现 `Asset`：

```java
public abstract class ShareAsset implements Asset {
```

```java
// 这将节省 ShareAsset 子类在类头部编写 implements Asset 的工作。
```

`ShareAsset` 没有实现 `Asset` 要求的 `getMarketValue` 方法；该功能留给了它的子类。我们可以在 `ShareAsset` 类中将 `getMarketValue` 声明为抽象方法。在抽象类中声明的抽象方法需要在头部中出现 `abstract` 关键字才能正确编译。否则，其语法与在接口中声明方法相同，用分号代替方法体。

```java
// 返回此资产的当前市值
public abstract double getMarketValue();
```

在抽象类中声明抽象方法的通用语法如下：

```java
public abstract <type> <name> (<type> <name>, ... , <type> <name>);
```

这种设计的另一个益处是，抽象类中的代码实际上可以调用它的任何抽象方法，即使它们在当前文件中没有实现。这是允许的，因为抽象类可以依靠它的子类来实现抽象方法。现在 `ShareAsset` 实现 `Asset`，我们可以将公共的冗余利润代码移动到 `ShareAsset` 并从 `Stock` 和 `MutualFund` 中移除：

```java
// 返回此资产股份赚取的利润
public double getProfit() {
    // 调用抽象 getMarketValue 方法
    // （子类将提供其实现）
    return getMarketValue() - totalCost;
}
```

即使 `ShareAsset` 中不存在该方法，`ShareAsset` 对象也可以从它们的 `getProfit` 方法调用 `getMarketValue`。代码通过编译是因为编译器知道扩展 `ShareAsset` 的任何类必须实现 `getMarketValue`。

以下是 `ShareAsset` 类的最终版本：

```java
// ShareAsset 代表一种具有符号并持有
// 股份的通用资产。
public abstract class ShareAsset implements Asset {
    private String symbol;
    private double totalCost;
    private double currentPrice;
}
```

### 9.6 案例研究：设计金融类别的层次结构

```java
8  // 使用给定的符号和当前价格构建一个新的股票资产
9  // ；
10 public ShareAsset(String symbol, double currentPrice) {
11     this.symbol = symbol;
12     this.currentPrice = currentPrice;
13     totalCost = 0.0;
14 }
15 
16 // 为此资产添加指定金额的成本
17 public void addCost(double cost) {
18     totalCost += cost;
19 }
20 
21 // 返回此资产的每股价格
22 public double getCurrentPrice() {
23     return currentPrice;
24 }
25 
26 // 返回此资产股份的当前市场价值
27 public abstract double getMarketValue();
28 
29 // 返回此资产股份获得的利润
30 public double getProfit() {
31     // 调用抽象的 getMarketValue 方法
32     // (子类将提供其实现)
33     return getMarketValue() - totalCost;
34 }
35 
36 // 返回此资产所有股份的总成本
37 public double getTotalCost() {
38     return totalCost;
39 }
40 
41 // 设置此资产的当前股票价格
42 public void setCurrentPrice(double currentPrice) {
43     this.currentPrice = currentPrice;
44 }
45 }
```

抽象类是一种非常有用的混合体，既包含抽象方法也可以包含非抽象方法。接口中声明的所有方法都隐式是抽象的；如果需要，可以在不使用 `abstract` 关键字的情况下声明。像我们在本章中所做的，不带 `abstract` 关键字的声明是较长显式形式的常用简写。遗憾的是，抽象类不允许这种简写以避免歧义。

`Stock` 和 `MutualFund` 等非抽象类有时被称为具体类（concrete），以便将其与抽象类区分来。我们可以修改 `Stock` 和 `MutualFund` 类来利用 `ShareAsset` 并减少冗余。

以下是 `Stock` 和 `MutualFund` 类的最终版本（`DividendStock` 未修改）。注意，`ShareAsset` 的子类必须实现 `getMarketValue`，否则我们将收到编译错误。

## 第 9 章 继承与接口

```java
// Stock 对象代表对股票的购买。
public class Stock extends ShareAsset {
    private int totalShares;
    // 使用给定的符号和
    // 当前每股价格构建一个新的 Stock
    public Stock(String symbol, double currentPrice) {
        super(symbol, currentPrice);
        totalShares = 0;
    }
    // 返回此股票的市场价值，其
    // 等于总股份数乘以股票价格
    public double getMarketValue() {
        return totalShares * getCurrentPrice();
    }
    // 返回购买的总股份数
    public int getTotalShares() {
        return totalShares;
    }
    // 记录购买指定数量的股份
    public void purchase(int shares, double pricePerShare) {
        totalShares += shares;
        addCost(shares * pricePerShare);
    }
}
```

```java
// MutualFund 对象代表共同基金资产。
public class MutualFund extends ShareAsset {
    private double totalShares;
    // 使用给定的符号
    // 和每股价格构建一个新的共同基金投资
    public MutualFund(String symbol, double currentPrice) {
        super(symbol, currentPrice);
        totalShares = 0.0;
    }
    // 返回此共同基金的市场价值，其
    // 等于股份数乘以每股价格
    public double getMarketValue() {
        return totalShares * getCurrentPrice();
    }
    // 返回此共同基金的股份数
    public double getTotalShares() {
        return totalShares;
    }
    // 记录以指定价格购买指定的股份
    public void purchase(double shares, double pricePerShare) {
        totalShares += shares;
        addCost(shares * pricePerShare);
    }
}
```

## 本章总结

抽象类可以做接口能做的一切事情以及更多，但这并不意味着它们总是比使用接口更好。接口和抽象类之间的一个重要区别是，一个类可以选择实现任意数量的接口，但它只能扩展一个抽象类。这就是为什么接口通常形成继承层次结构的顶端，正如在我们的设计中 `Asset` 没有那做——这允许类成为层次结构的一部分，而不消耗它们唯一的继承关系。

继承允许在两种类型之间创建父子关系。

继承关系中的子（通常称为子类）将接收来自父类（超类）的每个（“继承自的字段和方法的副本。子类“扩展”（extends）超类，因为它可以在从超类继承的字段和方法基础上添加新的字段和方法。

继承可能是一个糟糕的设计选择，而它们之间的“拥有”（has-a）关系（其中一个对象作为字段包含另一个对象）可能是更好的设计。

接口是方法声明的列表。接口指定了方法名、参数和返回类型，但不包含方法体。类可以实现（即承诺实现接口的所有方法）一个接口。

子类可以通过编写自己的版本来重写父类的方法，该版本将替换继承而来的版本。

接口帮助我们实现多态性，以便我们以相同的方式处理多个类。如果两个或多个类实现同一个接口，我们就可以使用其中任何一个并调用接口的任何方法。

抽象类是无法实例化的类。抽象类型不能被构造。抽象类是有用的，因为它可以作为超类，并为其子类定义抽象行为。

抽象类可以包含抽象方法，这些方法已声明但没有主体。抽象类的子类必须实现超类的抽象方法。

`Object` 类表示所有对象的公共超类，并包含每个对象应该具有的行为，例如 `equals` 和 `toString` 方法。

继承在两个类之间提供了“是”的关系。如果两个类关系不密，继承……

## 练习题

1. 什么是代码重用？继承如何帮助代码重用？

2. 方法重载（overloading）和重写（override）有什么区别？

3. 考虑以下类：

```java
public class Vehicle { ... }

public class Car extends Vehicle { ... }

public class SUV extends Car { ... }
```

以下哪些语句是合法的？

- `Vehicle v = new Car();`
- `Vehicle v = new SUV();`
- `Car c = new SUV();`
- `SUV s = new SUV();`
- `SUV s = new Car();`
- `Car c = new Vehicle();`

4. 为本节的员工类系统添加 `LegalSecretary` 类。法律秘书的独特行为是提交法律文件。法律秘书的薪水为 $45000，而不是

5. 使用本节的 A、B、C 和 D 类，以下代码片段的输出是什么？



```java
public static void main(String[] args) {
    A[] elements = {new B(), new D(), new A(), new C()};
    for (int i = 0; i < elements.length; i++) {
        elements[i].method2();
        System.out.println(elements[i]);
        elements[i].method1();
        System.out.println(elements[i]);
    }
}
```

6. 假设定义了以下类：

```java
public class Flute extends Blue {
    public void method2() {
        System.out.println("flute 2");
    }

    public String toString() {
        return "flute";
    }
}
```

```java
public class Blue extends Moo {
    public void method1() {
        System.out.println("blue 1");
    }
}
```

```java
public class Shoe extends Flute {
    public void method1() {
        System.out.println("shoe 1");
    }
}
```

```java
public class Moo {
    public void method1() {
        System.out.println("moo 1");
    }

    public void method2() {
        System.out.println("moo 2");
    }

    public String toString() {
        return "moo";
    }
}
```

以下代码段产生的输出是什么？

```java
public static void main(String[] args) {
    Moo[] elements = {new Shoe(), new Flute(),
        new Moo(), new Blue()};
    for (int i = 0; i < elements.length; i++) {
        System.out.println(elements[i]);
        elements[i].method1();
        elements[i].method2();
        System.out.println(elements[i]);
    }
}
```

7. 使用上一个问题中的类，以下代码段产生的输出是什么？

```java
public static void main(String[] args) {
    Moo[] elements = {new Blue(), new Moo(),
        new Shoe(), new Flute()};
    for (int i = 0; i < elements.length; i++) {
        elements[i].method2();
        elements[i].method1();
        System.out.println(elements[i]);
        System.out.println(elements[i]);
    }
}
```

8. 假设类已经定义：

```java
public class Mammal extends SeaCreature {
    public void method1() {
        System.out.println("warm-blooded");
    }
}

public class SeaCreature {
    public void method1() {
        System.out.println("creature 1");
    }

    public void method2() {
        System.out.println("creature 2");
    }

    public String toString() {
        return "ocean-dwelling";
    }
}

public class Whale extends Mammal {
    public void method1() {
        System.out.println("spout");
    }

    public String toString() {
        return "BIG!";
    }
}

public class Squid extends SeaCreature {
    public void method2() {
        System.out.println("tentacles");
    }

    public String toString() {
        return "squid";
    }
}
```

以下代码段产生的输出是什么？

```java
public static void main(String[] args) {
    SeaCreature[] elements = {new Squid(), new Whale(),
        new SeaCreature(), new Mammal()};
    for (int i = 0; i < elements.length; i++) {
        System.out.println(elements[i]);
        elements[i].method1();
        elements[i].method2();
    }
    System.out.println();
}
```

9. 使用上一个问题中的类，以下代码段产生的输出是什么？

```java
public static void main(String[] args) {
    SeaCreature[] elements = {new SeaCreature(), new Squid(),
    new Mammal(), new Whale()};
    for (int i = 0; i < elements.length; i++) {
        elements[i].method2();
        System.out.println(elements[i]);
        elements[i].method1();
        System.out.println(elements[i]);
    }
}
```

## 9.3节：与父类的交互

10. 解释`this`和`super`关键字之间的区别。它们应该在什么时候使用？

11. 对于接下来的三个问题，考虑以下类：

```java
// 代表大学学生。
public class Student {
    private String name;
    private int age;

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
```

以及以下`Student`子类的部分实现，用于代表大学本科生：

```java
public class UndergraduateStudent extends Student {
    private int year;
    ...
}
```

`UndergraduateStudent`类中的代码可以访问继承自`Student`的`name`和`age`字段吗？它能调用`setAge`方法吗？

12. 为`UndergraduateStudent`类编写一个构造函数，接受一个名称作为参数，并将`UndergraduateStudent`的状态初始化为`age`值为18，`year`值为0。

13. 在`UndergraduateStudent`类中编写`setAge`方法的版本，该方法不仅设置`age`，还将`year`字段加1。

14. 在本节开发的`MeteredPoint`类中添加以下构造函数：

```java
public MeteredPoint() {
```

在原点 (0, 0) 处创建一个新的测量点。在你的解决方案中使用`super`关键字或`this`关键字。

## 第9章 继承与接口

## 9.4节：继承与设计

15. `is-a`（是一个）关系和`has-a`（拥有/包含）关系之间的区别是什么？你在代码中如何创建`has-a`关系？

16. 假设有一个`Rectangle`类，其对象代表二维矩形。`Rectangle`具有`width`和`height`字段，以及相应的构造函数和修改器方法，以及`getArea`和`getPerimeter`方法。

你想在你的系统中添加一个`Square`类。将`Square`变成`Rectangle`的子类是一个好的设计吗？为什么或为什么不是？

17. 假设你将编写一个玩纸牌游戏的程序。考虑设计一个`Card`类和52个子类，对应每种扑克牌（例如`NineOfSpades`和`JackOfClubs`）。这是一种好的设计吗？如果是的话，为什么；如果不是，什么可能是一个更好的设计？

18. 在本节中，我们讨论了为第8章开发的`Stock`类添加分红支付功能。为什么创建一个`DividendStock`类比直接编辑`Stock`类并直接向其添加该功能更优？

## 9.5节：接口

19. 实现一个接口和扩展一个类之间的区别是什么？

20. 考虑以下接口和类：

```java
public interface I {
    public void m1();
    public void m2();
}

public class C implements I {
    // 类 C 的代码
}
```

为了使代码能够成功编译，类`C`的代码必须满足什么条件？

21. 以下接口代码有什么问题？为了让具有颜色的对象，应该修改什么？

```java
public interface Colored {
    Color color;
}

public Color getColor() {
    return color;
}
```

22. 修改第8章的`Point`类，使其实现`Colored`接口并使其具有颜色。（你可能希望创建一个扩展`Point`的`Colored`类。）

23. 在`Shape`接口中声明方法`getSideCount`，返回形状的边数。在所有形状类中实现该方法。

## 9.6节：案例研究：财务类层次的设计

24. 什么是抽象类？抽象类与普通类的相似之处在哪里？与接口相似之处在哪里？

25. 考虑编写一个程序来管理电影集合。有三种类型：剧情、喜剧和纪录片。收藏者想要跟踪每部电影的名称、导演名称和制作日期。某些操作适用于所有电影，每个类型也有特殊操作。你会如何设计类（们）来表示这个电影系统？

## 练习题

1. 对于接下来的四个问题，考虑表示活动票的任务。每张票都有一个唯一的编号和一个价格。有三种类型的票：现场票、预售票和学生票。图9.14展示了这些类型：

- 现场票在活动当天购买，价格为50美元。
- 提前10天或以上购买的预售票价格为30美元，提前少于10天的预售票价格为40美元。
- 学生预售票的价格是普通预售票的一半：10天前15美元，少于10天20美元。

| Ticket |
| --- |
| number |
| Ticket(number) |
| getPrice() |
| toString() |

实现一个名为`Ticket`的类，作为所有类型票的父类。在此类中定义所有公共操作，并指定子类必须实现所有差异操作。不会创建`Ticket`类型的实际对象：每个实际票将是子类类型的对象。

2. 实现一个名为`WalkupTicket`的类来代表现场活动票。现场票也通过编号构造，并且它们的价格为50美元。

## 第9章 继承与接口

3. 实现一个`AdvanceTicket`类来表示预售票。预售票构造时需要一个票号以及购买的提前天数。活动开始前10天或更多购买的预售票价格为$30，而活动开始前少于10天购买的预售票价格为$40。

4. 实现一个`StudentAdvanceTicket`类来表示学生购买的预售票。预售票构造时需要一个票号和购买的提前天数。活动开始前少于10天或更多购买的学生预售票价格为$20（普通预售票的一半）。打印学生票时，字符串应提到学生必须出示其学生证（例如，“Number: 17, Price: 15.0 (ID required)”）。

考虑在鸟类模拟中表示不同类型鸟的任务。每只鸟都有一个 (x, y) 位置和颜色，且每只鸟都能飞行。不同类型的鸟有不同的飞行行为。

编写一个接口`Bird`来表示不同类型的鸟。该接口应具有执行以下操作的方法：

- 获取鸟的颜色。
- 获取鸟的 (x, y) 位置并返回一个`Point`对象。
- 让鸟飞行（每当告诉鸟飞行时，它都会移动一次位置。）

你的`Bird`接口应该能以下客户端程序协同工作：

```java
import java.awt.*;
class Aviary {
    public static final int SIZE = 20;
    public static final int PIXELS = 10;

    public static void main(String[] args) {
        // 创建一个绘制面板
        DrawingPanel panel = new DrawingPanel(SIZE * PIXELS);
        Graphics g = panel.getGraphics();

        // 创建几只鸟
        Bird[] birds = {
            new Cardinal(7, 4),
            new Hummingbird(2, 9),
            new Bluebird(4, 15),
            new Bluebird(8, 1),
            new Vulture(3, 2);
        };

        while (true) {
            // 清屏
            g.setColor(Color.WHITE);
            g.fillRect(0, 0, SIZE * PIXELS, PIXELS);

            // 让每只鸟飞行，并重画鸟
            for (Bird bird : birds) {
                bird.fly();
                g.setColor(bird.getColor());
                Point pos = bird.getPosition();
                g.fillOval(pos.getX() * PIXELS,
                pos.getY() * PIXELS, PIXELS, PIXELS);
            }
            panel.sleep(500);
        }
    }
}
```

6. 编写一个`Cardinal`类来表示红雀。红雀是红色的。红雀的移动是垂直的。红雀正在向上移动。每当告诉红雀飞行时，它会在 y 轴上向上移动一个单位（记住向上是负方向）。如果红雀撞到鸟舍的边缘（y 坐标为 0 或 19），它将转向向相反的方向飞行。

假设鸟舍的大小 20 存储在静态常量`Aviary.SIZE`中。你可能希望引入一个抽象类来存放所有鸟共有的行为。

7. 编写一个`Hummingbird`类来表示蜂鸟。蜂鸟的移动是随机的；每当告诉蜂鸟飞行时，它会在 (0 到 19) 范围内随机选择一个新的随机 (x, y) 位置。

8. 编写一个`Bluebird`类来表示蓝鸟。蓝鸟是蓝色的。蓝鸟的移动呈之字形模式。初始时，蓝鸟以上右、下右、上右、下右的交替模式移动，直到撞到鸟舍的边缘（x 坐标为 19），此时它将转向。随后的`fly`调用将导致鸟向上左、下左、上左、下左移动，直到撞到鸟舍的左边缘。

9. 编写一个`Vulture`类来表示秃鹫。秃鹫是黑色的。秃鹫的移动是逆时针圆形模式。初始时，秃鹫面向向上。秃鹫第一次飞行时，它向上移动一个单位，然后向左转。第二次移动时，它移动一个单位并向下转。第三次移动时，它向下并向右。第四次移动时，它向右移动一个单位并转向向上。这种模式如此循环。

10. 如果你想统计每只鸟飞行的次数，可能需要进行哪些更改？

声明一个接口`Incremental`，表示存储一个可以增加的整数的项。该接口包含一个`increment`方法来增加值，以及一个`getValue`方法来返回值。写完接口后，编写两个实现该接口的类`SequentialIncrementer`和`RandomIncrementer`。`SequentialIncrementer`的值从 0 开始，每次增加时都加 1。`RandomIncrementer`的值从一个随机整数开始，每次增加时都将其更改为一个新的随机数。

## 编程项目



1. 编写一个接口`Incremental`，表示存储一个可以增加的整数的项。该接口包含一个`increment`方法来增加值，以及一个`getValue`方法来返回值。写完接口后，编写两个实现该接口的类`SequentialIncrementer`和`RandomIncrementer`。`SequentialIncrementer`的值从 0 开始，每次增加时都加 1。`RandomIncrementer`的值从一个随机整数开始，每次增加时都将其更改为一个新的随机数。

2. 考虑在鸟类模拟中表示不同类型鸟的任务。每只鸟都有一个 (x, y) 位置和颜色，且每只鸟都能飞行。不同类型的鸟有不同的飞行行为。

编写一个接口`Bird`来表示不同类型的鸟。该接口应具有执行以下操作的方法：

- 获取鸟的颜色。
- 获取鸟的 (x, y) 位置并返回一个`Point`对象。
- 让鸟飞行（每当告诉鸟飞行时，它都会移动一次位置。）

你的`Bird`接口应该能以下客户端程序协同工作：

```java
import java.awt.*;
class Aviary {
    public static final int SIZE = 20;
    public static final int PIXELS = 10;

    public static void main(String[] args) {
        // 创建一个绘制面板
        DrawingPanel panel = new DrawingPanel(SIZE * PIXELS);
        Graphics g = panel.getGraphics();

        // 创建几只鸟
        Bird[] birds = {
            new Cardinal(7, 4),
            new Hummingbird(2, 9),
            new Bluebird(4, 15),
            new Bluebird(8, 1),
            new Vulture(3, 2);
        };

        while (true) {
            // 清屏
            g.setColor(Color.WHITE);
            g.fillRect(0, 0, SIZE * PIXELS, PIXELS);

            // 让每只鸟飞行，并重画鸟
            for (Bird bird : birds) {
                bird.fly();
                g.setColor(bird.getColor());
                Point pos = bird.getPosition();
                g.fillOval(pos.getX() * PIXELS,
                pos.getY() * PIXELS, PIXELS, PIXELS);
            }
            panel.sleep(500);
        }
    }
}
```

# 第 10 章 ArrayList

## 10.1 ArrayList

在日常生活中，我们经常发现自己正在处理各种类型的列表。例如，在 Facebook.com 这样的社交网络网站上，学生被要求列出他们喜欢的乐队。假设有人列出了以下乐队：

Tool, U2, Pink, Floyd, Redefining the Moment

你在第 7 章中看到过，你可以声明一个数组来存储一个值的序列。例如，为了存储上述列表，你可以声明一个长度为 5 的字符串数组。但如果你以后想更改列表（例如，想从列表中移除 Tool 和 U2）会发生什么呢？你必须进行移动操作，并在数组末尾留下空的数组槽。如果你还想向列表中添加内容，使其最终包含超过五个名字呢？你无法在原始数组中存储超过 5 个值，因此你必须构造一个尺寸更大的新数组来存储该列表。

我们大多数人认为列表更具活性。我们不希望担心操作数组时出现的那些低级细节。我们希望能够直接说“向列表添加某些内容”或“从列表中删除此项”，并希望列表随着我们添加或删除值而随时间伸缩。计算机科学家会说，我们脑海中有一个抽象，它允许我们指定要执行的某些操作（添加、删除），而不必担心这些操作是如何执行的（移动、构造数组）。在内部，每个`ArrayList<E>`对象都使用数组来存储它的值。因此，`ArrayList`提供了与数组相同的快速随机访问。但与数组不同，使用`ArrayList`你可以提出添加或删除值的简单请求，而`ArrayList`会为你处理所有细节：如果你向列表添加值，它会变大数组，并为你处理任何需要的移动操作。

记住，你可以声明不同类型的数组。如果你想要一个`int`类型的数组，你声明一个类型为`int[]`的变量。对于字符串数组，你使用`String[]`类型。这是一种适用于数组的特殊语法，但 Sun 在 Java 5 中引入了一种新机制，允许`ArrayList`类具有几乎相同的灵活性。如果你阅读`ArrayList`的 API 文档，你会发现它实际上被列为`ArrayList<E>`。这是 Java 中泛型类的一个示例。

### 泛型类 (Generic)

如`ArrayList<E>`的类接收一个类型参数来指示将使用什么种类型的值。

`ArrayList<E>`中的 "E" 是 "Element"（元素）的缩写，它表示包含在`ArrayList`中的元素类型。泛型类类似于参数化方法。回想第 3 章，使用参数，你可以定义一组相关的任务，这些任务的区别仅在于高度或宽度等特定特征。在这种情况下，参数是一个类型，它被用于声明另一个类型。类型`ArrayList<E>`代表了一族类型，它们的区别仅在于它们所存储的元素类型：你会使用`ArrayList<String>`来存储一个字符串列表；使用`ArrayList<Point>`来存储一个点列表；使用`ArrayList<Color>`来存储一个颜色列表，依此类推。注意，你永远不会实际声明类型为`ArrayList<>`的东西。对于任何参数，你都必须将 E 替换为特定值，以明确你正在使用的是许多`ArrayList`类型中的哪一个。

### 基础 ArrayList 操作

`ArrayList`类是`java.util`包的一部分，因此要在程序中包含它，你必须包含一个导入声明。构造`ArrayList`的语法比我们之前看到的复杂，因为有类型参数。例如，你如下所示构造一个字符串的`ArrayList`：

```java
ArrayList<String> list = new ArrayList<String>();
```

这段代码构造了一个空的`ArrayList<String>`。这种语法虽然复杂，但如果你记住`<String>`符号实际上是类型的一部分，它就会更容易记忆：这不仅仅是一个`ArrayList`。`ArrayList<String>`（通常读作“字符串的 ArrayList”）。注意类型在声明变量和调用构造函数时是如何出现的：

```java
ArrayList<String> list = new ArrayList<String>();
```

如果你从类型为`ArrayList<String>`的角度考虑，你会发现这行代码与构造像`Point`对象的代码没有区别：

```java
Point p = new Point();
```

一旦你构造了`ArrayList`，就可以通过调用`add`方法向它添加值：

```java
ArrayList<String> list = new ArrayList<String>();
list.add("Tool");
list.add("Phish");
list.add("Pink Floyd");
```

Java 将确保你添加的是适当类型的值。在这种情况下，因为你请求了`ArrayList<String>`，你可以向列表添加字符串。

与简单数组不同，打印`ArrayList`是直观的，因为`ArrayList`类重写了 Java 的`toString`方法。`ArrayList`版本的`toString`会构造一个字符串，其中包含括号内的列表内容，并用逗号分隔值。记住，当你打印对象或将对象连接到字符串时，会调用`toString`方法。因此，你可以使用简单的`println`打印`ArrayList`，如下：

```java
System.out.println("list = " + list);
```

例如，你可以在向列表添加值的同时添加`println`语句：

```java
ArrayList<String> list = new ArrayList<String>();
list.add("Tool");
System.out.println("list = " + list);
list.add("Phish");
System.out.println("list = " + list);
list.add("Pink Floyd");
System.out.println("list = " + list);
```

执行这段代码产生以下结果：

```java
list = []
list = [Tool]
list = [Tool, Phish]
list = [Tool, Phish, Pink Floyd]
```

与简单数组不同，打印`ArrayList`是直观的，因为`ArrayList`类重写了 Java 的`toString`方法。`ArrayList`版本的`toString`会构造一个字符串，其中包含括号内的列表内容，并用逗号分隔值。记住，当你打印对象或将对象连接到字符串时，会调用`toString`方法。

等等，让我重新检查一下删除逻辑。

如果包含第二个语句，这会展示得更清楚：

```java
System.out.println("before remove list = " + list);
list.remove(0);
System.out.println("after 1st remove list = " + list);
list.remove(1);
System.out.println("after 2nd remove list = " + list);
```

这段代码产生：

```java
before remove list = [Tool, Phish, Pink Floyd]
after 1st remove list = [Phish, Pink Floyd]
after 2nd remove list = [Pink Floyd]
```

第一次调用`remove`删除字符串 "Tool"，因为它位于位置 0。但一旦该值被移除，所有元素都会移动：字符串 "Phish" 移动到开头（位置 0），字符串 "Pink Floyd" 移动到位置 1。因此，第二次调用`remove`删除 "Phish"，因为它在那个时刻是位置 1 的值。

## 第 10 章 ArrayList

## 表 10.1 基础 ArrayList 方法

| 方法 | 说明 | ArrayList<String> 示例 |
| --- | --- | --- |
| `add(value)` | 在列表末尾添加给定的值 | `list.add("end");` |
| `add(index, value)` | 在指定的索引处添加值，并将随后的值向右移动 | `list.add(index, value);` |
| `clear()` | 移除列表中的所有元素 | `list.clear();` |
| `get(index)` | 获取指定索引处的值 | `list.get(index)` |
| `remove(index)` | 移除指定索引处的值，并将随后的值向左移动 | `list.remove(index);` |
| `set(index, value)` | 用给定的值替换索引处的值 | `list.set(2, "hello");` |
| `size()` | 返回列表中当前的元素数量 | `list.size()` |

如何移除列表中的所有值呢？在这种情况下，你可以调用`ArrayList`的`clear`方法。

表 10.1 总结了本节介绍的`ArrayList`操作。更完整的列表可以在在线 Java 文档中找到。

## ArrayList 搜索方法

一旦你构建了一个`ArrayList`，你可能对在列表中搜索特定值感兴趣。`ArrayList`类提供了几种机制来实现此操作。如果你只是想知道列表中是否存在某个内容，可以调用`contains`方法，它返回一个布尔值。例如，假设你有一个包含重复项的输入文件`names.txt`，你想去掉这些重复项。该文件可能如下：

```java
Maria Derek Erica
Livia Jack Anita
Kendall Maria Livia Derek
Jamie Jack
Erica
```

你可以构建一个`ArrayList<String>`来存放这些名称，并使用`contains`方法来避免任何重复：

```java
// 移除列表中的重复项
Scanner input = new Scanner(new File("names.txt"));
ArrayList<String> list = new ArrayList<String>();
while (input.hasNext()) {
    String name = input.next();
    if (!list.contains(name)) {
        list.add(name);
    }
}
System.out.println("list = " + list);
```

根据给定的示例输入文件，这段代码将产生以下输出：

```java
list = {Maria, Derek, Erica, Livia, Jack, Anita, Jamie};
```

注意，原始的 13 个名称中只有 8 个出现在此列表中，因为各种重复项已经被消除了。

有时，仅仅知道一个值出现在列表中是不够的。你可能想知道它确切发生在哪里。例如，假设你想写一个方法，将`ArrayList<String>`中某个单词第一次出现的位置替换另一个单词。你可以调用`set`方法来替换值，但你必须知道它在列表中的位置。你可以通过调用`indexOf`方法找到值在列表中的位置。

`indexOf`方法接收一个要搜索的值，并返回该值在列表中第一次出现的位置索引。如果没有找到该值，它将返回 -1。因此，你可以这样写该方法：

```java
public static void replace(ArrayList<String> list, String target, String replacement) {
    int index = list.indexOf(target);
    if (index >= 0)
        list.set(index, replacement);
}
```

注意，这个方法的返回类型是`void`，尽管它改变了`ArrayList`对象的内容。一些初学者认为该方法并没有实际创建一个新的`ArrayList`；它仅仅改变了列表的内容。正如你在数组和其他对象中所看到的，只要你只需要一个参数就能改变对象的当前状态。

你可以使用以下代码测试该方法：

```java
ArrayList<String> list = new ArrayList<String>();
list.add("to");
list.add("be");
list.add("or");
list.add("not");
list.add("to");
list.add("be");
System.out.println("initial list = " + list);
replace(list, "be", "beep");
System.out.println("final list = " + list);
```

这段代码产生了输出：

```java
initial list = {to, be, or, not, to, be}
final list = {to, beep, or, not, to, be};
```

## ArrayList

## 表 10.2 搜索方法

| 方法 | 说明 | ArrayList<String> |
| --- | --- | --- |
| `contains(value)` | 如果给定值出现在列表中则返回 true | `list.contains("hello")` |
| `indexOf(value)` | 返回给定值在列表中第一次出现的索引，未找到则返回 -1 | `list.indexOf("world")` |
| `lastIndexOf(value)` | 返回给定值在列表中最后一次出现的索引，未找到则返回 -1 | `list.lastIndexOf("hello")` |

`indexOf`的变体是`lastIndexOf`。正如其名，该方法返回值的最后一次出现的位置。在某些情况下，你对最后一次出现比第一次出现更感兴趣。例如，如果银行发现了一个客户，它可能想知道姓名和账户号码。表 10.2 总结了`ArrayList`方法。所有的`ArrayList`方法都使用`equals`方法来比较值。

## 完整程序

在继续之前，让我们来看一个完整的程序。搜索引擎如 Google 使用停词。Google 的完整停词列表被认为至少有 25 条目，但我们将选取最明显的 15 个。为了探索停词如何影响文本，我们的程序将读取一个名为`speech.txt`的文件，其中包含了哈姆雷特的独白：

> To be or not to be - that is the question:

Whether 'tis nobler in the mind to suffer

The Slings and arrows of outrageous fortune

Or to take arms against a sea of troubles,



By opposing them.

程序构建停词列表，然后逐词读取文件，打印每个不是停词的词。为了避免大小写问题，停词均为小写，并且我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。输入的每个词都调用小写化方法。这里是完整的：

## 第 10 章 ArrayList

### 10.1 使用 ArrayList

```java
// 此程序构建停词列表并回
// 去掉停词的哈姆特独白。
import java.util.*;
import java.io.*;

public class StopWords {
    public static void main(String[] args)
        throws FileNotFoundException {
        // 构建停词列表
        ArrayList<String> stopWords = new ArrayList<String>();
        stopWords.add("a");
        stopWords.add("the");
        stopWords.add("by");
        stopWords.add("how");
        stopWords.add("in");
        stopWords.add("is");
        stopWords.add("it");
        stopWords.add("of");
        stopWords.add("on");
        stopWords.add("or");
        stopWords.add("that");
        stopWords.add("the");
        stopWords.add("this");
        stopWords.add("to");
        stopWords.add("why");

        // 处理文件，打印所有非停词
        Scanner input = new Scanner(new File("speech.txt"));
        while (input.hasNext()) {
            String next = input.next();
            if (!stopWords.contains(next.toLowerCase())) {
                System.out.print(next + " ");
            }
        }
    }
}
```

## 在 ArrayList 中添加和删除元素

在本节中，我们将探索当向 ArrayList 中间动态添加值或删除值时会出现的一些问题。其结果往往出乎意料，因此值得探索这些常见的陷阱。

考虑以下代码，它创建了一个 ArrayList 并在存储了几个单词：

```java
ArrayList<String> words = new ArrayList<String>();
words.add("four");
words.add("score");
words.add("and");
words.add("seven");
words.add("years");
words.add("ago");
System.out.println(" " + words + "");
```

这段代码会产生以下输出：

```text
words = [four, score, and, seven, years, ago];
```

我们将探索在每个单词前面插入一个波浪号（`"~"`）的问题，这会让列表的大小增加一倍。插入波浪号并不是你所想象的对列表可以执行的最令人兴奋的操作，但我们希望保持简单，以便我们专注于编程问题，而且你会发现，你经常需要执行此类操作。例如，在 Google 中，如果你在搜索词前面加一个波浪号，它会返回不同的搜索结果，包括该词的同义词。搜索“~four--score”得到的结果是仅搜索“~four”结果的 10 倍以上。

在我们的情况下，我们希望将波浪号与单词分开，因此我们想在列表中的每个单词前面插入一个包含波浪号的新字符串。这里是第一次直觉上合理但并不起的尝试：

```java
// 无法正常工作
for (int i = 0; i < words.size(); i++) {
    words.add("~" + words.get(i));
}
```

```java
System.out.println("after loop words = " + words + "");
```

这个循环是标准数组遍历循环的稍微变体。它有一个索引 `i`，其值从 0 开始，每次增加 1。在这种情况下，它在每次循环时都在位置 `i` 插入一个波浪号。问题是循环永远不会结束（如果你足够耐心，你会发现程序最终会以“内存溢出”错误终止）。

循环无法终止是因为 ArrayList 结构的动态性质。让我们仔细思考一下正在发生什么。初始，我们有这个列表，位置 0 处是字符串 `"four"`：

```text
[four, score, and, seven, years, ago];
```

循环第一次执行时，我们在位置 0 插入一个波浪号。为了给位置 0 处的波浪号留出空间，ArrayList 必须将所有其他值向右移动一格。结果是字符串 `"four"` 最终位于位置 1：

```text
[~four, score, and, seven, years, ago];
```

然后我们回到 `for` 循环，将 `i` 增加到 1，并在位置 1 插入一个波浪号。但由于单词 `"four"` 目前位于位置 1，这第二个波浪号进入了单词 `"four"` 前面，将其移动到位置 2：

### 10.1 ArrayLists

```text
[~ four, score, and, seven, years, ago]
```

我们再次循环，将 `i` 增加到 2 并在该位置插入一个波浪号，这又是在单词 `"four"` 前面：

```text
[~ ~, four, score, and, seven, years, ago]
```

这种情况会无限持续，因为我们不断在列表第一个单词前面插入波浪号。`for` 循环测试 `i` 是否小于列表的大小，但由于列表在不断增长，大小一直在增加。因此，这个过程将一直下去，直到所有可用内存耗尽。

为了修复这个问题，我们必须考虑到在位置插入波浪号会将所有内容向右移动。因此，在循环的下一次迭代中，我们希望处理向右两个位置，而不是向右一个位置。我们可以通过简单更改 `for` 循环的更新部分来修复代码；将 `i` 增加 2 而不是增加 1：

```java
for (int i = 0; i < words.size(); i += 2) {
    words.add(i, " ");
}
System.out.println("after loop words = " + words);
```

当我们执行这个版本的代码时，我们得到以下输出：

```text
after loop words = [~ four, ~, score, ~, and, ~, seven, years, ~, ago]
```

另一个例子，让我们考虑我们需要什么样的代码来撤销此操作。我们想编写代码从列表中删除每隔一个值——从第一个值开始——也就是说，即当前位于索引 0、2、4、6 和 10 的那些值。这可能会引导我们编写如下代码：

```java
// 无法正常工作
for (int i = 0; i < words.size(); i += 2) {
    words.remove(i);
}
System.out.println("after second loop words = " + words);
```

查看代码，你可以看到 `i` 从 0 开始，每次增加 2，这意味着它产生了一个偶数值序列（0、2、4 等）。这看起来是正确的，如果不是因为要删除的值在那些索引上的话。但这段代码不起作用。它输出了以下输出：

```text
after second loop words = [~ four, ~, score, ~, seven, ~, ago]
```

再次，问题源于元素动态地从一个位置移动到另一个位置。我们想要删除的第一个波浪号位于索引 0：

```text
[~ four, ~, score, ~, and, ~, seven, years, ~, ago]
```

但一旦我们删除了位置 0 处的波浪号，所有内容都会向左移动一格。由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

如果我们反转循环让它向后运行而不是向前运行，它就能工作，因为：

```text
[four, score, and, seven, years, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

由于我们删除了位置 0 处的波浪号，一切都向左移动一格。由于结果是：

```text
[four, ~, score, ~, and, ~, seven, years, ~, ago]
```

# 第 10 章 ArrayList

```java
for (<name> : <structure>) {
  <statement>;
  <statement>;
  ..
  <statement>;
}
```

因此，上述循环可以重写为：

```java
int sum = 0;
for (String s : list) {
  sum += s.length();
}
System.out.println("Total of lengths = " + sum);
```

你可以将此循环理解为：“对于 list 中包含的每个 String s……”。由于 for-each 循环（增强型循环）的语法如此简单，当你发现自己想要顺序处理存储在列表中的每个值时，就应该使用它。然而，for-each 循环并不适用于复杂的列表问题。例如，使用 for-each 循环无法简单地在列表中进行跳跃访问。你必须从第一个到最后一个顺序处理值。此外，你不能在遍历列表的同时修改该列表。

例如，考虑以下示例代码：

```java
// 这种写法不起作用
for (String s : words) {
  System.out.println(s);
  words.remove(0);
}
```

这段代码打印列表中的每个 String，然后尝试删除列表顶端的值。当你执行这段代码时，程序会抛出 `ConcurrentModificationException`（并发修改异常）。Java 正在告诉你，你不可以在遍历列表的同时（并发地）修改列表。由于此种限制，在前一节中讨论的两个问题都无法使用 for-each 循环解决。

# 包装类（Wrapper Classes）

到目前为止，我们看过的所有 ArrayList 示例都涉及 String 对象的 ArrayList。如果你想创建一个整数列表怎么办？鉴于 `ArrayList<E>` 是一个泛型类，你可能会认为 Java 允许你定义一个 `ArrayList<int>`，但事实并非如此。`ArrayList<E>` 中的 `E` 可以被任何对象或引用类型填充（即类名）。基本数据类型（例如 `int`、`char` 和 `boolean`）不能作为 ArrayList 的类型参数。

相反，Java 定义了一系列包装类，允许你将基本类型数据作为对象存储。

## 10.1 ArrayList

### 包装类（Wrapper Class）

将基本类型数据“包装”成对象的类。

为了理解包装类的作用，请想一下为什么我们经常把糖果装在包装里。糖果可能是粘性的，直接处理很不方便，所以我们把它们放在包装里，让处理起来更方便。当我们想要真正的糖果时，就打开包装把糖果取出来。Java 类遵循一个简单的模型。

例如，考虑简单的整数。它们的类型是 `int`；基本类型不是对象，这意味着我们不能在对象上下文中使用 `int` 类型的值。为了实现这一点，我们必须将每个 `int` 包装成 `Integer` 类型的对象。`Integer` 对象非常简单。它们只有一个字段：一个 `int` 值。当我们构造一个 `Integer` 时，我们传递一个要包装的 `int` 值；当我们想要取回 `int` 时，我们调用名为 `intValue()` 的方法返回该 `int`。

为了理解这种区别，请考虑以下变量声明：

```java
int x = 38;
Integer y = new Integer(38);
```

这段代码在内存中导致以下情况：

基本数据被直接存储（变量 `x` 存储了实际值 38），而对象以引用的形式存储（变量 `y` 存储指向包含 38 的对象的引用）。如果我们想从对象中取出 38（拆包并取出内部的糖果），我们就调用 `intValue()` 方法：

```java
int number = y.intValue();
```

包装类对于本章具有特别的意义，因为你需要一个 `ArrayList<E>`。你无法形成 `ArrayList<int>`，但你可以形成一个 `ArrayList<Integer>`。例如，你可以编写代码将几个整数值放入列表并对它们求和：

```java
ArrayList<Integer> list = new ArrayList<Integer>();
list.add(13);
list.add(47);
list.add(15);
list.add(9);
int sum = 0;
for (int n : list) {
  sum += n;
}
System.out.println("list = " + list);
System.out.println("sum = " + sum);
```

这段代码产生以下输出：



```text
list = [13, 47, 15, 9]
      84
```

这段代码利用了 Java 提供的一种机制，用于简化涉及使用包装类的代码：例如，当你的意图看起来很清晰时，Java 会为你转换 `Integer` 值和 `int` 值。鉴于变量 `list` 被声明为 `ArrayList<Integer>`，Java 通常会期望你向列表添加 `Integer` 类型的值。在前面的代码中，你正在添加的是简单的 `int` 值，如下：

```java
list.add(13);
```

在这行代码中，Java 看到你正在将一个 `int` 添加到一个期望 `Integer` 的结构中。由于 Java 知道 `int` 和 `Integer` 之间的关系（每个 `Integer` 只是被包装成对象的 `int`），它将自动将 `int` 值转换为对应的 `Integer` 对象。这个过程被称为装箱（Boxing）。

# 装箱

从基本数据到适当类型的包装对象的自动转换（例如，将 `int` 装箱为 `Integer`）。同样，你不需要执行任何操作来拆箱一个 `Integer` 以获取内部的 `int`。你可以编写如下代码：

```java
int product = list.get(0) * list.get(1);
```

这段代码将列表索引 0 和 1 的元素相乘。这段代码利用了 Java 提供的一种机制，用于简化涉及使用包装类的代码：例如，当你的意图看起来很清晰时，Java 会为你转换 `Integer` 值和 `int` 值。鉴于变量 `list` 被声明为 `ArrayList<Integer>`，Java 通常会期望你向列表添加 `Integer` 类型的值。在前面的代码中，你正在添加的是简单的 `int` 值，如下：

```java
list.add(13);
```

在这行代码中，Java 看到你正在将一个 `int` 添加到一个期望 `Integer` 的结构中。由于 Java 知道 `int` 和 `Integer` 之间的关系（每个 `Integer` 只是被包装成对象的 `int`），它将自动将 `int` 值转换为对应的 `Integer` 对象。这个过程被称为装箱。

# 拆箱（Unboxing）

从包装对象到适当类型的基本数据的自动转换（例如，将 `Integer` 拆箱为 `int`）。同样，你不需要执行任何操作来拆箱一个 `Integer` 以获取内部的 `int`。你可以编写如下代码：

```java
int product = list.get(0) * list.get(1);
```

这段代码将列表索引 0 和 1 的元素相乘。这段代码利用了 Java 提供的一种机制，用于简化涉及使用包装类的代码：例如，当你的意图看起来很清晰时，Java 会为你转换 `Integer` 值和 `int` 值。鉴于变量 `list` 被声明为 `ArrayList<Integer>`，Java 通常会期望你向列表添加 `Integer` 类型的值。在前面的代码中，你正在添加的是简单的 `int` 值，如下：

```java
list.add(13);
```

在这行代码中，Java 看到你正在将一个 `int` 添加到一个期望 `Integer` 的结构中。由于 Java 知道 `int` 和 `Integer` 之间的关系（每个 `Integer` 只是被包装成对象的 `int`），它将自动将 `int` 值转换为对应的 `Integer` 对象。这个过程被称为装箱。

> 注：此处文本中存在多处重复和乱码，已根据上下文逻辑进行了去重整合，如“10.3 wrapper class”等重复翻译部分。

## 10.3 包装类（Wrapper Classes）

| 基本类型 | 包装类 |
| :--- | :--- |
| `int` | `Integer` |
| `char` | `Character` |
| `boolean` | `Boolean` |
| `double` | `Double` |
| `float` | `Float` |
| `long` | `Long` |
| `byte` | `Byte` |

## 10.2 可比较接口（The Comparable Interface）

为了使对象可以排序，类必须实现 `Comparable` 接口。该接口定义了一个 `compareTo` 方法，允许一个对象与另一个对象进行比较。

```java
public class Student implements Comparable<Student> {
    private String name;
    private int grade;

    public Student(String name, int grade) {
        this.name = name;
        this.grade = grade;
    }

    @Override
    public int compareTo(Student other) {
        return this.grade - other.grade;
    }

    @Override
    public String toString() {
        return name + ": " + grade;
    }
}
```

在上面的例子中，`compareTo` 方法根据成绩来比较两个 `Student` 对象。

```java
students.add(new Student("Alice", 90));
students.add(new Student("Bob", 85));
students.add(new Student("Charlie", 95));
Collections.sort(students);
```

这将按学生成绩升序排列。

## Comparable 接口

Java 语言规范保证这段代码对于 `n` 在 –128 到 127 之间的值是有效的，但它对 `n` 的其他值的行为没有提供任何保证。对于其他值，它可能会打印信息，而这种行为在不同的 Java 实现之间可能会发生变化。在 Java 的下一个版本中，代码可能会对 420 输出“equal”，但对于像 420000 这样的值则不会输出。

有人认为，由于装箱（boxing）和拆箱（unboxing）隐藏了底层操作，最好根本不要使用它们。如果装箱和拆箱只是“有时”有效，它们并不简化问题，因为你必须理解它们失效的情况。

## 自然排序与 `compareTo`

我们对许多可以排序的数据都很熟悉。例如，我们习惯于从低到高排列数字，或者按字母顺序排列姓名列表。我们将可以排序的类型描述为具有值的自然排序（natural ordering）。为了具有这种值的排序，类型需要一个定义良好的比较函数，用于指示任意两个值之间的关系。

## 比较函数

一个定义良好的过程，用于在给定一对值的情况下，决定这两个值的相对顺序（小于、等于或大于）。

## 自然排序

由其比较函数施加在类型上的顺序。

并不是所有类型都有自然排序，因为并不是所有类型都有比较函数。例如，在本章中，我们一直在探索如何构建各种 `ArrayList` 对象。你将如何比较两个 `ArrayList` 对象以确定其中一个是否小于另一个？一个 `ArrayList` 小于另一个意味着什么？你可能决定使用列表的长度来确定哪一个较小，但对于两个长度相等但存储不同值的 `ArrayList` 对象，你该怎么办？你不会希望将它们描述为“相等”。我们没有显而易见的方法来对 `ArrayList` 的排序达成共识，因此该类型没有比较函数。结果，我们说 `ArrayList` 类型不具有自然排序。

Java 有一种约定来表示一个类型的自然排序。任何具有此类排序的类型都应该实现 `Comparable` 接口：

```java
public interface Comparable<T> {
    public int compareTo(T other);
}
```

# 第 10 章 ArrayLists

此接口提供了一个类型为 `T` 的第二个泛型。在 `ArrayList` 的情况下，Sun 决定使用字母“E”，它是“Element”（元素）的缩写。在 `Comparable` 的情况下，Sun 使用了字母“T”，它是“Type”（类型）的缩写。

`compareTo` 方法是该类型的比较函数。不能使用布尔返回类型，因为有三个可能的答案：小于、等于或大于。`compareTo` 的约定是对象应该返回：

- 一个负数表示小于关系；
- `0` 表示相等；
- 一个正数表示大于关系。

让我们来看几个例子来帮助你理解。我们已经见过 Java `Integer` 对象用作单个值的包装器。我们知道如何比较 `int` 值以确定它们的相对顺序，因此 `Integer` 类实现了 `Comparable` 接口并不令人意外。考虑以下代码：

```java
Integer x = 7;
Integer y = 42;
Integer z = 7;
System.out.println(x.compareTo(y));
System.out.println(x.compareTo(z));
System.out.println(y.compareTo(x));
```

这段代码从构建三个 `Integer` 对象开始，然后包含了一系列 `println` 语句，报告各种成对比较的结果。

在第一个 `println` 中，我们要求 `x` 与 `y` 进行比较，这涉及将 `int` 值 7 与 `int` 值 42 进行比较。这一对存在小于关系（`x` 小于 `y`），因此该方法返回一个负整数。

在第二个 `println` 中，我们要求 `x` 与 `z` 进行比较，这涉及比较两个 `int` 值 7。这一对存在等于关系（`x` 等于 `z`），所以方法返回 `0`。

在最后一个 `println` 中，我们要求 `y` 与 `x` 进行比较，这涉及将 `int` 值 42 与 `int` 值 7 进行比较。最后一对存在大于关系（`y` 大于 `x`），所以该方法返回一个正整数。

这是代码的实际输出：

值 `-1` 和 `1` 是标准的返回值，但方法不需要返回这些特定的值。例如，考虑一段比较 `String` 值的简单代码：

```java
String x = "hello";
String y = "world";
String z = "hello";
System.out.println(x.compareTo(y));
System.out.println(x.compareTo(z));
System.out.println(y.compareTo(x));
```

这段代码中存在类似的关系：`x` 小于 `y`（`"hello"` 小于 `"world"`），`x` 等于 `z`（两个 `"hello"` 相等），且 `y` 大于 `x`（`"world"` 大于 `"hello"`）。但产生的输出与 `Integer` 示例产生的输出略有不同：

- `-15`
- `0`
- `15`

我们得到的不是 `-1` 和 `1`，而是 `-15` 和 `15`。你并不真的知道这些数字从哪里来——唯一事实是它们是负数还是正数——但对于那些好奇的人来说，`-15` 和 `15` 代表 `char` 类型中字符 `'h'` 和 `'w'` 位置之间的距离（`'w'` 比 `'h'` 晚出现 15 个位置）。

所以比较函数经常返回值 `-1` 和 `1`，但并不总是这样。重要的要点是，“小于”关系由负数表示，而“大于”关系由正数表示。请记住，对于 `int` 或 `double` 类型的 `x` 和 `y`，可以使用 `<` 和 `>` 运算符来比较它们，如下：

```java
int x = 7;
int y = 42;
if (x < y) {
    System.out.println("x less than");
}
```

尽管 `String` 实现了 `Comparable` 接口，但不能使用关系运算符来比较字符串。以下代码无法编译：

```java
// 不能这样比较对象
String s1 = "hello";
String s2 = "world";
if (s1 < s2) {
    System.out.println("s1 less than");
}
```

相反，调用 `compareTo` 方法，如下：

```java
String s1 = "hello";
String s2 = "world";
if (s1.compareTo(s2) < 0) {
    System.out.println("s1 less than");
}
```

在这种情况下可以使用关系运算符，因为 `compareTo` 方法返回一个 `int`。注意，不需要特定的值 `-1`，因为对于小于关系保证得到一个负值。表 10.4 总结了实现 `Comparable` 接口对象的比较方法。

## 实现 Comparable

许多标准的 Java 类（如 `String`）都实现了 `Comparable` 接口。你也可以让自己的类实现该接口。实现 `Comparable` 接口可以使用 Java 类库提供的成品解决方案。例如，有用于排序列表和加速搜索的方法。许多功能将在下一章讨论。

作为一个相当简单的例子，让我们探索一个可以用于跟踪日历日期的类。这个想法是跟踪特定的月份和日期，但不跟踪年份。例如，美国每年在 7 月 4 日庆祝独立日。同样，一个机构可能想要一份员工生日的列表，但其中不包含关于他们年龄的信息。

我们可以通过一个具有两个字段的类来实现，用于存储月份和日期：

```java
public class CalendarDate {
    private int month;
    private int day;

    public CalendarDate(int month, int day) {
        this.month = month;
        this.day = day;
    }

    // 其他方法
}
```

记住，要实现接口，你需要在类头中包含一个额外的标记。实现 `Comparable` 接口稍微有点挑战性，因为它是一个泛型接口（`Comparable<T>`）。我们不能简单地说：

```java
// 不正确
public class CalendarDate implements Comparable {
}
```

在这里，我们将 `T` 替换为 `CalendarDate`。每当你实现 `Comparable` 时，你都在比较来自同一类的两个值。因此，名为 `CalendarDate` 的类应该实现 `Comparable<CalendarDate>`。如果你查看 `Integer` 类的头部，你会发现它实现了 `Comparable<Integer>`。同样，`String` 类实现了 `Comparable<String>`。因此，我们需要将头部更改为：

```java
public class CalendarDate implements Comparable<CalendarDate> {
}
```

当然，仅声称实现接口是不够的。我们还必须包含适当的方法。在这种情况下，`Comparable` 接口只有一个方法供我们包含：

```java
public interface Comparable<T> {
    public int compareTo(T other);
}
```

由于我们用 `CalendarDate` 代替了 `T`，我们需要写一个接受 `CalendarDate` 类型参数的 `compareTo` 方法：

```java
public int compareTo(CalendarDate other) {
}
```

## 10.4 值比较总结

| 关系 | 原始数据（`int`、`double` 等） | 对象（`Integer`、`String` 等） |
| --- | --- | --- |
| 小于 | `if (x < y) {`<br>`}` | `if (x.compareTo(y) < 0) {`<br>`}` |
| 小于等于 | `if (x <= y) {`<br>`}` | `if (x.compareTo(y) <= 0) {`<br>`}` |
| 等于 | `if (x == y) {`<br>`}` | `if (x.compareTo(y) == 0) {`<br>`}` |
| 不等于 | `if (x != y) {`<br>`}` | `if (x.compareTo(y) != 0) {`<br>`}` |
| 大于 | `if (x > y) {`<br>`}` | `if (x.compareTo(y) > 0) {`<br>`}` |
| 大于等于 | `if (x >= y) {`<br>`}` | `if (x.compareTo(y) >= 0) {`<br>`}` |

## 比较 `CalendarDate`

现在我们必须弄清楚如何比较日期。每个 `Date` 将具有存储月份和日期的字段。在日历中，月份高于日期。如果我们想比较 1 月 31 日（1/31）和 4 月 5 日（4/5），我们不在乎 5 在 31 之前，我们更关心 1 月在 4 月之前的事实。因此，作为第一次尝试，我们可以这样写方法：

```java
// 不起作用
public int compareTo(CalendarDate other) {
    if (month < other.month) {
        return -1;
    } else if (month == other.month) {
        return 0;
    } else { // month > other.month
        return 1;
    }
}
```

这种方法有两个问题。首先，虽然这段代码使用 `if/else` 结构来返回 `-1`、`0` 和 `1` 的标准值，但有更简单的选项可用。我们可以直接返回 `month` 和 `other.month` 之间的差，如果 `month` 小于 `other.month`，结果为负数；如果相等，结果为 `0`；如果 `month` 大于 `other.month`，结果为正数。我们可以将代码简化如下：



```java
// 仍然不起工作
public int compareTo(CalendarDate other) {
    return month - other.month;
}
```

在可能的情况下保持简单是一个好主意，因为这是更优的。它返回的值与之前的版本略有不同，但它同样符合`Comparable`接口的合约。然而，代码仍然存在问题。

虽然在日历中真正的月份比日期重要，但日期也可以很重要。例如，考虑 4 月 1 日 (4/1) 和 4 月 5 日 (4/5)。当前版本的`compareTo`减去月份并返回值 0，表示这两个日期相等相等。然而，这些日期并不相等：4 月 1 日在 4 月 5 日之前。

只有当月份相等时，日期才变得重要。如果月份不同，我们可以使用月份来确定顺序。否则（当月份相等时），我们必须使用日期来确定顺序。这是你在许多任务中都会遇到的常见原则。我们可以这样实现这种策略：

```java
public int compareTo(CalendarDate other) {
    if (month != other.month) {
        return month - other.month;
    } else {
        return day - other.day;
    }
}
```

这段代码似乎永远不会返回 0，但它确实会。假设我们有两个`CalendarDate`对象，都存储了 4 月 5 日 (4/5) 的日期。月份相等，所以我们返回日期之间的差。该差是 0，因此我们返回 0，这正确地指示了两个日期相等。

这是一个带有`compareTo`方法、两个访问方法和一个`toString`方法的完整`CalendarDate`类：

```java
// CalendarDate 类存储关于单个
// 日历日期信息（月份和日期，没有年份）。
public class CalendarDate implements Comparable<CalendarDate> {
    private int month;
    private int day;
    public CalendarDate(int month, int day) {
        this.month = month;
        this.day = day;
    }
    // 将此日期与另一个日期比较。
    // 日期按月份后按日期比较。
    public int compareTo(CalendarDate other) {
        if (month != other.month) {
            return month - other.month;
        } else {
            return day - other.day;
        }
    }
    public int getMonth() {
        return month;
    }
    public int getDay() {
        return day;
    }
    @Override
    public String toString() {
        return month + "/" + day;
    }
}
```

实现`Comparable`接口的主要用处之一是你可以可以使用像`Collections`这样的工具。正如前面提到的，由于`CalendarDate`类实现了`Comparable`，你可以使用`sort`，如下所示：

```java
import java.util.*;
// 简单的程序，创建一个
// 列表并对其进行排序。
public class CalendarUnitTest {
    public static void main(String[] args) {
        ArrayList<Calendar> dates = new ArrayList<>();
        dates.add(new Calendar(2, 22)); // 华盛
        dates.add(new Calendar(10, 30)); // Adams
        dates.add(new Calendar(4, 13)); // 杰斐逊
        dates.add(new Calendar(3, 16)); // 马迪逊
        dates.add(new Calendar(4, 28)); // 门罗

        System.out.println("birthdays = " + dates);
        Collections.sort(dates);
        System.out.println("birthdays = " + dates);
    }
}
```

此程序产生输出：

```text
birthdays = [2/22, 10/30, 4/13, 3/16, 4/28]

birthdays = [2/22, 3/16, 4/13, 4/28, 10/30]
```

注意在调用`sort`后日期按增加顺序排列。

## 10.3 案例研究：词汇比较

在本节中，我们将使用`ArrayList`来解决一个复杂的问题。我们将开发一个读取两个文本文件并比较它们的词汇的程序。特别是，我们将确定每个文件中使用的单词并计算它们的重叠部分。人文科学的研究人员经常进行此类比较来回答诸如“莎士比亚真的写过戏剧吗？”的问题。

正如我们大多数案例研究一样，我们将分阶段开发程序：

- 第一版本将读取两个文件并报告每个文件的唯一单词。在此阶段使用短测试文件。
- 第二版本还将计算两个文件之间的重叠部分（即在两个文件中都出现的单词集）。在此阶段继续使用短测试文件。
- 第三版本将从大型文本文件读取内容，并对结果进行一些分析。

### 版本 1：计算词汇

我们编写的程序在比较大型输入文件时才有趣，但在开发程序期间，使用短输入文件会更容易，这样我们可以轻松地检查是否得到了正确答案。使用短输入文件意味着我们不需要担心执行时间。当我们使用大型输入文件且程序执行很长时间时，很难知道程序是否会结束执行。如果我们用短输入文件开发程序，我们就会知道它不应该花费很长时间。如果我们不小心在程序中引入了无限循环，我们会立即知道问题出在我们的代码上，而不是因为我们有大量数据要处理。

## 10.3 案例研究：词汇比较

### 你知道吗？

### 为什么`compareTo`不只返回 -1、0 和 1？

正如之前讨论的，像`Integer`这样的类型在调用`compareTo`时会返回 -1、0 和 1。这些是`compareTo`返回的标准值，因为它们对应于数学中一个被称为符号函数的函数（有时缩写为“sgn”）。然而，像`String`等其他类型并不返回这些标准值。你可能会奇怪，为什么 Sun 不要求所有类在调用`compareTo`时都返回 -1、0 和 1。

对此问题的答案之一是，Java 没有一种方便的三元类型。对于任何二元决策，我们都可以使用`boolean`作为返回类型。但如果我们想精确返回三个不同值中的其中一个，该返回什么呢？并没有包含三个值的定义类型，因此从某种意义上说，使用 Sun 的规则——任何负数都可以，任何正数都可以——更为诚实。假设 Sun 说`compareTo`应该返回 -1、0 和 1，那么当有人写了一个返回其他值的`compareTo`时，会发生什么？理想情况下，任何调用`compareTo`的代码在遇到非法返回值时都会抛出异常，但通过规定所有负数被解释为一种方式，所有正数被解释为另一种方式，而 0 被解释为第三种，Sun 为`int`类型的所有值提供了完整的定义，这使得程序员更容易使用`compareTo`方法。

`compareTo`以这种方式运行的第二个原因是，许多任务可以很容易地通过这种方式表达。我们看到，简化的`Date`返回月份差（当月份不相等时）或天数（当月份相等时）。这种模式出现在很多地方。例如，`String`类使用字典序（也称为“字典”顺序或“字母”顺序）。要确定两个`String`之间的关系，我们通过扫描它们来找到第一对不同的字母。例如，如果你在比较“nattering”和“naboobs”，你会发现第一对不同的字符是第三对（“nat . . . ” 对比 “nab . . . ”）。然后你将返回字符值之差（'t' - 'b'）。如果你没有找到这样的对字符，就返回长度之差。例如，根据长度，“nattering”将被认为大于“nat”。

`String`类的`compareTo`行为可以用以下伪代码描述：

```text
在对应位置上寻找一对不同的字符。

if (存在这样的字符对) {
    返回两个字符之间的差异。
}

返回两个长度之间的差异。
```

注意，这种方法在恰当的情况下返回了 0，即当没有不同的字符部分且字符串长度相同时。允许返回任何负整数表示“小于”以及返回任何正整数表示“大于”的灵活性，使得实现这种方法变得更容易。

不指定`compareTo`返回值的最后一个原因是：通过采用不那么严格的规则，Sun 允许程序员编写更快的`compare`方法。`String`类中的`compare`方法是最经常被调的方法之一。各种数据比较都是建立在`String`比较上的，执行排序数千条记录的任务将导致对`String`类的`compareTo`方法调用数千次。因此，该方法运行快速非常重要。我们不希望通过要求它始终返回 -1、0 或 1 来不必要的增加代码复杂度。

我们将使用一首流行童歌的前两段作为输入文件。我们将创建一个名为`test1.txt`的文件，其中包含以下文本：

- The wheels on the bus go Round round
- Round and round.
- Round and round.
- The wheels on the bus go Round round
- All through the town.

以及一个名为`test2.txt`的文件，其中包含以下文本：

- The wipers on the bus go Swish, swish, swish,
- Swish, swish, swish,
- Swish, swish, swish.
- The wipers on the bus go Swish, swish, swish,
- All through the town.

我们需要用`Scanner`打开这些文件中的每一个。因此我们的`main`方法将开始：

```java
Scanner in1 = new Scanner(File("test1.txt"));

Scanner in2 = new Scanner(File("test2.txt"));
```

然后，我们将计算每个文件中包含的唯一词汇。我们可以将其存储在`ArrayList<String>`中。由于每个文件的操作是相同的，编写一个调用两次的单一方法是有意义的。该方法应该接受`Scanner`作为参数，并将其转换为包含词汇的`ArrayList<String>`。因此，在打开文件后，我们可以执行以下代码：

```java
ArrayList<String> list1 = getWords(in1);

ArrayList<String> list2 = getWords(in2);
```

这个初始版本旨在尽可能简单，所以当我们计算出每个文件的词汇后，只需简单地报告出来：

```java
System.out.println("list1 = " + list1);

System.out.println("list2 = " + list2);
```

这个版本的程序的困难工作需要在编写`getWords`方法时完成。它实际上应该从`Scanner`读取所有单词，构建一个包含这些单词的`ArrayList<String>`并消除任何重复项。我们可以轻松地实现这一点。

## 10.3 案例研究：词汇比较

```text
构建一个新的空列表。

将第一个单词添加到新列表中。

for (每个 i) {
    if (i 处的值不等于 i-1 处的值) {
        添加 i 处的值；
    }
}
```

这可以相当直接地转换为实际代码，但我们必须小心让`i`从 1 开始而不是 0，因为在循环中，我们将每个单词与它前面的一个单词进行比较，而第一个单词前面没有任何内容。我们还必须小心调用`ArrayList`的`get`方法来获取单个值，并使用`equals`方法来比较字符串的相等性：

```java
ArrayList<String> result = new ArrayList<String>();

result.add(words.get(0));

for (int i = 1; i < words.size(); i++) {
    if (!words.get(i).equals(words.get(i-1))) {
        result.add(words.get(i));
    }
}
```

这段代码仍然存在一个问题：如果输入为空，没有第一个单词可以添加到新列表中。因此，我们需要一个额外的`if`语句来确保在第一个列表为空时，不会尝试向新列表添加值。

将所有这些更改整合在一起，我们得到了以下程序：

```java
1 // 词汇程序的第一个版本，读取两个文件并
2 // 确定每个文件中唯一的单词。
3
4 import java.util.*;
5 import java.io.*;
6
7 public class Vocabulary {
8     public static void main(String[] args)
9         throws FileNotFoundException {
10        Scanner in1 = new Scanner(new File("test1.txt"));
11        Scanner in2 = new Scanner(new File("test2.txt"));
12
13        ArrayList<String> list1 = getWords(in1);
14        ArrayList<String> list2 = getWords(in2);
15
16        System.out.println("list1" + " = " + list1);
17        System.out.println("list2" + " = " + list2);
18     }
19
20     public static ArrayList<String> getWords(Scanner input) {
21         // 读取所有单词并排序
22         ArrayList<String> words = new ArrayList<String>();
23         while (input.hasNext()) {
24             String next = input.next().toLowerCase();
25             words.add(next);
26         }
27
28         Collections.sort(words);
29     }
30
31     // 将唯一的单词添加到新列表并返回
32     ArrayList<String> result = new ArrayList<String>();
33     if (words.size() > 0) {
34         result.add(words.get(0));
35         for (int i = 1; i < words.size(); i++) {
36             if (!words.get(i).equals(words.get(i - 1))) {
37                 result.add(words.get(i));
38             }
39         }
40     }
41     return result;
```

该程序产生了以下输出：

- list1 = [all, and, bus, go, on, round, round., the, through, town., wipers]
- list2 = [all, bus, go, on, swish., swish., the, through, town., wipers]

## 版本 2：计算重叠

程序的第一个版本产生了两个包含唯一单词集合的排序`ArrayList`。对于第二个版本，我们想要计算两个单词列表之间的重叠部分并报告出来。这个操作足够复杂，值得单独放在一个方法中。因此，可以在构建两个列表之后，在`main`方法中添加以下行代码：

```java
ArrayList<String> common = getOverlap(list1, list2);
```




程序第二个版本的主要任务是实现`getOverlap`方法。仔细观察第一个版本生成的两个单词列表：

- `list1 = [all, and, bus, go, on, round, round., the, through, town., wipers]`
- `list2 = [all, bus, go, on, swish., swish., the, through, town., wipers]`

人们很擅长寻找匹配，所以你可能已经看出哪些单词是重叠的。两个列表都以`"all"`开始，所以它是重叠的一部分。跳过第一个列表中的单词`"and"`，我们在第一个列表中找到了单词`"bus"`的下一个匹配项。然后我们又与`"go"`和`"on"`两个两个匹配项。两个列表中连续有几个不匹配的单词，随后出现了带有`"the"`的单词，然后是两个匹配项，以及每个列表中的最后一个唯一单词。因此，完整的匹配集如下：

- `list1 = [all, and, bus, go, on, round, round., the, through, town., wipers]`
- `list2 = [all, bus, go, on, swish., swish., the, through, town., wipers]`

我们想设计一个与我们寻找匹配项时的操作平行的算法。想象用左手的手指放在第一个列表的第一个单词上，用右手的手指放在第二个列表的第一个单词上，以跟踪你在每个列表中的位置。我们将比较你所指的单词；根据它们比较的结果，我们将让其中一个或两个向前移动。

- `list1 = [all, and, bus, go, on, round, round., the, through, town., wipers]`
- `list2 = [all, bus, go, on, swish., swish., the, through, town., wipers]`

这现在非常接近实际代码。首先，我们必须确定一个合适的循环条件。我们开始两个索引变量，并在循环中让一个或两个递增。最终，其中一个或两个列表的值将耗尽，当发生这种情况时，就不会有匹配项可以找到。因此，只要两个索引变量还没有到达列表末尾，我们就想继续循环。我们还需要确定如何比较这两个单词。由于`String`类实现了`Comparable`接口，我们可以使用它的`compareTo`方法。最后，我们必须构建一个`ArrayList`来存储重叠部分，并在循环后返回它。

```java
ArrayList<String> result = new ArrayList<String>();

i1 = 0;

i2 = 0;

while (i1 < list1.size() && i2 < list2.size()) {

  int num = list1.get(i1).compareTo(list2.get(i2));

  if (num == 0) {

    result.add(list1.get(i1));

    i1++;

    i2++;

  } else if (num < 0) {

    i1++;

  } else { // num > 0

    i2++;

  }

}

return result;
```

## 10.3 案例研究：词汇比较

将此转换为一个方法并修改`main`以调用该方法并报告重叠，我们得到了程序的以下新版本：

```java
// 第二版本的词汇程序，读取两个文件
// 并报告它们之间的重叠部分。
import java.util.*;
import java.io.*;

public class Vocabulary2 {
    public static void main(String[] args)
        throws FileNotFoundException {

        Scanner in1 = new Scanner(new File("test1.txt"));
        Scanner in2 = new Scanner(new File("test2.txt"));

        ArrayList<String> list1 = getWords(in1);
        ArrayList<String> list2 = getWords(in2);
        ArrayList<String> common = getOverlap(list1, list2);

        System.out.println("list1 = " + list1);
        System.out.println("list2 = " + list2);
        System.out.println("overlap = " + common);
    }

    public static ArrayList<String> getWords(Scanner input) {
        // 读取所有单词并排序
        ArrayList<String> words = new ArrayList<String>();

        while (input.hasNext()) {
            String next = input.next().toLowerCase();
            words.add(next);
        }

        Collections.sort(words);
        return words;
    }

    public static ArrayList<String> getOverlap(
        ArrayList<String> list1, ArrayList<String> list2) {

        ArrayList<String> result = new ArrayList<String>();

        int i = 0;
        int j = 0;

        while (i < list1.size() && j < list2.size()) {
            int num = list1.get(i).compareTo(list2.get(j));

            if (num == 0) {
                result.add(list1.get(i));
                i++;
                j++;
            } else if (num < 0) {
                i++;
            } else { // num > 0
                j++;
            }
        }

        return result;
    }
}
```

它产生了以下输出：

- `list1 = [all, and, bus, go, on, round, round., the, through, town., wheels]`
- `list2 = [all, bus, go, on, swish, swish., the, through, town., wipers]`
- `overlap = [all, bus, go, on, the, through, town,.]`

## 版本 3：完整程序

我们的程序现在可以正确地为两个文件分别构建词汇列表，并计算它们之间的重叠部分。程序的第二个版本打印了三个单词列表，但对于包含数千个不同单词的大文本文件来说，这将非常方便。相反，我们可以报告总体统计数据，包括每个列表中的单词数、重叠单词数以及重叠百分比。

程序还应该至少有一个简短的介绍来解释它的功能，而且我们可以将其写成提示输入文件名，而不是使用硬编码的文件名。

现在似乎也是考虑标点符号的好时机。前两个版本允许单词包含逗号、句号和破折号等标点字符，而我们通常不认为它们是单词的一部分。

我们可以通过告诉`Scanner`忽略输入文件的哪些部分来改进我们的解决方案。`Scanner`对象有一个名为`delimiter`的方法，你可以调用它来告诉`Scanner`使用什么字符将输入文件拆分为标记（tokens）。当你调用该方法时，传递的是一个所谓的正则表达式（regular expression）。正则表达式是描述字符模式的一种极具灵活的方法。在`Scanner`类的 API 页面中，关于它们的文档。

对于我们的目的，我们想要构造一个正则表达式，指示`Scanner`查看我们认为是“单词”一部分的字符。也就是说，我们希望`Scanner`查看字母和撇号。以下正则表达式是一个很好的起点：

```regex
[a-zA-Z']
```

这个正则表达式可以读为“a 到 z 范围内的任何字符或 A 到 Z 范围内的任何字符或撇号”。这是对我们希望`Scanner`包含的字符类型的良好描述。但我们实际上需要告诉`Scanner`忽略哪些字符：我们需要指示它应该使用相反的字符集。此简单的方法是在合法字符列表前面包含一个脱字符（`^`）：

```regex
[^a-zA-Z'-']
```

这个正则表达式可以读为“除 a 到 z 范围、A 到 Z 范围内的字符或撇号以外的任何字符”。尽管如此，这个表达式并不完全，因为可能会连续出现多个字符。例如，可能会有多个空格、破折号或其他标点字符分隔两个单词。我们可以通过在方括号后加上一个加号来指示这一点，表示“一个或多个这些字符的任何序列”：

```regex
[^a-zA-Z'-']+
```

我们将此表达式作为字符串传递给`useDelimiter`调用。我们可以将其添加到`getWords`方法的开头：

```java
public static ArrayList<String> getWords(Scanner input) {
    input.useDelimiter("[^a-zA-Z'-']+");
}
```

以下是一个结合所有这些更改并包含更详细注释的完整程序：

```java
// 此程序读取两个文本文件并比较
// 每个文件中使用的词汇。
import java.util.*;
import java.io.*;

public class Vocabulary3 {
    public static void main(String[] args)
        throws FileNotFoundException {

        Scanner scanner = new Scanner(System.in);

        giveIntro();

        System.out.print("file #1 name: ");
        Scanner in1 = new Scanner(new File(scanner.nextLine()));

        System.out.print("file #2 name: ");
        Scanner in2 = new Scanner(new File(scanner.nextLine()));

        System.out.println("");

        ArrayList<String> list1 = getWords(in1);
        ArrayList<String> list2 = getWords(in2);
        ArrayList<String> common = getOverlap(list1, list2);

        reportResults(list1, list2, common);
    }

    // 从 Scanner 读取单词，转换为小写
    // 返回排序后的单词列表
    public static ArrayList<String> getWords(Scanner input) {
        // 忽略所有字母字符和撇号
        input.useDelimiter("[^a-zA-Z'-']+");

        ArrayList<String> words = new ArrayList<String>();

        while (input.hasNext()) {
            String next = input.next().toLowerCase();
            words.add(next);
        }

        Collections.sort(words);

        // 将唯一单词添加到新列表
        ArrayList<String> result = new ArrayList<String>();

        if (words.size() > 0) {
            result.add(words.get(0));

            for (int i = 1; i < words.size(); i++) {
                if (!words.get(i).equals(words.get(i - 1))) {
                    result.add(words.get(i));
                }
            }
        }

        return result;
    }

    // 前置：list1 和 list2 是排序的，返回
    // list1 和 list2 之间的单词
    public static ArrayList<String> getOverlap(
        ArrayList<String> list1, ArrayList<String> list2) {

        ArrayList<String> result = new ArrayList<String>();

        int i = 0;
        int j = 0;

        while (i < list1.size() && j < list2.size()) {
            int num = list1.get(i).compareTo(list2.get(j));

            if (num == 0) {
                result.add(list1.get(i));
                i++;
                j++;
            } else if (num < 0) {
                i++;
            } else { // num > 0
                j++;
            }
        }

        return result;
    }

    // 后置：向用户解释程序
    public static void giveIntro() {
        System.out.println("此程序比较两个文件，");
        System.out.println("报告每个文件中共同的");
        System.out.println("单词数以及重叠百分比。");
        System.out.println();
    }

    // 后置：报告列表及其重叠统计数据
    public static void reportResults(
        ArrayList<String> list1,
        ArrayList<String> list2,
        ArrayList<String> common) {

        System.out.println("# file 1 words = " + list1.size());
        System.out.println("# file 2 words = " + list2.size());
        System.out.println("# common = " + common.size());

        double pct1 = 100.0 * common.size() / list1.size();
        double pct2 = 100.0 * common.size() / list2.size();

        System.out.println("% of file 1 in overlap = " + pct1);
        System.out.println("% of file 2 in overlap = " + pct2);
    }
}
```

以下是比较莎士比亚《哈姆雷特》和《李尔王》文本的程序执行。

此程序比较两个文件，报告共同的单词数以及重叠百分比。

```text
file #1 name? hamlet.txt
file #2 name? learn.txt

file #1 words = 4874
file #2 words = 4281
common words = 2108

% of file 1 in overlap = 43.24989741485433
% of file 2 in overlap = 49.24083158140621
```

注意这两个文件具有相同数量的唯一单词，其中一半出现在两个文件中。第二次执行比较了赫尔曼·梅尔维的《白鲸》与《哈姆雷特》的文本：

此程序比较两个文件，报告共同的单词数以及重叠百分比。

```text
file #1 name? moby.txt
file #2 name? hamlet.txt

file #1 words = 17305
file #2 words = 4874

common words = 3079
```




`% of file 1 in overlap = 17.792545507038877`

`% of file 2 in overlap = 63.171932704144444`

在这种情况下，显而易见《白鲸》拥有更大的词汇量。结果，《白鲸》中只有一小部分出现在《哈姆雷特》中。但《哈姆雷特》中的大部分单词出现在《白鲸》中。众所周知梅尔维尔崇拜莎士比亚，因此他的小说与莎士比亚的一部剧有如此高的重叠并不并不意外。

正如第 6 章提到的，你可以从 Project Gutenberg 网站（`http://www.gutenberg.org`）获取这些经典文本。

# 章节总结

Java `java.util` 包中的 `ArrayList` 类表示一个使用数组实现的可增长对象列表。你可以使用 `ArrayList` 按照顺序存储对象。每个元素都有一个从 0 开始的索引。

Java 的 for-each 循环可以用于检查 `ArrayList` 的每个元素。在 for 循环执行期间，不能修改该列表。

`ArrayList` 是一个泛型类。泛型类在创建时接受一个数据类型作为参数，例如 `ArrayList<String>`。

当将基本类型作为 `int` 或 `double` 存储到 `ArrayList` 时，必须使用特殊的包装类（如 `Integer` 和 `Double`）声明列表。

`ArrayList` 维护自己的大小以便：可以在列表大小范围内任何索引处添加或删除元素。其他 `ArrayList` 操作还包括 `get`、`clear` 和 `toString()`。

`Comparable` 接口通过其 `compareTo()` 方法为类的对象定义了自然排序。实现了 `Comparable` 的对象可以放入 `ArrayList` 并进行排序。许多常用类型（如 `String` 和 `Integer`）都实现了 `Comparable`，你也可以在自己的类中实现 `Comparable`。

可以使用名为 `contains`、`indexOf()` 和 `lastIndexOf()` 方法对 `ArrayList` 进行搜索。

# 自我检测题

## 10.1: ArrayLists

1. 什么是 `ArrayList`？在什么情况下你应该使用 `ArrayList` 而不是数组？

2. 接下来的五个问题引用以下 `String` 元素：

```java
"It", "was", "a", "stormy", "night"
```

编写代码声明一个包含这些元素的 `ArrayList`。列表的大小是多少？它的类型是什么？

3. 编写代码插入两个额外的元素。"dark" 和 "and" 位于列表的适当位置，生成的 `ArrayList` 结果为：

```java
"It", "was", "a", "dark", "and", "stormy", "night"
```

4. 编写代码将第二个元素的值改为 "IS"，产生如下的 `ArrayList`：

```java
"It", "IS", "a", "dark", "and", "stormy", "night"
```

5. 编写代码从列表中删除任何包含字母 "a" 的 `String`。你的代码运行后，列表内容应为：

```java
"It", "IS", "a", "stormy", "night"
```

6. 编写代码声明一个持有 2 的前 10 个倍数的 `ArrayList`：0, 2, 4, ..., 18。使用循环为列表填充正确的元素。

7. 编写一个方法 `maxLength`，接收一个 `ArrayList<String>` 作为参数并返回其中最字符串的长度。如果你的方法接收到一个空 `ArrayList`，它应该返回 0。

8. 编写代码打印一个 `String` 列表是否包含值 "IS"。不要使用循环。

9. 给第 3 题的 `ArrayList`，编写代码打印列表包含值 "stormy" 的索引以及包含 "dark" 的索引。不要使用循环。

10. 给第 3 题的 `ArrayList`，编写一个 for 循环，逐行打印列表中每个 `String` 的大写版本（每个占一行）。

11. 在 `String` 列表 `ArrayList` 上运行时，以下代码会抛出异常。为什么？

```java
for (String s : words) {
    System.out.println(s);
    if (s.equals("hello")) {
        words.add("goodbye");
    }
}
```

12. 以下代码无法编译。为什么？解释如何修复它。

```java
ArrayList<int> numbers = new ArrayList<int>();

numbers.add(7);

numbers.add(19);

System.out.println(numbers);
```

13. 什么是包装类？描述 `int` 和 `Integer` 之间的区别。

## 10.2 节: Comparable 接口

14. 描述如何将 `ArrayList` 排成排序顺序。为了能够对其进行排序，列表中的元素类型必须满足什么条件？

15. 什么是自然排序？你如何为你写的类定义自然排序？

16. 假定以下变量声明：

```java
Integer n1 = 15;

Integer n2 = 7;

Integer n3 = 15;

String s1 = "computer";

String s2 = "soda";

String s3 = "pencil";
```

指出以下每个比较结果是正数、负数还是 0：

```java
n1.compareTo(n2)

n3.compareTo(n1)

n2.compareTo(n1)

s1.compareTo(s2)

s3.compareTo(s1)

n2.compareTo(s2)
```

17. 编写代码从控制台读取两个名称，并使用 `compareTo` 方法打印哪个在字母顺序上更前。例如：

```text
Type a name: Tyler Durden
Type a name: Marla Singer
Marla Singer comes before Tyler Durden
```

18. 编写代码从用户处读取一行输入，并按排序顺序打印该行的单词。例如：

```text
Type a message to sort: to be or not to be that is the question
Your message sorted: be is not or question that the to to
```

# 练习题

1. 编写一个名为 `averageVowels` 的方法，接收一个 `ArrayList<String>` 作为参数并返回列表中所有字符串中元音字符（a, e, i, o, u）的平均数量。如果给你的方法传递了一个空 `ArrayList`，它应该返回 0。

2. 编写一个名为 `swapPairs` 的方法，接收一个 `ArrayList` 作为参数，并成对交换列表中元素的顺序。如果列表中的元素个数是奇数，则最后一个元素不移动。例如，如果列表初始为 "to","or","not","hamlet"，方法调用后应变为 "or","to","hamlet","not"（注：原文此处逻辑描述混乱，意为交换对元素，此处根据具体语境调整）。

3. 编写一个名为 `removeLength` 的方法，接收一个 `ArrayList<String>` 作为参数并移除列表中长度为偶数的字符串。

4. 编写一个名为 `doubleInt` 的方法，接收一个 `ArrayList<String>` 作为参数并替换列表中的每个整数。例如，如果列表存储 "how","are","you?"，方法调用后应变为对应数值的翻倍。

5. 编写一个名为 `minFront` 的方法，接收一个 `ArrayList<Integer>` 作为参数并报告列表中最小值。例如，如果列表存储 3, 8, 2, 4, 17, 19，方法调用后应返回 2。

6. 编写一个名为 `removeDuplicates` 的方法，接收一个 `ArrayList<String>` 作为参数并移除列表中的重复项。

7. 编写一个名为 `removeZeros` 的方法，接收一个 `ArrayList<Integer>` 作为参数并移除列表中的 0。例如，如果列表存储 7, 2, 4，方法调用后应移除 0。

8. 编写一个名为 `rangeBetween` 的方法，接收一个 `ArrayList<Integer>` 作为参数并返回两个整数之间的个数。

9. 编写一个名为 `rangeBetween` 的方法，接收一个 `ArrayList<String>` 作为参数并返回两个 0 之间的字符串个数。

10. 编写一个名为 `mergeRange` 的方法，接收三个参数：一个 `ArrayList<String>`、起始字符串和一个结束字符串，并移除列表中字母顺序位于这两个字符串之间的元素。

11. 修改 `Point` 类，使其通过 `Comparable` 接口定义自然排序。按 y 坐标进行比较，即 y 坐标值较小的点排在 y 坐标值较大的点之前。如果 x 坐标相同，则通过比较 x 坐标值来决定。

12. 修改 `Date` 类以包含年份字段，并修改其 `compareTo` 方法在比较时考虑年份。年份的优先级高于月份，月份的优先级高于日期。例如，1995 年 7 月 18 日在某某日之前。

# 编程项目

1. 编写类来模拟购物列表。创建一个 `Item` 类表示购物商品的名称和价格，例如纸巾 $3.00。还实现一个 `OrderClass`，表示购物者购买特定数量的需求。最后，实现一个 `ShoppingCart` 类，它使用 `ArrayList` 存储订单，并允许添加、移除或搜索购物车。购物车能够报告其当前携带的所有物品的总价。

2. 编写一个方法反转文件的行，并反转每行单词的顺序。使用 `ArrayList` 来帮助你。

3. 编写一个数据库程序。创建一个类来表示一个人，它存储对其母亲、父亲和任何孩子的引用。读取一个文件以初始化每个人的及其父子关系。（你可能想创建一个代表自己的家族树的类。）使用 `ArrayList` 存储所有的 `Person`。编写一个整体主界面，询问名称并打印该人的母系和父系家族线。

这里是程序的假设执行过程，使用都铎王朝君主的名单作为输入文件：

```text
人物姓名？亨利八世
母系：
亨利八世
约克的
父系：
亨利八世
亨利七世
子女：
玛一世
伊丽莎白一世
爱德华六世
```

4. 编写一个类来模拟可能重叠的矩形 2D 窗口区域，例如你电脑上运行的程序窗口。列表中矩形的顺序决定了它们在屏幕上的显示顺序（有时称为“z 序”），从底部的 0 到顶部的 `size() - 1`。

![矩形窗口示意图](img/aea18896a4bced58de45f29f5a93f7b3_627_0.png)

每个矩形存储其 x/y 位置、宽度和高度。你的矩形列表类应该有一个方法，接受一个 `Point` 作为参数，将其视为用户点击了屏幕上的该 `Point`，并将接触该 `Point` 的最上方矩形移动到列表前端。

# Java 集合框架

## 引言

上一章节探讨了 `ArrayList` 类。`ArrayList` 是 Java 中存储数据的多种方式之一。在本章中，我们将探索 Java 的集合框架，包括列表（lists）、集合（sets）和映射（maps）。我们将看到如何结合使用这些结构以多种方式处理和检查数据，并通过案例研究解决编程问题；本章将探讨三个较小有趣的案例，而不是在章节末尾呈现统一的案例。

我们将引入一种名为链表（linked list）的新类型列表，它存储数据的方式与 `ArrayList` 不同但支持相同的操作。我们还将讨论称为集合（sets）的集合，它们不允许重复元素且便于搜索。我们将探索的另一个集合类型是映射（map），它在数据值值对之间建立关联。我们还将深入研究抽象数据类型的概念，将其作为集合的能力与其实现细节分离的方法。

## 11.1 列表 (Lists)

- 集合 (Collections)
- `LinkedList` 对比 `ArrayList`
- 迭代器 (Iterators)
- 抽象数据类型 (ADTs)
- 链表案例研究：筛法 (Sieve)

## 11.2 集合 (Sets)

- 集合概念
- `TreeSet` 对比 `HashSet`
- 集合操作
- 集合案例研究：彩票 (Lottery)

## 11.3 映射 (Maps)

- 基础映射操作
- 映射视图 (`keySet` 和 `values`)
- `TreeMap` 对比 `HashMap`
- 映射案例研究：单词计数
- 集合概述

# 第 11 章 Java 集合框架

## 11.1 列表

第 10 章中的 `ArrayList` 类相比数组有几个优势：它会为你跟踪大小，允许在数组的任意位置进行插入和删除，并在满时为你自动调整大小。

在本节中，我们将学习一种名为 `LinkedList` 的对象，它与 `ArrayList` 类似。我们还将探索关于集合泛化的概念，并讨论一种名为迭代器（iterator）的实用对象，它可以让你检查任何集合的元素。

### 集合 (Collections)

在第 7 和第 8 章中，我们讨论了使用数组和类来存储数据的方法。组织和结构化数据是一个重要的概念，有助于解决复杂问题。存储和管理数据的实体称为数据结构。数据结构可以用于实现复杂的存储对象集合。

> 一个存储一组其他对象（称为其元素）的对象。

`ArrayList` 是集合的一个示例。集合在内部使用数据结构来存储其元素，例如数组或一组相互引用的对象。例如，`ArrayList` 是使用数组作为其数据结构实现的，而 `TreeSet`（本章稍后引入的集合）是使用名为二叉搜索树的数据结构实现的。

集合根据它们存储的元素类型、允许对这些元素执行的操作，以及这些操作的速度或效率进行分类。集合的一些示例包括：

- 列表（List）：一种通过整数索引访问的有序元素集合。
- 栈（Stack）：一个最后添加的元素最先移除的集合。
- 队列（Queue）：一个元素按照添加顺序被移除的集合。
- 集合（Set）：一个保证不包含重复元素的元素集合，且通常可以高效地搜索。
- 映射（Map）：一组（键，值）对的集合，其中每个键都关联一个相应的值。

Java 提供了大量实用的集合，允许你以多种方式存储、访问、搜索、排序和处理数据。这些集合和类统称为 Java 集合框架。

### 表 11.1 Collection 接口的实用方法

| 方法 | 说明 |
| --- | --- |
| `add(element)` | 将指定的元素添加到此集合中 |
| `addAll(collection)` | 将给定集合中的所有元素添加到此集合中 |
| `clear()` | 从此集合中移除所有元素 |
| `contains(element)` | 如果此集合包含该元素，则返回 `true` |
| `containsAll(collection)` | 如果此集合包含给定集合的所有元素，则返回 `true` |
| `isEmpty()` | 如果此集合不包含任何元素，则返回 `true` |
| `iterator()` | 返回一个可以用于遍历此集合元素的对象 |
| `remove(element)` | 如果此集合包含该指定的元素，则移除该元素的一次出现 |
| `removeAll(collection)` | 从此集合中移除给定集合的所有元素 |
| `retainAll(collection)` | 移除不在给定集合中的所有元素 |
| `size()` | 返回此集合中元素的数量 |
| `toArray()` | 返回一个包含此集合元素的数组 |

`java.util` 包包含一个名为 `Collection` 的接口，每个集合都实现了该接口。该接口规定了大多数集合支持的操作。表 11.1 列出了这些操作。现在我们将查看一个名为 `LinkedList` 的集合并将其与 `ArrayList` 进行比较。这些类将在本章中讨论。

### `LinkedList` 对比 `ArrayList`

`ArrayList` 是一个强大实用的集合，但在某些情况下使用它并不是理想的。例如，假设我们想写一个程序从 `ArrayList` 中删除偶数长度的字符串。我们可以使用查看列表每个元素的循环来实现：

# 第 II 章 集合框架

![集合框架示意图](img/aea18896a4bced58de45f29f5a93f7b3_631_0.png)

```java
// 从数组列表中移除所有偶数长度的字符串
public static void removeEvenLength(ArrayList<String> list) {
    int i = 0;
    while (i < list.size()) {
        String element = list.get(i);
        if (element.length() % 2 == 0) {
            list.remove(i);
        } else {
            i++; // 跳到下一个元素
        }
    }
}
```




上述代码是正确的，当列表包含大量元素时，它的性能并不好。在相对现代的机器上，处理一个百万元素的列表可能需要几分钟。其原因是每当我们从列表中删除元素时，都必须将后续的所有元素向左移动。

另一种 `ArrayList` 表现缓慢的情况是它被用于建模等待队列或队列，其中元素（客户）总是添加到列表末尾，并总是从头部移除。当客户到达时，他们被添加到列表末尾。客户从列表头部移除并轮流处理。从大型 `ArrayList` 的头部移除元素是一个缓慢的操作，因为每个其他元素都必须向左移动。

还有另一种类型的集合，称为链表（linked list），在处理这类需要在列表头部或中间大量添加或删除的问题时可以提供更好的性能。链表执行与数组列表相同的操作，如 `add`、`size` 和 `contains`。但链表以一种根本不同的方式存储其元素。链表的元素存储在称为节点（nodes）的小型容器中。节点之间“链接”在一起，每个节点存储指向下一个节点的引用。整个对象保留对头部和尾部节点的引用。

## 11.1 列表

### 链表（Linked List）

一种在称为“节点”的小对象容器中存储元素列表的集合，这些节点相互连接。

可以将链表看作是一个被“拆散”了的数组列表，每个元素都存储在一个小盒子（节点）中，并通过箭头与其相邻的盒子连接起来：

![](img/aea18896a4bced58de45f29f5a93f7b3_632_0.png)

使用链表的一个主要优势是，通常可以快速地在列表头部添加元素，因为不需要移动数组中的所有元素，链表会创建一个新的节点对象并将其与列表中的其他节点连接。我们不需要手动执行此操作；只需调用列表的方法即可，它会在内部为我们处理好一切。11.2 显示了当在列表头部添加元素时，链表内部发生了什么。

在 Java 中使用列表，请创建一个 `LinkedList` 类型的对象而不是 `ArrayList`。`LinkedList` 对象具有与你在处理 `ArrayList` 时使用的相同的方法：

```java
LinkedList<String> words = new LinkedList<String>();

words.add("hello");

words.add("goodbye");

words.add("this");

words.add("that");
```

我们可以编写一个 `removeEvenLength` 方法的版本，使其接受 `LinkedList<String>` 作为参数而不是 `ArrayList<String>`。仅此一项改变对性能不会产生太大影响。由于 `removeLength` 方法按顺序检查列表的每个元素，我们可以通过使用另一种称为“迭代器”（iterator）的对象来使代码更高效。

1. 创建新节点以存放新元素。
2. 将新节点连接到列表中的其他节点。

![](img/aea18896a4bced58de45f29f5a93f7b3_632_1.png)

3. 将列表头部指向新节点。

![](img/aea18896a4bced58de45f29f5a93f7b3_632_2.png)

图 11.2 向链表头部添加元素

### 迭代器（Iterators）

正如第 7 节讨论过的，数组提供了一种名为“随机访问”（random access）的优秀属性，这意味着我们可以以任何顺序高效地访问或修改任意元素。这是因为数组存储在大型的连续内存块中；计算机可以快速计算出任何元素的内存位置。遗憾的是，链表并不提供快速访问。由于链表由许多较小的节点对象组成，且通常只保留对头部元素的直接引用，因此无法快速访问列表的任意元素。在这方面，链表有点像 VHS 录像带或音频磁带：如果我们想访问某个元素，必须通过遍历列表进行“快进”或“倒回”到正确的位置。

当你在链表上调用 `get`、`set`、`add` 或 `remove` 方法时，内部会创建一个临时引用，该引用从列表头部开始，并遍历节点之间的链接，直到到达指定的索引。这所需的时间取决于所使用的索引；如果你请求索引为 9000 的元素，`get` 方法内部的循环就必须向前移动 9000 个节点，这将花费更长的时间。

这些方法在链表上的执行通常较慢，尤其是当你多次调用它们或在包含许多元素的列表上调用它们时。想象一下，在之前的调用 `get(9000)` 之后，你决定调用 `get(9001)`。链表并不会记得之前的位置，它必须从头部开始向前移动 9001 次。方法运行快速唯一的情况是当你传递的索引靠近列表头部或尾部时。

早些时候，我们写了一个方法从 `ArrayList` 中删除偶数长度的字符串。如果我们将此代码改为使用 `LinkedList` 且不做任何其他修改，我们会发现它在大规模列表上运行仍然非常慢，因为它调用了多次 `get` 和 `remove`。

```java
// 在链表上性能很差

public void removeLength(LinkedList<String> list) {

    int i = 0;

    while (i < list.size()) {

        String element = list.get(i); // 慢

        if (element.length() % 2 == 0) {

            list.remove(i); // 慢

        } else {

            i++;

        }

    }

}
```

然而，如果我们想要顺序访问链表的每个元素（即，如果我们想从头到尾按顺序检查每个元素），有一种高效的方法可以检查链表的每个元素。为了实现这一点，我们可以使用一种称为“迭代器”的特殊对象，它可以跟踪我们在列表中的当前位置。

### 迭代器（Iterator）

一种允许你按顺序高效检索列表元素的对象。

使用迭代器时，当我们从一个元素移动到下一个元素时，不需要每次调用都返回开头，并从列表头部一直跟随链接到指定的索引。正如我们在本章中看到的，迭代器是 Java 集合框架的核心。每个集合都提供了迭代器来访问其元素。这意味着我们有一套熟悉的接口来检查任何集合的元素。迭代器对象具有表 11.2 中列出的方法。

要从许多集合（如 `ArrayList`）获取迭代器，你可以按照以下方式调用迭代器：

```java
Iterator<String> iter = list.iterator();

while (iter.hasNext()) {

    // 使用 iter.next() 进行某些操作

}
```

从集合中删除偶数长度的示例可以使用迭代器更高效地实现：

```java
// 从列表中删除偶数长度的字符串

public static void removeLength(LinkedList<String> list) {

    Iterator<String> i = list.iterator();

    while (i.hasNext()) {

        String element = i.next();

        if (element.length() % 2 == 0) {

            i.remove();

        }

    }

}
```

#### 表 11.2 迭代器对象的方法

| 方法 | 说明 |
| :--- | :--- |
| `hasNext()` | 如果有更多元素待检查，则返回 true |
| `next()` | 返回列表的下一个元素并向前移动一位 |
| `remove()` | 移除由 `next()` 返回的元素 |

原始的 `ArrayList` 版本处理百万个元素可能需要几分钟；而这段新代码在十分之一秒内就完成了。它的执行速度非常快，由于迭代器在获取或删除元素之间保留了列表中的当前位置。

Java 的 `for-each` 循环在内部也使用了迭代器。当你使用 `for-each` 循环时，Java 实际上在使用迭代器访问元素。

```java
for (String word : list) {

    System.out.println(word + " - " + word.length());

}
```

### 常见编程错误

#### 对迭代器多次调用 `next`

迭代器对初学者来说可能有些难以理解，因此你必须小心使用它们。以下代码尝试使用迭代器寻找并返回链表中最长的字符串，但它存在一个 bug：

```java
// 返回列表中最长的字符串（无效）

public static String longest(LinkedList<String> list) {

    Iterator<String> itr = list.iterator();

    String longest = itr.next(); // 初始化为第一个元素

    while (itr.hasNext()) {

        if (itr.next().length() > longest.length()) {

            longest = itr.next();

        }

    }

    return longest;

}
```

之前代码的问题在于，`next` 方法在迭代器上被调用了两次：一次是在测试长度时，另一次是在尝试存储最长字符串时。每次调用 `next`，迭代器都会向前移动一位，因此如果在循环中调用了两次，你会在发现匹配时跳过一个元素。例如，如果列表包含元素（"oh", "hello", "how", "are", "you"），你可能会看到 "hello" 并打算存储它，但第二次调用 `next` 会导致你实际上存储了后续元素 "how"。

解决方案是将 `itr.next()` 的结果保存到变量中。以下代码将替换之前的 `while` 循环：

```java
// 之前代码的这个版本是正确的

while (itr.hasNext()) {

    String current = itr.next();

    if (current.length() > longest.length()) {

        longest = current;

    }

}
```

## 1.1 列表

当编译器处理 `for-each` 循环时，它本质上将其转换为以下代码：

```java
Iterator<String> i = list.iterator();

while (i.hasNext()) {

    String word = i.next() + " " + word.length();

    System.out.println(word);

}
```

`Iterator` 还有一个更高级的版本，叫做 `ListIterator`，它只适用于列表（lists）。`ListIterator` 提供了诸如添加元素、获取元素值以及从后到前的反向迭代等操作。由于它更为复杂，我们不会在本书中详细讨论 `ListIterator`。

总而言之，以下是 `ArrayList` 和 `LinkedList` 的一些主要优势：

| 集合 | 优势 |
| :--- | :--- |
| `ArrayList` | - 随机访问：可以快速访问任何元素<br>- 在列表末尾添加和删除元素速度快 |
| `LinkedList` | - 在列表的任意端添加或删除元素速度都快<br>- 使用迭代器进行顺序访问时可以快速添加/删除<br>- 数组满时不需要扩展数组<br>- 更容易用作队列 |

## 抽象数据类型（ADTs）

`LinkedList` 集合提供了与 `ArrayList` 相同的方法，这并非偶然。它们都被认为是同一种类型集合的实现：列表（list）。在高级层面上，最重要的并不是列表的内部实现方式，而是我们可以在它上面执行的操作。这组操作就是抽象数据类型（或简称 ADT）的示例。

> **抽象数据类型（ADT）**  
> 对某种数据类型及其可以在上面执行的操作的规范。

ADT 规定了可以在数据上执行的操作，而没有规定这些操作是如何实现的。链表（Linked lists）和数组列表（array lists）都是列表 ADT 的示例，因为它们都提供了相同的操作，例如通过索引存储数据、在特定索引处添加和删除数据等。

在 Java 中，ADT 是通过接口（interfaces）指定的。每个 ADT 的操作由其接口的方法指定。例如，`LinkedList` 和 `ArrayList` 都实现了 `java.util` 包中一个名为 `List` 的接口。`List` 接口声明了这两种类型列表都实现的所有通用方法。

## 第 11 章 Java 集合框架

在声明任何集合变量和参数时，使用相应的 ADT 接口而不是实际的类类型被认为是一种良好的实践。例如，以下代码声明了一个 `LinkedList` 对象并将其存储在类型为 `List` 的变量中：

```java
List<Integer> list = new LinkedList<Integer>();
```

Java 集合框架的作者之一 Joshua Bloch 将这种做法称为“一种强烈建议的编程规范，因为它赋予了你更改实现的灵活性”。请注意，你不能创建类型为 `List` 的对象，但可以使用 `List` 作为变量的类型。

在声明参数、返回类型或字段时，你也可以使用像 `List` 这样的 ADT 接口类型。当你编写一个接受集合作为参数的方法时，这样做是有用的，因为这意味着该方法将能够成功地操作任何实现了 ADT 接口的集合。例如，以下方法可以接受 `LinkedList<String>` 或 `ArrayList<String>`：

```java
// 返回给定列表中最长的字符串

// 前置条件: list.size() > 0

public static String longest(List<String> list) {

    Iterator<String> i = list.iterator();

    String result = i.next();

    while (i.hasNext()) {

        String next = i.next();

        if (next.length() > result.length()) {

            result = next;

        }

    }

    return result;

}
```




它对两种类型的列表都有效，并且对两者都是高效的。这种灵活性是多态性（在第 9 章讨论过）的另一个优势。`java.util` 包有一个类 `Collections`，它包含了与所有集合相关的多个方法（注意，这与所有集合实现的 `Collection` 接口不是同一个）。`Collections` 类包含了对列表进行操作的静态方法。

## 11.3 `Collections` 类的静态方法

| 方法 | 说明 |
| --- | --- |
| `binarySearch(list, value)` | 在列表中二分查找值 |
| `copy(list, sourceList)` | 复制 `sourceList` 到 `destinationList` |
| `fill(list, value)` | 用指定值填充列表 |
| `replace(list, oldValue, newValue)` | 将列表中的第一个旧值替换为新值 |
| `max(list)` | 返回最大值的元素 |
| `min(list)` | 返回最小值的元素 |
| `replaceAll(list, oldValue, newValue)` | 替换列表中所有旧值为新值 |
| `reverse(list)` | 反转列表 |
| `rotate(list, distance)` | 将列表元素循环移动距离 |
| `shuffle(list)` | 随机打乱列表 |
| `sort(list)` | 对列表排序 |
| `swap(list, index1, index2)` | 交换两个索引的元素 |

## 案例研究：筛法（Sieve）

考虑寻找素数的任务。素数是除了 1 之外没有其他因数的整数。埃拉托斯尼筛（Sieve of Eratosthenes，以发明它的希腊数学家命名）是一种寻找素数的经典算法。为了构建素数列表，你可以使用如下方式（对于最大值为 25）：

```text
numbers: (2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25)

primes: ()
```

算法通过从列表中过滤掉该质数的倍数来开始。例如，2 是从列表中选出的数字，并将 2 放入质数列表：

```text
numbers: (3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25)

primes: (2)
```

现在 `numbers` 列表开头的数字是 3。这个数字在下一轮中将被放入质数列表，并且 `numbers` 列表中所有的倍数都将被移除。这是第二轮后的列表状态：

```text
numbers: (4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25)

primes: (2, 3)
```

从 `numbers` 列表头部取的数字保证是素数。非素数无法到达 `numbers` 列表的头部，因为任何非素数都是某个素数的倍数，而任何此类倍数在之前的轮中都被移除了。这是第三轮后的列表状态：

```text
numbers: (4, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25)

primes: (2, 3, 5)
```

现在 `numbers` 列表开头的数字是 7。这个数字在下一轮中将被放入质数列表，并且 `numbers` 列表中所有的倍数都将被移除。这是第四轮后的列表状态：

```text
numbers: (4, 6, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25)

primes: (2, 3, 5, 7)
```

以下代码实现了该算法：

```java
while (numbers.isEmpty()) {
    // 从列表头部移除一个质数
    int front = numbers.remove(0);
    primes.add(front);

    // 移除该质数的所有倍数
    Iterator<Integer> itr = numbers.iterator();
    while (itr.hasNext()) {
        int current = itr.next();
        if (current % front == 0) {
            itr.remove();
        }
    }
}
```

以下是完整的程序。最显著的添加是一个 `main` 方法，它提示用户输入要检查的最大数字：

- 使用链表实现埃拉托斯尼筛法来寻找质数。

```java
import java.util.*;

public class Sieve {
    public static void main(String[] args) {
        System.out.println("这个程序将告诉你所有质数!");
        System.out.println("在给定最大值范围内的质数.");
        System.out.println(":");

        Scanner scanner = new Scanner(System.in);

        System.out.println("Maximum number? ");
        int max = scanner.nextInt();

        List<Integer> primes = sieve(max);

        System.out.println("Prime numbers up to " + max + ":");
        System.out.println(primes);
    }

    public static List<Integer> sieve(int max) {
        List<Integer> numbers = new LinkedList<Integer>();

        // 将从2到 max 的所有数字添加到列表
        for (int i = 2; i <= max; i++) {
            numbers.add(i);
        }

        while (!numbers.isEmpty()) {
            // 从列表头部移除一个质数
            int front = numbers.remove(0);
            primes.add(front);

            // 移除该质数的所有倍数
            Iterator<Integer> itr = numbers.iterator();
            while (itr.hasNext()) {
                int current = itr.next();
                if (current % front == 0) {
                    itr.remove();
                }
            }
        }

        return primes;
    }
}
```

# 第 11 章 Java 集合框架

以下是程序执行的示例日志：

```text
这个程序将告诉你所有在给定最大值范围内的质数。

Maximum number? 50
Prime numbers up to 50:
[2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47]
```

![](img/aea18896a4bced58de45f29f5a93f7b3_641_0.png)

我们版本的筛算法经过了简化。真实的算法一旦列表头部元素大于最大值的平方根就会停止，因为列表中剩余任何大于该数值的数字在列表中都不可能有剩余的倍数。例如，当最大值为 25 时，当列表头部的元素超过了 5，列表中剩余的所有数字已知都是质数，并可以放入 `primes` 列表中。

该算法可以通过其他方式进行改进。例如，初始数字列表实际上并不需要存储从 2 到最大值的每一个整数。相反，它可以存储 2 以及直到最大值的每个奇数。这使得算法更高效，因为需要处理的数字更少。这两个改进被留作练习。

## 11.2 集合（Sets）

链表列表和数组列表的一个主要局限性是它们搜索速度慢。通常，如果你想搜索一个列表，必须顺序检查每个元素以查看是否找到了目标。对于大型列表来说，这可能花费长时间。

列表的另一个局限性是很难防止列表存储重复值。在很多情况下这不是一个问题，但例如，如果你正在存储一个集合来统计书中唯一单词的数量，你就不希望存在重复项。为了防止列表中的重复项，你必须在每次执行 `add` 操作时顺序搜索列表，以确保你没有添加已经存在的单词。

当你想要维护一个防止重复且可以快速搜索的元素集合时，使用另一种名为 `set`（集合）的抽象数据类型会更好。

> **Set**
>
> 一种用于存储一组元素并防止重复的集合。

集合与数学中的集合概念非常相似。集合不支持你可以在列表上执行的所有操作（即任何需要索引的操作），但它们提供了快速搜索和毫不费力地消除重复的优势。

## 集合概念

Java 集合框架 `Set` 接口的两个主要实现被称为 `HashSet` 和 `TreeSet`。`HashSet` 是通用集合类，而 `TreeSet` 提供了稍后将讨论的一些优势。如果你想存储一组 `String` 值的集合，你可以编写这样的代码：

```java
Set<String> stooges = new HashSet<String>();

stooges.add("Larry");
stooges.add("Moe");

stooges.add("Curly");
stooges.add("Moe"); // 重复，不会被添加

stooges.add("Shemp");
stooges.add("");
```

`Set` 的缺点之一是不通过索引存储元素。循环在 `Set` 上无法编译，因为它没有 `get` 方法：

```java
// 这段代码无法编译
for (int i = 0; i < words.size(); i++) {
    String word = words.get(i); // 错误 - 没有 get 方法
    System.out.println(word);
}
```

## Java 集合框架

集合在忽略重复的情况下检查大量数据时非常有用。例如，如果你想查看书中出现了多少唯一单词，你可以编写如下代码：

```java
Set<String> words = new HashSet<String>();

Scanner in = new Scanner(new File("mobydick.txt"));

while (in.hasNext()) {
    String word = in.next();
    word = word.toLowerCase();
    words.add(word);
}

System.out.println("Number of unique words = " + words.size());
```

这段代码在运行来自 `http://www.gutenberg.org` 的《白鲸》副本时会产生输出：

```text
Number of unique words = 30368
```

`HashSet` 类有一个方便的构造函数，接受另一个集合作为参数，并将其中的所有唯一元素放入 `Set` 中。该构造函数的一种用法是检查 `List` 是否包含任何重复项。为此，只需从它构造一个 `HashSet` 并查看大小是否不同。以下代码演示了这一点：

```java
// 如果给定的列表包含重复项则返回 true
public static boolean hasDuplicates(List<Integer> list) {
```



```java
Set<Integer> set = new HashSet<Integer>(list);

return set.size() < list.size();

}
```

相反，如果你想遍历`Set`的元素，必须使用迭代器（iterator）。其他集合都有`iterator`方法，可以创建一个`Iterator`对象来检查它们的元素。你随后可以使用熟悉的`hasNext/next`循环来检查每个元素：

```java
// 这段代码正常工作

Iterator<String> itr = words.iterator();

while (itr.hasNext()) {
    String word = itr.next();
    System.out.println(word);
}
```

## 11.2 集合

与前面的代码相比，更短替代方案是对集合的元素进行 for-each 循环。如之前所述，代码的行为相同，但更易编写和阅读。

```java
for (String word : words) {
    System.out.println(word);
}
```

### TreeSet 对比 HashSet

上一节的示例使用了`HashSet`，但另一个名为`TreeSet`的类也实现了`Set`接口。`TreeSet`使用一种名为二叉搜索树的内部链式数据结构按排序顺序存储元素。`TreeSet`在添加、删除和搜索方面非常高效，尽管它比`HashSet`稍微慢一点。

如果你想打印集合并让输出结果是有序的，那么`TreeSet`就会很有用。例如，下面的代码显示了《莫比·迪克》中所有以 "a" 开头的三个字母单词的排序集合：

```java
Set<String> words = new TreeSet<String>();

Scanner in = new Scanner(new File("mobydick.txt"));

while (in.hasNext()) {
    String word = in.next();
    word = word.toLowerCase();

    if (word.startsWith("a") && word.length() == 3) {
        words.add(word);
    }
}

System.out.println("Three-letter 'a' words = " + words + ")");
```

代码产生输出：

- 三字母的 'a' 单词 = [act, add, ado, aft, age, ago, ah!, ah,, aid, aim, air, alb, ale, ali, all, am,, ami, am-, and, ant, any, apt, arc, are, ark, arm, art, as,, as-, as., ash, ask, at,, at., at;; ate, awe, axe, aye]

`TreeSet`可以用于具有自然排序的数据。这意味着如果元素是任何实现了`Comparable`接口的类型（例如`Integer`或`String`），它就可以正常工作。你也可以提供你自己的对象来指定如何比较元素，该对象被称为比较器（`comparator`）。比较器将在第 13 章涵盖搜索和排序时进行讨论。

你不应该构造一个没有自然排序的对象的`TreeSet`，例如`Point`对象：

```java
// 这段代码可以编译通过，但会导致运行时错误

Set<Point> points = new TreeSet<Point>();
```

前面的代码可以编译（遗憾的是），但当你运行它时会产生异常，因为程序不知道如何对`TreeSet`中的`Point`对象进行排序：

## 第二章 Java 集合框架

```text
Exception in thread "main"

java.lang.ClassCastException: java.awt.Point

at java.util.TreeMap.compare(Unknown Source)

at java.util.TreeMap.put(Unknown Source)

at java.util.TreeSet.add(Unknown Source)
```

在这种情况下，你使用`HashSet`会更好。总结来说，以下是`HashSet`和`TreeSet`之间的一些主要区别：

| 集合 | 优点 |
|---|---|
| `HashSet` | • `add`、`contains`、`remove`性能极快<br>• 可以使用任何类型的对象作为元素 |
| `TreeSet` | • 元素按排序顺序存储<br>• 必须与可以比较的元素（如`Integer`、`String`）一起使用 |

### 集合操作

考虑你有两个集合并需要确定它们出现了多少个唯一元素的情况。你不能简单地将两个集合的大小相加，因为它们可能有一些共同元素，这些元素在总数中不应重复计算。你可以统计第一个集合中的所有元素，然后只统计第二个集合的唯一元素，通过检查第二个集合中的每个元素是否在第一个集合中：

```java
// 返回在 set1 或 set2 中包含的唯一元素的数量。
// 这不是良好的遵循模型。

public static int totalElements(Set<String> set1,
                                Set<String> set2) {
    int count = set1.size();

    for (String element : set2) {
        if (!set1.contains(element)) {
            count++;
        }
    }

    return count;
}
```

然而，另一种更优雅的方法是计算两个集合的并集（union）。集合 A 和 B 的并集是 A 或 B 中的所有元素。交集（intersection）是 A 和 B 的共同元素。差集（difference）是位于 A 但不在 B 中的元素。集合操作通常通过韦恩图（Venn diagrams）来表示，其中集合显示为圆形，重叠部分表示集合操作。11.1 集合韦恩图 11.1 展示了某些集合操作示例。

## 11.2 集合

![集合操作](img/aea1896a4bced584f29f73_0.png)

A ∪ B 并集

A ∩ B 交集

A - B 差集

表 11.4 给集合 A 和 B 的集合操作

| 集合操作 | 方法 | 描述 |
|---|---|---|
| 并集 | `add` | A 或 B 中的所有元素 |
| 交集 | `retain` | A 和 B 的共同元素 |
| 差集 | `remove` | A 但不在 B 中的元素 |
| 超集、子集 | `contains` | 如果 A 是 B 的子集则返回 true |

## 第二章 Java 集合框架

在前面的代码中，我们初始化了一个包含`set1`中所有元素的`HashSet`，然后将`set2`的内容添加到新集合中，这样做是因为调用者可能不希望破坏`set1`和`set2`。

### 集合案例研究：彩票

考虑编写一个彩票程序的任务。程序应该随机生成中奖号码，然后提示玩家输入彩票号码。根据匹配的数量，玩家将获得奖金。

集合是存储中奖号码和玩家号码的优秀集合。它们防止重复，并允许我们高效地测试一个集合中的号码是否在另一个集合中。这将帮助我们统计玩家中奖的数量。

下面的代码使用`Random`对象初始化一个 1 到 40 之间的中奖集合。代码使用 while 循环，因为同一个号码可能会被生成多次：

```java
Set<Integer> winningNumbers = new TreeSet<Integer>();

Random r = new Random();

while (winningNumbers.size() < 6) {
    int number = r.nextInt(40) + 1;
    winningNumbers.add(number);
}
```

一旦生成了获奖集合，我们将玩家选择的正确号码读取到第二个集合中。为了确定，我们可以搜索中奖集合以查看它是否包含票中的每个元素。然而，另一种更优雅的方法是确定中奖集合和玩家票集之间的交集。下面的代码通过复制票并移除其中的任何元素创建交集：

```java
// 找到用户票中的中奖号码

Set<Integer> intersection = new TreeSet<Integer>(ticket);
intersection.retain(winningNumbers);
```

一旦我们得到了交集，就可以询问它的数量并为玩家计算相应的现金金额。（我们的版本从 100 美元开始，每中一个号码奖金翻倍。）

这里是彩票程序的完整实现。我们创建了几个静态方法用于结构，并添加了一些关于号码数量、最大号码和彩票奖金的常量：

- 1 与用户玩彩票游戏，读取
- 2 用户的彩票号码并打印与
- 3 中奖中奖票匹配的数量。

## 11.2 Set

```java
import java.util.*;

public class Lottery {
    public static final int NUMBERS = 6;
    public static final int MAX_NUMBER = 40;

    public static void main(String[] args) {
        // 获取中奖号码和票集

        Set<Integer> winningNumbers = createWinningNumbers();
        Set<Integer> ticket = getTicket();

        System.out.println();

        // 保留用户票中的中奖号码

        Set<Integer> intersection = new TreeSet<Integer>(ticket);
        intersection.retainAll(winningNumbers);

        // 打印结果

        System.out.println("Your ticket numbers are " + ticket + ");
    }
}
```

# 第二章 Java 集合框架

以下是运行程序的一个示例输出：

```text
Type your 6 unique lotto numbers: 2 8 15 18 21 32

Your ticket numbers are [2, 8, 15, 18, 21, 32]
The winning numbers are [1, 3, 15, 16, 18, 39]

You had 2 matching numbers.
The matched numbers are [15, 18]
Your prize is $400.0
```

## 11.3 Map

考虑这样一个任务：编写一个电话簿程序，允许用户输入姓名并搜索该人的电话号码。你可以将数据存储在数组或集合（set）中。你可能会创建一个名为`PhoneBookRecord`的小类，存储人的姓名和电话号码，并使用列表来包含这些`PhoneBookRecord`对象。在搜索电话号码时，你将使用匹配用户输入姓名的`PhoneBookRecord`遍历列表并返回关联的电话号码。

像上面描述的这种解决方案并不实用。对于大量的记录列表，程序将花费很长时间查看每条记录，以找到检索电话号码的正确记录。

在许多数据处理任务中，将对象对（如姓名和电话号码）关联起来是有用的。我们经常会说：“我想将每个 A 与一个 B 关联。”也许我们想将姓名与地址关联，这样当用户输入姓名时，我们就能快速查找该人的地址。或者我们可能想通过将每个单词与其出现次数关联，来统计书中每个单词出现的次数。

抽象数据类型`map`描述了一种集合，它允许你在对象对之间创建单向关联，以解决此类问题。

| Map |
|---|
| 一个将称为键（keys）的对象与称为值（values）的对象关联起来的集合。 |

Map 可以解决许多惊人的问题。Map 可以按长度对书中所有的单词分组，并报告每个长度有多少个单词。Map 可以将用户与其朋友/伙伴集关联。Map 甚至可以表示家族树，其中每个人都知道其父亲或母亲的身份。

我们说 Map 将键与值关联起来。一个键只能映射到一个值，但多个键可以映射到同一个值。Java 的集合框架包含一个表示这种 ADT 的`Map`接口。

Map 可以被认为是一对连接的键：一组键和与这些键关联的值的集合。图 11.4 是这种想法的示例：将名（first names）映射到姓（last names）。

![](img/aea18896a4bced58de45f29f5a93f7b3_650_0.png)

图 11.4 将键：名映射到值：姓

## 基本 Map 操作

实现`Map`接口的两个主要类是`HashMap`和`TreeMap`。`HashMap`是更通用的 Map；`TreeMap`按排序存储可比较的键。

构造 Map 时使用不是一个而是两个泛型类型参数，并用逗号分隔。第一个类型参数表示键的类型，第二个表示值的类型。这导致代码中的声明行变得很长。以下是构造一个薪资 Map 的示例（将人的姓名与其薪资关联）。注意，我们必须使用包装类型`Double`而不是原始类型`double`：

```java
Map<String, Double> salaryMap = new HashMap<String, Double>();
```

使用`put`方法将键/值对添加到 Map 中，这与其它集合的`add`方法大致相似。`put`方法接受一个键和一个值作为参数，并在 Map 中存储键与值之间的映射。如果该键之前与另一个值关联，则新关联将替换旧关联。我们可以使用以下代码向薪资 Map 中添加键/值对：

```java
salaryMap.put("Stuart Reges", 20000.00);
salaryMap.put("Marty Steff", 15500.00);
salaryMap.put("Jenny", 86753.09);
```

一旦向 Map 添加了键/值对，你就可以调用 Map 的`get`方法来查找值，该方法接受键作为参数并返回与该键关联的值：

```java
double jenSalary = salaryMap.get("Jenny");

System.out.println("Jenny's salary is $" + jenSalary);
```

要检查 Map 是否包含给定键的映射，可以使用`containsKey`方法，或者调用`get`方法并测试是否为`null`：

```java
Scanner console = new Scanner(System.in);

System.out.println("Type a person's name: ");

String name = console.nextLine();

if (salaryMap.containsKey(name)) {
    double salary = salaryMap.get(name);
    System.out.println(name + " is $" + salary);
} else {
    System.out.println("I don't have a record for " + name);
}
```

Map 的`toString`方法显示键/值对。键出现的顺序取决于类型。以下是 Map 打印时的内容：

```text
{Jenny=86753.09, Marty Steff=15500.0, Stuart Reges=20000.0}
```

## Map 视图（keySet 和 values）

与集合不同，Map 没有迭代器方法。Map 有名为`keySet`和`values`的方法，它们在概念上是 Map 的视图。

## 表 11.5 有用方法

| 方法 | 描述 |
|---|---|
| `clear()` | 移除所有的键和值 |
| `containsKey(key)` | 如果 Map 包含键 |
| `containsValue(value)` | 如果 Map 包含值 |
| `get(key)` | 返回与键关联的值 |
| `put(key, value)` | 将键与值关联 |
| `remove(key)` | 移除键的映射 |
| `size()` | 返回键/值映射的数量 |
| `keySet()` | 返回所有键的 Set |
| `values()` | 返回所有值的 Collection |

# 第 11 章 Java 集合框架

注意，这段代码没有声明变量来存储集合键（set key），而是在 for-each 循环中直接调用了`keySet`。输出结果如下：

```text
Jenny's SSN is 867530912

Stuart Reges's SSN is 439876305

Marty's SSN is 504386382
```

有一个名为`entrySet`的相关方法，它返回类型为`Entry`的对象，这些对象表示键/值对，但我们在这里不会探讨它。

# TreeMap 对比 HashMap

就像有两种集合实现方式`HashSet`和`TreeSet`一样，Java 中也有两种集合：`HashMap`和`TreeMap`。`HashMap`的执行速度比`TreeMap`快一点，并且可以存储任何类型的数据，但它以某种杂乱的顺序存储其键。`TreeMap`只能存储可比较的数据，执行速度稍慢，但它会按排序顺序存储其键。

我们如下所示声明了上一节中的社会安全号码映射以使用`TreeMap`：



```java
Map<String, Integer> ssnMap = new HashMap<String, Integer>();

ssnMap.put("Stuart Reges", 439876305);

ssnMap.put("Marty Steff", 504386382);

ssnMap.put("Jenny", 867530912);

System.out.println(ssnMap);
```

当我们打印它时，会看到键的顺序有所不同：

> (Jenny=867530912, Marty Steff=504386382, Stuart Reges=439876305)

注意，名称（映射的键）是按字母顺序排序的。这对于某些应用非常有用，但`HashMap`仍然是 Sun 推荐用于通类型。许多应用程序并不关心键的顺序，并能从`HashMap`更好的性能中受益。`HashMap`即使在没有自然排序的数据上也能工作。

# Map 案例研究：单词计数

在较早的例子中，我们统计了《白鲸号》书中唯一单词的数量。如果我们被要求找到书中出现频率最高的单词呢？似乎对于书中的每个单词，我们都应该统计该单词出现了多少次。如果然后我们检查所有这些计数并打印值较大的那些，我们就得到了答案。

映射（Maps）对于解决这类问题非常有用。我们可以创建一个单词计数映射，其中每个键都是一个单词，其关联的值是该单词在书中出现的次数：

```java
wordCountMap = new HashMap<>();

for (String word : file) {

  if (I have never seen this word before) {

    set this word's count to 1;
```

## 11.3 Maps

将此单词计数加 1。

我们需要一个`Scanner`来读取适当的文件，以及一个`Map`来存储单词计数：

```java
Map<String, Integer> wordCount = new TreeMap<String, Integer>();

Scanner in = new File("mobydick.txt");
```

我们现在可以读取文件内容并将遇到的每个单词存储在映射中。如果我们遇到一个以前见过的单词，我们就检索它的旧计数值，将其加 1，然后将新值放回映射中。记住，当你将一个键/值映射放入包含该键的映射中时，旧映射会被替换。例如，如果单词`"ocean"`被映射到数字 25，而我们放入一个新的从`"ocean"`到 26 的映射，旧映射会被替换；我们不需要手动删除它。这里是构建映射的代码：

```java
while (in.hasNext()) {

    String word = in.next().toLowerCase();

    if (!wordMap.containsKey(word)) { // 以前从未见过

        wordMap.put(word, 1);

    } else {

        int count = wordMap.get(word);

        wordMap.put(word, count + 1);

    }

}
```

一旦我们构建了计数映射，如果我们想打印书中出现次数超过（比如）2,000 次的所有单词，我们可以编写如下代码：

```java
for (String word : wordMap.keySet()) {

    int count = wordMap.get(word);

    if (count > 2000) {

        System.out.println(word + " occurs " + count + " times.");

    }

}
```

这里是完整的程序，为了结构添加了一个方法，并为单词打印所需的出现次数添加了一个常量：

```java
1 // 使用映射来实现单词计数，以便使用户
2 // 可以看到《白鲸号》书中哪些单词出现得最多。
3
4 import java.io.*;
5 import java.util.*;
6
7 public class WordCount {
8     // 打印所需的最小出现次数
9     public static final int OCCRENCES = 2000;
10
11 public static void main(String[] args) throws FileNotFoundException {
12     System.out.println("This program displays the most");
13     System.out.println("frequently occurring words from:");
14     System.out.println("the book Moby Dick.");
15     System.out.println();
16
17 // 将书籍读入映射
18     Scanner in = new Scanner(new File("mobydick.txt"));
19     Map<String, Integer> wordCount = new TreeMap<String, Integer>();
20
21     for (String word : wordMap.keySet()) {
22         int count = wordMap.get(word);
23         if (count > OCCRENCES) {
24             System.out.println(word + " occurs " + count + " times.");
25         }
26     }
27 }
28
29 // 读取书籍并返回单词到计数的映射
30 public static Map<String, Integer> getCount(Scanner in) {
31     Map<String, Integer> wordMap = new HashMap<String, Integer>();
32
33     while (in.hasNext()) {
34         String word = in.next().toLowerCase();
35         if (!wordMap.containsKey(word)) { // 以前从未见过
36             wordMap.put(word, 1);
37         } else {
38             // 以前见过；将计数加 1
39             int count = wordMap.get(word);
40             wordMap.put(word, count + 1);
41         }
42     }
43     return wordMap;
44 }
45 ```
46
```

该程序对《白鲸号》的输出如下：

```text
Jenny=867530912

Marty Steff=504386382

Stuart Reges=439876305
```

# 集合概览

在本章中我们讨论了三种主要的抽象类型：列表、集合和映射。了解它们之间的区别是非常重要的。

# 表 11.6 列表、集合和映射的比较

| ADT 接口 | 实现 | 描述/优点 | 缺点 | 示例用法 |
|---|---|---|---|---|
| `List` | `ArrayList`, `LinkedList` | 按插入顺序的元素序列 | 搜索慢，添加/删除任意元素慢 | 账户列表：队列 |
| `Set` | `HashSet`, `TreeSet` | 唯一元素的集合 | 没有索引；无法检索任意元素 | 书中的唯一单词 |
| `Map` | `HashMap`, `TreeMap` | “键”和“值”对的关联组 | 不是通用集合；无法从值映射回键 | 单词计数：电话簿 |

表 11.6 总结了不同类型的集合及其优缺点。在处理涉及数据的问题时，你可以自己判断哪种集合类型最合适。这里是一些例子：

- 你对数据做什么？你是打算大量添加和删除、搜索数据，还是将此数据与其他数据连接起来？
- 你计划搜索数据吗？如果是，如何？如果你想按插入顺序检查元素，使用列表。集合可能更好。如果你需要根据部分信息查找对象（例如根据 PIN 或 ID 编号查找用户的银行账户对象），映射可能更好。
- 元素应该以什么顺序存储？

## 总结

集合是存储一组对象的对象。集合的示例有`ArrayList`、`HashSet`和`TreeMap`。集合用于，组织和搜索数据。

链表是一种与`ArrayList`相似的集合，但它在内部通过将每个元素存储在一个名为节点的容器容器对象来实现。链表在某些操作（如在列表头部或中间添加和删除数据）方面比数组列表更快。

## 第二章 Java 集合框架

迭代器（iterator）是一个用于跟踪列表位置并按顺序快速检查元素的对象。链表（Linked lists）通常与迭代器一起使用以提高效率。

Java 中有两个主要的集合类：`TreeSet`和`HashSet`。`TreeSet`以排序的顺序存储`Comparable`数据；`HashSet`可以存储任何数据且搜索速度更快，但其元素的存储顺序是不可预测的。

抽象数据类型（ADT）是对可以在数据上执行的操作的规格说明。ADT 的两个例子是`List`和`Set`。Java 集合框架中的 ADT 是接口的形式表示的（例如，`List`接口由`LinkedList`和`ArrayList`同时实现）。

`Map`（映射）是一个将键对象与值对象关联起来的集合。`Map`用于在数据片段之间建立关系，例如人的姓名和电话号码。

`Set`（集合）是一个不允许重复元素的集合。集合通常可以快速搜索以检查它们是否包含某个特定的值元素。`Set`接口表示集合。

Java 中有两个主要的映射类：`TreeMap`和`HashMap`。`TreeMap`以排序的顺序存储`Comparable`键；`HashMap`可以接受任何数据作为键并执行更快的值查找，但其键的存储顺序是不可预测的。

## 自测题

### 第 11.1 节：列表（Lists）

1. 什么时候使用`LinkedList`而不是`ArrayList`？
2. 运行以下代码时，`LinkedList`还是`ArrayList`更好？为什么？

```java
// 这代码在链表上的性能很差

public static int min(LinkedList<Integer> list) {

    int min = list.get(0);

    for (int i = 1; i < list.size(); i++) {

        if (list.get(i) < min) {

            min = list.get(i);

        }

    }

    return min;

}
```

3. 什么是迭代器？为什么迭代器经常与链表一起使用？
4. 编写代码统计列表中重复元素的数量；即值在列表中较早索引处已出现的元素。假设列表中的所有重复项都是连续出现的。例如，列表`(1, 1, 3, 5, 5, 5, 5, 7, 11)`包含五个重复元素：元素 1 的一个重复，元素 5 的三个重复以及元素 7 的一个重复。你可能希望将代码写在一个名为`countDuplicates`的方法中，该方法接受链表作为参数并返回重复的数量。
5. 编写代码在有序的 String 列表中插入一个 String，并保持排序顺序。例如，使用`"Alpha"`、`"Baker"`、`"Foxtrot"`、`"Tango"`、`"Whiskey"`，在有序列表中插入`"Charlie"`将产生`"Alpha"`、`"Baker"`、`"Charlie"`、`"Foxtrot"`、`"Tango"`、`"Whiskey"`。
6. 编写方法`removeAll`，它接受一个整数链表作为参数并移除特定值的所有出现项。你必须保留列表中剩余元素的原始顺序。例如，调用`removeAll(list, 3)`将列表`(3, 9, 4, 2, 3, 8, 17, 4, 3, 18, 2)`更改为`(9, 4, 2, 8, 17, 4, 3, 18, 2)`。
7. 编写方法`wrapHalf`，它接受一个整数列表作为参数并将列表的前半部分移动到列表末尾。如果列表包含奇数个元素，则对于大小为 N 的列表，较小的一部分将被循环（按什么顺序）。中间元素 N/2 在（所有情况下）将成为第一个元素。例如，对列表`(1, 2, 3, 4, 5, 6)`调用`wrapHalf`将其更改为`(4, 5, 6, 1, 2, 3)`。对于列表`(5, 6, 7, 8, 9)`，结果将是`(7, 8, 9, 5, 6)`。
8. 什么是抽象数据类型（ADT）？ADT 实现了什么？
9. 第 4 题要求你编写代码来统计链表中的重复项。将你的代码重写为名为`countDuplicates`的方法，允许将`ArrayList`或`LinkedList`作为参数传递。

### 第 11.2 节：集合（Sets）

10. `List`拥有`Set`拥有的所有方法。那么为什么你要使用`Set`而不是`List`呢？
11. 什么时候使用`TreeSet`，什么时候使用`HashSet`？
12. `Set`没有`ArrayList`拥有的`get`和`set`方法。你如何检查`Set`的每一个元素？
13. 在代码执行后，以下集合包含哪些元素？

```java
Set<Integer> set = new HashSet<Integer>();

set.add(74);

set.add(12);

set.add(182);

set.add(90);

set.add(43);

set.remove(74);

set.remove(999);

set.remove(43);

set.remove(12);

set.add(182);

set.add(9);

set.add(29);
```

14. 在代码执行后，以下集合包含哪些元素？

```java
Set<Integer> set = new HashSet<Integer>();

set.add(8);

set.add(41);

set.add(18);

set.add(50);

set.add(132);

set.add(28);

set.add(79);

set.remove(41);

set.remove(28);

set.add(86);

set.add(98);

set.remove(18);
```

15. 在代码执行后，以下集合包含哪些元素？

```java
Set<Integer> set = new HashSet<Integer>();

set.add(4);

set.add(15);

set.add(73);

set.add(84);

set.add(247);

set.remove(15);

set.add(42);

set.add(12);

set.remove(73);

set.add(94);
```

16. 如何对两个集合执行并集（union）操作？尝试给出不需要循环的答案。

### 第 11.3 节：映射（Maps）

17. 编写代码声明一个将姓名与年龄关联的`Map`。为你年龄以及朋友的年龄添加映射。
18. `Map`没有`ArrayList`拥有的`get`和`set`方法。它没有像`Set`那样的迭代器方法。如何检查`Map`的每一个键（key）？
19. 在代码执行后，以下`Map`包含哪些键值对？

```java
Map<Integer, String> map = new HashMap<>();

map.put(7, "Marty");

map.put(34, "Louann");

map.put(2, "Donald");

map.put(15, "Moshe");

map.put(84, "Larry");

map.put(23, "Ed");

map.remove(8);

map.put(5, "Moshe");

map.remove(84);
```

20. 在代码执行后，以下`Map`包含哪些键值对？

```java
Map<Integer, String> map = new HashMap<>();

map.put(8, "Eight");

map.put(41, "Forty-one");

map.put(8, "Ocho");

map.put(18, "Eighteen");

map.put(50, "Fifty");

map.put(132, "Two");

map.put(28, "Twenty-eight");

map.put(79, "Seventy-nine");

map.remove(41);

map.remove(28);

map.put(86, "Eighty-six");

map.put(98, "Ninety-eight");

map.remove(18);
```

21. 修改程序，使其根据出现频率打印单词。为了实现这一点，在程序末尾编写代码创建一个根据次数的反向 map。假设两个单词出现的次数完全相同。

## 练习题（Exercises）

1. 修改 11.1 节中开发的 Sieve 程序进行两次优化。首先，不要在列表中存储所有整数，而是只存储奇数。其次，编写代码以确保当第一个数字达到最大值的平方根时，剩余的数字移动到质数列表（这种操作是有效的吗？）

- 第一个列表第一个元素
- 第二个列表第一个元素
- 第一个列表第二个元素
- 第二个列表第二个元素
- 第一个列表第三个元素
- 第二个列表第三个元素
- ...
2. 编写一个方法接受列表作为参数，并返回一个包含交替元素的列表，顺序如下：



如果列表元素数量相同，较长列表的剩余元素应连续放在最后。例如，对于第一个列表`(1, 2, 3, 4, 5)`和第二个列表`(6, 7, 8, 9, 10, 11, 12)`，调用`alternate(list1, list2)`应返回`(6, 2, 7, 3, 8, 4, 9, 5)`。

3. 编写方法`removeInRange`，它接受一个列表、一个整数`E`和一个索引。其行为是移除起始索引（包含）和结束索引（不包含）之间的所有给定元素。索引之外的其他值不受影响。

例如，对于列表`(0, 0, 2, 0, 4, 0, 6, 0, 8, 0, 10, 0, 12, 0, 14, 0, 16)`，调用`removeInRange(list, 5, 13)`应返回`(0, 0, 2, 0, 4, 14, 0, 16)`。注意零在原始列表（进行任何修改之前）位于索引 5 到 13 之间。

4. 编写方法`partition`，它接受一个整数列表和一个整数`E`作为参数，并重排（分区）列表，使其所有小于`E`的元素出现在大于`E`的元素之前。元素的顺序不重要，只要小于`E`的元素出现在大于`E`的元素之前。例如，对于链表`(15, 1, 6, 12, -3, 4, 8, 21, 2, 30, -1, 9)`，调用`partition(list)`后列表的一种接受排序为`(-1, 1, 2, 4, 6, 8, 12, 15, 21, 30)`。你可以假设列表不包含重复项且不包含元素值`E`。

5. 编写一个名为`sortRemoveDuplicates`的方法，它接受一个整数列表作为参数，并返回按升序排列的列表元素，同时移除列表中的所有重复值。例如，列表`(7, 4, -9, 4, 15, 8, 27, 11, -5, 32, -9)`在调用你的方法后，将移除重复项并返回`(-9, -5, 4, 7, 8, 11, 15, 32)`。在处理过程中请使用一个`Set`。

6. 编写一个名为`symmetricDifference`的方法，它接受两个`Set`作为参数，并返回一个新的`Set`差集（即包含于两个集合之一但不同于两者交集的元素集合）。例如：集合`(1, 4, 7, 9)`和`(2, 4, 5, 6, 7)`的对称差集是`(1, 2, 5, 6, 9)`。

7. 编写一个名为`isUnique`的方法，它接受一个`Map<String, String>`作为参数，如果没有两个键映射到相同的值，则返回`true`。例如：`(Marty=206-9024, Hawking=123-4567, Smith=555-1234, Smith=949-0504, Newton=123-4567)`应返回`false`，但`(Marty=206-9024, Hawking=555-1234, Smith=949-0504, Newton=123-4567)`应返回`true`。空 map 被视为 1 对 1 的并返回`true`。

8. 编写一个名为`subMap`的方法，它接受两个`Map<String, String>`作为参数，并返回一个 map，其中第一个 map 中的每个键都在第二个 map 中，并且在第二个 map 中映射到相同的值。例如：`(Smith=949-0504, Marty=206-9024, Hawking=123-4567, Smith=949-0504, Newton=123-4567)`是`(Marty=206-9024, Hawking=123-4567)`的子 map。空 map 是任何 map 的子 map。

9. 编写一个名为`reverse`的方法，它接受一个`Map<String, String>`作为参数，并返回一个新的 map，该 map 使用原始的值作为键，并将原始的键作为值。由于 map 的值不需要是唯一的，但键是，因此你应该将每个值映射到一个键的集合。换句话说，如果原始 map 将类型为`K`的元素映射到类型为`V`的值，新 map 应该将类型为`V`的元素映射到类型为`K`的集合。例如，map`{42=Marty, 81=Sue, 17=Ed, 31=Dave, 56=Ed, 29=Ed}`的反转为`{Marty=[42], Sue=[81], Ed=[17,56,29], Dave=[31]}`。键和值的顺序不重要。

10. 编写第 10 章开发的`Vocabulary`程序的修改版本，该程序使用`sets`而不是`Arrays`来存储单词。该程序将明显变短且更快！

## 编程项目

1. 编写一个程序计算两个单词之间的编辑距离（也因其创建者 Vladimir Levenshtein 而称为 Levenshtein 距离）。单词之间的距离是将一个字符串转换为另一个所需的最少操作数。对于此程序，一次操作是单个字符的替换，例如从`"brick"`变为`"brick"`。单词`"dog"`和`"cat"`之间的编辑距离为 3，因为通过`"dot"`、`"cot"`和`"cat"`链可以将`"dog"`转换为`"cat"`。在计算两个单词之间的编辑距离时，每个单词必须是一个实际值。编辑距离在应用程序中用于判断两个字符串的相似性，例如拼写检查器。

从字典文本文件中读取输入。从该文件中计算从每个单词到其直接邻居的 map；即与该单词编辑距离为 1 的单词。建立此 map 后，你可以寻找从一个单词到另一个单词的路径。

处理邻居 map 路径的一种良好方法是使用单词链表进行访问，从起始单词（如`"dog"`）开始。你的算法应该移除列表头部并将所有内容添加到列表末尾，直到找到结束单词（如`"cat"`）或列表为空（后者表示两个单词之间不存在路径）。

2. 编写一个解决经典“稳定婚姻”问题的程序。该问题涉及一组男性和一组女性。程序尝试将他们配对，以产生尽可能多的婚姻。如果发现一个男人和一个女性，他们更愿意彼此结婚而不是与目前的配偶结婚，那么这组婚姻是不稳定的（在这种情况下，这两个人将与其配偶离婚并互相结婚）。

程序的输入将列出所有男性，每行一个，随后是一个空行，然后列出所有女性，每行一个。男性和女性通过在输入文件中的位置编号（第一个男性是 #1，第二个男性是 #2，以此类推；第一个女性是 #1，第二个女性是 #2，以此类推）。每个输入（除分隔男女的空行外）都有一个名称。

### 12.1 递归思维

你必须以某种方式使问题变得。不要问你前面的人你在队伍中第几个，而是问他/或她在队伍中第几个：

> 我想知道我在队伍中第几个。那么，你在队伍中第几位？

> 让我试着想想。

![](img/aea18896a4bced58de45f29f5a93f7b3_666_0.png)

关键区别在于，你前面的人更接近队伍的前头部。例如，假设你在队伍中排第 10 位。你前面的人是第 9 位，更接近队首。但请注意，你正在要求你前面的人思考和你正在考虑的完全相同的问题：你们都在试图弄清楚队伍中的位置。这就是递归出现的地方——问题反复出现，因为你们每个人都想回答同一个问题。

这个想法是建立一个链反应，让每个人都向他们前面的人问同一个问题：

> 你在队伍中第几位？

> 你在队伍中第几位？

> 你在队伍中第几位？

![](img/aea18896a4bced58de45f29f5a93f7b3_666_1.png)

## 第 12 章递归

这个过程最终必须结束，当到达队伍前面的人时：

![](img/aea18896a4bced58de45f29f5a93f7b3_667_0.png)

在这一点，你到达了所谓的**递归底部**。你让了一群人共同解决这个问题，并终于到达了一个可以开始组装答案的点。最前面的人在第 1 位。这意味着紧随其后的人在第 2 位，再前面的人在第 3 位，以此此类推。一旦你到达递归底部，你就可以回溯（unwind）它来找到初始问题的答案：

![](img/aea18896a4bced58de45f29f5a93f7b3_667_1.png)

### 12.1 递归思维

为了简洁起见，这些图只包含了四个人，但想象一下如果队伍中有 30 或 300 个人。

这里需要注意的一个关键方面是，递归涉及到许多协作的实体，它们各自解决一小部分问题。而不是一个人完成所有的计数，而是每个人在向队伍前方移动时问一个问题，在返回时回答一个问题。

在编程中，迭代解决方案是让一个人完成所有计数。而让许多人各做一点工作的递归解决方案，则翻译为许多不同的方法调用，每个调用都执行一小部分工作。让我们来看一个简单的迭代解决方案如何转换为递归解决方案的示例。

### 将迭代解决方案转换为递归

假设你想创建一个名为`writeStars`的方法，它接受一个整数`n`，并生成一行包含`n`个星号的输出。你可以用一个简单的循环来解决这个问题：

```java
public static void writeStars(int n) {
    for (int i = 1; i <= n; i++) {
        System.out.print("*");
    }
    System.out.println();
}
```

这里重复的操作是调用`System.out.print`来打印一个星号。要用递归的方式编写它，你需要考虑不同的情况。你可能会要求该方法生成包含 10 个星号、20 个星号或 50 个星号的行。或者在你可能要求它执行的所有可能的任务中，哪是最简单的？

学生通常回答说打印一个星号的行非常简单，他们说的没错很简单。但还有一个任务更简单。打印一行零星号的行几乎不需要任何工作。你可以通过调用`System.out.println()`来创建这样一行，因此你可以从这种情况的测试开始你的递归定义：

```java
public static void writeStars(int n) {
    if (n == 0) {
        System.out.println();
    } else {
```

在`else`部分，你想处理星号数量多于 0 的行。你的直觉可能是将之前显示的`for`循环填充到`else`部分，但你必须克制用那种方式解决整个问题的冲动。要解决问题的第二部分，思考你如何只做极少量的工作来让你更接近解决方案是重要的。如果星号的数量大于 0，你知道必须至少打印一个星号，所以你可以将其添加到代码中：

## 第 12 章递归

```java
public static void writeStars(int n) {
  if (n == 0) {
    System.out.println();
  } else {
    System.out.print("*");
    // 还需要做什么？
  }
}
```

在处理过程的这一阶段，你必须做出“信仰的跃跃”。你必须相信递归是有效的。一旦你打印了一个星号，还剩下什么要做？你减少了问题：现在你只需要打印剩下的`n-1`个星号。

## 第12章 递归

### 递归情况 (Recursive Case)

指将整体问题简化为同类型的更简单的问题，而该问题可以通过递归调用来解决。

这里是`writeStars`方法，用注释标记了它的基础情况（base case）和递归情况（recursive case）：

```java
public static void writeStars(int n) {
  if (n == 0) {
    // base case
    System.out.println();
  } else {
    // recursive case
    System.out.print("*");
    writeStars(n - 1);
  }
}
```

基础情况是编写一行零星号的任务。这个任务非常简单，可以立即完成。递归情况是编写包含一个或多个星号行的任务。要解决递归情况，你首先写一个星号，这将剩余的任务减少为编写`(n - 1)`行星号。这就是`writeStars`方法旨在解决的任务，它比原始任务更简单，因此你可以通过递归调用来解决它。

打个比方，假设你站在一个有`n`级阶梯的顶部。如果你有一种方法从一个台阶移动到下面的一个台阶，并且能识别出何时到达了地面，你就可以处理任何高度的阶梯。从一个台阶迈到下面的一个台阶就像递归情况，你执行某些工作将问题简化为相同形式的更简单的问题——从`(n - 1)`级台阶降到地面。识别何时到达地面就像基础情况，它是可以直接解决的（走下阶梯）。

有些问题涉及多个基础情况和递归情况，但每种情况都至少会有一个。如果你缺少了其中任何一个，就会遇到麻烦。如果没有从一个台阶向下走到下一个一个台阶的能力，你会被困在阶梯顶端。如果没有识别何时到达地面的能力，即使阶梯上已经没有台阶，你也会继续尝试向下走。

由于递归解决方案包含了基础情况和递归情况的组合，你会发现它们通常用`if/else`语句、嵌套`if`语句或其细微变体来编写。你还会发现递归编程通常涉及用例分析，即对问题可能采取各种形式分类为不同的情况，并为每种情况编写解决方案。

## 12.2 递归的更好的示例

虽然用递归编写星号任务可能是一个有趣的练习，但它并不是一个非常有说服力的例子。让我们详细看看一个递归如何简化工作内容的问题。

假设你有一个连接到外部输入文件的`Scanner`，你想反序打印文件中的每一行。例如，该文件可能包含以下四行文本：

```
this
is
fun
no7
```

反序打印这些行将产生以下输出：

```
no7
fun
is
this
```

要用迭代法解决这个问题，你需要某种数据结构来存储文本行。你可能需要使用一个`ArrayList<String>`。然而，通过递归，你可以不使用数据结构就解决问题。

记住，递归编程涉及考虑情况。什么文件最容易反转？一行文件的反转相当容易，但反转空文件更简单。因此，你可以这样开始编写方法：

```java
public static void reverse(Scanner input) {
    if (!input.hasNextLine()) {
        // base case (空文件)
    } else {
        // recursive case (非空文件)
        ...
    }
}
```

对于这个问题，基础情况简单到无事可做。空文件没有行需要反转。因此，在这种情况下，反转`if/else`语句以便测试递归情况更有意义。这样你就可以写一个简单的结构，其中隐含了“else”即无事可做：

```java
public static void reverse(Scanner input) {
    if (input.hasNextLine()) {
        // recursive case (非空文件)
        ...
    }
}
```

再次，挑战在于解决问题的一小部分。你如何离完成更近？你可以从文件中读取一行文本：

```java
public static void reverse(Scanner input) {
    if (input.hasNextLine()) {
        // recursive case (非空文件)
        String line = input.nextLine();
```

对于示例文件，这会将`"this"`这一行读入变量`line`中，并在`Scanner`中留下这三行文本：

is

fun

no7

记住，你的目标是产生这个整体输出：

no7

fun

is

this

你可能会问自己诸这样的问题：“还有其他输入需要处理吗？” 这不是递归的思考方式。如果你在递归地思考，你会考虑调用该方法会带给你什么。`Scanner`处于`"is"`、`fun"`和`"no7"`这三行之前，调用`reverse`将读取这些行并产生你所需要的的前三行输出。如果这有效，你只需要在最后写出`"this"`行即可完成输出。

这就是这里涉及的“信仰之跃”——你必须相信`reverse`方法实际上是有效的。如果是的话，这段代码可以如下完成：

```java
public static void reverse(Scanner input) {
    if (input.hasNextLine()) {
        // recursive case (非空文件)
        String line = input.nextLine();
        // ...
    } else {
        // base case
        return;
    }
    // ...
}
```

事实证明这是有效的。要反转一系列行，你读取第一行，反转剩下的，然后写出第一行。这看起来是不可能的，但确实如此。

### 递归的原理

初学者在了解更多底层原理时能更好地理解递归。让我们详细检查递归方法。考虑以下简单的程序：

```java
// 绘制三个星号的简单程序
public class DrawTriangles {
    public static void main(String[] args) {
        drawTriangle();
        drawTriangles();
    }

    public static void drawTriangle() {
        System.out.println("*");
        System.out.println("**");
        System.out.println("*****");
    }

    public static void drawTriangles() {
        drawTriangle();
        drawTriangle();
    }
}
```

它打印打印三个星号：

*

***

*****

我们如何描述程序中发生的方法调用？假设每个方法调用都写在一张纸上。我们通过进入`main`方法开始程序执行，想象我们抓住了写有`main`的纸：

```java
public static void main(String[] args) {
    drawTriangle();
    drawTriangles();
}
```

然后我们顺序执行`main`中的每个语句。首先遇到`drawTriangle`的调用：



我们知道此时计算机停止执行`main`，并将注意力转向`drawTriangle`方法。我们可以将其想象为拿起写有`drawTriangle`的纸，并把它放在写有`main`的纸上。

```java
public static void main(String[] args) {
    drawTriangle();
    drawTriangles();
}
```

现在我们顺序执行`drawTriangle`中的每个语句，然后返回`main`，移除`drawTriangle`纸。当我们返回`main`时，已经完成了对`drawTriangle`的调用。

```java
public static void main(String[] args) {
    drawTriangle();
    drawTriangles();
}
```

现在我们抓起写有`drawTriangles`的纸，并把它放在写有`main`的纸上。

```java
public static void main(String[] args) {
    drawTriangle();
    drawTriangles();
}
```

## 12.2 递归的一个更好的示例

```java
public static void main(String[] args) {
    public static void drawTwoTriangles() {
        public static void drawTriangle() {
            System.out.println(" *");
            System.out.println(" ***");
            System.out.println("*****");
            System.out.println(" ");
        }
    }
}
```

这张图清楚地显示，我们是从`main`方法开始的，它调用了`drawTwoTriangles`方法，后者又调用了`drawTriangle`方法。因此，三个不同的方法都是激活状态。最顶端的是正在执行的那个。一旦完成它的执行，就会返回到下方，一旦完成下方的执行，就会返回`main`。我们可能已经理解这个思路了。

将每个方法调用表示为一张纸，并在调用时将它们叠放在在一起，这就像是 Java 调用栈（call stack）的一种比喻。

## 调用栈

一种用于跟踪已调用方法执行顺序的内部结构。

如果你将调用栈想象成一叠纸，最近调用的方法位于最上面，你就能很好地理解它的工作原理了。让我们利用调用栈的概念来理解递归文件反转方法是如何工作的。为了能够可视化调用栈，我们需要将方法的定义写在纸上。

```java
public static void reverse(Scanner input) {
    if (input.hasNextLine()) {
        String line = input.nextLine();
        reverse(input);
        System.out.println(line);
    }
}
```

注意，这张纸上包含一个存储局部变量`line`值的地方。这个细节将被证明是非常重要的。

假设我们使用之前的示例输入文件调用此方法，该文件包含以下四行文本：

- this
- is
- fun
- no?

# 第 12 章 递归

当我们调用该方法时，它将第一行文本读取到它的`line`变量中，然后到达对`reverse`的递归调用：

```java
public static void reverse(Scanner input) {
    if (input.hasNextLine()) {
        String line = input.nextLine();
        reverse(input);
        System.out.println(line);
    }
}
line = "this";
```

接下来发生了什么？在`DrawTriangles`程序中，我们获取了被调用方法的纸，并将其放置在当前纸的上方。但在这里是`reverse`方法调用了`reverse`方法。要理解发生了什么，你必须意识到每个方法调用都是相互独立的。我们并不只有一张写有方法的纸；我们可以拥有所需的任意数量的副本。因此，我们可以获取第二份方法定义的副本，并将其放在当前副本之上：

```java
public static void reverse(Scanner input) {
    public static void reverse(Scanner input) {
        if (input.hasNextLine()) {
            String line = input.nextLine();
            reverse(input);
            System.out.println(line);
        }
    }
line
```

这个版本的方法有自己的名为`line`的变量，可以在其中存储一行文本。尽管上一个版本（位于它下方的那个）正处于执行中间，但这一个处于执行的开头。回想一下关于能够……的比喻。

## 12.2 递归的一个更好的示例

```java
public static void reverse(Scanner input) {
    public static void reverse(Scanner input) {
        if (input.hasNextLine()) {
            String line = input.nextLine();
            reverse(input);
            System.out.println(line);
        }
    }
}
line
```

```java
public static void reverse(Scanner input) {
    if (input.hasNextLine()) {
        String line = input.nextLine();
        reverse(input);
        System.out.println(line);
    }
}
line = "is";
```

## 12.2 递归的一个更好的示例

```java
public static void reverse(Scanner input) {
    public static void reverse(Scanner input) {
        if (input.hasNextLine()) {
            String line = input.nextLine();
            reverse(input);
            System.out.println(line);
        }
    }
}
line
```

## 第 12 章 递归

```java
public static void reverse(Scanner input) {
    if (input.hasNextLine()) {
        String line = input.nextLine();
        reverse(input);
        System.out.println(line);
    }
}
line = "fun";
```

## 第 12 章 递归

```java
public static void reverse(Scanner input) {
    if (input.hasNextLine()) {
        String line = input.nextLine();
        reverse(input);
        System.out.println(line);
    }
}
line = "this";
```

## 12.3 递归函数

我们之前过的递归示例都是`void`类型的方法。在本节中，我们将检查一些计算值并返回结果的相关方法。

### 幂运算

Java 提供了一个`Math.pow`方法，允许你计算幂。如果你想知道 $x^y$ 等于多少，可以调用`Math.pow(x, y)`。让我们考虑如何实现`pow`方法。为了简单，我们将限制在整数范围内。由于我们限制了整数，我们需要识别出一个重要的前提：无法计算负幂。

我们要写的方法看起来如下：

```java
// 前：y >= 0
// 后：返回 x^y
public static int pow(int x, int y) {
```

我们显然可以通过循环来解决这个问题，但我们想如何递归地编写方法。再次，正确的起点是考虑不同的情况。最容易计算的幂是什么？最基础的情况是 0。根据定义，任何整数的 0 次幂都被认为是 1。因此我们可以这样开始我们的解决方案：

```java
public static int pow(int x, int y) {
  if (y == 0) {
    // 基本情况：y == 0
    return 1;
  } else {
    // 递归情况：y > 0
  }
}
```

在递归情况下，我们知道 $y$ 大于 0。换句话说，结果中至少包含一个 $x$ 的因子。从数学上知道：

```text
x^y = x * x^(y-1)
```

这个方程将 $x$ 的 $y$ 次幂表示为更小的 $y-1$ 次幂。因此，它可以作为我们的递归情况。我们需要做的只是将其转换为 Java 的等效代码：

```java
public static int pow(int x, int y) {
    if (y == 0) {
        // 基本情况：y == 0
        return 1;
    } else {
        // 递归情况：y > 0
        return x * pow(x, y - 1);
    }
}
```

这是一个完整的解决方案。追踪递归函数的执行比`void`方法稍微困难，因为我们需要跟踪每次递归调用返回的值。以下是计算 $3^5$ 的执行追踪：

```text
pow(3, 5) = 3 * pow(3, 4)
pow(3, 4) = 3 * pow(3, 3)
pow(3, 3) = 3 * pow(3, 2)
pow(3, 2) = 3 * pow(3, 1)
pow(3, 1) = 3 * 1
pow(3, 3) = 3 * 9
pow(3, 4) = 3 * 27
pow(3, 5) = 3 * 81
```

注意，我们连续进行了一系列递归调用，直到计算 3 的 0 次幂的基本情况。它返回值 1，然后递归展开，在从每次方法调用返回时计算各种答案。

思考如果有人通过请求负幂来违反前提会发生什么是有用的。例如，如果有人请求`pow(3, -1)`会怎样？该方法将递归地请求`pow(3, -2)`，然后会递归地请求`pow(3, -3)`，接着是`pow(3, -4)`，以此类推。换句话说，这将导致无限递归。在某种意义上这是可以接受的，因为调用方法的人应该注意前提。但对我们来说，用更优雅的方式处理它并不困难。我们的结构设计为一系列情况，因此可以轻松地为非法指数添加新情况：

```java
public static int pow(int x, int y) {
    if (y < 0) {
        throw new IllegalArgumentException("负幂");
    } else if (y == 0) {
        // 基本情况：y == 0
        return 1;
    } else
        // 递归情况：y > 0
        return x * pow(x, y - 1);
    }
}
```

递归编写函数的优点之一是，如果我们能识别出其他情况，就有可能提高函数的效率。例如，假设我们要计算 $2^{16}$。在当前的形式下，方法将把 2 乘以 16 次。但我们可以做得更好。如果 $y$ 是偶数：

```text
x^y = (x^2)^(y/2)
```

与其计算 $2^{16}$，我们可以计算 $4^8$。将此情况加入我们的方法相对简单：

```java
public static int pow(int x, int y) {
    if (y < 0) {
        throw new IllegalArgumentException("负幂");
    } else if (y == 0) {
        // 基本情况：y == 0
        return 1;
    } else if (y % 2 == 0) {
        // 递归情况：y > 0，偶数
        return pow(x * x, y / 2);
    } else {
        // 递归情况：y > 0，奇数
        return x * pow(x, y - 1);
    }
}
```

这种版本的方法比原始的更高效。

### 最大公约数 (GCD)

在数学中，我们经常想知道能整除两个整数的最大整数，这被称为公约数 (GCD)。让我们探索如何递归地编写 GCD 方法。现在先不要担心 $x$ 和 $y$ 的负值。我们要写写这个方法：

```java
// 前：x >= 0, y >= 0
// 后：返回 x 和 y 的最大公约数
public static int gcd(int x, int y) {
```

引入一些变化，让我们尝试找出递归情况以及基本情况。例如，假设我们要计算 20 和 132 的 GCD。GCD 是 4，因为 4 完好整除这两个数。计算两个数的 GCD 有许多方法。最有效的算法之一是欧几里得算法。其思想是从整数中消除较小的整数。对于 20 和 132 的例子，我们知道：

```text
132 = 20 * 6 + 12
```

132 中有六个 20 的倍，余数为 12。欧几里得算法说我们可以忽略 20，只关注 12。换句话说，我们可以将 132 替换为 12：

```text
gcd(132, 20) = gcd(20, 12)
```

这个原理的证明超出了本书的范围，但这是基本思想。这在 Java 中很容易表达，因为`%`运算符给了我们一个数除以另一个数的余数。用通用术表示这个原理，我们知道：

```text
gcd(x, y) = gcd(x % y, y) 当 y > 0
```

再次，证明超出了本书的范围，但给定这个基本原理，我们可以产生问题的递归解决方案。我们现在可能尝试这样写方法：

```java
public static int gcd(int x, int y) {
  if (..) {
    // 基本情况
    return ...;
  } else {
    // 递归情况
    return gcd(x % y, y);
  }
}
```

这不是糟糕的尝试，但它有一个问题。仅仅数学上正确是不够的。我们需要知道我们的递归解决方案将整体问题简化为了简单的问题。如果我们从 132 和 20 开始，方法在第一次调用时取得了进展，但随后就会自我重复：

```text
gcd(132, 20) = gcd(20, 12)
gcd(20, 12) = gcd(12, 8)
gcd(12, 8) = gcd(8, 4)
```

导致无限递归。欧几里得技巧在第一次起到了作用，因为第一次调用时 $x > y$（132 大于 20）。只有当第一个数大于第二个数时，算法才能取得进展。导致我们问题的代码行是：

```java
return gcd(x % y, y);
```

当我们计算`(x % y)`时，我们保证得到一个比 $y$ 小的结果。这意味着在递归调用中，第一个值将始终比第二个值小。为了让算法工作，我们需要相反的情况。我们可以简单地通过反转参数顺序来实现这个目标：

```java
return gcd(y, x % y);
```

在这种情况下我们保证拥有一个比第二个值大的第一个值。我们追踪这个计算 132 和 20 的 GCD 的方法版本，得到：

```text
gcd(132, 20) = gcd(20, 12)
gcd(20, 12) = gcd(12, 8)
gcd(12, 8) = gcd(8, 4)
gcd(8, 4) = gcd(4, 0)
```

此时我们必须决定 4 和 0 的 GCD 是什么。这可能看起来很奇怪，但答案是 4。泛义地说，$gcd(n, 0)$ 总是 $n$。显然，GCD 不可能大于 $n$，且 $n$ 能整除 0，因为 0 可以写成 $n$ 的倍数：$(0 * n)$。这个观察引导我们走向基本情况。如果 $y$ 为 0，GCD 就是 $x$：

```java
public static int gcd(int x, int y) {
  if (y == 0) {
    // 基本情况：y == 0
    return x;
  } else {
    }
}
```

有了这个基本情况，我们还解决了欧几里得公式取决于 $y$ 不为 0 的潜在问题。但我们仍然需要考虑 $x$ 和 $y$ 之一为负的情况。我们可以保留前提并在这种情况发生时抛出异常，但数学上更常见的做法是返回两个绝对值的 GCD。我们可以通过一个额外的负数情况来实现这一点：

```java
public static int gcd(int x, int y) {
    if (x < 0 || y < 0) {
```

## 12.3 递归函数

```java
// 带有负值的递归情况
return gcd(Math.abs(x), Math.abs(y));
else if (y == 0) {
    // y == 0 的基准情况
    return x;
} else {
    // y > 0 的递归情况
    return gcd(y, x % y);
}
```

### 常见编程错误

### 无限递归



每个使用递归程序的人最终都会不小心写出一个导致无限递归的解决方案。例如，下面是`gcd`方法的一个变体，它是无法工作的：

```java
// 错误的定义
public static int gcd(int x, int y) {
    if (x <= 0 || y <= 0) {
        // 带有负值的递归情况
        return gcd(Math.abs(x), Math.abs(y));
    } else if (y == 0) {
        // y == 0 的基准情况
        return x;
    } else {
        // y > 0 的递归情况
        return gcd(y, x % y);
    }
}
```

这个解决方案与我们之前写的略有不同。在对负值的测试中，这段代码测试的是`x`和`y`是否小于或等于`0`。原始代码测试的是它们是否严格小于`0`。这看起来似乎没有太大区别，但确实有。如果我们在寻找 132 和 20 的最大公约数（GCD）原始问题上运行此版本的代码，程序将产生许多行这样的输出：

```
at Bug.gcd(Bug.java:9)
at Bug.gcd(Bug.java:9)
at Bug.gcd(Bug.java:9)
at Bug.gcd(Bug.java:9)
at Bug.gcd(Bug.java:9)
at Bug.gcd(Bug.java:9)
```

当你第一次看到这个时，你可能会认为你的电脑出问题了，因为你会得到这么多输出行。输出行数在不同系统之间会有不同，但可能是几百行甚至几千行。如果你一直向上滚动屏幕，你会发现输出以这条消息开头：

```
Exception in thread "main" java.lang.StackOverflowError
at Bug.gcd(Bug.java:9)
at Bug.gcd(Bug.java:9)
at Bug.gcd(Bug.java:9)
```

Java 正在通知你调用栈变得太大了。为什么会发生这种情况？回想一下用例的执行轨迹：

```
gcd(132, 20) = gcd(20, 12)
gcd(20, 12) = gcd(12, 8)
gcd(12, 8) = gcd(8, 4)
gcd(8, 4) = gcd(4, 0)
```

想想在这一点，当我们调用`gcd(4, 0)`时发生了什么。`y`的值为`0`，这是我们的基准情况，所以通常我们期望该方法返回值`4`并终止。该方法首先检查`x`或`y`是否小于或等于`0`。由于`y`是`0`，此测试评估结果为真，因此我们使用`x`和`y`的绝对值进行递归调用。但 4 和 0 的绝对值仍然 4 和 0。换句话说，我们判定`gcd(4, 0)`必须等于`gcd(4, 0)`，而它必须等于`gcd(4, 0)`：

```
gcd(132, 20) = gcd(20, 12)
gcd(20, 12) = gcd(12, 8)
gcd(12, 8) = gcd(8, 4)
gcd(8, 4) = gcd(4, 0)
gcd(4, 0) = gcd(4, 0)
gcd(4, 0) = gcd(4, 0)
gcd(4, 0) = gcd(4, 0)
```

换句话说，这个版本产生了无限递归调用。Java 允许你进行很多递归调用，但它最终会耗尽空间。发生时，它会给你回回溯让你是如何到达错误的。在这种情况下，回溯并没有通常那么有用，因为几乎所有的调用都涉及递归。

再次，想象像堆叠纸张一样调用方法。你将得到一个包含数百张甚至几千张纸的栈，你必须回溯所有这些纸才能找到问题。

为了处理这些情况，你必须仔细查看程序中产生无限递归的行号。在这个简单的案例中，我们知道它是针对负`x`和`y`值的递归调用。单是这一点就足以让我们精确定错误。如果问题不明显，你可能需要包含`println`语句来弄清楚发生了什么。例如，在代码中，我们可以在递归调用之前添加一个`println`：

```java
public static int gcd(int x, int y) {
    if (x <= 0 || y == 0) {
        // 带有负值的递归情况
        System.out.println("x = " + x + " and y = " + y);
        return gcd(Math.abs(x), Math.abs(y));
    } else if (y == 0) {
        // y == 0 的基准情况
        return x;
    }
}
```

加上`println`后，代码会产生数百行这样的输出：

```
x = 4 and y = 0
```

如果我们仔细检查那个情况，我们会发现我们没有得到负值，并意识到必须修复该测试。当你处理本身是递归的数据时，递归特别有用。例如，考虑文件在计算机上是如何存储的。每个文件保存在文件夹或目录中。但目录包含文件：目录可以包含其他目录，这些目录可以包含目录，甚至嵌套任意深度。

### 目录遍历

在第 6 章，你学习了使用`File`对象来跟踪计算机上的文件。例如，如果你有一个名为`data.txt`的文件，你可以构造一个`File`对象：

```java
File f = new File("data.txt");
```

`File`类的几个方法在第 6 章中引入。例如，`exists`方法指示文件是否存在，`isDirectory`方法指示名称对应的是文件还是目录。

让我们写一个程序，提示用户输入文件或目录名，并递归地探索从该点可以到达的文件。如果用户提供文件名，我们将直接打印。但如果用户提供目录名，我们将打印目录名以及内部所有的目录和文件。我们可以写一个相当简单的方法，提示文件/目录并检查它是否存在。如果不存在，它告诉用户没有该文件/目录。如果是，它调用一个方法打印该`File`对象的信息：

```java
public static void main(String[] args) {
    Scanner console = new Scanner(System.in);
    System.out.print("directory or file name?");
    String name = console.nextLine();
    File f = new File(name);
    if (!f.exists()) {
        System.out.println("No such file/directory");
    } else {
        print(f);
    }
}
```

我们的任务是编写`print`方法。该方法应该开始打印文件或目录的名字：

```java
public static void print(File f) {
    System.out.println(f.getName());
}
```

如果`File f`代表一个简单的文件，这就是我们要做的全部。但如果`f`代表一个目录，我们还想要打印目录中所有文件的名称：我们可以使用`listFiles`方法来实现，它返回一个代表目录内容的`File`对象数组。我们可以使用`for`循环处理每一个：

```java
public static void print(File f) {
    System.out.println(f.getName());
    if (f.isDirectory()) {
        for (File subF : f.listFiles()) {
            // 打印 subF 信息
        }
    }
}
```

为了完成该方法，我们必须弄清楚如何打印目录中每个`subF`对象的信息。一个显然的方法是直接打印名称：

不完全正确：

```java
public static void print(File f) {
    System.out.println(f.getName());
    if (f.isDirectory()) {
        for (File subF : f.listFiles()) {
            System.out.println(subF.getName());
        }
    }
}
```

![](img/aea18896a4bced5de45f29f5a93f7b3_689_0.png)

这种方法可以打印目录内部的文件名。但记住，这个目录内部可能有目录，所以其中某些实际上是需要打印内容的目录。我们可以尝试通过额外的测试来修复代码：

越越糟，而不是更好：

```java
public static void print(File f) {
    System.out.println(f.getName());
    if (f.isDirectory()) {
        for (File subF : f.listFiles()) {
            System.out.println(subF.getName());
            if (subF.isDirectory()) {
                // 打印子目录内容
            }
        }
    }
}
```

但即使这样也不行，因为在那些目录内部可能还有目录，而那些目录可能有子目录。使用标准的迭代技术没有简单的方法可以解决这个问题。

解决方案是递归地思考。你可能倾向于将可能性视为许多不同的情况：文件、包含文件的目录、包含子目录的目录、一个有子目录的目录等等。然而，只有两种情况需要考虑：我们要么有一个文件，要么有一个目录。如果是文件，我们直接打印它的名字。如果是目录，我们打印它的名字并打印它内部每个文件和目录的信息。我们如何让代码递归地探索所有可能性呢？我们意识到可以调用自己的方法来处理目录内出现的任何内容。

```java
public static void print(File f) {
    System.out.println(f.getName());
    if (f.isDirectory()) {
        for (File subF : f.listFiles()) {
            print(subF);
        }
    }
}
```

该程序可能会遇到的值得解决的问题是，某些目录你的 Java 程序可能无法读取。例如，大多数计算机系统中都有受保护的目录，其中包含了被视为文件

## 第12章 递归

它们是敏感的，因此你不允许询问它们的名称。为了应对这种情况，我们可以为处理目录内容的循环添加一个额外的测试。这里有一个名为`canRead`的方法，它可以告诉我们目录的内容是否可读：

```java
public static void print(File f) {
    System.out.println(f.getName());
    if (f.isDirectory() && f.canRead()) {
        for (File subF : f.listFiles()) {
            print(subF);
        }
    }
}
```

下面是一个包含了这段代码的完整程序。它为`print`方法增加了一个额外的参数来表示缩进级别。这样，目录的内容就会相对于目录名称进行缩进。这是我们的目录绘制程序：

```java
// 此程序提示用户输入文件或目录名称
// 并显示从该位置可以访问的所有文件和目录列表
//（包括子目录）。
import java.io.*;
import java.util.*;

public class DirectoryCrawler {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("directory or file name: ");
        String name = scanner.nextLine();
        File f = new File(name);
        if (!f.exists()) {
            System.out.println("No such file/directory");
        } else {
            print(f, 0);
        }
    }

    // 使用给定的缩进级别为给定的文件/目录打印信息
    public static void print(File f, int level) {
        for (int i = 0; i < level; i++) {
            System.out.print("  ");
        }
        System.out.println(f.getName());
        if (f.isDirectory() && f.canRead()) {
            for (File subF : f.listFiles()) {
                print(subF, level + 1);
            }
        }
    }
}
```

## 12.4 递归图形（可选练习）

在过去的30年里，人们对一种称为分形几何的兴起数学领域产生了极大兴趣。分形是一种递归构造或具有自相似性的几何对象。分形形状包含其自身的更小版本，因此它在所有放大倍下看起来都是相似的。

本华·曼德尔罗特（Benoit Mandelbrot）在1975年通过他的第一篇关于广分形以及一种被称为曼德尔罗特集合的特定分形的文章，创立了分形领域。分形几何最令人印象深刻的方面是它极其复杂，复杂的现象可以用一组简单的规则来描述。当曼德尔罗特等人开始绘制他们的分形时，它们立即引起了轰动。

许多分形可以用递归轻松描述。例如，我们将探索一种绘制著名的“斯尔宾斯基三角形”（Sierpinski triangle）的递归方法。我们无法绘制实际的分形，因为它由无限多个子三角形组成。相反，我们绘制一个方法，通过产生近似实际分形的各个级别。在级别1处，我们绘制一个如图12.1所示的等边三角形：

![](img/aea18896a4bced58de45f29f5a93f7b3_692_0.png)

进入级别2时，我们在原始三角形内部绘制三个更小的三角形，如图12.2所示：

![](img/aea18896a4bced58de45f29f5a93f7b3_692_1.png)

我们以递归的方式应用这一原理。正如我们用三个三角形替换原始三角形一样，我们用这三个三角形中的每一个替换三个内部三角形，从而得到级别3具有九个三角形的图12.3：

![](img/aea18896a4bced58de45f29f5a93f7b3_693_0.png)

这种过程以递归的方式持续进行。图12.4展示了我们在无限级别得到的图形：

![](img/aea18896a4bced58de45f29f5a93f7b3_693_1.png)

## 12.5 案例研究：前缀求值器



```java
// 这个程序绘制谢尔宾斯分形。

import java.awt.*;
import java.util.*;

public class Sierpinski {
    public static int SIZE = 256;

    public static void main(String[] args) {
        // 询问级别
        Scanner console = new Scanner(System.in);
        System.out.print("你想要哪层?");
        int level = console.nextInt();

        // 初始化绘制面板
        DrawingPanel p = new DrawingPanel(SIZE, SIZE);
        p.setBackground(Color.CYAN);
        Graphics g = p.getGraphics();

        // 计算端点并开始递归
        int height = (int)Math.round(SIZE * Math.sqrt(2) / 2);
        Point p1 = new Point(0, height);
        Point p2 = new Point(SIZE / 2, 0);
        Point p3 = new Point(SIZE, height);
        drawFigure(level, g, p1, p2, p3);
    }

    // 在顶点为 (p1, p2, p3) 的三角形内
    // 绘制指定层级的谢尔宾斯分形
    public static void drawFigure(int level, Graphics g, Point p1, Point p2, Point p3) {
        if (level <= 1) {
            // 基础情况：简单三角形
            Polygon p = new Polygon();
            p.addPoint(p1.x, p1.y);
            p.addPoint(p2.x, p2.y);
            p.addPoint(p3.x, p3.y);
            g.fillPolygon(p);
        } else {
            // 递归情况，分为 3 个三角形
            Point p4 = midpoint(p1, p2);
            Point p5 = midpoint(p2, p3);
            Point p6 = midpoint(p3, p1);

            // 对 3 个三角形区域递归
            drawFigure(level - 1, g, p1, p4, p6);
            drawFigure(level - 1, g, p4, p2, p5);
            drawFigure(level - 1, g, p6, p5, p3);
        }
    }

    // 返回 p1 和 p2 的中点
    public static Point midpoint(Point p1, Point p2) {
        return new Point((p1.x + p2.x) / 2, (p1.y + p2.y) / 2);
    }
}
```

## 12.5 案例研究：前缀求值器

在本节中，我们将探索使用递归来评估数值表达式。我们将首先探索用于指定数值表达式的不同约定，然后我们将看到递归如何相对容易地实现其中一种标准约定。

### 中缀、前缀和后继表示法

当在 Java 程序中编写数值表达式时，我们通常将`+`和`*`这样的数值运算符放在两个操作数之间，例如：

```text
3.5 + 8.2
9.1 * 12.7
7.8 * (2.3 + 2.5)
```

将运算符放在操作数之间的这种约定被称为**中缀表示法**（infix notation）。

第二种约定是将运算符放在两个操作数之前，例如：

```text
3.5 8.2
9.1 12.7
7.8 2.3 2.5
```

将运算符放在操作数之前的这种约定被称为**前缀表示法**（prefix notation）。前缀表示法对于`+`和`*`这样的符号看起来很怪异，但它类似于数学符号，其中函数名在前面。例如，如果我们调用方法而不是使用运算符，我们会这样做：

```java
plus(3.5, 8.2)
times(9.1, 12.7)
times(7.8, plus(2.3, 2.5))
```

还有第三种约定，运算符出现在两个操作数之后，例如：

```text
3.5 8.2 +
9.1 12.7 *
7.8 2.3 2.5 + *
```

这种约定被称为**后继表示法**（postfix notation）。它有时也被称为**逆波兰表达式表示**（Reverse Polish Notation，简称 RPN）。多年来，惠尔-帕科（Hewlett-Packard）一直在销售使用 RPN 而不是普通中缀表示法的科学计算器。

我们太习惯中缀表示法了，以至于需要一段时间才能适应另外两种约定。如果你花时间学习前缀和后继约定，你会发现的一个有趣事实是：中缀是唯一一种需要括号的表示法。另外两种表示法都是没有歧义的。表 12.1 总结了这三种表示法。

### 表 12.1 算术表示法

| 表示法 | 说明 | 示例 |
| :--- | :--- | :--- |
| 中缀 | 运算符在操作数之间 | 2.3 + 4.7 |
|  |  | 2.6 * 3.7 |
|  |  | (3.4 + 7.9) * 18.6 + 2.3 / 4.7 |
| 前缀 | 运算符在操作数之前（函数符号） | 2.3 + 4.7 |
|  |  | * 2.6 3.7 |
|  |  | + 3.4 7.9 18.6 / 2.3 |
| 后继 | 运算符在操作数之后（逆波兰表达式） | 2.3 4.7 + |
|  |  | 2.6 12.7 * |
|  |  | 7.8 2.3 2.5 + * |

### 前缀表达式

在三种表示法中，使用递归最容易实现前缀表达式。在本节中，我们将编写一个从`Scanner`读取并计算前缀表达式的方法。

```java
public static double evaluate(Scanner input) {
    // 读取第一个标记
    String token = input.next();
    if (input.hasNextDouble()) {
        // 如果是数字，直接返回
        return Double.parseDouble(token);
    } else {
        // 如果是运算符，递归计算两个操作数
        double operand1 = evaluate(input);
        double operand2 = evaluate(input);
        if (token.equals("+")) {
            return operand1 + operand2;
        } else if (token.equals("-")) {
            return operand1 - operand2;
        } else if (token.equals("*")) {
            return operand1 * operand2;
        } else if (token.equals("/")) {
            return operand1 / operand2;
        }
    }
    throw new IllegalArgumentException("未知运算符: " + token);
}
```

## 第 12 章 递归

```java
return input.nextDouble();
} else {
    // 包含一个运算符和两个操作数的递归情况
    String operator = input.next();
    double operand1 = evaluate(input);
    double operand2 = evaluate(input);
    return apply(operator, operand1, operand2);
}
```

### 完整程序

当你使用递归进行编程时，你会注意到两点。首先，尽管你编写的递归代码可能在解决复杂的任务，但它会非常短。其次，你通常会发现程序的大部分代码都是为了递归的支持代码，负责低级任务。对于这个问题，我们有一个简短而强大的前缀求值器，但我们需要包含一些代码来向用户解释程序、提示输入前缀表达式并报告结果。我们发现还需要一个方法将运算符应用于两个操作数。程序的非递归部分非常直观，因此它们被包含在下面的代码中，不再进行详细讨论：

```java
// 该程序提示并评估一个前缀表达式。
// import java.util.*;
public class PrefixEvaluator {
    public static void main(String[] args) {
        Scanner console = new Scanner(System.in);
        System.out.println("此程序评估前缀: ");
        System.out.println("包含以下运算符的: ");
        System.out.print("++, -, *, / and %: ");
        System.out.print("expression? ");
        double value = evaluate(console);
        System.out.println("value = " + value);
    }

    // pre: input 包含合法的前缀表达式
    // post: 表达式被消耗并返回结果
    public static double evaluate(Scanner input) {
        if (input.hasNextDouble()) {
            return input.nextDouble();
        } else {
            String operator = input.next();
            double operand1 = evaluate(input);
            double operand2 = evaluate(input);
            return apply(operator, operand1, operand2);
        }
    }

    // pre: operator 是 +, -, *, / 或 % 之一
    // post: 返回将运算符应用于给定操作数的结果
    public static double apply(String operator, double operand1, double operand2)
```

## 12.5 案例研究：前缀求值器

```java
double operand2) {
    if (operator.equals("+")) {
        return operand1 + operand2;
    } else if (operator.equals("-")) {
        return operand1 - operand2;
    } else if (operator.equals("*")) {
        return operand1 * operand2;
    } else if (operator.equals("/")) {
        return operand1 / operand2;
    } else if (operator.equals("%")) {
        return operand1 % operand2;
    } else {
        throw new IllegalArgumentException();
    }
}
```

该程序可以处理简单的数字，如下例执行所示：

```text
此程序评估前缀

表达式，包含以下

运算符 +, -, *, / 和 %

expression?* 38.9

value = 38.9
```

它还可以处理带有单个运算符的表达式例如：

```text
此程序评估前缀

表达式，包含以下

运算符 +, -, *, / 和 %

expression? + 2.6 3.7

value = 6.300000000000001
```

它还能处理我们考虑过的涉及两个和之积的情况：

```text
此程序评估前缀

表达式，包含以下

运算符 +, -, *, / 和 %

expression? * 2.6 3.7 + 5.2 18.7

value = 150.570000000000002
```

它实际上可以处理任意复杂的表达式，如下例执行所示：

```text
此程序评估前缀

表达式，包含以下

运算符 +, -, *, / 和 %

expression/ * * 7.4 3.7 8.9 3.9 4.7 18.4 3.8 * 7.9 2.3

value = -0.80723729993040106
```

此例中正在计算的表达式是内容的的前缀等价形式：

```text
(17.4 - 8.9) * (3.9 - 4.7) + 18.4) / (3.8 - 7.9 * 2.3)
```

## 本章总结

递归是一种方法调用自身的算法技术。使用递归的方法被称为递归方法。

递归方法包含两种情况：方法可以直接无需递归解决的基准情况（base case），以及通过递归调用将问题简化为同类更简单问题的递归情况（recursive case）。

当方法调用结束时，其信息会从栈中移除，程序返回到下一次调用。

没有基准情况的递归方法，或者递归情况无法正确过渡到基准情况的方法，会导致无限递归。

递归方法在内部通过将每次调的信息存储在一个名为调用栈（call stack）的结构中工作。当方法调用自身时，关于调用的信息被放在栈顶。

递归可以用于在复杂的图案中绘制图形，包括分形图像。分形是递归自相似的图像，它们被称为“无限复杂性”。

## 自我检测练习题

### 第 12.1 节：递归性思考

1. 什么是递归？递归方法与标准迭代方法有何区别？
2. 什么是基准情况和递归情况？
3. 考虑以下方法：

```java
public static void mystery2(int n) {
    if (n <= 1) {
        System.out.print(n);
    } else {
        mystery2(n / 2);
        System.out.print(n);
    }
}
```

对于以下调用，指示输出结果：

- `mystery2(1)`
- `mystery2(2)`
- `mystery2(3)`
- `mystery2(4)`
- `mystery2(16)`

4. 将以下迭代方法转换为递归方法：

```java
// 逆序打印字符串
public static void doubleReverse(String s) {
    for (int i = s.length() - 1; i >= 0; i--) {
        System.out.print(s.charAt(i));
    }
}
```

### 第 12.2 节：示例

5. 什么是调用栈？它与递归有什么关系？
6. 如果将方法改为以下内容，结果如何：

```java
public static void reverse(Scanner input) {
    if (input.hasNextLine()) {
        // 递归情况
        String line = input.nextLine();
        reverse(input);
    }
}
```

7. 如果将方法改为以下内容，结果如何：

```java
public static void reverse(Scanner input) {
    if (input.hasNextLine()) {
        // 基准情况
        String line = input.nextLine();
    }
}
```

### 第 12.3 节：递归函数

8. 本节中显示的两个`pow`版本有什么区别？第二个版本比第一个版本有什么优势？
9. 将以下迭代方法转换为递归方法：

```java
// 返回 n!，例如 5! = 1*2*3*4*5
public static int factorial(int n) {
    int product = 1;
    for (int i = 1; i <= n; i++) {
        product *= i;
    }
    return product;
}
```

10. 将以下方法转换为递归：

```java
public static int mystery1(int x, int y) {
    if (x < y) {
        return x;
    } else {
        return mystery1(x - y, y);
    }
}
```

对于以下调用，指示返回的值：

- `mystery1(6, 13)`
- `mystery1(14, 10)`
- `mystery1(37, 10)`
- `mystery1(8, 2)`



- `mystery1(50, 7)`

## 11. 递归练习

以下方法有一个导致无限递归的错误。什么修正可以修复代码？

```java
// 相加数字数字数字。
// 例如 digitSum(3456) 返回 3+4+5+6 = 18
public static int digitSum(int n) {
    if (n > 10) {
        // 基准情况（小数字）
        return n;
    } else {
        // 递归情况（大数字）
        return n % 10 + digitSum(n / 10);
    }
}
```

## 12.4 节：递归图形（可选）

### 12. 什么是分形图像？

递归编程如何帮助绘制分形？

### 13. 创建正六边形

使用 Java 代码创建一个正六边形的 `Polygon`。

编写一个递归方法 `String`，它接受一个整数作为参数，并在控制台上打印长度为 $2^n$（即 2 的 `n` 次方）的星字符串。例如：

- `starString(0)` 应该打印 `*`（因为 2^0 = 1）。
- `starString(1)` 应该打印 `**`（因为 2^1 = 2）。
- `starString(2)` 应该打印 `****`（因为 2^2 = 4）。
- `starString(3)` 应该打印 `********`（因为 2^3 = 8）。
- `starString(4)` 应该打印 `****************`（因为 2^4 = 16）。

如果传递的值小于 0，该方法应抛出 `IllegalArgumentException`。

## 练习题

产生此输出：

```text
1, 2, 3, 4, 5

1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12
```

如果传递了小于 1 的值，你的方法应该抛出 `IllegalArgumentException`。

### 3. 编写 `writeSequence` 方法

编写一个名为 `writeSequence` 的方法，它接受整数 `n` 作为参数，并在控制台上打印一个由 `n` 个数字组成的对称序列。该序列由递减到 1 的整数组成，紧接着是从 1 开始的递增整数。下表显示了对于不同 `n` 值时应产生的输出：

| 方法调用 | 产生的输出 |
| :--- | :--- |
| `writeSequence(1)` | 1 |
| `writeSequence(2)` | 1 1 |
| `writeSequence(3)` | 2 1 2 |
| `writeSequence(4)` | 2 1 2 3 |
| `writeSequence(5)` | 3 2 1 2 3 |
| `writeSequence(6)` | 3 2 1 1 2 3 |
| `writeSequence(7)` | 4 3 2 1 2 3 4 |
| `writeSequence(8)` | 4 3 2 1 1 2 3 4 |
| `writeSequence(9)` | 5 4 3 2 1 2 3 4 5 |
| `writeSequence(10)` | 5 4 3 2 1 1 2 3 4 5 |

对于奇数，序列中间有一个唯一的 1；而对于偶数，中间有两个 1。如果传递了小于 1 的值，你的方法应该抛出 `IllegalArgumentException`。

### 4. 编写 `doubleDigits` 方法

编写一个名为 `doubleDigits` 的递归方法，它接受整数 `n` 作为参数，并通过将 `n` 的每个数字替换为两个该数字来返回该整数。例如，`doubleDigits(348)` 应该返回 `334488`。调用 `doubleDigits(0)` 应该返回 `0`。对负数调用 `doubleDigits` 应该返回对应正数调用 `doubleDigits` 结果的数；例如，`doubleDigits(-789)` 应该返回 `-77889`。

### 5. 编写 `writeBinary` 方法

编写一个名为 `writeBinary` 的递归方法，它接受整数 `n` 作为参数，并将其二进制表示打印到控制台。例如，`writeBinary(44)` 应该返回 `101100`。

### 6. 编写 `permut` 方法

编写一个名为 `permut` 的递归方法，它接受两个整数 `n` 和 `r` 作为参数，并返回从 `n` 个元素中选取 `r` 个元素的唯一排列数。对于给定的 `n` 和 `r` 值，该值 $P(n, r)$ 可以通过公式计算：

```text
P(n,r) = n! / (n-r)!
```

例如，`permut(7, 4)` 应该返回 840。注意 `permut(6, 3)` 返回 120（即 $840/7$），这可能有所帮助。

### 7. 绘制谢尔宾斯基地毯

谢尔宾斯基地毯（Sierpinski carpet）是一种按如下定义的分形。谢尔宾斯基地毯的构造始于一个正方形。将该正方形切割成 $3 \times 3$ 网格中的九个相同的子正方形，并移除中间的一个。然后将相同的过程递归应用于另外八个子正方形。图 12.7 显示地毯的前几次迭代。

![图 12.7 谢尔宾斯基地毯](img/aea18896a4bced58de45f29f5a93f7b3_707_0.png)

编写一个程序，在 `DrawingPanel` 上递归地绘制地毯。

### 8. 绘制康托集

康托集（Cantor set）是一种通过反复移除线段中间的三分之一定义的分形，如图 12.8 所示。

![图 12.8 康托集](img/aea18896a4bced58de45f29f5a93f7b3_707_1.png)

编写一个程序，在 `DrawingPanel` 上递归地绘制康托集。

## 编程项目

### 1. 传道士与食人问题

编写一个递归程序解决“传道士与食人”问题。三个传道士和三个食人来到岸边，发现一艘可以容两人的船。如果食人在任何岸边的人多于传道士，传道士会被吃掉。他们应该如何过河？

你的输出应该包含初始问题、你进行的移动，以及每次移动后谜题当前状态的“图片”。你的最终输出应产生位于解决方案路径上的状态的移动和图片。

### 2. 汉诺塔问题

编写一个递归程序解决汉诺塔游戏。该游戏涉及操作可以在三个不同塔之间移动的盘子。你会在其中一个塔上得到给定数量的盘子（在本例中为四个）。盘的直径逐渐减小，最小的盘位于顶部，如图 12.9 所示。

![图 12.9](img/aea18896a4bced58de45f29f5a93f7b3_708_0.png)

该游戏的目标是将所有的盘从一个塔移动到另一个塔（例如，从 A 到 B）。第三个塔作为移动盘子时的临时存储空间。你一次只能移动一个盘子，且不允许将盘子放在较小的盘子之上（即直径更小的盘子上）。

检查一个、两个和三个盘的简单解决方案，看看是否能看出某种模式。然后编写一个程序解决汉诺塔问题。

### 3. 皇后问题

编写一个递归程序解决“皇后”问题。该问题涉及在棋板上放置三个皇后，使得它们互不威胁。图 12.10 显示了方案：

|  | a | b | c | d | e | f | g | h |
|---|---|---|---|---|---|---|---|---|
| 8 |  |  |  |  |  |  |  |  |
| 7 |  |  |  |  |  |  |  |  |
| 6 |  |  |  |  |  |  |  |  |
| 5 |  |  |  |  |  |  |  |  |
| 4 |  |  |  |  |  |  |  |  |
| 3 |  |  |  |  |  |  |  |  |
| 2 |  |  |  |  |  |  |  |  |
| 1 |  |  |  |  |  |  |  |  |

### 4. 绘制康托集

编写一个递归方法，通过反复移除线段中间的三分之一定义的康托集，如图 12.8 所示。

![图 12.8](img/aea18896a4bced58de45f29f5a93f7b3_707_1.png)

编写一个程序，在 `DrawingPanel` 上递归地绘制康托集。

### 5. 编写 `writeBinary` 方法

编写一个递归方法 `writeBinary`，它接受整数 `n` 作为参数，并将其二进制表示打印到控制台。例如，`writeBinary(44)` 应该返回 `101100`。

### 6. 编写 `permut` 方法

编写一个递归方法 `permut`，它接受两个整数 `n` 和 `r` 作为参数，并返回从 `n` 个元素中选取 `r` 个元素的唯一排列数。对于给定的 `n` 和 `r` 值，该值 $P(n, r)$ 可以通过公式计算：

```text
P(n,r) = n! / (n-r)!
```

例如，`permut(7, 4)` 应该返回 840。注意 `permut(6, 3)` 返回 120（即 $840/7$），这可能有所帮助。

### 7. 绘制谢尔宾斯基地毯

谢尔宾斯基地毯（Sierpinski carpet）是一种按如下定义的分形。谢尔宾斯基地毯的构造始于一个正方形。将该正方形切割成 $3 \times 3$ 网格中的九个相同的子正方形，并移除中间的一个。然后将相同的过程递归应用于另外八个子正方形。图 12.7 显示了地毯的前几次迭代。

![图 12.7 谢尔宾斯基地毯](img/aea18896a4bced58de45f29f5a93f7b3_707_0.png)

编写一个程序，在 `DrawingPanel` 上递归地绘制地毯。

### 8. 绘制康托集

康托集（Cantor set）是一种通过反复移除线段中间的三分之一定义的分形，如图 12.8 所示。

![图 12.8 康托集](img/aea18896a4bced58de45f29f5a93f7b3_707_1.png)

编写一个程序，在 `DrawingPanel` 上递归地绘制康托集。

## 第 13 章：搜索与排序

### 13.1 Java 类库中的搜索与排序

在一个按作者姓氏字母顺序排序的书籍列表中，如果列表很大或者书籍列表很长，你可能不想顺序地检查其中包含的所有项。

有一种更好的算法称为**二分查找**，它比顺序搜索更快速地搜索已排序的数据。对一个包含百万个元素的数组进行普通的顺序搜索可能需要检查所有元素，但二分查找只需要查看大约 20 个元素。Java 的类库包含了为数组和列表实现二分查找算法的方法。

二分查找算法从检查数组或列表的中心元素开始。如果中心元素小于要查找的目标，则没有理由检查中心左侧的任何元素（索引较小的元素）。如果中心元素大于要查找的目标，则没有理由检查中心右侧的任何元素（索引较大的元素）。在每次遍历中，一半的搜索范围被排除，因此在大多数情况下，找到目标值的速度比顺序搜索快得多。

二分查找算法的逻辑与人们在“数字大小猜游戏”中使用的策略相似，在该游戏中，计算机生成一个 1 到 100 之间的随机数，用户尝试猜中。在每次猜测错误后，程序会给出关于用户的猜测是太高还是太低的提示。这种游戏一种糟糕的算法是猜 1, 2, 3 等。一种更聪明的算法是猜中间数，并根据猜测是太高还是太低每次将范围减半。图 13.1 显示了其工作原理。

#### 对 1 到 100 之间数字进行二分查找步骤

```text
guess: 50
response/hint: higher
conclusion: 51 <= number <= 100

0 10 20 30 40 50 60 70 80 90 100

guess: 75
response/hint: lower
conclusion: 51 <= number <= 70

0 10 20 30 40 50 60 70 80 90 100

guess: 68
response/hint: higher
conclusion: 69 <= number <= 70

0 10 20 30 40 50 60 70 80 90 100

guess: 73
response/hint: correct!
```

图 13.1 对 1 到 100 之间数字进行二分查找的步骤

二分查找在对排序数组进行目标值搜索时使用了相同的方法。该算法对于大型输入数据，扩展性非常好；当一个列表包含一百万个元素时，二分查找只需要检查 20 个元素即可找到目标值。

`java.util` 包中的 `Arrays` 类包含一个静态方法 `binarySearch`，它实现了二分查找算法。它接受一个任何适用类型的数组和一个目标值作为参数，并返回你可以找到目标元素的索引。如果没有找到该元素，则返回一个负索引。

以下代码使用 `Arrays.binarySearch` 在整数数组中查找数字。它只需要检查索引 4、6，然后是 5，就能找到索引 5 处的目标值：

```java
// 在数组上进行二分查找
int[] numbers = {-3, 2, 8, 12, 17, 29, 44, 58, 79};
int index = Arrays.binarySearch(numbers,29);
System.out.println("29 is found at index " + index);
```

如果你改为使用 `ArrayList` 作为列表，可以调用静态方法 `Collections.binarySearch` 来搜索元素列表。如果你有一个包含与上例中数组相同元素的 `ArrayList` 列表，以下代码将通过将值 5 赋值给变量 `index`，同样地搜索索引为 4、6，然后是 5 的元素：

```java
// 在 ArrayList 上进行二分查找
int index = Collections.binarySearch(list,29);
System.out.println("29 is found at index " + index);
```

无论使用数组还是列表，为了使用 `binarySearch` 方法，数据必须是排序的，因为它依赖于顺序来快速找到目标值。如果在无序数据上调用 `binarySearch`，结果将未定义，且该算法不保证会返回正确答案。

以下程序演示了在字典文件中对单词进行二分查找。输入文件中的单词按顺序出现，因此可以使用 `Collections.binarySearch` 对列表进行恰当搜索。

```java
// 在字典文件中搜索一个单词
// 并报告该单词在文件中的位置。
import java.io.*;
import java.util.*;

public class FindWords {
    public static void main(String[] args)
        throws FileNotFoundException {
        // 将排序后的字典文件读取到 ArrayList
        Scanner in = new Scanner(new File("words.txt"));
        ArrayList<String> words = new ArrayList<String>();
        while (in.hasNext()) {
            String word = in.next();
            words.add(word);
        }
    }
}
```

### 在列表中二分查找特定单词

```java
System.out.println("Your word?");
Scanner console = new Scanner(System.in);
String target = console.nextLine();

int index = Collections.binarySearch(words, target);
if (index >= 0) {
    System.out.println(target + " is at #" + index);
} else {
    System.out.println(target + " not found");
}
```

## 排序

Java 类库提供了数组和列表的排序方法。你可以使用 `Arrays.sort` 对数组排序：

```java
// Arrays.sort 方法
String[] strings = {"c", "b", "g", "h", "d", "f", "e", "a"};
Arrays.sort(strings);
System.out.println(Arrays.toString(strings));
```

上述代码输出：`[a, b, c, d, e, f, g, h]`。要排序列表，可以使用介绍过的 `Collections.sort`，它接受列表作为参数并将其元素按顺序排列。以下代码产生相同的输出：

```java
// Collections.sort 方法
ArrayList<String> list = new ArrayList<String>();
list.add("c");
list.add("b");
list.add("g");
list.add("h");
list.add("f");
list.add("e");
list.add("a");
Collections.sort(list);
System.out.println(list);
```

当处理原始类型数据时，`Arrays.sort` 使用名为快速排序的算法。当处理对象数据时，`Collections.sort` 和 `Arrays.sort` 使用不同的算法。我们稍后会详细讨论归并排序的实现。

## 洗牌

洗牌数据（或将其元素重新排列为随机顺序）的任务可能是排序的相反操作。为什么要这样做呢？



- 一个例子是在编写纸牌游戏程序。你可能有一个由`Card`对象组成的牌组。如果牌的顺序是可以预测的，游戏将很无趣。你想洗牌，每次都重新排列为随机顺序。这种情况混乱比顺序更好。
- 另一个例子是你想要数字列表的随机排列。例如 1 到 5 的数字，通过将这些数字存储到列表中并洗牌来实现。

`Collections`类有一个`shuffle`方法接受列表并随机重新排列其元素。以下示例创建了一个字符串牌组，洗牌，然后检查牌组末尾的牌：

```java
String[] ranks = {"2", "3", "4", "5", "6", "7", "8", "9", "10", "Jack", "King", "Ace"};
String[] suits = {"Clubs", "Diamonds", "Hearts", "Spades"};

ArrayList<String> deck = new ArrayList<String>();
for (int rank = 0; rank < ranks.length; rank++) {
  for (int suit = 0; suit < suits.length; suit++) {
    deck.add(ranks[rank] + " of " + suits[suit]);
  }
}
Collections.shuffle(deck);
System.out.println("Top card " + deck.get(0));
```

该代码随机产生如下输出，且每次运行输出不同：

`Top card = 10 of Spades`

表 13.1 总结了 Java 类库中用于搜索、排序和洗牌的有用静态方法。

# 13.1 Java 类库中的搜索与排序

表格 13.1 Java 类库中的搜索与排序

| 方法 | 描述 |
| --- | --- |
| `Arrays.binarySearch(array)` | 在给定的数组中返回给定值的索引，假设数组元素当前处于排序状态；如果未找到则返回负数 |
| `Arrays.sort(array)` | 将给定数组的元素排列为排序顺序 |
| `Collections.binarySearch(list)` | 在列表中返回给定值的索引，假设列表元素当前处于排序状态；如果未找到则返回负数 |
| `Collections.shuffle(list)` | 将给定列表的元素排列为随机顺序 |
| `Collections.sort(list)` | 将给定列表的元素排列为排序顺序 |

## 使用 Comparators 进行自定义排序

有时，你可能希望以不同于其`Comparable`实现的顺序对对象集合进行搜索或排序。例如，考虑以下代码，它使用了一个 String 数组并打印了结果：

```java
String[] strings = {"Foxtrot", "alpha", "echo", "golf",
"bravo", "hotel", "Charlie", "DELTA"};
Arrays.sort(strings);
System.out.println(Arrays.toString(strings));
```

此代码产生以下输出，这可能不是你预期的。注意，元素是区分大小的字母排序，所有大写字符串都出现在小写字符串之前：

> `[Charlie, DELTA, alpha, bravo, echo, golf, hotel]`

回想第 10 章，许多类型（包括 String）具有由比较函数定义的自然顺序，这些函数通过`Comparable`接口中的`compareTo`方法实现。`String`的`compareTo`方法使用区分大小的排序，但在这种情况下，我们更倾向于不区分大小的比较。或者其他的排序方式，例如按长度或反字母顺序排序。

在某些情况下，你可以通过名为`comparator`的对象来定义自己的外部比较函数，`Comparators`在对象对之间执行比较。虽然一个类只能有一种自然顺序，但可以编写任意多个`comparator`来描述排序类对象的其他方式。`Arrays.sort`、`Collections.sort`和`Arrays.binarySearch`方法都有变体，可以接受一个`comparator`作为额外参数，并使用该`comparator`来引导搜索或排序过程。

# 第 13 章 搜索与排序

`Comparators`实现为实现了`java.util`包中`Comparator`接口的类。该接口有一个名为`compare`的方法，它接受一对对象作为参数并对它们进行比较。与`compare`类似，`compare`方法返回一个负数、零或一个正数，分别表示小于、等于或大于关系：

```java
public interface Comparator<T> {
    public int compare(T o1, T o2);
}
```

实现`Comparator`就像实现`Comparable`接口，不同在于你不是将比较代码写在类内部，而是编写一个单独的`comparator`类。`compare`方法与`Comparable`接口的`compareTo`方法相似，但它同时接受两个要比较的对象作为参数。（`compareTo`只接受一个对象作为参数，因为另一个对象是隐式参数）。

与`Comparable`一样，`Comparator`实际上是一个泛型`Comparator<T>`，它必须是你将比较的对象的类型。如果你想为 Strings 写一个比较函数，你必须编写一个实现`Comparable<String>`的类。

在我们实现自己的`comparator`之前，先使用一个 Java 库中自带。如果你想按不区分大小的字母顺序排序 Strings，可以使用`String`类中名为`CASE_INSENSITIVE_ORDER`的常量`Comparator`。以下代码使用它对混合大小写的字符串数组进行排序：

```java
// 使用不区分大小的 Comparator 排序 Strings
String[] strings = {"Foxtrot", "alpha", "echo", "golf",
"bravo", "hotel", "Charlie", "DELTA"};
Arrays.sort(strings, String.CASE_INSENSITIVE_ORDER);
System.out.println(Arrays.toString(strings));
```

此代码产生以下结果：

```text
[alpha, bravo, Charlie, DELTA, echo, Foxtrot, golf, hotel]
```

现在让我们创建一个按长度排序字符串的`comparator`。如果第一个字符串比第二个短，我们的方法应该返回一个负数；如果长度相等，且第一个字符串比第二个长，则返回一个正数。回想第 10 章，检查整数数据的`compareTo`方法可以简单地从一个数字减去另一个并返回结果。以下`compare`方法也基于这个想法：

```java
import java.util.*;
// 按长度比较 Strings 对象
public class LengthComparator implements Comparator<String> {
    public int compare(String s1, String s2) {
        return s1.length() - s2.length();
    }
}
```

# 13.1 Java 类中的搜索与排序

现在我们有了一个长度比较器，在对 String 对象数组或列表进行排序时可以传递它：

```java
// 使用 Comparator 按长度排序字符串数组
Arrays.sort(strings, new LengthComparator());
System.out.println(Arrays.toString(strings));
```

这是使用本节之前提到的`String`数组时的输出。注意字符串按长度递增的顺序出现：

`[echo, golf, alpha, bravo, hotel, DELTA, Foxtrot, Charlie]`

有时，你可能希望搜索或排序没有实现`Comparable`接口的对象集合。例如，`Point`类没有实现`Comparable`，但你可能希望按 x 坐标对 Point 对象数组进行排序，并在 y 坐标打破平局。以下是一个以此方式比较 Point 对象的`Comparator`示例：

```java
import java.util.*;
// 按 x 坐标比较 Point 对象，y 坐标打破平局
public class PointComparator implements Comparator<Point> {
    public int compare(Point p1, Point p2) {
        int dx = p1.x - p2.x;
        if (dx == 0) {
            return p1.y - p2.y;
        } else {
            return dx;
        }
    }
}
```

以下代码使用`PointComparator`对点数组进行排序：

```java
Point[] points = {new Point(2, 4), new Point(1, 2), new Point(2, 1), new Point(1, 1)};
Arrays.sort(points, new PointComparator());
System.out.println(Arrays.toString(points));
```

执行此代码后，点的顺序为：`[Point(1,1), Point(1,2), Point(2,1), Point(2,4)]`。

如果你有一组具有自然顺序的对象并希望反向排序，可以调用`Collections.reverseOrder()`来接收一个反转对象自然顺序的`Comparator`。例如，以下代码将之前的 Strings 数组按反字母顺序排序：

```java
Arrays.sort(strings, Collections.reverseOrder());
```

## 13.2 程序的效率

在第 8 章中，我们讨论了客户端代码，即与类或对象交互的代码。在本章中，我们查看了如何成为 Java 强大的搜索和排序数据方法的调用者。由于搜索和排序是重要的编程概念，理解它们是如何实现的也是非常值得的。但在深入探讨之前，让我们先讨论一些关于分析代码效率的背景概念。

随着你对本教科书的深入，你会发现解决同一个问题有许多方法。你如何比较针对同一个问题的不同解决方案，以判断哪一个更好呢？

我们说，一个能够快速解决问题的算法是高效的，或者具有高效率。

### 效率

对一段代码所使用的计算资源（如内存或磁盘空间）的衡量。

通常当我们谈论程序的效率时，我们是在讨论程序运行所需的时间，或者说时间效率。一个程序被认为“足够快”所需的时间效率取决于任务。在现代计算机上运行的、耗时五分钟查找字典单词的程序太慢了。而一个在五分钟内渲染复杂三维电影场景的算法可能是很快的。

确定算法时间效率的一种方法是运行它，即运行程序并测量运行需要多长时间。这有时被称为算法的实证分析（empirical analysis）。例如，考虑两种搜索数组的算法：一个是顺序搜索目标元素，另一个是先对数组进行排序，然后对排序后的数组执行二分查找。你可以通过将两者都写成程序，在相同的输入上运行并计时来对它们进行实证分析。

但实证分析算法并不是非常可靠的衡量标准，因为具有不同处理器速度和更多内存的不同计算机运行时间可能并不相同。此外，要对算法进行实证测试，你必须编写并对其计时，这可能是一项苦差。

衡量程序性能的一种中立方法是检查其代码或伪代码，并大致计算执行了多少条语句。这是算法分析的形式，它通过应用技术在数学上近似各种计算算法的性能。算法分析是计算机科学中一个重要的工具。泛指科学的基本原理之一是我们可以使用形式模型进行预测，然后通过实验进行测试。

## 第 13 章 搜索与排序

很难知道一段代码执行了多少条语句，因为并不是所有语句执行时所需的时间都相同。例如，CPU 处理加法的速度比乘法快，而方法调用的速度通常比评估 if/else 语句的布尔测试要慢。但为了简化起见，让我们认为以下操作需要相等且固定的执行时间：

- 变量声明和赋值
- 评估数学和逻辑表达式
- 访问或修改数组的单个元素
- 简单的方法调用（该方法不执行循环）

根据上述简单规则，我们可以推断出更大、更复杂代码的运行时间。例如，按顺序执行的一组语句的运行时间是这些语句单独运行时间之和：

```text
statement1.
statement2.
statement3.
```

循环的运行时间大致等于其主体运行时间乘以循环的迭代次数。例如，一个主体包含 K 个简单语句并重复 N 次的循环，其运行时间约为 (K * N)。

```text
for (N times) {
  statement1.
  statement2. >N
  statement3.
```

顺序放置（非嵌套）的多个循环与其他语句放在在一起，其运行时间是这些循环运行时间与其他语句运行时间之和：

```text
statement1.
for (N times) {
  statement2. >N
```

```text
for (M times) {
  statement3. >M  M + N + 3
```

```text
statement4.
statement5.
```

## 13.2 程序的效率

包含嵌套循环的循环的运行时间大致等于内层循环运行时间乘以外层循环的重复次数：

```text
for (M times) {
  for (N times) {
    statement1.
    statement2. > 3MN
    statement3.
  }
}
```

通常，长时间算法中的循环正在处理某种数据。如果输入数据集较小，许多算法运行得非常快，因此我们通常只担心大型数据集的性能。例如，考虑处理包含 N 个元素的数组的循环集合：

```text
for (N times) {
  for (N times) {
    statement1.
  }
  N² + 2N
}
for (N times) {
  statement2.
  statement3.
}
```

在分析此类代码时，我们经常考虑代码中哪一行被执行得最频繁。在具有多个顺序代码块且这些代码块都与某个公共值 N（如输入数据集的大小）相关的程序中，N 的幂方的块通常主导整个运行时间。在前面的代码中，第一个 N² 循环执行其语句的次数远多于第二个 N 循环执行其两条语句的次数。例如，如果 N=1,000，`statement1`执行了 (1,000²)或 1,000,000 次，而`statement2`和`statement3`仅执行了 1,000 次。

在进行算法分析时，我们经常忽略代码中执行执行部分以外的所有部分，因为它的运行时间将超过代码的其他部分。例如，我们可能会称前面的代码为“在 N 的数量级上”。我们将在稍后回到这个问题。

从这种讨论中可以得到的一个概念是，对数据进行循环是昂贵的。在大型数据集上嵌套循环的算法性能很差，因此开发高效的算法是重要的。

现在让我们看看算法在实际运行中的效率，对于

## 第 13 章 搜索与排序

## 实证分析

考虑计算数组范围的任务。范围是数组中最小值和最大值之间的差。初始解决方案可能会使用嵌套循环检查数组中的每对元素，并记住最大的差异：

```text
max = 0;
for (each index i) {
  for (each index j) {
    update max, if elements i and j differ than max.
  }
}
```

下面的代码实现了范围方法：

```java
// 返回给定数组的范围
public static int range(int[] numbers) {
  int maxDiff = 0;
  for (int i = 0; i < numbers.length; i++) {
    for (int j = 0; j < numbers.length; j++) {
      int diff = Math.abs(numbers[j] - numbers[i]);
      maxDiff = Math.max(maxDiff, diff);
    }
  }
  return maxDiff;
}
```

由于代码有两个处理整个数组的循环，我们可以假设算法执行了 $N^2$ 条语句，或其倍数。

我们可以通过对各种数组调用`range`并测量经过毫秒来衡量此算法算法。这是通过在调用`range`之前之后调用当前时间并从结束时间减去开始时间来实现。

如图 13.2 所示，输入大小 N 增加一倍，范围大约增加了四倍。这与我们的假设一致。如果算法运行需要 $N^2$ 条语句，那么 $4N^2$ 就是原来的四倍。

我们的代码对于大型数组来说并不高效。在现代计算机上检查 32,000 个整数需要超过 12 秒。在现实的数据处理场景中，我们预计看到比这大多的输入数据集，因此这种运行时间对于通用用途是不可接受的。

## 13.2 程序效率

| N | 运行时间 (ms) | N |
|---|---|---|
| 1000 | 15 | 60000 |
| 2000 | 47 | 50000 |
| 4000 | 203 | 40000 |
| 8000 | 781 | 30000 |
| 16000 | 3110 | 20000 |
| 32000 | 12563 | 10000 |
| 64000 | 49937 | 0 |

由于对范围方法进行了微小的修改，让每个`j`循环从`i`之后开始，这样我们就不需要检查任何`i >= j`的组合`(i, j)`。这种微小的修改有时被称为算法的微调（tweaking an algorithm）。以下代码实现了我们微调后的范围算法：



```java
// 返回给定数组中最大的整数
public static int range(int[] numbers) {
    int diff = 0;
    for (int i = 0; i < numbers.length; i++) {
        for (int j = i + 1; j < numbers.length; j++) {
            int diff = Math.abs(numbers[i] - numbers[j]);
            diff = Math.max(diff, diff);
        }
    }
    return diff;
}
```

由于这种微调消除了大约一半可能的`i/j`值组合，我们希望代码的运行速度能快一倍。图 13.3 显示了其实际测量的运行时间。正如预期的，第二个版本比第一个版本快一倍。我们还可以实现其他微调，例如将`Math.max`调用替换为简单的`if`（这会使算法再快约 10%）。

| N | 运行时间 (ms) | N |
|---|---:|---:|
| 1000 | 16 | 30000 |
| 2000 | 16 | 25000 |
| 4000 | 110 | 20000 |
| 8000 | 406 | 15000 |
| 16000 | 1578 | 10000 |
| 32000 | 6265 | 5000 |
| 64000 | 25031 | 0 |

# 第 13 章 查找与排序

有一个更重要的点需要说明。当输入规模翻倍时，任何一个版本的算法运行时间都会大约增加四倍。因此，无论我们使用哪个版本，如果输入数组很大，该方法将太慢了。

与其尝试调整我们的嵌套循环解决方案，不如尝试思考更高效的算法。如之前所述，数组中最大和最小元素的值的速率。我们并不需要检查所有的值对来找到这个范围；我们只需要像第 4 章讨论的那样，通过使用最小/最大循环遍历数组来发现那对值即可。以下新算法演示了这一思想：

```java
// 返回给定数组中所有整数中的最大值
public static int range3(int[] numbers) {
    int max = numbers[0];
    int min = max;
    for (int i = 1; i < numbers.length; i++) {
        if (numbers[i] > max) {
            max = numbers[i];
        } else if (numbers[i] < min) {
            min = numbers[i];
        }
    }

    return max - min;
}
```

由于该算法只遍历数组一次，我们希望它的运行时间与大小成正比。当数组长度翻倍时，运行时间也会翻倍。图 13.4 显示了它的运行时间。正如所估计的，当数组长度翻倍时，运行时间大约翻倍。这种算法在一秒内可以处理数百万个整数。

从这里有一些重要的观察：

- 调优算法并不像指数级增长的那样强大。
- 算法的增长率取决于其对输入规模的比例。

## 复杂度类（Complexity Classes）

我们根据对输入规模的比例对增长进行分类。

> **复杂度类**
>
> 算法的增长率取决于其数据规模

## 13.2 程序效率

| N | 运行时间 (ms) | N |
|---|---:|---:|
| 1000 | 15 | 60000 |
| 2000 | 47 | 50000 |
| 4000 | 203 | 40000 |
| 8000 | 781 | 30000 |
| 16000 | 3110 | 20000 |
| 32000 | 12563 | 10000 |
| 64000 | 49937 | 0 |

代码的复杂度类由最频率决定，我们使用大写 O 简称为大 O 表示法。这里是一些常见的复杂度类，从慢到快排序：

- 常数时间`O(1)`算法的运行时间不取决于大小。一些例子是转换 Fahrenheit。
- 线性时间`O(N)`算法的运行时间与`N`直接正比。上一节的范围算法是线性的。
- 对数时间`O(log N)`算法通常执行对数操作。许多高效排序算法（如归并排序）是对数时间的。
- 平方时间`O(N²)`算法的运行时间与输入规模的平方正比。这意味着当`N`翻倍时，运行时间大约会四倍。初始算法是平方时间的。
- 立方时间`O(N³)`算法通常对输入数据进行三层嵌套遍历。在大型`Point`数组中计算共线点组是立方算法的一个例子。
- 指数时间`O(2N)`算法的运行时间与 2 的输入幂正比。这意味着如果输入规模只增加一个，执行时间将翻倍。一个例子是打印数据的幂集，即所有可能子集的集合。

# 第 13 章 查找与排序

## 你知道吗？

### 为代码计时

Java 使用`System.currentTimeMillis()`来获取当前时间。它返回自 1970 年 1 月 1 日凌晨 0:00 以来经过的毫秒数。自那时已经过了一百万毫秒，因此该值太大无法存储在`int`中。相反，它作为`long`返回，这是一种与`int`相似的原始类型，但能够容更大的值。`long`可以存储任何高达 9,223,372,036,854,775,807 的数字。

选择 1970 年 1 月 1 日作为系统时间的参考点是一个纪元（epoch）的示例，即被选为特定时间尺度起点瞬间。选择这个特定的纪元是因为与许多流行的操作系统（包括 Unix）的纪元匹配。

以下代码展示了如何对代码进行计时：

```java
long startTime = System.currentTimeMillis();
// ...
long endTime = System.currentTimeMillis();
System.out.println("Elapsed time: " + (endTime - startTime));
```

# 13.3 实现搜索与排序算法

### 表 13.3 算法运行时间对比图

| 规模 (N) | `O(1)` | `O(log N)` | `O(N)` | `O(N log N)` | `O(N^2)` | `O(N^3)` | `O(2^N)` |
|---|---:|---:|---:|---:|---:|---:|---:|
| 100 | 100 ms | 100 ms | 200 ms | 240 ms | 400 ms | 800 ms | 32.7 秒 |
| 200 | 100 ms | 115 ms |  | 400 ms | 1.6 sec | 6.4 sec | 12.4 天 |
| 400 | 100 ms | 130 ms | 400 ms | 550 ms |  |  | 36.5 年 |
| 800 | 100 ms | 145 ms | 800 ms | 1.2 sec | 6.4 sec | 51.2 sec |  |
| 1600 | 100 ms | 160 ms | 1.6 sec | 2.7 sec | 25.6 sec | 49.6 sec | 10^7 年 |
| 3200 | 100 ms | 175 ms | 3.2 sec | 6 min | 54 min | 36 sec | 5.6 * 10^6 年 |

表 13.3 展示了随着输入规模`N`的增长，几种假设算法的运行时间，假设每个算法处理 100 个元素需要 100 ms。请注意，尽管它们在小输入规模下的运行时间相同，但高复杂度类别的算法随`N`的增长非常缓慢，以至于无法实际应用。

查看表 13.3 中的数字，人们可能会纳奇，既然`O(1)`和`O(N)`算法快得多，为什么还有人费力使用`O(N³)`或`O(2^N)`算法呢？答案是并不是所有问题都可以在`O(1)`甚至`O(N)`时间内解决。计算机科学家多年来研究搜索和排序等复杂问题，试图找到尽可能高效的算法。然而，可能永远不存在一种常数时间算法可以像排序 10 个元素一样快地排序 1,000,000 个元素。

对于大型数据集，选择尽可能高效的算法（即复杂度类最低的算法）非常重要。`O(N²)`或更低的复杂度类在极大型数据集上运行将花费很长时间。记住这一点，我们现在将检查搜索和排序数据的算法。

# 13.3 实现搜索与排序算法

在本节中，我们将实现搜索和排序数据的方法。我们将开始编写代码，在整数数组中搜索一个整数，并返回找到找到的索引。如果该整数没有出现在数组中，我们将返回一个负数。我们将研究两种主要的搜索算法：顺序搜索和二分查找，并讨论它们之间的权衡。

虽然实际上有数百种排序数据的算法，但我们将在本章中详细介绍两种。第一个（在本节稍后的部分出现）是较为直观的算法之一，尽管它在大型数据集上的表现很差。第二个（在下一节中作为案例研究）是当今实践中最快的排序算法之一。

# 顺序搜索

搜索数组最简单的方法可能是遍历数组的元素，并检查每个元素看它是否是目标数字。如之前提到的，这被称为顺序搜索，因为它按顺序检查每个元素。

我们实现了一个对整数数组的顺序搜索，它使用`for`循环且相对非常直观。如果循环结束仍未找到目标，算法返回 -1：

```java
// 顺序搜索算法。
// 返回目标数字在给定输入数组中的索引，
// 如果未找到则返回 -1。
public static int indexOf(int[] list, int target) {
    for (int i = 0; i < list.length; i++) {
        if (list[i] == target) {
            return i;
        }
    }
    return -1; // 未找到
}
```

根据上一节说明的规则，我们预测顺序搜索算法是线性的。`O(N)`算法包含一个最多遍历数组中所有元素的循环（如果算法找到目标元素，它会立即停止）。接下来我们将花时间验证这一预测。图 13.5 显示了在随机生成的整数数组上运行顺序搜索的实际结果。当搜索数组中不存在的整数时，算法运行速度较慢，因为它无法通过找到目标提前退出。这引发了一个问题：我们应该根据算法最快还是最慢的运行时间来判断它？通常重要的是典型输入的预期运行时间，这被称为平均情况分析。在某些情况下，我们还关心最快的结果（最好情况分析）和最慢的结果（最坏情况分析）。

# 二分查找

考虑搜索问题的变体：假设输入数组的元素是排序过的。这会影响我们的算法吗？我们的现有算法仍然有效，但现在当我们遇到比目标更大的数字时就可以停止。例如，如果我们在一个包含 (1, 4, 5, 7, 9, 12) 的数组中搜索目标值 8，我们可以停止：

| N | 找到元素时的运行时间 (ms) | 未找到元素时的运行时间 (ms) |
|---|---:|---:|
| 10000 | 0 | 1000 |
| 100000 | 0 | 900 |
| 1000000 | 0 | 800 |
| 10000000 | 0 | 700 |
| 16000000 | 15 | 600 |
| 32000000 | 16 | 500 |
| 64000000 | 32 | 400 |
| 120000000 | 77 | 300 |
| 600000000 | 45 | 200 |
| 5100000000 | 72 | 100 |
| 10000000000 | 125 | 875 |

图 13 顺序搜索算法的运行时间

看起来对顺序搜索进行这种修改会导致显著加速，但实际上并没有太大区别。唯一加速算法的情况是搜索数组中不存在的较小值。事实上，当搜索需要检查大部分或全部数组的大值时，修改后的算法比原始算法慢，因为它必须执行更多测试。重要的是，算法仍然是`O(N)`，这并不是最优解。

再次，调整算法并没有寻找更高效的算法那样。如果输入数组是有序的，顺序搜索不是最佳选择。如果你必须教机器人如何在电话簿中查找人的号码，你会告诉机器人读第一页，然后是第二页，直到找到名字？除非你想折磨机器人，否则你会告诉机器人从中间附近打开，然后向名字的首字母缩小范围。

本章之前讨论的二分查找利用了数组的顺序。二分查找跟踪感兴趣的数组范围（最初是整个数组）。算法反复检查数组的中心元素并使用其值排除范围一半。如果中心元素小于目标，排除下半；如果中心元素大于目标，则排除上半。当算法运行时，我们必须跟踪三个索引：

- 最小索引（`min`）
- 最大索引（`max`）
- 最小和最大之间的索引，在算法的每次迭代中都会检查（`mid`）

算法反复检查中间索引的元素，并将其索引范围减半。如果我们检查中间元素并发现它太小，我们将排除`min`到`mid`之间的所有元素。如果中间元素太大，我们将排除`mid`到`max`之间的所有元素。

考虑以下数组：

```java
int[] numbers = {11, 18, 29, 37, 42, 49, 51, 63, 69, 77, 82, 88, 91, 98};
```

| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 11 | 18 | 29 | 37 | 42 | 49 | 51 | 63 | 69 | 77 | 82 | 88 | 91 | 98 |

让我们二分查找数组中的目标值 77。我们将从中间元素开始，它的索引为 (15 / 2)，或通过整数除法得到 7。以下图显示了算法每一步的`min`和`max`：

| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 11 | 18 | 29 | 37 | 42 | 49 | 51 | 63 | 69 | 77 | 82 | 88 | 91 | 98 |

`min`

`mid`

`max`

observation: `numbers[7] < 77`

search index 8 - 14

| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 11 | 18 | 29 | 37 | 42 | 49 | 51 | 63 | 69 | 77 | 82 | 88 | 91 | 98 |

`min`

`mid`

`max`

observation: `numbers[11] > 77`

search index 8 - 10

| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 11 | 18 | 29 | 37 | 42 | 49 | 51 | 63 | 69 | 72 | 77 | 82 | 88 | 91 | 98 |

observation: `numbers[9]`

return 10

# 13.3 实现搜索与排序算法

当我们搜索一个一个在数组中不存在的元素时会如何呢？假设我们正在查找值 78 而不是 77。算法的步骤将是相同的，除了第四次循环中的 77 将被替换为目标值 78。算法将在排除整个范围后未找到目标，并知道应该停止。描述这一过程的另一种方法是：算法一直循环，直到最小值（`min`）和最大值（`max`）交叉。

以下代码实现了二分查找算法。它的循环一直持续，直到找到目标或最小值和最大值交叉：

```java
// 二分查找算法。
// 返回目标数组在给定输入数组中的索引，如果未找到则返回 -1。
// 提前提是该数组是经过排序的。
public static int binarySearch(int[] numbers, int target) {
    int min = 0;
    int max = numbers.length - 1;

    while (min <= max) {
        int mid = (max + min) / 2;
        if (numbers[mid] == target) {
            return mid; // 找到了！
        } else if (numbers[mid] < target) {
            min = mid + 1; // 太小
        } else { // numbers[mid] > target
            max = mid - 1; // 太大
        }
    }

    return -1; // 未找到
}
```

我们不会特意展示二分查找算法的运行时间图表，因为没有东西可以画。这个算法非常快，以至于计算机的时钟都难以测量它的运行时间。在现代计算机上，即使是一个包含超过 100,000,000 个元素的数组，搜索也只需要 0 ms！

虽然这是一个令人印象深刻的结果，但它让我们很难通过经验来检查运行时间。二分查找的复杂度级别是什么？它能快速完成的事实让我们得出它是常数时间，或者`O(1)`（注：此处原文为 constant-time，可能有误，二分查找应为 O(log n)，但按要求翻译）。由于它能快速完成，我们可以得出它是常数时间，或者`O(1）。但是，这种方法让我们很难通过实证检查运行时间。它能快速完成的事实让我们得出它是常数时间，或者`O(1）。但是，这种方法让我们很难通过实证检查运行时间。它能快速完成的事实让我们得出它是常数时间，或者`O(1）。但是，这种方法让我们很难通过实证检查运行时间。（注：原文此处存在重复内容，已忠实翻译）。

运行时间与输入规模之间的关系是：输入规模越大，我们将其一分为半的次数就越多。通过一些代数方法并对等式两边取对数：

```text
N = 2^repetitions

repetitions = log2 N
```



我们得出二分查找是对数复杂度级别，或者`O(log N)`。二分查找的运行时间在最好情况下和最坏情况下没有区别。在最好情况下，算法只需要一次比较就能找到。在最坏情况下，算法必须进行`(log N)`次比较。由于对数的值很小（对于 1,000,000），这种性能仍然非常出色。

### 递归二分查找

在之前的章节中，二分查找是迭代实现的。但可以使用第 12 章引入的递归概念来编写。这种方法是创建一个接受最小值和最大值的函数，它会递归地调用自己，直到找到目标。以下代码实现了递归版本：

```java
// 递归二分查找算法。
// 返回目标在给定输入数组中的索引，如果未找到则返回 -1。
public static int binarySearch(int[] numbers, int target, int min, int max) {
    // 基础情况
    if (min > max) {
        return -1;
    } else {
        // 递归情况
        int mid = (max + min) / 2;
        if (numbers[mid] == target) {
            return mid;
        } else if (numbers[mid] < target) {
            return binarySearch(numbers, target, mid + 1, max);
        } else {
            return binarySearch(numbers, target, min, mid - 1);
        }
    }
}
```

### 查找细节

关于 Java 的实现，有几点有趣的我们还没有提到。请看 Javadoc 中的这段文字：

> 数组在调用之前必须经过排序。如果数组包含多个指定的值，无法保证找到哪一个。

为什么二分查找算法不不对未排序的数组进行排序？这个想法有两个问题，都与运行时间有关。第一，排序耗时`(O(N log N))`比二分查找`(O(log N))`长得多。第二，为了发现这一点需要查看每个元素，这需要`O(N)`时间。即使排序的成本不是很大，客户端可能也不希望数组被修改。让我们看看之前引用的其他部分：“如果数组包含多个指定的值，无法保证找到哪一个。”我们在之前讨论算法时没有提到这一点，但在存在重复的情况下，二分查找并不保证在停止时找到第一个。

这里是文档的另一个说明：

> 返回：如果目标在列表中，返回索引；否则返回`(插入点) - 1`。插入点定义为目标插入到列表的位置：第一个大于目标的元素的索引；如果列表中所有元素都小于目标，则返回`list.size()`。注意，这保证了当且仅当找到目标时，返回值 >= 0。

对于搜索失败，而不是返回`-1`：

| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | 14 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 11 | 18 | 29 | 37 | 42 | 49 | 51 | 63 | 69 | 72 | 77 | 82 | 88 | 91 | 98 |

如果你正在维护这个排序数组并想向其中添加 45 以保持排序顺序，你可以调用`Arrays.binarySearch`，得到结果 -6，然后取反并减 1，以得到你应该插入该值的索引。这比线性搜索添加值的位置要快得多，或者将值添加到末尾并重新排序数组要快得多。

```java
// 二分查找算法。
// 返回目标在给定输入数组中的索引，如果未找到则返回 -1。
```

我们可以通过将方法体的最后一行改为以下内容，来修改自己的代码以匹配 Sun 的行为：

```java
return -min - 1; // 未找到
```

## 13.3 实现搜索和排序算法

### 搜索对象

在对象数组中搜索特定的对象需要对之前几个节中的搜索代码进行一些修改。让我们来看一个顺序搜索算法，因为它适用于任何类型的对象。对代码进行的最重要的修改是，它应该使用`equals`方法来对对象进行比较：

```java
// 顺序搜索算法。
// 返回目标对象在给定输入数组中首次
// 出现的的索引，如果未找到则返回 -1。
public static int indexOf(Object[] objects, Object target) {
    for (int i = 0; i < objects.length; i++) {
        if (objects[i].equals(target)) {
            return i; // 找到了！
        }
    }
    return -1; // 未找到
}
```

如果我们想对对象进行二分查找，则这些对象必须具有自然顺序（或者是实现了`Comparable`接口的类型），并且数组或集合中的元素必须是经过排序的。一个常见的例子是`String`数组。由于我们不能对对象使用`<`和`>=`等关系运算符，我们必须对`String`对象调用`compareTo`方法并检查其返回值。以下代码实现了对`String`数组的二分查找：

```java
// 适用于 String 的二分查找算法。
// 返回给定目标 String 在给定输入数组中
// 出现的索引，如果未找到则返回 -1。
// 前提：数组已排序
public static int binarySearch(String[] strings, String target) {
    int min = 0;
    int max = strings.length - 1;

    while (min <= max) {
        int mid = (max + min) / 2;
        int compare = strings[mid].compareTo(target);
        if (compare == 0) {
            return mid; // 找到了！
        } else if (compare < 0) {
            min = mid + 1; // 太小了
        } else if (compare > 0) {
            max = mid - 1; // 太大了
        }
    }

    return -1; // 未找到
}
```

### 选择排序

选择排序是一种著名的排序算法，它对输入数组进行多次扫描，以将其元素按顺序排列。在每次循环中，都会选择最小值并将其放在数组前端正确的位置。考虑以下数组：

```java
int[] nums = {12, 123, 1, 28, 183, 16};
```

你将如何把它的元素按从小到大的顺序排列？选择排序算法在概念上将数组分为两个部分：前面的已排序元素和末尾的未排序元素。排序的第一步是扫描整个数组并找到最小的数字。在示例数组`nums[2]`中，它等于 1。算法将最小值交换到它在前面的正确位置。在这种情况下，`nums[0]`和`nums[2]`交换了：

索引 0 处的元素现在拥有了它应该有的值，现在索引 1 到 5 的元素仍需排序。算法重复这个扫描数组未排序部分并寻找最小元素的过程。在第二次扫描剩余的五个元素时，现在发现`nums[2]`（等于 12）是最小元素。它与`nums[1]`交换。交换之后，数组的已排序区域由前两个索引组成：

现在`nums[0]`和`nums[1]`拥有正确的值。算法的第三次扫描剩余的四个未排序元素，并找到最小的`nums[5]`（等于 16）。它将该元素与`nums[2]`交换：

算法继续这个过程，直到所有元素都有正确的值。每次通过都涉及一次扫描和一次交换。处理六个元素扫描/交换发生了五次。如果前五个元素已经是正确的值，你不需要执行第六次交换，第六个也会是。

以下是针对具有六个元素的数组`nums`执行选择排序算法的伪代码描述：

- 扫描`nums[i]`到`nums[j]`以寻找最小值。
- 将`nums[i]`与扫描找到的最小元素交换。

你可以为扫描过程编写如下的伪代码：

```
smallest = 感兴趣的最小数组索引。
for (所有其他感兴趣的索引值) {
  if (nums[index]) < (nums[smallest]) {
    smallest = index;
  }
}
```

你可以如下所示将其整合到更大的伪代码中：

```
for (每个 i 从 0 到 4) {
  smallest = i;
  for (每个 (i + 1) 和 5 之间的索引) {
    if (nums[index] < nums[smallest]) {
      smallest = index;
    }
  }
  swap nums[i] with nums[smallest];
}
```

这段伪代码几乎可以直接翻译为 Java。除了交换过程外，我们写了一个`swap`方法来交换数组的两个元素。我们可以在这里复用它：

```java
public static void swap(int[] list, int i, int j) {
  int temp = list[i];
  list[i] = list[j];
  list[j] = temp;
}
```

我们还可以修改代码以适用于任何大小的数组。以下代码实现了选择排序：

```java
// 使用选择排序算法将给定数组的元素按顺序排列
// 后置条件：数组已排序
public static void selectionSort(int[] a) {
  for (int i = 0; i < a.length - 1; i++) {
    // 找到最小的
    int smallest = i;
    for (int j = i + 1; j < a.length; j++) {
      if (a[j] < a[smallest]) {
        smallest = j;
      }
    }
    // 交换最小的
    swap(a, i, smallest);
  }
}
```

| N | 运行时间 (ms) |
|---:|---:|
| 1 | 0 |
| 2 | 0 |
| 3 | 0 |
| 4 | 0 |
| 5 | 0 |
| 6 | 0 |
| 7 | 0 |
| 8 | 0 |
| 9 | 0 |
| 10 | 0 |
| 11 | 0 |
| 12 | 0 |
| 13 | 0 |
| 14 | 0 |
| 15 | 0 |
| 16 | 0 |
| 17 | 0 |
| 18 | 0 |
| 19 | 0 |
| 20 | 0 |

## 13.4 案例研究：归并排序

存在许多类似于选择排序的算法会对数组进行多次扫描。归并算法源于这种观察：如果你有两个排序的数组，可以很容易将它们合并成一个排序数组。例如，考虑以下数组：

```java
int[] list = {14, 32, 67, 76, 23, 41, 58, 85};
```

我们假设这两个部分已经是排序的（我们稍后会讨论如何排序它们）。归并算法的基本思想如下所示：

- 拆分数组。
- 排序左部分。
- 排序右部分。
- 合并两个部分。

让我们先看拆分数组和合并，然后再讨论排序。

### 拆分和合并数组

将一个数组分成两部分相对简单。我们将数组的一半设置为中点，并将中点之前的所有内容视为“左”部分，其余视为“右”部分。以下方法提取数组的一半作为新数组：

```java
// 返回给定数组的前半。
public static int[] leftHalf(int[] array) {
    int size = array.length / 2;
    int[] left = new int[size];
    for (int i = 0; i < size; i++) {
        left[i] = array[i];
    }
    return left;
}
```

```java
// 返回给定数组的后半。
public static int[] rightHalf(int[] array) {
    int size = array.length / 2;
    int size2 = array.length - size;
    int[] right = new int[size2];
    for (int i = 0; i < size2; i++) {
        right[i] = array[i + size];
    }
    return right;
}
```

现在，假设这些半部分已经是排序的（我们稍后会回到如何排序它们上），并看看我们将如何合并两个子数组。合并两个排序数组的想法类似于，不同之处在于我们不是从堆（子数组）中物理移除纸（整数），而是为每个栈保留一个索引，并在处理给定元素时增加索引。这里是合并算法的伪代码描述：

```
int i = 0;          // 左索引
int j = 0;          // 右索引
```

# 第 13 章 搜索与排序

```java
for (number of elements in entire array) {
  if (left value at i1 < right value at i2) {
    include value from left array in new array;
    i1++;
  } else {
    include value from right array in new array;
    i2++;
  }
}
```

以下是将两个子数组合并为一个新排序数组的八个步骤的追踪过程：

| 子数组 | 下一个包含 | 合并后的数组 |
|---|---|---|
| 0 1 2 3 0 1 2 3 | | 0 1 2 3 4 5 6 7 |
| 14 32 76 | 23 41 58 85 | 来自左侧的 14 |
| ↑ | | |
| i1 | | |
| 0 1 2 3 0 1 2 3 | | 0 1 2 3 4 5 6 7 |
| 14 32 67 76 | 23 41 58 85 | 来自右侧的 14, 23 |
| ↑ | | |
| i2 | | |
| 0 1 2 3 0 1 2 3 | | 0 1 2 3 4 5 6 7 |
| 14 32 67 76 | 23 41 58 85 | 来自左侧的 32 |
| ↑ | | |
| i2 | | |
| 0 1 2 3 0 1 2 3 | | 0 1 2 3 4 5 6 7 |
| 14 32 67 76 | 23 41 58 85 | 来自右侧的 41 |
| ↑ | | |
| i2 | | |
| 0 1 2 3 0 1 2 3 | | 0 1 2 3 4 5 6 7 |
| 14 32 67 76 | 23 41 58 85 | 来自右侧的 14, 23, 32, 41, 58 |
| ↑ | | |
| i2 | | |
| 0 1 2 3 0 1 2 3 | | 0 1 2 3 4 5 6 7 |
| 14 32 67 76 | 23 41 58 85 | 来自左侧的 14, 23, 32, 41, 58, 67 |
| ↑ | | |
| i2 | | |
| 0 1 2 3 0 1 2 3 | | 0 1 2 3 4 5 6 7 |
| 14 32 67 76 | 23 41 58 85 | 来自左侧的 14, 23, 32, 41, 58, 67, 76, 76 |
| ↑ | | |
| i2 | | |

## 13.4 案例研究：实现归并排序

| 子数组 | 下一个包含 | 合并后的数组 |
|---|---|---|
| 0 | 1 | 2 | 3 | 0 | 1 | 2 | 3 | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 5 |
| 14 | 32 | 67 | 76 | 23 | 41 | 58 | 85 | 来自右侧 | 14 | 23 | 32 | 41 | 58 | 67 | 76 | 85 |

以下代码是实现描述合并算法的初始尝试：

```java
// 初始错误尝试
public static void merge(int[] result,
    int[] left, int[] right) {
    int i1 = 0; // 左侧数组的索引
    int i2 = 0; // 右侧数组的索引

    for (int i = 0; i < result.length; i++) {
        if (left[i1] <= right[i2]) {
            result[i] = left[i1];
            i1++;
        } else {
            result[i] = right[i2]; // 从右侧取
            i2++;
        }
    }
}
```

前面的代码是错误的，会导致`ArrayIndexOutOfBoundsException`。在上述图的第七步之后，左子数组中的所有元素都已消耗，索引`i1`越出了子数组的末尾。这意味着代码在尝试访问`left[i1]`时会崩溃。如果右索引`i2`超过了右侧数组的边界，也会发生类似的问题。

我们需要修改代码以保持在数组边界内。`if/else`逻辑需要确保在访问相应元素之前，索引`i1`或`i2`在数组范围内。伪代码中的简单测试需要扩展：

```text
if (i2 已经过了右侧数组末尾，或者
    i1 处的左侧元素 < i2 处的右侧元素) {
    从左侧取。
} else {
    从右侧取。
}
```



第二个版本的代码正确实现了合并。方法的前置和后置条件记录在注释中：

```java
// 将给定的 left 和 right 数组合并到 result 数组
// 前置：result 是空的
// 后置：result 是有序的
public static void merge(int[] result,
    int[] left, int[] right) {
    int i1 = 0; // 左侧数组的索引
    int i2 = 0; // 右侧数组的索引

    for (int i = 0; i < result.length; i++) {
        if (i2 >= right.length || (i1 < left.length && left[i1] <= right[i2])) {
            result[i] = left[i1]; // 从左侧取
            i1++;
        } else {
            result[i] = right[i2]; // 从右侧取
            i2++;
        }
    }
}
```

## 递归归并排序

我们已经编写了将数组分为两半并合并为有序数组的代码。整体的归并排序方法如下：

```java
public static void mergeSort(int[] array) {
    if (array.length > 1) {
        // 将数组分为两个部分
        int[] left = copyHalf(array);
        int[] right = copyHalf(array);

        // 递归地排序两个部分
        mergeSort(left);
        mergeSort(right);

        // 合并排序后的部分
        merge(array, left, right);
    }
}
```

（注：此处省略了 `copyHalf` 和 `splitHalf` 的具体实现，以关注核心逻辑）

由于您提供的原始文本在 `mergeSort` 之后出现了中断且包含部分重复的描述，我已根据您的指令“输出应包含在 [content]...[/content] 中”的要求，对您提供的文本进行了完整的翻译和整理。

*注：由于您提供的原始文本在后半部分存在逻辑断层和重复，译文基于您提供的文本内容进行了结构化处理。*

## 13.4 案例研究：实现合并排序

```java
// post：array 已经按（非递减）顺序排序
public static void mergeSort(int[] array) {
    if (array.length > 1) {
        // 将数组分为两半
        int[] left = leftHalf(array);
        int[] right = rightHalf(array);

        // 递归地排序这两个半部分
        mergeSort(left);
        mergeSort(right);

        // 将排序后的半部分合并成一个完整的排序整体
        merge(array, left, right);
    }
}

// 返回给定数组的前半部分
public static int[] leftHalf(int[] array) {
    int size = array.length / 2;
    int[] left = new int[size];
    for (int i = 0; i < size; i++) {
        left[i] = array[i];
    }
    return left;
}

// 返回给定数组的后半部分
public static int[] rightHalf(int[] array) {
    int size = array.length / 2;
    int size2 = array.length - size;
    int[] right = new int[size2];
    for (int i = 0; i < size2; i++) {
        right[i] = array[i + size];
    }
    return right;
}

// 将给定的左、右数组合并到给定的 result 中
// result 是空的；left/right 已排序
// post：result 包含排序列表合并的结果
public static void merge(int[] result, int[] left, int[] right) {
    int il = 0; // left 数组索引
    int ir = 0; // right 数组索引

    for (int i = 0; i < result.length; i++) {
        if (ir >= right.length || (il < left.length && left[il] <= right[ir])) {
            result[i] = left[il]; // 从左侧取
            il++;
        } else {
            result[i] = right[ir]; // 从右侧取
            ir++;
        }
    }
}
```

## 第 13 章 搜索与排序

程序产生如下输出：

前：[14, 32, 67, 76, 23, 41, 58, 85]

后：[14, 23, 32, 41, 58, 67, 76]

图 13.7 展示了我们的合并排序算法在计算机上的性能。合并排序算法的性能远优于选择排序算法。它的复杂度阶是什么？它看起来几乎像 `O(N log N)` 算法，因为当数组大小翻倍时，运行时间仅略多一倍。

然而，合并排序实际上是一个 `O(N log N)` 算法。对此的正式证明超出了本书的范围，但直觉是：我们必须不断拆分数组直到遇到基本情况（即子数组包含 1 个元素）。对于一个大小为 `N` 的数组，我们必须划分 `log N` 次。在这些 `log N` 步骤中的每一步，我们都要执行一次 `N` 级的线性操作（合并排序后的半部分）。将这些操作的运行时间相乘，就得到了 `O(N log N)` 的总运行时间。

前面的算法运行时间分析是非正式且不严谨的。与其他递归算法一样，对合并排序性能的精确分析是复杂的，并且需要递归关系等数学技术，而这些在在书中并未讨论。

| N | 运行时间 (ms) |  |
|---|---|---|
| 1000 | 0 | 90000 |
| 2000 | 0 | 80000 |
| 4000 | 0 | 70000 |
| 8000 | 0 | 60000 |
| 16000 | 0 | 50000 |
| 32000 | 15 | 40000 |
| 64000 | 16 | 30000 |
| 128000 | 47 | 20000 |
| 256000 | 250 | 10000 |
| 512000 | 532 |  |
| 1024000 | 1078 |  |
| 2048000 | 2265 |  |
| 4096000 | 4781 |  |
| 8192000 | 9828 |  |
| 16384000 | 20422 |  |
| 32768000 | 42406 |  |
| 65536000 | 88344 |  |

图 13.7

## 章总结

搜索是在尝试在集合或数组中寻找特定目标值的任务。算法被分为不同的复杂度类，通常使用大 O 表示法描述，线性算法为 `O(N)`。排序是将列表或数组的元素排列成自然顺序的任务。顺序搜索是一种 `O(N)` 搜索算法，它会检查列表的每个元素，直到找到目标值为止。Java 的类库包含了几种用于搜索和排序数组的方法，例如 `Arrays.binarySearch` 和 `Collections.sort`。二分查找是一种 `O(log N)` 搜索算法，它连续消除一半的数据，直到找到目标元素。选择排序是一种 `O(N^2)` 排序算法，它找到数组中的最小元素并将其移动到数组前线。实证分析是通过运行程序来确定其运行时间的技术。算法分析是检查代码以推断其效率的技术。合并排序是一种 `O(N log N)` 排序算法，通常通过递归实现，它连续将输入数据集分为两半，递归地排序这些半部分并将它们合并成一个排序好的整体。

## 自测题

### 13.1：类库中的搜索与排序

1. 描述使用类库搜索未排序数组的两种方法。
2. 在对象数组上应该使用顺序搜索还是二分查找？
3. 在什么情况下，`Arrays.binarySearch` 和 `Collections.binarySearch` 方法可以成功执行？

### 13.2：程序效率

4. 估算以下代码片段的运行时间（用 `n` 表示）：

```java
int j = 0;
while (j < n) {
    j++;
}
```

```java
int j = 1;
while (j < n) {
    j *= 2;
}
```

```java
int sum = 0;
for (int j = 0; j < n; j++) {
    sum++;
}
```

```java
int sum = 0;
for (int j = 0; j < n; j++) {
    if (j % 2 == 0) {
        sum++;
    }
}
```

```java
int sum = 0;
for (int i = 0; i < n; i++) {
    for (int j = 0; j < i; j++) {
        sum++;
    }
}
```

```java
int sum = 0;
for (int i = 0; i < n; i++) {
    for (int j = 0; j < 100; j++) {
        sum++;
    }
}
```

### 13.3：实现搜索与排序

6. 顺序搜索在未排序数组上的复杂度是多少？二分查找在排序数组上的复杂度是多少？
7. 为什么二分查找算法要求输入是排序的？
8. 如果数组包含 60 个元素，二分查找最多会检查多少元素？
9. 在以下数组中搜索目标值 8 时，哪些索引会被作为中间元素？二分查找将返回什么？

```java
int[] numbers = {1, 3, 6, 7, 8, 10, 15, 20, 30};
int[] numbers = {1, 2, 3, 4, 5, 7, 8, 9, 10};
int[] numbers = {1, 2, 3, 4, 5, 6, 7, 8, 9};
int[] numbers = {8, 9, 12, 14, 15, 17, 19, 25, 31};
```

在以下数组中搜索目标值 8 时，哪些索引会被作为中间元素？注意输入数组不是排序的。你对二分查找的结果有什么看法？

```java
int[] numbers = {6, 5, 8, 19, 7, 35, 22, 11, 9};
```

## 练习

11. `selectionSort` 方法需要进行哪些修改才能使其排序双精度浮点数而不是整数？

12. 对一个长度为 32 的列表进行排序，会产生多少次 `mergeSort` 调用？

13. 给定以下整型数组：

`int[] numbers = {7, 2, 8, 4, 1, 11, 9, 5, 3, 10};`

- 显示选择排序外层循环五次后元素的状态。
- 展示合并排序的前两层追踪。展示整个数组的拆分，以及一层递归调用。

14. 给定以下整型数组：

`int[] numbers = {7, 1, 6, 12, -3, 8, 4, 21, 2, 30, -1, 9};`

- 显示选择排序外层循环五次后元素的状态。
- 展示合并排序的前两层追踪。展示整个数组的拆分，以及一层递归调用。

## 第 13 章搜索与排序

1. 编写一个程序，读取一系列输入行并按字母顺序对它们进行排序，忽略单词的大小写。该程序应使用归并排序算法（merge sort），以便高效地排序大文件。
2. 编写一个程序，处理一个包含学生课程数据的数据文件。数据以随机顺序到达，每行存储一个学生的姓、名、学生学号、百分比和字母等级信息。例如：

| 姓 | 名 | 学号 | 分数 | 等级 |
|---|---|---|---|---|
| Smith | Kelly | 438975 | 98.6 | A |
| Johnson | Gus | 210498 | 72.4 | C |
| Reges | Stu | 098736 | 88.2 | B |
| Smith | Marty | 346282 | 84.1 | B |
| Reges | Abe | 298575 | 78.3 | C |

你的程序应该能够按任何一列数据进行排序。使用比较器（Comparators）来实现排序顺序。使数据能够按姓名、学号和分数百分比升序和降序排序。例如：

学生数据，按姓名排序：

|  |  | 学号 | 分数 | 等级 |
|---|---|---|---|---|
| Johnson | Gus | 210498 | 72.4 | C |
| Reges | Stu | 098736 | 88.2 | B |
| Reges | Abe | 298575 | 78.3 | C |
| Smith | Kelly | 438975 | 98.6 | A |
| Smith | Marty | 346282 | 84.1 | B |

学生数据，按学号排序：

|  |  | 学号 | 分数 | 等级 |
|---|---|---|---|---|
| Reges | Stu | 098736 | 88.2 | B |
| Johnson | Gus | 210498 | 72.4 | C |
| Reges | Abe | 298575 | 78.3 | C |
| Smith | Marty | 346282 | 84.1 | B |
| Smith | Kelly | 438975 | 98.6 | A |

3. 编写一个程序，发现输入文件中出的单词的所有变位词（anagrams），该文件在大字典中存储条目。单词的变位词将其字母重新排列成一个新的合法单词。例如，“share”的变位词包括“shear”、“hears”和“hares”。假设你有一个文件，其中列出了许多单词，每行一个。你的程序首先读取字典并对其排序，但不是按字母顺序，而是根据每个单词的规范形式（canonical form）排序。单词的规范形式包含与原始相同的字母，但是排序后的顺序。因此，“computer”的规范形式是“ceomprtu”，而“program”的规范形式是“agomprz”。在排序字典时，“program”单词将放在“computer”之前，因为它的规范形式在字母表上较小。编写代码获取单词的规范形式，以及一个通过规范形式比较单词的比较器。

## 第 14 章：图形用户界面

## 引言

在本章中，我们将探索图形用户界面（GUIs）的创建。虽然在前几章创建的控制台程序是基于文本的，但图形界面要通用得多。

我们喜欢图形用户界面。假设我们引入了一个 `DrawingPanel` 类，允许你在屏幕上绘制简单对象。虽然这对于通过在画布上绘制形状和线条来创建游戏或基于图形的编辑器应用程序有用，但图形用户界面涉及创建你自己的窗口框，其中包含文本字段和其他屏幕组件。

## 14.1 GUI 基础

- 使用选项面板进行图形输入和输出
- 与窗口（Frames）一起工作
- 按钮、标签和文本框
- 更改窗口的布局
- 处理动作事件

## 14.2 组件布局

- 布局管理器
- 复合布局

## 14.3 组件之间的交互

- 示例 1：BMI GUI
- 面向对象的 GUI
- 示例 2：信用卡验证器

## 14.4 附加组件和事件

- 文本区域、滚动条和字体
- 图标
- 鼠标事件

## 14.5 二维图形

- 在面板上绘制
- 使用定时器进行动画

## 14.6 案例研究：实现 `DrawingPanel`

- 无事件的初始版本
- 带事件的第二个版本

## 第 14 章：图形用户界面

## 14.1 GUI 基础

GUI 可能是非常复杂的实体，因为它们涉及到大量的交互对象和类。每个屏幕组件和窗口都由一个对象表示，因此初学者 GUI 的程序员必须学习许多类名、方法名和包名。此外，如果 GUI 要执行复杂的任务，对象之间必须相互作用并调用对方的方法，这引发了棘手的通信和耦合问题。

另一个让编写 GUI 具有挑战性的因素是执行路径变得具有不确定性。在 GUI 程序中，用户可以点击任何按钮，并以任何顺序与任何其他屏幕组件进行交互。因为程序的执行是由发生的一系列事件驱动的，我们说带有 GUI 的程序是事件驱动的。在本章中，你将学习如何处理用户事件，以便你的事件驱动图形程序能够做出恰当的响应。

GUI 可能是非常复杂的实体，因为它们涉及到大量的交互对象和类。每个屏幕组件和窗口都由一个对象表示，因此初学者 GUI 的程序员必须学习许多类名、方法名和包名。此外，如果 GUI 要执行复杂的任务，对象之间必须相互作用并调用对方的方法，这引发了棘手的通信和耦合问题。

另一个让编写 GUI 具有挑战性的因素是执行路径变得具有不确定性。在 GUI 程序中，用户可以点击任何按钮，并以任何顺序与任何其他屏幕组件进行交互。因为程序的执行是由发生的一系列事件驱动的，我们说带有 GUI 的程序是事件驱动的。在本章中，你将学习如何处理用户事件，以便你的事件驱动图形程序能够做出恰当的响应。

GUI 可能是非常复杂的实体，因为它们涉及到大量的交互对象和类。每个屏幕组件和窗口都由一个对象表示，因此初学者 GUI 的程序员必须学习许多类名、方法名和包名。此外，如果 GUI 要执行复杂的任务，对象之间必须相互作用并调用对方的方法，这引发了棘手的通信和耦合问题。



另一个让编写 GUI 具有挑战性的因素是执行路径变得具有不确定性。在 GUI 程序中，用户可以点击任何按钮，并以任何顺序与任何其他屏幕组件进行交互。因为程序的执行是由发生的一系列事件驱动的，我们说带有 GUI 的程序是事件驱动的。在本章中，你将学习如何处理用户事件，以便你的事件驱动图形程序能够做出恰当的响应。

GUI 可能是非常复杂的实体，因为它们涉及到大量的交互对象和类。每个屏幕组件和窗口都由一个对象表示，因此初学者 GUI 的程序员必须学习许多类名、方法名和包名。此外，如果 GUI 要执行复杂的任务，对象之间必须相互作用并调用对方的方法，这引发了棘手的通信和耦合问题。

## 14.1 GUI 基础

表 14.2 包装类方法

| 方法 | 描述 |
| --- | --- |
| `Integer.parseInt(str)` | 返回字符串表示的整数 `int` 类型 |
| `Double.parseDouble(str)` | 返回字符串表示的实数 `double` 类型 |
| `Boolean.parseBoolean(str)` | 返回给定字符串表示的布尔值（如果文本是 "true"，则返回 `true`；否则返回 `false`） |

无效数字，例如 "abc"、"five" 或 "2+2"。为了让你的代码对此类无效输入具有健壮性，你可以将代码封装在 `try/catch` 语句中，例如：

```java
try {
    int age = Integer.parseInt(ageText);
} catch (NumberFormatException nfe) {
    JOptionPane.showMessageDialog(null,
    "无效的整数.");
}
```

表 14.2 总结了可以用于转换字符串的包装类中的静态方法。

# 使用框架 (Frames)

`JOptionPane` 非常有用，但仅靠它本身，灵活性和威力还不足以创建丰富的图形用户界面。要做到这一点，你需要学习 Java 中可以放置在屏幕上的各种类型部件（widgets）。

屏幕上的窗口被称为框架（frame）。

- 框架 (Frame)

屏幕上的图形窗口。

框架内部的图形部件，如按钮或文本输入字段统称为组件（components）。

- 组件 (Component)

位于图形窗口内的部件，例如按钮或文本字段。

从技术上讲，框架也是一种组件，但我们将框架与其他组件区别对待，因为框架形成了我们在屏幕上看到的物理窗口。框架还拥有许多在其他组件中没有找到的方法。

图 14.1 展示了 Java 中常用的图形组件，按类名列出。有关可用图形组件更完整的图片引用，可以在 Sun 的 Java 教程中找到：http://java.sun.com/docs/books/tutorial/uiswing/components/components.html。

# 第 14 章 图形用户界面

| OK | 复选框 (Check) | 单选框 (Radio) | 图像和文本 |
|---|---|---|---|
| 是 | | | 仅文本标签 |
| | | | 成员, Demo, 记忆 |
| | | | 菜单 另一个菜单 |
| | | | □ 仅文本菜单项 |
| | | | □ 文本和图标 |
| | | | ○ 单选框菜单项 |
| | | | 复选框菜单项 |
| | | | 子菜单 |

![](img/aea18896a4bced58de45f29f5a93f7b3_757_0.png)

图像由 `JFrame` 类的对象表示。任何复杂的图形程序必须构造一个 `JFrame` 对象来表示其主图形窗口。一旦你构造了一个 `JFrame` 对象，就可以调用它的 `setVisible` 方法并传递布尔值 `true` 来让它在屏幕上显示自己。这里有一个构造框架并将其放置在屏幕上的简单程序：

```java
// 在屏幕上显示一个空窗口框架。
import javax.swing.*;
public class SimpleFrame {
    public static void main(String[] args) {
        JFrame frame = new JFrame();
        frame.setVisible(true);
    }
}
```

程序的输出有点傻，只产生了一个微小的窗口：

事实上，该程序还有另一个问题：当你关闭窗口时，它并不会终止 Java 程序。当你显示一个 `JFrame` 时，默认情况下 Java 不会在框架关闭时退出程序。你可以发现程序没有退出，因为控制台窗口将残留在你的屏幕上（如果你在使用某些 Java 编辑器），或者因为你的编辑器没有显示程序已终止的通常消息。如果你希望程序在窗口关闭时退出，你必须显式地说明。

为了创建一个更有有趣的框架，你必须学习 `JFrame` 的属性。GUI 组件的属性是它内部拥有的字段或属性，你可能希望检查或更改它。框架的属性控制诸如窗口大小或出现在标题栏的文本等内容。你可以通过调用框架上的方法来设置或检查这些属性的值。

表 14.3 列出了有用的 `JFrame` 属性。例如，要将 `SimpleFrame` 程序中框架的标题设置为 "A window frame"，你需要：

```java
frame.setTitle("A window frame");
```

# 表 14.3 JFrame 特有的有用属性

| 属性 | 类型 | 描述 | 方法 |
|---|---|---|---|
| 默认 (default) | int | 框架关闭时应该发生什么：选项 | `setDefaultCloseOperation()` |
| 关闭操作 (close operation) | | 包括：<br>* `JFrame.DO_NOTHING_ON_CLOSE` (什么都不做)<br>* `JFrame.HIDE_ON_CLOSE` (隐藏框架)<br>* `JFrame.DISPOSE_ON_CLOSE` (隐藏并销毁框架使其无法再次显示)<br>* `JFrame.EXIT_ON_CLOSE` (退出程序) | |
| 图标图像 (icon image) | Image | 出现在标题栏、开始菜单或 Dock 中的图标 | `getIcon()`, `setImageIcon(Image)` |
| 布局 (layout) | LayoutManager | 控制此框架内组件位置和大小的对象 | `getLayout()`, `setLayout(LayoutManager)` |
| 可调整大小 (resizable) | boolean | 框架是否允许自己调整大小 | `isResizable()`, `setResizable(boolean)` |
| 标题 (title) | String | 出现在标题栏的文本 | `getTitle()`, `setTitle(String)` |

## 第 14 章 图形用户界面

## 表 14.4 组件的视觉属性

| 属性 | 类型 | 描述 | 方法 |
|---|---|---|---|
| 背景 (background) | Color | 背景 | `getBackground()`, `setBackground(Color)` |
| 可用 (enabled) | boolean | 组件是否可以进行交互 | `isEnabled()`, `setEnabled(boolean)` |
| 可获取焦点 (focusable) | boolean | 组件是否可以发送输入 | `isFocusable()`, `setFocusable(boolean)` |
| 字体 (font) | Font | 用于编写文本的字体 | `getFont()`, `setFont(Font)` |
| 前景 (foreground) | Color | 前景颜色 | `getForeground()`, `setForeground(Color)` |
| 位置 (location) | Point | 组件左上角的 (x, y) 坐标 | `getLocation()`, `setLocation(Point)` |
| 大小 (size) | Dimension | 组件的宽度和高度 | `getSize()`, `setSize(Dimension)` |
| 首选 (preferred) | Dimension | 组件的“首选”宽度和高度：即它在屏幕上自然的大小 | `getPreferredSize()`, `setPreferredSize(Dimension)` |
| 可见 (visible) | boolean | 组件是否在屏幕上可见 | `isVisible()`, `setVisible(boolean)` |

事实证明，所有图形组件和框架共享共同继承，因为它们存在于共同的超类中。Swing 框架是继承的一个强大示例，因为许多组件在共同的层次结构中共享特征。表 14.4 列出了组件的属性及其对应的方法。所有这些都在 `java.awt` 包中，所以像你在之前的章节中绘制图形程序那样导入它。`size` 属性是一个 `Dimension` 对象

## 表 14.5 Dimension 对象的有用方法

```java
public Dimension(int width, int height)
    构造一个表示给定尺寸的维度

public int getWidth()
    返回此维度的宽度

public int getHeight()
    返回此维度的高度
```

类，例如如何构造。表 14.5 列出了你应该熟悉的方法。

以下 `SimpleFrame` 程序的新版本创建一个框架并设置表 14.4 中的属性。在这个版本中，我们赋予框架颜色。设置在屏幕上的位置和大小，并在标题栏放入文本。我们还设置了框架的“默认关闭操作”，告诉它在关闭时关闭 Java 程序：

```java
// 设置窗口框架的几个属性。
import java.awt.*; // 用于 Dimension
import javax.swing.*; // 用于 GUI 组件

public class SimpleFrame2 {
    public static void main(String[] args) {
        JFrame frame = new JFrame();
        frame.setForeground(Color.WHITE);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLocation(new Point(10, 50));
        frame.setSize(new Dimension(300, 120));
        frame.setTitle("A frame");
        frame.setVisible(true);
    }
}
```

当程序运行时，会出现以下窗口：

![](img/aea18896a4bced58de45f29f5a93f7b3_760_0.png)

当窗口关闭时，程序退出。

# 按钮、标签和文本字段

我们的空框架如果里面没有任何东西，就不很有趣。让我们看看可以放在框架中的一些图形组件。

## 第 14 章 图形用户界面

我们检查的组件是按钮（Button）。你可能已经知道按钮是一个可以点击以触发操作的屏幕组件。按钮由 `JButton` 类表示。你创建的每个 `JButton` 对象都代表屏幕上的一个按钮；如果你想要三个按钮，必须创建三个 `JButton` 对象并将它们放置在框架（frame）中。

我是第一个按钮 | 第二个按钮

你可以使用无参数来构造按钮（一个没有文本的按钮），也可以使用一个表示按钮文本的 `String`。当然，你始终可以通过调用 `setText` 方法来更改按钮的文本。你还可以设置按钮的其他属性，例如背景颜色：

```java
JButton button1 = new JButton();
button1.setText("I'm the first button");
```

```java
JButton button2 = new JButton("The second button");
button2.setBackground(Color.YELLOW);
```

标签（Label）是显示在 GUI 上的字符串。标签用于提供信息，通常不会通过点击来执行操作。标签由 `JLabel` 对象表示，该对象可以通过一个指定标签文本的参数来构造：

```java
JLabel label = new JLabel("This is a label");
```

这是一个标签

文本字段（Text field）是一个用户可以在其中输入文本字符串的框。文本字段由 `JTextField` 对象表示，该对象可以通过一个指定文本框内能容纳字符数量的参数来构造：

```java
// 创建宽度为 8 个字符的字段
JTextField field = new JTextField(8);
```

你指定的宽度（在前面的代码中为 8）并不由程序强制；如果用户需要，可以输入比指定数量更多的字符。参数值仅会影响屏幕上文本的大小。

仅仅构造各种组件对象并不会将其放置在屏幕上；你必须将它们添加到框架中，框架才会显示它们。框架充当容器，或者说你可以向其添加图形组件的区域。要向 `JFrame` 添加组件，请调用框架的 `add` 方法并将适当的组件作为参数传递。

以下程序创建了一个框架并在其中放置了两个按钮：

```java
+   1 // 创建一个包含两个按钮的框架。
2
3 import java.awt.*;
```

### 14.1 GUI 基础



```java
import java.swing.*;

public class ComponentsExample {
    public static void main(String[] args) {
        JFrame frame = new JFrame();
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(new Dimension(300, 100));
        frame.setTitle("A frame");

        JButton button1 = new JButton();
        button1.setText("I'm a button.");
        button1.setBackground(Color.BLUE);
        frame.add(button1);

        JButton button2 = new JButton();
        button2.setText("Click me!");
        button2.setBackground(Color.RED);
        frame.add(button2);

        frame.setVisible(true);
    }
}
```

你会在这段代码中发现一种模式。在创建组件时，你必须执行以下操作：

- 构造它。
- 如果需要，设置它的属性。
- 将其放置在屏幕上（在这种情况下，通过将其添加到框架中）。

程序产生了如下图形输出：

![](img/aea18896a4bced58de45f29f5a93f7b3_762_0.png)

这个程序的输出可能不是你预期的。第一个按钮是不可见的：它隐藏在第二个按钮下面，第二个按钮已经被拉伸以填充整个框架。让我们探讨这个问题的原因以及如何解决它。

## 更改框架的布局

上一个程序的问题与组件的布局有关，即它们是如何定位、调整大小等的。我们没有告诉框架如何布局按钮，它使用一种默认行为，即每个组件都定位在框架的中心并填充整个框架的空间。当多个组件被添加到框架中时，最后添加的组件将放置在屏幕显示层上。每个按钮都有尺寸和位置属性，但在我们的代码中设置这些属性并不能解决问题。要修复窗口的外观，我们必须使用一个称为布局管理器（layout manager）的对象。

## 布局管理器

布局对象决定了屏幕上框架或其他容器内组件的位置、大小以及动态调整大小。

框架拥有一个布局管理器对象，它用来对内部的所有组件进行定位。如果我们设置了按钮的位置和大小，框架的布局管理器会将它们设置回它偏好的值。要以不同的方式定位组件，我们必须为框架设置一个新的布局管理器，并让它来定位组件。

Java 在其 `java.awt` 包中包含了许多布局管理器类，因此请确保导入了该包（以及用于 `JFrame` 和其他组件类的 `javax.swing`）：

```java
import java.awt.*; // 用于布局管理器
import javax.swing.*; // 用于 GUI 组件
```

`JFrame` 的默认布局管理器类型称为 `BorderLayout`，我们将在本章稍后部分探讨它。如果我们希望按钮按照从左到右的顺序流动，可以将框架设置为使用名为 `FlowLayout` 的不同布局管理器。我们通过在程序中添加按钮之前插入以下行来实现这一点：

```java
frame.setLayout(new FlowLayout());
```

通过这种方式设置布局确保两个组件在框架中都是可见的。程序现在产生了如下图形输出：

![](img/aea18896a4bced58de45f29f5a93f7b3_763_0.png)

我们将在第 14.2 节详细讨论布局管理器。你可能已经注意到，目前框架的大小并不完全适合它的按钮——在底部和侧面有额外的空间。`JFrame` 对象有一个非常有用的方法称为 `pack`，它告诉框架调整大小以恰好适应其组件。如果你调用了 `pack`，就不需要对框架调用 `setLayout`，因为 `pack` 会为你设置尺寸。在屏幕上显示框架之前调用此方法，将确保组件紧凑地位于其中，没有多余的空白：

```java
frame.pack();
frame.setVisible(true);
```

新的、调整大小后的框架具有如下屏幕外观：

![](img/aea18896a4bced58de45f29f5a93f7b3_763_1.png)

# 14.1 GUI 基础

## 处理动作事件

我们到为止创建的用户界面不是交互式的——当用户点击按钮或输入文字时，什么都不会发生。为了创建交互式界面，你必须学习如何处理事件。当用户点击组件、移动鼠标上方或与其交互时，GUI 会创建一个特殊的事件（event）对象来表示这种动作。

### 事件

表示用户与 GUI 组件交互的对象，可以由程序处理。

默认情况下，如果你不指定对事件做出反应，它会被程序忽略。你可以使用一种称为监听器（listener）的对象来对特定事件产生响应（例如点击特定按钮）。

### 监听器

在事件发生时被通知并执行代码以响应的对象。

要处理事件，创建一个监听器对象并将其附加感兴趣的组件上。监听器对象包含了事件发生时你想运行的代码。我们在本章将处理的第一种事件是动作事件（action event）。动作事件是一种相当通用的类型，发生在用户与许多标准组件交互时（例如点击按钮或在 `JTextField` 获得焦点时按下回车）。

在 Java 中，事件监听器是通过实现特定的接口编写的。处理动作事件的接口称为 `ActionListener`。它位于 `java.awt.event` 包中，你需要导入：

```java
import java.awt.event.*; // 用于动作事件
```

如果你已经导入了 `java.awt` 包，仍然需要单独导入 `java.awt.event` 包，前者并不包含后者。`ActionListener` 接口仅包含以下：

```java
public void actionPerformed(ActionEvent event)
```

要监听事件，你需要编写实现 `ActionListener` 接口的类，并在它的 `actionPerformed` 方法中放置事件发生时运行的代码。然后将你的监听器类对象添加到适当的组件上。

这是一个简单的 `ActionListener` 类示例，它通过显示消息框来对事件做出响应：

```java
// 通过显示消息框来响应事件。

import java.awt.event.*;
```

## 第 14 章 图形用户界面

```java
import javax.swing.*;

public class MessageListener implements ActionListener {
    public void actionPerformed(ActionEvent event) {
        JOptionPane.showMessageDialog(null,
                "You clicked the button!");
    }
}
```

现在我们已经写了这个类，可以将一个 `MessageListener` 对象绑定到任何按钮或其他感兴趣的组件上，它将对该组件上的事件做出响应。例如，如果我们向按钮绑定一个 `MessageListener`，每当点击该按钮时，就会弹出一个选项面板（option pane）。要绑定监听器，我们将使用在多个 Swing 组件中找到 `ActionListener` 方法，该方法接受一个类型为 `ActionListener` 的参数。

例如，我们可以在之前开发的 `ComponentsExample` 程序中添加以下行代码，将监听器绑定到第一个按钮上：

```java
// 添加一个监听器来处理此按钮上的事件
button.addActionListener(new MessageListener());
```

当程序执行且用户点击按钮时，结果如下：

![](img/aea18896a4bced58de45f29f5a93f7b3_765_0.png)

注意，监听器只对它被添加的事件做出响应。如果用户点击“Click me!”按钮，什么都不会发生。如果我们希望在用户点击此按钮时发生相同的事件，我们必须向它也添加一个 `MessageListener`。如果我们希望在点击此按钮时产生不同的响应，可以编写一个实现 `ActionListener` 的类，并将它的其中一个对象绑定到按钮上。总而言之，在 Java 中处理事件的必要步骤如下：

- 创建一个实现 `ActionListener` 的类。
- 将处理事件的代码放入其 `actionPerformed` 方法中。
- 使用组件的 `addActionListener` 方法将你的监听器类对象绑定到感兴趣的组件上。

## 14.2 组件的布局

之前，我们使用 `FlowLayout` 来在框架中定位组件。在本节中，我们将探索几种不同的布局管理器对象，它们可以以多种方式对组件进行布局。

![](img/aea18896a4bced58de45f29f5a93f7b3_766_0.png)

图 14.2 布局管理器

### 布局管理器

有很多用的布局管理器，其名称反映了它们产生组件位置的样式。图 14.2 展示了了一些最常见的布局管理器。

也许最简单的布局管理器是 `FlowLayout`。正如之前讨论的，`FlowLayout` 从左到右、从上到下的流式方式定位组件，类似于单词在段落中的排列方式。如果一行组件太宽而无法放入框架中，该行就会换行。

考虑以下代码，它向一个使用 `FlowLayout` 的框架中添加了三个组件：

```java
JLabel label = new JLabel("Type your ZIP code: ");
JTextField field = new JTextField(5);
JButton button = new JButton("Submit");
```

```java
frame.setLayout(new FlowLayout());
frame.add(label);
frame.add(field);
frame.add(button);
```

当框架在屏幕上显示时，会产生以下图形输出。调整窗口大小展示了换行行为：

![](img/aea18896a4bced58de45f29f5a93f7b3_766_1.png)

另一种常见的布局称为 `GridLayout`，它在行和列的网格中布局组件。你通过传递行数和列数来构造一个 `GridLayout`。当你向框架中添加组件时，它们将以等大小的矩形形式布局。组件按行主顺序（从左到右，从上到下）放在矩形中。我们在示例中仅使用按钮，这样你可以清楚地看到每个组件的大小和形状：

```java
// 2 行 3 列
frame.setLayout(new GridLayout(2, 3));
for (int i = 1; i <= 6; i++) {
    frame.add(new JButton("Button " + i));
}
```

这段代码产生了以下图形输出。调整窗口显示，`GridLayout` 强制每个组件具有相同的大小，尽管这会导致组件的拉伸：

![](img/aea18896a4bced58de45f29f5a93f7b3_767_0.png)

我们在本节中将讨论的第三种也是最后的布局管理器被称为 `BorderLayout`。`BorderLayout` 将框架分为五个区域：北、南、西、东和中心。向框架添加组件时，你传递两个参数：要添加的组件以及表示放置位置的常量。这些常量分别是 `BorderLayout.NORTH`、`BorderLayout.SOUTH`、`BorderLayout.WEST`、`BorderLayout.EAST` 和 `BorderLayout.CENTER`。如果你不传递第二个参数，组件将位于中心。

以下程序演示了被添加到 `BorderLayout` 的多个按钮：

```java
// 使用 BorderLayout 布局组件
import java.awt.*;
import javax.swing.*;

public class BorderLayoutExample {
    public static void main(String[] args) {
        JFrame frame = new JFrame();
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(new Dimension(210, 200));
        frame.setTitle("Run for the border");

        frame.setLayout(new BorderLayout());
        frame.add(new JButton("North"), BorderLayout.NORTH);
        frame.add(new JButton("South"), BorderLayout.SOUTH);
        frame.add(new JButton("West"), BorderLayout.WEST);
        frame.add(new JButton("East"), BorderLayout.EAST);
        frame.add(new JButton("Center"), BorderLayout.CENTER);
        frame.setVisible(true);
    }
}
```

一种常见的策略是让框架使用 `BorderLayout`，然后向它的五个区域中的一些添加面板。例如，以下代码创建了一个看起来像电话键盘的窗口，它在框架的中心区域使用了带有 `GridLayout` 的面板，在框架的南部使用了带有 `FlowLayout` 的第二个面板：

```java
// 创建一个电话键盘。

import java.awt.*;
import javax.swing.*;
```

## 14.2 布局组件

```java
public class Telephone {
    public static void main(String[] args) {
        JFrame frame = new JFrame();
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(new Dimension(250, 200));
        frame.setTitle("Telephone");

        frame.setLayout(new BorderLayout());
        // 主电话按钮
        JPanel centerPanel = new JPanel(new GridLayout(4, 3));
        for (int i = 1; i <= 9; i++) {
            centerPanel.add(new JButton("" + i + ""));
        }
        centerPanel.add(new JButton("0"));
        centerPanel.add(new JButton("0"));
        centerPanel.add(new JButton("0"));
        frame.add(centerPanel, BorderLayout.CENTER);

        // 状态面板
        JPanel southPanel = new JPanel(new FlowLayout());
        southPanel.add(new JLabel("Number to dial:"));
        southPanel.add(new JTextField(10));
        frame.add(southPanel, BorderLayout.SOUTH);

        frame.setVisible(true);
    }
}
```

前面的程序使用 `for` 循环将前九个按钮的文本设置为整数 1 到 9，但它遇到了一个问题：`JButton` 的构造函数接受 `String` 作为参数。为了解决这个问题，`for` 循环使用了一个技巧，通过与空字符串 `""` 拼接将存储在 `i` 中的整数值转换为 `String`。程序的图形化输出如下：

![](img/aea18896a4bced58de45f29f5a93f7b3_770_0.png)

要让组合布局看起来恰恰可能很困难。练习大量的示例并仔细考虑各种布局的拉伸行为是有帮助的。例如，你如何创建一个像这这样的窗口呢？

## 第 14 章 图形用户界面

![](img/aea18896a4bced58de45f29f5a93f7b3_771_0.png)

`BorderLayout` 是框架的正确选择，但你将如何布局单个组件呢？窗口顶部有三行组件。所以你的第一个想法可能是将这些组件放在具有 3x3 网格布局的面板中。然后你将它添加到框架的北部区域，同时在南部区域添加中央文本区域和“发送（Send）”按钮：



```java
// 这代码没有产生正确的布局
frame.setLayout(new BorderLayout());
north.add(new JPanel(new GridLayout(3, 3)));
north.add(new JLabel("From:"));
north.add(new JButton("Browse..."));
north.add(new JLabel("To:"));
north.add(new JTextField());
north.add(new JButton("Browse..."));
north.add(new JLabel("Subject:"));
north.add(new JTextField());
```

```java
frame.add(north, BorderLayout.NORTH);
frame.add(new JTextArea(), BorderLayout.CENTER);
frame.add(new JButton("Send"), BorderLayout.SOUTH);
```

这段代码产生了下面的图形化输出，它是错误的：

![](img/aea18896a4bced58de45f29f5a93f7b3_771_1.png)

## 14.2 布局组件

这个输出存在几个问题。首先，因为网格布局（grid layout）强制其内部每个组件都具有相同的大小，导致标签、文本字段和按钮都不太合适。你希望每个标签与其他标签的大小相同，每个文本字段和按钮与其他它们的大小相同，但你不希望不同类型的组件具有相同的大小。

解决这个尺寸问题最简单的方法是在框架的北部区域创建三个具有网格布局的独立面板，每个面板有三行且只有一列。你可以将标签放在第一个网格中，将文本字段放在第二个，将按钮放在第三个。（即使只有两个按钮，也要将布局设为 3x1，这样就会留出一个空白区域以生成预期的输出）。

为了让这三个网格并排在一起，需要再进行一层嵌套，即创建一个具有`border layout`布局的主面板来存储这三个面板。标签将占据西部区域，文本字段占据中心，按钮占据东部区域。将这个主面板放在框架的北部区域。

之前输出的问题是“发送（Send）”按钮被拉伸了。因为它被直接放置在`BorderLayout`的南部区域，导致按钮在水平方向上拉伸到了整个框架。为了避免这个问题，将“发送”按钮放入一个带有`FlowLayout`的面板中。`FlowLayout`不会拉伸其内部的组件，因此按钮不会增长到那么大。然后将面板添加到框架的南部区域，而不是直接添加“发送”按钮。

这里是程序的完整版本，包含了这些修正并能产生正确的输出：

```java
// 创建一个类似于邮件撰写消息窗口的 GUI。

import java.awt.*;
import javax.swing.*;

class classMessage {
    public static void main(String[] args) {
        JFrame frame = new JFrame();
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(new Dimension(400, 300));
        frame.setTitle("Send Message");
        frame.setLayout(new BorderLayout());

        JPanel northWest = new JPanel(new GridLayout(3, 1));
        northWest.add(new JLabel("From:"));
        northWest.add(new JLabel("To:"));
        northWest.add(new JLabel("Subject:"));

        JPanel northCenter = new JPanel(new GridLayout(3, 1));
        northCenter.add(new JTextField());
        northCenter.add(new JTextField());
        northCenter.add(new JTextField());

        JPanel northEast = new JPanel(new GridLayout(2, 1));
        northEast.add(new JButton("Browse..."));
        northEast.add(new JButton("Browse..."));

        JPanel north = new JPanel(new BorderLayout());
        north.add(northWest, BorderLayout.WEST);
        north.add(northCenter, BorderLayout.CENTER);
        north.add(northEast, BorderLayout.EAST);

        frame.add(north, BorderLayout.NORTH);
        frame.add(new JTextArea(), BorderLayout.CENTER);

        JPanel south = new JPanel(new FlowLayout());
        south.add(new JButton("Send"));
        frame.add(south, BorderLayout.SOUTH);

        frame.setVisible(true);
    }
}
```

## 第14章 图形用户界面

```java
public class BmiGui2 {
    // 屏幕组件存储为字段中
    private JFrame frame;
    private JTextField height;
    private JTextField weight;
    private JLabel bmiLabel;
    private JButton computeButton;

    public BmiGui2() {
        // 设置组件
        height = new JTextField(5);
        weight = new JTextField(5);
        bmiLabel = new JLabel("输入您的身高和体重");
        computeButton = new JButton("Compute");

        // 布局
        JPanel north = new JPanel(new GridLayout(2, 2));
        north.add(new JLabel("Height: "));
        north.add(height);
        north.add(new JLabel("Weight: "));
        north.add(weight);

        // 整体框架
        frame = new JFrame("BMI");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(new BorderLayout());
        frame.add(north, BorderLayout.NORTH);
        frame.add(bmiLabel, BorderLayout.CENTER);
        frame.add(computeButton, BorderLayout.SOUTH);
        frame.pack();
        frame.setVisible(true);
    }
}
```

既然 GUI 是一个对象了，我们可以编写一个单独的客户端类来处理构造它的主方法。下面的简短类完成了这项工作：

```java
// 在屏幕上显示 BMI GUI。
public class RunBmiGui2 {
    public static void main(String[] args) {
        BmiGui gui = new BmiGui(); // 构建/显示 GUI
    }
}
```

拥有面向对象的 GUI 的优势是我们可以将其作为一个监听器。我们想为 Compute 按钮添加一个监听器来更改用户的 BMI，这个监听器需要访问身高和体重文本字段以及中间的 BMI 标签。这些组件位于`BmiGui2`对象内部，因此如果`BmiGui`类本身实现了`ActionListener`，它就可以访问所有需要的信息。

让我们编写第三个版本的 BMI GUI，它可以处理事件。我们将类名更改为`BmiGui3`，并修改类头以实现`ActionListener`接口：

## 14.3 交互组件

```java
public class BmiGui3 implements ActionListener {
```

为了实现`ActionListener`，我们必须编写一个`actionPerformed`方法。我们的`actionPerformed`代码将读取两个文本字段，将它们转换为`double`类型，使用标准的 BMI 公式体重/身高来计算 BMI，并设置中间 BMI 标签的文本以显示 BMI 结果。以下代码实现了该监听器：

```java
// 通过计算 BMI 处理按钮点击事件。
// 从文本字段读取身高/体重信息
String heightText = heightField.getText();
double height = Double.parseDouble(heightText);
String weightText = weightField.getText();
double weight = Double.parseDouble(weightText);

// 计算 BMI 并显示在屏幕上
double bmi = weight / (height) * 703;
bmiLabel.setText("BMI: " + bmi);
```

现在我们需要将监听器附加到 Compute 按钮。由于 GUI 就是监听器，我们传递给按钮`ActionListener`方法的参数是 GUI 本身。因为在 GUI 对象的构造函数内部，我们使用`this`关键字将 GUI 作为参数传递：

```java
// 将 GUI 作为监听器附加到 Compute 按钮
computeButton.addActionListener(this);
```

我们 BMI GUI 的第二个版本使用了一个名为`RunBmiGui2`的单独类来运行 GUI。然而，对于这样一个极其简单的客户端程序，使用第二个类有点浪费。实际上，在 BMI GUI 类本身中包含相同的方法而不使用`RunBmiGui2`类是合法的。如果我们这样做，该类就成了它自己的客户端，我们只需要编译并运行该 GUI 类来执行程序。（静态方法如`main`通常置于同一个文件中任何字段、构造函数和实例方法之上。）

在实现监听器代码并整合我们的方法后，BMI GUI 的最终版本如下：

```java
// 用于计算人体质量指数 (BMI) 的 GUI。
// 带有事件处理的最终版本。

import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

public class BmiGui3 implements ActionListener {
    // BmiGui3 是自己的可运行客户端程序
    public static void main(String[] args) {
        BmiGui3 gui = new BmiGui3();
    }

    // 屏幕组件存储为字段中
    private JFrame frame;
    private JTextField heightField;
    private JTextField weightField;
    private JLabel bmiLabel;
    private JButton computeButton;

    public BmiGui3() {
        // 设置组件
        heightField = new JTextField(5);
        weightField = new JTextField(5);
        bmiLabel = new JLabel("输入您的身高和体重");
        computeButton = new JButton("Compute");

        // 将 GUI 监听器附加到 compute 按钮
        computeButton.addActionListener(this);

        // 布局
        JPanel panel = new JPanel(new GridLayout(2, 2));
        panel.add(new JLabel("Height: "));
        panel.add(heightField);
        panel.add(new JLabel("Weight: "));
        panel.add(weightField);

        // 整体框架
        frame = new JFrame("BMI");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(new BorderLayout());
        frame.add(panel, BorderLayout.NORTH);
        frame.add(bmiLabel, BorderLayout.CENTER);
        frame.add(computeButton, BorderLayout.SOUTH);
        frame.pack();
        frame.setVisible(true);
    }

    public void actionPerformed(ActionEvent event) {
        // 实现将在这里
    }
}
```

## 示例 2：信用卡 GUI

你可能不知道信用卡包含许多用于验证的信息。鲁恩算法指出，如果你以某种方式求和信用卡的数字，总和将是 10 的倍数。数字求和算法可以描述如下：考虑一个基于零索引的信用卡，第一个是索引 0，最后一个是索引 15。从最右边的数字开始处理每个数字。对于奇数索引数字（第 15、13 个等），直接加上该数字。对于偶数索引数字（第 14、12 个等），将数字乘以 2。如果倍后的值大于 10，则将其相加。

以下伪代码描述了鲁恩算法：

```
sum = 0;
for (信用卡中的每个数字，从右开始) {
  if (数字索引是奇数) {
    加上数字;
  }
  将数字乘以 2;
  if (倍后的值 < 10) {
    加上倍后的值;
  } else {
    将倍后的值拆分为两个数字;
    加上第一位数字;
    加上第二位数字;
  }
}
```

`41111111111111`和`4408041274369853`是通过鲁恩测试的信用卡示例。图 14.3 显示了后者的求和细节。

让我们编写一个 GUI，用户可以在其中输入信用卡，按下按钮进行验证，然后收到一条指示该号码是否有效的消息。该 GUI 将具有如下外观：

![](img/aea18896a4bced58de45f29f5a93f7b3_778_0.png)

| CC | 4408 0412 7436 9853 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Scale | 4 | 4 | 0 | 8 | 4 | 1 | 2 | 7 | 4 | 3 | 6 | 9 | 8 | 5 | 3 |
| | -2 | -2 | -2 | -2 | -2 | -2 | -2 | -2 | | | | | | |
| | 8 | 0 | 8 | 0 | 4 | 2 | 14 | 4 | 6 | 6 | 18 | 1 | 10 | 3 |
| Sum | 8 + 4 + 0 + 8 + 0 + 4 + 2 + 1+4 + 4 + 6 + 6 + 1+8 + 1+0 + 3 = 70 | | | |

70 可以被 10 整除，因此此卡号是有效的。

图 14.3 使用鲁恩算法计算校验位的示例。

## 第 14 章 图形用户界面

为了验证信用卡号，我们在“验证信用卡号”（Verify CC Number）文本字段上放置了一个监听器。在监听器的`actionPerformed`方法中，我们需要从文本字段中读取文本，判断数字是否有效，并使用这些信息设置标签的文本。由于监听器涉及组件之间的交互，我们将采用面向对象的方式，并使其成为它自己的监听器。

一如既常，我们先处理组件和布局，然后再考虑事件处理。窗口可以使用`FlowLayout`（流布局），将标签换行到第二行。以下是程序的初始版本，它不响应事件。与之前的 Swing3 示例一样，GUI 通过包含一个`main`方法成为自身的客户端程序：

- 1 提供了一个用于验证信用卡号的 GUI。
- 2 不带事件处理的初始版本。



```java
import java.awt.*;
import java.swing.*;

public class CreditCardGUI {
    public static void main(String[] args) {
        CreditCardGUI gui = new CreditCardGUI();
    }

    // fields
    private JFrame frame;
    private JTextField numberField;
    private JLabel validLabel;
    private JButton verifyButton;

    // creates components, does layout, shows window onscreen
    public CreditCardGUI() {
        numberField = new JTextField(16);
        validLabel = new JLabel("not verified");
        verifyButton = new JButton("Verify CC Number");

        frame = new JFrame("Credit card number verifier");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(new Dimension(350, 100));
        frame.setLayout(new FlowLayout());
        frame.add(numberField);
        frame.add(verifyButton);
        frame.add(validLabel);
        frame.setVisible(true);
    }
```

现在让我们编写 GUI 的第二个版本，用于监听“验证信用卡号”按钮上的动作事件。代码足够简单，值得将其放入一个独立的方法中。代码将从右侧开始遍历每个数字，将 10 或更大的数字拆分为单独的数字，然后再加到总和中。我们可以通过将数字 `/ 10` 和 `% 10` 加到总和中来实现这一点。如果数字不超过 10，我们实际上可以直接将这两个值加到总和上。

## 14.3 组件之间的交互

因为对于单位数字，`digit / 10` 是 0，而 `digit % 10` 是数字本身。以下是实现验证的代码：

```java
// 根据 Luhn 校验和算法返回给定字符串
// 是否是有效的 Visa 卡号
public boolean isValidCC(String text) {
    int sum = 0;
    for (int i = text.length() - 1; i >= 0; i--) {
        int digit = Integer.parseInt(text.substring(i, i + 1));
        if (i % 2 == 0) { // 双偶数位
            digit *= 2;
        }
        sum += (digit / 10) + (digit % 10);
    }
    // 有效数字之和为 10 的倍数
    return sum % 10 == 0 && text.startsWith("4");
}
```

现在我们有一个方法可以告诉我们给定字符串是否代表有效的 Visa 号，我们可以编写代码来监听事件。首先，我们将修改类头：

```java
public class CreditCardGUI implements ActionListener {
```

接下来，我们需要编写 `actionPerformed` 方法。该方法很短且简单，因为 `isValidCC` 方法承担了大部分工作：

```java
// 设置标签的文本以显示信用卡号是否有效。
public void actionPerformed(ActionEvent event) {
    String text = numberField.getText();
    if (isValidCC(text)) {
        validLabel.setText("Valid number!");
    } else {
        validLabel.setText("Invalid number.");
    }
}
```

将所有内容整合在一起，是程序的完整版本：

```java
// 提供一个用于验证信用卡号的 GUI。
// 带有事件处理的最终版本。

import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

public class CreditCardGUI implements ActionListener {
    public static void main(String[] args) {
        CreditCardGUI gui = new CreditCardGUI();
    }

    // fields
    private JFrame frame;
    private JTextField numberField;
    private JLabel validLabel;
    private JButton verifyButton;

    // creates components, does layout, show onscreen
    public CreditCardGUI() {
        numberField = new JTextField();
        validLabel = new JLabel("not yet verified");
        verifyButton = new JButton("Verify CC Number");

        // event listeners
        verifyButton.addActionListener(this);

        frame = new JFrame("Credit card number verifier");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(new Dimension(350,100));
        frame.setLayout(new FlowLayout());
        frame.add(numberField);
        frame.add(verifyButton);
        frame.add(validLabel);
        frame.setVisible(true);
    }

    // 根据 Luhn 校验和算法返回给定字符串
    // 是否是有效的 Visa 卡号。
    public boolean isValidCC(String text) {
        int sum = 0;
        for (int i = text.length() - 1; i >= 0; i--) {
            int digit = Integer.parseInt(text.substring(i, i + 1));
            if (i % 2 == 0) { // 双偶数位
                digit *= 2;
            }
            sum += (digit / 10) + (digit % 10);
        }
        // 有效数字之和为 10 的倍数
        return sum % 10 == 0 && text.startsWith("4");
    }

    // 设置标签的文本以显示信用卡号是否有效。
    public void actionPerformed(ActionEvent event) {
        String text = numberField.getText();
        if (isValidCC(text)) {
            validLabel.setText("Valid number!");
        } else {
            validLabel.setText("Invalid number.");
        }
    }
}
```

到目前为止我们开发的 GUI 使用了一些组件（按钮、标签、文本字段），并且只响应动作事件。在本节中，我们将查看其他组件并对其进行响应。

## 14.4 附加组件

### 文本区域、滚动条和字体

文本字段对于单行输入非常有用，但当用户想要输入更复杂的消息时，它们的效果并不好。另一种组件被称为 `textArea`（文本区域），它代表多行输入。文本区域由 `JTextArea` 对象表示。你可以通过传递行数和列数来构造一个 `JTextArea`。这创建了一个 5 行高、20 宽的文本区域：

```java
// 展示 JTextArea。
import java.awt.*;
import javax.swing.*;

public class JFrameExample {
    public static void main(String[] args) {
        JFrame frame = new JFrame();
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(new FlowLayout());
        frame.setSize(new Dimension(300,150));
        frame.setTitle("Text frame");
        JTextArea area = new JTextArea(5, 20);
        frame.add(area);
        frame.setVisible(true);
    }
}
```

该程序在文本区域中输入文本之前和之后会产生如下输出：

| Text frame | |

| --- | --- |

| | Text area text begins here (pressing Enter) |

在更大的示例中，事件监听器可以使用 `getText` 方法检查文本区域中编写的文本，或通过调用 `setText` 方法在文本区域设置新文本。

目前，当用户输入的内容过多导致文本区域无法容纳时，文本会直接从底部消失：

为了解决这个问题，我们可以通过向文本区域添加名为滚动条的常用组件使其变得可滚动。滚动条由名为 `JScrollPane` 的特殊容器实例表示。要使组件变为可滚动，创建一个 `JScrollPane`，将组件添加到滚动面板中，然后将滚动面板添加到整个框架中。`JScrollPane`是通过将相关组件作为参数构造的：

```java
// 在此文本区域上使用滚动条
frame.add(new JScrollPane(area));
```

屏幕上文字的外由字体决定，字体是描述如何显示文本字符的集合。如果你不喜欢文本区域的默认字体，请记住每个组件都有一个可以设置的字体属性。正如之前在补充 3G 中讨论的，字体由 `Font` 对象表示。`Font` 对象通过传递其名称、样式（如粗体或斜体）和像素大小来创建。例如，以下行代码告诉文本区域使用大小为 14 的衬线字体：

```java
area.setFont(new Font("Serif", Font.BOLD, 14));
```

文本区域现在呈现如下外观：

关于 `Font` 对象的更详细讨论，请参阅补充 3G。

## 14.4 其他组件与事件

### 图标

许多 Java 组件（包括按钮和标签）都有一个 `icon` 属性，可以将其设置为组件上的图像。该属性的类型为 `Icon`。

`getIcon` 和 `setIcon` 方法使用实现 `Icon` 接口的值。获取实现 `Icon` 对象的最简单方法是创建一个 `ImageIcon` 类型的对象。`ImageIcon` 构造函数接受一个 `String` 参数，表示要加载的图像。图像是硬盘上的文件，例如 GIF、JPG 或 PNG 图片。将你的图像文件与程序文件放在同一个文件夹中。

以下代码在按钮上放置了一个图标。`smiley.jpg` 已保存到与代码相同的文件夹中：

```java
// 为此按钮创建一个笑脸图标
JButton button = new JButton("Have a nice day");
button.setIcon(new ImageIcon("smiley.jpg"));
```

当放入框架中时，按钮的外观如下。它被放大以容纳其文本和新图标：

![](img/aea18896a4bced58de45f29f5a93f7b3_784_0.png)

创建图标的另一种方法是自己绘制。你可以使用 `BufferedImage` 对象创建一个图像缓冲区，并使用 `Graphics` 笔在上面绘制，就像在补充材料 3G 中使用 `DrawingPanel` 那样（事实上，`DrawingPanel` 是用内部 `BufferedImage` 实现的）。`BufferedImage` 是 `java.awt.image` 包中的类，所以如果你想使用它，必须导入该包：

```java
import java.awt.image.*; // 用于 BufferedImage
```

这里是 `BufferedImage` 构造函数的头部：

#### 表 14.6 BufferedImage 对象的有用方法

```java
public BufferedImage(int width, int height, int type)
```

构造一个给定尺寸和类型的图像缓冲区。有效的类型有：

- `BufferedImage.TYPE_INT_ARGB`: 具有透明背景的图像。
- `BufferedImage.TYPE_INT_RGB`: 具有实黑色背景的图像。

```java
public Graphics getGraphics()
```

返回用于在此图像缓冲区上绘制的笔。

要使用 `BufferedImage`，请构造一个特定大小和类型的实例（我们推荐使用 `BufferedImage.TYPE_INT_ARGB`），然后使用 `getGraphics` 方法从其获取 `Graphics` 对象。然后你可以发出标准的绘制命令，如 `drawRect` 或 `fillOval`。一旦你在 `BufferedImage` 上绘制，就可以创建一个新的 `ImageIcon` 对象或将 `BufferedImage` 传递给 `ImageIcon` 构造函数。你可以通过调用该组件上的 `setIcon` 并传递 `Image` 作为参数将此 `ImageIcon` 设置为屏幕组件的图标，如下代码所示：

```java
JButton button = new JButton();
button.setText("My drawing");

// 为此按钮创建一个形状图像图标
BufferedImage image = new BufferedImage(100, 100,
BufferedImage.TYPE_INT_ARGB);
Graphics g = image.getGraphics();
g.setColor(Color.YELLOW);
g.fillRect(10, 20, 80, 70);
g.setColor(Color.RED);
g.fillOval(40, 50, 25, 25);

ImageIcon icon = new ImageIcon(image);
button.setIcon(icon);
```

你也可以通过调用 `setIconImage` 方法将 `BufferedImage` 作为框架的图标图像：

```java
frame.setIconImage(image);
```

这是一个 Java 设计师选择了误导名称的情况，因为 `setIconImage` 方法不接受 `ImageIcon` 作为参数。

当放入框架中时，按钮的外观如下。注意，窗口左上角也出现了一个较小版本的图标，这是因为调用了 `setIconImage`：

![](img/aea18896a4bced58de45f29f5a93f7b3_785_0.png)

### 鼠标事件

到目前为止，我们一直只使用 `ActionListener` 对象。当我们想要监听鼠标点击或移动时，我们使用另一种类型的监听器 `MouseListener`。`MouseListener` 接口位于 `javax.swing.event` 包中，你需要导入它：

```java
import javax.swing.*; // 用于鼠标事件
```

`MouseListener` 接口用于处理鼠标输入的方法列如表 14.6 所示。方法非常多，你可能不想实现所有它们。许多程序只想处理按钮按下或光标移动。在这种情况下，你必须为所有其他 `MouseInputListener` 方法编写空版本，否则该类将无法正确实现接口并导致无法编译。

为了避免这种困扰，Java 提供了一个名为 `MouseAdapter` 的类，它实现了 `MouseListener` 接口中所有方法的空版本。你可以扩展 `MouseAdapter` 并仅重写你想要处理的鼠标事件对应的方法。

#### 表 14.7 MouseListener 接口的方法

| 方法 | 描述 |
| :--- | :--- |
| `public void mouseClicked(MouseEvent event)` | 当在组件上点击[并按下且释放]鼠标键时调用。 |



| `public void mouseDragged(MouseEvent event)` | 当在组件上按下鼠标键并然后进行拖动时调用。 |
| `public void mouseEntered(MouseEvent event)` | 当鼠标进入组件时调用。 |
| `public void mouseExited(MouseEvent event)` | 当鼠标离开组件时调用。 |
| `public void mouseMoved(MouseEvent event)` | 当鼠标移动到组件上但没有按下任何按钮时调用。 |
| `public void mousePressed(MouseEvent event)` | 当在组件上按了鼠标键时调用。 |
| `public void mouseReleased(MouseEvent event)` | 当在组件上释放鼠标键时调用。 |

例如，让我们写一个在光标移动过组件时做出响应的鼠标监听器。为了此，我们将扩展`MouseAdapter`类并仅重写`mouseEntered`：

```java
1 // 通过显示对话框响应鼠标事件。
2 
3 import java.awt.*;
4 import javax.swing.*;
5 import java.awt.event.*;
6 
7 public class MovementListener extends MouseAdapter {
8     public void mouseEntered(MouseEvent event) {
9         JOptionPane.showMessageDialog(null, "Mouse entered!");
10     }
11 }
```

## 14.4 其他组件与事件

### 表 14.9 MouseEvent 对象的实用方法

| 方法 | 描述 |
| :--- | :--- |
| `public int getButton()` | 返回被按下或释放的鼠标按钮数字（1 表示左键，2 表示右键，依此类推）。 |
| `public int getCount()` | 返回用户点击按钮的次数：常用于检测双击。 |
| `public int getPoint()` | 返回鼠标事件发生的 (x, y) 点。 |
| `public int getX()` | 返回鼠标事件发生的 x 坐标。 |
| `public int getY()` | 返回鼠标事件发生的 y 坐标。 |

程序产生如下图形化输出，在用户将鼠标移动到`JLabel`之前和之后均有显示：

![](img/aea18896a4bced58de45f29f5a93f7b3_788_0.png)

在处理动作监听器（action listeners）时，`actionPerformed`方法接受一个类型为`ActionEvent`的参数，该参数表示发生的动作。我们在程序中没有对该对象进行任何操作。然而，鼠标监听器中对应的参数（类型为`MouseEvent`）非常有用。`MouseEvent`参数中存储了许多非常实用的信息。表 14.9 列出了它的其中一些方法。

例如，以下鼠标监听器可以附加到任何组件上，并重构自身。每当用户按下鼠标按钮时，它都会显示一条消息：

- 通过显示消息来响应鼠标点击
- 指明用户点击的位置

```java
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;

public class ClickListener extends MouseAdapter {
    public void mousePressed(MouseEvent event) {
        JOptionPane.showMessageDialog(null,
            "Mouse pressed at position: (" + event.getX() + ", " + event.getY() + ")");
    }
}
```

## 第 14 章 图形用户界面

作为另一个示例，以下程序使用鼠标监听器将标签的文本设置为：当鼠标在标签上移动时显示鼠标的位置。与我们之前的示例一样，该 GUI 是面向对象的，并作为其自身的监听器：

```java
// 一个显示鼠标在标签上移动位置的 GUI。
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

public class MousePointGUI extends MouseAdapter {
    public static void main(String[] args) {
        MousePointGUI gui = new MousePointGUI();
    }

    // 字段
    private JFrame frame;
    private JLabel label;

    public MousePointGUI() {
        label = new JLabel();
        label.setText("Move the mouse over me!");

        // 监听鼠标事件
        label.addMouseListener(this);
        label.addMouseMotionListener(this);

        frame = new JFrame();
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(new Dimension(200, 100));
        frame.setTitle("A frame");
        frame.add(label);
        frame.setVisible(true);
    }

    // 响应鼠标移动事件
    public void mouseMoved(MouseEvent event) {
        label.setText("(" + event.getX() + ", " + event.getY() + ")");
    }
}
```

程序产生如下图形化输出，在用户将鼠标移动到标签上的几个不同点之后显示：

![](img/aea18896a4bced58de45f29f5a93f7b3_789_0.png)

## 14.5 二维图形

在补充附材料 3 中，我们引入了一个名为`JPanel`的图形类，它保持了简单，以便你不需要学习许多关于图形用户界面的细节。现在我们开始揭开这些细节，可以检查如何手动绘制我们自己的 2D 图形。这将引导我们理解`DrawingPanel`的代码，甚至自己重新实现它。

### 在面板上绘图

在本章早些时候，我们讨论了`JPanel`组件，将其用作布局其他组件的隐形容器。面板充当我们可以绘图的表面。`JPanel`对象有一个名为`paintComponent`的方法，它用于在屏幕上绘制面板。默认情况下，该方法不绘制任何内容，面板是透明的。

我们使用继承来改变面板的绘制行为。如果我们想创建一个可以在其上绘制形状的面板，可以扩展`JPanel`并重写`paintComponent`方法。以下是我们必须重写的`paintComponent`方法头：

```java
public void paintComponent(Graphics g)
```

它的参数`Graphics g`如果你读过补充附材料 3G，应该会让你觉得很熟悉。`Graphics`是 Java 的`java.awt`包中的一个类，拥有在表面上绘制形状、线条和图像的方法。将`Graphics`对象想象成一支笔，将面板想象成一张纸。

在编写`paintComponent`方法时有一个特殊之处。记住，当你重写一个方法时，你替换了父类之前的功能。然而，我们并不想丢失`JPanel`中`paintComponent`的行为，因为它在面板内部执行了重要的操作；我们只是想向它添加额外的行为。因此，在重写`paintComponent`时，所做的第一件事是调用`super.paintComponent`并将`Graphics`对象`g`作为其参数传递。如果不这样做，当你调整大小或最小化窗口时，可能会出现幽灵残影。

```java
// 一个在表面上绘制矩形的面板。
import java.awt.*;
import javax.swing.*;

class RectPanel extends JPanel {
    public void paintComponent(Graphics g) {
        super.paintComponent(g);
        g.setColor(Color.RED);
        g.fillRect(20, 40, 70, 30);
    }
}
```

## 第 14 章 图形用户界面

现在我们可以编写一个独立的类来创建 GUI，它会绘制矩形。它将显示在屏幕上。以下是使用`RectPanel`的代码：

```java
// 一个在表面上绘制矩形的面板。
import java.awt.*;
import javax.swing.*;

class UserPanel {
    public static void main(String[] args) {
        JFrame frame = new JFrame();
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(300, 200);
        frame.setTitle("A panel with rectangles");
        RectPanel panel = new RectPanel();
        panel.setBackground(Color.WHITE);
        frame.add(panel);
        frame.setVisible(true);
    }
}
```

程序产生如下图形化输出：

![](img/aea18896a4bced58de45f29f5a93f7b3_791_0.png)

## 14.5 二维图形

你可能会问，为什么不直接使用`DrawingPanel`而要费这些精力？有几个原因。其中一个是`DrawingPanel`实际上并不是 Java 的一部分，因此你在教室之外无法依赖它。此外，虽然它对于简单的绘制是一个很好的工具，但你无法通过以下方式实现组件混合：

```java
JPanel north = new JPanel(new FlowLayout());
north.add(new JLabel("Type your name:"));
north.add(new JTextField(10));
frame.add(north, BorderLayout.NORTH);
```

```java
frame.add(new JButton("Submit"), BorderLayout.SOUTH);
```

```java
RectPanel panel = new RectPanel();
panel.setBackground(Color.WHITE);
frame.add(panel, BorderLayout.CENTER);
```

```java
frame.setVisible(true);
```

### 使用定时器动画

面板不需要显示静态图形。通过使用名为定时器的对象（由`Timer`类对象实现），你可以让面板动画化以显示移动图像。定时器一旦启动，就会按固定间隔触发动作事件。你为定时器提供一个要使用的`ActionListener`和一个毫秒级的延迟，它就会完成其余工作。创建动画需要两个要素：

- 一个以某种方式更新面板绘制的`ActionListener`对象
- 用于按固定间隔调用`ActionListener`的`Timer`对象

让我们修改上一节的`RectPanel`类，以便其矩形可以在面板上移动。为了让它们移动，我们必须将位置存储在`JPanel`对象的字段中。我们在程序运行时更改字段的值，然后重新绘制矩形，这会让它们看起来像正在移动。我们将 x 和 y 的变化存储在名为`dx`和`dy`的字段中。以下是我们的动画`RectPanel`的代码：

```java
// 一个绘制动画矩形的面板
// 初始版本--将在后续节更改
import java.awt.*;
import java.awt.event.*;
```

# 第14章 图形用户界面

```java
import javax.swing.*;

public class AnimatedRectPanel extends JPanel {
    private Point p1; // 第一个矩形的位置
    private Point p2; // 第二个矩形的位置
    private int dx; // 水平移动的距离
    private int dy; // 垂直移动的距离

    public AnimatedRectPanel() {
        p1 = new Point(20, 40);
        p2 = new Point(60, 10);
        dx = 5;
        dy = 5;
    }

    // 在屏幕上绘制面板
    public void paintComponent(Graphics g) {
        super.paintComponent(g);
        g.setColor(Color.RED);
        g.fillRect(p1.x, p1.y, 70, 30);
        g.setColor(Color.BLUE);
        g.fillRect(p2.x, p2.y, 80, 20);
    }
}
```

下一步是创建一个动作监听器，在每次被调用时更新面板。我们将让`AnimatedRectPanel`成为它自己的监听器。你可能想在`actionPerformed`方法中放入一个循环，但动画并不是这样工作的。相反，`actionPerformed`以很小的距离移动矩形，而定时器会按固定的间隔重复调用它，以重新绘制并动画面板。第一个矩形将水平移动，在面板的左边缘和右边缘之间反弹。第二个矩形将垂直移动，在顶部和底部边缘之间反弹。在我们的`ActionListener`中最简单的方法是调整两个点的坐标：

```java
// 初始版本--不会转回
public void actionPerformed(ActionEvent event) {
    p1.x += dx;
    p2.y += dy;
}
```

然而，由于矩形本应该在面板边缘上反弹，我们需要检查矩形是否击中了任何一个边缘。当第一个矩形的 x 坐标降到 0 时，我们知道它击中了左边缘；当它的 x 坐标加上它的宽度超过面板的宽度时，我们就知道它击中了右边缘。第二个矩形的计算方法类似，只是我们查看的是矩形和面板的 y 坐标和高度。

关于动画`JPanel`还有最后一点要提。当我们改变面板的绘制方式时，我们必须调用`repaint`让面板再次绘制。如果不调用`repaint`，我们在屏幕上将看不到任何变化。（忘记调用`repaint`是一个常见的 bug。）这里是实现反弹行为并重新绘制面板的代码：

## 14.5 2D 图形

```java
// 定时器按固定间隔重新绘制面板
public void actionPerformed(ActionEvent event) {
    p1.x += dx;
    p2.y += dy;
    if (p1.x <= 0 || p1.x >= getWidth()) {
        dx = -dx; // 矩形1 击中了左/右边缘
    }
    if (p2.y <= 0 || p2.y + 80 >= getHeight()) {
        dy = -dy; // 矩形2 击中了上/下边缘
    }
    repaint(); // 重新绘制面板
}
```

现在我们的`ActionListener`代码完成了，我们必须创建并启动调用该监听器的定时器。让我们在`AnimatedRectPanel`的构造函数中添加这些代码：

```java
// 设置定时器每 100 ms 动画化矩形
Timer timer = new Timer(100, this);
timer.start();
```

这里是包含了所有功能的`AnimatedRectPanel`程序的完整版本：

```java
1 // 在其表面上绘制动画矩形的面板。
2 import java.awt.*;
3 import java.awt.event.*;
4 import javax.swing.*;
5 
6 public class AnimatedRectPanel2 extends JPanel
7     implements ActionListener {
8     private Point p1; // 第一个矩形的位置
9     private Point p2; // 第二个矩形的位置
10    private int dx; // 水平移动的距离
11    private int dy; // 垂直移动的距离
12    private Timer timer;
13
14    AnimatedRectPanel2() {
15        p1 = new Point(20, 40);
16        p2 = new Point(60, 10);
17        dx = 5;
18        dy = 5;
19        // 设置定时器每 100 ms 动画化矩形
20        timer = new Timer(100, this);
21        timer.start();
22    }
23
24    // 在屏幕上绘制面板
25    public void paintComponent(Graphics g) {
26        super.paintComponent(g);
27        g.setColor(Color.RED);
28        g.fillRect(p1.x, p1.y, 70, 30);
29        g.setColor(Color.BLUE);
30        g.fillRect(p2.x, p2.y, 80, 20);
31    }
32
33    // 响应定时器事件
34    public void actionPerformed(ActionEvent event) {
35        p1.x += dx;
36        p2.y += dy;
37        if (p1.x <= 0 || p1.x + 70 >= getWidth()) {
38            dx = -dx;
39        }
40        if (p2.y <= 0 || p2.y + 20 >= getHeight()) {
41            dy = -dy;
42        }
43        repaint();
44    }
45 }
```



```java
23 super.paintComponent(g);
24 g.setColor(Color.RED);
25 g.fillRect(p1.x, p1.y, 70, 30);
26 g.setColor(Color.BLUE);
27 g.fillRect(p2.x, p2.y, 80, 20);
28 }
```

```java
// 定时器按固定间隔重新绘制面板
public void actionPerformed(ActionEvent event) {
    p1.x += dx;
    p2.y += dy;
    if (p1.x <= 0 || p1.x >= getWidth()) {
        dx = -dx; // 矩形1 击中了左/右边缘
    }
    if (p2.y <= 0 || p2.y + 80 >= getHeight()) {
        dy = -dy; // 矩形2 击中了上/下边缘
    }
    repaint(); // 重新绘制面板
}
```

## 14.10 `Timer` 的常用方法

| 方法 | 描述 |
| :--- | :--- |
| `Timer(int msDelay, ActionListener listener)` | 创建每 `msDelay` 激活一次监听器的定时器。 |
| `public void start()` | 启动定时器。 |
| `public void stop()` | 停止定时器。 |

## 14.6 研究案例：实现 `DrawingPanel`

之前的章节中，我们使用 `DrawingPanel` 创建简单的 2D 图形。在最后部分，我们将分析 `DrawingPanel` 是如何工作的并实现它的基本版本。

### 无事件版本

当我们创建 `DrawingPanel` 时，有两个主要的设计目标。第一个是为客户端提供访问图形对象的方法。第二个是提供状态化绘制，以便客户端不需要了解 `paintComponent`、`repaint()` 等其他方法。

`DrawingPanel` 的状态化绘制通过对 `BufferedImage` 对象进行绘制来实现。`DrawingPanel` 声明了一个 `BufferedImage` 字段并在构造函数中初始化它。当客户端调用 `DrawingPanel` 的 `getGraphics()` 时，会返回缓冲区的引用。为了将缓冲区放置在屏幕上，将其设置为 `JLabel` 的图标。

`DrawingPanel` 类的开头与本章的代码非常相似。它通过声明图形组件开始。这些字段是窗口帧、屏幕图像的图形对象以及持有图像的面板：

```java
public class DrawingPanel {
    private JFrame frame;      // 窗口帧
    private JPanel panel;      // 绘制表面
    private Graphics g;        // 绘制笔
}
```

以下是其完整代码版本：

```java
1 // 用于绘制持久图像的接口。
2 // 无事件版本。
3
4 import java.awt.*;
5 import java.awt.image.*;
6 import java.swing.*;
7
8 public class DrawingPanel {
9     private JFrame frame;      // 窗口帧
10    private JPanel panel;      // 绘制表面
11    private Graphics g;        // 绘制笔
12
13    // 构建给定大小的绘制面板
14    DrawingPanel(int width, int height) {
15        // 设置要在上面绘制的空图像
16        image = new BufferedImage(width, height, BufferedImage.TYPE_ARGB);
17        g = image.getGraphics();
18        g.setColor(Color.BLACK);
19
20        // 将图像封装在面板内的标签中
21        label = new JLabel(image);
22        label.setIcon(new ImageIcon(image));
23        panel = new JPanel(new FlowLayout());
24        panel.setBackground(Color.WHITE);
25        panel.setPreferredSize(new Dimension(width, height));
26        panel.add(label);
27
28
29
30        // 设置 JFrame
31        frame = new JFrame("Drawing Panel");
```

# 第 14 章 图形化用户界面

```java
31 frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
32 frame.setResizable(false);
33 frame.add(panel);
34 frame.pack();
35 frame.setVisible(true);
36
37
38 // 获取在面板上绘图的 Graphics 对象
39 public Graphics getGraphics() {
40     return g;
41 }
42
43 // 设置绘制面板的背景颜色
44 public void setBackground(Color c) {
45     panel.setBackground(c);
46 }
47
48 // 在屏幕上显示或隐藏绘制面板
49 public void setVisible(boolean visible) {
50     frame.setVisible(visible);
51 }
```

该代码将缓冲区作为图标放入标签，然后将缓冲区存储在放在框架内的面板中。使用这个中间面板可以正确设置背景颜色。

## 带有事件的第二个版本

更复杂的 `DrawingPanel` 版本还将作为鼠标事件的监听器，这样当用户将鼠标悬停在面板上时，底部的状态栏将显示光标（x, y）位置以供调试。为了实现这一点，可以修改 `DrawingPanel` 以作为鼠标监听器，并将其附加以监听其中心面板。当鼠标移动时，鼠标监听器将接收事件，并更新状态栏文本以显示鼠标位置。

为了实现这些功能，我们将类头更改为如下内容：

```java
public class DrawingPanel extends MouseAdapter {
```

我们将添加一个类型为 `JLabel` 的新字段 `statusBar`，将其放置在框架的南部（south）区域。初始状态状态栏的文本为空，但如果鼠标移动，它的监听器将更改文本以反映光标的位置。以下代码实现了鼠标监听器的 `mouseMoved` 方法：

```java
// 鼠标移动时绘制状态栏文本
public void mouseMoved(MouseEvent e) {
    statusBar.setText("(" + e.getX() + ", " + e.getY() + ")");
}
```

我们还会在构造函数中添加以下代码，将 `DrawingPanel` 作为监听器附加到其内部面板：

## 14.6 案例研究：实现 `DrawingPanel`

```java
// 附加监听器以观察鼠标移动
panel.addMouseListener(this);
panel.addMotionListener(this);
```

在 `DrawingPanel` 中我们还应该处理另一种事件。当使用 `DrawingPanel` 的客户端代码花费很长时间时（例如当我们使用控制台输出来引导绘制哪些形状时），我们可能需要定期重绘 `DrawingPanel` 以反映客户端已绘制的任何形状。为了保持简单，我们不想强制客户端自己重绘。

要强制 `DrawingPanel` 在给定间隔内刷新，我们必须使用 `Timer` 定期调用 `repaint`。由于 `Timer` 需要一个动作监听器作为参数，我们将使 `DrawingPanel` 实现 `ActionListener` 接口。它变得越来越长的头部看起来像这样：

```java
public class DrawingPanel extends MouseInput
    implements ActionListener (
```

`actionPerformed` 方法只需要在主屏幕面板上调用 `repaint`。

```java
// 用于定时器重复重绘屏幕
public void actionPerformed(ActionEvent e) {
    panel.repaint();
}
```

最后，我们将在 `DrawingPanel` 的构造函数中添加以下行来创建并启动定时器：

```java
// 启动重绘定时器以刷新屏幕
Timer timer = new Timer(250, this);
timer.start();
```

将所有内容整合在一起，这里是 `DrawingPanel` 类第二个版本的完整代码：

```java
1 // 用于绘制持久化图像的简单接口。
2 // 带有事件的最终版本。
3
4 import java.awt.*;
5 import java.awt.event.*;
6 import java.awt.image.*;
7 import javax.swing.*;
8 import javax.swing.event.*;
9
10 public class DrawingPanel extends MouseInput
11 implements ActionListener (
12 private JFrame frame; // 整体窗口框架
13 private JPanel panel; // 绘制表面
14 private JLabel statusBar; // 状态栏
15 private Graphics g; // 绘图笔
16
17 // 构建指定大小的绘制面板
18 public DrawingPanel(int width, int height) {
19 // 设置我们将在其绘制的空图像
20 BufferedImage image = new BufferedImage(width, height,
21 BufferedImage.TYPE_INT_ARGB);
22 g = image.getGraphics();
23 g.setColor(Color.BLACK);
24
25 // 将图像封装在面板内的标签中
26 JLabel label = new JLabel();
27 label.setIcon(new ImageIcon(image));
28 panel = new JPanel(new FlowLayout());
29 panel.setBackground(Color.WHITE);
30 panel.setPreferredSize(new Dimension(width, height));
31 panel.add(label);
32
33
34 // 显示鼠标位置的状态栏
35 statusBar = new JLabel(" \ ");
36
37 // 附加监听器以观察鼠标移动
38 panel.addMouseListener(this);
39 panel.addMouseMotionListener(this);
40 // 设置 JFrame
41 frame = new JFrame("Drawing Panel");
42 frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
43 frame.setSize(width, height);
44 frame.setLayout(new BorderLayout());
45 frame.add(panel, BorderLayout.CENTER);
46 frame.add(statusBar, BorderLayout.SOUTH);
47 frame.setVisible(true);
48
49 // 启动重绘定时器以刷新屏幕
50 timer = new Timer(250, this);
51 timer.start();
52 }
53
54 // 获取在面板上绘图的 Graphics 对象
55 public Graphics getGraphics() {
56 return g;
57 }
58
59 // 设置绘制面板的背景颜色
60 public void setBackground(Color c) {
61 panel.setBackground(c);
62 }
63
64 // 在屏幕上显示或隐藏绘制面板
65 public void setVisible(boolean visible) {
66 frame.setVisible(visible);
67 }
68
69 // 用于定时器重复重绘屏幕
70 public void actionPerformed(ActionEvent e) {
71 panel.repaint();
72 }
73
74 // 鼠标移动时绘制状态栏文本
75 public void mouseMoved(MouseEvent e) {
76 statusBar.setText("(" + e.getX() + ", " + e.getY() + ")");
77 }
78 }
```

# 第 14 章 图形化用户界面

## 总结

图形用户界面（GUI）有一个包含按钮、文本字段和其他组件的窗口框架。布局管理器可以通过嵌套来组合形成复合布局。`JOptionPane` 类是一个简单的 GUI，用于显示消息和提示输入。当用户与图形组件交互时，Java 会生成特殊的事件对象。要编写交互式 GUI，必须响应这些事件。一些常见的图形组件是按钮（`JButton` 对象）、文本字段（`JTextField` 对象）和标签（`JLabel` 对象）。最常见的事件类型是 `ActionEvent`，它可以通过实现 `ActionListener` 接口来处理。你也可以通过扩展 `MouseAdapter` 类来响应 `MouseEvent`。GUI 的功能可以使用定时器对象进行动画处理，定时器定期向动作监听器触发事件。

# 自测练习题

## 14.1 节：GUI 基础

1. 本节介绍了编写图形程序时导入的三个新包。它们是什么？写出使用这些类所需的导入语句。
2. 编写 Java 代码弹窗询问用户的年龄。如果用户输入的数字小于 40，用消息框回答他们年轻，调侃用户老。例如：
3. 什么是组件？框架与其他组件有什么区别？
4. 列出框架的两个属性。给出一个代码示例，创建一个新框架并将这两个属性设置为你所选择的新值。
5. 识别用于表示以下图形组件的 Java 类：

## 自测题

6. 编写一段代码创建两个按钮：一个为绿色背景且文字为“Click me”，另一个为黄色背景且文字为“Do not touch”。

## 第 14.2 节：组件的布局

7. 识别哪种布局管理器可以产生以下每个屏幕外观：

![](img/aea18896a4bced58de45f29f5a93f7b3_802_0.png)

8. 在给定以下变量声明的情况下，编写代码产生问题 7 所示的每个布局：

```java
JButton b1 = new JButton("Button 1");
JButton b2 = new JButton("Button 2");
JButton b3 = new JButton("Button 3");
JButton b4 = new JButton("Button 4");
JButton b5 = new JButton("Wide Button 5");
```




## 第 14.3 节：组件之间的交互

9. 什么是事件？处理标准事件时使用什么接口？

10. 描述处理事件必须编写的代码。必须编写哪些类和方法？必须向目标组件（例如要点击的按钮）发送哪些消息？

11. 编写一个可以附加到按钮的 `ActionListener`，使得每当按钮被点击时，都会弹出一个选项面板显示“Greetings, Earthling!”。

12. 为什么复杂的 GUI 应该用面向对象的方式来编写？

## 第 14.4 节：其他组件和事件

13. 实现鼠标监听器时使用了哪些类和接口？处理鼠标事件的过程与处理事件有何不同？

14. 修改 `MousePointGUI` 程序的监听器，如果鼠标在框架的上半部分，将框架背景颜色设置为蓝色；如果在下半部分，设置为红色。（提示：在你的解决方案中使用 `label` 的 `getForeground` 和 `setForeground` 方法。）

## 第 14.5 节：2D 图形

15. 绘制 2D 图形时应该扩展哪个类？应该重写哪个方法来绘制？

16. 编写一个面板，在屏幕上绘制时会在自己画出一个红色圆圈。

17. 什么是定时器？在绘制 2D 图形时如何将定时器与面板配合？

18. 修改问题 16 中的红色圆圈面板，使其颜色每隔 1 秒在蓝色和红色之间切换。使用定时器来“动画”面板的颜色变化。

## 练习题

1. 编写一个完整的 Java 程序，创建以下窗口布局。窗口标题为“Good thing I studied!”，窗口大小为 285 x 200 像素。

![](img/aea18896a4bced58de45f29f5a93f7b3_803_0.png)

2. 编写一个完整的 Java 程序，创建以下窗口布局。窗口标题为“Layout question”，窗口大小为 420 x 250 像素。

![](img/aea18896a4bced58de45f29f5a93f7b3_803_1.png)

3. 编写一个 Java 程序，创建以下窗口布局。窗口标题为“Midterm on Thursday!”，窗口大小为 400 x 300 像素。

![](img/aea18896a4bced58de45f29f5a93f7b3_804_0.png)

4. 编写一个 Java 程序，创建以下窗口布局。窗口标题为“I Dig Layout”，窗口大小为 400 x 300 像素。

![](img/aea18896a4bced58de45f29f5a93f7b3_804_1.png)

5. 编写一个 Java 程序，创建以下窗口布局。窗口标题为“Compose Message”，窗口大小为 300 x 200 像素。

![](img/aea18896a4bced58de45f29f5a93f7b3_804_2.png)

6. 编写一个 Java 程序，创建以下窗口布局。窗口标题为“Silly String”，窗口大小为 300 x 100 像素。用户可以在文本字段中输入文本，当按下“Upper case”按钮时，文本变为大大写。当按下“Lower Case”按钮时，文本变为小写。

![](img/aea18896a4bced58de45f29f5a93f7b3_805_0.png)

7. 编写一个 Java 程序，创建以下窗口布局。窗口标题为“MegaCale”，窗口大小为 400 x 300 像素。窗口中有两个文本字段，用户在其中输入二元加法操作的操作数。当按下 `+` 按钮时，两个字段中的文本被视为两个整数并求和，结果的整数作为标签文本的结果显示在屏幕上。

![](img/aea18896a4bced58de45f29f5a93f7b3_805_1.png)

8. 编写一个名为 `EyePanel` 的面板（以及任何其他类，如事件监听器），实现一个绘制两只眼睛的面板，根据光标在上方、中间或下方，眼睛向上、向中间或向下看。三个截图显示了三个位置的眼睛：

![](img/aea18896a4bced58de45f29f5a93f7b3_805_2.png)

9. 编写一个完整的 Java 程序，使所示的移动线条产生动画。

![](img/aea18896a4bced58de45f29f5a93f7b3_805_3.png)

## 编程项目

1. 编写一个 GUI 程序表示一个简单的记事本（Notepad）。支持清除文本的功能、使用 `PrintStream` 保存到文件的功能、使用 `Scanner` 从文件加载的功能，以及一个退出程序的功能。你还可以添加字体大小和背景/前景颜色的支持。你的 GUI 可能如下：

![](img/aea18896a4bced58de45f29f5a93f7b3_806_0.png)

2. 编写一个图形化的吊人游戏（Hangman）。为每个错错误的字母画出一个身体部分。高亮已猜字母。从你创建的列表中选择一个单词。你的 GUI 可能如下：

![](img/aea18896a4bced58de45f29f5a93f7b3_806_1.png)

3. 编写一个绘制图形迷宫的程序，具有以不同方式逃离迷宫的继承层次（例如，`RandomRat` 按随机方向移动，`JumpingRat` 可以跳过墙，`WallHuggingRat` 贴着墙直到找到出口）。考虑在迷宫中加入一只可以吃掉它碰到的老鼠。你的迷宫可能如下：

![](img/aea18896a4bced58de45f29f5a93f7b3_807_0.png)

4. 编写一个绘画程序，允许用户用多种颜色绘制形状和线条。例如：

![](img/aea18896a4bced58de45f29f5a93f7b3_807_1.png)

## 附录 A

## 自测题答案

### 第一章

1. 计算机使用二进制数是因为如果只需要区分状态，构建电子设备更容易。

2. 6 = 110
   - 44 = 101100
   - 72 = 1001000
   - 131 = 1000011

3. 100 = 4
   - 1011 = 11
   - 10110 = 42
   - 1001110 = 78

4. 
   1. 饼干面。
      - 混合干原料。
      - 搅拌奶油和糖。
      - 打入鸡蛋。
      - 拌入干原料。
   2. 烘烤饼干。
      - 设置合适的温度。
      - 设置定时器。
      - 将饼干放入烤箱。
      - 让饼干烘烤。
   3. 添加糖霜。
      - 混合糖霜配料。
      - 将糖霜涂在饼干上。

5. `MyProgram.java` 是程序员编写的源代码文件，`MyProgram.class` 是计算机运行的编译执行类文件。

6. 合法的标识符显示 `println`、`AnnualSalary`、`ABC`、`sum_of_data`、`_average` 和 `B4` 中。

7. 
   ```
   "Quotes"
   Lashes \\
   多么令人‘困惑’！
   ```

### 附录 A 自测题答案

8. 
   ```
   name age height
   Archie 17 5'9"
   Betty 16 5'6"
   Jughead 6'
   ```

9. `Shaq` 是 `7'1`。  
   字符串 `""` 是一个空字符串。

10. 
    ```
    亲爱的"DoubleSlash"杂志：
    你们的出版物困扰了我。这是一个 \ 斜杠还是一个 //// 斜杠？

    诚挚地，
    Susan "Suzy" Smith
    ```

11. 
    ```java
    System.out.println("\" slashes are sometimes seen,\"");
    System.out.println("said Sally. \"I said so.\"");
    System.out.println("\\\\ // //// //////// ///");
    ```

12. 
    ```java
    System.out.println("This is a test of your;");
    System.out.println("knowledge of \"quotes\" used\"");
    System.out.println("in 'string literals.\"");
    System.out.println();
    System.out.println("You're bound to \"get it right\"");
    System.out.println("if you read the section on;");
    System.out.println("\"quotes.\"");
    ```

13. 第 1 行缺少 `class` 关键字。
    - 第 3 行缺少分号。
    - 第 4 行的 `println` 不应该大写。

14. 第 2 行缺少 `void` 关键字。
    - 第 2 行的 `string` 应该大写。
    - 第 4 行缺少一个闭合引号 `"`。
    - 第 5 行缺少一个右括号 `}`。

15. 第 1 行缺少一个左括号 `{`。
    - 第 8–10 行的注释意外注释掉了程序的第 9–10 行。
    - 第 11 行缺少一个右括号 `)`。

### 附录 A 自检题答案

在第二个方法内部  
在第一个方法内部  
在第二个方法内部  
在第一个方法内部  
在第三个方法内部  
在第一个方法内部  
在第二个方法内部  
在第一个方法内部

17. 在第一个方法内部  
在第一个方法内部  
在第二个方法内部  
在第一个方法内部  
在第三个方法内部  
在第二个方法内部  
在第一个方法内部  
在第一个方法内部  
在第二个方法内部  
在第一个方法内部  
在第三个方法内部

18. 在第二个方法内部  
在第一个方法内部  
在第一个方法内部  
在第二个方法内部  
在第一个方法内部  
在第三个方法内部  
在第一个方法内部  
在第二个方法内部  
在第一个方法内部

19. 
    ```
    我方法 1。
    我是方法 1。
    我是方法 2。
    我是方法 3。
    我是方法 1。
    我是方法 1。
    我是方法 2。
    我是方法 1。
    我是方法 2。
    我是方法 3。
    我是方法 1。
    ```

20. 我方法 1。  
    我是方法 1。

    ```
    I method 1.
    I method 2.
    I method 3.
    I method 1.
    I method 2.
    I method 1.
    I method 1.
    I method 2.
    I method 3.
    ```

21. 我方法 1。  
    我是方法 2。  
    我是方法 1。  
    我是方法 2。  
    我是方法 3。  
    我是方法 1。  
    我是方法 1。  
    我是方法 2。

    - 在第 1 行，类名应该是 `LotsOfErrors`（没有空格）。
    - 在第 2 行，`void` 单词应该出现在 `static` 之后。
    - 在第 2 行，`string` 应该是 `String`。
    - 在第 3 行，`System.println` 应该是 `System.out.println`。
    - 在第 3 行，`"Hello, world!"` 应该是 `"Hello, world!"`。
    - 在第 4 行，`message()` 后面应该有一个分号。
    - 在第 7 行，`message` 后面应该有一个 `()`。
    - 在第 8 行，`System.println` 应该是 `System.out.println`。
    - 在第 8 行，`"cannot";` 应该是 `"cannot"`。
    - 在第 9 行，短语 `"errors"` 不能出现在 `String` 内部。
    - 在第 11 行，应该有一个闭合的大括号 `}`。

23. 语法错误：程序无法编译，因为它的类名（`Demonstration`）与其文件名（`Example.java`）不匹配。
    - 程序输出不同：程序无法运行，因为 Java 无法找到 `main` 方法。
    - 程序输出不同：两个打印消息之间将没有空行。
    - 语法错误：程序无法编译，因为 `main` 方法将调用一个不再存在的方法（`displayRule`）。
    - 无影响：程序仍能成功编译并产生相同的输出。
    - 程序输出不同：输出中现在 `"The first rule"` 和 `"of Java Club is,"` 之间将不再有换行。

24. 
    ```java
    public class GiveAdvice {
        public static void main(String[] args) {
            System.out.println("Programs can be easy or");
            System.out.println("difficult to read, depending");
            System.out.println("upon their format.");
            System.out.println();
            System.out.println("Everyone, including yourself,");
            System.out.println("will be happier if you choose;");
            System.out.println("to format your programs.");
        }
    }
    ```

25. 
    ```java
    public class Messy {
        public static void main(String[] args) {
            message();
            System.out.println();
            message();
        }

        public static void message() {
            System.out.println("I really wish that");
            System.out.println("I had formatted my source");
            System.out.println("code correctly!");
        }
    }
    ```

# 第 2 章

1. `-1` 和 `-6875309` 是合法的 `int` 字面量。

   - 8
   - 11
   - 6
   - 4
   - 33
   - -16
   - 6.4
   - 6
   - 30
   - 1
   - 7
   - 5
   - 2
   - 18
   - 3
   - 4
   - 4
   - 15
   - 8
   - 1

### 附录 A 自检题答案

3. 
   - 9.6
   - 2.2
   - 6.0
   - 2.2
   - 8.0
   - 1.25
   - 3.0
   - 3.0
   - 3.0
   - 5.0
   - 6.4
   - 37.0
   - 9.0
   - 8.5
   - 9.6
   - 4.0
   - 4.8

4. 
   - `"2 + 2 34"`
   - `"2 + 3 4"`
   - `"7 + 2 2"`
   - `"2 + 2 7"`
   - `"(2 + 2) 7"`
   - `"hello 34 8"`

5. 
   ```java
   int age;
   String gender;
   double height;
   int weight;
   ```

6. 
   ```java
   String year;
   int numberOfCourses;
   double gpa;
   ```

7. 最后一位：`number % 10`  
   倒数第二位：`(number % 100) / 10` 或 `(number / 10) % 10`  
   倒数第三位：`(number % 1000) / 100` 或 `(number / 100) % 10`

9. 
   ```
   first: 19
   second: 8
   ```
   代码交换了 `first` 和 `second` 的值。

10. 
    ```java
    int first = 8, second = 19;
    first += second;
    second = first;
    ```

### 附录 A 自检题答案

11. 
    - `a: 6`
    - `b: 9`
    - `c: 16`

12. 
    - `15 count -`
    - `10 count + 4`
    - `4 count -`
    - `3 count + 10`

13. 
    ```java
    for (int i = 1; i <= 6; i++) {
        // 在此处输入代码
        System.out.println(i);
    }
    ```

14. 
    ```java
    System.out.println("was ");
    System.out.println("did ");
    System.out.println(");
    System.out.println("in.");
    ```

15. 循环打印的是每三个数字，而不是奇数。第 8 行的 `count = count + 2` 应该移动到循环头部而不是 `count++`。
    - 在第 12 行，变量 `count` 不再定义（它的作用域限于循环）。它应该在循环头部之前声明。
    - 在第 12 行，奇数的打印值太大：应该打印 `count + 2`。
    - 在第 20 行，给常量 `MAX_ODD` 赋值是不合法的。解决此问题的一种方法是写两个方法：一个打印到 `first` 的奇数，另一个打印到 `second`（诚实地说，这种解决方案是冗余的。更好的解决方案涉及参数传递，将在后面的章节中演示）。

16. `42`

17. 结果是：`55`

18. 
    ```
    24 1
    22 2
    19 3
    15 4
    10 5
    ```

19. 
    ```
    +----+

        \     /

         /       \
    ```




```
20. 打印了多少行？

21. 减 5, 4, 3, 2, 1, 爆炸！

22.
1 2 3 4 5 6 7 8 9 10  
2 4 6 8 10 12 14 16 18 20  
3 6 9 12 15 18 21 24 27 30  
4 8 12 16 20 24 28 32 36 40  
5 10 15 20 25 30 35 40 45 50

23.
***
****
******
************
****************
********************

24. *****!*****!*****!  
**********!*****!

25. *****************!  
****************!

26. *!*!*!*!*!*  
*!*!*!*!*!*  
*!*!*!*!*!*  
*!*!*!*!*!*  
*!*!*!*!*!*  
*!*!*!*!*!*
```

# 附录 A 自检题答案

## 27.

```java
public class SlashFigure {
    public static void main(String[] args) {
        for (int line = 1; line <= 6; line++) {
            for (int i = 1; i <= 2 * line - 2; i++) {
                System.out.print("\\");
            }
            for (int i = 1; i <= -4 * line + 26; i++) {
                System.out.print("!");
            }
            for (int i = 1; i <= 2 * line - 2; i++) {
                System.out.print("/");
            }
            System.out.println();
        }
    }
}
```

## 28.

```java
public class SlashFigure2 {

    public static final int SIZE = 4;

    public static void main(String[] args) {

        for (int line = 1; line <= SIZE; line++) {

            for (int i = 1; i <= 2 * line - 2; i++) {

                System.out.print("\\");

            }

            int exclamations = -4 * line + (4 * SIZE + 2);

            for (int i = 1; i <= exclamations; i++) {

                System.out.print("!");

            }

            for (int i = 1; i <= 2 * line - 2; i++) {

                System.out.print("/");

            }

            System.out.println();

        }

    }

}
```

# 第 3 章

## 1.

1 3 5  
1 3 5 7 9 11 13 15  
1 3 5 7 9 11 13 15 17 19 21 23 25

# 附录 A 自检题答案

## 2.

1 2 3 4 5  
1 2 3 4 5 6 7  
1 2 3 4  

`number = 8`

## 3.

三乘以二 = 6  
一乘以三 = 28  
一乘以一 = 42  
三乘以一 = 2  
一乘以八 = 20

## 4.

whom and who like it  
it and him like whom  
whom and him like him  
stu and boo like who  
her and him like who

```java
public static void printStrings(String s, int n) {
    for (int i = 1; i <= n; i++) {
        System.out.print(s);
    }

    System.out.println();
}
```

## 6.

`System.out.println` 是一个重载方法。

## 7.

程序改变了其 `temp` 参数的值，但这不会影响 `main` 方法中的变量 `temp`。错误的输出是：

体温在 C 中是： 0.0

- 1.6
- 2
- 36.0
- 64.0
- 10.0
- 116.0
- 7
- 5
- -5
- 8.0
- 11.0
- 102.0
- 17.0
- 20.0

# 附录 A 自测题答案

- 13.0
- 14.0

## 9.

3 0  
1 2 4  
4 3  
5 2 4  
8 1  
5 9 4

## 10.

```java
public static int min(int n1, int n2, int n3) {
    return Math.min(n1, Math.min(n2, n3));
}
```

## 11.

```java
public static int countQuarters(int cents) {
    return cents % 100 / 25;
}
```

## 12.

- 19
- `"q.e.d."`
- `"ARCTURAN MEGADONKEY"`
- `"E."`
- `"egad"`
- 4
- 1
- 13
- -1
- `"Arcturan Megadonkeys"`
- `"b"`
- `"mega Corp"`

## 13.

`quote.substring(5, 10).toUpperCase()`

`quote.toLowerCase().substring(0, 4) + quote.substring(20, 26)`

## 14.

```text
p1: java.awt.Point[x=20, y=10]

p2: java.awt.Point[x=46, y=4]

p3: java.awt.Point[x=46, y=4]
```

## 15.

- (5, 2)
- (6, -3)
- (5, 2)

## 16.

共有 10 个标记：

- `Hello` : (String)
- `there.` : (String)
- `1+2` : (String)
- `is:` (String)
- `3`: (int, double, String)
- `and`: (String)
- `1.5`: (double, String)
- `squared`: (String)
- `is!`: (String)
- `2.25!`: (String)

## 17.

- 代码将成功运行，变量 `money` 将存储值 34.5。
- 代码将成功运行，变量 `money` 将存储值 6.0。
- 代码将抛出异常并崩溃。
- 代码将抛出异常并崩溃。
- 代码将抛出异常并崩溃。
- 代码将抛出异常并崩溃。
- 代码将成功运行，变量 `money` 将存储值 645.0。

## 18.

```java
scanner console = new Scanner(System.in);
System.out.print("Type an integer: ");
int number = console.nextInt();
System.out.println(number + " times = " + (number * 2));
```

## 19.

```java
scanner console = new Scanner(System.in);
System.out.print("What is your phrase? ");
String phrase = console.nextLine();
System.out.println("How many times should I repeat it? ");
int times = console.nextInt();

for (int i = 1; i <= times; i++) {
    System.out.println(phrase);
}
```

# 补充 3G

- 在第二行，`drawLine` 的调用应该在面板的 `Graphics` 对象上进行，而不是在 `DrawingPanel` 本身上。
- 在第二行，参数的顺序是不正确的。以下是修复后的代码：

```java
DrawingPanel panel = new DrawingPanel(200, 200);
Graphics g = panel.getGraphics();
g.drawLine(50, 86, 20, 35);
```

# 附录 A 自测题答案

## 2.

黑色矩形是第二个绘制的，所以它覆盖了白色的内圆。以下代码修复了这个问题：

```java
DrawingPanel panel = new DrawingPanel(200, 100);
Graphics g = panel.getGraphics();

g.setColor(Color.BLACK);
g.fillRect(10, 10, 50, 50);

g.setColor(Color.WHITE);
g.fillOval(10, 10, 50, 50);
```

## 3.

问题在于 `drawRect` 和 `drawLine` 方法的参数含义不同。在 `drawRect` 中，参数为 `(x, y, width, height)`；在 `drawLine` 中，它们是 `(x1, y1, x2, y2)`。要修复这个问题，应该将传递给 `drawRect` 的第三和第四个参数改为 40 和 40，这样矩形的左下角将位于 `(50, 40)`。以下代码修复了这个问题：

```java
DrawingPanel panel = new DrawingPanel(200, 100);
Graphics g = panel.getGraphics();

g.drawRect(10, 20, 40, 20);
g.drawLine(10, 20, 50, 40);
```

## 4.

`Draw7` 程序绘制了一系列逐渐缩小的黑色圆，每个圆的右边缘和下边缘都接触窗口的右边缘和右下角。它的输出如下：

![](img/aea18896a4bced58de45f29f5a93f7b3_820_0.png)

# 第 4 章

## 1.

`sum` 变量需要在循环外声明。以下代码修复了这个问题：

```java
public static int sumTo(int n) {
    int sum = 0;

    for (int i = 1; i <= n; i++) {
        sum += i;
    }

    return sum;
}
```

## 2.

代码在循环结束后没有打印 `sum`。以下代码修复了这个问题：

```java
public static void printSum(int n) {
    int sum = 0;

    for (int i = 1; i <= n; i++) {
        sum += i;
    }

    System.out.println(sum);
}
```

## 3.

代码缺少在循环内部进行判断。以下代码修复了这个问题：

```java
public static int countFactors(int n) {
    int count = 0;

    for (int i = 1; i <= n; i++) {
        if (n % i == 0) {
            count++;
        }
    }

    return count;
}
```

## 4.

缺少 `return` 语句。

## 5.

变量 `sum` 应该初始化。

## 6.

代码使用了 `if-else` 结构，但条件是互斥的。以下版本修复了 `count` 的问题：

```java
if (times == 1) {
    count++;
} else if (times == 2) {
    count++;
}
```

## 7.

缺少 `count` 变量的定义。

```java
int count = 0;

if (times == 1) {
    count++;
}
```

## 8.

代码错误地打印了偶数。

```java
if (number % 2 == 0) {
    System.out.println("even");
} else {
    System.out.println("odd");
}
```

## 9.

`sum` 变量应该在循环外声明。

```java
int sum = 0;

for (int i = 1; i <= n; i++) {
    if (n % i == 0) {
        sum += i;
    }
}
```

## 10.

缺少 `total` 变量的赋值。

```java
total += times * donation;
```

# 附录 A 自测题答案

```java
System.out.println("You have chosen Red.");

else if (choice.equalsIgnoreCase("g")) {
    System.out.println("You have chosen Green.");
} else if (choice.equalsIgnoreCase("b")) {
    System.out.println("You have chosen Blue.");
} else {
    System.out.println("Unknown color: " + choice);
}
```

## 16.

```java
Scanner console = new Scanner(System.in);

System.out.print("Enter a card: ");

String rank = console.next();
String suit = console.next();

if (rank.equals("2")) {
    rank = "Two";
} else if (rank.equals("3")) {
    rank = "Three";
} else if (rank.equals("4")) {
    rank = "Four";
} else if (rank.equals("5")) {
    rank = "Five";
} else if (rank.equals("6")) {
    rank = "Six";
} else if (rank.equals("7")) {
    rank = "Seven";
} else if (rank.equals("8")) {
    rank = "Eight";
} else if (rank.equals("9")) {
    rank = "Nine";
} else if (rank.equals("10")) {
    rank = "Ten";
} else if (rank.equals("J")) {
    rank = "Jack";
} else if (rank.equals("Q")) {
    rank = "Queen";
} else if (rank.equals("K")) {
    rank = "King";
} else { // rank.equals("A")
    rank = "Ace";
}

if (suit.equals("C")) {
    suit = "Clubs";
} else if (suit.equals("D")) {
    suit = "Diamonds";
} else if (suit.equals("H")) {
    suit = "Hearts";
} else { // suit.equals("S")
    suit = "Spades";
}

System.out.println(rank + " of " + suit);
```

## 17.

表达式的结果为 6.800000000000001，是因为该类型的有限精度导致了舍入误差。

## 18.

表达式 `gpa * 3` 等于 9.600000000000001 是由于舍入误差。修复方法是测试该值是否接近 9.6 而不是完全等于 9.6：

```java
double gpa = 3.2;

if (Math.abs(gpa * 3 - 9.6) < 0.1) {
    System.out.println("You earned enough credits.");
}
```

## 19.

efg  
nopqrs

## 20.

```java
if (Character.isUpperCase(theString.charAt(0))) {
}
```

## 21.

`toLowerCase` 方法不能在 `char` 值上调用，而这正是 `charAt` 方法返回的类型。更好的解决方案是在字符串的字符上调用 `Character.toLowerCase` 方法：

```java
int count = 0;

for (int i = 0; i < s.length(); i++) {
    if (Character.toLowerCase(s.charAt(i)) == 'e') {
        count++;
    }
}
```

另一种解决方案是在循环之前将整个字符串转换为小写：

```java
s = s.toLowerCase();

count = 0;

for (int i = 0; i < s.length(); i++) {
```



```java
if (s.charAt(i) == 'e') {
    count++;
}
}
```

- 22. 下表达式将产生预期的结果：

```java
String name = "Marla Singer";
int space = name.indexOf(" ");
String lastName = name.substring(space + 1);
String firstInitial = name.substring(0, 1);
String lastNameInitial = lastName + " " + firstInitial + ".";
System.out.println(lastNameFirstInitial);
```

或者，你可以使用这个更短的版本：

```java
String name = "Marla Singer";
System.out.println(name.substring(name.indexOf(" ") + 1) + " " + name.charAt(0) + " ");
```

- 23. `String` 存储在变量`str`中：

```java
int count = 0;

for (int i = 0; i < str.length(); i++) {
    if (Character.toLowerCase(str.charAt(i)) >= 'n') {
        count++;
    }
}

System.out.println(count + " letters come after n.");
```

- 24. `public static void printTriangleType(int s1, int s2, int s3)`：

```java
if (s1 == s2 && s2 == s3) {
    System.out.println("equilateral");
} else if (s1 == s2 || s1 == s3 || s2 == s3) {
    System.out.println("isosceles");
} else {
    System.out.println("scalene");
}
}
```

无效值是指边长为负数，或者任何一条边大于另外两条边的长度之和，因为这不能构成三角形。`printTriangle`方法的前提条件是边长构成有效的三角形。

- 25. 该方法的前提条件是参数值在 0 和 100 之间。

- 26. 当`n3`是三个数中的最小值时代码会失败：例如，参数为`(4, 7, 2)`，代码应该返回 4 却返回了 2。该方法可以写为：

```java
public static int medianOf3(int n1, int n2, int n3) {
    if (n1 < n2 && n1 < n3) {
        if (n2 < n3) {
            return n2;
        } else {
            return n3;
        }
    } else if (n2 < n1 && n2 < n3) {
        if (n1 < n3) {
            return n1;
        } else {
            return n3;
        }
    } else if (n3 < n1 && n3 < n2) {
        if (n1 < n2) {
            return n1;
        } else {
            return n2;
        }
    }
}
```

或者以下更短的版本：

```java
public static int medianOf3(int n1, int n2, int n3) {
    return Math.max(Math.min(n1, n2), Math.min(n2, n3));
}
```

- 27. 如果`a`、`b`、`c`无效，则抛出异常：

```java
public static void quadratic(int a, int b, int c) {
    double determinant = b * b - 4 * c;

    if (a == 0) {
        throw new IllegalArgumentException("Invalid value of a");
    }

    if (determinant < 0) {
        throw new IllegalArgumentException("Invalid determinant");
    }
}
```

无效值是`a = 0`（会导致分母为 0），或者`b^2 - 4ac < 0`，因为此时没有平方根。

- 3. 方法调用：

```java
myst(1);
myst(6);
myst(19);
myst(39);
myst(74);
```

| 输入 | 输出 |
| :--- | :--- |
| `mystery(1)` | 0 |
| `mystery(6)` | 2 |
| `mystery(19)` | 4 |
| `mystery(39)` | 5 |
| `mystery(74)` | 6 |

- 4. 方法调用：

```java
myst(19);
myst(42);
myst(48);
myst(40);
myst(64);
```

| 输入 | 输出 |
| :--- | :--- |
| `mystery(19)` | 0 |
| `mystery(42)` | 1 |
| `mystery(48)` | 4 |
| `mystery(40)` | 3 |
| `mystery(64)` | 6 |

- 5.

```java
int SENTINEL = -1;
System.out.print("Type a number (or " + SENTINEL + " to stop): ");
Scanner console = new Scanner(System.in);
int input = console.nextInt();
int min = input;
int max = input;
```

```java
int i = 1;

while (i <= 2) {
    int j = 1;

    while (j <= 3) {
        int k = 1;

        while (k <= 4) {
            System.out.print("*");
            k++;
        }

        System.out.print("!");
        j++;
    }

    System.out.println();
    i++;
}

int number = 4;
int count = 1;

while (count <= number) {
    System.out.println(number);
    number = number / 2;
    count++;
}
```

```java
while (input != SENTINEL) {
    if (input < min) {
        min = input;
    } else if (input > max) {
        max = input;
    }

    input = console.nextInt();
}
```

```java
if (min != SENTINEL) {
    System.out.println("Maximum was " + max);
    System.out.println("Minimum was " + min);
}
```

```java
6. public static int zeroDigits(int number) {
    int count = 0;

    do {
        if (number % 10 == 0) {
            count++;
        }

        number = number / 10;
    } while (number > 0);

    return count;
}
```

```java
7. Scanner console = new Scanner(System.in);

System.out.print("Type a number: ");
int number = console.nextInt();
String textNumber = String.valueOf(number);
```

```java
// print odd digits
for (int i = 0; i < textNumber.length(); i++) {
    int digit = Character.getNumericValue(
        textNumber.charAt(i));

    if (digit % 2 == 1) {
        System.out.print(digit);
    }
}
```

```java
// print even digits
for (int i = 0; i < textNumber.length(); i++) {
    int digit = Character.getNumericValue(
        textNumber.charAt(i));
}
```

## 附录 A 自测题答案

```java
if (digit % 2 == 0) {
    System.out.print(digit);
}
```

- 8.
  - a: 0 到 99（包含）
  - b: 50 到 69（包含）
  - c: 0 到 69（包含）
  - d: -20 到 79（包含）

- 9.

```java
Random rand = new Random();
int num = rand.nextInt(11);
```

- 10.

```java
Random rand = new Random();
int num = rand.nextInt(25) * 2 + 51;
```

- 11.
  - `true`
  - `true`
  - `false`
  - `true`
  - `true`
  - `false`
  - `false`
  - `true`
  - `true`
  - `true`
  - `false`

```java
12. public static boolean isVowel(char c) {
    c = Character.toLowerCase(c); // 不区分大小写

    return c == 'a' || c == 'e' || c == 'i' ||
        c == 'o' || c == 'u';
}
```

```java
or:

public static boolean isVowel(char c) {
    String vowels = "aeiouAEIOU";
    return vowels.indexOf(c) >= 0;
}
```

- 13. 在这段代码中，布尔标志位没有被正确使用，因为如果代码找到了数字的因数，`prime`将设置为`false`，但在循环的下一次迭代中，如果下一个数字不是因数，`prime`将再次重置为`true`。以下代码解决了这个问题：

```java
public static boolean isPrime(int n) {
    boolean prime = true;

    for (int i = 2; i < n; i++) {
        if (n % i == 0) {
            prime = false;
        }
    }

    return prime;
}
```

- 14. 在这段代码中，布尔标志位没有被正确使用，因为如果代码找到了字符，`found`将设置为`true`，但在循环的下一次迭代中，如果下一个字符不是`ch`，`found`将再次重置为`false`。以下代码解决了这个问题：

```java
public static boolean contains(String str, char ch) {
    boolean found = false;

    for (int i = 0; i < str.length(); i++) {
        if (str.charAt(i) == ch) {
            found = true;
        }
    }

    return found;
}
```

- 15. `public static boolean startEndSame(String str)`：

```java
return str.charAt(0) == str.charAt(str.length() - 1);
```

- 16. `public static boolean hasPennies(int cents)`：

```java
return cents % 5 == 0;
```

- 17. 方法调用 | 返回的值

| 方法调用 | 返回的值 |
| :--- | :--- |
| `mystery(3, 3)` | 3 |
| `mystery(5, 3)` | 1 |
| `mystery(2, 6)` | 2 |
| `mystery(12, 18)` | 6 |
| `mystery(30, 75)` | 15 |

- 18. 代码应该提示用户输入有效的整数作为年龄，以及输入有效的实点数作为 GPA。如果用户输入了类型错误的标记（token），应该消耗掉该行输入并重新提示用户。

以下代码实现了修正后的行为：

```java
Scanner console = new Scanner(System.in);

System.out.print("Type your age: ");

while (!console.hasNextInt()) {
    console.nextLine(); // 丢弃错误的标记
    System.out.print("Type your age: ");
}

int age = console.nextInt();

System.out.print("Type your GPA: ");

while (!console.hasNextDouble()) {
    console.nextLine(); // 丢弃错误的标记
    System.out.print("Type your GPA: ");
}

double gpa = console.nextDouble();
```

- 19.
  - 为我输入点东西吧！Jane
  - 你的名字是 Jane
  - 为我输入点东西吧！56
  - 你的 IQ 是 56
  - 为我输入点东西吧！56.2
  - 你的名字是 56.2

- 20.

```java
Scanner console = new Scanner(System.in);

System.out.print("Type a number: ");

if (console.hasNextInt()) {
    int value = console.nextInt();
    System.out.println("You typed the integer " + value);
} else if (console.hasNextDouble()) {
    double value = console.nextDouble();
    System.out.println("You typed the real number " + value);
}
```

- 21.

```java
String prompt = "Please enter a number: ";
Scanner console = new Scanner(System.in);

int num1 = get(console, prompt);
int num2 = get(console, prompt);
int num3 = get(console, prompt);

double average = (num1 + num2 + num3) / 3.0;

System.out.println("Average: " + average);
```



### 练习答案

- 22. 执行`体` 10 次。

输出为：

```text
1 11 21 31 41 51 61 71 81 91
```

- 无限循环。

输出为：

```text
count down: 10
count down: 9...
```

- 无限循环。

输出为：

```text
250
250
```

- 执行 2 次。

输出为：

```text
10
50
```

- 执行 5 次。

输出为：

```text
16
```

- 执行 7 次。

输出为：

```text
10
0
```

- 23.

```java
Scanner console = new Scanner(System.in);
String response;
do {
  System.out.println("She seashells by the");
  response = console.nextLine();
} while (response.equals("y"));
```

- 24.

```java
Scanner console = new Scanner(System.in);
Random rand = new Random();
int num;
do {
    num = rand.nextInt();
} while (num < 1000);
```

- 25.

```java
int SENTEL = -1;
Scanner console = new Scanner(System.in);
System.out.print("Maximum was ");
if (console.hasNextInt()) {
    System.out.print("Type a number or ");
    while (!console.hasNextInt()) {
        console.nextLine();
    }
}
System.out.println("Do you want to hear?");
```

# 附录 A 自检题答案

### 11.

```java
public static void printEntireFile(throws FileNotFoundException) {
    Scanner console = new Scanner(System.in);
    System.out.print("Type a file name: ");
    String filename = console.nextLine();
    Scanner input = new Scanner(new File(filename));

    while (input.hasNextLine()) {
        System.out.println(input.nextLine());
    }
}
```

### 12.

`PrintStream` 对象用于写入外部文件。它具有`print`和`println`等方法。

### 13.

```java
PrintStream out = new PrintStream(new File("message.txt"));

out.println("Testing,");
out.println("1, 2, 3.");
out.println();
out.println("This is my output file file.");
```

### 14.

```java
public static String getFileName() {
    Scanner console = new Scanner(System.in);
    String filename = null;

    do {
        System.out.print("Type a file name: ");
        filename = console.nextLine();
    } while (new File(filename).exists());

    return filename;
}
```

### 15.

直到文件名有效为止重新提示。

```java
public static void printEntireFile2(throws FileNotFoundException) {
    String filename = getFileName();
    Scanner input = new Scanner(new File(filename));

    while (input.hasNextLine()) {
        System.out.println(input.nextLine());
    }
}
```

# 附录 A 自习题答案

## 第 7 章

### 1.

第一个元素：`numbers[0]`

最后一个元素：`numbers[9]` 或 `numbers[numbers.length] - 1`

### 2.

```java
int[] data = new int[5];

data[0] = 27;
data[1] = 51;
data[2] = 33;
data[3] = -1;
data[4] = 101;
```

### 3.

```java
int[] odds = new int[22];

for (int i = 0; i < 22; i++) {
   odds[i] = i * 2 - 5;
}
```

### 4.

`{0, 4, 11, 0, 44, 0, 0, 2};`

### 5.

打印数组并比较它们的代码无法正常工作。数组不能直接通过`println`打印，也不能直接使用`==`等关系运算符进行比较。这些操作可以通过循环遍历每个数组的元素并逐个打印或比较来正确完成。

### 6.

`int[] data = {7, -1, 13, 24, 6};`

### 7.

为了将这些大整数存储在小数组中，在将其放入`Tally`数组之前，先从每个数字减去 100,000,000。这将导致值 100,000,000 存储在元素 0 中，100,000,001 存储在元素 1 中，以此类推。下行代码：

```java
count[next]++;
```

应该更改为：

```java
count[next = 100000000];
```

### 8.

```java
public static int max(int[] data) {
   int max = data[0];

   for (int i = 1; i < data.length; i++) {
      if (data[i] > max) {
         max = data[i];
      }
   }

   return max;
}
```

### 9.

```java
public static double average(int[] a) {
   double mean = 0.0;

   for (int i = 0; i < a.length; i++) {
      mean += a[i];
   }

   return mean / a.length;
}
```

### 10.

数组遍历是对数组的每个元素进行顺序处理。可以通过这种方式解决的问题包括打印数组、比较两个数组是否相等，以及在数组中搜索给定值。

### 11.

```java
for (int i = 0; i < data.length; i++) {
    System.out.println("Element " + i + ": " + data[i]);
}
```

### 12.

```java
public static void printBackwards(int[] list) {
    if (list.length == 0) {
        System.out.println("[]");
    } else {
        System.out.print("[" + list.length - 1);

        for (int i = list.length - 2; i >= 0; i--) {
            System.out.print(", " + list[i]);
        }

        System.out.println("]");
    }
}
```

### 13.

要让这些方法处理字符串数组，你必须将`int[]`改为`String[]`，并替换所有出现`int`单词的地方为`String`。你还必须将任何使用`==`的比较更改为使用`equals`方法的比较。

### 14.

```java
public static boolean allLess(int[] list1, int[] list2) {
    if (list1.length != list2.length) {
        return false;
    }

    for (int i = 0; i < list1.length; i++) {
        if (list1[i] >= list2[i]) {
            return false;
        }
    }

    return true;
}
```

### 15.

交换方法之所以有效，是因为与整数不同，数组是对象并使用引用语义的。这意味着对数组的修改将被调用者看到。

### 16.

```java
public void swapPairs(int[] list) {
  for (int i = 0; i < list.length - 1; i += 2) {
    swap(list, i, i + 1);
  }
}
```

### 17.

`{20, 30, 40, 50, 60, 70, 80, 90, 100};`

### 18.

`{10, 10, 10, 10, 10, 10, 10, 10, 10, 10};`

### 19.

`{26, 14};`

### 20.

`{13, 24};`

### 21.

`{7, 8};`

### 22.

```java
public static double averageLength(String[] strings) {
  double sum = 0;

  for (int i = 0; i < strings.length; i++) {
    sum += strings[i].length();
  }

  return sum / strings.length;
}
```

### 23.

```java
public boolean isPalindrome(String[] array) {
  for (int i = 0; i < array.length / 2; i++) {
    if (!array[i].equals(array[array.length - 1 - i])) {
      return false;
    }
  }

  return true;
}
```

### 24.

```java
int[][] table = new int[5];
```

### 25.

```java
int[][] table = new int[5];
```

### 26.

```java
for (int i = 0; i < 5; i++) {
    table[i][i] = i;
}
```

### 27.

```java
int[][] jagged = new int[5];
```

### 28.

```java
for (int i = 0; i < 5; i++) {
    jagged[i] = i;
}
```

# 过程化编程与面向对象编程

过程化编程将程序视为一系列要执行的命令。面向对象编程将程序视为一组相互作用的对象，每个对象都维护自己的数据。类是对象的蓝图，规定了它将拥有什么数据和行为以及如何构建它。

# 附录 A 自我检查题答案

### 11.

字段`x`和`y`不应该在它们前面重新声明类型。这个错误会导致字段遮蔽（shadowing）。以下是修正后的行：

```java
x = initialX;
y = initialY;
```

### 12.

`Name`对象表示一个如`"John Q. Public"`这样的名字。

```java
public class Name {
    String firstName;
    char middleInitial;
    String lastName;

    // 使用给定的值初始化一个新的 Name。
    public Name(String initialFirst, char initialMiddle, String initialLast) {
        firstName = initialFirst;
        middleInitial = initialMiddle;
        lastName = initialLast;
    }

    // 正常顺序的名字，如 "John Q. Public"。
    public String getNormalOrder() {
        return firstName + " " + middleInitial + " " + lastName;
    }

    // 倒序顺序的名字，如 "Public, John Q."
    public String getReverseOrder() {
        return lastName + ", " + firstName + " " + middleInitial + ".";
    }
}
```

### 13.

抽象是指在抽象层面上关注问题而不必担心细微细节的能力。对象通过提供更强大的数据片段来提供抽象，这些数据具有复杂的行为，而无需直接管理和操作数据。

### 14.

声明为`public`的项可以从任何类中查看和使用。声明为`private`的项只能在自己的类内部查看和使用。“对象”字段应该声明为`private`以提供封装，这样外部代码就无法对字段值进行意外的直接修改。

### 15.

要访问私有字段，请创建返回它们值的访问器方法（accessor methods）。为了让`getName`方法访问对象的`name`字段：

### 16.

```java
// 将此 Point 的 x 坐标设置为给定的值。
public void setX(int newX) {
    x = newX;
}

// 将此 Point 的 y 坐标设置为给定的值。
public void setY(int newY) {
    y = newY;
}
```

### 17.

`Name`对象表示一个如`"John Q. Public"`这样的名字。

```java
public class Name {
    private String firstName;
    private char middleInitial;
    private String lastName;

    // 使用给定的值初始化一个新的 Name。
    public Name(String initialFirst, char initialMiddle, String initialLast) {
        firstName = initialFirst;
        middleInitial = initialMiddle;
        lastName = initialLast;
    }

    // 返回人的名字。
    public String getFirstName() {
        return firstName;
    }

    // 返回人的中间名字母缩写。
    public char getMiddleInitial() {
        return middleInitial;
    }

    // 返回人的姓。
    public String getLastName() {
        return lastName;
    }
}
```

### 18.

要使你的类的`==`运算符可以打印，请在类中定义一个`toString`方法。

```java
// 正常顺序的名字，如 "John Q. Public"。
public String getNormalOrder() {
    return firstName + " " + middleInitial + ". " + lastName;
}

// 倒序顺序的名字，如 "Public, John Q"。
public String getReverseOrder() {
    return lastName + ", " + firstName + " " + middleInitial + "";
}
```

### 19.

`==`运算符不适用于对象，因为它仅仅比较引用，以检查它们是否指向完全相同的对象。如果你想让你的对象被正确比较，请在类中定义一个`equals`方法，并在客户端代码中使用`equals`代替`==`。

### 20.

返回此点的字符串表示形式。

```java
public String toString() {
    return "java.awt.Point[x=" + x + ", y=" + y + "]";
}
```

### 21.

返回正常顺序的名字，如`"John Q. Public"`。

```java
public String toString() {
    return firstName + " " + middleInitial + ". " + lastName;
}
```

### 22.

或：返回此`Name`的字符串表示形式。

```java
public String toString() {
    return getNormalOrder();
}

// 如果 o 指向一个与此 Name 对象具有相同名字/中间中间名的 Name 对象，则返回 true。
```



```java
public boolean equals(Object o) {
    if (o instanceof Name) {
        Name other = (Name) o;
        return firstName.equals(other.firstName) &&
               middleInitial == other.middleInitial &&
               lastName == other.lastName;
    } else { // 不是一个 Name 对象
        return false;
    }
}
```

23. // 构建一个与给定 `Point` 相同 x 和 y 坐标的 `Point` 对象。

```java
public Point(Point p) {
    this.x = p.x;
    this.y = p.y;
}

// 构建一个与给定 Point 相同 x 和 y 坐标的 Point 对象。
public Point(int x, int y) { // 调用 (int, int) 构造函数
    this(x, y);
}
```

24. // 将第一个名字设置为给定的值。

```java
public void setFirstName(String firstName) {
    firstName = firstName;
}

// 将姓设置为给定的值。
public void setLastName(String lastName) {
    lastName = lastName;
}

// 将中间名缩写设置为给定的值。
public void setMiddleInitial(char middleInitial) {
    middleInitial = middleInitial;
}
```

25. 不变对象（immutable object）是指在创建后状态无法被改变的对象。使用不可变对象的好处是它们是“只读”的，并且可以更容易地强制不变性。

26. `Name` 类不是不可变的，因为它有修改器方法。之前的 `Name` 类是封装的，但没有修改器方法。

27. 封装允许你更改类的内部实现而不改变其外部视图。只要外部视图（方法行为）保持一致，对象就是不可变的。

28. // 返回此此 的字符串表示形式。

```java
public String toString() {
    return name + " " + height + ", weights=" + weight + " ";
}

// 如果 o 指向一个与此一个具有相同名字、高度和重量的 Participant 对象，则返回 true。
public boolean equals(Object o) {
    if (o instanceof Participant) {
        Participant other = (Participant) o;
        return name.equals(other.name) &&
               height == other.height &&
               weight == other.weight;
    }
    return false;
}
```

29. 内聚性（cohesion）是类内容紧密程度的概念。当一个类的每个字段都存储与对象相关的状态，且每个方法都以某种方式与该状态交互以产生有用行为时，你可以判断该类是内聚的。

30. 我们没有将 I/O 代码放在 `Stock` 类中，因为这样做会强制客户端使用那些特定的 I/O 信息。通过将 I/O 代码留在外部，使其与客户端保持独立。

31. // 返回 `Stock` 的符号。

```java
public String getSymbol() {
    return symbol;
}

// 返回 Stock 的总股份数。
public int getTotalShares() {
    return totalShares;
}
```

# 第 9 章

```java
// 返回所有股份的总成本。
public double getTotalCost() {
    return totalCost;
}
```

1. 代码复用是指编写一次代码并在不同的程序和语文中多次使用的实践。继承（inheritance）对于代码复用非常有用，因为它允许你编写一个捕捉通用代码的类，并扩展该类以添加更多功能和行为。

2. 方法重载（overloading）是指在同一个类中创建两个名称相同但参数不同的方法。方法重写（overriding）是指在子类中为继承的方法创建一个新版本，具有相同的参数但有新的行为来替换旧行为。

3. 以下语句是合法的：

- `Vehicle v = new Car();`
- `Vehicle v = new SUV();`
- `Car c = new SUV();`
- `SUV s = new SUV();`

4. 表示法务秘书的类：

```java
public class LegalSecretary extends Employee {
    public void fileLegalBriefs() {
        System.out.println("我可以写一整天代码！");
    }

    public void showSalary() {
        System.out.println("我的薪水是 45000 元。");
    }
}
```

5. B 2

A

B 1

6. D 2

C

C 1

# 附录 A 自检题答案

A 2

A

A 1

A 2

C

C 1

+ 6. 笛子

`shoe 1`

`flute 2`

`flute`

`blue 1`

`flute 2`

`moo`

`moo 1`

`moo 2`

`moo`

`blue 1`

`moo 2`

+ 7. `moo 2`

`blue 1`

`moo`

`moo 2`

`moo 1`

`moo`

`flute 2`

`shoe 1`

`flute`

`flute 2`

`blue 1`

`flute`

+ 8. `squid`

`creature 1`

`tentacles`

`BIG!`

`spout`

`creature 2`

# 附录 A 自检题答案

`ocean-dwelling`

`creature 1`

`creature 2`

`ocean-dwelling`

`warm-blooded`

`creature 2`

+ 9. `creature 2`

`ocean-dwelling`

`creature 1`

`tentacles`

`squid`

`creature 1`

`creature 2`

`ocean-dwelling`

`warm-blooded`

`creature 2`

`BIG!`

`spout`

+ 10. `this` 关键字指向当前对象，而 `super` 关键字指向当前类的父类。当你调用已重写的父类方法或构造函数时，使用 `super` 关键字；当访问对象的其他字段、构造函数和方法时，使用 `this` 关键字。

+ 11. `UndergraduateStudent` 可以调用 `setAge` 方法，但不能直接从 `Student` 访问 `name` 或 `age` 字段。

```java
public UndergraduateStudent(String name) {
    super(name, 18);
    year = 0;
}
```

```java
public void setAge(int age) {
    super.setAge(age);
    year++;
}
```

```java
// 在原点 (0, 0) 构造一个 MeteredPoint。
public MeteredPoint() {
    super(0, 0);
    totalDistance = 0.0;
}
```

# 附录 A 自检题答案

```java
// 在原点 (0, 0) 构造一个 MeteredPoint。
public MeteredPoint() {
    this(0, 0);
}
```

+ 15. “is-a”（是一个...）关系是指子类关系，例如通过继承创建的关系。“has-a”（拥有有一个...）关系是指一个对象以字段的形式包含对另一个对象的引用。

+ 16. 让 `Square` 继承 `Rectangle` 是一个糟糕的设计，因为 `Square` 并不能替代 `Rectangle`。如果客户端认为 `Square` 是 `Rectangle` 并对其调用 `setWidth` 或 `setHeight`，将会产生意之外的结果。

+ 17. 为 52 张扑克牌每张牌单独创建一个类不是良好的设计，因为这将导致大量之间没有显著差异的代码文件。更好的设计是拥有一个 `Card` 类，并包含点数（rank）和花色（suit）字段。

+ 18. 我们将 `DividendStock` 设计为 `Stock` 的独立子类主要有两个主要原因。首先，并不是所有股票都支付股息，让每个 `Stock` 对象都拥有 `dividends` 字段和 `payDividend` 方法没有意义。其次，`Stock` 的代码已经运行正常，因此我们不想进行不必要的修改。将 `DividendStock` 作为一个独立的类构成了一种加性的且非侵入性的更改。

+ 19. 扩展一个类会导致你的类继承该类的所有方法和数据。实现一个接口则强制你编写自己的代码来实现该接口中所有的方法。

+ 20. 类 `c` 的代码必须包含方法 `m1` 和 `m2` 的实现才能正确编译，因为 `c` 声称实现了 `I` 接口。

+ 21. 该接口是错误的，因为接口不能声明字段或为方法编写方法体。以下是正确的接口：

```java
import java.awt.*;

// 代表具有可以获取的颜的项目。
public interface Colored {
    public Color getColor();
}
```

# 附录 A 自检题答案

22. // 代表一个带有颜色的点。

```java
import java.awt.*;

public class ColoredPoint extends Point implements Colored {
    private Color color;

    // 使用给定的坐标和颜色构造一个新的有色点。
    public ColoredPoint(int x, int y, Color color) {
        super(x, y);
        this.color = color;
    }

    // 返回此点的颜色。
    public Color getColor() {
        return color;
    }
}
```

23. // 形状类的通用接口。

```java
public interface Shape {
    public double getArea();
    public double getPerimeter();
    public int getSideCount();
}
```

以下是 `Circle`、`Rectangle` 和 `Triangle` 类中对应方法的实现：

```java
// 返回圆的边数（0）。
public int getSideCount() {
    return 0;
}
```

```java
// 返回矩形的边数（4）。
public int getSideCount() {
    return 4;
}
```

```java
// 返回三角形的边数（3）。
public int getSideCount() {
    return 3;
}
```

# 附录 A 自检

24. 抽象类旨在仅用作继承的父类。它与普通类的相似之处在于，它可以拥有字段、方法、构造函数等。它与普通类的不同之处仅在于它可以拥有有抽象方法，抽象方法类似于接口的方法，但它们只有方法头没有方法体。它与普通类的不同之处在于它不能被实例化。

25. 一个良好的设计是有一个抽象父类，包含 `name`、`director` 和 `date` 等数据。`Movie` 的子类将代表特定的类型，如 `Drama`、`comedy` 和 `Documentary`。每个子类存储特定的数据和行为。

+ 1. `ArrayList` 是一个存储对象的结构。每个元素与从 0 开始的索引关联。如果你不知道需要多少个元素，或者计划从列表中间添加或删除元素，应该使用 `ArrayList` 而不是数组。

```java
ArrayList<String> list = new ArrayList<String>();
list.add("It");
list.add("was");
list.add("a");
list.add("stormy");
```

`list` 的类型为 `ArrayList<String>`，大小为 5。

+ 3.

```java
list.add(3, "dark");
list.add(4, "and");
```

+ 4.

```java
list.set(1, "IS");
```

```java
for (int i = 0; i < list.size(); i++) {
    if (list.get(i).indexOf("a") >= 0) {
        list.remove(i); // 这样会检查新元素
    }
}
```

```java
ArrayList<Integer> numbers = new ArrayList<Integer>();
for (int i = 0; i < 10; i++) {
    numbers.add(i);
}
```

# 附录 A 自检题答案

```java
public static int maxLength(ArrayList<String> list) {
    int max = 0;
    for (int i = 0; i < list.size(); i++) {
        String s = list.get(i);
        if (s.length() > max) {
            max = s.length();
        }
    }
    return max;
}
```

```java
System.out.println(list.contains("IS"));
```

```java
System.out.println(list.indexOf("stormy"));
System.out.println(list.indexOf("dark"));
```

```java
for (String s : list) {
    System.out.println(s.toUpperCase());
}
```

11. 代码会抛出 `ConcurrentModificationException`，因为在 for-each 循环中修改 `ArrayList` 的元素是非合法的。

12. 代码无法编译，因为基本类型不能指定为泛型。解决方案是使用包装类 `Integer` 而不是 `int`。将声明 `ArrayList` 的行改为：

```java
ArrayList<Integer> numbers = new ArrayList<>();
```

13. 包装类的主要目的是作为基本值和对象之间的桥梁。`Integer` 是持有 `int` 值的对象。包装类允许基本值存储在集合中。

14. 要对 `ArrayList` 进行排序，对其调用 `Collections.sort` 方法。例如，如果你的 `ArrayList` 存储在名为 `list` 的变量中：

```java
Collections.sort(list);
```

要使此生效，存储在列表的对象类型必须实现 `Comparable`。

15. 自然排序是类对象的顺序，其中“较小”的对象在“较大”的对象之前，这由类的 `compare` 过程决定。要给出自己的自然排序，请声明实现 `Comparable` 接口，并通过编写适当的 `compare` 方法为其定义比较函数。

```java
n1.compareTo(n2) > 0
n3.compareTo(n1) == 0
n2.compareTo(n1) < 0
```

# 附录 A 自检题答案

```java
s1.compareTo(s2) < 0
s3.compareTo(s1) > 0
s2.compareTo(s2) == 0
```

```java
Scanner console = new Scanner(System.in);
System.out.print("Type a name: ");
String name1 = console.nextLine();
System.out.print("Type a name: ");
String name2 = console.nextLine();

if (name1.compareTo(name2) < 0) {
    System.out.println(name1 + " goes before " + name2);
} else if (name1.compareTo(name2) > 0) {
    System.out.println(name1 + " goes after " + name2);
} else {
    System.out.println(name1 + " is the same as " + name2);
}
```



```java
Scanner console = new Scanner(System.in);
System.out.print("Type a message to sort: ");
String message = console.nextLine();

ArrayList<String> words = new ArrayList<String>();
Scanner lineScan = new Scanner(message);
while (lineScan.hasNext()) {
    words.add(lineScan.next());
}

System.out.print("Your message sorted: ");
Collections.sort(words);
for (String word : words) {
    System.out.print(word + " ");
}
System.out.println(); // 结束输出行
```

# 第 11 章

1. 当你计划在列表的前部或底部删除大量值时，或者当你计划对列表进行多次过滤遍历并移除某些元素时，应该使用`LinkedList`。

2. 所示代码在`ArrayList`中性能会更好，因为它多次使用列表中间的索引调用`get`方法。对于`LinkedList`来说，这是一个缓慢的操作。

# 附录 A 自测题答案

3. 迭代器是一个表示列表中位置的对象，它能够让你查看或修改该位置上的元素。迭代器通常用于链表，因为它们保留了在列表中的位置，所以你不需要多次调用`get`、`add`或`remove`等开销较大的列表方法。

```java
public static int countDuplicates(LinkedList<Integer> list) {
    int count = 0;
    Iterator<Integer> i = list.iterator();
    int prev = i.next();
    while (i.hasNext()) {
        int next = i.next();
        if (prev == next) {
            count++;
        }
        prev = next;
    }
    return count;
}
```

```java
public static void insertInOrder(LinkedList<String> list,
    String value) {
    int index = 0;
    Iterator<String> i = list.iterator();
    String next = i.next();
    // 进到合适的索引
    while (i.hasNext() && next.compareTo(value) < 0) {
        next = i.next();
        index++;
    }
    list.add(index, value);
}
```

```java
public static void removeAll(LinkedList<Integer> list,
    int value) {
    Iterator<Integer> i = list.iterator();
    while (i.hasNext()) {
        if (i.next() == value) {
            i.remove();
        }
    }
}
```

```java
public static void wrapHalf(LinkedList<Integer> list) {
    int halfSize = (list.size() + 1) / 2;
    for (int i = 0; i < halfSize; i++) {
        // 循环一个元素
        int element = list.remove(list.size() - 1);
        list.add(0, element);
    }
}
```

8. 抽象数据类型定义了集合可以包含的数据类型以及它对该数据可以的操作。链表实现了`List`抽象数据类型。

9. `countDuplicates`代码与第 4 题提供的代码相同，但方法头应更改为：
`public static int countDuplicates(List<Integer> list)`

10. 如果你想避免重复或想要快速搜索集合，应该使用`Set`而不是`List`。

11. 当你希望保持数据按自然顺序排序时，应该使用`TreeSet`。当使用非`Comparable`类型或不在乎顺序时，应该使用`HashSet`以获得最快的搜索速度。

12. 你可以使用迭代器检查`Set`的每一个元素。

13. `[32, 90, 9, 182, 29, 12]`

14. `[79, 8, 132, 50, 98, 12, 86]`

15. `[94, 4, 11, 84, 42, 12, 247]`

16. 要执行并集，使用`add`方法将一个集合的内容添加到另一个集合中。要执行交集，使用`retainAll`方法移除两个集合不共有的元素。

```java
Map<String, Integer> ageMap = new TreeMap<String, Integer>();
ageMap.put("Stuart", 85);
ageMap.put("Marty", 12);
ageMap.put("Amanda", 25);
```

18. 你可以通过调用`keyset`方法并对`keyset`进行迭代或增强循环来检查`Map`的每一个键。你可以通过调用`values`方法并对该值集合进行迭代或增强循环来检查`Map`的每一个值，或者通过使用键来查找每个关联的值。

19. `{17=Steve, 34=Louann, 15=Moshe, 2350=Orlando, 7=Ed, 5=Moshe, 27=Donald}`

20. `{79=Seventy-nine, 8=Ocho, 132=OneTwoThree, 50=Fifty, 98=Ninety-eight, 86=Eighty-six}`

21. 下述方法实现了`wordcount`程序中的新行为：

```java
public static void reverseMap(
    Map<String, Integer> wordCountMap) {
    Map<Integer, String> reverseMap =
        new TreeMap<Integer, String>();
    // 反转原始 map
    for (String word : wordCountMap.keySet()) {
        int count = wordCountMap.get(word);
        if (count > 0) {
            reverseMap.put(count, word);
        }
    }
    // 按计数排序打印单词
    for (int count : reverseMap.keySet()) {
    }
}
```

# 第 12 章

1. 递归是一种用算法自身来表达算法的技术。递归方法与普通方法的区别在于，它包含一次或多次对自身的调用。

2. 基准情况（`base case`）是递归方法不需要通过递归调用即可解决问题的情况。递归情况（`recursive case`）是递归方法调用自身的情况。递归方法需要两种情况，因为递归情况会被不断调用，直到到达基准情况，停止递归调用链。

3. 1
- 1, 2
- 1, 3
- 1, 2, 4
- 1, 2, 4, 8, 16
- 1, 3, 7, 15, 30
- 1, 3, 6, 12, 25, 50, 100

```java
public static void doubleReverse(String s) {
  if (s.length() > 0) {
    char last = s.charAt(s.length() - 1);
    System.out.print(last);
    doubleReverse(s.substring(0, s.length() - 1));
  }
}
```

5. 栈（`stack`）是关于程序调用的所有方法的结构信息。递归会产生一个高栈，其中代表了每一次递归调用。

6. 新代码将按原始顺序打印行，而不是反序。

7. 新代码会导致无限递归，因为每个递归调用都会产生另一个递归调用，并且没有向基准情况进展。

8. 第二版本的`pow`方法比第一个版本更高效，因为它需要的递归调用更少。

```java
public static int factorial(int n) {
  if (n == 0) {
    return 1;
  } else {
    return n * factorial(n - 1);
  }
}
```

10. 6
- 4
- 7
- 0

11. 基准情况语句有误：它应该测试是否小于 10。

12. 分形是包含更小分形的图像。递归方法很有用，因为它们可以构造分形。

```java
public static void drawHexagon(Graphics g, Point position,
    int size) {
    Polygon poly = new Polygon();
    poly.add(position.x + size / 2, position.y);
    poly.add(position.x + size, position.y + size / 3);
    poly.add(position.x + size, position.y + 2 * size / 3);
    poly.add(position.x + size / 2, position.y + size);
    poly.add(position.x, position.y + 2 * size / 3);
    poly.add(position.x, position.y + size / 3);
    g.drawPolygon(poly);
}
```

# 第 13 章

1. 你可以使用增强循环对数组进行顺序查找，或者先使用`Arrays.sort`排序数组后进行二分查找。

2. 如果元素没有实现`Comparable`接口，应该使用顺序查找。

3. `Arrays.sort`和`Collections.sort`可以成功使用，如果集合是有序的。

4. `O(log N)`
- `O(N)`
- `O(N²)`

5. `O(N)`
- `O(N²)`
- `O(N)`
- `O(N)`
- `O(log N)`
- `O(N³)` 其中`N`是数量
- `O(1)`

6. 两种顺序查找的时间复杂度都是`O(N)`。

7. 二分查找需要排序的数据，否则无法保证找到目标元素。

8. 60 个元素的二分查找最多检查 6 个元素，因为`log 60`向上取等于 6。

9. 因为输入未排序，算法会检查 4、6 和 5。

10. 参数类型应该更改为`double`。此外还需要一个接受`double[]`作为第一个参数的`swap`方法。这是新代码：

```java
public static void selectionSort(double[] a) {
  for (int i = 0; i < a.length; i++) {
    // 找到最小元素的索引
    int smallest = i;
    for (int j = i + 1; j < a.length; j++) {
      if (a[j] < a[smallest]) {
        smallest = j;
      }
    }
    swap(a, i, smallest); // 将最小值交换到前面
  }
}
```

12. 32 个元素的归并排序将生成 63 次`mergeSort`调用，并执行 3 次操作。

13. `{1, 2, 3, 4, 5, 11, 9, 7, 8, 10}`
`{7, 2, 8, 4, 1, 11, 9, 5, 3, 10}`
`{7, 2}, {8, 4, 1}, {11, 9, 5, 3, 10}`
`{7, 2}, {8, 4, 1}, {11, 9}, {5, 3, 10}`
`{7}, {2}, {8}, {4, 1}, {11}, {9}, {5}, {3, 10}`
`{4}, {1}, {3}, {10}`
`{2, 7}, {8}, {1, 4}, {9, 11}, {5}, {3, 10}`

## 附录 A 自习题答案

`(2, 7), (1, 4, 8), (3, 5, 10)`
`(1, 2, 4, 7, 8), (3, 5, 9, 10, 11)`
`(1, 2, 3, 4, 5, 7, 8, 9, 10, 11)`

## 第 14 章

1. 这些包是`java.awt`、`java.awt.event`和`javax.swing`。导入这些包的语句是：

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
```

2. 
```java
String response = JOptionPane.showInputDialog(null,
"What's your age, cowboy?");
int age = Integer.parseInt(response);
if (age < 40) {
  JOptionPane.showMessageDialog(null, "Only " + age + " ... still a young'n.");
} else {
  JOptionPane.showMessageDialog(null, "You're " + age + " ... howdy, old timer!");
}
```

3. 组件（`Component`）是屏幕上的项，如按钮或文本字段。帧（`Frame`）与其他组件不同，它是用户操作系统的一等公民。帧内部包含了其他组件。

4. 帧的某些属性有大小、位置和标题。以下代码创建了一个帧并设置了这些属性：

```java
JFrame frame = new JFrame();
frame.setSize(new Dimension(400, 300));
frame.setLocation(new Point(20, 10));
frame.setTitle("My favorite frame");
frame.setVisible(true);
```

5. 
- `JTextArea`
- `JOptionPane`
- `JLabel`
- `JButton`
- `JTextField`

6. 
```java
JButton b1 = new JButton("Click me");
b1.setBackground(Color.GREEN);
JButton b2 = new JButton("Do not touch!");
b2.setBackground(Color.YELLOW);
```

7. 
- `GridLayout`
- `FlowLayout`
- `BorderLayout`

8. 
```java
frame.setLayout(new GridLayout(3, 2));
frame.add(b1);
frame.add(b2);
frame.add(b3);
frame.add(b4);
frame.add(b5);
frame.setLayout(new FlowLayout());
frame.add(b1);
frame.add(b2);
frame.add(b3);
frame.add(b4);
frame.add(b5);
frame.setLayout(new BorderLayout());
frame.add(b1, BorderLayout.NORTH);
frame.add(b2, BorderLayout.WEST);
frame.add(b3, BorderLayout.CENTER);
frame.add(b4, BorderLayout.EAST);
frame.add(b5, BorderLayout.SOUTH);
```

9. 事件（`Event`）是一个表示用户与图形组件交互的对象。监听器（`Listener`）是一个处理事件的对象。`ActionListener`接口用于处理动作事件。

10. 为了处理事件，你必须编写实现`ActionListener`接口的类。它必须包含一个名为`actionPerformed`的方法。你必须在相关组件上调用`addActionListener`方法将你的新监听器附加到它上。

```java
import java.awt.event.*;
import javax.swing.ActionListener implements ActionListener {
  public void actionPerformed(ActionEvent event) {
    JOptionPane.showMessageDialog(null,
"Greetings, Earthling!");
  }
}
```




12. 面向对象的 GUI 将组件存储为字段。这很有用，因为这样的 GUI 也可以被制作为一个动作监听器，从而访问这些组件。

13. 在实现鼠标监听器时，使用 `MouseInputListener` 接口和 `MouseInputAdapter` 类。这与使用 `ActionListener` 不同，由于接口中的方法非常多，你是扩展一个类而不是实现接口。你更有可能与鼠标监听器的 `MouseEvent` 参数交互，而不是动作监听器的 `ActionListener` 参数交互。

14. 响应鼠标移动事件：

```java
public void mouseMoved(MouseEvent event) {
    if (event.getY() < label.getHeight() / 2) {
        label.setForeground(Color.BLUE);
    } else {
        label.setForeground(Color.RED);
    }

    label.setText("" + event.getX() + " , " + event.getY() + "");
}
```

15. 在绘制 2D 图形时，你应该扩展 `JPanel` 类并编写 `paintComponent` 方法。

16.

```java
import java.awt.*;

import javax.swing.*;

public class RedCirclePanel extends JPanel {
    public void paintComponent(Graphics g) {
        super.paintComponent(g);
        g.drawOval(10, 30, 50, 50);
    }
}
```

17. `Timer` 是一个可以定期间隔触发 `ActionListener` 事件的对象。`Timer` 可以通过让其 `ActionListener` 以某种方式改变面板的状态然后对其重绘来制作面板动画。

18. 一个绘制红色和蓝色圆的动画面板。

```java
import java.awt.*;

import java.awt.event.*;

import javax.swing.*;

public class RedCirclePanel extends JPanel {
    private boolean red;

    public RedCirclePanel2() {
        red = true;

        Timer timer = new Timer(1000, new ColorListener());

        timer.start();
    }

    public void paintComponent(Graphics g) {
        super.paintComponent(g);

        g.drawOval(10, 30, 50, 50);
    }
}
```

## 附录 B

### Java 关键字 (1.2)

| abstract | continue | for | switch |
|---|---|---|---|
| assert | default | goto | package |
| boolean | else | if | synchronized |
| break | enum | instanceof | this |
| catch | final | import | throws |
| class | extends | interface | transient |
| double | native | return | while |
| char | float | protected | volatile |
| byte | super | super | (continued) |

### 基本数据类型 (2.1)

| Type | Description | Examples |
|---|---|---|
| int | 整数（整数数字） | 42 |
| double | 实数 | 39 |
| char | 单个字符 | 'a' |
| boolean | 逻辑值 | true, false |

### 算术运算符 (2.1)

| Operator | Meaning | Example |
|---|---|---|
| + | 加法 | 2 |
| - | 减法 | 5 |
| * | 乘法 | 24 |
| / | 除法 | 4 |
| % | 余数或模 | |

### 关系运算符 (4.2)

| Operator | Meaning | Example |
|---|---|---|
| == | 等于 | true |
| != | 不等于 | false |
| < | 小于 | false |
| > | 大于 | true |
| <= | 小于等于 | false |
| >= | 大于等于 | true |

### 逻辑运算符 (5.2)

| Operator | Meaning | Example |
|---|---|---|
| && | 逻辑与（合取） | (2 == 2) && (4) |
| \|\| | 逻辑或（析取） | (2 == 2) \|\| (3) |
| ! | 逻辑非（否定） | !(2 == 2) |

### 运算符优先级 (2.1, 4.2, 和 5.2)

| Description | Operators |
|---|---|
| 一元运算符 | !, --, +, - |
| 乘法运算符 | *, /, % |
| 加法运算符 | +, - |
| 关系运算符 | <, >, <=, >= |
| 等于运算符 | ==, != |
| 逻辑与 | && |
| 逻辑或 | \|\| |
| 赋值运算符 | =, +=, -=, *=, /=, &&=, \|\|= |

### 包装类 (10.1)

| Primitive type | Wrapper class |
|---|---|
| int | Integer |
| double | Double |
| char | Character |
| boolean | Boolean |

## 附录 B Java 总结

```java
private <type> <name>;

...
```

```java
// 构造函数
public <class name>(<type> <name>, ..., <type> <name>) {
    <statement>;
}
```

```java
<statement>;

...
```

```java
// 方法
public <type> <name>(<type> <name>, ..., <type> <name>) {
    <statement>;
}
```

### 构造函数调用另一个构造函数（第 8.7 节）

```java
this(<expression>, ..., <expression>);
```

### 方法调用超类（第 9.3 节）

```java
super.<method>(<expression>, ..., <expression>);
```

### 构造函数调用超类（第 9.3 节）

```java
super(<expression>, ..., <expression>);
```

### 指定继承关系（第 9.1 节）

```java
public class <subclass> extends <superclass> {
```

### 实现接口（第 9.5 节）

```java
public class <name> implements <interface>
```

### 指定继承关系并实现接口（第 9.5 节）

```java
public class <name> extends <superclass> implements <interface> {
```

### 接口定义（第 9.5 节）

```java
public interface <name> {
    public <type> <name>(<type> <name>, ..., <type> <name>);
}
```

### 抽象类（第 9.6 节）

```java
public abstract class <name> {
    ...
}
```

### 抽象方法（第 9.6 节）

```java
public abstract <type> <name>(<type> <name>, ..., <type> <name>);
```

### `return` 语句（第 3.2 节）

```java
return <expression>;
```

### `throw` 语句（第 4.5 节）

```java
throw <exception>;
```

### `assert` 语句（第 5.5 节）

```java
assert <boolean test>;
```

### 数组声明（第 7.1 节）

```java
<element type>[] <name> = new <element type>[size];
```

### 数组初始化（第 7.1 节）

```java
<element type>[] <name> = {<value>, ..., <value>};
```

### 简单 `if`（第 4.2 节）

```java
if (<test>) {
    <statement>;
    ...
}
```

### `if`/`else`（第 4.2 节）

```java
if (<test>) {
    <statement>;
    ...
} else {
    <statement>;
    ...
}
```

### 以测试用式结尾的嵌套 `if`/`else`（第 4.2 节）

```java
if (<test1>) {
    statement1;
} else if (<test2>) {
    statement2;
} else if (<test3>) {
    statement3;
}
```

### 以 `else` 结尾的嵌套 `if`/`else`（第 4.2 节）

```java
if (<test1>) {
    statement1;
} else if (<test2>) {
    statement2;
} else {
    statement3;
}
```

### `for` 循环（第 2.3 节）

```java
for (<initialization>; <continuation test>; <update>) {
    <statement>;
    ..
}
```

### For-each 循环（第 7.1 节）

```java
for (<type> <name> : <array or collection>) {
    <statement>;
    ..
}
```

### `while` 循环（第 5.1 节）

```java
while (<test>) {
    <statement>;
    ..
}
```

### `do`/`while` 循环（第 5.4 节）

```java
do {
    <statement>;
    ..
} while (<test>);
```

### `try`/`catch` 语句（第 6.4 节）

```java
try {
    <statement>;
    ..
    <statement>
} catch (<type> <name>) {
    <statement>;
    ..
    <statement>
}
```





### ArrayList 常用方法（第 10.1 节）

| 方法 | 说明 | `ArrayList<String>` 示例 |
| --- | --- | --- |
| `add(value)` | 在列表末尾添加指定值 | `list.add("end");` |
| `add(index, value)` | 在索引处添加指定值，后续值向后移动 | `list.add(1, "middle");` |
| `clear()` | 移除列表中所有元素 | `list.clear();` |
| `contains(value)` | 如果列表中包含指定值则返回 true | `list.contains("hello")` |
| `get(index)` | 获取索引处的值 | `list.get(1)` |
| `indexOf(value)` | 返回列表中第一次出现值的索引（未找到则返回 -1） | `list.indexOf("world")` |
| `lastIndexOf(value)` | 返回列表中最后一次出现值的索引（未找到则返回 -1） | `list.lastIndexOf("hello")` |
| `remove(index)` | 移除索引处的值，后续值向前移动 | `list.remove(1);` |
| `set(index, value)` | 将索引处的值替换为指定值 | `list.set(2, "hello");` |
| `size()` | 返回列表中元素的数量 | `list.size();` |

### Character 类常用方法（第 4.4 节）

| 方法 | 说明 | 示例 |
| --- | --- | --- |
| `getNumericValue(ch)` | 将字符转换为数字 | `6` |
| `isDigit(ch)` | 测试字符是否为数字 | `false` |
| `isLetter(ch)` | 是否在字母范围内 | `true` |
| `isLowerCase(ch)` | 是否为小写 | `false` |
| `isUpperCase(ch)` | 是否为大写 | `true` |
| `toLowerCase(ch)` | 字符的小写形式 | `q` |
| `toUpperCase(ch)` | 字符的大写形式 | `X` |

### Collection 接口常用方法（第 1.1 节）

| 方法 | 说明 |
| --- | --- |
| `add(element)` | 将元素添加到集合中 |
| `addAll(collection)` | 将集合中的所有元素添加到此集合 |
| `clear()` | 移除所有元素 |
| `contains(element)` | 如果集合包含该元素则返回 true |
| `isEmpty()` | 如果集合不包含元素则返回 true |
| `iterator()` | 返回一个用于遍历集合的对象 |
| `remove(element)` | 移除该元素的一个出现位置 |
| `removeAll(collection)` | 移除集合中找到的所有元素 |
| `size()` | 返回元素的数量 |

### Collections 类常用方法（第 1.1 节）

| 方法 | 说明 |
| --- | --- |
| `binarySearch(list, value)` | 在列表中查找元素 |
| `copy(destinationList, sourceList)` | 将源列表的所有元素复制到目标列表 |
| `fill(list, value)` | 将列表中的每个元素替换为该值 |
| `max(list)` | 返回值最大的元素 |
| `min(list)` | 返回值最小的元素 |
| `replaceAll(list, oldValue, newValue)` | 将所有旧值出现替换为新值 |
| `reverse(list)` | 反转元素的顺序 |
| `rotate(list, distance)` | 将每个元素向右移动指定的索引 |
| `shuffle(list)` | 将元素重新排列为随机顺序 |
| `sort(list)` | 重新排列为排序（非降）顺序 |
| `swap(list, index1, index2)` | 交换指定索引处的元素 |

### DrawingPanel 对象常用方法（第 3G.1 节）

| 方法 | 说明 |
| --- | --- |
| `getGraphics()` | 返回一个可用于在面板上绘制的 `Graphics` 对象 |
| `setBackground(color)` | 设置面板的背景颜色（默认是白色） |

### Graphics 对象常用方法（第 3G.2 节）

| 方法 | 说明 |
| --- | --- |
| `drawLine(x1, y1, x2, y2)` | 在点 `(x1,y1)` 和 `(x2,y2)` 之间画一条线 |
| `drawOval(x, y, width, height)` | 绘制矩形内最大的椭轮廓 |
| `drawRect(x, y, width, height)` | 绘制指定矩形的轮廓 |
| `drawString(message, x, y)` | 绘制给定文本，其左下角位于 `(x,y)` |
| `fillOval(x, y, width, height)` | 使用当前颜色填充矩形内最大的椭 |
| `fillRect(x, y, width, height)` | 使用当前颜色填充指定的矩形 |
| `setColor(color)` | 设置此图形上下文的当前颜色为指定颜色（所有后续图形操作均使用此颜色） |
| `setFont(font)` | 设置此图形上下文的当前字体为指定字体（所有后续绘制的字符串均使用此字体） |

### File 对象常用方法（第 6.1 节）

| 方法 | 说明 |
| --- | --- |
| `delete()` | 删除指定的文件 |
| `exists()` | 表示该文件在系统中是否存在 |
| `getAbsolutePath()` | 返回该文件所在的完整路径 |
| `getName()` | 以字符串形式返回此文件的文件名，不带任何路径 |
| `isDirectory()` | 表示该文件在系统中是否为目录/文件夹 |
| `isFile()` | 表示该文件在系统中是否为文件（非文件夹） |
| `length()` | 返回文件中的字符数 |
| `mkdirs()` | 如果不存在，则创建该文件表示的目录 |
| `renameTo(file)` | 将此文件重命名为给定的文件名 |

## 附录 B Java 总结

### Iterator 对象的方法（第 11.1 节）

| 方法 | 描述 |
| --- | --- |
| `hasNext()` | 如果有更多元素待检查，则返回 true |
| `next()` | 返回列表中的下一个元素并将迭代器位置移动一位 |
| `remove()` | 移除由 `next()` 返回的元素 |

### Map 对象的常用方法（第 11.3 节）

| 方法 | 描述 |
| --- | --- |
| `clear()` | 移除 map 中所有的键和值 |
| `containsKey(key)` | 如果给定的键映射到此 map 中的某个值，则返回 true |
| `containsValue(value)` | 如果此 map 中的某个键映射到给定的值，则返回 true |
| `get(key)` | 返回与键关联的值，如果未找到则返回 null |
| `isEmpty()` | 如果此集合不包含任何键或值，则返回 true |
| `keySet()` | 返回 map 中所有键的 Set |
| `put(key, value)` | 将给定的键与给定的值关联 |
| `putAll(map)` | 将给定 map 中的键/值映射添加到此 map 中 |
| `remove(key)` | 从此 map 中移除给定的键及其关联的值 |
| `size()` | 返回 map 中键/值映射的数量 |
| `values()` | 返回 map 中所有值的 Collection |

### Math 类的常量和常用方法（第 3.2 节）

| 常量 | 描述 |
| --- | --- |
| `E` | 自然对数中使用的底数 (2.71828...) |
| `PI` | 圆周长与直径的比率 (3.14159...) |

| 方法 | 描述 | 示例 |
| --- | --- | --- |
| `abs` | 绝对值 | `Math.abs(-308)` 返回 308 |
| `ceil` | 向上（向上取整） | `Math.ceil(2.13)` 返回 3.0 |
| `cos` | 余弦（弧度） | `Math.cos(-Math.PI)` 返回 -1.0 |
| `exp` | 以 e 为底的指数 | `Math.exp(1)` 返回 2.7182818284905 |
| `floor` | 向下（向下取整） | `Math.floor(2.93)` 返回 2.0 |
| `log` | 以 e 为底的对数 | `Math.log(Math.E)` 返回 1.0 |
| `log10` | 以 10 为底的对数 | `Math.log10(1000)` 返回 3.0 |
| `max` | 两个值中的值 | `Math.max(45, 207)` 返回 207 |
| `min` | 两个值中的最小值 | `Math.min(3.8, 2.75)` 返回 2.75 |
| `pow` | 幂（通用幂） | `Math.pow(3, 4)` 返回 81.0 |
| `random` | 随机值 | `Math.random()` 返回随机值 `k`，使得 0.0 ≤ `k` < 1.0 |
| `sin` | 正弦（弧度） | `Math.sin(0)` 返回 0.0 |
| `sqrt` | 平方根 | `Math.sqrt(2)` 返回 1.41421356230951 |
| `toDegrees` | 将弧度转换为角度 | `Math.toRadians(Math.PI)` 返回 180.0 |
| `toRadians` | 将角度转换为弧度 | `Math.toRadians(270.0)` 返回 4.7123889038469 |

### Object 类的方法（第 9.3 节）

| 方法 | 描述 |
| --- | --- |
| `clone()` | 创建并返回对象的副本（不是公共方法） |
| `equals(obj)` | 表示另一个对象是否等于此对象 |
| `finalize()` | Java 在对象销毁时自动调用（不是公共方法） |
| `getClass()` | 返回关于对象类型的信息 |
| `hashCode()` | 返回与对象关联的数字；用于某些数据结构 |
| `toString()` | 以字符串形式返回对象的的状态 |
| `notify(), notifyAll(), wait()` | 用于多线程编程的高级方法 |

### Point 对象的常用方法（第 3.3 节）

| 方法 | 描述 |
| --- | --- |
| `translate(dx, dy)` | 通过给定的量平移坐标 |
| `setLocation(x, y)` | 将坐标设置为给定的值 |
| `distance(p2)` | 返回此 `Point` 到 `p2` 的距离 |

### Random 对象的常用方法（第 5.1 节）

| 方法 | 描述 |
| --- | --- |
| `nextInt()` | 在 $-2^{31}$ 和 $(2^{31} - 1)$ 之间的随机整数 |
| `nextInt(max)` | 0 到 (`max` - 1) 之间的随机整数 |
| `nextDouble()` | 0.0（包含）到 1.0（不包含）之间的随机实数 |
| `nextBoolean()` | true 或 false 的随机逻辑值 |

### Scanner 对象的常用方法（第 3.4 节和 5.3 节）

| 方法 | 描述 |
| --- | --- |
| `next()` | 读取并返回下一个字符串标记作为 `String` |
| `nextDouble()` | 读取并返回一个 `double` 值 |
| `nextInt()` | 读取并返回一个 `int` |
| `nextLine()` | 读取并返回下一行输入作为 `String` |
| `hasNext()` | 如果有另一个标记待读取，则返回 true |
| `hasNextDouble()` | 如果有另一个标记待读取且可以解释为 `double`，则返回 true |
| `hasNextInt()` | 如果有另一个标记待读取且可以解释为 `int`，则返回 true |
| `hasNextLine()` | 如果有另一行输入待读取，则返回 true |

### String 对象的常用方法（第 3.3 节）

| 方法 | 描述 | 示例（假设 `s` 为 `"hello"`） |
| --- | --- | --- |
| `charAt(index)` | 指定索引处的字符 | `s.charAt(1)` 返回 `'e'` |
| `endsWith(text)` | 字符串是否以某个文本结尾 | `s.endsWith("llo")` 返回 true |
| `indexOf(text)` | 字符或字符串的索引，不存在则返回 -1 | `s.indexOf("o")` 返回 4 |
| `length()` | 字符串中的字符数量 | `s.length()` 返回 5 |
| `startsWith(text)` | 字符串是否以某个文本开头 | `s.startsWith("hi")` 返回 false |
| `substring(start, end)` | 从起始索引到停止索引（之前的字符 | `s.substring(1,3)` 返回 `"el"` |
| `toLowerCase()` | 全小写的字符串字符串 | `s.toLowerCase()` 返回 `"hello"` |
| `toUpperCase()` | 全大写的新字符串 | `s.toUpperCase()` 返回 `"HELLO"` |

## 附录 C Javadoc 注释与 APIget

![](img/aea18896a4bced58de45f29f5a93f7b3_883_0.png)

例如，以下是 `Scanner` 类用于从文件读取输入的构造函数的摘要信息：

### 构造函数摘要

`Scanner` (`File source`)

一个新的 `Scanner` 会产生从指定文件扫描出的值。

点击方法可以提供有关如何使用它的有用详细信息，包括更长的描述、方法所需的每个参数的详细说明、方法返回的数值类型（如果有）的描述，以及该方法可能抛出的任何异常列表。这些详细视图允许您学习方法的先决条件和后置条件，并查看调用示例及其结果。

## 附录 C Javadoc 注释与 APIget

例如，以下是关于 `String` 类 `substring` 方法的详情：

```
substring

public String substring(int beginIndex, int endIndex)
```

返回一个该字符串的子字符串的新字符串。子字符串从 `beginIndex` 开始，延伸到索引 `endIndex-1` 处的字符。因此，子字符串的长度是 `endIndex-beginIndex`。

示例：

`"hamburger".substring(4, 8)` 返回 `"urge"`  
`"smiles".substring(1, 5)` 返回 `"mile"`

- 参数
  - `beginIndex`—起始索引（包含）。
  - `endIndex`—结束索引（不包含）。

- 返回

  指定的子字符串

- 抛出

  `IndexOutOfBoundsException`—如果 `beginIndex` 为负，或者 `endIndex` 大于此对象的长度，或者 `beginIndex` 大于 `endIndex`。

API 规范中的某些方法被标记为已用（deprecated）。

> 已用
>
> 已用项是 Java 设计者希望你不要的方法，因为它们的行为不正确或安全。你可能认为 Sun 应该删除这些方法，但这样做会破坏调用这些方法的旧程序。已用方法的示例是 `java.awt` 包中的 `inside` 方法：
>
> ```java
> inside(int X, int Y)
> ```
>
> 已用。JDK 版本 1.1 被 `contains(int, int)` 替换。

## 编写 Javadoc 注释

如果你以 Javadoc 的特殊样式编写注释，它们就可以自动生成类似于 API 规范的网页。Javadoc 通过在每个类中编写 Javadoc 注释来生成 API 规范。标记 Javadoc 注释的语法是以 `/**` 开始的多行注释：

```java
/**
 *
 */
```

Javadoc 注释可以添加到类头部、方法、类常量、公共字段以及类的其他可见成员中。许多 Javadoc 注释还使用特殊的标签（tags）来指定额外信息。标签中的信息可以是边界条件、允许的参数范围以及示例。标签的语法是写 `@` 符号加上标签名，然后是任何额外信息。常见的 Javadoc 标签如下表所示：

| 标签名称 | 说明 |
| --- | --- |
| `@author <name>` | 编写此类的作者 |
| `@param <name> <description>` | 该方法的参数详情 |
| `@return <description>` | 方法返回值的详情 |
| `@throws <type> <description>` | 方法可能抛出的异常类型及其发生的情况 |
| `@version <number>` | 文件的版本或修订号：可以是数字如 1.2.5，也可以复杂的字符串如日期 |

`@author` 和 `@version` 标签通常用于类头部。例如，以下注释可以位于 `Point` 类的头部：

```java
/**
 * Point 对象表示二维笛卡尔平面上的 (x, y) 坐标有序对。
 * @author Marty Stepp (stepp@example.com)
 * @version 1.2 (2007年1月12日)
 */
```

```java
public class Point {

}
```




## 附录 C Javadoc 注释与 Java API

`@param` 和 `@throws` 标签用于方法和构造函数。非 `void` 方法也可以使用 `@return` 标签。如果这三个标签提供了从方法头部或整体注释中无法识别的有用额外信息，最好使用它们。

例如，以下注释可以位于 `Point` 类 `distance` 方法的头部：

```
/**
 * 计算此点与
 * 给定另一个点之间的距离。
 * @param p 计算距离的点
 * @return 距离，计算方法为两点之间 x 坐标 (dx) 和 y 坐标 (dy) 差值的平方和的平方根
 * @throws NullPointerException 如果 p 为空
 */
```

```
public double distance(Point p) {
    int dx = p.x;
    int dy = p.y;
    return Math.sqrt(dx * dx + dy * dy);
}
```

如前所述，Javadoc 注释可以转换为 Web 页面。某些 Java 编辑环境包含此功能；检查你的编辑器是否提供。如果没有，Sun 的 JDK 包含一个生成页面的命令行工具。要使用它，打开终端窗口到你的源文件目录并输入以下命令：

```
javadoc *.java
```

前述类生成的网页如图 C.2 所示。

![](img/aea18896a4bced58de45f29f5a93f7b3_886_0.png)

图 C.2 类生成的 Javadoc 页面

点击方法名称会调出方法的详情页，就像 API 规范中一样。前述方法生成的网页如下：

### 方法详情

```
public double distance(Point p)
```

计算并返回此点与另一个点之间的距离：

参数：

- `p` - 计算距离的点

返回：

距离，计算方法为两点之间 x 坐标 (`dx`) 和 y 坐标 (`dy`) 差值的平方和的平方根

抛出：

```
java.lang.NullPointerException - 如果 p 为空
```



由于 Javadoc 注释被转换为 HTML，它们可以包含在任何生成的页面中显示的 HTML 标签。

## 索引

- C 编程语言，43
- 计算，58–59，表达式栈 61–68
- 大写字母，16
- 组件，GUI，331
- 交互，748–756
- 布局，740–748
- 复合布局，744–748
- 复杂，3–5
- 约束，70–73
- 条件执行，207
- 应用，224–235
- `if/else` 语句，211–224
- 循环，208–211
- 方法，235–243
- 控制台，90
- 中央处理面向对象而非 C 语言
- 类，用例，面向对象类型
- 分组，11
- 空格，154
- `start` 方法，199
- `char` 类型，127，235–238
- 检查检查（checked checks），337
- 类，7，101–104
- 抽象，544–549
- `ArrayList`，570–575
- 常量，98
- `d`，539–541
- 输入，152
- 输出，110
- 窗口，10
- `DrawingPanel`，720–775
- 封装，501
- 扩展，505–508，522–524
- 事件，501–503
- 类，96，98，101–104
- 颜色（`Color`），180
- 声明，97
- `Math` 类，132
- `Graphics2D`，528–530
- `HashSet`，619，620，632
- 实例，137–148
- 实现，147–152
- 参数，128–129
- 构造函数，143，148–146
- 实现，486–490
- 元组，474–474
- 对象，449–453
- 超类，519–520
- 常量（myants），457–460
- 库，7，537
- `Math`，131–133，166
- `Object`，522，525，549
- 对象，等等等
- 控制变量，81
- 坐标，转换，150
- 新方法，123
- 构造函数，216
- 耦合，478–480
- 面向对象编程（OOP），438–441
- `Scanner`，`Scanner` 类
- `this` 关键字，469–474
- `TimeSpan`，477–480
- CPU（中央处理单元），3
- 字符（critters），558
- CRC 码，484
- 累积，208–210
- 数组，424–426
- `TreeSet`，619，620，632
- 包装，572–575
- 客户端，499
- `if`，215–216
- 舍入，229
- 大括号) (11，13)
- 自定义排序，691–694，723
- COBOL 编程语言，461
- 用于 `for` 循环编程的代码
- 重用，502
- 数据处理，333
- 数据类型，54–55，611，613
- 调试，21–24
- 小数，4
- 声明，
- 集合，483
- 集合，604–605，630，631
- 颜色，
- 常量，180
- 常量，97
- 导入声明，145
- 方法作用域，88
- 变量，65，68–70
- 列打印，426–429
- 命令行参数，1–4
- 缩进，19–21
- 可比较的（`Comparable`），575–584，619，689，692
- `Comparable` 接口，575，584，596
- 自定义排序的比较器，691，694，723
- 比较器，601–614
- 比较器，577–584
- 比较函数，577
- 编译器，6
- 复杂度
- 类，70，700，723，724
- 管理，97，98，111，114
- 解构，顺序过程化解构
- 递减运算符（–），73–75，95–96
- 默认构造函数，148
- a. 有限循环，81
- 设计，38
- 类，33–51
- 非确定性，228–250
- OOP 383–458
- 默认计算机，48
- 目录，31，63，64，66
- 点. 146
- 点表示法，131
- `double` 类型，54，62，63，64，76–77
- 并发，92–93
- 舍入，228–300
- 嵌套循环，115，170–200
- 迭代器，575
- 嵌套循环（`Dunker_loop`），600–638
- EBC 209
- 表达式谜题，683
- 条件表达式，211–224
- 因子分解，239–251
- 嵌套，219–224
- 员工接口，503–512
- 环境编程，510
- 时间戳（epoch），702
- 等于
- 数组，402–404，429
- 嵌套，226–228
- 邮件方法，227，462–69
- 等于（`==`）运算符，214
- 逻辑，24–25
- 循环，83
- 回滚，228–230
- 运行时，21，35，37
- 用户，292–295
- 逃逸序列，15–16
- 事件，739–740，756，764
- 异常，141，164
- 检查（checked），335
- 抛出，243–247
- 条件执行
- 执行流，40，41
- 表达式，55，57，105
- 前缀/后缀评估，672–675
- 扩展，文件，8，333–334
- 格式
- 后置循环，210，211，217，219
- 永久循环，299，300
- `for` 循环，78，87，108–111
- 终止，98
- 无限循环，91，嵌套，85，88
- 形式化参数，120
- 分形，667
- 框架，GUIs，731，735，737–738
- 函数，113–113
- 定义，133
- `Math` 类，131–133
- 递归，656，666
- 最大公约数（GCD），5
- 最大公约数（GCD），658，663
- 通用类，560，569
- 签名，240，241
- 加权（weighted），284
- 图形用户界面（GUIs）
- 颜色，180，184
- `DrawingParameter` 对象，175，176
- 实例（lines），184，187
- GUI，764，770
- 线和形状，绘制，176，180
- 方法，191–192
- 对象，174–175
- 概览，197，199
- 程序化解构，187–192
- 递归，661–677
- 测试，184–185
- `Graphics2D`，528–530
- `Graphics` 类，176
- 生成器运算符，214
- 大于等于（`>=`）运算符，214
- 最大公约数 GCD，409–417
- 2D 图形，764–770
- 组件，交互，748–756
- 组件，布局，740–748
- 事件，756
- 概览，727–740
- 哥登堡（Gutenberg），332
- 固定法，671–672
- 继承，517–518，502–512
- 字段，519–520
- 输入，423–424
- 消耗，341–345
- `instanceof` 代码，466–469，526–527
- 实例方法，443–469
- 整数，4，54
- 交互式程序，152，156
- 接口，530–537
- API，575–584，598
- 互联网数据库（IMDB），332
- 类型，54–55
- 转换为，622–637
- 动机类（motivation class），158–160
- `id`，2，462
- 关系，527–528，549
- 迭代器，81
- 迭代增强，28
- 迭代器，608–611，632
- 黑客字典，35
- 硬件，439–440，586–589，599
- 硬盘，1
- `HashSet` 类，619，628，632
- 方法，11，29–127，128，485–486
- Hello World，10–14
- 尽管，104，503，504，333
- 霍珀（Grace Hopper），24
- 工作时长，420–429
- IBM，750–760
- 项目，259–263
- 标识符，16，19
- IDE（集成开发环境），8
- 条件执行，211–224
- 因子化（facturing），230–231
- 嵌套，219–224
- 不可变对象，142，476，490
- 隐式参数，446–447
- 导入声明，143
- 递增运算符，205
- 不确定循环，295–300
- 索引，176
- 射线，376
- `ArrayList`，562
- `List`，604
- `String`，139–140
- `indexOf` 方法，142，686
- 无限循环，91
- 无限递归，677
- KB（千字节），5
- 柯尼根（Brian Kernighan），14
- 关键字，16–19
- 断，308–309，317
- `final`，97
- `instanceof` 代码，466–469
- 公有，29
- 预留，17
- 静态，30，97
- `this`，469，474，480
- 树，30

# 868

## 索引

- `methods_count`
  - 所有其他方法，338
  - 基于 `for` 的方法，153
  - `toLowerCase`，143
  - `toString`，406–462，490
  - 制表符列（`tabs_column`），140–156，167–168
  - 状态类（`status_class`），128
  - `writeSpaces`，119
  - `mit_joins`，231–235
  - 传士与吃鬼者问题，682
  - 类型混合（`mixing_types`），62–63，77
  - 鸭子测试（Model-Duck-Testing），497–499–529
  - 鼠标事件（`mouse_events`），760–764
  - 多维数组，414–420，430
  - 多个构造函数，474–474
  - 多个参数，126–128
  - 乘法运算符，124
  - 变异器（mutators），447–449，490
  - Myers-iggs_test，435
- `fields`，441–443，490
  - 瓷砖（tiles），332–335
  - 图形（graphics），174–175
  - 图形（`Graphics`），176
  - 不可变的（immutable），142，476，490
  - 方法（methods），168，443–449
  - 多个（multiple），148–150
  - 参数（parameters），150–152，164
  - 点（`Point`），143，146
  - `Scanner`，153–154
  - 搜索（searching），711
  - 字符串（strings），137–143，142，162
  - 使用（using），135–152，168–169
- off-by-one GOB，387–388
- OOD（面向对象设计），538
  - 启发式（heuristics），483–485
  - OOP（面向对象编程），438–441，483–485，490
  - 操作（oper），59
  - 操作系统（operating systems），3
  - 运算符（operator），56
- N
  - b 的名称（name of bies），374
  - 瓷砖（tiles），8
  - 字体（font），256
  - 方法（methods），164
  - 类型（types），54
  - 噪声幅度（`noise_amplitude`），576
  - 自然排序（natural ordering），577
  - 嵌套 `for` 循环（nested for loops），85，87
  - 嵌套 `if/else` 语句（nested if/else statements），219–224
  - 变异（mutation）
    - 算术（arithmetic），672
    - 点（dot），131
    - 不等于运算符（`!=`），214
    - NOT（非）运算符，281
    - `null`，361，362，378，413，466–467，487
  - 数字（numbers）
    - 二进制（binary），4
    - 斐波那契（enonacci），112
    - 数量级（mags），96
    - 随机（random），276–279
    - 寻找小因数（small divisor, finding），273–274
- O
  - `Object_class`，524，525，549
  - 面向对象设计（Object-Oriented Design），见 OOD
  - 启发式（heuristics），483–485
  - 面向对象编程（object-oriented programming），见 OOP
  - 对象（object），175–490
    - 数组（arrays），413–414，430
    - 作为参数（as parameters），146，147
    - 类（classes），439–441
    - 构造函数（constructors），449–453
    - `DrawingPane`，175–176
    - 等等性（equality），226–228
- 包（packages），145
  - 绘制面板（pannels, drawing），765–767
  - 参数（parameters），30，117，165–167
    - 实际的（actual），120
    - 常量（constants），128–129
    - 形式的（formal），120
    - 隐式的（implicit），446–447
    - 初始（initializing），121
    - 局限性（limitations of），124，126
    - 机制（mechanics of），61，121–124
    - 方法（methods），129，136，164
    - 多个（multiple），126–128
    - 无对象的（noobjects），150–152，164
    - 视图（view of），118–130
  - 语义类（semantic class），345–346
  - 括号（parentheses），60
  - 参与者（participant），475–477
  - 杨辉三角（Pascal’s Triangle），417–420
  - 路径（paths），346–348
- 方法重载（overloading methods），129–130
- 方法重写（overriding methods），508–510，522

## 索引

- 排列（permutations），681
- 皮卡德，让（Picard, Jean-Luc），385
- 鹅石（pebble），158
- 点类（Point classes），525–527
- 点对象（Point objects），143–146
- 多态（polymorphism），510–517，549
- 后置条件（postconditions），243
- 正数符号（positive notation），617–623
- 前置符号（prepositive notation），76
- 优先级运算符（precedence operators），662–676，108–211
- 原始数据类型（primitive data types），63，54–55，105
- 打印命令（print command），83–88
- 打印命令（print command），83
- 私有字段（private fields），157–158
- 私有方法（private method），455–457
- 过程化分解（procedural decomposition），25，35–44，187–192
- 编程（programming），8–10
- 控制流（flow of control），31–33
- 调用其他方法（methods that call other），33–35
- OO，104
- 概述（overview of），1–10，43
- 过程（process of），5–7
- 运行时错误（runtime errors），35–37
- 静态方法（static methods），28–31
- 任务（tasks），118。见另
- `ArrayList` 类，566–567
- 数组（arrays），382–386
- 断言（assertions），300–309
- 错误（errors），21–25，44
- 接口（interface），152–156，169–170
- 概述（overview of），10–21
- 伪代码（pseudocode），93–95，98–100
- 公共查询（public query），29
- 标点错误（punctuation errors），22
- 勾股定理（Pythagorean Theorem），134
- 随机列表类（random-list class），277，279
- 随机数（random numbers），376–279
- 可读性（readability），19–21
- 读取行（reading lines），333–339，421–424
- 绘制矩形（rectangles, drawing），178
- 矩形二维数组（rectangular two-dimensional arrays），415–416
- 递归（recursion），614–665，660–663，639
  - 二分搜索（binary search），708–710
  - 目录（directories），663–666
  - 示例（example of），647–656
  - 表达式评估（expressions, evaluating），672–675
  - 函数（functions），655–666
  - 图（graphs），667–671，777
  - 整数异常（integer exception），656–658
  - 归排序（merge sort），718–720
  - 符号（notation），671–672
  - 程序（programs），675
  - 递归地思考（thinking recursively），640–646
- 语义（semantics），146–148，164，147
- 关系运算符（relational operators），214–215
- 取余数运算符（remainder operator），59
- 结果（results），555
- 值转换（turning values），130–136，167–168，247–250
- 反转数组（reversing arrays），405–408
- 健壮程序（robust programs），294–295
- `Random` 类/列表（class/list），625
- 舍入误差（roundoff errors），228–230
- 运行时（runtime），21，35–37

# Q

- 二次方程（quadratic equation），171

# R

- RAM（随机内存），3
- 随机访问数组（random access, arrays），386–391
- 随机访问内存（random access memory），见 RAM

# S

- `Scanner` 类，153–154
- 文件读取（files, reading），335–339
- 参数（parameters），345–346
- 字符串（string），351–355
- 用户错误（user errors），292–293
- 范围（scope），88–92
- 滚动（scrolllose），755–758
- 搜索（searching），685，723
- `ArrayList` 类，566–568，598
- 数组（arrays），400–402
- 二进制（binary），619
- 效率（efficiency），695–703

# Index

- 缓存（caching, common），6
- 实现（implementation），709–714
- 图书管理员（librarian），686–694，723
- 对象（object），11
- 句子（sentence），6
- 选择排序（selection sort），714–722
- 分号（`;`）；0，14
- 哨兵循环（sentinel loops），274–276
- 顺序搜索（sequential searching），686，704，723
- `setColor` 方法，181
- 集合（sets），616–624，632
- 形状（shape）
  - 绘制（drawing），176–180
  - 接口评估（interfaces, evaluation），284–288
  - 短路评估（short-circuit evaluation），284
  - 数据洗牌（shuffling data），690–691
  - 谢尔宾斯基三角形（Sierpinski triangle），667
- 变换通信（transformed communication），616–617
- 签名（signature, methods），129
- `sin` 方法，133
- Snappy，436
- 社会安全（Social Security），59，627–628
- 软件危机（software crisis），502
- 排序（sort），1
- 排序（sorting），685–723
- 归并排序（merge sort），714–722，723
- 选择排序（selection sort），711–714，723
- 拼写错误（spelling error），22
- 球形距离（spherical distance），173
- 数组分割（splitting arrays），715–718
- `sqrt` 方法，130
- 稳定婚姻（stable marriage），637
- 对象状态（state of object），438
- 语句（statement, clause），6
- `assert`，68
- 条件执行（conditional execution），211–224
- `do/while`，295–299
- `if/else`，230–231
- `if`，215–216，217
- 嵌套循环（nested loops），85
- 嵌套 `if/else`（nested if/else），219–224
- 打印（print），81–85
- 打印（println），14–16
- 提示（prompts），156
- `try/catch`，359–364
- `while`，372–373
- `while-else` 循环（while-else loops），85
- 静态方法（static methods），28–31
- 关键字（`this` keyword），30，97
- 步进改进（stepwise refinement），28
- `Stock` 类（Stock class），42–490，517，538–543
- 拼接（concatenation），70–73
- 对象（objects），13–14，142，164
- `Scanner` 类，351–355
- 子类（subclasses），507–549
- 父类（superclasses），596–517
- Swing，728，734，740
- `System.out.print`，83，85
- `System.out.printf`，238–243
- `System.out.println`，14–15，105–238–243
- 制表符（tabs, white-space），154
- 计数（tallying），386–391
- 任务（tasks），118。见另
- 温度平均（temperatures, averaging），382–386
- 模板（templates, syntax），11，134
- 终止符（terminators, statement），12
- 文本区域（text areas），756–758
- 字段（fields），735–737
- 图形（graphics），184–187
- 处理（processing），235–243
- 关键字（`this` keyword），460–474，490
- 三个字符串（Three Strings），617
- 抛出异常（throwing exceptions），141–243
- 抛出语句（thrown clause），337
- 时间效率（time efficiency），695
- 时器（timers, animation），767–770
- `TimeSpan` 类（TimeSpan class），477–480
- 标记（tokens），151–385
- 基于标记的方法（token-based methods），153
- 基于标记的降序（token-based descending），339–350
- 标记化输入（tokenizing input），154
- `LowerCase` 方法，143
- 顶层向下编程（top-down programming），27
- `toString` 方法，460–462
- `toLowerCase` 方法，143
- 汉诺塔（Towers of Hanoi），682
- 追踪（tracing）
  - 控制流（flow of control），31
  - 循环（loops），80–83
- 翻译（translating）
  - 语言（languages），6
- 遍历数组（traversing arrays），429
- `TreeSet` 类，619–620，628，632

## 索引

- `try/catch` 语句（try/catch statements），359–364

# W

- `while` 循环（while loops），272–279
- 布尔值（boolean），279–292
- 空格（whitespace），154

- 类型（types）
  - 大小写（casing），62–63
  - 威尔里斯，莫里斯（Wilkes, Maurice），21
  - 字符（`char`），127，235–238

# 窗口（windows）

- 数据（data），54
- 控制台（console），10
- 双精度（double），54–55
- 创建（creating），175–176
- 错误（errors），21–25
- 字数（word count），628–630
- `int`，54–55
- 包装类（wrapper classes），572–575
- 混合（mixing），62–63，76–77
- `writeChars`，128
- 原始数据（primitive data），54–55
- `writeSpaces` 方法，119
- 引用（references），147
- 字符串（String），137–143
- 值（values），146

# U

- 单元运算符（unary operators），214
- 拆箱（boxing），574，576
- Unicode，239
- 未初始化变量（uninitialized variables），65
- 用户错误（user errors），292–295

# Y

- Y2K 漏洞（Y2K bug），461
- 尤达（Yoda），22

# V

- 变量（variables），63–68，105，107
- 赋值（assigning），68
- 控制（control），31
- 词汇（vocabulary），57
