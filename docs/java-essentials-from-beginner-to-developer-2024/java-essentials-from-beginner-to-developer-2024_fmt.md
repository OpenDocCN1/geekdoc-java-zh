
# Java 核心：从初学者到开发者 2024

- 2.4 调试 Java 应用程序
- 4.4 String 类的函数与操作
- 5.4 理解作用域与可访问性

（注：OCR 源文件中后续页的重复文本已根据目录提供的结构进行了简化。）

# 欢迎学习 Java

## 1.1 探索 Java：特性与架构

### 1.1.1 Java 简介：强大的编程语言

Java 是一种多功能且强大的编程语言。自 1995 年由太阳微科技公司（Sun Microsystems，现归 Oracle 公司所有）创立以来，它在软件开发领域一直保持着重要地位。Java 的设计遵循“编写一次，随处运行”（WORA）的原则，这使得开发者能够在任何支持 Java 的设备上编写代码，而无需重新编译。Java 的广泛采用证明了其稳健性、可移植性以及易于使用的设计。

### 1.1.2 Java 的核心特性：简单、面向对象且安全

Java 的设计准则旨在使其成为一种简单、安全且可靠的编程语言。它的基础特性之一是**面向对象**，这种设计侧重于数据（对象）以及操作这些对象的方法，从而促进了更整洁、模块化的编码方法。安全是另一个基石，它内置的机制可以最大限度地减少病毒攻击以及对数据和系统的未经授权访问。简化的语法和缺乏低级编程功能使得 Java 初学者易于上手，同时对经验丰富的开发者来说依然强大。

### 1.1.3 理解 Java 架构：JVM、JRE 和 JDK

Java 架构充分体现了它在不同平台上的可移植性和效率。它由以下部分组成：

- **Java 虚拟机 (JVM)**：执行 Java 字节码的运行时引擎，确保了 WORA 原则的实现。它将底层操作系统和硬件与 Java 应用抽象。
- **Java 运行时环境 (JRE)**：包含 JVM 以及运行 Java 程序所需的库和组件。它不包含编译器或调试器等开发工具。
- **Java 开发工具包 (JDK)**：用于 Java 开发的完整套件，包含了 JRE 和开发工具。

### 1.1.4 “编写一次，随处运行”(WORA) 哲学

WORA 哲学是 Java 身份的核心，它强调在任何配备了 JVM 的设备上运行 Java 代码的能力。这种跨平台的兼容性是一个巨大的优势，将开发者从特定平台的编码限制中解放出来，并实现了更顺畅的开发和部署过程。

## 1.2 编写你的第一个 Java 程序

### 1.2.1 准备工作：搭建你的开发环境

在深入编码之前，准备好开发环境是至关重要的。这个过程涉及安装 `Java 开发工具包 (JDK)` 以及你选择的集成开发环境 (IDE)，例如 `IntelliJ IDEA`、`Eclipse` 或 `NetBeans`。通过命令行或终端输入命令 `java -version` 检查版本，确保 Java 已正确安装在系统上。设置包括配置环境变量（如 `PATH`），以便从命令行轻松运行 Java 程序。

### 1.2.2 Hello, World!：理解 Java 程序的结构

任何旅程都始于足，而在 Java 中，这一步就是“Hello, World!”程序。Java 中的“Hello, World!”程序展示了基本的 Java 语法和结构，包括公类的声明、`main` 方法的声明以及向控制台打印输出的 `System.out.println` 语句。这个程序不仅是学习新编程语言的传统，更是对 Java 程序语法和功能的介绍。

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

### 1.2.3 编译并运行你的第一个程序

Java 程序是用纯文本编写的，因此可以随意使用任何文本编辑器来编写代码。要让你的 Java 程序能够运行，你首先需要使用 Java 编译器 (`javac`) 将其编译为字节码。这个过程会将你的 `.java` 文件转换为 Java 虚拟机 (JVM) 可以执行的 `.class` 文件。在命令行中编译和运行程序的基本命令是：

```bash
javac HelloWorld.java
java HelloWorld
```

第一条命令将 `HelloWorld.java` 源文件编译为 `HelloWorld.class` 字节码文件。第二个命令在 JVM 上运行编译后的字节码。

### 1.2.4 常见错误与排错

在开始时，需要仔细阅读错误信息。常见的错误类型包括：

- **语法错误**：缺少分号、括号不匹配或关键字拼写。
- **运行时错误**：在执行期间发生的错误，例如除以零。
- **编译错误**：在编译过程中发现的问题，如类路径错误。

## 1.3 探索 Java 开发工具包 (JDK)

### 1.3.1 什么是 JDK？全面概述

Java 开发工具包 (JDK) 是用于 Java 开发的完整软件套件，包含了运行应用程序所需的各种工具。它涵盖了 Java 运行时环境 (JRE)，以及编译器和调试器。

### 1.3.2 安装 JDK：步骤指南

为了让你的机器准备好，按照以下步骤安装 JDK：

1. **下载 JDK**：访问 Oracle 官网或 OpenJDK 版本，选择适合你系统的版本。
2. **运行安装程序**：执行下载的安装文件。按照屏幕提示操作，通常包括同意许可协议。
3. **设置环境变量**：为了从命令行使用 JDK，你需要将 JDK 的 `bin` 目录添加到 `PATH` 中。在 Windows 上，你可能还需要设置 `JAVA_HOME` 到 JDK 安装目录。
4. **验证安装**：打开命令提示符或终端输入 `java -version` 和 `javac -version`。如果 JDK 安装正确，你应该看到 Java 和编译器的版本。

### 1.3.3 JDK 的核心组件

JDK 不仅仅是一个编译器，它包含了许多 Java 开发的关键组件：

- `javac`：将源代码转换为 Java 字节码。
- `java`：Java 启动工具，运行你的 Java 程序字节码。
- `jar`：Java 归档工具，将多个文件合并成单个 JAR 文件。
- `javadoc`：文档生成器，从源码注释生成 HTML 格式文档。
- **调试器**：用于调试 Java 程序的工具，包括命令行和 IDE 集成的。
- **JVM (Java 虚拟机)**：执行字节码的关键部分。

### 1.3.4 导航 JDK 文档

JDK 文档是开发者宝贵的资源。它涵盖了 Java 的方方面面，从平台的全面概述到 Java 丰富的 API（应用程序接口）的详细描述。以下是导航 JDK 文档的一些提示：

- **从概述开始**：文档概述页提供了包含内容的摘要，可以帮助你找到所需信息。
- **API 文档**：熟悉 API 文档的结构。它按包、类和接口组织，对每个方法和字段都有详细描述。
- **教程和指南**：除了参考资料，JDK 文档还包含复杂主题或特定功能的教程、指南和文章。
- **示例代码**：留意文档中的示例代码段，这有助于澄清各种类和方法的用法。

## 1.4 Java 的演变：版本与发行

### 1.4.1 Java 的历史历程

Java 自诞生以来已经走了漫长的道路。它最初由 James Gosling 在 1991 年在 Sun Microsystems 构思为一个名为“Oak”的项目，旨在为机顶盒和电视等数字设备设计。然而，互联网的兴起为 Java 的繁荣提供了完美的环境。Sun Microsystems 于 1995 年正式发布了 Java 1.0，其“编写一次，随处运行”（Write Once, Run Anywhere）的承诺捕捉了全球开发者的想象。多年来，Java 经历了重大的演变，每个版本的发布都会不断添加新功能和改进。

### 1.4.2 Java SE vs Java EE vs Java ME：理解区别

Java 技术分为几个版本，每个版本针对不同的应用环境和需求：

- **Java SE（标准版）**：Java 编程的基础，提供了 Java 编程语言的核心功能。它包含了用于网络、UI、数据库访问、安全等基本的 API。
- **Java EE（企业版）**：基于 Java SE 构建，增加了用于企业级功能的 API，如分布式计算和 Web 服务。Java EE 设计用于开发大型、多层级、可扩展、可靠且安全的网络应用程序。
- **Java ME（微版）**：针对资源有限的移动和嵌入式设备进行了优化，Java ME 为在这些设备上运行提供了一个稳健、灵活的环境。

### 1.4.3 从 Java 1 到最新版本的亮点与特性

Java 的演变以每个版本的重大新增和改进为标志。以下是一些亮点：

- **Java 1.0 (1996)**：开端，引入了 Java 语言，并具有垃圾回收和用于可移植性的 JVM 等特性。
- **Java 5 (2004)**：引入了重大增强，包括泛型、元数据注解、增强型 for 循环、自动装箱/拆箱以及并发工具类。
- **Java 8 (2014)**：一个里程碑式的发布，引入了 Lambda 表达式、用于对集合批量数据操作的 Stream API，以及新的日期/时间 API。
- **Java 11 (2018)**：Java 8 之后的第一个长期支持（LTS）版本，带来了许多新功能，如 Lambda 参数的局部变量语法、HTTP Client API 等。
- **Java 17 (2021)**：截至我上次更新时的最新 LTS 版本，引入了密封类（sealed classes）、`instanceof` 的模式匹配，并弃用了 Applet API。

### 1.4.4 如何跟进 Java 开发

通过以下方式获取 Java 开发的动态：

- **官方 Java 博客和邮件列表**：订阅以接收最新消息和更新。
- **Java 社区进程 (JCP)**：参与或关注 JCP 以查看 Java 的未来方向和提案。
- **开发者大会**：参加 Java 大会，例如 Oracle Code One 或本地 Java 用户组会议。
- **关注专家和影响人物**：Java 思想领袖的社交媒体平台和个人博客是获取见解的良好来源。

# 设置你的 Java 环境

## 2.1 配置系统环境变量

### 2.1.1 Java 环境变量简介

计算机中的环境变量是影响计算机上运行进程行为的动态值。它们可以指定数据，如系统文件的位置或软件应用程序的设置。对于 Java 开发，设置环境变量至关重要，因为它们指导 Java 编译器（`javac`）和 Java 运行时（`java`）的查找位置。这允许开发者从任何目录从命令行运行 Java 命令，而无需指定 Java 可执行文件的完整路径。

### 2.1.2 设置 JAVA_HOME 并更新 PATH

设置 `JAVA_HOME`：`JAVA_HOME` 环境变量指向 JDK 的安装目录。应用程序使用此变量来查找 Java 库。

- **Windows**：
  1. 右键点击“我的电脑”并选择“属性”。
  2. 导航到“高级系统设置” > “环境变量”。
  3. 点击“新建”创建一个新变量。

### 2.1.3 在 Windows、macOS 和 Linux 上验证配置



在设置 `JAVA_HOME` 并更新 `PATH` 后，在 Windows、macOS 和 Linux 上验证配置：

- Windows：

  1. 打开命令提示符。
  2. 输入 `java -version` 并。
  3. 输入 `javac -version` 并。

- macOS：

  1. 打开终端。
  2. 输入 `java -version` 并。
  3. 输入 `javac -version` 并。

- Linux：

  1. 打开终端。
  2. 输入 `java -version` 并。
  3. 输入 `javac -version` 并。

## 2.2 在你的 IDE 中集成构建工具

### 2.2.1 构建工具概述：Maven 和 Gradle

Maven 和 Gradle 是 Java 最常用的两种构建工具。它们有助于项目创建、依赖管理和构建周期。

- Maven 以使用基于 XML 的 `pom.xml`（项目模型）文件来定义项目结构和依赖而闻名。它遵循约定优于配置的原则，简化了项目设置，但灵活性较低。
- Gradle 则使用基于 Groovy 的 DSL（领域特定语言）进行配置脚本（`build.gradle`），提供了更高的可扩展性和灵活性。Gradle 的性能被认为是一个优势，特别是它的增量构建。

### 2.2.2 在 Eclipse 和 IntelliJ IDEA 中设置 Maven

**Eclipse 中的 Maven：**

1. Eclipse 在多数版本中都带有 Maven 集成。要创建一个新的 Maven 项目，转到 `File > New > Other... > Maven > Maven Project`。
2. 向导指定组 ID、Artifact ID 和版本。

**IntelliJ IDEA 中的 Maven：**

1. 打开 IntelliJ IDEA，导航到 `File > New > Project`。
2. 选择 Maven。IntelliJ IDEA 会提示指定项目的 SDK 和其他 Maven 参数，如 `GroupId` 和 `ArtifactId`。

两个 IDE 都会根据 `pom.xml` 文件自动处理依赖解析，无需手动下载和库配置。

### 2.2.3 在你的 Java 项目中配置 Gradle

设置 Gradle 在不同 IDE 之间没有太大差异，因为 Eclipse 和 IntelliJ IDEA 都提供了良好的 Gradle 支持。

**在 Eclipse 中：**

1. 如果你的 Eclipse 版本未包含，你需要安装 Buildship Gradle Integration 插件。这可以通过 Eclipse Marketplace 进行。
2. 要创建一个新的 Gradle 项目，转到 `File > New > Other... > Gradle > Gradle Project` 并遵循向导。

**在 IntelliJ IDEA 中：**

1. IntelliJ IDEA 原生带有 Gradle 的支持。要启动一个新的 Gradle 项目，只需导航到 `File > New > Project`，然后从左侧栏选择 Gradle。
2. IntelliJ IDEA 将要求你定义 `GroupId`、`ArtifactId` 和其他选项。

对于 Maven 和 Gradle，在设置项目后，IDE 将根据构建配置（`pom.xml` 或 `build.gradle`）显示项目结构，允许你通过 IDE 的 UI 运行、调试和管理依赖。

将 Maven 或 Gradle 集成到开发环境中可以显著增强项目管理、依赖解析和构建自动化，并无缝集成到 Java 开发者使用的 IDE 中。

## 2.3 版本控制系统：Git 与 Java

### 2.3.1 Java 开发者 Git 简介

对于 Java 开发者来说，理解和利用版本控制系统（VCS）是不可或缺的，而 Git 是当今开发领域应用最广泛的 VCS。Git 帮助管理代码更改、与其他开发者协作并维护项目演进的历史记录。从简单的代码存储到复杂的协作开发项目，它都是至关重要的。

Git 基于“快照”原理运行，每个 commit 都代表项目在特定时间点的快照。这种模型允许强大的分支和合并操作，使得能够在互不干扰的情况下进行并行开发流。

### 2.3.2 使用 Git 克隆你的第一个 Java 项目

克隆（Cloning）是创建 Git 仓库本地副本的过程。要克隆你的第一个 Java 项目：

