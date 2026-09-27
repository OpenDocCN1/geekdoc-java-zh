
# Java 开发者 Java 入门指南

在我们的 Telegram 频道获取更多 Java 书籍：https://t.me/javalib

![](img/12066447fb3262172bd10949450d978a_1_0.png)

![](img/12066447fb3262172bd10949450d978a_3_0.png)

O. Campesato. 面向开发者的 JAVA 口袋版指南。

我想将这本书献给我的父母，给他们的生活带来快乐。

![](img/12066447fb3262172bd10949450d978a_6_0.png)

序言 xiii

本章总结 87

整数数字相加

通过递归反转字符串

Java 方法重载

- 总结 180

在我们的 Telegram 频道获取更多 Java 书籍：https://t.me/javalib

## 前言

### 目标是什么？

本书的目标是为对 Java 编程语言较新的人提供相当详尽的 Java 开发介绍。对于这种长度的书来说，最大的挑战是充分涵盖 Java 的一些基本方面，而这些方面主要通过 Java 8 的代码示例进行说明。在本书出版时，Java 17 已经是正式发布版本。如果你计划编写 Java 应用程序，你需要确定包含你应用程序所需功能的 Java 版本，然后你就可以确定需要安装的版本了。

### 为什么关注 JAVA？

问得好！如果你使用现代浏览器，你可能了解过“浏览器大战”，以及同一浏览器不同版本之间出现的不兼容性问题（以及当问题版本被停用时的如释负负）。

幸运的是，Java 不同版本之间的情况要好得多（不满意的主要来源是专有版本）。

### 代码示例使用的开发栈是什么？

书中的代码示例是在运行 OS X 10.10 (Mavericks) 的 MacBook Pro 上使用 Java 13 的早期发布版本开发的。

### 为什么有这么多短代码示例？

本书是为 Java 开发初学者编写的。代码示例旨在帮助你理解各种 Java 接口，这就是为什么每个代码示例的长度最多只有两页（通常少于一页）。重点是提供你可能在 Java 应用程序中需要的 Java 特性代码。较短的代码示例意味着本书可以包含更多的 Java API。

### 目录是如何确定的？

决策过程尽可能客观，涉及了几个标准。第一个标准是包含 Java 应用中常见的“必会”概念。第二个标准是包含对 Java 初学者有益的“有上添锦”的功能。第三个标准涉及对于想要编写“严肃” Java 应用程序的人可能有用且相关的 Java API。

此类 API 的示例包括社交连接（Facebook 和 Twitter）。第四个标准涉及书中 Java 应用程序所需要的 Java API。

### 哪些 Java 主题被排除了？为什么？

不符合上一节所列出的任何标准的 Java 特性均未包含在书中。因此，书中没有涵盖 `Java Native Interface (JNI)`，它允许 Java 调用 C/C++ 函数。此外，书中未涵盖 AWT、Java Swing、JavaFX、Java Servlets、JSPs、JAXB、JAXP、JAXR、JEE 和 Java Security。不过，你可以在许多在线博客文章中找到这些主题的内容。

### 读完这本书后我应该读什么？

这个问题的答案差异很大，主要因为答案在很大程度上取决于你的目标。具体来说，你需要决定准备好投入多少精力来进一步提高你的知识。在你的技术专业知识方面取得重大进展所需的时间也取决于你目前的技术知识水平和经验。例如，经理、学生和专业 Java 开发人员（以及其他）的需求显然是不同的。

考虑到上述几点，建议包括：1) 向朋友和同事寻求建议和指导；2) 确定基于 Java 项目（个人或工作相关）的主要特性；3) 进行互联网搜索并花一些时间评估其他可用资源。

![](img/12066447fb3262172bd10949450d978a_18_0.png)

# 第 1 章

## Java 简介

本章介绍了 Java 的基本特性，以及说明这些特性的代码示例。在许多情况下，随附的 Java 代码示例是简洁的，特别是当代码目的直观易懂时。本书的文件包含了额外的代码示例，用于说明本章中未涵盖的其他 Java 特性。

本章的第一部分对 Java 进行了非常短的介绍，并提供了一个将 Java 下载到你的机器的链接。你还将学习 Java 数据类型、运算符以及它们的优先级。

第二部分展示了如何从命令行创建、编译和启动 Java 类。你将学习如何创建一个“Hello World”代码示例，以及如何在 Java 中处理数字、随机数和三角函数。

第三部分涵盖了 Java 字符和字符串，以及 `new` 运算符的作用。你还将学习如何判断两个字符串是否相等，以及 Java 中的一些其他与字符串相关的函数。

请注意，有时你会看到对某个 Java 类的引用，但在章中没有完全解释。例如，列表 1.17 包含一个自动装箱示例，它调用了 `ArrayList` 类，但没有对该类进行解释。然而，这种情况很少发生，你可以通过在线文档找到更多细节。

另一个细节是：本章最后的代码示例被标记为“可选”，因为你可以跳过它们直接进入第 2 章，而不会影响连贯性。之所以包含它们，以防你渴望看到超出本章其他代码示例所插图的基础概念的代码示例。

### Java 简要介绍

Java 是一种面向对象的编程语言，它允许你在许多不同的硬件平台上运行代码，包括台式电脑、移动设备和树莓派。

你需要为每个打算运行 Java 代码的平台安装特定平台的 Java 发行版（详细信息见下一节）。尽管 Java 17 是 Java 的当前生产版本，但较早版本的 Java 仍然受到支持。

#### Java 发布日期

以下项目列表包含了 Java 的发布日期，范围从 Java 7 到 Java 18：

- Java SE 7 (2011年7月)
- Java SE 8 (2014年3月)
- Java SE 9 (2017年9月)
- Java SE 10 (2018年3月)
- Java SE 11 (2018年9月)
- Java SE 12 (2019年3月)
- Java SE 13 (2019年9月)
- Java SE 14 (2020年3月)
- Java SE 15 (2020年9月)
- Java SE 16 (2021年3月)
- Java SE 17 (2021年9月)
- Java SE 18 (2022年7月)

如你所见，Java 7 和 Java 9 之间经历了六年时间，之后新版本的发布速度变得更加快了。以下链接包含一张 Java 路线图：https://medium.com/javavisited/the-java-roadmap-f9db163c2

如果你想了解在不同 Java 版本中引入的特性，请访问：https://www.javatpoint.com/history-of-java

#### 下载 Java 版本（简短版）

鉴于有许多 Java 版本可供，你如何决定哪个版本最适合你？答案可能涉及以下之一：

- 你公司使用的 Java 版本
- 最新的 LTS（长期支持）版本
- 你偏好的 Java 版本
- 最新的 Java 版本

另一点需要记住：如果你想满足上述列表中的所有要求，也可以下载多个版本的 Java。在你确定了适合你的 Java 版本后，请访问以下位置：

#### 选择 Java 版本（详细版）

在本书印刷时，Java 17 已可用，且 Java 18 将于 2022 年 7 月发布。旧版本 Java 的发布周期有时涉及三年或更久，而较新的 Java 版本每六个月发布一次。较新版本的更新集通常要小得多。

### Java 8 和 Java 11

Java 8 和 Java 11 曾拥有 LTS（长期支持）状态，目前 Java 17 拥有 LTS 状态。由于各种因素，某些公司仍在使用 Java 8，它是 Java 历史上最重要的发布之一。如果你感兴趣，Oracle 网站包含了 Java 8 的特性列表。事实上，Java 8 在所有后续版本（包括 Java 17）中都能正常工作。

然而，Java 8 和 Java 11 已被弃用，目前 Java 17 拥有 LTS 状态。那么，推荐哪个 Java 版本？答案取决于你的需求。如果你没有维护或开发旧版本 Java 代码的负担，那么使用 Java 17 可能是安全的。如果你没有选择，请考虑使用 Java 13、Java 11 或 Java 8（按此顺序）。

访问以下 URL 可获取有关早期 Java 版本和未来 Java 版本发布日期信息：

https://www.oracle.com/java/technologies/java-se-support-roadmap.html

### Java 版本号

在 Java 8 之前，编号格式为 1.x。因此，Java 7 也称为 Java 1.7，Java 8 称为 Java 8。但是，从 Java 9 开始，这种命名习惯已被废弃。例如，你输入命令 `java -version`，如果你的机器上安装了 Java 13，你将看到类似下面的输出：

```
java 13.0.1 2019-10-15
Java (TM) SE Runtime Environment (build 13.0.1+9)
Java HotSpot (TM) 64-Bit Server VM (build 13.0.1+9), mixed mode, (sharing)
```

目标是牢牢掌握 Java 13，然后通过学习 Java 13 之后版本中的新特性来增加你的知识。

### JRE 与 JDK

`JRE`（Java 运行环境）允许你运行 Java 代码，这意味着 Java 提供了 `java` 命令行工具。如果你使用的是 Unix/Linux 类型的机器，请输入以下命令：

```
$ which java
```

上一个命令将显示如下类型的输出：

```
$ /usr/bin/java
```

另一方面，`JDK`（Java 开发工具包）允许你编译和运行 Java 代码。虽然在 Java 8 之前 `JRE` 和 `JDK` 是分开下载的，但它们已经合并了，即从 Java 9 开始，Java 下载包是包含 `JRE` 的 `JDK`。

### Java 分发

有多个网站提供多种 Java JDK：`OpenJDK` 项目、`OracleJDK` 和 `AdoptOpenJDK`。`OpenJDK` 项目是唯一包含 Java 源代码的站点。

Oracle 提供的 JDK 可以在 Java 应用程序中免费使用。但它不支持对旧版本的更新：例如，一旦 Java 13 可发布，对 Java 12 的更新就停止了。Oracle 还提供了 `OracleJDK`，但它仅在开发期间免费使用：如果你将代码部署到生产环境，则必须向 Oracle 支付费用（Oracle 将为你提供额外的支持）。

你也可以使用 `AdoptOpenJDK`，它由不同的开发者和供应商开发，并且免费提供（与 `OpenJDK` 一样）。

### Java IDE

许多人更倾向于在 IDE 中工作，并且许多编程语言都有非常好的 IDE 可用。例如，如果你计划开发 Android 应用，在 `Android Studio` 中进行开发是值得的，它是对不熟悉命令行的人来说的一种备选方案。

如果你想在 IDE（集成开发环境）中编写 Java 代码，有多种支持 Java 的 IDE，例如 `NetBeans` 和 `Eclipse`。

### Java 简介

然而，此书侧重于从命令行操作 Java，你可以使用任选的文本编辑器创建 Java 类（或者如果你喜欢的话，也可以从 IDE 创建）。从命令行开发 Java 代码涉及简单的步骤，例如更新 `CLASSPATH` 环境变量以包含 JAR 文件，有时也包括编译后的 Java 类。

本章还包含一个简短的章节，展示了如何创建一个包含编译后的 Java 代码的简单 JAR 文件，在将该 JAR 文件添加到 `CLASSPATH` 变量后，你将看到如何在你自己的 JAR 文件中调用自定义的 Java 代码。请记住，书中的 Java 代码示例很短（通常很简单），因此你不需要 IDE。

### Java 数据类型、运算符及其优先级

Java 支持其他编译型语言中常见的原始数据类型集合。此外，Java 还提供了基于对象的对应类型。例如，原始数据类型 `int`、`double` 和 `float` 分别对应基于类的类型 `Integer`、`Double` 和 `Float`。

某些数据结构（如哈希表）不支持原始数据类型，因此必须基于类的对应类型。例如，如果你需要哈希表来维护一组整数，你需要创建一个包含每个整数的 `Integer` 对象并将其添加到哈希表中。当你从该哈希表中检索特定的基于 `Integer` 的值对象时，然后提取它的 `int` 值。这种方法比简单地在哈希表中存储和检索 `int` 涉及稍多一点的代码。此外，Java 提供了八种作为语言关键字的原始数据类型：

- `byte`: 16 位有符号补码整数
- `int`: 32 位有符号补码整数
- `long`: 64 位有符号补码整数
- `float`: 单精度 32 位 IEEE 754 浮点数
- `boolean`: true 或 false
- `char`: 有符号 16 位 Unicode 字符

书中大多数涉及算术的代码示例都使用整数和浮点数。

### Java 注释

Java 支持单行注释和多行注释，两者在此处均有展示：

```java
// 这是一个单行注释
/*
这是一个多行注释
使用了 C 语言风格的语法
*/
```

然而，Java 不支持嵌套注释（如 C++），所以这是一个错误：

```java
/* 第一条注释 /* 第二条注释的开始 */
```

根据之前的示例，以下语法是正确的：

```java
/* 第一条注释 // 第二条注释的开始 第一条注释的结束 */
```

### Java 运算符

Java 支持常见的算术运算符，其标准优先级（幂）高于乘法和除法，这两者的优先级都高于加减法。此外，Java 支持以下运算符：

| 类型 | 运算符 |
| :--- | :--- |
| 算术 | `+`, `-`, `*`, `/`, `%` |
| 赋值 | `=`, `-=`, `*=`, `/=`, `%=`, `^=` |
| 位运算 | `&`, `|`, `^`, `~`, `<<`, `>>` |
| 逻辑 | `&&`, `||` |
| 关系 | `==`, `!=`, `>`, `<=` |
| 三元 | `?` |

### Java 运算符的优先级

运算符优先级决定了表达式中项的分组方式，这反过来决定了表达式的求值方式。高优先级运算符先于低优先级运算符执行。Java 运算符从高到低的优先级排列如下：

| 类型 | 运算符 |
| :--- | :--- |
| 后置 | `++` |
| 一元 | `++`, `~` |
| 乘法 | `*`, `%` |
| 加法 | `+`, `-` |
| 移位 | `>>`, `<<` |
| 关系 | `>=`, `<=` |
| 关系 | `==`, `!=` |
| 逻辑 | `&&`, `||` |
| 三元 | `?` |
| 赋值 | `=`, `-=`, `*=`, `/=`, `%=`, `^=` |



# Java 数据类型、运算符及其优先级

Java 支持其他编译型语言中常见的原始数据类型集合。此外，Java 还提供了基于对象的对应类型。例如，原始数据类型 `int`、`double` 和 `float` 分别对应基于类的类型 `Integer`、`Double` 和 `Float`。

某些数据结构（如哈希表）不支持原始数据类型，因此基于类的对应类型是必要的。例如，如果你需要哈希表来维护一组整数，你需要创建一个包含每个整数的 `Integer` 对象并将其添加到哈希表中。当你从该哈希表中检索特定的基于 `Integer` 的值对象时，然后提取它的 `int` 值。这种方法比简单地在哈希表中存储和检索 `int` 涉及稍多一点的代码。此外，Java 提供了八种语言关键字的原始数据类型：

- `byte`：16 位有符号补码整数
- `int`：32 位有符号补码整数
- `long`：64 位有符号补码整数
- `float`：单精度 32 位 IEEE 754 浮点数
- `boolean`：true 或 false
- `char`：有符号 16 位 Unicode 字符

本书中大多数涉及算术的代码示例都使用整数和浮点数。

## Java 注释

Java 支持单行注释和多行注释，两者在此处均有展示：

```java
// 这是一个单行注释
/*
这是一个多行注释
使用了 C 语言风格的语法
*/
```

然而，Java 不支持嵌套注释（如 C++），所以这是一个错误：

```java
/* 第一条注释 /* 第二条注释的开始 */
```

根据之前的示例，以下语法是正确的：

```java
/* 第一条注释 // 第二条注释的开始 第一条注释的结束 */
```

Java 支持常见的算术运算符，其标准优先级（幂）高于乘法和除法，这两者的优先级都高于加减法。此外，Java 支持以下运算符：

| 类型 | 运算符 |
| :--- | :--- |
| 算术 | `+`, `-`, `*`, `/`, `%` |
| 赋值 | `=`, `-=`, `*=`, `/=`, `%=`, `^=` |
| 位运算 | `&`, `|`, `^`, `~`, `<<`, `>>` |
| 逻辑 | `&&`, `||` |
| 关系 | `==`, `!=`, `>`, `<=` |
| 三元 | `?` |

## Java 运算符的优先级

运算符优先级决定了表达式中项的分组方式，这反过来决定了表达式的求值方式。高优先级运算符先于低优先级运算符执行。Java 运算符从高到低优先级排列如下：

| 类型 | 运算符 |
| :--- | :--- |
| 后置 | `++` |
| 一元 | `++`, `~` |
| 乘法 | `*`, `%` |
| 加法 | `+`, `-` |
| 移位 | `>>`, `<<` |
| 关系 | `>=`, `<=` |
| 关系性 | `==`, `!=` |
| 逻辑 | `&&`, `||` |
| 三元 | `?` |
| 赋值 | `=`, `-=`, `*=`, `/=`, `%=`, `^=` |

# Java 简介

在一个 Java 文件中可以有多个类，但只能有一个公共类（`public`），且文件中的该公共类名必须与文件名匹配。

打开命令行窗口，导航到包含 `MyClass.java` 的目录，使用 `javac` 可执行文件从命令行编译 `MyClass.java`：

```
javac MyClass.java
```

Java 可执行文件会创建一个名为 `MyClass.class` 的文件，该文件包含 Java 字节码。使用 Java 可执行文件启动 Java 字节码（不要包含扩展名）：

```
java MyClass
```

请注意，在启动 Java 字节码时，你不需要指定 `.java` 或 `.class` 后缀。上一个命令的输出是：

```
Exception in thread "main" java.lang.NoSuchMethodError: main
```

注意：Java 源代码的文件名必须与其中的公共 Java 类匹配。例如，文件 `MyClass.java` 必须定义一个名为 `MyClass` 的 Java 类。

我们可以修复上一个列表 1.2 中的错误，该列表包含一个 `main()` 方法，它作为从命令行启动 Java 类的初始“入口点”。

## 列表 1.2：MyClass.java

```java
public class MyClass
{
    // 此代码没有任何作用
    public static void main(String[] args) {}
}
```

列表 1.2 包含公共静态方法 `main()`，其返回类型为 `void`，因为它不返回任何内容。`main()` 方法是静态的（`static`），这确保了当我们从命令行启动 Java 类时它是可用的。现在重新编译代码：

```
javac MyClass.java
```

从命令行启动该类：

```
java MyClass
```

你现在已经成功地创建、编译并启动了一个名为 `MyClass` 的 Java 类，它除了编译成功外，仍然什么都没做。下一步涉及在 Java 类中显示文本字符串，这将在下一节中讨论。

## “HELLO WORLD”示例

列表 1.3 显示了 `HelloWorld.java` 的内容，向你展示了如何从 Java 类打印字符串 "Hello World"。

### 列表 1.3：HelloWorld.java

```java
public class HelloWorld {
    public static void main(String args[]) {
        System.out.println("Hello World");
    }
}
```

列表 1.3 中的代码显示了一个名为 `main()` 的例程，它包含一个 `System.out.println()` 语句，用于打印字符串 "Hello World"。打开终端编译并启动列表 1.3 中的 Java 代码：

```
javac HelloWorld.java
```

输入以下命令启动编译后的代码：

```
java HelloWorld
```

上一个命令的输出在这里：

```
Hello World
```

现在你已经看到创建和编译一个简单的 Java 程序有多容易了，让我们来看看在 Java 中处理数字的示例。

## 数字处理

列表 1.4 显示了 `Numbers.java` 的内容，向你展示了如何处理整数和小数值。在代码示例中，我们将略过 Java 字符串的细节，但将在本章稍后部分进行详细讨论。

### 列表 1.4：Numbers.java

```java
public class Numbers {
    public static void main(String args[]) {
        // int 和 double 是基本类型：
        int x1 = 3, x2 = 7;
        System.out.println("x1: "+x1+" x2: "+x2);
        // Integer 和 Double 是类类型：
        Integer a1 = 3, a2 = 5;
        Double b1 = 3.2, b2 = 5.7;
        System.out.println("a1: "+a1+" a2: "+a2);
        System.out.println("b1: "+b1+" b2: "+b2);

        String s1 = "3", s2 = "5";
        String t1 = s1.toString();
        String t2 = Integer.toString(s1);

        System.out.println("s1: " + s1);
        System.out.println("s2: " + s2);
        System.out.println("t1: " + t1);
        System.out.println("t2: " + t2);
    }
}
```

列表 1.4 定义了 Java 类 `Numbers` 和一个包含算术计算的 `main()` 方法。作为早期预览，列表 1.4 包含了 `Integer` 类，它是基本类型的“包装器”。`Integer` 类有一些有用方法，例如 `toString()`，它可以将整数值转换为其字符串。注意使用 `Math.ceil()` 方法来寻找数字的向上位。输入以下命令启动编译后的代码：

```
java Numbers
```

上一个命令的输出是：

```
x1: 3 x2: 7
a1: 3 a2: 5
b1: 3.2 b2: 5.7
s1: 3
s2: 5
t1: 3
t2: 3
```

## 进制转换

Java 中的数字默认是 10 进制，但也支持二进制、八进制和十六进制。如输出所示：

```
hex
```

## 随机数

列表 1.5 显示了 `RandomNumbers.java` 的内容，向你展示了如何处理 Java 中的随机数。虽然我们现在只简单介绍，但将在后文中进行更详细的讨论。

### 列表 1.5：RandomNumbers.java

```java
public class RandomNumbers {
    public static void main(String args[]) {
        int die1, die2, sum;
        for (int i = 0; i < 10; i++) {
            die1 = (int)(Math.random() * 6);
            die2 = (int)(Math.random() * 6);
            sum = die1 + die2;
            System.out.println("die1: " + die1 + " die2: " + die2 + " sum: " + sum);
        }
    }
}
```

## 内置数学函数

Java 支持许多数学函数。列表 1.6 显示了 `MathFunctions.java` 的内容，向你展示了如何调用各种数学函数。

### 列表 1.6：MathFunctions.java

```java
public class MathFunctions {
    public static void main(String args[]) {
```



## Java 代码示例

### 数学运算

```java
double a = 7, b = 3;

// b 的平方根：
System.out.println("Square root of b: " + Math.sqrt(b));

// a 的 b次方：
System.out.println("Power of a and b is:" + Math.pow(a, b));

// a 和 b 的对数：
System.out.println("Logarithm of a: " + Math.log(a));
System.out.println("Logarithm of b: " + Math.log(b));

// 自然数 e (~2.71828...) 的 a次方：
System.out.println("Exponential of a: " + Math.exp(a));

// 两个数字的最小值和最大值
System.out.println("Minimum of a and b: " + Math.min(a, b));
System.out.println("Maximum of a and b: " + Math.max(a, b));
```

列表 1.6 展示了如何计算平方根、指数值和对数，以及一对数字的最小值和最大值。运行列表 1.6 中的代码，你将看到以下输出：

```
Square root of b: 1.732050807568872
Power of a and b is: 343.0
Logarithm of a: 1.945910149053312
Logarithm of b: 1.098612286681092
Exponential of a: 1096.633158242485
Minimum of a and b: 3.0
Maximum of a and b: 7.0
```

### 使用内置三角函数

列表 1.7 显示了 `TrigFunctions.java` 的内容，它展示了如何对涉及三角函数的数字进行各种操作。

#### 列表 1.7：TrigFunctions.java

```java
public class TrigFunctions {
    public static void main(String args[]) {
        // 默认单位是度:
        double a = 45;

        // 度转换为弧度 (pi/4):
        double b = Math.toRadians(a);

        // a 的正弦、余弦和正切:
        System.out.println("Sine of a: " + Math.sin(a));
        System.out.println("Cosine of a: " + Math.cos(a));
        System.out.println("Tangent of a: " + Math.tan(a));

        // a 的反正弦和双正弦:
        System.out.println("Arc Sine of a: " + Math.asin(a));
        System.out.println("Hyperbolic Sine of a: " + Math.sinh(a));
    }
}
```

列表 1.7 首先将变量 `a` 初始化为值 45，并将变量 `b` 初始化为 `a` 的弧度值。列表 1.7 计算了变量 `a` 的正弦、余弦和正切值。列表 1.7 的最后部分计算了变量 `a` 的反正弦和双正弦。运行列表 1.7 中的代码，你将看到以下输出：

```
Sine of a: 0.8509035245341184
Cosine of a: 0.5253219881877297
Tangent of a: 1.61971905438615
Arc Sine of a: NaN
Hyperbolic Sine of a: 1.746713552872547E19
```

### 使用位运算

本节将介绍如何对数字进行位运算。

#### 列表 1.8：Bitwise.java

```java
public class Bitwise {
    // 位运算符: &, |, ^ 和 ~
    // 异或 (^) 函数:
    // 0 ^ 0 = 0
    // 0 ^ 1 = 1
    // 1 ^ 0 = 1
    // 1 ^ 1 = 0

    public static void main(String[] args) {
        int num1, num2;

        num1 = 5;  // 二进制: 00101
        num2 = 10; // 二进制: 01010

        System.out.println("num1: " + num1);
        System.out.println("num2: " + num2);
        System.out.println("~num1: " + (~num1));
        System.out.println("num1&num2: " + (num1 & num2));
        System.out.println("num1|num2: " + (num1 | num2));
        System.out.println("num1^num2: " + (num1 ^ num2));

        System.out.println("num1-num2");

        num1 = 16; // 二进制: 010000
        num2 = 32; // 二进制: 100000

        System.out.println("num1: " + num1);
        System.out.println("num2: " + num2);
        System.out.println("~num1: " + (~num1));
        System.out.println("num1&num2: " + (num1 & num2));
        System.out.println("num1|num2: " + (num1 | num2));
        System.out.println("num1^num2: " + (num1 ^ num2));
    }
}
```

列表 1.8 初始化了变量 `num1` 和 `num2`，并执行了位操作，例如反转 `num1` 的值以及计算 `num1` 和 `num2` 的异或、与和或值。运行列表 1.8 中的代码，你将看到以下输出：

```
num1: 5
num2: 10
~num1: -6
num1^num2: 15
num1&num2: 0
num1|num2: 15
num1: 16
num2: 32
~num1: -17
num1^num2: 48
num1&num2: 0
num1|num2: 48
```

### String 类

类型为 `char` 的变量是单个字符，你可以通过 `char` 关键字这样定义它：

```java
char chl = 'Z';
```

类型为 `String` 的变量是一个由字符值序列组成的对象。Java 还支持 ASCII、UTF-8 和 Unicode。

### 字符、数组与字符串

列表 1.9 显示了 `CharStrings.java` 的内容，展示了如何定义字符、数组和字符串。

#### 列表 1.9：CharStrings.java

```java
public class CharStrings {
    public static void main(String args[]) {
        char ch1 = 'Z';
        char ch2 = ' ';
        char[] chars = {'h', 'e', 'l', 'o'};
        String str1 = new String(chars);
        String str2 = "hello";

        System.out.println("ch1: " + ch1);
        System.out.println("ch2: " + ch2);
        System.out.print("chars: ");
        for (char ch : chars) {
            System.out.print(ch);
        }
        System.out.println();
    }
}
```

列表 1.9 首先初始化变量 `ch1` 为值 'Z'，并将变量 `ch2` 初始化为空格。列表 1.9 打印了 `ch1` 和 `ch2` 的值。列表 1.9 遍历了 `chars` 数组并打印其内容。

### 字符串中的特殊字符

Java 处理字符串中的特殊字符的方式与处理任何字母或数字相同。因此，在定义字符串时不需要“转义”特殊字符。

在之前的输出中，空格和制表符之间没有可见区别，你可以在 vi 编辑器中看到。首先，

#### 列表 1.10：MyStrings.java

列表 1.10 定义了 Java 类 `MyStrings` 以及一个 `main()` 方法，该方法初始化了名称、特殊字符和空白字符的字符串。

```java
public class MyStrings {
    public static void main(String args[]) {
        String str1 = "John";
        String str2 = "Sally";
        String str3 = "*?)";
        String str4 = ".+@";
        String str5 = "\t";

        System.out.println("str1: " + str1);
        System.out.println("str2: " + str2);
        System.out.println("str3: " + str3);
        System.out.println("str4: " + str4);
        System.out.println("str5: " + str5);
    }
}
```

这三个 `println()` 语句显示了它们的值，如下：

```
str1: John str2: Sally
str3: *?) str4: .+@
str5: 
```

将前面代码的输出重定向到名为 out1 的文件（或其他方便的名称）。接下来，用 vi 编辑器打开该文件，然后输入 `:set list`，之后你会看到如下输出：

```
str1: John str2: Sally$
str1: John str2: Sally$
str3: *)str4: .+@
str5: $
str6: ^IS
```

`$` 表示行结束，它出现在前述输出的每一行末尾。注意最后一行显示了 `^IS`，这表示存在制表符，该制表符是列表 1.10 中变量 `str6` 的值。

### 新的 new 运算符

上一个节包含了多个在 Java 中直接赋值字符串的示例。另一种方法涉及 `new` 运算符，它在表面上看起来是相似的，但它有一个重要的区别。当你以列表 1.11 所示的方式使用相同的字符串初始化两个变量时，它们将占据相同的内存位置。当你使用 `new` 运算符时，这两个变量将占据不同的内存位置。

列表 1.11 显示了 `ShowPeople.java` 的内容，该程序使用 `new` 运算符初始化两个字符串并打印它们的值。

#### 列表 1.11: ShowPeople.java

```java
public class ShowPeople {
    // 不能在 main() 中初始化
    String str5, str6;

    public ShowPeople(String args[]) {
        String str1, str2, str3, str4;

        // str1 和 str2 占据不同的内存位置
        str1 = new String("My name is John Smith");
        str2 = new String("My name is John Smith");

        // str3 和 str4 占据相同的内存位置
        str3 = "My name is Jane Andrews";
        str4 = "My name is Jane Andrews";

        System.out.println(str1);
        System.out.println(str2);
        System.out.println(str3);
        System.out.println(str4);

        // error: 非静态变量 str5 无法
        // 从静态上下文中引用：
        // str5 = new String("another string");
        // str6 = new String("yet another string");
    }
}
```

列表 1.11 包含一个 `main()` 方法，它定义并初始化了字符串 `str1` 到 `str4` 并打印了其内容。列表 1.11 的输出为：

```
My name is John Smith
My name is John Smith
My name is Jane Andrews
My name is Jane Andrews
```

列表 1.11 中的代码包含硬编码的值，因此没有重用性。例如，假设你想打印包含人员姓名的数组中定义的所有名字。也许你想打印从这些数组中随机选择的名称。你可能还会从命令行获取一个人的名和姓，然后打印该人的名字。

下一节提供了更多关于 Java String 类中 `==` 和 `equals()` 方法之间区别的详细信息。

### 字符串的相等性

与其他语言不同，`==` 运算符并不确定两个字符串是否相同：该运算符仅确定两个变量是否引用相同的内存位置。`equals()` 方法比较两个字符串的内容，而 `==` 运算符匹配字符串的对象或引用。

列表 1.12 显示了 `EqualStrings.java` 的内容，它说明了如何比较两个字符串并确定它们是否具有相同的值或引用（两者都有）。

#### 列表 1.12: EqualStrings.java

```java
import java.io.IOException;

public class EqualStrings {
    public static void main(String[] args) throws IOException {
        String str1 = "Pizza";
        String str2 = "Pizza";

        if (str1.equals(str2))
            System.out.println("str1 and str2: equal values");
        if (str1 == str2)
            System.out.println("str1 and str2: equal references");

        String str3 = "Pasta";
        String str4 = new String("Pasta");

        if (str3.equals(str4))
            System.out.println("str3 and str4: equal values");
        else
            System.out.println("str3 and str4: unequal values");

        if (str3 == str4)
            System.out.println("str3 and str4: equal references");
        else
            System.out.println("str3 and str4: unequal values");
    }
}
```

列表 1.12 定义了 Java `EqualStrings` 以及一个 `main()` 方法，该方法定义了字符串变量 `str1`、`str2`、`str3` 和 `str4`。运行列表 1.12 中的代码，将看到如下输出：

```
str1 and str2: equal values
str1 and str2: equal references
str3 and str4: unequal values
str3 and str4: references
```



当你创建一个字符串字面量时，JVM（Java 虚拟机）会检查该字符串是否存在于所谓的“字符串池”中。如果该字符串于池中，Java 将返回它的引用；否则将创建一个新的字符串实例（并将其放入池中）。下一节包含一个 Java 代码示例，说明如何确定两个字符串是否相同。

## 比较字符串

列表 1.13 显示了 `CompareStrings.java` 的内容，它说明了如何比较两个字符串并确定它们是否具有相同的值或相同的引用（两者都有）。

### 列表 1.13: CompareStrings.java

```java
public class CompareStrings {
    public CompareStrings() {}
    public static void main(String[] args) {
        String line1 = "This is a simple sentence";
        String line2 = "this is a simple sentence";
        System.out.println(line1);
    }
}
```

