
# Java 程序设计：高级特性（核心系列）更新至 Java 8

![](img/cover01308.jpeg)

![](img/image01208.jpeg)

![very-small-rose](img/image01209.jpeg) ![fractal-tree2](img/image01210.jpeg) ![very-small-rose](img/image01209.jpeg)

## 献词

“本书献给所有每天做出牺牲的人，特别是那些为了确保我们的自由与安全而做出牺牲的人。”

非常感谢湿婆神 Lord Shiva 在生命中赋予我写作的技术和一切能力。

亲爱的父亲，谢谢你 baauji，通过你的榜教教会了我基于原则生活的生活的意义。

亲爱的两位妈妈，谢谢你们向我真实地展示如何根据最重要的原则和无条件的爱去生活。

亲爱的兄弟姐妹+Priya，谢谢你，你的笑容点亮了我的每一天。你的热情让我的心歌唱。我爱你们所有人。

我特别提到生活中那些帮助我度过悲伤的美丽面孔：

谢谢 Priyanka，你是我生命的意义，是我眼中的明珠，我对你的爱溢于言表。

谢谢你们 Hem Zizu, Navneet, Aman(Rajjo) Eminem —— 你们是我的灵感，让我想起“为运动而唱”。

### 关于作者

Harry.H. Chaudhary 是一位在技术领域拥有多年经验的资深专家。他担任 IT 经理，并是知名的黑客主义者。他在计算机安全和编程领域有着深厚的造诣。他曾在全球多个社区中分享他的技术知识。

跟随畅销 Java 编程书籍作者 Harry H. Chaudhary 快速掌握 Java 编程的所有基础和高级特性（已售出超过 167,000 本！）。本 Java 指南从基础开始，通过数千行 Java 代码详细带你进入 Java 的进阶特性，我承诺这本书将让你成为 Java 专家级冠军。任何人都可以通过这本书学习到专家水平的 Java。

工程类专业的学生和新手开发者也可以使用这本书。这本书涵盖了所有计算机科学专业学位共同的核心大纲。如果你非常认真，请尽管通过这本终极 Java 书来成就自己。

这本 Java 书的主要目标不仅仅是提供 Java 编程知识，我遵循了一种模式，即针对每个 Java 主题通过清晰的理论解释和不同的 Java 复杂度来改进数千个代码问题的解决方案，你会为复杂的 Java 问题找到多种解决方案。

## 特别之处

在书中，我为开发者和新手详细涵盖并介绍了最新的 Java 8 特性的几个主题，例如：

- `Lambdas`
- `Java 8 函数式接口`
- `Java 8` 中的 `Stream` 和 `Time API`

如果你读过这本书，你就知道会有什么样的体验：一种专为你大脑工作方式设计的视觉丰富的格式。如果你没读过，那你大有福了。你会发现为什么人们说它与你读过的任何 Java 书不同。

学习一门新语言并非易事，尤其是对于像 `Java` 这样面向对象的编程语言时。你可能认为问题出在你的大脑上。它似乎有自己的主意，它并不总是想要吸收你被迫学习的那些枯燥的技术内容。事实是，你的大脑渴望新奇。

它不断地寻找、扫描，等待异常情况的发生。毕竟，它是为了帮助你生存而这样构建的。它将所有常规、平凡、无聊的内容过滤到背景中，以免干扰大脑的真正工作——记录重要的事情。你的大脑是如何知道什么是重要的？

## 第 1 章：Java 概述

### 引言

这本 `Java` 书不需要之前的编程经验。然而，如果你有 `C` 或 `C++` 编程背景，你将能够学得更快。

出于这个原因，本 Java 书对 `Java` 的几个关键特性进行了快速的详细概述。这里描述的内容将为你提供一个脚点，让你能够编写和理解简单且典型的程序。大多数讨论的主题将在后续章节中通过数千个实时的 Java 代码示例进行更详细的检查。

正如我们所知，过去几年文档记录了这样一个事实：Web 不可挽回地重塑了计算的面貌，不愿掌握其环境的程序员将被遗留。以上是一个强有力的陈述，也是事实。

越来越多的应用程序必须接入 Web 接口。应用程序本身已不再重要，几乎通用的 Web 访问正在拉动、推动并诱导程序员为在线世界编程，而 `Java` 是许多人将用来实现此点的语言。坦率地说，精通 `Java` 对于专业程序员来说不再是一个选项，而是一项要求。这本书将帮助你掌握。

`Java` 是由 Sun Microsystems 公司于 1991 年开发的强大面向对象编程语言。`Java` 最初是为消费电子设备开发的，但后来转向互联网。现在 `Java` 已成为互联网广泛使用的编程语言。`Java` 是一种平台中性的语言（机器无关）。由 `Java` 开发的程序可以运行在世界上任何硬件或任何操作系统上。

Sun Microsystems（甲文）于 1995 年 5 月的一次大会议上正式宣布了 `Java`。通常情况下，此类事件不会引起太大关注。然而，由于对万维网的极大兴趣，`Java` 引起了商业界的立即关注。

`Java` 现在用于创建具有动态交互内容的 Web 页面，开发大型企业应用，增强万维网的功能。

### Java 的需求

`Java` 的开发是因为需要一种平台中性的语言，可以用于创建嵌入到各种消费电子设备中的软件，如微波炉和遥控器。用 `C` 和 `C++` 编写的程序是针对特定特定硬件编译的，该程序不会在任何硬件上运行。因此需要一种平台中性的语言。

### Java 类库

`Java` 程序由所谓的“类”（classes）组成。“类”由“方法”（methods）组成，方法执行任务并在完成任务时返回信息。程序员指定编辑器中的文件应如何被保存，程序存储在次级存储设备（如磁盘）上。Java 程序文件名以 `.java` 扩展名结尾。

### 典型环境的基础

Java 系统通常由几个部分组成：环境、语言、应用程序接口 (`API`) 和各种类库。接下来的讨论解释了典型的 Java 开发环境，Java 程序通常通过五个阶段执行。这些阶段是：编辑、编译、加载、验证和执行。随后的描述使用了标准的 `Java SE 7` 开发工具包 (`JDK 7`)，它由 Oracle 提供。

如果你使用的是不同的 Java 开发环境，你可能需要遵循不同的程序来编译和执行 Java 程序。在这种情况下，请咨询你的编译器的文档以获取详情。

阶段 1 包含编辑文件。这是通过编辑器程序（通常称为编辑器）完成的。程序员使用编辑器输入 Java 程序，并在必要进行修正。

Java 集成开发环境（IDE），例如用于 Java 社区版的 Forte、NetBeans、Borland 的 `JBuilder`、Symantec 的 Visual Cafe 以及 IBM 的 Visual Age，都内置了集成到编程环境中的编辑器。

我们假设读者知道如何编辑文件。像 `Java` 这样的语言是面向对象的——在这样的语言中编程被称为面向对象编程（`OOP`），它允许设计人员将面向对象的设计实现为运行的系统。相反，`C` 等语言是过程化编程语言，因此编程倾向于以操作为中心。

在 `C` 中，编程单元是 `function`（函数）。在 `Java` 中，编程单元是 `class`（类），最终从中实例化对象（这是“创建”的形象术语）。`Java` 类包含 `methods`（实现类的行为）和 `attributes`（实现类的数据）。

`C` 程序员专注于编写 `functions`。执行某些共同任务的动作组被组成 `functions`，而 `functions` 又被组合成程序。数据在 `C` 中固然重要，但其观点是，数据的存在主要是为了支持 `functions` 执行的操作。系统规范中的动词帮助 `C` 程序员确定实现该系统所需的 `functions` 集合。

`Java` 程序员专注于创建自己的名为 `classes`（类）和 `components`（组件）的自定义类型。每个 `class` 包含数据以及操作这些数据的 `functions` 集合。`Java` 类的数据组件被称为 `attributes`。

`Java` 类的 `function` 组件被称为 `methods`。就像 `int` 等内置类型的实例被称为 `variable`（变量）一样，自定义类型（即 `class`）的实例被称为 `object`（对象）。程序员使用内置类型作为构建自定义类型的“构建块”。

`Java` 的重点在于 `classes`（我们从中创建对象）而不是 `functions`。系统规范中的名词帮助 `Java` 程序员确定用于创建对象并以实现系统的 `classes` 集合，这些对象将协作工作来实现系统。

`Classes` 之于 `objects` 就像蓝图之于房子。我们可以从一张蓝图建造许多房子，也可以从一个 `class` 实例化许多 `objects`。`Classes` 也可以与其他 `classes` 建立关系。

例如，在银行的面向对象设计中，“银行柜员” `class` 需要与“客户” `class` 关联。这些关系被称为关联（associations）。我们将看到，当软件被封装成 `classes` 时，这些 `classes` 可以在未来的软件系统中被重用。相关的 `classes` 组通常被封装成可重用的组件。

你创建的每一个新 `class` 都有成为有价值的软件资产的潜力，你和其他程序员可以使用这些资产来加速并提高未来软件开发工作的质量——这是一个令人兴奋的可能性。

## Java 与 C、C++ 及 C# 的关系

`Java` 从 `C` 处继承了语法，从 `C++` 处继承了面向对象的特性。它不是 `C++` 的增强版。`Java` 既不向上兼容 `C++` 也不向下兼容。我想告诉你们的一点重要的一点是，`Java` 语言的设计并不是为了取代 `C++` 和 `C#`。另一种由微软开发的用于支持 `.NET` 框架的语言 `C#` 与 `Java` 关系密切，因为它们都共享 `C++` 和 `C` 风格的语法，支持分布式编程，并使用相同的对象模型。

## Java 的主要目标是实现 -

### 1. 安全性

当我们使用兼容 `Java` 的网络浏览器时，不存在病毒感染的威胁。此外，也没有恶意程序从本地机器收集隐私信息（如信用卡号、银行账户余额和密码）的威胁。

`Java` 在网络应用程序和计算机之间提供了一个防火墙。

### 2. 可移植性

`Java` 程序可以从一台计算机移植到另一台运行不同操作系统且具有不同硬件的计算机。

## Java 字节码

`Java` 编译器的输出是 `bytecode`（字节码）而不是机器码（`.class` 文件）。`bytecode` 是一高度优化的指令集，旨在由 `Java` 运行时系统执行，该系统被称为 `JVM`（Java 虚拟机）。

`JVM` 是解释 `bytecode` 的解释器。编译后的程序运行更快，但 `Java` 仍然使用解释器来实现可移植性，因此 `Java` 程序的运行速度稍慢。现在，通过 `Java` 编译器编译的程序可以在任何环境中运行，但每个平台都需要实现一个 `JVM`。`Java` 程序是被解释的。这也有助于提高安全性，因为每个 `Java` 程序的执行都受到 `JVM` 的控制。

## JIT (即时编译)

`JIT` 是 `JVM` 使用的翻译器，用于将 `bytecode` 翻译成实际的机器码。它不翻译整个 `bytecodes`，而是按需逐段翻译。

## Java 的版本

**Java 1**

- `JDK 1.0`
- `JDK 1.1`

**Java 2**

- `JDK 1.2`
- `JDK 1.3`
- `JDK 1.4`
- `JDK 1.5` 或 `JDK 5`
- `JDK 1.6` 或 `JDK 6`
- `Java 1.7` 或 `SE 7`
- `Java 8` (2014 年 4 月)

注释 1 - `JDK` (Java 开发工具包)

注释 2 - 旧版 Java 的许多特性在新版本中被弃用

## Java 可以开发的应用程序类型

### 1. 独立运行应用程序

独立应用程序是运行在我们本地计算机上的程序，类似于 `C` 或 `C++` 程序。

### 2. Applet

`applet` 是一种跨越网络传输并在客户端机器上兼容 Java 的网络浏览器（如 `Internet Explorer` 或 `Netscape Navigator`）中执行的小程序。`applet` 实际上是一个微型 Java 程序，通过网络动态下载。`applet` 程序存储在 Web 服务器上，并在客户端机器请求时传输到客户端。`applet` 无法像独立应用程序那样执行。`applet` 只能通过嵌入 HTML 页面来执行，类似于声音文件、图像文件或视频片段。

### 3. Web 应用程序

这些是运行在 Web 服务器上的程序。当我们在网络浏览器中指定 `URL`（通用资源定位符）访问网站时，网络浏览器会向特定的 Web 服务器发送请求。接收此请求后，服务器运行一个程序，该程序被称为 Web 应用程序。我们使用 `Java Servlets` 和 `JSP`（Java 页面）编写此类程序。

### 4. 分布式应用程序

`Java` 应用程序被分成运行在单独机器上的小程序。这些程序中的对象可以相互通信。这些应用程序被称为分布式应用程序。这允许两个不同计算机上的对象远程执行过程。为此使用了 `RMI`（远程方法调用）。

## 1. 简单

Java 的语法几乎与 C 和 C++ 相似，因此熟悉 C/C++ 的程序员不需要从头开始学习语法。但 C/C++ 中许多过于复杂或导致歧义的特性在 Java 中被移除了。

1. Java 不支持多继承，因为这个概念有点复杂并且可能导致歧义。
2. Java 不支持全局变量，这也导致了 C/C++ 程序中出现许多 bug。
3. Java 不使用指针，也不允许指针运算，由于其固有的复杂性，这是 C/C++ 程序中大多数 bug 的根源。
4. Java 不支持运算符重载，因为可能会导致混淆。
5. Java 中没有垃圾值的概念。我们必须在使用变量之前初始化它们。

## 2. 安全

Java 程序运行在 `JVM`（Java 虚拟机）中，其他部分无法访问它们。这很大地提高了安全性。由于这一特性，Java 程序很少挂起。这与频繁挂起的 C/C++ 程序大不相同。Java 的安全模型由三个主要部分组成：

1. 类加载器（Class loader）。
2. 字节码验证器（Bytecode Verifier）。
3. 安全管理器（Security Manager）。

Java 使用不同的类加载器从本地机器和远程机器加载类文件（可执行文件）。从远程机器加载的类（如 Applet 类）不允许读取或写入本地机器上的文件。这防止了恶意程序破坏本地文件系统。字节码验证器在类加载器完成工作后立即对字节码进行验证。它确保字节码是有效的 Java 代码。它几乎消除了 Java 程序执行某些恶意活动（如访问 `JVM` 外部的内存）的可能性。安全管理器控制许多关键操作，如删除文件、创建线程等。只有当 Java 程序具有足够的权限，这些操作才被允许，否则安全管理器将不允许这些操作并生成 `Security Exception`。

## 3. 可移植

Java 程序是平台无关的。它们遵循“一次编写，随运行”的策略。为 Windows 平台编写的 Java 程序只需拷贝字节码（`.class` 文件）即可运行在任何其他平台（Unix、Linux、Sun Solaris 等）上。不需要像 C/C++ 程序那样复制源代码并重新编译。这一特性使 Java 成为了一门强大的语言。只要机器上有 `JVM`，我们就可以在任何机器上运行字节码。`JVM` 本身是依赖平台的，但它让 Java 代码变得与平台无关。实际上是 `JVM` 将字节码转换为机器码并执行它们。

因此我们可以说 Java 是一种可移植的语言。另一个让 Java 高度可移植的特性是原生数据类型的长度固定，与平台无关。例如，Java 中的 `int` 始终是 4 字节。这与 C/C++ 不同，在 C/C++ 中，`int` 的大小在某些机器上可能是 2 字节，而在另一些机器上可能是 4 字节。

## 4. 面向对象

Java Almost 是一门纯面向对象的语言，但出于性能考虑，它支持原生数据类型如 `byte`、short、int、long、float、double、char、boolean。

## 5. 健壮

大多数程序失败源于两个原因之一：

1. 内存管理。
2. 运行时的异常情况。

在设计语言时，目标之一是确保 Java 程序尽可能健壮，即它们很少失败。因此，Java 特别重视上述两个因素。

在 Java 中，内存的分配和释放由语言本身处理，这消除了由于 C/C++ 中动态内存管理功能引起的许多问题。Java 还支持面向对象的异常处理特性来处理运行时发生的异常情况。这使得 Java 程序在发生异常情况后能够恢复并继续执行。

## 6. 多线程

Java 的设计是为了满足创建交互式网络化程序的现实世界需求。Java 提供了编写多线程程序的支持来实现这一目标。这允许程序员编写可以并发执行许多任务的程序。

例如，基于 GUI（图形用户界面）的应用程序可能正在监听用户事件并采取适当操作，另一个线程可能正在打印，另一个线程可能正在从网络上的某机器下载文件，这一切都是并发进行的。这导致了更好的性能和更高的 CPU 利用率。

在其他语言中编写多线程程序也是可能的，但那仅通过使用 `System` 调用实现的，而在 Java 中，可以通过语言自身的特性来实现。

## 7. 体系中立

程序员面临的主要问题之一是，无法保证如果我们今天写了一个程序，它明天是否还能运行——即使在同一台机器上。操作系统的升级、处理器升级以及核心系统资源的更改都可能导致程序发生故障。但 Java 程序的目标是“一次编写，随处运行”。

## 8. 解释型与高性能

Java 程序是解释执行的，但与其他解释器相比，它们的运行速度仍然很快。

## 9. 分布式



Java 是为互联网的分布式环境设计的。Java 为此内置了对各种基于 TCP/IP 协议的支持。事实上，使用 `URL` 访问资源类似于访问本地机器上的文件。Java 还具有远程方法调用（Remote Method Invocation）功能，这与远程过程调用（RPC）类似。这允许不同计算机上的对象远程执行过程。Java 为此提供了内置 API，称为 `RMI`。

## 10. 动态

每个 Java 类都是一个独立的执行单元。类只有在需要时才会被加载。Java 绑定方法的默认机制也是动态的（运行时绑定）。

## 运行独立的 Java

当 C 或 C++ 程序被编译时，它被直接翻译成机器码。

## 执行步骤

### 步骤 2

输入 `CD \ JAPRG` 并按回车

### 步骤 3

输入 `Edit Sum.Java` 并按回车

### 步骤 4

输入 Java 程序并点击 `FileSave` 然后点击 `FileExit`

### 步骤 5

输入 `javac Sum.Java` 并按回车编译。这将创建一个 `Sum.class` 文件。该文件被称为字节码。

### 步骤 6

输入 `java Sum` 并按回车运行。这将调用 `JVM`。

### 步骤 7

输入 `Exit` 然后按回车退出命令提示符。

**注意**：我们也可以通过上述步骤使用记事本运行 Java 程序，但我们将使用记事本代替 `Edit` 命令。输入 Java 程序后，在另存为对话框中选择“所有文件”，然后将其保存到文件夹 `C:\JAVAPRG`。要编译和运行，我们需要遵循上述步骤。

---

## Java 程序语法

```java
class <class name> {
    public static void main(String args[]) or (String [] args) {
        // - - - - - - - -
    }
}
```

---

## 第一个 Java 程序 - 两个数字相加 (Sum.Java)

```java
class Sum {
    public static void main(String args[]) {
        int a,b,sum;
        a = 5;
        b = 6;
        sum = a + b;
        System.out.print("Sum is " + sum);
    }
}
```

**输出**：Sum is 11

---

## 示例 2 程序 - 交换两个数字 (Swap.Java)

```java
class Swap {
    public static void main(String args[]) {
        int a=5,b=7;
        t = a;
        a = b;
        b = t;
        System.out.print("After Swap Values are " + a +"," + b);
    }
}
```

**输出**：After Swap Values are 7,5

---

## 概念

### 注释

有 3 类型的注释：

- 单行注释：`//`
- 多行注释：`/* */`
- 文档注释：`/** ... */`

### 程序规则

- 每个 Java 程序都必须包含一个类。在 Java 中，`main()` 方法只能定义在类内部。
- 源文件可以包含任意数量的类或接口定义，但最多只有一个公共类或接口。
- 源文件可能包含也不包含带有 `main()` 方法的类，但独立的 Java 程序始终从 `main()` 方法开始执行。想要开始执行的类必须在其中定义了 `main()` 方法。
- `main()` 方法必须具有以下签名：`public static void main(String args[])`
- 关键字 `public` 表示该方法可以从任何地方访问。`main()` 方法必须声明为 `public`，因为它是由代码调用的，而这些代码是 `JVM` 的且位于包含 `main()` 方法的类之外。
- 关键字 `static` 表示 `main()` 是一个类方法，可以在不创建任何对象的情况下调用，对象的创建只发生在 `main()` 方法内部。
- 在 `main()` 方法前的 `void` 关键字表示它不返回任何值。
- `main()` 方法接收一个参数，即 `String` 数组。数组的每个元素代表一个命令行参数。
- `System` 是一个预定义的类，提供对系统的访问，`out` 是连接到控制台的输出流。`print()` 方法可显示任何类型的信息。

### Java 程序的结构

所有 Java 源文件必须以 `.java` 结尾。Java 是一种大小敏感的语言。注意在上面的程序中，类 `Sum` 和 `System` 的首字母是大写的。最好使用与类相同的文件名保存 Java 程序，但这不是强制的。不过如果类被声明为 `public`，则必须将类保存到与类同名的文件中。一个文件只能包含一个公共类，但可以包含多个非公共类。如果文件包含多个类，则每个类被放在以类名命名的、使用 `.class` 扩展名的独立文件中。

- **文档部分**：文档部分包含一组注释行，提供了程序名称、作者以及程序员可能在以后阶段参考的其他细节。注释解释了算法的原理和内容。除了单行、多行注释外，Java 还使用了第三种风格的注释 `/**...*/`，即文档注释。
- **包声明**：源文件最多有一个包声明。如果存在包声明，它必须是 Java 程序中的第一个语句。只有注释可以出现在包声明之前。
- **导入语句**：源文件可以有零个或多个导入语句。导入语句就像 C/C++ 中的 `#include`。如果存在，所有导入语句必须位于包声明之后、类/接口定义之前。
- **接口语句**：接口（Interface）类似于类，但它包含一组方法声明。这也是一个可选部分，仅当我们希望在程序中实现多继承特性时才使用。
- **不包含 main 方法的类定义**：Java 程序可以包含多个类定义。类是 Java 程序中主要且基本的元素。这些类用于映射现实世界问题的对象。
- **包含 main 方法的类定义**：由于每个独立的 Java 程序都需要 `main` 方法作为起点，因此该类是 Java 程序的组成部分。一个简单的 Java 程序可能只包含这部分。`main` 方法创建各种类的对象并建立它们之间的通信。当 `main` 执行结束时，程序终止并将控制交回操作系统。

### 垃圾回收

Java 对象的内存分配是完全动态的，但 Java 不支持像 C/C++ 那样的指针算术。每当我们运行 Java 程序时，`JVM` 也会在后台运行另一个名为 `Garbage Collector`（垃圾回收器）的程序（线程）。垃圾回收器会检查 Java 对象。当 Java 对象不再被使用时，会被垃圾回收器回收，即为对象的内存被加入空闲内存池/堆并可以重复使用。这在很大程度上简化了程序员的任务，消除了许多由于不当使用指针算术和显式释放内存等功能导致的错误。

---

## 选择题

1. 下列哪个是应用程序 `main()` 方法有效定义？

   - (a) `public static void main();`
   - (b) `public static void main(String args);`
   - (c) `public static void main(String args[])`
   - (d) `public static void main(Graphics g);`
   - (e) `public static boolean main(String args[])`

2. 哪个组织开发了 Java 语言？

   - (a) Microsoft
   - (b) IBM
   - (c) Sun Microsytems Inc.
   - (d) AT&T

### 3. Java 属于以下哪种语言分类？

(a) 面向对象
(b) 过程化
(c) (a) 和 (b) 都是
(d) 以上都不是

### 4. 下面哪一描述是不正确的？

(a) Java 的垃圾回收是自动的。
(b) Java 提供对分布式应用的支持。
(c) 与 C/C++ 相比，Java 效率更高。
(d) 与 C/C++ 相比，Java 更安全。

### 5. 下面哪一描述是正确的？

(a) Java 是一种平台无关语言？
(b) Java 是一种面向对象的语言？
(c) Java 支持多线程。
(d) 以上都是。

**答案：** 1. (c) 2. (c) 3. (a) 4. (c) 5. (d)

### 题

1. 解释 Java 虚拟机 (`JVM`) 的工作原理。
2. `C++` 和 `Java` 之间有什么区别？
3. "APPLET（小程序）" 和 "APPLICATION（应用程序）" 区别。
4. `Java` 的缺点。
5. 垃圾回收是如何工作的？
6. 什么是 `BYTE Code（字节码）`？
7. `java` 是完全面向对象的编程吗？如果不是，为什么？
8. `Java` 应用/程序的不同类型有哪些？
9. Java 可执行文件的扩展名是什么？
10. Java 源文件/程序文件的扩展名是什么？
11. 使用什么命令编译 Java 程序？
12. 哪个组织开发了 `Java` 语言？
13. 是什么让 `Java` 具有平台无关性？
14. 为什么 `Java` 比 `C/C++` 更安全？
15. 为什么 `Java` 比 `C` 语言更健壮？
16. 什么是分布式应用程序？
17. 描述 `Java` 的任何特性。
18. 描述编译和运行程序所需的步骤。
19. `Java`受欢迎的主要原因有哪些？
20. 为什么 `C/C++` 的许多特性在 `Java` 中被删除了？列举其中一些特性。
21. 列举 `Java` 中三种类型的注释。
22. 列出 `C` 和 `Java` 之间的 10 个主要区别。
23. 描述典型 `Java` 程序的结构。

## 编程练习

1. 编写一个计算整数平均值的程序。
2. 编写一个程序在不使用第三方变量的情况下交换两个数字。
3. 编写一个程序将小时、分钟和秒转换为总秒数。
4. 编写一个程序计算给定圆的面积和周长。

## 第二章 Java 语言

### 标记 (Tokens)

最小的单元被称为标记，如 `keywords（关键字）`、`identifiers（标识符）`、`strings（字符串）` 和 `Operators（运算符）`。

A. `Keywords（关键字）`是语言的保留名称，不能用变量、函数等的名称。
B. `Identifier（标识符）`是指变量、数组、类、接口等的名称。
C. `Constants/Literals（常量）`是指我们在程序中无法改变的固定值。
D. `Operators（运算符）`是作用于 `variable（变量）` 和 `constants（常量）` 并形成 `expression（表达式）` 的特殊符号。
E. `Separators（分隔符）`是用于分隔语句的特殊字符，如 `()`、`{}`、`[]`、`;`、`,`。

### 关键字 (Keywords)

`abstract`, `assert`, `boolean`, `break`, `byte`, `case`, `catch`, `char`, `class`, `default`, `do`, `double`, `else`, `extends`, `final`, `finally`, `float`, `goto`, `if`, `if`, `implements`, `import`, `instanceof`, `int`, `interface`, `long`, `native`, `package`, `private`, `public`, `return`, `short`, `strictfp`, `super`, `synchronized`, `this`, `throw`, `throws`, `transient`, `try`, `void`, `volatile`.

Java 提供了丰富的运算符算集。运算符将常量、变量和子表达式组合成表达式。Java 中的大多数运算符的行为与 C/C++ 相似，但有少量不同之处，本文将在此介绍这些差异。

运算符可以分类为：

### 算术运算符 (+, -, *, /, %)

- 这些运算符与 C/C++ 中的相同。
- `%` 运算符也可以作用于浮点数。
- 当二元运算符应用于两个不同类型的操作数时，低类型的操作数会在求值之前转换为高类型，结果的类型将与高类型操作数的类型相同。
- 对于 `int` 类型，除以零或对零取模会导致 `ArithmeticException`（运行时错误），但对于浮点数则不会。
- 当我们对 `int` 应用算术运算符且结果超出了 `int` 的范围时，额外的高位将被截断，这个新值将赋值给接收结果的变量；但在浮点类型中，如果发生溢出将导致 `Infinity` 或 `–Infinity`，如果发生下溢将导致 `0`。

### 递增和递减运算符 (++, --)

- 这些运算符与 C/C++ 中的相同。

```java
int a=5,b;
b = ++a*++a;
System.out.print(b); //42
a = 5;
System.out.print(++a*++a); //42
```

### 关系运算符 (<, >, <=, >=, instanceof)

- 这些运算符与 C/C++ 相同，但 `<`, `<=`, `>`, `>=` 不能应用于布尔类型和引用类型。

### instanceof 运算符

`instanceof` 运算符用于测试对象的类。`instanceof` 运算符的通用形式为：

```java
if(object instanceof type)
```

在这里，`object` 是一个类的实例，`type` 是类类型。如果 `object` 是指定类型的实例或指定类型任何子类的实例，则 `instanceof` 运算符返回 `true`，否则结果为 `false`。

### 赋值运算符 (=, +=, -=, *=, /=, %)

- 这些运算符与 C/C++ 中的相同。

### 等于运算符 (=, !=)

- 这些运算符与 C/C++ 中的相同。

### 逻辑运算符 (&&, ||, !)

- 这些运算符与 C/C++ 中的相同。

### 条件运算符 (? :)

- 该运算符与 C/C++ 中的相同。

### 位运算运算符 (&, |, ^, ~, <<, >>, >>>)

- 这些运算符与 C/C++ 相同，位移运算符除外。位移运算符仅适用于整数类型。

### 左移 (<<) 运算符

为了得到 `<<` 运算符的结果，左侧操作数中的位将根据右侧操作数指定的向左移动，右侧的空位将用零填充。左移 1 位等于乘以 2。结果的符号可能与左侧操作数的符号不同。这可能是因为符号取决于最左位，该位可能会从 0 变为 1 或从 1 变为 0，从而改变符号。

示例 `b = a << 2;`。为了得到 `b` 的值，将 `a` 中的位左移 2 位，并用零填充右侧 2 位。

### 右移 (>>) 运算符（有符号）

为了得到 `>>` 运算符的结果，左侧操作数中的位将根据右侧操作数指定的向右移动，左侧的空位将用符号位填充。右移 1 位等于除以 2。该运算符永远保持结果的符号，即它与左侧操作数的符号相同。

示例 `b = a >> 2;`。为了得到 `b` 的值，将 `a` 中的位右移 2 位，并用符号填充右侧 2 位（如果 `a` 为正则填充 0，如果 `a` 为负则填充 1）。

### 零填充右移 (>>>) 运算符（无符号）

为了得到 `>>>` 运算符的结果，左侧操作数中的位将根据右侧操作数指定的向右移动，左侧的空位将用 0 填充。右移 1 位等于除以 2。如果发生了位移，结果将始终为正数，因为最右侧位将变为零。

示例 `b = a >>> 2;`。为了得到 `b` 的值，将 `a` 中的位右移 2 位，并用 0 填充右侧 2 位。

![black_star_logo](img/image01215.jpeg)
![black_star_logo](img/image01215.jpeg)
![black_star_logo](img/image01215.jpeg)

### 运算符的优先级：

| 级别 | 运算符 | 描述 | 结合性 |
| :--- | :--- | :--- | :--- |
| 1 | `()[]` | 函数调用、下标、直接成员 | 从左到右 |
| 2 | `++--~!!` | 递增、递减、位取反、逻辑取反 | 从右到左 |
| 3 | `*/%` | 乘、除、取模 | 从左到右 |
| 4 | `+-` | 加、减 | 从左到右 |
| 5 | `>>><<` | 位右移、位左移、有符号右移、零填充右移 | 从左到右 |
| 6 | `>>=<<=instanceof` | 大于、小于、大于等于、小于等于 | 从左到右 |
| 7 | `!=` | 等于、不等于 | 从左到右 |
| 8 | `&` | 位与 | 从左到右 |
| 9 | `^` | 位异或 | 从左到右 |
| 10 | `\|` | 位或 | 从左到右 |
| 11 | `&&` | 逻辑与 | 从左到右 |
| 12 | `||` | 逻辑或 | 从左到右 |
| 13 | `?:` | 条件（三元运算符） | 从左到右 |
| 14 | `-*&=^>>>==` | 加赋值、减赋值、乘赋值、除赋值、位与赋值、位异或赋值、位移赋值 | 赋值 |

| 符号 | 名称 | 用途 |
| :--- | :--- | :--- |
| `()` | 圆括号 | 参数定义和调用 |
| `{}` | 大括号 | 初始化数组、定义作用域 |
| `[]` | 中括号 | 声明数组 |
| `;` | 分号 | 终止语句 |



| `,` | 逗号 | 分隔标识符 |
| `.` | 点 | 分隔包名与类 |

![black_star_logo](img/image01215.jpeg)

## 数据类型

Java 数据类型大致可分为两类：

1. 基本数据类型 / 简单数据类型

Java 是一种面向对象的语言，但基本数据类型不是对象，出于性能考虑保留了它们。它们是 Java 中定义的所有类型的基础。Java 是一种强类型语言。

### 数值类型

#### 整数类型

- `byte` (1 字节)：范围 -128 到 127
- `short` (2 字节)：范围 -32768 到 32767
- `int` (4 字节)：范围 -2147483648 到 2147483647
- `long` (8 字节)：范围 -9223372036854775808 到 9223372036854775807

包含 `byte`、`short`、`int` 的表达式会自动转换为 `int`。

#### 浮点数类型

- `float` (4 字节)：范围 1.401298464324817E-45f 到 3.4028234663852886E38f
- `double` (8 字节)：范围 4.9E-324d 到 1.7976931348623157E308d

#### 布尔类型

- `boolean`

#### 字符类型

- `char` (2 字节)：范围 0 到 65535

注意：Unicode 集合的前 128 个字符与 7 位 ASCII 字符集相同，Unicode 的前 256 个字符对应 256 扩展 ASCII（8 位 ISO Latin-1）字符集。

Java 字符也可以用于整数表达式。当字符作为整数表达式的一部分时，使用其 Unicode 值。

2. 非基本数据类型 / 派生数据类型或引用

## 引用数据类型

引用数据类型也称为派生数据类型，因为它们源自原始数据类型。

### 类 (Classes)

1. 内置/库类
2. 用户定义类

### 接口 (Interfaces)

1. 内置/库接口
2. 用户定义接口

### 数组 (Arrays)

数组在 Java 中也被视为对象。

## Java 的自动转换

当满足以下条件时发生：

1. 两个类型兼容。
2. 目标类型大于源类型。

## 变量 (Variables)

变量是用于存储值的内存位置名称。在向其中存储值之前，必须声明变量。或者变量是主内存内部的内存位置，我们可以在其中存储数据或值。

有三种变量：

### 局部变量 (Local Variables)

局部变量用于块或方法内部。局部变量（也称为自动变量）默认不初始化。局部变量在使用之前必须显式初始化，否则会出现编译时错误“变量可能未被初始化”。

#### 示例

```java
int a, b = 5;

if (b > 2) {
    a = b;
}

System.out.print(a);
```

在上述程序中，如果 `if` 条件为假，则 `a` 的值未定义，因此编译器将给出错误“变量 a 可能未被初始化”。

在 Java 中，我们不能在内部块中定义与外部块同名的变量。

```java
int a = 5;
{
    int a = 7; // Error
}
```

### 实例变量 (Instance Variables)

实例变量用于定义对象的属性或状态。

### 类变量 (Class Variables)

类变量用于定义该类所有对象通用的属性/状态。

## Math 类的库方法

| 方法 | 说明 |
| :--- | :--- |
| `public static double sin(double x);` | 返回弧度角 x 的正弦 |
| `public static double cos(double x);` | 返回弧度角 x 的余弦 |
| `public static double tan(double x);` | 返回弧度角 x 的正切 |
| `public static double asin(double x);` | 返回正弦对应的角度 x |
| `public static double acos(double x);` | 返回余弦对应的角度 x |
| `public static double atan(double x);` | 返回正切对应的角度 x |
| `public static double toRadians(double x);` | 将度 x 转换为弧度 |
| `public static double toDegrees(double x);` | 将弧度 x 转换为度 |
| `public static double exp(double x);` | 返回 e 的 x 次方 |
| `public static double log(double x);` | 返回 x 的自然对数 |
| `public static double log10(double x);` | 返回 x 以 10 为底对数 |
| `public static double sqrt(double x);` | 返回 x 的平方根 |
| `public static double ceil(double x);` | 返回大于等于 x 的最小整数（向上取） |
| `public static double floor(double x);` | 返回小于等于 x 的最大整数（向下取） |
| `public static double rint(double x);` | 返回 x 舍入后的值 |
| `public static double atan2(double x, double y);` | 返回正切值为 x/y 的角度 |
| `public static double pow(double x, double y);` | 返回 x 的 y 次方 |
| `public static int round(float x);` | 返回 x 的 int 类型舍入值 |
| `public static long round(double x);` | 返回 x 的 long 类型舍入值 |
| `public static double random();` | 返回 0 到 0.9999 之间的随机数 |

*(注：表格后续部分原文存在重复和乱码，已按逻辑处理)*

### 选择题

1. Java 中关键字 `goto` 和 `const` 的状态是？
   (a) 保留字
   (b) 使用中
   (c) 未使用
   (d) 以上都不是

2. 以下哪个不是 Java 关键字？
   (a) `class`
   (b) `interface`
   (c) `extends`
   (d) `unsigned`

3. 以下哪个是有效的标识符？
   (a) `2var`
   (b) `$var`
   (c) `class`
   (d) `int`

4. 以下哪个是 Java 中的字面量？
   (a) `true`
   (b) `false`
   (c) `null`
   (d) 以上都是

5. 以下哪些关键字在 Java 中未被使用？
   (a) `goto`
   (b) `const`
   (c) `goto` 和 `const`
   (d) 以上都不是

6. 以下哪些是 Java 中的分隔符？
   (a) `,`
   (b) `;`
   (c) `{}`
   (d) 以上都是

7. 以下哪个不是 Java 中的基本数据类型？
   (a) `int`
   (b) `float`
   (c) `String`
   (d) `boolean`

8. Java 中数据类型 `int` 的大小是多少？
   (a) 2 字节
   (b) 4 字节
   (c) 未定义
   (d) 2 字节或 4 字节

**答案：**

1. (b,e) 2. (d) 3. (b) 4. (a)
5. (d) 6. (b,e) 7. (c) 8. (b)

![black_star_logo](img/image01215.jpeg)

### 理论题

1. 为什么 Java 不是 100% 纯面向对象的语言？
2. Java 中的基本类型有哪些？
3. 写出 Java 源文件中可能出现的四个顶层元素。
4. 在 `package` 语句之前还可以出现哪些语句？
5. 写出三个用作字面量（literals）的 Java 关键字。
6. 写出两个在语言中没有使用的 Java 关键字。
7. Java 中哪些基本数据类型在 C 语言中不存在？
8. 写出 Java 中的三种变量。
9. 简述标识符的命名规则。
10. Java 程序中注释的作用是什么？
11. 列出任意数值数据类型及其范围。
12. Java 数组与 C 语言数组有何不同？
13. 什么是标记（tokens）？简述其类型。
14. 什么是字面量（literals）？举例说明。
15. 哪些不同的数据类型？详细描述。

## 编程练习

1. 编写一个程序展示所有位运算符的使用。
2. 编写一个程序展示显式转换和隐式转换。
3. 编写一个程序求解不同数据类型的方程并显示结果。
4. 编写一个程序证明内部作用域变量与外部作用域变量不同。
5. 编写一个程序计算面积（使用 `final` 声明常量）。
6. 编写一个程序将 `char` 转换为 Unicode。
7. 编写一个程序进行 `int` 到 `float` 的类型转换。
8. 编写一个程序计算两个 `float` 数的取模（`%`）。
9. 编写一个程序求二次方程的根。

![11](img/image01216.jpeg) ![11](img/image01216.jpeg) ![11](img/image01216.jpeg)

![STAR-LOGO-2013](img/img/image0113.jpeg)

## 第 3 章：控制语句

### 引言

控制语句用于改变执行流。Java 的控制语句可以分为三类。

#### 1. 选择语句（选择控制结构）

选择语句允许程序根据表达式的结果或变量的状态，从不同的执行路径中选择任意一条路径。

1. `if`
2. `if else`
3. `嵌套 if`
4. `if-else-if`
5. `switch`

**(a) `if` 的语法**

```java
if (condition) {
    statements;
}
```

**(b) `if else` 的语法**

```java
if (condition) {
    statements;
} else {
    statements;
}
```

**(c) 嵌套 if 的语法**

```java
if (condition) {
    if (condition) {
        statements;
    } else {
        statements;
    }
} else {
    statements;
}
```

**(d) `if-else-if` 阶字的语法**

```java
if (condition1) {
    statements;
} else if (condition2) {
    statements;
} else if (condition3) {
    statements;
} else {
    statements;
}
```

**(e) `switch case` 的语法**

```java
switch (expression) {
    case 1:
        statement 1 sequence;
        break;
    case 2:
        statement 2 sequence;
        break;
    case 3:
        statement 3 sequence;
        break;
    case n:
        break;
    default:
        default statement sequence;
}
```

### 示例 3.1 求两个数最大值的程序 (Max.Java)

```java
class Max {
    public static void main(String args[]) {
        int a, b, max;
        a = 0;
        b = 20;
        if (a > b) {
            max = a;
        } else {
            max = b;
        }
        System.out.println("Max of two numbers is " + max);
    }
}
```

**输出：**

`Max of two numbers is 20`

#### 2. 迭代语句（循环控制结构）

循环是一个允许我们重复单条语句或一组语句 n 次的过程。

1. `for`
2. `while`
3. `do while`

**(a) `for` 循环的语法**

```java
for (initialize; condition; increment/decrement) {
    statements;
}
```

**(b) `while` 循环的语法**

```java
initialize;
while (condition) {
    statements;
    increment/decrement;
}
```

**(c) `do while` 循环的语法**

```java
initialize;
do {
    statements;
    increment/decrement;
} while (condition);
```

条件可以是任何布尔表达式。只要条件表达式为真，循环体就会被执行。当 `condition` 变为假时，控制将立即传递到循环后的下一行代码。

### 示例 3.2

```java
class Loop1 {
    public static void main(String args[]) {
        int n = 5;
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print(j);
                System.out.println();
            }
        }
    }
}
```

**输出：**

```
1
12
123
1234
12345
```

### 3. 跳跃语句

它允许我们的程序以非线性的方式工作。

1. `break`
2. `labeled break`（标签中断）
3. `continue`
4. `labeled continue`（标签继续）
5. `return`

* 大多数语句的语法与 C/C++ 中对应的语句相同。但存在一些显著差异。
* `if`、`while` 和 `do` 语句中使用的条件表达式必须是有效的布尔表达式，即它们的值应该是 `true` 或 `false`。我们不能像 C/C++ 那样用 `0` 代替 `false` 或用非零值代替 `true`。
* Java 没有任何 `goto` 语句，尽管 `goto` 是该语言中的一个关键字。Java 提供了 `labeled break` 和 `labeled continue` 语句，它们通常被称为 `goto` 的文明形式，因为它们应该是 `goto` 语句更好的替代方案。
* 在 Java 中，`switch` 表达式可以是除 `long` 以外任何整数表达式，即 `switch` 表达式的类型可以是 `byte`、`short`、`char` 或 `int`。但 Java 的 `int` 是 4 字节，与 C/C++ 中 `long` 的大小相同。
* `case` 标签像 C/C++ 一样是常量表达式，但 `case` 标签的值必须在 `switch` 表达式类型的范围内，否则程序将无法编译。
* `labeled break` 语句用于终止由 `break` 语句中指定的标签的块。与简单的 `break` 语句不同，我们可以终止任何块。例如，可以从深度嵌套的 `for` 循环内部终止最外层循环。`break` 语句也可以用于终止简单块（即该块不需要是循环或 `switch` 语句）。
* `labeled continue` 语句指定要继续的外层循环的标签。该标签不需要对应于最近的外层循环。

#### 跳跃语句示例

**(a) break**

```java
for (int i = 1; i <= 10; i++) {
    if (i == 5)
        break; // 当 i 为 5 时终止循环
    System.out.print(i);
}
```

输出：`1 2 3 4`

**(b) labeled break**

```java
boolean t = true;
first: {
    second: {
        third: {
            System.out.println("Before the break");
            if (t) break second; // 跳出 second 块
            System.out.println("This will not execute");
        }
        System.out.println("This will not execute");
    }
    System.out.println("This is after second block");
}
```

输出：`Before the break is after second block`

**(c) continue**

```java
for (int i = 0; i < 10; i++) {
    System.out.print(i + " ");
    if (i % 2 == 0) continue;
    System.out.println();
}
```

注意：使用 `%` 运算符检查 `i` 是否为偶数。如果它是偶数，循环将继续执行而不打印新行。

输出：

```
0 1
2 3
4 5
6 7
8 9
```

**(d) labeled continue**

```java
outer: for (int i = 0; i < 5; i++) {
    for (int j = 0; j < 5; j++) {
        if (j > i) {
            System.out.println();
            continue outer;
        }
        System.out.print("\t" + (i * j));
    }
}
```

输出：

```
0
0	1
0	1	2
0	1	2	4	6
0	3	6	9	12
0	4	8	12	16
```

**(e) return**

```java
int sum(int a, int b) {
    int c;
    c = a + b;
    return c;
}
```

### 多选题：



# 练习题

## 1. 变量定义与有效性判断

给定下面定义的变量：

```java
int one = 1;
int two = 2;
char initial = '2';
boolean flag = true;
```

以下哪是有效的？

- (a) `if( one )`
- (b) `if( one = two )`
- (c) `If( one == two )`
- (d) `if( flag )`
- (e) `switch( one )`
- (f) `switch( flag )`
- (g) `switch( initial )`

## 2. Switch 语句输出

如果下面代码中的 `val = 1`：

```java
switch( val )
{
    case 1: System.out.print( "P" );
    case 2:
    case 3: System.out.print( "Q" );
        break;
    case 4: System.out.print( "R" );
    default: System.out.print( "S" );
}
```

哪些值会被打印？

- (a) P
- (b) Q
- (c) R
- (d) S

## 3. If-Else 逻辑判断

假设 `val` 对于下面的代码已定义为正整数：

```java
if( val > 4 )
    System.out.println( "Test A" );
else if( val > 9 )
    System.out.println( "Test B" );
else
    System.out.println( "Test C" );
```

哪些 `val` 值会导致打印 "Test C"：

- (a) `val < 0`
- (b) `val` 在 0 到 4 之间
- (c) `val` 在 4 到 9 之间
- (d) `val > 9`
- (e) `val = 0`
- (f) 没有满意的 `val` 值

## 4. While 循环输出

对于代码：

```java
m = 0;
while( m++ < 2 )
    System.out.println( m );
```

以下哪些被打印到标准输出？

- (a) 0
- (b) 1
- (c) 2
- (d) 3
- (e) 什么都没有打印并抛出异常

## 5. 标签循环与 Continue

考虑下面的代码片段：

```java
outer: for( int i = 1; i < 3; i++ )
inner: for( j = 1; j < 3; j++ )
{
    if( j == 2 )
        continue outer;
    System.out.println( "i = " + i + ", j = " + j );
}
```

哪些会被打印到标准输出？

- (a) i = 1, j = 1
- (b) `i = 1, j = 2`
- (c) `i = 1, j = 3`
- (d) `i = 2, j = 1`
- (e) `i = 2, j = 2`
- (f) `i = 2, j = 3`
- (g) `i = 3, j = 1`
- (h) `i = 3, j = 2`

**答案：** 1(c,d,e,f,g) 2(a,b) 3(b) 4(b,c) 5(a,d)

---

# 理论题

1. Java 有 "goto" 吗？
2. 什么是标签（labeled loops）。

---

# 编程练习

1. 编写一个程序检查给定年份是否为闰年。
2. 编写一个程序打印给定月份的天数（使用 `switch`）。
3. 编写一个程序打印斐波那契数列。
4. 编写一个程序检查给定数字是否为质数。
5. 编写一个菜单驱动的程序来计算两个数的加、减、乘、除。
   - 1 加
   - 2 减
   - 3 乘
   - 4 除
   - 5 退出（提示：使用 `do while` 和 `switch`）
6. 编写一个程序打印数字的反序。（提示：1234 结果为 4321）。
7. 编写一个程序找到给定三个数中的最大值。
8. 编写一个程序使用跳转语句打印前 10 个偶数。

![Images/image01217.jpeg] ISBN 13: 978-1500730413

![Images/image01213.jpeg]

---

# 第 4 章：Scanner 类与数组

## 引言

## Scanner 类

这是 Java 在 JDK 1.5/6/7 版本中添加的新类，用于从用户获取基本数据类型的输入。使用此类获取输入非常简单，因为我们只需要创建该类的对象并调用特定方法。该类位于 `java.util` 包中。

| 方法签名 | 说明 |
| :--- | :--- |
| `public java.util.Scanner(java.io.InputStream);` | 构造方法 |
| `public java.util.Scanner(java.io.File) throws java.io.FileNotFoundException;` | 构造方法 |
| `public java.util.Scanner(java.lang.String);` | 构造方法 |
| `public void close();` | 关闭扫描器 |
| `public boolean hasNext();` | 判断是否有下一个 token |
| `public java.lang.String next();` | 输入不包含空格的字符串 |
| `public java.lang.String nextLine();` | 输入可能包含空格的字符串 |
| `public boolean hasNextBoolean();` | 判断下一个是否为 boolean |
| `public boolean nextBoolean();` | 读取 boolean |
| `public boolean hasNextByte();` | 判断下一个是否为 byte |
| `public byte nextByte();` | 读取 byte |
| `public boolean hasNextShort();` | 判断下一个是否为 short |
| `public short nextShort();` | 读取 short |
| `public boolean hasNextInt();` | 检查输入缓冲区中的下一个值是否为 `int` |
| `public int nextInt();` | 输入一个整数 |
| `public boolean hasNextLong();` | 判断下一个是否为 long |
| `public long nextLong();` | 读取 long |
| `public boolean hasNextFloat();` | 判断下一个是否为 float |
| `public float nextFloat();` | 读取 float |
| `public boolean hasNextDouble();` | 判断下一个是否为 double |
| `public double nextDouble();` | 读取 double |

### 示例 4.1

```java
import java.util.*;

class SumInput {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        int a, b, sum;
        System.out.print("Enter number");
        a = sc.nextInt();
        System.out.print("Enter 2nd number");
        b = sc.nextInt();
        sum = a + b;
        System.out.println("Sum is " + sum);
    }
}
```

**输出：**

```
Enter number 45
Enter 2nd number 55
Sum is 100
```

---

## 数组

Java 数组是相同类型变量或数据项目的有序集合。Java 允许任何维度的数组。Java 数组与 C/C++ 有些不同。我们不能在声明时指定数组的大小。内存分配总是动态的。Java 中的每个数组都被视为一个对象，并有一个特殊的属性 `length`，该属性指定数组中的元素个数。

---

## 一维数组

### 声明

`type array_name[];` // 声明时不发生内存分配。

或者

`type[] array_name;`

需要注意的是，声明实际上并没有创建数组。它只是声明了一个可以指向数组对象的引用。

```java
int a1[], a2;
int[] a3, a4;
```

这两个声明将 `a1`、`a3` 和 `a4` 声明为指向 `int` 数组的引用变量，但变量 `a2` 不能指向 `int` 值的数组。它仅仅是一个 `int` 变量。当 `[]` 符号跟随类型之后时，声明中的所有变量都是数组。否则，`[]` 符号必须跟随声明中的每个单独数组名。

### 借助 `new` 运算符进行内存分配

`array_name = new type[SIZE];` // `SIZE` 可以是常量也可以是变量。

![Images/image1218.jpeg]

1. 数组的所有元素将初始化为零，但要用不同值初始化数组，可以这样做：`int a[] = {5, 7, 1};`
2. 数组索引从 0 开始。
3. 在 Java 中，数组存储大小在一个名为 `length` 的变量中。我们可以通过属性 `array_name.length` 获取数组长度。
4. `a = b = new int[5];` 在上述步骤中，`new` 创建了一个数组，该数组的引用将存储在 `b` 中。因此 `a` 和 `b` 指向同一个数组。赋值引用不会创建副本。

### 示例 4.2 数组存储的所有数字之和

```java
class SumArr {
    public static void main(String args[]) {
        int a[] = {10, 50, 20, 30};
        int n = a.length, sum = 0;
        for (int i = 0; i < n; i++) {
            sum += a[i];
        }
        System.out.println("Sum of numbers is " + sum);
    }
}
```

**输出：**

```
Sum of numbers is 150
```

### 示例 4.3 使用选择排序法对数组进行排序

```java
import java.util.Scanner;

class Sort {
    public static void main(String args[]) {
        int n;
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter many elements");
        n = sc.nextInt();
        int a[] = new int[n];
        // 输入数组
        for (int i = 0; i < n; i++) {
            System.out.print("Enter element " + (i + 1) + " ");
            a[i] = sc.nextInt();
        }
        // 排序
        for (int i = 0; i < n - 1; i++) {
            for (int j = i + 1; j < n; j++) {
                if (a[i] > a[j]) {
                    int t = a[i];
                    a[i] = a[j];
                    a[j] = t;
                }
            }
        }
        // 输出
        for (int i = 0; i < n; i++) {
            System.out.println(a[i]);
        }
    }
}
```

---

## 二维数组

### 内存分配

```java
array_name = new type[ROWS][COLUMNS];
```

// `ROWS` & `COLUMNS` 可以是常量或变量

到目前为止，我们讨论了可以存储值列表的数组变量。在某些情况下，必须存储一个值表。考虑以下数据表，它显示了三名销售人员三种商品的销售额。

该表总共 12 个值，每行 3 个。我们可以将此表看作由四行三列组成的矩阵。每行代表特定销售人员的销售额，每列代表特定商品的销售额。

### 示例 4.4 打印矩阵转置的程序

```java
import java.util.*;

class Transpose {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        int r, c;
        System.out.print("Enter how many rows");
        r = sc.nextInt();
        System.out.print("Enter how many cols.");
        c = sc.nextInt();

        int m[][] = new int[r][c];
        // input
        for (int i = 0; i < r; i++)
            for (int j = 0; j < c; j++) {
                System.out.print("Enter" + (i + 1) + "," + (j + 1));
                m[i][j] = sc.nextInt();
            }
        // transpose
        for (int i = 0; i < c; i++) {
            for (int j = 0; j < r; j++)
                System.out.print(m[j][i] + "\t");
            System.out.println();
        }
    }
}
```

### 示例 4.5 将两个矩阵相乘得到第三个矩阵的程序

```java
import java.util.*;

class MatrixMult {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        int r1, c1;
        System.out.print("Enter how many rows");
        r1 = sc.nextInt();
        System.out.print("Enter how many cols.");
        c1 = sc.nextInt();
        int r2, c2;
        System.out.print("Enter how many rows");
        r2 = sc.nextInt();
        System.out.print("Enter how many cols.");
        c2 = sc.nextInt();
        if (c1 != r2) {
            System.out.println("Can't mult");
            System.exit(1);
        }
        int m1[][] = new int[r1][c1];
        // input m1
        for (int i = 0; i < r1; i++)
            for (int j = 0; j < c1; j++) {
                System.out.print("Enter" + "element " + (i + 1) + "," + (j + 1));
                m1[i][j] = sc.nextInt();
            }
        int m2[][] = new int[r2][c2];
        // input m2
        for (int i = 0; i < r2; i++)
            for (int j = 0; j < c2; j++) {
                System.out.print("Enter" + "element " + (i + 1) + "," + (j + 1));
                m2[i][j] = sc.nextInt();
            }
        int m3[][] = new int[r1][c2];
        // matrix mult
        for (int i = 0; i < r1; i++)
            for (int j = 0; j < c2; j++)
                for (int k = 0; k < c1; k++)
                    m3[i][j] += m1[i][k] * m2[k][j];
        // Output m3
        for (int i = 0; i < r1; i++) {
            for (int j = 0; j < c2; j++)
                System.out.print(m3[i][j] + "\t");
            System.out.println();
        }
    }
}
```

---

## 3. 可变大小数组

数组将多维数组视为“数组的数组”，可以按照如下方式声明二维数组：

```java
int arr[][] = new int[4][];
arr[0] = new int[1];
arr[1] = new int[2];
arr[2] = new int[3];
arr[3] = new int[4];
```

这意味着数组共有 4 行，其列数从 1 开始逐递增加 1。这就是它们在内存中的表示方式（内存分配）。



**注意-1**：数组的所有元素都将自动初始化为零，但为了用不同的值初始化数组，我们可以在声明时进行初始化。数组的声明、内存分配和初始化步骤可以合并为：

```java
int a[][]={ {5,7,1}, {1,7,9}, {4,5,7}, {1,1,1} };
```

**注意-2**：在上述数组中，`a.length` 将显示行数，即 4；`a[0].length` 将显示第 0 行的列数，即 3。

## 命令行参数

有时我们希望在运行程序时向程序传递信息。这通过向 `main()` 方法传递命令行参数来实现。命令行参数是在执行程序时直接跟在程序名称后面的信息。

要在 Java 程序内部访问命令行参数，我们必须使用传递给 `main()` 的 `String` 数组。

JVM 调用 `main()` 方法并将命令行参数作为字符串数组传递给它。在示例中，数组的长度（即命令行参数的数量）通过 `length` 属性获取。

`for` 循环在控制台/显示器上显示命令行参数。

## 示例 4.6 从命令行参数输入名称的程序

```java
class Hello
{
    public static void main(String args[])
    {
        for(int i=0;i<args.length;i++)
    }
}
```

```
System.out.println("Hello " + args[i]);
}
```

`javac Hello.java`

`java Hello Ravi Ajay Vijay`

**输出：**

```
Hello Ravi
Hello Ajay
Hello Vijay
```

### 示例 4.7 通过命令行参数输入数字并打印它们的和的程序。

```java
class SumCmd {
    public static void main(String args[]) {
        int sum=0;
        for(int i=0;i<args.length;i++)
            sum+=Integer.parseInt(args[i]);
        System.out.println("Sum is " + sum);
    }
}
```

`javac SumCmd.java`

`java SumCmd 5 6`

**输出：** 

```
Sum is 11
```

### 示例 4.8 对从命令行输入的数组进行排序的程序。

```java
class SortCmd {
    public static void main(String args[]) {
        int n=args.length;
        int a[ ]=new int[n];
        //将 args 数组复制到 a 数组
        for(int i=0;i<n;i++)
            a[i] = Integer.parseInt(args[i]);
        //排序
        for(int i=0;i<n-1;i++)
            for(int j=i+1;j<n;j++)
                if(a[i]>a[j]) {
                    int t=a[i];
                    a[i]=a[j];
                    a[j]=t;
                }
        //输出数组
        for(int i=0;i<n;i++)
            System.out.print(a[i]+"\t");
    }
}
```

`javac SortCmd.java`

`java SortCmd 5 4 1 3 2`

**输出：**

```
1 2 3 4 5
```

### 多选题：

1. 如果将 `MyProg.java` 编译为应用程序并在命令行中通过 `java MyProg I like` 运行，那么 `main()` 方法内部 `args[1]` 的值是什么？

   a) `MyProg`

   b) `"I"`

   c) `"like"`

   d) `4`

   e) 在赋值前为空

2. 在声明 `char[] c = new char[100];` 后，`c[50]` 的值是？

   a) `50`

   b) `49`

   c) `'0'`

   d) `' '`

3. 下列哪些是整数二维数组的合法声明？

   a) `int[5][5]a = new int[];`

   b) `int a = new int[5,5];`

   c) `int[][]a = new int[5][5];`

   d) `int[][]a = new [5]int[5];`

4. 下列哪些是初始化包含 7 个值的数组 `"high"` 的正确方法？

   a) `int high = { 24, 23, 24, 25, 25, 23, 21 };`

   b) `int high[] = { 24, 23, 24, 25, 25, 23, 21 };`

   c) `int[] high = { 24, 23, 24, 25, 25, 23, 21 };`

   d) `int high [] = new int[24, 23, 24, 25, 25, 23, 21];`

   e) `int high = new[24, 23, 24, 25, 25, 23, 21];`

5. 下列哪项是正确的陈述？

   a) Java 数组是一个 `Object`。

   b) Java 数组的内存分配总是动态的。

   c) Java 数组由其元素的默认值初始化。

   d) 以上所有项。

**答案：** 1(c), 2(e), 3(c), 4(b, c), 5(d)

### 编程练习：

1. 编写一个程序使用线性查找在数组中搜索一个元素。

2. 编写一个程序使用二分查找在数组中搜索一个元素。

---

## 第 5 章：类与对象

### 引言

#### 类的定义

类代表一个 `ADT`（抽象数据类型）。它像一个模板，我们可以通过它创建多个对象（实例）。类的声明只创建一个模板，而不创建实际的对象。类创建了一个新的数据类型，该类型可以用于创建对象。也就是说，类创建了一个定义了其成员之间关系的逻辑框架。当我们声明一个类的对象时，我们正在创建该类的一个实例。因此，类是一个逻辑结构。而对象具有物理现实（也就是说，对象占用内存空间）。

```java
 class <classname> {
    修饰符 类型 变量;
    修饰符 类型 方法名(参数列表) {
        <方法体>
    }
}
```

#### 对象的声明

```
Student s1;
```

在上面的示例中 `s1` 不是对象。在 C++ 中 `s1` 被视为对象，但在 Java 中 `s1` 只是一个可以持有类型为 `Student` 对象引用的变量。在赋值之前 `s1` 为 `null`。

#### 内存分配

```
s1 = new Student();
```

在上面的示例中 `new` 运算符将为 `Student` 类分配内存并返回其引用，然后赋值给引用变量 `s1`。它还会调用默认构造函数初始化成员变量。

- `new` 在运行时为对象分配内存。如果 `new` 无法分配内存（内存不足），将产生运行时异常。

- 如果我们将引用变量赋值给另一个变量，传递的是地址。不会创建对象的副本。例如如果我们另一个变量 `s2` 然后执行 `s1 = s2`，这不会创建重复的对象，`s1` 和 `s2` 同一个对象。在 `s2` 中进行的任何更改都会反映在 `s1` 中。这种赋值不涉及内存分配。若干步后，如果我们给 `s1` 赋值 `null`，该对象不会被销毁，因为 `s2` 还引用着它。如果 `s1` 和 `s2` 都被赋值 `null`，该对象将被垃圾回收处理，其占用的内存将被释放。

```java
class A {
    int x;
    int y;
}

class Class1 {
    public static void main(String args[]) {
        A a1, a2; // 引用变量
        a1 = new A(); // 对象创建
        a2 = new A();
        a1.x = 10;
        a1.y = 20;
        a2.x = 5;
        a2.y = 6;
        System.out.println(a1.x + "\t" + a1.y);
        System.out.println(a2.x + "\t" + a2.y);
    }
}
```

### 示例 5.1 包含成员变量和成员方法的类。

```java
class A {
    int x;
    int y;
}
```

### 类成员的修饰符 / 可见性标签

可见性修饰符适用于类成员，而不适用于局部变量。

- `private`：如果我们为变量或方法指定了 `private` 修饰符，那么该成员在声明它的类外部是不可见的。这会将类的成员对其他类隐藏起来。

- `public`：如果我们为变量或方法指定了 `public` 修饰符，那么该成员对所有类都可见。该成员即使在包外部也可以被访问，因为 `main()` 方法始终被定义为 public，而 JVM 在定义 `main()` 方法的类外部访问了它。

- `protected`：声明为 `protected` 的成员可以被同一包中的所有类访问。`protected` 成员也可以被其他包的任何子类访问。

- `default / no modifier`（默认 / 无修饰符）：如果在声明之前没有指定可见性修饰符，则该成员可以被同包中的所有类访问。该成员在包外部无法访问。

### 类或接口的可见性修饰符

- `public`：如果一个类要对所有包的类都可见，则必须通过指定 `public` 修饰符将其声明为 `public`。

- `default / no modifier`（默认 / 无修饰符）：如果在类之前没有指定任何访问/可见性修饰符，其可见性仅限于其定义所在的包（类组）内。

### this 关键字

`this` 是一个引用变量，存储当前用于调用方法的对象的引用。`this` 的引用在运行时会被调用对象的引用所替换。有时，方法需要引用调用它的它的对象，这可以通过 `this` 来实现。`this` 可以用于任何方法内部以引用当前对象。注意：局部变量会隐藏实例变量，因此我们必须显式地使用 `this` 关键字。

### 实例变量隐藏

众所周知，在 Java 中，在相同或嵌套的作用域内声明两个同名的局部变量是违法的。但我们可以让局部变量（成员方法的参数）与类的实例成员变量具有相同的名称。当局部变量与实例变量同名时，局部变量会隐藏实例变量。但即使局部变量隐藏了它，`this` 关键字仍允许我们引用实例变量。

#### 示例 5.4 this 的使用

```java
class A {
    private int x;
    private int y;
    void setdata(int x, int y) {
        this.x = x; //this.x 是类成员 & x 是局部变量
        this.y = y;   
    }
    void display() {
        System.out.println(x + "\t" + y);
    }
}
class Class4 {
    public static void main(String args[]) {
        A a1 = new A();
        A a2 = new A();
        a1.setdata(10,20);
        a2.setdata(5,7);
        a1.display();
        a2.display();
    }
}
```

输出:

```
10	20
5	7
```

#### 方法重载

我们可以有多个同名的方法，只要它们在参数数量、参数类型或参数顺序上有所不同。这被称为方法重载。

在调用重载方法时，传递的实际参数类型可能与任何一个重载方法的的形式参数不完全匹配。在这种情况下，参数将提升到下一个更高的类型，直到找到匹配项。如果在提升参数后仍未找到匹配项，则会发生编译错误。

#### 示例 5.5 在示例中，有两个同名的 `setdata()` 方法，但参数不同，因此这是方法重载。

```java
class A {
    private int x,y;
    void setdata(int x1) {
        x = x1;
    }
    void setdata(int x1, int y1) {
        x = x1;
        y = y1;
    }
    void display() {
        System.out.println(x + "\t" + y);
    }
}
class ClassTest5 {
    public static void main(String args[]) {
        A a1 = new A();
        a1.setdata(5);
        a1.display();
        A a2 = new A();
        a2.setdata(10,20);
        a2.display();
    }
}
```

输出:

```
5	0
10	20
```

### 构造函数

在创建对象后立即对其初始化是一个非常常见的的需求。我们可以为此目的定义实例方法，但它们必须被显式调用。

```java
class A {
    private int y;
    void setdata(int x1, int y1) {
        x = x1;
        y = y1;
    }
    void display() {
        System.out.println(x + "\t" + y);
    }
}
class ClassTest2 {
    public static void main(String args[]) {
        A a1 = new A();
        A a2 = new A();
        //a1.x=10; error 因为 x 是私有的
        a1.setdata(10,20);
        a2.setdata(5,7);
        a1.display();
        a2.display();
    }
}
```

输出:

```
10	20
5	7
```

Java 为这一需求提供了解决方案。Java 允许对象在通过构造函数创建时进行自我初始化。它的语法与普通方法相同。

构造函数的语法与实例方法非常相似。它们的名称与类名相同，并且没有任何返回类型。

这是因为类构造函数的隐式返回类型是类本身。构造函数可以像方法一样进行重载。

当使用运算符 `new` 来创建类的实例/对象时，`JVM` 会为该对象分配内存，然后将实例变量初始化为默认初始值，最后调用相应的构造函数来初始化实例变量。

### Note

`constructor`（构造函数）这个名字有点误导。它似乎构造函数的目的是创建对象/实例。实际上，在构造函数被调用之前，对象已经创建，实例变量和静态变量已经初始化为它们的默认初始值。

因此，构造函数的目的是用非默认值来初始化实例变量。

### 构造函数的类型

#### 默认构造函数

每个类都有一个默认构造函数（如果没有定义显式构造函数），该函数不接受任何参数且函数体不包含任何语句。编译器会自动生成默认构造函数。

一旦我们添加了自身的构造函数，编译器就会停止生成默认构造函数。当我们不在类中创建任何构造函数时，`JVM` 将创建默认构造函数并将实例变量初始化为默认值 `null` 或 `zero`。

**Example 5.6 使用默认构造函数**

```java
class A {
    private int x;
    private int y;
    void display() {
        System.out.println(x + "\t" + y);
    }
}
class ClassTest6 {
    public static void main(String args[]) {
        A a1 = new A();
        a1.display();
    }
}
```

**Output:**

```
0       0
```

Note：在这里我们没有创建任何构造函数，`JVM` 在创建对象后会自动创建默认构造函数，并将实例变量初始化为 `0` 或 `null`。

#### 默认零参数构造函数

我们可以用自己的零参数构造函数替换默认构造函数。这将允许我们将实例变量初始化为任何值。

#### 参数化构造函数

带有参数的构造函数被称为参数化构造函数。

**Note:** 构造函数可以像方法一样进行重载。这被称为构造函数重载。

**Example 5.7 构造函数的使用.**



```java
class A {
    private int x;
    private int y;
    A() // 零参数构造函数 {
        x = 0;
    }
    A(int x1) // 参数化单参数构造函数 {
        x = x1;
    }
    A(int x1, int y1) // 参数化双参数构造函数 {
        x = x1;
        y = y1;
    }
    void display() {
        System.out.println(x + "\t" + y);
    }
}
class ClassTest7 {
    public static void main(String args[]) {
        A a1 = new A();
        a1.display();
        A a2 = new A(5);
        a2.display();
        A a3 = new A(4,7);
        a3.display();
    }
}
```

**Output:**

```
0   0
5
4   7
```

**Example 5.8:**

```java
import java.util.Scanner;
class Complex {
    private int real, imag;
    Complex()// 零构造函数 {
        imag = 0;
    }
    Complex(int real, int imag) {
        this.real = real;
        this.imag = imag;
    }
    void getdata() {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter real");
        real = sc.nextInt();
        System.out.print("Enter imag");
        imag = sc.nextInt();
    }
    void display() {
        if(imag>=0)
            System.out.println(real + "+" + "i");
        else
            System.out.println(real + "" + "i");
    }
    Complex sum(Complex c) {
        Complex t = new Complex();
        t.real = real + c.real;
        t.imag = imag + c.imag;
        return t;
        // or
        return new Complex(real+c.real,imag+c.imag);
    }
    Complex mult(Complex c) {
        Complex t = new Complex();
        t.real = real * c.real - imag * c.imag;
        t.imag = real * c.imag + imag * c.real;
        return t;
    }
    public static void main(String args[]) {
        Complex c1 = new Complex();
        Complex c2 = new Complex();
        Complex c3 = null, c4 = null;
        c1.getdata();
        c2.getdata();
        c3 = c1.sum(c2);
        System.out.print("Sum is ");
        c3.display();
        c4 = c1.mult(c2);
        System.out.print("Product is ");
        c4.display();
    }
}
```

### finalize() 方法

有时对象在被销毁时需要执行某些操作。例如，如果一个对象持有非 Java 资源（如文件句柄），那么我们可能希望在对象被销毁之前释放这些资源。

为了处理此类情况，Java 提供了一种名为终化（finalization）的机制。通过使用终化，我们可以定义在对象即将被垃圾回收器回收时执行的特定操作。`finalize()` 只在垃圾回收之前被调用。它不会在对象超出作用范围时被调用。在 C++ 中，使用析构函数的概念来实现终化，但它与 Java 中的 `finalize()`并不完全相同。

```java
protected void finalize() {
    // 在此处编写终化代码。
}
```

注意-我们可以使用 `public` 代替 `protected` 修饰符。

## 变量的类型

Java 有三种类型的变量：

### 1. 实例变量

在类中声明且位于所有成员方法之外的变量被称为实例变量。该变量的副本数量与对象的数量相同。

在 Java 中，不需要对实例变量进行初始化，因为这些变量在对象被创建并使用 `new` 操作符分配内存时就会被初始化。

变量根据其类型进行初始化。所有的数值型变量都自动初始化为 `0`，`Boolean` 变量初始化为 `false`，引用变量（对象）初始化为 `null` 值。

我们可以通过对象名和点（`.`）运算符来访问这些变量（`对象引用变量.实例变量名`）。我们不能像 C/C++ 那样使用 `->` 运算符分隔对象引用变量和实例变量。

### 2. 局部变量

在方法内部声明的变量被称为局部变量。它与实例变量不同。局部变量没有自动初始化。

### 3. 静态变量

静态变量像实例变量一样在方法/块之外声明。但静态变量在数据类型之前使用了 `static` 修饰符。静态变量对于类及其所有的实例（对象）来说都是全局的。

它们用于跟踪全局状态。例如，类中的静态变量 `count` 可以存储程序任何时刻创建的该类的实例/对象数量。

对象可以使用静态变量进行通信，就像 C 函数通过全局变量通信一样。对于静态变量，无论程序中创建了多少实例/对象，该变量只有一份拷贝并在所有实例之间共享。

点（`.`）运算符也用于访问类变量，但我们可以使用类名或对象名访问静态变量。如果我们在不同的对象中声明它们，它们都将指向静态变量的同一个副本。

静态变量在类加载/使用时会自动初始化为默认值（零、false 或 null）。

它们只能调用其他静态方法。它们只能访问静态数据。它们不能以任何方式引用 `this` 或 `super`。（关键字 `super` 涉及继承，将在后面描述。）

#### 示例 5.9

```java
class A {
    int x;    //实例变量
    static int y; //静态变量或类变量
}
class ClassTest8 {
    public static void main(String args[]) {
        A a1 = new A();
        A a2 = new A();
        A a3 = new A();
        a1.x = 10;
        a1.y = 20;
        a2.x = 11;
        a2.y = 21;
        a3.x = 12;
        a3.y = 22;
        System.out.println(a1.x + "\t" + a1.y);
        System.out.println(a2.x + "\t" + a2.y);
        System.out.println(a2.x + "\t" + a3.y);
    }
}
```

输出:

```
10  22
11  22
12  22
```

## 方法的类型

1. 实例方法

2. 静态方法

### 实例方法

这些与 C++ 函数相同。实例方法只能通过对象调用。如果我们在同类的静态方法内部调用实例方法，则必须使用对象名。

### 静态方法

静态方法可以使用对象以及类名来调用。静态方法只能访问静态成员。静态方法可以从同类的静态方法中直接调用（无需对象名或类名）。

#### 示例 5.10

```java
class A {
    int x;
    static int y;
    static int sum(int a, int b) {
        y = 5; // 任何方法都可以访问静态变量
        // x = 0; 错误，方法无法访问实例变量
        A a1 = new A();
        // a1.x = 10; 错误，因为方法可以通过对象访问实例变量
        // this.x = 10; 错误，方法无法访问 this 或 super
        int c;
        c = a+b;
        return(c);
    }
    static float avg(int a, int b) {
        return (float)(a+b)/2;
    }
}
class ClassTest9 {
    public static void main(String args[ ]) {
        System.out.println(A.sum(5,6)); // 静态方法可以通过类名调用
        System.out.println(A.avg(5,6));
        A a1 = new A();
        System.out.println(a1.sum(5,6)); // 静态方法也可以通过对象调用
    }
}
```

输出:

```
1
5
```

### 块

块用于初始化类的实例变量，静态块用于初始化类的静态变量。但构造函数在这些块之后调用。

#### 示例 5.1

```java
class A {
    int x;
    static int y;
    {
        // 初始化实例变量的块
        x = 10;
    }
    static {
        // 初始化静态变量的静态块
        y = 5;
    }
}
class ClassTest10 {
    public static void main(String args[]) {
        A a1 = new A();
        System.out.println(a1.x + "\t" + a1.y);
    }
}
```

输出:

```
10  5
```

### final 变量

如果一个变量被声明为 `final`，则我们不能改变它的值。`final double PI` final 变量不会每个实例占用内存。final 变量是一个常量变量，其值不能改变。final 变量引用类型不能改变其引用。

#### 示例 5.12

```java
class A {
    void m1() {
        System.out.println("Inside m1()");
    }
}
class ClassTest11 {
    public static void main(String args[])
    {
        final int x=10; //can not change
        final int y;    // Variable y not initialized so we can initialize y later
        y=20;           // Now y is initialize so after this we can’t change its value
        // y=30;         Error
        System.out.println(x);
        System.out.println(y);
        final A a1=new A();  // a1 is a constant reference so we can not
        // assign reference of any other object in f1.
        a1.m1();
        A a2 = new A();
        // a1 = a2;  error
    }
}
```

输出:

```
10
20
Inside m1()
```

# 参数传递机制

1. 值传递 (Call by Value)。

2. 引用传递 (Call by reference)。

当将基本类型（`int`、`float`、`long` 等）传递给方法时，使用的是值传递的方法。对于对象，实际传递的是对象的引用。

对象的引用也是通过值传递的方法传递的。然而，由于传递的值引用的是一个对象，该值的副本仍然指向与其对应的参数相同的对象。

例如，如果我们将一个存储对象引用的变量 `a1` 传递给函数，而函数中 `a2` 是形式参数，那么 `a1` 和 `a2` 都指向同一个对象。

通过 `a2` 对对象值的任何更改都会反映在 `a1` 中。但如果我们在 `a2` 中赋值一个新的引用，那么该引用不会自动复制到 `a1` 中。

#### 示例 5.13

```java
class Box
{
    private int feet;
    private int inches;
    Box()
    {
        feet = 0;
    }
    Box(int feet, int inches)
    {
        this.feet = feet;
        this.inches = inches;
    }
    void display()
    {
        System.out.println("Feet is " + feet +"\n" + "Inches is " +inches);
    }
    void swap(Box obj)
    {
        int t;
        t = feet;
        feet = obj.feet;
        obj.feet = t;

        t = inches;
        inches = obj.inches;
        obj.inches = t;
    }
}
class ClassTest12
{
    public static void main(String args[])
    {
        Box b1 = new Box(5,6);
        Box b2 = new Box(7,4);
        b1.swap(b2); //对象是通过引用传递的。
        b1.display();
        b2.display();
    }
}
```

输出:

```
Feet is 7
Inches is 4
Feet is 5
Inches is 6
```

## 嵌套类与内部类

可以在另一个类中定义一个类；此类类被称为嵌套类。嵌套类的作用范围受其外部类作用范围限制。

嵌套类可以访问其所包含的类的成员，包括该类的私有成员。然而，外部类无法访问嵌套类的成员。

嵌套类有两种类型：静态（static）和非静态（non static）。静态嵌套类是带有 `static` 修饰符的类。由于它是静态的，它必须通过对象来访问其外部类的成员。也就是说，它不能直接引用外部类的成员。由于这种限制，静态嵌套类很少使用。

非静态嵌套类可以访问其外部类的所有变量和方法，并可以像外部类的其他非静态成员一样直接引用它们。

### 示例 5.14

```java
class Outer
{
    class Inner
    {
        int member_inner=7;
        Inner()
        {
            member_outer = 5;
            System.out.println(member_outer);
        }
    }
    private int member_outer;
    Outer()
    {
        // member_inner = 9;  error
        Inner obj = new Inner();
        System.out.println(obj.member_inner);
    }
}
class ClassTest13
{
    public static void main(String args[])
    {
        Outer out_obj = new Outer();
    }
}
```

输出:

```
5
7
```

### 示例 5.15:



# 第 5 章 ∞

## 示例 5.15

```java
class Outer
{
    static class Inner
    {
        int member_inner = 7;
        Inner()
        {
            // member_outer = 5; error
            // System.out.println(member_outer); error
            Outer obj = new Outer();
            obj.member_outer = 5;
            System.out.println(obj.member_outer);
        }
    }
    private int member_outer;
    void prn()
    {
        Inner obj = new Inner();
        System.out.println(obj.member_inner);
    }
}
class ClassTest14
{
    public static void main(String args[])
    {
        Outer out_obj = new Outer();
        out_obj.prn();
    }
}
```

输出：

```
5
7
```

## 示例 5.16

```java
import java.util.Random;
class RandomTest
{
    public static void main(String args[])
    {
        Random r1 = new Random();
        for(int i = 1; i <= 10; i++)
        {
            System.out.println(Math.abs(r1.nextInt()));
        }
    }
}
```

## 理论题

1. 如果我们希望一个成员变量在当前类之外完全无法访问，在声明变量时应该在变量名前加上什么关键字？

2. 在 Java 中，对象/值是如何传递的？

3. 考虑以下代码：

```java
public static void main(String args[] )
{
    int a = 5;
    System.out.println( cube( a ));
}

int cube( int theNum )
{
    return theNum * theNum * theNum;
}
```

解释 `static` 关键字的重要性。

当我们尝试编译并运行这段代码时会发生什么？

a) 它无法编译，因为 `cube` 在 `java.lang.Math` 类中已经定义。

b) 它无法编译，因为 `cube` 不是静态的（static）。

c) 它可以编译，但会抛出算术异常（arithmetic exception）。

d) 它可以完美运行并在标准输出中打印 "125"。

4. 什么是静态内部类？它与其他静态成员有什么区别？

5. 如何在 Java 中声明常量值

6. `final` 关键字的什么含义？

7. 什么是类变量？

### 答案：

当我们创建一个同类的多个对象时，每个对象将共享变量的公共副本。这意味着无论从该类创建了多少个对象，每个类都只有一个副本。类变量或静态变量在类中使用 `static` 关键字进行声明。

这些变量存储在静态内存中。类变量主要用于常量，即初始值永远改变的变量。静态变量始终通过类名进行调用。

该变量在程序启动时创建，即在通过 `new` 运算符创建类的实例之前就已经创建了，并在程序停止时销毁。类变量的作用范围与实例变量相同。

类变量可以在类级别的任何地方使用 `static` 关键字定义。它的初始值与实例变量相同。当类变量定义为 `int` 时，其默认值为零；当声明为 `boolean` 时，默认值为 `false`；对象引用为 `null`。类变量与类相关，而不是与任何对象相关。

## 8. 解释垃圾回收。

### 答案：
垃圾回收是 Java 最重要的功能之一。垃圾回收也被称为自动内存管理，因为 JVM 会自动从内存中移除未使用的变量/对象（值为 `null`）。用户程序无法直接从内存中释放对象，相反，自动释放不再被程序引用的对象是回收器的工作。

每个类都从 `java.lang.Object` 继承 `finalize()` 方法，当垃圾回收器确定不再有对该对象的引用时，就会调用 `finalize()` 方法。

在 Java 中，当变量不再使用时，显式地将其赋值 `null` 是一个好习惯。在 Java 中，调用 `System.gc()` 和 `Runtime.gc()` 时，JVM 会尝试回收未使用的对象，但无法保证所有对象何时会被垃圾回收。

### 9. 如果一个类有多个构造函数，我们可以从一个构造函数调用另一个吗？

可以。使用 `this()` 从另一个构造函数调用构造函数。

## 10. 构造函数和普通方法有什么区别？

构造函数的名称必须与类名相同，且没有返回值。它们只被调用一次，而普通方法可以被调用多次，并且可以返回值或为 `void`。

## 11. 我们如何强制进行垃圾回收？

垃圾回收是自动过程，无法强制。我们可以通过调用 `System.gc()` 来请求它。JVM 并不保证 GC 会立即启动。

## 12. 下列哪种描述是不正确的？

(a) Java 中的局部变量总是由默认值初始化。

(b) Java 中的局部变量在用前必须初始化。

(c) 内部块中的局部变量不能与外部块中的局部变量具有相同的名称。

(d) 相同层级两个块中的局部变量可以同名。

![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg)

# 第 6 章 ∞

## 继承

### 序言

当一个类的属性转移到另一个类时，被称为继承。在这种情况下，被继承的类被称为超类、基类或父类，而继承的类被称为子类、派生类或子类。

继承允许我们通过添加额外功能来扩展现有的类（基类）。它鼓励代码的重用，这有助于减少代码量，尽管在某些情况下可能会导致复杂性。

例如，如果我们已经完成了一个简单计算器的代码。现在我们需要开发科学计算器，有两种可选方案：

(i) 创建一个新类。（重写类）

(ii) 扩展该类。

在大多数情况下，第二种方案是选择。在这种情况下，我们不需要花费大量时间进行调试和测试，因为基类已经过测试并使用了一段时间。当我们把一个类继承到另一个类时，必须使用 `extends` 关键字。

语法：`class sub_class extends base_class` (Images/image0122.jpeg)

类 A（超类或基类或父类）。类 B（子类或派生类或子类）。

子类将拥有基类的所有特征，加上在扩展类中定义的特征。Java 不支持多继承，但它支持多个接口，因此子类只继承一个基类。

### 示例 6.1

```java
class A {
    int x;
    void setX(int x1) {
        x = x1;
    }
    void displayX() {
        System.out.println(x);
    }
}

class B extends A {
    int y;
    void setY(int y1) {
        y = y1;
    }
    void displayY() {
        System.out.println(y);
    }
}

class Inherit1 {
    public static void main(String args[]) {
        A a1 = new A(); // 4 字节
        a1.setX(5);
        a1.displayX();

        B b1 = new B(); // 8 字节
        b1.setX(10);
        b1.setY(20);
        b1.displayX();
        b1.displayY();
    }
}
```

输出：

```
5
10
20
```

### 成员隐藏

如果子类成员与超类成员具有相同的名称（方法情况下签名也相同），那么它会隐藏超类成员。

虽然两个成员在子类中都是可用的，但使用成员名称只能访问子类成员，因为它隐藏了超类中同名的成员。

### 使用 super 关键字

每当子类需要引用其直接超类时，都可以通过使用关键字 `super` 来实现。`super` 有两个通用用途：

1. **调用超类的构造函数**

子类可以通过以下形式调用其超类定义的构造方法：`super(parameter-list);`

在这里，`parameter-list` 指定了超类构造所需的参数。事实上，`super()` 总是子类构造函数内部执行的第一条语句。

2. **访问被子类成员隐藏的超类成员**

`super` 关键字可以如下方式访问超类的被隐藏成员：

`super.member;`

在这里，成员可以是方法，也可以是数据成员。

## 方法重载与方法重写

### 方法重载

当两个或多个方法具有相同名称但不同的参数时，被称为方法重载。当对象需要执行相似的任务但使用不同的输入参数时，就会使用方法重载。

当我们调用一个方法时，Java 首先匹配方法名，然后匹配参数的数量和类型。决定调用哪一个方法定义的过程被称为多态。

### 方法重写

我们已经看到，超类中的方法被其子类继承，并由子类创建的对象使用。方法继承允许我们能够在子类中重复定义和使用方法，而无需在子类中再次定义该方法。

在类层次结构中，当子类中的实例方法与其超类中的实例方法（非私有）具有相同的签名时，则子类中的方法被认为重写了超类中的方法。

当从子类内部调用被重写的方法时，它将始终引用由子类定义的该方法版本。超类定义的方法版本将被隐藏。

![C:\Users\Made Man Harry\Desktop\Stars\black_star_logo.jpg](img/image0122.jpeg)

![C:\Users\Made Man Harry\Desktop\Stars\black_star_logo.jpg](img/image01222.jpeg)

### 示例 6.2

```java
class A {
    int x;
    void set(int x1) {
        x = x1;
    }
    void display() {
        System.out.println(x);
    }
}
class B extends A {
    int y;
    void set(int x1, int y1) // 类 B 的 set 方法没有重写类 A 的 set 方法，因为参数不同
    {
        set(x1);  // 这将调用类 A 的 set()
        y = y1;
    }
    void display() // 类 B 的 display 方法重写了类 A 的方法
    {
        display(); // 这调用类 B 的 display
        super.display(); // 这调用类 A 的 display
        System.out.println(y);
    }
}
class Inherit2 {
    public static void main(String args[]) {
        B b1 = new B();
        b1.set(0, 20);
        b1.display();
    }
}
```

输出：

```
10
20
```

Java 支持以下继承形式：

[1] 单继承。

[2] 多级继承。

[3] 层级继承。

### 单继承

![](img/image0123.jpeg)

### 示例 6.3

```java
class A {
    private int x;
    A() {
        x = 0;
    }
    A(int x1) {
        x = x1;
    }
    void display() {
        System.out.print(x);
    }
}
class B extends A {
    private int y;
    B() {
        super();
        // x = 0; error，因为 x 是私有的
        y = 0;
    }
    B(int x1, int y1) {
        super(x1);
        // x = x1; error，因为 x 是私有的
        y = y1;
    }
    void display() {
        super.display();
        System.out.print(y);
    }
}
class InheritTest3 {
    public static void main(String args[]) {
        B b1 = new B();
        b1.display();
        B b2 = new B(10, 20);
        b2.display();
    }
}
```

输出：

```
0 10 20
```

![](img/image0124.jpeg)

![C:\Users\Made Man Harry\Desktop\Stars\black_star_logo.jpg](img/image0125.jpeg)

### 示例 6.4

```java
class A {
    private int x;
    A() {
        x = 0;
    }
    A(int x1) {
        x = x1;
    }
    void display() {
        System.out.println(x);
    }
}
class B extends A {
    private int y;
    B() {
        super();
        y = 0;
    }
    B(int x1, int y1) {
        super(x1);
        y = y1;
    }
    void display() {
        super.display();
        System.out.println(y);
    }
}
class C extends B {
    private int z;
    C() {
        super();
        z = 0;
    }
    C(int x1, int y1, int z1) {
        super(x1, y1);
        z = z1;
    }
    void display() {
        super.display();
        System.out.println(z);
    }
}
class Inherit4 {
    public static void main(String args[]) {
        C b1 = new C();
        b1.display();
        C b2 = new C(10, 20, 30);
        b2.display();
    }
}
```

## 构造函数调用的顺序

当创建一个类层次结构时，构成该层次结构的类的构造函数按什么顺序被调用？答案是，在类层次结构中，构造函数按照派生顺序从父类到子类进行调用。

此外，由于 `super()` 必须是子类构造函数中执行的第一条语句；因此无论是否使用 `super()`，这种顺序都是相同的。如果不使用 `super()`，则将执行每个父类的默认构造函数或无参数构造函数。

构造函数按照派生顺序执行。因为父类并不知道任何子类，所以它需要执行的任何初始化都是独立的，并且可能是子类所执行的任何初始化的前决条件。因此，它必须首先执行。

`super` 关键字在满足以下条件时使用：

- `super()` 构造函数只能在子类的构造器方法中调用。

- 对父类构造函数的调用必须作为子类构造函数中的第一条语句。

- `super` 调用中的参数必须与父类构造函数的参数顺序和类型匹配。

# 动态方法绑定

（动态方法分发或运行时绑定）

方法重写构成了 Java 强大概念之一的基础：动态方法分发是一种在运行时而非编译时解析对被重写实例方法调用的机制。动态方法分发非常重要，因为这是 Java 实现运行时多态的方式。

父类引用变量可以指向子类对象。Java 利用这一事实在运行时解析对重写方法的调用。当通过父类引用调用重写方法时，Java 根据调用发生时所引用对象的类型来决定执行该方法的哪个版本。

因此，这种判断是在运行时进行的，当引用不同类型的对象时，将调用重写方法的不同版本。换句话说，是引用对象的类型（而不是引用的类型）决定了将执行哪个版本的重写方法。

重写方法允许 Java 支持运行时多态。多态对于面向对象编程（OOP）至关重要，原因在于：它允许通用类指定所有派生类都共有的方法，同时允许父类定义这些一些或所有方法的具体实现。

通过将继承与重写方法结合，父类可以定义所有子类都使用的方法的通用形式。现有代码库在不重新编译的情况下保持整洁的抽象接口并调用新类实例的方法的能力，是一种极其强大的工具。

基类引用可以接受子类引用，但子类引用不能接受基类引用。



![C:\Users\Made Man Harry\Desktop\Stars\black_star_logo.jpg](img/image01225.jpeg)

## Example 6.5

```java
class Shape {
    void getdata() {
        System.out.println("getdata() of Shape");
    }
    void area() {
        System.out.println("area() of Shape");
    }
    void display() {
        System.out.println("display() of Shape");
    }
}

class Circle extends Shape {
    void getdata() {
        System.out.println("getdata() of Circle");
    }
    void area() {
        System.out.println("area() of Circle");
    }
    void display() {
        System.out.println("display() of Circle");
    }
}

class Rectangle extends Shape {
    void getdata() {
        System.out.println("getdata() of Rectangle");
    }
    void area() {
        System.out.println("area() of Rectangle");
    }
    void display() {
        System.out.println("display() of Rectangle");
    }
}

class InheritTest {
    public static void main(String args[]) {
        // super 引用变量可以接受子类对象
        // 动态绑定
        Shape s[] = {new Circle(), new Rectangle()};
        for (int i = 0; i < s.length; i++) {
            s[i].getdata();
            s[i].area();
            s[i].display();
        }
    }
}
```

**输出：**

```
getdata() of Circle
area() of Circle
display() of Circle
getdata() of Rectangle
area() of Rectangle
display() of Rectangle
```

## 抽象类与抽象方法

我们已经通过将方法标记为 `final` 来确保该方法在子类中不会重定义。Java 允许我们做与此完全相反的事情。即我们可以指示某个方法必须在子类中重定义，从而使重写成为强制性。这是通过在方法定义中使用关键字 `abstract` 实现的。

在某些情况下，我们可能想要一个只声明结构而不提供完整实现的父类。也就是说，有时我们希望创建一个只定义所有子类共享的通用形式的父类，让每个子类去填充细节。这种类决定了子类必须实现的方法性质。

**Example 6.6：**

```java
abstract class Shape {
    abstract void getdata();
    abstract void area();
    abstract void display();
}

class Circle extends Shape {
    void getdata() {
        System.out.println("getdata() of Circle");
    }
    void area() {
        System.out.println("area() of Circle");
    }
    void display() {
        System.out.println("display() of Circle");
    }
}

class Rectangle extends Shape {
    void getdata() {
        System.out.println("getdata() of Rectangle");
    }
    void area() {
        System.out.println("area() of Rectangle");
    }
    void display() {
        System.out.println("display() of Rectangle");
    }
}

class InheritTest6 {
    public static void main(String args[]) {
        // super 引用变量接受子类对象
        // 动态绑定
        Shape s[] = {new Circle(), new Rectangle()};
        for (int i = 0; i < s.length; i++) {
            s[i].getdata();
            s[i].area();
            s[i].display();
        }
    }
}
```

输出：

```
getdata() of Circle
area() of Circle
display() of Circle
getdata() of Rectangle
area() of Rectangle
display() of Rectangle
```

### Final 方法 (Final method)

如果我们不希望一个方法被派生类重写，可以将基类定义为 `final`。任何重写该方法的尝试都会导致编译错误。

```java
class A {
    final void method1() {
        //
    }
}
class B extends A {
    void method1() // 错误
}
```

### Final 类 (Final class)

有时出于安全考虑，我们可能希望防止类被进一步子类化。不能被子类化的类被称为 `final class`。在 Java 中通过如下使用 `final` 关键字来实现：

```java
final class A1 {
    //
}
```

将类声明为 `final` 可以防止对该类的任何意外扩展。任何继承 `A` 的尝试都会导致错误，编译器将不允许这样做。

### 题 (Theory Questions)

1. 什么是继承？
2. Java 中共有多少类型的继承？
3. 默认构造函数和参数化构造函数的区别是什么？
4. `final class` 和 `final method` 的区别是什么？
5. 什么是 `super class`（父类）？
6. 什么是 `abstract class`（抽象类）？
7. 编译时绑定和运行时绑定的区别是什么？
8. 方法重载（method overloading）和方法重写（method overriding）的区别是什么？

### 简介 - 面向对象编程与过程化编程 (Introduction - Object oriented programming vs procedural programming)

所有程序都由两个元素组成：过程（逻辑）和数据。根据主要关注的是处理还是数据，有两种不同的方法。过程化语言（`FORTRAN`、`PASCAL`、`COBOL` 等）关注于处理部分，更重视“发生了什么”（过程），而较少重视“谁受到了影响”（数据）。

随着程序变得巨大且复杂，过程化方法变得不再适用。开发面向对象的编程语言是为了克服过程化语言的局限性。与过程化语言中的相似程序相比，面向对象的编程语言的复杂度相对低得多。面向对象的程序围绕数据（即对象）以及指向数据的一组定义的接口（方法）组织。

Java 基于面向对象范式。Java 几乎是一门面向对象的语言。我们使用“几乎”一词是因为出于性能考虑，Java 也支持基本级数据类型。`C++` 不是纯的面向对象语言。`C++` 是 `C` 的扩展，因此它使用了一种面向过程方法和面向对象方法混合的方法。

这两种方法的基本区别总结如下：

(i) 面向对象的程序是以数据为中心的，而用过程化语言编写的程序是以过程为中心的。
(ii) 面向对象的程序围绕数据（对象）组织，因此它们能更好地模拟现实世界的对象。
(iii) 与过程化方法相比，面向对象方法的代码重用性和扩展性非常高。因此代码量更少。
(iv) 面向对象的程序更容易维护，因为它们相对复杂度较低且尺寸较小。
(v) 面向对象的程序基于自底向上的设计方法，而过程化程序基于自顶向下的设计方法。

### OOP (面向对象编程) 的基本概念 (Basic concepts of OOP)

以下列出了面向对象编程的一些基本元素：

- 抽象 (Abstraction)
- 对象和类 (Objects and classes)
- 三大 OOP 原则：
    - 封装 (Encapsulation)
    - 继承 (Inheritance)
    - 多态 (Polymorphism)
- 持久化 (Persistence)
- 通用性 (Genericity)
- 组合 / 聚合 (Composition / Aggregation)

#### 1. 抽象 (Abstraction)

抽象是任何编程语言（包括过程化语言）的要素元素之一。内置数据类型的概念也是一种抽象。在 `C` 语言中使用 `struct` 定义自己的数据类型特征进一步扩展了这种抽象。

抽象的基本目的是通过隐藏实现细节来降低复杂性。例如，一栋建筑不被视为建筑材料的集合，而是一个具有独特特征和属性定义的定义对象。

抽象可以定义为识别对象的本质属性和行为，而不深究细节。对象的属性和行为使其与其他相似类型的对象区分开来，并有助于对对象进行分类/分组。面向对象的编程语言使用类和对象来模拟抽象。

#### 2. 对象和类 (Object and Classes)

**对象**：对象是一个物理或抽象的实体或事物，可以与其他相似类型的对象区分开来。对象具有三个特征：

(i) 标识性（Identification）。
(ii) 属性（Attributes）。
(iii) 行为（Methods / Operations / Functions）。

对象也可以被视为 `class` 的实例，其中 `class` 类似于内置数据类型，而 `object` 则是变量。

**类**：`class` 通过抽象其属性和行为来表示一类对象。`class` 可以被视为创建对象的蓝图。对象具有由其 `class` 定义的属性和行为。`class` 可以被视为一种自定义数据类型，而 `object` 是由 `class` 所表示的数据类型的变量/实例。

类也可以被视为一种用户定义的数据类型，而对象是该数据类型的变量。一旦定义了类，我们就可以创建任意数量该类的对象。

## 3. 三大面向对象编程原则

### 封装

封装是将代码及其所作用的数据绑定在一起的机制。`Java` 类支持这一点，因为它允许我们将代码和数据定义在一起。封装还通过将某些类成员声明为 `private` 来帮助实现数据隐藏，使得这些成员无法从不属于该类的代码访问。

### 继承

在面向对象编程中，继承指的是一个类的属性对其他被称为子类或派生类的类可用。子类或派生类是从现有类派生出来的类。它继承了现有类的所有特征，现有类也被称为基类（base-class）或超类（super-class）。因此，继承可以定义为从超类或基类派生类的过程。继承类不会给基类/超类引入任何更改。与基类相比，派生类/子类具有更多的属性和行为。

继承的主要优势是代码复用。如果基类已经使用了长时间，并且需要添加一些额外的属性和方法，我们可以通过派生另一个类来实现。派生类将能够使用基类的代码而无需调试，因为它已经使用了很长时间。

### 类层次结构

所有派生自同一个基类的类都属于一个家族并形成类层次结构。类层次结构可以与树形结构相比，其中一个基类位于根节点且没有超类。

所有其他类要么派生自层次结构根节点的类，要么派生自某些直接或间接派生自根类的类。随着向下移动，添加的功能越来越多。由叶节点表示的类没有任何子类。下面的示例展示了一些类层次结构。

```
![](img/image01227.jpeg)
```

### 多态

多态是一种允许同一接口用于一类操作的特性。大多数面向对象的语言在以下情况使用多态：

* 运算符重载。
* 方法重载。
* 方法重写。

#### 运算符重载

大多数语言使用这种形式的多态用于内置操作。例如，`C/C++` 或 `Java` 中的所有算术运算符都可以用于许多类型的操作数（`int`、`long`、`float`、`double` 等）。因此，相同的加法运算符可以用于加两个整数，也可以用于加两个浮点数。

`C++` 允许用户重载内置运算符。例如，我们可以重载算术运算符来处理复数。虽然 `Java` 对内置运算符使用了运算符重载，但它不允许用户重载运算符。

#### 方法重载

此特性允许我们编写多个同名的方法。`C++` 和 `Java` 具有这一特性。同名的方法（`C++` 中的函数）根据参数（参数值）进行区分。重载的方法必须具有不同的参数数量，或者如果参数数量相同，则参数类型必须不同。

如果对重载方法的调用可以在编译时解析，即如果编译器可以决定调用哪一个重载方法，则这被称为静态绑定，它是编译时多态的一个示例。

如果对重载方法的调用无法在编译时解析，即如果编译器无法决定将调用哪一个重载方法，则这被称为动态绑定，它是运行时多态的一个示例。

通常情况下，`Java` 在运行时解析对重载方法的调用，但在许多情况下，对重载方法的调用是在编译时解析的。

#### 方法重写

子类可以定义一个与超类中相同名称的方法，并具有相同数量和类型的参数。这被称为方法重写。

编译器无法解析对重写方法的调用。`Java` 通常使用动态绑定来解析对重写方法的调用，即决策发生在运行时。

## 4. 持久化

某些面向对象的语言允许我们从持久化存储介质存储/检索程序的状态，即如辅助存储之类的永久存储介质。这被称为持久化。

`Java` 允许我们将任何对象存储在辅助存储中并在以后检索它。如果我们尝试在对象图的顶部存储一个对象，所有其他引用的对象将被递归地找到并保存。同样，当以后检索对象时，所有的对象及其引用（即整个对象图）都会在主内存中正确创建。

例如，只需保存树的根就可以保存整个树结构。在稍后的阶段，只需保存树的根就可以在内存中重建整个树结构。`C++` 不支持这一特性。

## 5. 泛型

定义一次算法（独立于任何特定数据类型）并然后将该算法应用于各种数据类型而无需任何额外努力的概念被称为泛型。`C++` 使用模板支持这一特性。`Java` 也通过 `Object` 类支持这一特性，该类是 `Java` 中任何类层次结构的顶端。

例如，使用这一特性，我们可以实现一个泛型数据类型 `stack`，以便在栈中存储任何类型的元素。这一特性在很大程度上提高了可复用程度。

## 6. 组合 / 聚合

对象可能由其他对象组成。这样的对象被称为复合对象或聚合对象。例如，如果 `vehicle` 类的对象被定义为由 `Engine`、`Body`、`Axle`、`Seats` 等对象组成的复合对象是合适的。

### 继承与组合

从现有类派生新类的基本机制有两种：继承和组合。`Bus` 类可以通过继承 `vehicle` 类的属性来派生。在这里，`Bus` 是车辆的一种，具有一些所有车辆共同属性和行为之外的额外属性。换句话说，`Bus` 类与 `vehicle` 类之间存在关系，因为可以说公交是一辆车辆。

`vehicle` 类本身可能通过组合派生自许多其他类。例如，`vehicle` 类的对象可能由属于 `Engine`、`Gear Box`、`Seats`、`Driver’s Seat Body` 和 `Steering Wheel` 等类的对象组成。

### 超类与子类

通常，一个类的对象也是另一个类的对象。矩形显然是四边形（正方形、平行四边形和梯形也是如此）。因此，可以说 `Rectangle` 类继承自 `Quadrilateral` 类。在这种语境下，`Quadrilateral` 类是超类，而 `Rectangle` 类是子类。

矩形是四边形的一种类型，但声称四边形是矩形是不正确的（四边形可能是平行四边形）。图显示了超类和潜在子类的几个简单继承示例。

## 继承概览

然而，另一种看待这些术语的方式也完全合理。因为每个子类对象都“是”其父类的对象，而且由于一个父类可以有多个子类，所以父类所代表的对象集合通常比该父类的任何子类所代表的对象集合要大。

例如，父类 `Vehicle` 以通用方式表示所有车辆，如汽车、卡车、船、自行车等。然而，子类 `Car` 仅代表了世界上所有 `Vehicles` 中的一小部分集。继承关系形成了树形的层级结构。

父类与其子类之间存在层级关系。类完全可以独立存在，但只有当类配合继承机制使用时，它才成为向其他类提供属性和行为的父类，或者是继承这些属性和行为的子类。通常，一个类既是子类也是父类。

| 父类 | 子类 |
| :--- | :--- |
| `Student` | 研究生、本科生 |
| `Shape` | 圆形、三角形、矩形 |
| `Loan` | 汽车贷款、房贷、教育贷款 |
| `Employee` | 教职工、职员工 |
| `Account` | 支票账户、储蓄账户 |

![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg)

![STAR-LOGO-2013](img/image01213.jpeg)



# 第 8 章 (包)

## 引言

当我们开发项目时，必须将程序拆分为几个类。为了组织这些类，我们使用 `Packages`（包）。包既是一种命名机制，也是一种可见性控制机制。包是相互相关的类和接口的集合。借助包的帮助，只要它们定义在不同的包中，就可以给多个类赋予相同的名称。

单个包不能包含两个同名的类。

`PROGRAMS` 被组织为包的集合。每个包都有自己的子包集合，这有助于防止命名冲突。顶层包只有在被声明为 `public` 时，才能在包外访问。包的命名结构是层级的。包的成员是类类型、接口类型和子包。`java` 中的包是一种封装机制，可用于将相关的类、接口和子包组合在一起。

对于小型程序，包可以是未命名的或具有简单的名称，但如果代码要广泛分发，应该选择唯一的包名。

这可以防止发生冲突——如果两个开发小组恰好选择了相同的包名，且这些包后来被在同一个程序中使用，就会产生冲突。如果我们没有为 `java` 类指定包，那么该类将成为 Java 默认包的一部分，称为无名包。但这要求每个类必须具有唯一的名称以避免冲突。

## 无名包的示例

```java
class A {
    // - - - - - - -
    // - - - - - - -
}

class A_demo {
    public static void main(String args[]) {
        // - - - - - -
        // - - - - - -
    }
}
```

## 如何定义包

要创建一个包，请在源文件的第一个语句中包含 `package` 命令。在该文件中声明的任何类都将属于指定的包。包语句定义了存储类的空间。如果我们省略了包语句，类将被放入默认包中，该包没有名称，称为无名包。Java 使用文件目录来存储包。请记住大小写敏感，且目录名称必须与包名完全匹配。多个文件可以包含相同的包语句。

**语法：**

```java
package package_name; // 包声明
class A // 类声明
{
    // 类 A 的主体
}
```

`package` 是一个关键字。`p1` 是类 `A` 将要存储的包名。

**示例 8.1：**

```java
package p1;
class A {
    public static void main(String args[]) {
        System.out.println("First Package program.");
    }
}
```

我们假设当前文件夹是 (`c:\javaprg\p1>`。

```bash
C:\javaprg\p1>javac A.java
C:\javaprg\p1>java p1.A
```

输出：

`First Package program.`

注意：如果我们在 `c:\javaprg>` 下使用 `javac -d . A.java` 编译上述程序，则文件夹 `p1` 将自动创建，上述程序的 `.class` 文件将保存在该文件夹中。但如果我们不带 `-d` 选项编译，则我们需要创建 `p1` 文件夹并将 `.class` 文件放在当前目录下。

## 导入包

Java 的所有内置类都存储在命名的包中；包内的类必须使用全限定名，否则将为每个使用的类编写点分隔的长路径。因此，Java 提供了 `import` 语句将某些类或整个包引入可见范围。一旦导入，就可以直接使用名称引用类。`import` 语句是对程序员的一种便利，它在技术上并不是必须的。如果我们要在应用程序中引用几个类，`import` 语句将节省大量的输入工作。在 Java 源文件中，`import` 紧随包语句（如果存在）之后、类定义之前。这是 `import` 语句的通用形式。

```java
import pkg1.classname;
import pkg1.*;
```

**示例 8.2：**

// 使用 `java.util` 包中的 `Random` 类打印 10 个随机数

// 不使用 `import` 语句

```java
package java.util
class RandomTest1 {
    public static void main(String args[]) {
        java.util.Random r1 = new java.util.Random();
        for(int i=1; i<=10; i++) {
            System.out.println(Math.abs(r1.nextInt()));
        }
    }
}
```

输出：

```
1588659525
481996564
210875677
386971039
360473512
1922641171
393055462
889442536
1836112189
320882863
```

**示例 8.3**

// 使用 `java.util` 包中的 `Random` 类打印 10 个随机数

// 使用 `import` 语句

```java
import java.util.Random;
class RandomTest2 {
    public static void main(String args[]) {
        Random r1 = new Random();
        for(int i=1; i<=10; i++) {
            System.out.println(Math.abs(r1.nextInt()));
        }
    }
}
```

输出：

```
686722541
1154462827
452959606
1235134497
1421490552
1065881855
424893046
731473166
1217844570
437181304
```

### 类路径 (CLASSPATH)

如果在当前文件夹之外的任何文件夹运行上述程序，它将无法运行。默认情况下，Java 运行时系统使用当前工作目录作为起点。

因此，如果我们的包在当前目录下或当前目录的子目录下，它将会被找到。但要从任何其他文件夹运行上述程序，我们必须在命令提示符中使用命令 `SET CLASSPATH=.;C:\JAVAPRG` 来设置类路径。`CLASSPATH` 是一个环境变量。我们每次第一次启动电脑时都需要输入此命令。但如果我们将此命令放在 `我的计算机属性高级环境变量` 中，那么就不需要再反复地输入此命令了。

我们也可以在不设置 `CLASSPATH` 环境变量的情况下运行程序。为此只需输入：

```
java –classpath c:\javaprg p1.A
```

**注意 4**: 我们可以创建包的层级结构。要实现这一点，只需使用点 `.` 将每个包与其上面的包隔开。多级包语句的通用形式为：

`package package_name1[.package_name2][.package_name3];`

包的层级结构必须在 Java 开发系统的文件系统中反映。例如，包 `java.awt.Image` 需要存储在 `java\awt\image`（WINDOWS）或 `java/awt/image`（UNIX）或 `java:swt:image`（MAC）文件系统中。

包的层级结构代表了 Java 类和接口的组织。它并不代表类和接口的源代码组织。

每个 Java 源文件（也称为编译单元）可以包含零或多个类和接口的定义，但编译器会为它们生成一个包含 Java 字节码的独立类文件。类或接口可以使用包声明来指示其 Java 字节码被放在特定的包中。

*   包 `java` 有子包 `awt`、`applet`、`io`、`lang`、`net` 和 `util`，但没有类或接口。
*   包 `java.awt` 有一个名为 `image` 的子包以及许多类和接口。
*   因为包 `java.awt` 有子包 `image`，所以它不能包含名为 `image` 的类或接口类型的声明。
*   如果一个包的全限定名是 `P`，且 `Q` 是 `P` 的子包，那么 `P.Q` 就是该子包的全限定名。
*   如果有一个名为 `mouse` 的包，且该包中有一个成员类 `Button`（这可能被称为 `mouse.Button`），则不能有任何全限定名为 `mouse.Button` 或 `mouse.Button.Click` 的包。
*   一个源文件中最多可以出现一个包语句，且它必须是 Java 源文件的第一条语句。

## 类成员的可见性

类和包都是封装和包含变量及方法命名空间与范围的手段。包充当类和其他子包的容器。类充当数据和方法代码的容器。

类是 Java 最小的抽象单元。由于类和包之间的相互作用，Java 处理类成员有五类可见性：

1.  类内部的可见性。
2.  同一包中子类中的可见性。
3.  同一包中非子类中的可见性。
4.  不同包中子类中的可见性。
5.  既不在同一包中也不是子类的类中的可见性。

**注意 1**: 顶层类和接口只有两种可能的访问权限：默认的（default）和 `public`。

**注意 2**: 如果类被声明为 `public`，则可以通过其他代码访问。

**注意 3**: 如果类具有默认访问权限，则它只能被同一包内的其他代码访问。

**注意 4**: 成员可见性只有在类可见的情况下才有意义。如果类的可见性修饰符是默认的，即使是类的 `public` 成员也仅在包内可见。

## 访问修饰符

![](img/image01228.jpeg)

## JAR 文件 (Java 归档文件)

为了压缩文件，我们使用某些程序如 winzip。JAR 文件也可以用于压缩整个包。它提供了更好的安装体验。无需创建文件。JAR 技术使得分发变得容易得多。

JAR 有以下可用选项：

| 选项 | 说明 |
| :--- | :--- |
| `c` | 创建新归档。 |
| `C` | 执行期间更改目录。 |
| `f` | 文件列表的第一个元素是要创建的归档名称。 |
| `i` | 应提供索引信息。 |
| `m` | 文件列表的第二个元素是外部清单文件的名称。 |
| `M` | 不创建清单文件。 |
| `t` | 应该列出归档内容。 |
| `u` | 更新现有归档。 |
| `v` | 执行时提供详细输出。 |
| `x` | 从归档中提取的文件。 |

创建 JAR 文件：

```
jar -cf Myjar.jar pack1
```

这将创建一个包含 `pack1` 所有文件的 `Myjar.jar`。

解压 JAR 文件：

此命令用于提取文件（如 unzip）。

```
jar -xf Myjar.jar
```

列出 JAR 文件内容：

以下命令列出 `Myjar.jar` 的内容。

```
jar -tf Myjar.jar
```

更新现有 JAR 文件：

以下命令用于更新 JAR 文件。

```
jar -uf Myjar.jar pack1
```

创建可执行的 JAR 文件：

```
jar -cmf mainClass Myjar.jar pack1
```

其中 `mainClass` 是包含 `Main-Class: pack1.pack2.pack3.A` 的文本文件，保存在 `javaprg` 文件夹中。

执行 JAR 文件：

```
java -jar Myjar.jar
```

## 题：

1.  我们对包了解什么？
2.  解释所有的修饰符及其在不同包、子包以及子类和其他类中的范围。
3.  JAR 文件的作用是什么？
4.  `import` 语句的作用是什么？

![](img/image01229.jpeg)

在 Amazon.com 上搜索此书，ISBN 为 978-1500730413。

# 第 9 章

## 接口 (Interface)

### 引言

接口本质上是一种类。和类一样，接口包含方法和变量，但有一个主要区别。区别在于接口只定义抽象方法和 `final` 变量（常量）。这意味着接口不编写任何代码来实现这些方法，且数据字段只包含常量。

因此，类的职责是实现一个接口，定义实现这些方法的代码。接口在语法上与类相似，但它们缺乏实例变量，且其方法声明时没有方法体。在实践中，这意味着我们可以定义接口，而不对它们的实现方式做任何假设。接口的目的是将类的接口与其实现分离开。接口仅仅定义了类必须做什么，而不对实现进行任何说明。接口只定义方法签名，不包含任何实例变量。

嵌套接口是指任何声明在另一个类或接口体内的接口。顶层接口不是嵌套接口的接口。定义接口的语法与定义类非常相似。接口定义的通用形式如下：

```java
interface interface_name {
    variable declarations;
    methods declarations;
}
```

在这里，`interface` 是关键字，`interface_name` 是任何有效的 java 标识符（就像类名一样）。

**注意：** 当我们定义接口时，默认情况下它是公共的（`public`）且抽象的（`abstract`）。

### 接口修饰符

顶层接口可使用的唯一修饰符是 `abstract` 和 `public`。即使我们不使用 `abstract` 修饰符，接口也会隐式地声明为 `abstract`，因此不需要使用 `abstract` 修饰符。顶层接口的可见性可以是包级（package）或公共（`public`），就像顶层类一样。如果没有使用可见性修饰符，则接口的可见性假设为包。

### 数据变量成员声明

接口中只能定义常量。接口中的所有变量都隐式地 `public`、`final` 和 `static`，这意味着它们不能被实现类更改。它们还必须用常量值初始化。

```java
public static final type variable_name=value;
```

在接口中声明的变量是 `public`、`static` 且 `final`。这意味着它是具有公共访问权限的静态变量。该变量也被声明为 `final`，这意味着它必须在声明时赋值，并且之后不能再修改。`final` 关键字类似于 C/C++ 中的 `const`。

### 方法声明

方法声明将仅包含方法列表，而不包含任何语句。它们在参数列表后以分号结束。它们本质上是抽象方法，接口中指定的任何方法都不能有默认实现。

接口中的所有方法默认都是 `public` 和 `abstract` 修饰符。我们不能在接口中声明 `static` 方法。

```java
public abstract return_type method_name(parameter_list);
```

这是一个包含两个变量和一个方法的接口定义示例。

```java
interface item {
    static final int code =1001;
    static final String name = "Matrix";
    abstract void display();
}
```

**注意：** 方法的代码不包含在接口中，方法声明仅以分号结束。

另一个接口的示例：

```java
interface area {
    float pi = 3.14f;
    float compute(float x, float y);
    void show();
}
```

### 扩展接口

与类一样，接口也可以被扩展，即一个接口可以从其他接口派生。新接口将以类似于子类的方式继承子接口的所有成员。这通过使用 `extends` 关键字来实现，如下：

```java
interface interface_1 {
    int code = 1001;
    String name = "Matrix";
}

interface interface_2 extends interface_1 {
    void display();
}
```

`interface_2` 将继承其中的常量 `code` 和 `name`。

**注意：** 变量 `name` 和 `code` 是像普通变量一样声明的。这在这里是被允许的，但接口中的所有变量都被视为常量和静态，尽管这里没有使用 `public`、`static` 和 `final` 关键字。

我们可以将多个接口组合在一个接口中。以下声明是有效的：

```java
interface interface_1 {
    int code = 1001;
    String name = "Matrix";
}

interface interface_2 {
    void display();
}

interface interface_3 extends interface_1, interface_2 {
}
```

**注意：** 始终记住接口不能扩展类。这违反了接口只能有抽象方法和常量的规则。

### 实现接口

接口被用作“超类”，其属性被类继承。因此，有必要创建一个继承给定接口的类。一旦定义了接口，一个或多个类就可以实现该接口。

要实现接口，需要在类定义中包含 `implements` 子句，然后创建接口声明的方法。实现类必须提供所有接口中所有的方法体，否则必须被声明为抽象类。实现类还可以扩展一个类并实现多个接口。

```java
class <class-name> implements <interface-name> {
    // body of class
}
```

Java 不支持多继承，但支持多接口继承，即一个类可以实现多个接口，如下：

```java
class <class-name> implements <interface-1>, <interface-2>, <interface-n> {
    // body of class
}
```

**注意：** 当我们实现接口方法时，它必须声明为 `public`。实现接口方法类似于重写，因此我们不能降低可见性。

**示例 9.1**



```java
interface interface_1 {
    void show(int x);
}

class class_1 implements interface_1 {
    public void show(int x) {
    }
}
```

### 抽象类的 9.2 示例

```java
interface common {
    void push(int x);
    int pop();
}

abstract class stack implements common {
    abstract void disp();
}
```

在这里，`stack` 类没有实现 `push()` 和 `pop()` 方法。因此，我们必须将 `stack` 类声明为抽象类，这种技术被称为部分实现。

## 接口继承的各种形式

(a) ![](img/image01230.jpeg)
(单级接口继承)

(b) ![](img/image01231.jpeg)
(多级接口继承)

(c) ![](img/image01232.jpeg)
(层次结构接口继承)

(d) ![](img/image01233.jpeg)
(混合接口继承)

## 通过接口引用访问实现类对象

我们可以将变量声明为使用接口而非类类型的对象引用。任何实现了所声明接口的类实例都可以通过这种变量进行引用。当我们通过这些引用之一调用方法时，将根据所引用的接口的实际实例来调用正确的版本。

这是接口的重要特性之一。要执行的方法将在运行时动态查找，这允许类在调用其方法的代码之后才创建。调用代码可以通过接口进行分发，而无需了解“被调用者”的任何信息。这个过程类似于使用父类引用来访问子类对象。

由于在运行时动态查找方法与 Java 中的普通方法调用相比会产生巨大的开销，因此我们应该注意不要在性能敏感的代码中随意使用接口。

### 示例 9.3

```java
interface Math_function {
    void display(int x);
}

class Sqrt implements Math_function {
    public void display(int x) {
        System.out.println("sqrt of x ="+Math.sqrt(x));
    }
}

class Log implements Math_function {
    public void display(int x) {
        System.out.println("log of x = "+Math.log(x));
    }
}

class Math_Demo {
    public static void main(String args[]) {
        Math_function f1 = new Sqrt();
        Math_function f2 = new Log();
        f1.display(27);
        f2.display(3);
        Math_function f3;
        f3 = f1; // polymorphism (assign the reference)
        f3.display(30);
        f3 = f2; // polymorphism (assign the reference)
        f3.display(5);
    }
}
```

输出：![](img/image1234.jpeg)

## 接口的特性

- 接口是一个关键字。
- 接口可以声明为抽象的，但它本身就是抽象的，因此不需要添加 `abstract` 关键字。
- 所有变量始终是 `public static final`。
- 接口的所有方法必须在类中实现。
- 接口仅包含方法的声明。
- 接口方法不能声明为 `static`。它们始终被声明为实例方法。
- 类既不能缩小接口方法的访问权限，也无法在 `throws` 子句中指定新的异常；尝试这样做等同于修改接口，这是非法的。重写方法的标准也适用于实现接口方法。
- 这里允许使用 `abstract` 关键字进行部分实现。
- 无论类直接或间接实现了多少接口，它对一个在接口中可能有多个声明的方法提供单一的实现。
- 在类的情况下，方法原型声明也可以进行重载。
- 接口常量可以通过任何客户端（类或接口）使用其完全限定名来访问，无论该客户端是否扩展或实现了该接口。然而，如果客户端实现此接口的类或扩展此接口的接口，则客户端也可以不使用完全限定名访问此类常量。此类客户端继承了接口常量。
- 在接口多继承的情况下，任何名称冲突可以使用相关常量的完全限定名解决。

**接口变量**：接口中的所有变量始终是 `public static final`，因为它们是实现类访问数据类型和方法的公共部分。

**接口变量的内存管理**：静态变量在程序加载时始终获取内存，占用独立的内存且不与任何对象的内存共享。它们也被称为常量变量。可以使用接口名和 `.` 直接访问它们。

### 示例 9.4

```java
interface Static_Var {
    int sun=1;
    int mon=2;
    int tues=3;
    int wed=4;
    int thurs=5;
    int fri=6;
    int sat=7;
}

class Week_Day implements Static_Var {
    public static void main(String args[]) {
        System.out.println(sun);
        System.out.println(mon);
        System.out.println(tues);
        System.out.println(wed);
        System.out.println(thurs);
        System.out.println(fri);
        System.out.println(sat);
    }
}
```

```java
System.out.println(Static_Var.thurs);
System.out.println(Static_Var.fri);
System.out.println(Static_Var.sat);
```

输出:

```
1
2
3
4
5
6
7
```

### 示例 9.5

```java
interface Two_Methods {
    void m1();
    void m2();
}

class Three_Methods implements Two_Methods {
    public void m1() {
        // body of m1;
    }
    public void m2() {
        // body of m2;
    }
    public void m3() {
        // body of m3;
    }
}

class Methods_Demo {
    public static void main(String args[]) {
        Two_Methods tm1 = new Three_Methods();
        tm1.m1();
        tm1.m2();
        // tm1.m3(); error
        Three_Methods tm2 = new Three_Methods();
        tm2.m3();
    }
}
```

注：这里我们无法使用接口引用调用 `m3()`，因为 `m3()` 没有在接口中声明。因此，接口引用只能访问在接口中声明的方法。否则，我们可以调用同类对象或扩展类对象。

### 示例 9.6 在类中实现的两个接口

```java
interface Two_Methods {
    void push(int x);
    int pop();
}

interface One_Method extends Two_Methods {
    void m3();
}

class Three_Methods implements One_Method {
    int arr[] = new int[5];
    int top = -1;

    public void push(int item) {
        if (top == 4) {
            System.out.println("Overflow");
            return;
        }
        top++;
        arr[top] = item;
    }

    public int pop() {
        if (top == -1) {
            System.out.println("Underflow");
            return -1;
        }
        int item = arr[top];
        top--;
        return (item);
    }

    void disp() {
        for (int i = top; i >= 0; i--) {
            System.out.println(arr[i]);
        }
    }
}

class Stack_Demo {
    public static void main(String args[]) {
        Three_Methods s1 = new Three_Methods();
        s1.pop();
        for (int i = 0; i < 5; i++) {
            s1.push(i + 10);
        }
        s1.push(60);
        System.out.println("----Display All Item----");
        s1.disp(); // non methods
        System.out.println("----Removing All Items----");
        for (int i = 0; i < 5; i++) {
            System.out.println(s1.pop()); // -1 underflow
        }
        Two_Methods t1 = new Three_Methods();
        t1.push(10);
        System.out.println(t1.pop());
        // t1.disp(); error
    }
}
```

**非接口方法**：当任何类实现了接口的方法，同时在类中定义了未在接口中声明的额外方法，我们可以说这些额外方法为非接口方法。使用接口引用变量无法调用这些额外方法。

输出:

```
Underflow
Overflow
----Display All Item----
104
103
102
101
100
----Remove All Items----
104
103
102
101
100
10
```

![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg)

![STAR-LOGO-2013](img/img/image01213.jpeg)

# 章节 10 (String 和 StringBuffer)

## 引言

在 Java 中，`String` 是类对象，并通过两个类实现，即 `String` 和 `StringBuffer`。与 C 语言字符串相比，Java 的 `String` 更可靠且可预测。这基本上是因为 C 语言缺乏边界检查。Java 的 `String` 不是字符数组，也不是以 NULL 结尾的。通常情况下，Java 不允许将运算符应用于 `String` 对象。

该规则的唯一例外是 `+` 和 `+=` 运算符，它们可以连接两个字符串并产生一个 `String` 对象。在 Java 中，字符数组不被视为字符串。Java 的 `String` 类用于执行所有的字符串操作。`String` 类和 `StringBuffer` 类是 `java.lang` 包的一部分。

## String 类

```java
String s1 = new String("matrix");
String s2 = "matrix";
System.out.println(s1);
System.out.println(s1.length());
System.out.println("matrix".length());
```

`String` 在 Java 中具有以下特性：

### [i] String 在 Java 中是一个对象

`String` 表示一个字符序列，但与其他许多使用字符数组实现 `String` 的语言不同，Java 将字符串实现为 `String` 类型的对象。

字符串操作是许多 Java 程序中最常见的部分。将字符串实现为内置对象允许 Java 提供全方位的特性，使得字符串处理变得方便。此外，字符串对象可以通过多种方式构建，以便在需要时易于获取字符串。

### [ii] String 是不可变的

`String` 是不可变的，也就是说我们无法在创建后更改字符串。然而，声明为 `String` 引用的变量可以随时更改指向其他字符串对象。

我们仍然可以执行所有类型的字符串操作。每当我们需要一个现有字符串的修改版本时，都会创建一个包含修改内容的新字符串对象。

原始字符串保持不变。使用这种方法是因为固定的、不可变的字符串可以比可变的字符串实现得更高效。

对于那些需要修改字符串的情况，有一个名为 `StringBuffer` 的伴随类，其对象包含可以在创建后进行修改的字符串。

### [iii] String 类是 final 的

`String` 和 `StringBuffer` 类都是 `final` 的。这意味着我们不能在其他类中扩展 `String` 类。这允许某些优化，以提高常用字符串操作的性能。

## String 类的构造函数与方法

| # | 方法 | 描述 | 示例 |
|:---:|---|---|:---|
| 1 | `public String()` | 初始化新创建的 `String` 对象，使其表示空字符序列。 | `String s1 = new String();` |
| 2 | `public String(String str)` | 初始化新创建的 `String` 对象，使其表示与参数相同的字符序列；换句话说，新创建的字符串是参数字符串的拷贝。 | `String s1 = new String("Matrix"); String s2 = new String(s1);` 字符串 `s2` 是字符串 `s1` 的拷贝。尽管内容相同，但 `s1` 和 `s2` 指向不同的字符串对象。 |
| 3 | `public String(char ch[])` | 分配一个新的 `String`，表示字符数组参数当前包含的字符序列。 | `char ch[] = {'a', 'b', 'c'}; String s1 = new String(ch);` // `s1` 将持有 "abc" |
| 4 | `public String(char value[], int offset, int count)` | 分配一个新的 `String`，包含来自字符数组参数子数组的字符。 | `char ch[] = {'a', 'b', 'c', 'd', 'e', 'f'}; String s1 = new String(ch,2,3);` // `s1` 将持有 "cde" |
| 5 | `public String(int value[], int offset, int count)` | 分配一个新的 `String`，包含来自包含字符 Unicode 的整数数组参数子数组的字符。 | `int a[] = {97, 98, 99, 100, 101, 102}; String s1 = new String(a,2,3);` // `s1` 将持有 "cde" |
| 6 | `public String(byte b[], int offset, int count)` | 使用平台默认字符集解码指定的字节子数组以构造新的 `String`。 | `byte b[] = {97, 98, 99, 100, 101, 102}; String s1 = new String(b,2,3);` // `s1` 将持有 "cde" |
| 7 | `public String(byte[])` | 使用平台默认字符集解码指定的字节数组以构造新的 `String`。 | `byte b[] = {97, 98, 99}; String s1 = new String(b);` // `s1` 将持有 "abc" |
| 8 | `public String(StringBuffer)` | | |
| 9 | `public int length()` | 显示字符串的字符数量。 | |
| 10 | `public boolean isEmpty()` | 如果字符串为空，则显示 true，否则显示 false。 | `String s1 = new String(); System.out.println(s1.isEmpty());` |



# String 方法参考（续）

| 序号 | 方法 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| 11 | `public char charAt(int index)` | 返回指定索引处的字符值。索引范围从 0 到 `length()`–1。 | `String s1 = "matrix"; System.out.println(s1.charAt(0));` // 输出 "m" |
| 12 | `public void getChars(int srcBegin, int srcEnd, char[] dst, int dstBegin)` | 将字符从此字符串拷贝到目标数组。 | |
| 13 | `public void getBytes(int srcBegin, int srcEnd, byte dst[], int dstBegin)` | | |
| 14 | `public byte[] getBytes()` | 使用平台默认字符集将字符串编码为字节序列。 | |
| 15 | `public boolean equals(Object)` | 将调用字符串与指定对象。当参数不为空且是表示调用字符串相同字符序列的 `String` 对象时，结果为 true。 | |
| 16 | `public boolean equalsIgnoreCase(String)` | 在忽略大小写的情况下比较调用字符串与另一个字符串。 | |
| 17 | `public int compareTo(String)` | 按字典顺序比较调用字符串与作为参数的字符串。 | |
| 18 | `public int compareToIgnoreCase(String)` | 在忽略大小写的情况下按字典顺序比较两个字符串。 | |
| 19 | `public boolean regionMatches(int startIndex, String str2, int str2StartIndex, int len)` | 测试两个字符串区域是否相等。 | |
| 20 | `public boolean regionMatches(Boolean ignoreCase, int startIndex, String str2, int str2StartIndex, int len)` | 测试两个字符串区域是否相等。如果 `ignoreCase` 标志为 true，则忽略大小写差异。 | |
| 21 | `public boolean startsWith(String prefix, int startIndex)` | 测试此字符串从指定索引开始是否以指定的前缀开头。 | |

## String 方法参考

| 方法 | 描述 |
| :--- | :--- |
| `public boolean startsWith(String)` | 测试此字符串是否以指定的前缀开头。 |
| `public boolean endsWith(String suffix)` | 测试此字符串是否以指定的后缀结尾。 |
| `public int indexOf(char ch)` | 返回指定字符在此字符串中第一次出现的索引。 |
| `public int indexOf(char ch, int fromIndex)` | 从指定的索引开始搜索，返回指定字符在此字符串中第一次出现的索引。 |
| `public int indexOf(String str)` | 返回指定子字符串在此字符串中第一次出现的索引。 |
| `public int indexOf(String str, int fromIndex)` | 从指定的索引开始搜索，返回指定子字符串在此字符串中第一次出现的索引。 |
| `public int lastIndexOf(int ch)` | 返回指定字符在此字符串中最后一次出现的索引。 |
| `public int lastIndexOf(int ch, int fromIndex)` | 从指定的索引开始向后搜索，返回指定字符在此字符串中最后一次出现的索引。 |
| `public int lastIndexOf(String str)` | 返回指定子字符串在此字符串中最后一次出现的索引。 |
| `public int lastIndexOf(String str, int fromIndex)` | 从指定的索引开始向后搜索，返回指定子字符串在此字符串中最后一次出现的索引。 |
| `public String substring(int)` | 获取从第 n 个字符开始的子字符串 |
| `public String substring(int n, int m)` | 获取从第 n 个字符开始到第 m 个字符（不包含第 m 个）的子字符串 |
| `public String concat(String str)` | 将字符串 `str` 拼接调用字符串对象的末尾。 |
| `public String replace(char x, char y)` | 将所有的 `x` 替换为 `y` |
| `public String replaceFirst(String, String)` | |
| `public String replaceAll(String, String)` | |
| `public String toLowerCase()` | 将字符串转换为小写 |
| `public String toUpperCase()` | 将字符串转换为大写 |
| `public String trim()` | 去除开头和结尾的空格 |
| `public char[] toCharArray()` | 将调用的字符串转换为新的字符数组。提供此函数是为了方便，因为可以使用 `getChars()` 达到相同的结果 |
| `public static String valueOf(Object)` | 创建参数 `p`（简单类型或对象）的字符串对象 |

## 字符串数组

我们也可以创建并使用包含字符串的数组。

### 示例 10.1

```java
import java.util.Scanner;
class StringArrSort {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter how many names ");
        int n = sc.nextInt();
        String s[] = new String[n];
        // input
        for (int i = 0; i < n; i++) {
            System.out.println("Enter " + (i + 1));
            s[i] = sc.next();
        }
        // sorting
        for (int i = 0; i < n - 1; i++) {
            for (int j = i + 1; j < n; j++) {
                if (s[i].compareTo(s[j]) > 0) {
                    String t = s[i];
                    s[i] = s[j];
                    s[j] = t;
                }
            }
        }
        // output
        for (int i = 0; i < n; i++) {
            System.out.println(s[i]);
        }
    }
}
```

## 字符串转换与 toString()

当 Java 在拼接过程中将数据转换为其字符串表示时，它是通过调用 `String` 类定义的字符串转换方法的重载版本 `valueOf()` 实现的。`valueOf()` 是一个静态方法，针对所有简单类型和 `Object` 类型进行了重载。

对于简单类型，`valueOf()` 返回一个包含调用值的人类可读等价值的字符串。对于对象，`valueOf()` 会调用对象上的 `toString()` 方法。

每个类都继承 `toString()`，因为它是由 `Object` 类定义的。然而，`toString()` 的默认实现很少是足够的。它显示类名，后跟符号“@”，然后是对象 ID（例如 `Box@ab1342`），这通常没有用处。对于我们创建的大多数重要类，我们希望重写 `toString()` 并提供我们自己的字符串表示。

### 示例 10.2

```java
class A {
    private int x,y;
    A() {
        x = y = 0;
    }
    A(int x1, int y1) {
        x = x1;
        y = y1;
    }
}
class ToStringTest {
    public static void main(String args[]) {
        A a1 = new A(5,6);
        System.out.println(a1); // 调用了 Object 类的 toString()
        String s1="Object a1 is " + a1; // 对象与字符串拼接
        //再次调用了 Object 的 toString()
        System.out.println(s1);
    }
}
```

**输出:**

```
A@3e25a5
Object a1 is A@3e25a5
```

### 示例 10.3

```java
class A {
    private int x,y;
    A() {
        x = y = 0;
    }
    A(int x1, int y1) {
        x = x1;
        y = y1;
    }
    public String toString() {
        return (x + "," + y);
    }
}
class ToStringTest2 {
    public static void main(String args[]) {
        A a1 = new A(5,6);
        System.out.println(a1); // 调用了 A 类的 toString()
        String s1="Object a1 is " + a1; // 对象与字符串拼接
        //再次调用了 A 的 toString()
        System.out.println(s1);
    }
}
```

**输出:**

```
5,6
Object a1 is 5,6
```

### 示例 10.4

```java
import java.util.*;
class FindTest {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        String s1,s2;
        System.out.print("Enter a string");
        s1=sc.next();
        System.out.print("Enter string to search");
        s2=sc.next();
        int ans = s1.indexOf(s2);
        if(ans == -1)
            System.out.println("Not Found");
        else
            System.out.println("found at pos " + ans);
    }
}
```

## StringBuffer

`StringBuffer` 是 `String` 的对等类，提供了 `String` 的大部分功能。众所周知，`String` 代表固定长度且不可变的字符序列。与 `String` 不同，`StringBuffer` 代表可增长和可写的字符序列。`StringBuffer` 可以在中间插入或在末尾追加字符和子字符串。

`StringBuffer` 会自动扩展以为此类添加留出空间，通常分配的字符比实际需要的更多，以便允许增长。Java 频繁使用该类，但许多程序员通过重载的 `+` 运算符在后台操作 `StringBuffer`。

### 关于 `StringBuffer` 类的要点

- `StringBuffer` 类似于 `Object` 类。
- `StringBuffer` 类也是 `final` 类，类似于 `String` 类。
- `StringBuffer` 对象是可变的（可以修改），与 `String` 对象不同。

### `StringBuffer` 构造函数和方法

| 方法 | 描述 |
| :--- | :--- |
| `public StringBuffer()` | 默认构造函数，不重新分配地预留 16 个字符的空间。 |
| `public StringBuffer(int)` | 该构造函数接受一个整数参数，显式地设置缓冲区的大小。 |
| `public StringBuffer(String)` | 该构造函数接受一个 `String` 参数，设置 `StringBuffer` 对象的初始内容并在不重新分配的情况下预留 16 个字符。 |
| `public synchronized int length()` | 返回当前长度。 |
| `public synchronized int capacity()` | 返回当前容量，即新插入字符的可用存储空间。 |
| `public synchronized void ensureCapacity(int)` | 确保容量至少等于指定的最小值。如果我们预先知道将追加大量字符串，可以使用 `ensureCapacity()` 方法来预先留出空间。 |
| `public synchronized void trimToSize()` | 移除多余空间。现在容量将等于 `length`。 |
| `public synchronized void setLength(int newLength)` | 设置字符序列的长度。如果调用 `setLength()` 传入的值小于 `length()` 返回的值，则新长度之外字符将会丢失。 |
| `public synchronized char charAt(int index)` | 返回序列中指定索引处的 `char` 值。 |
| `public synchronized void getChars(int srcBegin, int srcEnd, char[] dst, int dstBegin)` | 从此序列复制字符到目标数组 `dst`。第一个拷贝的字符位于索引 `srcBegin`；最后一个位于索引 `srcEnd-1`。拷贝的字符总数为 `srcEnd-srcBegin`。确保目标数组足够大以容纳从 `dstBegin` 开始的字符。 |
| `public synchronized void setCharAt(int index, char ch)` | 将指定索引处的字符设置为 `ch`。如果索引为负或大于等于 `length()`，则发生 `IndexOutOfBoundsException`。 |
| `public synchronized StringBuffer append(Object)` | `append` 方法将任何其他类型的字符串表示追加到 `StringBuffer` 对象的末尾。 |
| `public synchronized StringBuffer delete(int start, int end)` | 删除从 `start` 到 `end-1` 的字符。 |
| `public synchronized StringBuffer deleteCharAt(int index)` | 删除指定位置的字符。 |
| `public synchronized StringBuffer replace(int start, int end, String str)` | 将 `start` 到 `end-1` 的字符替换为指定 `String` 中的字符。 |
| `public synchronized String substring(int)` | 返回一个新的 `String`，包含此序列中包含的子序列。子字符串从指定索引开始到此序列末尾。 |
| `public synchronized String substring(int start, int end)` | 返回一个新的 `String`，包含此序列中包含的子序列。子字符串从指定的 `start` 开始到 `end-1` 字符结束。 |
| `public synchronized StringBuffer insert(int, Object)` | 将一个 `String` 插入另一个 `String` 中。它被重载以接受所有简单类型和 `Objects`。 |
| `public int indexOf(String)` | |
| `public int indexOf(String, int)` | |
| `public int lastIndexOf(String)` | |
| `public int lastIndexOf(String, int)` | |
| `public synchronized StringBuffer reverse()` | 反转 `StringBuffer` 的内容。 |

### 示例 1.5



```java
import java.util.Scanner;

class SortStr {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a string");
        StringBuffer sb1 = new StringBuffer(sc.next());
        //Sorting
        for(int i=0; i<sb1.length()-1; i++) {
            for(int j=i+1; j<sb1.length(); j++) {
                if(sb1.charAt(i) > sb1.charAt(j)) {
                    char t=sb1.charAt(i);
                    sb1.charAt(i,sb1.charAt(j));
                    sb1.charAt(j,t);
                }
            }
        }
        System.out.println(sb1);
    }
}
```

**输出：** Enter a string SHIVAM $\rightarrow$ AHIMSV

### 示例 10.6：统计句子中单词数的程序。

```java
class WordCnt {
    public static void main(String args[]) {
        String s1 = "Mohan Das  Karam  Chand  Gandhi";
        boolean flag=false;
        int cnt=0;
        for(int i=0; i<s1.length(); i++) {
            if(s1.charAt(i) == ' ') {
                flag = false;
            } else {
                if(flag == false) {
                    cnt++;
                    flag = true;
                }
            }
        }
    }
}
```

```java
System.out.print("No. of Words=" + cnt);
```

Output: No. of Words=5

![STAR-LOGO-2013](img/image01213.jpeg)

## 第 11 章：异常处理

### 引言

异常（Exception）是由程序中的运行时错误导致的条件，它会破坏程序的正常流程。当 Java 解释器遇到如整数除以零之类的错误时，它会创建一个 `Exception` 对象并将其抛出（即通知我们发生了错误）。

每当运行时发生异常时，Java 异常/错误都是 `Exception` 类或其任一子类的对象。异常对象包含了有关异常的详细信息，可以使用为此目的提供的公共方法来访问这些信息。

在某些较旧的语言中，我们必须使用 `if`、`goto` 和 `return` 码来进行错误处理。

异常是代码序列在运行时出现的异常状态。换句话说，异常是一种运行时错误。在不支持异常处理的计算机语言中，必须手动检查并处理错误——通常通过使用错误代码等。

这种方法既繁琐又麻烦。Java 的异常处理避免了这些问题，并在过程中将运行时错误管理引入了面向对象的世界。

### 异常处理基础

Java 异常是一个对象，描述了代码中发生的异常（即错误）条件。当出现异常条件时，会在引起错误的方法中创建并抛出一个代表该异常的对象。该方法可以选择自己处理该异常，也可以将其传递下去。

无论何种方式，异常在某一点会被捕获并处理。异常可以由 Java 运行时系统生成，也可以由你的代码手动生成。Java 抛出的异常与违反 Java 语言规则或 Java 执行环境限制的底层错误有关。手动生成的异常通常用于向方法的调用者报告某些错误状态。

Java 异常处理通过五个关键字管理：`try`、`catch`、`throw`、`throws` 和 `finally`。简而言之，它们的工作原理如下：你想要监控异常的程序语句包含在 `try` 块中。如果 `try` 块内部发生异常，异常会被抛出。你的代码可以捕获此异常（使用 `catch`）并以某种方式处理它。系统生成的异常由 Java 运行时自动抛出。要手动抛出异常，请使用关键字 `throw`。任何抛出方法的异常都必须由 `throws` 子句指定。任何在 `try` 块完成后绝对必须执行的代码都放在 `finally` 块中。

这是异常处理块的一般形式：

```java
try {
    // 用于监控错误的代码块
} catch (Exception ex) {
    // 异常处理器
} .........
finally {
    // 在 try 结束后必须执行的代码块
}
```

### 异常类型

所有异常类型都是内置类 `Throwable` 的子类。因此，`Throwable` 位于异常层次结构的顶端。紧邻 `Throwable` 之下有两个子类，它们将异常分为两个不同的分支。一个分支由 `Exception` 引导。该类用于用户程序应该捕获的异常条件。你也将通过子化该类来创建自己的异常类型。`Exception` 有一个重要的子类，称为 `RuntimeException`。这种类型的异常会为你编写的程序自动定义，包括如除以零和无效数组索引等内容。

另一个分支由 `Error` 引导，它定义了在正常情况下不期望你的程序捕获的异常。`Error` 类型的异常由 Java 运行时系统使用，指示与运行时环境本身相关的错误。`Stack overflow`（栈溢出）就是此类错误的示例。本章将不会处理 `Error` 异常，因为这些异常通常是为了灾难性故障创建的，你的程序通常无法处理。

顶层异常层次结构所示：

![](img/image01235.jpeg)

#### 示例 11.1

```java
class ErrorTest1 {
    public static void main(String args[]) {
        int a=5,b=2,c=2,d;
        d=a/(b-c); // 发生了 ArithmeticException(Divide by zero)
        System.out.println(d);
        System.out.println("This will not be printed");
    }
}
```

程序将在除法操作期间终止，而不执行剩余的语句。

### 示例 1.2

```java
class A {
    void display() {
    }
}
class ErrorTest2 {
    public static void main(String args[]) {
        A a1=null;
        a1.display(); // 发生了 NullPointerException
    }
}
```

在上述程序中将发生 `NullPointerException`。引用变量没有用 `new` 初始化。在这种情况下程序也会终止。

#### 示例 11.3

```java
class ErrorTest3 {
    public static void main(String args[]) {
        int a[] = {10,20,30};
        System.out.println(a[3]); // 发生了 ArrayIndexOutOfBoundsException
    }
}
```

在上述情况下，数组长度为 3，索引从 0 到 2，所以如果我们打印 `a[3]`，那么这就是第 4 个元素，不是有效的索引。这将产生一个异常错误。在 C/C++ 中这是允许的，但在 Java 中不允许。

### 注意

JDK 7 增加了 `try` 语句的新形式，支持自动资源管理。这种新的 `try` 形式称为 try-with-resources，在文件章节中描述了它，因为文件是常用资源之一。

如果异常对象没有被正确捕获和处理，解释器将显示错误信息并终止程序。如果我们想继续执行剩余代码，那么我们应该尝试捕获由错误条件抛出的异常对象。

## 异常处理

此任务被称为异常处理。异常处理机制的目的是一种检测和报告“异常情况”的手段，以便采取适当的措施。该机制建议引入单独的错误处理代码，用以执行以下任务：

1. 发现问题（发生异常）。
2. 通知错误已发生（`throw` 异常）。
3. 接收错误信息（`catch` 异常）。
4. 采取纠正措施（处理异常）。

## Java 关键字

Java 异常处理通过五个关键字管理：`try`、`catch`、`throw`、`throws` 和 `finally`。

我们想要监控异常的程序语句包含在 `try` 块中，每当发生错误时，它就会被抛到 `catch` 块中。我们的代码可以捕获此异常（使用 `catch`）并以某种合理的方式处理它。系统生成的异常由 Java 运行时系统自动抛出。

要手动抛出异常，请使用 `throw` 关键字。任何抛出方法的异常都必须通过 `throws` 子句进行指定。任何在方法返回之前必须执行的代码放在 `finally` 块中。

## try 块

`try` 块必须封装在括号之间，即使它只有一个语句。可以有一个或多个 `catch` 语句，以及零或一个 `finally` 语句。`catch` 和 `finally` 块都是可选的，但必须至少有一个 `catch` 块或一个 `finally` 块。

`try` 块中的代码像任何其他 Java 代码一样执行。如果 `try` 块中的代码执行成功，控制将转移到 `finally` 块（如果存在），然后从 `finally` 块结束后的语句继续执行（即 `try` 语句结束之后）。如果不存在 `finally` 块，执行将从最后一个 `catch` 块结束后的语句继续（即 `try` 语句结束之后）。

如果在执行 `try` 块中的代码时发生某些运行时错误，JVM 将抛出一个 `Exception Error`。这意味着将根据运行时错误的类型创建一个 `Exception Error` 类型的对象或其子类之一。然后按照从上到下的顺序与 `catch` 块中的 `Exception`/`Error` 类型进行比较。

如果找到匹配的 `catch` 块，则处理该异常/错误，即程序不会终止。执行将从 `catch` 块中的第一个语句继续。在完成 `catch` 块后，执行将从 `try` 和 `catch` 语句结束后的语句继续。

无论有多少个 `catch` 块，最多只有一个 `catch` 块会被执行。如果异常/错误与任何 `catch` 块的异常/错误类型都不匹配，则我们称其未被处理。

执行将立即从 `try` 块返回。即使异常/错误未被处理，`finally` 块中的代码也将被执行。

如果有外层 `try` 块，异常/错误将由其处理，否则必须在调用当前方法的的方法中被处理。

异常/错误将沿层次结构向上传递，直到被处理，或者即使在 `main()` 方法（执行执行开始的第一个方法）中未被处理，也会作为未处理异常传递给 JVM。

JVM 然后简单地终止程序并在显示器/控制台上显示异常/错误的细节。

## 使用 try 和 catch

尽管 Java 运行时系统提供的默认异常处理器对于调试很有用，但你通常希望自己处理异常。这样做有两个益处：首先，它允许你修复错误；其次，它防止程序自动终止。如果你的程序每次发生错误就停止运行并打印堆栈跟踪，大多数用户会感到困惑（至少是这样）！幸运的是，防止这一点很容易。

为了防止和处理运行时错误，只需将你想要监控的代码封装在 `try` 块中。紧随 `try` 块之后，包含一个 `catch` 子句，指定你想要 `catch` 的异常类型。

为了说明如何轻松地完成这一点，以下程序包含一个 `try` 块和一个 `catch` 子句，用于处理由除零错误产生的 `ArithmeticException`：

```java
class Exc2 {
    public static void main(String args[]) {
        int d, a;
        try {
            // 监控一段代码。
            d = 0;
            a = 42 / d;
            System.out.println("This will not be printed.");
        } catch (ArithmeticException e) {
            // 捕获除零错误
            System.out.println("Division by zero.");
        }
        System.out.println("After catch statement.");
    }
}
```

该程序产生以下输出：

```
Division by zero.
After catch statement.
```

注意，`try` 块内部的 `println()` 调用从未被执行过。一旦抛出异常，程序就会跳出 `try` 块进入 `catch` 块。因此，`println()` 未被调用。`catch` 的范围限制在 `try` 指定的语句上。

构建良好的 `catch` 子句的目标应该是解决异常情况然后继续。例如，在下一个程序中，`for` 循环的每次迭代都会获取两个整数。这两个整数相互相除，结果存入 `a` 中。如果任何一个操作导致除零错误，它将被捕获，`a` 的值设置为零，然后程序继续。

### 处理异常并继续。

```java
import java.util.Random;

class HandleError {
    public static void main(String args[]) {
        int a=0, b=0, c=0;
        Random r = new Random();
        for(int i=0; i<3000; i++) {
            try {
                b = r.nextInt();
                c = r.nextInt();
                a = 12345 / (b/c);
            } catch (ArithmeticException e) {
                System.out.println("Division by zero.");
                a = 0; // 设置 a 为零并继续
            }
            System.out.println("a: " + a);
        }
    }
}
```

## 显示异常描述

`Throwable` 重写了由 `Object` 定义的 `toString()` 方法，使其返回一个包含异常描述的字符串。你可以通过简单将异常作为参数在 `println()` 语句中显示此描述。例如，上述程序中的 `catch` 块可以重写为：

```java
catch (ArithmeticException e) {
    System.out.println("Exception: " + e);
    a = 0; // 设置 a 为零并继续
}
```

当用此版本替换程序并运行程序时，每个除零错误都会显示以下消息：

`Exception: java.lang.ArithmeticException: / by zero`

虽然这在这种语境下没有特殊价值，但显示异常描述在其他情况下非常有价值——特别是当你正在尝试异常或进行调试时。

| 异常类型 | 异常原因 |
| :--- | :--- |
| `ArithmeticException` | 算术错误，如 - 除以 0 |
| `ArrayIndexOutOfBoundsException` | 数组索引越界 |
| `ArrayStoreException` | 在数组中存储了错误类型的数据 |
| `FileNotFoundException` | 访问不存在的文件 |
| `IOException` | 无法从文件中读取 |
| `NullPointerException` | 由引用空对象引起 |
| `NumberFormatException` | 字符串与数字转换失败 |
| `OutOfMemoryException` | 内存不足，无法分配新对象 |
| `SecurityException` | Applet 尝试执行浏览器安全设置不允许的操作 |
| `StackOverflowException` | 系统栈空间耗尽 |
| `StringIndexOutOfBoundsException` | 程序尝试访问字符串中不存在的字符位置 |

## Java 内置异常

在标准包 `java.lang` 中，Java 定义了多个异常类。其中一些在之前的示例中已经用过。这些异常中最通用的是其标准类型 `RuntimeException` 的子类。



正如之前解释的，这些异常不需要包含在任何方法的 `throws` 列表中。在 Java 语言中，这些异常被称为**未检查异常**（unchecked exceptions），因为编译器不会检查方法是否处理或抛出了这些异常。在 `java.lang` 中定义的未检查异常如表 -1 所示。表 -2 列出了由 `java.lang` 定义的异常，如果该方法可能产生此类异常且自身不进行处理，则必须将其包含在方法的 `throws` 列表中。这些被称为**检查异常**（checked exceptions）。Java 还定义了其他与其各种类库相关的异常类型。

![ss](img/image01236.jpeg)

# 异常处理机制

![](img/image01237.jpeg)

## 语法

```java
try {
    statement; // 生成异常
} catch (Exception-type e) {
    statement; // 处理异常
}
```

## 多个 catch 子句

在某些情况下，单段代码可能会抛出多个异常。为了处理这种情况，你可以指定两个或多个 catch 子句，每个子句捕获不同类型的异常。

当异常被抛出时，会按顺序检查每个 catch 语句，并执行第一个与异常类型匹配的语句。在一个 catch 语句执行后，其他 catch 语句将被跳过，执行将在 `try / catch` 块之后继续。下面的示例捕获了两种不同的异常类型：

```java
// 演示多个 catch 语句。
class MultipleCatches {
    public static void main(String args[]) {
        try {
            int a = args.length;
            System.out.println("a = " + a);
            int b = 42 / a;
            int c[] = {1};
            c[2] = 99;
        } catch (ArithmeticException e) {
            System.out.println("Divide by 0: " + e);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array oob: " + e);
        }
        System.out.println("After try/catch blocks.");
    }
}
```

如果程序在没有命令行参数的情况下启动，它将导致除以零异常，因为 `a` 等于 0。如果你提供了命令行参数，将 `a` 设置为大于 0 的值，程序将正常运行。但它会导致 `ArrayIndexOutOfBoundsException`，因为 int 数组 `c` 的长度为 1，但程序却尝试给 `c[2]` 赋值。

以下是两种运行方式生成的输出：

```
C:\java MultipleCatches
a = 0
Divide by 0: java.lang.ArithmeticException: / zero
After try/catch blocks.

C:\java MultipleCatchesArg
a = 1
Array oob: java.lang.ArrayIndexOutOfBoundsException:2 After try/catch blocks
```

在使用多个 catch 语句时，必须记住：**异常子类必须在其任何父类之前**。这是因为使用父类的 catch 语句会捕获该类型的异常以及它的任何子类异常。因此，如果子类在父类之后，它将永远无法被访问。此外，在 Java 中，不可达代码是一个错误。例如，考虑以下程序：

```java
/* 此程序包含一个错误。
在系列 catch 语句中，子类必须排在其父类之前。如果不是，
将创建不可达代码并导致编译时错误。 */
class SuperCatch {
    public static void main(String args[]) {
        try {
            int a = 0;
            int b = 42 / a;
        } catch (Exception e) {
            System.out.println("Generic catch.");
        } /* 这个 catch 永远不会被到达，因为 ArithmeticException 是 Exception 的子类。 */
        catch (ArithmeticException e) { // 错误 – 不可用
            System.out.println("This is never reached.");
        }
    }
}
```

如果你尝试编译此程序，将收到一条错误消息，说明第二个 catch 语句是不可达的，因为异常已经被捕获。由于 `ArithmeticException` 是 `Exception` 的子类，第一个 catch 语句将处理所有基于 `Exception` 的错误，包括 `ArithmeticException`。要修复这个问题，请交换 catch 语句的顺序。

## 嵌套 try 语句

`try` 语句可以嵌套。也就是说，一个 `try` 语句可以位于另一个 `try` 块内部。每当进入一个 `try` 语句，该异常的上下文就会推入栈。

如果内部 `try` 语句没有针对特定异常的 catch 处理器，栈将回溯并检查下一个 `try` 语句的 catch 处理器是否匹配。这将一直持续，直到某个 catch 语句执行成功，或者耗尽所有的嵌套 `try` 语句。如果没有 catch 语句匹配，Java 运行时系统将处理该异常。

### 多个 catch 语句语法

当存在多个 catch 语句时，就称为多个 catch 语句。

```java
try {
    statement; // 生成异常
} catch (Exception-type-1 e) {
    statement 1; // 处理类型 1
} catch (Exception-type-2 e) {
    statement 2; // 处理类型 2
} catch (Exception-type-n e) {
    statement n; // 处理类型 n
}
```

### 示例 1.4

```java
class ErrorTest {
    public static void main(String args[]) {
        int a=10,b=2,c=2,d;
        System.out.println("Before Exception ");
        d=a/(b-c);
        System.out.println("After Exception ");
    }
}
```

输出：

![](img/image01238.jpeg)

在这里我们没有捕获异常，因此程序会在显示消息“Before Exception”后终止。现在我们使用异常处理来解决这个问题。

### 示例 11.5

```java
class ErrorTest5 {
    public static void main(String args[]) {
    }
}
```

![](img/image01239.jpeg)

## 异常的优势

- 我们可以很容易地确定异常/错误将在哪里处理。异常/错误在运行时沿调用堆栈向上传播——首先到达外层的 `try` 块，然后返回到调用者方法——直到异常处理器 `catch` 捕获它们。
- 异常/错误的位置是确定的，因为用户可以获取完整的堆栈跟踪信息。这对于调试非常有帮助。
- 程序员有机会从错误/异常状态中恢复过来。
- 错误处理代码与正常程序流分离，以提高可读性和可维护性。
- 在 Java 中，无需测试是否会发生异常/错误情况。添加更多的错误/异常处理器只需添加更多的 `catch` 子句，而无需触动原始程序流。

## 异常类的层级结构

所有 `Exception` / `Error` 类的根类是 `Throwable` 类，它是 `Object` 类的直接子类。异常/错误在 Java 中也是对象。`Exception` 的子类带有后缀 `Exception`。`Throwable` 有两个直接子类：

### Error (错误)

`Error` 类基本上用于信号异常的系统状态，这些状态通常是不可恢复的且不应该被处理：

- `OutOfMemoryError` 信号 Java 虚拟机内存耗尽，且垃圾器无法回收任何可用内存。
- `StackOverflowError` 信号解释器发生堆栈溢出。

### Exception (异常)

`Exception` 类通常是可恢复的。例如：

- `EOFException` 信号我们打开的文件没有更多数据可读。
- `FileNotFoundException` 信号我们想要打开的文件在路径中不存在。
- **检查异常 (Checked Exception)**：如果必须 `catch` 某个异常，则它被称为检查异常。如果在 `try` 块中可能发生检查异常且未被处理，则程序将无法编译。编译器确保如果一个方法可以直接或间接地 `throw` 检查异常，那么该方法必须显式地处理它。该方法要么 `catch` 异常并采取适当措施，要么将异常传递给调用者。运行时异常及其子类是未检查的。
- **未检查异常 (Unchecked Exception)**：如果不需要 `catch` 某个异常，则它被称为未检查异常。如果程序中发生了未处理的未检查异常，程序将可以编译。但如果异常被处理，程序执行将因异常在该点终止。运行时异常及其所有子类都是未检查异常，不需要捕获。所有用户定义的 `Exception` 都是检查异常。

`Exception` 类中的可用方法：

| 方法 | 说明 |
| :--- | :--- |
| `getMessage()` | 获取与异常相关的消息。 |
| `printStackTrace()` | 打印异常/错误发生处的堆栈跟踪。 |
| `toString()` | 显示异常/错误的名称以及消息。 |

### 示例 1

![](img/image240.jpeg)

```java
class Test {
    public static void main(String[] arr) {
        int a=10,b=2,c=2,d;
        try {
            System.out.println("Before Exception");
            d=a/(b-c);
            System.out.println("This Will Not Print");
        } catch(ArithmeticException e) {
            System.out.println("After Exception");
            System.out.println("error : Division by zero");
            System.out.println(e.getMessage());
            System.out.println(e); // 调用了 toString()
            e.printStackTrace();
        }
    }
}
```

输出：

```
Before Exception
After Exception
error : Division by zero
java.lang.ArithmeticException: by zero
java.lang.ArithmeticException: by zero
at Test.main(Test.java:10)
```

### 示例 2：多个 catch

```java
class ErrorTest {
    public static void main(String args[]) {
        try {
            int a=args.length;
            System.out.println("Before Exception");
            int b=5/a;
            int c[] = {};
            c[4]=10;
            System.out.println("After Exception");
        } catch(ArithmeticException e) {
            System.out.println("Divide by zero :"+e);
        } catch(ArrayIndexOutOfBoundsException e) {
            System.out.println("Array Index oob :"+e);
        }
        System.out.println("After try/catch block");
    }
}
```

输出 1：当我们使用 `java ErrorTest` 运行上述程序时

```
Before Exception
Divide by zero :java.lang.ArithmeticException: / by zero
After try/catch block
```

输出 2：当我们使用 `java ErrorTest 45` 运行上述程序时

```
Before Exception
Array Index oob :java.lang.ArrayIndexOutOfBoundsException: 47
After try/catch block
```

## 嵌套 try catch

如果我们在另一个 `try` 块中使用 `try` 和 `catch` 语句，则称之为嵌套 try catch。

### 语法

```java
try // 外层 try
{
    try // 内层 try
    {
        statement ;
    }
    catch1() // 内层 catch
    {
        statement ;
    }
    catch2() // 内层 catch
    {
        statement ;
    }
}
catch() // 外层 catch
{
    statement ;
}
```

### 示例 11.8 嵌套的 try 和 catch

```java
class Nested {
    public static void main(String args[]) {
        try {
            int a = args.length;
            int b = 58/a;
            System.out.println("a="+a);
            try {
                if (a == 1)
                    a = a/(a-a);
                if (a == 2) {
                    int c[] = {1};
                    c[42] = 100;
                }
            } catch (ArrayIndexOutOfBoundsException e) {
                System.out.println("ArrayIndex oob "+e);
            }
        } catch (ArithmeticException e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**输出 I:**

当我们以 `java Error8` 运行程序时 / 除以零

**输出 II:**

当我们以 `java Error8 10` 运行程序时

`a=1 / by zero`

**输出 III:**

当我们以 `java Error8 10 20` 运行程序时

`a=2`

`ArrayIndex oob java.lang.ArrayIndexOutOfBoundsException: 42`

## finally 语句

Java 支持另一种名为 `finally` 的语句，它可以用于处理未被之前的任何 `catch` 语句捕获的异常。`finally` 块可以用于处理在 `try` 块内部生成的任何异常。无论是否发生错误，它都会执行。它可以紧跟在 `try` 块之后，也可以跟在最后一个 `catch` 块之后，如下所示：

### 语法

```java
try
{
    // ...
}
catch (...)
{
    // ...
}
catch (...)
{
    // ...
}
finally
{
    // ...
}
```

### 示例 1.9 finally 语句



```java
class ErrorTest9 {
    public static void main(String args[]) {
        int a[] = {5,10};
        int b = 5;
        try {
            int x = a[2]/b-a[1];
        } catch (ArithmeticException e) {
            System.out.println("Division Zero");
        } catch (ArrayIndexException e) {
            System.out.println("Array Index error");
        } catch (ArrayStoreException e) {
            System.out.println("Wrong Data Type");
        } finally { // 始终执行
            System.out.println("Always Execute");
            int y = a[1]/a[0];
            System.out.println("y = "+y);
        }
    }
}
```

**输出：**

`Array Index error`

`Always Execute`

`y =2`

到目前为止，我们只捕获由运行时系统抛出的异常。然而，我们的程序也可以使用 `throw` 语句显式地抛出异常，`throw` 的通用形式所示：

`throw instance;`

这里，`instance` 必须是 `Throwable` 类型的对象或其子类。简单类型如 `int` 或 `char`，以及非 `Throwable` 类（如 `String` 和 `Object`）不能作为异常。我们有两种方法可以获取 `Throwable` 对象：使用 `catch` 子句中的参数，或者使用 `new` 操作符创建一个。

执行流在 `throw` 语句后立即停止；任何后续语句都不会执行。程序将检查最近的嵌套 `try` 块，查看是否有匹配异常类型的 `catch` 语句。如果找到匹配，控制权将转移到该语句。如果没有，则检查下一个嵌套的 `try` 语句，以此类推。如果没有找到匹配的 `catch`，则默认异常处理器将停止程序并打印堆栈跟踪。在这里我们取创建一个并抛出异常的程序。捕获异常的处理器将其重新抛出给外层处理器。

### 示例 1.10

```java
class ErrorTest10 {
    int age;
    void setAge(int a) {
        if (a > 0)
            age = a;
        else
            throw new NullPointerException("Invalid");
    }
    public static void main(String args[]) {
        ErrorTest10 a1 = new Error10();
        try {
            a1.setAge(20);
            a1.setAge(-10);
        } catch (NullPointerException e) {
            System.out.println(e.getMessage());
        }
    }
}
```

## throws

如果一个方法可能会导致它未处理的异常，则它必须指定这种行为，以便该方法的调用者能够针对该异常进行防护。我们通过在方法的声明中包含 `throws` 子句来实现这一点。`throws` 子句列出了方法可能抛出的异常类型。

这对于所有检查异常（checked exceptions）都是必须的。方法可以抛出的所有异常必须在 `throws` 子句中声明。否则，会导致编译时错误。这是一个包含 `throws` 子句的方法声明通用形式：

### 语法

```
type method-name(parameter list)throws exception-list
{
    //方法体
}
```

在这里，`exception list` 是方法可以抛出的异常的用逗号分隔的列表。

### 示例 11.11

```java
import java.io.*;

class ErrorTest11 {
    int age;
    void setAge(int a) throws IOException {
        if(a>0)
            age = a;
        else {
            IOException e = new IOException("Invalid Age");
            throw e;
        }
    }

    public static void main(String args[]) {
        ErrorTest11 a1 = new ErrorTest11();
        try {
            a1.setAge(20);
            a1.setAge(-10);
        } catch(IOException e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**输出：**

```
Invalid Age
```

## 创建用户定义的异常/错误子类

### 自己的异常子类

这非常简单，只需定义 `Exception/Error` 类的子类即可。我们的子类并不需要实际实现任何内容。`Exception/Error` 类本身没有定义任何方法。当然，它继承了 `Throwable` 类提供的方法。

尽管 Java 的内置异常处理了大多数常见错误，但你可能想要创建自己的异常类型来处理特定于你应用程序的情况。这非常简单：只需定义 `Exception` 的子类（当然，它是 `Throwable` 的子类）即可。

你的子类并不需要实际实现任何内容——它们在类型系统中的存在就使得你能够将它们作为异常使用。

`Exception` 类本身没有定义任何方法。当然，它继承了由 `Throwable` 提供的方法。因此，所有异常（包括你创建的异常）都可以使用 `Throwable` 定义的方法。

`Exception` 定义了四个构造函数。其中两个支持链式异常（将在下一节中描述）。另外两个在此所示：

- `Exception()`

- `Exception(String msg)`

第一种形式创建一个没有描述的异常。第二种形式允许你指定异常的描述。虽然在创建异常时指定描述通常很有用，但有时重写 `toString()` 更好。原因如下：`Throwable` 定义（并 `Exception` 继承）的 `toString()` 版本显示异常名称，后面跟着一个冒号，然后是你的描述。通过重写 `toString`，你可以防止异常名称和冒号显示。这使得输出更加整洁，在某些情况下是需要的。

### 示例 1.2

```java
class AgeException extends Exception {
    AgeException(String msg) {
        super(msg);
    }
}

class ErrorTest2 {
    int age;
    void setAge(int a) throws AgeException {
        if(a>0)
            age = a;
        else {
            AgeException e = new AgeException("Invalid Age");
            throw e;
        }
    }

    public static void main(String args[]) {
        ErrorTest2 a1 = new ErrorTest2();
        try {
            a1.setAge(20);
            a1.setAge(-10);
        } catch(AgeException e) {
            System.out.println(e.getMessage());
        }
    }
}
```

**输出：**

```
Invalid Age
```

以下示例声明了一个 `Exception` 的新子类，然后使用该子类在方法中指示错误条件。它重写了 `toString()` 方法，允许显示经过精心定制的异常描述。

![sss](img/image01241.jpeg)

此示例定义了一个名为 `MyException` 的 `Exception` 子类。该子类非常简单：它只有一个构造函数以及一个重写的 `toString()` 方法，用于显示异常的值。

`ExceptionDemo` 类定义了一个名为 `compute()` 的方法，该方法抛出一个 `MyException` 对象。当 `compute()` 的整数参数大于 10 时，会抛出该异常。`main()` 方法为 `MyException` 设置了异常处理器，然后用一个合法值（小于 10）和一个不合法值调用 `compute()`，以展示代码中的两种路径。

结果如下：

```
Called compute(1)
Normal exit
Called compute(20)
Caught MyException[20]
```

### 链式异常

链式异常功能允许我们将另一个异常与异常相关联。第二个异常描述了第一个异常产生。例如，想象一种情况，方法由于尝试除以零而抛出 `ArithmeticException`。然而，问题的实际原因是发生了 I/O 错误，导致除数被设置不正确。

```java
Throwable(Throwable causeExc)
Throwable(String msg, Throwable causeExc)
```

在第一种形式中，`causeExc` 是发生的异常。第二种形式允许我们在指定原因异常的同时指定一个描述信息。这两个构造函数也被添加到了 `Error`、`Exception` 和 `RuntimeException` 类中。

添加到 `Throwable` 类中的链式异常方法是 `getCause()` 和 `initCause()`。

```java
Throwable getCause()
Throwable initCause(Throwable causeExc)
```

`getCause()` 方法返回当前异常的底层异常。如果没有底层异常，则返回 `null`。`initCause()` 方法将 `causeExc` 与调用的异常关联，并返回该异常的引用。因此，我们可以在异常创建后为其关联一个原因。然而，原因异常只能设置一次。

因此，对于每个异常对象我们只能调用一次 `initCause()`。此外，如果原因异常是通过构造函数设置的，那么我们无法再次使用 `initCause()` 方法来设置它。通常情况下，`initCause()` 用于为不支持前述两个额外构造函数的旧异常类设置原因。Java 大多数内置异常都没有定义额外的构造函数。因此，如果我们需要为这些异常添加异常链，将使用 `initCause()`。

链式异常并不是每个程序都需要的。但在了解底层原因有用的情况下，它们提供了一种优雅的解决方案。

### 示例 11.13

1. 类 `ErrorTest13`

2. ```java
class ErrorTest13 {
    int age;
    void setAge(int a) {
        if(a>0)
            age = a;
        else {
            NullPointerException e = new NullPointerException("Admission Failed");
            e.initCause(new ArithmeticException("Age is invalid"));
            throw e;
        }
    }
    public static void main(String args[]) {
        ErrorTest13 a1 = new Error13();
        try {
            a1.setAge(20);
            a1.setAge(-10);
        } catch(NullPointerException e) {
            System.out.println(e.getMessage());
            System.out.println(e.getCause());
        }
    }
}
```

**输出：**

```
Admission Failed
Age is Invalid
```

在这个示例中，顶层异常是 `NullPointerException`。在它上面添加了一个原因异常 `ArithmeticException`。当异常从 `setAge()` 抛出时，它被 `main()` 捕获。在那里，显示了顶层异常，随后是通过调用 `getCause()` 获取的底层异常。链式异常可以延伸到任何必要的深度。因此，原因异常本身也可以有自己的原因。请注意，过长的异常链可能意味着设计不当。链式异常并不是每个程序都需要的。但在了解底层原因有用的情况下，它们提供了一种优雅的解决方案。

### 三个 JDK 7 新特性（已更新）

JDK 7 为异常系统增加了三个有趣且实用的特性。第一个是自动化了释放资源（如文件）不再需要时的过程。它基于 `try` 语句的扩展形式，称为 `try-with-resources`，将在后续章节中描述。

第二个新特性称为 `multi-catch`（多异常捕获），第三个有时被称为 `final rethrow`（最终重抛）或更精确的重抛。这里描述了后两个特性。

`multi-catch` 特性允许两个或多个异常被同一个 `catch` 句捕获。两个或多个异常处理程序使用相同的代码序列并不罕见，尽管它们响应的是不同的异常。与其逐个捕获每种异常类型，现在可以使用单个 `catch` 子句处理所有异常，而避免代码重复。

要使用 `multi-catch`，在 `catch` 子句中使用或运算符（`|`）分隔每个异常类型。每个 `multi-catch` 参数隐式地为 `final`（如果需要，你可以显式指定 `final`，但没有必要）。因为每个 `multi-catch` 参数隐式为 `final`，所以它们不能被赋予新值。

这是一个使用 `multi-catch` 特性同时捕获 `ArithmeticException` 和 `ArrayIndexOutOfBoundsException` 的 `catch` 语句：

```java
catch(ArithmeticException | ArrayIndexOutOfBoundsException e) {
```

下面的程序展示了 `multi-catch` 特性的用法：

```java
// 展示 JDK 7 的 multi-catch 特性。
class MultiCatch {
    public static void main(String args[]) {
        int a=10, b=0;
        int vals[] = { 1, 2, 3 };
        try {
            int result = a / b; // 生成一个 ArithmeticException
            // vals[10] = 19; // 生成一个 ArrayIndexOutOfBoundsException
            // 这个 catch 子句捕获了这两个异常。
        } catch(ArithmeticException | ArrayIndexOutOfBoundsException e) {
            System.out.println("Exception caught: " + e);
        }
        System.out.println("After multi-catch.");
    }
}
```

当尝试除以零时，程序将生成一个 `ArithmeticException`。如果你注释掉除法语句并移除下一行的注释符号，就会生成 `ArrayIndexOutOfBoundsException`。这两个异常都会被同一个 `catch` 语句捕获。

更精确的重抛特性限制了可以重抛的异常类型，仅限于关联 `try` 块抛出的受检异常（checked exceptions）、未被之前的 `catch` 子句处理且是参数子类或超类的异常。虽然这种能力并不经常需要，但现在已经可以使用。为了使更精确的重抛特性生效，`catch` 参数必须是有效 final（即在 catch 块内部没有被赋值新值）或显式声明为 `final`。

## 使用异常

异常处理为具有许多动态特征复杂程序提供了一种强大的机制。将 `try`、`throw` 和 `catch` 视为处理程序逻辑中错误和异常边界条件的整洁方式。与其他某些使用错误返回码来指示失败的语言不同，Java 使用异常。因此，当方法可能失败时，让它抛出异常。

这是处理失败模式的一种更高的方法。最后一点：Java 的异常处理语句不应被视为非局部跳转的通用机制。如果你这样做，只会让代码变得混乱且难以维护。

## 理论题

1. 什么是异常？

2. 我们如何定义 `try` 块？

3. 我们如何定义 `catch` 块？



## 4. 列举 Java 中可能发生的一些常见异常类型。给出示例。

## 5. 捕获所有类型的异常是必要的吗？

## 6. 一个 `try` 块可以使用多少个 `catch` 块。

## 7. 创建一个可能产生三种异常的 `try` 块，并包含必要的 `catch` 块来捕获并适当地处理这些异常。

## 8. 什么是 `finally` 块？什么时候以及如何使用？给出一个合适的示例。

## 9. 解释异常处理机制如何用于程序调试。

![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg)

![STAR-LOGO-2013](img/image01213.jpeg)

# 章节：∞ 12 ∞

(多线程编程)

### 引言

线程是程序中的单一控制流。线程与进程非常相似。事实上，线程也被称为轻量级进程。

### 线程对比进程

通常情况下，不同的进程占用不同的内存空间。当 CPU 从一个进程切换到另一个进程时，当前运行进程的状态会被保存，另一个进程的状态会被恢复。在状态切换期间没有进行任何有用工作。状态切换时间应该尽可能短，以最大化 CPU 的利用率。

线程也像独立的进程，但它们共享相同的内存和状态。各个线程也有独立的状态，但与进程状态相比，该状态非常小。状态可能只包含程序计数器和栈指针。因此，从一个线程切换到另一个线程所需的时间非常短。因此与进程相比，线程的上下文切换时间非常小。因此在多线程情况下，CPU 的利用率高于多进程情况下的利用率。

### 多线程程序

多线程程序包含两个或多个可以并发运行的部分。此类程序的每个部分被称为线程，每个线程都定义了一条独立的执行路径。因此，多线程是多任务处理的一种特殊形式。

例如，一个程序可能有三个线程：

* 一个负责打印。
* 一个负责编辑。
* 一个负责从互联网下载文件。

所有这些线程可能都在并发运行，从而最大化 CPU 的利用率。

### 基于进程的多任务处理

大多数操作系统允许我们同时运行两个或多个程序。这被称为基于进程的多任务处理。例如，我们可以运行一个 Java 程序并同时编辑一个 Word 文档。基于进程的多任务处理确保了大部分时间会有程序在执行，从而增加了 CPU 的利用率。

在基于进程的多任务处理中，程序是调度程序可以分派的最小代码单元。

### 基于线程的多任务处理

线程是基于线程的多任务环境中执行的最小单元。一个进程可以被分成若干个并发执行的线程。这允许我们在单个程序中并发处理多个任务。

例如，我们可以在编辑 Word 文档的同时打印另一个文档。基于线程的多任务处理像基于进程的多任务处理一样提高了 CPU 的利用率。但同时，它通过在单独线程中并发执行程序的不同部分，有效地加快了单个程序的执行速度。

因此，基于进程的多任务处理处理“大局”，而基于线程的多任务处理处理“细节”。

### Java 线程模型

Java 运行时系统许多方面依赖线程，所有的类库在设计时都考虑了多线程。事实上，Java 使用线程来使整个环境成为异步。这有助于通过防止 CPU 周期的浪费来降低效率。

单线程系统使用一种称为“事件循环加轮询”的方法。在这种模型中，单一控制线程在无限循环中运行，轮询单个事件队列以决定下一步做什么。在单线程环境中，当线程因为等待某些资源而阻塞（即挂起执行）时，整个程序都会停止运行。

Java 多线程的优势在于消除了主循环/轮询机制。当 Java 程序中的线程被阻塞时，只有被阻塞的那个线程会暂停，所有其他线程继续运行。

### 线程生命周期（线程状态）

线程存在多种状态。线程可以处于运行状态。它一旦获得 CPU 时间就可以进入就绪运行状态。运行中的线程可以被挂起，暂时停止其活动。被挂起的线程随后可以恢复，允许它从中断的地方继续。线程在等待资源时可能会被阻塞。在任何时候，线程都可以被终止，立即停止其执行。线程一旦终止，就无法恢复。

#### 1. 新生状态 (Newborn State)

当我们创建一个线程时，线程就出生了，被称为新生状态。该线程尚未被调度运行。在此时状态下，我们只能对其执行以下操作之一：

1. 使用 `start()` 调度其运行。
2. 使用 `stop()` 将其杀死。

如果被调度，它将进入可运行状态。如果我们在此状态下尝试使用任何其他方法，将抛出异常。

#### 2. 可运行状态 (Runnable State)

可运行状态意味着线程已准备好执行，并正在等待处理器的可用。也就是说，线程已加入等待执行的线程队列。如果所有线程的优先级相同，则它们被轮流分配执行时间片。

放弃控制权的线程会重新加入队列的末尾并再次等待运行。然而，如果我们想让线程在轮到它之前向其他线程放弃控制权，可以通过调用 `yield()` 实现。

#### 3. 运行状态 (Running State)

运行状态意味着处理器已将时间分配给线程进行执行。运行中的线程在以下情况下可能会放弃控制权：

* 其时间片结束。
* 被高优先级线程抢占。
* 它让出（即主动放弃控制权）。
* 它完成了执行。
* 被其他线程停止。
* 被 `suspend()` 挂起。被挂起的线程可以通过 `resume()` 恢复。这种方法在我们想要由于某些原因暂停线程一段时间但不想杀死它时非常有用。
* 它被要求等待某些事件发生。这通过 `wait()` 实现。线程可以通过 `notify()` 调度再次运行。
* 它正在执行某些 I/O 操作。

#### 4. 阻塞状态 (Blocked State)

当线程被阻止进入可运行状态随后进入运行状态时，被称为阻塞。这发生在线程挂起、睡眠或等待以满足某些需求时。阻塞线程被认为“不可运行”但未死亡，因此完全能够再次运行。

#### 5. 死亡状态 (Dead State)

每个线程都有生命周期。运行的线程在执行完 `run()` 方法后结束生命。它有自然死亡。然而，我们可以在任何状态向它发送停止消息来杀死它，从而导致过早死亡。线程在刚出生时、运行期间甚至在处于“不可运行”（阻塞状态）时都可以被杀死。

### 线程优先级 (Thread Priorities)

Java 为每个线程分配一个优先级，该优先级决定了如何对待该线程。线程优先级是整数，指定了一个线程相对于另一个线程的相对优先级。

作为一个绝对值，优先级是毫无意义的；如果一个线程是唯一运行的线程，那么高优先级线程的运行速度不会比低优先级线程快。相反，线程的优先级用于决定何时从一个正在运行的线程切换到下一个。这被称为上下文切换（context switch）。决定上下文切换何时发生的规则非常简单：

* 线程可以自愿地（自己）放弃控制权。这是通过显式地让出（yielding）、睡眠（sleeping）、阻塞（blocking）或等待 I/O 来。在这种情况下，系统会检查所有其他线程，通常会将 CPU 赋予就绪运行的最高优先级线程。
* 线程可以被高优先级线程抢占（pre-empted）。在这种情况下，一个不释放处理器的低优先级线程无论正在做什么，都会会被高优先级线程直接抢占。基本上，只要有高优先级线程想要运行，它就会运行。这被称为抢占式多任务处理（preemptive multitasking）。
* 某些操作系统支持非抢占式优先级调度。在这种情况下，高优先级线程只有在低优先级线程完成后才能获得机会。
* 当两个优先级相同的线程竞争 CPU 周期时，情况会变得稍微复杂一些。对于像 windows98 这样的操作系统，等优先级的线程必须自愿地（自己）向同级线程让出（放弃）控制权。如果它们这样做，其他线程将不会运行。

> **注意**：操作系统处理等优先级线程上下文切换的方式可能会产生问题。

### 同步 (Synchronization)

由于多线程为我们的程序引入了异步行为，我们必须有某种方法在需要时强制同步。例如，如果我们想让两个线程进行通信并共享一个复杂的数据结构（如链表），我们需要某种方式来确保它们不会发生冲突。

也就是说，我们必须防止一个线程在另一个线程正在读取数据时写入数据。Java 使用监视器（monitor）进行线程间同步。我们可以将监视器想象成只能容纳一个线程的小盒子。一旦线程进入监视器，监视器就可以用来保护共享资源不被多个线程同时操作。

大多数多线程系统将同步暴露为对象，我们的程序必须显式地获取并锁定。Java 提供了一个更简洁的解决方案。

这里没有 `monitor` 类，相反，每个对象都有自己的隐式监视器，当调用该对象的 `synchronized` 方法时，该监视器会自动进入。一旦线程进入 `synchronized` 方法，其他线程就无法调用该对象上的任何其他 `synchronized` 方法。这使我们能够编写非常清晰且简洁的多线程代码，因为同步支持内置在语言中。

### 消息传递 (Messaging)

使用大多数其他语言编程时，我们必须依赖操作系统来建立线程之间的通信。

这无疑增加了开销。相比之下，Java 提供了一种简洁、低成本的方法让两个或多个线程通过调用所有对象都拥有的定义方法进行通信。Java 的消息传递系统允许线程进入对象的 `synchronized` 方法，然后在那里等待，直到其他某个线程显式通知退出。

### `Thread` 类和 `Runnable` 接口

Java 的多线程系统构建在 `Thread` 类、其方法及其伴侣接口 `Runnable` 之上。该类属于 `java.lang` 包，因此不需要显式导入。

`Thread` 封装了一个执行线程，由于我们无法直接引用运行线程的内部状态，我们将通过它的代理（即产生它的 `Thread` 实例）来处理处理它。要创建一个新线程，我们的程序要么扩展 `Thread` 类，要么实现 `Runnable` 接口。`Thread` 类定义了几个有助于管理线程的方法：

| 方法 | 描述 |
| :--- | :--- |
| `String getName()` | 返回此线程的名字 |
| `int getPriority()` | 返回此线程的优先级 |
| `boolean isAlive()` | 测试此线程是否仍在运行 |
| `void join()` | 等待此线程死亡（终止） |
| `void run()` | 如果此线程在使用单独 `Runnable` 对象构造的，则调用该 `Runnable` 对象的 `run` 方法；否则，此方法什么都不做并返回；如果扩展了线程类并在子类中重写了 `run()` 方法，则调用被重写的 `run()` 方法。 |
| `void setName(String name)` | 将此线程的名字更改为参数 name |
| `static void sleep(long millis) throws InterruptedException` | 使当前执行的线程睡眠指定的毫秒数（临时停止执行）。(1 sec = 1000ms) |
| `static void sleep(long millis, int nanos) throws InterruptedException` | 使当前执行的线程睡眠指定的毫秒数加上指定的纳秒数（停止执行）。 |
| `void start()` | 导致此线程开始执行，Java 虚拟机调用此线程的 `run` 方法。 |
| `static void yield()` | 使当前执行的线程对象临时暂停并允许其他线程执行。 |
| `static Thread currentThread()` | 返回当前执行的线程对象的引用。 |

### 主线程 (main thread)

当 Java 程序启动时，一个线程会立即开始。这通常被称为我们程序的主线程（main thread），因为它是程序开始时执行的线程。主线程是创建“子”线程的线程。虽然主线程是在程序启动时创建的，但可以通过 `Thread` 对象对其控制。要实现这一点，我们必须通过调用 `currentThread()` 获取引用，它是 `Thread` 类的 `public static` 成员。该方法返回调用它的方法的线程的引用。一旦我们有了主线程的引用，就可以像控制其他线程一样控制它。

示例 2：下面的示例演示了如何使用 `Thread` 类的方法获取主线程引用并访问其属性。

```java
class CurrentTest {
    public static void main (String args[]) {
        Thread t = Thread.currentThread();
        System.out.println("Current thread:" + t);
        System.out.println("Name:"+ t.getName());
        System.out.println("Priority:"+ t.getPriority());
        t.setName("MyThread");
        t.setPriority(Thread.MAX_PRIORITY);
        System.out.println("After name and priority change :" + t);
        System.out.println("Name:" + t.getName());
        System.out.println("Priority:" + t.getPriority());
        for (int n=1; n<=5; n++) {
            System.out.println(n);
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                System.out.println("Main thread interrupted");
            }
        }
    }
}
```

> **注意 1**：`Thread` 类中的 `sleep()` 方法可能会抛出 `InterruptedException`，这是一个检查异常。当其他线程想要中断这个正在睡眠的线程时，就会发生这种情况。
>
> **注意 2**：注意当 `t`（线程引用）作为 `println()` 的参数时产生的输出。它将按顺序显示：线程名称、其优先级以及其线程组名称。它的优先级为 5，这是默认值，`main` 也是该线程所属线程组的名称。线程组（thread group）是一个用于控制一组线程状态的数据结构。

### 创建线程

从广义上说，我们通过实例化 `Thread` 类型的对象来创建一个线程。Java 识别了两种实现这一目标的方法：

1. 我们可以实现 `Runnable` 接口。
2. 我们可以扩展 `Thread` 类本身。

### 实现 Runnable

创建线程最简单的方法是创建一个实现了 `Runnable` 接口的类。要实现 `Runnable`，类只需要实现一个名为 `run()` 的方法。

```java
public void run()
```

在 `run()` 方法内部，我们将定义构成新线程的代码。`run()` 可以调用其他方法、使用其他类并声明变量，就像主线程一样。

唯一的区别是，`run()` 为我们程序中的另一个并发执行线程建立了入口点。该线程将在 `run()` 返回时结束。

在我们创建一个实现了 `Runnable` 的类后，我们将在该类内部使用以下构造函数之一实例化 `Thread` 类型的对象：

```java
Thread(Runnable threadObj)
Thread(Runnable threadObj, String threadName)
```

在这里，`threadObj` 是被调用的 `run` 方法的对象，`threadName` 是新线程的名称。在新线程创建后，在我们调用 `start()` 方法之前，它不会开始运行。

`start()` 方法将线程放入就绪队列（可运行状态）。每当线程被调度时，它的执行将从 `run()` 方法开始。

### 示例 12.2

```java
class A implements Runnable {
    public void run() {
        for(int i=1;i<=5;i++) {
            System.out.println("Child Thread:" + i);
        }
        System.out.println("Exiting child thread");
    }
}

class RunnableTest {
    public static void main(String args[]) {
        A a1=new A();
        Thread t1 = new Thread(a1,"Demo Thread");
        t1.start();
        System.out.println("Main thread exiting");
    }
}
```

**输出：**

```
Main thread exiting
Child Thread:1
Child Thread:2
Child Thread:3
Child Thread:4
Child Thread:5
Exiting child thread
```

### 示例 12.3



```java
class A implements Runnable {
    Thread t;
    A() {
        t = new Thread(this, "Demo Thread");
        System.out.println("Child thread: " + t);
        t.start();
    }
    public void run() {
        for (int i = 1; i <= 5; i++) {
            System.out.println("Child Thread: " + i);
            try {
                Thread.sleep(500);
            } catch (InterruptedException e) {
                System.out.println(e);
            }
        }
        System.out.println("Exiting thread");
    }
}

class RunnableTest2 {
    public static void main(String args[]) {
        A a1 = new A();
        for (int i = 1; i <= 5; i++) {
            System.out.println("Main Thread: " + i);
            try {
                Thread.sleep(100);
            } catch (InterruptedException e) {
                System.out.println("main thread interrupted");
            }
        }
        System.out.println("End of Main thread");
    }
}
```

**输出：**

```
Child thread: Thread[Demo Thread,5,main]
Main Thread:1
Child Thread: 1
Child Thread: 2
Main Thread:2
Child Thread: 3
Child Thread: 4
Main Thread:3
Child Thread: 5
Exiting Child thread
Main Thread:4
Main Thread:5
End of Main thread
```

## 扩展 Thread 类

创建线程的另一种方法是创建一个扩展 `Thread` 的新类，然后创建该类的实例。扩展类必须重写 `run()` 方法，该方法是新线程的入口点。它还必须调用 `start()` 来开始新线程的执行。

### 示例 12.4

```java
class A extends Thread {
    A() {
        super("Test");
        System.out.println("Child thread:" + this);
        start();
    }
    public void run() {
        for (int i = 1; i <= 5; i++) {
            System.out.println("Child Thread:" + i);
            try {
                Thread.sleep(500);
            } catch (InterruptedException e) {
                System.out.println(e);
            }
        }
        System.out.println("Exiting Child thread");
    }
}

class ThreadTest {
    public static void main(String args[]) {
        new A();
        for (int i = 1; i <= 5; i++) {
            System.out.println("Main Thread: " + i);
            try {
                Thread.sleep(100);
            } catch (InterruptedException e) {
                System.out.println("Main interrupted");
            }
        }
        System.out.println("Main thread exiting");
    }
}
```

输出:

```
Child thread:Thread[Testing Thread,5,main]
Main Thread: 1
Child Thread:1
Child Thread:2
Main Thread: 2
Child Thread:3
Child Thread:4
Main Thread: 3
Child Thread:5
Exiting Child thread
Main Thread: 4
Main Thread: 5
Main thread exiting
```

**注**：如果 `Thread` 没有分配任何名称，它将类似于：`Thread-1`、`Thread-2`、`Thread-3` 等。

### 选择一种方法

`Thread` 类定义了几个可以被派生类重写的方法。在这些方法中，唯一必须重写的是 `run()`。当然，这与我们实现 `Runnable` 接口时要求的方法是相同的。

许多 Java 程序员认为，只有当类在某种程度上被增强或修改时，才应该被扩展。因此，如果我们不重写 `Thread` 的其他任何方法，最好的办法可能是简单实现 `Runnable` 接口。

### 创建多个线程

示例 12.5

```java
class A implements Runnable {
    String name;
    Thread t;
    A(String threadName) {
        name = threadName;
        t = new Thread(this, name);
        System.out.println("Child thread:" + t);
        t.start();
    }
    public void run() {
        for (int i = 1; i <= 5; i++) {
            System.out.println(name + ":" + i);
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                System.out.println(e);
            }
        }
        System.out.println(name + "Exiting");
    }
}

class MultiThreadTest {
    public static void main(String args[]) {
        A a1 = new A("One");
        A a2 = new A("Two");
        A a3 = new A("Three");
        try {
            Thread.sleep(10000);
        } catch (InterruptedException e) {
            System.out.println("main thread interrupted");
        }
        System.out.println("Main thread exiting");
    }
}
```

输出:

```
Child thread:Thread[One,5,main]
Child thread:Thread[Two,5,main]
Child thread:Thread[Three,5,main]
One:1
Two:1
Three:1
One:2
Two:2
Three:2
One:3
Two:3
Three:3
One:4
Two:4
Three:4
One:5
Two:5
Three:5
OneExiting
TwoExiting
ThreeExiting
Main thread exiting
```

### 使用 isAlive() 和 join() 强制排序

我们通常希望主线程最后结束。实现此点的一种方法是在 main 中调用 `sleep()`。这相当粗糙。有两种方法可以判断一个线程是否已完成。首先，我们可以对线程调用 `isAlive()`。该方法由 `Thread` 定义，其通用形式为：`boolean isAlive()`。如果调用该方法的线程仍在运行，则它返回 true；否则返回 false。虽然 `isAlive()` 有时很有用，但我们通常用于等待线程完成的方法是 `join()`，如下所示：`void join() throws InterruptedException`。该方法会等待直到调用它的线程终止为止。`join()` 的其他形式允许我们指定等待特定线程终止的最长时间。接下来的示例使用了 `join()` 来确保主线程是最后一个执行的。它还演示了 `isAlive()` 方法。

示例 12.6

```java
class A implements Runnable {
    String name;
    Thread t;
    A(String threadName) {
        name = threadName;
        t = new Thread(this, name);
        System.out.println("Child thread:" + t);
        t.start();
    }
    public void run() {
        for (int i = 1; i <= 5; i++) {
            System.out.println(name + ":" + i);
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                System.out.println(e);
            }
        }
        System.out.println(name + "Exiting");
    }
}

class DemoJoin {
    public static void main(String args[]) {
        A ob1 = new A("One");
        A ob2 = new A("Two");
        A ob3 = new A("Three");
        System.out.println("Thread One is alive?:" + ob1.t.isAlive());
        System.out.println("Thread Two is alive?:" + ob2.t.isAlive());
        System.out.println("Thread Three is alive?:" + ob3.t.isAlive());
        try {
            ob3.t.join();
            ob2.t.join();
            ob1.t.join();
        } catch (InterruptedException e) {
            System.out.println("main thread interrupted");
        }
        System.out.println("Thread One is alive?:" + ob1.t.isAlive());
        System.out.println("Thread Two is alive?:" + ob2.t.isAlive());
        System.out.println("Thread Three is alive?:" + ob3.t.isAlive());
        System.out.println("Main thread exiting");
    }
}
```

输出：

```
Child thread:Thread[One,5,main]
Child thread:Thread[Two,5,main]
Child thread:Thread[Three,5,main]
Thread One is alive?:true
Thread Two is alive?:true
Thread Three is alive?:true
One:1
Two:1
Three:1
One:2
Two:2
Three:2
One:3
Two:3
Three:3
One:4
Two:4
Three:4
One:5
Two:5
Three:5
OneExiting
TwoExiting
ThreeExiting
Thread One is alive?:false
Thread Two is alive?:false
Thread Three is alive?:false
Main thread exiting
```

### 示例 12.7

```java
class Clicker implements Runnable {
    long click = 0;
    Thread t;
    volatile boolean running = true;

    Clicker(int p) {
        t = new Thread(this);
        t.setPriority(p);
    }

    public void run() {
        while (running) {
            click++;
        }
    }

    void stop() {
        running = false;
    }

    void start() {
        t.start();
    }
}

class HiLoPri {
    public static void main(String args[]) {
        Thread.currentThread().setPriority(Thread.MAX_PRIORITY);
        Clicker hi = new Clicker(Thread.NORM_PRIORITY + 1);
        Clicker lo = new Clicker(Thread.NORM_PRIORITY - 1);
        lo.start();
        hi.start();
        try {
            Thread.sleep(10000);
        } catch (InterruptedException e) {
            System.out.println(e);
        }
        lo.stop();
        hi.stop();
        try {
            lo.join();
            hi.join();
        } catch (InterruptedException e) {
            System.out.println(e);
        }
        System.out.println("Low : " + lo.click);
        System.out.println("High : " + hi.click);
    }
}
```

高优先级线程获得了超过 98% 的 CPU 时间。但尽管线程既没有主动释放 CPU，也没有因为 I/O 而阻塞，它们仍然发生了上下文切换。当此相同的程序在非抢占式系统下运行时，将获得不同的结果。

**注意**：变量 `running` 前面带有关键字 `volatile`，以确保在每次迭代以下循环时，都会检查 `running` 的值。

```java
while (running) {
    click++;
}
```

如果不使用 `volatile`，Java 可以自由地对循环进行优化，创建一个 `running` 的局部副本。使用 `volatile` 可以防止这种优化，告诉 Java `running` 可能会以当前代码中无法直接看出的方式发生变化。

## 同步

当两个或多个线程需要访问共享资源时，它们需要某种方式来确保资源一次只有一个线程使用。实现这一目标的过程被称为同步。

同步的关键是监视器（monitor）的概念（也称为信号量 semaphore）。监视器是一个被用作互斥锁的对象。在任何时刻，只有一个线程可以拥有监视器。

当线程获取锁时，可以说它进入了监视器。所有其他尝试进入被锁监视器的线程都将被挂起，直到第一个线程退出监视器。这些其他线程被称为等待监视器。拥有监视器的线程如果需要，可以重新进入同一个监视器。我们可以通过两种方式同步我们的代码：

(i) 使用 `synchronized` 方法

(ii) 使用 `synchronized` 语句

## 使用 synchronized 方法

在 Java 中同步是非常简单的，因为所有对象都关联有自己的隐式监视器。要进入对象的监视器，只需调用用 `synchronized` 关键字修饰的方法。当线程在同步方法内部时，所有其他尝试调用该方法（或同一实例上的任何其他同步方法）的线程都必须 `wait()`。要退出监视器并将对象的控制权交给下一个等待线程，监视器的所有者只需从同步方法返回即可。

### 示例 12.8

以下程序说明了三个线程在并发运行时，它们生成的输出会发生混合。



```java
class A {
    void display(String msg) {
        System.out.print("[" + msg);
        try {
            Thread.sleep(1000);
        } catch (InterruptedException e) {
            System.out.println(e);
        }
        System.out.println("]");
    }
}

class B implements Runnable {
    A obj;
    String msg;
    Thread t;
    B(A obj1, String m) {
        msg = m;
        obj = obj1;
        t = new Thread(this);
        t.start();
    }
    public void run() {
        obj.display(msg);
    }
}

class Synch1 {
    public static void main(String args[]) {
        A a1 = new A();
        B b1 = new B(a1, "Hello");
        B b2 = new B(a1, "World");
        B b3 = new B(a1, "Matrix");
    }
}
```

**输出:**

```
[Hello[World[Matrix]
]
]
```

正如我们看到的，通过调用 `sleep()`，`display()` 方法允许执行切换到另一个线程。这导致了三个消息字符串的输出混合。在这个程序中，没有任何机制可以阻止所有三个线程同时在同一个对象上调用同一个方法。

这被称为竞态条件（race condition），因为这三个线程正在相互竞争以完成该方法。这个示例使用 `sleep()` 来使效果变得重复且显而易见。在大多数情况下，竞态条件更加微妙且难以预测，因为我们无法确定上下文切换何时发生。这可能导致程序在一次运行时是正确的，而在下一次运行时错误的。

要做到这一点，我们只需要在方法 `display()` 的定义之前加上 `synchronized` 关键字。这可以防止一个线程在另一个线程使用 `display()` 时进入该方法。

### 示例 12.9

混合问题通过将 `display()` 方法声明为同步方法就简单解决了。

```java
class A {
    synchronized void display(String msg) {
        System.out.print("[" + msg);
        try {
            Thread.sleep(100);
        } catch (InterruptedException e) {
            System.out.println(e);
        }
        System.out.println("]");
    }
}

class B implements Runnable {
    A obj;
    String msg;
    Thread t;
    B(A obj1, String m) {
        msg = m;
        obj = obj1;
        t = new Thread(this);
        t.start();
    }
    public void run() {
        obj.display(msg);
    }
}

class Synch2 {
    public static void main(String args[]) {
        A a1 = new A();
        B b1 = new B(a1, "Hello");
        B b2 = new B(a1, "World");
        B b3 = new B(a1, "Matrix");
    }
}
```

虽然在我们创建的类中创建同步方法是实现同步的一种简单且有效的方法，但在所有情况下它并不起作用。为了理解其原因，请考虑以下情况：假设我们想要对一个并非为多线程访问设计的类对象进行同步访问。也就是说，该类没有使用 `synchronized` 方法。此外，该类不是由我们创建，而是由第三方创建的；我们无法访问源代码。因此，我们无法在类内部适当的方法上添加 `synchronized` 修饰符。那么如何通过 `synchronized` 对该类的对象进行访问呢？

解决方案是将对该类定义的方法调用放在 `synchronized` 块内部。`synchronized`语句的一般形式如下：

```java
synchronized(object)
{
    //需要同步的语句
}
```

在这里，`object` 是被同步对象的引用。`synchronized` 块确保了对 `object` 成员方法的调用只有在当前线程成功进入 `object` 监视器后才会发生。

### 示例 12.10

前一个示例的变体版本，在 `run()` 中使用 `synchronized` 块。

```java
class A
{
    void display(String msg) {
        System.out.print("[" + msg);
        try {
            Thread.sleep(1000);
        } catch(InterruptedException e) {
            System.out.println(e);
        }
        System.out.println("]");
    }
}

class B implements Runnable
{
    A obj;
    String msg;
    Thread t;
    B(A obj1, String m) {
        msg = m;
        obj = obj1;
        t = new Thread(this);
        t.start();
    }
    public void run() {
        synchronized(obj) {
            obj.display(msg);
        }
    }
}

class Synch3
{
    public static void main(String args[]) {
        A a1 = new A();
        B b1 = new B(a1,"Hello");
        B b2 = new B(a1,"World");
        B b3 = new B(a1,"Matrix");
    }
}
```

输出:

```
[Hello]
[World]
[Matrix]
```

### 多线程在不同对象上调用同一方法

#### 示例 12.11

线程可以并发地在同类的不同对象上调用同一个同步实例方法，因为每个对象都有不同的锁。这再次导致输出混杂。

```java
class A
{
    synchronized void display(String msg) {
        System.out.print("[" + msg);
        try {
            Thread.sleep(100);
        } catch(InterruptedException e) {
            System.out.println(e);
        }
        System.out.println("]");
    }
}

class B implements Runnable
{
    A obj;
    String msg;
    Thread t;
    B(A obj1, String m) {
        msg = m;
        obj = obj1;
        t = new Thread(this);
        t.start();
    }
    public void run() {
        obj.display(msg);
    }
}

class Synch4
{
    public static void main(String args[]) {
        A a1 = new A();
        A a2 = new A();
        A a3 = new A();
        B b1 = new B(a1,"Hello");
        B b2 = new B(a2,"World");
        B b3 = new B(a3,"Matrix");
    }
}
```

输出:

```
[Hello[World[Matrix]
```

### 静态同步方法

#### 示例 12.2

在以下示例中，尽管我们在不同的对象上调用了 `display()` 方法，但输出并没有被打乱。原因是 `display()` 是 `static` 的，因此锁是针对整个类 `A` 获取的，而不是针对单个对象。

```java
class A
{
    static synchronized void display(String msg) {
        System.out.print("[" + msg);
        try {
            Thread.sleep(1000);
        } catch(InterruptedException e) {
            System.out.println(e);
        }
        System.out.println("]");
    }
}

class B implements Runnable
{
    A obj;
    String msg;
    Thread t;
    B(A obj1, String m) {
        msg = m;
        obj = obj1;
        t = new Thread(this);
        t.start();
    }
    public void run() {
        obj.display(msg);
    }
}

class Synch5
{
    public static void main(String args[]) {
        A a1 = new A();
        A a2 = new A();
        A a3 = new A();
        B b1 = new B(a1,"Hello");
        B b2 = new B(a2,"World");
        B b3 = new B(a3,"Matrix");
    }
}
```

输出:

```
[Hello]
[World]
[Matrix]
```

## 线程间通信

如前所述，多线程通过将我们的任务划分为离散且逻辑的单元来取代事件循环编程。`Threads` 同时也证明了一个次要优点：它们消除了轮询。轮询通常通过一个循环实现，该循环用于反复检查某些条件。一旦条件为真，就会采取相应的行动。

这会浪费 CPU 周期。例如，考虑经典的队列问题，其中一个线程产生数据，另一个线程消费这些数据。为了让这个问题更具交互性，假设生产者必须等待消费者完成任务后才能生成更多数据。在轮询系统中，消费者在等待生产者生产时会浪费许多 CPU 周期。一旦生产者完成工作，它又会开始轮询，在等待消费者完成任务时浪费更多 CPU 周期，以此类推。

为了避免轮询，Java 通过 `wait()`、`notify()` 和 `notifyAll()` 方法包含了一种优雅（智能）的进程间通信机制。这些方法被实现为 `Object` 类中的 `final` 方法，因此所有类都拥有这些方法。这三个方法都只能在 `synchronized`（同步）上下文中调用。使用这些方法有特定的规则。

- `wait()` 告诉调用线程释放监视器并进入睡眠，直到另一个线程进入同一个监视器并调用 `notify()`。
- `notify()` 唤醒在同一个对象上调用过 `wait` 的线程（通常是第一个线程）。
- `notifyAll()` 唤醒所有在同一个对象上调用过 `wait()` 的线程。通常优先级最高的线程会首先运行。这些方法在 `Object` 类中声明，如下所示：

```java
final void wait() throws InterruptedException
final void notify()
final void notifyAll()
```

### 示例 12.13

以下示例程序错误地实现了一个简单的生产者/消费者问题形式。它包含四个类：`Q`，我们正尝试同步的队列；`Producer`，产生队列条目的线程对象；`Consumer`，消费队列条目的线程对象；以及 `PC`，创建实例 `Q`、`Producer` 和 `Consumer` 的微类。

```java
class Q {
    int n;
    synchronized int get() {
        System.out.println("Got:"+n);
        return n;
    }
    synchronized void put(int n) {
        this.n=n;
        System.out.println("Put:"+n);
    }
}
class Producer implements Runnable {
    Q q1;
    Producer(Q q2) {
        q1=q2;
        new Thread("Producer").start();
    }
    public void run() {
        int i=0;
        while(true) {
            q1.put(++i);
        }
    }
}
class Consumer implements Runnable {
    Q q1;
    Consumer(Q q2) {
        q1=q2;
        new Thread(this,"Consumer").start();
    }
    public void run() {
        while (true) {
            q1.get();
        }
    }
}
class PC {
    public static void main(String args[]) {
        Q q1=new Q();
        new Producer(q1);
        new Consumer(q1);
        System.out.println("Press Control-C to stop");
    }
}
```

尽管 `Q` 类上的 `put()` 和 `get()` 方法同步，但没有什么能阻止生产者超过消费者，也没有什么能阻止消费者两次消费同一个队列值。因此，我们可能会得到所示的错误输出：

```
Output: Press Control-C to stop
Put :1
Put :2
Put:3
Put:4
Put:5
Put:6
Put:7
Got:7
Got:7
Got:7
Got:7
Got:7
Got:7
Got:7
Got:7
Put:8
Put:9
Put:10
Put:11
Put:12
Put:13
Put:14
Put:15
Got:15
Got:15
Got:15
Got:5
Got:5
Got:5
```

在 Java 中编写此程序的正确方法是使用 `wait()` 和 `notify()` 在两个方向上信号，如下所示：

```java
class Q {
    int n;
    boolean valueSet=false;
    synchronized int get () {
        if(!valueSet) {
            try {
                wait();
            } catch (InterruptedException e) {
                System.out.println(e);
            }
        }
        System.out.println("Got :" + n);
        valueSet = false;
        notify();
        return n;
    }
    synchronized void put (int n) {
        if(valueSet) {
            try {
                wait();
            } catch (InterruptedException e) {
                System.out.println(e);
            }
        }
        this.n = n;
        valueSet = true;
        System.out.println("Put :" + n);
        notify();
    }
}
```



```java
        }

        this.n = n;

        valueSet = true;
        System.out.println("Put :" + n);
        notify();
    }
}

class Producer implements Runnable {

    Q q1;

    Producer(Q q2) {
        q1 = q2;
        new Thread(this, "Producer").start();
    }

    public void run() {
        int i = 0;
        while (true) {
            q1.put(++i);
        }
    }
}

class Consumer implements Runnable {
    Q q1;

    Consumer(Q q2) {
        q1 = q2;
        new Thread(this, "consumer").start();
    }

    public void run() {
        while (true) {
            q1.get();
        }
    }
}

class PC2 {
    public static void main(String args[]) {
        System.out.println("Press Control-C to stop");
        Q q1 = new Q();
        new Producer(q1);
        new Consumer(q1);
    }
}
```

**输出:**

```
Press Control-C to stop
Put:1
Got:1
Put:2
Got:2
Put:3
Got:3
Put:4
Got:4
Put:5
Got:5
```

## 死锁

在多任务处理中，我们需要避免的一种特殊类型错误是死锁。当两个线程对一对同步对象产生循环依赖时，就会发生死锁。例如，假设一个线程进入对象 `X` 的监控器，而另一个线程进入对象 `Y` 的监控器。如果 `X` 中的线程尝试调用 `Y` 上的任何同步方法，它将如预期般被阻塞。然而，如果 `Y` 中的线程反过来尝试调用 `X` 上的任何同步方法，线程将永远等待，因为为了访问 `X`，它必须释放对 `Y` 的锁，以便第一个线程能够完成。死锁是一种很难调试的错误，因为：

(i) 通常情况下，当两个线程的切片方式正确时，这种情况很少发生。

(ii) 它可能涉及两个以上的线程和对象。

### 示例 1

```java
class A {
    synchronized void foo(B b1) {
        System.out.println("Method called then blocked");
        try {
            Thread.sleep(1000);
        } catch (InterruptedException e) {
            System.out.println(e.getMessage());
        }
        System.out.println("Trying to call b1.last()");
        b1.last();
    }

    synchronized void last() {
        System.out.println("This not be printed");
    }
}

class B {
    synchronized void bar(A a1) {
        System.out.println("Method called then blocked");
        try {
            Thread.sleep(1000);
        } catch (InterruptedException e) {
            System.out.println(e.getMessage());
        }
        System.out.println("Trying to call a1.last()");
        a1.last();
    }

    synchronized void last() {
        System.out.println("This not be printed");
    }
}

class DeadLock implements Runnable {
    A a1 = new A();
    B b1 = new B();

    DeadLock() {
        Thread t = new Thread(this);
        t.start();
        a1.foo(b1);
    }

    public void run() {
        b1.bar(a1);
    }

    public static void main(String args[]) {
        new DeadLock();
    }
}
```

**输出:**

```
Method called then blocked
Method called then blocked
```

## 在 Java 中挂起、恢复和停止线程

`suspend()` 和 `resume()` 是 `Thread` 类定义的方法，用于暂停和重启线程的执行。它们的用法所示：

### 示例 2

```java
class A implements Runnable {
    String name;
    Thread t;

    A(String threadname) {
        name = threadname;
        t = new Thread(this, name);
        System.out.println("Child Thread: " + t);
        t.start();
    }

    public void run() {
        for (int i = 1; i <= 30; i++) {
            System.out.println(name + ": " + i);
            try {
                Thread.sleep(100);
            } catch (InterruptedException e) {
                System.out.println(e);
            }
        }
    }
}
```

# Java 线程挂起与恢复示例

此示例展示了如何在 Java 中通过 `suspend()` 和 `resume()` 方法控制线程的执行。

## 代码实现

```java
class A implements Runnable {
    String name;
    Thread t;
    boolean suspendFlag;

    A(String threadname) {
        name = threadname;
        t = new Thread(this, name);
        System.out.println("Child Thread: " + t);
        suspendFlag = false;
        t.start();
    }

    void myspend() {
        suspendFlag = true;
    }

    synchronized void myresume() {
        suspendFlag = false;
        notify();
    }

    public void run() {
        for (int i = 1; i <= 15; i++) {
            System.out.println(name + ": " + i);
            try {
                Thread.sleep(200);
            } catch (InterruptedException e) {
                System.out.println(e);
            }
            synchronized (this) {
                if (suspendFlag) {
                    wait();
                }
            }
        }
        System.out.println(name + "exiting");
    }
}

class SuspendResume {
    public static void main(String args[]) {
        A ob1 = new A("One");
        A ob2 = new A("Two");
        try {
            Thread.sleep(100);
            ob1.t.suspend();
            System.out.println("Suspending Thread one");
            Thread.sleep(100);
            ob1.t.resume();
            System.out.println("Resuming Thread one");
            ob2.t.suspend();
            System.out.println("Suspending Thread two");
            Thread.sleep(1000);
            ob2.t.resume();
            System.out.println("Resuming Thread two");
        } catch (InterruptedException e) {
            System.out.println(e);
        }
        try {
            System.out.println("Waiting for threads to finish");
            ob1.t.join();
            ob2.t.join();
        } catch (InterruptedException e) {
            System.out.println(e);
        }
    }
}
```

## 预期输出

```text
Child Thread: Thread[Thread-0]
Child Thread: Thread[Thread-1]
One: 1
Two: 1
One: 2
Two: 2
One: 3
Two: 3
One: 4
Two: 4
One: 5
Two: 5
One: 6
Two: 6
Suspending Thread one
One: 7
Two: 7
One: 8
Two: 8
One: 9
Two: 9
One: 10
Two: 10
Resuming Thread one
One: 11
Two: 11
Suspending Thread two
One: 12
Two: 12
One: 13
Two: 13
One: 14
Two: 14
One: 15
Two: 15
Resuming Thread two
One: exiting
Two: exiting
Waiting for threads to finish
```

## 注意事项

- `Thread` 类也定义了一个名为 `stop()` 方法来停止线程。其签名如下：`final void stop()`。

- 一旦线程被停止，无法使用 `resume()` 方法重启。

- `suspend()`、`resume()` 和 `stop()` 在 Java 中已不再推荐使用。

```java
catch (InterruptedException e) {
    System.out.println(e);
}
System.out.println("main exiting");
}
```

**输出:**

```
Child Thread: Thread[One,5,main]
Child Thread: Thread[Two,5,main]
One: 1
Two: 1
One: 2
Two: 2
One: 3
Two: 3
One: 4
Two: 4
One: 5
Two: 5
Suspending Thread one
Two: 6
Two: 7
Two: 8
Two: 9
Two: 10
Resuming Thread one
One: 6
Suspending Thread two
One: 7
One: 8
One: 9
One: 10
Resuming Thread two
Two: 11
Waiting for threads to finish
One: 11
Two: 12
One: 12
Two: 13
One: 13
Two: 14
One: 14
Two: 15
One: 15
Twoexiting
Oneexiting
main exiting
```

![STAR-LOGO-2013](img/image01213.jpeg)

# 章节：∞ 13 ∞

## 修饰符 / 可见性模式

### 引言

修饰符是 Java 关键字，用于向编译器提供有关代码、数据、类或接口性质的信息。例如，我们一直在使用可见性修饰符 `public`、`private`、`protected`、`package public` 等来指定类成员的可见性。除了可见性，我们还使用了修饰符 `static`、`final` 和 `abstract`。

为了便于理解，可以将修饰符分为：

1. 顶级访问权限修饰符。
2. 类的访问权限/可见性修饰符。
3. 接口的访问权限/可见性修饰符。
4. 顶级类的其他修饰符。
5. 顶级接口的其他修饰符。
6. 接口成员的其他修饰符。
7. 类成员的其他修饰符。

### 1. 顶级类和接口的访问权限修饰符

* `public`
* `default`（包级）访问权限

### 2. 类的成员访问权限/可见性修饰符

通过指定成员访问权限修饰符，类可以控制客户端（即其他类）可以访问的信息。这些修饰符帮助类定义契约，使用户确切知道该类提供了哪些服务。

成员的访问权限/可见性可以是以下之一：

* `public`
* `protected`
* `default`（也称为包访问权限）
* `private`

> **注意**：成员访问权限修饰符只有在类（或其某个子类）对客户端可见时才有意义。另请注意，一个成员只能指定一个访问权限修饰符。

该讨论适用于类的实例成员和静态成员。

### 3. 接口的成员访问权限/可见性修饰符

可以与接口数据成员和方法使用的唯一访问权限/可见性修饰符是 `public`。

`public` 也是接口成员的隐式访问权限/可见性修饰符，即成员始终隐式地认为是 `public`，即使我们不使用 `public` 修饰符。

### 4. 顶级类的其他修饰符

除了可见性修饰符，我们还可以在顶级类之前使用以下修饰符：

#### (a) `abstract`

可以使用 `abstract` 关键字指定类，表示它不能被实例化。包含 `abstract` 方法的类必须如此声明。

#### (b) `final`

可以使用 `final` 关键字指定类，表示它不能被扩展。

### 5. 顶级接口的其他修饰符

#### (a) `abstract`

这是除可见性修饰符外唯一可用于接口的修饰符。接口指定方法原型而不包含任何实现：它们从本质上说是隐式抽象的。

### 6. 接口成员的其他修饰符

#### 数据成员

除了可见性修饰符 `public` 外，我们还可以使用修饰符 `static` 和 `final`。虽然可以使用这些修饰符，但它是多余的，因为数据成员隐式为 `public` 和 `final`。

#### 方法

除了可见性修饰符 `public` 外，我们还可以使用 `abstract`。虽然可以使用 `abstract`，但它是多余的，因为所有方法都是隐式的 `public` 和 `abstract`。

### 7. 类成员的其他修饰符

可以通过以下关键字在声明中指定字段和/或方法的特定特性：

1. `static`
2. `final`
3. `abstract`
4. `synchronized`
5. `native`
6. `transient`
7. `volatile`

#### A. `static` 修饰符

静态成员属于它们声明的类，而不是类的任何实例的一部分。根据类中静态成员的访问权限修饰符，客户端可以通过类名或通过类的对象引用来访问这些成员。

##### 静态变量（也称为类变量）

这些变量只存在于它们定义的类中。当类加载时，如果没有指定显式的初始化表达式，静态变量将初始化为默认值。静态成员变量通常用于跟踪有关实例的全局信息。

##### 静态方法

这些也被称为类方法。类中的静态方法可以直接访问该类中的其他静态成员。它不能访问类的实例（即非静态）成员，因为静态方法没有与之关联的对象的概念。

然而，请注意，类中的静态方法始终可以使用类类型的引用来访问其成员，无论这些成员是否是静态的。典型的静态方法可能会代表整个类和/或类的对象执行某些任务。

* 它们只能调用其他静态方法。
* 它们只能访问静态数据成员。
* 它们无法以任何方式引用 `this` 或 `super`。

### 静态初始化块

一个 Java 类可以有一个或多个静态初始化块。静态初始化块的语法如下：



```java
static {
    code
}
```

静态初始化块可以被视为静态方法，它在类加载时就会被隐式/自动地调用。

静态块在以下情况下非常有用：

* 静态变量的动态初始化。
* 在类加载时执行一次性活动。例如，加载 JDBC 驱动类。
* 在 `Hashtable`、`HashMap`、`Properties` 等中加载小型数据库/配置文件。

### B. final 修饰符

`final` 修饰符可以用于：

* 局部变量
* 实例变量/数据成员
* 静态变量/数据成员
* 实例方法

### final 变量

`final` 变量通常在声明时初始化，赋值后后值不能被修改。以下是与 `final` 变量的一些重要点：

* `final` 变量是一个常量，尽管被称为变量。一旦初始化，它的值就不能改变。这适用于实例、静态和局部变量，包括声明为 `final` 的参数。
* `final` 是唯一适用于局部变量或形式参数的修饰符。
* 原始数据类型的 `final` 变量一旦初始化，其值就不能改变。
* 引用类型的 `final` 变量一旦初始化，其引用值就不能改变，但它所指代的对象的状态仍然可以改变。
* 通常情况下，`final` 变量在声明时初始化，但并非必须。这种 `final` 变量也称为空白 final 变量（blank final variable），它们必须在使用之前被初始化一次。
* `final static` 变量通常用于定义命名常量，例如 `Integer.MAX_VALUE`，它是 int 的最大值。

### 局部 final 变量

#### 示例 13.1

以下示例说明了如上所述，局部 final 变量可以留空，但在首次使用之前必须初始化。变量 `x` 是在显示器上显示其值之前才进行初始化的。

```java
class FinalTest1 // 使用空白 final
{
    public static void main(String args[])
    {
        final int x; // 声明时不必须初始化
        x = 50;
        System.out.println(x);
    }
}
```

Output: 50

#### 示例 13.2

以下代码将由于 final 变量被初始化了两次而无法编译。

```java
class FinalTest2 // 使用空白 final
{
    public static void main(String args[ ])
    {
        final int x;
        x=0;
        System.out.println(x);
        x = 60;
    }
}
```

### 实例 final 变量

实例 final 可以留空，但在获取该类对象的引用之前必须初始化。因此，如果不在声明时进行初始化，那么可以对 final 变量初始化的其他地方是：

* 构造函数
* 初始化块

#### 示例 13.3

以下程序将无法编译，因为 final 变量已经初始化了。默认初始化的概念不适用于 final 变量，因为它们在初始化后不能被修改。

```java
class FinalTest3 // 使用空白 final
{
    final int x; // final 实例变量没有初始化
}
class MyClass
{
    public static void main(String args[])
    {
        FinalTest3 f=new FinalTest3();
        System.out.println(f.x);
    }
}
```

Output: (编译时错误): x 可能未被初始化

#### 示例 13.4

以下程序也将无法编译，因为 final 在获取引用后才初始化。

```java
class FinalTest4
{
    final int x;
}
class MyClass
{
    public static void main(String args[])
    {
        FinalTest4 f=new FinalTest4();
        f.x = 10;
        System.out.println(f.x);
    }
}
```

#### 示例 13.5

以下示例说明了空白实例变量可以在构造函数中初始化。

```java
class FinalTest5
{
    final int x;
    public static void main(String args[])
    {
        FinalTest5 f=new FinalTest5();
        System.out.println(f.x);
    }
    FinalTest5()
    {
        x=10;
    }
}
```

Output: 10

#### 示例 13.6

以下程序说明了空白 final 变量可以使用动态值初始化，并可以使用 `this` 关键字引用。因此，同一类的不同对象可以有不同的 final 变量值。

```java
class FinalTest6
{
    final int x;
    FinalTest6(int x1)
    {
        x = x1;
    }
    public static void main(String args[])
    {
        FinalTest6 f1=new FinalTest6(10);
        FinalTest6 f2=new FinalTest6(20);
        System.out.println(f1.x);
        System.out.println(f2.x);
    }
}
```

Output:

10

20

初始化块可以被视为构造函数，它在对象创建时就会被隐式地/自动调用。事实上，如果一个类包含初始化块，它们将按照定义的顺序从上到下，在任何构造函数之前执行。

### 示例 13.7:

```java
class FinalTest7 {
    final int x;
    public static void main(String args[]) {
        FinalTest7 f=new FinalTest7();
        System.out.println(f.x);
    }
    {
        x=20;
    }
}
```

初始化块在以下情况下非常有用：

* 实例变量的动态初始化。
* 定义所有构造函数通用的代码。这会增加代码的可用性并减少维护工作。

### static final 变量：

`static final` 变量可以留空，但必须在类对程序可用之前完成初始化。因此，如果我们不在声明时进行初始化，那么 `static final` 变量唯一可以初始化的地方就是：

* `static` 初始化块

### 示例 13.8

以下示例说明了空白的 `static final` 变量可以在 `static` 块中初始化。

```java
class FinalTest8 {
    static final int x;
    public static void main(String args[]) {
        System.out.println(FinalTest8.x);
    }
    static {
        x=20;
    }
}
```

输出：`20`

### final 方法：

* 类中的 `final` 方法是完整的（即具有实现），并且不能在任何子类中被重写。因此，子类在更改方法行为方面受到了了限制。
* 编译器能够对 `final` 方法执行某些优化，因为可以对此类成员做出某些假设。当调用非静态方法时，运行时系统会确定对象的实际类，将方法调用绑定到该类型的正确实现上，然后调用它。
* 对于 `final` 方法，我们确定子类不能重写该方法，因此绑定像 `private` 和 `static` 方法一样，是在编译时完成的，这极地提升了性能。
* 对于 `final` 方法，编译器可以将调用替换为方法的实际体，类似于宏。这种机制被称为“内联”（inlining）。在 C++ 中，我们可以选择将函数声明为 `inline`（尽管决定由编译器做出），但在 Java 中，由编译器做决定。

### abstract 修饰符：

`abstract` 修饰符只能用于实例方法。`abstract` 方法没有实现，也就是说，为 `abstract` 方法没有定义方法体，在类定义中仅提供方法原型。它的类也必须是 `abstract`（即不完整的），并且必须显式声明为 `abstract`。`abstract` 类的子类必须提供方法的实现；否则，它们也是 `abstract` 的。

以下是与抽象方法的一些重要点：

* `abstract` 方法不能声明为 `private`。这是显而易见的，因为我们无法无法重写 `private` 方法，而在 `abstract` 方法的情况下，方法体总会在子类中提供。
* 只有实例方法可以声明为 `abstract`，因为 `static` 方法不能被重写；声明一个 `abstract static` 方法将毫无意义，并会导致编译错误。
* `final` 方法不能是 `abstract` 的，反之亦然。
* 关键字 `abstract` 不能与方法的任何非访问权限的修饰符组合。
* 在接口中指定的方法隐式为 `abstract`，因为接口中只定义了方法原型。

### synchronized 修饰符：

`synchronized` 关键字可以用于方法和代码块。程序中可以多个线程同时执行。它们可能会尝试同时在同一个对象上执行多个方法。如果希望一次只有一个线程可以执行对象中的某个方法，可以将这些方法声明为 `synchronized`。它们的执行在所有线程之间是互斥的。

在任何给定时刻，最多有一个线程可以执行对象上的某个 `synchronized` 方法。此讨论也适用于类的 `static synchronized` 方法。

注意：`synchronized` 修饰符不适用于类或成员变量。

### native 修饰符：

`native` 修饰符只能引用方法。像 `abstract` 关键字一样，`native` 表示方法的体将在其他地方找到。`native` 方法体完全位于 JVM 之外，位于库中。`native` 代码用非 Java 语言（通常是 C 或 C++）编写，并针对单一目标机器类型编译。因此，违反了 Java 的平台独立性。将 Java 移植到新平台的人会实现大量的 `native` 代码来支持 GUI 组件、网络通信以及广泛其他特定平台的功能。然而，应用程序和 applet 程序员很少需要编写 `native` 代码。

### transient 修饰符：

对象可以使用序列化进行存储。序列化将对象转换为有利于存储对象的输出格式。稍后可以以序列化时相同的状态检索对象，这意味着包含在序列化中的所有字段将具有与序列化时相同的值。此类对象被称为持久化对象。

在类声明中，可以将某个字段指定为 `transient`，表示当类的对象被写入持久化存储时，其值不应被保存。

```java
class Experiment implements Serializable {
    transient int currentTemperature; // transient
    double mass; // 持久化值
}
```

对 `static` 变量指定 `transient` 修饰符是多余的，因此不建议这样做。`static` 变量不是序列化对象持久化状态的一部分。

### volatile 修饰符：

在执行期间，编译代码可能会为了效率缓存字段的值。由于多个线程可以访问同一个字段，确保缓存不会在读取和写入值时导致不一致是非常关键的。可以使用 `volatile` 修饰符来告知编译器不要尝试对该字段进行优化。

# 包装类 (Wrapper Classes)

Java 为每个基本数据类型都有对应的包装类，如下表所示：

| 基本数据类型 | 包装类 |
| :--- | :--- |
| boolean | Boolean |
| char | Character |
| byte | Byte |
| short | Short |
| int | Integer |
| long | Long |
| float | Float |
| double | Double |

## Number 类

抽象类 `Number` 定义了一个父类，封装数值类型 `byte`、`short`、`int`、`long`、`float` 和 `double` 的类都实现了该类。`Number` 类具有抽象方法，用于返回不同数值格式的对象值。这些方法是：

| 方法 | 说明 |
| :--- | :--- |
| `byte byteValue()` | 将指定的数字作为 `byte` 类型返回 |
| `short shortValue()` | 将指定的数字作为 `short` 类型返回 |
| `abstract int intValue()` | 将指定的数字作为 `int` 类型返回 |
| `abstract long longValue()` | 将指定的数字作为 `long` 类型返回 |
| `abstract float floatValue()` | 将指定的数字作为 `float` 类型返回 |
| `abstract double doubleValue()` | 将指定的数字作为 `double` 类型返回 |

**注意**：`byteValue()`、`shortValue()`、`intValue()`、`longValue()`、`floatValue()` 和 `doubleValue()` 方法返回值可能涉及舍入或截断。

### 示例 14.1

下面的示例演示了调用 `Number` 类的方法时是如何发生舍入和截断的。

```java
class Wrapper {
    public static void main(String args[] ) {
        Integer iObj = new Integer(128);
        System.out.println(iObj.byteValue()); // truncation
        Long lObj = new Long(123456789123456789L);
        System.out.println(lObj);
        System.out.println(lObj.doubleValue());
        Float fObj = new Float(3.99f);
        System.out.println(fObj.intValue()); // truncation
    }
}
```

**输出：**

```
-128
123456789123456789
1.23456789123456784E17
3
```

## 使用包装类的构造函数将基本数字转换为对象，并将数值对象转换回基本数字

### 示例 14.2

下面的示例演示了如何将基本类型封装成对象，以及如何将它们转换回基本类型。



```java
class Convert {
    public static void main(String args[]) {
        System.out.println("primitive numbers to objects using constructors");
        byte b = 15;
        Byte bObj = new Byte(b);
        System.out.println(bObj); // toString()
        short s = 205;
        Short sObj = new Short(s);
        System.out.println(sObj);
        int i = 32717;
        Integer iObj = new Integer(i);
        System.out.println(iObj);
        long l = 234543335565675L;
        Long lObj = new Long(l);
        System.out.println(lObj);
        float f = 3.145f;
        Float fObj = new Float(f);
        System.out.println(fObj);
        double d = 3.1415;
        Double dObj = new Double(d);
        System.out.println(dObj);

        System.out.println("numeric objects to primitive numbers");
        byte b1 = bObj.byteValue();
        short s1 = sObj.shortValue();
        int i1 = iObj.intValue();
        long l1 = lObj.longValue();
        float f1 = fObj.floatValue();
        double d1 = dObj.doubleValue();
        System.out.println(b1);
        System.out.println(s1);
        System.out.println(i1);
        System.out.println(l1);
        System.out.println(f1);
        System.out.println(d1);
    }
}
```

**输出：**

```
primitive numbers to objects using constructors
15
205
32717
234543335565675
3.145
3.1415
numeric objects to primitive numbers
15
205
32717
234543335565675
3.145
3.1415
```

## 使用包装类的 `toString()` 静态方法将基本数字转换为字符串的示例 14.3

```java
class ConvertPrimitiveToString {
    public static void main(String args[]) {
        System.out.println("primitive numbers to String using toString() static method of wrapper class:");
        byte b = 105;
        String str = Byte.toString(b);
        System.out.println(str);
        short s = 303;
        str = Short.toString(s);
        System.out.println(str);
        int i = 100;
        str = Integer.toString(i);
        System.out.println(str);
        long l = 45444444444l;
        str = Long.toString(l);
        System.out.println(str);
        float f = 3.444f;
        str = Float.toString(f);
        System.out.println(str);
        double d = 3.44444;
        str = Double.toString(d);
        System.out.println(str);
    }
}
```

**输出：**

```
primitive numbers to String using toString() static method of wrapper class:
105
303
100
45444444444
3.444
3.14444
```

## 使用包装类的 `toString()` 方法将对象转换为字符串

```java
class ObjectDemo {
    public static void main(String args[]) {
        System.out.println("numeric objects to Strings using toString() method of wrapper class");
        byte b = 105;
        Byte bObj = new Byte(b);
        String str = bObj.toString();
        System.out.println(str);
        short s = 203;
        Short sObj = new Short(s);
        str = sObj.toString();
        System.out.println(str);
    }
}
```

使用相应包装类的 `toString()` 方法将对象数字转换为字符串：

```java
System.out.println(str);
Integer iObj = new Integer(32000);
str = iObj.toString();
System.out.println(str);
str = new Long(4544444444444l).toString();
System.out.println(str);
str = new Float(3.1444f).toString();
System.out.println(str);
str = new Double(4.1444).toString();
System.out.println(str);
```

输出：

```
103
203
32000
4544444444444
3.1444
4.1444
```

## 使用相应包装类的静态 `valueOf()` 方法将字符串对象（数字字符串）转换为数值对象

### 示例 14.5

#### 1. `StringToNumericObjectDemo`

```java
class StringToNumericObjectDemo {
    public static void main(String args[]) {
        String str = "30";
        String str2 = "30.33";
        Byte bObj = Byte.valueOf(str);
        System.out.println(bObj);
        //Byte bObj = new Byte(str2); //NumberFormatException
        Short sObj = Short.valueOf(str);
        System.out.println(sObj);
        Integer iObj = Integer.valueOf(str);
        System.out.println(iObj);
        Long lObj = Long.valueOf("344324232432");
        System.out.println(lObj);
        Float fObj = Float.valueOf("3.333");
        System.out.println(fObj);
        Double dObj = Double.valueOf(str2);
        System.out.println(dObj);
    }
}
```

输出：

```
30
30
344324232432
3.33
30.33
```

注：如果字符串不包含可解析的数字，所有 `valueOf()` 方法都会抛出 `NumberFormatException`。

## 使用相应包装类的构造函数将字符串对象（数字字符串）转换为数值对象

### 示例 4.6

```java
class StringToNumericDemo1 {
    public static void main(String args[]) {
        String str = new String("30");
        //str = "30";
        String str2 = new String("30.333");
        Byte bObj = new Byte(str);
        System.out.println(bObj);
        //Byte bObj=new Byte(str2); //NumberFormatException
        Short sObj = new Short(str);
        System.out.println(sObj);
        Integer iObj = new Integer(str);
        System.out.println(iObj);
        Long lObj = new Long(str);
        System.out.println(lObj);
        Float fObj = new Float(str);
        System.out.println(fObj);
        Double dObj = new Double(str);
        System.out.println(dObj);
    }
}
```

输出：

```
30
30
30
30
30.333
30.333
```

注：如果字符串不包含可解析的数字，上述构造函数将抛出 `NumberFormatException`。

## 使用相应包装类的解析方法将字符串对象（数字字符串）转换为基本类型数字

### 示例 14.7

```java
class StringToPrimitiveDemo {
    public static void main(String args[]) {
        String str = new String("30");
        //str = "30";
        String str2 = new String("30.33");
        byte b = Byte.parseByte(str);
        System.out.println(b);
        //byte b1=Byte.parseByte(str2); //NumberFormatException
        short s = Short.parseShort(str);
        System.out.println(s);
        int i = Integer.parseInt(str);
        System.out.println(i);
        long l = Long.parseLong(str);
        System.out.println(l);
        float f = Float.parseFloat(str2);
        System.out.println(f);
        double d = Double.parseDouble(str2);
        System.out.println(d);
    }
}
```

（注：示例 14.7 的原始文本在源代码块中存在格式不一致的问题；我已根据提供的代码逻辑对其结构进行了清理）。

## `Byte` 类

| 方法 | 说明 |
| :--- | :--- |
| `static Byte decode(String nm)` | 返回一个包含字符串 `nm` 所指定值的 `Byte` 对象。接受由以下语法提供的十进制、十六进制和八进制数：`DecodableString:[-] DecimalNumerical[-] 0x HexDigits[-] 0X HexDigits[-] # HexDigits[-] 0 OctalDigits` |
| `boolean equals(Object obj)` | 将 `this` 对象与指定的对象进行比较。 |
| `int hashCode()` | 返回此 `Byte` 的哈希码。 |

## `Short` 类中的其他方法

`Short` 类的方法与 `Byte` 类的方法相同，仅在上述表格中使用 `short` 和 `Short` 单词代替了 `byte` 和 `Byte` 单词。

## `Integer` 类中的其他方法

某些方法与 `Byte` 或 `Short` 类的方法相同。其他方法描述如下所示：

| 方法 | 说明 |
| :--- | :--- |
| `static String toBinaryString(int i)` | 返回整数参数作为 2 进制无符号整数的字符串表示。 |
| `static String toHexString(int i)` | 返回整数参数作为 16 进制无符号整数的字符串表示。 |
| `static String toOctalString(int i)` | 返回整数参数作为 8 进制无符号整数的字符串表示。 |

## `Long` 类中的其他方法

`Long` 类的方法几乎与 `Integer` 类的方法相同。

## `Character` 类

`Character` 类将原始类型 `char` 的值封装在对象中。

### 构造函数

```java
Character(char value)
```

构造一个新分配的 `Character` 对象，用于表示指定的 `char` 值。

示例：`Character chObj = new Character('A');`

### 方法

`Character` 类的一些方法下表所示：

| 方法 | 说明 |
| :--- | :--- |
| `char charValue()` | 返回此 `Character` 对象的值。 |
| `static boolean isDefined(char ch)` | 确定指定的字符是否在 Unicode 中。 |
| `static boolean isDigit(char ch)` | 确定指定的字符是否为数字。 |
| `static boolean isJavaIdentifierPart(char ch)` | 确定指定的字符是否可以作为 Java 标识符的一部分（第一个字符外）。 |
| `static boolean isJavaIdentifierStart(char ch)` | 确定指定的字符是否允许作为 Java 标识符的首字符。 |
| `static boolean isLetter(char ch)` | 确定指定的字符是否为字母。 |
| `static boolean isLetterOrDigit(char ch)` | 确定指定的字符是否为字母或数字。 |
| `static boolean isLowerCase(char ch)` | 确定指定的字符是否为小写字母。 |
| `static boolean isSpaceChar(char ch)` | 确定指定的字符是否为 Unicode 空格字符。 |
| `static boolean isTitleCase(char ch)` | 确定指定的字符是否为标题大写字符。 |
| `static boolean isUpperCase(char ch)` | 确定指定的字符是否为大写字母。 |
| `static boolean isWhitespace(char ch)` | 根据 Java 确定指定的字符是否为空白字符。 |
| `static char toLowerCase(char ch)` | 将字符参数转换为小写。 |
| `static char toUpperCase(char ch)` | 将字符参数转换为大写。 |
| `static char toTitleCase(char ch)` | 将字符参数转换为标题大写。 |
| `int compareTo(Character anotherCharacter)` | 数值上比较两个 `Character` 对象。 |
| `int hashCode()` | 返回此 `Character` 的哈希码。 |
| `boolean equals(Object obj)` | 将 `this` 对象与指定的对象进行比较。 |

## `Boolean` 类

`Boolean` 类将原始类型 `boolean` 的值封装在对象中。

### 构造函数

| 构造函数 | 说明 |
| :--- | :--- |



| 构造方法 | 说明 |
| :--- | :--- |
| `Boolean(Boolean value)` | 分配一个表示值参数的 `Boolean` 对象。 |
| `Boolean(String s)` | 如果字符串参数不为空且在忽略大小写的情况下等于字符串“true”，则分配一个表示值 `true` 的 `Boolean` 对象。 |

### Boolean 类的方法

| 方法 | 说明 |
| :--- | :--- |
| `boolean booleanValue()` | 将此 `Boolean` 对象的值作为 `Boolean` 原始类型返回。 |
| `int compareTo(Boolean b)` | 将此实例与另一个比较。 |
| `boolean equals(Object obj)` | 当且仅当参数不为空且是一个与 `this` 表示相同布尔值的 `Boolean` 对象时，返回 true。 |
| `static Boolean getBoolean(String name)` | 当且仅当由参数命名的系统属性存在且等于字符串“true”时，返回 true。 |
| `int hashCode()` | 返回此 `Boolean` 对象的哈希码。 |
| `static boolean parseBoolean(String s)` | 将字符串参数解析为布尔值。 |
| `String toString()` | 返回表示此 `Boolean` 值的 `String` 对象。 |
| `static String toString(boolean b)` | 返回表示指定布尔值的 `String` 对象。 |
| `static Boolean valueOf(boolean b)` | 返回表示指定布尔值的 `Boolean` 实例。 |
| `static Boolean valueOf(String s)` | 返回一个表示指定字符串值的 `Boolean`。 |

# 章节：Java 输入/输出

## 引言

## 流

Java 程序通过流进行输入/输出。流是一个产生或消耗信息的抽象。流通过物理设备连接到系统。

所有流的行为都是相同的，即使它们连接的实际物理设备不同。相同的输入输出类和方法可以应用于任何类型的设备。

## 输入流和输出流

Java 流分为两种基本类型：输入流和输出流。输入流从源提取（即读取）数据并将其发送到程序。

程序连接并打开输入流，然后顺序读取数据。同样，程序连接并打开到数据目的地的输出流，并顺序写入数据。在这两种情况下，程序都不知道端点的细节（即源和目的地）。

## 字节流和字符流

Java2 定义了两种流：字节流和字符流。字节流为处理字节输入输出提供了方便的方法。字节流通常用于读取或写入二进制数据。字符流使用 Unicode，因此可以进行国际化。此外，在某些情况下，字符流比字节流更高效。Java 的原始版本（Java 1.0）不包含字符流，因此，所有的输入/输出都是面向字节的。

我们还可以根据流读取或写入的源或目的类型对流进行跨组分类。源（或目的地）可能是内存、文件或管道。

![Java 流类的分类](img/image01245.jpeg)

![Java 流类的分类](img/image01246.jpeg)

## 字节流类概述

字节流类通过两个类层次结构来定义。顶端是两个抽象类：

1. `InputStream`
2. `OutputStream`

这些抽象类中的每一个都有多个具体的子类，用于处理各种设备之间的差异，例如磁盘文件、网络连接甚至内存缓冲区。

### InputStream 类

用于读取 8 位字节的 `InputStream` 类包括一个名为 `InputStream` 的父类，以及若干支持各种输入相关函数的子类。

![输入流类的层次结构](img/image01247.jpeg)

![输入流类的层次结构](img/image01248.jpeg)

![输入流类的层次结构](img/image01249.jpeg)

#### InputStream 类

父类 `InputStream` 是一个抽象类，它定义了执行输入功能的方法，例如：

*   读取字节
*   关闭流
*   在流中标记位置
*   在流中跳过
*   查找流中的字节数

##### InputStream 类的方法

| 方法 | 说明 |
| :--- | :--- |
| `int available()` | 提供输入中可用字节数（必须由子类重写）。`InputStream` 类的 `available` 方法始终返回 0。 |
| `void close()` | 关闭此输入流并释放与流相关的任何系统资源。`InputStream` 的 `close` 方法没有任何操作。 |
| `void mark(int readlimit)` | 标记此输入流中的当前位置。`InputStream` 的 `mark` 方法没有任何操作。 |
| `boolean markSupported()` | 测试此输入流是否支持 mark 和 reset 方法。`InputStream` 的 `markSupported` 方法返回 false。 |
| `abstract int read()` | 从输入流中读取下一个字节数据。子类必须提供此方法的实现。 |
| `int read(byte[] b)` | 从输入流中读取若干字节并将其存储在缓冲区数组 `b` 中。实际读取的字节数作为整数返回。 |
| `int read(byte[] b, int offset, int len)` | 从输入流中读取若干字节并从参数 `off` 指定的位置开始存储到缓冲区数组 `b` 中。实际读取的字节数作为整数返回。 |
| `void reset()` | 将此流重新定位到上次对此输入流调用 `mark` 方法时的位置。`InputStream` 的 `reset` 方法没有任何操作并始终抛出 `IOException`。 |
| `long skip(long n)` | 跳过并丢弃此输入流最多 `n` 个字节的数据，并返回实际跳过的字节数。 |

#### DataInput 接口

`DataInput` 是一个接口，它定义了从 `InputStream` 读取原始数据类型的方法。

##### DataInput 接口的方法

| 方法 | 说明 |
| :--- | :--- |
| `boolean readBoolean()` | 读取一个输入字节，如果该字节非零则返回 true，如果为零则返回 false。 |
| `byte readByte()` | 读取并返回一个字节输入。 |
| `char readChar()` | 读取一个输入字符并返回其值。 |
| `double readDouble()` | 读取八个输入字节并返回一个 double 值。 |
| `float readFloat()` | 读取四个输入字节并返回一个 float 值。 |
| `void readFully(byte[] b)` | 从输入流中读取若干字节并存储在缓冲区数组 `b` 中。如果此流在读取所有字节之前到达末尾，该方法将抛出 `EOFException`。 |
| `void readFully(byte[] b, int off, int len)` | 从输入流中读取 `len` 个字节并从 `off` 指定的位置开始存储在缓冲区数组 `b` 中。如果此流在读取所有字节之前到达末尾，该方法将抛出 `EOFException`。 |
| `int readInt()` | 读取四个输入字节并返回一个 `int` 值。 |
| `String readLine()` | 从输入流中读取下一行。 |
| `long readLong()` | 读取八个输入字节并返回一个 `long` 值。 |
| `short readShort()` | 读取两个输入字节并返回一个 `short` 值。 |
| `String readUTF()` | 读取使用修改后的 UTF-8 格式编码的字符串。 |
| `int skipBytes(int n)` | 尝试从输入流中跳过 `n` 个字节的数据，忽略跳过的字节。返回实际跳过的字节数。 |

#### InputStream 类总结

| 类 | 说明 |
| :--- | :--- |
| `InputStream` | 此抽象类是所有表示字节输入流类的父类。 |
| `BufferedInputStream` | `BufferedInputStream` 为另一个输入流增加了功能，即缓冲输入并支持 mark 和 reset 方法。 |
| `ByteArrayInputStream` | `ByteArrayInputStream` 包含一个内部缓冲区，其中包含可以从流中读取的字节。 |
| `DataInputStream` | `DataInputStream` 允许应用程序从输入流读取原始数据类型。 |
| `FileInputStream` | `FileInputStream` 包含来自文件的输入字节。 |
| `FilterInputStream` | `FilterInputStream` 包含另一个输入流并将其作为基本数据源，可能在此过程中转换数据。 |
| `PipedInputStream` | `PipedInputStream` 应该连接到管道输出流，管道输入流随后提供管道输出流写入的数据。 |
| `PushbackInputStream` | `PushbackInputStream` 为另一个输入流增加了功能，即“回退”或未读回一个字节。 |
| `SequenceInputStream` | `SequenceInputStream` 代表类的逻辑连接。 |
| `ObjectInputStream` | `ObjectInputStream` 读取之前使用 `ObjectOutputStream` 写入的原始数据对象。 |

注意 `DataInputStream` 类继承自 `FilterInputStream` 并实现了 `DataInput` 接口。因此，`DataInputStream` 在继承 `FilterInputStream` 并在其使用 `InputStream` 类的方法外，还实现了 `DataInput` 中描述的方法。

### OutputStream 类

`OutputStream` 类派生自基类 `OutputStream`，它是一个抽象类并有若干支持各种输出功能的子类。

#### OutputStream 类

父类 `OutputStream` 是一个抽象类，它定义了执行输出功能的方法，例如：

*   写入字节
*   关闭流
*   刷新流

##### OutputStream 类的方法

| 方法 | 说明 |
| :--- | :--- |
| `void close()` | 关闭此输出流并释放与流相关的任何流资源。 |
| `void flush()` | 刷新此输出流并强制将缓冲的输出字节写出。 |
| `void write(byte[] b)` | 从指定的字节数组写入 `b.length` 个字节到其输出流。 |
| `void write(byte[] b, int off, int len)` | 从指定的字节数组从偏移量 `off` 开始写入 `len` 个字节到其输出流。 |
| `abstract void write(int b)` | 将指定的字节写入其输出流。 |

#### DataOutput 接口

`DataOutput` 是一个接口，它定义了向 `OutputStream` 写入原始数据类型的方法。

![IO_LayeredInput](img/image01252.jpeg)

![DataOutput 接口](img/image01253.jpeg)

##### DataOutput 接口方法

| 方法 | 说明 |
| :--- | :--- |
| `void writeBoolean(boolean v)` | 将一个布尔值写入其输出流。 |
| `void writeByte(int v)` | 向输出流写入参数 `v` 的八个低位。 |
| `void writeBytes(String s)` | 将字符串写入输出流。按照顺序对字符串 `s` 中的每个字符向输出流写入一个字节。 |
| `void writeChar(int v)` | 将一个由两个字节组成的字符值写入输出流。 |
| `void writeChars(String s)` | 将字符串 `s` 中的每个字符按每个两个字节的顺序写入输出流。 |
| `void writeDouble(double v)` | 将一个由八个字节组成的双精度浮点数值（double）写入输出流。 |
| `void writeFloat(float v)` | 将一个由四个字节组成的单精度浮点数值（float）写入输出流。 |
| `void writeInt(int v)` | 将一个由四个字节组成的整数值（int）写入输出流。 |
| `void writeLong(long v)` | 将一个由八个字节组成的长整数值（long）写入输出流。 |
| `void writeShort(int v)` | 将一个由两个字节组成的短整数值（short）写入输出流。 |
| `void writeUTF(String str)` | 向输出流写入两个字节的长度信息，随后是字符串 `s` 中每个字符的修改后的 UTF-8 表示。 |

#### OutputStream 类总结

`DataOutputStream` 是 `DataInputStream` 的对等类。`DataOutputStream` 类在使用 `OutputStream` 类方法外，还实现了 `DataOutput` 接口中描述的方法。

| 类 | 说明 |
| :--- | :--- |
| `OutputStream` | 此抽象类是所有表示字节输出流的类的父类。 |
| `BufferedOutputStream` | 该类实现了一个带缓冲的输出流。 |
| `ByteArrayOutputStream` | 该类实现了一个输出流，其中数据被写入字节数组中。 |
| `DataOutputStream` | 数据输出流允许应用程序以可移植的方式将 Java 原始数据类型写入输出流。 |
| `FileOutputStream` | 文件输出流是用于向 `File` 写入数据的输出流。 |
| `PipedOutputStream` | 管道输出流可以连接到管道输入流以创建通信管道。 |
| `FilterOutputStream` | `FilterOutputStream` 包含一些其他输出流，它将其作为目标，并可能在传输过程中对数据进行转换或提供额外功能。 |
| `PrintStream` | `PrintStream` 为另一个输出流增加了功能，即方便地打印各种数据值的表示的能力。 |

## 字符流类概览

字符流通过使用两个类层次结构定义。顶端是两个抽象类：`Reader` 和 `Writer`。这些抽象类处理 Unicode 字符流。

Java 拥有这些每个抽象类的几个具体子类。抽象的 `Reader` 和 `Writer` 类定义了其他流类实现的几个关键方法。其中最重要的两个方法是 `read()` 和 `write()`，它们分别读取和写入字符数据。这些方法被派生流类重写。

### Reader 流类

Reader 流类设计用于从文件中读取字符。`Reader` 类是此组中所有其他类的基类。这些类在功能上与输入流类非常相似，但输入流使用字节作为信息的根本单位，而 reader 流使用字符。

`Reader` 类包含了与 `InputStream` 类中提供的相同的方法。因此，`Reader` 类可以执行输入流类实现几乎的所有功能。

![Reader 流类层次结构](img/image01254.jpeg)

### Reader 类

`Reader` 是一个抽象类，定义了 Java 的字符输入流模型。该类中的所有方法都将抛出 `IOException`。

#### Reader 类方法

| 方法 | 说明 |
| :--- | :--- |
| `abstract void close()` | 关闭流。一旦流被关闭，进一步的 `read()`、`ready()`、`mark()` 或 `reset()` 调用将抛出 `IOException`。然而，关闭一个已经关闭的流将没有任何影响。 |
| `void mark(int readAheadLimit)` | 标记流中的当前位置。随后调用 `reset()` 将尝试将流重置到此点。并不是所有的字符输入流都支持 `mark()` 操作。 |
| `boolean markSupported()` | 告诉此流是否支持 `mark()` 操作。 |
| `int read()` | 读取单个字符并返回来自调用输入流的下一个可用字符的整数表示。当遇到文件末尾时返回 -1。 |
| `int read(char[] buffer)` | 尝试读取最多 `buffer` 长度的字符到 `buffer` 中，并返回成功读取的字符数。当遇到文件末尾时返回 -1。reader 子类必须实现此方法。 |
| `abstract int read(char[] buffer, int offset, int numChar)` | 尝试从 `buffer[offset]` 开始读取最多 `numChar` 个字符到 `buffer` 中，返回成功读取的字符数。当遇到文件末尾时返回 -1。reader 子类必须实现此方法。 |



## Reader 类方法

| 方法 | 说明 |
| :--- | :--- |
| `boolean ready()` | 告诉是否准备好读取。如果读取请求将等待则返回 `true`，否则返回 `false`。 |
| `void reset()` | 重置流。并不是所有字符输入流都支持此方法。 |
| `long skip(long n)` | 跳过 `n` 个字符并返回跳过的字符数。如果 `n` 为负则抛出 `IllegalArgumentException`。 |

## Reader 类总结

| 类 | 说明 |
| :--- | :--- |
| `Reader` | 读取字符流的抽象类。 |
| `BufferedReader` | 从字符输入流读取文本，缓冲字符以便高效读取字符和行。 |
| `CharArrayReader` | 实现一个可以作为字符输入流缓冲区。 |
| `FileReader` | 读取字符的便利类。 |
| `FilterReader` | 读取过滤字符流的抽象类。 |
| `InputStreamReader` | 字节流到字符流的桥接：它使用指定的字符将字节解码为字符。 |
| `PipedReader` | 管道字符输入流。 |
| `PushbackReader` | 允许将字符推回流的字符读取器。 |
| `StringReader` | 源自字符串的字符流。 |

## Writer 类

Writer 流类设计用于向文件/输出设备写入字符。`Writer` 类是一个抽象类，作为其他写入流类的基类。通过定义与 `OutputStream` 类相同的方法提供了对所有输出操作的支持。

`Writer` 类包含了与 `OutputStream` 类提供的相同的方法。因此，`Writer` 类可以执行输出类实现几乎的所有功能。

![](img/image01255.jpeg)

(Writer 流类层次结构)

### Writer 类方法

| 方法 | 说明 |
| :--- | :--- |
| `abstract void close()` | 关闭流并先刷新。 |
| `abstract void flush()` | 刷新流。 |
| `void write(char[] cbuf)` | 写入字符数组。 |
| `abstract void write(char[] cbuf, int off, int len)` | 从指定的偏移量开始写入数组的一部分。子类必须实现此方法。 |
| `void write(int c)` | 向调用的输出流写入单个字符。请注意该参数类型为 `int`，这允许你直接对表达式调用 `write`，而无需将其强制转换回 `char`。 |
| `void write(String str)` | 写入一个字符串。 |
| `void write(String str, int off, int len)` | 写入字符串从指定偏移量开始的部分。 |

![C:\Users\Made Man Harry\Desktop\Stars\Star_logo_yellow.jpg](img/image01257.jpeg)

## Writer 类摘要

| 类 | 描述 |
| :--- | :--- |
| `Writer` | 用于写入字符流的抽象类。 |
| `BufferedWriter` | 向字符输出流写入文本，通过对字符进行缓冲，提供单个字符、数组和字符串的高效写入。 |
| `CharArrayWriter` | 该类实现了一个可以作为 `Writer` 的字符缓冲区。 |
| `FileWriter` | 用于写入字符文件的便利类。 |
| `FilterWriter` | 用于写入过滤字符流的抽象类。 |
| `OutputStreamWriter` | `OutputStreamWriter` 是字符流到字节流的桥梁：写入它的字符将使用指定的 `charset` 编码为字节。 |
| `PipedWriter` | 管道字符输出流。 |
| `PrintWriter` | 向文本输出流打印对象的格式化表示。 |
| `StringWriter` | 一种字符流，将其输出收集在字符串缓冲区中，然后可以使用它来构造字符串。 |

## File 类

尽管 `java.io` 中定义的大多数类都是对流的操作，但 `File` 类并不是。它直接处理文件和文件系统。也就是说，`File` 类并没有指定如何从文件中检索信息或将其存储在文件中。它描述的是类本身的属性。

文件对象用于获取或操作与磁盘文件相关的信息，例如权限、时间、日期和目录路径，并导航子目录层次结构。

虽然出于安全考虑，文件在 applet 中的使用受到严格限制，但文件仍然是存储持久性和共享信息的核心资源。

Java 中的目录被简单地视为一个文件，额外多了一个属性——一个可以通过 `list()` 方法检查的文件名列表。

### File 构造函数

| 构造函数 | 描述 |
| :--- | :--- |
| `public File(String)` | 构造函数 |
| `public File(String, String)` | 构造函数 |
| `public File(File, String)` | 构造函数 |
| `public File(URI)` | 此构造函数在 Java 2（版本 1.4）中被添加 |

### File 方法

| 方法 | 描述 |
| :--- | :--- |
| `public String getName()` | 返回 `file` 或目录的名字 |
| `public String getParent()` | 返回从对象创建期间指定的 `path` 的 `file` 的父目录；如果该 `pathname` 未命名父目录，则返回 `null`。 |
| `public String getPath()` | 返回相对路径。 |
| `public boolean isAbsolute()` | 测试此抽象 `pathname` 是否为绝对路径。 |
| `public String getAbsolutePath()` | 返回从根开始的绝对（完整）路径。 |
| `public boolean canRead()` | 测试应用程序是否可以读取此抽象 `pathname` 所指示的文件。 |
| `public boolean canWrite()` | 测试应用程序是否可以修改此抽象 `pathname` 所指示的文件。 |
| `public boolean exists()` | 测试此抽象 `pathname` 所指示的文件或目录是否存在。 |
| `public boolean isDirectory()` | 测试此抽象 `pathname` 所指示的是否为目录。 |
| `public boolean isFile()` | 测试此抽象 `pathname` 所指示的是否为普通文件。 |
| `public boolean isHidden()` | 测试此抽象 `pathname` 命的文件是否为隐藏文件。 |
| `public long lastModified()` | 返回此抽象 `pathname` 所指示的文件最后修改的时间。 |
| `public long length()` | 返回此抽象 `pathname` 所指示的文件长度。 |
| `public boolean createNewFile() throws java.io.IOException` | 仅当不存在名为此名称的文件时，自动创建一个由此抽象 `pathname` 命名的新空文件。 |
| `public boolean delete()` | 删除此抽象 `pathname` 所指示的文件或目录。 |
| `public String[] list()` | 返回表示此抽象 `pathname` 所指示目录中的文件和目录名称的字符串数组。如果 `File` 对象对应文件，则返回 `null`。 |
| `public boolean mkdir()` | 创建由此抽象 `pathname` 命名的目录。 |
| `public boolean mkdirs()` | 创建由此抽象 `pathname` 命名的目录，包括任何必要的但不存在的父目录。 |
| `public boolean setLastModified(long)` | 设置此抽象 `pathname` 命名的文件或目录的最后修改时间。 |
| `public boolean setReadOnly()` | 标记此抽象 `pathname` 命名的文件或目录，使其只允许读操作。 |
| `public boolean setWritable(boolean)` | |
| `public boolean setReadable(boolean)` | |
| `public boolean canExecute()` | |
| `public long getTotalSpace()` | |
| `public long getFreeSpace()` | |
| `public long getUsableSpace()` | |
| `boolean renameTo(File)` | 重命名此抽象 `pathname` 所指示的文件。 |

#### 示例

```java
File f1 = new File("/");
File f2 = new File("/", "autoexec");
File f3 = new File(f1, "autoexec");
```

### 注意

Java 在所有平台上的路径分隔符都使用正斜杠 `/`。在 Windows 版本中，反斜杠 `\` 也是路径分隔符。如果你在 Windows 上使用正斜杠，Java 也能正确解析。

### 示例 15.1: 遵循类的几种方法

```java
import java.io.*;

class FileTest {
    public static void main(String args[]) throws IOException {
        File f = new File("/javap/ch15/15.1/FileTest.java");
        if(!f.exists()) {
            f.createNewFile();
        }
        System.out.println("Length=" + f.length() + " bytes");
        System.out.println("Name=" + f.getName());
        System.out.println("Parent=" + f.getParent());
        System.out.println("Absolute Path=" + f.getAbsolutePath());
        System.out.println(f.exists() ? "Exists" : "Does not exist");
        System.out.println(f.isFile() ? "is file" : "not a file");
        System.out.println(f.canRead() ? "is readable" : "not readable");
        System.out.println(f.canWrite() ? "is writable" : "not writable");
        System.out.println(f.isDirectory() ? "is directory" : "not a directory");
        System.out.println(f.isHidden() ? "is hidden" : "not hidden");
        System.out.println(f.isAbsolute() ? "is absolute" : "is not absolute");
        System.out.println("File modified:" + f.lastModified());
        // f.delete();
        File f3 = new File("C:/tally2");
        String[] nm = f3.list();
        System.out.println("List of Files & Directories of c:/tally2");
        for (int i = 0; i < nm.length; i++) {
            System.out.print(nm[i]);
            File f4 = new File("c:/tally2/" + nm[i]);
            if(f4.isFile() == true)
                System.out.println(" It is a File");
            else
                System.out.println(" It is a Directory");
        }
        File f5 = new File("zzz");
        f5.mkdir();
        File f6 = new File("yyy/aaa");
        f6.mkdirs();
    }
}
```

### 输出

```text
Length=1782 bytes
Name=FileTest.java
Parent=\javaprog\ch15\15.1
Path=\javaprog\ch15\15.1\FileTest.java
Absolute Path=C:\javaprog\ch15\15.1\FileTest.java
Exists
is file
is readable
is writable
not a directory
not hidden
is not absolute
File last modified :1236824168000
```

### c:/tally72 的文件与子目录列表

- TALLY.REW 这是一个文件
- Tally.ini 这是一个文件
- sentinel.sys 这是一个文件
- sentinel.vxd 这是一个文件
- spnsrv9x.exe 这是一个文件
- spnsrvnt.exe 这是一个文件
- stat.slk 这是一个文件
- tally72.exe 这是一个文件
- tallylic9xserver.exe 这是一个文件
- tallylicserver.exe 这是一个文件
- tallysav.dat 这是一个文件
- tallywin.dat 这是一个文件
- tally.imp 这是一个文件
- Data 这是一个目录

## FileInputStream

它是 `InputStream` 类的直接子类。为了打开文件进行读取，你只需创建 `FileInputStream` 类的一个对象，并将文件名（直接或间接）作为构造函数的参数传递进去即可。

| 方法 | 描述 |
| :--- | :--- |
| `public FileInputStream(String) throws FileNotFoundException` | 通过打开与实际文件的连接来创建 `FileInputStream`，该文件是由文件系统中路径名 `filePath` 命名的。 |
| `public FileInputStream(File) throws FileNotFoundException` | 通过打开与实际文件的连接来创建 `FileInputStream`，该文件是由文件系统中 `File` 对象 `file` 命名的。 |
| `public native int read() throws IOException` | |
| `public int read(byte[]) throws IOException` | |
| `public int read(byte[], int, int) throws IOException` | |
| `public native long skip(long) throws IOException` | |
| `public native int available() throws IOException` | |
| `public void close() throws IOException` | |

## FileOutputStream

它是 `OutputStream` 类的直接子类。为了打开文件进行写入，我们只需创建 `FileOutputStream` 类的一个对象，并将文件名（直接或间接）作为构造函数的参数传递即可。

| 方法 | 描述 |
| :--- | :--- |
| `public FileOutputStream(String) throws FileNotFoundException` | 创建一个向指定文件写入的输出流。 |
| `public FileOutputStream(String, boolean) throws java.io.FileNotFoundException` | 创建一个向指定文件写入的输出流。 |
| `public FileOutputStream(File) throws FileNotFoundException` | 创建一个向 `File` 对象代表的文件写入的输出流。 |
| `public FileOutputStream(File, boolean) throws FileNotFoundException` | 创建一个向 `File` 对象代表的文件写入的输出流。 |
| `public native void write(int) throws java.io.IOException` | |



| `public void write(byte[]) throws java.io.IOException` | |
| `public void write(byte[], int, int) throws java.io.IOException` | |
| `public void close() throws java.io.IOException` | |

#### 示例 5.2

```java
import java.io.*;
class FileRead {
    public static void main(String args[]) {
        FileInputStream fin = null;
        int a;
        try {
            fin = new FileInputStream(args[0]);
            System.out.println("No. of characters to read=" + fin.available());
            fin.skip(3);
            a = fin.read();
            while (a != -1) {
                System.out.print((char) a);
                a = fin.read();
            }
            System.out.println("No. of characters to read=" + fin.available());
            fin.close();
        } catch (ArrayIndexException e) {
            System.out.println(e);
        } catch (FileNotFoundException e) {
            System.out.println(e);
        } catch (IOException e) {
            System.out.println(e);
        }
    }
}
```

输出:

```text
A.txt
No. of characters to read=20
Computers
No. of characters to read=0
```

### 示例 5.3

```java
import java.io.*;
class FileCopy {
    public static void main(String args[]) throws IOException {
        FileInputStream fin = null;
        FileOutputStream fout = null;
        fin = new FileInputStream(args[0]);
        fout = new FileOutputStream(args[1]);
        int a;
        a = fin.read();
        while (a != -1) {
            fout.write(a);
            a = fin.read();
        }
        fin.close();
        fout.close();
    }
}
```

#### 示例 5.4

```java
import java.io.*;
class CopyFile {
    public static void main(String args[]) throws IOException {
        int n;
        FileInputStream fin = new FileInputStream("A.txt");
        FileOutputStream fout = new FileOutputStream("B.txt");
        byte b[] = new byte[10];
        n = fin.read(b);
        while (n != -1) {
            fout.write(b, 0, n);
            n = fin.read(b);
        }
        fin.close();
        fout.close();
    }
}
```

### FileReader

`FileReader` 类创建了一个 `Reader`，你可以用它来读取文件的内容。它最常用的两个构造函数是：

- `FileReader(File file)`：创建一个 `FileReader` 流，用于从指定的文件读取内容。
- `FileReader(String fileName)`：创建一个 `FileReader` 流，用于从指定的文件读取内容。

**注意：** 如果文件不存在、是一个目录而不是普通文件，或者由于其他原因无法打开读取，任何一个构造函数都会抛出 `FileNotFoundException`。

## FileWriter

`FileWriter` 类创建了一个写入器，你可以用它写入文件。它最常用的两个构造函数是：

### 构造函数

- `FileWriter(File file)`：构造一个 `FileWriter` 对象以写入指定文件。
- `FileWriter(String fileName)`：构造一个 `FileWriter` 对象以写入指定文件。
- `FileWriter(File file, boolean append)`：构造一个 `FileWriter` 对象，以追加模式写入指定文件。
- `FileWriter(String filename, boolean append)`：构造一个 `FileWriter` 对象，以追加模式写入指定文件。

如果使用前两个构造函数，则总是创建一个新文件。如果存在同名的文件，它会被删除。如果使用后两个构造函数且 `append` 标志为 false，则它们的行为与前两个构造函数相同。

如果 `append` 标志为 true，则以追加模式打开文件，即如果文件已存在，文件指针将指向文件末尾；如果文件不存在，则创建一个新文件。

**注意：**

如果文件存在但是目录而不是普通文件、不存在但无法创建，或由于其他原因无法打开，这些构造函数可能会抛出 `IOException`。例如，当你尝试打开一个只读文件时，将抛出 `IOException`。

### 示例 15.5

```java
import java.io.*;
class FileCopy {
    public static void main(String args[]) throws IOException {
        FileReader fin = null;
        FileWriter fout = null;
        fin = new FileReader(args[0]);
        fout = new FileWriter(args[1]);
        int a;
        a = fin.read();
        while (a != -1) {
            fout.write((char) a);
            a = fin.read();
        }
        fin.close();
        fout.close();
    }
}
```

## RandomAccessFile

`RandomAccessFile` 封装了一个随机访问文件。`RandomAccessFile` 允许我们在使用适当访问权限的情况下，从文件的任意位置读取或写入字节、文本和原始数据类型。它没有继承自 `InputStream`，而是实现了 `DataInput` 和 `DataOutput` 接口，这两个接口定义了基本的 I/O 方法。它还支持定位请求——也就是说你可以将文件指针定位到文件的任何位置。

`mode` 参数指定打开文件时的访问模式。允许的值及其含义如下：

| 值 | 含义 |
| :--- | :--- |
| `"r"` | 仅读打开。调用结果对象的任何写入方法都会导致抛出 `IOException`。 |
| `"rw"` | 读写打开。如果文件不存在，则将尝试创建它。 |
| `"rws"` | 读写打开，与 `"rw"` 相同，并且要求对文件内容或元数据的每次更新都同步写入底层存储设备。 |
| `"rwd"` | 读写打开，与 `"rw"` 相同。并且要求对文件内容（数据）的每次更新都同步写入底层存储设备。 |

### RandomAccessFile 类的方法

除了 `DataInput` 和 `DataOutput` 接口的方法外，该类的一些常用方法包括：

- `public RandomAccessFile(String, String) throws java.io.FileNotFoundException`：创建一个随机访问文件流，用于读取并可选地写入指定名称的文件。
- `public RandomAccessFile(File, String) throws FileNotFoundException`：创建一个随机访问文件流，用于读取并可选地写入 `File` 参数指定的文件。
- `public native int read() throws java.io.IOException`
- `public int read(byte[], int)`
- `public int read(byte[])`
- `public int skip(int)`
- `public native void write(int)`
- `public void write(byte[])`
- `public void write(byte[], int)`
- `public native long getPointer()`
- `public void seek(long)`
- `public native long length()`
- `public void setLength(long)`
- `public void close()`
- `public boolean readBoolean()`
- `public byte readByte()`
- `public int readUnsignedByte()`
- `public short readShort()`
- `public int readUnsignedShort()`
- `public char readChar()`
- `public int readInt()`
- `public long readLong()`
- `public float readFloat()`
- `public double readDouble()`
- `public String readLine()`
- `public String readUTF()`
- `public void writeBoolean(boolean)`
- `public void writeByte(int)`
- `public void writeChar(int)`
- `public void writeInt(int)`
- `public void writeLong(long)`
- `public void writeFloat(float)`
- `public void writeDouble(double)`
- `public void writeBytes(String)`
- `public void writeChars(String)`
- `public void writeUTF(String)`

### 示例 15.6

```java
import java.io.*;
class RandomIO {
    public static void main(String args[]) throws IOException {
        RandomAccessFile file = null;
        try {
            file = new RandomAccessFile("rand.dat", "rw");
            file.writeChar('X');
            file.writeInt(1999);
            file.writeDouble(222.44);
            System.out.println("File pointer Pos:" + file.getFilePointer());
            file.seek(0);
            System.out.println(file.readChar());
            System.out.println(file.readInt());
            System.out.println(file.readDouble());
            System.out.println("File pointer Pos:" + file.getFilePointer());
            file.seek(2);
            System.out.println("File Pos:" + file.getFilePointer());
            System.out.println(file.readInt());
            file.seek(file.length());
            file.writeBoolean(false);
            file.seek(4);
            System.out.println(file.readBoolean());
            System.out.println("File Pos:" + file.getFilePointer());
            System.out.println(file.readInt()); // Exception
        } catch (EOFException e) {
            System.out.println("Trying to read after end of file");
        } finally {
            file.close();
        }
    }
}
```

**输出：**

```text
File Pos:14
X
1999
222.4
File Pos:4
false
File Pos:15
Trying to read after end of file
```

注意：如果尝试在文件末尾之后进行读取，会发生 `EOFException`。

### ByteArrayInputStream

`ByteArrayInputStream` 是一个使用字节数组作为源的输入流实现。它包含一个内部字节缓冲区，可以从流中读取这些字节。该类有两个构造函数，每个构造函数都需要一个字节数组来提供数据。它实现了 `mark()` 和 `reset()` 方法。然而，如果没有调用 `mark()`，则 `reset()` 将指针置于流的开头。

- `ByteArrayInputStream(byte[])`
- `ByteArrayInputStream(byte[], int, int)`
- `synchronized int read()`
- `int read(byte[], int, int)`
- `synchronized long skip(long)`
- `synchronized int available()`
- `boolean markSupported()`
- `void mark(int)`
- `synchronized void reset()`
- `void close() throws IOException`

#### 示例 5.7

```java
import java.io.*;
class ByteArrayInputStreamTest {
    public static void main(String args[]) throws IOException {
        String s1 = "abcdefghijk";
        byte b[] = s1.getBytes();
        ByteArrayInputStream b1 = new ByteArrayInputStream(b);
        int a;
        while ((a = b1.read()) != -1) {
            System.out.print((char) Character.toUpperCase(a));
        }
        b1.close();
    }
}
```

**输出：** ABCDEFGHIJK

#### 示例 5.8



```java
import java.io.*;
class ByteArrayOutputStreamTest {
    public static void main(String args[]) throws IOException {
        ByteArrayOutputStream b1 = new ByteArrayOutputStream();
        b1.write('a');
        String s1 = "abcdefghijk";
        byte arr1[]= s1.getBytes();
        b1.write(arr1);
        System.out.println(b1);  //toString()
        // 使用 for 循环显示
        byte arr2[] = b1.toByteArray();
        for(int i=0;i<arr2.length;i++) {
            System.out.print((char)arr2[i]);
        }
        System.out.println();
        // 使用 each 循环显示
        for(int i:arr2) {
            System.out.print((char)i);
        }
        b1.close();
    }
}
```

### ByteArrayOutputStream

`ByteArrayOutputStream` 实现了一个写入字节数组的输出流。`ByteArrayOutputStream` 是一个使用字节数组作为目的地的输出流实现。缓冲区存储在 `ByteArrayOutputStream` 的 `buf` 字段中。如果需要，缓冲区的大小会自动增大。缓冲区持有的字节数包含在 `count` 字段中。

- `ByteArrayOutputStream()`
- `ByteArrayOutputStream(int)`
- `synchronized void write(int)`
- `synchronized void write(byte[], int, int)`
- `synchronized void writeTo(io.OutputStream) throws IOException`
- `synchronized void reset()`
- `synchronized byte[] toByteArray()`
- `synchronized int size()`
- `synchronized String toString()`
- `synchronized String toString(String) throws UnsupportedEncodingException`
- `synchronized String toString(int)`
- `void close() throws IOException`

从指定的字符数组创建一个 `CharArrayReader`。生成的读取器将从指定的偏移量开始读取。从此读取器可以读取的字符值总数将是 `length` 或 `buf.length`。

### 示例 15.9

```java
import java.io.*;

class CharArrayReaderTest {
    public static void main(String args[]) throws IOException {
        String tmp = "abcdefghijklmnopqrstuvwxyz";
        int length = tmp.length();
        char c[] = new char[length];
        tmp.getChars(0, length, c, 0);
        CharArrayReader input1 = new CharArrayReader(c);
        CharArrayReader input2 = new CharArrayReader(c, 0, 5);
        int i;
        while ((i = input1.read()) != -1) {
            System.out.print((char)i);
        }
        System.out.println();
        while ((i = input2.read()) != -1) {
            System.out.print((char)i);
        }
    }
}
```

**输出：**

abcdefghijklmnopqrstuvwxyz

abcde

### CharArrayWriter

`CharArrayWriter` 是一个写入流的实现，它使用字符数组缓冲区作为目标。

### 构造函数

- `CharArrayWriter()`
- `CharArrayWriter(int initialSize)`

在第一种形式中，将创建一个具有默认大小的缓冲区。在第二种形式中，创建一个按参数 `initialSize` 指定大小的缓冲区。

缓冲区存储在 `CharArrayWriter` 的 `buf` 字段中。如果需要，缓冲区的大小将会增加。缓冲区包含的字符数量由 `CharArrayWriter` 的 `count` 字段。`buf` 和 `count` 都是保护字段。

#### 示例 15.10

```java
import java.io.*;

class CharArrayWriterTest {
    public static void main(String args[]) throws IOException {
        CharArrayWriter f = new CharArrayWriter();
        String s = "This should end up in the array";
        char buf[] = new char[s.length()];
        s.getChars(0, s.length(), buf, 0);
        f.write(buf);
        System.out.println(f.toString());
        char c[] = f.toCharArray();
        for (int i = 0; i < c.length; i++) {
            System.out.print(c[i]);
        }
        FileWriter f2 = new FileWriter("test.txt");
        f.writeTo(f2);
        f2.close();
        f.reset();
        System.out.println();
        System.out.println("After:" + f.toString());
        for (int i = 0; i < 3; i++) {
            f.write('A');
            System.out.println(f.toString());
        }
    }
}
```

**输出：**

This should end up in the array

This should end up in the array

After:AAA

### 推回输入流 (Push back Input Stream)

`PushbackInputStream` 为另一个输入流增加了功能，即“推回”或“重读”一个字节的能力。缓冲区的用途之一就是实现推回。`pushback` 用于输入流，允许读取一个字节后将其返回流中。除了 `InputStream` 类常见的方法外，`PushbackInputStream` 还提供了此处所示的 `unread()` 方法：

| 方法签名 | 描述 |
| :--- | :--- |
| `public java.io.PushbackInputStream(java.io.InputStream, int);` | 创建一个具有指定大小推回缓冲区的 `PushbackInputStream`，并保存其参数输入流以备后用。这允许将多个字节返回输入流。 |
| `public java.io.PushbackInputStream(java.io.InputStream);` | 创建一个 `PushbackInputStream` 并保存其参数输入流以备后用。这允许将一个字节返回输入流。 |
| `public int read() throws java.io.IOException;` | |
| `public int read(byte[], int, int) throws java.io.IOException;` | |
| `public void unread(int) throws java.io.IOException;` | 通过将字节复制到推回缓冲区前端来推回一个字节。 |
| `public void unread(byte[], int, int) throws java.io.IOException;` | 通过将字节数组的一部分复制到推回缓冲区前端来推回部分字节数组。 |
| `public void unread(byte[]) throws java.io.IOException;` | 通过将字节数组复制到推回缓冲区前端来推回整个字节数组。 |
| `public int available() throws java.io.IOException;` | |
| `public long skip(long) throws java.io.IOException;` | |
| `public boolean markSupported();` | `PushbackInputStream` 的副作用是会使用于创建它的 `InputStream` 的 `mark()` 或 `reset()` 方法失效。使用 `markSupported()` 方法检查你将要使用 `mark()/reset()` 的任何流。 |
| `public synchronized void mark(int);` | |
| `public synchronized void reset() throws java.io.IOException;` | |
| `public synchronized void close() throws java.io.IOException;` | |

#### 示例 15.11

```java
import java.io.*;

class PushbackInputStreamTest {
    public static void main(String args[]) throws IOException {
        FileInputStream fin = new FileInputStream("A.txt");
        PushbackInputStream p1 = new PushbackInputStream(fin);
        int ch = p1.read();
        System.out.println((char)ch);
        ch = p1.read();
        System.out.println((char)ch);
        ch = p1.read();
        System.out.println((char)ch);
        p1.unread(ch); // or p1.unread('z')
        ch = p1.read();
        System.out.println((char)ch);
    }
}
```

**输出：**

A.txt 包含 “Matrix Computers”

m

a

t

| 方法签名 | 描述 |
| :--- | :--- |
| `public int read(char[], int, int) throws java.io.IOException;` | |
| `public void unread(int) throws java.io.IOException;` | 将单个字符推回。 |
| `public void unread(char[], int, int) throws java.io.IOException;` | 将字符数组的一部分拷贝到回退缓冲区头部，将其推回。 |
| `public void unread(char[]) throws java.io.IOException;` | 将一个数组拷贝到回退缓冲区头部，将其推回。 |
| `public boolean ready() throws java.io.IOException;` | |
| `public void mark(int) throws java.io.IOException;` | |
| `public void reset() throws java.io.IOException;` | |
| `public boolean markSupported();` | |
| `public void close() throws java.io.IOException;` | |
| `public long skip(long) throws java.io.IOException;` | |

注意：当回退缓冲区满时尝试返回字符，将抛出 `IOException`。

### 示例 15.12

```java
import java.io.*;
class PushbackReaderTest {
    public static void main(String args[]) throws IOException {
        FileReader fr = new FileReader("A.txt");
        PushbackReader pr=new PushbackReader(fr);
        int ch=pr.read();
        System.out.println((char)ch);
        ch=pr.read();
        System.out.println((char)ch);
        ch=pr.read();
        System.out.println((char)ch);
        pr.unread(ch);
        ch=pr.read();
        System.out.println((char)ch);
    }
}
```

**输出：**

```
m
a
t
t
```

### SequenceInputStream

`SequenceInputStream` 类是一个字节流，允许你连接多个 `InputStream`。序列 `InputStream` 的构造与其他任何 `InputStream` 都不同。`SequenceInputStream` 构造函数使用一对 `InputStream` 类或 `InputStream` 类的 `Enumeration` 作为其参数：

- `SequenceInputStream(InputStream is1, InputStream is2)`：通过记住两个参数来初始化新的 `SequenceInputStream`，这两个参数将按顺序读取（先是 `is1` 然后是 `is2`），以提供从该 `SequenceInputStream` 读取字节。
- `SequenceInputStream(Enumeration e)`：通过记住参数来初始化新的 `SequenceInputStream`，该参数必须是一个产生运行时类型为 `InputStream` 的对象的 `Enumeration`。

在操作上，该类会从第一个 `InputStream` 满足读取请求，直到其耗尽，然后切换到第二个。在 `Enumeration` 的情况下，它将继续遍历所有的 `InputStream` 直到达到最后一个的结束。

### 示例 15.13

在下面的示例中，将文件名作为命令行参数给出：

```java
import java.io.*;
class SequenceInputStreamTest {
    public static void main(String args[]) throws IOException {
        FileInputStream f1 = new FileInputStream(args[0]);
        FileInputStream f2 = new FileInputStream(args[1]);
        FileOutputStream f3 = new FileOutputStream(args[2]);
        SequenceInputStream sis = new SequenceInputStream(f1,f2);
        int c;
        while((c = sis.read()) != -1) {
            f3.write(c);
        }
        f3.close();f1.close();f2.close();
    }
}
```

**执行：** `java SequenceInputStreamTest A.txt B.txt C.txt`

### PrintStream

它是一个字节流类，继承自 `FilterOutputStream`。`PrintStream` 为另一个输出流增加了功能，即方便地打印各种数据值表示的能力。



可选地，可以创建一个 `PrintStream` 以便自动刷新（flush）；这意味着在写入字节数组、调用其中一个 `println` 方法或写入换行符或字节 `('\n')` 后，会自动调用 `flush` 方法。

`PrintStream` 打印的所有字符都将使用平台的默认字符编码转换为字节，然后写入构造函数中指定的 `OutputStream` 或 `File`。

### 构造函数

- `PrintStream(File file)`：使用指定的文件创建一个新的打印流，且不进行自动行刷新。
- `PrintStream(String fileName)`：使用指定的文件名创建一个新的打印流，且不进行自动行刷新。
- `PrintStream(OutputStream out)`：连接到指定的 `OutputStream` 创建一个新的打印流。
- `PrintStream(OutputStream out, boolean autoFlush)`：连接到指定的 `OutputStream` 创建一个新的打印流。

### 示例 15.4

```java
import java.io.*;
class PrintStream {
    public static void main(String args[]) throws IOException {
        PrintStream ps = new PrintStream(System.out, true);
        ps.println("This is a string");
        int i = -7;
        ps.println(i);
        double d = 4.5e-7;
        ps.println(d);
    }
}
```

**输出：**

```
This is a string
-7
4.5E-7
```

### 示例 15.15

```java
import java.io.*;
class PrintStreamTest2 {
    public static void main (String argv[]) throws IOException {
        FileOutputStream fout = new FileOutputStream("test.dat");
        PrintStream ps = new PrintStream(fout, true);
        ps.println("This is a string");
        int i = -7;
        ps.println(i);
        double d = 4.5e-7;
        ps.println(d);
    }
}
```

## PrintWriter 构造函数

创建一个新的 `PrintWriter`，不自动刷新行缓冲区，用于写入指定的 `OutputStream`。

`PrintWriter(OutputStream out, boolean autoFlush)`

创建一个新的 `PrintWriter`，用于写入指定的 `OutputStream`。

`PrintWriter(Writer out)`

创建一个新的 `PrintWriter`，不自动刷新行缓冲区，用于写入指定的 `Writer`。

`PrintWriter(Writer out, Boolean autoFlush)`

创建一个新的 `PrintWriter`，用于写入指定的 `Writer`。

## 用法与方法

最常用的构造函数是：

`PrintWriter(OutputStream os, boolean flushOnNewLine)` （等待，通常为 `autoFlush`）

在这里，`os` 是一个 `OutputStream` 类型的对象，而 `flushOnNewLine` 控制 Java 是否在每次调用 `println()` 方法时刷新输出流。如果 `flushOnNewLine` 为 `true`，则会自动进行刷新。如果为 `false`，则不进行自动刷新。

`PrintWriter` 支持对所有类型（包括对象在内的所有类型）的 `print()` 和 `println()` 方法。如果参数不是简单类型，`PrintWriter` 方法将调用对象的 `toString()` 方法并打印结果。

要使用 `PrintWriter` 写入控制台，请为输出流指定 `System.out` 并在新行后刷新流。例如，此行代码创建了一个连接到控制台输出的 `PrintWriter`。

`PrintWriter pw = new PrintWriter(System.out, true)`

### 示例 15.16

```java
import java.io.*;
class PrintWriterTest {
    public static void main (String argv[]) throws IOException {
        PrintWriter pw = new PrintWriter(System.out, true);
        pw.println("This is a string");
        int i = -7;
        pw.println(i);
        double d = 4.5e-7;
        pw.println(d);
    }
}
```

**输出：**

```
This is a string
-7
4.5E-7
```

### 示例 15.17

```java
import java.io.*;
class PrintWriterTest1 {
    public static void main (String argv[]) throws IOException {
        FileWriter fout = new FileWriter("test.dat");
        PrintWriter pw = new PrintWriter(fout, true);
        pw.println("This is a string");
        int i = -7;
        pw.println(i);
        double d = 4.5e-7;
        pw.println(d);
    }
}
```

### 示例 15.18

```java
import java.io.*;
class PrintWriterTest2 {
    public static void main (String argv[]) throws IOException {
        PrintWriter pw = new PrintWriter("test.dat");
        pw.println("This is a string");
        int i = -7;
        pw.println(i);
        double d = 4.5e-7;
        pw.println(d);
        pw.close();
    }
}
```

## 管道输入流 (PipedInputStream) 和 管道输出流 (PipedOutputStream)

管道输出流可以连接到管道输入流，以创建一个通信管道。管道输出流是管道的发送端。管道输入流应该连接到一个管道输出流；随后管道输入流将提供写入管道输出流的任何字节。

通常，数据由一个线程从 `PipedInputStream` 对象中读取，并由另一个线程写入相应的 `PipedOutputStream`。不建议在单个线程中使用这两个对象，因为可能会导致线程死锁。管道输入流包含一个缓冲区，在限制范围内将读操作与写操作解耦。

### 构造函数

- `PipedInputStream()`：创建一个 `PipedInputStream`，使其尚未连接。
- `PipedInputStream(PipedInputStream src)`：创建一个 `PipedInputStream`，使其连接到输出流 `src`。
- `PipedOutputStream()`：创建一个 `PipedOutputStream`，其尚未连接到管道输入流。
- `PipedOutputStream(PipedInputStream snc)`：创建一个连接到指定管道输入流的 `PipedOutputStream`。

### 示例 15.19

```java
import java.io.*;
class TextGenerator extends Thread {
    OutputStream out;
    TextGenerator(OutputStream out) {
        this.out = out;
    }
    public void run() {
        try {
            for(byte b = 65; b<=90; b++) {
                out.write(b);
            }
        } finally {
            out.close();
        } catch (IOException e) {
            System.out.println(e);
        }
    }
}
class Pipe {
    public static void main(String args[]) throws IOException {
        PipedOutputStream out = new PipedOutputStream();
        PipedInputStream in = new PipedInputStream(out);
        TextGenerator data = new TextGenerator(out);
        data.start();
        int ch;
        while((ch = in.read()) != -1) {
            System.out.print((char) ch);
        }
    }
}
```

**输出：**

```
ABCDEFGHIJKLMNOP
```

## 管道读取器 (PipedReader) 和 管道写入器 (PipedWriter)

它们的功能与 `PipedInputStream` 和 `PipedOutputStream` 相同，区别在于它们是字符流。

### 构造函数

- `PipedReader()`：创建一个 `PipedReader`，使其尚未连接。
- `PipedReader(PipedWriter src)`：创建一个 `PipedReader`，使其连接到管道写入器 `src`。
- `PipedWriter()`：创建一个 `PipedWriter`，其尚未连接到管道读取器。
- `PipedWriter(PipedReader snk)`：创建一个连接到指定管道读取器的 `PipedWriter`。

### 示例 15.20

```java
import java.io.*;
class TextGenerator extends Thread {
    Writer out;
    TextGenerator(Writer out) {
        this.out = out;
    }
    public void run() {
        try {
            try {
                for(char c = 'a'; c<='z'; c++)
                    out.write(c);
            }
            finally {
                try {
                    Thread.sleep(2000);
                } catch(Exception e) {}
                System.out.println("aaaaaaaaaaaaa");
                if(true) {
                    return; // IOException: pipe
                    out.close(); //IOException: Write end
                } //OK thread after closing the pipe
            }
        } catch(IOException e) { System.out.println(e);}
    }
}
class Pipe2 {
    public static void main (String argv[]) throws IOException {
        PrintStream ps = new PrintStream(System.out);
        PipedWriter out = new PipedWriter();
        PipedReader in = new PipedReader(out);
        TextGenerator data = new TextGenerator(out);
        data.start();
        int ch;
        while((ch = in.read()) != -1) {
            System.out.print((char) ch);
        }
    }
}
```

**输出：**

```
abcdefghijklmnopqrstuvwxyzaaaaaaaaaaa

Exception in thread "main" java.io.IOException: Pipe broken at java.io.PipedReader.read(Unknown Source) at Pipe2.main(Pipe2.java:43)
```

## 过滤字节流 (Filtered Byte Streams)

过滤流仅仅是输入流或输出流的包装器，能够透明地提供某些扩展功能。常见的扩展包括缓冲、压缩/解压缩等。过滤字节流是 `FilterInputStream` 和 `FilterOutputStream`。它们的构造函数如下：

- `FilterInputStream(InputStream in)`：通过将参数 `in` 赋值给字段 `this.in` 来创建一个 `FilterInputStream`，以便稍后使用。
- `FilterOutputStream(OutputStream out)`：创建一个构建指定的输出流之上的输出过滤器。

这些类中提供的方法与 `InputStream` 和 `OutputStream` 中的方法相同。

## 缓冲字节流 (Buffered Byte Streams)

对于面向字节的流，缓冲流通过在 I/O 流上附加内存缓冲区来扩展过滤流类。该缓冲区允许 Java 一次执行多一个字节的 I/O 操作，从而提高性能。由于缓冲区的存在，流的跳过（skip）和重置（reset）变得可能。缓冲流类是 `BufferedInputStream` 和 `BufferedOutputStream`。`PushbackInputStream` 也实现了缓冲流。

### BufferedInputStream

缓冲 I/O 是非常常见的性能优化。Java 的 `BufferedInputStream` 类允许你将任何 `InputStream` “包装”成缓冲流并实现这种性能。`BufferedInputStream` 有两个构造函数：

- `BufferedInputStream(InputStream in)`：创建一个 `BufferedInputStream` 并保存参数 `in` 以供以后使用。会创建一个内部缓冲区数组并存储在 `buf` 中。
- `BufferedInputStream(InputStream in, int size)`：创建一个具有指定缓冲区大小的 `InputStream` 并保存参数 `in` 以供以后使用。

缓冲输入流还提供了在可用缓冲区中向后移动所需的基础。除了任何 `InputStream` 实现的 `read()` 和 `skip()` 方法外，`BufferedInputStream` 还支持 `mark()` 和 `reset()` 方法。这种支持通过 `BufferedInputStream.markSupported()` 返回 `true` 来体现。

### 示例 15.21



```java
import java.io.*;
class BufferedInputStreamTest
{
    public static void main(String args[])throws IOException
    {
        FileInputStream fin=new FileInputStream("A.txt");
        BufferedInputStream b1 = new BufferedInputStream(fin);
        for(int i=1;i<=10;i++) {
            System.out.print((char)b1.read());
        }
        System.out.println();
        if(b1.markSupported()) {
            b1.mark(500);
            for(int i=1;i<=10;i++) {
                System.out.print((char)b1.read());
            }
            System.out.println();
            b1.reset();
            for(int i=1;i<=10;i++) {
                System.out.print((char)b1.read());
            }
        }
        else
            System.out.println("Marking option is not availabel");
        b1.close();
        fin.close();
    }
}
```

输出:

matrix Research And eearch And

**注意：**

`mark(32)` 为下次读取的 32 个字节保留标记（这对于所有实体引用都足够）。`mark` 的使用被限制在缓冲区内的访问。这意味着你只能为 `mark()` 指定一个小于流缓冲区大小的参数。

## BufferedOutputStream

与缓冲输入不同，缓冲输出不提供额外的功能。它仅用于提高性能。

以下是两个可用的构造函数：

`BufferedOutputStream(OutputStream out)`

### 构造函数

`BufferedOutputStream(OutputStream out, int size)`

创建一个新的缓冲输出流，使用指定的缓冲区大小将数据写入指定的底层输出流。

### 示例 15.22

```java
import java.io.*;

class BufferedOutputStreamTest {
    public static void main(String args[]) throws IOException {
        BufferedOutputStream f = new BufferedOutputStream(System.out, 100);
        byte buf[] = "This will not be displayed without flush()\n".getBytes();
        f.write(buf);
        f.write(buf);
        System.out.println("testing...");
        f.write(buf);
        //f.flush(); or
        //f.close();
    }
}
```

**输出：**

```
testing...
This will not be displayed without flush()
This will not be displayed without flush()
This will not be displayed without flush()
```

## BufferedReader

`BufferedReader` 通过缓冲输入来提高性能。它有两个构造函数：

### 构造函数

`BufferedReader(Reader in)`

创建一个使用默认大小输入缓冲区的缓冲化字符输入流。

`BufferedReader(Reader in, int sz)`

创建一个使用指定大小输入缓冲区的缓冲化字符输入流。

### 示例 15.23

```java
import java.io.*;

class BufferedReaderTest {
    public static void main(String args[]) throws IOException {
        FileReader fr = new FileReader("A.txt");
        BufferedReader b1 = new BufferedReader(fr);
        for (int i = 1; i <= 10; i++) {
            System.out.print((char)b1.read());
        }
        System.out.println();
        if (b1.markSupported()) {
            b1.mark(5);
            for (int i = 1; i <= 10; i++) {
                System.out.print((char)b1.read());
            }
            System.out.println();
            b1.reset();
            for (int i = 1; i <= 10; i++) {
                System.out.print((char)b1.read());
            }
        } else {
            System.out.println("Mark option is not available");
        }
        b1.close();
        fr.close();
    }
}
```

## BufferedWriter

使用 `BufferedWriter` 通过减少数据实际写入输出流的次数来提高性能。

### 构造函数

`BufferedWriter(Writer out)`

创建一个使用默认大小输出缓冲区的缓冲化字符输出流。

`BufferedWriter(Writer out, int sz)`

创建一个使用指定大小输出缓冲区的缓冲化字符输出流。

### 示例 15.24

```java
import java.io.*;

class Test {
    public static void main(String args[]) throws IOException {
        BufferedWriter f = new BufferedWriter(new PrintWriter(System.out));
        String s = "This will not be displayed without flush()\n";
        char buf[] = new char[s.length()];
        s.getChars(0, s.length(), buf, 0);
        f.write(buf);
        f.write(buf);
        System.out.println("testing...");
        f.write(buf);
        //f.flush();
        //f.close();
    }
}
```

**输出：**

```
testing...
```

# 使用字节流处理基本数据类型

基础输入和输出流提供的 `read/write` 方法只能用于读取/写入字节或字符。如果我们想读取/写入整数和双精度浮点数等基本类型，可以使用过滤器类作为现有输入输出流包装器，对原始流中的数据进行过滤。

用于创建处理基本数据类型的“数据流”的过滤器类是 `DataInputStream` 和 `DataOutputStream`。这些类使用了所示的多重继承概念，并实现了父类和接口中包含的所有方法。

从文件输入的数据流可以如下创建：

```java
FileInputStream fis = new FileInputStream(infile);
DataInputStream dis = new DataInputStream(fis);
```

这些语句基本上包装了 `fis` 并将其作为“过滤器”。同样，以下语句创建输出流 `dos` 并将其封装在输出文件中：

```java
FileOutputStream fos = new FileOutputStream(outfile);
DataOutputStream dos = new DataOutputStream(fos);
```

### 示例 15.25

下面的程序演示了基本数据的读取和写入。

```java
import java.io.*;

class ReadWritePrimitive {
    public static void main(String args[]) throws IOException {
        File primitive = new File("prim.dat");
        FileOutputStream fos = new FileOutputStream(primitive);
        DataOutputStream dos = new DataOutputStream(fos);
        dos.writeInt(1999);
        dos.writeDouble(2.4);
        dos.writeBoolean(false);
        dos.write('X');
        dos.close();
        fos.close();

        FileInputStream fis = new FileInputStream(primitive);
        DataInputStream dis = new DataInputStream(fis);
        System.out.println(dis.readInt());
        System.out.println(dis.readDouble());
        System.out.println(dis.readBoolean());
        System.out.println(dis.readChar());
        fis.close();
    }
}
```

**输出：**

```
1999
2.4
false
X
```

## 预定义流

`System` 类包含了三个定义的流变量：`in`、`out` 和 `err`。这些字段在 `System` 类中被声明为 `public` 且 `static`。这意味着程序的任何部分都可以使用它们，无需引用特定对象。

`System.out` 指向标准输出流。默认情况下是控制台。`System.out` 是一个 `PrintStream` 类型的对象。

`System.in` 指向标准输入，默认是键盘。`System.in` 是一个 `InputStream` 类型的对象。

`System.err` 指向标准错误流，默认情况下也是控制台。`System.err` 是一个 `PrintStream` 类型的对象。

这些都是字节流，尽管它们通常用于在控制台上读写字符。如果需要，你可以将它们封装在基于字符的流中。

### InputStreamReader

`InputStreamReader` 是从字节流到字符流的桥梁；它读取字节并使用指定的 `charset` 将其解码为字符。它使用的 `charset` 可以显式指定，也可以接受平台的默认字符集。

### 构造函数

- `InputStreamReader(InputStream in)`：创建一个使用默认字符集的 `InputStreamReader`。
- `InputStreamReader(InputStream in, String charsetName)`：创建一个使用指定名称的 `charset` 的 `InputStreamReader`。

### 示例 15.26

```java
import java.io.*;
class InputStreamReaderTest {
    public static void main (String argv[]) throws IOException {
        char c;
        InputStreamReader is = new InputStreamReader(System.in);
        System.out.println("Enter characters, 'q' to quit");
        c = (char)is.read();
        while(c!='q') {
            System.out.print(c);
            c = (char)is.read();
        }
    }
}
```

**输出：**

```
Enter characters, 'q' to quit
abcd
q
```

### 示例 15.27

对上一个示例进行修改，使用缓冲来提高性能。

```java
import java.io.*;
class BufferedReaderTest {
    public static void main (String args[]) throws IOException {
        char c;
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        System.out.println("Enter characters, 'q' to quit");
        c = (char)br.read();
        while(c!='q') {
            System.out.print(c);
            c = (char)br.read();
        }
    }
}
```

**输出：**

```
Enter characters, 'q' to quit
abcd
q
```

### 示例 15.28

`InputStreamReader` 没有提供 `readLine()` 方法，因此 `InputStreamReader` 通常链接到提供 `readLine()` 方法的 `BufferedReader`。

```java
import java.io.*;
class BufferedReaderTest {
    public static void main (String argv[]) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        System.out.println("Enter 'stop' to quit");
        String str = br.readLine();
        while(!str.equals("stop")) {
            System.out.println("Your Name:"+str);
            str = br.readLine();
        }
    }
}
```

**输出：**

```
Enter 'stop' to quit
Harry Feat
Your Name:Feat
```

### 示例 15.29

此示例演示了我们可以直接从 `System.in` 读取。

```java
import java.io.*;
class ReadFromConsole {
    public static void main (String arg[]) throws IOException {
        char c;
        System.out.println("Enter characters, 'q' to quit");
        c = (char) System.in.read();
        while(c!='q') {
            System.out.print(c);
            c = (char) System.in.read();
        }
    }
}
```

**输出：**

```
Enter characters, 'q' to quit
abcd
abcdq
```

### OutputStreamWriter

`OutputStreamWriter` 是从字符流到字节流的桥梁：写入它的字符将使用指定的 `charset` 编码为字节。它使用的 `charset` 可以显式指定，也可以接受平台的默认字符集。

### 构造函数

- `OutputStreamWriter(OutputStream out)`：创建一个使用默认编码的 `OutputStreamWriter`。



- `OutputStreamWriter(OutputStream out, String charsetName)`：创建一个使用指定名称的 `charset` 的 `OutputStreamWriter`。

### 读取输入

在 Java 中，执行控制台输入的唯一方法是使用字节流，使用这种方法的旧代码仍然存在。今天，控制台输入通过封装 `System.in` 实现，该对象可以进一步封装在 `BufferedReader` 对象中以提高性能。

## 输出控制台输出

控制台输出最简单的方法是使用 `print()` 和 `println()`。这些方法由 `PrintStream` 类定义（`System.out` 所引用对象的类型）。尽管 `System.out` 是一个字节流，但将它用于简单的程序输出仍然是可以的。

然而，基于字符的替代方案是正确的选择。因为 `PrintStream` 是一个派自 `OutputStream` 的输出流，它还实现了低级方法 `write()`。因此，可以使用 `write()` 向控制台写入内容。

### 示例 15.30

```java
import java.io.*;
class WriteTest {
}
```

```java
public static void main(String argv[]) throws IOException {
    int b;
    b = 'A';
    System.out.write(b);
    // System.out.flush();to flush
    System.out.write('\n');//to flush
}
```

Output:

A

### 注意：

你通常不会使用 `write()` 来执行控制台输出，因为 `print()` 和 `println()` 使用起来简单得多。

## 序列化

序列化（Serialization）是将对象的状态写入字节流的过程。当你想要将对象的状态存储到字节流时，这种方法非常有用。当你想要将程序的状态保存到持久化存储区域（如文件）时，这同样有用。在以后的时候，你可以通过反序列化过程来恢复这些对象。

实现 RMI（远程方法调用）也需要序列化。RMI 允许一台机器上的 Java 对象调用另一机器上 Java 对象的方法。对象可以作为远程方法的参数传递。发送端将对象序列化并转换，接收端则对其进行反序列化。

如果你尝试序列化对象图顶部的对象，所有其他引用的对象都会被递归地找到并序列化。

同样，在反序列化过程中，所有这些对象及其引用都会被正确存储。声明为 `transient` 或 `static` 的变量不会被序列化机制保存。

## Externalizable 接口（外部化接口）

Java 的序列化和反序列化机制使得保存和恢复对象状态的大部分工作自动完成。

然而，在某些情况下，程序员可能需要对这些过程进行控制。例如，使用压缩或加密技术。`Externalizable` 接口就是为了这些情况设计的。实现了 `Externalizable` 接口的类也可以被序列化和反序列化。

但控制权在用户手中，可以决定序列化和反序列化哪些部分。序列化代码写在 `writeExternal()` 方法中，反序列化代码写在 `readExternal()` 方法中。

### 方法：

`void readExternal(ObjectInput in)`

对象实现 `readExternal` 方法，通过调用 `DataInput` 的方法处理原始类型，通过调用 `readObject` 处理对象、字符串和数组来恢复其内容。

`void writeExternal(ObjectOutput out)`

对象实现 `writeExternal` 方法，通过调用 `DataOutput` 的方法处理其原始值，或调用 `ObjectOutput` 的 `writeObject` 方法处理对象、字符串和数组来保存其内容。

### ObjectOutput 接口

`ObjectOutput` 接口扩展了 `DataOutput` 接口并支持对象序列化。除了 `DataOutput` 接口定义的方法外，`ObjectOutput` 接口只定义了：

`Void writeObject(Object object)`

用于序列化对象。`ObjectOutput` 接口的所有方法在错误条件下均会抛出 `IOException`。

### ObjectOutputStream

`ObjectOutputStream` 类扩展了 `OutputStream` 类并实现了 `ObjectOutput` 接口。它负责将对象写入流。

- **构造函数**：`ObjectOutputStream(OutputStream out)` - 创建一个写入指定 `OutputStream` 的 `ObjectOutputStream`。参数 `out` 是序列化对象将要写入的输出流。

- **写入方法**：`void writeObject(Object obj)` - 将对象写入底层存储或流。

### ObjectInput 接口

`ObjectInput` 接口扩展了 `DataInput` 接口。支持对象序列化。除了 `DataInput` 接口定义的方法外，`ObjectInput` 只定义了一个方法：

`Object readObject()` 用于反序列化对象。

### ObjectInputStream

`ObjectInputStream` 类扩展了 `InputStream` 类并实现了 `ObjectInput` 接口。它负责从流中读取对象。

- **构造函数**：`ObjectInputStream(InputStream in)` - 创建一个从指定 `InputStream` 读取的 `ObjectInputStream`。参数 `in` 是从中读取序列化对象的输入流。

- **反序列化方法**：`readObject()` 从 `ObjectInputStream` 读取对象。

### 示例 5.3

```java
import java.io.*;
class SerializationTest {
    public static void main(String args[]) throws IOException {
        try {
            MyClass object1 = new MyClass("Hello", 123, 1.33);
            MyClass object2 = new MyClass("Hello1", 1, 2);
            System.out.println(object1);
            System.out.println(object2);
            FileOutputStream fos = new FileOutputStream("serial.dat");
            ObjectOutputStream oos = new ObjectOutputStream(fos);
            oos.writeObject(object1);
            oos.writeObject(object2);
            oos.flush();
            oos.close();
        } catch (Exception e) {
            System.out.println(e);
        }
        try {
            MyClass object3, object4;
            FileInputStream fis = new FileInputStream("serial.dat");
            ObjectInputStream ois = new ObjectInputStream(fis);
            object3 = (MyClass)ois.readObject();
            object4 = (MyClass)ois.readObject();
            ois.close();
            System.out.println("After deserialization");
            System.out.println(object3);
            System.out.println(object4);
        } catch (Exception e) {
            System.out.println(e);
        }
    }
}

class MyClass implements Serializable {
    String s;
    int i = 100;
    double d;
    MyClass(String s, int i, double d) {
        this.s = s;
        this.i = i;
        this.d = d;
    }
    public String toString() {
        return "s = "+ s +"; i = "+ i + " ; d = " +d;
    }
}
```

### 输出

```
s = Hello; i = 123 ; d = 1300.0
s = Hello1; i = 1 ; d = 2.0
```

### 反序列化后

```
s = Hello; i = 123 ; d = 1300.0
s = Hello1; i = 1 ; d = 2.0
```

注意：我们可以在一个文件中保存多个相同类型的对象，也可以在同一个文件中保存不同类型的对象。

### 示例 15.32

此示例演示了 `transient` 和 `static` 变量在序列化过程中不会被持久化。

```java
import java.io.*;

class SerializationTest2 {
    public static void main (String args[]) throws IOException {
        try {
            MyClass object1 = new MyClass("Hello", 123, 1.3e3);
            MyClass object3 = new MyClass("Hello1", 1, 2);
            object3.x = 200;
            A object5 = new A();
            System.out.println(object1);
            System.out.println(object3);
            System.out.println(object5);
            FileOutputStream fos = new FileOutputStream("serial.dat");
            ObjectOutputStream oos = new ObjectOutputStream(fos);
            oos.writeObject(object1);
            oos.writeObject(object3);
            oos.writeObject(object5);
            object3.x = 400;
            oos.flush();
            oos.close();
        } catch (Exception e) {
            System.out.println(e);
        }
        try {
            MyClass object2;
            A object6;
            FileInputStream fis = new FileInputStream("serial.dat");
            ObjectInputStream ois = new ObjectInputStream(fis);
            object2 = (MyClass) ois.readObject();
            object4 = (MyClass) ois.readObject();
            object6 = (A) ois.readObject();
            ois.close();
            fis.close();
            System.out.println("After deserialization");
            System.out.println(object2);
            System.out.println(object4);
            System.out.println(object6);
        } catch (Exception e) {
            System.out.println(e);
        }
    }
}

class MyClass implements Serializable {
    String s;
    transient int i=100;
    public static int x = 10;
    double d;
    MyClass(String s, int i, double d) {
        this.s = s;
        this.i = i;
        this.d = d;
        x = 10;
    }
    public String toString() {
        return "s = " + s + "; i = " + i + " ;d = " + d + x = " + x;
    }
}

class A implements Serializable {
    public String toString() {
        return "Class A";
    }
}
```

### 示例 15.33

使用 Externalizable

```java
import java.io.*;

class SerializationTest1 {
    public static void main (String args[]) throws IOException {
        try {
            MyClass object1 = new MyClass("Hello", 9, 23.5);
            System.out.println(object1);
            FileOutputStream fos = new FileOutputStream("serial.dat");
            ObjectOutputStream oos = new ObjectOutputStream(fos);
            System.out.println("before writing");
            oos.writeObject(object1);
            System.out.println("after writing");
            oos.flush();
            oos.close();
        } catch (Exception e) {
            System.out.println(e);
        }
        try {
            MyClass object2;
            FileInputStream fis = new FileInputStream("serial.dat");
            ObjectInputStream ois = new ObjectInputStream(fis);
            System.out.println("before reading");
            object2 = (MyClass) ois.readObject();
            System.out.println("after reading");
            ois.close();
            System.out.println(object2);
        } catch (Exception e) {
            System.out.println(e);
        }
    }
}

class MyClass implements Serializable {
    String s;
```



```java
int i = 100;
double d;
public MyClass() {}; // 必须的
public MyClass(String s, int i, double d) {
    this.s = s;
    this.i = i;
    this.d = d;
}
public String toString() {
    return "s = " + s + "; i = " + i + " ;d = " + d;
}
public void writeExternal(ObjectOutput oos) throws IOException {
    System.out.println("Inside writeExternal");
    oos.writeObject(s);
    oos.writeInt(i);
    oos.writeDouble(d);
}
public void readExternal(ObjectInput ois) throws ClassNotFoundException, IOException {
    System.out.println("Inside readExternal");
    s = (String) ois.readObject();
    i = ois.readInt();
    d = ois.readDouble();
}
```

**输出：**

```text
s = Hello; i = 99 ;d = 123.45
```

**注意：**

在反序列化期间，对象将使用默认构造函数进行构造（与 `serializable` 接口不同），然后进行初始化。任何状态必须在 `writeExternal()` 中显式保存。

# 第 16 章 Applet

## 简介

Applet 是一种设计用于在互联网传输并通过像 Internet Explorer 或 Netscape Navigator 等 Java Web 浏览器在客户端机器上执行的应用。Applet 也是 Java 程序，但它们存在于服务器上。

Applet 不能像独立应用程序那样执行。Applet 只能通过嵌入 HTML 页面（类似于图像或声音文件）来执行。要运行 applet，我们需要访问嵌入了 applet 的 HTML 页面。当浏览器下载此类 HTML 页面时，它随后会加载包含 applet 代码的可执行文件，然后在本地机器上执行它。

当 applet 到达客户端后，它对资源的访问受到限制，这样它可以产生任意的媒体界面并运行复杂的计算，而不会引入病毒风险或破坏数据完整性。

## 架构

Applet 与普通的 Java 程序不同：

* Applet 是基于 GUI（基于窗口）的程序
* Applet 是事件驱动的

当一个普通的 Java 程序（非基于 GUI 的）需要输入时，它会提示用户然后调用某些输入方法，如 `readLine()`，即交互是由程序发起的。这并不是基于 GUI 程序的行为。是由用户发起与程序的交互，而不是由程序发起动作。例如，在文字处理软件中，用户通过点击不同的按钮来发起动作，从而产生事件，结果执行某些代码，并相应发生动作。

Applet 使用 `awt` 包（抽象窗口工具包）来提供 GUI 和处理事件。之所以被称为 `awt`，因为它完全依赖于底层操作系统的功能。Applet 类似于一组中断服务程序。Applet 会等待直到事件发生。`awt` 通过调用 applet 提供的事件处理器来通知 applet 事件发生。一旦发生这种情况，applet 必须采取适当的行动，然后迅速将控制权交回 AWT。这是一个关键点。在大多数情况下，我们的 applet 不应该进入一种长时间保持控制的运行“模式”。相反，它必须在响应事件时执行特定操作，并将控制权交回 AWT 运行系统。在我们的 applet 需要独立执行重复任务的情况下（例如，在窗口中显示滚动消息），在这种情况下，我们必须启动一个额外的执行线程。

## 编写 Applet

所有的 applet 都是 `Applet` 类的子类。`Applet` 类位于 `java.applet` 包中。`Applet` 类的层级结构如下：

```
java.lang.Object
       |
  java.awt.Component
       |
  java.awt.Container
       |
  java.awt.Panel
       |
java.applet.Applet
```

`Applet` 类为 applet 执行提供了所有支持，例如启动和停止。它还提供了加载和显示图像的方法。它还为所有基于窗口的提供了必要的支持。我们扩展 applet 类的子类必须声明为 `public`，因为它是由 Web 浏览器实例化并执行的。浏览器在实例化 applet 时使用无参数构造函数，因此它必须提供具有 `public` 可见性的无参数构造函数。建议我们不要在 `Applet` 类中提供构造函数，因为在这种情况下编译器将提供默认的无参数构造函数。

我们可以利用 `init()` 方法进行初始化。在编写 applet 代码时，我们通常会重写 `Applet` 类的一些方法，这些方法在 applet 执行期间会被自动调用。重写 `paint()` 方法是常见的。`paint()` 方法中的代码主要在 Applet 窗口中显示输出。

**示例 16.1 (App1.java)** 以下程序演示了一个简单的 applet，它仅在窗口内显示“Hello World”。我们在 applet 的 `paint` 方法中绘制/显示任何内容，它都会出现在 applet 的窗口中。在下面的示例中，applet 窗口的背景颜色设置为红色，前景颜色设置为绿色，因此背景将显示为红色，文本“Hello Word”将以绿色显示。

```java
import java.awt.*;
import java.applet.Applet;
/*<applet code="App1" width=500 height=100></applet>*/
public class App1 extends Applet {
    public void init() {
        setBackground(Color.red);
        setForeground(Color.green);
    }
    public void paint(Graphics g) {
        g.drawString("Hello World", 20, 20);
    }
}
```

![](img/image01261.jpeg)

## 运行 Applet

Applet 不由基于控制台的 Java 运行时解释器执行。我们可以通过两种方式运行 applet：

1. 在兼容 Java 的 Web 浏览器中执行 applet。
2. 使用 `appletviewer`，例如标准 SDK 工具 `appletviewer`。`appletviewer` 会在一个窗口中运行我们的 applet。这是测试 applet 最快、最简单的方法。

### 在网页浏览器中执行 Applet

我们需要编写一个短的 HTML 文本文件，其中包含适当的 `<applet>` 标签。`<applet>` 标签必须包含三个属性：

* `code`
* `width`
* `height`

属性 `code` 的值指定包含 applet 代码的类名。属性 `width` 和 `height` 分别指定 applet 窗口的宽度和高度。

以下是嵌入了 applet "App1" 的 HTML 文件 `RunApp.Html`：

```html
<html>
<head>
<title>Simple Applet</title>
</head>
<body>
<h1>Simple “Hello World” Application </h1>
<applet code="App1" width=500 height=100>
</applet>
</body>
</html>
```

你可以通过在浏览器中打开 `RunApp.html` 文件来执行 applet。该文件可以位于本地文件系统上，也可以从 Web 服务器加载。

### 使用 appletviewer 执行 Applet

然而，存在一种更方便的方法可以用来加速测试。只需在你的 Java 源码文件中包含包含该 `<applet>` 标签的注释即可。通过这种方式，我们的代码包含了必要的 HTML 语句的原型作为文档，我们只需通过启动 `appletviewer` 并传入 Java 源码文件即可测试编译后的输出。如果我们使用这种方法，在编译后可以按照如下方式执行 applet：

```bash
appletviewer SimpleApplet.Java
```

# Applet 生命周期方法

Applet 重写了一组方法，这些方法提供了浏览器或 `appletviewer` 与 applet 交互并控制其执行的基本级机制。

这些方法也被称为生命周期方法，因为浏览器或 applet 查看器会在 applet 生命周期的不同阶段自动调用它们。总共有五个生命周期方法：

* `public void init()`
* `public void start()`
* `public void stop()`
* `public void destroy()`
* `public void paint(Graphics g)`

这五个方法中的四个：`init()`、`start()`、`stop()` 和 `destroy()` 是定义在 `applet` 类中的。

`paint()` 是由 `Component` 类定义的；它提供了所有这些方法的默认实现。Applet 不需要重写它们没有用到的方法。然而，非常简单的 applet 不需要定义它们。

## Applet 的初始化与终止

当 applet 开始运行时，会按顺序调用以下方法：

1. `init()`
2. `start()`
3. `paint()`

当 applet 终止时，会发生以下序列的调用：

4. `stop()`
5. `destroy()`

### `init()` 方法

这是第一个被调用的方法。在这里我们应该初始化变量并为其他初始化活动编写代码。该方法在 applet 生命周期内仅被调用一次，紧接实例化之后。

### `start()` 方法

`start()` 方法在 `init()` 之后被调用。它还用于在 applet 停止后重新启动它。`init()` 在 applet 第一次加载时调用一次，而 `start()` 在每次 applet 的 HTML 文档显示在屏幕上时被调用。因此，如果用户离开网页后返回，`start()` 会被调用。

### `paint()` 方法

`paint()` 在 `init()` 和 `start()` 之后被调用，当 applet 开始执行。每当 applet 需要重绘时，`paint()` 方法都会被调用。这种情况可能由于多种原因发生：例如窗口被覆盖，或者 applet 窗口被最小化后恢复。

### `stop()` 方法

`stop()` 方法在浏览器离开包含 applet 的文档时被调用。当调用 `stop()` 时，applet 不可见。我们应该在 `stop()` 中暂停那些不需要运行的线程，当不可见。

### `destroy()` 方法

`destroy()` 方法在环境确定 applet 需要从内存中完全移除时被调用。此时，我们应该释放 applet 可能使用的资源。`stop()` 方法总是在 `destroy()` 之前调用。

**示例 1：** 一个背景颜色设置为青色、前景颜色设置为红色并显示消息的简单 applet，它展示了 `init()`、`start()` 和 `paint()` 方法在 applet 开始时的调用顺序。

```java
import java.awt.*;
import java.applet.*;
/*<applet code="App2" width=500 height=100></applet>*/
class App2 extends Applet {
    String msg = "";
    public void init() {
        System.out.println("Inside init");
        setBackground(Color.cyan);
        setForeground(Color.red);
        msg = "Inside init --";
    }
    public void start() {
        System.out.println("Inside start");
        msg += "start --";
    }
    public void stop() {
        System.out.println("Inside Stop");
        msg += "stop --";
    }
    public void paint(Graphics g) {
        System.out.println("Inside paint");
        msg += "Inside paint --";
        g.drawString(msg, 10, 30);
    }
    public void destroy() {
        System.out.println("Inside destroy");
    }
}
```

输出：

![](img/image01262.jpeg)

## 动态 Applet

Applet 窗口中显示的输出可以是动态的。例如，我们可以显示一个移动横幅。Applet 还可以用于诸如通过从服务器获取显示比分和其他统计数据；股票价格等应用程序。

**示例 1.3：** 以下示例展示了一个移动横幅。它使用 `repaint()` 方法来刷新显示。该 applet 在 applet 窗口上从右向左滚动消息。由于消息的滚动是一项重复任务，它由一个 applet 启动时创建的独立线程来执行。此程序还演示了可以在 `stop()` 方法中释放资源，并在 `start()` 方法中获取。

```java
import java.awt.*;
import java.applet.*;
/*<applet code="App3" width=500 height=100></applet>*/
class App3 extends Applet implements Runnable {
    String msg = "A Simple Moving Banner.";
    Thread t = null;
    boolean stopFlag;

    public void init() {
        setBackground(Color.cyan);
        setForeground(Color.red);
    }

    public void start() {
        t = new Thread(this);
        stopFlag = false;
        t.start();
    }

    public void stop() {
        stopFlag = true;
        t = null;
    }

    public void paint(Graphics g) {
        g.drawString(msg, 50, 30);
    }

    public void run() {
        for (;;) {
            repaint();
            try {
                Thread.sleep(50);
            } catch (InterruptedException e) {
                System.out.println(e);
            }
            msg = msg.substring(1) + msg.charAt(0);
            if (stopFlag)
                break;
        }
    }
}
```

![](img/image0263.jpeg)

## 使用状态窗口

除了在窗口中显示信息外，applet（小程序）还可以向运行它的浏览器状态窗口或 applet 状态窗口输出消息。要做到这一点，可以调用 `showStatus()` 并传递我们想要显示的字符串。状态窗口是向用户提供 applet 中正在发生的情况反馈、建议选项或报告某些类型错误的好地方。状态窗口是一个极佳的辅助，因为它为我们提供了输出关于 applet 信息的简单方法。

### 示例 1.4：以下演示了如何使用状态窗口

```java
import java.awt.*;
import java.applet.*;
/*<applet code="App4" width=500 height=100></applet>*/
public class App4 extends Applet {
    public void init() {
        setBackground(Color.cyan);
    }
    public void paint(Graphics g) {
        g.drawString("This is in the applet window", 10, 20);
        showStatus("This is shown in the status window");
    }
}
```

![](img/image01264.jpeg)

## HTML 的 APPLET 标签

`APPLET` 标签用于从 HTML 文档和 `appletviewer` 启动 applet。`appletviewer` 会在单独窗口中执行它找到的每个 `APPLET` 标签；而像 Netscape Navigator 和 Internet Explorer 这样的浏览器允许在单个页面上运行多个 applet。

标准 `APPLET` 标签的语法为：



```html
<APPLET
    CODE=applet class
    CODEBASE=codebase
    ALT=alternate
    NAME=appletinstance
    WIDTH=pixels
    HEIGHT=pixels
    ALIGN=alignment
    SPACE=vertical space in pixels
    HSPACE=horizontal space in pixels>
<PARAM NAME=attributeName-1 VALUE=Attribute Value-1>
<PARAM NAME=attributeName-2 VALUE=Attribute Value-2>
-------------
<PARAM NAME=attributeName-N VALUE=Attribute Value-N>
………在没有 Java 的情况下 HTML………
</APPLET>
```

- `CODE`: `CODE` 是一个性属性，提供包含我们 applet 编译类的文件名。该文件相对于 applet 的 `CODEBASE`，即 html 文件所在的目录，或者如果设置了 `CODEBASE` 则由该属性指定的目录。

- `CODEBASE`: `CODEBASE` 是一个可选属性，指定 applet 可执行类所在的基础 URL，即 `CODE` 标签所在的目录。如果未指定该属性，则使用 HTML 文档所在的目录。

- `ALT`: `ALT` 标签是一个可选属性，用于指定当浏览器不支持 applet 时应显示的短文本消息。这是为不支持 applet 的浏览器提供的替代 HTML。

- `NAME`: `NAME` 是一个可选属性，用于指定 applet 实例名称。applet 必须命名，以便页面上的其他 applet 通过名称找到它们并与之通信。要通过名称获取 applet，使用 `getApplet()`，它由 `AppletContext` 接口定义。

- `WIDTH` 和 `HEIGHT`: `WIDTH` 和 `HEIGHT` 是 applet 显示区域的像素大小。

- `ALIGN`: `ALIGN` 是一个指定 applet 对齐方式的属性。该属性的处理方式与 HTML `IMG` 标签相同，可能的值：LEFT, RIGHT, BOTTOM, MIDDLE, BASELINE, TEXTTOP, ABSMIDDLE 和 ABSBOTTOM。

- `SPACE` 和 `HSPACE`: 这些是可选属性，`SPACE` 指定 applet 上下的空间（像素）。`HSPACE` 指定 applet 左右的空间（像素）。它们的处理方式与 `IMG` 标签的 `SPACE` 和 `HSPACE` 属性相同。

### PARAM 标签

`PARAM` 标签允许我们在 HTML 页面中指定 applet 特定参数。applet 通过 `getParameter()` 方法访问这些属性。`PARAM` 标签有两个属性：`NAME` 和 `VALUE`。

#### 示例 16.5 此示例演示了如何从 HTML 页面向 Applet 传递参数

```java
import java.awt.*;
import java.applet.*;
/*<applet code="App5" width=500 height=100>
<param name="fontName" value="Arial">
<param name="fontSize" value="30">
</applet>*/
public class App5 extends Applet
{
    String fName;
    int fSize;
    public void init( )
    {
        fName = getParameter("fontName");
        if (fName == null)
            fName = "Courier";
        fSize = Integer.parseInt(getParameter("fontSize"));
        Font f1= new Font(fName, Font.PLAIN, fSize);
        setFont(f1);
    }
    public void paint (Graphics g)
    {
        g.drawString ("Font Name : " + fName, 0, 25 );
    }
}
```

```java
g.drawString ("Font Size : " + fSize, 0, 50 );
g.drawString ("Hello world", 0,75);
```

![](img/image01265.jpeg)

## 获取 DocumentBase 和 CodeBase

通常，我们会创建需要显式加载媒体和文本的 applet。Java 允许 applet 从启动 applet 的 HTML 文件所在的目录（文档基，document base）以及加载 applet 类文件的目录（代码基，code base）加载数据。

这些目录以 `URL` 对象的形式返回。它们可以与命名我们要加载的文件的字符串拼接。要实际加载另一个文件，我们将使用由 `AppletContext` 接口定义的 `showDocument()` 方法。

### 示例 16.6 以下示例演示了如何在 applet 代码中获取文档基和代码基

#### App6.java

```java
import java.awt.*;
import java.applet.*;
import java.net.URL;
public class App6 extends Applet
{
    public void paint (Graphics g)
    {
        URL u1 = getCodeBase( );
        g.drawString ("Code base:-" + u1, 10,20);
        URL u2 = getDocumentBase();
        g.drawString ("Document base:-"+u2, 0,0);
    }
}
```

#### App6.html

```html
<html>
<body>
<applet code="App6" width=500 height=200></applet>
</body>
</html>
```

输出：

### Context 和 Document

Java 的应用之一是使用活动图像和动画提供一种图形化的网页导航手段，这比超文本使用的下划线更有趣。为了允许我们的 applet 将控制权转移到另一个 `URL`，我们必须使用由 `AppletContext` 接口定义的 `showDocument()` 方法。

`AppletContext` 是允许我们从 applet 的执行中获取信息的接口。当前执行的 applet 的上下文通过调用 applet 类定义的 `getAppletContext()` 方法获取。在 applet 中，一旦我们获取了 applet 的上下文，就可以调用 `showDocument()` 方法将另一个文档引入视图。此方法没有返回值，并且在失败时不会抛出异常，因此请谨慎使用。有两个 `showDocument()` 方法：

- `void showDocument(URL url)`：将正在查看的网页替换为给定的 `URL`。

- `void showDocument (URL url, String where)`：在浏览器窗口内的指定位置显示文档。`where` 的有效参数有：

    - `"_self"`（在当前帧中显示）

    - `"_parent"`（在父帧中显示）

    - `"_top"`（在顶帧中显示），以及

    - `"_blank"`（在新浏览器窗口中显示）

### 示例 16.7 以下 applet 演示了 AppletContext 和 showDocument 的用法。执行时，它获取当前 applet 上下文并使用该上下文将控制权转移到名为 `A.html` 的文件。该文件必须与 applet 位于同一目录下。`Test.html` 可以包含你喜欢的任何有效超文本

```java
import java.awt.*;
import java.applet.*;
import java.net.*;
public class App7 extends Applet
{ 
    AppletContext ac;
    URL u1;
    public void init()
    {
        setBackground(Color.cyan);
    }
    public void start()
    {
        ac = getAppletContext();
        u1 = getCodeBase();
        try
        {
            Thread.sleep(300);
            ac.showDocument(new URL(u1 + "A.html"),"_blank");
        }
        catch(MalformedURLException e)
        {
            showStatus("Invalid URL");
            e.printStackTrace();
        }
        catch(InterruptedException e) 
        { 
            showStatus("Invalid URL");
            e.printStackTrace();
        }
    }
    public void paint (Graphics g)
    {
        g.drawString(u1+"A.html",20,20);
        try
        {
            Thread.sleep(300);
        }
        catch(InterruptedException e)
        {
            System.out.println(e);
        }
    }
}
```

#### App7.html

```html
<html>
<head>
<Title>AppletContext</Title>
</head>
<body>
<applet code="App7" width=200 height=200></applet>
</body>
</html>
```

#### A.html

```html
<html>
<head>
<title>New Page</title>
</head>
<body bgcolor=blue text=red>
<h1>matrix</h1>
</body>
</html>
```

### 示例 16.8

```java
import java.applet.*;
import java.awt.*;
import java.awt.event.*;
/*<Applet code="CopyApp" width=500 height=200></applet>*/
public class CopyApp extends Applet implements ActionListener
{
    TextField tf1,tf2;
    Button b1;
    public void init()
    {
        setForeground(Color.red);
        Font f1=new Font("Arial", Font.BOLD+Font.ITALIC,20);
        tf1=new TextField();
        tf2=new TextField();
        tf1.setFont(f1);
        tf2.setFont(f1);
        b1=new Button("Copy");
        b1.addActionListener(this);
        b1.setFont(f1);
        add(tf1);
        add(tf2);
        add(b1);
    }
    public void paint(Graphics g)
    {
        g.drawString("Matrix",0,150);
    }
    public void actionPerformed(ActionEvent ae)
    {
        String s1=tf1.getText();
        tf2.setText(s1);
    }
}
```

![](img/image01266.jpeg)

## 16.9 使用 Applet 计算两个数字之和

```java
import java.applet.*;
import java.awt.*;
import java.awt.event.*;
/*<applet code = "SumApplet" width=400 height=400></applet>  */
public class SumApplet extends Applet implements ActionListener
{
    TextField tf1,tf2,tf3;
    Label l1,l2,l3;
    Button b1;
    public void init()
    {
        setLayout(new GridLayout(4,2));
        l1 = new Label("No. 1");
        l2 = new Label("No. 2");
        l3 = new Label("Result");
        tf1 = new TextField(8);
        tf2 = new TextField(8);
        tf3 = new TextField(8);
        b1 = new Button("Sum");
        b1.addActionListener(this);
        add(l1);add(tf1);
        add(l2);add(tf2);
        add(l3);add(tf3);
        add(b1);
    }
    public void actionPerformed(ActionEvent ae)
    {
        Button abc = (Button)ae.getSource();
        if(abc == b1)
        {
            int a,b,c;
            a = Integer.parseInt(tf1.getText());
            b = Integer.parseInt(tf2.getText());
            c = a + b;
            tf3.setText(String.valueOf(c));
        }
    }
}
```

# 第 17 章：抽象窗口工具包 (AWT)

### 引言

Java 提供了大量的内置类，帮助我们设计图形用户界面（GUI）。这些类大部分属于 `java.awt` 包，并统称为抽象窗口工具包（AWT）。

我们对 `MS-WORD`、`MS-EXCEL` 等软件非常熟悉。所有这些软件都有 GUI，即当我们运行这些软件时，可以看到图形用户界面。我们通过键盘或鼠标选择不同的选项来访问这些软件的各种功能。显示用户界面需要大量的编程工作。

AWT 中帮助设计图形用户界面的三个重要部分是：

* 组件（Components）
* 容器（Containers）
* 布局管理器（Layout Managers）

以上所有内容在设计 GUI 中都起着重要作用。

### 组件

组件是 Java 创建 GUI 的构建块。组件是一个具有图形表示的对象，它可以显示在屏幕上并与用户交互。组件的示例包括典型图形用户界面中的按钮、复选框和滚动条。`java.awt.Component` 类是非菜单相关 AWT 组件的抽象父类。`Component` 类也可以被直接扩展以创建轻量级组件。轻量级组件是不与原生不透明窗口相关的组件。

某些组件类型（如按钮和滚动条）直接用于 GUI 控制。其他类型的组件（继承自 `Container` 类的）提供了特殊的组织方式。而像 `TextField`、`TextArea`、`List` 等组件用于接受用户输入。`Label` 是一种不同类型的组件，其目的仅仅是显示适当标签以识别其他组件。

Java 的组件通过 `java.awt.Component` 和 `java.awt.Menu` 组件父类的许多子类来实现。组织这些大量类的一种方法是将它们分为几类：

* 可视组件
* 容器组件
* 菜单组件

### 组件层次结构

下图显示了 AWT 的组件层次结构。

![](img/image01267.jpeg)

### 容器

下图描述了容器的层次结构。

![](img/image01268.jpeg)

所有基于窗口应用程序都始于屏幕上可见的顶层窗口。同样，所有基于 GUI 的 Java 应用程序也从顶层窗口开始，在 Java 术语中被称为顶层容器（top-level container）。

容器也是 Java 组件，可以包含其他组件。组件只有通过将其添加到容器或将其放入容器内部，才能变得可见。

所有的 Java GUI 都存在于 `Applet` 或 `Frame` 中。`Applet` 和 `Frame` 是 Java 中的两个顶层容器。



在 Java 中可以使用绝对定位，但并不建议这样做。`AWT` 设计初衷是使用相对定位。我们可以通过相对规范来指定组件布局，例如：组件将添加到上一个组件的右侧、组件将添加到某个其他组件的下方、组件将出现在顶部、组件的大小将设为容器宽度的 `1/4` 等。即使在不知道组件尺寸的情况下，这些规范也是非常有用的。

Java 鼓励使用相对定位，因为它是平台无关的，相同的 GUI 可以在无需修改的情况下运行在各种平台上。

名为“布局管理器”（layout managers）的 Java 内置类负责将相对位置映射到实际/物理位置的任务。Java 支持许多类型的布局管理器，我们将讨论以下布局管理器：

1. `FlowLayout`
2. `GridLayout`
3. `BorderLayout`
4. `CardLayout`
5. `GridBagLayout`

## 使用布局管理器时的两个观察结果

- 我们不需要承担指定每个组件精确位置和尺寸的负担。
- 我们不再拥有指定每个组件精确位置和尺寸的权力。

## 为什么 Java 使用布局管理器？

原因有两个：

1. 理论上的原因在于，精确布局（即每个组件尺寸和位置的像素规范）是一项重复且经常执行的任务；因此，根据面向对象编程（OOP），布局功能应当封装在一个或多个类中以实现任务的自动化。显然，布局管理器消除了许多开发中的琐工作。许多程序员最初不喜欢布局管理器，但随着繁琐选择的消除，他们越来越欣赏它们。
2. 使用布局管理器的实际原因源于 Java 的平台无关性。在 Java 中，`AWT` 组件的行为借自运行 `JVM` 的底层硬件的窗口系统。因此，在 Macintosh 上，`AWT` 按钮就像其他 Mac 按钮一样；在 Motif 平台上，Java 按钮看起来就像其他 Motif 按钮，以此类推。这里的问题在于，按钮和其他组件在不同平台上实例化时具有不同的尺寸。

如果 Java 鼓励精确的像素级尺寸和定位，那么会有很多 Java GUI 在其源平台上看起来很精美，但在其他平台上看起来非常糟糕甚至无法使用。如上所述，布局管理器通过使用相对定位解决了这个问题。

## 布局策略

每个 Java 组件都有 `preferred size`（首选尺寸）。`preferred size` 表达了组件希望有多大，前提是不与布局管理器发生冲突。`Preferred size` 通常是渲染组件以使其在视觉上具有意义所必需的最小尺寸；例如，一个按钮的 `preferred size` 是其标签文本的大小，加上文本周围的一小圈空白边框，再加上标记按钮边界的阴影装饰，因此，按钮的首选尺寸是“恰好足够”。`Preferred size` 取决平台，因为组件的边界装饰随系统而异。

当布局管理器对其容器的子组件进行布局时，它必须平衡两个考量：

(i) 布局策略和
(ii) 每个组件的 `preferred size`

首要任务是执行布局策略。如果尊重组件的 `preferred size` 意味着违反了布局策略，那么布局管理器将覆盖组件的 `preferred size`。理解布局管理器意味着理解它将把组件放置在什么位置，以及它将如何处理组件的 `preferred size`。

## FlowLayout

流布局管理器的功能封装在 `java.awt.FlowLayout` 类中。流布局管理器将组件排列在水平行中。它是面板（panels）和 Applet 程序（applets）的默认布局管理器类型。

流布局管理器尽可能将多个组件放入第一行，并将其他组件移动到第二行。如果第二行没有留空间，组件将移动到第三行，依此类推。这与在文档中输入文字非常相似。当我们到达当前行的末尾时，下一个单词将移动到下一行，以此类推。如果我们更改了文档的宽度或高度，整个文档将重新格式化。

组件始终按照它们被添加到容器的顺序从左到右出现。

默认情况下，流布局管理器在水平和垂直方向上的组件之间留有五个像素的间隙。可以通过调用 `FlowLayout` 构造函数的重载版本并传入所需的水平和垂直间隙来更改此默认值。

在每一行内，组件间距均匀，且组件簇居中。簇的对齐方式（有时称为“对齐线”）可以通过向流布局构造函数传递参数来控制。可能的值有：

- `FlowLayout.LEFT`
- `FlowLayout.CENTER`
- `FlowLayout.RIGHT`

### 示例 17.1

```java
import java.awt.*;
class MyFrame1 {
    public static void main(String args[]) {
        Frame f = new Frame();
        FlowLayout flow = new FlowLayout();
        f.setLayout(flow);
        Label l1 = new Label("Name ");
        f.add(l1);
        TextField tf1 = new TextField("Matrix");
        f.add(tf1);
        tf1.setBackground(Color.green);
        tf1.setForeground(Color.red);
        Button b1 = new Button("ok");
        Font f1 = new Font("Arial", Font.BOLD, 4);
        b1.setFont(f1);
        f.add(b1);
        f.setSize(500, 100);
        f.setVisible(true);
    }
}
```

注意：如果我们减小上述窗口的大小且三个组件无法放入单行内，则组件将从最后一个组件开始移动到下一行。

输出：

![](img/image01269.jpeg)

### 示例 17.2

```java
import java.awt.*;
public class MyFrame2 extends Frame {
    public static void main(String args[]) {
        MyFrame2 f = new MyFrame2();
        f.setLayout(new FlowLayout(FlowLayout.CENTER));
        System.out.println();
        Label l1 = new Label("Name ");
        f.add(l1);
        TextField tf1 = new TextField("Sample");
        f.add(tf1);
        tf1.setBackground(Color.green);
        tf1.setForeground(Color.red);
        Button b1 = new Button("OK");
        b1.setFont(new Font("Serif", Font.BOLD, 24));
        b1.setEnabled(false);
        Dimension d = b1.getSize();
        System.out.println("Button Size :" + d.width + " " + d.height);
        f.add(b1);
    }
}
```

```java
// f.setResizable(false);
// f.setUndecorated(true);
f.setVisible(true);
Dimension d1 = b1.getSize();
System.out.println("Button Size: " + d1.width + " " + d1.height);
Dimension d2 = f.getSize();
System.out.println("Frame Size: " + d2.width + " " + d2.height);
try {
    Thread.sleep(5000);
} catch (InterruptedException e) { }
f.setVisible(false);
f.setSize(500, 100);
f.setVisible(true);
try {
    Thread.sleep(500);
} catch (InterruptedException e) { }
f.setVisible(false);
f.setBounds(20, 20, 100, 100);
f.setVisible(true);
Dimension d3 = f.getSize();
System.out.println("Frame Size : " + d3.width + " " + d3.height);
System.out.println(f.paramString());
}
```

**输出：**

![](img/image01270.jpeg)

```
frame0,0,0,0x0,invalid,hidden,layout=java.awt.FlowLayout,title=,resizable,normal
Button Size :0 0
Button Size: 52 35
Frame Size: 123 34
Frame Size : 123 100
frame0,20,20,123x100,layout=java.awt.FlowLayout,title=,resizable,normal
```

### 示例 17.3

如果我们改变这一行，组件将左对齐：

`f.setLayout(new FlowLayout(FlowLayout.LEFT));`

**输出：**

![](img/image1271.jpeg)

### 示例 17.4

如果我们改变这一行，组件将右对齐：

`f.setLayout(new FlowLayout(FlowLayout.RIGHT));`

**输出：**

![](img/image1272.jpeg)

### 示例 17.5

我们可以在设置布局时，使用重载的构造函数来更改行内组件之间的间距（水平间距）以及行之间的间距（垂直间距）：

`f.setLayout(new FlowLayout(FlowLayout.CENTER, 20, 20));`

**输出：**

![](img/image1275.jpeg)

## 3. GridLayout

`GridLayout` 的功能封装在 `java.awt.GridLayout` 类中。`GridLayout` 以表格格式按行和列排列组件。我们可以将容器空间视为由行和列组成的网格。在指定布局时，必须指定行数和列数。`GridLayout` 根据行的大小（即布局中指定的列数）将尽可能多的组件放入第一行，并将其他组件移动到第二行，依此类推。这类似于电子表格，它被分为固定数量的行和列。流式布局管理器总是尊重组件的首选大小，而 `GridLayout` 管理器则处于另一个极端：当它在给定空间内执行布局时，它会忽略组件的首选大小。网格布局中的每一行和每一列的大小都相同，布局可用的总区域在行数和列数之间平分。当我们添加较少的组件（即远少于行乘以列数）或非常多的组件（即多于行乘以列数）时，`GridLayout` 的表现会很奇怪。如果将相同的组件放置在一个更高更窄的框架中，那么每个组件都会按比例地变得更高、更窄，反之亦然。

### 示例 17.6

```java
import java.awt.*;
public class MyFrame6 extends Frame {
    public static void main(String args[]) {
        Frame f = new MyFrame6();
        f.setLayout(new GridLayout(5, 3));
        for (int row = 0; row < 5; row++) {
            f.add(new Label("Label" + row));
            f.add(new Button("Button" + row));
            f.add(new TextField("TextField" + row));
        }
        f.setSize(500, 200);
        f.setVisible(true);
    }
}
```

**输出：**

![](img/image01276.jpeg)

## 4. Border Layout（边界布局）

`BorderLayout` 管理器的功能封装在 `java.awt.BorderLayout` 类中。`BorderLayout` 管理器是框架的默认管理器，因此应用程序程序员迟早都会熟悉它。

它强制执行非常实用的布局策略，但可能没有流式布局或网格布局管理器那样的直观。流式布局管理器总是尊重组件的首选大小；而网格布局管理器从不。`Border layout` 管理器的做法介于两者之间。

`Border Layout` 管理器将可用的容器空间分为五个部分：`North`（北）、`South`（南）、`East`（东）、`West`（西）和 `Center`（中心）。我们可以在每个区域添加一个组件。

这五个区域可以是空的，也可以包含一个组件（即不是每个区域都需要包含组件，但每个区域只能包含一个组件）。

`Border layout` 管理器尊重 `North` 和 `South` 组件的首选高度，并强制它们的宽度与容器完全一致。`North` 和 `South` 区域适用于工具栏、状态栏以及任何应该尽可能宽但高度不应超过所需的控件。

`East` 和 `West` 区域与 `North` 和 `South` 相反。在 `East` 和 `West` 中，组件获得其首选宽度，但高度受到限制。

在这里，组件垂直向上延伸到 `North` 组件的底部（如果存在）或容器的顶部（如果没有 `North`）。

同样地，组件垂直向下延伸到 `South` 组件（如果存在）或容器的底部（如果没有 `South`）。

- `BorderLayout.SOUTH`
- `BorderLayout.EAST`
- `BorderLayout.WEST`
- `BorderLayout.CENTER`

`Border` 布局管理器控制的第五个区域被称为 `Center`。`Center` 仅仅是容器在分配了 `North`、`South`、`East` 和 `West` 后剩余的部分。

在向 `center` 添加组件时，向 `add()` 调用传递第二个参数是合法的但非常不明智的。在 Java 平台上，`Border` 布局管理器假设我们的意思是 `center`。

然而，在旧版本中，这种行为是不可预测的，通常会导致组件完全不可见。

### Example 17.7

```java
import java.awt.*;
public class MyFrame7 {
    public static void main(String args[]) {
        Frame f = new Frame();
        Scrollbar sbRight = new Scrollbar(Scrollbar.VERTICAL);
        f.add(sbRight, BorderLayout.EAST);
        Scrollbar sbLeft = new Scrollbar(Scrollbar.VERTICAL);
        f.add(sbLeft, BorderLayout.WEST);
        Label labelTop = new Label("This is North");
        labelTop.setFont(new Font("Serif", Font.ITALIC, 36));
        labelTop.setForeground(Color.white);
        labelTop.setBackground(Color.black);
        f.add(labelTop, BorderLayout.NORTH);
        Label labelBottom = new Label("This is south");
        labelBottom.setFont(new Font("Monaced", Font.BOLD, 18));
        labelBottom.setForeground(Color.white);
        labelBottom.setBackground(Color.black);
        f.add(labelBottom, BorderLayout.SOUTH);
        f.setSize(50, 20);
        f.setVisible(true);
    }
}
```

输出：![](img/image01277.jpeg)

### Example 17.8



```java
import java.awt.*;
public class MyFrame8 extends Frame {
    public static void main(String args[]) {
        Frame f = new MyFrame8();
        // f.setLayout(new BorderLayout());
        f.add(new Button("N"), BorderLayout.NORTH);
        f.add(new Button("S"), BorderLayout.SOUTH);
        f.add(new Button("E"), BorderLayout.EAST);
        f.add(new Button("W"), BorderLayout.WEST);
        Panel p = new Panel();
        p.setBackground(Color.green);
        f.add(p, BorderLayout.CENTER);
        // f.add(p); default center
        f.setSize(300, 300);
        f.setVisible(true);
    }
}
```

输出：![](img/image01278.jpeg)

### Example 17.9

```java
import java.awt.*;
class BorderLayout3 extends Frame {
    public static void main(String args[]) {
        Frame f = new BorderLayout3();
        // f.setLayout(new BorderLayout());
        Panel toolbar = new Panel();
        toolbar.setLayout(new FlowLayout(FlowLayout.LEFT));
        toolbar.setBackground(Color.lightGray);
        toolbar.add(new Button("This"));
        toolbar.add(new Button("Is"));
        toolbar.add(new Button("The"));
        toolbar.add(new Button("Toolbar"));
        f.add(toolbar, BorderLayout.NORTH);
        TextField status = new TextField("Status.");
        status.setFont(new Font("Monospaced", Font.BOLD, 48));
        f.add(status, BorderLayout.SOUTH);
        f.setSize(300, 300);
        f.setVisible(true);
    }
}
```

输出：![](img/image01279.jpeg)

### CardLayout

在 `CardLayout` 中，我们可以存储许多卡片，但一次只显示一张。一次只有一张卡片可见，但你可以切换到另一张。如果我们想一次显示多个卡片，必须为每张卡片创建一个 `Panel`，并创建一个包含它们的父 `Panel`。

### 构造函数

- `CardLayout()`
- `CardLayout(int h, int v)`

### 方法

- `first(Container parent)`：跳转到第一个卡片。
- `next(Container parent)`：跳转到下一张卡片。如果当前显示的卡片是最后一张，此方法将切换到第一张。
- `previous(Container parent)`：跳转到上一个卡片。如果当前显示的卡片是第一张，此方法将切换到最后一张。
- `last(Container parent)`：跳转到最后一张卡片。
- `show(Container parent, String name)`：跳转到使用 `name` 添加到布局的组件。如果不存在此类组件，则什么也不会发生。

### 使用方法

1. 创建一个新的 `Panel` 和一个 `CardLayout` 对象。
2. 使用第一步中创建的实例为 `Panel` 设置布局。
3. 现在，为每张卡片创建一个单独的 `Panel`，并添加任何我们想添加的内容（按钮、复选框等）。
4. 将步骤 3 中创建的每个 `Panel` 添加到步骤 1 中创建的主 `Panel` 中，并为每个指定一个唯一的卡片名称。
5. 最后，将主面板添加到 applet 窗口。

### Example 17.10

```java
import java.awt.*;
import java.awt.event.*;
import java.applet.*;
/*<applet code="CardLayoutTest" width=500 height=100></applet>*/
public class CardLayoutTest extends Applet implements ActionListener, MouseListener {
    Panel mp;
}
```

```java
CardLayout c1;

public void init() {
    Button b1 = new Button("First");
    Button b2 = new Button("Second");
    b1.addActionListener(this);
    b2.addActionListener(this);
    add(b1);
    add(b2);
    Panel p1 = new Panel();
    Label l1 = new Label("INDIA");
    p1.add(l1);
    Panel p2 = new Panel();
    Label l2 = new Label("USA");
    p2.add(l2);
    mp = new Panel();
    c1 = new CardLayout();
    mp.setLayout(c1);
    mp.add(p1, "Country1");
    mp.add(p2, "Country2");
    add(mp);
    addMouseListener(this);
}

public void actionPerformed(ActionEvent ae) {
    Button b = (Button) ae.getSource();
    if (b.getLabel().equals("First"))
        c1.show(mp, "Country1");
    else
        c1.show(mp, "Country2");
}

public void mousePressed(MouseEvent me) {
    c1.next(mp);
}

public void mouseReleased(MouseEvent me) {}
public void mouseClicked(MouseEvent me) {}
public void mouseEntered(MouseEvent me) {}
public void mouseExited(MouseEvent me) {}
```

Output:

![](img/image0280.jpeg)

### GridBagLayout

`GridBagLayout` 是标准布局管理器中最复杂且最灵活的一种。尽管它听起来似乎应该是 `GridLayout` 的子类，但实际上它完全不同。在 `GridLayout` 中，元素排列为

### 示例 17.11

AWT 组件可以分类为：

1. 可视化组件。
2. 容器组件。
3. 菜单组件。

可视化组件和容器组件都是从 `java.awt.Component` 类开始的组件层次结构的一部分。

#### `java.awt.Component` 类的方法

由于继承自 `java.awt.Component`，所有可视化组件和容器组件都实现了几个方法。（菜单组件继承自 `java.awt.MenuComponent`，因此它们不继承相同的父类功能）。这些方法在下文中进行了讨论：

- `Dimension getSize()`：以 `Dimension` 对象的格式返回此组件的大小，该对象具有类型为 `int` 的公共数据成员 `height` 和 `width`。
- `void setBackground(Color c)`：设置组件的背景颜色。通常，背景颜色用于渲染组件的非文本区域。
- `void setForeground(Color c)`：设置组件的前景色。通常组件的前景色用于渲染文本。如果我们不显式设置组件的前景色或背景色，组件将使用其直接容器的前景色和背景色。
- `void setFont(Font f)`：`setFont()` 方法决定组件用于渲染任何需要显示的文本的字体。如果我们不显式设置组件的字体，组件将使用其容器的字体。
- `void setEnabled(boolean b)`：如果参数为 `true`，则组件具有正常外观。如果参数为 `false`，则组件将变为灰色且不响应用户输入。
- `void setSize(Dimension d)`：设置组件的大小。
- `void setSize(int width, int height)`：设置组件的大小。
- `void setBounds(int x, int y, int width, int height)`：尝试移动并调整组件的大小。左上角的新位置由 `x` 和 `y` 指定，新大小由 `width` 和 `height` 指定。
- `void setVisible(boolean b)`：此方法接受一个布尔参数，用于决定组件是否在屏幕上可见。此方法通常用于帧。

**注意：** 如果我们尝试过调用 `setSize()` 或 `setBounds()`，会发现这通常是徒劳的。我们尝试赋予组件的大小和位置会被布局管理器覆盖。事实上，这两个方法大部分存在是为了供布局管理器使用的。该规则的一个主要例外是 `Frame` 类，它不属于布局管理器之下，并且完全接受设置其大小或边界。

### 可视化组件

可视化组件是用户可以直接看到并交互的组件。AWT 支持以下可视化组件：

- `Canvas`（画布）
- `Checkbox`（复选框）
- `Choice`（组合框）
- `Dialog`（对话框）
- `Label`（标签）
- `List`（列表）
- `ScrollPane`（滚动面板）
- `TextField`

要在 GUI 中使用这些组件之一，我们首先通过调用相应的构造函数创建一个实例。然后将组件添加到容器中。

### Button

`Button` 类实现了一个按钮。

**构造函数：**

- `Button()`
- `Button(String)`：构造函数接受一个字符串参数，指定按钮的标签。当按钮按下时，它会发送一个 `ActionEvent`。

**方法：**

- `String getLabel()`：获取此按钮的标签。
- `void setLabel(String label)`：将按钮的标签设置为指定的字符串。
- `void addActionListener(ActionListener l)`：添加指定的动作监听器以接收此按钮的动作事件。

#### 示例 17.2

```java
import java.awt.*;
class ButtonTest {
    public static void main(String args[]) {
        Frame f = new Frame("Testing Button Component");
        f.setLayout(new FlowLayout());
        Font f1 = new Font("Arial", Font.BOLD, 40);
        Color c1 = new Color(255, 0, 0);
        Color c2 = new Color(0, 25, 0);
        Button b1 = new Button();
        Button b2 = new Button("Cancel");
        b1.setForeground(c1);
        b2.setForeground(c1);
        b1.setBackground(c2);
        b2.setBackground(c2);
        b1.setFont(f1);
        b2.setFont(f1);
        b1.setLabel("Ok");
        System.out.println(b2.getLabel());
        f.add(b1);
        f.add(b2);
        f.setSize(500, 200);
    }
}
```

```java
f.setVisible(true);
}
}
```

输出：

![](img/image0128.jpeg)

## Canvas

`Canvas` 是一种组件，没有默认的显示或行为。我们可以通过子类 `Canvas` 来创建自定义的绘制区域、工作区域、组件等。`Canvas` 接收来自鼠标和键盘的输入事件，由程序员将这些输入转换为有意义的外观和感受。

画布的默认尺寸（或更准确地说，首选尺寸）小得毫无用处。处理这个问题的一种方法是使用可以调整画布大小的布局管理器。另一种方法是手动对画布调用 `setSize()`，画布是少数这种方法可能有效的案例之一，因为我们传递给 `setSize()` 方法的值将直接成为画布的首选尺寸。

### 示例 17.13

```java
import java.awt.*;
class CanvasTest {
    public static void main(String args[]) {
        Frame f = new Frame();
        f.setLayout(new FlowLayout());
        Canvas c = new MyCanvas();
        c.setSize(100, 100);
        f.add(c);
        f.setSize(300, 300);
        f.setVisible(true);
    }
}
class MyCanvas extends Canvas {
    public void paint(Graphics g) {
        setBackground(Color.green);
        g.setColor(Color.red);
        g.drawLine(0, 0, 99, 99);
    }
}
```

输出：

![](img/image1282.jpeg)

## Checkbox

复选框是一个双状态的按钮。这两个状态分别是 `true`（已选中）和 `false`（未选中）。`Checkbox` 构造函数的三个基本形式为：

- `Checkbox()`：创建一个带标签为空字符串的复选框。
- `Checkbox(String label)`：创建一个带有指定标签的复选框。
- `Checkbox(String label, boolean state)`：创建一个带有指定标签并设置指定状态的复选框。如果我们不指定初始状态，默认值为 `false`。

方法：

- `String getLabel()`：获取此复选框的标签。
- `void setLabel(String label)`：将复选框的标签设置为字符串参数。
- `boolean getState()`：确定复选框处于“开启”还是“关闭”状态。
- `void setState(boolean state)`：将此复选框的状态设置为指定的状态。
- `void addItemListener(ItemListener)`：添加指定的项监听器以接收来自此复选框的项事件。

### 示例 17.14

```java
import java.awt.*;
class CheckboxTest {
    public static void main(String args[]) {
        Frame f = new Frame("Testing Checkbox Component");
        f.setLayout(new GridLayout(3, 1));
        Checkbox c1 = new Checkbox();
        Checkbox c2 = new Checkbox("Lunch", true);
        Checkbox c3 = new Checkbox("Dinner");
        c1.setLabel("Fast");
        c3.setState(true);
        f.add(c1);
        f.add(c2);
        f.add(c3);
        if (c1.getState())
            System.out.println(c1.getLabel());
        if (c2.getState())
            System.out.println(c2.getLabel());
        if (c3.getState())
            System.out.println(c3.getLabel());
        f.setSize(100, 100);
        f.setVisible(true);
    }
}
```

输出：



![](img/image1283.jpeg)

### 另一个示例

```java
import java.awt.*;
import java.awt.event.*;
class CheckboxTest extends Frame implements ItemListener {
    Checkbox c1;
    TextField tf1;
    CheckboxTest() {
        setLayout(new GridLayout(2,1));
        c1=new Checkbox("Red");
        c1.addItemListener(this);
        add(c1);
        tf1=new TextField();
        add(tf1);
        setSize(100,100);
        setVisible(true);
    }
    public static void main(String args[]) {
        new CheckboxTest();
    }
    public void itemChanged(ItemEvent ie) {
        if(c1.getState())
            tf1.setBackground(Color.red);
        else
            tf1.setBackground(Color.white);
    }
}
```

## Radio button

复选框可以被组成复选框组，它们具有单选行为。在单选行为下，框组中任何时候只能有一个成员状态为 `true`；选择新成员会将上一个成员的状态更改为 `false`。许多系统（例如 Motif）将单选组作为它们自身的组件来实现。

我们可以通过创建多个复选框并使用 `java.awt.CheckboxGroup` 将它们进行分组来实现单选行为。在 Java 中，`java.awt.CheckboxGroup` 类并不是一个组件；它仅仅是一个用于组织复选框的类。这意味着 Java 对复选框组成员之间的空间关系没有加任何限制。如果我们愿意，可以将组中的一个成员放在框架的左上角，另一个成员放在右下角，第三个成员放在另一个框架中。当然，结果可能违背逻辑和大多数 GUI 指南。

`CheckboxGroup` 两个方法支持获取和设置当前选中的成员或组：

- `Checkbox getSelectedCheckbox()`：获取此复选框组的当前选择。
- `void setSelectedCheckbox(Checkbox box)`：将此组中当前选中的复选框设置为指定的复选框。

### 示例 17.15

```java
import java.awt.*;
class CheckboxGroupTest {
    public static void main(String args[]) {
    }
}
```

```java
f.setLayout(new GridLayout(3,1));
CheckboxGroup cbg=new CheckboxGroup();
Checkbox c1=new Checkbox("BreakFast",false,cbg);
Checkbox c2=new Checkbox("Lunch",true,cbg);
Checkbox c3=new Checkbox("Dinner",false,cbg);
c3.setState(true);
f.add(c1);f.add(c2);f.add(c3);

if(c1.getState())
    System.out.println(c1.getLabel());
else if(c2.getState())
    System.out.println(c2.getLabel());
else if(c3.getState())
    System.out.println(c3.getLabel());

f.setSize(100,100);
f.setVisible(true);
```

输出：

![](img/image0284.jpeg)

### Choice

`Choice` 是一个下拉列表。

### 方法

- `void add (String item)`: 向此 `Choice` 菜单添加添加项。
- `void addItemListener (ItemListener i)`: 添加指定的项监听器以接收来自此选择菜单的项事件。
- `String getItem (int index)`: 获取此 `Choice` 菜单中指定索引处的字符串。
- `int getItemCount ()`: 返回此 `Choice` 菜单中项的数量。
- `int getSelectedIndex ()`: 返回当前选中项的索引。
- `String getSelectedItem ()`: 获取当前选择的字符串表示形式。
- `void insert (String item, int index)`: 在指定位置将项插入到此选择框中。
- `void remove (int position)`: 移除选择菜单中第一个出现的指定位置项。
- `void remove(String item)`: 从 `Choice` 菜单中移除第一个出现的指定项。
- `void removeAll ()`: 移除选择菜单中的所有项。
- `void select (int pos)`: 将此选择中的选中项设置为指定位置的项。
- `void select (String Str)`: 将此 `Choice` 中名称与指定字符串相同的项设置为选中。

#### 示例 7.16

```java
import java.awt.*;
class Choice
{
    public static void main(String args[]) throws InterruptedException
    {
        Frame f = new Frame("Testing Choice");
        f.setLayout(new FlowLayout());
        f.setSize(100,100);
        f.setVisible(true);
        Choice c1=new Choice();
        c1.add("BreakFast");
        c1.add("Lunch");
        c1.add("Dinner");
        f.add(c1);
        c1.select("Dinner"); // c1.select(2);
        Thread.sleep(100);
        System.out.println(c1.getSelectedItem());
        System.out.println(c1.getSelectedIndex());
        System.out.println(c1.getItemCount());
        System.out.println(c1.getItem(0));
        c1.insert("Brunch",1);
        c1.remove(2); // c1.remove("Lunch");
    }
}
```

输出：

![](img/image0285.jpeg)

```java
import java.awt.*;
import java.awt.event.*;
class CheckboxItemTest extends Frame implements ItemListener
{
    TextField tf1;
    Choice c1;
    CheckboxItemTest()
    {
        setLayout(new FlowLayout());
        c1=new Choice();
        c1.add("red");
        c1.add("green");
        c1.add("blue");
        tf1 = new TextField(8);
        tf1.setBackground(Color.red);
        c1.addItemListener(this);
        add(c1);
        add(tf1);
        setSize(200,200);
        setVisible(true);
    }
    public static void main(String args[])
    {
        new CheckboxItemTest();
    }
    public void itemChanged(ItemEvent ie)
    {
        String s=(String)ie.getItem();
        if(s.equals("red"))
            tf1.setBackground(Color.red);
        else if(s.equals("green"))
            tf1.setBackground(Color.green);
        else if(s.equals("blue"))
            tf1.setBackground(Color.blue);
    }
}
```

### Label

简单的可见 AWT 组件是 `label`。`Label` 通常不用于响应用户输入或发送事件。

### 构造函数

- `Label ()`: 构造一个空标签。
- `Label (String text)`: 构造一个带有指定字符串文本的新标签，并左对齐。
- `Label (String text, int alignment)`: 构造一个标签，以指定的对齐方式显示指定的字符串。

`Label` 的默认对齐方式是左对齐。要设置对齐方式，使用构造函数的第三种形式并传入以下值：

- `Label.LEFT`
- `Label.CENTER`
- `Label.RIGHT`

### 方法

- `String getText ()`: 获取此标签的文本。
- `void setText (String text)`: 将此标签的文本设置为指定的文本。

示例 7.17

```java
import java.awt.*;

class LabelTest
{
    public static void main(String args[])
    {
        Frame f = new Frame("Testing Label Component");
        f.setLayout(new GridLayout(3,3));
        f.setFont(new Font("Arial",Font.PLAIN, 20));
        Label l1 = new Label("India",Label.LEFT);
        Label l2 = new Label("Pakistan",Label.LEFT);
        Label l3 = new Label("UK",Label.LEFT);
        Label l4 = new Label("India",Label.CENTER);
        Label l5 = new Label("Pakistan",Label.CENTER);
        Label l6 = new Label("UK",Label.CENTER);
        Label l7 = new Label("India",Label.RIGHT);
        Label l8 = new Label("Pakistan",Label.RIGHT);
        Label l9 = new Label("UK",Label.RIGHT);
        l3.setText("USA");
        System.out.println(l1.getText());
        f.add(l1);f.add(l4);f.add(l7);
        f.add(l2);f.add(l5);f.add(l8);
        f.add(l3);f.add(l6);f.add(l9);
        f.setSize(500,200);
        f.setVisible(true);
    }
}
```

输出：

![](img/image0286.jpeg)

### 列表 (List)

列表是垂直排列的文本集合。如果列表包含的项目超过显示范围，它会自动获取一个垂直滚动条。

### 构造函数

- `List()`: 创建一个新的滚动列表。此构造函数未指定行数，但会产生四行的默认首选高度。当然，在许多情况下，列表的实际高度将布局管理器决定。
- `List(int rows)`: 创建一个新的滚动列表，并用指定的可见行数初始化。
- `List(int rows, boolean multipleMode)`: 创建一个新的滚动列表，初始化为显示指定的行数并允许多项选择。

#### 示例 17.18

```java
import java.awt.*;
class ListTest
{
    public static void main(String args[])
    {
        Frame f = new Frame () ;
        f.setLayout (new FlowLayout());
        List l1=new List(3,true);
        l1.add("India");
        l1.add("Nepal");
        l1.add("Shri Lanka");
        l1.add("USA");
        l1.add("UK");
        f.add(l1);
        System.out.println(l1.getRows());
        f.setSize(300, 300);
        f.setVisible(true);
    }
}
```

输出：

![](img/image0287.jpeg)

该列表有五个项目，但只有 3 行可见，因此提供了一个滚动条以访问底部行。注意：在列表中选择项目会导致列表发送一个项目事件（Item event）；双击项目会发送一个动作事件（Action）。

- `void add(String item)`: 将指定项目添加到滚动列表的末尾。
- `void add(String item, int index)`: 在索引指定的位置将指定项目添加到滚动列表。
- `void addActionListener(ActionListener i)`: 添加指定的监听器以接收来自此列表的动作事件。
- `void addItemListener(ItemListener i)`: 添加指定的监听器以接收此列表的项目事件。
- `String getItem(int index)`: 获取与指定索引关联的项目。
- `int getItemCount()`: 获取列表中的项目数量。
- `String[] getItems()`: 获取列表中的所有项目。
- `int getRows()`: 获取此列表中可见的行数。
- `int getSelectedIndex()`: 获取列表中被选中项目的索引。
- `int[] getSelectedIndexes()`: 获取列表中被选中的索引。
- `String getSelectedItem()`: 获取滚动列表中的被选中项目。
- `String[] getSelectedItems()`: 获取滚动列表中的被选中项目。
- `void remove(int position)`: 从滚动列表中移除指定位置的项目。
- `void remove(String item)`: 从列表中移除首次出现的指定项目。
- `void removeAll()`: 从此列表中移除所有项目。
- `void replaceItem(String newValue, int index)`: 用新字符串替换滚动列表中指定索引处的项目。
- `void select(int index)`: 选中滚动列表中指定索引的项目。
- `void setMultipleMode(boolean b)`: 设置标志以决定此列表是否允许多项选择。



```java
import java.awt.*;
import java.awt.event.*;

class ListTest extends Frame implements ActionListener {
    Button b1, b2, b3, b4, b5, b6;
    List l1, l2;
    TextField tf1, tf2;

    ListTest() {
        setLayout(new GridLayout(3, 3));
        l1 = new List(3, true);
        l2 = new List(3, true);
        b1 = new Button(">");
        b2 = new Button(">>");
        b3 = new Button("<");
        b4 = new Button("<<");
        b5 = new Button("Add");
        b6 = new Button("Add");
        b1.addActionListener(this);
        b2.addActionListener(this);
        b3.addActionListener(this);
        b4.addActionListener(this);
        b5.addActionListener(this);
        b6.addActionListener(this);
        tf1 = new TextField();
        tf2 = new TextField();
    }
}
```

```java
Panel p1 = new Panel();
p1.setLayout(new GridLayout(4, 1));
p1.add(b1);
p1.add(b2);
p1.add(b3);
p1.add(b4);
add(l1);
add(p1);
add(l2);
add(tf1);
add(new Label());
add(tf2);
add(b5);
add(new Label());
add(b6);
setSize(300, 300);
setVisible(true);
}

public static void main(String args[]) {
    new Test();
}

public void actionPerformed(ActionEvent ae) {
    Button b = (Button) ae.getSource();
    if (b == b1) {
        String s[] = l1.getSelectedItems();
        for (int i = 0; i < s.length; i++) {
            l2.add(s[i]);
            l1.remove(s[i]);
        }
    } else if (b == b2) {
        String s[] = l1.getItems();
        for (int i = 0; i < s.length; i++) {
            l2.add(s[i]);
            l1.remove(s[i]);
        }
    } else if (b == b3) {
        String s[] = l2.getSelectedItems();
        for (int i = 0; i < s.length; i++) {
            l1.add(s[i]);
            l2.remove(s[i]);
        }
    } else if (b == b4) {
        String s[] = l2.getItems();
        for (int i = 0; i < s.length; i++) {
            l1.add(s[i]);
            l2.remove(s[i]);
        }
    } else if (b == b5) {
        l1.add(tf1.getText());
    } else if (b == b6) {
        l2.add(tf2.getText());
    }
}
```

### TextField 和 TextArea

`TextField` 和 `TextArea` 类实现了用于文本输入、显示和编辑的一维和二维组件。这两个类都继承了父类 `TextComponent`：

`Object` -> `Component` -> `TextComponent` -> (`TextField`, `TextArea`)。

这两个类都拥有多种构造函数，提供了指定或不指定初始字符串或大小的选项。不指定大小的构造函数最适用于布局管理器将忽略组件尺寸的情况。

#### TextField 类的构造函数

- `TextField()`: 构建一个新的文本字段。
- `TextField(int columns)`: 构建一个具有指定列数的新文本字段。
- `TextField(String text)`: 构建一个带有指定文本的新文本字段。
- `TextField(String text, int columns)`: 构建一个带有指定文本的新文本字段，其宽度足够容纳指定的列数。

#### TextArea 类的构造函数

- `TextArea()`: 构建一个带有空字符串的新文本区域。
- `TextArea(int rows, int columns)`: 构建一个具有指定行数和列数且内容为空的文本区域。
- `TextArea(String text)`: 构建一个带有指定文本的文本区域。
- `TextArea(String text, int rows, int columns)`: 构建带有指定文本以及指定行数和列数的文本区域。
- `TextArea(String text, int rows, int columns, int ScrollPolicy)`: 构建带有指定文本以及指定的行、列和滚动策略的文本区域。

`TextArea` 类定义了几个常量，可以作为 `scrollPolicy` 参数的值：

- `SCROLLBARS_BOTH`
- `SCROLLBARS_VERTICAL_ONLY`
- `SCROLLBARS_HORIZONTAL_ONLY`
- `SCROLLBARS_NONE`

对于这两个类，`columns` 参数都存在一些出人意料的问题。首先，列数是根据特定字体渲染的文本宽度的度量。一个使用微字体的 25 列文本区域将非常窄，而一个使用巨大字体的 5 列文本区域将极其宽。其次，存在等比例字体的问题。对于等宽字体，列宽应该是多少显而易见。对于等比例字体，列宽取该字体所有字符宽度的平均值。这个平均值是集合中所有字符的简单平均值；并没有考虑使用频率。因此在大多数情况下，包含小写字母的文本组件显示的字符数将超过请求的数量。

#### TextComponent 类中的方法

- `String selectText()`: 返回该文本组件显示的文本中的选定文本。
- `String getText()`: 返回该文本组件显示的文本。
- `void setEditable(Boolean b)`: 设置决定此文本组件是否可编辑的标志。
- `void setText(String t)`: 将该文本组件显示的文本设为指定的文本。

#### 示例 17.19

```java
import java.awt.*;

class TextFieldTest {
    public static void main(String args[]) {
        Frame f = new Frame();
        f.setLayout(new FlowLayout());
        TextField tf1 = new TextField();
    }
}
```

```java
TextField tf2 = new TextField(8);
TextField tf3 = new TextField("matrix");
TextField tf4 = new TextField("matrix", 20);
TextArea ta1 = new TextArea();
TextArea ta2 = new TextArea(3, 8);
TextArea ta3 = new TextArea("abc\nxyz\naaa");
TextArea ta4 = new TextArea("abc\nxyz\naaa", 2, 2);
TextArea ta5 = new TextArea("abc\nxyz\naaa", 4, 20, TextArea.SCROLLBARS_BOTH);
f.add(tf1);
f.add(tf2);
f.add(tf3);
f.add(tf4);
f.add(ta1);
f.add(ta2);
f.add(ta3);
f.add(ta4);
f.add(ta5);
tf1.setText("abc");
System.out.println(tf3.getText());
tf3.setEditable(false);
f.setSize(800, 400);
f.setVisible(true);
```

输出: ![](img/image0128.jpeg)

### FileDialog

此类表示文件打开或保存对话框。文件对话框是一个模态对话框，这意味着只要对话框显示在屏幕上，来自父框架的输入将专门定向到对话框。当用户指定文件或点击取消按钮时，对话框会自动移除。最有用的 `FileDialog` 构造函数形式如下：

`FileDialog(Frame parent, String title, int mode)`

对话框的 `parent` 是对话框将出现的帧。`title` 显示在对话框的标题栏中。`mode` 应该是以下：

- `FileDialog.LOAD`
- `FileDialog.SAVE`

在用户指定文件后，可以使用以下方法获取文件名或其目录：

- `String getDirectory()`: 获取此文件对话框选定的目录。
- `String getFile()`: 获取此文件对话框选择的文件。

#### 示例 17.20

```java
import java.awt.*;

public class FileDialogTest {
    public static void main(String args[]) {
        Frame f = new Frame();
        f.setLayout(new FlowLayout());
        f.setSize(200, 200);
        f.setVisible(true);
        FileDialog fd = new FileDialog(f, "Load file", FileDialog.LOAD);
        fd.setVisible(true);
        System.out.println(fd.getFile());
        System.out.println(fd.getDirectory());
    }
}
```

### ScrollPane

`ScrollPane` 可以包含单个组件，该组件可能比滚动面板本身更高或更宽。如果容器大于滚动面板，那么滚动面板的默认行为是根据需要获取水平/或垂直滚动条。

该类有两个构造函数：

- `ScrollPane()`: 创建一个滚动条策略为“按需”的滚动面板容器。
- `ScrollPane(int scrollDisplayPolicy)`: 创建一个具有指定滚动条行为的新滚动面板。滚动面板的显示策略应该是以下之一：
    - `ScrollPane.SCROLLBARS_AS_NEEDED`（默认）
    - `ScrollPane.SCROLLBARS_ALWAYS`
    - `ScrollPane.SCROLLBARS_NEVER`

下面列出的代码创建了一个具有默认（`As_NEEDED`）滚动条行为的滚动面板。该滚动面板包含一个巨大的按钮；因此肯定需要滚动条。

#### 示例 17.21

```java
import java.awt.*;

class SPaneTest {
    public static void main(String args[]) {
        Frame f = new Frame();
        f.setLayout(new GridLayout(1, 2));
        f.setSize(250, 150);
        ScrollPane spane = new ScrollPane();
        spane.setBackground(Color.green);
        f.add(spane);
        f.add(new TextArea());
        Button b1 = new Button("Push Me !");
        b1.setFont(new Font("Serif", Font.ITALIC, 100));
        spane.add(b1);
        f.setVisible(true);
    }
}
```

输出: ![](img/image01289.jpeg)

### Scrollbar

调整列表和滚动面板的 `Scrollbar` 组件可以作为一个独立的组件使用。有三个构造函数：

- `Scrollbar()`: 构建一个新的垂直滚动条。
- `Scrollbar(int orientation)`: 构建一个具有指定方向的新滚动条。
- `Scrollbar(int orientation, int initialValue, int sliderSize, int minValue, int maxValue)`: 构建一个具有指定方向、初始值、滑块大小以及最小值和最大值的新滚动条。`sliderSize` 参数控制滑块的大小，但不是以像素为单位。

对于接受方向参数的构造函数，该值应该是以下之一：

- `Scrollbar.HORIZONTAL`
- `Scrollbar.VERTICAL`

#### 示例 17.2

```java
import java.applet.*;
import java.awt.*;
import java.awt.event.*;

class RGB extends Applet implements AdjustmentListener {
    TextField tf1;
    Scrollbar sb1, sb2, sb3;

    public void init() {
        setLayout(new GridLayout(4, 1));
        sb1 = new Scrollbar(Scrollbar.HORIZONTAL, 0, 10, 0, 255);
        sb2 = new Scrollbar(Scrollbar.HORIZONTAL, 0, 10, 0, 255);
        sb3 = new Scrollbar(Scrollbar.HORIZONTAL, 0, 10, 0, 255);
        sb1.addAdjustmentListener(this);
        sb2.addAdjustmentListener(this);
        sb3.addAdjustmentListener(this);
        tf1 = new TextField(8);
        add(tf1);
        add(sb1);
        add(sb2);
        add(sb3);
    }

    public void adjustmentValueChanged(AdjustmentEvent ae) {
        int a = 0, b = 0, c = 0;
        a = sb1.getValue();
        b = sb2.getValue();
        c = sb3.getValue();
        Color c1 = new Color(a, b, c);
    }
}
```

```java
tf1.setBackground(c1);
}
}
```

![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg)

![STAR-LOGO-2013](img/image01213.jpeg)

# 第 18 章

## AWT 事件简介

### 序言

当一个普通的 Java 程序（非 GUI 的）需要输入时，它会提示用户并调用某些输入方法，例如 `readline()`，也就是说交互是由程序发起的。这并不是基于 GUI 的程序的行为方式。是由用户发起与程序的交互，而不是由程序发起动作。

例如，在文字处理软件中，用户通过点击不同的按钮来启动动作，这产生一个事件并执行某些代码，相应地发生某些操作。点击保存按钮将调用将内容保存到文件的方法。

| 接口 | 事件(方法) | 类 | 方法 |
| :--- | :--- | :--- | :--- |
| `ActionListener` | `actionPerformed()` | `ActionEvent ae` | `getSource` |
| `ItemListener` | `itemStateChanged()` | `ItemEvent ie` | `getItem` |



| `AdjustmentListener` | `adjustmentValueChanged()` | `AdjustmentEvent ae` | `getAdjustable()` |
|---|---|---|---|
| `MouseListener` / `MouseAdapter` | `mouseEntered()` / `mouseExited()` / `mouseClicked()` / `mousePressed()` / `mouseReleased()` | `MouseEvent me` | `getX()` / `getY()` / `getPoint()` / `getClickCount()` / `getButton()` / `getModifiersEx()` / `getModifiersExText()` |
| `MouseMotionListener` / `MouseMotionAdapter` | `mouseMoved()` / `mouseDragged()` | `MouseEvent me` | 同上 |
| `KeyListener` / `KeyAdapter` | `keyTyped()` / `keyPressed()` / `keyReleased()` | `KeyEvent ke` | `getKeyChar()` / `getKeyCode()` |
| `FocusListener` / `FocusAdapter` | `focusGained()` / `focusLost()` | `FocusEvent fe` | `getSource()` |
| `WindowListener` / `WindowAdapter` | `windowOpened()` / `windowClosing()` / `windowClosed()` / `windowActivated()` / `windowDeactivated()` / `windowIconified()` / `windowDeiconified()` | `WindowEvent we` | `getWindow()` |

Java 使用事件委托模型进行事件处理。在事件委托模型中，可以告诉组件，当组件产生特定类型的事件时，应该通知哪个对象。

如果组件对某种类型的事件不感兴趣，那么该类型的事件将不会被传播。委托模型基于以下核心概念：

*   事件类（Event classes）。
*   事件监听器（Event listeners）。
*   适配器（Adapters）。

### 事件类

点击按钮会产生一个事件。该事件关联有许多信息，例如：时间、产生事件的组件、发生点击点的坐标等。

这些信息被放在一个事件类中。这个概念与异常处理类似。每当发生异常时，都会创建一个相应异常类的对象并将所有异常相关信息放入此对象中。

我们拥有事件类的层次结构，这与异常类的层次结构有些相似。每当发生某些事件时，会被事件处理机制检测到，该机制创建相应事件类的对象并将所有事件相关信息放入其中。

### 事件监听器

事件监听器负责在事件发生时采取适当的动作。事件监听器是一个对象，组件将处理特定类型事件的任务委托给了该对象。

当组件接收输入时，会构造一个相应类型的事件，然后该事件作为参数传递给监听器的方法调用。监听器必须实现包含该事件处理方法的接口。

我们可以将事件监听器与处理异常的 `catch` 块进行比较。我们需要提供一个与要处理的异常相对应的 `catch` 块。同样，如果我们想处理由某个组件生成的事件，我们需要提供相应的监听器。

监听器与组件相关联。不同的事件有不同的监听器。当事件发生时，会调用相应的监听器方法，并将事件对象作为参数传递。

### 适配器

在语言中定义的监听器只是接口。我们需要提供相应监听器的实现。某些监听器具有 2 个或更多方法。

为了实现一个具有多个方法的监听器，即使我们只对一个方法感兴趣，也需要提供所有方法的实现。适配器类为这个问题提供了解决方案。

适配器类提供了监听器所有方法的空实现（dummy implementation）。这有助于减少编程工作。如果我们只想使用包含 5 个方法的监听器类中的一个方法，只需简单的扩展适配器类并重写所需的方法。

### 事件层次结构

AWT 拥有定义良好的事件层次结构。通常，事件层次结构中叶子节点对应的类代表实际事件。而非叶子节点的类则作为基类并封装。

AWT 事件层次结构在图中所示。

![](img/image01290.jpeg)

#### `java.util.EventObject` 类

这是所有事件类的顶层父类。它是一个非常通用的类，有一个感兴趣的方法，返回产生事件的对象。

```java
Object getSource()
```

#### `java.awt.AWTEvent` 类

`EventObject` 的一个子类是 `java.awt.AWTEvent`，它是所有事件的父类。同样，只有一个感兴趣的方法，返回事件的 ID。

```java
int getID()
```

事件的 ID 是一个指定确切性质的 int。例如，`MouseEvent` 类的实例可以表示七种情况之一：点击、拖拽、进入、退出、按下、释放。这些可能性都通过 `MouseEvent.MOUSE_CLICKED`、`MouseEvent.DRAGGED` 等整数表示。

`java.awt.AWTEvent` 的子类代表组件生成的各种事件类型，包含了与触发活动相关的所有信息。

非超类的事件类型（即实际由组件触发的类型）包括：

1.  `ActionEvent`：组件激活时产生，例如点击按钮、双击列表项以及在 `TextField` 中按回车产生。
2.  `AdjustmentEvent`：可调节组件（如滚动条）调整时产生。
3.  `ContainerEvent`：组件添加到或从容器中移除时产生。
4.  `FocusEvent`：组件接收或失去输入焦点时产生。
5.  `ItemEvent`：从列表、选择框或复选框选择项目时产生。
6.  `KeyEvent`：键盘活动产生。
7.  `MouseEvent`：鼠标活动产生。
8.  `MouseWheelEvent`：指示在组件中旋转鼠标轮的事件。
9.  `WindowEvent`：窗口活动产生（如最小化或恢复最大化等）。
10. `TextEvent`：文本组件被修改时产生。

#### `java.awt.event` 包

该包提供了用于处理 AWT 组件触发的不同类型事件的接口和类。事件由事件源触发。事件监听器向事件源注册以接收特定类型事件的通知。

该包定义了事件和事件监听器，以及事件监听器适配器，后者是简化编写事件监听器的便利类。

### 事件监听器接口

每个事件类都有对应的监听器接口并定义了一个或多个方法。常用的监听器接口将在后续章节中描述。

#### ActionListener 接口

这是用于接收动作事件的监听器接口。感兴趣处理动作事件的类实现此接口，并使用该类创建的对象通过组件的 `addActionListener()` 方法注册到组件中。当动作事件发生时，将调用动作监听器的 `actionPerformed()` 方法，其方法签名如下：

| 方法 | 描述 |
| :--- | :--- |
| `void actionPerformed(ActionEvent e)` | 当动作发生时调用。 |

#### AdjustmentListener 接口

这是用于接收调整事件的监听器接口。

| 方法 | 描述 |
| :--- | :--- |
| `void adjustmentValueChanged(AdjustmentEvent e)` | 当滑块/滑动条的值改变时调用。 |

#### ContainerListener 接口

这是用于接收组件添加到容器或从容器中移除时的事件的监听器接口。

| 方法 | 描述 |
| :--- | :--- |
| `void componentAdded(ContainerEvent e)` | 当组件添加到容器时调用。 |
| `void componentRemoved(ContainerEvent e)` | 当组件从容器中移除时调用。 |

#### FocusListener 接口

这是用于接收组件获得或失去焦点的事件的监听器接口。

| 方法 | 描述 |
| :--- | :--- |
| `void focusGained(FocusEvent e)` | 当组件获得键盘焦点时调用。 |
| `void focusLost(FocusEvent e)` | 当组件失去键盘焦点时调用。 |

#### ItemListener 接口

这是用于接收项目状态事件的监听器接口。

| 方法 | 描述 |
| :--- | :--- |
| `void itemStateChanged(ItemEvent e)` | 当用户选中或取消选择某项时调用。 |

#### KeyListener 接口

这是用于接收键盘事件（按键输入）的监听器接口。

| 方法 | 描述 |
| :--- | :--- |
| `void keyPressed(KeyEvent e)` | 当按键被按下时调用。 |
| `void keyReleased(KeyEvent e)` | 当按键被释放时调用。 |
| `void keyTyped(KeyEvent e)` | 当输入按键（按下并释放）时调用。 |

#### MouseListener 接口

这是用于接收组件上鼠标事件（按下、释放、点击、进入、和退出）的监听器接口。

| 方法 | 描述 |
| :--- | :--- |
| `void mouseClicked(MouseEvent e)` | 当在 `Component` 上点击鼠标按钮（按下并释放）时调用。 |
| `void mouseEntered(MouseEvent e)` | 当鼠标进入组件时调用。 |
| `void mouseExited(MouseEvent e)` | 当鼠标离开组件时调用。 |
| `void mousePressed(MouseEvent e)` | 当在组件上按下鼠标按钮时调用。 |
| `void mouseReleased(MouseEvent e)` | 当在组件上释放鼠标按钮时调用。 |

#### MouseMotionListener 接口

这是用于接收组件上鼠标移动量事件（移动和拖拽）的监听器接口。

| 方法 | 描述 |
| :--- | :--- |
| `void mouseDragged(MouseEvent e)` | 当在组件上按下鼠标按钮并拖动时调用。 |
| `void mouseMoved(MouseEvent e)` | 当鼠标光标在组件上移动但未按下任何按钮时调用。 |

#### MouseWheelListener 接口

这是用于接收组件上鼠标滚轮事件的监听器接口。

| 方法 | 描述 |
| :--- | :--- |
| `void mouseWheelMoved(MouseWheelEvent e)` | 当旋转鼠标滚轮时调用。 |

#### WindowListener 接口

当窗口的状态由于打开、关闭、激活或取消激活、最小化或恢复正常而改变时，会调用监听器对象中的相关方法，并将 `WindowEvent` 传递给它。

| 方法 | 描述 |
| :--- | :--- |
| `void windowActivated(WindowEvent e)` | 当窗口被设置为活动窗口时调用。 |
| `void windowClosed(WindowEvent e)` | 当由于对窗口调用 `dispose()` 导致窗口关闭时调用。 |
| `void windowClosing(WindowEvent e)` | 当用户尝试从窗口系统菜单关闭窗口时调用。 |
| `void windowDeactivated(WindowEvent e)` | 当窗口不再是活动窗口时调用。 |
| `void windowDeiconified(WindowEvent e)` | 当窗口从最小化恢复到正常状态时调用。 |
| `void windowIconified(WindowEvent e)` | 当窗口从正常状态变为最小化状态时调用。 |
| `void windowOpened(WindowEvent e)` | 当窗口第一次变为可见时调用。 |

### 处理事件

以下示例解释了如何处理点击按钮产生的 `ActionEvent` 事件。

#### Example 18.1

```java
import java.awt.*;
import java.awt.event.*;

class A1 {
    public static void main(String args[]) {
        Frame f = new Frame();
        f.setLayout(new FlowLayout());
        f.setSize(500, 100);
        Button b1 = new Button("Push me");
        Button b2 = new Button("Click me");
        b1.addActionListener(new B());
        b2.addActionListener(new C());
        f.add(b1);
        f.add(b2);
        f.setVisible(true);
    }
}

class B implements ActionListener {
    public void actionPerformed(ActionEvent ae) {
        System.out.println("Button Pushed");
    }
}

class C implements ActionListener {
    public void actionPerformed(ActionEvent ae) {
        System.out.println("Button Clicked");
    }
}
```

输出：

![](img/image01291.jpeg)

#### Example 18.2

```java
import java.awt.*;
import java.awt.event.*;

class A2 implements ActionListener {
    static Button b1 = null, b2 = null;

    public static void main(String args[]) {
        Frame f = new Frame();
        f.setLayout(new FlowLayout());
        f.setSize(500, 100);
        b1 = new Button("Push me");
        b2 = new Button("Click me");
        b1.addActionListener(new A2());
        b2.addActionListener(new A2());
        f.add(b1);
        f.add(b2);
        f.setVisible(true);
    }

    public void actionPerformed(ActionEvent ae) {
        if (ae.getSource() == b1)
            System.out.println("Button Pushed");
        else
            System.out.println("Button Clicked");
    }
}
```

#### Example 18.3

输出：与上例相同。

```java
import java.awt.*;
import java.awt.event.*;

class A3 implements ActionListener {
    Button b1 = null, b2 = null;

    A3() {
        Frame f = new Frame();
        f.setLayout(new FlowLayout());
        f.setSize(500, 100);
        b1 = new Button("Push me");
        b2 = new Button("Click me");
        b1.addActionListener(this);
        b2.addActionListener(this);
        f.add(b1);
        f.add(b2);
        f.setVisible(true);
    }

    public static void main(String args[]) {
        new A3();
    }

    public void actionPerformed(ActionEvent ae) {
        if (ae.getSource() == b1)
            System.out.println("Button Pushed");
        else
            System.out.println("Button Clicked");
    }
}
```

#### Example 18.4



```java
import java.awt.*;
import java.awt.event.*;
class A4 implements ActionListener {
    static Button b1=null,b2=null;
    static TextField tf1=null,tf2=null, tf3=null;
    public static void main(String args[]) {
        Frame f=new Frame();
        f.setLayout(new GridLayout(4,2));
        f.setSize(500,300);
        Label l1 = new Label("No1.");
        Label l2 = new Label("No2.");
        Label l3 = new Label("Result");
        tf1 = new TextField();
        tf2 = new TextField();
        tf3 = new TextField();
        b1=new Button("Sum");
        b2=new Button("Avg");
        b1.addActionListener(new A4());
        b2.addActionListener(new A4());
        f.add(l1);f.add(tf1);
        f.add(l2);f.add(tf2);
        f.add(l3);f.add(tf3);
        f.add(b1);f.add(b2);
        f.setVisible(true);
    }
    public void actionPerformed(ActionEvent ae) {
        int a,b,c;
        float av;
        a=Integer.parseInt(tf1.getText());
        b=Integer.parseInt(tf2.getText());
        if(ae.getSource() == b1)
            tf3.setText("" +(a+b));
        else
            tf3.setText("" + (a+b)/2);
    }
}
```

注意：一个组件可以关联多个监听器，无法保证监听器接收通知的顺序与添加的顺序一致。同样，无法保证所有通知都在同一个线程中发生，因此，监听器必须防止损坏共享数据。可以通过调用 `removeListener()` 方法并传入要移除的监听器从组件的监听器列表中移除监听器。例如，代码通过 `btn.removeActionListener(al)` 从按钮中移除监听器 `al`。

## 处理事件

### Example 18.5

```java
import java.awt.*;
import java.awt.event.*;
class A5 {
    public static void main(String args[]) {
        Frame f= new Frame();
        f.setLayout(new FlowLayout());
        f.setSize(300,300);
        f.addWindowListener(new B( ));
        f.setVisible(true);
    }
}
class B implements WindowListener {
    public void windowOpened(WindowEvent we) {
        System.out.println("Window Opened");
    }
    public void windowActivated(WindowEvent we) {
        System.out.println("Window Activated");
    }
    public void windowDeactivated(WindowEvent we) {
        System.out.println("window Deactivated");
    }
    public void windowClosing(WindowEvent we) {
        System.out.println("Window Closing");
        Frame f = (Frame) we.getWindow();
        f.dispose();
    }
    public void windowClosed(WindowEvent we) {
        System.out.println("Window Closed");
    }
    public void windowIconified(WindowEvent we) {
        System.out.println("Window Iconified");
    }
    public void windowDeiconified(WindowEvent we) {
        System.out.println("Window Deiconified");
    }
}
```

### 适配器 (Adapters)

某些事件监听器接口包含多个方法。最大的接口 `WindowListener` 有七个方法。假设我们要捕获 `windowClosing()` 事件，以便执行关闭窗口的代码。虽然我们在实现 `WindowListener` 的类中只需要 `windowClosing()` 一个方法，但我们必须为所有方法提供空实现（dummy implementation）。

`java.awt.event` 包提供了几个适配器类，每个适配器都对应一个定义了多个单一方法的监听器接口。

适配器（Adapter）简单来说就是一个通过提供空方法来实现接口的类。例如，`WindowAdapter` 类实现了 `WindowListener` 接口，并包含了七个空方法。

### 适配器类及其接口

| 适配器类 | 监听器接口 |
| :--- | :--- |
| `ContainerAdapter` | `ContainerListener` |
| `FocusAdapter` | `FocusListener` |
| `KeyAdapter` | `KeyListener` |
| `MouseAdapter` | `MouseListener` |
| `MouseMotionAdapter` | `MouseMotionListener` |
| `WindowAdapter` | `WindowListener` |

### 示例 18.6 WindowAdapter 类的用法。

```java
import java.awt.*;
import java.awt.event.*;

class A6 {
    public static void main (String args[]) {
        Frame f = new Frame();
        f.setLayout(new FlowLayout());
        f.setSize(300,300);
        f.addWindowListener(new B( ));
        f.setVisible(true);
    }
}

class B extends WindowAdapter {
    public void windowClosing(WindowEvent we) {
        System.out.print("Window Closing");
        Frame f = (Frame) we.getWindow();
        f.dispose();
    }
}
```

### InputEvent 类

这是组件级输入事件的根事件类。输入事件在由产生源进行正常处理之前，会被派送给监听器。这允许监听器和子类“消耗”事件，使得源不会以默认方式处理这些事件。例如，在 `Button` 组件上消耗鼠标事件将防止 `Button` 被激活。

### 方法

- `void consume()`: 消耗此事件，使其由产生源以默认方式处理。
- `int getModifiers()`: 返回此事件的修饰符掩码（Modifier mask）。
- `int getModifiersEx()`: 返回此事件的扩展修饰掩码。
- `static String getModifiersExText(int modifiers)`: 返回描述扩展修饰键的字符串，例如“shift”、“Ctrl + Shift”等。
- `long getWhen()`: 返回事件发生的时间戳。
- `boolean isAltDown()`: 返回此事件发生时 Alt 修饰符是否被按下。
- `boolean isConsumed()`: 返回此事件是否已被消耗。
- `boolean isControlDown()`: 返回此事件发生时 Control 修饰符是否被按下。
- `boolean isShiftDown()`: 返回此事件发生时 Shift 修饰符是否被按下。

### Mouse Event

这是 `Event` 类的子类。该事件表示组件中发生了鼠标操作。当且仅当光标位于组件子的未遮挡部分或顶层窗口时，才认为鼠标操作发生在特定组件中。此事件用于鼠标事件（点击、按下、释放）和移动事件（移动和拖拽）。

### 方法

- `int getButton()`: 返回哪个鼠标按钮状态发生了变化（如果有）。
- `int getClickCount()`: 返回与此事件相关的鼠标点击次数。
- `static String getModifiersText(int modifiers)`: 返回描述事件发生期间按下的修饰键的字符串，例如“Shift”或“Ctrl + shift”。
- `Point getPoint()`: 返回事件相对于源组件的 x, y 位置。
- `int getX()`: 返回事件相对于源组件的水平 x 位置。
- `int getY()`: 返回事件相对于源组件的垂直 y 位置。
- `boolean isPopupTrigger()`: 返回此鼠标事件是否为该平台的弹出菜单触发事件。

**注意：** 弹出菜单在不同系统上的触发方式不同。因此，为了实现良好的跨平台功能，应该在 `mousePressed` 和 `mouseReleased` 中都检查 `isPopupTrigger()`。

### 处理鼠标事件：示例 18.7

```java
import java.awt.*;
import java.awt.event.*;

class A7 {
    public static void main(String args[]) {
        Frame f = new Frame();
        f.setLayout(new FlowLayout());
        f.setSize(300,30);
        Button b1 = new Button("Push Me");
        b1.addMouseListener(new B());
        b1.addMouseMotionListener(new C());
        b1.addActionListener(new D());
        f.add(b1);
        f.setVisible(true);
    }
}

class B implements MouseListener {
    public void mouseEntered(MouseEvent me) {
        System.out.println("Mouse Entered...");
        System.out.println(me.getX());
        System.out.println(me.getY());
    }

    public void mouseExited(MouseEvent me) {
        System.out.println("Mouse Exited...");
        Point p1 = me.getPoint();
        System.out.println(p1.x);
        System.out.println(p1.y);
    }

    public void mousePressed(MouseEvent me) {
        System.out.println("Mouse pressed...");
        int ms = me.getModifiersEx();
        String s = me.getModifiersText(ms);
        System.out.println(s);
    }

    public void mouseReleased(MouseEvent me) {
        System.out.println("Mouse Released...");
        System.out.println("ClickCount-->" + me.getClickCount());
    }

    public void mouseClicked(MouseEvent me) {
        System.out.println("Mouse Clicked...");
        System.out.println("Button-->"+me.getButton());
    }
}

class C implements MouseMotionListener {
    public void mouseMoved(MouseEvent me) {
        System.out.println("Mouse Moved...");
    }
    public void mouseDragged(MouseEvent me) {
        System.out.println("Mouse Dragged...");
    }
}

class D implements ActionListener {
    public void actionPerformed(ActionEvent ae) {
        System.out.println ("Button Pressed...");
    }
}
```

### ActionEvent 类

这是一种语义化事件，表示发生了组件动作。这种高层事件在特定动作发生（如被按下）时，由组件（如 `Button`）生成。该事件通过组件的 `addActionListener` 方法传递给每个注册用于接收此类事件的 `ActionListener` 对象。当事件发生时，实现 `ActionListener` 接口的对象将获取此事件。监听器无需处理处理个别鼠标移动和点击的细节，转而处理诸如“按钮被按下”等“有意义的”（语义）事件。

注意：使用键盘在 `Button` 上触发 `ActionEvent`，请使用空格键。

#### ActionEvent 的方法：

- `String getAction()`：返回与此动作关联的命令字符串。
- `int getModifiers()`：返回动作事件期间期间按的修饰键。
- `long getWhen()`：返回事件发生的时间戳。

### 示例 18.8

此示例说明了如何识别在 `ActionEvent` 发生时有效的按修饰符。



```java
import java.awt.*;
import java.awt.event.*;
public class KeyModifierDemo extends Frame implements ActionListener
{
    Button b;
    KeyModifierDemo ()
    {
        b = new Button ("Button");
        b.addActionListener (this);
        setLayout (new FlowLayout ( ) );
        add (b);
        setBounds (100,0,20,20);
        setVisible (true);
    }
    public static void main (String args[])
    {
        new KeyModifierDemo ();
    }
    public void actionPerformed (ActionEvent ae )
    {
        System.out.println ("Button Pressed");
        int ms = ae.getModifiers ();
        if (ms & InputEvent.CTRL_DOWN_MASK)!=0)
        {
            System.out.println ("CTRL key was pressed");
        }
        if (ms & InputEvent.SHIFT_DOWN_MASK)!=0)
        {
            System.out.println ("Shift Key was pressed");
        }
        if (ms & InputEvent.ALT_DOWN_MASK)!=0)
        {
            System.out.println ("ALT key was pressed");
        }
    }
}
```

### 处理多个 Action 命令

Action 事件是最简单的。当我们发现滚动条发送了调整事件时，显而易的问题是：“现在滚动条的值是多少？”。当我们发现鼠标被点击时，自然会想知道：“鼠标的 x 和 y 坐标是什么？”但当我们发现一个按钮发送了 `ActionEvent` 时，似乎没有额外的信息需要寻找；按钮已经通过点击了，这似乎就是全部的已知信息。

然而，`ActionEvent` 还关联着一个额外信息。这条信息是一个字符串，被称为 Action 命令（Action command）。我们可以通过 `getActionCommand()` 方法提取 `ActionEvent` 的 Action 命令。如果 `ActionEvent` 是由文本字段发送的，`getActionCommand()` 返回文本字段当前的内容（用户输入回车键时文本字段会发送 `ActionEvent`）。如果 `ActionEvent` 是由按钮发送的，默认行为是 `getActionCommand()` 返回按钮的标签字符串。然而，我们可以通过调用 `setActionCommand(String)` 方法显式地设置按钮的 `ActionCommand`。

```java
Button btn = new Button ("Hello");
btn.setActionCommand ("Hello");
```

当按钮的 `ActionListener` 需要决定如何响应 `ActionEvent` 时，按钮 Action 命令的优势就显而易见了。单个监听器作为多个组件的监听器是常见的；在我们的语境下，一个对象可能是多个或按钮的 `ActionListener`。在这种情况下，对象的 `actionPerformed()` 方法必须开始判断哪个按钮被命中了。以下示例演示了这一点：

### 示例 18.9

```java
import java.awt.*;
import java.awt.event.*;
class ButtonTest
{
    Button b1,b2,b3;
    ButtonTest()
    {
        Frame f=new Frame();
        f.setLayout(new FlowLayout ( ) );
        f.setSize(300,300);
        b1=new Button("Push Me");
        b2=new Button("Click Me");
        b3=new Button("Hit Me");
        f.add(b1); f.add(b2); f.add(b3);
        B obj= new B(b1,b2,b3);
        b1.addActionListener(obj);
        b2.addActionListener(obj);
        b3.addActionListener(obj);
        f.setVisible(true);
    }
    public static void main (String args[])
    {
        new ButtonTest();
    }
}
class B implements ActionListener
{
    Button b4,b5,b6;
    B(Button b1, Button b2, Button b3)
    {
        b4 = b1;
        b5 = b2;
        b6 = b3;
    }
    public void actionPerformed(ActionEvent ae)
    {
        Button b = (Button)ae.getSource();
        if (b == b4)
            System.out.println("First Button was pressed");
        else if (b == b5)
            System.out.println("Second Button was pressed");
        else if (b == b6)
            System.out.println("Third Button  was pressed");
    }
}
```

### 示例 18.10

```java
import java.awt.*;
import java.awt.event.*;

class GetLabelTest {
    Button b1, b2, b3;

    GetLabelTest() {
        Frame f = new Frame();
        f.setLayout(new FlowLayout());
        f.setSize(300, 300);
        b1 = new Button("Push Me");
        b2 = new Button("Click Me");
        b3 = new Button("Hit Me");
        f.add(b1);
        f.add(b2);
        f.add(b3);
        B obj = new B();
        b1.addActionListener(obj);
        b2.addActionListener(obj);
        b3.addActionListener(obj);
        f.setVisible(true);
    }

    public static void main(String args[]) {
        new GetLabelTest();
    }
}

class B implements ActionListener {
    public void actionPerformed(ActionEvent ae) {
        Button b = (Button)ae.getSource();
        String s = b.getLabel();
        if (s.equals("Push Me"))
            System.out.println("First Push Me Button was pressed");
        else if (s.equals("Click Me"))
            System.out.println("Second Push Me Button was pressed");
        else if (s.equals("Hit Me"))
            System.out.println("Third Push Me Button was pressed");
    }
}
```

### 示例 18.1: 使用 setActionCommand() 设置命令

```java
import java.awt.*;
import java.awt.event.*;

class ActionCommandTest {
    Button b1, b2, b3;

    ActionCommandTest() {
        Frame f = new Frame();
        f.setLayout(new FlowLayout());
        f.setSize(300, 300);
        b1 = new Button("Push Me");
        b2 = new Button("Push Me");
        b3 = new Button("Push Me");
        b1.setActionCommand("First");
        b2.setActionCommand("Second");
        b3.setActionCommand("Third");
        f.add(b1);
        f.add(b2);
        f.add(b3);
        B obj = new B();
        b1.addActionListener(obj);
        b2.addActionListener(obj);
        b3.addActionListener(obj);
        f.setVisible(true);
    }

    public static void main(String args[]) {
        new ActionCommandTest();
    }
}

class B implements ActionListener {
    public void actionPerformed(ActionEvent ae) {
        Button b = (Button)ae.getSource();
        String s = b.getActionCommand();
        if (s.equals("First"))
            System.out.println("First Push Me Button was pressed");
        else if (s.equals("Second"))
            System.out.println("Second Push Me Button was pressed");
        else if (s.equals("Third"))
            System.out.println("Third Push Me Button was pressed");
    }
}
```

### 处理按键事件

```java
import java.awt.*;
import java.awt.event.*;

class KeyTest extends Frame implements KeyListener {
    String msg = "";
    int x = 50, y = 10;

    public static void main(String args[]) {
        KeyTest f = new KeyTest();
        f.setSize(300, 300);
        f.addKeyListener(f);
        f.setVisible(true);
    }

    public void keyReleased(KeyEvent ke) {
        System.out.println("Key Up...");
    }

    public void keyTyped(KeyEvent ke) {
        System.out.println("Key Typed...");
        msg = msg + ke.getKeyChar();
        repaint();
    }

    public void keyPressed(KeyEvent ke) {
        System.out.println("Key Pressed...");
        int key = ke.getKeyCode();
        switch(key) {
            case KeyEvent.VK_F1:
                msg = msg + "<F1>";
                break;
            case KeyEvent.VK_F2:
                msg = msg + "<F2>";
                break;
            case KeyEvent.VK_F3:
                msg = msg + "<F3>";
                break;
            case KeyEvent.VK_PAGE_DOWN:
                msg = msg + "<PgDn>";
                break;
            case KeyEvent.VK_PAGE_UP:
                msg = msg + "<PgUp>";
                break;
            case KeyEvent.VK_LEFT:
                msg = msg + "<Left Arrow>";
                break;
            case KeyEvent.VK_RIGHT:
                msg = msg + "<Right Arrow>";
                break;
            case KeyEvent.VK_CONTROL:
                msg = msg + "<Ctrl>";
                break;
        }
        repaint();
    }
    public void paint(Graphics g) {
        g.setColor(Color.red);
        g.drawString(msg,x,y);
    }
}
```

### 示例 18.13: FocusListener 演示 TextField 在失去或获得焦点时颜色的变化

```java
import java.awt.*;
import java.awt.event.*;
class FocusTest extends Frame implements FocusListener {
    static TextField tf1,tf2;
    public static void main(String args[]) {
        FocusTest f = new FocusTest();
        f.setLayout(new FlowLayout());
        tf1 = new TextField(8);
        tf1.setBackground(Color.blue);
        tf1.addFocusListener(f);
        tf2 = new TextField(8);
        tf2.setBackground(Color.blue);
        tf2.addFocusListener(f);
        f.add(tf1);
        f.add(tf2);
        f.setSize(300, 200);
        f.setVisible(true);
    }
    public void focusGained(FocusEvent fe) {
        TextField tf = (TextField)fe.getSource();
        tf.setBackground(Color.red);
    }
    public void focusLost(FocusEvent fe) {
        TextField tf = (TextField)fe.getSource();
        tf.setBackground(Color.blue);
    }
}
```

### 示例 18.14: requestFocus() 演示

我们不能在同一个类中使用 `WindowListener`，因此我们定义了两个类，一个用于 frame，另一个用于 `WindowListener`。



```java
import java.awt.*;
import java.awt.event.*;
class A extends Frame implements ActionListener {
    static TextField tf1,tf2;
    static Button b1;
    public static void main(String args[]) {
        A f = new A();
        f.setLayout(new FlowLayout());
        f.addWindowListener(new B());
        tf1 = new TextField(8);
        tf2 = new TextField(8);
        b1 = new Button("Set");
        b1.addActionListener(f);
        f.add(tf1);
        f.add(tf2);
        f.add(b1);
        f.setSize(200,200);
        f.setVisible(true);
    }
    public void actionPerformed(ActionEvent ae) {
        tf2.requestFocus();
    }
}
class B extends WindowAdapter {
    public void windowClosing(WindowEvent we) {
        Frame f = (Frame)we.getWindow();
        f.dispose();
    }
}
```

### 示例 18.15 显示对话框

```java
import java.awt.*;
class DialogTest {
    public static void main(String args[]) throws InterruptedException {
        Frame f1 = new Frame();
        f1.setSize(300,300);
        f1.setVisible(true);
        Dialog d1 = new Dialog(f1);
        d1.setSize(10,10);
        d1.setVisible(true);
        Thread.sleep(300);
        d1.dispose();
    }
}
```

### 示例 18.16 菜单栏演示

```java
import java.awt.*;
import java.awt.event.*;
class MyMenu extends Frame implements WindowListener, ItemListener {
    TextField tf1;
    String msg="";
    CheckboxMenuItem item4;
    MyMenu() {
        super("Matrix");
        setLayout(new FlowLayout());
        tf1 = new TextField(8);
        add(tf1);
        MenuBar mbar = new MenuBar();
        Menu file = new Menu("File");
        MenuItem item1 = new MenuItem("New...");
        item1.addActionListener(this);
        file.add(item1);
        MenuItem item2 = new MenuItem("Open...");
        item2.addActionListener(this);
        file.add(item2);
        Menu sub = new Menu("Sub Menu");
        MenuItem item3 = new MenuItem("Option1");
        sub.add(item3);
        file.add(sub);
        item4 = new CheckboxMenuItem("TextBox",true);
        item4.addItemListener(this);
        file.add(item4);
        mbar.add(file);
        addWindowListener(this);
        setMenuBar(mbar);
        setSize(400,400);
        setVisible(true);
    }
    public void paint(Graphics g) {
        g.drawString(msg,150,250);
    }
    public void actionPerformed(ActionEvent ae) {
        String s=(String)ae.getActionCommand();
        if(s.equals("New")) {
            tf1.setText("New Selected");
            msg="New Selected";
        } else if(s.equals("Open")) {
            tf1.setText("Open Selected");
            msg="Open Selected";
        }
        repaint();
    }
    public void windowClosing(WindowEvent we) {
        Frame f = (Frame)we.getWindow();
        f.dispose();
    }
    public void windowClosed(WindowEvent we){}
    public void windowActivated(WindowEvent we){}
    public void windowDeactivated(WindowEvent we){}
    public void windowIconified(WindowEvent we){}
    public void windowDeiconified(WindowEvent we){}
    public void windowOpened(WindowEvent we){}
    public void itemStateChanged(ItemEvent ie) {
        tf1.setVisible(ie.getStateChange() == ItemEvent.SELECTED);
    }
    public static void main(String args[]) {
        new MyMenu();
    }
}
```

### Listbox 演示

```java
import java.awt.*;
import java.awt.event.*;
class ListTest extends Frame implements ActionListener {
    static List l1,l2;
    public static void main(String args[]) {
        ListTest f = new ListTest();
        f.setLayout(new FlowLayout());
        l1 = new List(3,true);
        l1.add("India");
        l1.add("Pakistan");
        l1.add("USA");
        l1.add("UK");
        l1.add("China");
        l2 = new List(3,true);
        Button b1 = new Button("Transfer");
        b1.addActionListener(f);
        f.add(l1);
        f.add(l2);
        f.add(b1);
        f.setSize(200,200);
        f.setVisible(true);
    }
    public void actionPerformed(ActionEvent ae) {
        String s1[] = l1.getSelectedItems();
        for(int i=0;i<s1.length;i++) {
            l2.add(s1[i]);
            l1.remove(s1[i]);
        }
    }
}
```

### 使用 frame 计算两个数之和

```java
import java.awt.*;
import java.awt.event.*;
class Sum implements ActionListener {
    static Button b1,b2;
    static TextField tf1,tf2,tf3;
    static Frame f;
    public static void main(String args[]) {
        f = new Frame();
        Sum s1 = new Sum();
        f.setLayout(new GridLayout(4,2));
        Label l1 = new Label("Enter No. 1:");
        tf1 = new TextField(8);
        Label l2 = new Label("Enter No. 2:");
        tf2 = new TextField(8);
        Label l3 = new Label("Result :");
        tf3 = new TextField(8);
        b1 = new Button("Sum");
        b2 = new Button("Close");
        b1.addActionListener(s1);
        b2.addActionListener(s1);
        f.add(l1);
        f.add(tf1);
        f.add(l2);
        f.add(tf2);
        f.add(l3);
        f.add(tf3);
        f.add(b1);
        f.add(b2);
        f.setSize(300,200);
        f.setVisible(true);
    }
    public void actionPerformed(ActionEvent ae) {
        Button b=(Button)ae.getSource();
        if(b==b1) {
            int n1=Integer.parseInt(tf1.getText());
            int n2=Integer.parseInt(tf2.getText());
            tf3.setText(String.valueOf(n1+n2));
        }
        if(b == b2) {
            f.dispose();
        }
    }
}
```

## 示例 18.19 在 Applet 上显示图像

```java
import java.awt.*;
import java.net.*;
import java.applet.*;
/*<applet code="ScrollPane" width=300 height=200></applet>*/
public class ScrollPane extends Applet {
    Image img1;
    URL file1;
    public void init() {
        try {
            file1 = new URL("file:/c:/java/a.jpg");
        } catch(MalformedURLException e) {
            System.out.print(e);
        }
        img1=getImage(file1);
    }
    public void paint(Graphics g) {
        g.drawImage(img1,0,0,this);
    }
}
```

## 示例 18.20 移动圆的演示

```java
import java.awt.*;
import java.awt.event.*;
class Circle1 extends Frame implements MouseListener,Runnable {
    int x,y,w,h;
    static Circle1 f;
    public void run() {
        y=50;
        w=50;
        h=50;
        for(x=0;x<500 ;x+=10) {
            try {
                Thread.sleep(50);
            } catch(InterruptedException e) {
                System.out.println(e);
            }
            repaint();
        }
    }
    public static void main(String args[]) {
        f = new Circle1();
        Thread t=new Thread(f);
        t.start();
        f.addMouseListener(f);
        f.setSize(500,500);
        f.setVisible(true);
    }
    public void paint(Graphics g) {
        g.setColor(Color.RED);
        g.drawOval(x,y,w,h);
        g.setColor(Color.BLUE);
        g.fillOval(x+1,y+1,w-1,h-1);
    }
    public void mousePressed(MouseEvent me) {
        x = me.getX();
        y = me.getY();
        w=50;
        h=50;
        Graphics g=f.getGraphics();
        g.clearRect(0,0,200,200);
        paint(g);
    }
    public void mouseReleased(MouseEvent me) {}
    public void mouseClicked(MouseEvent me) {}
    public void mouseEntered(MouseEvent me) {}
    public void mouseExited(MouseEvent me) {}
}
```

# 第 19 章：AWT 绘图

## 引言

许多类型的 `AWT` 组件（例如 `buttons` 和 `scrollbars`）的外观是由底层窗口系统规定的。其他组件类型，特别是 `applets`、`frames`、`panels` 和 `canvases`，没有内在外观。如果我们不仅仅将这些类作为容器使用，并希望我们的组件看起来足够用，那么我们必须提供实现组件外观的代码。

每个组件都关联着一个图形上下文（`Graphics Context`）。该图形上下文与组件相关的帧缓冲区相对应。

我们可以使用 `Graphics Context` 支持的方法在组件上进行绘图。绘制在 `Graphics Context` 上的任何内容都会显示在组件上。

在任何组件上进行绘图的正确方法是重写它的 `paint()` 方法并提供恰当的代码。

`paint()` 方法有一个类型为 `Graphics` 的参数，它代表组件的 `Graphics Context`。也可以在不使用 `paint()` 方法的情况下在组件上绘图，虽然不建议这种做法。

## `paint()` 方法与图形上下文

在下面的示例中，关于 `frame` 的一个有趣点是，没有显式地调用 `paint()` 方法；该方法被提供了。环境似乎在正确的时刻成功调用了 `paint()`。

在组件上进行绘图是通过调用图形上下文来实现的，图形上下文是 `Graphics` 类的实例。图形上下文知道如何渲染到单个目标。`Graphics Context` 可以渲染到的三种介质是：

1.  `Components`（组件）。
2.  `Images`（图像）。
3.  `Printers`（打印机）。

任何类型的组件都可以与一个图形上下文关联。这种关联是永久的；上下文无法重新分配给新的组件。

`Buttons`、`Choices`、`Checkboxes`、`Labels`、`Scrollbars`、`TextFields` 和 `TextAreas` 通常不需要程序员级别的渲染。大多数情况下，这些组件仅使用从组件父类继承的 `paint()` 版本。

这个版本什么都不做；组件由底层窗口系统进行渲染。然而，有四类“空白”组件，它们没有默认外观，将显示为空矩形，除非它们被子类化并赋予 `paint()` 方法。

这四个组件类是：

* `Applet`
* `Canvas`
* `Frame`
* `Panel`

## 示例 19.1：扩展 `Frame` 类并重写 `paint()` 方法以改变框架的外观。



```java
import java.awt.*;

public class SimplePaint extends Frame
{
    public static void main (String args[])
    {
        Frame f=new SimplePaint();
        f.setSize(200,200);
        f.setVisible(true);
    }
    public void paint (Graphics g)
    {
        g.setColor(Color.white);
        g.fillRect(0,0,300,300);
        g.setColor(Color.grey);
        g.fillOval(30,30,50,50);
    }
}
```

输出：

![](img/image0293.jpeg)

当我们子类一个 `Component` 类并为子类提供它自己的 `paint()` 方法时，环境会在适当的时间调用该方法，并传入一个适当的 `Graphics` 实例。

### `Graphics` 类支持的操作

`Graphics` 类（上下文）提供的四大类操作是：

* 选择颜色。
* 选择字体。
* 绘制与填充。
* 裁剪。

#### 选择颜色

通过调用 `setColor()` 方法选择颜色。所需的参数是 `Color` 类的实例。有 13 种预定义的颜色，可以通过 `Color` 类的 `static final` 变量访问（这些变量本身就是 `Color` 类的实例。这让一些人感到不安，但 Java 并没有问题）。这些预定义的颜色有：

1. `Color.black`
2. `Color.blue`
3. `Color.cyan`
4. `Color.darkGray`
5. `Color.gray`
6. `Color.green`
7. `Color.lightGray`
8. `Color.magenta`
9. `Color.orange`
10. `Color.pink`
11. `Color.red`
12. `Color.white`
13. `Color.yellow`

如果我们需要一个不在此列表中的颜色，可以自己构造。`Color` 构造函数有几个版本，最简单：`Color(int redLevel, int greenLevel, int blueLevel)`。这三个参数是原色在 0 到 255 范围内的强度级。颜色是加色的，这意味着它们像光一样混合，而不是像 `paint`（颜料）。

* `new Color(0,0,0)`（无光）
* `new Color(255,0,0)`（仅包含红色调）
* `new Color(255,255,255)`（所有颜色同时发光）

下面的代码片段列出了 `paint()` 方法的第一部分，该方法将其图形上下文的颜色设置为浅绿色：

```java
public void paint(Graphics g)
{
    Color c= new Color(170,255,170);
    g.setColor(c);
}
```

在上述代码调用 `setColor()` 之后，所有的图形都将绘制成浅绿色（绿色），直到下一次调用 `setColor()`。调用 `setColor(0)` 不会改变已经绘制内容的颜色；它只影响后续操作。

#### 选择字体

设置图形上下文的字体就像设置颜色一样；后续的绘制操作将使用新字体，而之前绘制的字符串不受影响。在我们设置字体之前，必须先创建一个。`Font` 类的构造函数看起来如下：`Font(String fontName, int style, int size)`。

第一个参数是字体名称。字体的可用性取决于平台。我们可以通过这样调用工具包上的 `getFontList()` 方法来获取以字符串数组形式返回的可用字体名称列表：

```java
String fontNames[]= Toolkit.getDefaultToolkit().getFontList();
```

有三个与平台无关且我们鼓励使用的字体名称：

1. "Serif"
2. "SansSerif"
3. "Monospaced"

在 JDK 的 1.0.X 版本中，这些分别被称为 "TimesRoman"、"Helvetica" 和 "Courier"。

`style` 参数可以发送给以下任何一个 `int` 常量：

1. `Font.PLAIN`
2. `Font.BOLD`
3. `Font.ITALIC`

下面的代码片段将图形上下文 `gc` 的字体设置为 24 点加粗无衬线字体：

```java
Font f =new Font("SansSerif",Font.BOLD,24);
gc.setFont(f);
```

我们可以通过传递样式的和来指定样式的组合，例如加粗斜体字体，如下所示：`Font.BOLD + Font.ITALIC`。

#### 绘制与填充

`Graphics` 类的所有渲染方法都为它们渲染的形状指定了像素坐标位置。每个组件都有自己的坐标系，原点位于组件的左上角，x 向右增加，y 向下增加。下图显示了组件坐标系：

![](img/image01294.jpeg)

`Graphics` 上下文类没有广泛的绘制方法（复杂的渲染由扩展 API 如 2D、3D 和动画处理）。

我们需要了解的图形上下文类中的方法有：

| 方法 | 说明 |
| :--- | :--- |
| `void drawLine(int x1, int y1, int x2, int y2)` | 在此图形中使用当前颜色在点 `(x1, y1)` 和 `(x2, y2)` 之间绘制一条线。 |
| `void drawRect(int x, int y, int width, int height)` | 绘制指定矩形轮廓。 |
| `void fillRect(int x, int y, int width, int height)` | 填充指定矩形。 |
| `void drawOval(int x, int y, int width, int height)` | 绘制指定矩形边界的椭圆轮廓。 |
| `void fillOval(int x, int y, int width, int height)` | 使用当前颜色填充指定矩形边界的椭圆。 |
| `void drawArc(int x, int y, int width, int height, int startAngle, int arcAngle)` | 绘制指定矩形内的圆形或椭圆弧轮廓。 |
| `void fillArc(int x, int y, int width, int height, int startAngle, int arcAngle)` | 填充指定矩形内的圆形或椭圆弧。 |
| `void drawPolygon(int[] xPoints, int[] yPoints, int nPoints)` | 绘制由 x 和 y 数组定义的闭合多边形。 |
| `void fillPolygon(int[] xPoints, int[] yPoints, int nPoints)` | 填充由 x 和 y 数组定义的闭合多边形。 |
| `void drawPolyline(int[] xPoints, int[] yPoints, int nPoints)` | 绘制由 x 和 y 数组定义的一系列连接线。 |

### 方法参考

* `void drawString(String str, int x, int y)`: 使用此图形上下文的当前字体和颜色绘制指定的字符串文本。`x`, `y` 参数指定字符串基线的左边缘。带有下延伸部的字符（在大多数字体中为 `g, j, p, q, 和 y`）会延伸到基线以下。文本坐标相对于基线这一事实非常重要。例如，在简单文本中，我们可能会尝试在 `(0,0)` 处绘制字符串，并期望它出现在区域的左上角。然而，由于基线的存在，我们只能看到字符串的下延伸部，这可能意味着我们什么也看不到。默认情况下，图形上下文使用关联组件的字体；但是，我们可以通过调用图形上下文的 `setFont()` 方法设置不同的字体。

* `boolean drawImage(Image img, int x, int y, ImageObserver observer)`: 绘制当前可用的指定图像。这里，`img` 是要渲染的图像，`x` 和 `y` 是目标组件内图像左上角的坐标。图像观察者必须是一个实现了 `ImageObserver` 接口的对象。图像是矩形像素值集合的离屏表示。Java 的图像支持非常复杂。现在，假设我们通过某种方式获取了图像（即 `java.awt.Image` 类的实例），并想要使用特定的图形上下文将其渲染到屏幕上。实现的方法是调用图形上下文的 `drawImage()` 方法。

### 示例 19.2

此示例演示了如何创建一个图像并使用其图形上下文在其进行绘制。然后可以使用 `drawImage()` 方法在 applet 窗口显示该图像。

```java
import java.awt.*;
import java.applet.*;
import java.net.URL;
/*<applet code="PaintImage" width=200 height=100></applet>*/
public class PaintImage extends Applet {
    private Image im;
    public void init() {
        im = createImage(100,50);
        Graphics imgc = im.getGraphics();
        imgc.setColor(Color.gray);
        imgc.fillRect(0,0,100,50);
        imgc.setColor(Color.black);
        imgc.fillOval(0,0,50,40);
    }
    public void paint(Graphics g) {
        g.drawImage(im,10,10,this);
    }
}
```

### 示例 19.3

此示例演示了如何从现有图像创建图像对象。然后可以使用 `drawImage()` 方法在 applet 窗口显示该图像。

```java
import java.awt.*;
import java.applet.*;
import java.net.*;
/*<applet code="PaintImage" width=50 height=50></applet>*/
public class PaintImage extends Applet {
    private Image im;
    public void init() {
        try {
            im = getImage(new URL("file:///c:/logo.gif"));
            // im=getImage(new URL("http://127.0.0.1:8080/logo.gif"));
        } catch (MalformedURLException e) {
            System.out.println(e);
        }
    }
    public void paint(Graphics g) {
        g.drawImage(im,10,0,this);
    }
}
```

### 裁剪

程序员在图形上下文上进行的大多数调用涉及颜色或绘制。一种不常用的操作是裁剪。裁剪简单地限制上下文可以修改的区域。每个图形上下文、每个 `Graphics` 类的实例都有一个裁剪区域，该区域定义了关联组件的所有或部分。当我们调用 `Graphics` 类的 `draw()` 或 `fill()` 方法时，只有位于上下文裁剪区域内的像素会被修改。图形上下文的默认裁剪区域是关联组件的整个可见区域。有方法可以获取和修改裁剪区域。考虑以下 `paint` 方法。

```java
import java.awt.*;
class Clip extends Frame {
    public static void main(String args[]) {
        Frame f = new Clip();
        f.setSize(300,330);
        f.setVisible(true);
    }
    public void paint(Graphics g) {
        for(int i=0; i<300; i+=100) {
            for(int j=30; j<330; j+=100) {
                g.fillOval(i,j,100,100);
            }
        }
    }
}
```

上述程序的 `paint()` 方法绘制了一个点状图案。考虑一下当这是一个 200*200 像素帧的 `paint()` 方法时会发生什么。由于计数器一直到 500，它尝试在帧边界之外绘制。这并不是一个问题，因为上下文默认的裁剪区域与帧本身重合。要为图形上下文设置矩形区域，我们可以调用 `setClip(x, y, width, height)`，传入四个描述所需矩形位置和大小的整数。例如，上面的代码可以修改如下：

```java
import java.awt.*;
class Clip2 extends Frame {
    public static void main(String args[]) {
        Frame f = new Clip2();
        f.setSize(300,330);
        f.setVisible(true);
    }
    public void paint(Graphics g) {
        g.setClip(50,80,200,200);
        for(int i=0; i<300; i+=100) {
            for(int j=30; j<330; j+=100) {
                g.fillOval(i,j,100,100);
            }
        }
        g.drawString("Hello! Kamal", 50,50);
        g.drawString("Bye! Kamal", 120,150);
    }
}
```

输出：

![](img/image01298.jpeg)

如所示，现在绘制被裁剪到 300 * 300 Applet 框架中心的 200 * 200 矩形内。

裁剪本身是一个值得了解的知识。当环境需要修复组件的暴露部分时，裁剪也会发挥作用。

### 关于 `paint()` 方法和图形上下文的总结

`Graphics` 上下文是专属于单个组件的。要在组件上进行绘制，我们调用图形上下文的 `drawXXXX()` 和 `fillXXXX()` 方法。若要更改图形操作的颜色或字体，我们分别调用图形上下文的 `setColor()` 或 `setFont()` 方法。

### GUI 线程与绘制

Java 运行时环境创建并控制其在后台运行的各个线程，其中一个线程负责 GUI 管理。

GUI 线程是环境用于接受用户输入事件以及调用需要绘制的组件的 `paint()` 方法的工具。

对 `paint()` 的调用并非都由环境生成。Java 程序当然可以进行自己的调用，无论是直接调用，还是通过 `repaint()` 方法间接调用。

还可以使用组件的图形上下文在组件上进行绘制。这种方法不需要调用 `paint()` 或 `repaint()` 方法。

在组件上绘图的不同方法如下：

(i) 在获取组件的图形上下文后直接绘制。
(ii) 自发绘制（由 GUI 线程隐式/自动调用 `paint()` 方法）。
(iii) 显式调用 `paint()` 方法。
(iv) 显式调用 `repaint()` 方法，由其间接调用 `paint()` 方法。

### 在获取组件的图形上下文后直接绘制

由于可以使用 `getGraphics()` 方法获取组件 `Graphics` 上下文的引用，人们可能认为可以从任何方便的方法在组件上绘图。通常，这种方法存在严重缺陷。

假设我们有一个 Applet，想要在最近鼠标点击的位置画一个红点。Applet 的其余部分应该是黄色。假设该 Applet 正在处理自己的鼠标事件。我们可能会考虑创建这样的事件处理器：

**示例 19.6：**



```java
import java.awt.*;
import java.awt.event.*;

class PaintApproach extends Frame implements MouseListener {
    public static void main(String args[]) {
        PaintApproach f = new PaintApproach();
        f.setSize(300, 300);
        f.addMouseListener(f);
        f.setVisible(true);
    }

    public void mouseEntered(MouseEvent e) {}
    public void mouseExited(MouseEvent e) {}
    public void mousePressed(MouseEvent e) {}
    public void mouseReleased(MouseEvent e) {}
    public void mouseClicked(MouseEvent e) {
        System.out.println("Mouse Clicked...");
        Graphics g = getGraphics();
        g.setColor(Color.yellow);
        g.fillRect(0, 0, getSize().width, getSize().height);
        g.setColor(Color.Red);
        g.fillOval(e.getX() - 10, e.getY() - 10, 20, 20);
    }
}
```

## 自发绘制（由 GUI 线程隐式/自动调用 `paint()` 方法）

“自发绘制”并不是一个正式术语，但也可以使用。例如，当浏览器启动时，在 `init()` 方法完成后不久就会调用 `paint()` 方法。此外，当浏览器的部分或全部被覆盖后又重新暴露时，GUI 线程会在发生以下任一情况后调用 `paint()`：

*   暴露后
*   最小化后
*   首次显示后

当浏览器返回到之前包含 Applet 的页面时（只要该 Applet 至少可见）。当 GUI 线程调用 `paint()` 时，它必须提供一个图形上下文，因为 `paint()` 方法的输入参数是 `Graphics` 类的实例。

前面的章节（“裁剪”）讨论了每个图形上下文都有裁剪区域的事。GUI 线程确保传递给 `paint()` 的图形上下文已设置了裁剪区域。大多数情况下，默认裁剪区域是合适的。

然而，当组件被暴露时，裁剪区域被设置为仅包含组件需要修复的部分。如果只暴露了组件的一小部分，裁剪区域将确保不会浪费时间去绘制已经是正确颜色的像素。

如果暴露区域不是矩形，则可能会发生多次 `paint()` 调用，每次的裁剪区域都会连续累积，以确保暴露区域最终被重绘。

## 显式调用 `paint()` 方法

如果在组件上的绘制操作是在 `paint()` 方法以外的方法中执行的，组件可能不会刷新。如果绘制是在 `paint` 方法中完成的，那么当我们显式调用 `paint()` 方法以及 GUI 线程隐式调用 `paint()` 方法时，它都会被显示出来。

上一个示例中的 `mouseClicked()` 方法被重写为每当发生鼠标点击时只需修改实例变量 `mouseX` 和 `mouseY`。

红点仅在 `paint()` 方法中绘制，以便即使 Applet 被覆盖并暴露，它也能得到修复。

### 示例 19.7

上一节的示例经过了修改，使得组件显示在上述情况下可以得到刷新。这是因为红点是在 `paint()` 方法中绘制的。

```java
import java.awt.*;
import java.awt.event.*;
```

### PaintApproach1 实现

```java
public class PaintApproach1 extends Frame implements MouseListener {
    int mouseX, mouseY;

    public static void main(String arg[]) {
        PaintApproach1 f = new PaintApproach1();
        f.setSize(300, 300);
        f.addMouseListener(f);
        f.setVisible(true);
    }

    public void mouseEntered(MouseEvent e) {}
    public void mouseExited(MouseEvent e) {}
    public void mousePressed(MouseEvent e) {}
    public void mouseReleased(MouseEvent e) {}
    public void mouseClicked(MouseEvent e) {
        System.out.println("MouseClicked...");
        mouseX = e.getX();
        mouseY = e.getY();
        Graphics g = getGraphics();
        paint(g);
    }

    public void paint(Graphics g) {
        g.setColor(Color.yellow);
        g.fillRect(0, 0, getSize().width, getSize().height);
        g.setColor(Color.red);
        g.fillOval(mouseX - 10, mouseY - 10, 20, 20);
    }
}
```

## 显式调用 `repaint()`

显式调用 `repaint()` 方法（随后会间接调用 `paint()`）可能会导致严重的问题。第一个问题是 GUI 线程在需要处理区域暴露时调用了 `paint()`。这可能会导致线程问题。公平地说，我们会发现，即使使用首选方法，我们可能仍然需要处理其中的一些问题，因为 `paint()` 方法将使用我们在其他线程中修改的数据。

第二个问题是关于 CPU 使用率的。考虑以下场景：我们的程序定期接收到通知，要求使用动画的下一帧或连续移动的图形来更新显示。假设绘图过程是复杂且耗时的。如果我们调用整个 `paint()` 方法，当新帧发生时，我们可能只完成了绘图的一部分。这将导致程序将所有时间花在绘图上。此外，绘图进度会越来越落后于预期。

这些问题可以通过使用首选的处理方法简单地解决。其思想是：主程序维护一个描述应呈现给用户的绘图的数据集，但不调用绘图程序。相反，程序请求 GUI 线程运行绘图程序，其方式与该线程处理区域暴露时的操作大致相同。GUI 线程使用主程序提供的数据来决定画什么以及如何画。

为了支持这种方法，GUI 系统提供了名为 `repaint()` 的方法。该方法定义在 `Component` 类中，因此 GUI 中的任何可见对象都可以。当我们调用此方法时，我们是在向 GUI 线程发出一个请求，让它执行绘图程序。GUI 线程会在合理的时间范围内执行操作，尽管这可能会受到其他高优先级线程活动的限制。这种方法确保了 GUI 线程与用户线程之间的交互降至最低。我们自然必须确保在数据处于不一致状态时，GUI 线程不会使用我们的数据集。然而，通过使用同步或双缓冲技术，可以很容易地实现这一点。这种行为的另一个结果是，无论程序尝试进行多少绘图，系统通常保持与当前帧的同步。例如，如果我们在 GUI 线程能够处理第一次调用之前调用了十次 `repaint()` 方法，那么结果将是绘图系统只执行了一次。

因此，在过载的情况下，绘图系统会自动跳过主机 CPU 无法处理的帧。这意味着程序员可以编写代码，在给定平台上可靠地获得最佳可用视频性能，同时在任何其他平台上都能运行良好。以下代码实现了这种方案。

### 示例 19.8

```java
import java.awt.*;
import java.awt.event.*;

class PaintApproach2 extends Frame implements MouseListener {
    int mouseX, mouseY;

    public static void main(String args[]) {
        PaintApproach2 f = new PaintApproach2();
        f.setSize(300, 300);
        f.addMouseListener(f);
        f.setVisible(true);
    }

    public void mouseEntered(MouseEvent e) {}
    public void mouseExited(MouseEvent e) {}
    public void mousePressed(MouseEvent e) {}
    public void mouseReleased(MouseEvent e) {}
    public void mouseClicked(MouseEvent e) {
        System.out.println("Mouse Clicked …");
        mouseX = e.getX();
        mouseY = e.getY();
        repaint();
    }

    public void paint(Graphics g) {
        g.setColor(Color.yellow);
        g.fillRect(0, 0, getSize().width, getSize().height);
        g.setColor(Color.red);
        g.fillOval(mouseX - 10, mouseY - 10, 20, 20);
    }
}
```

前台绘图线程与 GUI 线程之间的线程交互是受控且可预测的。

虚拟机永远不会被绘图操作淹没。

当所有代码按这种方式编写时，其他尝试调试代码的程序员就不会遇到任何“意外状况”。

尽管这种方法效果良好，但存在一种需要进一步改进的情况：动画。如果我们完全按照描述的方法来操作，可能会注意到动画在运行时会产生不愉快的闪烁。

## 平滑动画

重绘机制的默认行为中有一个特性我们可能并不总是需要的，那就是系统在准备响应我们对 `repaint()` 调用的准备阶段，会清除我们的绘图区域。这会导致动画和其他实时绘制出现不愉快的闪烁。事实证明，当我们调用 `repaint()` 时，GUI 线程并没有调用 `paint()`；而是调用 `update()` 方法。`update()` 的默认行为是做两件事：清除背景然后调用 `paint`。如下所示：

```java
public void update(Graphics g) {
    g.clearRect(0, 0, width, height);
    paint(g);
}
```

我们可能会合理地问，为什么 `repaint()` 一开始就清除窗口，如果这会导致闪烁的话。嗯，在很多情况下，绘制是使用在背景上绘制线条、矩形、圆形等完成的。

如果我们正试图制作一个旋转的棒子，我们需要在绘制新线之前移除旧线。这种问题的另一种方式是：如果我们试图画一个新图，就应该先擦掉旧的。

那么，我们如何能够在不先清除整个显示器的情况下让新图出现呢？我们只需要找到另一种移除旧图的方法。通用方法是确保我们在每次绘制帧时，都绘制整个图——包括背景和前景。如果我们能安排好这一点，就不需要清除组件，闪烁也会消失。

为了防止组件在调用 `paint()` 之前被清除，我们只需要重写 `update()` 方法，使其直接调用 `paint`，如下所示：

```java
public void update(Graphics g) {
    paint(g);
}
```

这是一项标准技术且运行完美，前提是我们的 `paint()` 方法确实刷新了显示器的所有像素。处理这种问题的一种特别简单的方法是使用离屏图像来存储应该在显示器上显示的绘图。

这种技术在速度或内存方面并不总是最高效的，但它简单易于实现，且 Java 程序员通常都能良好理解。

![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg)

![STAR-LOGO-2013](img/image01213.jpeg)

# Java.Lang.Object 类

## 简介

`Object` 类是 `java.lang` 包的根类，所有 Java 类的基类。即使你写一个简单的类（即不继承任何基类），它也会继承 `Object`。因此，该类的功能在所有类中可用。

## Object 类的方法

`Object` 类定义了以下方法，被所有类继承：

1. `public int hashCode()`
2. `public boolean equals(Object obj)`
3. `final Class getClass()`
4. `public String toString()`
5. `protected void finalize() throws Throwable`
6. `protected Object clone() throws CloneNotSupportedException`
7. `final void wait(long timeout) throws InterruptedException`
8. `final void wait(long timeout, int nanos) throws InterruptedException`
9. `final void wait() throws InterruptedException`
10. `final void notify()`
11. `final void notifyAll()`

### 1. `public int hashCode()`

在哈希表中存储对象时，可以使用此方法获取对象的哈希值。该值在程序执行期间保持一致。

### 2. `boolean equals(Object obj)`

如果每个对象都被认为是唯一的，那么没有必要重写 `Object` 类的 `equals` 方法。该方法比较对象的引用。

### 3. `final Class getClass()`

返回对象的运行时类，该类由 `java.lang.Class` 的对象表示。



## 公共字段 (1)

```java
public static final java.util.Comparator java.lang.String.CASE_INSENSITIVE_ORDER
```

## 声明方法 (70)

```java
public int java.lang.String.hashCode()

public int java.lang.String.compareTo(java.lang.String)

public int java.lang.String.compareTo(java.lang.Object)

public int java.lang.String.indexOf(int, int)

public int java.lang.String.indexOf(int)

public int java.lang.String.indexOf(java.lang.String)

public int java.lang.String.indexOf(java.lang.String, int)

static int java.lang.String.indexOf(char[], int, int, char[], int, int, int)

public boolean java.lang.String.equals(java.lang.Object)

public String java.lang.String.toString()

public char java.lang.String.charAt(int)

private static void java.lang.String.checkBounds(byte[], int, int)

public int java.lang.String.codePointAt(int)

public int java.lang.String.codePointBefore(int)

public int java.lang.String.codePointCount(int, int)

public int java.lang.String.compareToIgnoreCase(java.lang.String)

public String java.lang.String.concat(java.lang.CharSequence)

public boolean java.lang.String.contains(java.lang.String)

public boolean java.lang.String.equals(java.lang.CharSequence)

public static String java.lang.String.valueOf(char[])

public static String java.lang.String.valueOf(char[], int, int)

public boolean java.lang.String.endsWith(java.lang.String)

public boolean java.lang.String.equalsIgnoreCase(java.lang.String)

public static String java.lang.String.format(java.util.Locale, java.lang.String, java.lang.Object[])

public static String java.lang.String.format(java.lang.String, java.lang.Object[])

public byte[] java.lang.String.getBytes()

public byte[] java.lang.String.getBytes(java.nio.charset.Charset)

public byte[] java.lang.String.getBytes(java.lang.String) throws java.io.UnsupportedEncodingException

public void java.lang.String.getBytes(int, int, byte[], int)

public void java.lang.String.getChars(int, int, char[], int)

public native java.lang.String java.lang.String.intern()

public boolean java.lang.String.isEmpty()

public int java.lang.String.lastIndexOf(int)

public int java.lang.String.lastIndexOf(java.lang.String)

public int java.lang.String.lastIndexOf(java.lang.String, int)

public int java.lang.String.lastIndexOf(int, int)

public int java.lang.String.length()

public boolean java.lang.String.matches(java.lang.String)

public int java.lang.String.offsetByCodePoints(int, int)

public boolean java.lang.String.regionMatches(boolean, int, java.lang.String, int, int)

public boolean java.lang.String.regionMatches(int, java.lang.String, int, int)

public static String java.lang.String.replace(java.lang.CharSequence, java.lang.CharSequence)

public static String java.lang.String.replace(char, char)

public static String java.lang.String.replaceAll(java.lang.String, java.lang.String)

public static String java.lang.String.replaceFirst(java.lang.String, java.lang.String)

public String[] java.lang.String.split(java.lang.String, int)

public String[] java.lang.String.split(java.lang.String)

public boolean java.lang.String.startsWith(java.lang.String, int)

public boolean java.lang.String.startsWith(java.lang.String)

public CharSequence java.lang.String.subSequence(int, int)

public String java.lang.String.substring(int, int)

public String java.lang.String.substring(int)

public char[] java.lang.String.toCharArray()

public String java.lang.String.toLowerCase()

public String java.lang.String.toLowerCase(java.util.Locale)

public String java.lang.String.toUpperCase()

public String java.lang.String.toUpperCase(java.util.Locale)

public String java.lang.String.trim()

public static String java.lang.String.valueOf(boolean)

public static String java.lang.String.valueOf(char[], int, int)

public static String java.lang.String.valueOf(int)

public static String java.lang.String.valueOf(long)

public static String java.lang.String.valueOf(float)

public static String java.lang.String.valueOf(double)

public static String java.lang.String.valueOf(char[])

public static String java.lang.String.valueOf(java.lang.Object)

public static String java.lang.String.valueOf(char)
```

## 声明字段 (7)



```java
private final char[] java.lang.String.value

private final int java.lang.String.offset

private final int java.lang.String.count
```

`private int java.lang.String.hash`

`private static final long java.lang.String.serialVersionUID`

`private static final java.io.ObjectStreamField[] java.lang.String.serialPersistentFields`

`public static final java.util.Comparator java.lang.String.CASE_INSENSITIVE_ORDER`

### 示例 20.2

之前的示例经过修改，可以从命令行参数读取全限定类名，然后使用反射/内省显示关于类的方法和字段的信息。

```java
import java.lang.reflect.Method;
import java.lang.reflect.Field;
class DispClassMembers2
{
    public static void main(String args[]) throws ClassNotFoundException {
        Class c = Class.forName(args[0]);
        Method m[] = c.getMethods();
        System.out.println("……Public Methods (” + m.length + “……”);
        for(int i=0; i< m.length; i++)
            System.out.println(m[i]);
        Field f[] = c.getFields();
        System.out.println("……Public Fields (” + f.length + “)……”);
        for(int i=0; i< f.length; i++)
            System.out.println(f[i]);
        m = c.getDeclaredMethods();
        System.out.println("……Declared Methods (“ + m.length + ”……”);
        for(int i=0; i<m.length; i++)
            System.out.println(m[i]);
        f = c.getDeclaredFields();
        System.out.println("……Declared Fields (“ + f.length + ”……”);
        for(int i=0; i< f.length; i++)
            System.out.println(f[i]);
    }
}
```

**输出：**

与之前相同，但从命令行参数传递了类名 "String"。

```
javac DispClassMembers2.java
java DispClassMembers2 String
```

## 4. String toString()

如果子类没有重写此方法，它将返回对象的文本表示，其格式如下：

“<类名>@<对象的哈希码值>

该方法通常会被重写，并用于调试。方法调用 `System.out.println(Objref)` 会隐式地使用 `toString()` 方法将其参数转换为文本表示。

### 示例 20.3

此示例演示了当我们尝试显示 Box 类对象时会显示什么内容。对象使用其所属类的 `toString` 方法转换为文本表示。

```java
class Box
{
    double w,h,d;
    Box(double w, double h, double d) {
        this.w=w;
        this.h=h;
        this.d=d;
    }
}
class ToString1
{
    public static void main(String args[]) {
        Box b= new Box(10,12,4);
        String s=”Box:”+b;
        System.out.println(b);
        System.out.println(s);
    }
}
```

**输出：**

```
Box1@82b41
Box1 b: Box1@82b41
```

### 示例 20.4

此示例演示了如果我们在 Box 类中重写了 `toString()` 方法，则将使用重写后的方法将对象转换为文本表示。

```java
class Box
{
    double w,h,d;
    Box(double w, double h, double d) {
        this.w=w;
        this.h=h;
        this.d=d;
    }
    public String toString() {
        return “Dimensions are ”+ w + “ by ”+ h + “ by ”+ d + “.”;
    }
}
class ToStringDemo2
{
    public static void main(String args[]) {
        Box b= new Box(8,11,13);
        String s=”Box b:” + b; // 拼接 box 对象并调用 toString() 方法
        System.out.println(b); // 调用 toString() 方法
        System.out.println(s);
    }
}
```

**输出：**

```
Dimension are 8.0 by 11.0 by 13.0
Box b: Dimension are 8.0 by 11.0 by 13.0
```

## 5. `protected void finalize() throws Throwable`

它在对象被垃圾回收之前被调用，以便可以进行任何清理工作。然而， `object` 类中的默认 `finalize()` 方法并没有做任何有用的事情。这对于释放非 Java 资源可能有用，但不建议。如果可用内存足够，`finalize()` 方法可能永远不会被调用，在这种情况下资源可能永远不会被释放。

## 6. `protected Object clone() throws CloneNotSupportedException`

通过 `clone()` 方法可以创建与当前对象完全相同（即具有相同状态）的新对象，即原始值和引用值都会被复制，这被称为浅拷贝。

类可以重写 `clone()` 方法以提供其自己的克隆概念。例如，通过递归地克隆组成对象来克隆复合对象被称为深克隆。

在重写时，子类中的该方法通常是公共的，以允许任何客户端进行克隆。

如果重写 `clone()` 方法依赖于 `Object` 类中的 `clone()` 方法，则子类必须实现 `cloneable` 接口以表明其对象可以安全地克隆。否则，`Object` 类中的 `clone()` 方法将抛出 `CloneNotSupportedException`。

### 使用 clone() 和 Cloneable 接口

`clone()` 方法生成调用它的对象的对象的副本。以下是关于 `clone()` 方法的一些重要事实：

只有实现了 `Cloneable` 接口的类才能被克隆。`Cloneable` 接口没有定义成员。它用于指示一个类允许对对象进行位位复制（即创建克隆）。

如果你尝试对未实现 `cloneable` 接口的类对象调用 `clone()`，将抛出 `CloneNotSupportedException`。

`Cloneable` 接口是一个空接口。这种接口被称为标记接口。在创建克隆体时，被克隆对象的构造函数不会被调用。

克隆体只是原始对象的完全拷贝。克隆是一个潜在的危险操作，因为它会导致意外的副作用。

例如，如果被克隆的对象包含一个名为 `objRef` 的引用变量，那么在创建克隆时，克隆体中的 `objRef` 将指向与原始对象的 `objRef` 相同的对象。如果克隆改变了 `objRef` 所指对象的内容，那么原始对象也会随之改变。

### 示例 20.5

以下示例演示了 `clone()` 方法的使用。`CloneDemo1` 类通过间接通过 `clone2()` 方法调用 `clone()` 方法，为 `TestClone1` 类对象创建克隆。

```java
class TestClone1 implements Cloneable
{
    int a;
    float b;
    public TestClone1 clone2() throws CloneNotSupportedException
    {
        return (TestClone1) clone();
    }
}
class CloneDemo1
{
    public static void main(String a[]) throws CloneNotSupportedException
    {
        TestClone1 tc1 = new TestClone1();
        TestClone1 tc2;
        tc1.a = 8; tc1.b = 4.5f;
        tc2 = tc1.clone2();
        System.out.println(tc2.a);
        System.out.println(tc2.b);
    }
}
```

```
8
4.5
```

在这里，`clone2()` 方法调用了 `Object` 类的 `clone()` 并返回结果。注意，`clone()` 返回的对象必须强制转换为其适当类型，即 `TestClone1`。

### 示例 20.6

在以下示例中，`clone()` 方法被重写，以便可以从类外部调用。为了做到这一点，其修饰符必须是 `public`。

```java
class TestClone2 implements Cloneable
{
    int a;
    float b;
    public Object clone() throws CloneNotSupportedException
    {
        return super.clone();
    }
}
class CloneDemo2
{
    public static void main(String args[]) throws CloneNotSupportedException
    {
        TestClone2 tc1 = new TestClone2();
        TestClone2 tc2;
        tc1.a = 8; tc1.b = 4.5f;
        tc2 = (TestClone2) tc1.clone();
        System.out.println(tc2.a + " , " + tc2.b);
    }
}
```

输出:

```
8 , 4.5
```

### 示例 20.7

在以下示例中，`clone()` 方法被重写，使其没有使用 `Object` 类的 `clone()` 方法。我们正在编写自己的 `clone()` 方法。

```java
class TestClone3
{
    int a;
    float b;
    public Object clone() throws CloneNotSupportedException
    {
        TestClone3 tc = new TestClone3();
        tc.a = a;
        tc.b = b;
        return tc;
    }
}
class CloneDemo3
{
    public static void main(String args[]) throws CloneNotSupportedException
    {
        TestClone3 tc1 = new TestClone3();
        TestClone3 tc2;
        tc1.a = 8;
        tc1.b = 4.5f;
        tc2 = (TestClone3) tc1.clone();
        System.out.println(tc2.a + " " + tc2.b);
    }
}
```

输出:

```
8 , 4.5
```

注意：在实现 `clone()` 方法时，你需要声明 `CloneNotSupportedException` 并实现 `Cloneable` 接口。

### 克隆的副作用

克隆引起的副作用起初很难察觉。人们很容易认为一个类对于克隆是安全的，但实际上并非如此。通常，如果没有没有理由，你不应为任何类实现 `Cloneable` 接口。

### 示例 20.8

此示例演示了克隆的副作用。

```java
class TestShallowClone implements Cloneable
{
    int a;
    float b;
    int c[];
    public Object clone() throws CloneNotSupportedException
    {
        return super.clone();
    }
}
class ShallowCloneDemo
{
    public static void main(String arg[]) throws CloneNotSupportedException
    {
        TestShallowClone tc1 = new TestShallowClone();
        TestShallowClone tc2;
        tc1.a = 8;
        tc1.b = 4.5f;
        int c[] = new int[4];
        for(int i=0; i<4; i++)
            c[i] = i;
        tc1.c = c;
        for(int i=0; i<4; i++)
            System.out.println("tc1.c[" + i +]="=" + tc1.c[i]);
        tc2 = (TestShallowClone) tc1.clone();
        System.out.println("tc2.a"+tc2.a);
        System.out.println("tc2.b"+tc2.b);
        for(int i=0; i<4; i++)
            System.out.println("tc2.c[" + i +]="=" + tc2.c[i]);
        for(int i=0; i<4; i++)
            tc2.c[i] = i+4;
        for(int i=0; i<4; i++)
            System.out.println("tc2.c[" + i +]="=" + tc2.c[i]);
        for(int i=0; i<4; i++)
            System.out.println("tc1.c[" + i +]="=" + tc1.c[i]);
    }
}
```

输出:

```
tc1.c[0]=0
tc1.c[1]=1
tc1.c[2]=2
tc1.c[3]=3
tc2.a=8
tc2.b=4.5
tc2.c[0]=0
tc2.c[1]=1
tc2.c[2]=2
tc2.c[3]=3
tc2.c[0]=4
tc2.c[1]=5
tc2.c[2]=6
tc2.c[3]=7
tc1.c[0]=4
tc1.c[1]=5
tc1.c[2]=6
tc1.c[3]=7
```

### 示例 20.9

以下代码通过实现深克隆解决了上一个示例中面临的问题。

```java
class TestDeepClone implements Cloneable
{
    int a;
    float b;
    int c[];
    public Object clone() throws CloneNotSupportedException
    {
        TestDeepClone tc = (TestDeepClone) super.clone();
        int d[] = new int[4];
        for(int i=0; i<4; i++)
            d[i] = c[i];
        tc.c = d;
        return tc;
    }
}
class CloneDemo
{
    public static void main(String arg[]) throws CloneNotSupportedException
    {
        TestDeepClone tc1 = new TestDeepClone();
        TestDeepClone tc2;
    }
}
```



```java
tc1.a = 8;
tc1.b = 4.5;
int c[] = new int[4];
for(int i=0; i<4; i++)
    c[i] = i;
tc1.c = c;
for(int i=0; i<4; i++)
    System.out.println(“tc1.c[”+ i +”]=” + tc1.c[i]);
tc2 = (TestDeepClone) tc1.clone();
System.out.println(“tc2.a”+tc2.a);
System.out.println(“tc2.b”+tc2.b);
for(int i=0; i<4; i++)
    System.out.println(“tc2.c[” + i + “]=” + tc2.c[i]);
for(int i=0; i<4; i++)
    tc2.c[i] = i+4;
for(int i=0; i<4; i++)
    System.out.println(“tc2.c[” + i + “]=” + tc2.c[i]);
for(int i=0; i<4; i++)
    System.out.println(“tc1.c[” + i + “]=” + tc1.c[i]);
```

输出：

tc1.c[0]=0

tc1.c[1]=1

tc1.c[2]=2

tc1.c[3]=3

tc2.a=8

tc2.b=4.5

tc2.c[0]=0

tc2.c[1]=1

tc2.c[2]=2

tc2.c[3]=3

tc2.c[0]=4

tc2.c[1]=5

tc2.c[2]=6

tc2.c[3]=7

tc1.c[0]=0

tc1.c[1]=1

## 多线程环境下的有用方法

除了上述讨论的方法，`Object` 类通过以下方法在同步代码中提供线程通信支持：导致当前线程等待，直到另一个线程调用该对象的 `notify()` 方法或 `notifyAll()` 方法。

8. `final void wait(long timeout) throws InterruptedException`

9. `final void wait(long timeout, long nanos) throws InterruptedException`

导致当前线程等待，直到另一个线程调用该对象的 `notify()` 方法或 `notifyAll()` 方法，或者其他线程中断了当前线程，或者经过了指定的时间。

10. `final void notify()`

唤醒等待在该对象监视器上的单线程线程。

11. `final void notifyAll()`

唤醒所有等待在该对象监视器上的线程。线程通过调用其中一个 `wait` 方法在对象的监视器上进行等待。线程在它持有的锁对应的对象上调用这些方法。线程等待另一个线程的通知。

## 集合框架

### 简介

Java 集合框架标准化了你的程序处理对象组的方式。在 Java 2 之前，Java 提供了诸如 `Vector`、`Stack`、`Dictionary`、`Hashtable` 和 `Properties` 等临时类来存储和操作对象组。

尽管这些类非常有用，但它们缺乏一个核心的统一主题。我们使用 `Vector` 的方式与使用 `Properties` 类的方式不同，此外，之前的临时方法并非设计为易于扩展或适应。集合就是这些（以及其他）问题的救星。

### 目标

为了实现这些目标，框架设计为：

- 必须是高性能的。
- 允许不同类型的集合以类似的方式工作。
- 之前的临时方法并非设计为易于扩展或适应。集合就是这些（以及其他）问题的救星。

### 集合接口

集合框架定义了几个接口。具体类仅提供不同的实现。支撑集合的接口有：

- `Collection`：使能够处理对象组；它位于层次结构的顶端。
- `List`：扩展了 `Collection`，以处理序列（对象列表）。
- `Set`：扩展了 `Collection`，以处理必须包含唯一元素的集合。
- `SortedSet`：扩展了 `Set`，以处理排序集合。

除了集合接口，集合还使用了 `Comparator`、`Iterator`、`ListIterator` 和 `RandomAccess` 接口。`Comparator` 定义了如何比较两个对象；`Iterator` 和 `ListIterator` 遍历集合中的对象。

通过实现 `RandomAccess`，列表表示支持对其元素进行随机访问。为了提供最大的灵活性，集合接口允许某些方法是可选的。

### Iterator 接口

`Iterator` 接口定义了以下方法：

- `hasNext()`：如果迭代还有更多元素，返回 `true`。
- `next()`：返回迭代的下一个元素。
- `remove()`：从底层集合中移除迭代器返回的最后一个元素（在某些情况下如 EJB 可能不允许这样做）。这是一个可选操作，如果迭代器不支持此操作，则抛出 `UnsupportedOperationException`。

迭代器与枚举的区别在于两点：

- 迭代器允许调用者在迭代期间从底层集合中删除元素并具有良好的语义。
- 方法名称得到了改进。

### ListIterator 接口

这是 `Iterator` 的子接口。

```java
public interface ListIterator extends Iterator
```

它是列表的迭代器，允许程序员以任一方向遍历列表，在迭代过程中修改列表，并获取迭代器在列表中的当前位置。

#### 方法总结

| 类型 | 描述 |
| :--- | :--- |
| `void add(Object obj)` | 将指定的元素插入列表中（可选操作）。 |
| `boolean hasNext()` | 如果在正向遍历列表时此迭代器还有更多元素，则返回 `true`。 |
| `boolean hasPrevious()` | 如果在反向遍历列表时此迭代器还有更多元素，则返回 `true`。 |
| `Object next()` | 返回列表中的下一个元素。 |
| `int nextIndex()` | 返回下次调用 `next()` 将返回的元素的索引。 |
| `Object previous()` | 返回列表中的上一个元素。 |
| `int previousIndex()` | 返回下次调用 `previous()` 将返回的元素的索引。 |
| `void remove()` | 从列表中移除由 `next()` 或 `previous()` 返回的最后一个元素（可选操作）。 |
| `void set(Object obj)` | 用指定的元素替换由 `next()` 或 `previous()` 返回的最后一个元素（可选操作）。 |

### RandomAccess 接口

这是一个由 `List` 使用的标记接口，用于指示它们支持随机访问。`ArrayList` 和 `Vector` 实现了此接口。

### Comparator 接口

比较器（Comparators）用于控制某些数据结构（如 `TreeSet` 和 `TreeMap`）的顺序。

| 类型 | 描述 |
| :--- | :--- |
| `int compare(Object o1, Object o2)` | 比较其参数的大小。 |
| `boolean equals(Object obj)` | 表示另一个对象是否“等于”当前对象。 |

### Collection 接口

集合接口是构建集合框架的基础。它声明了所有集合将拥有的核心方法。由于所有集合都实现了 `Collection` 接口，因此熟悉它的方法对于清晰理解该框架是必要的。其中几个方法可能会抛出 `UnsupportedOperationException`。当一个对象与另一个对象不兼容时，会产生 `ClassCastException`，例如尝试向集合中添加不兼容的对象时。

#### Collection 接口中的方法

| 类型 | 描述 |
| :--- | :--- |
| `boolean add(Object obj)` | 确保此集合包含指定的元素（可选操作）。将对象添加到调用集合中。如果 `obj` 已添加到集合中，则返回 `true`。如果 `obj` 已经是集合的成员且集合不允许重复，则返回 `false`。 |
| `boolean addAll(Collection c)` | 将指定集合中的所有元素添加到此集合中（可选操作）。 |
| `void clear()` | 移除此集合中的所有元素（可选操作）。 |
| `boolean contains(Object o)` | 如果此集合包含指定的元素，则返回 `true`。 |
| `boolean containsAll(Collection c)` | 如果此集合包含指定集合中的所有元素，则返回 `true`。 |
| `boolean equals(Object o)` | 将指定的对象与此集合进行等值比较。 |
| `int hashCode()` | 返回此集合的哈希码。 |
| `boolean isEmpty()` | 如果此集合不包含元素，则返回 `true`。 |
| `Iterator iterator()` | 返回一个用于遍历集合中元素的迭代器。 |
| `boolean remove(Object o)` | 如果集合中存在指定的元素，则从集合中移除该元素的单个实例（可选操作）。 |
| `boolean removeAll(Collection c)` | 移除所有也包含在指定集合中的元素（可选操作）。 |
| `boolean retainAll(Collection c)` | 保留此集合中包含在指定集合中的元素（可选操作）。 |
| `int size()` | 返回此集合中的元素数量。 |
| `Object[] toArray()` | 返回包含此集合中所有元素的数组。 |

可以通过调用 `equals()` 方法比较两个集合的等值性。“等值性”的精确含义可能因集合而异。例如，你可以实现 `equals()` 使其比较集合中存储的元素的值。或者，`equals()` 可以比较这些元素的引用。

### List 接口

列表是一种有序的集合，被称为序列（sequence）。`List` 接口扩展了 `Collection` 并声明了存储元素序列的集合的行为。可以通过元素在列表中的位置插入或访问元素，使用从 0 开始的索引。列表可以包含重复元素。除了 `Collection` 定义的方法外，`List` 还定义了一些自己的方法。

#### List 接口中的方法

| 类型 | 描述 |
| :--- | :--- |
| `boolean add(Object o)` | 将指定的元素添加到此列表的末尾（可选操作）。该方法定义在 `Collection` 接口中但作为 `List` 接口的一部分，它应该实现为始终将元素添加到列表的末尾。 |
| `void add(int index, Object element)` | 在此列表的指定位置插入指定的元素（可选操作）。插入点处或该点之后的任何预先存在的元素都会向前移动。因此，元素不会被覆盖。 |
| `boolean addAll(Collection c)` | 按指定集合 `iterator()` 返回的顺序，将指定集合中的所有元素添加到此列表的末尾（可选操作）。该方法定义在 `Collection` 接口中，作为 `List` 接口的一部分，它应该实现为始终将元素添加到列表的末尾。 |
| `boolean addAll(int index, Collection c)` | 将指定集合中的所有元素插入此列表的指定位置（可选操作）。如果调用列表发生变化，则返回 `true`，否则返回 `false`。 |
| `Object get(int index)` | 返回此列表中指定位置的元素。 |
| `int indexOf(Object o)` | 返回指定元素首次出现的索引，如果列表不包含该元素，则返回 -1。 |
| `int lastIndexOf(Object o)` | 返回指定元素最后一次出现的索引，如果列表不包含该元素，则返回 -1。 |
| `Iterator iterator()` | 返回一个遍历此列表元素的迭代器（按正确顺序）。 |
| `ListIterator listIterator(int index)` | 返回一个遍历此列表元素的列表迭代器（按正确顺序），从列表的指定位置开始。 |
| `Object remove(int index)` | 移除指定位置的元素（可选操作）并返回删除的元素。生成的列表将压缩。也就是说，后续元素的索引减一。 |
| `Object set(int index, Object element)` | 用指定的元素替换此列表中指定位置的元素（可选操作）。 |
| `List subList(int fromIndex, int toIndex)` | 返回包含调用列表从 `fromIndex`（包含）到 `toIndex`（不包含）元素的视图。返回列表中的元素也被调用对象引用。 |

### Set 接口

`Set` 接口定义了一个集合。它扩展了 `Collection` 并声明了不允许重复元素的集合的行为。因此，当尝试向集合添加重复元素时，`add()` 方法返回 `false`。它没有定义任何额外的方法。

### SortedSet 接口

`SortedSet` 接口扩展了 `Set` 并声明了按升序排序的集合的行为。

| 方法 | 描述 |
| :--- | :--- |
| `Comparator comparator()` | 返回与此排序集合关联的比较器；如果它使用元素的自然排序，则返回 `null`。 |
| `Object first()` | 返回此排序集合中的第一个元素。 |
| `SortedSet headSet(Object toElement)` | 返回此排序集合某个部分的视图，其元素严格小于 `toElement`。 |
| `Object last()` | 返回此排序集合中的最后一个元素。 |
| `SortedSet subSet(Object fromElement, Object toElement)` | 返回此排序集合某个部分的视图，其元素范围从 `fromElement`（包含）到 `toElement`（不包含）。 |
| `SortedSet tailSet(Object fromElement)` | 返回此排序集合某个部分的视图，其元素大于或等于 `fromElement`。 |

当调用的集合中不包含项时，有几个方法会抛出 `NoSuchElementException`。当对象与集合中的元素不兼容时，会抛出 `ClassCastException`。如果尝试使用 `null` 对象且集合中不允许 `null`，则会抛出 `NullPointerException`。

## 集合类

某些集合类提供了完整的实现，可以直接使用。另一些类是抽象的，它们提供了骨架实现，用作创建具体集合的起点。

没有任何集合类是同步版本。

标准集合类有：

| 类 | 描述 |
| :--- | :--- |
| `AbstractCollection` | 实现了 `Collection` 接口的大部分方法。 |
| `AbstractList` | 扩展 `AbstractCollection` 并实现了 `List` 接口的大部分方法。 |



| `AbstractSequenceList` | 扩展 `AbstractList`，用于按顺序而非随机访问元素的集合。 |
| `AbstractSet` | 扩展 `AbstractCollection` 并实现了 `Set` 接口。 |
| `LinkedList` | 通过扩展 `AbstractSequentialList` 实现链表列表。 |
| `ArrayList` | 通过扩展 `AbstractList` 实现动态数组。它使用对元素的进行随机访问。 |
| `HashSet` | 扩展 `AbstractSet` 用于哈希表。 |
| `LinkedHashSet` | 扩展 `HashSet` 以允许按插入顺序进行迭代。 |
| `TreeSet` | 扩展 `AbstractSet` 并实现 `SortedSet` 接口。它使用二叉搜索树按排序顺序存储元素。 |

注意：除了集合类外，一些旧类（如 `Vector`、`Stack`、`Hashtable`）已重构以支持集合。

## 通过 Iterator 和 ListIterator 访问集合

通常，你需要遍历集合中的元素。到目前为止，实现此最简单的方法是使用迭代器，这是一个实现了 `Iterator` 或 `ListIterator` 接口的对象。

`Iterator` 允许你通过遍历集合来获取或移除元素。`ListIterator` 扩展了 `Iterator`，允许对列表进行双向遍历并修改元素。

在通过迭代器访问集合之前，你必须先获取一个。每个集合类都提供一个 `iterator()` 方法，返回一个指向集合起始部分的迭代器。通过使用该迭代器对象，你可以一次一次访问集合中的每个元素。

对于实现 `List` 的集合，你还可以通过调用 `listIterator()` 获取迭代器。列表迭代器允许你按正向或反向访问集合，并且你可以修改元素。否则，`ListIterator` 的用法与 `Iterator` 一致。

## ArrayList 类

`ArrayList` 类扩展了 `AbstractList` 并实现了 `List` 接口。`ArrayList` 支持可以根据需要增长的动态数组。在 Java 中，标准数组是固定长度的。

数组创建后就不能增长或缩小，这意味着我们必须预先知道数组将包含多少元素。为了处理这种情况，集合框架定义了 `ArrayList`。

`ArrayList` 是一个对象引用的变长数组，也就是说，`ArrayList` 的大小可以动态增加或减少。数组列表创建时有一个初始大小。

当超过容量时，集合会自动扩大；当对象被移除时，数组可能会缩小。使用 J2SE 5 引入的泛型功能，可以限制添加到 `ArrayList` 中的元素类型。

注意：旧类 `Vector` 也支持动态数组。

## ArrayList 类的构造函数与方法

| 方法 | 描述 |
| :--- | :--- |
| `public ArrayList(int capacity)` | 构建一个具有指定初始容量的空列表。当元素被添加到数组列表时，容量会自动增长。 |
| `public ArrayList()` | 构建一个初始容量为十的空列表。 |
| `public ArrayList(Collection c)` | 构建一个包含指定集合中元素的列表。顺序取决于集合的 `Iterator` 返回元素的顺序。 |
| `public void trimToSize()` | 反之，如果我们想减少底层 `ArrayList` 对象的数组的大小，使其大小恰好等于当前持有的项数，可以调用 `trimToSize()` 方法。 |
| `public void ensureCapacity(int capacity)` | 虽然 `ArrayList` 对象的容量会随着存储对象而自动增加，但我们可以通过调用 `ensureCapacity()` 方法手动增加 `ArrayList` 对象的容量。在开始时一次增加其容量，可以防止后续多次重新分配。因为重新分配在时间上是昂贵的，防止不必要的重新分配可以提高性能。 |
| `public int size()` | |
| `public boolean isEmpty()` | |
| `public Object clone()` | |
| `public Object[] toArray()` | 在处理 `ArrayList` 时，我们有时可能想要获取一个包含列表内容的实际数组。我们可以通过调用 `toArray()` 方法来实现。我们可能想要将集合转换为数组的原因有几个，例如：为某些操作获得更快的处理时间；将数组传递给没有重载以接受集合的方法；将我们较新的基于集合的代码与不理解集合的旧代码集成。 |
| `public Object[] toArray(Object[] a)` | |
| `public Object get(int index)` | |
| `public Object set(int index, Object element)` | |
| `public boolean add(Object o)` | |
| `public void add(int index, Object o)` | |
| `public Object remove(int index)` | |
| `public boolean remove(Object o)` | |
| `public void clear()` | |
| `public boolean addAll(Collection c)` | |
| `public boolean addAll(int index, Collection c)` | |
| `public boolean contains(Object o)` | |
| `public int indexOf(Object o)` | |
| `public int lastIndexOf(Object o)` | |

### 示例 1

```java
import java.util.*;
class ArrayListTest {
    public static void main(String args[]) {
        ArrayList a1 = new ArrayList();//可以存储不同类型的对象容量为 10
        System.out.println("Initial size of a1 : "+ a1.size());
        a1.add("A");
        a1.add("C");
        a1.add(new Integer(56));
        a1.add("E");
        a1.add("F");
        a1.add(1, "B");
        System.out.println("Size of a1 after additions: "+ a1.size());
        System.out.println("Contents of a1 : "+ a1);
        a1.remove("F");
        a1.remove(2);
        System.out.println("Size of a1 after deletions: "+ a1.size());
        System.out.println("Content of a1  "+ a1);
        ArrayList<String> a2 = new ArrayList<String>(20); //只能添加 String 对象容量为 20
        a2.ensureCapacity(25); //将容量从 20 增加到 25。
        a2.ensureCapacity(22); //容量将不会改变，因为已经多了
        a2.add("A");
        a2.add("B");
    }
}
```

```java
a2.add("C");
a2.add("D");
a2.add("E");
//a2.add(new Integer(5));//无法通过编译
System.out.println("Contents of a2 : "+ a2);
a2.remove("D");
System.out.println(a2);
a2.remove(0);
System.out.println(a2);
a2.clear();
System.out.println(a2);

ArrayList<Integer> a3 = new ArrayList<Integer>(); //只能添加 Integer 对象
a3.add(new Integer(1));
a3.add(new Integer(2));
a3.add(new Integer(3));
a3.add(4); //自动装箱
System.out.println("Contents of a3 : "+ a3);
for(int i=0;i<a3.size();i++)
    System.out.print(a3.get(i)+ " ");
System.out.println();

Object b[]=a3.toArray();
for(int i=0;i<b.length;i++)
    System.out.print((Integer)b[i]+ " ");
System.out.println();
System.out.println("Contents of a3 using iterator: ");
Iterator itr = a3.iterator();
while(itr.hasNext())
{
    int x = ((Integer)itr.next()).intValue();
    System.out.print(x + " ");
}
System.out.println();

// 使用 ListIterator 修改列表
ListIterator<Integer> litr = a3.listIterator();
while(litr.hasNext())
{
    Integer element = litr.next();
    litr.set(element + 10);
}

// 逆序打印列表在到达末尾后才有效。
while(litr.hasPrevious())
{
    Integer element = litr.previous();
    System.out.print(element + " ");
}
System.out.println();
System.out.println("Contents of a3 for each loop");
for(int i : a3) //自动拆箱
    System.out.print(i + " ");
System.out.println();

Integer ia[] = new Integer[a3.size()];
a3.toArray(ia);
int sum= 0;
for(int i=0; i<ia.length; i++)
    sum = sum + ia[i].intValue();
System.out.println("Sum is " + sum);
a3.trimToSize();
```

**输出：**

```
Contents of a2 : [C, D, E]
[C, E]
[E]
[]
Contents of a3 : [1, 2, 3, 4]
1 2 3 4 
1 2 3 4 
Contents of a3 using iterator: 
1 12 13 14 
14 13 12 11 
Contents of a3 for each loop
11 12 13 14 
Sum is 50
```

创建一个新的空集合，其底层的 `HashMap` 实例具有指定的初始容量和指定的负载因子。填充率必须在 0.0 到 1.0 之间。

```java
public java.util.Iterator iterator();
public int size( );
public boolean isEmpty( );
public boolean contains(java.lang.Object);
public boolean add(java.lang.Object);
public boolean remove(java.lang.Object);
public void clear( );
public java.lang.Object clone( );
```

`HashSet` 不保证其元素的顺序，因为哈希过程通常不适用于创建排序集合。如果你需要排序存储，那么另一个像 `TreeSet` 这样的集合是更好的选择。

## 示例 21.3

```java
import java.util.*;
class HashSetTest {
    public static void main (String args[]) {
        HashSet<String> hs = new HashSet<String>();
        hs.add("B");
        hs.add("A");
        hs.add("E");
        hs.add("C");
        hs.add("F");
        System.out.println(hs);
    }
}
```

输出：

`[E, F, A, B, C]`

元素并不是按排序顺序存储的，精确输出可能会有所不同。

## LinkedHashSet 类

`LinkedHashSet` 类扩展了 `HashSet` 并没有添加任何自己的成员。`LinkedHashSet` 类维护了集合中条目的链表列表，按照它们被插入的顺序排列。

这也是它们在对 `LinkedHashSet` 对象调用 `toString()` 方法时返回的字符串中的顺序。要查看 `LinkedHashSet` 的效果，请尝试将前面的程序中的 `HashSet` 替换为 `LinkedHashSet`。输出将是：`[B, A, E, C, F]`。这是元素插入的顺序。

## TreeSet 类

`TreeSet` 是 `Set` 接口的实现，它使用树进行存储。对象按升序排序顺序存储。访问和检索速度非常快，这使得在存储大量必须快速找到排序信息时，`TreeSet` 是一个极佳的选择。

### 构造函数

它有以下构造函数：

- `TreeSet()`：创建一个新的空集合，根据元素顺序排序。
- `TreeSet(Collection c)`：创建一个新的集合，包含指定集合中的元素并按自然顺序排序。
- `TreeSet(Comparator c)`：创建一个新的空集合，按照比较器排序。
- `TreeSet(SortedSet ss)`：创建一个新的集合，包含指定的排序集合中的元素并采用相同的排序方式。

```java
public java.util.Iterator iterator();
public java.util.Iterator descendingIterator();
public int size( );
public boolean isEmpty( );
public boolean contains(java.lang.Object);
public boolean add(java.lang.Object);
public void clear( );
public boolean addAll(java.util.Collection);
public java.lang.Object clone();
```

### 示例 1.4

```java
import java.util.*;
class TreeSetTest {
    public static void main (String args[]) {
        TreeSet<String> ts = new TreeSet<String>();
        ts.add("C");
        ts.add("A");
        ts.add("D");
        ts.add("E");
        ts.add("F");
        ts.add("B");
        // 显示元素。
        Iterator i= ts.iterator();
        while(i.hasNext()) {
            Object o = i.next();
            System.out.println(o + " ");
        }
    }
}
class MyComp implements Comparator {
    public int compare(Object a, Object b) {
        String aStr, bStr;
        aStr = (String) a;
        bStr = (String) b;
        // 反转比较。
        return bStr.compareTo(aStr);
    }
}
```

输出：

`[A, B, C, D, E, F]`

`TreeSet` 和 `TreeMap` 都是按排序顺序存储元素。然而，正是 `comparator` 定义了什么是“排序顺序”的确切含义。

默认情况下，这些类使用 `java` 所说的“自然顺序”来存储元素，这通常是我们预期的顺序。如果我们想以不同的方式对元素进行排序，可以在构造集合或映射时指定一个 `comparator` 对象。这样做使我们能够精确地控制元素在排序集合或映射中的存储方式。

`comparator` 接口定义了两个方法：如之前所述的 `compare()` 和 `equals()`。`compare()` 方法比较两个元素的顺序：

`int compare(T obj1, T obj2)`

- `obj1` 和 `obj2` 是要比较的对象。



- 如果对象相等，则该方法返回零。
- 如果 `obj1` 大于 `obj2`，则返回正值。
- 如果 `obj1` 小于 `obj2`，则返回负值。
- 如果对象的类型不兼容比较，这些方法可能会抛出 `ClassCastException`。通过重写 `compare()`，你可以更改对象排序的方式。例如，要按逆序排序，可以创建一个反转比较结果的 `comparator`。

`equals()` 方法测试对象是否等于调用的比较器：`boolean equals(Object obj)`

输出：

```
F E D C B A
```

# 使用 Map

`map` 是一个存储键和值之间关联（或键/值对）的对象。给定键，我们可以找到它的值。

键和值都是对象。键必须是唯一的，但值可以重复。某些 map 接受 `null` 键和 `null` 值，而另一些不能。

## Map 接口

基于以下接口的 Map 类：

| 接口 | 描述 |
| :--- | :--- |
| `Map` | 将唯一的键映射到值。 |
| `Map.Entry` | map 中的元素（键/值对）。 |
| `SortedMap` | 扩展 `Map`，使键按升序排列。 |

## Map 接口

`Map` 接口将唯一的键映射到值。给定键和值，你可以将值存储在 `Map` 对象中。存储值后，你可以使用其键检索它。

方法摘要：

- `void clear()`：从此 map 中移除所有映射（可选）。
- `boolean containsKey(Object key)`：如果此 map 包含指定键的映射，则返回 true。
- `boolean containsValue(Object value)`：如果此 map 将一个或多个键映射到指定的值，则返回 true。

## Map 接口方法详情

| 方法 | 描述 |
| :--- | :--- |
| `Set entrySet()` | 返回一个包含 map 中条目的集合。该集合包含类型为 `Map.Entry` 的对象。此方法提供了调用 map 的集合视图。 |
| `boolean equals(Object o)` | 如果 `o` 是 `Map` 且包含这些条目，则返回 true，否则返回 false。 |
| `Object get(Object key)` | 返回此 map 映射到指定 `key` 的值。 |
| `int hashCode()` | 返回此 map 的哈希码值。 |
| `boolean isEmpty()` | 如果此 map 不包含任何键值映射，则返回 true。 |
| `Set keySet()` | 返回包含此 map 中所有键的集合视图。 |
| `Object put(Object key, Object value)` | 将指定的 `value` 与此 map 中的指定 `key` 关联（可选操作），覆盖与该键关联的任何旧值。如果该键已存在，则返回 `null`。否则，返回与该键关联的旧值。 |
| `void putAll(Map m)` | 将从指定 map 的所有映射拷贝到此 map（可选操作）。 |
| `Object remove(Object key)` | 如果此 map 中存在该键，则从 map 中移除该键的映射（可选操作）。 |
| `int size()` | 返回此 map 中键值映射的数量。 |
| `Collection values()` | 返回包含此 map 中所有值的集合视图。 |

当调用 map 中不存在任何项时，某些方法会抛出 `NoSuchElementException`。当对象与 map 中的元素不兼容时，会抛出 `ClassCastException`。

如果尝试使用空对象且 `Map` 不允许 `null`，则会抛出 `NullPointerException`。当尝试更改不可修改的 map 时，会抛出 `UnsupportedOperationException`。

`Map` 围绕两个基本操作 `get()` 和 `put()` 展开。

Map 不是集合（Collections），因为它们没有实现 `Collection` 接口，但我们可以获取 map 的集合视图。集合视图意味着 map 整合到集合框架中的方式。

## SortedMap 接口

`SortedMap` 接口扩展了 `Map`。它确保条目按升序顺序维护。

### 方法摘要

| 方法 | 描述 |
| :--- | :--- |
| `Comparator comparator()` | 返回与此排序 map 关联的比较器，如果使用其键的自然排序，则返回 `null`。 |
| `Object firstKey()` | 返回此排序 map 中的第一个键。 |
| `SortedMap headMap(Object toKey)` | 返回此排序 map 的部分视图，其键严格小于 `toKey`。 |
| `Object lastKey()` | 返回此排序 map 中的最后一个键。 |
| `SortedMap subMap(Object fromKey, Object toKey)` | 返回此排序 map 的部分视图，其键大于或等于 `fromKey` 且不包含 `toKey`（注：原文此处描述有遗漏）。 |
| `SortedMap tailMap(Object fromKey)` | 返回此排序 map 的部分视图，其键大于或等于 `fromKey`。 |

当调用 map 中不存在任何项时，某些方法会抛出 `NoSuchElementException`。当对象与 map 中的元素不兼容时，会抛出 `ClassCastException`。

如果尝试使用空对象且 `Map` 不允许 `null`，则会抛出 `NullPointerException`。

## Map.Entry 接口

`Map.Entry` 接口允许你处理 map 条目。回想 `Map` 接口声明的 `entrySet()` 方法返回一个包含 map 条目的集合。该集合中的每个元素都是一个 `Map.Entry` 对象。

### 方法摘要

| 方法 | 描述 |
| :--- | :--- |
| `boolean equals(Object o)` | 将指定的对象与此条目进行等值性比较。如果 `o` 是一个 `Map.Entry` 对象，且其键和值与调用对象的键相等，则返回 true。 |
| `Object getKey()` | 返回与此条目对应的键。 |
| `Object getValue()` | 返回与此条目对应的值。 |
| `int hashCode()` | 返回此 map 条目的哈希码值。 |
| `Object setValue(Object value)` | 用指定的 `value` 替换此条目对应的值（可选操作）。如果 `value` 不是 map 的正确类型，则抛出 `ClassCastException`。如果 `value` 为 `null` 且 map 不允许空键，则抛出 `NullPointerException`。如果 map 无法更改，则抛出 `UnsupportedOperationException`。 |

## Map 类

多个类提供了 map 接口的实现。

| 类 | 描述 |
| :--- | :--- |
| `AbstractMap` | 此类提供了 map 接口的骨架实现，以减少实现此接口所需的努力。 |
| `HashMap` | 基于哈希表的 map 接口实现。扩展 `AbstractMap` 类。 |
| `TreeMap` | 扩展 `AbstractMap` 并实现 `SortedMap` 接口以使用树。 |
| `LinkedHashMap` | 扩展 `HashMap` 以允许插入顺序迭代。 |

`AbstractMap` 是所有具体 map 实现的超类。

## HashMap 类

`HashMap` 类使用哈希表来实现 `Map` 接口。这使得 `get()` 和 `put()` 等基本操作的执行时间即使对于大型集合也能保持常数级。

### 构造函数

`HashMap` 具有以下构造函数：

- `HashMap()`：构造一个具有默认容量(16) 和默认负载因子的空 `HashMap`。
- `HashMap(int initialCapacity)`：构造一个具有指定初始容量的空 `HashMap`。
- `HashMap(Map m)`：构造一个具有指定 map 映射的空 `HashMap`，默认负载因子为 0.75。

`HashMap` 类扩展了 `AbstractMap` 并实现了 `Map`。它没有添加任何自己的方法。你应该注意，哈希 map 不保证其元素的顺序。

### 示例 21.6

```java
import java.util.*;
class HashMapTest {
    public static void main(String args[]) {
        HashMap<String,Integer> hm = new HashMap<String,Integer>();
        hm.put("C",100);
        hm.put("C++",1000);
        hm.put("Java",1500);
        Set s = hm.entrySet();
        Iterator itr = s.iterator();
        while(itr.hasNext()) {
            Map.Entry me = (Map.Entry) itr.next();
            System.out.print(me.getKey() + ": ");
            System.out.println(me.getValue());
        }
        System.out.println();
        int fees = ((Integer)hm.get("Java")).intValue();
        hm.put("Java", fees + 1000);
        System.out.println("New Fees of Java:"+hm.get("Java"));
    }
}
```

输出：

```
C: 100
C++: 1000
Java: 1500

New Fees of Java:2500
```

## TreeMap 类

`TreeMap` 类通过树来实现 `Map` 接口。`TreeMap` 提供了一种按排序存储键值对有效方法，树 map 保证其元素按键顺序排序。

### 构造函数

`TreeMap` 具有以下构造函数：

- `TreeMap()`：根据键的自然排序构造一个空 map。
- `TreeMap(Comparator c)`：根据给定的比较器构造一个新的空 map。
- `TreeMap(Map m)`：构造一个包含指定 map 映射的新 map，按键的自然排序。
- `TreeMap(SortedMap m)`：构造一个包含指定 `SortedMap` 映射的新 map，按相同的排序。

`TreeMap` 实现了 `SortedMap` 并扩展了 `AbstractMap`。它没有定义任何自己的额外方法。

### 示例 21.7

以下程序重构了前面的示例，使其使用 `TreeMap`。键将按地名排序。可以通过在创建 map 时指定比较器来更改此行为，以便键可以按姓或任何顺序排序。

```java
import java.util.*;
class TreeMapTest {
    public static void main(String args[]) {
        TreeMap <String,Integer> tm = new TreeMap<String,Integer>();
        tm.put("C",100);
        tm.put("C++",1000);
        tm.put("Java",1500);
        Set<Map.Entry<String,Integer>> s = tm.entrySet();
        for(Map.Entry<String,Integer> me : s)
        {
            System.out.print(me.getKey() + ": " );
            System.out.println(me.getValue() );
        }
        System.out.println();
        int fees = tm.get("Java");
        tm.put("Java", fees + 1000);
        System.out.println("New fees of Java:"+tm.get("Java"));
    }
}
```

输出：

```
C: 100
C++: 1000
Java: 1500
New fees of Java:2500
```

## LinkedHashMap 类

Java 2 版本 1.4 增加了 `LinkedHashMap` 类。该类扩展了 `HashMap`。`LinkedHashMap` 在映射中维护了一个项目的双链表，并按照它们插入的顺序排列。

这允许对映射进行插入顺序的迭代。也就是说，在遍历 `LinkedHashMap` 时，元素将按照它们被插入的顺序返回。

# 遗留类和接口

原始的 `java.util` 版本并不包含集合框架。相反，它定义了几个类和一个接口，提供了一种存储对象的临时方法。随着 Java 2 增加了 `Collection`，原始类中的几个类被重新设计以支持 `Collection` 接口。

因此，它们与框架完全兼容。虽然实际上没有类被废弃，但其中有一个类已经过时了。当然，当集合的功能重复了遗留类的功能时，你通常希望在新代码中使用集合。通常情况下，支持遗留类是因为仍然有代码在使用它们。

某些集合类是同步的，但所有的遗留类都是同步的。这一操作在某些情况下可能非常重要。当然，我们也可以轻松地对集合进行同步。

## Enumeration 接口

`Enumeration` 接口定义了用于枚举（一次获取一个）对象集合中元素的方法。遗留接口已被 `Iterator` 取代。

尽管 `Enumeration` 没有被废弃，但在新代码中它被认为是过时的。然而，它被遗留类（如 `Vector` 和 `Properties`）使用的几个方法使用，被其他几个 API 类使用，并且最近在应用代码中广泛使用。

`Enumeration` 规定了以下两个方法：

- `boolean hasMoreElements()`：测试此枚举器是否包含更多元素。当还有更多元素待提取时，此方法必须返回 true。当所有元素都已枚举完毕时，返回 false。
- `Object nextElement()`：如果此枚举器对象至少多一个元素可以提供，则返回该枚举器的下一个元素。

## Vector 类

`Vector` 实现了一个动态数组。它与 `ArrayList` 类似，但有两个区别：

1. `Vector` 是同步的，并且 `Vector` 包含许多不是集合框架一部分遗留方法。
2. 随着集合的出现，`Vector` 被重新设计以扩展 `AbstractList` 并实现 `List` 接口。

这意味着 `Vector` 与集合完全兼容，可以使用增强 for 循环对 vector 的内容进行迭代。

### 构造函数

`Vector` 有几个构造函数：

- `Vector()`：创建一个初始容量为 10 的空 vector。
- `Vector(int initialCapacity)`：创建一个具有指定初始容量的空 vector。
- `Vector(Collection c)`：创建一个包含指定集合元素的 vector。
- `Vector(int initialCapacity, int capacityIncrement)`：创建一个具有指定初始容量和容量增量的空 vector。

### 方法摘要

除了列表方法外，`Vector` 还定义了几个遗留方法：

- `void addElement(Object obj)`：将指定的对象添加到 vector 的末尾。
- `int capacity()`：返回当前容量。
- `Object clone()`：返回此 vector 的副本。
- `void copyInto(Object[] array)`：将组件复制到指定的数组中。
- `Object elementAt(int index)`：返回指定索引处的组件。
- `Enumeration elements()`：返回组件的枚举器。
- `void ensureCapacity(int minCapacity)`：将容量增加到至少 `minCapacity`。
- `Object firstElement()`：返回 vector 的第一个组件。
- `boolean isEmpty()`：测试此 vector 是否没有组件。
- `Object lastElement()`：返回 vector 的最后一个组件。
- `int lastIndexOf(Object element)`：返回指定对象最后一次出现的索引。
- `int lastIndexOf(Object element, int index)`：从索引开始搜索指定的对象。
- `void removeAllElements()`：从此 vector 中删除所有组件并将大小置零。
- `boolean removeElement(Object obj)`：从此 vector 中移除参数第一次索引出现的项。
- `void removeElementAt(int index)`：删除指定索引处的组件。
- `void removeRange(int fromIndex, int toIndex)`：从此列表中删除所有索引在 `fromIndex`（包含）和 `toIndex`（不包含）之间的元素。



- `void setElementAt(Object obj, int index)`：将此 vector 指定索引处的组件设置为指定的对象。
- `void setSize(int newSize)`：设置此 vector 的大小。
- `int size()`：返回此 vector 中组件的数量。
- `void trimToSize()`：将 vector 的容量设置为其当前持有的元素数量。

由于 `vector` 实现了 `List`，你可以像使用 `ArrayList` 实例一样使用 vector。你也可以使用遗留方法操作 vector。

### 示例 21.8

```java
import java.util.*;
class VectorTest {
    public static void main(String args[]) {
    }
}
```

```java
{
    Vector<Integer> v1 = new Vector<Integer>();
    System.out.println("Size is " + v1.size() + " Capacity is " + v1.capacity());
    for(int i=1;i<=15;i++)
        v1.addElement(i);
    System.out.println("Size is " + v1.size() + " Capacity is " + v1.capacity());
    Iterator itr=v1.iterator();
    while(itr.hasNext())
    {
        System.out.print(itr.next() + " ");
    }
    System.out.println();
    for(int i:v1)
        System.out.print(i + " ");
    System.out.println();
    Enumeration e=v1.elements();
    while(e.hasMoreElements())
    {
        System.out.print(e.nextElement() + " " );
    }
    System.out.println();
    Integer a[]=new Integer[v1.size()];
    v1.copyInto(a);
    for(int i=0;i<a.length;i++)
        System.out.print(a[i] + " ");
    System.out.println();
    System.out.println("First Element= " + v1.firstElement());
    System.out.println("Last Element= " + v1.lastElement());
}
```

输出:

```
Size is 0 Capacity is 10
Size is 15 Capacity is 20
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15
First Element= 1
Last Element= 15
```

## Stack 类

`Stack` 是 `Vector` 的子类，实现了一个标准的后进先出（LIFO）栈。`Stack` 只定义了创建一个空栈的默认构造函数，包含了 `Vector` 定义的所有方法，并添加了一些自己的方法。

#### 方法摘要

- `empty()`: 测试栈是否为空。
- `peek()`: 返回此栈顶部的对象，但不将其从栈中移除。
- `pop()`: 移除栈顶部的对象并将该对象作为此栈的值返回。
- `push(Object item)`: 将一个项推入栈的顶部。
- `search(Object o)`: 返回对象在栈中的位置（从 1 开始计数）。

#### 示例

以下示例创建了一个栈，向其推入了几个 `Integer` 对象，然后将它们弹出：

```java
import java.util.*;
class Stack {
    public static void main(String args[]) {
        Stack<Integer> st=new Stack<Integer>();
        st.push(0);
        st.push(20);
        st.push(30);
        System.out.println("Stack is " + st);
        System.out.println("30 is at pos " + st.search(30));
        try {
            Integer iobj=st.pop();
            System.out.println("Popped value is " + iobj.intValue());
            iob = st.peek();
            System.out.println("Peek value is " + iobj.intValue());
        } catch(EmptyStackException e) {
            System.out.println("Stack is " + e);
        }
    }
}
```

输出:

```
Stack is [0, 20, 30]
30 is at pos 1
Popped value is 30
Peek value is 20
```

### Dictionary 类

`Dictionary` 是一个表示键值存储的抽象类。像 `Map` 一样，`dictionary` 可以被认为是一个键/值列表。它已经被 `Map` 取代。

`Dictionary` 定义的抽象方法有：

- `elements()`: 返回此字典中所有值的枚举。
- `get(Object key)`: 返回键所映射的值。
- `isEmpty()`: 测试此字典是否没有映射键。
- `keys()`: 返回此字典中所有键的枚举。
- `put(Object key, Object value)`: 将指定的键映射到此字典中的指定值。
- `remove(Object key)`: 从此字典中移除键（以及相应的值）。
- `size()`: 返回此字典中条目（不同键）的数量。

### Hashtable 类

`Hashtable` 是 `Dictionary` 的具体实现。然而，Java 2 重新设计了 `Hashtable`，使其实现了 `Map` 接口。它与 `HashMap` 类似，但它是同步的。`Hashtable` 在哈希表中存储键/值对。使用 `Hashtable` 时，你指定一个用作键的对象以及你想与该键关联的值。然后对键进行哈希处理，生成的哈希码被用作在表中存储值的索引。

`Hashtable` 只能存储重写了 `hashCode()` 和 `equals()` 方法的对象。通常使用字符串对象作为键，因为它已经实现了 `hashCode()` 和 `equals()`。

### 构造函数

`Hashtable` 具有以下构造函数：

- `Hashtable()`: 构建一个新的、具有默认初始容量（11）和负载因子（0.75）的空 `Hashtable`。
- `Hashtable(int initialCapacity)`: 构建一个新的具有指定初始容量和默认负载因子（0.75）的空 `Hashtable`。
- `Hashtable(int initialCapacity, float loadFactor)`: 构建一个新的具有指定初始容量和指定负载因子的空 `Hashtable`。
- `Hashtable(Map m)`: 构建一个与指定的 `Map` 具有相同映射的新 `hashtable`。

`Hashtable` 还定义了旧版方法：

- `clear()`: 清空此哈希表，使其不包含任何键。
- `clone()`: 创建此哈希表的浅层拷贝。
- `contains(Object value)`: 测试此 `Hashtable` 中是否有某个键映射到指定的值。
- `containsKey(Object key)`: 测试指定的对象是否是此 `Hashtable` 中的一个键。
- `containsValue(Object value)`: 如果此 `Hashtable` 将一个或多个键映射到此值，则返回 true。
- `elements()`: 返回此 `Hashtable` 中所有值的枚举。
- `entrySet()`: 返回此 `Hashtable` 包含的条目的集合视图。

## Hashtable 方法总结

| 方法 | 描述 |
| :--- | :--- |
| `boolean equals(Object o)` | 比较指定的对象与此映射是否相等。 |
| `Object get(Object key)` | 返回指定的键在此 hashtable 中映射的值。 |
| `int hashCode()` | 根据 `Map` 接口的定义，返回此 `Map` 的哈希值。 |
| `boolean isEmpty()` | 测试此 hashtable 是否没有将键映射到值。 |
| `Enumeration keys()` | 返回此 hashtable 中所有键的枚举器。 |
| `Set keySet()` | 返回此 hashtable 中包含的键的集合视图。 |
| `Object put(Object key, Object value)` | 将指定的键映射到此 hashtable 中指定的值上。 |
| `void putAll(Map m)` | 将指定 `Map` 中的所有映射复制到此 Hashtable 中；这些映射将替换此 Hashtable 对指定 `Map` 中当前任何键的已有映射。 |
| `protected void rehash()` | 增加哈希表的大小并对其所有键进行重新哈希。 |
| `Object remove(Object key)` | 从此 hashtable 中移除键（及其对应的值）。 |
| `int size()` | 返回此 hashtable 中条目（不同键）的数量。 |
| `String toString()` | 返回此 hashtable 对象的字符串表示，形式为条目集合，用括号包裹并用 ASCII 字符“,”（逗号和空格）分隔。 |
| `Collection values()` | 返回此 Hashtable 中包含的所有值的集合。 |

### 示例 21.10

以下示例使用 `Hashtable` 来存储存款人的姓名及其当前余额。

```java
import java.util.*;

class HashtableTest {
    public static void main(String args[]) {
        Hashtable<String,Integer> ht = new Hashtable<String,Integer>();
        ht.put("C", 1000);
        ht.put("Java", 1500);
        ht.put("Vb", 1500);

        // 使用 Enumeration 显示列表
        Enumeration<String> courses;
        courses = ht.keys();
        while(courses.hasMoreElements()) {
            String s1 = courses.nextElement();
            System.out.println("Course= " + s1 + " Fees= " + ht.get(s1));
        }

        // 使用 for each 显示列表
        Set s = ht.keySet();
        for(Object ob : s) {
            System.out.println("Course= " + (String)ob + " Fees= " + ht.get((String)ob));
        }

        Integer fees = ht.get("Java");
        ht.put("Java", fees + 1000);
        System.out.println("After Update ");

        // 使用 Iterator 显示列表
        Iterator itr = s.iterator();
        while(itr.hasNext()) {
            String s1 = (String)itr.next();
            System.out.println("Course= " + s1 + " Fees= " + ht.get(s1));
        }
    }
}
```

**输出：**

```
Course= Java Fees= 1500
Course= Vb Fees= 1500
Course= C Fees= 1000
Course= Java Fees= 1500
Course= Vb Fees= 1500
Course= C Fees= 1000
After Update
Course= Java Fees= 2500
Course= Vb Fees= 1500
Course= C Fees= 1000
```

## Properties 类

`Properties` 是 `Hashtable` 的子类。它用于维护一个值列表，其中键是 `String` 且值也是字符串。许多 Java 类都使用 `Properties` 类。例如，在获取环境变量值时，`System.properties()` 返回的对象就是该类型。

### 实例变量

- `defaults`: 该变量持有一个与 `Properties` 对象关联的默认属性列表。

### 构造函数

- `Properties()`: 创建一个没有默认值的空属性列表。
- `Properties(Properties defaults)`: 创建一个带有指定默认值的空属性列表。

除了继承自 `Hashtable` 的方法外，`Properties` 还定义了一些更多方法。`Properties` 还包含一个已过用的方法 `save()`。它已被 `store()` 取代，因为 `save()` 无法正确处理错误。

### 方法总结

| 方法 | 描述 |
| :--- | :--- |
| `String getProperty(String key)` | 返回与键关联的值。如果键既不在列表中也不在默认属性列表中，则返回 null 对象。 |
| `String getProperty(String key, String defaultValue)` | 返回与键关联的值。如果键既不在列表中也不在默认属性列表中，则返回默认属性。 |
| `void list(PrintStream out)` | 将此属性列表打印到指定的输出流。 |
| `void list(PrintWriter out)` | 将此属性列表打印到指定的输出流。 |
| `void load(InputStream inStream)` | 从输入流读取属性列表（键和元素对）。 |
| `Enumeration propertyNames()` | 返回所有键的枚举器。这包括在默认属性中找到的键。 |
| `void save(OutputStream out, String comments)` | 已弃。如果在保存属性列表时发生 I/O 错误，此方法不会抛出 `IOException`。保存属性列表的首优方法是通过 `store(OutputStream out, String comments)` 方法。 |
| `Object setProperty(String key, String value)` | 调用 `Hashtable` 的 `put` 方法。返回与键关联的值，如果没有关联则返回 null。 |
| `void store(OutputStream out, String comments)` | 将此属性列表（键和元素对）写入输出流，格式适用于使用 `load` 方法加载到 `Properties` 表。 |

### 示例 21.11

以下程序创建了一个属性列表，其中键是课程名称，值是课程时长。



```java
import java.util.*;

class PropertiesTest {
    public static void main(String args[]) {
        Properties def = new Properties();
        def.put("C", "2 months");
        def.put("C++", "3 months");
        Properties courses = new Properties(def);
        courses.put("Java", "4 months");
        courses.put("Dot Net", "6 months");

        System.out.println("Duration of Java is " + courses.getProperty("Java"));
        System.out.println("Duration of C is " + courses.getProperty("C"));
        System.out.println("Duration of VB is " + courses.getProperty("VB"));

        System.out.println("List of all Courses:-");
        Set s = courses.keySet();
        for(Object ob : s) {
            System.out.println("Duration of Course " + (String)ob + " is " + courses.getProperty((String)ob, "not found"));
        }

        Iterator itr = s.iterator();
        while(itr.hasNext()) {
            String s1 = (String)itr.next();
            System.out.println("Duration of Course " + s1 + " is " + courses.getProperty(s1, "Not Found"));
        }
    }
}
```

**输出：**

```
Duration of Java is 4 months
Duration of C is 2 months
Duration of VB is Not Found
List of all Courses:-
Duration of Course Java is 4 months
Duration of Course Dot Net is 6 months
```

Dot Net 课程时长为 6 个月

## 使用 `store()` 和 `load()`

`Properties` 最实用的方面之一是 `Properties` 对象中包含的信息可以通过 `store()` 和 `load()` 轻松地存储到磁盘或从磁盘加载。

你可以在任何时候将 `Properties` 对象写入流或将其读回。这使得属性列表在实现简单数据库时特别方便。

例如，以下程序使用属性列表创建一个简单的计算机电话簿，用于存储姓名和电话号码。要查找某人的电话，只需输入其姓名即可。

该程序使用 `store()` 和 `load()` 方法来存储和检索列表。当程序执行时，它首先尝试从名为 `phonebook.dat` 的文件中加载列表。如果该文件存在，则加载列表。然后你可以向列表中添加内容。

![Big-Sun-Icon-Smile-Cartoon-Kid](img/image01300.jpeg) ![Big-Sun-Icon-Smile-Cartoon-Kid](img/image01300.jpeg) ![Big-Sun-Icon-Smile-Cartoon-Kid](img/image01300.jpeg)

![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg) ![11](img/image01212.jpeg)

![STAR-LOGO-2013](img/image01301.jpeg)

章节

∞ 22 ∞

## 面向开发者的 Java 8 特性

### Lambda、函数式接口

Java 8 已于 2014 年 3 月 18 日发布，现在是时候为开发者寻找 Java 8 的特性了。目前关于 Java 8 的材料还足够的。但在经过大量努力后，我写了 Java 8 中引入的一些我非常期待的重要特性，包括：

1. `Iterable` 接口中的 `forEach()` 方法。
2. 接口中的 `default` 和 `static` 方法。
3. `函数式接口 (Functional Interfaces)` 和 `Lambda 表达式 (Lambda Expressions)`。
4. 用于对 `Collections` 进行批量数据操作的 `Java Stream API`。
5. `Java Time API`。
6. `Collection API` 的改进。
7. `Concurrency API` 的改进。
8. `Java IO` 的改进。
9. `其他核心 API` 的改进。

让我们简单查看一下这些 Java 8 特性。我将提供一些代码片段以帮助更好地理解，因此如果你想在 Java 8 中运行程序，必须按照以下步骤设置 Java 8 环境。

下载 `JDK8` 并安装它。安装过程与其他 Java 版本一样简单。在 Java 中编写、编译和运行程序需要安装 `JDK`。

注意：当前的 Eclipse IDE 不支持 Java 8，因此你必须从 eclipse.org 下载适用于 Java 8 的 Eclipse。针对 Mac OS、Windows 和 Linux 系统有不同版本的稳定构建，请下载最新版本以获得大多数功能。

我今天（2014 年 7 月 28 日）刚刚检查过，Eclipse Kepler 4.3.2 SR2 程序包可以用于 Java 8。你需要先下载它，然后从 Eclipse 市场中心安装 “Java 8 support for Eclipse Kepler SR2” 插件。我试过了，它看起来运行良好。

### 1. `Iterable` 接口中的 `forEach()` 方法

每当我们需要遍历 `Collection` 时，都需要创建一个 `Iterator`，其全部目的就是迭代，然后我们在循环中为 `Collection` 中的每个元素编写业务逻辑。如果迭代器使用不当，可能会得到 `ConcurrentModificationException`。

Java 8 在 `java.lang.Iterable` 接口中引入了 `forEach` 方法，这样我们在编写代码时只需关注业务逻辑即可。`forEach` 方法接受 `java.util.function.Consumer` 对象作为参数，这有助于将我们的业务逻辑保持在独立的位置，以便我们复用。让我们通过简单的示例来看 `forEach` 的用法。

| Java8ForEachExample.java |

```java
package com.journaldev.java8.foreach;
import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;
import java.util.function.Consumer;
import java.lang.Integer;
public class Java8ForEachExample {
    public static void main(String[] args) {
        //creating sample Collection
        List<Integer> myList = new ArrayList<Integer>();
        for(int i=0; i<10; i++) myList.add(i);
        //traversing using Iterator
        Iterator<Integer> it = myList.iterator();
        while(it.hasNext()){
            Integer i = it.next();
            System.out.println("Iterator Value::"+i);
        }
        //traversing through forEach method of Iterable with anonymous class
        myList.forEach(new Consumer<Integer>() {
            public void accept(Integer t) {
                System.out.println("forEach class Value::"+t);
            }
        });
        //traversing with Consumer interface
        MyConsumer action = new MyConsumer();
        myList.forEach(action);
    }
}
//Consumer implementation that can be reused
class MyConsumer implements Consumer<Integer>{
    public void accept(Integer t) {
        System.out.println("Consumer impl::"+t);
    }
}
```

行数可能会增加，但 `forEach` 方法有助于实现迭代逻辑。

`forEach` 方法有助于实现关注点分离。

### 2. 接口中的 `default` 和 `static` 方法

Java 8 增强了接口方法体。

`Iterable` 接口中的 `forEach` 方法如下：

```java
default void forEach(Consumer<? super T> action) {
    Objects.requireNonNull(action);
    for (T t : this) {
        action.accept(t);
    }
}
```

记住：

我们知道 Java 不支持多重继承，因为这会导致“菱问题”。所以如何通过接口来处理，由于接口现在是抽象类。

解决方案是编译器会抛出异常，我们需要在类中提供实现逻辑。

| Interface1.java |

```java
package com.journaldev.java8.defaultmethod;
@FunctionalInterface
public interface Interface1 {
    void method1(String str);
    default void log(String str) {
        System.out.println("I1 logging::"+str);
    }
    static void print(String str) {
        System.out.println("Printing "+str);
    }
    //尝试覆盖 Object 方法会导致编译错误，“A default method cannot override a method from java.lang.Object"
    // default String toString(){
    //     return "i1";
    // }
}
```

| Interface2.java |

```java
package com.journaldev.java8.defaultmethod;
@FunctionalInterface
public interface Interface2 {
    void method2();
    default void log(String str) {
        System.out.println("I2 logging::"+str);
    }
}
```

注意到两个接口都有公共方法 `log()` 的实现逻辑。

| MyClass.java |



```java
package com.journaldev.java8.defaultmethod;
public class MyClass implements Interface1, Interface2 {
    @Override
    public void method2() {
    }
    @Override
    public void method1(String str) {
    }
    // 如果没有它自己的 log() 实现，MyClass 将无法编译
    @Override
    public void log(String str){
        System.out.println("MyClass logging::"+str);
        Interface1.print("abc");
    }
}
```

你可以看到 `Interface1` 有一个静态方法实现，它被用于 `MyClass.log()` 方法实现。Java 8 在 `Collection API` 中大量使用默认和静态方法，添加默认方法使我们的代码保持向后兼容。

如果层次结构中的任何类具有相同签名的方法，那么默认方法将失效。由于任何实现接口的类已经以 `Object` 为父类，如果我们在接口中有 `equals()`、`hashCode()` 默认方法，它们将变得失效。这就是为什么为了清晰起见，接口不允许拥有 `Object` 类的默认方法。

要了解 Java 8 接口更改的完整信息，请阅读下方的 Java 8 接口更改。

Java 8 最大的设计变化之一是接口概念引入。在 Java 7 之前，接口中只能包含方法声明。但从 Java 8 开始，我们可以在接口中拥有 `default methods`（默认方法）和 `static methods`（静态方法）。

设计接口一直是一项辛苦的工作，因为如果我们想在接口中添加额外方法，将需要修改所有的实现类。

随着接口变旧，实现它的类数量可能会增加到无法扩展接口的程度。这就是为什么在设计应用程序时，大多数框架都会提供一个基础实现类，然后我们扩展它并重写适用于我们应用程序的方法。让我们来看看接口默认方法、静态方法以及引入它们的原因。

## 接口默认方法

要在接口中创建默认方法，我们需要在方法签名处使用 `default` 关键字。例如：

### Interface1.java

```java
package com.journaldev.java8.defaultmethod;
public interface Interface1 {
    void method1(String str);
    default void log(String str){
        System.out.println("I1 logging::"+str);
        print(str);
    }
}
```

注意 `log(String str)` 是 `Interface1` 中的默认方法。现在当一个类实现 `Interface1` 时，并没有强制为默认方法提供实现。这一特性将帮助我们通过添加额外方法来扩展接口，我们只需要提供默认实现即可。假设我们另一个带有以下方法的接口：

### Interface2.java

```java
package com.journaldev.java8.defaultmethod;
public interface Interface2 {
    void method2();
    default void log(String str){
        System.out.println("I2 logging::"+str);
    }
}
```

我们知道 Java 不允许继承多个类，因为这会导致“菱形问题”（Diamond Problem），编译器无法决定使用哪一个父类的方法。有了默认方法，接口也会出现菱形问题。

因为如果一个类同时实现了 `Interface1` 和 `Interface2` 且没有实现公共的默认方法，编译器将无法选择哪一个。

扩展多个接口是 Java 中不可或缺的一部分，你可以在 Java 核心类以及大多数企业级应用框架中发现它。因此，为了确保这个问题不会在接口中发生，强制要求为公共的默认方法提供实现。

所以，如果一个类同时实现了上述两个接口，它将必须为 `log()` 方法提供实现，否则编译器将抛出错误。一个实现了 `Interface1` 和 `Interface2` 的简单类如下：

### MyClass.java

```java
package com.journaldev.java8.defaultmethod;
public class MyClass implements Interface1, Interface2 {
    @Override
    public void method2() {
    }
    @Override
    public void method1(String str) {
    }
    @Override
    public void log(String str){
        System.out.println("MyClass logging::"+str);
        Interface1.print("abc");
    }
}
```

**关于接口默认方法的要点：**

- 默认方法将帮助我们扩展接口，而不必破坏实现类。
- 默认方法缩小了接口和抽象类之间的差异。
- 默认方法将帮助我们避免工具类，例如所有的 Collections 类方法都可以直接提供在接口本身中。
- 默认方法将帮助我们移除基础实现类，我们可以提供默认实现，而实现类可以选择重写哪一个。
- 引入默认方法的主要原因之一是为了增强 Java 8 中的 Collections API 以支持 lambda 表达式。
- 如果层级结构中的任何类具有相同签名的方法，那么默认方法将变得无关。默认方法不能重写 `java.lang.Object` 的方法。原因非常简单，因为 Object 是所有 Java 类的基类。所以即使我们在接口中将 Object 类的方法定义为默认方法，它也是用的，因为始终会使用 Object 类的方法。因此为了避免混淆，我们不能拥有重写 Object 类方法的默认方法。
- 默认方法也被称为防御方法（Defender Methods）或虚拟扩展方法（Virtual extension methods）。

## 接口静态方法

静态方法与默认方法不同，我们不能在实现类中重写它们。这一特性有助于我们避免在子类实现不当的情况下出现意外结果。让我们通过一个简单的示例来看。

### MyData.java

```java
package com.journaldev.java8.staticmethod;
public interface MyData {
    default void print(String str) {
        if (!isNull(str))
    }
    static boolean isNull(String str) {
        System.out.println("Interface Null Check" + str);
        return str == null ? true : false;
    }
}
```

现在让我们看一个拥有 `isNull()` 的实现类。

### MyDataImpl.java

```java
package com.journaldev.java8.staticmethod;
public class MyDataImpl implements MyData {
    public boolean isNull(String str) {
        System.out.println("Impl Check");
        return str == null ? true : false;
    }
    public static void main(String args[]){
        MyData obj = new MyDataImpl();
        obj.print("");
        isNull("abc");
    }
}
```

注意 `isNull(String str)` 是一个简单的类方法，它并没有重写接口方法。例如，如果我们在 `isNull()` 方法上添加 `@Override` 注解，会导致编译器错误。现在当我们运行应用程序时，得到如下输出：

```
Interface Null Check
Impl Check
```

如果我们将接口方法从静态改为默认，我们将得到如下输出：

```
Interface Null Check
MyData Print::Impl Check
```

**关于接口静态方法的要点：**

- 接口静态方法是接口的一部分，我们无法通过实现类对象使用它。
- 接口静态方法非常适合提供工具方法，例如空检查、集合排序等。
- 接口静态方法通过不允许实现类重写它们来帮助我们提供安全性。
- 我们不能为 Object 类的方法定义静态方法，否则会导致编译器错误，提示“此静态方法无法隐藏 Object 的实例方法”。这是因为在 Java 中是不被允许的，由于 Object 是所有类的基类，我们不能拥有一个类级静态方法和一个相同签名的实例方法。
- 我们可以使用接口静态方法来移除工具类（如 Collections），将其所有的静态方法移动到相应的接口中，这样更容易查找和使用。

## 函数式接口

在结束这个话题之前，我想对函数式接口进行简要介绍。只有一个抽象方法的接口被称为函数式接口。

引入了新的注解 `@FunctionalInterface` 来标记接口为函数式接口。`@FunctionalInterface` 注解是一种用于防止在函数式接口中意外添加抽象方法的机制。它是可选的，但使用它是一个良好的习惯。

函数接口是 Java 8 中期待已久且广受欢迎的功能，因为它使我们能够使用 lambda 表达式来实例化它们。新增了 `java.util.function` 包，其中包含许多函数接口，用于为 lambda 表达式和方法引用提供目标类型。

## 函数接口与 Lambda 表达式

如果你注意上面的接口代码，你会发现 `@FunctionalInterface` 注解。函数接口是 Java 8 引入的新概念。恰好有一个抽象方法的接口就变成了函数接口。

我们不需要使用 `@FunctionalInterface` 注解来将接口标记为函数接口。`@FunctionalInterface` 注解是一个为了避免在函数接口中意外添加抽象方法的机制。

你可以把它类比为 `@Override` 注解，使用它是一种最佳实践。具有单个抽象方法 `run()` 的 `java.lang.Runnable` 是函数接口的一个绝佳示例。

函数接口的主要优势之一是可能使用 lambda 表达式来实例化它们。我们可以通过匿名类来实例化接口，但代码看起来非常臃肿。

```java
Runnable r = new Runnable(){
    @Override
    public void run() {
        System.out.println("My Runnable");
    }
};
```

由于函数接口只有一个方法，lambda 表达式可以轻松地提供方法的实现。

我们只需要提供方法参数和业务逻辑。例如，我们可以使用 lambda 表达式这样写上面的实现：

```java
Runnable r1 = () -> {
    System.out.println("My Runnable");
};
```

如果方法实现中只有单条语句，我们也不需要大括号。例如，上面的 `Interface1` 匿名类可以使用如下 lambda 方式进行实例化：

```java
Interface1 i1 = (s) -> System.out.println(s);
i1.method1("abc");
```

所以，lambda 表达式是方便创建函数接口匿名类的手段。使用 lambda 表达式在运行时并没有什么收益，因此我会谨慎地使用它，因为我不介意多写几行代码。

新增了 `java.util.function` 包，其中包含许多函数接口，用于为 lambda 表达式和方法引用提供目标类型。

Lambda 表达式是一个巨大的话题，我将在将来（本书的下一版本）针对此编写一个单独的章节。你可以在下方的 Java 8 Lambda 表达式教程中阅读完整的教程。

## Java 8 Lambda 表达式与函数接口教程

Java 一直是一种面向对象的编程语言。这意味着 Java 编程中的一切都围绕着对象（为了简单，某些基本类型除外）。在 Java 中不只有函数，函数是类的一部分，我们需要使用类/对象来调用任何函数。

如果我们看看其他编程语言，如 `C++`、`JavaScript`；它们被称为函数式编程语言，因为我们可以编写函数并在需要时使用它们。这些语言中的一些也支持面向对象编程和函数式编程。

面向对象并不，它给程序带来了大量的冗余。例如，假设我们需要创建一个 `Runnable` 实例。通常我们使用下面的匿名类来完成。

```java
Runnable r = new Runnable(){
    @Override
    public void run() {
        System.out.println("My Runnable");
    }
};
```

如果你观察上面的代码，实际有部分是 `run()` 方法内部的代码。其余所有代码都是因为 Java 程序结构的方式。

Java 8 为我们带来了函数接口和 Lambda 表达式的概念，以避免编写那些我们可以通过让 Java 编译器智能化而轻松避免的无用代码。

### 函数接口

恰好有一个抽象方法的接口被称为函数接口。添加 `@FunctionalInterface` 注解是为了我们可以将接口标记为函数接口。使用它并不是强制的，但在函数接口中使用它是一种最佳实践，以避免意外添加额外方法。如果接口标记了 `@FunctionalInterface` 注解而我们尝试包含多个抽象方法，它将抛出编译错误。

函数接口的主要优势是我们可以使用 lambda 表达式来实例化它们，避免使用臃肿的匿名类实现。

Java 8 Collections API 进行了重写，并提供了新的 Stream API，它使用了许多函数接口。Java 8 在 `java.util.function` 包中定义了许多函数接口，其中一些实用的包括 `Consumer`、`Supplier`、`Function` 和 `Predicate`。你可以在 Stream 示例中找到更多详情。

`java.lang.Runnable` 是具有单个抽象方法 `run()` 的函数接口的绝佳示例。

由于函数接口只有一个方法，lambda 表达式可以轻松地提供方法的实现。我们只需要提供方法参数和业务逻辑。例如，我们可以使用 lambda 表达式这样写上面的实现：

```java
Runnable r1 = () -> {
    System.out.println("My Runnable");
};
```

如果方法实现中只有单条语句，我们也不需要大括号。例如，上面的 `Interface1` 匿名类可以使用如下 lambda 方式进行实例化：

```java
Interface1 i1 = (s) -> System.out.println(s);
i1.method1("abc");
```

所以，lambda 表达式是方便创建函数接口匿名类的手段。使用 lambda 表达式在运行时并没有什么收益，因此我会谨慎地使用它，因为我不介意多写几行代码。

### Lambda 表达式

Lambda 表达式是我们在 Java 面向对象世界中视觉化函数式编程的方式。对象是 Java 编程的基础，没有对象我们就永远无法函数，这就是为什么 Java 语言仅支持配合函数接口使用 lambda 表达式。

Lambda 表达式的语法是 `(argument) -> (body)`。现在让我们如何使用 lambda 表达式编写上面的匿名 Runnable。

```java
Runnable r1 = () -> System.out.println("My Runnable");
```

* 让我们尝试理解上面 lambda 表达式中发生了什么。
* `Runnable` 是函数接口，这就是为什么我们可以使用 lambda 表达式来创建它的实例。
* 由于 `run()` 方法不接收参数，我们的 lambda 表达式也没有参数。
* 就像 if-else 块一样，由于方法体中只有一条语句，我们可以避免大括号 (`{}`)。

### 为什么我们需要 Lambda 表达式

#### 1. 减少代码量

使用 lambda 表达式的一个明显优势是减少了代码量，我们已经看到使用 lambda 表达式比使用匿名类更方便地创建函数接口的实例。

#### 2. 支持顺序执行与并行执行

使用 lambda 表达式的另一个好处是我们可以从 Stream API 的顺序和并行操作支持中受益。为了解释这一点，让我们来看一个简单的例子，我们需要编写一个方法来测试传递的数字是否为素数。

传统上，我们会像下面这样编写代码。这段代码没有经过完全优化，但对于示例目的已经足够了，所以请包涵。

```java
// 传统方法
private static boolean isPrime(int number) {
    if(number < 2) return false;
    for(int i=2; i<number; i++){
        if(number % i == 0) return false;
    }    
    return true;
}
```



上述代码的问题在于它在本质上是顺序的，如果数字非常大，它将花费大量时间。代码的另一个问题是有许多退出点，且可读性差。让我们看看如何使用 lambda 表达式和流 API 编写相同方法。

```java
// 声明式方法
private static boolean isPrime(int number) {
    return number > 1
           && IntStream.range(2, number - 1).noneMatch(
                   index -> number % index == 0);
}
```

`IntStream` 是支持顺序和并行聚合操作的原始 int 值元素序列。这是 `Stream` 的 int 原生类型特化。为了提高可读性，我们也可以像下面这样编写方法。

```java
private static boolean isPrime(int number) {
    IntPredicate isDivisible = index -> number % index == 0;
    return number > 1
           && IntStream.range(2, number - 1).noneMatch(
                   isDivisible);
}
```

如果你不熟悉 `IntStream`，它的 `range()` 方法返回一个从 `startInclusive`（包含）到 `endExclusive`（不包含）、步增量为 1 的顺序 `IntStream`。`noneMatch()` 方法返回此流中没有元素匹配提供的谓词。

如果对于确定结果不是必要的，它可能不会对所有元素求值谓词。

### 3. 将行为传递到方法

让我们通过一个简单的例子看看如何使用 lambda 表达式传递方法的行为。假设我们需要编写一个方法，如果列表中的数字符合给定标准，则对它们求和。我们可以使用 `Predicate` 并编写如下所示的方法。

```java
public static int sumWithCondition(List<Integer> numbers, Predicate<Integer> predicate) {
    return numbers.parallelStream()
               .filter(predicate)
               .mapToInt(i -> i)
               .sum();
}
```

示例用法：

```java
// 所有数字之和
sumWithCondition(numbers, n -> true)
// 所有偶数之和
sumWithCondition(numbers, i -> i%2==0)
// 所有大于 5 的数字之和
sumWithCondition(numbers, i -> i>5)
```

### 4. 惰性带来的效率

使用 lambda 表达式的另一个优势是惰性求值，例如，假设我们需要编写一个方法来找到 3 到 11 范围内最大的奇数并返回它的平方。通常我们这样写这个方法的代码：

```java
private static int findSquareOfMaxOdd(List<Integer> numbers) {
    int max = 0;
    for (int i : numbers) {
        if (i % 2 != 0 && i > 3 && i < 11 && i > max) {
            max = i;
        }
    }
    return max * max;
}
```

上述程序将始终按顺序运行，但我们可以使用 Stream API 来实现这一点并获得惰性。让我们看看如何使用 Stream API 和 lambda 表达式以函数式方式重写这段代码。

```java
public static int findSquareOfOdd(List<Integer> numbers) {
    return numbers.stream()
               .filter(NumberTest::isOdd) // 谓词是函数接口
               .filter(NumberTest::isGreaterThan3) // 我们使用 lambda 来初始化它
               .filter(NumberTest::isLessThan11) // 而不是匿名类
               .max(Comparator.naturalOrder())
               .map(i -> i * i)
               .get();
}
public static boolean isOdd(int i) {
    return i % 2 != 0;
}
public static boolean isGreaterThan3(int i){
    return i > 3;
}
public static boolean isLessThan11(int i){
    return i < 11;
}
```

如果你对双冒号 `::` 运算符感到惊讶，它在 Java 8 中引入，用于方法引用。Java 编译器会处理参数到被调用方法的的映射。它是 lambda 表达式 `i -> isGreaterThan3(i)` 或 `i -> NumberTest.isGreaterThan3(i)` 的简写形式。

#### 表达式示例

下面我提供了一些 lambda 表达式的代码片段，并附带了简单的注释进行解释。

```java
() -> {} // 无参数；void 结果
() -> 42 // 无参数，表达式体
() -> null // 无参数，表达式体
() -> { return 42; } // 无参数，带返回的块体
() -> { System.gc(); } // 无参数，void 块体- 复杂的块体（带有多个返回）
() -> {
    if (true) return 10;
    else {
        int result = 15;
        for (int i = 1; i < 10; i++)
            result *= i;
        return result;
    }
}
(int x) -> x+1 // 单个声明类型参数
(int x) -> { return x+1; } // 与上述相同
(x) -> x+1 // 单个推断类型参数
x -> x+1 // 单个推断类型情况，括号可选
(String s) -> s.length() // 单个声明类型参数
(Thread t) -> { t.start(); } // 单个声明类型参数
s -> s.length() // 单个推断类型参数
t -> { t.start(); } // 单个推断类型参数
(int x, int y) -> x+y // 多个声明类型
(x,y) -> x+y // 多个推断类型
(x, final y) -> x+y // 错误：不能修改推断类型参数
(x, int y) -> x+y // 错误：不能混合推断类型和声明类型
```

方法引用和构造函数引用

方法引用用于在不调用方法的情况下引用方法；构造函数引用同样用于在不创建命名类或数组类型实例引用构造函数。

方法引用和构造函数引用示例：

```java
System::getProperty
System.out::println
"abc"::length
ArrayList::new
int[]::new
```

以上就是函数接口和 Lambda 表达式教程的全部内容，我强烈建议研究它，因为这种语法对于 Java 来说是新的，需要一些时间来掌握并更好地使用它。

### 4. 用于集合批量数据操作的 Java Stream API

Java 8 添加了新的 `java.util.stream`，用于对集合执行 filter/map/reduce 等操作。Stream API 允许顺序和并行执行。

Collection 接口扩展了 `stream()` 和 `parallelStream()` 默认方法，以获取顺序和并行执行的 Stream。让我们通过简单的例子来看它们的用法。

![](img/image01302.jpeg)

```java
package com.journaldev.java8.stream;
import java.util.ArrayList;
import java.util.List;
import java.util.stream.Stream;

public class StreamExample {
    public static void main(String[] args) {
        List<Integer> myList = new ArrayList<>();
        for(int i=0; i<100; i++) myList.add(i);
        //sequential stream
        Stream<Integer> sequentialStream = myList.stream();
        //parallel stream
        Stream<Integer> parallelStream = myList.parallelStream();
        //using lambda with Stream API, filter example
        Stream<Integer> highNums = parallelStream.filter(p -> p > 90);
        //using lambda in forEach
        highNums.forEach(p -> System.out.println("High Nums parallel="+p));
        Stream<Integer> highNumsSeq = sequentialStream.filter(p -> p > 90);
        highNumsSeq.forEach(p -> System.out.println("High Nums sequential="+p));
    }
}
```

如果你运行上述示例代码，将得到如下输出：

High Nums parallel=91High Nums parallel=96High Nums parallel=93High Nums parallel=98High Nums parallel=94High Nums parallel=95High Nums parallel=97High Nums parallel=92High Nums parallel=99High Nums sequential=91High Nums sequential=92High Nums sequential=93High Nums sequential=94High Nums sequential=95High Nums sequential=96High Nums sequential=97High Nums sequential=98High Nums sequential=99

注意，并行处理的值不是有序的，因此在处理巨大集合时，并行处理将非常有帮助。在本主题中无法涵盖 Stream API 的所有内容，你可以在下一章的《Java 8 Stream API Tutorial》中阅读关于 Stream API 的所有内容。

![STAR-LOGO-2013](img/image01303.jpeg)

## 章节

# ∞ 23 ∞

## Java 8 Stream 和时间 API

## Java 8 Stream API 示例教程

在最后的话中，我们查看了 `Java 8 接口更改` 以及 `函数式接口和 Lambda 表达式`。

现在我们将介绍 Java 8 中引入的主要 API 之一 – `Java Stream API`。

1. `Stream API 概述`。

2. `集合与 Stream`。

3. `Stream 中常用的函数式接口`。

    1. `Function` 和 `BiFunction`。

    2. `Predicate` 和 `BiPredicate`。

    3. `Consumer` 和 `BiConsumer`。

    4. `Supplier`。

4. `java.util.Optional`。

5. `java.util.Spliterator`。

6. `中间操作与终端操作`。

7. `短路操作`。

8. `Java Stream 示例`。

    1. `创建 Stream`。

    2. `将 Stream 集合或数组`。

    3. `Stream 中间操作`。

    4. `Stream 终端操作`。

9. `Java Stream API 局限性`。

## Stream API 概述

在查看 Java 8 Stream API 示例之前，让我们看看为什么需要它。假设我们要遍历一个整数列表，并找到所有大于 10 的整数之和。在 Java 8 之前，实现的方法是：

```java
private static int sumIterator(List<Integer> list) {
    Iterator<Integer> it = list.iterator();
    int sum = 0;
    while (it.hasNext()) {
        int num = it.next();
        if (num > 10) {
            sum += num;
        }
    }
    return sum;
}
```

上述方法有三个主要问题：

1) 我们只想知道整数之和，但还必须提供如何进行迭代，这被称为 `外部迭代`（external iteration），因为客户端程序正在处理遍历列表的算法。

2) 程序本质上是顺序的，我们无法轻松以并行方式执行此。

3) 即使是一个简单的任务，也有大量的代码。

为了克服上述所有缺点，Java 8 引入了 Stream API。我们可以使用 Stream API 来实现 `内部迭代`（internal iteration），这样更好，因为 Java 框架控制着迭代。`内部迭代`提供了许多功能，如顺序和并行执行、根据给定标准进行过滤、映射等。

大多数 Stream API 方法的参数都是函数式接口，因此 Lambda 表达式与它们配合得非常好。让我们看看如何用单行语句编写上述逻辑。

```java
private static int sumStream(List<Integer> list) {
    return list.stream().filter(i -> i > 10).mapToInt(i -> i).sum();
}
```

注意，上述程序利用了 Java 框架的迭代策略、过滤和映射方法并将提高效率。首先我们将查看 Stream API 的核心概念，然后通过一些示例来理解最常用的方法。

## 集合与 Stream

集合（collection）是一种用于存储值的内存数据结构，在我们开始使用集合之前，所有值都应该已经填充。而 `Stream` 是一种按需计算的数据结构。

Stream 不存储数据，它在源数据结构（集合和数组）上操作，并产生我们可以使用的流水线数据。



# Java Stream API 详解

## Stream 特性

Stream 不存储数据，它在源数据结构（集合和数组）上操作，并产生我们可以使用的流水线数据。

## 函数式接口

### 1. `Consumer`

它代表一个接受单个输入参数且不返回结果的操作。它可以用于对流中的所有元素执行某些操作。使用 `Consumer`、`BiConsumer` 或其原始特化接口的 `Stream` 方法包括：

- `Stream<T> peek(Consumer<? super T> action)`
- `void forEach(Consumer<? super T> action)`
- `void forEachOrdered(Consumer<? super T> action)`

### 2. `Supplier`

`Supplier` 代表一种通过我们可以在流中生成新值的操作。`Stream` 中接受 `Supplier` 参数的一些方法是：

- `public static<T> Stream<T> generate(Supplier<T> s)`
- `<R> R collect(Supplier<R> supplier, BiConsumer<R, ? super T> accumulator, BiConsumer<R, R> combiner)`

### 3. `java.util.Optional`

`Optional` 是一个容器对象，可能包含也不包含非空值。如果存在值，`isPresent()` 将返回 `true`，`get()` 将返回该值。`Stream` 终端操作返回 `Optional` 对象。这些方法包括：

- `Optional<T> reduce(BinaryOperator<T> accumulator)`
- `Optional<T> min(Comparator<? super T> comparator)`
- `Optional<T> max(Comparator<? super T> comparator)`
- `Optional<T> findFirst()`
- `Optional<T> findAny()`

### 4. `java.util.Spliterator`

为了支持 `Stream` API 的并行执行，使用了 `Spliterator` 接口。`Spliterator` 的 `trySplit` 方法返回一个新的 `Spliterator`，它管理原始 `Spliterator` 元素的子集。

## 操作分类

### 中间操作与终端操作

返回新 `Stream` 的 `Stream` API 操作被称为中间操作。大多数情况下，这些操作本质上是懒性的，因此它们开始产生新的流元素并将其发送给下一个操作。中间操作永远不是产生最终结果的操作。

常用的中间操作是 `filter` 和 `map`。

返回结果或产生副作用的 `Stream` API 操作称为终端操作。一旦在流上调用了终端方法，它就会消耗该流，之后我们无法再使用该流。终端操作在本质上是急进的，即它们在返回结果之前会处理流中的所有元素。

常用的终端方法有 `forEach`、`toArray`、`min`、`max`、`findFirst`、`anyMatch`、`allMatch` 等。你可以通过返回类型识别终端方法，它们永远不会返回 `Stream`。

### 短路操作

如果一个中间操作可以为无限流产生有限流，则该操作被称为短路操作。例如，`limit()` 和 `skip()` 是两个短路中间操作。

如果一个终端操作可以在有限时间内终止无限流的终止，则该操作被称为短路操作。例如，`anyMatch`、`allMatch`、`noneMatch`、`findFirst` 和 `findAny` 是短路终端操作。

## Java Stream 示例

### 创建流

有几种方法可以从数组和集合创建流。

#### 1. 使用 `Stream.of()`

我们可以使用 `Stream.of()` 从相同类型的数据创建流。例如，我们可以从一组 `int` 或 `Integer` 对象创建整数的 `Stream`。

```java
Stream<Integer> stream = Stream.of(1, 2, 3, 4);
```

#### 2. 使用对象数组

我们可以使用带有 `Objects` 数组的 `Stream.of()` 返回流。注意它不支持自动装箱，所以我们不能传递原始类型数组。

```java
Stream<Integer> stream = Stream.of(new Integer[]{1, 2, 3, 4}); // 正常工作
Stream<Integer> stream1 = Stream.of(new int[]{1, 2, 3, 4}); // 编译错误，类型不匹配：无法从 Stream<int[]> 转换为 Stream<Integer>
```

#### 3. 使用 Collection

我们可以使用 `Collection` 的 `stream()` 创建顺序流，并使用 `parallelStream()` 创建并行流。

```java
List<Integer> myList = new ArrayList<>();
for (int i = 0; i < 100; i++) myList.add(i);
// 顺序流
Stream<Integer> sequentialStream = myList.stream();
// 并行流
Stream<Integer> parallelStream = myList.parallelStream();
```

#### 4. 使用 `generate()` 和 `iterate()`

我们可以使用 `Stream.generate()` 和 `Stream.iterate()` 方法创建 `Stream`。

```java
Stream<String> stream1 = Stream.generate(() -> { return "abc"; });
Stream<String> stream2 = Stream.iterate("abc", (i) -> i);
```

#### 5. 使用 `Arrays.stream()` 和 `String.chars()`

```java
LongStream is = Arrays.stream(new long[]{1, 2, 3, 4});
IntStream is2 = "abc".chars();
```

### 将流转换为集合或数组

#### 1. 使用 `collect()`

我们可以使用 `Stream` 的 `collect()` 方法从流中获取 `List`、`Map` 或 `Set`。

```java
Stream<Integer> intStream = Stream.of(1, 2, 3, 4);
List<Integer> intList = intStream.collect(Collectors.toList());

Stream<Integer> intStream2 = Stream.of(1, 2, 3, 4);
Map<Integer, Integer> intMap = intStream2.collect(Collectors.toMap(k -> k, v -> v));
```

#### 2. 使用 `toArray()`

我们可以使用 `Stream` 的 `toArray()` 创建数组。

```java
Stream<Integer> intStream = Stream.of(1, 2, 3, 4);
Integer[] intArray = intStream.toArray(Integer[]::new);
```

### 中间操作示例

#### `filter()`

我们可以使用 `filter()` 方法根据条件测试流元素。

```java
List<Integer> myList = new ArrayList<>();
for (int i = 0; i < 100; i++) myList.add(i);
Stream<Integer> sequentialStream = myList.stream();
Stream<Integer> highNums = sequentialStream.filter(p -> p > 90);
highNums.forEach(p -> System.out.print(p));
```

#### `map()`

我们可以使用 `map()` 对流应用函数。

```java
Stream<String> names = Stream.of("aBc", "d", "ef");
System.out.println(names.map(s -> s.toUpperCase()).collect(Collectors.toList()));
```

#### `sorted()`

我们可以通过传递参数使用 `sorted()` 对流元素进行排序。

```java
Stream<String> names2 = Stream.of("aBc", "d", "ef", "12346");
List<String> reverseSorted = names2.sorted(Comparator.reverseOrder()).collect(Collectors.toList());
System.out.println(reverseSorted);

Stream<String> names3 = Stream.of("aBc", "d", "ef", "12346");
List<String> naturalSorted = names3.sorted().collect(Collectors.toList());
System.out.println(naturalSorted);
```

#### `flatMap()`

我们可以使用 `flatMap()` 从列表流创建一个流。

```java
Stream<List<String>> namesOriginalList = Stream.of(
    Arrays.asList("Pankaj"),
    Arrays.asList("David", "Lisa"),
    Arrays.asList("Amit")
);
Stream<String> flatStream = namesOriginalList.flatMap(strList -> strList.stream());
flatStream.forEach(System.out::println);
```

### 终端操作示例

#### 1. `reduce()`

我们可以使用 `reduce()` 对流元素执行归约，使用结合累加函数并返回一个 `Optional`。让我们看看如何使用它来乘以流中的整数。

```java
Stream<Integer> numbers = Stream.of(1, 2, 3, 4, 5);
Optional<Integer> intOptional = numbers.reduce((i, j) -> { return i * j; });
if (intOptional.isPresent()) System.out.println("Multiplication = " + intOptional.get());
```

#### 2. `count()`

我们可以使用此终端操作来计算流中元素的数量。



```java
Stream<Integer> numbers1 = Stream.of(1,2,3,4,5);System.out.println("Number of elements in stream="+numbers1.count()); //5
```

### 3. Stream `forEach()` 示例

它可以用于遍历流。我们可以用它来替代迭代器（iterator）。让我们看看如何使用它打印流中的所有元素。

```java
Stream<Integer> numbers2 = Stream.of(1,2,3,4,5);numbers2.forEach(i -> System.out.print(i+",")); //1,2,3,4,5,
```

### 4. Stream `match()` 示例

让我们来看看 Stream API 中匹配方法的一些示例。

```java
Stream<Integer> numbers3 = Stream.of(1,2,3,4,5);System.out.println("Stream contains 4? "+numbers3.anyMatch(i -> i==4));//Stream contains 4? true
Stream<Integer> numbers4 = Stream.of(1,2,3,4,5);System.out.println("Stream contains all elements less than 10? "+numbers4.allMatch(i -> i<10));//Stream contains all elements less than 10? true
Stream<Integer> numbers5 = Stream.of(1,2,3,4,5);System.out.println("Stream doesn't contain 10? "+numbers5.noneMatch(i -> i==10));//Stream doesn't contain 10? true
```

### 5. Stream `findFirst()` 示例

这是一个短路终端操作（short circuiting terminal operation），让我们看看如何使用它从流中找到第一个以 D 开头的字符串。

```java
Stream<String> names4 = Stream.of("Pankaj","Amit","David", "Lisa");
Optional<String> firstNameWithD = names4.filter(i -> i.startsWith("D")).findFirst();
if(firstNameWithD.isPresent()){
    System.out.println("First Name starting with D="+firstNameWithD.get()); //David
}
```

## Java Stream API 的局限性

Stream API 为处理列表和数组带来了许多新功能，但也有一些局限性。

### 1. 无状态 lambda 表达式

如果你在使用并行流（parallel stream）且 lambda 表达式是有状态的（stateful），可能会导致随机的结果。让我们通过一个简单的程序来看。

`StatefulParallelStream.java`

```java
package com.journaldev.java8.stream;
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Stream;
public class StatefulParallelStream {
    public static void main(String[] args) {
        List<Integer> ss = Arrays.asList(1,2,3,4,5,6,7,8,9,10,11,12,13,14,15);
        List<Integer> result = new ArrayList<Integer>();
        Stream<Integer> stream = ss.parallelStream();
        stream.map(s -> {
            synchronized (result) {
                if (result.size() < 10) {
                    result.add(s);
                }
            }
            return s;
        }).forEach( e -> {});
        System.out.println(result);
    }
}
```

如果运行上面的程序，你将得到不同的结果，因为它取决于流的迭代方式，而且我们没有为并行处理定义任何顺序。如果我们使用顺序流（sequential stream），这个问题就不会出现。

### 2. 一次性消费

一旦 `Stream` 被消费，它就不能再次被使用。如你在上面的示例所示，我每次都是创建一个新的流。

### 3. 方法繁多

Stream API 中有很多方法，最令人困惑的部分是……

这就是关于 Java Stream 局限性的全部内容。

## Java 的安全模型

Java 的安全模型旨在通过“沙箱”帮助并保护用户免受网络中不可信资源下载的恶意程序的侵害。它允许所有 Java 程序仅在沙箱内运行，并防止来自不可信资源的许多活动，包括读取或写入本地磁盘、创建任何新进程，甚至在调用本地方法时加载任何新的动态链接库。

### 不使用指针

C/C++ 语言使用指针，当其他程序获取指针值时，可能会导致内存块的未经授权访问。与传统的 C/C++ 语言不同，Java 从不使用任何类型的指针。Java 有其内部的内存管理机制。它只在获得适当验证授权的情况下才会允许程序访问数据。

### 异常处理概念

异常处理概念使 Java 能够捕获一系列错误，帮助开发者消除系统崩溃的风险。

### 定义的执行顺序

所有基本类型都有预定义的大小，且所有操作都按照特定的执行顺序定义。因此，在不同的 `Java Virtual Machines` 中执行的代码执行顺序不会有所不同。

### 字节码验证

每当用户编译 Java 程序时，Java 编译器都会创建一个包含 `Bytecode` 的类文件，这些字节码会在程序执行时由 `JVM` 检查病毒和其他恶意文件。

### 经过测试的代码重用性

Java 对象的封装为“契约编程”概念提供了支持。这允许开发者在开发 Java 企业级应用程序时，重用已经过测试的代码。

### 访问控制功能

Java 对对象内部变量和方法的访问控制功能通过防止不可信代码访问关键对象，提供了程序的安全性保障。

### 防止安全攻击

它允许开发者将类或方法声明为 `FINAL`。我们都知道，任何声明为 `final` 的类或方法都不能被重写，这有助于开发者保护代码免受安全攻击，例如创建子类并替换原始类以及重写方法。

### 垃圾回收机制

垃圾回收机制有助于 Java 的安全措施。它提供了透明的存储分配和未利用内存的回收，而不是通过手动操作释放内存。这将帮助开发者确保程序在执行期间的完整性，并避免因内存释放错误导致的任何 `JVM` 崩溃。

### JVM 中的类型安全引用转换

每当你使用对象引用时，`JVM` 都会监控。如果你尝试将引用转换为不同的类型，它将使该转换无效。

除了所有这些，结构化错误处理通过帮助增强程序的健壮性对 Java 的安全模型做出了巨大贡献。以上理由绝对证明，与其他编程语言相比，用 Java 开发的项目更加安全。然而，在开发企业级 Java 应用程序时，遵循一些最佳实践是开发者的责任。