1. 找到仓库：找到你想要克隆的 Git 仓库 URL。这可能位于 GitHub、GitLab、Bitbucket 或任何 Git 服务器上。
2. 打开终端或命令提示符：切换目录（`cd`）到你想要克隆仓库的位置。
3. 克隆仓库：使用 `git clone` 命令后跟仓库的 URL。

例如：

```
git clone https://github.com/example/project.git
```

此命令将项目下载到与项目同名的本地文件夹中。

4. 使用 IDE 打开：使用你喜欢的 IDE（例如 Eclipse 或 IntelliJ IDEA）将克隆的目录作为既有项目打开。大多数 IDE 会自动识别 Git 仓库并启用 VCS 支持。

### 2.3.3 在 Java 项目中提交和推送更改

在对 Java 项目进行更改后，你可能希望将这些更改保存到 Git 仓库中。

提交（Committing）和推送（Pushing）是实现此目的的两个主要操作。

**提交更改（Committing Changes）：**

1. 审查更改：使用 `git status`，你可以查看哪些文件被更改了。要查看具体的更改，使用 `git diff`。
2. 暂存文件以提交：在提交之前，你需要使用 `git add` 暂存更改。你可以使用 `git add .` 暂存所有更改的文件，或使用 `git add filename` 暂存单个文件。
3. 提交：使用 `git commit -m "Your commit message"` 提交暂存的更改。commit 信息应该是对更改的简短描述。

**推送更改（Pushing Changes）：**

1. 如果你在克隆的仓库上工作，它已链接到远程仓库。使用 `git push` 将提交推送到远程仓库。
2. 第一次推送时，你可能需要使用 `git push --upstream origin branch_name` 设置上游分支，将 `branch_name` 替换为你当前的分支。

通过掌握 Git 中克隆、提交和推送的基础知识，Java 开发者可以有效地管理和协作软件项目，确保更改能够安全地存储并在团队成员之间共享。

## 2.4 调试 Java 应用程序

### 2.4.1 Java 调试基础

调试是开发过程中的关键阶段，允许开发者诊断并修复 Java 应用程序中的错误。它涉及识别 bug 的来源、理解它们为何发生以及确定纠正它们的最佳方法。有效的调试可以节省时间和精力，确保应用程序顺利运行并符合预期。

Java 提供了一系列调试工具和 IDE 特性，例如堆栈跟踪分析、断点、单步执行和变量检查，以促进这一过程。理解这些工具以及如何利用它们可以显著提高开发者快速诊断和解决问题的能力。

### 2.4.2 设置断点和检查变量

**设置断点（Setting Breakpoints）：** 断点会在特定的代码行处临时停止程序的执行。这允许你检查程序在那一刻的状态，这对于诊断问题具有极高价值。在大多数 Java IDE 中设置断点：

1. 打开你想要暂停执行的源代码。
2. 点击行号旁边的左边距或直接点击代码行。会出现一个标记或高亮行。

**检查变量（Inspecting Variables）：** 当程序暂停时，你可以检查变量的当前值：

1. 在 IDE 中打开变量视图。
2. 悬停在变量上查看其当前值。
3. 你可以在调试期间修改变量值以测试各种场景。

### 2.4.3 常见调试场景和解决方案

**场景 1：空指针异常（NullPointerException）**

- 问题：尝试使用一个为空的对象。
- 解决方案：在使用对象之前检查其是否为空。

**场景 2：数组越界（Array Out of Bounds）**

- 问题：尝试访问超出数组大小的索引。
- 解决方案：确保循环逻辑和索引检查正确。

**场景 3：死循环（Infinite Loops）**

- 问题：循环永不终止。
- 解决方案：检查循环条件和递增逻辑。

**场景 4：并发问题（Concurrency Issues）**

- 问题：多个线程访问共享资源引起的问题。
- 解决方案：使用同步块（`synchronized blocks`）或锁来管理访问。

# Java 编程基础

## 3.1 理解变量和数据类型

### 3.1.1 什么是变量？

**变量简介：** Java 中的变量是存储数据值的基本容器。它们被称为变量，是因为其中包含的数据可以改变（或变化）。在 Java 中，每个变量都有特定的类型，该类型决定了大小和布局、可以存储的值范围以及可以应用的操作集合。

**变量命名规范：** Java 变量命名遵循某些约定和规则：

- 变量名应以小写字母开头并遵循驼峰命名法。
- 可以包含字母、数字、下划线和美元符号，但不能以数字开头。
- 选择反映变量用途的有意义命名很重要。
- Java 关键字不能作为变量名。

### 3.1.2 原始数据类型

**原始数据类型概述：** 原始数据类型由语言定义并用关键字命名。它们代表了基础的数据类型。

**数值数据类型：** `int`、`short`、`long`、`byte`

- `byte`：从 -128 到 127 的极小整数。在大数组中节省内存。
- `short`：从 -32768 到 32767 的小整数。
- `int`：默认整数类型，范围从 -2^31 到 2^31-1。
- `long`：从 -2^63 到 2^63-1 的大整数，当 `int` 不够大时使用。

**浮点数类型：** `float`、`double`

- `float`：单精度 32 位浮点数。绝不应用于精确值（例如货币）。
- `double`：双精度 64 位 IEEE 754 浮点数。它通常是小数值的默认选择。

**布尔类型和字符类型**

- `boolean`：此类型代表一个比特位的信息，但其“大小”并不是精确定义的。值为 `true` 或 `false`。
- `char`：单个 16 位 Unicode 字符。它的最小值为 `'\u0000'`（或 0），最大值为 `'\uffff'`（包含 65535 在内）。

### 3.1.3 引用数据类型

**理解引用变量：** 引用变量用于引用对象。与存储实际值的原始数据类型不同，引用变量存储的是实际数据的内存地址或引用。

**字符串和数组**

- 字符串（Strings）：字符串类不是原始数据类型，而是可以存储字符序列的引用类型。
- 数组（Arrays）：数组是引用类型，用于存储多个相同类型的条目。原始类型和对象都可以存储在数组中。

### 3.1.4 类型转换与强制转换

**隐式转换与显式转换**

- 隐式转换（宽转换）：当源类型的大小小于目标类型时，就会发生这种情况。例如，Java 会隐式地将一个 `int` 赋值给 `long`。
- 显式转换（窄转换）：当你将尺寸较大的类型赋值给较小的类型时（例如将 `double` 转换为 `int`），就需要强制转换。这需要使用强制转换运算符。

**数据类型之间的转换：** 在执行涉及不同类型值的操作时，可能需要数据类型之间的转换。在转换时，请注意可能的数据丢失（对于窄转换而言），并确保转换是必要且刻意的，以维护数据的准确性和完整性。

## 3.2 深入理解运算符和表达式

### 3.2.1 算术运算符

**基本操作：加法、减法等。** Java 提供了几种算术运算符来执行常见的数学运算：

- `+`（加法）：合并两个值。
- `-`（减法）：从另一个值中减去一个。
- `*`（乘法）：两个值相乘。
- `/`（除法）：将一个值除以另一个。如果两个操作数都是整数，结果也将是整数，并丢弃任何余数。
- `%`（模运算符）：返回除法操作的余数。

**模运算符：** 模运算符用 `%` 表示，对于寻找余数、判断数字是偶数还是奇数（通过对 2 取模）以及在特定阈值处通过回绕循环值特别有用。

### 3.2.2 关系运算符和逻辑运算符

**比较值：** 关系运算符比较两个值并确定它们之间的关系。主要的关系运算符有：

- `==`（等于）
- `!=`（不等于）
- `>`（大于）
- `<`（小于）
- `>=`（大于或等于）
- `<=`（小于或等于）

这些运算符返回一个布尔结果（`true` 或 `false`）。

**组合条件：AND、OR、NOT：** 逻辑运算符用于构建更复杂的条件表达式：

- `&&`（逻辑与）：只有当两个操作数均为真时，才返回 `true`。
- `||`（逻辑或）：如果至少有一个操作数为真，则返回 `true`。
- `!`（逻辑非）：反转布尔值，将 `true` 变为 `false`，反之亦然。

### 3.2.3 赋值运算符

**简单赋值：** 简单赋值运算符 `=` 用于将其右侧的值赋值给左侧的操作数。

**复合赋值运算符：** 复合赋值运算符在一步中完成操作和赋值。示例包括 `+=`、`-=`、`*=`、`/=` 和 `%=`。例如，`x += y` 等同于 `x = x + y`。

### 3.2.4 一元运算符、三元运算符和运算符优先级

**自增与自减：** 自增（`++`）和自减（`--`）运算符分别增加或减少变量的值 1。它们既可以作为前缀也可以作为后缀使用，这会影响操作在表达式中的执行时机。

**使用三元运算符进行条件赋值：** 三元运算符 `? :` 为 `if-else` 语句提供了快捷方式，并用于条件赋值。语法为 `条件 ? 真值 : 假值`。

**理解运算符优先级和结合性：** 运算符优先级决定了表达式中项的分组。这影响了表达式的评估方式。某些运算符的优先级高于其他；例如，乘法的优先级高于加法和减法。结合性定义了执行的方向（从左到右或从右到左），当表达式中出现具有相同优先级的多个运算符时，这一点至关重要。

## 3.3 用于决策的条件语句

### 3.3.1 if 语句

**基本 if 结构：** `if` 语句是 Java 中基本的控制流语句之一。它允许程序根据条件的真假执行不同的操作。基本语法如下：

```java
if (condition) {
  // 如果条件为真，则执行代码块
}
```

**if-else 和 if-else-if 链：** 对于需要在条件为真时执行一个操作、条件为假时执行另一个操作的情况，使用了 `if-else` 结构：

```java
if (condition) {
  // 如果条件为真，则执行代码块
} else {
  // 如果条件为假，则执行代码块
}
```

对于多个条件，`if-else-if` 链非常有用：

### 3.3.2 switch 语句

**语法和用例：** `switch` 语句提供了一种简单的方法，根据表达式的值将执行分发到代码的不同部分。与顺序评估条件的 `if-else-if` 链不同，`switch` 语句根据匹配项执行一个 `case`：

```java
switch(expression) {
  case value1:
    // 匹配 value1 时执行代码块
    break;
  case value2:
    // 匹配 value2 时执行代码块
    break;
  default:
    // 如果没有匹配项，执行代码块
}
```

`switch case` 可以适用于 `byte`、`short`、`char` 和 `int`。

**Java 新的 switch 表达式：** Java 引入了简化 switch 使用表达式，可以直接从 switch 返回值。

### 3.3.3 实践中的条件逻辑

**组合条件：** 逻辑运算符（`&&`、`||`）允许在 `if` 语句中组合条件，创建更复杂的控制路径：

```java
if (condition1 && condition2) {
  // 如果 condition1 和 condition2 均为真，则执行
}
```

**嵌套条件语句：** 条件语句可以嵌套在另一个内部以进一步细化决策路径。这涉及到在另一个 `if` 或 `switch` 语句内部放入：

```java
if (condition1) {
  // 如果 condition1 为真
  if (condition2) {
    // 如果两者均为真，则执行
  }
}
```

正确使用条件语句允许开发者编写灵活且可扩展的 Java 代码，能够根据各种条件执行不同的代码块。

## 3.4 循环机制：for、while 和 do-while 循环

### 3.4.1 for 循环

**语法和基本用法：** Java 中的 `for` 循环用于执行固定次数的代码块。基本 `for` 循环的语法如下：

```java
for(initialization; condition; update) {
  // 执行代码块
}
```

- 初始化：通常用于初始化计数器。
- 条件：只要该条件为真，循环就会运行。
- 更新：在每次迭代后执行；通常用于更新计数器。

**用于数组和集合的增强型 for 循环：** Java 5 引入了增强型 for 循环，使得遍历数组和集合元素变得简单：

```java
for(dataType item : arrayOrCollection) {
  // 对每个项目执行代码块
}
```

这种形式消除了对维护索引或直接使用迭代器的需要。

### 3.4.2 while 循环

**何时使用 while 循环：** 当循环开始前不知道迭代次数时，应使用 `while` 循环。只要指定的条件评估为真，循环就会继续。

```java
while(condition) {
  // 执行代码块
}
```

**无限循环与循环控制：** 当循环条件永远不变为假时，就会发生无限循环。有时会特意配合 `break` 语句，根据循环体内部的条件退出循环。

### 3.4.3 do-while 循环

**与 while 循环的区别：** do-while 循环与 `while` 循环相似，主要区别在于 do-while 循环保证至少执行一次。这是因为条件是在执行完循环体后进行检查的。

```java
do {
  // 要执行的代码块
} while(condition);
```

**实际用法示例：** 当在评估条件之前至少执行一次循环体时，do-while 循环特别有用，例如在用户输入循环中显示菜单时。

### 3.4.4 循环控制语句



# 循环中的 break 和 continue

- `break` 语句用于立即退出循环，跳过所有剩余的迭代。
- `continue` 语句跳过当前迭代，并继续循环的下一次迭代。

## 嵌套循环

嵌套循环是指位于另一个内部的循环。它们通常用于遍历多维数组等任务。

`break` 和 `continue` 等循环控制结构可以应用于嵌套循环，影响内层和外层循环的流。准确控制和理解循环对于创建能够处理重复任务的高效 Java 程序至关重要。

# 第 4 章：深入学习：数组与字符串

## 4.1 数组操作

### 4.1.1 数组简介：定义与声明

**数组**是一个容器对象，存储固定数量的相同类型的值。数组长度在创建时确定且不能更改。Java 中的数组是从零开始的，这意味着数组的初始元素通过索引 0 访问。

在 Java 中声明数组时，你需要指定它将包含的元素类型，后跟方括号，然后是数组的名称：

```java
int[] myIntArray;
String[] myStringArray;
```

你也可以将括号放在数组名称之后：

```java
int myIntArray[];
String myStringArray[];
```

然而，为了一致性，前一种声明更常用且更受推荐。

### 4.1.2 初始化和访问数组元素

要为数组分配内存并对其初始化，使用 `new` 关键字，后跟数组元素的类型及其大小：

```java
myIntArray = new int[10]; // 初始化一个可以容纳十个整数的数组
```

数组也可以在声明时通过在花括号 `{}` 中包含值来初始化。访问数组元素是直接的；你使用数组名称后跟方括号 `[]` 中的元素索引：

```java
int firstElement = myIntArray[0]; // 访问第一个元素
myIntArray[4] = 20; // 修改第五个元素的值
```

### 4.1.3 遍历数组

为了对数组的每个元素执行操作，可以使用循环遍历数组。`for` 循环通常用于此目的：

```java
for (int i = 0; i < myArray.length; i++) {
    System.out.println(myIntVar[i]); // 打印数组中的每个元素
}
```