列表 1.13 定义了 Java 类 `CompareStrings` 以及一个 `main()` 方法，它定义了字符串变量 `line1` 和 `line2`。运行 1.13 中的代码，将看到如下输出：

```
This is a simple sentence
```

（等待，OCR 文字说：“line1 和 line2 是不区分大小写的，line1 是混合大小写的”）

## 在 Java 中搜索子字符串

列表 1.14 显示了 `SearchString.java` 的内容，说明了如何使用 `indexOf()` 方法确定一个字符串是否是另一个字符串的子字符串。注意此代码示例涉及一个 `if` 语句，将在章节的最后一个代码示例中进行详细讨论。

### 列表 1.14: SearchString.java

```java
public class SearchString {
    public static void main(String args[]) {
        int index;
        String str1 = "zz", str2 = "Pizza";
        index = str2.indexOf(str1);
        if (index < 0) {
            System.out.println(str1 + " is not a substring of " + str2);
        } else {
            System.out.println(str1 + " is a substring of " + str2);
        }
    }
}
```

列表 1.14 包含一个 `main()` 方法，它计算 `str1` 在 `str2` 中的索引。运行 1.14 中的代码，将看到如下输出：

```
zz is not a substring of Pizza
```

## 解析字符串

Java 支持命令行参数，这使得你能够从命令行使用不同的命令行值启动程序。比较

使用 `equals()` 方法判断两个 Java 字符串的值是否相同。虽然某些语言使用 "=" 来比较字符串，但在 Java 中，"=" 仅比较字符串的两个引用（而不是值）。

使用 `parseInt()` 方法（尝试）将字符串转换为整数：

```java
int num = Integer.parseInt("1234");
```

使用 `substring()` 方法根据空白字符分割字符串：

```java
String[] strArray = aString.split("\\s+");
```

正则表达式 `\s` 匹配一个或多个各种空白字符，包括 `" "`、`"\t"`、`"\r"` 和 `"\n"`。

使用此代码段反转 Java 字符串的简单方法：

```java
String rev = new StringBuilder(original).reverse().toString();
```

到为止，你已经看到了在 Java 中处理字符串的几个示例，欲了解更多信息，请访问此 URL：

https://docs.oracle.com/javase/7/docs/api/java/lang/String.html

## 重写 Java 的 toString() 方法（可选）

你已经已经在 Java 类中看到了几个 `toString()` 方法的示例，包括 `Integer.toString()` 和 `Character.toString()`。`Object` 类是 Java 中所有类的父类，它的 `toString()` 方法返回 Java 中任何对象的字符串表示。`Object` 类的默认 `toString()` 方法显示对象类名及其哈希值的组合，这是一种用以区分同一 Java 类中不同实例的机制。这里是默认 `toString()` 方法的示例：

```
OverrideToString@4dc63996
```

但你可以重写 `toString()` 方法，为你的自定义类返回不同的字符串表示。

列表 1.16 显示了 `OverrideToString.java` 的内容，说明了如何重写属于 `Object` 类的 `toString()` 方法，以便为自定义 Java 类返回新的字符串表示。

### 列表 1.16：OverrideToString.java

```java
public class OverrideToString {
    private String fname = "John";
    private String lname = "Smith";

    @Override
    public String toString() {
        return fname + " " + lname;
    }

    public static void main(String[] args) {
        OverrideToString ots = new OverrideToString();
        System.out.println("Overriding toString(): " + ots.toString());
    }
}
```

列表 1.16 包含了变量 `fname`、`lname` 以及拼接 `fname` 和 `lname` 值的 `toString` 方法。运行列表 1.16 中的代码，你将看到以下输出：

```
Overriding toString(): John Smith
```

顺便一下，如果你“注释掉”列表 1.16 中的 `toString()` 方法，你将看到默认 `toString()` 方法的输出：

```
OverrideToString@4dc63996
```

## 自动装箱与拆箱（可选）

自动装箱（autoboxing）一词是指 Java 编译器在基本类型与其对应的对象包装类之间进行的自动转换。例如，自动装箱将 `int` 转换为 `Integer`，将 `double` 转换为 `Double` 等。拆箱（unboxing）则指向相反方向进行转换的情况。

自动装箱和拆箱让你能够编写更整洁的代码，从而使你的代码更易读。下表列出了基本类型及其对应的包装类，Java 编译器在自动装箱和拆箱时使用它们：

| 基本类型 | 包装类 |
| :--- | :--- |
| boolean | Boolean |
| byte | Byte |
| char | Character |
| float | Float |
| int | Integer |
| long | Long |
| short | Short |
| double | Double |

这是自动装箱最简单的示例：

```java
Character ch = 'a';
```

本节剩余的示例使用了泛型。如果你不熟悉泛型的语法，网上有带有详细解释的文章。

考虑以下代码，它涉及 `ArrayList` 类和一个通过 `for` 循环向变量 `items` 添加 50 个数字的操作：

```java
List<Integer> items = new ArrayList<Integer>();
for (int i = 1; i < 50; i += 2)
    items.add(i);
```

虽然你将 `int` 值作为基本类型而不是 `Integer` 对象传递变量 `items`，但代码可以正确编译。由于 `items` 是 `Integer` 对象的列表，而不是 `int` 值的列表，你可能会奇怪为什么 Java 编译器没有发出编译时错误。编译器没有生成错误，因为它从 `i` 创建了一个 `Integer` 对象并将其添加到 `items` 中。因此，编译器在运行时将之前的代码替换为如下：

```java
List<Integer> items = new ArrayList<Integer>();
for (int i = 1; i < 50; i += 2)
    items.add(Integer.valueOf(i));
```

作为自动装箱的另一个示例，考虑以下方法：

```java
public static int sumEven(List<Integer> items) {
    int sum = 0;
    for (Integer i : items)
        if (i % 2 == 0)
```

### 列表 2.1: Conditional.java

```java
public class Conditional {
    int x = 12, y = 15;
    public Conditional() {}
    public void IfElseLogic() {
        if (x % 2 == 0) {
            System.out.println("x is even: " + x);
        } else if (x % 4 == 0) {
            System.out.println("x is divisible by 4: " + x);
        } else {
            System.out.println("x is odd: " + x);
        }
        if (x % 2 == 0) {
            if (x % 4 == 0) {
                System.out.println("x is divisible by 4: " + x);
            }
        }
        if (y % 3 == 0 && y % 5 == 0) {
            System.out.println("y is divisible by 3 and 5: " + y);
        } else if (y % 3 == 0) {
            System.out.println("y is divisible only by 3: " + y);
        } else if (y % 5 == 0) {
            System.out.println("y is divisible only by 5: " + y);
        } else {
            System.out.println("y is not divisible by 3 or 5: " + y);
        }
    }
    public static void main(String args[]) {
        Conditional c1 = new Conditional();
        c1.IfElseLogic();
    }
}
```

列表 2.1 定义了 Java 类 `Conditional` 以及公共方法 `IfElseLogic`，该方法对整数变量 `x` 和 `y` 执行取模运算，`x` 和 `y` 分别地被初始化为值 12 和 15。

如果 `x % 2` 等于 0，则 `x` 是偶数；如果 `x % 4` 等于 0，则 `x` 是 4 的倍数；如果 `y % 3` 等于 0，则 `y` 是 3 的倍数。列表 2.1 包含了 if-else 块，其中一个嵌套块。尝试确定代码的输出。运行列表 2.1 中的代码，你将看到以下输出：

```
x is even: 12
x is divisible by 4: 12
y is divisible by 3 and 5: 15
```

你可以创建更复杂的布尔表达式，涉及“与”(and)、“或”(or)和“非”(not) 的组合。使用列表 2.1 中的代码作为基准，你可以添加自己的代码。下一节将展示如何在 Java 中处理涉及数字和字符串的布尔表达式。

## 处理布尔表达式

本节展示了如何根据各种类型的比较创建布尔表达式。列表 2.2 显示了 `BooleanExamples.java` 的内容，它比较了整数、double 和字符。虽然大多数结果符合你的预期，但请看你可以如何预测然后比较你的答案。

### 列表 2.2: BooleanExamples.java

```java
public class BooleanExamples {
    public static void main(String[] args) {
        // 处理整数和 double（浮点数）
        int int1 = 5;
        double double1 = 3.53;
        double double2 = 54.88;
        System.out.println("int1 = " + int1);
        System.out.println("double1 = " + double1);
        System.out.println("double2 = " + double2);
        System.out.println("");
        System.out.println("int1 < 5: " + (int1 < 5));
        System.out.println("double1 > double2: " + (double1 > double2));
        System.out.println("");
        // int1 和 double 提升
        System.out.println("int1 >= double1: " + (int1 >= double1));
        System.out.println("double1 <= 3: " + (double1 <= 3));
        System.out.println("");
        // 处理字符
        char char1 = 'A';
        char char2 = 'C';
        System.out.println("char1 = " + char1);
        System.out.println("char2 = " + char2);
        // 字典序比较
        System.out.println("char1 < char2: " + (char1 < char2));
        // A: 65, B: 66, C: 67, ..., Z: 90
        // a: 97, b: 98, c: 99, ..., z: 122
        // char2 提升为十进制值 (67)
        System.out.println("10 > char2: " + (10 > char2));
        System.out.println("");
        boolean mixed = (int1 == 5) || char1 < 'A' && double1 != 21.8;
        System.out.println("mixed: " + mixed);
        System.out.println("");
        // 处理布尔值
        boolean bool1 = false;
        boolean bool2 = true;
        System.out.println("bool1: " + bool1);
        System.out.println("bool2: " + bool2);
        System.out.println("bool1 == bool2: " + (bool1 == bool2));
        System.out.println("bool1 = bool2: " + (bool1 = bool2));
        System.out.println("");
        String str1 = new String("Pizza1");
        String str2 = new String("Pizza2");
        System.out.println("str1: " + str1);
        System.out.println("str2: " + str2);
        // 比较 str1 和 str2
        System.out.println("str1 == str2: " + (str1 == str2));
        System.out.println("str1 = str2: " + (str1 = str2));
    }
}
```



列表 2.2 包含了各种数据类型，包括整数、浮点值、字符值和布尔值。运行列表 2.2 中的代码你将看到以下输出：

```
int1 = 5
double1 = 3.53
double2 = 54.88
int1 < 5: false
double1 > double2: false
int1 >= double1: true
double1 <= 3: false
char1 = A
char2 = C
char1 < char2: true
10 > char2: false
mixed: true
bool1: false
bool2: true
bool1 == bool2: false
bool1 = bool2: true
str1: Pizza1
str2: Pizza2
str1 == str2: false
str1 = str2: true
```

注意加粗显示的输出：第一部分显示为 true，尽管 `bool1` 被赋值为 false。这是因为 `=` 运算符是一个赋值运算符；因此，`bool1` 被赋值为 `bool2` 的值，导致 `bool1` 的新值为 true。

类似地，第二个加粗的输出显示了字符串 Pizza2，因为 `=` 运算符赋值了字符串 Pizza2。

下一节将展示如何在 Java 中处理涉及数字和字符串的布尔表达式。

`java.util` 包包含 `Date` 类，该类封装了当前日期。`Date` 支持空构造函数，该构造函数将对象初始化为自 1970 年 1 月 1 日午以来的毫秒数。

## 当前日期和时间

列表 2.3 显示了 `DateTime.java` 的内容，说明了如何配合 `toString()` 方法使用 `Date` 对象。

### 列表 2.3: DateTime.java

```java
import java.util.Date;

public class DateDemo {

    public static void main(String[] args) {

        // 实例化 Date
        Date date = new Date();

        // 使用 toString() 显示时间和日期
        System.out.println(date.toString());

    }

}
```

Java 还提供了几种用于日历日期的方法，其中一些所示：

- `getTime()` 返回自 1970 年 1 月 1 日午以来的毫秒数
- `before()`、`after()` 和 `equals()`

```java
SimpleDateFormat ft = new SimpleDateFormat("yyyy-MM-dd");
```

```java
// 注意这里的三元运算符：
String input = args.length == 0 ? "1818-11-11" : args[0];
System.out.print(input + " 解析为 ");
```

```java
try {
    t = ft.parse(input);
    System.out.println(t);
} catch (ParseException e) {
    System.out.println("无法解析: " + ft);
}
```

示例 2.5 定义了 `StringToDate` 类和一个 `main()` 方法，并将变量 `ft` 定义为 `SimpleDateFormat` 的实例。通过三元运算符初始化 `input`：如果没有指定命令行参数，它将初始化为字符串 `"1818-11-11"`；否则，`input` 变量被赋值为 `args[0]` 的值（第一个参数）。

`main()` 方法的后续部分包含一个 `try/catch` 块用于将输入转换为有效日期：如果 `input` 的值格式无效，则执行 `catch()` 块并显示相应的消息。现在编译并运行示例 2.5 中的代码，你将看到如下输出：

`Thu Aug 13 09:51:52 CDT 2021`

`java.time` 包（稍后会讨论）包含一些常用的类，在这里提供了：

- `LocalDate`
- `LocalDateTime`
- `Period`
- `Duration`

如果你需要在 Java 代码中处理日期，请搜索详细的解释和 Java 代码示例。

## 使用 Unicode、i18n 和 i10n

本节讨论了 Java 对 UTF-8 和 Unicode 的支持，并提供了一个显示中文和假名文本的代码示例。Unicode 标准为每种语言的每个字符提供了一个唯一的数字。此外，Unicode 在主流操作系统、搜索引擎、浏览器、笔记本电脑和智能手机上都得到了支持。截至 2019 年 5 月，Unicode 包含了 137,994 个字符，涵盖了现代和历史脚本，以及多种符号和表情。Unicode 可以通过不同的编码实现，包括 UTF-8、UTF-16 和 UTF-32（以及其他编码），这些编码提供了完整的 Unicode 支持。

Java 支持 UTF-8，它是 Web 上的主流编码（用于 94% 的网站）。UTF-8 对前 128 个代码点使用一个字节，对其他字符最多使用 4 个字节。前 128 个 Unicode 代码点代表 ASCII 字符，这意味着任何 ASCII 文本都是 UTF-8。有关 Unicode 的更多信息，请参阅维基百科页面：https://en.wikipedia.org/wiki/Unicode

此外，访问 Unicode 官网获取更多信息：https://home.unicode.org/

示例 2.6 显示了 `Unicode.java` 的内容，其中包含一些 Unicode 代码片段。

### 示例 2.6: Unicode.java

```java
public class Unicode {

    public Unicode() {}

    public static void main(String[] args) {

        String mand = "你好";
        String hira = "こんにちは";

        System.out.println("中文: " + mand);
        System.out.println("假名: " + hira);

    }

}
```

示例 2.6 分别用中文和假名的 Unicode 字符初始化字符串变量 `mand` 和 `hira`。运行该代码，你将看到如下中文和假名输出（“输出很酷”）：

中文：你好
假名：こんにちは

虽然 i18n（国际化）和 i10n（本地化）非常相似且经常被混淆，但它们的主要区别在于：i18n 指在网页上显示不同语言的文本，而 i10n 指“本地化”，即在网页上根据特定语言显示日期、数字和货币。

i18n 的实现涉及一个包含键值对的文件，每种语言一个文件。Java 使用 `Bundle` 类和算法来确定选择哪种语言和地区，这些已经在每个用户的笔记本电脑或桌面上设置好了。例如，一个包含美式英语和意大利语的文件可能如下：

```
hello: ciao
goodbye: ciao
friend: amico
```

请记住，与英语不同，罗曼语（包括意大利语）和日耳曼语有性别区分：意大利语有阳性和阴性之分。因此，`amico` 指男性朋友，而 `amica` 指女性朋友。顺便提到，某些语言（如日语）没有性别区分。

网上有一篇关于 i18n 和 i10n 的详细文章：

> https://dzone.com/articles/a-beginners-guide-to-java-internationalization

本节的最后一个主题是 i10n，通过显示数字格式的代码示例来说更为直观。具体而言，示例 2.7 显示了 `I10NumberFormats.java` 的内容，说明了三种语言（英语、意大利语和中文）的数字格式，包括小数点和千位分隔符。

### 示例 2.7: I10NumberFormats.java

```java
import java.util.Locale;
import java.text.NumberFormat;

public class I10NumberFormats {

    public I10NumberFormats() {}

    public static void main(String[] args) {

        double d = 123456.789;

        NumberFormat nf1 = NumberFormat.getInstance(Locale.US);
        NumberFormat nf2 = NumberFormat.getInstance(Locale.ITALY);
        NumberFormat nf3 = NumberFormat.getInstance(Locale.CHINA);

        System.out.println(nf1.format(d));
        System.out.println(nf2.format(d));
        System.out.println(nf3.format(d));

    }

}
```

## Java 异常处理

为了方便起见，这里列出了一些较早 Java 异常的导入语句：

- `java.io.IOException`
- `java.lang.ArithmeticException`
- `java.lang.NumberFormatException`
- `java.lang.ArrayIndexOutOfBoundsException`
- `java.net.MalformedURLException`
- `java.util.InputMismatchException`

本章后续的 Java 代码示例包含了上述异常的示例（即：本书未讨论与 SQL 相关的异常）。

Java 提供了两种异常：检出异常（checked exceptions）和未检异常（unchecked exceptions），这两者将在接下来的章节中进行讨论。

### 检出异常

检出异常（也称为编译异常）由编译器在编译期间进行检查：这样做可以确认异常是否已由程序员处理。如果没有处理，系统将显示编译错误。例如，`SQLException`、`IOException`、`InvocationTargetException` 和 `ClassNotFoundException` 都是检出异常。

### 未检异常

未检异常（也称为运行时异常）在 Java 程序执行期间发生。通常情况下，运行时异常在编译过程中会被忽略。它们在编译程序时不会被检查。示例包括错误的 API 调用和逻辑错误。Java 中的未检异常包括以下几种：

- `ArrayIndexOutOfBoundsException`
- `NullPointerException`
- `IllegalArgumentException`
- `IllegalStateException`

当你的代码尝试访问不存在的数组元素时，会发生 `ArrayIndexOutOfBoundsException`：即索引值无效（太大或为负）。

当你的代码尝试访问一个未初始化的对象时，会发生 `NullPointerException`。

当向方法传递了错误的参数类型时，会发生 `IllegalArgumentException`。例如，如果一个方法期望 `int` 类型的变量，而你传递了一个不兼容类型的变量，或者传递了一个 `null` 变量，你就会看到此异常。

当环境状态与正在执行的操作不匹配时，会发生 `IllegalStateException`。

### throws 关键字

`throws` 关键字表示如果方法中发生了指定的异常，该方法可能抛出的异常类型，在这种情况下，可能会发生以下情况：

- 调用者方法处理了抛出的异常，或者
- 它的“父级”处理了该异常，或者
- “父级”通过调用方法链将异常向上传递。

如果异常没有被调用方法链中的任何方法处理，则会抛出异常并停止程序执行。

或者，你可以将代码包含在 `try/catch/finally` 块中，其中 `catch` 块指定了捕获的异常。你可以包含多个 `catch` 块，每个 `catch` 块捕获特定的异常：第一个 `catch` 是最具体的（例如 `DivisionByZero`），而最后一个 `catch` 块是最“通用”的（例如 `Exception`）。

### Throwable 类

`Throwable` 类是所有异常和错误的超类。请记住以下规则：不要在 `catch` 句中捕获 `Throwable` 异常，因为这将会捕获所有的错误以及所有的异常。错误由 JVM 抛出以表示严重问题（应用程序并不打算处理它们）。典型的示例包括 `OutOfMemoryError` 或 `OverflowError`。两者都是由应用程序控制之外的情况引起的，且无法处理。

另一个建议：避免在捕获异常后再次抛出相同的异常。这样做会为同一个异常生成多个错误信息。

### 获取用户输入并处理异常

涉及用户输入的代码示例包含一个 `try` 块，尝试某些操作，例如将字符串转换为数字。如果用户提供了非数字输入，转换将失败，此时 `catch` 块将捕获发生的错误，并执行 `catch` 块中的代码。

此外，你可以在 `catch` 块之后包含一个 `finally` 块（是的，允许包含多个 `catch` 块），它会在几乎每种情况下被执行（该规则的“例外”涉及调用 `System.exit(1)` 语句）。请注意，如果你在一个无法抛出异常的类中使用 `try/catch` 块，Java 将在你尝试编译代码时提醒你。

代码示例向你展示了两个尚未讨论的内容。首先，你将看到如何使用 `import` 语句来访问为我们处理底层细节现有类，这样我们就不需要“重复轮子”。Java 导入语句非常强大，书中几乎所有的代码示例都使用了它们。

其次，你将学习如何使用 `try/catch` 块来处理尝试将输入字符串转换为整数或浮点值时可能发生的异常。`System.in.read()` 将输入字符串视为 ASCII 值，这意味着输入字符串“0”会被转换为 48，“1”会被转换为 49，依此类推。

列表 2.9 显示了 `UserInput.java` 的内容，该程序提示用户输入字符串，然后尝试将该字符串转换为数字。这是本部分中最简单的示例，没有用于处理任何异常的 `try/catch` 代码块。

### 列表 2.9: UserInput.java

```java
import java.util.Scanner;

public class UserInput {

    public static void main(String args[]) {

        System.out.print("Enter a number: ");
        Scanner scan = new Scanner(System.in);
        int num1 = scan.nextInt();
        System.out.println("you entered a number");

    }

}
```

列表 2.9 提示用户输入，这些输入由 `Scanner` 类的实例变量 `scan` 进行处理。`Scanner` 的 `nextInt()` 方法将输入转换为整数值，并赋值给变量 `num1`，然后通过 `System.out.println()` 语句打印。以下是启动代码时的输出：

```
Enter a number: 123
you entered a number
```

当用户输入非数字字符串时，输出如下：

```
Enter a number: x123
Exception in thread "main" java.util.InputMismatchException
    at java.util.Scanner.throwFor(Scanner.java:840)
    at java.util.Scanner.next(Scanner.java:1461)
    at java.util.Scanner.nextInt(Scanner.java:2091)
    at java.util.Scanner.nextInt(Scanner.java:2050)
    at UserInput.main(UserInput.java:9)
```

由于此异常在列表 2.9 中未被捕获，可以看到堆栈跟踪。

让我们检查列表 2.10，它显示了 `UserInput.java` 的内容，该程序提示用户输入字符串。注意此代码示例包含一个 `try/catch` 块，尝试将输入字符串转换为数字。

### 列表 2.10: UserInput.java

```java
import java.util.InputMismatchException;
import java.util.Scanner;

public class UserInput2 {

    public static void main(String args[]) {

        System.out.print("Enter a number: ");
        Scanner scan = new Scanner(System.in);

        try {
            int num1 = scan.nextInt();
            System.out.println(num1 + " is a number");
        } catch (InputMismatchException ime) {
            System.out.println("You did not enter a number");
            System.out.println("==> Before the stack trace...");
            ime.printStackTrace();
        }
    }
}
```



System.out.println("==> After the stack trace...");

}

}

```

列表 2.10 包含一个 try/catch 代码块，其中 try 块包含输入相关的代码，catch 块包含在发生错误时调用的代码。特别是，我们知道当用户输入无法转换为数字的字符串时会发生错误。当你启动代码时的输出如下：

```
Enter a number: 123
123 is a number
```

当你输入非数字字符串时，输出如下：

```
Enter a number: x123

You did not enter a number

==> Before the stack trace...

java.util.InputMismatchException
    at java.util.Scanner.throwFor(Scanner.java:840)
    at java.util.Scanner.next(Scanner.java:1461)
    at java.util.Scanner.nextInt(Scanner.java:2091)
    at java.util.Scanner.nextInt(Scanner.java:2050)
    at UserInput2.main(UserInput.java:12)

==> After the stack trace...
```

### 解析用户输入和处理异常

`Integer` 类包含两个用于解析字符串的方法（即将字符串转换为数字）：

```java
static int parseInt(String s)
static int parseInt(String s, int radix)
```

第一个方法（如列表 2.11 所示）使用默认的基数 10，而第二个方法允许你指定不同的基数。例如，如果你想将用户输入转换为十六进制值，则可以指定基数为 16。

列表 2.11 显示了 `UserInput.java` 的内容，它提示用户输入字符串，然后尝试将该字符串转换为数字。它还捕获了用户的输入字符串。

### 列表 2.11：TextInput.java

```java
import java.io.Console;
import java.lang.NumberFormatException;

public class UserInput {

    public static void main(String[] args) {

        Console input = System.console();

        String strl = input.readLine("Enter a number: ");

        try {

            int numl = Integer.parseInt(strl);

            System.out.println(strl + " is a number");

        } catch (NumberFormatException nfe) {

            System.out.println(strl + " is not a number");

        }

    }

}
```

列表 2.11 初始化变量 `input` 为 `Console` 类的一个实例。接下来，变量 `strl` 被赋值为用户输入的值，该值是由 `readLine()` 方法“捕获”的。

此时，我们已经获得了用户输入的内容，可以使用 `try/catch` 块来判断输入字符串是否可以转换为数字。当你运行代码时的输出如下：

```
Enter a number: 123
123 is a number
```

当你输入非数字字符串时的输出如下：

```
Enter a number: x123
x123 is not a number
```

列表 2.11 中的代码正确处理了输入非数字字符串的情况。请注意，这里没有堆栈跟踪（stack trace），我们可以轻松地看到转换为整数值失败的情况。此外，我们还可以处理输入字符串为浮点数的情况。

列表 2.12 显示了 `UserInput4.java` 的内容，它提示用户输入字符串，然后尝试将该字符串转换为整数。如果失败，代码将尝试将字符串转换为小数；如果这次也失败，则显示错误消息。

### 列表 2.12：UserInput4.java

```java
import java.io.Console;
import java.lang.NumberFormatException;

public class UserInput {

    public static void main(String[] args) {

        Console input = System.console();

        String strl = input.readLine("Enter a number: ");

        try {

            int numl = Integer.parseInt(strl);

            System.out.println(strl + " is a number");

        } catch (NumberFormatException nfe) {

            System.out.println(strl + " is not an integer");

            try {

                float decl = Float.parseFloat(strl);

                System.out.println(decl + " is a decimal value");

            } catch (NumberFormatException nfe2) {

                System.out.println(strl + " is not a decimal");

            }

        }

    }

}
```

列表 2.12 的代码与列表 2.11 相同，唯一的区别是：`try/catch` 块包含了第二个 `try/catch` 块，它尝试将用户输入转换为浮点数。因此，代码对输入字符串进行了两次尝试，之后代码判断输入是非数字字符串。当你运行代码时的输出如下：

```
Enter a number: 123.4
123.4 is not an integer
123.4 is a decimal value
```

当你输入非数字字符串时的输出如下：

```
Enter a number: x123
x123 is not a number
```

### 嵌套异常

Java 提供了许多类来处理在各种情况下可能发生的异常。例如，当你尝试打开一个文件时，Java 会抛出 `FileNotFoundException`。当你尝试将包含字母的字符串转换为数字时，会得到异常。通用语法是 `try/catch`，其中 `catch` 块可以包含多个 `catch` 语句。如果抛出异常，匹配的 `catch` 块将被执行。请记住，`finally` 块无论是否发生异常都会执行。

另一个需要注意的是，`finally` 块在 `try/catch` 语句中是可选的。列表 2.13 显示了 `UserInput1.java` 的内容，展示了如何使用 `try/catch` 块来处理转换错误。

### 列表 2.13：UserInput1.java

```java
import java.io.Console;
import java.lang.NumberFormatException;

public class UserInput {

    public static void main(String[] args) {

        Console input = System.console();

        String strl = input.readLine("Enter a number: ");

        try {

            int numl = Integer.parseInt(strl);

            System.out.println(strl + " is a number");

        } catch (NumberFormatException nfe) {

            System.out.println(strl + " is not a number");

        } finally {

            System.out.println("Conversion attempt finished.");

        }

    }

}
```

列表 2.13 显示了 `String1.java` 的内容，展示了如何使用 `valueOf()` 和 `parseInt()` 方法进行转换。

### 列表 2.13：String1.java

```java
import java.lang.NumberFormatException;

public class String1 {

    int x;
    int y;

    public void convert(String str) {

        try {

            x = Integer.parseInt(str);

            System.out.println("x: " + x);

        } catch (NumberFormatException nfe) {

            System.out.println("x: " + str + " is not an integer");

        } finally {

            System.out.println("Conversion of x finished.");

        }

    }

    public void convert(String str) {

        try {

            y = (int) Double.parseDouble(str);

            System.out.println("y: " + y);

        } catch (NumberFormatException nfe) {

            System.out.println("y: " + str + " is not a decimal");

        } finally {

            System.out.println("Conversion of y finished.");

        }

    }

    public static void main(String[] args) {

        String1 s1 = new String1();

        s1.convert("123");

        s1.convert("123.4");

        s1.convert("x123");

    }

}
```

列表 2.13 展示了基数 10 转换的示例。列表 2.14 展示了如何使用 `try/catch/finally` 来处理除以零的情况。

### 列表 2.14：DivideBy.java

```java
import java.lang.ArithmeticException;
import java.util.InputMismatchException;
import java.util.Scanner;

public class DivideBy {

    public static void main(String[] args) {

        int number = 3, denom = 0;
        double ratio = 0.0;

        System.out.print("Enter a number: ");

        Scanner scan = new Scanner(System.in);

        try {

            denom = scan.nextInt();

            System.out.println(denom + " is a number");

            try {

                ratio = (double) number / denom;

                System.out.println("1ratio = " + ratio);

            } catch (ArithmeticException ae) {

                System.out.println("=> 1Divide by zero");

            } finally {

                System.out.println("first finally block");

            }

        } catch (InputMismatchException ime) {

            System.out.println("You did not enter a number");

            System.out.println("Trying to divide by zero");

        }

        try {

            ratio = (double) number / denom;

            System.out.println("2ratio = " + ratio);

        } catch (ArithmeticException ae) {

            System.out.println("=> 2Divide by zero");

        } finally {

            System.out.println("second finally block");

        }

    }

}
```

本章介绍了如何使用 `if-then` 语句和嵌套 `if-then` 语句进行条件逻辑处理。接下来你学习了如何与 `Date` 类工作，以及如何将字符串转换为指定格式的日期。

### 总结

本章向你介绍了使用 `if-then` 语句和嵌套 `if-then` 语句处理多重条件逻辑。接下来你学习了如何与 `Date` 类工作，以及你如何将字符串转换为指定格式的日期。

你还学习了如何处理 Unicode，并参考了一个涉及日语和中文文本字符串的示例。随后，你还对国际化（i18n）和本地化（l10n）进行了简要介绍。

然后，你看到了如何获取用户输入，以及在尝试将字符串转换为数字和小数时如何使用 `try/catch` 块和 `try/catch/finally` 块。

# 第3章

# 方法与构造函数

本章描述了可以在自定义 Java 类中定义的不同类型的方法。你还将学习在 Java 类中调用方法和访问变量的不同权限级别。此外，本章包含代码示例，说明了调用 Java 构造函数和各种方法。

第一部分介绍了 Java 类中方法和变量的公共（public）、受保护（protected）和私有（private）属性，以及这些属性如何决定其他 Java 类对给定 Java 类中变量和方法的访问权限。

本章第二部分讨论了 Java 类中的静态变量、方法和静态代码块。接下来，你将学习如何构建自定义 Java 类实例的数组。

本章第三部分包含五个 Java 代码示例，说明了在自定义 Java 类中调用构造函数的各种方法。此节还介绍了匿名内部类、Java 具名内部类和私有构造函数。

本章第四部分讨论了 Java `import` 语句，并解释了 `package` 语句的作用，以及一些展示如何使用 `package` 语句的代码示例。

本章最后一部分讨论了 JAR 文件及其用途以及如何使用 jar 工具创建 JAR 文件。

## 什么是 Java 类？

正如你在之前的代码示例所示，Java 类由方法和数据组成，对象是 Java 类的实例。对象通过 `new` 关键字创建。文件名和文件内部的类名必须相同。例如，文件 `MyClass.java` 必须包含一个名为 `MyClass` 的公共类。Java 类可以包含其他 Java 类，但 Java 也支持匿名内部类概念，这种类通常用于 GUI 控件中监听器的实现。

一个类只能通过 `extends` 关键字继承一个类；因此，Java 不支持类的多继承。然而，一个类可以通过 `implements` 关键字实现多个接口。抽象类包含至少一个必须由子类实现的方法。因此，抽象类不能被直接实例化，但实现父类抽象方法的子类是可以实例化的。

### 公共、私有还是受保护？

Java 方法可以是公共（public）、受保护（protected）或私有（private）。与其他语言不同，每个 Java 方法都是虚方法。一个类可以包含一个或多个构造函数，因为它们具有不同的签名（即参数集及其类型）。

变量也可以是公共或私有的；变量的其他关键字还包括 `static`、`final` 和 `transient`。如果变量没有初始化，Java 编译器会为其分配一个取决于其类型的值：`int` 类型的变量初始化为 0，`String` 类型的变量初始化为 `null`，依此类推。

`public` 关键字暴露属性和方法，而 `private` 关键字限制对类本身的访问。`protected` 关键字允许子类以及类本身访问该类的内部结构。

这里是一些使用 `private` 和 `public` 关键字的示例：



private `String fname = "Dave"`

public `String getName()` { return `fname`; }

public `void setName(String newName)` { `fname = newName`; }

类中的 setter（set方法）和 getter（get方法）分别是访问器（accessors）和变异器（mutators）。

### Java 变量的范围

Java 支持在类实例化期间创建的引用数据类型。

引用变量可以指向声明类型或任何兼容类型（如子类）的任何对象。

Java 中的变量有三种范围：局部、实例和静态。局部变量声明在方法、构造函数或块内部。实例变量声明在类中，它们不会出现在任何方法、构造函数或块内部。列表 3.1 显示了 `JavaVars.java` 的内容，澄清了这些类型变量之间的差异。

### 列表 3.1: JavaVars.java

```java
public class JavaVars {

