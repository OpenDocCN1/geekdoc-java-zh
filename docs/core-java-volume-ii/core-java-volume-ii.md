
# Java 核心卷二

![](img/240dbf1b84e081687f1e252bd386c684_0_0.png)

![](img/240dbf1b84e081687f1e252bd386c684_1_0.png)

## 序言

## 致谢

- 7.1.2. 指定 `Locale`
- 7.1.4. 显示名称
- 7.2. 数字格式
  - 7.2.1. 格式化数值
  - 7.2.3. 货币
- 7.3. 日期与时间
- 7.4. 排序规则（Collation）与规范化
- 7.5. 消息格式化
  - 7.5.1. 格式化数字和日期
  - 7.7.2. 行结束符
  - 7.7.4. UTF-8 字节顺序标记
  - 8.2.6. 示例：脚本页（Script Sheets）

## 9. 安全

- 9.1. 类加载器（Class Loaders）
  - 9.1.1. 类加载过程
  - 9.1.2. 类加载器层次结构
  - 9.1.3. 使用类加载器作为命名空间
  - 9.1.4. 编写你自己的类加载器
  - 9.1.5. 字节码验证
- 9.2. 用户身份验证
  - 9.2.1. JAAS 框架
  - 9.2.2. JAAS 登录模块
- 9.3. 数字签名
  - 9.3.1. 消息摘要（Message Digests）
  - 9.3.2. 密码哈希
  - 9.3.3. 消息签名
  - 9.3.4. 验证签名
  - 9.3.5. 身份验证问题
  - 9.3.6. 证书签名
  - 9.3.7. 代码签名
- 9.4. 加密
  - 9.4.1. 对称加密（Ciphers）
  - 9.4.2. 密钥生成
  - 9.4.3. 密文
  - 9.4.4. 公钥加密

## 10. 图形用户界面

- 10.1. 用户界面工具包
- 10.2. 显示窗口（Frames）
  - 10.2.1. 创建窗口
  - 10.2.2. 窗口属性
- 10.3. 显示信息
  - 10.3.1. 使用 2D 形状
  - 10.3.2. 使用颜色
  - 10.3.3. 使用字体
  - 10.3.4. 显示图像
- 10.4. 事件处理
  - 10.4.1. 基础概念
  - 10.4.2. 处理点击
  - 10.4.3. 监听器
  - 10.4.4. 适配器类
  - 10.4.5. 鼠标事件
  - 10.4.6. AWT 层次结构
- 10.5. Preferences API

## 11. 使用 Swing 的用户界面

- 11.1. Swing 与模型-视图-控制器（MVC）
- 11.2. 布局管理
  - 11.2.1. 布局管理器
  - 11.2.2. 边框布局
  - 11.2.3. 网格布局（Grid Layout）
- 11.3. 文本输入
  - 11.3.1. 文本字段
  - 11.3.2. 标签（Labels）
  - 11.3.3. 密码字段
  - 11.3.4. 文本区域
  - 11.3.5. 滚动面板（Scroll Panes）
- 11.4. 选择组件
  - 11.4.1. 复选框（Checkboxes）
  - 11.4.2. 单选按钮（Radio Buttons）
  - 11.4.3. 边界
  - 11.4.4. 下拉框（Combo Boxes）
  - 11.4.5. 滑块（Sliders）
- 11.5. 菜单
  - 11.5.1. 构建
  - 11.5.2. 菜单项
  - 11.5.3. 复选框与单选按钮项
  - 11.5.4. 弹出菜单（Pop-Up Menus）
  - 11.5.5. 键盘快捷键与加速器
  - 11.5.6. 启用与禁用项
  - 11.5.7. 工具栏
  - 11.5.8. 提示框（Tooltips）
- 11.6. 网格布局（Grid Bag Layout）
  - 11.6.1. Grid Bag 基础
  - 11.6.2. `gridx`、`gridy`、`gridwidth` 和 `gridheight` 参数
  - 11.6.3. 权重字段（Weight Fields）
  - 11.6.4. `fill` 和 `anchor` 参数
  - 11.6.5. 内边距（Padding）
  - 11.6.6. 指定 `gridx`、`gridwidth` 和 `gridheight` 参数的替代方法
  - 11.6.7. Grid Bag 布局配方
  - 11.6.8. 约束 Grid Bag 类的辅助类
- 11.7. 自定义布局管理器
- 11.8. 对话框
  - 11.8.1. 选项面板（Option Panes）
  - 11.8.2. 创建对话框
  - 11.8.3. 数据交换
  - 11.8.4. 文件对话框

## 12. 高级 Swing 与图形

- 12.1. 表
  - 12.1.1. 简单表格
  - 12.1.2. 表模型
- 12.2. 处理行和列
  - 12.2.1. 列类
  - 12.2.2. 访问表格列
  - 12.2.3. 调整列
  - 12.2.4. 调整行
  - 12.2.5. 选择行、列和单元格
  - 12.2.6. 排序行
  - 12.2.7. 过滤行
  - 12.2.8. 隐藏与显示列
- 12.3. 单元格渲染与编辑
  - 12.3.1. 渲染单元格
  - 12.3.2. 渲染表头
  - 12.3.3. 编辑单元格
  - 12.3.4. 自定义编辑器
- 12.4. 树
  - 12.4.1. 简单树
  - 12.4.2. 渲染树与树路径
  - 12.4.3. 节点枚举
  - 12.4.4. 渲染节点
  - 12.4.5. 监听树事件
  - 12.4.6. 自定义树模型
- 12.5. 高级 AWT
  - 12.5.1. 渲染流水线
  - 12.5.2. 形状类层次结构
  - 12.5.3. 构建形状
  - 12.5.4. 区域（Areas）
  - 12.5.5. 笔画（Strokes）
  - 12.5.6. 绘制（Paint）
  - 12.5.7. 坐标变换
  - 12.5.8. 裁剪（Clipping）
  - 12.5.9. 透明度与合成
- 12.6. 栅格图像
  - 12.6.1. 图像读取器与写入器
  - 12.6.2. 获取针对文件类型的读取器与写入器
  - 12.6.3. 读写包含多个图像的文件
  - 12.6.4. 图像处理
  - 12.6.5. 图像过滤

## 注解

## Java 平台模块系统

第二卷深入探讨了最重要的类库。在过去的十二版本中，用户界面编程一直被视为基础内容，但现在已经意识到它不再是了，并将其移动到了第二卷。本卷包含了对以下主题的详细讨论：

- Stream API
- 文件处理与正则表达式
- 数据库
- XML 处理
- 脚本与编译 API
- 国际化
- 网络编程
- 图形用户界面设计
- 图形编程
- 外部函数与内存

和任何书本一样，错误和不准确之处是不可避免的。如果您在书中发现任何错误，我们非常希望听到您的反馈。当然，我们希望这些错误只出现一次。因此，我们在 <https://horstmann.com/corejava> 建立了一个网站，包含常见问题解答（FAQ）、错误修复和变通方案。在错误报告网页的末尾策略性地放置了一个表单（以鼓励您阅读之前的报告），您可以使用它来报告错误或问题，并为未来的版本提供改进建议。

## 本书简介

书中的章节大部分是相互独立的。您可以深入研究您最感兴趣的主题，并按照任何顺序阅读章节。

在第一章中，您将学习关于 Java Stream 库的所有知识。它为数据处理带来了现代化的风格，通过指定您想要什么，而不详细描述如何获取结果。这使得流库能够专注于优优的评估策略，这对于在多核心上并行执行计算特别有利。

在本章中，你将学习如何使用 Java 流库，它允许你以“做什么，而不是怎么做”风格处理值序列。

## 1.1. 从迭代到流操作

当你处理集合时，通常会遍历其元素并对每个元素执行某些操作。例如，假设我们想统计一本书中的长单词。首先，把它们放入一个列表：

```java
String contents = Files.readString(Path.of("alice.txt")); // 将文件读入字符串
String[] words = contents.split("\\s+"); // 拆分为单词
```

第二章的主题是输入/输出处理（I/O）。在 Java 中，所有的输入和输出都通过输入/输出流处理。这些流（不要与第一章中的流混淆）让您以统一的方式处理各种数据源（如文件、网络连接或内存块）之间的通信。我们包含了对 reader 和 writer 类的详细覆盖，这使得处理 Unicode 变得容易。我们展示了当使用对象序列化机制时底层发生了什么，这使得保存和加载对象变得简单方便。然后我们转向正则表达式以及文件和路径的操作。在本章中，您将发现最近 Java 版本中欢迎的增强。

第三章涵盖了 XML。我们将向您展示如何解析 XML 文件、如何生成 XML 以及如何使用 XSL 转换。作为一个实用的示例，我们展示了如何在 XML 中指定 Swing 表单的布局。我们还讨论了 XPath API，它使得在 XML 文本大海中找针变得容易得多。

第四章涵盖了网络 API。Java 让进行复杂的网络编程变得异常简单。我们将向您展示如何与服务器建立网络连接、如何实现自己的服务器以及如何建立 HTTP 连接。本章包含了对新 HTTP client 的介绍。

第五章涵盖了数据库编程。重点是 JDBC，即 Java 数据库连接 API，允许 Java 程序连接到关系型数据库。我们展示了如何使用 JDBC API 的核心子集编写实用的程序来处理真实的数据库任务。（完整介绍 JDBC API 需要一本几乎本书一样大的书。）

Java 之前曾尝试过处理日期和时间的类库。第三次尝试是 Java 8 中的亮点。在第六章中，您将学习如何使用新的日期时间库处理日历和时区的复杂性。

第七章讨论了一个我们认为重要性日益增加特性：国际化。Java 编程语言是少数从一开始就设计为处理 Unicode 的语言之一，但 Java 平台的国际化支持要深入得多。因此，您可以对 Java 应用进行国际化，使其不仅跨越平台还能跨越国界。例如，我们向您展示如何编写一个可以使用英语、德语或中文的退休计算器。

第八章讨论了脚本和编译器 API，这些 API 允许您的程序调用 JavaScript 或 Groovy 等脚本语言的代码，并编译 Java 代码。

第九章涉及了 Java 安全模型、用户身份验证以及 Java 安全库中的加密函数。您将学习一些重要特性，如消息和代码签名、授权与身份验证以及加密。我们以使用 AES 和 RSA 加密算法的示例结束。

第 10 章提供了 GUI 编程的介绍。我将向您展示如何创建窗口、如何在上面画画、如何用几何形状绘图、如何格式化多种字体文本以及如何显示图像。接下来，您将看到如何编写响应事件（如鼠标点击或按键按下）的代码。

第 11 章详细讨论了 Swing 工具包。Swing 工具包允许您构建跨平台的图形用户界面。您将学习关于各种按钮、文本组件、边框、滑块、列表框、菜单和对话框的所有知识。

第 12 章包含了高级 Swing 材质，特别是重要但复杂的树和表格组件。我们还涵盖了 Java 2D API，您可以使用它创建真实的绘画和特殊特效。当然，现在已经没有多少程序员需要编写 Swing 用户界面了，因此我们特别关注对于可以在服务器上生成的图像有用的特性。

第 13 章涉及了外部函数（foreign functions），它允许您调用其他编程语言编写的代码。当您与 Java 不支持的设备或服务交互时，您可能需要转向目标平台的操作系统 API。或者您可能想调用一个经过实战的机器学习或数据分析库。

一如既往，所有章节已针对最新的 Java 版本进行了完全修订。

## 约定

与许多书籍一样，我使用等宽字体来表示计算机代码。

> 注意：注释带有像这里这样的“note”图标标记。
>
> 提示：提示带有像这里这样的“tip”图标标记。
>
> **警告**：当前方有危险时，我将用“caution”图标警告您。
>
> **预览**：计划未来成为语言或 API 部分的预览特性将用此图标标记。

Java 自带了一个庞大的编程接口（API）。当第一次使用 API 调用时，我会在章节末尾添加简短描述。这些描述有些非正式，但希望比官方文档中的更具信息量。接口名称使用斜体表示。类、接口或方法名称后的数字是引入该功能的 JDK 版本，如下例所示：

| `java.io.println(Object obj)` | 将对象转换为字符串并在控制台上打印，随后紧跟一个换行符。 |
| --- | --- |

源代码包含在本书配套代码中的程序被列为示例，例如：

### 清单 `HelloWorld.java`

```java
void main() {
  System.out.println("We will not use 'Hello, World!");
}
```

您可以从 <https://horstmann.com/corejava> 下载配套代码。

## 致谢

写一本书总是一项艰巨的工程，而重写似乎并不容易，特别是在 Java 技术变化如此迅速的情况下。将一本书变为现实需要许多人的投入，我很荣幸地感谢整个 Java 团队的贡献。

感谢我的编辑 Harry Misth，以及 Pearson 的 Julie Nahil，她引导了书籍制作过程。我使用 HTML 和 CSS 编写书籍，并通过 Prince（<https://princexml.com>）将其转换为 PDF——这是一个我非常推荐的工作流。

感谢早期版本的许多读者，他们报告了尴尬的错误并提供了许多建设性的改进建议。我特别感谢优秀的评审团队，他们以惊人的细节关注眼光审查了手稿，为我避免了更多尴尬的错误。

Crane (devXsolution), Joe Darcy (Oracle), Nicholas J. De Lillo (曼哈顿学院), Rakesh Dhoopar (Oracle), Ahmad R. Elkemey, Hanno Embregets (Info Support), Robert Evans (高级员工), 约翰霍普金斯大学应用物理实验室, David Geary (Clarity Training), Jim Gish (Oracle), Brian Goetz (Oracle), Angela Gordon, Dan Gordon (Electric Cloud), Rob Gordon, John Gray (哈特福大学), Cameron Gregory (olabs.com), Andrzej Gesky, Majid Hameed, Vincent Hardy (Adobe Systems), Dan Harkey (加州州大学), Steve Haines, William Higgins (IBM), Marc Hoffmann (mtrail), Vladimir Ivanovic (PointBase), Jerry Jackson (CA Technologies), Joseph June, Heinz Kabutz (The Java Specialists' Newsletter, <https://javascriptspecialists.eu>), Stepan V. Kalinin (I-Teco/Servionica LTD), Tim Kimmet (Walmart), John Kostaras, Jerzy Krolak, Chris Laffra, Charlie Lai (Apple), Angelika Langer, Jeff Lang (Langr Software Solutions), Doug Langston, Hang Lau (麦吉尔大学), Mark Lawrence, Doug Lee (纽约州立 Oswego), Jason Lee (IBM), Gregory Longshore, Bob Lynch (Lynch Associates), Michael McMahon (Oracle), Rustam Mehmandarov, Philip Milne (顾问), Mark Morrissey (俄勒冈学院), Maurice Naftalin, Mahesh Neelakanta (佛罗里达大大学), José Paumard (Oracle), Hao Pham, Paul Philipp, Blake Ragsdell, Yber Ramadani (瑞森大学), Stuart Regents Simon Ritter (Azul Systems), Rich Rosen (Interactive Data Corporation), Peter Sanders (法国尼斯 ESSI 大学), Paul Sanghera 博士 (加州州大学与 Brooks 学院), 佐藤 (Oracle), Paul Sevinc (Teamup AG), Devang Shah (太阳系统), Yoshiki Shiba, Richard Slywczak (NASA/格伦研究中心), Bradley A. Smith, Steven Stelting (Oracle), Christopher Taylor, Luke Taylor (Valtech), George Thiruvathathukal, Kim Topley (StreamingEdge), Janet Traub, Henri Tremblay, Paul Tyma (顾问), Christian Ullenboom, Peter van der Linden, Joe Wang (Oracle), Sven Woltmann, Burt Walsh, Dan Xu (Oracle), 以及 John Zavgren (Oracle)。

最后，衷心感谢我早期版本的合著者 Gary Cornell，以及担任我近三十年的编辑 Greg Doench。

Cay Horstmann

德国，杜塞尔多夫

2025年9月



`split` 方法根据给定的正则表达式分隔符将字符串拆分为若干部分。（关于正则表达式的更多信息，请参阅第 2 章。现在，只需相信 `\s+` 表达式是有效的即可。）

现在我们准备好进行迭代了：

```java
int count = 0;
for (String w : words) {
  if (w.length() > 12) count++;
}
```

使用流，相同的操作看起来如下：

```java
long count = Stream.of(words)
  .filter(w -> w.length() > 12)
  .count();
```

现在，你不需要扫描循环来寻找过滤和计数的证据了。方法名会立即告诉你代码意图要做什么。此外，循环详尽地规定了操作顺序，而流能够以任何想要的方式调度操作，只要结果正确即可。

只需将 `stream` 改为 `parallelStream`，流库即可并行过滤和计数。

```java
long count = words.parallelStream()
  .filter(w -> w.length() > 12)
  .count();
```

流遵循“做什么，而不是怎么做”的原则。在流示例中，我们描述了需要做什么：获取长单词并进行计数。我们没有指定这应该以什么顺序或在哪个线程中发生。相比之下，本节开头的循环精确指定了计算应该如何工作，从而放弃了任何优化机会。

流看起来与集合非常相似，允许你转换和检索数据。但它们存在显著差异：

1. 流不存储其元素。元素可能存储在底层集合中，或按需生成。
2. 流操作不会改变源。例如，`filter` 方法不会从流中删除元素，而是产生一个不包含这些元素的新流。
3. 流操作在可能的情况下是惰性的（lazy）。这意味着在需要结果之前，它们不会执行。

## 1.2. 流的创建

你已经看到，可以通过 `Collection` 接口的 `stream` 方法将任何集合转换为流。如果你有一个数组，请使用静态方法 `Stream.of`。

```java
Stream<String> words = Stream.of(contents.split("\\s+"));
```

在前面的示例中，我们从 `split` 方法返回的数组创建流。`of` 方法具有变长参数，因此你可以从任意数量的参数构造流：

```java
Stream<String> song = Stream.of("gently", "down", "the", "stream");
```

使用 `Arrays.stream(array, from, to)` 从数组的一部分创建流。

创建一个空元素流，使用静态方法 `Stream.empty`：

```java
Stream<String> silence = Stream.empty();
// 泛型类型 <String> 被推断；等同于
```

`Stream` 接口有两个用于创建无限流的静态方法。`generate` 方法接收一个无参数函数（从技术上讲，一个 `Supplier<T>` 接口对象）。每当需要流值时，就会调用该函数来产生一个值。你可以获取常量值的流，如：

```java
Stream<String> echos = Stream.generate(() -> "Echo");
```

或者随机数的流，如：

```java
Stream<Double> randoms = Stream.generate(Math::random);
```

要产生如 0 1 2 3 . . 这样的序列，请使用 `iterate` 方法。它接收一个“种子”值和一个函数（技术上，是一个 `UnaryOperator<T>`），并反复地将该函数应用于上一个结果。例如：

```java
Stream<BigInteger> integers = Stream.iterate(
    BigInteger.ZERO,
    n -> n.add(BigInteger.ONE)
);
```

序列中的第一个元素是 `BigInteger.ZERO`。第二个元素是 $f(seed)$，产生 1（作为一个大整数）。下一个元素是 $f(f(seed))$，产生 2，以此此类推。

若要产生一个有限流，请添加一个指定迭代何时结束的谓词：

```java
var limit = new BigInteger("10000000");

Stream<BigInteger> integers = Stream.iterate(
    BigInteger.ZERO,
    n -> n.compareTo(limit) < 0,
    n -> n.add(BigInteger.ONE)
);
```

一旦谓词拒绝了迭代生成的值，流就会结束。

最后，`Stream.ofNullable` 方法从一个对象创建一个非常短的流。如果对象为 null，则流长度为 0；否则长度为 1，仅包含该对象。这通常与 `flatMap` 结合使用——参见第 1.7.7 节。

Java API 中的许多方法都会产生流。例如，`String` 类有一个 `lines` 方法，可以产生包含字符串中所有行的流：

```java
Stream<String> greetings = "Hello\nGutenTag\nBonjour".lines();
```

`Pattern` 类有一个 `splitAsStream` 方法，可以通过正则表达式对 `CharSequence` 进行分割。你可以使用以下语句将字符串分割单词：

```java
Stream<String> words =
    Pattern.compile("\\PL+").splitAsStream(contents);
```

`Scanner.tokens` 方法产生扫描器的标记流。从字符串获取单词流的另一种方法是：

```java
Stream<String> words = new Scanner(contents).tokens();
```

静态的 `Files.lines` 方法返回文件中所有行的流：

```java
try (Stream<String> lines = Files.lines(path)) {
  Process lines
}
```

注意，使用 `try-with-resources` 块来关闭文件。

在 Java API 中以流的形式提供数据变得越来越常见。例如，Java 21 添加了一个静态的 `availableLocales` 方法，产生 `Locale` 对象的流。

> **注意：** 为了产生有限流，你始终可以将元素添加到列表中，然后将其转换为流。`Stream.Builder` 接口为此目的效率略高：

```java
Stream<Integer> digits(int n) {
    Stream.Builder<Integer> builder = Stream.builder();

    while (n != 0) {
        builder.add(n % 10);
        n = n / 10;
    }

    return builder.build();
}
```

要查看本节引入的流之一的内容，使用 `toList` 方法，它将流的元素收集到列表中。与 `count` 一样，`toList` 是终端操作。如果流是无限的，先用 `limit` 方法对其截断：

```java
System.out.println(Stream.generate(Math::random).limit(10).toList());
```

**注意：** 为了将 `Iterator` 或不是集合的通用 `Iterable` 转换为流，你需要使用 `spliterators` 的辅助方法。分割器（splitter）类似于迭代器，但它可以被分割，使得每个生成的分割器都产生元素的一部分。这种分割被用于并行处理元素——参见[第 1.13 节](#)。

如果你有一个 `Iterator` 并想要其结果的流，使用：

```java
StreamSupport.stream(
    Spliterators.spliteratorUnknownSize(
        iterator,
        Spliterator.ORDERED
    ),
    false
);
```

如果你有一个不是集合的 `Iterable`，可以通过调用将其转换为流：

```java
StreamSupport.stream(iterable.spliterator(), false);
```

**警告：** 在执行流操作期间，不要修改支持流的集合是非常重要的。记住，流并不会收集它们的数据——数据始终存储在单独的集合中。如果你修改了该集合，流操作的结果将变得未定义。JDK 文档将此要求称为“非干涉”（noninterference）。

准确来说，由于中间流操作是惰性的，可能在终端操作执行之前变异集合。例如，下面的代码虽然绝对不建议，但可以工作：

```java
List<String> wordList = new ArrayList<>();

Stream<String> words = wordList.stream();

wordList.add("END");

long n = words.distinct().count();
```

但这段代码是错误的：

```java
Stream<String> words = wordList.stream();

words.forEach(s -> {
    if (s.length() < 12)
        wordList.remove(s);
});

// ERROR--interference
```

列表 1.2 中的示例显示了创建流的各种方式。

## 列表 1.2 `v2ch01/streams/CreatingStreams.java`

```java
package v2ch01.streams;

import module java.base;

class CreatingStreams {
    void main() throws Exception {
        Path path = Path.of("test.txt");

        try (Stream<String> lines = Files.lines(path)) {
            Stream<String> words =
                lines.flatMap(
                    l -> Pattern.compile("\\PL+").splitAsStream(l)
                );
            Stream<String> song = words.limit(10);
            List<String> firstElements = song.toList();

            System.out.print("First elements: ");

            for (int i = 0; i < firstElements.size(); i++) {
                if (i > 0) System.out.print(", ");

                if (i < 10) {
                    System.out.print(firstElements.get(i));
                } else {
                    System.out.print("...");
                }
            }

            System.out.println();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## `java.util.regex.Pattern` 1.4

- `Stream<String> splitAsStream(CharSequence input)` 8  
  产生一个流，其元素是输入中由此模式分隔的分段。

## `java.nio.file.Files` 7

- `static Stream<String> lines(Path path)` 8
- `static Stream<String> lines(Path path, Charset cs)` 8  
  产生一个流，其元素是指定文件的行，使用 UTF-8 或指定的字符集。

## `java.util.stream.StreamSupport` 8

- `static <T> Stream<T> stream(Spliterator<T> spliterator, boolean parallel)`  
  产生一个包含给定可拆分迭代器产生的流。

## `java.lang.Iterable` 5.0

- `Spliterator<T> spliterator()` 8  
  产生一个此 `Iterable` 的可拆分迭代器。默认实现不拆分，也不报告一个

## `java.util.Scanner` 5.0

- `public Stream<String> tokens()` 9  
  产生一个通过调用此扫描器方法返回的字符串流。

## `java.util.function.Supplier<T>` 8

- `T get()`  
  提供一个值。

## 1.3. `filter`、`map` 和 `flatMap` 方法

流转换产生一个流，其元素派生自另一个流。你已经见过 `filter` 转换，它会产生一个包含符合特定条件的元素的新流。在这里，我们将一个字符串流转换为另一个只包含长单词的流：

```java
List<String> wordList = . . ;

Stream<String> longWords =
    wordList.stream().filter(w -> w.length() > 12);
```

`filter` 的参数类型是 `Predicate<T>`——也就是说一个从 T 到布尔值的函数。

通常，你想要以某种方式转换流中的值。使用 `map` 方法并传递执行转换的函数。例如，你可以这样将所有单词转换为小写：

```java
Stream<String> lowercaseWords =
    words.stream().map(String::toLowerCase);
```

在这里，我们使用了方法引用的 `map`。通常，你会使用 lambda 表达式代替：

```java
Stream<Character> firstCodeUnits =
    words.stream().map(s -> s.charAt(0));
```

生成的流包含每个单词的第一个代码单元。当你使用 `map` 时，函数被应用于每个元素，产生一个由返回值的新流。现在考虑返回值为流的情况。以下方法产生一个字符串中所有字符簇（grapheme clusters）的流：

```java
public static Stream<String> graphemeClusters(String s) {
    return Stream.of(s.split(""));
}
```

例如，`graphemeClusters("Ahoy ")` 是包含 "A", "h", "o", "y" 和 "" 的字符串流，由多个值。现在我们在字符串流上映射 `graphemeClusters` 方法：

```java
List<String> wordList = List.of(..);

Stream<String> result =
    wordList.stream().map(w -> graphemeClusters(w));
```

你将得到一个流的流，例如 ["y", "o", "r"], ["b", "a", "t"]。要将其展平为单个流，请使用 `flatMap` 方法而不是 `map`：

```java
Stream<String> flatResult =
    words.stream().flatMap(w -> graphemeClusters(w));
```

有时，为每个结果产生一个流是低效的。与其产生一个结果流，不如生成结果并将它们传递给收集器（collector）——一个实现函数接口的对象。对于每个结果，调用收集器的 `accept` 方法。让我们通过示例来这样做。以下循环遍历字符串 s 的字符簇：

```java
BreakIterator iter = BreakIterator.getCharacter();

iter.setText(s);

int start = iter.first();
int end = iter.next();

while (end != BreakIterator.DONE) {
    String gc = s.substring(start, end);

    // 对 gc 进行操作

    start = end;
    end = iter.next();
}
```

调用 `mapMulti` 时，你提供一个带有流元素和收集器的函数。在你的函数中将结果给收集器：

```java
Stream<String> result =
    words.stream().mapMulti((s, collector) -> {
        iter.setText(s);

        int start = iter.first();
        int end = iter.next();

        while (end != BreakIterator.DONE) {
            String gc = s.substring(start, end);
            collector.accept(gc);

            start = end;
            end = iter.next();
        }
    });
```




# `java.util.stream.Stream<T>`（Java 8）

- `Stream<T> filter(Predicate<? super T>)`  
  产生此流中符合谓词的元素。
- `<R> Stream<R> map(Function<? super T, extends R> mapper)`  
  产生对此流元素应用 `mapper` 产生的流。
- `<R> Stream<R> flatMap(Function<? super T, extends Stream<? extends R>> mapper)`  
  通过连接对此流元素应用 `mapper` 的流。（注意每个 `mapper` 结果是一个流）。
- `<R> Stream<R> mapMulti(BiConsumer<? super T, super Consumer<R>> mapper)`（Java 16）

## 1.4. 提取子流和合并流

`stream.limit(n)` 返回一个在 `n` 个元素后结束的新流（如果原始流更短则结束）。该方法对于限制无限流的大小特别有用。例如：

```java
Stream<Double> randoms =
    Stream.generate(Math::random).limit(100);
```

产生一个包含 100 个随机数的流。

`stream.skip(n)` 调用恰好相反。它丢弃前 `n` 个元素。这在我们阅读书籍示例中非常方便，由于 `split` 方法的工作方式，第一个元素是一个不需要的空字符串。我们可以通过调用 `skip` 让它消失：

```java
Stream<String> words =
    Stream.of(contents.split("\\P+")).skip(1);
```

`stream.takeWhile(predicate)` 调用在谓词为真时获取流的所有元素，然后停止。例如，假设我们使用上一节的 `graphemeClusters` 方法将字符串分为字符，并想要收集所有的初始数字。`takeWhile` 方法可以做到：

```java
Stream<String> initialDigits =
    graphemeClusters(str).takeWhile(
        s -> "0123456789".contains(s));
```

`dropWhile` 方法相反，在条件为真时丢弃元素，并产生从第一个条件为假的元素开始的流。例如：

```java
Stream<String> withoutInitialWhitespace =
    graphemeClusters(str).dropWhile(
        s -> s.strip().length() == 0);
```

你可以使用 `Stream` 类的静态方法 `concat` 合并两个流：

```java
Stream<String> combined =
    Stream.concat(
        graphemeClusters("Hello"),
        graphemeClusters("World"));
```

```java
// 产生流 ["H", "e", "l", "l", "o", "W", "o", "r", "l", "d"]
```

当然，第一个流不应是无限的——否则第二个流将没有机会。

每当元素被检索时都会执行操作。这对于调试非常有用：

```java
Object[] powers = Stream.iterate(1.0, p -> p * 2)
    .peek(e -> IO.println("Fetching " + e))
    .limit(20)
    .toArray();
```

当元素被实际访问时，会打印一条消息。通过这种方式，你可以验证 `iterate` 返回的无限流是否是惰性处理的。

> **提示：** 当你使用调试器调试流计算时，可以在从某个转换操作中调用的方法中设置断点。在大多数 IDE 中，你也可以在 lambda 表达式中设置断点。如果你只想知道流流水线中某一点发生了什么，可以添加：

```java
.peek(x -> {
    return;
})
```

并在第二行上设置断点。

| `java.util.stream.Stream<T>` | 8 |
| :--- | :--- |
| `Stream<T> distinct()` | 返回此流中去重元素的流。 |
| `Stream<T> sorted()` |  |
| `Stream<T> sorted(Comparator<? super T> comparator)` | 返回一个元素按排序顺序排列的流。第一个方法要求元素是实现 `Comparable` 类的实例。 |
| `Stream<T> peek(Consumer<? super T> action)` | 返回一个与此流元素相同的流，在消费每个元素时将其传递给 `action`。 |

## 1.6. 简单归约（Simple Reductions）

现在你已经了解了如何创建和转换流，我们将进入最重要的点——从流数据中获取答案。本节涵盖的方法称为*归约*（reductions）。归约是*终端操作*（terminal operations）。它们将流归约为一个非流值，该值可以在你的程序中使用。

你已经见过一个简单的归约了：`count` 方法，它返回流中元素的数量。

其他的简单归约还有 `max` 和 `min`，它们返回最大值或最小值。这里有一个不同之处——这些方法返回一个 `Optional<T>` 值，该值封装了答案，或者表示没有结果（因为流恰好为空）。在过去，在这种情况下返回 `null` 是很常见的。但在测试不完全的程序中发生这种情况时，会导致空指针异常。`Optional` 类型是表示缺失返回值的更好方法。我们将在下一节中详细讨论 `Optional`。以下是你可以获取流的最大值：

```java
Optional<String> largest =
    words.map(String::compareToIgnoreCase);

IO.println("largest: " + largest.orElse(""));
```

`findFirst` 返回非空集合中的第一个值。它与 `filter` 结合使用时通常非常有用。例如，在这里我们找到第一个以字母 Q 开头的单词，如果它存在：

```java
Optional<String> startsWithQ =
    words.filter(s -> s.startsWith("Q"))
         .findFirst();
```

如果你对任何匹配项都接受，而不只是第一个，请使用 `findAny` 方法。当对流进行并行处理时，这种方法非常有效，因为流可以报告它找到的任何匹配项，而不是受限于第一个。

```java
Optional<String> startsWithQ =
    words.parallel()
         .filter(s -> s.startsWith("Q"))
         .findAny();
```

如果你只想知道是否存在匹配项，请使用带有谓词参数的终端操作 `anyMatch`：

```java
boolean aStartsWithWithQ =
    words.parallel()
         .anyMatch(s -> s.startsWith("Q"));
```

还有 `allMatch` 和 `noneMatch` 方法，如果所有元素或没有元素匹配谓词，则返回 `true`。这些方法也从并行运行中获益。

| `java.util.stream.Stream<T>` | 8 |
| :--- | :--- |
| `Optional<T> max(Comparator<? super T> comparator)` | 使用给定比较器定义的顺序返回此流的最大或最小元素，如果此流为空则返回一个空的 `Optional`。这些是终端操作。 |
| `Optional<T> findFirst()` | 返回此流的第一个或任意元素，如果此流为空则返回一个空的 `Optional`。这些是终端操作。 |
| `Optional<T> findAny()` |  |
| `boolean allMatch(Predicate<? super T> predicate)` | 如果此流的任何、所有或无元素匹配给定的谓词，则返回 `true`。这些是终端操作。 |
| `boolean noneMatch(Predicate<? super T> predicate)` |  |

## 1.7. `Optional` 类型

`Optional<T>` 对象是 `T` 类型对象或无对象的封装。在前一种情况下，我们说该值是*呈现的*（present）。`Optional<T>` 类型旨在作为 `T` 类型引用的安全替代方案，它可以引用对象或为 `null`。但只有当你正确使用它时它才是安全的。接下来的三节将向你展示如何。

### 1.7.1. 获取 `Optional` 值

有效使用 `Optional` 的关键是使用一种方法：在值不存在时*产生替代方案*，或者仅在值存在时*消费该值*。

在本节中，我们来看第一种策略。通常，当没有匹配时你有一个想要使用的默认值，可能是空字符串：

```java
String result = optionalString.orElse("");

// 封装的字符串，如果没有则是 ""
```

你也可以调用代码来计算默认值：

```java
String result = optionalString.orElseGet(() ->
    // 函数只有在需要时才被调用
    "default value");
```

或者在没有值时抛出异常：

```java
String result = optionalString.orElseThrow(() ->
    new IllegalStateException("No value"));
```

| `java.util.Optional` | 8 |
| :--- | :--- |
| `T orElse(T other)` | 如果此 `Optional` 为空，则返回 `other`。 |
| `T orElseGet(Supplier<? extends T> other)` | 如果此 `Optional` 为空，则返回 `other` 的结果。 |
| `<X extends Throwable> T orElseThrow(Supplier<? extends X> exceptionSupplier)` | 如果此 `Optional` 为空，则抛出 `exceptionSupplier`。 |

### 1.7.2. 消费 `Optional`

在前节中，你看到了如何在存在时产生替代方案。处理可选值的另一种策略是仅在值存在时消费它。

`ifPresent` 方法接受一个函数。如果可选值存在，将其传递给该函数。否则，什么都不会发生。

```java
optionalValue.ifPresent(v ->
    // 处理 v);
```

例如，如果你想在值存在时将其添加到集合中，调用：

```java
optionalValue.ifPresent(v -> results.add(v));
```

或者简单地：

```java
optionalValue.ifPresent(results::add);
```

如果你想在 `Optional` 有值时执行一个操作而在没有时执行另一个操作，使用 `ifPresentOrElse`：

```java
optionalValue.ifPresentOrElse(
    v -> IO.println("Found " + v),
    () -> logger.warning("No match"));
```

| `java.util.Optional` | 8 |
| :--- | :--- |
| `void ifPresent(Consumer<? super T> action)` | 如果此 `Optional` 非空，将其值传递给 `action`。 |
| `void ifPresentOrElse(Consumer<? super T> action, Runnable emptyAction)` | 如果此 `Optional` 非空，将其值传递给 `action`，否则调用 `emptyAction`。 |

### 1.7.3. `Optional` 值的流水化

在前面的节中，你看到了如何从 `Optional` 对象中获取值。另一种有效的策略是保持 `Optional` 完整。你可以通过 `map` 方法转换 `Optional` 内部的值：

```java
Optional<Path> transformed =
    optionalString.map(Path::of);
```

如果 `optionalString` 为空，那么 `transformed` 也是空的。

同样，你可以使用 `filter` 方法只考虑某些属性的 `Optional` 值，在转换之前或之后。如果不符合该属性，流水线将产生一个空结果：

```java
Optional<Path> transformed = optionalString
    .filter(s -> s.endsWith(".txt"))
    .map(Path::of);
```

你可以使用 `or` 方法为空的 `Optional` 提供替代的 `Optional`。替代方案是惰性计算的。

```java
Optional<String> result = optionalString.or(() ->
    // 提供一个 Optional
    alternatives.stream().findFirst());
```

如果 `optionalString` 有值，那么 `result` 就是 `optionalString`。如果不是，则计算 lambda 表达式并使用其结果。

## `java.util.Optional`（Java 8）

- `Optional<U> map(Function<? super T,? extends U> mapper)`  
  返回一个 `Optional`，如果此 `Optional` 的值存在，则通过将给定函数应用于该值来获取结果；否则返回一个空的 `Optional`。
- `Optional<T> filter(Predicate<? super T> predicate)`  
  如果此 `Optional` 的值满足指定的谓词，则返回包含该值的 `Optional`；否则返回一个空的 `Optional`。
- `Optional<T> or(Supplier<? extends Optional<? extends T>> supplier)`  
  如果此 `Optional` 不为空，则返回它本身；否则返回由 `supplier` 产生的 `Optional`。

### 1.7.4. 如何不正确使用 `Optional` 值

如果你不正确使用 `Optional` 值，那么你并比过去的“某个值或 `null`”方法没有任何好处。

`get` 方法在 `Optional` 的值存在时获取其被包装的元素，如果不存在则抛出 `NoSuchElementException`。因此：

```java
Optional<T> optionalValue = . . .;

optionalValue.get().someMethod();
```

这并不比下面的代码安全：

```java
T value = . . .;

value.someMethod();
```

`isPresent` 和 `isEmpty` 方法报告一个 `Optional<T>` 对象是否有值。但是：

```java
if (optionalValue.isPresent())
    optionalValue.get().someMethod();
```

这并不比下面的代码简单：

```java
if (value != null)
    value.someMethod();
```

> **提示：** 如果你发现自己在使用 `get`、`isPresent` 或 `isEmpty` 方法，请尝试重新思考你的方法，并使用前两个节中的策略之一。

> **注意：** `orElseThrow` 方法是一个听起来很吓人的 `get` 方法别词。当你调用 `optionalValue.orElseThrow().someMethod()` 时，如果 `optionalValue` 为空，将发生异常将变得非常明确。希望程序员只有在绝对确定这种情况不会发生时才使用 `orElseThrow`。

这里是关于正确使用 `Optional` 类型的更多提示：

- `Optional` 类型的变量永远不应该为 `null`。
- 不要使用 `Optional` 类型的字段。代价是额外的一个对象。在类内部，对于缺失的字段使用 `null`。为了抑制人们使用 `Optional` 字段，该类是不可序列化的。
- `Optional` 类型的方法参数是值得怀疑的。在请求的值存在的常见情况下，它们会让调用变得不愉快。相反，可以考虑该方法的两个重载版本，一个带参数，一个不带参数。（另一方面，返回一个 `Optional` 是好的。它是指示函数可能没有结果的标准方法。）
- 不要将 `Optional` 对象放入 `set` 中，也不要把它们作为 `map` 的键。相反，收集值。

| 方法 | 说明 |
| :--- | :--- |
| `T get()` | 返回此 `Optional` 的值，如果它为空则抛出 `NoSuchElementException`。 |
| `T orElseThrow()` | 返回此 `Optional` 的值，如果它为空则抛出 `NoSuchElementException`。 |
| `boolean isEmpty()` | 如果 `Optional` 为空则返回 `true`。 |
| `boolean isPresent()` | 如果 `Optional` 不为空则返回 `true`。 |

### 1.7.5. 创建 `Optional` 值

到目前为止，我们讨论了如何使用别人创建的 `Optional` 对象。如果你想写一个创建 `Optional` 对象的方法，有几个静态方法用于此目的，包括 `Optional.of(result)` 和 `Optional.empty()`。例如：

```java
public static Optional<Double> inverse(Double x) {
    return x == 0
        ? Optional.empty()
        : Optional.of(1 / x);
}
```





`ofNullable` 方法旨在作为可能为 `null` 的值到可选值的桥梁。

如果 `obj` 不为 `null`，`Optional.ofNullable(obj)` 返回 `Optional.of(obj)`，否则返回 `Optional.empty()`。

- `static <T> Optional<T> of(T value)`
- `static <T> Optional<T> nullable(T value)`  
  返回一个带有给定值的 `Optional`。如果 `value` 为 `null`，第一个方法会抛出 `NullPointerException`，而第二个方法返回一个空的 `Optional`。
- `static <T> Optional<T> empty()`  
  返回一个空的 `Optional`。

### 1.7.6. 使用 `flatMap` 组合 `Optional` 值函数

假设你有一个方法 `f` 返回一个 `Optional<T>`，并且目标类型 `T` 有一个返回 `Optional<U>` 的方法 `g`。如果它们是普通方法，你可以通过调用 `s.f()...g()` 来组合它们。但这种组合不起作用，因为 `s.f()` 的类型是 `Optional<T>` 而不是 `T`。相反，调用：

```java
Optional<U> result = s.f().flatMap(T::g);
```

如果 `s.f()` 存在，则对它应用 `g`。否则，返回一个空的 `Optional<U>`。

显然，如果你有更多产生 `Optional` 值的方法或 lambda 表达式，你可以重复该过程。你可以通过链式调用 `flatMap` 构建一个步骤流水线，只有当所有部分都成功时才会成功。

例如，考虑前节中安全的 `inverse` 方法。假设我们还有一个安全的平方根方法：

```java
public static Optional<Double> squareRoot(Double x) {
    return x < 0 ? Optional.empty() :
        Optional.of(Math.sqrt(x));
}
```

那么你可以这样计算倒数的平方根：

```java
Optional<Double> result = inverse(arg).flatMap(x -> squareRoot(x));
```

我们可以通过从一个 `Optional` 开始让这样的链看起来更规整一些：

```java
Optional<Double> result =
    Optional.of(arg).flatMap(x -> squareRoot(x));
```

使用方法引用看起来甚至更整洁：

```java
Optional<Double> result =
    Optional.of(arg).flatMap(this::squareRoot);
```

```java
33 optionalValue.ifPresent(results::add);

34 Optional<Boolean> added =
35 OptionalValue.map(results::add);

36 IO.println(added);

38 IO.println(inverse(4.0).flatMap(this::squareRoot));

39 IO.println(inverse(-1.0).flatMap(this::squareRoot));

40 IO.println(inverse(0.0).flatMap(this::squareRoot));

41 Optional<Double> result2 = Optional.of(-4.0)

42 .flatMap(this::inverse)

43 .flatMap(this::squareRoot);

44 IO.println(result2);

46 }

47 Optional<Double> inverse(Double x) {

48 return x == 0 ? Optional.empty() : Optional.of(1 /

49 x);

50 }

51 Optional<Double> squareRoot(Double x) {

52 return x < 0 ? Optional.empty() :

53 Optional.of(Math.sqrt(x));

53 }
```

## `java.util.Optional<U>`

- `<U> Optional<U> flatMap(Function<? super T,Optional<U>> mapper)` 9  
  产生将 `mapper` 应用于此 `Optional` 值的结果；如果此 `Optional` 为空，则返回一个空的 `Optional`。

## 1.8. 收集结果

当你完成流（stream）的操作后，通常会希望查看结果。你可以调用 `iterator` 方法，它会产生一个旧式的迭代器，你可以用它来访问元素。

或者，你可以调用 `forEach` 方法将函数应用到每个元素：

```java
stream.forEach(IO::println);
```

在并行流（parallel stream）上，`forEach` 方法以任意顺序遍历元素。如果你想按照流的顺序处理它们，请调用 `forEachOrdered`。当然，你可能会放弃部分或全部的并行带来的益处。

但大多数情况下，你可能更希望将结果收集到数据结构中。你已经见过了 `toList` 方法，它产生包含流元素的列表。

调用 `toArray` 来获取流元素的数组。

由于在运行时无法创建泛型数组，表达式 `stream.toArray()` 返回 `Object[]` 数组。如果你想获取正确类型的数组，请传入数组构造函数：

```java
String[] result = stream.toArray(String[]::new);

// stream.toArray() 的类型为 Object[]
```

要将结果收集到其他数据结构，`Stream` 接口有一个泛型 `collect` 方法。你可以将结果拼接成字符串，将它们存储在任何集合中，并将它们插入 map 中。通过实现自己的收集器（collector），你可以以任意方式消费流数据。你将在后续章节中看到细节。

## `java.util.stream.BaseStream` 8

- `Iterator<T> iterator()`  
  产生一个用于获取此流元素的迭代器。这是一个终端操作。

## `java.util.stream.Stream<T>` 8

- `List<T> toList()` 16  
  产生此流中元素的列表。
- `void forEach(Consumer<? super T> action)`  
  对流的每个元素调用 `action`。
- `Object[] toArray()`
- `<A> A[] toArray(IntFunction<A[]> generator)`  
  产生一个对象数组，或者当传入构造器引用 `A::new` 时产生类型 `A` 的数组。这些都是终端操作。
- `<R,A> R collect(Collector<? super T,A,R> collector)`  
  使用给定的收集器收集流中的元素。`Collectors` 类为许多收集器提供了工厂方法。

## 1.9. `Collectors`

为了将流元素收集到另一个目标，有一个方便的 `collect` 方法，它接受 `Collector` 接口的实例。收集器是一个累积元素并产生结果的对象。

`Collectors` 类为常见的收集器提供了大量的工厂方法。

假设你想通过拼接收集流中的所有的字符串。你可以调用：

```java
String result = stream.collect(Collectors.joining());
```

如果你想在元素之间添加分隔符，请将其传递给 `joining` 方法：

```java
String result = stream.collect(Collectors.joining(", "));
```

如果你的流包含字符串以外的对象，你需要先将它们转换为字符串，如下所示：

```java
String result = stream.map(Object::toString).collect(Collectors.joining(", "))
```

如果你想将流结果归约为和、计数、平均值、最大值或最小值，请使用 `summarizingInt(Int|Long|Double)` 方法之一。这些方法接受一个将流对象映射为数字的函数，并产生类型为 `(Int|Long|Double)SummaryStatistics` 的结果，同时计算和、计数、平均值、最大值、最小值。

```java
IntSummaryStatistics summary = stream.collect(Collectors.summarizingInt(String::length));

double averageWordLength = summary.getAverage();

double maxWordLength = summary.getMax();
```

注意，你并不是在流上调用 `joining` 和 `summarizingInt` 方法。这些是 `Collectors` 类的静态方法。它们产生 `Collector` 实例，并传递给 `Stream` 接口的 `collect` 方法。

`joining` 收集器产生字符串，而 `summarizing` 收集器产生四个数字。然而，大多数收集器是在数据结构中收集，正如你将在后续章节看到的。

列表 1.5 中的示例程序展示了如何从流中收集元素。

### 列表 1.4

```java
package;

import java.util.*;
import java.util.stream.*;
import java.nio.file.*;
import java.io.IOException;

class CollectingResults {

    public static void main(String[] args) {
        String contents = Files.readString(Path.of("gutenberg.txt"));
        Stream<String> words = Stream.of(contents.split("\\W+"));
        Iterator<String> vowels = words.filter("[aeiouAEU]");

        while (vowels.hasNext()) {
            IO.println(vowels.next());
        }

        String[] numbers = vowels.limit(10).toArray();

        IO.println(": " + Arrays.toString(numbers));

        String result = vowels.collect(Collectors.joining(", "));

        IO.println("Joining: " + result);

        IntSummaryStatistics summary =
            words.collect(Collectors.summarizingInt(String::length));

        double averageWordLength = summary.getAverage();
        double maxWordLength = summary.getMax();

        IO.println("Average length: " + averageWordLength);
        IO.println("Max length: " + maxWordLength);
    }

    public static <T> void show(String label, Set<T> set) {
        IO.print(label + ": ");

        IO.println(
            set.stream()
                .limit(10)
                .map(Object::toString)
                .collect(Collectors.joining(", ")) + "]"
        );
    }
}
```

## `java.util.stream.Collectors` 8

- `static Collector<CharSequence,?,String> joining()`
- `static Collector<CharSequence,?,String> joining(CharSequence delimiter)`
- `static Collector<CharSequence,?,String> joining(CharSequence delimiter, CharSequence prefix, CharSequence suffix)`  
  产生一个在第一个字符串前拼接 `prefix`、最后一个字符串后拼接 `suffix` 的收集器。如果没有指定，这些为空。
- `static <T> Collector<T,?,IntStatistics> summarizingInt(ToIntFunction<? super T> mapper)`
- `static <T> Collector<T,?,LongStatistics> summarizingLong(ToLongFunction<? super T> mapper)`
- `static <T> Collector<T,?,DoubleStatistics> summarizingDouble(ToDoubleFunction<? super T> mapper)`  
  产生 `(Int|Long|Double)SummaryStatistics` 对象的收集器，从中获取 `mapper` 应用于每个元素的计数、和、平均值、最大值和最小值。

| `java.util.IntSummaryStatistics` | 8 |
|---|---:|
| `java.util.LongSummaryStatistics` | 8 |
| `java.util.DoubleSummaryStatistics` | 8 |

- `long getCount()`  
  产生汇总元素的计数。
- `long getSum()`
- `double getAverage()`  
  产生汇总元素的和或平均值，如果没有元素，则返回 0。
- `long getMax()`
- `long getMin()`  
  产生汇总元素的最大值或最小值，如果没有元素，则返回对应的 `(Integer|Long|Double).(MAX|MIN)_VALUE`。

### 1.9.1. 收集到集合

`toList` 方法是在 Java 16 中添加的，之前你必须使用 `Collectors.toList()` 产生的收集器：

```java
List<String> result = stream.collect(Collectors.toList());
```

同样，这里是如何将流元素收集到集合中的：

```java
Set<String> result =
    stream.collect(Collectors.toSet());
```

这些调用会为你返回一个列表或集合，但你无法对其进行任何进一步的假设。该集合可能是不可变的、不可序列化的，或者不是线程安全的。如果你想控制获取的是哪种集合，请使用下面的调用：

```java
TreeSet<String> result =
    stream.collect(Collectors.toCollection(TreeSet::new));
```

列表 1.5 中的示例程序展示了如何将元素放入集合中。

### 列表 1.5

`v2ch01/collecting/CollectingResults.java`

```java
package v2ch01.collecting;

import java.base;

class CollectingResults {

    void main() throws Exception {
        // 将流转换为迭代器
        Iterator<Integer> iter =
            Stream.iterate(0, n -> n + 1).limit(10).iterator();

        while (iter.hasNext()) {
            IO.out.println(iter.next());
        }

        Object[] numbers =
            Stream.iterate(0, n -> n + 1).limit(10).toArray();

        IO.out.println(
            "Object array: " + numbers + " " + Arrays.toString(numbers)
        );

        // 注意这是一个 Object[] 数组
        try {
            var number = (Integer) numbers[0]; // OK
            IO.out.println("number: " + number);
        } catch {
            IO.println("以下语句抛出了异常：");
            var _ = (Integer[]) numbers; // 抛出异常
        } catch (ClassCastException e) {
            IO.println(e);
        }
    }
}
```




```java
Integer[] numbers3 = Stream.iterate(0, n -> n + 1).limit(10).toArray(Integer[]::new);

IO.println("Integer array: " + numbers3 + " " + Arrays.toString(numbers3));

// 注意这是一个 Integer[]

String result = noVowels().limit(10).collect(Collectors.joining(", "));

IO.println(": " + result);

result = noVowels().limit(10).collect(Collectors.joining(", "));

IO.println("Joining with commas: " + result);

IntSummaryStatistics summary = noVowels().collect(Collectors.summarizingInt(String::length));

double averageWordLength = summary.getAverage();

double maxWordLength = summary.getMax();

IO.println("Max word length: " + maxWordLength);

IO.println("ForEach:");

noVowels().limit(10).forEach(IO::println);

}

Stream<String> noVowels() throws Exception {

String contents = Files.readString(Path.of("gutenberg,alice30.txt"));

Stream<String> words = contents.split("\\W+");

return words.map(s -> s.replaceAll("[aeiouAEIOU]", ""));

}

<T> void show(String label, Set<T> set) {

IO.print(label + ": " + set.getClass().getName());

IO.println("");

}

set.stream().limit(10).map(Object::toString).collect(Collectors.joining(", "));

}
```

## `java.util.stream.Collectors`（Java 8）

- `static <T> Collector<T?, List<T>> toList()`
- `static <T> Collector<T?, List<T>> toUnmodifiableList()`（Java 10）
- `static <T> Collector<T?, Set<T>> toSet()`
- `static <T> Collector<T?, Set<T>> toUnmodifiableSet()`（Java 10）

返回一个将元素收集到列表或集合的收集器。

- `static <T> Collector<T, C extends Collection<T>> Collector<T?, C> toCollection(Supplier<C> collectionFactory)`

返回一个收集到任意集合的收集器。传递一个构造引用，如 `TreeSet::new`。

## 1.9.2. Maps

假设你有一个 `Stream<Person>`，并希望将元素收集到 map 中，以便以后通过 ID 查找人员。调用 `Collectors.toMap` 并传入 map 的键和值的函数。例如：

```java
public record Person(int id, String name) {}

Map<Integer, String> idToName = people.collect(
    Collectors.toMap(Person::id, Person::name));
```

在值应该是元素的常见情况下，对第二个函数使用 `Function.identity()`。

```java
Map<Integer, Person> idPerson = people.collect(
    Collectors.toMap(Person::id, Function.identity()));
```

如果有多个具有相同的键，就会发生冲突，收集器将抛出 `IllegalStateException`。你可以通过提供第三个函数来覆盖该行为，根据现有值和新值确定键的值。你的函数可以返回现有值、新值或两者的组合。

在这里，我们构建一个 map，其中包含每个 locale 在其默认语言中的名称（如 "German"）以及其本地化名称（如 "Deutsch"）。

```java
Map<String, String> languageNames = Locale.availableLocales().collect(
    Collectors.toMap(
        Locale::getDisplayName,
        loc -> loc.getDisplayName(loc)));
```

**注意：** 在本章中，我使用 `Locale` 类作为数据源。现在假设我们想知道某个国家的所有语言。我们需要 `Map<String, Set<String>>`。例如，“Switzerland”的值是 `[French, German, Italian]`。每当发现某个国家的新语言时，我们将现有集合和新集合合并。

```java
Map<String, Set<String>> countryLanguageSets =
    Locale.availableLocales().collect(
        Collectors.toMap(
            Locale::setDisplayCountry,
            l -> Collections.singleton(l.getLanguage()),
            (a, b) -> { // a 和 b 的并
                Set<String> union = new HashSet<>(a);
                union.addAll(b);
                return union;
            }));
```

将在本节看到获取此 map 的更简单的方法。如果你需要 `TreeMap`，请将构造函数作为第四个参数。这是开头的一个示例，现在返回 `TreeMap`：

```java
Map<Integer, Person> idToPerson = people.collect(
    Collectors.toMap(
        Person::id,
        Function::identity(),
        (existingValue, newValue) -> {
            throw new IllegalStateException();
        },
        TreeMap::new));
```

**注意：** 对于每个 Map 方法，都有相应的 ConcurrentMap 方法。与并行流一起使用，共享 map 比合并 map 更高效。注意元素不再按流顺序收集，但这通常没有区别。列表 1.6 中的程序给出了将流结果收集到 map 的示例。

### 列表 1.6：`v2ch01/collecting/CollectingMaps.java`

| 列表 1.6 | v2ch01/collecting/CollectingMaps.java |
| :--- | :--- |
| 1 | `package v2ch01.collecting;` |
| 2 | `import java.base;` |
| 3 | `record Person(int id, String name) {}` |
| 4 | `class CollectingMaps {` |
| 5 | `void main() throws Exception {` |
| 6 | `Map<Integer, String> idToName = people()` |
| 7 | `.collect(Collectors.toMap(Person::id,` |
| 8 | `Person::name));` |
| 9 | `IO.println("idToName: " + idToName);` |
| 10 | `Map<Integer, Person> idToPerson = people()` |
| 11 | `.collect(Collectors.toMap(Person::id,` |
| 12 | `Function.identity()));` |
| 13 | `IO.println("idToPerson: " +` |
| 14 | `idToPerson.getClass().getName() + idToPerson);` |
| 15 | `idToPerson = people().collect(` |
| 16 | `Collectors.toMap(Person::id,` |
| 17 | `Function::identity(), (l, _) -> {` |
| 18 | `throw new IllegalStateException();` |
| 19 | `}, TreeMap::new());` |
| 20 | `IO.println("idToPerson: " +` |
| 21 | `idToPerson.getClass().getName() + idToPerson);` |
| 22 | `Map<String, String> languageNames =` |
| 23 | `.collect(Locale.availableLocales())` |
| 24 | `.collect(Collectors.toMap(Locale::getDisplayNameCountry,` |
| 25 | `l -> l.getLanguage(l),` |
| 26 | `(existingValue, _) ->` |
| 27 | `IO.println("languageNames: " + languageNames);` |
| 28 | `Map<String, Set<String>> countryLanguageSets =` |
| 29 | `.collect(Collectors.toMap(Locale::getDisplayNameCountry,` |
| 30 | `l -> Set.of(l.getLanguage()),` |
| 31 | `(a, b) -> { // a 和 b 的并` |
| 32 | `Set<String> union = new HashSet<>(a);` |
| 33 | `union.addAll(b);` |
| 34 | `return union;` |
| 35 | `});` |
| 36 | `IO.println("countryLanguageSets: " +` |
| 37 | `countryLanguageSets);` |
| 38 | `}` |
| 39 | `static Stream<Person> people() {` |
| 40 | `return Stream.of(new Person(1001, "Peter"),` |
| 41 | `Person(1002, "Paul"),` |
| 42 | `new Person(1003, "Mary"));` |
| 43 | `}` |

## `java.util.stream.Collectors`（Java 8）

- `static <T> Collector<T?, List<T>> toList()`
- `static <T> Collector<T?, List<T>> toUnmodifiableList()`（Java 10）
- `static <T> Collector<T?, Set<T>> toSet()`
- `static <T> Collector<T?, Set<T>> toUnmodifiableSet()`（Java 10）

返回一个将元素收集到列表或集合的收集器。

- `static <T> Collector<T, C extends Collection<T>> Collector<T?, C> toCollection(Supplier<C> collectionFactory)`

返回一个收集到任意集合的收集器。传递一个构造引用，如 `TreeSet::new`。

```java
K> keyMapper, Function<? super T?, extends U> valueMapper, BinaryOperator<U> mergeFunction

static <T, K, U, M extends ConcurrentMap<K, U>>
Collector<?, M> toConcurrentMap(
    Function<? super T?, extends K> keyMapper,
    Function<? super T?, extends U> valueMapper,
    BinaryOperator<U> mergeFunction,
    Supplier<M> mapSupplier)
```

返回一个产生 map、不可修改 map 或并发 map 的收集器。`keyMapper` 和 `valueMapper` 函数被应用于每个收集到的元素，生成结果 map 的键/值条目。默认情况下，当两个元素产生相同的键时，会抛出 `IllegalStateException`。你可以提供一个 `mergeFunction` 来合并具有相同键的值。默认情况下，结果是 `ConcurrentHashMap`。你也可以提供一个 `mapSupplier` 来产生所需的 map 实例。

### 1.9.3. 分组与分区

在前面的节中，你已经看到了如何收集特定国家的所有语言。但这个过程有点繁琐。你必须为每个 map 值生成一个单例集，并指定如何合并旧值和新值。对具有相同特征的值进行分组是非常常见的，因此 `groupBy` 方法直接支持这种操作。

让我们来看看按国家对 locale 进行分组。首先，构建这个 map：

```java
Map<String, List<Locale>> countryToLocales =
    Locale.availableLocales().collect(
        Collectors.groupBy(Locale::getCountry));
```

函数 `Locale::getCountry` 是分组的分类器。你现在可以查找特定国家代码的所有 locale，例如：

```java
List<Locale> swissLocales = countryToLocales.get("CH");

// 返回 locales de_CH, fr_CH, it_CH 等可能更多
```

> **注意：** 快速回顾 locale（区域语言）：每个 locale 都有一个语言代码（如英语的 `en`）和一个国家代码（如美国的 `US`）。locale `en_US` 描述在美国使用的英语，而 `en_IE` 是爱尔兰的英语。某些国家有多个 locale。例如，`ga_IE` 是爱尔兰的盖尔克语，正如前面的示例所示，JDK 至少知道瑞士的三个 locale。

分类器函数是一个谓词函数（即返回布尔值的函数），流元素被划分为两个列表：函数返回 `true` 的元素和它们的补集。在这种情况下，使用 `partitioningBy` 比使用 `groupingBy` 更高效。例如，我们将所有 locale 分为使用英语的 locale 和其他所有：

```java
Map<Locale, List<Locale>> englishAndOtherLocales =
    Locale.availableLocales().collect(
        Collectors.partitioningBy(
            l -> l.getLanguage().equals("en")));

List<Locale> englishAndOtherLocales =
    englishAndOtherLocales.get(true);
```

> **注意：** 如果你调用 `groupingByConcurrent` 方法，你会得到一个并发 map，当与并行流一起使用时会被并发填充。这与 `ConcurrentMap` 方法完全类似。

## `java.util.stream.Collectors`（Java 8）

- `static <T, K> Collector<T, ?, Map<K, List<T>>> groupingBy(Function<? super T, ? extends K> classifier)`
- `static <T, K> Collector<T, ?, ConcurrentMap<K, List<T>>> groupingByConcurrent(Function<?...`
- `static <T> Collector<T, ?, Map<Boolean, List<T>>> partitioningBy(Predicate<? super T> predicate)`

返回一个产生 map 的收集器，其键为 `true`/`false`，值为满足/不满足谓词元素的列表。

### 1.9.4. 下游收集器

`groupingBy` 方法产生一个值为列表的 map。如果你想以某种方式处理这些列表，请提供一个**下游收集器**（downstream collector）。例如，如果你想要集而不是列表，可以使用你在前面的节中看到的 `Collectors.toSet` 收集器：

```java
Map<String, Set<Locale>> countryToLocaleSet =
    Locale.availableLocales().collect(
```



`groupingBy(Locale::getCountry, toSet()))`

> 注意：在这个示例中以及本节剩余的示例中，我假设静态导入了 `java.util.stream.Collectors.*` 以使表达式更易读。

你也可以应用两次 `groupingBy`：

```java
Map<String, Map<String, List<Locale>>> countryAndLanguageToLocale =
    Locale.availableLocales().collect(
        groupingBy(Locale::getCountry,
            groupingBy(Locale::getLanguage)));
```

然后，`countryAndLanguageToLocale.get("IN").get("hi")` 是印度印地语 locale 的列表。（有几种变体。）

提供了几个收集器将收集到的元素还原为数字：

- `counting` 产生收集元素的计数。例如：

  ```java
  Map<String, Long> countryToLocaleCounts =
      Locale.availableLocales().collect(
          groupingBy(Locale::getCountry,
              counting()));
  ```

  统计每个国家有多少 locale。

- `summingInt`、`summingLong`、`summingDouble` 和对应的 `averaging` 收集器对下游元素应用提供的函数，并产生函数结果的和或平均值。例如：

  ```java
  public record City(String name, String state, int population) {}

  Map<String, Double> stateToPopulation =
      cities.collect(
          groupingBy(City::state,
              averagingInt(City::population)));
  ```

- `maxBy` 和 `minBy` 接受一个比较器并产生结果：

  ```java
  Map<String, Optional<City>> stateToCity =
      cities.collect(
          groupingBy(City::state,
              maxBy(Comparator.comparing(City::population))));
  ```

- `collectingAndThen` 可以在下游收集器完成后应用一个函数：

  ```java
  Map<Character, Integer> stringCountsByLetter =
      strings.collect(
          groupingBy(s -> s.charAt(0),
              collectingAndThen(toSet(), Set::size)));
  ```

- `mapping` 对下游元素应用提供的映射函数，并将结果交给下游收集器。例如：

  ```java
  Map<Character, Set<Integer>> stringLengthsByLetter =
      strings.collect(
          groupingBy(s -> s.charAt(0),
              mapping(String::length, toSet())));
  ```

- `filtering` 收集器对每个分组应用过滤器：

  ```java
  Map<String, Set<City>> largeCitiesByState =
      cities.collect(
          groupingBy(City::state,
              filtering(c -> c.population() > 500000,
                  toList()))); // 没有大城市的州将为空集
  ```

最后，你可以使用 `teeing` 收集器分支到两个下游收集器。每当你需要从流中计算多个结果时，这非常有用。假设你想收集城市名称并同时计算它们的平均人口。你不能读取两次流，但 `teeing` 允许你执行两次计算。指定两个下游收集器以及一个合并结果的函数。

```java
record Pair<S, T>(S first, T second) {}

Pair<List<String>, Double> result =
    cities.filter(c -> c.state().equals("NV"))
        .collect(teeing(
            mapping(City::name, toList()), // 第一个下游收集器
            averagingDouble(City::population), // 第二个下游收集器
            (list, avg) -> new Pair(list, avg))); // 合并函数
```

# 列表 1.7

`v2ch01/collecting/DownstreamCollectors.java`

```java
package v2ch01.collecting;

import static java.util.stream.Collectors.*;

import java.base;

record City(String name, String state, int population) {}

class DownstreamCollectors {

    void main() throws Exception {

        Map<String, Set<Locale>> countryToLocaleSet =
            Locale.availableLocales().collect(
                groupingBy(Locale::getCountry, toSet()));

        Map<String, Map<String, List<Locale>>> countryLanguageToLocale =
            Locale.availableLocales().collect(
                groupingBy(Locale::getCountry,
                    groupingBy(Locale::getLanguage)));

        System.out.println(
            "Hindi locales in India: "
                + countryLanguageToLocale.get("IN"));

        Map<String, Long> countryToLocaleCounts =
            Locale.availableLocales().collect(
                groupingBy(Locale::getCountry, counting()));

        System.out.println(
            "countryToLocaleCounts: "
                + readCities("v2ch01/cities.txt"));

        Map<String, Integer> stateToCityPopulation =
            cities.collect(
                groupingBy(City::state,
                    summingInt(City::population)));

        System.out.println(
            "stateToCityPopulation: "
                + stateToCityPopulation);
```

```java
31 List<City> cities = readCities("v2ch01/cities.txt");

32 Map<String, Optional<String>> stateLongestCityName
33     = cities.collect(groupingBy(
34         City::state, mapping(City::name,
35             maxBy(Comparator.comparing(String::length)))));

36 System.out.println("stateLongestCityName: " +
37     stateLongestCityName);

38 Map<String, Set<String>> countryToLanguages =
39     Locale.availableLocales())
40         .collect(groupingBy(Locale::getDisplayCountry,
41             mapping(Locale::getDisplayLanguage,
42                 toSet());

43 System.out.println("countryToLanguages: " +
44     countryToLanguages);

45

46 cities = readCities("v2ch01/cities.txt");

47 Map<String, IntSummaryStatistics> stateToPopulationSummary =
48     cities.collect(groupingBy(City::state,
49         summarizingInt(City::population)));

50 System.out.println(stateToPopulationSummary.get("NY"));

51

52 cities = readCities("v2ch01/cities.txt");

53 Map<String, String> stateToCityNames =
54     cities.collect(groupingBy(City::state,
55         reducing("", City::name, (s, t) -> s.length() ==
56             0 ? t : s + ", " + t))); // 注意：OCR 中的逻辑似乎略有错误

57

58 cities = readCities("v2ch01/cities.txt");

59 stateToCityNames = cities
60     .collect(groupingBy(City::state,
61         mapping(City::name, joining(", ")))));

62 System.out.println("stateToCityNames: " + stateToCityNames);

63 cities = readCities("v2ch01/cities.txt");

64 record Pair<S, T>(S first, T second) {
65 }

66 Pair<String, Double> result = cities.filter(c
67     -> c.state().equals("NV")).collect(
68         collecting(mapping(City::name, toList()),
69             averagingDouble(City::population),
70             (names, avg) -> new Pair<>(names, avg)));

71 System.out.println(result);

72 }

73 Stream<City> readCities(String filename) throws
```

```java
IOException {

    65 return Files.lines(Path.of(filename)).map(l ->
        l.split(", "))

    66     .map(a -> new City(a[0], a[1],
        Integer.parseInt(a[2])));

67 }

68 }
```

# `java.util.stream.Collectors` 8

- `static <T,K,A,D> groupingBy(Function<? super T,? extends K> classifier, Collector<? super T,A,D> downstream)` 返回一个产生 map 的收集器。键是将分类器应用于所有收集元素的元素的。值是使用下游收集器对具有相同键的元素进行收集的结果。
- `static <T> Collector<T,?,Long> counting()` 返回一个计算收集元素的收集器。
- `static <T> Collector<T,?,Integer> summingInt(ToIntFunction<? super T> mapper)`
- `static <T> Collector<T,?,Long> summingLong(ToLongFunction<? super T> mapper)`
- `static <T> Collector<T,?,Double> summingDouble(ToDoubleFunction<? super T> mapper)`
- `static <T> Collector<T,?,Optional<T>> maxBy(Comparator<? super T> comparator)`
- `static <T> Collector<T,?,Optional<T>> minBy(Comparator<? super T> comparator)` 返回一个使用指定排序计算收集元素最大或最小值的收集器。
- `static <T,A,R,RR> Collector<T,A,RR> collectingAndThen(Collector<T,A,R> downstream, Function<R,RR> finisher)`
- `static <T,A,R> Collector<T,A,R> mapping(Function<? super T, ? extends U> mapper, Collector<? super U,A,R> downstream)`
- `static <T,A,R> Collector<T,A,R> flatMap(Function<? super T, ? extends Stream<? extends U>> mapper, Collector<? super U,A,R> downstream)`
- `static <T,A,R> Collector<T,A,R> filtering(Predicate<? super T> predicate, Collector<? super T,A,R> downstream)`

## 元素

以下是使用方法：

```java
Stream<Integer> numbers = . . .;

List<Integer> sampled =
    numbers.collect(randomSampling(0.05)); // 大约每20个元素取一个
```

如果我们不想将接受的元素放在列表中怎么办？

API 应该支持下游收集器（downstream collectors）。方法如下：

```java
<T, A, R> Collector<T, A, R>
randomSampling(double p, Collector<T, A, R>
    downstream) {

    BiConsumer<A, T> downstreamAccumulator =
        downstream.accumulator();

    return Collector.of(
        downstream.supplier(),
        (resultContainer, e) -> {
            if (Math.random() < p)
                downstreamAccumulator.accept(resultContainer, e);
        },
        downstream.combiner(),
        downstream.finisher(),
        downstream.characteristics().toArray(
            Collector.Characteristics[]::new));
}
```

在这里，`downstream` 是一个接受类型为 `T` 的元素的收集器，其结果容器类型为 `A`，结果类型为 `R`。

我们可以复用 `downstream` 的 `supplier`、`combiner` 和 `finisher`，但我们必须适配它的 `accumulator`，以便只有部分传入的元素被插入。

遗憾的是，API 在这个特定的用例上仍有改进空间。我必须将 `downstream` 的特征集转换为数组，以适应可变参数参数。

列表 1.8 中的程序包含了完整的示例。

# 列表 1.8

`v2ch01/collecting/ImplementingCollectors.java`

```java
package v2ch01.collecting;

import module java.base;

class ImplementingCollectors {

    void main() {

        System.out.println(
            IntStream.range(1, 1000)
                .boxed()
                .parallel()
                .collect(randomSampling(0.05)));

        System.out.println(
            IntStream.range(1, 1000)
                .boxed()
                .parallel()
                .collect(randomSampling(
                    0.05, Collectors.toSet())));
    }
}

static <T> Collector<T, List<T>, List<T>> randomSampling(double p) {
```



```java
return Collector.of(ArrayList<T>::new,

    (resultContainer, e) -> {

        if (Math.random() < p)

            resultContainer.add(e);

    },

    (rc1, rc2) -> { rc1.addAll(rc2); return rc1; },

    Function.identity());

}
```

```java
<T, A, R> Collector<T, A, R> randomSampling(double p,

Collector<T, A, R> downstream) {

    BiConsumer<A, T> downstreamAccumulator = downstream.accumulator();

    return Collector.of(downstream.supplier(),

    (resultContainer, e) -> {

        if (Math.random() < p)

            downstreamAccumulator.accept(resultContainer, e);

    },

    downstream.combiner(),

    downstream.finisher(),

    Collector.Characteristics.IDENTITY_FINISH);

}
```

```java
downstream.characteristics().toArray(Collector.Characteristics[]::new);

}
```

## `java.util.stream.Collector<T, A, R>`

- `Supplier<A> supplier()`：提供新结果容器的函数。
- `BiConsumer<A, T> accumulator()`：将流中的元素整合到结果容器中的函数。
- `BinaryOperator<A> combiner()`：合并两个结果容器的函数。
- `Function<A, R> finisher()`：将最终结果容器转换为收集器结果的函数。
- `Set<Collector.Characteristics> characteristics()`：此收集器的特征。
- `static <T,A,R> Collector<T,A,R> of(Supplier<A> supplier, BiConsumer<A,T> accumulator, BinaryOperator<A> combiner, Function<A,R> finisher, Collector.Characteristics...)`：产生一个具有给定 `supplier`、`accumulator`、`combiner`、`finisher` 和特征的收集器。

## 1.10. 规约操作（Reduction Operations）

`reduce` 方法是另一种从流中计算值的通用机制。特别是对于数学运算，指定一个规约操作比使用 `collector` 实现相同的操作要容易得多。最简单的形式接受一个二元函数并从前两个元素开始不断应用它。如果函数是求和，那么解释起来就很简单：

```java
List<Integer> values = . . .;

Optional<Integer> sum = values.stream().reduce((x, y) -> x + y);
```

在这种情况下，`reduce` 方法计算 $v_0 + v_1 + v_2 + ...$，其中 $v_j` 是流元素。该方法返回一个 `Optional`，因为如果流为空，则没有结果。

> **注意：** 在这种情况下，你可以用 `reduce(Integer::sum)` 代替 `reduce((x, y) -> x + y)`。

更通用地说，你可以使用任何将部分结果 $x$ 与下一个值 $y$ 结合以产生新部分结果的操作。

另一种看待规约的视角是：给定一个规约操作 $op$，规约产生 $v_0 \text{ op } v_1 \text{ op } v_2 \dots$，其中 $v_i$ 是流元素。特别是对于数学运算，指定一个规约操作比使用 `collector` 实现相同的操作要容易得多。最简单的形式接受一个二元函数并从前两个元素开始不断应用它。如果函数是求和，那么解释起来就很简单：

```java
List<Integer> values = . . ++;

Optional<Integer> sum = values.stream().reduce((x, y) -> x + y);
```

在这种情况下，`reduce` 方法计算 $v_0 + v_1 + v_2 + ...$，其中 $v_j$ 是流元素。该方法返回一个 `Optional`，因为如果流为空，则没有结果。

> **注意：** 在这种情况下，你可以用 `reduce(Integer::sum)` 代替 `reduce((x, y) -> x + y)`。

## 11.11.1. 定义的 Gatherer（Gatherers）

`Gatherers` 类提供了几个 `Gatherer` 实现。`windowFixed` 和 `windowSliding` gatherer 将相邻元素组合在一起，产生一个列表流。通过示例展示它们的运行效果比用文字解释更直观：

```java
IntStream.range(0, 10).boxed().gather(Gatherers.windowFixed(4)).toList()

// [[0, 1, 2, 3], [4, 5, 6, 7], [8, 9]]

IntStream.range(0, 10).boxed().gather(Gatherers.windowSliding(4)).toList()

// [[0, 1, 2, 3], [1, 2, 3, 4], [2, 3, 4, 5], [3, 4, 5, 6], [4, 5, 6, 7], [5, 6, 7, 8], [6, 7, 8, 9]]
```

`windowSliding` gatherer 用于比较流中的相邻元素。例如，这里是丢弃相邻的重复元素：

```java
Stream.concat(words, Stream.of((String) null))
    .gather(Gatherers.windowSliding(2))
    .filter(w -> !w.get(0).equalsIgnoreCase(w.get(1)))
    .map(w -> w.get(0))
```

通过向流中添加一个 `null`，可以将最后一个元素与某些内容进行比较。

`mapConcurrent` gatherer 与 `map` 类似，但计算在虚拟线程中运行。这对于阻塞操作非常有用。例如，如果你有一个 URL 列表，可以并发地读取它们。

```java
String read(String url) {

    try {

        return new String(URI.create(url).toURL().openStream().readAllBytes());

    } catch (IOException e) {

        throw new UncheckedIOException(e);

    }

}
```

```java
int max = 100; // 最大并发线程数

List<String> contents = urls.stream()
    .gather(Gatherers.mapConcurrent(this::read))
    .toList();
```

如果其中一个计算抛出异常，所有剩余任务将被取消，异常将被重新抛出。

> **注意：** 如你将在第 1.13 节中看到的，并行流用于在多个处理器核心上并行处理计算密集型任务。相比之下，`mapConcurrent` gatherer 主要用于大部分阻塞的并发操作。

最后，还有 `fold` 和 `scan` gatherer。`fold` 是一种重复应用操作的通用机制。它从初始值 `iv` 开始并计算 `(((iv op v0) op v1) op v2 op vn) ...`，其中 `vj` 是流元素。

这看起来与你在第 1.10 节看到的 reduction 相似。然而，`reduction` 用于可并行化的操作。`fold` 本质上是顺序的，且操作不需要满足结合律。

一些函数式程序员喜欢 `fold`，因为任何循环都可以转换为 `fold`。考虑从十进制数字计算一个数字：

```java
int n = 0;

for (int d : digits)
    n = 10 * n + d;
```

下面是使用 `fold` 实现的相同计算：

```java
int n = digits.stream()
    .gather(Gatherers.fold(() -> 0, (x, y) -> x * 10 + y))
    .findFirst()
    .orElse(0);
```

`fold` gatherer 产生一个包含一个元素的流，或者如果 `digits` 为空则产生空流。

如示例所示，你必须为初始值提供一个供应者（supplier），以及一个重复应用的操作。

> **注意：** 将折叠实现为 gatherer 而不是 collector 似乎很奇怪。由于它产生单个结果，将其作为一种终端操作（terminal operation）会更自然。但 collectors 无法表示它们必须按顺序接收流元素。如你将在第 11.11.2 节中看到的，gatherers 具有这种能力。但一个 gatherer 必须产生一个流；在这种情况下，长度为零或一。

还有一个 `scanner`，它可以产生包含所有中间结果的流。例如：

```java
Stream.of(1, 7, 2, 9)
    .gather(Gatherers.scan(() -> 0, (x, y) -> x * 10 + y))
    .toList() // [1, 17, 172, 1729]
```

## 11.1.2. 实现 Gatherers

实现一个 gatherer 与实现一个 collector（第 9.5 节）类似。一个 gatherer 有四个方法：

- `Supplier<A> initializer()`：提供状态。
- `BiFunction<A, T, Downstream<? super R>> integrator()`：处理元素。
- `BinaryOperator<A> combiner()`：合并两个状态（用于并行流）。
- `Function<A, R> finisher()`：在流结束后调用。

通常情况下，你不需要为不需要的初始化器、`combiner` 和 `finisher` 提供参数。使用仅包含你需要的 gatherer 的重载版本。

**提示：** 使用这些工厂方法而不是声明式类。这样工作量更小，而且更容易看出你的 gatherer 是顺序的还是可并行的。

你可能会好奇流如何区分这两者。如果 `combiner` 方法返回与默认方法返回相同的“无操作”实例，则该 gatherer 是顺序的。工厂方法处理了这一细节。

如果你声明了自己的类，则需要小心。顺序 gatherer **不应该**重写 `combiner`，而是保留默认方法。如果你有一个不需要 `combiner` 的可并行 gatherer，你仍然需要声明一个。

例如，让我们实现一个采样 gatherer：

```java
static class IntermediateState {

    long index = -1;

}

<T> Gatherer<T, IntermediateState> sampling(int n) {

    return Gatherer.ofSequential(

        IntermediateState::new,

        (state, e, downstream) -> {

            state.index++;

            if (state.index % n == 0)

                return downstream.push(e);

            else

                return true;

        }

    );

}
```

下面是如何使用它来采样第 `n` 个元素：

```java
List<String> samples = word.stream().gather(sampling(50)).toList();
```

采样 gatherer 没有 `combiner` 或 `finisher`。还有一个用于构建并行 gatherer 的 `Gatherer.of` 方法。

通过实现 `Gatherer.Integrator.Greedy` 接口来指示这一事实。为此有一个工厂方法：

```java
<T> Gatherer<T, IntermediateState, T>
sampling(int n) {

    return Gatherer.ofSequential(

        IntermediateState::new,

        Gatherer.Integrator.ofGreedy((state, e, downstream) -> {

            state.index++;

            if (state.index % n == 0)

                return downstream.push(e);

            else

                return true;

        })

    );

}
```




> **提示：** 你可以创建一个实现接口的类，但使用工厂方法更容易。

> **提示：** 你在第一个实现中看到的 `Gatherer.Integrator.of` 方法并不是必须的。我们可以使用 lambda 表达式，会被转换为 `Gatherer.Integrator`。但工厂方法能更清晰地告诉读者这不是贪婪整合器。

正如你所看到的，编写自己的 gatherer 起初可能看起来有些可畏，但它并没有那么复杂。请遵循以下步骤：

1. 决定你的 gatherer 是否可以并行执行（`Gatherer.of`），或者是否必须按顺序处理元素（`Gatherer.ofSequential`）。
2. 决定整合器是否可以短路（`Gatherer.Integrator.of`）或是否始终接受元素（`Gatherer.Integrator.ofGreedy`）。
3. 你需要状态吗？如果需要，为状态提供一个类；如果你的 gatherer 不是顺序的，请实现一个合并器（combiner）。
4. 在整合器中，在短路时或下游 push 被拒绝时返回 `false`。

> 注意：与收集器（collectors）不同，gatherers 不使用枚举来表示它们的特征。它们使用这些替代机制：

1. 贪婪 gatherer 的整合器实现了 `Gatherer.Integrator.Greedy`。否则，该 gatherer 是短路的。
2. 顺序 gatherer 的合并器是由 `Gatherer.defaultCombiner()` 返回的对象。否则，该 gatherer 是可并行的。
3. 无状态 gatherer 的初始化器是由 `Gatherer.defaultInitializer()` 返回的对象。

否则，该 gatherer 是状态的。

## `java.util.Stream<T>` 8

- `<R> Stream<R> gather(Gatherer<? T, ?, R> gatherer)` 24

产生一个通过给定的 gatherer 处理此流的元素而产生的流。

## `java.util.stream.Gatherers` 24

- `static <TR> Gatherer<TR,?,List<TR>> windowFixed(int windowSize)`
- `static <TR> Gatherer<TR,?,List<TR>> windowSliding(int windowSize)`

产生一个 gatherer，将流元素分组为给定大小的独立或重叠窗口。

- `static <T,R> Gatherer<T,?,R> fold(Supplier<R> initial, BiFunction<? super R, ? super T, ?extends R> folder)`
- `static <T,R> Gatherer<T,?,R> scan(Supplier<R> initial, BiFunction<? super R, ? super T, ?extends R> scanner)`

产生一个 gatherer，重复地将二元操作应用于上一个结果和下一个流元素。`fold` 只产生最终结果，而 `scan` 产生所有中间结果。

- `static <T,R> Gatherer<T,?,R> mapConcurrent(int maxConcurrency, Function<? super T, ? extends R> mapper)`

产生一个 gatherer，应用给定的函数，在最多 `maxConcurrency` 个虚拟线程中运行计算，产生结果流。

## `java.util.stream.Gatherer.Downstream<T>` 24

- `boolean push(T element)`

将元素推送到处理流水线的下一个阶段。如果元素被拒绝，则返回 `false`。

- `boolean isRejecting()`

如果处理流水线不再接受元素，则返回 `true`。

## `java.util.stream.Gatherer<T, A, R>` 24

- `Supplier<A> initializer()`
- `Gatherer.Integrator<A,T,R> integrator(`
- `BinaryOperator<A> combiner(`
- `BiConsumer<A, Gatherer.Downstream<? super R>> finisher())`

返回此 gatherer 的初始化器、整合器、合并器和终结器。

- `static <T,R> Gatherer<T,Void,R> of(Gatherer.Integrator<Void,T,R> integrator)`
- `static <T,R> Gatherer<T,Void,R> of(Gatherer.Integrator<Void,T,R> integrator, BiConsumer<Void, Gatherer.Downstream<? super R>> finisher)`

```java
static <T,A,R> Gatherer<T,A,R> of(
    Supplier<A> initializer,
    Gatherer.Integrator<A,T,R> integrator,
    BinaryOperator<A> combiner,
    BiConsumer<A, Gatherer.Downstream<? super R>> finisher
)
```

产生一个具有给定初始化器、整合器、合并器和终结器的可并行 gatherer。如果没有初始化器时，该 gatherer 是无状态的。

- `static <T,R> Gatherer<T,Void,R> ofSequential(Gatherer.Integrator<Void,T,R> integrator)`
- `static <T,R> Gatherer<T,Void,R> ofSequential(Supplier<A> initializer, Gatherer.Integrator<A,T,R> integrator, BinaryOperator<A> combiner, BiConsumer<A, Gatherer.Downstream<? super R>> finisher)`

产生一个具有给定初始化器、整合器、合并器和终结器的可并行 gatherer。（注：原文此处 OCR 存在重复和格式错误）

# 12. 原始类型流（Primitive Type Streams）

到目前，我们已经在 `Stream<Integer>` 中收集了整数，尽管包装每个整数效率很低。对于其他原始类型——`double`、`long`、`char`、`byte` 也是如此。流具有专门类型 `IntStream`、`LongStream` 和 `DoubleStream`，它们直接存储原始类型，而无需包装。

创建 `IntStream`，使用 `IntStream.of` 和 `Arrays.stream` 方法：

```java
IntStream stream = IntStream.of(1, 2, 3, 5);

stream = Arrays.stream(values); // values 是 int[]
```

与对象流一样，你也可以使用静态 `generate` 和 `iterate` 方法。此外，`IntStream` 和 `LongStream` 拥有静态 `range` 和 `rangeClosed` 方法，生成带步长的整数范围：

```java
IntStream zeroToNinetyNine = IntStream.range(0, 100); // 排除上界

IntStream zeroToHundred = IntStream.rangeClosed(0, 100); // 包含上界
```

`CharSequence` 接口拥有 `codePoints` 和 `chars` 方法，产生一个 `IntStream`，包含字符的 Unicode 编码或 UTF-16 编码中的代码单元。（详情见第 2 章。）

```java
String greeting = "Ahoy ☜";

IntStream codes = greeting.codePoints();

// 值为 67, 105, 97, 111, 32, 12988, 8205, 65039 的流
```

`RandomGenerator` 接口拥有 `ints`、`longs` 和 `doubles` 方法，返回随机数的原始类型流。

```java
IntStream randomIntegers = RandomGenerator.getDefault().ints();
```

- `toArray` 方法返回原始类型数组。
- 返回可选结果的方法返回 `OptionalInt`、`OptionalLong` 或 `OptionalDouble`。这些类与 `Optional` 类类似，但它们拥有的是 `getAsInt`、`getAsLong` 和 `getAsDouble` 方法，而不是 `get` 方法。
- 有 `sum`、`average`、`max` 和 `min` 方法分别返回和、计数、平均值、最大值最小值。这些方法未为对象流定义。
- `summaryStatistics` 方法产生 `IntSummaryStatistics`、`LongSummaryStatistics` 或 `DoubleSummaryStatistics` 对象，可以同时报告流的和、计数、平均值、最大值最小值。

列表 1.9 中的程序给了原始类型流 API 的示例。

## 列表 1.9

`v2ch01/streams/PrimitiveTypeStreams.java`

```java
1 package v2ch01.streams;

2 import module java.base;

3

4 class PrimitiveTypeStreams {

5   void main(throws) throws Exception {

6     IntStream is1 = IntStream.generate(() -> (int)

7     (Math.random() * 100));

8     show("is1", is1);

9     IntStream is2 = IntStream.range(5, 10);

10    show("is2", is2);

11    IntStream is3 = IntStream.rangeClosed(5, 10);

12    show("is3", is3);

13

14 String contents =

15 Files.readString(Path.of("gutenberg", "alice30.txt"));

16

17 Stream<String> words =

18 Stream.of(contents.split("\\P+"));

19 IntStream is4 = words.mapToInt(String::length);

20 show("is4", is4);

21 String sentence = "\uD835\uDD46 is the set of

22 octonions.\n";

23 System.println(sentence);

24 IntStream codes = sentence.codePoints();

25 System.println(codes.mapToObj(c -> "%X

26 " ").formatted(c).collect(Collectors.joining())));

27

28 Stream<Integer> integers = IntStream.range(0,

29 100).boxed();

30 IntStream is5 = integers.mapToInt(Integer::intValue);

31 show("is5", is5);

32

33 void show(String title, IntStream stream) {

34 final int SIZE = 10;

35 int[] firstElements = stream.limit(SIZE +

36 1).toArray();

37 for (int i = 0; i < firstElements.length; i++) {

38 if (i > 0) System.out.print(", ");

39 if (i < SIZE)

40 System.out.println(firstElements[i]);

41 else

42 System.out.print("...");

43 }

44 System.out.println();

45 }
```




# `java.util.stream.IntStream`（Java 8）

- `static IntStream range(int startInclusive, int endExclusive)`
- `static IntStream rangeClosed(int startInclusive, int endInclusive)`

产生一个包含给定范围内整数的 `IntStream`。

- `static IntStream of(int... values)`

产生一个包含给定元素的 `IntStream`。

- `int[] toArray()`

产生一个包含此流元素的数组。

- `int sum()`
- `OptionalDouble average()`
- `OptionalInt max()`
- `OptionalInt min()`
- `IntSummaryStatistics summaryStatistics()`

产生此流中元素的和、平均值、最大值或最小值，或者一个可以从其中获得所有这四个值的对象。

- `Stream<Integer> boxed()`

产生一个包含此流中元素的包装对象的流。

# `java.util.stream.LongStream`（Java 8）

- `static LongStream range(long startInclusive, long endExclusive)`
- `static LongStream rangeClosed(long startInclusive, long endInclusive)`

产生一个包含给定范围内整数的 `LongStream`。

- `static LongStream of(long... values)`

产生一个包含给定元素的 `LongStream`。

- `long[] toArray()`

产生一个包含此流元素的数组。

- `long sum()`
- `OptionalLong average()`
- `OptionalLong max()`
- `OptionalLong min()`
- `LongSummaryStatistics summaryStatistics()`

产生此流中元素的和、平均值、最大值或最小值，或者一个可以从其中获得所有这四个值的对象。

- `Stream<Long> boxed()`

产生一个包含此流中元素的包装对象的流。

# `java.util.stream.DoubleStream`（Java 8）

- `static DoubleStream of(double... values)`

产生一个包含给定元素的 `DoubleStream`。

- `double[] toArray()`

产生一个包含此流元素的数组。

- `double sum()`
- `OptionalDouble average()`
- `OptionalDouble max()`
- `OptionalDouble min()`
- `DoubleSummaryStatistics summaryStatistics()`

产生此流中元素的和、平均值、最大值或最小值，或者一个可以从其中获得所有这四个值的对象。

- `Stream<Double> boxed()`

产生一个包含此流中元素的包装对象的流。

# `java.lang.CharSequence`

- `IntStream codePoints()`

产生一个包含所有 Unicode 点的流。

# `java.util.random.RandomGenerator`（Java 17）

- `IntStream ints()`
- `IntStream ints(int startInclusive, int endExclusive)`
- `IntStream ints(int startInclusive, int endExclusive, long count)`
- `IntStream ints(int startInclusive, long bound, long count)`
- `LongStream ints(long startInclusive, long endExclusive)`
- `LongStream ints(long startInclusive, long endExclusive, long count)`
- `LongStream ints(long startInclusive, long bound, long count)`
- `DoubleStream ints(double startInclusive, double endExclusive)`
- `DoubleStream ints(double startInclusive, double endExclusive, long count)`
- `DoubleStream ints(double startInclusive, double bound, long count)`

# `java.util.stream.OptionalInt`（Java 8）

- `static OptionalInt of(int value)`

产生一个带有值的 `OptionalInt`。

- `int getInt()`

返回该值，如果不存在则抛出 `NoSuchElementException`。

- `int getInt(int other)`

返回该值，如果不存在则返回 `other`。

- `int getInt(IntSupplier other)`

返回该值，如果不存在则返回提供者的值。

- `boolean isPresent()`

如果存在值则返回 `true`。

- `void ifPresent(IntConsumer action)`

如果存在值则执行操作。

# `java.util.IntSummaryStatistics`（Java 8）

- `long count()`
- `long sum()`
- `double average()`
- `long max()`
- `long min()`

# `java.util.LongSummaryStatistics`（Java 8）

- `long count()`
- `long sum()`
- `double average()`
- `long max()`
- `long min()`

# `java.util.DoubleSummaryStatistics`（Java 8）

- `long count()`
- `double sum()`
- `double average()`
- `double max()`
- `double min()`

# `java.util.stream.OptionalLong`（Java 8）

- `static OptionalLong of(long value)`

产生一个带有值的 `OptionalLong`。

- `long getLong()`

返回该值，如果不存在则抛出 `NoSuchElementException`。

- `long getLong(long other)`

返回该值，如果不存在则返回 `other`。

- `long getLong(LongSupplier other)`

返回该值，如果不存在则返回提供者的值。

- `boolean isPresent()`

如果存在值则返回 `true`。

- `void ifPresent(LongConsumer action)`

如果存在值则执行操作。

# `java.util.stream.OptionalDouble`（Java 8）

- `static OptionalDouble of(double value)`

产生一个带有值的 `OptionalDouble`。

- `double getDouble()`

返回该值，如果不存在则抛出 `NoSuchElementException`。

- `double getDouble(double other)`

返回该值，如果不存在则返回 `other`。

- `double getDouble(DoubleSupplier other)`

返回该值，如果不存在则返回提供者的值。

- `boolean isPresent()`

如果存在值则返回 `true`。

- `void ifPresent(DoubleConsumer action)`

如果存在值则执行操作。

## 1.13 并行流

Streams 使并行化操作变得简单。这个过程大部分是自动的，但你需要遵循一些规则。首先，你必须有一个并行流。你可以通过任何集合的 `parallelStream()` 方法获取并行流：

```java
Stream<String> parallelWords = words.parallelStream();
```

此外，`parallel()` 方法可以将任何顺序流转换为并行流。

```java
Stream<String> parallelWords = Stream.of(wordArray).parallel();
```

只要在执行终端操作时流处于并行模式，所有的中间操作都将被并行化。

当流操作并行运行时，其意图是返回与串行执行相同的结果。重要的是操作必须是无状态的，并且可以任意顺序执行。

这里有一个你不能做的示例。假设你想统计字符串流中所有单词的数量：

```java
var shortWords = new int[12];

words.parallelStream().forEach(
    s -> {
        if (s.length() < 12) {
            shortWords[s.length()]++;
        }
    });

// 错误竞态条件！

IO.println(Arrays.toString(shortWords));
```

这是糟糕的代码。传递给 `forEach` 的函数在多个线程中并发运行，每个线程都在更新共享数组。正如你在第一卷第十章中所看到的，这是一个经典的竞态条件。如果你多次运行此程序，很可能每次运行都得到不同的计数序列——每个都是错误的。

你有责任确保传递给并行流操作的任何函数都是执行安全的。最好的方法是避免可变状态。在这个示例中，你可以安全地并行化。

当你按长度对字符串进行分组并计数时，计算如下：

```java
Map<Integer, Long> shortWordCounts =
    words.parallelStream()
        .filter(s -> s.length() < 12)
        .collect(groupingBy(String::length, counting()));
```

默认情况下，流源于有序集合（数组和列表）、范围、生成器和迭代器，以及通过调用 `Stream.sorted` 产生的流都是有序的。结果按照原始元素的顺序进行累积，并且是完全可预测的。如果你运行两次相同的操作，将得到完全相同的结果。

有序性并不排除高效的并行化。例如，在计算 `stream.map(fun)` 时，流可以被划分为 $n$ 个段，每个段都被并发处理。结果将按顺序重新组装。

当放弃顺序性要求时，某些操作可以更有效地进行并行化。通过调用 `Stream.unordered` 方法，你明确表示你对顺序不感兴趣。其中一个可以从中获益的操作是 `Stream.distinct()`。在有序流上，`distinct` 保留了所有相等元素中的第一个。这阻碍了并行化——处理某个段的线程在前面的段被处理之前，无法知道丢弃哪些元素。如果保留任何唯一元素都是可以的，那么所有段都可以并发处理（使用共享集合来跟踪重复）。

你也可以通过放弃顺序性来加速 `limit` 方法。如果你只是想要流中的任意 $n$ 个元素，且不在乎得到的是哪几个，可以调用：

```java
Stream<String> sample =
    words.parallelStream().unordered().limit(n);
```

正如第 1.9.2 节讨论，合并 map 是有开销的。因此，`Collectors.groupingConcurrent` 方法使用共享的并发 map。为了从并行中受益，map 值的顺序将与流的顺序不同。

```java
Map<Integer, List<String>> result =
    words.parallelStream()
        .collect(Collectors.groupingConcurrent(String::length)); // 值不是按流顺序收集的
```

当然，如果你使用一个独立于顺序的下游收集器，你将不在乎，例如：

```java
Map<Integer, Long> wordCounts =
    words.parallelStream()
        .collect(groupingConcurrent(String::length, counting()));
```

不要为了提高操作速度而将所有的流都转换为并行流。记住这些问题：

- 并行化有相当大的开销，只有在大数据集上才会有收益。
- 只有当底层数据源可以有效拆分为多个部分时，并行流才有意义。
- 并行流使用的线程池可能会被阻塞操作（如文件 I/O 或网络访问）耗尽。并行流在处理巨大的内存数据集合和计算密集型处理时效果最好。**提示：** 如果你处理一个大文件的行，并行化流可能会提高性能。`Files.lines` 方法使用内存映射文件（如果你简单地一次读取一行，那么你将必须在读取后半部分之前读取文件的前半部分，并行化将无法工作）。**注意：** 如果你在并行流中需要随机数，请从 `RandomGenerator.of()` 方法获取生成器。**注意：** 默认情况下，并行流使用由 `ForkJoinPool.commonPool()` 返回的全局 fork-join 池。如果你的操作不阻塞且不与其他任务共享该池，那是没问题的。有一个使用不同 fork-join 池的技巧：在该池的线程中执行并行流操作：

```java
ForkJoinPool customPool = . . .;

result = customPool.submit(() ->
    stream.parallel().map(. . .).collect(. . .)).get();
```

或者，异步地：

```java
CompletableFuture.supplyAsync(() ->
    stream.parallel().map(. . .).collect(. . .), customPool)
    .thenAccept(result -> . . .);
```

这仅适用于任意执行器。列表 1.10 中的示例程序演示了如何与并行流工作。

# 列表 1.10：`v01/parallel/ParallelStreams.java`

```java
package v01.parallel;

import static java.util.stream.Collectors.*;

import java.util.*;

import java.nio.file.*;

public class ParallelStreams {

    public static void main(String[] args) throws Exception {

        String contents = Files.readString(Path.of("gutenberg/aliceberg.txt"));

        List<String> wordList = List.of(contents.split("\\n"));

        // 极糟糕的代码

        var shortWords = new int[10];

        wordList.parallelStream().forEach(s -> {

            if (s.length() < 10) shortWords[s.length()]++;

        });

        System.out.println(Arrays.toString(shortWords));

        // 再次尝试 - 结果可能会不同（也是错误的）

        Arrays.fill(shortWords, 0);

        wordList.parallelStream().forEach(s -> {

            if (s.length() < 10) shortWords[s.length()]++;

        });

        System.out.println(Arrays.toString(shortWords));

        // 补救：分组并计数

        Map<Integer, Long> shortWordCounts = wordList.parallelStream()

            .filter(s -> s.length() < 10)

            .collect(groupingBy(String::length, counting()));

        System.out.println(shortWordCounts);

        // 下游顺序不是确定的

        Map<Integer, List<String>> result = wordList.parallelStream()

            .collect(groupingByConcurrent(String::length));

        System.out.println(result);

        Map<Integer, Long> wordCounts = words.parallelStream()

            .collect(groupingConcurrent(String::length, counting()));

        System.out.println(wordCounts);

    }

}
```

`in.transferTo(out);`

读取和写入方法都会阻塞，直到字节被实际读取或写入。这意味着，如果无法立即访问输入流（通常是因为网络连接繁忙），当前线程将会被阻塞。这使得其他线程在方法等待输入流再次可用时，有机会执行有用的工作。

`available` 方法允许你检查当前可用于读取的字节数。这意味着像下面这样的代码片段是不可能发生阻塞的：

```java



`int bytesAvailable = in.available();`

```
if (bytesAvailable > 0) {

    var data = new byte[bytesAvailable];

    in.read(data);

}
```

当你完成对输入/输出流的读取或写入后，通过调用`close`方法将其关闭。这可以释放数量有限的操作系统资源。如果应用程序打开了太多的输入/输出流而不关闭它们，系统资源可能会耗尽。关闭输出流还会刷新该输出流的缓冲区：任何临时存放在缓冲区以便作为较大的数据包交付的字节都会被发送出去。特别是，如果你不关闭文件，最后一个字节包可能永远不会被送达。你也可以使用`flush`方法手动刷新输出内容。

即使输入/输出流类提供了用于处理原始读写函数的具体方法，应用程序程序员也很少使用它们。你感兴趣的数据可能包含数字、字符串和对象，而不是原始字节。

与其处理字节，你可以使用许多构建在基本`InputStream`和`OutputStream`类之上的输入/输出类之一。

## java.io.InputStream 1.0

- `abstract int read()`
  读取一个字节的数据并返回所读取的字节；在输入流末尾返回 -1。

- `int read(byte[] b)`
  读取到字节数组中，并返回实际读取的字节数，或在输入流末尾返回 -1；此方法最多读取`b`长度的字节。

- `int readNBytes(byte[] b, int off, int len)`
  读取最多`len`个字节，如果可用且不阻塞（`read`），或者阻塞直到所有值都被读取完毕（`readNBytes`）。值从`off`开始处放置。返回实际读取的字节数。

- `byte[] readAllBytes()`
  产生一个可以从此流读取的所有字节的数组。

- `long transferTo(OutputStream out)`
  将此输入流传输所有字节到给定的输出流，并返回传输的字节数。两个流都不会关闭。

- `long skip(long n)`
  尝试在输入流中跳过`n`个字节，返回实际跳过的字节数（由于任何原因，可能少于`n`）。

- `long skipBytes(long n)`
  在输入流中跳过`n`个字节，返回实际跳过的字节数（如果遇到输入流末尾，可能少于`n`）。

- `int available()`
  返回可用的字节数，不阻塞（记住，阻塞意味着当前线程失去了 CPU 使用权）。

- `void close()`
  关闭输入流。

- `void mark(int readlimit)`
  在输入流的当前位置放置一个标记（并非所有流都支持此功能）。如果从输入流中读取了多于`readlimit`的字节，流允许遗忘该标记。

- `void reset()`
  返回到上一个标记。随后的`read`调用将重新读取这些字节。如果没有当前标记，则输入流不会被重置。

- `boolean markUpSupported()`
  如果输入流支持标记，则返回 true。

- `static InputInputStream nullInputStream()`
  返回一个没有字节的输入流。

## java.io.OutputStream 1.0

- `abstract void write(int n)`
  写入一个字节的数据。

- `void write(byte[] b)`

- `void write(byte[] b, int off, int len)`
  写入数组`b`中的所有字节，或从`off`开始的`len`个字节。

- `void close()`
  刷新并关闭输出流。

- `void flush()`
  刷新输出流——即，将任何缓冲中的数据发送到目标地。

- `static OutputStream nullOutputStream()`
  返回一个丢弃所有字节的输出流。

## 2.1.2. 完整的流动物园

与 C 不同（C 仅凭单一类型`FILE*`运行得很好），而 Java 拥有超过 60 个（！）类和接口，用于输入和输出。

图 2.1：输入和输出流层次结构

图 2.2：读取器和写入器层次结构

让我们根据使用方法对输入/输出动物园中的动物进行分类。处理字节和字符的类有独立的层级结构。正如你所看到的，`InputStream`和`OutputStream`类允许你读取单个字节和字节数组。这些类构成了 #ch01fig01 所示层次结构的基础。为了读取和写入字符串，你需要更强大的子类。例如，`DataInputStream`和`DataOutputStream`允许你以二进制格式读取和写入所有 Java 基本类型。最后，还有用于特殊任务的输入/输出流；例如，`ZipInputStream`和`ZipOutputStream`允许你读取和写入 ZIP 压缩格式的文件。

对于 Unicode 文本，可以使用抽象类`Reader`和`Writer`的子类（参见 #ch01fig02）。`Reader`和`Writer`类的基本方法与`InputStream`类似。还有四个额外的接口：`Closeable`、`Flushable`、`Reader`和`Appendable`。

注意：`Closeable`继承自`java.AutoCloseable`。因此，你可以对`Closeable`使用`try-with-resources`。前两个接口非常简单，包含：`Closeable`、`Flushable`、`Reader`和`Appendable`。

图 2.3：Closeable, Flushable, Reader

`Closeable`接口扩展了`java.AutoCloseable`。因此，你可以对`Closeable`使用`try-with-resources`。前两个接口非常简单，包含：`Closeable`、`Flushable`、`Reader`和`Appendable`。

图 2.3：Closeable, Flushable, Reader

`Readable`接口有一个方法：

```
int read(ByteBuffer)
```

`CharBuffer`有顺序访问和随机访问。它表示内存映射文件。（参见 2.4 节。）

`Appendable`接口具有追加字符和序列的方法：

- `append(char c)`
- `append(CharSequence)`

`CharSequence`接口描述序列的基本属性。由`String`、`CharBuffer`和`StringBuffer`实现。

在输出类中，只有`Writer`实现了`Appendable`。

## java.io.Closeable 5.0

- `void close()`
  关闭`Closeable`。此方法可能会抛出`IOException`。

## java.io.Flushable 5.0

- `void flush()`
  刷新`Flushable`。

## java.lang.Readable 5.0

- `int read(ByteBuffer)`
  尝试向`cb`读取尽可能多的值。返回读取的值数量，如果没有更多可用值，则返回 -1。

## java.lang.Appendable 5.0

- `append(char c)`
- `append(CharSequence cs)`
  将给定的代码单元或序列中的所有代码单元追加到`Appendable`；返回自身。

## java.lang.CharSequence 1.4

- `char charAt(int index)`
  返回索引处的代码单元。
- `int length()`
  返回序列中代码单元的数量。
- `CharSequence subSequence(int startIndex, int endIndex)`
  产生一个由从`startIndex`到`endIndex - 1`的代码单元组成的`CharSequence`。

- `String toString()`
  返回一个由序列代码单元组成的字符串。

### 2.1.3. 输入输入/流过滤器

`FileInputStream`和`File`提供了到磁盘文件的输入输出流。你需要将文件名或文件的完整路径传递给构造函数。例如，

```
var fin = new FileInputStream("employee.dat");
```

查找名为`employee.dat`的文件。

> 注意：相对路径从工作目录开始。你可以通过`System.getProperty("user.dir")`获取此目录。它在虚拟机启动时设置，之后无法更改。如果你从命令行启动程序，工作目录就是终端中的当前目录。在 IDE 中，你可以在运行配置中设置工作目录。

> 警告：由于反斜字符是 Java 字符串中的转义字符，请确保在 Windows 风格的路径名中使用`\`（例如`C:\Windows\win.ini`）。在 Windows 上，你也可以使用正斜杠（`C:/Windows/win.ini`），因为大多数 Windows 文件处理系统调用会将正斜杠解释为文件分隔符。但不建议这样做——相反，对于可移植程序，请使用程序运行平台的文件分隔符。它可以通过常量字符串`java.io.File.separator`获取。

与抽象`InputStream`和`OutputStream`类一样，这些类仅支持字节层级的读取和写入。也就是说，我们只能从`fin`对象读取字节和字节数组。

```java
byte b = (byte) fin.read();
```

正如你将在下一节中看到的，如果我们只有一个`DataInputStream`，我们就可以读取数值类型：

```java
DataInputStream din = . . ;
double x = din.readDouble();
```

但正如`FileInputStream`没有读取数值类型的方法一样，`DataInputStream`也没有从文件中获取数据的方法。

Java 使用了一种巧妙的机制来分离两种职责。某些输入流（例如`FileInputStream`和通过`URL`类的`openInputStream`方法返回的输入流）从文件和其他特殊位置检索字节。其他输入流（例如`DataInputStream`）可以将字节组装成更有用的数据类型。Java 程序员必须将两者结合。例如，为了能够从文件中读取数字，首先创建一个`FileInputStream`，并将其传递给`DataInputStream`的构造函数。

```java
var fin = new FileInputStream("employee.dat");
var din = new DataInputStream(fin);
double x = din.readDouble();
```

如果你再次查看 #ch01fig01，你可以看到`FilterInputStream`和`FilterOutputStream`类。这些类的子类用于为处理字节的输入/输出流添加功能。

你可以通过嵌套过滤器来添加多个功能。例如，默认的输入流是没有缓冲的。这意味着每次调用`read`都会请求操作系统分发另一个字节。请求数据块并将其存储在缓冲区中会更高效。如果你需要缓冲功能以及针对文件的数据输入方法，请使用以下构造函数序列：

```java
var din = new DataInputStream(
    new BufferedInputStream(
    new FileInputStream("employee.dat")));
```

注意，我们将`DataInputStream`放在构造函数链的最后面，因为我们想使用`DataInputStream`的方法，并且我们希望这些方法使用缓冲读取方法。

有时，当你将输入流链在一起时，需要跟踪中间的输入流。例如，在读取输入时，你通常需要查看下一个字节，以确定它是否是你预期的值。Java 提供了`PushbackInputStream`用于此目的。

```java
var pbin = new PushbackInputStream(
    new BufferedInputStream(
    new FileInputStream("employee.dat")));
```

现在你可以推测性地读取下一个字节

```java
int b = pbin.read();
```

如果它不是你想要的，就将其推回。

```java
if (b != '<') pbin.unread(b);
```

> 注意：`unread`方法实际上不会更改流读取字节的源。未读取的字节被存储在缓冲区中，并由下一次`read`操作返回。默认情况下，缓冲区长度为 1，但你可以在`PushbackInputStream`构造函数中指定更长的缓冲区。

读取和推回是适用于推回输入流的唯一方法。如果你想向前查看并读取数字，你需要一个推回输入流引用和一个数据输入流引用。

```java
var pbin = new PushbackInputStream(
    new BufferedInputStream(
    new FileInputStream("employee.dat")));
var din = new DataInputStream(pbin);
```

当然，在其他编程语言的输入/输出库中，缓冲和前瞻等便利功能是自动处理的——因此在 Java 中诉助于组合流过滤器有点麻烦。

然而，混合和匹配过滤器类以构建有用的输入输出流序列的能力赋予了你极大的活性。例如，你可以使用以下输入流序列从压缩的 ZIP 文件中读取数字（参见 #ch01fig04）：

```java
var zin = new ZipInputStream(new
FileInputStream("employee.zip"));
var din = new DataInputStream(zin);
```

图 2.4：一组过滤后的输入流序列

（关于 Java 处理 ZIP 文件的更多信息，请参见第 2.2.3 节。）

| java.io.FileInputStream | 1.0 |
| :--- | :--- |
| - `FileInputStream(String name)` | |
| - `FileInputStream(File file)` | |
| 使用`name`字符串指定的路径名或旧`File`类对象创建新的文件输入流 | |

| java.io.FileOutputStream | 1.0 |
| :--- | :--- |
| - `FileOutputStream(String name)` | |
| - `FileOutputStream(String name, boolean append)` | |
| - `FileOutputStream(File file)` | |
| - `FileOutputStream(File file, boolean append)` | |
| 由`name`字符串或文件对象指定新的文件输出流。（`File`类在在本章末尾描述。）如果`append`参数为`true`，则同名的现有文件不会被删除，数据将添加到文件末尾。否则，此方法将删除任何同名的现有文件。 |

## java.io.BufferedInputStream 1.0

- `BufferedInputStream(InputStream)` 创建一个缓冲输入流。缓冲输入流从流中读取字节，而不会每次都导致设备访问。当缓冲区为空时，会将一个新数据块读入缓冲区。

## java.io.BufferedOutputStream 1.0

- `BufferedOutputStream(OutputStream out)` 创建一个缓冲输出流。缓冲输出流收集待写入的字节，而不会每次都导致设备访问。当缓冲区满或当流被刷新时，数据将被写入。

## java.io.PushbackInputStream 1.0

- `PushbackInputStream(InputStream)`
- `PushbackInputStream(InputStream in, int size)` 构建一个具有单字节前瞻或指定大小推回缓冲区的输入流。
- `void unread(int b)` 推回一个字节，

### 2.1.4 文本输入与输出

保存文本时，你在二进制和文本之间选择。从 18 开始，这些类默认使用 UTF-8。在 Java 18 之前，如果你需要支持某种编码，请在构造函数中指定编码，例如：

```java
var in = new InputStreamReader(new FileInputStream("data.txt"), StandardCharsets.UTF_8);
```

### 2.1.5 如何读取文本

你可以像这样将短文本文件读取为字符串：

```java
String content = Files.readString(path);
```

但如果你想要文件作为行序列，调用

```java
List<String> lines = Files.readLines(path);
```

如果文件很大，以`Stream<String>`延迟处理行：

```java
try (Stream<String> lines = Files.lines(path)) {

  }
```

注意：如果在流获取行时发生`IOException`，该异常将被封装为`UncheckedIOException`并抛出流操作。这种手段是必要的，因为流操作没有声明抛出异常。

处理任意文本简单的方法是`Scanner`类。以下代码处理文件中的所有行：

```java
try (var in = new Scanner(path)) {

    while (in.hasNextLine()) {

        String line = in.nextLine();

        // 处理行

    }

}
```




你还可以使用 `Scanner` 读取标记——即由分隔符分隔的字符串。默认分隔符是空白字符。你可以将分隔符更改为任何正则表达式。例如，这里是如何配置 `Scanner` 以使用任何非 Unicode 字母作为分隔符：

```java
Scanner in = ...;

in.useDelimiter("\\PL+");
```

此 `Scanner` 现在接受仅包含 Unicode 字母的标记。

调用 `next()` 方法产生下一个标记：

```java
while (in.hasNext()) {
    String word = in.next();
}
```

或者，你可以获取所有标记的流：

```java
Stream<String> words = in.tokens();
```

**注意：** 在旧代码中，你可能会发现通过重复调用 `BufferedReader` 的 `readLine()` 方法来读取行的代码。如今，没有理由再这样做。

`nextInt()` 和 `nextDouble()` 方法产生输入中的下一个整数或浮点数。先调用 `hasNextInt()` 或 `hasNextDouble()` 以确保下一个标记是数字。

**注意：** `next()`、`nextInt()` 和 `nextDouble()` 方法只消耗空白字符和一个标记。末尾的空白字符会留在输入中。如果你也调用了 `nextLine()`，请记住这一点。如果你的输入是：

```text
29.95
Blackwell Toaster
```

并且调用了：

```java
double price = in.nextDouble();
double description = in.nextLine(); // ERROR
```

那么 `description` 将是空的！`nextLine()` 调用只读取了数字后面的换行符。

只需再次添加 `nextLine()` 调用来消耗末尾的空白字符。

### 2.1.6. 如何输出文本

对于文本输出，请使用 `PrintWriter`。该类具有以文本格式打印字符串和数字的方法。要打印到文件，可以使用文件名构造 `PrintWriter`：

```java
var out = new PrintWriter("employee.txt");
```

> **警告：** 奇怪的是，你不能从 `Path` 构造 `PrintWriter`。

注意：在 Java 18 之前，请确保将字符编码作为第二个参数：

```java
var out = new PrintWriter(
    "employee.txt",
    StandardCharsets.UTF_8
);
```

否则，将使用平台编码，导致你的程序行为取决于宿主机操作系统的配置。

要向写入器 `out` 写入，请使用 `print()` 和 `println()` 方法。你可以使用这些方法打印数字（`int`、`short`、`long`、`float`、`double`）、字符、布尔值、字符串和对象。

例如，考虑这段代码：

```java
String name = "Harry Hacker";
double salary = 75000;

out.print(name);
out.print(' ');
out.println(salary);
```

向写入器 `out` 写入字符：

```text
Harry Hacker 75000.0
```

字符随后被转换为字节并进入 `employee.txt` 文件。

`println()` 方法将行修正为目标系统的行结束符（Windows 上为 `"\r\n"`，UNIX 上为 `"\n"`）。这是通过调用 `System.getProperty("line.separator")` 获取的字符串。

如果写入器设置为自动刷新模式，则每当调用 `println()` 时，缓冲区中的所有字符都会发送到目的地（`PrintWriter` 总是缓冲的）。默认情况下，未启用自动刷新。你可以通过 `PrintWriter(Writer writer, boolean autoFlush)` 构造函数启用或禁用自动刷新：

```java
var out = new PrintWriter(
    new OutputStream(
        new FileOutputStream("employee.txt")
    ),
    true
); // autoflush
```

`print()` 方法不会抛出异常。你可以调用 `checkError()` 方法来查看输出流是否出现问题。

- **注意：** Java 资深人士可能会好奇 `PrintStream` 类和 `System.out` 发生了什么。在 Java 1.0 中，`PrintStream` 简单地通过丢弃高字节将所有 Unicode 字符截断为 ASCII 字符（当时，Unicode 仍然是 16 位编码）。显然，这不是一种整洁或可移植的方法，并在 Java 1.1 引入读取器和写入器后得到了修复。为了与现有代码兼容，`System.in`、`System.out` 和 `System.err` 仍然是输入输出流，而不是读取器和写入器。但现在 `PrintStream` 类内部以与 `PrintWriter` 相同的方式将 Unicode 字符转换为字符编码。使用 `print()` 和 `println()` 方法时，`PrintStream` 类型的对象与写入器完全相同；与写入器不同的是，它们允许你通过 `write(int)` 和 `write(byte[])` 方法输出原始字节。

| `java.io.PrintWriter` 1.1 |
| :--- |
| `PrintWriter(OutputStream out)` |
| `PrintWriter(OutputStream out, boolean autoFlush)` |
| `PrintWriter(Writer writer)` |
| `PrintWriter(Writer writer, boolean autoFlush)` |

创建一个新的写入到给定输出流或写入器的 `PrintWriter`。如果 `autoFlush` 指定为 `true`，则 `println()` 和 `printf()` 将刷新输出。

- `PrintWriter(String filename, String encoding)`
- `PrintWriter(File file, String encoding)`：创建一个新的写入到给定文件并使用给定字符编码的 `PrintWriter`。
- `void print(Object obj)`：通过打印 `toString()` 产生的字符串来打印对象。
- `void print(String s)`：打印包含 Unicode 编码单元的字符串。
- `void println(String s)`：打印字符串后跟一个行终止符。如果输出流处于自动刷新模式，则刷新输出流。
- `void print(char[] s)`：打印给定数组中的所有 Unicode 编码单元。
- `void print(char c)`：打印一个 Unicode 编码单元。
- `void print(int i)`
- `void print(long f)`
- `void print(float f)`
- `void print(double d)`
- `void print(boolean b)`：以文本格式打印给定值。
- `void print(String format, Object... args)`：按格式字符串指定打印给定值。参见第一卷第 3 章。
- `boolean checkError()`：如果发生格式化或输出错误，则返回 `true`。一旦输出流遇到错误，它就会被污染，所有 `checkError()` 调用都返回 `true`。

### 2.1.7. 以文本格式保存对象

在本节中，我们将讨论一个示例程序，该程序在文本文件中存储 `Employee` 记录数组。每个记录存储在单独的一行中。实例字段之间用分隔符分开。以下是一组示例记录：

- Harry Hacker 75000.0
- Blackwell Toaster 29.95

```java
// 将所有记录读取到一个新数组
try (var in = new Scanner(new FileInputStream("employee.dat"))) {
    Employee[] newStaff = readData(in);
}
```

```java
// 打印新读取的员工记录
for (Employee e : newStaff) {
    out.println(e);
}
```

```java
void writeData(Employee[] employees, PrintWriter out) throws IOException {
    // 写入员工数量
    out.println(employees.length);

    for (Employee e : employees) {
        writeEmployee(out, e);
    }
}
```

```java
Employee[] readData(Scanner in) {
    // 获取数组大小
    int n = in.nextInt();
    in.nextLine(); // 消耗换行符

    var employees = new Employee[n];

    for (int i = 0; i < n; i++) {
        employees[i] = readEmployee(in);
    }

    return employees;
}
```

```java
void getHireDay(PrintWriter out, Employee e) {
    out.println(
        e.getName() + "|" + e.getSalary() + "|" + e.getHireDay()
    );
}
```

```java
Employee readEmployee(Scanner in) {
    String line = in.nextLine();
    String[] tokens = line.split("\\||");

    double salary = Double.parseDouble(tokens[1]);
    LocalDate hiredate = LocalDate.parse(tokens[2]);

    int year = hiredate.getYear();
    int month = hiredate.getMonthValue();
    int day = hiredate.getDayOfMonth();

    return new Employee(name, salary, year, month, day);
}
```

### 2.1.8. 字符编码

每个 Unicode“编码点”（code point）都是一个 21 位的整数。有不同的字符编码——将这 21 位的数字封装成字节的方法。

最常见的编码是 UTF-8，它将每个 Unicode 编码点编码为一到四个字节的序列。表 2.1 详细显示了如何使用位 $a_{20}a_{19} \dots a_{1}a_{0}$ 编码一个 21 位的编码点。UTF-8 的优势在于，传统的 ASCII 字符集（包含英语中使用的所有字符）每个只占用一个字节。

### 表 2.1：UTF-8 编码

| 字符范围 | 编码 |
|---|---|
| 头部 14 位为零 | $a_{6}a_{5}a_{4}a_{3}a_{2}a_{1}a_{0}$ |
| 前十位为零 | $110a_{10}a_{9}a_{8}a_{7}a_{6}$ $10a_{5}a_{4}a_{3}a_{2}a_{1}a_{0}$ |
| 前六位为零 | $1110a_{15}a_{14}a_{13}a_{12}$ $10a_{11}a_{10}a_{9}a_{8}a_{7}a_{6}$ $10a_{5}a_{4}a_{3}a_{2}a_{1}a_{0}$ |
| 剩余部分 | $11111a_{20}a_{19}a_{18}$ $10a_{17}a_{16}a_{15}a_{14}a_{13}a_{12}$ $10a_{11}a_{10}a_{9}a_{8}a_{7}a_{6}$ $10a_{5}a_{4}a_{3}a_{2}a_{1}a_{0}$ |

### 表 2.2：UTF-16 编码

| 字符范围 | 编码 |
|---|---|
| 头部六位为零 | $a_{15}a_{14}a_{13}a_{12}a_{11}a_{10}a_{9}a_{8}$ $a_{7}a_{6}a_{5}a_{4}a_{3}a_{2}a_{1}a_{0}$ |
| 剩余部分 | $11011b_{19}b_{18}$ $b_{17}b_{16}a_{15}a_{14}a_{13}a_{12}a_{11}a_{10}$ $110111a_{9}a_{8}$ $a_{7}a_{6}a_{5}a_{4}a_{3}a_{2}a_{1}a_{0}$，其中 $b_{19}b_{18}b_{17}b_{16} = a_{20}a_{19}a_{18}a_{17} - 1$ |

另一种常见的编码是 UTF-16，它将每个 Unicode 编码点编码为一个或两个 16 位的值（见表 2.2）。这是 Java 字符串中使用的编码。实际上，UTF-16 有两种形式，称为“大端序”（big-endian）和“小端序”（little-endian）。考虑 16 位值 `0x2122`。在大端格式中，高位字节在前：`0x21` 后是 `0x22`。在小端格式中，情况相反：`0x22 0x21`。为了指示是哪一种，可以使用 BOM（字节序标记）。

（注：原文后半部分似乎存在乱码或重复错误，译文已根据语境进行了良性处理，保留了技术术语逻辑）

那种格式。此类解析器通常一次读取一个字符。在需要实现此类解析器的罕见情况下，请使用 `BufferedReader` 来提高效率。持续调用它的 `read()` 方法，它会返回一个 `char` 值或在输入结束时返回 `-1`。读取器产生 UTF-16 代码单元。如果你对代码点（code points）感兴趣，你需要处理 UTF-16 编码：

```java
int ch = reader.read();

if (ch != -1) {
    int codePoint;

    if (Character.isHighSurrogate((char) ch)) {
        int ch2 = reader.read();

        if (Character.isLowSurrogate((char) ch2)) {
            codePoint = Character.toCodePoint((char) ch, (char) ch2);
        } else {
            throw new MalformedInputException(2);
        }
    } else {
        codePoint = ch;
    }
}
```

`Character` 类包含了一些方法用于判断特定的代码点是否具有特定的属性。例如，`Character.isLetter(codePoint)` 如果 `codePoint` 是某种语言中的字母，则返回 `true`。这里是其他一些分类方法：

- `isUpperCase()`
- `isLowerCase()`
- `isDigit()`
- `isSpaceChar()`
- `isEmoji()`

这些方法使用了 Unicode 标准规则。其他的引用了 Java 语言规则：

- `isJavaIdentifierStart()`
- `isJavaIdentifierPart()`
- `isWhitespace()`

在分析代码点之后，你通常需要将它们存储在字符串中，将其转换回 UTF-16。`StringBuilder` 类的 `appendCodePoint()` 方法将代码点转换为一个两个 `char` 值，并将它们附加到构建器上。

## 2.2. 读取和写入二进制数据

文本格式便于测试和调试，因为它是人类可读的，但它不如以二进制格式传输数据那样高效。在接下来的章节中，你将学习如何对二进制数据进行输入和输出。

### 2.2.1. DataInput 和 DataOutput 接口

`DataOutput` 接口定义了以下方法用于以二进制格式写入数字、字符、布尔值或字符串：

```text
writeChars  writeFloat
writeByte   writeDouble
writeInt    writeChar
writeShort  writeBoolean
writeLong   writeUTF
```




例如，`writeInt` 无论数字位数有多少，始终将整数作为 4 字节二进制量写入，而 `writeDouble` 始终将双精度浮点数作为 8 字节二进制量写入。生成的输出不是人类可读的，但它为给定类型的每个值使用相同的空间，读取它将比解析文本更快。

> 在内存中存储整数和浮点数有两种不同的方法，取决于你所使用的处理器。假设你正在处理一个 4 字节的 `int`，例如十进制数字 1234 或十六进制的 4D2（1234 = 4 × 256 + 13 × 16 + 2）。该值可以以这种方式存储：内存中四个字节的第一个字节持有该值的最高有效字节（MSB）：00 00 04 D2。这就是所谓的大端序（big-endian）方法。或者，我们可以从最低有效字节（LSB）开始：D2 04 00 00。这理所当然地被称为小端序（little-endian）方法。例如，SPARC 使用大端序；Intel 处理器使用小端序。这可能会导致问题。当从 C 或 C++ 文件保存文件时，数据完全按照处理器存储的方式进行保存。这使得即使是最简单的数据文件从一个平台移动到另一个平台也具有挑战性。在 Java 中，所有值都以大端序方式写入，无论处理器如何。这使得 Java 数据文件独立平台。

`writeUTF` 方法使用修改版的 8 位 Unicode 转换格式写入字符串。它不是简单地使用标准的 UTF-8 编码，而是首先将 Unicode 代码单元序列表示为 UTF-16，然后使用 UTF-8 规则对结果进行编码。这种修改后的编码对于代码高于 0xFFFF 的字符是与不同的。它被用于与在 Unicode 增长到 16 位之前构建的虚拟机保持向后兼容。

由于没有其他人使用这种 UTF-8 的修改版本，你应该只使用 `writeUTF` 方法来编写用于 Java 虚拟机的字符串——例如，在生成字节码的程序中。对于其他用途请使用 `writeChars` 方法。

要读回数据，请使用 `DataInput` 接口定义的以下方法：

```text
readInt    readDouble
readShort  readChar
readLong   readBoolean
readFloat  readUTF
```

`DataInputStream` 类实现了 `DataInput` 接口。要从文件读取二进制数据，请结合 `DataInputStream` 与字节源（如 `FileInputStream`）：

```java
var in = new DataInputStream(
    new FileInputStream("employee.dat"));
```

同样，要写入二进制数据，请使用实现 `DataOutput` 接口的 `DataOutputStream` 类：

```java
var out = new DataOutputStream(new FileOutputStream("employee.dat"));
```

### `java.io.DataInput` 1.0

- `boolean readBoolean()`
- `byte readByte()`
- `char readChar()`
- `double readDouble()`
- `float readFloat()`
- `int readInt()`
- `long readShort()`
- `short readShort()`  
  读取给定类型的值
- `void readFully(byte[] b)`  
  读取字节到数组中直到读完所有字节。
- `void readFully(byte[] b, int off, int len)`  
  放置 `len` 个字节
- `String readUTF()`  
  读取修改后的 UTF 格式的字符串
- `int skipBytes(int n)`  
  跳过 `n` 个字节

### `java.io.DataOutput` 1.0

- `boolean writeBoolean()`
- `byte writeByte()`
- `char writeChar()`
- `double writeDouble()`
- `float writeFloat()`
- `int writeInt()`
- `long writeLong()`
- `short writeShort()`
- `void writeChars(char[] s)`  
  写入字符数组
- `void writeUTF(String str)`  
  写入修改 UTF 格式的字符串

## 2.2.2. 随机访问文件

`RandomAccessFile` 让你在文件的任何位置读取或写入。磁盘文件是随机访问的，但与网络通信的输入输出流不是。你可以打开随机访问文件，通过构造函数的第二个参数指定字符串 `"r"`（只读）或 `"rw"`（读写）来实现。

```java
var in = new RandomAccessFile("employee.dat", "r");

var inOut = new RandomAccessFile("employee.dat", "rw");
```

还有 `"rwd"` 和 `"rws"` 模式可以将数据的元数据刷新到磁盘。这较慢，但可以防止程序或计算机崩溃时丢失数据。

随机访问文件有一个文件指针，指示下一个要读取或写入的字节。`seek` 方法用于将文件指针设置为文件的任意位置，用 `long` 值指定。`getPointer` 方法返回文件指针当前的位置。

`RandomAccessFile` 类实现了 `DataInput` 和 `DataOutput` 接口。要从随机访问文件读写，可以使用我们在上一节讨论过的 `readInt/writeInt` 和 `readChar/writeChar` 方法。

让我们通过一个在随机访问文件中存储员工记录的示例。每个记录的大小相同。这使得读取任意记录变得容易。假设你想将文件指针指向第三条记录。只需将文件指针设置回记录的开头即可。

```java
long n = 3;

in.seek((n - 1) * RECORD_SIZE);

var e = new Employee();

e.writeData(in);
```

如果你想修改记录并将其写回相同的位置，记得将文件指针设置回记录的开头：

```java
in.seek((n - 1) * RECORD_SIZE);

e.writeData(out);
```

要确定文件的总字节数，使用 `length` 方法。总记录数是长度除以每个记录的大小。

```java
long nbytes = in.length(); // 字节数

int nrecords = (int) (nbytes / RECORD_SIZE);
```

整数和浮点值在二进制格式下有固定大小，但对于字符串我们需要付出更多努力。我们提供了两个辅助方法，用于写入和读取固定大小的字符串。

`writeFixedString` 从字符串开始写入指定数量的代码单元。如果代码单元数量不足，该方法将使用零值对字符串进行填充。

```java
public static void writeFixedString(String s, int size, DataOutput out)
    throws IOException {
    for (int i = 0; i < size; i++) {
        char ch = 0;
        if (i < s.length()) ch = s.charAt(i);
        out.write(ch);
    }
}
```

`readFixedString` 方法从输入流中读取字符，直到消耗了 `size` 个代码单元，或者遇到值为零的字符。然后，它会跳过输入字段中剩余的零值。为了提高效率，该方法使用 `StringBuilder` 类来读取字符串。

```java
public static String readFixedString(int size, DataInput in)
    throws IOException {
    var b = new StringBuilder(size);
    int i = 0;
    var done = false;
    while (!done && i < size) {
        char ch = in.readChar();
        i++;
        if (ch == 0) done = true;
        else b.append(ch);
    }
    in.skipBytes(2 * (size - i));
    return b.toString();
}
```

我们将 `writeFixedString` 和 `readFixedString` 方法放在了 `DataIO` 辅助类中。

要写入固定大小的记录，只需以二进制格式写入所有字段。

```java
DataIO.writeFixedString(e.getName(), Employee.NAME_SIZE, out);

out.writeDouble(e.getSalary());

LocalDate hireDay = e.getHireDay();

out.writeInt(hireDay.getYear());

out.writeInt(hireDay.getMonthValue());

out.writeInt(hireDay.getDayOfMonth());
```

读回数据同样简单。

```java
String name = DataIO.readFixedString(Employee.NAME_SIZE, in);

double salary = in.readDouble();

int y = in.readInt();

int m = in.readInt();

int d = in.readInt();
```

让我们计算每条记录的大小。我们将为字符串使用 40 个字符。因此，每条记录将包含 100 字节：

- 40 个字符 = 80 字节的名字
- 1 个 `double` = 8 字节的工资
- 3 个 `int` = 12 字节的

列表 2.2 显示的程序将三条记录写入数据文件，然后按反序从文件中读取。要高效地实现此操作需要随机访问——我们需要获取最后一条记录。

# 列表 2.2 `vch02/randomAccess/RandomAccessDemo.java`

```java
package vch02.randomAccess;

import module java.base;

import com.horstmann.corejava.*;

public class RandomAccessDemo {

    final int NAME_SIZE = 40;

    final int RECORD_SIZE = 2 * NAME_SIZE + 8 + 4 + 4;

    void main() throws Exception {

        Employee[] staff = new Employee[3];

        staff[0] = new Employee("Carl Cracker", 75000, 1987, 12, 15);

        staff[1] = new Employee("Harry Hacker", 50000, 1989, 10, 1);

        staff[2] = new Employee("Tony Tester", 40000, 1990, 3, 15);
```

```java
try (var out = new DataOutputStream(new FileOutputStream("employee.dat"))) {

    // 将所有员工记录保存到文件 employee.dat

    for (Employee e : staff) {

        writeData(out, e);

    }

} catch (IOException e) {

    e.printStackTrace();

} catch (Exception e) {

    e.printStackTrace();

}

try (var in = new RandomAccessFile("employee.dat", "r")) {

    // 将所有记录检索到一个新数组

    // 计算数组大小

    int n = (int) (in.length() / RECORD_SIZE);

    var newStaff = new Employee[n];

    // 按反序读取员工

    for (int i = 0; i < n; i++) {

        in.seek((n - 1) * RECORD_SIZE);

        newStaff[i] = readData(in);

    }

    // 新读取的员工记录

    for (Employee e : newStaff) {

        IO.println(e);

    }

} catch (IOException e) {

    e.printStackTrace();

}

/**

 * 将员工数据写入数据输出流。

 * @param out 数据输出

 * @param e 员工

 */

void writeData(DataOutputStream out, Employee e) throws IOException {

    DataIO.writeFixedString(e.getName(), NAME_SIZE, out);

    out.writeDouble(e.getSalary());

    LocalDate hireday = e.getHireDay();

    out.writeInt(hireday.getYear());

    out.writeInt(hireday.getMonthValue());

    out.writeInt(hireday.getDayOfMonth());

}

/**

 * 从数据输入读取员工数据。

 * @param in 数据输入

 * @return 员工

 */

Employee readData(DataInput in) {

    String name = DataIO.readFixedString(NAME_SIZE, in);

    double salary = in.readDouble();

    int y = in.readInt();

    int m = in.readInt();

    int d = in.readInt();

    return new Employee(name, salary, y, m, d);

}
```

### `java.util.zip.ZipEntry` 1.1

- `ZipEntry(String name)`  
  创建一个给定名称的 ZIP 条目。
- `long getCrc()`  
  返回此 `ZipEntry` 的 CRC32 校验和值。
- `String getName()`  
  返回此条目的名称。
- `long getSize()`  
  返回此条目的未压缩前的大小，如果未知未压缩的大小，则返回 -1。
- `boolean isDirectory()`  
  如果此条目是一个目录，则返回 true。
- `void setMethod(int method)`  
  将条目的压缩方法设置为 DEFLATED 或 STORED。
- `void setSize(long size)`  
  设置此条目的大小。只有在压缩方法为 STORED 时才需要设置。
- `void setCrc(long crc)`  
  设置此条目的 CRC32 校验和。使用 `CRC32` 类计算此校验和。只有在压缩方法为 STORED 时才需要设置。

## 2.3. 文件操作

你已经学习了如何从文件中读取和写入数据。然而，文件管理不仅仅是读和写。`Path` 接口和 `Files` 类封装了在用户机器上处理文件系统所需的功能。例如，`Files` 类可以用于删除或重命名文件，或者查找文件何时被修改过。换句话说，输入/输出流类关注文件的内容，而我们讨论的类关注的是文件在磁盘上的存储。

`Path` 接口和 `Files` 类比追溯到 JDK 1.0 的 `File` 类要方便得多。除非是为了与遗留代码交互，否则你不应该使用 `File` 类。

### 2.3.1. 路径（Paths）

`Path` 是目录名称的序列，后面可选跟一个文件名。路径的第一个组件可以是根组件，例如 `/` 或 `C:\`。允许的根组件取决于文件系统。以根组件开头的路径是绝对路径。否则，它是相对路径。例如，我们构建了一个绝对路径和一个相对路径。对于绝对路径，我们假设使用一个类 Unix 文件系统。

```java
Path absolute = Path.of("/home", "harry");

Path relative = Path.of("myprog", "conf", "user.properties");
```

静态 `Path` 方法接收一个或多个字符串，并将其与默认文件系统的路径分隔符连接（类 Unix 文件系统为 `/`，Windows 为 `\`）。然后它会解析结果，如果结果在给定的文件系统中不是有效路径，则抛出 `InvalidPath`。其结果是一个 `Path` 对象。

该方法可以获取一个包含多个组件的单个字符串。例如，你可以像这样从配置文件读取路径：

```java
String baseDir = props.getProperty("base.dir");

// 可能是字符串 /opt/myprog 或 c:\Program\myprog

Path basePath = Path.of(baseDir); // baseDir 包含分隔符是允许的
```



> 注意：路径并不非要对应一个实际存在的文件。它仅仅是一个抽象的名称序列。正如你将在下一节中看到的，当你想要创建一个文件时，首先创建一个路径，然后调用方法来创建对应的文件。

组合或解析路径是非常常见的。调用 `p.resolve(q)` 根据以下规则返回一个路径：

- 如果 `q` 是绝对路径，则结果为 `q`。
- 如果 `q` 没有根路径，则结果通过连接 `p` 和 `q` 获得。
- 否则，结果取决于文件系统的规则。

例如，假设你的应用程序需要相对于上一个示例中从配置文件读取的给定基目录查找其工作目录。

```java
Path workRelative = Path.of("work");

Path workPath = basePath.resolve(workRelative);
```

`resolve` 方法有一个快捷方法，接受字符串而不是 `Path` 对象：

```java
Path workPath = basePath.resolve("work");
```

> 注意：`resolve` 方法不会简化结果。例如，`Path.of("/usr/bin").resolve("../local")` 是路径 `/usr/bin/../local`。

有一个便利方法 `resolveSibling` 可以相对于路径的父目录进行解析。例如，如果 `workPath` 是 `/opt/myapp/work`，调用：

```java
Path tempPath = workPath.resolveSibling("temp");
```

将创建 `/opt/myapp/temp`。

`resolve` 的相反操作是 `relativize`。调用 `p.relativize(r)` 会产生路径 `q`，当 `q` 与 `p` 解析时，会产生 `r`。例如，相对于 `/home/fred/input.txt` 对 `/home/harry` 进行相对化得到 `../fred/input.txt`。在这里，我们假设 `..` 表示文件系统中的父目录。

`normalize` 方法移除任何冗余的 `.` 和 `..` 组件（或文件系统认为冗余的任何组件）。例如，规范化路径 `/home/harry/../fred/./input.txt` 得到 `/home/fred/input.txt`。

`toAbsolutePath` 方法产生给定路径的绝对路径，从根组件开始，例如 `/home/fred/input.txt` 或 `c:\Users\fred\input.txt`。

`Path` 接口有很多有用的方法来分解路径。代码显示了一些最有用的：

```java
Path p = Path.of("/home", "fred", "myprog.properties");

Path parent = p.getParent(); // 路径 /home/fred

Path file = p.getFileName(); // 路径 myprog.properties

Path root = p.getRoot(); // 路径 /home
```

> 注意：偶尔你可能需要与使用输入/输出流或读取器/写入器的 API 交互：

```java
var in = new Scanner(Path.of("/home/fred/input.txt"));
```

以下方法允许你与使用输入/输出流或读取器/写入器的 API 交互：

```java
InputStream in = Files.newInputStream(path);

OutputStream out = Files.newOutputStream(path);

Reader in = Files.newBufferedReader(path);
```

### 2.3.2. 读取和写入文件

`Files` 类可以快速处理常用操作。例如，你可以轻松地将文件的内容读取为字节数组、字符串、行列表或行流：

```java
byte[] bytes = Files.readAllBytes(path);

String content = Files.readString(path);

List<String> lines = Files.readAllLines(path);

Stream<String> lineStream = Files.lines(path);
```

相反，对于写入：

```java
Files.write(path, bytes);

Files.writeString(path, content);

Files.write(path, lines);
```

要追加到给定文件，使用：

```java
Files.write(path, content, StandardOpenOption.APPEND);
```

调用：

```java
long pos = Files.match(path1, path2);
```

产生文件内容出现不同的第一个字节的位置。

要获取文件的 MIME 类型（例如 `"text/html"` 或 `"image/png"`），调用：

```java
String mimeType = Files.probeContentType(path);
```

实际行为取决于 Java 的实现。每个实现拥有一个 `FileDetector` 实例集合并按不指定的顺序进行尝试。每个检测器可能会检查文件扩展名、操作系统特定的元数据或内容的开头几个字节。

```java
Writer out = Files.newBufferedWriter(path);
```

这些方便的方法可以让你免于处理 `FileInputStream`、`FileOutputStream`、`BufferedReader` 或 `BufferedWriter`。

## java.nio.file.Files 7

- `static byte[] readAllBytes(Path path)`
- `static String readString(Path path, Charset charset)`
- `static List<String> readLines(Path path, Charset charset)`

  读取文件内容。

- `static Path write(Path path, byte[] contents, OpenOption... options)`
- `static Path write(Path path, String contents, Charset charset, OpenOption... options)`
- `static Path write(Path path, CharSequence contents, Charset cs, OpenOption... options)`
- `static Path write(Path path, Iterable<? extends CharSequence> contents, OpenOption... options)`

  将给定的内容写入文件并返回路径。

- `static long mismatch(Path path, Path path2)`

  返回文件内容出现不同的第一个字节的位置。

- `static String probeContentType(Path path)`

  返回已安装的文件类型检测器的最佳猜测，或者如果无法确定类型则返回 `null`。

- `static InputStream newInputStream(Path path, OpenOption... options)`
- `static OutputStream newOutputStream(Path path, OpenOption... options)`
- `static BufferedReader newBufferedReader(Path path, Charset charset)`
- `static BufferedWriter newBufferedWriter(Path path, Charset charset, OpenOption... options)`

  打开文件进行读取或写入。

### 2.3.3. 创建文件和目录

要创建一个新目录，调用：

```java
Files.createDirectory(path);
```

路径中最后一个组件以外的所有部分必须已经存在。如果也要创建中间目录，请使用：

```java
Files.createDirectories(path);
```

你可以使用以下方法创建一个空文件：

```java
Files.createFile(path);
```

如果文件已存在，该调用将抛出异常。存在性检查和创建是原子的。如果文件不存在，它会在其他人有机会相同操作之前被创建。

有一些方便的方法，可以在给定的或系统特定的位置创建临时文件或目录：

```java
Path newPath = Files.createTempFile(dir, prefix, suffix);

Path newPath = Files.createTempFile(prefix, suffix);

Path newPath = Files.createTempDirectory(dir, prefix);

Path newPath = Files.createTempDirectory(prefix);
```

这里是一个 `Path`，而 `prefix`/`suffix` 是可能为 `null` 的字符串。例如，调用 `Files.createTempFile(null, ".txt")` 可能会返回类似 `/tmp/1234405522364837194.txt` 的路径。

创建文件或目录时，你可以指定属性，例如所有者或权限。然而，细节取决于文件系统，我们在这里不会介绍它们。

| `java.nio.file.Files` |
| :--- |
| `static Path createFile(Path path, FileAttribute<?>... attrs)` |
| `static Path createDirectory(Path path, FileAttribute<?>... attrs)` |
| `static Path createDirectories(Path path, FileAttribute<?>... attrs)` - 创建文件或目录。`createDirectories` 方法也会创建任何中间目录。 |
| `static Path createLink(Path link, Path existing)` |
| `static Path createSymbolicLink(Path link, Path target, FileAttribute<?>... attrs)` - 为给定的目标创建“硬”链接或符号链接。 |
| `static Path createTemp(String prefix, String suffix, FileAttribute<?>... attrs)` |
| `static Path createTemp(Path parentDir, String prefix, String suffix, FileAttribute<?>... attrs)` |
| `static Path createDirectory(String prefix, FileAttribute<?>... attrs)` |
| `static Path createDirectory(Path parentDir, String prefix, FileAttribute<?>... attrs)` - 创建临时文件或目录，位于适用于临时文件的位置或在给定的父目录中。返回创建的文件或目录的路径。 |

### 2.3.4. 复制、移动和删除文件

要将文件从一个位置复制到另一个位置，只需调用：

```java
Files.copy(fromPath, toPath);
```

如果想移动文件，请调用：

```java
Files.move(fromPath, toPath);
```

如果目标存在，复制或移动将失败。如果你想覆盖现有目标，请使用 `REPLACE_EXISTING` 选项。如果你想复制所有文件属性，请使用 `COPY_ATTRIBUTES` 选项。你可以这样提供两者：

```java
Files.copy(fromPath, toPath,

    StandardCopyOption.REPLACE_EXISTING,

    StandardCopyOption.COPY_ATTRIBUTES);
```

你可以指定移动应该是原子的。这样你就能确保要么移动成功完成，要么源文件继续存在。使用 `ATOMIC_MOVE` 选项：

```java
Files.move(fromPath, toPath,

    StandardCopyOption.ATOMIC_MOVE);
```

你也可以将输入流复制到 `Path`，这意味着将输入流保存到磁盘。同样，你可以将 `Path` 复制到输出流。使用以下调用：

```java
Files.copy(inputStream, toPath);

Files.copy(fromPath, outputStream);
```

与其他复制调用一样，你可以根据需要提供复制选项。

最后，要删除文件，只需调用：

```java
Files.delete(path);
```

如果文件不存在，此方法将抛出异常，因此你可能想使用：

```java
boolean deleted = Files.deleteIfExists(path);
```

删除方法也可以返回布尔值。请参见表 2.4 的选项摘要。

### 表 2.4：操作的标准选项

| 选项 | 描述 |
| :--- | :--- |
| `READ` | 读取。 |
| `WRITE` | 写入。 |
| `APPEND` | 追加到文件末尾。 |
| `REPLACE_EXISTING` | 如果目标存在则替换。 |
| `CREATE` | 如果不存在则创建新文件。 |
| `DELETE_ON_CLOSE` | 关闭时删除。 |
| `SPARSE` | 使文件稀疏。 |
| `SYNC` | 要求同步写入每次更新。 |
| `ATOMIC_MOVE` | 原子地移动。 |
| `COPY_ATTRIBUTES` | 复制文件属性。 |
| `NOFOLLOW_LINKS` | 不跟随符号链接。 |
| `FOLLOW_LINKS` | 跟随符号链接。 |

## java.nio.file.Files 7

- `static Path copy(Path from, Path to, CopyOption... options)`
- `static Path move(Path from, Path to, CopyOption... options)`
- `static long copy(InputStream from, Path to, CopyOption... options)`
- `static long copy(Path from, OutputStream to, CopyOption... options)`
- `static void delete(Path path)`
- `static boolean deleteIfExists(Path path)`

### 2.3.5. 获取文件信息

以下静态方法返回布尔值以检查路径的属性：

- `exists(path)`
- `isHidden(path)`
- `isReadable(path)`
- `isWritable(path)`
- `isExecutable(path)`
- `isRegularFile(path)`
- `isDirectory(path)`
- `isSymbolicLink(path)`

`size` 方法返回文件中的字节数。

```java
long fileSize = Files.size(path);
```

`getOwner` 方法返回文件的所有者，其为 `java.nio.file.attribute.UserPrincipal` 实例。

所有文件系统都会报告一组基本属性，由 `BasicAttributes` 接口封装，与信息部分重叠。基本属性是：

- 文件创建、最后访问和最后修改的时间，其为 `java.nio.file.attribute.FileTime` 实例。
- 文件是否为普通文件、目录、符号链接或这些这些者之一。
- 文件大小。
- 文件键——某些类的对象，特定于文件系统，可能或无法唯一标识一个文件。

要获取这些属性，调用：

```java
BasicFileAttributes attributes = Files.readAttributes(path, BasicFileAttributes.class);
```

如果你知道用户的文件系统是符合 POSIX 标准的，你可以改为获取 `PosixFileAttributes` 实例：

```java
PosixFileAttributes attributes = Files.readAttributes(path, PosixFileAttributes.class);
```

然后你可以找到组所有者以及所有者、组和世界的访问权限。

- `A readAttributes(Path path, Class<A> type, LinkOption... options)` 读取类型为 `A` 的文件属性。

| `java.nio.file.attribute.BasicFileAttributes` | 7 |
| :--- | :--- |
| `FileTime creationTime()`、`lastAccessTime()`、`lastModifiedTime()`、`boolean isRegularFile()`、`isDirectory()`、`isSymbolicLink()`、`isOther()`、`long size()`、`Object fileKey()` | |

| `java.nio.file.attribute.FileTime` | 8 |
| :--- | :--- |
| `Instant toInstant()` | 返回一个与此 `FileTime` 表示相同时间的 `Instant`。 |

### 2.3.6. 访问目录条目

静态 `Files.list` 方法返回一个 `Stream<Path>`，用于读取目录的条目。目录是按需读取的，使得高效处理包含海量条目的目录成为可能。

由于读取目录涉及到一个需要关闭的系统资源，您应该使用 `try` 块：

```java



```java
try (Stream<Path> entries = Files.list(pathToDirectory)) {

  ...

}
```

`list` 方法不会进入子目录。要处理目录的所有后代节点，请改用 `Files.walk` 方法。

```java
try (Stream<Path> entries = Files.walk(pathToRoot)) {

  // 所有后代，按深度优先遍历

}
```

以下是解压后的 `src.zip` 树的示例遍历：

```java
java/nio

java/nio/DirectCharBufferU.java

java/nio/ByteBufferAsShortBufferRL.java

java/nio/MappedByteBuffer.java

java/nio/ByteBufferAsDoubleBufferB.java

java/nio/charset

java/nio/charset/CoderMalfunctionError.java

java/nio/charset/CharsetDecoder.java

java/nio/charset/UnsupportedCharsetException.java

java/nio/charset/spi

java/nio/charset/spi/CharsetProvider.java

java/nio/charset/StandardCharsets.java

java/nio/charset/Charset.java

java/nio/charset/CoderResult.java

java/nio/HeapFloatR.java
```

如您所示，每当遍历产生目录时，它会在继续处理其兄弟节点之前进入该目录。

您可以通过调用 `Files.walk(pathToRoot, depth)` 来限制想要访问的树深度。两个 `walk` 方法都有一个类型为 `FileVisitOption...` 的变长参数，您只能提供一个选项：`FOLLOW_LINKS` 以跟踪符号链接。

> 注意：如果您过滤了 `walk` 返回的路径，且您的过滤标准调用了存储与目录关联的文件属性（例如大小、创建时间或类型（文件、目录、符号链接）），请使用 `find` 方法代替 `walk`。调用该方法时传入一个接受 `path` 和 `BasicFileAttributes` 对象的谓词函数。

唯一的优势是效率。由于目录正在读取中，这些属性是可以直接使用的。

这段代码片段使用 `Files.walk` 方法将一个目录复制到另一个目录：

```java
Files.walk(source).forEach(p -> {

  try {

    Path q = target.resolve(source.relativize(p));

    if (Files.isDirectory(p))

      Files.createDirectory(q);

    else

      Files.copy(p, q);

  } catch (IOException e) {

    throw new UncheckedIOException(e);

  }

});
```

遗憾的是，您无法轻松使用 `Files.walk` 方法来删除目录树，因为您需要在删除父目录之前删除子目录。第 2.3.8 节展示了如何克服这个问题。

> 警告：如果任何子目录不可读，`Files.walk` 方法将抛出异常。如果您只想访问可读目录，请使用下一节描述的 `walkFileTree` 方法。

### 2.3.7. Glob 模式

有时，通过模式来过滤目录遍历是有帮助的。对于这种需求，`glob` 语法比正则表达式更有用。例如，glob 表达式 `/**java` 表示任意任何嵌套子目录下的 Java 源文件。

表 2.5 显示了所有 glob 模式。

| 模式 | 说明 | 示例 |
| :--- | :--- | :--- |
| `*` | 匹配路径组件中的零或多个字符 | `*.java` 匹配当前目录下的所有 Java 文件。 |
| `**` | 匹配跨目录边界的零或多个字符 | `****java` 匹配任何子目录下的所有 Java 文件。 |
| `?` | 匹配一个字符。 | `????` 匹配所有四个字符（不计扩展名）的 Java 文件。 |
| `[ .. ]` | 匹配字符集。您可以使用连字符 `[0-9]` 和取反 `[0-9]`。 | `Test [0-9A-F].java` 匹配 `Textx.java`，其中 x 是一个十六进制数字。 |
| `{ .. }` | 匹配由逗号分隔的备选项。 | `*.{java,class}` 匹配所有 Java 和 class 文件。 |
| `\` | 转义上述任何字符以及 `\.`。 | `\*\*` 匹配所有名称中带有 `*` 的文件。 |

> **警告：** 如果您在 Windows 上使用 glob 语法，您必须转义反斜杠**两次**——一次是为了 glob 语法，一次是为了 Java 字符串语法：`Files.newDirectoryStream(dir, "C:\\\\")`

要按此类模式进行过滤，请构建一个 `PathMatcher` 并使用它的 `matches` 方法。

```java
PathMatcher javaSource =
    FileSystems.getDefault().getPathMatcher("glob:**/*.java");

List<Path> sourcePaths =
    Files.walk(root).filter(javaSource::matches).toList();
```

| `java.nio.file.FileSystem` | 7 |
| :--- | :--- |
| `- PathMatcher getPathMatcher(String syntax)` | |

| `java.nio.file.PathMatcher` | 7 |
| :--- | :--- |
| `boolean matches(Path path)` |

### 2.3.8. 目录流

正如您在 2.3.6 中看到的，`walk` 方法产生一个遍历目录的 `Stream<Path>`。有时您需要对遍历进行更细粒度的控制。在这种情况下，请使用 `DirectoryStream`。

```java
try (DirectoryStream<Path> entries = Files.newDirectoryStream(dir)) {

  for (Path entry : entries) {

    ...

  }

}
```

`try-with-resources` 块确保目录流被正确关闭。条目的访问没有特定的顺序。您可以使用模式过滤文件：

```java
try (DirectoryStream<Path> entries = Files.newDirectoryStream(dir, "*.java")) {

  for (Path entry : entries) {

    ...

  }

}
```

`walkFileTree` 方法接受 `FileVisitor<? super Path>`，但 `Path` 并没有大量的父类型。

一个便利类 `SimpleFileVisitor` 实现了 `FileVisitor` 接口，其默认方法为继续访问或在异常时终止访问。扩展它并根据需要重写方法。

例如，以下是如何打印给定目录的所有子目录：

```java
Files.walkFileTree(Path.of("/"), new SimpleFileVisitor<Path>() {

    public FileVisitResult preVisitDirectory(Path path, BasicFileAttributes attrs)

        throws IOException {

            System.out.println(path);

            return FileVisitResult.CONTINUE;

        }

    public FileVisitResult postVisitDirectory(Path dir, IOException exc) {

        return FileVisitResult.CONTINUE;

    }

    public FileVisitResult visitFileFailed(Path path, IOException exc)

        throws IOException {

            if (exc != null) throw exc;

            return FileVisitResult.SKIP_SUBTREE;

        }

});
```

注意我们需要重写 `postVisitDirectory` 和 `visitFailed`。否则，一旦遇到无法的目录或无法访问的文件，遍历就会失败。

此外注意，路径的属性作为参数传递给 `preVisitDirectory` 和 `visitFile` 方法。访问器已经需要进行操作系统调用来获取属性，因为它需要区分在文件和目录之间。通过这样，你不需要再次进行调用。

如果你需要在进入或离开目录时执行某些工作，`FileVisitor` 接口的其他方法将非常有用。例如，在删除目录树时，你需要在删除所有文件后删除当前目录。以下是删除目录树的完整代码：

```java
// 删除从 root 开始的目录树

Files.walkFileTree(root, new SimpleFileVisitor<Path>() {

    public FileVisitResult visitFile(Path file,

        BasicFileAttributes attrs)

        throws IOException {

            Files.delete(file);

            return FileVisitResult.CONTINUE;

        }

    public FileVisitResult postDirectory(Path dir,

        IOException e)

        throws IOException {

            if (e != null) throw e;

            Files.delete(dir);

            return FileVisitResult.CONTINUE;

        }

});
```

# `java.nio.file.Files` 7

- `static DirectoryStream<Path> newDirectoryStream(Path path)`  
  获取给定目录中文件和目录的迭代器。
- `static DirectoryStream<Path> newDirectoryStream(Path path, String glob)`  
  获取给定目录中文件和目录的迭代器。第二个方法只接受匹配给定 glob 模式的项。
- `static Path walkFileTree(Path start, FileVisitor<? super Path> visitor)`  
  遍历给定路径的所有后代，并将访问者应用到所有后代。

## `java.nio.file.SimpleFileVisitor<T>` 7

- `static FileVisitResult visitFile(T path, BasicFileAttributes attrs)`  
  在访问文件或目录时调用；返回 `CONTINUE`、`SKIP_SUBTREE`、`SKIP_SIBLINGS` 或 `TERMINATE` 之一。默认实现什么都不做并继续。
- `static FileVisitResult preVisitDirectory(T dir, BasicFileAttributes attrs)`
- `static FileVisitResult postVisitDirectory(T dir, IOException exc)`  
  在访问目录之前和之后调用。默认实现什么都不做并继续。然而，如果 `exc` 不为空，则会将其抛出，导致访问以该异常终止。
- `static FileVisitResult visitFailed(T path, IOException exc)`  
  如果在尝试获取给定文件的信息时抛出异常，则调用。默认实现重新抛出该异常，导致访问以该异常终止。如果你想继续，请重写该方法。

### 2.3.9. ZIP 文件系统

`Paths` 类在默认文件系统（用户本地磁盘上的文件）中查找路径。你可以拥有其他文件系统。其中一个更有用的是 ZIP 文件系统。如果 `zipname` 是一个 ZIP 路径的名称，那么调用

```java
FileSystem fs = FileSystems.newFileSystem(zippath);
```

将建立一个包含 ZIP 存档中所有文件的文件系统。如果你知道文件的名称，从存档中拷贝文件是一件容易的事：

```java
Files.copy(fs.getPath(sourceName), targetPath);
```

在这里，`fs.getPath` 是任意文件系统的 `Path` 别名。

要列出 ZIP 存档中的所有文件，请遍历树：

```java
Files.walk(fs.getPath("/")).forEach(IO::println);
```

要创建一个新的 ZIP 文件，调用：

```java
FileSystem fs = FileSystems.newFileSystem(zippath, Map.of("create", "true"));
```

然后将文件复制到文件系统中。完成后，调用

```java
fs.close();
```

以便将更改写入磁盘。

ZIP 文件系统比第 2.2.3 节描述的 API 更好，后者仅为了处理 ZIP 存档就需要专门的类。

| `java.nio.file.FileSystems` 7 |
| :--- |
| `■ static FileSystem newFileSystem(Path path)` |
| `■ static FileSystem newFileSystem(Path path, Map<String, ?> env)` 返回由接受给定路径第一个文件系统提供者创建的文件系统。默认情况下，有一个用于 ZIP 文件系统的提供者，接受名称以 `.zip` 或 `.jar` 结尾的文件。使用 `env` 映射用于依赖于文件系统提供者的配置参数。 |
| `■ void close()` 拷贝此文件系统并永久写入任何更改。 |

| `java.nio.file.FileSystem` 7 |
| :--- |
| `■ static Path getPath(String first, String... more)` 通过连接给定字符串来创建路径。 |

## 2.4. 内存映射文件

大多数操作系统都可以利用虚拟内存实现将文件（或文件的一个区域）“映射”到内存中。然后，就可以像访问内存数组一样访问文件，这比传统的文件操作要快得多。

### 2.4.1. 内存映射文件的性能

在本节的末尾，你可以找到一个使用传统文件输入和内存映射文件计算文件 CRC32 校验的程序。在某机器上，当计算 JDK `lib` 目录下的 51MB 文件 `src.zip` 的校验和时，我们得到了表 2.6 所示的时间数据。

表 2.6：文件操作的时间数据

| 方法 | 时间 |
| :--- | :--- |
| 普通输入流 | 15.1 秒 |
| 缓冲输入流 | 0.8 秒 |
| 随机访问文件 | 11.9 秒 |
| 内存映射文件 | 0.2 秒 |

如你所示，与随机访问相比，内存映射的提升是巨大的。内存映射使用的 API 比缓冲输入不直观。以下是操作方法。首先，获取一个通道：

```java
FileChannel channel = FileChannel.open(path, options);
```

然后，通过调用 `map` 从通道获取 `ByteBuffer`。指定要映射的文件区域和模式。支持三种模式：

- `FileChannel.MapMode.READ_ONLY`：结果是只读的。对缓冲区进行写入尝试将导致 `ReadOnlyBufferException`。
- `FileChannel.MapMode.READ_WRITE`：结果是可写的，映射相同文件的其他程序可以立即看到更改。
- `FileChannel.MapMode.PRIVATE`：结果是可写的，但任何更改对该缓冲区私有的。

例如：

```java
MappedByteBuffer buffer = channel.map(FileChannel.MapMode.READ_ONLY, 0, channel.size());
```

一旦有了缓冲区，可以使用 `ByteBuffer` 类和 `Buffer` 超类的方法来读取数据。缓冲区支持顺序和随机访问。缓冲区有一个位置，会被 `get` 和 `put` 操作移动。例如，你可以顺序遍历缓冲区中的所有字节：

```java
while (buffer.hasRemaining()) {

    byte b = buffer.get();

}
```

或者，你可以使用随机访问：

```java
for (int i = 0; i < buffer.limit(); i++) {

    byte b = buffer.get();

}
```

你还可以通过以下方法读写字节数组：

```java
get(byte[]) bytes

get(byte[]) bytes, int offset, int length
```

最后，还有方法：

```java
getChar

getLong

getFloat

getShort
```




用于读取以二进制值存储在文件中的基本类型值。正如我们已经提到的，Java 使用大端序二进制数据。然而，如果你需要处理包含小端序二进制数字的文件，只需调用：

```java
buffer.order(ByteOrder.LITTLE_ENDIAN);
```

要发现缓冲区的当前字节序，调用：

```java
ByteOrder b = buffer.order();
```

要向缓冲区写入数字，使用以下方法之一：

```java
putInt
putLong
putFloat
putShort
putDouble
```

在某时刻，特别是当通道关闭时，这些更改会被写回文件。

CRC 计算的细节并不重要。我们只是将其作为一个有用的文件操作示例。（在实际操作中，你会分大块地读取和更新数据，而不是一次一个字节地处理。速度差异并没有那么显著。）

按如下方式运行程序：

```bash
java v2ch02.memoryMap/MemoryMapDemo filename
```

## 列表 2.3：`v2ch02/memoryMap/MemoryMapDemo.java`

```java
package v2ch02.memoryMap;

import module java.base;

/**
 * 此程序以四种方式计算文件的 CRC 校验和。
 */
public class MemoryMapDemo {

    static void main(String[] args) throws Exception {
        Path filename = Path.of(args.length > 0 ? args[0]
            : IO.println("请输入大文件的路径: "));

        long start = System.nanoTime();
        long crcValue = checksumInputStream(filename);
        long end = System.nanoTime();

        IO.println(Long.toString(crcValue));
        IO.println("%.3f seconds ".formatted(end - start) * 1E-9));

        IO.println("缓冲式输入流: ");
        start = System.nanoTime();
        crcValue = checksumBufferedInputStream(filename);
        end = System.nanoTime();

        IO.println(Long.toString(crcValue));
        IO.println("%.3f seconds ".formatted(end - start) * 1E-9));

        IO.println("随机访问文件: ");
        start = System.nanoTime();
        crcValue = checksumRandomAccessFile(filename);
        end = System.nanoTime();

        IO.println(Long.toString(crcValue));
        IO.println("%.3f seconds ".formatted(end - start) * 1E-9));

        IO.println("内存映射文件: ");
        start = System.nanoTime();
        crcValue = checksumMappedFile(filename);
        end = System.nanoTime();

        IO.println(Long.toString(crcValue));
        IO.println("%.3f seconds ".formatted(end - start) * 1E-9));
    }

    static long checksumInputStream(Path filename) throws IOException {
        try (InputStream in = Files.newInputStream(filename)) {
            var crc = new CRC32();
            boolean done = false;

            while (!done) {
                int c = in.read();

                if (c == -1)
                    done = true;
                else
                    crc.update(c);
            }

            return crc.getValue();
        }
    }

    static long checksumBufferedInputStream(Path filename) throws IOException {
        try (BufferedInputStream in = Files.newInputStream(filename)) {
            var crc = new CRC32();
            boolean done = false;

            while (!done) {
                int c = in.read();

                if (c == -1)
                    done = true;
                else
                    crc.update(c);
            }

            return crc.getValue();
        }
    }

    static long checksumRandomAccessFile(Path filename) throws IOException {
        try (RandomAccessFile file = new RandomAccessFile(filename.toFile(), "r")) {
            var crc = new CRC32();
            long length = file.length();

            for (long p = 0; p < length; p++) {
                int c = file.readByte();
                crc.update(c);
            }

            return crc.getValue();
        }
    }

    static long checksumMappedFile(Path filename) throws IOException {
        try (FileChannel channel = FileChannel.open(filename)) {
            var crc = new CRC32();
            int length = (int) channel.size();

            MappedByteBuffer buffer = channel.map(
                FileChannel.MapMode.READ_ONLY, 0, length
            );

            for (int p = 0; p < length; p++) {
                int c = buffer.get(p);
                crc.update(c);
            }

            return crc.getValue();
        }
    }
}
```





| `java.io.FileInputStream` | 1.0 |
| :--- | :--- |
| `FileChannel getChannel()` | 1.4 返回一个用于访问此输入流的通道。 |

| `java.io.FileOutputStream` | 1.0 |
| :--- | :--- |
| `FileChannel getChannel()` | 1.4 返回一个用于访问此输出流的通道。 |

| `java.io.RandomAccessFile` | 1.0 |
| :--- | :--- |
| `FileChannel getChannel()` | 1.4 返回一个用于访问此文件的通道。 |

| `java.nio.channels.FileChannel` | 1.4 |
| :--- | :--- |
| `static FileChannel open(Path path, OpenOption... options)` | 7 为给定路径打开文件通道。默认情况下，该通道以读模式打开。参数 `options` 是 `StandardOpenOption` 枚举中的 `WRITE`、`APPEND`、`TRUNCATE_EXISTING`、`CREATE` 值之一。 |
| `MappedByteBuffer map(FileChannel.MapMode mode, long position, long size)` | 将文件的某个区域映射到内存。参数 `mode` 是 `FileChannel.MapMode` 类中的 `READ_ONLY`、`READ_WRITE` 或 `PRIVATE` 常量之一。 |

## `java.nio.Buffer` 1.4

- `boolean hasRemaining()` 如果当前缓冲区位置尚未到达缓冲区边界，则返回 `true`。
- `int limit()` 返回缓冲区的限制。

## 2.4.2. Buffer 数据结构

当使用内存映射时，你创建一个跨整个文件或你感兴趣的文件区域的缓冲区。你也可以使用缓冲区来读取和写入小块信息。

在本节中，我们简要描述了 `Buffer` 的基本操作。`Buffer` 是相同类型值的数组。`Buffer` 类是一个抽象类，其具体子类包括 `ByteBuffer`、`CharBuffer`、`DoubleBuffer`、`FloatBuffer`、`IntBuffer`、`LongBuffer` 和 `ShortBuffer`。

> 注意：`StringBuffer` 类与这些缓冲区无关。

如 `#ch01fig11` 所示，缓冲区具有：

- 不改变的容量（`capacity`）
- 下一个读写位置（`position`）
- 读写无意义的限制（`limit`）
- 可选的用于重复读写操作的标记（`mark`）

图 2.5：缓冲区

缓冲区的主要用途是执行“填充-消费”的循环。开始时，缓冲区的位置为 `0`，限制为容量。通过调用 `put` 或从通道读取来持续填充缓冲区。

当数据耗尽或达到容量时，就是切换到消费内容的时间了。调用 `flip` 将限制设置为当前位置，并将位置置为 `0`。

现在，通过调用 `get` 或向通道写入来继续消费，只要 `remaining` 方法（计算 `limit - position`）返回正值即可。

当你耗尽缓冲区中的所有值时，调用 `compact` 来准备缓冲区以便再次填充。任何未被消费的数据都会被复制到缓冲区的开头。`position` 被设置为紧跟在复制数据之后，而 `limit` 被设置为容量（`capacity`）。

如果你想重新读取缓冲区，请使用 `rewind` 或 `mark/reset`（详情见 API 注意事项）。

要获取缓冲区，请调用静态方法，如 `ByteBuffer.allocate` 或 `ByteBuffer.wrap`。

此循环使用缓冲区将数据从一个通道传输到另一个通道：

```java



```java
ByteBuffer buffer = ByteBuffer.allocate(BUFFER_SIZE);

boolean doneReading = false;

boolean doneWriting = false;

while (!(doneReading && doneWriting)) {
  if (sourceChannel.read(buffer) == -1) doneReading = true;

  buffer.flip();

  destinationChannel.write(buffer);

  if (buffer.remaining() == 0) doneWriting = true;

  buffer.compact();
}
```

## `java.nio.Buffer` 1.4

- `Buffer flip()`

  通过将 `limit` 设置为 `position` 并将 `position` 设置为 0，准备此缓冲区进行读取操作；返回此。

- `Buffer rewind()`

  通过将 `position` 设置为 0 并保持 `limit` 不变，准备此缓冲区以重新读取相同值；返回此。

- `Buffer clear()`

  通过将 `position` 设置为 0 并将 `limit` 设置为容量，准备此缓冲区进行写入操作；返回此。

- `Buffer mark()`

  将此缓冲区的标记（`mark`）设置为当前 `position`；返回此。

- `Buffer reset()`

  将此缓冲区的 `position` 设置为 `mark`，从而允许对标记部分再次读取或写入；返回此。

- `int remaining()`

  返回剩余的可读或可写值——即 `limit` 与 `position` 之间的差值。

## `java.nio.ByteBuffer` 1.4

- `Buffer compact()`

  将任何未消费的字节复制到缓冲区的开头，将 `position` 设置为后续字节，并将 `limit` 设置为容量；返回此。

## `java.nio.ReadableByteBuffer` 1.4

- `int read(ByteBuffer dst)`

  用可用字节填充缓冲区的剩余部分，并返回传输的字节数；如果通道已到达末尾则返回 -1。

## `java.nio.WritableByteChannel` 1.4

- `int write(ByteBuffer src)`

  尝试消费缓冲区中的剩余字节，并返回传输的字节数。

## 2.5 文件锁

当多个同时执行的程序需要修改同一个文件时，它们需要以某种方式进行通信，否则文件很容易损坏。文件锁可以解决这个问题。文件锁控制对文件或文件中某个字节范围的访问。

假设你的应用程序保存了一个带有系统级偏好的文件。如果用户启动了程序的两个实例，可能会发生它们都想同时写入文件的情况。在这种情况下，第一个实例应该锁定文件。当第二个实例发现文件被锁定时，它可以决定等待文件被解锁，或简单地跳过写入过程。

要锁定文件，请调用 `FileChannel` 类的 `lock` 或 `tryLock` 方法。

```java
FileChannel channel = FileChannel.open(path);

FileLock lock = channel.lock();
```

或者：

```java
FileLock lock = channel.tryLock();
```

第一次调用会阻塞直到锁可用。第二次调用会立即返回，返回锁或在锁不可用时返回 `null`。文件一直保持锁定，直到通道关闭或在锁上调用 `release` 方法。

你也可以通过以下调用锁定文件的部分内容：

```java
FileLock lock(long start, long size, boolean shared)
```

或者：

```java
FileLock tryLock(long start, long size, boolean shared)
```

（注：由于原文后半部分存在重复的 API 注释和代码块，已根据要求过滤掉重复内容，仅保留了核心逻辑描述翻译。）

| `java.nio.channels.FileChannel` | 1.4 |
| :--- | :--- |
| `FileLock lock()` | 获取整个文件上的排斥锁。此方法会阻塞直到获取锁为止。 |
| `FileLock tryLock()` | 获取整个文件上的排斥锁，如果无法获取锁，则返回 `null`。 |
| `FileLock lock(long position, long size, boolean shared)` | 在文件的某个区域获取锁。第一个方法会阻塞直到获取锁为止，第二个方法在无法获取锁时返回 `null`。 |
| `FileLock tryLock(long position, long size, boolean shared)` | 如果无法获取锁，方法返回 `null`。参数 `shared` 为 `true` 表示共享锁，为 `false` 表示排斥锁。 |
| `FileChannel truncate(long size)` | 如果文件大于给定大小，则将其截断为该大小。 |

| `java.nio.channels.FileLock` | 1.4 |
| :--- | :--- |
| `void close()` | 释放此锁。 |

| `java.io.RandomAccessFile` | 1.0 |
| :--- | :--- |
| `FileChannel getChannel()` | 1.4 版本返回此随机访问文件的通道。 |

## 2.6 对象输入输出流与序列化

在第 2.1.7 节和第 2.2.2 节中，你已经了解了如何以文本或二进制格式存储 `Employee` 对象。然而，你在面向对象的程序中创建的对象很少是同一种类型。例如，你可能有一个名为 `staff` 的数组，它是一个 `Employee` 记录数组，但其中包含的对象实际上是 `Manager` 等子类的实例。

完全可以设计一种允许存储此类多态集合的数据格式——幸运的是，我们不需要这样做。Java 语言支持一种非常通用的机制，称为对象序列化，它允许任何对象写入输出流并在稍后重新读取。（你将在接后的章节中看到“序列化”一词的来源）。

### 2.6.1 保存和加载可序列化对象

要保存对象数据，你首先需要打开一个 `ObjectOutputStream` 对象：

```java
var out = new ObjectOutputStream(new FileOutputStream("employee.dat"));
```

现在，要保存，只需在下面的代码片段中使用 `ObjectOutputStream` 类的 `writeObject` 方法：

```java
var harry = new Employee("Harry Hacker", 50000, 1989, 10, 1);

var boss = new Manager("Carl Cracker", 80000, 1987, 12, 15);

out.writeObject(harry);

out.writeObject(boss);
```

要将对象重新读回，首先获取一个 `ObjectInputStream` 对象：

```java
var in = new ObjectInputStream(new FileInputStream("employee.dat"));
```

然后，使用 `readObject` 方法按照写入时的相同顺序检索对象：

```java
var e1 = (Employee) in.readObject();

var e2 = (Employee) in.readObject();
```

然而，对于任何想要保存到输出流并从对象输入流恢复的类，你都需要进行一处更改。该类必须实现 `Serializable` 接口：

```java
class Employee implements Serializable { . . }
```

`Serializable` 接口没有方法，因此你不需要以任何方式更改你的类。在这方面，它与我们在第一卷第 6 章中讨论的 `Cloneable` 接口相似。然而，要使类可克隆，你仍然需要重写 `Object` 类的 `clone` 方法。而要使类可序列化，你不需要做其他任何。

> **注意：** 你只能使用 `writeObject/readObject` 方法写入和读取对象。对于基本类型值，请使用 `writeInt/readInt` 或 `writeDouble/readDouble` 等方法。（输入/输出流类实现了 `DataInput/DataOutput` 接口。）

在底层，`ObjectOutputStream` 会查看对象的所有字段并保存其内容。例如，在写入 `Employee` 对象时，名称、日期和薪水字段会被写入输出流中。

然而，有一个重要的情况需要考虑：当一个对象作为多个对象状态的一部分被共享时，会发生什么？

为了说明这个问题，让我们对 `Manager` 类进行细小的修改。让我们怀旧地假设，每个经理都有一个秘书：

```java
class Manager extends Employee {
  private Employee secretary;

  . . .
}
```

每个 `Manager` 对象现在包含一个指向描述秘书的 `Employee` 对象的引用。当然，两个经理可以共享同一个秘书，如 `#ch01fig06` 和接后的代码所示：

```java
var harry = new Employee("Harry Hacker", . . .);

var carl = new Manager("Carl Cracker", . . .);

carl.setSecretary(harry);

var tony = new Manager("Tony Tester", . .);

tony.setSecretary(harry);
```

**图 2.6：两个经理可以共享同一个员工。**

保存这样的对象网络是一项挑战。当然，我们无法保存和恢复秘书对象的内存地址。当对象被重新加载时，它占据的内存地址可能与原始完全不同。

相反，每个对象保存时都带有一个序列号——这就是该机制被称为“对象序列化”的原因。以下是该算法：

1. 为遇到的每个对象引用关联一个序列号（如 `#ch01fig07` 所示）。
2. 第一次遇到对象引用时，将对象数据保存到输出流。
3. 如果之前保存过，则只需检索对象引用。

当读回对象时，过程反过来：

1. 当在输入流中第一次指定一个对象时，构造它，用流数据对其初始化，并记住序列号与对象引用之间的关联。

**注意：** 在本章中，我们使用序列化将对象集合保存到磁盘文件，并按照我们存储的方式将其检索。另一个非常重要的应用是通过网络连接将对象集合传输到另一个计算机。正如内存地址在文件中没有意义一样，当你与另一个处理器通信时，它们也是没有意义。

**注意：** 如果序列类的父类不是可序列化的，则它必须有一个可访问的无参数构造函数。考虑这个例子：

```java
class Person // 不序列化

class Employee implements Serializable
```



当反序列化 `Employee` 对象时，其实例字段从对象输入流中读取，但 `Person` 实例字段由 `Person` 构造函数设置。

列表 2.5 是一个保存并重新加载 `Employee` 和 `Manager` 对象网络（其中一些共享同一个员工作为秘书）的程序。注意，重新加载后秘书对象是唯一的——`staff[1]` 获得率，这体现在经理的秘书字段中。

- `Object readObject()`

  从 `ObjectInputStream` 中读取一个对象。特别地，该方法会读取对象的类、类的签名以及该类及其所有父类的非瞬态（nontransient）和非静态（nonstatic）字段的值。它执行反序列化，以便恢复多个对象引用。

## 2.6.2. 理解对象序列化文件格式

对象序列化将对象数据以特定的文件格式保存。当然，你可以使用 `writeObject`/`readObject` 方法，而不需要知道表示文件中对象的确切字节序列。尽管如此，我们发现研究数据格式对于深入了解对象序列化过程非常有帮助。由于细节具有一定的技术性，如果你对实现不感兴趣，可以随时跳过本节。

每个文件都以两个字节的“魔数”开头：

```text
AC ED
```

随后是对象序列化格式的版本号，目前为：

```text
00 05
```

（在本节中，我们全程使用十六进制表示字节。）

然后，它包含一系列对象，按照它们保存的顺序排列。

字符串对象的保存格式为：

- `74`
- 两个字节长度
- “修改后的 UTF-8”格式的字符

例如，字符串 `"Harry"` 被保存为：

```text
74 00 05 Harry
```

当保存一个对象时，该对象的类也必须被保存。类描述符（class descriptor）具有以下格式：

- `72`
- 2 字节类名长度
- 类名
- 8 字节指纹
- 1 字节标志
- 2 字节实例字段描述符计数
- 实例字段描述符
- `78`（结束标记）
- 父类描述符（如果没有，则为 `70`）

指纹通过对类、父类、接口、字段类型和方法签名的描述进行规范化排序，然后对该数据应用安全哈希算法版本 1（SHA-1）得到的。

SHA-1 为一个块的信息提供一个“指纹”。无论原始数据的大小如何，该指纹始终是一个 20 字节的数据包。它是通过对数据进行一系列巧妙的位操作创建的，这使得信息一旦发生任何更改时，指纹极有可能发生变化。序列化机制仅使用 SHA-1 代码的前八个字节作为类的指纹。如果实例字段或方法发生变化，指纹仍然极有可能发生变化。

读取对象时，其指纹会与类的当前指纹进行比较。如果它们不匹配，意味着类定义在对象写入后发生了变化，并将生成异常。当然，在实践中，类会演进，程序可能需要读取旧版本的对象。我们将在 2.6.7 节中讨论这一点。

标志字节由 `java.io.ObjectStreamConstants` 中定义的位掩码组成，如表 2.7 所示。

表 2.7：位掩码

| 名称 | 值 | 描述 |
| :--- | :--- | :--- |
| `SC_WRITE_METHOD` | 1 | 类定义了 `writeObject` 方法。 |
| `SC_SERIALIZABLE` | 2 | 类实现了 `Serializable`。 |
| `SC_EXTERNALIZABLE` | 4 | 类实现了 `Externalizable`。 |
| `SC_BLOCK_DATA` | 8 | 以“块数据”写入的不透明数据（JDK 1.2 起默认）。 |
| `SC_ENUM` | 16 | 类是一个枚举。 |

我们实现 `Serializable` 接口的类将具有标志值为 02。可序列化的 `java.util.Date` 类标志为 03，因为它定义了自身的 `writeObject` 方法（见 2.6.4 节）。第 2.6.5 节中讨论 `Externalizable` 接口。

每个实例字段描述符的格式为：

- 1 字节类型代码
- 2 字节字段名长度
- 字段名
- 类名（如果字段是对象）

类型代码为以下内容之一：

| 代码 | 类型 |
| :--- | :--- |
| `B` | byte |
| `C` | char |
| `D` | double |
| `F` | float |
| `I` | int |
| `J` | long |
| `L` | object |
| `S` | short |
| `Z` | boolean |
| `[` | array |

当类型代码为 `L` 时，字段名后紧跟着字段类型。类名和字段名字符串不以代码 `74` 开头，但字段类型是。字段类型使用略有不同的名称编码方式——即原生方法使用的格式。

例如，`Employee` 类的 `salary` 字段被编码为：

```text
D 00 06 salary
```

以下是示例程序中 `serial` 包内 `Employee` 类的完整类描述符：

| 数据 | 描述 |
| :--- | :--- |
| `72 00 0F serial.Employee` | |
| `74 1E C8 E6 C3 F8 B8 77 02` | 指纹和标志 |
| `00 03` | 实例字段数量 |
| `D 00 06 salary` | 实例字段类型和名称 |
| `L 00 07 hireDay` | 实例字段类型和名称 |
| `74 00 10 Ljava/util/Date;` | 实例字段类名：`java.util.Date` |
| `L 00 04 name` | 实例字段类型和名称 |

序列号指向上一个类。相同的机制也适用于对象。如果写入对之前保存对象的引用，它将以完全相同的方式保存——即 `71` 后跟序列号。从上下文总是清楚地知道特定的序列引用是指类描述符还是对象。

某些类（例如 `Date` 类）将对象状态存储在不透明二进制块中，编码如下：

- `77`（短块）或 `7A`（长块）
- 1 字节或 4 字节的块长度
- 块内容
- `78`

最后，空引用存储为：

```text
70
```

以下是前节 `ObjectStreamDemo` 程序的带注释输出。运行该程序，查看其数据文件 `employee.ser` 的十六进制转储，并将其与注释列表进行比较。最重要的行位于输出的末尾。它们显示了对之前保存对象的引用。

| Data | Description |
| :--- | :--- |
| `AC ED 00 05` | 文件头 |
| `75` | 数组 `staff`（serial #1） |
| `72 00 12 Lserial.Employee;` | 新类，字符串长度，名称 `Employee[]`（serial #0） |
| `40 05 D6 7E 3B BB F2 50 02` | 指纹和标志位 |
| `00 00` | 实例字段数量 |
| `78` | 结束标记 |
| `70` | 无超类 |
| `00 00 00 03` | 数组项数量 |
| `73` | `staff[0]`：新对象（serial #7） |
| `72 00 0E serial.Manager` | 新类，字符串长度，名称（serial #2） |
| `2F FF 1F 1D 8E 7A A9 74 02` | 指纹和标志位 |
| `00 01` | 实例字段数量 |
| `L 00 09 secretary` | 实例字段类型和名称 |
| `74 00 11 Lserial/Employee;` | 实例字段类名：String（serial #3） |
| `78` | 结束标记 |
| `72 00 0F serial.Employee` | 超类：新类，字符串长度，类名（serial #4） |
| `74 1E C8 E6 C3 F8 B8 77 02` | 指纹和标志位 |
| `00 03` | 实例字段数量 |
| `D 00 06 salary` | 实例字段类型和名称 |
| `L 00 07 hireDay` | 实例字段类型和名称 |
| `74 00 10 Ljava/util/Date;` | 实例字段类名：String（serial #5） |
| `L 00 04 name` | 实例字段类型和名称 |
| `74 00 12 Ljava/lang/String;` | 实例字段类名：String（serial #6） |
| `78` | 结束标记 |
| `70` | 无超类 |
| `40 F3 88 00 00 00 00` | `salary` 字段值：double |
| `73` | `hireDay` 字段值：新对象（serial #9） |
| `72 00 0E java.util.Date` | 新类，字符串长度，类名（serial #8） |
| `68 6A 81 01 4B 59 74 19 03` | 指纹和标志位 |
| `00 00` | 无实例字段 |
| `78` | 结束标记 |
| `70` | 无超类 |
| `77 08` | 外部存储，字节数 |
| `00 00 00 83 E7` | 不透明字节 |
| `4B 7D 80` | 结束标记 |
| `74 00 0C Carl Cracker` | `name` 字段值：String（serial #10） |
| `73` | `secretary` 字段值：新对象（serial #11） |
| `71 00 7E 00 04` | 现有类（使用 serial #4） |
| `40 E8 6A 00 00 00 00` | `salary` 字段值：double |
| `73` | `hireDay` 字段值：新对象（serial #12） |
| `71 00 7E 00 08` | 现有类（使用 serial #8） |
| `77 08` | 外部存储，字节数 |
| `00 00 00 91 19 97 3D 80` | 不透明字节 |
| `78` | 结束标记 |
| `74 00 0C Harry Hacker` | `name` 字段值：String（serial #13） |
| `71 00 7E 00 0B` | `staff[1]`：现有对象（使用 serial #11） |
| `73` | `staff[2]`：新对象（serial #14） |
| `71 00 7E 00 02` | 现有类（使用 serial #2） |
| `40 E3 88 00 00 00 00` | `salary` 字段值：double |
| `73` | `hireDay` 字段值：新对象（serial #15） |
| `71 00 7E 00 08` | 现有类（使用 serial #8） |
| `77 08` | 外部存储，字节数 |
| `00 00 00 94 6B 50 89 80` | 不透明字节 |
| `78` | 结束标记 |
| `Tester 74 00 0B Tony` | `name` 字段值：String（serial #16） |
| `71 00 7E 00 0B` | `secretary` 字段值：新对象（serial #11） |

要实现这一点，类必须实现 `Externalizable` 接口。这反过来要求定义两个方法：

```java
public void readExternal(ObjectInput in)
    throws IOException, ClassNotFoundException;

public void writeExternal(ObjectOutput out)
    throws IOException;
```

与 `readObject` 和 `writeObject` 方法不同，这些方法完全负责保存和恢复整个对象，包括父类数据。在写入对象时，序列化机制仅在输出流中记录对象的类信息。在读取一个 `externalizable` 对象时，输入流会使用无参数构造函数创建一个对象，然后调用 `readExternal` 方法。

在这个示例中，`LabeledPixel` 类继承了实现 `Serializable` 的 `Point` 类，但它接管了该类及其父类的序列化。对象的字段没有存储在标准的序列化格式中，而是被放置在一个不透明的块中。

```java
public class LabeledPixel extends Point implements
    Externalizable {

    private String label;

    public LabeledPixel() {} // externalizable 要求的

    public void writeExternal(ObjectOutput out)
        throws IOException {

        out.writeInt((int) getX());
        out.writeInt((int) getY());
        out.writeUTF(label);
    }

    public void readExternal(ObjectInput in)
```



```java
throws IOException, ClassNotFoundException {

    int x = in.readInt();

    int y = in.readInt();

    setLocation(x, y);

    label = in.readUTF();

}

}
```

> 注意：`readExternal` 和 `writeExternal` 方法不应带有 `@Serial` 注解。由于它们是在 `Externalizable` 接口中定义的，你可以简单地为它们加上 `@Override`。

> 注意：与私有的且只能由序列化机制调用的 `readObject` 和 `writeObject` 方法不同，`readExternal` 和 `writeExternal` 方法是公共的。特别是 `readExternal` 可能会允许修改现有对象的状态。

## 2.6.6. `readResolve` 和 `writeReplace` 方法

我们理所当然认为对象只能通过构造函数构造。然而，反序列化的对象并不是构造的。它的字段仅仅是从对象流中恢复的。

如果构造函数强制执行某些条件，就会出现问题。例如，单例对象可以实现为构造函数只能被调用一次。作为另一个例子，数据库实体可以被构造为始终来自一个受管理的实例的池。

你不应该为单例实现你自己的机制。如果你需要一个单例，请创建一个包含一个实例的枚举类型，按照惯例该实例被称为 `INSTANCE`。

```java
public enum PersonDatabase {

    public Person findById(int id) { . . .

    . . .

}
```

这之所以有效，是因为枚举实例保证能被正确地反序列化。

现在，假设你正处于一种罕见的情况，即你想控制每个反序列化实例的标识性。例如，假设一个 `Person` 类希望在反序列化时从数据库恢复其实例。那么你不应该序列化对象本身。相反，应该请求保存一个代理实例。在恢复时，由代理对象来定位并构造所需的对象。你的类需要提供一个返回代理对象的 `writeReplace` 方法：

```java
public class Person implements Serializable {

    private int id;

    // 其他字段

    @Serial private Object writeReplace() {

        return new PersonProxy(id);

    }

}
```

当一个 `Person` 对象被序列化时，它的没有任何一个字段被保存。相反，会调用 `writeReplace` 方法，其返回值被序列化并写入流中。

代理类需要实现一个产生 `Person` 实例的 `readResolve` 方法：

```java
class PersonProxy implements Serializable {

    private int id;

    public PersonProxy(int id) {

        this.id = id;

    }

    @Serial private Object readResolve() {

        return PersonDatabase.INSTANCE.findById(id);

    }

}
```

当 `readObject` 方法在 `ObjectInputStream` 中发现 `PersonProxy` 时，它会反序列化代理，调用其 `readResolve` 方法并返回结果。

> 注意：与 `readObject` 和 `writeObject` 方法不同，`readResolve` 和 `writeReplace` 方法不需要私有。

> 注意：对于枚举和记录（records），`readObject/writeObject` 以及 `readExternal/writeExternal` 方法不用于序列化。对于记录（但不对于枚举），将使用 `writeReplace` 方法。

## 2.6.7. 版本控制

如果你使用序列化来保存对象，你需要考虑程序演进时会发生什么。版本 1.1 能读取旧文件吗？仍使用 1.0 的用户能读取新版本产生的文件吗？显然，如果对象文件能够处理类的演进将是理想的。

初看之下，这似乎是不可能的。当类定义发生任何变化时，它的 SHA 指纹也会随之改变，而你知道对象输入流将拒绝读取指纹不同的对象。然而，一个类可以表示它与自己的早期版本兼容。为了做到这一点，你必须先获取该类早期版本的指纹。使用 JDK 部分的独立 `serialver` 程序来获取此数字。例如，运行：

```bash
serialver serial.Employee
```

将打印：

```text
serial.Employee: static final long serialVersionUID = 8367346051156850807L;
```

该类的所有后续版本必须将 `serialVersionUID` 常量定义为与原始相同的指纹。

```java
class Employee implements Serializable { // 版本 1.1

    @Serial static final long serialVersionUID = 8367346051156850807L;

}
```

一旦类拥有了 `serialVersionUID`，它将不再手动计算指纹，而是使用该值。

如果只是类的方法发生变化，读取不同版本没有问题。然而，如果实例字段发生变化，你拥有的字段可能比序列化对象的多或少，或者字段类型不同。在这种情况下，输入流不会尝试将一种类型转换为另一种。如果序列化对象具有当前版本不存在的实例字段，输入流将忽略这些额外数据。如果当前版本具有序列化对象不存在的实例字段，新增的字段将设置为默认值（对象为 `null`，数字为 0，布尔值为 `false`）。

这里有一个例子。假设我们使用类的原始版本（1.0）在磁盘上保存了一些员工记录。现在我们通过添加一个名为 `department` 的字段将 `Employee` 类更改为 2.0。`ch01fig09` 显示了当将 1.0 对象读入使用 2.0 对象的程序时发生了什么。`department` 字段被设置为 `null`。`ch01fig10` 显示了相反的情况：使用 1.0 对象的程序读取 2.0 对象。额外的 `department` 字段被忽略了。

这个过程是安全的吗？这取决于情况。丢弃实例字段似乎是害的——接收者仍然拥有它已知要操作的所有数据。将实例字段设置为 `null` 可能就不那么安全。许多类努力在所有构造函数中将所有实例字段初始化为非空值，以便方法不需要准备处理 `null` 数据。类设计者负责在 `readObject` 方法中实现额外的代码来修复版本不兼容问题，或者确保方法足够健壮以处理 `null` 数据。

可以声明 `record` 的 `serialVersionUID`，但反序列化时这些 ID 并不匹配。

> 注意：在本节中，你已经看到了当读取器版本的类具有对象流中不存在的实例字段时会发生什么。在类演进过程中，也可能出现添加超类的情况。在这种情况下，使用新版本的读取器可能会读取一个对象流，其中超类的实例字段未被设置。默认情况下，这些实例字段被设置为它们的零/null 默认值。这可能导致超类处于不安全状态。超类可以通过定义一个初始化方法来防止该问题：

```java
@Serial private void readObjectNoData() throws
ObjectStreamException
```

该方法应该设置成与无参数构造函数相同的状态，或者抛出一个 `InvalidObjectException`。它只在一种异常情况下——即读取一个包含具有缺失超类数据的子类实例的对象流时——才会被调用。

## 2.6.8. 反序列化与安全

在对可序列化类进行反序列化期间，对象的创建不会调用该类的任何构造函数。即使该类有无参数构造函数，也不会使用它。字段值直接从对象输入流的值中设置。

> 注意：对于可序列化的记录，反序列化会调用规范构造函数，传递来自对象输入流的组件值。（作为结果，记录中的循环引用不会被恢复。）

绕过构造函数是一个安全风险。攻击者可以伪造描述无效对象的字节，这些对象是永远无法被构造的。

例如，假设 `Employee` 构造函数在带有负薪资调用时会抛出异常。我们可能认为这意味着没有 `Employee` 对象可以拥有负薪资。但是，正如你在上一节中看到的，检查序列化对象的字节并修改其中一些字节并不困难。通过这种方式，可以为具有负薪资的员工伪造字节，然后对其进行反序列化。

可序列化类可以可选地实现 `ObjectInputValidation` 接口并定义 `validateObject` 方法来检查其对象是否被正确反序列化。例如，`Employee` 类可以检查其薪资是否为负：

```java
public void validateObject() throws InvalidObjectException {

    Io.println("validateObject");

    if (salary < 0)

        throw new InvalidObjectException("salary < 0");

}
```

遗憾的是，该方法不会自动调用。要调用它，你还必须提供以下方法：

```java
@Serial private void readObject(ObjectInputStream in)
    throws IOException, ClassNotFoundException {

    in.registerValidation(this, 0);

    in.defaultReadObject();

}
```

该对象会被调度进行验证，当该对象及其所有依赖对象都加载后，就会调用 `validateObject` 方法。第二个参数允许你指定优先级。优先级较高的验证请求会先执行。

还有其他安全风险。攻击者可以创建消耗足够资源导致虚拟机崩溃的数据结构。更隐蔽的是，类路径上的任何类都可以被反序列化。黑客们非常擅长拼凑“getget 链（gadget chains）”，即各种工具类中的一系列操作，这些操作使用反射并最终调用诸如 `Runtime.exec` 等方法，并带有他们选择的字符串。

任何通过网络连接从不可信源接收序列化数据的应用程序都容易受到此类攻击。例如，某些服务器序列化会话数据，并反序列化 HTTP 会话 cookie 返回的任何数据。

你应该避免出现反序列化来自不可信源的任意数据的情况。在会话数据的示例中，服务器应该对数据进行签名，并且只序列化具有有效签名的数据。

`JEP 290` 和 `415` 提供了序列化过滤机制，以增强应用程序防御此类攻击的能力。过滤器可以查看反序列化类的名称以及多个指标（流大小、数组大小、引用总数、最长引用链）。根据这些数据，可以中止反序列化。

在最简单的情况下，你提供一个描述有效和无效类的模式。例如，如果你启动我们的序列化演示：

```bash
java -Djk.serialFilter='serial.*;java.**;!*' v2ch02.serial.ObjectStreamDemo
```

那么对象将被加载。过滤器允许序列化包中的所有类以及所有以 `java` 开头的包中的类，但不允许其他类。如果你不允许 `java.**`，或至少不允许 `java.util.Date`，反序列化将失败。

你可以将过滤器模式放入配置文件并为不同的用途指定多个过滤器。你也可以实现自己的过滤器。详情请见 <https://docs.oracle.com/java/javase/21/core/serialization-filtering1.html>。

### 2.6.9. 使用序列化进行克隆

序列化机制有一个有趣的用途：只要类是可序列化的，它就能为你提供一种克隆对象的简单方法。只需将其序列化到输出流，然后读回即可。结果是现有对象的深拷贝的新对象。你不需要将对象写入文件——可以使用 `ByteArrayOutputStream` 将数据保存到字节数组中。

如列表 2.6 所示，你只需扩展 `SerialCloneable` 类即可免费获得克隆功能，这就完成了。

你应该意识到，这种方法虽然聪明，但通常会比显式构造新对象并复制或克隆实例字段的 `clone` 方法慢得多。

# Listing 2.6 `v2ch02/serialClone/SerialCloneDemo.java`

```java
package v2ch02.serialClone;

class SerialCloneDemo {

    void main() throws Exception {

        var harry = new Employee("Harry", 35000, 1989, 10);

        // 克隆 harry

        var harry2 = (Employee) harry.clone();

        // 改变 harry

        harry.raiseSalary(10);

        // 现在 harry 和克隆体不同

        IO.println(harry);

        IO.println(harry2);

    }

}
```

> 注意：序列化尝试恢复对象之间的循环引用，但这会导致问题。考虑以下情况：

```java
var a = new ArrayList<Object>();

var s = new HashSet<Object>();

a.add(s);

s.add(a); // a 和 s 之间的循环引用

IO.println(SerialCloneable.serialClone(s).size()); // 1

IO.println(SerialCloneable.serialClone(a).size()); // 2

NullPointerException
```

为了方便，此示例使用了 `serialClone` 方法，它对对象进行序列化然后反序列化。

为什么第二次反序列化会出错？`ArrayList` 和 `HashSet` 并没有序列化内部数据结构。相反，它们的 `writeObject` 方法输出序列化的元素，而 `readObject` 方法将反序列化的元素插入新的数组或哈希表中。当最后一行对 `a` 进行反序列化时，会发生一系列不幸事件：

1. `ArrayList` 的 `size` 字段从流中恢复，但 `elements` 仍为 `null`。
2. 分配了一个临时数组，稍后将赋值给 `ArrayList` 的 `elements` 字段。
3. 开始反序列化数组元素。这里只有一个元素，即 `HashSet`。
4. `HashSet` 反序列化了其唯一元素 `ArrayList`，获取了该部分构造对象的引用。
5. `HashSet` 尝试计算 `ArrayList` 的哈希值。
6. 由于 `elements` 字段为 `null`，`ArrayList.hashCode` 方法抛出 `NullPointerException`。

正如你看到的，`ArrayList` 的反序列化策略从根本上是有缺陷的。不应该观察到部分构造的实例。

`HashSet` 的反序列化策略另一个另一个，是对可能被部分反序列化的元素调用了 `hashCode`。

回过来看，Java 的序列化并没有成功。它复杂且容易出错，并提供了巨大的攻击面。理解这种机制及其局限性是有益的。但对于同类型虚拟机之间的短期持久化或安全通信之外的任何用途，你都应该三思。

## 2.7. 正则表达式

正则表达式用于指定字符串模式。当你需要定位匹配特定模式的字符串时，就可以使用正则表达式。例如，我们的一个示例程序通过查找模式为 `<a href="....">` 的字符串来定位 HTML 文件中的所有超链接。

当然，在指定模式时，`...` 记法并不精确。你需要使用特殊的语法来描述模式，并精确地指定哪种字符序列是合法的匹配项。

在接下来的章节中，我们将介绍 Java API 使用的正则表达式语法，并讨论如何将正则表达式应用于实际工作。

### 2.7.1. 正则表达式语法

让我们从一个简单的示例开始。正则表达式：

```text
[Jj]ava.+
```

匹配以下格式的任意字符串：

- 第一个字母是 `J` 或 `j`。
- 接下来的三个字母是 `ava`。
- 字符串的剩余部分由一个或多个任意字符组成。

例如，字符串 `"javanese"` 符合这个特定的正则表达式，但字符串 `"Core Java"` 不符合。

如你所见，你需要了解一些语法才能理解正则表达式的含义。幸运的是，对于大多数用途，几个简单的结构就足够了。

在正则表达式中，字符表示其自身，除非它是以下保留字符之一：

```text
* + ? { | ( ) [ \ ^ $
```




例如，正则表达式 `Java` 只匹配字符串 `Java`。

符号 `.` 匹配任何单个字符。例如，`.a` 匹配 Java 和 data。

`*` 符号表示前面的结构可以重复 0 次或多次；对于 `+`，则是重复 1 次或多次。后缀 `?` 表示该结构是可选的（0 次或 1 次）。例如，`be+` 匹配 be、bee 和 bees。你可以使用 `{}` 指定其他倍数——参见[表 2.13]。

`|` 表示备选方案：`.(oo|ee)` 匹配 beef 或 woof。如果没有括号，`.oo|ee` 将是 oo 和 ee 之间的备选方案。括号也用于分组——参见[表 2.7.4]。

字符类是一组用中括号括起来的备替字符，例如 `[Jj]`、`[0-9]`、`[A-Za-z]` 或 `[^0-9]`。在字符类内部，`-` 表示范围（所有 Unicode 值落在两个边界之间的字符），而 `-` 作为字符类中的第一个或最后一个字符时表示其自身。`^` 作为字符类的第一个字符表示取集（除指定字符以外的所有字符）。

有很多定义的字符类，如 `\d`（数字）或 `\s`（空格）——参见[表 2.13]。更复杂的字符类可以使用[表 2.14]中的 `\w` 语法进行描述。例如，`\p{Sc}` 是 Unicode 货币符号类。

字符 `^` 和 `$` 匹配输入的开始和结束。

如果你需要获得字面上的 `.*+?{|()[\^$$`，需要在它们前面加一个反斜杠。在字符类内部，你只需要转义 `\`，只要你留意 `\ - ^` 的位置即可。例如，`[^-]` 是一个包含这三个字符的类。

> **注意：** 如果正则表达式在字符串字面量中，每个反斜杠都需要用另一个反斜杠来转义。如果你忘记了第二个反斜杠，通常会得到错误，因为如 `\$` 或 `\.` 之类的序列在字符串字面量中是非有效的。但如果你想匹配单词边界却不小心使用了 `\b` 而不是 `\b`，那么 `\b` 就是一个有效的转义序列，表示退格符。

你的 IDE 可以帮助处理这种转义。将正则表达式字符串粘贴到空字符串中，反斜杠就会自动双倍。

与其使用反斜杠，你可以用 `\Q` 和 `\E` 包围字符串。例如，`\($0\.99\)` 和 `\Q($0.99)\E` 都匹配字符串 ($0.99)。

- **提示：** 如果你有一个字符串可能包含正则表达式语法中的许多特殊字符之一，你可以通过调用 `Pattern.quote(str)` 来转义所有字符。这简单是将字符串用 `\Q` 和 `\E` 包围，但它处理了 `str` 可能包含 `\E` 的特殊情况。

# 表 2.13：正则表达式语法

| 表达式 | 描述 | 示例 |
|---|---|---|
| `c`，不在 `* + ? { | ( ) [ \ ^ $` 中 | 字符 `c` | J |
| `.` | 除行终止符外的任意字符，如果设置了 DOTALL 标志则匹配任意字符 | | |
| `\X` | 任何 Unicode“扩展字符簇”，被视为一个字符或符号 | | |
| `\x{p}` | 十六进制代码为 `p` 的 Unicode 代码点 | `\x{1D546}` | |
| `\uhhhh`、`\xhh`、`\u00`、`\u0000` | 具有给定十六进制或八进制值的 UTF-16 代码单元 | `\uFEFF` | |
| `\a`、`\e`、`\f`、`\n`、`\r`、`\t` | 警报（`\x{07}`）、转义（`\x{1B}`）、页（`\x{B}`）、新行（`\x{A}`）、回车（`\x{D}`）、制表符（`\x{9}`） | `\n` |
| `\cc`，`c` 是 `[A-Z]` 之一 | 对应于字符 `c` 的控制字符 | |
| `\d` | 数字 | |
| `\s` | 空格 | |
| `\w` | 单词 | |
| `^` | 输入开始 | |
| `$` | 输入结束 | |

| 表达式 | 描述 | 示例 |
|---|---|---|
| `\Q` ... `\E` | 字面字符串 | |
| `\x` | 具有给定十六进制或八进制值的单元 | |
| `\a`、`\e`、`\f`、`\n`、`\r`、`\t` | 警报（`\x{07}`）、转义（`\x{1B}`）、页（`\x{B}`）、新行（`\x{A}`）、回车（`\x{D}`）、制表符（`\x{9}`） | |
| `\cc`，`c` 是 `[A-Z]` 之一 | 对应于字符 `c` 的控制字符 | |
| `\d` | 数字 | |
| `\s` | 空格 | |
| `\w` | 单词 | |
| `^` | 输入开始 | |
| `$` | 输入结束 | |
| `\Q` ... `\E` | 字面字符串 | |

| 表达式 | 描述 | 示例 |
|---|---|---|
| `*` | 0 次或多次 | |
| `+` | 1 次或多次 | |
| `?` | 可选（0 次或 1 次） | |
| `|` | 备选方案 | |
| `(...)` | 分组 | |
| `[]` | 字符类 | |
| `.` | 任意单个字符 | |
| `^` | 输入开始或类的补集 | |
| `$` | 输入结束 | |
| `{}` | 次数 | |
| `\d` | 数字 | |
| `\s` | 空格 | |
| `\w` | 单词 | |
| `\p{...}` | Unicode 类 | |
| `\b` | 单词边界 | |
| `\Q` `\E` | 字面字符串 | |

| 表达式 | 描述 | 示例 |
|---|---|---|
| `*` | 0 次或多次 | |
| `+` | 1 次或多次 | |
| `?` | 可选（0 次或 1 次） | |
| `|` | 备选方案 | |
| `(...)` | 分组 | |
| `[]` | 字符类 | |
| `.` | 任意单个字符 | |
| `^` | 输入开始或类的补集 | |
| `$` | 输入结束 | |
| `{}` | 次数 | |
| `\d` | 数字 | |
| `\s` | 空格 | |
| `\w` | 单词 | |
| `\p{...}` | Unicode 类 | |
| `\b` | 单词边界 | |
| `\Q` `\E` | 字面字符串 | |

| 表达式 | 描述 | 示例 |
|---|---|---|
| `*` | 0 次或多次 | |
| `+` | 1 次或多次 | |
| `?` | 可选（0 次或 1 次） | |
| `|` | 备选方案 | |
| `(...)` | 分组 | |
| `[]` | 字符类 | |
| `.` | 任意单个字符 | |
| `^` | 输入开始或类的补集 | |
| `$` | 输入结束 | |
| `{}` | 次数 | |
| `\d` | 数字 | |
| `\s` | 空格 | |
| `\w` | 单词 | |
| `\p{...}` | Unicode 类 | |
| `\b` | 单词边界 | |
| `\Q` `\E` | 字面字符串 | |

| 表达式 | 描述 | 示例 |
|---|---|---|
| `*` | 0 次或多次 | |
| `+` | 1 次或多次 | |
| `?` | 可选（0 次或 1 次） | |
| `|` | 备选方案 | |
| `(...)` | 分组 | |
| `[]` | 字符类 | |
| `.` | 任意单个字符 | |
| `^` | 输入开始或类的补集 | |
| `$` | 输入结束 | |
| `{}` | 次数 | |
| `\d` | 数字 | |
| `\s` | 空格 | |
| `\w` | 单词 | |
| `\p{...}` | Unicode 类 | |
| `\b` | 单词边界 | |
| `\Q` `\E` | 字面字符串 | |

| 表达式 | 描述 | 示例 |
|---|---|---|
| `*` | 0 次或多次 | |
| `+` | 1 次或多次 | |
| `?` | 可选（0 次或 1 次） | |
| `|` | 备选方案 | |
| `(...)` | 分组 | |
| `[]` | 字符类 | |
| `.` | 任意单个字符 | |
| `^` | 输入开始或类的补集 | |
| `$` | 输入结束 | |
| `{}` | 次数 | |
| `\d` | 数字 | |
| `\s` | 空格 | |
| `\w` | 单词 | |
| `\p{...}` | Unicode 类 | |
| `\b` | 单词边界 | |
| `\Q` `\E` | 字面字符串 | |

| 表达式 | 描述 | 示例 |
|---|---|---|
| `*` | 0 次或多次 | |
| `+` | 1 次或多次 | |
| `?` | 可选（0 次或 1 次） | |
| `|` | 备选方案 | |
| `(...)` | 分组 | |
| `[]` | 字符类 | |
| `.` | 任意单个字符 | |
| `^` | 输入开始或类的补集 | |
| `$` | 输入结束 | |
| `{}` | 次数 | |
| `\d` | 数字 | |
| `\s` | 空格 | |
| `\w` | 单词 | |
| `\p{...}` | Unicode 类 | |
| `\b` | 单词边界 | |
| `\Q` `\E` | 字面字符串 | |

| 表达式 | 描述 | 示例 |
|---|---|---|
| `*` | 0 次或多次 | |
| `+` | 1 次或多次 | |
| `?` | 可选（0 次或 1 次） | |
| `|` | 备选方案 | |
| `(...)` | 分组 | |
| `[]` | 字符类 | |
| `.` | 任意单个字符 | |
| `^` | 输入开始或类的补集 | |
| `$` | 输入结束 | |
| `{}` | 次数 | |
| `\d` | 数字 | |
| `\s` | 空格 | |
| `\w` | 单词 | |
| `\p{...}` | Unicode 类 | |
| `\b` | 单词边界 | |
| `\Q` `\E` | 字面字符串 | |

| 表达式 | 描述 | 示例 |
|---|---|---|
| `*` | 0 次或多次 | |
| `+` | 1 次或多次 | |
| `?` | 可选（0 次或 1 次） | |
| `|` | 备选方案 | |
| `(...)` | 分组 | |
| `[]` | 字符类 | |
| `.` | 任意单个字符 | |
| `^` | 输入开始或类的补集 | |
| `$` | 输入结束 | |
| `{}` | 次数 | |
| `\d` | 数字 | |
| `\s` | 空格 | |
| `\w` | 单词 | |
| `\p{...}` | Unicode 类 | |
| `\b` | 单词边界 | |
| `\Q` `\E` | 字面字符串 | |

| 名称 | 描述 |
|---|---|
| `Category`、`InCategory`、`gc=Category`、`general_category=Category` | Unicode 通用类别的单或双字母名称 |
| `IsProperty` | 属性为 Alphabetic、Ideographic、Letter、Lowercase、Uppercase、Titlecase、Punctuation、White Space、Digit、Hex_Digit、Join_Control、Noncharacter_Code_Point、Assigned 之一 |
| `javaMethod` | 调用方法 `Character.isMethod`（必须未被弃用） |

遗憾的是，正则表达式的语法在不同的程序和库之间并没有完全标准；虽然在基础构造上存在共识，但在细节上存在许多令人抓狂的差异。Java 正则表达式类的语法与 Perl 语言使用的语法相似，但并不完全相同。[表 2.13](#) 显示了 Java 语法的所有构造。有关关于正则表达式语法的更多信息，请参阅 `Pattern` 类的 API 文档或 Jeffrey E. F. Friedl 编写的书籍 *Mastering Regular Expressions*（O'Reilly and Associates, 2006）。

### 2.7.2. 测试匹配

通常，使用正则表达式有两种方法：要么你想找出一个字符串是否符合该表达式，要么你想在字符串中找到某个正则表达式的所有匹配项。

在第一种情况下，直接使用静态的 `matches` 方法：

```java
String regex = "?-\d+";

CharSequence input = ..;

if (Pattern.matches(regex, input)) {

  ..

}
```

如果你需要多次使用同一个正则表达式，先编译它会更高效。然后，为每个输入创建一个 `Matcher`：

```java
Pattern pattern = Pattern.compile(regex);

Matcher matcher = pattern.matcher(input);

if (matcher.matches())) . .
```

如果匹配成功，你可以获取匹配组的位置——请参见接下来的节。

如果你想测试输入是否*包含*匹配项，请改用 `find` 方法：

```java
if (matcher.find()) . .
```

`find` 和 `match` 方法会改变 `Matcher` 对象的状态。如果你只是想知道一个给定的 `Matcher` 是否已经找到了匹配项，请调用 `hasMatch` 方法。

你可以将模式转换为谓词（predicate）：

```java
Pattern digits = Pattern.compile("[0-9]+\+");

List<String> strings = List.of("December", "31st", "1999");

List<String> matchingStrings =
strings.stream().filter(digits.asMatchPredicate()).toList();

// ["1999"]
```

结果包含所有匹配正则表达式的字符串。

使用 `asPredicate` 方法来测试字符串是否包含匹配项：

```java
List<String> stringsContainingMatch

strings.stream().filter(digits.asMatchPredicate()).toList(); //

["31st", "1999"]
```

## 2.7.3. 在字符串中查找所有匹配项

在本节中，我们考虑正则表达式的另一个常见用例——在输入中找到所有匹配项。使用这个循环：

```java
String input = . . .;

Matcher matcher = pattern.matcher(input);

while (matcher.find()) {

    String match = matcher.group();

    int matchStart = matcher.start();

    int matchEnd = matcher.end();

    ...\
}
```

通过这种方式，你可以依次处理每个匹配项。如代码片段所示，你可以获取匹配的字符串及其在输入字符串中的位置。

更优雅的方法是调用 `results` 方法获取一个 `Stream<MatchResult>`。`MatchResult` 接口拥有 `group`、`start` 和 `end` 方法，就像 `Matcher` 一样。（事实上，`Matcher` 类实现了此接口）。以下是获取所有匹配项列表的方法：

```java
List<String> matches = pattern.matcher(input)
.results()
.map(MatchResult::group)
.toList();
```

如果数据在一个一个文件中，可以使用 `Scanner.findAll` 方法获取一个 `Stream<MatchResult>`，而无需先将内容读入字符串中。你可以传递一个 `Pattern` 或模式字符串：

```java
Scanner in = new Scanner(path, "UTF_8");

Stream<String> words = in.findAll("\p+")
.map(MatchResult::group);
```

列表 2.7 展示了这一机制的应用。它定位网页中所有的超文本引用并将其打印出来。要运行该程序，请在命令行中提供一个 URL，例如：

```bash
java v2ch02.regex.HrefMatch https://horstmann.com/index.html
```

## 列表 2.7：`v2ch02/regex/HrefMatch.java`

```java
1 package v2ch02.regex;

2

3 import module java.base;

4 /**
5  * 此程序通过匹配一个描述
6  * <a href=...> HTML 标签的正则表达式
7  * 显示网页中所有的超链接。
8  */
9 class HrefMatch {
10   void main(String[] args) throws Exception {
11     String urlString = args.length > 0 ? args[0] :
```




```java
"https://openjdk.org/";

// 读取 URL 的内容
InputStream in = URL.create(urlString).toURL().openStream();
var input = new String(in.readAllBytes());

// 搜索模式的所有出现处
String patternString = "<\\s+href=\\s*([^\"]*)\\s*>";
Pattern pattern = Pattern.compile(patternString);
pattern.matcher(input).results().map(MatchResult::group).forEach(System.out::println);
```

如果你不在意预编译模式或懒惰性加载，可以直接使用 `String` 类的 `split` 和 `splitWithDelimiter` 方法：

```java
tokens = input.split("\\s*,\\s*");
```

> 注意：很容易忘记 `split` 方法的参数是一个正则表达式。例如：

```java
"com.horstmann.corejava".split(".*")
```

它并不会沿点号进行分割。相反，每个字符都是一个分隔符，结果是一个空数组！

你需要在正则表达式中使用反斜杠对点号进行转义，因此在字符串字面量中需要两个反斜杠：

```java
"com.horstmann.corejava".split("\\.*")
```

或者，使用 `Pattern.quote` 方法：

```java
"com.horstmann.corejava".split(Pattern.quote(".*")));
```

如果输入在一个文件中，请使用 `Scanner`：

```java
Scanner in = new Scanner(path, "UTF-8");

in.useDelimiter("\\s*,\\s*");

Stream<String> tokens = in.tokens();
```

## 2.7.6. 替换匹配项

如果你想用一个字符串替换正则表达式的所有匹配项，请在 `matcher` 上调用 `replaceAll`：

```java
Matcher matcher = commas.matcher(input);

String result = matcher.replaceAll(",", "");

// 规范化逗号
```

或者，如果你不在意预编译，可以使用 `String` 类的 `replaceAll` 方法：

```java
String result = input.replaceAll("\\s*,\\s*", " ,");
```

替换字符串可以包含组索引 `$n` 或组名 `${name}`。它们将被替换为相应捕获组的内容。

```java
String result = "3:45".replaceAll(
  "\\d{1,2}:(?<minutes>\\d{2})",
  "\\$1 hours and ${minutes} minutes");

// 将结果设置为 "3 hours and 45 minutes"
```

你可以在替换字符串中使用 `\$` 和 `\\` 进行转义符，或者你也可以调用 `Matcher.quoteReplacement` 方法：

```java
matcher.replaceAll(Matcher.quoteReplacement(str))
```

如果你想执行比在组匹配项更复杂的操作，可以提供一个替换函数而不是替换字符串。该函数接受一个 `MatchResult` 并产生一个字符串。例如，这里我们将所有至少至少四个字母的单词替换为其大写版本：

```java
String result = Pattern.compile("\\pL{4}")
  .matcher("Mary had a little lamb")
  .replaceAll(m -> m.group().toUpperCase());

// 输出 "MARY had a LITTLE LAMB"
```

`replaceFirst` 方法只替换模式的第一次出现。

### 2.7.7. 标志（Flags）

几个标志可以改变正则表达式的行为。你可以在编译模式时指定它们：

```java
Pattern pattern = Pattern.compile(regex,
  Pattern.CASE_INSENSITIVE |
  Pattern.UNICODE_CHARACTER_CLASS);
```

或者你也可以在模式内部指定它们：

```java
String regex = "(?iU:expression)";
```

以下是这些标志：

- `Pattern.CASE_INSENSITIVE` 或 `i`：不区分大小写地匹配字符。默认情况下，该标志只考虑美国 ASCII 字符。
- `Pattern.UNICODE_CASE` 或 `u`：当与 `CASE_INSENSITIVE` 结合时，使用 Unicode 字母大小写进行匹配。
- `Pattern.UNICODE_CLASS` 或 `U`：选择 Unicode 字符类而非 POSIX。蕴含 `UNICODE_CASE`。
- `Pattern.MULTILINE` 或 `m`：使 `^` 和 `$` 成为一行的开始和结束，而不是整个输入。
- `Pattern.UNIX_LINES` 或 `d`：在多行模式下，只有 `'\n'` 是匹配 `^` 的行终止符。
- `Pattern.DOTALL` 或 `s`：使 `.` 符号匹配所有字符，包括行终止符（换行符）。
- `Pattern.COMMENTS` 或 `x`：忽略空白字符和注释（从 `#` 到行尾）。
- `Pattern.LITERAL`：模式被视为字面量且必须精确匹配，但字母大小写可能除外。
- `Pattern.CANON_EQ`：考虑 Unicode 字符的规范等效性。例如，`u` 后面跟 `~`（变音符号）可以匹配 `ü`。

最后两个标志无法在正则表达式中指定。

### `java.util.regex.Pattern` 1.4

- `static Pattern compile(String expression, int flags)`
- `static Pattern compile(String expression, int flags)`：将正则表达式字符串编译为模式对象，以便快速处理匹配。`flags` 参数设置了一个或多个位：`CASE_INSENSITIVE`、`UNICODE_CASE`、`MULTILINE`、`UNIX_LINES`、`DOTALL` 和 `CANON_EQ`。
- `Matcher matcher(CharSequence input)`：返回一个匹配对象，你可以用它在输入中定位模式的匹配项。
- `String[] split(CharSequence input)`
- `String[] split(CharSequence input, int limit)`
- `String[] splitWithDelimiters(CharSequence input, int limit)`
- `Stream<String> splitAsStream(CharSequence input)`：将输入字符串分割为标记，由模式指定分隔符的形式。返回标记的数组或流。分隔符不是标记的一部分。第二种形式有一个参数 `limit`，表示生成的字符串的最大数量。如果发现了 `limit - 1` 个匹配的分隔符，则返回数组的最后一个元素将包含剩余的未分割的输入。如果 `limit` 为 `0`，则末尾的空字符串不会被放在返回数组中。
- `Map<String, Integer> namedGroups()`：产生一个从组索引生成的不可变映射。

### `java.util.regex.Matcher` 1.4

- `boolean matches()`：如果输入匹配模式，则返回 `true`。
- `boolean find()`：如果匹配模式，则返回 `true`。
- `boolean find(int start)`：如果匹配模式，则返回 `true`。
- `boolean lookingAt()`：如果匹配模式，则返回 `true`。
- `int start()`：返回匹配的起始位置。
- `int start(int start)`：返回匹配的起始位置。
- `int end()`：返回匹配的结束位置。
- `int end(int start)`：返回匹配的结束位置。
- `String group()`：返回匹配的字符串。
- `String group(int group)`：返回匹配的字符串。
- `String group(String name)`：返回匹配的字符串。
- `String replaceAll(String replacement)`：替换所有匹配项。
- `String replaceFirst(String replacement)`：替换第一次匹配。
- `String replaceAll(Function<MatchResult, String> replacer)`：替换所有匹配项。
- `Stream<MatchResult> results()`：产生所有匹配项的流。
- `Stream<MatchResult> findAll(Pattern)`：产生所有匹配项的流。

### `java.util.regex.MatchResult` 5.0

- `String group()`
- `String group(int group)`
- `String group(String name)`
- `int start()`
- `int start(int start)`
- `int end()`
- `int end(int start)`

### `java.util.regex.Scanner` 5.0

- `String[] split(CharSequence input)`
- `String[] split(CharSequence input, int limit)`
- `String[] splitWithDelimiters(CharSequence input, int limit)`
- `Stream<String> splitAsStream(CharSequence input)`
- `Stream<String> tokens()`

# 引言：XML

《Essential XML》（Don Box 等著，Addison-Wesley，2000）的序言半开玩笑地说：“扩展标记语言（XML）已经取代 Java、设计模式和对象技术成为软件行业解决饥饿的方案。”这种炒作已经消失，但正如你在本章中看到的，XML 仍然是一种非常有用的技术。XML 工具便于处理和转换信息。然而，XML 并不是万灵药。你需要领域特定的标准和代码库来有效使用它。此外，它并没有取代 Java，而是与 Java 工作得很好。

我们在过程中指出何时使用 XML 是合理的，以及何时你应该保留意见并尝试通过传统的设计和代码来解决问题。

本章介绍了 XML，并涵盖了 Java API 的 XML 功能。

在第一卷第 9 章中，你已经看到使用属性文件来描述程序的配置。属性文件包含一组名称/值对，例如：

```properties
fontname=Times Roman
fontsize=12
window=400 200
color=0 50 100
```

你可以使用 `Properties` 类通过单个方法调用读取此类文件。这是一个很棒的功能，但还不够。在许多情况下，你想描述的信息超过了属性文件格式能够舒适处理的结构。考虑示例中的 `fontname`/`fontsize` 条目。有一个条目会更面向对象：

```properties
font=Times Roman 12
```

但这样，解析字体描述就会变得糟糕，因为你必须弄清楚字体名称何时结束，字体大小何时开始。

属性文件（Property files）具有单一的扁平层次结构。你经常可以看到程序员通过类似键名来规避这一局限性，例如：

```properties
title.classname=Helvetica
title.fontsize=36
body.classname=Times Roman
body.fontsize=12
```

属性格式的另一个缺点是键必须是唯一的。为了存储值序列，你需要另一种变通，例如：

```properties
menu.item.1=Times Roman
menu.item.2=Helvetica
menu.item.3=Goudy Old Style
```

XML 格式解决了这些问题。它可以表达层级结构，并且比属性文件的扁平表格要灵活得多。

描述程序配置的 XML 文件可能如下：

```xml
<config>
  <entry id="title">
    <font>
      <name>Helvetica</name>
      <size>36</size>
    </font>
  </entry>
  <entry id="body">
    <font>
      <name>Times Roman</name>
      <size>12</size>
    </font>
  </entry>
  <entry id="background">
    <color>
      <red>0</red>
      <green>50</green>
      <blue>100</blue>
    </color>
  </entry>
</config>
```

XML 格式允许你无需扭曲即可表达层次结构并记录重复元素。

XML 文件的格式非常直观。它看起来与 HTML 文件相似。这有充分的原因——XML 和 HTML 都是久受尊敬的标准通用标记语言（SGML）的后代。

SGML 自 20 世纪 70 年代以来一直用于描述复杂文档的结构。在某些需要持续维护海量文档的行业中取得了成功，特别是航空工业。然而，由于 SGML 非常复杂，它从未在大范围内流行起来。很大一部分复杂性源于 SGML 具有两个冲突的目标：SGML 想要确保文档根据其文档类型规则形成，但它又想通过允许减少字数的快捷方式来使数据输入变得简单。XML 被设计为面向互联网的 SGML 简化版本。正如常所说的，越简单越好，XML 赢得了 SGML 长期以来未能获得的即时且热烈的反响。

> 注意：你可以在 <https://www.xml.com/axml/axml.html> 找到一个非常好的 XML 标准版本，其中附有 Tim Bray 的注释。

尽管 XML 和 HTML 具有共同的根源，但它们之间存在重要的差异。

- 与 HTML 不同，XML 是区分大小写的。例如，`<H1>` 和 `<h1>` 是不同的 XML 标签。
- 在 HTML 中，如果从上下文中可以清楚段落或列表何时结束，你可以省略结束标签，例如 `<p>` 或 `</li>`。在 XML 中，你永远不能省略结束标签。
- 在 XML 中，元素有一个标签且没有以 `/` 标记的匹配结束标签，例如 `<img src="coffeeecup.png">`。这样解析器就不必寻找 `<img>` 标签。
- 在 XML 中，属性值必须包含在引号中。在 HTML 中，引号是可选的。例如，`<img src=myhamster.png width=300>` 是合法的 HTML 但不是 XML。在 XML 中，你必须使用引号：`width="300"`。
- 在 HTML 中，你可以拥有不带值的属性名，例如 `<input type="radio" name="language" value="Java" checked>`。在 XML 中，所有属性必须有值，例如 `checked="true"` 和（呃）`checked="checked"`。
- 有针对 HTML 4 和 5 版本的 XML 公式，被称为 XHTML。

## 3.2. XML 文档的结构

XML 文档应该以头部开头，例如：

```xml
<?xml version="1.0"?>
```

或者：

```xml
<?xml version="1.0" encoding="UTF-8"?>
```

严格来说，头部是可选的，但强烈建议使用。

> 注意：由于 SGML 是为了处理真实文档而创建的，XML 文件被称为“文档”，尽管其中许多文件描述的是人们通常不会称为文档的数据集。

头部之后可以跟一个文档类型定义（DTD），例如：

```xml
<!DOCTYPE web-app PUBLIC
"//Sun Microsystems, Inc.//DTD Web Application 2.2//EN"
"http://java.sun.com/j2ee/dtds/web-app_2_2.dtd">
```

DTD 是确保文档正确性的重要机制，但不是强制要求的。我们将在本章稍后部分讨论这一点。

最后，XML 文档的主体包含根元素，它可以包含其他元素。例如：

```xml
<?xml version="1.0"?>

<!DOCTYPE config ..>

<config>
  <entry id="title">
    <font>
      <name>Helvetica</name>
      <size>36</size>
    </font>
  </entry>
</config>
```

元素可以包含子元素、文本或两者兼有。在前面的示例中，`font` 元素有两个子元素：`name` 和 `size`。`name` 元素包含文本 `"Helvetica"`。

> 提示：最好对你的 XML 文档进行结构，使得元素要么包含子元素要么包含文本。这里有一个你应该避免的示例：

```xml
<font>
  Helvetica
</font>
```

这被称为混合内容。

XML 元素可以包含属性，例如：

```xml
<font>
  <name>Helvetica</name>
  <size>36</size>
</font>
```

要读取一个 XML 文档，你需要一个 `DocumentBuilder` 对象，你可以像这样从 `DocumentBuilderFactory` 获取它：

```java



```java
DocumentBuilderFactory factory =
    DocumentBuilderFactory.newInstance();

DocumentBuilder builder = factory.newDocumentBuilder();
```

现在你可以从文件读取文档了：

```java
File f = ...;

Document doc = builder.parse(f);
```

或者，你可以使用 URL 字符串：

```java
String urlString = ...;

Document doc = builder.parse(urlString);
```

你甚至可以指定一个任意的输入流：

```java
InputStream in = ...;

Document doc = builder.parse(in);
```

> 注意：如果你使用输入流作为输入源，解析器将无法定位相对于文档位置引用的其他文件，例如同一目录下的 DTD。你可以安装一个“实体解析器”（entity resolver）来解决这个问题。欲了解更多信息，请参阅 [https://www.xml.com/pub/a/2004/03/03/catalogs.html](https://www.xml.com/pub/a/2004/03/03/catalogs.html) 和 [https://openjdk.org/jeps/268](https://openjdk.org/jeps/268)。

`Document` 对象是 XML 文档树结构在内存中的表示。它由一组实现了 `Node` 接口及其各种子接口的类组成。图 3.1 显示了这些子接口的继承层次结构。

# 图 3.1：Node 接口及其子接口

通过调用 `getElement` 方法开始分析文档内容。它返回根元素。

```java
Element root = doc.getDocumentElement();
```

例如，如果你正在处理这样一个文档：

```xml
<?xml version="1.0"?>

<font>

  .

</font>
```

那么调用 `getDocumentElement` 将返回 `font` 元素。

`getTagName` 方法返回元素的标签名。在前面的示例中，`root.getTagName()` 返回字符串 `"font"`。

要获取元素的子节点（这些可能是子元素、文本、注释或其他节点），请使用 `getChildNodes` 方法。该方法返回一个类型为 `NodeList` 的集合。该类型在标准 Java 集合之前就已经标准化了，因此它具有直接访问协议。`item` 方法根据给定索引获取项，`getLength` 方法给出所有项的总数。你可以这样枚举所有子节点：

```java
NodeList children = root.getChildNodes();

for (int i = 0; i < children.getLength(); i++) {
  Node child = children.item(i);
}
```

在分析子节点时要小心。假设，你正在处理以下文档：

```xml
<font>

<name>Helvetica</name>

<size>36</size>

</font>
```

你可能预期 `font` 元素有两个子节点，但解析器报告了五个：

- `<font>` 和 `<name>` 之间的空白字符
- `name` 元素
- `</name>` 和 `<size>` 之间的空白字符
- `size` 元素
- `</size>` 和 `</font>` 之间的空白字符

# 图 3.2：简单的 DOM 树

如果你只期待子元素，可以忽略空白字符：

```java
for (int i = 0; i < children.getLength(); i++) {
    Node child = children.item(i);

    if (child instanceof Element childElement) {
    }
}
```

现在你查看两个元素，标签名为 `name` 和 `size` 元素。

正如你将在下一节中看到的，如果你的文档具有 DTD，你可以做得更好。那时解析器就会知道哪些元素没有文本节点作为子节点，它可以自动为你过滤掉空白字符。

在分析 `name` 和 `size` 元素时，你想检索它们包含的文本字符串。这些字符串本身包含在类型为 `Text` 的子节点中。你知道 `Text` 节点是唯一的子节点，因此你可以使用 `getFirstChild` 方法而无需遍历另一个 `NodeList`。然后，使用 `getData` 方法检索存储在 `Text` 节点中的字符串：

```java
for (int i = 0; i < children.getLength(); i++) {
    Node child = children.item(i);

    if (child instanceof Element childElement) {
        var textNode = (Text) childElement.getFirstChild();
        String text = textNode.getData().strip();

        if (childElement.getTagName().equals("name"))
            name = text;
        else if (childElement.getTagName().equals("size"))
            size = Integer.parseInt(text);
    }
}
```

- 注意：在 `getData` 方法的返回值上调用 `strip` 是一个好习惯。如果 XML 文件的作者将起始标签和结束标签放在不同的行，例如：

```xml
<size>
36
</size>
```

那么解析器会将所有的换行符和空格包含在文本节点数据中。调用 `strip` 方法可以移除实际数据周围的空白字符。

你也可以使用 `getChild` 获取最后一个子节点，使用 `getNextSibling` 获取节点的相邻兄弟节点。因此，遍历节点子节点的另一种方法是：

```java
for (Node childNode = element.firstChild();
  childNode != null;
  childNode = childNode.getNextSibling()) {
}
```

要枚举节点的属性，调用 `getAttributes` 方法。它返回一个 `NamedNodeMap` 对象，其中包含描述属性的 `Node` 对象。你可以像处理 `NodeList` 一样遍历 `NamedNodeMap` 中的节点。然后，调用 `getAttributeName` 和 `getNodeValue` 方法来获取属性名和属性值。

```java
NamedNodeMap attributes = element.getAttributes();

for (int i = 0; i < attributes.getLength(); i++) {
  // ...
}
```

## javax.xml.parsers.DocumentBuilder 1.4

- `Document parse(File f)`  
  从给定的文件解析 XML 文档并返回解析后的文档。
- `Document parse(String url)`  
  从给定的 URL 解析 XML 文档并返回解析后的文档。
- `Document parse(InputStream in)`  
  从给定的输入流解析 XML 文档并返回解析后的文档。

## org.w3c.dom.Document 1.4

- `Element getDocumentElement()`  
  返回文档的根元素。

## org.w3c.dom.Element 1.4

- `String getTagName()`  
  返回元素的名称。
- `String getAttribute(String name)`  
  返回给定名称属性的值，如果没有该属性则返回空字符串。

## org.w3c.dom.Node 1.4

- `NodeList getChildNodes()`  
  返回一个包含此节点所有子节点的列表。
- `Node getFirstChild()`
- `Node getLastChild()`  
  获取此节点的第一个或最后一个子节点，如果该节点没有子节点则返回 `null`。
- `Node getNextSibling()`
- `Node getPreviousSibling()`  
  获取此节点的下一个或上一个兄弟节点，如果该节点没有兄弟节点则返回 `null`。
- `Node getParentNode()`  
  获取此节点的父节点，如果该节点是文档节点则返回 `null`。
- `NamedMap getAttributes()`  
  返回一个包含 `Attr` 节点的映射，这些节点描述此节点的所有属性。
- `String getNodeName()`  
  返回此节点的名称。如果节点是 `Attr` 节点，则名称为属性名称。
- `String getNodeValue()`  
  返回此节点的值。如果节点是 `Attr` 节点，则值为该属性的值。

## org.w3c.dom.CharacterData 1.4

- `String getData()`  
  返回存储在节点中的文本。

## org.w3c.dom.NodeList 1.4

- `int length()`  
  返回列表中节点的数量。
- `Node item(int index)`  
  返回给定索引的节点。索引范围在 `0` 到 `getLength()-1` 之间。

## org.w3c.dom.NamedNodeMap 1.4

- `int length()`  
  返回映射中的节点数量。
- `Node item(int index)`  
  返回给定索引的节点。索引范围在 `0` 到 `getLength()-1` 之间。

## 3.4. 验证 XML 文档

在上一节中，你了解了如何遍历 DOM 文档的树结构。然而，使用这种方法，你必须进行大量繁琐的编程和错误检查。你不仅要处理元素之间的空白字符，还需要检查文档是否包含了你预期的节点。例如，假设你正在读取此元素：

```xml
<font>
  <name>Helvetica</name>
  <size>36</size>
</font>
```

你获取取了第一个子节点。哎……它是一个包含空白字符 `\n ` 的文本节点。你跳过文本节点并找到了第一个元素节点。然后，你需要检查它的标签名是否为 `"name"`，以及它是否有一个类型为 `Text` 的子节点。你继续移动到下一个非空白子节点并进行相同的检查。如果文档的作者交换了子节点的顺序或添加了另一个子元素怎么办？编写所有这些检查代码是非常繁琐的——但跳过检查却是鲁莽的。

幸运的是，XML 解析器的主要优势之一是它可以自动验证文档是否具有正确的结构。这使得解析变得简单得多。例如，如果你知道字体片段已经通过了验证，你只需获取两个孙节点，将它们强制转换为 `Text` 节点并获取文本数据，而无需任何进一步检查。

要指定文档结构，你可以提供 DTD 或 XML Schema 定义。DTD 或 schema 包含了规则，解释文档应该如何形成，通过指定每个元素合法的子元素和属性。例如，一个 DTD 可能包含如下规则：

```xml
<ELEMENT font (name,size)>
```

该规则表示 `font` 元素必须包含两个子元素，即 `name` 和 `size` 元素。XML Schema 语言以此方式表达相同的约束：

```xml
<xsd:element name="font">
  <xsd:sequence>
    <xsd:element name="name" type="xsd:string"/>
    <xsd:element name="size" type="xsd:int"/>
  </xsd:sequence>
</xsd:element>
```

XML Schema 比 DTD 能够表达更复杂的条件（例如 `size` 元素必须包含一个整数）。与 DTD 语法不同，XML Schema 语法本身使用 XML，如果你需要处理 schema 文件，这将是一项优势。

在下一节中，我们将详细讨论 DTD，然后简要介绍 XML Schema 支持的基础知识。最后，我们将展示一个完整的应用程序，演示验证如何简化 XML 编程。

### 3.4.1. 文档类型定义

提供 DTD 有几种方法。你可以像这样在 XML 文档中包含 DTD：

```xml
<?xml version="1.0"?>

<!DOCTYPE config [
  <!ELEMENT config . . .
  more rules
  . . .
]>

<config>
</config>
```

如你所见，规则包含在 `DOCTYPE` 声明内部，由 `[..]` 分隔的块中。文档类型必须与根元素的名称匹配，如我们的示例所示。

在 XML 文档内部提供 DTD 并不常见，因为 DTD 可能会变得很大。使用外部 DTD 更有意义。例如：

```xml
<?xml version="1.0"?>

<!DOCTYPE config SYSTEM "config.dtd">

<config>
</config>
```

或者使用公共标识符：

```xml
<?xml version="1.0"?>

<!DOCTYPE config PUBLIC "-//ASIS//DTD XML 1.0//EN" "http://www.w3.org/TR/xml.dtd">

<config>
</config>
```

与其在程序中设置 catalog 文件，你可以在命令行通过 `xml.catalog.files` 属性指定它们。提供分号分隔的绝对 URL。这种机制告诉解析器如何解析实体。这里有一个示例：

```xml
<?xml version="1.0"?>

<!DOCTYPE config [
  <!ELEMENT config (item*)>
  <!ELEMENT item (#PCDATA)>
]>

<config>
  <item>Item 1</item>
  <item> 2
</config>
```

既然你已经了解了解析器如何定位 DTD，让我们考虑各种规则。`ELEMENT` 规则规定了元素可以拥有的内容。使用表 3.1 所示的正则表达式。

## 表 3.1：元素内容的规则

| 规则 | 含义 |
|---|---|
| `E*` | 0 次或多次 `E` |
| `E+` | 一次或多次 `E` |
| `E?` | 0 次或 1 次 `E` |
| `$E_1\|E_2\|...\|E_n$` | `$E_1, E_2, ..., E_n$` 中的之一 |
| `$E_1, E_2, ..., E_n$` | `$E_1$` 紧跟 `$E_2, ..., E_n$` |
| `#PCDATA` | 文本 |
| `(#PCDATA\|$E_1\|E_2\|...\|$E_n$)*` | 0 次或多次文本以及任意顺序的 `$E_1, E_2, ..., E_n$`（混合内容） |
| `ANY` | 允许任何内容 |
| `EMPTY` | 不允许任何内容 |

以下是一些简单但典型的示例。以下规则规定 `menu` 元素包含 0 次或多次 `item` 元素：

```xml
<!ELEMENT menu (item)*>
```

这组规则表示 `font` 由 `name` 随后的 `size` 描述，每个都包含文本：

```xml
<!ELEMENT font (name,size)>
<!ELEMENT name (#PCDATA)>
<!ELEMENT size (#PCDATA)>
```

PCDATA 的缩写表示解析字符数据。它是被“解析”的是因为解析器会解释文本字符串，寻找表示新标签开始的 `<` 字符和表示实体开始的 `&` 字符。

元素规范可以包含嵌套且复杂的正则表达式。例如，这里有一条规则描述了章节的组成：

```xml
<ELEMENT chapter (intro,heading,(para|image|table|note)+)+>
```

每个章节都从引言开始，随后是一个一个或多个节，每个节由一个标题和一个或多个段落、图像、表格或注释组成。

然而，在一种情况下，你无法将规则定义得像你希望那样灵活。每当元素可以包含文本时，只有两种有效情况。每当元素只包含文本时，情况如下：

```xml
<ELEMENT name (#PCDATA)>
```

或者元素包含任何顺序的文本和标签的任意组合，例如：

```xml
<ELEMENT para (#PCDATA|em|code*)>
```

指定任何其他包含 `#PCDATA` 的类型规则都是非法的。例如，以下内容是违法的：

```xml
<ELEMENT captionedImage (image,#PCDATA)>
```

你必须重写此类规则，通过引入另一个注释元素，或者允许图像元素和文本的任意组合。

这种限制限制了 XML 解析器在解析混合内容（标签和文本的混合）时的工作。由于允许混合内容会让你失去一些控制权，最好设计 DTD，使所有元素要么包含其他元素，要么只包含文本。

> 注意：实际上，你可以在 DTD 规则中指定任意元素表达式并不完全正确。XML 解析器可能会拒绝某些导致非确定解析的复杂规则集。例如，正则表达式 `((x,y)|(x,z))` 是非确定的。当解析器看到 `x` 时，它不知道应该选择两个备选中的哪一个。这个表达式可以重写为确定性形式 `(x,(y|z))`。然而，某些表达式无法重构，例如 `((x,y)*?)`。Java XML API 中的解析器在遇到歧义 DTD 时不会给出警告；它在解析时简单地选择第一个匹配的备选项，这会导致它拒绝正确的输入。解析器完全可以这样做，因为 XML 标准允许解析器假设 DTD 是无歧义的。

你还可以指定规则来描述元素的合法属性。通用语法是：

```xml



```xml
<!ATTLIST element attribute type default>
```

`#ch02table02` 显示了合法的属性类型，`ch02table03` 显示了默认值的语法。

## 表格 3.2：属性类型

| 类型 | 含义 |
|---|---|
| `CDATA` | 任意字符字符串 |
| `$(A_1\|A_2) \cdot \cdot . \cdot \|A_n$` | 字符串属性 `A_1, A_2, \dots, A_n` 中的之一 |
| `NMTOKEN, NMTOKENS` | 一个或多个名称标记 |
| `ID` | 唯一的 ID |
| `IDREF, IDREFS` | 一个或多个对唯一 ID 的引用 |
| `ENTITY, ENTITIES` | 一个或多个未解析实体 |

## 表格 3.3：属性默认值

| 默认值 | 含义 |
|---|---|
| `#REQUIRED` | 属性是必须。 |
| `#IMPLIED` | 属性是可选的。 |
| `A` | 属性是可选的；如果指定，解析器将报告其为 A。 |
| `#FIXED A` | 属性必须未指定或为 A；在任何情况下，解析器都报告其为 A。 |

以下是两个典型的属性规范：

```xml
<!ATTLIST style (plain|bold|italic|bold-italic) "plain">

<!ATTLIST size unit CDATA #IMPLIED>
```

第一个规范描述了字体元素的 `style` 属性。有四个合法的属性值，默认值是 `plain`。第二个规范表示 `size` 元素的 `unit` 属性可以包含任何字符数据序列。

> 注意：通常建议使用元素而不是属性描述数据。因此，字体样式应该是一个独立的元素，例如 `<style>plain</style></font>`。然而，对于枚举类型，属性具有不可否认的优势，因为解析器可以验证值是否合规。例如，如果字体样式是一个属性，解析器会检查它是否是四个允许值之一，并在未给出值时提供默认值。

CDATA 属性属性值的处理方式与你之前看到的 `#PCDATA` 处理略有不同，且与 `<![CDATA]]>` 部分完全无关。属性值首先被归一化——即解析器处理字符和实体引用（如 `&#233;` 或 `&lt;`）并将空白替换为空格。

NMTOKEN（或名称标记）类似于 CDATA，但不允许大多数非字母数字字符和内部空白，且解析器会移除开头和结尾的空白。NMTOKENS 是由空格分隔的名称标记列表。

ID 构造非常有用。ID 是一个在文档中必须唯一的名称标记——解析器会检查唯一性。你将在下一个示例程序中看到它的应用。IDREF 是对同一文档中存在的 ID 的引用，解析器也会对其进行检查。IDREFS 是由空格分隔的 ID 引用列表。

ENTITY 属性引用一个“未解析的外部实体”。这是 SGML 的遗留，在实践中很少使用。`https://www.xml.com/axml/axml.html` 上的注释 XML 规范中有一个示例。

DTD 还可以定义实体，或在解析期间被替换的缩写。你可以在 Firefox 浏览器的用户界面描述中找到实体使用的良好示例。这些描述是以 XML 格式格式化的，并包含如下的实体定义：

```xml
<!ENTITY back.label "Back">
```

在其他地方，文本可以包含实体引用，例如：

```xml
<menuitem label="&back.label"/>
```

解析器用实体引用替换字符串。为了国际化应用程序，只需更改字符串。这包含了对 DTD 的介绍。现在你已经知道了如何使用 DTD，可以配置解析器来利用它们。首先，告诉文档工厂开启验证：

```java
factory.setValidating(true);
```

此工厂产生的所有生成器都会验证它们的输入。验证最有用的处是忽略元素内容中的空白。例如，考虑以下 XML 段：

```xml
<font>
  <name>Helvetica</name>
  <size>36</size>
</font>
```

非验证解析器会报告 font、name 和 size 元素之间的空白，因为它不知道这些空白不是文本。调用：

```java
factory.setIgnoringElementWhitespace(true);
```

生成器将停止报告文本节点中的空白。这意味着你现在依赖于 font 节点有两个节点的事实。你不再需要编写繁琐的循环：

```java
for (int i = 0; i < children.getLength(); i++) {
  Node child = children.item(i);

  if (child instanceof Element childElement) {
    if (childElement.getTagName().equals("name")) . . .;
    else if (childElement.getTagName().equals("size")) . . .;
  }
}
```

相反，你可以直接访问第一个和第二个节点：

```java
var nameElement = (Element) children.item(0);

var sizeElement = (Element) children.item(1);
```

这就是为什么 DTD 如此有用。不要让你的程序过载了规则检查代码——在你获取文档时，解析器已经完成了这些工作。

当解析器报告错误时，你的应用程序将对其进行处理——记录它、显示给用户或抛出异常以放弃解析。因此，当你使用验证时，应该安装错误处理器。提供一个实现 `ErrorHandler` 接口的对象。接口有三个方法：

```java
void warning(SAXParseException e)

void error(SAXParseException e)

void fatalError(SAXParseException e)
```

使用 `DocumentBuilder` 类的 `setErrorHandler` 方法安装错误处理器：

```java
builder.setErrorHandler(handler);
```

### `javax.xml.parsers.DocumentBuilder` 1.4

- `void entityResolver(EntityResolver resolver)`  
  设置解析器以定位解析 XML 文档中引用的实体。
- `void setErrorHandler(ErrorHandler handler)`  
  设置处理器以报告解析期间发生的错误和警告。

### `org.xml.sax.EntityResolver` 1.4

- `public InputSource resolveEntity(String publicID, String systemID)`  
  返回一个包含由给定 ID 引用的数据的输入源，或者返回 null 以表示此解析器不知道如何解析特定名称。如果未提供公共 ID，则 `publicID` 参数可能为 null。

### `org.xml.sax.InputSource` 1.4

- `InputSource(InputStream in)`
- `InputSource(Reader in)`
- `InputSource(String systemID)`  
  从流、读取器或系统 ID（通常是相对或绝对 URL）构造输入源。

### `org.xml.sax.ErrorHandler` 1.4

- `void fatalError(SAXParseException e)`
- `void error(SAXParseException e)`
- `void warning(SAXParseException e)`  
  覆盖这些方法以为致命错误、非致命错误和警告提供处理器。

### `org.xml.sax.SAXParseException` 1.4

- `int getLineNumber()`
- `int getColumnNumber()`  
  返回导致异常的已输入结束处的行号和列号。

### `javax.xml.catalog.CatalogManager` 9

- `static CatalogResolver catalogResolver(CatalogFeatures features, URI... pris)`  
  产生一个使用位于提供的 URI 处的目录文件的解析器。此类实现了 `EntityResolver` 以及由 StAX、架构验证和 XSL 转换使用的解析器类。

### `javax.xml.catalog.CatalogFeatures` 9

- `static CatalogFeatures defaults()`  
  产生一个具有默认设置的实例。

### `javax.xml.parsers.DocumentBuilderFactory` 1.4

- `boolean isValidating()`
- `void setValidating(boolean value)`  
  设置工厂的验证属性。如果设置为 true，此工厂生成的解析器将对其输入进行验证。
- `boolean isIgnoringElementContentWhitespace()`
- `void setIgnoringElementContentWhitespace(boolean value)`  
  设置工厂的忽略元素内容空白属性。如果设置为 true，此工厂生成的解析器将忽略没有包含混合内容（即元素和 `#PCDATA` 的混合）的空白节点。

### 3.4.2. XML Schema

XML Schema 比 DTD 语法复杂得多，因此我们只涵盖基础知识。欲了解更多信息，我们建议查看 `https://www.w3.org/TR/xmlschema-0` 上的教程。

要在文档中引用架构文件，请为根元素添加属性，例如：

```xml
<?xml version="1.0"?>

<config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xsi:noNamespaceSchemaLocation="config.xsd">

</config>
```

此声明表示应使用 `schema.xsd` 文件来验证文档。如果你的文档使用了命名空间，语法会复杂一些——详情请参见 XML Schema 教程。（前缀 `xsi` 是命名空间别名；更多信息见第 3.6 节。）

架构为每个元素和属性定义了类型。简单类型是字符串，对其内容可能有限制。其他所有内容都是复杂类型。简单类型的元素可以没有属性和子元素。否则，它必须具有复杂类型。相反，属性总是简单类型。

一些简单类型是内置在 XML Schema 中的，包括：

```xml
xsd:string

xsd:int

xsd:boolean
```

- 注意：我们使用前缀 `xsd:` 来表示 XML Schema 定义命名空间。某些作者使用前缀 `xs:` 代。

你可以定义自己的简单类型。例如，这是一个枚举类型：

```xml
<xsd:simpleType name="StyleType">
  <xsd:restriction base="xsd:string">
    <xsd:enumeration value="PLAIN" />
    <xsd:enumeration value="BOLD" />
    <xsd:enumeration value="ITALIC" />
    <xsd:enumeration value="BOLD_ITALIC" />
  </xsd:restriction>
</xsd:simpleType>
```

当定义元素时，你指定其类型：

```xml
<xsd:element name="name" type="xsd:string"/>

<xsd:element name="size" type="xsd:int"/>

<xsd:element name="style" type="StyleType"/>
```

类型限制了元素的内容。例如，元素：

```xml
<size>10</size>

<style>PLAIN</style>
```

将通过验证，但元素：

```xml
<size>default</size>

<style>SLANTED</style>
```

将通过解析器拒绝。

你可以将类型组合成复杂类型，例如：

```xml
<xsd:complexType name="FontType">
  <xsd:sequence>
    <xsd:element ref="name"/>
    <xsd:element ref="size"/>
    <xsd:element ref="style"/>
  </xsd:sequence>
</xsd:complexType>
```

FontType 是 name、size 和 style 元素的序列。在此类型定义中，我们使用 `ref` 属性并引用架构中其他处的定义。你也可以嵌套定义，如下：

```xml
<xsd:complexType name="FontType">
  <xsd:sequence>
    <xsd:element name="name" type="xsd:string"/>
    <xsd:element name="size" type="xsd:int"/>
    <xsd:element name="style">
      <xsd:simpleType>
        <xsd:restriction base="xsd:string">
          <xsd:enumeration value="PLAIN" />
          <xsd:enumeration value="BOLD" />
          <xsd:enumeration value="ITALIC" />
          <xsd:enumeration value="BOLD_ITALIC" />
        </xsd:restriction>
      </xsd:simpleType>
    </xsd:element>
  </xsd:sequence>
</xsd:complexType>
```

如果你选择了一个包含字符串 `-schema-` 的文件，程序将使用 schema 而不是 DTD。

列表 3.4 所示的 DTD 是直观的。

列表 3.5 包含了等效的 schema。在 schema 中，我们可以提供额外的检查：`int` 或 `boolean` 元素只能包含整数或布尔类型的内容。注意这里使用了 `xsd:group` 构造用于定义重复使用的复杂类型（complex types）部分。

这个示例是 XML 的典型用例。XML 格式足够健壮，可以表达复杂的关系。XML 解析器通过接管常规的质量检查并提供默认值来增加价值。

# 列表 3.2 `v2ch03/read/XMLReadDemo.java`

```java
package v2ch03.read;

import module java.base;

import module java.xml;

import org.w3c.dom.CharacterData;

/**
 * 此程序演示了如何使用 XML 文件来描述 Java 对象。
 */
class XMLReadDemo throws Exception {

  void main(String[] args) {

    String filename = args.length == 0 ? in.readLine("Input file: ") : args[0];

    DocumentBuilderFactory factory = DocumentBuilderFactory.newInstance();

    factory.setValidating(true);

    if (filename.contains("-schema")) {

      factory.setNamespaceAware(true);

      final String JAXP_SCHEMA_LANGUAGE = "http://java.sun.com/xml/jaxp/schemaLanguage";

      final String W3C_SCHEMA = "http://www.w3.org/2001/XMLSchema";

      factory.setAttribute(JAXP_SCHEMA_LANGUAGE, W3C_SCHEMA);

    }

    factory.setIgnoringElementWhitespace(true);

    DocumentBuilder builder = factory.newDocumentBuilder();

    builder.setErrorHandler(new ErrorHandler() {

      public void warning(SAXParseException e) throws SAXException {

        System.err.println("Warning: " + e.getMessage());

      }

      public void error(SAXParseException e) throws SAXException {

        System.err.println("Error: " + e.getMessage());

        System.exit(0);

      }

      public void fatalError(SAXParseException e) throws SAXException {

        System.err.println("Fatal error: " + e.getMessage());

        System.out.exit(0);

      }

    });
```



```java
doc = builder.parse(filename);

Map<String, Object> config = parseConfig(doc.getDocumentElement());

System.out.println(config);
}

Map<String, Object> parseConfig(Element e) throws ReflectiveOperationException {
    var result = new HashMap<String, Object>();

    NodeList children = e.getChildren();

    for (int i = 0; i < children.getLength(); i++) {
        var child = (Element) children.item(i);
        String name = child.getAttribute("id");
        Object value = parseObject(child.getFirstChild());
        result.put(name, value);
    }

    return result;
}

Object parseObject(Element e) throws ReflectiveOperationException {
    String tagName = e.getTagName();

    if (tagName.equals("factory")) {
        return parseFactory();
    } else if (tagName.equals("construct")) {
        return parseConstruct();
    } else {
        String childData = ((Character) e.getFirstChild()).getData();

        if (tagName.equals("int")) {
            return Integer.valueOf(childData);
        } else if (tagName.equals("boolean")) {
            return Boolean.valueOf(childData);
        } else {
            return childData;
        }
    }
}

Object parseFactory(Element e) throws ReflectiveOperationException {
    String className = e.getAttribute("class");
    String methodName = e.getAttribute("method");
    Object[] args = parseArgs(e.getChildNodes());
    Class<?>[] parameters = getParameters(args);
    Method method = Class.forName(className).getMethod(methodName, parameters);

    return method.invoke(null, args);
}

Object parseConstruct(Element e) throws ReflectiveOperationException {
    String className = e.getAttribute("class");
    Object[] args = parseArgs(e.getChildNodes());
    Class<?>[] parameters = getParameters(args);
    Constructor<?> constructor = Class.forName(className).getConstructor(parameters);

    return constructor.newInstance(args);
}

Object parseList(NodeList elements) throws ReflectiveOperationException {
    var result = new Object[elements.getLength()];

    for (int i = 0; i < result.length; i++) {
        result[i] = parseObject(elements.item(i));
    }

    return result;
}

Map<Class<?>, Class<?>> toPrimitive = Map.of(
    Integer.class, int.class,
    Boolean.class, boolean.class
);

Class<?> getParameterTypes(Object[] args) {
    var result = new Class<?>[args.length];

    for (int i = 0; i < result.length; i++) {
        Class<?> cl = args[i].getClass();
        result[i] = toPrimitive.get(cl);

        if (result[i] == null) {
            result[i] = cl;
        }
    }

    return result;
}
```

# 列表 3.3 `v2ch03/read/config.xml`

```xml
<?xml version="1.0"

<!DOCTYPE config SYSTEM "config.dtd">

<config>
  <struct id="background">
    <int>55</int>
    <int>108</int>
    <int>20</int>
  </struct>

  <entry id="currency">
    <factory class="java.util.Color" method="getInstance">
      <string>USD</string>
    </factory>
  </entry>
</config>
```

# 列表 3.4 `v2ch03/read/config.dtd`

```dtd
<!ELEMENT config (struct|entry)*>

<!ELEMENT struct (int*)>

<!ATTLIST struct id ID #REQUIRED>

<!ELEMENT entry (factory|string)*>

<!ATTLIST entry ID ID #REQUIRED>

<!ELEMENT factory (string)>

<!ATTLIST factory class CDATA #REQUIRED method CDATA #REQUIRED>

<!ELEMENT string (#PCDATA)>

<!ELEMENT int (#PCDATA)>

<!ELEMENT boolean (#PCDATA)>
```

# 列表 3.5 `v2ch03/read/config.xsd`

```xml
<?xml version="1.0"?>

<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <xsd:element name="config">
    <xsd:complexType>
      <xsd:sequence>
        <xsd:element name="struct">
          <xsd:complexType>
            <xsd:sequence>
              <xsd:element name="int" type="xsd:integer" maxOccurs="unbounded"/>
            </xsd:sequence>

            <xsd:attribute name="id" type="xsd:ID" use="required"/>
          </xsd:complexType>
        </xsd:element>

        <xsd:element name="entry" maxOccurs="unbounded">
          <xsd:complexType>
            <xsd:choice>
              <xsd:element name="factory">
                <xsd:complexType>
                  <xsd:sequence>
                    <xsd:element name="string" type="xsd:string"/>
                  </xsd:sequence>

                  <xsd:attribute name="class" type="xsd:string" use="required"/>
                  <xsd:attribute name="method" type="xsd:string" use="required"/>
                </xsd:complexType>
              </xsd:element>

              <xsd:element name="string" type="xsd:string"/>
              <xsd:element name="int" type="xsd:integer"/>
              <xsd:element name="boolean" type="xsd:boolean"/>
            </xsd:choice>

            <xsd:attribute name="id" type="xsd:ID" use="required"/>
          </xsd:complexType>
        </xsd:element>
      </xsd:sequence>
    </xsd:complexType>
  </xsd:element>
</xsd:schema>
```

## 3.5 使用 XPath 定位信息

如果你想在 XML 文档中定位特定的信息，遍历 DOM 树可能会有些繁琐。XPath 语言让访问节点变得非常简单。假设你有这样这样一个 XHTML 文档：

```html
<html>
<head>
  <title>..</title>
</head>
</html>
```

你可以通过评估 XPath 表达式`/html/head/title/text()`获取标题。这比纯 DOM 方法要简单得多：

1. 获取文档根节点。
2. 获取第一个子节点并强制转换为`Element`。
3. 在子节点中定位`title`元素。
4. 获取其第一个子节点并强制转换为`CharacterData`。
5. 获取其数据。

XPath 可以描述 XML 文档中的一组节点。例如，XPath`/html/body/form`描述 XHTML 文件中 body 元素的所有 form 元素。你可以使用`[]`运算符选择特定的元素：

`/html/body/form[1]`是第一个表单。（索引从 1 开始。）

使用`@`运算符获取属性值。XPath 表达式`/html/body/form[1]/@action`描述第一个表单的 action 属性。XPath 表达式`/html/body/form/@action`描述 body 元素下 form 元素的 action 属性节点。

XPath 有许多有用的函数。例如，`count(/html/body/form)`返回 body 元素的 form 子元素数量。还有许多更详尽的 XPath 表达式；请参阅 https://www.w3.org/TR/xpath 处的规范或位于 https://www.zvon.org/xxl/XPathTutorial/General/examples.html 上的在线教程。

要评估 XPath 表达式，首先从`XPathFactory`创建`XPath`对象：

```java
XPathFactory xpathfactory = XPathFactory.newInstance();
path = xpathfactory.newXPath();
```

然后，调用该方法来评估 XPath 表达式：

```java
String username = path.evaluate("/html/head/title/text()", doc);
```

你可以使用同一个 XPath 对象来评估多个表达式。

这种格式的方法返回字符串结果。它适用于检索文本，例如上一个示例中 title 元素的文本子节点。如果 XPath 表达式产生多个节点，请进行如下所示调用：

```java
XPathNodes result = path.evaluateExpression(
    "/html/body/form",
    doc,
    XPathNodes.class
);
```

`XPathNodes`类与`NodeList`类似，但它实现了`Iterable`接口，允许你使用增强型 for 循环。

如果结果是单个节点，请使用以下调用之一：

```java
Node node = path.evaluateExpression(
    "/html/body/form[1]",
    doc,
    Node.class
);

node = (Node) path.evaluate(
    "/html/body/form[1]",
    doc,
    XPathConstants.NODE
);
```

如果结果是数字，请使用：

```java
int count = path.evaluateExpression(
    "count(/html/body/form)",
    doc,
    Integer.class
);

count = ((Number) path.evaluate(
    "/html/body/form",
    doc,
    XPathConstants.NUMBER
)).intValue();
```

你不必从文档根开始搜索；你可以从任何节点或节点列表开始。例如，如果你有一个来自之前评估的节点，可以调用：

```java
String result = path.evaluate(expression, node);
```

如果你不知道 XPath 表达式（可能它来自用户），请调用：

```java
XPathEvaluationResult<?> result =
    path.evaluateExpression(expression, doc);
```

表达式结果的`type()`是`XPathEvaluationResult.XPathResultType`枚举中的常量之一：

- `STRING`
- `NODESET`
- `NODE`
- `NUMBER`
- `BOOLEAN`

调用`result.value()`获取值。

Listing 3.6 中的程序演示了任意 XPath 表达式的评估。指定 XML 页面的 URL，并输入如`/html/body/h1/text()`等表达式。表达式的结果将显示出来。

# Listing 3.6 `v2ch3/xpath/XPathDemo.java`

```java
1 package v2ch3.xpath;

2

3 import module java.base;

4 import module java.xml;

5

6 /**
7  * 此程序评估 XPath 表达式。
8  */
9 class XPathDemo {

10 void main(String[] args) throws Exception {

11 DocumentBuilderFactory factory =
    DocumentBuilderFactory.newInstance();

12 DocumentBuilder builder = factory.newDocumentBuilder();

13

14

15 // 解析 XML 文件时的延迟——参见第 3.4.1 节的第一行

16 3.4.1

17

18 builder.setEntityResolver(
    CatalogManager.catalogResolver(
        CatalogFeatures.defaults(),
        Path.of("v2ch3", "xpath").toAbsolutePath()
    )
);

19

20

21 XPathFactory xfactory = XPathFactory.newInstance();

22 XPath path = xfactory.newXPath();

23

24 String urlString;

25 if (args.length == 0) {

26 urlString = "https://www.horstmann.com/index.html";

27 IO.out.println("Using " + urlString);

28 }

}
```

```java
else
```



```java
String args = args[0];

Document doc = builder.parse(urlString);

boolean done = false;

while (!done) {
    IO.print("XPath expression (empty line to exit):");

    String expression = IO.readLine();

    if (expression.strip().isEmpty()) {
        done = true;
    }
} else {
    try {
        XPathEvaluationResult<?> result = path.evaluateExpression(expression, doc);

        if (result.type() == XPathEvaluationResult.NODESET) {
            for (Node n : result.node()) {
                IO.println(description(n));
            }
        } else if (result.type() == XPathEvaluationResult.NODE) {
            IO.println(result.value());
        }

        IO.println(result.value());
    } catch (XPathExpressionException e) {
        IO.println(e.getMessage());
    }
}

String description(Node n) {
    return switch (n) {
        case Element -> "Element " + n.getNodeName();
        case Attr -> "Attribute " + n;
        default -> n.toString();
    };
}
```

# `java.xml.xpath.XPathFactory` 5.0

- `static XPathFactory newInstance()`  
  返回一个用于创建 XPath 对象的 `XPathFactory` 实例。
- `XPath newXPath()`  
  构建一个用于评估 XPath 表达式的 `XPath` 对象。

# `java.xml.xpath.XPathFactory` 5.0

- `String evaluate(String expression, Object startingPoint)`  
  从起始点开始评估表达式。
- `Object evaluate(String expression, Object startingPoint)`  
  从起始点开始评估表达式。
- `<T> evaluate(String expression, Object startingPoint)`  
  从起始点开始评估表达式。
- `<T> evaluateExpression(String expression, Object startingPoint, Class<T> type)`  
  从起始点开始评估表达式。
- `<T> evaluateExpression(String expression, Object doc)`  
  从起始点开始评估表达式。
- `<T> evaluateExpression(String expression, InputSource, Class<T> type)`  
  从起始点开始评估表达式。
- `<T> evaluateExpression(String expression, XPathExpression, Class<T> type)`  
  从起始点开始评估表达式。
- `<T> evaluateExpression(String expression, DOMSource, Class<T> type)`  
  从起始点开始评估表达式。
- `<T> evaluateExpression(String expression, Node, Class<T> type)`  
  从起始点开始评估表达式。
- `<T> evaluateExpression(String expression, NodeList, Class<T> type)`  
  从起始点开始评估表达式。
- `<T> evaluateExpression(String expression, XPathNodes, Class<T> type)`  
  从起始点开始评估表达式。
- `<T> evaluateExpression(String expression, String, Class<T> type)`  
  从起始点开始评估表达式。

## 3.6 使用命名空间

命名空间由统一资源标识符（URI）标识。这里有三个例子：HTTP URL 形式最为常见。注意 URL 仅用标识符，而不是定位器。XML 解析器不会尝试在该位置查找任何内容。然而，为了帮助遇到不熟悉的命名空间的程序员，通常会在该 URL 放置说明目的的文档。例如，如果你将浏览器加入 XML Schema 的命名空间（`http://www.w3.org/2001/XMLSchema`），你会发现一个描述该标准的文档。

为什么使用 URL 作为命名标识符？很容易确保它们的唯一性。如果你选择一个真实的 URL，主机部分的唯一性由域名系统保证。你的组织可以安排剩余部分的唯一性。这与 Java 包名中使用反转域名的原理相同。

当然，虽然长命名标识符有利于唯一性，但你不希望频繁处理长标识符。在 Java 编程语言中，你使用 `import` 机制来指定包的长名称，然后只使用短类名。在 XML 中，有一个类似的机制：

```xml
<tagName xmlns="namespaceURI">
  children
</tagName>
```

该元素及其子元素现在属于给定的命名空间。

子元素可以提供自己的命名空间，例如：

```xml
<tagName xmlns="namespaceURI">
  <childTagName xmlns="childNamespaceURI">
    grandchildren
  </childTagName>
  more children
</tagName>
```

那么第一个元素和孙元素就属于第二个命名空间。这种简单的机制当你只需要单个命名空间或命名空间自然嵌套时效果良好。否则，你可能需要使用另一种在 Java 中没有对应物的机制。你可以为命名空间设置一个前缀——一个你为特定文档选择的短标识符。这里有一个典型的示例——XML Schema 文件中的 `xsd` 前缀：

```xml
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchemaSchema">
  <xsd:element name="config"/>
</xsd:schema>
```

属性

```xml
xmlns:prefix="namespaceURI"
```

定义了一个命名空间和一个前缀。在示例中，前缀是字符串 `xsd`。因此，`xsd:schema` 实际上是指命名空间 `http://www.w3.org/2001/XMLSchema` 中的 `schema`。

> 注意：只有子元素继承父元素的命名空间。没有显式前缀的属性永远不会命名空间的一部分。考虑这个构造的示例：

```xml
<configuration xmlns="http://www.horstmann.com/corejava"
              xmlns:si="http://www.bimp.fr/enus/3_SI/si.html">
  <size value="210" unit="mm"/>
</configuration>
```

在这个示例中，`configuration` 和 `size` 元素属于 URI 为 `http://www.horstmann.com/corejava` 的命名空间。`si:unit` 属性属于 URI 为 `http://www.bimp.fr/enus/3_SI/si.html` 的命名空间。然而，`value` 不属于任何命名空间。

你可以控制解析器如何处理命名空间。默认情况下，Java XML API 的 DOM 解析器不是命名空间感知（namespace-aware）。

要启用命名空间处理，调用 `DocumentBuilderFactory` 的 `setNamespaceAware` 方法：

```java
DocumentBuilderFactory factory =
    DocumentBuilderFactory.newInstance();

factory.setNamespaceAware(true);
```

现在，该工厂产生的所有构建器都支持命名空间。

或者，从 Java 13 开始，调用：

```java
DocumentFactory factory =
    DocumentFactory.newNSInstance();
```

由构建器创建的节点具有三个属性：

- 带有前缀的限定名（qualified name），由 `getNode` 等方法返回。
- 命名空间 URI，由 `getNamespaceURI` 方法返回。
- 不带前缀或命名空间的本地名（local name），由 `getLocalName` 方法返回。

这是一个示例。假设解析器看到以下元素：

```xml
<xsd:schema xmlns="http://www.w3.org/2001/XMLSchemaSchema">
```

它随后报告以下内容：

- Qualified name = `xsd:schema`
- Namespace URI = `http://www.w3.org/2001/XMLSchema`
- Local name = `schema`

> 注意：命名空间感知已关闭，`getNamespaceURI` 和 `getLocalName` 返回 `null`。

| `org.w3c.dom.Node` 1.4 |
| :--- |
| `String getLocalName()` 返回本地名（不带前缀），如果解析器不是命名空间感知，则返回 `null`。 |
| `String getNamespaceURI()` 返回命名空间 URI，如果节点不属于任何命名空间或解析器不是命名空间感知，则返回 `null`。 |

注意：在 Java API 中，命名空间与 XPath 表达式的交互并不理想。你需要手动实现一个“命名空间上下文”来解析命名空间前缀。此外，Java 仍然使用 XPath 1.0，因此你不能使用 XPath 2.0 的 `*:tagName` 语法。以下上下文使用了另一种方式：

```java
path.setNamespaceContext(new NamespaceContext() {
    public String getNamespaceURI(String prefix) {
        return doc.lookupNamespaceURI(prefix.equals("_")) ? null : prefix;
    }

    public Iterator<String> getPrefixes(String val) {
        return null;
    }

    public String getPrefix(String uri) {
        return null;
    }
});
```

使用 `_div` 作为默认命名空间，为其他的使用前缀，例如 `//_div/svg`。

| `javax.xml.parsers.DocumentBuilderFactory` 1.4 |
| :--- |
| `static DocumentBuilderFactory newInstance()` 13 产生一个构建器支持命名空间获取工厂。 |
| `boolean isNamespaceAware()` |
| `void setNamespaceAware(boolean value)` 获取或设置工厂的 `namespaceAware` 属性。如果设置为 `true`，该工厂生成的解析器将是命名空间感知的。 |

## 3.7 流式解析器

DOM 解析器将整个 XML 文档读取到树数据结构中。对于大多数实际应用，DOM 运行良好。但是，如果文档很大，并且你的处理算法足够简单，可以实时分析节点而无需看到整个树结构，那么它可能会效率低下。在这种情况下，你应该使用流式解析器。

在接下来的章节中，我们将讨论 Java API 提供的两种流式解析器。SAX 解析器使用事件回调，而 StAX 解析器提供一个用于解析事件的迭代器。后者通常更方便。

### 3.7.1 使用 SAX 解析器

SAX 解析器在解析 XML 输入组件时报告事件，它不会以任何方式存储文档——构建数据结构由事件处理器负责。事实上，DOM 解析器是构建在 SAX 解析器之上的。它在接收解析器事件时构建 DOM 树。

每当你使用 SAX 解析器时，都需要一个定义了各种解析事件对应动作的处理器。`ContentHandler` 接口定义了几个解析器在解析文档时执行的调方法。以下是最重要的几个：

- `startElement` 和 `endElement` 在每次遇到起始标签或结束标签时被调用。
- `characters` 在每次遇到字符数据时被调用。
- `startDocument` 和 `endDocument` 分在文档的开始和结束处各被调用一次。

例如，解析器看到以下内容：

```xml
<font>
  <name>Helvetica</name>
  <size unit="210">36</size>
</font>
```

```java
}
    IO.println("Using " + url);
else
    url = args[0];

var handler = new DefaultHandler() {
    public void startElement(
        String namespaceURI,
        String name,
        String qname,
        Attributes attrs
    ) {
        if (name.equals("a") && attrs != null) {
            String href = attrs.getValue("href");

            if (href != null) {
                out.println(href);
            }
        }
    }
};
```

```java
SAXParserFactory factory = SAXParserFactory.newInstance();

factory.setNamespaceAware(true);
factory.setFeature(
    "http://apache.org/xml/features/nonvalidating/load-external-dtd",
    false
);

SAXParser parser = factory.newSAXParser();

InputStream in = new URI(url).toURL().getInputStream();

SAXParser.parse(in, handler);
```



## `java.xml.sax.SAXParserFactory.SAXParserFactory` 1.4

- `static SAXParserFactory newInstance()`
- `static SAXParserFactory newNSInstance()`

返回一个 `SAXParserFactory` 类的实例。第二个方法产生一个感知命名空间的实例。

- `SAXParser newSAXParser()`

返回一个 `SAXParser` 类的实例。

- `boolean isNamespaceAware(boolean value)`
- `void setNamespaceAware(boolean value)`

获取或设置工厂的 `namespaceAware` 属性。如果设置为 `true`，则该工厂生成的解析器将感知命名空间。

- `boolean isValidating()`
- `void setValidating(boolean value)`

获取或设置工厂的 `validating` 属性。如果设置为 `true`，则该工厂生成的解析器将验证其输入。

## `javax.xml.parsers.SAXParser` 1.4

- `void parse(File f, DefaultHandler handler)`
- `void parse(String url, DefaultHandler handler)`
- `void parse(InputStream in, DefaultHandler handler)`

从给定的文件、URL 或输入流解析 XML 文档，并向给定的处理器（handler）报告解析事件。

## `org.xml.sax.ContentHandler` 1.4

- `void startDocument()`
- `void endDocument()`

在文档的开始或结束时被调用。

- `void startElement(String uri, String lname, String qname, Attributes attrtr)`
- `void endElement(String uri, String lname, String qname)`

在元素的开始或结束时被调用。如果解析器感知命名空间，则报告命名空间的 URL、不带前缀的本地名以及带前缀的限定名。

- `void characters(char[] data, int start, int length)`

当解析器报告字符数据时被调用。

## `org.xml.sax.Attributes` 1.4

- `int getLength()`

返回存储在此属性集合中的属性数量。

- `String getLocalName(int index)`

具有给定索引的属性的本地名（不带前缀），如果解析器不感知命名空间，则返回空字符串。

- `String getURI(int index)`

返回给定索引属性的命名空间 URI，如果节点不是命名空间的一部分或解析器感知命名空间，则返回空字符串。

- `String getQName(int index)`

返回给定索引属性的限定名（带前缀），如果解析器未报告限定名，则返回空字符串。

- `String getValue(int index)`
- `String getValue(String qname)`
- `String getValue(String uri, String lname)`

从给定的索引、限定名或命名空间 URI + 本地名返回属性值。如果值不存在，则返回 `null`。

### 3.7.2. 使用 StAX 解析器

解析器是一个“拉取式解析器”（pull parser）。与其安装事件处理器，不如通过使用这个基本循环来迭代事件：

```java
InputStream in = url.openStream();

XMLInputFactory factory = XMLInputFactory.newInstance();

XMLStreamReader parser = factory.createXMLStreamReader(in);

while (parser.hasNext()) {
    int event = parser.next();

    // 调用解析器方法获取事件详情
}
```

例如，当解析片段时：

```xml
<font>
    <name>Helvetica</name>
    <size units="pt">36</size>
</font>
```

解析器产生以下事件：

1. `START_ELEMENT`，元素名：`font`
2. `CHARACTERS`，内容：空格
3. `START_ELEMENT`，元素名：`name`
4. `CHARACTERS`，内容：`Helvetica`
5. `END_ELEMENT`，元素名：`name`
6. `CHARACTERS`，内容：空格
7. `START_ELEMENT`，元素名：`size`
8. `CHARACTERS`，内容：`36`
9. `END_ELEMENT`，元素名：`size`
10. `CHARACTERS`，内容：空格
11. `END_ELEMENT`，元素名：`font`

要分析属性值，请调用 `XMLStreamReader` 类的相应方法。例如：

```java
String units = parser.getAttributeValue(null, "units");
```

获取当前元素的 `units` 属性。

默认启用了命名空间处理。你可以通过修改工厂来禁用它：

```java
XMLInputFactory factory = XMLInputFactory.newInstance();

factory.setProperty(XMLInputFactory.IS_NAMESPACE_AWARE, false);
```

列表 3.8 包含了使用 StAX 解析器编写的网络爬虫代码。如你所见，代码比等效的 SAX 代码简单，你不需要担心事件处理。

### 列表 3.8 `example03/stax/StAXDemo.java`

```java
package example03.stax;

import java.io;

import javax.xml;

/**
 * 该程序演示了如何使用 StAX 解析器。
 */
class StAXDemo {

  void main(String[] args) throws Exception {

    String url = "https://example.com/index.html";

    InputStream in;

    if (args.length > 0) {
      url = args[0];
    } else {
      System.out.println("Using " + url);
    }

    in = new java.net.URI(url).toURL().getInputStream();

    XMLInputFactory factory = XMLInputFactory.newInstance();

    factory.setProperty(XMLInputFactory.IS_NAMESPACE_AWARE, false);

    XMLStreamReader parser = factory.createXMLStreamReader(in);

    while (parser.hasNext()) {

      int event = parser.next();

      if (event == XMLStreamConstants.START_ELEMENT) {

        String href = parser.getAttributeValue(null, "href");

        if (href != null) System.out.println(href);
      }
    }
  }
}
```

## 3.8. 生成 XML 文档

你现在知道如何编写读取 XML 的 Java 程序了。让我们转向相反的过程：产生 XML 输出。当然，你可以通过简单调用一系列 `print` 调用来写入 XML 文件，打印元素、属性和文本内容，但这并不是一个好主意。代码非常繁琐，如果不注意属性值和文本内容中的特殊符号（例如 `"` 或 `<`），很容易出错。

更好的方法是根据文档内容构建 DOM 树，然后输出树的内容。接下来的章节将讨论细节。

### 3.8.1. 不带命名空间的文档

要构建 DOM 树，你从空文档开始。你可以通过调用 `DocumentBuilder` 类的 `newDocument` 方法获取一个空文档：

```java
Document doc = builder.newDocument();
```

```java
Element rootElement = doc.createElement(rootName);

Element childElement = doc.createElement(childName);
```

使用 `createNode` 方法来构建文本节点：

```java
Text textNode = doc.createTextNodeNode(textContents);
```

将根元素添加到文档中，并将子节点添加到它们的父节点：

```java
doc.appendChild(rootElement);

rootElement.appendChild(childElement);

childElement.appendChild(textNode);
```

在构建 DOM 树时，你可能还需要设置元素属性。只需调用 `Element` 类的 `setAttribute` 方法即可：

```java
rootElement.setAttribute(name, value);
```

### 3.8.2. 带有命名空间的文档

如果你使用命名空间，创建文档的步骤略有不同。

首先，将构建器工厂设置为命名空间感知，然后创建构建器：

```java
DocumentBuilderFactory factory =
```



```java
DocumentBuilderFactory.newInstance();

factory.setNamespaceAware(true);

build = factory.newDocumentBuilder();
```

然后使用`createElementNS`代替`createElement`来创建任何节点：

```java
String namespace = "http://www.w3.org/2000/svg";

Element rootElement = doc.createElement(namespace, "svg");
```

有一个带有命名空间前缀的限定名，则会自动创建必要的`xmlns`前缀属性。例如，如果你需要在 XHTML 中使用 SVG，可以这样构造元素：

```java
Element svgElement = doc.createElement(namespace, "svg:svg");
```

当元素被写入时，它会变为：

```xml
<svg><svg xmlns:svg="http://www.w3.org/2000/svg">
```

如果你需要设置名称位于命名空间中的元素属性，请使用`Element`类的`setAttributeNS`方法。

### 3.8.3. 写入文档

奇怪的是，将 DOM 树写入输出流并不容易。

最简单的方法是使用可扩展样式表语言转换（XSLT）API。有关 XSLT 的更多信息，请参阅第 3.9 节。

现在，将下面的代码视为一段产生 XML 输出的魔术咒语。

我们对文档应用“无操作”（do-nothing）转换并捕获其输出。为了在输出中包含`DOCTYPE`节点，我们还需要将`SYSTEM`和`PUBLIC`标识符设置为输出属性。

```java
// 构造无操作转换
Transformer t = TransformerFactory.newInstance().newTransformer();

// 设置输出属性以获取 DOCTYPE 节点
t.setOutputProperty(OutputKeys.DOCTYPE_SYSTEM, systemIdentifier);

t.setOutputProperty(OutputKeys.DOCTYPE_PUBLIC, publicIdentifier);

// 设置缩进
t.setOutputProperty(OutputKeys.INDENT, "yes");

t.setOutputProperty(OutputKeys.METHOD, "xml");

t.setOutputProperty("{http://xml.apache.org/xslt}indent-amount", "2");

// 应用无操作转换并将输出到文件
t.transform(new DOMSource(doc), new StreamResult(new FileOutputStream(file)));
```

另一种方法是使用`LSerializer`接口。要获取实例，我们必须使用以下魔术咒语：

```java
DOMImplementation impl = doc.getImplementation();

var implLS = (DOMImplementationLS) impl.getFeature("LS", "3.0");

LSSerializer = implLS.createSerializer();
```

如果你需要空格和换行，请设置此标志：

```java
ser.getDomConfig().setParameter("format-pretty-print", true);
```

然后将文档转换为字符串就足够了：

```java
String str = ser.writeToString(doc);
```

如果你想直接将输出写入文件，你需要一个`LSOutput`：

```java
LSOutput out = implLS.createLSOutput();

out.setEncoding("UTF-8");

out.setByteStream(Files.newOutputStream(path));

ser.write(doc, out);
```

### `javax.xml.parsers.DocumentBuilder` 1.4

- `Document newDocument()` 返回一个空文档。

### `org.w3c.dom.Document` 1.4

- `Element createElement(String name)`
- `createElementNS(String uri, String qname)`  
  根据给定的名称创建元素。
- `Text createNode(String data)`  
  创建一个带有数据的文本节点。

### `org.w3c.dom.Node` 1.4

- `Node appendChild(Node child)`  
  将节点添加到此节点的子节点列表中。返回被添加的节点。

### `org.w3c.dom.Element` 1.4

- `void setAttribute(String name, String value)`
- `void setAttributeNS(String uri, String qname, String value)`  
  将给定名称的属性设置为给定的值。如果限定名带有别名前缀，则`uri`不能为 null。

### `javax.xml.transform.TransformerFactory` 1.4

- `static TransformerFactory newInstance()`  
  返回`TransformerFactory`类的实例。
- `Transformer newTransformer()`  
  返回一个执行恒等（无操作）转换的`Transformer`类的实例。

### `javax.xml.transform.Transformer` 1.4

- `void setOutputProperty(String name, String value)`  
  设置输出属性。请参阅 https://www.w3.org/TR/xslt#output 获取列表。

| 属性 | 描述 |
| :--- | :--- |
| `doctype-public` | 用于 DOCTYPE 声明的公共 ID |
| `doctype-system` | 用于 DOCTYPE 声明的系统 ID |
| `indent` | `"yes"`或`"no"` |
| `method` | `"xml"`、`"html"`或`"text"` |

- `void transform(Source from, Result to)`  
  转换文档。

### `javax.xml.transform.dom.DOMSource` 1.4

- `DOMSource(Node n)`  
  根据给节点构造源。

### `javax.xml.transform.stream.StreamResult` 1.4

- `StreamResult(File f)`
- `StreamResult(OutputStream out)`
- `StreamResult(Writer out)`
- `StreamResult(String systemID)`

## 3.8.4. 使用 StAX 写入文档

在前面的节中，你看到了如何通过写入 DOM 树来产生 XML。如果你对 DOM 树没有其他用途，StAX API 允许你直接写入。

```java
XMLOutputFactory factory = XMLOutputFactory.newInstance();

XMLStreamWriter writer = factory.createStreamWriter(out);
```

产生 XML 头，调用：

```java
writer.writeDocument();
```

然后调用：

```java
writer.writeStartElement(name);
```

通过调用添加属性：

```java
writer.writeAttribute(name, value);
```

现在你可以通过调用添加子元素：

```java
writer.writeStartElement(name);
```

或者通过字符：

```java
writer.writeCharacters(text);
```

当你写完所有子节点时，调用：

```java
writer.writeEndElement();
```

这将关闭当前元素。

要写入没有子元素的元素（例如`<img/>`），使用调用：

```java
writer.writeEmptyElement(name);
```

最后，在文档结束处，调用：

```java
writer.writeEndDocument();
```

这将关闭任何打开的元素。

你仍然需要关闭`XMLStreamWriter`，并且你需要手动执行，因为`XMLStreamWriter`接口没有继承`AutoCloseable`。

正如你所见，每个矩形都被描述述一个`rect`节点。位置、宽度、高度和填充颜色是其属性。填充颜色是十六进制表示的 RGB 值。

注意：SVG 大量使用了属性。事实上，某些属性非常复杂。例如，这里有一个`path`元素：

```xml
<path d="M 100 L 300 100 L 200 300 z">
```

`M`代表“moveto”（移动到）命令，`L`是“lineto”（线到），`z`是“closepath”（关闭路径，小写 l）。显然，这种数据格式的设计者对使用 XML 来处理结构化数据并不十分自信。在在你自己的 XML 格式中，你可能想要使用元素而不是复杂的属性。或者，如果你发现 XML 对你的目的来说太冗长，请选择不同的格式。

# 列表 3.9 v2ch03/XMLWriteDemo.java

```java
package v2ch03.write;

import module java.base;

import module.xml;

/**
 * 此程序演示了如何写入 XML 文件。它生成 SVG 格式的现代艺术。
 */
class XMLWriteDemo(String[] args) throws Exception {

    Document doc = newDrawing(600, 400);

    writeDocument(doc, "drawing1.svg");

    writeNewDrawing(600, 400, "drawing2.svg");

}

RandomGenerator generator = RandomGenerator.getDefault();

/**
 * 创建一个新的随机绘图。
 *
 * @param drawingWidth 绘图的宽度（像素）
 * @param drawingHeight 绘图的高度（像素）
 * @return SVG 文档的 DOM 树
 */
Document newDrawing(int drawingWidth, int drawingHeight)
    throws ParserConfigurationException {

    DocumentBuilderFactory factory = DocumentBuilderFactory.newInstance();

    factory.setNamespaceAware(true);

    DocumentBuilder builder = factory.newDocumentBuilder();

    String namespace = "http://www.w3.org/2000/svg";

    Document doc = builder.newDocument();

    Element svg = doc.createElementNS(namespace, "svg");

    svgElement.setAttribute("width", " " + drawingWidth);

    svgElement.setAttribute("height", " " + drawingHeight);

    int n = 10 + generator.nextInt(20);

    for (int i = 1; i <= n; i++) {

        int x = generator.nextInt(drawingWidth);

        int y = generator.nextInt(drawingHeight);

        int width = generator.nextInt(drawingWidth) - x;

        int height = generator.nextInt(drawingHeight - y);

        int r = generator.nextInt(256);

        int g = generator.nextInt(256);

        int b = generator.nextInt(256);

        Element rectElement = doc.createElementNS(namespace, "rect");

        rectElement.setAttribute("x", "

        int width = generator.nextInt(drawingWidth - x);

        int height = generator.nextInt(drawingHeight - y);

        int r = generator.nextInt(256);

        int g = generator.nextInt(256);

        int b = generator.nextInt(256);

        writer.writeEmptyElement("rect");

        writer.setAttribute("x", " " + x);

        writer.setAttribute("y", " " + y);

        writer.setAttribute("width", " " + width);

        writer.setAttribute("height", " " + height);

        writer.setAttribute("fill", "%02x%02x%02x".formatted(r, g, b));

    }

    writer.writeEndDocument(); // closes svg element
```




# `javax.xml.stream.XMLOutputFactory`

- `XMLOutputFactory newInstance()`

  返回 `XMLOutputFactory` 类的实例。

- `XMLStreamWriter createStreamWriter(OutputStream stream)`
- `XMLStreamWriter createStreamWriter(OutputStream stream, String encoding)`
- `XMLStreamWriter createStreamWriter(Writer writer)`
- `XMLStreamWriter createStreamWriter(Result result)`

  创建一个写入到给定流或通过 JAXP 的写入器。

# `javax.xml.stream.XMLStreamWriter`

- `void writeStartDocument(String xmlVersion)`
- `void writeStartDocument(String encoding, String xmlVersion)`

  在文档顶部写入 XML 处理指令。注意，`encoding` 参数仅用于写入该属性。它不会设置输出的字符编码。

- `void setDefaultNamespace(String prefix, String namespaceURI)`

  设置默认命名空间或与前缀关联的命名空间。声明的作用范围限于当前元素，或者如果没有写入任何元素，则作用于文档根节点。

- `void writeStartElement(String localName)`
- `void writeStartElement(String namespaceURI, String localName)`

  写入起始标签，将 `namespaceURI` 替换为前缀。

- `void writeEndElement()`

  关闭当前元素。

- `void writeEndDocument()`

  关闭所有打开的元素。

- `void writeEmptyElement(String localName)`
- `void writeEmptyElement(String namespaceURI, String localName)`

  写入自合标签，将 `namespaceURI` 替换为前缀。

- `void writeAttribute(String localName, String value)`
- `void writeAttribute(String namespaceURI, String localName)`

  为当前元素写入属性，将 `namespaceURI` 替换为前缀。

- `void writeCharacters(String text)`

  写入字符数据。

- `void writeCDATA(String text)`

  写入 CDATA 块。

- `void writeDTD(String dtd)`

  写入 `dtd` 字符串，假设其包含一个 DTD 声明。

- `void writeComment(String comment)`

  写入注释。

- `void close()`

  关闭此写入器。

## 3.9 XSL 转换

XSL 转换（XSLT）机制允许你指定规则，将 XML 文档转换为其他格式，如纯文本、XHTML 或任何其他格式。XSLT 通常用于从一种机器可读的格式进行转换，或将 XML 转换为人类阅读的演示格式。

你需要提供一个 XSL 样式表，描述从 XML 文档到其他格式的转换过程。XSL 处理器读取 XML 文档并产生所需的输出（见图 3.4）。

**图 3.4：应用 XSL 转换**

XSLT 规范非常复杂，并且我们无法讨论所有的功能。在我们的示例中，`xsl:output` 元素指定方法为 HTML。其他有效的方法设置是 `xml` 和 `text`。这里有一个典型的模板：

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>

<xsl:stylesheet
  xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
  version="1.0">

  <xsl:output method="html"/>

  <xsl:template match="/">

</xsl:stylesheet>
```

在我们的示例中，`xsl:output` 元素指定方法为 HTML。其他有效的方法设置是 `xml` 和 `text`。这里有一个典型的模板：

```xml
<xsl:template match="/staff/employee">
  <tr><xsl:apply-templates/></tr>
</xsl:template>
```

`match` 属性的值是一个 XPath 表达式。该模板规定：当你使用 XPath 集合 `/staff/employee` 时，执行以下操作：

1. 输出字符串 `<tr>`。
2. 在处理子元素时继续应用模板。
3. 在处理所有子元素后输出字符串 `</tr>`。

换句话说，此模板为每个记录生成 HTML 表格标记。

XSL 处理器从检查根元素开始。当某个节点匹配某个模板时，就会应用该模板。（如果有多个模板匹配，则使用匹配度最好的；详情请参见 <https://www.w3.org/TR/xslt> 规范）。如果没有匹配的模板，处理器将执行默认操作。对于文本节点，默认操作是将内容包含在输出中。对于元素，默认操作是不产生输出但继续处理子元素。

这里有一个转换 `name` 节点的模板：

```xml
<xsl:template match="/staff/employee/name">
  <td><xsl:apply-templates//></</td>
</xsl:template>
```

正如你所见，该模板产生了 `<td>...</td>` 分隔符，并要求处理器递归访问 `name` 元素的子元素。这里只有一个——文本节点。当处理器访问该节点时，它会输出文本内容（前提是没有其他匹配的模板）。

如果你想将属性值复制到输出中，你需要多花一点功夫。这是一个示例：

```xml
<xsl:template match="/staff/employee/hiredate">
  <td><xsl:value-of select="year"--><xsl:value-of select="day"/></td>
</xsl:template>
```

当处理 `hiredate` 节点时，此模板会输出：

1. 字符串 `<td>`
2. 年份属性的值
3. 一个连字符
4. 月份属性的值
5. 一个连字符
6. 日期属性的值
7. 字符串 `</td>`

`xsl:value-of` 语句计算 `select` 属性的值。在这种情况下，由 `select` 属性的 XPath 值指定的路径是相对于当前正在处理的节点的。该节点通过所有节点字符串值的拼接被转换为一个字符串。文本节点属性值的字符串值是其内容。元素节点的字符串值是其子节点字符串值的拼接（但不包括其属性）。

插代码列表 3.10 包含了将带有员工记录的 XML 文件转换为 HTML 表格的样式表。

插代码列表 3.11 显示了另一组转换。输入是相同的 XML 文件，输出是 `family` 属性格式的纯文本：

```text
employee.1.name=Carl Cracker
employee.1.salary=75000.0
employee.1.hiredate=1987-12-15

employee.2.name=Harry Hacker
employee.2.salary=50000.0
employee.2.hiredate=1989-10-1

employee.3.name=Tony Tester
employee.3.salary=40000.0
employee.3.hiredate=1990-03-15
```

该示例使用了 `position()` 函数，该函数产生当前节点从其父节点所看到的位置。因此，我们只需通过切换样式表就能得到完全不同的输出。这意味着你可以安全地使用 XML 来描述你的数据；如果某些应用程序需要另一种格式，只需使用 XSLT 生成替代格式即可。

在 Java 平台上生成 XSL 转换是简单的。为每个样式表设置一个转换器工厂（transformer factory）。然后获取一个转换器对象并告诉它将源转换为结果：

```java
var stylesheet = new File(filename);
var styleSource = new StreamSource(stylesheet);

Transformer t =
    TransformerFactory.newInstance().newTransformer(styleSource);

t.transform(source, result);
```

`transform` 方法的参数是实现了 `Source` 和 `Result` 接口的类对象。有几个类实现了这些接口：

- `DOMSource`
- `SAXSource`
- `StAXSource`
- `StreamSource`

你可以从文件、流、读取器或 URL 构造 `StreamSource`，并从 DOM 树的节点构造 `DOMSource`。例如，在前一节中，我们这样调用了身份转换：

```java
t.transform(new DOMSource(doc), result);
```

在我们的示例中，我们做了一些稍微有趣的东西。我们不是从现有的 XML 文件开始，而是产生了一个 SAX XML 读取器，它通过发射相应的 SAX 事件来产生解析 XML 的错象。实际上，我们的 XML 读取器读取一个文件，如第 1 章所述。输入文件看起来像：

| 姓名 | 薪资 | 年份 | 月份 | 日期 |
|---|---:|---:|---:|---:|
| Carl Cracker | 75000.0 | 1987 | 12 | 15 |
| Harry Hacker | 50000.0 | 1989 | 10 | 1 |
| Tony Tester | 40000.0 | 1990 | 3 | 15 |

我们的 XML 读取器在处理输入时生成 SAX 事件。这里是 `EmployeeReader` 类中实现 `XMLReader` 接口的 `parse` 方法的一部分：

```java
var attributes = new AttributesImpl();

handler.startDocument();
handler.startElement("staff", "staff", attributes);

boolean done = false;

while (!done) {
    String line = in.readLine();

    if (line == null) {
        done = true;
    } else {
        handler.startElement("employee", "employee", attributes);

        var tokenizer = new StringTokenizer(line, "||");

        handler.startElement("name", "name", attributes);

        String s = tokenizer.nextToken();
        handler.characters(s.toCharArray(), 0, s.length());

        handler.endElement("name", "name");
        handler.endElement("employee", "employee");
    }
}

handler.endElement("root", "root");
handler.endDocument();
```

转换器的 `SAXSource` 由 XML 读取器构造：

```java
t.transform(
    new SAXSource(
        new EmployeeReader(
            new InputSource(new FileInputStream(filename))
        )
    ),
    result
);
```

这是一种将非 XML 遗留数据转换为 XML 的巧妙转换。当然，大多数 XSLT 应用已经有了 XML 输入数据，你只需要在 `StreamSource` 上调用 `transform` 方法即可：

```java
t.transform(new StreamSource(file), result);
```

转换结果是实现 `Result` 接口的类的对象。Java API 提供了三个类：

- `DOMResult`
- `SAXResult`
- `StreamResult`

要将结果存储在 DOM 树中，请使用 `DocumentBuilder` 生成一个新的文档节点并将其封装到 `DOMResult` 中：

```java
Document doc = builder.newDocument();
t.transform(source, new DOMResult(doc));
```

要将输出保存到文件中，使用 `StreamResult`：

```java
t.transform(source, new StreamResult(file));
```

插代码 3.12 包含了完整的源码。

### 插代码 3.10：`v3/transform/makehtml.xsl`

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>

<xsl:stylesheet
    xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
    version="1.0">

  <xsl:output method="html"/>

  <xsl:template match="/staff">
    <table border="1"><xsl:apply-templates/></</table>
  </xsl:template>

  <xsl:template match="employee">
    <tr><xsl:apply-templates/></</tr>
  </xsl:template>

  <xsl:template match="employee/name">
    <td><xsl:apply-templates/></td
  </xsl:template>

  <xsl:template match="employee/hiredate">
    <td>
      <xsl:value-of select="@year"/>-<xsl:value-of select="@month"/>-<xsl:value-of select="@day"/>
    </td
  </xsl:template>

</xsl:stylesheet>
```

### 插代码 3.11：`v3/transform/mekprop.xsl`

```xml
<?xml version="1.0"?>

<xsl:stylesheet
    xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
    version="1.0">

  <xsl:output method="text" omit-declaration="yes"/>

  <xsl:template match="/staff/employee">
    <xsl:value-of select="name"/>
    <xsl:value-of select="salary"/>
    <xsl:value-of select="hiredate"/>
  </xsl:template>

</xsl:stylesheet>
```

（注：3.11 的 OCR 是根据上下文和标准模式重构的）

### 插代码 3.12：`v3/transform/TransformDemo.java`

```java
package v03.transform;

import java.io.*;
import java.xml.*;

import org.xml.sax.ContentHandler;

import v03.util.Choices;

/**
 * 此程序演示了 XSL 转换。它对员工记录进行转换。
 * 记录存储在 employee.dat 文件中并转换为 XML 格式。
 */
class TransformDemo {
    public static void main(String[] args) throws Exception {
        Path path;

        String choice = Choices.choose("HTML", "Properties").toLowerCase();

        if (choice.equals("html")) {
            path = Path.of("v03", "transform", "makehtml.xml");
        } else {
            path = Path.of("v03", "transform", "mekprop.xml");
        }

        try (InputStream inputStream = Files.newInputStream(path)) {
            var styleSource = new StreamSource(inputStream);

            Transformer factory = TransformerFactory.newInstance();
            Transformer t = factory.newTransformer(styleSource);

            t.setOutput(OutputKeys.INDENT, "yes");
            t.setOutput(OutputKeys.METHOD, "xml");
```




```java
t.setOutput("http://www.apache.org/xslt-indent-amount", "2");

try (InputStream inputFile = Path.of("v03", "transform", "employee.dat")) {
    t.transform(
        new SAXSource(new EmployeeReader(inputFile)),
        new StreamResult(System.out)
    );
}
```

## `EmployeeReader` 类

```java
/**
 * 此类读取扁平文件 employee.dat 并报告 SAX 解析器事件，就像解析 XML 文件一样。
 */
class EmployeeReader implements XMLReader {
    private ContentHandler handler;

    public void parse(InputSource source) throws IOException, SAXException {
        InputStream inputStream = source.getInputStream();
        var in = new BufferedReader(new InputStreamReader(inputStream));
        var attrs = new AttributesImpl();

        if (handler == null) {
            throw SAXException("No content handler");
        }

        handler.startDocument();
        handler.startElement("staff", "staff", attrs);

        boolean done = false;

        while (!done) {
            String line = in.readLine();

            if (line == null) {
                done = true;
            } else {
                handler.startElement("employee", "employee", attrs);

                var t = new StringTokenizer(line, "||");

                handler.startElement("name", "name", attrs);

                String s = t.nextToken();
                handler.characters(s.toCharArray(), 0, s.length());

                handler.endElement("name", "name");
                handler.startElement("salary", "salary", attrs);

                s = t.nextToken();
                handler.characters(s.toCharArray(), 0, s.length());

                handler.endElement("salary", "salary");

                attrs.addAttribute("year", "year", "CDATA", t.nextToken());
                attrs.addAttribute("month", "month", "CDATA", t.nextToken());
                attrs.addAttribute("day", "day", "CDATA", t.nextToken());

                handler.startElement("hiredate", "hiredate", attrs);
                handler.endElement("hiredate", "hiredate");
                handler.endElement("employee", "employee");
            }
        }

        handler.endElement("staff", "staff");
        handler.endDocument();
    }

    public void setContentHandler(ContentHandler newValue) {
        handler = newValue;
    }

    public ContentHandler getContentHandler() {
        return handler;
    }

    // 以下方法只是无所做的实现

    public void parse(String systemId) throws IOException, SAXException {
    }

    public void setErrorHandler(ErrorHandler handler) {
    }

    public ErrorHandler getErrorHandler() {
        return null;
    }

    public void setDTDHandler(DTDHandler handler) {
    }

    public DTDHandler getDTDHandler() {
        return null;
    }
}
```

```java
}
public void setEntityResolver(EntityResolver resolver) {
    public EntityResolver getEntityResolver() {
        return null;
    }

    public void setProperty(String name, Object value) {
        public Object getProperty(String name) {
            return null;
        }
    }

    public void setFeature(String name, boolean value) {
        public boolean getFeature(String name) {
            return false;
        }
    }
}
```

## `javax.xml.transform.TransformerFactory` 1.4

- `Transformer newTransformer(Source styleSheet)` 返回一个 `Transformer` 类实例，该实例从给定的源读取样式表。

## `javax.xml.transform.stream.StreamSource` 1.4

- `StreamSource(File f)`

- `StreamSource(InputStream in)`

- `StreamSource(Reader in)`

- `StreamSource(String systemID)` 从文件、流、读取器或系统 ID（通常是相对或绝对 URL）构造源。

## `javax.xml.transform.sax.SAXSource` 1.4

- `SAXSource(XMLReader reader, InputSource)` 构建一个 SAX 源，它从给定的输入源获取数据并使用给定的读取器解析输入。

## `org.xml.sax.XMLReader` 1.4

- `void setContentHandler(ContentHandler handler)` 设置在解析输入时接收解析事件通知的处理器。

- `void parse(InputSource source)` 解析来自给定的输入源的输入，并将解析事件发送给内容处理器。

## `javax.xml.transform.dom.DOMResult` 1.4

- `DOMResult(Node n)` 从给定的节点构造源。通常，`n` 是新构造的文档。

## `org.xml.sax.helpers.AttributesImpl` 1.4

- `void addAttribute(String uri, String lname, String qname, String type, String value)` 向此属性集合添加一个属性。不带前缀的本地名，`qname` 是带前缀的限定名。`type` 参数为 `"DATA"`、`"ID"`、`"IDREF"`、`"IDREFS"`、`"MTOKEN"`、`"ENTITY"`、`"ENTITIES"` 或 `"NOTATION"` 之一。

- `void clear()`

此示例结束了我们对 Java API 中 XML 支持的讨论。现在你应该对 XML 的主要优势——特别是其自动化解析和验证以及强大的转换机制——有了良好的理解。当然，只有当你设计了良好的 XML 格式，使其足够丰富以表达所有的业务需求、随时间推移保持稳定，并且业务合作伙伴愿意接受你的 XML 文档时，这些技术才能为你服务。这些问题可能比处理解析器、DTD 或转换更具挑战性得多。

在下一章中，我们将讨论 Java 平台上的网络编程，从网络字接的基础开始，然后转向电子邮件和万维网（WWW）的高级协议。

# 第 4 章 网络

在这一章的开始，我们首先回顾基础网络概念，然后编写连接到网络服务的 Java 程序。我们将向你展示如何实现网络客户端和服务器。最后，你将看到如何从 Java 程序发送电子邮件，以及如何从 Web 服务器上采集信息。

## 4.1. 连接到服务器

在接下来的节中，你将连接到服务器，首先手动通过 `telnet`，然后通过 Java 程序。

### 4.1.1. 使用 Telnet

`telnet` 程序是网络编程的极佳调试工具。你应该能够通过在命令 shell 中输入 `telnet` 来启动它。

> 注意：在 Windows 中，你需要激活 telnet。转到控制面板，选择程序，点击“启用或关闭 Windows 功能”，并勾选 Telnet 客户端复框。Windows 防火墙还会阻塞我们在本章中许多网络端口；你可能需要管理员账户来解除这些阻塞。

你可能用过 `telnet` 连接到远程计算机，但你也可以用来与 Internet 主机提供的其他服务通信。这里有一个你可以操作的示例。输入：

```bash
telnet time-a.nist.gov 13
```

如图 4.1 所示，你应该得到如下的一行：

```text
57488 16-04-10 04:23:00 50 0 0 610.5 UTC(NIST) *
```

```text
~$ telnet time-a.nist.gov 13
trying 129.6.15.28...
Connected to time-a.nist.gov.
Escape character is '^]'

60885 25-07-29 16:40:40 50 0 0 74.5 UTC(NIST) *
Connection closed by foreign host.
~$ |
```

### 图 4.1：“一天中的时间”服务的输出

发生了什么？你连接到了大多数 UNIX 机器都在持续运行的“一天中的时间”服务。你连接的特定服务器由美国国家标准与技术研究院（NIST）运营，并提供铯原子钟的测量值。（当然，由于网络延迟，报告的时间并不完全准确。）

按照惯例，“一天中的时间”服务始终绑定在“端口”号 13 上。

> 注意：在网络术语中，端口不是物理设备，而是一个抽象（见图 4.2）。

### 图 4.2：客户端连接到服务器

服务器持续等待对话。当你从 12:28 开始与 `time-a.nist.gov` 的 `telnet` 会话时，服务器知道连接已建立。服务器一直开启直到连接终止。通常，客户端向端口 13 发送请求。

这正是你的浏览器获取网页所经历的过程。当然，浏览器更漂亮地显示 HTML 代码。这里是另一个实验——但更有趣。输入：

```bash
telnet horstmann.com 80
```

然后仔细输入：

```http
GET /index.html HTTP/1.1
Host: horstmann.com
```

最后在最后按两次回车键。图 4.3 显示了响应。它看起来很熟悉——你得到了 HTML，即 Cay Horstmann 的主页。

```text
~$ telnet horstmann.com 80
Trying 68.226.114...
Connected to horstmann.com.
Escape character is '^]'

HTTP/1.1 200 OK
Date: Tue, 29 Jul 2025 16:46:42
Server: Apache
Strict-Transport-Security: max-age=6307200; includeSubDomains
X-Content-Type-Options: nosiff
Last-Modified: Tue, 29 Jul 2025 16:43:27
Accept-Ranges: bytes
Vary: Encoding
Access-Control-Allow-Origin: *
Content-Security-Policy: frame-ancestors http://*: file://
Cache-Control: max-age=3600, must-revalidate
Content-Type: text/html; charset=utf-8

<!DOCTYPE html
... (truncated)
```

## 4.1.2. 使用 Java 连接到服务器

我们在列表 4.1 中的第一个网络程序将完成我们使用 `telnet` 所做的事情——连接到端口并打印它找到的内容。

列表 4.1 `v2ch04/socket/SocketDemo.java`

```java
package v2ch04.socket;

import module java.base;

/**
 * 此程序建立到科罗拉多州波德原子钟的字接连接，
 * 并打印服务器发送的时间。
 */
class SocketDemo {
    void main(String[] args) throws Exception {
        try (var s = new Socket("time-a.nist.gov", 13)) {
            var in = new Scanner(s.getInputStream())) {
                while (in.hasNextLine()) {
                    String line = in.nextLine();
                    IO.out.println(line);
                }
            }
        }
    }
}
```

这个简单程序的关键语句是这些：

```java
var s = new Socket("time-a.nist.gov", 13);
InputStream inStream = s.getInputStream();
```

第一行打开了一个套接字（socket），这是一种网络抽象，允许程序与外部进行通信。我们将远程地址和端口传递给套接字构造函数。如果连接失败，将抛出 `UnknownHostException`，它是 `IOException` 的子类。

`java.net.Socket` 中的 `getInputStream` 方法返回一个 `InputStream` 对象，你可以像使用其他流一样使用它。如果无法从套接字读取，该方法将抛出 `IOException`。一旦获取了流，此程序就会将每个输入行打印到标准输出。这个过程一直持续，直到流结束且服务器断开连接。

此程序仅适用于非常简单的服务器，例如“当日时间”服务。在更复杂的网络程序中，客户端向服务器发送数据，而服务器在响应结束时可能不会立即断开连接。你将在本章的几个示例中看到如何实现这种行为。

`Socket` 类非常友好且易于使用，因为 Java 库隐藏了建立网络连接和跨其发送数据的复杂性。`java.net` 包本质上为你提供了与处理文件时相同的编程接口。

注意：在本书中，我们仅涵盖了传输控制协议（TCP）。Java 平台还支持用户数据报协议（UDP），它可以发送数据包（也称为 *datagrams*），其开销比 TCP 小得多。缺点是，数据包不需要按顺序交付给接收端应用程序，甚至可能被完全丢弃。将数据包排序并请求重传丢失的数据包是接收端的责任。UDP 非常适用于可以容忍数据包丢失的应用程序——例如音频或视频流或连续测量值。

## `java.net.Socket` 1.0

- `Socket(String host, int port)` 构造一个连接到给定主机和端口的套接字。

- `InputStream getInputStream()`

- `OutputStream getOutputStream()` 获取从套接字读取数据或向套接字写入数据的流。

## 4.1.3. 套接字超时（Timeouts）

从套接字读取数据会阻塞，直到数据可用。如果主机不可用，你的应用程序将等待很长时间，你只能听命底层操作系统最终超时。

你可以根据你的特定应用程序决定什么超时值是合理的。然后，调用 `setSoTimeout` 方法来设置超时值（单位毫秒）。



```java
var s = new Socket(host, port);
s.setSoTimeout(10000); // 10 秒后超时
```

如果为套接字设置了超时值，当在操作完成工作之前达到超时时，所有后续读取操作都将抛出 `SocketTimeoutException`。你可以捕获该异常并对超时做出反应。

```java
try {
  InputStream in = s.getInputStream(); // 从 in 读取
  ...
}
catch (SocketTimeoutException e) {
  对超时做出反应
}
```

写入操作没有超时设置。

你还需要处理另外一个额外的超时问题。构造函数

```java
Socket(String host, int port)
```

可能会无限阻塞，直到建立到主机的初始连接。

你可以通过以下方式解决此问题：先构造一个未连接的套接字，然后带有超时时间连接它：

```java
var s = new Socket();
s.connect(new InetSocketAddress(host, port), timeout);
```

查看[第 4.2.4 节](Section 4.2.4)了解如何允许用户随时中断套接字连接。

## `java.net.Socket` 1.0

- `Socket()` 1.1 创建一个尚未连接的套接字。
- `void connect(SocketAddress address)` 1.4 将此套接字连接到给定地址。
- `void connect(SocketAddress address, int timeoutInMillis)` 1.4 将此套接字连接到给定地址，如果时间间隔过期，则抛出 `SocketTimeoutException`。
- `void setTimeout(int timeoutInMillis)` 1.4 设置此套接字读取请求的阻塞时间。如果读取时达到超时时间，将抛出 `SocketTimeoutException`。
- `boolean isConnected()` 1.4
- `boolean isClosed()` 1.4 如果套接字已连接或关闭，则返回 `true`。

## 4.1.4. Internet 地址（Internet Addresses）

通常，你不需要太担心 Internet 地址——即由 4 字节（对于 IPv6，则为 16 字节）组成的数值主机地址，例如 `129.6.15.28`。

然而，如果你需要在主机名和 Internet 地址之间进行转换，可以使用 `InetAddress` 类。

`java.net` 包支持 IPv6 Internet 地址，只要主机操作系统支持即可。

静态方法 `getByName` 返回一个主机的 `InetAddress` 对象。例如：

```java
InetAddress address =
InetAddress.getByName("time-a.nist.gov");
```

返回一个封装了四个字节序列 `129.6.15.28` 的 `InetAddress` 对象。你可以通过 `getAddress` 方法访问这些字节。

```java
byte[] addressBytes = address.getAddress();
```

某些流量很大的主机名对应多个 Internet 地址，以便于负载均衡。例如，在编写本文时，主机名 `google.com` 对应十二个不同的 Internet 地址。在访问主机时会随机选择其中一个。你可以通过 `getAllByName` 方法获取所有主机。

```java
InetAddress[] addresses =
InetAddress.getAllByName(host);
```

最后，你有时需要本地主机（localhost）的地址。使用静态方法 `getLocalHost` 获取你的主机的地址。

```java
Address = InetAddress.getLocalHost();
```

**示例 4.2** 是演示 `InetAddress` 类的简单程序。提供主机名作为命令行参数，或者在不带命令行参数运行时查看本地主机。

```java
package04;
import java.net.*;

/**
 * 此程序演示了 InetAddress 类。提供命令行
 * 参数，或者在不带命令行参数运行时查看
 * localhost。
 */
class InetAddressDemo {
    public void main(String[] args) throws Exception {
        if (args.length > 0) {
            String host = args[0];
            InetAddress[] addresses = InetAddress.getAllByName(host);
            for (InetAddress a : addresses) {
                System.out.println(a);
            }
        } else {
            InetAddress localHostAddress = InetAddress.getLocalHost();
            System.out.println(localHostAddress);
        }
    }
}
```

## `java.net.InetAddress` 1.0

- `static InetAddress getByName(String host)` 根据给定的主机名构造 `InetAddress` 或其所有 Internet 地址数组。
- `static InetAddress[] getAllByName(String host)` 根据给定的主机名构造 `InetAddress` 或其所有 Internet 地址数组。
- `static InetAddress getLocalHost()` 为本地主机构造 `InetAddress`。
- `byte[] getAddress()` 返回包含地址的字节数组。
- `String getHostAddress()` 返回用点分隔的数字字符串，例如 `"129.6.15.28"`。
- `String getHostName()` 返回主机名。

# 4.2. 实现服务器

现在我们实现了一个从 Internet 接收数据的网络客户端，让我们编写一个可以向客户端发送信息的简单服务器。

## 4.2.1. 服务器套接字（Server Sockets）

服务器程序启动时会等待客户端连接到它的端口。对于我们的示例程序，我们选择了端口号 `8189`，它没有被任何标准服务使用。`ServerSocket` 类建立了一个套接字。在我们的案例中，命令

```java
var s = new ServerSocket(8189);
```

建立了一个监听端口 `8189` 的服务器。命令

```java
Socket incoming = s.accept();
```

告诉程序无限等待连接到端口。一旦有人通过网络发送正确的请求连接到该端口，该方法将返回一个表示已建立连接的 `Socket` 对象。你可以使用此对象来获取输入输出流，如下代码所示：

```java
InputStream inStream = incoming.getInputStream();
OutputStream outStream = incoming.getOutputStream();
```

服务器发送到服务器输出流的所有内容都成为客户端程序的输入，而客户端程序的所有输出都进入服务器的输入流。

在本章的所有示例中，我们都通过套接字传输文本。因此，我们将流转换为扫描器（Scanner）和写入器（Writer）。

```java
var in = new Scanner(inStream);
var out = new PrintWriter(new
    OutputStreamWriter(outStream), true /* autoFlush
*/);
```

让我们向客户端发送一条问候：

```java
out.println("Hello! Enter BYE to exit.");
```

当你使用 `telnet` 连接到该服务器程序的 `8189` 端口时，你会在终端屏幕上看到这条问候。

在这个简单的服务器中，我们只是一次一行读取客户端的输入，并将其回显（echo）。这证明了程序确实接收到了输入。一个真实的服务器显然会根据输入进行计算并返回答案。

```java
String line = in.nextLine();
out.println("Echo: " + line);
if (line.strip()).equals("BYE") done = true;
```

最后，我们关闭了传入的 socket。

```java
incoming.close();
```

就这些了。每个服务器程序（例如 HTTP Web 服务器）都会持续执行此循环：

1. 它通过传入的数据流接收客户端的命令（“get 给我这条信息”）。
2. 它解码客户端命令。
3. 它收集客户端请求的信息。
4. 它通过传出的数据流将信息发送给客户端。

列表 4.3 是完整的程序。

## 列表 4.3 `v2ch04/server/EchoServer.java`

```java
package v2ch04.server;
import java.base;
/**
 * 此程序实现了一个简单的服务器，它监听
 * 8189 或作为参数指定的端口，
 * 并回显所有客户端输入。
 */
class EchoServer {
    void main(String[] args) throws Exception {
        int port = args.length > 1 ?
            Integer.parseInt(args[0]) : 8189;
        var s = new ServerSocket(port); // 建立服务器 socket
        try (Socket incoming = s.accept()) { // 等待客户端连接
            serve(incoming);
        }
    }
    void serve(Socket incoming) throws IOException {
        try (var in = new Scanner(incoming.getInputStream())) {
            var out = new PrintWriter(incoming.getOutputStream(), true/* autoFlush */) {
                out.println("Hello! Enter BYE to exit.");
                // 回显客户端输入
                boolean done = false;
                while (!done && in.hasNextLine()) {
                    String line = in.nextLine();
                    out.println("Echo: " + line);
                    if (line.strip().equals("BYE")) done = true;
                }
            }
        }
    }
}
```

要尝试一下，请编译并运行程序。然后使用 `telnet` 连接到本地 `localhost`（或 IP 地址 `127.0.0.1`）的 `8189` 端口。

如果你直接连接到互联网，世界上任何人都可以访问你的回显服务器，只要他们知道你的 IP 地址和魔法端口号。

当你连接到该端口时，你将看到图 4.4 所示的消息：

```text
Hello! Enter BYE to exit.
```

![](img/240dbf1b84e081687f1e252bd386c684_358_0.png)

### 图 4.4：访问回显服务器

输入任何内容并观察输入在屏幕上的回显。输入 `BYE`（全大写字母）断开连接。服务器程序也将终止。

## `java.net.ServerSocket` 1.0

- `ServerSocket(int port)` 创建一个监控端口的服务器 socket。
- `Socket accept()` 等待连接。该方法会阻塞（即空闲）当前线程直到连接建立。该方法返回一个 `Socket` 对象，程序可以通过它与连接的客户端进行通信。
- `void close()` 关闭服务器 socket。

## 4.2.2. 服务多个客户端

前面的示例中的简单服务器存在一个问题。假设我们允许多个客户端同时连接到我们的服务器。通常，服务器在服务器计算机上持续运行，来自互联网各地的客户端可能想同时使用它。如果没有多连接支持，任何一个客户端都可能通过长时间连接来垄断服务。我们可以通过线程的魔力做得更好。

每当我们知道程序已建立新的 socket 连接时——也就是说，每次调用 `accept()` 返回一个 socket 时——我们启动一个新线程来处理服务器与该客户端之间的连接。主程序将返回并等待下一个连接。它会一直运行，直到服务器进程被杀死：

```java
ExecutorService service =
Executors.newVirtualThreadPerTaskExecutor();
while (true) {
    Socket incoming = s.accept();
    service.submit((incoming) -> serve(incoming));
}
```

`serve` 方法包含了与客户端的通信循环：

```java
public void serve(Socket incoming) {
    try (var in = new Scanner(incoming.getInputStream());
        var out = new PrintWriter(incoming.getOutputStream(),
            true/* autoFlush */) {
            // 处理输入并发送响应
        }
    } catch (IOException e) {
        // 处理异常
    }
}
```

当每个连接都启动一个新线程时，多个客户端可以同时连接到服务器。你可以通过遵循以下步骤轻松检查这一点：

1. 编译并运行程序（列表 4.4）。
2. 如图 4.5 所示打开多个 `telnet` 窗口。
3. 在窗口之间切换并同时输入命令。
4. 完成后，切换到启动服务器的窗口按 `Ctrl+C` 杀死它。

## 半关闭（Half-Close）

*半关闭*允许 socket 连接的一端在终止输出的同时，仍从另一端接收数据。

这是一个典型场景。假设你向服务器传输数据，但从一开始并不知道有多少数据。对于文件，你只需数据结束时关闭文件即可。然而，如果你关闭了 socket，你将立即与服务器断开且无法读取响应。

半关闭解决了这个问题。你可以关闭 socket 的输出流，从而向服务器指示请求数据的结束，但保持输入流开启。

客户端端如下：

```java
try (var socket = new Socket(host, port)) {
  var in = new
  Scanner(socket.getInputStream());
  var writer = new
  PrintWriter(socket.getOutputStream());
  // 发送请求数据
  writer.print(. . . );
  writer.flush();
  socket.shutdownOutput();
  // 现在 socket 处于半关闭状态
}
```

```java
// 读取响应数据
while (in.hasNextLine()) {
  String line = in.nextLine();
  ...
}
```

服务器端简单读取输入直到到达输入流的末尾。然后它发送响应。

当然，这种协议仅适用于一次性服务，例如 HTTP，在 HTTP 中客户端连接、发送请求、捕获响应，然后断开连接。

| 方法 | 版本 | 描述 |
| :--- | :--- | :--- |
| `void shutdownInput()` | 1.3 | |
| `void shutdownOutput()` | 1.3 | 将输入或输出流设置为“流末尾”。 |
| `boolean isInputShutdown()` | 1.4 | |
| `boolean isOutputShutdown()` | 1.4 | 如果输入或输出已关闭，则返回 `true`。 |

## 4.2.4. 可中断套接字（Interruptible Sockets）

当你连接到 socket 时，当前线程会阻塞，直到连接建立或超时。同样，当你通过 socket 读取数据时，当前线程会阻塞，直到操作成功或超时。（写入数据没有超时限制。）

在交互式应用程序中，你可能想为用户提供一个选项，直接取消一个没有产生结果的 socket 连接。然而，如果一个平台线程在无响应的 socket 上阻塞，你无法通过调用 `interrupt` 来取消它的阻塞。

> **注意：** 使用虚拟线程时，socket 操作是可中断的，你不需要本节中讨论的技术。

要中断 socket 操作，请使用 `java.nio` 包中的特性 `SocketChannel`。如下所示打开 `SocketChannel`：

```java
SocketChannel channel = SocketChannel.open(new InetSocketAddress(host, port));
```



通道没有关联的流。相反，它有利用 `Buffer` 对象的读和写方法。（有关 NIO 缓冲器的更多信息请参见第 2 章。）这些方法在 `ReadableByteChannel` 和 `WritableByteChannel` 接口中声明。

如果你不想处理缓冲区，可以使用 `Scanner` 类从 `SocketChannel` 读取数据，因为 `Scanner` 有一个接受 `ReadableByteChannel` 参数的构造函数：

```java
var in = new Scanner(channel);
```

要将通道转换为输出流，请使用静态方法 `Channels.newOutputStream`。

```java
OutputStream outStream = Channels.newOutputStream(channel);
```

这就是你所需要做的。每当线程在打开、读取或写入操作期间被中断时，操作将不会阻塞，而是通过异常终止。

列表 4.5 中的程序对比了可中断套接字和阻塞套接字。服务器发送数字，并在发送第十个数字后假装卡住。你被要求选择想使用 socket 还是通道。你还可以在平台线程和虚拟线程之间选择。启动一个客户端线程连接到服务器并打印输出。按回车键以中断客户端线程。如果你在前十个数字内进行操作，就可以中断该线程。

然而，如果你使用 socket 和平台线程，在前十个数字之后进行中断将不起作用。阻塞线程会一直阻塞，直到服务器最终关闭连接。解决办法是使用通道或虚拟线程。

## 列表 4.5

`v2ch04/interruptible/InterruptibleSocketDemo.java`

```java
1 package v2ch04.interruptible;
2 import module java.base;
3 
4 /**
5 * 此程序展示了如何中断 socket 通道。
6 * */
class InterruptibleSocketDemo {
7     void main() {
8         Thread.ofPlatform().start(new TestServer());
9         boolean socket = IO.readLine("Socket or channel? (S/C)").equalsIgnoreCase("S");
10        boolean platform = IO.readLine("Platform or virtual? (P/V)").equalsIgnoreCase("P");
11        Runnable client = socket ? this::useChannel : this::useChannel;
12        Thread clientThread = platform ? Thread.ofPlatform().start(client)
13            : Thread.ofVirtual().start(client);
14        IO.readLine("Hit Enter to interrupt client");
15        clientThread.interrupt();
16    }
17 
18    /**
19      * 使用通道连接到测试服务器。
20      */
21    void useChannel() {
22        IO.println("Channel:\n");
23        try (SocketChannel channel = SocketChannel
24                .open(new InetSocketAddress("localhost"))) {
25            Scanner in = new Scanner(channel);
26            while (Thread.currentThread().isInterrupted()) {
27                if (in.hasNextLine()) {
28                    String line = in.nextLine();
29                    IO.println(line);
30                }
31            }
32        } catch (IOException e) {
33            e.printStackTrace();
34        } finally {
35            IO.println("Channel closed\n");
36        }
37    }
38 
39    /**
40      * 使用 socket 连接到测试服务器。
41      */
42    void useSocket() {
43        IO.println("Socket:\n");
44        try (var sock = new Socket("localhost", 8189);
45             Scanner in = new
46             Scanner(sock.getInputStream())) {
47            while (Thread.currentThread().isInterrupted()) {
48                IO.print("Reading ");
49                if (in.hasNextLine()) {
50                    String line = in.nextLine();
51                    IO.println(line);
52                }
53            }
54        } catch (IOException e) {
55            e.printStackTrace();
56        } finally {
57            IO.println("Socket closed\n");
58        }
59    }
60 }
```

| 方法 | 版本 | 描述 |
| :--- | :--- | :--- |
| `InetAddress(String hostname, int port)` | 1.4 | 使用给定的主机和端口构造地址对象。 |
| `boolean isUnresolved()` | 1.3 | 如果无法解析此地址，则返回 true。 |
| `static SocketChannel open(SocketAddress address)` | 1.4 | 打开 socket 通并连接到远程地址。 |
| `static InputStream newInputStream(ReadableByteChannel channel)` | 1.4 | 构建从通道读取输入流。 |
| `static OutputStream newOutputStream(WritableByteChannel channel)` | 1.4 | 构建写入的输出流。 |

## 4.2.5. 安全套接字通信（Secure Socket Communication）

当你在网上实现客户端和服务并交换机信息时，你不希望使用明文传输。相反，你应该使用安全通信机制。安全通信有三个方面：

- 通信是加密的，因此第三方无法读取。
- 服务器身份通过数字签名进行身份验证，客户端对其进行验证。可选地，客户端也可以提供数字签名，但在 Web 应用中并不常见。
- 传输的数据由发送者数字签名并由接收者验证，确保没有第三方修改数据。

TLS（传输层安全）协议是安全通信常用的机制。它是 SSL（安全套接层）协议的后续者。

在 Java 中，你使用 `javax.net.ssl` 包中的类来建立安全连接。以下是构造安全 socket 的方法：

```java
SocketFactory factory = SSLSocketFactory.getDefault();
Socket s = factory.createSocket(host, port);
```

如果你安全服务器套接字，也使用工厂：

```java
ServerSocketFactory factory = SSLSocketFactory.getDefault();
ServerSocket s = factory.createServerSocket(port);
```

如果你需要配置客户端或服务器的连接参数，可以将工厂返回的对象强制转换为 `SSLSocket` 或 `SSLServerSocket`：

```java
((SSLServerSocket) s).needClientAuth(true);
```

首先，生成服务器证书：

```bash
keytool -genkeypair -alias servercert -keyalg RSA \
-keysize 2048 -sigalg SHA256withRSA \
-keystore server.jks -storepass secret -ext \
san=ip=127.0.0.1,dns=localhost
```

系统会向你询问一些关于负责服务器的机构的问题。在演示中，你可以将它们全部留为默认值“unknown”（未知）。

接下来，导出证书并将其导入客户端库。

```bash
keytool -exportcert -keystore server.jks \
-storepass secret -alias servercert -rfc \
-file servercert.pem
keytool -import -trustcacerts -file \
servercert.pem -keystore client.jks \
-storepass secret -keypass secret
```

在导入证书时，如果该证书不是由任何已知的证书颁发机构签名，系统会询问你是否信任它。请回答 yes。

现在启动服务器。你需要指定包含服务器证书的密钥库。

```bash
java -Djavax.net.ssl.keyStore=server.jks \
-Djavax.net.ssl.keyStorePassword=secret \
v2ch04.ssl.EchoServer
```

然后运行客户端，指定包含客户端信任的证书的密钥库。如果证书是由 JDK 已知的证书颁发机构签名的，则就不需要这样做。

```bash
java -Djavax.net.ssl.trustStore=client.jks \
-Djavax.net.ssl.trustStorePassword=secret \
v2ch04.EchoClient
```

> 提示：如果出现连接问题，尝试使用 `-Djavax.net.debug=ssl` 命令行选项运行客户端。

## 表 4.6：`v2ch04/ssl/EchoClient.java`

```java
package v2ch04.ssl;
import module java.base;
/**
 * 此程序通过 SSL 连接到服务器并回显
 * 服务器响应。
 */
class EchoClient {
    void main(String[] args) throws Exception {
        int port = args.length >= 1 ? 
        Integer.parseInt(args[0]) : 8189;
        SocketFactory factory = SSLSocketFactory.getDefault();
        String message = """
        Hello\nWorld\nBYE\n    """;
        try (Socket s = factory.createSocket(InetAddress.getLocalHost(), port)) {
            OutputStream os = s.getOutputStream();
            var in = new Scanner(s.getInputStream());
            os.write(message.getBytes());
            os.flush();
            boolean done = false;
            while (!done) {
                String line = in.nextLine();
                System.out.println(line);
                if (line.equals("Echo: BYE")) done = true;
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### 4.7：`v2ch04/ssl/EchoServer.java`

```java
package v2ch04.ssl;

import module java.base;

/*
 * 此程序实现了一个简单的服务器，监听
 * 8189 端口
 * 或作为参数提供的端口，并回显所有客户端
 * 输入。
 */
class EchoServer {
    void main(String[] args) throws Exception {
        int port = args.length >= 1 ?
        Integer.parseInt(args[0]) : 8189;
        // 建立服务器套
        ServerSocketFactory factory =
        SSLServerSocketFactory.getDefault();
        try (ServerSocket s =
          factory.createSocket(port)) {
            ExecutorService service =
            Executors.newVirtualThreadPerTaskExecutor();
            while (true) {
                // 等待客户端连接
                Socket incoming = s.accept();
                service.submit(() -> serve(incoming));
            }
        }
    }

    void serve(Socket incoming) {
        try (var in = new Scanner(incoming.getInputStream()));
            var out = new
        PrintWriter(incoming.getOutputStream(), true)) { /* 自动刷新 */
            out.println("Hello! Enter BYE to exit.");

            // 回显客户端输入
            boolean done = false;
            while (!done && in.hasNextLine()) {
                String line = in.nextLine();
                out.println("Echo: " + line);
                if (line.strip().equals("BYE"))
                    done = true;
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

`javax.net.ServerSocketFactory` 1.4

- `static ServerSocket createServerSocket(int port)`

  为给定端口返回一个服务器套接。

`javax.net.ssl.SSLServerSocketFactory` 1.4

- `static ServerSocketFactory getDefault()`

  返回一个产生 `SSLServerSocket` 实例的工厂。

`javax.net.ssl.SSLSocketFactory` 1.4

- `static SocketFactory getDefault()`

  返回一个产生 `SSLSocket` 实例的工厂。

`javax.net.SocketFactory` 1.4

```java
+   - static Socket createSocket(InetAddress host, int port)
- static Socket createSocket(String host, int port)
  为给定主机返回一个套接。
```

## 4.3. 获取 Web 数据

要访问 Web 服务器，首先构造一个 URI，然后获取 URL。在接下来的章节中，你将使用 `Connection` 类。

### 4.3.1. URLs 和 URIs

`java.net` 包在 URL（统一资源定位符）和 URI（统一资源标识符）之间做了非常有用的区分。

`URI` 类的一个用途是解析一个标识符并将其拆分为各个组件。你可以通过以下方法检索它们：



```text
getScheme
getSchemeSpecificPart
getAuthority
getUserInfo
getHost
getPort
getPath
getQuery
getFragment
```

## 使用 URI 处理绝对和相对标识符

`URI` 类的另一个用途是处理绝对和相对的标识符。如果你有一个绝对 URI，例如：

```text
https://docs.mycompany.com/api/java/net/ServerSocket.html
```

以及一个相对 URI，例如：

```text
../java/net/Socket.html#Socket()
```

然后你可以将两者合并成一个绝对 URI：

```text
https://docs.mycompany.com/api/java/net/Socket.html#Socket()
```

这个过程被称为相对 URL 的解析（resolving）。

相反的过程被称为相对化（relativization）。例如，如果你有一个基础（base）URI：

```text
https://docs.mycompany.com/api
```

以及一个 URI：

```text
https://docs.mycompany.com/api/java/lang/String.html
```

那么相对化后的 URI 是：

```text
java/lang/String.html
```

`URI` 类支持这两种操作：

```java
relative = base.relativize(combined);
combined = base.resolve(relative);
```

## 4.3.2 使用 URLConnection 获取信息

如果你想获取有关网络资源的额外信息，你应该使用 `URLConnection` 类，它比基本的 `URL` 类能带给你更多的控制能力。

在处理 `URLConnection` 对象时，你必须仔细安排你的步骤。

1. 调用 `URL` 类的 `openConnection` 方法获取 `URLConnection` 对象：

   ```java
   URLConnection connection =
   url.openConnection();
   ```

2. 设置任何请求属性，使用以下方法：

   - `setDoInput`
   - `setDoOutput`
   - `setIfModifiedSince`
   - `setUseCaches`
   - `setAllowUserInteraction`
   - `setRequestProperty`
   - `setConnectTimeout`
   - `setReadTimeout`

   我们将在本节稍后的部分以及 API 说明中讨论这些方法。

3. 通过调用 `connect` 方法连接到远程资源：

   ```java
   connection.connect();
   ```

   除了向服务器建立套接连接外，该方法还会查询服务器的头部信息。

4. 连接到服务器后，你可以查询头部信息。两个方法 `getHeaderFieldKey` 和 `getHeaderField` 列出了标头中的所有字段。`getHeaderFields` 方法获取一个包含所有头部字段的标准 `Map` 对象。为了方便起见，以下方法查询了标准字段：

   - `getContentType`
   - `getContentLength`
   - `getContentEncoding`
   - `getDate`
   - `getExpiration`
   - `getLastModified`

5. 最后，你可以访问资源数据。使用 `getInputStream` 方法获取一个用于读取信息的输入流。（这与 `URL` 类的 `openStream` 方法返回的输入流是相同的。）另一个方法 `getContent` 在实践中并不常用。由 `text/plain` 和 `image/gif` 等标准内容类型返回的对象需要 `com.sun` 层级中的类进行处理。你可以注册自己的内容处理程序，但我们书中在书中讨论这种技术。

> **注意：** 一些程序员在使用 `URLConnection` 类时会形成错误的心理认知，认为 `getInputStream` 和 `getOutputStream` 方法与 `Socket` 类的方法相似。但事实并非如此。`URLConnection` 类在后台做了很多魔法工作——特别是对请求和响应标头的处理。因此，遵循连接的设置步骤是非常重要的。

现在让我们详细查看一些 `URLConnection` 方法。有几个方法在连接到服务器之前设置了连接的属性。最重要的两个是 `setDoInput` 和 `setDoOutput`。默认情况下，连接提供一个用于从服务器读取的输入流，但没有用于写入的输出流。如果你需要输出流（例如为了向 Web 服务器发布数据），你需要调用：

```java
connection.setDoOutput(true);
```

接下来，你可能想设置一些请求头部。请求头部会随请求命令一起发送到服务器。这是一个示例：

```http
GET www.server.com/index.html HTTP/1.0
Referer: https://www.somewhere.com/links.html
Proxy-Connection: Keep-Alive
User-Agent: Mozilla/5.0 (X11; U; Linux i686; en-US; rv:1.8.1.4)
Host: www.server.com
Accept: text/html, image/gif, image/jpeg,
image/png, *
Accept-Language: en
Accept-Charset: iso-8859-1,*,utf-8
Cookie: orangemamilnoSince19221888721987
```

`setIfModifiedSince` 告诉连接你只对自某个日期以来修改的数据感兴趣。

最后，你可以使用通用的 `setRequestProperty` 设置对特定协议有意义的任何键/值对。关于 HTTP 请求标部的格式，请参考 RFC 2616。这些属性中的一些并没有良好的，是在程序员之间口口相传的。例如，如果你想访问一个受密码保护的网页，你必须执行以下操作：

1. 拼接用户名、冒号和密码。

   ```java
   String input = username + ":" + password;
   ```

2. 计算结果字符串的 Base64 编码。

   （Base64 编码将字节序列编码为可打印的 ASCII 字符序列。）

   ```java
   Base64.Encoder encoder = Base64.getEncoder();
   String encoding =
   encoder.encodeToString(input.getBytes());
   ```

3. 调用 `setRequestProperty` 方法，名称为 `"Authorization"`，值为 `"Basic " + encoding`。

   ```java
   connection.setRequestProperty("Authorization",
   "Basic " + encoding);
   ```

> **提示：** 你刚刚学会了如何访问受密码保护的网页。若要通过 FTP 访问受密码保护的文件，请使用完全不同的方法：构造一个如下格式的 URL：

```text
ftp://username:password@server.com/file.txt
```

一旦你调用 `connect`，你就可以查询头部信息。首先，让我们看看如何通过 `getHeaderField(n)` 来列出所有字段，其中 `n` 从 1 开始。如果 `n` 大于字段总数，则返回 `null`。同样，调用 `headers.get(0)` 获取状态行（例如 `"HTTP/1.1 200 OK"`）。即使 `getHeaderField(0)` 返回 `null`，你也可以通过调用 `getHeaderFields()` 获取它。为了方便，六个方法查询了常见的头部类型并在适当的情况下转换为数值类型。表 4.1 显示了这些方法返回自 1970 年 1 月 1 日的秒数。

## 表 4.1 头部值的便利方法

| Key 名称 | 方法名称 | 返回类型 |
|---|---|---|
| Date | `getDate` | `long` |
| Expires | `getExpiration` | `long` |
| Last-Modified | `getLastModified` | `long` |
| Content-Length | `getContentLength` | `int` |
| Content-Type | `getContentType` | `String` |
| Content-Encoding | `getContentEncoding` | `String` |

列表 4.8 中的程序让你实验 URL 连接。在运行程序时提供 URL 以及可选的用户名和密码（用于 HTTP 基本身份验证），例如：

程序打印：

- 所有的头部键值
- 表 4.1 中便利方法的返回值
- 请求资源的前十行

## 列表 4.8 v2ch04/urlConnection/URLConnectionDemo.java

```java
package v2ch04.urlConnection;

import java.base;

/*
 * 此程序连接到 URL 并显示响应
 * 头部数据和请求的前十行。
 *
 * 在命令行提供 URL 以及可选的用户名和密码
 *（用于 HTTP 基本身份验证）。
 */
class URLConnectionDemo {
  void main(String[] args) throws Exception {
    String userName = args.length > 0 ? args[0] :
    "http://horstmann.com";

    var url = new URI(userName).toURL();
    URLConnection connection = url.openConnection();

    // 如果命令行指定了则设置用户名、密码
    // 行
    if (args.length > 2) {
      String username = args[1];
      String password = args[2];
      String input = username + ":" + password;
      Base64.Encoder encoder = Base64.getEncoder();
      String encoding = encoder.encodeToString(input.getBytes());
      connection.setRequestProperty("Authorization",
    "Basic " + encoding);
    }

    connection.connect();

    // 打印头部字段
    Map<String, List<String>> headers =
    connection.getHeaderFields();
    for (Map.Entry<String, List<String>> entry :
```

```java
headers.entrySet() {
    String key = entry.getKey();
    for (String value : entry.getValue())
        IO.println(key + ": " + value);
  }

  // print convenience functions

  IO.println("--------------------");
  IO.println("getContentType: " + connection.getContentType());
  IO.println("getContentLength: " + connection.getContentLength());
  IO.println("getContentEncoding: " + connection.getContentEncoding());
  IO.println("getDate: " + connection.getDate());
  IO.println("getExpiration: " + connection.getExpiration());
  IO.println("getLastModified: " + connection.getLastModified());
  IO.println("--------------------");
  String encoding = connection.getContentEncoding();
  if (encoding == null) encoding = "UTF-8";
  try (var in = new Scanner(connection.getInputStream(), encoding)) {
      // print first ten lines of contents
      for (int n = 1; in.hasNextLine() && n <= 10; n++)
        IO.println(in.nextLine());
      if (in.hasNextLine()) IO.println(". . . ");
  }
}
```

## `java.net.URL` 1.0

- `InputStream openStream()`

  打开一个用于读取资源数据的输入流。

- `URLConnection openConnection()`

  返回一个 `URLConnection` 对象，用于管理与资源的连接。

## `java.net.URLConnection` 1.0

- `void setDoInput(boolean newInput)`

- `boolean getInput()`

  如果 `doInput` 为 `true`，用户可以从此 `URLConnection` 接收输入。

- `void setDoOutput(boolean doOutput)`

- `boolean getDoOutput()`

  如果 `doOutput` 为 `true`，用户可以向此 `URLConnection` 发输出。

- `void setIfModifiedSince(long time)`

- `long getIfModifiedSince()`

  `ifModifiedSince` 属性配置此 `URLConnection` 仅获取自给定时间以来修改的数据。该时间自格林威治 1970 年 1 月 1 日午夜以来的秒数。

- `void setConnectTimeout(int timeout)` 5.0

- `getConnectTimeout()` 5.0

  设置或获取连接的超时时间（毫秒）。如果在建立连接之前超时已过期，则关联输入流的 `connect` 方法将抛出 `SocketTimeoutException`。

- `void setReadTimeout(int timeout)` 5.0

- `getReadTimeout()` 5.0

  设置或获取读取数据的超时时间（毫秒）。如果在读取操作成功之前超时已过期，则 `read` 方法将抛出 `SocketTimeoutException`。

- `setRequestProperty(String key, String value)`

  设置请求头字段。

- `Map<String,List<String>> getRequestProperties()` 1.4

  返回请求属性映射。相同键的所有值都存放在一个列表中。

- `void connect()`

  连接到远程资源并检索响应头信息。

- `Map<String,List<String>> getHeaderFields()` 1.4

  返回响应头映射。相同键的所有值都存放在一个列表中。

- `String getFieldName(int n)`

  获取第 `n` 个响应头字段的键，如果 `n ≤ 0` 或大于响应头字段的数量，则返回 `null`。

- `String getHeaderField(int n)`

  获取第 `n` 个响应头字段的值；如果 `n` 为 0，则返回响应状态行；如果 `n < 0` 或大于响应头字段的数量，则返回 `null`。

- `int getContentLength()`

  如果可用，获取内容长度；如果未知则返回 `-1`。

- `String getContentType()`

  获取内容类型，例如 `text/plain` 或 `image/gif`。

- `String getContentEncoding()`

  获取内容编码，例如 `gzip`。此值并不常用，因为默认的 `identity` 编码不应在 `Content-Encoding` 头部中指定。

- `long getDate()`
- `long getExpiration()`
- `long getLastModified()`

  获取资源的创建日期、过期时间和最后修改日期。日期指定为自格林威治 1970 年 1 月 1 日午夜以来的秒数。

- `InputStream getInputStream()`
- `OutputStream getOutputStream()`

  返回从资源读取或向资源写入的流。

- `Object getContent()`

  选择适当的内容处理器来读取资源数据并转换为对象。对于读取标准类型（如 `text/plain` 或 `image/gif`），此方法没有用，除非你安装了自定义的内容处理器。

## 4.3.3 发布表单数据

在前面的节中，你已经了解了如何从 Web 服务器读取数据。现在我们将向你展示你的程序如何向服务器发送数据。

要从 Web 浏览器向服务器发送信息，用户需要填写表单，如图 4.6 所示。

## 邮政编码™ 查询 | USPS - Mozilla Firefox

USPS.COM

## 查找邮政编码

- 按地址查找邮政编码 | 按城市和州查找邮政编码 | 按邮政编码查找城市 | 常见问题

按地址查找邮政编码

输入包含城市和州的街道地址，或者输入街道地址和邮政编码™



# 按地址查找邮政编码

输入包含城市和州的街道地址，或者输入街道地址和邮政编码城市。

## 查找邮政编码

- 按地址查找邮政编码
- 按城市和州查找邮政编码
- 按邮政编码查找城市
- 常见问题

## 按地址查找邮政编码

输入包含城市和州的街道地址，或者输入街道地址和邮政编码。

### 示例输入

- 州
- CA
- California
- `Find`
- `USPS.COM`
- `Main`
- `Suite`
- `Apt`
- `ZIP Code`
- `1`
- `35`
- `20`
- `17`
- `25`
- `067`
- `25`
- `38`
- `30`
- `36`
- `27`
- `39`
- `31`
- `32`
- `33`
- `34`

```java
out.close();
```

最后，调用`getInputStream`并读取服务器响应。

> **注意：** 静态方法`URLEncoder.encode`和`URLDecoder.decode`有一个使用默认字符集的版本，但它们在 Java 6 中已被弃用，因为它们应该始终与 UTF-8 使用。遗憾的是，尽管 Java 18 将默认字符编码更改为 UTF-8，它们仍然被弃用。

让我们来看一个实际的示例。网站`https://tools.usps.com/zip-code-lookup.htm?byaddress`包含一个用于通过街道地址查找美国邮政编码的表单（见图 4.6）。要在 Java 程序中使用此表单，你需要知道该 URL 以及 POST 请求的参数。

你可以通过查看表单的 HTML 代码来获取这些信息，但通常使用网络监视器“监视”请求更为简单。大多数浏览器在其开发工具包中包含网络监视器。例如，图 4.8 显示了向我们的示例网站提交数据时 Firefox 网络监视器的屏幕截图。你可以找到提交的 URL 以及参数名和值。

![](img/240dbf1b84e081687f1e252bd386c684_399_0.png)

# 图 4.8：监控表单提交

在发布表单数据时，HTTP 请求头包含内容类型：

```http
Content-Type: application/x-www-form-urlencoded
```

你也可以以其他格式发布数据。例如，当使用 JavaScript 对象表示法（JSON）发送数据时，将内容类型设置为`application/json`。

POST 头部还必须包含内容长度，例如：

```http
Content-Length: 124
```

列表 4.9 中的程序将 POST 表单数据发送到任何服务器端程序。将数据放入如下`.properties`文件中：

```properties
url=https://tools.usps.com/tools/app/ziplookup/zipByAddress
User-Agent=HTTPPie/0.9.2
address1=1 Market Street
address2=
c=San Francisco
state=CA
companyName=
..
```

程序删除了`url`和`User-Agent`项，并将所有其他项发送到`doPost`方法。

在`doPost`方法中，我们首先打开连接并设置用户代理。（邮编服务不支持默认的 User-Agent 请求参数，因为它包含字符串`Java`，可能是因为邮局不想响应程序化的请求。）

然后我们调用`setDoOutput(true)`并打开输出流。接着我们枚举所有的键和值。对于每一个项，我们发送键、`=`字符、值和`&`分隔符：

```java
out.print(key);
out.print("=");
out.print(URLEncoder.encode(value, StandardCharsets.UTF_8));
if (more pairs) out.print("&");
```

当从写入切换到读取响应的任何部分时，与服务器的实际交互就会发生。`Content-Length`头部设置为输出的大小。除非指定了不同的内容类型，否则`Content-Type`头部设置为`application/x-www-form-urlencoded`。头部和数据被发送到服务器。然后读取响应头部和服务器响应并可以进行查询。在我们的示例程序中，这种切换发生在对`connection.getContentEncoding()`的调用。

在读取响应时有一个特殊情况。如果发生服务器端错误，调用`connection.getInputStream()`将抛出`FileNotFoundException`。然而，服务器仍然向浏览器发送错误页面（例如随处可见的“Error 404—page not found”）。要获取此错误页面，请调用`getErrorStream`方法：

```java
InputStream err = connection.getErrorStream();
```

> **注意：** `getErrorStream`方法以及程序中的其他几个方法属于`URLConnection`的子类`HttpURLConnection`。如果你对以`http://`或`https://`开头的 URL 进行请求，可以将得到的连接对象强制转换为`HttpURLConnection`。

当你向服务器发送 POST 数据时，服务器端程序可能会响应重定向：即应该调用的另一个 URL，以获取实际信息。服务器这样做是因为信息可以在其他地方，或者为了提供一个可以书签的 URL。`HttpURLConnection`类可以处理重定向。

> **注意：** 如果需要在重定向期间从一个站点向另一个站点发送 Cookie，可以像这样配置全局 Cookie 处理器：

```java
CookieHandler.setDefault(new CookieManager(null, CookiePolicy.ACCEPT_ALL));
```

然后 Cookie 将被正确包含在重定向中。

尽管重定向通常会被自动处理，但在某些情况下你需要手动处理它们。出于安全考虑，系统不支持 HTTP 和 HTTPS 之间的自动重定向。重定向也可能因为更微妙的原因而失败。例如，早期版本的邮编服务使用了重定向。回想我们设置了`User-Agent`请求参数，以便邮局不认为我们是通过 Java API 发起请求的。虽然在初始请求中可以将用户代理设为不同的字符串，但该设置在自动重定向中不会被使用。相反，自动重定向总是发送一个包含`Java`单词的通用用户代理字符串。

在这种情况下，你可以手动执行重定向。在连接服务器之前，关闭自动重定向：

```java
connection.setInstanceFollowRedirects(false);
```

发送请求后，获取响应码：

```java
int responseCode = connection.getResponseCode();
```

检查是否为：

```java
HttpURLConnection.MOVED_PERM
```

或：

```java
HttpURLConnection.MOVED_TEMP
```

在那种情况下，通过`Location`头部来获取重定向 URL。

```java
if (responseCode == HttpURLConnection.HTTP_SEE_OTHER) {
    String location = connection.getHeaderField("Location");
    if (location != null) {
        URL base = connection.getUrl();
        connection.disconnect();
        return doPost(base.toURI()).resolve(location).toURL(), nameValuePairs,
            userAgent, redirects - 1);
    }
} else if (redirects == 0) throw new IOException("Too many redirects");
var response = new StringBuilder();
try (var in = new Scanner(connection.getInputStream(), encoding)) {
    while (in.hasNextLine()) {
        response.append(in.nextLine());
        response.append("\n");
    }
} catch (IOException e) {
    InputStream err = connection.getErrorStream();
    if (err == null) throw e;
    try (var in = new Scanner(err)) {
        response.append(in.nextLine());
        response.append("\n");
    }
}
return response.toString();
```

## `java.net.HttpURLConnection` 1.0

| 方法 | 说明 |
| --- | --- |
| `InputStream getErrorStream` | 返回一个流，你可以从其中读取服务器错误消息。 |

## `java.net.URLEncoder` 1.0

- `static String encode(String s, String encoding)` 1.4

  返回字符串`s`的 URL 编码形式，使用给定的字符编码方案。（推荐的方案是 `"UTF-8"`。）在 URL 编码中，字符 A-Z、a-z、0-9、`-`、`_`、`~`保持不变，所有其他字符均被编码为形式如`%XY`的编码字节序列，其中 XY 是该字节的十六进制值。

## `java.net.URLDecoder` 1.2

- `static String decode(String s, String encoding)` 1.4

  在给定的字符编码方案下返回 URL 编码字符串`s`的解码结果。

# 4.4 HTTP 客户端

`URLConnection`类的设计早于 HTTP 成为 Web 通用协议。它提供了许多协议的支持，但其对 HTTP 的支持有些繁琐。当决定采用 HTTP/2 时，显然提供一个现代的客户端接口比重构现有的 API 要好。`HttpClient`提供了 HTTP/2 支持，并且比具有那套繁琐设计的`URLConnection`类提供了更方便的 API。

## 4.4.1 `HttpClient` 类

`HttpClient`可以发送请求并接收响应。你可以通过调用以下方法获取客户端：

```java
HttpClient client = HttpClient.newHttpClient();
```

或者，如果你需要配置客户端，可以使用构建器 API，如下所示：

```java
HttpClient client = HttpClient.newBuilder()
    .followRedirects(HttpClient.Redirect.ALWAYS)
    .build();
```

也就是说，你获取一个构建器，调用方法来自定义将要构建的对象，然后调用`build`方法来完成构建过程。这是构建不可变对象的常用模式。

有许多高级选项用于选择 HTTP/2 以及控制 Cookie、SSL、代理设置和身份验证。

`HttpClient`是自动关闭的（autocloseable），你可以在 try-with-resources 语句中声明它。它的`close`方法等待已提交请求完成，然后关闭其连接池。

## 4.4.2 `HttpRequest` 类和 Body 发布器

你构建请求时也遵循构建器模式。

这是一个 GET 请求：

```java
HttpRequest request = HttpRequest.newBuilder()
    .uri(new URI(urlString))
    .GET()
    .build();
```

URI 是“统一资源标识符”，在使用 HTTP 时，它与 URL 相同。然而，在 Java 中，`URL`类拥有实际打开到 URL 连接的方法，而`URI`类只关注语法（方案、主机、端口、路径、查询参数、片段等）。

对于 POST 请求，你需要一个“正文发布器”（body publisher）将请求数据转换为正在发布的数据。有用于字符串、字节数组和文件的正文发布器。例如，如果你的请求是 JSON，只需将 JSON 字符串提供给正文发布器即可。

```java
HttpRequest request = HttpRequest.newBuilder()
    .uri(new URI(urlString))
    .header("Content-Type", "application/json")
    .POST(HttpRequest.BodyPublishers.ofString(jsonString))
    .build();
```

遗憾的是该 API 不支持常见内容类型所需的格式化。列表 4.10 中的示例程序提供了表单数据和文件上传的正文发布器。

在那个程序中，你可以看到如何使用正文发布器发送字符串和文件。文件上传需要两者，通过使用`BodyPublishers.concat`方法连接多个正文发布器以生成请求正文。

`HttpRequest.Builder`类也拥有用于不常用的 PUT、DELETE 和 HEAD 请求的 build 方法。

Java 16 增加了一个用于过滤现有`HttpRequest`头部的构建器。你提供请求和一个函数，该函数接收头部名称和值，并对于那些应该保留的头部返回 true。例如，在这里我们修改了内容类型：

```java
HttpRequest request2 =
    HttpRequest.newBuilder(request, (name, value) ->
        !name.equalsIgnoreCase("Content-Type")) // 移除旧的内容类型
    .header("Content-Type", "application/xml") // 添加新的内容类型
    .build();
```

## 4.4.3 `HttpResponse` 接口和 Body 处理器

在发送请求时，你必须告诉客户端如何处理响应。如果你只需要将正文作为字符串，可以使用`BodyHandlers.ofString()`发送请求，如下：

```java
HttpResponse<String> response =
    client.send(request, HttpResponse.BodyHandlers.ofString());
```

`HttpResponse`是一个泛型接口，其类型参数表示正文的类型。你可以直接获取响应正文：

```java
String bodyString = response.body();
```

还有其他正文处理器可以将响应作为字节数组或输入流。`BodyHandlers.ofFile(filePath)`返回一个将响应保存到指定文件的处理器，`BodyHandlers.ofDirectory(directoryPath)`使用`Content-Disposition`头部将响应保存到指定目录。最后，从`BodyHandlers.discarding()`获取的处理器直接丢弃响应。

处理响应的内容被视为 API 的一部分。例如，如果你接收 JSON 数据，你需要 JSON 库来解析内容。

`HttpResponse`对象还提供状态码和头部：

```java
int status = response.statusCode();
var headers = response.headers();
```

你可以将`HttpHeaders`对象转换为映射：

```java
Map<String, List<String>> headerMap = headers.map();
```

映射的值是列表，因为在 HTTP 中每个键可以有多个值。



如果你只需要特定键的值，并且知道不会有多个值，请调用`firstValue`方法：

```java
Optional<String> lastModified = headers.firstValue("Last-Modified");
```

如果没有提供，则返回一个空的`Optional`。

> **注意：**`HttpHeaders`类感知 HTTP 参数键不区分大小写。如果你调用`headers.firstValue("Last-Modified")`，即使它是以小写形式发送的，你也能获取所需的头部值。

## 4.4.4. 异步处理

你可以异步处理响应。在构建客户端时，提供一个执行器：

```java
ExecutorService executor = Executors.newCachedThreadPool();
HttpClient client = HttpClient.newBuilder().executor(executor).build();
```

构建请求并在客户端上调用`sendAsync`方法。你接收到一个`CompletableFuture<HttpResponse<T>>`，其中`T`是 body 处理器的类型。按照第一卷第 10 章所述使用`CompletableFuture` API：

```java
HttpRequest request = HttpRequest.newBuilder().uri(uri).GET().build();
client.sendAsync(request, HttpResponse.BodyHandlers.ofString())
  .thenAccept(response -> . . . .);
```

> **提示：**要启用`HttpClient`的日志，请在 JDK 的`net.properties`中添加此行：

```properties
jdk.httpclient.HttpClient.log=all
```

除了`all`之外，你可以指定以下事件类型的逗号分隔列表：

- `channel`
- `content`
- 错误（`errors`）
- 帧，可选跟随一个或多个：
  - `:control`
  - `:data`
  - `:window`
  - `:all`
- 头部（`headers`）
- 请求（`requests`）
- `ssl`
- `trace`

不要使用任何空格：

```properties
jdk.httpclient.HttpClient.log=headers,requests,frames:control:data
```

然后，为名为`jdk.httpclient.HttpClient`的记录器设置日志级别为 INFO，例如通过在你的 JDK 中的`logging.properties`文件中添加此行：

```properties
jdk.httpclient.HttpClient.level=INFO
```

列表 4.10 中的程序展示了如何向不同的服务发送同步请求。列表 4.11 中的类实现了表单、文件上传和 JSON 的请求体发布器（body publishers）。按如下方式运行程序：

```bash
javac v2ch04/httpClient/HttpClientDemo.java
java v2ch04.HttpClient.HttpClientDemo
v2ch04/httpClient/form.properties
java v2ch04.httpClient.HttpClientDemo
v2ch04/httpClient/fileupload.properties
java v2ch04.httpClient.HttpClientDemo
v2ch04/httpClient/json.properties
```

每次运行，都会向 CodeCheckservice 发一个 "Hello, World" 程序，并显示运行结果。该服务可以接受表单提交、文件上传和 JSON 提交。注意来自`HttpClient`的日志输出。

### 列表 4.10：`v2ch04/httpClient/HttpClientDemo.java`

```java
package v2ch04.httpClient;
import module java.base;
import module java.net.http;
import import java java.net.http.HttpRequest.BodyPublisher;

/**
 * 此程序演示了 HTTP 客户端
 * */
class HttpClientDemo {
    void main(String[] args) throws Exception {
        System.setProperty("jdk.http.client.log", "headers,requests,content");
        String propsFilename = args.length > 0 ? args[0] : "v2ch04/httpClient/json.properties";
        Path propsPath = Path.of(propsFilename);
        var props = new Properties();
        try (Reader in = Files.newBufferedReader(propsPath)) {
            props.load(in);
            String urlString = "" + props.remove("url");
            String contentType = "" + props.remove("Content-Type");

            BodyPublisher publisher = null;
            if (contentType.equals("application/x-www-form-urlencoded")) {
                publisher = MoreBodyPublishers.offFormData(props);
            } else if (contentType.equals("multipart/form-data")) {
                // 按逗号分割每个值，将以 // file:// 开头的
                // 替换为 Path 对象
                var data = new HashMap<String, List<?>>();
                for (Map.Entry<Object, Object> entry : data) {
                    data.put(entry.getKey().toString(),
```

```java
30
Stream.of(entry.getValue()).toString().split("\s*,\s*")
31
    .map(s -> s.startsWith("file://
```

### 列表 4.11：`v2ch04/httpClient/MoreBodyPublishers.java`

```java
package v2ch04.httpClient;
import module java.base;
import module java.net.http.HttpRequest.*;
public class MoreBodyPublishers {
    public static BodyPublisher ofFormData(Map<Object, Object> data) {
        boolean first = true;
        var builder = new StringBuilder();
        for (Map.Entry<Object, Object> entry : data.entrySet()) {
            if (first) {
                first = false;
            } else {
                builder.append("&");
            }
            builder.append(URLEncoder.encode(entry.getKey().toString(), StandardCharsets.UTF_8));
            builder.append("=");
            builder.append(URLEncoder.encode(entry.getValue().toString(), StandardCharsets.UTF_8));
        }
        return BodyPublishers.ofString(builder.toString());
    }
    public static BodyPublisher ofMimeMultipartData(Map<String, List<?>> data, String boundary) throws IOException {
        var bps = new ArrayList<BodyPublisher>();
        var header = new StringBuilder();
        for (Map.Entry<String, List<?>> entry : data.entrySet()) {
            for (Object value : entry.getValue()) {
                header.append("-%s\r\nContent-Disposition: form-data;name=%s".formatted(boundary, entry.getKey()));
            }
        }
```

```java
33 if (value instanceof Path path) {
34 header.append("");
filename="%s\r\n".formatted(path.getFileName());
35 String mimeType =
36 Files.probeContentType(path);
37 if (mimeType != null) {
38 header.append("Content-Type:
39 %s\r\n".formatted(mimeType));
40 header.append("\r\n");
41 bps.add(BodyPublishers.ofString(header.toString()));
42 bps.add(BodyPublishers.file(path));
43 }
44 else {
45 header.append("\r\n\n%s\r\n".formatted(value));
46 header.append("\r\n");
47 bps.add(BodyPublishers.ofString(header.toString()));
48 }
49 header = new StringBuilder();
50 bps.add(BodyPublishers.ofString(header.toString()));
51 return BodyPublishers.concat(bps));
52 } public static BodyPublisher ofJSON(Map<Object, Object> data) {
53 var builder = new StringBuilder();
54 builder.append("{");
55 var first = true;
56 for (Map.Entry<Object, Object> entry : data.entrySet()) {
57 if (first) {
58 first = false;
59 } else {
60 builder.append(",");
61 }
62 builder.append(entry.getKey().toString());
63 builder.append(": ");
64 builder.append(entry.getValue().toString());
65 }
66 builder.append("}");
67 return BodyPublishers.ofString(builder.toString());
68 }
```

```java
69 private static Map<Character, String> replacements = Map.of('\b', '\f', '\n', '\r');
70 static StringBuilder jsonEscape(String str) {
71 var result = new StringBuilder();
72 for (int i = 0; i < str.length(); i++) {
73 char ch = str.charAt(i);
74 String replacement = replacements.get(ch);
75 if (replacement == null) {
76 result.append(ch);
77 } else
78 result.append(replacement);
79 }
80 return result.toString();
81 }
```

## `java.net.http.HttpClient` 11

- `static HttpClient newHttpClient()`

  获取默认配置的`HttpClient`。

- `static HttpClient.Builder newBuilder()`

  返回一个构建`HttpClient`的构建器。

- `<T> HttpResponse<T> send(HttpRequest request, HttpResponse.BodyHandler<T> responseHandler)`

  执行同步请求并使用指定的处理器处理响应体。

- `<T> CompletableFuture<HttpResponse<T>> sendAsync(HttpRequest request, HttpResponse.BodyHandler<T> responseHandler)`

  执行异步请求并使用指定的处理器处理响应体。

## `java.net.http.HttpClient.Builder` 11

- `HttpClient build()`

  生成由此构建器配置的`HttpClient`。

- `followRedirects(HttpClient.Redirect)`

  将重定向策略设置为`HttpClient.Redirect`枚举中的`ALWAYS`、`NEVER`、`NORMAL`（仅拒绝从 HTTPS 到 HTTP 的重定向）之一。

- `executor(Executor executor)`

  设置异步请求的执行器。

## `java.net.http.HttpRequest` 11

- `HttpRequest.Builder newBuilder()`

  返回一个构建`HttpRequest`的构建器。

- `HttpRequest.Builder newBuilder(HttpRequest request, BiPredicate<String,String> filter)`

  返回一个与提供的请求属性相同的构建器，但仅包含被过滤器接受的头部。

## `java.net.http.HttpRequest.Builder` 11

- `HttpRequest build()`

  生成由此构建器配置的`HttpRequest`。

- `uri(URI uri)`

  设置此请求的 URI。

- `header(String name, String value)`

  为此请求设置一个请求头。

- `GET()`
- `DELETE()`
- `POST(HttpRequest.BodyPublisher) bodyPublisher)`
- `PUT(HttpRequest.BodyPublisher) bodyPublisher)`

  设置此请求的方法和请求体。

## `java.net.http.HttpResponse<T>` 11

- `T body()`

  获取此响应的响应体。

- `int statusCode()`

  获取此响应的状态码。

- `HttpHeaders headers()`

  获取响应头。

## `java.net.http.HttpHeaders` 11

- `Map<String,List<String>> map()`

  获取这些头部的 Map。

- `Optional<String> firstValue(String name)`

  获取这些头部中给定名称的第一个值（如果存在）。

## 4.5. 简单的 HTTP 服务器

自 Java 6 以来，JDK 在`com.sun.net.httpserver`包中提供了一个简单的 Web 服务器。在 Java 18 中，JDK 增加了一个命令行工具，用于调用该包的静态文件服务器。当时，添加了一些便利类，且 JEP 408 确认该包已获得“官方支持”。该 Web 服务器用于测试、开发和调试。

### 4.5.1. 命令行工具

要启动简单的文件服务器，请使用命令：

```bash
webserver
```

它会在端口 8000 上提供当前目录及其子目录下的所有文件。当提供文件服务时，会打印一条消息。你可以使用`-d`和`-p`选项更改目录和端口：

```bash
webserver -d /tmp -p 8189
```



你还可以使用`-o`命令行选项设置消息输出级别。选项有`info`（默认值）、`verbose`（详细）和`none`（无）。

要杀死服务器，请按`Ctrl+C`或使用`kill`/`kill`命令。

此服务器仅用于提供文件服务。它类似于`python -m http.server`命令。事实上，你也可以通过`java -m jdk.httpserver`调用这个简单的 Java 文件服务器。

### 4.5.2. HTTP 服务器 API

你可以通过程序化方式启动简单的文件服务器：

```java
import com.sun.net.httpserver.*;

HttpServer server =
    SimpleFileServer.createFileServer(
        new InetSocketAddress(port),
        Path.of("/tmp/"),
        OutputLevel.VERBOSE);

server.start();
```

现在你可以以各种方式对其进行自定义。或者，如果你不想提供文件服务，可以获取一个什么都不做的服务器：

```java
HttpServer server = HttpServer.create(
    new InetSocketAddress(port), 0);
```

第二个参数是服务器套接字的“队列长度”（backlog）——即队列连接请求的最大数量。如果参数为零，则使用默认值。

你可以设置执行器来处理请求：

```java
server.setExecutor(Executors.newVirtualThreadPerTaskExecutor());
```

为了让服务器执行有趣的操作，你需要创建上下文（contexts）。

一个上下文包含：

- 一个必须是请求路径前缀的路径
- 一个计算响应的处理器（handler）
- 一个可以转换请求或响应的过滤器列表（见第 4.5.4 节）

如果请求匹配多个上下文，将执行路径最长的那个。例如，在这里我们为`/static/`和`/`安装了两个处理器：

```java
server.createContext(
    "/static/",
    SimpleFileHandler.createFileHandler(staticRoot));

server.createContext(
    "/",
    HttpHandlers.of(
        301,
        Headers.of(
            "Location",
            "https://horstmann.com/corejava"),
        ""));
```

注意，你可以利用现有的处理器，例如简单文件服务器的处理器。

静态方法`HttpHandlers.method`返回一个固定响应的简单处理器。你传递状态码、响应头和响应体。

静态方法`HttpHandlers.handleOrElse`使用`Predicate<Request>`在两个处理器之间进行选择：

```java
HttpHandler handler = HttpHandlers.handleOrElse(
    request ->
        request.getRequestMethod().equals("GET"),
    SimpleFileHandler.createFileHandler(staticRoot),
    HttpHandlers.of(
        500,
        Headers.of(),
        "Bad request method"));
```

对于更复杂的处理器，你需要提供`HttpHandler`子类的实例。详情见下一节。

### 4.5.3. 处理器

处理器在它的方法中产生 HTTP 请求的响应：

```java
public void handle(HttpExchange exchange)
```

`HttpExchange`实例同时持有请求和响应数据。处理器必须按照此特定顺序使用该对象：

1. 读取请求方法、URI 和请求头：

```java
String method = exchange.getRequestMethod();

URI uri = exchange.getRequestURI();

Headers requestHeaders = exchange.getRequestHeaders();

String userAgent =
    requestHeaders.getFirst("user-agent");
```

2. 读取 POST、PUT 和 PATCH 请求的请求体：

```java
InputStream in = exchange.getRequestBody();

String body = new String(in.readAllBytes());

in.close();
```

3. 设置响应头：

```java
Headers responseHeaders =
    exchange.getResponseHeaders();

responseHeaders.add(
    "Content-type",
    "text/plain");
```

4. 设置状态码和响应体长度：

```java
exchange.sendResponseHeaders(
    200,
    responseBytes.length);
```

5. 如果有响应体，则写入响应体：

```java
OutputStream responseBody =
    exchange.getResponseBody();

responseBody.write(responseBytes);

responseBody.close();
```

请求头和响应头是`Headers`类的实例，该类实现了`Map<String, List<String>>`。记得每个标头可能有多个值。

`Headers`类与你在第 4.4 节中看到的`HttpHeaders`类类似，但它直接实现了`Map<String, List<String>>`接口。在`HttpHeaders`中，键是不区分大小写的。

如果你知道给定键最多有一个值，请调用`getFirst`来检索它。要向响应映射中添加键值对，请使用代码所示的`add`方法。

## 4.5.4. 过滤器

除了处理器之外，上下文还可以有一个过滤器链。过滤器可以修改请求或响应——例如日志记录或身份验证。要实现过滤器，请扩展抽象的`Filter`类并实现两个方法。通常，`doFilter`方法如下：

```java
public void doFilter(
    HttpExchange exchange,
    FilterChain chain) {

    chain.doFilter(exchange);
}
```

通过调用`chain.doFilter(exchange)`，将调用剩余的过滤器。如果身份验证失败，则不应调用。

`Filter`类为过滤器提供了三个静态工厂方法：

- `beforeEach(String description, Consumer<HttpExchange> operation)`
- `afterHandler(String description, Consumer<HttpExchange> operation)`
- `adaptRequest(String description, UnaryOperator<Request> requestOperator)`

在处理交换之前（在请求之前或之后）传递给可以检查或修改它的消费者。第三种方法使得向请求中添加标头变得更加方便：

```java
Filter f = Filter.adaptRequest(
    "Adding header",
    request -> request.with(
        headerName,
        List.of(headerValue)));
```

**注意：** 如你所见，HTTP 服务器 API 有些粗糙且过时。在你自己的代码中，不要提供返回可变数据结构引用的方法，就像`Context.getFilters()`方法所做的那样。

列表 4.12 中的程序显示了一个简单的服务器，它以纯文本响应回显所有请求数据。启动它并将浏览器指向`http://localhost:8189`来查看你浏览器的请求头。该服务器也用于观察列表 4.10 程序中的表单提交和文件上传请求。

```java
23 String response =
    "%s\n%s\n%s\n\n".formatted(
        exchange.getRequestMethod(),
        exchange.getRequestURI(),
        headers,
        requestBody);

24 byte[] responseBytes = response.getBytes();

25

26 exchange.sendHeaders(
    200,
    responseBytes.length);

27 OutputStream responseBody =
    exchange.getResponseBody();

28 responseBody.write(responseBytes);

29 responseBody.close();

30 }

31 server.start();

32 }

33 }
```

# 4.6 发送电子邮件

在过去，通过连接到邮件服务器的 25 端口（SMTP 端口）来编写一个发送电子邮件的程序是非常简单的。简单邮件传输协议（SMTP）描述了电子邮件的格式。一旦连接到服务器，就可以发送一个 SMTP 格式的邮件头（这很容易生成），然后是邮件正文。

以下是详细步骤：

1. 为你的主机打开一个 socket。

```java
var s = new Socket(
    "mail.yourserver.com",
    25); // 25 是 SMTP

var out = new PrintWriter(
    s.getOutputStream());
```

2. 向打印流发送以下信息：

```text
HELO sending host

MAIL FROM: sender e-mail address

RCPT TO: recipient e-mail address

DATA

Subject: subject

（空行）

mail message (任意行)

.

QUIT
```

SMTP 规范（RFC 821）规定行必须以`\r`后跟`\n`结束。

过去，SMTP 服务器通常愿意路由来自任何人的电子邮件。然而，在如今垃圾邮件泛滥的时代，大多数服务器都内置了检查，仅接受来自受信任的用户或 IP 地址范围的请求。验证通常在安全的 socket 连接上进行。

手动实现这些验证方案将非常麻烦。相反，我们将为你展示如何使用 Jakarta Mail API 从 Java 程序发送电子邮件。

要使用 Jakarta Mail，你需要设置一些取决于邮件服务器的属性。例如，使用 Gmail 时使用：

```properties
mail.transport.protocol=smtp
mail.smtps.auth=true
mail.smtps.host=smtp.gmail.com
mail.smtps.user=accountname@gmail.com
```

我们的示例程序从属性文件中读取这些内容。

出于安全考虑，我们不会将密码放入属性文件中，而是提示用户输入。

> **注意：** 对于大多数邮件提供商，你需要生成并使用特殊的应用程序密码，而不是使用你的普通邮件密码。

从属性文件中读取，然后获取邮件会话：

```java
Session mailSession =
    Session.getDefaultInstance(props);
```

创建一个带有所需的发送者、接收者、主题和消息正文的消息：

```java
var message = new MimeMessage(mailSession);

message.setFrom(new InternetAddress(from));

message.addRecipient(
    RecipientType.TO,
    new InternetAddress(to));

message.setSubject(subject);

message.setText(builder.toString());
```

然后将其发送：

```java
Transport tr = mailSession.getTransport();

tr.connect(null, password);

tr.sendMessage(
    message,
    message.getAllRecipients());

tr.close();
```

程序从格式如下的文本文件中读取消息：

```text
发送者
接收者
主题
消息正文（任意行）
```

在编写本文时，Gmail 并不检查信息的真实性——你可以提供任何喜欢的发送者。（下次当你再次收到来自`president@whitehouse.gov`的邀请你参加前坪正式晚会的邮件时，请记住这一点。）

由于程序需要外部 JAR 文件，它没有包含在`corejava-bookcode.zip`中，而是包含在`corejava-modulechapter.zip`中。你不需要使用模块来运行程序。只需按照如下编译并运行即可：

```bash
cd corejava-modulechapter/v2ch04.mail

javac -classpath ../jars/* \
    com.horstmann/mail/MailDemo.java

java -classpath ../../jars/* \
    com.horstmann.mail.MailDemo \
    path/to/message.txt
```

如果你愿意，可以使用模块：

```bash
cd corejava-modulechapter/

javac -p \
    v2ch04.mail:jars/jakarta.mail-api-2.1.3.jar:jars/jakarta.activation-api-2.1.3.jar \
    v2ch04.mail/com/horstmann/mail/MailDemo.java \
    v2ch04.mail/module-info.java

java -p \
    v2ch04.mail:jars/jakarta.mail-api-2.1.3.jar:jars/jakarta.activation-api-2.1.3.jar:jars/angus-activation-2.0.2.jar:jars/angus-mail-2.0.3.jar \
    -m v2ch04.mail/com.horstmann.mail.MailDemo \
    path/to/message.txt
```

> **提示：** 如果你无法确定为什么你的邮件连接不起工作，请调用：

```java
mailSession.setDebug(true);
```




并检查消息。此外，访问 Jakarta Mail API 常见问题解答：https://www.eclipse.org/jakarta/mail/faq/

> 注意：JDBC 规范可以在 https://jcp.org/aboutJava/communityprocess/model/jsr221/index3.html 找到。

大多数数据库供应商都会随其数据库提供类型 3 或类型 4 驱动程序。此外，许多第三方公司专门负责生产驱动程序，这些驱动程序在标准合规性、支持更多平台、更好的性能方面，或者在某些情况下仅仅是可靠性上，比数据库供应商提供的驱动程序更好。

总而言之，JDBC 的最终目标是实现以下目标：

- 程序员可以使用 Java 编程语言编写应用程序，使用标准 SQL 语句（甚至是 SQL 的特殊扩展）来访问任何数据库，同时遵循 Java 语言规范。
- 数据库供应商和数据库工具供应商可以提供低级驱动程序。因此，他们可以针对其特定产品优化驱动程序。

> 注意：如果你对 Java 为什么不直接采用 ODBC 模型感兴趣，根据 1996 年 JavaOne 大会上给出的原因如下：

- ODBC 很难学习。
- ODBC 拥有少数几个带有大量复杂选项的命令。Java 编程语言的首选风格是拥有简单且直观的方法，并且方法要多。
- ODBC 依赖于 `void*` 指针和其他 C 语言特性，这些特性在 Java 语言中并不自然。
- 基于 ODBC 的解决方案天生比纯 Java 解决方案不安全且更难部署。

## 5.1.2. JDBC 的典型用途

传统的客户端/服务器模型在客户端拥有丰富的 GUI，在服务器上拥有数据库（见图 5.1）。在此模型中，JDBC 驱动程序部署在客户端。

> 图 5.1：传统的客户端/服务器应用程序

然而，现在更常见的是三层模型，客户端应用程序不直接进行数据库调用。相反，它调用服务器上的中间件层，再由中间件层执行数据库查询。三层模型有几个优势。它将视觉呈现（在客户端上）与业务逻辑（在中间层）以及原始数据（在数据库中）分离开。因此，可以从多个客户端（例如 Java 桌面应用程序、网页浏览器或移动应用）访问相同的数据和相同的业务规则。

客户端与中间层之间的通信通过 HTTP 进行。JDBC 管理中间件层与后端数据库之间的通信。图 5.2 显示了基本架构。

> 图 5.2：三层应用程序

## 5.2. 结构化查询语言

JDBC 让你可以使用 SQL 与数据库通信，SQL 是本质所有关系型数据库服务器的命令语言。Microsoft Access 等桌面数据库拥有查询和更新的 GUI，但 JDBC 专注于基于服务器的数据库，如 Oracle、PostgreSQL、MySQL、Microsoft SQL Server 等。

JDBC 包可以被看作用于向数据库通信 SQL 语句的 API。我们将在本节中简要介绍 SQL。如果你以前从未见过 SQL，你可能觉得这些材料还不够。如果是这样，请转向该主题的许多学习资源之一；我推荐 Alan Beaulieu 编写的 *Learning SQL*（O'Reilly，2009）或在线书籍 *Learn SQL The Hard Way*（https://sql.learncodetheardway.org）。

你可以将数据库认为一组命名的、带有行和列的表。每列都有一个列名。每行包含一组相关数据。

作为本书的示例数据库，我们使用了一组描述经典计算机科学书籍的数据库表。

### 表 5.1：作者表

| Author_Id | Name | Fname |
|---|---|---|
| ALEX | Alexander | Christopher |
| BR00 | Brooks | Frederick P. |
| ... | ... | ... |

### 表 5.2：书籍表

| Title | ISBN | Publisher_Id | Price |
|---|---|---|---|
| A Guide to the SQL Standard | 0-201-96426-0 | 0201 | 47.95 |
| A Pattern Language: Towns, Buildings, Construction | 0-19-501919-9 | 019 | 65.00 |
| . . . | . . . | . . . | . . . |

**表 5.3：书籍作者表（BooksAuthors Table）**

| ISBN | Author_Id | Seq_No |
|---|---|---|
| 0-201-96426-0 | DATE | 1 |
| 0-201-96426-0 | DARW | 2 |
| 0-19-501919-9 | ALEX | 1 |
| . . . | . . . | . . . |

**表 5.4：出版社表（Publishers Table）**

| Publisher_Id | Name | URL |
|---|---|---|
| 0201 | Addison-Wesley | www.aw-bc.com |
| 0407 | John Wiley & Sons | www.wiley.com |
| . . . | . . . | . . . |

图 5.3 显示了 Books 表的视图。图 5.4 显示了该表与 Publishers 表连接的结果。Books 和 Publishers 表各包含一个出版商标识符。当我们根据出版商代码连接两张表时，我们得到了一个由连接表组成的查询结果。结果中的每行都包含书籍的信息，以及出版商名称和网页 URL。注意，出版商名称和 URL 在行之间是重复的，因为我们有几本属于同一出版商的书。

> 图 5.3：包含书籍的表

### Query 1

| Title | Publisher_Id | Price | Name |
|---|---|---|---|
| UNIX System Handbook | 0-13-020616 | 013 | 68.00 | Prentice Hall | |
| The C Programming Language | 0-13-10362-8 | 013 | 42.00 | Prentice Hall | |
| A Pattern Language: Towns, Buildings, Construction | 0-19-501919-9 | 019 | 65.00 | Oxford | |
| Introduction to Automata, Languages, and Computation | 0-201-44124-1 | 021 | 105.00 | Addison-W | |
| Design Patterns | 0-201-63361-2 | 021 | 54.99 | Addison-W | |
| The C++ Language | 0-201-70073-5 | 021 | 64.99 | Addison-W | |
| The Mythical Man-Month | 0-201-83595-9 | 021 | 29.95 | Addison-W | |
| Computer Graphics: Principles and Practice | 0-201-84840-6 | 021 | 79.99 | Addison-W | |
| The Art of Computer Programming, vol. 1 | 0-201-89683-4 | 021 | 59.99 | Addison-W | |
| The Art of Computer Programming, vol. 2 | 0-201-89684-2 | 021 | 59.99 | Addison-W | |
| The Art of Computer Programming, vol. 3 | 0-201-89686-0 | 021 | 59.99 | Addison-W | |
| A Guide to the SQL Standard | 0-201-94626-9 | 021 | 47.95 | Addison-W | |
| Introduction to Algorithms | 0-262-03293-7 | 026 | 80.00 | Addison-W | |
| Applied Cryptography | 0-471-11709-9 | 041 | 60.00 | Addison-W | |
| JavaScript: The Definitive Guide | 0-596-00048-0 | 059 | 44.95 | Addison-W | |
| The Cathedral and the Bazaar | 0-596-01008-5 | 059 | 16.95 | Addison-W | |
| The Soul of a New Machine | 0-679-60261-5 | 069 | 18.95 | Addison-W | |
| The Codebreakers | 0-684-83130-9 | 073 | 70.00 | Addison-W | |
| Cuckoo's Egg | 0-7434-1146-3 | 074 | 13.95 | Addison-W | |
| The Unix Hater's Handbook | 1-56884-203-1 | 047 | 16.95 | Addison-W | |

> 图 5.4：Two tables joined together

| Books | Publisher_Id | URL |
|---|---|---|
| * | * | |
| Title | | |
| ISBN | | |
| Publisher_Id | | |

按照惯例，SQL 关键字使用大写字母，尽管这并非必须。

`SELECT` 语句非常灵活。你可以仅通过以下查询来选择 Books 表中的所有行：

```sql
SELECT * FROM Books
```

`FROM` 子句在每个 SQL `SELECT` 语句中都是必不可少的。它告诉数据库需要检查哪些表来查找数据。

你可以选择你需要的列：

```sql
SELECT ISBN, Price, Title
FROM Books
```

你可以使用 `WHERE` 子句来限制结果中的行：

```sql
SELECT ISBN, Price, Title
FROM Books
WHERE Price <= 29.95
```

在使用“等号”比较时要小心。SQL 使用 `=` 和 `<>` 进行等性测试，而不是像 Java 编程语言中的 `==` 或 `!=`。

> 注意：某些数据库供应商支持使用 `!=` 进行不等性测试。这并不是标准 SQL，因此我不建议使用这种用法。

`WHERE` 子句还可以通过 `LIKE` 运算符使用模式匹配。然而，通配符并不是通常的 `*` 和 `?`。请使用 `%` 表示零或多个字符，使用下划线 `_` 表示单个字符。例如：

```sql
SELECT ISBN, Price, Title
FROM Books
WHERE Title NOT LIKE '%n_x%'
```

这将排除标题中包含 Unix 或 Linux 等单词的书籍。

注意字符串被包含在单引号中，而不是双引号。字符串内部的单引号用一对单引号来表示。例如：

```sql
SELECT Title
FROM Books
WHERE Title LIKE '%%%%'
```

这会报告所有包含单引号的标题。

你可以从多个表中选择数据：

```sql
SELECT * FROM Books, Publishers
```

由于没有 `WHERE` 子句，这个查询将毫无意义。它列出了两个表中所有行的组合。在我们的案例中，Books 有 20 行，Publishers 有 8 行，结果将是一个包含 20 × 8 条记录的行集，并且有大量重复。我们确实想对查询进行限制，说明我们只对书籍与其出版商的匹配项感兴趣：

```sql
SELECT * FROM Books, Publishers
WHERE Books.Publisher_Id =
Publishers.Publisher_Id
```

此查询结果有 20 行，每本书对应一行，因为每本书在 Publisher 表中都有一个出版商。

当你在查询中涉及多个表时，相同的列名可能会出现在两个不同的地方。在我们的示例中就发生了这种情况。Books 和 Publishers 表中都有名为 `Publisher_Id` 的列。当出现歧义时，你必须在每个列名前加上其所属表名，例如 `Books.Publisher_Id`。

你也可以使用 SQL 来更改数据库内部的数据。例如，假设你想将所有标题中包含“C++”的书籍当前价格降低 5.00 美元：

```sql
UPDATE Books
SET Price = Price - 5.00
WHERE Title LIKE '%C++%'
```

同样，要删除所有 C++ 书籍，请使用 `DELETE` 查询：

```sql
DELETE FROM Books
WHERE Title LIKE '%C++%'
```

SQL 带有用于计算平均值、查找列的最大值和最小值的内置函数等，我们在这里不讨论。

通常，要向表中插入值，你可以使用 `INSERT` 语句：

```sql
INSERT INTO Books
VALUES ('A Guide to the SQL Standard', '0-201-96426-0', '0201', 47.95)
```

表中插入的每一行都需要一个独立的 `INSERT` 语句。

当然，在查询、修改和插入数据之前，你必须有一个存储数据的地方。使用 `CREATE TABLE` 语句创建一个新表。为每一列指定名称和数据类型。例如：

```sql
CREATE TABLE Books
(
  Title VARCHAR(60),
  ISBN CHAR(13),
  Publisher Id VARCHAR(6),
  Price DECIMAL(10,2)
)
```

表 5.5 显示了最常见的 SQL 数据类型。

## 表 5.5：常见的 SQL 数据类型

| 数据类型 | 说明 |
|---|---|
| INTEGER or INT | 通常是 32 位整数 |
| SMALLINT | 通常是 16 位整数 |
| NUMERIC(m,n), DECIMAL(m,n) or DEC(m,n) | 固定精度的小数，总共有 $m$ 位有效数字，小数点后有 $n$ 位数字 |
| FLOAT(n) | 具有 $n$ 位二进制精度的浮点数 |
| REAL | 通常是 32 位浮点数 |
| DOUBLE | 通常是 64 位浮点数 |
| CHARACTER(n) or CHAR(n) | 长度为 $n$ 的固定长度字符串 |
| VARCHAR(n) | 最大长度为 $n$ 的变长字符串 |
| BOOLEAN | 布尔值 |
| DATE | 日历日期，取决于实现 |
| TIME | 一天中的时间，取决于实现 |
| TIMESTAMP | 日期和具体时间，取决于实现 |
| BLOB | 二进制大对象 |
| CLOB | 字符大对象 |

在书中，我们不讨论用于 `CREATE TABLE` 语句的额外子句，例如键和约束。

## 5.3. JDBC 配置

当然，你需要一个提供 JDBC 支持的数据库。有很多选择，例如 DB2、Microsoft SQL Server、MySQL、Oracle 和 PostgreSQL。

### 5.3.1. 数据库 URL

连接到数据库时，你必须使用各种参数，如主机名、端口号和数据库名称。通用语法是：

```text
jdbc:subprotocol:database
```

其中 `subprotocol` 选择特定的驱动程序。以下是 JDBC URL 的示例：

```text
jdbc:derby://localhost:1527/COREJAVA;create=true
```

### 5.3.2. Driver JAR 文件

你需要获取驱动所在的 JAR 文件。如果你使用 Derby，你需要 `derbyclient.jar`。对于其他数据库，你需要定位驱动。例如，PostgreSQL 的驱动可以在 https://jdbc.postgresql.org 获取。

在运行访问数据库的程序时将驱动 JAR 文件包含在类路径中。（编译时不需要 JAR 文件。）

当你从命令行启动程序时，只需使用命令：

```bash
java -classpath driverPath:. ProgramName
```

在 Windows 上，使用分号分隔当前目录（用 `.` 表示）和驱动路径。

### 5.3.3. 启动数据库

在连接数据库之前需要启动数据库服务器。细节取决于你的数据库。

对于 数据库，按照以下步骤操作：

- 打开命令行并切换到存放数据库文件的目录。
- 在 Derby 安装目录中找到 `derbyrun.jar` 文件。
- 运行命令：

```bash
java -jar derby/derbyrun.jar server start
```

- 检查数据库运行正常。创建一个包含以下内容的 `ij.properties` 文件：

```properties
ij.driver=org.apache.derby.jdbc.ClientDriver
ij.protocol=jdbc:derby://localhost:1527/
ij.database=COREJAVA;create=true
```

- 从另一个命令行运行 Derby 的交互式脚本工具（称为 `ij`），执行：

```bash
java -jar derby/derbyrun.jar ij -p ij.properties
```

现在你可以发布 SQL 命令，例如：

```sql
CREATE TABLE Greetings (Message VARCHAR(20));

INSERT INTO Greetings VALUES ('Hello, World!');

SELECT * FROM Greetings;
```




```sql
DROP TABLE Greetings;
```

注意每个命令必须以分号终止。要退出，请输入：

```sql
EXIT;
```

- 当你完成数据库的使用后，使用以下命令停止服务器：

```bash
java -jar derby/lib/derbyrun.jar server shutdown
```

如果你使用其他数据库，需要查阅文档以了解如何启动和停止数据库服务器、如何连接它以及如何执行 SQL 命令。

## 5.3.4. 连接到数据库

在你的 Java 程序中，如下所示打开数据库连接：

```java
String url = "jdbc:postgresql:COREJAVA";
String username = "dbuser";
String password = "secret";
Connection conn = DriverManager.getConnection(url, username, password);
```

驱动管理器会遍历已注册的驱动程序，以寻找可以使用数据库 URL 中指定的子协议的驱动程序。

`getConnection` 方法返回一个 `Connection` 对象。在后续章节中，你将看到如何使用 `Connection` 对象来执行 SQL 语句。

要连接到数据库，你需要数据库的用户和密码。

> 注意：默认情况下，Derby 允许使用任何用户名连接，且不检查密码。每个用户都会生成一套独立的表。默认用户名是 `app`。

Listing 5.1 中的测试程序演示了这些步骤。它从名为 `database.properties` 的文件中加载连接参数并连接到数据库。示例代码提供的 `database.properties` 文件包含了 Derby 数据库的连接信息。如果你使用不同的数据库，请将特定数据库的连接信息放入该文件。以下是连接 PostgreSQL 数据库的示例：

```properties
jdbc.drivers=org.postgresql.Driver
jdbc.url=jdbc:postgresql:COREJAVA
jdbc.username=dbuser
jdbc.password=secret
```

连接数据库后，测试程序执行以下 SQL 语句：

```sql
CREATE TABLE Greetings (Message VARCHAR(20));
INSERT INTO Greetings VALUES ('Hello, World!');
SELECT * FROM Greetings;
```

`SELECT` 语句的结果将被打印，你应该看到如下输出：

```text
Hello, World!
```

然后通过执行以下语句删除表：

```sql
DROP TABLE Greetings;
```

要运行此测试，请按照之前的描述启动数据库，并如下启动程序：

```bash
java -classpath driverJarPath:. test.TestDB
```

> **提示：** 调试 JDBC 相关问题的一种方法是启用 JDBC 跟踪。调用 `DriverManager.setLogWriter` 方法将跟踪消息发送到 `PrintWriter`。跟踪输出包含 JDBC 活动的详细列表。大多数 JDBC 驱动实现都提供了额外的跟踪机制。例如，在 Derby 中，你可以为 JDBC URL 添加 `traceFile` 选项：`jdbc:derby://localhost:1527/COREJAVA;create=t;traceFile=trace.out`。

> **注意：** 从 JDBC 4 开始，驱动 JAR 文件包含一个 `META-INF/services/java.sql.Driver`，其中包含了驱动程序类的名称。

在极少数使用较旧驱动 JAR 的情况下，你需要找到供应商所使用的 JDBC 驱动程序类名。然后在命令行上设置 `jdbc.drivers` 属性：

```bash
java -Djdbc.drivers=driverClassName ProgramName
```

## Listing 5.1 v2ch05/test/TestDB.java

```java
package v2ch05.test;

import module java.base;
import module java.sql;

import v2ch05.exec.ExecSQL;

/**
 * 此程序测试数据库和 JDBC 驱动
 * 是否配置正确。
 */
class TestDB {
    void main(String[] args) throws Exception {
        try {
            runTest();
        } catch (SQLException e) {
            for (Throwable t : e) {
                t.printStackTrace();
            }
        }
    }

    /**
     * 通过创建表、添加值、
     * 显示表内容以及
     * 删除表来运行测试。
     */
    void runTest() throws SQLException, IOException {
        try (Connection conn = SQL.getConnection()) {
            Statement stat = conn.createStatement();
            stat.executeUpdate("CREATE TABLE Greetings (Message VARCHAR(20))");
            stat.executeUpdate("INSERT INTO Greetings VALUES ('Hello, World!')");
            ResultSet result = stat.executeQuery("SELECT * FROM Greetings");
            if (result.next()) {
                System.out.println(result.getString(1));
            }
            stat.executeUpdate("DROP TABLE Greetings");
        }
    }
}
```

```java
java.sql.DriverManager 1.1

static Connection getConnection(String url,
String user, String password)

与给定数据库建立连接并
返回一个 Connection 对象。
```

## 5.4. 使用 JDBC 语句

在后续章节中，你将看到如何使用 JDBC `Statement` 执行 SQL 语句、获取结果以及处理错误。然后我们将向你展示一个用于填充数据库的简单程序。

### 5.4.1. 执行 SQL 语句

要执行 SQL 语句，首先需要创建一个 `Statement` 对象。要创建语句对象，请使用从 `DriverManager.getConnection()` 获取的 `Connection` 对象。

```java
Statement stat = conn.createStatement();
```

接下来，将你想要执行的语句放入字符串中，例如：

```java
String command = """
UPDATE Books
SET Price = Price - 5.00
WHERE Title NOT LIKE '%Introduction%'
""";
```

然后，调用 `Statement` 接口的 `executeUpdate` 方法：

```java
stat.executeUpdate(command);
```

`executeUpdate` 方法返回受 SQL 语句影响的行数，对于不返回任何行的语句则返回 0。

`executeUpdate` 方法用于 DML 语句（`INSERT`、`UPDATE`、`DELETE`）和 DDL 语句（`CREATE`、`DROP`、`ALTER`）。对于 `SELECT` 查询，使用 `executeQuery` 方法。

```java
ResultSet rs = stat.executeQuery("SELECT * FROM Books");
```

分析结果集的基本循环如下：

```java
while (rs.next()) {
    // 处理行数据
}
```

- `int executeUpdate(String sqlStatement)`
- `long executeLargeUpdate(String sqlStatement)`

  执行由字符串指定的 SQL `INSERT`、`UPDATE` 或 `DELETE` 语句。也可以执行数据定义语言（DDL）语句，例如 `CREATE TABLE`。返回受影响的行数，对于没有更新计数的语句，返回 0。

- `boolean execute(String sqlStatement)`

  执行由字符串指定的 SQL 语句。可能会产生多个结果集和更新计数。如果第一个结果是结果集，则返回 `true`；如果结果是更新计数，则返回 `false`。调用 `getResultSet` 或 `getUpdateCount` 来获取第一个结果。有关处理多个结果的详细信息，请参阅相关章节。

- `ResultSet getResultSet()`

  返回上一个查询语句的结果集，如果上一个语句没有结果集，则返回 `null`。每个执行的语句仅调用一次此方法。

- `int getUpdateCount()`
- `long getLargeUpdateCount()`

  返回上一个更新受影响的行数，如果上一个语句是没有更新计数的语句，则返回 `-1`。每个执行的语句仅调用一次此方法。

- `void close()`

  关闭此语句对象及其关联的结果集。

- `boolean isClosed()`

  如果此语句已关闭，则返回 `true`。

- `void closeOnCompletion()`

  当所有结果集都关闭后，导致此语句关闭。

## `java.sql.ResultSet` 1.1

- `boolean next()`

  使结果集中的当前行向前移动一个。在最后一行之后返回 `false`。注意，你必须调用此方法才能移动到第一行。

- `T getXXX(int columnName)`
- `T getXXX(String columnName)`

  （`T` 是一种如 `int`、`double`、`String`、`Date` 等的类型。）

- `<T> T getObject(int columnIndex, Class<T> type)`
- `<T> T getObject(String columnName, Class<T> type)`

- `void updateObject(int columnIndex, Object x, SQLException targetSql)`
- `void updateObject(String columnName, Object x, SQLException targetSql)`

  返回或更新给定列索引或标签的列的值，并将其转换为指定的类型。列标签是 SQL `AS` 子句中指定的标签，如果没有使用 `AS`，则为列名。

- `int findColumn(String columnName)`

  给出与列名关联的列索引。

- `void close()`

  立即关闭当前的结果集。

- `boolean isClosed()`

  如果此语句已关闭，则返回 `true`。

### 5.4.2. 管理连接、语句和结果集

每个 `Connection` 对象都可以创建一个或多个 `Statement` 对象。你可以对同一个 `Statement` 对象执行多个不相关的命令和查询。然而，一个语句最多有一个打开的结果集。如果你并发发布多个需要分析其结果的查询，则你需要多个 `Statement` 对象。

但请预警，每个连接的语句数量是有限的。使用 `DatabaseMetaData` 接口的 `getMaxStatements` 方法可以查找 JDBC 驱动支持的并发打开语句的数量。

在实践中，你可能不需要纠结于多个并发的结果集。如果结果集是相关的，你应该能够发布一个组合查询并分析单个结果。让数据库组合查询比让 Java 程序遍历多个结果集要高效得多。

在对 `Statement` 对象发布任何新的查询或更新之前，请务必完成对任何结果集的处理。先前的查询结果集会自动关闭。

当你完成对 `ResultSet`、`Statement` 或 `Connection` 的使用后，立即调用 `close` 方法是一个好习惯。这些对象使用大型数据结构，消耗数据库服务器的有限资源。

`Statement` 对象的 `close` 方法会关闭任何关联的结果集。同样，`Connection` 类的 `close` 方法会关闭该连接的所有语句。

相反，你可以在 `Statement` 上调用 `closeOnCompletion` 方法，它会在所有结果集关闭后自动关闭语句。

如果你的连接是短寿命的，不必担心关闭语句和结果集。使用 try-with-resources 语句可以确保连接对象不可能保持打开：

```java
try (Connection conn = . ) {
    Statement stat = conn.createStatement();
    ResultSet result = stat.executeQuery(queryString);

    // process query result
}
```

### 5.4.3. 分析 SQL 异常

每个 `SQLException` 有一个 `SQLException` 对象链，可以通过 `getNextException` 方法获取。这个异常链是每个异常都拥有的 `Throwable` 对象“原因”链之外的。（有关 Java 异常的详情请参见第一卷第七章。）需要两个嵌套循环才能完全枚举所有这些异常。幸运的是，`SQLException` 类已经增强并实现了 `Iterable<Throwable>` 接口。`iterator()` 方法产生一个 `Iterator<Throwable>`，它可以遍历这两个链：它从遍历第一个 `SQLException` 的链开始，然后移动到下一个 `SQLException`，依此类推。你可以简单地使用增强 `for` 循环：

```java
for (Throwable t : sqlType) {
    do something with t
}
```

你可以在 `SQLException` 上调用 `getSQLState` 和 `getErrorCode` 来进一步分析它。第一个方法产生一个由 X/Open 或 SQL:2003 标准化的字符串。（调用 `DatabaseMetaData` 接口的 `getTypeType` 方法可以找出驱动使用的是哪种标准。）错误代码是特定于厂商的。

SQL 异常组织成继承树（如图 5.5 所示）。这允许你以与厂商无关的方式捕获特定的错误类型。

确保你的数据库服务器正在运行，并按照以下方式运行程序：

```bash
java -classpath driverJarPath::. v2ch05.exec.ExecSQL v2ch05/Books.sql
java -classpath driverJarPath::. v2ch05.exec.ExecSQL v2ch05/Authors.sql
java -classpath driverJarPath::. v2ch05.exec.ExecSQL v2ch05/Publishers.sql
java -classpath driverJarPath::. v2ch05.exec.ExecSQL v2ch05/Authors.sql
```

在运行程序之前，检查 `database.properties` 是否已按你的环境正确配置（参见第 5.3.4 节）。

> **注意：** 你的数据库可能也有一个处理 SQL 文件的工具。例如，使用 Derby，你可以运行：

```bash
java -jar derby/lib/derbyrun.jar -p ij.properties v2ch05/Books.sql
```

（`ij.properties` 文件在第 5.3.3 节中描述。）

在 `ExecSQL` 命令的数据格式中，我们允许在每行末尾带有可选的分号，因为大多数数据库工具都期望这种格式。

以下步骤简要描述了 `ExecSQL` 程序：

1. 连接到数据库。`getConnection` 方法读取 `database.properties` 文件中的属性并将 `jdbc.drivers` 属性添加到系统属性中。驱动管理器使用 `jdbc.drivers` 属性加载相应的数据库驱动程序。`getConnection` 方法使用 `jdbc.url`、`jdbc.username` 和 `jdbc.password` 属性打开数据库连接。
2. 打开包含 SQL 语句的文件。如果未提供文件名，则提示用户在控制台上输入语句。
3. 使用通用 `execute` 方法执行每条语句。如果它返回 `true`，则说明该语句有一个结果集。为书籍数据库提供的四个 SQL 文件都以 `SELECT *` 语句结束，这样你就可以看到数据已成功插入。
4. 如果存在结果集，则打印结果。由于这是一个通用的结果集，我们需要使用元数据来查找结果中有多少列。更多信息，请参见第 5.8 节。
5. 如果发生任何 SQL 异常，打印该异常以及其中可能包含的任何链式异常。
6. 关闭数据库的连接。

列表 5.2 显示了程序的代码。

## 列表 5.2 v2ch05/exec/ExecSQL.java

```java
1 package v2ch05.exec;
2 import module java.base;
```

```java
import module java.sql;

/**
 * 执行文件或控制台中的所有 SQL 语句。
 */
```



```java
public class ExecSQL {

    public void main(String[] args) throws Exception {

        try (Scanner in = (args.length == 0
                ? new Scanner(System.in)
                : new Scanner(Path.of(args[0]))) {

            Connection conn = getConnection();
            Statement stat = conn.createStatement();

            while (true) {

                if (args.length == 0) {
                    System.out.println("Enter command or EXIT to exit:");
                }

                if (!in.hasNextLine()) {
                    return;
                }

                String line = in.nextLine().strip();

                if (line.equalsIgnoreCase("EXIT")) {
                    return;
                }

                if (line.endsWith(";")) {
                    // 移除末尾的分号
                    line = line.substring(0, line.length() - 1);
                }

                try {
                    boolean isResult = stat.execute(line);

                    if (isResult) {
                        ResultSet rs = showResultSet((ResultSet) null); // 注意：原始代码逻辑
                    } else {
                        int updateCount = stat.getUpdateCount();
                        System.out.println(updateCount + " rows updated");
                    }

                } catch (SQLException e) {
                    e.printStackTrace();
                }
            }

        } catch (SQLException | IOException e) {
            e.printStackTrace();
        }
    }

    /**
     * 从 database.properties 文件
     * 指定的属性中获取连接
     *
     * @return 数据库连接
     */
    public static Connection getConnection() throws SQLException, IOException {

        var props = new Properties();

        try (Reader in = Files.newBufferedReader(
                Path.of("v2ch05", "database.properties"))) {
            props.load(in);
        }

        String drivers = props.getProperty("jdbc.drivers");

        if (drivers != null) {
            System.setProperty("jdbc.drivers", drivers);
        }

        String url = props.getProperty("jdbc.url");
        String username = props.getProperty("jdbc.username");
        String password = props.getProperty("jdbc.password");

        return DriverManager.getConnection(url, username, password);
    }

    /**
     * 打印结果集。
     *
     * @param result 要打印的结果集
     */
    private void showResultSet(ResultSet result) throws SQLException {

        ResultSetMetaData metaData = result.getMetaData();
        int columnCount = metaData.getColumnCount();

        while (result.next()) {
            for (int i = 1; i <= columnCount; i++) {
                System.out.print(
                        metaData.getColumnLabel(i) + ": "
                                + result.getObject(i) + "\t");
            }

            System.out.println();
        }
    }
}
```

*（注：代码块的 OCR 包含严重的碎片化和语法错误（例如，使用 `jdbc0h5` 而非 `v2ch05`，`Scanner([0])` 以及损坏的大括号）。我根据 Java/JDBC 模式修正了逻辑。）*

## 5.5 查询执行

在本节中，我们将编写一个针对数据库执行查询的程序。为了使此程序工作，你需要选择数据。价格更新功能通过 `UPDATE` 语句实现。注意我们调用 `executeUpdate`，因为 `UPDATE` 语句不返回结果集。

### 5.5.1 预编译语句

手动拼接字符串构建查询既枯燥又危险。你必须担心引号等特殊字符——而且如果你的查询涉及用户输入，你必须防止注入攻击。因此，当查询涉及变量时，请使用预编译语句。

当数据库执行查询时，首先计算执行策略。通过准备查询并重复使用它，可以确保规划步骤只执行一次。准备查询中的每个主机变量都用 `?` 表示。如果有多个变量，在设置值时必须跟踪位置。例如，我们的查询变为：

```java
String publisherQuery =
        "SELECT Books.Price, Books.Title FROM Books, Publishers "
                + "WHERE Publisher_Id = ? AND Name = ?";

PreparedStatement pstat = conn.prepareStatement(publisherQuery);
```

在执行预编译语句之前，你必须使用 `set` 方法将主机变量绑定到实际值。与 `ResultSet` 接口的 `get` 方法一样，针对各种类型有不同的 `set` 方法。在这里，我们要为出版者名称设置一个字符串：

```java
pstat.setString(1, publisher);
```

第一个参数是我们要设置的主机变量的位置。位置 1 表示第一个 `?`。第二个参数是我们要赋值给主机变量的值。

如果你重复使用一个已经执行过的预编译查询，除非使用 `set` 方法更改它们，否则所有变量都将保持绑定。这意味着你只需要对那些在查询之间变化的主机变量调用 `setXxx` 方法。一旦变量都绑定了值，就可以执行预编译语句了：

```java
ResultSet rs = pstat.executeQuery();
```

```java
int r = stat.executeUpdate();

IO.println(r + " rows updated");
```

> **注意：** 关联的 `Connection` 对象关闭后，`PreparedStatement` 对象将失效。然而，许多数据库会自动缓存预语句。如果同一个查询被准备了两次，数据库将直接重用该查询策略。因此，不必担心调用 `prepareStatement` 的开销。

以下列表简要描述了示例程序的结构：

- 作者和出版者列表通过运行两个查询来填充，这两个查询返回数据库中所有的作者和出版者名称。
- 涉及作者的查询是复杂的。一本书可以有多个作者，因此 `BooksAuthors` 表存储了作者与书籍之间的关系。例如，ISBN 为 `0-201-96426-0` 的书有两个代码为 `DATE` 和 `DARW` 的作者。`BooksAuthors` 表有以下行：
  - `0-201-96426-0, DATE, 1`
  - `0-201-96426-0, DARW, 2`

  以此表示这一事实。第三列列出了作者的顺序。（我们不能简单地使用表中的行位置。在关系表中没有固定的行顺序。）因此，查询必须连接 `Books`、`BooksAuthors` 和 `Authors` 表，将作者名称与用户选择的名称进行比较。

```sql
SELECT Books.Price, Books.Title
FROM Books, BooksAuthors, Authors, Publishers
WHERE Authors.Author_Id = BooksAuthors.Author_Id
  AND BooksAuthors.ISBN = Books.ISBN
  AND Books.Publisher_Id = Publishers.Publisher_Id
  AND Authors.Name = ?
  AND Publishers.Name = ?
```

> **提示：** 一些 Java 程序员会避免这种复杂的 SQL 语句。一种异常常见但非常低的解决方法是编写大量的 Java 代码来遍历多个结果集。但数据库执行查询代码的能力远比 Java 程序强大——这是数据库的核心竞争力。一个经验法则是：如果你可以用 SQL 完成它，就不要在 Java 中完成。

- `changePrices` 方法执行一个 `UPDATE` 语句。注意 `UPDATE` 语句的 `WHERE` 子句需要出版者代码，而我们只知道出版者名称。这个问题通过嵌套子查询来解决：

```sql
UPDATE Books
SET Price = Price + ?
WHERE Books.Publisher_Id = (
    SELECT Publisher_Id
    FROM Publishers
    WHERE Name = ?
)
```

代码列表 5.3 是完整的程序代码。

## 代码列表 5.3 `v2ch05/query/QueryDemo.java`

```java
package v2ch05.query;

import java.base;
import java.sql;

import v2ch05.exec.ExecSQL;

/**
 * 此程序演示了几个复杂的数据库
 * 查询。
 */
class QueryDemo {

    String allQuery =
            "SELECT Books.Price, Books.Title FROM Books";

    String authorQuery =
            "SELECT Books.Price, Books.Title "
                    + "FROM Books, BooksAuthors, Authors, Publishers "
                    + "WHERE Authors.Author_Id = BooksAuthors.Author_Id "
                    + "AND Books.Publisher_Id = Publishers.Publisher_Id "
                    + "AND Authors.Name = ? "
                    + "AND Publishers.Name = ?";

    String publisherQuery =
            "SELECT Books.Price, Books.Title "
                    + "FROM Books, BooksAuthors, Authors "
                    + "WHERE Authors.Author_Id = BooksAuthors.Author_Id "
                    + "AND BooksAuthors.ISBN = Books.ISBN "
                    + "AND Authors.Name = ?";

    String publisherQuery2 =
            "SELECT Books.Price, Books.Title "
                    + "FROM Books, Publishers "
                    + "WHERE Books.Publisher_Id = Publishers.Publisher_Id "
                    + "AND Publishers.Name = ?";

    String priceUpdate =
            "UPDATE Books SET Price = Price + ? "
                    + "WHERE Books.Publisher_Id = "
                    + "(SELECT Publisher_Id FROM Publishers WHERE Name = ?)";

    ArrayList<String> authors = new ArrayList<>();
    ArrayList<String> publishers = new ArrayList<>();

    void main(Exception Exception) {

        try (Connection conn = SQL.getConnection()) {

            authors.add("Any");
            publishers.add("Any");

            try (Statement stat = conn.createStatement()) {

                // 填充作者列表
                String query = "SELECT Name FROM Authors";

                try (ResultSet rs = stat.executeQuery(query)) {
                    while (rs.next()) {
                        authors.add(rs.getString(1));
                    }
                }

                // 填充出版者列表
                query = "SELECT Name FROM Publishers";

                try (ResultSet rs = stat.executeQuery(query)) {
                    while (rs.next()) {
                        publishers.add(rs.getString(1));
                    }
                }

                boolean done = false;

                while (!done) {
                    String input = IO.readLine("Q").toUpperCase();

                    if (input.equals("Q")) {
                        executeQuery(conn);
                    } else if (input.equals("C")) {
                        changePrices(conn);
                    } else {
                        done = true;
                    }
                }

            } catch (SQLException e) {
                for (Throwable t : e) {
                    IO.println(t.getMessage());
                }
            }
        }
    }
}

/**
 * 执行查询。
 *
 * @param conn 数据库连接
 */
void executeQuery(Connection conn) throws SQLException {

    try (PreparedStatement stat = conn.prepareStatement(allQuery)) {

        try (ResultSet rs = stat.executeQuery()) {

            while (rs.next()) {



```java
IO.println(rs.getString(1) + " " + rs.getString(2));

}

}

}

}

/**
 * 执行更新以价格。
 * @param conn 数据库连接
 */
void changePrices(Connection conn) throws SQLException {
    try (PreparedStatement stat = conn.prepareStatement(priceUpdate)) {
        double priceChange = Double.parseDouble(IO.readLine("Change prices by: "));
        stat.setDouble(1, priceChange);
        stat.setString(2, "Any"); // 逻辑占位
        int r = stat.executeUpdate();
        IO.println(r + " records updated.");
    }
}

/**
 * 要求用户选择字符串。
 * @param prompt 显示的提示
 * @param options 用户可以选择的选项
 * @return 用户选择的索引
 */
String select(String prompt, List<String> options) {
    while (true) {
        IO.println(prompt);
        for (int i = 0; i < options.size(); i++)
            IO.println("%2d %s".formatted(i + 1, options.get(i)));
        int sel = Integer.parseInt(IO.readLine());
        if (sel > 0 && sel <= options.size()) return sel - 1;
    }
}
```

## 5.5.2. 读取和写入 LOB

除了数字、字符串和日期外，许多数据库还可以存储大对象（LOB），例如图像或其他数据。在 SQL 中，二进制大对象被称为 BLOB，字符大对象被称为 CLOB。

> **注意：**取决于应用程序，将大对象存储在数据库中还是文件系统中更好。本节将告诉你一旦决定使用数据库来实现该目的后该如何做。

要读取 LOB，请执行 `SELECT` 语句并在 `ResultSet` 上调用 `getBlob` 或 `getClob` 方法。你将得到一个 `Blob` 或 `Clob` 类型的对象。要从 `Blob` 中获取二进制数据，请调用 `getBytes` 或 `getBinaryStream`。例如：

如果你有一个包含书籍封面图像的表格，可以像这样检索图像：

```java
PreparedStatement pstat = conn.prepareStatement("SELECT Cover FROM BookCovers WHERE ISBN=?");

pstat.set(1, isbn);

try (ResultSet result = pstat.executeQuery()) {
    if (result.next()) {
        Blob coverBlob = result.getBlob(1);
        Image coverImage = IO.read(coverBlob.getBinaryStream());
    }
}
```

同样，如果你检索的是一个 `Clob` 对象，可以通过调用 `getString` 或 `CharacterStream` 方法获取字符数据。

要将一个 LOB 放入数据库，请在 `Connection` 对象上调用 `createClob` 或 `createClob`，获取 LOB 的输出流或写入器，写入数据，并将对象存储在数据库中。例如，这里是存储图像的方法：

```java
Blob coverBlob = connection.createBlob();
int offset = 0;
OutputStream out = coverBlob.setBinaryStream(offset);
IO.write(coverImage, "PNG", out);
PreparedStatement pstat = conn.prepareStatement("INSERT INTO Cover VALUES (?, ?)");
```

```java
pstat.set(1, isbn);
pstat.set(2, coverBlob);
pstat.executeUpdate();
```

## `java.sql.ResultSet` 1.1

- `Blob getBlob(int columnIndex)` 1.2
- `Blob getBlob(String columnLabel)` 1.2
- `Clob getClob(int columnIndex)` 1.2
- `Clob getClob(String columnLabel)` 1.2

获取指定列的 BLOB 或 CLOB。

## `java.sql.Blob` 1.2

- `long length()`

  获取此 BLOB 的长度。

- `byte[] getBytes(long startPosition, long length)`

  获取此 BLOB 中指定范围内的数据。

- `InputStream getBinaryStream()`
- `InputStream getBinaryStream(long startPosition, long length)`

  返回一个用于从此 BLOB 或指定范围读取数据的流。

- `OutputStream setBinaryStream(long startPosition)` 1.4

  返回一个用于写入此 BLOB 的输出流，从指定位置开始。

## `java.sql.Clob` 1.4

- `long length()`

  获取此 CLOB 的字符数。

- `String getSubstring(long startPosition, long length)`

  获取此 CLOB 中指定范围内的字符。

- `Reader getCharacterStream()`
- `Reader getCharacterStream(long startPosition, long length)`

  返回一个读取器（不是流），用于从此 CLOB 或指定范围读取字符。

- `Writer setCharacterStream(long startPosition)` 1.4

  返回一个写入器（不是流），用于写入此 CLOB，从指定位置开始。

## `java.sql.Connection` 1.1

- `Blob createBlob()` 6
- `Clob createClob()` 6

  创建一个空的 BLOB 或 CLOB。

## 5.5.3. SQL 转义（SQL Escapes）

“转义”语法功能通常被数据库支持，但使用特定于数据库的语法变体。JDBC 驱动程序的工作是将转义语法翻译为特定数据库的语法。

以下功能提供了转义支持：

- 日期和时间字面量
- 调用标量函数
- 调用存储过程
- 外连接
- `LIKE` 子句中的转义字符

日期时间字面量在不同数据库之间差异巨大。要嵌入日期或时间字面量，请按下方所示 ISO 8601/RFC 3339 格式之一指定值，其中毫秒是可选的。驱动将其翻译为原生格式。使用 `d`、`t`、`ts` 用于 DATE、TIME 或 TIMESTAMP 值：

```sql
{d '2024-01-24'}

{t '23:59:59'}

{ts '2024-01-24 23:59:59.999'}
```

标量函数是返回单个值的函数。许多函数在数据库中广泛可用，但名称不同。JDBC 规范提供了标准名称并将其翻译为特定数据库的名称。要调用函数，请如下所示嵌入标准函数名和参数：

```sql
{fn left(?, 20)}

{fn user()}
```

你可以在 JDBC 规范中找到支持的函数完整列表。

两个表的外连接并不要求每个表的行都根据连接条件匹配。例如，查询：

```sql
SELECT * FROM {oj Books LEFT OUTER JOIN Publishers
ON Books.Publisher_Id = Publisher.Publisher_Id}
```

包含了某些书籍，其 `Publisher_Id` 在 `Publishers` 表中没有匹配，并用 NULL 值表示不存在匹配。你需要 `RIGHT OUTER JOIN` 来包含没有匹配书籍的出版商，或者使用 `FULL OUTER JOIN` 来返回两者。大多数数据库都支持所有形式的外连接，但某些并不支持。`oj` 转义允许 JDBC 驱动程序定位并重写任何不支持的外连接操作。如果你的数据库支持所有形式的外连接，则无需担心此转义。

最后，`_` 和 `%` 字符在 `LIKE` 子句中具有特殊含义——用于匹配单个字符或字符序列。没有标准方法可以字面上使用它们。如果你想匹配所有包含 `_` 的字符串，请使用此构造：

```sql
{escape _%}
```

在这里我们定义转义符。存储过程是以特定数据库语言执行的过程。要调用存储过程，请使用：

```java
CallableStatement cstat = conn.prepareCall("{call ?, ?)}");

cstat.setInt(1, id);
cstat.registerOutParameter(2, java.sql.Types.VARCHAR);
cstat.execute();

String name = cstat.getString(2);
```

## 5.5.4. 多结果（Multiple Results）

查询可能会返回多个结果集或更新计数。这发生在执行存储过程时，或者在使用允许多个 `SELECT` 语句的数据库时。以下是检索所有结果的方法：

1. 使用 `execute` 方法执行语句。
2. 获取第一个结果集或更新计数。
3. 重复调用 `Results` 方法到下一个结果集或更新计数。
4. 当没有更多结果集或更新计数时结束。

以下循环遍历所有结果：

```java
boolean isResult = stat.execute(command);
boolean done = false;

while (!done) {
    if (isResult) {
        ResultSet result = stat.getResultSet();
        对 result 进行某些操作
    } else {
        int updateCount = stat.getUpdateCount();

        if (updateCount >= 0) {
            对 updateCount 进行某些操作
        } else {
            done = true;
        }
    }

    if (!done) isResult = stat.getMoreResults();
}
```

## `java.sql.Statement` 1.1

- `boolean getMoreResults()`
- `boolean getMoreResults(int current)` 6

  获取此语句的下一个结果。`current` 参数可以是 `CLOSE_CURRENT_RESULT`（默认）、`KEEP_CURRENT_RESULT` 或 `CLOSE_ALL RESULTS`。如果存在结果且是结果集，则返回 `true`。

## 5.5.5. 获取自动生成键（Retrieving Autogenerated Keys）

大多数数据库都支持某种表中行自动编号的机制。遗憾的是，这些机制在厂商之间差异巨大。这些自动数字通常用作主键。虽然 JDBC 未提供独立厂商的键生成解决方案，但它提供了检索这些键的有效方法。当你向表中插入新行并自动生成键时，可以使用以下代码检索它：

```java
stat.executeUpdate(insertStatement,
    Statement.RETURN_GENERATED_KEYS);

ResultSet rs = stat.getGeneratedKeys();

if (rs.next()) {
    int key = rs.getInt(1);
}
```

## `java.sql.Statement` 1.1

- `boolean execute(String statement, int autogenerated)` 1.4
- `int executeUpdate(String statement, int autogenerated)` 1.4

执行给定的 SQL 语句，如之前所述。如果 `autogenerated` 设置为 `Statement.RETURN_GENERATED_KEYS` 且语句是 `INSERT` 语句，则第一列包含自动生成的键。

## 5.6. 可滚动和可更新的结果集

正如你所看到的，`ResultSet` 接口的下一个方法是遍历结果集中的行。对于需要分析数据的程序来说这足够了。然而，考虑一个显示表格或查询结果的可视化数据显示（如图 5.4 所示），通常希望用户能够在结果集中向前向后移动。在可滚动的结果集中，你可以向前向后移动结果集，甚至可以跳转到任何位置。

此外，一旦用户看到显示的结果集内容，他们可能会想要编辑它。在可更新的结果集中，你可以通过程序更新条目，从而使数据库自动更新。我们将在接下来的章节中讨论这些功能。

### 5.6.1. 可滚动的结果集

默认情况下，结果集是不可滚动或不可更新的。要从查询获取可滚动的结果集，你必须获取带有方法的不同 `Statement` 对象：

```java
Statement stat = conn.createStatement(type, concurrency);
```

对于预编译语句（prepared statement），使用调用：

```java
PreparedStatement pstat =
    conn.prepareStatement(command, type, concurrency);
```

`type` 和 `concurrency` 的可能值如表 5.6 所示。你有以下选择：

- 你是否希望结果集是可滚动的？如果不是，使用 `ResultSet.TYPE_FORWARD_ONLY`。
- 如果结果集是滚动的，你是否希望它反映产生该结果集的查询之后发生的数据库更改？（在讨论中，我们假设可滚动结果集使用 `ResultSet.TYPE_SCROLL_INSENSITIVE` 设置。这假设结果集不会“感知”查询执行后发生的数据库更改）
- 你是否希望通过编辑结果集来更新数据库？（详细信息请见下一节。）

#### 表 5.6：ResultSet 类型和并发性值

| 值 | 解释 |
|---|---|
| `TYPE_FORWARD_ONLY` | 结果集不可滚动（默认）。 |
| `TYPE_SCROLL_INSENSITIVE` | 结果集是滚动的，但对数据库更改不敏感。 |
| `TYPE_SCROLL_SENSITIVE` | 结果集是滚动的，且对数据库更改敏感。 |
| `CONCUR_READ_ONLY` | 结果集不能用于更新数据库（默认）。 |
| `CONCUR_UPDATABLE` | 结果集可用于更新数据库。 |

例如，如果你只是想要滚动结果集但不想编辑其数据，请使用：

```java
Statement stat = conn.createStatement(
    ResultSet.TYPE_SCROLL_INSENSITIVE,
    ResultSet.CONCUR_READ_ONLY);
```

所有由调用

```java
ResultSet rs = stat.executeQuery(query);
```

返回的结果集现在都是可滚动的。可滚动的结果集有一个指示当前位置的游标。

> **注意：**并不是所有的数据库驱动程序都支持滚动或可更新的结果集。（`DatabaseMetaData` 接口的 `supportsResultSetType` 和 `supportsResultSetConcurrency` 方法将告诉你使用特定驱动程序的数据库支持哪些类型和并发模式。）即使数据库支持所有结果模式，特定的查询也可能无法产生具有所有请求属性的结果集。（例如，复杂查询的结果集可能是不可更新的。）在这种情况下，`executeQuery` 方法将返回一个能力较少的 `ResultSet` 并向连接对象添加一个 `SQLException`。[第 5.4.3 节显示了如何检索警告。）或者，你可以使用 `ResultSet` 接口的 `getType` 和 `getConcurrency` 方法来查找结果集实际上处于什么模式。如果你不检查结果集能力而执行了不支持的操作（如之前在不可滚动的结果集上操作的那样），该操作将抛出 `SQLException`。

滚动非常简单。使用：

```java
if (rs.previous()) . . ;
```

向后滚动。如果游标位于实际行上，该方法返回 `true`；如果它现在位于第一行之前，则返回 `false`。

你可以通过调用移动游标向前向后任意行：

```java
rs.relative(n);
```

如果 `n` 为正数，游标向前移动。如果 `n` 为负数，它向后移动。如果 `n` 为零，则调用没有影响。如果你尝试将游标移动到当前行集之外，它将被指向最后一行之后或第一行之前，取决于 `n` 的符号。然后，方法返回 `false` 且游标不移动。如果游标位于实际行上，方法返回 `true`。

或者，你可以将游标设置为特定的行号：

```java
rs.absolute(n);
```

要获取当前行号，调用：



```java
int currentRow = rs.getRow();
```

结果集中的第一行编号为 1。如果返回值为 0，则游标当前不在某行上——它在第一行之前或最后一行之后。

便利方法 `first`、`last`、`beforeFirst` 和 `afterLast` 将游标移动到第一个、最后一个、第一个之前或最后一个之后。

最后，方法 `isFirst`、`isLast`、`isBeforeFirst` 和 `isAfterLast` 测试游标是否位于这些特殊位置之一。

使用可滚动的结果集非常简单。缓存查询数据的复杂工作已由完成。

### 5.6.2 可更新的结果集

如果你想编辑结果集中的数据并让更改反映在数据库中，你需要可更新的结果集。要获取可更新的结果集，请创建语句：

```java
Statement stat = conn.createStatement(
    ResultSet.TYPE_SCROLL_INSENSITIVE,
    ResultSet.CONCUR_UPDATABLE);
```

返回的结果集是可更新的。

> **注意**：并不是所有的查询都会返回可更新的结果集。如果你的查询连接了多个表，结果可能不可更新。

例如，假设你想提高某些书籍的价格，根据任意条件遍历所有书籍。

```java
String query = "SELECT * FROM Books";

ResultSet rs = stat.executeQuery(query);

while (rs.next()) {
    if (. .) {
        double price = rs.getDouble("Price");
        rs.updateDouble("Price", price + increase);
    }

    rs.updateRow(); //
}
```

对应所有 SQL 类型的 `updatexx` 方法，例如 `updateDouble`、`updateString` 等；使用列名或列号指定。

> **注意**：如果你使用参数为列号的 `updatexx` 方法，请注意这是结果集中的列号。它与数据库中的列号可能不同。

`updatexx` 方法仅更改行值，而不更改数据库。当你完成某行的字段更新时，必须调用 `updateRow` 方法。该方法将当前行的所有更新发送到数据库。如果你在调用 `updateRow` 之前移动到其他行，该行的更新将被丢弃且不会通信到数据库。你也可以调用 `cancelRowUpdates` 方法取消当前行的更新。

前面的示例显示了如何修改现有行。如果你想向数据库添加新行，首先使用 `moveToInsertRow` 方法将游标移动到一个特殊位置，称为插入行。然后，通过发布更新指令在插入行位置构建新行。完成后，调用 `insertRow` 方法将新行传递到数据库。插入完成后，调用 `moveToCurrentRow` 将游标移回调用 `moveToInsertRow` 之前的位置。这里有一个示例：

```java
rs.moveToInsertRow();

rs.updateString("Title", title);
rs.updateString("ISBN", isbn);
rs.updateString("Publisher_Id", pubid);
rs.updateDouble("Price", price);

rs.insertRow();
rs.moveToCurrentRow();
```

注意，你无法影响新数据添加到结果集或数据库中的位置。如果你没有在插入行中指定列值，它将被设置为 SQL `NULL`。但是，如果该列有 `NOT NULL` 约束，将抛出异常且不会插入该行。

最后，你可以删除光标下的行：

```java
rs.deleteRow();
```

`deleteRow` 方法会立即从结果集和数据库中删除该行。

`ResultSet` 接口的 `updateRow`、`insertRow` 和 `deleteRow` 方法提供的功能与执行 `UPDATE`、`INSERT` 和 `DELETE` SQL 语句相同。然而，Java 程序员可能会发现，通过结果集操作数据库内容比通过构建 SQL 语句更自然。

> **注意：** 如果你不够小心，使用可更新的结果集可能会编写出效率极低的代码。执行一个 `UPDATE` 语句比执行查询并在遍历结果的同时更改数据要高效得多。可更新的结果集对于用户可以进行任意更改的交互式程序是有意义的，但对于大多数程序更改，SQL `UPDATE` 更合适。

> **注意：** JDBC 2 对结果集进行了进一步的增强，例如如果数据已被另一个并发数据库连接修改，则具有使用最新数据更新结果集的能力。JDBC 3 增加了另一项改进，规定了事务提交时结果集的行为。然而，这些高级功能超出了本介绍章节的范围。我们建议你参考 Maydenes Fisher、Jon Ellis 和 Jonathan Bruce 编写《JDBC™ API Tutorial and Reference, Third Edition》（Addison-Wesley, 2003）以及 JDBC 规范以获取更多信息。

## `java.sql.Connection` 1.1

- `Statement createStatement(int type, int concurrency)` 1.2
- `PreparedStatement prepareStatement(String command, int type, int concurrency)` 1.2：创建语句或预编译语句，产生给定类型和并发允许的结果集。参数 `type` 为常量 `TYPE_FORWARD_ONLY`、`TYPE_SCROLL_INSENSITIVE` 或 `TYPE_SCROLL_SENSITIVE` 之一，`concurrency` 为常量 `CONCUR_READ_ONLY` 或 `CONCUR_UPDATABLE` 之一，这些都定义在 `ResultSet` 接口中。

## `java.sql.ResultSet` 1.1

- `int getType()` 1.2：返回此结果集的类型——`TYPE_FORWARD_ONLY`、`TYPE_SCROLL_INSENSITIVE` 或 `TYPE_SCROLL_SENSITIVE` 之一。
- `int getConcurrency()` 1.2：返回此结果集的并发设置——`CONCUR_READ_ONLY` 或 `CONCUR_UPDATABLE` 之一。
- `boolean previous()` 1.2：将光标移动到上一行。如果光标位于某一行，则返回 `true`；如果光标位于第一行之前，则返回 `false`。
- `int getRow()` 1.2：获取当前行号。行从 1 开始编号。
- `boolean absolute(int r)` 1.2：将光标移动到第 `r` 行。如果光标位于某一行，则返回 `true`。
- `boolean relative(int d)` 1.2：将光标移动 `d` 行。如果 `d` 为负数，则光标后移动。如果光标位于某一行，则返回 `true`。
- `boolean first()` 1.2
- `boolean last()` 1.2：将光标移动到第一行或最后一行。如果光标位于某一行，则返回 `true`。
- `void beforeFirst()` 1.2
- `void afterLast()` 1.2：将光标移动到第一行之前或最后一行之后。
- `boolean isFirst()` 1.2
- `boolean isLast()` 1.2：测试光标是否在第一行或最后一行。
- `boolean isBeforeFirst()` 1.2
- `boolean isAfterLast()` 1.2：测试光标是否在第一行之前或最后一行之后。
- `void moveToInsertRow()` 1.2：将光标移动到插入行。插入行是一个特殊行，用于通过 `updateXXX` 和 `insertRow` 方法插入新数据。
- `void moveToCurrentRow()` 1.2：将光标从插入行移回调用 `moveToInsertRow` 方法时所占的位置。
- `void insertRow()` 1.2：将插入行的内容插入到数据库和结果集中。
- `void deleteRow()` 1.2：从数据库和结果集中删处当前行。
- `void updateXXX(int column, Xxx data)` 1.2
- `void updateXXX(String columnName, Xxx data)` 1.2（`Xxx` 是如 `int`、`double`、`String`、`Date` 等类型）：更新结果集中当前行中的字段。
- `void updateRow()` 1.2：将当前行的更新发送到数据库。
- `void cancelRowUpdates()` 1.2：取消当前行的更新。

## `java.sql.DatabaseMetaData` 1.1

- `boolean supportsResultSetType(int type)` 1.2：如果数据库支持给定类型的结果集，则返回 `true`；`type` 为 `ResultSet` 接口中的常量 `TYPE_FORWARD_ONLY`、`TYPE_SCROLL_INSENSITIVE` 或 `TYPE_SCROLL_SENSITIVE` 之一。
- `boolean supportsResultSetConcurrency(int type, int concurrency)` 1.2：如果数据库支持给定类型和并发组合的结果集，则返回 `true`。参数 `type` 为常量 `TYPE_FORWARD_ONLY`、`TYPE_SCROLL_INSENSITIVE` 或 `TYPE_SCROLL_SENSITIVE` 之一，这些都定义在 `ResultSet` 接口中。

## Scrollable Row Sets

可滚动结果集非常强大，但它们有一个主要的缺点：你需要保持连接开启。正如我们在 5.4 节的示例程序所示，这极大地简化了交互式程序的实现。每个用户只需打开数据库连接，发布查询，将结果放入行集中，然后断开连接。

### 5.7.1 构建行集

`java.sql.rowset` 包提供了以下扩展 `ResultSet` 的接口：

- `CachedRowSet`：允许离线操作。我们将在后续节中讨论缓存行集。
- `JdbcRowSet` 是 `ResultSet` 的一个薄封装。它添加了 `ResultSet` 接口中的实用方法，并允许你离开数据库连接。
- `FilteredRowSet` 和 `JoinRowSet`：支持等于 SQL `SELECT` 和 `JOIN` 操作的行集。

要获取缓存行集，调用：

```java
RowSetFactory factory = RowSetProvider.newFactory();
CachedRowSet crs = factory.createCachedRowSet();
```

### 5.7.2 Cached Row Sets

缓存行集包含来自结果集的所有数据。由于 `CachedRowSet` 是 `ResultSet` 接口的子接口，你可以完全像使用结果集一样使用缓存行集。缓存行集带来了一个重要的优势：你可以关闭连接并仍然使用该行集。

你可以从结果集填充 `CachedRowSet`：

```java
ResultSet result = ...;

RowSetFactory factory = RowSetProvider.newFactory();
CachedRowSet crs = factory.createCachedRowSet();

crs.populate(result);

conn.close(); // 现在可以关闭数据库连接
```

或者，你可以让 `CachedRowSet` 对象自动建立连接。设置数据库参数：

```java
crs.setURL("jdbc:derby://localhost:1527/COREJAVA");
crs.setUsername("dbuser");
crs.setPassword("secret");
```

然后设置查询语句和任何参数：

```java
crs.sendCommand("SELECT * FROM Books WHERE Publisher_Id = ?");
crs.setString(1, publisherId);
```

最后，用查询结果填充行集：

```java
crs.execute();
```

此调用建立数据库连接、执行查询、填充行集并断开连接。

如果你的查询结果很大，你可能不想将其全部放入行集中。毕竟，你的用户可能只会查看几行。在这种情况下，指定一个页面大小：

```java
CachedRowSet crs = ...;

crs.sendCommand(command);
crs.setPageSize(20);
```

```java
crs.execute();
```

现在你只会获取 20 行数据。要获取下一批数据，请调用：

```java
crs.nextPage();
```

你可以使用与处理结果集（result sets）相同的方法来检查和修改行集（row set）。如果你修改了行集的内容，必须通过调用以下方法将其写回数据库：

```java
crs.acceptChanges(conn);
```

或者：

```java
crs.acceptChanges();
```

只有当你已经为行集配置了连接数据库所需的信息（如 URL、用户名和密码密码）时，第二次调用才会生效。

在第 5.6.2 节中，你已经看到并不是所有的结果集都是可更新的。同样，包含复杂查询结果的行集将无法将其更改写回数据库。如果你的行集包含来自单张表的数据，那么应该是安全的。

> **注意：** 如果你是从结果集中填充行集的，则行集并不知道要更新的表名。你需要调用 `setTableName` 来设置表名。

如果在你填充行集之后，数据库中的数据发生了变化，就会出现另一种复杂性。这显然是可能导致数据不一致的故障迹象。参考实现会检查原始行集值（即编辑前的值）是否与数据库中的当前值相同。如果相同，则它们会被替换为编辑后的值；否则，将抛出 `SyncProviderException` 且不写入任何更改。其他实现可能会使用其他的同步策略。

## `javax.sql.ResultSet` 1.4

- `String getURL()`
- `void setURL(String url)`  
  获取或设置数据库 URL。
- `String getUsername()`
- `void setUsername(String username)`  
  获取或设置连接数据库的用户名。
- `String getPassword()`
- `void setPassword(String password)`  
  获取或设置连接数据库的密码。
- `String getCommand()`
- `void setCommand(String command)`  
  获取或设置用于填充行集的执行命令。
- `void execute()`  
  通过执行由 `setCommand` 设置的语句来填充此行集。为了驱动管理器获取连接，必须设置 URL、用户名和密码。

## `javax.sql.rowset.CachedRowSet` 5.0

- `void execute(Connection conn)`  
  通过执行由 `SqlCommand` 设置的语句来填充此行集。此方法使用给定的连接并将其关闭。
- `void populate(ResultSet result)`  
  使用给定结果集的数据填充此缓存行集。
- `String getTableName()`
- `void setTableName(String tableName)`  
  获取或设置填充此缓存行集的源表名。
- `int getPageSize()`
- `void setPageSize(int size)`  
  获取或设置分页大小。
- `boolean nextPage()`
- `boolean previousPage()`  
  加载下一页或上一页行。如果存在下一页或上一页，则返回 `true`。
- `void acceptChanges()`
- `void acceptChanges(Connection conn)`  
  连接到数据库并写入编辑行集产生的更改。如果因为数据库数据已更改导致无法写回，可能会抛出 `SyncProviderException`。

## `javax.sql.rowset.RowSetProvider` 7

- `static RowSetFactory newFactory()`  
  创建一个行集工厂。

## `javax.sql.rowset.RowSetFactory` 7

- `CachedRowSet createCachedRowSet()`
- `FilteredRowSet createFilteredRowSet()`
- `JdbRowSet createJdbcRowSet()`
- `JoinRowSet createJoinRowSet()`
- `WebRowSet createWebRowSet()`  
  创建一个指定类型的行集。

## 5.8 元数据

在前面的章节中，你学习了如何填充、查询和更新数据库表。然而，JDBC 可以为你提供关于数据库及其表结构的额外信息。例如，你可以获取特定数据库中的表列表，或者某个表的列名和类型。当你在实现一个具有预定义数据库的业务应用程序时，这些信息并没有用处。毕竟，如果你设计了表，你自然知道它们的结构。但是，对于编写适用于任何数据库的工具的程序员来说，结构信息是极其用的。

在 SQL 中，描述数据库或其部分的数据被称为*元数据*（metadata，以区别于存储在数据库中的实际数据）。你可以获取三种元数据：关于数据库的、关于结果集的以及关于预编译语句参数的。

要了解更多关于数据库的信息，请从数据库连接请求一个 `DatabaseMetaData` 类型的对象。

```java
DatabaseMetaData meta = conn.getMetaData();
```



使用此对象获取关于数据库的信息。例如，调用：

```java
ResultSet mrs = meta.getTables(null, null, null, new String[] { "TABLE" });
```

返回一个包含数据库中所有表信息的结果集。（请参本节末尾的 API 注释了解该方法的其他参数。）

结果集中的每一行都包含数据库中某张表的信息。第三列是表名。（再次查看 API 注释了解其他列。）以下循环收集了所有的表名：

```java
while (mrs.next())
  tableNames.add(mrs.getString(3));
```

数据库元数据还有第二个重要的用途。数据库是复杂的，而 SQL 标准为变体留下了大量空间。`DatabaseMetaData` 中有百多个方法可以查询数据库，包括如下调用：

```java
meta.supportsCatalogs()
```

和：

```java
meta.supportsNull()
```

显然，这些是针对有特殊需求的高级用户的——特别是那些需要编写可跨多个数据库代码的人。`DatabaseMetaData` 接口提供关于数据库的数据。第二个元数据接口 `ResultSetMetaData` 报告关于结果集的信息。当你从查询获取结果集时，可以查询列的数量以及每列的名称、类型。这是一个典型的循环：

```java
ResultSet rs = stat.executeQuery("SELECT * FROM " + tableName);

ResultSetMetaData rsmd = rs.getMetaData();

for (int i = 1; i <= rsmd.getColumnCount(); i++) {
    String columnName = rsmd.getColumnLabel(i);
    int columnWidth = rsmd.getColumnDisplaySize(i);
}
```

如果你有一个预编译语句，可以获取执行时返回的结果集的元数据：

```java
PreparedStatement pstat = conn.prepareStatement(sql);
ResultSetMetaData rsmd = pstat.getMetaData();
```

第三种元数据描述预编译语句的参数：

```java
ParameterMetaData pmd = pstat.getMetaData();

for (int i = 1; i <= pmd.getParameterCount(); i++) {
    System.out.println(pmd.getParameterTypeName(i));
}
```

列表 5.4 中的程序使用元数据让你浏览数据库中的所有表并执行简单的编辑。该程序还演示了缓存行集的使用。伴随代码有一个更美的 GUI 版本。顶部的组合框显示数据库中的所有表。选择其中一个，框架中心就会填充该表的字段名和第一行的值，如图 5.6 所示。点击 Next 和 Previous 可以滚动查看表中的行。你还可以删除一行并编辑 String 类型的值。点击 Save 按钮将更改保存到数据库。

```java
/*
 * class ViewDB {
 * CachedRowSet crs;
 * record Column(String label, int width, String
 * columnClass) {
 }
 *
 * List<Column> columns = new ArrayList<>();
 *
 * void main() {
 * try (Connection conn = ExecSQL.getConnection()) {
 * DatabaseMetaData meta = conn.getMetaData();
 * var tableNames = new ArrayList<String>();
 *
 * try (ResultSet mrs = meta.getTables(null, null, null, new String[]{"TABLE"})) {
 * while (mrs.next()) {
 * tableNames.add(mrs.getString(3));
 * }
 * IO.out.println("Choose a table:");
 * String selected = Choices.choose(tableNames);
 * showTable(selected, conn);
 * executeCommands(conn);
 * crs.acceptChanges(conn);
 * }
 * } catch (SQLException e) {
 * for (Throwable t : e) {
 * t.printStackTrace();
 * }
 * } catch (IOException e) {
 * e.printStackTrace();
 * }
 *
/**
 * Prepares the columns list for showing a new table, and
 * shows the first row.
 * @param tableName the name of the table to display
 * @param conn the database connection
 */

void showTable(String tableName, Connection conn) throws SQLException {
 * try (Statement stat = conn.createStatement()) {
 * ResultSet result = stat.executeQuery("SELECT * FROM " + tableName + ")");
 * // copy into cached row set
 * RowSetFactory factory =
RowSetProvider.newFactory();

54      crs = factory.createCachedRowSet();
55      crs.setTableName(tableName);
56      crs.populate(result);
57
58      ResultSetMetadata rsmd = result.getMetaData();
59      for (int i = 1; i <= rsmd.getColumnCount(); i++) {
60          columns.add(new
61              Column(rsmd.getColumnLabel(i), rsmd.getColumnDisplaySize(i),
62                  rsmd.getColumnClassName(i)));
63      }
64
65      showNextRow();
66}
67

68
void executeCommands() throws SQLException {
70      while (true) {
71          String selection = Choices.choose("Next",
72      "Previous", "Edit", "Delete", "Quit");
73          switch (selection) {
74              case "Next" -> showNextRow();
75              case "Previous" -> showPreviousRow();
76              case "Edit" -> editRow();
77              case "Delete" -> deleteRow();
78              default -> {
79                  return;
80              }
81          }
82      }
83  }

84
85  /**
86   * Shows a database row by populating all text fields
87   * with the column values.
88   */

89  void showRow(ResultSet rs) throws SQLException {
90      for (int i = 1; i <= columns.size(); i++) {
91          String format = "%%-%s%%s"
92              "[%%ds]".formatted(columns.get(i - 1).width());

94      IO.println(format.formatted(columns.get(i - 1).label(),
95              rs == null ? "" : rs.getString(i)));
96      }
97  }

* Moves to the previous table row.
 *

void showPreviousRow() throws SQLException {
    if (crs == null || crs.isFirst()) return;
    crs.previous();
    showRow(crs);
}

/**
 * Moves to the next table row.
 */

void nextRow() throws SQLException {
    if (crs == null || crs.getLast()) return;
    crs.next();
    showRow(crs);
}

/**
 * Deletes current table row.
 */

void deleteRow() throws SQLException {
    if (crs == null) return;
    crs.deleteRow();
    if (!crs.last()) crs = null;
    showRow(crs);
}

/**
 * Updates changed data into the current row of the row
 */

void editRow() throws SQLException {
    List<String> editableColumns = columns.stream()
        .filter(c -> c.columnClass.equals("java.lang.String")).map(Column::name)
        .toList();

    IO.println("Choose column");
    String label = Choices.choose(editableColumns);
    String newValue = IO.readLine("New value: ");

    crs.updateString(label, newValue);
    crs.updateRow();
}
```

## `java.sql.Connection` 1.1

- `DatabaseMetadata getMetaData()` 返回作为 `DatabaseMetadata` 对象的连接元数据。

## `java.sql.DatabaseMetadata` 1.1

- `ResultSet getTables(String catalog, String schemaPattern, String tableNamePattern, String types[])` 返回目录中符合模式、表名模式以及类型标准的所有表的描述。（`schema`（模式/架构）描述了一组相关的表和访问权限。`catalog`（目录）描述了相关的模式组。这些概念对于结构化大型数据库非常重要。）`catalog` 和 `schemaPattern` 参数可以为空。

| 列 | 名称 |
|---|---|
| 1 | catalog（可能为 null） |
| 2 | schema（可能为 null） |
| 3 | name |
| 4 | type |
| 5 | remarks |

## 5.9.1 使用 JDBC 进行编程事务

默认情况下，数据库连接处于*自动提交模式*，每条 SQL 语句在执行后都会立即提交到数据库。一旦语句提交，你将无法对其进行回滚。关闭此默认设置以可以使用事务：

```java
conn.setAutoCommit(false);
```

按照常规方式创建语句对象：

```java
Statement stat = conn.createStatement();
```

调用任意次数 `executeUpdate`：

```java
stat.executeUpdate(command1);
stat.executeUpdate(command2);
stat.executeUpdate(command3);
...
```

如果所有语句都已无错误执行，调用 `commit` 方法：

```java
conn.commit();
```

然而，如果发生了错误，则调用：

```java
conn.rollback();
```

然后，自上次提交以来执行的所有语句都将自动反滚。通常当你的事务被 `SQLException` 中断时，你会执行回滚。

### 5.9.2 存点（Save Points）

在某些数据库和驱动程序中，你可以通过保存点对回滚过程进行更细粒度的控制。创建一个保存点会标记一个点，你稍后可以返回此处，而无需放弃整个事务。例如：

```java
Statement stat = conn.createStatement(); // 开始 transaction；rollback() 在此处执行

stat.executeUpdate(command1);

Savepoint svpt = conn.setSavepoint(); // 设置 savepoint；rollback(svpt) 在此处执行

stat.executeUpdate(command2);
```

```java
if (.. ) conn.rollback(svpt); // 撤销 command2 的效果
...
conn.commit();
```

当你不再需要某个保存点时，应该释放它：

```java
conn.releaseSavepoint(svpt);
```

### 5.9.3 批处理（Batch Updates）

假设一个程序需要执行许多 `INSERT` 语句来填充数据库表。你可以通过使用批处理来提高程序的性能。在批处理中，一组语句会被收集起来并作为一个批（batch）提交。

> **注意：** 使用 `DatabaseMetaData` 接口的 `supportsBatchUpdates` 方法来确定你的数据库是否支持此功能。

批中的语句可以是 `INSERT`、`UPDATE` 或 `DELETE` 等操作，也可以是 `CREATE TABLE` 或 `DROP TABLE` 等数据定义语句。如果在批处理中添加 `SELECT` 语句，将抛出异常。（从概念上讲，`SELECT` 语句在批处理中没有意义，因为它返回的是结果集而不更新数据库。）

要执行批处理，首先按通常方式创建一个 `Statement` 对象：

```java
Statement stat = conn.createStatement();
```

现在，不再调用 `executeUpdate`，而是调用 `addBatch` 方法：

```java
String command = "CREATE TABLE . . ...";

stat.addBatch(command);

while (. . .) {
    command = "INSERT INTO . . . VALUES(" +
    + ")";
    stat.addBatch(command);
}
```

最后，提交整个批：

```java
int[] counts = stat.executeBatch();
```

对 `executeBatch` 的调用返回所有提交语句的行计数数组。

为了在批模式下进行正确的错误处理，请将批执行视为一个单一事务。如果批处理在中间失败，你希望回滚到批开始之前的状态。

首先，关闭自动提交模式，然后收集批处理、执行它、提交它，最后恢复原始自动提交模式：

```java
boolean autoCommit = conn.getAutoCommit();

conn.setAutoCommit(false);

Statement stat = conn.getStatement();

// 继续调用 stat.addBatch(.. ..);

stat.executeBatch();

conn.commit();
conn.setAutoCommit(autoCommit);
```



#### `java.sql.Connection` 1.1

- `boolean getAutoCommit()`
- `void setAutoCommit(boolean b)`

  获取或设置此连接的自动提交模式为`b`。如果自动提交为`true`，则所有语句在执行完成后立即提交。

- `void commit()`

  提交自上次提交以来发出的所有语句。

- `void rollback()`

  撤销自上次提交以来发出的所有语句的影响。

- `Savepoint setSavepoint()` 1.4
- `Savepoint setSavepoint(String name)` 1.4

  设置未命名的或具名的保存点。

- `void rollback(Savepoint svpt)` 1.4

  回滚到指定的保存点。

- `void releaseSavepoint(Savepoint svpt)` 1.4

  释放指定的保存点。

#### `java.sql.Savepoint` 1.4

- `int getSavepointId()`

  获取此未命名保存点的 ID，如果这是一个具名的保存点，则抛出 `SQLException`。

- `String getSavepointName()`

  获取此保存点的名称，如果这是一个未命名的保存点，则抛出 `SQLException`。

#### `java.sql.Statement` 1.1

- `void addBatch(String command)` 1.2

  将命令添加到该语句的当前命令批中。

- `int[] executeBatch()` 1.2
- `long[] executeLargeBatch()` 8

  执行当前批中的所有命令。返回数组中的每个值对应于批中的一个语句。如果是非负数，则为行计数。如果值为 `SUCCESS_NO_INFO`，则表示语句执行成功但没有行计数可用。如果是 `EXECUTE_FAILED`，则表示语句失败。

#### `java.sql.DatabaseMetaData` 1.1

- `boolean supportsBatchUpdates()`

  如果你的数据库支持批处理，则返回 `true`。

### 5.9.4. 高级 SQL 类型

| SQL 类型 | Java 类型 |
|---|---|
| `INTEGER` | `int` |
| `SMALLINT` | `short` |
| `NUMERIC(m,n)`, `DECIMAL(m,n)` | `java.math.BigDecimal` |
| `FLOAT(n)` | `double` |
| `REAL` | `float` |
| `CHARACTER(n)`, `CHAR(n)` | `String` |
| `VARCHAR(n)`, `LONG VARCHAR` | `String` |
| `BOOLEAN` | `boolean` |
| `DATE` | `java.sql.Date` |
| `TIME` | `java.sql.Time` |
| `TIMESTAMP` | `java.sql.Timestamp` |
| `BLOB` | `java.sql.Blob` |
| `CLOB` | `java.sql.Clob` |
| `ARRAY` | `java.sql.Array` |
| `ROWID` | `java.sql.RowId` |
| `NCHAR(n)`, `NVARCHAR(n)`, `LONG NVARCHAR` | `String` |
| `NCLOB` | `java.sql.NClob` |
| `SQLXML` | `java.sql.SQLXML` |

`SQL ARRAY` 是一个值的序列。例如，在 Student 表中，你可以有一个 ARRAY 类型的 Scores。`getArray` 方法返回 `Array` 接口的对象。该接口具有获取数组值的方法。

当你从数据库获取 LOB 或数组时，实际内容仅会在你请求时才从数据库获取。这是一种性能优化，因为数据可能很大。

某些数据库支持 ROWID 值，它描述行的位置以便快速检索。JDBC 4 引入了 `java.sql.RowId` 接口以及在查询中提供和从结果中检索的方法。

国家字符字符串（NCHAR 及其变体）使用本地字符编码存储字符串并使用本地排序规则排序。JDBC 4 提供了在 Java `String` 对象与国家字符字符串之间转换的方法。

某些数据库可以存储自定义结构化类型。JDBC 3 提供了将结构化 SQL 类型映射到 Java 对象的机制。

某些数据库为 XML 提供原生存储。JDBC 4 引入了 `SQLXML` 接口，它可以在内部 XML 表示与 DOM `Source`/`Result` 接口以及二进制流之间进行调解。详情请参阅 `SQLXML` 类的文档。

我们不再进一步讨论这些高级 SQL 类型。你可以在 JDBC API 教程和参考以及规范中找到有关这些主题的更多信息。

```java
var jndiContext = new InitialContext();

var source = (DataSource) jndiContext.lookup("java:comp/env/jdbc/corejava");

Connection conn = source.getConnection();
```

注意，`DriverManager` 不再参与其中。相反，由 JNDI 服务来定位数据源。数据源是一个接口，允许进行简单的 JDBC 连接以及更高级的服务，例如执行涉及多个数据库的分布式事务。`DataSource` 接口定义在 `javax.sql` 标准扩展包中。

> Note：在 Java EE 容器中，你甚至不需要编写 JNDI 查找代码。只需在 `DataSource` 字段上使用 `@Resource` 注解，当应用程序加载时，数据源引用就会设置：

```java
@Resource(name="jdbc/corejava")
private DataSource source;
```

当然，数据源需要在某处进行配置。如果你编写了运行在 Servlet 容器（如 Apache Tomcat）或应用服务器（如 GlassFish）中的数据库数据库程序，请将数据库配置（包括 JNDI 名称、JDBC URL、用户名和密码）放在配置文件中，或在管理 GUI 中设置。

用户名和登录管理只是需要特别关注的问题之一。另一个问题涉及建立数据库连接的成本。我们的示例数据库程序使用了两种策略来获取数据库连接。列表 5.3 中的 `QueryDB` 程序在程序开始时建立了一个单一数据库连接，并在程序结束时关闭。列表 5.4 中的 `ViewDB` 程序在每次需要时都会打开新连接。

然而，这两种方法都不令人如意。数据库连接是有限的资源。如果用户离开应用程序一段时间，连接不应保持打开状态。相反，为每个查询都获取连接并在之后关闭是成本极高的。

解决方案是使用连接池。这意味着数据库连接不会被物理关闭，而是被保留在队列中并重用。连接池是一项重要服务，JDBC 规范为实现者提供了提供该服务的钩子。然而，JDBC 没有提供任何实现，数据库供应商通常也不会在其 JDBC 驱动中包含连接池。相反，Web 容器和应用服务器的供应商提供了连接池的实现。

使用连接池对程序员来说是完全透明的。通过获取数据源并调用 `getConnection` 从池化连接源中获取连接。当你完成使用后，调用 `close`。这不会关闭物理连接，而是告诉连接池你已完成使用。连接池通常还会尝试对预编译语句（prepared statements）进行池化处理。

你现在学习了 JDBC 的基础知识，并具备足够的知识来实现简单的数据库应用程序。然而，正如本章开头提到的，数据库是复杂的，相当高级的主题出了本介绍章节的范围。要了解高级 JDBC 能力的概览，请参考 JDBC API 教程与参考，或 JDBC 规范。

在本章中，你学习了如何在 Java 中操作关系型数据库。下一章将介绍日期和时间库。

# 第 6 章 ■ 日期和时间 API

时光飞逝，我们可以轻松地设置一个起点并以秒为单位向前后计数。那么为什么处理时间这么困难呢？问题出在人类。如果我们能互相说：“在 `1523793600` 会合，不要迟到！”，一切都会简单了。我们想要联系光照和季节。这使得事情变得复杂。Java 1.0 有一个 `Date` 类，从事后看来来看，它是幼稚的，而且在 Java 1.1 引入 `Calendar` 类时，它的大部分方法都被弃用了。这个 API 并不完美，它的实例是可变的，而且它没有处理闰秒等问题。第三次是幸运，在 Java 8 中引入的 `java.time` API 弥补了过去的缺陷，并且应该为我们服务很长一段时间。在本章中，你将学习为什么计算是如此烦恼，以及日期和时间 API 是如何解决这些问题的。

## 6.1. 时间线

从历史上看，基本单位——秒源于地球绕自轴的旋转。一个完整的转圈有 24 小时，即 24 x 60 x 60 = 86400 秒，精确定义秒似乎只是一个天文测量的问题。不幸的是，地球会轻微摇晃，需要更精确的定义。1967 年，根据 133 铯原子的内在属性，推导出了与历史定义相匹配的新型精确精确定义。然后，一个原子钟网络维持着官方时间。

尽管如此，官方计时器经常将绝对时间与地球自转进行同步。首先，对官方秒进行了轻微调整，但从 1972 年开始，偶尔会插入“闰秒”（有人说需要偶尔将其移除，但这种情况尚未发生）。显然，闰秒是个麻烦，许多计算机系统改为使用“平滑”处理，即在闰秒之前人为地减慢或加速时间，保持每天 86,400 秒。这之所以有效，是因为计算机上的本地时间并不完全精确，而且计算机被用于与外部时间服务同步。

日期和时间 API 规范要求 Java 使用符合以下条件的时间尺度：

- 每天 86,400 秒
- 每天中午与官方时间完全匹配
- 在其他地方以一种精确定义的方式紧密匹配

这使得 Java 具有了适应时间线未来变化的灵活性。起点，即纪元（epoch），是：

在 Java 中，`Instant` 代表时间线上的一个点。起点被任意设定为 1970 年 1 月 1 日午夜，位于穿过伦敦格林维治天文台的本初午线。这是 UNIX/POSIX 时间使用的惯例。从该起点开始，时间以每天 86,400 秒为单位向前后测量，精度达到纳秒。最大值 `Instant.MAX` 是 1,000,000 年的 12 月 31 日。这不足以表达宇宙的年龄（约 135 亿年），但对于所有实际目的来说足够了。毕竟，十亿年前，地球被冰覆盖，并居住着今天植物动物的微型祖先。

静态方法 `Instant.now()` 给出当前时刻。你可以用通常的方式通过 `equals` 和 `compareTo` 方法比较两个 `instant`，因此你可以将 `instant` 用时间戳。要找到两个 `instant` 之间的差异，使用静态方法 `Duration.between`。例如，这里是衡量算法运行时间的方法：

```java
Instant start = Instant.now();

runAlgorithm();

Instant end = Instant.now();

Duration elapsedTime = Duration.between(start, end);

long millis = elapsedTime.toMillis();
```

`Duration` 是两个 `instant` 之间的时间量。你可以通过调用 `getNanos`、`toMillis`、`toSeconds`、`toMinutes`、`toHours` 或 `toDays` 获取各种单位的 `Duration` 长度。

> Note：在 Java 8 中，可以使用 `getSeconds` 代替 `toSeconds`。

如果你需要纳秒精度，请注意溢出问题。一个 `long` 值可以容纳近 300 年的纳秒。如果你的持续时间短于此，只需将其转换为纳秒。你可以使用更长的持续时间——`Duration` 对象在 `long` 中存储秒数，并在另一个 `int` 中存储纳秒数。`Duration` API 有许多方法（在本节末尾显示），用于算术运算。

例如，如果你想检查一个算法是否比另一个快十倍，你可以计算：

```java
Duration elapsedTime2 = Duration.between(start2, end2);

boolean overTenTimesFaster = elapsedTime.multipliedBy(10).minus(timeElapsed2).isNegative();
```

这只是为了展示语法。由于算法不会运行几百年年，你可以直接使用：

```java
boolean overTenTimesFaster = elapsedTime.toNanos() * 10 < timeElapsed2.toNanos();
```

注意：`Instant` 和 `Duration` 类是不可变的，所有的方法（如 `multipliedBy` 或 `minus`）都会返回一个新的实例。

Listing 6.1 中的示例程序使用了 `Instant` 和 `Duration` 类对两个算法进行计时。

注意：示例程序的方法在实践中过于简单，因为它没有处理诸如 JVM 中即时编译器（JIT）的“预热”等问题。如果你需要比较算法，应该使用专门的基准工具，如 Java Microbenchmark Harness (JMH)。`https://www.oracle.com/technical-resources/articles/java/architect-benchmarking.html` 的结果提供了有用的建议。

### Listing 6.1 `v2ch06/Timeline.java`

```java
package v2ch06;

/**
 * 此程序演示了实例和时长。
 */

import java.base.*;

public class Timeline {

    RandomGenerator generator = RandomGenerator.getDefault();

    void main() {

        Instant start = Instant.now();

        runAlgorithm(1);

        Instant end = Instant.now();

        Duration timeElapsed = Duration.between(start, end);

        long millis = timeElapsed.millis();

        System.out.println(millis + " milliseconds: " + formatted(millis));

        Instant start2 = Instant.now();

        runAlgorithm(2);

        Instant end2 = Instant.now();

        Duration timeElapsed2 = Duration.between(start2, end2);

        System.out.println(timeElapsed2.millis() + " milliseconds: " + formatted(timeElapsed2));

        boolean isNegative = timeElapsed2.multipliedBy(10).millis() < 0;

        System.out.printf("The first algorithm is %s than ten times faster", isNegative);

    }

    void runAlgorithm1() {

        int size = 10;

        Array<Integer> list = generator.ints().map(i -> i % 100).limit(size).boxed()
            .collect(Collectors.toCollection(ArrayList::new));

        System.out.println(list);

    }

    void runAlgorithm2() {

        int size = 10;

        List<Integer> list = generator.ints().map(i -> i % 100).limit(size).boxed()
            .collect(Collectors.toCollection(ArrayList::new));

        while (!IntStream.range(1, list.size())
            .allMatch(i -> list.get(i - 1).compareTo(list.get(i)) <= 0)) {

            Collections.shuffle(list);

            IO.println(list);

        }

    }

}
```




# `java.time.Instant` 8

- `static Instant now()`：从最佳可用系统时钟获取当前瞬间。
- `Instant plus(TemporalAmount amountToAdd)`
- `Instant minus(TemporalAmount amountToSubtract)`：返回一个与此 `Instant` 相差给定偏移量的瞬间。`Duration` 和 `Period` 类实现了 `TemporalAmount` 接口。
- `Instant plusXxx(long number)`
- `Instant minusXxx(long number)`：返回一个与此 `Instant` 相差指定单位的瞬间，其中 `Xxx` 是 `Nanos`、`Millis` 或 `Seconds`。

# `java.time.Duration` 8

- `static Duration ofXxx(long number)`：返回一个指定单位数量的时长，其中 `Xxx` 是 `Nanos`、`Millis`、`Seconds`、`Hours` 或 `Days`。
- `static Duration between(Temporal startInclusive, Temporal end)`：返回两个时间点之间的时长。`Temporal` 接口由 `Instant` 类以及 `LocalDate`、`LocalDateTime`、`LocalTime` 和 `ZonedDateTime` 实现。
- `long toXxx()`
- `longSeconds(9)`：获取此时长中方法名所代表的单位数量，其中 `Xxx` 是 `Millis`、`Minutes`、`Hours` 或 `Days`。
- `int toXxxPart()`
- `long toDays(9)`：返回此时长中指定时间单位的部分。例如，在 100 秒的时长中，该部分是 1，第二部分是 40。这里，`Xxx` 是 `nanos`、`Millis`、`Seconds`、`Minutes` 或 `Hours` 之一。
- `Duration plus(TemporalAmount amountToAdd)`
- `Duration minus(TemporalAmount amountToSubtract)`：返回一个与此 `Duration` 相差给定偏移量的时长。`Duration` 和 `Period` 类实现了 `TemporalAmount` 接口。
- `Duration multipliedBy(long multiplicand)`
- `Duration dividedBy(long divisor)`
- `Duration negated()`：返回一个通过将此 `Duration` 乘以或除以给定数量或 `-1` 得到的时长。
- `boolean isZero()`
- `boolean isNegative()`：如果此时长为零或为负，则返回 `true`。
- `Duration plusXxx(long number)`
- `minusXxx(long number)`：返回通过加或减给定数量时间单位得到的时长，其中 `Xxx` 是 `Nanos`、`Millis`、`Seconds`、`Minutes` 或 `Hours` 之一。

## 6.2. Local Dates

现在让我们从绝对时间转向人类时间。Java API 中有两种人类时间：本地日期/时间和时区时间。本地日期/时间包含日期和或一天的时间，但没有关联的时区信息。本地日期的示例是 1903 年 6 月 14 日（lambda 演算术发明者 Alonzo Church 的生日）。由于该日期既没有时间也没有区域信息，因此它不对应于精确的时间瞬间。

除了 `LocalDate` 外，还有 `MonthDay`、`YearMonth` 和 `Year` 类来描述日期。例如，12 月 25 日（不指定年份）可以表示为 `MonthDay`。

列表 6.2 中的示例程序展示了如何使用 `LocalDate` 类。

# 列表 6.2 `v2ch06/LocalDate.java`

```java
package v2ch06;

/**
 * 此程序演示了本地日期。
 */

import java.base.*;

class Dates {

    void main(String[] args) {

        LocalDate today = LocalDate.now(); // 今日日期

        out.println("today: " + today);

        LocalDate alBirthday = LocalDate.of(1903, 6, 14);

        alBirthday = LocalDate.of(1903, Month.JULY, 14);

        // 使用 Month 枚举

        out.println("alBirthday: " + alBirthday);

        LocalDate programmersDay = LocalDate.of(2018, 1, 31).plusDays(255);

        // 9月13日，在闰年将会是9月12日

        out.println("programmersDay: " + programmersDay);

        LocalDate independenceDay = LocalDate.of(2018, Month.JULY, 4);

        LocalDate christmas = LocalDate.of(2018, Month.DECEMBER, 25);

        out.println("until christmas: " + independenceDay.until(christmas));

        out.println("until christmas: " + independenceDay.until(christmas, ChronoUnit.DAYS));

        out.println(LocalDate.of(2016, 1, 31).plusMonths(1));

        out.println(LocalDate.of(2016, 1, 31).minusMonths(1));

        DayOfWeek startLastMillennium = LocalDate.of(1900, 1, 1).getDayOfWeek();

        out.println("startLastMillennium: " + startLastMillennium);

        out.println("startLastMillennium: SATURDAY, " + DayOfWeek.plus(3));

        LocalDate start = LocalDate.of(2000, 1, 1);

        LocalDate exclusive = LocalDate.now();

        Stream<LocalDate> firstDaysOfMonth = start.datesUntil(
            exclusive,
            Period.ofMonths(1)
        );

        out.println("firstDaysOfMonth: " + firstDaysOfMonth.toList());
    }
}
```

## `java.time.LocalDate` 8

- `static LocalDate now()`：获取当前的 `LocalDate`。
- `static LocalDate of(int year, int month, int dayOfMonth)`
- `static LocalDate of(int year, Month month, int day)`：返回一个具有给定年份（1 到 12 之间的整数或 `Month` 枚举的值）和当月几号（1 到 31 之间）的日期。
- `LocalDate plusXxx(long number)`
- `LocalDate minusXxx(long number)`：返回一个通过加或减给定数量的时间单位得到的 `LocalDate`，其中 `Xxx` 是 `Days`、`Weeks`、`Months` 或 `Years` 之一。
- `LocalDate plus(TemporalAmount amountToAdd)`
- `LocalDate minus(TemporalAmount amountToSubtract)`：返回一个与此 `LocalDate` 相差给定金额的 `LocalDate`。`Duration` 和 `Period` 类实现了 `TemporalAmount` 接口。
- `LocalDate withOfMonth(int month)`
- `withOfYear(int year)`
- `withMonth(int month)`
- `withYear(int year)`：返回一个新的 `LocalDate`，其当月、当年、月份或年份更改为给定值。
- `int getOfMonth()`：获取当月的几号（1 到 31 之间）。
- `int getOfYear()`：获取一年中的第几天（1 到 366 之间）。
- `DayOfWeek getDayOfWeek()`：获取星期几，返回 `DayOfWeek` 枚举的值。
- `Month getMonth()`
- `int getMonth()`：以 `Month` 枚举的值获取月份，或作为 1 到 12 之间的数字获取。
- `int getYear()`：获取年份，范围在 -999,999,999 到 999,999,999 之间。
- `Period until(ChronoLocalDate endDateExclusive)`：获取直到指定的结束日期。`ChronoLocalDate` 接口由 `LocalDate` 和非格里哥日历的日期类实现。
- `boolean isBefore(ChronoLocalDate other)`
- `boolean isAfter(ChronoLocalDate other)`：如果此日期在给定日期之前或之后，则返回 `true`。
- `boolean isLeapYear()`：如果年份是闰年则返回 `true`——即能被 4 整除但不能被 100 整除，或者能被 400 整除。该算法适用于所有年份，尽管这在历史上是不准确的。闰年是在 -46 年发明的，涉及 100 和 400 整除的规则是在 1582 年的格里哥日历改革中引入的。
- `Stream<LocalDate> datesUntil(LocalDate endDateExclusive)`
- `Stream<LocalDate> datesUntil(LocalDate endDateExclusive, Period step)`：返回一个从此 `LocalDate` 到结束的日期流，步长为 1 或给定的 `Period`。

## `java.time.Period` 8

- `static Period of(int years, int months, int days)`
- `Period ofXxx(int number)`：返回一个具有给定数量时间单位的 `Period`，其中 `Xxx` 是 `Days`、`Weeks`、`Months` 或 `Years`。
- `int getXxx()`：获取此 `Period` 的时间单位数量，其中 `Xxx` 是 `Days`、`Months` 或 `Years`。
- `Period plusXxx(long number)`
- `Period minusXxx(long number)`：返回一个通过加或减给定数量的时间单位得到的 `Period`，其中 `Xxx` 是 `Days`、`Months` 或 `Years`。
- `Period plus(TemporalAmount amountToAdd)`
- `Period minus(TemporalAmount amountToSubtract)`：返回一个与此 `Instant` 相差给定金额的时间。`Duration` 和 `Period` 类实现了 `TemporalAmount` 接口。
- `Period withXxx(int number)`：返回一个新的 `Period`，其天、月或年更改为给定数字，其中 `Xxx` 是 `Days`、`Months` 或 `Years`。

## 6.3. 日期调整器（Date Adjusters）

对于调度应用程序，你通常需要计算如“每月第一个星期二”之类的日期。`TemporalAdjusters` 类提供了许多用于常用调整的静态方法。你可以调整调整器方法的结果。例如，一个月的第一个星期二可以这样计算：

```java
LocalDate firstTuesday =
    LocalDate.of(year, month, 1)
        .with(TemporalAdjusters.nextSame(DayOfWeek.TUESDAY));
```

一如既往，该方法返回一个新的 `LocalDate`，而不修改原始对象。本节末尾的 API 注释显示了可用的调整器。你可以实现 `Temporal` 接口来创建自己的调整器。这里步长为 1 或给定的 `Period`，用于计算下一个周期的调整器。

| `java.time.LocalDate` 9 |
| :--- |
| `with(TemporalAdjuster)`：返回使用给定调整器调整此日期的结果。 |

| `java.time.temporal.TemporalAdjusters` 9 |
| :--- |
| `static next(DayOfWeek dayOfWeek)`：返回一个将日期调整到下一个指定周期的调整器。 |
| `static nextSame(DayOfWeek dayOfWeek)`：返回一个将日期调整到下一个或相同周期的调整器。 |
| `static previous(DayOfWeek dayOfWeek)`：返回一个将日期调整到上一个周期的调整器。 |
| `static previousOrSame(DayOfWeek dayOfWeek)`：返回一个将日期调整到上一个或相同周期的调整器。 |
| `static dayOfWeekInMonth(int n, DayOfWeek dayOfWeek)`：返回一个将日期调整到月份第 `n` 个指定周期的调整器。 |
| `static lastInMonth(DayOfWeek dayOfWeek)`：返回一个将日期调整到月份最后一个指定周期的调整器。 |
| `static firstDayOfMonth()`：返回一个将日期调整到每月第一日的调整器。 |
| `static firstDayOfNextMonth()`：返回一个将日期调整到下个月第一日的调整器。 |
| `static firstDayOfNextYear()`：返回一个将日期调整到明年第一日的调整器。 |
| `static lastDayOfMonth()`：返回一个将日期调整到本月最后一日的调整器。 |
| `static lastDayOfYear()`：返回一个将日期调整到当年最后一日的调整器。 |

## 6.4. 本地时间（Local Time）

`LocalTime` 表示一天中的时间，例如 15:30:00。你可以通过 `now` 或 `of` 创建实例：

```java
LocalTime rightNow = LocalTime.now();

LocalTime bedtime = LocalTime.of(22, 30); // 或 LocalTime.of(22, 30, 0)
```

API 注释显示了本地时间的常用操作。加和减操作会在 24 小时内环回。例如：

```java
LocalTime wakeup = bedtime.plusHours(8); // wakeup 是 6:30:00
```

> 注意：`LocalTime` 不涉及上午/下午。这种区分被留给格式化器处理——请参见第 6.6 节。

有一个名为 `LocalDateTime` 的类表示日期和时间。该类适用于存储固定时区中的时间点——例如，课程或事件的日程表。然而，如果你需要创建跨越夏令时的类，或者需要处理来自不同时区的用户，你应该使用我们接下来要讨论的 `ZonedDateTime` 类。

### `java.time.LocalTime` 8

- `static LocalTime now()`：获取当前的 `LocalTime`。
- `static LocalTime of(int hour, int minute)`
- `static LocalTime of(int hour, int minute, int second)`
- `static LocalTime of(int hour, int minute, int second, int nanoSecond)`：产生一个具有给定小时（0 到 23 之间）、分钟（0 到 59 之间）、秒和纳秒（0 到 999,999,999 之间）的时间。
- `LocalTime plusXXX(long number)`
- `LocalTime minus(long number)`：产生通过增加或减去给定时间单位得到的时间，其中 `XXX` 是小时、分钟、秒或纳秒。
- `LocalTime plus(TemporalAmount amountToAdd)`
- `LocalTime minus(TemporalAmount amountSubtract)`：产生一个与此 `LocalTime` 偏移给定数量的 `LocalTime`。
- `LocalTime withXXX(int value)`：返回一个新的 `LocalTime`，其时间更改为给定值，其中 `XXX` 是纳秒、秒、分钟或小时。
- `int getHour()`：获取小时（0 到 23 之间）。
- `int getMinute()`
- `int getSecond()`：获取分钟或秒（0 到 59 之间）。
- `int getNano()`：获取纳秒（0 到 999,999,999 之间）。
- `int toZeroOfDay()`
- `long toNanoOfDay()`：产生自午夜以来的秒和纳秒。
- `boolean isBefore(LocalTime other)`
- `boolean isAfter(LocalTime other)`




如果此日期在给定日期之前或之后，则返回 `true`。

## 6.5 时区时间

时区，也许因为像 `America/New_York` 这样的旋转，完全是人类的创造，比地球不规则旋转引起的复杂性还要混乱。在一个理性的世界里，我们都应该遵循格林威治的钟表，有些人可能 `02:00` 吃午饭，另一些则在 `22:00` 吃。我们的胃会解决问题的。这在中国实际上是实现的，那里跨越四个标准时区。在其他地方，我们拥有边界不规则且移动的时区，更糟糕的是夏令时。

尽管时区对开明者来说可能是反复无常，但它们是生活事实。当你实现一个日历应用程序时，它需要适用于从一个国家到另一个国家的人。当你在纽约 `10:00` 有一个电话会议，但恰好在柏林时，你应该被提醒当地时间。

互联网分配编号机构（IANA）维护着全球所有已知时区的数据库（<https://www.iana.org/time-zones>），该数据库每年更新几次。大部分更新涉及夏令时规则的更改。Java 使用 IANA 数据库。

每个时区都有一个 ID，可以通过 `ZoneId.getAvailableZoneIds` 获取。要找到所有可用时区，调用 `ZoneId.getAvailableZoneIds`。在写作时，有 600 个 ID。

给定一个时区：

```java
ZonedDateTime apolloillaunch = ZonedDateTime.of(
    1969, 7, 16, 9, 32, 0, 0,
    ZoneId.of("America/New_York")
);

// 1969-07-17T16:09:32-04:00[America/New_York]
```

这是一个特定的瞬间，调用 `apolloillaunch.toInstant()` 来获取 `Instant`。相反，如果你有一个瞬时时间，调用 `instant.atZone(ZoneId.of("UTC"))` 来获取格林威治皇家天文台的 `ZonedDateTime`，或使用另一个 `ZoneId` 获取地球上其他地方的时间。

> 注意：UTC 代表“协调世界时”（Coordinated Universal Time），该缩写是上述英语和法语“Temps Universel Coordiné”之间的折中方案，其特点是在两种语言中都是错误的。UTC 是格林威治皇家天文台的时间，不实行夏令时。

`ZonedDateTime` 的许多方法与 `LocalDateTime` 相同（参见本节末尾的 API 注释）。大部分是直观的，但夏令时引入了一些复杂性。

当夏令时开始时，时钟会快一小时。当你构造一个落在跳过小时的时间时会发生什么？例如，2013 年，中欧在 3 月 31 日 `2:00` 切换到夏令时。如果你尝试构造不存在的时间 3 月 31 日 `2:30`，你实际上得到的是 `3:30`。

```java
ZonedDateTime skipped = ZonedDateTime.of(
    LocalDate.of(2013, 3, 31),
    LocalTime.of(2, 30),
    ZoneId.of("Europe/Berlin")
);

// 构建了 3 月 31 日 3:30
```

相反，当夏令时结束时，时钟会拨回一小时。当你构造一个落在重复小时的时间时，会出现两个相同的本地时间。例如，2013 年，中欧在 10 月 27 日结束夏令时。如果你构造时间 10 月 27 日 `2:30`，则该本地时间会出现两次。

```java
ZonedDateTime ambiguous = ZonedDateTime.of(
    LocalDate.of(2013, 10, 27),
    LocalTime.of(2, 30),
    ZoneId.of("Europe/Berlin")
);

// 2013-10-27T02:30+02:00[Europe/Berlin]
```

一个小时后，偏移量发生了变化。当你跨越夏令时边界调整日期时也需要注意。例如，如果你为下周设置一个日期，不要增加持续时间：

```java
ZonedDateTime nextMeeting = ambiguous.plus(Duration.ofDays(7));
```

相反，使用 `Period`：

```java
ZonedDateTime nextMeeting = ambiguous.plus(Period.ofDays(7));
```

> 注意：带有 UTC 偏移的 `ZonedDateTime` 是为了专门不需要时区的应用程序设计的。

### 列表 6.3 `ZonedTimes.java`

```java
package package6;

import java.time.*;

/**
 * 此程序演示了时区时间。
 */
class ZonedTimes {
    public static void main(String[] args) {
        ZonedDateTime apolloillaunch = ZonedDateTime.of(
            1969, 7, 16, 9, 32, 0, 0,
            ZoneId.of("America/New_York")
        );

        // 1969-07-17T16:09:32-04:00[America/New_York]

        Instant instant = apolloillaunch.toInstant();

        ZonedDateTime zonedDateTime = instant.atZone(ZoneId.of("UTC"));

        ZonedDateTime skipped = ZonedDateTime.of(
            LocalDate.of(2013, 3, 31),
            LocalTime.of(2, 30),
            ZoneId.of("Europe/Berlin")
        );

        // 构建了 3 月 31 日 3:30

        ZonedDateTime ambiguous = ZonedDateTime.of(
            LocalDate.of(2013, 10, 27),
            LocalTime.of(2, 30),
            ZoneId.of("Europe/Berlin")
        );

        // 2013-10-27T02:30+02:00[Europe/Berlin]

        ZonedDateTime hourLater = ambiguous.plusHours(1);

        ZonedDateTime nextDuration = ambiguous.plus(Duration.ofDays(7));

        ZonedDateTime nextPeriod = ambiguous.plus(Period.ofDays(7));
    }
}
```

- `ZonedDateTime withZoneSameInstant(ZoneId zone)`
- `ZonedDateTime withZoneSameLocal(ZoneId zone)`

  返回一个新的指定时区的 `ZonedDateTime`，表示相同的瞬间或相同的本地时间。

- `int getOfMonth()`

  获取月份中的第几天（1 到 31 之间）。

- `int getOfYear()`

  获取一年中的第几天（1 到 366 之间）。

- `DayOfWeek getDayOfWeek()`

  获取星期，返回 `DayOfWeek` 枚举值。

- `Month getMonth()`
- `int getValue()`

  以 `Month` 枚举的值获取月份，或作为 1 到 12 之间的数字。

- `int getYear()`

  获取年份，范围在 -999,999,999 到 999,999,999 之间。

- `int getHour()`

  获取小时（0 到 23 之间）。

- `int getMinute()`
- `int getSecond()`

  获取分钟或秒（0 到 59 之间）。

- `int getNano()`

  获取 0 到 999,999,999 之间的纳秒。

- `public Zone getOffset()`

  获取与 UTC 的偏移量。偏移量范围从 -12 到 +14:00。某些时区具有小数偏移量。偏移量会随夏令时而变化。

- `LocalDate toLocalDate()`
- `LocalTime toLocalTime()`
- `LocalDateTime toLocalDateTime()`
- `Instant toInstant()`

  产生本地日期、时间或日期/时间，或者相应的 `Instant`。

- `boolean isBefore(ChronoZonedDateTime other)`
- `boolean isAfter(ChronoZonedDateTime other)`

  如果此日期/时间在指定的日期/时间之前或之后，则返回 `true`。

## 6.6 格式化与解析

`DateTimeFormatter` 类提供了三种类型的格式化器来打印日期/时间值：

- 预定义的标准格式化器（见表 6.1）
- 特定区域语言的格式化器
- 带有自定义模式的格式化器

要使用其中一种标准格式化器，只需调用其 `format` 方法：

```java
String formatted = DateTimeFormatter.ISO_OFFSET_DATE_TIME.format(apollo11launch);

// 1969-07-16T09:32:00-04:00
```

### 表 6.1：预定义格式化器

| 格式化器 | 描述 | 示例 |
|---|---|---|
| `BASIC_ISO_DATE` | 年、月、日、无分隔符的时区偏移 | `19690716-0400` |
| `ISO_LOCAL_DATE`、`ISO_LOCAL_TIME`、`ISO_LOCAL_DATE_TIME` | 分隔符 `-`、`:`、`T` | `1969-07-16`、`09:32:00`、`1969-07-16T09:32:00` |
| `ISO_OFFSET_DATE`、`ISO_OFFSET_TIME`、`ISO_OFFSET_DATE_TIME` | 与 `ISO_LOCAL_XXX` 相同，但带有时区偏移量 | `1969-07-16-04:00`、`09:32:00-04:00`、`1969-07-16T09:32:00-04:00` |
| `ISO_ZONED_DATE_TIME` | 带有时区偏移和时区 ID | `1969-07-16T09:32:00-04:00[America/New_York]` |
| `ISO_INSTANT` | UTC 格式，由 `Z` zone ID 表示 | `1969-07-16T13:32:00Z` |
| `ISO_DATE`、`ISO_TIME`、`ISO_DATE_TIME` | 与 `ISO_OFFSET_DATE`、`ISO_OFFSET_TIME` 和 `ISO_ZONED_DATE_TIME` 类似，但信息是可选的 | `1969-07-16-04:00`、`09:32:00-04:00`、`1969-07-16T09:32:00-04:00[America/New_York]` |
| `ISO_ORDINAL_DATE` | 用于 `LocalDate` 的年份和一年中的第几天 | `1969-197-0400` |
| `ISO_WEEK_DATE` | 用于 `LocalDate` 的年份、周和星期 | `1969-W29-3-04:00` |
| `RFC_1123_DATE_TIME` | 电子邮件时间戳的标准，在 RFC 822 中编码并在 RFC 1123 中更新为四位数的年份 | `Wed, 16 Jul 1969 09:32:00 -0400` |

标准格式化器主要用于机器可读的时间戳。要向人类读者展示日期和时间，请使用特定区域语言的格式化器。日期和时间都有四种样式：`SHORT`、`MEDIUM`、`LONG` 和 `FULL`——见表 6.2。

`ofLocalizedDate`、`ofLocalizedTime` 和 `ofLocalizedDateTime` 的静态方法可以创建此类格式化器。例如：

```java
DateTimeFormatter formatter =
    DateTimeFormatter.ofLocalizedDateTime(FormatStyle.LONG);

String formatted = formatter.format(apollo1launch);

// July 16, 1969 9:32:00 AM EDT
```

这些方法使用默认区域语言。要切换到不同的区域语言，只需使用 `withLocale()`：

```java
formatted = formatter.withLocale(Locale.FRENCH).format(apollo1launch);

// 16 juillet 1969 09:32:00 EDT
```

`DayOfWeek` 和 `Month` 方法拥有 `getDisplayName`，用于以不同的语言和格式提供星期和月份名称。

```java
for (DayOfWeek w : DayOfWeek.values()) {
    System.out.print(
        w.getDisplayName(TextStyle.SHORT, Locale.ENGLISH) + " "
    );
}

// 输出 Mon Thu Fri Sun
```

关于区域语言的更多信息，请参阅第 7 章。

### 表 6.2：特定区域语言的格式化

| 样式 | 日期 | 时间 |
|---|---|---|
| `SHORT` | `7/16/69` | `9:32 AM` |
| `MEDIUM` | `Jul 16, 1969` | `9:32:00 AM` |
| `LONG` | `July 16, 1969` | `9:32:00 AM` |
| `FULL` | `Wednesday, July 16, 1969` | `9:32:00 AM EDT` |

注：`java.util.DateTimeFormatter` 类旨在替代 `java.util.Date`。最后，你可以通过指定模式来自定义自己的格式。

```java
formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm");
```

```java
IO.print(w.getDisplayName(TextStyle.SHORT, Locale.ENGLISH) + " ");

}
```



# `java.time.format.DateTimeFormatter` 8

- `String format(TemporalAccessor temporal)`  
  格式化给定值。`Instant`、`LocalDate`、`LocalTime`、`LocalDateTime` 和 `ZonedDateTime` 以及许多其他类实现了 `TemporalAccessor` 接口。

- `static DateTimeFormatter ofLocalizedDate(TextStyle style)`
- `static DateTimeFormatter ofLocalizedTime(TextStyle style)`
- `static DateTimeFormatter ofLocalizedTime(Format dateTimeStyle)`
- `static DateTimeFormatter ofLocalizedDateTime(TextStyle date, TextStyle timeStyle)`  
  为给定的样式产生一个格式化器。`TextStyle` 枚举具有 `SHORT`、`MEDIUM`、`LONG` 和 `FULL` 等值。

- `static DateTimeFormatter ofPattern(String requestedTemplate)`  
  创建一个可以适应特定区域的格式化器，使用模板中指定的各个。

- `DateTimeFormatter withLocale(Locale locale)`  
  产生一个与此等价的使用给定区域的格式化器。

- `static DateTimeFormatter ofPattern(String pattern)`
- `static DateTimeFormatter ofPattern(String pattern, Locale locale)`  
  产生一个使用给定模式和区域的格式化器。请参见模式语法。

| `java.time.LocalDate` 8 |
| :--- |
| `static LocalDate parse(CharSequence text)` |
| `static LocalDate parse(CharSequence text, DateTimeFormatter formatter)` | 使用默认格式化器或给定的格式化器产生 `LocalDate` |

# `java.time.ZonedDateTime` 8

- `static ZonedDateTime parse(CharSequence text)`
- `static ZonedDateTime parse(CharSequence text, DateTimeFormatter formatter)`  
  产生一个使用默认格式化器或给定的格式化器的 `ZonedDateTime`。

# 6.7. 与旧代码的互操作

作为一个新的创建，日期和时间 API 必须与现有类进行交互——特别是无处不在的 `java.util.Date`、`java.util.GregorianCalendar` 以及 `java.sql.Date`、`java.sql.Time` 和 `java.sql.Timestamp`。

# 第 7 章 国际化

世界很大；我们希望有很多居民对你的软件感兴趣。互联网毫不费力地跨越国界障碍。另一方面，当你忽视国际受众时，你实际上是在设置一道障碍。

Java 编程语言是第一个从底层开始设计用于支持国际化的语言。从一开始，它就拥有一个有效国际化所需的本质特性：它对所有字符串使用 Unicode。Unicode 的支持使得编写能够操作世界上大多数语言字符串的 Java 程序变得简单。

许多程序员认为，使应用程序国际化所需要的只需要支持 Unicode 并翻译用户界面中的消息。然而，正如本章所示，程序的国际化远比仅仅支持 Unicode 要复杂得多。日期、时间、货币，甚至数字在世界不同部分的格式化方式也不相同。你需要一种简单的方法来为不同的语言配置菜单和按钮名称、字符串以及键盘快捷键。

在本章中，你将看到如何编写国际化的 Java 程序以及如何对日期、时间、数字、文本和 GUI 进行本地化。我将向你展示 Java 为编写国际化程序所提供的工具。本章以一个完整的示例结束——一个具有英语、德语和中文用户界面的退休金计算器。

## 7.1. 区域（Locales）

当你观察一个适应国际市场的应用程序时，你注意到的最明显的区别是语言。这种观察对于真正的国际化来说其实有点局限，因为不同国家可以共享共同语言，但你可能仍然需要做一些工作来让这两个国家的计算机用户都感到满意。正如奥斯卡·王尔德所说：“如今我们与美国确实有一切共同点，除了语言之外。”

### 7.1.1. 为什么需要区域？

当你提供程序的国际版本时，所有的程序消息都需要被翻译成本地语言。然而，仅仅翻译用户界面文本是不够的。还有许多细微的差异——例如，数字在英语和德语中的格式化方式大不相同。

数字 `123,456.78` 对于德国用户应该显示为 `123,456.78`——也就是说，小数点和十进制位分隔符的作用反过来了。日期的显示上也有类似的差异。在美国，日期（在某种程度上理性地）显示为月/日/年。德国使用更符合逻辑的日/月/年顺序，而在中国，使用习惯是年/月/日。因此，日期 `3/22/61` 对于德国用户应该呈现为 `22.03.1961`。当然，如果显式写出月份，语言之间的差异就会显而易见。英语的 `March 22, 1961` 在德语中应呈现为 `22. März 1961`，在中文中应呈现为 `1961年3月22日`。

区域（locale）捕获了此类本地偏好。每当你展示数字、日期、货币值和其他格式随语言或位置变化的项目时，你都需要使用感知区域的 API。

### 7.1.2. 指定区域

一个区域由五个部分组成：

1. 语言，由两个或三个小写字母指定，如 `en`（英语）、`de`（德语）或 `zh`（中文）。表 7.1 显示了常用代码。
2. 可选的脚本，由首字母大写的四个字母指定，如 `Latn`（拉丁）、`Cyr`（西里字母）或 `Hant`（繁体中文）。
3. 可选的国家或地区，由两个大写字母指定。
4. 可选的变体，指定杂杂特征。
5. 可选的扩展。

表 7.1：常用 639-1 语言

| 语言 | 代码 | 语言 | 代码 |
| :--- | :--- | :--- | :--- |
| 中文 | `zh` | 意大利语 | `it` |
| 丹麦语 | `da` | 日语 | `ja` |
| 荷兰语 | `nl` | 韩语 | `ko` |
| 英语 | `en` | 挪威语 | `no` |
| 法语 | `fr` | 葡萄牙语 | `pt` |
| 芬兰语 | `fi` | 西班牙语 | `es` |
| 德语 | `de` | 瑞典语 | `sv` |
| 希腊语 | `el` | 土耳其语 | `tr` |

表 7.2：常用 3166-1 国家代码

| 国家 | 代码 | 国家 | 代码 |
| :--- | :--- | :--- | :--- |
| 奥地利 | `AT` | 日本 | `JP` |
| 比利时 | `BE` | 韩国 | `KR` |
| 加拿大 | `CA` | 荷兰 | `NL` |
| 中国 | `CN` | 挪威 | `NO` |
| 丹麦 | `DK` | 葡萄牙 | `PT` |
| 芬兰 | `FI` | 西班牙 | `ES` |
| 德国 | `DE` | 瑞典 | `SE` |
| 英国 | `GB` | 瑞士 | `CH` |
| 希腊 | `GR` | 台湾 | `TW` |
| 爱尔兰 | `IE` | 土耳其 | `TR` |
| 意大利 | `IT` | 美国 | `US` |

`Locale.TAIWAN`  
`Locale.UK`  
`Locale.US`

一些预定义的区域仅指定语言而不指定地理位置：

- `Locale.CHINESE`
- `Locale.ENGLISH`
- `Locale.FRENCH`
- `Locale.GERMAN`
- `Locale.ITALIAN`
- `Locale.JAPANESE`
- `Locale.KOREAN`
- `Locale.SIMPLIFIED_CHINESE`
- `Locale.TRADITIONAL_CHINESE`

`Locale.ROOT` 具有语言中性的规则，对于机器处理的字符串非常有用。

最后，`staticAvailableLocales` 方法返回虚拟机已知的所有区域的数组。而 `availableLocales` 方法则返回一个流（stream）。

> 注意：你可以通过 `Locale.getISOLanguages()` 获取所有语言代码，通过 `Locale.getISOCountries()` 获取所有国家代码。

### 7.1.3. 默认区域

该类的静态 `getDefault` 方法最初获取由本地操作系统存储的默认区域。你可以通过调用带有不同区域的 `setDefault` 方法来更改默认的 Java 区域。

某些操作系统允许用户为显示消息和格式化指定不同的区域。例如，居住在美国的法语语者可以使用法语菜单，但货币值使用美元。

要获取这些偏好设置，请调用：

```java
Locale displayLocale = Locale.getDefault(Locale.Category.DISPLAY);

Locale formatLocale = Locale.getDefault(Locale.Category.FORMAT);
```

**注意：** 在 UNIX 中，你可以通过设置 `LC_NUMERIC`、`LC_MONETARY` 和 `LC_TIME` 环境变量为数字、货币和日期指定单独的区域。Java 不支持这些设置。

**提示：** 如果你想测试一个只有语言和国家设置的区域，可以在启动程序时在命令行提供这些设置。例如，我们将默认区域设置为 `de-CH`：

```java
java -Duser.language=de -Duser.region=CH MyProgram
```

### 7.1.4. 显示名称

一旦你有了一个区域，你可以用它做什么呢？事实证明，最初并不多。`Locale` 类中唯一有用的方法是用于识别语言和国家代码。最重要的方法是 `getDisplayName`。它返回一个描述该区域的字符串。该字符串包含晦涩的两个字母代码，但是以可以呈现给用户的形式存在的，例如：

`German (Switzerland)`

实际上，这里存在一个问题。显示名称是用默认区域生成的。这可能并不合适。如果你的用户已经选择了德语作为首选语言，你可能希望用德语呈现该字符串。你可以通过将德语区域作为参数来实现。代码如下：

```java
Locale locale = Locale.of("de", "CH");

System.out.println(locale.getDisplayName(Locale.GERMAN));
```

`Deutsch`

这个示例说明了为什么你需要 `Locale` 对象。你将它们传递给感知区域的方法，这些方法产生的文本将呈现给不同位置的用户。你将在接下来的章节中看到许多此类示例。

> **警告：** 即使是像将字符串转换为小写或大写这样平凡的操作也可能是特定区域的。例如，在土耳其区域中，字母 `I` 的小写是一个不带点的 `i`。试图通过将字符串存储在区域中来规范化字符串的程序在土耳其客户那里神秘地失败了，因为 `i` 和带点的 `i` 没有相同的小写版本。始终使用带有 `Locale` 参数的 `toLowerCase` 变体是一个好习惯。例如，尝试一下：

```java
String command = "QUIT".toLowerCase(Locale.of("tr"));

// 带有不带点的 i "quit"
```

当然，在土耳其，`Locale.getDefault()` 返回的正是该区域，因此 `"QUIT".toLowerCase()` 不同于 `"quit"`。

如果你想将英文字符串规范化为小写，你应该将英语区域传递给 `toLowerCase` 方法。对于语言中性的处理，请使用 `Locale.ROOT`。

**注意：** 你可以显式地设置输入输出操作的区域。

- 从 `Scanner` 读取数字时，可以使用 `useLocale` 方法设置它的区域。
- `String.format` 和 `PrintWriter.printf` 方法具有带有 `Locale` 参数的重载形式。

| 方法 | 说明 |
| :--- | :--- |
| `static Locale.of(String language)` | 使用给定的语言构造区域。 |
| `static Locale.of(String language, String country)` | 使用给定的语言和国家构造区域。 |
| `static Locale forLanguageTag(String languageTag)` | 与给定的语言标签对应的区域。 |
| `static Locale getDefault()` | 返回默认区域。 |
| `static void setDefault(Locale newLocale)` | 设置默认区域。 |
| `String getDisplayName()` | 返回一个描述区域的名称，用当前区域表示。 |
| `String getDisplayName(Locale inLocale)` | 返回一个描述区域的名称，用给定的区域表示。 |
| `String getLanguage()` | 返回语言代码——一个小写的两个字母 ISO 639 代码。 |
| `String getDisplayLanguage()` | 返回语言名称，用当前区域表示。 |
| `String getDisplayLanguage(Locale inLocale)` | 返回语言名称，用给定的区域表示。 |
| `String getCountry()` | 返回作为大写的两个字母 ISO 3166 国家代码。 |
| `static String[] getISOCount()` | 返回所有两个字母的国家代码，或所有 2、3 或 4 个字母的代码。 |
| `static Set<String> getISOCount(Locale.IsoCountry type)` | `type` 是枚举常量 `PART1_ALPHA2`、`PART1_ALPHA3` 和 `PART3` 之一。 |
| `String getDisplayCountry()` | 用当前区域表示的区域名称。 |
| `String getDisplayCountry(Locale inLocale)` | 用给定的区域表示的区域名称。 |
| `String toLanguageTag()` | 返回 IETF B47 标签。 |
| `String toString()` | 返回区域的表示形式。 |

## 7.2. 数字格式化

`NumberFormat` 类提供了格式化和解析数字、货币和百分比的方法。有三个子类：`DecimalFormat`、`CurrencyFormat` 和 `PercentFormat`。

要格式化数字，请遵循以下步骤：

1. 按照前面的章节获取区域。
2. 使用工厂方法获取格式化器。
3. 使用格式化器格式化值。工厂方法是 `NumberFormat` 的静态方法：
   - `getNumberInstance()`
   - `getCurrencyInstance()`
   - `getPercentInstance()`

例如，用德国格式化数字：

```java
Locale locale = Locale.GERMAN;

NumberFormat formatter = NumberFormat.getNumberInstance(locale);

double amount = 12345.78;

String result = formatter.format(amount);
```

结果是 `12345,78`。

相反，解析输入的数字，使用 `parse` 方法：

```java
Locale locale = Locale.GERMAN;

NumberFormat formatter = NumberFormat.getNumberInstance(locale);

Number input = formatter.parse("12345,78");

double x = input.doubleValue();
```




`parse` 的返回类型是抽象类型 `Number`。根据解析数字是否为浮点数，返回的对象是 `Double` 或 `Long`。如果你不关心这种区别，可以简单地使用 `Number` 类的 `doubleValue` 方法。

> **警告：** `Number` 对象不会自动拆箱——不能简单地将 `Number` 对象赋值给原始类型。相反，请使用 `doubleValue` 或 `intValue` 方法。

如果数字格式不正确，方法将抛出 `ParseException`。例如，字符串中的导空格是不允许的。（调用 `strip` 来移除）。然而，数字后的任何字符都会被忽略，因此不会抛出异常。

`getXXInstance` 工厂方法的实例实际上不是 `NumberFormat`。`NumberFormat` 是一个抽象类，实际的格式属于它的某个子类。工厂方法知道如何定位特定区域的对象。

你可以通过 `getAvailableLocales` 方法获取当前支持的区域列表。该方法返回可以获取数字格式化器的区域数组。

> **注意：** 你可以使用 `Scanner` 读取本地化的整数和浮点数。调用 `useLocale` 方法设置区域。

书籍配套代码包含一个 GUI 程序，可以让你实验数字格式化器（见图 7.1）。顶部的组合框包含所有具有数字格式化器的区域。你可以在数字、货币和百分比格式化器之间切换。每当你做出选择时，文本字段中的数字就会重新格式化。你还可以输入不同的数字并点击 `Parse` 按钮来调用 `parse` 方法，它尝试解析你输入的内容。如果你的输入解析成功，它将被传递给 `format`，并且结果将显示。如果解析失败，文本字段将显示“Parse error”（解析错误）消息。

![](img/240dbf1b84e081687f1e252bd386c684_568_0.png)

图 7.1：`NumberFormatDemo` 程序

列表 7.1 显示了数字格式浏览器的文本版本，它更容易理解。

- 列表 7.1 `v2ch07/numberFormat/NumberFormat2.java`

```java
package v2ch07.numberFormat;

import module java.base;

import v2ch07.util.Choices;

/**
 * 此程序演示了在不同区域下的数字格式化。
 */
class NumberFormatDemo2 {
   void main() {
      var locales = [Locale] NumberFormat.getAvailableLocales().clone();
      Arrays.sort(locales, Comparator.comparing(locale::getDisplayName));
      Locale locale = Choices.choose(locales, locale::getDisplayName);

      var formatters = new LinkedHashMap<NumberFormat, String>();
      formatters.put(NumberFormat.getInstance(locale), "Number");
      formatters.put(NumberFormat.getCompactInstance(locale,
         NumberFormat.Style.SHORT),
         "Compact Short");
      formatters.put(NumberFormat.getCompactInstance(locale,
         NumberFormat.Style.LONG),
         "Compact Long");
      formatters.put(NumberFormat.getPercentInstance(locale), "Percent");
      formatters.put(NumberFormat.getCurrencyInstance(locale), "Currency");
      NumberFormat format = Choices.choose(formatters);

      String operation = Choices.choose("Format", "Parse");
      if (operation.equals("Format")) {
         double number = Double.parseDouble(
         System.out.println("Enter a floating-point number to format: ") + number));
      }
      else {
         String text = IO.readln("Enter a floating-point number to parse: ");
         try {
            System.out.println(format.parse(text));
         }
         catch (ParseException e) {
            System.out.println("ParseException " + e.getMessage());
         }
      }
   }
}
```

# `java.text.NumberFormat` 1.1

- `static Locale[] getAvailableLocales()`

  返回一个 `Locale` 对象数组，其中包含 `NumberFormat` 格式化器。

- `static NumberFormat getNumberInstance()`
- `static NumberFormat getNumberInstance(Locale in)`
- `static NumberFormat getCurrencyInstance()`
- `static NumberFormat getCurrencyInstance(Locale in)`
- `static NumberFormat getPercentInstance()`
- `static NumberFormat getPercentInstance(Locale in)`

  返回一个用于当前区域或给定区域的数字、货币金额或百分比值的格式化器。

- `static NumberFormat getCompactNumberInstance()`
- `static NumberFormat getCompactNumberInstance(Locale locale, NumberFormat.Style style)`

  返回一个在当前区域和 `SHORT` 样式（`SHORT` 或 `LONG`）的紧凑数字格式化器。

- `String format(double number)`
- `String format(long number)`

  返回格式化给定的浮点数或整数后生成的字符串。

- `Number parse(String source)`

  解析给定字符串并返回数字值；如果输入字符串是一个浮点数，则返回 `Double`，否则返回 `Long`。字符串开头必须包含数字；不允许有前导空格。数字后面可以是其他字符，这些字符会被忽略。如果解析未成功，则抛出 `ParseException`。

- `void setParseIntegerOnly(boolean value)`
- `boolean isParseIntegerOnly()`

  设置或获取一个标记，指示此格式化器是否应该解析整数值。

- `void setGroupingUsed(boolean newValue)`
- `boolean isGroupingUsed()`

  设置或获取一个标记，指示此格式化器是否会输出并识别分组分隔符（例如 `100,000`）。

- `void setMinimumIntegerDigits(int newValue)`
- `int getMinimumIntegerDigits()`
- `void setMaximumIntegerDigits(int newValue)`
- `int getMaximumIntegerDigits()`
- `void setMinimumFractionDigits(int newValue)`
- `int getMinimumFractionDigits()`
- `void setMaximumFractionDigits(int newValue)`
- `int getMaximumFractionDigits()`

## 2.2.2. `DecimalFormat` 类

在大多数区域中，你在上一节中看到的 `NumberFormat` 工厂方法返回一个 `DecimalFormat` 类的实例。该类描述了全球范围内发生的格式化变化。你可以修改单个设置，也可以创建一个全新的格式化器。模式语法使得这变得更加方便。

模式描述了必需和可选的位数，以及正负数的前缀和后缀。还有特殊的设置——参见表 7.3。

考虑这个示例：

```java
var formatter = new DecimalFormat("0.00; (#)");
```

分号分隔正部分和可选的负部分。从正部分中，我们可以看到整数部分至少有一个数字，小数部分至少有两个数字。这适用于所有数字，无论正负号。负数使用会计格式——一个前缀（和后缀）。

前缀或后缀可能包含货币符号。

如果你需要在前缀或后缀中插入特殊字符，请使用引号。

### 表 7.3：`DecimalFormat` 属性

| 名称 | 描述 | 模式 |
| :--- | :--- | :--- |
|  | 数字的位数 |  |
|  | 最小整数位数 |  |
|  | 最大整数位数 |  |
|  | 最小小数位数 |  |
|  | 最大小数位数 |  |
|  | 分组分隔符 |  |
|  | 小数分隔符 |  |
|  | 货币符号 |  |
|  | 指数部分 |  |
|  | 用于正负数的标记 |  |
|  | 格式化 `Double_INFINITY`、`NEGATIVE_INFINITY` 和 `Double.NaN` |  |

### 表 7.4：`DecimalSymbols`

| 属性 | 类型 | 描述 |
| :--- | :--- | :--- |
| `currencySymbol` | `String` | 使用的如 `$` 或 `EUR` 的字符串 |
| `decimalSeparator`、`monetaryDecimalSeparator` | `char` | 用于数字或货币值的小数分隔符 |
| `exponentSeparator` | `String` | 指数前的字符串，通常为 `E` |
| `groupingSeparator`、`monetaryGroupingSeparator` | `char` | 用于数字或货币值的分组分隔符 |
| `infinity`、`NaN` | `String` | 格式化 `Double_INFINITY`、`NEGATIVE_INFINITY` 和 `Double.NaN` 的字符串 |
| `internationalCurrencySymbol` | `String` | ISO 4217 货币符号——见 7.2.3 |
| `minusSign` | `char` | 在没有模式时使用的负号 |
| `percent`、`perMill` | `char` | 用于百分比和千分比的字符 |
| `zeroDigit` | `char` | 数字 0 的字符。其他数字是随后的字符 |

假设，例如，你希望无论区域如何，都以美国风格显示分组分隔符和小数分隔符。自定义 `DecimalFormatSymbols` 和格式化器：

```java
DecimalFormatSymbols symbols = new DecimalFormatSymbols(locale);
symbols.setGroupingSeparator(',');
symbols.setDecimalSeparator('.');
DecimalFormat formatter = (DecimalFormat)
   NumberFormat.getNumberInstance(locale);
formatter.setDecimalFormatSymbols(symbols);
```

## 7.2.3. 货币

要格式化货币值，可以使用 `getCurrencyInstance` 方法。该方法并不灵活——它返回单一货币的格式化器。假设你为一位美国客户准备一份发票，其中某些金额是美元，另一些是欧元。你不能直接使用两个格式化器：

```java
NumberFormat dollarFormat =
   NumberFormat.getCurrencyInstance(Locale.US);
NumberFormat euroFormatter =
   NumberFormat.getCurrencyInstance(Locale.GERMANY);
```

你的发票看起来会很奇怪，某些值显示为 `$100,000`，而另一些显示为 `100.000 €`。（注意，欧元使用小数点，而不是逗号。）

相反，使用 `Currency` 类来控制格式化器使用的货币。你可以通过将货币标识符传递给静态 `Currency.getInstance` 方法来获取 `Currency` 对象。然后调用 `setCurrency` 方法。以下是为您的美国客户设置欧元格式化的方法：

```java
NumberFormat euroFormatter = NumberFormat.currencyInstance(Locale.US);
euroFormatter.setCurrency(Currency.getInstance("EUR"));
```

货币标识符由 ISO 4217 定义（请参 https://www.iso.org/iso-4217-currency-codes.html）。表 7.5 提供了部分列表。

## 表 7.5：货币标识符

| 货币值 | 标识符 | 数字代码 |
| :--- | :--- | :--- |
| 美元 | USD | 840 |
| 欧元 | EUR | 978 |
| 英镑 | GBP | 826 |
| 日元 | JPY | 392 |
| 人民（元） | CNY | 156 |
| 印度卢比 | INR | 356 |
| 俄罗斯卢布 | RUB | 643 |

```java
java.util.Currency 1.4

static Currency getInstance(String currencyCode)
static Currency getInstance(Locale locale)
```

返回给定的 ISO 4217 货币代码或给定 `locale` 对应的货币实例。

```java
String toString()
String getCurrencyCode()
String getNumericCode()
String getNumericCodeAsString()
```

获取此货币的 ISO 4217 字母或数字货币代码。

```java
String getSymbol()
String getSymbol(Locale locale)
```

获取该货币在默认 `locale` 或给定 `locale` 的格式化符号。例如，USD 的符号可以是 `$` 或 `US$`，取决于 `locale`。

```java
int getDefaultFractionDigits()
```

获取该货币的默认小数位数。

```java
static Set<Currency> getAvailableCurrencies()
```

获取所有可用的货币。

## 7.3. 日期和时间

当您对日期和时间进行格式化时，应该关注四个依赖于区域的问题：

- 月份和星期几的名称应以本地语言显示。
- 年、月、日的顺序会有本地偏好。
- 格列哥日历可能不是表示日期的本地偏好。
- 必须考虑所在地的时间。

`java.time` 包中的 `DateTimeFormatter` 类处理了这些问题。从表 7.6 中选择一种格式化样式。

```java
FormatStyle style = . . . ; // FormatStyle.SHORT, FormatStyle.MEDIUM 中的之一
DateTimeFormatter dateTimeFormatter = DateTimeFormatter.ofLocalizedDate(style);
DateTimeFormatter dateTimeFormatter = DateTimeFormatter.ofLocalizedTime(style);
DateTimeFormatter dateTimeFormatter = DateTimeFormatter.ofLocalizedDateTime(style);
// 或者 DateTimeFormatter.ofLocalizedDateTime(dateStyle, timeStyle)
```

这些格式化器使用当前的 `locale`。要使用不同的 `locale`，请使用 `withLocale` 方法：

```java
DateTimeFormatter formatter = DateTimeFormatter
   .ofLocalizedDate(style)
   .withLocale(locale);
```

现在您可以格式化 `LocalDate`、`LocalDateTime`、`LocalTime` 或 `zonedDateTime`：

```java
ZonedDateTime appointment = . . . ;
String formatted = formatter.format(appointment);
```

## 表 7.6：日期和时间格式化样式

| 样式 | 日期 | 时间 |
| :--- | :--- | :--- |
| `SHORT` | 7/16/69 | 9:32 AM |
| `MEDIUM` | Jul 16, 1969 | 9:32:00 AM |
| `LONG` | July 16, 1969 | 9:32:00 AM EDT in en-US, 9:32:00 MSZ in de-DE（仅限 `ZonedDateTime`） |




| FULL | Wednesday, July 16, 1969 | 9:32:00 AM EDT in en-US, 9:32 Uhr MSZ in de-DE（仅限 `ZonedDateTime`） |

> 注意：我们使用了 `java.time` 包中的 `DateTimeFormatter` 类。还有一个旧的 `java.text.DateFormat` 类可以与 `Date` 和 `Calendar` 对象一起使用。

可以使用 `LocalDate`、`LocalDateTime`、`LocalTime` 或 `ZonedDateTime` 的静态解析方法来解析字符串中的日期或时间：

```java
LocalTime time = LocalTime.parse("9:32 AM", formatter);
```

这些方法不适用于解析人类输入，至少在没有预处理的情况下不是。例如，美国的短时间格式化器可以解析 `"9:32 AM"`，但不能解析 `"9:32AM"` 或 `"9:32 am"`。

> 注意：日期格式化器会解析不存在的日期（例如 11 月 31 日），并将其调整为该月的最后一天。

有时，您只需要显示星期几和月份的名称，例如在日历应用程序中。调用 `DayOfWeek` 和 `Month` 枚举的 `getDisplayName` 方法。

```java
for (Month m : Month.values())
    System.out.println(m.getDisplayName(TextStyle, locale));
```

表 7.7 显示了文本样式。`STANDALONE` 版本用于在格式化日期之外显示。例如，在芬兰语中，1 月在日期内部是 `"tammikuuta"`，但单独使用时是 `"tammikuu"`。

## 表 7.7：`java.time.format.TextStyle` 枚举的值

| 样式 | 示例 |
| --- | --- |
| FULL / FULL_STANDALONE | January |
| SHORT / SHORT_STANDALONE | Jan |
| NARROW / NARROW_STANDALONE | J |

> 注意：每周的第一天可以是星期六或星期日。

例如，以下五个字符串根据 `compareTo` 方法进行排序：

- America
- Zulu
- able
- zebra
- Åström

对于字典排序，你可能希望将大写和小写字母视为等同。对于英语母语者来说，示例单词列表的排序如下：

- able
- America
- Åström
- zebra
- Zulu

然而，这种顺序对于瑞典用户来说是不可接受的。在瑞典语中，字母 Å 与字母 A 不同，并且它排在字母 Z 之后！这意味着，瑞典用户会希望单词按以下方式排序：

- able
- America
- zebra
- Zulu
- Åström

要获取一个与区域敏感的比较器，请调用静态 `Collator.getInstance` 方法：

```java
Collator coll = Collator.getInstance(locale);
words.sort(coll); // Collator implements Comparator<Object>
```

> 注意：从 Java 21 开始，你可以使用扩展来指定特殊的比较器。例如，语言标记为 `sv-u-co-trad` 的区域使用传统的瑞典语排序，它不区分 `"v"` 和 `"w"`。

由于 `Collator` 类实现了 `Comparator` 接口，你可以将 `Collator` 对象传递给 `List.sort(Comparator)` 方法来对字符串列表进行排序。

比较器有几个高级设置。你可以设置比较器的强度（strength）来调整其选择性。字符差异被分为初级（primary）、次级（secondary）或三级（tertiary）。例如，在英语中，“A”和“Z”之间的差异被认为是初级的，“A”和“Å”之间的差异是次级的，而“A”和“a”之间的差异是三级的。

通过将比较器的强度设置为 `Collator.PRIMARY`，你告诉它只关注初级差异。通过将强度设置为 `Collator.SECONDARY`，你指示比较器考虑次级差异。也就是说，当强度设置为“secondary”或“tertiary”时，两个字符串更有可能是不同的，如表 7.8 所示。

## 表 7.8：不同强度的排序（英语区域）

| 初级 | 次级 | 三级 |
| --- | --- | --- |
| Angstrom = Ångström | Angstrom ≠ Ångström | Angstrom ≠ Ångström |
| Able = able | Able = able | Able ≠ able |

当强度设置为 `Collator.IDENTICAL` 时，则不允许任何差异。此设置主要与一个相当技术性的比较器设置——分解模式（decomposition mode）结合使用，我们稍后讨论。

偶尔，一个字符或字符序列在 Unicode 中可以被描述为多种形式。例如，“Å”可以使用 Unicode U+00C5，也可以表示为一个“A”（U+0065）后跟一个“̈”（组合上音符号；U+030A）。更令人惊讶的是，字母序列“ffi”可以使用单个字符“Latin 小写字母连字 ffi”（代码为 U+FB03）来表示。（有人认为这只是显示问题，不应导致不同的 Unicode 字符，但规则不是由我们制定的。）

Unicode 标准为字符串定义了四种规范化形式（D、KD、C 和 KC）。详情请参阅 <https://www.unicode.org/unicode/reports/tr15/tr15-23.html>。

在规范化形式 C 中，带重音的字符总是组合的。例如，“A”和组合符号“°”的序列被组合成单个字符“Ä”。在形式 D 中，带重音的字符总是分解为它们的基字母和组合重音：“Ä”被转换为“A”后跟“°”。形式 KC 和 KD 也会将此类字符分解为连字或商标符号。

你可以选择你希望比较器使用的规范化程度。`Collator.NO_DECOMPOSITION` 值完全不对字符串进行规范化。此选项速度更快，但可能不适用于以多种形式表示字符的文本。默认的 `Collator.CANONICAL_DECOMPOSITION` 使用规范化形式 D。它对于包含重音符号但不包含连字的文本很有用。最后，“全分解”使用规范化形式 KD。示例请参见表 7.9。

## 表 7.9：不同分解模式之间的差异

| 无分解 | 规范化分解 | 全分解 |
| --- | --- | --- |
| Ä ≠ A° | Ä = A° | Ä = A° |
| TM ≠ TM | TM = TM | TM = TM |

让比较器多次分解字符串是浪费的。如果一个字符串多次与其他字符串进行比较，你可以将分解结果保存在一个排序键（collation key）对象中。

`getCollationKey` 方法返回一个 `CollationKey` 对象，你可以将其用于进一步的快速比较。这是一个示例：

```java
String a = . . ++;
CollationKey aKey = coll.getCollationKey(a);
if(aKey.compareTo(coll.getCollationKey(b)) == 0) // 快速比较
. .
```

最后，即使你不进行排序，可能也想将字符串转换为规范化形式——以便在数据库中存储字符串或与其他程序通信。`java.text.Normalizer` 类执行规范化过程。示例：

```java
String name = "Åström";
String normalized = Normalizer.normalize(name, Normalizer.Form.NFD);
// 使用规范化形式 D
```

规范化后的字符串包含字符。规范化形式 C 将文本中的“Å”和“ö”替换为“A”和“o”。规范化形式 C 最适合存储。根据更改比较器、强度或分解模式，列表将重新排序。图 7.3 显示了不同设置下的单词顺序。`collator.getInstance(locale)` 让你对区域进行实验。

### 图 7.3：排序演示

```java
package collation;

import java.text.*;
import java.util.*;

/**
 * 此程序演示了不同区域下的字符串排序。
 */
class CollationDemo {
    void main() {
        var locales = (Locale[]) Collator.getAvailableLocales();
        Collator collator = Collator.getInstance(locale);

        List<String> strings = new ArrayList<>();
        strings.add("America");
        strings.add("able");
        strings.add("zebra");
        strings.add("Åström");
        strings.add("office");

        collator.setStrength(Collator.PRIMARY);
        collator.setDecomposition(Collator.CANONICAL_DECOMPOSITION);

        strings.sort(collator);

        for (int i = 0; i < strings.size(); i++) {
            String s = strings.get(i);
            if (i > 0 && collator.compare(s, strings.get(i - 1)) == 0) {
                System.out.print(" ");
            }
            System.out.println(s);
        }
    }
}
```

规范化后的字符串包含字符。规范化形式 C 将文本中的“Å”和“ö”替换为“A”和“o”。规范化形式 C 最适合存储。根据更改比较器、强度或分解模式，列表将重新排序。图 7.3 显示了不同设置下的单词顺序。`collator.getInstance(locale)` 让你对区域进行实验。

## `java.text.Normalizer`

- `static String normalize(CharSequence str, Normalizer.Form form)`：返回 `str` 的归一化形式。`form` 值可以是 `NFD`、`NFKD`、`NFC` 或 `NFKC` 之一。

## 7.5. 格式化

Java 拥有 `MessageFormat` 类，用于格式化带有部分的文本。它与使用 `printf` 方法格式化类似，但它支持本地化以及数字和日期的格式。我们将在接下来的章节中检查该机制。

### 7.5.1. 格式化和日期

这是一个典型的消息格式字符串：

```text
"On {2}, {0} destroyed {1} houses and caused {3} damage."
```

括号中的数字是实际名称和值的占位符。静态方法 `MessageFormat.format` 允许你为变量替换值。这是一个“可变参数”方法，因此你可以如下所示提供参数：



```java
String msg = MessageFormat.format("On {2}, {0} destroyed {1} houses and caused {3} damage.",
"hurricane", new GregorianCalendar(1999, 0, 1).getTime(), 10.0E8);
```

在这个示例中，占位符`{0}`被替换为`"hurricane"`，`{1}`被替换为`99`，依此类推。

我们示例的结果是字符串：

```text
On 1/1/99 12:00 AM, a hurricane destroyed 99 houses and caused 100,000,000 of damage.
```

这只是开始，但并不完美。我们不想显示时间`"12:00 AM,"`，而且我们希望损害金额以货币值的形式打印。这样做的方法是为某些占位符提供可选的格式：

```text
"On {2,date,long}, a {0} destroyed {1} houses and caused {3,number,currency} of damage."
```

此示例代码打印：

```text
On January 1, 1999, a hurricane destroyed 99 houses and caused $100,000,000 of damage.
```

通常情况下，占位符索引后面可以跟着类型和样式。用逗号分隔索引、类型和样式。类型可以是任意一种：

- `number`
- `time`
- `date`
- `choice`

如果类型是`number`，则样式可以是：

- `integer`
- `currency`
- `percent`

或者它可以是一个`DecimalFormat`模式，例如`$,##0`——参见第 7.2.2 节的可能格式。

如果类型是`time`或`date`，则样式可以是：

- `short`
- `medium`
- `long`
- `full`

或者一个日期格式模式，例如`yyyy-MM-dd`。（参见`SimpleDateFormat`类的文档获取可能的格式。）

> 注意：若要在消息格式字符串中包含大括号，请用单引号将其括起来，例如：`"A {0} is enclosed in '{' and '}' symbols"`。文本最好使用弯单引号：`"{0}'s favorite symbols are braces`。但如果你必须使用直单引号，则需要将其双写：

```java
String template = "<a href='{0}'>{1}</a>";
```

静态`MessageFormat.format`方法使用当前语言来格式化值。要使用任意语言格式化，你需要额外努力，因为没有你可以使用的“可变参数”方法。你需要将要格式化的值放入`Object[]`数组中，如下：

```java
var formatter = new MessageFormat(pattern, locale);
String message = formatter.format(new Object[] { values });
```

## `java.text.MessageFormat` 1.1

- `MessageFormat(String pattern)`
- `MessageFormat(String pattern, Locale locale)` 使用指定的模式和本地语言构造一个消息格式对象。
- `void applyPattern(String pattern)` 将消息格式对象的模式设置为指定的模式。
- `void setLocale(Locale locale)`
- `Locale getLocale()` 设置用于消息中占位符的本地语言。该语言仅用于通过调用`applyPattern`方法设置的后续模式。
- `static String format(String pattern, Object... args)` 使用`args[i]`作为占位符`{i}`的输入来格式化模式。
- `StringBuffer format(Object args, StringBuffer result, FieldPosition pos)` 格式化此`MessageFormat`的模式。`args`参数必须是一个对象数组。格式化后的字符串附加到`result`中，并返回`result`。如果`pos`等于`new FieldPosition(MessageFormat.Field.ARGUMENT)`，其`beginIndex`和`endIndex`属性将被设置为替换`{1}`占位符的文本的位置。如果不感兴趣位置信息，请提供`null`。

## `java.text.Format` 1.1

- `String format(Object obj)` 根据此格式化器的规则格式化给定对象。此方法调用`format(obj, new StringBuffer(), new FieldPosition(0)).toString()`。

## 7.5.2. `Choice`格式

让我们仔细观察前一部分的模式：

```text
"On {2}, a {0} destroyed {1} houses and caused {3} of damage."
```

如果我们将灾难占位符`{0}`替换为`"earthquake"`，该句子在英语中是不符合语法的：

- `On January 1, 1999, a earthquake destroyed . .`

我们真正想做的是将冠词“a”整合到占位符中：

```text
"On {2}, {0} destroyed {1} houses and caused {3} of damage."
```

静态`MessageFormat.format`方法使用当前语言来格式化值。要使用任意语言格式化，你需要额外努力，因为没有你可以使用的“可变参数”方法。你需要将要格式化的值放入`Object[]`数组中，如下：

```java
var formatter = new MessageFormat(pattern, locale);
String message = formatter.format(new Object[] { values });
```

```java
while (end != BreakIterator.DONE) {
  String segment = s.substring(start, end);
  start = end;
  end = iter.next();
  IO.println(segment);
}
```

这里有四种迭代器，由这些静态方法返回：

- `getInstanceOf`方法产生一个用于扩展文本字符簇（grapheme clusters）的迭代器——即产生可见字符的 Unicode 序列。
- `getWordInstance`方法产生一个可以生成单词或单词分隔符的迭代器。你需要根据情况判断每个段落的类型。
- `getSentenceInstance`方法的迭代器将文本分割成句子。
- `getLineInstance`迭代器产生行。

每个方法都有两个版本：一个是不带参数的，使用默认区域（locale），另一个是带有`Locale`参数的版本。

> 提示：与其使用`BreakIterator`遍历扩展文本字符簇，您可以使用正则表达式：

```java
String[] clusters = s.split("\b{g}");
```

## 7.7. 文本输入与输出

如你所知，Java 编程语言本身完全基于 Unicode。然而，在西欧国家，Windows 和 Mac OS 仍然支持旧字符编码，如 Windows-1252 或 Mac Roman；而在台湾则是 Big5。因此，通过文本与用户通信并没有想象中那么简单。接下来的章节将讨论你可能会遇到的复杂情况。

### 7.7.1. 文本文件

现在，使用 UTF-8 保存和加载文本文件是最好的。你可能需要处理旧文件。如果你知道预期的字符编码，可以在读写文本文件时指定它：

```java
Charset windows1252 = Charset.forName("Windows-1252");
var out = new PrintWriter(filename, windows1252);
```

为了猜测用户偏好的编码，可以使用源自执行 Java 虚拟机的“原生编码”。从 Java 18 开始，该名称即为系统属性`native.encoding`的值。

在 Java 18 之前，原生编码是默认字符集，你可以通过静态方法`Charset.defaultCharset()`获取它。

### 7.7.2. 行结束符

在 Windows 上，文本文件预期每行末尾是`\r\n`，而基于 UNIX 的系统只需要一个`\n`字符。现在，大多数 Windows 程序可以处理`\n`，但旧程序和控制台可能会给用户带来麻烦。

使用`println`方法写入的任何行都会正确终止。唯一的问题是你打印了包含`\n`字符的字符串。它们不会自动修改以产生行格式结束符。

与其在字符串中使用`\n`，你可以使用`printf`和`%n`格式说明符来产生取决于平台的行结束符。例如：

```java
out.printf("Hello%World%n");
```

在 Windows 上产生：

```text
Hello\r\nWorld\r\n
```

在其他地方产生：

```text
Hello\nWorld\n
```

### 7.7.3. 控制台

如果你编写了通过`IO`、`System.in.out`或`System.console()`与用户通信的程序，你就必须面对控制台可能使用与默认字符集不同的字符编码的可能性。这在 Windows 上使用`cmd`终端时尤为明显。在美版 Windows 11 中，命令 shell 仍使用源自 1982 年 IBM 个人电脑的过时 IBM 编码。`Charset.defaultCharset()`方法将返回 Windows-1252 字符集，这非常不同。例如，欧元符号 € 存在于 Windows-1252 中但在 IBM437 中不存在。当你调用：

```java
IO.println("100 €");
```

控制台将显示：

```text
100 ?
```

理想情况下，你的用户应该将控制台切换到 UTF-8。在 Windows 中，命令是：

```bash
chcp 65001
```

从 Java 18 开始，这就足够让 Java 在控制台中使用 UTF-8 了。在之前的版本中，还有必要通过文件编码属性设置平台编码：

```bash
java -Dfile.encoding=UTF-8 MyProgram
```

如果你无法让用户更改控制台编码，你可以查出它是什么。从 Java 18 开始，系统属性`stdout.encoding`和`stderr.encoding`可以为你提供这些信息。你也可以在命令行上更改设置。

你也可以调用`System.console().charset()`，前提是`System.console()`不为空。

> 警告：如果你从新的`Scanner(System.in)`获取用户输入，该扫描器使用的是默认字符集而不是控制台字符编码。如果它们不匹配，这对键盘输入将无效。如果`System.console()`不为空，请改用`new Scanner(System.console()).reader()`。

### 7.7.4. UTF-8 字节顺序标记（BOM）

如前所述，可能时对文本文件使用 UTF-8 是一个好主意。然而，如果你的应用程序必须读取其他程序创建的 UTF-8 文本文件，就会遇到另一个潜在问题。将字符 U+FEFF 作为文件的“字节顺序标记”是完全合法的。在 UTF-16 编码中，每个代码单元都是两个字节，字节顺序告诉读者文件使用的是“大端序”还是“小端序”字节。UTF-8 是单字节编码，因此不需要指定字节顺序。如果文件以字节 0xEF 0xBB 0xBF 开头，它就是一个 UTF-8 字节顺序标记。然而，Unicode 标准不建议对 UTF-8 使用它。

### 7.7.5. 源文件的字符编码

在本地化应用程序时，你可能会有大量的消息字符串、按钮标签等需要翻译。现在配置文本编辑器和开发环境使用 UTF-8 处理源文件已经很容易。Java 编译器默认期望 UTF-8。在较早版本中，运行编译器如下：

```bash
javac -encoding UTF-8 MyProgram.java
```

## 7.8. 资源包（Resource Bundles）

在本地化应用程序时，你会产生一组资源包。每个资源包是一个属性文件或类，用于描述特定区域的项目（如消息等）。对于每个资源包，你都必须为支持的所有区域提供版本。

### 7.8.1. 资源包的定位

你需要为这些资源包使用特定的命名规范。例如，针对德国的资源放在文件`baseName_DE`中，而所有德语国家共享的资源放在`baseName_de`中。通常情况下，使用：

```text
baseName_language_country
```

用于所有特定国家的资源，以及：

```text
baseName_language
```

用于所有特定语言的资源。最后，作为回退，你可以将默认值放在一个没有任何后缀的文件中。

要加载包（bundle），请使用命令：

```java
ResourceBundle currentResources =
ResourceBundle.getBundle(baseName, currentLocale);
```

`getBundle`尝试加载与当前语言和国家匹配的当前区域（locale）的包。如果失败，将依次去掉国家和语言。然后对默认区域（default locale）进行相同的查找，最后查询默认的包文件。即使该尝试失败，该方法也会抛出`MissingResourceException`。

也就是说，`getBundle`尝试加载以下包：

```text
baseName_currentLocaleLanguage_currentLocaleCountry
baseName_currentLocaleLanguage
baseName_defaultLocaleLanguage_defaultLocaleCountry
baseName_defaultLocaleLanguage
baseName
```

一旦`getBundle`方法找到了一个包（例如`baseName_de_DE`），它仍然会继续查找`baseName_de`和`baseName`。如果这些包存在，它们将成为资源层级中`baseName_DE`包的父包。稍后在查找资源时，如果在当前包中查找未成功，则会查找父包。也就是说，如果在`baseName_de_DE`中没有找到特定资源，则也会查询`baseName_de`和`baseName`。

这显然是一个非常有用的服务——手动编写它将非常繁琐。Java 编程语言的资源包机制会自动定位与给定区域最匹配的条目。在现有程序中添加越来越多的本地化内容是很容易的——你只需要创建额外的资源包即可。

> 注意：如果一个区域具有脚本（script）或变体（variant），查找过程将变得复杂得多。请参见方法`ResourceBundle.Control.getCandidateLocales`的文档以获取详细细节。

> 提示：你不需要将应用程序的所有资源都放在一个包中。你可以为按钮标签准备一个包，为错误消息准备一个包，依此类推。

### 7.8.2. 属性文件（Property Files）

字符串的国际化非常简单。你将所有字符串放入类似于`MyProgramStrings.properties`的属性文件中。这是一个简单的文本文件，每行一个键/值对。一个典型的文件看起来如下：

```properties
computeButton=Rechnen
colorName=black
defaultPointSize=210×297
```

然后，按照上一节的描述为你的属性文件命名，例如：

```text
MyProgramStrings.properties
MyProgramStrings_en.properties
MyProgramStrings_de_DE.properties
```

你可以简单地加载包：

```java
ResourceBundle bundle =
ResourceBundle.get("MyProgramStrings", locale);
```

要查找特定字符串，请调用：

```java
String computeButtonLabel = bundle.getString("computeButton");
```

属性文件以 UTF-8 格式编码。

> 警告：在 Java 9 之前，存储属性必须使用 ASCII 文件，非 ASCII 字符必须使用`\xxxx`记法进行编码。例如，`"colorName=Grün"`必须指定为：

### 7.8.3. 包类（Bundle Classes）

为了提供不是字符串的资源，请定义扩展`ResourceBundle`类的类。使用标准的命名规范为你的类命名，例如：

```text
MyProgramResources.java
MyProgramResources_en.java
MyProgramResources_de_DE.java
```

使用与加载属性文件相同的`getBundle`方法加载该类：

```java
ResourceBundle bundle = ResourceBundle.getBundle("MyProgramResources", locale);
```

> 警告：在搜索包时，当两个包具有相同的基名称时，类中的包优先级高于属性文件。

每个资源包类都实现了一个查找表。你需要为每个想要本地化的设置提供一个键字符串，并使用该键字符串来检索设置。例如：

```java
var backgroundColor = (Color)
bundle.getObject("backgroundColor")
double[] paperSize = (double[])
bundle.getObject("defaultPaperSize");
```

实现资源包类最简单的方法是扩展`ListResourceBundle`类。`ListResourceBundle`将你所有的资源放入一个对象数组中，然后为你进行查找。遵循以下代码：



```java
public class baseName_language_country extends
ListResourceBundle {
    private static final Object[][] contents = {
        { key1, value1 },
        { key2, value2 },};
```

```java
{
  public Object[][] getContents() { return contents; }
}
```

例如，类 `ProgramResources_de` 扩展 `ListResourceBundle`：

```java
private static final Object[][] contents = {
  "backgroundColor", Color.black },
  "defaultPaperSize", new double[] { 210, 297 }
}
public Object[][] getContents() { return contents; }
```

类 `ProgramResources_en_US` 扩展 `ListResourceBundle`：

```java
private static final Object[][] contents = {
  "backgroundColor", Color.blue },
  "defaultPaperSize", new double[] { 216, 279 }
}
public Object[][] getContents() { return contents; }
```

> 注意：纸张尺寸以毫米为单位给出的。除了美国和加拿大外，地球上的所有人都使用 ISO 216 尺寸。更多信息请参阅 <https://www.cl.cam.ac.uk/~mqk25/iso-paper.html>。

或者，你的资源包类可以扩展 `ResourceBundle` 类。那么你需要实现两个方法，用于枚举所有键以及查找给定键的值：

```
Enumeration<String> getKeys()
Object handleGetObject(String key)
```

`ResourceBundle` 的 `getObject` 方法调用你提供的 `handleGetObject` 方法。

```
java.util.ResourceBundle 1

* static ResourceBundle getBundle(String baseName, Locale locale)
* static ResourceBundle getBundle(String baseName)
```

## 7.9. 完整示例

在本节中，我们将本章的材料应用于一个本地化的退休计算器。该程序计算你是否储蓄了足够的退休金。你输入年龄、每月存款金额等（见图 7.4）。

Applet Viewer: `Retire.class`

Applet

| 语言 | English (United States) | 退休收入 $60,000.00 |
|---|---|---|
| 之前的储蓄 $10,000 | 每年贡献 $9,000.00 | 预期寿命 85 |
| 当前年龄 35 | 退休年龄 65 | 计算 |
| 通货膨胀 5% | 投资回报率 10% | |

![](img/240dbf1b84e081687f1e252bd386c684_603_0.png)

Applet 已启动。

### 图 7.4：英文版的退休计算器

文本区域和图表显示了退休账户每年的余额。如果数字在生活的后期变为负数，且图中的条形出现在 x 轴下方，说明你需要做些什么——例如，存更多钱、推迟退休、早逝或年轻一点。

该退休计算器在三个区域（英语、德语和中文）工作。以下是国际化的一些亮点：

- 标签、按钮和消息被翻译成德语和中文。你可以在 `RetireResources_de` 和 `RetireResources_zh` 类中找到它们。英语作为回退——参见 `RetireResources` 文件。
- 当区域更改时，我们会重置标签并格式化文本字段的内容。
- 文本字段处理本地格式的数字、货币和百分比。
- 计算字段使用 `MessageFormat`。格式字符串存储在每个语言的资源包中。

仅仅为了证明这是可行的，我们对条图使用了不同的颜色，取决于用户选择的语言。

图 7.5 显示了德语的输出。要查看中文字符（如图 7.6 所示），请确保你的 Java 运行时已安装并配置了中文字符。否则，中文字符将显示为“缺失字符”。

列表 7.4 显示了简化文本版本的代码，遗憾的是它没有颜色。

列表 7.5 是英语字符串的属性文件。本地化字符串位于列表 7.6（德语）和列表 7.7（中文）。

![](img/240dbf1b84e081687f1e252bd386c684_604_0.png)

# 图 7.5：德语版的退休金计算器

## Applet Viewer: `Retire.class`

| 语言 | 默认(中国) | | 退休收入 $60,000.00 |
| :--- | :--- | :--- | :--- |
| 投资 $0.00 | 每年存款 $9,000.00 | 预期寿命 $85 |
| 现金 $35 | 退休年龄 $65 | | | | |
| 通货膨胀 $5% | 投资收益率 $10% | | | |
| | | | 计 |
| | 63 | $551,904.41 |
| | 64 | $588,949.63 |
| | 65 | $629,313.01 |
| | 66 | $672,166.96 |
| | 67 | $717,275.21 |
| | 68 | $764,934.08 |
| | 69 | $815,909.55 |
| | 70 | $870,728.32 |
| | 71 | $929,533.53 |
| | 72 | $992,552.97 |
| | 73 | $1,056,865.62 |
| | 74 | $1,116,410.00 |
| | 75 | $1,112,276.14 |
| | 76 | $1,173,333.35 |
| | 77 | $1,235,365.56 |
| | 78 | $1,301,234.84 |
| | 79 | $1,372,053.53 |
| | 80 | $1,450,018.81 |
| | 81 | $1,528,059.75 |
| | 82 | $1,611,962.75 |
| | 83 | $1,705,710.87 |
| | 84 | $1,805,496.41 |
| | 85 | $1,909,521.23 |

Applet 已启动。

# 图 7.6：中文版的退休金计算器

# 列表 7.4 `v2ch07/retire2/Retire2.java`

```java
package v2ch07.retire2;
import module java.base;
import v2ch07.util.Choices;
/**
 * 此程序显示了一个退休金计算器。提示以英语、德语或
 * 中文显示。
 */
class Retire2 {
    void main(String[] args) throws Exception {
    // 获取本地化
    ResourceBundle bundle = ResourceBundle.getBundle("v2ch07.retireStrings", Locale.getDefault());
    String language = bundle.getString("language");
    Locale locales = new Locale(language, Locale.CHINA, Locale.GERMANY);
    ResourceBundle currentBundle = ResourceBundle.getBundle("v2ch07.retireStrings", locales);
    Locale currentLocale = locales;
    NumberFormat integerFormat = NumberFormat.getIntegerInstance(currentLocale);
    NumberFormat numberFormat = NumberFormat.getInstance(currentLocale);
```

```java
// 提示输入参数；
double savings = numberFormat.parse(
Double.parseDouble(bundle.get("savings") + ": "")).doubleValue();
double contributions = numberFormat.parse(
Double.parseDouble(bundle.get("contrib") + ": "")).doubleValue();
double income = numberFormat.parse(
Double.parseDouble(bundle.get("income") + ": "")).doubleValue();
int currentAge = integerFormat.parse(
Integer.parseInt(bundle.get("currentAge") + ": "")).intValue();
int retireeAge = integerFormat.parse(
Integer.parseInt(bundle.get("retireAge") + ": "")).intValue();
int deathAge = integerFormat.parse(
Integer.parseInt(bundle.get("deathAge") + ": "")).intValue();
double inflationPercent = numberFormat.parse(
Double.parseDouble(bundle.get("inflationPercent") + ": "")).doubleValue();

double investmentPercent = numberFormat.parse(
Double.parseDouble(bundle.get("investmentPercent") + ": "")).doubleValue();

// 显示值
// ... (此处代码未翻译逻辑，保持原样)
```

```java
StandardJavaFileManager stdFileManager = compiler.getStandardFileManager(diagnosticsListener, null, null);
```

## 8.1.4 从内存中读取源文件

如果你动态生成源代码，可以将其从内存中进行编译，而无需将文件保存到磁盘。使用此类来持有代码：

```java
public class StringSource extends SimpleJavaFileObject {
    private String code;

    StringSource(String name, String code) {
        super(URI.create("string:///" + name.replace(".", "/") + ".java"), Kind.SOURCE);
        this.code = code;
    }

    public CharSequence getCharContent(boolean ignoreEncodingErrors) {
        return code;
    }
}
```

然后，为你的类生成代码，并给编译器提供一个 `StringSource` 对象列表：

```java
List<StringSource> sources = List.of(
    new StringSource(className1, class1CodeString),
    new StringSource(className2, class2CodeString)
);
task = compiler.getTask(null, file, diagnosticsListener, null, null, sources);
```

## 8.1.5 将字节码写入内存

如果你动态地编译代码，则不需要将类文件保存到磁盘。你可以将它们保存到内存中并立即加载。

首先，这是一个用于持有字节的类：

```java
public class ByteArrayClass extends SimpleJavaFileObject {
    private ByteArrayOutputStream out;

    ByteArrayClass(String name) {
        super(URI.create("file:///" + name.replace(".*", "/") + ".CLASS"), Kind.CLASS);
    }

    public byte[] getContent() {
        return out.toByteArray();
    }

    public OutputStream openOutputStream() throws IOException {
        out = new ByteArrayOutputStream();
        return out;
    }
}
```

接下来，你需要配置文件管理器以使用这些类作为输出：

```java
var classes = new ArrayList<ByteArrayClass>();
StandardJavaFileManager stdFileManager = compiler.getStandardFileManager(null, null, null);
JavaFileManager fileManager = new ForwardingFileManager<>(stdFileManager) {
    public JavaFileObject getFileFor(Location location, String className, Kind kind, FileObject sibling) throws IOException {
        if (kind == Kind.CLASS) {
            ByteArrayClass outFile = new ByteArrayClass(className);
            classes.add(outFile);
            return outFile;
        } else {
            return super.getFileFor(location, className, kind);
        }
    }
};
```

要加载类，你需要一个类加载器（参见第 9 章）：

```java
public class ByteArrayClassLoader extends ClassLoader {
    private Iterable<ByteArrayClass> classes;

    public ByteArrayClassLoader(Iterable<ByteArrayClass> classes) {
        this.classes = classes;
    }

    public Class<?> findClass(String name) throws ClassNotFoundException {
        for (ByteArrayClass cl : classes) {
            if (cl.getName().equals(name.replace(".", "/") + ".class")) {
                byte[] bytes = cl.getCode();
                return defineClass(name, bytes, 0, bytes.length);
            }
        }
        throw new ClassNotFoundException(name);
    }
}
```

编译完成后，调用 `Class.forName` 方法：

```java
ByteArrayClassLoader loader = new ByteArrayClassLoader(classes);
Class<?> cl = Class.forName(className, true, loader);
```

## 8.1.6. 示例：动态 Java 代码生成

在用于动态页面的 Jakarta Server Pages（JSP）技术中，你可以将 HTML 与 Java 代码段混合，例如：

```html
<p>当前日期和时间是 <b><%= LocalDateTime.now() %></b></p>
```

JSP 引擎动态地将 Java 代码编译为 servlet。在我们的示例应用程序中，我们使用一个简单的示例，并为非常简单的工作表格式生成代码。作者将文本、Java 表达式（用反引号包含）和 Java 语句（用三个反引号包含）引入工作表中。`???` 表示一行输入。该工作表被编译为一个 Java 类，该类打印文本和表达式的值，并执行 Java 语句。这是一个示例工作表：

你的名字是什么？

```java
String name = ???;
```

你多大了？

```java
int age = Integer.parseInt(???);
```

你好，`name!` 明年你将是 `age + 1`。



这是一个极简的编程笔记本（https://docs.jupyter.org/en/latest/#what-is-a-notebook）版本。工作表被翻译成类，该类的 `main` 方法包含打印语句，用于输出文本和表达式值。语句是逐字包含的。可以想象对该程序进行增强，使其显示图像和表格，就像真正的编程笔记本一样。

列表 8.1 程序中的 `BuildSource` 方法构建了这些代码并将其放入 `StringSource` 对象中。该对象被传递给 Java 编译器。

如前一节所述，我们使用 `ForwardingJavaFileManager`，它为每个编译的类构建一个 `ByteArrayClass`。这些对象捕获了类在编译时生成的类文件。编译后，我们使用前一节中的类加载器来加载类并执行其 `main` 方法。

此示例演示了如何使用内存中的源文件和类文件进行动态编译。

# 列表 8.1 `v2ch08/compiler/CompilerDemo.java`

```java
1 package v2ch08.compiler;
2 import java.io.*;
3 import java.nio.file.*;
4 import java.util.*;
5 import javax.tools.*;
6 import javax.tools.*;
7 
8 /**
 * 演示在内存中编译 Java 代码。
9  */
10 class CompilerDemo {
11     public static void main(String[] args) throws Exception {
12         JavaCompiler compiler = ToolProvider.getJavaCompiler();
13         DiagnosticCollector<JavaFileObject> diagnostics = new DiagnosticCollector<>();
14         StandardJavaFileManager stdFileManager = compiler.getStandardFileManager(null, null, null);
15 
16         List<ByteArrayClass> classes = new ArrayList<>();
17         JavaFileManager fileManager = new ForwardingFileManager<>(stdFileManager) {
18             public JavaFileObject getFileFor(Location location, String className, Kind kind, FileObject sibling) throws IOException {
19                 if (kind == Kind.CLASS) {
20                     ByteArrayClass outFile = new ByteArrayClass(className);
21                     classes.add(outFile);
22                     return outFile;
23                 } else {
24                     return super.getFileFor(location, className, kind);
25                 }
26             }
27         };
28 
29         String className = "v2ch08.Main";
30         String worksheetName = args.length > 0 ? args[0] : "v2ch08/workbook";
31         JavaFileObject source = buildSource(className, Path.of(worksheetName));
32 
33         JavaCompilationTask task = compiler.getTask(null, fileManager, diagnostics, null, null, List.of(source));
34         boolean result = task.call();
35 
36         if (!result) {
37             for (Diagnostic<? JavaFileObject> d : diagnostics.getDiagnostics()) {
38                 System.err.println(d.getKind() + ": " + d.getMessage(null));
39             }
40             System.exit(1);
41         }
42 
43         ByteArrayClassLoader loader = new ByteArrayClassLoader(classes);
44         Class<?> mainClass = loader.loadClass(className);
45         mainClass.getMethod("main").invoke(null);
46     }
47 
48     /**
 * 构建实现工作表动作的类源码。
 * @param className 要构建的类名
 * @param worksheet 包含工作表指令的文件
 * @return 包含字符串源码的文件对象
 */
54     static JavaFileObject buildSource(String className, Path worksheet) throws IOException {
55         StringBuilder builder = new StringBuilder();
56         int n = className.lastIndexOf(".");
57         if (n >= 0) {
58             String packageName = className.substring(0, n);
59             className = className.substring(n + 1);
60             builder.append("package ").append(packageName).append("\n\n");
61         }
62         builder.append("public class ").append(className).append(" {\n");
63         builder.append("public static void main() {\n");
64         // 解析工作表的逻辑将在此处
65         builder.append("}\n");
66         builder.append("}\n");
67         return new StringSource(className, builder.toString());
68     }
69 }
```

```java
else
    builder.append(fragments[i]);
    builder.append("\n");
}
    builder.append("IO.println(\n\n");
}
    builder.append(" \n");
    return new StringSource(className, builder.toString());
}
```

## `javax.tools.Tool` 6

- `int run(InputStream in, OutputStream out, OutputStream err, String... arguments)`

  使用输入、输出、错误流以及指定的参数运行工具。成功返回 0，失败返回非零值。

- `StandardJavaFileManager`

  `getStandardFileManager(DiagnosticListener<? super JavaObject> diagnosticListener, Locale local, Charset charset)`

  获取此编译器的标准文件管理器。你可以为默认的错误报告、语言区域和字符集传递 null。

- `JavaCompiler.CompilationTask getTask(Writer out, JavaFileManager manager, DiagnosticListener<? super JavaObject> diagnosticListener, Iterable<String> options, Iterable<String> classesForAnnotationProcessing, Iterable<? extends JavaObject> sourceFiles)`

  获取一个编译任务，该任务在调用时将编译给定的源文件。详情请见上一节的讨论。

## `javax.tools.StandardJavaFileManager` 6

- `Iterable<? extends JavaObject>`

  `getJavaFileObjectsFromStrings(Iterable<String> fileNames)`

- `Iterable<? extends JavaObject>`

  `getJavaFileObjectsFromPaths(Collection<? extends Path> paths)`

- `Iterable<? extends JavaFileObject>`

  `getFileObjectsFromFiles(Iterable<? extends File> files)`

  将一系列文件名或文件转换为一系列 `JavaFileObject` 实例。

## `javax.tools.Compiler.CompilationTask` 6

- `Boolean call()`

  执行编译任务。

## `javax.tools.DiagnosticCollector<S>` 6

- `DiagnosticCollector()`

  构造一个空的收集器。

- `List<Diagnostic<? extends S>> getDiagnostics()`

  获取收集到的诊断信息。

## `javax.tools.Diagnostic<S>` 6

- `S getSource()`

  获取与此诊断关联的源对象。

- `Diagnostic.Kind getKind()`

  获取此诊断的类型——ERROR（错误）、WARNING（警告）、MANDATORY（强制）、NOTE（备注）或 OTHER（其他）。

- `String getMessage(Locale locale)`

  获取描述此诊断中提出的问题的消息。传递 null 则使用默认语言区域。

- `long getLineNumber()`

- `long getColumnNumber()`

  获取此诊断中提出的问题的位置。

```java
javax.tools.SimpleFileObject 6
```

- `CharSequence getCharContent(boolean ignoreEncodingErrors)`

  对于代表源文件的文件对象，重写此方法以产生源代码。

- `OutputStream openOutputStream()`

  对于代表类文件的文件对象，重写此方法产生一个可以写入字节码的流。

```java
javax.tools.ForwardingJavaFileManager<M extends JavaFileManager> 6
```

- `protected ForwardingJavaFileManager(M fileManager)`

  构造一个 `JavaFileManager`，它将所有调用委托给给定的文件管理器。

- `FileObject getFileForOutput(JavaFileManager.Location location, String className, Object.Kind kind, FileObject sibling)`

  如果你想用一个文件对象来写入类文件，请拦截此调用；kind 是 SOURCE、CLASS、HTML 或 OTHER 之一。

## 8.2 Java 平台的脚本语言

脚本语言是一种通过在运行时解释程序文本来避免通常的“编辑/编译/链接/运行”循环的语言。脚本语言具有许多优势：

- 快速迭代，鼓励实验
- 改变正在运行程序的行为
- 允许用户进行自定义

另一方面，大多数脚本语言缺乏对构建复杂应用程序有用的特性，例如强类型、封装和模块化。

因此，将脚本语言和传统语言的优势结合起来是非常吸引人的。脚本 API 允许你在 Java 平台上实现这一点。它允许你从 Java 程序中调用用 JavaScript、Groovy、Ruby 甚至像 Scheme 和 Haskell 这样特殊语言编写的脚本。例如，Renjin 项目（https://www.renjin.org）提供了 R 编程语言的 Java 实现（R 语言通常用于统计编程），并带有一个脚本 API 的“引擎”。

在寻找你喜欢的语言的兼容实现时，请搜索对 JSR 222 支持。（Java 规范请求 223 在集成到 Java 之前已经开发了脚本 API。）

JMeter 性能分析工具（https://tomcat.apache.org/）是一个允许用户使用 Java 脚本用任何语言编写脚本的程序示例。Maven 构建工具有一个插件（https://maven.apache.org/plugins/maven-scripting-plugin/index.html），用于用任何带有 JavaScript 引擎的语言编写构建步骤。

在后续章节中，我将为你展示如何为特定语言选择引擎、如何执行脚本，以及如何利用某些脚本引擎提供的高级功能。

### 8.2.1 获取脚本引擎

脚本引擎是一个可以执行特定语言脚本的库。当虚拟机启动时，它会发现可用的脚本引擎。要列出它们，请构造一个 `ScriptEngineManager` 并调用 `getEngineFactories` 方法。你可以询问每个工厂支持的引擎名称、MIME 类型和文件扩展名。表 8.1 显示了典型值。

本章中的示例使用了 Rhino 脚本引擎（可以在 https://github.com/mozilla/rhino 获取），它实现了一个旧版本的 JavaScript。

### 表 8.1：脚本引擎的属性

| 引擎 | 标识 | MIME 类型 | 扩展名 |
| :--- | :--- | :--- | :--- |
| JavaScript | rhino | application/javascript | text/javascript |
| Groovy | groovy | application/groovy | text/groovy |
| Renjin | Renjin | application/x-java | text/java |
| R | R | application/x-r | text/r |

## `javax.script.ScriptEngineManager` 6

- `List<EngineFactory> getEngineFactories()`

  获取所有引擎工厂列表。

- `ScriptEngine getByName(String name)`

  根据名称获取引擎。

- `ScriptEngine getByExtension(String extension)`

  根据扩展名获取引擎。

### 8.2.2 脚本评估与绑定

一旦你有了引擎，只需通过调用 `Object result = engine.eval(scriptString)` 来调用脚本。

如果存储在文件中，打开一个 `Reader` 并调用 `Object result = engine.eval(reader)`。

可以在同一个引擎上调用多个脚本。如果一个脚本定义了变量、函数或类，大多数脚本引擎会保留这些定义。例如：

```java
var manager = new ScriptEngineManager();
ScriptEngine engine = manager.getByName("javascript");
```

要确定是否安全可以并发执行脚本，请调用 `Object param = factory.getParameter("THREADING")`。返回的值之一：

- `null`：不安全。
- `"MULTITHREADED"`：安全。一个线程的影响对另一个线程可见。
- `"THREAD-ISOLATED"`：除了 MULTITHREADED 之外，每个线程维护不同的变量绑定。
- `"STATELESS"`：除了 THREAD-ISOLATED，脚本不会更改变量。

你通常会将变量绑定添加到引擎中。绑定由名称和关联的 Java 对象组成。例如，考虑以下语句：

```java
engine.put("k", 1728);
Object result = engine.eval("k + 1");
```

脚本代码从引擎作用域的绑定中读取 `k` 的定义。这特别重要，因为大多数脚本语言可以访问 Java 对象，且通常比 Java 语法简单。例如：

```java
engine.put("d", LocalDate.now());
Object result = engine.eval("d.month"); // 调用 getMonth
```



相反，你可以检索通过脚本语句绑定变量：

```java
engine.eval("n = 1728");
Object result = engine.get("n");
```

除了引擎作用域，还有一个全局作用域。添加到`ScriptEngineManager`的任何绑定对所有引擎可见。

与其将绑定添加到引擎或全局作用域，不如将其收集到一个`Bindings`对象并传递给`eval`方法：

```java
Bindings scope = engine.createBindings();
scope.put("d", LocalDate.now());
engine.eval(scriptString, scope);
```

如果一组绑定不应该对后续的`eval`调用持续，这种方法就是很有用的。

> **注意：**你可能需要引擎和全局作用域以外的作用域。例如，Web容器可能需要请求和会话作用域。但是，你需要自己处理。你需要编写一个实现`ScriptContext`接口的类来管理作用域集合。每个作用域由一个整数标识，应该优先搜索数字较小的作用域。（标准库提供了一个`SimpleScriptContext`类，但它只包含全局和引擎作用域。）

## `javax.script.ScriptEngine`

- `Object eval(String script)`
- `Object eval(Reader reader)`
- `Object eval(String script, Bindings bindings)`
- `Object eval(Reader reader, Bindings bindings)`

  *执行由字符串或`Reader`提供的脚本，受给定绑定限制。*

- `Object get(String key)`
- `void put(String key, Object value)`

  *在引擎作用域中获取或放入绑定。*

- `Bindings createBindings()`

  *创建一个适用于此引擎的空`Bindings`对象。*

## `javax.script.ScriptEngineManager`

- `Object get(String key)`
- `void put(String key, Object value)`

  *在全局作用域中获取或放入绑定。*

## `javax.script.Bindings`

- `Object get(String key)`
- `void put(String key, Object value)`

  *向此`Bindings`对象表示的作用域中获取或放入绑定。*

## 8.2.3. 重定向输入和输出

你可以通过调用脚本上下文的`setReader`和`setWriter`方法来重定向脚本的标准输入输出。例如：

```javascript
var writer = new StreamWriter();
engine.getContext().getWriter(new PrintWriter(writer, true));
```

任何使用 JavaScript `print`或`println`函数写入的输出都会发送到`writer`。

`setReader`和`setWriter`方法只影响脚本引擎的标准输入输出源。例如，如果你执行以下 JavaScript 代码：

```javascript
println("Hello");
java.lang.System.out.println("World");
```

只有第一个输出被重定向了。

Rhino 引擎没有标准输入源的概念。调用`setReader`没有效果。

## `javax.script.ScriptEngine`

- `ScriptContext getContext()`

  *获取此引擎的默认脚本上下文。*

## `javax.script.ScriptContext`

- `Reader getReader()`
- `void setReader(Reader reader)`
- `Writer getWriter()`
- `void setWriter(Writer writer)`
- `Writer getErrorWriter()`
- `void setErrorWriter(Writer writer)`

  *获取脚本用于输入的`Reader`或用于普通或错误输出的`Writer`。*

## 2.2.4. 调用脚本函数和方法

在某些脚本引擎中，你可以直接在 Java 代码中调用脚本语言函数，而无需评估调用该函数的脚本代码段。如果你允许用户使用他们选择的脚本语言实现服务，那么这将非常有用，因为你可以从 Java 调用它。

提供此功能的脚本引擎实现了`Invocable`接口。特别是，Rhino 引擎实现了`Invocable`。

要调用函数，请调用`invokeFunction`方法并传入函数名，随后是函数参数：

```javascript
// 在 JavaScript 中定义 greet 函数
engine.eval("greet(how, whom) { return how + ',', ' \n' + whom + '!' }");
```

```javascript
// 使用参数 "Hello", "World" 调用函数
result = ((Invocable) engine).invokeFunction("greet", "Hello", "World");
```

如果脚本语言是面向对象的，请调用`invokeMethod`：

```javascript
// 在 JavaScript 中定义 Greeter 类
engine.eval("""
function Greeter(how) { 
    this.how = how; 
    Greeter.prototype.welcome = function (whom) { return this.how + ',', ' + whom + '!' } 
}""");

// 构造一个实例
Object yo = engine.eval("new Greeter('Yo')");

// 在实例上调用 welcome 方法
result = ((Invocable)engine).invokeMethod(yo, "World");
```

> **注意：**Rhino 不支持现代 JavaScript 类语法。有关如何以旧方式在 JavaScript 中定义类的更多信息，请参见 Douglas Crockford (2008) 编写的 *JavaScript—The Good Parts*。

> **注意：**如果脚本引擎没有实现`Invocable`接口，你可能仍然以独立语言的方式调用方法。`ScriptEngineFactory`接口的`getMethodCallsSyntax`生成一个你可以传递给`eval`方法的字符串。然而，所有的方法参数必须绑定到名称，而`invokeMethod`可以使用任意值调用。

你可以更进一步，要求脚本引擎实现一个 Java 接口。然后你可以使用 Java 方法调用语法来调用脚本函数和方法。

细节取决于脚本引擎，但通常你需要为接口的每个方法提供一个函数。例如，考虑一个 Java 接口：

```java
public interface Greeter {
    String welcome(String whom);
}
```

如果你在 Rhino 中定义了一个同名的全局函数，你就可以通过此接口调用它：

```javascript
// 在 JavaScript 中定义 welcome 函数
engine.eval("function welcome(whom) { return 'Hello, ' + whom + '!' }");
```

```java
// 获取 Java 对象并调用 Java 方法
Greeter g = ((Invocable) engine).getInterface(Greeter.class);
result = g.welcome("World");
```

在面向对象的脚本语言中，你可以通过匹配的接口访问脚本。例如，这里是使用 Java 调用该对象的方法：

总而言之，如果你想从 Java 调用脚本代码而不必担心脚本语言，那么`Invocable`接口是有用的。

## 8.2.5. 编译脚本

某些引擎可以将脚本编译为中间形式以便高效执行。只有当你需要重复执行脚本时，编译脚本才有意义。

```java
46     IO.out.println();
47     }
48     }
49     }
50 }
```

# Listing 8.3 v2ch08/script/worksheet

```java
1 2 var name = java.lang.IO.println("What is your name? ");
3 var age = 1 * java.lang.IO.println("How old are you? ");
4
5 Hello, `name`! Next year, you will be `age + 1`.
```

## 第 9 章 - 安全

当 Java 技术首次出现时，人们兴奋的点并不是由于一个精良的编程语言，而是安全地执行通过网络传输的小程序（applets）的可能性。显然，只有当接收者确定代码不会对其机器造成破坏时，提供可执行的小程序才是有实际意义的。因此，安全从过去一直是 Java 技术设计者和用户关注的焦点。这意味着与其他语言和系统（这些系统中通常是事后考虑或作为对入侵的反应而实现的）不同，安全机制是 Java 技术不可或缺的一部分。

安全架构由三部分组成：

1. 语言和虚拟机设计特性（数组的边界检查、无未经检查的类型转换、无指针算术等等）。

2. 安全管理器，用于控制代码可以的操作（文件访问、网络访问等）。

3. 代码签名，代码作者通过这种方式可以使用标准加密算法对 Java 代码进行认证。然后，代码的用户就可以准确确定是谁创建了代码，并确保代码在签名后没有被篡改。

第一部分取得了巨大的成功。C++程序通常容易受到缓冲区溢出等攻击，但 Java 提供了强有力的保护。遗憾的是，另外两个部分表现并不理想。安全管理器非常复杂且攻击面很大。从 Java 17 开始它被弃用了。随着 applet 和 Java Web Start 的消灭——这两种用于安全交付客户端应用程序的机制——代码签名架构也实际上被废弃了。

在本书之前的版本中，安全管理器和代码签名是本章的亮点，但显然这种覆盖的需求已经不存在了。我们将首先讨论类加载器，它们在将类文件加载到虚拟机时会检查类文件的完整性。我将演示该机制如何检测对类文件的篡改。然后，你将学习用于安全相关操作的身份验证框架和加密算法。

## 9.1. 类加载器

Java 编译器将源指令转换为 Java 虚拟机的代码。虚拟机代码存储在具有`.class`扩展名的类文件中。每个类文件都包含一个类或接口的定义和实现代码。在接下来的章节中，你将看到虚拟机是如何加载这些类文件的。

### 9.1.1. 类加载过程

虚拟机只加载程序执行所需的所需的类文件。例如，假设程序执行从`MyProgram.class`开始。以下是虚拟机执行的步骤：

1. 虚拟机有一种加载类文件的机制——例如，从磁盘读取文件或从 Web 请求它们；它使用这种机制加载`MyProgram`类的内容。

2. 如果`MyProgram`类具有其他类类型的字段或超类，则它们的类文件也会被加载。（加载给定类所依赖的所有类的过程被称为类的*解析*/resolving。）

3. 然后虚拟机执行`MyProgram`中的`main`方法。

4. 如果`main`方法或`main`调的方法需要额外的类，则将加载这些类。

然而，类加载机制并不只使用单个类加载器。每个 Java 程序都至少有三个类加载器：

- 启动类加载器（bootstrap class loader）
- 平台类加载器（platform class loader）
- 系统类加载器（system class loader，有时称为应用类加载器）

启动类加载器加载模块中包含的平台类：

```java
java.base
java.datatransfer
java.desktop
java.instrument
java.logging
java.management
java.management.rmi
java.naming
java.prefs
java.rmi
java.security.sasl
java.xml
```

以及许多 JDK 内部模块。

没有与启动类加载器相对应的`ClassLoader`对象。例如：

```java
StringBuilder.class.getClassLoader()
```

返回`null`。

在 Java 9 之前，Java 平台类位于`rt.jar`文件中。现在，Java 平台是模块化的，每个平台模块都包含在 JMOD 中（见第一卷第 9 章）。平台类加载器加载未启动类加载器加载的 Java 平台类。

系统类加载器从模块路径（module path）和类路径（class path）加载应用类。

> **注意：**在 Java 9 之前，“扩展类加载器”从`jre/lib/ext`目录加载“标准扩展”，并且“背书标准覆盖”机制提供了一种用新版本覆盖某些平台类（包括 CORBA 和 XML 实现）的方法。这两种机制都已被移除。

### 9.1.2. 类加载器层级结构

类加载器之间存在父/子关系。除了启动类加载器外，每个类加载器都有一个父类加载器。类加载器会给其父类加载任何给定类的机会，只有在父类加载失败时才会加载它。例如，当要求系统类加载器加载一个平台类（例如`java.lang.StringBuilder`）时，它首先询问平台类加载器。启动类加载器。

> **警告：**在 Java 9 之前，系统类加载器是`URLClassLoader`的实例。某些程序员使用强制类型转换来访问`getURLs`方法，或者通过调用`addURLs`将 JAR 文件添加到类路径中。这现在已不再可能。

大多数情况下，你不需要担心类加载器层级。通常情况下，类是因为被其他类需要而加载的，且该过程对你是透明的。

然而，有时你需要干预并指定类加载器。考虑以下示例：

- 你的应用程序代码包含一个调用`Class.forName(classNameString)`的辅助方法。
- 该方法从一个插件类被调用。
- `classNameString`指定了插件 JAR 中的一个类。

插件作者希望该类被加载。然而，辅助方法的类是由系统类加载器加载的，而这就是`Class.forName`使用的类加载器。插件 JAR 中的类不可见。这种现象被称为类加载器反转（classloader inversion）。

为了解决这个问题，辅助方法需要使用正确的类加载器。它可以将类加载器作为参数。或者，它可以要求正确的类加载器设置为当前线程的上下文类加载器。这种策略被许多框架（例如 JAXP 和 JNDI）使用。

每个线程都有类加载器的引用，称为上下文类加载器。主线程的上下文类加载器是系统类加载器。创建新线程时，其上下文类加载器被设置为创建线程的上下文类加载器。因此，如果你什么都不做，所有线程的上下文类加载器都将被设置为系统类加载器。

然而，你可以通过调用以下代码来设置任何类加载器：

```java
Thread t = Thread.currentThread();
t.setContextClassLoader(loader);
```

辅助方法随后可以获取上下文类加载器：

```java
var url = new URL("file:///path/to/plugin.jar");
var pluginLoader = new URLClassLoader(new URL[] {url});
```

```java
Class<?> cl = pluginLoader.loadClass("mypackage.MyClass");
```

由于`URL`构造函数没有指定父类，`pluginLoader`的父类是系统类加载器。图 9.1 显示了该层级结构。

# 图 9.1: 类加载器层级结构

```java
Thread t = Thread.currentThread();
ClassLoader loader = t.getContextClassLoader();
Class<?> cl = loader.loadClass(className);
```

> **提示：**如果你编写了一个通过名称加载类的优秀方法，请让调用者能够在显式传递类加载器和使用上下文类加载器之间进行选择。不要仅仅简单地使用方法所在类的类加载器。

### 9.1.3. 将类加载器作为命名空间

每个 Java 程序员都知道，包名被用于消除命名冲突。标准库中有两个名为`Date`的类，但它们真正的名称显然是`java.util.Date`和`java.sql.Date`。简单名称只是为了方便程序员使用，并且需要包含适当的`import`语句。在运行的程序中，所有的类名都包含其包名。

然而，令你惊讶的是，你可以在同一个虚拟机中拥有两个具有相同类和包名的不同类。一个类是由其全名和类加载器决定的。这种技术对于从多个源加载代码非常有用。例如，应用程序服务器为每个应用程序使用独立的类加载器。这允许虚拟机分离来自不同应用程序的类，无论它们被命名为什么。图 9.2 展示了一个示例。假设一个应用程序服务器加载两个不同的应用程序，每个程序都有一个名为`Util`的类。由于每个类都由单独的类加载器加载，这些类是完全不同的且互不冲突。

**图 9.2：**两个类加载器加载了同名的不同类。

### 9.1.4. 编写你自己的类加载器

你可以为特殊目的编写自己的类加载器。这可以让你在将字节码传递给虚拟机之前执行自定义检查。例如，你的类加载器可能会拒绝加载一个未被标记为“已支付”的类。

要编写自己的类加载器，只需扩展`ClassLoader`类并重写方法：

```java
findClass(String className)
```



`ClassLoader` 超类的`loadClass`方法负责处理向父类的委托，并且只有当类尚未被加载且父类加载器无法加载该类时，它才会调用`findClass`。

你对该方法的实现必须执行以下操作：

1. 从本地文件系统或其他源加载该类的字节码。
2. 调用`Class`超类的`defineClass`方法将字节码呈现给虚拟机。

在[Listing 9.1](https://docs.oracle.com/javase/tutorial/java/jls/classloader.html#listing-9-1)程序中，我们实现了一个加载加密类文件的类加载器。程序向用户询问要加载的第一个类（即包含`main`方法的类）以及解密密钥。然后它使用特殊的类加载器加载指定的类并调用`main`方法。类加载器解密指定的类以及其引用的所有非系统类。最后，程序调用被加载类的`main`方法。

为了简单起见，我们忽略了密码学领域2000年的进步，并使用古老的凯撒密码来加密类文件。

> **注意：** David Kahn 的精彩著作 *The Codebreakers (Macmillan, 1967, p. 84)* 提到提德高乌是凯撒密码的历史来源。凯撒将罗马字母表中的 24 个字母移动了 3 个字母，这在当时困扰了他的对手。

当本章初次撰写时，美国政府限制了强加密方法的出口。因此，我在示例中使用了凯撒方法，因为它在出口上显然是合适的。

我们版本的凯撒密码的密钥是 1 到 255 之间的数字。要解密，只需将该密钥加到每个字节上并对 256 取模。Listing 9.2 中的`Caesar.java`程序执行了加密。

为了不混淆普通的类加载器，我们为加密类文件使用了不同的扩展名`.caesar`。

要解密，类加载器简单地从每个字节中减去密钥。在本书的配套代码中，你会找到用密钥值 3（传统的选择）加密的四个类文件。要运行加密程序，你将需要我们在`ClassLoaderDemo`程序中定义的自定义类加载器。

尝试使用`Calculator`作为类名和`3`作为解密密钥来运行该程序。一个计算器将会弹出。但如果你使用不同的密钥，类加载器将抛出异常。

加密类文件有许多实际用途（当然，前提是你使用了比凯撒密码更强的东西）。如果没有解密密钥，这些类文件是无用的。它们既不能被标准的虚拟机执行，也无法被轻易反编译。

这意味着你可以使用自定义类加载器来验证类的用户，或者在允许程序运行之前确保该程序已付费。当然，加密只是自定义类加载器的一种应用。你可以使用其他类型的类加载器来解决其他问题——例如，将类文件存储在数据库中。

### Listing 9.1

`v2ch09/classLoader/ClassLoaderDemo.java`

```java
1 package v2ch09.classLoader;
2 import module java.base;
/**
4  * 这个程序演示了一个可以
5  * 解密类文件的自定义类加载器。
6  */
7 class ClassLoader {
8   void main(String[] args) throws Exception {
9     String className = IO.println("Class name: ");
10    int decryptionKey = Integer.parseInt("decryption key: ");
11    var loader = new CryptoLoader(decryptionKey);
12    Class<?> c = loader.loadClass(className);
13    Method m = c.getMethod("main", String[].class);
14    m.invoke(null, (Object) new String[] {});
15  }
16 /**
17  * 这个类加载加密类文件。
18  */
19 class CryptoLoader extends ClassLoader {
20   private int key;
21   /**
22    * 构造一个类加载器。
23    * @param k 解密密钥
24    */
25   public CryptoLoader(int k) {
26     key = k;
27   }
28 /**
29  * 加载并解密类文件。
30  * @param name 类名
31  * @return 包含类字节的数组
32  */
33 private byte[] loadClassBytes(String name) throws IOException
34 try {
35   String cname = name.replace(".", "/") + ".caesar";
36   byte[] bytes = getClass().getResourceAsStream(cname).readAllBytes();
37   for (int i = 0; i < bytes.length; i++)
38     bytes[i] = (byte) (bytes[i] - key);
39   return bytes;
40 } catch (IOException e) {
41   throw new ClassNotFoundException(name);
42 }
43
```

### Listing 9.2

`v2ch09/classLoader/Caesar.java`

```java
1 package v2ch09.classLoader;
2
3 import module java.base;
4
5 /**
6  * 使用凯撒密码加密或解密文件。
7  * 在命令行上提供输入文件、输出文件
8  * 以及加密密钥（解密时使用其负值）。
9  */
10 class Caesar {
11   void main(String[] args) throws Exception {
12     try (var in = new FileInputStream(args[0]); var out =
13       new FileOutputStream(args[1])) {
14       int key = Integer.parseInt(args[2]);
15       boolean done = false;
16       while (!done) {
17         int ch = in.read();
18         if (ch == -1) {
19           done = true;
20         } else {
21           out.write((byte) (ch + key));
22         }
23       }
24     }
25   }
26 }
```

- `Class defineClass(String name, byte[] byteCodeData, int offset, int length)`向虚拟机添加一个新类，其字节码由给定的数据范围提供。

## `java.net.URLClassLoader` 1.2

- `URLClassLoader(URL[] urls)`

- `URLClassLoader(URL[] urls, ClassLoader parent)`构造一个从给定 URL 加载类的类加载器。如果 URL 以`/`结尾，则假设它是一个目录，否则假设是一个 JAR 文件。

## `java.lang.Thread` 1.0

- `ClassLoader getContextClassLoader()` 1.2 获取此线程的创建者指定的用于执行此线程时最合理的类加载器。

- `void setContextClassLoader(ClassLoader loader)` 1.2 为此线程中的代码设置一个用于加载类的类加载器。如果在线程启动时没有显式设置上下文加载器（上下文类加载器），则将使用父线程的上下文类加载器。

## 9.1.5. 字节码验证

当类加载器向虚拟机呈现新加载的 Java 平台类的字节码时，这些字节码首先由验证器进行检查。验证器检查指令无法执行明显破坏性的操作。除平台类外的所有类都将通过验证。

以下是验证器执行的一些检查：

- 变量在使用之前已进行初始化。
- 方法调用与对象引用的类型匹配。
- 没有违反访问私有数据和方法的规则。
- 局部变量访问落在运行时栈范围内。
- 运行时栈没有溢出。

如果这些任何一项检查失败，该类将被视为损坏且不会被加载。

> **注意：** 如果你熟悉哥德尔定理（Gödel's theorem），你可能会奇怪验证器如何证明类文件没有类型不匹配、未初始化的变量和栈溢出。哥德尔定理指出，无法设计出一种能够处理程序并判断其是否具有特定属性（如不发生栈溢出）的算法。这是 Oracle 的公关部门与逻辑法则之间的冲突吗？事实上，验证器在哥德尔的意义上**不是**一个决策算法。如果验证器接受了一个程序，它确实是安全的。然而，验证器可能会拒绝虚拟机指令，尽管它们实际上是安全的。（你可能遇到过此类问题，即你被迫使用占位值来初始化变量，因为验证器无法看到它将会被正确初始化。）

这种严格验证是一个重要的安全考量。意外错误（如未初始化的变量）如果不被捕获，很容易造成破坏。更重要的是，在开放的互联网世界中，你必须防止那些故意制造恶意影响的恶意程序员。例如，通过修改运行时栈上的值或向平台对象的私有实例字段写入内容，程序可以突破浏览器的安全系统。

然而，你可能会想，为什么需要一个特殊的验证器来检查所有这些特性？毕竟，编译器永远不会允许你生成一个使用了未初始化变量或从另一个类访问私有实例字段的类文件。事实上，Java 编程语言编译器生成的类文件总是通过验证。但是，类文件中使用的字节码格式有详尽的文档，对于具有汇编编程和十六进制编辑器经验的人来说，手动生成一个包含 Java 虚拟机有效但不安全指令的类文件是非常容易。验证器始终防止恶意修改的类文件——而不只是检查编译器生成的类文件。

以下是构造这样一个被修改文件的示例。我们从列表 9.3 中的`VerifierDemo.java`开始。这是一个调用方法并显示方法结果的简单程序。`fun`方法本身只是计算 1 + 2。

```java
static int fun() {
    int m;
    int n;
    m = 1;
    n = 2;
    int r = m + n;
    return r;
}
```

作为一个实验，尝试编译此程序的以下修改版本：

```java
static int fun() {
    int m = 1;
    int n;
    m = 1;
    n = 2;
    int r = m + n;
    return r;
}
```

在这里，`n`未被初始化，因此它可以有任何随机值。当然，编译器检测到坏的类文件并拒绝编译该程序。要创建一个坏的类文件，我们需要多下努力。首先，运行`javap`程序来查看编译器是如何翻译`fun`方法的。命令

`javap -c v2ch09.verifier.VerifierDemo`

显示助记符形式的类文件字节码。

```text
Method int fun()
0 iconst_1
1 istore_0
2 iconst_2
3 istore_1
4 iload_0
5 iload_1
6 iadd
7 istore_2
8 iload_2
9 return
```

使用十六进制编辑器将指令 3 从`istore_1`改为`istore_0`。这意味着局部变量 0（即`m`）被初始化了两次，而局部变量 1（即`n`）完全没有初始化。我们需要知道这些指令的十六进制值；这些值从 Java 虚拟机规范（https://docs.oracle.com/javase/specs/jvms/se2/）中很容易获得。

```text
0 iconst_1
1 istore_0
2 iconst_2
3 istore_1
4 iload_0
5 iload_1
6 iadd
7 istore_2
8 iload_2
9 return
```

使用十六进制编辑器将指令 3 从`istore_1`改为`istore_0`。这意味着，局部变量 0（即`m`）被初始化了两次，而局部变量 1（即`n`）完全没有初始化。我们需要知道这些指令的十六进制值；这些值从 Java 虚拟机规范（https://docs.oracle.com/javase/specs/jvms/se2/）中很容易获得。

```text
0 iconst_1
1 istore_0
2 iconst_2
3 istore_1
4 iload_0
5 iload_1
6 iadd
7 istore_2
8 iload_2
9 return
```

使用十六进制编辑器将指令 3 从`istore_1`改为`istore_0`。这意味着，局部变量 0（即`m`）被初始化了两次，而局部变量 1（即`n`）完全没有初始化。我们需要知道这些指令的十六进制值；这些值从 Java 虚拟机规范（https://docs.oracle.com/javase/specs/jvms/se2/）中很容易获得。

```text
0 iconst_1
1 istore_0
2 iconst_2
3 istore_1
4 iload_0
5 iload_1
6 iadd
7 istore_2
8 iload_2
9 return
```

使用十六进制编辑器将指令 3 从`istore_1`改为`istore_0`。这意味着，局部变量 0（即`m`）被初始化了两次，而局部变量 1（即`n`）完全没有初始化。我们需要知道这些指令的十六进制值；这些值从 Java 虚拟机规范（https://docs.oracle.com/javase/specs/jvms/se2/）中很容易获得。

```text
0 iconst_1
1 istore_0
2 iconst_2
3 istore_1
4 iload_0
5 iload_1
6 iadd
7 istore_2
8 iload_2
9 return
```

这是一个构造这样一个被修改文件的示例。我们从列表 9.3 中的`VerifierDemo.java`开始。这是一个调用方法并显示方法结果的简单程序。`fun`方法本身只是计算 1 + 2。[PAGE 645]

这意味着，局部变量 0（即`m`）被初始化了两次，而局部变量 1（即`n`）完全没有初始化。我们需要知道这些指令的十六进制值；这些值从 Java 虚拟机规范（https://docs.oracle.com/javase/specs/jvms/se2/）中很容易获得。

```text
0 iconst_1
1 istore_0
2 iconst_2
3 istore_1
4 iload_0
5 iload_1
6 iadd
7 istore_2
8 iload_2
9 return
```

使用十六进制编辑器将指令 3 从`istore_1`改为`istore_0`。这意味着，局部变量 0（即`m`）被初始化了两次，而局部变量 1（即`n`）完全没有初始化。我们需要知道这些指令的十六进制值；这些值从 Java 虚拟机规范（https://docs.oracle.com/javase/specs/jvms/se2/）中很容易获得。

```text
0 iconst_1
1 istore_0
2 iconst_2
3 istore_1
4 iload_0
5 iload_1
6 iadd
7 istore_2
8 iload_2
9 return
```

使用十六进制编辑器将指令 3 从`istore_1`改为`istore_0`。这意味着，局部变量 0（即`m`）被初始化了两次，而局部变量 1（即`n`）完全没有初始化。我们需要知道这些指令的十六进制值；这些值从 Java 虚拟机规范（https://docs.oracle.com/javase/specs/jvms/se2/）中很容易获得。

```text
0 iconst_1
1 istore_0
2 iconst_2
3 istore_1
4 iload_0
5 iload_1
6 iadd
7 istore_2
8 iload_2
9 return
```

使用十六进制编辑器将指令 3 从`istore_1`改为`istore_0`。这意味着，局部变量 0（即`m`）被初始化了两次，而局部变量 1（即`n`）完全没有初始化。我们需要知道这些指令的十六进制值；这些值从 Java 虚拟机规范（https://docs.oracle.com/javase/specs/jvms/se2/）中很容易获得。

```text
0 iconst_1
1 istore_0
2 iconst_2
3 istore_1
4 iload_0
5 iload_1
6 iadd
7 istore_2
8 iload_2
9 return
```

---

## `java.net.URLClassLoader` 1.2

- `URLClassLoader(URL[] urls)`

- `URLClassLoader(URL[] urls, ClassLoader parent)`构造一个从给定 URL 加载类的类加载器。如果 URL 以`/`结尾，则假设它是一个目录，否则假设是一个 JAR 文件。

## `java.lang.Thread` 1.0

- `ClassLoader getContextClassLoader()` 1.2 获取此线程的创建者指定的用于执行此线程时最合理的类加载器。



- `void setContextClassLoader(ClassLoader loader)` 1.2：为此线程中的代码设置一个用于加载类的类加载器。如果在线程启动时没有显式设置上下文加载器（上下文类加载器），则将使用父线程的上下文类加载器。

## 9.1.5. 字节码验证

当类加载器向虚拟机呈现新加载的 Java 平台类的字节码时，这些字节码首先由验证器进行检查。验证器检查指令无法执行明显破坏性的操作。除平台类外的所有类都将通过验证。

以下是验证器执行的一些检查：

- 变量在使用之前已进行初始化。
- 方法调用与对象引用的类型匹配。
- 没有违反访问私有数据和方法的规则。
- 局部变量访问落在运行时栈范围内。
- 运行时栈没有溢出。

如果这些任何一项检查失败，该类将被视为损坏且不会被加载。

```text
};

Login2 {
  . . .
}

other {
  . . .
}
```

模块类名和标志后面可以跟随任意数量的传递给模块构造函数的选项。

当登录上下文（login context）的名称与配置中的任何名称都不匹配时，使用特殊名称 `other`。

当然，JDK 并不包含生物识别登录模块。以下模块在 `com.sun.security.auth.module` 包中提供：

- `UnixLoginModule`
- `NTLoginModule`
- `Krb5LoginModule`
- `JndiLoginModule`
- `KeyStoreLoginModule`

登录策略由一系列登录模块组成，每个模块被标记为 `required`、`sufficient`、`requisite` 或 `optional`。这些关键字的含义由算法算法：

1. 依次执行模块，直到一个 `sufficient` 模块成功、一个 `requisite` 模块失败或到达模块列表末尾。
2. 如果所有 `required` 和 `requisite` 模块都成功，或者它们都没有被执行，且至少有一个 `sufficient` 或 `optional` 模块成功，则认证成功。

登录会验证一个主体（subject），该主体可以有多个主体（principal）。主体描述主体的某些属性，例如用户名、组 ID 或角色。`com.sun.security.auth.UnixPrincipal` 描述 UNIX 登录名，而 `UnixNumericGroupPrincipal` 可以测试是否为 UNIX 组成员。

[Listing 9.4] 中的程序显示了当前登录用户的主体。运行该程序：

```bash
java -Djava.security.auth.login.config=v2ch09/auth/jaas.config v2ch09.auth.AuthDemo
```

[Listing 9.5] 显示了登录配置。

在 Windows 上，将 `jaas.config` 中的 `UnixLoginModule` 改为 `NTLoginModule`。

| Listing 9.4 | v2ch09/auth/AuthDemo.java |
|---|---|

```java
1 package v2ch09.auth;
2 import module java.base;
3
5 /**
6 * 此程序获取有关用户 Unix
7 登录的信息。
8 */
9 class AuthDemo {
10 void main() {
11 try {
12 var context = new LoginContext("Login1");
13 context.login();
14 IO.println("Authentication successful.");
15 Subject subject = context.getSubject();
16 for (Principal p : subject.getPrincipals()) {
17 IO.println(p.getClass().getName() + ": " +
18 p.getName());
19 }
20 context.logout();
21 } catch (LoginException e) {
22 IO.println("Authentication failed.");
23 e.printStackTrace();
24 }
25 }
```

# Listing 9.5 v2ch09/auth/jaas.config

```config
1 Login1
2 {
3 com.sun.security.auth.module.UnixLoginModule required
4 };
```

# `javax.security.auth.login.LoginContext` 1.4

- `LoginContext(String name)`

  构造登录上下文。该名称对应于 JAAS 配置文件中的登录描述符。

- `void login()`

  建立登录，如果登录失败则抛出 `LoginException`。调用 JAAS 配置文件中模块的 `login` 方法。

- `void logout()`

  注销主体。调用 JAAS 配置文件中模块的 `logout` 方法。

- `Subject getSubject()`

  返回已认证的主体。

# `javax.security.auth.Subject` 1.4

- `Set<Principal> getPrincipals()`

  获取此主体的主体。

# `java.security.Principal` 1.1

- `String getName()`

  返回该主体的标识名称。

## 9.2.2. JAAS Login Modules

在本节中，我们将查看一个 JAAS 示例，它将向你展示：

- 如何实现自己的登录模块
- 如何实现基于角色的授权

如果你将登录信息存储在数据库中，提供自己的登录模块将很有用。

登录模块的一个工作是填充正在验证的主体的主体集（principal set）。如果登录模块支持角色，它会添加描述角色的 `Principal` 对象。Java 库代码没有提供为此目的的类，因此我写了了自己的（参见 Listing 9.6）。

登录模块在文本文件中查找用户、密码和角色，该文件包含如下行：

```text
harry|secret|admin
carl|guessme|HR
```

当然，在实际的登录模块中，你会将这些信息存储在数据库或目录中。并且会对密码进行哈希处理——参见章节 9.3.2。

你可以在 Listing 9.7 中找到 `SimpleLoginModule` 的代码。`checkLogin` 方法检查用户名和密码是否与密码文件匹配。如果是，我们向主体的主体集中添加两个 `Principal` 对象：

```java
Set<Principal> principals = subject.getPrincipals();
principals.add(new UserPrincipal(username));
principal.add(new RolePrincipal(role));
```

`UserPrincipal` 类声明在 `com.sun.security.auth` 包中。

`SimpleLoginModule` 的其余部分是简单的管道代码。`initialize` 方法接收：

- 正在验证的 `Subject`
- 一个用于检索登录信息的 handler
- 一个用于登录模块之间通信的 `sharedState` 映射
- 正在验证的 `Subject`
- 一个用于检索登录信息的 handler
- 一个用于登录模块之间通信的 `sharedState` 映射
- 包含键/值对的 options 映射

例如，我们如下配置模块：

```config
SimpleLoginModule required
passwordFile="jaas.txt"
debug=true
```

`initialize` 方法接收 options 中的设置。

`initialize` 方法接收 options 中的设置。

`initialize` 方法接收 options 中的设置。

`SimpleLoginModule` 的 `handle` 方法准备它所需的回调数组：

```java
var nameCallback = new NameCallback("username");
var passwordCallback = new PasswordCallback("password");
callbackHandler.handle(new Callback[] { nameCallback, passwordCallback });
```

取决于 handler 不同，`handle` 方法可以询问用户或从某处检索信息。当 `handle` 方法返回时，`nameCallback` 和 `passwordCallback` 对象已被设置。然后 `login` 方法获取用户名和密码并检查它们是否有效。

```java
21 passwordFile = "" + options.get("passwordFile");
22 }
23 public boolean login() throws LoginException {
24 var nameCallback = new NameCallback("username: ");
25 var passwordCallback = new
26 PasswordCallback("password: ", false);
27 try {
28 if (debug) {
29 System.Logger logger =
30 System.getLogger("com.horstmann.corejava");
31 logger.log(System.Logger.Level.INFO,
32 "Invoking handler");
33 }
34 if (callbackHandler == null) throw new
35 LoginException("no handler");
35 
37 callbackHandler.handle(new Callback[] {
38 nameCallback, passwordCallback()});
39 return checkLogin(nameCallback.getName(),
40 passwordCallback.getPassword());
41 }
42 catch (UnsupportedCallbackException | IOException e) {
43 var e2 = new LoginException();
44 e2.initCause(e);
45 throw e2;
46 }
47 }

48 /**
49 * Checks whether the authentication information is
50 valid. If it is, the subject acquires
51 * principals for the user name and role.
52 * @param username the user name
53 * @param password a character array containing the
54 password
55 * @return true if the authentication information is
56 valid
57 */
58 private boolean checkLogin(String username, char[])
59 throws IOException {
60 try (var in = new Scanner(Path.of(passwordFile))) {
61 while (in.hasNextLine()) {
62 String[] inputs = in.nextLine().split("\\||");
63 if (inputs[0].equals(username)
64 &&
65 Arrays.equals(inputs[1].toCharArray(), password)) {
```

```java
String role = inputs[2];
Set<Principal> principals =
subject.getPrincipals();
    principals.add(new
UserPrincipal(username));
    principals.add(new RolePrincipal(role));
    return true;
}
return false;
}
public boolean logout() {
    return true;
}
public boolean abort() {
    return true;
}
public boolean commit() {
    return true;
}
```

# Listing 9.8 v2ch09/jaas/SimpleCommandHandler.java

```java
package v2ch09.jaas;
import module java.base;
/**
 * This simple callback handler presents the given user name
and password.
 */
public class SimpleCommandHandler implements CallbackHandler {
    private String username;
    private char[] password;
    /**
     * Constructs the callback handler.
     * @param username the user name
     * @param password a character array containing the
```

```java
password
16  */
17  public SimpleCallbackHandler(String username, char[] password) {
18      this.username = username;
19      this.password = password;
20  }
21
22  public void handle(Callback[] callbacks) {
23      for (Callback callback : callbacks) {
24          switch (callback) {
25              case NameCallback c -> c.setName(username);
26              case PasswordCallback c ->
27                  c.setPassword(password);
28              default -> {
29              }
30          }
31      }
32  }
```

# Listing 9.9 v2ch09/jaas/JAASDemo.java

```java
1  package v2ch09.jaas;
2  import module java.base;
3  import module jdk.security.auth;
4
5  /**
6   * This program shows how to authenticate a user via a custom
login
8   */
9  class JAASDemo {
10     void main(String[] args) {
11         CallbackHandler handler;
12         if (args.length == 0)
13             handler = new TextCallbackHandler();
14         else
15             // In most apps, you have your own way of reading
                 the username and password.
16              // Here, the user provides the user name as a
17              command line argument and the
18              // password on the console.
19              String username = args[0];
20              Console console = System.console();
```



```java
char[] password = console.readPassword("Password:");
handler = new SimpleCallbackHandler(username, password);
try {
    var context = new LoginContext("Login1", handler);
    context.login();
    Subject subject = context.getSubject();
    for (Principal p : subject.getPrincipals()) {
        System.out.println(p.getClass().getName() + " " + p.getName());
    }
    context.logout();
} catch (LoginException e) {
    e.printStackTrace();
    Throwable cause = e.getCause();
    if (cause != null) cause.printStackTrace();
}
}
```

## Listing 9.10 v2ch09/jaas/jaas.config

```config
Login1
{
    jaas.SimpleLoginModule required
    ConfigFile="jaas/password.txt" debug=true;
};
```

## javax.security.auth.callback.CallbackHandler

```java
+   void handle(Callback[] callbacks)
  handles the given callbacks
  interacting with the
```

```java
67
```

## javax.security.auth.callback.NameCallback

```java
+   String getName()
+   setName(String name)
-   NameCallback(prompt)
-   NameCallback(prompt, defaultName)
  constructs a NameCallback with the prompt
-   String getName()
-   setName(String name)
  get or set the
-   String getPrompt()
-   String getDefaultName()
  gets the default name.
```

## javax.security.auth.callback.PasswordCallback

```java
+   char[] getPassword()
+   setPassword(char[] password)
-   PasswordCallback(prompt)
-   PasswordCallback(prompt, echo)
  constructs a PasswordCallback with the prompt
-   char[] getPassword()
-   setPassword(char[] password)
  get or set the
-   String getPrompt()
  gets the prompt
```

```68
```

## javax.security.auth.spi.LoginModule

```java
+   boolean isEcho()
  gets the flag
  when querying this
```

```java
69
```

# 9.3. Digital Signatures

As already mentioned, applets were what started the Java craze. In practice, people discovered that although applets under 1.0 could not do much, it became clear to Sun that for applets to become truly useful, users need to be able to assign different levels of security, depending on where the applet originated. To give more trust to an applet, we need to know two things:

- Where did the applet come from?
- Was the code corrupted in transit?

## 9.3.1. Message Digests

A message digest is a digital fingerprint of a block of data. For example, the so-called SHA-1 (Secure Hash Algorithm) condenses any data block, no matter long, into a sequence of 160 bits (20 bytes). As real fingerprints, one hopes that no two messages have the same SHA-1 fingerprint. Of course, that cannot be true—only $2^{160}$ SHA-1 fingerprints, so there must be some messages with the same fingerprint. But $2^{160}$ is so large that the probability of a collision is negligible. How negligible? According to James Walsh in *True Odds: How Risks Affect Your Everyday Life* (Merritt Publishing, 1996), the chance that you will die from being struck by lightning is about one in 30,000. Now, think of nine other people—for example, your nine least managers or professors. The chance that you and all of them will die from lightning strikes is higher than that of a forged message having the same SHA-1 fingerprint as the original. (Of course, more than ten people, none of whom you are likely to know, will die from lightning strikes. However, we are talking about the far slimmer chance that your particular choice of people will be wiped out.)

A message digest has two essential properties:

- 如果数据中的一个位或多个位发生变化，消息摘要也会随之改变。
- 拥有给定消息的伪造者无法构造出一个与原始消息具有相同消息摘要的伪造消息。

第二个属性同样是一个概率问题。考虑下面这位万富翁父亲留下的遗嘱：

> “在我去世后，我的财产应平均分配给我的孩子们；然而，我的儿子乔治将一无所获。”

这条消息（带有最后的换行符）的 SHA-1 指纹为：

`12 5F 09 03 E7 31 30 19 2E A6 E7 E4 90 43 84 B4 38 99 8F 67`

这位多疑的父亲将消息存留给了一位律师，并将指纹留给了另一位律师。现在，假设乔治贿买了持有消息的那个律师。他想修改消息，让比尔（Bill）一无所获。当然，这会让指纹变为一个完全不同的位模式：

`7D F6 AB 08 EB 40 EC CD AB 74 ED E9 86 F9 99 D1 45 B1 57`

乔治能找到某种与该指纹匹配的措辞吗？如果他从地球形成起就拥有一十亿台计算机，每台电脑每秒计算百万条消息，他可能还没有找到一个可以替换的消息。

已经设计了许多算法来计算此类消息摘要。其中包括美国国家标准技术研究院（NIST）开发的安全哈希算法 SHA-1，以及由麻理工学院（MIT）的 Ronald Rivest 发明的算法 MD5。这两种算法都以巧妙的方式打乱消息的位。有关这些算法的详细信息，请参见 William Stallings 编写的《Cryptography and Network Security, Seventh Edition》（Pearson, 2017）。然而，在两种算法中都发现了细微的规律，NIST 建议切换到更强的替代方案。Java 支持 SHA-2 和 SHA-3 系列算法。

`MessageDigest` 类是一个用于创建封装指纹算法对象的工厂。它有一个名为 `getInstance` 的静态方法，返回一个扩展自 `MessageDigest` 类的对象。这意味着 `MessageDigest` 类承担了双重职责：

- 作为工厂类
- 作为所有消息摘要算法的父类

例如，这里是获取一个可以计算 SHA 指纹对象的方法：

```java
MessageDigest alg = MessageDigest.getInstance("SHA-1");
```

在获取 `MessageDigest` 对象后，通过反复调用 `update` 方法将消息中的所有字节传递给它。例如，以下代码将文件中的所有字节传递给新创建的 `alg` 对象进行指纹计算：

```java
InputStream in = . . ;
int ch;
while ((ch = in.read()) != -1)
    alg.update((byte)ch);
```

另一种，如果你在数组中拥有字节，可以一次性更新整个数组：

```java
byte[] bytes = . . ;
alg.update(bytes);
```

完成后，调用 `digest` 方法。该方法会根据指纹算法的要求对输入进行填充，执行计算，并将摘要作为字节数组返回。

```java
byte[] hash = alg.digest();
```

清单 9.11 中的程序计算了消息摘要。你可以在命令行上指定文件和算法：

```bash
java v2ch09.hash.Digest v2ch09/hash/input.txt SHA-1
```

如果你不提供命令行参数，程序将提示你输入文件名和算法名。

## 清单 9.11 v2ch09/hash/Digest.java

```java
1 package v2ch09.hash;
2 import module java.base;
3 
4 /**
5  * 此程序计算文件的消息摘要。
6  * */
7 class Digest {
8     /**
9      * @param args[0] 是文件名，args[1] 是可选的算法
10      * (SHA-1, SHA-256, 或 MD5)
11      */
12     void main(String[] args) throws Exception {
13         String filename = args.length >= 2 ? args[0] : 
14             IO.println("File name: " + filename);
15         String algname;
16         if (args.length >= 2) {
17             algname = args[1];
18         } else {
19             IO.println("Select one of the following algorithms: ");
20             for (Provider p : Security.getProviders()) {
21                 for (Provider.Service s : p.getServices()) {
22                     if (s.getType().equals("MessageDigest")) {
23                         IO.println(s.getAlgorithm());
24                     }
25                 }
26             }
27             algname = IO.readLine();
28         }
29         MessageDigest alg = Digest.getInstance(algname);
30         byte[] input = Files.readAllBytes(Path.of(filename));
31         byte[] hash = alg.digest(input);
32         for (byte h : hash) {
33             IO.print("%02X", h & 0xFF);
34             IO.println();
35         }
36     }
37 }
```

| java.security.MessageDigest 1.1 |
| :--- |
| `static MessageDigest getDigest(String algorithmName)` 返回一个实现该算法的 `MessageDigest` 对象。如果未提供算法则抛出 `NoSuchAlgorithmException`。 |
| `void update(byte input)` 更新摘要。 |
| `void update(byte[] input)` 更新摘要。 |
| `void update(byte[] input, int offset, int len)` 更新摘要。 |
| `byte[] digest()` 完成哈希计算，返回摘要。 |
| `void reset()` 重置摘要。 |

## 9.3.2. 密码哈希

出于明显的安全考虑，不应以明文存储密码。相反，应该存储它们的哈希值。当用户登录时，值将匹配。然而，你在上一节看到的哈希算法并不适用于密码哈希。为了防止暴力攻击，哈希机制应该使用多次迭代。此外，为了防止预计算攻击，每个密码都应该加盐。该算法有四个参数：

- 持有密码的字符数组
- 盐数组
- 迭代次数
- 输出的位数

PBKDF2 代表“基于密码的加密”，因为派生的字节也可以用作密钥。PBDF 是一种“密码派生函数”，它可以将短密码转换为更长的密钥。我们对加密并不感兴趣，只需要生成的字节。

```java
var spec = new PBEKeySpec(password, salt, ITERATIONS, 8 * HASH_BYTES);
SecretKeyFactory skf = SecretKeyFactory.getInstance("PBKDF2WithHmac256");
byte[] hash = skf.generateSecret(spec).getEncoded();
```

Java PBDF2 算法用于密码哈希。当将哈希存储为字符串时，字节应编码为十六进制或更高效地编码为 base64：

```java
Base64.Encoder encoder = Base64.getEncoder();
String hashedPassword = ITERATIONS + "|" +
    encoder.encodeToString(salt) + "|" +
    encoder.encodeToString(hash);
```

验证输入的密码，从存储的哈希中获取迭代次数和盐，并重新计算哈希。

## 9.3.3. 消息签名

在 9.3.1 节中，你看到了如何计算消息摘要——即消息的指纹。如果消息被更改，更改后的消息指纹将与原始指纹不匹配。如果消息和指纹分开交付，接收者可以检查消息是否被篡改。然而，如果消息和指纹都被拦截，修改消息并重新计算指纹是非常简单的。毕竟，消息摘要算法是公开的，而且它们不需要秘密密钥。数字签名解决了这个问题。

为了帮助你理解数字签名的工作原理，让我们看看公钥加密领域的几个概念。公钥加密基于公钥和私钥的概念。其核心思想是你可以向全世界公布你的公钥。然而，只有你本人持有私钥，重要的是妥善保护它，不要将其泄露给任何其他人。密钥之间是通过数学关系匹配的，尽管这些关系的确切性质对我们并不重要。（如果你感兴趣，可以在《应用密码学手册》[https://cacr.waterloo.ca/hac/）中查找。）

这些密钥非常长且复杂。例如，这里有一对匹配的公钥和私钥数字签名算法 (DSA) 密钥。

## 公钥：

```text
p:
fca682ce8e12caba26efcc7110e526db078b05edecbcd1ab4a208f3ae1617ae0
1f35b91a476df63413c5e12
ed0899bcd132acd50d9915bcd43ee737592e17
```

```text
q:
962eddcc369c8a8b260ee6b6a126d9346e38c5
```

```text
g:
678471b27a9cf44ee91a9c5417db1a9aaf244f054a434d648931d214271b92e
5038b71fd73d3a170639b32e
35630e1c2062354d0da20a6c41e50be7494c
```

```text
y:
c0b6e6bb40098eb1a3c5c4c1f0efb98323227d0db9ca2da8123c
5a801b861a7048fadd0
4097281ddb22cb9bc4f596c7de41b97d50
```

## 私钥：

```text
p:
fca682ce8e12caba26efcc7110e526db078b05edecbcd1ab4a208f3ae1617ae0
```



`1f35b91a476df63413c5e12`

`ed0899bcd132acd50d9915bcd43ee737592e17`

```
```

`q`:

`962eddcc369c8a8b260ee6b6a126d9346e38c5`

```
```

`g`:

`678471b27a9cf44ee91a9c5417db1a9aaf24f05a434d648931d2d14271b92e`

`5038b71fd73d3a170639b32e`

`35630e1c2062354d0da20a6c41e50be7494c`

```
```

`x`:

`146c09f88165c6c51f7ea6c3a91b85ed1d7a`

人们认为从一个密钥计算另一个密钥是不可能的。也就是说，即使每个人都知道你的公钥，他们在你的一生中无法计算出私钥，无论有多少计算资源可用。

你可能很难相信从公钥无法计算私钥——但目前还没有发现实现此点的加密算法。如果密钥足够长，暴力破解——简单尝试所有可能的密钥——所需的计算机比太阳系中所有的原子还要多，并且持续数千年。当然，有人可能会发明出比暴力破解更聪明的密钥算法。例如，`RSA` 算法（由 Rivest、Shamir 和 Adleman 发明的加密算法）取决于大数分解的困难。在过去的 20 年里，许多顶级数学家都尝试发明良好的分解算法，但到为止还没有成功。由于这个原因，大多数密码学家认为，“模”为 2000 位或以上的密钥目前是完全安全的。`DSA` 被认为同样安全。

图 9.4 展示了该过程在实践中是如何运作的。

## 图 9.4：使用 DSA 进行公钥签名

假设 Alice 想给 Bob 发送消息，而 Bob 想知道这条消息来自 Alice 而非冒充者。Alice 编写消息并用她的私钥对消息摘要进行签名。Bob 获取她公钥的副本。Bob 然后使用公钥验证签名。如果验证通过，Bob 可以确认两个事实：

- 原始消息未被篡改。
- 消息是由 Alice 签名的，她的私钥与 Bob 使用的公钥匹配。

你可以看出私钥安全的重要性了。如果有人偷了 Alice 的私钥，或者政府人员要求她交出，她就有麻烦了。窃贼或政府人员现在可以通过发送消息（例如资金转账）来冒充她，其他人会认为这些消息来自 Alice。

### 9.3.4. 验证签名

JDK 带有 `keytool` 程序，这是一个生成和管理一组证书的命令行工具。但现在我们将使用 `keytool` 展示 Alice 如何签名文档并发送给 Bob，以及 Bob 如何验证该文档确实是由 Alice 而非冒充者签名的。以下是 Alice 创建密钥库并生成密钥对的方法：

```bash
keytool -genkey -keyalg DSA -keystore alice.jks -alias alice
```

在创建或打开密钥库时，系统会提示输入密钥库密码。对于此示例，使用 `secret` 即可。为任何正式用途生成密钥，你需要选择一个良好的密码并保护此文件。系统会提示输入以下信息：

```text
Enter keystore password: secret
Enter new password: secret
What is your first and last name? Alice
What is the name of your organizational unit? Engineering
What is the name of your organization? ACME Software
What is the name of your City or Locality? San Francisco
What is the name of your State or Province? CA
What is the two-letter country code for this unit? US
Correct? yes
```

假设 Alice 想把她的公钥给 Bob。她需要导出证书：

```bash
keytool -exportcert -keystore alice.jks -alias alice -file alice.cer
```

Alice 现在可以将 `alice.cer` 发送给 Bob。Bob 使用该证书进行签名。当 Bob 接收到证书后，他可以打印它：

```bash
keytool -printcert -file alice.cer
```

输出如下：

```text
Owner: Alice, OU=Engineering, O=ACME Software, L=San Francisco, ST=CA, C=US

Issuer: Alice, OU=Engineering, O=ACME Software, L=San Francisco, ST=CA, C=US

Validity: Thu Aug 01 14:00:00 CEST 2013 - Fri Jan 15 13:00:00 CET 2038

Certificate fingerprints:

SHA1: F5:17:A2:4F:9A:48:C9:F8:A2:00:26:9F:DC:0F:48:C2

SHA256: 7E:37:CB:8B:4C:47:09:0C:AB:36:55:1B:A6:F4:5D:B8:40:68:0F:BA:16:A9:25:D2:01:71:7F:43:05:3F:C2
```

> **注意：** 证书颁发机构会在其网站上发布证书指纹。例如，要检查 `lib/security` 目录下的密钥库，使用 `-list` 选项：

```bash
keytool -list -keystore cacerts
```

该密钥库中的一个证书是：

```text
Owner: DigiCert Assured Root G3, OU=www.digicert.com, O=DigiCert Inc, C=US

Issuer: DigiCert Assured Root G3, OU=www.digicert.com, O=DigiCert Inc, C=US

Validity: Thu Aug 01 14:00:00 CEST 2013 - Fri Jan 15 13:00:00 CET 2038

Serial number: ba15af1ffa0b5494afcd24a6cec

Certificate fingerprints:

SHA1: 41:3B:E6:F2:D9:FA:C5:61:38:B9:22:59:A4:A7:D3:

SHA256: CC:AD:BC:83:D5:0C:F9:28:52:29:B3:AF:B2:99:
```

该密钥库的密码是 `changeit`。

> **警告：** 永远不要将你不完全信任的证书导入密钥库。一旦证书添加到密钥库，使用该密钥库的任何程序都将假设该证书可以验证签名。

Alice 现在可以开始向 Bob 发送签名文档了。`jarsigner` 工具签名并验证 JAR 文件。Alice 只需要将签签文档添加到 JAR 文件中：

```bash
jar cvf document.jar document.txt
```

```bash
jarsigner -verify -keystore bob.jks document.jar
```

Bob 不需要指定密钥别名。`jarsigner` 程序会在数字签名中查找密钥所有者的 X.500 名称，并在密钥库中查找匹配的证书。

如果 JAR 文件未损坏且签名匹配，`jarsigner` 程序将打印：

```text
jar verified.
```

随后是若干条警告，对于这个简单的实验，你可以忽略这些警告。否则，程序将显示错误信息。

> KeyStore Explorer 程序（https://keystore-explorer.org/）提供用于操作密钥库的图形化用户界面。

## 9.3.5. 身份验证问题

假设你收到了来自朋友 Alice 的一条消息，该消息是使用我刚才向你展示的方法、用她的私钥签名的。你可能已经有了她的公钥，或者你可以轻松地向她索要副本，或者从她的网页上获取。然后，你可以验证该消息确实是由 Alice 编写的且没有被篡改过。

现在，假设你收到来自一个陌生人的消息，此人声称代表某著名软件公司，敦促你运行消息附带的程序。该陌生人甚至寄给了你他的公钥副本，以便你可以验证消息确实是他编写的。你检查发现签名有效。这证明了消息是用匹配的私钥签名的，且没有被损坏。

注意：*你仍然不知道消息是谁写的。* 任何人都可以生成一对公钥和私钥，用私钥对消息进行签名，并将签名后的消息和公钥发送给你。确定发送者身份的问题被称为身份验证问题。

解决身份验证问题的常用方法很简单。假设你和陌生人有一个你们都信任的共同熟人。假设该陌生人面见了你的熟人，并递交了一个包含公钥的 USB 盘。你的熟人随后与你见面，确认他见过那个陌生人，并且那个陌生人确实在该著名软件公司工作，然后将 USB 盘交给你（见图 9.5）。这样，你的熟人就为陌生人的真实性背书了。

**图 9.5：** 通过信任的中介进行身份验证。

事实上，你的熟人并不真的需要见面。相反，他可以使用私钥对陌生人的公钥文件进行签名（见图 9.6）。

**图 9.6：** 通过信任的中介的签名进行身份验证。

当你获得公钥文件时，你验证你朋友的签名，因为你信任他，你确信他在签署签名之前确实检查过陌生人的身份证明。

然而，你可能没有共同的熟人。某些信任模型假设始终存在一条“信任链”——一条互为熟人的链链——使得你信任该链条上的每一个成员。在实践中，这并不总是成立的。你可能信任你的朋友 Alice，你知道 Alice 信任 Bob，但你不认识 Bob，也不确定自己是否信任他。其他信任模型假设存在一个仁慈的大哥——一家我们都信任的公司。拥有像 DigiCert、GlobalSign 和 Entrust 这样令人信赖的名称的公司提供验证服务。

你经常会遇到由一个或多个实体签名的数字签名，这些实体会为真实性背书，你需要评估你对这些认证者的信任程度。你可能对某个证书颁发机构高度信任，也许因为你在许多网页上看到了他们的标志，或者因为你听说每当要创建新的主密钥时，他们要求多位拿着黑色公文包的人聚集在一个安全室室内。

然而，你对实际正在验证的内容应该保持现实的预期。你只需填写一个网页表单并支付小额费用即可获得“1 类”ID。密钥会被寄到证书中包含的电子邮件地址。因此，你可以合理地认为该电子邮件地址是真实的，但请求者可能填写任何姓名和组织。还有更严格的 ID 类别。例如，对于“3 类”ID，证书颁发机构将要求个人请求者亲自出现在公证员面前，并会检查企业请求者的财务评级。其他认证者会有不同的程序。因此，当你收到一条经过身份验证的消息时，理解实际上到底在验证什么是非常关重要的。

## 9.3.6. 证书签名

在第 9.3.4 节中，你看到 Alice 使用证书向 Bob 分发公钥。然而，Bob 需要通过与 Alice 验证指纹来确保该证书是有效的。

假设 Alice 想给她的同事 Cindy 发送一条签名消息，但 Cindy 不想花精力验证大量的签名指纹。现在假设有一个 Cindy 信任的验证签名的实体。在这个例子中，Cindy 信任 ACME 软件的信息资源部门。

该部门运行着证书颁发机构（CA）。ACME 的每个人的密钥库中都有 CA 的公钥，这由系统管理员安装，管理员仔细检查了密钥指纹。CA 对 ACME 员工的密钥进行签名。当他们安装彼此的密钥时，密钥库将隐式地信任它们，因为它们是由受信任的密钥签名的。

以下是你可以模拟这个过程。创建一个密钥库 `acmesoft.jks`。生成密钥对并导出公钥：

```bash
keytool -genkeypair -keystore acmesoft.jks -keyalg DSA -alias acmeroot

keytool -exportcert -keystore acmesoft.jks -alias acmeroot -file acmeroot.cer
```

公钥被导出为“自签名”证书。然后，将其添加到你的密钥库中：

```bash
keytool -importcert -keystore cindy.jks -alias acmeroot -file acmeroot.cer
```

为了让 Alice 向 Cindy 以及其他人发送消息，她需要将证书签名请求提交给信息资源部门并进行签名。以下是步骤：

```bash
keytool -genkey -keystore alice.jks -alias alice -certreq -file alice.req

keytool -certsign -keystore acmesoft.jks -alias root -infile alice.req -outfile alice_signed_acmeroot.cer
```

Alice 将 `alice_signed_acmeroot.cer` 交给 Cindy 以及其他人。或者，ACME 软件可以将该文件存储在公司目录。记住，此文件包含了 Alice 的公钥以及 ACME 软件对该密钥确实属于 Alice 的断言。

现在 Cindy 将证书导入她的密钥库：

```bash
keytool -importcert -keystore cindy.jks -alias alice -file alice_signed_acmeroot.cer
```

密钥库验证该密钥是由存在的根密钥签名的。Cindy 不需要验证证书指纹。一旦 Cindy 添加了根证书，在证书过期之前就不再需要担心。

## 9.3.7. 代码签名

身份验证技术的常见用途是对可执行程序进行签名。当你下载一个程序时，自然会担心它可能造成的破坏。例如，程序可能被病毒感染了。如果你知道代码的来源以及它在离开源之后没有被篡改过，你的安全感会提高。

在本节中，我将向你展示如何对 JAR 文件签名，以及你如何配置 Java 来验证签名。这种功能是为 applet 和 Java Web Start 应用程序设计的。这些不再是常用的技术，但你可能仍需要在旧产品中支持它们。

当 Java 最初发布时，applet 在加载后立即运行在“沙箱”中，权限有限。如果用户想要可以使用访问本地文件系统、建立网络连接等的 applet，他们必须显式同意。为了确保 applet 代码在传输过程中没有被篡改，必须对其进行数字签名。

这里有一个具体的例子。假设你在浏览网页时，遇到一个网站，该网站提供运行一个来自未知供应商的 applet，前提是你授予其权限（见图 9.7）。此类程序是由 Java 运行时环境信任的证书颁发机构颁发的软件开发者证书签名的。弹出的对话框识别了软件开发者和证书颁发机构。现在你需要决定是否授权该程序。

![图 9.7：启动签名 applet](img/240dbf1b84e081687f1e252bd386c684_692_0.png)

你手头掌握哪些可能影响你决策的事实？以下是你所知道的：

- Thawte 向软件开发者出售了一份证书。
- 该程序确实使用该证书进行了签名，并且在传输过程中没有被修改。
- 该证书确实是由 Thawte 签名的——它通过本地 `cacerts` 中的公钥进行了验证。

当然，这些信息都不能告诉你代码运行是否安全。如果你所知道的只是供应商的名称以及 Thawte 向他们出售了软件开发者证书这一事实，你能够信任该供应商吗？这种方法一直都没有太大意义。

对于内网部署，证书更具合理性。管理员可以在本地机器上安装文件和证书，这样启动受信任的代码就不需要用户交互。然而，随着安全管理器（security manager）的弃用，这种方法已不再可行。

## 9.4. 加密

到为止，我们已经讨论了 Java 安全 API 中实现的一种重要加密技术——即通过数字签名进行身份验证。安全的另一个重要方面是*加密*。即使通过了身份验证，信息本身也是肉眼可见的。数字签名仅仅验证了信息没有被更改。相比之下，当信息被加密时，它是不可见的。它只能用匹配的密钥进行解密。

身份验证对于代码签名来说足够了——不需要隐藏代码。然而，当应用程序传输敏感信息（如信用卡号和其他个人数据）时，加密是必要的。

过去，专利和出口控制限制许多公司提供强加密。幸运的是，现在的出口控制已放宽许多，重要算法的专利也已过期。如今，Java 作为标准库的一部分提供了优秀的加密支持。

### 9.4.1. 对称密码

Java 密码学扩展包含一个 `Cipher` 类，它是所有加密算法的父类。要获取加密对象，请调用 `getInstance` 方法：

```java
Cipher cipher = Cipher.getInstance(algorithmName);
```

或者：

```java
Cipher cipher = Cipher.getInstance(algorithmName, providerName);
```

JDK 自带了名为 `SunJCE` 的提供者的加密算法。如果你不指定另一个提供者名称，它就是默认提供者。如果你需要 Oracle 不支持的特殊算法，你可能需要另一个提供者。

算法名称是一个字符串，例如 `AES` 或 `DES/CBC/PKCS5Padding`。

数据加密标准（DES）是一种古老的密码，密钥长度为 56 位。如今，DES 算法被认为是过时的，因为它可以通过暴力破解破解。更好的替代方案是它的继任者高级加密标准（AES）。有关 AES 算法的详细描述，请参见 https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.197.pdf。我在示例中使用 AES。

一旦获取了加密对象，可以通过设置模式和密钥来初始化它：

```java
int mode = . . .;

Key key = . . .;

cipher.init(mode, key);
```

模式有以下几种：

- `Cipher.ENCRYPT_MODE`
- `Cipher.DECRYPT_MODE`
- `Cipher.WRAP_MODE`
- `Cipher.UNWRAP_MODE`

封装（wrap）和解封（unwrap）模式用于用一个密钥加密另一个密钥——参见下一节的示例。

现在你可以反复调用 `update` 方法来加密数据块：

```java
int blockSize = cipher.getBlockSize();

var inBytes = new byte[blockSize];

.. // read inBytes
```



```java
int outputSize = cipher.getOutputSize(blockSize);

var outBytes = new byte[outputSize];

int inLength = cipher.update(inBytes, 0, blockSize, outBytes);

// write outBytes
```

完成后，你必须调用一次`doFinal`方法。如果存在最后的输入数据块（少于`blockSize`字节），调用：

```java
outBytes = cipher.doFinal(inBytes, 0, inLength);
```

如果所有输入数据都已加密，则调用：

```java
outBytes = cipher.doFinal();
```

调用`doFinal`是为了执行最后一个数据块的填充。考虑一下 DES。它的块大小为八字节。假设输入数据的最后一个块少于八字节。当然，我们可以用 0 填充剩余字节，以获得一个八字节的最后一个块并对其进行加密。但当解密这些块时，结果末尾会附加几个 0 字节，因此与原始输入文件略有不同。为了避免这个问题，我们需要一种填充方案。一种常用的填充方案是 RSA Security, Inc. 定义的[公钥密码标准 (PKCS) #5](https://datatracker.ietf.org/doc/html/rfc2898)。

在该方案中，最后一个块不是用 0 填充值填充，而是用等于填充字节数的填充值填充。换句话说，如果 L 是最后一个（不完整的）块，其填充方式如下：

- `L 01 = 7` 如果 `length(L) = 1`
- `L 02 = 06` 如果 `length(L) = 2`
- `L 03 = 05` 如果 `length(L) = 3`
- `L 04 = 04` 如果 `length(L) = 4`
- `L 05 = 03` 如果 `length(L) = 5`
- `L 06 = 02` 如果 `length(L) = 6`
- `L 07 = 01` 如果 `length(L) = 7`

### 9.4.2. 密钥生成

要生成密钥，遵循以下步骤：

1. 获取对应算法的`KeyGenerator`。
2. 使用源初始化生成器。
3. 调用`generateKey`方法。

例如，以下是生成一个密钥：

```java
KeyGenerator keygen = KeyGenerator.getInstance("AES");

var random = new SecureRandom();

keygen.init(random);

Key key = keygen.generateKey();
```

```java
/*
 * 此程序测试 AES 密算法。它可以生成密钥，
 * 或者对文件进行加密或解密。
 */
public void main(String[] args) throws Exception {
    if (args[0].equals("-genkey")) {
        KeyGenerator keygen = KeyGenerator.getInstance("AES");

        var random = new SecureRandom();

        keygen.init(random);

        SecretKey key = keygen.generateKey();

        try (var out = new ObjectOutputStream(new FileOutputStream(args[1]))) {
            out.writeObject(key);
        }
    } else {
        int mode;

        if (args[0].equals("-encrypt"))
            mode = Cipher.ENCRYPT_MODE;
        else
            mode = Cipher.DECRYPT_MODE;

        try (var keyIn = new ObjectInputStream(new FileInputStream(args[3]))) {
            var keyIn = new FileInputStream(args[1]);

            var out = new FileOutputStream(args[2]);

            var key = (Key) keyIn.readObject();

            Cipher cipher = Cipher.getInstance("AES");

            cipher.init(mode, key);

            Util.crypt(in, out, cipher);
        }
    }
}
```

### Listing 9.13 `v2ch09/aes/Util.java`

```java
package v2ch09.aes;

import java.base;

public class Util {
    /**
     * 使用密算法转换输入流中的字节，
     * 并将转换后的字节发送到输出流。
     * @param in 输入流
     * @param out 输出流
     * @param cipher 用于转换字节的密算法
     */
    public static void crypt(InputStream in, OutputStream out, Cipher cipher)
            throws IOException, GeneralSecurityException {
        int blockSize = cipher.getBlockSize();

        int outputSize = cipher.getOutputType(blockSize);

        var inBytes = new byte[blockSize];

        var outBytes = new byte[outputSize];

        int inLength = 0;

        boolean done = false;

        while (!done) {
            inLength = in.read(inBytes);

            if (inLength == blockSize) {
                int outLength = cipher.update(
                    inBytes, 0, blockSize, outBytes, 0, outLength
                );
            } else {
                done = true;
            }

            if (inLength > 0) {
                outBytes = cipher.doFinal(inBytes, 0, inLength);
            } else {
                outBytes = cipher.doFinal();
            }

            out.write(outBytes);
        }
    }
}
```

### `javax.crypto.Cipher` 1.4

- `static Cipher getInstance(String algorithmName)`
- `static Cipher getInstance(String algorithmName, String providerName)`

  返回一个实现指定算法的`Cipher`对象。如果未提供算法，则抛出`NoSuchAlgorithmException`。

- `int getBlockSize()`

  返回密算法块的大小（字节），如果该密算法不是分组密算法，则返回 0。

- `int getOutputSize(int inputLength)`

  返回如果下次输入具有给定数量的字节时，则所需的输出缓冲区大小。该方法考虑了密算法对象中任何缓冲的字节。

- `void init(int mode, Key key)`

  初始化密算法对象。`mode`为`ENCRYPT_MODE`、`DECRYPT_MODE`、`WRAP_MODE`或`UNWRAP_MODE`之一。

- `byte[] update(byte[] in)`
- `byte[] update(byte[] in, int offset, int length)`
- `int update(byte[] in, int offset, int length) byte[] out`

  转换一个块输入数据。前两个方法返回放入`out`中的字节数。

- `byte[] doFinal()`
- `byte[] doFinal(byte[])`
- `int doFinal(byte[] in, int offset, int length) byte[] out`

  转换最后一个块输入数据并刷新该密算法对象的缓冲区。前三个方法返回输出。第四个方法返回放入`out`中的字节数。

### `javax.crypto.KeyGenerator` 1.4

- `static KeyGenerator getInstance(String algorithmName)` 返回一个实现指定算法的`KeyGenerator`对象。如果未提供算法，则抛出`NoSuchAlgorithmException`。
- `void init(SecureRandom random)`
- `void init(int keySize, SecureRandom random)` 初始化密钥生成器。
- `SecretKey generateKey()` 生成新密钥。

### `javax.crypto.spec.SecretKeySpec` 1.4

- `SecretKeySpec(byte[] key, String algorithmName)` 构造一个密钥规范。

### 9.4.3. 密流

JCE 库提供了一组方便的类，可以自动加密或解密流数据。例如，以下是如何将数据加密到文件的：

```java
Cipher cipher = . . .;

cipher.init(Cipher.ENCRYPT_MODE, key);

var out = new ObjectOutputStream(new FileOutputStream(args[1]))) {
    out.writeObject(key);
}
```

等待，提供的 OCR 文本在后面的页面中似乎有一些重叠或乱码部分。让我根据提供的源文本的逻辑流重新组合 9.4.3 节。

### 9.4.3. 密流

JCE 库提供了一组方便的类，可以自动加密或解密流数据。例如，以下是如何将数据加密到文件的：

```java
Cipher cipher = . . .;

cipher.init(Cipher.ENCRYPT_MODE, key);

var out = new ObjectOutputStream(new FileOutputStream(args[1]))) {
    out.writeObject(key);
}
```

实际上，关于 705-707 页的 OCR 文本存在一些重复和交叉。我将基于可用的片段提供连贯的内容：

### 9.4.3. 密流

JCE 库提供了一组方便的类，可以自动加密或解密流数据。例如，以下是如何将数据加密到文件的：

```java
Cipher cipher = . . .;

cipher.init(Cipher.ENCRYPT_MODE, key);

var out = new ObjectOutputStream(new FileOutputStream(args[1]))) {
    out.writeObject(key);
}
```

（注：705-707 页的 OCR 文本高度碎片并包含循环。我将根据片段进行重构。）

### 9.4.4. 公钥密码

对称密算法的致命弱是密钥分发。如果 Alice 想给 Bob 发密钥，她需要通过安全通道发送。但她可能没有安全通道。

公钥密码法解决了这个问题。在公钥密码法中，Bob 拥有一由公钥和一个匹配的私钥组成的密钥对。Bob 可以在任何地方发布公钥，但他必须保护私钥。Alice 直接使用公钥加密她的信息。

实际上，所有知的公钥算法都比 AES 等对称算法慢得多。使用公钥算法加密大量信息是不切行的。然而，这个问题可以通过将公钥与快速对称算法结合来解决，如下：

1. Alice 生成随机对称密钥。她使用它加密明文。
2. Alice 使用 Bob 的公钥加密对称密钥。
3. Alice 将加密后的对称密钥和加密后的明文发送给 Bob。
4. Bob 使用他的私钥解密对称密钥。
5. Bob 使用解密的对称密钥解密消息。

同样，RSA 算法如下：

```java
KeyPairGenerator pairgen =
    KeyPairGenerator.getInstance("RSA");

var random = new SecureRandom();

pairgen.initialize(KEYSIZE, random);

Key keyPair = pairgen.generateKeyPair();

Key publicKey = keyPair.getPublic();

Key privateKey = keyPair.getPrivate();
```

最常用的公钥算法是由 Rivest、Shamir 和 Adleman 发明的 RSA 算法。直到 2000 年 10 月，该算法受 RSA Security, Inc. 的保护。许可证并不便宜——通常为 3% 的版税，每年最低支付额为 5 万美元。现在 RSA 算法已进入公共领域。

它随后生成一个包含以下内容的文件：

- 封装密钥的长度
- 封装密钥字节
- 使用 AES 密钥加密的明文

`-decrypt`参数解密此类文件。要尝试该程序，首先生成 RSA 密钥：

```java
java v2ch09.rsa.RSADemo -genkey public.key private.key
```

然后加密一个文件：

```java
java v2ch09.rsa.RSADemo -encrypt plaintextFile encryptedFile public.key
```

最后，解密它并验证解密后的文件是否与明文匹配：

```java
java v2ch09.rsa.RSADemo -decrypt encryptedFile decryptedFile private.key
```

### Listing 9.14 `v2ch09/rsa/RSADemo.java`

```java
1 package v2ch09.rsa;

2 import module java.base;

5 import v2ch09.aes.Util;

7 /**
8  * 此程序测试 RSA 加密。它可以生成公钥和私钥对，
9  * 或者加密或解密文件。
10 */
11 class RSADemo {
12     final int KEYSIZE = 512;

13     void main(String[] args) throws Exception {
14         if (args[0].equals("-genkey")) {
15             KeyPairGenerator pairgen =
16                 KeyPairGenerator.getInstance("RSA");

17             var random = new SecureRandom();

18             pairgen.initialize(KEYSIZE, random);

19             KeyPair keyPair = pairgen.generateKeyPair();

20             try (var out = new ObjectOutputStream(
21                     new FileOutputStream(args[1]))) {
22                 out.writeObject(keyPair.getPublic());
23             }

24             try (var out = new ObjectOutputStream(
25                     new FileOutputStream(args[2]))) {
26                 out.writeObject(keyPair.getPrivate());
27             }
28         } else if (args[0].equals("-encrypt")) {
29             KeyGenerator keygen = new SecureRandom();

30             keygen.init(random);

31             SecretKey key = keygen.generateKey();

32             // 使用 RSA 公钥封装

33             try (var keyIn = new ObjectInputStream(
34                     new FileInputStream(args[3]))) {
35                 var out = new ObjectOutputStream(
36                     new FileOutputStream(args[1])) {
37                     var publicKey = (Key) keyIn.readObject();
38                     Cipher cipher = Cipher.getInstance("RSA");
```



```java
39                 cipher.init(Cipher.WRAP_MODE, publicKey);
40                 byte[] wrappedKey = cipher.wrap(key);
41                 out.writeInt(wrappedKey.length);
42                 out.write(wrappedKey);
43             }
44         }
45         Cipher cipher = Cipher.getInstance("AES");
46         cipher.init(Cipher.ENCRYPT_MODE, key);
47         Util.crypt(in, out, cipher);
48     }
49     else {
50         try (var in = new DataInputStream(new FileInputStream(args[1]))) {
51             var keyIn = new ObjectInputStream(new FileInputStream(args[3])));
52             var out = new FileOutputStream(args[2]);
53             int length = in.readInt();
54             var wrappedKey = new byte[length];
55             in.read(wrappedKey, 0, length);
56
57             // 使用 RSA 私钥解封装
58             var privateKey = (Key) in.readObject();
59             Cipher cipher = Cipher.getInstance("RSA");
60             cipher.init(Cipher.UNWRAP_MODE, privateKey);
61             Key key = (Key) cipher.unwrap(wrappedKey, "AES", Cipher.SECRET_KEY);
62             cipher = Cipher.getInstance("AES");
63             cipher.init(Cipher.DECRYPT_MODE, key);
64             Util.crypt(in, out, cipher);
65         }
66     }
}
```

在本章中，你简略了解了类加载器，并接触了 Java 库提供的认证和加密服务。在此过程中，你或许会为基于安全管理器和代码签名的经典 Java 安全架构如今已成为遥远记忆而感到感叹。

在下一章中，我们将深入研究高级 Swing 和图形编程。

# 第 10 章 - 图形用户界面编程

Java 诞生时，大多数计算机通过图形用户界面（GUI）与桌面应用程序交互。如今，基于浏览器的和移动应用程序更为常见，但在某些情况下开发桌面应用程序仍然很有用。此外，许多老师和学生喜欢通过 GUI 应用程序学习 Java。在本章及后续章节中，我将讨论使用 Swing 工具包进行用户界面编程的基础。第 12 章涵盖了更高级的技术，如果你对编写 GUI 和图形程序感兴趣，可以安全地跳过这些章节。

## 10.1 Java 用户界面工具包的历史

当 Java 1.0 引入时，它包含一个名为抽象窗口工具包（AWT）的类库，用于 GUI 编程。基础 AWT 库通过将元素的创建和行为委托给每个目标平台（Windows、Linux、Macintosh 等）上的原生 GUI 工具包来处理用户界面元素。如果你使用原始的 AWT 在 Java 窗口上放置文本框，实际上是由一个“原生（peer）”文本框处理输入。生成的程序就可以在任何平台上运行。

这种原生方法虽然效果良好，但很快就发现编写高质量的用户界面变得困难。菜单、滚动条和文本字段等用户界面元素需要不断改进。

2007 年，Sun Microsystems 引入了另一个完全不同的用户界面工具包 JavaFX，作为 Flash 的竞争对手。它运行在虚拟机上，但有自己的编程语言 JavaFX Script。该语言针对动画进行了优化。程序员们对此敬而远之。2011 年，Oracle 发布了新版本 JavaFX 2.0，它拥有 Java API 而不再需要独立的编程语言。从 Java 7 更新 6 开始，JavaFX 与 JDK 绑定，但这在 Java 11 中被取消了。

1996 年，Sunscape 创建了基于 Java 基金类（JFC）的库 Swing。Swing 作为 Java 1.1 的扩展可用，并在 Java 1.2 中成为标准。Swing 现在是“绘制（painted）”工具包的官方名称。

> 注意：Swing 并不是 AWT 的完全替代品——它是基于 AWT 构建的。当你编写 Swing 程序时，使用的是功能强大的组件。从现在起，当我说“Swing”时，指的是绘制类；当我说“AWT”时，指的是窗口工具包的底层机制，例如事件处理。

当 Swing 最初发布时，用户抱怨它很慢（如果你在树莓派上运行应用程序，仍然可以感受到这种问题）。过了一段时间，桌面电脑变快了，用户抱怨 Swing 很奇怪——事实上，它已经落后于那些无论运行在什么平台上看起来和行为都相同的原生控件。

## 10.2 显示帧（Frames）

顶层窗口（即不包含在另一个窗口内的窗口）被称为帧（frame）。AWT 库有一个类 `Frame` 用于这种顶层。Swing 版本的该类称为 `JFrame`，并继承自 `Frame` 类。`JFrame` 是 Swing 组件中少数不在画布上绘制的组件之一。因此，装饰（按钮、标题栏、图标等）是由用户的窗口系统绘制的，而不是由 Swing。

> 注意：大多数 Swing 组件类以“J”开头：`JButton`、`JFrame` 等。虽然有 `Button` 和 `Frame` 等类，但它们是 AWT 组件。

由于这是一本关于 Java 核心语言和 API 的书，我将重点关注使用 Swing 进行界面编程。

如果你不小心漏掉了一个“J”，你的程序可能仍然编译并运行，但 Swing 和 AWT 组件的混合会导致视觉和行为上的不一致。

### 10.2.1 创建帧（Frame）

在本节中，我们将介绍使用 Swing `JFrame` 的最常用方法。代码列表 10.1 列出了一个在屏幕上显示空帧的简单程序，如图 10.1 所示。

![](img/240dbf1b84e081687f1e252bd386c684_714_0.png)

图 10.1：最简单的可见帧

**代码列表 10.1** `v2ch10/simpleFrame/SimpleFrame.java`

```java
package v2ch10.simpleFrame;

import javax.swing.*;

class SimpleFrameDemo {

    void main() {
        EventQueue.invokeLater(() -> {
            var frame = new SimpleFrame();
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}

class SimpleFrame extends JFrame {

    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 200;

    public SimpleFrame() {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);
    }
}
```

让我们逐行分析这个程序。

Swing 类存放在 `javax.swing` 包中。包名 `javax` 表示这是一个 Java 扩展包，而不是核心包。由于历史原因，Swing 被认为是一个扩展包。然而，自 1.2 版本以来，它在每个 Java 实现中都存在。

默认情况下，帧的尺寸为 0x0 像素，这个尺寸是相当没用的。我们定义了一个子类 `SimpleFrame`，其构造函数将尺寸设置为 300x200 像素。这是 `SimpleFrame` 和 `JFrame` 之间的唯一区别。

在 `SimpleFrameDemo` 类的 `main` 方法中，我们构造了一个 `SimpleFrame` 对象并使其可见。

在每个 Swing 程序中，我们都需要解决两个技术问题。

首先，所有的 Swing 组件必须在“事件分发线程”（event dispatch thread）中进行配置，该线程是负责将鼠标点击和击键等事件传递给用户界面组件的控制线程。以下代码片段用于在事件分发线程中执行语句：

```java
EventQueue.invokeLater(() -> {
    statements
});
```

> 注意：你会看到许多 Swing 程序并没有在事件分发线程中初始化用户界面。过去在主线程中进行初始化是完全可以的。遗憾的是，随着 Swing 组件变得越来越复杂，JDK 开发者已经无法保证这种方法的安全性了。虽然错误发生的概率极低，但你可能不想成为少数几个遇到间歇性问题的倒霉蛋之一。即使代码看起来有些奇妙，也最好是做正确的事情。

接下来，我们定义当用户关闭应用程序的帧时应该发生什么。对于这个特定的程序，我们希望程序退出。为了选择这种行为，我们使用语句：

```java
frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
```

在其他具有多个帧的程序中，你并不希望程序因为用户关闭了其中一个帧而退出。默认情况下，当用户关闭帧时，帧会被隐藏，但程序不会终止。（如果程序在最后一个帧变得不可见时就终止，那也许是可以，但那不是 Swing 的工作方式。）

仅仅构造帧并不会自动显示它。帧在创建时是不可见的。这为程序员提供了机会在第一次显示帧之前向帧中添加组件。要显示帧，`main` 方法调用了帧的 `setVisible` 方法。

在调度了初始化语句后，`main` 方法退出。退出 `main` 并不终止程序——只是终止主线程。事件分发线程会保持程序运行，直到它通过关闭帧或调用 `System.exit` 方法被终止。

运行中的程序如图 10.1 所示——这是一个真正无聊的顶层窗口。如图所示，标题栏和周围的装饰（如缩放角）是由操作系统绘制的，而不是由 Swing 库。Swing 库绘制帧内部的所有内容。在这个程序中，它只是用默认背景颜色填充了帧。

## 10.2.2 帧属性

`JFrame` 类本身只有几个用于更改帧外观的方法。当然，通过继承的魔力，用于处理帧尺寸和位置的大部分方法都自 `JFrame` 的各种父类。以下是一些最重要的方法：

- `setLocation` 和 `setBounds` 方法，用于设置帧的位置
- `setIcon` 方法，用于告诉窗口系统在标题栏、任务切换器等地方显示哪个图标
- `setTitle` 方法，用于更改标题栏中的文本
- `setResizable` 方法，接收一个布尔值来决定帧是否可以由用户缩放

图 10.2 展示了 `JFrame` 类的继承层次结构。

> 图 10.2：AWT 和 Swing 中帧和组件类的继承层次结构

正如 API 注释所示，`Component` 类（所有 GUI 对象的祖先）和 `Window` 类（`Frame` 类的子类）是你需要查找缩放和重塑帧的方法的地方。例如，`Component` 类中的 `setLocation` 方法是重新定位组件的一种方法。如果你调用：

```java
setLocation(x, y)
```

左上角将根据 `x` 和 `y` 像素定位，其中 (0,0) 是屏幕的左上角。同样，`setBounds` 方法允许在一个步骤中调整大小并移动组件：

```java
setBounds(x, y, width, height)
```

仅仅构造帧并不会自动显示它。帧的生命始于不可见状态。这为程序员提供了机会在第一次显示帧之前向帧中添加组件。要显示帧，`main` 方法调用了帧的 `setVisible` 方法。

在调度了初始化语句后，`main` 方法退出。退出 `main` 并不终止程序——只是终止主线程。事件分发线程会保持程序运行，直到它通过关闭帧或调用 `System.exit` 方法被终止。

运行中的程序如图 10.1 所示——这是一个真正无聊的顶层窗口。如图所示，标题栏和周围的装饰（如缩放角）是由操作系统绘制的，而不是由 Swing 库。Swing 库绘制帧内部的所有内容。在这个程序中，它只是用默认背景颜色填充了帧。

## 10.2.2 帧属性

`JFrame` 类本身只有几个用于更改帧外观的方法。当然，通过继承的魔力，用于处理帧尺寸和位置的大部分方法都自 `JFrame` 的各种父类。以下是一些最重要的方法：

- `setLocation` 和 `setBounds` 方法，用于设置帧的位置
- `setIcon` 方法，用于告诉窗口系统在标题栏、任务切换器等地方显示哪个图标
- `setTitle` 方法，用于更改标题栏中的文本
- `setResizable` 方法，接收一个布尔值来决定帧是否可以由用户缩放

图 10.2 展示了 `JFrame` 类的继承层次结构。

> 图 10.2：AWT 和 Swing 中帧和组件类的继承层次结构

正如 API 注释所示，`Component` 类（所有 GUI 对象的祖先）和 `Window` 类（`Frame` 类的子类）是你需要查找缩放和重塑帧的方法的地方。例如，`Component` 类中的 `setLocation` 方法是重新定位组件的一种方法。如果你调用：

```java
setLocation(x, y)
```

左上角将根据 `x` 和 `y` 像素定位，其中 (0,0) 是屏幕的左上角。同样，`setBounds` 方法允许在一个步骤中调整大小并移动组件：

```java
setBounds(x, y, width, height)
```

许多类的方法以 getter/setter 对的形式出现，例如 `Frame` 类的方法：

```java
public String getTitle();

public void setTitle(String title)
```

这样的 getter/setter 对被称为一个属性。`title` 是帧的一个属性。当我们设置属性时，我们期望标题在用户的屏幕上改变。当我们获取属性时，我们期望得到我们设置的值。

get/set 约定有一个例外：对于布尔类型的属性，getter 以 `is` 开头。例如，以下两个方法定义了 `resizable` 属性：

```java
public boolean isResizable();

public void setResizable(boolean resizable)
```

要确定帧的合适尺寸，首先获取屏幕尺寸。使用 `Toolkit` 的静态方法 `getDefaultToolKit` 获取 `Toolkit` 对象。（`Toolkit` 类是与窗口系统交互的各种方法的聚集地。）然后调用 `getScreenSize` 方法，它返回 `Dimension` 对象返回尺寸。`Dimension` 对象同时存储宽度和高度在公共实例字段 `width` 和 `height` 中。然后可以使用屏幕尺寸的适当百分比来设置帧。代码如下：

```java
Toolkit kit = Toolkit.getDefaultToolKit();

Dimension screenSize = kit.getScreenSize();

int screenWidth = screenSize.width;

int screenHeight = screenSize.height;

setSize(screenWidth / 2, screenHeight);
```

你也可以为帧提供图标：

```java
Image img = new ImageIcon("icon.gif").getImage();

setIconImage(img);
```




| `java.awt.Component` 1.0 | |
| :--- | :--- |
| `boolean isVisible()` | 获取或设置可见性属性。 |
| `void setVisible(boolean b)` | 初始为可见，顶层组件 `JFrame` 除外。 |
| `void setSize(int width, int height)` 1.1 | 将组件调整为指定的宽度和高度。 |
| `void setLocation(int x, int y)` 1.1 | 将组件移动到新位置。`x` 和 `y` 坐标如果组件不是顶层组件，则使用容器的坐标；如果组件是顶层的（例如 `JFrame`），则使用屏幕的坐标。 |
| `void setBounds(int x, int y, int height)` 1.1 | 移动并调整此组件。 |
| `Dimension getSize()` 1.1 | 获取或设置此组件的尺寸属性。 |
| `void setSize(Dimension d)` 1.1 | |

如果你不小心漏掉了一个“J”，你的程序可能仍然编译并运行，但 Swing 和 AWT 组件的混合会导致视觉和行为上的不一致。

## 10.2.1 创建帧（Frame）

在本节中，我们将介绍使用 Swing `JFrame` 的最常用方法。代码列表 10.1 列出了一个在屏幕上显示空帧的简单程序，如图 10.1 所示。

![](img/240dbf1b84e081687f1e252bd386c684_714_0.png)

图 10.1：最简单的可见帧

代码列表 10.1 `v2ch10/simpleFrame/SimpleFrame.java`

```java
package v2ch10.simpleFrame;

import javax.swing.*;

class SimpleFrameDemo {

    void main() {
        EventQueue.invokeLater(() -> {
            var frame = new SimpleFrame();
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}

class SimpleFrame extends JFrame {

    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 200;

    public SimpleFrame() {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);
    }
}
```

让我们逐行分析这个程序。

Swing 类存放在 `javax.swing` 包中。包名 `javax` 表示这是一个 Java 扩展包，而不是核心包。由于历史原因，Swing 被认为是一个扩展包。然而，自 1.2 版本以来，它在每个 Java 实现中都存在。

默认情况下，帧的尺寸为 0x0 像素，这个尺寸是相当没用的。我们定义了一个子类 `SimpleFrame`，其构造函数将尺寸设置为 300x200 像素。这是 `SimpleFrame` 和 `JFrame` 之间的唯一区别。

在 `SimpleFrameDemo` 类的 `main` 方法中，我们构造了一个 `SimpleFrame` 对象并使其可见。

在每个 Swing 程序中，我们都需要解决两个技术问题。

首先，所有的 Swing 组件必须在“事件分发线程”（event dispatch thread）中进行配置，该线程是负责将鼠标点击和击键等事件传递给用户界面组件的控制线程。以下代码片段用于在事件分发线程中执行语句：

```java
EventQueue.invokeLater(() -> {
    statements
});
```

> 注意：你会看到许多 Swing 程序并没有在事件分发线程中初始化用户界面。过去在主线程中进行初始化是完全可以的。遗憾的是，随着 Swing 组件变得越来越复杂，JDK 开发者已经无法保证这种方法的安全性了。虽然错误发生的概率极低，但你可能不想成为少数几个遇到间歇性问题的倒霉蛋之一。即使代码看起来有些奇妙，也最好是做正确的事情。

接下来，我们定义当用户关闭应用程序的帧时应该发生什么。对于这个特定的程序，我们希望程序退出。为了选择这种行为，我们使用语句：

```java
frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
```

在其他具有多个帧的程序中，你并不希望程序因为用户关闭了其中一个帧而退出。默认情况下，当用户关闭帧时，帧会被隐藏，但程序不会终止。（如果程序在最后一个帧变得不可见时就终止，那也许是可以的。）

仅仅构造帧并不会自动显示它。帧在创建时是不可见的。这为程序员提供了机会在第一次显示帧之前向帧中添加组件。要显示帧，`main` 方法调用了帧的 `setVisible` 方法。

在调度了初始化语句后，`main` 方法退出。退出 `main` 并不终止程序——只是终止主线程。事件分发线程会保持程序运行，直到它通过关闭帧或调用 `System.exit` 方法被终止。

运行中的程序如图 10.1 所示——这是一个真正无聊的顶层窗口。如图所示，标题栏和周围的装饰（如缩放角）是由操作系统绘制的，而不是由 Swing 库。Swing 库绘制帧内部的所有内容。在这个程序中，它只是用默认背景颜色填充了帧。

## 10.2.2 帧属性

`JFrame` 类本身只有几个用于更改帧外观的方法。当然，通过继承，用于处理帧尺寸和位置的大部分方法都来自 `JFrame` 的各种父类。以下是一些最重要的方法：

- `setLocation` 和 `setBounds` 方法，用于设置帧的位置。
- `setIcon` 方法，用于告诉窗口系统在标题栏、任务切换器等地方显示哪个图标。
- `setTitle` 方法，用于更改标题栏中的文本。
- `setResizable` 方法，接收一个布尔值来决定帧是否可以由用户缩放。

图 10.2 展示了 `JFrame` 类的继承层次结构。

> 图 10.2：AWT 和 Swing 中帧和组件类的继承层次结构

正如 API 注释所示，`Component` 类（所有 GUI 对象的祖先）和 `Window` 类（`Frame` 类的子类）是你需要查找缩放和重塑帧的方法的地方。例如，`Component` 类中的 `setLocation` 方法是重新定位组件的一种方法。如果你调用：

```java
setLocation(x, y)
```

左上角将根据 `x` 和 `y` 像素定位，其中 `(0, 0)` 是屏幕的左上角。同样，`setBounds` 方法允许在一个步骤中调整大小并移动组件：

```java
setBounds(x, y, width, height)
```

许多类的方法以 getter/setter 对的形式出现，例如 `Frame` 类的方法：

```java
public String getTitle();

public void setTitle(String title);
```

这样的 getter/setter 对被称为一个属性。`title` 是帧的一个属性。当我们设置属性时，我们期望标题在用户的屏幕上改变。当我们获取属性时，我们期望得到我们设置的值。

`get/set` 约定有一个例外：对于布尔类型的属性，getter 以 `is` 开头。例如，以下两个方法定义了 `resizable` 属性：

```java
public boolean isResizable();

public void setResizable(boolean resizable);
```

要确定帧的合适尺寸，首先获取屏幕尺寸。使用 `Toolkit` 的静态方法 `getDefaultToolkit` 获取 `Toolkit` 对象。（`Toolkit` 类是与窗口系统交互的各种方法的聚集地。）然后调用 `getScreenSize` 方法，它返回 `Dimension` 对象表示的尺寸。`Dimension` 对象同时将宽度和高度存储在公共实例字段 `width` 和 `height` 中。然后可以使用屏幕尺寸的适当百分比来设置帧。代码如下：

```java
Toolkit kit = Toolkit.getDefaultToolkit();

Dimension screenSize = kit.getScreenSize();

int screenWidth = screenSize.width;

int screenHeight = screenSize.height;

setSize(screenWidth / 2, screenHeight);
```

你也可以为帧提供图标：

```java
Image img = new ImageIcon("icon.gif").getImage();

setIconImage(img);
```

| `java.awt.Component` 1.0 | |
| :--- | :--- |
| `boolean isVisible()` | 获取或设置可见性属性。 |
| `void setVisible(boolean b)` | 初始为可见，顶层组件 `JFrame` 除外。 |
| `void setSize(int width, int height)` 1.1 | 将组件调整为指定的宽度和高度。 |
| `void setLocation(int x, int y)` 1.1 | 将组件移动到新位置。`x` 和 `y` 坐标如果组件不是顶层组件，则使用容器的坐标；如果组件是顶层的（例如 `JFrame`），则使用屏幕的坐标。 |
| `void setBounds(int x, int y, int height)` 1.1 | 移动并调整此组件。 |
| `Dimension getSize()` 1.1 | 获取或设置此组件的尺寸属性。 |
| `void setSize(Dimension d)` 1.1 | |

### `java.awt.Frame` 1.0

- `boolean isResizable()`
- `void setResizable(boolean b)`  
  获取或设置可调整大小属性。当该属性被设置时，用户可以调整帧的大小。
- `String getTitle()`
- `void setTitle(String s)`  
  获取或设置标题属性，该属性决定帧标题栏中的文本。
- `Image getImage()`
- `void setIconImage(Image image)`  
  获取或设置图标属性，该属性决定帧的图标。窗口系统可能会将图标作为帧装饰的一部分或在其他位置显示。

### `java.awt.Toolkit` 1.0

- `static Toolkit getDefaultToolkit()`  
  返回此平台的默认工具包。
- `Dimension getScreenSize()`  
  获取用户屏幕的大小。

### `javax.swing.ImageIcon` 1.2

- `ImageIcon(String filename)`  
  构造一个图像存储在文件中的图标。
- `Image getImage()`  
  获取此图标的图像。

## 10.3 在组件中显示信息

在本节中，我将向你展示如何在帧内显示信息（图 10.3）。

![](img/240dbf1b84e081687f1e252bd386c684_718_0.png)

**图 10.3：** 显示信息的帧

你可以直接将消息字符串画在帧上，但这不被认为是良好的编程实践。在 Java 中，帧的设计初衷是作为组件的容器，例如菜单栏和其他用户界面元素。你通常在添加到帧的另一个组件上进行绘图。

`JFrame` 的结构出奇地复杂。看图 10.4，它显示了 `JFrame` 的组成部分。如你所见，`JFrame` 中层叠了四个面板。根面板（root pane）、分层面板（layered pane）和玻璃面板（glass pane）对我们没有意义；它们是组织菜单栏和内容面板以实现外观效果所必需的。Swing 程序员关注的部分是内容面板（content pane）。任何添加到帧的组件都会自动放置在内容面板中：

```java
Component c = ...;

frame.add(c); // 已添加到内容面板中
```

## 图 10.4：`JFrame` 的内部结构

在我们的情况下，我们想向帧添加单个组件，并在其上绘制我们的消息。要在组件上绘图，请定义一个扩展 `JComponent` 的类，并重写该类中的 `paintComponent` 方法。

`paintComponent` 方法有一个类型为 `Graphics` 的参数。`Graphics` 对象记录了用于绘制图像和文本的设置集合，例如你设置的字体或当前颜色。Java 中所有的绘图都必须通过 `Graphics` 对象进行。它拥有绘制形状、图像和文本的方法。

以下是创建一个你可以在上面绘图的组件的方法：

```java
class MyComponent extends JComponent {

    public void paintComponent(Graphics g) {
        // 绘图代码
    }
}
```

每当窗口需要重绘时，无论出于什么原因，事件处理器都会通知该组件。这会导致所有组件的 `paintComponent` 方法被执行。

永远不要自己手动调用 `paintComponent` 方法。每当应用程序的部分需要重绘时，该方法就会被自动调用，并且不会干扰这个自动过程。

什么类型的操作会触发这种自动响应？例如，当用户增大窗口尺寸时进行绘图，或者最小化然后恢复窗口。如果用户弹出一个覆盖现有窗口的另一个窗口，然后让覆盖的窗口消失，那么被覆盖的窗口现在就损坏了，需要重新绘制（`Graphics` 系统不保存下方的像素）。而且，当窗口第一次被显示时，它需要处理指定你应该如何以及在何处绘制初始元素的代码。

> **提示：** 如果你需要强制重绘屏幕，请调用 `repaint` 方法而不是 `paintComponent` 方法。`repaint` 方法会导致所有组件都调用 `paintComponent`，并传入一个配置良好的 `Graphics` 对象。

当你使用代码帧时，`paintComponent` 方法有一个类型为 `Graphics` 的单一参数。在 `Graphics` 对象上进行的屏幕显示测量是以像素为单位的。`(0, 0)` 坐标表示你正在绘图的组件的左上角。

`Graphics` 类有各种绘图方法，而显示文本被视为一种特殊的绘图。我们的 `paintComponent` 方法看起来如下：

```java
public class HelloWorldComponent extends JComponent {

    public static final int MESSAGE_X = 75;
    public static final int MESSAGE_Y = 100;

    public void paintComponent(Graphics g) {
        g.drawString("Not a Hello, World program", MESSAGE_X, MESSAGE_Y);
    }
}
```

最后，组件应该告诉用户它希望自己有多大。重写 `getPreferredSize` 方法并返回一个带有偏好宽度和高度的 `Dimension` 类对象：

```java
public class HelloWorldComponent extends JComponent {

    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 200;

    public Dimension getPreferredSize() {
        return new Dimension(DEFAULT_WIDTH, DEFAULT_HEIGHT);
    }
}
```

当你用一个或多个组件填充帧时，如果你只是简单地使用你的偏好尺寸，请调用 `pack` 方法：

```java
class HelloWorldFrame extends JFrame {

    public HelloWorldFrame() {
        add(new HelloWorldComponent());
        pack();
    }
}
```

## 列表 10.2：显示完整代码

```java
package javax.swing;

import java.awt.*;
import java.awt.event.*;

class HelloWorld {

    public static void main(String[] args) {
        EventQueue.invokeLater(() -> {
            JFrame frame = new HelloWorldFrame();
            frame.setTitle("HelloWorld");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}
```




```java
class HelloWorldFrame extends JFrame {

    public HelloWorldFrame() {
        add(new HelloWorldComponent());
        pack();
    }
}

class HelloWorldComponent extends JComponent {

    public static final int MESSAGE_X = 75;
    public static final int MESSAGE_Y = 100;

    public void paintComponent(Graphics g) {
        g.drawString("Not a Hello, World program", MESSAGE_X, MESSAGE_Y);
    }
}
```

### 10.3.1 使用 2D 形状

从 Java 1.0 开始，`Graphics` 类有绘制线条、矩形、椭圆等的方法。但那些绘图操作非常有限。我们改为使用 Java 2D 库。

要使用该库，你需要获取一个 `Graphics2D` 对象。该类是 `Graphics` 类的子类。从 Java 1.2 开始，像 `paintComponent` 这样的方法会自动接收一个 `Graphics2D` 对象。只需进行类型转换即可：

```java
public void paintComponent(Graphics g) {
    Graphics2D g2 = (Graphics2D) g;
}
```

Java 2D 库以面向对象的方式组织几何形状。特别是，有用于表示线条、矩形和椭圆的类：

- `Line2D`
- `Rectangle2D`
- `EllipseD`

它们都实现了 `Shape` 接口。Java 2D 库支持更复杂的形状——弧、二次和三次曲线以及通用路径，这些我们在本章中不讨论。

要绘制形状，首先创建一个实现 `Shape` 接口的类的对象，并调用 `Graphics2D` 类的 `draw` 方法。例如：

```java
Rectangle2D rect = . . .;
g2.draw(rect);
```

Java 2D 库使用浮点坐标而不是整数像素。内部计算使用单精度浮点数进行。单精度是足够的——毕竟，几何计算的最终目的是在屏幕或打印机上设置像素。只要舍入误差在一个像素范围内，视觉结果就不会受到影响。

然而，对于程序员来说，操作 `float` 值有时是不方便的，因为 Java 在将 `double` 值转换为 `float` 值时强硬要求进行类型转换。例如，考虑以下语句：

```java
float f = 1.2; // ERROR--可能丢失精度
```

此语句无法编译，因为常量 1.2 的类型是 `double`，而编译器担心丢失精度。解决办法是在浮点数常量后加上 `F` 后缀：

```java
float f = 1.2F; // OK
```

现在考虑此语句：

```java
float f = r.getWidth(); // ERROR
```

此语句同样无法编译，原因相同。`getWidth()` 方法返回一个 `double` 值。这次的解决办法是提供一个类型转换：

```java
float f = (float) r.getWidth(); // OK
```

这些后缀和类型转换有些麻烦，因此 2D 库的设计者决定对每个形状类使用两个版本：一个带有 `float` 坐标以供节约程序员使用，另一个带有 `double` 坐标以供懒惰的人使用。（在书中，我们属于第二阵营，尽可能使用 `double` 坐标。）

库的设计者为这些选择选择了一种奇特的机制。考虑 `Rectangle2D` 类。这是一个抽象类，具有两个具体的子类，这两个子类同时也是静态嵌套类：

- `Rectangle2D.Float`
- `Rectangle2D.Double`

图 10.5 显示了继承关系。

## 图 10.5：2D 矩形类

最好忽略这两个具体类是静态内部类的事实——这只是为了避免命名为 `FloatRectangle2D` 和 `DoubleRectangle2D` 的一种技巧。

当你构造一个 `Rectangle2D.Float` 对象时，你提供的坐标是 `float` 数字。对于 `Rectangle2D.Double` 对象，你提供的则是 `double` 数字。

```java
var floatRect = new Rectangle2D.Float(10.0F, 25.0F, 22.5F, 20.0);
var doubleRect = new Rectangle2D.Double(10.0, 25.0, 22.5, 20.0);
```

构造参数表示矩形的左上角、宽度和高度。

`Rectangle2D` 方法具有 `double` 参数类型和返回类型。例如，`getWidth()` 方法返回一个 `double` 值，即使宽度在 `Rectangle2D.Float` 对象中是以 `float` 存储的。

> 提示：直接使用 `Double` 形状类以完全避免处理 `float` 值。然而，如果你正在构造数千个形状对象，请考虑使用 `Float` 类来节省内存。

我们刚刚对 `Rectangle2D` 类讨论的内容也适用于其他形状类。此外，还有一个 `Point2D` 类，带有子类 `Point2D.Float` 和 `Point2D.Double`。以下是创建点对象的方法：

```java
var p = new Point2D.Double(10, 20);
```

`Rectangle2D` 和 `Ellipse` 类都继承自共同父类 `RectangularShape`。诚然，椭圆不是矩形，但它们有一个外接矩形（见图 10.6）。

## 图 10.6：椭圆的外接矩形

`RectangularShape` 类定义了 20 多个这些形状通用的方法，其中包含实用的方法如 `getWidth`、`getCenterX` 和 `getCenterY`（但遗憾的是，在写作时，没有 `getCenter` 方法可以返回 `Point2D` 对象作为中心）。

最后，几个来自 Java 1.0 的遗留类被置入了形状层次结构中。`Rectangle2D` 和 `Point` 类存储具有整数坐标的矩形和点，它们继承自 `Rectangle2D` 和 `Point2D` 类。

图 10.7 显示了形状类之间的关系。然而，省略了 `Double` 和 `Float` 子类。遗留类用灰色填充标记。

## 图 10.7：形状类之间的关系

`Rectangle2D` 和 `Ellipse` 对象很容易构造。你需要指定：

- 左上角的 x 和 y 坐标
- 宽度和高度

对于椭圆，这些指的是外接矩形。例如：

```java
var e = new Ellipse2D.Double(150, 200, 100, 50);
```

这构造了一个由矩形边界的椭圆，其左上角位于 (150, 200)，宽度为 100，高度为 50。

在构造椭圆时，你通常知道中心、宽度和高度，但不知道外接矩形的角点（这些点甚至不在椭圆上）。`setFrameFromCenter` 方法使用了中心，但它仍然需要四个角点之一。因此，你通常会如下所示构造它：

```java
var ellipse =
    new Ellipse2D.Double(centerX - width / 2, centerY - height / 2, width, height);
```

要构造直线，你提供起点和终点，可以作为 `Point2D` 对象，也可以作为数字对：

```java
var line = new Line2D.Double(start, end);
```

或者：

```java
var line = new Line2D.Double(startX, startY, endX, endY);
```

代码列表 10.3 中的程序绘制了一个矩形、包含在矩形内的椭圆、矩形的对角线，以及一个与矩形相同中心的圆。图 10.8 显示了结果。

![](img/240dbf1b84e081687f)

**图 10.8：** 画形状

## 列表 10.3

```java
package java.awt;

import java.awt.geom.*;

import javax.swing.*;

import java.awt.event.EventQueue;

public class DrawDemo {

    private static final int DEFAULT_WIDTH = 400;

    private static final int DEFAULT_HEIGHT = 400;

    public static void main(String[] args) {

        EventQueue.invokeLater(() -> {

            var frame = new DrawFrame();

            frame.setVisible(true);

        });

    }

}

class DrawFrame extends JFrame {

    public DrawFrame() {

        add(new DrawComponent());

        pack();

        setTitle("DrawTest");

        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        setSize(new Dimension(DEFAULT_WIDTH, DEFAULT_HEIGHT));

    }

}

class DrawComponent extends JComponent {

    @Override

    public void paintComponent(Graphics g) {

        Graphics2D g2 = (Graphics2D) g;

        double leftX = 100;

        double topY = 100;

        double width = 200;

        double height = 150;

        var rect = new Rectangle2D.Double(leftX, topY, width, height);

        g2.draw(rect);

        // 画包含的椭圆

        var ellipse = new Ellipse2D.Double();

        ellipse.setFrame(rect);

        g2.draw(ellipse);

        // 画对角线

        g2.draw(new Line2D.Double(leftX, topY, leftX + width, topY + height));

        // 画相同中心的圆

        double centerX = rect.getCenterX();

        double centerY = rect.getCenterY();

        double radius = 50;

        var circle = new Ellipse2D.Double();

        circle.setFrameFromCenter(centerX, centerY, radius, radius);

        g2.draw(circle);

    }

    @Override

    public Dimension getPreferredSize() {

        return new Dimension(DEFAULT_WIDTH, DEFAULT_HEIGHT);

    }

}
```

```java
g2.setPaint(Color.RED);
g2.drawString("Warning!", 100, 100);
```

你可以用颜色填充封闭形状（如矩形或椭圆）的内部。只需调用 `fill` 而不是 `draw` 即可：

```java
Rectangle2D rect = ...;

g2.setPaint(Color.RED);

g2.fill(rect); // 用红色填充 rect
```

若要绘制多种颜色，可以选择一种颜色，进行绘制或填充，然后选择另一种颜色，再次进行绘制或填充。

> 注意：该方法绘制的右侧和底部会少一个像素。例如，如果你绘制了一个新的 `Rectangle2D.Double(0, 0, 10, 20)`，该绘制将包含 `x = 10` 和 `y = 20` 的像素。如果你填充同一个矩形，这些像素将不会被绘制。

使用 `Color` 类定义颜色。`java.awt.Color` 类提供了以下 13 种标准颜色的预定义常量：

`BLACK`（黑色）、`BLUE`（蓝色）、`CYAN`（青色）、`DARK GRAY`（深灰色）、`GRAY`（灰色）、`GREEN`（绿色）、`LIGHT_GRAY`（浅灰色）、`MAGENTA`（洋红色）、`ORANGE`（橙色）、`PINK`（粉色）、`RED`（红色）、`WHITE`（白色）、`YELLOW`（黄色）

你可以通过红、绿、蓝组件创建 `Color` 对象来指定自定义颜色，每个值在 0 到 255 之间：

```java
g2.setPaint(new Color(0, 128, 128)); // 一种暗的蓝绿色
g2.drawString("Welcome!", 75, 125);
```

> 注意：除了固色，你可以使用实现 `Paint` 接口类的实例调用 `setPaint`。这允许使用渐变和纹理绘制。

要设置组件的背景颜色，请使用 `Component` 类（`JComponent` 的祖类）的 `setBackground` 方法：

```java
var component = new MyComponent();
component.setBackground(Color.PINK);
```

还有一个 `foreground` 方法。它指定用于在组件上绘制的默认颜色。

## `java.awt.Color` 1.0

- `Color(int r, int g, int b)`：一个具有给定 0 到 255 之间的红、绿、蓝组件的颜色对象。

## `java.awt.Graphics2D` 1.2

- `Paint getPaint()`
- `void setPaint(Paint p)`：获取或设置图形上下文的绘制画属性。`Color` 类实现了 `Paint` 接口。因此，你可以使用此方法将绘制属性设置为固色。
- `void fill(Shape s)`：用当前的绘制画填充形状。

## `java.awt.Component` 1.0

- `Color getForeground()`
- `Color getBackground()`
- `void setForeground(Color c)`
- `void setBackground(Color c)`：获取或设置前景颜色或背景颜色。

### 10.3.3 使用字体

本章开头的“Hello World”程序使用默认字体显示字符串。有时你想用不同的字体显示你的文本。你可以通过*字体族名称*（font face name）指定字体。字体名称由*字体族名称*（font family name，如 `"Helvetica"`）和一个可选的后缀（如 `"Bold"`）组成。例如，字体族 `"Helvetica"` 和 `"Helvetica Bold"` 都被认为属于 `"Helvetica"` 族的一部分。

要查找特定计算机上可用的字体，请调用 `GraphicsEnvironment` 类的 `getAvailableFontNames` 方法。该方法返回一个包含所有可用字体名称的字符串数组。要获取描述用户图形环境的 `GraphicsEnvironment` 类实例，请使用静态方法 `getLocalGraphics`。以下程序打印你系统上所有字体的名称：

```java
import java.awt.*;

void main(String[]) {

    String[] fontNames = GraphicsEnvironment
        .getLocalGraphics()
        .getAvailableFontFamilyNames();

    for (String fontName : fontNames) {
        System.out.println(fontName);
    }

}
```

AWT 定义了五个*逻辑*字体名称：

- `SansSerif`（无衬线）
- `Serif`（衬线）
- `Monospaced`（等宽）
- `Dialog`（对话框）
- `DialogInput`（对话框输入）

这些名称始终映射到客户端上实际存在的字体。例如，在 Windows 系统上，`SansSerif` 映射到 Arial。

此外，Oracle JDK 始终包含三个名为 `"Lucida Sans"`、`"Lucida Bright"` 和 `"Lucida Sans Typewriter"` 的字体族。

要用某种字体绘制字符，你必须先创建字体类的对象。指定字体名称、样式和点数大小。这里是如何构造 `Font` 对象的示例：

```java
var sansbold14 = new Font("SansSerif", Font.BOLD, 14);
```



第三个参数是点数大小。点在排版中通常用于指示字体的大小。每英寸有 72 点。

你可以在`Font`构造函数的字体族名称中使用逻辑字体名称。通过将第二个`Font`构造函数参数设置为以下内容之一来指定样式（标准、粗体、斜体或粗斜体）：

- `Font.PLAIN`
- `Font.BOLD`
- `Font.ITALIC`
- `Font.BOLD + Font.ITALIC`

以下代码在你的系统上使用标准衬线字体、14 点字体类型显示字符串 "Hello, World!"：

```java
var sansbold14 = new Font("SansSerif", Font.BOLD, 14);

g2.setFont(sansbold14);

var message = "Hello, World!";

g2.drawString(message, 75, 125);
```

```java
49 double y = (getHeight() - bounds.getHeight()) / 2;

// 为 y 添加上升高度以到达基线
53 double ascent = -bounds.getY();
54 double baseY = y + ascent;

// 绘制消息
58 g2.drawString(message, (int) x, (int) baseY);
59
60 g2.setPaint(Color.LIGHT_GRAY);

// 绘制基线
65 g2.draw(new Line2D.Double(x, baseY, x + bounds.getWidth(), baseY));

// 绘制外矩形
70 var rect = new Rectangle2D.Double(x, y, bounds.getWidth(), bounds.getHeight());
71 g2.draw(rect);

74 public Dimension getPreferredSize() {
75     return new Dimension(DEFAULT_WIDTH, DEFAULT_HEIGHT);
76 }
```

## `java.awt.FontMetrics` 1.0

- `Font(String name, int style, int size)` 创建一个新的字体对象。字体名称可以是具体的字体名称（如 "Helvetica Bold"）或逻辑名称（如 "Serif", "SansSerif"）。样式可以是`Font`、`Font.BOLD`、`Font.ITALIC`或`Font.BOLD + Font.ITALIC`之一。
- `StringFontName()` 获取字体脸名称（如 "Helvetica Bold"）。
- `StringFontFamily()` 获取字体族名称（如 "Helvetica"）。
- `StringGetName()` 如果字体是用逻辑字体名称创建的，则获取逻辑名称（如 "SansSerif"）；否则，获取字体名称。
- `Rectangle2D getBounds(String s, FontRenderContext context)` 1.2 返回一个包含字符串的矩形。矩形的原点位于基线上。矩形的顶部 y 坐标等于上升高度（ascent）的负值。矩形的高度等于上升高度、下降高度（descent）和行距（leading）之和。宽度等于字符串宽度。
- `LineMetrics getLineMetrics(String s, FontRenderContext context)` 1.2 返回一个行度对象以确定字符串的范围。

## `java.awt.font.LineMetrics` 1.2

- `floatAscent()` 获取字体上升高度——从基线到大写字母顶部的距离。
- `float getDescent()` 获取字体下降高度——从基线到下降字母（descenders）底部的距离。
- `float getLeading()` 获取字体行距——一行文本底部与下一行顶部之间的空间。
- `float getHeight()` 获取字体的总高度——文本两个基线之间的距离（下降高度 + 行距 + 上升高度）。

## `java.awt.Graphics2D` 1.2

- `FontRenderContext getRenderContext()` 获取指定此图形上下文字体特征的渲染上下文。
- `void drawString(String str, float x, float y)` 用当前的字体和颜色绘制字符串。

## `javax.swing.JButton` 1.2

- `FontMetrics getFontMetrics(Font f)` 5.0 获取字体的字体度量。`FontMetrics`类是`LineMetrics`类的前身。

## `java.awt.FontMetrics` 1.0

- `FontRenderContext getRenderContext()` 1.2 获取该字体的渲染上下文。

## 10.3.4. 显示图像

你可以使用`ImageIcon`类从文件读取图像：

```java
Image image = new ImageIcon(filename).getImage();
```

现在变量`image`包含指向封装图像数据的对象的引用。使用`Graphics`类的`drawImage`方法显示图像。

```java
public void paintComponent(Graphics g) {
    g.drawImage(image, x, y, null);
}
```

我们可以更进一步，用图形图像对窗口进行平铺填充。结果如图 10.11 所示。我们在`paintComponent`方法中执行此操作。我们首先在左上角绘制图像的一个副本，并使用`copyArea`调用将其复制到整个窗口：

```java
for (int i = 0; i * imageWidth <= getWidth(); i++)
  for (int j = 0; j * imageHeight <= getHeight(); j++)
    if (i + j > 0)
      g.copyArea(0, 0, imageWidth, imageHeight, i * imageWidth, j * imageHeight);
```

![](img/240dbf1b84e081687f1e252bd386c684_735_0.png)

图 10.11：带有平铺图形的窗口

## 列表 10.5 `v2ch10/image/ImageDemo.java`

```java
package v2ch10.image;

import java.awt; // 已修复 OCR 错误

class ImageDemo {

  void main(String[] args) {

    EventQueue.invokeLater(() -> {

      JFrame frame = new ImageFrame();

      frame.setTitle("ImageTest");

      frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

      frame.setVisible(true);

    });

  }

}

/**
 * 带有组件的框架。
 */
class ImageFrame extends JFrame {

  public ImageFrame() {

    add(new ImageComponent());

    pack();

  }

}

/**
 * 一个显示平铺图像的组件。
 */
class ImageComponent extends JComponent {

  private static final int DEFAULT_WIDTH = 300;

  private static final int DEFAULT_HEIGHT = 200;

  private Image image;

  public ImageComponent() {

    image = new ImageIcon("images/blue-ball.gif").getImage();

  }

  public void paintComponent(Graphics g) {

    if (image == null) return;

    int imageWidth = image.getWidth(null);

    int imageHeight = image.getHeight(null);

    if (imageWidth <= 0 || imageHeight <= 0) return;

    // 在左上角绘制图像
    g.drawImage(image, 0, 0, null);

    // 跨越组件平铺图像
    for (int i = 0; i * imageWidth <= getWidth(); i++) {

      for (int j = 0; j * imageHeight <= getHeight(); j++) {

        if (i + j > 0)
          g.copyArea(0, 0, imageWidth, imageHeight, i * imageWidth, j * imageHeight);

      }

    }

  }

}
```

### 10.4.2. 示例：处理按钮点击

为了熟悉事件委托模型，让我们详细介绍实现响应按钮点击这一简单示例所需的所有细节。在这个示例中，我们将展示一个包含三个按钮的面板。三个监听器对象（listener objects）作为动作监听器（action listeners）被添加到按钮。

在这种情况下，当用户每次点击面板上的任何按钮时，关联的监听器对象都会接收一个指示按钮点击的`ActionEvent`。在我们的示例程序中，监听器对象随后监听面板的背景颜色。

在向您展示监听按钮点击程序之前，我需要解释如何创建按钮以及如何将它们添加到面板中。

要创建一个按钮，可以在按钮构造函数中指定标签字符串、图标或两者。以下是两个示例：

```java
var yellowButton = new JButton("Yellow");

var activeButton = new JButton(new ImageIcon("blue-ball.gif"));
```

调用`add`方法将按钮添加到面板中：

```java
var yellowButton = new JButton("Yellow");

var blueButton = new JButton("Blue");

var redButton = new JButton("Red");

buttonPanel.add(yellowButton);

buttonPanel.add(blueButton);

buttonPanel.add(redButton);
```

**图 10.14** 显示了结果。

![](img/240dbf1b84e081687f1e252bd386c684_738_0.png)

**图 10.14：** 填充了按钮的面板

接下来，我们需要添加监听这些按钮的代码。这需要实现`ActionListener`接口的类，正如我刚才提到的，它有一个方法：`actionPerformed`，其签名如下：

```java
public void actionPerformed(ActionEvent event)
```

使用`ActionListener`接口的方法在所有情况下都是相同的：`actionPerformed`方法（它是`ActionListener`中唯一的方法）接收一个`ActionEvent`类型的对象作为参数。这个事件对象可以为您提供关于所发生事件的信息。

当按钮被点击时，我们希望面板的背景颜色改变为特定的颜色。我们将所需的颜色存储在监听器类中。

```java
class ColorAction implements ActionListener {

    private Color backgroundColor;

    public ColorAction(Color c) {

        backgroundColor = c;

    }

    public void actionPerformed(ActionEvent event) {

        // 设置背景颜色

        ..

    }

}
```

然后我们为每个颜色构造一个对象，并将这些对象设置为按钮监听器。

```java
var yellowAction = new ColorAction(Color.YELLOW);

var blueAction = new ColorAction(Color.BLUE);

var redAction = new ColorAction(Color.RED);

yellowButton.addActionListener(yellowAction);

blueButton.addActionListener(blueAction);

redButton.addActionListener(redAction);
```

例如，如果用户点击标记为 "Yellow" 的按钮，`yellowAction`实例字段的`actionPerformed`方法将被设置为`Color.YELLOW`，现在它就可以继续设置面板的背景颜色了。

仅剩下一个问题。`ColorObject`无法访问面板变量。你有两种方法解决这个问题。你可以将面板存储在`ColorObject`中并在`ColorAction`构造函数中设置它。或者更方便地，你可以让`ColorAction`成为`ButtonFrame`类的内部类。这样这些方法就可以自动访问外部面板。

**列表 10.6** 包含了完整的框架类。每当您点击其中一个按钮时，相应的动作监听器就会更改面板的背景颜色。

## 列表 10.6 `v2ch10/button/ButtonFrame.java`

```java
package v2ch10.button;

import java.desktop;

/**
 * 一个带有按钮面板的框架。
 */
public class ButtonFrame extends JFrame {
    private JPanel buttonPanel;
    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 200;

    public ButtonFrame() {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

        // 创建按钮
        var yellowButton = new JButton("Yellow");
        var blueButton = new JButton("Blue");
        var redButton = new JButton("Red");

        buttonPanel = new JPanel();

        // 将按钮添加到面板
        buttonPanel.add(yellowButton);
        buttonPanel.add(blueButton);
        buttonPanel.add(redButton);

        // 将面板添加到框架
        add(buttonPanel);

        // 创建按钮动作
        var yellowAction = new Color(Color.YELLOW);
        var blueAction = new Color(Color.BLUE);
        var redAction = new Color(Color.RED);

        // 将动作与按钮关联
        yellowButton.addActionListener(yellowAction);
        blueButton.addActionListener(blueAction);
        redButton.addActionListener(redAction);
    }

    /*
     * 设置面板背景颜色的监听器。
     */
    private class ColorAction implements ActionListener {
        private Color backgroundColor;

        public ColorAction(Color c) {
            backgroundColor = c;
        }

        public void actionPerformed(ActionEvent event) {
            buttonPanel.setBackground(backgroundColor);
        }
    }
}
```

| `javax.swing.JButton` 1.2 |
| --- |
| ■ `JButton(String label)` |
| ■ `JButton(Icon icon)` |
| ■ `JButton(String label, Icon icon)` construct |
| `javax.swing.JButton` 1.2 |



| :--- |
| `■ JButton(String label)` |
| `■ JButton(Icon icon)` |
| `■ JButton(String label, Icon icon)` construct |
| `java.awt.Component 1` |
| :--- |
| `add(Component)` |

### 10.4.3. 简洁地指定监听器

并不是所有事件都像按钮点击那样容易处理。假设你想要监控用户尝试关闭主框架的操作，以便弹出对话框并在用户同意后才退出程序。

当用户尝试关闭窗口时，`JFrame` 对象是 `ActionEvent` 的源头。如果你想捕获它，你需要一个适当的监听器并将其添加到框架列表中。

```java
WindowListener listener = ... ;
frame.addWindowListener(listener);
```

监听器必须是实现 `WindowListener` 接口的对象。`WindowListener` 接口实际上包含了七种可能发生在窗口上的事件。这里是完整的 `WindowListener` 接口：

```java
public interface WindowListener {
    void windowOpened(WindowEvent e);
    void windowClosing(WindowEvent e);
    void windowClosed(WindowEvent e);
    void windowIconified(WindowEvent e);
    void windowDeiconified(WindowEvent e);
    void windowActivated(WindowEvent e);
    void windowdeactivated(WindowEvent e);
}
```

当然，我们可以定义一个实现接口的类，在 `windowClosing` 方法中添加 `System.exit(0)` 的调用，并为其他方法编写空函数。然而，为六个没有操作的方法编写代码是没人喜欢的无聊工作。为了简化这项任务，每个具有多个方法的 AWT 接口都带有一个相应的适配器类（adapter class），该类实现了接口中的所有方法但不对其执行任何操作。例如，`WindowAdapter` 类拥有七个空方法。你可以扩展适配器类来对接口中的某些而非所有事件类型指定所需的反应。（像 `ActionListener` 这样只有一个方法的接口不需要适配器类。）

以下是我们如何定义一个重写了 `windowClosing` 方法的窗口监听器的：

```java
class Terminator extends WindowAdapter {
    public void windowClosing(WindowEvent e) {
        if (user agrees)
            System.exit(0);
        }
    }
}
```

现在可以将 `Terminator` 类型的对象注册为事件监听器：

### 10.4.4. 适配器类

并不是所有事件都像按钮点击那样容易处理。假设你想要监控用户尝试关闭主框架的操作，以便弹出对话框并在用户同意后才退出程序。

当用户尝试关闭窗口时，`JFrame` 对象是 `ActionEvent` 的源头。如果你想捕获它，你需要一个适当的监听器对象并将其添加到框架列表中。

当然，这种相当冗长的代码不再需要了。使用 Lambda 表达式更加简单且清晰：

```java
exitButton.addActionListener(new ActionListener() {
    public void actionPerformed(ActionEvent event) {
        System.exit(0);
    }
});
```

```java
var listener = new Terminator();
frame.addWindowListener(listener);
```

> 注意：现在，人们通常会将 `WindowListener` 接口中的空方法实现为默认方法。然而，Swing 的发明是在默认方法出现之前的很多年前了。

## `java.awt.event.EventListener` 1.1

- `void windowOpened(WindowEvent e)`

  在窗口打开后调用。

- `void windowClosing(WindowEvent e)`

  在用户使用窗口管理器关闭窗口后调用。注意，只有当调用窗口的 `hide` 或 `dispose` 方法时，窗口才会关闭。

- `void windowClosed(WindowEvent e)`

  在窗口关闭后调用。

- `void windowIconified(WindowEvent e)`

  在窗口被最小化（变为图标化状态）后调用。

- `void windowDeiconified(WindowEvent e)`

  在窗口恢复还原状态后调用。

- `void windowActivated(WindowEvent e)`

  在窗口变为激活后调用。只有帧（frame）或对话框会装饰激活窗口——例如，通过高亮标题栏。

- `void windowDeactivated(WindowEvent e)`

  在窗口失去激活后调用。

## `java.awt.event.WindowStateListener` 1.4

- `void windowChanged(WindowEvent event)`

  在窗口最大化、最小化或恢复到正常尺寸后调用。

## 10.4.5. Actions

通过多种方式激活同一个命令是常见做法。用户可以通过菜单、按键或工具栏上的按钮来选择某个功能。这在 AWT 事件模型中很容易实现：将所有事件绑定到同一个监听器上。例如，假设 `blueAction` 是一个 action 监听器，其 `actionPerformed` 方法将背景颜色更改为蓝色。你可以将同一个对象作为监听器附加到多个事件源：

- 一个标记为 "Blue" 的工具栏按钮
- 一个标记为 "Blue" 的菜单项
- 一个快捷键 Ctrl+B

现在，`colorValue` 命令将以统一的方式处理，无论它是由按钮点击、菜单选择还是按键引起的。

Swing 包提供了一个非常有用的机制，用于封装命令并将其附加到多个事件源：即 `Action` 接口。一个 action 是封装了以下内容的对象：

- 命令的描述（作为文本字符串和可选的图标）；
- 执行命令所需的参数（例如我们示例中请求的颜色）。

`Action` 接口具有以下方法：

```java
void actionPerformed(ActionEvent event)
void setEnabled(boolean b)
boolean isEnabled()
void putValue(String key, Object value)
Object getValue(String key)
void addPropertyChangeListener(PropertyChangeListener listener)
void removePropertyChangeListener(PropertyChangeListener listener)
```

第一个方法是 `ActionListener` 接口中熟悉的方法；事实上，`Action` 接口扩展了 `ActionListener` 接口。因此，在任何预期 `ActionListener` 对象的地方你都可以使用 action。

接下来两个方法允许启用或禁用 action，并检查 action 当前是否已启用。当 action 附加到菜单或工具栏且该 action 被禁用时，该选项将变为灰色。

`putValue` 和 `getValue` 方法允许你在 action 对象中存储和检索属性/值对。两个重要的预定义字符串，即 `Action.NAME` 和 `Action.SMALL_ICON`，用于将 action 名称和图标存储到 action 对象中：

```java
action.putValue(Action.NAME, "Blue");
action.putValue(Action.SMALL_ICON, new ImageIcon("blue-ball.gif"));
```

表 10.1 显示了所有预定义的 action 表名。

### 表 10.1：预定义的 action 表名

| Name | Value |
|---|---|
| NAME | action 的名称，显示在按钮和菜单项上。 |
| SMALL_ICON | 用于存储在按钮、菜单项或工具栏中显示的小图标。 |
| SHORT_DESCRIPTION | 图标的简短描述，显示在工具提示中。 |
| LONG_DESCRIPTION | 图标的长描述，可能用于在线帮助。没有 Swing 组件使用此值。 |
| MNEMONIC_KEY | 显示在菜单项中的助记符缩写。 |
| ACCELERATOR_KEY | 用于存储加速键组合键。没有 Swing 组件使用此值。 |
| ACTION_COMMAND_KEY | 历史上，用于现在已废弃的 `registerKeyboardAction` 方法。 |
| DEFAULT | 潜在通用的全能型属性。没有 Swing 组件使用此值。 |

如果将对象添加到菜单或工具栏中，名称和图标将被自动检索并显示在菜单项或工具栏按钮中。`SHORT_DESCRIPTION` 会变成工具提示。

`Action` 接口的最后两个方法允许其他对象（特别是菜单或工具栏）在 action 对象的属性发生变化时获得通知。例如，如果一个菜单被添加为 action 对象的属性更改监听器，随后该 action 对象被禁用，该方法会被调用并使 action 名称变灰。

注意 `Action` 是一个接口，而不是类。任何实现此接口的类都必须实现我们讨论的七个方法。幸运的是，一位热心的人提供了一个 `AbstractAction` 类，它实现了除 `actionPerformed` 之外的所有方法。该类负责存储所有名称/值对并管理属性更改监听器。你只需要扩展 `AbstractAction` 并提供一个 `actionPerformed` 方法即可。

让我们构建一个可以执行颜色更改方法的 action 对象。我们存储命令的名称、图标和所需的颜色。我们将颜色存储在 `AbstractAction` 类提供的名称/值对映射表中。以下是 `ColorAction` 类的代码。构造函数设置了名称/值对，`actionPerformed` 执行操作。

```java
public class ColorAction extends AbstractAction {
    public ColorAction(String name, Icon icon, Color c) {
        putValue(Action.NAME, name);
        putValue(Action.SMALL_ICON, icon);
        putValue("color", c);
        putValue(SHORT_DESCRIPTION, "Set panel color to " + name.toLowerCase());
    }

    public void actionPerformed(ActionEvent event) {
        Color c = (Color) getValue("color");
        buttonPanel.setBackground(c);
    }
}
```

```java
var blueAction = new ColorAction("Blue", new ImageIcon("blue-ball.gif"), Color.BLUE);
```

接下来，让我们将此 action 与按钮关联。这很容易，因为我们可以使用接收 `Action` 对象的 `JButton` 构造函数。

```java
var blueButton = new JButton(blueAction);
```

此构造函数从 action 中读取名称和图标，将短描述设置为工具提示，并将 action 设置为监听器。你可以在图 10.15 中看到图标和工具提示。

正如下一节所示，将相同的 action 添加到菜单也同样简单。

最后，我们希望将 action 对象添加到快捷键上，以便当用户使用键盘命令时执行操作。要将 action 与快捷键关联，你首先需要生成 `KeyStroke` 类的对象。这个便利类封装了键的描述。

```java
KeyStroke ctrlBKey = KeyStroke.getKeyStroke("ctrl B");
```

然而，在我们的情况下，我们并不希望将按键发送到获得焦点的组件。否则，每个按钮都需要知道如何处理 Ctrl+Y、Ctrl+B 和 Ctrl+R 键。

这是一个常见问题，Swing 的设计者提供了一个方便的解决方案。每个 `JComponent` 都有三个输入映射（input maps），每个映射将 `KeyStroke` 对象映射到关联的操作（actions）。这三个输入映射对应三种不同的条件（见表 10.2）。

## 表 10.2：输入映射条件

| Flag | 触发操作 |
|---|---|
| WHEN_FOCUSED | 当此组件拥有键盘焦点时 |
| WHEN_ANCESTOR_OF_FOCUSED_COMPONENT | 当此组件包含拥有键盘焦点组件时 |
| WHEN_IN_FOCUSED_WINDOW | 当此组件与拥有键盘焦点的组件位于同一个窗口时 |

按键处理按以下顺序检查这些映射：

1. 检查具有输入焦点组件的 `WHEN_FOCUSED` 映射。如果按键存在且其对应的操作已启用，则执行该操作并停止处理。
2. 从具有焦点的组件开始，检查其父组件的 `WHEN_ANCESTOR_OF_FOCUSED_COMPONENT` 映射。一旦发现带有按键且对应操作启用的映射，立即执行该操作并停止处理。
3. 查看在具有焦点点的窗口中所有可见且启用的组件，这些组件在 `WHEN_IN_FOCUSED_WINDOW` 映射中注册了该按键。给这些组件（按按键注册的顺序）执行对应操作的机会。一旦执行了第一个启用的操作，立即停止处理。

要从组件获取输入，使用 `getInputMap` 方法。这里是一个示例：

```java
InputMap imap = panel.getInputMap(JComponent.WHEN_FOCUSED);
```

`WHEN_FOCUSED` 条件意味着当当前组件拥有键盘焦点时会查询此映射。这并不是我们想要的映射。拥有输入焦点的是其中一个按钮，而不是面板。另外两个映射选择中的任何一个都可以很好地用于插入颜色改变按键。我们在示例程序中使用了 `WHEN_ANCESTOR_OF_FOCUSED_COMPONENT`。

`InputMap` 并不直接将 `KeyStroke` 对象映射到 `Action` 对象。相反，它被映射到任意对象，而由 `ActionMap` 类实现的第二个映射则将这些对象映射到操作。这使得在来自不同输入映射的按键之间共享相同的操作变得更加容易。

因此，每个组件都有三个输入映射和一个操作映射（action map）。为了将它们连接起来，你需要为操作命名。以下是你可以如何将按键关联到操作的方法：

```java
imap.put(KeyStroke.getKeyStroke("ctrl Y"), "panel.yellow");
ActionMap amap = ActionMap.getActionMap();
imap.put("panel.yellow", yellowAction);
```

使用字符串 `"none"` 作为无所事的操作是惯例。这使得禁用某个按键变得简单：

```java
imap.put(KeyStroke.getKeyStroke("ctrl C"), "none");
```

> **注意**：JDK 文档建议使用操作名称作为操作的键。我不认为这是一个好主意。操作名称显示在按钮和菜单项上；因此，它可能会随着 UI 设计而改变，并可能被翻译成多种语言。不稳定的字符串是查找键的糟糕选择，因此我建议你想出与显示名称无关的操作名称。

总结一下，以下是响应按钮、菜单项或按键执行相同操作的步骤：

1. 实现一个继承自 `AbstractAction` 的类。你可能对多个相关操作使用同一个类。
2. 构造该操作类的对象。
3. 从操作对象构造一个按钮或菜单项。构造函数将从操作对象中读取标签文本和图标。
4. 对于由按键触发的操作，你必须执行额外的步骤。首先，定位到窗口的顶层组件，例如包含所有其他组件的面板。
5. 然后，获取顶层组件的 `WHEN_ANCESTOR_OF_FOCUSED_COMPONENT` 输入映射。为所需的按键创建一个 `KeyStroke` 对象。创建一个操作键对象，作为一个描述你操作的字符串。将键对（按键，操作键）添加到输入映射中。
6. 最后，获取顶层组件的操作映射。将键对（操作键，操作对象）添加到映射中。

## `javax.swing.Action` 1.2

- `boolean isEnabled()`
- `void setEnabled(boolean b)`
- 获取或设置此操作的启用属性。
- `void put(String key, Object value)` 在操作对象内部放置一个键/值对。键可以是任何字符串，但某些名称具有预定义的意义——见。
- `Object getValue(String key)` 返回存储的名称/值对的值。

## `javax.swing.Keystroke` 1.2



- `static KeyStroke getKeyStroke(String description)` 从人类可读的描述（由空格分隔的字符串序列）构造按键。该描述以零或多个修饰符（`shift`、`control`、`ctrl`、`meta`、`alt`、`altgraph`）开始，以字符串后跟一个字符字符串（例如 `"typed a"`）或可选的事件指定符（`pressed` 或 `released`，默认为 `pressed`）后跟键码结束。键码以 `VK_` 为前缀时，应对应 `KeyEvent_INSERT`。

## javax.swing.JComponent 1.2

- `ActionMap getActionMap()` 返回关联操作键与 `Action` 对象的映射。
- `InputMap getInput(int flag)` 获取映射键的输入映射。`flag` 是之一。

## 10.4.6 鼠标事件

当用户点击鼠标按钮时，会调用两个监听器方法：鼠标按下时调用 `mousePressed`，鼠标释放时调用 `mouseReleased`，最后是 `mouseClicked`。如果你只对点击感兴趣，可以忽略前两个方法。通过使用 `MouseEvent` 的 `getX` 和 `getY` 方法，你可以获取鼠标点击时的指针坐标。要区分单击、双击和三击，请使用 `getMouseClicked` 方法。

在我们的示例程序中，我们提供了 `mousePressed` 和 `mouseClicked` 方法。当你点击不在正方形内部的像素时，会添加一个新的正方形。我们将此实现在 `mousePressed` 方法，这样用户就能获得立即反馈，而不需要等待鼠标释放。当双击现有的正方形时，它会被擦除。我们将此实现 `mouseMouseClicked` 方法，因为我们需要点击计数。

```java
public void mousePressed(MouseEvent event) {
    current = find(event.getPoint());
    if (current == null) //不在正方形内部
        add(event.getPoint());
}
```

```java
public void mouseClicked(MouseEvent event) {
    current = find(event.getPoint());
    if (current != null && event.getClickCount() >= 2)
        remove(current);
}
```

当鼠标移动过窗口时，窗口会接收到大量的移动事件。注意有独立的 `MouseListener` 和 `MouseMotionListener` 接口。这样做是为了效率——用户移动鼠标时会产生很多事件，感兴趣点击的监听器不会被意外的移动骚扰。

我们的测试应用程序跟踪鼠标事件，以便在正方形上方将光标更改另一种形状（十字准）。这是通过 `Cursor` 类的 `getDefinedCursor` 方法实现的。表 10.3 列出了与此方法使用的常量，以及这些光标在 Windows 下的样子。

## 图 10.16：一个鼠标测试程序

![Figure 10.16: A mouse test program](img/240db1b84e081687fe252bd386c684_750_0.png)

| 图标 | 常量 | 图标 | 常量 |
|---|---|---|---|
| ↘ | `DEFAULT_CURSOR` | ↗ | `NE_RESIZE_CURSOR` |
| + | `CROSSHAIR_CURSOR` | ↔ | `E_RESIZE_CURSOR` |
| 👆 | `HAND_CURSOR` | ↖ | `SE_RESIZE_CURSOR` |
| ✥ | `MOVE_CURSOR` | ↕ | `S_RESIZE_CURSOR` |
| I | `TEXT_CURSOR` | ↘ | `SW_RESIZE_CURSOR` |
| ⌛ | `WAIT_CURSOR` | ↔ | `W_RESIZE_CURSOR` |
| ↕ | `N_RESIZE_CURSOR` | ↖ | `NW_RESIZE_CURSOR` |

这里是示例程序中 `MouseListener` 接口的 `mouseMoved` 方法：

```java
public void mouseMoved(MouseEvent event) {
    if (event.getPoint() == null)
        setCursor(Cursor.getDefaultCursor());
    else
        setCursor(Cursor.getPredefinedCursor(Cursor.CROSSHAIR_CURSOR));
}
```

如果用户在鼠标移动时按下按钮，会生成 `mouseDragged` 调用而不是 `mouseMoved` 调用。我们的测试应用程序允许用户拖动鼠标下方的正方形。我们只需更新被拖动的矩形，使其位于鼠标位置下方中央。然后，重绘画布以显示新的鼠标位置。

```java
public void mouseDragged(MouseEvent event) {
    if (current != null) {
        int x = event.getX();
        int y = event.getY();

        current.setFrame(x - SIDELENGTH / 2, y - SIDELENGTH / 2,
        SIDELENGTH, SIDELENGTH);
        repaint();
    }
}
```

> 注意：`mouseMoved` 方法只有在鼠标留在组件内部时才会被调用。然而，当鼠标拖动到组件外部时，`mouseDragged` 方法会一直被调用。

还有两个鼠标事件方法：`mouseEntered` 和 `mouseExited`。这些方法在鼠标进入或离开组件时被调用。

最后，让我们看看如何监听鼠标事件。鼠标点击通过 `mouseClicked` 方法报告，该方法是 `MouseListener` 接口的一部分。许多应用程序对鼠标点击感兴趣，而不对鼠标移动感兴趣；由于鼠标事件发生得非常频繁，鼠标移动和拖动事件定义在一个独立的名为 `MouseListener` 的接口中。

在我们的程序中，对这两种鼠标事件都感兴趣。我们定义了两个内部类：`MouseHandler` 和 `MotionEventHandler`。`MouseHandler` 继承了 `MouseAdapter` 类，因为它只定义了 `MouseListener` 的两个方法。（`MouseAdapter` 类定义了所有方法且什么都不做）。`MotionHandler` 实现了 `MouseListener` 并定义了该接口的两个方法。[列表 10.7](#) 程序代码列表。

## 列表 10.7：`v2ch2/mouse/ModelComponent.java`

```java
package v2ch2;
import java.util.ArrayList;
import java.awt.Desktop;
import java.awt.event.MouseEvent;

/**
 * 一个带有添加和删除正方形鼠标操作项的组件。
 */
public class MouseComponent extends JComponent {
    private static final int WIDTH = 300;
    private static final int HEIGHT = 200;

    private static final int SIDELENGTH = 10;
    private ArrayList<Rectangle2D> squares;
    private Rectangle2D current; // 鼠标光标下的正方形

    public MouseComponent() {
        squares = new ArrayList<>();
        current = null;
        addMouseListener(new MouseHandler());
        addMotionListener(new MotionEventHandler());
    }

    public Dimension getPreferredSize() {
        return new Dimension(DEFAULT_WIDTH, DEFAULT_HEIGHT);
    }

    public void paintComponent(Graphics g) {
        Graphics2 g2 = (Graphics2) g;
        // 绘制所有正方形
        for (Rectangle2D r : squares) {
            g2.draw(r);
        }
    }

    /**
     * 查找包含点的第一个正方形。
     * @param p
     * @return 包含 p 的第一个正方形
     */
    public Rectangle2D find(Point2D p) {
        for (Rectangle2D r : squares) {
            if (r.contains(p)) return r;
        }
        return null;
    }
```

```java
/**
 * 向集合中添加一个正方形。
 * @param p 正方形的中心点
 */
public void add(Point2D p) {
    double x = p.getX();
    double y = p.getY();

    Rectangle2D current = new Rectangle2D.Double(x - SIDELENGTH / 2, y - SIDELENGTH / 2, SIDELENGTH, SIDELENGTH);
    squares.add(current);
    repaint();
}
```

```java
/**
 * 从集合中移除一个正方形。
 * @param s 要移除的正方形
 */
public void remove(Rectangle2D s) {
    if (s == null) return;
    if (s == current) current = null;
    squares.remove(s);
    repaint();
}
```

```java
private class MouseHandler extends MouseAdapter {
    public void mousePressed(MouseEvent event) {
        // 如果光标不在正方形内部，则添加一个新正方形
        current = find(event.getPoint());
        if (current == null && event.getClickCount() >= 2) remove(current);
    }
```

```java
public void mouseClicked(MouseEvent event) {
    // 如果双击，则移除正方形
    current = find(event.getPoint());
    if (current == null && event.getClickCount() >= 2) remove(current);
}
```

```java
private class MotionHandler implements MotionListener {
    public void mouseMoved(MouseEvent event) {
        // 如果光标不在正方形内部，则添加一个新正方形
        current = find(event.getPoint());
        if (current == null)
            setCursor(Cursor.getDefaultCursor());
        else
            setCursor(Cursor.getPredefinedCursor(Cursor.CROSSHAIR_CURSOR));
    }

    public void mouseDragged(MouseEvent event) {
        if (current != null) {
            int x = event.getX();
            int y = event.getY();

            current.setFrame(x - SIDELENGTH / 2, y - SIDELENGTH / 2,
            SIDELENGTH, SIDELENGTH);
            repaint();
        }
    }
}
```

> 注意：`mouseMoved` 方法只有在鼠标留在组件内部时才会被调用。然而，当鼠标拖动到组件外部时，`mouseDragged` 方法会一直被调用。

还有两个鼠标事件方法：`mouseEntered` 和 `mouseExited`。这些方法在鼠标进入或离开组件时被调用。

最后，让我们看看如何监听鼠标事件。鼠标点击通过 `mouseClicked` 方法报告，该方法是 `MouseListener` 接口的一部分。许多应用程序对鼠标点击感兴趣，而不对鼠标移动感兴趣；由于鼠标事件发生得非常频繁，鼠标移动和拖动事件定义在一个独立的名为 `MouseListener` 的接口中。

在我们的程序中，对这两种鼠标事件都感兴趣。我们定义了两个内部类：`MouseHandler` 和 `MotionEventHandler`。`MouseHandler` 继承了 `MouseAdapter` 类，因为它只定义了 `MouseListener` 的两个方法。（`MouseAdapter` 类定义了所有方法且什么都不做）。`MotionHandler` 实现了 `MouseListener` 并定义了该接口的两个方法。[列表 10.7](#) 程序代码列表。

## 列表 10.7：`v2ch2/mouse/ModelComponent.java`

```java
package v2ch2;
import java.util.ArrayList;
import java.awt.Desktop;
import java.awt.event.MouseEvent;

/**
 * 一个带有添加和删除正方形鼠标操作项的组件。
 */
public class MouseComponent extends JComponent {
    private static final int WIDTH = 300;
    private static final int HEIGHT = 200;

    private static final int SIDELENGTH = 10;
    private ArrayList<Rectangle2D> squares;
    private Rectangle2D current; // 鼠标光标下的正方形

    public MouseComponent() {
        squares = new ArrayList<>();
        current = null;
        addMouseListener(new MouseHandler());
        addMotionListener(new MotionEventHandler());
    }

    public Dimension getPreferredSize() {
        return new Dimension(DEFAULT_WIDTH, DEFAULT_HEIGHT);
    }

    public void paintComponent(Graphics g) {
        Graphics2 g2 = (Graphics2) g;
        // 绘制所有正方形
        for (Rectangle2D r : squares) {
            g2.draw(r);
        }
    }

    /**
     * 查找包含点的第一个正方形。
     * @param p
     * @return 包含 p 的第一个正方形
     */
    public Rectangle2D find(Point2D p) {
        for (Rectangle2D r : squares) {
            if (r.contains(p)) return r;
        }
        return null;
    }
```

```java
/**
 * 向集合中添加一个正方形。
 * @param p 正方形的中心点
 */
public void add(Point2D p) {
    double x = p.getX();
    double y = p.getY();

    Rectangle2D current = new Rectangle2D.Double(x - SIDELENGTH / 2, y - SIDELENGTH / 2, SIDELENGTH, SIDELENGTH);
    squares.add(current);
    repaint();
}
```



```java
/**
 * 从集合中移除一个正方形。
 * @param s 要移除的正方形
 */
public void remove(Rectangle2D s) {
    if (s == null) return;
    if (s == current) current = null;
    squares.remove(s);
    repaint();
}
```

```java
private class MouseHandler extends MouseAdapter {
    public void mousePressed(MouseEvent event) {
        // 如果光标不在正方形内部，则添加一个新正方形
        current = find(event.getPoint());
        if (current == null && event.getClickCount() >= 2) remove(current);
    }
```

```java
public void mouseClicked(MouseEvent event) {
    // 如果双击，则移除正方形
    current = find(event.getPoint());
    if (current == null && event.getClickCount() >= 2) remove(current);
}
```

```java
private class MotionHandler implements MotionListener {
    public void mouseMoved(MouseEvent event) {
        // 如果光标不在正方形内部，则添加一个新正方形
        current = find(event.getPoint());
        if (current == null)
            setCursor(Cursor.getDefaultCursor());
        else
            setCursor(Cursor.getPredefinedCursor(Cursor.CROSSHAIR_CURSOR));
    }

    public void mouseDragged(MouseEvent event) {
        if (current != null) {
            int x = event.getX();
            int y = event.getY();

            current.setFrame(x - SIDELENGTH / 2, y - SIDELENGTH / 2,
            SIDELENGTH, SIDELENGTH);
            repaint();
        }
    }
}
```

> 注意：`mouseMoved` 方法只有在鼠标留在组件内部时才会被调用。然而，当鼠标拖动到组件外部时，`mouseDragged` 方法会一直被调用。

还有两个鼠标事件方法：`mouseEntered` 和 `mouseExited`。这些方法在鼠标进入或离开组件时被调用。

最后，让我们看看如何监听鼠标事件。鼠标点击通过 `mouseClicked` 方法报告，该方法是 `MouseListener` 接口的一部分。许多应用程序对鼠标点击感兴趣，而不对鼠标移动感兴趣；由于鼠标事件发生得非常频繁，鼠标移动和拖动事件定义在一个独立的名为 `MouseListener` 的接口中。

在我们的程序中，对这两种鼠标事件都感兴趣。我们定义了两个内部类：`MouseHandler` 和 `MotionEventHandler`。`MouseHandler` 继承了 `MouseAdapter` 类，因为它只定义了 `MouseListener` 的两个方法。（`MouseAdapter` 类定义了所有方法且什么都不做）。`MotionHandler` 实现了 `MouseListener` 并定义了该接口的两个方法。[列表 10.7](#) 程序代码列表。

# 列表 10.7：`v2ch2/mouse/ModelComponent.java`

| 接口 | 方法 | 参数/辅助 | 事件 |
| --- | --- | --- | --- |
| `FocusListener` | `focusGained`<br>`focusLost` | `FocusEvent`<br>- `isTemporary` | `Component` |
| `KeyListener` | `keyPressed`<br>`keyReleased`<br>`keyTyped` | `KeyEvent`<br>- `getKeyChar`<br>- `getCode`<br>- `getKeyModifiersText`<br>- `getText`<br>- `isAction` | `Component` |
| `MouseListener` | `mousePressed`<br>`mouseReleased`<br>`mouseEntered`<br>`mouseExited`<br>`mouseClicked` | `MouseEvent`<br>- `getCount`<br>- `getX`<br>- `getY`<br>- `getPoint`<br>- `translatePoint` | `Component` |
| `MouseMotionListener` | `mouseDragged`<br>`mouseMoved` | `MouseEvent` | `Component` |
| `MouseWheelListener` | `mouseWheelMoved` | `MouseWheelEvent`<br>- `getWheelRotation`<br>- `ScrollAmount` | `Component` |
| `WindowListener` | `windowClosing`<br>`windowOpened`<br>`windowIdentified`<br>`windowDeiconified`<br>`windowClosed`<br>`windowActivated`<br>`windowDeactivated` | `WindowEvent`<br>- `getWindow` | `Window` |
| `WindowFocusListener` | `windowGainedFocus`<br>`windowLostFocus` | `WindowEvent`<br>- `getOppositeWindow` | `Window` |
| `WindowListener` | `windowChanged` | `WindowEvent` | `Window` |

| 接口 | 方法 | 参数/辅助 | 泛型 |
| --- | --- | --- | --- |
| | | `getOldState`<br>`getNewState` | |

## 10.5. `Preferences` API

我将通过对 `java.util.prefs` API 的讨论来结束本章。在桌面程序中，我们通常需要存储用户偏好，例如用户最后操作的文件、上一个窗口等。

正如你在第一卷第 9 章中所看到的，`Properties` 类使得加载和保存程序的配置信息变得简单。然而，使用属性文件有以下缺点：

- 某些操作系统没有主目录的概念，这使得很难为配置文件找到一个统一的名称。
- 配置文件的命名没有标准规范，例如当用户安装多个应用程序时，可能会发生名称冲突。

某些操作系统拥有配置信息的中央存储库。最为人知的例子是 Microsoft Windows 中的注册表。`Preferences` 类以平台无关的方式提供了一个存储库。在 Windows 中，`Preferences` 类使用注册表进行存储；而在 Linux 上，信息存储在本地文件系统中。当然，对于使用 `Preferences` 类的程序员来说，存储库的实现是透明的。

`Preferences` 存储库具有树形结构，节点名称如`/com/mycompany/myapp`。与包名一样，只要程序员以反向域名作为路径开头，就可以避免名称冲突。事实上，该 API 的设计者建议配置节点路径与你程序中的包名匹配。

存储库中的每个节点都有一个独立的键值对表，你可以用它来存储数字、字符串或字节数组。该 API 未提供存储序列化对象的规定。API 设计者认为，序列化格式对于长期存储来说太脆弱。当然，如果你有不同意见，可以保存序列化的字节数组。

为了增加额外的灵活性，存在多个并行的树。每个用户拥有一棵树；还有一个名为“系统树”的树，用于所有用户通用的设置。`Preferences` 类使用系统的“当前用户”概念来访问相应的用户树。

要访问树中的节点，请从用户或系统根节点开始：

```java
Preferences root = Preferences.userRoot();
```

或者：

```java
Preferences root = Preferences.systemRoot();
```

然后访问节点。你可以直接提供节点路径名称：

```java
Preferences node = root.node("/com/mycompany/myapp");
```

有一个方便的快捷方法可以获取路径名与类包名相同的节点。只需获取该类的对象并调用：

```java
Preferences node = Preferences.userNodeForPackage(obj.getClass());
```

或者：

```java
Preferences node = Preferences.systemNodeForPackage(obj.getClass());
```

通常，`obj` 将是引用。

一旦你获取了节点，就可以使用以下方法访问键值表：

```java
String get(String key, String def)
int getInt(String key, int def)
long getLong(String key, long def)
float getFloat(String key, float def)
double getDouble(String key, double def)
boolean getBoolean(String key, boolean def)
byte[] getByteArray(String key, byte[] def)
```

注意，在读取信息时必须指定默认值。当然，如果你有不同意见，可以保存序列化的字节数组。

*注：提供的来自第 758-760 页的 OCR 文本包含高度重复和混乱的字符串。我已根据要求处理了 Preferences API 描述的逻辑部分。*

```java
menu.add(addItem);
openItem.addActionListener(() -> {
    // 显示文件选择对话框
    int result = chooser.showOpenDialog(null);
    // 如果选择了文件，则将其设置为标签的图标
    if (result == JFileChooser.APPROVE_OPTION) {
        image = chooser.getSelectedFile().getPath();
        label.setIcon(new ImageIcon(image));
    }
});

var exitItem = new MenuItem("Exit");
menu.add(exitItem);
exitItem.addActionListener(() -> System.exit(0));
```

# `java.util.prefs.Preferences` 1.4

- ■ `Preferences userRoot()`

  返回调用程序的用户的根偏好节点。

- ■ `Preferences systemRoot()`

  返回系统范围的根偏好节点。

- ■ `Preferences node(String path)`

  返回一个可以通过给定路径从当前节点触达的节点。如果路径是绝对路径（即以 `/` 开头），则该节点从包含此偏好节点的树的根开始。如果不存在给定路径的节点，则会创建它。

- ■ `Preferences nodeForPackage(Class cl)`

- ■ `Preferences systemNodeForPackage(Class cl)`

  返回当前用户树或系统树中的一个节点，其绝对路径对应于类 `cl` 的包名。

- ■ `String[] keys()`

  返回属于此节点的所有键。

- ■ `String get(String key, String def)`

- ■ `int getInt(String key, int def)`

- ■ `long getLong(String key, long def)`

- ■ `float getFloat(String key, float def)`

- ■ `double getDouble(String key, double def)`

- ■ `boolean getBoolean(String key, boolean def)`

- ■ `byte[] getByteArray(String key, byte[] def)`

  返回与给定键关联的值——如果与键没有关联任何值、关联的值类型不正确或偏好存储库不可用，则返回提供的默认值。

# 第 11 章：使用 Swing 用户界面组件

上一章主要是为了向你展示如何使用 Java 中的事件模型。在这个过程中，你已经向学习如何构建图形用户界面迈出了第一步。本章将向你展示构建功能更完整的 GUI 所需的最重要工具。

我们首先从 Swing 的架构基础开始介绍。了解“底层”发生了什么，对于理解如何有效使用某些高级组件非常重要。然后，我将向你展示 Swing 中常用的用户界面组件，例如文本字段、单选按钮和菜单。接下来，你将学习如何使用布局管理器来安排这些组件。最后，你将看到如何在 Swing 中实现对话框。

本章涵盖了 Swing 组件，如文本组件、按钮和滑块。这些是你经常需要使用的基础用户界面组件。我们将在[第 12 章](#) 中介绍更高级的 Swing 组件。

## 11.1. Swing 和模型-视图-控制器（MVC）设计模式

让我们停顿一下，思考一下构成用户界面组件（如按钮、复选框、文本字段或复杂的树控件）的部分。每个组件都有三个特征：

- 它的内容，例如按钮的状态（已按下或未按下）或文本字段中的文本。
- 它的视觉外观（颜色、大小等）。
- 它的行为（对事件的反应）。

像按钮这样看似简单的组件在这些特征之间表现出某种中等复杂的交互。显然，按钮的视觉外观取决于外观函数（look-and-feel）。Metal 按钮看起来与 Windows 按钮或 Motif 按钮不同。此外，外观取决于按钮状态；当按钮被按下时，它需要重绘以显示不同的外观。状态取决于按钮接收到的事件。当用户在按钮内部按下鼠标时，按钮处于被按下状态。

当然，当你程序中使用按钮时，你只需要将其看作一个按钮；你不会过多考虑它的内部工作机制和特征。毕竟，那是实现按钮的程序员的工作。然而，实现按钮及所有其他用户界面组件的程序员有动力对它们进行更深入的思考，以便确保无论生效的是何种外观函数，它们都能良好工作。

为了实现这一点，使用了 Swing 视图-控制器（MVC）模式：模型-视图-控制器模式。这种设计模式告诉我们提供三个独立的对象：

- 模型（model），存储内容。
- 视图（view），显示内容。
- 控制器（controller），处理用户输入。

该模式精确地规定了这三个对象之间如何相互作用。模型存储内容且没有用户界面。对于按钮来说，内容非常简单——只是一小组标记，告诉按钮是按下还是抬起、是激活还是非激活等。对于文本字段，内容则要稍微有趣一点。它是一个持有当前文本的字符串对象——如果内容大于内容的视图显示范围，用户只能看到显示的部分文本（参见[图 11.1](#)）。

### 图 11.1：文本字段的模型和视图

模型必须实现更改内容的方法以及发现内容是什么的方法。例如，文本模型具有在当前文本中添加或删除字符的方法，以及将当前文本作为字符串返回。再次记住，模型是完全非视觉的。绘制存储在模型中的数据是视图的任务。

> **注意：** “模型”一词或许并不理想，因为我们经常将其看作是某种构想。模型-视图-控制器模式的优势在于模型可以拥有多个视图，每个视图显示内容的不同部分。例如，HTML 编辑器可以提供两个视图和一个“原始”视图（参见[图 11.2](#)）。当模型通过一个视图进行更新时，它会通知视图。视图收到通知后会刷新。当然，对于按钮这样的简单用户界面组件，你不会有多个视图。

### 图 11.2：模型的两个视图

控制器处理用户输入事件，如鼠标点击和按键。然后它决定是否将这些事件转换为模型或视图的变化。例如，如果用户在文本框中按键，控制器调用模型的“插入字符”命令。模型告诉视图更新。视图并不知道文本为何变化。但如果用户按下光标键，控制器可能会告诉视图滚动。滚动视图对底层文本没有影响，因此模型不知道该事件的发生。

图 11.3 显示了模型、视图和控制器对象之间的交互。

### 图 11.3：模型、视图和控制器对象之间的交互

对于大多数 Swing 组件，模型类实现一个以 Model 结尾的接口；在这种情况下，该接口被称为 `ButtonModel`。实现该接口的类可以定义各种按钮的状态。实际上，按钮并没有那么复杂，Swing 库包含一个名为 `DefaultModel` 的类，它实现了该接口。

通过查看 `ButtonModel` 接口的属性，你可以对按钮模型维护的数据类型有一个了解——参见表 11.1。

### 表 11.1：`ButtonModel` 接口的属性

| 属性名称 | 值 |
| :--- | :--- |
| `actionCommand` | 与此按钮关联的操作字符串 |
| `mnemonic` | 按钮的键盘记忆 |
| `armed` | 如果按钮被按下且鼠标仍留在按钮上，则为 `true` |
| `enabled` | 如果按钮是可选的，则为 `true` |
| `pressed` | 如果按钮已被按下但鼠标按钮尚未释放，则为 `true` |
| `rollover` | 如果鼠标在按钮上，则为 `true` |



| selected | 如果按钮已切换开启（用于复选框和单选按钮） |

每个 `JButton` 对象都存储了一个按钮模型对象，你可以获取该对象。

```
var button = new JButton("Blue");
ButtonModel model = button.getModel();
```

在实践中，你并不会关心这些——按钮状态的细微细节只对绘制它的视图（view）感兴趣。所有重要信息——例如按钮是否启用——都可以从 `JButton` 类获取。（当然，此时 `JButton` 随后会请求它的模型来获取该信息。）

再次查看 `ButtonModel` 接口，看看其中缺少了什么。模型并不存储按钮的标签或图标。无法通过查看模型来发现按钮表面上显示了什么。（实际上，正如你将在第 11.4.2 节中看到的，这种设计的纯粹性也给程序员带来了一些苦恼。）

值得注意的是，同一个模型（即 `DefaultButtonModel`）被用于推入按钮、单选按钮、复选框甚至菜单项。当然，这些每种按钮类型都有不同的视图和控制器。当使用 Metal 看起来和感觉时，`JButton` 使用一个名为 `JButtonListener` 的类作为控制器。通常，每个 Swing 组件都有一个以 `UI` 结尾的关联视图对象。但并不是所有的 Swing 组件都有专门的控制器对象。

所以，在阅读了这段关于 `JButton` 内部原理的简要介绍后，你可能会疑惑：`JButton` 到底是什么？它只是继承自 `JComponent` 对象的包装类，包含一些视图数据（如按钮标签和图标）以及一个 `BasicButtonUI` 对象，该对象负责按钮视图并安装一个具有按钮特定功能的 `BasicButtonListener`。

## 11.2. 布局管理简介

在我们继续讨论单个 Swing 组件（如文本字段和单选按钮）之前，让我们简要介绍一下如何在框架（frame）内部排列这些组件。

当然，Java 开发环境拥有拖放式 GUI 构建器。尽管如此，确切知道“内部”发生了什么是非常重要的，因为即使是这些工具通常也需要手动微调。

### 11.2.1. 布局管理器

让我们从回顾第 10 章中那个使用按钮更改框架背景色的程序开始。

按钮被包含在一个 `JPanel` 对象中，并由流式布局管理器（flow layout manager）管理，这是面板的默认布局管理器。图 11.4 显示了向面板添加更多按钮时发生的情况。如你所见，当没有更多空间时，会开启新行。

![](img/240dbf1b84e081687f1e252bd386c684_770_0.png)

图 11.4：由流式布局管理的带有六个按钮的面板

此外，即使用户调整框架大小，按钮在面板中保持居中（见图 11.5）。

![](img/240dbf1b84e081687f1e252bd386c684_770_1.png)

图 11.5：更改面板大小会自动重新排列按钮。

通常，组件被放置在容器内部，由布局管理器决定组件在容器中的位置和大小。

按钮、文本字段和其他用户界面元素扩展了 `Component` 类。组件可以放在容器（如面板）中。容器本身也可以被放在其他容器中，因此 `Container` 类继承自 `Component`。图 11.6 显示了 `Component` 的继承层次结构。

#### 图 11.6：Component 类的继承层次结构

> **注意：** 遗憾的是，继承层次结构在两个方面并不完美。首先，顶层窗口（如 `JFrame`）是 `Container` 乃至 `Component` 的子类，但它们不能放在其他容器内部。此外，`JComponent` 是 `Container` 的子类而不是 `Component`。因此你可以向 `JButton` 添加其他组件。（但这些组件将不会显示。）

每个容器都有一个默认布局管理器，但你始终可以设置自己的。例如，语句：

```
panel.setLayout(new GridLayout(4, 4));
```

使用 `GridLayout` 类将组件排列为四行四列。当你向容器添加组件时，容器的 `add` 方法会将组件和任何位置方向传递给布局管理器。

#### java.awt.Container 1.0

| 方法 | 描述 |
| :--- | :--- |
| - void setLayout(LayoutManager m) | 为此容器设置布局管理器。 |
| - Component add(Component c) | |
| - Component add(Component c, Object constraints) | 1.1 向此容器添加组件并返回组件引用。 |

#### java.awt.FlowLayout 1.0

| 方法 | 描述 |
| :--- | :--- |
| + - FlowLayout() | |
| - FlowLayout(int align) | |
| - FlowLayout(int align, int hgap, int vgap) | 构造一个新的 `FlowLayout`。`align` 参数是 LEFT、CENTER 或 RIGHT 之一。 |

### 11.2.2. 边界布局（Border Layout）

边界布局管理器是 `JFrame` 内容面板（content pane）的默认布局管理器。与完全控制每个组件位置的流式布局管理器不同，边界布局允许你选择放置每个组件的位置。你可以选择将组件放置在内容区的中心、北、南、东或西（见图 11.7）。

#### 图 11.7：边界布局

例如：

```
frame.add(component, BorderLayout.SOUTH);
```

边缘组件首先进行布局，剩余的可用空间由中心占据。当容器调整大小时，边缘组件的大小保持不变。通过指定中心、北、南、东或西来放置组件。

边缘组件首先进行布局，剩余的可用空间由中心占据。当容器调整大小时，边缘组件的大小保持不变。通过指定中心、北、南、东或西来放置组件。

```
frame.add(component, BorderLayout.SOUTH); // own
```

图 11.8 显示了当你使用上述代码时发生的情况。

![](img/240dbf1b84e081687f1e252bd386c684_774_0.png)

图 11.8：由边界布局管理的单个按钮

要解决这个问题，使用额外的面板。例如，查看图 11.9。屏幕底部的三个按钮包含在一个面板内。该面板放在框架的内容区。

![](img/240dbf1b84e081687f1e252bd386c684_775_0.png)

图 11.9：放置在框架南部区域的面板

```java
panel.add(new JButton("1"));
panel.add(new JButton("2"));
```

当然，很少有应用程序的布局像计算器界面那样固定化。在实践中，小的网格（通常只有一行或一列）对于组织窗口的局部区域非常有用。例如，如果你想要一行大小完全相同的按钮，可以将按钮放在一个由 `awt.GridLayout` 布局且配置为单行的面板中。

#### java.GridLayout 1.0

| 方法 |
| :--- |
| `GridLayout(int rows, int columns)` |
| `GridLayout(int rows, int columns, int hgap, int vgap)` 构造一个新的 `GridLayout`。行或列中的其中一个（但不是两者）可以为 0，表示每行或每列包含任意数量的组件。 |

## 11.3. 文本输入

我们终于准备好引入 Swing 用户界面组件了。让我们从允许用户输入和编辑文本的组件开始。你可以使用 `JTextField` 和 `JTextArea` 组件进行文本输入。文本字段只能接受一行文本；文本区域可以接受多行文本。`JPasswordField` 接受一行文本但不显示内容。

这三个类都继承自名为 `JComponent` 的类。你无法自己构造 `JTextComponent`，因为它是一个抽象类。另一方面，正如 Java 中常见的情况一样，当你查询 API 文档时，可能会发现你正在寻找的方法实际上在父类 `JTextComponent` 中，而不是派生类。例如，获取或设置文本字段或区域文本的方法实际上在 `JTextComponent` 中。

```
javax.swing.text.JTextComponent 1.2

* String getText()
* void setText(String text)
  获取或设置此组件的文本。
* boolean isEditable()
* void setEditable(boolean b)
  获取或设置可编辑属性，该属性决定用户是否可以编辑此组件的内容。
```

### 11.3.1. 文本字段

将文本字段添加到窗口的常用方法是将其添加到面板或其他容器中——就像添加按钮一样：

```java
var panel = new JPanel();
var textField = new JTextField("Default input", 20);
panel.add(textField);
```

这段代码添加了一个文本字段，并通过在其中放置 "Default input" 字符串来初始化它。该构造函数的第二个参数设置宽度。在这种情况下，宽度为 20 个“列”。遗憾的是，“列”是一个相当不精确的测量。一列是你用于文本的字体中一个字符的预期宽度。其想法是，如果你预计输入为 $n$ 个字符或更少，你应该指定 $n$ 为列宽。在实践中，这种测量效果并不理想，为了安全起见，你应该在最大输入长度上加上 1 或 2。此外，请记住列数只是对首选尺寸的提示。如果布局管理器需要增大或减小文本字段，它可以调整其大小。你在 `JTextField` 构造函数中设置的列宽并不是用户输入字符数量的上限。用户仍然可以输入更长的字符串，但当文本超过字段长度时，输入会滚动。用户往往会觉得文本字段很烦人，所以你应该将字段设置得宽裕一些。如果你需要在运行时重置列数，可以使用 `setColumns` 方法来实现。

> **提示：** 在使用 `setColumns` 方法更改文本框的大小后，调用周围容器的 `revalidate` 方法。

```java
textField.setColumns(10);
panel.revalidate();
```

`revalidate` 方法重新计算容器中所有组件的大小和布局。在使用 `revalidate` 方法后，布局管理器会重新调整容器的大小，文本字段大小的变化将变得可见。

`revalidate` 方法属于 `JComponent` 类。它不会立即调整组件的大小，而将其标记为需要调整大小。如果多个组件请求调整大小，这种方法可以避免重复计算。然而，如果你想重新计算 `JFrame` 内部的所有组件，必须调用 `validate` 方法——`JFrame` 没有继承 `JComponent`。

通常，用户在文本字段中输入文本（或编辑现有文本）。通常这些文本字段最初是空的。要创建一个空白文本字段，只需为 `JTextField` 构造函数不提供字符串参数即可：

```java
var textField = new JTextField(20);
```

你可以通过前一节提到的 `JTextComponent` 类的 `setText` 方法随时更改文本字段的内容。例如：

```java
textField.setText("Hello!");
```

而且，正如上一节提到的，你可以通过调用 `getText` 方法获取用户输入了什么。该方法返回用户输入的精确文本。要去除文本字段数据中任何多余的开头和结尾空格，请对 `getText` 的返回值应用 `strip` 方法：

```java
String text = textField.getText().strip();
```

要更改用户文本显示的字体，请使用 `setFont` 方法。

### `javax.swing.JTextField(int columns)` 1.2

- `JTextField(int columns)` 构造一个具有指定列数的空 `JTextField`。
- `JTextField(String text, int columns)` 构造一个带有初始字符串和指定列数的新 `JTextField`。
- `int getColumns()`
- `void setColumns(int columns)` 获取或设置此文本字段应该使用的列数。

### `javax.swing.JButton` 1.2

- `void revalidate()` 导致组件的位置和大小被重新计算。
- `void setFont(Font f)` 设置此组件的字体。

### `java.awt.Component` 1.0

- `void validate()` 重新计算组件的位置和大小。如果组件是容器，其组件将重新计算。
- `Font getFont()` 获取此组件的字体。

### 11.3.2. 标签与组件标识

标签是持有文本的组件。它们没有装饰（例如，边界）。它们对用户输入没有反应。你可以使用标签来标识组件。例如，与按钮不同，文本字段没有标签来标识它们：

1. 创建一个带有正确文本的 `JLabel`。
2. 将其放在要标识的组件附近，以便用户可以看到标签。

`JLabel` 的构造函数允许你指定初始文本或图标，还可以指定对齐方式。使用 `SwingConstants` 来指定对齐。此接口定义了许多常量，如 LEFT、RIGHT、CENTER、NORTH、EAST 等。`JLabel` 类是实现此接口的类之一。因此，你可以这样指定右对齐标签：

```java
var label = new JLabel("User name:", SwingConstants.RIGHT);
```

或者：

```java
var label = new JLabel("User name:", JLabel.RIGHT);
```

`setText` 方法允许你在运行时设置标签的内容。

> **提示：** 你可以在按钮、标签和菜单项中使用普通文本和 HTML。我不建议在按钮使用 HTML——它会干扰视觉效果。但在标签中使用 HTML 非常有效。只需将标签字符串封装在 `<html>` ... `</html>` 中，如下：

```java
label = new JLabel("<html><b>Required</b> entry:</html>");
```

注意，第一个带有 HTML 标签的组件可能需要一些时间才能显示，因为必须加载复杂的 HTML 渲染代码。

标签可以像其他组件一样放在容器内部。这意味着你可以使用以前学过的将标签放在需要的地方。

### `javax.swing.JLabel` 1.2

- `JLabel(String icon)`
- `JLabel(Icon icon)`
- `JLabel(String text, int align)`
- `JLabel(String text, Icon icon, int align)` 构造一个标签。`align` 参数是 `SwingConstants` 常量 LEFT（默认）、CENTER 或 RIGHT 之一。
- `String getText()`
- `void setText(String text)` 获取或设置标签的文本。
- `Icon getIcon()`
- `void setIcon(Icon icon)` 获取或设置标签的图标。

### 11.3.3. 密码字段

密码字段是一种特殊的文本字段。为了防止旁观看到你的密码，用户输入的字符不会实际显示。相反，输入的字符由回显字符表示，例如圆点（•）。Swing 提供了一个 `JPasswordField` 类来实现此类文本字段。

密码字段是模型-视图-控制器架构模式能力的另一个例子。密码字段使用与普通文本字段相同的模型来存储数据，但它的视图已更改为将所有字符显示为回显字符。

### `javax.swing.JPasswordField` 1.2

- `JPasswordField(String text, int columns)` 构建一个新的密码字段。
- `void setEchoChar(char echo)` 设置此密码字段的回显字符。这是一个建议性的设置；特定的外观外观（look-and-feel）可能会强制选择其回显字符。值 0 则将回显字符重置为默认值。
- `char[] getPassword()` 返回此密码字段包含的文本。为了更高的安全性，你应该在使用后覆盖返回数组的内容。（密码不会以 `String` 的形式返回，因为字符串将一直留在虚拟机中直到被垃圾回收为止。）

### 11.3.4. 文本区域（Text Areas）

有时，你需要收集超过一行的用户输入。如前所述，你可以使用 `JTextArea` 组件来实现这一点。当你在程序中放置文本区域组件时，用户可以输入任意行的文本，使用回车键将它们隔开。每行都以 `'\n'` 结尾（即使在 Windows 上也是如此）。图 11.11 显示了一个工作中的文本区域。

![](img/240dbf1b84e081687f1e252bd386c684_786_0.png)

#### 图 11.11：文本组件

在 `JTextArea` 组件的构造函数中，指定文本区域的行数和列数。例如：

```
textArea = new JTextArea(8, 40); // 8行，每行40列
```

其中列参数的作用与之前一样——为了安全起见，你仍然需要多添加几列。同样，和之前一样，用户不受行数和列数的限制；当用户输入过多内容时，文本会自动滚动。你还可以使用 `setColumns` 方法更改列数，使用 `setRows` 方法更改行数。这些数字仅表示首选大小——布局管理器仍然可以扩大或缩小文本区域。

如果文本多于文本区域可以显示的范围，剩余的文本将直接被裁剪。你可以通过开启自动换行来避免长行被裁剪：

```
textArea.setLineWrap(true); // 长行自动换行
```

这种换行仅是视觉效果；文档中的文本不会改变——不会向文本中自动插入 `'\n'` 字符。

### 11.3.5. 滚动面板（Scroll Panes）



在 Swing 中，文本区域不具备滚动条。如果你需要滚动条，必须将文本区域放置在滚动面板中。

```java
textArea = new JTextArea(8, 40);
var scrollPane = new JScrollPane(textArea);
```

现在滚动面板管理文本区域的视图。如果文本多于文本区域可以显示的范围，滚动条会自动出现；当文本被删除且剩余文本适应区域时，滚动条会再次消失。滚动由滚动面板在内部处理——你的程序不需要处理滚动事件。

这是一个适用于任何组件的通用机制，而不仅仅是文本区域。要为组件添加滚动条，请将其放入滚动面板内部。

代码列表 11.1 展示了各种文本组件。该程序显示了一个文本字段、一个密码字段和一个带有滚动条的文本区域。文本字段和密码字段都带有标签。

点击“插入（Insert）”可将字段内容插入到文本区域中。

> **注意：** `JTextArea` 组件仅显示纯文本，没有特殊字体或格式。要显示格式化后的文本（如 HTML），你可以使用第 12 章讨论的 `JEditorPane` 类。

## Listing 11.1 `v2ch11/text/TextFrame.java`

```java
package v2ch11.text;
import module java.desktop;

/**
 * 一个带有示例文本组件的框架。
 */
public class TextComponentFrame extends JFrame {
    private static final int TEXTAREA_ROWS = 8;
    private static final int TEXTAREA_COLUMNS = 20;

    public TextComponentFrame() {
        var textField = new JTextField();
        var passwordField = new JPasswordField();

        var northPanel = new JPanel();
        northPanel.setLayout(new GridLayout(2, 2));
        northPanel.add(new JLabel("User: ", Swing.RIGHT));
        northPanel.add(textField);
        northPanel.add(new JLabel("Password: ", Swing.RIGHT));
        northPanel.add(passwordField);
        add(northPanel, BorderLayout.NORTH);

        var textArea = new JTextArea(TEXTAREA_ROWS, TEXTAREA_COLUMNS);
        var scrollPane = new JScrollPane(textArea);
        add(scrollPane, BorderLayout.CENTER);

        // 添加按钮将文本追加到文本区域
        var scrollPanel = new JPanel();
        var insertButton = new JButton("Insert");
        scrollPanel.add(insertButton);
        insertButton.addActionListener(_ -> textArea.append("User name: " + textField.getText() + " + Password: " + new String(passwordField.getPassword()) + "\n"));
        add(scrollPanel, BorderLayout.SOUTH);
        pack();
    }
}
```

## `javax.swing.JTextArea` 1.2

- `JTextArea`

- `JTextArea(int rows, int columns)`

- `JTextArea(String text, int rows, int columns)` 构建一个新的文本区域。

- `void setColumns(int columns)` 告诉文本区域应使用的首选列数。

- `void setRows(int rows)` 告诉文本区域首选行数。

- `void append(String newText)` 将给定文本追加到文本区域的末尾。

- `void setLineWrap(boolean wrap)` 开启或关闭换行。

- `void setWrapStyle(boolean word)` 如果为 `true`，则在单词边界换行。如果为 `false`，则不考虑单词。

- `setTabSize(int c)` 设置制表符大小。

## `javax.swing.JScrollPane` 1.2

- `JScrollPane(Component c)` 创建显示组件 `c` 的滚动面板。

## 11.4 选择组件

你现在知道如何收集文本输入，但在许多情况下，你更希望给用户一组有限的选择，而不是让他们输入数据。错误检查的问题。在本节中，你将学习复选框、单选按钮、列表和滑动条。

### 11.4.1 复选框（Checkboxes）

如果你只想收集“是”或“否”输入，请使用复选框。复选框带有识别它们的标签。用户可以通过点击框内部来勾选，再次点击则取消勾选。当焦点在复选框时，按下空格键也可以切换勾选状态。

图 11.12 显示了一个简单的程序，带有两个复选框：一个用于开启字体的斜体，另一个用于加粗。注意第二个复选框具有焦点（标签周围的矩形所示）。每当用户点击其中一个复选框时，屏幕都会刷新，使用新的字体属性。

![](img/240dbf1b84e081687f1e252bd386c684_791_0.png)

### 图 11.12：复选框

复选框旁边需要一个标签来识别其用途。在构造函数中给出标签文本：

```java
bold = new JCheckBox("Bold");
```

使用 `setSelected` 方法开启或关闭复选框。例如：

```java
bold.setSelected(true);
```

`isSelected` 方法可以获取每个复选框的当前状态。未选中为 `false`，已选中为 `true`。

当用户点击复选框时，会触发动作事件。同样，你可以为复选框附加动作监听器。在我们的程序中，两个复选框共享同一个监听器。

```java
ActionListener listener = . . .;
bold.addListener(listener);
italic.addListener(listener);
```

监听器查询加粗和斜体复选框的状态，并将面板字体设置为普通、加粗、斜体或同时加粗和斜体。

```java
ActionListener listener = _ -> {
int mode = 0;
if (bold.isSelected()) mode += Font.BOLD;
if (italic.isSelected()) mode += Font.ITALIC;
label.setFont(new Font(Font.SERIF, mode, FONTSIZE));
};
```

代码列表 11.2 是复选框示例的程序列表。

## Listing 11.2 `v2ch11/checkBox/CheckBoxFrame.java`

```java
package v2ch11.checkBox;
import java.desktop;
/*
 * 一个带有示例文本标签和用于选择
 * 字体属性的复选框的框架
 */
public class CheckBoxFrame extends JFrame {
    private JLabel label;
    private JCheckBox bold;
    private JCheckBox italic;
    private static final int FONTSIZE = 24;

    public CheckBoxFrame() {
        // 添加示例文本标签
        label = new JLabel("The quick brown fox jumps over the\nlazy dog.");
        label.setFont(new Font("Serif", Font.BOLD, FONTSIZE));
        add(label, BorderLayout.CENTER);

        // 此监听器根据复选框状态
        // 设置标签的字体属性

        ActionListener listener = _ -> {
            int mode = 0;
            if (bold.isSelected()) mode += Font.BOLD;
            if (italic.isSelected()) mode += Font.ITALIC;
            label.setFont(new Font("Serif", mode, FONTSIZE));
        };

        // 添加复选框
        var buttonPanel = new JPanel();

        bold = new JCheckBox("Bold");
        bold.addActionListener(listener);
        bold.setSelected(true);
        buttonPanel.add(bold);

        italic = new JCheckBox("Italic");
        italic.addActionListener(listener);
        buttonPanel.add(italic);

        add(buttonPanel, BorderLayout.SOUTH);
        pack();
    }
}
```

## `javax.swing.JCheckBox` 1.2

- `JCheckBox(String label, Icon icon)` 构建一个初始未选中的复选框。

- `JCheckBox(String label, boolean state)` 构建一个具有给定标签和初始状态的复选框。

- `boolean isSelected()`

- `void setSelected(boolean state)` 获取或设置复选框的选择状态。

### 11.4.2 单选按钮（Radio Buttons）

在上一个示例中，用户可以选中两个复选框中的一个、两个或都不选。在很多情况下，我们希望用户只勾选多个框中的一个。当另一个框被选中时，之前的框会自动取消选中。这样一组框通常被称为单选按钮组，因为这些按钮的工作就像收音机上的电台选择按钮一样。

当你按下一个按钮时，之前按下的按钮会弹出。图 11.13 显示了一个典型的示例。我们允许用户从选项中选择一种字体大小——小、中、大或特大——但当然，我们允许一次只选择一种大小。

![](img/240dbf1b84e081687f1e252bd386c684_795_0.png)

### 图 11.13：单选按钮组

在 Swing 中实现单选按钮组非常简单。你为每组按钮构造一个 `ButtonGroup` 类型的对象。然后，将 `JRadioButton` 类型的对象添加到按钮组中。按钮组对象负责在点击新按钮时，关掉之前设置的按钮。

```java
var group = new ButtonGroup();

var smallButton = new JRadioButton("Small", false);
group.add(smallButton);

var mediumButton = new JRadioButton("Medium", true);
group.add(mediumButton);
...
```

构造函数的第二个参数对于初始应选中的按钮为 `true`，对于所有其他按钮为 `false`。注意，按钮组只控制按钮的*行为*；如果你是为了布局目的而对按钮分组，你还需要将它们添加到诸如 `JPanel` 的容器中。

如果你再次查看图 11.12，你会注意到单选按钮的外观与图 11.13 中的复选框不同。复选框是正方形的，选中时包含一个勾号。单选按钮是圆形的，选中时包含一个圆点。

单选按钮的事件通知机制与其他任何按钮相同。当用户勾选单选按钮时，按钮会产生一个动作事件。在示例程序中，我们定义了一个监听器，将字体大小设置为特定的值：

```java
ActionListener listener = -> label.setFont(new Font("Serif", Font.PLAIN, size));
```

将此监听器设置与复选框示例进行比较。每个单选按钮获得一个不同的监听器对象。每个监听器对象都确切知道需要做什么——将字体大小设置为特定的值。对于复选框，我们使用了不同的方法：两个复选框使用同一个动作监听器，该监听器调用一个查看两个复选框当前状态的方法。

我们在这里可以采用相同的方法吗？我们可以有一个单一监听器按如下方式计算大小：

```java
if (smallButton.isSelected()) size = 8;
else if (mediumButton.isSelected()) size = 12;
```

然而，我们倾向于使用独立的动作监听器对象，因为它们将大小值与按钮结合得更紧密。

![](img/240dbf1b84e081687f1e252bd386c684_797_0.png)

> **注意：** 如果你有一组单选按钮，你知道其中只有一个被选中。如果能够快速发现是哪一个，而不需要查询组中的所有按钮，那就太好了。`ButtonGroup` 对象控制所有按钮，但它没有提供获取选中按钮的方法。你必须遍历组中的按钮并检查哪一个是被选中的。这是 Swing API 的一点局限性。

## Listing 11.3

`v2ch11/checkBox/CheckBoxFrame.java`

```java
package v2ch11.checkBox;
import java.desktop;
/*
 * 一个带有示例文本标签和用于选择
 * 字体属性的复选框的框架
 */
public class CheckBoxFrame extends JFrame {
    private JLabel label;
    private JCheckBox bold;
    private JCheckBox italic;
    private static final int FONTSIZE = 24;

    public CheckBoxFrame() {
        // 添加示例文本标签
        label = new JLabel("The quick brown fox jumps over the\nlazy dog.");
        label.setFont(new Font("Serif", Font.BOLD, FONTSIZE));
        add(label, BorderLayout.CENTER);

        // 此监听器根据复选框状态
        // 设置标签的字体属性

        ActionListener listener = _ -> {
            int mode = 0;
            if (bold.isSelected()) mode += Font.BOLD;
            if (italic.isSelected()) mode += Font.ITALIC;
            label.setFont(new Font("Serif", mode, FONTSIZE));
        };

        // 添加复选框
        var buttonPanel = new JPanel();

        bold = new JCheckBox("Bold");
        bold.addActionListener(listener);
        bold.setSelected(true);
        buttonPanel.add(bold);

        italic = new JCheckBox("Italic");
        italic.addActionListener(listener);
        buttonPanel.add(italic);

        add(buttonPanel, BorderLayout.SOUTH);
        pack();
    }
}
```

## `javax.swing.JCheckBox` 1.2

- `JCheckBox(String label, Icon icon)` 构建一个初始未选中的复选框。

- `JCheckBox(String label, boolean state)` 构建一个具有给定标签和初始状态的复选框。

- `boolean isSelected()`

- `void setSelected(boolean state)` 获取或设置复选框的选择状态。

### 11.4.2 单选按钮（Radio Buttons）

在上一个示例中，用户可以选中两个复选框中的一个、两个或都不选。在很多情况下，我们希望用户只勾选多个框中的一个。当另一个框被选中时，之前的框会自动取消选中。这样一组框通常被称为单选按钮组，因为这些按钮的工作就像收音机上的电台选择按钮一样。

当你按下一个按钮时，之前按下的按钮会弹出。图 11.13 显示了一个典型的示例。我们允许用户从选项中选择一种字体大小——小、中、大或特大——但当然，我们允许一次只选择一种大小。



![](img/240dbf1b84e081687f1e252bd386c684_795_0.png)

图 11.13：单选按钮组

在 Swing 中实现单选按钮组非常简单。你为每组按钮构造一个 `ButtonGroup` 类型的对象。然后，将 `JRadioButton` 类型的对象添加到按钮组中。按钮组对象负责在点击新按钮时，关掉之前设置的按钮。

```java
var group = new ButtonGroup();

var smallButton = new JRadioButton("Small", false);
group.add(smallButton);

var mediumButton = new JRadioButton("Medium", true);
group.add(mediumButton);
...
```

构造函数的第二个参数对于初始应选中的按钮为 `true`，对于所有其他按钮为 `false`。注意，按钮组只控制按钮的行为；如果你是为了布局目的而对按钮分组，你还需要将它们添加到诸如 `JPanel` 的容器中。

如果你再次查看图 11.12，你会注意到单选按钮的外观与图 11.13 中的复选框不同。复选框是正方形的，选中时包含一个勾号。单选按钮是圆形的，选中时包含一个圆点。

单选按钮的事件通知机制与其他任何按钮相同。当用户勾选单选按钮时，按钮会产生一个动作事件。在示例程序中，我们定义了一个监听器，将字体大小设置为特定的值：

```java
ActionListener listener = -> label.setFont(new Font("Serif", Font.PLAIN, size));
```

将此监听器设置与复选框示例进行比较。每个单选按钮获得一个不同的监听器对象。每个监听器对象都确切知道需要做什么——将字体大小设置为特定的值。对于复选框，我们使用了不同的方法：两个复选框使用同一个动作监听器，该监听器调用一个查看两个复选框当前状态的方法。

我们在这里可以采用相同的方法吗？我们可以有一个单一监听器按如下方式计算大小：

```java
if (smallButton.isSelected()) size = 8;
else if (mediumButton.isSelected()) size = 12;
```

然而，我们倾向于使用独立的动作监听器对象，因为它们将大小值与按钮结合得更紧密。

![](img/240dbf1b84e081687f1e252bd386c684_797_0.png)

**注意：** 如果你有一组单选按钮，你知道其中只有一个被选中。如果能够快速发现是哪一个，而不需要查询组中的所有按钮，那就太好了。`ButtonGroup` 对象控制所有按钮，但它没有提供获取选中按钮的方法。你必须遍历组中的按钮并检查哪一个是被选中的。这是 Swing API 的一点局限性。

# Listing 11.3

`v2ch11/radioButton/RadioButtonFrame.java`

```java
package v2ch11.radioButton;
import java.desktop;
/*
 * 一个带有示例文本标签和用于选择
 * 字体大小的单选按钮的框架
 */
public class RadioButtonFrame extends JFrame {
    private JPanel buttonPanel;
    private ButtonGroup group;
    private JLabel label;
    private static final int DEFAULT_SIZE = 36;

    public RadioButtonFrame() {
        // 添加示例文本标签
        label = new JLabel("The quick brown fox jumps over the\nlazy dog.");
        label.setFont(new Font("Serif", Font.BOLD, FONTSIZE));
        add(label, BorderLayout.CENTER);
        // 添加单选按钮
        buttonPanel = new JPanel();
        group = new ButtonGroup();
        addRadioButton("Small", 8);
        addRadioButton("Medium", 12);
        addRadioButton("Large", 18);
        addRadioButton("Extra large", 36);

        add(buttonPanel, BorderLayout.SOUTH);
        pack();
    }

    /**
     * 添加一个设置字体大小的单选按钮
     * @param name 显示在按钮上的字符串
     * @param size 设置的字体大小
     */
    public void addRadioButton(String name, int size) {
        boolean selected = size == DEFAULT_SIZE;
        var button = new JRadioButton(name, selected);
        group.add(button);
        buttonPanel.add(button);

        // 此监听器设置字体大小
        ActionListener listener = -> label.setFont(new Font("Serif", Font.PLAIN, size));
        button.addActionListener(listener);
    }
}
```

# `javax.swing.JCheckBox` 1.2

- `JCheckBox(String label, Icon icon)` 构建一个初始未选中的复选框。
- `JCheckBox(String label, boolean state)` 构建一个具有给定标签和初始状态的复选框。
- `boolean isSelected()`
- `void setSelected(boolean state)` 获取或设置复选框的选择状态。

# `javax.swing.ButtonGroup` 1.2

- `void add(AbstractButton b)` 将按钮添加到组。
- `ButtonModel getSelection()` 返回选中按钮的模型。

# `javax.swing.ButtonModel` 1.2

- `String getActionCommand()` 返回此按钮模型的动作命令。

# `javax.swing.AbstractButton` 1.2

- `void setActionCommand(String s)` 设置按钮及其模型的动作命令。

## 11.4.3. 边框（Borders）

如果你在一个窗口中有多个单选按钮组，你会希望在视觉上指示哪些按钮是一组的。Swing 提供了一组用于此有用的边框。你可以将边框应用于任何扩展 `JComponent` 的组件。最常用的用法是在面板周围放置边框，并向该面板填充其他用户界面元素。

你可以选择多种边框，但对于所有边框都需要遵循相同的步骤。

1. 调用 `BorderFactory` 的静态方法创建边框。你可以从以下样式中选择[图 11.14]：

   - 下凹斜角（Lowered bevel）
   - 凸起级别（Raised level）
   - 蚀刻（Etched）
   - 线条（Line）
   - 哑光（Matte）
   - 空（Empty，仅用于在组件周围留出空白空间）

![](img/240dbf1b84e081687f1e252bd386c684_801_0.png)

**图 11.14：** 测试边框类型

2. 如果需要，可以通过将边框传递给 `BorderFactory.createTitledBorder` 为你的边框添加标题。
3. 如果你真的想追求极致，可以通过调用 `BorderFactory.createCompoundBorder` 将多个边框组合。
4. 通过调用 `JComponent` 类的 `setBorder` 方法将生成的边框添加到你的组件中。

例如，以下是如何向面板添加带有标题的刻蚀边框的：

```java
Border etched = BorderFactory.createEtchedBorder();
Border titled = BorderFactory.createTitledBorder(etched, "A Title\n");
panel.setBorder(titled);
```

不同的边框具有设置边框宽度和颜色的不同选项；详情请参见 API 注释。真正的边框爱好者会发现，还有一个 `SoftBevelBorder` 类用于具有圆角的斜角边框，并且 `LineBorder` 也可以具有圆角。你只能通过使用类的构造函数来构建这些边框——它们没有对应的 `BorderFactory` 方法。

## `javax.swing.BorderFactory` 1.2

- `static Border createLineBorder(Color color)`
- `static Border createLineBorder(Color color, int thickness)`  
  创建一个简单的线条边框。
- `static Border MatteBorder(int top, int left, int bottom, int right, Color color)`
- `static Border MatteBorder(int top, int left, int bottom, int right, Icon tileIcon)`  
  创建一个填充颜色或重复图标的厚边框。
- `static Border createEmptyBorder()`
- `static Border createEmptyBorder(int top, int left, int bottom, int right)`  
  创建一个空空边框。
- `static Border createEtchedBorder()`
- `static Border createEtchedBorder(Color highlight, Color shadow)`
- `static Border createEtchedBorder(int type)`
- `static Border createEtchedBorder(int type, Color highlight, Color shadow)`  
  创建一个具有 3D 效果的线条边框。`type` 参数是 `EtchedBorder.RASED` 或 `etchedBorder.LOWERED` 之一。
- `static Border createBevelBorder(int type)`
- `static Border createBevelBorder(int type, Color shadow)`
- `static Border createLoweredBevelBorder()`
- `static Border createRaiserBevelBorder()`  
  创建一个具有凹凸凸表面效果的边框。`type` 参数是 `BevelBorder.RASED` 或 `BevelBorder.LOWERED` 之一。
- `static TitledBorder createTitledBorder(String title)`
- `static TitledBorder createTitledBorder(Border border)`
- `static TitledBorder createTitledBorder(Border border, String title)`
- `static TitledBorder createTitledBorder(Border border, String title, int justification, int position)`
- `static TitledBorder createTitledBorder(Border border, String title, int justification, int position, Font font)`
- `static TitledBorder createTitledBorder(Border border, String title, int justification, int position, Font font, Color color)`  
  带有指定属性的标题边框。`justification` 参数是 `TitledBorder` 常量 `LEFT`、`CENTER`、`RIGHT`、`LEADING`、`TRAILING` 或 `DEFAULT_JUSTIFICATION`（左对），而 `position` 是 `ABOVE_TOP`、`TOP`、`BELOW_TOP`、`ABOVE_BOTTOM`、`BOTTOM`、`BELOW_BOTTOM` 或 `DEFAULT_POSITION`（顶部）之一。
- `static CompoundBorder createCompoundBorder(Border outsideBorder, Border insideBorder)`  
  将两个边框组合成一个新的边框。

## `javax.swing.border.SoftBevelBorder` 1.2

- `SoftBevelBorder(int type)`
- `SoftBevelBorder(int type, Color highlight, Color shadow)`  
  创建一个具有软圆角的斜角边框。`type` 参数是 `SoftBevelBorder.RAISED` 或 `SoftBevelBorder.LOWERED` 之一。

## `javax.swing.border.LineBorder` 1.2

- `public LineBorder(Color color, int thickness, boolean roundedCorners)`  
  创建一个具有给定颜色和厚度的线条边框。如果 `roundedCorners` 为 `true`，则边框具有圆角。

## `javax.swing.JComponent` 1.2

- `void setBorder(Border border)`  
  设置此组件的边框。

## 11.4.4. 组合框（Combo Boxes）

如果你有很多备选方案，单选按钮（radio buttons）不是很好的选择，因为它们占据了过多屏幕空间。相反，你可以使用组合框。当用户点击此组件时，会出现一个选择列表，用户随后可以选择其中之一（见图 11.15）。

![](img/240dbf1b84e081687f1e252bd386c684_805_0.png)

图 11.15：组合框

如果下拉列表框被设置为可编辑，你就可以像处理文本字段一样编辑当前选择。为此，该组件被称为组合框（combo box）——它结合了文本字段的灵活性和一组预定义的选项。`JComboBox` 类提供了组合框组件。

从 Java 7 开始，`JComboBox` 类是一个泛型类。例如，`JComboBox<String>` 存储对象，而 `JComboBox<Integer>` 存储整数。

如果下拉列表框被设置为可编辑，你就可以像处理文本字段一样编辑当前选择。为此，该组件被称为组合框——它结合了文本字段的灵活性和一组预定义的选项。`JComboBox` 类提供了组合框组件。

从 Java 7 开始，`JComboBox` 类是一个泛型类。例如，`JComboBox<String>` 存储对象，而 `JComboBox<Integer>` 存储整数。

如果下拉列表框被设置为可编辑，你就可以像处理文本字段一样编辑当前选择。为此，该组件被称为组合框——它结合了文本字段的灵活性和一组预定义的选项。`JComboBox` 类提供了组合框组件。

调用 `setEditable` 方法使组合框变为可编辑。用户可以从字体列表中（Serif、Sansif、Monospaced 等）选择字体。

- `static Border createLineBorder(Color color)`
- `static Border createLineBorder(Color color, int thickness)`  
  创建一个简单的线条边框。
- `static Border MatteBorder(int top, int left, int bottom, int right, Color color)`
- `static Border MatteBorder(int top, int left, int bottom, int right, Icon tileIcon)`  
  创建一个填充颜色或重复图标的厚边框。

当用户从组合框中选择项目时，组合框会生成一个动作事件（action event）。要确定选择了哪个项目，请对事件参数调用 `getSource` 以获取发送事件的组合框的引用。然后调用 `getItem` 方法获取当前选择的项目。你需要将返回的值转换为相应的类型，通常是 `String`。

```java
ActionListener listener = e -> label.setFont(new Font(
    faceCombo.getItemAt(faceCombo.getSelectedIndex()),
    Font.PLAIN,
    DEFAULT_SIZE));
```



```java
Font(
    32,
    faceCombo.getSelectedItem(faceCombo.getSelectedIndex()), Font.PLAIN,
    DEFAULT_SIZE));

// 将组合框添加到框架底部的面板中
var comboPanel = new JPanel();
comboPanel.add(faceCombo);
add(comboPanel, BorderLayout.SOUTH);
pack();

}
```

## `java.swing.JComboBox`

- `boolean isEditable()`
- `void setEditable(boolean b)`

  获取或设置此组合框的`editable`（可编辑）属性。

- `void addItem(Object item)`

  向项目列表添加一个`item`。

- `void insertItemAt(Object item, int index)`

  在指定的索引处向项目列表插入一个`item`。

- `void removeItem(Object item)`

  从项目列表中移除一个`item`。

- `void removeItemAt(int index)`

  移除指定索引处的项。

- `void removeAllItems()`

  从项目列表中移除所有项目。

- `Object getSelectedItem()`

  返回当前选中的项。

## 11.4.5. 滑块（Sliders）

组合框允许用户从离散的值集中进行选择。滑块则允许用户从连续的值中进行选择——例如，1 到 100 之间的任何数字。

构建滑块最常见的方法如下：

```java
var slider = new JSlider(min, max, initialValue);
```

如果你省略了最小值、最大值和初始值，它们将分别初始化为 0、100 和 50。

或者，如果你想让滑块垂直显示，请使用以下构造函数调用：

```java
var slider = new JSlider(SwingConstants.VERTICAL, min, max, initialValue);
```

这些构造函数创建了一个简单的滑块，例如图 11.16 中顶部的滑块。你现在将看到如何为滑块添加装饰。

### 图 11.16：滑块

当用户滑动滑块条时，滑块的`值`会在最小值和最大值之间移动。当值发生变化时，一个`ChangeEvent`会发送给所有更改监听器。要接收更改通知，请调用`addChangeListener`方法并安装一个实现`ChangeListener`接口的对象。在回调中，获取滑块的值：

```java
ChangeChangeListener listener = _ -> {
    JSlider slider = (JSlider) event.getSource();
    int value = slider.getValue();
};
```

你可以通过显示刻度线（ticks）来装饰滑块。例如，在示例程序中，第二个滑块使用了以下设置：

```java
slider.setMajorTickSpacing(20);
slider.setMinorTickSpacing(5);
```

滑块每隔 20 个单位有一个大刻度，每隔 5 个单位有一个小刻度。单位指的是滑块的值，而不是像素。

这些指令仅设置了刻度的单位。要让刻度线实际出现，请调用：

```java
slider.setPaintTicks(true);
```

主刻度和小刻度是独立的。例如，你可以设置每隔 20 个单位一个主刻度，每隔 7 个单位一个小刻度，但这会给你带来一个非常混乱的刻度。

你可以强制滑块吸附到刻度上。每当用户在吸附模式下完成拖动滑块时，它会立即移动到最近的刻度处。你通过调用以下方法来激活此模式：

```java
slider.setSnapToTicks(true);
```

> **注意：**“吸附到刻度”的行为并没有你想象的那么好。在滑块真正吸附之前，更改监听器报告的滑块值并不对应刻度。而且如果你点击滑块旁边——此操作通常会让滑块向点击方向移动一点——开启了“吸附到刻度”的滑块不会移动到下一个刻度。

你可以通过调用以下方法为主刻度显示标签：

```java
slider.setPaintLabels(true);
```

例如，对于范围从 0 到 100 且主刻度间距为 20 的滑块，刻度标签为 0、20、40、60、80 和 100。

还可以提供其他刻度标签，例如字符串或图标（见图 11.16）。这个过程有点复杂。你需要填充一个键为`Integer`类型、值为`Component`类型的哈希表。然后调用`setLabelTable`方法。组件被放置在刻度线下方。通常使用`JLabel`对象。以下是如何将刻度标记为 A、B、C、D、E 和 F 的：

```java
var labelTable = new Hashtable<Integer, Component>();
labelTable.put(0, new JLabel("A"));
labelTable.put(20, new JLabel("B"));
labelTable.put(100, new JLabel("F"));
slider.setLabelTable(labelTable);
```

列表 11.5 还显示了一个使用图标作为刻度标签的滑块。

> **提示：**如果你的刻度线或标签没有显示，请双检你是否调用了`setPaintTicks(true)`和

图 11.16 中的第四个滑块没有轨道。第五个滑块通过调用反转了方向。列表 11.5 中的示例显示了所有的视觉效果，并将滑块值放入了`textField`中。

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class SliderFrame extends JFrame {
    private JSlider slider;
    private JTextField textField;
    private ChangeChangeListener listener;

    public SliderFrame() {
        sliderPanel = new JPanel();
        textField = new JTextField();
        slider = new JSlider(0, 100, 50);
        sliderPanel.add(slider);
        sliderPanel.add(textField);
        add(sliderPanel, BorderLayout.CENTER);
        pack();

        listener = event -> {
            JSlider slider = (JSlider) event.getSource();
            textField.setText("" + slider.getValue());
        };

        slider.addChangeListener(listener);
    }
}
```

`ImageIcon("images/ace.gif"));`

112

```java
slider.setLabelTable(labelTable);
```

113

```java
addSlider(slider, "Icon labels");
```

114

115

```java
// add the text field that displays the slider
```

116

117

```java
textField = new JTextField();
```

118

```java
add(sliderPanel, BorderLayout.CENTER);
```

119

```java
add(textField, BorderLayout.SOUTH);
```

120

121

```java
pack();
```

122

```java
}
```

```java
/**
 * Adds a slider to the slider panel and hooks up the
 * listener.
 * @param slider the slider slider
 * @param description the slider description
 */
public void addSlider(JSlider slider, String description) {
    slider.addChangeListener(listener);
    var panel = new JPanel();
    panel.add(slider);
    panel.add(new JLabel(description));
    panel.setAlignment(Component.LEFT_ALIGNMENT);
    var gbc = new GridBagConstraints();
    gbc.gridy = slider.getCount();
    gbc.anchor = GridBagConstraints.WEST;
    slider.add(panel, gbc);
}
```

## `javax.swing.JSlider 1.2`

- `JSlider()`
- `JSlider(int direction)`
- `JSlider(int min, int max)`
- `JSlider(int min, int max, int initialValue)`
- `JSlider(int direction, int min, int max, int initialValue)`

根据给定的方向、最小值、最大值和初始值创建一个滑块。`direction`参数是`SwingConstants.HORIZONTAL`或`SwingConstants.VERTICAL`之一。默认为水平方向。最小、初始和最大值的默认值为 0、50 和 100。

- `void setPaintTicks(boolean b)`

  如果`b`为 true，则显示刻度。

- `void setMajorTickSpacing(int units)`
- `void setMinorTickSpacing(int units)`

  在给定单位的倍数处设置主刻度或次要刻度。

- `void setPaintLabels(boolean b)`

  如果`b`为 true，则显示刻度标签。

- `void setLabelTable(Dictionary table)`

  设置用于刻度标签的组件。表中的键/值对格式为`Integer.valueOf(value)/component`。

- `void setSnapToTicks(boolean b)`

  如果`b`为 true，则滑块在每次调整后将对齐到最近的刻度处。

- `void setPaintTrack(boolean b)`

  如果`b`为 true，则显示滑块运行的轨道。

# 11.5. 菜单

本章首先介绍了你可能想要放入窗口的各种常用组件，例如各种类型的按钮、文本字段和组合框。Swing 还支持另一种类型的用户界面元素——下拉菜单，这在 GUI 应用中很常见。

窗口顶部的菜单栏包含下拉菜单的名称。点击名称将打开包含菜单项和子菜单的菜单。当用户点击菜单项时，所有菜单将关闭，并向程序发送消息。图 11.17 显示了一个带有子菜单的典型菜单。

![](img/240dbf1b84e081687f1e252bd386c684_819_0.png)

## 11.5.1. 菜单构建

构建菜单非常简单。首先，创建一个菜单栏：

```java
var menuBar = new JMenuBar();
```

菜单栏只是一个可以放在任何地方的组件。通常，你希望它出现在框架的顶部。你可以使用`setJMenuBar`方法将其添加到那里：

```java
frame.setJMenuBar(menuBar);
```

对于每个菜单，你创建一个菜单对象：

```java
var editMenu = new JMenu("Edit");
```

将顶层菜单添加到菜单栏：

```java
menuBar.add(editMenu);
```

将菜单项、分隔符和子菜单添加到菜单对象：

```java
var pasteItem = new JMenuItem("Paste");
editMenu.add(pasteItem);
editMenu.addSeparator();
JMenuItem optionsMenu = . . .; // 一个子菜单
editMenu.add(optionsMenu);
```

你可以在下方图 11.17 中的“粘贴（Paste）”和“只读（Read-only）”菜单项下方看到分隔符。

当用户选择菜单项时，会触发一个动作事件。你需要为每个菜单项安装一个动作监听器：

```java
ActionListener listener = . . .;
pasteItem.addActionListener(listener);
```

`JMenu.add(String s)`方法方便地将菜单项添加到菜单的末尾。例如：

```java
editMenu.add("Paste");
```

`add`方法返回创建的菜单项，因此你可以捕获它并添加监听器：

```java
pasteItem.addActionListener(listener);
```

经常发生的情况是菜单项触发的动作也可以通过按钮等用户界面元素激活。在第 10 章中，你学习了如何通过`Action`对象指定命令。你定义一个继承`AbstractAction`的类，并重写`actionPerformed`方法。例如：

```java
var exitAction = new AbstractAction("Exit") {
    public void actionPerformed(ActionEvent event) {
        System.exit(0);
    }
};
```

然后你可以将动作添加到菜单：

```java
fileMenu.add(exitAction);
```

## `javax.swing.JSlider 1.2`

- `JSlider()`
- `JSlider(int direction)`
- `JSlider(int min, int max)`
- `JSlider(int min, int max, int initialValue)`
- `JSlider(int direction, int min, int max, int initialValue)`

根据给定的方向、最小值、最大值和初始值创建一个滑块。`direction`参数是`SwingConstants.HORIZONTAL`或`SwingConstants.VERTICAL`之一。默认为水平方向。最小、初始和最大值的默认值为 0、50 和 100。

- `void setPaintTicks(boolean b)`

  如果`b`为 true，则显示刻度。

- `void setMajorTickSpacing(int units)`
- `void setMinorTickSpacing(int units)`

  在给定单位的倍数处设置主刻度或次要刻度。

- `void setPaintLabels(boolean b)`

  如果`b`为 true，则显示刻度标签。

- `void setLabelTable(Dictionary table)`

  设置用于刻度标签的组件。表中的键/值对格式为`Integer.valueOf(value)/component`。

- `void setSnapToTicks(boolean b)`

  如果`b`为 true，则滑块在每次调整后将对齐到最近的刻度处。

- `void setPaintTrack(boolean b)`

  如果`b`为 true，则显示滑块运行的轨道。

## 11.5.2. 菜单项中的图标

菜单项与按钮非常相似。事实上，`JMenuItem`类继承自`AbstractButton`类。就像按钮一样，菜单可以有文本标签、图标或两者兼有。你可以通过`JMenuItem(String, Icon)`或`JMenuItem(Icon)`构造函数指定图标，也可以使用`JMenuItem`类从`AbstractButton`类继承的`setIcon`方法设置它。这是一个示例：

```java
var cutitem = new JMenuItem("Cut", new ImageIcon("cut.gif"));
```

在图 11.17 中，你可以在菜单项旁边看到图标。默认情况下，菜单项文本位于图标的右侧。如果你希望将文本放在左侧，请调用`MenuItem`类从`AbstractButton`类继承的`setHorizontalTextPosition`方法。例如，调用：

```java
cutItem.setHorizontalTextPosition(SwingConstants.LEFT);
```

将将菜单项文本移动到图标的左侧。

你也可以为动作添加图标：

```java
cutAction.putValue(Action.SMALL_ICON, new ImageIcon("cut.gif"));
```

每当你从动作构造菜单项时，`Action.NAME`值将成为菜单项的文本，`Action.SMALL_ICON`值将成为图标。

或者，你可以在`AbstractAction`构造函数中设置图标：



```java
cutAction = new AbstractAction("Cut", new ImageIcon("cut.gif")) {
    public void actionPerformed(ActionEvent event) {
        . . .
    }
}
```

```java
javax.swing.AbstractButton 1.2
```

- `void setHorizontalTextPosition(int pos)`

  设置文本相对于图标的水平位置。`pos` 参数为 `SwingConstants.RIGHT`（文本位于图标右侧）或 `SwingConstants.LEFT`。

```java
javax.swing.AbstractAction 1.2
```

- `AbstractAction(String name, Icon smallIcon)`

  根据给定的名称和图标构造一个抽象动作（action）。

## 11.5.3. 复选框和单选按钮菜单项

复选框和单选按钮菜单项在名称旁边显示一个复选框或单选按钮（参见图 11.17）。当用户选择该菜单项时，该项会在选中和未选中之间自动切换。

除了按钮装饰外，你可以像处理其他菜单项一样处理这些菜单项。例如，以下创建复选框菜单项的方法：

```java
var readonlyItem = new JCheckBoxMenuItem("Read-only");
optionsMenu.add(readonlyItem);
```

单选按钮菜单项与普通单选按钮一样。你必须将它们添加到按钮组（`ButtonGroup`）中。当组中的一个按钮被选中时，所有其他按钮都会自动取消选中。

```java
var group = new ButtonGroup();
var insertItem = new JRadioButtonMenuItem("Insert");
insertItem.setSelected(true);
var overtypeItem = new JRadioButtonMenuItem("Overtype");
group.add(insertItem);
group.add(overtypeItem);
optionsMenu.add(insertItem);
optionsMenu.add(overtypeItem);
```

对于这些菜单项，你并不一定在用户选择项时收到通知。相反，你可以简单地使用 `isSelected` 方法来测试菜单项的当前状态。（当然，这意味着你应该在实例字段中保留对该菜单项的引用）。使用 `setSelected` 方法设置状态。

### `javax.swing.JCheckBoxMenuItem` 1.2

- `JCheckBoxMenuItem(String label)`

  根据给定的标签构造复选框菜单项。

- `JCheckBoxMenuItem(String label, boolean state)`

  根据给定的标签和给定的初始状态（`true` 为选中）构造复选框菜单项。

### `javax.swing.JRadioButtonMenuItem` 1.2

- `JRadioButtonMenuItem(String label)`

  根据给定的标签构造单选按钮菜单项。

- `JRadioButtonMenuItem(String label, boolean state)`

  根据给定的标签和给定的初始状态（`true` 为选中）构造单选按钮菜单项。

### `javax.swing.AbstractButton` 1.2

- `boolean isSelected()`

- `void setSelected(boolean state)`

  获取或设置此项的选择状态（`true` 为选中）。

## 11.5.4. 弹出菜单

弹出菜单（Pop-Up Menu）是一种没有附加到菜单栏上，而是浮动在某处的菜单（参见图 11.18）。

![](img/240dbf1b84e081687f1e252bd386c684_828_0.png)

### 图 11.18：弹出菜单

创建弹出菜单与创建普通菜单相同，不同之处是弹出菜单没有标题。

```java
var popup = new JPopupMenu();
```

然后，像通常一样添加你的菜单项：

```java
var item = new JMenuItem("Cut");
item.addActionListener(listener);
popup.add(item);
```

与始终显示在框架顶部的普通菜单栏不同，你必须使用 `show` 方法显式地显示弹出菜单。指定父组件并使用父组件的坐标系指定弹出菜单的位置。例如：

```java
popup.show(panel, x, y);
```

通常，你希望在用户点击特定的鼠标按钮时弹出菜单——这就是所谓的弹出触发器（pop-up trigger）。在 Windows 和 Linux 中，弹出触发器是非主（通常是右键）鼠标按钮。若要在用户使用弹出触发器点击组件时弹出菜单，只需调用方法：

```java
component.setComponentPopupMenu(popup);
```

极少数情况下，你可能会将一个组件放在另一个弹出菜单的组件内部。子组件可以通过调用以下方法继承父组件的弹出菜单：

```java
child.setInheritsPopupMenu(true);
```

### `javax.swing.JPopupMenu` 1.2

- `void show(Component c, int x, int y)`

  在组件 `c` 上显示弹出菜单，左上角位于 `(x, y)`（在 `c` 的坐标空间内）。

- `boolean isPopupTrigger(MouseEvent event)` 1.3

  如果此鼠标事件是弹出菜单触发器，则返回 `true`。

### `java.awt.event.MouseEvent` 1.1

- `boolean isPopupTrigger()`

  如果此鼠标事件是弹出菜单触发器，则返回 `true`。

### `javax.swing.JComponent` 1.2

- `JPopupMenu getComponentPopupMenu()` 5.0

- `void setComponentPopupMenu(JPopupMenu popup)` 5.0

  获取或设置此组件的弹出菜单。

- `boolean getInheritsPopupMenu()` 5.0

- `void setInheritsPopupMenu(boolean b)` 5.0

  获取或设置 `inheritsPopupMenu` 属性。

## 11.5.5. 键盘记忆键（Mnemonics）和加速键（Accelerators）

记忆键对于通过键盘选择项目的经验用户来说非常方便。你可以通过指定字符为菜单项创建记忆键，例如：

```java
var aboutItem = new MenuItem("About");
```

记忆键允许你从当前打开的菜单中选择子菜单或菜单项。要为菜单附加记忆键，请调用 `setMnemonic` 方法：

```java
var helpMenu = new JMenu("Help");
helpMenu.setMnemonic('H');
```

要在菜单栏中选择顶层菜单，请配合 Alt 键按下记忆字母。例如，Alt+H 选择帮助菜单。

相比之下，加速键是快捷键，允许你在无需打开菜单的情况下选择项目。例如，许多程序为打开和保存项附加 Ctrl+O 和 Ctrl+S。使用 `setAccelerator` 方法为菜单项附加加速键。该方法接受 `KeyStroke` 类型的对象。例如，以下代码将 Ctrl+O 附加到 `openItem`：

```java
openItem.setAccelerator(KeyStroke.getKeyStroke("ctrl O"));
```

输入加速组合会自动选择菜单项并触发动作事件，就像用户手动选择了该菜单项一样。

加速键只能附加到菜单项，不能附加到菜单。加速键不会打开菜单，而是直接触发与菜单关联的动作事件。

从概念上讲，为菜单项添加加速键与为 Swing 组件添加加速键的技术相似。但当加速键添加到菜单项时，按键组合会自动显示在菜单中（参见图 11.20）。

![](img/240dbf1b84e081687f1e252bd386c684_833_0.png)

### 图 11.20：加速键

**注意：** 在 Windows 下，Alt+F4 会关闭窗口。但这并不是 Java 中编写的加速键。它是操作系统定义的快捷键。无论菜单上是否有“关闭”项，该按键组合都会触发 `WindowClosing` 事件。

### `javax.swing.JMenuItem` 1.2

- `JMenuItem(String label, int mnemonic)`

  根据给定的标签和记忆键构造菜单项。

- `void setAccelerator(KeyStroke k)`

  将击键 `k` 设置为此菜单的加速键。加速键显示在标签旁边。

```java
javax.swing.AbstractButton 1.2
```

- `void setMnemonic(int mnemonic)`

  设置按钮的快捷键字符。该字符将在标签中带有下划线显示。

- `void setDisplayedMnemonicIndex(int index)` 1.4

  设置按钮文本中带有下划线的字符的索引。如果你不想让第一个出现的快捷键字符带有下划线，请使用此方法。

## 11.5.6. 启用和禁用菜单项

有时，特定的菜单项只在某些语境下才能被选中。例如，当文档以只读模式打开时，“保存（Save）”菜单项就没有意义。当然，我们可以通过 `JMenu.remove` 方法从菜单中移除该项，但用户对于内容不断变化的菜单会感到有些惊讶。相反，更好的做法是禁用那些通往暂时不恰命令的菜单项。禁用的菜单项以灰色显示，且无法选择（见图 11.21）。

![](img/240dbf1b84e081687f1e252bd386c684_835_0.png)

### 图 11.21：禁用的菜单项

要启用或禁用菜单项，使用 `setEnabled` 方法：

```java
saveItem.setEnabled(false);
```

启用和禁用菜单项有两种策略。每当情况发生变化时，你都可以对相关的菜单项或动作（actions）调用 `setEnabled`。例如，一旦文档被设置为只读模式，你就可以找到“保存”和“另存为”菜单项并禁用它们。或者，你可以在显示菜单之前禁用菜单项。要做到这一点，你必须为“菜单被选中（menu selected）”事件注册监听器。`javax.swing.event` 包定义了一个包含三个方法的 `MenuListener` 接口：

```java
void menuSelected(MenuEvent)
void menuDeselected(MenuEvent event)
void menuCanceled(MenuEvent event)
```

`menuSelected` 方法在菜单显示*之前*被调用。因此，它可以用于禁用或启用菜单项。下面的代码展示了每当“只读（Read Only）”复选框菜单项被选中时，如何禁用“保存”和“另存为”动作：

```java
public void menuSelected(MenuEvent event) {
  saveAction.setEnabled(!readonlyItem.isSelected());
  saveAsAction.setEnabled(!readonlyItem.isSelected());
}
```

> **注意：** 在显示菜单之前禁用菜单项是一个聪明的主意，但对于同样带有快捷键（accelerator keys）的菜单项无效。因为当按下快捷键时菜单永远不会打开，动作永远不会被禁用，并且仍然会被快捷键触发。

### `javax.swing.JMenuItem` 1.2

- `void setEnabled(boolean b)` 启用或禁用菜单项。

### `javax.swing.event.EventListener` 1.2

- `void menuSelected(MenuEvent e)` 在菜单被选中后、在它打开之前被调用。

- `void menuDeselected(MenuEvent e)` 在菜单被取消选中后、在它被关闭后被调用。

- `void menuCanceled(MenuEvent e)` 在菜单被取消时被调用，例如当用户点击菜单外部时。

**Listing 11.6** 是一个生成一组菜单的示例程序。它展示了你在本节中看到的所有功能：嵌套菜单、禁用的菜单项、复选框和单选按钮菜单项、弹出菜单以及键盘快捷键和加速键。

# Listing 11.6 v2ch11/menu/MenuFrame.java

```java
package v2ch11.menu;
import module java.desktop;
/**
* 一个带有示例菜单栏的框架。
 */
public class MenuFrame extends JFrame {
    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 200;
    private Action saveAction;
    private Action saveAsAction;
    private JCheckBoxMenuItem readonlyItem;
    /**
    * 一个将动作名称打印到 System.out 的示例动作。
    */
    class TestAction extends AbstractAction {
        public TestAction(String name) {
            super(name);
        }

        public void actionPerformed(ActionEvent event) {
System.out.println(getValue(Action.NAME) + " \
selected.");
```

```java
public void MenuFrame() {
    setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

    var fileMenu = new JMenuItem("File");
    fileMenu.add(new TestAction("New"));

    // 展示加速键
    var openItem = fileMenu.add(new TestAction("Open"));
openItem.setAccelerator(KeyStroke.getKeyStroke(ctrl O));
```

```java
fileMenu.addSeparator();
    saveAction = new TestAction("Save");
JMenuItem saveItem = fileMenu.add(saveAction);
saveItem.setAccelerator(KeyStroke.getKeyStroke(ctrl S));
```

```java
saveAction = new TestAction("Save As");
fileMenu.add(saveAction);
fileMenu.addSeparator();
```

```java
fileMenu.add(new AbstractAction("Exit") {
    public void actionPerformed(ActionEvent event) {
        System.exit(0);
    }
});

// 展示复选框和单选按钮菜单
```

```java
readonlyItem = new JCheckBox("Read-only");
readonlyItem.addActionListener(() -> {
    boolean saveOk = !readonlyItem.isSelected();
    saveItem.setEnabled(saveOk);
});
```

```java
readonlyItem = new JCheckBox("Read-only");
readonlyItem.addActionListener(() -> {
    boolean saveOk = !readonlyItem.isSelected();
    saveItem.setEnabled(saveOk);
});
```

```java
var group = ButtonGroup();
var insertItem = new JRadioButton("Insert");
insertItem.setSelected(true);
group.add(insertItem);
var overItem = new JRadioButton("Overtype");
group.add(overItem);
```



```java
// 展示图标
var cutAction = new TestAction("Cut");
cutAction.setAccelerator(KeyStroke.getKeyStroke(ctrl C));
var copyAction = new TestAction("Copy");
copyAction.setAccelerator(KeyStroke.getKeyStroke(ctrl V));
var pasteAction = new TestAction("Paste");
pasteAction.setAccelerator(KeyStroke.getKeyStroke(ctrl P));

// 展示嵌套菜单
var editMenu = new JMenu("Edit");
editMenu.add(cutAction);
editMenu.add(copyAction);
editMenu.add(pasteAction);

// 展示快捷键
var helpMenu = new JMenu("Help");
helpMenu.setMnemonic('H');
var indexItem = new JMenuItem("Index");
indexItem.setMnemonic('I');
helpMenu.add(indexItem);

// 展示快捷键
var aboutAction = new TestAction("About");
aboutAction.setMnemonic('A');
helpMenu.add(aboutAction);
```

```java
// 将顶层菜单添加到菜单栏
var menuBar = new JMenuBar();
setMenuBar(menuBar);

menuBar.add(fileMenu);
menuBar.add(editMenu);
menuBar.add(helpMenu);

// 展示弹出菜单
var popup = new JPopupMenu();
popup.add(cutAction);
popup.add(copyAction);
popup.add(pasteAction);
var panel = new JPanel();
panel.setPopupMenu(popup);
add(panel);
```

## 11.5.7. 工具栏

工具栏是一种快速访问程序中常用命令的按钮栏（见图 11.22）。

![](img/240dbf1b84e081687f1e252bd386c684_840_0.png)

图 11.22：工具栏

工具栏的特殊之处在于你可以将其移动到其他地方。你可以将工具栏拖到框架的四个边界之一（见图 11.23）。当你释放鼠标按钮时，工具栏会落在新的位置（见图 11.24）。

![](img/240dbf1b84e081687f1e252bd386c684_841_0.png)

图 11.23：拖动工具栏

- **注意：** 如果工具栏位于具有边界布局（border layout）的容器中，或者任何支持北、东、南、西约束的布局管理器中，拖动就可以生效。

工具栏甚至可以从框架中完全分离。分离的工具栏包含在一个独立的框架中（见图 11.25）。当你关闭包含分离工具的框架时，工具栏回到原始框架。

![](img/240dbf1b84e081687f1e252bd386c684_842_0.png)

图 11.25：分离工具栏

工具栏的编程非常简单。将组件添加到工具栏中：

```java
var toolbar = new JToolBar();
toolbar.add(blueButton);
```

`JToolBar` 类还有一个添加 `Action` 对象的方法。只需像这样用 `Action` 对象填充工具栏即可：

```java
toolbar.add(blueAction);
```

操作的小型图标显示在工具栏中。

你可以使用分隔符将一组按钮隔开：

```java
toolbar.addSeparator();
```

例如，图 11.22 中的工具栏在第三个和第四个按钮之间有一个分隔符。

然后，将工具栏添加到框架中：

```java
add(toolbar, BorderLayout.NORTH);
```

你还可以为工具栏指定一个标题，当工具栏被停靠（undocked）时显示：

```java
toolbar = new JToolBar(titleString);
```

默认情况下，工具栏初始是水平方向的。要让工具栏从垂直方向开始，请使用：

```java
toolbar = new JToolBar(SwingConstants.VERTICAL);
```

或者：

```java
toolbar = new JToolBar(titleString, SwingConstants.VERTICAL);
```

按钮是工具栏内部最常见的组件。但对你可以添加到工具栏的组件没有限制。例如，你可以向工具栏中添加一个组合框。

## 11.5.8. 提示文字（Tooltips）

工具栏的一个缺点是，用户往往会对工具栏中微小图标的含义感到困惑。为了解决这个问题，用户界面设计师发明了提示文字（tooltips）。当光标悬停在按钮上片刻时，提示文字就会激活。提示文字显示在一个颜色的矩形内。当用户移动鼠标时，提示文字就会消失（见图 11.26）。

![](img/240dbf1b84e081687f1e252bd386c684_844_0.png)

图 11.26：提示文字

在 Swing 中，你只需调用 `setToolTipText` 方法即可为任何 `JComponent` 添加提示文字：

```java
exitButton.setToolTipText("Exit");
```

或者，如果你使用 `Action` 对象，可以将提示文字与 `SHORT_DESCRIPTION` 键关联：

```java
exitAction.putValue(Action.SHORT_DESCRIPTION, "Exit");
```

## javax.swing.JToolBar 1.2

- `JToolbar()`

- `JToolbar(String titleString)`

- `JToolbar(int orientation)`

- `JToolbar(String titleString, int orientation)`

  根据给定的标题字符串和方向创建一个工具栏。`orientation` 是 `SwingConstants.HORIZONTAL`（默认）或 `SwingConstants.VERTICAL` 之一。

- `JButton add(Action a)`

  根据给定的 `action`，使用名称、图标、短描述和动作回调，在工具栏内部创建一个新按钮，并将按钮添加到工具栏的末尾。

- `void addSeparator()`

  在工具栏末尾添加一个分隔符。

## javax.swing.JButton 1.2

- `void setToolTipText(String text)`

  设置鼠标悬停在组件上时应显示为提示文字的文本。

## 11.6. 网格包布局（Grid Bag Layout）

到目前为止，我们在示例应用程序的用户界面中仅使用了边界布局、流式布局和网格布局。对于更复杂的任务，这些是不够的。

自 Java 1.0 以来，AWT 包含了网格包布局，它将组件在行和列中排列。行和列的大小是灵活的，组件可以跨越多行多列。这种布局管理器非常灵活，但也非常复杂。仅仅是提到“grid bag layout”这几个词，就让 Java 程序员感到恐惧。

在尝试设计一种能让程序员摆脱网格包布局统治的布局管理器失败后，Swing 设计师提出了箱体布局（box layout）。根据 `BoxLayout` 类的 JDK 文档：“嵌套多个具有不同水平和垂直[sic]组合的面板，可以产生与 `GridBagLayout` 类似的效果，而没有后者的复杂性。”然而，由于每个框都是独立布局的，你无法使用箱体布局同时在水平和垂直方向上排列相邻组件。

Java 1.4 见证另一个尝试设计网格包布局替代品的尝试——弹簧布局（spring layout），你在其中使用想象的弹簧来连接容器中的组件。随着容器大小的改变，弹簧会拉伸或收缩，从而调整组件的位置。这听起来既冗长又困惑，事实也如此。弹簧布局很快就销声无迹了。

NetBeans IDE 结合了布局工具（称为“Matisse”）和布局管理器。用户界面设计师使用该工具将组件拖入容器中，并指示哪些组件应该对齐。该工具将设计师的意图翻译成对组布局管理器的指令。这比手动编写布局管理代码要方便得多。

在接下来的章节中，我将介绍网格包布局，因为它被常用，并且仍然是编程生成布局代码的最简单机制。我将向你展示一种策略，使得网格包布局在常见情况下变得相对不痛苦。

### 11.6.1. 网格包基础

网格包布局是所有布局管理器的母亲。你可以将网格包布局想象成没有限制的网格布局。在网格包布局中，行和列的大小是可变的。你可以合并相邻单元格为更大的组件留出空间。（许多文字处理器以及 HTML 都为表格提供了类似的功能：你可以从网格开始，根据需要合并相邻单元格。）组件不需要填充整个单元格区域，你可以指定它们在单元格内的对齐方式。

考虑图 11.27 中的字体选择器。它由以下组件组成：

- 用于指定字体和大小的两个组合框
- 这两个组合框的标签
- 用于选择粗体和斜体的两个复选框
- 用于示例字符串的文本区域

![](img/240dbf1b84e081687f1e252bd386c684_848_0.png)

图 11.27：字体选择器

现在，将容器划分为单元格，如图 11.28 所示。（行和列不需要大小。）每个复选框跨两列，文本区域跨四行。要描述网格，请使用以下步骤：

1. 创建一个 `GridBagLayout` 对象。你不需要告诉它网格有多少行列。
2. 将此 `GridBagLayout` 对象设置为组件的布局管理器。
3. 对于每个组件，创建一个 `GridBagConstraints` 对象。设置 `GridBagConstraints` 的字段值以指定布局方式。
4. 最后，通过调用以下代码添加组件：

   ```java
   add(component, constraints);
   ```

这里是代码示例：

```java
layout = new GridBagLayout();
panel.setLayout(layout);
var constraints = new GridBagConstraints();
constraints.weight = 100;
constraints.weighty = 100;
constraints.gridx = 0;
constraints.gridy = 2;
constraints.borderwidth = 2;
constraints.gridheight = 1;
```

关键在于如何设置 `GridBagConstraints`。我们将在后面的章节中讨论该对象。

### 11.6.2. `gridx`、`gridy`、`gridwidth` 和 `gridheight` 参数

`gridx`、`gridy`、`gridwidth` 和 `gridheight` 约束定义了组件在网格中的位置。`gridx` 和 `gridy` 值指定了要添加的组件左上角的行列位置。`gridwidth` 和 `gridheight` 值决定了组件占据的列数行数。

左上角的 `gridx = 0`，`gridy = 0`。我们示例中的文本区域 `gridx = 2`、`gridy = 0`，因为它从第 0 行的第 2 列（即第三列）开始。它的 `gridwidth = 1`、`gridheight = 4`，因为它跨了一列四行。

### 11.6.3. 权重字段

你始终需要为网格包布局中的每个区域设置字段（`weightx` 和 `weighty`）。如果你将权重设置为 0，则该区域在该方向上不会超出其初始大小进行缩小。在图 11.27 的网格包布局中，我们将标签的权重字段设置为 0。这允许标签在调整窗口时保持宽度不变。相反，如果你将所有区域的权重设置为 0，容器将聚集在分配区域的中心，而不是扩展填充它。

从概念上讲，权重参数的问题在于权重是行和列的属性，而不是单个单元格。但你需要为单元格指定它们，因为网格包布局（bag layout）并不暴露行和列。行和列的权重是通过每行或每列单元格权重的最大值计算得。因此，如果你想让某一行或一列保持固定大小，你需要将其中所有组件的权重设置为零。

请注意，权重实际上并没有给出列的相对大小。它们告诉的是，如果容器超过了它的首选尺寸，应该将多少比例的“剩余”（slack）空间分配给每个区域。这并不特别直观。我建议你将所有权重设置为 100。然后运行程序并查看布局效果。调整对话框的大小，观察行和列是如何调整的。如果你发现某一行或某一列不应该增长，请将其中所有组件的权重设置为 0。你可以尝试不同的权重值，但通常不值得花精力。

### 11.6.4. `fill`（填充）和 `anchor`（锚点）参数

如果你不想让组件拉伸并填充整个区域，请设置 `fill` 约束。该参数有四种可能：有效值为 `GridBagConstraints.NONE`、`GridBagConstraints.HORIZONTAL`、`GridBagConstraints.VERTICAL` 和 `GridBagConstraints.BOTH`。

如果组件没有填充整个区域，你可以通过设置 `anchor` 字段来指定你希望它位于区域的位置。有效值为 `GridBagConstraints.CENTER`（默认值）、`GridBagConstraints.NORTH`、`GridBagConstraints.NORTHEAST`、`GridBagConstraints.EAST` 等。

### 11.6.5. Padding（内边距）

你可以通过设置 `GridBagConstraints` 的 `insets` 字段在组件周围留出额外的空白。将 `Insets` 对象的左、上、右、下值设置为你希望在组件周围保留的空间量。这被称为外部内边距。

`ipadx` 和 `ipady` 值设置内部内边距。这些值会被加上组件的最小宽度和高度。这确保了组件不会缩小到它的最小尺寸。

### 11.6.6. 指定 `gridx`、`gridy`、`gridwidth` 和 `gridheight` 参数的替代方法

AWT 文档建议，不要将 `gridx` 和 `gridy` 值设置为绝对位置，而是将它们设置为常量 `GridBagConstraints.RELATIVE`。然后，按照标准顺序将组件添加到 `gridbag` 布局中：从第一行从左到右，然后移动到下一行，依此类推。

你仍然可以通过提供适当的 `gridheight` 和 `gridwidth` 字段来指定跨越的行列数。然而，如果组件延伸到最后一行或最后一列，你不需要指定实际数字，可以使用常量 `GridBagConstraints.REMAINDER`。

这告诉布局管理器该组件是其行中的最后一个。

这种方案似乎确实有效。但向布局管理器隐藏实际的放置信息并希望它能重新发现，这听起来真的很愚蠢。

### 11.6.7. Grid Bag 布局配方（Recipe）

在实践中，以下配方可以使 `grid bag` 布局变得相对省心：

1. 在纸上勾勒组件布局。
2. 找到一个网格，使得小型组件各包含在一个单元格中，而较大的组件跨越多个单元格。
3. 用 0、1、2、3、……为网格的行和列标记。现在你可以读出 `gridx`、`gridy`、`gridwidth` 和 `gridheight` 值了。
4. 对于每个组件，问问自己它是否需要水平或垂直填充其单元格。如果不需要，你想让如何对齐？这决定了 `fill` 和 `anchor` 参数。
5. 将所有权重设置为 100。然而，如果你想让某一行或某一列始终保持默认大小，请将属于该行或该列的所有组件的 `weight` 或 `weighty` 设置为 0。
6. 编写代码。仔细双检你的 `GridBagConstraints` 设置。一个错误的约束就会毁掉你的整个布局。
7. 编译、运行并享受。

### 11.6.8. 一个用于简化 Grid Bag 约束的辅助类

`grid bag` 布局最枯燥的是编写设置约束的代码。大多数程序员会为此目的编写辅助函数或一个较小的辅助类。我在字体对话框示例的完整代码之后展示了这样一个类。该类具有以下特征：

- 它的名字很短：是 `GBC` 而不是 `GridBagConstraints`。
- 它继承自 `GridBagConstraints`，因此你可以使用 `GBC.EAST` 这样更短的名字作为常量。
- 在添加组件时使用 `GBC` 对象，例如 `add(component, new GBC(1, 2));`
- 有两个构造函数来设置最常用的参数：`gridx` 和 `gridy`，或者 `gridx`、`gridy`、`gridwidth` 和 `gridheight`。`add(component, new GBC(1, 2, 1, 4));`
- 对于成对出现的 x/y 字段，提供方便的 setter：`add(component, new GBC(1, 2).setWeight(100, 100));`
- setter 方法返回 `this`，因此你可以链式调用：`add(component, new GBC(1, 2).setAnchor(GBC.EAST).setWeight(100, 100));`

`setInsets` 方法用于构造 `Insets` 对象。要获得 1 像素的内边距，只需调用：

```java
add(component, new GBC(1, 2).setAnchor(GBC.EAST).setInsets(1));
```

列表 11.7 显示了字体对话框示例的框架。`GBC` 辅助类在列表 11.8 中。以下是将组件添加到 `grid bag` 的代码：

```java
add(component, new GBC(1, 2).setAnchor(GBC.EAST));
```



```java
/**
 * 将值设置为默认值。
 * @param gridx 的 gridx 位置
 * @param gridy 的 gridy 位置
 */
public GBC(int gridx, int gridy) {
    this.gridx = gridx;
    this.gridy = gridy;
}

/**
 * 使用给定的 gridx, gridy, gridwidth,
 * gridheight 构造一个 GBC，并将所有其他网格包约束值设置为默认值。
 * @param gridx 的 gridx 位置
 * @param gridy 的 gridy 位置
 * @param gridwidth x方向的单元格跨度
 * @param gridheight y方向的单元格跨度
 */
public GBC(int gridx, int gridy, int gridwidth, gridheight) {
    this.gridx = gridx;
    this.gridy = gridy;
    this.gridwidth = gridwidth;
    this.gridheight = gridheight;
}

/**
 * 设置锚点。
 * @param anchor 锚点值
 * @return 此对象以便进行进一步修改
 */
public GBC setAnchor(int anchor) {
    this.anchor = anchor;
    return this;
}

/**
 * 设置填充方向。
 * @param fill 填充方向
 * @return 此对象以便进行进一步修改
 */
public GBC setFill(int fill) {
    this.fill = fill;
    return this;
}

/**
 * 设置单元格权重。
 * @param weighttx x方向的单元格权重
 * @param weighty y方向的单元格权重
 * @return 此对象以便进行进一步修改
 */
public GBC setWeight(double weighttx, double weighty) {
    this.weighttx = weighttx;
    this.weighty = weighty;
    return this;
}

/**
 * 设置此单元格的内边距。
 * @param distance 在所有方向使用的间距
 * @return 此对象以便进行进一步修改
 */
public GBC setInsets(int distance) {
    this.insets = new Insets(distance, distance, distance);
    return this;
}

/**
 * 设置此单元格的内边距。
 * @param top 顶部使用的间距
 * @param left 左侧使用的间距
 * @param bottom 底部使用的间距
 * @param right 右侧使用的间距
 * @return 此对象以便进行进一步修改
 */
public GBC setInsets(int top, int left, int bottom, int right) {
    this.insets = new Insets(top, left, bottom, right);
    return this;
}

/**
 * 设置内部填充。
 * @param ipad x方向的填充
 * @param ipady y方向的内部填充
 * @return 此对象以便进行进一步修改
 */
public GBC setPadding(int ipad, int ipady) {
    this.ipadx = ipad;
    this.ipady = ipady;
    return this;
}
```

# `java.awt.GridBagConstraints` 1.0

- `int gridx, int gridy`：指定单元格的起始列和行。默认值为 0。
- `int gridwidth, int gridheight`：指定单元格的列和行跨度。默认值为 1。
- `double weightx, double weighty`：指定单元格增长的能力。默认值为 0。
- `int anchor`：指明组件在单元格内的对齐方式。你可以选择以下绝对位置：

| NORTHWEST | NORTH | NORTHEAST |
| :--- | :--- | :--- |
| WEST | CENTER | EAST |
| SOUTHWEST | SOUTH | SOUTHEAST |

或者它们与方向无关的对应项：

| FIRST_LINE_START | LINE_START | FIRST_LINE_END |
| :--- | :--- | :--- |
| PAGE_START | CENTER | PAGE_END |
| LAST_LINE_START | LINE_END | LAST_LINE_END |

如果你的应用程序可能针对从右到左或从上到下的文本进行本地化，请使用后者。默认值为 `CENTER`。

- `int fill`：指定单元格内组件的填充行为：`NONE`、`BOTH`、`HORIZONTAL` 或 `VERTICAL` 之一。默认值为 `NONE`。
- `int ipadx, int pady`：指定组件周围的“内部”填充。默认值为 0。
- `Insets`：指定沿单元格边界的“外部”填充。默认值为无填充。
- `GridBagConstraints(int gridx, int gridy, int gridwidth, int gridheight, double weight, double weighty, int anchor, int fill, Insets insets, int ipadx, int ipady)` 1.2：通过参数指定的所有字段来构造 `GridBagConstraints`。此构造函数应该只由自动代码生成器使用，因为它会让你的源代码非常难以阅读。

# 11.7. 自定义布局管理器

你可以设计自己的 `LayoutManager` 类，以特殊方式管理组件。例如，让我们将容器中的所有组件排列成一个圆（见图 11.29）。

# 图 11.29：圆形布局

你自己的布局管理器必须实现 `LayoutManager` 接口。你需要重写以下方法：

```java
void addLayoutComponent(String name, Component c)
void removeLayoutComponent(Component c)
Dimension preferredLayoutSize(Container parent)
Dimension minimumLayoutSize(Container parent)
void layoutContainer(Container parent)
```

前两个方法在组件添加或删除时被调用。如果你不保留任何关于组件的信息，你可以什么都不做。接下来两个方法计算所需的最小和首选空间。第五个方法执行实际工作并对组件进行布局。AWT 有第二个接口叫做 `Layout2`，它有五个方法，允许你使用约束。GridBag 的示例是，沿圆形排列父容器内部的。示例 11.10：`circleLayout`

示例 11.9：`CircleLayout.java`

```java
package circleLayout;
import java.awt.*;

/**
 * 沿圆形排列组件的布局管理器。
 */
public class CircleLayout implements LayoutManager {
    private int minWidth = 0;
    private int minHeight = 0;
    private int preferredWidth = 0;
    private int preferredHeight = 0;
    private boolean sizes = false;
    private int maxComponentWidth = 0;
    private int maxComponentHeight = 0;

    public void addLayoutComponent(String name, Component c) {
    }

    public void removeLayoutComponent(Component c) {
    }

    public void setSizes(Container parent) {
        if (sizes) return;
        int n = parent.getComponentCount();
        preferredWidth = 0;
        preferredHeight = 0;
        maxComponentWidth = 0;
        maxComponentHeight = 0;

        // 计算最大组件的宽度和高度
        // 设置首选尺寸之和
        for (int i = 0; i < n; i++) {
            Component c = parent.getComponent(i);
            if (c.isVisible()) {
                Dimension d = c.getPreferredSize();
                maxComponentWidth = Math.max(maxComponentWidth, d.width);
                maxComponentHeight = Math.max(maxComponentHeight, d.height);
                preferredWidth += d.width;
                preferredHeight += d.height;
            }
        }
        minWidth = preferredWidth / 2;
        minHeight = preferredHeight / 2;
        sizes = true;
    }

    public Dimension preferredLayoutSize(Container parent) {
        setSizes(parent);
        Insets insets = parent.getInsets();
        int width = preferredWidth + insets.left + insets.right;
        int height = preferredHeight + insets.top + insets.bottom;
        return new Dimension(width, height);
    }

    public Dimension minimumLayoutSize(Container parent) {
        setSizes(parent);
        Insets insets = parent.getInsets();
        int width = minWidth + insets.left + insets.right;
        int height = minHeight + insets.top + insets.bottom;
        return new Dimension(width, height);
    }

    public void layoutContainer(Container parent) {
        setSizes(parent);
        // 计算圆心
        Insets insets = parent.getInsets();
        int containerWidth = parent.getSize().width - insets.left - insets.right;
        int containerHeight = parent.getSize().height - insets.top - insets.bottom;
        int xcenter = insets.left + containerWidth / 2;
        int ycenter = insets.top + containerHeight / 2;

        // 计算圆的半径
        int xradius = (containerWidth - maxComponentWidth) / 2;
        int yradius = (containerHeight - maxComponentHeight) / 2;
        int radius = Math.min(xradius, yradius);

        // 沿圆形布局组件
        int n = parent.getComponentCount();
        for (int i = 0; i < n; i++) {
            Component c = parent.getComponent(i);
            if (c.isVisible()) {
                double angle = 2 * Math.PI * i / n;

                // 组件中心点
                int x = xcenter + (int) (Math.cos(angle) * radius);
                int y = ycenter + (int) (Math.sin(angle) * radius);

                // 移动组件使其中心位于 (x, y)
                // 且尺寸为其首选尺寸
                Dimension d = c.getPreferredSize();
                c.setBounds(x - d.width / 2, y - d.height / 2, d.width, d.height);
            }
        }
    }
}
```

# Listing 11.10

`v2ch11/circleLayout/CircleLayoutFrame.java`

```java
package v2ch11.circleLayout;
import javax.swing.*;

/**
 * 一个显示沿圆形排列的按钮的框架。
 */
public class CircleLayoutFrame extends JFrame {
    public CircleLayoutFrame() {
        setLayout(new CircleLayout());
        add(new JButton("Yellow"));
        add(new JButton("Blue"));
        add(new JButton("Red"));
        add(new JButton("Green"));
        add(new JButton("Orange"));
        add(new JButton("Fuchsia"));
        add(new JButton("Indigo"));
    }

    pack();
}
```

# `java.awt.Layout` 1.0

- `void addLayoutComponent(String name, Component comp)`：向布局管理器添加一个组件。
- `void removeLayoutComponent(Component comp)`：从布局中移除一个组件。
- `Dimension preferredLayoutSize(Container cont)`：返回该布局管理器下容器的首选尺寸。
- `Dimension minimumLayoutSize(Container cont)`：返回该布局管理器下容器的最小尺寸。
- `void layoutContainer(Container cont)`：对容器中的组件进行布局。

## 11.8. 对话框

在 GUI 应用中，你通常希望弹出独立的对话框向用户提供信息或从用户处获取信息。

与大多数窗口系统一样，AWT 区分了模态（modal）和非模态（modelless）对话框。模态对话框在用户处理它之前，不允许用户与应用程序的其余窗口交互。当你需要在继续执行之前获取用户的信息时，使用模态对话框。例如，当用户想要读取文件时，就会弹出一个模态对话框。用户在程序开始读取操作之前必须指定文件名。只有用户关闭模态对话框后，应用程序才能继续。

非模态对话框允许用户在对话框和程序的其余输入信息。非模态对话框的一个例子是工具栏。工具栏可以一直保持在那里，用户可以同时与应用程序窗口和工具栏进行交互。

让我们从简单的对话框开始——仅带有单个消息的模态对话框。Swing 有一个方便的 `JOptionPane` 类，它可以让你无需编写任何特殊的对话框代码即可显示简单的对话框。接下来，你将看到如何通过实现自己的对话窗口来编写更复杂的对话框。最后，你将看到如何将数据从应用程序传输到对话框并返回。

我们将通过查看 Swing `JFileChooser` 来结束对对话框的讨论。

### 11.8.1. 选项面板

Swing 有了一系列现成的简单对话框，足以向用户询问单个信息。`JOptionPane` 有四个静态方法来显示这些简单的对话框：

| 方法 | 描述 |
| :--- | :--- |



| 方法 | 描述 |
| :--- | :--- |
| `showMessageDialog` | 显示消息并等待用户点击 OK |
| `showConfirmDialog` | 显示消息并获取确认（如 OK/取消） |
| `showOptionDialog` | 显示消息并获取选项（通常来自一组按钮） |
| `showInputDialog` | 显示消息并获取用户输入（通常来自输入字段或组合框） |

图 11.30 显示了一个典型的对话框。如你所见，该对话框包含以下组件：

- 一个图标
- 一条消息
- 一个或多个选项按钮

输入对话框包含一个额外的用户输入的额外组件。这可以是一个用户可以在其中输入任意字符串的文本字段，也可以是一个用户可以从中选择某一项的组合框。

这些对话框的准确布局以及标准消息类型的图标选择取决于可插的外观（pluggable look-and-feel）。

左侧的图标取决于五种消息类型之一：

```
ERROR_MESSAGE
INFORMATION_MESSAGE
WARNING_MESSAGE
QUESTION_MESSAGE
PLAIN_MESSAGE
```

`PLAIN_MESSAGE` 类型没有图标。每个对话框类型也有一个方法让你提供自己的图标作为替代。

对于每种对话框类型，你可以指定一条消息。此消息可以是字符串、图标、用户界面组件或任何其他对象。消息对象的显示方式如下：

| 类型 | 操作 |
| :--- | :--- |
| `String` | 绘制字符串 |
| `Icon` | 显示图标 |
| `Component` | 显示组件 |
| `Object[]` | 显示数组中的所有对象，并堆叠在一起 |
| 任何其他对象 | 应用 `toString()` 并显示生成的字符串 |

当然，提供消息字符串是最常见的情况。提供一个 `Component` 赋予了你极大的灵活性，因为你可以让 `paintComponent` 方法绘制你想要的任何内容。

底部的按钮取决于对话框的类型和选项类型。当调用 `showMessageDialog` 和 `showInputDialog` 时，你只会得到一组标准的按钮（分别是 OK 和 OK/取消）。当调用 `showConfirmDialog` 时，你可以在四种选项类型中选择：

```
DEFAULT_OPTION
YES_NO_OPTION
YES_NO_CANCEL_OPTION
OK_CANCEL_OPTION
```

通过 `showOptionDialog`，你可以指定一组任意的选项。你为选项提供一个对象数组。每个数组元素的渲染方式如下：

| 类型 | 操作 |
| :--- | :--- |
| `String` | 以字符串作为标签创建按钮 |
| `Icon` | 以图标作为标签创建按钮 |
| `Component` | 创建带有组件的按钮 |
| 任何其他对象 | 应用 `toString()` |

这些函数的返回值如下：

| 方法 | 返回值 |
| :--- | :--- |
| `showMessageDialog` | 无 |
| `showConfirmDialog` | 表示所选选项的整数 |
| `showOptionDialog` | 表示所选选项的整数 |
| `showInputDialog` | 用户输入的字符串 |

这听起来有很多选择，但实际上操作很简单。遵循以下步骤：

1. 选择对话框类型（消息、确认、选项或输入）。
2. 选择图标（错误、信息、警告、问题或自定义）。
3. 选择消息（字符串、图标、组件或它们的数组）。
4. 对于确认对话框，选择选项类型（默认、是/否、是/否/取消或确定/取消）。
5. 对于选项对话框，选择选项（字符串、图标或组件）以及默认选项。
6. 对于输入对话框，在文本字段和组合框之间选择。
7. 在 `JOptionPane` API 中定位相应的方法。

例如，假设你想显示图 11.30 中的对话框。该对话框显示消息并询问用户确认或取消。因此，这是一个确认对话框。图标是问题图标。消息是字符串。选项类型是 `OK_CANCEL_OPTION`。这是你进行的调用：

```java
int selection = JOptionPane.showConfirmDialog(parent,
"Message", "Title",
    JOptionPane.OK_CANCEL_OPTION,
    JOptionPane.QUESTION_MESSAGE);
if (selection == JOptionPane.OK_OPTION) . . .
```

**提示：** 消息字符串可以包含换行符（`'\n'`）。此类字符串将多行显示。

# `javax.swing.JOptionPane` 1.2

- `static void showDialog(Component parent, Object message, String title, int messageType, Icon icon)`
- `static void showDialog(Component parent, Object message, String title, int messageType)`
- `static void showDialog(Component parent, Object message)`
- `static void showInternalMessageDialog(Component parent, Object message, String title, int messageType, Icon icon)`
- `static void showInternalMessageDialog(Component parent, Object message, String title, int messageType)`
- `static void showInternalMessageDialog(Component parent, Object message)`
- `static int showConfirmDialog(Component parent, Object message, String title, int messageType, Icon icon)`

显示一个消息对话框或内部消息对话框。（内部对话框完全在它的所有者框架内渲染）。父组件可以为 `null`。在对话框上显示的消息可以是字符串、图标、组件或它们的数组。`messageType` 参数是 `ERROR_MESSAGE`、`INFORMATION_MESSAGE`、`WARNING_MESSAGE`、`QUESTION_MESSAGE` 或 `PLAIN_MESSAGE` 之一。

- `static int showConfirmDialog(Component parent, Object message)`
- `static int showInternalConfirmDialog(Component parent, Object message, String title, int optionType, int messageType, Icon icon)`
- `static int showInternalConfirmDialog(Component parent, Object message, String title, int optionType, int messageType)`
- `static int showInternalConfirmDialog(Component parent, Object message, String title, int optionType)`
- `static int showInternalConfirmDialog(Component parent, Object message)`

显示确认对话框或内部确认对话框。（内部对话框完全渲染在用户的 own内）。返回用户选择的选项（`OK_OPTION`、`CANCEL_OPTION`、`YES_OPTION`、`NO_OPTION` 之一），如果用户关闭了对话框，则返回 `CLOSED_OPTION`。父组件可以为 `null`。在对话框上显示的消息可以是字符串、图标、组件或它们的数组。`messageType` 参数为 `ERROR_MESSAGE`、`INFORMATION_MESSAGE`、`WARNING_MESSAGE`、`QUESTION_MESSAGE` 或 `PLAIN_MESSAGE` 之一，`optionType` 为 `DEFAULT_OPTION`、`YES_NO_OPTION`、`YES_NO_CANCEL_OPTION` 或 `OK_CANCEL_OPTION` 之一。

- `static int showOptionDialog(Component parent, Object message, String title, int optionType,`

```java
int messageType, Icon icon, Object[] options,
Object default)
static int showInternalOptionDialog(Component parent, Object message, String title, int optionType, int messageType, Icon icon, Object[] options, Object default)
```

显示选项对话框或内部选项对话框。（内部对话框完全在其所有者的框架内渲染）。返回用户选择的选项索引，如果用户取消对话框，则返回 `CLOSED_OPTION`。父组件可以为 `null`。在对话框上显示的消息可以是字符串、图标、组件或它们的数组。`messageType` 参数为 `ERROR_MESSAGE`、`INFORMATION_MESSAGE`、`WARNING_MESSAGE`、`QUESTION_MESSAGE` 或 `PLAIN_MESSAGE` 之一，`optionType` 为 `DEFAULT_OPTION`、`YES_NO_OPTION`、`YES_NO_CANCEL_OPTION` 或 `OK_CANCEL_OPTION` 之一。`options` 参数是字符串、图标或组件的数组。

- `static Object showInputDialog(Component parent, Object message, String title, int messageType, Icon icon, Object[] values, Object default)`
- `static String showInputDialog(Component parent, Object message, String title, int messageType)`
- `static String showInputDialog(Component parent, Object message)`
- `static String showInputDialog(Object message)`
- `static String showInputDialog(Component parent, Object message, Object default) 1.4`
- `static String showInputDialog(Object message, Object default) 1.4`
- `static Object showInternalInputDialog(Component parent, Object message, String title, int messageType, Icon icon, Object[] values, Object default)`
- `static String showInternalInputDialog(Component parent, Object message, String title, int messageType)`
- `static String showInternalInputDialog(Component parent, Object message)`

显示输入对话框或内部输入对话框。（内部对话框完全在其所有者的框架内渲染）。返回用户输入的字符串，如果用户取消了对话框，则返回 `null`。对话框上显示的父组件可以是字符串、图标、组件或它们的数组。`messageType` 参数为 `ERROR_MESSAGE`、`INFORMATION_MESSAGE`、`WARNING_MESSAGE`、`QUESTION_MESSAGE` 或 `PLAIN_MESSAGE` 之一。

## 11.8.2. 创建对话框

在上一节中，你学习了如何使用 `JOptionPane` 类来显示简单的对话框。在本节中，你将看到如何手动创建这样一个对话框。

图 11.31 显示了一个典型的模态对话框——一个当用户点击“关于（About）”按钮时显示的程序信息框。

![](img/240dbf1b84e081687f1e252bd386c684_878_0.png)

**图 11.31:** 一个“关于”对话框

要实现对话框，你需要扩展 `JDialog` 类。这与为应用程序的主窗口扩展 `JFrame` 的过程本质上相同。具体步骤：

1. 在你的对话框构造函数中，调用父类 `JDialog` 的构造函数。
2. 添加对话框的用户界面组件。
3. 添加事件处理器。
4. 设置对话框的大小。

当你调用父类构造函数时，需要提供所有者框架、对话框标题以及模态性（modality）。

所有者框架控制对话框的显示位置。你可以提供 `null` 作为所有者；此时，对话框将由隐藏框架所有。

模态性指定了在对话框显示期间应用程序的哪些窗口会被阻塞。非模态对话框（modeless）不阻塞其他窗口。模态对话框（modal）会阻塞应用程序的所有其他窗口（对话框的子窗口除外）。对于用户可以随时访问的工具箱，可以使用非模态对话框。如果你想强制用户在继续之前提供必要信息，则可以使用模态对话框。

以下是对话框的代码：

```java
public AboutDialog extends JDialog {
    public AboutDialog(JFrame owner) {
        super(owner, "About DialogTest", true);
        add(new JLabel("<html><h1><i>Core Java/</i></html><hr>By Cay Horstmann</html>"),
            BorderLayout.CENTER);
        var panel = new JPanel();
        var ok = new JButton("OK");
        ok.addActionListener(_ -> setVisible(false));
        add(panel, BorderLayout.SOUTH);
        setSize(250, 150);
    }
}
```

## 11.8.3. 数据交换

弹出对话框的最常见目的是从用户获取信息。你已经看到过创建一个对话框对象是多么简单：给它初始数据并调用 `setVisible(true)` 即可在屏幕上显示对话框。现在，让我们来看如何在对话框中进行数据传输。

考虑图 11.32 中的对话框，它可以用于获取用户名和密码以连接到某些在线服务。

![](img/240dbf1b84e081687f1e252bd386c684_883_0.png)

图 11.32：密码对话框

你的对话框应该提供设置默认数据的方法。例如，示例程序中的 `PasswordChooser` 类有一个 `setUser` 方法，用于将默认值放入相应的字段中：

```java
public void setUser(User u) {
    username.setText(u.getName());
}
```

一旦设置了默认值（如果需要），通过调用 `setVisible(true)` 显示对话框。此时对话框已显示。

用户随后填写信息并点击 OK 或 Cancel 按钮。这两个按钮的事件处理程序都会调用 `setVisible(false)`，这将终止对 `setVisible(true)` 的调用。或者，用户也可以关闭对话框。如果你没有为对话框安装窗口监听器，则应用默认的窗口关闭操作：对话框变为不可见，这也会终止对 `setVisible(true)` 的调用。

重要的问题是，`setVisible(true)` 的调用会阻塞，直到用户关闭了对话框。这使得实现模态对话框变得简单。

你想知道用户是接受了还是取消了对话框。我们的示例代码在显示对话框之前将 `ok` 标志设为 `false`。只有 OK 按钮的事件处理程序会将 `ok` 标志设为 `true`；这就是你从对话框检索用户输入的方法。

> 注意：从非模态对话框传输数据并不简单。当显示非模态对话框时，`setVisible(true)` 的调用不会阻塞，程序会在对话框显示期间继续运行。如果用户在非模态对话框上选择了项目然后点击 OK，则对话框需要向程序中的某些监听器发送事件。

示例程序包含了另一个有用的改进。

当你构造 `JDialog` 对象时，需要指定所有者帧（owner frame）。然而，通常你希望用不同的所有者帧显示同一个对话框。最好在你准备显示对话框时选择所有者帧，而不是在构造 `PasswordChooser` 对象时。

技巧是让 `PasswordChooser` 继承 `JPanel` 而不是 `JDialog`。在 `showDialog` 方法中动态构建 `JDialog` 对象：



```java
public boolean showDialog(Frame owner, String title) {
    ok = false;

    if (dialog == null || dialog.getOwner() != owner) {
        dialog = new JDialog(owner, true);
        dialog.add(this);
        dialog.pack();
    }

    dialog.setTitle(title);
    dialog.setVisible(true);
    return ok;
}
```

注意`owner`等于`null`是安全的。

你可以做得更好。有时所有者帧并不可直接可用。从任何组件计算它是很容易的，如下：

```java
Frame owner;
if (parent instanceof Frame)
    owner = (Frame) parent;
else
    owner = (Frame) SwingUtilities.getAncestorOfClass(Frame.class, parent);
```

我们在示例程序使用了这种增强方法。`JOptionPane`也使用了这种机制。

许多对话框有一个默认按钮，如果用户按下触发键（在大多数外观和感觉实现中为 Enter 键），该按钮会被自动选中。默认按钮会被特别标记，通常有一个加粗的轮廓。

在对话框的根面板中设置默认按钮：

```java
dialog.getRootPane().setDefaultButton(okButton);
```

如果你遵循在面板（panel）中布局对话框的建议，那么你必须小心，在将面板封装进对话框之后再设置默认按钮。面板对话框本身没有根面板。

列表 11.13 是程序的帧类，说明了流入和流出对话框的数据流。列表 11.14 显示了对话框类。

## 列表 11.13

`v2ch11/dataExchange/DataExchangeFrame.java`

```java
package v2ch11.dataExchange;
import java.desktop.*;

/**
 * 一个带有菜单的帧，其 File->Connect 操作会显示
 * 密码对话框。
 */
public class DataExchangeFrame extends JFrame {
    public static final int TEXT_ROWS = 20;
    public static final int TEXT_COLUMNS = 40;
    private PasswordChooser dialog = null;
    private JTextArea textArea;

    public DataExchangeFrame() {
        // 构建一个 File 菜单

        var mbar = new JMenuBar();
        setJMenuBar(mbar);
        var fileMenu = new JMenu("File");
        mbar.add(fileMenu);

        // 添加 Connect 和 Exit 项

        var connectItem = new JMenuItem("Connect");
        connectItem.addActionListener(new ConnectAction());
        fileMenu.add(connectItem);

        // Exit 项退出程序

        var exitItem = new JMenuItem("Exit");
        exitItem.addActionListener(_ -> System.exit(0));
        fileMenu.add(exitItem);

        textArea = new JTextArea(TEXT_ROWS, TEXT_COLUMNS);
        add(new JScrollPane(textArea), BorderLayout.CENTER);

        dialog = new PasswordChooser();
        add(dialog, BorderLayout.CENTER);
    }
}

class ConnectAction implements ActionListener {
    public void actionPerformed(ActionEvent event) {
        if (dialog == null) {
            dialog = new PasswordChooser();
        }
        dialog.setVisible(true);
    }
}
```

## 列表 11.14

`v2ch11/dataExchange/PasswordChooser.java`

```java
package v2ch11.dataExchange;
import java.desktop.*;

/**
 * 在对话框内显示的密码选择器。
 */
public class PasswordChooser extends JPanel {
    private JTextField username;
    private JPasswordField password;
    private JButton okButton;
    private boolean ok;
    private JDialog dialog;

    public PasswordChooser() {
        // 构建一个包含用户名和密码字段的面板
        setLayout(new GridLayout(2, 2));
        add(new JLabel("User name:"));
        username = new JTextField();
        add(new JLabel("Password:"));
        password = new JPasswordField();
        
        // 创建终止对话框的 Ok 和 Cancel 按钮
        okButton = new JButton("Ok");
        okButton.addActionListener(_ -> {
            ok = true;
            dialog.setVisible(false);
        });

        var cancelButton = new JButton("Cancel");
        cancelButton.addActionListener(_ -> {
            dialog.setVisible(false);
        });

        // 将按钮添加到南部边界
        var buttonPanel = new JPanel();
        buttonPanel.add(okButton);
        buttonPanel.add(cancelButton);
        add(buttonPanel, BorderLayout.SOUTH);
    }

    /**
    * 设置对话框默认值。
    * @param u 默认用户信息
    */
    public void setUser(User u) {
        username.setText(u.getName());
    }

    /**
    * 获取对话框内容。
    * @return 表示对话框状态的 User 对象
    */
    public User getUser() {
        return new User(username.getText(),
        new String(password.getPassword()));
    }

    /**
    * 在对话框中显示选择器面板。
    * @param parent 所有者帧中的组件或 null
    * @param title 对话框标题
    */
    public boolean showDialog(Component parent, String title) {
        ok = false;
        // 定位所有者帧
        Frame owner = (Frame)SwingUtilities.getAncestorOfClass(Frame.class, parent);
        // 如果是第一次，或者所有者已更改，则创建对话框
        if (dialog == null || dialog.getOwner() != owner) {
            dialog = new JDialog(owner, true);
            dialog.add(this);
            dialog.getRootPane().setDefaultButton(okButton);
            dialog.pack();
        }
        // 设置标题并显示对话框
        dialog.setTitle(title);
        dialog.setVisible(true);
        return ok;
    }
}
```

`javax.swing.JComponent 1.2`

- `JRootPane getRootPane()`

  获取包含此组件的根面板，如果此组件没有具有根面板的祖先，则返回 `null`。

`javax.swing.JRootPane 1.2`

- `void setDefaultButton(JButton button)`

  设置此根面板的默认按钮。如需停用默认按钮，请传入 `null`参数调用此方法。

`javax.swing.JButton 1.2`

- `boolean isDefaultButton()`

  如果此按钮是其根面板的默认按钮，则返回 `true`。

## 11.8.4. 文件对话框

在应用程序中，你通常希望能够打开和保存文件。编写一个能够显示文件和目录并允许用户浏览文件系统的良好的文件对话框是困难的，而且你不想重复造轮子。幸运的是，Swing 提供了一个`JFileChooser`类，它允许你显示一个与大多数原生应用程序类似的文件对话框。`JFileChooser`对话框总是模态的。注意`JFileChooser`类不是`JDialog`的子类。不要调用`setVisible(true)`，而应调用`showOpenDialog`来显示打开文件的对话框，或调用`showSaveDialog`来显示保存文件的对话框。接受文件的按钮将自动标记为“打开”或“保存”。你也可以通过`showDialog`方法提供自己的按钮标签。图 11.33 显示了文件选择对话框的示例。

![](img/240dbf1b84e081687f1e252bd386c684_892_0.png)

图 11.33：文件选择对话框

以下是建立文件对话框并获取用户从中选择内容的步骤：

1. 创建一个`JFileChooser`对象。与`JDialog`类的构造函数不同，你不需要提供父组件。这允许你在多个帧中重用一个文件选择对话框。

   例如：

   ```java
   var chooser = new JFileChooser();
   ```

   > **提示：** 重用文件选择器对象是一个好主意，因为`JFileChooser`的构造函数可能会慢，特别是在 Windows 上用户有许多映射的网络驱动器时。

2. 通过调用`setCurrentDirectory`方法设置目录。

   例如，要使用当前工作目录：

   ```java
   chooser.setCurrentDirectory(new File("."));
   ```

   你需要提供一个`File`对象。`File`对象在第 2 章中进行了详细解释。你现在只需要知道构造函数`File(String filename)`会将文件或目录名转换为`File`对象。

3. 如果你有一个希望用户选择的默认文件名，可以通过`setSelectedFile`方法提供它：

   ```java
   chooser.setSelectedFile(new File(filename));
   ```

4. 要允许用户在对话框中选择多个文件，请调用`setMultiSelectionEnabled`方法。当然这完全是可选的，而且并不常见。

   ```java
   chooser.setMultiSelectionEnabled(true);
   ```

5. 如果你想将对话框中显示的文件限制为特定类型（例如，所有扩展名为`.gif`的文件），你需要设置一个文件过滤器。我们将在本节稍后的部分讨论文件过滤器。

6. 默认情况下，用户使用文件选择器只能选择文件。如果你想让用户选择目录，请使用`setFileSelectionMode`方法。传入`JFileChooser.FILES_ONLY`（默认值）、`JFileChooser.DIRECTORIES_ONLY`或`JFileChooser.FILES_AND_DIRECTORIES`。

7. 通过调用`showInputDialog`或`showSaveDialog`方法显示对话框。在这些调用中你必须提供父组件：

   ```java
   int result = chooser.showOpenDialog(parent);
   ```

   或者：

   ```java
   int result = chooser.showSaveDialog(parent);
   ```

   这些调用之间的唯一区别是“确认按钮”的标签——即用户点击以完成文件选择的按钮。你也可以调用`showDialog`方法并为确认按钮传递一个显式文本：

   ```java
   int result = chooser.showDialog(parent, "Select");
   ```

   这些调用只有在用户确认、取消或驳回文件对话框后才会返回。返回值是`JFileChooser.APPROVE_OPTION`、`JFileChooser.CANCEL_OPTION`或`JFileChooser.ERROR_OPTION`。

8. 使用`getSelectedFile()`或`getSelectedFiles()`方法获取选中的文件或多个文件。这些方法返回单个`File`对象或一个`File`对象数组。如果你只需要文件对象的名称，调用其`getPath`方法。例如：

   ```java
   String filename = chooser.getSelectedFile().getPath();
   ```

在大多数情况下，这些步骤都是简单的。使用文件对话框的主要困难在于指定用户应该从中选择的文件子集。例如，假设用户应该选择一个 GIF 图像文件。那么，文件选择器应该只显示扩展名为`.gif`的文件。它还应该给用户提供某种反馈，说明显示的文件属于特定类别，例如“GIF Images”。但情况可能更复杂。如果用户应该选择一个 JPEG 图像文件，扩展可以是`.jpg`或`.jpeg`。与其用一种方式来编码这些复杂性，文件选择器的设计者提供了一种更优雅的机制：要限制显示的文件，提供一个扩展`javax.swing.filechooser.ImageFilter`类的对象。文件选择器会将每个文件传递给文件过滤器，并只显示过滤器接受的文件。

在编写时，提供了两个这样的子类：接受所有文件的默认过滤器，以及一个接受给定扩展名的过滤器。然而，编写临时文件过滤器很容易的。只需实现`Filter`基类的两个抽象方法即可：

```java
public boolean accept(File f);
public String getDescription();
```

第一个方法测试文件是否应该被接受。第二个方法返回文件类型的描述，可以显示在文件选择对话框中。

> **注意：** `java.io`包中一个不相关的`FileFilter`接口只有一个方法，`boolean accept(File f)`。它被`Class`类的`listFiles`方法用于列出目录中的文件。我不知道为什么 Swing 的设计者没有扩展这个接口——也许 Java 类库在 1998 年那个早时候就已经变得如此复杂，以至于他们不再了解所有的标准类和接口了。

如果你同时导入了`java.io`和`javax.swing`，你需要解决这两个同名类型之间的命名冲突。

示例程序包含一个简单的文件视图类。每当文件匹配文件过滤器时，该类就会显示特定的图标。我们使用它为所有图像文件显示调色板图标。

```java
class FileIconView extends FileView {
    private FileFilter filter;
    private Icon icon;

    public FileIconView(FileFilter aFilter, Icon aIcon) {
        filter = aFilter;
        icon = aIcon;
    }

    public Icon getIcon(File f) {
        if (!f.isDirectory() && filter.accept(f))
            return icon;
        else return null;
    }
}
```

使用`setFileView`方法将此文件视图安装到你的文件选择器中：



```java
chooser.setFileView(new FileIconView(filter, new ImageIcon("palette.gif")));
```

文件选择器随后将在所有通过过滤器的文件旁边显示调色板图标，并使用默认文件视图显示所有其他文件。自然地，我们使用了与在文件选择器中设置相同的过滤器。

最后，你可以通过添加辅助组件来自定义文件对话框。例如，图 11.34 显示了文件列表旁边的预览辅助组件。该组件显示当前选中文件的缩略图视图。

![](img/240dbf1b84e081687f1e252bd386c684_900_0.png)

图 11.34：带有预览辅助组件的文件对话框

辅助可以是任何 Swing 组件。在我们的情况下，我们扩展了 `JLabel` 类并将其图标设置为图形图像的缩放副本：

```java
class ImagePreview extends JLabel {
    public ImagePreview(JFileChooser chooser) {
        setPreferredSize(new Dimension(100,
        setBorder(BorderFactory.createEtchedBorder()));
    }

    public void loadImage(File f) {
        var icon = new ImageIcon(f.getPath());
        if(icon.getIconWidth() > getWidth()) {
          icon = new ImageIcon(icon.getImage()).getScaledInstance(
            getWidth(), -1,
            Image.SCALE_DEFAULT));
          setIcon(icon);
          repaint();
        }
    }
}
```

这里只有一个挑战。我们希望在用户选择不同的文件时更新预览图像。文件选择器使用“JavaBeans 机制，当其任何属性发生变化时通知感兴趣的监听器”。选中的文件是一个你可以通过安装 `PropertyChangeListener` 来监控的属性。以下是你需要捕获通知的代码：

```java
chooser.addPropertyChangeListener(event -> {
  if (event.getPropertyName() == JFileChooser.SELECTED_FILE_CHANGED_PROPERTY) {
    var newFile = (File) event.getNewValue();
    // update the accessory
  }
});
```

## `javax.swing.JFileChooser` 1.2

| 方法 | 说明 |
|---|---|
| `JFileChooser()` | 创建一个文件选择器对话框，可以用于多个帧。 |
| `void setCurrentDirectory(File dir)` | 设置文件对话框的初始目录。 |
| `void setSelectedFile(File file)` |  |
| `void setSelectedFiles(File[] file)` | 设置文件对话框的默认选择文件。 |
| `void setMultiSelectionEnabled(boolean b)` | 设置或清除多选模式。 |
| `void setFileSelectionMode(int mode)` | 允许用户仅选择文件（默认）、目录或同时选择文件和目录。`mode` 参数是 `JFileChooser.FILES_ONLY`、`FileChooser.DIRECTORIES_ONLY` 和 `JFileChooser.FILES_AND_DIRECTORIES` 之一。 |
| `int showInputDialog(Component parent)` |  |
| `int showSaveDialog(Component parent)` |  |
| `int showDialog(Component parent, String approveButtonText)` | 显示一个对话框，其中确认按钮标记为“打开”、“保存”或 `approveButtonText` 字符串。返回 `APPROVE_OPTION`、`CANCEL_OPTION`（如果用户选择了取消按钮或关闭了对话框）或 `ERROR_OPTION`（如果发生了错误）。 |
| `File getSelectedFile()` |  |
| `File[] getSelectedFiles()` | 显示用户选择的文件或文件（如果用户没有选择任何文件则返回 `null`）。 |
| `void setFileFilter(FileFilter)` | 设置文件对话框的掩码。所有 `filter.accept` 返回 `true` 的文件都将显示。同时，将过滤器添加到可选过滤器列表中。 |
| `void addChoosableFileFilter(FileFilter)` | 将过滤器添加到可选过滤器列表中。 |
| `void setAcceptAllFileFilterUsed(boolean b)` | 在过滤器组合框中包含或抑制“所有文件”过滤器。 |
| `void resetChoosableFileFilters()` | 清空可选过滤器列表。除非显式抑制，否则只保留“所有文件”过滤器。 |
| `void setLayerView(LayerView view)` | 设置视图以提供有关文件选择器显示的文件的信息。 |
| `void setAccessory(JComponent component)` | 设置辅助组件。 |

## `javax.swing.filechooser.FileFilter` 1.2

| 方法 | 说明 |
|---|---|
| `boolean accept(File f)` | 如果文件选择器应该显示此文件，则返回 `true`。 |
| `String getDescription()` | 返回此文件过滤器的描述——例如，“图像文件（*.gif,*.jpeg）”。 |

## `javax.swing.filechooser.FileNameExtensionFilter` 6

| 方法 | 说明 |
|---|---|
| `FileNameExtensionFilter(String description, String... extensions)` | 根据给定描述构造过滤器。 |

## `javax.swing.filechooser.FileView` 1.2

| 方法 | 说明 |
|---|---|
| `String getName(File f)` | 返回 `f` 的名称，或返回 `null`。 |
| `String getDescription(File f)` | 返回文件 `f` 的描述，或返回 `null`。 |
| `String getTypeDescription(File f)` | 返回 `f` 类型的人类可读描述，或返回 `null`。 |
| `Icon getIcon(File f)` | 返回 `f` 的图标，或返回 `null`。 |
| `Boolean isTraversable(File f)` | 如果 `f` 是用户可以打开的目录，则返回 `Boolean.TRUE`。如果目录是复合文档，此方法可能会返回 `Boolean.FALSE`。 |

## 表 12.1：一个简单的表格

| 行星 | 半径 | 卫星 | 气态行星 | 颜色 |
|---|---:|---:|---|---|
| 水星 | 2440.0 | 0 | `false` | `java.awt.C...` |
| 金星 | 6052.0 | 0 | `false` | `java.awt.C...` |
| 地球 | 6378.0 | 1 | `false` | `java.awt.C...` |
| 火星 | 3397.0 | 2 | `false` | `java.awt.C...` |
| 木星 | 71492.0 | 16 | `true` | `java.awt.C...` |
| 土星 | 60268.0 | 18 | `true` | `java.awt.C...` |
| 天王星 | 25559.0 | 17 | `true` | `java.awt.C...` |
| 海王星 | 24276.0 | 18 | `true` | `java.awt.C...` |

如你在代码列表 12.1 所示，表格数据存储在 `Object` 类型的二维数组中：

```java
Object[] cells = {
  { "Mercury", 2440.0, 0, false, Color.YELLOW },
  { "Venus", 6052.0, 0, false, Color.YELLOW };
```

> 注意：这里，我们利用了自动装箱。第二、第三和第四列的条目会自动转换为 `Double`、`Integer` 和 `Boolean` 类型的对象。

表格简单地调用每个对象的 `toString` 方法来显示它。这就是为什么颜色以 `java.awt.Color[r= . ..g= . ..b= .]` 显示的形式。

在单独的字符串数组中提供列名：

```java
String[] columnNames = { "Planet", "Radius", "Moons", "Gaseous", "Color" };
```

然后，从单元格和列名数组构造表格：

```java
var table = new JTable(cells, columnNames);
```

你可以用通常的方法添加滚动条——通过将表格包装在 `JScrollPane` 中：

```java
var pane = new JScrollPane(table);
```

当你滚动表格时，表头不会滚出视图。

接下来，点击其中一个列头并将其向左或向右拖动。观察整个列是如何分离出去的（见图 12.2）。你可以将其放置在不同的位置。这只会重新排列视图中的列。数据模型不受影响。

## 图 12.2：移动列

要调整列的大小，只需将光标置于两列之间，直到光标形状变为箭头。然后，将列边界拖动到所需位置（见[图 12.3](#)）。

![](img/240dbf1b84e081687f1e252bd386c684_907_0.png)

## 图 12.3：调整列大小

![](img/240dbf1b84e081687f1e252bd386c684_907_1.png)

用户可以通过点击行中的任何位置来选择行。选中的行会被高亮显示；稍后你将看到如何获取选择事件。用户还可以通过点击单元格并输入内容来编辑表格。然而，在这个代码示例中，编辑不会更改底层数据。在你的程序中，你应该要么使单元格变为不可编辑，要么处理编辑事件并更新你的模型。我们将在本节稍后讨论这些主题。

最后，点击一个列头。行将自动排序。再次点击，排序顺序将反转。这种行为通过以下调用激活：

```java
table.setAutoCreateRowSorter(true);
```

你可以通过以下调用打印表格：

```java
table.print();
```

> 注意：如果你没有将表格放入滚动面板中，你需要显式地添加表头：

```java
add(table.getTableHeader(), BorderLayout.NORTH);
```

## 代码列表 12.1 v2ch12/table/TableDemo.java

```java
1 package v2ch12.table;
2 import module java.desktop;
3 /**
4  * 此程序演示了如何显示简单的表格。
5  */
6 class TableDemo {
7  void main() {
8    EventEventQueue.invokeLater(() -> {
9      var frame = new PlanetTableFrame();
10     frame.setTitle("TableTest");
11     frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
12     frame.setVisible(true);
13   });
14 }
15 }
16
17 /**
18 * 此框架包含一个包含行星数据的表格。 */
19 class PlanetTableFrame extends JFrame {
20   String[] columnNames = { "Planet", "Radius", "Moons", "Gaseous", "Color" };
21   Object[][] cells = { { "Mercury", 2440.0, 0, false, Color.YELLOW },
22     { "Earth", 6371.0, 1, false, Color.BLUE },
23     { "Jupiter", 71492.0, 16, true, Color.ORANGE },
24     { "Saturn", 60268.0, 18, true, Color.ORANGE },
25     { "Uranus", 25559.0, 17, true, Color.BLUE },
26     { "Neptune", 24276.0, 18, true, Color.BLUE },
27     { "Pluto", 2378.0, 1, false, Color.BLACK } };
28   public PlanetTable() {
29     var table = new JTable(cells, columnNames);
30     table.setAutoCreateRowSorter(true);
31     add(new JScrollPane(table), BorderLayout.CENTER);
32     var button = new JButton("Print");
33     button.addActionListener(() -> {
34       try {
35         table.print();
36       } catch (SQLException e) {
37         e.printStackTrace();
38     });
39     var panel = new JPanel();
40   }
```

## `javax.swing.JTable`

- `JTable(Object[][] cells, Object[] columnNames)` 创建一个表格。
- `print()` 显示表格并打印表格。
- `setAutoCreateRowSorter(boolean)` 默认排序器每当模型更改时都会自动设置。
- `fillsViewport(boolean)` 表格始终填充视口。

## 1.2. 模型

在前面的示例中，表格数据存储在二维数组中。然而，你不应该将数据倾入数组，而是考虑实现自己的模型。`AbstractTableModel` 特别简单，因为它实现了大部分所需的方法。你只需要提供三个方法：

```java
public intRowCount();

public int getColumnCount();

public Object getValueAt(int row, int column);
```

实现 `getValueAt` 有方法。如果你想显示 `ResultSet` 的内容，只需提供此方法：

```java
public Object getValueAt(int r, int c) {
  try {
    return resultSet.getObject(c + 1);
  } catch (SQLException e) {
    e.printStackTrace();
    return null;
  }
}
```

我们的示例程序更加简单。我们构造的表格显示了不同利率场景下的计算值（见图 12.4）。

## 投资表格

| | 5% | 6% | 7% | 8% | 9% | 10% |
|---|---:|---:|---:|---:|---:|---:|
| 100000 | 100000.00 | 100000.00 | 100000.00 | 100000.00 | 100000.00 | 100000.00 |
| 105000.00 | 106000.00 | 107000.00 | 108000.00 | 109000.00 | 110000.00 |  |
| 115762.50 | 119101.60 | 125404.50 | 125971.20 | 129502.90 | 133100.00 |  |
| 121550.63 | 126247.70 | 134025.37 | 136048.90 | 141518.16 | 146410.00 |  |
| 127652.35 | 132365.35 | 140252.67 | 145168.31 | 149850.40 | 156133.00 |  |
| 134009.56 | 148151.91 | 150073.48 | 155867.41 | 167710.01 | 177159.10 |  |
| 140710.04 | 150263.05 | 160538.15 | 171382.43 | 182803.91 | 194871.71 |  |

* 此程序展示了如何从表格模型构建表格。

```java
class InvestmentTable {
    void main() {
        EventQueue.invokeLater(() -> {
            var frame = new InvestmentTableFrame();
            frame.setTitle("InvestmentTable");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}
```

```java
/*
 * 此框架包含投资表格。
 */
```



```java
class InvestmentTableFrame extends JFrame {

    public InvestmentTableFrame() {
        var model = new InvestmentTableModel(30, 5, 10);
        var table = new JTable(model);
        add(new JScrollPane(table));
    }
}
```

```java
/*
 * 该模型在每次请求时计算单元格条目。表格显示了在不同利率下，投资在若干年的增长情况。
 */

class InvestmentTableModel extends AbstractTableModel {

    private static double INITIAL_BALANCE = 100000.0;
    private int years;
    private int minRate;
    private int maxRate;

    /*
     * 构建一个投资表格模型。
     *
     * @param y 年份数
     * @param r1 统计的最低利率
     * @param r2 统计的最高利率
     */

    public InvestmentTableModel(int y, int r1, int r2) {
        years = y;
        minRate = r1;
        maxRate = r2;
    }

    public int getRowCount() {
        return years;
    }

    public int getColumnCount() {
        return maxRate - minRate + 1;
    }

    public Object getValueAt(int r, int c) {
        double rate = (c + minRate) / 100.0;
        int periods = r;
        double futureBalance = INITIAL_BALANCE + Math.pow(1 + rate, periods);
        return String.format("%.2f", futureBalance);
    }

    public String getColumnName(int c) {
        return (c + minRate) + "%";
    }
}
```

# `javax.swing.table.TableModel` 1.2

- `int getRowCount()`
- `int getColumnCount()`

  获取表格模型的行数和列数。

- `Object getValueAt(int row, int column)`

  获取指定行和列的值。

- `void setValue(Object newValue, int row, int column)`

  在指定的行和列处设置新值。

- `boolean isCellEditable(int row, int column)`

  如果指定行和列的单元格可编辑，则返回 `true`。

- `String getColumnName(int column)`

  获取列标题。

## 12.2. 操作行和列

在接下来的小节中，你将看到如何操作表格中的行和列。在阅读这些材料时，请记住 Swing 表格是相当不对称的——你对行和列可以的操作是不同的。表格组件经过优化，用于显示具有相同结构的信息行（例如数据库查询的结果），而不是任意的二维对象网格。你将在整个小节中看到这种非对称性。

### 12.2.1. 列类

在接一个示例中，我们再次显示我们的行星数据，但这次我们想为表格提供更多关于列类型的信息。这是通过定义表格模型的方法 `Class<?> getColumnClass(int columnIndex)` 来实现的，该方法返回描述列类型的类。

`JTable` 类使用这些信息为该类提供适当的渲染器。表格 12.1 显示了默认渲染动作。

**表格 12.1：默认渲染动作**

| 类型 | 渲染为 |
| :--- | :--- |
| `Boolean` | 复选框 |
| `Icon` | 图片 |
| `Object` | 字符串 |

你可以在图 12.5 中看到复选框和图片。（感谢 Jim Evins 提供行星图片！）

| 行 | us | Gaseous | Image |
| --- | --- | --- | --- |
| 列 | 52 | 0 | `java.awt.Color[r=255,g=255,b=0]` |
| 地球 | 6,378 | 1 | `java.awt.Color[r=0,g=0,b=255]` |
| 火星 | 3,397 | 2 | `java.awt.Color[r=255,g=0,b=0]` |
| 木星 | 71,492 | 16 | `java.awt.Color[r=255,g=0,b=200]` |
| 土星 | 60,268 | 18 | `java.awt.Color[r=255,g=200,b=0]` |

**图 12.5：** 带有行星数据的表格

要渲染其他内容，你可以安装自定义渲染器——参见第 12.3 节。

### 12.2.2. 访问表格列

`Table` 类在 `TableColumn` 类型的对象中存储表格列的信息。`TableColumnModel` 管理这些列。（图 12.6 显示了最重要的表格类之间的关系）。如果你不想动态插入或删除列，你就不会经常使用列模型。列模型最常见的用法仅仅是获取一个 `TableColumn` 对象：

```java
int columnIndex = ...;
TableColumn column = table.getColumnModel().getColumn(columnIndex);
```

### 12.2.3. 列的缩放

`TableColumn` 类提供了对缩放的控制。可以通过以下方法设置首选宽度、最小宽度和最大宽度：

```java
void setPreferredWidth(int width)

void setMinWidth(int width)

void setMaxWidth(int width)
```

这些信息被表格组件用于允许用户缩放列。使用方法：

```java
void setResizable(boolean resizable)
```

**表格 12.2：缩放模式**

| 模式 | 行为 |
| --- | --- |
| `AUTO_SIZE_OFF` | 不缩放列；更改宽度。 |
| `AUTO_SIZE_NEXT_COLUMN` | 仅缩放下一列。 |
| `AUTO_SIZE_SUBSEQUENT_COLUMNS` | 等比例缩放所有列。 |
| `AUTO_SIZE_LAST_COLUMN` | 仅缩放最后一列。 |

### 12.2.4. 行的缩放

行高由 `JTable` 直接管理。如果单元格比默认高，你可能需要设置行高：

```java
void setRowHeight(height)
```

默认情况下，所有行的高度相同。你可以通过方法更改行边距：

```java
void setRowMargin(margin)
```

## 12.2.5. 选择行、列和单元格

根据选择模式，你可以选择行、列或单个单元格。默认启用了行选择。点击单元格会选择整行（见图 12.5）。要禁用行选择，调用：

```java
table.setRowAllowed(false);
```

当启用行选择时，你可以控制用户选择单行、连续行或一组行。你需要获取选择模型并使用其 `setMode` 方法：

```java
table.getModel().setSelectionMode(mode);
```

在这里，`mode` 是三个值之一：

- `ListSelectionModel.SINGLE_SELECTION`
- `ListSelectionModel.SINGLE_INTERVAL_SELECTION`
- `ListSelectionModel.MULTIPLE_INTERVAL_SELECTION`

列选择默认是禁用的。你可以通过调用开启：

```java
table.setColumnAllowed(true);
```

同时行和列选择相当于启用单元格选择。用户选择单元格范围（见图 12.7）。你也可以通过调用启用该设置：

```java
table.setCellSelectionEnabled(true);
```

# `TableColumnTest`

| 行星 | 半径 | 卫星 | 气态 | 颜色 | 图片 |
| --- | --- | --- | --- | --- | --- |
| 火星 | 3,397 | 2 | | `java.awt.Color[r=255,g=0,b=0]` | ![image] |
| 木星 | 71,492 | 16 | | `java.awt.Color[r=255,g=0,b=200]` | ![image] |
| 土星 | 60,268 | 18 | | `java.awt.Color[r=255,g=200,b=0]` | ![image] |
| 天王星 | 25,559 | 17 | | `java.awt.Color[r=0,g=0,b=255]` | ![image] |

**图 12.7：** 选择单元格范围

运行列表 12.3 中的程序观察单元格选择的操作。在选择菜单中启用行、列或单元格选择，观察选择行为的变化。

你可以通过调用 `getSelectedRows` 和 `getSelectedColumns` 方法确定哪些行和列被选中了。这两个方法都返回一个包含选中索引的 `int` 数组。注意索引值是相对于视图的，而不是底层的表格模型。尝试选择行和列，拖动到不同位置并点击列头进行排序。使用“打印选择”菜单项查看哪些行和列被报告为选中。

如果你需要将表格索引值转换为模型索引值，请使用 `JTable` 的方法 `convertRowToIndexModel` 和 `convertColumnIndexToModel`。

## 12.2.6. 排序行

正如我们在第一个表格示例所示，只需通过调用 `createRowSorter` 方法即可为 `JTable` 添加排序。然而，为了对排序行为进行更细粒度的控制，可以向 `JTable` 安装一个 `TableSorter<M>` 对象并对其进行自定义。类型参数 `M` 表示表格模型；它不是 `TableModel` 接口的子类型。

```java
var sorter = new TableSorter<TableModel>(model);
sorter.setRowSorter(sorter);
```

某些列不应该是可排序的，例如我们行星数据中的图像列。通过调用关闭排序：

```java
sorter.setSortable(IMAGE_COLUMN, false);
```

为每一列安装自定义的比较器。在示例中，我们将对 `Color` 列中的颜色进行排序，优先考虑蓝色和绿色而不是红色。当你点击 `Color` 时，你会看到蓝色行星移动到表格底部。可以通过以下代码实现：

```java
sorter.setComparator(COLUMN, new Comparator<Color>() {

    public int compare(Color c1, Color c2) {
        int d = c1.getBlue() - c2.getBlue();
        if (d != 0) return d;

        d = c1.getGreen() - c2.getGreen();
        if (d != 0) return d;

        return c1.getRed() - c2.getRed();
    }

});
```

如果你没有为列指定比较器，排序顺序确定如下：

1. 如果类是 `String`，则使用 `Collator` 返回的默认排序器（coll）。它以适用于当前区域的方式对字符串进行排序。（有关区域和排序器的更多信息，请参见第 7 章）。
2. 如果类实现了 `Comparable`，则使用它的 `compareTo` 方法。
3. 如果排序设置了 `TableStringConverter`，则使用转换器的 `toString` 方法返回的字符串并配合默认排序器进行排序。如果你想使用这种方法，可以这样定义转换器：

```java
sorter.setStringConverter(new TableStringConverter() {

    public String toString(TableModel model, int row, int column) {
        Object value = model.getValueAt(row, column);

        // 将 value 转换为字符串并返回
    }

});
```

否则，对单元格值调用 `toString` 方法并使用默认排序器进行排序。

## 12.2.7. 过滤行

除了排序行，`TableRowSorter` 还可以选择性地隐藏行——这一过程被称为过滤。要激活过滤，请设置 `RowFilter`。例如，要包含至少有一个卫星的所有行，调用：

```java
sorter.setRowFilter(RowFilter.numberFilter(ComparisonType.NOT_EQUAL, 0, MOONS_COLUMN));
```

在这里，我们使用预定义的过滤器。要构造数字过滤器，需要提供：

- 比较类型（`EQUAL`、`NOT_EQUAL`、`AFTER` 或 `BEFORE` 中的之一）。
- 子对象（例如 `Integer` 或 `Double`）。只有与 `Number` 对象具有相同类的对象会被考虑。
- 零或多个列索引值。如果没有提供索引值，则将搜索所有列。

静态的 `RowFilter.dateFilter` 以相同的方式构造过滤器；你需要提供 `Date` 对象而不是 `Number` 对象。

最后，静态的 `RowFilter.regexFilter` 为匹配正则表达式的字符串构造过滤器。例如：

```java
sorter.setRowFilter(RowFilter.regexFilter(".*[s$", PLANET_COLUMN));
```

只显示名称不以 "s" 结尾的行星。（有关正则表达式的更多信息，请参见第 2 章。）

你还可以结合 `and`、`orFilter` 和 `notFilter` 方法组合过滤器。对于不以 "s" 结尾且至少有一个卫星的行星，可以使用这种过滤器组合：

```java
sorter.setRowFilter(RowFilter.and(List.of(
    RowFilter.regexFilter(".*[s$", PLANET_COLUMN),
    RowFilter.numberFilter(ComparisonType.NOT_EQUAL, 0, MOONS_COLUMN)
)));
```

要实现自己的过滤器，请定义 `RowFilter` 的子类并实现 `include` 方法以指示哪些行应该被显示。这很容易做到，但 `RowFilter` 类强大的通用性使得它变得有点复杂。

`RowFilter<M, I>` 有两个类型参数——模型类型和行标识符的类型。在处理表格时，模型始终是 `TableModel` 的子类型，且标识符类型是 `Integer`。（在未来的某个时刻，其他组件也可能支持行过滤。例如，在 `JTree` 中过滤行，可能会使用 `RowFilter<TreeModel, TreePath>`）。

行过滤器必须实现该方法：

```java
public boolean include(RowFilter<? extends M, ? extends I> entry)
```

`RowFilter` 类提供了方法来获取模型、行标识符以及给定索引处的值。因此，你可以根据行标识符和行内容进行过滤。

例如，此过滤器每隔行显示一行：

```java
var filter = new RowFilter<TableModel, Integer>() {

    public boolean include(Entry<? extends TableModel, ? extends Integer> entry) {
        return entry.getIdentifier() % 2 == 0;
    }

};
```

如果你只想包含具有偶数卫星的行星，你将测试：

```java
((Integer) entry.getValue(MOONS_COLUMN)) % 2 == 0
```

在我们的示例程序中，我们允许用户隐藏任意行。我们将隐藏索引存储在一个集合（set）中。设置过滤器会导致它立即生效。

```java
sorter.setRowFilter(filter);
```

## 12.2.8. 隐藏和显示列

正如你在上一节中看到的，你可以根据内容或标识符来过滤行。隐藏列使用完全不同的机制。`JTable` 的 `removeColumn` 方法会从视图中移除列——它们只是被隐藏了。如果你想把它们回来，请调用 `getColumn`：

```java
TableColumn column = table.getColumn(i);
table.addColumn(column);
```

这会将列添加到末尾。如果你想让它出现在其他地方，调用 `moveColumn`：

```java
TableColumn column = table.getColumn(i);
table.moveColumn(column, j);
```

通过添加 `TableColumn` 对象，你可以拥有一个与模型中的列对应的新列：



```java
TableColumn column = new TableColumn(model);
table.addColumn(column);
```

12.3 中的程序演示了行的选择和过滤。

```java
table = new JTable(model);
```

```java
table.setRowHeight(100);

table.getColumnModel().getColumn(COLOR_COLUMN).setMinWidth(250);

table.getColumnModel().getColumn(IMAGE_COLUMN).setMinWidth(100);
```

```java
var sorter = new TableSorter(model);

sorter.setComparator(
    COLOR_COLUMN,
    Comparator.comparing(Color::blue)
        .thenComparing(Color::green)
        .thenComparing(Color::red)
);

sorter.setSortKeys(new RowSorter.SortKey[]{0});

add(JScrollPane(table), BorderLayout.CENTER);
```

```java
removedIndices = new HashSet<>();
removedColumns = new ArrayList<>();
```

```java
var rowFilter = new RowFilter<TableModel, Integer>() {

    public boolean contains(
        Entry<? extends TableModel, ? extends Integer> entry
    ) {
        return !removedIndices.contains(entry.getValue());
    }
};
```

```java
// 创建菜单栏
var menuBar = new JMenuBar();
setJMenuBar(menuBar);
```

```java
rowsItem = new JMenuItem("Rows");
columnsItem = new JMenuItem("Columns");
cellsItem = new JMenuItem("Cells");
```

```java
rowsItem.setSelection(table.getSelectedRowAllowed());
columnsItem.setSelection(table.getColumnModel().SelectionAllowed());
cellsItem.setSelection(table.getCellSelectionEnabled());
```

```java
rowsItem.addActionListener(_ -> {
    table.clearSelection();
    table.setRowSelectionAllowed(rowsItem.isSelected());
    updateCheckboxMenus();
});
```

```java
selectionMenu.add(rows);
```

```java
columnsItem.addActionListener(_ -> {
    table.clearSelection();
    table.setColumnSelectionAllowed(columnsItem.isSelected());
    updateCheckboxMenus();
});
```

```java
selectionMenu.add(columnsItem);
```

```java
cellsItem.addActionListener(_ -> {
    table.clearSelection();
    table.setCellSelectionEnabled(cellsItem.isSelected());
    updateCheckboxMenus();
});
```

```java
selectionMenu.add(cellsItem);
```

```java
var tableMenu = new JMenuItem("Edit");
menuBar.add(tableMenu);
```

```java
var hideColumns = new JMenuItem("Hide Columns");

hideColumns.addActionListener(_ -> {
    int[] selected = table.getSelectedColumns();
    TableColumn columnModel = table.getColumnModel();

    // 从视图中移除列，从最后一个索引开始
    // 这样列号不受影响
    for (int i = selected.length - 1; i >= 0; i--) {
        TableColumn column = columnModel.getColumn(selected[i]);
        table.removeColumn(column);

        // 存储移除的列以便执行“显示列”命令
        removedColumns.add(column);
    }
});

tableMenu.add(hideItems());

var showColumns = new JMenuItem("Show Columns");

showColumns.addActionListener(() -> {
    // 恢复所有被移除的列
    for (TableColumn tc : removedColumns) {
        table.addColumn(tc);
    }
});

tableMenu.add(showColumns);

var hideRows = new JMenuItem("Hide Rows");

hideRows.addActionListener(() -> {
    int[] selected = table.getSelectedRows();

    for (int i : selected) {
        removedRows.add(table.convertRowIndexToModel(i));
    }

    sorter.RowFilter(filter);
});

tableMenu.add(hideRows);

var showRows = new JMenuItem("Show Rows");

showRows.addActionListener(() -> {
    removedRows.clear();
    sorter.setRowFilter(filter);
});

tableMenu.add(showRows);

var printSelection = new JMenuItem("Print Selection");

printSelection.addActionListener(() -> {
    int[] selected = table.getSelectedRows();
    System.out.println("Selected rows: " + Arrays.toString(selected));

    int[] selected = table.getSelectedColumns();
    System.out.println("Selected columns: " + Arrays.toString(selected));
});

tableMenu.add(printSelection);
```

## `javax.swing.TableModel` 1.2

- `getColumnClass(int columnIndex)` 获取此列中值的类型类。此信息用于排序和渲染。

## `javax.swing.JTable` 1.2

- `TableColumn getColumnModel()` 获取描述表格列布局的模型。
- `voidAutoResizeMode(int mode)` 设置表格列自动调整大小的模式。模式参数为 `AUTORESIZE_OFF`、`AUTORESIZE_NEXT_COLUMN`、`AUTORESIZE_SUBSEQUENT_COLUMNS`、`AUTORESIZE_LAST_COLUMN` 和 `AUTORESIZE_ALL_COLUMNS`。
- `getRowMargin() void setRowMargin(int margin)` 获取或设置相邻行之间的空隙。
- `getRowHeight() void setRowHeight(int height)` 获取或设置表格中所有行的默认高度。
- `getRowHeight(int row) void setRowHeight(int row, int height)` 获取或设置特定行的高度。
- `ListSelectionModel getSelectionModel()` 返回选择模型，以便可以在行、列和单元格选择之间进行切换。
- `boolean getRowSelectionAllowed() void setRowSelectionAllowed(boolean b)` 获取或设置 `rowSelectionAllowed` 属性。如果为 true，当用户点击单元格时将选中行。
- `boolean getColumnSelectionAllowed() void setColumnSelectionAllowed(boolean b)` 获取或设置 `columnSelectionAllowed` 属性。如果为 true，当用户点击单元格时将选中列。
- `boolean getCellSelectionEnabled() void setCellSelectionEnabled(boolean b)` 获取或设置单元格选择是否启用。
- `void setRowSelectionAllowed(boolean b)` 设置行选择允许。
- `void setColumnSelectionAllowed(boolean b)` 设置列选择允许。
- `void clearSelection()` 清除所有选择。
- `boolean getRowSelectionAllowed()` 获取行选择允许。
- `boolean getColumnSelectionAllowed()` 获取列选择允许。
- `boolean getCellSelectionEnabled()` 获取单元格选择是否启用。
- `TableColumnModel getColumnModel()` 获取列模型。
- `int[] getSelectedRows()` 返回所有被选中行。
- `int[] getSelectedColumns()` 返回所有被选中列。

## 12.3. 单元格的渲染与编辑

正如你在[第 12.2.2 节](_Section 12.2.2)中所示，列类型决定了单元格如何渲染。`Boolean` 和 `Icon` 类型有默认渲染器，用于渲染复选框或图标。对于所有其他类型，你需要安装自定义渲染器。

### 12.3.1. 渲染单元格

表格单元格渲染器类似于你之前看到的列表渲染器。它们实现了 `TableCellRenderer` 接口，该接口有一个方法：

```java
Component getTableCellRendererComponent(
    JTable table,
    Object value,
    boolean isSelected,
    boolean hasFocus,
    int row,
    int column
)
```

当表格需要绘制单元格时会调用该方法。你返回一个组件，其 `paint` 方法将被调用以填充单元格区域。

[图 12.8](_Figure 12.8) 中的表格包含 `Color` 类型的单元格。渲染器简单返回一个带有颜色的面板，该颜色是存储在单元格中的颜色对象。颜色通过 `value` 参数传递。

```java
class TableCellRenderer extends JPanel implements TableCellRenderer {

    public Component getTableCellRendererComponent(
        JTable table,
        Object value,
        boolean isSelected,
        boolean hasFocus,
        int row,
        int column
    ) {
        setBackground((Color) value);

        if (hasFocus) {
            setBorder(UIManager.getBorder("Table.focusHighlightBorder"));
        } else {
            setBorder(null);
        }

        return this;
    }
}
```

| 行星 | 半径 | 气态 | 颜色 | 图像 |
| :--- | :--- | :--- | :--- | :--- |
| 火星 | 3,397 | 2 | | |
| 木星 | 71,492 | 16 | | |
| 土星 | 60,268 | 18 | | |

**图 12.8：** 带有单元格渲染器的表格

如你所见，当单元格获得焦点时，渲染器会绘制一个边框。（我们向 `UIManager` 请求正确的边框。为了找到查找键，我们查阅了 `DefaultTableCellRenderer` 类的源代码。）

> 提示：如果你的渲染器绘制的是文本字符串或图标，你可以扩展 `DefaultTableCellRenderer` 类。它会为你处理焦点和选中状态的渲染。

你需要告诉表格使用此渲染器处理所有 `Color` 类型的对象。`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器：

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在被用于此表格中所有给定类型的对象。

如果你想根据其他标准选择渲染器，你需要派生 `JTable` 类并重写 `getCellRenderer` 方法。

### 12.3.2. 渲染表头

要在表头显示图标，请设置表头值：

```java
moonColumn.setHeaderValue(new ImageIcon("Moons.gif"));
```



然而，表格表头并不智能到为表头值选择合适的渲染器。你必须手动安装渲染器。例如，要在列头中显示图像图标，请调用：

```java
moonColumn.setHeaderRenderer(table.getDefaultRenderer(ImageIcon.class));
```

### 12.3.3. 编辑单元格

要启用单元格编辑，表格模型必须通过定义 `isEditable` 方法来指示哪些单元格是可编辑的。通常情况下，你可能希望某些列是可编辑。在示例程序中，我们允许四列进行编辑。

```java
public boolean isCellEditable(int r, int c) {
    return c == PLANET_COLUMN || c == MOONS_COLUMN || c == GASEOUS_COLUMN
        || c == COLOR_COLUMN;
}
```

> 注意：`AbstractTableModel` 定义的 `isEditable` 方法始终返回 `false`。`DefaultTableModel` 重写了该方法使其始终返回 `true`。

如果你运行本节末尾的示例程序，请注意你可以点击 Gaseous 列中的复选框并开启或关闭勾选标记。如果你点击 Moons 列中的单元格，会弹出一个组合框（见图 12.9）。你很快就会看到如何将此类组合框安装为单元格编辑器。

| 行星 | 半径 | 气态 | 颜色 | 图像 |
| :--- | :--- | :--- | :--- | :--- |
| 水星 | 2,440 | 0 |  |  |
| 金星 | 6,052 |  |  |  |
| 地球 | 6,378 | 1 |  |  |

**图 12.9：** 单元格编辑器

最后，点击第一列中的单元格。单元格获得焦点。你可以开始输入，单元格内容会发生变化。

你刚刚看到的演示是 `DefaultCellEditor` 类的三种变体。`DefaultCellEditor` 可以使用 `JTextField`、`JCheckbox` 或 `JComboBox` 来构造。`JTable` 会自动为 `Boolean` 单元格安装复选框编辑器，并为所有未提供自定义渲染器的可编辑单元格安装文本字段编辑器。文本字段允许用户编辑字符串，这些字符串是通过对表格模型 `getCellValue` 方法的返回值应用 `toString` 得到的。

当编辑完成后，通过调用你编辑器的 `getCellEditor` 方法来获取编辑后的值。该方法应该返回正确类型的值（即模型中 `getColumnType` 方法返回的类型）。

要获取组合框编辑器，请手动设置单元格编辑器——`JLabel` 并不知道对于特定类型哪些值可能是合适的。

```java
JComboBox moonCombo = new JComboBox();

for (int i = 0; i < 20; i++)
    moonCombo.addItem(i);
```

```java
DefaultCellEditor moonEditor = new DefaultCellEditor(moonCombo);
```

接下来，我们需要安装编辑器。与单元格渲染器不同，此编辑器不依赖焦点。在我们的示例中，我们使用：

```java
moonColumn.setCellEditor(moonEditor);
```

### 12.3.4. 自定义编辑器

`JTable` 类会带上事件（例如鼠标点击）调用你的编辑器，以确定该事件是否可以启动编辑过程。`AbstractCellEditor` 类定义的方法接受所有事件。

```java
public boolean isEditable(Object anEvent) {
    return true;
}
```

如果你覆盖了该方法并返回 `false`，表格将不会费力插入编辑器组件。一旦编辑器组件安装完成，就会调用 `shouldSelectCell` 方法，通常带有相同的事件。你应该在该方法中启动编辑——例如，通过弹出一个外部编辑对话框。

```java
public boolean shouldSelectCell(Object anEvent) {
    colorDialog.setVisible(true);
    return true;
}
```

最后，你需要一个方法来返回用户在编辑过程中提供的值：

```java
public Object getCellEditorValue() {
    return colorChooser.getColor();
}
```

总结一下，你的自定义编辑器应该执行以下操作：

1. 扩展 `AbstractCellEditor` 类并实现 `TableCellEditor` 接口。
2. 定义 `getTableCellEditorComponent` 方法以提供组件。这可以是一个占位组件（如果你弹出一个对话框），也可以是用于原地编辑的组件，如组合框或文本字段。
3. 定义 `shouldSelectCell`、`stopCellEditing` 和 `cancelCellEditing` 方法来处理编辑过程的开始、完成和取消。`stopCellEditing` 和 `cancelCellEditing` 应该调用父类方法以确保通知监听器。
4. 定义 `getCellEditorValue` 方法来返回编辑过程的结果。

最后，通过调用 `stopCellEditing` 和 `cancelCellEditing` 方法来指示用户已完成编辑。在构建颜色对话框时，我们安装了处理这些事件的接受和取消回调。

```java
colorDialog = JColorChooser.createDialog(null, "Planet Color", false, colorChooser);

EventHandler.create(ActionListener.class, this, "stopCellEditing");

EventHandler.create(ActionListener.class, this, "cancelCellEditing");
```

此时自定义编辑器的实现完成。

你现在已经知道了如何让单元格变得可编辑以及如何安装编辑器。还剩一点——如何用用户编辑的值来更新模型。当编辑完成后，`JTable` 类会遵循表格模型的以下方法：

```java
void setValue(Object value, int r, int c)
```

你需要重写该方法来存储新值。`value` 参数是单元格编辑器返回的对象。如果你实现了单元格编辑器，你就知道从 `getCellEditorValue` 方法返回的对象的类型。在 `DefaultCellEditor` 的情况下，该类型有三种可能：如果单元格编辑器是复选框，则为 `Boolean`；如果是文本字段，则为字符串（`String`）；如果值来自组合框，则它是用户选择的对象。

如果 `value` 对象没有相应的类型，你需要对它进行转换。这通常发生在文本字段中编辑数字时。在我们的示例中，为组合框填充了 `Integer` 对象，因此不需要进行转换。

## Listing 12.4 v2ch12/tableCellRenderer/TableCellRenderFrame.java

```java
package v2ch12.tableCellRenderer;

import java.desktop;

/**
 * 此框架包含一个行星数据表格。
 */
public class TableCellRendererFrame extends JFrame {
    private static final int WIDTH = 600;
    private static final int DEFAULT_HEIGHT = 400;

    public TableCellRendererFrame() {
        setSize(WIDTH, DEFAULT_HEIGHT);

        var model = new PlanetTableModel();
        var table = new JTable(model);

        table.setRowAllowed(false);

        // 设置渲染器和编辑器
        table.setDefaultCellRenderer(Color.class, new TableCellRenderer());
        table.setDefaultCellEditor(Color.class, new TableCellEditor());

        var comboBox = new JComboBox<Integer>();

        for (int i = 0; i <= 20; i++) {
            comboBox.addItem(i);
        }

        TableColumn column = table.getColumnModel();
        TableColumn moonColumn = column.getColumn(PlanetTableModel.MOONS_COLUMN);

        moonColumn.setEditor(new DefaultCellEditor(comboBox));
        moonColumn.setHeaderRenderer(new DefaultRenderer(ImageIcon.class));
        moonColumn.setHeaderValue(new ImageIcon("images/Moons.gif"));

        // 显示表格
        table.addRowHeight(100);
        add(new JScrollPane(table), BorderLayout.CENTER);
    }
}
```

## Listing 12.5 v2ch12/tableCellRenderer/PlanetTableModel.java

```java
package v2ch12.tableCellRenderer;

import java.desktop;

/**
 * 行星模型指定了行星数据的值、渲染和编辑属性。
 */
public class PlanetTableModel extends AbstractTableModel {
    public static final int PLANET_COLUMN = 0;
    public static final int MOONS_COLUMN = 2;
    public static final int GASEOUS_COLUMN = 3;
    public static final int COLOR_COLUMN = 4;

    private Object[][] cells = {
        { "Mercury", 0.0, 0, false, Color.YELLOW, new ImageIcon("images/Mercury.gif") },
        { "Venus", 6052.0, 0, false, Color.YELLOW, new ImageIcon("images/Venus.gif") },
        { "Earth", 6378.0, 1, false, Color.BLUE, new ImageIcon("images/Earth.gif") },
        { "Mars", 3397.8, 2, false, Color.RED, new ImageIcon("images/Mars.gif") },
        { "Jupiter", 71492.0, 10, true, Color.ORANGE, new ImageIcon("images/Jupiter.gif") },
        { "Saturn", 60268.0, 18, true, Color.ORANGE, new ImageIcon("images/Saturn.gif") },
        { "Uranus", 25362.0, 19, true, Color.BLUE, new ImageIcon("images/Uranus.gif") },
        { "Neptune", 24619.0, 20, true, Color.BLUE, new ImageIcon("images/Neptune.gif") },
    };
}
```

- `TableCellEditor getDefaultEditor(Class<?> type)`  
  获取指定类型的默认编辑器。

## `javax.swing.table.TableCellRenderer` 1.2

- `ComponentTableCellRendererComponent(JTable table, Object value, boolean hasFocus, int row, int column)`  
  返回一个组件，其 `paint` 方法被调用用以渲染单元格。

## `javax.swing.table.TableCellColumn` 1.2

- `void setCellEditor(TableCellEditor editor)`  
  `void setCellRenderer(TableCellRenderer renderer)`  
  设置此列所有单元格的编辑器或渲染器。
- `void setHeaderRenderer(TableCellRenderer renderer)`  
  设置此列表头单元格的渲染器。
- `void setHeaderValue(Object value)`  
  设置此列表头显示的值。

## `javax.swing.DefaultTableCellEditor` 1.2

- `DefaultTableCellEditor(JComboBox comboBox)`  
  构造一个呈现组合框的编辑器，用于选择单元值。

## `javax.swing.table.TableCellEditor` 1.2

- `Component getCellEditorComponent(JTable table, Object value, boolean selected, int row, int column)`  
  返回一个组件，其 `paint` 方法用于渲染单元格。

## `javax.swing.CellEditor` 1.2

- `boolean isEditable(Object event)`  
  如果该事件适用于启动此单元格的编辑过程，则返回 `true`。
- `boolean selectCell(Object event)`  
  启动编辑过程。如果编辑后的单元格应该被选中，则返回 `true`。通常情况下你希望返回 `true`，但如果不希望编辑过程改变单元格的选择，则可以返回 `false`。
- `void cancelCellEditing()`  
  取消编辑过程。你可以放弃部分编辑。
- `boolean stopCellEditing()`  
  停止编辑过程并意图使用结果。如果编辑后的值处于可检索的范围，则返回 `true`。
- `Object getCellEditorValue()`  
  返回编辑后的结果。
- `void addCellEditorListener(CellEditorListener l)`  
  `void removeCellEditorListener(CellEditorListener l)`  
  添加或移除强制单元格编辑器监听器。

### 12.4. 树

每个处理过分级文件系统的计算机用户都见过树形显示。当然，目录和文件只是树形组织结构的一个例子。日常生活中存在着许多树形结构，例如图 12.11 所示的国家、州和城市的层级结构。

图 12.11：国家、州和城市的层级结构

作为程序员，我们需要显示树形结构。幸运的是，Swing 库有一个 `JTree` 类专门用于此目的。`JTree` 类（连同它的辅助类）负责树的布局以及处理用户对展开和折叠节点的请求。在本节中，你将学习如何使用 `JTree` 类。

与其他复杂的 Swing 组件一样，我们必须关注常见且实用的情况，无法涵盖每一个细微差别。如果你想实现某些不寻的功能，我们建议你使用 David M. Gears 编写的《Graphic Java》（第三版）或 Kim Topley 编写的《Core Swing》。

在继续下去之前，让我们先确定一些术语（见图 12.12）。树由*节点*（nodes）组成。每个节点要么是*叶节点*（leaf），要么拥有*子节点*（child nodes）。除了根节点外，每个节点恰好有一个*父节点*（parent）。树恰好有一个根节点。有时你拥有一组树（集合），每棵树都有自己的根节点。这样的集合被称为*森林*（forest）。

图 12.12：树的术语

### 12.4.1. 简单树

在我们的第一个示例程序中，我们将简单地显示一个带有节点的树（见图 12.14）。与许多其他 Swing 组件一样，你需要提供数据模型，由组件为你显示它。要构造一个 `JTree`，可以在构造函数中提供树模型：

```java
TreeModel = . . .;
var tree = new JTree(model);
```

> 注意：还有一些从元素集合构造树的构造函数：

- `JTree(Object[]) nodes`
- `JTree(Vector<>) nodes`
- `JTree(Hashtable<?, ?> nodes)` // 值将变为节点

这些构造函数并没有什么用。它们仅仅构建了一个树森林，每棵树都只有一个节点。第三种构造函数似乎特别没用，因为节点按照键的哈希值决定的看似随机的顺序出现。

如何获取树模型？你可以通过创建一个实现 `Tree` 接口的类来构建自己的模型。你将在本章稍后的部分看到如何这样做。现在，我们将使用 Swing 库提供的 `DefaultTreeModel`。

要构造一个默认树模型，你必须提供一个根节点。

```java
TreeNode root = . .;
```



`var model = new DefaultTreeModel(root);`

`TreeNode` 是另一个接口。用任何实现该接口的类的对象填充默认树模型。现在，我们将使用 Swing 提供的具体类——`DefaultMutableTreeNode`。该类实现了 `MutableTreeNode` 接口，它是 `TreeNode` 的子接口（见图 12.13）。

图 12.13：树类

默认树节点持有一个对象——用户对象。树渲染所有节点的用户对象。除非你指定渲染器，否则树将显示 `toString` 方法结果的字符串。

在我们的第一个示例中，我们使用字符串作为用户对象。在实践中，你通常会用具有表现力的用户对象填充树。例如，在显示目录树时，使用 `File` 对象作为节点是有意义的。

你可以在构造函数中指定用户对象，也可以稍后设置。

接下来，你需要建立节点之间的父子关系。从根节点开始，使用 `add` 方法添加子节点：

```
var root = DefaultMutableTreeNode("World");

var country = DefaultMutableTreeNode("USA");

root.add(country);

var state = DefaultMutableTreeNode("California");

country.add(state);
```

图 12.14：一个简单的树

以这种方式链接所有节点。然后，使用根节点构造 `DefaultTreeModel`。最后，使用模型构造 `JTree`。

```
var model = new DefaultTreeModel(root);

var tree = new JTree(model);
```

或者，作为快捷，你可以直接将根节点传递给 `JTree` 构造函数。然后树会自动构造默认树模型：

```
var tree = new JTree(root);
```

列表 12.8 包含了完整代码。

```java
// 设置树形数据

var root = DefaultMutableTreeNode("World");

var country = DefaultMutableTreeNode("USA");

root.add(country);

var state = DefaultMutableTreeNode("California");

country.add(state);

var city = DefaultMutableTreeNode("San Jose");

state.add(city);

city = DefaultMutableTreeNode("Cupertino");

state.add(city);

state = DefaultMutableTreeNode("Michigan");

country.add(state);

city = DefaultMutableTreeNode("Ann Arbor");

country.add(city);

country = DefaultMutableTreeNode("Germany");

root.add(country);

var state = DefaultMutableTreeNode("Schleswig-Holstein");

city = DefaultMutableTreeNode("Kiel");

state.add(city);

// 构造树并放入滚动面板

var tree = new JTree(root);

add(new JScrollPane(tree));
```

![](img/240dbf1b84e081687f1e252bd386c684_941_0.png)

**图 12.16：** 折叠和展开的子树

> 注意：当然，树的显示取决于所选的视图（look-and-feel）。在 Windows 外观中，上述描述的句柄指的是 Metal 外观的——方框中的 `-` 或 `+`（参见[图 12.17]()）。

![](img/240dbf1b84e081687f1e252bd386c684_941_1.png)

**图 12.17：** 具有 Windows 外观的树

你可以使用以下“魔咒”来关闭连接父节点和子节点之间的线条（参见[图 12.18]()）。

```
tree.putClientProperty("JTree.lineStyle", "None");
```

![](img/240dbf1b84e081687f1e252bd386c684_942_0.png)

相反，要确保显示线条，请使用：

```
tree.putClientProperty("Tree.lineStyle", "Angled");
```

另一种线条样式 `"Horizontal"`（水平）显示在图 12.19 中。树的显示方式仅用水平线分隔根节点的节点。我不确定这有什么用。

![](img/240dbf1b84e081687f1e252bd386c684_942_1.png)

默认情况下，没有用于折叠树根节点的句柄。如果你愿意，可以通过调用添加一个：

```
tree.setShowsRootHandles(true);
```

图 12.20 显示了结果。现在你可以将整棵树折叠到根节点中。

![](img/240dbf1b84e081687f1e252bd386c684_943_0.png)

**图 12.20：** 具有根节点句柄的树

相反，你可以完全隐藏根节点。这样你就显示了一个“森林”——一组树，每棵树都有自己的根节点。你仍然必须将森林中的所有树连接到一个公共根节点；然后使用指令隐藏根节点：

```
tree.setRootVisible(false);
```

看图 12.21。似乎有两个根节点，分别标记为 `"USA"` 和 `"Germany"`。连接这两个者的实际根节点不可见的。

![](img/240dbf1b84e081687f1e252bd386c684_943_1.png)

**图 12.21：** 森林

让我们从根节点转向树的叶子节点。注意，叶子节点的图标与其他节点不同（参见图 12.22）。

![](img/240dbf1b84e081687f1e252bd386c684_944_0.png)

**图 12.22：** 叶子图标和文件夹图标

当显示树时，每个节点都用一个图标绘制。实际上有三种类型的图标：叶子图标、打开的非叶子图标和关闭的非叶子图标。为了简单起见，我们将后两种称为文件夹图标。

节点渲染器需要知道为每个节点使用哪种图标。默认情况下，决策过程如下：如果一个节点的 `isLeaf` 方法返回 `true`，则使用叶子图标；否则，使用文件夹图标。

`DefaultMutableTreeNode` 类的 `isLeaf` 方法在节点没有子节点时返回 `true`。因此，有子节点的节点获得文件夹图标，而没有子节点的节点获得叶子图标。

有时，这种行为并不恰当。假设我们在示例树中添加了一个名为 `"Montana"`（蒙大拿州）的节点，但我们不知道应该添加哪些城市。我们不希望状态节点获得叶子图标，因为从概念上说，只有城市才是叶子。

`JTree` 类并不知道哪些节点应该是叶子。它询问树模型。如果一个子节点不是自动成为概念上的叶子，你可以要求树模型使用不同的标准来判断是否为叶子——即查询“允许子”节点属性。

对于不应该有子节点的节点，调用：

```
node.setAllowsChildren(false);
```

然后，告诉树模型询问“允许子”属性的值来确定一个节点是否应该显示为叶子图标。使用 `DefaultTreeModel` 类的 `setAsksAllowsChildren` 方法来设置此行为：

```
model.setAsksAllowsChildren(true);
```

使用这种决策标准，允许子节点的节点获得文件夹图标，而不允许子节点的节点获得叶子图标。

或者，如果你从根节点构造树，请在构造函数中提供“询问允许子”属性的设置。

```
var tree = new JTree(root, true); // 不允许子节点的节点获得叶子图标
```

| `javax.swing.JTree` 1.2 |
| :--- | :--- |
| ■ `JTree(TreeModel model)` | 从树模型构建树。 |
| ■ `JTree(TreeNode root)` | 从根节点构建树。 |
| ■ `JTree(TreeNode root, boolean asksChildren)` | 从根节点构建树。 |
| ■ `void setHandles(boolean b)` | 如果 `b` 为 true，根具有句柄。 |
| ■ `void setRootVisible(boolean b)` | 如果 `b` 为 true，根被隐藏。 |
| ■ `boolean isLeaf()` | 如果节点是叶子，返回 true。 |
| ■ `boolean allowsChildren()` | 如果节点允许子节点，返回 true。 |
| ■ `void setUser(Object user)` | 设置用户。 |

| `javax.swing.TreeModel` 1.2 |
| :--- | :--- |
| ■ `boolean isLeaf(Object node)` | 如果节点是叶子，返回 true。 |
| ■ `boolean allowsChildren()` | 如果节点允许子节点，返回 true。 |
| ■ `void setAsksAllowsChildren(boolean b)` | 如果 `b` 为 true，模型询问子。 |

| `javax.swing.TreeNode` 1.2 |
| :--- | :--- |
| ■ `DefaultMutableTreeNode(Object user)` | 使用对象构造可变节点。 |
| ■ `void add(TreeNode child)` | 向树添加子节点。 |
| ■ `void setAllowsChildren(boolean b)` | 如果 `b` 为 true，节点允许子节点。 |

| `javax.swing.Component` 1.2 |
| :--- | :--- |
| ■ `Object selectionPath()` | 返回节点的路径。 |
| ■ `void putClientProperty(Object key, Object value)` | 设置键值对。 |

## 12.4.2 编辑树和路径

在下一个示例中，你将找到如何编辑树。图 12.23 显示了界面。如果你点击“添加兄弟”或“添加子节点”，程序将向树添加新节点。如果你点击“删除”，程序将删除当前选中的节点。

![](img/240dbf1b84e081687f1e252bd386c684_946_0.png)

**图 12.24：** 路径

**注意：** 树路径（Tree paths）是 `JTree` 类描述节点的两种方式之一。许多 `JTree` 方法接收或返回整数索引——即行位置。行位置简单指的是节点在树显示中的行号（从 0 开始）。只有可见节点才有行号，而且如果该节点之前的节点被展开、折叠或修改，该节点的行号就会改变。因此，你应该避免使用行位置。所有使用行位置的 `JTree` 方法都有对应使用树路径的替代方法。

一旦你选中了节点，就可以对其进行编辑。但是，不要直接向树节点添加子节点：

```
selectedNode.add(newNode); // 不要！
```

如果你更改了节点的结构，你改变了模型，但关联的视图不会收到通知。如果你使用 `DefaultTreeModel` 的 `insertNodeInto` 方法，模型类会处理这一点。例如，以下调用会将新节点作为所选节点的最后一个子节点，并通知树视图：

```
model.insertNodeInto(newNode, selectedNode, selectedNode.getChildCount());
```

相应的调用 `removeNodeFromParent` 会移除一个节点并通知视图：

```
model.removeNodeFromParent(selectedNode);
```

如果你保持节点结构不变但更改了用户对象，则应该调用以下方法：

```
model.nodeChanged(changedNode);
```

自动通知是使用 `DefaultTreeModel` 的一个主要优势。如果你提供自己的模型，则需要手动实现自动通知。（详情请参见 Kim Topley 编写的《Core Swing》。）

> 注意：`DefaultTreeModel` 类有一个 `reload` 方法，可以重新加载整棵树。然而，不能仅仅为了在做一些更改后通过它来更新树。当树重新生成时，根节点之外的节点将再次折叠。如果用户在每次更改后都必须重新展开树，将令他们感到非常困惑。

当你收到节点结构变化的通知时，它会更新显示，但不会自动展开节点来显示新添加的子节点。特别是，如果示例程序中的用户为一个当前处于折叠状态的节点添加新子节点，新节点将静默地被添加到折叠的子树中。这给用户提供了反馈，确认命令已实际执行。在这种情况下，你应该特意展开父节点，以便新添加的节点变得可见。为此，请使用 `JTree` 类的 `makeVisible` 方法。`makeVisible` 方法期望接收一个指向应可见节点的树路径。

因此，你需要构建一个从根节点到新插入节点的树路径。要获取树路径，首先调用 `DefaultTree` 类的 `getPathToRoot` 方法。它返回一个从节点到根路径的 `TreeNode[]` 数组。将该数组传递给 `TreePath` 构造函数即可。

例如，以下是创建新节点的方法：

```
TreeNode[] nodes = model.getPathToRoot(newNode);

var path = new TreePath(nodes);

tree.makeVisible(path);
```

> 注意：奇怪的是，`DefaultTree` 类几乎完全忽略了 `TreePath` 类，尽管它的工作是与 `JTree` 通信。`JTree` 使用树路径，而从不使用节点数组。

假设你的树包含在一个滚动面板（scroll pane）中。在树节点展开后，新节点可能仍然不可见，因为超出了视口（viewport）。为了解决这个问题，请调用：

```
tree.scrollPathToVisible(path);
```

而不是调用 `makeVisible`。此调用会展开路径上的所有节点，并告诉周围的滚动面板滚动到路径末端的节点（参见图 12.25）。

![](img/240dbf1b84e081687f1e252bd386c684_949_0.png)

图 12.25：滚动面板滚动以显示新节点。

默认情况下，树节点是不可编辑的。然而，如果你调用：

```
tree.setEditable(true);
```

用户只需通过双击、编辑字符串并按下 Enter 键即可编辑节点。双击会调用默认单元格编辑器，该渲染器由 `DefaultCellEditor` 类实现（参见图 12.26）。你可以使用我们在讨论表格单元格编辑器时看到的相同过程来安装其他单元格编辑器。

![](img/240dbf1b84e081687f1e252bd386c684_950_0.png)

**图 12.26：** 默认单元格编辑器

列表 12.9 显示了树编辑程序的完整源代码。运行程序，添加几个节点，并通过双击进行编辑。观察折叠节点如何展开以显示添加的子节点，以及滚动面板如何保持节点在视口内。

# Listing 12.9 `v2ch2/treeEdit/TreeEditFrame.java`

```java
package v2ch2.treeEdit;

import java.desktop;

/** 一个带有树和添加树按钮的框架。 */

public class TreeEditFrame extends JFrame {

    private static final int DEFAULT_WIDTH = 400;

    private static final int DEFAULT_HEIGHT = 200;

    private DefaultTreeModel model;

    private JTree tree;

    public TreeEditFrame() {

        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

        // 构造函数

        TreeNode root = makeSampleTree();

        model = new DefaultTreeModel(root);

        tree = new JTree(model);

        tree.setEditable(true);

        // 添加滚动面板

        JScrollPane scrollPane = new JScrollPane(tree);

        add(scrollPane, BorderLayout.CENTER);

        // 按钮

        JPanel panel = new JPanel();

        JButton addButton = new JButton("Sibling");

        addButton.addActionListener(e -> {

            TreeNode selectedNode = (TreeNode) tree.getLastPathComponent();

            if (selectedNode != null) {

                TreeNode newNode = new TreeNode("New");

                int index = selectedNode.getIndex();

                model.insertNodeInto(newNode, selectedNode, index);



```java
TreeNode[] nodes = model.getPathToRoot(newNode);

TreePath path = new TreePath(nodes);

tree.makeVisible(path);

}

});

panel.add(addButton);

JButton addChildButton = new JButton("Child");

addChildButton.addActionListener(e -> {

TreeNode selectedNode = (TreeNode) tree.getLastPathComponent();

if (selectedNode != null) {

TreeNode newNode = new DefaultTreeNode("New");

model.insertNodeInto(newNode, selectedNode, selectedNode.getChildCount());

TreeNode[] nodes = model.getPathToRoot(newNode);

TreePath path = new TreePath(nodes);

tree.scrollPathToVisible(path);

}

});

panel.add(addChildButton);

JButton deleteButton = new JButton("Delete");

deleteButton.addActionListener(e -> {

TreeNode selectedNode = (TreeNode) tree.getLastPathComponent();

if (selectedNode != null && selectedNode.getParent() != null) {

model.removeNodeFromParent(selectedNode);

}

});

panel.add(deleteButton);

add(panel, BorderLayout.SOUTH);

}

TreeNode makeSampleTree() {

// 为了简洁起见省略实现

return new DefaultTreeNode("Root");

}

}

```

- `void reload()`
  - 将所有节点重新加载到模型中。这是一个剧烈的操作，只有当节点由于某些外部影响而完全变化时，你才使用它。

## 12.4.3. 节点枚举

有时，你需要从根节点开始在树中查找节点，并访问所有子节点直到找到匹配项。`DefaultMutableTreeNode` 类具有几个方便方法，用于遍历节点。

`breadthEnumeration` 和 `depthFirstEnumeration` 方法返回枚举对象，其 `nextElement` 方法使用广度优先或深度优先遍历来访问当前节点的子节点。图 12.27 显示了示例树的遍历情况——节点标签指示了节点被遍历的顺序。

### 12.27：树的遍历顺序

广度优先枚举最容易可视化。树按层进行遍历。首先访问根节点，然后是它所有的子节点、孙子节点，依此类推。

要可视化深度优先枚举，可以想象一只被困在树形迷宫中的老鼠。它沿着第一条路径冲直到遇到叶子节点。然后它回溯并转向下一条路径，依此类推。

计算机科学家也称称为后序遍历，因为搜索过程在访问父节点之前访问了子节点。`postOrderEnumeration` 方法是 `depthFirstEnumeration` 的同义词。为了完整起见，还有 `preOrderEnumeration`，这是一种在子节点之前枚举节点的深度优先搜索。

这里是典型的用法模式：

```java
Enumeration breadth = node.breadthFirstEnumeration();

while (breadth.hasMoreElements())

do something with breadth.nextElement();

```

最后，一个相关方法 `pathFromEnumeration` 找到从祖先到给定节点的路径，并枚举该路径上的节点。这没什么大不了——它不断调用 `getParent` 直到找到祖先然后按反序输出路径。

在我们的下一个示例中，我们把节点枚举投入实际工作。程序显示类的继承树。在框架（frame）底部的文本框中输入类名。该类及其所有的父类都会被添加到树中（见图 12.28）。

![](img/240dbf1b84e081687f1e252bd386c684_954_0.png)

图 12.28：继承树

在这个示例中，我们利用了树节点的节点对象（user objects）可以是任何类型对象的特性。由于我们的节点描述的是类，我们在节点中存储了 `Class` 对象。

我们不想重复添加同一个类，因此我们需要检查类是否已经存在于树中。以下方法如果类存在于树中则查找带有用户对象的节点：

```java
public DefaultMutableTreeNode findUserObject(Object obj) {

    Enumeration e = root.breadthFirstEnumeration();

    while (e.hasMoreElements()) {

        DefaultMutableTreeNode node = (DefaultMutableTreeNode) e.nextElement();

        if (node.getUserObject().equals(obj)) {

            return node;

        }

    }

    return null;

}

```

## 12.4.4. 节点的渲染

在你的应用程序中，你经常需要更改树组件绘制节点的方式。最常见的更改为节点和叶子节点选择不同的图标。其他更改可能涉及更改节点标签的字体或在树上绘制图像。所有更改可以通过向树中安装新的树单元渲染器（tree cell renderer）来实现。默认情况下，`JTree` 使用 `DefaultTreeCellRenderer` 对象来绘制每个节点。`DefaultTreeCellRenderer` 继承自 `JLabel` 类。标签包含节点图标和节点标签。

> 注意：单元渲染器不绘制用于展开和折叠子树的“句柄”（handles）。句柄是外观（look-and-feel）的一部分，建议你不要对它们进行更改。

你可以通过三种方式自定义显示：

- 你可以更改 `DefaultTreeCellRenderer` 使用的图标、字体和背景颜色。这些设置适用于树中的所有节点。
- 你可以安装扩展 `DefaultTreeCellRenderer` 类的渲染器，并为每个节点改变图标、字体和背景颜色。
- 你可以安装实现 `TreeCellRenderer` 接口的渲染器来为每个节点绘制自定义图像。

让我们逐来看这些可能性。最简单的自定义是构造一个 `DefaultTreeCellRenderer` 对象，更改图标并将其安装到树中：

```java
var renderer = new DefaultTreeCellRenderer();

renderer.setLeafIcon(new ImageIcon("blue-ball.gif")); // 用于叶子节点

renderer.setClosedIcon(new ImageIcon("red-ball.gif")); // 用于折叠节点

renderer.setOpenIcon(new ImageIcon("yellow-ball.gif")); // 用于展开节点

tree.setCellRenderer(renderer);

```

你可以在图 12.28 中看到效果。我们只是使用“球”作为占位符，假设你的用户设计师会提供相应的图标供你的应用程序使用。

我们不建议你更改整棵树的字体或背景颜色——那实际上是外观（look-and-feel）的工作。

然而，更改树中节点的字体以突出显示它们可能是很有用的。如果你仔细观察图 12.28，你会注意到抽象类是斜体字。

要更改单个节点的显示，请安装树单元渲染器。单元渲染器与我们在本章稍后讨论的单元渲染器非常相似。`TreeCellRenderer` 有一个简单的接口：

```java
Component TreeCellRendererComponent(
    JTree tree,
    Object value,
    boolean selected,
    boolean expanded,
    boolean leaf,
    int row,
    boolean hasFocus
)

```

`DefaultTreeCellRenderer` 类的 `getTreeRendererComponent` 方法返回此——换句话说，一个标签。（`DefaultTreeCellRenderer` 继承自 `JLabel` 类）。要自定义组件，请扩展 `DefaultTreeCellRenderer` 类。重写 `getTreeRendererComponent` 方法如下：调用父类方法以便准备标签数据，自定义标签属性，最后返回此。

```java
class MyTreeCellRenderer extends DefaultTreeCellRenderer {

    public Component getTreeRendererComponent(
        JTree tree,
        Object value,
        boolean selected,
        boolean expanded,
        boolean leaf,
        int row,
        boolean hasFocus) {

        Component comp = super.getTreeRendererComponent(
            tree,
            value,
            selected,
            expanded,
            leaf,
            row,
            hasFocus);

        DefaultMutableTreeNode node = (DefaultMutableTreeNode) value;

        look at node.getUserObject();

        Font font = appropriate font;

        comp.setFont(font);

        return comp;

    }

}

```

> 注意：`getTreeRenderer` 的 `value` 参数是节点对象，而不是用户对象！如果你的树使用 `DefaultMutableTreeNode`，你必须在第二步中检索用户对象。

> 注意：`DefaultCellRenderer` 为所有节点使用同一个标签对象，再次调用该方法时必须将其设置回默认值。

列表 12.10 中的 `ClassNameTreeCellRenderer` 根据类将类名设置为正体或斜体字体。我们不想设置特定的字体，因为我们不想更改外观用于标签的任何字体。出于该原因，我们使用了标签的字体并从中推导出斜体字体。

此外，注意我们在 `ClassFrame` 构造函数中更改节点图标的方式。

组件。当用户选择树节点时，某些信息会在另一个窗口中显示。示例见图 12.29。当用户选择一个类时，该类的实例和静态变量将显示在右侧的文本区域中。

## ClassTree

![](img/240dbf1b84e081687f1e252bd386c684_958_0.png)

图 12.29：类浏览器

要获得这种行为，你需要安装一个树形选择监听器。该监听器必须实现 `TreeSelectionListener` 接口——该接口只有一个方法：

`void valueChanged(TreeSelectionEvent event)`

每当用户选择或取消选择树形节点时，该方法就会被调用。按照常规方式将监听器添加到树中：

`tree.addTreeSelectionListener(listener)`

你可以指定允许用户选择单个节点、连续的节点范围或任意的可能不连续的节点集合。`JTree` 类使用 `TreeSelectionModel` 来管理节点选择。你需要获取模型，并将选择状态设置为 `SINGLE_TREE_SELECTION`、`CONTIGUOUS_TREE_SELECTION` 或 `DISCONTINUOUS_TREE_SELECTION`。（不连续选择模式是默认值。）例如，在我们的浏览器中，我们希望允许选择单个类：

```java
int mode = SelectionModel.SINGLE_TREE_SELECTION;
tree.getSelection().setMode(mode);
```

除了选择模式外，你不需要担心树形选择模型。

> 注意：用户如何选择多个项目取决于外观（look-and-feel）。在 Metal 外观中，点击项目时按住 Ctrl 键将其添加到选择中，或者如果它已被选中则将其移除。点击项目时按住 Shift 键可以选择一个项目范围，从上一个选中的项目扩展到新项目。

要查找当前选择，请使用 `getSelectionPaths` 方法查询树：

```java
TreePath[] selectedPaths = tree.getSelectionPaths();
```

如果你将用户限制为单项选择，可以使用方便方法 `getSelectionPath`，它返回第一个选中的路径，或者在没有选择路径时返回 `null`。

> 注意：`TreeSelectionEvent` 类有一个 `getPaths` 方法，返回 `Tree` 对象的数组，但该数组描述的是变化，而不是当前选择。

列表 12.10 显示了类树的框架。程序显示了继承层次结构，并自定义了显示，以斜体显示抽象类。（单元渲染器请参见列表 12.11。）你可以在框架底部的文本字段中输入任何类的名称。按回键或点击“添加”按钮将该类及其父类添加到树中。你必须输入完整的包名，例如 `java.util.ArrayList`。

这个程序有点复杂，因为它使用反射来构建类树。这项工作在 `addClass` 方法内部完成。（细节并不重要。我们在本示例中使用类树是因为继承可以产生大量良好的树，而无需编写繁琐的代码。）该方法使用广度优先搜索算法，通过调用在前节中实现的 `findObject` 方法来查找当前类是否已经在树中。如果该类不在树中，我们将父类添加到树中，然后创建新的类节点并使节点可见。

当你选择一个树形节点时，右侧区域将填充所选类的字段。在构造函数中，我们将用户限制为单项选择并添加了树监听器。当 `valueChanged` 方法被调用时，我们忽略它的事件参数并请求当前的选择路径。一如既往，我们需要获取路径的最后一个节点并查找其用户对象。然后我们调用 `getFieldDescription` 方法，该方法使用反射组合包含所选类所有字段的字符串。

## 列表 12.10：vch12/treeRenderer/ClassTreeFrame.java

```java
package vch12.treeRenderer;

import module java.base;

import module java.desktop;

/**
  * 此框架显示类树、一个文本字段以及一个向树中添加更多类的
  * 的“添加”按钮。
  */

public class ClassTreeFrame extends JFrame {

  private static final DEFAULT_WIDTH = 400;

  private static final DEFAULT_HEIGHT = 300;

  private DefaultMutableTree root;

  private DefaultTreeModel model;

  private JTree tree;

  private JTextField textField;

  private JTextArea textArea;

  public TreeFrame() {

    setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

    // 树的根是 Object

    root = new DefaultMutableTreeNode(java.lang.Object.class);

    model = new DefaultTreeModel(root);

    tree = new JTree(model);

    // 添加此类以向树填充一些数据

    addClass(getClass());

    // 设置节点图标

    var renderer = new ClassTreeRenderer(new ImageIcon("images/red-ball.gif"));

    renderer.setSelectionIcon(new ImageIcon("images/yellow-ball.gif"));

    renderer.setLeafIcon(new ImageIcon("images/blue-ball.gif"));

    tree.setCellRenderer(renderer);

    // 设置选择模型

    tree.getSelectionModel().addTreeSelectionListener(e -> {

      // 用户选择了不同的节点--更新描述
```




```java
TreePath path = tree.getPath();

if (path == null) return;

var selectedNode = e.getSelectedNode().getPathComponent();

Class cls = (Class) selectedNode.getUserObject();

textArea.setText(cls.getDescription());

});

int mode = SelectionModel.SINGLE_SELECTION;

tree.getSelectionModel().setSelectionMode(mode);

}

}
```

`标签内似乎只包含了一小段代码片段，而没有包含后续的正文内容。根据您的要求，我将对`[content]`中存在的实际内容进行翻译。

以下是翻译后的内容：

```java
r.append(f.getType());

r.append(" ");

r.append(f.getName());

r.append("\n");

{

return r.toString();

}
```

# List 11.22 v2ch2/treeRender/ClassNameCellRenderer.java

```java
package v2ch2.treeRender;

import module java.base;

import module java.desktop;

/**
 * 此类以正体或斜体形式渲染名称。抽象类也是如此。
 */

public class ClassNameCellRenderer extends DefaultTreeCellRenderer {

    private PlainFont font = null;

    private PlainFont italicFont = null;

    public DefaultTreeCellRendererComponent(JTree tree, Object value, boolean selected, boolean expanded, boolean leaf, int row, boolean hasFocus) {

        super(tree, value, selected, expanded, leaf, row, hasFocus);

    }

    var node = (DefaultMutableTreeNode) value;

    Class<?> c = (Class<?>) node.getUserObject();

    // 第一次时，从正字体派生斜体字体

    if (plainFont == null) {

        plainFont = getFont();

        // 树单元渲染器有时会被带有空字体的标签调用

        if (italicFont == null) italicFont = plainFont.deriveFont(Font.ITALIC);

    }

    // 如果类是抽象的，将字体设置为斜体，否则设置为正体

    if (Modifier.isAbstract(c.getModifiers())) {

        setFont(italicFont);

    } else {

        setFont(plainFont);

    }

}
```

# `javax.swing.TreePath` 1.2

- `TreePath getSelection()`
- `TreePath[] getSelectionPaths()`

返回第一个选中的路径，或指向所有选中节点的路径数组。如果没有选中的路径，则两个方法都返回 `null`。

# `javax.swing.event.TreeSelectionListener` 1.2

- `void valueChanged(TreeSelection event)`

每当节点被选中或取消选中时都会调用。

## `javax.swing.event.TreeSelectionEvent` 1.2

- `TreePath getPath()`
- `TreePath[] getPaths()`

获取在此选择事件中发生变化的第一个路径或所有路径。如果你想知道当前的选择状态，而不是选择的变化，请调用 `JTree.getSelectionPaths`。

## 12.4.6. 自定义树模型

在最后一个示例中，我们实现了一个可以检查对象内容的程序，就像调试器工作的那样（见图 12.30）。

![](img/240dbf1b84e081687f1e252bd386c684_963_0.png)

**图 12.30：** 对象检查树

在继续之前，编译并运行该程序。每个节点对应一个实例字段。如果该字段是一个对象，则扩展它以查看其实例字段。该程序检查框架窗口的内容。如果你翻看几个实例字段，应该能找到一些熟悉的类。你也会对 Swing 用户界面组件在底层是多么复杂产生敬畏。

该程序的独特之处在于，树没有使用 `DefaultTreeModel`。如果你已经有了层次化组织的数据，你可能不想构建一个重复的树并担心保持两棵树的同步。这正是我们情况的情况——被检查的对象已经通过对象引用相互链接，因此没有复制链接结构。

`TreeModel` 接口只有几个方法。第一组方法允许 `JTree` 通过先获取根节点，然后获取子节点来查找树节点。`JTree` 只有在用户实际展开节点时才会调用这些方法。

```java
Object getRoot()

int getChildCount(Object parent)

Object getChild(Object parent, int index)
```

这个示例展示了为什么 `TreeModel` 接口像 `JTree` 类一样，不需要节点的显式名称。根节点及其子节点可以是任何对象。`TreeModel` 负责告诉 `JTree` 它们是如何连接的。

`TreeModel` 接口的下一个方法是 `getChild` 的反向：

```java
int getIndexOfOfChild(Object parent, Object child)
```

实际上，可以通过前三个方法来实现——参见列表 12.12 中的代码。

树模型告诉 `JTree` 哪些节点应该显示为叶子节点：

```java
boolean isLeaf(Object node)
```

如果你的代码更改了树，则需要通知树以便它可以重绘。树将自己添加为模型的 `TreeListener`。因此必须支持常用的监听器管理方法：

```java
void addTreeModelListener(TreeModelListener l)

void removeTreeModelListener(TreeModelListener l)
```

你可以在列表 12.13 中看到这些方法的实现。

当模型修改树时，它会调用 `TreeModelListener` 接口的四个方法之一：

```java
void nodesChanged(TreeModelEvent e)

void nodesInserted(TreeModelEvent e)

void nodesRemoved(TreeModelEvent e)

void treeStructureChanged(TreeModelEvent e)
```

`TreeModelEvent` 描述了更改的位置。组装描述插入或删除事件的树事件细节是技术性的。只有当你的树可以添加和删除节点时，才需要担心触发这些事件。在列表 12.12 中，我们展示了如何通过用新对象替换根节点来触发一个事件。

> **提示：** 为了简化触发事件的代码，使用收集监听器的 `javax.swing.EventListener` 便利类。列表 12.13 的最后三个方法展示了如何使用该类。

最后，如果用户编辑树节点，你的模型会被调用并传递：

```java
void valueForPathChanged(TreePath path, Object newValue)
```

如果你不允许编辑，则此方法永远不会被调用。

如果你不需要支持编辑，构建树模型很容易。实现以下三个方法：

```java
Object getRoot()

getChildCount(Object parent)

getChild(Object parent, int index)
```

这些方法描述了树的结构。按照列表 12.12 提供其他五个方法的常规实现。你现在准备好显示你的树了。

现在让我们转向示例实现。我们的树将包含类型为 `Variable` 的对象。

> 注意：如果我们使用了 `DefaultTreeModel`，我们的节点将是用户对象为 `Variable` 的 `DefaultMutableNode` 对象。

例如，你检查变量：

`Employee joe;`

该变量类型为 `Employee.class`，名称为 `"joe"`，值为 `joe`。如果类型是基本类型，你必须使用对象包装类 `Double.valueOf(salary)`。

```java
public ObjectInspectorframe() {

    setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

    // inspect this frame object

    var v = new Variable(getClass(), "this", this);

    var model = new ObjectTreeModel();

    model.setRoot(v);

    // construct and show tree

    Tree tree = new JTree(model);

    add(new JScrollPane(tree), BorderLayout.CENTER);

}
```

# 列表 12.13 vch12/treeModel/ObjectModel.java

```java
package vch12.treeModel;

import module java.base;

import module java.desktop;

/**
 * 该模型描述了 Java 对象的树形结构。子节点是存储
 * 在实例变量中的对象。
 */

public class ObjectTreeModel implements TreeModel {

    private Variable root;

    private EventEventListener listenerList = newEventListenerList();

    /**
     * 构建一个空树。
     */

    public ObjectTreeModel() {

        root = null;

    }

    /**
     * 将根节点设置为指定的变量。
     * @param v 被此树描述的变量
     */

    public void setRoot(Variable v) {

        Variable oldRoot = v;

        root = v;

        fireTreeStructurechanged(oldRoot);

    }

    public Object getRoot() {

        return root;

    }

    public int getChildCount(Object parent) {

        return ((Variable) parent).getFields().size();

    }

    public Object getChild(Object parent, int index) {

        ArrayList fields = ((Variable) parent).getFields();

        Field f = (Field) fields.get(index);

        Object parentValue = ((Variable) parent).getValue();

        try {

            return new Variable(f.getType(), f.getName(), f(parentValue));

        } catch (IllegalAccessException e) {

            return null;

        }

    }

    public int getIndexOfOfChild(Object parent, Object child) {

        int n = getChildCount();

        for (int i = 0; i < n; i++) {

            if (getChild(parent, i).equals(child)) return i;

        }

        return -1;

    }

    public boolean isLeaf(Object node) {

        return getChildCount(node) == 0;

    }

    public void valueForPathChanged(TreePath path, Object newValue) {

    }

    public void addTreeModelListener(TreeModelListener l) {

        listenerList.add(TreeModelListener.class, l);

    }

    public void removeTreeModelListener(TreeModelListener l) {

        listenerList.remove(TreeModelListener.class, l);

    }

    protected void treeStructureChanged(Object root) {

        var event = new TreeModelEvent(this, new Object[]{root});

        for (TreeModelListener l : listenerList.getListeners(TreeModelListener.class)) {

            l.treeStructureChanged(event);

        }

    }

}
```

# 列表 12.14 vch12/treeModel/Variable.java

```java
package vch12.treeModel;

import module java.base;

/**
 * 一个具有类型、名称和值的变量。
 */

public class Variable {

    private Class<?> type;

    private String name;

    private Object value;

    private ArrayList<Field> fields;

    /**
     * 构建一个变量。
     * @param atype 类型
     * @param name 名称
     * @param avalue 值
     */

    public Variable(Class<?> atype, String name, Object avalue) {

        type = atype;

        name = name;

        value = avalue;

        fields = new ArrayList<>();

        // 如果我们有一个不扩展字符串和

        // 空值的类类型，则查找所有字段

        if (!type.isPrimitive() && !type.isArray() && !type.equals(String.class)) {

            value = null;

            // 从该类及其所有超类获取字段

            for (Class<?> c = type.getClass(); c != null; c = c.getSuperClass()) {

                for (Field f : c.getDeclaredFields()) {

                    AccessibleObject.setAccessible(f, true);

                }

            }

            // 获取所有静态字段

            for (Field f : fields) {

                if (!Modifier.isStatic(f.getModifiers())) fields.add(f);

            }

        }

    }

    /**
     * 获取此变量的值。
     * @return 值
     */

    public Object getValue() {

        return value;

    }

    /**
     * 获取该变量的所有非静态字段。
     * @return 描述字段的变量数组
     */

    public ArrayList<Field> getFields() {
```




```java
return fields;
}

public String toString() {
    String r = name + "";

    if (type.isPrimitive()) {
        r += value;
    } else if (type.equals(String.class)) {
        r += value;
    } else if (value == null) {
        r += "null";
    }

    return r;
}
```

当然，在许多实际情况下，你并不需要所有的步骤。2D 图形上下文的设置有合理的默认值；只有当你想要偏离默认值时，才更改设置。

在接下来的章节中，你将看到如何描述形状、描边、填充、变换和组合规则。

各种方法只是设置 2D 图形上下文的状态。它们不会引起任何绘制。同样，当你构建`Shape`对象时，也不会发生绘制。只有当你调用`draw`或`fill`时，形状才会被渲染。此时，新的形状会在渲染流水线中计算（见图 12.31）。

# 图 12.31：渲染流水线

在渲染流水线，会执行以下步骤来渲染形状：

1. 对形状的路径进行描边。
2. 对形状进行变换。
3. 对形状进行裁剪。如果形状与裁剪区域没有交集，则处理停止。
4. 填充裁剪后形状的剩余。
5. 将填充形状的像素与现有像素进行组合。（在图 12.31 中，圆是现有像素的一部分，杯子形状叠加在它上面。）

在下一节中，你将看到如何定义形状。然后，我们将转向 2D 图形上下文的设置。

| java.awt.Graphics2D 1.2 |
| :--- |
| `void draw(Shape s)` 使用当前画笔绘制给定形状的轮廓。 |
| `void fill(Shape s)` 使用当前画笔填充给定形状的内部。 |

## 12.5.2. Shape 类层次结构

这里是`Graphics`类中用于绘制形状的一些方法：

- `drawLine`
- `drawRectangle`
- `drawRoundRect`
- `draw3DRect`
- `drawPolygon`
- `drawPolyline`
- `drawOval`
- `drawArc`

还有对应的`fill`方法。这些方法自 JDK 1.0 以来一直存在于`Graphics`类中。Java 2D API 使用了完全不同的面向对象的方法。它使用的不是方法，而是类：

- `Line2D`
- `Rectangle2D`
- `RoundRectangle2D`
- `Ellipse2D`
- `Arc2D`
- `QuadCurve2D`
- `CubicCurve2D`
- `GeneralPath`

这些类都实现了`Shape`接口，我们将在接下来的章节中进行检查。

`Line2D`、`Rectangle2D`、`RoundRectangle2D`、`Ellipse2D`和`Arc2D`类分别对应`drawLine`、`drawRectangle`、`drawRoundRect`、`drawOval`和`drawArc`方法。（“3d矩形”的概念已经消失——没有对应的`draw3DRect`方法。）Java 2D API 提供了两个额外的类——二次和三次曲线，我们将在本节中讨论。没有`Polygon2D`类；相反，`GeneralPath`描述由直线、二次三次曲线组成的路径。我们可以使用`GeneralPath`来描述多边形；我们将在本节后面向你展示方法。

要绘制形状，首先创建一个实现`Shape`接口类的对象，然后调用`Graphics2D`类的`draw`方法。

这些类：

- `Rectangle2D`
- `RoundRectangle2D`
- `Ellipse2D`
- `Arc2D`

都继承自一个公共父类`RectangularShape`；椭圆和弧不是矩形，但它们有一个边界矩形（见图 12.32）。

> 图 12.32：椭圆和弧的边界矩形

每个名称带有“2D”的类都有两个子类，用于指定`float`或`double`数量的坐标。在第一卷中，你已经遇到过`Rectangle2D.Float`和`Rectangle2D.Double`。

其他类也使用了相同的方案，例如`Arc2D.Float`和`Arc2D.Double`。

内部，所有图形都使用`float`坐标，因为`float`使用的存储空间较少，但对于几何计算具有足够的精度。然而，Java 编程语言处理`float`数字稍微繁琐。因此，图形类的方法使用`double`参数和返回值。当你仅构造 2D 对象时，你需要在`float`和`double`坐标的构造函数之间进行选择。例如：

```java
var floatRect = new Rectangle2D.Float(5F, 10F, 7.5F, 15F);
var doubleRect = new Rectangle2D.Double(5, 10, 7.5, 15);
```

`Xxx2D.Float`和`Xxx2D.Double`类是`Xxx2D`类的子类。在对象构造后，记住子类几乎没有好处，你只需要像上面的代码示例那样，将构造的对象存储在父类变量中即可。

从这些奇怪的名字中可以看出，`Xxx2D.Float`和`Xxx2D.Double`类也是`Xxx2D`类的内部类。这仅仅是为了在语法上的小便利，以避免类名过于膨胀。

最后，`Point2D`类描述了一个具有 x 和 y 坐标的点。点被用于定义形状，但它们本身并不是形状。

[图 12.33](https://docs.oracle.com/javase/tutorial/java/2d/images/fig1233.png)显示了形状类之间的关系。但是省略了`Double`和`Float`子类。来自预 2D 库的遗留类标记为灰色填充。

> 图 12.33：形状类之间的关系

## 12.5.3. 构建形状

你已经知道如何使用`Rectangle2D`、`Ellipse2D`和`Line2D`。在本节中，我们将学习如何处理其他形状。对于`Round2D`形状，指定圆角、宽度和高度。例如：

```java
var r = new Rectangle2D.Float(5F, 10F, 7.5F, 15F);
```

> 图 12.34：构建 Round2D

构建弧，指定边界框、起始角度和闭合类型。例如：

```java
var a = new Arc2D.Double(5, 10, 7.5, 15, 0, 90, Arc2D.OPEN);
```

> 图 12.35：构建 Arc

二次曲线并不灵活，实践中并不常用。然而，三次曲线（例如由`Cubic`类绘制的曲线）非常常见。通过组合连接处斜率相同的曲线，你可以创建复杂的、光滑的形状。更多信息请参阅 John F. 的《Computer Graphics: Principles and Practice》。

你可以构建任意的线段、二次和三次曲线，并将它们存储在`GeneralPath`对象中。使用`moveTo`方法指定路径的第一个坐标，例如：

```java
var path = new GeneralPath();
path.moveTo(10, 20);
```

可以通过调用`lineTo`、`quadTo`或`curveTo`来扩展路径。这些方法通过直线、二次曲线或三次曲线扩展路径。调用`lineTo`时提供终点。对于两个曲线方法，提供控制点，然后是终点。

```java
path.lineTo(20, 30);
path.curveTo(controlX, controlY, control2X, control2Y, endX, endY);
```

调用`close`方法关闭路径。它画一条返回路径起点的直线。

要制作多边形，只需使用`moveTo`到达第一个顶点，然后重复调用`LineTo`访问其他顶点。最后，调用`close`关闭多边形。列表 12.15 中的程序显示了更详细的内容。

通用路径不需要是连接的。你可以随时调用`moveTo`来启动一个新的段路径。

最后，你可以使用`append`方法将任意`Shape`对象添加到通用路径中。形状的轮廓会被添加到路径末尾。

如果`append`方法为`true`，则新形状应该连接到路径上的最后一个点，否则为`false`。例如，调用：

```java
Rectangle2D r = . . .;
path.append(r, false);
```

将矩形的轮廓添加到路径中，但不将其与现有路径连接。

但如果：

```java
path.append(r, true);
```

会从路径的终点到矩形的起始点添加一条直线，并将矩形的轮廓添加到路径中。

列表 12.15 中的程序允许你创建示例路径。为组合框选择一个形状生成器。该程序包含以下形状的生成器：

- 直线
- 矩形、圆角矩形和椭圆
- 弧（除了弧本身外，还显示边界矩形以及起始和结束角度的线）
- 多边形（使用`GeneralPath`）
- 二次曲线和三次曲线

使用鼠标调整控制点。当你移动它们时，形状会连续地重绘自身。

该程序有点复杂，因为它处理了多种形状并支持控制点的拖拽。

抽象超类`ShapeMaker`封装了形状生成类的共同性。每个形状都有固定数量的控制点，用户可以移动这些点。`getPointCount`方法返回抽象方法：

```java
makeShape(Point2D[])
```

该方法根据控制点的当前位置计算实际形状。`toString`方法返回类名，以便`ShapeMaker`对象可以简单地放入`JComboBox`中。

为了启用控制点的拖拽，`ShapePanel`类同时处理鼠标事件和移动事件。如果鼠标在矩形上被按下，随后的鼠标拖拽将移动该矩形。

大多数形状生成器类都是简单的——它们的`makeShape`方法只需构造并返回请求的形状。然而，`ArcMaker`类需要计算变形后的起始和结束角度。此外，为了证明计算确实是正确的，返回的形状是一个`GeneralPath`，其中包含了弧本身、边界矩形以及从弧的中心到角度控制点的线（见图 12.39）。

![](img/240dbf1b84e081687f1e252bd386c684_978_0.png)

图 12.39：ShapeDemo 程序

```java
Listing 12.15 v2ch12/shape/ShapeDemo.java

package v2ch12.shape;

import java.base;
import java.desktop;
import java.awt.event.MouseEvent;

/*
 * 此程序演示了各种 2D 形状。
 */
class ShapeDemo {
    void main() {
        invokeLater(() -> {
            var frame = new ShapeTestFrame();
            frame.setTitle("ShapeTest");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}

/*
 * 此程序包含一个组合框，用于选择形状和绘制它的组件。
 */
class ShapeTestFrame extends JFrame {
    public ShapeTestFrame() {
        var combo = new ShapeComponent();
        add(combo, BorderLayout.CENTER);
        var comboBox = new JComboBox<ShapeMaker>();
        comboBox.addItem(new LineMaker());
        comboBox.addItem(new RectangleMaker());
        comboBox.addItem(new RoundRectangleMaker());
        comboBox.addItem(new EllipseMaker());
        comboBox.addItem(new ArcMaker());
        comboBox.addItem(new PolygonMaker());
        comboBox.addItem(new QuadCurveMaker());
        comboBox.addItem(new CubicCurveMaker());

        comboBox.addActionListener(() -> {
            ShapeMaker shapeMaker = (ShapeMaker) comboBox.getSelectedItem();
            comp.setShapeMaker(shapeMaker);
        });

        add(comboBox, BorderLayout.NORTH);
        comp.setShapeMaker(comboBox.getItemAt(0));
        pack();
    }
}

/*
 * 此组件绘制一个形状并允许用户移动定义它的点。
 */
class Shape extends JComponent {
    private static final Dimension PREFERRED_SIZE = new Dimension(300, 200);
    private Point2D[] points;
    private static RandomGenerator generator = RandomGenerator.getDefault();
    private static int SIZE = 0;
    private int pointCount;

    private ShapeMaker shapeMaker;

    public ShapeComponent() {
        addMouseListener(new MouseAdapter() {
            public void mousePressed(MouseEvent e) {
                Point p = e.Point();

                for (int i = 0; i < points.length; i++) {
                    double x = points[i].getX() - SIZE / 2;
                    double y = points[i].getY() - SIZE / 2;
                    Rectangle2D r = new Rectangle2D.Double(x, y, SIZE, SIZE);

                    if (r.contains(p)) {
                        current = i;
                        return;
                    }
                }
            }

            public void mouseReleased(MouseEvent e) {
                current = -1;
            }
        });

        addMouseMotionListener(new MouseMotionAdapter() {
            public void mouseDragged(MouseEvent e) {
                if (current == -1) return;
                points[current] = e.Point();
                repaint();
            }
        });

        current = -1;
    }

    /*
     * 设置一个形状生成器并用随机点集初始化它。
     * @param shapeMaker 一个根据点集定义形状的生成器
     */
    public void setShapeMaker(ShapeMaker shapeMaker) {
        shapeMaker = shapeMaker;
        pointCount = shapeMaker.getPointCount();

        for (int i = 0; i < pointCount; i++) {
            double x = generator.nextDouble() * getWidth();
            double y = generator.nextDouble() * getHeight();
            points[i] = new Point2D.Double(x, y);
        }

        repaint();
    }

    public void paintComponent(Graphics g) {
        if (points == null) return;

        Graphics2D g2 = (Graphics2D) g;

        for (int i = 0; i < points.length; i++) {
            double x = points[i].getX() - SIZE / 2;
            double y = points[i].getY() - SIZE / 2;
            g2.draw(new Rectangle2D.Double(x, y, SIZE, SIZE));
        }

        g2.draw(shapeMaker.makeShape(points));
    }
}
```



```java
public Dimension getPreferredSize() {
    return PREFERRED_SIZE;
}
```

```java
/**
 * 形状生成器可以点集创建一个形状。
 * 子类必须在 makeShape 方法中返回形状。
 */
abstract class ShapeMaker {
    private int pointCount;

    /**
     * 构造生成器。
     *
     * @param pointCount 定义此形状的点数
     */
    public ShapeMaker(int pointCount) {
        this.pointCount = pointCount;
    }

    /**
     * 获取定义此形状的点数。
     *
     * @return 点数
     */
    public int getPointCount() {
        return pointCount;
    }

    /**
     * 根据集创建一个形状。
     *
     * @param p 定义形状的点
     * @return 由点定义的形状
     */
    public abstract Shape makeShape(Point2D[] p);

    public String toString() {
        return getClass().getName();
    }
}
```

```java
/**
 * 连接两个点的线。
 */
class LineMaker extends ShapeMaker {
    public LineMaker() {
        super(2);
    }

    public Shape makeShape(Point2D[] p) {
        return new Line2D.Double(p[0], p[1]);
    }
}
```

```java
/**
 * 连接两个角的矩形。
 */
class RectangleMaker extends ShapeMaker {
    public RectangleMaker() {
        super(2);
    }

    public Shape makeShape(Point2D[] p) {
        var s = new Rectangle2D.Double();
        s.setFrameFromDiagonal(p[0], p[1]);
        return s;
    }
}
```

```java
/**
 * 连接两个给定点的圆角矩形。
 */
class RoundRectangleMaker extends ShapeMaker {
    public RoundRectangleMaker() {
        super(2);
    }

    public Shape makeShape(Point2D[] p) {
        var s = new Rectangle2D.Double(0, 0, 20, 20);
        s.setFrameFromDiagonal(p[0], p[1]);
        return s;
    }
}
```

```java
/**
 * 在带有两个给定角的边界矩形内创建一个椭圆。
 */
class EllipseMaker extends ShapeMaker {
    public EllipseMaker() {
        super(2);
    }

    public Shape makeShape(Point2D[] p) {
        var s = new EllipseD.Double();
        s.setFrameFromDiagonal(p[0], p[1]);
        return s;
    }
}
```

```java
/**
 * 在带有两个给定角的边界矩形内创建一个弧，并带有从边界矩形中心发射到两个给定点的起始和结束角度线。为了证明角度计算的正确性，返回的形状是弧、边界矩形和线。
 */
class ArcMaker extends ShapeMaker {
    public ArcMaker() {
        super(4);
    }

    public Shape makeShape(Point2D[] p) {
        var center = new Point2D.Double(
            p[0].getX() + p[1].getX() / 2,
            p[0].getY() + p[1].getY() / 2
        );
        var width = Math.abs(p[1].getX() - p[0].getX());
        var height = Math.abs(p[1].getY() - p[0].getY());
        var skewedStart = Math.atan2(
            p[0].getY() - center.getY(),
            p[0].getX() - center.getX()
        );
        var skewedEnd = Math.atan2(
            p[1].getY() - center.getY(),
            p[1].getX() - center.getX()
        );
        var skewedAngleDifference = skewedEnd - skewedStart;

        if (skewedStart < 0) {
            skewedStart += 360;
        }
        if (skewedAngleDifference < 0) {
            skewedAngleDifference += 360;
        }

        var s = new Arc2D.Double(
            0,
            0,
            0,
            0,
            skewedStart,
            skewedAngleDifference
        );
        s.setFrameFromDiagonal(p[0], p[1]);

        var g = new GeneralPath();
        g.append(s);

        var r = new Rectangle2D.Double();
        r.setFrameFromDiagonal(p[0], p[1]);
        g.append(r);

        g.append(new Line2D.Double(center, p[2]));
        g.append(new Line2D.Double(center, p[3]), false);

        return g;
    }
}

/**
 * 创建一个由六个顶点定义的多边形。
 */
class PolygonMaker extends ShapeMaker {
    public PolygonMaker() {
        super(6);
    }

    public Shape makeShape(Point2D p) {
        var s = new Path2D();
        s.moveTo((float) p[0].getX(), (float) p[0].getY());

        for (int i = 1; i < p.length; i++) {
            s.lineTo((float) p[i].getX(), (float) p[i].getY());
        }

        s.closePath();
        return s;
    }
}

/**
 * 创建一个由两个点和一个控制点定义的二次曲线。
 */
class QuadCurveMaker extends ShapeMaker {
    public QuadCurveMaker() {
        super(3);
    }

    public Shape makeShape(Point2D p) {
        return new Quad2D.Double(
            p[0].getX(),
            p[0].getY(),
            p[1].getX(),
            p[1].getY(),
            p[2].getX(),
            p[2].getY()
        );
    }
}

/**
 * 创建一个由两个点和两个控制点定义的三次曲线。
 */
class CubicCurveMaker extends ShapeMaker {
    public CubicCurveMaker() {
        super(4);
    }

    public Shape makeShape(Point2D p) {
        return new Cubic2D.Double(
            p[0].getX(),
            p[0].getY(),
            p[1].getX(),
            p[1].getY(),
            p[2].getX(),
            p[2].getY(),
            p[3].getX(),
            p[3].getY()
        );
    }
}
```

## `java.awt.Rectangle2D.Double(double x, double y, double width, double height, double arcWidth, double arcHeight)`

- `Rectangle2D.Double(double x, double y, double width, double height, double arcWidth, double arcHeight)` 根据给定的边界矩形和弧尺寸构造一个圆矩形。请参阅 `arcWidth` 和 `arcHeight` 参数的解释。

## `java.awt.geom.Arc2D.Double` 1.2

- `Arc2D.Double(double x, double y, double w, double h, double startAngle, double arcAngle, int type)` 根据给定的边界矩形、起始角度和弧角度构造一个弧。`startAngle` 和 `arcAngle` 如下所示。`type` 是 `Arc2D.OPEN`、`Arc2D.PIE` 和 `Arc2D.CHORD` 之一。

## `java.awt.geom.QuadCurve2D.Double` 1.2

- `QuadCurve2D.Double(double x1, double y1, double ctrlx, double ctrly, double x2, double y2)` 从起点、控制点和终点构造一条二次曲线。

## `java.awt.geom.CubicCurve2D.Double` 1.2

- `CubicCurve2D.Double(double x1, double y1, double ctrlx1, double ctrly1, double ctrlx2, double ctrly2, double x2, double y2)` 从起点、两个控制点和终点构造一条三次曲线。

## `java.awt.geom.GeneralPath` 1.2

- `GeneralPath()` 构建一个空通用路径。

## `java.awt.geom.Path2D.Float` 6

- `void moveTo(float x, float y)` 将 `(x, y)` 设置为当前点——即下一个段的起点。
- `void lineTo(float x, float y)`
- `void quadTo(float ctrlx, float ctrly, float x, float y)`
- `void curveTo(float ctrlx1, float ctrly1, float ctrl2x, float ctrly2, float x, float y)` 从当前点到终点 `(x, y)` 绘制直线、二次曲线或三次曲线，并使终点连接当前点。

## `java.awt.geom.Path2D` 6

- `void append(Shape s, boolean connect)` 将给定形状的轮廓添加到通用路径中。如果 `connect` 为 `true`，则用直线将通用路径的当前点与所添加形状的起点连接。
- `void closePath()` 通过从当前点到路径中的第一个点画一条直线来关闭路径。

## 12.5.4. Areas

在前面的节中，你已经了解了如何通过构造由线条和曲线组成的通用路径来指定复杂形状。通过使用足够数量的线条和曲线，你可以基本上绘制任何形状。例如，你在屏幕和打印输出上看到的字体字符是由线条和二次或三次曲线组成的。

有时，通过组合形状来描述形状更为简单，Java 2D API 支持以下几种操作：

- `add`：将第二个区域添加到第一个区域中。
- `subtract`：从第一个区域中减去第二个区域。
- `intersect`：保留两个区域的交集部分。
- `exclusiveOr`：保留位于两个区域之一但不在两者交集中的区域。

## 12.5.5. Strokes

角接限制（miter limit）是尖端距离与描边宽度的比值。当两条线以非常锐的角度相交时，会使用斜角连接（bevel join）代替，以防止产生极长的尖端。10 的角接限制对应大约 11 度的角度。你可以在 `BasicStroke` 构造函数中指定这些选择：

```java
g2.setStroke(new BasicStroke(
    10.0F,
    BasicStroke.CAP_ROUND,
    BasicStroke.JOIN_ROUND
));

g2.setStroke(new BasicStroke(
    10.0F,
    BasicStroke.CAP_BUT,
    BasicStroke.JOIN_MITER,
    15.0F /* 角接限制 */
));
```

最后，你可以通过设置虚线创建虚线。在列表 12.16 的程序中，你可以选择一个用摩斯密码拼出 SOS 的虚线。虚线是一个 `float[]` 数组，包含了“开启”和“关闭”间隔的长度。在构造 `BasicStroke` 时可以指定虚线和虚相位：

```java
float[] dashPattern = { 10, 10, 10, 10, 10, 30, 30, . . . };

g2.setStroke(new BasicStroke(
    10.0F,
    BasicStroke.CAP_BUT,
    BasicStroke.JOIN_MITER,
    10.0F /* 角接限制 */,
    dashPattern,
    0 /* dash相位 */
));
```

![](img/240dbf1b84e081687f1e252bd386c684_987_0.png)

# 图 12.44：`StrokeDemo` 程序

该程序与列表 12.15 中的程序类似。鼠标监听器记录线段末端的点击操作，而鼠标移动监听器监控末端的拖动。一组单选按钮用于信号端点样式、连接处样式以及实线或虚线的选择。`StrokePanel` 类的 `paintComponent` 方法构造了一个 `GeneralPath`，该路径由两条线段组成，连接连接了用户可以用鼠标移动的三个点。它根据用户的选择构造一个 `BasicStroke`，最后绘制路径。

# 列表 12.16 `v2ch12.stroke/StrokeDemo.java`

```java
package v2ch12.stroke;

import java.awt.*;
import java.awt.event.MouseEvent;

/* 此程序演示了不同的描边类型。 */
class StrokeDemo {
    public void main() {
        EventQueue.invokeLater(() -> {
            var frame = new StrokeTestFrame("StrokeTest");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}
```

```java
/**
 * 此框架允许用户选择端点、连接和样式，并显示结果描边。
 */
```



```java
class StrokeTestFrame extends JFrame {
    private StrokeComponent canvas;
    private JPanel buttonPanel;

    public StrokeTestFrame() {
        canvas = new StrokeComponent();
        add(canvas, BorderLayout.CENTER);

        buttonPanel = new JPanel();
        buttonPanel.setLayout(new GridLayout(3, 3));
        add(buttonPanel, BorderLayout.NORTH);

        var group1 = new ButtonGroup();
        makeCapButton("Cap", BasicStroke.CAP_BUT, group1);
        makeCapButton("Round", BasicStroke.CAP_ROUND, group1);
        makeCapButton("Square", BasicStroke.CAP_SQUARE, group1);

        var group2 = new ButtonGroup();
        makeJoinButton("Miter", BasicStroke.JOIN_MITER, group2);
        makeJoinButton("Bevel", BasicStroke.JOIN_BEVEL, group2);
        makeJoinButton("Round", BasicStroke.JOIN_ROUND, group2);

        var group3 = new ButtonGroup();
        makeDashButton("Solid Line", false, group3);
        makeDashButton("Dashed Line", true, group3);
    }

    /**
     * 创建一个单选按钮来改变端点样式。
     * @param label 标签文本
     * @param style 样式
     * @param group 单选按钮组
     */
    private void makeCapButton(String label, final int style, ButtonGroup group) {
        // 选择组中的第一个
        boolean selected = group.getButtonCount() == 0;
        var button = new JRadioButton(label, selected);
        buttonPanel.add(button);
        group.add(button);
        button.addActionListener(() -> canvas.setCap(style));
    }

    /**
     * 创建一个单选按钮来改变连接处样式。
     * @param label 标签文本
     * @param style 样式
     * @param group 单选按钮组
     */
    private void makeJoinButton(String label, final int style, ButtonGroup group) {
        // 选择组中的第一个
        boolean selected = group.getButtonCount() == 0;
        var button = new JRadioButton(label, selected);
        buttonPanel.add(button);
        group.add(button);
        button.addActionListener(() -> canvas.setJoin(style));
    }

    /**
     * 创建一个单选按钮来设置实线或虚线。
     * @param label 标签文本
     * @param false 表示实线，true 表示虚线
     * @param group 单选按钮组
     */
    private void makeDashButton(String label, final boolean dash, ButtonGroup group) {
        // 选择组中的第一个
        boolean selected = group.getButtonCount() == 0;
        var button = new JRadioButton(label, selected);
        buttonPanel.add(button);
        group.add(button);
        button.addActionListener(() -> canvas.setDash(dash));
    }
}

/**
 * 此组件绘制两条条连接的线，使用不同的描边对象，
 * 并允许用户拖动定义线的三个点。
 */
class StrokeComponent extends JComponent {
    private static final Dimension PREFERRED_SIZE = new Dimension(400, 400);
    private int size = 10;

    private Point2D[] points;
    private int current;
    private float width;
    private int cap;
    private int join;
    private boolean dash;

    public StrokeComponent() {
        addMouseListener(new MouseAdapter() {
            public void mousePressed(MouseEvent event) {
                Point p = event.getPoint();
                for (int i = 0; i < points.length; i++) {
                    double x = points[i].getX() - PREFERRED_SIZE.getWidth() / 2;
                    double y = points[i].getY() - PREFERRED_SIZE.getHeight() / 2;
                    if (new Rectangle2D(x, y, PREFERRED_SIZE.getWidth(), PREFERRED_SIZE.getHeight()).contains(p)) {
                        current = i;
                    }
                }
            }

            public void mouseReleased(MouseEvent event) {
                current = -1;
            }
        });

        addMouseMotionListener(new MouseAdapter() {
            public void mouseDragged(MouseEvent event) {
                if (current != -1) {
                    // 更新点的逻辑在此
                }
            }
        });

        points = new Point2D[3];
        // 省略点的初始化
    }

    public void setCap(int cap) {
        this.cap = cap;
    }

    public void setJoin(int join) {
        this.join = join;
    }

    public void setDash(boolean dash) {
        this.dash = dash;
    }

    @Override
    protected void paintComponent(Graphics g) {
        super.paintComponent(g);
        Graphics2D g2 = (Graphics2D) g;
        Path2D path = new Path2D();
        path.moveTo(points[0].getX(), points[0].getY());

        for (int i = 1; i < points.length; i++) {
            path.lineTo(points[i].getX(), points[i].getY());
        }

        BasicStroke stroke;
        if (dash) {
            stroke = new BasicStroke(width, BasicStroke.CAP_BUT, BasicStroke.JOIN_MITER, 10, new float[]{10}, 0);
        } else {
            stroke = new BasicStroke(width);
        }

        g2.setStroke(stroke);
        g2.draw(path);
    }
}
```

## 12.5.6. Paint

当填充形状时，其内部会被填充覆盖。使用`setPaint`方法将填充样式设置为实现`Paint`接口的对象。Java 2D 提供了三个此类类：

- `Color`类：实现了`Paint`接口。要用实色填充形状，只需传递`Color`对象，例如`g2.setPaint(Color.red)`。
- `GradientPaint`类：通过在两个给定的颜色值之间进行插值来变化颜色（见图 12.45）。

![](img/240dbf1b84e081687f1e252bd386c684_991_0.png)

- `TexturePaint`类：使用图像的重复填充区域（见图 12.46）。

![](img/240dbf1b84e081687f1e252bd386c684_991_1.png)

你可以通过指定两个点以及这些点对应的颜色来构造一个`GradientPaint`对象。

```java
g2.setPaint(new GradientPaint(p1, Color.RED, p2, Color.YELLOW));
```

颜色沿连接点的直线进行插值。颜色沿该连接线的垂直线方向保持不变。超出直线端点的点将获得端点的颜色。

或者，如果你在调用`GradientPaint`构造函数时对循环参数为`true`：

```java
g2.setPaint(new GradientPaint(p1, Color.RED, p2, Color.YELLOW, true));
```

随后，颜色变化循环并在超出端点后持续变化。

要构造一个`TexturePaint`对象，请指定一个`BufferedImage`和锚点矩形。

```java
g2.setPaint(new TexturePaint(bufferedImage, anchorRectangle));
```

我将在本章稍后讨论图像时介绍`BufferedImage`类。获取缓冲图像最简单的方法是读取图像文件：

```java
bufferedImage = ImageIO.read(new File("blue-ball.gif"));
```

锚点矩形在 x 和 y 方向上无限扩展，以填满整个坐标平面。图像被缩放以适应锚点，然后复制到每个瓦片中。

## `java.awt.Graphics2D` 1.2

- `void setPaint(Paint s)`

将此图形上下文的绘制画具设置为实现`Paint`接口的给定对象。

## `java.awt.GradientPaint` 1.2

- `GradientPaint(float x1, float y1, Color color1, float x2, float y2, Color color2)`
- `GradientPaint(float x1, float y1, Color color1, float x2, float y2, Color color2, boolean cyclic)`
- `GradientPaint(Point2D p1, Color color1, Point2D p2, Color color2)`
- `GradientPaint(Point2D p1, Color color1, Point2D p2, Color color2, boolean cyclic)`

构造一个渐变绘制对象，用颜色填充形状，使得起点用`color1`填充，终点用`color2`填充，之间的颜色进行线性插值。颜色是垂直于起点和终点连线的等值线。默认情况下，渐变绘制不是循环的——也就是说，超出起点和终点的点将与起点和终点的相同的颜色。如果渐变绘制是循环的，则颜色将继续插值，首先返回起点颜色，并在两个方向上无限重复。

## `java.awt.TexturePaint` 1.2

- `TexturePaint(BufferedImage texture, Rectangle2D anchor)`

创建一个纹理绘制对象。锚点矩形定义了要绘制空间的平铺；它在 x 和 y 方向上无限重复，纹理图像被缩放以适应每个瓦片。

## 12.5.7. 坐标变换

假设你需要绘制一个对象，例如汽车。根据制造商的规格，你知道它的高度、轴距和总长度。当然，你可以算出所有的像素位置，假设每米有若干像素。然而，有一种更简单的方法：你要求图形上下文为你自己完成转换。

```java
g2.scale(pixelsPerMeter, pixelsPerMeter);
g2.draw(new Line2D.Double(coordinates in meters)); // 转换为像素
并绘制缩放后的线条
```

`Graphics2D`类的方法将图形上下文的坐标变换设置为缩放变换。该变换将用户坐标（用户指定的单位）转换为设备坐标（像素）。图 12.47 显示了变换是如何运作的。

图 12.47：用户坐标和设备坐标

坐标变换在实践中非常有用。它们允许你使用方便的坐标值工作。图形上下文负责将它们转换为像素的脏活。

有四种基本的变换：

- 缩放（Scaling）：放大或缩小所有到某个固定点的距离。
- 旋转（Rotation）：绕固定中心旋转所有点。
- 平移（Translation）：按固定量移动点。
- 剪切（Shear）：固定一条线，并使其与之平行的线按与固定线距离成正比的量“滑动”。

图 12.48 显示了这四种基本变换如何作用于单位正方形。

图 12.48：基本变换

`Graphics2D`类的`scale`、`rotate`、`translate`和`shear`方法将图形上下文的坐标变换设置为这些基本变换之一。

你可以组合变换。例如，你想旋转形状并将其尺寸增加倍；同时提供旋转变换和缩放变换：

```java
g2.rotate(angle);
g2.scale(2, 2);
g2.draw(..);
```

在这种情况下，你提供变换的顺序并不重要。然而，对于大多数变换来说，顺序是重要的。例如，如果你想旋转和剪切，那么先提供哪种变换就会产生区别。你需要明确你的意图。图形内容将按照与你提供的顺序相反的顺序应用变换——也就是说，你提供的最后一个变换最先应用。

你可以提供任意数量的变换。例如，考虑以下变换序列：

```java
g2.translate(x, y);
g2.rotate(a);
g2.translate(-x, -y);
```

最后一个变换（最先应用的）将点`(x, y)`移动到原点。第二个变换绕原点以某个角度旋转。最后一个变换将原点移回`(x, y)`。整体效果是以`(x, y)`为中心点的旋转——参见图 12.49。由于绕原点以外的点进行旋转是一项常见操作，因此有一个快捷方法：

```java
g2.rotate(a, x, y);
```

## 图 12.49：组合变换

如果你熟悉矩阵理论，你可能知道所有的旋转、平移、缩放、剪切及其组合都可以表示为形式如下的变换矩阵：

![](img/240dbf1b84e081687f1.png)

这种变换被称为*仿射变换*（affine transformation）。在 Java2D API 中，`AffineTransform`类描述了这种变换。如果你知道特定变换矩阵的分量，可以直接这样构造它：

```java
AffineTransform t = new AffineTransform(a, b, c, d, e, f);
```

此外，工厂方法`getRotateInstance`、`getScaleInstance`、`getTranslateInstance`和`getSheInstance`构建了代表这些类型的矩阵。例如：

```java
t.setRotation(angle); // 设置 t 为旋转
```

你可以将图形上下文的坐标设置为`AffineTransform`对象。



```java
g2.setTransform(t); // 替换当前变换
```

然而，在实践中，你不应该调用`setTransform(t)`操作，因为它会替换图形上下文可能具有任何变换。例如，横屏模式打印的图形上下文已经包含 90 度的旋转变换。相反，请调用`transform`方法。

```java
g2.transform(t); // 与当前变换组合 t
```

如果你只想临时应用变换，先获取旧变换，将其与你的新变换组合，最后完成后恢复旧变换。

```java
AffineTransform oldTransform = g2.getTransform(); // 保存旧变换
g2.transform(t); // 应用临时变换
绘制 g2
g2.setTransform(oldTransform); // 恢复旧变换
```

## `java.awt.geom.AffineTransform` 1.2

- `AffineTransform(double a, double b, double c, double d, double e, double f)`
- `AffineTransform(float a, float b, float c, float d, float e, float f)`
- `AffineTransform(double[] m)`
- `AffineTransform(float[] m)`
- `static AffineTransform getRotateInstance(double a)`

  绕原点以角度 a（弧度）旋转。变换为：

  ```
  cos(a) - sin(a) 0
  sin(a) cos(a) 0
  0 0 1
  ```

  如果 a 在 0 到 π/2 之间，旋转将点 x 移向正 y 轴。

- `static AffineTransform getRotateInstance(double a, double x, double y)`

  绕点 (x,y) 以角度 a（弧度）旋转。

- `static AffineTransform getScaleInstance(double sx, double sy)`

  将 x 轴按 sx、y 轴按 sy 缩放的缩放变换。矩阵为：

  ```
  sx 0 0
  0 sy 0
  0 0 1
  ```

```java
static AffineTransform getShearInstance(double shx, double shy)
创建一个剪切变换，将 x 轴剪切 shy，将 y 轴剪切 shy。
变换矩阵为
  1 shx 0
  shy 1 0
  0 0 1
```

```java
static AffineTransform getTranslateInstance(double tx, double ty)
创建一个平移，将 x 轴移动 tx，将 y 轴移动 ty。
变换矩阵为
  1 tx
  0 1 ty
  0 0 1
```

```java
void setToRotation(double a)
void setToRotation(double a, double x, double y)
void setToScale(double sx, double sy)
void setToShear(double sx, double sy)
void setToTranslation(double tx, double ty)
将此仿射变换设置为给定参数的解释。参见 getXXInstance 方法以获取基本变换及其参数的解释。
```

## `java.awt.Graphics2D` 1.2

```java
void setTransform(AffineTransform t)
用 t 替换此图形上下文现有的坐标变换。
void transform(AffineTransform t)
将此图形上下文现有的坐标变换与 t 组合。
void rotate(double a)
void rotate(double a, double x, double y)
void scale(double sx, double sy)
void shear(double sx, double sy)
void translate(double tx, double ty)
将此图形上下文现有的坐标变换与给定参数的基本变换组合。参见 AffineTransform.getXXInstance 方法以获取基本变换及其参数的解释。
```

## 12.5.8 裁剪（Clipping）

通过在图形上下文设置裁剪形状，可以将所有绘制操作限制在该裁剪形状的内部。

- `g2.setClip(clipShape);` // 但请看下文
- `g2.draw(shape);` // 仅绘制落在裁剪形状内的部分

然而，在实践中，你并不希望设置`setClip`操作，因为它会替换图形上下文可能具有的任何裁剪形状。例如，你将在本章后面看到，用于打印的图形上下文带有一个裁剪矩形，确保你不会在页边距上绘图。相反，请调用`clip`方法。

```java
g2.clip(clipShape); // 更好
```

`clip`方法将现有的裁剪形状与你提供的新形状取交集。如果你只是想临时应用裁剪区域，应该先获取旧裁剪，添加你的新裁剪，最后在完成时恢复旧裁剪：

```java
Shape oldClip = g2.getClip(); // 保存旧裁剪
g2.clip(clipShape); // 应用临时裁剪
在 g2 上绘图
g2.setClip(oldClip); // 恢复旧裁剪
```

在图 12.50 中，我们展示了裁剪能力，画了一个非常戏剧线条图案，该图案被一个复杂形状裁剪——即一组字母的轮廓。

![](img/240dbf1b84e081687f1e252bd386c684_998_0.png)

图 12.50：使用字母形状裁剪线条图案

要获取字符轮廓，你需要一个字体渲染上下文（font render context）。使用`Graphics2D`类的`getFontRenderContext`方法。

```java
FontRenderContext context = g2.getFontRenderContext();
```

接下来，使用字符串、字体和字体渲染上下文，创建一个`TextLayout`对象：

```java
var layout = new TextLayout("Hello", font, context);
```

此文本布局对象描述了字符序列的布局，该布局是由特定的字体渲染上下文渲染的。布局依赖于字体渲染上下文——相同的字符在屏幕和打印机上会有所不同。

对于我们的应用程序更重要的是，`getOutline`方法返回一个`Shape`对象，它描述了文本布局中字符轮廓的形状。轮廓形状从原点 (0, 0) 开始，这可能不是你想要的。在这种情况下，为`getOutline`操作提供仿射变换（affine transform），以指定你想让轮廓出现的位置。

```java
AffineTransform transform = AffineTransform.getTranslateInstance(0, 100);
Shape outline = layout.getOutline(transform);
```

然后将轮廓添加到裁剪形状中。

```java
var clipShape = new GeneralPath();
clipShape.append(outline, false);
```

最后，设置裁剪形状并绘制一组线条。线条出现在字符边界内部。

```java
g2.setClip(clipShape);
var p = new Point2D.Double(0, 0);
for (int i = 0; i < NLINES; i++) {
  double x = .;
  double y = .;
  var q = new Point2D.Double(x, y);
  g2.draw(new Line2D.Double(p, q)); // 线条被裁剪了
}
```

## `java.awt.Graphics` 1.0

- `void setClip(Shape s)` 1.2

  将当前裁剪形状设置为形状 s。

- `Shape getClip()` 1.2

  返回当前的裁剪形状。

## `java.awt.Graphics2D` 1.2

- `void clip(Shape s)`

  将当前裁剪形状与形状 s 取交集。

- `FontRenderContext getFontRenderContext(Context)`

  返回一个构建`StatelessWidget`对象所需的字体上下文。

## `java.awt.font.TextLayout` 1.2

- `TextLayout(String s, Font f, FontRenderContext context)`

  根据字符串、字体和字体渲染上下文构建文本布局。

- `getAdvance()`

  返回布局的宽度。

- `getAscent()`

  返回到基线以上的距离。

- `getDescent()`

  返回到基线以下的距离。

- `getLeading()`

  返回连续行之间的距离。

## 12.5.9 透明度与合成（Transparency and Composition）

在标准的 RGB 模型中，透明度是由 Alpha 通道（alpha channel）描述的。然而，当你叠加图像时，像素可以是透明或半透明的。`Graphics2D` API 使用 Porter-Duff 规则处理这种情况。

| 规则 | 解释 |
| --- | --- |
| `SRC_OUT` | 源清除目标并覆盖空像素。 |
| `DST_IN` | 源的 alpha 通道修改目标。 |
| `DST_OUT` | 源的 alpha 补码修改目标。 |
| `SRC_ATOP` | 源与目标混合。 |
| `DST_ATOP` | alpha 修改目标。源覆盖空像素。 |
| `XOR` | 源的补码修改目标。源覆盖空像素。 |

# 图 12.53：Porter-Duff 组合规则

如你所见，大多数规则并没有非常用处。以极端情况为例，考虑`DST_IN`规则。它不考虑源（source）颜色，而是使用源的 alpha 值来影响目标。`SRC`可能是无用之物——它强制使用源颜色，从而关闭了对目标的混合。

使用`Graphics2D`类的`setComposite`方法来实现`Composite`接口的类对象。Java 2D API 提供了图 12.53 中所有的 Porter-Duff 规则。

`AlphaComposite`类的工厂方法`getInstance`会产生一个`AlphaComposite`对象。你提供规则以及用于源像素的 alpha 值。例如，考虑以下代码：

```java
int rule = AlphaComposite.SRC_OVER;
float alpha = 0.5f;
g2.setComposite(AlphaComposite.getInstance(rule, alpha));
g2.setPaint(Color.blue);
g2.fill(rectangle);
```

随后，矩形被涂成蓝色且 alpha 值为 0.5。由于组合规则是`SRC_OVER`，它将透明地叠加在现有图像上。

列表 12.17 中的程序允许你探索这些组合规则。从组合框框中选择一个规则，并使用滑动条设置`AlphaComposite`对象的 alpha 值。

此外，程序还显示了每个规则的文字描述。请注意，这些描述是从组合规则图中计算出来的。例如，第二行中的 "DS" 代表“与目标混合”。

该程序有一个重要的转折点。无法保证对应屏幕的图形上下文具有 alpha 通道。（事实上，它通常没有。）当像素被放置到没有 alpha 通道的区域上时，像素颜色将与 alpha 值相乘，并丢弃 alpha 值。若干 Porter-Duff 规则使用了目标的 alpha 值，这意味着目标 alpha 通道非常重要。出于此原因，我们使用带有 ARGB 颜色模型的缓冲图像来组合形状。在组合完成后，我们将生成的图像绘制到屏幕上。

```java
var image = new BufferedImage(getWidth(), getHeight(),
BufferedImage.TYPE_INT_ARGB);
Graphics2D gImage = image.createGraphics();
// 现在绘制到 gImage
g2.drawImage(image, 0, 0, 0);
```

列表 12.17 显示了框架类。列表 12.19 中的组件类为每个规则提供了简要解释——参见图 12.54。当你运行程序时，通过将 alpha 滑动条从左向右移动，以观察对组合形状的影响。特别需要注意的是，`DST_IN`规则和`DST_OUT`规则唯一区别在于当更改源 alpha 时，颜色变化的方向不同。

![](img/240dbf1b84e081687f1e252bd386c684_1003_0.png)

图 12.54：CompositeDemo 程序

# 列表 12.17 `v2ch2/composite/CompositeDemoFrame.java`

```java
package v2ch2.composite;

import java.desktop.*;
/**
 * 此框架包含一个用于选择组合规则的组合框、一个用于更改源
 * alpha 通道的滑动条，以及一个显示组合结果的组件。
 */
class CompositeDemoFrame extends JFrame {
    private static final int DEFAULT_WIDTH = 400;
    private static final int DEFAULT_HEIGHT = 400;

    private CompositeComponent canvas;
    private JComboBox<Rule> ruleCombo;
    private JSlider alphaSlider;
    private JTextField traceField;

    public CompositeDemoFrame() {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

        canvas = new CompositeComponent();
        add(canvas, BorderLayout.CENTER);

        ruleCombo = new JComboBox<>(new Rule[]{
            new Rule("CLEAR", "", "1", new Rule("SRC", "S", "DS"),
            new Rule("DST", "S", "D", new Rule("SRC OVER", "S", "D"),
            new Rule("DST OVER", "S", "D", new Rule("SRC IN", "S", "DS"),
            new Rule("SRC OUT", "S", "D", new Rule("DST IN", "S", "DS"),
            new Rule("DST OUT", "S", "D", new Rule("SRC ATOP", "S", "D"))
        });

        ruleCombo.addActionListener(e -> {
            var r = ruleCombo.getSelectedItem();
            canvas.setRule(r);
            traceField.setText(r.explanation());
        });

        alphaSlider = new JSlider(0, 100, 75);
        alphaSlider.addChangeListener(() -> canvas.setAlpha(alphaSlider.getValue()));

        var panel = new JPanel();
        panel.add(new JLabel("Alpha"));
        panel.add(alphaSlider);
        add(panel, BorderLayout.NORTH);

        traceField = new JTextField();
        add(traceField, BorderLayout.SOUTH);
    }
```

# 列表 12.18 `v2ch2/composite/CompositeComponent.java`



```java
package v2ch2.composite;

import java.awt.*;
import java.awt.image.*;
import javax.swing.*;

/**
 * 此组件绘制两个形状。
 */
class CompositeComponent extends JComponent {
    private Rule rule;
    private float alpha;
    private Shape shape1;
    private Shape shape2;

    public CompositeComponent() {
    }

    @Override
    protected void paintComponent(Graphics g) {
        Graphics2D g2 = (Graphics2D) g;
        super.paintComponent(g);
    }

    public void setRule(Rule r) {
        rule = r;
        repaint();
    }

    public void setAlpha(int a) {
        alpha = (float) a / 100.0;
        repaint();
    }
}
```

# 列表 12.19 `v2ch2/composite/Rule.java`

```java
package v2ch2.composite;

/**
 * 此类描述 Porter-Duff 规则。
 */
public class Rule {
    private String name;
    private String porterDuff1;
    private String porterDuff2;

    /**
     * 构造 Rule。
     * @param name 规则名称
     * @param p1 Porter-Duff 第一行
     * @param p2 Porter-Duff 第二行
     */
    public Rule(String name, String p1, String p2) {
        name = name;
        porterDuff1 = p1;
        porterDuff2 = p2;
    }

    /**
     * 获取此规则的解释。
     * @return 解释
     */
    public String getExplanation() {
        StringBuilder s = new StringBuilder("source ");
        if (porterDuff1.equals("S")) s.append("clears");
        if (porterDuff1.equals("DS")) s.append("overwrites");
        if (porterDuff2.equals("P")) s.append("alpha modifies");
        if (porterDuff2.equals("DO")) s.append("complement modifies");
        if (porterDuff2.equals("DD")) s.append("does not affect");
        s.append("destination");
        if (porterDuff2.equals("S")) s.append(" and overwrites empty pixels");
        return s.toString();
    }

    @Override
    public String toString() {
        return name;
    }

    /**
     * 获取此规则在 AlphaComposite 类中的值。
     * @return AlphaComposite 常量值，如果没有常量则返回 -1。
     */
    public int getAlpha() {
        try {
            return (Integer)AlphaComposite.class.getField(name).get(null);
        } catch (Exception e) {
            return -1;
        }
    }
}
```

## 12.6 栅格图像

Java2D API 允许创建由线条、曲线和区域组成的图形。它是一个“矢量” API，因为你指定的是形状的数学属性。然而，对于处理由像素组成的图像，你希望处理的是颜色数据的“栅格”。接下来的章节将向你展示如何在 Java 中处理栅格图像。

### 12.6.1 图像的读取器和写入器

`javax.imageio` 包包含了对常见文件格式读取和写入的内置支持，还提供了一个允许第三方为其他格式添加读取器和写入器的框架。它支持 GIF、JPEG、PNG、BMP（Windows 位图）和 WBMP（Windows 位图）文件格式。

该库的基础用法非常直观。要加载图像，请使用 `ImageIO` 类的静态 `read` 方法：

```java
File f = ...;
BufferedImage image = ImageIO.read(f);
```

`ImageIO` 类会根据文件类型选择合适的读取器。为了实现这一目的，它可能会检查文件扩展名以及文件开头的“魔数”。如果找不到合适的读取器，或者读取器无法解码文件内容，`read` 方法将返回 `null`。

将图像写入文件同样简单：

```java
File f = ...;
String format = ...;
ImageIO.write(image, format, f);
```

在这里，`format` 字符串是标识图像格式的字符串，例如 `"JPEG"` 或 `"PNG"`。`ImageIO` 类会选择一个合适的写入器并保存文件。

### 12.6.2 获取图像文件类型的读取器和写入器

对于超出 `ImageIO` 类静态 `read` 和 `write` 方法的高级图像读写操作，你首先需要获取合适的 `ImageReader` 和 `ImageWriter` 对象。`ImageIO` 类列出了匹配以下任一条件的读取器和写入器：

- 图像格式（例如 `"JPEG"`）
- 文件后缀名（例如 `"jpg"`）
- MIME 类型（例如 `"image/jpeg"`）

> 注意：MIME 是多用途互联网邮件扩展标准。MIME 标准定义了常见的数据格式，如 `image/jpeg` 和 `application/pdf`。

例如，你可以通过以下方式获取读取 JPEG 文件的读取器：

```java
ImageReader reader = null;
Iterator<ImageReader> iter = ImageIO.getImageReadersByFormat("JPEG");
if (iter.hasNext()) reader = iter.next();
```

`getImageReadersBySuffix` 和 `getImageReadersByMIMEType` 方法列出了匹配文件扩展名或 MIME 读取器。

`ImageIO` 类可能会定位到多个可以读取特定图像的读取器。在这种情况下，你需要选择其中一个，但并不清楚如何决定哪一个是最好的。要获取有关读取器的更多信息，可以获取其服务提供接口（SPI）：

```java
ImageReaderSpi spi = reader.getOriginatingProvider();
```

然后，你可以获取厂商名称和版本号：

```java
String vendor = spi.getVendor();
String version = spi.getVersion();
```

也许这些信息可以帮助你在多个选项中做出决定——或者你也可以直接向程序用户展示读取器列表并让他们自行选择。目前，我们假设第一个枚举的读取器就足够了。

在示例程序 Listing 12.20 中，我们想要找到所有读取器的后缀名，以便在过滤器中使用。请使用静态方法 `ImageIO.getWriterFileSuffixes` 来此目的：

```java
String[] extensions = ImageIO.getWriterFileSuffixes();
chooser.setFilter(new FileNameExtensionFilter("Image files", extensions));
```

对于保存文件，我们需要付出更多努力。我们希望向用户展示一个支持的图像类型菜单。遗憾的是，`ImageIO` 类的 `getFormatNames` 方法返回了一个带有冗余名称的奇怪列表，例如：

```text
jpg, BMP, bmp, JPG, jpeg, wbmp, png, JPEG, PNG, WBMP, gif, GIF, tif,
```

这不是人们想要在菜单中展示的内容。什么是一个“首选”格式名称列表呢？Listing 12.20 中的辅助方法 `getFormatNames` 查找与每个格式关联的写入器，并询问它的格式名称是什么，希望它能列出最流行的那个。事实上，对于 JPEG 写入器，这确实有效——它在其他选项之前列出了 `"JPEG"`。相反，PNG 则在 `"PNG"` 之前列出了小写的 `"png"`。因此，为了一致性，该辅助方法强制将小写名称转换为大写。

## 12.6.3 读取和写入包含多个图像的文件

某些文件——特别是动画 GIF 文件——包含多个图像。`ImageIO` 类的 `read` 方法读取单个图像。要读取多个图像，可以将输入源（例如输入流或文件）转换为 `InputStream`。

```java
InputStream in = ...;
InputStream imageIn = ImageIO.createInputStream(in);
```

然后，将图像输入流挂到读取器上：

```java
reader.setInput(imageIn, true);
```

第二个参数表示输入处于“仅允许向前移动”模式。否则，将使用随机访问，这通过在读取时对流进行缓冲或使用随机文件访问来实现。某些操作需要随机访问。例如，要查找 GIF 文件中的图像数量，你需要读取整个文件。如果你接着想获取图像，则必须再次读取输入。

这种考虑仅在你从流中读取、输入包含多个图像，且图像格式在文件头中没有包含你请求的信息（如图像计数）时才变得重要。如果你从文件读取，只需使用：

```java
File f = ...;
ImageInputStream imageIn = ImageIO.createImageStream(f);
reader.setInput(imageIn);
```

一旦你有了读取器，就可以通过调用来读取输入中的图像：

```java
BufferedImage image = reader.read(index);
```

其中 `index` 是图像索引，从 0 开始。

如果输入处于“仅允许向前移动”模式，`getNumImages` 方法将返回 `-1`。或者，你可以调用该参数表示允许搜索。在这种情况下，你无法确定图像数量。

```java
int n = reader.getNumImages(true);
```

如果输入是“仅允许向前移动”模式，读取器无法确定图像数量。

某些文件包含图像的缩略图——用于预览的较小版本。你可以通过调用获取图像的缩略图数量：

```java
int count = reader.getThumbnails(index);
```

然后获取特定索引的缩略图：

```java
BufferedImage thumbnail = reader.getThumbnail(index);
```

有时你想在实际获取图像之前获取图像尺寸——如果图像很大或来自网络连接。使用调用：

```java
int width = reader.getWidth(index);
int height = reader.getHeight(index);
```

要写入包含多个图像的文件，你首先需要一个 `ImageWriter`。`ImageIO` 类可以列出能够写入特定图像格式的写入器：

```java
String format = ...;
ImageWriter writer = null;
Iterator<ImageWriter> iter = ImageIO.getImageWritersByFormat(format);
if (iter.hasNext()) writer = iter.next();
```

接下来，将输出流或文件转换为 `ImageOutputStream` 并将其挂到写入器上。例如：

```java
File f = ...;
ImageOutputStream imageOutput = ImageIO.createImageOutputStream(f);
writer.setOutput(imageOutput);
```

你必须将每个图像封装成 `IIOImage`。你可以可选地提供缩略图列表和图像元数据（如压缩算法和颜色信息）。在本示例中，对这两者都使用了 `null`；更多信息请参见 API 文档。

```java
var iioImage = new IIOImage(images[i], null, null);
```

要写入第一个图像，使用 `write` 方法：

```java
writer.write(new IIOImage(images[0], null, null));
```

对于后续图像，使用：

```java
if (writer.canInsertImage(i))
    writer.writeInsert(i, iioImage, null);
```

第三个参数可以包含 `ImageWriteParam` 以设置图像写入细节，如分块和压缩；使用 `null` 默认值。

并不是所有格式都能处理多个图像。在这种情况下，如果 `i > 0`，`canInsertImage` 方法将返回 `false`，且只保存单个图像。

Listing 12.20 中的程序允许你加载和保存 Java 库提供读取器和写入器的格式。该程序显示多个图像（见图 12.55），但并不显示缩略图。

![](img/240dbf1b84e081687f1e252bd386c684_1011_0.png)

# Listing 12.20 `v2ch12/imageIO/ImageIOFrame.java`



```java
package v2ch12.imageIO;

import module java.base;
import module java.desktop;
import java.util.List;

/*
 * 此框架显示已加载的图像。菜单包含加载和保存文件的项。
 */
public class ImageIOFrame extends JFrame {
    private static final int DEFAULT_WIDTH = 400;
    private static final int DEFAULT_HEIGHT = 400;

    private static Set<String> writerFormats = getWriterFormats();
    private BufferedImage[] images;

    public ImageIOFrame() {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);
        var fileMenu = new JMenuItem("文件");
        var open = new JMenuItem("打开");
        open.addActionListener(() -> openFile());
        fileMenu.add(open);

        var save = new JMenuItem("保存");
        fileMenu.add(save);

        Iterator<String> iter = writerFormats.iterator();
        while (iter.hasNext()) {
            final String formatName = iter.next();
            var formatItem = new JMenuItem(formatName);
            save.add(formatItem);
            formatItem.addActionListener(() -> saveFile(formatName));
        }

        var exitItem = new JMenuItem("退出");
        exitItem.addActionListener(() -> System.exit(0));
        fileMenu.add(exitItem);

        var menuBar = new JMenuBar();
        menubar.add(fileMenu);
        setJMenuBar(menubar);
    }

    /**
     * 打开文件并加载图像。
     */
    public void openFile() {
        var chooser = new JFileChooser();
        chooser.setCurrentDirectory(directory);
        String[] extensions = ImageIO.getInputReaderNames(null);
        chooser.setFileFilter(new FileNameExtensionFilter("image", extensions));
        int r = chooser.showDialog(this);

        if (r == JFileChooser.APPROVE_OPTION) {
            File f = chooser.getSelectedFile();
            Box box = new Box(VerticalBox());

            try {
                String name = f.getName();
                String suffix = name.substring(name.lastIndexOf(".") + 1);
                Iterator<ImageReader> iter = ImageIO.getImageReadersBySuffix(suffix);
                ImageReader reader = iter.next();
                InputStream image = ImageIO.createInputStream(f);
                int count = reader.getNumNumbers(true);
                BufferedImage[] images = new BufferedImage[count];

                for (int i = 0; i < count; i++) {
                    images[i] = reader.read(i);
                    box.add(new JLabel(images[i]));
                }
            } catch (Exception e) {
                JOptionPane.showMessageDialog(this, e);
            }

            setContentPane(new JScrollPane(box));
            validate();
        }
    }

    /**
     * 将当前图像保存到文件中。
     *
     * @param formatName 文件格式
     */
    public void saveFile(String formatName) {
        if (image == null) {
            return;
        }

        Iterator<ImageWriter> iter = ImageIO.getImageritersByFormat(formatName);
        ImageWriter writer = iter.next();
        var chooser = new JFileChooser();
        chooser.setCurrentDirectory(directory);
        String[] extensions = writer.getFileNameExtensionSuffixes();
        chooser.setFileFilter(new FileNameExtensionFilter("image", extensions));
        int r = chooser.showDialog(this);

        if (r == JFileChooser.APPROVE_OPTION) {
            File f = chooser.getSelectedFile();

            try {
                OutputStream imageOutput = ImageIO.createImageOutputStream(f);
                writer.write(new ImageIcon(images[0]), null, null);

                for (int i = 1; i < images.length; i++) {
                    var iioImage = new IIImage(images[i], null, null);
                    if (writer.canWriteImage(i)) {
                        writer.writeInsert(i, iioImage, null);
                    }
                }
            } catch (Exception e) {
                JOptionPane.showMessageDialog(this, e);
            }
        }
    }

    /**
     * 获取所有写入器的“首选”格式名称集合。首选
     * 格式是写入器指定的第一个格式名称。
     *
     * @return 格式名称集合
     */
    public Set<String> getWriterFormats() {
        var writerFormats = new TreeSet<String>();
        var formatNames = List.of(ImageIO.getFormatNames());

        while (formatNames.size() > 0) {
            String formatName = formatNames.iterator().next();
            Iterator<ImageWriter> iter = ImageIO.getImageWritersByFormatName(formatName);
            ImageWriter writer = iter.next();
            String[] names = writer.getOriginatingProvider().getFormatNames();
            String format = names[0];

            if (format.equals(format.toLowerCase())) {
                format = format.toUpperCase();
            }

            writerFormats.add(format);
            formatNames.remove(List.of(names));
        }

        return writerFormats;
    }
}
```

你所操作的大多数图像直接是从图像文件中读取的——它们要么是由数字相机或扫描仪等设备产生的，要么是由绘图程序构建的。在本节中，我们将向你展示一种构建图像的不同技巧：逐像素地构建图像。

要创建一个图像，请按照通常的方法构造一个`BufferedImage`对象。

```java
image = new BufferedImage(width, height, BufferedImage.TYPE_INT_ARGB);
```

现在，调用`getRaster`方法获取一个`WritableRaster`类型的对象。你将使用该对象来修改图像的像素。

```java
WritableRaster raster = image.getRaster();
```

`setPixel`方法用于设置单个像素。这里的复杂之处在于，你不能简单地将像素设置为一个`Color`值。你必须了解缓冲图像是如何指定颜色的。如果你的图像类型为`TYPE_INT_ARGB`，则每个像素由四个值描述——红、绿、蓝和 alpha（透明度），每个值都在 0 到 255 之间。你必须以整数数组的形式提供它们：

```java
int[] black = { 0, 0, 0, 255 };
raster.setPixel(i, j, black);
```

在 Java 2D API 中，这些值是像素的采样值。

> 注意：还存在参数类型为`float[]`和`double[]`的`setPixel`方法。然而，你需要放入这些数组的值并不是 0 到 1.0 之间的归一化颜色。

```java
float[] red = { 1.0F, 0.0F, 0.0F, 1.0F };
raster.setPixel(i, j, red); // 错误
```

无论数组类型是什么，你都必须提供 0 到 255 之间的值。

你可以使用`setPixel`方法一次提供一组像素。指定要设置的矩形起始像素位置以及其宽度和高度。然后提供一个包含所有像素采样值的数组。例如，如果你的缓冲图像类型为`TYPE_INT_ARGB`，则提供第一个像素的红、绿、蓝、alpha 值，依此类推。

```java
var pixels = new int[4 * width];
pixels[0] = ...; // 第一个像素的红色值
pixels[1] = ...; // 第一个像素的绿色值
pixels[2] = ...; // 第一个像素的蓝色值
pixels[3] = ...; // 第一个像素的 alpha 值
...
```

```java
raster.setPixels(x, y, width, height, pixels);
```

相反，要读取像素，请使用`getPixel`方法。提供一个四个整数的数组来存储采样值。

```java
var sample = new int[4];
raster.getPixel(x, y, sample[0], sample[1], sample[2]);
var color = new Color(sample[0],
```

你可以使用`getPixels`方法读取多个像素。

```java
raster.getPixels(x, y, width, height, samples);
```

如果你使用了`TYPE_INT_ARGB`以外的任何图像类型，你仍然可以使用`getPixel/setPixel`方法。但是，你必须知道特定图像类型中采样值的编码方式。

如果你需要操作具有任意、未知图像类型的图像，那么你必须付出更多努力。每种图像类型都是一种颜色模型，可以在采样值和 RGB 颜色模型之间进行转换。

> 注意：RGB 颜色模型并不像你想象的那样标准。颜色值的精确外观取决于成像设备的特性。数字相机、扫描仪、监视器和 LCD 显示器都有各自的独特性。因此，相同的 RGB 值在不同设备上看起来可能完全不同。国际色彩联盟（https://www.color.org）建议所有数据都通过 ICC 配置文件进行处理，该配置指定了颜色如何映射到标准形式（例如 1931 CIE XYZ 规范）。该规范由国际照明委员会（CIE，https://www.cie.co.at）设计，CIE 是负责在所有照明和色彩事务方面提供技术指导的国际组织。该规范是一种标准方法，用于将人眼可感知的任何颜色以 X、Y、Z 三元坐标的形式表示。（有关 1931 CIE XYZ 规范的更多信息，请参阅例如 John F. Hughes 等人编写的《Computer Graphics: Principles and Practice, Third Edition》第 28 章）。

ICC 配置文件是复杂的，但一个更简单的建议标准——[sRGB](https://www.w3.org/Graphics/Color/sRGB.html），规定了 RGB 值与 1931 CIE XYZ 值之间精确的映射，该映射旨在与典型的色彩显示器良好地配合工作。Java 2D API 在在 RGB 和其他颜色之间转换时使用了这种映射。

`getColorModel`方法返回颜色模型：

```java
ColorModel model = image.getColorModel();
```

要找到像素的颜色，请使用`Raster`类的`getDataElements`方法。它返回一个包含特定颜色模型颜色值描述的`Object`。

```java
Object data = raster.getDataElements(x, y, null);
```

> 注意：`getDataElements`方法返回的对象实际上是一个采样值数组。你不需要知道如何处理该对象，但它解释了为什么该方法被称为`getDataElements`。

颜色模型可以将该对象转换为标准的 ARGB 值。`getRGB`方法返回一个`int`值，其中包含每八位一组 alpha、红、绿、蓝值。你可以用该整数构造一个`Color`值。

常见的图像类型有`TYPE_INT_RGB`、`TYPE_INT_ARGB`、`TYPE_BYTE_GRAY`和`TYPE_BYTE_INDEXED`。

- `ColorModel getColor()`

  返回此缓冲图像的颜色模型。

- `WritableRaster getRaster()`

  获取用于访问和修改此缓冲图像像素的栅格。

## `java.awt.image.Raster` 1.2

- `getDataElements(int x, int y, Object data)`

  返回栅格点的样本数据，该数据位于数组的元素类型和长度取决于颜色模型。如果`data`不为`null`，则假设它是适用于处理样本数据的数组并对其进行填充。如果`data`为`null`，则分配一个新数组。其元素类型和长度取决于颜色模型。

- `getPixel(int x, int y, int[] sampleValues)`

- `getPixel(int x, int y, float, float[] sampleValues)`

- `double getPixel(int x, int y, double[] sampleValues)`

- `int[] getPixels(int x, int y, int width, int height, int[] sampleValues)`

- `float[] getPixels(int x, int y, int width, int height, float[] sampleValues)`

- `double[] getPixels(int x, int y, int width, int height, double[] sampleValues)`



返回栅格点或栅格点矩形的样本值，其数组长度取决于颜色模型。如果 `sampleValues` 不为 `null`，则假设它足够长以容纳样本值并对其进行填充。如果 `sampleValues` 为 `null`，则分配一个新数组。这些方法只有在你知道颜色模型样本值的含义时才有用。

## `java.awt.image.WritableRaster` 1.2

- `setDataElements(int x, int y, Object data)`

  设置栅格点的样本数据。`data` 是一个填充了像素样本数据的数组。其元素类型和长度取决于颜色模型。

- `setPixel(int x, int y, int[] sampleValues)`
- `setPixel(int x, int y, float[] sampleValues)`
- `setPixel(int x, int y, double[] sampleValues)`
- `setPixels(int x, int y, int width, int height, int[] sampleValues)`
- `setPixels(int x, int y, int width, int height, float[] sampleValues)`
- `setPixels(int x, int y, int width, int height, double[] sampleValues)`

  设置栅格点或栅格点矩形的样本值。这些方法只有在你知道颜色模型样本值的编码时才有用。

### `java.awt.image.ColorModel` 1.2

- `int getRGB(Object data)`

  返回与传入 `data` 数组的样本数据对应的 ARGB 值。

  其类型取决于颜色模型。

- `Object getDataElements(int arg, Object data)`

  返回颜色值的样本数据。如果 `data` 不为 `null`，则假设它是适用于存储样本数据的数组并对其进行填充。如果 `data` 为 `null`，则分配一个新数组。`Data` 是一个填充了像素样本数据的数组。其类型取决于颜色模型。

### `java.awt.Color` 1.0

- `Color(int arg, boolean hasAlpha)` 1.2

  如果 `hasAlpha` 为 `true`，则根据指定的 ARGB 值创建颜色；如果 `hasAlpha` 为 `false`，则根据指定的 RGB 值创建。

- `int getRGB()`

  返回对应此颜色的 ARGB 值。

#### 12.6.5 图像过滤

在前面的节中，你看到了如何从零开始构建图像。然而，通常你出于其他原因访问图像数据：你已经有一张图像，并想以某种方式改进它。

当然，你可以使用前面节中看到的 `getPixel`/`getDataElements` 方法来读取图像数据、对其进行处理并写回。幸运的是，Java 2D API 已经提供了许多过滤器，可以为你执行常见的图像处理操作。

所有的图像操作都实现了 `BufferedImage` 接口。在构造操作后，只需调用过滤器方法将一个图像转换为另一个。

```java
BufferedImage op = . . ;
BufferedImage filteredImage = new BufferedImage(image.getWidth(), image.getHeight(), image.getType(), filteredImage);
op.filter(image, filteredImage);
```

某些操作可以原地转换图像（`op.filter(image, image)`），但大多数操作不能。

有五个类实现了 `BufferedImage` 接口：

- `AffineTransformOp`
- `RescaleOp`
- `LookupOp`
- `ColorConvertOp`
- `ConvolveOp`

`AffineTransformOp` 对像素执行仿射变换。例如，这里是绕中心旋转图像的方法：

```java
AffineTransform transform = AffineTransform.getRotateInstance(Math.toRadians(angle), image.getWidth() / 2, image.getHeight() / 2);
var op = new AffineTransformOp(transform, interpolation);
op.filter(image, renderedImage);
```

`AffineTransform` 构造函数需要一个仿射变换和一个插值策略。如果源像素在目标像素之间进行变换，则必须确定目标像素。例如，如果旋转源像素，它们通常不会恰好落在目标像素上。有三种插值策略：`AffineTransformOp.TYPE_BICUBIC`、`AffineTransformOp.TYPE_NEAREST`。

`RescaleOp` 对图像执行缩放操作。每个像素值被乘以缩放因子并加上一个偏移量。这对于亮化或暗图像非常有用。

```java
float a = 1.1f;
float b = 10.0f;
var op = new RescaleOp(a, b, null);
op.filter(image, filteredImage);
```

`LookupOp` 使用表将像素值映射到新值。它可以用于颜色反转或灰度化等效果。

```java
short[] table = new short[256];
for (int i = 0; i < 256; i++) table[i] = (short) (255 - i);
LookupTable table = new LookupTable(0, table);
var op = new LookupOp(table, null);
op.filter(image, filteredImage);
```

`ConvolveOp` 使用卷积核执行卷积操作。这用于模糊、锐化和边缘检测等效果。

```java
float[][] data = {
    {0, -1, 0},
    {-1, 4, -1},
    {0, -1, 0}
};
Kernel kernel = new ConvolveKernel(3, 3, data);
ConvolveOp op = new ConvolveOp(kernel, null);
op.filter(image, filteredImage);
```

要构造卷积操作，首先为卷积核设置值数组并构造一个 `Kernel` 对象。然后，从卷积核构造一个 `ConvolveOp` 对象并使用它进行过滤。

```java
float[] elements = {
  0.0f, -1.0f, 0.0f,
  -1.0f, 4.0f, -1.0f,
  0.0f, -1.0f, 0.0f
};
var kernel = new Kernel(3, 3, elements);
var op = new ConvolveOp(kernel);
op.filter(image, filteredImage);
```

列表 12.22 中的程序允许你加载 GIF 或 JPEG 图像，并执行我们讨论过的图像处理。得益于 Java 2D API 提供的操作能力，该程序非常简单。

# 列表 12.22 `v2ch2/imageProcessing/ImageProcessingFrame.java`

```java
package v2ch2.imageProcessing;
import java.awt;
import java.awt.desktop;
/*
 * 此帧包含一个加载图像的方法用于指定各种变换，
 * 以及一个显示结果图像的组件。
 */
public class ImageProcessingFrame extends JFrame {
  private static final int DEFAULT_WIDTH = 400;
  private static final int DEFAULT_HEIGHT = 400;

  private BufferedImage image;
  public ImageProcessingFrame() {
    setTitle("ImageProcessingTest");
    setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

  add(new JComponent() {
    public void paintComponent(Graphics g) {
      if (image != null) g.drawImage(image, 0, 0);
    }
  });

  var fileMenu = new JMenu("File");
  var openItem = new JMenuItem("Open");
  openItem.addActionListener(_ -> openFile());
  fileMenu.add(openItem);
  var exitItem = new JMenuItem("Exit");
  exitItem.addActionListener(_ -> System.exit(0));
  fileMenu.add(exitItem);

  var editMenu = new JMenu("Edit");
  var blurItem = new JMenuItem("Blur");
  blurItem.addActionListener(_ -> {
    float weight = 1.0f / 9.0f;
    float[] elements = new float[9];
    for (int i = 0; i < 9; i++)
      elements[i] = weight;
    convolve(elements);
  });
  editMenu.add(blurItem);

  var sharpenItem = new JMenuItem("Sharpen");

  sharpenItem.addActionListener(e -> {
    float[] elements = {0.0f, -1.0f, 0.0f, -1.0f, 5.0f, -1.0f, 0.0f, -1.0f, 0.0f};
    convolve(elements);
  });

  var brightenItem = new JMenuItem("Brighten");
  brightenItem.addActionListener(e -> {
    float a = 1.0f;
    float b = 20.0f;
    var op = new RescaleOp(a, b, null);
    filter(op);
  });

  editMenu.add(brightenItem);
  var edgeDetectItem = new JMenuItem("Edge detect");
  edgeDetectItem.addActionListener(e -> {
    float[] elements = {0.0f, -1.0f, 0.0f, -1.0f, 4.0f, -1.0f, 0.0f, 0.0f};
    convolve(elements);
  });

  editMenu.add(edgeDetectItem);
  var negativeItem = new JMenuItem("Negative");
  negativeItem.addActionListener(e -> {
    short[] negative = new short[256];
    for (int i = 0; i < 256; i++) negative[i] = (short) (255 - i);
    var table = new ShortLookupTable(0, negative);
    var op = new LookupTable(table, null);
    filter(op);
  });

  editMenu.add(negativeItem);
  var rotateItem = new JMenuItem("Rotate");
  rotateItem.addActionListener(e -> {
    if (image == null) return;
    var transform = new AffineTransform.rotate(Math.toRadians(5));
    var image = new BufferedImage(image.getWidth(), image.getHeight(), BufferedImage.TYPE_BICUBIC);
    var op = new AffineTransformOp(transform, transform.TYPE_BICUBIC);
    filter(op);
  });

  editMenu.add(rotateItem);
  var menuBar = new JMenuBar();
  menubar.add(fileMenu);
  menubar.add(editMenu);
  setJMenuBar(menubar);

  /*
   * 打开文件并加载图像。
   */
  var chooser = new JFileChooser("Images");
  chooser.setCurrentDirectory(new File(System.getProperty("user.home")));
  String[] extensions = Image.readFileExtensions("Image files");
  chooser.setFilter(new FileNameExtensionFilter("Image files", *extensions));
  int r = chooser.showOpenDialog(this, JFileChooser.APPROVE_OPTION);
  if (r == JFileChooser.APPROVE_OPTION) {
    try {
      Image image = Image.read(chooser.getSelectedFile());
      Image image = new BufferedImage(image.getWidth(), image.getHeight(), BufferedImage.TYPE_BICUBIC);
      var op = new AffineTransformOp(transform, transform.TYPE_BICUBIC);
      filter(op);
    }
  }
```

## 图 12.60：跨平台打印对话框

考虑实现 `PrintRequestAttributeSet` 接口的类对象的打印设置，例如 `HashPrintRequestAttributeSet` 类。

```java
var attributes = new HashPrintRequestAttributeSet();
```

添加属性设置并将属性对象传递给对话框方法。

如果用户点击确定，`printDialog` 方法返回 `true`；如果用户取消了对话框，则返回 `false`。如果用户接受，调用 `PrinterJob` 类的 `print` 方法来开始打印过程。`print` 方法可能会抛出 `PrinterException`。以下是打印代码的概述：

```java
if (job.printDialog(attributes)) {
  try {
    job.print(attributes);
  }
  catch (PrinterException e) {
  }
}
```



> 注意：在 JDK 1.4 之前，打印系统使用宿主平台的原生打印和页面设置对话框。要显示原生打印对话框，请调用无参数的`printDialog`方法。（没有办法在属性集中收集用户设置。）

在打印期间，`PrinterJob`类的`print`方法会反复调用与作业相关的`Printable`对象的`print`方法。

由于作业不知道你想打印多少页，它只是一直调用`print`方法。只要`print`方法返回`Printable.PAGE_EXISTS`值，作业就会继续生成页面。当`print`方法返回`Printable.NO_SUCH_PAGE`时，作业停止。

> 注意：打印作业传递给`print`方法的页码从页 0 开始。

因此，在打印完成之前，打印作业没有准确的页数。由于这个原因，打印对话框无法显示正确的页范围——而是显示“Pages 1 to ..”。在下一节中你将看到如何通过向打印作业提供`Book`对象来避免这个问题。

在打印过程中，打印作业反复调用`PrinterObject`的`print`方法。作业允许对同一页进行多次调用。因此，你不应该在`print`方法内部计算页数，而应该始终保持在当前页码。打印作业可能对同一页反复调用`print`方法有一个充分的原因。某些打印机（特别是针式和喷墨打印机）使用带式打印（banding）。它们一次打印一个带，推进纸张，然后打印下一个带。即使对于一次打印整页的激光打印机，打印作业可能使用带式打印——这为打印作业提供了一种管理池文件的方法。

如果作业需要`Printable`对象进行分带，它会将图形上下文的裁剪区域设置为请求的带并调用`print`方法。它的绘制操作将根据带矩形进行裁剪，只有在带中显示的绘制元素会被渲染。你的`print`方法不需要感知这一点，但有一个例外：它不应该干扰裁剪区域。

> 注意：你的`print`方法获取的`Graphics`对象也根据页边距进行了裁剪。如果你替换了裁剪区域，你可以在页边距之外绘制。特别是在打印机图形环境中，必须尊重裁剪区域。调用`clip`而不是`setClip`来进一步限制裁剪区域。如果你必须移除裁剪区域，请确保在`print`方法的开始调用`getClip`并恢复该裁剪区域。

`print`方法的`PageFormat`包含有关打印页面的信息。`getWidth`和`getHeight`方法返回以点（points）为单位的尺寸。

（1点等于1/72英寸；1英寸等于25.4毫米。）例如，A4纸约为595 × 842点，US Letter纸为612 × 792点。

点是美国打印行业中常用的测量单位。令世界其他地方感到遗憾的是，打印包使用了点单位。这样做有两个目的：页面大小和页边距是以点为单位的，且点是所有打印图形上下文的默认单位。你可以在本节末尾的示例程序中验证这一点。该程序打印了两行文本，它们间隔72个单位。示例程序测量了基线之间的距离；它们恰好相1英寸或25.4毫米。

`PageFormat`类的`Width`和`getHeight`方法提供完整的页面尺寸。用户通常会选择边距，即使他们不选择，打印机也需要某种方式处理打印的纸张，因此在边缘有一个小的不可打印区域。

`getImageableWidth`和`getImageableHeight`方法告诉你实际上可以填充的区域尺寸。然而，边距可能不是对称的，因此你必须知道可打印区域的左上角（见图 12.61），你通过`getImageableX`和`getImageableY`方法获取它。

## 图 12.61：页面格式测量

> 提示：你在`print`方法中收到的图形上下文经过裁剪以排除边距，但坐标系的原点仍然是页面的左上角。将坐标系转换到可打印区域的左上角是有意义的。只需在`print`方法开始时：

```java
g.translate(pageFormat.getImageableX(), pageFormat.getImageableY());
```

如果你想在不设置其他打印属性的情况下选择页边距设置或在纵向和横向之间切换，请调用`Printer`类的`pageDialog`方法：

```java
PageFormat format = job.pageDialog(attributes);
```

> 注意：要显示页面设置对话框，请向`pageDialog`方法传递默认的`PageFormat`对象。该方法会克隆它，根据对话框中的用户选择对其修改，并返回克隆的对象。

# Listing 12.v2ch12.print/PrintComponent.java

```java
package v2ch12.print;

import java.awt.*;

/**
 * This component generates a 2D graphics image for screen display and printing.
 */

public class PrintComponent extends JComponent implements Printable {

    private static final Dimension PREFERRED_SIZE = new Dimension(300, 300);

    public void paintComponent(Graphics g) {

        var g2 = (Graphics2D) g;

        drawPage(g2);

    }

    public int print(Graphics g, PageFormat pf, int page) throws PrinterException {

        if (page >= 1) return NO_SUCH_PAGE;

        var g2 = (Graphics2D) g;

        g2.translate(pf.getImageWidth(), pf.getImageHeight());

        g2.draw(new Rectangle2D(0, 0, pf.getImageWidth(), pf.getImageHeight()));

        drawPage(g2);

        return PAGE_EXISTS;

    }

}

/**
 * This method draws the page on both the screen and the printer graphics context.
 */

public void drawPage(Graphics2D g2) {

    FontRenderer context = g2.getFontRenderer();

    var f = new Font("Ser", Font.PLAIN, 72);

    var clipShape = new GeneralPath();

    var layout = new TextLayout("Hello", f, context);

    AffineTransform transform = AffineTransform.translateInstance(0, 72);

    var outline = layout.getOutline(transform);

    clipShape.add(outline, false);

    g2.clip(clipShape);

    g2.draw(clipShape);

    final int LINES = 50;

    for (int i = 0; i < LINES; i++) {

        double x = i * 2 * getWidth();

        double y = getHeight() * (LINES - 1) / LINES;

        var q = new Point2D.Double(x, y);

        g2.draw(new Line2D.Double(p, q));

    }

}

public Dimension getPreferredSize() {

    return PREFERRED_SIZE;

}
```

# `java.awt.print.Printable` 1.2

- `int print(Graphics g, PageFormat format, int pageNumber)`  
  渲染一个页面并返回`PAGE_EXISTS`，或者返回`NO_SUCH_PAGE`。

# `java.awt.print.PrinterJob` 1.2

- `static PrinterJob getPrinterJob()`  
  返回一个打印作业对象。
- `PageFormat defaultPage()`  
  返回此打印机默认的页页格式。
- `boolean printDialog(printDialog attributes)`
- `boolean printDialog()`  
  打开一个对话框，允许选择页面并更改打印设置。第一个方法显示一个跨平台对话框，第二个方法显示原生对话框。第一个方法修改属性以反映用户设置。如果用户接受对话框，这两种方法都返回`true`。
- `PageFormat pageDialog(printDialog attributes)`
- `PageFormat pageDialog(PageFormat defaults)`  
  显示一个页面设置对话框。第一个方法显示一个跨平台对话框，第二个方法显示原生对话框。两种方法都返回带有用户在对话框中请求的格式的`PageFormat`对象。第一个方法修改属性以反映用户设置。第二个方法不修改默认对象。
- `void setPrintable(Printable p)`
- `void setPrintable(Printable p, PageFormat format)`  
  设置此打印作业的`Printable`和可选的页格式。
- `void print()`
- `void print(printDialog attributes)`  
  通过重复调用其`print`方法并将渲染后的页面发送到打印机来打印当前的`Printable`，直到没有更多可用页面。

# `java.awt.print.PageFormat` 1.2

- `double getWidth()`
- `double getHeight()`  
  返回页面的宽度和高度。
- `double getImageableWidth()`
- `double getImageableHeight()`  
  返回页面可用区域的宽度和高度。
- `double getImageableX()`
- `double getImageableY()`  
  返回可用区域左角的角的。
- `int getOrientation()`  
  返回`PORTRAIT`、`LANDSCAPE`或`REVERSE_LANDSCAPE`之一。页面方向对程序员来说是透明的，因为页格式和图形上下文设置会自动反映页面方向。

## 12.7.2. 多页打印

在实践中，你通常不会向打印作业传递一个原始的`Printable`对象。相反，你应该获取一个实现了`Pageable`接口的类的对象。Java平台提供了这样一个类，称为`Book`。一本书由多个部分组成，每个部分都是一个`Printable`对象。要制作一本书，添加`Printable`对象及其页数。

```java
var book = new Book();

Printable coverPage = ...;

Printable bodyPages = ...;

book.append(coverPage, pageFormat); // 添加 1 页

book.append(bodyPages, pageFormat, pageCount);
```

然后，使用`setPageable`方法将`Book`传递给打印作业。

```java
printJob.setPageable(book);
```

现在，打印作业确切知道要打印多少页，因此打印对话框会显示准确的页范围，用户可以选择一个或多个范围。

> 注意：当打印作业调用每个部分的方法时，它传递的是书籍的当前页码，而不是每个部分的页码，因为当前页码就是当前的页码。这对程序员来说是一个挑战，因为他们必须处理页数。页面的布局取决于内容。使用`Pageable`接口来处理多页。

## 图 12.63：打印页面

此示例展示了变换的力量。使用`Pageable`接口来处理多页。

## 图 12.64：打印页面

此示例展示了变换的力量。使用`Pageable`接口来处理多页。

# 12.25 vch12/book/BookDemoFrame.java

```java
package vch12.book;

import java.desktop.*;

/**
 * 此框架包含一个用于 banner 文本的字段以及用于打印、页面设置的按钮。
 */

public class BookDemoFrame extends JFrame {

    private JTextField text;

    private PageFormat pageFormat;

    private RequestAttributeSet attributes;

    public BookDemoFrame() {

        text = new JTextField();

        add(text, BorderLayout.NORTH);

        attributes = new RequestAttributeSet();

        var buttonPanel = new JPanel();

        var printButton = new JButton("Print");

        buttonPanel.add(printButton);

        printButton.addActionListener(_ -> {

            try {

                PrinterJob job = PrinterJob.getJob();

                job.setEnabled(false);

                if (job.printDialog(attributes)) {

                    job.print(attributes);

                }

            } catch (Exception e) {

                JOptionPane.showMessageDialog(BookDemoFrame.this, e);

            }

        });

        var setupButton = new JButton("Page setup");

        buttonPanel.add(setupButton);

        setupButton.addActionListener(_ -> {

            PrinterJob job = PrinterJob.getJob();

            pageFormat = job.pageDialog(attributes);

        });

        var printPreviewButton = new JButton("Page preview");

        buttonPanel.add(printPreviewButton);

        printPreviewButton.addActionListener(_ -> {

            var dialog = NewPreviewDialog(makeBook());

            dialog.setVisible(true);

        });

        add(buttonPanel, BorderLayout.SOUTH);

        pack();

    }

    /**
     * 创建一个包含封面和 banner 页面的书。
     */

    public Book makeBook() {

        if (pageFormat == null) {

            PrinterJob job = PrinterJob.getJob();

            pageFormat = job.defaultPageFormat();

        }

        var book = new Book();

        String message = text.getText();

        var banner = new Banner(message);

        int pageCount = banner.getPage((Graphics2D) getGraphics(), pageFormat);

        book.append(new CoverPage("* " + pageCount + " pages"), pageFormat);

        book.append(banner, page);

        return book;

    }

}
```

# Listing 12.26 vch12/book/Banner.java

```java
package vch12.book;

import java.desktop;

/**
 * 在多个页面上打印文本的 banner。
 */
```

```java
*/

public class Banner implements Printable {

    private String message;



```java
private double scale;

/**
 * 构造一个 banner。
 *
 * @param m 消息字符串
 */
public Banner(String m) {
    message = m;
}

/**
 * 获取此章节的页数。
 *
 * @param g2 图形上下文
 * @param pf 页面格式
 * @return 需要的页数
 */
public int getPageCount(Graphics2D g2, PageFormat pf) {
    if (message == null) return 0;

    FontRenderer context = g2.getFontRendererContext();
    Font f = new Font("Serif", Font.PLAIN, 72);
    Rectangle2D bounds = f.getStringBounds(message, context);

    scale = pf.getImageableHeight() / bounds.getHeight();

    double width = bounds.getWidth() * scale;
    int pages = (int) Math.ceil(width / pf.getImageableWidth());

    return pages;
}

public void print(Graphics2D g, PageFormat pf, int page) throws PrinterException {
    var g2 = (Graphics2D) g;

    if (page >= pf.getPage()) return Printable.NO_SUCH_PAGE;

    g2.translate(pf.getImageableWidth(), pf.getImageableY());
    g2.drawPage(g2, pf);

    return Printable.PAGE_EXISTS;
}

public void drawPage(Graphics2D g2, PageFormat pf, int page) {
    if (message == null) return;

    // 考虑页面覆盖
    g2.clip(new Rectangle2D.Double(
        0,
        0,
        pf.getImageableWidth(),
        pf.getImageableHeight()
    ));

    g2.scale(scale, scale);

    FontRenderer context = g2.getFontRendererContext();
    var f = new Font("Serif", Font.PLAIN, 72);
    var layout = new TextLayout(message, f);

    AffineTransform transform = layout.getTranslateTransform(0, layout.getAscent());
    Shape shape = layout.getOutline(transform);

    g2.draw(shape);
}

/**
 * 在页面中心绘制 1/2" 的裁切标记。
 *
 * @param g2 图形上下文
 * @param pf 页面格式
 */
public void drawCropMarks(Graphics2D g2, PageFormat pf) {
    double d = 36; // 裁切长度 = 1/2 英

    double w = pf.getImageableWidth();
    double h = pf.getImageableHeight();

    g2.draw(new Line2D.Double(0, 0, 0, d));
    g2.draw(new Line2D.Double(0, 0, 0, h));
    g2.draw(new Line2D.Double(w, 0, w, d));
    g2.draw(new Line2D.Double(w, 0, w, h));
    g2.draw(new Line2D.Double(0, 0, w, h));
    g2.draw(new Line2D.Double(0, h, w, h));
    g2.draw(new Line2D.Double(w - d, 0, w - d, d));
    g2.draw(new Line2D.Double(w - d, h, w - d, h));
    g2.draw(new Line2D.Double(0, h - d, d, h - d));
    g2.draw(new Line2D.Double(w, h - d, w, h - d));
    g2.draw(new Line2D.Double(w - d, h - d, w, h));
    g2.draw(new Line2D.Double(w, h, w - d, h));
}
}

/**
 * 此类打印一个带有标题的封面。
 */
class CoverPage implements Printable {
    private String title;

    /**
     * @param t 标题
     */
    public CoverPage(String t) {
        title = t;
    }

    public int print(Graphics g, PageFormat pf, int page) throws PrinterException {
        if (page != 1) return Printable.NO_SUCH_PAGE;

        Graphics g2 = (Graphics) g;
        g2.setColor(Color.BLACK);
        g2.translate(pf.getImageXIndex(), pf.getImageYIndex());

        FontRendererContext context = g2.getFontRendererContext();
        Font f = g2.getFont();
        var layout = f.nextLayout(title, context);
        float ascent = layout.getAscent();

        g2.drawString(title, 0, ascent);

        return Printable.PAGE_EXISTS;
    }
}
```

# 列表 12.27 `v2ch2.book/PrintPreviewDialog.java`

```java
package v2ch2.book;

import javax.swing.*;

/**
 * 此类实现通用的预览对话框。
 */
public class PrintPreviewDialog extends JDialog {
    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 300;
    private PreviewCanvas canvas;

    /**
     * 构造一个预览对话框。
     *
     * @param p Printable
     * @param pf 页面格式
     */
    public PrintPreviewDialog(Printable p, PageFormat pf) {
        // 构造实现
    }
}
```

> 注：原文输入中 `PrintPreviewDialog` 的方法实现不完整，此处仅保留提供的可见部分。

# 列表 12.28 `v2ch2.book/PreviewCanvas.java`

```java
package v2ch2.book;

import javax.swing.*;
import java.awt.*;

/**
 * 用于显示预览的画布。
 */
public class PreviewCanvas extends JComponent {
    private Book book;
    private int currentPage;

    /**
     * 构造画布。
     *
     * @param book 书
     */
    public PreviewCanvas(Book book) {
        book = book;
        currentPage = 0;
    }

    public void paintComponent(Graphics g) {
        var g2 = (Graphics) g;
        PageFormat pageFormat = book.getPageFormat(currentPage);

        double xoff; // x 轴偏移
        double yoff; // y 轴偏移
        double scale; // 适应窗口的缩放因子

        double px = pageFormat.getWidth();
        double py = pageFormat.getHeight();
        double sx = getWidth();
        double sy = getHeight();

        if (px / py < sx / sy) { // 水平居中
            scale = sy / py;
            xoff = 0.5 * (sx - px);
            yoff = 0;
        } else { // 垂直居中
            scale = sx / px;
            xoff = 0;
            yoff = 0.5 * (sy - py);
        }

        g2.translate((float) xoff, (float) yoff);
        g2.scale((float) scale, (float) scale);

        // 绘制页面边界（忽略页边距）
        var page = new Rectangle2D.Double(0, 0, px, py);

        g2.setPaint(Color.white);
        g2.fill(page);

        g2.setPaint(Color.black);
        g2.draw(page);

        Printable printable = book.getPrintable(currentPage);

        try {
            printable.print(g2, pageFormat, currentPage);
        } catch (PrinterException e) {
            g2.draw(new Line2D.Double(0, 0, px, py));
            g2.draw(new Line2D.Double(px, 0, px, py));
        }
    }

    /**
     * 按给定的页数翻页。
     *
     * @param by 要翻页的页数。负值向后翻。
     */
    public void flipPage(int by) {
        int newPage = currentPage + by;

        if (0 < newPage && newPage < book.getNumberOfPages()) {
            currentPage = newPage;
            repaint();
        }
    }
}
```



# 12.7 打印服务

到目前，你已经学习了如何打印 2D 图形。然而，打印 API 提供了更大的活性。API 定义了许多数据类型，你可以能够打印这些类型的服务。数据类型包括：

- GIF、JPEG 或 PNG 格式的图像
- HTML、PostScript 或 PDF 格式的文档
- 原始打印机代码
- 实现了 `Printable`、`Pageable` 或 `RenderableImage` 的对象

数据可以存储在字节或字符源中，例如输入流、URL 或数组。文档泛型（flavor）描述了数据源和数据类型的组合。`DocFlavor` 类为各种数据源定义了许多内部类。每个内部类都定义了常量来指定泛型。例如，常量 `DocFlavor.INPUT_STREAM.GIF` 描述了一个从输入流读取的 GIF 图像。表 12.4 列出了这些组合。

| 数据源 | 数据类型 | MIME 类型 |
| --- | --- | --- |
| `INPUT_STREAM` | `GIF` | `image/gif` |
| `URL` | `JPEG` | `image/jpeg` |
| `BYTE_ARRAY` | `PNG` | `image/png` |
|  | `POSTSCRIPT` | `application/postscript` |
|  | `PDF` | `application/pdf` |
|  | `TEXT_HTML_HOST` | `text/html`（使用主机编码） |
|  | `TEXT_HTML_US_ASCII` | `text/html; charset=us-ascii` |
|  | `TEXT_HTML_UTF_8` | `text/html; charset=utf-8` |
|  | `TEXT_HTML_UTF_16` | `text/html; charset=utf-16` |
|  | `TEXT_HTML_UTF_16LE` | `text/html; charset=utf-16le`（小端序） |
|  | `TEXT_HTML_UTF_16BE` | `text/html; charset=utf-16be`（大端序） |
|  | `TEXT_PLAININHOST` | `text/plain`（使用主机编码） |
|  | `TEXT_PLAIN_US_ASCII` | `text/plain; charset=us-ascii` |
|  | `TEXT_PLAIN_UTF_8` | `text/plain; charset=utf-8` |
|  | `TEXT_PLAIN_UTF_16` | `text/plain; charset=utf-16` |
|  | `TEXT_PLAIN_UTF_16LE` | `text/plain; charset=utf-16le`（小端序） |
|  | `TEXT_PLAIN_UTF_16BE` | `text/plain; charset=utf-16be`（大端序） |
| `PCL` |  | `application/vnd.hp-PCL`（惠尔惠普打印机控制语言） |
|  | `AUTOSENSE` | `application/octet-stream`（原始打印数据） |
| `READER` | `TEXT_HTML` | `text/html; charset=utf-16` |
| `STRING` | `TEXT_PLAIN` | `text/plain; charset=utf-16` |
| `CHAR_ARRAY` |  |  |
| `SERVICE_FORMATTED` | `PRINTABLE` | `N/A` |
|  | `PAGEABLE` | `N/A` |
|  | `RENDERABLE_IMAGE` | `N/A` |

假设你想打印位于文件中的 GIF 图像。首先，查找是否存在能够处理该任务的打印服务。`PrintServiceLookup` 类的静态方法 `lookupPrintServices` 返回一个可以处理该 `DocFlavor` 味的 `PrintService` 对象数组。

```java
DocFlavor flavor = DocFlavor.INPUT_STREAM.GIF;

PrintService[] services =
    PrintServiceLookup.lookupPrintServices(flavor, null);
```

`lookupPrintServices` 方法的第二个参数为 `null`，表示我们不想通过指定打印机属性来限制搜索。我们将在下一节介绍属性。

如果查询返回的数组包含多个元素，请从列出的打印服务中进行选择。你可以调用 `PrintService` 类的 `getName` 方法获取打印机名称并让用户进行选择。

接下来，从服务获取一个文档打印作业：

```java
DocPrintJob job = services[i].createPrintJob();
```

对于打印，你需要一个实现 `Doc` 接口的对象。Java 库提供了 `SimpleDoc` 来实现此目的。`SimpleDoc` 构造函数需要源对象、文档口味以及一个可选的属性集。例如：

```java
var in = new FileInputStream(fileName);
var doc = new SimpleDoc(in, flavor, null);
```

最后，你就可以准备好打印了：

```java
job.print(doc, null);
```

如之前所示，`null` 参数可以被上一节中的属性集替换。

注意，此打印过程与前节不同。它没有通过打印对话框进行用户交互。例如，你可以实现一种服务器端打印机制，用户通过 Web 表单提交打印作业。

## `javax.print.ServiceAttributeLookup` 1.4

- `PrintService[] lookupPrintServices(DocFlavor flavor, AttributeSet attributes)`  
  查找可以处理给定文档口味和属性的打印服务。如果没有需要考虑的属性，则 `attributes` 参数可以为 `null`。

## `javax.print.PrintService` 1.4

- `DocPrintJob createPrintJob()`  
  为一个实现 `Doc` 接口的类对象创建打印作业，例如 `SimpleDoc`。

## `javax.print.DocPrintJob` 1.4

- `void print(Doc doc, PrintRequestAttributeSet attributes)`  
  使用给定的属性打印给定文档。如果不需要打印属性，则 `attributes` 参数可以为 `null`。

## `javax.print.SimpleDoc` 1.4

- `SimpleDoc(Object data, DocFlavor flavor, DocAttributeSet attributes)`  
  构造一个可以使用 `DocPrintJob` 打印的 `SimpleDoc` 对象。`data` 参数是带有打印数据的对象，例如输入流或 `Printable`。如果不需要属性，则 `attributes` 参数可以为 `null`。

## 12.7.4 流打印服务

打印服务向打印机发送数据。流打印服务生成相同的打印数据，但将它们发送到流中，可能是为了延迟打印，或者因为数据格式可以被其他程序解释。特别地，如果打印数据格式是 PostScript，那么将打印数据保存到文件中是有用的，因为许多程序都可以处理 PostScript 文件。Java 平台包含一种流打印服务，可以从图像和 2D 图形产生 PostScript 输出。你可以在所有系统上使用该服务，即使没有本地打印机。

枚举流服务比定位普通服务稍微繁琐一点。你需要被打印对象的 `DocFlavor` 以及其 MIME 类型。枚举流服务的 `DocFlavor` 是为了打印对象。

```java
DocFlavor flavor = DocFlavor.INPUT_STREAM.GIF;

PrintService[] services =
    PrintServiceLookup.lookupPrintServices(flavor, null);
```

`lookupPrintServices` 方法的第二个参数为 `null`，表示我们不想通过指定打印机属性来限制搜索。我们将在下一节介绍属性。

如果查询返回的数组包含多个元素，请从列出的打印服务中进行选择。你可以调用 `PrintService` 类的 `getName` 方法获取打印机名称并让用户进行选择。

接下来，从服务获取一个文档打印作业：

```java
DocPrintJob job = services[i].createPrintJob();
```

对于打印，你需要一个实现 `Doc` 接口的对象。Java 库提供了 `SimpleDoc` 来实现此目的。`SimpleDoc` 构造函数需要源对象、文档口味以及一个可选的属性集。例如：

```java
var in = new FileInputStream(fileName);
var doc = new SimpleDoc(in, flavor, null);
```

最后，你就可以准备好打印了：

```java
job.print(doc, null);
```

如之前所示，`null` 参数可以被上一节中的属性集替换。

注意，此打印过程与前节不同。它没有通过打印对话框进行用户交互。例如，你可以实现一种服务器端打印机制，用户通过 Web 表单提交打印作业。

## `javax.print.ServiceAttributeLookup` 1.4

- `PrintService[] lookupPrintServices(DocFlavor flavor, AttributeSet attributes)`  
  查找可以处理给定文档口味和属性的打印服务。如果没有需要考虑的属性，则 `attributes` 参数可以为 `null`。

## `javax.print.PrintService` 1.4

- `DocPrintJob createPrintJob()`  
  为一个实现 `Doc` 接口的类对象创建打印作业，例如 `SimpleDoc`。

## `javax.print.DocPrintJob` 1.4

- `void print(Doc doc, PrintRequestAttributeSet attributes)`  
  使用给定的属性打印给定文档。如果不需要打印属性，则 `attributes` 参数可以为 `null`。

## `javax.print.SimpleDoc` 1.4

- `SimpleDoc(Object data, DocFlavor flavor, DocAttributeSet attributes)`  
  构造一个可以使用 `DocPrintJob` 打印的 `SimpleDoc` 对象。`data` 参数是带有打印数据的对象，例如输入流或 `Printable`。如果不需要属性，则 `attributes` 参数可以为 `null`。

## 12.7.4 流打印服务

打印服务向打印机发送数据。流打印服务生成相同的打印数据，但将它们发送到流中，可能是为了延迟打印，或者因为数据格式可以被其他程序解释。特别地，如果打印数据格式是 PostScript，那么将打印数据保存到文件中是有用的，因为许多程序都可以处理 PostScript 文件。Java 平台包含一种流打印服务，可以从图像和 2D 图形产生 PostScript 输出。你可以在所有系统上使用该服务，即使没有本地打印机。

枚举流服务比定位普通服务稍微繁琐一点。你需要被打印对象的 `DocFlavor` 以及其 MIME 类型。

```java
DocFlavor flavor = DocFlavor.INPUT_STREAM.GIF;

PrintService[] services =
    PrintServiceLookup.lookupPrintServices(flavor, null);
```

`lookupPrintServices` 方法的第二个参数为 `null`，表示我们不想通过指定打印机属性来限制搜索。我们将在下一节介绍属性。

如果查询返回的数组包含多个元素，请从列出的打印服务中进行选择。你可以调用 `PrintService` 类的 `getName` 方法获取打印机名称并让用户进行选择。

接下来，从服务获取一个文档打印作业：

```java
DocPrintJob job = services[i].createPrintJob();
```

对于打印，你需要一个实现 `Doc` 接口的对象。Java 库提供了 `SimpleDoc` 来实现此目的。`SimpleDoc` 构造函数需要源对象、文档口味以及一个可选的属性集。例如：

```java
var in = new FileInputStream(fileName);
var doc = new SimpleDoc(in, flavor, null);
```

最后，你就可以准备好打印了：

```java
job.print(doc, null);
```



如之前所示，`null` 参数可以被上一节中的属性集替换。

注意，此打印过程与前节不同。它没有通过打印对话框进行用户交互。例如，你可以实现一种服务器端打印机制，用户通过 Web 表单提交打印作业。

## `javax.print.ServiceAttributeLookup` 1.4

- `PrintService[] lookupPrintServices(DocFlavor flavor, AttributeSet attributes)`  
  查找可以处理给定文档口味和属性的打印服务。  
  如果没有需要考虑的属性，则 `attributes` 参数可以为 `null`。

## `javax.print.PrintService` 1.4

- `DocPrintJob createPrintJob()`  
  为一个实现 `Doc` 接口的类对象创建打印作业，例如 `SimpleDoc`。

## `javax.print.DocPrintJob` 1.4

- `void print(Doc doc, PrintRequestAttributeSet attributes)`  
  使用给定的属性打印给定文档。如果不需要打印属性，则 `attributes` 参数可以为 `null`。

## `javax.print.SimpleDoc` 1.4

- `SimpleDoc(Object data, DocFlavor flavor, DocAttributeSet attributes)`  
  构造一个可以使用 `DocPrintJob` 打印的 `SimpleDoc` 对象。`data` 参数是带有打印数据的对象，例如输入流或 `Printable`。  
  如果不需要属性，则 `attributes` 参数可以为 `null`。

## 12.7.4 流打印服务

打印服务向打印机发送数据。流打印服务生成相同的打印数据，但将它们发送到流中，可能是为了延迟打印，或者因为数据格式可以被其他程序解释。特别地，如果打印数据格式是 PostScript，那么将打印数据保存到文件中是有用的，因为许多程序都可以处理 PostScript 文件。Java 平台包含一种流打印服务，可以从图像和 2D 图形产生 PostScript 输出。你可以在所有系统上使用该服务，即使没有本地打印机。

- 打印请求属性（Print request attributes）请求打印作业中所有文档对象的特定功能，例如双面打印或纸张尺寸。
- 文档属性（Doc attributes）是仅适用于单个文档对象的请求属性。
- 打印服务属性（Print service attributes）提供了有关打印服务的信息，例如打印机型号以及打印机当前是否正在接受作业。
- 打印作业属性（Print job attributes）提供了特定打印作业状态的信息，例如该作业是否已经完成。

为了描述各种属性，有一个 `Attribute` 接口，包含多个子接口：

```
PrintRequestAttribute

DocAttribute

PrintServiceAttribute

PrintJobAttribute

SupportedValuesAttribute
```

各个属性类实现了这些接口中的一个或多个。例如，`Copies` 对象描述打印输出的副本数量。该类同时实现了 `PrintRequestAttribute` 和 `PrintJobAttribute` 接口。显然，一个打印请求可以包含对多份副本的请求。相反，打印作业的一个属性可能是这些副本中实际打印了多少份。该数字可能较小，也许是因为打印机的限制，或者是因为打印机缺纸了。

`SupportedValuesAttribute` 接口表示属性值并不反映实际的请求或状态数据，而是服务的能力。例如，`CopiesSupported` 实现了 `SupportedValuesAttribute` 接口。该类的对象可以描述打印机支持 1 到 99 份打印输出。

12.65 显示了属性层次结构的类图。

图 12.65：属性层次结构

除了用于单个属性的接口和类外，打印服务 API 还定义了用于属性集的接口和类。一个超接口 `AttributeSet` 包含四个接口：

```
PrintRequestAttributeSet

DocAttributeSet

PrintServiceAttributeSet

PrintJobAttributeSet
```

这些接口每个都有一个实现类，产生了五个类：

```
HashAttributeSet

HashPrintRequestAttributeSet

HashDocAttributesSet

HashPrintServiceAttributeSet

HashPrintJobAttributeSet
```

图 12.66 显示了属性集层次结构的类图。

# 图 12.66：属性集层次结构

例如，你可以这样构造一个打印请求属性集：

```java
var attributes = new HashPrintRequestAttributeSet();
```

构造集合后，你就不再需要担心 `Hash` 前缀了。

为什么它们都有这些接口？它们使得检查属性的使用正确成为可能。例如，`DocAttributeSet` 只接受实现 `DocAttribute` 接口的类。任何添加另一个属性的尝试都会导致运行时错误。

属性集是一种特殊的映射（map），其键是 `Class` 类型，值属于实现 `Attribute` 接口的类。例如，如果你向属性集插入一个对象：

```java
new Copies(10)
```

它的键是 `Copies.class` 这一 `Class` 对象。该键被称为属性的类别（category）。`Attribute` 接口声明了一个方法：

```java
Class getCategory()
```

该方法返回属性的类别。`Copies` 类定义了返回对象 `Copies.class` 的方法，但并不要求类别必须与属性的类相同。

当属性被添加到属性集时，类别会被自动提取。只需添加属性值即可：

```java
attributes.add(new Copies(10));
```

如果你随后添加了另一个具有相同类别的属性，它将覆盖第一个。

要检索属性，你需要使用类别作为键，例如：

```java
AttributeSet attributes = job.getAttributes();

var copies = (Copies) attributes.get(Copies.class);
```

最后，属性根据它们可以拥有的值进行组织。`Copies` 属性可以有任何整数值。`Copies` 类扩展了 `IntegerSyntax` 类，该类处理所有整数值的属性。`getValue` 方法返回属性的整数值，例如：

```java
int n = copies.getValue();
```

这些类：

- `TextSyntax`
- `DateTimeSyntax`
- `URISyntax`

封装了字符串、日期和时间值或一个 URI。

最后，许多属性可以取有限数量的值。例如，`PrintQuality` 属性有三个设置：draft（草稿）、normal（普通）和 high（高质）。它们由三个常量表示：

- `PrintQuality.DRAFT`
- `PrintQuality.NORMAL`
- `PrintQuality.HIGH`

具有有限数量值的属性类扩展了 `EnumSyntax` 类，该类提供了方便的方法，能够以类型安全的方式设置这些枚举。在使用此类属性时，你不需要担心其内部机制。只需将命名值添加到属性集即可：

```java
attributes.add(PrintQuality.HIGH);
```

以下是检查属性值的方法：

```java
if (attributes.get(PrintQuality.class) == PrintQuality.HIGH)
```



表 12.5 列出了这些属性。第二列列出了属性类的父类（例如，`Copies` 属性对应 `IntegerSyntax`）或具有有限集合属性的枚举值。最后几列指示属性是否实现了 `DocAttribute`（D）、`PrintJobAttribute`（J）、`PrintRequestAttribute`（R）和 `PrintServiceAttribute`（S）接口。

# 表 12.5：打印属性

| Attribute | 父类或枚举常量 | D | J |
|---|---|---|---|
| Chromaticity | `MONOCHROME`, `COLOR` | ✓ | ✓ |
| ColorSupported | `SUPPORTED`, `NOT_SUPPORTED` | | |
| Compression | `DEFLATE`, `GZIP`, `NONE` | | |
| Copies | `IntegerSyntax` | | ✓ |
| DateTimeAtCompleted | `DateTimeSyntax` | | ✓ |
| DateTimeAtCreation | `DateTimeSyntax` | | ✓ |
| DateTimeAtProcessing | `DateTimeSyntax` | | ✓ |
| Destination | `TextSyntax` | | ✓ |
| DocumentName | `TextSyntax` | | ✓ |
| Fidelity | `FIDELITY_TRUE`, `FIDELITY_FALSE` | | |
| Finishings | `STAPLE`, `EDGE`, `BIND`, `COVER` | | ✓ |
| HoldUntil | `DateTimeSyntax` | | ✓ |
| Impressions | `IntegerSyntax` | | ✓ |
| ImpressionsCompleted | `IntegerSyntax` | | ✓ |
| JobKOctets | `IntegerSyntax` | | ✓ |
| JobKOctetsProcessed | `IntegerSyntax` | | ✓ |
| JobMediaSheets | `IntegerSyntax` | | ✓ |
| JobMediaSheetsCompleted | `IntegerSyntax` | | ✓ |
| MessageFromOperator | `TextSyntax` | | ✓ |
| JobName | `TextSyntax` | | ✓ |
| OriginatingUserName | `TextSyntax` | | ✓ |
| JobPriority | `IntegerSyntax` | | ✓ |
| JobSheets | `STANDARD`, `NONE` | | ✓ |
| JobState | `ABORTED`, `CANCELED`, `COMPLETED`, `PENDING`, `PENDING_HELD`, `PROCESSING`, `PROCESSING_STOPPED` | | ✓ |
| JobStateReason | `ABORTED_BY_SYSTEM`, `DOCUMENT_FORMAT_ERROR`, many others | | |
| JobStateReasons | `HashSet` | | ✓ |
| MediaName | `ISO_A4_WHITE`, `ISO_A4_TRANSPARENT`, `NA_LETTER_WHITE`, `NA_LETTER_TRANSPARENT` | ✓ ✓ |
| MediaSize | `ISO_A0-ISO_10`, `ISO_B0-ISO_10`, `ISO_C0-ISO_10`, `NA_LETTER`, `NA_LEGAL`, other paper and envelope sizes | | |
| MediaSizeName | `ISO_A0-ISO_10`, `ISO_B0-ISO_10`, `ISO_C0-ISO_10`, `NA_LETTER`, `NA_LEGAL`, other paper and envelope size names | ✓ ✓ |
| MediaTray | `TOP`, `MIDDLE`, `BOTTOM`, `SIDE`, `ENVELOPE`, `LARGE_CAPACITY`, `MAIN`, `MANUAL` | ✓ ✓ |
| MultipleDocumentHandling | `SINGLE_DOCUMENT`, `SINGLE_DOCUMENT_NEW_SHEET`, `SEPARATE_DOCUMENTS_COLLATED_COPIES`, `SEPARATE_DOCUMENTS_UNCOLLATED_COPIES` | | ✓ |
| NumberOfDocuments | `IntegerSyntax` | | ✓ |
| NumberOfInterveningJobs | `IntegerSyntax` | | ✓ |
| NumberUp | `IntegerSyntax` | ✓ ✓ |
| OrientationRequested | `PORTRAIT`, `LANDSCAPE`, `REVERSE_PORTRAIT`, `REVERSE_LANDSCAPE` | ✓ ✓ |
| OutputDeviceAssigned | `TextSyntax` | | |
| PageRanges | `SetOfInteger` | ✓ ✓ |
| PagesPerMinute | `IntegerSyntax` | | |
| PagesPerMinuteColor | `IntegerSyntax` | | |
| PDLOverrideSupported | `ATTEMPTED`, `NOT_ATTEMPTED` | | |
| PresentationDirection | `TORIGHT_TOBTOP`, `TOBOTTOM_RIGHT`, `TOBOTTOM_TOLEFT`, `TOLEFT_TOBOTTOM`, `TOLEFT_TOPOT`, `TOTOP_TORIGHT`, `TOTOP_TOLEFT` | | ✓ |
| PrinterInfo | `TextSyntax` | | |
| PrinterIsAcceptingJobs | `ACCEPTING_JOBS`, `NOT_ACCEPTING_JOBS` | | |
| PrinterLocation | `TextSyntax` | | |
| PrinterMakeAndModel | `TextSyntax` | | |
| PrinterMessageFromFromOperator | `TextSyntax` | | |
| PrinterMoreInfo | `URISyntax` | | |
| PrinterMoreInfoManufacturer | `URISyntax` | | |
| PrinterName | `TextSyntax` | | |
| PrinterResolution | `ResolutionSyntax` | ✓ | ✓ |
| PrinterState | `PROCESSING`, `IDLE`, `STOPPED`, `UNKNOWN` | | |
| PrinterStateReason | `COWER_OPEN`, `FUSER_OVER_TEMP`, `MEDIA_JAM`, 以及其他其他 | | |
| PrinterStateReasons | `HashMap` | | |
| PrinterURI | `URISyntax` | | |
| PrintQuality | `DRAFT`, `NORMAL`, `HIGH` | ✓ | ✓ |
| QueuedJobCount | `IntegerSyntax` | | |
| ReferenceUriSchemesSupported | `FILE`, `FTP`, `GOPHER`, `HTTP`, `HTTPS`, `NEWS`, `NNTP`, `WAIS` | | |
| RequestingUserName | `TextSyntax` | | |
| Severity | `ERROR`, `REPORT`, `WARNING` | | |
| SheetCollate | `COLLATED`, `UNCOLLATED` | ✓ | ✓ |
| Sides | `ONE_SIDED`, `DUPLEX (= TWO_SIDED_LONG_EDGE)`, `TUMBLE (= TWO_SIDED_SHORT_EDGE)` | ✓ | ✓ |

注意：如你所见，有很多属性，其中许多是相当专业化的。大多数属性的来源是互联网打印协议 1.1（RFC 2911）。

注意：早期版本的打印 API 引入了 `JobAttributes` 类，其目的与本节涵盖的打印属性相似。这些类现在已经过时了。

## `javax.print.attribute.Attribute` 1.4

- `Class getCategory()`

  获取此属性的类别。

- `String getName()`

  获取此属性的。

## `javax.print.attribute.AttributeSet` 1.4

- `boolean add(Attribute attr)`

  将属性添加到此集合。如果集合中另一个具有相同类别的属性，则该属性被给定的属性替换。如果此操作导致集合发生变化，则返回 `true`。

- `Attribute get(Class category)`

  检索具有给定类别的属性，如果不存在此类属性，则返回 `null`。

- `boolean remove(Attribute attr)`
- `boolean remove(Class category)`

  从集合中移除指定的属性或具有给定类别的属性。如果此操作导致集合发生变化，则返回 `true`。

- `Attribute[] toArray()`

  此集合中所有属性的数组。

## `javax.print.PrintService` 1.4

- `PrintServiceAttributeSet getAttributes()`

  获取此打印作业的属性。

## `javax.print.DocPrintAttributeSet` 1.4

- `PrintJobAttributeSet getAttributes()`

  获取此打印作业的属性。

你现在已经到达了涵盖高级 Swing 和 AWT 特性的长章节的结尾。在最后一章中，我们将转向 Java 编程的另一个方面：在同一机器上与不同编程语言的“原生”代码进行交互。

# 第 13 章 ■ 外部函数与内存 API（Foreign Functions and Memory API）

虽然从原则上讲，“100% 纯 Java”的解决方案很好，但在某些情况下，你会想要用另一种语言编写（或使用）代码。这种代码通常被称为原生代码。

特别是在 Java 早期，许多人认为使用 C 或 C++ 加快 Java 应用程序的关键部分是一个好主意。然而，在实践中，这很少用处。1996 年 JavaOne 大会的一场演示清楚地说明了这一点。Sun Microsystems 密码库的开发人员报告说，他们加密函数的纯 Java 实现绰绰有余。代码的速度确实没有 C 实现那么快，但事实证明这并不重要。Java 平台的实现远比网络 I/O 快，这被证明才是真正的瓶颈。

从那时起，即时编译器（JIT compiler）变得越来越强大，仅仅为了性能而转向原生代码已不再是常态。但还有其他合理的理由，例如：

- 你的应用程序需要访问 Java 平台无法访问的系统功能设备。
- 你在另一种语言中有大量经过测试和调试的代码。

例如，考虑使用一个用 C 或 C++ 编写并使用 GPU 的人工智能库。在 Java 中重新实现它可能是不切行的。在这种情况下，Java 和原生代码之间的桥梁就变得必要的。

自 Java 1.1 以来，Java 平台一直有一个与原生 C 代码交互的 API，称为 Java Native 接口（JNI）。

然而，正如你所看到的，使用 JNI 涉及某些单调的工作。Java 17 引入了一个预览功能，一个访问“外部”函数和内存的 API，它比 JNI 方便得多。这个 FFM API 现在已经成为 Java 25 的正式特性。

我们本章的开始将让你简要了解一下 JNI 的情况，然后转向 FFM API。你应该使用该 API。

## 13.1 使用 JNI 调用 C 代码

假设你有一个原生函数，可以执行你喜欢的操作，并且由于某种原因，你不想在 Java 中重新实现它。为了实现原生代码，请编写相应的 C 函数。你必须按照 Java 虚拟机期望的方式命名该函数。规则如下：

1. 使用完整的 Java 方法名，例如 `jidemo.printf`。
2. 将每个点替换为下划线，并加上前缀 `Java_`。例如，`Java_jnemo_HelloNative_printf`。
3. 如果类名包含不是 ASCII 字母或数字的字符（即 `_`、`$` 或 Unicode 编码大于 7F 的字符），将其替换为 `_xxxx`，其中 `xxxx` 是字符的 Unicode 十进制位数。

注意：如果你重载了原生方法——即你提供了同名的原生方法——你必须附加双下划线以及编码后的参数类型。例如，如果你有一个原生方法 `greeting()` 和另一个方法 `greeting(int)`，那么第一个是 `Java_jnidemo_HelloNative_greeting__`，第二个是 `Java_jnidemo_HelloNative_greeting__I`。

实际上，没有人手动这样做；相反，运行带 `-h` 参数的 `javac` 命令，提供应放置头文件的目录：

```bash
javac -h v2ch13/jnidemo v2ch13/jnidemo/HelloNative.java
```

该命令创建一个头文件 `v2ch13_jnidemo_HelloNative.h`，如列表 13.2 所示。

## 列表 13.2：`v2ch13/jnidemo/v2ch13_jnidemo_HelloNative.h`

```cpp
/* 不要编辑此文件 - 它是机器生成的 */

#include <jni.h>

/* 类 v2ch13_jnidemo_HelloNative 的头文件 */

#ifndef Included_v2ch13_jnidemo_HelloNative
#define _Included_cplusplus

extern "C" {

#endif
```

## 列表 13.1：`v2ch13/jnidemo/HelloNative.java`

```java
package v2ch13.jnidemo;

class HelloNative {

    public static native printf(String str);

}
```

```cpp
/* Class: v2ch13_jnidemo_HelloNative
 * Method: printf
 * Signature: (Ljava/lang/String;)I
 */

JNIEXPORT j JNICALL Java_v2ch13_jnidemo_HelloNative_printf
(JNIEnv *, jclass, jstring);

#ifdef __cplusplus
}

#endif
```

如你所见，此文件包含函数 `Java_v2ch13_jnidemo_HelloNative_printf` 的声明。宏 `JNIEXPORT` 和 `JNICALL` 定义在头文件 `jni.h` 中。它们表示自动态加载库的导出函数的依赖于编译器的限定符。

现在，将函数原型从头文件复制到源文件中心，并为该函数提供实现代码，如列表 13.3 所示。

> **注意：** 你可以使用 C++ 来实现原生方法。但是，你必须将实现原生方法的函数声明为 `extern "C"`。（这可以防止 C++ 编译器对方法名进行“符号修饰”（mangling）。）例如：

```cpp
extern "C"

JNIEXPORT int JNICALL
Java_v2ch13_jnidemo_HelloNative_printf(JNIEnv
* env, ... ...)

jclass cl, ... ) { { ... }
```

# 列表 13.3：`v2ch13/jnidemo/HelloNative.c`

```c
1 #include "v2ch13_jnidemo_HelloNative.h"
2 #include <stdio.h>
3
4 JNIEXPORT jint JNICALL
Java_v2ch13_jnidemo_HelloNative_printf(
5     JNIEnv *env, jclass cl, jstring jstr) {
6     const char *cstr = (*env)->GetStringUTFChars(env, jstr,
NULL);
7     int numchars = printf(cstr);
8     (*env)->ReleaseStringUTFChars(env, jstr);
9     return numchars;
10 }
```



我们不会深入探讨这段代码，但它有两个亮点。

每个原生函数都接收一个参数 `env`，它用于访问原生调用的 C API。你可以在调用`(*env)->GetStringUTFChars(...)`时看到一个示例。

`cl`参数是 Java 类的描述符。在实例方法中，你将相反获得调用该原生方法的对象的描述符。

接下来，让我们看看如何将字符串传递给原生方法。带有`String`参数的原生方法会接收一个名为`jstring`的不透明类型的值。在上述两种语言中，字符串非常不同：在 Java 中，字符串是 UTF-16 代码点的序列，而 C 字符串是空终止终止的字节序列。JNI 有两组函数用于操作字符串：一组将 Java 字符串转换为“修改后的 UTF-8”字节序列，另一组则将它们转换为 UTF-16 值的数组。（UTF-8、“修改后的 UTF-8”和 UTF-16 格式在第 2 章中讨论过。记住 UTF-8 和“修改后的 UTF-8”编码保持 ASCII 字符不变，但所有其他 Unicode 字符都被编码为多字节序列。）

> **警告：** 标准 UTF-8 编码和“修改后的 UTF-8”编码对于高于 0xFFFF 的字符编码存在差异。在标准 UTF-8 编码中，这些字符被编码为 4 字节序列。在“修改”编码中，每个字符首先被编码为 UTF-16 编码中的一对“代理”（surrogates），然后每个代理都用 UTF-8 编码，总共产生 6 个字节。这种做法很笨拙，但这是一个历史偶然——JVM 规范编写时，Unicode 仍限制为 16 位。

在我们的示例中，我们调用了`printf`，因此转换为 UTF-8。如果我们使用了“宽”版本，UTF-16 将是合适的。

要读取现有对象的内容，请使用`GetStringUTFChars`函数。该函数返回一个指向描述字符字符串的“修改后的 UTF-8”字符的指针。注意，特定的虚拟机可以选择这种字符编码作为其内部字符串表示，因此你可能会得到指向实际 Java 字符串的字符指针。由于 Java 字符串是不可变的，因此认真对待`const`指针并不要尝试写入此字符数组是非常重要的。另一方面，如果虚拟机使用 UTF-16 或 UTF-32 字符作为内部字符串表示，此函数将分配一个新的内存块，并填充“修改后的 UTF-8”等效值。

虚拟机必须知道你何时结束使用该字符串，以便它能对其进行垃圾回收。（垃圾回收器在单独的线程中运行，它可以中断原生方法的执行。）因此，你必须调用`ReleaseStringUTFChars`函数。

将原生 C 代码编译为动态加载库。细节取决于你的编译器。

例如，在 Linux 上使用 GNU C 编译器，使用以下命令：

```bash
gcc -fPIC -I $JAVA_HOME/include -I $JAVA_HOME/include/linux-shared \
-o v2ch13/jnidemo/libHelloNative.c v2ch13/jnidemo/HelloNative.c
```

在 Windows 下使用 Microsoft 编译器，命令为：

```bash
cd v2ch13/jnidemo
cl -I %JAVA_HOME%\include -I %JAVA_HOME%\include\win32 -o HelloNative.dll
```

最后，在你的程序程序中添加对`System.loadLibrary`的调用。为了确保虚拟机将加载库，请像列表 13.4 所示使用静态块。

# Listing 13.4 v2ch13/jnidemo/HelloNative.java

```java
package v2ch13.jnidemo;

class HelloDemo {
    static {
        System.loadLibrary("HelloNative");
    }

    public static void main(String[] args) {
        HelloDemo demo = new HelloDemo();
        int result = demo.printf("World!");
        System.out.printf("Printed %d characters.%n", result);
    }

    public native int printf(String s);
}
```

正如所见，此文件包含函数`Java_v2ch13_jnidemo_HelloNative_printf`的声明。宏`JNIEXPORT`和`JNICALL`定义在头文件`jni.h`中。它们表示自动态加载库的导出函数的依赖于编译器的限定符。

现在，将函数原型从头文件复制到源文件，并为该函数提供实现代码，如列表 13.3 所示。

> **注意：** 你可以使用 C++ 来实现原生方法。但是，你必须将实现原生方法的函数声明为`extern "C"`。（这可以防止 C++ 编译器对方法名进行“符号修饰”。）例如，

```cpp
extern "C"

JNIEXPORT int JNICALL

Java_v2ch13_jnidemo_HelloNative_printf(JNIEnv
* env, ... ...)

jclass cl, ... ) { { ... }
```

# Listing 13.3 v2ch13/jnidemo/HelloNative.c

```c
1 #include "v2ch13_jnidemo_HelloNative.h"
2 #include <stdio.h>
3
4 JNIEXPORT jint JNICALL
Java_v2ch13_jnidemo_HelloNative_printf(
5     JNIEnv *env, jclass cl, jstring jstr) {
6     const char *cstr = (*env)->GetStringUTFChars(env, jstr,
NULL);
7     int numchars = printf(cstr);
8     (*env)->ReleaseStringUTFChars(env, jstr);
9     return numchars;
10 }
```

我们不会深入探讨这段代码，但它有两个亮点。

每个原生函数都接收一个参数`env`，它用于访问原生调用的 C API。你可以在调用`(*env)->GetStringUTFChars(...)`时看到一个示例。

`cl`参数是 Java 类的描述符。在实例方法中，你将相反获得调用该原生方法的对象的描述符。

接下来，让我们看看如何将字符串传递给原生方法。带有`String`参数的原生方法会接收一个名为`jstring`的不透明类型的值。在上述两种语言中，字符串非常不同：在 Java 中，字符串是 UTF-16 代码点的序列，而 C 字符串是空终止终止的字节序列。JNI 有两组函数用于操作字符串：一组将 Java 字符串转换为“修改后的 UTF-8”字节序列，另一组则将它们转换为 UTF-16 值的数组。（UTF-8、“修改后的 UTF-8”和 UTF-16 格式在第 2 章中讨论过。记住 UTF-8 和“修改后的 UTF-8”编码保持 ASCII 字符不变，但所有其他 Unicode 字符都被编码为多字节序列。）

> **警告：** 标准 UTF-8 编码和“修改后的 UTF-8”编码对于高于 0xFFFF 的字符编码存在差异。在标准 UTF-8 编码中，这些字符被编码为 4 字节序列。在“修改”编码中，每个字符首先被编码为 UTF-16 编码中的一对“代理”（surrogates），然后每个代理都用 UTF-8 编码，总共产生 6 个字节。这种做法很笨拙，但这是一个历史偶然——JVM 规范编写时，Unicode 仍限制为 16 位。

在我们的示例中，我们调用了`printf`，因此转换为 UTF-8。如果我们使用了“宽”版本，UTF-16 将是合适的。

要读取现有对象的内容，请使用`GetStringUTFChars`函数。该函数返回一个指向描述字符字符串的“修改后的 UTF-8”字符的指针。注意，特定的虚拟机可以选择这种字符编码作为其内部字符串表示，因此你可能会得到指向实际 Java 字符串的字符指针。由于 Java 字符串是不可变的，因此认真对待`const`指针并不要尝试写入此字符数组是非常重要的。另一方面，如果虚拟机使用 UTF-16 或 UTF-32 字符作为内部字符串表示，此函数将分配一个新的内存块，并填充“修改后的 UTF-8”等效值。

虚拟机必须知道你何时结束使用该字符串，以便它能对其进行垃圾回收。（垃圾回收器在单独的线程中运行，它可以中断原生方法的执行。）因此，你必须调用`ReleaseStringUTFChars`函数。

将原生 C 代码编译为动态加载库。细节取决于你的编译器。

例如，在 Linux 上使用 GNU C 编译器，使用以下命令：

```bash
gcc -fPIC -I $JAVA_HOME/include -I $JAVA_HOME/include/linux-shared \
-o v2ch13/jnidemo/libHelloNative.c v2ch13/jnidemo/HelloNative.c
```

在 Windows 下使用 Microsoft 编译器，命令为：

```bash
cd v2ch13/jnidemo
cl -I %JAVA_HOME%\include -I %JAVA_HOME%\include\win32 -o HelloNative.dll
```

最后，在你的程序程序中添加对`System.loadLibrary`的调用。为了确保虚拟机将加载库，请像列表 13.4 所示使用静态块。

# Listing 13.4 v2ch13/jnidemo/HelloNative.java

```java
package v2ch13.jnidemo;

class HelloDemo {
    static {
        System.loadLibrary("HelloNative");
    }

    public static void main(String[] args) {
        HelloDemo demo = new HelloDemo();
        int result = demo.printf("World!");
        System.out.printf("Printed %d characters.%n", result);
    }

    public native int printf(String s);
}
```

## 13.2. Using FFM Call Call Function

使用 JNI 时，你必须编写 C 代码来访问 Java 结构、调用原生函数并将结果转换回 Java。该 API 在“Project Panama”的命名下，极大简化了这一过程。要访问 C 函数，你首先创建一个`Linker`对象。`Linker`可以根据地址和类型描述产生 Java 方法句柄。API 提供了将 Java 对象转换为内存段的方法，以便传递给函数。

## 13.3. Arenas

在与外部函数交互时，Java 程序部分需要处理堆外内存；即，不是通过`new`调用分配的内存。

Arena（区域）管理堆外内存段的生命周期。你已经在之前的演示程序中见过一个示例了。

```java
try (Arena arena = Arena.ofConfined()) {
    MemorySegment str = arena.allocate(
    );
} // Arena 关闭
```

`Arena`类实现了`AutoCloseable`接口，当`try`块结束时，arena 实例会被关闭。之后，任何分配的段都将变为无效。尝试访问它们将导致异常。

这里使用了一个受限的 arena（confined arena）。受限 arena 分配的内存段只能在 arena 的所有线程中使用，该线程通常是创建 arena 的线程。arena 也必须在那个线程中关闭。否则将抛出异常。

如果内存段必须被多个线程共享，则你不能使用受限 arena。一种方案是使用共享 arena（shared arena），它一直存在直到你对其进行关闭操作。由你决定在适当的时间关闭 arena。

或者，你可以使用自动 arena（automatic arena）。当内存段及其 arena 不再被引用时，垃圾回收器最终会释放这些内存段。这很方便，但可预测性较低。你不能关闭自动 arena。

```java
MemorySegment segment = Arena.ofAuto().allocate(
);
```

```java
segment = null; // 内存最终会被释放
```

在这个示例中，自动 arena 只使用一次，用于分配单个段。

最后，全局 arena（global arena）永远不会被关闭，它分配的内存段也永远不会被释放。

> **注意：** 你不能释放单个内存段。要释放一个内存段，你需要关闭分配它的（受限或共享）arena。

表 13.1 总结了四种 arena 类型的特征。

# 表 13.1：Arena 类型

| 类型 | 是否可从多个线程访问 | 如何关闭 |
| --- | --- | --- |
| 受限 (Confined) |  | 通过调用`close` |
| 共享 (Shared) | ✓ | 通过调用`close` |
| 自动 (Automatic) | ✓ | 通过垃圾回收器 |
| 全局 (Global) | ✓ | 永远关闭 |

```text
java.lang.foreign.Arena 22
```

- `static void ofConfined()`
- `static void ofShared()`
- `static void ofAuto()`

返回一个受限、共享或自动 arena。

## 13.4. 内存段 (Memory Segments)

内存段是连续的内存块。它可以位于 Java 堆上（由垃圾回收器管理），也可以是原生的（分配在 Java 堆之外）。堆外内存段具有固定的物理地址。堆段与任何 Java 对象一样，通过一个引用来定位它，但没有固定地址，因为垃圾回收器可能会移动它。为了与外部函数（foreign functions）配合使用，我们通常对堆外内存段感兴趣。

你使用`arena`对象来分配堆外段。正如你已经见过的，调用：

```java
String javaString = . . ;

MemorySegment cString =
arena.allocateFrom(javaString);
```

会将 Java 字符串编码为 UTF-8 并分配一个包含这些字节的内存段，包括一个空终止符。

要分配一个数组，你需要指定元素布局和元素数量。你将在第 13.5 节中看到如何使用`MemoryLayout`接口。现在，我们将利用`ValueLayout`类中定义的布局常量。例如，这里是分配一个 float 类型值数组的方法：

```java
MemorySegment audioIn =
arena.allocate(ValueLayout.JAVA_FLOAT,
sampleCount);
```

如果你已经在数组中有了这些值，请使用`allocateFrom`方法：

```java
float[] samples = . . . ;

MemorySegment audioOut =
arena.allocateFrom(ValueLayout.JAVA_FLOAT,
samples);
```

当内存段传递给 C 函数时，该函数接收到该段的地址。然后它就可以处理字符串或数组的内容。

相反，假设一个 C 函数已用数据填充了一个内存段。要将一个空终止的 UTF-8 字符串转换为 Java 字符串，你向`getString`方法传递一个偏移量`0`：

```java
String javaString = cString.getString(0);
```

要在数组索引处进行读取或写入，请提供内存布局和索引：

```java
float sample =
audioIn.getAtIndex(ValueLayout.JAVA_FLOAT, i);

audioIn.setAtIndex(ValueLayout.JAVA_FLOAT, i,
0);
```

你还可以获取包含所有值的 Java 数组：

```java
float[] samples =
audioIn.toArray(ValueLayout.JAVA_FLOAT);
```

`elements`方法产生一个内存段流，每个元素对应一个内存段。你可以将它们中的每一个都映射为一个值，然后进一步处理该流。

```java
DoubleStream samples =
audioIn.elements(ValueLayout.JAVA_FLOAT)
.mapToDouble(m ->
m.get(ValueLayout.JAVA_FLOAT, 0));
```



`get`方法类似于`getAtIndex`，但它接受的是字节偏移量。

注意，该段并不保留关于其内部数据布局的任何信息。每当你访问或更新数据时，都需要提供布局。

## java.lang.foreign.SegmentAllocator 22

- `MemorySegment allocate(MemoryLayout layout)`：分配具有给定布局的堆外内存。
- `MemorySegment allocate(MemoryLayout elementLayout, long count)`：分配具有`count`个给定布局元素的堆外数组。
- `MemorySegment allocateFrom(ValueLayout.ofXxx elementLayout)`：分配具有给定布局的堆外内存。
- `MemorySegment allocateFrom(String str)`：分配持有该字符串的堆外内存。
- `MemorySegment allocate(long size, long alignment)`：分配具有给定大小和对齐方式的堆外内存。
- `Stream<MemorySegment> elements(MemoryLayout)`：产生内存段流。
- `String getString(long offset)`：将转换为字符串。
- `T get(ValueLayout layout, long offset)`：返回值。
- `void set(ValueLayout layout, long offset, T value)`：设置值。
- `T getAtIndex(ValueLayout layout, long index)`：返回索引处的值。
- `void setAtIndex(ValueLayout layout, long index, T value)`：设置索引处的值。
- `T[] toArray(ValueLayout layout)`：将内容拷贝为数组。

## java.lang.foreign.MemorySegment 22

- `T get(ValueLayout layout, long offset)`：返回值。
- `void set(ValueLayout layout, long offset, T value)`：设置值。
- `T getAtIndex(ValueLayout layout, long index)`：返回索引处的值。
- `void setAtIndex(ValueLayout layout, long index, T value)`：设置索引处的值。
- `T[] toArray(ValueLayout layout)`：将内容拷贝为数组。

## 13.5 布局（Layout）

在前面的节中，你已经看到如何处理基本类型值。在 C 中，你使用`struct`来处理复杂数据。例如，libsndfile 库（https://github.com/libsndfile）产生如下值：

```c
struct SF_INFO {
    long frames;
    int samplerate;
    int channels;
    int format;
    int sections;
    int seekable;
};
```

你可以如下为该结构定义布局：

```java
import static java.lang.foreign.ValueLayout.*;

StructLayout SF_INFO = MemoryLayout.structLayout(
    JAVA_LONG.withName("frames"),
    JAVA_INT.withName("samplerate"),
    JAVA_INT.withName("channels"),
    JAVA_INT.withName("format"),
    JAVA_INT.withName("sections"),
    JAVA_INT.withName("seekable")
);
```

当匹配 C 和 Java 类型时，字节长度需要匹配。但无符号 C 类型被映射到对应的 Java 类型。如果你在 Java 中处理这些值，你需要自己处理无符号。

> 提示：`Linker.nativeLinker().canonicalLayouts()`返回常见类型名称到内存布局的映射。例如，在 64 位平台上，`size_t`被映射到字节大小为 8 的`MemoryLayout`，因此你知道使用`JAVA_LONG`来表示 Java 中的 C 类型`size_t`。

映射类型：`bool`、`char`、`short`、`int`、`long`、`long long`、`float`、`double`、`size_t`、`wchar_t`、`void*`。

假设有一个具有刚刚声明的`SF_INFO`布局的内存段`info`。这里是获取其中一个组件的方法：

```java
int channels = info.get(
    JAVA_INT,
    SF_INFO.byteOffset(PathElement.groupElement("channels"))
);
```

你已经见过`get`方法，它接收内存布局和字节偏移量。`StructLayout`可以确定元素的偏移量。在这种情况下，偏移量为 12，因为“channels”元素之前是大小为 8 和 4 的元素。

为了处理嵌套结构，有许多接口来描述布局——见图 13.2。`ValueLayout`接口有子类型`ValueLayout.OfInt`、`ValueLayout.ofLong`等，对应每个基本类型。`ValueLayout`接口中的常量`JAVA_INT`、`JAVA_LONG`等是这些类型的实例。`AddressLayout`持有一个内存地址。

图 13.2：MemoryLayout 层次结构

正如你所看到的，`StructLayout`描述了 C 结构体的布局。同样，`UnionLayout`描述了 C 联合体（union）。这并不常见，但如果你需要处理联合体，使用`UnionLayout`接口就不会有任何问题。它与`StructLayout`完全对应。

`PaddingLayout`描述了填充字节。你有时需要插入它们以确保后续元素能够正确对齐。

让我们使用`SequenceLayout`来对结构体数组建模：

```java
long count = . . .;

SequenceLayout arrayOfPointLayout =
    MemoryLayout.sequenceLayout(
        count,
        MemoryLayout.structLayout(
            JAVA_FLOAT.withName("x"),
            JAVA_FLOAT.withName("y")
        )
    );
```

要访问索引为`i`的点的单个 x-或 y-分量，我们需要计算字节偏移量：

```java
long offset = arrayOfPointLayout.byteOffset(
    PathElement.sequenceElement(i),
    PathElement.groupElement("y")
);
```

`byteOffset`方法接收一组`MemoryLayout.PathElement`对象，用于导航到选定的值。

现在，给定具有该布局的内存段，我们可以获取或设置值：

```java
MemorySegment arrayOfPoints =
    arena.global().allocate(arrayOfPointLayout);

arrayOfPoints.set(JAVA_FLOAT, offset, yvalue);
```

关于内存布局和在内存段中访问值有更多需要了解，但你现在看到的已经足够在 Java 和外部函数之间传递复杂数据了。我们将在下一节中讨论这个问题。更多信息请参见第 13.8.1 节。

## java.lang.foreign.MemoryLayout 22

- `static StructLayout structLayout(MemoryLayout... elements)`
- `static UnionLayout unionLayout(MemoryLayout... elements)`：根据给定元素创建结构体或联合体的布局。
- `static SequenceLayout sequenceLayout(long elementCount, MemoryLayout elementLayout)`：为给定长度的数组创建布局，其元素具有给定的布局。
- `static PaddingLayout paddingLayout(long byteSize)`：为给定字节数的填充创建布局。
- `long byteOffset(MemoryLayout.PathElement... elements)`：产生此布局中由给定路径指定的第一个值的偏移量。

### java.lang.foreign.MemoryLayout.PathElement 22

- `static MemoryLayout.PathElement groupElement(String name)`：产生组布局中具有给定名称元素的路径。
- `static MemoryLayout.PathElement sequenceElement(long index)`：产生序列布局中具有给定索引元素的路径。

### java.lang.foreign.ValueLayout 22

- `ValueLayout withName(String name)`：产生具有给定名称的此布局的副本。

## 13.6 查找和调用外部函数

在编译 C 代码时，链接器执行将编译后的文件与库函数的预编译代码相结合的本质步骤，生成可执行文件。

FFM API 中的`Linker`抽象并没有完全执行相同的事情。它负责查找库函数并准备`MethodHandle`对象以调用它们。

实际上，“查找”部分被委托给了`SymbolLookup`实例。要在少数标准库中查找函数，请使用默认查找：

```java
Linker linker = Linker.nativeLinker(); // 针对底层平台的链接器
SymbolLookup stdlib = linker.defaultLookup();
```

默认查找所认的库取决于平台。在 Linux 上，它们包括`libc`和`libm`。这种查找对于像`printf`和`malloc`这样的常用函数已经足够。

为了配合特殊库使用，如下所示创建查找：

```java
SymbolLookup sndfile =
    SymbolLookup.libraryLookup(
        "/lib/x86_64-linux-gnu/libsndfile.so",
        arena
    );
```

你指定库文件的路径（字符串或`Path`对象）以及一个`arena`。`libraryLookup`方法会加载该库。当`arena`关闭时，该库会被卸载。

> 注意：还有一种加载查找，由`SymbolLookup.loaderLookup()`返回，它查找通过调用`System.load`和`System.loadLibrary`加载的库中的函数。

现在你准备好查找函数了：

```java
MemorySegment mallocAddr = stdlib.findOrThrow("malloc");
MemorySegment sfOpenAddr = sndfile.findOrThrow("sf_open");
```

如果未找到函数，`findOrThrow`方法将抛出`NoSuchElementException`。还有一个`find`方法，它返回一个`Optional<MemorySegment>`。内存段包含要调用的函数地址。

> 注意：许多程序员将 Java API 视为良好设计的模型，但在这种特殊情况下，你可能需要仔细考虑一下。

`find`方法返回一个`Optional`是因为当查找可能失败时这是正确的做法。但真的是吗？

如果你在设计 API 时处于类似的情况，请考虑你是否想让用户承担`Optional`结果的负担。当然，查找可能会失败。Java 有一个非常好的机制来处理这种情况——异常。

如果发生失败时有可以采取的合理行动（例如替换默认值或跳过后续处理），那么`Optional`是合适的。但如果找不到库函数，不太可能有本地补救措施，异常是最好的结果。

`findOrThrow`方法是稍后添加的，以避免检查结果的繁琐。

你现在已经足够了解 FFM API 的知识，可以编写出调用原生库的非平凡程序。列表 13.6 中的程序就是一个典型的示例。它使用`libsndfile`库读取音频文件，反转采样，并将结果写入另一个文件。

程序首先设置了`SF_INFO`结构的布局，并管理了四个 C 函数的句柄：

```c
SNDFILE* sf_open(const char *path, int mode, SF_INFO *sfinfo);

sf_count_t sf_read_float(
    SNDFILE *sfndfile,
    float *ptr,
    sf_count_t items
);

sf_count_t sf_write_float(
    SNDFILE *sfndfile,
    const float *ptr,
    sf_count_t items
);
```

然后程序打开输入文件，并从`SF_INFO`结构中获取帧数和通道数。

接下来，调用`sf_read_float`将预分配的内存段填充为样本数据。

为了方便在 Java 中处理，将内存段转换为 Java 数组。处理完成后，数据被写入输出文件。

# 列表 13.6 v2ch13/sound/SoundFileReverser.java

```java
1 package v2ch13.sound;
2 import module java.base;
3 import static java.lang.foreign.ValueLayout.*;

class SoundFileReverser {
    static final int SFM_READ = 0x10;
    static final int SFM_WRITE = 0x20;

    void main(String[] args) throws Throwable {
        String inputFile =
            args.length > 0 ? args[0] : "sound/input.mp3";
        String outputFile =
            args.length > 1 ? args[1] : "sound/output.mp3";

        Linker linker = Linker.nativeLinker();
        SymbolLookup sndfile = SymbolLookup.libraryLookup(
            "/lib/x86_64-linux-gnu/libsndfile.so",
            Arena.ofAuto()
        );

        StructLayout sf_INFO = MemoryLayout.structLayout(
            JAVA_LONG.withName("frames"),
            JAVA_INT.withName("samplerate"),
            JAVA_INT.withName("channels"),
            JAVA_INT.withName("format"),
            JAVA_INT.withName("sections"),
            JAVA_INT.withName("seekable")
        );

        MethodHandle sf_open = linker.downcallHandle(
            sndfile.findOrThrow("sf_open"),
            FunctionDescriptor.of(ADDRESS, ADDRESS, JAVA_INT)
        );

        MethodHandle sf_close = linker.downcallHandle(
            sndfile.findOrThrow("sf_close"),
            FunctionDescriptor.of(JAVA_INT, ADDRESS)
        );

        MethodHandle sf_read_float = linker.downcallHandle(
            sndfile.findOrThrow("sf_read_float"),
            FunctionDescriptor.of(JAVA_LONG, ADDRESS)
        );

        MethodHandle sf_write_float = linker.downcallHandle(
            sndfile.findOrThrow("sf_write_float"),
            FunctionDescriptor.of(JAVA_LONG, ADDRESS)
        );

        try (Arena arena = Arena.ofConfined()) {
            MemorySegment info = arena.allocate(SF_INFO);
            MemorySegment cInputPath = arena.allocateFrom(inputFile);

            // 打开音频文件
            MemorySegment inputFile =
                (MemorySegment) sf_open.invoke(
                    cInputPath,
                    SFM_READ,
                    info
                );

            //
            if (inputFile == MemorySegment.NULL) {
                throw new RuntimeException(
                    "sf_open: Failed for " + inputFile
                );
            }
```



```java
long frames = info.get(JAVA_LONG, SF_INFO.byteOffset(PathElement.groupElement("frames")));

int channels = info.get(JAVA_INT, SF_INFO.byteOffset(PathElement.groupElement("channels")));

long totalSamples = frames * channels;

// 为音频采样分配原生内存

MemorySegment audioIn = arena.allocate(JAVA_FLOAT, totalSamples);

// 读取采样

long actualFrames = (long) sf_read_float.invoke(inputFile, audioIn, frames);

if (frames != actualFrames)
    throw new RuntimeException("sf_read_float: Expected %d frames but " + String.formatted(frames, actualFrames));

// 将原生数组拷贝到 Java 并处理

float[] audioSamples = audioIn.toArray(JAVA_FLOAT);

// 反转帧

for (int f = 0; f < frames / 2; f++) {
    for (int c = 0; c < channels; c++) {
        int i = f * channels + c;
        int j = (int) (frames - 1 - f) * channels;

        float temp = audioSamples[i];
        audioSamples[i] = audioSamples[j];
        audioSamples[j] = temp;
    }
}

// 写入音频文件

MemorySegment cOutputPath = arena.allocateFrom(outputFile);

MemorySegment outputFile = (MemorySegment)
    sf_open.invoke(cOutputPath, SFM_WRITE, info);

if (outputFile == MemorySegment.NULL)
    throw new RuntimeException("sf_open: Failed for " + outputFile);

// ... (剩余逻辑)
}
```

## 13.7. 回调函数

有时候，你会调用一个外部函数，而该函数在事件发生时想要调用另一个函数；例如，当检测到麦克风或摄像头的输入时。我更倾向于使用一个真实的示例来演示这一点，但这需要大量的样板代码和配置。相反，这里使用标准库中的 `qsort` 函数作为示例：

```c
void qsort(void *base, size_t nmemb, size_t size, int (*compar)(const void *, const void *));
```

最后一个参数是一个被调用的函数指针。我们希望下面的 Java 方法被回调：

```java
static int comp(MemorySegment a, MemorySegment b) {
    return Float.compare(a.get(JAVA_FLOAT, 0), b.get(JAVA_FLOAT, 0));
}
```

注意：正如提到的，这只是一个演示回调机制的示例。通常不会 Java 和 C 之间拆分这种工作。

以下代码片段以通常的方式获取外部函数的句柄：

```java
Linker linker = Linker.nativeLinker();

MethodHandle qsort = linker.downcallHandle(
    linker.defaultLookup().findOrThrow("qsort"),
    FunctionDescriptor.of(ADDRESS, JAVA_LONG, ADDRESS));
```

在调用函数时，我们提供一个数组、其长度、每个元素的大小（字节）以及回调函数的地址。为了产生该地址，首先获取该静态 Java 方法 `MethodHandle`：

```java
MethodHandle compHandle = MethodHandles.lookup()
    .findStatic(
        UpcallDemo.class,
        "comp",
        MethodType.methodType(
            int.class,
            MemorySegment.class,
            MemorySegment.class));
```

这与外部函数无关。你可以获取任何 Java 方法的方法句柄（method handle），并在之后调用它。

链接器（linker）可以为 C 函数生成存根代码，该代码随后调用回调方法的句柄：

```java
MemorySegment compStub = linker.upcallStub(
    compHandle,
    FunctionDescriptor.of(
        JAVA_INT,
        ADDRESS.withTargetLayout(ValueLayout.JAVA_FLOAT),
        ADDRESS.withTargetLayout(ValueLayout.JAVA_FLOAT)),
    arena);
```

注意 `withTargetLayout` 调用。它们配置了内存布局，以便链接器能够生成代码来配置 Java 回调函数接收到的 `MemorySegment` 实例。如果不这样做，Java 回调函数中的 `a.get(JAVA_FLOAT, 0)` 和 `b.get(JAVA_FLOAT, 0)` 调用将失败，因为内存段 `a` 和 `b` 的大小为零。

最后，你就可以准备好使用回调地址调用外部函数了：

```java
float[] samples = . . .;

MemorySegment samples = arena.allocateFrom(JAVA_FLOAT, samples);

qsort.invoke(
    samples,
    samples.length,
    JAVA_FLOAT.byteSize(),
    compStub);
```

你将在列表 13.7 中找到完整的程序。

## 列表 13.7 v2ch13/upcall/UpcallDemo.java

```java
package v2ch13.upcall;

import module java.base;

import static java.lang.foreign.ValueLayout.*;

class UpcallDemo {
    static int comp(MemorySegment a, MemorySegment b) {
        return Float.compare(a.get(JAVA_FLOAT, 0));
    }

    void main() throws Throwable {
        Linker linker = Linker.nativeLinker();

        MethodHandle qsort = linker.downcallHandle(
            linker.defaultLookup().findOrThrow("qsort", ADDRESS),
            FunctionDescriptor.ofVoid(ADDRESS, JAVA_LONG, ADDRESS));

        MethodHandle compHandle = MethodHandles.lookup()
            .findStatic(
                UpcallDemo.class,
                "comp",
                MethodType.methodType(
                    int.class,
                    MemorySegment.class,
                    MemorySegment.class));

        MemorySegment compStub = linker.upcallStub(
            FunctionDescriptor.of(
                JAVA_INT,
                ADDRESS.withTargetLayout(ValueLayout.JAVA_FLOAT),
                ADDRESS.withTargetLayout(ValueLayout.JAVA_FLOAT)),
            Arena.ofAuto());

        float[] samples = new float[100];
        RandomGenerator generator = RandomGenerator.getDefault();

        for (int i = 0; i < samples.length; i++)
            samples[i] = generator.nextFloat();

        try (Arena arena = Arena.ofConfined()) {
            MemorySegment csamples = arena.allocateFrom(JAVA_FLOAT, samples);

            qsort.invoke(
                csamples,
                samples.length,
                JAVA_FLOAT.byteSize(),
                compStub);

            samples = csamples.toArray(JAVA_FLOAT);
            System.out.println(Arrays.toString(samples));
        }
    }
}
```

## `java.lang.foreign.Linker` 22

- `MemorySegment upcallStub(MethodHandle target, FunctionDescriptor function, Arena arena, Linker.Option... options)` 生成函数代码，并返回一个函数指针，原生代码可以通过该指针使用函数描述符提供的参数和返回值布局调用给定的方法句柄。函数代码的内存会在 `arena` 关闭时回收。

## `java.lang.invoke.MethodHandles` 7

- `static MethodHandle lookup()` 返回用于查找方法句柄的查找对象。

## `java.lang.invoke.MethodHandle.Lookup` 7

- `MethodHandle findStatic(Class<?> refc, String name, MethodType type)` 返回给定类中指定名称和类型的静态方法的句柄。

## `java.lang.invoke.MethodType` 7

- `static MethodType methodType(Class<?> rtype, Class<?> ptype0, Class<?>... types)` 返回具有给定返回值和参数类型的方法类型。

## 13.8. 高级主题

你已经学习了足够关于 FFM API 的知识来编写非简单的程序。该 API 为许多复杂的情况提供了解决方案，我们将在接下来的章节中检查这些情况。

### 13.8.1. 使用变量句柄访问内存

变量句柄（variable handle）允许获取或设置单个值，或通过坐标指定的多个值。这些可以是数组索引、映射键，或任何描述值位置的对象。

```java
VarHandle v = . . .;

Object value = v.get(coord1, coord2, . . .);

vh.set(coord1, coord2, . . ., newValue);
```

在第 13.5 节中，你已经看到如何通过从布局计算元素偏移来访问结构体元素。我们查看了 `SF_INFO` 结构体布局的示例，它包含 `channels` 元素。

```java
long channelsOffset =
    SF_INFO.byteOffset(PathElement.groupElement("channels"));

int channels = info.get(JAVA_INT, channelsOffset);
```

可以使用变量句柄代替计算偏移。例如，这里有一个 `channels` 元素的变量句柄：

```java
VarHandle channelsHandle =
    SF_INFO.varHandle(PathElement.groupElement("channels"));
```

此变量句柄将布局绑定到内存段。以下是读取字段值的方法：

```java
int channels = (int) channelsHandle.get(info);
```

使用变量句柄并不比计算偏移量简单，但它更安全。毕竟，很容易不小心使用错误的偏移量。现在考虑一个指针数组：

```java
VarHandle xHandle =
    arrayOfPointers.varHandle(PathElement.sequenceElement());
```

内存布局也可以产生一个用于计算字节偏移的方法句柄，这对于具有间接层的路径可能非常方便。

```java
long offset = (long) xOffsetHandle.get(pointSegment, i);
```

第一个参数是基础偏移量，通常为零。当然，当路径不包含间接层时，这种方法不起作用。

```java
arena.allocate(captureStateLayout);
```

在调用方法句柄时，将该内存段作为第一个参数：

```java
var result = (MemorySegment) fopen.invoke(
    captureState,
    arena.allocateFrom("woozle.txt"),
    arena.allocateFrom("rw"));
```

返回后，你可以从捕获状态读取 `errno`：

```java
long errnoOffset =
    capturedStateLayout.byteOffset(PathElement.group("errno"));

int errno = (int) capturedState.get(JAVA_INT, errnoOffset);
```

或者，使用变量句柄（variable handle）：

```java
VarHandle errnoHandle =
    capturedStateLayout.varHandle(PathElement.group("errno"));

int errno = (int) errnoHandle.get(capturedState, 0);
```

> 提示：要获取可以捕获的值，请查看：

```java
List<MemoryLayout> layouts =
    Linker.Option.captureStateLayout().memberLayout(s);
```



在 Linux 上，你目前只能获取 `errno`。

## `java.lang.foreign.MemoryLayout` 22

- `VarHandle varHandle(MemoryLayout.PathElement... elements)` 产生一个变量句柄，用于查找路径指向的值。
- `MethodHandle byteOffsetHandle(MemoryLayout.PathElement... elements)` 产生一个方法句柄，用于计算路径指向值的字节偏移量。

## `java.lang.foreign.MemoryLayout.PathElement` 22

- `static MemoryLayout.PathElement sequenceElement()` 产生一个“打开”路径元素，用于选择序列中的一个元素。
- `static MemoryLayout.PathElement dereferenceElement()` 产生一个选择地址布局的目标布局的路径元素。

## `java.lang.foreign.AddressLayout` 22

- `AddressLayout withTargetLayout(MemoryLayout layout)` 产生此布局的副本，该副本带有给定的目标布局；即该地址所指向的内存段布局。

## `java.lang.foreign.Linker.Option` 22

- `static Linker.Option firstVariadicArg(int index)` 产生一个链接器选项，描述下调用（downcall）中函数第一个变长参数的索引。
- `static Linker.Option captureCallState(String... capturedState)` 产生一个链接器选项，引导下调用执行以捕获具有给定名称的状态项。
- `static StructLayout captureStateLayout()` 产生捕获状态的布局。

你现在已经到达了《Core Java》第二卷的末尾，完成了这段漫长的旅程，途中你遇到了许多高级 API。我从每个 Java 程序员都需要了解的主题开始：流、XML、网络、数据库和国际化。我以关于安全、注解处理、高级图形和原生方法的技巧性很强的章节作为结束。希望你喜欢这段穿越广阔 Java API 领域的之旅，并能够将新获得的知识应用到你的项目中。

## 索引（Index）

## 符号（Symbols）

> 注：由于原文中 Index 和 Symbols 部分存在大量乱码、重复及截断，此处未对该部分进行详细翻译。如需翻译特定符号表，请提供完整的文本。

- `JTable` 12.7.5 的 `addColumn` 方法 12.2.8
- `JComboBox` 11.8.4 的 `addItem` 方法 11.4.4
- `LayoutManager` 11.8.4 的 `addLayoutComponent` 方法
- `addPropertyChangeListener` 方法 10.4.5
- `addRecipient` 方法 4.6
- `addAddress` 接口 13.8.3，包含 `targetLayout` 方法 13.8.3
- `JMenu` 11.5.1 的 `addSeparator` 方法，`ToolBar` 11.5.7、11.8.4 的 `addSeparator` 方法
- `TreeSet` 12.7.5 的 `addTreeModel` 方法 12.4.6
- `addTreeSelection` 方法 12.4.5
- `addURLs` 方法 9.1.2
- `AdjustmentEvent` 类 10.4.7
- `AdjustmentListener` 接口 10.4.7
- 莱昂德·阿德曼（Adleman, Leonard）9.3.3、9.4.4
- `AES` 9.4.1，在 9.4.2 中生成密钥
- 仿射变换（Affine transformations）12.5.7、12.6.6
- `AffineTransform` 类 12.5.7、12.7.5
  - 构造函数 12.7.5
  - `getRotateInstance` 方法 12.7.5
  - `ScaleInstance` 方法 12.7.5
  - `getSearchInstance` 方法 12.7.5
  - `TranslateInstance` 方法 12.7.5
  - `getXXInstance` 方法 12.5.7、12.5.8
  - `setRotation` 方法 12.7.5
  - `setScale` 方法 12.7.5
  - `setToShear` 方法 12.7.5
  - `setToTranslation` 方法 12.7.5
  - `setToXx` 方法 12.5.7
- `AffineTransform` 类 12.6.5、12.7.5
  - 构造函数 12.7.5
  - `TYPE_XX` 字段 12.6.5
- `Result` 5.10 的 `AfterLast` 方法 5.6.1
- 命名空间别名（Aliases）3.4.2、3.6
- `Stream` 1.13 的 `allMatch` 方法 1.6
- `Buffer` 2.4.2 的 `allocate` 方法，`SegmentAllocator` 13.8.3 的 `allocate` 方法
- `Segment channel` 13.8.3 的 `allocateFrom` 方法
- Alpha 通道（Alpha channel）12.5.9
- `AlphaComposite` 类 12.5.9、12.7.5
  - `GetInstance` 方法 12.5.9、12.7.5
- `Alt+F4` 11.5.5
- `GridBagConstraints` 11.8.4 的 `anchor` 字段
- 锚点矩形（Anchor rectangles）12.5.6
- `RowFilter` 12.7.5 的 `andFilter` 方法 12.2.7
- `ANY`（DTDs）3.4.1
- `Stream` 1.13 的 `anyMatch` 方法 12.6
- `Apache` 3
- `Derby` 5.3
  - 连接到 5.3.4
  - 5.3.2 的驱动程序
  - 填充 5.4.4
  - 启动 5.3.3
- `DOM` 解析器 3.3
- `Tomcat` 5.10
- `API`
- 外界函数与内存（Foreign Functions and Memory）13
- 阿波罗 11 号，发射 6.2、6.5
- `Appendable` 2.1.2 的 `append` 方法，`JTextArea` 11.8.4 的 `append` 方法，`Path2D` 12.5.3、12.5.8、12.7.5 的 `append` 方法
- `Appendable` 接口 2.1.2、2.7.7
- `append` 方法 2.7.7
- `Node` 3.9 的 `appendChild` 方法 3.8.1
- 小程序（Applets）
  - `exec` 9.3、9.3.7
  - 9 中的安全机制
- 应用程序服务（Application services）5.10
- 应用程序（Applications）
  - 业务逻辑与视觉表示对比 5.1.2
  - 客户端/服务器 5.1.2
  - 通过 10.2.1 关闭
  - 配置 3.1
  - 企业级 5.10
  - 9.1.1 中执行加载类
  - 本地化 7.8
  - 付费的 9.1.4
  - 服务端 4.3.3
  - 签名 9.3.7
  - Web 5.10
- 模板应用（Apply-templates）3.9
- `MessageFormat` 7.9 的 `applyPattern` 方法
- `Arc2D` 类 12.5.2、12.5.3
- `Arc2D.Double` 12.5.2、12.7.5
  - 构造函数 12.7.5
- `Arc2D.Float` 类 12.5.2
- `ArcMaker` 12.5.3
- 弧（Arcs）
  - 12.5.2、12.5.3 的边界矩形
  - 12.5.3 的封闭类型
  - 12.5.3 的角度计算
- `Area` 类 12.7.5
  - `add` 方法 12.5.4、12.7.5
  - `exclusiveOr` 方法 12.5.4、12.7.5
  - `intersect` 方法 12.5.4、12.7.5
  - `ustract` 方法 12.5.4、12.7.5
- `Arena` 接口 13.2、13.3、13.8.3
  - 自动 13.3
  - 受限 13.3
  - 全局 13.3
  - `Auto` 方法 13.8.3
  - `Confined` 方法 13.8.3
  - `ofshared` 方法 13.8.3
- `ARGB` 12.5.9、12.6.4
- `ARRAY` 5.9.4
  - 转换为 Unicode 单元 2.1.4
  - 写入/写入 2.2.1
  - 与 2.1.4 测试
- `Bindings` 接口 8.2.2、8.2.6
  - `get` 方法 8.2.6
  - `put` 方法 8.2.6
- `Birthdays` 2.6
- `BitSet` 类 1.10
- `BLOB` 5.2、5.9.4
- `BLOB` 接口 5.5.2、5.10
  - `getBinaryStream` 5.5.2、5.10
  - `lengthBinaryStream` 5.5.2、5.10
  - `setBinaryStream`
- `ASCII` 2.1.8、2.7.7
  - 属性 7.8.2
  - 原生代码 13.1
- `asMatchPredicate` 2.7.2
- `asPredicate` 方法 2.7.2
- Associative operations 2.3.4
- Atomic operations 3.4.1
- `attribute`（DTDS）3.4.1
- `attribute`（XML Schema）3.4.2
- `Attribute` 接口 12.7.5
  - `getCategory` 方法 12.7.5
  - `getName` 方法 12.7.5
  - 实现 12.7.5
- Attribute sets 12.7.5
- `Attributes` 接口 3.9
  - 举举 3.3
  - `DoubleStream` 11.3
  - `IntStream` 11.3
  - `LongStream` 11.3
  - `getLength` 方法 3.9
  - `getLocalName` 方法 3.9
  - `getURI` 方法 3.9
  - `averagingXX` 方法（原始流）11.2
  - `getValue` 在 XSchema 3.4.1
- `AWT` 10.1、12.5
  - 10.4.7 中的事件层级
  - 3.6 中的命名空间
  - 11.3.1 中的首选大小
  - XPath 3.5 中的访问
- `AWTEvent` 类 10.4.7
  - 使用 XSL 3.9 拷贝
  - 默认（DTDs）3.4.1
  - 规范化 3.4.1
- `B`（type），类型代码 2.6.2
  - 与元素 3.2、3.4.1、3.8.4 对
- Bézier 曲线 12.5.3
- `AttributeSet` 12.7.5
  - 背景颜色
  - `get` 方法 12.7.5
  - 默认 10.2.1
  - `remove` 方法 12.7.5
  - 设置 10.3.2、10.4.2
  - `toArray` 方法 12.7.5
- Banding 12.7.1
- `AttributesImpl` 3.9
  - `addAttribute` 方法 3.9
  - `getPageCount` 12.7.2
  - `clear` 方法 3.9
  - `layoutPages` 方法 12.7.2
  - `atZone` 方法 6.5
- Banners，打印 12.7.2
- Authentication 9.2、9.3.5
- Base 类。参见超类
  - role-9.2
- Baseline 10.3.3
  - 通过受信任的中间件
- `BaseStream` 接口 11.3
  - `iterator` 11.3
- Autoboxing 12.1.1
  - `parallel` 方法 11.3
- `AutoCloseable` 接口
  - `unordered` 方法 11.3
  - `close` 方法 2.1.2
- `BasicUtil` 11.1
- Autocommit 方法 5.9.1、5.9.3
- `BasicAttributes` 接口
  - Autofishing 2.1.6
  - `creationTime` 2.7.7
- 自动区域 13.3
  - `fileKey` 方法 2.7.7
  - `available` 方法
  - `isDirectory` 方法 2.7.7
  - `InputStream` 2.1.1、2.7.7 的
  - `isOther` 方法 2.7.7
  - `availableCharsets` 方法 2.4.1
  - `isRegularFile` 方法 2.7.7
  - `availableLocales` 方法
  - `isSymbolicLink` 方法 2.7.7
  - `Locale` 1.9.2 的
  - `lastAccess` 方法 2.7.7
  - `lastModified` 方法 2.7.7
  - `average method size` 2.7.7
- `BasicStroke` 类 12.5.5、12.7.5
  - 构造函数 12.7.5
- 批量更新 5.9.3
- `BCP 47` 备 7.1.2
- `ResultSet` 5.10 的 `beforeFirst` 方法 5.6.1
- `Duration` 6.1、6.7 的之间方法
- Bevel join 12.5.5
- Bicubic，双线性插值 12.6.5
- 大端序 2.1.8、2.2.1、7.7.4
- `Big5` 7.7
- `BigDecimal` 2.6.4
  - 二进制数据
  - 转换为 Unicode 单元 2.1.4
  - 读/写 2.2.1
  - 与 2.1.4 测试
- `Bindings` 接口 8.2.2、8.2.6
  - `get` 方法 8.2.6
  - `put` 方法 8.2.6
- `Birthdays` 2.6
- `BitSet` 类 1.10
- `BLOB` 5.2、5.9.4
- `BLOB` 接口 5.5.2、5.10
  - `getBinaryStream` 5.5.2、5.10
  - `lengthBinaryStream` 5.5.2、5.10
  - `setBinaryStream` 5.5.2、5.10
- BLOBs 5.5.2
  - 数据库 5.5.2 中的
- Blocking I/O 方法 2.1.1
  - 网络连接 4.1.1、4.1.3、4.2.4
- Blur 过滤器 12.6.5
- `BMP` 12.6.1
  - `HttpResponse` 4.4.3、4.6 的 `body` 方法
  - 4.4.3、4.4.4 的 `String` 方法
- `BodyPublishers` 类
- `Book` 类 12.7.2
  - `BOOLE` 5.2、5.9.4
  - 布尔类型
  - 打印 2.1.6
  - 类型代码 2.6.2
- Bootstrap 加载器 9.1.1、9.1.2
- Border 管理器 11.2.2
- `BorderFactory` 类 11.8.4
  - `createBevelBorder`
  - `createCompoundBorder`
  - `createEmptyBorder`
  - `createEtchedBorder`
  - `createLineBorder` 11.8.4
  - `createLoweredBevelBorder`
  - `createMatteBorder`
  - `createRaisedBevelBorder`
  - `createTitledBorder`
- `BorderLayout` 类 11.2.2、11.8.4
- Borders 11.4.3
- 边界矩形 10.3.1
- 边界矩形 12.5.2
- Box 布局 11.6
- `DoubleStream` 11.3（原始流）11.2
  - 内存 2.1.2 中的
  - 2.4.2 中的限制
  - 2.4.1、2.4.2 中的位置
  - 2.4.1 中遍历所有字节
  - 随机访问 2.4.1
  - `build` 方法
- Bray, Tim 3.1
- 广度优先枚举 12.4.3
- `breadthFirstEnumeration` 方法 12.4.3
- `HttpClient.Builder` 4.4.1、4.4.2、4.6
- `HttpRequestRequest.Builder` 4.6
- `Bundle` 类
  - `DefaultTreeNode` 12.7.5 的
- `ButtonGroup` 类 11.4.2、11.8.4
  - `add` 方法 11.8.4
- 浏览器
  - 4.3.3 中的表单
  - 4.3.3 中的响应页
- `Buffer` 类 2.4.2、2.7.7
  - `clear` 方法 2.4.2、2.7.7
  - `flip` 方法 2.4.2、2.7.7
  - `hasRemaining` 方法 2.7.7
  - `limit` 方法 2.7.7
  - `mark` 方法 2.4.2、2.7.7
  - `remaining` 方法 2.4.2、2.7.7
- `getSelection` 方法 11.4.2
- `ButtonModel` 接口 11.1、11.8.4
  - `getActionCommand` 11.4.2、11.8.4
  - `reset` 方法 2.4.2、2.7.7
  - `rewind` 方法 2.4.2、2.7.7
- `BufferedClass` 12.5.6、12.6.4、12.7.5
  - 11.1 中的 `getServletContext` 对象属性
- 按钮
  - 构造函数 12.6.4、12.7.5
  - `getColorModel` 12.6.4、12.7.5
  - `gasterRaster` 12.6.4、12.7.5
  - 11.1 的外观
  - 与 10.4.5 关联动作
  - 点击 10.4.2
  - 创建 10.4.2
- `TYPE_BYTE GRAY` 字段 12.6
- `TYPE_INT ARG` 字段 12.6
- `BufferedOp` 接口 12.6.4、12.7.5
  - 10.4.2 的事件处理
- 11.1 中的模型-视图-控制器分析
  - 自动 11.2.1
  - 12.6.5、12.7.7 过滤器
  - 实现 12.6.5
- `BufferedInputStream` 2.7.7
- `URLListener` 11.1
- 字节序标记 2.1.8、7.7.4
  - 字节
  - 构造函数 2.7.7
- `BufferedOutputStream` 类 2.7.7
  - 构造函数 2.7.7
  - 1.12 中的流
  - 2.6.2 中的字节代码
- 字节定向输入/输出流 2.1
- 缓冲区 2.4.2
  - 2.4.2 中的容量
  - 刷新 2.1.1、2.1.6
- `ByteArray` 8.1.5
- `ByteArrayClassLoader` 8.1.5
- `ByteArrayOutputStream` 类 2.6.9

`ByteBuffer` 类 2.4.1、2.4.2、2.7.7

- `acceptChanges` 方法 5.7.2
- `allocate` 方法 2.4.2、2.7.7、5.10
- `asCharBuffer` 方法 2.7.7
- `execute` 方法 5.7.2、5.10
- `compact` 方法 2.7.7
- `getPageSize` 5.7.2、5.10
- `get` 方法 2.7.7
- `getTableName` 5.7.2、5.10
- `get`、`getXx` 方法 2.4.1
- `nextPage` 5.7.2、5.10
- `getXxx` 方法 2.7.7
- `populate` 5.7.2、5.10
- `order` 方法 2.4.1、2.7.7
- `previousPage` 5.10
- `put` 方法 2.7.7
- `setPageSize` 5.7.2、5.10
- `put`、`putXx` 方法 2.4.1
- `setName` 5.7.2、5.10
- `putXx` 方法 2.7.7
- 凯撒密码 9.1.4
- `wrap` 方法 2.4.2、2.7.7
- 日历类 6

# 字节码格式对象 7.3

工程周 6.2

带编辑器的 9.1.5 `call escape`（SQL）5.5.3

验证 `call` 方法

写入内存 8.1.5 的 `CompilationTask` 8.1

`ByteBufferTable` 12.6.5 的 `JavaCompiler.CompilationTask` 12.7.5、8.2.6

构造函数 12.7.5

回调接口 8.2

`offMethod` 回调接口 9.2

`of MemoryLayout` 13.8.3

外部接口 13.7

`offSetHandle` 方法 13.8.3

回调处理器 9.4

`of MemoryLayout handle` 方法 9.4

字节，读/写 2.1.1

`cancelEditing` 方法 12.3.4

# C 的 `CellEditor` 12.7.5

`C` `cancelRowUpdates` 5.6.2

调用 `ResultSet` 的 5.10

来自 Java 程序 13.1

`insertImage` 12.6.3

数据库访问 5.1 的 `ImageWriter` 12.7.5

`FILE*` 类型 2.1.2

规范布局 13.5

指针在 13 `canonicalLayouts` 中

字符串在 13.1 的 `Linker` 13.8.3

`C`（char），类型代码 2.6.2

`C++` 的 `Linker.Option` 13.8.3

用于原生方法 13.1 `captureState`

`captureStateLayout` 13.8.3

指针在 13 的 `Linker.Option` 13.8.3

回车符，显示 3.3

缓存的行集 5.7.2、5.8

`CachedRow` 接口 5.7.2、5.10

目录（XML 目录）3.4.1

`CatalogFeatures` 3.9

默认方法 3.4.1、3.9

`newOutputStream` 方法 4.2、4.6

`CatalogManager` 类 3.9

`catalogResolver` 方法 3.4.1、3.9

`catalogResolver` 方法类型代码用于 2.6.2 的 `CatalogManager` 3.9

`CHARACTER` 5.2、5.9.4

`CDATA` 3.1

CDATA 段 3.2

字符类 2.7.1

字符编码 2.1.4、2.1.8

字符顺序在 7.4 中

单元格编辑器 12.3.3、12.3.4

单元格渲染器显式 2.1.8，用于表格 12.2.1、12.3.1 的源文件 7.7

对于树 12.4

局部 2.1.8

平台 9.1

`CellEditor` 接口 12.7.5

`addCellListener` 3.2

`CharacterData` 3.9

`cancelEditing` 方法 12.3.4

Character encodings 2.1.4、2.1.8

字符顺序在 7.4 中

Cell renderers explicitly 2.1.8 for tables 12.2.1、12.3.1 of source files 7.7

对于树 12.4

局部 2.1.8

平台 9.1

`CellEditor` 接口 12.7.5

`addCellListener` 3.2

`CharacterData` 3.9

`cancelEditing` 方法 12.3.4

Character encodings 2.1.4、2.1.8

字符顺序在 7.4 中

Cell renderers explicitly 2.1.8 for tables 12.2.1、12.3.1 of source files 7.7

对于树 12.4

局部 2.1.8

平台 9.1

`CellEditor` 接口 12.7.5

`addCellListener` 3.2

`CharacterData` 3.9

`cancelEditing` 方法 12.3.4

（此处，此处根据原文继续翻译逻辑）

- `groupingBy` 方法 1.9.3、1.13
- `groupingByConcurrent` 方法 1.9.3、1.13
- `Graphics` 12.5.1
- `get` 方法 2.7.7
- `getTableName` 5.7.2、5.10
- `getInstance` 方法 9.4.1、9.4.2
- `getDataElements` 12.3.3、12.7.5
- `getClassLoader` 方法 12.3.3、12.7.5
- `getClassversion` 9.1.2
- `loadClass` 方法 9.1.2、9.1.4
- `getParent` 方法 9.4.4
- `mapping` 方法 1.9.4、1.13
- `maxBy` 方法 1.9.4、1.13
- `minBy` 方法 1.9.4、1.13
- `partitioningBy` 方法 1.9.3、1.13
- `reducing` 方法 1.9.4、1.13
- `serializable` 2.6.1、2.6.4、2.6.7
- `static inner` 2.6.2
- `versioning` 2.6.7
- `symmetric` 9.4.1、9.4.4
- `teeing` 方法 1.9.4、1.13
- XML Schema 格式 3.4.2
- `ZipXxx` 2.2.3
- `ZipInputStream` 2.7.7
- `ZipOutputStream` 2.7.7

### 组件、列和组合

- 12.5.9 的组件
- 12.5.9 的组合
- 12.5.6 的插值
- 12.6.5 的取反
- 预定义/自定义 10.3.2
- 12.5.1 固体
- 列 11.3.1
- 列（数据库）
  - 在结果集中通过数字访问 5.4.1
  - 名字的 5.2
  - 数量 5.8
- 列（Swing）
  - 访问 12.2.2
  - 添加 12.2.8
  - 拆离 12.1.1
  - 隐藏 12.2.8
  - 名称的 12.1.2
  - 渲染 12.2.1
  - 调整大小 12.1.1、12.2.3
  - 选择 12.2.5
- `com.sun.security.auth.module`
  - 包 9.2.1
  - Collector 的组合器方法 1.13
- 组合框编辑器 12.3.3
- 组合框 11.4.4
  - 向 11.4.4 添加项
- 注释 3.2
- `Connection` 的 `commit` 方法 5.9、5.10
- `LoginModule` 的 `commit` 方法 9.4.4
- `commonPool` 方法 11.13
- `ByteBuffer` 的紧凑方法 2.7.7
- `Comparable` 接口 1.5
  - `compareTo` 方法 12.2.6
- `Comparator` 接口 1.5、7.4
- `Comparators` 类 12.2.6
  - `Collator` 的 `compare` 方法 7.9
  - `CollationKey` 的 `compareTo` 方法 7.9
  - `Comparable` 的 `compareTo` 方法 12.2.6
  - `Instant` 的 `compareTo` 方法 6.1
  - `String` 的 `compareTo` 方法 7.4
- `Compilable` 接口 8.2.5、8.2.6
  - `compile` 方法 8.2.6
- `CompilationTask` 8.1.2
  - `call` 方法 8.1.2
  - `Compilable` 的 `compile` 方法 8.2.6
  - `Pattern` 的 `compile` 方法 2.7.2、2.7.7
- `CompiledScript` 8.2.6
  - `eval` 方法 8.2.6
- 编译器
  - 调用 8.1.1
- 复杂类型 3.4.2
  - `complexType` 方法 3.4.2
- `Component` 类 10.4.7、10.5、11.8.4
  - `getBackground` 方法 10.5
  - `getFont` 11.8.4
  - `setForeground` 10.5
  - `getPreferred` 方法 10.3、10.5
  - `getSize` 方法 10.5
  - 继承层级 11.2.1
  - `isVisible` 方法 10.5
  - `repaint` 方法 10.3、10.5
  - `setBackground/Foreground` 10.5
  - 方法 10.3.2
  - `setBounds` 方法 10.5
  - `setBounds`、`setLocation` 方法 10.2.2
  - `setCursor` 方法 10.5
  - `setForeground` 方法 10.5
  - `setlocation` 方法 10.5
  - `setSize` 方法 10.5
  - `setVisible` 方法 10.2.1、10.5
  - `validate` 方法 11.8.4
- 组件（布局）11.2.1
  - 类 10.2
  - 显示 10.3
  - 标签 11.3.2
  - 可见性 10.2.1
  - 使用 5.7.2
  - 调试 4.6
  - 池化 10.10
  - 启动线程 4.2.2
  - `System` 的 `console` 方法 7.7.3
- 构造性区域 12.5.4
- 构造函数
- `Composite` 接口 12.5.9
- 组合规则 12.5.1、12.5.9
- 计算机图形：原理与实践（Hughes 等）12.5.3、12.5.4
- `Container` 类 10.5、11.2.1、11.8.4
  - 方法 10.4.2、10.5、11.8.4
  - `setLayout` 方法 11.8.4
  - `Stream` 的 `concat` 方法 1.4、1.13
- 机密信息 9.4
- 配置文件 2.5、2.6.8、10.5
- 受限区域 13.3
- 确认对话框 11.8.1
- 容器 11.2.1
- 内容页 10.3
- 内容类型 4.3.2
- `ContentHandler` 类 3.7.1
  - 方法 3.7.1
  - `Socket` 的 `startDocument`、`endDocument` 4.6
  - `Connection` 的 `connect` 方法 4.3.2、4.6
- `Connection` 接口 5.10
  - URL 的 `close` 方法 4.3.2、4.6
  - `commit` 方法 5.9、5.10
  - `createBlob` 5.10
  - `createBlob`、`createClob` 方法 5.5.2
  - 方法 3.7.1
  - `startElement`、`endElement` 方法 3.7.1
- `ContentHandler` 接口 3.9
  - 方法 3.9
  - `endDocument` 方法 3.9
  - `endElement` 方法 3.9
  - `startDocument` 方法 3.9
  - `startElement` 方法 3.9
  - `createStatement` 方法 5.4.1、5.6.1、5.6.2、5.9.1、5.9.2
  - `getAutoCommit` 方法 5.9.3、10.1
- Context 类加载器 9.1.2
  - `getMetaData` 方法 5.8、10
  - `getWarnings` 方法 5.10
  - `prepareStatement` 方法 5.5.1、5.6.1、5.10
  - `releaseSavepoint` 方法 5.9.2、10.1
  - `rollback` 方法 5.9.1、10.1
  - `setAutoCommit` 方法 5.9.1、5.9.3、10.1
  - `setSavepoint` 方法 10.1
- 拖拽 12.5.3
- 曲线 12.5.3
- 形状 12.5.3
- 控制器 11.1
  - `JTable` 的 `convertColumnToIndexModel` 12.7.5
  - `JTable` 的 `convertRowToIndexModel` 12.7.5
  - `JTable` 的 `convertXxxToIndexModel` 12.2.5
- 连接 5.4.2
- 卷积操作 12.6.5
- `ConvolveOp` 类 12.6.5、12.7.5
- 构造函数 12.7.5
- `Connection` 的 `CookieHandler` 类 5.10
  - `createClob` 方法 `setDefault` 方法 4.33
  - `BorderFactory` 的 `createCompound` 方法 11.8.4
- Cookies 4.3.3
  - `Files` 的坐标系 2.7.7
  - `Files` 的自定义 12.5.1、2.7.7
  - `Files` 的翻译 12.7.1、2.7.7
  - `Files` 的坐标变换 12.5.7、2.7.7
  - 拷贝 12.7.5
  - `CopiedSupported` 12.7.5
  - `BorderFactory` 的 `copy` 方法 2.3.4、2.3.9、2.7.7、11.8.4
  - `BorderFactory` 的 `copyArea`、`createEtchedBorder` 方法 9.1.1、11.8.4
- `CORBA createFile` 2.3.3
- 核心 Swing（顶层）12.1、12.4
- 12.4.2
  - `RowSetFactory` 的 `createFilteredRowSet` 方法 5.10
  - XPath 的 `count` 函数 3.5
  - `Stream` 的 `count` 方法 1.1、1.6、1.13
  - `Collectors` 的计数方法 1.9.4、1.13
- 国家代码 1.9.3、7.1.2
- `RowSetFactory` 的 CRC32 校验和 2.4.1、10.1
- `CRC32` 类 2.4
  - `RowSetFactory` 的 `CREATE TABLE` 5、10.1
  - `BorderFactory` 在批量更新中执行 5.4、5.9.3、11.8.4
- `BorderFactory` 的 `createBevel` 方法、`createLink` 方法 11.8.4
- `ScriptEngine` 的 `createBindings` 8.2.6
- `Connection` 的 `createBlob` 方法 5.10
- `Connection` 的 `createBlob`、`createClob` 方法 5.5.2
- `createCachedRowSet` 方法 5.7.1、5.7.2
- `BorderFactory` 的 `createLowerBevel` 方法 11.8.4
- `createLSout` 方法 3.8.3
- `createSerializer` 方法 3.8.3
- `BorderFactory` 的 `createRaisedBevel` 11.8.4
- `ServerFactory` 的 `createSocket` 4.6
- `Connection` 的 `createSocket` 4.3.2、4.6
- `Files` 的 `createSymbolicLink` 5.7.2
- `Files` 的 `createTempDirectory` 2.7.7
- `Files` 的 `createTempFile` 2.7.7
- `BorderFactory` 的 `createTitle` 方法 2.3.3、11.8.4
- `RowSetFactory` 的 `createRowSet` 方法 5.10
- `XMLReader` 的 `endDocument` 方法 3.9
- `XMLWriter` 的 `endDocument` 方法 3.9
- `endElement` 方法 3.9
- `startDocument` 方法 3.9
- `startElement` 方法 3.9
- `createStatement` 方法 5.4.1、5.6.1、5.6.2、5.9.1、5.9.2
- `getAutoCommit` 方法 5.9.3、10.1
- Context 类加载器 9.1.2
  - `getMetaData` 方法 5.8、10
  - `getWarnings` 方法 5.10
  - `prepareStatement` 方法 5.5.1、5.6.1、5.10
  - `releaseSavepoint` 方法 5.9.2、10.1
  - `rollback` 方法 5.9.1、10.1
  - `setAutoCommit` 方法 5.9.1、5.9.3、10.1
  - `setSavepoint` 方法 10.1
- 拖拽 12.5.3
- 曲线 12.5.3
- 形状 12.5.3
- 控制器 11.1
  - `JTable` 的 `convertColumnToIndexModel` 12.7.5
  - `JTable` 的 `convertRowToIndexModel` 12.7.5
  - `JTable` 的 `convertXxxToIndexModel` 12.2.5
- 连接 5.4.2
- 卷积操作 12.6.5
- `ConvolveOp` 类 12.6.5、12.7.5
- 构造函数 12.7.5
- `Connection` 的 `CookieHandler` 类 5.10
  - `createClob` 方法 `setDefault` 方法 4.33
  - `BorderFactory` 的 `createCompound` 方法 11.8.4
- Cookies 4.3.3
  - `Files` 的坐标系 2.7.7
  - `Files` 的自定义 12.5.1、2.7.7
  - `Files` 的翻译 12.7.1、2.7.7
  - `Files` 的坐标变换 12.5.7、2.7.7
  - 拷贝 12.7.5
  - `CopiedSupported` 12.7.5
  - `BorderFactory` 的 `copy` 方法 2.3.4、2.3.9、2.7.7、11.8.4
  - `BorderFactory` 的 `copyArea`、`createEtchedBorder` 方法 9.1.1、11.8.4
- `CORBA createFile` 2.3.3
- 核心 Swing（顶层）12.1、12.4
- 12.4.2
  - `RowSetFactory` 的 `createFilteredRowSet` 方法 5.10
  - XPath 的 `count` 函数 3.5
  - `Stream` 的 `count` 方法 1.1、1.6、1.13
  - `Collectors` 的计数方法 1.9.4、1.13
- 国家代码 1.9.3、7.1.2
- `RowSetFactory` 的 CRC32 校验和 2.4.1、10.1
- `CRC32` 类 2.4
  - `RowSetFactory` 的 `CREATE TABLE` 5、10.1
  - `BorderFactory` 在批量更新中执行 5.4、5.9.3、11.8.4

## 异常（Exceptions）

- `FileNotFoundException` 4.3.3
- `IllegalStateException` 1.9.2、12.6.3
  - SQL 中的 5.4.3
- `IndexOutOfBoundsException` 12.6.3
- `InvalidObjectException` 2.6.7
- `InvalidPathException` 2.3.1
- `IOException` 2.1.2、4.1.2
- `MissingResourceException` 7.8.1
- `NotSerializable` 2.6.4
- `OverlappingFileLockException` 2.5
- `ParseException` 7.2.1
- `ReadOnlyBufferException` 2.4.1
- `SocketTimeoutException` 4.1.3
- `SQLException` 5.4.3、5.6.1、5.9.1
- `SQLWarning` 5.6.1
- `SyncProvider` 5.7
- `UnknownHostException` 4.1.2

- 排他锁 2.5
- `exclusiveOrMethod` 12.5.4
  - `Area` 的 12.7.5
  - 方法
  - `Runtime` 的 2.6.8
- `execute` 方法
  - `CachedRow` 的 5.7、5.10
  - `RowSet` 的 5.10
  - `Statement` 的 5.4.4、5.5.4、5.10
- `executeBatch` 5.9.3
  - `Statement` 的 5.10
- `executeLargeBatch`
  - `Statement` 的 5.10
- `executeLargeUpdate`
  - `Statement` 的 5.10
- `executeQuery` 方法
  - `PreparedStatement` 的 5.5.1、5.10
  - `Statement` 的 5.4.1、5.6.1、5.9.2、5.10
- `executeUpdate` 方法
  - `PreparedStatement` 的 5.5.1、5.10
- `executor` 方法
  - `HttpClient.Builder` 的 4.6
- `ExecutorService` 接口 8.1.2
- `exists` 方法
  - `Files` 的 2.3.5、2.7.7
- `EXIT` 5.3.3
- `exportNode` 方法
  - `Preferences` 的 10.5
- `exportSubtree` 方法
  - `Preferences` 的 10.5
- `Extension` 类 9.1.1
- 原生方法（C++）
- `FileFilter`（Swing）11.8.4
- `FileLock` 类 2.7.7
  - `getChannel` 方法 2.7.7
  - `read` 方法 2.1.1
- External 实体 3.4.1
- External padding 11.6.5
- Externalizable 方法的 2.6.5
- `fileKey` 方法
  - `BasicFileAttributes` 的 2.7.7
- `FileLock` 类 2.7.7
  - `close` 方法 2.7.7
  - `isShared` 2.5
- 因子算法 9.3.3
- `fatalError` 3.4.1
  - `ErrorHandler` 的 3.9
- `FileNameExtensionFilter` 11.8.4
  - 构造函数 11.8.4
- `FileNotFoundException` 类 4.3.3
- `FileOutputStream` 类 2.1.3、2.7.7
  - 构造函数 2.7.7
- `Field` 类
  - `getName`、`getTypes` 12.4.6
- 字段
  - 反序列化对象 2.6.6
  - `transient` 2.6.3、2.6.4
- `File` 类 2.7.7
  - `getChannel` 方法 2.7.7
- `Files` 类 2.13、2.3、2.7.2
  - 2.4.1 的通道
  - closing 2.3.6、2.3.8
- 配置 2.5
- 分隔符 2.1.3
- `toPath` 2.3.1、2.7.7
- 文件对话 11.8.4
- 辅助组件
  - `copy` 方法 2.3.4、2.3.9、2.7.7
- `copy` 2.3.4
- `createDirectories` 方法 2.7.7
- `createDirectory` 方法 2.7.7
- `createFile` 2.7.7
- 文件指针 2.2.2
- POSIX 兼容的文件系统 2.3.5
- `file.encoding` 路径 2.1.9
- `file` 方案 4.3.1
- `FileChannel` 类 2.7.7
  - `createSymbolicLink` 方法 2.7.7
  - `createTemp` 方法 2.7.7
- `createXXX` 方法 2.3.3
- 创建中 2.3.3
- `lock` 方法 2.5、2.7.7
- `map` 方法 2.4.1、2.7.7
- `open` 方法 2.4.1、2.7.7
- `truncate` 2.7.7
- `tryLock` 方法 2.5、2.7.7
- `delete` 方法 2.7.7
- `delete`、`deleteIfExists` 方法 2.3.4
- `deleteIfExists` 方法 2.7.7
- `FileFilter` 接口 11.8.4
- `FileFilter` 类 11.8.4
  - `accept` 方法 11.8.4
  - `getDescription` 方法 11.8.4
- 删除 2.3.4
- 9.4.3 中的加密数据
- `exists` 方法 2.3.5、2.7
- 逐字节字节 2.1.1
- 过滤 2.3.7、2.8、12.6.2
- `readSize` 2.3.2、2.7
- 11.8.4 的过滤器
- `size` 方法 2.3.5、2.7
- `find` 方法 2.3.6
- 2.2.2 中的总字节数
- `getOwner` 2.3.5
- 遍历 2.3.8
- 12.4 的层级结构
- `walk` 方法 2.3.6
- `isDirectory` 2.7.7
- `walkTree` 2.3.8、2.7.7

## `FocusListener` 接口

- `format` 方法 7.9
- 10.4.7
- `format` 方法
- `fold` 方法
- `of DateFormatter` 6.6、6.7
- `of Gatherers` 1.13
- 7.9
- Folders，图标用于 12.4.1、12.4.4
- `of Format` 7.9
- `followRedirect` 方法 4.4.1
- `of LocalDate` 7.3
- `of HttpClient.Builder` 4.6
- `of LocalTime` 7.3
- `Font` 类 10.3.3、10.5
- `of MessageFormat` 7.5、7.9
- 构造函数 10.5
- `of NumberFormat` 7.2.1、7.9
- `getFamily` method 10.5
- `of String` 7.1.4
- `getFunctionName` 10.5
- `of ZonedDateTime` 7.3
- `getLineMetrics` method 10.3.3
- 格式 10.5
- `dates` 7.1.1、7.3、7.3
- `getName` method 10.5
- `messages` 7.5
- `getStringBounds` method 10.3.3
- `numbers` 7.1.1、7.2、7.5.1
- 10.5
- Forms，处理 4.3.3
- Font 渲染器上下文 12.5.8
- `forName` 方法
- `FontMetrics` 类 10.5
- `of Charset` 2.1.8
- `getRenderContext`
- `of Class` 8.1.5
- 10.5
- `ForwardingFileManager` 类 8.2.6
- Fonts 10.3.3
- 检查可用性 10.3.3
- `ForwardingFileManager names of` 10.3.3
- method 8.2.6
- size of 10.3.3
- `getFileForOutput` 方法 8.2.6
- styles of 10.3.3
- 排版属性 of 10.3.3
- `ForwardingFileManager` 方法
- `forEach` 1.8
- `of ForwardingFileManager of Stream` 1.13
- 8.2.6
- `forOrdered` 方法 1.8
- `Frame` 类 10.2、10.5
- 前景颜色 10.3.2
- `getImageMethod` 10.5
- 回调函数
- `getTitle` 10.5
- 外接函数 13.7
- 外接函数 13.2
- 外接函数与内存 10.5
- 13
- `setResizable` 方法 10.2.2、10.5
- `Forest` 12.4、12.4.1
- `ForkJoinPool` 类
- `common` method 1.13
- Frames
- `forLanguage` tag 7.1.2
- 用户关闭 10.2.1
- `of Locale` 7.9
- 创建 10.2
- `Format` 类 6.7、7.9
- 在 10.3 中显示信息
- 定位 10.2.2
- properties of 10.2.2
- `GeneralPath` 类 12.5.2、12.5.3、12.7.5
- 构造函数 12.7.5
- `Generate` 1.12
- `generate` method of Stream 1.2、1.13
- `generateKey` method 9.4.2
- `of KeyGenerator` 9.4.4
- Generators，转换为流 1.13
- `FROM` 5.2
- `from` method of Instant 6.7
- `of ZonedDateTime` 6.7
- `FTP` 4.3.2
- `ftp:` scheme 4.3.1、4.3.2
- `Function` 接口
  - `identity` method 1.9.2
- `FunctionDescriptor` 接口 13.8.3
  - `of` method 13.8.3
  - `of oid` method 13.8.3
- 11.4.4 中的泛型编程类
- `GET` 4.3.3
- 构建 4.4.2
- `get` method of `AttributeSet` 12.7.5
- `of Bindings` 8.2.6
- `of ByteBuffer` 2.4.1、2.7.7
- `of CharBuffer` 2.7.7
- `of HttpRequest.Builder` 4.4.2
- Functions。参见 Methods

# G

- 哥德尔定理 9.1.5
- Gadget 链 2.6.8
- 垃圾回收原生方法和 13.1
- `gather` method of Stream 1.13
- `Gatherer` 接口 1.13
  - `initializer` method 1.13
  - `of` method 1.13
  - `of sequential` method 1.13
- `Gatherer.Downstream` 接口 1.13
  - `isRejecting` method 1.13
  - `push` method 1.13
- `Gatherer.Integrator` 接口 1.13
  - `integrate` method 1.13
  - `of` method 1.13
- `Gatherers` 类 11.13
  - `fold` method 1.13
  - `mapConcurrent` method 11.13
  - `windowFixed` method 1.13
- 4.6
- `of MemorySegment` 13.8.3
- `of Optional` 1.7.4、1.7.7、13
- `of Paths` 2.3.1
- `of Preferences` 10.5
- `of ScriptEngine` 8.2.6
- `of ScriptEngineManager` 8.2.6
- `of Supplier` 13
- `getActionCommand`
- `of ActionEvent` 10.4.7
- `of ButtonModel` 11.4.2、11.8.4
- `of KeyEvent` 10.4.7
- `getActionMap`
- `of Component` 10.5
- `getAddress` method 4.1.4
- `of InAddress` 4.6
- `getAdjustable`、`AdjustmentEvent` 10.4.7
- `getAdvance` method of Layout 12.7.5
- `getAllByName` method 4.1.4
- `of InAddress` 4.6
- `getAllChildren` method of TreeNode 12.7.5
- `getAncestorClass` 11.8.3
- `of SwingUtilities` 11.8.4
- `getAscent` method of LineMetrics 10.5
- `of TextLayout` 12.7.5
- `getAsXX` method of Optional 13
- `of OptionalLong` 13
- `of OptionalX` 12
- `getIndex` method of MemorySegment 13.8.3
- `getAttribute` 3.3
- `getAttributeCount` method of XMLStreamReader 3.9
- `getAttributeLocalName` method of XMLStreamReader 3.9
- `getAttributeName` method of XMLStreamReader 3.9
- `getAttributes` method of DocPrintJob 12.7.5
- `of Node` 3.3、3.9
- `of PrintService` 12.7.5
- `getAttributeValue` method of XMLStreamReader 3.9
- `of XMLStreamReader` 3.7.2
- `getAuthority` method 4.3.1
- `getAutoCommit` method 5.9
- `getAutoCreateSorter` method of Table 12.7.5
- `getAvailableCurrencies` method of Currency 7.9
- `getAvailableFontNames` method of GraphicsEnvironment 10.3.3
- `getAvailableLocales` method of Collator 7.9
- `getAvailableIds` method of NumberFormat 7.1.2、7.2.1、7.9
- `getAverage` method of ZoneId 6.5
- `of DoubleSummaryStatistics` 13
- `of IntSummaryStatistics` 13
- `of LongSummaryStatistics` 13
- `getBackground` method of Component 10.5
- `getBinarySearch` method 5.5.2
- `getBlob` method of ResultSet 5.5.2、5.10
- `getBlockSize` method of Cipher 9.4.4
- `getBoolean` method of Preferences 10.5
- `getBundle` method 7.8.1
- `of ResourceBundle` 7.9
- `getByName` method 4.1.4
- `of InAddress` 4.6
- `getByteArray` method 10.5
- `getBytes` method 5.5.2
- `of Blob` 5.10
- `getCandidateLocales` method of ResourceBundle.Control 7.8.1
- `getCategory` method 12.7.5
- `of Attribute` 12.7.5
- `getEditorValue` method 12.3.3、12.3.4
- `of CellEditor` 12.7.5
- `getCellRenderer` 12.3.1
- `getCellSelectionEnabled` method of JTable 12.7.5
- `getCenterX` method of RectangularShape 10.5
- `getColumnCount` method of ResultSetMetaData 5.8、5.10
- `of RectangularShape` 10.3.1
- `of TableModel` 12.1.2、12.7.5
- `getCenterY` method
- `getColumnSize` method of RectangularShape 10.5
- `of ResultSetMetaData` 5.10
- `getChannel` method of ColumnLabel method of InputStream 2.7
- `of OutputStream` 2.7
- `of ColumnModel` 12.2.2
- `of RandomAccess` 2.7
- `of JTable` 12.7
- `getChar` method 2.4
- `getColumnName` method 12.1
- `getCharacterStream` method 5.5.2
- `of ResultSetMetaData` 5.10
- `of Clob` 5.10
- `of TableModel` 12.7
- `getCharContent` method
- `getFieldNumber` method of SimpleFileObject 8.6
- `of Diagnostic` 8.2
- `getChild` method 12.4.6
- `of SAXParseException` 3.9
- `of TreeModel` 12.7.5
- `getChildId` method of JTextField 11.8
- `of TreeNode` 12.7.5
- `getSelectionAllowed` method
- `getChildCount` method of JTable 12.7
- `of TreeModel` 12.4.6、12.7.5
- `getColumnType` 12.3.3 of TreeNode 12.7.5
- `getChildNodes` method 3.3 of ResultSetMetaData 5.8
- `of Node` 3.9
- `getCommand` method of RowSet 5.1
- `getClassLoader` method 9.1.1
- `of Class` 9.4.4
- `getNumberInstance` method
- `getCount` method 10.4.6、10.4.7
- `getComponentPopupMenu` method of MouseEvent 10.5
- `of JComponent` 11.8
- `getClip` method 12.7.1
- `getcurrency` method 5.6.1、5.6.2
- `of Graphics` 12.7.5
- `of ResultSet` 5.10
- `getBlob` method
- `get` method 5.3.4
- `of ResultSet` 5.10

## Java Bug 数据库 12.6.5

- Java Development Kit（JDK）文档 10.4.5，10.3.3 随附字体
- Java EE 5.1.2，Java 视图与外观 10.4.5
- Java Native Interface 13，Java 插件，日志签名代码 9.3.7
- Java 虚拟机规范 9.1.5
- `java.awt.geom` 包 2.6.4
- `java.base` 包 9.1.1
- `java.datatransfer` 9.1.1
- `java.desktop` 包 9.1.1
- `java.instrument` 包 9.1.1
- `java.io` 包 2.1.8
- `java.logging` 包 9.1.1
- `java.management` 包 9.1.1
- `java.management.rmi` 包 9.1.1
- `java.naming` 包 9.1.1
- `java.net` 包 4.1.2，支持 IPv6 地址的套接连接 4.1.4，4.3.1 URL 对 URIs
- `java.net.http` 包 4.4
- `java.nio` 包 4.2.4，2.4.1 中的内存映射
- `java.prefs` 包 9.1.1
- `java.rmi` 包 9.1.1
- `java.security` 包 9.3
- `java.security.sasl` 包 9.1.1
- `java.sql` 包 6.7
- `java.time` 包 7.3
- `java.xml` 包 9.1.1
- JavaBeans 11.8.4
- Javac 字节顺序标记 7.7.4，向 8.1.1 传递参数
- `JavaCompiler` 接口 8.2.6，`getStandardFileManager` 方法 8.2.6
- `getTask` 方法 8.1.2、8.2.6
- `JavaCompiler.CompilationTask` 接口 8.2.6，`call` 方法 8.2.6
- `JavaObject` 接口 8.1.2
- JavaFX 10.1
- JavaScript 8.2、8.2.6
- `javax.imageio` 包 12.6.1
- `java.sql.rowset` 包 5.7.1
- `java.swing` 包 10.2.1
- `java.xml.catalog.files` 属性 3.4.1
- JAXP（Java XML 处理 API）3.3
- JAXP（Java XML 处理 API）库 9.1.2
- `JButton` 10.4.2、10.4.5，构造函数 10.5，默认按钮 11.8.4
- `JCheckBox` 类 11.4.1、11.8.4，构造函数 11.8.4，`isSelectedMethod` 11.4.1
- `JCheckBoxItem` 11.5.3、11.8.4
- `JComboBox` 10.4.7、11.4.4、11.8.4、12.3.3
  - `addItem` 11.4.4、11.8.4
  - `getSelectedItemItem` 11.4.4、11.8.4
  - `insertItem` 方法 11.4.4、11.8.4
  - `isEditable` 方法 11.8.4
  - `removeAllItems` 方法 11.8.4
  - `removeAllItems` 11.4.4、11.8.4
  - `removeItemAt` 方法 11.8.4
  - `setModel` 11.4.4
- `Component` 类 10.3、10.5、11.8.4、12.7.5
- 调试 5.3
- 5.1 设计
- 5.1.1 规范
- 跟踪 5.3.4
- 5.1.2 使用
- JDBC API 教程与参考（et al.）5.6.2、5.9.4，JAR 文件 5.3.2
- 5.3.4 注册
- 可滚动/可更新结果 5.6.1
- 5.1.1 类型
- JDBC/ODBC 桥接 5.1.1
- `JdbcRowSet` 接口 5.7.1
- `Dialog` 类 11.8.2、11.8.4
  - `setDefaultCloseOperation` 方法 11.8.2
  - `setVisible` 方法 11.8.2、11.8.3
- `Dialog` 方法 11.8.4
- action maps 10.4.5
- `getSetComponentPopupMenu` 方法 11.5.4
- `getSetInheritsPopupMenu` 方法 11.5.4
- `getComponentPopupMenu` 方法 11.8.4
- `getMetrics` 方法 10.3.3、10.5
- `getInheritsPopupMenu` 方法 11.8.4
- `getInputMap` 方法 10.4.5、10.5
- `getRootPane` 方法 11.8.3、11.8.4
- input maps 10.4.5
- `paint` 方法 12.3.1、12.5.1
- `paintComponent` 方法 10.3、10.3.3、10.4、12.5.1-12.7
- `putClientProperty` 方法 12.4.1、12.7.5
- `revalidate` 方法 11.3.1、11.8.4
- `setBorder` 方法 11.4.3、11.8.4
- `setComponentPopupMenu` 方法 11.8.4
- `setFont` 方法 11.8.4
- `setInheritsPopupMenu` 方法 11.8.4
- `setToolTip` 方法 11.8.4
- JDBC 5、5.10
- DOM 解析器 3.3
- `keytool` 程序 9.3.4
- serial ver 2.6.7
- SunJCE 算法 9.4.1
- `jdk.jdbc.http` 包 4.4
- `EditorPane` 类 11.3.5
- `JEP 290, 415` 2.6.8
- 提取工具 13.6
- `FileChooser` 类 11.8.4
  - `addChooserFilter` 方法 11.8.4
  - 构造函数 11.8.4
  - `getSelectedFile` 方法 11.8.4
  - `getSelectedFile/Files` 方法 11.8.4
  - `getSelectedFiles` 方法 11.8.4
  - `insert` 方法 11.8.4
  - `resetChoosableFileFilters` 11.8.4
  - `insertSeparator` 方法 11.8.4
  - `remove` 方法 11.8.4
- `JMenuBar` 类 11.5.1
- `setAcceptAllFilterUsed` `JMenuItem` 类 11.8.4
- 方法 11.8.4，构造函数 11.8.4
- `setAccessory` 方法
- `setAccelerator` 方法 11.5.5、11.8.4
- `setCurrentDirectory` 方法
- `setEnabled` 方法 11.5.6、11.8.4
- `setIcon` 方法 11.5.2
- `setFilter` 方法 11.8.4
- JMOD 文件 9.1.1
- `setSelectionMode` 方法 JNI 服务 5.10、9.122
- `diLoginModule` 9.2.1
- `setViewMethod` 11.8.4
- `setMultiSelectionEnabled` JNI ALL、JNI EXPORT 13
- JobAttributes（已弃）。Joining 12.5.5
- `getSelectedFile/Files` 方法 11.8.4
- `setSelectedFiles` 方法 11.8.4
- Collectors
- 5.1.1
- `JOptionPane` 类 10.3、11.8.4
  - `showOpenDialog` 方法 11.8.4
  - `showSaveDialog` 方法 11.8.4
- 5.1.1
- `Dialog` 类 11.8.2、11.4
  - `showConfirmDialog` 方法 11.8.4
  - `showInputDialog` 方法 11.8.4
  - `showOptionDialog` 方法 11.8.4
  - `showMessageDialog` 方法 11.8.4
  - `showInternalDialog` 方法 11.8.4
- `JLabel` 类 10.3、11.8.4
  - `getText` 方法 11.8.4
  - `setText` 方法 11.8.4
- `JPanel` 类 11.4、11.8
- `JMenu` 类 11.5.4
- 11.8.4

## `JTextArea` 类 11.3.4、11.8.4

- `append` method 11.8.4
- 构造函数 11.8.4
- `setColumns` method 11.8.4
- `setColumns`、`setRows` methods 11.3.4
- `setLineWrap` method 11.3.4、11.8.4
- `setRows` method 11.8.4
- `setTabSize` method 11.8.4
- `setWrapStyleMethod` 11.8.4

## `JComponent`

- `getType` method 11.3.1
- `setText` method 11.3.1

## `JComponent` 类 11.8.4

- `getType` method 11.8.4
- `isEditable` method 11.8.4
- `setEditable` method 11.8.4
- `setText` method 11.8.4

## `JTreeField` 类 10.4.7、11.3、11.8.4、12.3.3

- 构造函数 11.8.4
- `getColumns` method 11.8.4
- `setColumns` method 11.3.1、11.8.4

## `JToolBar` 类 11.5.7、11.8.4

- `add` method 11.8.4
- `add`、`addSeparator` methods 11.5.7
- `addSeparator` method 11.8.4
- 构造函数 11.8.4

## `JTree` 类 12.4、12.7.5

- `addTreeSelectionListener` method 12.4.5
- 构造函数 12.4.1、12.7.5
- `getLastSelectedPathComponent` method 12.4.2、12.7.5
- `getSelectionPath` method 12.4.2、12.7.5
- `getSelectionPaths` method 12.4.5、12.7.5
- 识别节点 12.4.2
- `makeVisible` method 12.4.2、12.7.5
- `scrollPathToVisible` method 12.4.2、12.7.5
- `setEditable` method 12.4.2
- `setRootVisible` method 12.4.1、12.7.5
- `setShowsRootHandles` method 12.4.1、12.7.5

## JVM

- 9.1 中的类文件
- 9.1.1 中的类加载器
- 9.1.5 的规范

## Kerberos 协议 9.2.1

## `Kernel` 类 12.6.5、12.7.5

- 构造函数 12.7.5
- 卷积的 `Kernel` 12.6.5

## Keyboard

- 与操作关联 10.4.5
- `lastDayOfYear` method
- 10.4.5 的焦点
- `TemporalAdjusters` 的 6.7
- 11.5.5 的记忆键
- `lastInMonth` method
- 从 2.1.1 读取 Keyboard
- `TemporalAdjusters` 的 6.7

## `KeyEvent` 类 10.4.7

- `lastModifiedTime` method
- `BasicFileAttributes` 的 `getKeyCode`、`isActionKey` methods 2.7.7、10.4.7

## 布局算法 12.7.2

## 布局管理 11.2

## `KeyGenerator` 类 9.4.2、9.4.4

- `generateKey` 9.4.2、9.4.4
- border 11.2.2
- `getInstance` method 9.4.4
- box 11.6
- `init` method 9.4.4
- custom 11.7

## `KeyListener` 接口，keyCodes

- flow 11.2.1
- methods 10.4.7
- grid 11.2.3
- grid bag 11.6
- `KeyPairGenerator` 9.4.4
- `Preferences` 10.5 组 11.6 的 `keys` method，复杂的 spring 11.6

## `KeyStoreExceptionModule` 9.2.1

## Keystores 9.3.4

## `LayoutManager` 的 `LayoutContainer` 11.8.4

`LayoutManager` 接口 11.8.4

## `KeyStroke` 类 10.5

- `getKeyStroke` 10.5
- `KeyStroke` 类，`getKeyStroke`
- `addLayoutComponent` method 10.4.5
- 设计自定义 11.7
- `LayoutContainer` 11.8.4
- `minimumLayoutSize` method
- `KeyTool` 9.3.4
- `LoginModule` 9.2.1
- `preferredLayoutSize` method 11.8.4
- 组件的标签 11.3.2
- 滑块刻度 11.4.5
- `Layout2` 接口 11.7
- 事件监听器 10.4.3
- 横向 12.5.7
- `LD_LIBRARY_PATH` 13.1
- 语言代码 1.9、7.1.2
- Leading 10.3.3
- 闰秒 6.1
- `ResultSet` 5.6、5.10
- 闰年 6.2
- `BasicFileAttributes` 的 `lastAccessTime` method 2.7.7
- 学习 SQL The Hard Way
- 学习 SQL（Bean）
- 叶子 12.4、12.4.1
- `Layouts` method 12.4.4
- legacy APIs 2.3.1、6.7
- 将遗留数据转换为 XML 3.9
- legacy 类 6.7
- `LayoutState` 13.8.3
- Linux 5.2
- Library 13.1
- `CharSequence` 2.7.7
- `Clob` 5.10
- `RandomAccess` 2.2.2、2.7.7
- `lib/ext` 9.1.1
- library path 13.1
- `limit` method
- `List` method
- List-menu 11.5.4
- Line feed 2.1.6、7.7.2
- Listener interfaces 10.4.1
- Listener objects 10.4.1
- List-mails 4.6
- `ListBundle` 7.8.3
- Lists, to streams 13
- `List2class` 10.3、12.5.2
- `ListSelectionModel` 12.2.5、12.5.2
- `Line2.Double` 10.5
- `Line2.Double`、`Line2D.Float` classes
- `LineBorder` 11.4、11.8.4
- `LineBorder` method 11.8.4
- Little-endian order 2.1.8、2.2.1、2.4.1、7.7.4

## `LoadClass` of `ClassLoader` 9.1.2、9.1.4

- `URLClassLoader` 9.1.2

## `LineMetrics` 10.3、10.5

- `getAscent` method 10.5
- `getDescent` method 10.5
- `loadLibrary` method 13.1
- `getHeight` method 10.5
- `getLeading` method 13.8.3
- Lines 10.3.1
- placing in database 5.5.2
- constructing 10.3.1
- reading 5.5.2
- Lines method
- Local hosts 4.1.4
- Local names 3.6
- `String` 1.2、11.13、2.3.2
- `LocalDate` 类 6.7、7.9
  - `lineTo` method 12.5.3
  - `datesUntil` 6.2、6.7
- `Path2D.Float` 12.7.5
- `format` method 7.3
- `Linker` interface 13.2、13.6、13.8
- `getDayOfMonth` method 7.9
- `getDayOfWeek` method 6.7
- `getDayOfXX` methods 6.2
- `getDayOfYear` method 6.7
- `getMonth` method 6.7
- `getMonthValue` method 6.7
- `getYear` method 6.7
- `isAfter` method 6.7
- `isBefore` method 6.7
- `isLeapYear` method 6.7
- legacy classes and 6.7
- `minus` method 6.2
- `minus`、`minusXxx` methods 6.4
- `now` method 6.4、6.7
- `MAX_VALUE` constant 2.5
- `of` method 6.4、6.7
- `LONG VARCHAR` 5.9.4
- `parse` method 7.3、7.9
- long type
- `plus` method 6.7
- `plus`、`plusXX` methods 6.4
- streams of 1.12
- `toLocalTime` method 6.7
- type for 2.6.2
- `toNanoOfDay` method 6.7
- writing in binary format 2.2.1
- `secondOfOfDay` method 6.7
- `LONG VARCHAR` 5.9.4
- `LongBuffer` 类 2.4.2
- `lock` method methods method of of `FileChannel` 2.5、2.7
- Locks 2.5
- `ofRandomGenerator` 1.13
- for the tail portion of a file 2.5
- `LongStream` 接口 11.2、11.2
- shared 2.5
- average 11.2、11.13
- boxed 11.2、11.13
- logging.properties file 4.4
- `mapToTop` 11.2
- `login` method 9.4.4
- max 11.2
- `of LoginContext` 9.4.4
- max、min methods 11.2
- `of LoginModule` 9.4.4
- min 13

## `Maps`（映射）

- `Stream` 1.13 的 `lookingAt` 方法
- `Matcher` 2.7.7 的 `lookingAt` 方法
- `mapping` 方法
- `Collectors` 1.9.4、1.13 的 `lookup` 方法
- `MethodHandles` 13.8.3 的
- `Lookupop` 类 12.6.5、12.7.5
- concurrent 1.9.2
- stream elements 1.9.2、1.13 的构造函数 12.7.5
- `lookupPrintServices` 方法
- `mapToInt` 方法 1.10、12.7.3
- `PrintServiceLookup` 12.7.5 的 `mapToXxx` 方法
- `XxxStream` 12.12 的
- `s` 方法
- `PrintServiceFactory` 的 `mark` 方法
- `Buffer` 2.4.2、2.7.7、12.7.5 的
- `Input` 2.7.7 的
- `LookupTable` 12.6.5
- `markSupported` 方法

## 低层事件 10.4.7

## 精通正则表达式（Friedl）

- LSB（最低有效字节）2.2.1、2.7.1
- `LOutput` 3.8.3
- `match`（XSLT）3.9
- `LSerializer` 3.8.3
- `Matcher` 类 2.7.7
- `writeToString` 方法 3.8.3
- `find` 方法 2.7.7
- `hasMatch` 2.7.7

# M

## Mac OS X

- `lookingAt` 2.7.7
- 字符编码 7.7
- `matches` 方法 2.7.7
- 7.8 中的资源
- `Pattern` 2.7.2、2.7.7 的
- Mac Roman 7.7
- `quoteReplacement` 方法 2.7.7
- `replaceAll` 方法 2.7.6、2.7.7
- `main` 方法 9.1.1
- `replaceFirst` 方法 2.7.6、2.7.7
- `makeShape` 12.5.3
- `results` 方法 2.7.7
- `makeVisible` 12.4.2
- `JTree` 12.7.5 的 `matcher` 方法
- `Pattern` 2.7.2、2.7.7 的
- Mandelbrot 集合 12.6.4
- `Matcher` 2.7.7 的 `methods` 方法
- 命名混淆（Mangling names）13.1
- 清单文件 2.2.3
- `PathMatcher` 2.7.7、2.7.7 的
- `Pattern` 2.7.2 的 `map` 方法
- `FileChannel` 2.4.1、2.7.7 的
- `MatchResult` 接口 2.7.3、2.7.7
- `HttpHeaders` 4.4.3、4.6 的
- `Optional` 1.7.3、1.13 的 `end` 方法 2.7.7
- `Stream` 1.3、1.13 的 `group` 方法 2.7.7
- `namedGroups` 方法 2.7.7
- `Gatherers` 1.13 的 `mapConcurrent` 方法
- `start` 方法 2.7.7

## Matisse 11.6

## 矩阵、变换 12.5.7

- 原始流 11.12 的 `mapMulti` 方法
- `DoubleStream` 1.13 的 `max` 方法，`IntStream` 1.13 的 `max`
- `reinterpret` 方法 13.8.3
- `set` 方法 13.8.3
- `setAtIndex` 方法 13.8.3
- `LongStream` 11.13、`Stream` 1.6、1.13 的 `toArray` 方法 13.8.3
- `OfListener` 11.8.4 的 `menuCancelled` 方法
- `MAX_VALUE` 2.5
- `Collectors` 1.13 的 `maxByMethod` 1.9.4
- `MenuListener` 11.8.4 的 `menuDelected` 方法 11.8.4
- `maxoccurs` 属性（XSLT）3.4.2
- DS 9.3.1
- `MenuListener` 接口 11.5.6、11.8.4
- 内存地址对比序列号 2.6.1
- `menuCancelled` 方法 11.8.4
- `menuSelected` 方法 11.8.4
- `menuXX` 方法 11.5.6
- `native` 13
- `native` 131
- `native code` 13
- `MissingResource` class
- `mismatch` method
- Modernist painting 3.8.4
- Modernist painting example 3.8.4
- multiple views 11.1
- Model-view 11.1
- Modules 4.6
- Memory 11.5
- Menus 11.5
- checkboxes 11.5.3
- 11.5.2 中的图标
- 11.5.5 的键盘记忆键
- menu bar 11.5、11.5
- menu items 11.5
- enabling/disabled 11.5.6
- pop-up 11.5.4
- radio buttons 11.5.3
- submenus 11.5、11.5
- `MenuListener` 11.8.4
- `MessageDigest` class 9.4.4
- `MemoryLayout.PathElement` interface 13.8.3
- `MemorySegment` 13.4
- `MessageFormat` 7.5、7.9
- `MessageLayout` 13.8.3
- `MessageListener` 11.8.4
- `MessageSegment` interface 13.8.3
- MIME 12.6.2
- `MimeMessage` class
- `Month` enumeration 6.2
- `MonthDay` 6.2
- Mouse events 10.4.6
- `MouseAdapter` 10.4.6
- `MouseHandler` 10.4.6
- `MouseListener` interface 10.4.6
- `MouseEvent` class 10.4.7、10.5、11.8.4

## 无参数构造函数 2.6.1、2.6.8

- 12.4.2 的行位置
- 搜索 12.4.3、12.4.5
- 选择 12.4.5

## `Node` 接口 `appendChild` 3.9

### 方法 3.8、3.9

- 3.8、3.9
- `getAttributes` 3.3、3.9
- `getChildNodes` 3.3、3.9
- `getFirstChild` 3.3、3.9
- `getChildMethod` 3.3、3.9
- `getLocalName` 3.6、3.9
- `getNamespaceURI` 3.6、3.9
- `getNextSibling` 3.3、3.9
- `getNodeName` 3.9
- `getNode` 3.9
- `getNextXxx` 3.3、3.6
- 12.4.1、12.4.2、12.4.3、12.4.5 的用户对象
- `nodesChanged`
- `of DefaultTreeModel` 12.7.5
- 非确定性解析 3.4.1
- `noneMatch` 方法 1.6
- `of Stream` 1.13
- 非干扰性，of stream 1.2
- 规范化 7.4
- `normalize` 方法
- `getParentNode` 3.9
- `getPreviousSibling` 3.3
- 3.3 的子接口
- `of Normalizer` 7.9 方法
- `of Path` 2.3.1、2.7.7
- 归一化颜色值 12.6.4
- `Normalizer` 7.4、7.9
- `normalize` 方法 7.9
- `of Preferences` 10.5
- `changed` 12.4.2
- `of DefaultTreeModel` 12.7.5
- `Nodelist` 3.3、3.9
  - `getLength` 3.3、3.9
  - `item` 方法 3.3、3.4.1、3.9
- `NoSuchElementException` 类 1.7.4
- `notFilter` 方法 12.2.7
- `of RowFilter` 12.7.5
- `NotSerializableException` 类 2.6.4
- adding 12.4.2
- child 12.4.4、12.4.1
- collapsed 12.4.2
- 12.4.1 的连接线
- 当前选中的 12.4.2
- editing 12.4.2、12.4.3
- enumerating 12.4.2
- 12.4.1、12.4.4 的句柄
- highlighting 12.4.4
- 通过树路径识别 12.4.2
- 使可见 12.4.2
- parent 12.4、12.4.1
- removing 12.4.2
- rendering 12.4.1、12.4.4
- root 12.4、12.4.1
- `of Instant` 6.1、6.7 的 `now` 方法
- `of LocalDate` 6.2、6.7
- `of LocalTime` 6.4、6.7
- `of ZonedDateTime` 6.7
- `NTLogInputModule` 9.2.1
- `of InputStream` 2.7.7 的 `nullInputStream` 方法
- `of OutputStream` 2.7.7 的 `nullOutputStream` 方法
- `NullPointerException` 类对比 Optional 1.6
- `Number` 类
  - `doubleValue` 方法 7.2.1
  - `intValue` 方法 7.2.1
- `numberFilter` 方法 12.2.7
- `of RowFilter` 12.7.5
- 在正则表达式中 2.7.1
- `NumberFormat` 类 7.2、7.9
  - printing 2.1.6
  - `format` 方法 7.2.1、7.9
  - random 1.2、1.4、1.12、9.4.2
  - `getAvailableLocale` reading 7.1.2、7.2.1、7.9
  - 来自文件 2.1.3
  - 从 ZIP 归档获取 `getCompactNumberInstance` 2.1.3
  - 7.9 使用 locales 7.2.1
  - 存储在内存中的 `getCurrencyInstance` 2.2.1
  - 7.2.1、7.2.3、7.9
  - 以二进制格式写入 2.2.1
  - `getMaximumFractionDigits` NUMERIC 5.2、5.9.4
  - 7.9 `NVARCHAR` 5.9.4

## `Object` 类

- `clone` 方法 2.6.1、2.6.9
- 对象内省树 12.4.6
- 对象序列化 2.6
- 使用 2.6.9 克隆
- 2.6.2 的文件格式
- 2.6.1 的序列号
- `ObjectInputStream` 类 2.6.1、2.7.7
  - 构造函数 2.7.7
  - `readObject` 方法 2.6.1、2.6.4、2.7.7
- `ObjectInputValidation` 接口 2.6.8
- `ObjectOutputStream` 类 2.6.1、2.7.7
  - 构造函数 2.7.7
  - `defaultWrite` 方法 2.6.4
  - `writeObject` 方法 2.6.1、2.6.4、2.7.7
- `getMaximumIntegerDigits` 7.9
- `getMinimumFractionDigits` 7.9
- `getMinimumIntegerDigits` 7.9
- `getNumber` 方法 7.2.1、7.9
- `getPercentInstance` 7.2.1、7.9
- `isGroupingUsed` 7.9
- `isParseIntegerOnly` 7.9
- `parse` 方法 7.2.1、7.9
- `setCurrency` 方法 7.2.3
- `setGrouping` 方法 7.9
- `setMaximumFractionDigits` 7.9
- `setMinimumIntegerDigits` 7.9
- `setMinimumFractionDigits` 7.9
- `setParseIntegerOnly` 方法 7.9
- Numbers 12.2.7
  - floating-point 7.1.1、7.2
  - formatting 7.1.1、7.2、7.5
  - supported locales for 7.2.1
  - grouped elements 1.9.4
  - cloning 2.6.9
  - converting to streams 1.2、7.7
  - deserialized 2.6.6
  - fingerprints 2.6.2
  - printing 2.1.6
  - reading from an input stream 2.6.1
  - in output streams 2.6.1
  - in text format 2.1.7
  - serializable 2.6.1
  - transmitting over network 2.6.1
  - type 2.6.2
  - versioning 2.6.7

## `P`

- `Paper` 类
- `pack` method
- margins of 12.7.1
- `of Window` 10.3、10.5
- sizes of 7.8.3、12.7.1

## Packages

- `parallel` method
- avoiding name clashes with 9.1.3
- `of BaseStream` 1.13
- Packets 4.1.2
- `parallelStream` 1.1、1.3
- Padding she 9.4.1
- `of Collection` 1.13
- `PaddingLayout` 接口 13.5
- `ParameterMetaData` 接口 5.10
- Page setup dialog box 12.7.1
- `getParameterClassName` 5.10
- `Pageable` 接口
- `getParameterCount` 5.10
- implementing 12.7.2
- `getParameterMode` 5.10
- objects, printing 12.7.3
- `getParameterType` 5.10
- `PageAttributes` 类（obsolete）
- `getParameterTypeName` 5.10
- 12.7.5
- `pageDialog` method 12.7.1
- `getPrecision` method 5.10
- `of PrinterJob` 12.7.5
- `setScale` method 5.10
- `PageFormat` 类 12.7.5
- 父类。见超类
- `getHeight` method 12.7.1、12.7.5
- 父节点 12.4、12.4.1

## 领先语言

面面今日的技术趋势：`www.oracle.com/java`

## 在 OCI 上构建、测试和部署应用程序——完全免费

下一代云，旨在以更快速、更安全、更低成本运行任何应用程序。

了解更多客户选择 OCI 的原因并进行免费尝试：`oracle.com/free`

## Oracle 骨文基础设施

学习。  
启动。

勾选此框以接收我们的消息并获取新版本的独家优惠。

充分利用我们的特别优惠和促销活动（`informit.com/promotions`）。

## 入门指南

获取技术文档的解答。

在 Oracle Help 查找入门指南、教程、架构等。

Oracle 文档。

## 骨文

告别复杂性。  
你好，简单性。

使用适用于所有工作负载的数据库降低复杂性和成本。Oracle Database 是云原生、融合且自动化的，消除了手动维护，并提供性能、安全性和自动扩展。

在云端或本地获取简单性。

Oracle Database

访问 `oracle.com/autonomous-database` 获取更多信息。

## 骨文

### Beta 测试软件

首眼预览 Oracle 最新产品、功能和云服务——并帮助完善它们！与 Oracle 开发团队紧密合作，分享您的反馈和建议。

要查看并申请参加 Beta，请访问 Oracle Beta 测试网站：<https://pdpm.oracle.com/pls/apex/f?p=102:250>

## 在 informit.com 注册您的产品

获取额外福利并在下次购买时节省高达 65%*。

- 自动接收书籍、eBooks 和网络版的 6 折优惠券，以及视频课程的 35 折优惠券，有效期为 30 天。在您的 InformIT 购物车或账户页面的“管理代码”部分查找您的代码。
- 下载可用的产品更新。
- 如果可用，可访问赠送材料。*
- 勾选此框以接收我们的消息并获取新版本产品的独家优惠。

Informit 是值得信赖的技术学习源，也是全球领先学习公司 Pearson 旗下信息技术品牌的在线家园。在 `informit.com`，您可以购买我们的书籍、eBooks 和视频培训。大多数电子书均无 DRM 限制，并包含 PDF 和 EPUB 文件。

- 充分利用我们的特别优惠和促销活动（`informit.com/promotions`）。
- 订阅特别优惠和内容通讯（`informit.com/newsletters`）。
- 访问数千个免费章节和视频课程。
- 美国订单享受免费陆运运。*

优惠可能会变动。

**** 注册福利随产品而异。福利将列在您的账户页“已注册产品”下。

与 Informit 建立——访问 `informit.com/community`