Java 还提供了一种增强型 `for` 循环（也称为“for-each”循环）来遍历数组，这使得代码更简洁、更易读：

```java
for (int element : myArray) {
    System.out.println(element); // 打印数组中的每个元素
}
```

### 4.1.4 多维数组：概念与用法

多维数组是数组的数组，主数组的每个元素都持有另一个数组。最常见的形式是二维数组，或矩阵。二维数组通过指定两组方括号来声明、分配和访问：

```java
int[][] myMatrix = new int[3][4]; // 一个 3x4（行 x 列）的数组
```

使用值初始化二维数组：

访问元素需要为每个维度指定索引：

```java
int firstRowThirdColumn = myMatrix[0][2];
```

遍历多维数组通常涉及嵌套循环：

```java
for (int i = 0; i < myMatrix.length; i++) { // 遍历行
    for (int j = 0; j < myMatrix[i].length; j++) { // 遍历列
        System.out.print(myMatrix[i][j] + " ");
    }
    System.out.println(); // 每行后换行
}
```

有效理解和使用数组是 Java 编程的基础，它有助于高效且逻辑上严密地存储和操作数据集合。

## 4.2 在 Java 中操作字符串

### 4.2.1 String 类概述

Java 中的 `String` 类用于存储和操作字符序列。字符串是不可变的，这意味着一旦创建了 `String` 对象，其内容就无法更改。如果你执行任何修改字符串的操作，Java 都会创建一个新的 `String` 对象来保存结果。

Java 在 `String` 类中提供了丰富的方法，用于执行各种操作，如比较、拼接、分割、搜索以及检查字符串中的单个字符。

### 4.2.2 创建和初始化字符串

在 Java 中创建字符串有两种方式：通过使用字符串字面量或使用 `new` 关键字。

- 使用字符串字面量

```java
String greeting = "Hello";
```

当你使用字符串字面量时，Java 会首先检查字符串池。

- 使用 `new` 关键字

```java
String str1 = new String("Hello");
```

### 4.2.3 比较字符串：方法

Java 提供了多种方法来比较字符串：

- `equals()`：该方法比较内容。如果字符串相等则返回 `true`，否则返回 `false`。

```java
String str1 = "Hello";
String str2 = "Hello";
boolean result = str1.equals(str2);
```

- `equalsIgnoreCase()`：该方法类似于 `equals()`，但在比较时不忽略大小写。

```java
String str1 = "hello";
String str2 = "Hello";
boolean result = str1.equalsIgnoreCase(str2); //
```

- `compareTo()`：该方法按字典顺序比较两个字符串并返回一个整数值。值为 0 表示两个字符串相等。值小于 0 表示调用字符串小于参数字符串。值大于 0 则相反。

```java
String str1 = "Hello";
String str2 = "World";
int result = str1.compareTo(str2); //
```

### 4.2.4 字符串拼接与分割

- 拼接：可以使用 `+` 运算符或 `concat()` 方法拼接字符串。

```java
String greeting = "Hello";
String name = "John";
String message = greeting + ", " + name + "!"; // 使用 + 运算符
String anotherMessage = greeting.concat(", ").concat(name); // 使用 concat()
```

- 分割：`split()` 方法根据给定的正则表达式将字符串分割为字符串数组。

```java
String fruits = "apple, banana, cherry";
String[] fruitsArray = fruits.split(",");
// fruitsArray 包含 ["apple", "banana", "cherry"]
```

操作字符串是 Java 编程中的常见任务。`String` 类提供了许多用于字符串比较、拼接和分割的方法，使得在 Java 应用中管理和修改字符串更加容易。

## 4.3 高级数组概念

### 4.3.1 动态数组及其用法

在 Java 中数组的大小是固定的。然而，有时我们需要根据需要增长或收缩的数据结构。Java 集合框架提供了 `ArrayList`，这是一个实现动态数组的类，它会自动调整容量。

```java
import java.util.ArrayList;

ArrayList<Integer> dynamicArray = new ArrayList<>();
dynamicArray.add(10); // 添加元素
dynamicArray.add(20);
System.out.println(dynamicArray.get(0)); // 访问元素
```

当元素数量提前未知时，动态数组特别有用。它们提供了高效添加、删除和搜索元素的方法。

### 4.3.2 Arrays 类：排序与搜索

`java.util.Arrays` 类提供了静态方法，用于对数组进行排序和搜索。这些工具类极大地简化了数组的操作。

- 排序

要对数组进行排序，可以使用 `Arrays.sort()` 方法。它会在原地修改数组，将元素按升序排列。

```java
import java.util.Arrays;

int[] numbers = {5, 3, 9, 1};
Arrays.sort(numbers); // numbers 数组现在已经排序
```

- 搜索

在对数组进行排序后，可以使用 `Arrays.binarySearch()` 方法进行二分查找。如果找到了搜索值，它将返回值的索引；否则返回一个负数。

```java
int[] numbers = {1, 3, 5, 9}; // 二分查找前必须排序
int index = Arrays.binarySearch(numbers, 5); // 返回 2
```

### 4.3.3 数组转换：从数组到集合及反之

Java 提供了在数组与集合（如 `List`、`Set` 和 `Map`）之间转换的机制，允许你利用集合框架提供的工具类。

- 数组转集合

你可以使用 `Arrays.asList()` 方法将数组转换为列表（`List`）。集合可以通过 `toArray()` 方法转换回数组。

```java
String[] colorArray = new String[colorList.size()];
colorList.toArray(colorArray); // 将 List 转换回数组
```

### 4.3.4 实际用例与示例

动态数组以及 `Arrays` 类提供的数组操作工具广泛应用于各个领域：

- 数据聚合：为报告或分析收集并汇总数据通常涉及集合的动态调整大小、排序和搜索操作。
- 系统管理：解析和处理日志文件、配置文件或用户输入，可能涉及数组与集合类型之间的转换，以便于操作。
- 游戏开发：管理游戏中的实体（如角色、障碍物和强化道具）通常需要动态数组来灵活地添加和删除元素。

示例：寻找最大值和最小值

```java
int[] numbers = {4, 1, 13, 0, 6};
Arrays.sort(numbers); // 对数组排序
int min = numbers[0]; // 第一个元素是最小的
int max = numbers[numbers.length - 1]; // 最后一个元素是最大的
System.out.println("Minimum: " + min + ", Maximum: " + max);
```

示例：列表去重

高级数组概念（包括动态数组和 `Arrays` 类提供的工具）是开发高效且健壮的 Java 应用的基础。

## 4.4 String 类函数与操作

### 4.4.1 将数据类型转换为字符串

将各种数据类型转换为字符串是一个常见需求。在 Java 中，可以通过几种方法实现：

- `String.valueOf()`：此静态方法可以将各种数据类型（`int`、`long`、`float`、`double`、`char`、数组等）转换为字符串。

```java
int num = 100;
String str = String.valueOf(num); // "100"
```

- 使用 `toString()` 方法：Java 中的每个类都继承自 `Object` 类的 `toString()` 方法，该方法可以被重写以字符串形式表示对象。

```java
Integer numInteger = 100;
String str = numInteger.toString(); // "100"
```

- 与空字符串拼接：将值转换为字符串的快速方法。

```java
int num = 100;
String str = num + ""; // "100"
```

### 4.4.2 字符串操作：截取、替换与大小写转换

- Substring（截取）：提取字符串的一部分。

```java
String str = "Hello World";
String substr = str.substring(0, 5); // "Hello"
```

- Replace（替换）：替换字符串的部分。

```java
String str = "Java is fun";
String replacedStr = str.replace("fun", "awesome"); // "Java is awesome"
```

- Case Conversion（大小写转换）：转换字符串的大小。

```java
String str = "Java Programming";
String lowerStr = str.toLowerCase(); // "java programming"
String upperStr = str.toUpperCase(); // "JAVA PROGRAMMING"
```

### 4.4.3 字符串分析：长度、字符提取与模式匹配

- Length（长度）：返回字符串中字符的数量。

```java
String str = "Hello";
int length = str.length(); // 5
```

- Character Extraction：获取指定索引处的字符。
- Pattern Matching：Java 提供了 `Pattern` 和 `Matcher` 类用于正则表达式的模式匹配。

### 4.4.4 高级字符串处理：StringBuilder 和 StringBuffer 类

当需要频繁修改字符串时，由于 `String` 的不可变性，直接使用 `String` 会导致性能问题。Java 为此场景提供了 `StringBuilder` 和 `StringBuffer`。

- `StringBuilder`：为可变字符串提供 API。它不是线程安全的，这使其在单线程环境中速度更快。

```java
StringBuilder sb = new StringBuilder("Hello");
sb.append(" World"); // 在末尾追加字符串
System.out.println(sb.toString()); // "Hello World"
```

- `StringBuffer`：与 `StringBuilder` 类似，但是线程安全的，适用于多线程环境。

```java
StringBuffer sbf = new StringBuffer("Hello");
sbf.append(" World");
System.out.println(sbf.toString()); // "Hello World"
```

# 第 5 章：方法

## 5.2 方法参数与返回值

可用的。当你定义一个方法时，你将其参数列表作为其声明的一部分。当你调用该方法时，你需要提供与这些参数对应的参数。Java 方法通过“按值传递”接收参数，这意味着方法接收的是原始数据的拷贝。

```java
public static void greet(String name) {
    System.out.println("Hello, " + name);
}

public static void main(String[] args) {
    greet("Alice"); // 将 "Alice" 作为参数传递给 greet 方法
}
```

### 5.2.2 基本类型 vs. 引用参数

在 Java 中，方法参数是通过值传递的。这一概念对于基本类型和引用类型的行为有所不同。

- 基本类型参数：对于基本数据类型（例如 `int`、`double`、`char`），方法接收的是该值的拷贝。修改此值不会影响原始变量。

```java
public static void increment(int number) {
    number++;
    System.out.println("Number inside method: " + number);
}

public static void main(String[] args) {
    int value = 5;
    increment(value); // value 在方法外仍保持为 5
    System.out.println("Number after method call: " + value);
}
```

- 引用参数：对于引用数据类型（例如数组、对象），方法接收的是引用的拷贝，指向内存中的同一个对象。通过此引用修改对象将影响原始对象。

```java
public static void updateArray(int[] arr) {
    arr[0] = 100;
}

public static void main(String[] args) {
    int[] values = {1, 2, 3};
    updateArray(values);
    System.out.println("First element: " + values[0]); // 输出 100，显示了
}
```

### 5.2.3 返回类型的详细说明

方法的返回类型决定了它可以传回调用者的值的类型。返回类型在声明中紧跟在方法名称之前。方法可以返回任何类型的数据，包括基本类型、对象，甚至没有数据（`void`）。如果方法声明了返回类型（`void` 除外），则它必须使用 `return` 语句来返回该类型的值。

```java
public static double getAverage(int sum, int count) {
    return (double) sum / count;
}
```

### 5.2.4 从方法返回多个值

Java 方法只能返回一个值。然而，你可以通过使用数组或对象来封装多个值来绕过这一局限。

- 使用数组：适用于返回相同类型的多个值



```java
public static int[] minMax(int[] numbers) {
    int[] result = {numbers[0], numbers[0]}; // 假设数组不为空
    for (int num : numbers) {
        if (num < result[0]) result[0] = num; // 更新最小值
        if (num > result[1]) result[1] = num; // 更新最大值
    }
    return result; // 包含最小值和最大值的数组
}
```

- 使用对象：适用于返回不同类型的值，或者当你需要返回结构化数据时。

```java
class MinMax {
    int min;
    int max;

    MinMax(int min, int max) {
        this.min = min;
        this.max = max;
    }

    public static MinMax findMinMax(int[] numbers) {
        return new MinMax(/* 计算最小值的逻辑 */, /* 计算最大值的逻辑 */);
    }
}
```

理解参数及其类型，并掌握返回机制，是开发高效且灵活的 Java 程序的必备技能。

## 5.3 方法重载

### 5.3.1 方法重载的概念

方法重载是 Java 的一项特性，允许在同一个类中具有多个相同名称的方法。这种概念对于基本类型和引用类型行为在参数列表上有所不同。

### 5.3.2 不同参数类型的方法重载

方法重载允许方法处理不同的类型。

```java
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public double add(double a, double b) {
        return a + b;
    }
}
```

### 5.3.3 不同参数个数的方法重载

方法重载允许方法处理不同参数个数。

```java
public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public int add(int a, int b, int c) {
        return a + b + c;
    }
}
```

### 5.3.4 方法重载的最佳实践

虽然重载增加了灵活性，但遵循以下最佳实践很重要：

1. 谨慎使用重载：仅在合理时重载。
2. 保持逻辑一致性：确保重载方法执行相同的任务。
3. 使用清晰且描述性的参数：这有助于清晰度。
4. 针对相同类型考虑变长参数：这简化了调用。

## 5.4 理解作用域与访问性

### 5.4.1 方法中变量的作用域

变量的作用域决定了在代码的哪些部分可以访问它。方法变量（称为局部变量）定义在方法内部，并且仅在该方法内可用。它们在方法执行完成后就会消失。这种有限的作用域有助于减少命名冲突和内存占用。

```java
public void myMethod() {
    int local = 5;
}
```

### 5.4.2 全局变量与局部变量

- **局部变量**：这些变量定义在方法内部，只能在该方法内访问。它们在每次调用方法时初始化，并且在方法作用域外不可见。

```java
public void someMethod() {
    int localVar = 10; // 局部变量，在此可见
}
```

- **全局变量**：在 Java 上下文中，全局变量通常被称为字段或类变量。这些变量可以从类中的任何方法访问（取决于访问修饰符）。它们声明在方法之外，通常位于类的顶部。

```java
public class MyClass {
    int globalVar = 20; // 字段，类内任何方法均可访问

    public void anotherMethod() {
        System.out.println(globalVar); // 访问全局变量
    }
}
```

### 5.4.3 访问修饰符及其作用

Java 中的访问修饰符控制类字段（变量）和方法对其他类以及整个程序的可见性。理解它们对于控制访问级别和保护对象至关重要。

- **私有 (`private`)**：私有修饰符将可见性限制在声明的类内部。这是封装的核心原则，可以防止数据被意外访问和修改。
- **默认（无修饰符）**：允许在同一个包内访问字段和方法。它比私有更有访问性，但仍然提供受限的访问级别。
- **保护 (`protected`)**：与默认访问类似，额外允许子类（即使在不同的包中）也可以访问受保护的成员。
- **公共 (`public`)**：`public` 修饰符允许字段和方法被应用程序中的任何其他类访问。