    // 所有实例共享一个 x1

    public static int x1 = 10;

    // 每个实例拥有独立的 x2

    public int x2 = 20;

    public void display() {

        // 局部变量 x3 无法从其他方法访问：

        int x3 = 30;

        System.out.println("Display x1 = " + x1);

        System.out.println("Display x2 = " + x2);

        System.out.println("Display x3 = " + x3);

    }

    public static void main(String args[]) {

        JavaVars jv1 = new JavaVars();

        System.out.println("Invoking display from jv1");

        jv1.display();

        JavaVars jv2 = new JavaVars();

        jv2.x1 = 1000;

        jv2.x2 = 345;

        System.out.println("Invoking display from jv2");

        jv2.display();

        System.out.println("Invoking display from jv1");

        jv1.display();

    }

}
```

列表 3.1 定义了 `JavaVars` 类，以及静态变量 `x1`、类变量 `x2` 和局部变量 `x3`，它们分别初始化为 10、20 和 30。注意 `x3` 是局部变量，因为它定义在 `display()` 方法内部。

现在你已经了解静态、实例和局部变量之间的差异，接下来的节将提供关于静态方法的更多细节。

### 静态方法

静态变量的声明方式与实例变量相同，但带有 `static` 关键字。如果你将一个方法声明为 `static`，该方法只能更新静态变量而非非静态方法。静态方法的一个关键点是可以在不实例化对象的情况下引用静态方法。例如，代码段 `MyClass.myStaticMethod(userId)` 调用了静态方法 `myStaticMethod(userId)`，其参数 `userId` 的类型定义在 `MyClass` 类中。

相反，非静态方法只能通过类的实例可用。请记住关于静态方法的以下几点：

- 它们只能调用其他静态方法。
- 它们只能访问静态数据。
- 同一个方法出现在所有类实例中。
- 它们没有 `this` 引用。

列表 3.2 显示了 `StaticMethod.java` 的内容，说明了如何在 Java 类中定义和调用静态方法。

```java
public class StaticMethod {

  // 一个非静态方法
  public void display1() {
    System.out.println("Inside display1");
  }

  // a static method:
  public static void display2() {
    System.out.println("Inside display2");
  }

  public static void main(String args[]) {
    System.out.println("Inside main()");

    // cannot invoke non-static method:
    //StaticMethod.display1();

    // this works correctly:
    StaticMethod.display2();

    // this works correctly:
    StaticMethod sm = new StaticMethod();
    sm.display1();
  }
}
```

列表 3.2 定义了 `StaticMethod` 类、非静态方法 `display1()` 以及静态方法 `display2()`。因此，`main()` 方法可以直接调用 `display2()` 方法，而无需 `StaticMethod` 类的实例。接下来，`main()` 方法将变量 `sm` 初始化为 `StaticMethod` 类的实例，随后 `sm` 调用了方法 `display1()`，这是一个非静态方法。

### 其他静态类型

正如你在上一节中看到的，Java 类中的静态方法可以在不实例化对象的情况下被调用。此外，你可以定义一个只包含静态方法的 Java 类，每个方法都可以在不实例化对象的情况下被调用。

> 静态块（也称为静态初始化块）是一组指令，当 Java 类加载到内存时会执行一次。静态块用于在对象构造之前初始化，如下：

```java
class MyClass {

  int x;
  int y;

  // this is a static block:
  static {
    x = 123;
    System.out.println("static block executed");
  }

  public static void main(String[] args) {}
}
```

编译并运行上述类中的代码，你将看到以下输出：

```
static block executed
```

本章的下一部分将向你展示如何定义 getters 方法和 setters 方法（分别称为访问器和变异器）。

### 什么是访问器和变异器？

本质上，访问器从 "get" 方法返回一个值，而变异器在 "set" 方法中更新一个值（或多个值）。

本节的示例向你展示如何定义一个 Java 类，该类仅代表人的两个属性：名和姓，以说明如何调用此类中的其他方法。现实中的类会包含许多其他属性，在你阅读此示例后，你能够轻松地扩展此代码以实现真实的示例。

列表 3.3 显示了 `Person.java` 的内容，其中包含了用于跟踪人的姓的私有 `String` 变量，以及允许你访问任何人的名和姓的方法。

### 列表 3.3: Person.java

```java
public class Person {

    private String firstName;
    private String lastName;

    public Person(String firstName, String lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }

    public String getFirstName() {
        return(this.firstName);
    }

    public String getLastName() {
        return(this.lastName);
    }

    public static void main(String[] args) {
        Person p1 = new Person("John", "Smith");
        Person p2 = new Person("Jane", "Andrews");

        System.out.println("My name is " + 
            p1.getFirstName() + " " +
            p1.getLastName());

        System.out.println("My name is " +
            p2.getFirstName() + " " +
            p2.getLastName());
    }
}
```

列表 3.3 定义了 `Person` 类和一个 `main()` 方法，该方法将变量 `p1` 和 `p2` 初始化为 `Person` 类的实例，但在构造函数中使用不同的值。`main()` 方法的后续部分显示了 `p1` 和 `p2` 变量的内容：

```
My name is John Smith
My name is Jane Andrews
```

你可以增强列表 3.3 中的代码，读取存储在 ASCII 文件、CSV 文件、XML 文件甚至 Web 服务返回的 JSON 字符串中的姓名列表。

### 定义构造函数和访问器

在本章前面的部分，你学习了 public、private 和 protected 变量，在本节中，你将看到 Java 类中私有方法的示例。列表 3.6 显示了 `ArrayExamples3.java` 的内容，重写后包含一个构造函数和一个访问器方法。

### 列表 3.6：ArrayExamples3.java

```java
public class ArrayExamples3 {

    private int arraySize = 12;
    private int maxCelsius = 40;
    private double intSumCelsius = 0;
    private double intAvgCelsius = 0;
    private double dblSumCelsius = 0.0;
    private double dblAvgCelsius = 0.0;
    private double[] celsiusValues = new double[arraySize];
    private int[] celsiusValues2 = new int[arraySize];
    private String[] names = {"Tic", "Tac", "Toe"};

    public ArrayExamples3() {
        initializeArrays();
        calculateTotals();
        displayCelsiusResults();
        displayNames();
    }

    private void initializeArrays() {
        // initialize arrays with random values
        for (int i = 0; i < arraySize; i++) {
            celsiusValues[i] = (int) maxCelsius * Math.random();
            celsiusValues2[i] = (int) celsiusValues[i];
        }
    }

    private void calculateTotals() {
        // calculate the array sums
        for (int i = 0; i < arraySize; i++) {
            intSumCelsius += celsiusValues2[i];
            dblSumCelsius += celsiusValues[i];
        }
        dblAvgCelsius = dblSumCelsius / arraySize;
        intAvgCelsius = (int) (intSumCelsius / arraySize);
    }

    private void displayCelsiusResults() {
        System.out.println("Total Celsius: " + dblSumCelsius);
        System.out.println("Avg Celsius: " + dblAvgCelsius);
        System.out.println("Total Celsius2: " + intSumCelsius);
        System.out.println("Avg Celsius2: " + intAvgCelsius);
    }

    private void displayNames() {
        // display the contents of the names array;
        for (int i = 0; i < names.length; i++) {
            System.out.println("Name " + (i + 1) + ": " + names[i]);
        }
    }
}
```

### 访问器、变异器与 this 关键字

列表 3.7 显示了 `Employee.java` 内容，说明了如何定义访问器（也称为 "getter" 方法）和变异器（也称为 "setter" 方法）。

### 列表 3.7：Employee.java

```java
public class Employee {

    private String empid;
    private int grade;
    private double years;
```



# 方法与构造函数

```java
public Employee(String empid, int grade, double years) {
    this.empid = empid;
    this.grade = grade;
    this.years = years;
}

public String getEmpid() {
    return empid;
}

public void setEmpid(String empid) {
    this.empid = empid;
}

public int getGrade() {
    return grade;
}

public void setGrade(int grade) {
    this.grade = grade;
}

public double getYears() {
    return years;
}

public void setYears(double years) {
    this.years = years;
}

public static void main(String args[]) {
    Employee empl = new Employee("2000", 10, 5);
    System.out.println("Local empid: " + empl.getEmpid());
    System.out.println("Instance empid: none");
    System.out.println("Instance empid: " + empl.getEmpid());
    System.out.println("Grade: " + empl.getGrade());
    empl.setGrade(18);
    System.out.println("Grade: " + empl.getGrade());
}
```

```java
private int grade;
private double years;
```

```java
public Employee(String empId, int grade, double years) {
    this.empId = empId;
    this.grade = grade;
    this.years = years;
}
```

```java
public void setGrade(int grade) {
    this.grade = grade;
}
```

```java
public int getGrade() {
    return (this.grade);
}
```

```java
public ArrayEmployees Employees() {
    Employee[] empList = new Employee[3];
    String[] ids = {"1000", "2000", "3000"};
    int[] grades = {10, 11, 12};
    int[] years = {2, 3, 4};
    for (int i = 0; i < empList.length; i++) {
        empList[i] = new Employee(ids[i], grades[i], years[i]);
    }
    for (int i = 0; i < empList.length; i++) {
        Employee emp = empList[i];
        int grade = emp.getGrade();
        System.out.println("Grade emp " + (i + 1) + ": " + grade);
    }
}
```

```java
public static void main(String args[]) {
    ArrayEmployees arrEmps = new ArrayEmployees();
}
```

列表 3.8 定义了 `ArrayEmployees` 类，该类包含了 `Employee` 类的定义。现在运行列表 3.8 中的代码，你将看到以下输出：

```
Grade for emp #1: 10
Grade for emp #2: 11
Grade for emp #3: 12
```

# 66 * 开发者 Java 快速指南

注意与该类一起生成的文件：

```
ArrayEmployees.java
ArrayEmployees.class
ArrayEmployees$Employee.class
```

## 静态方法

静态方法可以直接从 Java 类进行调用，而非静态方法只能从 Java 类的实例调用。例如，如果 `staticMethod()` 是 `classB` 的静态方法，那么以下语句是合法的：

```
classB.staticMethod();
```

然而，如果 `nonStaticMethod()` 是 `classB` 的非静态方法，那么以下语句是合法的：

```java
ClassB b = new ClassB();
b.nonStaticMethod();
// 此行是非法的：
classB.nonStaticMethod();
```

类的每个实例都包含一个实例变量的副本，但所有实例共享一个静态变量的副本。如果在其中一个实例中修改了静态变量，那么修改后的值对该类的所有其他实例都可用，包括在静态变量被修改后创建的实例。如果 `x`、`y` 和 `z` 是类中的静态变量，并且它们的值被修改了，那么修改后的值在该类的所有实例中都可用。

请记住以下区别：实例变量在创建实例时初始化，而类变量在类创建时初始化。

列表 3.9 显示了 `DataTypesVars.java` 的内容，该文件包含了原始数据类型和变量。

### 列表 3.9: DataTypesVars.java

```java
public class DataTypesVars {
    // 一个静态变量
    static int club = 5;
    // 四个类变量
    int length = 4;
    int myInt = 123;
    double myDouble = 123.4;
    double total = 10.0;

    public DataTypesVars() {}

