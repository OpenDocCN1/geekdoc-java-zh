
# 测试人员的 Java：快速掌握 Java 基础

![](img/3571bcaadac59e6bb801bc317a52cb1e_0_0.png)

联系方式：

- alan@compendiumdev.co.uk

相关网站：

- 测试人员的 Java：javaForTesters.com
- 作者的软件测试博客：eviltester.com
- Compendium Developments：compendiumdev.co.uk
- 作者的 Selenium 博客：seleniumSimplified.com

如既往。本书献给 Billie 和 Keeran。

## 引言

这是一本入门读物。有时它采用教学方法，并采用分步说明。一些熟悉编程的人可能会觉得这种方法很慢。本书并不是针对那些人的。

本书针对初次接触 Java 的人，特别是那些为了增加自动化而学习的人。其学习方法围绕编写自动化代码展开，而不是编写应用程序。书中没有涵盖自动化工具。我涵盖了编写和构建代码所需的基础知识。

我的目标是帮助你开始使用 Java 编写自动化代码，并拥有所需的基础知识。支持测试的自动化不再局限于测试人员，但这本书适用于任何想要提高 Java 使用水平的人：经理、业务分析师、用户，当然还有测试人员。

## 测试人员使用 Java 的方式不同

我记得当我开始从传统书籍学习 Java 时，我记得我对某些必须使用的概念感到不必要的困惑，例如创建清单文件和从命令行编译。

测试人员使用 Java 的方式不同。

大多数 Java 书从 `main` 类开始，展示如何从命令行编译代码并编写简单的应用程序，然后构建更复杂的 Java 结构和 GUI 应用程序。当我编写 Java 时，我很少将其编译为独立应用程序，我大部分时间都在 IDE 中，编写和运行小型检查并进行抽象层重构。

## 排除内容

这不是一份“全面”的介绍。这是一份“入门”指南。尽管我侧重于 Java，但 Java 还有某些方面我没有详细介绍，我涵盖了“恰好足够”让你理解的内容。例如：继承、接口、枚举、内部类等。

由于排除了一些内容，有些人可能会对此持有轻视的态度。因此，请将此视为一个带有个人色彩的 Java 介绍，因为我知道在最初几年的自动化编程中，我并不需要使用那些排除的内容。

我坚持认为，Java 有一套核心集合，是你开始编写自动化代码并为自动化项目创造价值所必需的。我的目标是在书中涵盖这些。

基本上，我查看了我在开始编写自动化以支持我的测试时所需的 Java 知识，并将其作为本书的范畴。虽然对接口、继承和枚举的知识都有助于让自动化抽象更具可读性和可维护性，但在早期的自动化中，我并没有使用这些构造。

我还想让这本书保持小巧且易于上手，这样人们才会真正去阅读并学习它，而不是因为太畏惧而买回来后就放在书架上。这意味着我会省略 Java 的某些部分，一旦你掌握了书中的概念，就可以自己去学习。

本书不涵盖任何 Java 1.8 的功能。与本书配合所需的最高 Java 版本是 Java 1.7。书中的代码可以在 Java 1.8 上运行，我只是没有涵盖 Java 1.8 添加的任何新功能，我希望你学习基础并快速开始产生生产力。在完成这本书后，你应该能够在需要时上手 Java 1.8 的新特性。

## 支持的源代码

你可以从 github.com 下载本书的源代码。源码包含了示例和练习题的答案。

我建议你在查看源代码之前，先通读这本书并尽力尝试。

- github.com/eviltester/javaForTestersCode

源代码被组织成两个高级源码文件夹：`main` 和 `test`。这些内容的完整意义将在后面的章节中解释。但目前，`test` 文件夹包含了你在书中使用的所有 JUnit 测试。每个章节都有一个包（package），下面都有一个练习（exercises）和示例（examples）文件夹：

- 第 3 章的 `main` 文件夹是：
  - `src\test\java\com\javaforter\chap003myfirsttest`
  - 它包含一个 `examples` 文件夹，其中包含正文中使用的所有代码
  - 它包含一个 `exercises` 文件夹，其中包含第 3 章练习题创建的所有答案代码

这应该让你更方便地浏览代码库。如果你在输入任何代码时遇到困难，可以将其与书中的实际代码进行对比以获得支持。

为了让你在不需要打开源代码的情况下阅读本书，我在正文中加入了大量代码，你可以在附录中找到大部分练习代码。

附录“IntelliJ Hints and Tips”（IntelliJ 提示与技巧）提供了加载源码的信息，并提供了一个参考章节，帮助你在 IntelliJ 中导航和处理源码。

## 关于作者

Alan Richardson 自 1995 年以来一直担任软件专业人员（尽管感觉更久了）。他主要从事软件测试，尽管他也用 C++ 以及其他各种语言编写过商业软件。

Alan 有多种在线培训课程，包括免费和商业性质的：

- "Selenium 2 WebDriver With Java"
- "Start Using Selenium WebDriver"
- "Technical Web Testing"

你可以在他的公司主网站找到其他书籍、培训课程、会议论文、幻灯片和视频的详情：

- CompendiumDev.co.uk

Alan 维护着网站：

- SeleniumSimplified.com：使用 Selenium WebDriver 进行 Web 自动化
- EvilTester.com：技术测试
- JavaForTesters.com：面向测试者的 Java

# Hello World

## 总结

我直接把你带入了深水区；给你展示了一页可能看起来晦涩难懂的内容。我这样做是为了让你快速上手 Java 编程语言。

# Java 编程语言核心概念：

- 类 (`Class`)
- 方法 (`Method`)
- JUnit
- 注解 (`Annotation`)
- 包 (`Package`)
- 变量 (`Variables`)
- 实例化变量 (`Instantiate variables`)
- 类型 (`Type`)
- 导入 (`Import`)

# 编程规范概念：

- 驼峰命名法 (`Camel Case`)
- JUnit 测试是带有 `@Test` 注解的 Java 方法

# 集成开发环境概念：

- 控制台 (`Console`)

在接下来的章节中，我将详细解释这些概念。

# 第二章 - 安装必要的软件

| 章节总结 |
| :--- |
| 在章中，你将学习 Java 编程所需的工具以及如何安装它们。你还会找到额外的常见问题解答（FAQs）和视频教程的链接，当你遇到困难时可以参考。<br><br>你将安装的工具：\n* Java 开发包 (JDK)\n* Maven\n* 集成开发环境 (IDE)\n<br><br>你还将学习如何创建你的第一个项目。\n当你完成本章后，就可以开始编写代码了。 |

*我建议你先通读整个章节，然后从头开始按照列出的步骤进行操作。*

## 引言

编程需要你配置一系列工具来完成工作。

对于 Java，这意味着你需要安装：

* JDK - Java 开发包 (Java Development Kit)
* IDE - 集成开发环境 (Integrated Development Environment)

对于本书，我们还将安装：

* Maven - 一个依赖管理和构建工具

安装 Maven 会增加设置过程的复杂度，但请相信，它会让构建项目以及将你的 Java 开发到更高水平的过程变得容易得多。

我为安装创建一个支持页面，包含了视频和故障排除指南的链接。

* JavaForTesters.com/install

如果你遇到本章或支持页面中未涵盖的问题，请告诉我，以便我尝试提供帮助、修改本章，并可能在支持页面上添加新资源。

## 你已经安装了 JDK 或 Maven 吗？

你们中的一些人可能已经在机器上安装了这些工具。我们要学会的第一件事就是检查它们是否已安装。

## Java JDK

许多人可能已经有了 JRE（Java 运行环境），但使用 Java 开发时我们需要使用 JDK。

如果你在命令行中输入 `javac -version` 并得到错误提示说找不到 javac（或类似信息），那么你需要安装并配置 JDK。

如果你看到类似的内容：

```
javac 1.7.0_10
```

那么你已经安装了 JDK。值得注意的是下面的指令，用它可以检查你安装的 JDK 是否为最新，但如果你安装了 1.7.x（或更高版本）的 JDK，那么就有足够版本来完成本书而无需任何修改。如果你的 JDK 是 1.6，那么某些代码示例将无法运行。

![](img/3571bcaadac59e6bb801bc317a52cb1e_17_0.png)

## Java 有多个版本

Java 随着时间的推移不断改进。每个新版本都会添加新功能。如果你不幸无法在公司安装 Java 1.7（那么我建议你在家里或在虚拟机上学习本书），那么部分源代码将无法运行，且你为本书下载的代码将会报错。

具体来说，我们涵盖了 Java 1.7 引入以下功能：

- 集合章节中的菱形运算符 `<>`
- 二进制字面量，例如 `0b01001`
- 字面量中的下划线，例如 `0_000_000_000L`
- 使用字符串的 switch 语句

上述语句现在可能还没有意义，但如果你使用的 Java 版本低于 1.7，那么你可以预期这些概念在 JDK 1.6 或更低版本中会报错。

## 安装 Maven

Maven 需要安装对应版本的 Java，所以如果你检查了 Java 发现它不存在，你就需要安装 Maven。

如果你在命令行中输入 `mvn -version` 并收到错误提示找不到 mvn（或类似信息），那么在遵循本书内容之前，你需要安装并配置 Maven。

如果你看到类似的内容：

```
Apache Maven 3.0.4 (r1232337; 2012-01-17 08:44:56+0000)
Maven home: C:\maven\maven-3.0.4
Java home: 1.7.0-Program Files\Java\jdk1.7.0_10\jre
Default locale: en_GB, platform encoding: Cp1252
OS name: "windows", version: "6.2", arch: "amd64", family: "windows"
```

![](img/3571bcaadac59e6bb801bc317a52cb1e_17_1.png)

那么你已经安装了 Maven。本书不需要特定的 Maven 版本，但拥有 3.x.x 或更高版本应该是可以的。

## 安装 Java JDK

可以从 oracle.com 下载 Java JDK。如果你误下载了 java.com，那么你下载的是 JRE，而对于开发工作我们需要 JDK。

* oracle.com/technetwork/java/
* oracle.com/technetwork/java/downloads

安装应该使用适用于你平台的标准安装方法。

你可以通过打开命令行并运行以下命令来检查 JDK 是否安装：

```
javac -version
```

这应该显示你从 oracle.com 下载并安装的版本号。

## 安装 Maven

Maven 是一个依赖管理和构建工具。我们将使用它向项目中添加 JUnit。

Maven 官方网站是 maven.apache.org。你可以在下载页面下载 Maven 并找到安装说明。

* maven.apache.org/download.cgi

## 安装指令

我总结了下方的说明：

* 解压你想要安装 Maven 的压缩包
* 创建一个环境变量 `M2_HOME`，指向上述目录
* 将 `M2_HOME/bin` 添加到你的路径 (`path`) 中
* 在 Windows 上，使用 `%M2_HOME%`
* 在 Unix 上，使用 `$M2_HOME/bin` 添加到路径
* 确保你有一个环境变量 `JAVA_HOME`，指向你的 JDK 根目录

你可以通过打开一个新的命令行并运行命令来检查它是否已安装：

```
mvn -version
```

这应该显示你刚刚安装的版本号以及你的 JDK 路径。

我建议你花时间阅读 Maven 官方网站上的“5 分钟上手 Maven”指南：

* maven.apache.org/guides/getting-started/maven-in-minutes.html

## 安装 IDE

虽然书中的代码可以在任何 IDE 中运行，但我建议你使用 IntelliJ。我发现 IntelliJ 对初学者很好，因为它往往比 Eclipse 更能识别路径和默认位置。

对于本书，我将使用 IntelliJ，我为本书创建的任何支持视频或提到的任何与 IDE 相关的快捷键将假设你正在使用 IntelliJ。

IntelliJ 官方网站是 jetbrains.com/idea

IntelliJ 有两个版本：免费的“社区版 (Community)”和需要付费的“旗舰版 (Ultimate)”。

对于本书以及你的大部分自动化开发工作，“社区版”将满足你的需求。

从此处下载社区版 IDE：

* jetbrains.com/idea/download

当你熟悉了书中的概念后，可以尝试其他 IDE，例如 Eclipse 或 Netbeans。

我建议在你更熟悉 Java 之前一直使用 IntelliJ，因为这样可以最大程度地减少因 IDE 误导你认为 Java 出了问题的风险。

## 使用 IDE 创建项目

要创建你的第一个项目，请让 IntelliJ 完成繁琐的工作。

* 启动你已安装的 IntelliJ
* 选择 `File \ New Project`
* 在新项目向导中：
  * 选择 Maven Module
  * 输入项目名称，例如 javafortesters
  * 为项目源码选择一个位置
  * IntelliJ 应该找到你已安装的 JDK
  * 点击 Next（下一步）

你可以直接使用向导的所有默认设置。

## 关于你的新项目

“新建项目”向导将创建一个结构如下的新文件夹：

- javaForTesters
- .idea
- src
- main
- java
- resources
- test
- java
- javaForTesters.iml
- pom.xml

在上述层级结构中：

- `.idea` 文件夹是存储大多数 IntelliJ 配置文件的地方，
- `.iml` 文件包含其他 IntelliJ 配置详情，
- `pom.xml` 文件是你的 Maven 项目配置文件。

如果你在任何一个目录中创建了任何 `.java` 文件，可以删除它们，因为它们并不重要。你将从零开始这个项目。

上述目录结构是标准的 Maven 结构。Maven 期望某些文件位于特定的目录，以便使用默认的 Maven 配置。由于你只是刚刚开始，可以保持目录结构不变。

为了让你作为初级开发者的工作更轻松，你将遵循某些约定：

- 将你的单元测试类放在 `src\test\java` 目录层级中
- 创建单元测试类时，确保在类名后加上 `Test`

`src\main\java` 目录层级用于不用于断言行为的 Java 代码。通常是应用程序代码。我们将用它来编写抽象层代码。你可以将创建的代码添加到 `src\test\java` 层级中，但在可能的情况下，我将抽象代码拆分到了单独文件夹中。

上面的描述目前可能没有意义，但希望随着你阅读这本书，它会变得清晰。现在先不要担心它。

`pom.xml` 文件可能看起来像：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0">
```

```xml
<project xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
     http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>JavaTesters</groupId>
  <artifactId>JavaTesters</artifactId>
  <version>1.0-SNAPSHOT</version>
</project>
```

这是空文件的基础并定义了项目的名称。

你可以在 Maven 网站上找到关于 `pom.xml` 文件的信息。

- [maven.apache.org/pom.xml](http://maven.apache.org/pom.xml)

## 将 JUnit 添加到 pom.xml 文件

我们将使用名为 JUnit 的库来帮助我们运行代码。

- [junit.org](https://junit.org)
- [github.com/junit-team/junit/wiki/Download-and-Install](https://github.com/junit-team/junit/wiki/Download-and-Install)

你可以在 JUnit 网站上找到使用 Maven 使用 JUnit 的安装说明。

我们基本上通过编辑 `pom.xml` 文件来包含对 JUnit 的依赖。我们通过创建一个 `dependencies` 元素和一个 `dependency` XML 元素来定义我们想要使用的 JUnit 版本。在编写时，它是第 4.11 版本。

我们在本书中使用的 `pom.xml` 文件只需要 JUnit 依赖，所以它看起来像这样：



```xml
<xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
     xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
     xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>JavaTesters</groupId>
  <artifactId>JavaTesters</artifactId>
  <version>1.0-SNAPSHOT</version>
  <packaging>jar</packaging>
  <properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
  </properties>
  <dependencies>
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>4.11</version>
    </dependency>
  </dependencies>
  <build>
    <plugins>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-compiler-plugin</artifactId>
        <version>3.1</version>
        <configuration>
          <source>1.7</source>
          <target>1.7</target>
        </configuration>
      </plugin>
    </plugins>
  </build>
</project>
```

你可以看到我还添加了一个带有 Maven 输出警告的 `build` 部分。如果你真的想让 `pom.xml` 文件变小，可以只添加 `<dependencies>` XML 元素及其所有关于 JUnit 的包含信息。

修改你的 `pom.xml` 文件以包含上述 `dependencies` 和 `build` 元素。IntelliJ 应该为你下载 JUnit 依赖，以便你在下一章中编写 JUnit 测试。

你可以在 Maven 网站上找到关于该插件的更多信息：

- [maven.apache.org/plugins/maven-compiler-plugin](http://maven.apache.org/plugins/maven-compiler-plugin)

## 总结

如果你遵循了本章的指令，你现在应该拥有：

- 安装了 Maven - `mvn -version`
- 安装了 JDK - `javac -version`
- 安装了 IntelliJ IDE
- 创建了你的第一个项目
- 一个带有 JUnit 依赖的 `pom.xml` 文件

# 第三章 - 编写你的第一个 Java 代码

## 总结

在本教程中，你将跟随文本创建你的第一个 JUnit 测试。你将学习到：

- 组织类
- 创建类
- 如何运行 Java
- 如何从命令行运行
- 如何编写 Java
- 关于 Java

上面的描述目前可能没有意义，但希望随着你阅读这本书，它会变得清晰。现在先不要担心它。

## 我的第一个 JUnit 测试

我们首先要创建的是一个类，向其中添加我们的测试方法。

类是 Java 代码的基本构建模块。所以我们要创建一个名为 `MyFirstTest` 的类。

`MyFirstTest` 这个名字有一些重要的特征：

```java
package com.javafortesters;
import org.junit.Test;
import static org.junit.Assert.assertEquals;

public class MyFirstTest {

    @Test
    public void addTwo() {
        int answer = 2+2;
        assertEquals("2+2", 4, answer);
    }
}
```

## 前提条件

我假设你已经准备好了以下内容：

- 已安装 JDK
- 已安装 IDE
- 已安装 Maven
- 已创建项目
- 在 pom.xml 中添加了 JUnit

我已经安装了本章列出的三个工具（JDK, Maven, IDE）。

安装应该是简单的，但可能会出现问题。

我在 JavaTesters.com/install 网站上创建了一些视频，展示如何安装这些工具。

- [JavaTesters.com/install](http://JavaTesters.com/install)

我在“Java For Testers”博客上添加了一些 Maven 故障排除提示和技巧：

- [javafortesters.blogspot.co.uk/2013/08/maven-troubleshooting-and-tips.html](http://javafortesters.blogspot.co.uk/2013/08/maven-troubleshooting-and-tips.html)

如果你卡住了，尝试使用你常用的搜索引擎并将收到的准确错误信息粘贴到搜索引擎中，你可能会发现已经有人解决了相同的问题。

## 需要导入 Maven 项目

作为代码，如果你在 IntelliJ 中看到弹出一个小窗口，说“Maven Projects need to be imported”（Maven 项目需要导入），点击“Enable Auto-Import”（启用自动导入）。这将使你的工作变得更容易，因为它会在你更新代码或更改 `pom.xml` 文件时自动导入语句。

## 创建类

在 IDE 中，弹出项目层次结构，这样你就可以看到 `src\test\java` 分支和 `src\main\java` 分支。

我的项目层次结构如下：

- javaForTester
- .idea
- src
  - main
    - java
    - resources
  - test
    - java

`.idea` 是 IntelliJ 的文件夹，所以我可以忽略它。

我右键点击 `test` 下的 `java` 文件夹，选择 `New \ Java Class` 菜单。

或者，我可以点击 `test` 下的 `java` 文件夹并使用快捷键 `alt + insert`，选择 `Java Class`（Mac 使用 `ctrl + n`）。

输入你想创建的 Java 类名称，例如 `MyFirstTest`，并点击 [OK]。

暂时不要担心包结构。我们以后可以轻松手动移动代码，或者让 IntelliJ 使用重构为我们移动。

## 模板代码

你可能会发现 IntelliJ 自动添加了一段注释块：

```java
/*
* Created with IntelliJ IDEA.
* User: Alan
* Date: 24/04/13
* Time: 11:48
* To change this template use File | Settings | File Templates.
*/
```

你可以忽略这段代码，因为它是一段注释。如果你愿意，可以删除所有这些行。

## Java 注释介绍

```java
/* 使用斜杠星号创建的注释
支持跨多行 */
```

## 将类添加到包中

IntelliJ 已经为你创建一个空类，例如：

```java
public class MyFirstTest {
}
```

由于我们没有指定包，它将位于我们 `test\java` 层次结构的根目录级别。

我们有两种方法来创建包并将类移动到其中：

- 手动创建包并将类拖入其中
- 在我们的代码中添加包语句并让 IntelliJ 移动类

通过右键点击 `test` 下的 `java` 文件夹并选择 `New \ Package`，然后输入你想创建的包名，来手动创建包并将类拖入。

对于这本书，我建议你使用顶层包结构：

- com.javafortesters

然后根据需要对任何子结构命名。对于这个类，我们可以创建一个名为 `com.javafortesters.chap003myfirsttest.examples` 的包。你不需要使用 `chap003` 前缀，但它可能帮助你将代码追溯到书中的章节。我使用这种约定来帮助你在源码下载中找到示例和练习源码。

## 包的命名

在 Java 中，包名倾向于全小写，且不使用驼峰命名法。

如果我们愿意，可以在代码中添加包语句并让 IntelliJ 移动类：

在类的第一行添加以下内容：

```java
package com.javafortesters.chap003myfirsttest.examples;
```

行末的分号是重要的，因为 Java 语句以分号结束。

IntelliJ 会用红色下划线高亮此行，因为我们的类并不在代表该包的文件夹结构中。

IntelliJ 不仅仅能告诉我们问题所在，如果我们点击带有下划线的文本并按下 `alt + return` 键，它还能为我们解决这个问题。

IntelliJ 会弹出一个菜单，为我们提供以下选项：

- 移动到包 `com.javafortesters.chap003myfirsttest.examples`

选择此选项，IntelliJ 将自动将类移动到正确位置。

![](img/3571bcaadac59e6bb801bc317a52cb1e_28_0.png)

## 你也可以先创建包

当然，我也可以先创建包，但有时我喜欢先创建类并专注于代码编写，然后再专注于代码的排序和分类。

随着你经验的增加，你将发展出自己的编码风格。我喜欢让 IDE 尽可能完成工作，这样我可以保持在编码的“心流”中。

## 空类解释

```java
package com.javafortesters.chap003myfirsttest.examples;
public class MyFirstTest {
}
```

如果你遵循了操作，你将拥有一个空类，它位于正确的包中，且项目窗口将显示与你创建的包层次结构匹配的目录结构。

## 包语句

包语句是定义该类所属包的行代码。

```java
package com.javafortesters.chap003myfirsttest.examples;
```

当我们后续的代码中使用此类时，我们将从该包导入该类。

包语句映射到我们 `src\test` 文件夹下的物理结构。如果你探索项目文件夹，你会发现包实际上是嵌套的文件夹。

- src
  - test
    - java

在 `java` 文件夹下方，你会看到代表包结构的文件夹结构。

- com
  - javafortesters
  - chap003myfirsttest
  - examples

Java 类在作用域内必须唯一。

## 类声明

以下行是我们的类声明：

```java
public class MyFirstTest {
}
```

我们在使用类之前必须对其声明。

## 作用域

该方法声明为 public，意味着任何类都可以使用 `MyFirstTest`。

当我们使用 JUnit 时，任何想要作为 JUnit 测试的方法都应该声明为 public。

## Java 有更多作用域声明

> Java 有其他作用域声明，如 private 和 protected，但我们现在不需要考虑它们。

当我们创建将要使用的类时，我们需要将它们声明为 public。

`{` 和 `}` 是块标记。左括号 `{` 标记块的开始，右括号 `}` 标记块的结束。

我们为类编写的所有代码必须放在左括号和右括号之间，这代表类体。

在这种情况下，体是空的。

## 创建方法

我们将创建一个方法来相加数字。具体说是 2+2。

我通过输入方法声明来创建一个方法：

```java
public void canAddTwo()
```

记住，方法声明包含在类体内部：

```java
public class MyFirstTest {
  public void canAddTwo() {
  }
}
```

由于 `@Test` 注解随 JUnit 一起提供，我们需要将其导入到代码中。

当你在方法声明之前的行上输入 `@Test` 时，IDE 会将其标记为错误。

```java
@Test
public void canAddTwoPlusTwo(){
}
```

当我们点击带有错误的行并按下组合键 `alt + return` 时，我们会获得一个选项来执行：

- Import Class（导入类）

选择该选项将导致 IntelliJ 在我们的类中添加导入语句。

`import org.junit.Test;`

我们必须确保仔细查看导入选项列表。有时我们会看到多个选项，因为可能存在许多同名的类，它们的区别在于所处的包。

![](img/3571bcaadac59e6bb801bc317a52cb1e_31_0.png)

## 如果你选择了错误的导入

如果你不小心选择了错误的导入，只需从代码中删除现有的导入语句，然后使用 IntelliJ 的 `alt + return` 来纠正类和包。

## 计算和

为了实际计算 2+2 的和，我需要创建一个变量，然后我可以将计算结果存储在变量中。

```java
int answer = 2+2;
```

变量是代表其他值的符号。在编程中，我们使用变量来存储值：字符串、整数等，以便我们可以在程序代码中使用并修改它们。

我将创建一个名为 `answer` 的变量。

我将变量设为 `int`，这声明了变量的类型。`int` 是 integer（整数）的缩写，是一种基本类型，所以除了为我们存储整数值外，它没有很多功能。`int` 不是一个类，因此它没有任何方法。

代码中的符号 `2` 被称为数字字面量或整数字面量。

![](img/3571bcaadac59e6bb801bc317a52cb1e_31_1.png)

## int 有局限性

`int` 可以存储从 -2,147,483,648 到 2,147,483,647 之间的值。例如：

```java
int minimumInt = -2147483648;
int maximumInt = 2147483647;
```

当我创建变量时，我将将其设为 2+2。

Java 会为我们完成计算，我使用了 `+` 运算符。`+` 运算符作用于两个 `int` 操作数并返回一个结果。即：它将 2 加到 2 并返回值 4，该值将存储在 `int` 变量 `answer` 中。

## Java 运算符

Java 有几个我们可以使用的明显运算符：

- `+` 加法
- `-` 减法
- `*` 乘法
- `/` 除法

还有更多，但我们稍后会介绍。

## 断言值

我们需要做的下一件事是断言该值。

```java
assertEquals("2+2=4", 4, answer);
```

当我们编写 `@Test` 方法时，必须确保我们断言某些内容，因为我们希望确保代码能够自动向我们报告失败。

Assert（断言）是一种特殊的检查：

- 如果检查失败，assert 将抛出一个断言错误，我们的方法将失败。
- 如果检查通过，assert 不产生任何副作用。

我们最初在代码中使用的断言来自 JUnit Assert 包。

当我输入 assert 时，IntelliJ 会显示该语句处于错误状态，因为我没有从 JUnit 导入 `assertEquals` 方法或类。

要修复错误，在 `assertEquals` 语句上按 `alt + return` 并选择：

- static import method...（静态导入方法...）
- org.junit 包中的 Assert.assertEquals

IntelliJ 随后将向我的代码中添加正确的导入语句。

```java
import static org.junit.Assert.assertEquals;
```

`assertEquals` 方法是多态的。简单来说，它可以用于不同类型的参数。

我选择使用如下形式的形式：

```java
assertEquals("2+2=4", 4, answer);
```

其中：

- `assertEquals` 是一个检查两个值是否相等的断言。
- `"2+2=4"` 是在断言失败时显示的消息。
- `4` 是一个代表预期值的整数字面量，即：我期望 2+2 等于 4。
- `answer` 是 `int` 变量，包含了我想要与预期值进行比对的实际值。

我本可以这样写断言：

```java
assertEquals(4, answer);
```

我没有添加消息，所以如果断言失败，告诉我应该发生什么的线索就少了，在某些情况下，我可能甚至要在代码中添加注释来解释断言的作用。

我尽量记得在使用 JUnit 断言方法时添加消息，因为这使得代码更易读，并在断言失败时提供帮助。

注意，在两种形式中，**预期结果**都在**实际结果**之前。

如果你顺序反了，JUnit 不会抛出错误，它不知道你的意图，但失败断言的输出会误导你。例如，如果在初始化 `int` `answer` 时我不小心写了 2+3，并且把**预期**和**实际**结果放反了，那么输出将类似于：

`java.lang.AssertionError: 2+2=4 expected:<5> was:<4>`

这会让你感到困惑。



# 练习：检查 JUnit 测试类的命名

当你在从 IDE 运行 JUnit 测试类时，它们不需要在名称的开头或结尾带有“Test”。但为了从 Maven 运行，它们需要遵循这一命名规范。请验证这一点。

创建一个类，其中包含一个会执行失败的方法，例如 `assertTrue(false);`。按照不同的规则重命名该类并在 IDE 中运行它，你会发现命名会产生影响。

- 以 Test 开头，例如 `TestClassName`，在 IDE 和 Maven 中都可以运行
- 以 Test 结尾，例如 `NameTest`，在 IDE 和 Maven 中都可以运行
- Test 在中间，例如 `NameTestClass`，在 IDE 中可以运行但在 Maven 中不运行
- 不带 Test，例如 `NameClass`，在 IDE 中可以运行但在 Maven 中不运行

## 参考文献和推荐阅读

- Wikipedia 上的驼峰命名法 (en.wikipedia.org/wiki/CamelCase)
- Java 官方文档 - 什么是对象？ (docs.oracle.com/javase/tutorial/concepts/object.html)
- 什么是类？ (docs.oracle.com/javase/tutorial/concepts/class.html)
- Java 教程 - 命名规范 (docs.oracle.com/javase/tutorial/java/naming.html)
- Java 代码块 (docs.oracle.com/javase/tutorial/java/nutsandbolts/expressions.html)
- Java 运算符 (docs.oracle.com/javase/tutorial/java/nutsandbolts/operators.html)
- JUnit - 主页 (junit.org)
- 文档 (github.com/junit-team/junit)
- API 文档 (junit.org/javadoc/latest)
- Test (junit.org/javadoc/latest/Test.html)
- IntelliJ 导入设置 (jetbrains.com/idea/webhelp/importing.html)

# 第四章 - 类操作

在本章中，你将学习：

- 如何使用另一个类的静态方法
- 如何将类实例化为对象
- 如何访问静态字段和常量
- `Integer` 和实例化之间的区别

在本章中，你将学习如何在你的 `@Test` 方法中使用其他类。最终这些将是你编写的类，但目前我们将使用 Java 内置的其它类。你已经在上一章中做过这些，所以你可能没有注意到（我将在下一章解释 `static` 的含义）。但在之前，这里有一些关于如何学习 Java 的指导。

## 使用 Test 方法理解 Java

当我处理 Java 工作时，我鼓励他们编写断言（assertions），这有助于他们理解这些库。例如，你已经见过一种名为 `int` 的原始数据类型。Java 还提供了一个名为 `Integer` 的类。因为 `Integer` 是一个类，它拥有我们可以调用的方法，而且我们可以将对象变量实例化为 `Integer`。当我创建一个 `int` 变量时，我能做的只是在变量中存储数字并检索该数字。

- `compareTo` - 与另一个整数比较
- `intValue` - 返回一个 `int`
- `longValue` - 返回一个 `long` 原型
- `shortValue` - 返回一个 `short` 原型

## 使用 Test 方法探索 Integer 类

事实上，你可以亲眼看到整数可用的方法。

- 创建新包：`com.java.chap04.testwithotherclasses.examples`
- 创建新类 `IntegerExamplesTest`
- 创建方法 `integerExploration`
- 使用 `@Test` 注解该方法，以便用 JUnit 运行它

你最终得到的应该像这样：

```java
package com.java.chap04.testwithotherclasses.examples;

import org.junit.Test;

public class IntegerExamplesTest {

    @Test
    public void integerExploration(){
    }
}
```

我们可以使用这个，这被称为对 `Integer` 类进行实验。

## 实例化 Integer 类

我们需要做的第一件事是创建一个 `Integer` 类型的变量。

```java
Integer four = new Integer(4);
```

因为 `Integer` 是一个类：

- `int` 是一个原始类型。
- `Integer` 是一个类。
- 在使用类时通过 `new` 关键字实例化
- 使用 `new` 关键字创建类的实例

我们只需要将 `int` 赋值给 `Integer`，自动装箱（autoboxing）就会为我们处理，例如：

## 什么是构造函数？

> 构造函数是在创建类实例时调用的方法。

一个类构造函数可以接收参数，但没有返回类型。例如 `Integer(int value){...}` 构造函数的名称与类名相同，且首字母大写。

`Integer` 类实际上有多个构造函数。你可以亲眼看到：

- 使用 `new` 关键字实例化一个值为 4 的 `Integer`
- 在括号内输入 4
- 按快捷键 `ctrl + p`（Mac 上为 `cmd + p`）

你会看到一个弹窗，显示构造函数可以接受的形式。

## 检查 intValue 是否返回正确的 int

我们知道 `Integer` 类有一个返回 `int` 的方法 `intValue`，所以我们可以创建一个断言来检查返回值。在实例化 `Integer` 的语句之后：

添加一个新的语句，断言 `intValue` 返回值为 4 的 `int`。

```java
assertEquals("intValue returns 4", four.intValue());
```

当你运行这个方法时，它应该通过。

我们看到看到 Integer 的构造函数之一可以接收字符串，所以让我们写一些代码来测试它。

- 创建一个新的 `Integer` 变量，使用字符串 "5" 调用 `Integer` 构造函数
- 断言 `intValue` 返回整数 5

```java
Integer five = new Integer("5");
assertEquals("intValue returns 5", five.intValue());
```

## 快速总结

这可能看起来没什么，但我们刚刚涵盖了一些重要的点。

- 你有没有注意到不需要导入 `Integer` 类？因为它在 `java.lang` 包中，我们不需要导入它们。
- 我们学习了要使用类需要通过 `new` 关键字进行实例化。
- 在我们使用的 Java 版本中，我们不需要实例化类就可以调用静态方法。
- 使用 `ctrl + p` 让 IDE 显示所有静态方法的代码补全（Mac 上为 `cmd + p`）。
- 对于这些每个方法，如果你按下 `ctrl + q`（Mac 上为 `ctrl + j`），你应该能看到该方法的帮助文件信息。

## 自动装箱 (AutoBoxing)

在我们使用的 Java 版本中，我们不需要通过 `new` 关键字实例化类。自动装箱（Autoboxing）会自动将原始类型转换为关联类。因此，我们只需将一个 `int` 赋值给 `Integer`，自动装箱就会为我们处理，例如：

```java
Integer six = 6;
assertEquals("autoboxing assignment for 6", six.intValue());
```

`MIN_VALUE` 和 `MAX_VALUE` 包含了 `int` 支持的最小值和最大值。建议使用这些值而不是 -2147483648 和 2147483647，以确保未来的兼容性和跨平台兼容性。

要访问常量，你不需要添加圆括号，因为你访问的是变量，而不是调用方法。

例如，你写的是 `Integer.MAX_VALUE` 而不是 `Integer.MAX_VALUE()`。

## 练习：确认 Integer 的最大值最小值

在上一节中，我们提到 `int` 的范围是从 -2147483648 到 2147483647。`Integer` 类有静态常量 `MIN_VALUE` 和 `MAX_VALUE`。

编写一个带有 `@Test` 注解的方法，来断言：

- `Integer.MIN_VALUE` 等于 -2147483648
- `Integer.MAX_VALUE` 等于 2147483647

## 定期这样做

我鼓励你定期执行以下操作。

当你遇到：

- 任何你不知道如何使用的 Java 库
- 你不确定的 Java 部分
- 你的团队中你没有编写且不理解的代码

那么你可以：

- 阅读文档 - `ctrl + q` (Mac 上为 `ctrl + j`) 或在线网络文档
- 读取源码 - 按住 `ctrl` 并点击方法以查看源码
- 编写一些带有 `@Test` 注解的方法，并使用断言（assertions）来帮助你探索库的功能

在编写 `@Test` 方法时，你需要记住以下几点：

- 只编写恰好触发功能的代码
- 确保你编写的断言语句能够良好地覆盖功能且具有可读性
- 对“异常”情况进行实验

当你以后为自己的代码编写断言时，这会对你有帮助。

## 关于 Integer 的警告

我在这一章使用了 `Integer`，是因为我们在较早的章节中使用了 `int` 原始数据类型，而 `Integer` 是相关的后续类。

但是……有经验的开发者会担心你开始在代码中使用 `Integer`，并担心在代码中实例化新的整数，例如 `new Integer(0)`。

他们担心是因为，虽然一个 `int` 等于另一个 `int`，但一个 `Integer` 并不总是等于另一个 `Integer`。

我不那么担心，是因为：

- 我信任你，
- 代码的用法与生产代码略有不同，你更有可能使用 `Integer` 的静态方法
- 我正将其作为实例化类和使用静态方法的示例
- 这只是“第四章”，我们还有很长的路要走

我将通过代码示例说明为什么有经验的开发者会担心。你可能无法理解接下来的几段，但我只想告诉你一个细节，即为什么一个 `Integer` 或一个 `Object` 并不总是等于另一个 `Object`。

例如，如果以下断言位于 `@Test` 方法中，它们将通过：

```java
assertEquals(4,4);
assertTrue(4==4);
```

注意 `==` 是 Java 中检查一个东西是否等于另一个的运算符。

如果以下代码在 `@Test` 中，第二个断言将失败：

```java
Integer firstFour = new Integer(4);
Integer secondFour = new Integer(4);

assertEquals(firstFour, secondFour);
assertTrue(firstFour==secondFour);
```

具体来说，以下断言将失败：

```java
assertTrue(firstFour==secondFour);
```

为什么呢？

嗯，原始类型（primitives）是简单的，对于原始类型来说，值和标识（identity）没有区别。代码中的每个 4 都指代同一个 4。

对象是不同的，我们实例化它们，所以两个 `Integer` 变量（`firstFour` 和 `secondFour`）都引用了不同的对象。尽管它们有相同的“值”，但它们是不同的对象。

当我执行 `assertEquals` 时，JUnit 使用对象上的 `equals` 方法来比较“值”或顺序（即在本例中为 4）。当我们使用 `==` 运算符时，Java 正在检查这两个对象是否指向同一个实例化对象，而它们并没有，它们指向两个独立实例化的对象。

所以 `assertEquals` 实际上等同于：

```java
assertTrue(firstFour.equals(secondFour));
```

如果你现在还不理解这个，不要担心。它以后会变得清晰。

现在，请记住：

- 你可以使用 `new` 关键字创建类的对象实例，并使用类上的非静态方法，例如 `Integer.intValue()`
- 你可以在不实例化类为对象的情况下访问类上的静态方法，例如 `Integer.equals(..)`

## 总结

你学习了在 IntelliJ 中，你可以按住 `ctrl` 然后点击左鼠标键来点击方法名并查看源码。

你学习了以下快捷键：

| 功能 | Windows | Mac |
| --- | --- | --- |
| 显示参数 | `ctrl + p` | `cmd + p` |
| 显示 JavaDoc | `ctrl + q` | `ctrl + j` |

你还学习了静态方法以及对象值与对象标识之间的区别。

无论你在书中学了什么，请确保你继续通过编写断言来不断实验。

你还学习了如何实例化一个新对象以及构造函数的作用。

## 参考文献和推荐阅读

- 创建对象
  - docs.oracle.com/javase/tutorial/javaOO/objectcreation.html
- 自动装箱
  - docs.oracle.com/javase/tutorial/data/autoboxing.html
- Integer
  - docs.oracle.com/javase/tutorial/lang/Integer.html

# 第五章 - 使用自定义类

## 章总结

在本章你将学习：

- 编写你自己的类
- 查看静态与非静态方法的区别
- 调用方法
- 创建静态常量
- 使用 IDE

## 背景

对于本章的示例，我们将查看一个名为 `TestAppEnv` 的环境对象，它代表我们运行自动化测试和断言的环境。

假设你有一个待测试的应用程序，你将其安装在了多个测试环境中，你想在其中任何一个环境中运行自动化代码（可能包括线上环境）。

你不需要在每次使用不同环境时修改自动化代码，因此你想将实际的环境配置抽象到一个对象后面，由它来为你处理。

而不是像这样在 `@Test` 方法中写：

```java
@Test
public void checkTitleCorrectOnApp(){
    FirefoxDriver driver = new FirefoxDriver();
    driver.get("http://192.123.0:67");
    assertEquals("Title should match",
    "Test App", driver.getTitle());
}
```

注意：上面的示例使用了 WebDriver API，所以如果你直接输入它是无法工作的。它的意思是：使用 Firefox 浏览器，打开 URL "http://192.123.0:67" 并检查页面标题是否为 "Test App"。

你可以将连接细节抽象到环境领域对象，例如 `TestAppEnv`。

```java
@Test
public void checkTitleCorrectOnAppDomainObject(){
    FirefoxDriver driver = new FirefoxDriver();
    driver.get(TestAppEnv.getUrl());
    assertEquals("Title should match",
    "Test App", driver.getTitle());
}
```

通过这样做，你不再需要在所有的 `@Test` 方法中硬编码字符串字面量 "http://192.123.0:67"，而是调用对象 `TestAppEnv.getUrl()`。

通过遵循本章的文本，你将构建 `TestEnv` 类，以及相关的 `@Test` 方法和断言。

## 首先创建一个 @Test 方法

我们想要做的的第一件事是创建一个 `@Test` 方法。

为了实现这一点，我们需要一个类来存放该方法。

- `@Test` 方法位于你项目的测试文件夹层级结构中。
- 我将创建一个包
  - `com.javaforesters.chap05.testwithourownclasses.domainobject.example`
- 然后在那个包中，创建一个名为 `TestAppEnvironmentTest` 的类。

![](img/3571bcaadac59e6bb801bc317a52cb1e_46_0.png)

## 关于包和 JUnit 测试类创建的提示

使用项目树（Project Tree）来创建包。在相应的 `src` 分支（例如 `src\test\java`）上点击相关包，右键并选择 `New` > `Package`。输入包名。

如果弄错了，请删除并重新开始，或者直接使用项目树将其拖动到正确的位置。

使用项目树创建类。重复上述操作，但在你想要创建类的包中选择 `New` > `Java Class`。

```java
package com.javaforesters.chap05.testwithourownclasses.domainobject.examples;

public class TestAppEnvironmentTest {
```

然后添加一个 `@Test`。我将创建一个名为 `getUrlStatically` 的方法，因为我决定我希望能够静态地从 `TestApp` 类中检索 URL，而不是在每次想使用它时实例化一个新的 `TestAppEnv` 实例。

```java
@Test
public void getUrlStatically(){
}
```

![](img/3571bcaadac59e6bb801bc317a52cb1e_46_1.png)

## 关于 @Test 方法创建的提示



在类的体内部、在起始（`{`）和结束（`}`）代码块之间创建方法代码。

记得添加 `import org.junit.Test;` 来导入 `@Test` 注解，因为 IDE 不会自动添加它。

## 编写不存在的代码

由于我还没有创建 `TestAppEnv` 类，我使用它编写的任何代码都无法工作。

那么自然的倾向就是去创建 `TestAppEnv` 类，编写代码，然后返回我们的 JUnit 测试类并编写方法和断言来检查它。

我们不打算这样做。我们将通过编写自动化代码来驱动代码的创建。

因此，在 `cangetUrlStatically` @Test 方法中，我们将编写我们想要看到的输出代码。

实际上，我们正在通过在用上下文中看到它来设计代码。

所以在我的 `cangetUrlStatically` 方法中，我写了这一行：

```
assertEquals("Returns Hard Coded URL",
"http://192.123.0:67",
TestAppEnv.getUrl());
```

我们可以自动从 JUnit 包中添加 `assertEquals` 的导入。但 IDE 会报错说无法解析符号 `TestAppEnv`。这并不意外，因为我们还没有写它。

但我们将让 IDE 来繁重的工作，让它为我们创建该类。

## 创建一个类

点击 `TestAppEnv` 并按下 `alt + enter`（IntelliJ 意图操作快捷键），你将看到一个修复选项的小弹出菜单。类似于：

- 创建本地变量 'TestAppEnv'
- 创建类 'TestAppEnv'
- 创建字段 'TestAppEnv'
- 创建内部类 'TestAppEnv'
- 创建参数 'TestAppEnv'
- 等。

对我们来说重要的是**创建类 'TestAppEnv'**。

选择类 'TestAppEnv'，然后我们需要告诉 IDE 我们想在哪里创建它。

我们将使用不同的包。

我们使用包来组织代码，仅仅因为我们这一章的 @Test 方法代码被组织在一个包中，并不意味着我们的领域对象也需要放在同一个包中。

我将使用一个包：

```
package com.javaforesters.domainobject;
```

由于这个类是我抽象层的一部分，我不希望它在 `src\test\java` 文件夹结构中，我希望它在我的主代码 `src\main\java` 中。确保你更改目标位置并在那里创建。

## 如果弄乱了也不要

尝试选择好的名称是重要的，但不要纠结于此也很重要，因为一旦代码运行，将代码组织到不同的包中是非常容易的，IDE 也有许多自动化重构工具可以完成这一点。

我将常量设置为我们最初在 `getUrl` 方法中返回的字符串值。

如果我们运行 `@Test` 方法，它们应该能够通过的。

# 现在进行重构

TDD（测试驱动开发）以及所有编程中的一个重要元素就是重构。

这意味着回头。审视我们的代码。识别浪费和改进之处。并修改代码，使得带有 `@Test` 注解的方法继续通过，且不修改代码的任何外部接口。

在我们的情况下，这意味着只要 `TestAppEnv` 中仍然保留两个名为 `DOMAIN` 和 `PORT` 的字段，以及一个返回与断言所需的相同字符串对象的 `getUrl` 方法，我们就可以更改 `TestAppEnv` 中的任何代码。

显然需要更改的地方是，我们的领域对象中有重复的字符串字面量，因为我们的域名字符串和 `PORT` 字符串作为 `getUrl` 中硬编码字符串的一部分重复出现了。我有这样的一行：

```java
return "http://192.123.0:67";
```

# 简单的字符串拼接

由于 `DOMAIN` 常量和 `PORT` 常量的值是 `getUrl` 中硬编码字符串的一部分，我们确实希望使用 `DOMAIN` 和 `PORT` 常量来构建 `getUrl` 返回的字符串，这样当环境细节发生变化时，我们只需要修改字段，而不需要修改方法中的字符串。

在构建自动化代码时，我们经常进行字符串拼接，例如：

- 创建发送到系统的消息
- 生成输入数据
- 创建日志消息
- 等

我将快速展示拼接字符串的最简单方法。事实上，你已经看到过我们需要使用的代码了。

是的，“加号”符号可以将字符串对象的值连接在一起。

我可以修改 `getUrl` 方法，使其使用 `DOMAIN` 和 `PORT`：

```java
return "http://" + DOMAIN + ":" + PORT;
```

通过这样做，我减少了重复代码，而且如果我想更改 `@Test` 方法使用的环境细节，只需要在抽象层中更改单行代码。

运行 JUnit 测试类并确保 `@Test` 方法仍然通过。

对于这一章我还可以做更多事情，但目前这样已经足够了，我们稍后会重它。

# TestAppEnv 代码

我包含了在本章中构建的源代码，以便你可以检查自己的结果。后面的章节将不再包含完整的源代码，因为我建议你下载并查看本书的完整源码（详情请参见引言章节）。

更改后，你的 `TestAppEnv` 类应该如下：

```java
1 package com.javafortosters.domainobject;
2
3 public class TestAppEnv {
4
5     public static final String DOMAIN = "192.123.0.3";
6     public static final String PORT = "67";
7
8
9     public static String getUrl() {
10      return "http://" + DOMAIN + ":" + PORT;
11 }
12 }
```

由于这是一个非常简单的类，我们不需要添加任何额外的导入。

`TestAppEnvironmentTest` 代码所示：

```java
1 package com.javafortosters.chap005testwithourownclasses.domainobject;
2
3 import com.javafortosters.domainobject.TestAppEnv;
4 import org.junit.Test;
5 import static org.junit.Assert.assertEquals;
6
7 public class TestAppEnvironmentTest {
8
9     @Test
10     public void canGetUrlStaticallyCoded() {
11      assertEquals("http://192.123.0.3:67", TestAppEnv.getUrl());
12     }
13
14     @Test
15     public void canGetDomainAndPortStatically() {
16      assertEquals("http://192.123.0.3:67", TestAppEnv.getUrl());
17      assertEquals("http://192.123.0.3:67", TestAppEnv.getUrl());
19 }
```

# 静态使用与静态导入

需要指出的一是，“静态使用”（Static Usage）和“静态导入”（Static Import）之间的区别。

## 静态使用

你可以在代码中看到静态使用的示例：

我们使用 `TestAppEnv` 作为前缀：

```java
import com.javafortosters.domainobject.TestAppEnv;
```

## 静态导入

我们可以从这里导入静态：

```java
import static org.junit.Assert.assertEquals;
```

（注：后续页面代码块的 OCR 文字是碎片化且重复的；我已根据源文本提供的上下文重建了逻辑结构。）

# 第六章 - 重温 Java 类：构造函数、字段、Getter 与 Setter 方法

## 章节总结

在本章中，你将学习到：

* 理解什么是构造函数
* 创建默认构造函数
* 创建带有参数的构造函数
* 从一个构造函数调用另一个构造函数
* 创建 getter 和 setter 方法

前几章都是“直接进入深水区”和“教程”阶段。

现在我们将更详细地讲解 Java 概念。

我们之所以这样做，是因为你已经学会了如何：

* 创建类
* 创建方法
* 使用 @Test 注解方法以以 JUnit 测试的形式运行它们

## 背景

在对应用程序进行建模时，我经常创建的领域实体（Domain Entities）之一是 User（用户）。通常是指在系统中拥有账户的人，可以使用“用户名”和“密码”登录。它可能还包含其他一些细节。

对于本章中的示例，我们应该想象成想要为我们的 JUnit 测试构建一个 User 对象。

我们需要遵循正常流程来开始：

* 创建包 `com.javafortesters.domainentities`
* 将其创建在 `src.main.java` 下，因为它是一个抽象类，而不是 JUnit 测试类
* 在该包中创建一个类 `User`

```java
package com.javafortesters.domainentities;

public class User {
}
```

接下来创建一个 JUnit 测试类，以便我们使用 TDD（测试驱动开发）构建该类。

* 创建包 `com.javafortesters.chap006domainentities.examples`
* 记得将其创建在 `src.test.java` 下
* 在该包中创建一个类 `UserTest`

```java
package com.javafortesters.chap006domainentities.examples;
public class UserTest {
}
```

## 构造函数

![](img/3571bcaadac59e6bb801bc317a52cb1e_57_0.png)

## 什么是构造函数？

构造函数是一种特殊的方法，当使用 `new` 关键字实例化类时会被调用。

编写一个 `@Test` 方法来实例化一个新用户：

```java
@Test
public void canConstructANewUser() {
    User user = new User();
}
```

希望没有语法错误 - 记得导入 `org.junit.Test`。

你还需要导入 `User` 类。

![](img/3571bcaadac59e6bb801bc317a52cb1e_57_1.png)

## 共享同一个包

如果 `User` 和 `UserTest` 类在同一个包中，你就可以在不导入的情况下使用 `User` 类。

类位于不同的目录结构，但如果它们在同一个包中，你就可以使用同包内的任何公共类无需导入。

![](img/3571bcaadac59e6bb801bc317a52cb1e_57_2.png)

## 尝试包结构

将 `UserTest` 移动到不同的包（可以在 `.domainentities` 之上或同级包中）。你可以在不导入的情况下使用 `User` 类吗？

注意 - 取决于你是如何移动它的，IDE 可能会自动为你添加导入。

![](img/3571bcaadac59e6bb801bc317a52cb1e_57_3.png)

## 包作用域

如果你在声明字段或方法时没有使用修饰符（即省略了 `public`），那么只有相同包中的类可以使用它，而不是每个类都能导入它。

## 默认构造函数

如果你运行 `@Test` 方法 - 它做了什么？

嗯，其实什么都没做。

它创建了 `user` 类的新实例并将其存储在变量 `user` 中。但我们没有在 `user` 类上创建构造函数，因此 `User` 类中没有任何代码被执行。

现在我们将通过在 `User` 类中编写一个不带参数的构造函数来添加一些在类实例化时执行的代码，这种构造函数被称为无参构造函数。

## 默认构造函数

如果你不写构造函数，Java 会为你提供一个默认的。这就是无参构造函数。

## 无参构造函数

如果你不写构造函数，Java 会为你提供一个默认的。但是，一旦定义了任何构造函数，Java 将不再提供默认构造函数。

我们可以定义一个无参构造函数来初始化我们的字段：

```java
public User() {
    // 不需要代码
}
```

## 带参数的构造函数

如果我们想在创建对象时传递值，我们就定义一个带参数的构造函数：

```java
public User(String username, String password) {
    this.username = username;
    this.password = password;
}
```

这允许我们现在创建时设置字段：

```java
User user = new User("admin", "password123");
```

## 尝试字段名和参数名

编写构造函数代码，如文中使用 `this` 关键字所示。

从构造函数中删除 `.` 和 `,`，会发生什么情况？

更改构造函数的参数名称，使得 `@Test` 方法通过且你不使用 `this` 关键字。你会在什么情况下这样做？

> this
>
> `this` 关键字指向当前对象。
>
> 你可以使用 `this` 关键字来使用对象中的任何方法或字段。
>
> `this` 关键字可以帮助你区分与字段同名的局部变量。
>
> 你还可以使用 `this` 关键字来调用方法或构造函数。

## 显式构造函数调用

如果你遵循了之前的章节，那么你会发现在 `User` 类中存在重复代码，因为无参数构造函数中有给字段赋值的代码，而带参数的构造函数也是如此。

```java
public class User {
    private String username;
    private String password;

    public User() {
        username = "username";
        password = "password";
    }

    public User(String username, String password) {
        this.username = username;
        this.password = password;
    }
}
```

我们可以从一个构造函数调用另一个构造函数

使用 `this` 关键字，我们可以从无参数构造函数调用带参数的构造函数，例如：

```java
public User() {
    this("username", "password");
}
```

通过重构这段代码，我们：

- 只有一个地方为 `username` 和 `password` 字段赋值，
- 仍然保留了调用默认构造函数并为字段分配默认值的能力。

即：

```java
public User() {
    this("username", "password");
}

public User(String username, String password) {
    this.username = username;
    this.password = password;
}
```

## Getter 和 Setter

### Getters

你已经在 `User` 类中看到了两个 getter（或访问器）方法，即 `getUsername` 和 `getPassword`。

```java
public String getUsername() {
    return username;
}
```

```java
public String getPassword() {
    return password;
}
```

### Setters

我们还希望能够在类中修改或设置字段值。我们通过 setter 方法来实现。

对于我们的代码，我们希望能够修改密码但不想修改用户名。一旦我们的 `username` 通过构造函数调用被设置，我们绝不希望允许任何调用类修改 `username`，但我们希望允许修改密码。

为了修改密码，我们将编写一个 setter 方法（`setPassword`），我们在这段代码中将其用作 `@Test`：

```java
@Test
public void setPasswordAfterConstructed() {
    User user = new User();

    user.setPassword("PazZwor6");

    assertEquals("setter password expected", "PazZwor6",
        user.getPassword());
}
```

而 `User` 类中实际的 setter 方法如下：

```java
public void setPassword(String password) {
    this.password = password;
}
```

再次，你可以看到使用 `this` 关键字来区分字段和由 `String password` 参数定义的局部变量. (此处应为局部变量)。

编写代码并运行 `@Test` 方法以确保我们所有的断言仍然通过。

## 为什么需要 Setter 和 Getter？

通过创建 setter 方法，我们获得了控制分配给字段的值的能力，例如：

- 我们可以添加验证代码，确保我们不能分配错误的密码
- 如果密码必须有最小长度，我们可以编写代码在需要时将其添加到正确的长度

我们可以使用 getter 方法来隐藏实现细节，例如，我们可能会“计算”返回值，而不是总是返回一个被设置过的值。

有时我们需要放宽对对象字段的控制并将其变为公共，以便人们可以随地以他们想要的方式修改和访问它们。但我们更有可能使用 setter 和 getter 方法来控制访问，并为未来提供灵活性。

## 总结

在本章中，你应该了解：

- Java 注释



# Java 命名规范

# 字段、方法和 `final` 关键字的作用域

# 数据类型：boolean、浮点型、整数、String 及其包装类

# 运算符：算术、赋值、条件、三元、位运算

# 运算符优先级

# 字符串拼接

## 注释

注释是不执行的。`this` 关键字有三种类型的注释：

- 直到行尾的注释 `//`
- 以 `/*` 开始并 `*/` 结束的块注释
- 以 `/**` 开始并 `*/` 结束的 JavaDoc 注释

当我们需要小的注释时，可以在语句后面添加，任何 `//` 之后的内容都被视为注释。这些注释对于快速说明很有用。

```java
assertTrue(true); // 行尾注释
```

为了注释掉一段代码或拥有较大的描述性文本，我们使用以 `/*` 开始并 `*/` 结束的块注释。这些注释可以跨行并从行的中间开始结束。

```java
/*
这段代码检查 true
值是否设置为
true。
*/
boolean truthy = true;
assertTrue(truthy);
```

## 块注释不支持

你不能嵌套块注释，即如果你尝试注释掉一段已经包含块注释的文本，将得到语法错误。

你可以通过在每行开头放置 `//` 来注释掉块注释。

JavaDoc 有助于沟通，因为你可以使用 IDE 显示方法和类的 JavaDoc，即如果我按下 `ctrl + q`（Mac 上为 `ctrl + j`），我将看到注释中的 JavaDoc 文档。

这是在抽象类和方法上的一种非常有用的注释风格，例如：

```java
@Test
public void aJavaComment(){
    assertTrue(addTwoNumbers(4,3)==7);
}

/**
 * 将两个整数相加并返回整数。
 * 存在溢出的风险，因为大的
 * 整数会超过返回整数的最大值。
 * @param a 要加的第一个数字
 * @param b 要加的第二个数字
 * @return 整数形式的 a+b
 */
public int addTwoNumbers(int a, int b){
    return a+b;
}
```

## 语句

语句是 Java 可执行代码的最小单元。我们用 `;` 结束 Java 语句，例如：

```java
assertEquals(4, 2);
```

Java 语句可以跨行。这对于使你的代码更具可读性以及方法调用中的行参数很有用。例如：

```java
assertEquals("2+2 = 4", 4, 2+2);
```

## Packages

Java 允许我们将类（Classes）分组到包（packages）中。每个类在包内必须是唯一的。只要它们位于不同的包中，我们可以拥有多个同名的类。

```java
package com.javafortesters.chap007basicsofjavarevisited.examples;
```

要将类添加到包中，你需要编写像上面那包声明语句，它通常是类中的第一行，并且一定在声明类的代码之前。

## Java 类

我们所有的 Java 代码都会以某种形式涉及类。无论是使用他人编写的类、将抽象层编写成类，还是创建 JUnit 测试（这些测试实际上是标记了 `@Test` 注解的类中的方法）。

```java
public class EmptyClass {
}
```

这个示例类展示了类的许多特性：

```java
package com.javafortesters.chap007basicsofjavarevisited.examples;
```

```java
public class ClassExample {
    public static final String CONST = "constant string";
    public static String classField = "a class field";
    protected String proField = "a class field";
    public String pubField = "a public field";
    private String privField = "a private field";
    private String name;

    public ClassExample(String name) {
        this.name = name;
    }

    public String getName() {
        return this.name;
    }

    public void setName(String name) {
        this.name = name;
    }
}
```

类的第一行是包声明。这不需要是第一行，它只需要在类声明之前。

```java
package com.javafortesters.chap007basicsofjavarevisited.examples;
```

在这里，类被声明为 `ClassExample`，并声明为 public（公有）。

```java
public class ClassExample {
```

因为该类是公的，它可以被另一个类使用，只要该类导入了它；如果没有我添加 public，该类将具有包作用域，并且对同一包中的其他类可用。

## 静态方法和字段

类可以暴露静态方法和字段，这允许你在无需实例化类的新实例对象的情况下使用它们。

当你使用 JUnit 中的任何断言时已经见过了这一点，这些都是 `Assert` 类中的静态方法。

## 实例化类

大多数类在使用之前都需要被实例化。

```java
ClassExample instance = new ClassExample("bob");
```

当我们实例化一个类时，我们使用 `new` 关键字并调用类的构造方法之一。

## 字段和方法的作用域

字段或方法的作用域由 public（公共）、protected（保护）、private（私有）或包私有（无修饰符）定义。

- public：对任何导入父类的类可见。
- protected：对同一包中的任何类或任何子类可见。
- private：对类中的方法可见。
- package-private：当不使用修饰符时，字段或方法对该类以及同一包中的任何类可见（这是默认值）。

额外的字段和方法修饰符：

- static：字段或方法存在于类级别而非实例级别，因此被所有实例共享，并且可以在不需要实例化类变量的情况下进行访问。

## 字段与变量

字段是类中任何方法都可以访问的变量，并且取决于作用域，可能对其他类可见。

字段通常指声明在类级别的变量，而局部变量指的是在方法中创建的变量。

额外的字段修饰符是：

- final：一旦字段赋值，值就不能更改。

下文解释了作用域和修饰符组合及其细微差别的示例。

## 命名

字段或变量名必须以字母开头，我们通常遵循代表字母的 Unicode 字符，以保持代码的可读性，通常为 'A' 到 'Z'，'a' 到 'z'，虽然有些人也使用符号 '_' 和 '$'。

在第一个字母之后，变量名可以包含任何字母或数字。

大小写敏感，所以 `amount` 不等于 `Amount`。

名称倾向于使用驼峰命名（camel case）并以小写字母开头。常量倾向于大写，并用 '_' 分隔单词。

变量名可以很长，你可以在名称中使用范围字符，但请尽量保持名称的可读性，并能够朗读出来。

```java
@Test
public void variableNaming(){
    String $aString="bob";
    float owed=0;
    int amount=4;
    long Amount=5;
    String A0123456789bcdf="ugh";

    assertEquals(4, Amount);
    assertEquals(10.0, owed, 0);
    assertEquals("bob", $aString);
    assertEquals("ugh", A0123456789bcdf);
}
```

## Public Static Final

`public static final` 字段通常被称为常量，因为一旦赋值，该值就不能更改。这使得它们对于向其他类暴露常量值非常有用。

> `public static final String CONSTANT = "a constant string";`

通常你会在声明中看到赋值，如上面的示例所示，但也可以通过方法调用设置，这允许你从文件或属性值读取常量。

## Final

注意，`final` 不一定具有 `public static` 作用域。任何作用域关键字都可以与 `final` 一起使用，例如，`private final` 仅意味着一旦赋值，值就不能更改。

## Public Static

```java
public static String classField = "a class field";
```

静态字段不需要实例化类即可访问。

```java
String staticField = "a field";
```

## Public

```java
public String pubField = "a public field";
```

## Protected

```java
protected String proField = "a class field";
```

## Private

```java
private String privField = "a private field";
```

## Package-private

```java
String packageField = "a package field";
```

## 整数类型

每个原始类型都有一个关联的类，例如 `Byte`、`Short`、`Integer`、`Long`。这些类可以用于转换并拥有其他方法。它们还为每个原始类型提供了 `MIN_VALUE` 和 `MAX_VALUE` 常量。

Java 存在多种语法用于将字面量表示为特定的原始类型：

- 通过添加后缀 `L` 将整数字面量表示为 long
- 使用前缀 `0x`（zero x）表示十六进制值
- 使用前缀 `0`（zero）表示八进制值
- 使用前缀 `0b`（zero b）表示二进制值（Java 1.7）
- 通过添加 `_`（例如 `0_000_000`）来提高数字的可读性（Java 1.7）

上述示例下所示：

```java
@Test
public void IntegerTypes(){
    byte byteHas1Byte;
    short asHas2Bytes;
    int anIntHas4Bytes;
    long longHas8Bytes;

    System.out.println(" *short' range: " + 
        Byte.MIN_VALUE + " to " + 
        Byte.MAX_VALUE);

    System.out.println(" *int' range: " + 
        Integer.MIN_VALUE + " to " + 
        Integer.MAX_VALUE);

    System.out.println(" *long' range: " + 
        Long.MIN_VALUE + " to " + 
        Long.MAX_VALUE);

    longHas8Bytes = 0L; // long 使用后缀 L
    assertEquals(0, longHas8Bytes);

    byteHas1Byte = 0xA; // 为十六进制添加前缀 0x
    assertEquals(10, byteHas1Byte);

    anIntHas4Bytes = 010; // 为八进制添加 'zero' 前缀
    assertEquals(8, anIntHas4Bytes);

    byteHas1Byte = 0b0001; // Java 1.7 为二进制添加了 0b 'zero' b
    assertEquals(byteHas1Byte, 2);

    // Java 1.7 允许下划线增强可读性
    longHas8Bytes = 9_000_000_000L; // 90 亿
    assertEquals(9000000000L, longHas8Bytes);
}
```

## 浮点类型

浮点类型具有不同的精度，这控制了它们存储的值的大小：

- float: 单精度 32 位数字
- double: 双精度 64 位数字

范围：

- float 范围：1.4E-45 到 3.4028235E38
- double 范围：4.9E-324 到 1.7976931348623157E38

后缀：

- 使用后缀 `F` 表示 float
- 使用后缀 `D` 表示 double，或者如果你使用小数点（例如 `20.0`），则数字默认为 double

官方文档建议，如果你需要精确的值（例如货币），请使用 `java.math.BigDecimal` 类。`BigDecimal` 有助于避免错误。

这些原始类型也有关联的类，例如 `Float` 和 `Double`。

```java
@Test
public void FloatingPointType(){
    float singlePrecision32bit;
    double doublePrecision64bit;

    System.out.println(" + float range: " + 
        Float.MIN_VALUE + " to " + 
        Float.MAX_VALUE);

    System.out.println(" + double range: " + 
        Double.MIN_VALUE + " to " + 
        Double.MAX_VALUE);

    singlePrecision32bit = 10.0F; // 使用后缀 F 获取 float
    assertEquals(10F, singlePrecision32bit, 0);

    doublePrecision64bit = 20.0; // 默认为 double
    assertEquals(20D, doublePrecision64bit);
}
```

## 字符类型

`char` 类型用于表示单个字符。

`char` 可以表示 Unicode 字符，例如 `'a'`。

Java 还有一些特殊字符：

- `\t` - 制表符
- `\b` - 退格
- `\n` - 换行
- `\r` - 回车
- `\'` - 单引号
- `\"` - 双引号
- `\\` - 反斜杠

所有这些特殊字符也可用于字符串。Java 还有关联的方法来处理 `char` 变量。

```java
@Test
public void CharacterType(){
    char aChar = 'a';
    assertEquals('a', aChar);
}
```

## 运算符

### 传统运算符

Java 具有以下传统的算术运算符：

- `+` 加
- `-` 减
- `*` 乘
- `/` 除

上述所有运算符都可以用于整数和浮点数。由于在浮点数上你可能无法得到预期的结果，因此推荐使用 `BigDecimal`。

- `%` 取模

```java
@Test
public void traditionalOperators(){
    int num = 10;
    num += 2;
    assertEquals(12, num);

    num -= 4;
    assertEquals(8, num);

    num *= 2;
    assertEquals(16, num);

    num /= 4;
    assertEquals(4, num);
}
```

### 赋值运算符

运算符也用于赋值，当你实例化变量时。

传统的运算符也可以在赋值中使用：

- `+=` 增加变量
- `-=` 减少变量
- `*=` 乘以变量
- `/=` 除以变量
- `%=` 计算并赋值

```java
@Test
public void assignmentOperators(){
    String ab = "ab";
    assertEquals(ab, ab);

    int num = 10;
    num += 2;
    assertEquals(12, num);

    num -= 4;
    assertEquals(8, num);

    num *= 2;
    assertEquals(16, num);

    num /= 4;
    assertEquals(4, num);

    num %= 3;
    assertEquals(1, num);
}
```

### 递增和递减

你可以使用 `++` 和 `--` 递增和减少变量，例如 `++num` 返回递增后的 num。

你可以将 `++` 和 `--` 放在变量之前或之后。

- 在变量之前 `++` 或 `--` 意味着后修改它（前缀）
- 在变量之后 `++` 或 `--` 意味着先使用它再递增（后置）

## 布尔运算符

Java 有一系列运算符比较两个操作数并返回 true 或 false。

- `==` 等于
- `!=` 不等于
- `>` 大于
- `<` 小于
- `<=` 小于等于
- `>=` 大于等于



```java
@Test
public void booleanOperatorsExplored(){
    assertTrue(4 == 4);
    assertTrue(4 != 5);
    assertTrue(3 < 4);
    assertTrue(5 > 4);
    assertTrue(6 >= 6);
    assertTrue(8 <= 8);
    assertTrue(8 <= 9);
}

assertTrue(false);

boolean truthy = true;
assertFalse(!truthy);
```

## 条件运算符

你可以通过 `&&` 和 `||` 创建复杂的布尔语句：

- `&&` 逻辑与
- `||` 逻辑或

```java
@Test
public void conditionalOperatorsExplored(){
    assertTrue(true && true);
    assertTrue(true || false);
    assertTrue(false || true);
    assertFalse(false || false);
    assertFalse(false && true);
}
```

注意这些逻辑条件运算符具有短路特性，因此它们只在需要时评估第二个操作数。例如，`true || false` 只需要检查第一个值，`false || true` 则必须评估两者。

## 三元运算符

Java 支持三元运算符，它对条件进行检查并：

- 如果为 true，返回第一个操作数的值
- 如果为 false，返回第二个操作数的值。

`condition ? operand1 : operand2;`

注意，只有当三元运算符位于语句右侧时，才需要在末尾加 `;`；如果在语句内部求值，则不需要添加 `;`。

```java
@Test
public void ternaryOperatorsExplored(){
    int x;
    x = 4>3 ? 2 : 1;
    assertEquals(2, x);

    assertTrue( 5==4 ? true : false );
}
```

## 位运算符

你可以对整数数据类型使用位运算进行二进制操作。

- `&` 与
- `|` 或
- `^` 异或
- `~` 位取反码（反转位）

```java
@Test
public void bitwiseOperatorsExplored(){
    assertEquals(0b0001, 0b0101 & 0b0101);

    assertEquals(0b1101, 0b1001 | 0b0101);

    assertEquals(0b1100, 0b1001 ^ 0b0101);

    int x = 0b0001;
    assertEquals("111111111111111111111110", Integer.toBinaryString(-x));
}
```

位运算符也可以在赋值中使用。

```java
@Test
public void bitwiseAssignmentOperatorsExplored(){
    byte x = 0b0001;

    x &= 0b0111;
    assertEquals(0b0001, x);

    x |= 0b001;
    assertEquals(0b101, x);

    x ^= 0b1110;
    assertEquals(0b0111, x);
}
```

## 位移运算符

你可以对 Integer 数据类型执行二进制算术运算和位移操作。

- `<<` 左移，例如 `<<3` 向左移 3 位
- `>>` 有符号右移
- `>>>` 无符号右移（向左侧位置补 0）

位移运算符也可以配合赋值操作使用。

```java
@Test
public void bitwiseShiftOperatorsExpanded(){
    int x = 56;

    assertEquals(x*2, x<<1);
    assertEquals(x*4, x<<2);
    assertEquals(x*8, x<<3);

    x <<=3;
    assertEquals(56*8, x);

    x = Integer.MAX_VALUE;
    assertEquals(Integer.MAX_VALUE/2, x>>1);
    assertEquals(Integer.MAX_VALUE/4, x>>2);
    assertEquals(Integer.MAX_VALUE/8, x>>3);

    x = Integer.MIN_VALUE; // -ve
    assertEquals((Integer.MAX_VALUE/2)+1, x>>1);
}
```

## 运算符优先级

运算符优先级列在 Java 文档页面上：

`docs.oracle.com/javase/tutorial/java/nutsandbolts/operators.html`

虽然理解运算符优先级很有价值，但通常使用括号 `()` 来明确复杂语句的意图会比理解优先级顺序更易于阅读，因为嵌套操作会先执行。

例如，比较以下断言：

```java
@Test
public void operatorPrecedence(){
    assertEquals(8, 4+2/6 );
    assertEquals(12, ((4+2)*6/3) );
}
```

因此，请尝试使用优先级符号 `()` 来控制优先级顺序，这将使代码更易于阅读和维护。

优先级的基本规则是：

- 优先级最高的运算符按照左到右的顺序计算
- 优先级相同的运算符按照左到右的顺序计算
- 赋值运算符按照右到左的顺序计算

在下表中，运算符按优先级顺序列出，如果同一行有多个运算符，则它们的优先级相同。

| 运算符 |
| :--- |
| `x++` `x--` |
| `++x` `--x` `+x` `-x` `~` `!` |
| `*` `/` `%` |
| `+` `-` |
| `<<` `>>` `>>>` |
| `<` `>` `<=` `>=` `==` `!=` |
| `&` |
| `^` |
| `|` |
| `&&` |
| `||` |
| `?:` |
| `+=` `-=` `*=` `/=` `%=` `&=` `|=` `^=` `<<=` `>>=` `>>>=` |

## 字符串

`String` 是 `java.lang` 中的一个类，所以你不需要导入即可使用它。

字符串是不可变的，因此它们不能改变。所有看起来像改变字符串值的命令实际上都会返回一个经过修改后的新字符串。

### 字符串拼接

可以使用 `+` 运算符拼接字符串。

```java
@Test
public void stringsConcatenated(){
  assertEquals("123456", "12" + "34" + "56");
}
```

### 字符串方法

`String` 类提供了静态方法，无需实例化 `String` 对象变量即可直接使用：

- `length` 字符串中字符的数量
- `charAt` 返回特定索引处的字符
- `contains` 如果包含子字符串则返回 true
- 等等

```java
@Test
public void someStringMethods(){
    String aString = "abcdef";

    assertEquals(6, aString.length());
    assertTrue(aString.compareToIgnoreCase("ABCDEF")==0);
    assertTrue(aString.contains("bcde"));
    assertTrue(aString.startsWith("abc"));

    // 字符串索引从 0 开始
    assertEquals("c", aString.charAt(2));
    assertEquals("ef", aString.substring(4));
}
```

对于使用索引的方法（例如 `substring` 或 `charAt`），索引从 0 开始，所以第一个字符位于索引 0 处。

字符串将在本书的后续部分进行详细探讨。

## 总结

本章本打算内容相当充实，但我穿插了大量的代码示例。

确保你练习了这些并理解它们。

如果你想加深知识，请在自己的代码中重现这些示例并进行实验。

如果你没有完全理解，不要担心。我们稍后会详细介绍本章中的某些主题，因为这是你第一次在这里看到这些主题。

## 参考文献和推荐阅读

- JavaDoc 注释文档
  - `oracle.com/technetwork/java/javase/documentation/index-137868.html`
- Wikipedia JavaDoc
  - `en.wikipedia.org/wiki/Javadoc`
- 方法作用：public, protected, package
  - `docs.oracle.com/javase/tutorial/java/javaOO/accesscontrol.html`
- Java 原生数据类型
  - `docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html`
- Unicode 字符
  - `en.wikipedia.org/wiki/List_of_Unicode_characters`
- Java 字符
  - `docs.oracle.com/javase/tutorial/java/data/characters.html`
- 补码
  - `en.wikipedia.org/wiki/Two%27s_complement`
- 运算符与优先级
  - `docs.oracle.com/javase/tutorial/java/nutsandbolts/operators.html`

# 第八章 - 选择与决策

## 章总结

在本章中，你将学习如何使用选择和决策：如何使用三元运算符、`if/else` 语句、`switch` 语句等。

## 三元运算符

你可以使用三元运算符进行简单赋值：

```java
x = condition ? value1 : value2;
```

示例：

```java
String result = (age >= 18) ? "Adult" : "Minor";
```

## if 语句

`if` 语句有以下形式：

```java
if (condition)
    statement;
或
if (condition){
    statement1;
    statement2;
}
```

- 当 `if` 后只使用一个语句时，不需要添加 `{}` 定界符。
- 当使用多个语句时，需要添加 `{}`。

> 编码风格

我倾向于无论有多少条语句都添加 `{}`。我认为这让代码更易读。而且当我以后添加更多语句时，就不容易忘记添加块定界符。

示例：

```java
@Test
public void addHttp(){
    String url = "www.seleniumsimplified.com";
    if(!url.startsWith("http")){
        url = addHttp(url);
    }
}
```

```java
private String addHttp(String url) {
    return "http://" + url;
}
```

## else 语句

由于 `if` 之后的语句只有在条件为真时执行，因此我们需要在条件为假时执行代码的能力。

这就是 `else` 关键字出现的地方。

```java
if (condition)
    statement;
else
    statement;
or
if (condition){
    statement1;
    statement2;
}else{
    statement3;
    statement4;
}
```

再次看，你可以看到，当没有定界块时，`else` 执行单个语句，但当 `else` 有定界块时，该块中的所有语句都会执行。

示例：

```java
@Test
public void ifElseAddHttp(){
  String url = "www.seleniumsimplified.com";
  if(url.startsWith("http")){
    url = addHttp(url);
  }
  assertTrue(url.startsWith("http"));
  assertEquals("http://www.seleniumsimplified.com", url);
}
```

## 复合语句

块中的一组语句通常被称为“复合语句”。

而单个语句则被称为“简单语句”。

## 练习：AssertTrue else AssertFalse

给定一个变量：`boolean truth=true;`

编写一个 `@Test` 方法，使用不带大括号 `{}` 的语句对 `truth` 进行断言：如果 `truth` 为真则断言，否则对 `truth` 使用 `assertFalse`。

编写一个 `@Test` 方法，如果 `truth` 为真，对 `truth` 使用 `assertTrue` 并对 `!truth` 使用 `assertFalse`；否则对 `truth` 使用 `assertFalse`。

请确保在 `truth=false` 的情况下运行这些方法，以便看到两种值下的效果。

## 嵌套 if else

由于 `if` 和 `else` 是语句，它们可以像任何其他语句一样嵌套在 `if` 和 `else` 语句中。

例如：

在使用嵌套的 `if` 和 `else` 时，代码格式变得非常重要：

另外注意我采用的编码风格是将左大括号 `{` 放在 `if` 或 `else` 语句所在同一行的末尾，其他人倾向于将左大括号放在 `if` 或 `else` 下方但与其对齐。

例如：

```java
if(url.startsWith("http"))
{
    // do nothing the url is fine
} else
{
  if(!url.startsWith("www")) {
    url = "www." + url;
  }
  url = addHttp(url);
}
```

我个人认为上面的风格占了太多空间，而且左大括号 `{` 没有增加任何信息，当我阅读代码时，右大括号 `}` 确实增加了关于范围的信息。

通过实验并决定一种适合自己的风格。查看你所在机构使用的代码并采用公司内部风格。

## 练习：嵌套 If Else 的噩梦

将以下伪代码以 Java 形式编写在 `@Test` 中：

给定变量 `truth` 设置为 `true`，变量 `falsy` 设置为 `false`：

- truth
  - 如果 lousy 则
    - 如果 falsy 或 truth 则
      - ...断言 truth 为真，并且
      - ....断言 falsy 为假
  - Else
    - 断言 truth 为真
    - 断言 falsy 为真
- Else
  - 如果 truth 则
    - 如果 falsy 则
      - 断言 falsy 为真
      - 断言 truth 为假
  - else
    - 断言 falsy 为假
    - 断言 truth 为假

尝试使用 `truth` 和 `falsy` 的不同值组合，以确保你覆盖了所有路径。

## switch 语句

当你的代码中有许多 `if else` 语句时，使用 `switch` 语句可能会更合适。

`switch` 语句允许你对单个条件 checks 拥有多个 `case`。

```java
@Test
public void switchExample() {
  assertEquals("M", likelyGenderIs("sir"));
  assertEquals("M", likelyGenderIs("mr"));
  assertEquals("M", likelyGenderIs("master"));
  assertEquals("F", likelyGenderIs("miss"));
  assertEquals("F", likelyGenderIs("mrs"));
  assertEquals("F", likelyGenderIs("ms"));
  assertEquals("F", likelyGenderIs("lady"));
  assertEquals("F", likelyGenderIs("madam"));
}
```

```java
public String likelyGenderIs(String title){
  String likelyGender;
  switch(title.toLowerCase()){
    case "sir":
      likelyGender = "M";
      break;
    case "mr":
      likelyGender = "M";
      break;
    case "master":
      likelyGender = "M";
      break;
    default:
      likelyGender = "F";
      break;
  }
  return likelyGender;
}
```

- `switch` 语句接收一个要检查的表达式。
- `switch` 块有一系列 `case`。
- `break` 语句对于结束每个 `case` 非常重要。
- 最后一个 `case` 应该是 `default`，在没有其他 `case` 匹配时执行它。
- `default` 不需要 `break`，但我通常会加上一个。



注意：如果你想在 `case` 语句中使用字符串字面量，需要使用 Java 1.7 或更高版本。

小心。如果你忘记了 `break`，`case` 将穿透（fall through）到下一个。例如：

我是这样写 `switch` 的：

```java
switch(title.toLowerCase()){
  case "sir":
  case "mr":
    case "master":
      likelyGender = "M";
      break;
    default:
      likelyGender = "F";
      break;
}
```

当刻意编写时，穿透可以使代码易于阅读。但注意，忘记 `break` 语句是一个常见的错误，它很容易在你的代码中引入 bug。

## 练习：对短代码进行 switch

创建一个方法，使用 `switch` 语句根据作为方法参数传递的 `shortCode` 返回字符串：

- 给定 "UK" 返回 "United Kingdom"
- 给定 "US" 返回 "United States"
- 给定 "USA" 返回 "United States"
- 给定 "FR" 返回 "France"
- 给定 "SE" 返回 "Sweden"
- 给任意其他值，返回 "Rest Of World"

加分项：使短代码不大小敏感，即 "uK", "UK", "Uk", "uk" 都应该返回 "United Kingdom"

## 练习：对 int 进行 switch

创建一个方法，使用 `switch` 语句根据作为方法参数传递的 `int` 返回对应的字符串：

- 给定 1 返回 "One"
- 给定 2 返回 "Two"
- 给定 3 返回 "Three"
- 给定 4 返回 "Four"
- 给定 5 返回 "Five"
- 给定 6 返回 "Six"
- 给定 7 返回 "Seven"
- 给定 8 返回 "Eight"
- 给定 9 返回 "Nine"
- 给定 10 返回 "Ten"

# 声明一个空数组

你可以使用下面的语法声明一个长度为零的数组：

```java
int[] zeroLength = {};
int[] moreZeroLength = new int[];
```

## 声明一个后续初始化的数组

如果你需要，可以声明一个数组并在稍后进行初始化。例如，这段代码声明了一个数组但没有对其进行初始化。

```java
int[] uninitializedArray;
```

我倾向于在声明时初始化它，或者将其初始化为空数组。

如果你想为现有的数组变量分配新数组，可以使用你在声明时看到的语法，即：

```java
uninitializedArray = new int[10];
```

或者你也使用以下语法，它创建一个匿名数组并将其分配给现有变量：

```java
uninitializedArray = new int[] {100, 200, 300};
```

## 访问数组中的项

你可以使用 `[i]` 符号访问数组中的项，其中 `i` 是你想要的索引。

数组的索引从 0 开始；数组中的第一个项目位于 `[0]`。

```java
String[] weekdays = {"Monday", "Tuesday", "Wednesday", "Thursday", "Friday"};

assertEquals("Monday", weekdays[0]);
assertEquals("Friday", weekdays[4]);
```

## 练习：创建一个用户数组

使用你之前创建的 `User` 对象。

创建一个包含 3 个 `User` 对象的数组。

## 遍历数组

我们可以使用 for each 循环和 for 循环来遍历数组。

下面的迭代示例使用了所有的 `weekdays` 数组：

```java
String[] weekdays = {"Monday", "Tuesday", "Wednesday", "Thursday", "Friday"};
```

## For Each 循环

for each 循环遍历数组中的每一个项。

```java
for (variable : collection) {
    // 执行某些操作
}
```

该变量会自动分配集合中的下一个项，并自动遍历数组中的每一个项。

例如：

```java
String days="";
for(String workday : workdays) {
    days = days + "|" + workday;
}
assertEquals("Monday|Tuesday|Wednesday|Thursday|Friday", days);
```

创建一个 for 循环，一个变量数组声明：数组

- 在这种情况下，变量是一个名为 `workday` 的 `String`
- 集合是数组 `workdays`
- 代码遍历循环，数组中的每个项都被分配给变量 `workday`
- 循环第一次执行时，变量 `workday` 分配了数组 `workdays` 中索引为 `[0]` 的值，即 "Monday"
- 循环第二次执行时，变量 `workday` 分配了数组 `workdays` 中索引为 `[1]` 的值，即 "Tuesday"，依此类推
- 循环遍历数组中的每一个项
- 当数组中没有更多可遍历的项时，循环停止

这种循环结构意味着我们可以遍历数组中的每一个项而不会遗漏任何一个。从而避免了传统的边界值分析非常喜欢尝试检测的“差一错误”。

## 练习：遍历用户数组

使用你在上一个练习中创建的用户对象数组。

遍历数组并使用 `System.out.println` 打印每个用户的用户名。

## For loop

for 循环允许我们对循环有更多控制。我们设置用于循环的初始变量，然后是一个决定是否结束 for 循环的条件，然后我们有一个设置循环下一次迭代的语句。

```java
for ( variable ; loop_condition ; iterator ) {
    // 执行某些操作
}
```

例如，for 循环的传统用法：

```java
String days="";
for(int i=0; i<5; i++){
    days = days + "|" + workdays[i];
}
assertEquals("Monday|Tuesday|Wednesday|Thursday|Friday", days);
```

- `for` 创建了一个初始值为 0 的 for 循环索引变量
- `int i=0` 声明了循环
- `i<5` 只要循环条件满足，循环将继续，在这种情况下，只要我们仍在访问数组中的某一项——数组中有 5 个项。记住数组索引从 0 开始，所以最后一项是 4。索引 5 越界，所以我们使用 `<5`。
- `i++` 增加索引的值

对 for 循环更通用的解释实际上是：

```java
for ( 初始化语句仅执行一次; 循环条件; 每次循环后执行) {
    // 执行某些操作
}
```

所以我可以这样写循环：

```java
int i=0;
for(i<5; i++) {
    days = days + "|" + workdays[i];
}
```

其中变量在循环外初始化，初始化语句为空。

此外：

```java
int i=0;
for(i<5) {
   days = days + "|" + workdays[i];
   i++;
}
```

甚至：

```java
int i=0;
for(; ) {
   days = days + "|" + workdays[i];
   i++;
   if(i>=5) break;
}
```

在上面的代码中，我使用了在 switch 部分看到的 `break` 语句来跳出循环。

## break

`break` 是用于结束控制执行的通用关键字。`break` 可以在 if、switch 和 for 迭代结构中退出。

通常，保留本节开头所示的传统示例会让你的代码具有可读性和可维护性。例如：

```java
for(int i=0; i<5; i++){
   days = days + "|" + workdays[i];
}
```

## 使用 copyOf() 复制并调整数组大小

```java
String[] weekdays = weekdays;
weekdays = Arrays.copyOf(weekdays, 7);
```

使用 copyOf 复制，输出如下：

- 1 found Monday
- 2 found Tuesday
- 3 found Wednesday
- 4 found Thursday
- 5 found Friday
- 6 found null
- 7 found null

## 练习：创建 100 个用户的数组

创建一个可以包含 100 个 `User` 对象的数组。使用 for 循环填充数组，断言数组已正确创建。

## 使用 length 方法计算数组的大小

- `length` - 返回数组的长度

```java
assertEquals(5, weekdays.length);
```

`length` 方法的典型用法是在循环中，例如：

```java
for(int i=0; i<weekdays.length; i++) {
    days = days + "," + weekdays[i];
}
```

## Arrays 类中的实用方法

Java 在 `java.util` 中提供了 `Arrays` 类。

为了使用 `Arrays`，你需要导入它。

```java
import java.util.Arrays;
```

`Arrays` 类提供了许多静态方法。

在这里涵盖了其中一部分。你可以在官方文档中查看完整范围。

- `copyOf` - 创建数组的副本，并根据需要调整大小
- `copyOfRange` - 创建数组某部分的副本
- `fill` - 用单个值填充数组或部分数组
- `sort` - 排序数组

下面的部分引用 `weekdays` 数组：

```java
String[] weekdays = {"Monday", "Tuesday", "Wednesday", "Thursday", "Friday"};
```

```java
weekDays[5] = "Saturday";
weekDays[6] = "Sunday";
```

我们也可以使用 `copyOf` 来截断数组并使其变短：

```java
String[] weekDays;
weekDays = Arrays.copyOf(workdays, 3);
```

```java
assertEquals(3, weekDays.length);
assertEquals("Monday", weekDays[0]);
assertEquals("Tuesday", weekDays[1]);
assertEquals("Wednesday", weekDays[2]);
```

## 使用 copyOfRange 复制数组的子集

`copyOfRange` 将数组的一个子集复制到一个与子集大小相同的新数组中。

`Arrays.copyOfRange(arrayToCopy, startIndex, endIndex);`

`startIndex` 是你想复制的数组中的第一个元素。

`endIndex` 是你想要复制的索引 + 1。

例如，如果我想复制包含 3 到 5 的元素（"Wednesday", "Thursday", "Friday"），那么我将从索引 2（第三个元素的索引）开始复制，并在索引 5 处结束（尽管第五个元素的索引是 4）。

示例代码如下：

```java
String[] weekDays = Arrays.copyOfRange(workdays, 2, 5);
```

```java
assertEquals(3, weekDays.length);
assertEquals("Wednesday", weekDays[0]);
assertEquals("Thursday", weekDays[1]);
assertEquals("Friday", weekDays[2]);
```

```java
assertEquals(weekDays[0], workdays[2]);
assertEquals(weekDays[1], workdays[3]);
assertEquals(weekDays[2], workdays[4]);
```

我们也可以用 `copyOfRange` 来增加数组的大小，就像我们使用 `copyOf` 一样。为了做到，我们使用大于数组大小的 `endIndex`。例如：

```java
String[] weekDays = Arrays.copyOfRange(workdays, 2, 7);
```

```java
assertEquals(5, weekDays.length);
assertEquals("Wednesday", weekDays[0]);
assertEquals("Thursday", weekDays[1]);
assertEquals("Friday", weekDays[2]);
assertEquals(null, weekDays[3]);
assertEquals(null, weekDays[4]);
```

## 使用 fill 填充数组数据

`Arrays` 提供了一个名为 `fill` 的静态方法，我们可以用它向数组填充特定值，或者填充数组中的某个索引范围。

要用相同的值填充数组中的每个项目，我们只需要简单地调用一次 `fill`：

`Arrays.fill( array , value );`

例如，要用负值 (-1) 填充整数数组，我可以这样操作：

```java
int[] minusOne = new int[30];
Arrays.fill(minusOne,-1);
```

我可能会选择填充数组的部分内容——可能是在我刚刚执行了复制、`copyOf` 并调整数组大小之后。

`Arrays.fill( array, startIndex, endIndexCount, value );`

再次，索引范围是从我们想要开始的元素开始计数，范围的末端是是索引 - 1 + 1。也就是说，如果我们想在数组的第 10 个元素处停止（其索引为 '9'），我们应该使用值 '10'：

```java
int[] tenItems = {0,0,0,0,0,1,1,1,1,1};

// 将 5 - 9 填充为 '2'
Arrays.fill(tenItems,5,10);

// 0 - 4 保持未触
assertEquals(0, tenItems[0]);
assertEquals(0, tenItems[4]);

// 5 - 9 等于 2
assertEquals(2, tenItems[5]);
assertEquals(2, tenItems[6]);
assertEquals(2, tenItems[7]);
assertEquals(2, tenItems[8]);
assertEquals(2, tenItems[9]);
```

## 使用 Sort 排序数组

Java 提供了 `QuickSort` 的实现来快速排序数组。

`Arrays.sort( array );`

例如，如果有一个顺序混乱的整数数组，我可以快速对其进行排序。

```java
int[] outOrder = {2,4,3,1,5,0};

Arrays.sort(outOrder);
```

```java
assertEquals(0, outOrder[0]);
assertEquals(1, outOrder[1]);
assertEquals(2, outOrder[2]);
assertEquals(3, outOrder[3]);
assertEquals(4, outOrder[4]);
assertEquals(5, outOrder[5]);
```

你也可以排序 `String` 或其他对象。请记住，大写字母的 Unicode 值比小写字母小，所以在排序之前你可能希望让它们一致。

## 练习：排序 Workdays Array

创建一个 `@Test` 方法，实例化 `workdays`，如所示：
`String[] workdays = {"Monday", "Tuesday", "Wednesday", "Thursday"};`
然后使用 `Arrays.sort` 对其排序；断言 `workdays` 的结果为 "Thursday", "Monday", "Tuesday", "Wednesday"。

## 多维数组

多维数组实际上是数组的数组。普通的二维数组具有相等长度的数组。我可以这样定义二维数组：

```java
int[][] multi = new int[4][4];
```

这创建了一个名为 `multi` 的 4x4 二维数组，由于我没有初始化它，所有值均为 0。

```
0,0,0,0,
0,0,0,0,
0,0,0,0,
0,0,0,0,
```

`multi` 中的每个项目都是长度为 4 的数组。通过添加另一个索引可以访问数组中的值，例如访问 `multi[0]`：

```java
assertEquals(4, multi[0].length);
```

我可以在一个语句中声明并初始化多维数组：

```java
int[][] multi = {{1,2,3,4}, {5,6,7,8}, {9,10,11,12}, {13,14,15,16}};
```

上面的数组填充情况如下：

```
1,2,3,4,
5,6,7,8,
9,10,11,12,
13,14,15,16
```

我们可以使用 `[0][0]` 符号来访问值：

```java
assertEquals(1, multi[0][0]);
assertEquals(7, multi[1][2]);
assertEquals(12, multi[2][3]);
assertEquals(14, multi[3][1]);
```



## 三维数组

如果我需要，我可以创建额外的维度，例如 `3x4x5` 的三维数组：

```java
int[][][] multid = new int[3][4][5];
```

* `multid` 是长度为 3 的数组
* 每个项目都是长度为 4 的数组
* 每个项目都是长度为 5 的数组

```java
assertEquals(3, multid.length);
assertEquals(4, multid[0].length);
assertEquals(4, multid[1].length);
assertEquals(4, multid[2].length);
assertEquals(5, multid[0][1].length);
assertEquals(5, multid[0][2].length);
assertEquals(5, multid[1][0].length);
```

## 锯形数组 (Ragged Arrays)

由于我们知道多维数组实际上是数组的数组……我们可以看到创建锯形数组是简单的，每个数组的长度可以不同：

```java
int[][] ragged2d = {{1,2,3,4}, {5,6}, {7,8,9}};
```

这将创建一个数组：

```
1,2,3,4,
5,6,
7,8,9,
```

每个数组的长度都不同：

```java
assertEquals(4, ragged2d[0].length);
assertEquals(2, ragged2d[1].length);
assertEquals(3, ragged2d[2].length);
```

我们可以使用普通符号访问数组值：

```java
assertEquals(4, ragged2d[0][3]);
assertEquals(6, ragged2d[1][1]);
assertEquals(7, ragged2d[2][0]);
```

我们可以动态定义锯形数组，在创建它时将锯形维度留空：

```java
int[][] ragged2d = new int[10][];
```

上面的代码创建了一个长度为 10 的二维数组，我们没有定义这 10 个数组中每个的长度，我们会在初始化它们时这样做，例如：

```java
ragged2d[0] = new int[10];
ragged2d[1] = new int[3];
```

上面的代码初始化了 `ragged2d` 前两个项目：一个包含 10 个元素的数组和一个包含 3 个元素的数组，`ragged2d` 中所有剩余项目将保持为默认值 `null`。例如：

```
0,0,0,0,0,0,0,0,0,0,
0,0,0,
null
null
null
null
null
null
```

## 练习

### 理解 print2DArray 方法的工作原理

我在编写本书时使用了以下代码来打印本章看到的二维数组。仔细查看这段代码并确保你理解了它。

```java
public void print2DArray(int[][] multi) {
  for (int[] outer : multi) {
    if (outer == null)
      System.out.print("null");
    else {
      for (int inner : outer) {
        System.out.print(inner + " , ");
      }
    }
    System.out.println("");
  }
}
```

### 创建三角形

创建一个数组，当你将数组作为参数传递给 `print2DArray` 时，你在控制台输出一个如下的三角形：

```
0,
0,1,
0,1,2,
0,1,2,3,
0,1,2,3,4,
0,1,2,3,4,5,
0,1,2,3,4,5,6,
0,1,2,3,4,5,6,7,
0,1,2,3,4,5,6,7,8,
0,1,2,3,4,5,6,7,8,9,10,
```

## 总结

数组是收集对象的一种快速且方便的方法。

预先定义数组的大小需要一点努力，但你已经看到可以使用 `java.util.Arrays` 中的拷贝工具方法来帮助调整数组的大小。

在遍历数组时要务必小心，避免引入“差一错误”（off by one errors）。如果你不确定，使用 `for each` 形式的 `for` 循环可以避免引入这种错误。

## 参考文献和推荐阅读

- Java for 循环
  - docs.oracle.com/javase/tutorial/java/nutsandbolts/for.html
- 分支语句 (Branch statement)
  - docs.oracle.com/javase/tutorial/java/nutsandbolts/branch.html
- Java 数组 (Java Arrays)
  - docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html
- Java 1.7 数组文档
  - docs.oracle.com/javase/7/docs/api/java/util/Arrays.html

# 第十章 - 简介集合 (Collections)

我们已经通过数组看到了集合概念的实际应用。我先介绍数组是为了让你理解这一概念以及遍历集合的基础知识。

集合是考虑其他循环结构（如 `while`、`do`）的好地方。我们还将介绍接口（Interfaces）的概念。

## 本章总结

在本章中，你将学习主要的集合类。这些类在你的开发工作中提供了更多的灵活性和功能。

- For Each 循环 - 遍历集合中的每一个元素
- 转换 (Conversion) - 将集合转换为数组以及将数组转换为集合
- while 和 do...while - 你可以使用额外循环结构
- 接口 (Interfaces) - 集合通过接口组织，每个接口都有多个实现
- 泛型 (Generics) - 你将学习泛型的基础知识来帮助你声明集合
- 集合 (Collections) - 核心接口：List, Set, Map
- 核心实现 (Core Implementations) - 核心集合实现：ArrayList, HashSet, HashMap

这是书中最长的章节之一。我知道这看起来可能很复杂。因此，我将从一个简单的介绍开始本章节，将数组与一种名为 `List` 的特定集合进行比较，然后涵盖集合，最后介绍集合的不同接口和实现。

## 简单介绍

为了介绍集合，我将向你展示一个简单的示例，比较集合的使用与数组的使用。

```java
@Test
public void simpleArrayExample() {
  String[] numbers0123 = {"zero", "one", "two", "three"};
  for (String numberText : numbers0123) {
    System.out.println(numberText);
  }
  assertEquals("zero", numbers0123[0]);
  assertEquals("three", numbers0123[3]);
}
```

上面是你之前见过的代码。

以下是上述代码重写为集合的形式。

```java
@Test
public void simpleCollectionExample() {
  String[] numbers0123Array = {"zero", "one", "two", "three"};
  List<String> numbers0123 = Arrays.asList(numbers0123Array);
  for (String numberText : numbers0123) {
    System.out.println(numberText);
  }
  assertEquals("zero", numbers0123.get(0));
  assertEquals("three", numbers0123.get(3));
}
```

在上面的代码中，你可以看到我使用 `java.util.Arrays` 类中的 `asList` 方法将数组转换为 `List`。

我按照遍历数组的方式来遍历 `List`。

我使用与数组相同的索引编号方案访问 `List` 中的特定元素，即 0 是 `List` 中的第一个元素，3 是 `List` 中的第四个元素。

我使用不同的语法声明 `List`，即 `List<String>`。这使用了“泛型”符号，我将在本章中解释，但本质上我在说“一个字符串列表”。

## 集合是动态的

集合相对于数组的一个优势是它们是动态的，因此我们不需要预先声明它们的大小。

我可以重写你见过的示例，动态地构建 `List`。

```java
@Test
public void simpleDynamicCollectionExample() {
    List<String> numbers0123 = new ArrayList<String>();
    numbers0123.add("zero");
    numbers0123.add("one");
    numbers0123.add("two");
    numbers0123.add("three");
    for (String numberText : numbers0123) {
        System.out.println(numberText);
    }
    assertEquals("zero", numbers0123.get(0));
    assertEquals("three", numbers0123.get(3));
}
```

在上面的示例中，你可以看到我有一种新的声明语法。我将 `String` 值添加到 `List` 中，无需担心 `List` 的大小，我知道 `List` 会自动调整大小。

```java
List<String> numbers0123 = new ArrayList<String>();
```

在上面的声明中，`List` 是一个接口，声明了我正在使用的集合类型。

我将在本章中更详细地解释接口。但目前，接口是一种类型，它指定了对象将实现的方法。因此当我将 `numbers0123` 声明为 `List` 时，我知道我可以访问 `get` 方法，并且 `List` 中的元素将按顺序添加。

所以 `List` 的行为等同于数组，但它是动态的。事实上，`ArrayList` 是一种使用数组实现的 `List` 类型。

## 使用 while 和 do...while 进行迭代

除了 `for` 循环外，Java 还提供了 `while` 循环。这允许我们在“满足”特定条件时进行循环。

我使用 `for` 循环来遍历集合。但有时我们不想处理每个元素，或者想遍历到满足特定条件为止。

有两种形式：

- `while(condition){...}`
- `do{...}while(condition)`

使用 `while` 循环时，循环体可能不会执行，因为条件可能不满足。

使用 `do...while` 循环时，循环体至少会执行一次。

作为示例比较，我将创建一个简单的日期列表。

```java
String[] someDays = {"Tuesday", "Thursday", "Wednesday", "Monday", "Saturday", "Sunday", "Friday"};
List<String> days = Arrays.asList(someDays);
```

我将使用每种循环结构编写一些简单的代码：

- for each
- for
- do while
- while

我们看到了不同的方法

我们看到了我在 `List` 中查找 "Monday" 时采取的各种方法。

```java
int count = 0;
for (String day : days) {
  if (day.equals("Monday")) {
    break;
  }
  count++;
}
assertEquals("Monday is at position 3", 3, count);
```

使用 `for` 循环，我将遍历 `List` 的大小，并在找到 "Monday" 时退出：

```java
int loopCount;
for (loopCount = 0; loopCount < days.size(); loopCount++) {
  if (days.get(loopCount).equals("Monday")) {
    break;
  }
}
assertEquals("Monday is at position 3", 3, loopCount);
```

使用 `while` 循环，我可以将对 "Monday" 的检查作为循环的退出条件，这样我只使用循环的 `do` 部分，只要我没有找到 "Monday" 就继续 `while`：

```java
int count = 0;
while (!days.get(count).equals("Monday")) {
  count++;
}
assertEquals("Monday is at position 3", 3, count);
```

使用 `do..while`，我需要在列表有效边界之外设置索引，因为我在循环体中递增它，同样，我只在没有找到 "Monday" 时执行循环体的 `do` 部分：

```java
int doCount = -1;
do {
  doCount++;
} while (!days.get(doCount).equals("Monday"));
assertEquals("Monday is at position 3", 3, doCount);
```

当遍历集合中的每个元素时，`for each` 循环是一个很好的选择。你不需要担心索引错误或越界异常。但你必须提前结束循环。

循环是一种非常强大的结构，但如果条件很长，或者循环的设置或结束操作很复杂，就会变得难以阅读。

`while` 和 `do..while` 循环在需要根据任意或复杂条件终止循环时是非常好的选择。在 `while` 和 `do..while` 之间进行选择基于：

- 如果你想让循环运行一次或多次，使用 `do..while`
- 如果你想让循环运行零次或多次，使用 `while`

### 练习：使用 for 循环代替 while 循环

使用上面的代码创建星期数组，将其转换为列表，并使用 `while` 循环遍历它。将 `while` 循环转换为 `for` 循环。提示：将 `while` 循环中的条件作为 `for` 条件语句，并证明 `for` 可以像 `while` 循环一样使用。
例如 `for(;;; 在此处添加 while 条件; ...)`

## 接口

数组是一种简单的集合机制，但它们不提供与集合相同的接口。

Java 有一个接口（interface）的概念。我所说的接口，指的是它们暴露出的、我们用来与类交互的 API 方法，也就是说，接口定义了你可以做什么。

一个类可以实现多个接口，在这种情况下，它必须实现所有这些接口中定义的方法。

Java 为集合（collections）提供了许多接口：

- `Collection`：一个可以添加对象的泛型集合。
- `Set`：一个不允许重复元素的集合。
- `List`：一个可以在特定索引位置访问和添加元素的集合。
- `Map`：一种“键-值”对的结构，你可以在集合中存储一个对象，但可以通过唯一的键来访问它。

Collection 接口都在 `java.util` 包中。

## 重要的接口

我上面只列出了我认为的最重要的接口，即我最频繁使用的那些。

这体现了我的偏好，以及我所编写的代码的需求。

随着时间的推移，你将会识别出经常使用的接口和实现。详细学习这些内容，以便充分理解它们。但请确保你学习其他接口和实现的功能，以便你知道何时使用它们，并且不要只使用一种集合类型，因为另一种可能更符合你的需求。

## 声明为接口，实例化实现类

接口本身不能用于任何操作。其他类实现了接口，因此我们将变量声明为接口，但必须用具体的实现类来实例化它们。例如：

```java
Collection weekdays;
weekdays = new ArrayList();
```



在这里，我声明了一个名为 `Collection` 的变量，因为我只需要使用集合接口提供的方法。但我必须将其实例化为 `ArrayList`，这是一个实现了 `Collection` 接口的类。

`ArrayList` 暴露的方法比 `Collection` 接口多得多。如果我将变量 `weekdays` 声明为 `ArrayList`，就可以访问 `indexOf`、`trimToSize` 和 `get` 方法。

当我只需要访问 `Collection` 的方法时，应该按照所需的最小功能级别来声明变量。

通过这种面向接口的编码，我们能够切换实现类；如果我们发现某个实现比另一个更快，或者占用的内存更少。当我们切换到另一个实现时，不需要更改方法体的代码。

例如，我可以使用 `ArrayList`、`LinkedList` 和 `HashSet` 作为 `Collection` 的实现，因为它们都实现了 `Collection` 接口。但我需要理解这些实现类，以防其中某一个对我的代码施加了我不想要的限制，例如，`HashSet` 不允许重复元素，但 `ArrayList` 可以。

这可能听起来没道理，但这是一个重要的概念，我将通过本章中的所有示例来阐明它。

## 核心集合接口

官方文档列出了以下核心集合接口：

- `Collection`
- `List`
- `Set`
  - `SortedSet`
- `Queue`
  - `Deque`
- `Map`
  - `SortedMap`

在本章中，我们将涵盖 `List`、`Set` 和 `Map`，其他集合留到书中后面的部分。

## 继承层次结构

> 这是一个继承层次结构；因此 `Set` 是 `Collection`，`List` 也是 `Collection`，但 `Set` 和 `List` 都有让它们变得独特的细微差别。

有两个主要的集合概念：`Collection` 和 `Map`。

`Collection` 提供了一种分组对象的方式。`Map` 提供了一种将对象与“键”关联的方法，以便稍后检索和访问。

下表提供了接口上主要方法的总结：

| Collection | List | Set | Map |
| --- | --- | --- | --- |
| `add(e)` | `get(i)` | All in Collection | `put(k, v)` |
| `remove(e)` | `remove(i)` | | `remove(k)` |
| `removeAll(c)` | `add(i,e)` | | `entrySet` |
| `retainAll(c)` | `addAll(i,c)` | | `get(k)` |
| `clear` | `indexOf(e)` | | `clear` |
| `contains(e)` | `lastIndexOf(e)` | | `containsKey(k)` |
| `containsAll(c)` | `set(i,e)` | | `containsValue(v)` |
| `size` | `subList(i1, i2)` | | `size` |
| `isEmpty` | | | `values` |
| `toArray` | All in Collection | | `keySet` |
| `toArray(a)` | | | `putAll(m)` |
| `addAll(c)` | | | |

其中：`e == element`, `c == collection`, `a == array`, `i == index`, `k == key`, `v == value`, `m == map`

## Collection 接口

集合是一组对象。每个对象被称为一个元素。`Collection` 接口提供了一组基本方法。

- `add`：向集合添加一个元素。
- `remove`：从集合中移除一个元素。
- `size`：返回集合中元素的数量。
- `isEmpty`：检查集合是否为空。
- `addAll`：将另一个集合的所有元素添加到集合中。
- `removeAll`：从集合中移除另一个集合中的所有元素。
- `retainAll`：移除集合中不在另一个集合中的所有元素。
- `clear`：如果集合中有对象，则移除所有元素。
- `contains`：检查集合中是否存在某个对象。
- `containsAll`：检查一个集合是否包含另一个集合的所有元素。
- `toArray`：将集合转换为数组。

### 实例化集合

我们无法实例化 `Collection`，因为 `Collection` 是一个接口。有很多类实现了该接口，例如 `ArrayList`。我们将变量声明为集合，并用实现接口的类来实例化它们。

```java
Collection workdays;

workdays = new ArrayList();
```

在上面的代码中，我们将变量声明为 `Collection`，因为我只需要使用集合接口提供的方法。但我将其实例化为 `ArrayList`，这是一个实现了 `Collection` 接口的类。

`ArrayList` 暴露的方法比 `Collection` 接口多得多。如果我将变量 `weekdays` 声明为 `ArrayList`，就可以访问 `indexOf`、`trimToSize` 和 `get` 方法。

当我只需要访问 `Collection` 的方法时，应该按照所需的最小功能级别来声明变量。

通过这种面向接口的编码，我们能够切换实现类；如果我们发现某个实现比另一个更快，或者占用的内存更少。当我们切换到另一个实现时，不需要更改方法体的代码。

例如，我可以使用 `ArrayList`、`LinkedList` 和 `HashSet` 作为 `Collection` 的实现，因为它们都实现了 `Collection` 接口。但我需要理解这些实现类，以防其中某一个对我的代码施加了我不想要的限制，例如，`HashSet` 不允许重复元素，但 `ArrayList` 可以。

这可能听起来没道理，但这是一个重要的概念，我将通过本章中的所有示例来阐明它。

```java
workdays.add("Monday");

workdays.add("Tuesday");

workdays.add("Wednesday");

workdays.add("Thursday");

workdays.add("Friday");

assertEquals(5, workdays.size());
```

我们可以使用 `size` 方法来计算 `Collection` 中的元素数量。
我们可以使用 `addAll` 方法将一个 `Collection` 中的所有元素添加到另一个 `Collection` 中：

```java
daysOfWeek.add(workdays);

assertEquals(workdays.size(), daysOfWeek.size());

assertTrue(daysOfWeek.containsAll(workdays));
```

在上面的代码中，我们把 `workdays` 中的所有元素添加到了一个空集合 `daysOfWeek` 中。`containsAll` 方法可以帮助我们检查一个集合是否包含了另一个集合的所有元素。调用 `containsAll` 方法的集合（如 `daysOfWeek`）可以包含比参数 `Collection`（即 `workdays`）更多的元素，但为了 `containsAll` 返回 `true`，参数集合中的所有元素都必须存在。

## 移除单个元素：remove, contains

如果我向 `weekendDays` 中添加了一些元素。

```java
weekendDays.add("Saturday");

weekendDays.add("Friday");
```

那么你可以看到我犯了一个拼写错误，把 `Sunday` 拼成了 `Funday`。
我可以通过 `remove` 方法删除 `Funday` 来修复这个错误：

```java
workdays.remove("Funday");
```

我可以使用该方法检查集合是否包含某个特定元素。如果我检查 `Funday`，`contains` 将返回 `false`：

```java
assertFalse(weekendDays.contains("Funday"));
```

当然，我向 `Collection` 中添加了正确的值，并检查它的是否存在，

```java
weekendDays.add("Sunday");

assertEquals(2, weekendDays.size());

assertTrue(Bug Fixed, Sunday is in the collection now);

weekendDays.contains("Sunday"));
```

## 遍历集合

集合实际上实现了 `Iterable` 接口。该接口构成了我们之前看到的 `for` 循环功能的核心。所以，通过这一点，我将所有的工作日（`workdays`）和周末添加到了 `daysOfWeek` 中，我可以使用 `for` 结构对其进行遍历。

```java
for(String dayOfWeek : daysOfWeek){

  System.out.println(dayOfWeek);

}
```

在控制台生成以下输出：

```
Monday
Tuesday
Wednesday
Thursday
Friday
Saturday
Sunday
```

遍历集合很好地说明了为什么我们想要声明集合所持有的元素类型。对于我们之前展示的 `workdays` 声明：

```java
Collection workdays;

workdays = new ArrayList();
```

当我遍历它时，我得到的是一个 `Object` 而不是一个特定类型：

```java
for(Object workday : workdays){

  String outputDay = (String)workday;

  System.out.println(outputDay);

}
```

在上面的代码中，我必须将 `workday` 声明为 `Object`，并且在循环中使用它时，我必须使用 `(String)` 符号将其转换为 `String`。

当我们想要精炼对象的类型时，可以将其强制转换为特定类型。当对象已经支持该接口或已经是该类型时，我们无法这样做。

我们以前经常在 Java 中进行对象强制转换，但现在集合支持泛型（`Generics`），我们可以在声明中指定类型并避免强制转换。

## 空集合：clear, isEmpty

`clear` 方法允许我们清空一个集合。

```java
Collection<String> daysWeek = new ArrayList<String>();
```

```java
daysWeek.addAll(workdays);

daysWeek.addAll(weekendDays);
```

```java
assertEquals(7, daysWeek.size());
```

```java
daysWeek.clear();
```

```java
assertEquals(0, daysWeek.size());
```

```java
assertTrue(daysWeek.isEmpty());
```

我们可以使用 `size` 和 `isEmpty` 来验证它是否没有元素。

## 从一个集合中移除另一个集合的所有元素：removeAll

假设我的 `daysWeek` 包含了所有的 `weekendDays`。可以使用 `removeAll` 方法从 `daysWeek` 中移除集合的内容：

```java
Collection<String> daysWeek = new ArrayList<String>();
```

```java
daysOfWeek.addAll(workdays);

daysOfWeek.addAll(weekendDays);

assertEquals(7, daysOfWeek.size());

daysOfWeek.removeAll(weekendDays);

assertTrue(daysOfWeek.contains(workdays));

assertEquals(5, daysOfWeek.size());

assertFalse(daysOfWeek.contains(weekendDays));
```

## 从另一个集合中移除除外所有元素：retainAll

为了只保留 `daysOfWeek` 中的工作日，我会这样做：

```java
daysOfWeek.retainAll(weekendDays);
```

使用 `retainAll` 方法从另一个集合中移除除外所有元素。换句话说，在集合中只保留参数集合中的元素：

```java
Collection<String> daysOfWeek = new ArrayList<String>();
```

```java
daysOfWeek.addAll(workdays);

daysOfWeek.addAll(weekendDays);
```

```java
assertTrue(daysOfWeek.containsAll(workdays));
```

```java
assertEquals("only weekdays now", 2, daysOfWeek.size());

assertTrue(daysOfWeek.contains(workdays));
```

## 将集合转换为数组

使用 `toArray` 方法将集合转换为数组。该方法有两种形式：

- `toArray()`
- `toArray(anArray)`

当我们不带参数调用 `toArray()` 时，它将返回一个 `Object` 数组：

```java
Object[] daysArray = daysOfWeek.toArray();

assertEquals(7, daysArray.length);
```

如果我们随后需要数组中的元素，则必须将其转换为 `String`，即通过 `toArray(anArray)` 避免这些问题：

```java
String[] anotherArray = daysOfWeek.toArray(new String[0]);

assertEquals("Monday", anotherArray[0]);
```

## Collection 文档

你可以在官方文档中找到 `Collection` 的详情。

### Interface
- `docs.oracle.com/javase/tutorial/collections/interfaces`

### Implementation
- `docs.oracle.com/javase/tutorial/collections/implementations`

当我们需要通用集合时，通常使用 `List` 实现，但稍后涵盖其他实现。

## 练习：创建并操作用户集合

- 创建用户集合
- 断言 `size=0` 且 `isEmpty()==true`
- 创建用户对象
- 将用户添加到集合
- 断言 `size=2` 且 `isEmpty()==false`
- 创建两个不同用户的集合
- 将第二个集合添加到第一个集合
- 检查第一个集合是否包含第二个集合的元素
- 从第二个集合移除用户对象
- 清空第一个集合

在每一步之后进行断言

## List

`List` 构建于 `Collection` 之上，因此所有 `Collection` 方法都是可用的。

`List`：
- 允许重复元素
- 保留添加顺序
- 允许在特定位置添加元素

我倾向于使用 `List` 而不是数组。数组层级更低且速度更快。但只有当我处理一组永远不会改变的对象时，我才会使用 `Array`。

如果我的代码需要特别快，可能会优化为 `Array`。但如果我在进行动态操作，`List` 通常是我的首选，因为它是非常简单的集合。

`List` 提供了 `collection` 的所有方法以及：

- `get(i)`：从特定索引检索元素
- `remove(i)`：移除索引处的元素
- `add(i, e)`：在特定索引添加元素
- `addAll(i, c)`：在特定索引添加集合中的元素
- `indexOf(e)`：返回元素的索引
- `lastIndexOf(e)`：返回元素的最后一个索引
- `set(i, e)`：设置特定索引处的元素
- `subList(i1, i2)`：返回从 `index1` 到 `index2` 的子列表

在所有示例中，我将声明一个包含 `String` 的 `List` 并实例化 `ArrayList`，你在 `Collection` 的 `@Test` 方法中也见过。我倾向于对 `Collection` 和 `List` 默认使用 `ArrayList`。例如：

```java
List<String> days = new ArrayList<String>();
```

### 获取索引处的元素

`List` 暴露了数组风格的接口，列表中的每个元素都有位置，就像数组从 0 开始。

```java
@Test

public void getElementAtIndex() {

    List<String> days = new ArrayList<String>();

    days.add("Monday");

    days.add("Tuesday");

    days.add("Wednesday");

    assertEquals("Monday", days.get(0));

    assertEquals("Tuesday", days.get(1));

    assertEquals("Wednesday", days.get(2));

}
```

在上面的代码中，`List` 保证我添加的元素将按照添加的顺序被访问，因此可以通过索引 0 第一个元素，可以通过索引 1 添加第二个元素，以此此类推。

### 移除索引处的元素

除了移除元素的能力外，我们还可以根据索引移除元素。

```java
@Test
```



public void removeElementAtIndex() {

    List<String> days = new ArrayList<String>();

    days.add("Monday");

    days.add("Tuesday");

    days.add("Wednesday");

    days.remove(1);

    assertEquals(2, days.size());

    assertEquals("Wednesday", days.get(1));

}

```

```java
days.remove(1);
```

```java
assertEquals(2, days.size());
assertEquals("Monday", days.get(0));
assertEquals("Wednesday", days.get(1));
```

```

}

当我根据索引删除元素时，列表会调整大小，被删除元素之后的元素索引也会相应调整。因此，如果我删除了索引为 1 的元素，那么原本位于索引 2 的元素现在可以在索引 1 找到。

## 在特定索引处添加元素

在集合（`Collection`）中，我们可以添加元素，但它们只是在集合中，它们可以在任何地方，我们并不关心。

对于数组（`array`），如果我们想添加新元素，就必须调整数组的大小。

对于列表（`List`），我们可以在列表的特定位置添加元素。

在这个示例中，我从一个包含部分天日的列表开始。

```java
List<String> days = new ArrayList<String>();
```

```java
days.add("Tuesday");
days.add("Thursday");
days.add("Saturday");
```

我需要向这个列表添加几天：

```java
days.add(0, "Monday");
days.add(2, "Wednesday");
days.add(4, "Friday");
days.add(6, "Sunday");
```

如果我将 "Monday" 添加到列表开头，将 "Wednesday" 和 "Friday" 添加到列表中间，并将 "Sunday" 添加到末尾。

你可以看到，当我在中间或开头添加元素时，它不会覆盖已有的元素，而是插入该元素并将列表中的所有其他元素移动到新索引。

## 添加到末尾

当向列表末尾添加元素时，你只能向末尾添加，你不能在超出列表大小的情况下添加元素并期望它自动调整大小。

例如，如果我的列表中有 3 个元素，那么我可以在索引 3 处添加另一个元素。在我添加它之前，索引 3 是不存在的（我无法 `get(3)`），但我可以通过向末尾添加元素来增加列表的大小。如果我尝试向索引 20 处添加元素，Java 将抛出 `IndexOutOfBoundsException` 。

我也可以使用 `add(e)` 方法，因为向列表中添加元素就是将其添加到列表的末尾。

## 在特定索引处批量添加集合中的元素

对于集合（`Collection`），`addAll` 将元素添加到集合的某处。对于列表（`List`），我们可以精确控制将集合中的元素插入集合的位置。

例如，如果我创建了一个 `days` 列表：

```java
days.add("Monday");
days.add("Friday");
```

我可以创建另一个名为 `missingDays` 的集合，并将它们插入到 `days` 集合的中间。

```java
days.addAll(1, missingDays);
```

这会将集合插入到索引 1 处，并将 "Friday" 移动到位置 4。它不会覆盖索引 1 处的现有元素，带索引的 `addAll` 会插入：

```java
List<String> days = new ArrayList<String>();
List<String> missingDays = new ArrayList<String>();
```

```java
days.add("Monday");
days.add("Friday");
```

```java
missingDays.add("Tuesday");
missingDays.add("Wednesday");
missingDays.add("Thursday");
```

```java
days.addAll(1, missingDays);
```

```java
assertEquals(5, days.size());
assertEquals("Monday", days.get(0));
assertEquals("Tuesday", days.get(1));
assertEquals("Wednesday", days.get(2));
assertEquals("Thursday", days.get(3));
assertEquals("Friday", days.get(4));
```

## 可以在开头和末尾插入

与 `addAll(i,c)` 方法一样，可以使用索引 0 将集合插入到列表开头，或者使用 'next' 或 'size' 插入到列表末尾。

使用索引添加到末尾等同于使用不带索引的 `add` 或 `addAll` 方法。因为列表的 `add` 方法会将元素添加到列表的末尾。

## 使用 indexOf 查找元素的索引

当我们有一个列表但不知道列表中某个元素的索引时，我们使用 `indexOf` 方法来告诉我们元素在列表的哪个位置。

```java
List<String> days = new ArrayList<String>();
```

```java
days.add("Tuesday");
days.add("Thursday");
days.add("Saturday");
```

```java
assertEquals(1, days.indexOf("Thursday"));
```

如果在包含重复元素的列表上使用 `indexOf`，它将返回元素的第一个索引。

## 使用 lastIndexOf 查找元素的最后一个索引

列表允许重复元素，因此我们可能想要找到最后一个重复元素的位置。在这种情况下，我们使用 `lastIndexOf` 方法来实现。

```java
List<String> days = new ArrayList<String>();
```

```java
days.add("Tuesday");
days.add("Thursday");
days.add("Saturday");
days.add("Thursday");
days.add("Sunday");
```

```java
assertEquals(4, days.indexOf("Thursday"));
```

如果在不包含重复元素的列表上使用 `indexOf`，它返回的结果与索引相同。

## 设置索引处的元素

当使用数组时，`array[1]="New Element"` 会覆盖索引 1 处的现有内容。我们可以通过 `set` 执行相同的操作，它允许设置特定索引的值。例如：

```java
List<String> days = new ArrayList<String>();
```

```java
days.add("Monday");
days.add("Friday");
days.add("Wednesday");
```

```java
days.set(1, "Tuesday");
```

days.add("Thursday");

```

```java
days.add("Friday");
days.set(4, "Saturday");
```

```java
assertEquals(6, days.size());
assertEquals("Monday", days.get(0));
assertEquals("Tuesday", days.get(1));
assertEquals("Wednesday", days.get(2));
assertEquals("Thursday", days.get(3));
assertEquals("Friday", days.get(4));
assertEquals("Saturday", days.get(5));
```

`Map` 与 `Collection` 有一些共同的方法：

- `size`
- `clear`
- `isNotEmpty`

这意味着你已经知道这些方法的作用了。

还有一些方法具有非常相似对应方法：`containsKey` 和 `containsValue` 类似于 `Collection` 的方法 `contains`。

- `put(k, v)` 向 map 添加“键，值”值对
- `remove(k)` 移除带有该键的元素
- `entrySet(v)` 调用 `entrySet()` 返回一个包含所有 `Map.Entry` 对象的 `Set`
- `get(k)` 根据键检索元素
- `containsKey(k)` 如果键存在于 `Map` 中，则返回 true
- `containsValue(v)` 如果值存在于 `Map` 中，则返回 true
- `values` 返回包含所有值的 `Collection`（集合）
- `keySet` 返回包含所有键的 `Set`（集合）
- `putAll(m)` 将一个 `Map` (m) 添加到 `Map` 对象中

我打算使用 `HashMap` 作为我的默认实现。下面你可以看到声明和初始化的代码示例：

```java
Map<String, User> map = new HashMap<>();
Map<String, User> mapb = new HashMap<>();
Map<String, User> mapc = new HashMap<String, User>();
```

在上面的代码中你可以看到 `Map` 是带有两个值的 `Map<Key, Value>` 声明的，因此在上面的代码中我 `Map` 变量具有 `String` 类型的键和 `User` 类型的值。我将使用 `Map` 来存储 `User` 对象。

### put(k,v)

使用 `put` 方法向 `Map` 添加“键，值”值对。

```java
Map<String,String> map = new HashMap<>();

map.put("key1", "value1");
map.put("key2", "value2");
map.put("key3", "value3");

assertEquals(3, map.size());
```

键可以是一个对象，就像值一样。`Map` 的声明决定了我们可以将哪些对象放入 `Map` 中。

如果我放入的“键，值”值对中的键已经存在于 `Map` 中，那么旧值将将被新值覆盖：

```java
map.put("key1", "newvalue1");
assertEquals("newvalue1", map.get("key1"));
```

### get(k) 从 Map 中检索值

我可以使用将值存入 `Map` 的键从 `Map` 中获取值。

```java
assertEquals("value1", map.get("key1"));
assertEquals("value2", map.get("key2"));
assertEquals("value3", map.get("key3"));
```

如果我尝试使用不存在的键获取值，则将返回 null。

```java
assertEquals(null, map.get("key4"));
```

### remove(k) 移除“键，值”

我可以通过调用带有现有键的 `remove` 方法从 `Map` 中移除一个值。

```java
map.remove("key1");
assertEquals(2, map.size());
```

如果键不存在，则不会抛出异常，`Map` 不发生任何变化，方法调用没有影响。

# 使用 clear 清空 Map，通过 size 和 isEmpty 检查

就像对 `Collection` 一样，我们可以通过调用 `clear` 方法清空 `Map`。

```java
map.clear();
assertEquals(0, map.size());
assertTrue(map.isEmpty());
```

我可以使用 `containsKey` 和 `containsValue` 方法检查 `Map` 是否为空。

## 使用 containsKey(k) 和 containsValue(v) 检查 Map 内容

`containsKey` 方法返回 true 或 false。当带有该键的内容被放入 `Map` 时，它返回 true；当没有将此类键放入 `Map` 时，它返回 false。

```java
Map<String, String> map = new HashMap<>();

map.put("key1", "value1");
map.put("key2", "value2");
map.put("key3", "value3");

assertTrue(map.containsKey("key1"));
assertFalse(map.containsKey("key23"));

assertTrue(map.containsValue("value2"));
assertFalse(map.containsValue("value23"));
```

## putAll(m) 将 Map 添加到 Map 中

我可以使用 `putAll` 方法将一个 `Map` 放入另一个 `Map` 中：

```java
map.putAll(putToAdd);
```

如果我尝试添加一个包含重复现有键的 `Map`，那么新 `Map` 的值将被覆盖：例如在下面的代码中，键 "key1" 将被覆盖。

```java
String yourAge = "You are " + ageAsString + " years old";
```

在上述代码中，Java 将执行：

- 对 `age` 变量调用 `toString` 方法
- 将 `toString` 的返回值赋值给 `ageAsString` 变量
- 根据常量 "You are " + 变量 `ageAsString` 以及常量 "years old" 构建一个 String
- 将该 String 赋值给 `yourAge` 变量

上述所有代码将按顺序执行。

异常是在出现问题时中断正常执行流的一种方式。

当发生异常时，当前语句将被终止，执行流将停止。如果在调用序列的任何地方代码来捕获并处理该异常，则异常将终止程序。

## 异常看起来是什么样？

理解异常最简单的方法是观察它的运行。

我在 `src\test\java` 中创建了一个包：

```java
package com.javafosters.chap01exceptions.examples;
```

并添加了一个名为 `ExceptionsExampleTest` 的 JUnit 测试类。

我将把所有带有 `@Test` 注解的方法添加到这个类中。

以下代码在标记了 `@Test` 后，会导致抛出 `NullPointerException`。

运行并查看：

```java
public void throwNullPointerException(){
    Integer age=null;

    String ageAsString = age.toString();

    String yourAge = "You are " + ageAsString + " years old";

    assertEquals("You are 18 years old", yourAge);
}
```

在上述代码中，你可以看到我忘记给 `Integer age` 赋值，并且被设置为 `null`。因此当我尝试在 Java 上调用 `toString()` 方法时，Java 抛出了 `NullPointerException`。

在这种情况下，抛出的异常对我们是有益的，因为我们发现编码中犯了错误，可以通过给 `age` 变量赋值（即 18）来修复它。

异常报告被写入控制台：

```
1 java.lang.NullPointerException
2 at com.javafotesters.exceptionsExampleTest.
3 throwANullPointerException(ExceptionsExampleTest.java:15)
4 at sun.reflect.NativeMethodImpl.invoke(Native Method)
5 ...
6 at org.junit.runners.ParentRunner.run(ParentRunner.java:309)
7 at org.junit.runner.JUnitCore.run(JUnitCore.java:160)
8 at com.intellij.junit.4.JUnit4IdeaTestRunner.startWithArgs
9 (JUnit4IdeaTestRunner.java:77)
10 at com.intellij.rt.execution.JUnitStarter.prepareStreamsAndStart
11 (JUnitStarter.java:195)
12 at com.intellij.rt.execution.JUnitStarter.main
13 (JUnitStarter.java:63)
14 at sun.reflect.NativeMethodImpl.invoke(Native Method)
15 at sun.reflect.NativeMethodImpl.invoke
16 (NativeMethodImpl.java:57)
17 at com.intellij.rt.execution.application.AppMain.java(AppMain.java:120)
```

在异常消息中你可以看到堆栈跟踪（stack trace）。我删除了几行以避免代码冗余（在列表中用 `...` 表示）。



每一行都代表一次调用，是代码执行中的一个嵌套步骤。最近的调用在顶部（列表中的第 2 行和第 3 行）。这些行告诉我们在 `ExceptionsExampleTest.java` 的第 15 行抛出了 `NullPointerException`。

`throwANullPointerException(ExceptionsExampleTest.java:15)`

然后每一行都是代码执行的另一个层级。我们正在使用 JUnit，我可以在 IDE 中运行代码，这涉及到许多步骤。

从底部向上看你可以看到：

- 第 17 行：从 IntelliJ 调用了一个应用程序方法
    - `AppMain.java:120`
- 第 14-16 行：调用了各种反射方法启动代码
    - `NativeMethodImpl.java:57`
- 第 10-13 行：JUnit 被调用
    - `JUnitStarter.java:63`
- 第 8 & 9 行：JUnit 启动了一个运行器运行 `@Test`
    - `JUnit4IdeaTestRunner.java:77`
- 第 5-9 行：许多与启动和执行相关的行
- 第 1-3 行：在第 15 行调用了我们的代码
    - `ExceptionsExampleTest.java:15`

老实说，我不完全理解堆栈跟踪中的所有行。但我可以查看它们并看到最重要的部分。

堆栈跟踪非常有用，因为它显示了调用代码时涉及的行号，而列表中第 (15) 行 `ExceptionsExampleTest.java` 是异常的来源。这有助于我们在抛出异常时调试代码。

## 练习：修复代码中的 NullPointerException

修改代码为 `age` 赋值 18，检查代码是否运行而不抛出异常。

## 捕获异常

在某些情况下，我们预知可能会发生异常，想要捕获异常并采取措施。例如，我们尝试打开一个文件但它不存在，所以我们捕获异常。

`try` 和 `catch` 关键字帮助了我们。

```java
Integer age = null;
String ageAsString;
try {
    ageAsString = age.toString();
} catch (NullPointerException e) {
    age = 18;
    ageAsString = age.toString();
}
```

我对代码做了一些更改以使用 `try catch`：

- 在 `try` 之前声明 `String ageAsString`
- 声明要捕获的异常类型，在这种是 `NullPointerException`
- 在 `catch` 块中采取措施处理异常
- 给 `Integer age` 赋值

我必须在 `try` 之前声明 `ageAsString`。你可以看到 `catch` 块是用 `{ }` 包围的。如果在该块内声明 `ageAsString`，它将会在 `try` 块中可访问，而在 `catch` 块或之后不可用。我必须声明要捕获的异常类型。在这种情况下我只想捕获 `NullPointerException`，所以声明 `e` 为 `NullPointerException`。

在 `catch` 块中，我假设是因为 `age` 为 null 所以使用 `catch` 块来修复异常原因并允许代码运行完成。

## try catch 注意

- `try` 块中的代码始终运行。
- 只有当抛出声明的异常时，`catch` 块才会执行。
- `catch` 块中抛出的异常将向上传播（即到调用方法）。

`try` 块中的代码始终运行。

如果抛出了异常且其类型是 `catch` 块声明的，那么 `catch` 块中的代码将运行。

如果在 `catch` 块内抛出异常，它将不会被捕获，因为周围没有 `try catch` 语句。

如果抛出了不同的异常，它将不会被捕获，因为我指定了捕获 `NullPointerException`。我的完整代码如下：

```java
@Test
public void catchNullPointerException() {
    Integer age = null;
    String ageString;

    try {
        ageString = age.toString();
    } catch (NullPointerException e) {
        age = 18;
        ageString = age.toString();
    }

    String yourAge = "You are " + age.toString() + " years old";
    assertEquals("You are 18 years old", yourAge);
}
```

## 练习：使用不同的异常代替 NullPointerException

将 `NullPointerException` 替换为 `ArithmeticException`。发生了什么？

## 练习：不要修复异常原因

从 `catch` 块内部移除 `age = 18;` 语句。运行 `@Test` 方法查看结果。

## 练习：捕获检查异常

使用 `NoSuchMethodException` 替换 `NullPointerException`。发生了什么？

## 异常是一个对象

```java
} catch (NullPointerException e) {
    age = 18;
    ageAsString = age.toString();
}
```

在我的 `catch` 块中可以看到我声明参数 `e` 为 `NullPointerException`。这意味着在 `catch` 块内部我可以访问本地变量 `e`。你可以随意命名这个变量，很多人都习惯这样做。

`e` 是一个 `NoSuchElementException` 类型的对象，因此我可以访问此异常的各种方法。一些实用的方法：

- `getMessage()` - 显示与异常相关的错误消息，以便我记录。
- `getStackTrace()` - `StackElement` 对象数组，显示了导致抛出异常的代码行，可以帮助调试。
- `printStackTrace()` - 将堆栈跟踪打印到错误输出流（通常是你的控制台或命令行）。

## 练习：将异常作为对象

在你的 `catch` 块中添加以下代码，运行 `@Test` 方法，查看你从异常本身获取了什么信息。`getStackTrace()` 方法返回 `StackElement` 对象数组，调查该对象上的方法。

```java
System.out.println("getMessage - " + e.getMessage());
System.out.println("getStackTrace - " + e.getStackTrace());
System.out.println("printStackTrace" + e.printStackTrace());
```

## 捕获多个异常

在上面的 `catch` 代码中，我只检查了单一类型的异常。`catch` 块可以重复以编写捕获多个异常的代码。

```java
Integer age = null;
String ageAsString;

try {
    ageAsString = age.toString();
} catch (NullPointerException e) {
    age = 18;
    ageAsString = age.toString();
} catch (IllegalArgumentException e) {
    System.out.println("Illegal Argument: " + e.getMessage());
}
```

在上面的代码段中，`catch` 块将处理 `NullPointerException` 或 `IllegalArgumentException`。

# JUnit 与异常

JUnit 有一个非常方便的功能，允许我们检查抛出的异常。

```java
@Test(expected = NullPointerException.class)
```

我们可以告诉 `@Test` 注解期望抛出一个特定类别的异常。

上面的代码告诉 JUnit 期望在执行期间会抛出一个类型为 `NullPointerException` 的异常。

如果没有抛出 `NullPointerException`，则该方法将失败。

如果抛出了 `NullPointerException`，则该方法将通过。

例如，该方法通过的原因是因为抛出了 `NullPointerException`：

```java
@Test(expected = NullPointerException.class)
public void nullPointerExceptionExpected() {
    Integer age = null;
    age.toString();
}
```

使用此参数时要小心，因为异常可能在方法的任何地方抛出，而你的代码仍然会通过。因此，当你使用此参数时，请确保你的代码尽可能小以触发异常，并且你有其他的 `@Test` 方法来确保设置代码工作正常。毕竟，如果你的设置代码抛出了 `NullPointerException`，那么方法将会通过，但并没有检查你想要检查的内容。

## 抛出异常

我们不仅限于捕捉别人编写的代码中抛出的异常。我们在需要时也可以抛出异常。

作为一个示例，我将回到我们为用户构建的抽象层，在其中我们可以通过传递用户名和密码来构造用户。

我的意图是检查密码，如果密码长度小于 7 个字符，则构造函数将抛出一个异常。

我将在构造函数中重用 `setPassword()` 方法并传入参数，我只需要在相应的方法中添加校验规则检查。

```java
public User(String username, String password) {
    this.username = username;
    setPassword(password);
}
```

然后我编写代码来实现密码长度的检查。

```java
public void setPassword(String password) {
    if (password.length() < 7)
        throw new IllegalArgumentException("Password must be > 6 chars");
    this.password = password;
}
```

为了更详细地解释这一点，我们将查看密码长度。

```java
if (password.length() < 7) {
    throw new IllegalArgumentException("Password must be > 6 chars");
}
```

为了验证密码的长度，我检查字符串的长度。如果长度小于 7（那么七）。

```java
...
throw new IllegalArgumentException("Password must be > 6 chars");
```

由于异常是一个对象，所以我们必须创建一个 `IllegalArgumentException` 的新实例。`throw` 关键字是非常重要的，因为这是导致异常中断执行流的原因。

另外注意，当我们抛出新异常时，可以添加解释性消息。这为堆栈跟踪添加了额外信息，以帮助任何人调试代码。如果该异常没有被捕获，其错误输出如下：

```
java.lang.IllegalArgumentException: Password must be > 6 chars
at com.javafor.ters.dominities.interim.exceptions.User.setPassword(User.java:29)
at com.javafor.ters.dominities.interim.exceptions.User.<init>(User.java:10)
at com.javafor.ters.exceptions.UserPasswordExceptionTest.passwordMustBeGreaterThan6Chars(UserPasswordExceptionTest.java:22)
```

你可以从错误消息输出中看到，堆栈跟踪中的第一项是我抛出异常时的解释性文本。

在你的抽象层中抛出异常是保持代码简单洁的有用方法，并避免在你的 `@Test` 方法中犯简单的错误。

## finally

有时我们想要尝试某些事情，捕获并处理任何异常，最后始终执行某些代码。

```java
try {
    // 尝试做某些事情
} catch (NullPointerException e) {
    // 在此处处理异常
} finally {
    // 在此处执行代码
    // 无论是否抛出了
    // 异常
}
```

在下面的代码中，`finally` 块用于给你的 `age` 变量赋值：

```java
@Test
public void tryCatchFinallyNullPointerException() {
    Integer age = null;
    String ageAsString;
    String yourAge = "";

    try {
        ageAsString = age.toString();
    } catch (NullPointerException e) {
        age = 18;
        ageAsString = age.toString();
    } finally {
        yourAge = "You are " + age.toString() + " years old";
        assertEquals("You are 18 years old", yourAge);
    }
}
```

`finally` 块主要用于我们想要重新抛出异常，但我们失去了对清理资源的代码执行的控制。

在下面的代码中，修复问题后，我将 `NullPointerException` 重新抛出 `IllegalArgumentException`。如果我没有添加 `finally` 块，那么当我抛出 `IllegalArgumentException` 时，此处的没有更多代码将执行。因为我添加了 `finally` 块，`IllegalArgumentException` 被抛出了，但在控制传递向下调用之前，`finally` 块中的代码被执行了：

```java
@Test(expected = IllegalArgumentException.class)
public void exampleTryCatchFinally() {
    Integer age = null;

    try {
        System.out.println("1. generate a null pointer exception");
        System.out.println(age.toString());
    } catch (NullPointerException e) {
        System.out.println("2. handle null pointer exception");
        throw new IllegalArgumentException("Null pointer became Illegal", e);
    } finally {
        System.out.println("3. run code in finally section");
    }
}
```



这生成了以下输出：

- 1. generate a null pointer exception
- 2. handle null pointer exception
- 3. run code in finally section
- 4. `java.lang.IllegalArgumentException: Null pointer became Illegal`
- 5. `at com.java.framework.exceptions.ExceptionsExampleTest.exampleTryCatchFinally(ExceptionsExampleTest.java:144)`
- 6. `at sun.reflect.NativeMethodAccessorImpl.invoke(Native Method)`
- 7. ... 26 more

你可以从上面看到：

- `try` 块执行了
- 捕获了 `NullPointerException`
- 我们抛出了 `IllegalArgumentException`
- 由于我们即将因为 `IllegalArgumentException` 丢失执行控制，`finally` 块执行
- `IllegalArgumentException` 被触发，执行流被中断。

## 总结

在编写自动化代码时，你必须处理异常，因为你使用的许多库将抛出异常来提醒你意外事件。

我们将在未来的章节中复习异常，以便你学习如何创建自己的异常。

在编写抽象层时，我尽量不在我的层中放置断言，而是抛出异常，以便 `@Test` 方法可以传播或捕获它们。

## 参考文献和推荐阅读

- 异常
  - `docs.oracle.com/javase/tutorial/exceptions`
- 异常官方定义
  - `docs.oracle.com/javase/tutorial/exceptions/definition.html`
- 堆栈跟踪元素
  - `docs.oracle.com/javase/7/docs/api/java/lang/StackTraceElement.html`

# 第十二章 引入继承

| 章节总结 |
| :--- |
| 在本章中，你将学习继承的简单概述：<br>- 对象可以继承另一个对象<br>- 对象可以重新实现<br>- 你可以通过组合以及继承重用代码<br>- 使用 Java 关键字继承类 |

## 继承

继承是一种面向对象的设计概念。Java 提供了继承的一些实现。在本章中，你将获得继承的简单概述，主要目的是让你理解 Java 提供的机制，并帮助你在学习此本书时理解更高级的部分。

从之前的代码中可以看出，`EmptyUser` 的类体内没有任何代码，但我可以在 `@Test` 方法中使用它，因为它继承了来自 `User` 对象的方法。

```java
@Test
public void emptyUserTestMethod() {
    EmptyUser enu = new EmptyUser();
    assertEquals("username", enu.getUsername());
    assertEquals("password", enu.getPassword());
}
```

此时，`EmptyUser` 提供了与 `User` 相同的功能。

## 继承与组合

继承是一种面向对象的设计技术，表示一种“是一个（is a）”的关系。当我们扩展一个对象时，我们实际上是在说新对象“是一个”我们正在扩展的那个对象的类型。

组合是一种面向对象的设计技术，表示一种“有一个（has a）”的关系，因此对象“拥有”某些其他对象，例如：瓶子有一个盖子。

面向对象的设计超出了本书的范围（更多细节请参阅参考文献部分）。但理解 Java 的某些功能实现实现面向对象的概念是非常重要的。

### 继承

继承是一种面向对象的设计技术，表示一种“是一个（is a）”的关系。当我们扩展一个对象时，我们实际上是在说新对象“是一个”我们正在扩展的那个对象的类型。

例如：`SuperWidget` **是一个** `Widget`，`EmptyUser` **是一个** `User`。

如果我们仅仅因为想重用代码而使用继承，那么我们可能会面临让代码更难重用、维护和理解的风险，因为 Java 支持单继承，即你只能扩展一个对象。如果你以后想“更改”父类（我们扩展的那个类），那么在不对代码进行大量修改的情况下，这将很难实现。

注意，以下示例是一个非常糟糕的示例，永远、永远不要在你的代码中编写类似这样的代码。虽然在功能上扩展几乎任何其他类都是可行的，但这并不意味着我们应该这样做。请参考本章的后续章节以获取指导。但再次重申——永远不要执行以下操作：

例如：我设计时想让 `User` 能够返回他们正在使用的 URL，目前我将此内容放在 `TestAppEnv` 对象中。我可以通过 `User` 对象扩展 `TestAppEnv` 来重用 `TestAppEnv` 中的代码。这样 `User` 对象就继承了一个 get 方法。

遗憾的是，`User` 并不是一个测试应用程序环境，虽然这可能是一个重用某些代码的有用捷径，但我认为这并不是一种良好的做法。

因为 `User` 不是 `TestAppEnv`，扩展 `TestAppEnv` 来重用代码会导致代码依赖于不相关的对象，如果你在整个代码库中都这样做，它最终将变得不可维护、不可读，且代码某个区域的更改将对代码的其他区域产生意想不到的后果。

### 组合

通常我不会在我的代码中使用继承。使用“组合”和“接口”的代码这基本上意味着实现接口，并在我的代码中嵌入其他对象，从而通过使用它们的方法来获得重用。

例如：如果我想在 `user` 中有一个 `getUrl` 方法，我可能会找到一种在 `user` 对象中重用 `TestAppEnv` 对象的方法。如果 `TestAppEnv` 对象需要实例化，我会在 `user` 的构造函数中实例化它。然后我会为 `user` 添加一个 `getUrl` 方法，但该方法实际上调用了 `TestAppEnv` 的 `getUrl`。

## 练习：创建一个由 TestAppEnv 组成的 User

尝试实现上述 `User` 对象，使得 `User` “是一个” `User` 对象，并且拥有一个 `getUrl` 方法，该方法的实现通过委托给 `TestAppEnv` 对象完成。

## 使用继承

考虑到我们目前少量的领域抽象对象，使用继承的一个更好的例子可能是创建一个管理员用户（Admin User）。

假设被测系统有不同类型的用户，而管理员用户与普通用户拥有的权限不同。我可以在 `User` 中添加一个 `getPermission` 级别。

以下代码将检查这一点：

```java
@Test
public void aUserHasNormalPermissions(){
    User aUser = new User();
    assertEquals("Normal", aUser.getPermission());
}
```

然后我在 `User` 上实现 `getPermission` 方法。

```java
public String getPermission() {
    return "Normal";
}
```

为了创建 `AdminUser`，我会将 `AdminUser` 类声明为扩展 `User` 的类，然后在 `AdminUser` 中重写 `getPermission` 方法以返回不同的值。

```java
public class AdminUser extends User {
    public AdminUser() {
        super();
    }

    @Override
    public String getPermission() {
        return "Elevated";
    }
}
```

如果我想抛出一个未检查的异常，我首先会尝试使用标准的 `java.lang.unchecked` 异常之一。

例如，当我们在 `User` 类的密码验证中添加异常时，你看到了 `java.lang.unchecked` 异常的使用，我们使用了 `IllegalArgumentException`，因为我正在对一个方法的参数进行验证。

如果我想区分抽象层在运行时抛出的异常与 Java 运行时抛出的异常，那么创建我自己的未检查异常可能是恰当的。

## 检查异常

你将在编译时被通知需要处理检查异常，因为检查异常会在方法声明中被声明为会抛出。

例如，我可以将 `User` 类上的 `setPassword` 方法声明为抛出 `InvalidPassword`（假设 `InvalidPassword` 存在，尽管它不存在，但当我来到本章后面的“创建你自己的异常类”章节时）：

```java
public void setPassword(String password) throws InvalidPassword {
```

那么，在我使用 `setPassword` 方法的代码中，我必须：

- 处理异常，正如我们之前在 `try catch` 块中看到的那样，或者
- 忽略这些异常并允许它们向上传播

### 忽略检查异常

我们允许异常向上传播的方法是将我们在其中“忽略”的方法声明为抛出该特定的异常。

例如，由于 `User` 构造函数调用了 `setPassword`，我必须处理该异常，或者如下所示，允许它向上传播：

```java
public User(String username, String password) throws InvalidPassword {
    this.username = username;
    setPassword(password);
}
```

### 在默认构造函数中处理检查异常

如果我在另一个构造函数中调用构造函数，例如：

```java
this("username", "password");
```

那么构造函数中的第一个语句必须是这个调用。这意味着我不能用 `try catch` 封装这个调用。

我必须找到一种不同的委托构造调用的方法。在这段代码中，我选择更改默认构造函数，使其调用一个私有构造函数。

```java
public User() {
    this("username", "password", false);
}

private User(String username, String password, boolean b) {
    // 只有在这里调用这个，因为我们不想抛出异常
    this.username = username;
    try{
        setPassword(password);
    } catch(InvalidPassword e) {
        throw new IllegalArgumentException("Default password incorrect", e);
    }
}
```

通过这种方式，我确保任何使用无参数构造函数的人都不需要为硬编码密码处理 `InvalidPassword` 异常。

```java
@Test
public void canCreateDefaultUserWithoutHandlingException() {
    User aUser = new User();
    assertEquals("username", aUser.getUsername());
    assertEquals("password", aUser.getPassword());
}
```

但如果他们使用了程序员传递用户名和密码的构造函数，他们仍然必须处理异常。

```java
@Test
public void haveToCatchIllegalPasswordForParamConstructor() {
    try {
        User aUser = new User("", "wrong");
        fail("An exception should have been thrown");
    } catch (InvalidPassword invalidPassword) {
        assertTrue("The exception was thrown", true);
    }
}
```

注意，在我使用的来自 JUnit 代码中，我使用 `@Test` 方法来查找我们在创建用户后是否没有抛出断言。如果没有 `fail`，即使没有抛出异常，该方法也会通过，尽管该方法实际上失败了。在处理异常时要非常小心，因为你需要确保没有出现“假阳性”，即：在应该失败时，在 `@Test` 处却通过了。

## Exception、Error 和 Throwable 的区别

Java 有一个异常层次结构：

- `Throwable`
  - `Error`
  - `Exception`
    - `RuntimeException`

根对象是 `Throwable`，`Error` 和 `Exception` 都继承了它。`Error` 留给严重的 Java 平台错误。给 Java 程序员的通用指导是“永远不要捕获 Java Error”。我们希望捕获 `RuntimeException`，因为它继承自 `Exception`。我们希望捕获 `Exception`，捕获 `RuntimeException`，因为它继承自 `Throwable`。

## 创建你自己的异常类

在这个章节，你看到了使用 `Exception` 来抛出 `InvalidPassword`。

```java
public class InvalidPassword extends Exception {
    public InvalidPassword(String message) {
        super(message);
    }
}
```



# 练习：创建你的异常

在这个章节中，你学习如何创建并抛出检查异常：

- 编写一个 `InvalidPassword` 异常
- 在 `User` 类中抛出它
- 编写测试用例来验证异常被抛出
- 编写测试用例来验证异常没有被抛出
- 使用 `assertEquals` 验证：
    - 抛出 `InvalidPassword`
    - 抛出 `IllegalArgumentException`
    - 抛出 `NullPointerException`

# 第十四章 - JUnit 探索

## 章节总结

在本章节中，你将学习更多 JUnit 功能：

- `@Test` - 标记方法为 JUnit 测试
- `assertEquals` - 断言两个值是否相等
- `@Test(expected...)` - 期望抛出特定类
- `fail` - 强制方法失败
- 使用 `@Rule ExpectedException` 来检查异常
- `@BeforeClass` - 在任何 `@Test` 方法之前运行一次
- `@AfterClass` - 在所有 `@Test` 方法之后运行一次
- `@Before` - 在每个 `@Test` 方法之前运行
- `@After` - 在每个 `@Test` 方法之后运行
- `@Ignore` - 防止 `@Test` 方法运行
- 更多 JUnit 断言：
    - `assertEquals` - 检查期望和实际值是否相等
    - `assertFalse` - 检查实际是否为假
    - `assertTrue` - 检查实际是否为真
    - `assertArrayEquals` - 检查数组是否相等
    - `assertNotNull` - 检查实际是否不为空
    - `assertNotSame` - 检查对象是否不同
    - `assertNull` - 检查实际是否为空
    - `assertSame` - 检查期望和实际是否相同
- 使用 Hamcrest matcher 进行字面化断言：
    - `assertThat` - 使用 Hamcrest Matcher 进行断言
    - `is` - 当 `assertThat(x, is(y))` 为真
    - `equalTo` - 当 `assertThat(x, equalTo(y))` 为真
    - `not` - 当 `assertThat(x, is(not(y)))` 为真
    - `containsString` - 当 `assertThat(x, containsString(y))` 为真
    - `endsWith` - 当 `assertThat(x, endsWith(y))` 为真
    - `startsWith` - 当 `assertThat(x, startsWith(y))` 为真
    - `nullValue` - 当 `assertThat(x, is(nullValue(y)))` 为真

## @Test

我们已经看到，为了让一个方法被识别为 JUnit 测试，必须使用 `@Test` 注解。

```java
@Test
public void thisTestWillNeverFail() {
}
```

如果断言失败或方法体中抛出异常，该方法将失败。

尽可能表现力。

## 检查异常

因为如果抛出异常，方法将会失败。JUnit 赋予了我们检查异常的能力，并且只有在抛出异常时才让 `@Test` 方法通过。

### `@Test(expected=...)`

如果我想检查是否抛出了某个特定的异常，那么我可以在 `expected` 参数中声明它。

```java
@Test(expected = InvalidPassword.class)
public void expectInvalidPasswordException() throws InvalidPassword {
    User user = new User("username", "6");
}
```

注意，如果在执行过程的任何地方抛出了与预期类匹配的异常，你的 `@Test` 方法将通过。

我们可以使用 `ExpectedException` 规则来更具体地定义我们认为通过的异常。

### `ExpectedException` rule

JUnit 有“规则”（rules）的概念来扩展和增强 JUnit。我们不会涵盖书中介绍的许多可用规则。

`ExpectedException` 规则允许你对异常进行更具体的描述，并将特定异常视为通过：

- 抛出了特定类别的异常
- 异常具有特定的消息
- 异常具有特定的原因（cause）
- 上述任一组合

以下代码的效果与使用参数 `expected` 标注相同：

```java
@Rule
public ExpectedException expected = ExpectedException.none();

@Test
public void invalidPasswordThrown() throws InvalidPassword {
    expected.expect(InvalidPassword.class);
    User user = new User("username", "6");
}
```

我们可以看到，我可以将 `@Rule` 作为类中的一个字段，并使用 `ExpectedException` 上的静态方法进行实例化。

```java
@Rule
public ExpectedException expected = ExpectedException.none();
```

在 `@Test` 方法本身中，通过调用 `ExpectedException` 对象上的 `expect` 方法，我配置规则以期望 `InvalidPassword.class`。

我可以通过订阅预期消息的子类来使检查更具体。通过这样做，如果抛出了 `InvalidPassword` 异常但消息不同，我的方法将不会通过。

```java
expected.expect(InvalidPassword.class);
expected.expectMessage("> 6 chars");
User user = new User("username", "6");
```

该子类也可以是一个 Hamcrest 匹配器（matcher）：

```java
expected.expectMessage(containsString("> 6 chars"));
```

## 之前与之后

JUnit 提供了注解，用于在任何测试运行之前和之后，以及在每个测试之前和之后执行代码。这允许对数据或环境条件进行设置和清理。

- `@BeforeClass` - 在任何 `@Test` 方法运行之前运行一次
- `@AfterClass` - 在所有 `@Test` 方法运行之后运行一次
- `@Before` - 在每个 `@Test` 方法之前运行
- `@After` - 在每个 `@Test` 方法之后运行

任何标注了 `@BeforeClass` 或 `@AfterClass` 的方法都必须声明为静态（`static`）方法：

```java
@BeforeClass
public static void runOncePerClass() {
    System.out.println("@BeforeClass method");
}
```

标注了 `@Before` 和 `@After` 的方法不需要是静态的：

```java
@Before
public void runEveryTestMethod() {
    System.out.println("@Before each method");
}
```

所有方法都需要是公有的（`public`）的。无论前一个方法是通过还是失败，`@After` 和 `@BeforeClass` 都会运行。

## @Ignore

我们可以用 `@Ignore` 标注方法，这样 `@Test` 方法将不会运行。

```java
@Ignore
@Test
public void thisTestIgnored() {
}
```

对于 `@Ignore`，不会调用任何 `@Before` 或 `@After` 方法。

我们还可以为 `@Ignore` 添加一个文本参数以提供被忽略的原因。

```java
@Ignore("Because it is not finished")
```

当你忽略一个方法时，我建议添加一个文本参数来描述原因，否则人们会忘记该方法可能被删除。

## JUnit 断言

JUnit 内置了它的断言：

```java
import static org.junit.Assert.*;
```

JUnit 断言主要以方法的形式存在，带有一个预期结果的参数，然后是实际结果的参数，某些实际值作为预期值。

```java
assertEquals(6, 3);
```

通过 JUnit 断言，你可以添加一个可选的消息来描述该断言：

```java
assertEquals("3 + 3 = 6", 6, 3);
```

如果断言失败，该消息将作为消息的一部分写入，以便识别，例如：

```
java.lang.AssertionError: 3 + 3 = 6 expected: 7 but: 6
```

JUnit 提供了以下断言：

- `assertEquals` - 检查预期和实际相等
- `assertFalse` - 检查实际是否为 `false`
- `assertTrue` - 检查实际是否为 `true`
- `assertArrayEquals` - 检查预期和实际数组相等
- `assertNull` - 检查实际是否为空
- `assertNotSame` - 检查预期和实际是否不同
- `assertSame` - 检查预期和实际是否相同

如果我在代码中使用 JUnit 断言，我主要使用 `assertEquals`、`assertFalse` 和 `assertTrue`。

> **练习：创建一个使用所有断言的 `@Test` 方法。** 通过创建一个包含所有上述断言且能够通过的 `@Test` 方法来对 JUnit 断言进行实验。

JUnit 还提供了用于与匹配器（matchers）配合使用的 `assertThat` 断言。

你可以结合匹配器使用 `assertThat` 方法（例如来自 Hamcrest 的匹配器），使你的代码更具可读性。

```java
assertThat(3 + 3, is(6));
```

当一个没有原因的 `assertThat` 失败时，输出如下：

```
java.lang.AssertionError: Expected: 7 but: was 6
```

`assertThat` 也可以给出一个“原因”。

```java
assertThat("3 + 3 = 6", 3, 3, is(6));
```

如果带有原因的 `assertThat` 失败，输出如下：

```
java.lang.AssertionError: 3 + 3 = 6 Expected: 7 but: was 6
```

由于 `assertThat` 在代码中具有可读性，我倾向于不添加原因，只需使用堆栈跟踪找到包含错误的行。你可以选择你自己的风格。

## Hamcrest 核心匹配器

JUnit 依赖 Hamcrest 核心，因此当你将 JUnit 作为依赖添加到项目时，你也可以访问 Hamcrest 核心。

Hamcrest 核心提供了一组“匹配器”，帮助我们编写文学化的断言（literate asserts），使你的代码更具可读性。Hamcrest 核心提供的匹配器如：

- `is` - 当 `assertThat(x, is(y))` 时为真
- `equalTo` - 当 `assertThat(x, equalTo(y))` 时为真
- `not` - 当 `assertThat(x, is(not(y)))` 时为真
- `containsString` - 当 `assertThat(x, containsString(y))` 时为真
- `endsWith` - 当 `assertThat(x, endsWith(y))` 时为真
- `startsWith` - 当 `assertThat(x, startsWith(y))` 时为真

匹配器可以链式调用以创建文学化的语句，例如：

```java
assertThat("", is(nullValue()));
```

## 练习：使用 `assertThat` 重现 JUnit 断言

复制你为断言编写的 `@Test` 方法。然后使用 `assertThat` 重写所有断言。例如 `assertEquals(x,y)` 变为 `assertThat(y, is(x))`。

对所有断言执行上述操作：

- `assertEquals` - 检查预期和实际相等
- `assertFalse` - 检查实际是否为 `false`
- `assertTrue` - 检查实际是否为 `true`
- `assertArrayEquals` - 检查预期和实际数组相等
- `assertNull` - 检查实际是否为空
- `assertNotSame` - 检查预期和实际是否不同
- `assertSame` - 检查预期和实际是否相同

## 练习：使用所有列出的 Hamcrest 匹配器

创建一个使用所有列出的 Hamcrest 匹配器的 `@Test` 方法，尝试在可以使断言迭代的地方组合使用它们。

- `is` - 当 `assertThat(x, is(y))` 时为真
- `equalTo` - 当 `assertThat(x, equalTo(y))` 时为真
- `not` - 当 `assertThat(x, is(not(y)))` 时为真
- `containsString` - 当 `assertThat(x, containsString(y))` 时为真
- `endsWith` - 当 `assertThat(x, endsWith(y))` 时为真
- `startsWith` - 当 `assertThat(x, startsWith(y))` 时为真
- `nullValue` - 当 `assertThat(x, is(nullValue(y)))` 时为真

Hamcrest 提供了更多匹配器，如果你在 `pom.xml` 文件中包含了 Hamcrest，你就可以访问它们。例如：

```xml
<dependency>
  <groupId>org.hamcrest</groupId>
  <artifactId>hamcrest-core-all</artifactId>
  <version>1.3</version>
</dependency>
```

有关完整的 Hamcrest 匹配器的信息，请参见本章参考文献中的 Hamcrest 教程链接。

## fail

JUnit 提供了一个 `fail` 方法，可故意导致方法失败。可以在不带描述的情况下调用：

```java
fail();
```

或者带一个描述参数调用：

```java
fail("fail always fails");
```

当调用 `fail` 时，会抛出一个 `AssertionError`。

## 静态导入

到目前为止你看到 JUnit 断言的主要方法是从 JUnit 静态导入该方法：

```java
import static org.junit.Assert.assertEquals;
```

这样在 `@Test` 方法代码中，我们可以直接编写断言：

```java
@Test
public void addTwoPlusTwo() {
}
```



## JUnit 断言风格

```java
int answer = 2+2;

assertEquals("2+2=4", 4, answer);
}
```

另一种你可能会看到或选择采用的 JUnit 断言使用风格是：

```java
Assert.assertEquals("2+2=4", 4, answer);
```

在后一种用法中，我导入了 `Assert` 类而不是单个方法。

```java
import org.junit.Assert;
```

在 `@Test` 方法的上下文中，它看起来是这样：

```java
@Test
public void addTwoPlusTwo(){
    int answer = 2+2;
    assertEquals("2+2=4", 4, answer);
}
```

你的偏好可能不同。

我认为第一种没有 `Assert` 前缀的方法通常更具读性。但通过使用 `Assert.` 前缀，在编码时通常对我很有帮助，因为当我使用 IDE 代码补全时，我可以看到所有可用的断言范围。

## 总结

JUnit 提供了多种断言方法。尝试使用可用范围来使你的断言具有表现力，尽管通常可以将所有的断言都写为 `assertTrue`。这意味着通过阅读代码来解析整个断言条件。

我们可以坚持 JUnit 默认提供的断言，或者选择通过 `assertThat` 导入来使用它们。

Hamcrest 提供的匹配器（matchers）比本节列出的多。一旦你熟悉了 `assertThat` 的用法，通过 Hamcrest 网站并尝试额外的功能，你将会编写出比简单 `assert` 更多的代码。理想情况下应该会让断言背后的意图易于阅读和理解。你可以从实验断言中获得很多价值，帮助你构建代码并移动到正确的级别：

- 类级（`@Before` 和 `@After`）
- 方法级（`@Before` 和 `@After`）

## 参考与推荐阅读

- [JUnit 主页](https://junit.org)
- [JUnit 异常检查](https://github.com/junit-team/junit)
- [JUnit 断言](https://github.com/junit-team/junit/Assertions)
- [Hamcrest 主页](https://hamcrest.com)
- [Hamcrest 教程](https://code.google.com/p/hamcrest/Tutorial)

# 第十五章 - 字符串回顾

## 章节总结

在本章中，你将回顾已经知道的内容，并学习更多关于字符串的知识：

- `String` 是具有许多有用方法的对象，而不是字符的容器
- `System.out.println` - 将 `String` 打印到控制台
- 使用以下编码的特殊字符：例如 `\t`、`\b`、`\n`、`\`、`\"`
- 使用 `concat` 方法连接字符串
- 使用 `toString` 方法将其转换为 `String`
- 使用 `valueOf` 方法从 `char[]`、`byte[]`、`StringBuffer`、`StringBuilder` 等对象构造 `String`
- `String` 对象有许多比较方法
    - `compareToIgnoreCase` - 等于 `compareTo`，但忽略大小写
    - `contains` - 返回参数是否在 `String` 中
    - `contentEquals` - 返回内容是否等于参数
    - `equals` - 返回内容是否等于参数
    - `equalsIgnoreCase` - 等于 `equals`，但忽略大小写
    - `endsWith` - 返回是否以参数结尾
    - `startsWith` - 返回是否以参数开头
    - `isEmpty` - 返回长度是否为0
    - `indexOf` - 返回 substring 的索引位置
    - `lastIndexOf` - 返回 substring 的最后一个索引
    - `regionMatches` - 比较 `String` 的区域
    - `matches` - 易于使用正则表达式匹配
- 使用 `replace`、`replaceAll`、`replaceFirst` 替换 `String` 的部分
- 使用 `toUpperCase` 和 `toLowerCase` 进行大小写转换
    - `trim` - `String` 中的空格
    - `substring` - 返回 `String` 的部分
    - `format` - 使用简单的字符串模板
    - `split` - 解析字符串
    - `StringBuilder` - 构建字符串：`append`、`delete`、`insert`、`replace`

你在整本书中已经看到过字符串的用法。本章将所有这些信息汇集到一个章节，因为 `String` 是构建我们的 `@Test` 方法和抽象层的本质对象。我们的许多字段将以字符串形式开始，例如 `username`、`password`。在某些时刻我们可能会让它们成为对象，因为我们可以让他们负责自身的验证。

## 字符串总结

对已学内容的简要总结。`String` 是 `java.lang` 中的一个对象，所以我们不需要担心导入。

```java
String aString = "abcdef";
```

字符串字面量也是一个对象，所以我们可以在字符串字面量上调用方法。

```java
assertThat("hello".length(), is(5));
```

可以使用运算符连接字符串。

```java
assertEquals("123456", "12" + "34" + "56");
```

`String` 是不可变的。一旦创建了 `String` 就不能修改它，它看起来像我们在修改它，但实际上我们是在创建一个新的 `String` 对象。

这意味着 Java 可以在整个代码中重用相同的 `String` 值，即使我们在多个地方使用 `String`，它也不会占用内存。当然，我们不应该以此为理由在代码中重复字符串字面量，因为那会让我们的代码更难维护。

## System.out.println

你在之前的代码中看到过 `System.out.println`，此语句允许我们将 `String` 对象查看到控制台。

当你尝试获取代码的见解并生成粘贴到应用程序中的临时文件或字符串时，它是非常有用的。

它可以作为一个简单的日志工具，例如在控制台打印执行进度，或将变量作为输入数据打印。

以下示例代码展示了这一点：

```java
int i=4;
System.out.println("Print an int to the console " + i);
```

注意在上面的示例中，`int` 在输出时自动转换为 `String` 并连接到字符串字面量：

Print an int to the console 4

## 特殊字符编码

我们在之前的章节中遇到过转义序列。

- `\t` - 制表符
- `\b` - 退格符
- `\n` - 换行
- `\r` - 回车符
- `\'` - 单引号
- `\"` - 双引号
- `\\` - 反斜杠

```java
System.out.println("Bob said \"hello\" to his cat's friend\"");
System.out.println("This is a single backslash \\\"");
```

输出：

Bob said "hello" to his cat's friend
This is a single backslash \

## 练习：尝试使用其他特殊字符

在某些 `@Test` 方法中实验其他特殊字符例如 `\"t`、`\"b`、`\"n`、`\"r`，并观察 `System.out.print` 打印到控制台时的效果。

## 比较字符串

`String` 提供了许多比较和搜索方法：

- `compareTo` - 如果字符串相等则返回 0
- `compareToIgnoreCase` - 与 `compareTo` 相同，但忽略大小写
- `contains` - 如果参数包含在 `String` 中则返回 true
- `contentEquals` - 如果 `String` 与参数的内容相同则返回 true
- `equals` - 如果内容相等则返回 true
- `equalsIgnoreCase` - 与 `equals` 相同，但忽略忽略大小写
- `endsWith` - 如果字符串的末尾与参数匹配则返回 true
- `startsWith` - 如果字符串的开头与参数匹配则返回 true
- `isEmpty` - 如果 `String` 的长度为 0 则返回 true
- `indexOf` - 返回子字符串在 `String` 中的位置
- `lastIndexOf` - 从字符串末尾开始搜索子字符串的位置
- `regionMatches` - 比较字符串的某个区域与另一个字符串的区域

## indexOf & lastIndexOf

`indexOf` 方法返回参数在 `String` 中首次出现的位置。

```
"Hello fella"
01234567890
```

`lastIndexOf` 方法返回参数在 `String` 中最后出现的位置。

`indexOf` 和 `lastIndexOf` 都可以带有一个额外的参数，用于指定从 `String` 的哪个位置开始搜索。

```java
String hello = "Hello fella";
assertThat(hello.indexOf('l', 3), is(3));
assertThat(hello.indexOf('l', 4), is(8));
```

如果 `indexOf` 或 `lastIndexOf` 在 `String` 中没有找到字符或子字符串，则方法返回 -1（负一）。

```java
assertThat(hello.indexOf('z'), is(-1));
assertThat(hello.lastIndexOf("z"), is(-1));
```

## 练习：查找字符串中所有出现的位置

- 编写一个方法，接收一个 `String` 和一个子字符串作为参数，并返回一个 `List<Integer>`，其中每个 Index 是子字符串在 `String` 中的位置。
    - 例如 `findAllOccurrences("Hello fella", "l")` 将返回一个包含值 2,3,8,9 的 `List<Integer>`
    - 额外加分项：编写 `findAllOccurrences` 方法，以反序返回列表，即 9,8,3,2

## contentEquals & equalsIgnoreCase

`contentEquals` 方法如果 `String` 与参数的内容相同则返回 true，否则返回 false。

```java
String hello = "Hello";
assertThat(hello.contentEquals("Hello"), is(true));
assertThat(hello.contentEquals("hello"), is(false));
```

`contentEquals` 方法适用于任何实现了 `CharSequence` 接口的对象，或者对比 `StringBuffer`（例如 `StringBuilder`）。

`equals` 方法强制执行了一个额外规则：参数必须是 `String`，且内容相等。

`equalsIgnoreCase` 方法的工作原理与 `equals` 相同，但在比较时忽略大小写。

```java
assertThat(hello.equalsIgnoreCase("hello"), is(true));
```

## endsWith & startsWith

`endsWith` 方法比较字符串的末尾与参数。

```java
String hello = "Hello";
assertThat(hello.endsWith("Hello"), is(true));
```

`startsWith` 方法比较字符串的开头与参数。

```java
assertThat(hello.startsWith("Hello"), is(true));
assertThat(hello.startsWith(""), is(true));
assertThat(hello.startsWith("He"), is(true));
```

`endsWith` 和 `startsWith` 均实现大小写敏感的搜索。

```java
assertThat(hello.startsWith("he"), is(false));
assertThat(hello.startsWith("Lo"), is(false));
```

## isEmpty

`isEmpty` 方法如果 `String` 的长度为 0 则返回 true，如果长度 > 0 则返回 false。

```java
String empty = "";
assertThat(empty.isEmpty(), is(true));
assertThat(empty.length(), is(0));
```

## regionMatches

`regionMatches` 方法允许使用索引来指定 `String` 中的某个区域，在该区域内查找另一个字符串的区域。

```java
regionMatches(boolean ignoreCase, int offset, int toOffset, String other, int offset, int len)
```

或者：

```java
region(int offset, String other, int offset, int len)
```

给定一个特定的字符串：

```
"Hello fella"
01234567890
```

我可以在上述字符串中搜索子字符串，例如：

```java
String hello = "Hello fella";
assertThat(
    hello.regionMatches(true, 6, "fez", 0, 2),
    is(true)
);
```

在上述示例中，我指定了：

- `hello` String 的搜索区域从位置 6 开始，直到到字符串末尾
- 子字符串为 "fez"，且
  - 我希望这个 "fez" String 的区域从位置 0 开始，
  - 长度仅为 2 个字符

实际上，我是在位置 6 开始在字符串中查找 "fe"。这是一个比较复杂的方法，我倾向于使用 `contains`。

## 使用正则表达式

正则表达式是处理字符串的极其强大的工具。

Java 有一个专门用于正则表达式的包 `java.util.regex`，但详细查看正则表达式的处理超出了本书的论述范围。我在本章的“参考资料”部分列出了我使用的主要参考资料。

在本书中，我想通过 `.matches` 方法向你介绍正则表达式。

正则表达式是一种字符串，其中某些字符具有特殊含义，例如通配符或分组结构。“正则表达式（Regular Expression）”通常缩写为“Regex”。

`matches` 方法帮助我们完成最简单的正则表达式任务，即回答“这个正则表达式是否匹配这个字符串？”

使用正则表达式的一个示例场景可能是我们想要扩展 User 类中的密码验证：

我们可以使用 `indexOf` 运算符并遍历数字或大写字母，在字符串中查找它们。但那是一种比较困难的方法，它需要复杂的循环，并可能导致产生 Bug 的代码。

或者，我们可以构建一个正则表达式，仅匹配符合这些条件中的每一个项。

例如，我可以写一个匹配字符串的正则表达式，并检查它是否包含数字 `.*[0123456789].*`。

从高层次来说，上述正则表达式的意思是：

- `.*` - 匹配 0 个或多个字符
- `[0123456789]+` - 直到我们找到 1 个或多个以下字符“0123456789”
- `.*` - 后面可以跟着 0 个或多个字符

进一步详细说明：

- `.` - 匹配任何单个字符
- `*` - 匹配前一个元素的 0 个或多个
- `[]` - 匹配括号内包含的任意单个字符
- `+` - 匹配前一个元素的 1 个或多个

我可以像下面一样在 Java 代码中使用它：

```java
String mustIncludeDigit = ".*[0123456789].*";
```

我将正则表达式赋值给一个变量以便复用。

我在字符串上调用方法，并将正则表达式作为参数传入，如果正则表达式匹配字符串，则返回 true。

如果匹配失败，则返回 false。

```java
assertThat("123456789").matches(mustIncludeDigit), is(true));
assertThat("invalid").matches(mustIncludeDigit), is(false));
```

我可以写一个类似的正则表达式来匹配大写字母：

```java
String mustIncludeUppercase = "[A-Z].*";
```

我使用了一个额外的条件来构建正则表达式：

- `A-Z` 在 `[A-Z]` 中 - 匹配 A-Z 之间的任意字符，这样我可以做到...

```java
assertThat("Valid").matches(mustIncludeUppercase), is(true));
assertThat("valid").matches(mustIncludeUppercase), is(false));
```



## 练习：用于用户集的正则表达式

在 `User` 类的 `setPassword` 方法中添加正则表达式，如果密码不包含数字或不包含大写字母，则抛出 `IllegalPassword` 异常。

## 使用正则表达式

当你刚接触正则表达式时，它们看起来可能很令人生畏。每当我回到它们时，它们似乎都很令人生畏，因为我忘记了很多细节以及如何编写它们。所以，我想告诉你们我如何重新进入状态的秘密。

1. 我使用 regular-expressions.info 来帮助我记忆语法
2. 我使用像 regexpal.com 这样的工具来构建并针对示例文本检查正则表达式
3. 我使用像 RegexBuddy (regexbuddy.com) 这样的桌面工具来帮助构建和检查正则表达式。RegexBuddy 还能构建可用的代码片段
4. 我编写 JUnit 测试来检查我的正则表达式是否正常工作
5. 我对使用正则表达式的代码编写 JUnit 测试，例如测试 `setPassword` 方法

当你掌握了正则表达式后，它们是一个非常强大的工具。随着你对 Java 的经验越来越丰富并开始使用 `java.util.regex` 包，你可以使用正则表达式来解析字符串并使用正则表达式提取子字符串。但目前，请从 `.matches` 方法开始，习惯编写正则表达式来进行校验。

## 字符串操作

### 替换字符串

Java 在 `String` 上提供了三个方法来帮助我们生成新字符串，但将字符串中的元素替换为其他字符。

- `.replace` - 将所有匹配的子字符串替换为新的子字符串
- `.replaceAll` - 将所有匹配正则表达式的子字符串替换为新的子字符串
- `.replaceFirst` - 将第一个匹配正则表达式的子字符串替换为子字符串

```java
String hello = "Hello fella fella fella";

assertThat(hello.replace("fella", "World"), is("Hello World World World"));
```

你可能会疑惑为什么对于普通字符串没有 `replaceFirst`，而是直接使用正则表达式。原因是“普通”字符串本身就是一个正则表达式，但它只匹配该字符串本身。这允许我使用 `replaceFirst` 将第一个出现的 fella 替换为 world：

```java
assertThat(hello.replaceFirst("fella", "world"));
```

并且，当正则表达式是一个不包含任何正则表达式特殊字符的字符串字面量时，我可以使用 `replaceAll` 代替 `replace`：

```java
assertThat(hello.replaceAll("fella", "World"), is("Hello World World"));
```

`replaceFirst` 和 `replaceAll` 提供了一种非常简单的方法来利用正则表达式的额外功能。例如，将数字替换为字符串 "digit"：

```java
assertThat("1,2,3".replaceFirst("[0-9]", "digit"), is("digit,2,3"));
```

```java
assertThat("1,2,3".replaceAll("[0-9]", "digit"), is("digit,digit,digit"));
```

### 大写和小写

Java 提供了非常直观的方法来将整个字符串转换为大写或小写：

- `.toUpperCase` - 将字符串转换为大写
- `.toLowerCase` - 将字符串转换为小写

```java
String text = "In the lower 3rd";
```

```java
assertThat(text.toUpperCase(), is("IN THE LOWER 3RD"));
```

```java
assertThat(text.toLowerCase(), is("in the lower 3rd"));
```

### 空格

`String` 方法可以移除字符串首尾的空格。

```java
String text = "  hello  ";

assertThat(text.trim(), is("hello"));
```

### StringBuilder

`StringBuilder` 继承自 `StringBuffer`，并且速度稍快，但仅适用于单线程应用程序。当你将 Java 进展到使用多线程的阶段时，你可能需要改用 `StringBuilder`。

#### 构建 StringBuilder

我们可以构造一个空的 `StringBuilder`：

```java
StringBuilder builder = new StringBuilder();
```

我们可以从任何实现了 `CharSequence` 接口的类型（例如 `String`）构造一个带有起始字符串值的 `StringBuilder`：

```java
StringBuilder sb = new StringBuilder("hello");
```

#### 容量管理

由于 `StringBuilder` 维护其所分配的字符串的内部表示，因此它为内部表示分配了特定的内存容量。当向 `StringBuilder` 中添加项时，容量会自动增加。

默认情况下，如果你使用无参数构造函数，容量为 16。

```java
StringBuilder builder = new StringBuilder();

assertThat(builder.capacity(), is(16));
```

你可以通过 `capacity` 方法找到当前容量。

你可以根据需要构造一个特定容量的 `StringBuilder`。

```java
StringBuilder sblen = new StringBuilder(512);

assertThat(sblen.capacity(), is(512));

assertThat(sblen.toString().length(), is(0));
```

对于自动化，我们通常不需要担心容量，但如果你编写的代码需要快速，可能会调整 `StringBuilder` 的大小以避免频繁重新分配内存。你可以使用 `ensureCapacity` 方法在构造后调整 `StringBuilder` 的大小。

```java
builder.ensureCapacity(600);
```

如果你修改了容量或删除了大量字符串，可以将容量设置为容纳字符串所需的最小值：

```java
builder.trimToSize();
```

#### 向 StringBuilder 添加内容

`append` 方法的工作类似于字符串拼接方法 `+`。我们可以将对象、原始类型、字符串和 `char[]` 添加到 `StringBuilder` 的末尾。

```java
StringBuilder builder = new StringBuilder(">");
```

```java
builder.append(2);

char[] ca = {'=', ' ', '3'};

builder.append(ca);

assertThat(builder.toString(), is(">2 = 3"));
```

在添加过程中，如果添加的字符超过了当前容量，`StringBuilder` 会自动调整大小。

**练习：检查 StringBuilder**

写一个方法验证当添加的字符超过当前容量时，`StringBuilder` 会调整大小。

#### 插入

`insert` 方法支持与 `append` 方法相同的对象和原始类型。当我们向 `StringBuilder` 插入时，必须指定插入的位置：

```java
StringBuilder builder = new StringBuilder("123890");

builder.insert(3, "4567");

assertThat(builder.toString(), is("1234567890"));
```

在 Java 中，索引从 0 开始。如果索引大于字符串的内部表示长度，将抛出 `StringIndexOutOfBoundsException`。当 `StringBuilder` 有某些值时，我们可以在以下位置插入：

- 头部
- 尾部
- 中间

**练习：插入到 StringBuilder**

向一个空的 `StringBuilder` 插入一个字符串。在末尾插入一个字符串。在中间插入一个字符串。除了索引外，我们还可以指定从字符数组复制的字符数量。给定以下带有 "abgh" 的 `StringBuilder`：

```java
char[] ca = {'.', 'a', 'b', 'c', 'd', 'e', 'f'};

StringBuilder builder = new StringBuilder("abgh");
```

代码将在字符串的位置 2 插入（即 'b' 之后）从位置 3（'c'）开始的后续 4 个字符：

```java
// 字符串中的位置 2
// 从索引 3 开始的 char[] ca
// 插入后续 4 个字符 (cdef)

builder.insert(2, ca, 3, 4);

assertThat(builder.toString(), is("abcdefgh"));
```

#### 删除

我们可以根据索引删除子字符串：

```java
StringBuilder builder = new StringBuilder("abcdefgh");

builder.delete(2, 4);

assertThat(builder.toString(), is("abefgh"));
```

给定字符串 "abcdef"：

- 指定删除的起始索引，例如 2，即 "c"
- 指定删除的结束索引，例如 4，即跨越 "cd" 即 "cd"

或者我们可以使用 `deleteCharAt` 删除指定索引处的特定字符：

```java
builder.deleteCharAt(2);

assertThat(builder.toString(), is("abefgh"));
```

#### 替换子字符串和字符

我们可以使用 `replace` 方法替换子字符串，该方法接受起始索引、结束索引和字符串作为参数。从起始索引到结束索引的字符会被字符串替换：

```java
StringBuilder builder = new StringBuilder("abcdefgh");
builder.replace(0, 4, "12345678");
assertThat(builder.toString(), is("12345678gh"));
```

我们可以使用 `setCharAt` 方法替换单个字符：

```java
StringBuilder builder = new StringBuilder("0123456789");
builder.setCharAt(5, 'f');
assertThat(builder.toString(), is("01234f789"));
```

#### 反转

反转字符串的能力非常有用。`StringBuilder` 内置此意味着我经常使用 `reverse()` 来构造 `StringBuilder`。

```java
StringBuilder builder = new StringBuilder("0123456789");
assertThat(builder.reverse().toString(), is("9876543210"));
```

#### 子字符串

`substring` 方法返回从起始索引到结束索引的字符串：

```java
StringBuilder builder = new StringBuilder("0123456789");
assertThat(builder.substring(3, 7), is("3456"));
```

或者从起始索引到字符串末尾的：

```java
assertThat(builder.substring(3), is("3456789"));
```

### StringBuilder 总结

`StringBuilder` 是一个非常强大的类，它避免了使用大量字符串并不断拼接的需求。`StringBuilder` 的使用也非常高效，因为它使用内部表示而不是在方法调用时构造新对象。

为了效率，我们可以自己维护容量，并根据当前任务调整 `StringBuilder` 的大小，而不是让 `StringBuilder` 在每次调用方法时动态调整。

`StringBuilder` 还有这里没有涵盖的方法，这里是你将经常使用的 `StringBuilder` 主要功能的概述。

我使用 `StringBuilder` 来构建字符串，因此主要使用 `append` 和 `insert` 方法。我很少使用 `replace` 和 `substring` 方法，倾向于直接使用 `String` 类进行替换和处理子字符串。

你将形成自己的风格，并使用对你来说最有逻辑的类。

要查看完整文档和所有方法，请参考引用中的链接或使用 IDE 中的代码补全。记得在 IntelliJ 中，按下 `ctrl + q` (Windows) 或 `ctrl + j` (Mac)，代码补全弹出框将显示方法的 JavaDoc 文档。

## 拼接、.format 还是 StringBuilder

如何选择构建字符串的正确方法？

我们看到了许多构造字符串的不同方式：

- 使用 `+` 进行简单拼接
- 使用 `String.format` 使用简单模板
- 使用 `StringBuilder` 进行灵活的插入、添加和删除

那么哪种最好呢？

嗯，我都用。

对于简单的字符串构建，我使用拼接。

当拼接过多导致代码难以阅读和维护时，或者当我们需要多处复用格式字符串时，我使用格式化。我尽量记住在只有少量一组拼接时也使用 `String.format`，但有时我会偷懒直接将字符串拼接在一起。

如果我要长时间构建一个字符串，或者需要在多个方法调用之间构建字符串，我倾向于使用 `StringBuilder`。

我不认为有一个标准答案。但请注意，你有多种选择。

尽量让你的代码具有可读性和可维护性。因此，请选择有助于你构建长久代码的方法。

## 总结

当你一直使用字符串进行自动化时：表示数据、解析文件、处理 JSON、创建 HTTP 请求等。

因此，我使用了许多基础字符串处理方法和 `StringBuilder` 生成方法。

本章涵盖了许多基础知识，尽管我们没有在许多领域进行深入探讨。在处理自动化和数据时，可以翻阅本章，你会发现这里列出了许多你正在使用或可以使用的基础函数。

我尝试涵盖了大部分我字符串处理需求背后的方法和类，希望这能满足你最初及未来的需求。

## 参考文献和推荐阅读

- Java 转义序列
  - docs.oracle.com/javase/tutorial/java/data/characters.html
- Java 字符串教程
  - docs.oracle.com/javase/tutorial/java/data/strings.html
- Java 字节编码与字符串
  - docs.oracle.com/javase/tutorial/i18n/text/string.html
- 字符串格式语法
  - docs.oracle.com/javase/7/docs/api/util/Formatter.html#syntax
- StringBuilder 教程
  - docs.oracle.com/javase/7/docs/api/java/lang/StringBuilder.html
- StringBuilder 文档
  - docs.oracle.com/javase/7/docs/api/java/lang/StringBuilder.html
- Java 正则表达式
  - docs.oracle.com/javase/tutorial/essential/regex
- 正则表达式信息和教程
  - regular-expressions.info/
- 维基百科正则表达式
  - en.wikipedia.org/wiki/Regular_expression
- 在线正则表达式测试器
  - regexpal.com
- RegexBuddy 桌面工具
  - regexbuddy.com

# 第十六章 - 随机数据

## 章节总结

在本章中，你将学习如何使用 Java 的 `Random` 功能来创建随机数据：

- `Math.random()` - 易用的静态随机生成器，用于生成 0.0 到 1.0 之间的随机 double
- `java.util.Random` - Java 主要的随机包：
  - `nextBoolean()` - 返回 true 或 false
  - `nextLong()` - 返回一个随机值
  - `nextInt()` - 在所有 Integer 值的范围内生成随机数
  - `nextInt(int bound)` - 大于或等于 0 且小于 bound 的随机数
  - `nextDouble()` - 0.0 到 1.0 之间每个值出现概率相等的分布
  - `nextGaussian()` - 平均值为 0.0、标准差为 1.0 的高斯分布，这意味着约 70% 的值集中在 0.0 附近（+1.0 或 -1.0）
  - `nextFloat()` - 大于或等于 0.0 且小于 1.0 的随机 float
  - `nextBytes()` - 用随机字节填充给定的 `byte[]`
- 使用 `new Random(seed)` 为随机数生成设置种子
- 生成随机字符串



# Java 随机数据生成

自动化中的随机数据是一个备有争议的话题。有些人认为自动化应该是完全确定性的，并且始终以相同的方式运行——这意味着我们总是使用相同的数据。我更倾向于改变对检查条件不重要的数据，即应该作为等价类一部分的数据。通过这样做，我们增加了自动化的数据覆盖率，并增加了自动化检查发现 bug 的可能性。

Java 有一组非常简单的随机方法和类。

- `java.util.Random`
- `Math.random()`

Java 作为安全包的一部分，有一个 `SecureRandom` 类，它暴露了与本章中讨论的相同的方法。我没有在书中介绍 `SecureRandom`，是因为：

- 我从未在生产环境自动化代码中使用过它，
- 实例化速度稍慢，
- 稍微难用一点。

你在自动化代码中需要的大部分随机性可以通过 `java.util.Random` 实现。

## Math.random

`Math` 静态随机方法提供一个“伪随机”数。

它实际上是 `java.util.Random.nextDouble()` 方法的封装，但使其使用变得非常简单。

当第一次调用 `Math.random()` 时，会创建一个新的随机数生成器，用于每次调用 `Math.random()`。`Math.random()` 返回一个大于或等于 0.0 且小于 1.0 的 double。

```java
double rnd = Math.random();
System.out.println("generated %f as random number", rnd);
assert(rnd < 1.0);
assert(rnd >= 0.0);
```

## java.util.Random

`java.util.Random` 类提供了以下生成随机值的方法：

### boolean
- `nextBoolean()` - 返回 true 或 false

### long
- `nextLong()` - 返回一个随机值

### int
- `nextInt()` - 在所有 Integer 值的范围内生成随机数
- `nextInt(int bound)` - 生成大于或等于 0 且小于 bound 的随机数

### double
- `nextDouble()` - 0.0 到 1.0 之间每个值出现概率相等的分布
- `nextGaussian()` - 平均值为 0.0、标准差为 1.0 的高斯分布，这意味着约 70% 的值集中在 0.0 附近（+1.0 或 -1.0）

### float
- `nextFloat()` - 大于或等于 0.0 且小于 1.0 的随机 float

### byte
- `nextBytes(byte[] bytes)` - 用随机字节填充给定的 byte[]

使用 `new Random(seed)` 为随机数生成设置种子。

## 生成随机字符串

[此处原文缺失具体实现代码，保留标题占位]



- `nextBytes()` - 用随机字节填充给定的 `byte[]`

- 使用 `new Random(seed)` 为随机数生成设置种子

- 生成随机字符串

自动化中的随机数据是一个备有争议的话题。有些人认为自动化应该是完全确定性的，并且始终以相同的方式运行——这意味着我们总是使用相同的数据。我更倾向于改变对检查条件不重要的数据，即应该作为等价类一部分的数据。通过这样做，我们增加了自动化的数据覆盖率，并增加了自动化检查发现 bug 的可能性。

Java 有一组非常简单的随机方法和类。

- `java.util.Random`

- `Math.random()`

Java 作为安全包的一部分，有一个 `SecureRandom` 类，它暴露了与本章中讨论的相同的方法。我没有在书中介绍 `SecureRandom`，是因为：

- 我从未在生产环境自动化代码中使用过它
- 实例化速度稍慢
- 稍微难用一点

你在自动化代码中需要的大部分随机性可以通过：

- `java.util.Random`

## Math.random

`Math` 静态随机方法提供一个“伪随机”数。

它实际上是 `java.util.Random.nextDouble()` 方法的封装，但使其使用变得非常简单。

当第一次调用 `Math.random()` 时，会创建一个新的随机数生成器，用于每次调用 `Math.random()`。`Math.random()` 返回一个大于或等于 0.0 且小于 1.0 的 `double`。

```java
double rnd = Math.random();
System.out.println("generated %f as random number", rnd);
assert(rnd < 1.0);
assert(rnd >= 0.0);
```

## java.util.Random

`java.util.Random` 包提供了以下生成随机值的方法：

- boolean
  - `nextBoolean()` - 返回 true 或 false

- long
  - `nextLong()` - 返回一个随机值

- int
  - `nextInt()` - 在所有 Integer 值的范围内生成随机数
  - `nextInt(int bound)` - 大于或等于 0 且小于 bound 的随机数

- double
  - `nextDouble()` - 0.0 到 1.0 之间每个值出现概率相等的分布
  - `nextGaussian()` - 平均值为 0.0、标准差为 1.0 的高斯分布，这意味着约 70% 的值集中在 0.0 附近（+1.0 或 -1.0）

- float
  - `nextFloat()` - 大于或等于 0.0 且小于 1.0 的随机 float

- byte
  - `nextBytes()` - 用随机字节填充给定的 `byte[]`

在处理年龄（ages）时，你可能需要添加额外的代码来确保最小最大值，尽管出现极端值的概率很低，但可能会发生。

### 练习：编写一个使用 nextGaussian 生成 1000 个年龄的 @Test 方法

编写一个 `@Test` 方法，使用均值为 35、标准差为 5 的 `nextGaussian()` 生成 1000 个年龄。统计生成的每个年龄，并将排序后的年龄和计数列表输出到控制台。

例如：

```
34 : 70
35 : 167
36 : 83
37 : 80
38 : 66
39 : 51
```

## 随机数种子

随机数是“伪随机”的，因为它们基于“种子”（seed），如果控制了“种子”，每次对“random”的调用都是确定性的。

例如：

```java
Random generate = new Random(1234567L);
```

将生成一个随机数生成器，其中 `nextInt()` 返回 1042961893。

### 练习：为带种子的 Random 创建一个 @Test 方法

为种子 `1234567L` 创建一个 `@Test` 方法，并断言：

- `nextInt() == 1042961893`
- `nextLong() == -674250865724111202L`
- 继续断言并添加：
  - `nextDouble()`
  - `nextGaussian()`
  - `nextFloat()`
  - `nextBoolean()`

确保你可以重新运行该方法并获得相同的“随机”数字。

当你想要让方法的执行具有可重复性时，这非常有用。例如，如果在运行开始时使用当前日期时间运行 `Random`，如果你记录了日期时间，即使使用了随机数据，你也可以精确地重复运行。

例如：

```java
long currentSeed = System.currentTimeMillis();
System.out.println("seed used: " + currentSeed);
```

```java
Random generate = new Random(currentSeed);
```

如果 `System.out.println` 是一个日志调用，那么我就可以通过输出中记录的种子值为随机数设置种子，从而重建运行。

## 使用随机数生成随机字符串

生成随机字符串的一种粗糙方法是通过向字符串中随机添加有效字符来构建字符串。

例如，如果我想从大写字母和空格构建一个字符串：

```java
String validValues = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
```

那么我就可以从该字符串中随机选择一个字符：

```java
int rndIndex = random.nextInt(validValues.length());
char chr = validValues.charAt(rndIndex);
```

如果我循环这个生成过程并拼接结果，就可以生成一个随机字符串。

### 练习：生成一个 100 字符的随机字符串

生成一个长度为 100 个字符、包含 ' '（空格）和 'A' 到 'Z' 字符的随机字符串。

## 关于自动化中随机数据的讨论

很多人不喜欢在他们的自动化中添加随机数据。

我喜欢。

我将自动化检查视为带有变量数据执行系统中的特定路径。

某些数据是控制路径所需的，如果我更改这些数据，我就会运行不同的路径。

例如：如果我只在 65 岁时才被要求提供护照号码，如果我创建一个不是 65 岁的用户，我就无法覆盖该路径。但如果我在 65 岁或以上时被要求提供护照号码，那么我就有一个等价类。如果我随机生成一个 65 岁或更大的年龄，我就可以覆盖它。这对于 `@Test` 方法应该没有区别，因此我可以更改数据。如果我更改了数据但 `@Test` 方法没有按预期运行，我可能发现由于我们对等价类的理解存在 Bug，但也可能发现了一个与应用程序处理特定年龄有关的 Bug。

我使用随机性为等价类生成数据，并控制需要保持静态以满足执行路径前提条件的数据。

## 使用随机数据时记录日志重要性

当我使用随机数据时，我需要记录它。

最简单的日志记录机制是 `System.out.println`，如果我的 `@Test` 方法向控制台写入它们已使用的数据输出，那么我以后可以使用该输出来重建运行。因为方法可能由于特定的随机值组合而失败，我需要使用该数据重现任何断言。

我可能需要创建一个机制来使用特定数据重新运行方法，在这种情况下，为随机机制设置种子并记录种子值可能是合适的解决方案。

在大多数生产环境的随机化中使用，我已经通过将随机生成的输出记录到 `System.out.println` 来。当代码作为持续集成的一部分运行时，日志会出现在 `System.out` 中，如果断言失败，我们可以查看日志并使用种子来精确地重建执行。从简单的功能开始你的自动化。要能够看到你使用了哪些数据，以便你可以手动重新运行并判断随机数据是否触发了 Bug。

## 总结

你通过后面使用 `nextGaussian()` 和字符串生成的示例看到，即使只有一小组随机函数，我们也轻松地使用它们来生成复杂的数据。

## 参考文献和推荐阅读

- 标准差 (Standard Deviation)
  - <en.wikipedia.org/wiki/Standard_deviation>
- 数学 (Math)
  - <docs.oracle.com/javase/7/docs/api/lang/Math.html>
- java.util.Random
  - <docs.oracle.com/javase/7/docs/api/util/Random.html>
- 关于在范围内生成值的提示 (Hints on generating values in range)

# 第十七 - 日期与时间

## 总结

在本章中，你将学习使用 Java：

- `System.currentTimeMillis` - 自 1970 年 1 月 1 日以来的毫秒
- `System.nanoTime` - 纳秒
- `Date`
- `Calendar`
- `SimpleDateFormat`
- `String`
- `format`
- `wrapper`
- `days`
- `months`
- `pattern`
- 范围
- 差异
- 路径

一个纳秒是秒的十亿分之一。我通常使用这些方法来：

- 计算任务花费的时间
- 创建唯一的 ID 和文件名

## 计算任务所花费的时间

为了计算任务所花费的时间，我会：

- 实例化 `startTime`
- 执行任务
- 实例化 `endTime`
- 计算 `totalTime` 为 `endTime - startTime`

例如，为了向控制台输出十次 `currentTimeMillis`，我可以编写如下代码：

```java
@Test
public void currentTimeMillis() {
  long startTime = System.currentTimeMillis();

  for (int x = 0; x < 10; x++) {
    System.out.println("Current Time " + System.currentTimeMillis());
  }

  long endTime = System.currentTimeMillis();
  System.out.println("Total Time " + (endTime - startTime));
}
```

当我运行这段代码时，我会得到一个 1 左右的总值，但有时我会得到 0 总值，因为结束任务发生在 `currentTimeMillis` 校准的同一个“毫秒”内。

`currentTimeMillis` 所表示值的精度会随操作系统而异，它不能保证是“毫秒”，它可能更多，例如几十毫秒。虽然这对于精确时间来说不是一个很好的方法，但对于自动化计时来说通常足够，特别是当你最终要四舍五入到秒时。

假设你没有将计算机时钟重置过去，它对于唯一的数字或值有什么用处？

> 练习：使用 nanoTime 重写计时 @Test 方法

使用 `nanoTime` 重写上面的 `millis@Test` 方法并观察输出的差异。

使用 `nanoTime` 时，分辨率再次由底层操作系统决定，但以纳秒为报告。

- `nanoTime` 更适合计算运行快速的任务持续时间，并且你希望获得更准确的测量。
- `nanoTime` 对于创建唯一的数字没有用，因为你并不真正知道 JVM 时间的依据。

为了创建唯一的标识符或名称，我经常会在 `currentTimeMillis()` 的值前面加上字符串前缀：

```java
String userID = "user" + System.currentTimeMillis();
```

这种方法虽然粗糙简单，但快速且直观。

例如：`user142410138642`

### 练习：使用 currentTimeMillis 创建一个不包含数字的唯一名称

我们需要创建一个唯一的名称，其中包含所有字母，即不包含数字。

- 创建一个测试，从 `currentTimeMillis` 生成一个唯一的字符串，但最终字符串中不包含数字。

## Date

`Date` 类暴露了一组少量的方法。

```java
Date date = new Date();
```

`Date` 提供的方法有：

- `after` - 如果参数 date 在 Date 对象之后，则返回 true
- `before` - 如果参数 date 在 Date 对象之前，则返回 true
- `compareTo` - 如果两个 Date 对象相等则返回 0；如果 Date 对象小于参数则返回负数；如果 Date 对象大于参数，则返回正数
- `equals` - 如果参数和 Date 代表相同的日期和时间，则返回 true
- `setTime` - 将 Date 代表的时间设置为特定的毫秒值
- `getTime` - 返回 Date 所代表的自 1970 年 1 月 1 日午夜以来的毫秒数
- `toString` - 返回日期的字符串表示

不带参数实例化 `Date` 将把 Date 代表的时间默认设置为与 `System.currentTimeMillis()` 相同的值。

以下两个语句本质上是等价的：

```java
Date equivDate1 = new Date();
Date equivDate2 = new Date(System.currentTimeMillis());
```

`toString` 方法提供了一种输出日期字符串的简单方法。

```java
System.out.println(date.toString());
```

在我的机器上，`toString` 输出的格式如下：

- Thu Jun 20 12:18:04 BST 2013

我们将在下一节学习如何控制 Date 的输出。

我们也可以通过 `long` 类型实例化 `Date`，以便将 Date 设置为特定的时间。

例如，我可以通过操作实例化 `Date` 时的 `long` 值，创建一个当前 Date 之后 7 天的 `Date`：

```java
long oneWeekFromNowTime = date.getTime();
oneWeekFromNowTime = oneWeekFromNowTime + (1000 * 60 * 60 * 7);
Date oneWeekFromNow = new Date(oneWeekFromNowTime);
System.out.println(oneWeekFromNowTime.toString());
```

在上面的代码中，我从一个 `Date` 获取时间，然后向 `long` 值加上 7 天的毫秒数，并从该毫秒值实例化新的 `Date`。结果输出如下：

- Thu Jun 27 12:18:04 BST 2013

我们使用 `setTime` 在构造后设置日期的时间值，因此我可以使用构造函数或 `setTime` 方法创建一个重复的时间：

```java
Date sameDate = new Date();
sameDate.setTime(date.getTime());
assertThat(date.equals(sameDate), is(true));
assertThat(date.compareTo(sameDate), is(0));
```

## SimpleDateFormat

`SimpleDateFormat` 允许我们按照选择的格式将 `Date` 对象的值输出为字符串。

```java
SimpleDateFormat sdf = new SimpleDateFormat();
```

如果我实例化一个 `Date` 为 1970 年 1 月 1 日：

```java
SimpleDateFormat sdf = new SimpleDateFormat();
```

那么下表显示了示例模式以及相关的生成的输出：

| 模式 | 输出 |
|---|---|
| "MM/dd/yyyy" | "01/01/1970" |
| "MMM/dd/yyyy" | "Jan/01/1970" |
| "MMMM/d/yyyy" | "January/1/1970" |

我可以使用 `applyPattern` 方法为 `SimpleDateFormat` 设置模式，并使用 `format` 方法在日期上应用该模式。

```java
sdf.applyPattern("MM/dd/yyyy");
assertThat(sdf.format(date), is("01/01/1970"));
```

- `applyPattern` - 设置下次格式化使用的模式
- `format` - 使用定义的模式设置给定的日期

我还会在使用想要使用的模式实例化 `SimpleDateFormat`，例如下面所示的“年 月 日 24小时:分:秒.毫秒”：

```java
SimpleDateFormat sdf = new SimpleDateFormat("y M d HH:mm:ss.SSS")
```

你可以使用 `SimpleDateFormat` 为给定的日期字符串生成 `Date`，例如“2013年12月15日”、“下午11:39”以及“54秒123毫秒”：

```java
Date date = sdf.parse("2013 12 15 23:39:54.123");
```

用于日期格式的重要元素列如下，使用：

| 元素 | 描述 | 输出 |
|---|---|---|
| "y" | 年 | "2013" |
| "yy" | 年 | "13" |
| "yyy" | 年 | "2013" |
| "yyyy" | 年 | "2013" |
| "yyyyy" | 年 | "02013" |
| "M" | 月 | "12" |
| "MM" | 月 | "12" |
| "MMM" | 月 | "Dec" |
| "MMMM" | 月 | "December" |
| "d" | 月中的日 | "15" |
| "dd" | 月中的日 | "15" |
| "ddd" | 月中的日 | "015" |
| "h" | 上/下午的小时 | "11" |
| "hh" | 上/下午的小时 | "11" |
| "hhh" | 上/下午的小时 | "011" |
| "H" | 24小时制小时 | "23" |
| "HH" | 24小时制小时 | "023" |



| "m" | 分 | "39" |
| "mm" | 分 | "39" |
| "mmm" | 分 | "039" |
| "s" | 秒 | "54" |
| "ss" | 秒 | "54" |
| "sss" | 秒 | "054" |
| "S" | 毫秒 | "123" |
| "E" | 星期 | "Sun" |
| "EEEE" | 星期 | "Sunday" |
| "a" | 上/下午 | "PM" |

是一些不常用的日期模式，我并不经常使用：

| 元素 | 描述 | 输出 |
|---|---|---|
| "w" | 年中的周 | "50" |
| "www" | 年中的周 | "050" |
| "W" | 月中的周 | "2" |
| "WW" | 月中的周 | "02" |
| "WWW" | 月中的周 | "002" |
| "D" | 年中的日 | "349" |
| "F" | 月中的日 | "3" |
| "FF" | 月中的日 | "03" |
| "FFF" | 月中的日 | "003" |
| "u" | 周几数 | "7" |
| "uu" | 周几数 | "07" |
| "k" | 24小时制小时 (1-24) | "23" |
| "kkk" | 24小时制小时 (1-24) | "023" |
| "H" | 24小时制小时 (0-23) | "23" |
| "HH" | 24小时制小时 (0-23) | "023" |
| "z" | 一般时区 | "GMT" |
| "Z" | UTC 822 时区 | "+0000" |
| "X" | ISO8601 时区 | "Z" |

显示许多不同的组合（如 `"y"`, `"yy"`, `"yyyy"`）是为了演示某些模式会截断、填充或扩展 `Date` 的值。

`SimpleDateFormat` 还有其他方法，如果你想了解更多，建议阅读 `SimpleDateFormat` 的在线文档。通常我会根据所需的模式创建一个 `SimpleDateFormat` 并用该模式格式化 `Date`。这种方法非常有收获。

## Calendar

`Calendar` 是 `Date` 类的封装，允许我们按单个组件对其进行编辑，例如更改日期、日、月份或年份，而不是直接操作毫秒数。

使用 `Calendar` 类的静态方法 `getInstance` 实例化 `Calendar`。

```java
Calendar cal = Calendar.getInstance();
```

最初我将比较 `Calendar` 和 `Date` 以便你熟悉它，然后我们将详细探索它的方法和功能。

我们有很多你已经在 `Date` 中遇到过的方法，但这些方法作用于 `Calendar` 参数：

- `after` - 如果参数在 `Calendar` 之后，则返回 true
- `before` - 如果参数在 `Calendar` 之前，则返回 true
- `equals` - 如果参数代表与 `Calendar` 相同的日期时间，则返回 true
- `compareTo` - 如果参数与 `Calendar` 相等、之后或之前，返回 0、负数或正数

我们在 `Calendar` 上像 `Date` 一样有一个 `getTime` 方法，但 `Calendar` 的 `getTime` 方法返回一个 `Date`，因此以下行代码是等价的：

```java
System.out.println(cal.getTime());
System.out.println(System.currentTimeMillis());
```

`Calendar` 的 `toString` 方法不会打印格式良好的日期时间，而是显示 `Calendar` 对象的所有属性。

### 练习：将 toString 输出到控制台

编写一个 `@Test` 方法实例化日对象并将 `toString` 的输出写入控制台。

我可以使用 `setTime` 方法控制 `Calendar` 的日期：

```java
Calendar sameDate = Calendar.getInstance();
sameDate.setTime(cal.getTime());
assert(cal.equals(sameDate), is(true));
assert(cal.compareTo(sameDate), is(0));
```

由于我使用了来自另一个 `Calendar` 的 `Date`，因此可以使用 `equals` 和 `compareTo` 比较两个 `Calendar`，并期望它们具有相同的日期时间详情。

为了推进另一个 `Calendar` 的日期，我可以使用 `add` 方法。例如，像我之前对 `Date` 那样增加 7 天：

```java
Calendar oneWeekFromNow = Calendar.getInstance();
oneWeekFromNow.setTime(cal.getTime());
oneWeekFromNow.add(Calendar.DATE, 7);
```

我可以像之前看到的那样，使用 `after`、`compareTo` 比较 `Calendar` 对象：

```java
assert(oneWeekFromNow.after(cal), is(true));
assert(cal.before(oneWeekFromNow), is(true));
assert(cal.compareTo(oneWeekFromNow), is(-1));
assert(oneWeekFromNow.compareTo(cal), is(1));
```

## 设置 Calendar 值

### Calendar Constants

`Calendar` 提供了一些常量，以便以字面方式处理字段：

- `DATE`
- `YEAR`
- `MONTH`
- `DAY_OF_MONTH`

```java
cal.setDate(2013, 3, Calendar.THURSDAY);
```

上述代码将日期设置为了 2013 年 1 月 17 日。请随时在实际的日历上双击验证。

## 从 Calendar 获取详细信息

正如我们使用 `Calendar` 常量在 `Calendar` 中设置值一样，我们可以使用相同的常量从 `Calendar` 中获取信息。

假设有一个 `Calendar` 设置为 2013 年 12 月 15 日 23:49:54 秒：

```java
cal.set(2013, Calendar.DECEMBER, 15, 23, 39, 54);
```

我们可以使用这些常量来断言 `Calendar` 是否按照我们预期的方式创建：

```java
assertThat(cal.get(Calendar.MONTH), is(Calendar.DECEMBER));
```

### 练习：使用其他 Calendar 常量

编写一个 `@Test` 方法来初始化日历，并对你预期的以下常量值进行断言：

使用一个设置为 2013 年 12 月 15 日 23:49:54 秒的日历。

对你预期的值进行断言：

- `MONTH`（月份）
- `YEAR`（年份）
- `DAY_OF_MONTH`（日期）
- `HOUR_OF_DAY`（24小时制小时）
- `MINUTE`（分钟）
- `HOUR` - AM/PM 小时
- `AM_PM` - `Calendar.AM` 或 `Calendar.PM`

### 练习：尝试其他常量

尝试其他常量以确保你确实已经理解了它们。例如，为 2013 年 12 月 15 日确认以下内容：

- 它是星期日
- 它是该月的第 3 周（基于 0 索引，所以 0 是第一周）
- 它是该周的第一天
- 它是该年的第 50 周
- 它是该年的第 349 天

## 从 Calendar 获取更多信息

- `getTime` - 返回作为 `Date` 对象的 `Calendar`
- `getTimeInMillis` - 返回作为 `Date` 对象的 `Calendar`

`Calendar` 上还有其他方法可以获取更多关于日历的信息，但我建议你阅读在线文档或使用代码补全，以帮助你理解从此对象中可以获取的所有信息的范围。

在实践中，我倾向于根据需要设置日期、获取日期，然后让日期向前或向后移动。我们接下来将介绍这些。

## 使用加和减法在时间上滚动日期

`Calendar` 对象有两个主要机制可以相对地移动时间：

- `add` - 从字段中增加或减去一个值
- `roll` - 改变单个字段而不影响其他字段

我们可以使用 `add` 来增加或减少字段值。例如，我可以取一个 23:39 的 `Calendar` 并减少小时数：

```java
cal.add(Calendar.HOUR_OF_DAY, -1);
assertThat(cal.get(Calendar.HOUR_OF_DAY), is(22));
```

同样，我可以增加时间的分钟数：

```java
cal.add(Calendar.MINUTE, 10);
assertThat(cal.get(Calendar.MINUTE), is(49));
```

### 练习：增减其他字段

尝试 `add` 方法并以不同的方式更改字段，将日期从 2013 年 12 月 23 日移动到 2011 年 6 月 3 日。

使用 `roll` 方法，我可以更改单个字段而不影响任何更大的单位。例如，给定日期 2013 年 12 月 15 日，我可以将月份向前滚动 17 天跨越到 1 号，而仍然是 2013 年 12 月。如果我使用 `add` 这样做，日期将变成 2014 年 1 月 1 日，其他字段也会之进以保持日期有效。

```java
cal.roll(Calendar.DAY_OF_MONTH, 17);
assertThat(cal.get(Calendar.YEAR), is(2013));
assertThat(cal.get(Calendar.MONTH), is(Calendar.DECEMBER));
assertThat(cal.get(Calendar.DAY_OF_MONTH), is(1));
```

### 练习：确认 add 会移动年份

编写一个 `@Test` 方法演示在 2013 年 12 月 23 日增加 17 天，而不是滚动，会将日期移动到 2014 年 1 月 1 日。

## 总结

在生产环境中，在主应用程序中，我们经常使用 Joda-Time 库。我正试图将“库”的内容保持在范围之外，以便让你更容易上手，并帮助你建立对内置功能的知识和经验。

过度依赖外部库通常意味着在只需要对现有核心 Java 进行更快速封装时，向代码库中添加了另一个库。

本章涵盖了以下基本示例：

- 计时一组代码执行所需的时间
- 为文件创建唯一 ID 和名称
- 格式化日期
- 日期算术和处理

在为应用程序自动化生成输入数据时，我经常需要以不同的方式格式化日期。

在编写简单的性能自动化时，我会对代码运行进行计时。

我经常使用 `currentTimeMillis` 返回的值创建唯一文件名。

你看到了将数字文件转换为字母的示例。我有时通过这种方式使用 `currentTimeMillis` 为输入数据生成唯一的用户名。

我们在本章中涵盖了日期算术。一个非常有用的功能是能够处理“何时”。

```java
assertThat(properties.getProperty("missing"), is(nullValue()));
```

当我们调用 `getProperty` 时，可以指定一个默认值，这样如果属性键没有被设置，我们收到的就不是 `null`，而是默认值。

```java
assertThat(properties.getProperty("missing", "default"), is("default"));
```

## 属性的操作

通常情况下，如果我们已经设置了属性，我们将使用 `getProperty` 方法进行操作。

但有时你可能想通过一组键来操作 `Properties` 对象。我们使用 `stringPropertyNames` 方法来实现这一点：

如果我想遍历属性键并输出所有的值，那么我就遍历 `String` 类型属性键的集合（Set）：

```java
for (String key : properties.stringPropertyNames()) {
    System.out.println("Key: " + key + " : " + "Value: " + properties.getProperty(key));
}
```

上述代码将输出：

```text
Key: port Value: 80
Key: browser Value: firefox
```

```java
properties.list(System.out);
```

调用 `list` 方法将输出：

```text
- listing properties
port=80
browser=firefox
```

我还使用 `containsKey` 方法检查属性是否存在：

```java
assertThat(properties.containsKey("browser"), isTrue());
```

### 练习：创建并列出 Properties 对象

编写一个带有 `@Test` 注解的方法，该方法需要：

- 创建一个 `Properties` 对象
- 添加以下“键，值”对对：`name=bob`, `gender=male`, `password=paSSword`
- 断言 `Properties` 对象的大小为 3
- 通过遍历键将“键，值”输出到控制台
- 使用 `list` 方法输出属性
- 断言 `Properties` 对象包含该键
- 断言属性 `name` 的值为 `bob`
- 使用带有默认值的 `getProperty` 方法，并断言键 `"permission"` 的值为 `"Admin"`

## Java 的系统属性

### 读取系统属性

Java 的 `System` 对象拥有一组属性，这些属性在编写自动化代码时非常有用。

例如，`"user.dir"` 返回运行应用程序的工作目录。

```java
String workingDirectory = System.getProperty("user.dir");
```

我可以用它来访问自动化中需要的数据文件，例如，如果我在项目的 `/src/test/resources/` 下创建了一个名为 `property_files` 的目录，那么我可以通过加上当前工作目录来构建完整路径：

```java
String resourceFilePath = workingDirectory +
    "/src/test/resources/" +
    "property_files/" +
    "static_example.properties";
```

你可以通过 `Properties` 方法直接对 `System` 上的 `Properties` 对象进行操作。

例如，我想列出系统属性，可以使用以下代码：

```java
Properties sys = System.getProperties();
sys.list(System.out);
```

下面是上述命令的部分输出内容：

```text
- listing properties
java.runtime.name=Java(TM) Runtime Environment
sun.boot.library.path=C:\Program Files\Java\jdk1.7.0_10\jre...
java.vm.version=23.6-b04
java.vm.vendor=Oracle Corporation
java.vendor.url-http=http://java.oracle.com/
path.separator=\n
java.vm.name=Java HotSpot(TM) 64-Bit Server VM
```

### 执行：输出系统属性对象

> 编写一个带有 `@Test` 注解的方法，列出系统属性的内容。

阅读系统属性文档，以便了解你默认可用的属性范围。

- `docs.oracle.com/javase/tutorial/essential/environment/sysprop.html`

我最常用的系统属性有：

- `user.dir` - 代码当前工作目录
- `user.home` - 用户主目录
- `line.separator` - 换行符字符串
- `file.separator` - 文件路径分隔符
- `java.io.tmpdir` - 临时目录

### 设置系统属性

你可以通过 `Properties` 方法直接处理 `System` 上的 `Properties` 对象。

例如，我想列出系统属性，可以使用以下代码：

```java
Properties sys = System.getProperties();
sys.list(System.out);
```

## 属性的操作

通常情况下，如果我们已经设置了属性，我们将使用 `getProperty` 方法进行操作。

但有时你可能想通过一组键来操作 `Properties` 对象。我们使用 `stringPropertyNames` 方法来实现这一点：

如果我想遍历属性键并输出所有的值，那么我就遍历 `String` 类型属性键的集合（Set）：

```java
for (String key : properties.stringPropertyNames()) {
    System.out.println("Key: " + key + " : " + "Value: " + properties.getProperty(key));
}
```

上述代码将输出：

```text
Key: port Value: 80
Key: browser Value: firefox
```

```java
properties.list(System.out);
```

调用 `list` 方法将输出：

```text
- listing properties
port=80
browser=firefox
```

我还使用 `containsKey` 方法检查属性是否存在：



```java
assertThat(properties.containsKey("browser"), isTrue());
```

## 练习：创建并列出 Properties 对象

编写一个带有 `@Test` 注解的方法，该方法需要：

- 创建一个 `Properties` 对象
- 添加以下“键，值”对：`name=bob`, `gender=male`, `password=paSSword`
- 断言 `Properties` 对象的大小为 3
- 通过遍历键将“键，值”输出到控制台
- 使用 `list` 方法输出属性
- 断言 `Properties` 对象包含该键
- 断言属性 `name` 的值为 `bob`
- 使用带有默认值的 `getProperty` 方法，并断言键 `"permission"` 的值为 `"Admin"`

## Java 的系统属性

### 读取系统属性

Java 的 `System` 对象拥有一组属性，这些属性在编写自动化代码时非常有用。

例如，`"user.dir"` 返回运行应用程序的工作目录。

```java
String workingDirectory = System.getProperty("user.dir");
```

我可以用它来访问自动化中需要的数据文件，例如，如果我在项目的 `/src/test/resources/` 下创建了一个名为 `property_files` 的目录，那么我可以通过加上当前工作目录来构建完整路径：

```java
String resourceFilePath = workingDirectory +
    "/src/test/resources/" +
    "property_files/" +
    "static_example.properties";
```

你可以通过 `Properties` 方法直接对 `System` 上的 `Properties` 对象进行操作。

例如，我想列出系统属性，可以使用以下代码：

```java
Properties sys = System.getProperties();
sys.list(System.out);
```

下面是上述命令的部分输出内容：

- listing properties
- java.runtime.name=Java(TM) Runtime Environment
- sun.boot.library.path=C:\Program Files\Java\jdk1.7.0_10\jre...
- java.vm.version=23.6-b04
- java.vm.vendor=Oracle Corporation
- java.vendor.url-http=http://java.oracle.com/
- path.separator=\n
- java.vm.name=Java HotSpot(TM) 64-Bit Server VM

## 执行：输出系统属性对象

> 编写一个带有 `@Test` 注解的方法，列出系统属性的内容。

阅读系统属性文档，以便了解你默认可用的属性范围。

- docs.oracle.com/javase/tutorial/essential/environment/sysprop.html

我最常用的系统属性有：

- `user.dir` - 代码当前工作目录
- `user.home` - 用户主目录
- `line.separator` - 换行符字符串
- `file.separator` - 文件路径分隔符
- `java.io.tmpdir` - 临时目录

## 设置系统属性

你可以通过 `Properties` 方法直接对 `System` 上的 `Properties` 对象进行操作。

例如，我想列出系统属性，可以使用以下代码：

```java
Properties sys = System.getProperties();
sys.list(System.out);
```

# 第十九章 - 文件

## 章节总结

在本章中，你将学习如何使用 Java 基础文件处理类：

- **File**: 文件的通用包装器
    - `createTempFile` - 创建临时文件
    - `createNewFile` - 创建文件
    - `delete` - 现在删除文件
    - `deleteOnExit` - 在应用程序关闭时删除文件
    - `getName` - 返回文件名或目录名
    - `getPath` - 返回父目录的路径
    - `getAbsolutePath` - 返回唯一的完整文件名和路径
    - `getCanonicalPath` - 返回 `File` 的唯一完整表示形式
    - `mkdir` - 创建目录以及路径中所有必要的目录
    - `isDirectory`, `isFile` - 确定物理文件的类型
    - `separator`, `pathSeparator` - 用于文件（例如 `'\'`）和路径（例如 `';'`）
    - `listRoots` - 返回文件系统中的根目录数组
    - `length` - 文件的长度（以字节计）
    - `getFreeSpace`, `getTotalSpace`, `usableSpace` - 磁盘空间
    - `rename` - 重命名文件
- **目录方法**
    - `list` - 以 `String` 形式的文件列表
    - `listFiles` - 每个文件和目录的 `File` 对象列表
- **属性方法**
    - `canWrite`, `write`, `canExecute`, `lastModified`
    - `setExecutable`, `setReadable`, `setWritable`
    - `setReadOnly`, `setLastModified`
- **静态方法复制或移动文件或目录的类**
    - `PrintWriter` - 拥有让写入更方便的方法，例如 `print`, `println`
    - `FileWriter` - 写入基于字符的文件
    - `BufferedWriter`, `BufferedReader` - 为了效率对输出和输入进行缓冲
    - `FileReader` - 从输入流读取

我打算尽量让我的文件代码尽可能简单，因为我的用例通常很简单：

- 读取他人编写的文件 - 有时检查数据的有效性
- 读取简单的 CSV 或制表符分隔的文件 - 通常作为数据驱动检查的输入
- 复制文件 - 保留自动化过程中使用的数据文件夹，或用于初始化数据
- 创建目录 - 让我的工作流更简单
- 移动文件 - 截图图像、日志文件
- 删除文件
- 编写报告 - 简单的日志文件或 HTML 报告输出

在本章中，我将涵盖实现上述用例的基础类和方法。

## 读写文件的示例

我将快速向你展示写入文件并读取同一个文件的代码。

如果你想立即尝试，请尽管尝试。本章其余部分将详细介绍使用的各种方法和类，并进行更深入的解释。

## 写入临时文件

```java
private File writeTestDataFile() throws IOException {
    File outputFile = File.createTempFile("Reading", null);
    BufferedWriter print = new BufferedWriter(
        new FileWriter(outputFile));

    for (int lineNumber = 1; lineNumber < 6; lineNumber++){
        print.println("line " + lineNumber);
    }

    print.close();
    return outputFile;
}
```

上述代码在系统的 'Temp' 目录下创建一个临时文件。

例如在 `%TEMP%`（Windows 上）中的 `Reading253645339676632859.temp`。

它使用了 3 个类来包装文件：`FileWriter`, `BufferedWriter` 和 `PrintWriter`。

然后向文件打印 5 行文本，关闭文件，并将 `File` 对象返回给调用方法。

## 读取临时文件

```java
@Test
public void outputToFileSystemOutBufferedReader() throws IOException {
    File inputFile = writeTestDataFile();
    BufferedReader reader = new BufferedReader(new FileReader(inputFile));

    try{
        String line;
        while ((line = reader.readLine())!=null){
            System.out.println(line);
        }
    } finally{
        reader.close();
    }
}
```

上述代码调用 `writeTestDataFile` 方法创建一个临时文件。

它返回 `File`，并用 `FileReader` 和 `BufferedWriter` 对其封装，然后读取每一行并打印出来。

代码在读取时使用 `try/finally` 块封装读取代码，以确保在发生异常时文件能够正确关闭。

## 笔记

这里似乎涉及到很多类。但正如你稍后看到的，它们相互构建，使得读写文件对你变得简单。

如果你从复制上面的代码并进行微调开始，你可能满足我在本章开头提到的至少 3 个用例。

通过阅读类的上下文相关代码补全，你可能推断出其他用例。

本章其余部分将详细介绍涉及的每个类。

## File

`File` 类提供了表示“文件”或“目录”的主类，以及用于创建目录和其他本地文件操作的方法。

`File` 类还提供了一组可以帮助我们的静态方法。

`File` 位于 `java.io` 包中。

## 静态方法

- `createTempFile`:
    - 在系统临时目录创建临时文件（Windows 上为 `%TEMP%`）
- `separator`:
    - 文件的值分隔符（例如 `'\'`）
- `pathSeparator`:
    - 路径中的系统分隔符（例如 `';'`）
- `listRoots`:
    - 文件系统的根路径数组

我确实使用了 `createTempFile` 和 `separator`，但将涵盖所有上述方法。

```java
File outputFile = File.createTempFile("forReading", null);
```

该方法在系统临时目录创建一个空文件。

在上面的示例中，我使用了 `File` path。强制性参数是：

- `prefix`:
    - 文件名的前缀
- `suffix`:
    - 文件名的后缀
- `directory`:
    - 文件所在的目录

上述代码在系统的 'Temp' 目录下创建一个临时文件。

```java
assertThat(aTempFile.exists(), is(false));

aTempFile.createNewFile();
assertThat(aTempFile.exists(), is(true));

aTempFile.delete();
assertThat(aTempFile.exists(), is(false));
```

构造函数的另一种形式允许我们将文件路径和文件作为独立的参数传入。

```java
File aTempFile = new File("d", "tempJavaForTesters.txt");
```

请注意，当我在 `File` 构造函数中使用两个参数时，我不需要担心末尾的目录分隔符。

文件操作可能会抛出各种异常，但 `java.io.IOException` 是可能抛出的异常的通用捕获。

在这个短小节中，我们涵盖了：

- 两个 `File` 构造函数
- `exists` 方法用于检查文件或目录是否存在
- `delete` 用于删除文件或目录
- `createNewFile` 创建空文件

## 练习：使用自定义代码创建临时文件

使用普通的 `File` 对象和 `createNewFile` 方法模拟 `createTempFile` 方法。

提示：可以通过系统属性 `"java.io.tmpdir"` 访问系统临时目录。

使用 `System.currentTimeMillis` 创建一个“唯一的”数字作为文件名的一部分。

## 其他基础方法

我们起初需要学习的 `File` 基础方法有：

- `deleteOnExit` - 在应用程序关闭时删除文件
- `getName` - 文件名或目录名
- `getParent` - 父级目录的路径
- `getAbsolutePath` - 包含根目录、文件夹层级和用于创建 `File` 的文件名的完整文件名
- `getCanonicalPath` - `File` 的唯一全路径表示形式
- `mkdir` - 创建单个目录
- `mkdirs` - 创建目录以及该路径中所有必要的目录

### deleteOnExit

一旦你有一个 `File` 对象，就可以将其添加到“退出时删除”队列。

```java
File aTempFile = File.createTempFile("prefix", "suffix");
aTempFile.deleteOnExit();
```

![](img/3571bcaadac59e6bb801bc317a52cb1e_200_0.png)

当应用程序结束时，当所有的 `@Test` 方法运行完成后，“退出时删除”队列中的所有文件都将被删除。

这是一个与 `createTempFile` 方法结合使用的有用方法，因为它意味着你的临时文件在 `@Test` 方法运行后会被删除，而不是依赖于你操作系统的临时清理程序。

### getName, getParent, getAbsolutePath, getCanonicalPath

如果我创建一个临时文件：

```java
aTempFile = File.createTempFile("prefix", "suffix");
```

我不确切知道文件的具体名称是什么。

在处理 `File` 对象 `aTempFile` 时，我不需要知道实际名称，因为我是直接操作 `File` 对象的。

如果我想处理名称或路径，可以使用以下方法：

- `getName`
- `getParent`
- `getAbsolutePath` 以及
- `getCanonicalPath`

`getName` 返回文件名，不包含路径。因此，对于上面的示例，我将创建一个前缀为 `12345678901234567890` 的文件名。

```java
assertThat(aTempFile.getName().startsWith("prefix"), is(true));
assertThat(aTempFile.getName().endsWith("suffix"), is(true));
```

`getParent` 返回父目录的路径结构。

`getAbsolutePath` 和 `getCanonicalPath` 返回完整路径，并包含 `File` 的文件名：

“绝对”路径会在名称中显示相对文件操作符，例如 `../`，但规范路径（canonical）则不会。

规范路径是唯一的路径，因此相对元素会被转换为绝对路径。

- `C:/1/2/3/4/../../..`
- `C:/1/2/../1`

将被表示为以下规范路径：

- `C:/1`

## 练习：编写一个 @Test 方法检查规范路径转换

编写一个 `@Test` 方法，检查以下绝对路径的断言：

- `C:/1/2/3/4/../../..`
- `C:/1/2/../1`

如果我创建一个临时文件：

```java
aTempFile = File.createTempFile("prefix", "suffix");
```

我不确切知道该文件的具体名称是什么。

在处理 `File` 对象 `aTempFile` 时，我不需要知道实际名称，因为我是直接操作 `File` 对象的。

如果我想处理名称或路径，可以使用以下方法：

- `getName`
- `getParent`
- `getAbsolutePath` 以及
- `getCanonicalPath`

`getName` 返回文件名，不包含路径。因此，对于上面的示例，我将创建一个前缀为 `12345678901234567890` 的文件名。

```java
assertThat(aTempFile.getName().startsWith("prefix"), is(true));
assertThat(aTempFile.getName().endsWith("suffix"), is(true));
```

`getParent` 返回父目录的路径结构。

`getAbsolutePath` 和 `getCanonicalPath` 返回完整路径，并包含 `File` 的文件名：

“绝对”路径会在名称中显示相对文件操作符，例如 `../`，但规范路径（canonical）则不会。

规范路径是唯一的路径，因此相对元素会被转换为绝对路径。

- `C:/1/2/3/4/../../..`
- `C:/1/2/../1`

将被表示为以下规范路径：

- `C:/1`

## 练习：编写一个 @Test 方法检查规范路径转换

编写一个 `@Test` 方法，检查以下绝对路径的断言：

- `C:/1/2/3/4/../../..`
- `C:/1/2/../1`

如果我创建一个临时文件：

```java
aTempFile = File.createTempFile("prefix", "suffix");
```

我不确切知道该文件的具体名称是什么。

在处理 `File` 对象 `aTempFile` 时，我不需要知道实际名称，因为我是直接操作 `File` 对象的。

如果我想处理名称或路径，可以使用以下方法：

- `getName`
- `getParent`



- `getAbsolutePath` 以及
- `getCanonicalPath`

`getName` 返回文件名，不包含路径。因此，对于上面的示例，我将创建一个前缀为 `12345678901234567890` 的文件名。

```java
assertThat(aTempFile.getName().startsWith("prefix"), is(true));
assertThat(aTempFile.getName().endsWith("suffix"), is(true));
```

`getParent` 返回父目录的路径结构。

`getAbsolutePath` 和 `getCanonicalPath` 返回完整路径，并包含 `File` 的文件名：

“绝对”路径会在名称中显示相对文件操作符，例如 `../`，但规范路径（canonical）则不会。

规范路径是唯一的路径，因此相对元素会被转换为绝对路径。

- `C:/1/2/3/4/../../..`
- `C:/1/2/../1`

将被表示为以下规范路径：

- `C:/1`

## 练习：编写一个 @Test 方法检查规范路径转换

编写一个 `@Test` 方法，检查以下绝对路径的断言：

- `C:/1/2/3/4/../../..`
- `C:/1/2/../1`

如果我创建一个临时文件：

```java
aTempFile = File.createTempFile("prefix", "suffix");
```

我不确切知道该文件的具体名称是什么。

在处理 `File` 对象 `aTempFile` 时，我不需要知道实际名称，因为我是直接操作 `File` 对象的。

如果我想处理名称或路径，可以使用以下方法：

- `getName`
- `getParent`
- `getAbsolutePath` 以及
- `getCanonicalPath`

`getName` 返回文件名，不包含路径。因此，对于上面的示例，我将创建一个前缀为 `12345678901234567890` 的文件名。

```java
assertThat(aTempFile.getName().startsWith("prefix"), is(true));
assertThat(aTempFile.getName().endsWith("suffix"), is(true));
```

`getParent` 返回父目录的路径结构。

`getAbsolutePath` 和 `getCanonicalPath` 返回完整路径，并包含 `File` 的文件名：

“绝对”路径会在名称中显示相对文件操作符，例如 `../`，但规范路径（canonical）则不会。

规范路径是唯一的路径，因此相对元素会被转换为绝对路径。

- `C:/1/2/3/4/../../..`
- `C:/1/2/../1`

将被表示为以下规范路径：

- `C:/1`

## mkdir

- `mkdir` - 创建单个目录
- `mkdirs` - 创建目录以及该路径中所有必要的目录

### 退出时删除

一旦你有一个 `File` 对象，就可以将其添加到“退出时删除”队列。

```java
File aTempFile = File.createTempFile("prefix", "suffix");
aTempFile.deleteOnExit();
```

当应用程序结束时，当所有的 `@Test` 方法运行完成后，“退出时删除”队列中的所有文件都将被删除。

这是一个与 `createTempFile` 方法结合使用的有用方法，因为它意味着你的临时文件在 `@Test` 方法运行后会被删除，而不是依赖于你操作系统的临时清理程序。

### getName, getParent, getAbsolutePath, getCanonicalPath

如果我创建一个临时文件：

```java
aTempFile = File.createTempFile("prefix", "suffix");
```

我不确切知道该文件的具体名称是什么。

在处理 `File` 对象 `aTempFile` 时，我不需要知道实际名称，因为我是直接操作 `File` 对象的。

如果我想处理名称或路径，可以使用以下方法：

- `getName`
- `getParent`
- `getAbsolutePath` 以及
- `getCanonicalPath`

`getName` 返回文件名，不包含路径。因此，对于上面的示例，我将创建一个前缀为 `12345678901234567890` 的文件名。

```java
assertThat(aTempFile.getName().startsWith("prefix"), is(true));
assertThat(aTempFile.getName().endsWith("suffix"), is(true));
```

`getParent` 返回父目录的路径结构。

`getAbsolutePath` 和 `getCanonicalPath` 返回完整路径，并包含 `File` 的文件名：

“绝对”路径会在名称中显示相对文件操作符，例如 `../`，但规范路径（canonical）则不会。

规范路径是唯一的路径，因此相对元素会被转换为绝对路径。

- `C:/1/2/3/4/../../..`
- `C:/1/2/../1`

将被表示为以下规范路径：

- `C:/1`

```java
assertThat(aTempFile.exists(), is(false));

aTempFile.createNewFile();
assertThat(aTempFile.exists(), is(true));

aTempFile.delete();
assertThat(aTempFile.exists(), is(false));
}
```

构造函数的另一种形式允许我们将文件路径和文件作为独立的参数传入。

```java
File aTempFile = new File("d", "tempJavaForTesters.txt");
```

请注意，当我在 `File` 构造函数中使用两个参数时，我不需要担心末尾的目录分隔符。

文件操作可能会抛出各种异常，但 `java.io.IOException` 是可能抛出的异常的通用捕获。

在这个短小节中，我们涵盖了：

- 两个 `File` 构造函数
- `exists` 方法用于检查文件或目录是否存在
- `delete` 用于删除文件或目录
- `createNewFile` 创建空文件

## 练习：使用自定义代码创建临时文件

使用普通的 `File` 对象和 `createNewFile` 方法模拟 `createTempFile` 方法。

提示：可以通过系统属性 `"java.io.tmpdir"` 访问系统临时目录。

使用 `System.currentTimeMillis` 创建一个“唯一的”数字作为文件名的一部分。

## 其他基础方法

我们起初需要学习的 `File` 基础方法有：

- `deleteOnExit` - 在应用程序关闭时删除文件
- `getName` - 文件名或目录名
- `getParent` - 父级目录的路径
- `getAbsolutePath` - 包含根目录、文件夹层级和用于创建 `File` 的文件名的完整文件名
- `getCanonicalPath` - `File` 的唯一全路径表示形式
- `mkdir` - 创建单个目录
- `mkdirs` - 创建目录以及该路径中所有必要的目录

### deleteOnExit

一旦你有一个 `File` 对象，就可以将其添加到“退出时删除”队列。

```java
File aTempFile = File.createTempFile("prefix", "suffix");
aTempFile.deleteOnExit();
```

当应用程序结束时。当所有的 `@Test` 方法运行完成后，“退出时删除”队列中的所有文件都将被删除。

这是一个与 `createTempFile` 方法结合使用的有用方法，因为它意味着你的临时文件在 `@Test` 方法运行后会被删除，而不是依赖于你操作系统的临时清理程序。

### getName, getParent, getAbsolutePath, getCanonicalPath

如果我创建一个临时文件：

```java
aTempFile = File.createTempFile("prefix", "suffix");
```

我不确切知道该文件的具体名称是什么。

在处理 `File` 对象 `aTempFile` 时，我不需要知道实际名称，因为我是直接操作 `File` 对象的。

如果我想处理名称或路径，可以使用以下方法：

- `getName`
- `getParent`
- `getAbsolutePath` 以及
- `getCanonicalPath`

`getName` 返回文件名，不包含路径。因此，对于上面的示例，我将创建一个前缀为 `12345678901234567890` 的文件名。

```java
assertThat(aTempFile.getName().startsWith("prefix"), is(true));
assertThat(aTempFile.getName().endsWith("suffix"), is(true));
```

`getParent` 返回父目录的路径结构。

`getAbsolutePath` 和 `getCanonicalPath` 返回完整路径，并包含 `File` 的文件名：

“绝对”路径会在名称中显示相对文件操作符，例如 `../`，但规范路径（canonical）则不会。

规范路径是唯一的路径，因此相对元素会被转换为绝对路径。

- `C:/1/2/3/4/../../..`
- `C:/1/2/../1`

将被表示为以下规范路径：

- `C:/1`

## 练习：编写一个 @Test 方法检查规范路径转换

编写一个 `@Test` 方法，检查以下绝对路径的断言：

- `C:/1/2/3/4/../../..`
- `C:/1/2/../1`

- `length` - 文件的长度（以字节为单位）
- `getFreeSpace` - 空闲空间的字节数
- `getTotalSpace` - 总空间的字节数
- `getUsableSpace` - 可用空间的字节数

## 练习：创建文件并计算长度

创建一个文件并计算预期的文件大小。提示：使用 `System.lineSeparator()` 获取行结束符。

## 目录方法

对于代表目录的特定 `File` 对象，你可以获取该目录中包含的文件名列表。

- `list` 将返回文件名的列表
- `listFiles` 将返回 `File` 对象的列表

使用 `list` 方法：

```java
@Test
public void listTempDirectory() {
    File tempdir = new File(System.getProperty("java.io.tmpdir"));
    String[] fileList = tempdir.list();
    for (String inFile : fileList){
        System.out.println(inFile);
    }
}
```

## 练习：使用 listFiles 显示临时目录

在 `File` 上使用 `listFiles` 方法输出临时目录中每个文件的名称。对于每个文件，如果是目录则也写出 `"DIR:"`，如果是文件则写出 `"FIL:"`。

## Files

- `copy` - 创建文件或目录的副本
- `move` - 移动文件或目录，创建一个新的并删除旧的

## 属性

你可以使用以下方法检查和修改文件：



- `canRead` - 如果文件可读则返回 `true`
- `canWrite` - 如果文件可写则返回 `true`
- `canExecute` - 如果文件可执行则返回 `true`
- `lastModified` - 以 `long` 类型返回最后的修改日期
- `setExecutable`
- `setReadable`
- `setWritable`
- `setLastModified`

## 练习：输出文件的属性

扩展你为 `listFiles` 编写的 `@test` 方法，也输出读、写、执行属性以及最后修改日期。

## Files

`Files` 是 `java.nio` 包的一部分。nio 是 Java 4 引入的“新 IO”类；所以其实并没有那么“新”，但它们为其他库添加了一些有用的功能。nio 包提供了很多方法，但我们将主要查看 `Files` 类和 `copy` 方法。

## 重命名 vs 移动

`File` 有一个 `renameTo` 方法，但当我想要重命名文件时，倾向于使用 `Files` 上的 `move` 方法。`move` 和 `copy` 可以用于 `Path` 对象而不是 `File`。幸运的是，`File` 对象有 `toPath` 方法，我们可以用它来返回一个 `Path` 对象。

```
Files.copy(copy.toPath(), toPath());
```

`move` 和 `copy` 都接受一个可选列表，用于指定 `java.nio.file.StandardCopyOption` 中包含的选项。因此，你需要在类中添加额外的导入：

- `REPLACE_EXISTING` - 如果目标已存在，则允许操作完成
- `COPY_ATTRIBUTES` - 在复制过程中保留文件属性
- `ATOMIC_MOVE` - 任何操作系统都会等待移动完成

下面的 `move` 使用了复制选项：

```java
Files.move(move.getPath(), toPath(), REPLACE_EXISTING, ATOMIC_MOVE);
```

## 练习：复制并移动文件

- 向临时目录写入一个文件并复制到后缀为 `".copy"` 的新文件中。
- 向临时目录写入一个文件并将其移动到后缀为 `".moved"` 的新文件中。

## 总结

我们还没有涵盖所有处理文件的可用方法。我建议你使用代码补全和官方帮助文档来探索 Java 输入包中可用的类。本章涵盖的方法和类应该能为你解决自动化支持测试所需的初始问题提供足够的信息。当然，你应该具备足够的信息来读写文本文件：无论是用于输入数据还是临时报告。请阅读下方链接的页面。Java 核心库中有一系列丰富的库用于处理文件。此外，在本章中我们专注于处理文本文件，我怀疑自动化过程中大多数文件都需要解析和写入，而这些将是文本文件。

## 参考与推荐阅读

- IO 文档
  - `docs.oracle.com/javase/7/tutorial/io`
- File 文档
  - `docs.oracle.com/javase/7/File`
- Files 文档
  - `docs.oracle.com/javase/7/api/nio/Files`
- NIO vs IO
  - `blogs.oracle.com/nio_io`
- BufferedWriter 文档
  - `docs.oracle.com/javase/7/api/io/BufferedWriter`
- PrintWriter 文档
  - `docs.oracle.com/javase/7/api/io/PrintWriter`
- 读写文件
  - `www.javpractices.com/TopicAction?Id=42`
- 读取文件的不同方法
  - `stackoverflow.com/questions/4716503/best-way-to-read-a-text-file`
- 复制
  - `docs.oracle.com/javase/7/tutorial/io/copy`
- 移动
  - `docs.oracle.com/javase/7/tutorial/io/move`

# 第二十章 - 数与 BigDecimal

## 章节总结

在本章中，你将学习如何使用额外的数字类：

- `BigDecimal` - 一个提供无舍入精确操作的类，对于金融应用很重要
    - `subtract` - 从 `BigDecimal` 中减去一个值
    - `add` - 给 `BigDecimal` 加一个值
    - `multiply` - 将 `BigDecimal` 乘以一个值
    - `divide` - 将 `BigDecimal` 除以一个值
    - `valueOf` - 静态方法，根据提供的 `double` 或 `long` 返回 `BigDecimal`
    - `BigDecimal` 不支持 `<=、<` 等运算符，请使用 `compareTo` 方法
- `Math` - 一个包含处理 `float` 和 `double` 相关方法的类
    - `max` - 比较两个值并返回较大的
    - `min` - 比较两个值并返回较小的
    - `abs` - 返回绝对值
    - `random` - 返回一个大于 `0.0` 且小于 `1.0` 的随机数
    - 三角函数：`sin, cos, tan, asin, acos, toDegrees, toRadians`

我们还没有涵盖所有处理文件的可用方法。我建议你使用代码补全和官方帮助文档来探索 Java 输入包中可用的类。本章涵盖的方法和类应该能为你解决自动化支持测试所需的初始问题提供足够的信息。当然，你应该具备足够的信息来读写文本文件：无论是用于输入数据还是临时报告。请阅读下方链接的页面。Java 核心库中有一系列丰富的库用于处理文件。此外，在本章中我们专注于处理文本文件，我怀疑自动化过程中大多数文件都需要解析和写入，而这些将是文本文件。

## 练习：说服你自己使用 BigDecimal 或 int

创建一个 `@Test` 方法来计算以下情况的结果。

（1 英镑等于 100 便便士，或者 1 美元等于 100 美分）在这个示例中，我使用 `BigDecimal` 将其转换为你需要的任何货币，只需注意在转换时 1 英镑有 100 便便士。

## BigDecimal 构造函数

你可以通过以下类型构造 `BigDecimal`：

- `int`
- `long`
- `String`
- `double`
- `BigInteger` - 大于 64 位

```java
BigDecimal fromInt = new BigDecimal(5);
BigDecimal fromLong = new BigDecimal(5L);
BigDecimal fromString = new BigDecimal("5");
BigDecimal fromDouble = new BigDecimal(5.0);
BigDecimal fromInteger = BigDecimal.valueOf(5L);
```

## 静态方法

`BigDecimal` 提供了一些工厂方法来创建 `BigDecimal` 对象：

- `ONE`
- `TEN`
- `valueOf` - 将 `double` 或 `long` 转换为 `BigDecimal`

```
BigDecimal bd0 = BigDecimal.ZERO;
BigDecimal bd1 = BigDecimal.ONE;
BigDecimal bd10 = BigDecimal.TEN;
BigDecimal bdVal = BigDecimal.valueOf(5.0);
```

## 基础算术方法

`BigDecimal` 的基础算术方法有：

- `add`
- `subtract`
- `multiply`
- `divide`

这些每个方法都接受一个 `BigDecimal` 参数，并返回一个代表运算符 `+`, `*`, 或 `/` 结果的新 `BigDecimal`。

创建一个 `@Test` 方法，使用 `BigDecimal` 方法实现以下计算：

- `a = 0`
- `((a + 10) * 2) = 5`

## 练习：使用 BigDecimal 进行基础算术运算

## 比较运算符

你不能在 `BigDecimal` 上使用普通的比较运算符，即 `>, <, !=, >=, <=`。你可以使用 `equals` 来比较 `BigDecimal` 对象。

```java
assertThat(BigDecimal.ONE.equals(new BigDecimal(1.0)));
```

你也可以使用 `compareTo` 方法：

- 如果 `BigDecimal` 小于值，返回 `-1`
- 如果 `BigDecimal` 等于值，返回 `0`
- 如果 `BigDecimal` 大于值，返回 `1`

官方文档建议使用以下用法：

```
BigDecimal.TEN.compareTo(BigDecimal.ONE) > 0
```

这等同于：

```
BigDecimal.TEN > BigDecimal.ONE
```

## 练习：比较 TEN 和 ONE

编写一个 `@Test` 方法来比较 `TEN` 和 `ONE`。模拟每个比较运算符：

```
>, <, !=, >=, <=
```

遵循上述建议模式，例如 `> 0`。

## 使用 BigDecimal

如果你开始使用 `BigDecimal`，请阅读官方文档或在你的 IDE 中使用代码补全来查看提供的额外方法。在本章节中，我们涵盖了 `BigDecimal` 方法的一个子集，帮助你入门，并帮助你理解 `BigDecimal` 与基本类型 `double` 和 `float` 之间的区别。

`BigDecimal` 支持不同的舍入方法，你可以结合算术操作使用。你还可以提供一个“精度”（scale）以便在不同的十幂上进行操作。Java 在 `java.math` 包中还提供了一个 `BigInteger` 对象，它可以处理大于 64 位的数据。与 `int` 或 `long` 相关的普通运算符和函数可以通过方法访问。

你还可以使用 `floatValue`、`doubleValue`、`intValue`、`longValue` 等从 `BigDecimal` 转换。当你希望在系列计算后使用 `Math` 类中的某些方法时这非常有用。

## Math

`java.lang.Math` 类提供了一系列用于 `float` 或 `double` 的数学方法。官方文档列出了所有可用方法集，因此你可以轻松地在线或在 IDE 中找到它们。该类中的方法都是静态的，因此无需实例化 `Math` 对象即可使用，且不需要导入 `Math` 包。

例如，找到两个值中的最大值：

```java
assertThat(Math.max(23.0, 42.0), is(42.0));
```

我在下面描述了我过去发现非常有用的小部分方法。以下方法作用于 `int`、`long`：

- `max` - 返回两个值中的最大值
- `min` - 返回两个值中的最小值
- `abs` - 绝对值
- `random` - 生成随机数

你还拥有三角函数：`sin, cos, tan, asin, acos, atan, toDegrees`（转角度），`toRadians`（转弧度）。

我并不打算涵盖所有方法，只是想让你了解 `Math` 类现有的功能。现在，当你开始处理数学运算时，可以检查 `Math` 类以查看哪些方法能满足你的需求。

## 总结

本章节介绍了两个重要的类：

- `BigDecimal`
- `Math`

当处理货币值或需要高精度时使用 `BigDecimal`。

当你需要超出简单的运算符 `-*/` 时使用 `Math`。记住在处理大于 64 位的数据时使用 `BigInteger`。

## 参考与推荐阅读

- `BigDecimal`
- `Math`

# 第二十章：回顾 Collections

我们在早期的章节中描述了 set。在本章节中，我们将基于 Set 并考虑 SortedSet。

## Collection 接口

官方文档列出了以下 接口：

- `List`
- `Set`
- `Queue`
- `Deque`
- `Map`

下表提供了接口的关键方法总结：

| Collection | Set | SortedSet | Map | SortedMap |
| :--- | :--- | :--- | :--- | :--- |
| `add(e)` | All in Collection | `first` | `put(k, v)` | `firstKey` |
| `remove(e)` | | `last` | `remove(k)` | `firstKey` |
| `removeAll(c)` | | `headSet(e)` | `entrySet` | `headMap` |
| `retainAll(c)` | | `tailSet(e)` | `get(k)` | `tailMap` |
| `clear` | | `subSet(i1,i2)` | `clear` | `subMap(k,k)` |
| `contains(e)` | | | `containsKey(k)` | |
| `containsAll(c)` | | | `containsValue(v)` | |
| `size` | | `comparator` | `size` | `comparator` |
| `isEmpty` | | | | |
| `toArray` | All in Collection | `values` | All in Map | |
| `toArray(a)` | | `keySet` | | |
| `addAll(c)` | | `putAll(m)` | | |

其中：`e == element, c == collection, a == array, i == index, k == key, v == value, m == map`

## Collection 实现

以下是核心 Collection 实现：

- `TreeSet`
- `TreeMap`

## SortedSet

`SortedSet` 同 `Set` 一样在尝试添加重复项时会去除。`SortedSet` 还：

- 根据 `Comparator` 或元素的 `compare` 方法保证元素的顺序

排序依赖集合中的元素实现 `comparable` 接口，该接口强制实现 `compareTo` 方法。或者你可以在实例化时为 `SortedSet` 提供一个 `Comparator`，`Comparator` 知道如何比较对象。

在示例中，我将主要使用 `String`，但也会对 `Comparator` 进行简要概述。

- `first` - 返回第一个项
- `last` - 返回最后一个
- `headSet(e)` - 返回元素 `e` 之前的 `SortedSet`
- `tailSet(e)` - 返回包含元素 `e` 之后的 `SortedSet`
- `subSet(e1, e2)` - 从元素 `e1`（包含）到 `e2`（不包含）的 `SortedSet`
- `comparator` - 返回用于排序顺序比较的 `Comparator` 对象

使用 `SortedSet`，你也可以访问 `Collection` 接口中的所有方法。

对于 `SortedSet`，我使用 `java.util` 中的 `TreeSet` 作为我的默认实现。

以下示例展示了：

- 即使我按乱序添加了元素，`SortedSet` 仍然保持了元素的顺序
- `SortedSet` 不会添加重复的元素 `"a"`

```java
@Test
public void sortedSetCanMaintainSortOrder() {
    SortedSet<String> alphabet = new TreeSet<>();

    alphabet.add("c");
    alphabet.add("d");
    alphabet.add("a");
    alphabet.add("b");
    alphabet.add("a");

    assertEquals(4, alphabet.size());

    String[] alphas = new String[alphabet.size()];
    alphabet.toArray(alphas);

    assertEquals("a", alphas[0]);
    assertEquals("b", alphas[1]);
    assertEquals("c", alphas[2]);
    assertEquals("d", alphas[3]);
}
```

在上面的代码列表中，我以随机顺序将 `String` 值添加到 `alphabet` 中，但当我将 `alphabet` 转换为数组时，数组中的 `String` 值是有序的。

此外，尽管我添加了两次 `String` `"a"`，但它只被添加到 `alphabet` 一次：`size()` 方法返回 `4`，且转换为数组后也只包含一个 `String` `"a"`，这证明了这一点。

### first 获取排序中的第一个元素

当元素被添加到 `SortedSet` 时，元素的排序顺序会保持不变，因此 `first` 总是返回集合中的第一个元素。

```java
@Test
public void canRetrieveFirstFromSortedSet() {
    SortedSet<String> alphabet = new TreeSet<>();

    alphabet.add("c");
    assertEquals("c", alphabet.first());

    alphabet.add("d");
    assertEquals("c", alphabet.first());

    alphabet.add("b");
    assertEquals("b", alphabet.first());

    alphabet.add("a");
    assertEquals("a", alphabet.first());
}
```

### last 获取排序中的最后一个元素

当元素被添加到 `SortedSet` 时，元素的排序顺序保持不变，因此 `last` 根据排序顺序返回集合中的最后一个元素。



```java
@Test
public void canRetrieveLastFromSortedSet() {
  SortedSet<String> alphabet = new TreeSet<>();

  alphabet.add("c");
  assertEquals("c", alphabet.last());

  alphabet.add("b");
  assertEquals("c", alphabet.last());

  alphabet.add("d");
  assertEquals("d", alphabet.last());

  alphabet.add("a");
  assertEquals("d", alphabet.last());
}
```

### headSet 获取元素之前的子集

你可以创建一个包含特定元素之前的所有元素的子集。

```java
SortedSet<String> subset = alphabet.headSet("c");
```

上面的语句将返回 "c" 之前的元素 "a" 和 "b"，如下所示：

```java
@Test
public void sortedCanReturnHeadSet() {
  SortedSet<String> alphabet = new TreeSet<>();

  alphabet.add("c");
  alphabet.add("d");
  alphabet.add("b");
  alphabet.add("a");

  SortedSet<String> subset = alphabet.headSet("c");
  assertEquals(2, subset.size());

  String[] alphas = new String[subset.size()];
  subset.toArray(alphas);

  assertEquals("a", alphas[0]);
  assertEquals("b", alphas[1]);
}
```

### tailSet 获取元素之后并包含元素的子集

```java
SortedSet<String> subset = alphabet.tailSet("c");
```

`tailSet` 创建了集合中大于或等于该元素的子集，因此子集也包含了元素本身。如下所示：

```java
@Test
public void sortedSetReturnTailSet() {
    SortedSet<String> alphabet = new TreeSet<>();

    alphabet.add("c");
    alphabet.add("d");
    alphabet.add("b");
    alphabet.add("a");

    SortedSet<String> subset = alphabet.tailSet("c");

    assertEquals(2, subset.size());

    String[] alphas = new String[subset.size()];
    subset.toArray(alphas);

    assertEquals("c", alphas[0]);
    assertEquals("d", alphas[1]);
}
```

### 两个元素之间的子集

集合包含从第一个元素到第二个元素的元素。例如，给定 "a", "b", "c", "d"，那么 `subSet("b", "d")` 将得到 "b", "c"。如下所示：

```java
@Test
public void sortedSetReturnSubset() {
    SortedSet<String> alphabet = new TreeSet<>();

    alphabet.add("c");
    alphabet.add("d");
    alphabet.add("b");
    alphabet.add("a");

    SortedSet<String> subset = alphabet.subSet("b", "d");

    assertEquals(2, subset.size());

    String[] alphas = new String[subset.size()];
    subset.toArray(alphas);

    assertEquals("b", alphas[0]);
    assertEquals("c", alphas[1]);
}
```

## 用于排序的 Comparator

`comparator` 返回 `SortedSet` 用于比较的 `Comparator` 对象。因此我们需要学习如何创建一个 `Comparator`。

我选择了 `Comparator` 而不是 `Comparable`，因为我认为 `Comparator` 提供了更大的重用潜力和可能性。为了说明这一功能，我们将之前创建的 `User` 对象创建一个 `SortedSet`。

在下面的示例中，我们创建 `User` 对象 `SortedSet` 的尝试将会失败。当我们尝试向 `SortedSet` 添加 "Bob" 时，会抛出 `ClassException`。因为我们的 `User` 对象没有实现 `Comparable` 接口。

```java
@Test
public void sortedSetWithComparator() {
    User bob = new User("Bob", "password5"); // 11
    User tiny = new User("TinyTim", "hello"); // 12
    User rich = new User("Richie", "RichieRich"); // 22
    User sum = new User("sum", "tzu"); // 6
    User mrBaer = new User("Stafford", "sys"); // 11

    SortedSet<User> userSortedList = new TreeSet<>(new UserComparator());

    userSortedList.add(bob);
    userSortedList.add(tiny);
    userSortedList.add(rich);
    userSortedList.add(sum);
    userSortedList.add(mrBaer);

    User[] users = new User[userSortedList.size()];
    userSortedList.toArray(users);

    assertEquals(sum.getUsername(), users[0].getUsername());
    assertEquals(bob.getUsername(), users[1].getUsername());
    assertEquals(mrBaer.getUsername(), users[2].getUsername());
    assertEquals(tiny.getUsername(), users[3].getUsername());
    assertEquals(rich.getUsername(), users[4].getUsername());
}
```

我希望排序基于用户名长度 + 密码长度。这是 `UserComparator` 将要实现的算法。

你可以看到我在每个 `User` 实例化后都以注释的形式加上长度，这样我就知道要断言什么。

代码的其他部分非常简单：

- 创建 `User` 对象
- 使用 `UserComparator` 实例化 `SortedSet`
- 将集合转换为数组，以便我们断言预期的顺序

下一步是创建 `Comparator`。

我将在 `src/main/java` 分支创建它，因为我可能会在更多地方重用它。我会将其添加到 `com.javafortesters.denominities` 包中。

这是你第一次看到哪个元素实现了接口。在这个例子中，我们将实现 `Comparator` 接口：

```java
public class UserComparator implements Comparator {
    public int compare(Object user1, Object user2) {
        // implementation
    }
}
```

为了满足这个接口，我必须实现一个 `compare` 方法，它接收两个 `Object` 参数并返回一个 `int`：

该 `int` 必须对应：

- 如果两个对象在排序算法上相等，则为 0
- 如果 `object1` 小于 `object2`，则为负数 (-ve)
- 如果 `object1` 大于 `object2`，则为正数 (+ve)

由于参数是 `Object` 类型，我们需要在代码中将它们强制转换为正确的类型，对于我们来说就是 `User`：

```java
User user1 = (User) oUser1;
User user2 = (User) oUser2;
```

实现确定的算法来帮助比较值：

```java
int user1Comparator = user1.getPassword().length() + 
             user1.getUsername().length();
```

```java
int user2Comparator = user2.getPassword().length() + 
             user2.getUsername().length();
```

然后计算返回值：

```java
int val = user1Comparator - user2Comparator;
```

太棒了。利用所有这些内容来实现排序算法。问题是 `SortedSet` 同样使用 `Comparator` 来判断 `SortedSet` 中的值是否唯一。而上面的实现允许我将任何用户名 + 密码长度相同的 `User` 添加到 `SortedSet` 中。

在上面的代码中，我无法添加 `mrBaer`，因为他的长度和 `bob` 相同。但我希望在 `SortedSet` 中包含 `mrBaer`。

### Beer

> 我其实并不喜欢喝啤酒。事实上，我受不了那种东西。我更喜欢喝葡萄酒。但我喜欢斯塔福德·比尔先生的书。他是一位特别出色的思想家和控制论专家。如果有机会，读读他的书。

我必须对 `Comparator` 进行一个微小的调整，以允许长度重复，但我将从 `SortedSet` 中排除具有相同用户名且长度重复的用户。这仍然允许具有相同用户名的 `User` 进入（前提是它们的密码长度不同），但这是为了这个比较算法。

```java
if (val == 0) {
    val = user1.getUsername().compareTo(user2.getUsername());
}
```

这样我们就可以返回 `val`：

允许 `@Test` 方法完成的 `UserComparator` 完整代码如下：

```java
public class UserComparator implements Comparator {

    public int compare(Object oUser1, Object oUser2) {

        User user1 = (User) oUser1;
        User user2 = (User) oUser2;

        int user1Comparator = user1.getPassword().length() + 
                             user1.getUsername().length();

        int user2Comparator = user2.getPassword().length() + 
                             user2.getUsername().length();

        int val = user1Comparator - user2Comparator;

        if (val == 0) {
            val = user1.getUsername().compareTo(user2.getUsername());
        }

        return val;
    }
}
```

### 练习：移除 if(val==0)

删除 `if(val==0)` 代码块并运行 `@Test` 方法。确保你理解了之前添加那行代码的原因。

### 练习：不允许重复用户名

创建一个 `DupeUserComparator`，它实现了上述的长度检查，但也不允许具有重复用户名的用户被添加到 `SortedSet` 中。在 `@Test` 方法中使用它，以演示其工作原理。

### 练习：User 类实现 Comparable 接口

在 `User` 类中添加实现 `Comparable` 的代码，并包含不允许重复用户名的算法以及长度检查。在 `@Test` 方法中使用它，以演示其工作原理。

### 练习：查看排序运行过程

在你的 `Comparator` 中添加下面的代码行。在 `return val` 行之前，查看 `Comparator` 的运行情况：

```java
System.out.println("Compare " + user1.getUsername() + 
" with " + user2.getUsername() + " = " + val);
```

## Set & SortedSet 文档

你可以在官方文档网站找到 `Set` 和 `SortedSet` 的详情。

接口：

- docs.oracle.com/javase/tutorial/collections/interfaces/set.html
- docs.oracle.com/javase/tutorial/collections/interfaces/sorted-set.html

实现：

- docs.oracle.com/javase/tutorial/collections/implementations/set.html

# Map

我们在前一章节中描述了 `Map`。在本章中，我们将基于 `Map` 构建并考虑 `SortedMap`。

## SortedMap

`SortedMap` 之于 `Map` 就像 `SortedSet` 之于 `Set`。`SortedMap` 的接口和功能与 `SortedSet` 相同。因此你很快就能理解 `SortedMap` 的工作原理。

- `SortedMap` 根据其键排序，而不是值。
- 使用比较器来确定顺序，或者使用键的 `compareTo` 方法。
- `firstKey` - 根据排序顺序的第一个键
- `lastKey` - 根据排序顺序的最后一个键
- `headMap(k)` - 包含键 "key" 之前的“key-value”键值对的 `SortedMap`
- `tailMap(k)` - 包含键之后及包含键的“key-value”键值对的 `SortedMap`
- `subMap(k1, k2)` - 包含 k1 和 k2 之间（包含 k1，不包含 k2）的“key-value”键值对的 `SortedMap`
- `comparator` - 用于确定键排序顺序的比较器

为了简洁起见，由于我们已经详细介绍过 `SortedSet`，且 `SortedMap` 非常相似，我将使用示例来解释 `SortedMap`，而不是大量的文本。所有方法都使用以下 `Map` 声明和实例化：

```java
SortedMap<String, String> map = new TreeMap<>();

map.put("key1", "value1");
map.put("key3", "value3");
map.put("key2", "value2");
map.put("key5", "value5");
map.put("key4", "value4");
```

## 使用 firstKey & lastKey 获取键

`firstKey` 和 `lastKey` 分别返回 map 中的第一个和最后一个键：

```java
assertEquals("key1", map.firstKey());
assertEquals("key5", map.lastKey());
```

## 使用 headMap, tailMap 和 subMap 创建排序提取集

`headMap(k)` 返回包含键 "key" 之前的“key-value”键值对的 `SortedMap`：

```java
SortedMap<String, String> headMap;
headMap = map.headMap("key3");
assertEquals(2, headMap.size());
assertTrue(headMap.containsKey("key1"));
assertTrue(headMap.containsKey("key2"));
```

`tailMap(k)` 返回包含键之后及包含键的“key-value”键值对的 `SortedMap`：

```java
SortedMap<String, String> tailMap;
tailMap = map.tailMap("key3");
assertEquals(3, tailMap.size());
assertTrue(tailMap.containsKey("key3"));
assertTrue(tailMap.containsKey("key4"));
assertTrue(tailMap.containsKey("key5"));
```

`subMap(k1, k2)` 返回包含 k1 和 k2 之间（包含 k1，不包含 k2）的“key-value”键值对的 `SortedMap`，例如：

```java
SortedMap<String, String> subMap;
```



## SortedMap 与 Comparator

`SortedMap` 的比较器用法与 `SortedSet` 的不同之处在于排序的是键而不是值（或元素）。

当我使用 `SortedMap` 时，我的键通常是字符串，自然排序通常足够了。`Map` 可以使用任何对象作为键，因此我使用了 `SortedSet` 的相同示例来演示 `SortedMap` 比较器。尽管这代表了对 `Map` 的相当奇特的用法。

在这个示例中，假设用户是键，值为 `User` 的描述。

像对待 `SortedSet` 一样使用 `Comparator` 实例化 `SortedMap`：

```java
SortedMap<User, String> userMap = new TreeMap<User, String>(new UserComparator());
```

其余代码与 `SortedSet` 相同：

- 创建一组 `User` 对象
- 实例化 `SortedMap`
- 将所有 `User` 对象作为键放入 `Map`，并添加描述作为值
- 将键提取到数组中 - 它们将按照比较器指定的排序排序
- 对排序进行断言

```java
@Test
public void sortedMapWithComparatorForUser() {
    User bob = new User("Bob", "pASswword"); // 11
    User tiny = new User("TinyTim", "hello"); // 12
    User rich = new User("Richie", "RichieRich"); // 22
    User sun = new User("sun", "tzu"); // 6
    User mrBeer = new User("Stafford", "sys"); // 11

    SortedMap<User, String> userMap = new TreeMap<User, String>(new UserComparator());

    userMap.put(bob, "Bob rules");
    userMap.put(tiny, "Tiny Time");
    userMap.put(rich, "Rich Richie");
    userMap.put(sun, "Warfare Art");
    userMap.put(mrBeer, "Cybernetician");

    User[] users = new User[userMap.size()];
    userMap.keySet().toArray(users);

    assertEquals(sun.getUsername(), users[0].getUsername());
    assertEquals(bob.getUsername(), users[1].getUsername());
    assertEquals(mrBeer.getUsername(), users[2].getUsername());
    assertEquals(tiny.getUsername(), users[3].getUsername());
    assertEquals(rich.getUsername(), users[4].getUsername());
}
```



# Queue & Deque

我不会详细介绍 `Queue` 和 `Deque`，因为在现实世界中我从未使用过它们。

`Queue`（队列）提供了一种先进先出的集合。你可以在队列的末尾添加元素，并从头部移除它们。

`Deque`（双端队列）允许你在队列的头部或尾部添加元素，但不能在中间添加。

了解这些集合是值得的，但如果你需要使用它们，我相信你现在能够理解官方网站上的文档了。

## Queue & Deque 文档

你可以在官方文档站点找到 `Queue` 和 `Deque` 的详情。

### 接口

- docs.oracle.com/javase/tutorial/collections/interfaces/queue.html
- docs.oracle.com/javase/tutorial/collections/interfaces/deque.html

### 实现

- docs.oracle.com/javase/tutorial/collections/implementations/queue.html
- docs.oracle.com/javase/tutorial/collections/implementations/deque.html

## 实现汇总

你在上面的列表中看到了我使用的实现。

为了完整起见，我在下面列出了我们在章节中涵盖过的各种接口的实现。

- 集合 Collection & List:
    - `ArrayList`
- Set:
    - `HashSet`
    - `TreeSet` - 用于排序
- Map:
    - `HashMap`
    - `TreeMap` - 用于排序键

在编写用于并行运行的 `@Test` 方法的共享对象代码时，我经常需要调用 `java.util.concurrent` 中的 `ConcurrentHashMap`。在开始之前，我并不了解 `ConcurrentHashMap`。但我了解集合，并且知道需要一些并发处理，所以我进行了一些网络搜索并找到了它。

我在上面的段落中真正想说的是先学习几个类。然后，如果你有时间，看看其他的，或者等到你需要的时候。你会发现你需要一个新的实现，因为你不得不对现有的实现编写变通方案，很可能别人已经遇到过你的问题并写了解决它的类。你只需要把它找出来。

## 总结

`SortedMap` 和 `SortedSet` 需要一些额外的工作——特别是实现 `Comparator` 或 `Comparable` 接口。

在实践中，我默认实现 `Comparator` 对象，因为这给了我更大的灵活性，而且不需要让我的领域对象充斥 `Comparable` 接口。

## 参考文献和推荐阅读

- Sorted Set 接口
    - docs.oracle.com/javase/tutorial/collections/interfaces/set.html
    - docs.oracle.com/javase/tutorial/collections/interfaces/sorted-set.html
- Sorted Set 实现
    - docs.oracle.com/javase/tutorial/collections/implementations/set.html
- Sorted Map 接口
    - docs.oracle.com/javase/tutorial/collections/interfaces/map.html
    - docs.oracle.com/javase/tutorial/collections/interfaces/sorted-map.html
- Sorted Map 实现
    - docs.oracle.com/javase/tutorial/collections/implementations/map.html
- Queue and Deque 接口
    - docs.oracle.com/javase/tutorial/collections/interfaces/queue.html
    - docs.oracle.com/javase/tutorial/collections/interfaces/deque.html
- Queue and Deque 实现
    - docs.oracle.com/javase/tutorial/collections/implementations/queue.html
    - docs.oracle.com/javase/tutorial/collections/implementations/deque.html

# 第二十二章 - 高级概念

| 章节总结 |
| --- |
| 本章提供了以下领域的简要概述……（下接列表） |

本章提供了以下每个领域的简要概述，并提供了供你开始研究该主题的链接。

- 接口
- 抽象类
- 泛型
- 日志
- 枚举
- 正则表达式
- 反射
- 注解
- 设计模式
- 并发
- 额外的文件考虑

我们现在快结束了。

这本书的原始意图是按照顺序涵盖你需要理解的 Java 基础，让你能够快速使用这些概念，而不会被过多的额外开销分散注意力。

本章提供了“高级”概念的概述，这些概念在 Java 中并不一定是功能性的，但知道它们存在是重要的，并为你的后续步骤提供了可以研究的内容。

在编写简单的 JUnit 测试时，你可能不需要这些概念。

当你开始构建大量良好结合的代码时，当 Java 代码本身需要体现良好的设计原则时，你可能需要它们。

在我编写自动化代码的前 3 或 4 年里，我可能根本没有用过任何这些概念。

- 我使用组合来重用代码，而不使用接口。
- 我很少使用继承。
- 我从不使用抽象类。
- 我并不真的知道枚举是什么。
- 等等。

我的代码很简单，但没有设计原则将它们结合在一起。这就是为什么我把这些称为“高级概念”。

## 接口

我不会详细介绍 `Queue` 和 `Deque`，因为在现实世界中我从未使用过它们。

`Queue`（队列）提供了一种先进先出的集合。你可以在队列的末尾添加元素，并从头部移除它们。

`Deque`（双端队列）允许你在队列的头部或尾部添加元素，但不能在中间添加。

了解这些集合是值得的，但如果你需要使用它们，我相信你现在能够理解官方网站上的文档了。

## Queue & Deque 文档

你可以在官方站点找到 `Queue` 和 `Deque` 的详情。

### 接口

- docs.oracle.com/javase/tutorial/collections/interfaces/queue.html
- docs.oracle.com/javase/tutorial/collections/interfaces/deque.html

### 实现

- docs.oracle.com/javase/tutorial/collections/implementations/queue.html
- docs.oracle.com/javase/tutorial/collections/implementations/deque.html

## 实现汇总

你在上面的列表中看到了我使用的实现。

为了完整起见，我在下面列出了我们在章节中涵盖过的各种接口的实现。

- 集合 Collection & List:
    - `ArrayList`
- Set:
    - `HashSet`
    - `TreeSet` - 用于排序
- Map:
    - `HashMap`
    - `TreeMap` - 用于排序键

在编写用于并行运行的 `@Test` 方法的共享对象代码时，我经常需要调用 `java.util.concurrent` 中的 `ConcurrentHashMap`。在开始之前，我并不了解 `ConcurrentHashMap`。但我了解集合，并且需要一些并发处理，所以我进行了一些网络搜索并找到了它。

我在上面的段落中真正想说的是先学习几个类。然后，如果你有时间，看看其他的，或者等到你需要的时候。你会发现你需要一个新的实现，因为你不得不对现有的实现编写变通方案，很可能别人已经遇到过你的问题并写了解决它的类。你只需要把它找出来。

## 总结

`SortedMap` 和 `SortedSet` 需要一些额外的工作——特别是实现 `Comparator` 或 `Comparable` 接口。

在实践中，我默认实现 `Comparator` 对象，因为这给了我更大的灵活性，而且不需要让我的领域对象充斥 `Comparable` 接口。

## 参考文献和推荐阅读

- Sorted Set 接口
    - docs.oracle.com/javase/tutorial/collections/interfaces/set.html
    - docs.oracle.com/javase/tutorial/collections/interfaces/sorted-set.html
- Sorted Set 实现
    - docs.oracle.com/javase/tutorial/collections/implementations/set.html
- Sorted Map 接口
    - docs.oracle.com/javase/tutorial/collections/interfaces/map.html
    - docs.oracle.com/javase/tutorial/collections/interfaces/sorted-map.html
- Sorted Map 实现
    - docs.oracle.com/javase/tutorial/collections/implementations/map.html
- Queue and Deque 接口
    - docs.oracle.com/javase/tutorial/collections/interfaces/queue.html
    - docs.oracle.com/javase/tutorial/collections/interfaces/deque.html
- Queue and Deque 实现
    - docs.oracle.com/javase/tutorial/collections/implementations/queue.html
    - docs.oracle.com/javase/tutorial/collections/implementations/deque.html

## 枚举

一个枚举可以被看作一组预定义的常量。对于在你的抽象层中组织常量非常有用。

这些常量也可以拥有方法，使它们变得非常灵活，甚至可能省去在 `switch` 语句中使用它们的需求，转而直接使用枚举本身的方法。

### 研究链接

- 官方枚举文档
  - docs.oracle.com/javase/tutorial/javaOO/enum.html

## 正则表达式

我们在正文中简要提到了正则表达式。

正则表达式为输入的解析和处理提供了极其强大的功能和灵活性。

当你的代码开始变得复杂，你拥有一系列嵌套的 `if` 语句或复杂的转换逻辑时，那么可能是时候升级到使用正则表达式了。

### 研究链接

- docs.oracle.com/javase/tutorial/essential/regex/

## 反射

我们的大部分编程工作都使用特定的对象，而且我们在编码时已经知道了可用的方法和接口。

反射意味着在运行时查询类以查找有关对象的信息，例如：发现对象上有哪些方法、它们的参数是什么、存在哪些注解等。

你也可以添加方法签名，允许你调用私有方法或访问私有变量等。

我认识的大多数程序员都反感反射。事实上，在应用程序中使用反射时，它的速度可能会很慢，而且在运行时执行这些操作可能是危险的。

然而，我过去遇到的一些问题只有通过反射才能解决：

- 在没有文档的情况下尝试使用库
- 按非顺序使用某些功能
- 绕过抽象层中的局限性

我们使用的一些工具（例如 JUnit）之所以能工作是因为反射，而且你添加到代码中的所有注解都是通过反射访问的。

学习反射，以便你知道它能做什么。这样当你遇到一个你认为没有其他方法解决的问题时，你就可以尝试使用它。

### 研究链接

- docs.oracle.com/javase/tutorial/reflect

## 注解

当你在方法代码上方放置 `@Test` 时，你就使用了注解。

注解是元数据。它们被编译器使用，并在运行时通过反射访问你的代码时被使用。

我过去曾在尝试寻找报告执行覆盖的方法以及创建自定义 JUnit 运行器时使用过注解。

了解这些很重要，但我猜你可能不会频繁使用它们。

### 研究链接

- docs.oracle.com/javase/tutorial/java/annotations

## 设计模式

设计模式是你在项目中听到的那些大家认为每个人都懂、但从不解释的说法，例如：

- 单例
- 观察者
- 访问者
- 工厂
- 代理
- 等

这些是解决常见问题的方法。Gamma、Helm、Johnson 和 Vlissides 编写的著名书籍《设计模式》列出了 23 种常见模式和一些解决方案。

对它们有一定的熟悉很重要，因为它们提供了他人已经解决的问题的方法。它们还将帮助你理解开发者在向你解释代码时在说什么。

### 研究链接

- c2.com/cgi/wiki?DesignPatternsBook
- oodesign.com/

## 并发

并发在 Java 中非常重要。它允许你在多个线程中运行代码，并可能更快地获得结果，或者同时运行多个 `@Test` 方法。

你经常会读到某些类不是“线程安全的”，这意味着当你尝试使用并发时应该谨慎使用它们。

并发有不同的方法，从简单地使用 `synchronized`（意味着一个方法一次只能被单个线程调用）到完全的非阻塞并发。

这个话题对于这本书来说太高级了。遗憾的是，很多测试人员试图尽早解决这个问题，因为他们想并行运行他们的 `@Test` 方法。通常甚至有并行检查用例的迫切需求。

并发是 Java 中非常有趣的一部分，我曾创建以多线程方式使用的自动化抽象。但在我学习 Java 早期并不是这样。我建议你阅读相关内容，但在你非常熟悉应用程序如何工作之前，不要尝试进行任何并发编程。否则，你可能会创建出一些间歇失败、难以调试和修复的代码。

我主要在这一节中添加并发内容，是为了防止你过快地尝试去使用它。

### 研究链接

- docs.oracle.com/javase/tutorial/essential/concurrency

## 额外的文件考量

在文件章节中，我跳过了很多信息，试图创建示例代码和基础信息，以涵盖你许多初始的文件处理需求。

我还涵盖了我使用文件的大部分内容。我很少需要处理基础的文件块：流和通道。

我很少担心文件编码，因为我的大多数文件都是从同一个 JUnit 测试类中创建和读取的，而且因为它们是临时的，在 `@Test` 完成后就会被删除。

我将链接作为研究项目包含在下方，以防你在你的环境中需要它们。

### 研究链接

- 流
  - docs.oracle.com/javase/tutorial/i18n/text/stream.html
- 文件 IO
  - docs.oracle.com/javase/tutorial/essential/io/file.html

## 总结

我知道这一章的示例很少。主要目的是通过创建示例代码和基础信息，来涵盖你许多初始的文件处理需求。

我涵盖了我使用文件的大部分内容。我很少需要处理基础的文件块：流和通道。

我没有详细介绍 Java 提供的许多其他功能，因为这些领域有专门的书籍，我在下一章会提到其中一些。我希望你关注并阅读提供的研究链接。

# 推荐阅读与资源

## 推荐阅读

### 有效 Java

《有效 Java》由 Joshua Bloch 编写，他在编写时是第二版。这本书适用于初学者和高级程序员。

Java 开发者通常从其他地方积累知识，“有效 Java”可以帮助缩短这一过程。它有 78 个章节，每一章都比较短，但内容很密集。当我第一次读它时，我觉得很重，因为我没有足够的经验来理解它。但我重新读了它，并随着经验的增长不断阅读。每次阅读，我都能发现新的细节，或对概念有更深入的理解。

因为每一章都很短，我会回到这本书来刷新记忆。这本书也帮助我充分理解了枚举，足以让我阅读《并发实战》。我建议你在学习早期就阅读并购买这本书。如果你没有完全理解，就反复阅读。它专注于 Java 语言的各个方面，可以提高你的实际工作效率。

### 实现模式

另一本需要反复阅读的书籍。根据你阅读时的经验水平，你每次从中获得的信息不同。

《实现模式》由 Kent Beck 编写，解释了专业编码涉及的一些思维过程。这本书是帮助我做到：

- 专注于保持代码简单
- 决定学习 Java 基础（并知道需要如何查找信息）
- 在引入新库之前，尝试使用语言内置的功能

其他涵盖相似主题的书包括 Robert C. Martin 写的《整洁代码》，以及 Andrew Hunt 和 David Thomas 写的《实战程序员》。但我发现《实现模式》对我工作更有用且实用。

有关 Kent Beck 的写作和工作的更多信息，请访问他的网站：

- threereiversinstitute.org

### 测试引导的面向对象软件增长

另一本在我还没准备好阅读它时就受益匪浅的书。后来我能够重读它并学到更多。重读它仍然让我获得了价值。

- Steve Freeman 和 Nat Pryce 写的《测试引导的面向对象软件增长》

重点关注如何使用 `@Test` 方法来编写和理解代码。它对模拟对象也有很好的讲解。

这本书改变了我的编码风格，以及我构建抽象层的方法。

该书的官方首页是 growing-object-oriented-software.com

### 隐蔽 Java

由 Alex Kalinovovsky 编写的《隐蔽 Java：反编译、补丁与逆向工程技术》由于写于 2004 年，开始显出它的时代感。但它强调了一些处理 Java 库的方法，如果你是一个程序员，你真的不会用到这些方法。

但有时作为测试人员，我们必须处理没有源代码的预编译库，并在脱离上下文的情况下使用部分代码。

我发现这本书对于学习反射以及其他拆解 Java 应用相关的实践非常有帮助。

你通常可以以很廉的价格买到它的二手书。还有其他关于反编译、逆向工程和反射的书。但这一本开启了我的门，我仍然觉得它清晰简单。

### Java 并发实战

我不建议在刚开始学习 Java 时尝试处理并发问题。

但在某个时刻，你可能想要并行运行你的代码，或者创建一些线程让你的代码运行得更快。然后你可能会失败，并且并不真正理解为什么。

我使用《Effective Java》来帮助入门。但 Brian Goetz 写的《Java 并发实战》是我在必须让自动化抽象层与并发代码工作时阅读的书。

### Java 核心：第一卷

《Java 核心》系列书籍非常厚，超过 1000 页。如果你真的想深入理解 Java，那么这些是你该读的书。

我觉得读它们很费力，而且并不经常读。我倾向于直接使用 Java 库和方法本身的 JavaDoc。

但是，有时我想对该语言有一个概览，了解我没有使用的内置功能的范围，而这些功能在其他情况下我会求助于外部库的。

每当我翻阅《Java 核心》时，我都会发现一些细微之处和一组新功能，但我并没有去使用它们。

### 精通正则表达式

我们在这书中并没有涵盖正则表达式的全部威力。

我倾向于保持代码简单易读，所以我起初会使用字符串处理。

但随着时间的推移，我发现可以用正则表达式来替换一系列的 `if` 块和字符串转换。

由于我不经常使用正则表达式，我发现每次都必须重新学习，并且仍然会参考 Jeffrey E.F. Friedl 写的《精通正则表达式》。

可以考虑的替代方案：Jan Govaerts 写的《正则表达式食谱》，它也非常好。

我有时会在编写正则表达式时使用 RegexMagic 工具，它是 Jan Govaerts 编写的，让我可以在一系列示例数据上测试正则表达式，并为许多不同的语言生成示例代码。

Jan 还维护着 web 网站 regular-expressions.info，上面有很多教程信息。

## 推荐视频

John Purcell 在 caveofprogramming.com 制作的视频被我的测试人员推荐过。

我查看了其中一些，John 为书中涵盖的许多项目以及“进阶概念”部分中的内容提供了编码示例。

John 的方法是围绕编写程序展开的，我认为如果你已经完成了这本书，你将从 John 提供的基于传统程序员的覆盖中受益。

## 推荐网站

对于通用的 Java 新闻以及最新的会议视频，我推荐以下网站。

- theserverside.com
- infoq.com/java

确保你订阅了上述网站的 RSS 订阅。

我要提醒你，我有一个 javaForTesters.com 网站，我计划随着时间的推移添加更多信息和其他资源的链接。我还会在该网站上添加额外的练习和示例，而不是继续扩展这本书。

记住，书中使用的所有代码以及练习题的答案都可以从 github.com/eviltester 下载。

## 下一步

这是一本初级书籍。

你可以从“进阶概念”章节看到，Java 中有很多我没有涵盖的特性。其中许多我并不常用，我不想用在其他书籍或视频中可以找到广泛覆盖来充实这本书。

我希望这本书能以一种我认为对于编写代码的人但不一定是编写系统的人来说合理的顺序带你了解 Java 语言。

你的下一步是什么？继续学习。

我建议你从这里推荐的书籍和视频开始，但也问问你的同事。

你将致力于项目工作，取决于你使用的库类型以及技术领域。

## 参考文献

- Java For Testers
  - github.com/eviltester
- Joshua Bloch
  - en.wikipedia.org/JoshuaBloch
- Kent Beck
  - twitter.com/kentbeck
- Three Rivers Institute
  - threereiversinstitute.org
- Growing Object-Oriented Software, Guided by Tests
  - growing-object-oriented-software.com
- Steve Freeman's Blog
  - natpryce.com
- Core Java Book
  - borstmann.com
- Java Concurrency In Practice
  - jcip.net
- Regular Expressions
  - Mastering Regular Expressions home page regex.info
  - regular-expressions.info/
  - RegexMagic
    - regexmagic.com
  - regexpal.com
  - www.regexxr.com

# 附录 - IntelliJ 提示与技巧

在书中我提到的使用 IntelliJ 的提示、技巧和快捷键。我将所有这些收集在附录中以便查询，并在书中增加了一些关于 IntelliJ 的额外信息。

## 快捷键

此表包含了我最常用的快捷键。

| 功能 | Windows | Mac |
|---|---|---|
| 创建 | `alt + insert` | `ctrl + n` |
| 意图 | `alt + enter` | `alt + enter` |
| 操作 | `alt + return` | `alt + return` |
| 运行单元测试 | `ctrl + shift + F10` | `ctrl + shift + F10` |
| 显示参数 | `ctrl + p` | `cmd + p` |
| 显示 Java | `ctrl + q` | `ctrl + j` |
| 代码补全 | `ctrl + space` | `ctrl + space` |
| 按类查找 | `ctrl + n` | `ctrl + n` |
| 按文件名查找 | `ctrl + shift + n` | `ctrl + shift + n` |
| 按符号查找 | `ctrl + shift + alt + n` | `ctrl + shift + alt + n` |

## 代码补全

代码补全是你的朋友。你可以用它来探索 API 和库。你只需要开始输入，然后看到你可以使用的特定项目。

如果你关闭了弹出菜单，可以通过按下按键强制开始代码补全：

- `ctrl + space`

## 导航源代码



## Ctrl + Click

对于你代码中的任何方法，无论是内置方法、库方法，甚至是你自己编写的方法，你都可以按住 `ctrl` 键并左键点击方法名，以跳转到该方法的源码。

系统可能会提示你允许 IntelliJ 下载外部库的源码。在处理本书的示例源码时，这非常有帮助，因为你可以从 `@Test` 方法代码内部导航到领域对象。

## 查找类和符号

如果你在本书中使用某个方法名或类名，但不知道在源码中哪里找到它，可以使用 IntelliJ 的查找功能来帮助。

要查找类名，请使用键盘快捷键：

- `ctrl + n`

这可以执行部分匹配，因此你不需要输入类的完整名称。如果你想在项目中查找“文件”，请使用键盘快捷键：

- `ctrl + shift + n`

如果你想查找方法名或变量名（符号），请使用键盘快捷键：

- `ctrl + shift + alt + n`

## 运行 JUnit 测试

使用 `@Test` 注解方法使我们轻松地“运行”所编写的方法。你可以右键点击方法名或类，并选择“Run as JUnit test”。或使用快捷键：

- `ctrl + shift + F10`

## 加载项目源码

将项目加载到 IntelliJ 最简单的方法（适用于本书的示例代码）是使用：

- `File \ Open` 并选择 `pom.xml` 文件。

## 帮助菜单

帮助菜单提供的不仅仅是指向帮助文件的链接。

### 查找操作

`Help \ Find Action` 菜单选项允许你输入操作，IntelliJ 将提供菜单选项和快捷键来提供帮助。
例如：

- 选择 `Help \ Find Action`
- 输入 "unit"，你将看到一个可以帮助在 IntelliJ 中配置 JUnit 的“设置”列表
- 输入 "run"，你将看到一系列运行代码或测试的选项

该列表不仅仅是为了提供信息，你可以点击列表中的项目，将会被带到 IntelliJ 的相应功能或运行该命令。

### 生产力指南

`Help \ Productivity Guide` 菜单选项会显示带有常用生产力改进内容的对话框。

你可以点击列表中的项目查看其作用，还可以查看你使用了哪些、哪些尚未使用。

这可以帮助你快速学会 IntelliJ 的基础知识。

## 总结

IntelliJ 在处理代码方面提供了很大的灵活性。随着时间的推移，随着你对 IDE 的了解，你将学会让 Java 工作变得更快。

随着时间的推移，我会在 JavaForTesters.com 上添加视频和信息，展示书中没有空间添加的 IntelliJ 功能。

## 附录 - 练习答案

本附录包含了书中练习题的答案和注释。
这里找到的所有代码也可以在支持源码 github 仓库中找到：

- https://github.com/eviltester/javaForTestersCode

## 第三章 - 我的第一个 JUnit 测试

### 检查是 5 而不是 4

当我运行 JUnit 测试时，看到控制台显示 `2=4 expected:<5> but was:<4>`，这是一个断言错误（Assertion Error）。

```
1 java.lang.AssertionError: 2=4 expected:<5> but was:<4>
2 at org.junit.Assert.fail(Assert.java:88)
3 at org.junit.Assert.failNotEquals(Assert.java:743)
4 at org.junit.Assert.assertEquals(Assert.java:118)
5 at org.junit.Assert.assertEquals(Assert.java:555)
6 at com.javafortesters.chap03myfirsttest.examples.MyFirstTest.
7 canAddTwoWoPlusTwo(MyFirstTest.java:19)
```

实际消息比这个长，但我们将在后面的章节中解释错误消息。

重要的是，在 IntelliJ 中点击错误消息中的 `MyFirstTest.java:19` 超链接，将被带到编辑器中抛出异常的代码行。这会让调试变得容易得多。创建额外的 `@Test` 方法来检查：

```java
@Test
public void canSubtractFromTwo(){
  int answer = 2-2;
  assertEquals("2-2=0", 0, answer);
}
```

```java
@Test
public void canDivideByTwo(){
  int answer = 4/2;
  assertEquals("4/2=2", 2, answer);
}
```

```java
@Test
public void canMultiplyTwoByTwo(){
  int answer = 2*2;
  assertEquals("2*2=4", 4, answer);
}
```

### 检查类的命名

在示例代码中，你会看到我编写了一些没有运行的 JUnit 测试，断言失败了。为了说明命名非常重要这一点：

```java
public class NameClass {
    @Test
    public void classNameHasNoTestInItIsNotRun(){
        // 这个测试没有运行，所以我们可以通过
        // 测试让它在 IntelliJ 中失败
        assertTrue(true);
    }
}
```

*（注：原文第246-247 页的 OCR 文本存在大量重复或损坏，此处提供了唯一的逻辑块。）*

但 User 类对其数据没有控制权。稍后我们在 setter 和 getter 方法中添加了检查，这样我们就可以向对象添加无效数据。如果你将字段设为 `public`（公共），你就失去了这些保护措施。

```java
@Test
public void canConstructWithUsernameAndPassword() {
    User user = new User();
    user.username = "bob";
    assertEquals("not default username", "bob", user.username);
}
```

```java
@Test
public void setNameToInvalidValue() {
    User user = new User();
    user.username = "12345$%%";
    assertEquals("invalid username", "12345$%", user.username);
}
```

### 测试字段和参数名

当你从*构造函数*中移除这些时：

```java
public User(String username, String password) {
    username = username;
    password = password;
}
```

当 Java 看到这一行时：

```java
username = username;
```

它会执行该行，但将传入的*参数*值赋值给*参数*，而不是*字段*。我们名为 `username` 的*字段*从未被赋予过值，且为 `null`，正如断言消息所示：

`java.lang.AssertionError: given username expected:<admin> but was: <null>`

当我们重命名参数时：

```java
public User(String a, String aPassword) {
    username = aUsername;
    password = aPassword;
}
```

那么我们就不需要 `this` 关键字了。*参数*和*字段*名称不同，因此它们不会冲突。

这取决于你选择适应哪种编码风格。

我这两种者都使用，并在不同的时间之间切换。通过将*参数*命名为与*字段*相同的名称，并使用 `this` 关键字来区分它们，当我在构造函数中使用代码补全时，代码补全会显示 `username` 和 `password`，这让我很容易看出*参数*指代的是什么。这种代码补全的用例是我决定是否使用 `this` 或重命名参数的主要因素。

## 第八章 - 选择与决策

### 猫还是猫们？三元运算符

编写一个 `@Test` 方法，使用三元运算符：如果 `numberOfCats` 等于 1，则返回 "cat"；如果 `numberOfCats` 不等于 1，则返回 "cats"。

```java
@Test
public void catOrCats() {
    int numberOfCats = 1;
    assertEquals("1 == cat", "cat", (numberOfCats == 1) ? "cat" : "cats");
    numberOfCats = 0;
    assertEquals("0 == cats", "cats", (numberOfCats == 1) ? "cat" : "cats");
    numberOfCats = 2;
    assertEquals("2 == cats", "cats", (numberOfCats == 1) ? "cat" : "cats");
}
```

当我重写代码以使用方法时，代码变得更简洁并避免了重复。

```java
@Test
public void catOrCatsAsMethod() {
    assertEquals("1 == cat", "cat", catOrCats(1));
    assertEquals("0 == cats", "cats", catOrCats(0));
    assertEquals("2 == cats", "cats", catOrCats(2));
}

private String catOrCats(int numberOfCats) {
    return (numberOfCats == 1) ? "cat" : "cats";
}
```

### 如果为真则执行 AssertTrue

```java
@Test
public void truthy() {
    boolean truth = true;
    if (truth) {
        assertTrue(truth);
    }
    assertFalse(!truth);
}
```

### AssertTrue 否则执行 AssertFalse

对于单个语句，我不需要添加大括号：

```java
@Test
public void truthIfElse() {
    boolean truth = true;
    if (truth)
        assertTrue(truth);
    else
        assertFalse(truth);
}
```

当 `if` 或 `else` 中有多个语句时，我需要添加 `{ }` 大括号：

```java
@Test
public void truthIfElseBraces() {
    boolean truth = true;
    if (truth) {
        assertTrue(truth);
    } else {
        assertFalse(truth);
    }
}
```

我可以选择不写 `else` 的大括号，因为只有一个条件，但在实践中我不会这样做，因为我以后可能想扩展 `if/else` 语句的数量，我的代码如下：

```java
@Test
public void truthIfElseBraces() {
    boolean truth = true;
    if (truth) {
        assertTrue(truth);
    } else {
        assertFalse(truth);
    }
}
```

```java
@Test
public void truthIfElseBraces() {
    boolean truth = true;
    if (truth)
        assertTrue(truth);
        assertFalse(!truth);
    else
        assertFalse(truth);
}
```

### 嵌套 If Else

如果你发现自己写了类似下面的代码，说明你做错了，没有正确考虑到问题。我决定将主逻辑提取到单独的方法中，这样可以更方便地处理 `true` 和 `false` 的组合。你检查你的答案了吗？

```java
@Test
public void nestedIfElse() {
    horrorOfIfElse(true, true);
    horrorOfIfElse(true, false);
    horrorOfIfElse(false, true);
    horrorOfIfElse(false, false);
}
```

```java
public void horrorOfIfElse(boolean truthy, boolean falsy) {
    if (truthy) {
        if (falsy) {
            System.out.println("T | F");
            assertTrue(truthy);
            assertFalse(falsy);
        } else {
            System.out.println("T | T");
            assertTrue(truthy);
            assertFalse(falsy);
        }
    } else {
        System.out.println("F | F");
        assertFalse(truthy);
    }
}
```

### Switch 代码

我为 `default` 添加了 `break`。你可以自己去验证一下它是否需要 `break`，或者移除一些 `break` 语句并验证结果是否符合预期。

```java
@Test
public void countrySwitch() {
    assertEquals("United Kingdom", countryOf("UK"));
    assertEquals("United States", countryOf("US"));
    assertEquals("France", countryOf("FR"));
    assertEquals("Sweden", countryOf("SE"));
    assertEquals("Rest of World", countryOf("ES"));
    assertEquals("Rest of World", countryOf("CH"));
}
```

```java
private String countryOf(String shortCode) {
  String country;
  switch (shortCode.toUpperCase()) {
    case "UK":
      country = "United Kingdom";
      break;
    case "US":
      country = "United States";
      break;
    case "FR":
      country = "France";
      break;
    case "SE":
      country = "Sweden";
      break;
    default:
      country = "Rest Of World";
      break;
  }
  return country;
}
```

### Switch 它

这个练习的设计是为了让你对 `String` 以外的变量进行 `switch`，并看到你如何处理 `> 4` 和 `< 1` 条件。在我下面的答案中，你可以看到我在 `default` 中添加了 `if` 语句。

```java
@Test
public void integerString() {
  assertEquals("One", integerString(1));
  assertEquals("Two", integerString(2));
  assertEquals("Three", integerString(3));
  assertEquals("Four", integerString(4));
  assertEquals("Too big", integerString(5));
  assertEquals("Too big", integerString(Integer.MAX_VALUE));
  assertEquals("Too small", integerString(0));
  assertEquals("Too small", integerString(Integer.MIN_VALUE));
}
```

```java
private String integerString(int anInt) {
  String valReturn = "";
  switch (anInt) {
    case 1:
```



## 第九章 - 数组和 for 循环迭代

### 创建用户数组

为了处理 `User` 对象，我必须先导入 `User` 类。然后创建了数组并添加了用户。

```java
import com.javafortesters.domainentities.User;

@Test
public void createArrayOfUsers() {
    User[] users = new User[3];
    users[0] = new User("bob", "ba55Password");
    users[1] = new User("eris", "ea55Password");
    users[2] = new User("ken", "ka55Password");

    assertEquals("bob", users[0].getUsername());
    assertEquals("eris", users[1].getUsername());
    assertEquals("ken", users[2].getUsername());
}
```

注意我在用户名上添加了断言，以检查我是否正确添加了用户。你曾在你的 `@Test` 方法中添加断言吗？如果没有，你是如何知道它运行正常的的？

### 遍历用户数组

我在上面的 `@Test` 方法中添加了以下代码，用于遍历数组并打印数组中的值：

```java
for(User aUser : users) {
    System.out.println(aUser.getUsername());
}
```

### 创建一个包含 100 个用户的数组

在我的示例答案中，我选择使用 `system.out.println` 数组进行检查。我可以在循环之后设置一个断点，并使用调试器通过在调试模式下运行代码来检查。我添加了断言，它使用 `for each` 循环遍历每一个项目，并使用计数器 `userId` 检查用户名和密码。由于我知道理论上应该是 100 个，因此当我退出 `for each` 循环时，我期望我的 `userId` 等于 101。你可能选择了其他方法来实现。这就是为什么有许多方法。

```java
@Test
public void exerciseCreateArrayOf100Users() {
    User[] users = new User[100];

    for(int index = 0; index < 100; index++) {
        int userId = index + 1;
        users[index] = new User("user" + userId, "password" + userId);
    }

    // 检查创建
    for(User aUser : users) {
        System.out.println(aUser.getUsername() + ", " + aUser.getPassword());
    }

    // 额外的断言检查
    int userId = 1;
    for(User aUser : users) {
        assertEquals("user" + userId, aUser.getUsername());
        assertEquals("password" + userId, aUser.getPassword());
        userId++;
    }
    // 检查最后一个输出是 100，即下一个将是 101
    assertEquals(userId, 101);
}
```

### 排序工作日数组并断言结果

文本按字母顺序排序，由于所有字符串都以大写字母开头，单词的顺序正是我们预期的。

```java
@Test
public void sortWorkdaysArrayAssertResult() {
    String[] workdays = {"Monday", "Tuesday", "Wednesday", "Thursday", "Friday"};

    Arrays.sort(workdays);

    assertEquals(workdays[0], "Friday");
    assertEquals(workdays[1], "Monday");
    assertEquals(workdays[2], "Thursday");
    assertEquals(workdays[3], "Tuesday");
    assertEquals(workdays[4], "Wednesday");
}
```

在更改日期名称后，我期望以小写字母开头的单词在前：

```java
@Test
public void sortWorkdaysMixedCaseArrayAssertResult() {
    String[] workdays = {"Monday", "Tuesday", "Wednesday", "thursday", "Friday"};

    Arrays.sort(workdays);

    assertEquals(workdays[0], "Friday");
    assertEquals(workdays[1], "Tuesday");
    assertEquals(workdays[2], "Wednesday");
    assertEquals(workdays[3], "monday");
    assertEquals(workdays[4], "thursday");
}
```

### 理解 print2DIntArray 方法是如何运作的

```java
public void print2DIntArray(int[][] matrix) {
    for (int[] outer : matrix) {
        if (outer == null) {
            System.out.print("null");
        } else {
            for (int inner : outer) {
                System.out.print(inner + ", ");
            }
        }
        System.out.println("");
    }
}
```

- 第 01 行声明接收二维 `int` 参数的方法
- 第 02 行遍历外层数组
- 第 03 行如果外层数组为空，则...
- 第 04 行输出 `"null"`，我们不尝试处理该数组的内容
- 第 05 行外层数组不为空，因此...
- 第 06 行遍历该数组的内容
- 第 07 行输出数组单元格
- 第 10 行输出空行

### 创建三角形数组

为了创建一个三角形，我创建了一个允许锯齿数组的数组。然后遍历数组，为数组中的每个单元格赋值。我遍历单元格并插入值。

```java
@Test
public void createTriangleArray() {
    int[][] triangle = new int[5][];
    for(int row = 0; row < triangle.length; row++) {
        triangle[row] = new int[row + 1];
        for(int i = 0; i < triangle[row].length; i++) {
            triangle[row][i] = i;
        }
    }
    
    print2DArray(triangle);
}

public void print2DArray(int[][] multi) {
    for(int[] outer : multi) {
        if(outer == null) {
            System.out.print("null");
        } else {
            for(int inner : outer) {
                System.out.print(inner + ", ");
            }
        }
        System.out.println("");
    }
}
```

## 第十章 - 用 for 循环代替 while 循环

```java
@Test
public void useForLoopInstead() {
    String[] days = {"Tuesday", "Thursday", "Monday", "Sunday", "Friday"};
    List<String> list = Arrays.asList(days);
    for(String day : list) {
        // for 循环逻辑
    }
}
```

### 创建并操作 Users 集合

```java
@Test
public void createAndManipulateCollectionOfUsers() {
    Collection<User> someUsers = new ArrayList<>();
    assertEquals(0, someUsers.size());

    User bob = new User("bob", "Password");
    User eris = new User("eris", "ChaosTime");

    someUsers.add(bob);
    assertEquals(1, someUsers.size());

    someUsers.add(eris);
    assertEquals(2, someUsers.size());

    someUsers.clear();
    assertEquals(0, someUsers.size());
}
```

### 创建并操作 Users List

```java
@Test
public void createAndManipulateListOf() {
    List<User> someUsers = new ArrayList<>();
    assertEquals(0, someUsers.size());

    User bob = new User("bob", "Password");
    User eris = new User("eris", "ChaosTime");

    someUsers.add(bob);
    assertEquals(1, someUsers.size());

    someUsers.add(eris);
    assertEquals(2, someUsers.size());

    someUsers.remove(0);
    assertEquals(1, someUsers.size());
}
```

### 创建并操作 Users Set

```java
@Test
public void createAndManipulateASetOfUsers() {
    Set<User> someUsers = new HashSet<>();
    assertEquals(0, someUsers.size());

    User bob = new User("bob", "Password");
    someUsers.add(bob);
    assertEquals(1, someUsers.size());

    someUsers.add(bob); // 重复
    assertEquals(1, someUsers.size());
}
```

### 创建并操作 Users Map

```java
@Test
public void createAndManipulateAMapOfUsers() {
    Map<String, User> someUsers = new HashMap<>();
    assertEquals(0, someUsers.size());

    User bob = new User("bob", "Password");
    User eris = new User("eris", "ChaosTime");

    someUsers.put(bob.getUsername(), bob);
    assertEquals(1, someUsers.size());

    someUsers.put(eris.getUsername(), eris);
    assertEquals(2, someUsers.size());
}
```

## 第十一章 - 引入异常

### 修复代码中的空指针异常

我只需要获取该章节早些列出的代码，并在尝试访问它之前将 18 赋值给 `age` 变量。

```java
@Test
public void noLongerThrowNullPointerException() {
    Integer age = 18;
    String ageAsString = age.toString();
    String yourAge = "You are " + ageAsString + " years old";
    assertEquals("You are 18 years old", yourAge);
}
```

未初始变量和参数是异常的常见来源。

### 使用不同的异常代替 NullPointerException

当我将 `NullPointerException` 替换为 `ArithmeticException` 时。抛出 `NullPointerException` 是因为没有代码来捕获它。

```java
@Test(expected = NullPointerException.class)
public void catchDifferentException() {
    Integer age = null;
    String ageAsString;

    try {
        ageAsString = age.toString();
    } catch(ArithmeticException e) {
        age = 18;
        ageAsString = age.toString();
    }

    String yourAge = "You are " + age.toString() + " years old";
    assertEquals("You are 18 years old", yourAge);
}
```

你可以看到我使用了 `expected` 参数来检查由 `@Test` 方法抛出的此异常。

### 不修复异常产生

当我从 `catch` 块中移除 `age = 18;` 语句并运行代码时。代码抛出了 `NullPointerException`，因为我们没有在 `catch` 块内部添加 `try` 块。



```java
@Test(expected = NullPointerException.class)
public void testNotFixedStillThrowsNullPointer() {
    Integer age = null;
    String ageAsString;

    try {
        ageAsString = age.toString();
    } catch (ArithmeticException e) {
        // age = 18;
        ageAsString = age.toString();
    }

    String yourAge = "You are " + age.toString() + " years old";
    assertEquals("You are 18 years old", yourAge);
}
```

# 捕获检查异常

当我用 `NoSuchMethodException` 代替 `NullPointerException` 时，我收到了语法错误。

```java
@Test
public void thisTriggersSyntaxErrorBecauseExceptionIsNotDeclared() {
    Integer age = null;
    String ageString;

    try {
        ageString = age.toString();
    } catch (NoSuchMethodException e) {
        age = 18;
        ageString = age.toString();
    }

    String yourAge = "You are " + age.toString() + " years old";

    assertEquals("You are 18 years old", yourAge);
}
```

我在 `NoSuchMethodException` 这一行收到了语法错误：

```java
catch (NoSuchMethodException e) {
```

`NoSuchMethodException` 是一个检查异常，需要在方法中进行声明。`toString` 方法没有声明它会抛出 `NoSuchMethodException`，所以我收到了语法错误。`NullPointerException` 和 `ArithmeticException` 是未检查异常，不需要在方法中声明。

# 将异常作为对象

当我向代码中添加为了使用异常的方法时：

```java
@Test
public void useExceptionAsObject() {
    Integer age = null;
    String ageString;

    try {
        ageString = age.toString();
    } catch (NullPointerException e) {
        System.out.println("GetMessage - " + e.getMessage());
        System.out.println("GetStackTrace - " + e.getStackTrace());
        e.printStackTrace();
    }
}
```

我收到了以下输出，为了节省空间：

```
getMessage - null
getStackTrace - [java.lang.StackTraceElement;@4ea369a
printStackTrace
at exercises.IntroducingExceptionsTest.useExceptionAsObject(IntroducingExceptionsTest.java:99)
at java.reflect.Method.invoke(Method.java:60)
at execution.AppMain.main(AppMain.java:120)
```

在这种情况中，`NullPointer` 异常没有返回消息，所以我们需要使用堆栈来找出发生了什么。其他异常会返回消息，当你创建自己的异常时，这让其他人更容易理解问题。`getStackTrace` 是 `StackTrace` 对象的数组，我可以访问它来查找堆栈的某部分，例如：

- `ClassName`
- `FileName`
- `LineNumber`
- `MethodName`

```java
System.out.println("Stack Trace - " + e.getStackTrace().length);
System.out.println("Stack Trace [0] className - " + e.getStackTrace()[0].getClassName());
System.out.println("Stack Trace [0] filename - " + e.getStackTrace()[0].getFileName());
System.out.println("Stack Trace [0] linenumber - " + e.getStackTrace()[0].getLineNumber());
System.out.println("Stack Trace [0] methodname - " + e.getStackTrace()[0].getMethodName());
```

将会显示：

```
Stack Trace - 27
Stack Trace [0] className com.javafortesters.exceptions.IntroducingExceptionsTest
Stack Trace [0] filename IntroducingExceptionsTest.java
Stack Trace [0] linenumber - 100
Stack Trace [0] methodname useExceptionAsObject
```

关于 `StackTraceElement` 的更多信息，你可以阅读官方文档：

- [docs.oracle.com/java/7/docs/api/java/lang/StackTraceElement.html](https://docs.oracle.com/java/7/docs/api/java/lang/StackTraceElement.html)

# 第十二章 - 引入继承

# 创建一个由 TestApp 组成的类

我有多种方法来实现。我可以：

- 在我的 `User` 对象内部创建一个 `TestApp` 对象，
- 在我的 `User` 对象内部静态地复用 `TestApp`
- 创建一个继承 `User` 并使用 `TestApp` 的新 `EnvironmentUser` 对象

# 在 User 对象内部创建一个 TestAppEnv 对象

要在我的 `User` 对象内部创建一个 `TestAppEnv` 对象，我可以：

- 添加一个新的 `TestAppEnv` 字段，
- 在构造函数中实例化对象，
- 在对象上实现一个 `getUrl` 方法。

```java
public class User {
    private String username;
    private String password;
    private TestAppEnv testAppEnv;

    public User() {
        this("username", "password");
    }

    public User(String username, String password) {
        this.username = username;
        this.password = password;
        this.testAppEnv = new TestAppEnv();
    }

    public String getUsername() {
        return username;
    }

    public String getPassword() {
        return password;
    }

    public void setPassword(String password) {
        this.password = password;
    }

    public String getUrl() {
        return this.testAppEnv.getUrl();
    }
}
```

# 在 User 对象内部静态复用 TestAppEnv

由于 `TestAppEnv` 最初设计为用于静态访问，我不需要声明字段或实例化对象，我只需要：

- 为 `User` 添加一个 `getUrl` 方法
- 委托给 `TestAppEnv` 上的静态方法

```java
public String getUrl() {
    return TestAppEnv.getUrl();
}
```

# 创建一个新的 EnvironmentUser

由于 `EnvironmentUser` 是 `user` 的特殊情况，我完全不需要修改 `User` 对象。我创建一个名为 `EnvironmentUser` 的新对象并继承 `User`，然后给 `EnvironmentUser` 添加一个静态使用 `TestAppEnv` 对象的方法。

```java
package com.javafortesters.chap012inheritance.exercises;

import com.javafortesters.domainidentities.User;
import com.javafortesters.domainobject.TestAppEnv;

public class EnvironmentUser extends User {

    public String getUrl() {
        return TestAppEnv.getUrl();
    }
}
```

我将如下在 `@Test` 方法中使用它：

```java
@Test
public void createEnvironmentUser() {
    EnvironmentUser enuser = new EnvironmentUser();

    assertEquals("username", enuser.getUsername());
    assertEquals("http://192.123", enuser.getUrl());
}
```

# 创建 ReadOnlyUser

为了创建 `ReadOnlyUser`，我使用一个 `@Test` 方法来检查默认值。

```java
@Test
public void readOnlyUserAndDefaults() {
    ReadOnlyUser rod = new ReadOnlyUser();
    assertEquals("username", rod.getUsername());
    assertEquals("password", rod.getPassword());
}
```

然后我实现了 `ReadOnlyUser`。这是一个继承 `User` 的简单类，并实现了 `getPermission`。

```java
package com.javafortesters.chap012inheritance.exercises;
import com.javafortesters.domainidentities.User;

public class ReadOnlyUser extends User {

    @Override
    public String getPermission() {
        return "ReadOnly";
    }
}
```

# 第十三章 - 更多异常

# 创建 InvalidPassword 异常

“帮助”用户使用 `user` 对象是为了提醒他们可能遇到的验证和异常。我们可以通过文档来实现，也可以通过自定义异常来实现。

通过创建 `InvalidPassword` 异常，我们提醒用户设置密码时的验证规则。

正如你在类中所看到的，我创建了一个带有 `InvalidPassword` 代码的代码：

```java
public class InvalidPassword extends Exception {
    public InvalidPassword(String message) {
        super(message);
    }
}
```

在我的类中，让 `setPassword` 方法在通过长度检查时抛出 `InvalidPassword`：

```java
public void setPassword(String password) throws InvalidPassword {
    if (password.length() < 7) {
        throw new InvalidPassword("Password must be > 6 chars");
    }

    this.password = password;
}
```

你可以从代码中看到我向 `InvalidPassword` 异常传递了一个消息，用来描述抛出异常的情况。

为了检查所有这些，我创建一个带有 `@Test` 方法的类，将检查：

- 构造函数中抛出了 `InvalidPassword`
- 默认构造函数没有抛出 `InvalidPassword`
- 抛出的异常错误消息包含“Password must be > 6 chars”文本
- `setPassword` 方法上抛出了 `InvalidPassword`

为了检查构造函数中是否抛出了 `InvalidPassword`，我使用 `expected` 参数来检查异常。由于该异常是检查异常，我必须在方法声明中添加 `throws` 关键字：

```java
@Test(expected = InvalidPassword.class)
public void createUserWithException() throws InvalidPassword {
    User aUser = new User("username", "password");
}
```

为了检查构造函数没有抛出异常，我所只需创建用户并断言密码已创建。

```java
@Test
public void createDefaultUserWithNoThrowsInvalidPasswordException() {
    User aUser = new User();
    assertEquals("password", aUser.getPassword());
}
```

我的思路如下：

- 由于该异常是受检异常（Checked Exception），如果抛出异常，我无法编写代码，因为我必须添加 `try catch` 块或在方法签名中添加 `throws` 声明。
- 我断言 `User` 被正确创建，因为如果创建失败，断言就会失败。
- 如果抛出了异常，`@Test` 方法将失败。

为了检查错误消息，我尝试捕获（catch）异常，然后检查错误消息：

```java
@Test
public void createUserWithInvalidPasswordMessages() {
    User aUser;

    try {
        aUser = new User("username", "p");
        fail("An Invalid Password Exception should have been thrown");
    } catch (InvalidPassword e) {
        assertTrue(e.getMessage().startsWith("Password must be > 6 chars"));
    }
}
```

注意上面的代码，我在 `try` 块中添加了一个 `fail` 语句：

- 我这样做是因为异常本应该被抛出，而这个 `fail` 语句永远不应该被执行。
- 如果执行了 `fail` 语句，说明异常没有抛出，我需要强制 `@Test` 失败。
- 如果我没有添加 `fail` 语句且没有抛出异常，那么 `@Test` 方法将通过，但原因是错误的。

我还确保确保了 `setPassword` 方法会抛出异常。

```java
@Test
public void setPasswordWithInvalidPasswordExceptionMessages() {
    User aUser = new User();

    try {
        aUser.setPassword("tiny");
        fail("An Invalid Password Exception should have been thrown");
    } catch (InvalidPassword e) {
        assertTrue(e.getMessage().startsWith("Password must be > 6 chars"));
    }
}
```

为了实现这一点，我使用默认构造函数创建了 `User`，因为我知道它不会抛出异常。然后用 `try catch` 包装住 `setPassword`。我在 `catch` 块中重复了该断言。注意我同样添加了 `fail` 语句。

这个练习是说明为什么 `fail` 语句如此重要的很好的例子。如果没有 `fail`，我的 `@Test` 方法可能会因为没有抛出异常而通过。

# 第十四章 - JUnit 详解

## 创建一个使用所有断言的 @Test 方法



# 第十四章 - JUnit 详解

## 创建一个使用所有断言的 @Test 方法

```java
@Test
public void junitAssertions(){
    assertEquals(6, 3 + 3);
    assertEquals("3 + 3 = 6", 6, 3 + 3);

    assertFalse("false is false", false);
    assertFalse(false);

    assertTrue("true is true", true);
    assertTrue(true);

    int[] oneToTen = {1,2,3,4,5,6,7,8,9,10};
    int[] tenToOne = {10,9,8,7,6,5,4,3,2,1};
    Arrays.sort(tenToOne);
    assertEquals(oneToTen, tenToOne);

    assertNull("An empty string is not null", "");
    assertNull(null);

    assertNotSame("An empty string is not null", null, "");
    assertNotSame(null, "");

    assertNull("Only null is null", null);
    assertNull(null);

    assertSame("Only null is null", null, null);
    assertSame(null, null);
}
```

## 使用 assertThat 重现所有的 JUnit 断言

```java
@Test
public void assertThatWithHamcrestMatchers(){
    assertThat(3 + 3, is(6));
    assertThat("3 + 3 = 6", 3 + 3, is(6));

    assertThat("false is false", false, equalTo(false));
    assertThat(false, is(false));

    assertThat("true is true", true, equalTo(true));
    assertThat(true, is(true));

    int[] oneToTen = {1,2,3,4,5,6,7,8,9,10};
    int[] tenToOne = {10,9,8,7,6,5,4,3,2,1};
    Arrays.sort(tenToOne);
    assertThat(oneToTen, equalTo(tenToOne));

    assertThat("An empty string is not null", "");
    is(not(nullValue)));
    assertThat("", is(not(nullValue)));
}
```

```java
assertThat("", is(notNullValue()));

assertThat("null is null", null, is(nullValue()));
assertThat(null, nullValue());
```

## 使用 Hamcrest 匹配器

```java
@Test
public void useTheHamcrestMatchers() {

    assertThat(3, is(equalTo(3)));
    assertThat(3, is(not(4)));
    assertThat("This is a string", containsString("is"));
    assertThat("This is a string", startsWith("is"));

}
```

# 第十五章 - 重新回顾字符串

## 尝试使用转义字符

```java
@Test
public void tryUsingEscapeCharactersOutput() {
    System.out.println("New lines, and Tabs");
    String firstLine = "first line\n";
    String secondLine = "\tsecond line\n";
    String thirdLine = "\\third line\n";
    String fullLine = firstLine + secondLine;
    System.out.println(fullLine);

    System.out.println("Carriage return after each word");
    System.out.println("one\rtwo\rthree\rfive");

    System.out.println("Backspace after each word");
    System.out.println("one\btwo\bthree\bfive");

    System.out.println("quotes and slashes");
    System.out.println("Bob's toy said\\\"");
}
```

在输出到控制台时，你可能注意不到某些字符，例如 `\r` 和 `\b`。有时当你向控制台输出时，由于缓冲和刷新到控制台的原因，你看到的并不是完全预期的。

为了实现这一点，我使用默认构造函数创建了 `User`，因为我知道它不会抛出异常。然后用 `try catch` 包装住 `setPassword`。我在 `catch` 块中重复了该断言。注意我同样添加了 `fail` 语句。

这个练习是说明为什么 `fail` 语句如此重要的很好的例子。如果没有 `fail`，我的 `@Test` 方法可能会因为没有抛出异常而通过。




# 第十五章 - 重新回顾字符串

## 尝试使用转义字符

```java
@Test
public void tryUsingEscapeCharactersOutput() {
    System.out.println("New lines, and Tabs");
    String firstLine = "first line\n";
    String secondLine = "\tsecond line\n";
    String thirdLine = "\\third line\n";
    String fullLine = firstLine + secondLine;
    System.out.println(fullLine);

    System.out.println("Carriage return after each word");
    System.out.println("one\rtwo\rthree\rfive");

    System.out.println("Backspace after each word");
    System.out.println("one\btwo\bthree\bfive");

    System.out.println("quotes and slashes");
    System.out.println("Bob's toy said\\\"");
}
```

在输出到控制台时，你可能注意不到某些字符，例如 `\r` 和 `\b`。有时当你向控制台输出时，由于缓冲和刷新到控制台的原因，你看到的并不是完全预期的。

为了实现这一点，我使用默认构造函数创建了 `User`，因为我知道它不会抛出异常。然后用 `try catch` 包装住 `setPassword`。我在 `catch` 块中重复了该断言。注意我同样添加了 `fail` 语句。

这个练习是说明为什么 `fail` 语句如此重要的很好的例子。如果没有 `fail`，我的 `@Test` 方法可能会因为没有抛出异常而通过。

## 使用 regionMatches

```java
@Test
public void useRegionMatches() {
  User aUser = new User();

  try {
    aUser.setPassword("tiny");
    fail("An Invalid Password Exception should have been thrown");
  } catch (InvalidPassword e) {
    assertTrue(e.getMessage().startsWith("Password must be > 6 chars"));
  }
}
```

## 在字符串中使用 indexOf 查找所有出现的位置

```java
private List<Integer> findAllOccurrences(String string, 
  String substring) {

  List<Integer> results = new ArrayList<>();

  // 设置搜索从字符串的开始
  int lastfoundPosition = 0;
  // 使用循环查找
  do {
    // 尝试从当前位置开始查找子字符串
    lastfoundPosition = string.indexOf(substring, lastfoundPosition);

    // 如果我们找到了
    if(lastfoundPosition!=-1){
      // 将添加到结果列表中
      results.add(lastfoundPosition);

      // 下次搜索从该索引之后开始
      lastfoundPosition++;
    }
  } while(lastfoundPosition!=-1 && lastfoundPosition < string.length());
  return results;
}
```

这样一来，如果我由于原因以错误的顺序执行了它们，只有 `.get` 会失败。但如果我未能产生出现项，那么 `contains` 就会失败。

同时使用 `contains` 和 `get` 似乎是多余的，但我认为通过这个 `@Test` 方法可能会在我未来重构代码并以某种方式弄错返回值的顺序时对我有所帮助。

写完上述代码后，我尝试思考该方法可能预期处理的其他参数，并编写了“压力”该方法的 `@Test` 方法。

这些帮助我添加了参数代码。

```java
@Test
public void worksWhenNothingToFind() {
    List<Integer> results;
    results = findAllOccurrences("Hello fella", "z");
    assertThat(results.size(), is(0));

    results = findAllOccurrences("", "z");
    assertThat(results.size(), is(0));
}
```

```java
@Test(expected = IllegalArgumentException.class)
public void cannotSearchForEmpty() {
    List<Integer> results = findAllOccurrences("", "");
}
```

```java
@Test(expected = IllegalArgumentException.class)
public void cannotSearchForNullString() {
    List<Integer> results = findAllOccurrences(null, "hello");
}
```

```java
@Test(expected = IllegalArgumentException.class)
public void cannotSearchForNullSubstring() {
    List<Integer> results = findAllOccurrences("hello", null);
}
```

```java
@Test(expected = IllegalArgumentException.class)
public void cannotSearchForNulls() {
    List<Integer> results = findAllOccurrences(null, null);
}
```

## 使用 lastIndexOf

为了反转列表，我依赖了 `lastIndexOf` 方法。

我使用的主要的 `@Test` 方法是：

```java
@Test
public void findAllOccurrencesStringUsingLastIndexOf() {
    List<Integer> results;
    results = findAllOccurrences("Hello fella", "1");

    assertThat(results.contains(2), is(true));
    assertThat(results.contains(3), is(true));
    assertThat(results.contains(8), is(true));
    assertThat(results.contains(9), is(true));
}
```

```java
assertThat(results.get(0), is(9));
assertThat(results.get(1), is(8));
assertThat(results.get(2), is(3));
assertThat(results.get(3), is(2));
}
```

我没有包含用于检查此方法的额外方法，但它们与用于 `indexOf` 方案的方法相同。

```java
private List<Integer> findAllOccurrences(String string, String substring) {
    List<Integer> results = new ArrayList<Integer>();

    if(string==null || substring==null){
        throw new IllegalArgumentException("Cannot search for null");
    }

    if(substring.isEmpty()) {
        throw new IllegalArgumentException("Cannot search for Empty substring");
    }

    // 将搜索位置设置为字符串开头
    int lastPosition = string.length();

    do{
        // 尝试查找字符串
        lastPosition = string.lastIndexOf(substring);

        // 如果找到了
        if(lastPosition!=-1){
            // 将其添加到结果中
            results.add(lastPosition);
            // 下下一个起始位置在此索引之前
            lastPosition--;
        } // 继续查找直到找不到为止
    } while(lastPosition!=-1);

    return results;
}
```

## 用于用户 setPassword 的正则表达式

```java
public void setPassword(String password) throws InvalidPassword {
    if(password.length()<7){
        throw new InvalidPassword("Password must be > 6 chars");
    }

    if(!password.matches(".*[0123456789]+.*")) {
        throw new InvalidPassword("Password must have a digit");
    }
}
```

```java
if(!password.matches(".*[A-Z].*")) {
    throw new InvalidPassword("Password must have an Uppercase Letter");
}

this.password = password;
}
```

当然我必须修改默认构造函数，否则验证会失败：

```java
public User() {
    this("username", false);
}
```

由于默认密码需要更改，我修改了该类。

## 检查 StringBuilder 扩容

```java
@Test
public void capacityIncreasesWithAppend() {
    StringBuilder builder = new StringBuilder(5);
    assertThat(builder.capacity(), is(5));
    builder.append("Hello World");
}
```

## 插入到 StringBuilder

```java
@Test
public void testInsert() {
    StringBuilder builder = new StringBuilder();

    // 插入开头
    builder.insert(0, "a");
    assertThat(builder.toString(), is("a"));

    // 插入末尾
    builder.insert(builder.length(), "b");
    assertThat(builder.toString(), is("ab"));

    // 插入中间
    builder.insert(1, "b");
    assertThat(builder.toString(), is("abb"));

}
```

# 第十六章 - 随机数据

创建基础的 `@Test` 方法如下：

```java
@Test
public void generateInt() {
    Random generate = new Random();
    int randomInt = generate.nextInt();
    System.out.println(randomInt);
    assertThat(randomInt<Integer.MAX_VALUE, is(true));
    assertThat(randomInt>=Integer.MIN_VALUE, is(true));
}
```

其他方法都采用相同的形式，只是随机生成的不同。对于布尔检查，我统计了 true 和 false 的值以确保两者都生成了：

```java
@Test
public void canGenerateBoolean() {
    Random generate = new Random();
    int countTrue = 0;
    int countFalse = 0;
    for(int x=0; x<1000; x++) {
        boolean randomBoolean = generate.nextBoolean();
        if(randomBoolean)
            countTrue++;
        if(randomBoolean==false)
            countFalse++;
        System.out.println(randomBoolean);
    }
    System.out.println(String.format("%d as true", countTrue));
    System.out.println(String.format("%d as false", countFalse));
    assertThat(countTrue>0, is(true));
    assertThat(countFalse>=0, is(true));
    assertThat(countTrue + countFalse, is(1000));
}
```

由于所有 `@test` 方法的形式相同，我没有包含下面的完整代码，只包含了随机生成和断言部分。

## 检查 Long

```java
long randomLong = generate.nextLong();
System.out.println(randomLong);
assertThat(randomLong<Long.MAX_VALUE, is(true));
assertThat(randomLong>=Long.MIN_VALUE, is(true));
```

注意 `next` 的文档报告算法将返回所有值。

## 检查 Float

```java
float randomFloat = generate.nextFloat();
System.out.println(randomFloat);
assertThat(randomFloat<=1.0f, is(true));
assertThat(randomFloat>=0.0f, is(true));
```



注意上限检查是不包含的（`<`），下限检查是包含的（`>=`）。

## 检查 Double

```java
double randomDouble = generate.nextDouble();
System.out.println(randomDouble);
assertThat(randomDouble <= 1.0d, is(true));
assertThat(randomDouble >= 0.0d, is(true));
```

注意上限检查是不包含的（`<`），下限检查是包含的（`>=`）。

## 检查 Byte

```java
// 生成长度在 0 到 99 之间的字节数组
int arrayLength = generate.nextInt(100);
byte[] bytes = new byte[arrayLength]; // 填充随机数据
generate.nextBytes(bytes);
Assert.assertEquals(arrayLength, bytes.length);
String values = new String(bytes);
System.out.println(bytes.length + " - " + bytes);
```

注意我生成了字节数组的大小。

## 检查 Int 范围

```java
int randomIntRange = generate.nextInt(12);
System.out.println(randomIntRange);
assertThat(randomIntRange <= 11, is(true));
assertThat(randomIntRange >= 0, is(true));
```

注意我生成的是 12 以下的，所以我的断言是从 0 到 11 包含。

## 创建在 15 到 20 之间包含生成 1000 个数字的 @Test 方法

```java
@Test
public void generateRandomIntGivenRange() {
    Random generate = new Random();

    int minValue = 1;
    int maxValue = 5;
    int randomIntRange = generate.nextInt(
        maxValue - minValue + 1) + minValue;

    assertThat(randomIntRange <= maxValue, is(true));
    assertThat(randomIntRange >= minValue, is(true));
}
```

在上述代码中，我循环大约 1000 次，以确保我不是只是碰巧了一个通过断言的幸运数字。我将生成的存储在 `set` 中：

- 这防止了重复，因此每个生成的数字只会出现一次
- 这意味着 `set` 的大小就是生成的不同整数的数量

我对集合的大小进行了断言，因为我知道应该生成 6 个数字。

我断言每个数字（15, 16, 17, 18, 19, 20）都已经被生成。

## 编写一个显示分布的 @Test 方法

```java
@Test
public void canGenerateRandomGaussianDistributionDouble() {
    Random generate = new Random();

    int standardDeviationCount1 = 0;
    int standardDeviationCount2 = 0;
    int standardDeviationCount3 = 0;
    int standardDeviationCount4 = 0;

    for (int x = 0; x < 1000; x++) {
        double randomGaussian = generate.nextGaussian();
        System.out.println(randomGaussian > -1.0d && randomGaussian < 1.0d);
        standardDeviationCount1++;

        if (randomGaussian > -2.0d && randomGaussian < 2.0d)
            standardDeviationCount2++;

        if (randomGaussian > -3.0d && randomGaussian < 3.0d)
            standardDeviationCount3++;

        if (randomGaussian > -4.0d && randomGaussian < 4.0d)
            standardDeviationCount4++;
    }

    float sd1percentage = (standardDeviationCount1 / 1000f) * 100f;
    System.out.println("about 70% one standard deviation = " + sd1percentage);

    float sd2percentage = (standardDeviationCount2 / 1000f) * 100f;
    System.out.println("about 95% two standard deviation = " + sd2percentage);

    float sd3percentage = (standardDeviationCount3 / 1000f) * 100f;
    System.out.println("about 99% three standard deviation = " + sd3percentage);

    float sd4percentage = (standardDeviationCount4 / 1000f) * 100f;
    System.out.println("about 99.9% four standard deviation = " + sd4percentage);

    Assert.assertTrue(sd1percentage < sd2percentage);
    Assert.assertTrue(sd2percentage < sd3percentage);
    // I do not assert that sd3 and sd4 are different
    // because of the small % difference, they do overlap
}
```

## 编写一个使用 nextGaussian() 生成 1000 个年龄的 @Test 方法

```java
@Test
public void canGenerate1000AgesUsingDeviation() {
    Random generate = new Random();
    Map<Integer, Integer> ages =
        new HashMap<Integer, Integer>();

    for (int x = 0; x < 1000; x++) {
        int age = (int) (generate.nextGaussian() * 5 + 35);
        int count = 0;
        if (ages.containsKey(age)) {
            count = ages.get(age);
        }
        count++;
        ages.put(age, count);
    }

    SortedSet<Integer> agesSorted = new TreeSet<>(ages.keySet());

    for (int age : agesSorted) {
        System.out.println(age + " : " + ages.get(age));
    }
}
```

## 创建一个带有种子的 @Test 方法

```java
@Test
public void generateRandomNumbersWithSeed() {
    for (int x = 0; x < 10; x++) {
        Random generate = new Random(1234567L);

        assert(generate.nextInt(), is(1042961893));
        assert(generate.nextLong(), is(-6749250865724112022L));
        assert(generate.nextDouble(), is(0.4476832574617084D));
        assert(generate.nextGaussian(), is(-0.11571220827310763D));
        assert(generate.nextFloat(), is(0.3314418F));
        assert(generate.nextBoolean(), is(false));
    }
}
```

为了识别我需要断言的值，首先为每一行代码创建一个 `System.out.println`，然后使用输出到控制台的值作为断言依据。

## 生成一个长度为 10 字符的随机字符串

```java
@Test
public void generateRandomString() {
    String validValues = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
    StringBuilder rString;

    Random random = new Random();

    rString = new StringBuilder();
    for (int x = 0; x < 100; x++) {
        int rndIndex = random.nextInt(validValues.length());
        char rChar = validValues.charAt(rndIndex);
        rString.append(rChar);
    }
    System.out.println(rString);
    Assert.assertTrue(rString.length() == 10);
    Assert.assertTrue(rString.toString().matches("[A-Z]+"));
}
```

也使用 `StringBuilder` 通过追加每个生成的字符来构建字符串。

# 第十七 - 日期与时间

## 使用 nanoTime 重写计时方法

```java
@Test
public void nanoTime() {
    long startTime = System.nanoTime();
    for (int x = 0; x < 10; x++) {
        System.out.println("Current Time " + System.nanoTime());
    }
    long endTime = System.nanoTime();
    System.out.println("Total Time " + (endTime));
}
```

## 使用 currentTimeMillis 创建带有数字的唯一名称

有很多实现这种方法。

```java
@Test
public void createUserIDAllChars() {
    String initialUserID = "user" + System.currentTimeMillis();
    System.out.println(initialUserID);
    String userID = initialUserID;
    for (int x = 0; x < 10; x++) {
        String charReplacement = "" + (char) ('A' + x);
        String intToReplace = String.valueOf(x);
        userID = userID.replace(intToReplace, charReplacement);
    }
    assert(userID.contains("0"), isFalse);
    assert(userID.contains("1"), isFalse);
    assert(userID.contains("2"), isFalse);
    assert(userID.contains("3"), isFalse);
    assert(userID.contains("4"), isFalse);
    assert(userID.contains("5"), isFalse);
    assert(userID.contains("6"), isFalse);
    assert(userID.contains("7"), isFalse);
    assert(userID.contains("8"), isFalse);
    assert(userID.contains("9"), isFalse);
    assertThat(initialUserID.length(), is(userID.length()));
    System.out.println(userID);
}
```

- 第 10 行 - 我利用 `'A'` (`char`) 可以加上整数来获取新字符，然后将其与空字符串拼接创建一个数字字符串。
- 第 11 行 - 我将 `int` 转换为 `String`
- 第 12 行 - 我将字符串中的所有整数替换为该计算出的字符，`'A' + 0` 等于 `'A'`，我会替换字符串中的所有 0
- `'A' + 1` 等于 `'B'`，我会替换字符串中的所有 1
- 等此类推。

剩余的代码包含了检查没有数字的断言。

## 将 toString 写入控制台

```java
@Test
public void writeToStringConsole() {
    Calendar cal = Calendar.getInstance();
    System.out.println(cal.toString());
}
```

## 使用其他的 Calendar 常量

```java
@Test
public void useOtherConstants() {
    Calendar cal = Calendar.getInstance();

    cal.set(2013, Calendar.DECEMBER, 15, 23, 54);
    assertThat(cal.get(Calendar.MONTH), is(Calendar.DECEMBER));
    assertThat(cal.get(Calendar.YEAR), is(2013));
    assertThat(cal.get(Calendar.DAY_OF_MONTH), is(15));
    assertThat(cal.get(Calendar.HOUR_OF_DAY), is(23));
    assertThat(cal.get(Calendar.MINUTE), is(39));
    assertThat(cal.get(Calendar.HOUR), is(11));
    assertThat(cal.get(Calendar.AM_PM), is(Calendar.PM));
}
```

## 使用其他常量实验

```java
@Test
public void experimentWithCalendarConstants() {
    Calendar cal = Calendar.getInstance();
    cal.set(2013, Calendar.DECEMBER, 15, 23, 39, 54);

    assertThat(cal.get(Calendar.DAY_OF_WEEK), is(1));
    assertThat(cal.get(Calendar.DAY_OF_WEEK), is(Calendar.SUNDAY));
    assertThat(cal.get(Calendar.WEEK_OF_MONTH), is(2));
    assertThat(cal.get(Calendar.WEEK_OF_YEAR), is(50));
    assertThat(cal.get(Calendar.DAY_OF_YEAR), is(34));
}
```

![](img/3571bcaadac596bb801bc317a52cb1e_279_0.png)

## 增加和减少其他字段



```java
@Test
public void incrementDecrementOtherFields() {
    Calendar cal = Calendar.getInstance();
    cal.set(2013, Calendar.DECEMBER, 15, 23, 39, 54);

    cal.add(Calendar.YEAR, -2);
    cal.add(Calendar.MONTH, -6);
    cal.add(Calendar.DAY_OF_MONTH, -12);

    assertThat(cal.get(Calendar.YEAR), is(2011));
    assertThat(cal.get(Calendar.MONTH), is(Calendar.JUNE));
    assertThat(cal.get(Calendar.DAY_OF_MONTH), is(3));

    cal.set(2013, Calendar.DECEMBER, 15, 23, 39, 54);

    // 将其推到 2014 年 6 月 3 日，
    // 然后将其拉回
    cal.add(Calendar.DAY_OF_MONTH, 19);
    cal.add(Calendar.MONTH, 5);
    cal.add(Calendar.YEAR, -3);
}
```

确认 `roll` 添加了年份

```java
@Test
public void rollCalendar() {
    Calendar cal = Calendar.getInstance();
    cal.set(2013, Calendar.DECEMBER, 15, 23, 39, 54);

    cal.roll(Calendar.DAY_OF_MONTH, 17);

    assertThat(cal.get(Calendar.YEAR), is(2013));
    assertThat(cal.get(Calendar.MONTH), is(Calendar.DECEMBER));
    assertThat(cal.get(Calendar.DAY_OF_MONTH), is(1));

    cal.set(2013, Calendar.DECEMBER, 15, 23, 39, 54);

    cal.add(Calendar.DAY_OF_MONTH, 17);
    assertThat(cal.get(Calendar.YEAR), is(2014));
    assertThat(cal.get(Calendar.MONTH), is(Calendar.JANUARY));
    assertThat(cal.get(Calendar.DAY_OF_MONTH), is(1));
}
```

```java
properties.setProperty("password", "passSword");
assertThat(properties.getPropertyNames().size(), is(3));

for (String key : properties.getPropertyNames()) {
    System.out.println("Key: " + key + " = " +
            "Value: " + properties.getProperty(key));
}

properties.list(System.out);

Assert.assertTrue(properties.containsKey("gender"));
Assert.assertEquals("bob", properties.getProperty("name"));
Assert.assertEquals("Admin",
        properties.getProperty("permission"), "Admin");
```

# 存储和加载保存的属性

```java
@Test
public void canSaveAndLoadPropertiesFile() throws IOException {

    String tempDirectory = System.getProperty("java.io.tmpdir");
    String tempResourceFilePath = tempDirectory +
            System.currentTimeMillis() +
            System.nanoTime() +
            ".properties";

    Properties saved = new Properties();

    long nanoTime = System.nanoTime();
    long millis = System.currentTimeMillis();
    saved.setProperty("nanoTime", String.valueOf(nanoTime));
    saved.setProperty("millis", String.valueOf(millis));

    FileOutputStream outputFile = new FileOutputStream(tempResourceFilePath);
    saved.store(outputFile, "Time Data When File Written");
    outputFile.close();

    FileReader propertyReader = new FileReader(tempResourceFilePath);
    Properties loaded = new Properties();

    try {
        loaded.load(propertyReader);
    } finally {
        propertyReader.close();
    }

    assertThat(loaded.getProperty("nanoTime"),
            is(String.valueOf(nanoTime)));
    assertThat(loaded.getProperty("millis"),
            is(String.valueOf(millis)));

    new File(tempResourceFilePath).delete();
}
```

# 第十九章 - 文件

## 创建临时文件并改变参数

```java
@Test
public void createTempFileVaryParameters() throws IOException {
    // 在 Windows 上，这些文件位于 %TEMP%
    File temp1 = File.createTempFile("temp1", null);
    File temp2 = File.createTempFile("temp2OutFile", ".out");

    assertThat(temp1.exists(), is(true));
    assertThat(temp2.exists(), is(true));

    temp1.deleteOnExit();
    temp2.deleteOnExit();
}
```

你可以看到我使用了 `exists()` 方法来检查是否存在，并使用 `deleteOnExit()` 在执行完成后删除创建的临时文件。

但注意，如果执行过程中发生错误并抛出异常，文件可能没有被删除。在处理文件时，我真的应该使用 `try/finally` 块。

```java
@Test
public void writeOutOutputFileRoots() {
    File[] roots = File.listRoots();
    assertThat(roots.length > 0, is(true));

    for (File file : roots) {
        System.out.println(file.getAbsolutePath());
    }
}
```

## 使用自定义代码创建临时文件

```java
@Test
public void createTempFileWithCustomCode() throws IOException {
    String directory = System.getProperty("java.io.tmpdir");
    String fileName = "prefix" + System.currentTimeMillis() + ".tmp";

    File tempFile = new File(directory, fileName);
    assertThat(tempFile.exists(), is(false));

    tempFile.createNewFile();
    assertThat(tempFile.exists(), is(true));

    tempFile.delete();
    assertThat(tempFile.exists(), is(false));
}
```

## 编写一个 Test 方法来检查规范化转换

```java
@Test
public void writeATestToCheckCanonicalConversion() throws IOException {
    File absolute1 = new File("C:1/2/3/4/../...");
    File absolute2 = new File("C:1/2/../1");
    File canonical = new File("C:1/");

    assertThat(canonical.getAbsolutePath(),
            is(canonical.getCanonicalPath()));
    assertThat(absolute1.getAbsolutePath(),
            is(absolute1.getCanonicalPath()));
    assertThat(absolute2.getAbsolutePath(),
            is(absolute2.getCanonicalPath()));

    assertThat(absolute1.getAbsolutePath().contains("..."), is(true));
    assertThat(absolute2.getAbsolutePath().contains("..."), is(true));
}
```

## 检查临时目录是否为目录

```java
@Test
public void checkTempDirectoryIsDirectory() {
    File tempDir = new File(System.getProperty("java.io.tmpdir"));

    assertThat(tempDir.isDirectory(), is(true));
    assertThat(tempDir.isFile(), is(false));
}
```

## 使用追加模式向 PrintWriter 写入

```java
@Test
public void exerciseWriteToAppend() throws IOException {
    File outputFile = File.createTempFile("print", null);

    System.out.println("check file " + outputFile.getAbsolutePath());

    FileWriter writer = new FileWriter(outputFile);
    BufferedWriter buffer = new BufferedWriter(writer);
    PrintWriter print = new PrintWriter(buffer);

    print.println("Append to BufferedWriter");

    // 追加到文件
    writer = new FileWriter(outputFile, true);
    buffer = new BufferedWriter(writer);
    print = new PrintWriter(buffer);
    print.println("==================");
    print.close();

    String lineEnd = System.lineSeparator();
    long fileLen = 62L + lineEnd.length();
    assertThat(outputFile.length(), is(fileLen));
}
```

## 创建文件并计算长度

```java
@Test
public void spaceMethods() throws IOException {
    File temp = new File(System.getProperty("java.io.tmpdir"));

    long freeSpace = temp.getFreeSpace();
    long totalSpace = temp.getTotalSpace();
    long usableSpace = temp.getUsableSpace();

    File outputFile = writeTestData();
    assertThat(outputFile.length(), is(0));
}
```

## 使用列表显示临时目录内容

```java
@Test
public void listDirectory() {
    File tempDir = new File(System.getProperty("java.io.tmpdir"));
    File[] fileList = tempDir.listFiles();

    for (File fileInList : fileList) {
        String outputString = "";
        if (fileInList.isDirectory()) {
            outputString = "DIR: ";
        } else {
            outputString = "FIL: ";
        }
        outputString += fileInList.getName();
        System.out.println(outputString);
    }
}
```

## 输出临时目录中文件的属性

```java
@Test
public void listAttrs() {
    File tempDir = new File(System.getProperty("java.io.tmpdir"));
    File[] fileList = tempDir.listFiles();

    for (File fileInList : fileList) {
        String outputString = "";
        if (fileInList.isDirectory()) {
            outputString = "DIR: ";
        } else {
            outputString = "FIL: ";
        }
        outputString += fileInList.getName();
        System.out.println(outputString);
    }
}
```

```java
bd = bd.divide(BigDecimal.valueOf(2L));
```

```java
assertThat(bd, is(BigDecimal.valueOf(5L)));
```

在我的系统上，`double` 的计算结果为 "2.5000000000000004"，这并不等于 2.5。在与外部系统的结果进行比较或进行金融交易时，请始终记住使用 `BigDecimal`。

## 比较 TEN 和 ONE

```java
@Test
public void BigDecimalCompareTenAndOne() {
    assertTrue(BigDecimal.TEN.compareTo(BigDecimal.ONE) > 0);
    assertTrue(BigDecimal.ONE.compareTo(BigDecimal.TEN) < 0);
    assertTrue(BigDecimal.TEN.compareTo(BigDecimal.TEN) == 0);
    assertTrue(BigDecimal.TEN.compareTo(BigDecimal.ONE) != 0);
    assertTrue(BigDecimal.ONE.compareTo(BigDecimal.ONE) >= 0);
    assertTrue(BigDecimal.ONE.compareTo(BigDecimal.TEN) >= 0);
    assertTrue(BigDecimal.TEN.compareTo(BigDecimal.TEN) <= 0);
    assertTrue(BigDecimal.ONE.compareTo(BigDecimal.TEN) <= 0);
}
```

# 第二十一章 - 集合回顾

## 移除 if(val==0)



```java
userSortedList.add(bob);
userSortedList.add(dupebob);
userSortedList.add(rich);
userSortedList.add(dupebob);
assertEquals(2, userSortedList.size());
userSortedList.add(mrBeer);
assertEquals("Mr Beer could not be added", 2, userSortedList.size());
```

在 `Comparator` 中不写 `val==0` 这一行会导致 `mrBeer` 对象加入 `SortedSet`。

```java
// if(val==0) {
// val = user1.getUsername().compareTo(user2.getUsername());
// }
```

## 不允许重复用户名

我创建的代码：

```java
@Test
public void sortedSetWithComparatorForUser() {
  User bob = new User("Bob", "Password"); // 11
  User dupebob = new User("Bob", "hello");
  User rich = new User("Richie", "RichieRichRich"); // 22
  User dupebob2 = new User("Bob", "BobsMightyBigBobPassword");
  User mrBeer = new User("Stafford", "sys"); // 11

  SortedSet<User> userSortedList = 
    new TreeSet<User>(new UserComparatorDisallowDupes());
}
```

```java
userSortedList.add(bob);
userSortedList.add(dupebob);
```

```java
userSortedList.add(rich);
userSortedList.add(dupebob2);
userSortedList.add(mrBeer);

assertEquals(3, userSortedList.size());

User[] users = new User[userSortedList.size()];
userSortedList.toArray(users);

assertEquals(bob.getUsername(), users[0].getUsername());
assertEquals(mrBeer.getUsername(), users[1].getUsername());
assertEquals(rich.getUsername(), users[2].getUsername());

}
```

以及相关的 `UserComparatorDisallowDupes` 类：

```java
public class UserComparatorDisallowDupes implements Comparator {

    public int compare(Object user1, Object user2) {
        User user1 = (User)user1;
        User user2 = (User)user2;

        if(user1.getUsername().compareTo(user2.getUsername())== 0) {
            return 0;
        }

        int user1Comparator = user1.getPassword().length() +
            user1.getUsername().length();

        int user2Comparator = user2.getPassword().length() +
            user2.getUsername().length();

        int val = user1Comparator - user2Comparator;

        if(val==0) {
            val = user1.getUsername().compareTo(user2.getUsername());
        }

        return val;
    }
}
```

## User 类实现 Comparable

我对 `User` 类所做的基础修改是类定义：

```java
public class User implements Comparable {
```

然后我添加了 `compareTo`：

```java
@Override
public int compareTo(Object user2) {
    User user2 = (User)user2;

    if(this.getUsername().compareTo(user2.getUsername())== 0) {
        return 0;
    }

    int user1Comparator = user1.getPassword().length() +
        user1.getUsername().length();

    int user2Comparator = user2.getPassword().length() +
        user2.getUsername().length();

    int val = user1Comparator - user2Comparator;

    if(val==0) {
        val = user1.getUsername().compareTo(user2.getUsername());
    }

    return val;
}
```

然后我创建了一个 `@Test` 来演示它：

```java
@Test
public void sortedSetWithComparable() {
    User bob = new User("Bob", "Password"); // 11
    User dupebob = new User("Bob", "hello");
    User rich = new User("Richie", "RichieRichRich"); // 22
    User dupebob2 = new User("Bob", "BobsMightyBigBobPassword");
    User mrBeer = new User("Stafford", "sys"); // 11

    SortedSet<User> userSortedList = new TreeSet<User>(new UserComparatorDisallowDupes());

    userSortedList.add(bob);
    userSortedList.add(dupebob);
    userSortedList.add(rich);
    userSortedList.add(dupebob2);
    userSortedList.add(mrBeer);

    assertEquals(3, userSortedList.size());

    User[] users = new User[userSortedList.size()];
    userSortedList.toArray(users);

    assertEquals(bob.getUsername(), users[0].getUsername());
    assertEquals(mrBeer.getUsername(), users[1].getUsername());
    assertEquals(rich.getUsername(), users[2].getUsername());
}
```

## 查看排序顺序

当我添加了这一行时：

```java
System.out.println("Compare " + user1.getUsername() + " with " + user2.getUsername() + " = " + val);
```

执行输出输出：

1 Compare Richie with Bob = 11

2 Compare Stafford with Bob = 17

3 Compare Stafford with Richie = -11

这意味着三次调用进入了重复检查。所有其他调用都达到了用户名重复检查的结果。

## 按键顺序访问 Map 中的值

```java
@Test
public void exerciseGetAllKeysSortedSet() {
    Map<String, String> map = new HashMap<>();

    map.put("key4", "value4");
    map.put("key2", "value2");
    map.put("key1", "value1");
    map.put("key3", "value3");

    SortedSet<String> keys = new TreeSet<String>(map.keySet());

    int valSuffix = 1;
    for (String key : keys) {
        assertEquals("value" + valSuffix,
            map.get(key));
        valSuffix += 1;
    }
}
```

在上面的代码中，我无序地将值添加到 `Map` 中。由于不是 `SortedMap`，所以我不能依赖它的顺序。

我从已经生效的排序构造了一个 `TreeSet`，正如我预期的 `map.keySet()` 返回的集合那样，所以我现在拥有了一个有序的键集合。