```java
public class ModifierExample {
    private int privateVar = 1;
    int defaultVar = 2;
    protected int protectedVar = 3;
    public int publicVar = 4;
}
```

### 5.4.4 封装与受保护访问

封装是面向对象编程的一个基本原则。它将数据（属性）和操作数据的方法（函数）封装在一个单元（或类）中，并限制对数据细节的访问。

**实现封装**：在字段上使用 `private` 访问修饰符，并提供 `public` 的 getter 和 setter 方法来访问和更新值。

```java
public class EncapsulatedObject {
    private int id;

    // Getter
    public int getId() {
        return id;
    }

    // Setter
    public void setId(int id) {
        this.id = id;
    }
}
```

**受保护访问**：`protected` 访问通常在继承上下文中使用。它允许子类访问父类的字段和方法，在促进代码复用的同时，与 `public` 访问相比仍保持限制的访问级别。

```java
public class Base {
    protected int baseNumber;
}

public class Derived extends Base {
    public void show() {
        baseNumber = 10; // 由于受保护访问可以访问
        System.out.println("Base number is: " + baseNumber);
    }
}
```

理解作用域和访问性的差异可以显著影响 Java 应用的设计和安全性，确保数据完整性和系统健壮性。

# 面向对象编程基础

## 6.1 面向对象编程简介

### 6.1.1 OOP 概念概述

面向对象编程（OOP）是一种基于“对象”概念的编程范式，对象可以包含以字段（通常称为属性）的形式的数据，以及以过程（通常称为方法）的形式的代码。OOP 将现实世界的实体建模为具有状态和行为的对象，封装了操作数据的相关数据和函数。

OOP 的核心概念包括：

- **类（Classes）**：创建对象的模板，定义了它们的结构和行为。
- **对象（Objects）**：类的实例，代表特定的实体。
- **继承（Inheritance）**：一种从现有类创建新类的机制，增强了代码的可复用性。
- **多态（Polymorphism）**：在不同对象上调用相同方法并让它们以自己的方式做出响应的能力。
- **封装（Encapsulation）**：将数据和操作数据的方法封装在一个单元内，限制对对象某些组件的访问。

### 6.1.2 面向对象编程的优点

- **模块化（Modularity）**：对象的源代码可以独立与其他对象的源代码进行编写和维护。这使得管理大型应用程序变得更容易。
- **代码复用（Reuse of Code）**：通过继承可以从现有类派生新类，继承其属性和方法，从而实现显著的代码复用。
- **可扩展性（Scalability）**：OOP 允许通过增量添加新对象来构建程序，使得处理更大的软件项目变得可行。
- **维护（Maintenance）**：通过封装，对象可以隐藏其内部状态并在不影响代码其他部分的情况下更改，从而便于维护。
- **设计优势（Design Benefits）**：OOP 方法论鼓励设计阶段的规划和思考过程，使设计更加灵活、模块化和抽象。

### 6.1.3 OOP 对比 过程化编程

虽然 OOP 以对象和数据为组织代码，但过程化编程以过程或例程为中心。主要区别包括：

- **状态与行为**：在 OOP 中，数据（状态）和操作（行为）封装在一起；而在过程化编程中，过程对传入的数据进行操作。
- **模块化与维护**：OOP 为程序提供了更清晰的模块化结构，使得更容易跟踪程序元素、增强它们并修复错误。
- **可复用性和可扩展性**：得益于继承和多态，面向对象的程序鼓励软件组件的复用，而这在过程化方法中并不那么自然。

### 6.1.4 OOP 关键术语：类、对象、方法和属性

- **类（Class）**：创建对象的蓝图。类定义了对象的初始状态以及一组动作（方法）。
- **对象（Object）**：类的实例，代表特定的实体。
- **方法（Method）**：与类相关的过程。
- **属性（Property）**：对象的特征。

## 6.2 使用类和对象

### 6.2.1 定义类

在 Java 中，类是创建对象的模板，由大括号定义。它包含属性和方法。

```java
public class Car {
    // Attributes
    String model;
    int year;

    // Method
    void displayInformation() {
        System.out.println("Model: " + model + ", Year: " + year);
    }
}
```

### 6.2.2 创建和使用对象

对象是使用 `new` 关键字创建的类实例。一旦创建了对象就可以访问其属性并调用方法。

```java
public class TestCar {
    public static void main(String[] args) {
        // 创建 Car 对象
        Car myCar = new Car();
        myCar.model = "Toyota";
        myCar.year = 2020;

        // 使用 Car 方法
        myCar.displayInformation();
    }
}
```

### 6.2.3 实例变量和方法

实例变量和方法属于类的实例。对于每个创建的对象，每个实例都有自己的变量副本。

- **实例变量（Instance Variables）**：声明在类内部、方法之外的变量。它们在使用 `new` 关键字创建对象时创建，在对象销毁时销毁。
- **实例方法（Instance Methods）**：必须先创建类实例才能调用的方法。

### 6.2.4 静态变量和方法

静态变量和方法属于类而不是任何实例。这意味着可以在不创建对象的情况下访问它们。

- **静态变量（Static Variables）**：也称为类变量，由类的所有实例共享。对静态变量的任何更改都会反映在所有实例中。
- **静态方法（Static Methods）**：无需创建对象即可调用的方法。

```java
public class Counter {
    static int count = 0; // 静态变量

    static void increment() { // 静态方法
        count++;
    }
}
```

```java
public class Bicycle {
    int gear;
    int speed;

    // Constructor
    Bicycle(int gear, int speed) {
        this.gear = gear;
        this.speed = speed;
    }
}
```

## 6.3 构造函数

### 6.3.1 构造函数基础

构造函数是一种特殊的方法，用于初始化对象。它在创建对象时自动调用。

### 6.3.2 构造函数的类型：默认和参数化

- **默认构造函数（Default Constructor）**：如果类中没有显式定义构造函数，Java 会自动提供一个没有参数的默认构造函数，它除了实例化对象外什么都不做。但如果在类中显式声明了任何其他构造函数，则不会提供此默认构造函数。

```java
public class Example {
    // Java 将在这里创建一个默认构造函数。
}
```

- **参数化构造函数（Parameterized Constructor）**：包含参数的构造函数，用于在创建对象时初始化特定的状态。使用参数化构造函数，你可以在创建对象时为其提供不同的值。

```java
public class Book {
    String title;
    int pageCount;

    // 参数化构造函数
    Book(String title, int pageCount) {
        this.title = title;
        this.pageCount = pageCount;
    }
}
```

### 6.3.3 构造函数重载

构造函数重载（Constructor overloading）是 Java 中的一项特性，允许一个类拥有多个构造函数，这些构造函数接受的参数不同。它允许你根据创建对象时可用的信息以不同的方式创建对象。

```java
public class Rectangle {
    int length;
    int width;

    // 默认构造函数
    Rectangle() {
        this.length = this.width = 0;
    }

    // 参数化构造函数 1
    Rectangle(int side) {
        this.length = this.width = side;
    }

    // 参数化构造函数 2
    Rectangle(int length, int width) {
        this.length = length;
        this.width = width;
    }
}
```

### 6.3.4 构造链

构造链（Constructor chaining）是指相对于当前对象从一个构造函数调用另一个构造函数的过程。这可以通过 `this()` 和 `super()` 调用来实现。使用 `this()` 允许你调用同一类中的另一个重载构造函数，而 `super()` 调用父类中的构造函数。

```java
public class Student {
    String name;
    int age;

    // 有 1 个参数的构造函数
    Student(String name) {
        this(name, 18); // 调用有 2 个参数的构造函数
    }

    // 有 2 个参数的构造函数
    Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

- 使用 `super()`：

```java
class Person {
    String name;
    Person(String name) {
        this.name = name;
    }
}

class Teacher extends Person {
    int salary;
    Teacher(String name, int salary) {
        super(name); // 调用父类构造函数
        this.salary = salary;
    }
}
```

构造链通过允许构造函数利用另一个构造函数的初始化程序，简化了代码并消除冗余。

## 6.4 OOP 的支柱：封装、继承和多态

### 6.4.1 封装：使用访问修饰符保护数据

封装（Encapsulation）是面向对象编程中的一个基本概念，涉及将数据（属性）和处理数据的代码（方法）打包成一个单元。此外，它限制了对对象某些组件的直接访问，这是防止意外修改数据的一种手段。对受限组件的访问通常通过 getter 和 setter 方法实现。

Java 使用访问修饰符来保护变量和方法。常见的访问修饰符有：

- **Private（私有）**：成员仅在其所属类内部可访问。
- **Protected（受保护）**：成员在所属包内以及其子类中可访问。
- **Public（公共）**：成员可以从任何其他类进行访问。

```java
public class Account {
    private double balance;

    // Getter 方法
    public double getBalance() {
        return balance;
    }

    // Setter 方法
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }
}
```

### 6.4.2 继承：扩展类和代码复用

继承（Inheritance）允许一个类继承另一个类的方法和字段。在 Java 中，继承用于促进代码复用并建立类之间的关系。

#### 创建子类



要继承一个类，需使用 `extends` 关键字。被继承的类被称为父类（superclass），而继承它的类被称为子类（subclass）。

示例：

```java
class Vehicle {
    protected String brand = "Ford";
    public void honk() {
        System.out.println("Tuut, tuut!");
    }
}

class Car extends Vehicle {
    private String modelName = "Mustang";
    public static void main(String[] args) {
        Car myFastCar = new Car();
        myFastCar.honk();
        System.out.println(myFastCar.brand + " " + myFastCar.modelName);
    }
}
```

# 方法重写和 super 关键字

方法重写（Method overriding）发生在子类为其父类提供的方法提供了特定实现时。`super` 关键字用于访问被重写的方法。

示例：

```java
class Animal {
  void sound() {
    System.out.println("The animal makes a sound");
  }
}

class Pig extends Animal {
  @Override
  void sound() {
    super.sound(); // 调用父类方法
    System.out.println("The pig says: wee wee");
  }
}
```

# 6.4.3 多态：静态和动态

多态（Polymorphism）在 Java 中有两种类型：编译时（静态）和运行时（动态）。

## 方法重载

方法重载（Method overloading）发生在同一个类中，当两个或多个方法同名但参数不同时，属于静态多态。（注：此处原文示例代码有误，已按逻辑对应）

示例：

```java
class Display {
    void show(int x) {
        System.out.println("Show int: " + x);
    }

    void show(String s) {
        System.out.println("Show String: " + s);
    }
}
```

## 方法重写和动态方法分发

方法重写（Dynamic polymorphism）允许子类重写父类的方法。动态方法分发（Dynamic method dispatch）是一种在运行时而非编译时解析重写方法的机制。

```java
class Figure {
  double dim1;
  double dim2;

  Figure(double a, double b) {
    dim1 = a;
    dim2 = b;
  }

  double area() {
    System.out.println("Area for Figure is undefined.");
    return 0;
  }
}

class Rectangle extends Figure {
  Rectangle(double a, double b) {
    super(a, b);
  }

  // 重写 area
  @Override
  double area() {
    System.out.println("Inside Area for Rectangle.");
    return dim1 * dim2;
  }
}
```

# 6.4.4 抽象类和接口：强制合约

- **抽象类（Abstract Classes）**：抽象类不能实例化，包含抽象方法（即没有体的方法）。当你想在多个相关类之间共享代码时，可以使用它们。

```java
abstract class Animal {
    public abstract void sound();
}

class Dog extends Animal {
    public void sound() {
        System.out.println("Woof");
    }
}
```

- **接口（Interfaces）**：接口是一种完全“抽象的类”，用于组合一组空体的方法。类可以实现多个接口，克服了单继承的限制。

示例：

```java
interface Animal {
    void sound(); // 接口方法（没有体）
}

class Pig implements Animal {
    public void sound() { // 在这里提供 sound 的体
        System.out.println("The pig says: wee wee");
    }
}
```

# 7.1 实现继承

继承是面向对象编程（OOP）的核心概念之一。它允许一个类继承另一个类的属性和方法。在 Java 中，继承用于促进代码的复用并建立类之间的关系。

## 7.1.1 理解继承的基础

继承允许一个新类（称为子类或派生类）吸收另一个类（称为父类或基类）的成员（字段、方法和构造函数）。其主要优势是能够定义一个通用的基类，以便在多个派生类之间共享代码。

核心概念包括：

- **父类和子类**：父类是被其他类继承的类，而子类是继承自父类的类。
- **`extends` 关键字**：在 Java 中，类使用 `extends` 关键字来声明它继承自另一个类。

## 7.1.2 创建和扩展父类

创建父类涉及定义一个其他类将要继承自的普通类。使用 `extends` 关键字来扩展该类。例如，如果 `Animal` 是一个父类，创建一个继承自 `Animal` 的子类 `Dog` 可以如下所示：通过扩展 `Animal`，`Dog` 继承了 `eat` 方法，也可以定义自己的方法，例如 `bark`。

## 7.1.3 利用保护访问修饰符

`protected` 访问修饰符在继承中起着至关重要的作用。在父类中声明为 `protected` 的成员可以被子类访问（包括包外的子类），但无法被包外的其他类访问。

该修饰符有助于封装父类的成员，允许对它们进行受控的访问，而不是 `public` 访问（这可能会暴露过多父类的内部细节）或 `private` 访问（这会阻止子类访问重要成员）。

## 7.1.4 探索继承层次结构和多重继承问题

当一个类继承自子类时，就会产生继承层次结构，创建一个具有多个级别的类“族树”。这允许在每个子类层级上实现更具体的分类和行为。

Java 不支持通过类来实现多重继承，以避免“菱问题”（该问题是指一个类继承自两个具有相同签名方法的类，这可能会让编译器困惑应该调用哪一个方法）。然而，Java 通过允许类实现多个接口来解决多重继承的需求。

继承层次结构的示例：

```java
class Animal {
    void eat() {
        System.out.println("This animal eats.");
    }
}

class Mammal extends Animal {
    void breathe() {
        System.out.println("This mammal breathes.");
    }
}