    public void calculations() {
        // 局部变量
        double dbl2 = myDouble / length;
        int myAvg = (int) (total / length);
        System.out.println("length: " + ((++length));
        System.out.println("dbl2: " + dbl2);
        System.out.println("myAvg: " + myAvg);
        System.out.println("");
    }

    public static void printClub() {
        // 访问非静态变量将导致编译错误
        System.out.println("club: " + ((++club));
    }

    public static void main(String[] args) {
        DataTypesVars.printClub();
        DataTypesVars dtvl1 = new DataTypesVars();
        dtvl1.calculations();
        DataTypesVars.printClub();
        DataTypesVars dtvl2 = new DataTypesVars();
        dtvl2.calculations();
    }
}
```

列表 3.9 定义了 `DataTypesVars` 类和一个 `main()` 方法，该方法调用静态方法 `printClub()`，该方法包含一个 `System.out` 语句用于显示 `club` 变量的自增值。`main()` 方法的下一部分将变量 `dtvl1` 初始化为 `DataTypesVars` 类的实例，然后调用 `calculations()` 方法来显示在该列表顶部定义的标量变量的值。`main()` 方法中的最后一个代码块也调用了 `calculations()` 方法并显示了变量 `dtvl2` 的值。列表 3.9 的输出如下：

```
club: 6
length: 5
dbl2: 24.6
myAvg: 2
club: 7
length: 5
dbl2: 24.6
myAvg: 2
```

注意静态变量 `club` 的值在 `dtvl1` 和 `dtvl2` 中是不同的。然而，非静态变量 `length` 在方法内部被递增。

（注：此处由于原文文本存在大量逻辑混乱和重复，翻译时已根据语意进行理顺，保留了核心技术术语与格式。）

## 第四个“HELLO WORLD”示例

列表 3.13 显示了 `HelloWorld4.java` 的内容，该程序从一个类中打印字符串“Hello World”。

### 列表 3.13: HelloWorld4.java

```java
public class HelloWorld {
    public HelloWorld() {
        System.out.println("Constructor1");
        sayHello();
    }

    public HelloWorld(int x) {
        System.out.println("Constructor2");
        sayHello();
    }

    public HelloWorld(int x, int y) {
        System.out.println("Constructor3");
        sayHello();
    }

    public void sayHello() {
        System.out.println("Hello World from HelloWorld");
    }

    public static void main(String[] args) {
        HelloWorld hw1 = new HelloWorld();
        HelloWorld hw2 = new HelloWorld(10);
        HelloWorld hw3 = new HelloWorld(10, 40);
    }
}
```

列表 3.13 定义了 `HelloWorld` 类和几个构造函数。如你所见，这些构造函数带有零或多个参数，并且每个构造函数都调用了名为 `sayHello()` 的方法，该方法包含一个 `print()` 语句。

这次，`main()` 方法包含了在以下代码块中创建三个 `HelloWorld` 类实例：

```java
HelloWorld hw1 = new HelloWorld();
HelloWorld hw2 = new HelloWorld(10);
HelloWorld hw3 = new HelloWorld(10, 40);
```

前面的代码块在不带任何参数的情况下从 `HelloWorld` 类实例化了一个名为 `hw1` 的对象，这意味着执行了空构造函数。

接下来，实例化了名为 `hw2` 的对象，这次提供了值 `10` 作为参数，这匹配了列表 3.13 中的第二个构造函数。

最后，前面的代码块使用两个参数从 `HelloWorld` 类实例化了名为 `hw3` 的对象，这匹配了列表 3.13 中的第三个构造函数。

列表 3.13 中的每个构造函数都会打印一个字符串并调用 `sayHello()` 方法，该方法会打印字符串“Hello from HelloWorld”。运行列表 3.13 中的代码，你将看到以下输出：

```
Constructor1
Hello from HelloWorld
Constructor2
Hello from HelloWorld
Constructor3
Hello from HelloWorld
```

> 注意：第二个和第三个构造函数中的参数在代码中没有使用，因为代码的目的仅仅是为了说明如何定义带有零或多个参数的构造函数。

该系列示例中的下一个代码示例说明了如何从一个构造函数调用另一个构造函数。

## 第五个“HELLO WORLD”示例

列表 3.14 显示了 `HelloWorld5.java` 的内容，该程序从一个 Java 类打印字符串“Hello World”。

### 列表 3.14: HelloWorld5.java

```java
public class HelloWorld5 {
    public HelloWorld5() {
        this(10);
        System.out.println("Constructor1");
    }

    public HelloWorld5(int x) {
        this(10, 20);
        System.out.println("Constructor2");
    }

    public HelloWorld5(int x, int y) {
        sayHello();
        System.out.println("Constructor3");
    }

    public void sayHello() {
        System.out.println("Hello World from HelloWorld5");
    }

    public static void main(String args[]) {
        HelloWorld hw1 = new HelloWorld5();
        HelloWorld hw2 = new HelloWorld5(10);
        HelloWorld hw3 = new HelloWorld5(10, 40);
    }
}
```

列表 3.14 定义了 `HelloWorld5` 类，带有多个具有零或多个参数的构造函数。注意，零参数构造函数使用 `this` 关键字来调用带一个参数的构造函数。同样，带一个参数的构造函数使用 `this` 关键字来调用带两个参数的构造函数，后者调用了包含 `print()` 语句的 `sayHello()` 方法。

`main()` 方法在以下代码块中创建了三个 `HelloWorld5` 类实例：

```java
HelloWorld hw1 = new HelloWorld5();
HelloWorld hw2 = new HelloWorld5(10);
HelloWorld hw3 = new HelloWorld5(10, 40);
```

前面的代码块与列表 3.14 `HelloWorld5.java` 中的对应代码块相同。然而，如你所见，输出是不同的（你能猜到发生了什么吗？）：

```
Hello World from HelloWorld5
Constructor3
Constructor2
Constructor1
Hello World from HelloWorld5
Constructor3
Constructor2
Hello World from HelloWorld5
Constructor3
```

再次，第二个和第三个构造函数中的参数在代码中未使用，因为代码的目的仅仅是为了说明如何定义带有零或多个参数的构造函数。

`this` 关键字出现在构造函数的 `print()` 语句（或任何其他代码）之前，否则你将看到以下错误：

```
call to this must be first statement in constructor
```

结束了关于创建 Java 类的讨论。

## 匿名内部类

内部类是在另一个类的文件中定义的类。具体来说，如果 `ClassA.java` 包含 `ClassB`，那么 `ClassB` 就是一个内部类。列表 3.15 定义了 `Regular.java` 的内容，说明了如何定义内部类。

### 列表 3.15: Regular.java

```java
public class Regular {
    class Nested {
        public Nested() {
            System.out.println("Inside constructor");
        }
    }

    class Nested2 {
        public Nested2() {
            System.out.println("Inside2 constructor");
        }
    }

    public Regular() {
        System.out.println("Inside constructor");
        Nested nest = new Nested();
        Nested2 nest2 = new Nested2();
    }

    public static void main(String args[]) {
```



System.out.println("Inside main()");

Regular reg = new Regular();

}

}

```

列表 3.15 定义了 `Regular` 类以及内部类 `Nested` 和 `Nested2`。注意后者不包含 `public` 关键字。现在编译 3.15 中的代码，你将在目录中发现以下文件：

```
Regular.java
Regular.class
Regular$Nested.class
Regular$Nested2.class
```

使用 `main()` 运行代码，你将看到以下输出：

```
Inside main()
Inside Nested constructor
```

### Java 命名内部类

列表 3.16 显示了 `Regular2.java` 的内容，说明了如何定义命名内部类（它是静态的）。

列表 3.16: Regular2.java

```java
public class Regular2
{
    // 命名内部类
    private static class Nested {
        public Nested() {
            System.out.println("Inside constructor");
        }
    }

    // 命名内部类
    private class Nested2 {
        public Nested2() {
            System.out.println("Inside2 constructor");
        }
    }

    public Regular2() {
        System.out.println("Inside Regular2 constructor");
        Nested nest = new Nested();
        Nested2 nest2 = new Nested2();
    }

    public static void main(String[] args) {
        System.out.println("Inside main()");
        Regular2 reg2 = new Regular2();
        System.out.println("Instantiating Nested inside main()");
        Nested nest = new Nested();
        // 非静态变量无法在静态文中引用：
        Nested2 nest2 = new Nested2();
    }
}
```

列表 3.16 定义了 `Regular2` 类、私有内部类 `Nested` 和私有类 `Nested2`。现在运行代码，你将看到以下输出：

```
Inside main()
Inside Regular2 constructor
Inside Nested constructor
Inside Nested2 constructor
Instantiating Nested inside main()
Inside Nested constructor
```

### 匿名类与命名内部类的对比

如你所知，Java 类可以扩展一个类并实现任意数量的接口。相比之下，匿名内部类只能实现一个接口。此外，匿名内部类是私有的（即其他公共类无法访问它们），而命名内部类只能被封闭类使用。

小心不要无意中将命名内部类与在多个处使用的类（这种情况不太可能发生）误认为是匿名类。建议，当它们只使用一次时（例如 GUI 中按钮点击的事件处理器），使用匿名内部类；如果它们在代码中被多次使用，则使用命名内部类。Java 中的匿名类可以具有如下初始化器：

```java
{
    super.foo(finalVariable + this.bar);
}
```

### 匿名类的局限性

虽然匿名类有一些优势，但它们也有局限性，如下所示：

- 它们无法被重用
- 它们的定义中不能包含任何静态内容
- 它们的字段无法在 Eclipse 中检查
- 它们不能作为类型使用
- 无法在 Eclipse 中使用类名定位
- 它们没有名称，因此不能有构造函数
- 它们不能更改任何包含的类成员的值

相比之下，命名内部类没有上述局限性。顺便说，这里有一个非静态内部类可能会出现问题的场景：当外部类不是可序列化的，而内部类是可序列化的。在这种情况下，将尝试序列化外部类，但会失败（因此将花费更多时间来调试代码）。

由于匿名类没有构造函数，你如何将非构造函数变量从 B 传递给 A，其中 B 是 A 的子类？一种可能性涉及使用（静态）命名内部类。

### 列表 3.17：SingleInstance.java

```java
class PrivateConstructor {
    static PrivateConstructor instance = null;
    public int prime = 37;

    // 私有构造函数在类外部不可访问
    private PrivateConstructor() {}

    // 用于构造实例的方法：
    static public PrivateConstructor getInstance() {
        // 仅创建一次实例：
        if (instance == null) {
            instance = new PrivateConstructor();
        }
        return instance;
    }
}

public class SingleInstance {
    public SingleInstance() {}
    public static void main(String[] args[]) {
        PrivateConstructor inst1 = PrivateConstructor.getInstance();
        PrivateConstructor inst2 = PrivateConstructor.getInstance();
        System.out.println("Before update:");
        System.out.println("Value of inst1.prime = " + inst1.prime);
        System.out.println("Value of inst2.prime = " + inst2.prime);
        inst1.prime = inst1.prime + 64;
        System.out.println("After update:");
        System.out.println("Value of inst1.prime = " + inst1.prime);
        System.out.println("Value of inst2.prime = " + inst2.prime);
    }
}
```

列表 3.17 定义了内部类 `PrivateConstructor`，它包含一个私有构造函数，其中变量 `instance` 的初始值为 `null`。变量 `instance` 仅初始化一次，这确保了 `PrivateConstructor` 类只有一个实例。

列表 3.17 还定义了 `SingleInstance` 类、一个公共构造函数以及一个 `main()` 方法，该方法将变量 `inst1` 和 `inst2` 初始化为 `PrivateConstructor` 类的实例。

接下来，两个 `print()` 语句显示了整数变量 `prime`（`PrivateConstructor` 类中的一个公共变量）的值，其初始值为 37。实例变量 `inst1` 和 `inst2` 的变量 `prime` 值均为 37。

`main()` 方法的下一部分将变量 `prime` 的值加了 64，并通过两个 `print()` 语句显示其更新后的值。运行列表 3.17 中的代码，你将看到以下输出：

```
Before update:
Value of inst1.prime = 37
Value of inst2.prime = 37
After update:
Value of inst1.prime = 101
Value of inst2.prime = 101
```

### JAVA import 语句

你可以使用 `import` 语句将 Java 类导入到你的 Java 类中。例如，假设文件 `MyClass.java` 在包 `com.acme.dept` 中，并且你想导入包为 `com.acme.employees` 的 `Employee` 类。`MyClass.java` 文件必须出现在以下目录结构中：

```
<your-top-directory>.com/acme/dept/MyClass.java
```

`MyClass.java` 将包含以下代码：

```java
package com.acme.dept;
import com.acme.employees.Employee;
public class MyClass extends MyBase implements BaseInfo {
    private Employee emp;
    // 代码在此处
}
```

前面的代码块包含了对导入的 `Employee` 类的引用，因为你可能要在 `MyClass` 类中对该类进行某些操作。

你可以导入属于某个包的所有 Java 类。例如，以下 `import` 语句导入了 `com.acme.employees` 包中的所有类：

```
import com.acme.employees.*;
```

编译器将只导入你的代码所需的 Java 类，因此你可以使用通配符语句或包中特定的显式 Java 类。然而，在许多情况下，显式地导入程序所需的 Java 类可能比依赖编译器是更好的编码实践。

### JAVA package 语句

Java 支持在其他语言（如 Ada）中可用的包（package）构造结构。请注意，包名必须作为 Java 文件的第一个非注释行出现。包是一种区分出现在多个位置的同名 Java 文件的方便方法。此功能类似于 XML 中命名空间（namespaces）的使用。

例如，假设你现在 `com.acme.employees` 包中有一个名为 `Employee` 的 Java 文件，在 `com.acme.dept` 包中有一个第二个名为 `Employee` 的 Java 文件，在 `com.acme.employees.internal` 包中有一个第三个名为 `Employee` 的文件。这些文件必须出现在以下目录结构中：

```
<your-top-directory>.com/acme/employees/Employee.java
<your-top-directory>.com/acme/dept/Employee.java
<your-top-directory>.com/acme/employees/internal/Employee.java
```

每个 `Employee` 文件将包含类似的代码：

```java
package com.acme.employees;
public class Employee {
    // 代码在此处
}
```

```java
package com.acme.dept;
public class Employee {
    // 代码在此处
}
```

```java
package com.acme.employees.internal;
public class Employee {
    // 代码在此处
}
```

包的使用允许你有同名的类，只要它们位于不同的包中。要使用这些类，你必须导入它们或使用它们的全限定名。



```java
private Employee emp;

// 代码在此处

}
```

前面的代码块包含了对导入的 `Employee` 类的引用，因为你可能要在 `MyClass` 类中对该类进行某些操作。

你可以导入属于某个包的所有 Java 类。例如，以下 `import` 语句导入了 `com.acme.employees` 包中的所有类：

```java
import com.acme.employees.*;
```

编译器将只导入你的代码所需的 Java 类，因此你可以使用通配符语句或包中特定的显式 Java 类。然而，在许多情况下，显式地导入程序所需的 Java 类可能比依赖编译器是更好的编码实践。

## JAVA package 语句

Java 支持在其他语言（如 Ada）中可用的包（package）构造结构。请注意，包名必须作为 Java 文件的第一个非注释行出现。包是一种区分出现在多个位置的同名 Java 文件的方便方法。此功能类似于 XML 中命名空间（namespaces）的使用。

例如，假设你现在在 `com.acme.employees` 包中有一个名为 `Employee` 的 Java 文件，在 `com.acme.dept` 包中有一个第二个名为 `Employee` 的 Java 文件，在 `com.acme.employees.internal` 包中有一个第三个名为 `Employee` 的文件。这些文件必须出现在以下目录结构中：

```
<your-top-directory>.com/acme/employees/Employee.java
<your-top-directory>.com/acme/dept/Employee.java
<your-top-directory>.com/acme/employees/internal/Employee.java
```

每个 `Employee` 文件将包含类似的代码：

```java
package com.acme.employees;

public class Employee {

    // 代码在此处

}
```

```java
package com.acme.dept;

public class Employee {

    // 代码在此处

}
```

```java
package com.acme.employees.internal;

public class Employee {

    // 代码在此处

}
```

包的使用允许你有同名的类，只要它们位于不同的包中。要使用这些类，你必须导入它们或使用它们的全限定名。

## 包语句的一个示例 (2)

前一节中的 Java 类 `LongEmployee` 将重构为四个 Java 类：`Employee.java`、`EmpDetails.java`、`Person.java` 和 `Address.java`，它们都属于同一个包。在这个示例中，`Employee` 实体包含一个 `EmpDetails` 实体、一个 `Person` 实体和一个 `Address` 实体。因此，`Employee` 实体与其他实体之间是一一对的关系。然而，`Employee` 实体与 `Address` 实体建立一对多的关系也是可能的。

请记住，重构后的代码行数比 `LongEmployee` 类稍长。但是，你可以对每个“较小”的类进行独立的单元测试，这使得更容易发现并修复代码中的错误。此外，与重构后的类比单一的单体类 `LongEmployee` 更容易重用。

列表 3.19 显示了属于 `com.employees` 包的 `Employee.java` 内容。

### 列表 3.19: Employee.java

```java
package com.employees;

public class Employee {

    private Person person;

    private Address address;

    private EmpDetails empDetails;

    private String firstName;

    private String lastName;

    private String street;

    private String city;

    private String state;

    private String empId;

    private int grade;

    private double years;

    public Employee(String firstName, String lastName, String street, String city, String state, String empId, int grade, double years) {

        this.firstName = firstName;
        this.lastName = lastName;
        this.person = new Person(firstName, lastName);
        this.street = street;
        this.city = city;
        this.state = state;
        this.address = new Address(street, city, state);
        this.empId = empId;
        this.grade = grade;
        this.years = years;
        this.empDetails = new EmpDetails(empId, grade, years);
    }

    public Person getPerson() {
        return this.person;
    }

    public Address getAddress() {
        return this.address;
    }

    public EmpDetails getEmpDetails() {
        return this.empDetails;
    }

    public void printDetails() {
        person = this.getPerson();
        address = this.getAddress();
        empDetails = this.getEmpDetails();
        System.out.println("First Name: " + person.getFirstName());
        System.out.println("Last Name: " + person.getLastName());
    }

    public static void main(String args[]) {
        Employee e1 = new Employee("John", "Smith", "1234 Main St", "Chicago", "IL", "2000", 10, 5);
        Employee e2 = new Employee("Jane", "Andrews", "1234 Oak Ave", "Newport", "CA", "2000", 10, 5);
        e1.printDetails();
        e2.printDetails();
    }
}
```

列表 3.19 包含一个包语句三个新类：

```java
private Person person;
private Address address;
private EmpDetails empDetails;
```

列表 3.19 的下部分包含了在 `LongEmployee` 中声明的八个私有变量。接下来，构造函数接收八个参数并执行若干初始化。然而，此初始化块还实例化了三个对象。具体来说，以下代码段实例化了类型为 `Person` 的对象 `person`：

```java
this.person = new Person(firstName, lastName);
```

下一个代码段实例化了类型为 `Address` 的对象 `address`：

```java
this.address = new Address(street, city, state);
```

第三个代码段实例化了类型为 `EmpDetails` 的对象 `empDetails`：

```java
this.empDetails = new EmpDetails(empId, grade, years);
```

列表 3.20 显示了属于 `com.employees` 包的 `EmpDetails.java` 内容。

### 列表 3.20: EmpDetails.java

```java
package com.employees;

public class EmpDetails {

    private String empId;
    private int grade;
    private double years;

    public EmpDetails(String empId, int grade, double years) {
        this.empId = empId;
        this.grade = grade;
        this.years = years;
    }

    public void setGrade(int grade) {
        this.grade = grade;
    }

    public int getGrade() {
        return this.grade;
    }

    public double getYears() {
        return this.years;
    }
}
```

# 循环、数组与递归

本章包含了涉及 Java 中 `for` 循环、`while` 循环、数组和递归的各种代码示例。

本章的第一部分包含 `for` 循环和 `while` 循环的 Java 代码示例。尽早引入这些构造是因为更有用的代码示例通常包含循环和条件逻辑的组合。

本章的第二部分包含处理字符串的 Java 代码，例如反转字符串以及将字符串转换为大写和小写。该部分还展示了如何处理嵌套循环。

本章的最后一部分将展示如何使用递归来计算阶乘、斐波契数、两个正整数的最大公约数（GCD）以及两个正整数的最小公倍数（LCM）。

虽然你可能不需要在日常任务中实现欧几里得算法，但它提供了一种计算两个数字最大公约数的优雅方法，且代码是递归的一个极佳示例。不过，你可以跳过这一节而不影响内容的连续性。当你准备好处理递归时，可以随时回到本章的这里。

## 使用 FOR 循环

列表 4.1 显示了 `ForLoops1.java` 的内容，该程序遍历一组数字并打印它们的值。

### 列表 4.1：ForLoops1.java

```java
public class ForLoops1 {

    private int maxCount = 8;
    private double sum1 = 0;

    public ForLoops1() { }

    public void calculateAverage() {
        for(int i=0; i<maxCount; i++) {
            sum1 += i;
            System.out.println("Partial sum: " + sum1);
        }

        double avg = sum1/maxCount;
        System.out.println("Total: " + sum1);
        System.out.println("Average: " + avg);
    }

    public static void main(String args[]) {
        ForLoops1 fl1 = new ForLoops1();
        fl1.calculateAverage();
    }
}
```

列表 4.1 定义了类 `ForLoops1` 为 `ForLoops1` 类的一个实例。接下来，调用了 `calculateAverage()` 方法（属于 `ForLoops1` 类），它通过一个简单的循环开始计算 1 到 `maxCount` 之间的数字之和。`calculateAverage()` 方法的最后部分计算这组数字的平均值，并打印总和和平均数。列表 4.1 的输出如下：

```
Partial sum: 0.0
Partial sum: 1.0
Partial sum: 3.0
Partial sum: 6.0
Partial sum: 10.0
Partial sum: 15.0
Partial sum: 21.0
Partial sum: 28.0
Total: 28.0
Average: 3.5
```

## 判断闰年

列表 4.2 显示了 `LeapYear.java` 的内容，用于判断一个正整数是否为闰年。闰年是 4 的倍数，但排除不是 400 倍数的世纪。根据前面的定义，1700、1800 和 1900 不是闰年，而 2000 是闰年。

本节的代码示例具有很好的特性。首先，条件逻辑很好地说明了嵌套条件语句的用处。其次，注意到闰年的定义在列表 4.2 中仅用两行注释描述，而实现这两行注释需要 40 行代码。第三，该代码示例说明了清晰理解任务的重要性，这将使得你的代码逻辑更容易于实现和调试。

如果你对测试自己的编程技能感兴趣，可以编写自己的判断闰年代码，并将其与列表 4.2 的内容进行比较。

### 列表 4.2：LeapYear.java

```java
public class LeapYear {

    public LeapYear() {}

    // 闰年是4的倍数，
    // 除非不是400倍数的世纪

    public void checkYear(int year) {
        if(year % 4 == 0) {
            if(year % 100 == 0) {
                if(year % 400 == 0) {
                    System.out.println(year + " is a leap year");
                }
            } else {
                System.out.println(year + " is not a leap year");
            }
        } else {
            System.out.println(year + " is not a leap year");
        }
    }

    public static void main(String[] args[]) {
        LeapYear ly = new LeapYear();
        int[] years = {1234, 1900, 2000, 2020, 3000, 5588};
        for (int year : years) {
            ly.checkYear(year);
        }
    }
}
```

列表 4.2 定义了类 `LeapYear`，其中包含一个判断正整数是否为闰年的 `checkYear()` 方法。查看列表 4.2 开头的注释块，你会发现 `checkYear` 方法实现了相同的逻辑。运行列表 4.2 中的代码，你将看到输出：

```
1234 is not a leap year
1900 is not a leap year
2000 is a leap year
2020 is a leap year
3000 is not a leap year
5588 is a leap year
```

## 整数循环

对于本节的 Java 代码，记住 `int` 类型变量有对应的字符串。列表 4.3 展示了如何将整数值转换为字符串。

### 列表 4.3：MyIntegers.java

```java
public class MyIntegers {

    public static void main(String[] args) {
        int[] myInts = {1, 2, 3, 4, 5};
        for (int i = 0; i < myInts.length; i++) {
            System.out.println("Integer: " + myInts[i]);
        }
    }
}
```

列表 4.3 使用增强 for 循环来遍历整数数组。增强 for 循环提供了更简单的数组遍历语法。

## 检查回文

回文是指正反读（例如从左到右）相同的数字或字符序列。例如，字符串 "Bob" 是回文，但 "1234" 不是。列表 4.4 显示了 `Palindromes.java` 的内容，检查指定的字符串或数字是否为回文。

### 列表 4.4：Palindromes.java

```java
public class Palindromes {

    public Palindromes() {}
```



```java
public void check(String str) {

    int result = 0;

    int len = str.length();

    for (int i = 0; i < len / 2; i++) {

        if (str.charAt(i) != str.charAt(len - 1 - i)) {

            result = 1;

            break;

        }

    }

    if (result == 0) {

        System.out.println(str + " is a palindrome");

    } else {

        System.out.println(str + " is not a palindrome");

    }

}

public static void main(String[] args) {

    String[] names = {"Dave", "BobB", "radar", "rotor"};

    int[] numbers = {1234, 767, 1234321, 101};

    Palindromes pall = new Palindromes();

    for (String name : names) {

        pall.check(name);

    }

    for (int num : numbers) {

        pall.check(Integer.toString(num));

    }

}
```

列表 4.4 定义了类 `Palindromes`，其中包含一个判断字符串是否为回文的 `check()` 方法。`main()` 方法定义了数组 `names` 和数组 `numbers`。接下来，`main()` 方法实例化 `Palindromes` 类，然后用 `names` 数组中的每个字符串调用 `check()` 方法。同样，通过 `Integer.toString()` 方法将数值转换为字符串，用 `numbers` 数组中的每个数字调用该方法。

### 嵌套循环

列表 4.5 显示了 `Triangular1.java` 的内容，该程序遍历一组数字并以三角形打印它们的值。

### 列表 4.5：Triangular1.java

```java
public class Triangular1 {

    private int maxCount1 = 8;

    private double sum1 = 0;

    public Triangular1() {}

    public void nestedLoop() {

        for(int i=2; i<maxCount1; i++) {

            for(int j=1; j<i; j++) {

                System.out.print(j);

            }

            System.out.println();

        }

    }

    public static void main(String args[]) {

        Triangular1 fl1 = new Triangular1();

        fl1.nestedLoop();

    }

}
```

列表 4.5 定义了 `Triangular` 类，该类包含 `nestedLoop()` 方法，用于显示三角形的数字。

`nestedLoop()` 方法包含一个外层循环，其循环变量遍历从 2 到 `maxCount` 的数字，以及一个循环变量 `j` 遍历 1 到 `i` 的内层循环。对于外层循环中的每个 `i` 值，内层循环显示一行数字，所示：

+   1
12
123
1234
1235
123456

### 哥德巴赫猜

哥德巴赫猜指出，每一个大于 4 的偶数都可以表示为两个质数之和。例如，12 = 5 + 7，14 = 3 + 11，14 = 7 + 7，22 = 5 + 17，以及 22 = 11 + 11，这说明某些偶数可以表示为多组质数之和。本节中的代码示例将验证 6 到 50 之间偶数的哥德巴赫猜。

列表 4.6 显示了 `GoldbachConjecture.java` 的内容，它寻找所有之和等于偶数的质数对。

### 列表 4.6：GoldbachConjecture.java

```java
public class GoldbachConjecture {

    int PRIME = 1;

    int COMPOSITE = 0;

    public GoldbachConjecture() {}

    public int prime(int num) {

        int div = 2;

        while (div < num) {

            if(num % div != 0) {

                ++div;

            } else {

                return COMPOSITE;

            }

        }

        return PRIME;

    }

}

public void findPrimeFactors(int evenNum) {

    for (int num=3; num<=evenNum/2; num+=1) {

        if(this.prime(num) == 1 && (this.prime(evenNum-num) == 1)) {

            System.out.println(evenNum + " = " + num + " + " + (evenNum-num));

        }

    }

}

static void main(String args[]) {

    int upperBound = 30;

    GoldbachConjecture gbach = new GoldbachConjecture();

    for (int num=4; num<=upperBound; num+=2) {

        gbach.findPrimeFactors(num);

    }

}
```

列表 4.6 包含一个判断数字是否为质数的方法。`findPrimeFactors` 方法将找到所有质数且之和等于给定数字的整数对，在这种情况下，该数字是变量 `evenNum` 的值。核心思想是：如果 `x` 和 `evenNum` 都是质数，那么这两个数就满足数字 `evenNum` 的哥德巴赫猜。列表 4.6 的输出如下：

```
6 = 3 + 3
8 = 3 + 5
10 = 3 + 7
10 = 5 + 5
12 = 5 + 7
14 = 3 + 11
16 = 7 + 7
16 = 3 + 13
16 = 5 + 11
18 = 5 + 13
20 = 3 + 17
20 = 7 + 13
22 = 3 + 19
22 = 5 + 17
22 = 11 + 11
24 = 5 + 19
24 = 7 + 17
24 = 11 + 13
26 = 3 + 23
26 = 7 + 19
26 = 13 + 13
28 = 5 + 23
28 = 11 + 17
30 = 7 + 23
30 = 11 + 19
30 = 13 + 17
```

### 基础循环的变体

之前包含 `for` 循环的代码示例具有相同的结构：初始化、逻辑测试和增量。本节向你展示了一些可能有用的变体。代码示例非常简洁：大多数它们没有循环体，虽然几个代码片段是显而易见的，但其中一些可能需要你编写一些代码来确定它们的输出。

将 `i` 从 5 递减到 0：

```java
for (int i=5; i>=0; i--) { ... }
```

在 `for` 循环内部递增（从 0 到 5）：

```java
for (int i=0; i<=5;);
{
  i++;
}
```

在 `for` 循环之前初始化：

```java
int i=0;
for(; i < 5; i++) { ... }
```

初始化 `i` 和 `j`，递增 `i` 并递减 `j`：

```java
for(i=0, j=5; i<j; i--) { ... }
```

“无限”循环（用于用户输入）：

```java
for(); { ... }
```

下面的 `print()` 语句是无效的：

```java
for(int i=0; i<5; i++)
System.out.println(":i: " +i)
System.out.println(":i: " +i)
```

带有 `break` 语句的 `for` 循环：

```java
for (int i=0; i<=5; i++)
{
  if(i == 3) break;
  System.out.println(":i: " +i)
}
```

带有 `continue` 语句的 `for` 循环：

```java
for (int i=0; i<=5; i++)
{
  if(i == 3) continue;
  System.out.println("i: "+i);
}
```

带有 `break` 和 `continue` 语句的嵌套循环：

```java
for (int i=0; i<=5; i++) {
  if (i == 3) continue;
  for (int j=0; j<=5; j++) {
    if (j == 3) break;
    System.out.println("i: "+i" j: "+j);
  }
}
```

你可以想象，在使用这些块时很容易意外引入 Bug：只有在必要时使用它们。

### 使用 WHILE 循环

选择 `for` 循环还是 `while` 循环取决于你的喜好；有时 `while` 循环更清晰。列表 4.7 显示了 `WhiteLoops.java` 的内容，它遍历一组数字并打印它们的值。

### 列表 4.7：WhiteLoops.java

```java
public class WhiteLoops {

  private int maxCount = 8;

  private double sum1 = 0;

  public WhiteLoops() {}

  public void calculateAverage() {

    int i=0;

    while(i<maxCount) {

      sum1 += i;

      i++;

    }

    double avg = sum1/maxCount;

    System.out.println("Average: "+avg);

  }

  public static void main(String args[]) {

    WhiteLoops wll = new WhiteLoops();

    wll.calculateAverage();

  }

}
```

```java
case 4: theMonth = "May";
    break;
default: theMonth = "After May";
    break;
}
System.out.println("Month: "+theMonth);
```

列表 10 定义了 `Switch` 类，其 `main()` 方法包含一个 `switch()` 语句，该语句将整数变量 `month` 的值与其对应的月份进行“匹配”。具体而言，值 0 代表一月，值 1 代表二月，依此类推，直到值 11 对应 12 月。运行列表 4.10 中的代码，你将看到以下输出：

Month: after May

## JAVA 数组

Java 数组包含相同类型的元素，这些元素可以是基本类型，也可以是对象。常见操作包括 `append()` 和 `remove()`，它们分别允许你添加和删除元素。以下是一些数组操作和属性：

- 初始化
- 迭代
- 长度
- 单维/多维
- 排序
- 可变参数参数
- ArrayIndexOutOfBoundsException

列表 4.11 显示了 `SimpleArray.java` 的内容，说明了如何执行简单的数组操作。

### 列表 4.11: SimpleArray.java

```java
import java.lang.ArrayIndexOutOfBoundsException;

public class SimpleArray
{
    public SimpleArray() {
    }

    public static void main(String[] args) {
        int index = 5;
        int[] numbers = {3, 5, 19, -123};
        System.out.println("length: " +numbers.length);
        System.out.print("numbers: "");
    }
}
```

```java
for(int num : numbers) {
    System.out.print(num+" ");
    System.out.println("");
}

try {
    System.out.print("index "+index+": " +
    numbers[index]);
} catch (ArrayIndexOutOfBoundsException aiob) {
    System.out.println("Index "+index+": exceeds "
    ""numbers.length+");");
}
```

列表 4.11 定义了 `SimpleArray` 类以及一个用四个数字初始化数值型数组的 `main()` 方法。`main()` 方法的后续部分包含一个 `for` 循环，用于显示 `numbers` 数组的内容。

`main()` 方法的最后部分包含一个 `try/catch` 代码块，代码尝试访问 `numbers` 数组最后一个元素之后的元素。此外，最后一个代码块抛出了一个在 `catch` 块中处理的异常。运行列表 4.11 中的代码，你将看到以下输出：

```
length: 4
numbers: 3 5 19 -123
Index 5 exceeds 4
```

## 数字数组

Java 数组包含相同类型的元素，这些元素可以是基本类型或对象（必须是相同类型）。创建 Java 数组的一种方法是声明数组变量并在同一行代码中初始化数组。以下是一个示例：

```java
private String[] letters = {"a", "b", "c"};
```

另一种方法涉及声明一个数组变量，然后使用循环来填充数组变量的元素：

1. 声明一个变量来存放数组值。
2. 创建一个新的数组对象并将其赋值给数组变量中的一个元素。
3. 重复步骤 2 直到数组填满。

以下代码段分别声明了元素为 `String`、`double`、`int` 和 `MyClass` 的数组：

- `String wordlist[];`
- `double prices[];`
- `int intValues[];`
- `MyClass myClasses[];`

书中使用的另一种等效方法在此所示：

- `String[] wordList;`
- `double[] prices;`
- `int[] intValues;`
- `MyClass[] myClasses;`

列表 4.12 显示了 `Arrays1.java` 的内容，说明了如何声明数组并初始化数组的元素。

### 列表 4.12: Arrays1.java

（注：此处代码块在原文中不完整，未翻译代码内部逻辑）...

### 冒泡排序算法

冒泡排序是一种著名的排序算法。列表 4.13 显示了 `BubbleSort.java` 的内容，说明了如何按升序对数字数组进行排序。

### 列表 4.13: BubbleSort.java

```java
public class BubbleSort {

    public BubbleSort() {

    public void sortNumbers() {

        int[] numbers = {-3, 50, 10, 5, 20, 300, -200};

        System.out.println("Original array:");

        for (int i=0; i<numbers.length; i++) {

            System.out.print(numbers[i]+" ");

        }

        System.out.println();

        for(int i=0; i<numbers.length-1; i++) {

            for(int j=i+1; j<numbers.length; j++) {
```



```java
if (numbers[i] > numbers[j]) {
    int temp = numbers[i];
    numbers[i] = numbers[j];
    numbers[j] = temp;
}
```

列表 4.13 定义了 `BubbleSort` 类，将变量 `bs` 初始化为 `BubbleSort` 类的实例并调用 `sortNumbers()` 方法。

该方法包含一个嵌套循环，用于遍历包含整数值的 `numbers` 数组的元素。给定一个索引位置 `i`，代码检查大于 `i` 的索引位置的内容。如果这些位置之一（我们称为位置 `j`）的数组值大于索引 `i` 处的数组值，则交换数组元素 `numbers[i]` 和 `numbers[j]`（使用整数 `temp` 作为临时值）。运行列表 4.13 中的代码，你将看到以下输出：

```
Original array:
-3 50 10 5 20 300 -200
Sorted array:
-200 -3 5 10 20 50 300
```

## JAVA 多维数组

除了一维数组外，Java 还支持多维数组。列表 4.14 显示了 `MultiDimArrays.java` 的内容，说明了如何初始化二维数组。

列表 4.14 的输出如下：

```
(0,0): 0.0
(0,1): 5.0
(0,2): 10.0
(0,3): 15.0
(1,0): 5.0
(1,1): 10.0
(1,2): 15.0
(1,3): 20.0
(2,0): 10.0
(2,1): 15.0
(2,2): 20.0
(2,3): 25.0
(3,0): 15.0
(3,1): 20.0
(3,2): 25.0
(3,3): 30.0
Total Sum: 240.0
Avg Value: 15.0
```

## JAVA 多维数组 (2)

列表 4.15 显示了 `MultiDimArrays2.java` 的内容，展示了如何初始化二维数组和三维数组。

### 列表 4.15: MultiDimArrays2.java

```java
public class MultiDimArrays2 {

    public MultiDimArrays2() {
    }

    public void array1D() {
        // 声明/初始化一个一维数组：
        int arr1[] = {1,2,3,4,5,6,7,8,9};
        System.out.println("Contents of 1D array:");
        for(int i=0; i<9; i++) {
            System.out.print(arr1[i] + " ");
        }
        System.out.println();
    }

    public void array2D() {
        // 声明/初始化一个二维数组：
        int arr2[][] = {{1,2,3}, {4,5,6}, {7,8,9}};
        System.out.println("Contents of 2D array:");
        for(int i=0; i<3; i++) {
            for(int j=0; j<3; j++) {
                System.out.print(arr2[i][j] + " ");
            }
            System.out.println();
        }
    }

    public void array3D() {
        // 声明/初始化一个三维数组；
        int arr3[][][] = {
            {{1,2,3}, {4,5,6}, {7,8,9}},
            {{11,12,13}, {14,15,16}, {17,18,19}},
            {{21,22,23}, {24,25,26}, {27,28,29}}
        };
        System.out.println("Contents of 3D array");
        for(int i=0; i<3; i++) {
            for(int j=0; j<3; j++) {
                for(int k=0; k<3; k++) {
                    System.out.print(arr3[i][j][k] + " ");
                }
                System.out.println();
            }
            System.out.println();
        }
    }

    public static void main(String args[]) {
        MultiDimArrays2 mda2 = new MultiDimArrays2();
        mda2.array1D();
        mda2.array2D();
        mda2.array3D();
    }
}
```

列表 4.15 定义了 `MultiDimArrays2` 类，它将变量 `mda2` 初始化为 `MultiDimArrays2` 类的实例。接下来，`array1D()` 方法定义并初始化了一个一维数组，随后通过一个循环打印该数组的值。

接下来，`array2D()` 方法定义并初始化了一个二维数组，随后通过一个嵌套循环打印该数组的值。同样，`array3D()` 方法定义并初始化了一个三维数组，随后通过一个三重嵌套循环打印该数组的值。列表 4.15 的输出为：

```
Contents of 1D array:
1 2 3 4 5 6 7 8 9
Contents of 2D array:
1 2 3
4 5 6
7 8 9
Contents of 3D array:
1 2 3
4 5 6
7 8 9
11 12 13
14 15 16
17 18 19
21 22 23
24 25 26
27 28 29
```

## 处理字符与字符串

列表 4.16 显示了 `DisplayChars.java` 的内容，说明了如何打印字符串中的字符，以及关于字符（数字、大写、小写或空格）的信息。

### 列表 4.16: DisplayChars.java

```java
public class DisplayChars {

    public static void main(String args[]) {
        char chr, up, lwr;
        String line = "Some text";
        String lower = line.toLowerCase();
        String upper = line.toUpperCase();
        System.out.println("Line: " + line);
        System.out.println("Length: " + line.length() + "\n");
        for (int i=0; i < line.length(); i++) {
            chr = line.charAt(i);
            lwr = lower.charAt(i);
            up = upper.charAt(i);
            if (chr == ' ') {
                System.out.println("Character is a space");
            } else if (Character.isDigit(chr)) {
                System.out.println("Character is a digit");
            } else if (Character.isUpperCase(chr)) {
                System.out.println("Character is uppercase");
            } else if (Character.isLowerCase(chr)) {
                System.out.println("Character is lowercase");
            }
            System.out.println("Character: " + chr);
        }
    }
}
```

列表 4.16 定义了 `DisplayChars` 类，其 `main()` 方法包含一个循环，遍历 `line` 字符串中的字符。循环内部使用 `if-else if` 结构判断字符是否为空格、数字、大写或小写字母，并打印相应的信息。列表 4.16 的输出如下：

```
Line: Some text
Length: 9
Character is uppercase
Character: S
Character is lowercase
Character: o
Character is lowercase
Character: m
Character is lowercase
Character: e
Character is a space
Character:  
Character is lowercase
Character: t
Character is lowercase
Character: e
Character is lowercase
Character: x
```

## STRINGBUFFER 和 STRING 类

回想一下 `String` 类创建一个不可变的字符序列，对于大字符串，这可能会消耗大量的内存。`StringBuilder` 类是 `String` 类的替代方案，它支持可变的字符序列。

`StringBuilder` 类有许多有用方法，每个方法的返回类型都是 `StringBuilder`，如下所示：

- `capacity()`
- `charAt()`
- `delete()`
- `codePointAt()`
- `codePointBefore()`
- `codePointCount()`
- `deleteCharAt()`
- `ensureCapacity()`
- `getChars()`
- `length()`
- `replace()`
- `reverse()`
- `subSequence()`

`StringBuffer` 类与 `StringBuilder` 类相似。尽管它们都通过创建可变字符序列提供了 `String` 类的替代方案，但它们在同步方面具有不同的行为。

`StringBuilder` 类不是线程安全的，而 `StringBuffer` 类保证同步。因此，如果你需要线程安全的代码，请使用 `StringBuffer` 类；如果你的代码是单线程的，请使用 `StringBuilder` 类，因为它在大多数情况下会更快。

### 使用 StringBuilder 和 StringBuffer 类的 Java 示例

列表 4.20 显示了 `ReverseString.java` 的内容，它使用 `StringBuilder` 类和 `StringBuffer` 类来反转字符串。

### 列表 4.20: ReverseString.java

```java
public class ReverseString {

    private int maxCount1 = 8;
    private double sum = 0;

    public ReverseString() {}

    public void reverse(String str) {
        System.out.println("Original: " + str);
        int strlen = str.length();
        char[] strArray = str.toCharArray();
        for (int i=0; i<strlen/2; i++) {
            char temp = strArray[i];
            strArray[i] = strArray[strlen-1-i];
            strArray[strlen-1-i] = temp;
        }
        System.out.println("Reversed: " + String.valueOf(strArray));

        char[] strArray2 = new char[str.length()];
        for (int i=0; i<strlen/2; i++) {
            char temp = str.charAt(i);
            strArray2[i] = str.charAt(strlen-1-i);
            strArray2[strlen-1-i] = temp;
        }
        System.out.println("Reversed1: " + String.valueOf(strArray2));
    }

    public void reverse2(String str) {
        String reversed = "";
        for(int i=str.length()-1; i>=0; i--) {
            reversed += str.charAt(i);
        }
        System.out.println("Reversed2: " + reversed);
    }

    public void reverse3(String str) {
        StringBuilder reversed = new StringBuilder(str);
        System.out.println("Reversed3: " + reversed.reverse());
    }

    public void reverse4(String str) {
        StringBuilder reversed = new StringBuilder();
        for(int i=str.length()-1; i>=0; i--) {
            reversed.append(str.charAt(i));
        }
        System.out.println("Reversed4: " + reversed);
    }

    public static void main(String[] args) {
        ReverseString rs = new ReverseString();
        rs.reverse("abcd");
        rs.reverse2("abcd");
        rs.reverse3("abcd");
        rs.reverse4("abcd");
    }
}
```

列表 4.20 定义了 `ReverseString` 类，它包含了四个可以反转字符串的方法。`reverse()` 方法包含两个循环，使用临时变量交换字符数组中的元素，从最左和最右的字符对开始，向字符变量 `strArray` 的中间点移动，第一个循环交换 `strArray` 中的字符，该数组初始化的大小足够容纳参数字符串变量 `str` 中的字符。

`reverse2()` 方法包含一个反向的循环，将参数 `str` 的字符从右向左（使用 `+=` 运算符）附加到字符串变量 `reversed`，之后该变量将包含 `str` 的反转字符。

`reverse3()` 方法使用 `StringBuilder.reverse()` 方法。

`reverse4()` 方法使用循环按反序添加字符。

## 循环、数组和递归

这里是前一个函数的迭代阶乘实现：

```java
int factorial = 1;
for(int i=1; i<=n; i++) {
    factorial *= i;
}
```

与其调用上述代码，你可以使用 1 到 n 整数乘积的闭式解：`factorial(n) = n*(n-1)*(n-2)....3*2*1`

### 斐波契数

斐波契数的递归定义如下：



## 递归示例：斐波那契数列与阶乘

### 斐波那契数列定义

```text
fib(0) = 0
fib(1) = 1
fib(n) = fib(n-1) + fib(n-2)
```

### 阶乘递归代码示例

```java
if (n <= 1) {
    return 1;
} else {
    return n * factorial(n - 1);
}
```

### 计算阶乘值

如你所见，正整数 `n` 的阶乘值是 1 到 `n` 之间所有整数的乘积。阶乘符号为感叹号 (`!`)，以下是一些阶乘示例值：

- 1! = 1
- 2! = 2
- 3! = 6
- 4! = 24
- 5! = 120

列表 4.21 显示了 `Factorial.java` 的内容，展示了如何使用递归来计算正整数的阶乘值。

#### 列表 4.21: Factorial.java

```java
public class Factorial {

    public Factorial() {}

    public int factorial(int num) {
        if (num > 1) {
            return num * factorial(num - 1);
        } else {
            return 1;
        }
    }

    public static void main(String args[]) {
        Factorial f1 = new Factorial();
        int result = f1.factorial(5);
        System.out.println("The factorial of 5 = " + result);
    }
}
```

列表 4.21 包含了实现了数字阶乘值递归定义的 `factorial()` 函数。列表 4.21 的输出如下：

```text
The factorial of 5 = 120
```

除了递归解决方案外，还有一种计算数字阶乘值的迭代解决方案。列表 4.22 显示了 `Factorial2.java` 的内容，展示了如何使用 `for` 循环来计算正整数的阶乘值。

#### 列表 4.22: Factorial2.java

```java
public class Factorial2 {

    public Factorial2() {}

    public int factorial(int num) {
        int prod = 1;
        for (int i = 2; i < num + 1; i++) {
            prod *= i;
        }
        return prod;
    }

    public static void main(String args[]) {
        Factorial2 f2 = new Factorial2();
        int result = f2.factorial(5);
        System.out.println("The factorial of 5 = " + result);
    }
}
```

列表 4.22 定义了带有参数 `num` 的函数 `factorial()`，随后是初始值为 1 的变量 `prod`。`factorial()` 的下部分是一个 `for` 循环，其变量 `i` 范围于 2 到 `num + 1` 之间，每次循环都会将 `prod` 的值乘以 `i` 的值，从而计算出 `num` 的阶乘值。列表 4.22 的输出如下：

```text
The factorial of 5 = 120
```

### 计算两个数的最大公约数 (GCD)

两个正整数的 GCD（最大公约数）是能整除这两个整数且余数为 0 的整数。以下是一些值：

```text
gcd(6, 2) = 2
gcd(10, 4) = 2
gcd(24, 16) = 8
```

列表 4.23 使用递归和欧几里得算法寻找两个正整数的 GCD。虽然可以将代码变得更紧凑，但这个版本的算法逻辑更清晰。

#### 列表 4.23: GCD.java

```java
public class GCD {

    public GCD() {}

    public int gcd(int num1, int num2) {
        if (num1 % num2 == 0) {
            return num2;
        } else if (num1 < num2) {
            System.out.println("Switching " + num1 + " and " + num2);
            return gcd(num2, num1);
        } else {
            System.out.println("Reducing " + num1 + " and " + num2);
            return gcd(num1 % num2, num2); // 修正了原代码中可能的递归死循环逻辑
        }
    }

    public static void main(String[] args) {
        GCD g = new GCD();
        int result = g.gcd(24, 10);
        System.out.println("The GCD of 24 and 10 = " + result);
    }
}
```

## 字符串递归反转

列表 4.26 显示了 `Reverser.java` 的内容，它使用递归来反转字符串。第 1 章向你展示了一个非递归的反转字符串示例，它比使用递归更简单。此代码仅用于说明。

#### 列表 4.26: Reverser.java

```java
public class Reverser {

    public Reverser() {}

    private String reverser(String original) {
        if (original.isEmpty()) {
            return original;
        }
        return reverser(original.substring(1)) + original.charAt(0);
    }

    public static void main(String[] args) {
        String result;
        String[] names = {"Sally", "Steve", "Robert"};
        Reverser rev = new Reverser();
        for (String name : names) {
            result = rev.reverser(name);
            System.out.println("Word: " + name + ": reverse: " + result);
        }
    }
}
```

列表 4.26 定义了 `Reverser` 类以及一个 `main()` 方法，该方法将变量初始化为 `Reverser` 类的实例。`for` 循环遍历了 `names` 数组中的字符串，然后调用 `reverser()` 方法来反转当前字符串。运行列表 4.26 中的代码，你将看到以下输出：

```text
Word: Sally reverse: yllaS
Word: Steve reverse: evetS
Word: Robert reverse: treboR
```

### 总结

本章从包含条件逻辑的 `for` 循环和 `while` 循环的 Java 代码示例开始，这些逻辑在第 1 章中介绍过。你学习了如何判断一个整数是偶数还是奇数，以及指定的年份是否为闰年。接下来，你学习了如何处理字符串和数字数组。

你还学习了递归以及如何定义被递归调用的方法以计算数字的阶乘值。你还使用递归来寻找正整数的质因数，以及任意两个正整数的最大公约数（GCD）。最后，你学习了如何使用递归来反转字符串。

## OOP 导论

本章包含了自定义 Java 类的各种示例，并介绍了各种面向对象编程（OOP）概念，如继承、封装和多态。之前的章节中散布了一些涉及 OO 概念的代码示例，旨在对 OOP 进行预览。本章提供了对 OOP 概念的综合讨论和 Java 代码示例。

顺便提一下，如果你通过在其他编程语言工作已经熟悉 OOP，那么可能只需跳过本章就足够了，只需确保你对所有代码示例都熟悉。作为第二个益处，你可以将现有的代码示例转换为 Java，这将加速你的学习过程。

然而，如果你是一个新手，可能需要花费更多时间来彻底掌握 OOP 概念中更微妙的以及它们在 Java 代码中的实现方式。为了方便学习过程，本章在概念和代码示例之间交替出现。此外，请阅读第 2 章（如果你还没有的话），因为本章的内容假设你已经熟悉该章节中的概念和代码示例。

本章的第一部分向你展示了如何在 Java 类中重写方法，随后解释了用于变量和方法的 Java 关键字 `private`、`protected` 和 `public`。本章的第二部分通过代码示例引入了继承，并引入了可以简化测试过程并增加自定义类重用性的值对象。

本章的第三部分讨论了继承，并提供了如何使用不同类来实例化类的示例。你还将学习接口和抽象类。本章的第四部分深入探讨了多态，通过代码示例说明了关于多态的一些更微妙的细节。

## Java 构造函数

你之前学习过，Java 类可以非正式地视为一组函数和数据，分别称为方法和属性（或字段），它们的访问性通过特定的键确定。类的实例是一个具体的对象，也就是说它存在于内存中的某处。实例还具有一个标识，可以将其与同一类的其他实例区分开来。

同一类的多个实例通常具有不同的属性值（稍后你会学习到该规则的例外）。在随后的章节中，你将看到两个不同的实例可以包含相同的内容，尽管它们占据不同的内存位置。

类中的构造函数允许你初始化类实例的属性。事实上，Java 允许你定义具有不同参数的多个构造函数。列表 5.1 显示了 `MyClass` 的内容，定义了两个构造函数：一个是空构造函数，另一个构造函数接受两个参数。

### 列表 5.1: MyClass.java

```java
public class MyClass {

    private String fname = "";
    private String lname = "";

    // public 空构造函数
    public MyClass() {
        this("unknown", "person");
    }

    // public 构造函数
    public MyClass(String fname, String lname) {
        this.fname = fname;
        this.lname = lname;
    }

    public static void main(String[] args) {
        MyClass inst1 = new MyClass("Dave", "Smith");
        MyClass inst2 = new MyClass();
    }
}
```

列表 5.1 定义了 `MyClass` 类，`main()` 方法将变量 `inst1` 和 `inst2` 初始化为 `MyClass` 的实例。注意 `inst1` 是通过调用接受两个参数的构造函数创建的，而 `inst2` 是通过调用空构造函数创建的。

作为提醒，在第 3 章中学习了类中的构造函数可以通过几种方式被调用，如下列表所示：

1. 使用 `new` 关键字（构造调用）
2. 使用类的 `newInstance()` 方法（构造调用）
3. 使用 `clone()` 方法（构造调用）
4. 使用反序列化（构造调用）

## 方法重载

除了重写方法，Java 还允许你重载方法名；然而，这两个方法的参数在数量或类型上有所不同。方法的签名是参数数据类型的组合。下面是一些示例：

```java
public void add(int x1, int x2) { ... }
public void add(int x1, double x2) { ... }
public void add(int x1, int x2, int x3) { ... }
```

上述方法对应的方法签名如下：

```text
int, int
int, double
int, int, int
```

方法重载使你的类支持更广泛的数据类型。

## `public`、`protected` 和 `private` 关键字

记得第 3 章讨论了这些 Java 关键字，本节包含了完整的代码示例。

列表 5.2 显示了 `ClassA.java` 的内容，它包含了 `public`、`protected` 和 `private` 变量，以及一个返回私有变量 `x3` 值的 `public` 方法。

### 列表 5.2: ClassA.java

```java
public class ClassA {

    public int x1 = 1;
    protected int x2 = 2;
    private int x3 = 3;

    public ClassA() {}

    public void display() {
        System.out.println("ClassA x1: " + x1);
        System.out.println("ClassA x2: " + x2);
        System.out.println("ClassA x3: " + x3);
        System.out.println("ClassA x3: " + getX3());
    }

    public int getX3() {
        return this.x3;
    }

    public static void main(String args[]) {
        ClassA al = new ClassA();
        al.display();
    }
}
```

## 身份等性与相等性是不同的概念

假设变量 `a1` 和 `a2` 都是类 `A` 的实例。关于 `a1` 和 `a2` 存在以下几种可能性：

1. `a1` 和 `a2` 包含不同的值
2. `a1` 和 `a2` 包含相同的值，但位于不同的内存地址
3. `a1` 和 `a2` 包含相同的值且位于相同的内存地址

在情况 1 中，我们知道 `a1` 不等于 `a2`，这意味着以下代码段的执行结果为真：

```java
if (a1 != a2) { ... }
```

在情况 2 中，`a1` 和 `a2` 是相等性的示例，这意味着以下代码段的评估为真：

```java
if (a1.equals(a2)) { ... }
```

在情况 3 中，`a1` 和 `a2` 是身份性的示例，这意味着以下代码段的评估为真：

```java
if (a1 == a2) { ... }
```

`Object` 类（将在本章稍后部分详细讨论）提供了 `equals()` 和 `hashCode()` 方法，作为确定每个类每个实例身份的默认机制。然而，如果你想更改类实例身份的定义，可以重写这两个方法中的任意一个。列表 5.3 显示了 `MyEmployee.java` 的内容，说明了上述概念。

### 列表 5.3: MyEmployee.java

```java
public class MyEmployee {

    private String fname;
    private String lname;
    private String empId;

    public MyEmployee(String fname, String lname, String empId) {
        this.fname = fname;
        this.lname = lname;
        this.empId = empId;
        System.out.println("Employee: " + fname + " " + lname + " " + empId);
    }

    // 重写默认的 equals() 方法
    public boolean equals(Object o) {
        if (o == this) return true;
        if (o == null || this.getClass() != o.getClass())
            return false;
        MyEmployee that = (MyEmployee) o;
        return (this.fname.compareTo(that.fname) == 0 &&
                this.lname.compareTo(that.lname) == 0 &&
                this.empId.compareTo(that.empId) == 0);
    }

    @Override
    public int hashCode() {
        // 返回一个计算出的值，例如被调用方法的 
        // Object 的内存地址
        // 对于 emp1/emp2/emp3 都返回相同的值：
        // return this.fname.hashCode();
        // return this.fname + this.lname.hashCode();
    }
}
```



# 代码示例：MyEmployee 类与继承演示

## MyEmployee 类实现

```java
String key = this.fname + this.lname + this.empId;

return key.hashCode();
```

```java
// 这段代码片段会导致栈溢出错误：
// return this.hashCode();
```

```java
public static void main(String[] args) {
    MyEmployee emp1 = new MyEmployee("Sally", "Jones", "1000");
    MyEmployee emp2 = new MyEmployee("Sally", "Jones", "1000");
    MyEmployee emp3 = emp1;
    MyEmployee emp4 = new MyEmployee("Sally", "Smith", "1000");

    System.out.println("");
    if (emp1 == emp2) {
        System.out.println("emp1==emp2 is true");
    } else {
        System.out.println("emp1==emp2 is false");
    }
    if (emp1.equals(emp2)) {
        System.out.println("emp1.equals(emp2) is true");
    } else {
        System.out.println("emp1.equals(emp2) is false");
    }
    System.out.println("");
    if (emp1 == emp3) {
        System.out.println("emp1==emp3 is true");
    } else {
        System.out.println("emp1==emp3 is false");
    }
    if (emp1.equals(emp3)) {
        System.out.println("emp1.equals(emp3) is true");
    } else {
        System.out.println("emp1.equals(emp3) is false");
    }
    System.out.println("");
    System.out.println("emp1 hashcode: " + emp1.hashCode());
    System.out.println("emp2 hashcode: " + emp2.hashCode());
    System.out.println("emp3 hashcode: " + emp3.hashCode());
    System.out.println("emp4 hashcode: " + emp4.hashCode());
}
```

列表 5.3 定义了 `MyEmployee` 类以及一个 `main()` 方法，该方法将 `emp1`、`emp2` 和 `emp3` 初始化为 `MyEmployee` 类的实例。由于 `emp1` 和 `emp2` 包含不同的值，它们是占据内存中不同位置的不同实例。然而，由于 `emp3` 的初始化方式，`emp1` 和 `emp3` 具有相同的内容且具有相同的内存位置。

`equals()` 方法被重写了，它决定了两个 `MyEmployee` 类实例是否为同一个实例。`main()` 方法的后续部分包含多个条件逻辑语句，用于进行各种比较，其输出如下：

```
emp1==emp2 is false
emp1.equals(emp2) is false
emp1==emp3 is true
emp1.equals(emp3) is true
emp1 hashcode: 195969035
emp2 hashcode: 195969035
emp3 hashcode: 195969035
emp4 hashcode: -33642395
```

如果你需要确认默认方法已被重写，请执行以下步骤：

1. 注释 `equals()` 方法。
2. 注释 `hashCode()` 方法。
3. 编译修改后的代码。

当你运行编译后的代码时，将看到以下输出（差异）：

```
Employee: Sally Jones 1000
Employee: Sally Jones 1000
emp1==emp2 is false
emp1.equals(emp2) is false
emp1==emp3 is true
emp1.equals(emp3) is true
```

## 继承简介

虽然继承的基本概念很直观，但如果你是初学者，继承的某些方面可能会困惑。让我们考虑包含 A 和 B 的韦恩图，A 是 B 的真集。因此，B 的实例可以被 A 的实例替换。

## 列表 5.4：SubClassB.java

```java
public class SubClassB extends ClassA {
    public SubClassB() {}

    public void display() {
        // public 和 protected 变量是可以访问的
        System.out.println("SubClassB x1: " + x1);
        System.out.println("SubClassB x2: " + x2);

        // private 变量通过访问器访问
        System.out.println("SubClassB x3: " + getX3());
        System.out.println("");

        // 错误：x3 是私有变量
        // System.out.println("SubClassB x3: " + x3);
    }

    public static void main(String[] args[]) {
        ClassA al = new ClassA();
        al.display();

        SubClassB b1 = new SubClassB();
        b1.display();

        ClassA b2 = new SubClassB();
        b2.display();
        ((ClassA) b2).display();

        // 错误：
        // ((SubClassB) b1).display();
    }
}
```

列表 5.4 定义了 `SubClassB` 类以及一个 `main()` 方法，该方法将变量 `al` 初始化为 `ClassA` 的实例。`main()` 方法的后续部分调用了 `display()` 方法，该方法分别打印变量 `x1`、`x2` 和 `x3` 的值，这些变量分别是 `public`、`protected` 和 `private` 的。

尽管你可能认为调用的是 `ClassA` 中的 `display()` 方法，但实际上，调用的是 `SubClassB` 中的 `display()` 方法。运行列表 5.4 中的代码，你将看到如下输出：

```
ClassA x1: 1
ClassA x2: 2
ClassA x3: 3

SubClassB x1: 1
SubClassB x2: 2
SubClassB x3: 3

SubClassB x1: 1
SubClassB x2: 2
SubClassB x3: 3
```

请注意列表 5.4 中接下来的被注释代码：如果你取消这段代码的注释，你将得到编译错误，因为 `al` 是 `ClassA` 的实例，而不是 `SubClassB` 的实例。正如我们所注意到的，`SubClassB` 的实例不能被 `ClassA` 的实例替换；因此，`al` 不能强制转换为 `SubClassB` 实例。

记住，如果 `B` 是 `A` 的子类，那么 `B` 可以访问 `A` 的非私有成员，但无法访问 `B` 的成员。在类子类的情况下，构造函数的调用顺序是从父类开始，然后“向下”传递到子类。

例如，假设 `A` 是一个类，`B` 是 `A` 的子类，而 `C` 是 `B` 的子类。当创建 `C` 的实例时，构造函数的调用顺序是：`A`，然后是 `B`，最后是 `C`。

## Java 方法和类的 final 修饰符

你可以通过将该方法标记为 `final` 来防止 `A` 类中的方法在 `B` 类中被重写。通常，你还可以通过将该类声明为 `final` 来防止该类被子类化。这种功能什么时候有用呢？假设你给了某人一个包含编译类的 JAR 文件，但没有内容被声明为 `final`。那么其他人就可以导入你的类，并通过定义你的类的子类来重写你的最终方法。

## 在 Java 中处理值对象

值对象是一种仅跟踪逻辑实体属性的类，它通常涉及 setter、getter 和构造函数。例如，假设一个学生注册了多门课程，你想跟踪这些课程。

简单来说，一门课程包含其属性：名称、描述以及课程的学分。因此，每门课程都可以通过值对象来维护，你不会对名称、描述或学分执行任何操作。结果是你只需要创建该类的实例，并将其添加到每个学生的课程列表中即可。

实体和值对象通常具有主/从关系，例如订单和订单行项、员工和部门、人员和地址，以及客户和订单之间也可能存在这种关系。某些实体可以包含对多个实体和/或值对象的引用。例如，一个客户可以拥有多个 `PurchaseOrder` 实例，每个实例可以包含一个或多个 `LineItem` 实体。

然而，学生和课程之间是多对多的关系，因为一个学生可以修读多门课程，而一门课程可以有多个学生就读。类似的说明也适用于用户和电影之间的关系。

## Java 中值对象的示例

上一节提供了实体和值对象的高级描述。本节包含了 `LongEmployee.java` 中一个值对象的具体示例，它包含了员工的属性，例如员工的姓、名、地址相关信息以及员工特定的细节。如果你为这个类创建一个关系型数据库表，它将是完全反规范化的。

本节的代码代表了“暴力”定义，它没有考虑到该类中属性之间的任何逻辑关系。随后的章节将向你展示如何将 `LongEmployee` 规范为四个类：`Employee.java`、`EmpDetails.java`、`Person.java` 和 `Address.java`（位于第 1 章）。这四个 Java 类实际上是包含逻辑属性的值对象。

列表 5.5 显示了 `LongEmployee.java` 的内容，它定义了八个私有变量和一个这些变量的构造函数。

### 列表 5.5: LongEmployee.java

```java
public class LongEmployee {
    private String firstName;
    private String lastName;

    private String street;
    private String city;
    private String state;

    private String empID;
    private int grade;
    private double years;

    public LongEmployee(String firstName, String lastName, String street, String city, String state, String empId, int grade, double years) {
        this.firstName = firstName;
        this.lastName = lastName;

        this.street = street;
        this.city = city;
        this.state = state;

        this.empId = empId;
        this.grade = grade;
        this.years = years;
    }

    public void printDetails() {
        System.out.println("First Name: " + firstName);
        System.out.println("Last Name: " + lastName);
        System.out.println("Street: " + street);
        System.out.println("City: " + city);
        System.out.println("State: " + state);
        System.out.println("ID: " + empId);
        System.out.println("Grade: " + grade);
        System.out.println("Years: " + years);
        System.out.println();
    }

    public static void main(String[] args) {
        LongEmployee e = new LongEmployee("John", "Doe", "123 Main St", "Springfield", "IL", "E123", 5, 2.5);
        e.printDetails();
    }
}
```

## OOP 简介

```java
private int[] celsiusValues2 = new int[arraySize];
private String[] names = {"Tic", "Tac", "Toe"};
```

```java
public ArrayExamples() {
    initializeArrays();
    calculateTotals();
    displayCelsiusResults();
    displayNames();
}
```

```java
public void initializeArrays() {
    // 使用随机值初始化数组
    for (int i = 0; i < arraySize; i++) {
        celsiusValues[i] = maxCelsius * Math.random();
        celsiusValues2[i] = (int) celsiusValues[i];
    }
}
```

```java
public void calculateTotals() {
    // 计算数组之和
    for (int i = 0; i < arraySize; i++) {
        intSumCelsius += celsiusValues2[i];
        dblSumCelsius += celsiusValues[i];
    }

    dblAvgCelsius = dblSumCelsius / arraySize;
    intAvgCelsius = (int) (intSumCelsius / arraySize);
}
```

```java
public void displayCelsiusResults() {
    System.out.println("Total Celsius: " + dblSumCelsius);
    System.out.println("Avg Celsius: " + dblAvgCelsius);
    System.out.println("Total Celsius2: " + intSumCelsius);
    System.out.println("Avg Celsius2: " + intAvgCelsius);
}
```

```java
public void displayNames() {
    // 显示 names 数组的内容
    for (int i = 0; i < names.length; i++) {
        System.out.println("Name " + (i + 1) + ": " + names[i]);
    }
}
```

```java
public String getFirstName() {
    return names[0];
}
```



```java
public static void main(String args[]) {
    ArrayExamples4 ae4 = new ArrayExamples4();
    String name0 = ae4.firstName();
    System.out.println("First name: " + name0);
}
```

列表 5.7 包含了你在列表 5.5 中看到的相同代码：唯一的变化是第一行（`粗体显示`），它将 `ArrayExamples` 类声明为接口 `MyArrayMethods` 的实现。运行列表 5.7 中的代码，你将看到与上一节中 `ArrayExamples2` 相同的输出。

| Name 1 | Tic |
| :--- | :--- |
| Name 2 | Tac |
| Name 3 | Toe |
| Total Celsius | 249.4551395046532 |
| Avg Celsius | 20.78792892054424 |
| Total Celsius2 | 243.0 |

# Java 抽象方法与类

抽象方法是一种不包含代码的方法。Java 类可以包含：

1. 所有具体方法
2. 抽象方法与具体方法的混合
3. 所有抽象方法

上述列表中只有类型为 #1 的类可以直接实例化；其他类型必须首先由一个实现抽象方法的类 B 派生类，然后就可以直接实例化实现类 B。你可以以创建任何其他 Java 类完全相同的方式创建类 B 的实例。

以下代码块是在文件 `A.java` 中定义的抽象类示例：

```java
public class A {
    int instanceVariable;

    public abstract int methodMustBeImplemented();

    public void doSomething() {
        // 在此处插入一些代码
    }
}
```

# OOP 简介

以下代码块是在文件 `B.java` 中定义的具体类 B 的示例：

```java
public class B extends A {
    public int methodMustBeImplemented() {
        // 我们*必须*实现此方法
    }
}
```

以下代码片段会导致编译错误，因为你不能将变量初始化为抽象类的实例：

```java
Object asc = new A(); // 错误
```

然而，以下代码片段是有效的，因为变量 `Bint` 是具体类的实例：

```java
Object Bint = new B(); // 有效
```

正如你在在本章早期看到的，抽象类 A 是一个只包含抽象方法的类，将在下一个小节中讨论。

# Java 中的抽象类

如上一节所述，抽象类 A 是只包含抽象方法的类，并且在类 A 的声明中指定了 `abstract` 关键字。抽象类的示例在此：

```java
public abstract class AnAbstractClass { . . }
```

前面的类定义表明 `AnAbstractClass` 仅包含抽象方法，因此子类必须实现所有这些抽象方法。

```java
abstract class MyFirstAbstractClass {
    public abstract int methodOne();
    public abstract int methodTwo();
    public abstract String methodThree();
}
```

```java
public class MyConcreteSubClass extends MyFirstAbstractClass {
    public int methodOne() {
        // 我们*必须*实现此方法
        return 0;
    }
    public int methodTwo() {
        // 我们*必须*实现此方法
        return 0;
    }

    public String methodThree() {
        // *必须*实现此方法
        return "0";
    }
}
```

# Java 中的子类总是具体类吗？

简单来说，这个问题的答案是“否”。例如，假设我们有以下子类链：

- `Base` 包含一个多个抽象方法
- `Sub1` 是 `Base` 的子类
- `Sub2` 是 `Sub1` 的子类
- ...
- `SubN` 是 `SubN-1` 的子类
- `Concrete1` 是 `SubN` 的子类

此外，假设 `Sub` 到 `SubN` 类包含抽象方法。然而，我们无法实例化 `Base` 或 `Sub` 到 `SubN`。这种子类链将以一个具体类结束。

# 方法参数与接口

通常情况下，将接口而非具体实现作为方法的参数。这允许你使用不同的具体类调用方法。此外，你可以在不修改方法签名的情况下为用户提供新的更新代码。

任何带有接口作为参数的方法都可以将该接口转换为具体类型以访问其中的方法。

然而，我们也可以为使用抽象类提供合理的理由。两种方法都涉及权衡，因此取决于哪些权衡对你的代码有意义。网上有一篇讨论权衡的好文章：

<http://hannesdorfmann.com/android/library-class>

# 什么是 OOP？

之前的材料从 Java 视角描述了接口和抽象类，这为你提供了良好的基础。在本节中，你将从通用观点学习 OOP 概念，这意味着它们适用于其他编程语言。

作为起点，类是一组函数和数据（分别称为方法和属性），它们可以通过特定的 Java 关键字具有不同的访问类型。类的实例是具有状态和标识的实体对象。

考虑到上述内容，有几个重要的 OOP 概念需要了解：

- 继承
- 委托
- 封装
- 多态

**继承**指的是两个类 A 和 B 之间的关系：如果 B 是 A 的子类，则说 B 继承自 A。

**委托**指的是对象的组合。例如，如果 A 包含 B、C 和 D 的实例，那么 A 可以将功能块委托给这些类。

**封装**指的是在类 A 的方法内部执行一组操作，这些代码对其他方法和类不可见。

**多态**涉及一个类作为不同的类表现。例如，如果类 A 有子类 B，B 有子类 C，那么类 C 的实例可以作为 B 的实例，也可以作为 A 的实例。

这里有一个几何学中的简单示例，矩形是一个四边形，而正方形是一个四条边相等且四个内角均为 90 度的四边形。

正方形是矩形的一种特殊情况（或者说后者是前者的泛化）。因此，矩形由正方形和其他不是正方形四边形组成。因此，正方形集是矩形集的*子集*，但正方形是矩形的*子类*。

在下面定义的两个类中，它们都有构造函数（尚未提供代码），并且都有一个 `perimeter()` 方法。

## 公有类 Rectangle

```java
public class Rectangle {
    public int width, length;
    public Rectangle() { ... }
    public double perimeter() { . . }
}
```

## 公有类 Square

```java
public class Square {
    public int side;
    public Square() { ... }
    public double perimeter() { . . }
}
```

下面的代码段包含 `extends` 关键字，表示 `Square` 是 `Rectangle` 类的子类：

```java
public class Square extends Rectangle { . . }
```

## Java Object 类

Java 层次结构中的顶层类是 `Object`，所有其他 Java 类都继承自 `Object` 类。`Object` 类定义了 `Java` 类层次结构中所有对象的特定行为。随着类链向下移动（从 `Object` 类开始），会指定附加信息，每个类将具有更具体的目的。相反，低层类具有更具体的功能，而高层类倾向于具有更抽象的概念。

## 继承与方法重写

在 OOP 中，你可以定义一个与父类中定义的方法具有相同签名（名称和参数类型）的方法。这种情况被称为*重写*一个类方法。

例如，`Square` 和 `Rectangle` 类都包含 `perimeter()` 方法，这意味着 `Square` 中 `perimeter()` 的定义重写了 `Rectangle` 中 `perimeter()` 的定义。

如果 `Square` 类没有包含 `perimeter()` 的定义，并且从 `Square` 类的实例调用了该方法，Java 将如下处理此情况：从类层次结构的底部开始向上移动，第一个出现的方法定义就是被执行的方法。正如你将在本章的稍后部分看到的，显式地调用父类中被重写的方法也是可能的。

## 封装

封装涉及使用访问器和变异器来“屏蔽” Java 类内部属性（如变量）免受其他类的影响。使用访问器还允许你在不修改公共 API 的情况下重构 Java 类中的代码。因此，其他类可以访问属性的值（通过访问器），而无需知道这些属性是如何计算的。

封装指的是将类的内部细节与“外部世界”分离或隔离开来。封装之所以重要，是因为因为它防止了其他程序员修改类的内部细节，这反过来可能会改变类中方法的意图行为，并可能导致它们失败。

打个比方，你汽车里的引擎被“封装”了，所以你不需要知道（或理解）内部细节。理论上，你的引擎可以被另一个引擎替换，而不需要理解新引擎的工作原理。

另一个例子是你的手机：每当你升级硬件或下载后续版本的内部软件时，你通常不知道新功能的具体细节（或已修复的漏洞）。因此，封装使你能够进行内部更改而不影响系统的其他部分（如其他类）。

作为一种简单的实现，`Person.java` 类（在第 1 章定义）定义了一个具有两个属性的人：名字和姓氏，它们是私有的 `String` 变量。该类定义了两个公共访问方法，其他类可以通过这些方法获取 `Person` 类实例的名字和姓氏。

## 多态

多态意味着“具有多种形式”。例如，一个人可以拥有多个角色：既是一个班级的学生，也是另一个班级的老师。通过多态，我们可以在不同的类中以多种方式执行操作，所有这些类都实现了同一个接口。例如，`Mammal` 接口可以被 `Cat` 类、`Dog` 类和 `Lion` 类实现。如果 `Mammal` 接口包含 `speak()` 方法，那么上述三个类每个都有该方法的自己的实现，它们可能会输出文本“Meow”、“Woof”和“Roar”。

正如你所知的列表 5.4 所示，当类具有继承关系时，我们可以在赋值语句中使用子类替换类，在处表示如下：

```java
ClassA b2 = new SubClassB();
b2.display();
((ClassA) b2).display();
```

注意，前面的代码块赋值语句的左侧是赋值语句右侧的父类，因此你可以执行以下操作：

- 左侧类可以被右侧类的父类或右侧类本身替换
- 左侧实例只能“看到”左侧类中的方法
- 左侧实例必须强制转换为右侧类才能“看到”右侧类中的方法

列表 5.8、列表 5.9 和列表 5.10 分别显示 `BaseClass2.java`、`SubClass2.java` 和 `SubClassB.java` 的内容。注意 `BaseClass2.java` 有一个子类 `SubClassC.java`。

## 列表 5.8：BaseClass2.java

```java
public class BaseClass2 {
    public BaseClass2() {
        System.out.println("Inside BaseClass2");
    }
    public void greetings() {
        System.out.println("Greetings from BaseClass2");
    }
    public void hello() {
        System.out.println("Hello from BaseClass2");
    }
    public static void main(String[] args) {
        BaseClass2 bc = new BaseClass2();
    }
}
```

列表 5.8 定义了 `BaseClass2` 类、一个非空构造函数、两个简单方法，以及一个 `main` 方法，该 `main` 方法初始化变量 `bc` 为 `BaseClass2` 的实例。构造函数被调用，打印出 Inside BaseClass2。注意，`greetings()` 或 `hello()` 方法都没有调用。

## 列表 5.9：SubClassC.java

```java
public class SubClassC extends BaseClass2 {
    public SubClassC() {
        System.out.println("Inside SubClassC");
    }
    public void hello() {
        System.out.println("Hello from SubClassC");
    }
    public void goodbye() {
        System.out.println("Goodbye from SubClassC");
    }
    public static void main(String[] args) {
        System.out.println("Invocation #1");
        SubClassC cl1 = new SubClassC();
        cl1.hello();

        System.out.println("Invocation #2");
        BaseClass2 bl1 = new SubClassC();
        bl1.hello();

        System.out.println("Invocation #3");
        ((SubClassC)bl1).goodbye();
    }
}
```

列表 5.9 定义了 `SubClassC`、一个非空构造函数和两个简单方法，以及一个 `main` 方法，该 `main` 方法初始化变量 `cl` 为 `SubClassC` 的实例。当构造函数被调用时，打印出 Inside SubClassC。接下来，代码段 `cl1.hello()` 调用了 `SubClassC` 的 `hello()` 方法，打印 Hello from SubClassC。

现在我们将讨论代码中最感兴趣的部分。下面的代码段声明了类型为 `BaseClass2` 的 `bl1`，但将 `bl1` 初始化为 `SubClassC` 的实例并调用了 `hello()` 方法：

```java
BaseClass2 bl1 = new SubClassC();
bl.hello();
```

上述代码段的输出是什么？它会调用 `BaseClass2` 的 `hello()` 方法还是 `SubClassC` 的 `hello()` 方法？

以下代码段将 `b1` 强制转换为 `SubClassC` 的实例，然后调用 `hello()` 方法：

```java
((SubClassC)b1).goodbye();
```

上述片段调用了 `SubClassC` 的 `hello()` 方法，这是一个合理的推断。然而，尽管下面的代码片段与上述代码片段相似，但它无法工作（`SubClassD` 定义在列表 5.10 中）：

```java
//((SubClassD)b1).goodbye();
```

上述代码片段失败的原因如下：尽管 `SubClassD` 继承了 `SubClassC`，但它不能作为 `SubClassC` 的可替代类型，因为 `SubClassD` 可能包含 `SubClassC` 不可见的方法。

接下来的代码片段声明了类型为 `BaseClass2` 的 `b2`，然后将 `b2` 初始化为 `SubClassD` 的实例，这是有效的，因为 `BaseClassD` 被定义为 `BaseClass2` 的子类：

```java
BaseClass2 b2 = new SubClassD();
b2.hello();
((SubClassD)b2).goodbye();
```

在我们运行列表 5.9 中的代码之前，我们需要定义类 `SubClassD`，它显示在列表 5.10 中。

## 列表 5.10: SubClassD.java

```java
public class SubClassD extends SubClassC
{
    public SubClassD()
    {
        System.out.println("Inside SubClassD");
    }
    public void hello()
    {
        System.out.println("Hello from SubClassD");
    }
    public void goodbye()
    {
        System.out.println("Goodbye from SubClassD");
    }
    public static void main(String[] args)
    {
        SubClassD sd = new SubClassD();
        sd.greetings();
    }
}
```



列表 5.10 定义了类 `ClassD` 以及 `main()` 方法，该方法将变量 `sd` 初始化为 `SubClassD` 的实例。随后调用了构造函数，片段显示 `sd.greetings()` 调用了来自 `SubClassD` 的 `greetings()` 方法。

接下来，`greetings()` 方法调用了 `greetings()` 方法，该方法没有在 `SubClassD` 中定义（定义在列表 5.9 中），也没有在 `SubClassD` 的父类 `SubClassC` 中定义。

事实上，`greetings()` 方法定义在 `BaseClass2` 中，它是 `SubClassC` 的父类。`greetings()` 方法显示以下字符串：

```
Greetings from BaseClass2
```

编译 `BaseClass2.java`、`SubClassC.java` 和 `SubClassD.java`，现在运行以下命令：

```
java BaseClass2
```

上述代码段的输出如下：

```
Inside BaseClass2
```

接下来，运行以下命令：

```
java SubClassD
```

上述代码段的输出如下：

```
Inside BaseClass2
Inside SubClassD
Greetings from BaseClass2
```

类 `SubClassD` 是 `BaseClass2` 的子类，包含 `greetings()` 方法，而 `SubClassD` 本身并不包含 `greetings()` 方法。然而，由于 `BaseClass2` 和 `SubClassD` 之间的继承关系，`SubClassD` 的实例可以调用 `greetings()` 方法，Java 将在 `BaseClass2` 类中找到该方法并执行它。运行以下命令：

```
java SubClassC
```

上述代码段的输出如下：

```
Invocation #1
Inside BaseClass2
Inside SubClassC
Hello from SubClassC
```

```
Invocation #2
Inside BaseClass2
Inside SubClassC
Hello from SubClassC
```

## 开发者 Java 入门指南

Invocation #3

Goodbye from SubClassC

Invocation #4

Inside BaseClass2

Inside SubClassD

Hello from SubClassD

Invocation #5

Goodbye from SubClassD

有趣的代码位于 `SubClassC` 的 `main()` 程中。接下来的部分将解释哪些代码是正确的，哪些代码是错误的，随后是一组规则，帮助你判断赋值语句的正确性。

以下代码片段是正确的，因为 `c1` 是 `SubClassC` 的实例：

```
SubClassC c1 = new SubClassC();
```

你可以用父类替换上述代码段左侧的类。由于 `BaseClass2` 是 `SubClassC` 的父类，因此 #2 中的代码是正确的：

```
BaseClass2 b1 = new SubClassC();
```

接下来，`b1` 在右侧使用类 `SubClassC` 实例化，这意味着我们可以将 `b1` “向下转换”为 `SubClassC` 的实例，因此 #3 中的代码是正确的：

```
((SubClassC)b1).goodbye();
```

然而，`SubClassD` 不是 `SubClassC` 的父类，且显然不等于 `SubClassC`，因此此行代码是错误的：

```
// ((SubClassD)b1).goodbye();
```

由于 `BaseClass2` 是 `SubClassD` 的父类，因此 #4 中的代码是正确的：

```
BaseClass2 b2 = new SubClassD();
```

接下来，`b2` 在右侧使用类 `SubClassD` 实例化，这意味着我们可以将 `b2` “向下转换”为 `SubClassD` 的实例，因此 #5 中的代码是正确的：

```
((SubClassD)b2).goodbye();
```

以下代码片段是错误的，因为 `c2` 不是 `SubClassC` 的实例：

```
SubClassC c2 = new SubClassD();
```

### 总结

本章介绍了继承和多态。此外，你学习了接口以及方法与变量之间的区别。接下来，你学习了封装和多态。

## 6 数据结构

本章介绍了各种数据结构，例如哈希映射和链表，以及如何使用它们。本章的第一部分讨论了遗留类，随后是迭代器的概述。本章的第二部分深入探讨了常用的数据结构。本章的最后部分讨论了遗留数据结构。

## 遗留数据结构

Java 工具包提供了以下接口和类：`BitSet`、`Enumeration`、`Hashtable`、`Properties`、`Stack` 和 `Vector`。从版本 2 开始，Java 引入了名为 `Collection` 的框架。

## 迭代器

本节讨论了迭代器的概念以及不同类型的迭代器。你将看到在 Java 早期版本执行迭代的代码。如果你已经接触过迭代器，可以快速跳过本节。

### 什么是迭代器？

迭代器允许按顺序访问集合中的所有元素。实际上，迭代器允许你遍历（循环）对象集合。你可以使用迭代器遍历数组元素、目录中的文件以及图的顶点。迭代器不会改变给定的集合，但对集合元素执行的操作可能会改变集合。

### 主动与被动

在主动迭代器的情况下，客户端控制迭代器的创建以及主动迭代器的迭代。相比之下，被动迭代器控制其对集合的迭代。注意，主动迭代器用于 Java 8 之前，而被动迭代器用于后续的 Java 版本。

### Enumeration: 旧式迭代

在 Java 的初始版本中，迭代器模式是通过 `Enumeration` 类（遗留代码的一部分）实现的，如示例所示：

```java
Vector words = new Vector();

// 用一些字符串填充 words
// . . .
Enumeration e = words.elements();
while (e.hasMoreElements()) {
    String word = (String) e.nextElement();
    System.out.println(word);
}
```

注意，前面的 `while` 循环调用了 `e.nextElement()` 来访问变量 `e`（这是一个 `Enumeration`）中的下一个元素。

### 迭代器：第二种迭代风格

在 Java 1.2 到 1.4 中，以下代码块演示了如何使用 `Iterator` 执行迭代：

```java
List words = new LinkedList();

// populate 'words'
//
Iterator iter = words.iterator();
while (iter.hasNext()) {
  String word = (String) iter.next();
  System.out.println(word);
}
```

让我们看看如何使用泛型来执行迭代，正如该节所述。

### 泛型：第三种迭代风格

在 Java 1.2 到 1.4 中，以下代码块演示了如何使用 `for` 循环执行迭代：

```java
List<String> words = new LinkedList<String>();

// populate 'words'
//
for (String word : words) {
  System.out.println(word);
}
```

Java 7 引入了“菱形运算符”，在此所示：

```java
List<String> words = new LinkedList<>();
```

上述代码段将变量 `words` 定义为 `LinkedList` 的实例，其中每个元素都是 `String`。

顺便提到，`List` 是一个接口，而 `LinkedList` 是实现 `List` 接口的具体类。请阅读第 6 章关于用子类替换类的解释：当用实现该接口的类来替换接口时，情况也是如此。

### forEach：第四种迭代风格

Java 8 支持使用 `forEach()` 循环执行迭代，如下所示：

```java
List<String> words = new LinkedList<>();

// populate 'words'
// . . .
words.forEach(word -> System.out.println(word));
```

上述代码块包含一个 lambda 表达式，它本质上是一个匿名函数。当你需要执行一个只执行一次的代码块时，lambda 表达式非常有用，例如按钮点击事件的事件处理器。

### 流：第五种迭代风格

Java 8 及更高版本引入了包含惰性操作（lazy operators）和终端操作符（terminal operators）的类。惰性操作是不立即执行的操作符，而终端操作符的执行会触发惰性操作的执行。终端操作符是惰性操作序列中的最后一个操作符。这里有一个幽默的类比（借自 Venkat Subramanian），可能帮助理解惰性操作和终端操作符之间的区别：

- 母亲和两个儿子在客厅看电视
- 母亲：“你需要去倒垃圾。”
- 儿子们[没有反应]
- 母亲[几分钟后]：“你需要完成作业。”
- 儿子们[沉默]
- 母亲[几分钟后]：“我去叫你们爸爸了。”
- 儿子们：立即行动……

作为简短预览，以下代码块涉及菱形运算符来初始化变量 `words`，随后调用了 `stream()` 方法。链式调用触发了 `filter()` 操作符（这是一个惰性操作），然后调用了 `forEach()` 操作符（这是一个终端操作符）：

```java
List<String> words = new LinkedList<>();
// populate 'words'
// . . .
words.stream()
  .filter(word -> word.startsWith("A"))
  .forEach(w -> System.out.println(w));
```

现在你已经对迭代器（Iterators）和流（Streams）有了基本的了解，请查看集合接口（Collection interfaces）、集合类（Collection classes）以及一些代码示例。

## 集合接口

本节包含了集合框架（Collection framework）中定义的接口列表，以及关于其用途的简单描述。你将在本章后部分看到涉及其中某些接口的代码示例。

- `Collection` 接口允许你处理对象组；它位于集合层次结构的最顶端。
- `List` 接口扩展了 `Collection`，`List` 实例存储有序的元素集合。
- `Set` 接口包含与 `Collection` 相同的方法，并限制集合必须包含唯一元素。`SortedSet` 扩展了 `Set` 以处理排序集合。
- `Map` 将唯一的键（keys）映射到值（values），`Map.Entry` 是 `Map` 类的内部类，用于描述 map 中的一个元素（键/值对）。
- `SortedMap` 扩展了 `Map` 使键按升序排列。`Enumeration` 是一个遗留接口，定义了用于对对象集合进行枚举（一次获取一个）获取元素的方法。正如你在前一节中看到的，`Iterator` 替代了 `Enumeration` 接口。

## 集合类

Java 提供了两种类型实现 `Collection` 接口的集合类：一些提供完整的实现，另一些是抽象类。记住你不能实例化抽象类。首先，你必须用实现抽象类中抽象方法的类来扩展抽象类。

集合框架提供了核心接口的若干种通用实现。特别是 `List`、`Map`、`Deque`、`Queue` 和 `Set` 接口最常见的实现分别是 `ArrayList`、`HashMap`、`ArrayDeque`、`LinkedList` 和 `HashSet`。

这里是标准集合类的详细列表，及其用途的简单描述：

- `AbstractCollection`：实现 `Collection` 接口的大部分
- `AbstractList`：扩展 `AbstractCollection` 并实现 `List` 接口
- `AbstractSequentialList`：扩展 `AbstractList` 用于使用顺序而非随机访问的集合
- `LinkedList`：通过扩展 `AbstractSequentialList` 实现链表
- `ArrayList`：通过扩展 `AbstractList` 实现动态数组
- `AbstractSet`：扩展 `AbstractCollection` 并实现 `Set` 接口
- `HashSet`：扩展 `AbstractSet` 用于哈希表
- `LinkedHashSet`：扩展 `HashSet` 允许插入顺序
- `TreeSet`：实现存储在树中的集合
- `AbstractMap`：实现 `Map` 接口的大部分
- `HashMap`：扩展 `AbstractMap` 使用哈希表
- `TreeMap`：扩展 `AbstractMap` 使用树
- `WeakHashMap`：扩展 `AbstractMap` 使用弱引用哈希表
- `LinkedHashMap`：扩展 `HashMap` 允许插入顺序
- `IdentityHashMap`：扩展 `AbstractMap` 在比较时使用引用相等

在本章后部分，你将看到涉及列表中某些类的代码示例，可以在网上查询剩余类的信息。

## Java 集合概述

正如你在本章之前看到的，各种 Java 遗留类是同步的，而集合框架中的实现是非同步的。然而，集合框架提供了线程安全的“包装”类。

这六个集合接口（`Collection`、`Set`、`List`、`Map`、`SortedSet` 和 `SortedMap`）提供了相应的静态工厂方法，如下：

- `public static <T> Collection<T> synchronizedCollection(Collection<T> c);`
- `public static <T> Set<T> synchronizedSet(Set<T> s);`
- `public static <T> List<T> synchronizedList(List<T> list);`
- `public static <K,V> Map<K,V> synchronizedMap(Map<K,V> m);`
- `public static <T> SortedSet<T> synchronizedSortedSet(SortedSet<T> s);`
- `public static <K,V> Map<K,V> synchronizedSortedMap(Map<K,V> m);`

上述列表的方法返回一个同步的（即线程安全的）集合，它涉及指定的“底层”集合。注意，对底层集合的操作必须通过返回的集合进行以确保串行访问。通过以下代码片段创建同步集合：

```java
List<Type> list = Collections.synchronizedList(new ArrayList<Type>())
```

在对返回集合进行迭代时，你必须手动进行同步。这种要求是因为迭代涉及对集合的多次调用，这些调用必须作为一个原子操作来处理。以下是迭代包装集合的示例：

```java
Collection<Type> coll = Collections.synchronizedCollection(myCollection);
synchronized(coll) {
  for (Type elem : coll) {
    someMethod(elem);
  }
}
```

关于上述代码块有两点说明。首先，注意代码块中的 `synchronized` 关键字：这将确保代码以线程安全的方式执行。其次，如果你指定了显式的迭代器，则必须在 `synchronized` 块中调用迭代器方法，以确保行为的正确。

## 便利性实现

本节描述了若干种小型实现，当你不需要它们的全部功能时，这些实现比通用型实现更方便、更高效。本节中的所有实现都是通过静态工厂方法创建的，而不是通过公共类。

### 数组的 List 视图

在查看代码之前，回想一下关于 `List` 和 `ArrayList` 的以下细节：

- `List` 是一个 Java 接口。
- `ArrayList` 是一个具体的 Java 类。
- `ArrayList` 实现了 `List` 接口。

提醒一下，如果 A 是一个具体类而 B 是 A 的具体子类，那么 A 的实例可以被 B 的实例取代：当 A 是接口而 B 是具体类时情况也是如此。因此，以下代码片段是合法的（`Integer` 可以被其他类替换）：

```java
List<Integer> itemList = new ArrayList<Integer>();
```

`Arrays.asList()` 方法返回数组的 List 视图，你可以将包含元素的 `List` 传递给需要 `List` 参数的其他方法。此外，你可以通过 `ArrayList` 类将 `List` 变量转换为数组，如下：

```java
List<Integer> itemList = new ArrayList<Integer>();
itemList.add(1);
itemList.add(2);
itemList.add(3);
Integer[] array = new Integer[itemList.size()];
array = itemList.toArray(array);
```

### 不变多副本列表

Java 提供了 `Collections.nCopies()` 方法，允许你创建一个由相同元素重复副本组成的 `List`。以下是一个示例调用：



```java
List<Type> myList = new ArrayList<Type>(
Collections.nCopies(1000, (Type)null));
```

请确保将上述片段中的 `Type` 单词替换为具体类，例如 `Integer` 或 `Decimal`。

作为代码片段的变体，你可以使用以下代码初始化一个包含 1000 个元素的 `ArrayList`：

```java
List<Type> list = new ArrayList<Type>(
Collections.nCopies(1000, (Type)null));
```

作为第三个示例，你可以将另一个字符串的多个副本添加到类型为 `List<String>` 的变量中，如下代码所示：

```java
myTools.addAll(Collections.nCopies(10, "hammer"));
```

此外，`Collections.singleton()` 方法返回一个包含单个指定元素的不可变 `Set`。

## ARRAYLIST 类

在上一节中，你已经看到了 `ArrayList` 类的示例。有趣的是，`ArrayList` 类既有数组的属性，也有列表的属性。

因此，`ArrayList` 支持 `insert()`、`remove()` 和 `findAt()` 方法，这些方法分别用于插入、删除和查找元素。这些方法使得 `ArrayList` 适用于插入和删除操作。

列表 6.1 显示了 `ArrayListChars.java` 的内容，它说明了如何将文本字符串中的字符追加到 `ArrayList` 中，然后显示其内容。此代码只会追加尚未追加到列表中的字符。

### 列表 6.1：ArrayListChars.java

```java
import java.util.ArrayList;
import java.util.List;
public class ArrayListChars {
    private char chr;
    private int charCount=0;
    private String line = "Line one and line two and three";
    private List al = new ArrayList();

    public ArrayListChars() {
      // 处理当前行中的每个字符
      for(int i=0; i<line.length(); i++) {
        char chr = line.charAt(i);

        // 检查字符是否已存在
        boolean found = false;
        for(int j=0; j<al.size(); j++) {
          if((Character)al.get(j) == chr) {
            found = true;
            break;
          }
        }

        if (found == false) {
          al.add(chr);
        }
      }

      for(int i=0; i<al.size(); i++) {
        System.out.println(al.get(i));
      }
    }
}
```

列表 6.1 定义了 `ArrayListChars` 类。第一个循环遍历字符串的每个字符，检查它是否已存在列表中。如果不在，则将其添加。第二个循环随后打印列表中存储的所有唯一字符。

列表 6.3 定义了 `HashMap1` 类，其 `main()` 方法使用字符串和字符初始化了各种集合相关的类。列表 6.3 的输出为：

```
Key = A
Values = [Apple, Aeroplane]
Key = B
Values = [Bat]
Key = C
Values = [Cat, Car]
```

## HASHSET 类

`HashSet` 类实现了 `Set` 接口，并由哈希表作为“支持”，但它不保证元素迭代的顺序。这允许执行基本操作，例如 `get()` 和 `put()`。

一个 `HashSet` 包含键/值对。给定一个特定的键，可以在常数时间内找到它的值（如果存在）。因此，`HashSet` 非常适用于将快速查找作为首要优先任务的场景，就像你在 `HashMap` 类中看到的那样。

列表 6.4 显示了 `HashSetChars.java` 的内容，展示了如何创建一个 `HashSet` 并更新其内容。

### 列表 6.4：HashSetChars.java

```java
import java.util.HashSet;
import java.util.Iterator;

public class HashSetChars {
    private char chr;
    private int charCount=0;
    private String line = "Line one and line three";
    private HashSet<Character> sl = new HashSet<Character>();

    public HashSetChars() {
        // 处理当前行中的每个字符
        for(int i=0; i<line.length(); i++) {
            chr = line.charAt(i);
            // 检查字符是否已经存在
            boolean found = false;

            Iterator iter = sl.iterator();
            while (iter.hasNext()) {
                char charl = (Character)iter.next();
                if(chrl == chr) {
                    found = true;
                    break;
                }
            }
            if (found == false) {
                sl.add(chr);
            }
        }
        System.out.println("Characters: "+sl);
    }

    public static void main(String args[]) {
        HashSetChars hsc = new HashSetChars();
    }
}
```

列表 6.4 定义了 `HashSetChars`，其构造函数包含一个 `for` 循环，该循环使用 `charAt()` 方法通过字符串变量 `line` 中的字符初始化变量 `chr`。

接下来，一个 `while` 循环在 `HashSet sl` 中搜索 `chr`；如果未找到，则将 `chr` 添加到 `sl`。此过程对变量的每个字符重复执行。列表 6.4 的输出为：

```
Characters: [, d, e, a, L, n, o, l, h, i, w, t, r]
```

## LINKEDLIST

早之前你学习了 `ArrayList` 既具有数组的属性也具有列表的属性：`LinkedList` 类也是如此。`LinkedList` 的常用操作是 `insert()`、`remove()` 和 `get()`，分别用于插入、删除和查找元素。`LinkedList` 对于快速插入和删除操作非常有用。

列表 6.5 显示了 `LinkedListChars.java` 的内容，展示了如何将文本字符串中的字符追加到 `LinkedList` 中并显示其内容。此代码只追加尚未追加到列表中的字符。

### 列表 6.5：LinkedListChars.java

```java
import java.util.LinkedList;
public class LinkedListChars {
  private char chr;
  private int charCount=0;
  private String line = "line one and line two and three";
  private LinkedList<Character> ql = new LinkedList<Character>();

  public LinkedListChars() {
    // 处理当前行中的每个字符
    for (int i=0; i<line.length(); i++) {
      char chr = line.charAt(i);
      // 检查字符是否已经存在
      boolean found = false;

      for (int j=0; j<ql.size(); j++) {
        char chl = (Character)ql.get(j);
        if((Character)ql.get(j) == chr) {
          found = true;
          break;
        }
      }

      if (found == false) {
        ql.add(chr);
      }
    }
    System.out.println("Characters: "+ql);
  }

  public static void main (String args[]) {
    LinkedListChars llc = new LinkedListChars();
  }
}
```

列表 6.5 定义了 `LinkedListChars` 类，其构造函数包含一个循环，该循环调用 `charAt()` 方法通过字符串变量 `line` 中的字符初始化变量 `chr`。

接下来，一个 `for` 循环从 `LinkedList` 内容中搜索 `chr`；如果未找到，则将 `chr` 添加到 `ql`。此过程对变量 `line` 的每个字符重复执行。运行列表 6.5 中的代码，将看到以下输出：

```
Characters: [L, i, n, e, o, a, d, l, t, w, h, r]
```

## QUEUE 类

`Queue` 是一种 FIFO（先进先出）数据结构，例如流水线，流水线中的第一个项目是第一个被移除的项目。`Queue` 是一个接口，有多个实现，例如 `ArrayBlockingQueue`、`LinkedList`、`PriorityBlockingQueue`、`PriorityQueue` 和 `SynchronousQueue`。

当你创建一个 `Queue` 时，可以指定它的最大容量。`Queue` 的常用操作是 `queue()` 和 `dequeue()`，分别追加新元素和移除元素。

当 `Queue` 达到容量时，任何后续的添加都会导致从 `Queue` 中移除最旧的（即第一个）元素。`Queue` 适用于显示显示的条目的时间相关功能。

列表 6.6 显示了 `Queue` 的内容，你你想显示创建的条目。

### 列表 6.6：QueueChars.java

```java
import java.util.LinkedList;
import java.util.Queue;

public class QueueChars {
    private char chr;
    private int charCount=0;
    private String line = "line one and line two and three";
    private Queue<Character> ql = new LinkedList<Character>();

    public QueueChars() {
        // 处理当前行中的每个字符
        for (int i=0; i<line.length(); i++) {
            chr = line.charAt(i);
            // 检查逻辑...
            ql.add(chr);
        }
        System.out.println("Characters: "+ql);
    }

    public static void main(String args[]) {
        QueueChars = new QueueChars();
    }
}
```

列表 6.6 定义了 `QueueChars`，其构造函数包含一个 `for` 循环，该循环调用 `charAt()` 方法通过字符串变量 `line` 中的字符初始化变量 `chr`。接下来，`chr` 被添加到 `ql`。列表 6.6 的输出为：

## TREESET 类

正如你之前看到的，`TreeSet` 是一个 `Set` 接口，由 `LinkedList` 类实现。列表 6.7 显示了 `TreeSet1.java` 的内容，展示了如何创建一个 `Set` 并更新其内容。

### 列表 6.7：TreeSet1.java

```java
import java.util.Iterator;
import java.util.Set;
import java.util.TreeSet;

public class TreeSet1 {
    private char chr;
    private int charCount=0;
    private String line = "Line one and line three";
    private Set<Character> sl = new TreeSet<Character>();

    public TreeSet1() {
        // 处理当前行中的每个字符
        for(int i=0; i<line.length(); i++) {
            chr = line.charAt(i);
            // 检查字符是否已经存在
            boolean found = false;

            Iterator iter = sl.iterator();
            while (iter.hasNext()) {
                char charl = (Character)iter.next();
                if(chrl == chr) {
                    found = true;
                    break;
                }
            }
            if (found == false) {
                sl.add(chr);
            }
        }
        System.out.println("Characters: "+sl);
    }

    public static void main(String args[]) {
        TreeSet1 tsc = new TreeSet1();
    }
}
```

(注：由于用户提供的待翻译文本在列表 6.6 和 6.7 部分存在部分逻辑断层和重复描述，翻译时已根据上下文和 Markdown 结构进行了对齐，以确保中文表述通顺。)

## 列表 6.9: Collections2.java

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class Collections2 {
    public static void main(String[] a) {
        List<Integer> nums = new ArrayList<Integer>();
        nums.add(40);
        nums.add(10);
        nums.add(30);
        nums.add(20);

        int min = Collections.min(nums);
        int max = Collections.max(nums);

        System.out.println("nums: "+nums);
        System.out.println("Min: "+min);
        System.out.println("Max: "+max);

        Collections.sort(nums);
        System.out.println("Sort: "+nums);
    }
}
```

列表 6.9 通过 `ArrayList` 实例定义了 `Collections` 类。列表 6.9 的后续部分通过 `Collections` 类中的 `min()` 和 `max()` 方法分别计算 `nums` 列表中的最小值和最大值。

在显示 `nums` 的内容、最小值和最大值之后，`sort()` 方法对 `nums` 的元素进行排序，然后显示排序后的内容。运行列表 6.9 的输出结果：

```
nums: [40, 10, 30, 20]
Min: 10
Max: 40
Sort: [10, 20, 30, 40]
```

你的编程任务可能还需要需要其他数据结构，例如树、图、双向链表和循环链表。虽然 Java 没有为这些数据结构提供内置类，但你可以定义自己的自定义类来实现这些数据结构。



作为一个简单的示例，下一节将展示如何定义一个单向链表，其元素是自定义 Java 类的实例。

## 对象的链表

列表 6.10 显示了 `Emp` 类的内容，该类包含了与员工相关的信息。

### 列表 6.10: Emp.java

```java
package com.acme;
public class Emp {
    public String name, address, id;

    public Emp() {}

    public Emp(String name, String address, String id) {
        this.name = name;
        this.address = address;
        this.id = id;
    }

    public static void main(String[] args) {
```

列表 6.10 定义了 `Emp` 类，它包含原始类型 `name`、`address` 和 `id`。该类仅仅是一个值对象，因为类中没有其他方法，这又简化了代码。

列表 6.11 显示了 `EmpLinkedList.java` 的内容，展示了如何创建一个由自定义 `Emp` 类实例组成的员工链表。

### 列表 6.11: EmpLinkedList.java

```java
package com.acme;

import java.util.LinkedList;
import com.acme.Emp;

public class EmpLinkedList {
    private LinkedList<Emp> empList = new LinkedList<Emp>();

    public void addInitialEmployees() {
        System.out.println("*** Initial Employee List ***");
        Emp emp1 = new Emp("Jane Smith", "1234 Main St", "1000");
        System.out.println("Adding employee "+emp1.id);
        empList.add(emp1);

        Emp emp2 = new Emp("John Smith", "4321 Oak St", "2000");
        System.out.println("Adding employee "+emp2.id);
        empList.add(emp2);

        Emp emp3 = new Emp("Dave Stone", "5678 Maple St", "3000");
        System.out.println("Adding employee "+emp3.id);
        empList.add(emp3);
        System.out.println("Employee count: "+empList.size());
    }

    public void removeEmployees(int index)
    {
        if (empList.size() != 0) {
            System.out.println("Removing employee at index "+index);
            empList.remove(index);
        }
        else {
            System.out.println("List is empty");
        }
    }

    public void displayEmployees()
    {
        System.out.println("*** Employee List ***");
        for (int i = 0; i < empList.size(); i++) {
            Emp emp = empList.get(i);
            System.out.println(emp.name);
        }
    }

    public void findEmployee(String name)
    {
        for (int i = 0; i < empList.size(); i++) {
            Emp emp = empList.get(i);
            if (emp.name.equals(name)) {
                System.out.println("Found employee: "+emp.id);
                return;
            }
        }
        System.out.println("Employee not found");
    }

    public static void main(String[] args) {
        EmpLinkedList list = new EmpLinkedList();
        list.addInitialEmployees();
        list.displayEmployees();
        list.findEmployee("Jane Smith");
    }
}
```

## 泛型方法

泛型方法允许你为多个数据集指定方法。例如，你可以写一个方法来对对象数组进行排序。泛型方法提供了编译时检查，这意味着你可以在编译期间捕捉无效类型。定义泛型方法的规则如下：

- 泛型方法声明有一个由尖括号 `<` 隔定的参数部分，该部分位于返回类型之前。
- 每个参数部分包含一个或多个用逗号分隔的类型参数。
- 类型参数只能表示引用类型，不能表示原始类型（如 `int`、`char` 等）。
- 泛型方法的体声明与任何其他方法相同。

```java
public class Generic1 {
    //泛型方法 printArray
    public static <E> void printArray(E[] inputArray) {
        // 显示数组元素
        for (E element : inputArray) {
            System.out.printf("%s ", element);
        }
        System.out.println();
    }

    public static void main(String[] args) {
        // 创建 Integer, Double 和 Character 数组
        Integer[] intArray = { 1, 2, 3, 4, 5 };
        Double[] doubleArray = { 1.1, 2.2, 3.3, 4.4 };
        Character[] charArray = { 'H', 'E', 'L', 'L', 'O' };

        System.out.println("Array integer contains:");
        printArray(intArray); // 传递一个 Integer 数组
        System.out.println("\nArray doubleArray contains:");
        printArray(doubleArray); // 传递一个 Double 数组
        System.out.println("\nArray characterArray contains:");
        printArray(charArray); // 传递一个 Character 数组
    }
}
```

列表 6.12 定义了 `Generic` 类，包含一个公共静态方法 `printArray()`，其参数接收类型为 `E` 的元素数组。该方法使用 `for` 循环遍历 `E` 的元素。

`main()` 方法初始化了三个数组：一个整数数组、浮点数数组和一个字符数组。`main()` 方法的剩余部分调用了三次 `printArray()` 方法来显示所有三个数组的内容。列表 6.12 在：

Array integer contains:

1 2 3 4 5 

Array doubleArray contains:

1.1 2.2 3.3 4.4 

Array characterArray contains:

H E L L O

## 通用类

泛型类在 Java 类定义中包含一个类型参数。与泛型方法一样，泛型类的类型参数部分可以有一个或多个由逗号分隔的类型参数。这些类被称为参数类或参数化类型，因为它们接受一个或多个参数。列表 6.13 显示了 Box.java 的内容，展示了一个泛型类。

### 列表 6.13: Box.java

```java
public class Box<T>
{
    private T t;

    public void add(T t) {
        this.t = t;
    }

    public T get() {
        return t;
    }

    public static void main(String[] args)
    {
        Box<Integer> integerBox = new Box<Integer>();
        Box<String> stringBox = new Box<String>();

        integerBox.add(new Integer(10));
        stringBox.add(new String("Hello World"));

        System.out.printf("Integer Value :%d\n\n", integerBox.get());
        System.out.printf("String Value :%s\n", stringBox.get());
    }
}
```

列表 6.13 定义了 Box 类以及一个 main() 方法，该方法创建了 Box 类的两个实例：类型为 Integer 的 integerBox 和类型为 String 的 stringBox。

接下来，调用这两个变量的 add() 方法，分别添加类型为 Integer 和 String 的元素。main() 方法的最后部分调用了 get() 方法，以检索并显示之前代码块中添加的值 10 和 Hello World。运行前面的代码可以看到如下结果：

```
Integer Value :10
String Value :Hello World
```

## 统计不同字符

列表 6.14 显示了 DistinctChars.java 的内容，该类统计文本字符串中不同字符的数量。

### 列表 6.14: DistinctChars.java

```java
import java.io.*;
import java.util.Collections;
import java.util.Hashtable;
import java.util.Iterator;
import java.util.List;

public class DistinctChars {
    private char chr;
    private int charCount=0;
    private String line = "Line one and two and three";
    private DataInput is;
    private Hashtable ht = new Hashtable();

    public DistinctChars() {
        // process each character in the current line
        for(int i=0; i<line.length(); i++) {
            char chr = line.charAt(i);
            if (ht.get(chr) == null) {
                ht.put(chr, 0);
            }
            charCount = (Integer)ht.get(chr);
            ht.put(chr, ++charCount);
        }
    }

    public void display() {
        for(Iterator iter=ht.keySet().iterator(); iter.hasNext(); ) {
            Character key = (Character) iter.next();
            int value = (Integer) ht.get(key);
            System.out.println("Character: "+key+": "+value);
        }

        List<Character> tmp = Collections.list(ht.keys());
        Collections.sort(tmp);
        Iterator<Character> it = tmp.iterator();

        // display ordered items
        while(it.hasNext()) {
            char key = it.next();
            int value = (Integer) ht.get(key);
            System.out.println("Character: "+key+": "+value);
        }
    }

    public static void main(String[] args) {
        DistinctChars dcl = new DistinctChars();
    }
}
```

列表 6.14 定义了 DistinctChars 类，其构造函数包含一个 for 循环，该循环调用 charAt() 方法从 String 变量 line 获取字符来初始化 chr。如果 chr 不存在 Hashtable 变量 ht，则将其值初始化为 0，之后将 charCount 加 1。思考分钟来说服自己该逻辑是正确的。

接下来，使用 while 循环遍历 ht 的元素并显示它们的值及其计数（即每个字母出现的次数）。列表 6.14 的输出如下：

```
Character: Count: 6
Character: L Count: 1
Character: a Count: 2
Character: d Count: 2
Character: e Count: 5
Character: h Count: 1
Character: i Count: 2
Character: l Count: 1
Character: n Count: 5
Character: o Count: 2
Character: r Count: 1
Character: t Count: 2
Character: w Count: 1
```

列表 6.14 上述列表按照 ASCII 排序顺序排序，其中大写字母在小写字母之前。

## Java 8 集合增强

Java 8 同时使用 Lambda 表达式和默认方法来改进早期 Java 版本中提供的集合框架。如果你还没有读过本章前面讨论过的这两个主题，现在是阅读的好时机。

java.lang.Iterable 包中的新方法有：

- default void forEach(Consumer<? super T> action)
- default Spliterator<T> spliterator()

java.util.Collection 包中的新方法有：

- default Boolean removeIf(Predicate<? super E> filter)
- default Spliterator<E> spliterator()
- default Stream<E> stream()
- default Stream<E> parallelStream()
- default getOrDefault(Object key, V value)
- default putIf(K key, V value)
- default putAbsent(K key, V value)

### 总结

在本章中，你学习了一些常用接口，随后学习了 DataInputStream。Java 输入流从流中读取数据，而 Java 输出流则向流写入数据。

流与文件 • 183

`java.io` 中也存在接口，例如 `DataInput` 和 `DataOutput`。请记住，首选实践是在方法参数中以及实例化对象时，指定接口（而不是具体对象或原始类型）作为参数。这样做的原因是，你可以传递（直接或间接地）任何实现了所指定接口的类实例。当你看到本章中使用 `java.io` 包的 `DataInput` 和 `DataOutput` 接口的示例时，请记住这一点。

如前所述，`java.io` 包包含两个抽象 Java 类 `InputStream` 和 `OutputStream`，它们是其他流型类的基类，将在下一节中进行讨论。

## 抽象输入类

正如上一节学到的，`InputStream` 是一个抽象类，基于 `InputStream` 的类中的每个方法都会抛出 `java.IOException`，而该异常又是 `Exception` 类的子类。`InputStream` 提供了一个 `read()` 方法（及其变体）来从输入流中读取数据。由于 `read()` 方法会等待数据可用，因此 `read()` 方法是一个“阻塞”方法。



当应用程序进行 API 调用并“等待”结果时，如果应用程序并不等待结果，则该 API 是一个异步 API，通常 API 会指定一个“回调”函数，当结果返回给应用程序时调用它。

在输入和输出流的情况下，你负责在完成使用后关闭这些流。通常情况下，你会在发生错误时的 `catch` 块中关闭输入流，然后在正常代码执行期间的块中关闭它。

## FileInputStream 类

`FileInputStream` 类可用于从文件系统上的文件读取数据，如下代码片段所示：

```
InputStream is = new FileInputStream("/path/and/fileName");
```

注意，上述代码片段的左侧指定了 `InputStream`，而右侧指定了 `FileInputStream` 类。这段代码之所以有效是因为 `FileInputStream` 是 `InputStream`（一个抽象类）的子类。

回想第 4 章，如果 `B` 是 `A` 的子类，那么 `A` 的出现可以用 `B` 的出现替换，因此以下两个代码片段都是有效的：

```
A a1 = new A();
A a2 = new B();
```

执行类似读取操作的另一种方法是使用以下代码片段：

```
FileInputStream fis = new FileInputStream("/path/and/fileName");
```

需要记住的一点是，`FileInputStream` 中 `finalize()` 方法的实现（这是一个受保护的方法）将关闭流，因此你不需要在代码中显式地关闭该流。

在许多情况下，当流不再使用时，垃圾回收器会调用 `finalize()`（但你不知道流何时实际被关闭）。由于存在时间延迟，你需要小心不要过快地向文件写入内容、关闭并再次打开它们，因为这样做可能会导致状态不一致。如果你不确定在方法中收到的 `InputStream` 的确切类型，也可以考虑调用 `close()` 方法。

## FilterInputStream 类

`FilterInputStream` 类是一个抽象类，它本质上充当 `InputStream` 接口中方法的“透传”闸门。关于 `FilterInputStream` 类的一个有趣事实是，你可以进行多次嵌套，如下所示：

```
InputStream is1 = getInputStream();
FilterInputStream fis1 = new FilterInputStream(is1);
FilterInputStream fis2 = new FilterInputStream(fis1);
FilterInputStream fis3 = new FilterInputStream(fis2);
```

在 `fis3` 中执行读取操作后，请求被发送到 `fis2`，`fis2` 将请求转发到 `fis1`，直到 `fis1` 提供某些数据。上述结构也可以通过方法链来实现，以及使用这种技术：

```
fis3 = new FilterInputStream(new FilterInputStream(new FilterInputStream(is)));
```

上述结构简单且比其他替代方案更推荐。接下来的几节包含了关于 `FilterInputStream` 某些子类的信息。

## BufferedInputStream 类

`BufferedInputStream` 类实现了 `InputStream` 中的方法。此外，`BufferedInputStream` 类更高效地处理更大块的数据（正如你对缓冲类所期望的那样）。如果有需要，你可以执行“包装”操作，如下代码片段所示：

```
InputStream is = new BufferedInputStream(new FileInputStream("a.txt"));
```

上述代码片段从 `a.txt` 创建了一个缓冲输入流，这让你能够利用流的缓冲特性。

## DataInputStream 类

`DataInputStream` 类实现了 `DataInput` 接口。某些方法包括 `readFully()`、`skipBytes()`、`readInt()`、`readLong()`、`readFloat()` 和 `readDouble()`，它们在更复杂的流上运行良好。以下代码块包含 `DataInputStream` 的示例：

```
DataInputStream dis = new DataInputStream(System.in);
while (dis.available() > 0) {
    int val = dis.readInt();
    System.out.println("Read int: " + val);
}
```

`DataInputStream` 中的许多方法在到达流末尾时抛出 `EOFException`。

## 从控制台读取输入

从控制台读取输入的 Java 代码涉及将 `System.in` 包装在 `InputStreamReader` 中，然后是 `BufferedReader` 以创建缓冲区。前述语句的代码如下所示：

```
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
```

下一节包含读取行向输入的完整代码示例。

## 读取行向用户输入

列表 7.1 显示了 `ReadUserInput` 的内容，它包装了 `System` 的 `DataInputStream` 以从命令行读取用户输入，然后显示每行用户输入。

### 列表 7.1: ReadUserInput.java

```java
import java.io.DataInput;
import java.io.DataInputStream;
import java.io.IOException;

public class ReadUserInput {
    public static void main(String[] args) {
        String line;
        DataInput dis = new DataInputStream(System.in);
        try {
            for(;;) {
                line = dis.readLine();
                if(line != null && line.length() > 0) {
                    String trim = line.trim();
                    System.out.println("Original: " + line);
                    System.out.println("Trimmed: " + trim);
                } else {
                    break;
                }
            }
        } catch (IOException ioe) { }
    }
}
```

列表 7.1 定义了 `ReadUserInput` 类，其 `main()` 方法初始化变量 `dis` 为 `DataInputStream` 实例，该实例包装了标准输入 `System.in`。列表 7.1 的后续部分是一个 `try/catch` 块，包含一个无限执行的 `for` 循环（即直到没有额外的命令行用户输入）。该循环读取用户提供的行并修剪外部空格。后续部分在原始行和修剪后的行前后添加字符 `x`，然后打印结果。列表 7.1 的示例输出如下：

Original: xqwerx

Trimmed: xqwerx

asdf

Original: x x asdf x

Trimmed: xasdfx

## 读取字符向用户输入

列表 7.2 显示了 `BufferedRead.java` 的内容，它从命令行读取输入，然后显示每行用户输入。

### 列表 7.2：BufferedRead.java

```java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.IOException;

public class BufferedRead {
    public static void main(String[] args) throws IOException {
        char chr;

        // 使用 System.in 创建一个 BufferedReader
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

        System.out.println("输入字符或输入 'x' 退出");

        // 读取字符
        do {
            chr = (char) br.read();
            if (chr != '\n') {
                System.out.println("char: " + chr);
            }
        } while (chr != 'x');
    }
}
```

列表 7.2 定义了 `BufferedRead` 类以及 `main()` 方法，该方法将变量 `br` 初始化为 `BufferedReader` 类的实例，该实例包装了 `InputStreamReader` 类，而后者又包装了 `System.in`。列表 7.2 的示例输出如下：

输入字符或输入 'x' 退出

as

char: a

char: s

char: d

q

char: q

char: e

char: x

## 读取文本文件

列表 7.3 显示了 `ReadTextFile.java` 的内容，该类打开一个文本文件并读取其内容。

### 列表 7.3：ReadTextFile.java

```java
import java.io.*;
class ReadTextFile {
    private String inputFile = "text.txt";
    private String line;
    //private DataInputStream is;

    public ReadTextFile() {
        try {
            // 注意：将 is 定义在 try 块之外，
            // 以便在 finally 块中使用
            DataInputStream is =
                new DataInputStream(new FileInputStream(inputFile));

            while ((line = is.readLine()) != null) {
                System.out.println("Line: " + line);
            }
        } catch (IOException ie) {
            ie.printStackTrace();
        } finally {
            // 失败，因为 'is' 定义在 'try' 块中：
            is.close();
        }
    }

    public static void main (String args[]) {
        ReadTextFile rtf = new ReadTextFile();
    }
}
```

列表 7.3 定义了 `ReadTextFile` 类以及包含一个 `try/catch/finally` 块的构造函数。在 `try` 块内部，变量 `is` 是 `DataInputStream` 类的实例，它包装了指向 `text.txt` 的 `FileInputStream`。代码的下一部分包含一个 `while` 循环，它逐行读取 `text.txt` 的内容并打印每一行。如果发生错误（例如文件缺失），则将调用 `catch` 块。如注释所示，`finally` 块并没有关闭输入流（在代码中该部分目前被注释掉了）。为了在 `finally` 块中关闭输入流，你必须在 `try` 块之外声明变量，以便在 `finally` 块中可以访问：

```java
DataInputStream is = null;
try {
    // code
} catch (IOException ie) {
    ie.printStackTrace();
} finally {
    is.close();
}
```

运行列表 7.3 中的代码，你将看到以下输出：

Line: line one

Line: line two

Line: line three

`file.txt` 的内容如下所示：

```
line one
line two
line three
```

## 读取 CSV 文件

另一种技术涉及使用正则表达式的 `split()` 方法。尽管出于兼容性考虑保留了 `StringTokenizer` 类，但建议使用 `java.util.regex` 包中的 `split()` 方法。`String.split()` 方法的一个优势是它支持多个分隔符，因为它基于正则表达式，而 `StringTokenizer` 只能指定单个分隔符。

列表 7.4 显示了 `ReadCSV1.java` 的内容，该类以行为导向的方式读取文本文件中的名称。

### 列表 7.4：ReadCSV1.java

```java
import java.io.*;
import java.util.StringTokenizer;

public class ReadCSV1 {
    private String line, fname, lname;
    private String inputFile = "names.txt";
    private String delim = ",";
    private DataInputStream is;

    public ReadCSV1() {
        try {
            is = new DataInputStream(new FileInputStream(inputFile));
            while ((line = is.readLine()) != null) {
                if(line.startsWith("#")) {
                    // 跳过注释行
                } else {
                    // 使用 StringTokenizer 类：
                    StringTokenizer st = new StringTokenizer(line, delim);
                    fname = (String)st.nextToken();
                    lname = (String)st.nextToken();
                    System.out.println("My name is " + fname + " " + lname);

                    // 使用 split 方法拆分：
                    String[] person = line.split(delim);
                    System.out.println("My name is " + person[0] + " " + person[1]);
                }
            }
        } catch (IOException ie) {
            ie.printStackTrace();
        } finally {
            is.close();
        }
    }

    public static void main (String args[]) {
        ReadCSV1 rtf = new ReadCSV1();
    }
}
```

列表 7.4 定义了 `ReadCSV1` 类，包含一个构造函数和一个 `try/catch/finally` 块。`try` 块包含一个 `while` 循环，逐行读取 `names.txt` 的内容。如果行的第一个字符是 `#`，则该行被忽略；即它被视为注释行。否则，该行通过 `StringTokenizer` 实例被拆分为标记（单词）。`fname` 和 `lname` 变量通过连续调用 `nextToken()` 方法进行初始化，然后使用以下代码片段打印 person：

`System.out.println("My name is " + fname + " " + lname);`

`main` 方法的最后部分包含一个 `catch` 块来捕获错误，以及一个 `finally` 块来关闭输入文件。运行列表 7.4 中的代码，你将看到以下输出：

My name is Jane Smith

My name is John Jones

My name is Bob Stone

列表 7.5 显示了列表 7.4 引用的 `names.txt` 内容。

### 列表 7.5：names.txt

```
#first name and last name
Jane, Smith
John, Jones
Bob, Stone
```

如果你决定使用 `split()` 方法，可以使用以下代码片段跨分隔符匹配行中的字段：

```java
String[] person = line.split(",| ");
```

## 向文本文件写入数据

列表 7.6 显示了 `WriteTextFile1.java` 的内容，它读取一个文本文件并创建一个内容相同的新文件，模拟复制命令。

### 列表 7.6：WriteTextFile1.java



```java
import java.io.*;
class WriteTextFile {
    private String line;
    private String inputFile = "text1.txt";
    private String outputFile = "textcopy.txt";
    private DataInputStream is;
    private DataOutput os;

    public void WriteTextFile() {
        try {
            is = new DataInputStream(new FileInputStream(inputFile));
            os = new DataOutputStream(new FileOutputStream(outputFile));
            while ((line = is.readLine()) != null) {
                StringBuilder modifiedLine = new StringBuilder(line);
                os.write(modifiedLine.toString()+"\n");
            }
        } catch (IOException ie) {
            ie.printStackTrace();
        } finally {
            is.close();
            os.close();
        }
    }

    public static void main(String args[]) {
        WriteTextFile rtf = new WriteTextFile();
    }
}
```

# 流与文件

```java
class AppendToFile {
    public static void main(String[] args) throws IOException {
        FileWriter file = null;

        try {
            file = new FileWriter("twolines.txt");
            file.write("The first line\n");
            file.append("The second line\n");
        } catch (IOException ioe) {
            System.out.println("Write failed; throwing an exception");
            throw ioe;
        } finally {
            file.close();
        }
    }
}
```

列表 7.7 展示了包含两个导入语句和 `AppendToFile` 类声明的类，随后是一个 `main()` 方法，该方法包含一个 try/catch 块，用于向文本文件写入数据。

变量 `file` 被初始化为 `FileWriter` 类的实例，它通过调用 `write()` 方法写入第一行，然后调用 `append()` 方法写入第二行，向 `twolines.txt` 文件写入两行文本。

如果发生错误，`catch` 块将显示消息；否则 `finally` 块将关闭输出文件。运行列表 7.7 中的代码以查看 `twolines.txt` 文件的内容，如下：

第一行

第二行

# PrintWriter 类

`PrintWriter` 类继承自 `Writer` 类，并实现了 `PrintStream` 中找到的所有打印方法，但它不处理字节。该类支持在调用 `println()` 或 `print()` 方法时执行自动刷新（flushing）。因此，刷新不是基于输出流中的换行符的。

此外，`PrintWriter` 类的方法不会抛出 I/O 异常；它们会设置一个布尔标志，你可以通过 `checkError()` 方法访问该标志。

# PrintStream 类

`PrintStream` 类继承自 `FilterWriterStream` 类，允许你将格式化后的数据作为文本写入底层的 `OutputStream`，而不是其字节值。

由 `PrintStream` 打印的所有字符都将使用底层平台的默认字符编码转换为字节。注意，在涉及写入字符而非字节的情况下，优先使用 `PrintWriter` 类。

此外，`PrintStream` 类的方法不会抛出 I/O 异常；它们会设置一个可以通过 `checkError()` 方法访问的布尔标志（与 `PrintWriter` 类一样）。

# 在文件中统计单词和字符

列表 7.8 展示了 `WordsAndChars.java` 的内容，该程序统计文本文件 `Words.txt` 中的单词数和字符数，该文件的内容在列表 7.9 中。

## 列表 7.8: WordsAndChars.java

```java
import java.io.*;
public class WordsAndChars {
    private int wordCount=0, charCount=0;
    private String line, word, delim = " +";
    private String inputFile = "Words.txt";
    private DataInputStream is;
    public WordsAndChars() {
        try {
            is = new DataInputStream(new FileInputStream(inputFile));
            while((line = is.readLine()) != null) {
                String[] words = line.trim().split("\\w+");
                // 处理当前行中的每个单词
                for(int i=0; i<words.length; i++) {
                    ++wordCount;
                    charCount += words[i].length();
                }
            }
        } catch (IOException ioe) {
            ioe.printStackTrace();
        } finally {
            //is.close();
        }
        System.out.println("Word Count: "+wordCount);
        System.out.println("Char Count: "+charCount);
    }
    public static void main(String args[]) {
        WordsAndChars rtf1 = new WordsAndChars();
    }
}
```

列表 7.8 定义了 `WordsAndChars` 类，该类的构造函数包含一个 try/catch/finally 代码块。`try` 块包含一个 `while` 循环，按逐行读取并分词 `Words.txt` 文件的内容。

接下来，一个 `for` 循环统计当前分词行中的单词（标记）数量，然后更新总字符数。注意，字符数没有考虑到 `Words.txt` 文件中单词之间的空格。`main()` 方法的最后部分包含一个 `catch()` 块和一个 `finally()` 块，包含了通常的功能。列表 7.8 的输出在此：

Word Count: 11

Char Count: 43

## 列表 7.9: Words.txt

```
First line of text
Second line of text
The third line
```

本章的下一节将展示如何在文本文件中执行搜索操作。

# 在文件中搜索字符串

列表 7.10 展示了 `SearchWord.java` 的内容，它说明了如何在文本文件中搜索字符串。

## 列表 7.10: SearchWord.java

```java
import java.io.*;

public class SearchCount {
    private int wordCount=0;
    private String search="line", delim = " ";
```

# 目录操作

Java 提供了两种创建目录的方法：`mkdir()` 方法和 `mkdirs()` 方法。`mkdir()` 方法创建一个目录，如果目录创建成功，则返回 `true`，否则返回 `false`。目录创建可能会因为各种原因而失败：

- 目录已存在
- 中间目录不存在
- 文件权限不足
- 路径属于另一个用户（如 root 节点）

幸运的是，`mkdirs()` 方法会同时创建目录和所有中间目录，这处理了上一个列表中提到的第二种情况。列表 7.12 显示了文件 `CreateDir.java` 的内容，该文件创建了目录 `/tmp/user/java/bin`。

## 列表 7.12：CreateDir.java

```java
import java.io.*;
import java.io.File;

public class CreateDir {
    public static void newdir(String args[]) {
        String newdir = "/tmp/user/java/bin";
        File dir = new File(newdir);

        // Create directory:
        boolean result = dir.mkdirs();
        System.out.println("result: "+result);
    }
}
```

列表 7.12 定义了类 `CreateDir` 以及 `main()` 方法，该方法指定了一个位于 `/tmp` 下几层的目录。这些目录可能不存在，`main()` 方法调用了 `mkdirs()` 方法。如果你多次调用此代码，将得到错误，因为目录已经存在。

列表 7.13 显示了 `ListDirectory.java` 的内容，它显示了 `/tmp` 目录的内容。

## 列表 7.13：ListDirectory.java

```java
import java.io.File;
public class ListDirectory {
    public static void main(String args[]) {
        String dirname = "/tmp";
        File file = new File(dirname);
if (file.isDirectory()) {
  System.out.println(" Directory of " + dirname);
  String s[] = file.list();

  for (int i=0; i < s.length; i++) {
    File f = new File(dirname+"/" + s[i]);

    if (f.isDirectory()) {
      System.out.println(s[i]+" is a directory");
    } else {
      System.out.println(s[i]+" is a file");
    }
  }
} else {
  System.out.println(dirname+" is not a directory");
}
}
```

列表 7.13 定义了类 `ListDirectory` 和 `main()` 方法，该方法包含一个遍历 `/tmp` 目录内容的循环。根据当前文件是目录还是实际文件，会显示不同的消息。

# 序列化

Java 支持字节流序列化，这允许你将对象转换为流，你可以通过该流通过网络发送对象，或将对象存储在磁盘上。如果你想在自定义的 Java 类中支持序列化，那么该类必须实现 `Serializable` 接口。注意，Java 中的序列化对象不包含代码。

Java 序列化是通过反射执行的，以便从要序列化的对象的字段（包括 private 和 final 字段）中获取数据。此外，如果给定的字段包含一个对象，Java 将对该对象递归执行序列化。

`ObjectOutputStream` 类用于序列化对象。列表 7.14 显示了 `Employee.java` 的内容，它将被另外两个类序列化后进行反序列化。

## 列表 7.14：Employee.java

```java
public class Employee implements java.io.Serializable {
  public String name;
  public String address;
  public transient int SSN;
  public int number;

  public void mailCheck() {
    System.out.println("Mailing a check to " + name + " + " + address);
  }
}
```

列表 7.14 定义了实现 `java.io.Serializable` 接口的类 `Employee`。注意，该接口不包含任何方法，作为一个“标记”，指示该类是可序列化的。

列表 7.15 显示了 `Serialize.java` 的内容，它实例化 `Employee` 对象并将其序列化到名为 `employee.ser` 的文件中，这是程序唯一的“输出”。

注意：将对象序列化到文件时，Java 的标准惯是给文件赋予 `.ser` 扩展名。

## 列表 7.15：Serialize.java

```java
import java.io.*;

public class Serialize {
    private static String serFile = "/tmp/employee.ser";
    public static void main(String [] args) {
        Employee e = new Employee();
        e.name = "John Doe";
        e.address = "1234 Appian Way, San Francisco";
        e.SSN = 123456789;
        e.number = 5000;

        try {
            FileOutputStream fileOut = new FileOutputStream(serFile);
            ObjectOutputStream out = new ObjectOutputStream(fileOut);
            out.writeObject(e);
            out.close();
            System.out.printf("Serialized data saved to %s", serFile);
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

列表 7.15 定义了类 `Serialize` 和 `main()` 方法，它包含两个部分。第一部分创建一个 `Employee` 实例并填充其 `name`、`address`、`SSN` 和 `number` 字段。第二部分是 `main()` 方法的 `try/catch` 块，它处理 `IOException`。

# 反序列化

你可能已经猜到，反序列化是序列化的反面：从字节流重建对象。

列表 7.16 显示了 `Deserialize.java` 的内容，它展示了如何反序列化对象。

## 列表 7.16：Deserialize.java



```java
import java.io.*;

public class Deserialize {
    private static String serFile = "/tmp/employee.ser";
    public static void main(String[] args) {
        Employee object1 = null;
        try {
            // Read the object from the file:
            FileInputStream fileInputStream = new FileInputStream(serFile);
            ObjectInputStream in = new ObjectInputStream(fileInputStream);

            // deserialization of object:
            object1 = (Employee) in.readObject();

            in.close();
            fileInputStream.close();

            System.out.println("name = " + object1.name);
            System.out.println("address = " + object1.address);
            System.out.println("SSN = " + object1.SSN);
            System.out.println("number = " + object1.number);
        } catch (IOException e) {
            System.out.println("IOException occurred");
        } catch (ClassNotFoundException e) {
            System.out.println("ClassNotFoundException");
        }
    }
}
```

代码 7.16 执行了 7.15 的反操作：从文件系统读取序列化文件并重建为类实例。为了让 JVM（Java虚拟机）反序列化对象，必须能够找到类的字节码；否则 JVM 会抛出 `ClassNotFoundException`。另外注意，当对象序列化时 `SSN` 字段的值为 123456789，但由于该字段是 `transient`，此值没有被发送到输出。反序列化 `Employee` 的 `SSN` 字段为 0。列表 7.16 的输出：

```
name = John Doe
address = 1234 Appian Way, San Francisco
SSN = 0
number = 5000
```

# 反射

Java 反射是一项强大的功能，它允许程序通过查找成员名称来检查自身的属性。

列表 7.17 显示了 `ShowMyMethods.java` 的内容，展示了如何显示 `ShowMyMethods` 类中的方法。

## 列表 7.17：ShowMyMethods.java

```java
import java.lang.reflect.*;

public class ShowMyMethods
{
    public void emptyMethod1() {}
    public void emptyMethod2() {}
    public void emptyMethod3() {}

    public static void main(String args[]) {
        try {
            //Class clz = Class.forName(args[0]);
            Class clz = Class.forName("ShowMyMethods");
            Method[] m = clz.getDeclaredMethods();
            
            for (int i = 0; i < m.length; i++) {
                System.out.println("method: "+m[i].toString());
            }
        } catch (Throwable e) {
            System.err.println(e);
        }
    }
}
```

接下来，`main()` 方法包含一个 `try/catch` 块用于初始化变量 `clz`，然后获取 `ShowMyMethods` 类中的方法数组。

`main()` 方法的最后部分包含一个循环，该循环遍历数组 `m` 并显示其内容。列表 7.17 中的代码你将看到如下输出：

```
method: public void ShowMyMethods.emptyMethod1()
method: public void ShowMyMethods.emptyMethod2()
method: public void ShowMyMethods.emptyMethod3()
method: public static void ShowMyMethods.main(java.lang.String())
```

如你所见，列表 7.17 包含以下被注释的代码段：

```java
//Class clz = Class.forName(args[0]);
```

你可以取消上述代码段的注释，以便对从命令行指定的类进行反射，此处是一个示例：

`java ShowMyMethods AnotherClass`

尽管介绍非常简短，但你可能已经体会到了反射在 Java 类加载器中的用处，这是另一个有趣的（更高级的）话题。可以上网搜索关于 Java 反射和类层级的更多详细信息。

# 注解

Java 注解为编译器提供信息。例如，Java 提供了 `@Override` 注解，你可以使用它（通过在方法前指定 `@Override`）指示被注解的方法正在重写同名的方法。

Java 还支持 `@Deprecated` 和 `@SuppressWarnings` 分别将方法标记为已弃并抑制警告信息。注解减少了你需要手动编写的样板代码。此外，注解可以为编译器提供编译信息，其他工具可以进行相应的处理。

列表 7.18：MyAnnotation.java 展示了如何使用 Java 注解。

## 列表 7.18：MyAnnotation.java

```java
class ClassA
{
    public ClassA()
    {
        this.simpleMethod();
    }

    public void simpleMethod() {
        System.out.println("Inside simpleMethod in classA");
    }
}

public class MyAnnotation extends ClassA {
    public MyAnnotation() {
        super();
    }

    @Override
    public void simpleMethod() {
        System.out.println("Inside simpleMethod in MyAnnotation");
    }

    public static void main(String[] args) {
        MyAnnotation ma = new MyAnnotation();
        ma.simpleMethod();
    }
}
```

列表 7.18 定义了内部类 `ClassA` 和继承 `ClassA` 的类 `MyAnnotation`：这两个类都包含 `simpleMethod()` 方法，该方法在 `MyAnnotation` 中被重写。

列表 7.18 还定义了一个 `main()` 方法，将变量 `ma` 初始化为 `MyAnnotation` 的实例，然后调用 `simpleMethod()`。注意事件的级联顺序：`MyAnnotation` 的构造函数调用了后者的构造函数。接下来，`ClassA` 的构造函数调用了 `simpleMethod()`，它显示了属于 `MyAnnotation` 的指定消息，而不是 `ClassA` 中的 `simpleMethod()`。

此外，`MyAnnotation` 的构造函数也调用了 `simpleMethod()`，这意味着相同的文本会被显示两次。运行列表 7.18 中的代码，你将看到如下输出：

```
Inside simpleMethod in MyAnnotation
Inside simpleMethod in MyAnnotation
```

# 总结

本章从 Java 流和面向流的类的快速概述开始。通过使用面向流的代码从命令行获取用户输入的示例，你学习了某些支持缓冲操作的接口和类。

然后，你学习了如何读取文本文件的内容、将文本行分词为单词以及如何将数据写入文本文件。接着学习了如何对自定义类进行序列化和反序列化，以及如何统计文件中字符串出现的次数。

# Java 与 SQL

本章包含代码示例，演示了如何从 Java 访问 MySQL 表中的数据。上一章包含了展示如何在 Java 中处理流的代码示例，这对于本章的某些内容很有帮助。

本章的第一部分简要介绍了 SQL（结构化查询语言）并解释了主要的 SQL 语句类型：DCL、DDL 和 DML。本章的第二部分介绍了 MySQL 数据库，并向你展示了创建和删除表的各种方法。

本章的第二部分包含系列带有 `SELECT` 关键字的 SQL 语句。第三部分向你展示如何编写连接 MySQL 的代码、如何删除并重建 MySQL 表，以及如何从 MySQL 表中查询数据。

> 注意：对于访问 MySQL 数据库的 Java 类，请记得按照本文后部分的描述设置环境变量 `CLSPATH`。

# 什么是 SQL？

SQL 是 Structured Query Language（结构化查询语言）的缩写，用于管理关系型数据库（RDBMS）中的数据。SQL 命令可以分为以下四类：

- DCL（数据控制语言）
- DDL（数据定义语言）
- DQL（数据查询语言）
- DML（数据操作语言）

以下子节提供了上述列表中每个项的额外信息。

## 什么是 DCL？

DCL 是 Data Control Language（数据控制语言）的缩写，指任何包含 `GRANT` 或 `REVOKE` 关键字的 SQL 语句。这些关键字分别从任何数据库用户授予或撤销访问权限。

例如，以下 SQL 语句授予了用户 ABC 视图和修改 `employee` 表中记录的权限：

```sql
GRANT ALL ON employee
TO ABC;
```

`GRANT` 允许用户向其他用户授予权限。相比之下，以下 SQL 语句从 ABC 处撤销了对 `employee` 表的 `UPDATE` 权限：

```sql
REVOKE UPDATE
ON employee
FROM ABC;
```

## 什么是 DDL？

DDL 是 Data Definition Language（数据定义语言）的缩写，指任何包含以下关键字的 SQL 语句：

- CREATE
- ALTER
- DROP
- RENAME
- TRUNCATE
- COMMENT

上述关键字列表可以出现在引用表作为视图（后文讨论）的 SQL 语句中。以下是使用这些关键字的部分示例：

```sql
ALTER TABLE
CREATE/DROP/ATE views
CREATE TABLE abc as (SELECT * from def);
```

### DELETE、DROP 还是 TRUNCATE

这些之间存在重要差异。`DELETE` 关键字和 `TRUNCATE` 关键字都可以从表中删除数据，但性能存在显著差异。考虑以下 SQL 语句（两者都会删除表的所有行）：

```sql
DELETE FROM customers;
TRUNCATE customers;
DROP TABLE customers;
```

`DELETE` 语句处理表中的所有行，而 `TRUNCATE` 语句执行一次操作删除所有行。因此，当表包含大量行时，`TRUNCATE` 比 `DELETE` 快得多。相比之下，`DROP` 语句删除了行和表本身。

当然，如果你想删除表的子集，则必须指定 `WHERE` 子句，因此所需的 SQL 语句可能如下：

```sql
DELETE FROM customers
WHERE cust_id < 10000;
```

## 什么是 DQL？

DQL 是 Data Query Language（数据查询语言）的缩写，指任何包含 `SELECT` 关键字的 SQL 语句。注意，DQL 可以涉及选择部分数据，也可以涉及删除部分数据，如下所示的 SQL 语句：

```sql
SELECT *
FROM customers
WHERE cust_id < 10000;
```

```sql
DELETE FROM customers
WHERE cust_id IN
(SELECT cust_id FROM customers
WHERE cust_id < 10000);
```

虽然上述两个语句的效果相同，但第一个比第二个高效，后者也被称为相关子查询，因为在外部 SQL 查询和内部 SQL 查询中引用了同一个表。

## 什么是 DML？

DML 是 Data Manipulation Language（数据操作语言）的缩写，指对数据库中一个或多个表执行查询的 SQL 语句。DML 语句是包含任何以下关键字的 SQL 语句：

- INSERT
- UPDATE
- DELETE
- MERGE
- CALL
- EXPLAIN PLAN
- LOCK TABLE

在大多数情况下，前面的关键字会修改一个或多个表中现有的数据值。下面的 SQL 语句指定了 `INSERT` 关键字向 `user` 表插入一个新行（`user` 表在本章稍后定义）：

```sql
INSERT INTO user VALUES (1000, 'Developer');
```

接下来的 SQL 语句包含 `UPDATE` 关键字的示例，用于更新行的属性：

```sql
UPDATE user
SET TITLE = 'Team Lead'
WHERE USER_ID = 1000;
```

以下 SQL 查询可以影响 `TAX_INFO` 表中的多行：

```sql
UPDATE tax_info
SET tax_rate = tax_rate + 0.05;
```

## 什么是 TCL？

TCL 是事务控制语言（Transaction Control Language）的缩写，指包含以下关键字的 SQL 语句：

- COMMIT
- ROLLBACK
- SAVEPOINT
- SET TRANSACTION

`COMMIT` 关键字将 SQL 语句或事务的结果提交到数据库，而 `ROLLBACK` 关键字的作用相反。`SAVEPOINT` 关键字标识一个后续事务可以回滚的点，当 SQL 语句中出现 `ROLLBACK` 时发生。`SET TRANSACTION` 语句用于指定事务的各种特性，例如事务的开始。当事务完成后，调用 `COMMIT` 关键字或 `ROLLBACK` 关键字。

# 使用 MYSQL

Oracle 提供了 MySQL 数据库，你可以为你的操作系统下载：

```
https://dev.mysql.com/downloads/
```

MySQL 版本及其安装程序。

## 登录 MySQL

你可以使用以下命令以 root 用户身份登录 MySQL，它会提示你输入密码：

```
$ mysql -u root -p
```

如果你通过 DMG 文件安装了 MySQL，当你启动前面的命令时，会提示输入 root 密码。

## 创建 MySQL 数据库

登录 MySQL 并调用以下命令创建 `mytools` 数据库：

```sql
MySQL [mysql]> create database mytools;
Query OK, 1 row affected (0 sec)
```

使用以下命令选择 `mytools` 数据库：

```sql
MySQL [mysql]> use mytools;
Database changed
```

使用以下命令显示 `mytools` 数据库中的表：

```sql
MySQL [mytools]> show tables;
Empty set (0 sec)
```

前面的输出是有意义的，因为 `mytools` 数据库是空的。

## 创建和删除表

在 MySQL 中创建表有三种方法，与其他 RDBMS 一样。一种方法是手动（在下一节显示）；另一种方法（如所示）调用包含 SQL 命令的文件；第三种方法涉及将 SQL 文件重定向到 MySQL 可执行文件。

下一节介绍了如何使用 MySQL 提示符显式定义 SQL 语句来手动创建表。

### 手动创建 MySQL 表

本节介绍了如何手动创建在本章后面提到的表。具体来说，你将看到如何创建以下表：

- customers
- friends
- weather

登录 MySQL 并选择 `mytools` 数据库，调用列表 8.1、8.2 和 8.3 中的 SQL 文件分别创建 `customers`、`weather` 和 `friends` 表。列表 8.1 显示了 `customers.sql` 的内容，它定义了 `customers` 表的结构并填充了数据。

## 列表 8.1：customers.sql



```sql
DROP TABLE IF EXISTS customers;

CREATE TABLE customers (cust_id INTEGER, first_name VARCHAR(20), last_name VARCHAR(20), home_address VARCHAR(20), city VARCHAR(20), state VARCHAR(20), zip_code VARCHAR(20));

INSERT INTO customers
VALUES (1000,'Smith','123 Main St','Fremont','CA','94123');

INSERT INTO customers
VALUES (2000,'Jones','123 Main St','Fremont','CA','95015');
```

列表 8.2 显示了 `weather.sql` 的内容，它定义了 `weather` 表的结构并填充了数据。

# 列表 8.2：weather.sql

```sql
DROP TABLE IF EXISTS weather;

CREATE TABLE weather (day DATE, temper INTEGER, wind INTEGER, forecast CHAR(20), city CHAR(20), state CHAR(20));

INSERT INTO weather VALUES ('2021-04-01', 42, 16, 'Rain','sf','ca');
INSERT INTO weather VALUES ('2021-04-02', 45, 3, 'Sunny','sf','ca');
INSERT INTO weather VALUES ('2021-04-03', -78, NULL, 'se','wa');
INSERT INTO weather VALUES ('2021-07-01', 42, 16, 'Rain','sf','ca');
INSERT INTO weather VALUES ('2021-07-02', 45, 3, 'Sunny','sf','ca');
INSERT INTO weather VALUES ('2021-07-03', 78, 12, NULL,'sf','mn');
INSERT INTO weather VALUES ('2021-08-04', 50, 32, 'Snow','sf','ca');
INSERT INTO weather VALUES ('2021-08-06', 51, '', 'sf','ca');
INSERT INTO weather VALUES ('2021-09-01', 42, 16, 'Rain','sf','ca');
INSERT INTO weather VALUES ('2021-09-02', 45, '', 'sf','ca');
INSERT INTO weather VALUES ('2021-09-03', 15, 12, 'Snow','chi','il');
```

列表 8.3 显示了 `people.sql` 的内容，它定义了 `people` 表的结构并填充了数据。

# 列表 8.3：people.sql

```sql
DROP TABLE IF EXISTS people;

CREATE TABLE people (fname varchar(20), lname varchar(20), age varchar(20), gender char(1), country varchar(20));
```

# Java 和 SQL

在大多数情况下，前面的关键字会修改一个或多个表中现有的数据值。下面的 SQL 语句指定了 `INSERT` 关键字向 `user` 表插入一个新行（`user` 表在本章稍后定义）：

```sql
INSERT INTO user VALUES (1000, 'Developer');
```

接下来的 SQL 语句包含 `UPDATE` 关键字的示例，用于更新行的属性：

```sql
UPDATE user
SET TITLE = 'Team Lead'
WHERE USER_ID = 1000;
```

以下 SQL 查询可以影响 `TAX_INFO` 表中的多行：

```sql
UPDATE tax_info
SET tax_rate = tax_rate + 0.05;
```

# 什么是 TCL？

TCL 是事务控制语言（Transaction Control Language）的缩写，指包含以下关键字的 SQL 语句：

- `COMMIT`
- `ROLLBACK`
- `SAVEPOINT`
- `SET TRANSACTION`

`COMMIT` 关键字将 SQL 语句或事务的结果提交到数据库，而 `ROLLBACK` 关键字的作用相反。`SAVEPOINT` 关键字标识一个后续事务可以回滚的点，当 SQL 语句中出现 `ROLLBACK` 时发生。`SET TRANSACTION` 语句用于指定事务的各种特性，例如事务的开始。当事务完成后，调用 `COMMIT` 关键字或 `ROLLBACK` 关键字。

# 使用 MYSQL

Oracle 提供了 MySQL 数据库，你可以为你的操作系统下载：

```
https://dev.mysql.com/downloads/
```

MySQL 版本及其安装程序。

# 登录 MySQL

你可以使用以下命令以 root 用户身份登录 MySQL，它会提示你输入密码：

```
$ mysql -u root -p
```

如果你通过 DMG 文件安装了 MySQL，当你启动前面的命令时，会提示输入 root 密码。

# 创建 MySQL 数据库

登录 MySQL 并调用以下命令创建 `mytools` 数据库：

```sql
MySQL [mysql]> create database mytools;
Query OK, 1 row affected (0 sec)
```

使用以下命令选择 `mytools` 数据库：

```sql
MySQL [mysql]> use mytools;
Database changed
```

使用以下命令显示 `mytools` 数据库中的表：

```sql
MySQL [mytools]> show tables;
Empty set (0 sec)
```

前面的输出是有意义的，因为 `mytools` 数据库是空的。

# 创建和删除表

在 MySQL 中创建表有三种方法，与其他 RDBMS 一样。一种方法是手动（在下一节显示）；另一种方法（如所示）调用包含 SQL 命令的文件；第三种方法涉及将 SQL 文件重定向到 MySQL 可执行文件。

下一节介绍了如何使用 MySQL 提示符显式定义 SQL 语句来手动创建表。

# 手动创建 MySQL 表

本节介绍了如何手动创建在本章后面提到的表。具体来说，你将看到如何创建以下表：

- `customers`
- `friends`
- `weather`

登录 MySQL 并选择 `mytools` 数据库，调用列表 8.1、8.2 和 8.3 中的 SQL 文件分别创建 `customers`、`weather` 和 `friends` 表。列表 8.1 显示了 `customers.sql` 的内容，它定义了 `customers` 表的结构并填充了数据。

# 列表 8.1：customers.sql

```sql
DROP TABLE IF EXISTS customers;

CREATE TABLE customers (cust_id INTEGER, first_name VARCHAR(20), last_name VARCHAR(20), home_address VARCHAR(20), city VARCHAR(20), state VARCHAR(20), zip_code VARCHAR(20));

INSERT INTO customers
VALUES (1000,'Smith','123 Main St','Fremont','CA','94123');

INSERT INTO customers
VALUES (2000,'Jones','123 Main St','Fremont','CA','95015');
```

列表 8.2 显示了 `weather.sql` 的内容，它定义了 `weather` 表的结构并填充了数据。

# 列表 8.2：weather.sql

```sql
DROP TABLE IF EXISTS weather;

CREATE TABLE weather (day DATE, temper INTEGER, wind INTEGER, forecast CHAR(20), city CHAR(20), state CHAR(20));

INSERT INTO weather VALUES ('2021-04-01', 42, 16, 'Rain','sf','ca');
INSERT INTO weather VALUES ('2021-04-02', 45, 3, 'Sunny','sf','ca');
INSERT INTO weather VALUES ('2021-04-03', -78, NULL, 'se','wa');
INSERT INTO weather VALUES ('2021-07-01', 42, 16, 'Rain','sf','ca');
INSERT INTO weather VALUES ('2021-07-02', 45, 3, 'Sunny','sf','ca');
INSERT INTO weather VALUES ('2021-07-03', 78, 12, NULL,'sf','mn');
INSERT INTO weather VALUES ('2021-08-04', 50, 32, 'Snow','sf','ca');
INSERT INTO weather VALUES ('2021-08-06', 51, '', 'sf','ca');
INSERT INTO weather VALUES ('2021-09-01', 42, 16, 'Rain','sf','ca');
INSERT INTO weather VALUES ('2021-09-02', 45, '', 'sf','ca');
INSERT INTO weather VALUES ('2021-09-03', 15, 12, 'Snow','chi','il');
```

列表 8.3 显示了 `people.sql` 的内容，它定义了 `people` 表的结构并填充了数据。

# 列表 8.3：people.sql

```sql
DROP TABLE IF EXISTS people;

CREATE TABLE people (fname varchar(20), lname varchar(20), age varchar(20), gender char(1), country varchar(20));
```

# 简单查询语句

在本章前面的部分，你看到了 `SELECT` 关键字的示例。在最简单的形式下，它如下：

```sql
MySQL [tools]> select *;
+----------------------+
| fname | lname | age | gender | country |
+----------------------+
| john  | smith | 30  | m      | usa     |
| jane  | jones | 31  | f      | france  |
| jack  |       | 32  | m      | france  |
| dave   | stone | 33  | m      | italy  |
| sara   | stein | 34  | f      | germany |
| eddy   | bower | 35  | m      | spain  |
+----------------------+
```

`LIMIT` 子句允许你指定返回的行数。例如：

```sql
MySQL [tools]> select * limit 1;
+----------------------+
| fname | lname | age | gender | country |
+----------------------+
| john  | smith | 30  | m      | usa     |
+----------------------+
```

`WHERE` 子句允许你根据条件过滤行。例如：

```sql
MySQL [tools]> select * where fname = 'john';
+----------------------+
| fname | lname | age | gender | country |
+----------------------+
| john  | smith | 30  | m      | usa     |
+----------------------+
```

`ORDER BY` 子句允许你对结果进行排序。例如：

```sql
MySQL [tools]> select * order by age desc;
+----------------------+
| fname | lname | age | gender | country |
+----------------------+
| eddy   | bower | 35  | m      | spain  |
| sara   | stein | 34  | f      | germany |
| dave   | stone | 33  | m      | italy  |
| jack  |       | 32  | m      | france  |
| jane  | jones | 31  | f      | france  |
| john  | smith | 30  | m      | usa     |
+----------------------+
```

`GROUP BY` 子句允许你将具有相同值的行分组。例如：

```sql
MySQL [tools]> select gender, count(*) from people group by gender;
+----------+
| gender | count(*) |
+----------+
| m      | 4        |
| f      | 2        |
+----------+
```

`HAVING` 子句用于过滤由 `GROUP BY` 创建的组。例如：

```sql
MySQL [tools]> select gender, count(*) from people group by gender having count(*) > 2;
+----------+
| gender | count(*) |
+----------+
| m      | 4        |
+----------+
```

`JOIN` 子句允许你根据相关列合并两个或多个表的行。例如：

```sql
MySQL [tools]> select users.name, orders.amount from users join orders on users.id = orders.user_id;
```

# EXISTS 关键字

`EXISTS` 关键字根据值的是否存在来选择行。

```sql
select city, state
from weather where exists
(select city from weather city = 'abc');
Empty set (0.001 sec)
```

前面的写法有些困惑，因为它可以被更简单直观的查询所替换：

```sql
select city, state
from weather
where city = 'abc';
```

# LIMIT 关键字

`LIMIT` 关键字限制了结果集中的行数。例如，`weather` 表包含 11 行，如下所示：

```sql
SELECT COUNT(*) FROM weather;
+----------------+
| count (*) | |
+----------------+
|    11     |
+----------------+
1 row in set (0.001 sec)
```

如果只想只想查看 `weather` 表中的三行，而不是所有的行，请执行以下 SQL 查询：

```sql
SELECT city, state
FROM weather ORDER
BY state, city
LIMIT 3;
+------+------+
| city | state |
+------+------+
| sf   | ca   |
| sf   | ca   |
+------+------+
3 rows in set (0.000 sec)
```

# SQL 中的 DELETE, TRUNCATE 和 AND DROP

SQL 允许你通过多种方式删除表中的所有数据。其中一种方法是调用以下 SQL 语句：

```sql
DELETE * from customers;
```

然而，如果数据库表具有大量行，一种更快的方法是 `TRUNCATE` 语句，如下所示：

```sql
TRUNCATE customers;
```

上述两个命令都涉及从表中删除行而不删除表。如果你想删除表中的行以及表本身，请使用 `DROP` 语句，如下所示：

```sql
DROP TABLE IF EXISTS customers;
```

# SQL 中 DELETE 语句的更多选项

上一节向你展示了如何删除表中所有的行，而本节向你展示了如何删除表中的子集，这涉及到为你想要从表中删除的行指定一个条件。

以下 SQL 语句删除了 `customers` 表中名为 JOHN 的行：



接接的 SQL 语句删除了 `customers` 表中名为 JOHN 的行，以及 `purchase_orders` 表中与 JOHN 相关的行：

```sql
DELETE
FROM customers
Where FNAME = 'JOHN'
CASCADE;
```

上述语句被称为级联删除（cascading delete），当表中的行与 `purchase_orders` 表存在一对多的关系时，它非常有用；因此，如果你从 `customers` 表中删除一个“子”行，你可能也删除 `purchase_orders` 表中的对应行。

你也可以在 `DELETE` 中指定 `LIMIT` 关键字，示例所示：

```sql
DELETE
FROM customers
Where FNAME = 'JOHN'
LIMIT 1;
```

上述语句将删除一行，但存在一个异常：如果你在 `customers` 表的定义中指定了 `ON DELETE CASCADE`，上述 SQL 查询将删除所有名字等于 JOHN 的行。

## 什么是 SQL 索引？

索引是一种能够从数据库表中更快地检索记录的结构，从而提高性能。索引包含一个与表中每行相对应的条目，而索引本身存储在树形结构中。SQL 允许你为一个表定义一个或多个索引，随后的章节将提供一些指南。

类比地，书的索引允许你搜索某个单词或术语并找到相关的页码，然后你就可以跳转到那些页面。显然，使用书索引比顺序查看书的每一页快得多。

## 索引的类型

唯一索引（unique index）可以防止列中的重复值，前提是该列也具有唯一索引，如果表具有主键，则可以自动完成。

聚集索引（clustered index）会更改表中行的顺序，然后根据键值执行搜索。一个表只能有一个聚集索引。

MySQL 引入了不可见索引（invisible indexes），查询优化器无法使用这些索引。MySQL 确保当引用的列中的数据被修改时，这些索引保持最新。你可以通过在创建表时声明其可见性，或通过 `ALTER TABLE` 命令使索引变为不可见（本章将不讨论这一点）。

## 创建索引

在表上创建索引可以通过两种方式定义，如下：

- 在创建表期间创建索引
- 在表创建后创建

这里是在创建表期间创建索引的示例：

```sql
DROP TABLE IF EXISTS customers;

CREATE TABLE customers (
    id int NOT NULL AUTO_INCREMENT, 
    fname varchar(50) NOT NULL,
    lname varchar(50) NOT NULL,
    PRIMARY KEY (id),
    INDEX (fname)
);
```

这里是在表创建后创建索引的示例：

```sql
CREATE INDEX idx_lname ON customers(lname);
Query OK, 0 rows affected 0.03 sec
```

## 索引的开销

索引占用存储空间。通常情况下，当引用的列中的数据被修改时，MySQL 会确保这些索引是最新的。如果使用索引执行 SQL 语句，性能通常比不使用索引快。然而，如果索引过多，可能会增加更新索引的时间，这可能会导致性能下降。

## 定义索引的考虑因素

在定义索引之前，你应该考虑以下因素：

1. 索引可以提高查询速度。
2. 索引会减慢插入（`INSERT`）、更新（`UPDATE`）和删除（`DELETE`）操作的速度。
3. 索引占用额外的磁盘空间。

在定义索引之前，考虑以下 SQL 语句：

```sql
SELECT *
FROM customers
WHERE lname = 'Smith';
```

插入数据的最大数取决于 `max_allowed_packet`（默认值为 4M），详见：

https://dev.mysql.com/doc/refman/5.7/en/packet-large

## 在 Java 中连接 MySQL

在编译并运行 Java 代码之前，你需要执行两个步骤。

第一步是下载数据库操作所需的 JAR 文件，你可以从此网站下载：

https://dev.mysql.com/downloads/connector/j

第二步是更新环境变量以包含上一步下载的 JAR 文件（实际版本号可能不同）：

```bash
export CLASSPATH=$CLASSPATH::.mysql-connector-java-8.0.18.jar
```

列表 8.4 显示了 `MySQLCONNECT.java` 的内容，说明了如何连接到 MySQL 数据库。

### 列表 8.4: MySQLCONNECT.java

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;

class MySQLCONNECT {
    public static void main(String[] args[]) {
        try {
            //过时的类：
            //Class.forName("com.mysql.jdbc.Driver");
            Class.forName("com.mysql.cj.jdbc.Driver");
            // 数据库/用户名/密码
            Connection conn = DriverManager.getConnection(
                "jdbc:mysql://127.0.0.1:3306/mytools?serverTimeZone=UTC",
                "root", "yourpassword"
            );
            System.out.println("成功连接到 MySQL!");
        } catch (Exception e) {
            System.out.println("出错了：");
            System.out.println(e);
            // 某些错误：
            // java.lang.ClassNotFoundException: com.mysql.cj.jdbc.Driver
            // export CLASSPATH=mysql-connector-java-8.0.18.jar:$CLASSPATH
        }
    }
}
```

## 218 • 开发者 Java 快速入门指南

```java
finally { }
}
```

```java
/* java.sql.SQLException: 服务器时区值 'PDT' 无法无法识别或代表多个时区。如果你想利用时区支持，必须配置服务器或 JDBC 驱动程序（通过 `serverTimeZone` 配置属性）以使用更具体的时区值。 */
```

列表 8.4 以几个 `import` 语句开始，这些语句指定了位于 JDBC JAR 文件中的 Java 类，该文件也包含在 `CLASSPATH` 环境变量中（否则代码将无法成功编译）。

下一部分代码初始化了字符串变量 `URL`、`USER` 和 `PASS`。如果需要，请将 `mysql` 替换为你自己的数据库（现有数据库或新数据库），并为 `PASS` 指定正确的值。列表 8.4 的后续部分是 `main()` 方法，它包含一个 `try/catch` 块，在其中建立数据库连接。如果发生错误，`catch()` 块将显示描述所遇错误的堆栈跟踪信息。运行列表 8.4 中的代码，你将看到以下输出：

Successfully connected to MySQL

## 删除并重建 MYSQL 表

在编译和运行本节中的代码之前，请确保你已经执行了上一节中的两个步骤。列表 8.5 显示了 Java 类 `MySQLDROPTABLE.java` 的内容，它展示了如何连接到 MySQL 数据库并重建表。

### 列表 8.5: MySQLDROPTABLE.java

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;

class MySQLDROPTABLE {
  public static void main(String[] args[]) {
    try {
      //已废弃类：
      //Class.forName("com.mysql.jdbc.Driver");
      Class.forName("com.mysql.cj.jdbc.Driver");

      // mytools/root/yourpassword = database/username/
      Connection conn = DriverManager.getConnection(
  "jdbc:mysql://127.0.0.1:3360/mytools?serverTimeZone=UTC",
  "root", "yourpassword");
      "jdbc:mysql://localhost:3360/mytools",
  "root", "yourpassword");

      // employees 表：emp_id, mgr_id, title
      Statement stmt = conn.createStatement();
      stmt.executeUpdate("DROP TABLE IF EXISTS EMPLOYEES");

      String sql = "CREATE TABLE employees (" + 
  "emp_id INT(8)," + 
  "mgr_id INT(8)," + 
  "title VARCHAR(200)," + 
  "PRIMARY KEY (emp_id)");

      stmt.executeUpdate(sql);
      conn.close();
    } catch (Exception e) {
      System.out.println(e);
    } finally {
    }
  }
}
```

列表 8.5 以几个 `import` 语句开始，这些语句指定了位于 JDBC JAR 文件中的 Java 类，该文件也包含在 `CLASSPATH` 环境变量中（否则代码将无法成功编译）。

下一部分代码初始化了字符串变量 `URL`、`USER` 和 `PASS`。你必须将 `mytools` 替换为你自己的数据库（现有数据库或新数据库），并为 `PASS` 指定正确的值。

列表 8.5 的后续部分是 `main()` 方法，它包含一个 `try/catch` 块，在其中建立数据库连接，并且字符串变量 `sql` 被初始化为用于删除已存在的 `friends` 表的 SQL 语句。第三步将字符串变量 `sql2` 初始化为用于创建 `friends` 表的 SQL 语句。

第四步执行变量 `sql1` 和 `sql2` 中的 SQL 代码。如果发生错误，`catch(e)` 块将显示描述所遇错误的堆栈跟踪。运行列表 8.5 中的代码，你将看到以下输出：

Created table in database

注意，旧版本的 JDBC 代码需要显式关闭数据库连接，而这一步现在是自动完成的。运行列表 8.5 中的代码将不会看到任何输出。但是，你可以登录 MySQL 并执行以下 SQL 语句来验证表是否存在：

```sql
desc employees;
+-------+------+------+
| Field | Type  | Key |
+-------+------+------+
| emp_id|int    | PRI |
| mgr_id|int    |     |
| title|varchar(200)| |
+-------+------+------+
```

## 向 MYSQL 表插入数据

列表 8.6 显示了 `MySQLINSERT.java` 的内容，它展示了如何向表中插入数据。

### 列表 8.6: MySQLINSERT.java

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;

class MySQLINSERT {
    public static void main(String[] args[]) {
        try {
            //已废弃类：
            //Class.forName("com.mysql.jdbc.Driver");
            Class.forName("com.mysql.cj.jdbc.Driver");

            // mytools/root/yourpassword = database/username/
            Connection conn = DriverManager.getConnection(
  "jdbc:mysql://127.0.0.1:3360/mytools?serverTimeZone=UTC",
  "root", "yourpassword");
      "jdbc:mysql://localhost:3360/mytools",
  "root", "yourpassword");

            // employees 表：emp_id, mgr_id, title
            Statement stmt = conn.createStatement();
            stmt.executeUpdate("DROP TABLE IF EXISTS EMPLOYEES");

            String sql = "CREATE TABLE employees (" + 
  "emp_id INT(8)," + 
  "mgr_id INT(8)," + 
  "title VARCHAR(200)," + 
  "PRIMARY KEY (emp_id)");

            stmt.executeUpdate(sql);

            String sql1 = "INSERT INTO employees (emp_id, mgr_id, title) VALUES (1000, 2000, 'Developer');";
            stmt.executeUpdate(sql1);

            String sql2 = "INSERT INTO employees (emp_id, mgr_id, title) VALUES (2000, 3000, 'Project Lead');";
            stmt.executeUpdate(sql2);

            conn.close();
        } catch (Exception e) {
            System.out.println(e);
        } finally {
        }
    }
}
```

列表 8.6 以几个 `import` 语句开始，这些语句指定了位于 JDBC JAR 文件中的 Java 类，该文件也包含在 `CLASSPATH` 环境变量中（否则代码将无法成功编译）。

下一部分代码初始化了字符串变量 `URL`、`USER` 和 `PASS`。你必须将 `mysql` 替换为你自己的数据库（现有数据库或新数据库），并为 `PASS` 指定正确的值。

列表 8.6 的后续部分是 `main()` 方法，它包含一个 `try/catch` 块，在其中建立数据库连接，并且字符串变量 `sql` 被初始化为用于删除 `friends` 表的 SQL 语句。第三步将字符串变量 `sql2` 初始化为向 `friends` 表插入数据的 SQL 语句。这一步使用不同的值执行了两次。

运行列表 8.6 中的代码将不会看到任何输出。但是，你可以登录 MySQL 并执行以下 SQL 语句来验证表是否存在并包含数据：

```sql
select * from employees;
2 rows in set (0.001 sec)
```

## 从 MYSQL 表查询数据

列表 8.7 显示了 `MySQLSELECT.java` 的内容，它展示了如何从数据库表中查询数据。

### 列表 8.7: MySQLSELECT.java



```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;

class MySQLSELECT {
    public static void main(String[] args[]) {
        int rowCount = 0;

        try {
            Class.forName("com.mysql.cj.jdbc.Driver");

            Connection conn = DriverManager.getConnection(
  "jdbc:mysql://127.0.0.1:3360/mytools?serverTimeZone=UTC",
  "root", "yourpassword");

            // employees 表：emp_id, mgr_id, title
            Statement stmt = conn.createStatement();
            ResultSet rs = stmt.executeQuery("SELECT * FROM EMPLOYEES");

            // 显示 EMPLOYEES 表的内容：
            while(rs.next()) {
                System.out.println(rs.getInt("emp_id") + "\t" + rs.getInt("mgr_id") + "\t" + rs.getString("title"));
                rowCount++;
            }

            conn.close();
        } catch (Exception e) {
            System.out.println(e);
        } finally {
        }
    }
}
```

```java
{
  System.out.println(rs.getInt(1) + " " + rs.getString(2) + " " + rs.getString(3));
  rowCount++;
} catch (Exception e) {
  System.out.println(e);
} finally {
  System.out.println("Row Count = "+rowCount);
}
```

列表 8.7 起于几个导入语句，这些语句指定了位于 JDBC JAR 文件中的 Java 类，该文件也包含在 `CLASSP` 环境变量中（否则，代码将无法成功编译）。

下部分代码初始化了字符串变量 `URL`、`USER` 和 `PASS`。你必须将 `mytools` 替换为你自己的数据库（现有数据库或新数据库），并为 `PASS` 指定正确的值。

列表 8.7 的下一部分部分是 `main()` 方法，它包含一个 `try/catch` 块，在该块中建立了数据库连接，并将字符串变量 `dell` 初始化为用于删除 `friends` 表中行的 SQL 语句。下一步将字符串变量 `sql` 初始化为用于向 `employees` 表插入行数据的 SQL 语句。这一步使用不同的数据值执行了两次。运行列表 8.7 中的代码，你将看到以下输出：

- 名字和姓: Jane Jones
- 名字和姓: John Smith
- 名字和姓: Sally Stone
- 名字和姓: Dave Edwards

## 下一步

现在你已经理解了 Java 的基本概念，还有其他有趣的 Java 方面可以学习，它们分为三组列在这里。

## Java 线程与套字

- 基础线程概念
- 扩展 Java Thread 类
- 实现 Java Runnable 接口
- Java 线程之间的数据共享
- 使用 Java ThreadGroup 工作
- 与线程相关的异常
- 执行多个 Java 线程

## 面向开发者的 Java Pocket指南

- Java 线程中的简单竞态条件
- Java 同步
- 死锁状态下的 Java 线程

## Java 网络

- URLConnection 类
- 发送 HTTP GET 请求
- 发送 HTTP POST 请求
- 使用 HTTP/2
- 服务端 Socket
- 安全的服务端 Socket
- 客户端 Socket 示例
- 从服务器 Socket 发送 JSON 数据
- 客户端 Socket 请求 JSON 数据
- 从服务器 Socket 发送 JSON 数据

## 反射、GC 与类加载器

- 在 Java 内部启动进程
- Java 反射
- Java 系统相关命令
- 垃圾收集
- 调用 `System.exit()`
- Java 类加载器
- Java 类加载器的类型
- `java.lang.ClassLoader` 方法

### 总结

在本章中，你学习了 SQL（结构化查询语言）以及主要的 SQL 语句类型，如 DCL、DDL 和 DML。然后你看到了如何从 MySQL 执行各种 SQL 命令，例如创建一个 MySQL 数据库。你还学习了如何创建数据库表以及如何向表中填充数据。

此外，你看到了各种包含 `SELECT` 关键字的 SQL 语句。

接下来，你学习了如何使用 Java 代码连接到 MySQL 数据库。此外，你看到了如何创建数据库表、向表中填充数据以及从该表中检索数据。最后，你学习了如何在 Java 中读取基于 JSON 的数据。

恭喜！你成功完成了一本节奏较快的入门读物，书中包含了大量的概念和代码示例，这为你提供了学习更高级概念的基础。祝你的旅程中好运！

## 索引

### A

- 访问器器 (Accessors), 56–57, 62
- 构造函数 (constructor and), 60–62
- 无构造函数的 Java 类, 57–58
- 使用...重构代码, 58–60
- 注解 (Annotations), 203–204
- 匿名内部类, 74
- 局限性 (limitations), 76
- ：命名内部类 (ex. named inner class), 76
- 数组 (Arrays), 102–105
- ofof 类, 64–66
- 字符串的 (of strings), 111–114
- 调用方法, 171–172
- Java 8 增强, 179
- 集合接口 (Collection interface), 158–159
- 便利实现 (convenience implementations), 161–162
- 统计不同字符, 177–179
- 泛型类 (generic class), 177
- 泛型方法 (generic methods), 175–176
- HashMap 类, 164–166
- HashSet 类, 166–167
- 迭代器 (iterators), 156
- 主动/被动示例 (active ex. passive), 156–157
- 枚举 (enumeration), forEach() 循环, 157–158
- 泛型 (generics), 157
- 迭代器 (Iterator), 157
- Stream 类, 158
- LinkedList 类, 167–168
- 对象链表 (linked lists of objects), 172–175
- Queue 类 (Queue), 168–169
- TreeSet 类, 169–170
- 同步类 (synchronized classes), 156

### B

- 泡排序算法 (Bubble sort algorithm), 105–106

### C

- 字符与字符串 (Characters and strings), 110–111
- 命令行参数 (Command line arguments), 112–113
- 构造函数 (Constructors), 128–129

### D

- 数据控制语言 (DCL), 206
- 数据定义语言 (DDL), 206
- 数据操作语言 (DML), 207–208
- 数据查询语言 (DQL), 207
- 数据结构 (Data structures)
  - ArrayList 类, 162–164
  - 集合类 (collection classes), 159–160
- 日期 (Dates)
  - 当前日期时间, 33
  - 日期比较, 33–34
  - 解析字符串, 34–35
  - SimpleDateFormat 类, 34
- 反序列化 (Deserialization), 201–202
- d-while 循环, 100–101

### E

- 异常 (Exceptions)
  - 检查型与未检查 (checked and unchecked), 40
  - 异常处理 (handling exceptions), 39
  - 解析输入, 44–46
  - try/catch 块, 31–44
  - 导入语句, 40
  - 嵌套异常, 46–47
  - Throwable 类, 41
  - throws 关键字, 41
  - 注解, 203–204
  - 匿名内部类, 74
  - 局限性, 76
  - 命名内部类, 76
  - 数组类, 64–66
  - 数组, 102–105
  - 字符串的, 111–114
  - 基础, 38
  - 泡排序算法, 105–106
  - 字符与字符串, 110–111
  - 类, 51–52

### F

- BufferedWriter, 196–197
- 字符与字符串, 194–195
- CSV 文件, 187–189
- 目录, 198–199
- FileWriter, 192–193
- PrintStream, 193–194
- ReadText, 187–189
- 搜索, 195–196
- WriteText, 191–192
- for 循环, 89–90
- 线程, 90–92
- 命令行参数, 112–113
- 构造函数, 128–129
- 计数, 122–123
- 数据结构
  - ArrayList 类, 162–164
  - 集合类, 159–160
  - 集合接口, 158–159
  - 便利实现, 161–162
  - 统计不同字符, 177–179
  - 泛型类, 177
  - 泛型方法, 175–176
  - HashMap 类, 164–166
  - HashSet 类, 166–167
  - 迭代器, 156
  - LinkedList 类, 167–168
  - 对象链表, 172–175
  - Queue 类, 168–169
  - TreeSet 类, 169–170
  - 同步类, 156

### G

- 垃圾收集 (Garbage Collection), 224
- 费米猜想, 95–97
- 最大公约数 (GCD), 121–122
- 当前日期时间, 33
- 日期比较, 33–34
- 解析字符串, 34–35
- SimpleDateFormat 类, 34
- 反序列化, 201–202
- d-while 循环, 100–101
- 异常
  - 检查型与未检查, 40
  - 异常处理, 39
  - 解析输入, 44–46
  - try/catch 块, 31–44
  - 导入语句, 40
  - 嵌套异常, 46–47
  - Throwable 类, 41
  - throws 关键字, 41
  - 注解, 203–204
  - 匿名内部类, 74
  - 局限性, 76
  - 命名内部类, 76
  - 数组类, 64–66
  - 数组, 102–105
  - 字符串的, 111–114
  - 基础, 38
  - 泡排序算法, 105–106
  - 字符与字符串, 110–111
  - 类, 51–52

### I

- 继承 (Inheritance), 134–136
- 接口 (Interfaces), 139
- 抽象类, 140
- 扩展, 139–140
- 方法参数, 144

### J

- Java
  - 抽象类, 140
  - 扩展, 139–140
  - 方法参数, 144
  - 类, 57–58
  - 构造函数, 128–129
  - 构造函数, 60–62
  - 无构造函数的类, 57–58
  - 重构代码, 58–60
- BufferedWriter, 196–197
- 字符与字符串, 194–195
- CSV 文件, 187–189
- 目录, 198–199
- FileWriter, 192–193
- PrintStream, 193–194
- ReadText, 187–189
- 搜索, 195–196
- WriteText, 191–192
- for 循环, 89–90
- 线程, 90–92
- 命令行参数, 112–113
- 构造函数, 128–129
- 计数, 122–123
- 数据结构
  - ArrayList 类, 162–164
  - 集合类, 159–160
  - 集合接口, 158–159
  - 便利实现, 161–162
  - 统计不同字符, 177–179
  - 泛型类, 177
  - 泛型方法, 175–176
  - HashMap 类, 164–166
  - HashSet 类, 166–167
  - 迭代器, 156
  - LinkedList 类, 167–168
  - 对象链表, 172–175
  - Queue 类, 168–169
  - TreeSet 类, 169–170
  - 同步类, 156

### G

- 垃圾收集 (Garbage Collection), 224
- 费米猜想, 95–97
- 最大公约数 (GCD), 121–122
- 当前日期时间, 33
- 日期比较, 33–34
- 解析字符串, 34–35
- SimpleDateFormat 类, 34
- 反序列化, 201–202
- d-while 循环, 100–101
- 异常
  - 检查型与未检查, 40
  - 异常处理, 39
  - 解析输入, 44–46
  - try/catch 块, 31–44
  - 导入语句, 40
  - 嵌套异常, 46–47
  - Throwable 类, 41
  - throws 关键字, 41
  - 注解, 203–204
  - 匿名内部类, 74
  - 局限性, 76
  - 命名内部类, 76
  - 数组类, 64–66
  - 数组, 102–105
  - 字符串的, 111–114
  - 基础, 38
  - 泡排序算法, 105–106
  - 字符与字符串, 110–111
  - 类, 51–52

### I

- 继承 (Inheritance), 134–136
- 接口 (Interfaces), 139
- 抽象类, 140
- 扩展, 139–140
- 方法参数, 144

### J

- Java
  - 抽象类, 140
  - 扩展, 139–140
  - 方法参数, 144
  - 类, 57–58
  - 构造函数, 128–129
  - 构造函数, 60–62
  - 无构造函数的类, 57–58
  - 重构代码, 58–60
- BufferedWriter, 196–197
- 字符与字符串, 194–195
- CSV 文件, 187–189
- 目录, 198–199
- FileWriter, 192–193
- PrintStream, 193–194
- ReadText, 187–189
- 搜索, 195–196
- WriteText, 191–192

# 开发者 Java 快速指南

### P

- 回文, 93–94
- 私有构造函数, 76–78

### R

- 递归, 117
  - 整数加, 118
  - 阶乘值, 118–119
  - 斐波那契数列, 119
  - 2 的幂, 118
  - verser() 方法, 125
- 从控制台读取输入, 185–186
- 流相关的类, 182
- 结构化查询语言 (SQL)
  - 级联删除, 2114
  - DCL, 206
  - DDL, 206
  - DELETE 语句, 213–214
  - DML, 207–208
  - DQL, 207
  - EXISTS 关键字, 212
  - GROUP BY 和 HAVING, 212
  - 索引, 214
    - 聚簇索引, 215
      - 创建, 215
      - 定义索引的注意事项, 216
      - 不可见索引, 215
      - 性能影响, 215–216
    - 唯一索引, 214
  - JOIN 关键字, 212
  - LIMIT 关键字, 213
  - MySQL (见 MySQL)
  - SELECT 关键字, 211–212
  - TCL, 208
  - TRUNCATE 和 DROP, 213
- switch 语句, 101–102

### S

- 变量作用域
  - 实例变量, 52, 54
  - 局部变量, 52, 53
  - 静态变量, 54
- 序列化, 199–201
- 单例模式, 76
- SQL 索引, 214
  - 聚簇索引, 215
    - 创建, 215
    - 定义索引的注意事项, 216
    - 不可见索引, 215



- 性能影响, 215–216
- 唯一索引, 214

静态块, 55

静态方法, 54–55, 66–67

流

- `BufferedInputStream` 类, 184–185
- `DataInputStream` 类, 185
- 描述, 181
- `FileInputStream` 类, 183–184
- `FilterInputStream` 类, 184
- `InputStream` 类, 183
- 读取面向字符的用户输入, 186–187

T

`this` 关键字, 62–64

事务控制语言 (TCL), 208

`try/catch/finally` 代码块, 47–48

U

Unicode, 35–36

W

`while` 循环, 98–99