class Bat extends Mammal {
    void fly() {
        System.out.println("This bat can fly.");
    }
}
```

在这里，`Bat` 继承自 `Mammal`，而 `Mammal` 又继承自 `Animal`，形成了一个层次结构。通过正确理解和实现继承，开发者可以创建灵活且可维护的代码库。

# 7.2 使用 'super' 和方法重写

`super` 关键字的使用和方法重写的概念在 Java 继承中起着重要作用，增强了功能性和多态性。

## 7.2.1 'super' 关键字在访问父类成员中的作用

Java 中的 `super` 关键字是一个引用变量，用于引用父类对象。它可以用于访问在子类中被重写或隐藏的父类方法和构造函数。

- **访问父类方法**：可以使用 `super` 调用在子类中被重写的父类方法。当你希望在子类中同时访问方法的父类和子类版本时，这特别有用。
- **调用父类构造函数**：`super()` 可以调用父类构造函数。`super()` 的调用必须是子类每个构造函数的第一个语句。如果子类构造函数没有显式调用父类构造函数，Java 编译器会自动插入对父类无参数构造函数的调用。

```java
class Animal {
    void move() {
        System.out.println("Animals can move");
    }
}

class Dog extends Animal {
    void move() {
        super.move(); // 调用 Animal 类中的方法
        System.out.println("Dogs can walk and run");
    }
}
```

## 7.2.2 在子类中重写方法

方法重写发生在子类重新定义父类中的方法时。重写允许子类对其父类提供的方法提供特定的实现。

重写规则：参数列表必须与被重写的方法完全匹配。返回类型也必须相同或是子类型（协变返回类型）。此外，子类不能重写声明为 `final` 或 `static` 的方法。

重写的示例：

```java
class Vehicle {
    void run() {
        System.out.println("The vehicle is running");
    }
}

class Car extends Vehicle {
    @Override
    void run() {
        System.out.println("The car is running safely");
    }
}
```

## 7.2.3 方法重写的规则和最佳实践

1. **签名匹配**：方法名和参数必须与父类中的方法签名完全匹配。
2. **访问级别**：访问级别不能比被重写方法的访问级别更严格。
3. **返回类型**：必须与父类方法的返回类型相同或为子类型（协变返回类型）。
4. **调用父类方法**：有时，在重写的方法中使用 `super` 调用父类版本是有益的。

遵循这些规则可以确保继承层次结构整洁、具有功能性且行为可预测。

## 7.2.4 注解 @Override 的重要意义

`@Override` 注解表示该方法意图重写父类中的方法。如果该方法实际上没有重写父类，编译器将产生错误。此注解提高了代码的清晰度，并帮助发现错误，例如拼错方法名或参数不匹配。

带有 `@Override` 的示例：

```java
class Animal {
    void eat() {
        System.out.println("This animal eats.");
    }
}

class Dog extends Animal {
    @Override
    void eat() {
        System.out.println("A dog eats.");
    }
}
```

# 7.3 接口和抽象类

接口和抽象类是 Java 中用于实现抽象和多重继承（通过接口）两个核心概念。它们为类设定了蓝图，指导类必须具备哪些方法。

## 7.3.1 定义和实现接口

Java 中的接口是一种引用类型，类似于类，但只能包含常量、方法签名、默认方法、静态方法和嵌套类型。接口不能包含实例字段。接口中的方法默认是抽象的。

要定义接口，你使用 `interface` 关键字。类实现接口，并且必须为接口中的所有抽象方法提供具体的实现。

```java
interface Animal {
    void eat();
    void travel();
}

class Mammal implements Animal {
    public void eat() {
        System.out.println("Mammal eats");
    }

    public void travel() {
        System.out.println("Mammal travels");
    }
}
```

## 7.3.2 接口与抽象类的比较

接口和抽象类都可以拥有抽象方法，但它们存在关键区别：

- **抽象类**：可以包含带有实现或不带实现的方法。子类只能扩展一个抽象类。
- **接口**：在 Java 8 之前，接口只能包含不带实现的抽象方法。从 Java 8 开始，它们可以包含默认方法和静态方法。一个类可以实现多个接口。

抽象类用于子类共享带有实现的方法的情况。接口通常用于定义一组公共功能，这些功能由任何类提供，无论其在类层次结构中的位置如何。

## 7.3.3 在接口中使用默认和静态方法

Java 8 引入了通过默认方法和静态方法在接口中定义具体方法的能力。这允许向接口中添加新功能，而不影响实现这些接口的类。

**默认方法**：允许在接口内部实现方法。实现接口的类可以重写默认方法。

```java
interface Vehicle {
  default void print() {
    System.out.println("I am a vehicle!");
  }
}
```

**静态方法**：可以在接口内部声明，且不能被实现类的类重写。

```java
interface Animal {
  static void test() {
    System.out.println("Static method in interface");
  }
}
```

## 7.3.4 应用接口实现多继承

在 Java 中，多继承——一个类继承自多个父类行为的能力——是不直接支持的（为了避免“菱形问题”）。然而，Java 允许通过接口实现类型多继承。类可以实现多个接口，从而继承多个源的抽象方法。

多继承的示例：

```java
interface WaterAnimal {
    void swim();
}

interface LandAnimal {
    void walk();
}

class Frog implements WaterAnimal, LandAnimal {
    public void swim() {
        System.out.println("Frog swims");
    }

    public void walk() {
        System.out.println("Frog walks");
    }
}
```

在这种配置下，`Frog` 类可以从 `WaterAnimal` 和 `LandAnimal` 接口继承行为（`swim` 和 `walk` 方法），展示了接口在克服 Java 单继承局限性方面的灵活性。

# 7.4 多态的实际应用

多态是面向对象编程的核心概念，它允许根据执行操作的实际对象来执行不同的操作。它增强了灵活性并在不修改代码的情况下扩展代码的能力。Java 中的多态有两种类型：静态（编译时）和动态（运行时）。

## 7.4.1 演示静态多态和动态多态

- **静态多态**通过方法重载实现。它发生在编译时。在静态多态中，对函数的响应由编译时的参数列表决定。

方法重载的示例：

```java
class Display {
    void show(int x) {
        System.out.println("Show with int: " + x);
    }

    void show(String s) {
        System.out.println("Show with String: " + s);
    }
}
```



- 动态多态通过方法重写实现，这意味着要调用的确切方法是在运行时根据对象的实例化确定的。动态多态的示例：

## 7.4.2 方法重载 vs 方法重写

- 方法重载（静态多态）：它允许一个类拥有多个同名方法，但方法签名不同（即不同的参数列表）。通过根据输入参数以不同方式处理相同的方法，它提高了代码的可读性和重用性。
- 方法重写（动态多态）：它允许子类为其父类中已经提供的方法提供特定的实现。子类中的方法在名称、返回类型和参数上必须与父类中的方法相同。

## 7.4.3 动态方法分发

动态方法分发是一种机制，其中对重写方法的调用在运行时而非编译时进行解析。这是 Java 实现运行时多态的方式。在这种场景下，引用类型 `Animal` 并不决定调用哪个版本的 `sound()`。要调用的方法是由实例类型在运行时决定的。

## 7.4.4 多态的现实世界示例

1. 图形用户界面 (GUI) 元素：不同的对象（如按钮、文本框和复选框）可能继承自一个公共父类（例如 `Component`）。每个对象都可能重写 `draw()` 方法来渲染自己。在遍历组件集合并调用 `draw()` 时，多态确保了每个元素都调用了正确的方法。
2. 支付处理系统：在支付系统中，不同的支付方式（信用卡、PayPal、银行转账）可能派自 `Payment` 父类。每种方法都有其自己的 `processPayment()` 方法实现。多态允许系统以统一的方式处理不同的支付类型，增强了代码的重用性和活性。

多态（无论是静态还是动态）在简化复杂性方面起着至关重要的作用，允许同一个接口用于不同的底层形式（数据类型或类），促进了代码的重用。

# 异常处理

## 理解异常

异常是程序执行过程中发生的、中断指令执行流的事件。在 Java 中，处理异常允许你的程序继续运行，而不是因为意外问题而崩溃。

### 8.1.1 什么是异常？

异常可以是程序遇到的任何错误状况或意外行为。当出现这种状况时，会创建一个表示该异常的对象，并从导致该异常的方法中抛出。如果该方法没有处理异常，运行时系统将尝试在调用栈中寻找另一个能够处理异常的方法。

### 8.1.2 异常类型

Java 中的异常主要分为两类：检异常（checked exceptions）和未检异常（unchecked exceptions）。

- 检异常：检异常是在编译时进行检查的异常，这意味着编译器要求代码要么处理这些异常或使用 `throws` 声明它们。检异常的存在标志着预期的但可以预防的问题，合理的应用程序应该预见到并从中恢复。检异常的一个示例是 `FileNotFoundException`。
- 未检异常：未检异常代表程序中的缺陷（bug）——通常是逻辑错误。这些异常在编译时不进行检查，而是在运行时检查。示例包括 `NullPointerException` 和 `ArrayIndexOutOfBoundsException`。

### 8.1.3 异常层次结构

所有异常类都是 `Throwable` 类的后代。`Throwable` 类分为两个主要的子类：`Error`（用于普通应用程序不应尝试捕获的错误状况）和 `Exception`，后者进一步分为检异常和运行时异常（未检异常）。

### 8.1.4 常见异常场景和处理策略

- 输入/输出操作：这些操作很容易因为许多原因失败，如文件不存在或硬件故障。处理策略包括使用 `try` 处理这些异常或使用 `throws` 声明它们。
- 空指针访问：像访问数组一样访问或修改 `null` 的槽位。在访问方法或字段之前进行预防性的空检查可以缓解这种问题。
- 数组索引越界：尝试访问超出数组大小的元素。在访问数组之前确保索引边界检查可以防止此类问题。
- 类型转换异常：尝试将对象转换为其不是其实例的子类。可以通过在转换之前使用 `instanceof` 检查来防止这种异常。

以受控的方式捕获并处理异常，确保程序能够从错误中恢复并执行必要的清理操作。

## 8.2.1 try 块

`try` 块允许你定义一段代码块，并在执行时对其进行错误测试。

### 在 try 块中编写易异常的代码

任何可能抛出异常的代码都应该包含在 `try` 块中。例如，处理文件操作、解析或网络连接的代码经常遇到异常情况，是放入 `try` 块的理想选择。

示例：

```
try {
    // 可能会抛出异常的代码
    FileReader fr = new FileReader("file.txt");
    // 使用文件...
} catch (FileNotFoundException e) {
    // 处理异常
}
```

## 8.2.2 catch 块

`catch` 块用于处理异常。它必须在 `try` 块之后使用。在括号内，你指定了想要捕获的异常类型。

### 处理不同的异常

不同类型的异常可以被不同的捕获和处理。良好的做法是先捕获特定异常，然后捕获更通用的异常，以提供更详细的错误处理。

### 多个 catch 块

一个 `try` 块可以跟随多个针对不同异常类型的 `catch` 块。这允许对每种异常类型进行特定处理。

示例：

```
try {
    // 可能会抛出多个异常的代码
} catch (ArithmeticException e) {
    // 对 ArithmeticException 的特定处理
} catch (NullPointerException e) {
    // 对 NullPointerException 的特定处理
}
```

### 8.2.3 finally 块

`finally` 块包含在 `try` 和 `catch` 块执行后必须执行的代码，无论是否捕获到异常。

#### 保证资源释放和清理操作

`finally` 块是清理代码的理想选择，例如关闭文件流或释放网络连接，以确保资源不泄漏。

`try`、`catch` 和 `finally` 块的组合提供了一种处理异常的健壮机制，确保你的程序能够地处理错误并维护资源的完整性。

### 8.3 创建自定义异常

自定义异常允许开发者创建特定的错误条件，这些条件可以更具描述性且更符合应用程序的需求。通过定义特定于应用程序领域的异常，它们为错误处理增加了清晰度。

#### 8.3.1 为什么要创建自定义异常？

自定义异常提供了多处好处：

- 增强语义化：通过清晰地指示发生的特定问题，可以使你的代码更可读、更易理解。
- 一致的错误报告：允许在整个应用程序中统一的错误报告和处理。
- 特定异常处理：能够创建针对应用程序需求进行精细调整的异常处理机制。

### 8.3.2 扩展异常类

在 Java 中创建自定义异常，只需扩展 `Exception` 类或其任何子类。

示例：

```
public class MyCustomException extends Exception {
    public MyCustomException(String message) {
        super(message);
    }
}
```

如果你倾向于创建一个未检查异常，也可以扩展 `RuntimeException`。

### 8.3.3 实现自定义异常逻辑

在创建自定义异常时，你可以添加额外的字段和方法，以提供更多关于错误条件的信息。

示例：

```
public class DatabaseConnectionException extends Exception {
    private String dbName;

    public DatabaseConnectionException(String dbName, String message) {
        super(message);
        this.dbName = dbName;
    }

    public String getDbName() {
        return dbName;
    }
}
```

此示例包含一个接受数据库名称和错误信息的构造函数，并提供了一个数据库名称的 getter 方法。

### 8.3.4 在应用程序中使用自定义异常

自定义异常可以像其他异常一样在你的应用程序中使用，额外的好处是更具表达力。

示例：

```
public class DatabaseService {
    public void connectToDatabase(String dbName) throws DatabaseConnectionException {
        if (dbName == null || dbName.isEmpty()) {
            throw new DatabaseConnectionException(dbName, "Database name cannot be");
        }
        // 尝试连接数据库
        // 如果连接失败，抛出 DatabaseConnectionException
    }
}

public class App {
    public static void main(String[] args) {
        DatabaseService dbService = new DatabaseService();
        try {
            dbService.connectToDatabase("myDatabase");
        } catch (DatabaseConnectionException e) {
            System.err.println("Failed to connect to database " + e.getDbName());
        }
    }
}
```

在此示例中，一个自定义异常（`DatabaseConnectionException`）被抛出并捕获，允许对错误条件做出清晰且有意义的响应。

在应用程序中创建和使用自定义异常可以大大提高错误处理代码的清晰度和可维护性，使你的应用程序更加健壮和友好。

## 8.4 异常处理的最佳实践

适当的异常处理对于维护软件的可靠性和可读性至关重要。遵循最佳实践不仅让你的代码更健壮，而且更易维护。

### 8.4.1 避免常见陷阱

异常处理中的某些做法可能导致难以维护或调试的代码。避免这些陷阱对于编写简洁有效的异常处理代码至关重要。

#### 捕获通用异常

捕获基类 `Exception`（或 `Throwable`）可能会使诊断变得困难，因为可能会捕获比预期更多的异常，包括你希望向上抛出或以方式处理的异常。相反，应尽可能捕获特定异常。

糟糕的做法：

```
try {
    // 风险代码
} catch (Exception e) {
    // 通用处理
}
```

更好的方法：

```
try {
    // 风险代码
} catch (SpecificException e) {
    // 特定处理
}
```

#### 忽略异常

静默捕获并忽略异常可能会导致程序处于不可预测的状态，难以诊断问题。

糟糕的做法：

```
try {
    // 风险代码
} catch (Exception e) {
    // 忽略
}
```

更好的方法：

始终以有意义的方式处理异常，或者至少将其记录。

```
try {
    // 风险代码
} catch (Exception e) {
    log.error("发生错误", e);
}
```

### 8.4.2 使用 finally 进行清理

无论是否抛出异常，你通常都需要执行某些清理代码（例如关闭文件流或数据库连接）。`finally` 块确保这些代码被执行。

```
FileReader fr = null;
try {
    fr = new FileReader("file.txt");
    // 使用文件...
} catch (FileNotFoundException e) {
    // 处理异常
} finally {
    if (fr != null) {
        try {
            fr.close();
        } catch (IOException e) {
            // 处理或记录 IOException
        }
    }
}
```

### 8.4.3 文档异常行为

使用 JavaDoc 中的 `@throws`（或 `@exception`）标签记录你的方法可能抛出的异常。这些文档对于使用你方法的其他开发者至关重要，让他们了解涉及的风险以及如何处理潜在问题。

```java
/**
 * 连接到指定的数据库。
 *
 * @param dbName 数据库名称。
 * @throws DatabaseConnectionException 如果连接失败则抛出异常。
 */
public void connectToDatabase(String dbName) throws DatabaseConnectionException {
    // 实现
}
```



### 8.4.4 异常处理与应用程序设计决策

异常处理应该是初始设计阶段的一部分，而不是事后补救。应尽早决定哪些异常应该是受检的/未检查的，如何使用自定义异常进行更清晰的错误报告，并建立应用程序不同层级处理异常的准则。

设计良好的异常处理可以极大提高应用程序的健壮性、可维护性和用户体验。它是影响软件整个生命周期中架构和设计决策的关键方面。

# 深入理解 Java 集合框架

## 9.1 Java 集合概述

Java 集合框架（简称 `JCF`）是一组实现常用的可重用集合数据结构的类和接口。它是 Java 最强大且最灵活的 API 之一，包含了多种可以动态存储对象的数据结构。

### 9.1.1 集合框架简介

集合框架在 Java 2 中引入，为表示和操作集合提供了一个统一的体系。它极大地改进了处理对象集合的方式，允许通过一致的 API 进行数据操作。该框架包含了 `List`、`Set` 和 `Map` 等接口，以及 `ArrayList`、`HashSet` 和 `HashMap` 等实现类。

### 9.1.2 Collection 接口

框架的核心是 `Collection` 接口，它为所有集合类型提供了标准功能。`Collection` 接口是 `List`、`Set` 和 `Queue` 等接口的基础，每个接口都服务于不同的抽象数据类型。实现类必须提供常见操作的功能，如添加、删除和查询集合的大小。

### 9.1.3 集合的主要特性

集合的主要特性包括：

- **动态大小**：与数组不同，集合的大小可以动态增长或缩小，根据需要容纳更多元素。
- **类型安全**：泛型允许集合强制类型安全，确保只存储指定类型的对象，从而减少运行时错误。
- **可迭代性**：可以使用迭代器（`iterator`）或增强 `for` 循环对集合进行迭代，使得遍历和操作元素变得更容易。
- **数据操作**：集合提供了添加、删除和搜索元素的方法，比原始数据类型或数组提供了更大的灵活性。

### 9.1.4 集合、数组和原始数据类型的比较

集合与数组及原始数据类型在多个方面有所不同：

- **大小与灵活性**：集合是动态的，而数组具有固定大小。集合比数组提供了更高的灵活性和功能。
- **性能**：对于添加或删除元素等某些操作，由于增加了抽象，集合可能比数组慢。然而，某些集合类型针对特定操作进行了优化。
- **类型安全与工具方法**：集合支持泛型，与数组相比增强了类型安全。此外，集合框架提供了排序和搜索等常见任务的工具方法，而这些任务在数组上非常繁琐。

### 9.1.5 选择合适的集合

选择合适的集合类型取决于几个因素：

- **顺序**：如果你需要维护插入顺序，请考虑 `ArrayList` 或 `LinkedHashSet`。
- **重复**：如果你的集合不能包含重复元素，请使用 `HashSet` 等 `Set` 实现。
- **键值对**：为了高效检索通过键值对存储数据，请使用 `HashMap` 等 `Map` 实现。
- **访问**：如果你需要通过索引快速访问元素，请使用 `ArrayList` 等 `List` 实现。
- **并发**：在多线程环境中工作时，请考虑使用 `java.util.concurrent` 包中的线程安全或并发集合。

选择合适的集合类型可以同时优化代码的性能和可读性，这使得集合框架成为高效 Java 开发的基石。

## 9.2 Lists、Sets 和 Queues

Java 集合框架将其数据结构划分为几个核心接口，每个接口服务于不同的数据管理目的。其中，`List`、`Set` 和 `Queue` 接口是基础性的，每个都满足特定的需求。

Java 中的 `List` 接口允许元素的有序集合，包括重复元素。`List` 在元素插入顺序很重要或需要对元素进行直接位置访问的场景中表现出色。

### 9.2.1 List 实现类

#### ArrayList

- **描述**：一种基于可调整大小数组的 `List` 接口实现。它通过索引快速访问元素。
- **用例**：适用于插入和删除操作极少但有大量访问操作场景。
- **关键特性**：自动调整大小，快速的随机访问。

#### LinkedList

- **描述**：一种 `List` 和 `Deque` 接口的双链表实现。它允许在列表的开头或结尾进行常数时间的插入和删除。
- **用例**：适用于需要频繁插入和删除的应用。
- **关键特性**：每个元素（节点）都包含指向前一个和下一个节点的引用。

#### Vector 和 Stack

- **Vector 描述**：一种同步的、可调整大小的数组实现。比 `ArrayList` 慢，但适用于线程安全操作。
- **Stack 描述**：一种继承自 `Vector` 的后进先出（LIFO）对象栈。它实现了传统的栈操作。
- **用例**：`Vector` 用于需要动态数组的线程安全应用程序。`Stack` 用于深度优先搜索算法和撤销机制。

### 9.2.2 探索 Set 接口

`Set` 接口模拟了数学中的集合抽象，适用于存储不重复元素，而无需担心它们的顺序。

#### HashSet

- **描述**：实现 `Set` 接口，由哈希表支持。它是性能最好的实现，但不提供任何顺序保证。
- **用例**：当元素的唯一性优于顺序时是理想。
- **关键特性**：基本操作具有常数时间性能（假设哈希函数能够良好地分散元素）。

#### LinkedHashSet

- **描述**：`HashSet` 的有序版本，在所有元素之间维护一个双链表。它按照插入顺序进行迭代。
- **用例**：当迭代顺序需要可预测，但又必须保持元素唯一性时有用。
- **关键特性**：由于增加了列表维护开销，比 `HashSet` 稍慢。

#### TreeSet

- **描述**：实现 `NavigableSet` 接口并根据其值组织元素。它由 `TreeMap` 支持。
- **用例**：适用于对快速检索和排序顺序重要的大型集合。
- **关键特性**：保证基本操作（添加、删除）的时间复杂度为 log(n)。

### 9.2.3 使用 Queue 接口

队列（`Queue`）支持典型的队列操作：提供（`offering`）、取队（`polling`）和检查元素（`inspecting`），主要满足 FIFO（先进先出）顺序。

#### PriorityQueue

- **描述**：一种基于优先级堆的无界优先级队列。元素根据它们的自然顺序或构造时提供的 `Comparator` 进行排序。
- **用例**：适用于你希望根据优先级而非插入顺序来处理元素的场景。
- **关键特性**：不允许 `null` 元素。

#### Deque 接口

一种支持在两端进行元素插入和删除的线性集合。它是栈和队列的泛化。

#### ArrayDeque

- **描述**：一种 `Deque` 接口的可调整大小数组实现。当被作栈或队列使用时，比 `Stack` 和 `LinkedList` 快。
- **关键特性**：没有容量限制。

#### 作为 Deque 的 LinkedList

- **描述**：虽然 `LinkedList` 主要是一个列表，但它也实现了 `Deque` 接口，支持两端的操作。
- **用例**：适用于同时需要列表和队列功能的情况。
- **关键特性**：双链表实现允许常数时间的插入和删除。

## 9.3 Map 接口及实现类

### 9.3.1 常用 Map 实现类

#### HashMap

- **描述**：实现了 `Map` 接口，使用哈希表。它允许 `null` 值和一个 `null` 键，在假设哈希函数能够很好地分散到各个桶中，基本操作（`get` 和 `put`）具有常数时间性能。
- **用例**：当插入顺序不重要且需要快速访问元素时，使用效果最佳。
- **关键特性**：对 `HashMap` 视图（键、值、条目）的迭代取决于哈希表的容量和键值对的数量。

#### LinkedHashMap

- **描述**：一个内部运行着链表的 `HashMap`，因此它维护了插入顺序（或可选的访问顺序）。除了排序行为外，它的特性与 `HashMap` 相同。
- **用例**：在需要保留插入/访问顺序的场景中非常有用。
- **关键特性**：由于为了维护顺序而增强了数据结构，其在迭代方面的性能略低于 `HashMap`。

#### TreeMap

- **描述**：实现了 `NavigableMap` 接口，并根据键的自然顺序或指定的 `Comparator` 对键进行排序。它基于红黑树结构。
- **用例**：当你需要提取键的范围或要求键进行排序时，它是理想的选择。
- **关键特性**：为 `containsKey`、`get`、`put` 和 `remove` 操作提供了保证的 log(n) 时间成本。

### 9.3.2 比较 Map 实现类

| 特性/Map 类型 | HashMap | LinkedHashMap | TreeMap |
|---|---|---|---|
| 排序 | 无顺序 | 插入/访问顺序 | 排序顺序 |
| Get/Put 时间 | 平均 O(1) | 平均 O(1) | O(log n) |
| 迭代顺序 | 随机 | 插入/访问顺序 | 键的升序 |
| 键的可空性 | 允许一个 null key | 允许一个 null key | 不允许 null key（如果使用自然排序） |
| 用例 | 需要映射的最常见场景 | 当插入/访问顺序很重要时 | 需要排序顺序或范围搜索时 |

### 9.3.3 特殊 Map 实现类

#### WeakHashMap

- **描述**：一种 `HashMap` 变体，将键作为弱引用存储。当 `WeakHashMap` 中的键不再被普通使用时，该条目将自动被移除。
- **用例**：适用于缓存和元数据存储，其中存储数据的生命周期取决于对键的外部引用。
- **关键特性**：当键不再被引用时，垃圾回收器会自动删除条目。

#### EnumMap

- **描述**：一种专门用于枚举（`enum`）类型键的特殊 `Map` 实现。`EnumMap` 中的所有键都来自创建 map 时显式或隐式指定的单个枚举类型。
- **用例**：当使用枚举进行基于键的数据访问时，极其高效且紧凑。
- **关键特性**：map 的迭代顺序遵循枚举键的自然顺序。

#### Hashtable (遗留类)

- **描述**：一种 map 数据结构的早期实现，它是同步的，这意味着它是线程安全的，但在单线程场景下与 `HashMap` 相比，性能较低。
- **用例**：现在被认为是遗留类，在存在 `ConcurrentHashMap`（用于线程安全的 map）的情况下，它很少被推荐使用。
- **关键特性**：与 `HashMap` 不同，它不允许 `null` 键或值。

选择正确的 `Map` 实现类可以极大影响你的 Java 应用程序的性能和资源消耗，特别是在处理大型数据集或对性能敏感的应用程序时。

## 9.4 Collection 类工具类

Java 集合框架不仅提供了多种数据结构，还通过 `Collections` 类包含了一套强大的工具类。这些工具类提供了用于排序、搜索、修改和转换集合的方法，增强了高效管理和操作数据的能力。

### 9.4.1 排序集合

排序是集合的一种基本操作，允许其元素按特定顺序排列。

#### 使用 Comparable

- **描述**：`Comparable` 接口提供单一的 `compareTo` 方法，定义了对象的自然顺序。实现此接口的类可以很容易地排序。
- **工作原理**：将对象与另一个对象进行比较以确定顺序，根据该对象小于、等于或大于指定对象，返回一个负整数、零或正整数。

#### 使用 Comparator

- **描述**：`Comparator` 接口定义了 `compare` 方法，允许在对象外部控制对象的顺序。当一个类无法修改以实现 `Comparable` 时，或者需要多个排序顺序时，它特别有用。
- **工作原理**：它比较它的两个参数以确定顺序，根据第一个参数是小于、等于还是大于第二个参数，返回负整数、零或正整数。

### 9.4.2 在集合中搜索

- **技术**：`Collections.binarySearch()` 提供了一种在已排序列表中搜索特定对象的高效方法。该集合必须根据其元素的自然顺序（或使用指定的 `Comparator`）按升序排序。

### 9.4.3 集合与数组之间的转换

- **方法**：集合接口中的 `toArray()` 方法将集合转换为数组。相反，`Arrays.asList()` 提供了一个由指定数组支持的固定大小列表，作为基于数组的 API 和基于集合的 API 之间的桥梁。

### 9.4.4 Collections 类工具类概览

#### Collections.sort()

- 将列表按升序排序，可以使用其元素的自然顺序（`Comparable`）或使用指定的 `Comparator`。

#### Collections.binarySearch()

- 使用二分查找算法在给定的排序列表中搜索指定对象，这需要一个有序集合才能获得有意义的结果。

#### Collections.reverse(), Collections.shuffle(), 以及更多

- `Collections.reverse()` 反转列表的顺序。
- `Collections.shuffle()` 随机化元素的顺序。
- 这些及更多方法提供了方便的修改工具类。

### 9.4.5 使用 synchronizedList, synchronizedSet, synchronizedMap 实现线程安全

- **目的**：包装标准集合并返回它们的线程安全版本。当集合被多个线程访问时至关重要。
- **注意事项**：对返回的集合进行迭代必须手动同步。

### 9.4.6 高级工具类

#### Collections.unmodifiableCollection 及其他不可变封装

- 提供集合的只读访问，修改尝试将抛出 `UnsupportedOperationException`。

#### 使用 singleton(), emptyList() 和 emptyMap()

- 这些方法适用于优化，在需要时减少内存占用并提高性能。
- 它们返回不可变实例，确保集合无法被修改。

`Collections` 类是 Java 集合框架的基石，提供了重要的工具类，增强了 Java 中集合操作的多样性和功能性。

## 10.1 文件处理与流操作

### 10.1.1 读取文件

读取文件是文件处理的基础操作。`InputStream` 和 `FileReader` 分别适用于二进制数据和字符数据的读取。

### 10.1.2 写入文件

写入文件同样非常灵活。`OutputStream` 和 `FileWriter` 分别适用于二进制数据和字符数据。对于追加数据，这些类的构造函数接受一个布尔参数，用以指示是否将内容追加到文件末尾。

### 10.1.3 追加数据

当你想要向文件的现有内容添加内容而不覆盖原有内容时，可以使用支持追加模式的构造函数或方法。在 NIO 中，`Files.write(Path, byte[], StandardOpenOption.APPEND)` 方法方便了这种操作。

### 10.1.4 Try-with-Resources 和 AutoCloseable 接口

文件处理和流操作中的一个重要问题是确保在使用后正确关闭资源以防止资源泄漏。Java 7 引入的 `try-with-resources` 语句简化了这项任务。它在语句执行结束时自动管理资源的关闭。为了兼容此语句，资源必须实现 `AutoCloseable` 接口，该接口包含了大多数流和相关资源。以下是一个简洁的用法示例：

```
try (FileReader reader = new FileReader("input.txt")) {

    int data;

    while ((data = reader.read()) != -1) {

        System.out.print((char) data);

    }

} catch (IOException e) {

    e.printStackTrace();

}
```



在这个示例中，`FileReader` 是实现 `AutoCloseable` 的资源。一旦退出 `try` 块（无论是正常退出还是由于异常），它就会自动关闭，显著减少了样板代码并最小化了资源泄漏的风险。

## 10.2 NIO 包

### 10.2.1 Java NIO 简介

Java NIO（新输入/输出）在 Java 1.4 中引入，作为标准 Java I/O API 的替代方案和补充。它提供了非阻塞 IO 操作、面向缓冲区的数据处理方法，以及通过单个线程管理多个网络连接的能力。NIO 的核心组件包括通道（Channels）、缓冲区（Buffers）、选择器（Selectors）和字符集，能够实现更快、更具扩展性的 I/O 操作，特别是对于需要同时管理大量连接的应用程序（如 Web 服务器）。

### 10.2.2 缓冲区：NIO 的核心

缓冲区（Buffers）是 NIO 的核心概念，代表一个连续的内存块，数据在 I/O 操作期间临时存储在其中。与传统的 I/O 模型中以线性、顺序方式处理数据的流不同，缓冲区允许随机读写数据。Java NIO 中的缓冲区是带类型的；即，针对不同类型的数据类型（如 `ByteBuffer`、`CharBuffer`、`IntBuffer` 等）有独立的缓冲区类。这些缓冲区在 `flip` 机制下运行，缓冲区从写入模式切换到读取模式，确保了数据的高效访问和处理。

### 10.2.3 通道：处理 IO 的新方式

通道（Channels）可以被看作是管道，数据在缓冲区和外部实体（例如文件或网络套字）之间传输。它们提供了一个统一的 API，用于管理各种类型的文件读写 I/O 操作以及网络通信。主要的通道类型包括用于文件 I/O 的 `FileChannel`、用于 TCP 网络 I/O 的 `SocketChannel` 以及用于 UDP 网络 I/O 的 `DatagramChannel`。与流不同，通道支持在同一个实例上同时读取和写入，从而提供了更灵活、更强大的数据处理能力。

### 10.2.4 选择器：使用 NIO 进行多路复用

选择器（Selector）组件允许单个线程监控多个通道事件的机制，例如数据到达、连接打开或读/写就绪。这种能力能够开发无需为每个连接创建一个线程的高度扩展性网络应用程序，显著减少了资源消耗并提高了性能。通过向选择器注册多个通道，应用程序可以以后阻塞的方式高效管理数千个打开的连接，检查 I/O 事件并在发生时进行处理。这对于实现处理许多并发连接的服务器（如 Web 或应用服务器）特别有用。

Java NIO 引入缓冲区、通道和选择器标志着 Java I/O 能力的重大增强，为开发者提供了构建高度可扩展且高效的网络和文件 I/O 应用程序的工具。从基于流的模型向面向缓冲区的模型转变，使得数据处理具有更多的控制和灵活性，使 Java NIO 成为现代 Java 应用开发中的核心组件。

## 10.3 在 Java 中读写文件

### 10.3.1 使用 FileInputStream 和 FileOutputStream

`FileInputStream` 和 `FileOutputStream` 是 `java.io` 包中的类，设计用于以字节流的形式读取和写入文件，使它们在处理图像和可执行文件等二进制数据时非常有效。

- `FileInputStream`：用于从文件中读取数据。数据以字节格式读取，意味着它是逐字节读取的，因此适合读取二进制文件。

```
FileInputStream fis = new FileInputStream("example.txt");

int i;

while ((i = fis.read()) != -1) {

    System.out.print((char) i);

}

fis.close();
```

- `FileOutputStream`：此类用于向文件写入数据。与 `FileInputStream` 类似，它逐字节地处理数据。它对于向文件写入二进制数据特别有用。

```
FileOutputStream fos = new FileOutputStream("output.txt");

String data = "Hello World!";

fos.write(data.getBytes());

fos.close();
```

### 10.3.2 Reader 和 Writer 类

对于面向字符的数据（如文本文件），Java 在 `java.io` 包中提供了 `Reader` 和 `Writer` 抽象类。

- `FileReader` 和 `FileWriter` 是读取和写入字符的子类。与字节流（`FileInputStream`/`FileOutputStream`）不同，这些设计用于处理字符，使其非常适合处理文本。

### 10.3.3 使用 Files 类进行高效 IO

`java.nio.file` 中的 `Files` 类提供了一系列用于操作文件和目录的静态方法。这些方法使用 `Path` 对象，使得文件操作更加高效。

- 读取文件：

```
Path path = Paths.get("example.txt");

byte[] fileArray = Files.readAllBytes(path);
```

- 写入文件：

```
Path newPath = Paths.get("newfile.txt");

byte[] data = "Sample text".getBytes();

Files.write(newPath, data, StandardOpenOption.CREATE);
```

### 10.3.4 Path 和 Paths：NIO 增强

Java 7 引入的 NIO.2 文件 API 增加了 `Path` 接口和 `Paths` 工具类，为文件系统提供了更全面的方法。

- `Path`：表示系统的路径。它是用于定位文件的对象，提供了检查、定位和操作文件对象的方法。
- `Paths`：一个工具类，包含静态方法可以将路径字符串转换为 `Path`。

采用 `Files` 类以及 `Path`/`Paths` 接口可以使 I/O 操作的代码更具可读性和维护性，并提供了符号链接处理、文件属性访问和目录遍历等高级功能，这些功能在传统的流中是直接实现的。

## 10.4 理解字节流和字符流

### 10.4.1 字节流与字符流的区别

Java I/O 流分为两大类：字节流和字符流。字节流（`InputStream` 和 `OutputStream` 的子类）主要用于处理原始二进制数据，如图像文件、音频文件和序列化对象。它们逐字节读写数据。字符流（`Reader` 和 `Writer` 子类）则设计用于处理字符数据，如文本文件。它们逐字符读写数据，自动处理字符编码和解码，从而简化了字符与字节转换的复杂性。

### 10.4.2 何时使用字节流而非字符流

当处理原始数据或不一定代表字符的二进制文件时应使用字节流。示例包括：

- 读取或写入二进制文件（如图像、视频）。
- 处理序列化对象。
- 与来自或发往不产生字符的数据流交互。

不表示文本数据。在处理文本数据时推荐使用它们，因为它们考虑了字符编码，这对于国际化至关重要。用例包括：

- 读取或写入包含文本的文件。
- 处理源或目标是基于文本的数据流，例如文档文件或标准 I/O。

### 10.4.3 常见的字节流和字符流类

字节流类：

- `FileInputStream` 和 `FileOutputStream` 用于读取和写入文件。`BufferedInputStream` 和 `BufferedOutputStream` 用于缓冲 I/O 操作，通过减少所需的 I/O 操作次数来提高效率。

字符流类：
- `FileReader` 和 `FileWriter` 用于读取和写入文本文件。`BufferedReader` 和 `BufferedWriter` 为字符输入输出流提供缓冲，使文本的读写更高效。

### 10.4.4 流操作的性能提示

- 使用缓冲流：将文件流封装在缓冲流（`BufferedInputStream`、`BufferedOutputStream`、`BufferedReader`、`BufferedWriter`）中，可以通过减少 I/O 操作次数来显著增强性能。
- 复用对象：在可能的情况下，在程序中复用 I/O 对象，以尽可能的减少创建和销毁资源的开销。
- 正确关闭资源：始终使用 `finally` 块关闭流或使用 `try-with-resources` 语句，以确保所有资源都能释放，底层文件或套接字得到关闭。
- 限制资源分配：注意循环或递归调用中的资源分配。在循环内部打开文件而不进行适当关闭可能会导致资源泄漏。
- 使用 NIO 处理大数据量：对于处理大文件或需要可扩展 I/O 操作的应用（如读取、写入或传输大文件），考虑使用 Java NIO 包，因为它提供了通道（channels）和缓冲区（buffers），可以更高效地处理这些场景。

应用这些性能提示将带来更高效、可扩展且可维护的 Java 应用程序，充分利用 I/O 流来读写数据。

# Java 并发与多线程

## 11.1 Java 线程基础

### 11.1.1 使用 Thread 类和 Runnable 接口创建线程

Java 线程有两种主要的创建方式：继承 `Thread` 类和实现 `Runnable` 接口。

继承 `Thread` 类：这种方法涉及创建一个继承 `Thread` 的新类并重写其 `run()` 方法。可以创建该类的实例并使用其 `start()` 方法启动它。

```java
class MyThread extends Thread {

    public void run() {

        // 在新线程中运行的代码

        System.out.println("Thread running: " + Thread.currentThread().getName());

    }

}

public class ThreadExample {

    public static void main(String[] args) {

        MyThread myThread = new MyThread();

        myThread.start(); // 启动线程

    }

}
```

实现 `Runnable` 接口：在这种方法中，类实现 `Runnable` 接口及其 `run()` 方法。然后创建一个 `Thread` 实例，并将实现接口的类实例传递给其构造函数。

```java
class MyRunnable implements Runnable {

    public void run() {

        // 在新线程中运行的代码

        System.out.println("Thread running: " + Thread.currentThread().getName());

    }

}

public class RunnableExample {

    public static void main(String[] args) {

        Thread thread = new Thread(new MyRunnable());

        thread.start(); // 启动线程

    }

}
```

### 11.1.2 线程生命周期和状态

Java 中的线程可以处于以下状态之一：

1. New（新建）：线程已创建但尚未启动。
2. Runnable（可运行）：线程可能正在运行，或已准备好运行并在等待资源分配。
3. Blocked（阻塞）：线程被阻塞等待监视器锁。
4. Waiting（等待）：线程无限期等待另一个线程执行特定操作。
5. Timed Waiting（计时等待）：线程等待另一个线程执行操作的最长指定的等待时间。
6. Terminated（已终止）：线程已完成执行。

### 11.1.3 线程优先级和守护线程

- 线程优先级：Java 提供了通过 `setPriority(int priority)` 方法为线程分配优先级（最小：1，最大：10）的机制。高优先级线程优先于低优先级线程执行，尽管由于实现的原因这并不是一个严格的保证。
- 守护线程（Daemon Threads）：Java 中的守护线程是一种服务线程，不会阻止 JVM 退出。使用 `setDaemon(true)` 方法进行标记。

### 11.1.4 处理 InterruptedException

当线程在等待、睡眠或其他被占用时，会抛出 `InterruptedException`。正确处理此异常至关重要。

```java
class MyRunnable implements Runnable {

    public void run() {

        try {

            Thread.sleep(1000);

        } catch (InterruptedException e) {

            System.out.println("Thread was interrupted");

        }

    }

}
```

## 11.2 同步与线程间通信

### 11.2.1 Synchronized 关键字和内置锁

Java 中的同步对于确保只有一个线程可以访问资源至关重要。`synchronized` 关键字可以标记方法或代码块，以便只有一个线程可以执行它。

- 同步方法：当方法被声明为 `synchronized` 时，它会锁定其调用的对象监视器。

```java
public synchronized void increment() {

    count++;

}
```

- 同步块：同步块比同步方法更灵活，因为允许在不同的对象上锁定，并可以覆盖方法的一部分。

```java
synchronized(this) {

    count++;

}
```

### 11.2.2 Volatile 关键字和内存可见性

Java 中的 `volatile` 关键字确保对变量的变化可以预测地传播到其他线程。当字段被声明为 `volatile` 时，编译器和运行时会被该变量是共享的，对其修改不应缓存或重排序。

用例：当不同线程修改变量的值，但对变量的操作不依赖于其当前值时，使用了 `volatile` 变量。

```java
private volatile boolean active;

public void stop() {

  active = false;

}
```

### 11.2.3 Wait, Notify 和 NotifyAll 方法

`Object` 类中的 `wait()`、`notify()` 和 `notifyAll()` 方法用于线程间通信和协调多个线程。

- `wait()`：使当前线程等待，直到另一个线程对对象调用 `notify()` 或 `notifyAll()`。
- `notify()`：唤醒等待对象监视器的一个线程。
- `notifyAll()`：唤醒等待对象监视器的所有线程。

这些方法必须在针对对象的同步上下文中（方法或块）中调用。

```java
synchronized(obj) {

    while (<条件不满足>) obj.wait();

    // 执行符合条件的操作

    obj.notifyAll(); // 或 obj.notify();

}
```

### 11.2.4 ReentrantLock 和 Condition

`java.util.concurrent.locks` 包中的 `ReentrantLock` 类提供了使用同步方法和块的替代方案，并具有更扩展的功能，例如可中断锁获取、锁轮询、超时锁等待和公平性。

```java
private final ReentrantLock lock = new ReentrantLock();

public void method() {

    lock.lock();

    try {

        // 临界区代码

    } finally {

        lock.unlock();

    }

}
```

- **Conditions：** `ReentrantLock` 提供了创建多个 `Condition` 对象的能力，允许线程等待特定条件变为真。

```java
private final Condition condition = lock.newCondition();

public void awaitCondition() throws InterruptedException {

    lock.lock();

    try {

        condition.await(); // 类似于 Object.wait()

        // await 之后执行的代码

    } finally {

        lock.unlock();

    }

}

public void signalCondition() {

    lock.lock();

    try {

        condition.signal(); // 类似于 Object notify()

    } finally {

        lock.unlock();

    }

}
```



使用 `ReentrantLock` 和 `Condition` 可以对线程的锁定和唤醒提供更细粒度的控制，适用于需要复杂同步策略的场景。

## 11.3 并发工具类

### 11.3.1 java.util.concurrent 包概览

`java.util.concurrent` 包提供了健壮、高性能的工具，用于构建并发应用程序。该包于 Java 5 中引入，并在随后的版本中显著增强，包含了一系列同步集合、用于管理线程池的执行器接口、原子操作工具类、同步器等。它的设计通过抽象许多同步机制的复杂性，显著地简化了并发应用程序的开发。

### 11.3.2 并发集合 (ConcurrentHashMap, BlockingQueue)

**ConcurrentHashMap**：`HashMap` 的线程安全变体，专为并发设计。它允许并发的读取和更新，而不需要同步锁。通过分段锁机制，`ConcurrentHashMap` 实现了高吞吐量和可扩展性。

```java
ConcurrentHashMap<String, String> map = new ConcurrentHashMap<>();
map.put("key", "value");
```

**BlockingQueue**：表示队列的接口，它额外支持以下操作：在获取元素时等待队列变为非空，在存储元素时等待队列有可用空间。`ArrayBlockingQueue`、`LinkedBlockingQueue`、`PriorityBlockingQueue` 和 `SynchronousQueue` 是著名的实现类。

```java
BlockingQueue<String> queue = new ArrayBlockingQueue<>(1024);
queue.put("item");
String item = queue.take();
```

### 11.3.3 原子变量和原子包

`java.util.concurrent.atomic` 包提供了一系列支持在单个变量上无锁线程安全的类。原子类（如 `AtomicInteger`、`AtomicLong`、`AtomicBoolean` 和 `AtomicReference`）提供了原子更新其值的机制。

```java
AtomicInteger atomicInt = new AtomicInteger(0);
int oldValue = atomicInt.getAndIncrement(); // 原子性递增 1
```

这些对于计数器、标志位或引用特别有用，因为它们可以在不需要同步的情况下安全地进行更新。

### 11.3.4 SynchronousQueue 和 Phaser

**SynchronousQueue**：一种 `BlockingQueue`，其中每个插入操作必须等待另一个线程执行相应的移除操作，反之亦然。同步队列没有任何内部容量，甚至容量不为 1。它适用于你想将数据从一个线程传递给另一个线程的场景。

```java
BlockingQueue<String> syncQueue = new SynchronousQueue<>();
Thread producer = new Thread(() -> syncQueue.put("hello"));
Thread consumer = new Thread(() -> {
    String received = syncQueue.take();
});
producer.start();
consumer.start();
```

**Phaser**：一种可复用的同步屏障，功能上类似于 `CyclicBarrier` 和 `CountDownLatch`，但更具活性。`Phaser` 可以处理注册到它的动态数量的线程，并支持从一个阶段到另一个阶段。每个阶段数字代表一个阶段。

```java
Phaser phaser = new Phaser(1); // '1' 用于注册当前线程
int currentPhase = phaser.arriveAndAwaitAdvance();
```

`Phaser` 特别适用于需要从一个阶段推进到另一个阶段的场景。

## 11.4 使用执行器和线程池

### 11.4.1 Executor 框架基础

Executor 框架通过抽象许多线程执行的复杂性，极大地简化了任务的开发。其主要组件包括：

- `Executor`：一个表示可执行对象的接口。
- `Executors`：提供创建常见类型执行器的方法的工具类。
- `ExecutorService`：一个提供可以跟踪任务执行情况并管理线程池的执行器。

简单用法：

```java
ExecutorService executor = Executors.newSingleThreadExecutor();
executor.submit(() -> {
    System.out.println("执行任务");
});
executor.shutdown();
```

### 11.4.2 创建固定和缓存线程池

**固定线程池**：具有固定数量线程的线程池。如果没有空闲线程，任务将放入队列等待。

```java
ExecutorService fixedThreadPool = Executors.newFixedThreadPool(4);
fixedThreadPool.execute(() -> System.out.println("固定线程池任务"));
```

**缓存线程池**：根据需要创建新线程并复用之前构造线程的线程池。

```java
ExecutorService cachedThreadPool = Executors.newCachedThreadPool();
cachedThreadPool.execute(() -> System.out.println("缓存线程池任务"));
```

### 11.4.3 用于定时任务的 ScheduledExecutor

允许你在指定的延迟后或定期执行命令。这对于实现超时机制非常有用。

```java
ScheduledExecutorService scheduler = Executors.newScheduledThreadPool(1);
Runnable task = () -> System.out.println("延迟执行的任务");
ScheduledFuture<?> scheduledFuture = scheduler.schedule(task, 5, TimeUnit.SECONDS);
scheduler.shutdown();
```

### 11.4.4 通过 ThreadPoolExecutor 自定义线程池

如果 `Executors` 类提供的执行器不能满足你的需求，你可以直接创建 `ThreadPoolExecutor` 并对其自定义。创建 `ThreadPoolExecutor` 时，你可以指定核心池大小、最大池大小、空闲线程存活时间、等待执行任务的阻塞队列以及创建新线程的线程工厂。

```java
int corePoolSize = 2;
int maxPoolSize = 4;
long keepAliveTime = 10;
ThreadPoolExecutor executor = new ThreadPoolExecutor(
    corePoolSize,
    maxPoolSize,
    keepAliveTime,
    TimeUnit.SECONDS,
    new LinkedBlockingQueue<Runnable>(),
    Executors.defaultThreadFactory()
);
executor.execute(() -> System.out.println("自定义线程池任务"));
executor.shutdown();
```

## 高级 OOP

## 12.1 抽象类和方法

### 12.1.1 抽象简介

抽象是面向对象编程 (OOP) 的核心概念，旨在隐藏复杂的实现细节，仅显示对象的必要特征。它通过允许程序员在更高层次的逻辑上思考来帮助管理复杂性。在 Java 中，抽象可以通过抽象类或接口来实现。抽象类可以包含抽象方法（没有体的方法）和非抽象方法，使其成为在相关类之间共享共同设计的强大工具，同时允许每个类对某些细节有独特的实现。

### 12.1.2 定义抽象类

Java 中的抽象类使用 `abstract` 关键字声明。它不能被实例化，意味着不能直接从抽象类创建对象。然而，你可以创建继承自抽象类的具体子类的对象。抽象类用于为其他类的构建提供一个基础模板或架构规划。

```java
abstract class Animal {
    abstract void makeSound();
    void eat() {
        System.out.println("This animal eats food.");
    }
}
```

### 12.1.3 抽象方法及其影响

抽象方法是抽象类中没有方法体的方法。相反，它们仅提供方法签名。提供这些方法的实际实现是子类的责任。如果一个类中只包含一个抽象方法，该类也必须声明为抽象类。

类中存在抽象方法表明，该类旨在作为其他类的蓝图或基类。它与子类强制了一种契约，确保某些基本方法被实现，从而促进了继承类之间统一的使用和行为。

```java
class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Bark");
    }
}
```

### 12.1.4 抽象类的实际用途

抽象类在需要为一组子类定义通用框架的场景中特别有用，它们在确保功能一致性的同时，允许实现上具有灵活性。一些实际用途包括：

- **模板方法**：抽象类可以定义一个包含执行任务的一系列步骤的“模板方法”。子类可以定义这些步骤的实际实现。
- **代码复用**：通过声明并可能为常用方法提供默认实现，它们允许重大的代码复用，子类可以直接使用这些方法，或在需要时重写。
- **设计与文档**：作为未来开发的蓝图，抽象类有助于记录类层次结构，促进良好的设计实践。

总而言之，抽象类和方法提供了一种结构化的方式来封装相关类之间的共同特征，同时确保了某种程度的抽象，并要求子类根据其需求实现特定的功能。

## 12.2 探索接口

### 12.2.1 接口基础

在 Java 中，接口是一种引用类型，类似于类，但可以只包含常量、方法签名、默认方法、静态方法和嵌套类型。接口不能包含实例字段或构造函数。接口中的方法默认是抽象的，这意味着它们没有方法体，必须由选择实现接口的类来实现。

```java
public interface Animal {
    void eat();
    void sleep();
}
```

接口通过在类中使用 `implements` 关键字来实现。实现接口的类必须为接口中声明的所有抽象方法提供具体的实现。

### 12.2.2 实现多个接口

Java 通过使用接口支持类型的多重继承。这意味着一个类可以实现多个接口，从而从多个源继承抽象方法。

```java
public interface Herbivore {
    void graze();
}

public interface Carnivore {
    void hunt();
}

public class Bear implements Herbivore, Carnivore {
    public void graze() {
        System.out.println("Bear is grazing");
    }
    public void hunt() {
        System.out.println("Bear is hunting");
    }
}
```

这种方法允许灵活的设计，而避免了与实现的多重继承相关的复杂性和问题。

### 12.2.3 接口中的默认方法

Java 8 引入的默认方法允许你向已经有实现者的接口添加新方法，而不会破坏它们的代码。与接口中定义的其他方法不同，默认方法具有方法体且不是抽象的。

```java
public interface Animal {
    void eat();
    default void breathe() {
        System.out.println("Breathing");
    }
}
```

引入默认方法主要是为了增强 Java 8 中的集合 API，允许在不影响现有代码的情况下添加新方法。

### 12.2.4 函数式接口与 Lambda 表达式

Java 中的函数式接口是指恰好包含一个抽象方法的接口。它可以有多个方法，但所有其他方法必须有默认实现或是静态的。这些接口的设计主要用于配合 Lambda 表达式，Lambda 表达式提供了一种清晰简洁的方式来表示单方法接口（函数式接口）。

```java
@FunctionalInterface
public interface Greeting {
    void sayHello(String message);
}

public class Demo {
    public static void main(String[] args) {
        Greeting greeting = message -> System.out.println("Hello, " + message);
        greeting.sayHello("World");
    }
}
```

Lambda 表达式提供了一种清晰简洁的方式来表示单方法接口（函数式接口）。

## 12.3 深入理解内部类

### 12.3.1 内部类概览

在 Java 中，内部类定义在另一个类内部。根据其目的和声明方式，内部类分为几种类型：成员内部类、局部内部类、匿名内部类和静态嵌套类。

### 12.3.2 成员内部类

成员内部类是定义在实例变量同一层级的非静态类。它可以访问外部类的所有成员。

```java
class OuterClass {
    private String message = "Hello";
    class InnerClass {
        void display() {
            System.out.println(message);
        }
    }
}
```

### 12.3.3 局部内部类

局部内部类定义在块（通常是方法）中，并且仅在该块可见。与局部变量一样，它们可以访问有效 final（effectively final）的变量。

### 12.3.4 匿名内部类

匿名内部类是没有命名的，通常用于临时实例化接口或抽象类，而无需正式声明子类。

```java
Runnable runnable = new Runnable() {
    @Override
    public void run() {
        System.out.println("Anonymous inner class.");
    }
};
```

### 12.3.5 静态嵌套类

与其他类型的内部类不同，静态嵌套类不需要创建外部类的实例。它们无法直接访问外部类的非静态成员。

## 12.4 理解 static 和 final

### 12.4.1 static 关键字：变量和方法

Java 中的 `static` 关键字用于指示特定成员属于类而不是类的实例。这意味着静态成员只有一个副本，并供所有实例共享。

- **静态变量**：也称为类变量，它们在类中方法之外用 `static` 关键字声明。它们在类加载时初始化。
- **静态方法**：这些方法可以在创建类实例的情况下调用。静态方法无法直接访问实例变量。

### 12.4.2 final 关键字：不可变状态

Java 中的 `final` 关键字用于声明常量、防止继承以及防止方法重写。应用于变量时，它使其在初始化后不可更改。

- **final 变量**：这些变量必须在声明时或在构造函数中初始化。
- **final 参数**：声明为 `final` 的方法参数在方法内部不能被修改。

### 12.4.3 静态块与初始化器

**静态块**：静态块用于初始化静态变量。该块只执行一次：在类首次加载到内存中时。

```java
class MyClass {
    static {
        // code to be executed when class is loaded
    }
}
```

**初始化器**：非静态初始化器块用于初始化实例变量。每当类的实例被创建时，这些块就会执行。

```java
class MyClass {
    {
        // code to be executed when an instance is created
    }
}
```

### 12.4.4 Final 类与方法

- **Final 类**：声明为 `final` 的类不能被子类化。这在创建像字符串类这样的不可变类时特别有用。
- **Final 方法**：声明为 `final` 的方法不能被子类重写。这用于防止无意重写可能会改变类关键行为的方法。

```java
final class MyFinalClass {
    // class body
}

class MyClass {
    final void myFinalMethod() {
        // method body
    }
}
```



正确使用 `static` 和 `final` 关键字可以显著增强 Java 应用的设计和性能，通过提高不可变性、减少开销并保护关键功能免受修改。

## 关于作者

Programming Hub 是一个开创性的平台，它改变了数百万学习者参与编码和计算机科学的方式。Programming Hub 肩负着让编程对所有人触及的任务，取得了重要的里程碑，赋予了来自不同背景的人探索编程世界的能力。

Programming Hub 应用拥有超过 500 万次下载，在 Play Store 和 App Store 上凭借超过 18 万条评价获得 4.7 分，被认为是最好的应用程序之一。它是一个全面的学习伙伴，涵盖了大量的编程语言和主题。从 Python、Java 到 C++ 和 HTML，该应用提供了互动式课程、编码挑战和测验，帮助你精进技能。其直观的界面和游戏化的学习方法让掌握编程语言变得有趣且易上手。Programming Hub 曾获得众多奖项，荣获 2017 年 Google 编辑精选、2017 年 Google 最佳应用、Google LaunchPad 加速器，并在 Product Hunt 上登登，获得了 Facebook 的 FB Start 奖励。

Programming Hub 为用户提供 45 多个应用程序，赢得了全球学习者的赞誉。用户赞扬该应用用户友好的界面、吸引人的内容和有效的教学方法。所有年龄和技能水平的学习者都发现 Programming Hub 是他们编程之旅中可靠伙伴，点燃了他们对编程的热情并释放了他们的全部潜力。

Programming Hub 用户经常使用的其他应用包括：

1. Python
2. 数字营销
3. Java
4. 黑客技术
5. 人工智能
6. C++ 编程
7. C 语言编程
以及更多

各位魔法师们，这段旅程就此结束，但请记住，这只是开始！请保持关注，并期待这一启发性系列的下一卷，我们将深入探索迷人的编程世界，并继续我们的精通之路。冒险远未结束！
