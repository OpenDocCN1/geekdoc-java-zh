
# Java 入门：从初学者到开发者

## 如何与我们联系？

请将有关本书的意见和问题发送至以下地址：

Rightsol Private Limited

Platinum Palm Woods, Sector- 38, Nerul Office No. 5 and 6, Plot No. 15 B

Navi Mumbai, Maharashtra 400706 India

您可以通过以下平台联系我们：

- [Facebook](https://www.facebook.com/programminghub)
- [LinkedIn](www.linkedin.com/company/pro-programming-hub)
- [Twitter](twitter.com/prghub?lang=en)
- [Instagram](https://www.instagram.com/programminghub_app_official/)

如需对本书提出意见或提问技术问题，请发送电子邮件至：Hello@programminghub.io

有关我们产品的更多信息，请访问我们的网站：https://programminghub.io/

## 前言

欢迎来到《Java 基础》！这本书旨在为想要学习 Java 的人提供坚实的基础。无论你是初学者还是想复习技能，本指南将引导你了解该语言的核心概念。

在书中，我们将探索 Java 的特性、架构和最佳实践。我们希望这本书能在你成为开发者的道路上为你提供支持。

## 欢迎来到 Java

### 1.1 探索 Java：特性与架构

#### 1.1.1 Java 简介：一种强大的编程语言

Java 是一种多功能且强大的编程语言。自 1995 年由 Sun Microsystems 公司（现归 Oracle 甲骨文公司所有）创立以来，它在软件开发领域一直保持着重要地位。Java 遵循“一次编写，随处运行”（WORA）的设计原则，使开发者能够编写出在任何支持 Java 的设备上运行的代码，而无需重新编译。Java 的广泛应用证明了其健壮性、可移植性和易于使用的设计理念。

#### 1.1.2 Java 的核心特性：简单、面向对象且安全

Java 的设计原则旨在使其成为一种简单、安全且可靠的编程语言。它的基础特性之一是面向对象，这种设计重点关注数据（对象）以及操作这些对象的方法，促进了更整洁、模块化的编码方式。安全是另一个基石，它内置的机制可以最大限度地减少病毒攻击以及对数据和系统的未经授权访问。简化的语法和缺乏低级编程功能，使得 Java 对初学者容易上手，同时对经验丰富的开发者来说依然强大。

#### 1.1.3 理解 Java 架构：JVM、JRE 和 JDK

Java 架构充分体现了它在不同平台上的可移植性和效率。它由：

- Java 虚拟机 (JVM)：执行 Java 字节码的运行时，确保了 WORA 原则的实现。它将底层操作系统和硬件与 Java 应用抽象化。
- Java 运行环境 (JRE)：包含 JVM 以及运行 Java 程序所需的类库和组件。它不包含编译器或调试器等开发工具。
- Java 开发工具包 (JDK)：用于 Java 开发的完整套件，包含了 JRE 和开发工具。

#### 1.1.4 “一次编写，随处运行”(WORA) 哲学

WORA 哲学是 Java 身份的核心，强调了在任何配备 JVM 的设备上运行 Java 代码的能力。这种跨平台的兼容性是一个巨大的优势，将开发者从特定平台的编码限制中解脱出来，并实现了更高效的开发和部署流程。

### 1.2 编写你的第一个 Java 程序

#### 1.2.1 准备工作：搭建你的开发环境

在开始编码之前，准备开发环境至关重要。这一过程涉及安装 Java 开发工具包 (JDK) 以及你选择的集成开发环境 (IDE)，如 IntelliJ、Eclipse 或 NetBeans。通过在命令行或终端输入 `java -version` 命令，确保 Java 已正确安装在你的系统中。设置过程包括配置环境变量（如 `PATH`），以便从命令行轻松运行 Java 程序。

#### 1.2.2 Hello, World!：理解 Java 程序的结构

任何旅程都始于第一步，在 Java 中，这一步就是“Hello, World!”程序。一个简单的 Java "Hello, World!" 程序展示了基础 Java 语法和结构，包括 `public` 类的声明、`main` 方法的声明以及用于向控制台输出的 `System.out.println` 语句。这个程序不仅是学习新编程语言的传统，更是对 Java 程序语法和功能的介绍。

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

#### 1.2.3 编译并运行你的第一个程序

Java 程序是用纯文本编写的，因此可以自由使用任何文本编辑器来编写代码。要将你的 Java 程序转换为可运行程序，你首先需要使用 Java 编译器 (`javac`) 将其编译为字节码。这个过程会将你的 `.java` 文件创建一个 `.class` 文件，Java 虚拟机 (JVM) 可以执行该文件。在命令行中编译和运行程序的基本命令如下：

```bash
javac HelloWorld.java
java HelloWorld
```

第一条命令将 `HelloWorld.java` 源文件编译为 `HelloWorld.class` 字节码文件。第二条命令运行编译后的 `HelloWorld`。

#### 1.2.4 常见错误与排除

在开始阶段，不可避免会遇到错误。常见的类型包括：

- 语法错误：缺少分号、括号不匹配或拼写错误。
- 运行时错误：在程序执行期间发生的错误，例如除以零。
- 编译错误：在编译期间发现的问题。

排除故障涉及仔细阅读错误信息，这些信息通常会提供问题的提示。

### 1.3 探索 Java 开发工具包 (JDK)

#### 1.3.1 什么是 JDK？全面概述

Java 开发工具包 (JDK) 是用于开发 Java 应用的完整功能套件。它包含了运行环境 (JRE) 以及编码、调试和运行程序所需的工具。

#### 1.3.2 安装 JDK：步骤说明

要安装 JDK，遵循以下步骤：

1. 下载 JDK：访问官方网站或 OpenJDK 版本，选择适用于你操作系统的版本。
2. 运行安装：执行下载的文件并按照屏幕说明操作。
3. 设置环境变量：为了从命令行使用 JDK，你需要将 `PATH` 环境变量指向 JDK 的 bin 目录。在 Windows 上，你可能还需要设置 `JAVA_HOME` 到 JDK 目录。
4. 验证安装：打开命令提示符或终端并输入 `java -version` 和 `javac -version`。如果 JDK 安装正确，你将看到 Java 和编译器的版本。

#### 1.3.3 JDK 的核心组件

JDK 不仅仅是一个编译器，它包含了若干对 Java 开发的关键组件：

- `javac`：将源代码转换为 Java 字节码。
- `java`：Java 启动工具，在 JVM 上运行你的程序。
- `jar`：Java 归档工具，将多个文件合并为一个 JAR（Java 归档）文件。
- `javadoc`：文档生成器，根据 Java 注释生成 HTML 文档。
- `debugger`：调试 Java 程序的工具，既有命令行版本也有集成版本。

#### 1.3.4 导航 JDK 文档

JDK 文档是开发者宝贵的资源。它涵盖了 Java 的方方面面，从全面概述到 Java API（应用程序接口）的详细描述。以下是导航 JDK 文档的一些技巧：

- 从概览开始：文档概览页提供了摘要，可以帮助你找到所需信息。
- API 文档：熟悉 API 文档的结构。它按包、类和接口组织，并对每个方法都有详细说明。
- 教程和指南：除了参考资料外，JDK 文档还包含了针对复杂主题或特定功能的教程、指南和文章。
- 示例代码：留意文档中的示例代码段，这有助于明确各种类和方法用法。

### 1.4 Java 的演变：版本与发行

#### 1.4.1 Java 的历史历程

Java 自诞生以来已经走过了很长的路。它由 James Gosling 在 1991 年在 Sun Microsystems 公司构思，最初是一个名为“Oak”的项目，设计用于机顶盒和电视机等数字设备。然而，互联网的兴起为 Java 的繁荣提供了完美的土壤。Sun Microsystems 于 1995 年正式发布了 Java 1.0，其“一次编写，随处运行”（Write Once, Run Anywhere）的承诺捕捉了全球开发者的想象。多年来，Java 经历了重大的演变，每个版本的发布都持续添加了新功能和改进。

#### 1.4.2 Java SE vs Java EE vs Java ME：理解它们的区别

Java 技术分为几个版本，每个版本针对不同的应用环境和需求：

- Java SE (标准版)：Java 编程的基础，提供了 Java 编程语言的核心功能。它包含了用于网络、UI、数据库访问、安全等基础 API。
- Java EE (企业版)：基于 Java SE 构建，增加了用于分布式计算和 Web 服务等企业功能的 API。Java EE 旨在开发大型、多层级、可扩展、可靠且安全的网络应用。
- Java ME (微型版)：针对资源有限的移动和嵌入式设备进行了优化，Java ME 为这些设备上运行的应用提供了一个强大且灵活的环境。

#### 1.4.3 从 Java 1 到最新版本的亮点与特性

Java 的演变以每个版本的重大新增和改进为标志。以下是一些亮点：

- Java 1.0 (1996)：开端，引入了 Java 语言，并具有垃圾回收和用于移植性的 JVM 等特性。
- Java 5 (2004)：引入了重大增强，包括泛型、元数据注解、增强型 for 循环、自动装箱/拆箱以及并发工具类。
- Java 8 (2014)：一个里程碑式的发布，引入了 Lambda 表达式、用于集合进行批量数据操作的 Stream API 以及新的日期/时间 API。
- Java 11 (2018)：Java 8 之后的第一个长期支持 (LTS) 版本，带来了诸如 Lambda 参数的局部变量语法、HTTP Client API 等新功能。
- Java 17 (2021)：截至我上次更新时的最新 LTS 版本，引入了密封类（sealed classes）、`instanceof` 的模式匹配，并弃用了 Applet API。

#### 1.4.4 如何跟进 Java 的发展

通过以下方式获取 Java 动态：

- 官方 Java 博客和邮件列表：订阅以接收最新消息和更新。
- Java 社区进程 (JCP)：参与或关注 JCP 以查看 Java 的未来方向和提案。
- 开发者会议：参加 Java 会议，例如 Oracle One 或本地的 Java 用户组会议。
- 关注专家和影响者：Java 领域思想领袖的社交媒体平台和个人博客是获取见解的绝佳来源。

# 搭建你的 Java 环境

## 2.1 配置系统环境变量

### 2.1.1 Java 环境变量简介

计算机中的环境变量是影响计算机上运行进程行为的动态值。它们可以指定某些数据，例如系统文件的位置或软件应用程序的设置。对于 Java 开发来说，设置环境变量至关重要，因为它们能指导系统如何找到 Java 编译器 (`javac`) 和 Java 运行环境 (`java`)。这允许开发者从任何目录在命令行中运行 Java 命令，而无需指定 Java 可执行文件的完整路径。

### 2.1.2 设置 JAVA_HOME 并更新 PATH

设置 JAVA_HOME：`JAVA_HOME` 环境变量指向 JDK 的安装目录。应用程序使用此变量来查找 Java 库。

Windows：

1. 右键点击“此电脑”并选择“属性”。
2. 导航到“高级系统设置” > “环境变量”。
3. 点击“新建”创建一个新的环境变量。命名为 `JAVA_HOME` 并将其值设置为 JDK 的安装路径（例如 `C:\Program Files\Java\jdk-17`）。

macOS/Linux:

1. 打开终端 (Terminal)。
2. 编辑你的 shell 配置文件（`.bash_profile`, `.bashrc`, `.zshrc` 等）。例如，你可以使用 `nano ~/.bashrc` 打开它。
3. 添加此行：`export JAVA_HOME=$(/usr/libexec/java_home).`。
4. 保存更改并关闭编辑器。

更新 PATH：为了方便从命令行中运行 Java 可执行文件，请将 JDK 的 `bin` 目录添加到系统的 `PATH` 中。

Windows：按照上述步骤进入“环境变量”，然后找到 `PATH` 变量并选择“编辑”。追加 JDK 的 `bin` 目录路径（例如 `C:\Program Files\Java\jdk-17`）。

macOS/Linux：像之前一样打开 shell 配置文件，并添加该行：`export PATH=$PATH:$JAVA_HOME/bin`。

### 2.1.3 在 Windows、macOS 和 Linux 中验证配置

在设置 `JAVA_HOME` 并更新 `PATH` 之后，验证配置：

- 打开一个新的终端或命令提示符（更改可能不会应用于已打开的终端）。
- 输入 `java -version` 和 `javac -version`。如果安装成功，你应该能看到每个命令对应的已安装 Java 版本。

Windows：

- 如果配置错误，`java` 或 `javac` 命令可能无法被识别。

macOS/Linux：

- 如果配置错误，`java` 或 `javac` 命令可能无法被识别。

## 2.2 将构建工具集成到你的 IDE

### 2.2.1 构建工具概述：Maven 和 Gradle

Maven 和 Gradle 是 Java 中最常用的两种构建自动化工具。它们帮助进行项目创建、依赖管理和生命周期管理。

- Maven 以使用基于 XML 的 `pom.xml`（项目对象模型）文件闻名。它遵循“约定优于配置”的方法，这简化了项目设置，但在复杂配置下灵活性较低。
- 另一方面，Gradle 使用基于 Groovy 的 DSL（领域特定语言）编写配置脚本 (`build.gradle`)，提供了更多的可扩展性和灵活性。Gradle 的性能被认为是一个优势，特别是它的增量构建功能。

### 2.2.2 在 Eclipse 和 IntelliJ IDEA 中设置 Maven

Eclipse：

1. Eclipse 大多数版本都集成了 Maven。要创建新的 Maven 项目，前往 `File > New > Other... > Maven > Maven Project`。
2. 向导指定 Group ID 和 Artifact ID。

IntelliJ IDEA：

1. 打开 IntelliJ IDEA，导航到 `File > New > Project`。
2. 选择 Maven。IntelliJ IDEA 会提示你指定项目的 SDK（开发工具包）。

两个 IDE 都会根据 `pom.xml` 文件自动处理依赖解析，无需手动下载和配置库。

### 2.2.3 在你的 Java 项目中配置 Gradle

由于 Eclipse 和 IntelliJ IDEA 都提供了良好的 Gradle 支持，设置 Gradle 在不同 IDE 之间差异不大。

Eclipse：

1. 如果你的 Eclipse 版本未包含，你需要安装 Buildship Gradle Integration 插件。可以通过 Eclipse 市场进行安装。
2. 要创建新的 Gradle 项目，前往 `File > New > Other... > Gradle > Gradle Project` 并按照向导操作。

IntelliJ IDEA：

1. IntelliJ IDEA 内置了对 Gradle 的支持。要启动一个新的 Gradle 项目，只需导航到 `File > New > Project`，然后在左侧栏选择 Gradle。
2. IntelliJ IDEA 会要求你定义 Group、ArtifactId 以及其他选项。

对于 Maven 和 Gradle，在设置好项目后，IDE 将根据构建配置（pom.xml 或 build.gradle）显示项目结构，允许你通过 IDE 的 UI 运行、调试和管理依赖。

将 Maven 或 Gradle 整合到你的开发环境中可以显著增强项目管理、依赖解析和构建自动化，能够无缝集成到 Java 开发者使用的 IDE 中。

## 2.3 版本控制系统：Git 与 Java

### 2.3.1 Java 开发者的 Git 简介

对于 Java 开发者来说，理解和利用版本控制系统（VCS）是不可或缺的，而 Git 是当今开发领域应用最广泛的 VCS。Git 帮助管理代码更改、与其他开发者协作，并维护项目演化的历史记录。从简单的代码存储到复杂的协作开发项目，它都是至关重要的。

Git 基于“快照”原理运行，每个 commit 都代表项目在特定时间点的快照。这种模型允许强大的分支和合并操作，使得在互不干扰的情况下可以实现并行的开发流。

### 2.3.2 使用 Git 克隆你的第一个 Java 项目

克隆（Cloning）是创建 Git 仓库本地副本的过程。要克隆你的第一个 Java 项目：

1. 找到仓库：找到你想要克隆的 Git 仓库 URL。这可能位于 GitHub、GitLab、Bitbucket 或任何 Git 服务器上。
2. 打开终端或命令提示符：切换目录（cd）到你想要克隆仓库的路径。
3. 克隆仓库：使用 `git clone` 命令后跟仓库的 URL。

例如：

```bash
git clone https://github.com/example/project.git
```

此命令将项目下载到与项目同命名的本地文件夹中。



- 6. 使用 IDE 打开：使用你喜爱的 IDE（例如 Eclipse 或 IntelliJ IDEA）将克隆的目录作为现有项目打开。大多数 IDE 都会自动识别 Git 仓库并启用 VCS 支持。

### 2.3.3 在 Java 项目中提交和推送更改

对你的 Java 项目进行更改后，你可能想将这些更改保存到你的 Git 仓库中。提交（Committing）和推送（Pushing）是实现此两个主要操作。

#### 提交更改（Committing Changes）

- 1. 查看更改：使用 `git status` 可以查看哪些文件已更改。要详细查看特定更改，使用 `git diff`。
- 2. 暂存文件以提交：在提交之前，你需要使用 `git add` 暂存更改。你可以使用 `git add .` 暂存所有更改的文件，或使用 `git add filename` 暂存单个文件。
- 3. 提交：使用 `git commit -m "Your commit message"` 提交暂存的更改。commit message 应该是对更改的简要描述。

#### 推送更改（Push Changes）

- 1. 如果你在克隆的仓库上工作，它已链接到远程仓库。使用 `git push` 将提交的更改送到远程仓库。
- 第一次推送时可能需要使用 `git push --upstream origin branch_name` 设置上游分支，将 `branch_name` 替换为你的当前分支名称。

通过掌握 Git 中克隆、提交和推送的基础知识，Java 开发者可以有效地管理和协作软件项目，确保更改被安全地存储并在团队成员之间共享。

## 2.4 调试 Java 应用

### 2.4.1 Java 调试基础

调试是开发过程中的关键阶段，允许开发者诊断并修复 Java 中的错误。它涉及识别 bug 的来源、理解它们为何发生，并确定纠正它们的最佳方法。有效的调试可以节省精力和精力，确保应用程序顺利运行并符合预期。

Java 提供了一系列调试工具和 IDE 特性，例如堆栈跟踪分析、断点、单步执行和变量检查，以促进这一过程。理解这些工具以及如何利用它们可以显著提高开发者快速诊断和解决问题的能力。

### 2.4.2 设置断点和检查变量

#### 设置断点（Setting Breakpoints）

断点会在代码的特定行临时暂停程序的执行。这允许你检查程序此时的状态，对于诊断问题具有无比拟的价值。在大多数 Java IDE 中设置断点：

- 1. 打开你想暂停执行的源代码。
- 2. 点击行号左侧的边缘区域或直接点击代码行。标记或高亮行表示已设置断点。
- 3. 在调试模式下运行你的程序（通常通过点击“虫”图标或从运行菜单中选择“Debug”）。执行将在断点处暂停。

#### 检查变量（Inspecting Variables）

在断点处暂停时，你可以检查变量的当前值：

- 1. 大多数 IDE 会调试窗口中显示变量列表及其值。
- 2. 你通常可以在代码编辑器中悬停在变量上查看弹出的值。
- 3. 某些 IDE 允许你在调试期间修改变量的值，以测试更改对程序执行的影响。

### 2.4.3 常见调试场景和解决方案

#### 场景 1：空指针异常（Null Pointer Exception）

- 问题：尝试使用值为 `null` 的对象引用。
- 解决方案：使用 IDE 调试工具识别 `null` 值的来源，并确保对象引用在使用之前已正确初始化。

#### 场景 2：数组索引越界（Array Index Out of Bounds）

- 问题：尝试使用超过数组大小的索引访问数组元素。
- 解决方案：在访问元素之前使用 `.length` 属性检查数组长度。使用断点跟踪索引。

#### 场景 3：无限循环（Infinite Loops）

- 问题：永不终止的循环。
- 解决方案：使用断点检查循环条件。

#### 场景 4：并发问题

- 问题：多线程访问共享资源引起的问题。
- 解决方案：使用同步块（`synchronized blocks`）或锁（`locks`）管理访问。

# Java 编程基础

## 3.1 理解变量和数据类型

### 3.1.1 什么是变量？

变量简介变量是在执行期间存储数据的变量容器。它们之所以被称为变量是因为包含的内容可以改变（变化）。在 Java 中，每个变量都有特定的类型，类型决定了大小和布局、可以存储的值范围以及可以的操作set。

变量规范 Java 遵循某些命名规则：

- 变量名应以小字母开头并遵循驼峰命名法。
- 它们可以包含字母、数字、下划线和美元符号，但不能以数字开头。
- 选择反映变量用途的意义命名很重要。
- Java 关键字不能作为变量名。

### 3.1.2 原型数据类型

原型类型概述 原型类型由语言预定义并用关键字命名。它们代表了基本数据类型。

#### 数值数据类型：`int`, `short`, `long`, `byte`

- `byte`：从 -128 到 127 的极小整数。适用于在大型数组中节省内存。
- `short`：从 -32,768 到 32,767 的小整数。
- `int`：默认整数类型，范围从 -2^31 到 2^31-1。
- `long`：从 -2^63 到 2^63-1 的大整数，当 `int` 不够大时使用。

#### 浮点类型：`float`, `double`

- `float`：单精度 32 位浮点数。它永远不应用于精确值（例如货币）。
- `double`：双精度 64 位 IEEE 754 浮点数。它通常是小数值的默认选择。

#### 布尔型类型和字符类型

- `boolean`：该类型表示一个位的信息，但其“大小”并不是一个精确定义的数字。值可以是 `true` 或 `false`。
- `char`：单个 16 位 Unicode 字符。它的最小值为 `'\u0000'`（或 0），最大值为 `'\uffff'`（包含 65,535 在内）。

### 3.1.3 引用类型

理解引用变量 引用变量用于引用对象。与存储实际值的基本数据类型不同，引用变量存储的是实际数据的内存地址或引用。

#### 字符串与数组

- 字符串（Strings）：字符串类不是基本数据类型，而是一种可以存储字符序列的引用类型。
- 数组（Arrays）：数组是存储相同类型多个项的引用类型。基本类型和对象都可以存储在数组中。

### 3.1.4 类型转换与强制转换

#### 隐式转换与 显式转换

- 隐式转换（宽宽转换）：当源类型的尺寸小于目标类型时，就会发生这种情况。例如，Java 将 `int` 赋值给 `long` 是隐式完成的。
- 显式转换（窄转换）：当你将较大的类型赋值给较小的类型时（例如将 `double` 转换为 `int`），就需要转换。这需要使用强制转换运算符。

#### 数据类型之间的转换

在执行涉及不同类型值的操作时，可能需要进行数据类型之间的转换。在转换时，请注意数据丢失的风险（对于窄转换），并确保转换是必要且刻意的，以维护数据的准确性和完整性。

## 3.2 深入理解运算符与表达式

### 3.2.1 算术运算符

基本操作：加、减等。Java 提供了几种算术运算符来执行常见的数学运算：

- `+`（加法）：合并两个值。
- `-`（减法）：从一个值中减去另一个值。
- `*`（乘法）：两个值相乘。
- `/`（除法）：将一个值除以另一个值。如果两个操作数都是整数，结果也将是整数，并舍弃余数。
- `%`（模运算符）：返回除法运算的余数。

#### 模运算符

模运算符表示为 `%`，对于寻找余数、判断数字是偶数还是奇数（通过模 2）以及在特定阈值处循环回绕值特别有用。

### 3.2.2 关系运算符与逻辑运算符

#### 比较值

关系运算符比较两个值并确定它们之间的关系。主要的关系运算符有：

- `==`（等于）
- `!=`（不等于）
- `>`（大于）
- `<`（小于）
- `>=`（大于或等于）
- `<=`（小于或等于）

这些运算符返回布尔结果（`true` 或 `false`）。

#### 组合条件：与、或、非

逻辑运算符用于构建更复杂的条件表达式：

- `&&`（逻辑与）：只有当两个操作数都为 `true` 时，才返回 `true`。
- `||`（逻辑或）：当至少有一个操作数为 `true` 时，就返回 `true`。
- `!`（逻辑非）：反转布尔值的值，将 `true` 变为 `false`，反之亦然。

### 3.2.3 赋值运算符

#### 简单赋值

简单赋值运算符 `=` 用于将其右侧的值赋值给左侧的操作数。

#### 复合赋值运算符

复合赋值运算符一步完成操作和赋值。示例包括 `+=`、`-=`、`*=`、`/=` 和 `%=`。例如，`x += y` 等于 `x = x + y`。

### 3.2.4 一元运算符、三元运算符与运算符优先级

#### 增与减

增（`++`）和减（`--`）分别增加或减少变量的值 1。它们都可以作为前缀和后缀形式使用，这会影响操作在表达式中执行的时机。

#### 使用三元运算符进行条件赋值

三元运算符 `? :` 提供了 if-else 语句的快捷方式，并用于条件赋值。语法为 `条件 ? 真值 : 假值`。

#### 理解运算符优先级与结合性

运算符优先级决定了表达式中项的分组。这影响了表达式如何评估。某些运算符的优先级高于其他运算符；例如，乘法的优先级高于加法减法。结合性定义了执行的方向（从左到右或从右到左），当表达式中出现具有相同优先级运算符的多个操作时，这一点至关重要。

## 3.3 用于决策的条件语句

### 3.3.1 if 语句

#### 基本 if 结构

`if` 语句是 Java 中基本的控制流语句之一。它允许程序根据条件的真假来执行不同的操作。基本语法如下：

```java
if (condition) {
    // 如果条件为真则执行的代码块
}
```

#### if-else 和 if-else-if 阶梯

对于需要在条件为真时执行一个操作、在条件为假时执行另一个操作的情况，使用了 if-else 结构：

```java
if (condition) {
    // 如果条件为真则执行的代码块
} else {
    // 如果条件为假则执行的代码块
}
```

对于多个条件，if-else-if 阶梯非常有用：

### 3.3.2 switch 语句

#### 语法与用例

`switch` 语句提供了一种简单的方法，根据表达式的值将执行分发到代码的不同部分。与顺序评估条件的 if-else-if 阶梯不同，`switch` 语句根据匹配执行一个 case：

```java
switch(expression) {
  case value1:
    // 当表达式匹配 value1 时执行的代码块
    break;
  case value2:
    // 当表达式匹配 value2 时执行的代码块
    break;
  // 额外的 cases
  default:
    // 如果没有匹配到任何 case，则执行的代码块
}
```

Switch cases 可以与 `byte`、`short`、`char` 和 `int` 基本类型、枚举类型（Java 的 `enum` 类型）、字符串类和 `Integer` 一起工作。

Java 中新的 `switch` 表达式引入了增强型 switch 表达式，通过消除对 `break` 语句的需求，简化了 switch 语句中的用法和控制流：

### 3.3.3 实践中的条件逻辑

#### 组合条件

逻辑运算符（`&&`、`||`、`!`）允许在语句中组合多个条件，创建更复杂的控制路径：

```java
if (condition1 && condition2) {
  // 如果 condition1 和 condition2 都为真则执行
}
```

#### 嵌套条件语句

条件语句可以嵌套在另一个语句内部以进一步决策。这涉及在另一个 if 或 switch 语句内部：

```java
if (condition1) {
    // 如果 condition1 为真则执行
    if (condition2) {
        // 如果 condition1 和 condition2 都为真则执行
    }
}
```

正确使用条件语句允许开发者编写灵活的可扩展 Java 应用程序，根据各种条件执行不同的代码块。

## 3.4 循环机制：for、while 和 do-while 循环

### 3.4.1 for 循环

#### 语法与基本用法

Java 中的 for 循环用于执行固定次数的代码。基本 for 循环的语法如下：

```java
for(initialization; condition; update) {
    // 要执行的代码块
}
```

- 初始化：通常用于初始化计数器变量。
- 条件：只要该条件为真，循环就会运行。
- 更新：在每次迭代后执行；通常用于更新计数器变量。

#### 增强 for 循环用于数组和集合

Java 5 引入了增强 for 循环，使得遍历数组和集合中的元素变得简单：

```java
for(dataType item : arrayOrCollection) {
  // 为每个 item 执行的代码块
}
```

这种形式消除了对维护索引或直接使用迭代器的需求。

### 3.4.2 while 循环

#### 何时使用 while 循环

当循环开始前不知道迭代次数时，应使用 while 循环。只要指定的条件为真，循环就会继续。

```java
while(condition) {
  // 要执行的代码块
}
```

#### 无限循环与循环控制

当循环条件永远不会变为假时，就会发生无限循环。有时会特意配合 `break` 语句使用，根据循环体内部的条件来退出循环。

### 3.4.3 do-while 循环

#### 与 while 循环的区别

do-while 循环与 while 循环相似，主要区别在于 do-while 循环保证至少执行一次。这是因为条件是在执行循环体之后才进行检查的。

```java
do {
  // 要执行的代码块
} while(condition);
```

#### 实际用法示例

当循环体在评估条件之前至少执行一次时，do-while 循环特别有用，例如在用户输入循环中显示菜单时。

### 3.4.4 循环控制语句

#### 循环中的 break 和 continue

- `break` 语句用于立即退出循环，跳过所有剩余迭代。
- `continue` 语句跳过当前迭代，并继续循环的下一次迭代。

#### 嵌套循环

嵌套循环是指另一个循环内部的循环。它们通常用于遍历多维数组等任务。`break` 和 `continue` 等循环控制语句可以应用于嵌套循环中，影响内部和外部循环的流。准确地控制和理解循环对于创建能够有效处理重复任务的 Java 程序至关重要。

# 第 4 章：深入探讨：数组与字符串

## 4.1 数组简介：定义与声明

`array` 是一种容器对象，用于持有固定数量的单一类型的值。数组的长度在创建时确定，不能更改。Java 中的数组是基于零索引的，这意味着数组的初始元素通过索引 0 访问。

在 Java 中声明数组，你需要指定它将包含的元素类型，后跟方括号，然后是数组名称：

```java
int[] myArray;
String[] myStringArray;
```

你也可以将方括号放在数组名称之后：

```java
int myArray[];
String myStringArray[];
```

然而，前一种声明更为常用且为了一致性更受推荐。

### 4.1.2 初始化和访问数组元素

要为数组分配内存并初始化，你需要使用 `new` 关键字，后跟数组元素的类型及其大小：

```java
myArray = new int[10]; // 初始化一个可以容纳十个整数的数组
```

数组也可以在声明时通过在花括号 `{}` 中包含值来进行带值初始化：

访问数组元素非常简单；你使用数组名称，后跟方括号中括的元素索引：

```java
int firstElement = myArray[0]; // 访问第一个元素
myArray[4] = 20; // 修改第五个元素的值
```

### 4.1.3 遍历数组

为了对数组的每个元素执行操作，你可以使用循环遍历数组。`for` 循环通常用于此目的：

```java
for(int i = 0; i < myArray.length; i++) {
    System.out.println(myArray[i]); // 打印数组中的每个元素
}
```

Java 还提供了一种增强型 for 循环（也称为 "for-each" 循环）来遍历数组，这使得代码更简洁、更易读：

```java
for(int element : myArray) {
    System.out.println(element); // 打印数组中的每个元素
}
```

### 4.1.4 多维数组：概念与用法

多维数组是数组的数组，主数组的每个元素都持有另一个数组。最常见的形式是二维数组，或矩阵。二维数组通过指定两组方括号来声明、分配和访问：

```java
int[][] myMatrix = new int[3][4]; // 一个 3x4 (行 x 列) 数组
```

用值初始化二维数组：

访问元素需要为每个维度指定索引：

```java
int firstRowThirdColumn = myMatrix[0][2];
```

遍历多维数组通常涉及嵌套循环：

```java
for(int i = 0; i < myMatrix.length; i++) {
    for(int j = 0; j < myMatrix[i].length; j++) {
        System.out.println(myMatrix[i][j]);
    }
}
```

理解并操纵数组对于掌握 Java 数据结构至关重要。

## 4.2 操作字符串

Java 中的 `String` 类用于字符序列。字符串是不可变的，这意味着一旦创建，其内容就不能更改。Java 为字符串提供了一系列丰富的方法。

### 4.2.1 创建和初始化字符串

字符串可以通过两种方式创建：字符串字面量或 `new`。

#### 使用字符串字面量

```java
String greeting = "Hello";
```

#### 使用 new

```java
String str1 = new String("Hello");
String str2 = "Hello";
```

### 4.2.2 比较字符串：方法与操作

Java 提供了几种方法来比较字符串：

- `equals()`：此方法比较字符串的实际内容。如果字符串相等则返回 `true`，否则返回 `false`。



```java
boolean result = str1.equals(str2); // 返回 true
```

- `equalsIgnoreCase()`：此方法与 `equals()` 类似，但在比较时忽略大小写。

```java
boolean result = str1.equalsIgnoreCase("HELLO"); // 返回 true
```

- `compareTo()`：此方法按字典顺序比较两个字符串并返回一个整数值。值为 0 表示两个字符串相等。小于 0 的值表示调用字符串在字典顺序上小于参数字符串。大于 0 的值表示相反。

```java
int result = "apple".compareTo("banana"); // 返回负值
```

### 4.2.3 拼接与分割

- 拼接

字符串可以使用 `+` 运算符或 `concat()` 方法进行拼接。

```java
String greeting = "Hello";
String name = "John";
String message = greeting + ", " + name; // 使用 + 运算符
String anotherMessage = greeting.concat(", "); // 使用 concat()
```

- 分割

`split()` 方法用于根据给定的表达式将字符串分割为字符串数组。

```java
String fruits = "apple, banana, cherry";
String[] fruitsArray = fruits.split(", ");
// fruitsArray 包含 ["apple", "banana", "cherry"]
```

## 4.3.2 Arrays 类：排序与搜索

`java.util.Arrays` 类提供了静态方法，用于对数组进行排序和搜索。这些工具类极大地简化了数组的操作。

- 排序

要对数组进行排序，可以使用 `Arrays.sort()` 方法。它会在原位修改数组，将元素按升序排列。

```java
import java.util.Arrays;

int[] numbers = {5, 3, 9, 1};
Arrays.sort(numbers); // numbers 数组现在已经排序
```

- 搜索

在对数组进行排序后，可以使用 `Arrays.binarySearch()` 方法进行二分查找。如果找到了被搜索的值，它将返回其索引；否则，返回一个负数。

```java
int[] numbers = {1, 3, 5, 9}; // 二分查找前必须先进行排序
int index = Arrays.binarySearch(numbers, 5); // 返回 2
```

### 4.3.3 数组转换：从数组到集合及反之

Java 提供了数组与集合（如 `List`、`Set` 和 `Map`）之间转换的机制，允许你利用集合框架提供的工具类。

- 数组到集合

可以使用 `Arrays.asList()` 方法将数组转换为列表。

- 集合到数组

集合可以使用 `toArray()` 方法转换回数组。

```java
String[] colorArray = new String[colorList.size()];
colorList.toArray(colorArray); // 将列表转换回数组
```

### 4.3.4 实际用例与示例

动态数组配合 `Arrays` 类提供的数组操作工具，广泛应用于多个领域：

- 数据聚合：为报告或分析收集并汇总数据通常涉及集合的动态调整大小、排序和搜索操作。
- 系统管理：解析和处理日志文件、配置文件或用户输入，可能涉及数组与集合类型之间的转换，以便于操作。
- 游戏开发：管理游戏中的实体（如角色、障碍物和道具）通常需要动态数组来灵活地添加和删除元素。

示例：寻找最大值和最小值

```java
int[] numbers = {4, 1, 13, 0, 6};
Arrays.sort(numbers); // 对数组排序
int min = numbers[0]; // 第一个元素最小
int max = numbers[numbers.length - 1]; // 最后一个元素最大
System.out.println("Minimum: " + min + ", Maximum: " + max);
```

示例：从列表中去重

高级数组概念（包括动态数组和 `Arrays` 类提供的工具）是开发高效且健壮的 Java 应用程序的基础。

## 4.4 String 类函数与操作

### 4.4.1 将数据类型转换为字符串

将各种数据类型转换为字符串是一个常见需求。在 Java 中，可以通过几种方法实现：

- `String.valueOf()`：此静态方法可以将各种数据类型（`int`、`long`、`float`、`double`、`char`、`char` 数组等）转换为字符串。

```java
int num = 100;
String str = String.valueOf(num); // "100"
```

- 使用 `toString()` 方法：Java 中的每一个类都继承自 `Object` 类的 `toString()` 方法，该方法可以被重写以以字符串形式表示对象。

```java
Integer numInteger = 100;
String str = numInteger.toString(); // "100"
```

- 与空字符串拼接：将值转换为字符串的快速方法。

```java
int num = 100;
String str = num + ""; // "100"
```

### 4.4.2 字符串操作：子字符串、替换与大小写转换

- 子字符串（Substring）：提取字符串的一部分。

```java
String str = "Hello World";
String substr = str.substring(0, 5); // "Hello"
```

- 替换（Replace）：替换字符串的部分。

```java
String str = "Java is fun";
String replacedStr = str.replace("fun", "awesome"); // "Java is awesome"
```

- 大小写转换：转换字符串的大小写。

```java
String str = "Java Programming";
String lowerStr = str.toLowerCase(); // "java programming"
String upperStr = str.toUpperCase(); // "JAVA PROGRAMMING"
```

### 4.4.3 字符串分析：长度、字符提取与模式匹配

- 长度（Length）：返回字符串中的字符数。

```java
String str = "Hello";
int length = str.length(); // 5
```

- 字符提取：获取指定索引处的字符。

```java
char ch = str.charAt(0); // 'H'
```

- 模式匹配（Pattern Matching）：Java 提供了 `Pattern` 和 `Matcher` 类用于正则表达式模式匹配。

### 4.4.4 高级字符串处理：StringBuilder 和 StringBuffer 类

当需要频繁修改字符串时，直接使用 `String` 会因为其不可变性导致性能问题。Java 提供了 `StringBuilder` 和 `StringBuffer` 来应对此类场景。

- `StringBuilder`：为可变字符串提供 API。它不是线程安全的，这在单线程环境下速度更快。

```java
StringBuilder sb = new StringBuilder("Hello");
sb.append(" World"); // 在末尾追加字符串
System.out.println(sb.toString()); // "Hello World"
```

- `StringBuffer`：与 `StringBuilder` 类似，但是线程安全的，适用于多线程环境。

```java
StringBuffer sbf = new StringBuffer("Hello");
sbf.append(" World"); // 在末尾追加字符串
System.out.println(sbf.toString()); // "Hello World"
```

## 5.1 方法与调用

### 5.1.1 定义与调用方法

Java 中的方法（在某些编程语言中被称为函数）是将一组语句封装成一个单元，可以在需要时执行。

### 5.1.2 方法结构

Java 方法具有以下结构：

```java
accessModifier returnType methodName(parameterList) {
    // 方法体
}
```

- `accessModifier`：定义方法的访问级别（例如 `public`、`private`）。如果不指定，则默认为包私有可见性。
- `returnType`：指定方法返回的值的数据类型。如果方法不返回值，则使用 `void`。
- `methodName`：方法的名称，遵循小驼峰命名法。
- `parameterList`：方法接收的输入参数列表（包含类型和名称）。它可以为空。

### 5.1.3 void 方法与返回方法

- void 方法：这些方法不返回任何值。在声明时使用 `void` 关键字。当方法需要执行某些操作但不需要向调用者提供反馈时使用它们。

```java
public void displayMessage() {
    System.out.println("Hello, World!");
}
```

- 返回方法：这些方法将值返回给调用者。它们必须声明要返回的数据类型。在方法的末尾，使用 `return` 语句提供该值。

```java
public int addNumbers(int a, int b) {
    return a + b;
}
```

### 5.1.4 编写你的第一个方法

让我们写一个接受两个整数作为参数并返回它们的和的简单方法：

```java
public class Calculator {
    // 添加两个数字并返回结果的方法
    public static int add(int num1, int num2) {
        return num1 + num2;
    }

    public static void main(String[] args) {
        int result = add(5, 3);
        System.out.println("The sum is: " + result);
    }
}
```

在这个示例中，`add` 方法定义了两个参数（`num1` 和 `num2`），并返回它们的和。`main` 方法通过两个参数（5 和 3）调用了 `add` 方法并打印结果。这演示了定义和调用方法，以及处理返回类型和参数的操作。

## 5.2 参数与返回类型

### 5.2.1 向方法传递参数

参数允许 Java 方法从外部接收数据，使方法更加灵活且可重用。

当你定义一个方法时，你将其参数列表指定为其声明的一部分。当你调用该方法时，你需要提供与这些参数相对应的实参。Java 方法通过“值传递”（pass-by-value）接收参数，这意味着方法接收的是原始数据的拷贝。

```java
public static void greet(String name) {
    System.out.println("Hello, " + name);
}

public static void main(String[] args) {
    greet("Alice"); // 将 "Alice" 作为参数传递给 greet 方法
}
```

### 5.2.2 基本类型与引用参数

在 Java 中，方法参数是按值传递的。这一概念在基本类型和引用类型上的表现不同。

- 基本类型参数：对于基本数据类型（例如 `int`、`double`、`char`），方法接收的是该值的拷贝。修改此值不会影响原始变量。

```java
public static void increment(int number) {
    number++;
    System.out.println("Number inside method: " + number);
}

public static void main(String[] args) {
    int value = 5;
    increment(value); // value 在方法外部仍保持 5
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

方法的返回类型决定了它可以发送回调用者的值的类型。返回类型在声明中紧邻方法名之前。方法可以返回任何类型的数据，包括基本类型、对象，甚至不返回任何数据（`void`）。如果方法声明了返回类型（`void` 除外），则必须使用 `return` 语句返回该类型的值。

```java
public static double getAverage(int sum, int count) {
    return (double) sum / count;
}
```

### 5.2.4 从方法返回多个值

Java 方法只能返回一个值。然而，你可以通过数组或对象来封装多个值，从而规避这一限制。

- 使用数组：适用于返回相同类型的多个值。

```java
public static int[] minMax(int[] numbers) {
    int[] result = {numbers[0], numbers[0]}; // 假设数组不为空
    for (int num : numbers) {
        if (num < result[0]) result[0] = num; // 更新最小值
        if (num > result[1]) result[1] = num; // 更新最大值
    }
    return result; // 包含最大值的数组
}
```

- 使用对象：适用于返回不同类型的值，或当你需要返回结构化数据时。

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

理解参数及其类型，并掌握返回机制，是开发高效灵活的 Java 应用程序的必备技能。

## 5.3 方法重载

### 5.3.1 方法重载的概念

方法重载是 Java 的一项特性，允许多个方法具有相同名称。这一特性允许方法在参数列表上有所不同。

### 5.3.2 不同类型的方法重载

```java
public class Calculator {
    public void add(int a, int b) {
        System.out.println("Sum: " + (a + b));
    }

    public void add(double a, double b) {
        System.out.println("Sum: " + (a + b));
    }

    public void add(int a, int b, int c) {
        System.out.println("Sum: " + (a + b + c));
    }
}
```

### 5.3.3 不同参数数量的方法重载

```java
public class Printer {
    public void print(int a) {
        System.out.println("Integer: " + a);
    }

    public void print(int a, int b) {
        System.out.println("Two Integers: " + a + ", " + b);
    }
}
```

### 5.3.4 方法重载的最佳实践

虽然重载增加了灵活性，但遵循以下最佳实践可以确保代码质量：

1. 谨慎使用重载：仅在合理时使用。
2. 保持逻辑一致性：确保重载方法执行相同的任务。
3. 使用清晰且描述性强的参数：这有助于理解。
4. 对于相同类型的多个参数考虑可变参数（varargs）：处理不定数量参数。

## 5.4 理解作用域与可见性



### 5.4.1 方法中变量的作用域

变量的作用域决定了代码中哪些部分可以访问它。方法变量（称为局部变量）定义在方法内部，仅在该方法内可用。它们在方法执行完成后就会消失。这种有限的作用域有助于减少命名冲突。

```java
public void myMethod() {
    int local = 5;
}
```

### 5.4.2 全局变量与局部变量

- **局部变量**：定义在方法内部，只能在该方法内访问。它们每次调用方法时都会初始化，在方法范围外未知。

```java
public void someMethod() {
    int localVar = 10; // 局部变量。在此可见
}
```

- **全局变量**：在 Java 上下文中，全局变量通常被称为字段或类变量。它们可以从类的任何方法访问（取决于访问修饰符）。它们定义在方法之外，通常位于类的顶部。

```java
public class MyClass {
    int globalVar = 20; // 字段，在该类中任何方法中均可用

    public void anotherMethod() {
        System.out.println(globalVar); // 访问全局变量
    }
}
```

### 5.4.3 访问修饰符及其影响

Java 中的访问修饰符控制类字段（变量）和方法对其他类以及程序的可见性。理解它们对于控制访问级别和保护对象至关重要。

- **私有（private）**：私有修饰符将可见性限制在类内部。这是封装的核心原则，防止数据被意外访问和修改。
- **默认（无修饰符）**：允许在包内访问字段和方法。它比私有的具有更高的访问性，但仍然提供了受限的访问级别。
- **保护（protected）**：与默认访问类似，子类（即使在不同的包中）也可以访问受保护的成员。
- **公共（public）**：`public` 修饰符允许字段和方法被应用程序中的任何其他类进行访问。

```java
public class ModifierExample {
    private int privateVar = 1;
    int defaultVar = 2;
    protected int protectedVar = 3;
    public int publicVar = 4;
}
```

### 5.4.4 封装与保护级访问

封装是面向对象编程的基本原则。它涉及将数据（属性）和操作这些数据的方法（函数）打包成单个单元（即类），并限制对数据特定实现细节的访问。

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

**保护级访问**：`protected` 访问通常在继承的语境中使用。它允许子类访问父类的字段和方法，在保持与 `public` 访问相比受限访问级别的同时，促进了代码复用。

```java
public class Base {
    protected int baseNumber;
}

public class Derived extends Base {
    public void show() {
        baseNumber = 10; // 由于保护级访问可以访问
        System.out.println("Base number is: " + baseNumber);
    }
}
```

理解作用域和可见性的细微差别可以显著影响 Java 应用的设计和安全性，确保数据完整性和系统健壮性。

# 面向对象编程基础

## 6.1 面向对象编程简介

### 6.1.1 OOP 概念概述

面向对象编程（OOP）是一种基于“对象”概念的编程范式，对象可以包含以字段形式（通常称为属性或属性）存在的数据以及以过程形式（通常称为方法）存在的代码。OOP 将现实世界的实体建模为具有状态和行为的对象，封装了相关的数据和操作这些数据的功能。

OOP 的核心概念包括：

- **类（Classes）**：创建对象的模板，定义了它们的结构和行为。
- **对象（Objects）**：类的实例，代表特定的实体。
- **继承（Inheritance）**：从现有类创建新类的机制，增强了代码的可复用性。
- **多态（Polymorphism）**：在不同对象上调用相同方法并让每个对象以其自己的方式做出响应的能力。
- **封装（Encapsulation）**：将数据和操作数据的方法封装在一个单元内，限制对该对象某些组件的访问。

### 6.1.2 面向对象编程的优势

- **模块化（Modularity）**：对象的源代码可以独立于其他对象的源代码进行编写和维护。这使得管理大型应用程序变得更容易。
- **代码复用（Reuse of Code）**：通过继承，新类可以从现有类派生，继承其属性和方法，从而实现显著的代码复用。
- **可扩展性（Scalability）**：OOP 允许通过增量添加新对象来构建程序，使得处理更大的软件项目变得可行。
- **维护（Maintenance）**：通过封装，对象可以隐藏其内部状态并在不影响代码其他部分的情况下进行更改，从而便于维护。
- **设计益处（Design Benefits）**：OOP 方法论鼓励设计阶段的规划和思考过程，使设计更加灵活、模块化和抽象。

### 6.1.3 OOP 与过程化编程

虽然 OOP 以对象和数据组织代码，但过程化编程以过程或例程为中心。主要区别包括：

- **状态与行为**：在 OOP 中，数据（状态）和操作（行为）封装在一起；而在过程化编程中，过程对传入它们的数据进行操作。
- **模块化与维护**：OOP 为程序提供了更清晰的模块化结构，更容易跟踪程序元素、增强它们并修复错误。
- **可复用性与可扩展性**：面向对象的程序鼓励代码复用。

### 6.1.4 OOP 术语：类、对象、方法和属性

- **类（Class）**：创建对象的模板。
- **对象（Object）**：类的实例。
- **方法（Method）**：对象执行的操作。
- **属性（Property）**：对象的特征。

## 6.2 与类和对象工作

### 6.2.1 在 Java 中定义类

在 Java 中，类是使用 `class` 关键字定义的模板，它包含了属性和方法。

```java
public class Car {
    // 类的属性
    String model;
    int year;

    // 类的方法
    void displayInformation() {
        System.out.println("Model: " + model + ", Year: " + year);
    }
}
```

### 6.2.2 创建和使用对象

对象是使用 `new` 关键字创建的类实例。一旦创建了对象，就可以访问其方法。

```java
public class TestCar {
    public static void main(String[] args) {
        // 创建 Car 对象
        Car myCar = new Car();
        myCar.model = "Toyota";
        myCar.year = 2020;

        // 使用 Car 的方法
        myCar.displayInformation();
    }
}
```

### 6.2.3 实例变量和方法

实例变量和方法属于类的实例。每个从类创建的实例都有自己的实例变量，并可以使用方法来操作它们。

```java
public class Student {
    String name; // 实例变量

    void introduce() { // 实例方法
        System.out.println("Hi, my name is " + name);
    }
}
```

### 6.2.4 静态变量和方法

静态变量和方法属于类而不是任何实例。这意味着可以在不创建类对象的情况下访问它们。

- **静态变量（Static Variables）**：也称为类变量，它们被所有实例共享。对静态变量的任何更改都会反映在所有实例中。
- **静态方法（Static Methods）**：无需创建对象即可调用的方法。它们可以访问静态变量并更改其值。

```java
public class Counter {
    static int count = 0; // 静态变量

    static void increment() { // 静态方法
        count++;
    }
}
```

理解类与实例成员的区别对于正确的编程实践至关重要，因为它们影响了信息在类和对象之间存储、共享和操作的方式。

## 6.3 理解构造函数

### 6.3.1 Java 中构造函数的目的

在 Java 中，构造函数是在实例化对象时调用的特殊方法。构造函数的名称与类名相同，且没有返回值（即使是 `void`）。构造函数的主要作用是在使用对象之前对新创建的对象进行初始化，通常是为其字段分配初始值。

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

### 6.3.2 构造函数的类型：默认构造与参数化构造

- **默认构造函数**：如果类中没有显式定义构造函数，Java 会自动提供一个没有参数的默认构造函数，它除了实例化对象外什么都不做。然而，如果类中显式声明了任何其他构造函数，则不再提供默认构造函数。

```java
public class Example {
    // Java 将在这里创建一个默认构造函数。
}
```

- **参数化构造函数**：一种包含参数的构造函数，用于在创建对象时初始化特定的状态。使用参数化构造函数，你可以在创建对象时为其提供不同的值。

```java
public class Book {
    String title;
    int pageCount;

    // Parameterized constructor
    Book(String title, int pageCount) {
        this.title = title;
        this.pageCount = pageCount;
    }
}
```

### 6.3.3 构造函数重载

构造函数重载是 Java 中的一项特性，一个类可以拥有多个接受参数不同的构造函数。它允许你根据在对象创建时所可用的信息，以不同的方式创建对象。

```java
public class Rectangle {
    int length;
    int width;

    // Default constructor
    Rectangle() {
        this.length = this.width = 0;
    }

    // Parameterized constructor 1
    Rectangle(int side) {
        this.length = this.width = side;
    }

    // Parameterized constructor 2
    Rectangle(int length, int width) {
        this.length = length;
        this.width = width;
    }
}
```

### 6.3.4 构造函数链

构造函数链指的是相对于当前对象从一个构造函数调用另一个构造函数的过程。可以通过 `this()` 和 `super()` 调用来实现。使用 `this()` 允许你调用同一类中另一个重载的构造函数，而 `super()` 则调用父类的构造函数。

```java
public class Student {
    String name;
    int age;

    // Constructor with 1 parameter
    Student(String name) {
        this(name, 18); // 调用带有2个参数的构造函数
    }

    // Constructor with 2 parameters
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
        super(name); // 调用父类的构造函数
        this.salary = salary;
    }
}
```

构造函数链通过允许构造函数利用另一个构造函数的初始化过程，简化了代码并消除了冗余。

## 6.4 OOP 的支柱：封装、继承和多态

### 6.4.1 封装：使用访问修饰符保护数据

封装是面向对象编程中的基本概念，涉及将数据（属性）和作用于数据的代码（方法）封装成一个单元。此外，它限制了对对象某些组件的直接访问，这是防止意外修改数据的手段。对限制组件的访问通常通过 getter 和 setter 方法实现。

Java 使用访问修饰符来保护变量和方法。最常用的访问修饰符有：

- **Private（私有）**：成员仅在其类内部可访问。
- **Protected（保护）**：成员在自己的包内以及子类中可访问。
- **Public（公共）**：成员可以从任何其他类访问。

```java
public class Account {
    private double balance;

    // Getter method
    public double getBalance() {
        return balance;
    }

    // Setter method
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }
}
```

### 6.4.2 继承：扩展类和代码复用

继承允许一个类继承另一个类的方法和字段。在 Java 中，继承用于促进代码复用并建立类与类的关系。

#### 创建子类

要继承一个类，你使用 `extends` 关键字。被继承的类被称为父类（superclass），而继承的类被称为子类（subclass）。

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

#### 方法重写和 super 关键字

方法重写发生在子类为其父类已提供的方法的特定实现时。`super` 关键字用于访问父类方法。

示例：

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Pig extends Animal {
    @Override
    void sound() {
        super.sound(); // 调用父类方法
    }
}
```

### 6.4.3 多态：静态与动态

Java 中的多态有两种类型：编译时（静态）和运行时（动态）。

#### 方法重载

方法重载（静态多态）发生在同一个类中，当两个或多个方法的名称相同但参数不同时。

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

#### 方法重写和动态方法调度

方法重写（动态多态）允许子类重写父类的方法。动态方法调度是一种在运行时解析重写方法调用的机制。

示例：



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

    // override area method
    double area() {
        System.out.println("Inside Area for Rectangle.");
        return dim1 * dim2;
    }
}
```

## 6.4.4 抽象类和接口：强制合约

* **抽象类**：抽象类不能实例化，并且可以包含抽象方法，即没有体的方法。当你想在多个相关类之间共享代码时，可以使用它们。

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

* **接口**：接口是一个完全“抽象类”，用于将带有空方法的分组在一起。类可以实现多个接口，从而克服了单继承的限制。

```java
interface Animal {
    void sound(); // 接口方法（没有体）
}

class Pig implements Animal {
    public void sound() { // 在这里提供了 sound() 的体
        System.out.println("The pig says: wee wee");
    }
}
```

## 7.1.1 理解继承的基础知识

继承允许一个新类（称为子类或派生类）吸收另一个类（称为父类或基类）的成员（字段、方法和构造函数）。其主要优势是可以定义一个公共基类，以便在多个派生类之间共享代码。

核心概念包括：

* **父类与子类**：父类是被其他类继承的类，而子类是继承自父类的类。
* **`extends` 关键字**：在 Java 中，类使用 `extends` 关键字来声明它继承自另一个类。

### 7.1.2 创建和扩展父类

创建父类涉及定义一个普通类，其他类将继承自该类。使用 `extends` 关键字来扩展此类。例如，如果 `Animal` 是一个父类，可以如下方式创建一个继承自 `Animal` 的子类 `Dog`：通过扩展 `Animal`，`Dog` 继承了 `eat` 方法，并且还可以定义自己的方法，如 `bark`。

### 7.1.3 利用 `protected`（受保护）访问修饰符

`protected` 访问修饰符在继承中起着至关重要的作用。在父类中声明为 `protected` 的成员可以被子类访问（包括包外的子类），但不能被包外的其他类访问。

该修饰符有助于封装父类的成员，允许对它们进行受控访问，而不是 `public`（公共）访问（这可能会暴露过多的类内部细节）或 `private`（私有）访问（这将阻止子类访问重要成员）。

### 7.1.4 探索继承层次结构和多重继承问题

当一个类继承自一个子类时，就会形成层次结构，创建一个具有多个级别的类“族树”。这允许在每个子类层级实现更具体的分类和行为。

Java 不支持通过类进行多重继承，以避免“菱问题”（即一个类继承自两个具有相同签名方法的类）。这可能会让编译器在调用哪个方法时感到困惑。然而，Java 通过允许一个类实现多个接口来解决多重继承的需求。

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

在这里，`Bat` 继承自 `Mammal`，而 `Mammal` 继承自 `Animal`，形成了一个层次结构。通过正确理解和实现继承，开发者可以创建灵活且易于维护的代码库。

## 7.2 使用 `super` 和方法重写

`super` 关键字的使用和方法重写的概念在 Java 继承实现中起着重要作用，增强了功能性和多态性。

### 7.2.1 `super` 关键字在访问父类成员中的作用

Java 中的 `super` 关键字是一个引用变量，用于引用直接父类对象。它可以用于访问在子类中被重写或隐藏的父类方法和构造函数。

* **访问父类方法**：`super` 可以调用在子类中被重写的父类方法。当你希望在子类中同时访问方法的父类和子类版本时，这特别有用。
* **调用父类构造函数**：`super()` 可以调用父类构造函数。`super()` 的调用必须是子类每个构造函数的第一条语句。如果子类构造函数没有显式调用父类构造函数，Java 编译器会自动插入对父类无参数构造函数的调用。

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

### 7.2.2 在子类中重写方法

当子类重新定义其父类中的方法时，就会发生方法重写。重写允许子类为其父类提供的方法提供特定的实现。

重写规则：参数列表必须与被重写的方法完全匹配。返回类型也必须相同或子类型（协变返回类型）。此外，子类不能重写声明为 `final` 或 `static` 的方法。

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

### 7.2.3 方法重写的规则和最佳实践

1.  **签名匹配**：方法名和参数必须与父类中的方法签名完全匹配。
2.  **访问级别**：访问级别不能比被重写方法的访问级别更严格。
3.  **返回类型**：必须是父类方法返回类型的相同类型或子类型（协变返回类型）。
4.  **调用父类方法**：有时，在重写方法中使用 `super` 调用父类版本是有益的。

遵循这些规则可以确保拥有结构整洁、功能完备且行为可预测的继承层次结构。

### 7.2.4 注解 `@Override` 的意义

`@Override` 注解表示该方法旨在重写其父类中的方法。如果该方法实际上没有重写父类，编译器将产生错误。此注解提高了代码的可读性，并有助于避免错误，例如拼错方法名。

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

## 7.3 接口和抽象类

接口和抽象类是实现抽象和多重继承（通过接口）两个关键概念。它们为类设定蓝图，引导它们需要实现的方法。

### 7.3.1 定义和实现接口

Java 中的接口是一种引用类型，类似于类，可以包含常量、方法签名、默认方法、静态方法和嵌套类型。接口不包含实例字段。接口中的方法默认是抽象的。定义接口使用 `interface` 关键字。类实现接口并为所有抽象方法提供具体实现。

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

### 7.3.2 比较接口与抽象类

接口和抽象类都可以拥有抽象方法，但存在关键区别：

* **抽象类**：可以包含带有实现或不带实现的方法。子类只能继承一个抽象类。
* **接口**：在 Java 8 之前，接口只能包含不带实现的抽象方法。从 Java 8 开始，它们可以拥有默认和静态方法。一个类可以实现多个接口。

当子类共享带有实现的方法使用抽象类。接口通常用于定义一组由任何类提供的公共功能，无论其在类层次结构中的位置如何。

### 7.3.3 在接口中使用默认和静态方法

Java 8 引入了通过默认和静态方法在接口中定义具体方法的能力。这允许在接口中添加新功能，而不影响实现这些接口的类。

* **默认方法**：允许在接口中实现方法。实现接口的类可以重写默认方法。

```java
interface Vehicle {
    default void print() {
        System.out.println("I am a vehicle!");
    }
}
```

* **静态方法**：可以在接口内声明，且不能被实现类重写。

```java
interface Animal {
    static void test() {
        System.out.println("Static method in interface");
    }
}
```

### 7.3.4 应用接口多重继承

在 Java 中，多重继承——一个类继承多个父类的行为的能力是不被直接支持的（为了避免“菱形问题”）。然而，Java 允许通过接口实现多重继承。一个类可以实现多个接口，从而继承多个源的抽象方法。

多重继承示例：

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

## 7.4 多态的实际应用

多态是面向对象编程中的核心概念，它允许操作根据执行操作的实际对象以不同的方式运行。它增强了代码的灵活性和在不修改代码的情况下进行扩展的能力。Java 中的多态有两种类型：静态（编译时）和动态（运行时）。

### 7.4.1 演示静态多态与动态多态

* **静态多态**通过方法重载实现。它发生在编译时。在静态多态中，对函数的响应是由编译时的参数列表决定的。

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

* **动态多态**通过方法重写实现，这意味着要调用的精确方法是在运行时根据对象的实例化来决定的。

### 7.4.2 方法重载 vs 方法重写

* **方法重载（静态多态）**：它允许一个类拥有多个同名但方法签名不同（即参数列表不同）的方法。通过根据输入参数以不同方式处理相同的方法，它提高了代码的可读性和可重用性。
* **方法重写（动态多态）**：它允许子类为已由父类提供的方法提供特定的实现。子类中的方法名称、返回类型和参数必须与父类中的方法相同。

### 7.4.3 动态方法分派

动态方法分派是一种机制，其中对重写方法的调用在运行时解析，而不是在编译时解析。这就是 Java 实现运行时多态的方式。

在这种场景下，引用类型 `Animal` 并不决定调用哪个版本的 `sound()`。要调用的方法在运行时由实例的类型决定。

### 7.4.4 多态的现实世界示例

1.  **图形用户界面（GUI）元素**：不同的对象（如按钮、文本框和复选框）可能继承自一个公共父类（例如 `Component`）。每个对象都可以重写 `draw()` 方法来渲染自己。在遍历组件集合并调用 `draw()` 时，多态确保了为每个元素调用了正确的方法。
2.  **支付处理系统**：在支付系统中，不同的支付方式（信用卡、PayPal、银行转账）可能派生自 `Payment` 超类。每种方法都有其自己的 `processPayment()` 方法实现。多态允许系统以统一的方式处理不同的支付类型，增强了代码的重用性和灵活性。

多态（无论是静态还是动态）在简化复杂性方面起着至关重要的作用，它允许同一个接口用于不同的底层形式（数据类型或类），促进了代码的可重用性和系统的扩展性。

# 异常处理

## 8.1 理解异常

异常是程序执行过程中发生的破坏指令正常流的事件。在 Java 中，异常是在运行时抛出的一个对象，用于表示发生了异常情况。恰当地处理异常允许你的程序继续运行或优雅地终止，而不是因为不可见的问题而崩溃。

### 8.1.1 什么是异常？

异常可以是执行程序遇到的任何错误条件或意外行为。当此类情况发生时，会创建一个代表该异常的对象，并从导致错误的方法抛出。该方法可以选择自己处理异常，也可以将其传递下去。如果方法没有处理异常，运行时系统将尝试在调用栈中寻找另一个可以处理异常的方法，如果未被捕获，最终会导致程序终止。

### 8.1.2 异常的类型

Java 中的异常主要分为两类：受检异常和未检异常。

**受检异常**

受检异常是在编译检查的异常，这意味着编译器要求代码要么处理这些异常，要么在方法签名中使用 `throws` 关键字声明它们。受检异常的存在标志着可以预料但无法避免的问题，合理的应用程序应该预见到并从中恢复。受检异常的示例是 `FileNotFoundException`。

**未检异常**

未检异常代表程序中的缺陷——通常是逻辑错误。这些异常在编译时不进行检查；它们在运行时检查。由于它们反映了编程错误，通常是不被预期的。示例包括 `NullPointerException` 和 `ArrayIndexOutOfBoundsException`。

### 8.1.3 异常层次结构

所有异常类都是 `Throwable` 类的后代。`Throwable` 类分为两个主要的子类：`Error`（用于应用程序不应尝试捕获的错误条件）和 `Exception`，后者进一步分为受检异常和运行时异常（未检异常）。

### 8.1.4 常见异常场景与处理策略

* **输入/输出操作**：这些操作容易失败，原因有很多，如文件不存在或硬件故障。策略包括使用 `try` 处理这些异常，或使用 `throws` 声明它们。
* **空指针访问**：像数组一样访问或修改空值。在访问方法或字段之前进行空值检查可以缓解此问题。
* **数组越界**：尝试访问数组大小之外的元素。在访问数组之前确保索引检查可以防止此类问题。
* **类型转换异常**：将对象转换为其不是其实例的子类。可以通过转换前使用 `instanceof` 检查来防止。

异常处理的关键不仅在于防止程序崩溃，还在确保资源（如文件句柄或网络连接）得到适当清理，并为用户和日志提供有意义的错误信息以便调试。仔细的规划和异常使用可以显著提高软件的可靠性和可维护性。

## 8.2 `try`、`catch` 和 `finally` 块

`try`、`catch` 和 `finally` 块构成了 Java 异常处理机制的核心。它们共同工作以受控的方式捕获并处理异常，确保程序能够从错误中恢复并执行必要的清理操作。

### 8.2.1 `try` 块

`try` 块允许你定义一段代码块，并在执行时对其进行错误测试。

#### 在 `try` 块中编写易出异常的代码

任何预期会抛出异常的代码都应该封装在 `try` 块中。例如，处理文件操作、解析或网络连接的代码经常遇到异常情况，是包含在 `try` 块中的理想人选。

示例：



```
try {
  // 可能抛出异常的代码
  FileReader fr = new FileReader("file.txt");
  // 使用文件...
} catch (FileNotFoundException e) {
  // 处理异常
}
```

### 8.2.2 catch 块

`catch` 块用于处理异常。它必须在 `try` 块之后使用。在括号中，你指定了想要捕获的异常类型。

#### 处理不同的异常

不同类型的异常可以被捕获并进行不同的处理。良好的做法是先捕获特定异常，然后捕获更通用的异常，以提供更详细的错误处理。

#### 多个 catch 块

一个 `try` 块后面可以跟随多个针对不同异常类型的 `catch` 块。这允许对每个异常类型进行特定处理。

示例：

```
try {
  // 可能抛出多个异常的代码
} catch (ArithmeticException e) {
  // 对 ArithmeticException 的特定处理
} catch (NullPointerException e) {
  // 对 NullPointerException 的特定处理
}
```

### 8.2.3 finally 块

`finally` 块包含在 `try` 和 `catch` 块执行后必须执行的代码，无论是否捕获到异常。

#### 保证资源释放和清理操作

`finally` 块是清理代码的理想选择，例如关闭文件流或释放网络连接，以确保资源不泄露。

`try`、`catch` 和 `finally` 块的组合提供了一种处理异常的健壮机制，确保你的程序能够优雅地处理错误并维护资源的完整性。

## 8.3 创建自定义异常

自定义异常允许开发者创建特定的错误条件，这些条件可以根据应用程序需求更具描述性和针对性。通过定义特定于应用程序领域的异常，它们为错误处理增加了清晰度。

### 8.3.1 为什么要创建自定义异常？

自定义异常提供了多处好处：

- 增强语义化：通过清晰地指示发生的特定问题，使你的代码更具可读性和理解性。
- 一致的错误报告：允许在整个应用程序中进行统一的错误报告和处理。
- 特定的异常处理：能够创建针对应用程序需求进行精细调整的异常处理机制。

### 8.3.2 扩展 Exception 类

在 Java 中创建自定义异常，只需扩展 `Exception` 类或其任何子类即可。

示例：

```java
public class MyCustomException extends Exception {
    public MyCustomException(String message) {
        super(message);
    }
}
```

如果你倾向于创建一个非检查异常，也可以扩展 `RuntimeException`。

### 8.3.3 实现自定义异常逻辑

在创建自定义异常时，你可以添加额外的字段和方法，以提供有关错误条件的更多信息。

示例：

```java
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

此示例包含一个接受数据库名称和错误消息的构造函数，并提供了一个数据库名称的 getter 方法。

### 8.3.4 在应用程序中使用自定义异常

自定义异常可以像任何其他异常一样在你的应用程序中使用，额外的好处是更具表现力。

示例：

```java
public class DatabaseService {
    public void connectToDatabase(String dbName) throws DatabaseConnectionException {
        // ...
    }
}

public class App {
    public static void main(String[] args) {
        DatabaseService dbService = new DatabaseService();
        try {
            dbService.connectToDatabase("myDatabase");
        } catch (DatabaseConnectionException e) {
            System.err.println("Failed to connect to " + e.getDbName());
        }
    }
}
```



```java
public class DatabaseService {
    public void connectToDatabase(String dbName) throws DatabaseConnectionException {
        // ...
    }
}

public class App {
    public static void main(String[] args) {
        DatabaseService dbService = new DatabaseService();
        try {
            dbService.connectToDatabase("myDatabase");
        } catch (DatabaseConnectionException e) {
            System.err.println("Failed to connect to " + e.getDbName());
        }
    }
}
```

在应用程序中使用自定义异常可以像任何其他异常一样在你的应用程序中使用，其额外的好处是更具表现力。

示例：

```java
public class DatabaseService {
    public void connectToDatabase(String dbName) throws DatabaseConnectionException {
        // ...
    }
}

public class App {
    public static void main(String[] args) {
        DatabaseService dbService = new DatabaseService();
        try {
            dbService.connectToDatabase("myDatabase");
        } catch (DatabaseConnectionException e) {
            System.err.println("Failed to connect to " + e.getDbName());
        }
    }
}
```

## 8.4 异常处理中的最佳实践

良好的异常处理对于程序的健壮性和维护性至关重要。遵循最佳实践不仅使代码更健壮，而且易于维护。

### 8.4.1 避免常见陷阱

某些异常实践会导致代码难以调试。为了避免这些陷阱，应尽可能捕获特定的异常。

#### 捕获通用异常

捕获基类 `Exception`（或 `Throwable`）会增加诊断难度，因为它可能捕获了比你预期的更多的异常。相反，应捕获特定的异常。

**错误做法：**

```
try {
    // 风险代码
} catch (Exception e) {
    // 通用处理
}
```

**更好的做法：**

```
try {
    // 风险代码
} catch (SpecificException e) {
    // 特定处理
}
```

#### 忽略异常

静默捕获并忽略异常可能会让程序处于不可预测的状态，难以诊断问题。

**错误做法：**

```
try {
  // 风险代码
} catch (Exception e) {
  // 忽略
}
```

**更好的做法：**

始终以有意义的方式处理异常，或者至少将其记录。

```
try {
  // 风险代码
} catch (Exception e) {
  log.error("发生错误", e);
}
```

### 8.4.2 使用 finally 进行清理

无论是否抛出异常，你通常都需要执行某些清理代码（例如关闭文件流或数据库连接）。`finally` 块确保了这些代码的执行。

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

在 JavaDoc 中记录方法可能抛出的异常，使用 `@throws` 或 `@exception` 标签。这些文档对于使用你方法的开发者来说至关重要，让他们了解涉及的风险以及如何处理潜在问题。

```java
/**
 * 连接到指定的数据库。
 * 
 * @param dbName 数据库名称。
 * @throws DatabaseConnectionException 如果连接失败。
 */
public void connectToDatabase(String dbName) throws DatabaseConnectionException {
    // 实现
}
```

### 8.4.4 异常处理与应用程序设计决策

异常处理应该是设计阶段的一部分，而不是事后考虑。及早决定哪些异常应该是检查的（checked）是非检查的，如何使用自定义异常进行更清晰的错误报告，并建立在应用程序不同层级如何处理异常的准则。

良好的异常处理可以极大地提高应用程序的健壮性、可维护性和用户体验。它是一个贯穿整个软件生命周期影响架构和设计决策的关键方面。

# 深入理解 Java 集合框架

## 9.1 Java 集合概述

Java 集合框架 (JCF) 是一组实现了常用复用集合数据结构的类和接口。它是 Java 最强大且最灵活的 API 之一，包含了各种可以动态存储对象的数据结构。

### 9.1.1 集合框架简介

集合框架在 Java 2 中引入，为表示和操作集合提供了统一的架构。它极大地改进了处理对象集合的方式，允许通过一致的 API 进行数据操作。该框架包含了 `List`、`Set` 和 `Map` 等接口，以及 `ArrayList`、`HashSet` 和 `HashMap` 等实现类。

### 9.1.2 Collection 接口

框架的核心是 `Collection` 接口，它为所有集合类型提供了标准功能。`Collection` 接口是 `List`、`Set` 和 `Queue` 等接口的基础，每个接口对应不同的抽象数据类型。实现类必须提供添加、删除和查询集合大小等常用操作的功能。

### 9.1.3 集合的关键特性

集合的关键特性包括：

- 动态大小：与数组不同，集合的大小可以动态增长或缩小，以根据需要容纳更多元素。
- 类型安全：泛型允许集合强制类型安全，确保只存储指定类型的对象，从而减少运行时错误。
- 可迭代性：可以使用迭代器（iterators）或增强型 for 循环对集合进行迭代，使得遍历和操作元素变得更容易。
- 数据操作：集合提供了添加、删除和搜索元素的方法，比基本数据类型或数组提供了更大的灵活性。

### 9.1.4 集合、数组和基本数据类型的比较

集合与数组及基本数据类型在多个方面有所不同：

- 大小与灵活性：集合是动态的，而数组具有固定大小。集合比数组提供了更多的灵活性功能。
- 性能：对于某些操作（如添加或删除元素），由于增加了抽象层，集合可能比数组慢。然而，某些集合类型针对特定操作进行了优化。
- 类型安全与实用性方法：集合支持泛型，与数组相比增强了类型安全。此外，集合框架为排序和搜索等常见任务提供了实用方法，而这些操作在数组上非常繁琐。

### 9.1.5 选择合适的集合

选择合适的集合类型取决于几个因素：

- 顺序：如果你需要维护插入顺序，请考虑 `ArrayList` 或 `LinkedHashSet`。
- 重复：如果集合不能包含重复元素，请使用 `HashSet` 等 `Set` 实现。
- 键值对：为了以键值对的形式存储数据以便高效检索，请使用 `HashMap` 等 `Map` 实现。
- 访问：如果你需要通过索引快速访问元素，请使用 `ArrayList` 等 `List` 实现。
- 并发：在多线程环境中工作时，请考虑 `java.util.concurrent` 包中的线程安全或并发集合。

选择合适的集合类型可以同时优化代码的性能和可读性，使集合框架成为高效 Java 开发的基石。

## 9.2 List、Set 和 Queue

Java 集合框架将其数据结构划分为几个核心接口，每个接口都有不同的数据管理目的。其中，`List`、`Set` 和 `Queue` 接口是基础性的，每个都满足特定的需求。

### 9.2.1 理解 List 接口

Java 中的 `List` 接口允许对元素进行有序集合，包括重复元素。在元素的插入顺序很重要或需要对元素进行直接位置访问的场景下，`List` 表现出色。

#### ArrayList

- 描述：一种基于可伸缩数组的 `List` 接口实现。它通过索引提供快速元素访问。
- 使用场景：适用于插入和删除操作极少但访问操作大量的场景。
- 主要特性：自动调整大小，快速的随机访问。

#### LinkedList

- 描述：`List` 和 `Deque` 接口的双向链表实现。它允许在列表的开头或结尾以常数时间插入和删除。
- 使用场景：适用于频繁插入和删除的应用。
- 主要特性：每个元素（节点）都包含指向下一个和上一个节点的引用。

#### Vector 和 Stack

- Vector 描述：一种 `List` 接口的同步、可伸缩数组实现。比 `ArrayList` 慢，但适用于线程安全操作。
- Stack 描述：一个扩展 `Vector` 的同步类，表示后进先出（LIFO）栈。

### 9.2.2 探索 Set 接口

`Set` 接口模拟了数学中的集合，不包含重复元素。

#### HashSet

- 描述：一种基于哈希表的 `Set` 接口实现。它不保证任何顺序。
- 使用场景：适用于需要唯一性但不在意顺序的场景。
- 主要特性：基本操作（`add`、`remove`、`contains`）具有常数时间性能。

#### LinkedHashSet

- 描述：`HashSet` 的扩展，维护了一个贯穿其条目的双向链表。
- 使用场景：当必须保留插入顺序时有用。
- 主要特性：由于链表维护，比 `HashSet` 略慢。

#### TreeSet

- 描述：一种在树结构中存储元素的 `Set` 接口实现。
- 使用场景：适用于需要对元素进行排序或范围搜索的理想场景。
- 主要特性：保证操作具有 log(n) 时间代价。

### 9.2.3 使用 Queue 接口

`Queue` 支持典型的队列操作，主要满足 FIFO（先入先出）。

#### PriorityQueue

- 描述：一种基于堆的无界优先级队列。元素根据其自然顺序或通过比较器进行排序。
- 使用场景：适用于你希望根据优先级处理元素的场景。
- 主要特性：不允许 `null` 元素。

#### Deque 接口

一种支持在两端插入和删除元素的线性集合。它是栈（stack）和双队列（deque）的泛化。

#### ArrayDeque

- 描述：一种 `Deque` 接口的可伸缩数组实现。
- 使用场景：作为栈或队列使用时，比 `Stack` 和 `LinkedList` 快。
- 主要特性：没有容量限制。

#### LinkedList 作为 Deque

- 描述：虽然主要是列表，但 `LinkedList` 也实现了 `Deque` 接口。
- 使用场景：适用于同时需要列表和双队列功能的情况。
- 主要特性：双向链表允许常数时间的插入和删除。

## 9.3 Map 及其实现

Java 中的 `Map` 为管理键值对提供了强大的方式，允许根据键进行高效存储和检索。理解不同 `Map` 实现的细微差别有助于为特定用例选择正确的实现。

### 9.3.1 理解 Map 接口

`Map` 接口表示键值对映射；键是唯一的，每个键映射到一个值。`Map` 不是 `Collection` 接口的扩展；它有自己的层次结构。

#### HashMap

- 描述：实现了 `Map` 接口，使用哈希表。它允许 `null` 值和单个 `null` 键，假设哈希函数能够良好地分散到各个桶中，基本操作（`get` 和 `put`）具有常数时间性能。
- 使用场景：当插入顺序不重要且需要快速访问元素时，效果最好。
- 关键特性：对 `HashMap` 视图（键、值、条目）的迭代取决于哈希表的容量和键值对的数量。

#### LinkedHashMap

- 描述：一种内部运行着链形列表的 `HashMap`，因此它维护了插入顺序（或可选的访问顺序）。除了排序行为外，它的特性与 `HashMap` 相同。
- 使用场景：适用于需要保留插入/访问顺序的场景。
- 关键特性：由于为了维护顺序而采用了增强的结构，其在迭代方面的性能略低于 `HashMap`。

#### TreeMap

- 描述：实现了 `NavigableMap` 接口，并根据键的自然顺序或指定的 `Comparator` 来排列键。它基于红黑树结构。
- 使用场景：当需要提取键的范围或要求键进行排序时是理想选择。
- 关键特性：为 `containsKey`、`get`、`put` 和 `remove` 操作提供了保证的 log(n) 时间成本。

### 9.3.2 比较 Map 实现类

| 特性/Map 类型 | HashMap | LinkedHashMap | TreeMap |
|---|---|---|---|
| 排序 | 无顺序 | 插入/访问顺序 | 排序顺序 |
| Get/Put 时间 | 平均 O(1) | 平均 O(1) | O(log n) |
| 迭代顺序 | 随机 | 插入/访问顺序 | 键的升序顺序 |
| 键是否为空 | 允许一个 null 键 | 允许一个 null 键 | 不允许 null 键（如果使用自然排序） |
| 使用场景 | 需要映射的最常见场景 | 访问顺序很重要时 | 需要排序顺序或范围搜索时 |

### 9.3.3 特殊 Map 实现类

#### WeakHashMap

- 描述：一种 `HashMap` 变体，将键存储为弱引用。当 `WeakHashMap` 中的键不再被普通使用时，该条目将自动被移除。
- 使用场景：适用于缓存和元数据存储，其中存储数据的生命周期取决于对键的外部引用。
- 关键特性：当键不再被引用时，垃圾回收器会自动删除条目。

#### EnumMap

- 描述：一种用于枚举（enum）类型键的特殊 `Map` 实现。`EnumMap` 中的所有键必须来自一个单个枚举类型，该类型在创建 map 时显式或隐式地指定。
- 使用场景：当使用枚举进行基于键的数据访问时，极其高效且紧凑。
- 关键特性：map 的迭代顺序遵循枚举键的自然顺序。

#### Hashtable (遗留)

- 描述：一种早期的 map 数据结构实现，它是同步的，这意味着它是线程安全的，但在单线程场景下的性能低于 `HashMap`。
- 使用场景：现在被认为是遗留类，在存在 `ConcurrentHashMap`（用于线程安全的 map）的情况下，极少建议使用它。
- 关键特性：与 `HashMap` 不同，它不允许 `null` 键或值。

选择正确的 `Map` 实现类可以极大地影响 Java 应用程序的性能和资源消耗，特别是在处理大型数据集或性能关键型应用程序时。

## 9.4 Collection 类工具

Java 集合框架不仅提供了多种数据结构，还通过 `Collections` 类包含了一套强大的工具类。这些工具提供了用于排序、搜索、修改和转换集合的方法，增强了高效管理和操作数据的能力。

### 9.4.1 集合排序

排序是集合的一项基本操作，允许元素按特定顺序排列。

#### 使用 Comparable

- 描述：`Comparable` 接口提供了一个单一的 `compareTo` 方法，定义了对象的自然顺序。实现此接口的类可以很容易地排序。
- 工作原理：将对象与另一个对象进行比较以确定顺序，根据该对象小于、等于或大于指定对象返回负整数、零或正整数。

#### 使用 Comparator

- 描述：`Comparator` 接口定义了一个 `compare` 方法，允许在对象外部控制对象的顺序。当一个类无法修改以实现 `Comparable`，或者当需要多种排序顺序时，它特别有用。
- 工作原理：它比较两个参数以确定顺序，根据第一个参数是小于、等于还是大于第二个参数，返回负整数、零或正整数。

### 9.4.2 在集合中搜索

- 技术：`Collections.binarySearch()` 提供了一种在排序后的列表中搜索特定对象的高效方法。该集合必须根据元素的自然顺序（或使用指定的 `Comparator`）按升序排序。

### 9.4.3 集合与数组之间的转换

- 方法：集合接口中的 `toArray()` 方法将集合转换为数组。相反，`Arrays.asList()` 提供了一个由指定数组支持的固定大小列表，作为基于数组的 API 和基于集合的 API 之间的桥梁。

### 9.4.4 Collections 类工具概览

- `Collections.sort()`：将列表按升序排序，可以使用其元素的自然顺序（`Comparable`）或使用指定的 `Comparator`。
- `Collections.binarySearch()`：使用二分查找算法在给定的排序列表中搜索指定对象，这需要有序的集合才能获得有意义的结果。
- `Collections.reverse()`，`Collections.shuffle()`：
  - `Collections.reverse()` 反转列表的顺序。
  - `Collections.shuffle()` 随机化元素的顺序。
  - 这些以及其他方法提供了修改集合的便利实用程序。

### 9.4.5 使用 synchronizedList, synchronizedSet, synchronizedMap 实现线程安全

- 目的：封装标准集合并返回它们的线程安全版本。当集合被多个线程访问时，这一点至关重要。



## 9.4.6 高级工具：unmodifiableCollection 和其他不可修改封装

- 提供集合的只读访问，保护其免受修改尝试，修改尝试将抛出 `UnsupportedOperationException`。
- 使用 `Collections.singleton()`、`Collections.emptyList()` 和 `Collections.emptyMap()`：这些方法对于优化目的非常有用，可以减少内存占用并提高性能。
- 它们返回不可变实例，确保集合无法被更改。

## 10.1.4 Try-with-Resources 和 AutoCloseable 接口

文件处理和流操作中的一个重要关注点是确保资源在使用后正确关闭，以防止资源泄露。Java 在 Java 7 中引入的 `try-with-resources` 语句简化了语句执行结束时的资源关闭工作。为了与该语句兼容，资源必须实现 `AutoCloseable` 接口，该接口包含了所有的流和相关资源。以下是其用法的简洁示例：

在这个示例中，`FileReader` 是实现 `AutoCloseable` 的资源。一旦退出 `try` 块（无论是正常退出还是由于异常），它都会自动关闭，从而显著减少了样板代码并降低了资源泄露的风险。

## 10.2 NIO 包

### 10.2.1 Java NIO 简介

Java NIO（新输入/输出）在 Java 1.4 中引入，作为标准 Java I/O API 的替代方案和补充。它提供了非阻塞 IO 操作、面向缓冲器的数据处理方法，以及通过单个线程管理多个网络连接的能力。NIO 的核心组件包括通道（Channels）、缓冲区（Buffers）、选择器（Selectors）和字符集，实现了更快速、更具扩展性的 I/O 操作，特别是对于需要同时管理大量连接的应用（如 Web 服务器）。

### 10.2.2 缓冲区：NIO 的核心

缓冲区（Buffers）是 NIO 中的核心概念，代表一段连续的内存，数据在 I/O 操作期间临时存储其中。与传统 I/O 模型中以线性、顺序方式处理数据的流不同，缓冲区允许对数据的随机读写。Java NIO 中的缓冲区是分类型的；即针对不同的数据类型有不同的缓冲区类，如 `ByteBuffer`、`CharBuffer`、`IntBuffer` 等。这些缓冲区在 `flip`（翻转）机制下运行，缓冲区从写模式切换到读模式，确保了高效的数据访问和处理。

### 10.2.3 通道：处理 IO 的新方式

通道（Channels）可以被看作是缓冲区和外部实体（例如文件或网络套接字）之间传输数据的管道。它们提供了一个统一的 API 来管理各种类型的 I/O 操作，如从文件读取和写入文件以及网络通信。主要的通道类型包括用于 I/O 的 `FileChannel`、用于 TCP 网络 I/O 的 `SocketChannel` 以及用于 UDP 网络 I/O 的 `DatagramChannel`。与流（streams）相比，通道支持在同一个实例上同时进行读和写，从而提供了更灵活、更强大的数据处理能力。

### 10.2.4 选择器：使用 NIO 进行多路复用

选择器（Selector）组件允许单线程监控多个通道事件的机制，例如数据到达、连接打开或读写就绪。这种能力使得开发高度可扩展的网络应用程序成为可能，无需为每个连接创建一个线程，显著减少了资源消耗并提高了性能。通过向选择器注册多个通道，应用程序可以以非阻塞的方式高效管理成千上万个打开的连接，检查 I/O 事件并在发生时进行处理。这对于实现处理许多并发连接的服务器（如 Web 或应用服务器）特别有用。

Java NIO 引入缓冲区、通道和选择器标志着 Java I/O 能力的重大增强，为开发者提供了构建高度可扩展且高效的网络和文件 I/O 应用的工具。从基于流的模型向面向缓冲区的模型转变，允许对数据处理方式进行更多的控制和灵活性，使 Java NIO 成为现代 Java 应用开发中的组成部分。

## 10.3 在 Java 中读写文件

### 10.3.1 使用 FileInputStream 和 FileOutputStream

`FileInputStream` 和 `FileOutputStream` 是来自 `java.io` 包的类，设计用于字节流的形式从文件读取和写入，它们在处理图像和可执行文件等二进制数据时非常有效。

- **FileInputStream**：它被用于从文件中读取数据。数据以字节格式读取，这意味着它是按字节逐字节读取的，适用于读取二进制文件。

```
FileInputStream fis = new FileInputStream("example.txt");
int i;
while ((i = fis.read()) != -1) {
    System.out.print((char) i);
}
fis.close();
```

- **FileOutputStream**：此类被用于向文件写入数据。与 `FileInputStream` 类似，它按字节逐字节操作数据。它对于向文件写入二进制数据特别有用。

```
FileOutputStream fos = new FileOutputStream("output.txt");
String data = "Hello World!";
fos.write(data.getBytes());
fos.close();
```

### 10.3.2 Reader 和 Writer 类

对于面向字符的数据（如文本文件），Java 在 `java.io` 包中提供了 `Reader` 和 `Writer` 抽象类。

- `FileReader` 和 `FileWriter` 是用于读写字符文件的子类。与字节流（`FileInputStream`/`FileOutputStream`）不同，这些设计用于处理字符，使得它们非常适合处理文本文件。

### 10.3.3 使用 NIO Files 类进行高效 IO

`java.nio.file` 包中的 `Files` 类提供了一系列用于文件和目录操作的静态方法。这些方法设计为使用 `Path` 对象，使得文件操作执行更加高效且简单。

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

### 10.3.4 Path 和 Paths：NIO2 增强

Java 7 引入的 NIO.2 文件 API 增加了 `Path` 接口和 `Paths` 工具类，为处理文件系统提供了更全面的方法。

- **Path**：代表与系统相关的路径。它是一个用于定位文件系统中文件的对象。提供了检查、定位和操作文件系统对象的方法。
- **Paths**：工具类，包含静态方法，可以通过转换路径字符串或 URI 返回 `Path`。

采用 `Files` 类以及 `Path`/`Paths` 接口可以使文件 I/O 操作更具可读性和可维护性，提供了符号链接处理、文件属性访问和目录遍历等高级功能，这些功能在传统的 I/O 流中无法直接获得。

## 10.4 理解字节流和字符流

### 10.4.1 字节流与字符流的区别

Java I/O 流分为两大类：字节流和字符流。字节流（`InputStream` 和 `OutputStream` 的子类）主要用于处理原始二进制数据，如图像文件、音频文件和序列化对象。它们按字节读写数据。字符流（`Reader` 和 `Writer` 子类）则设计用于处理字符数据，如文本文件。它们按字符读写数据，自动处理字符编码和解码，从而抽象了字符与字节之间转换的复杂性。

### 10.4.2 何时使用字节流而非字符流

当处理原始数据或不一定是字符二进制的文件时，应该使用字节流。示例包括：

- 读取或写入二进制文件（例如图像、视频）。
- 处理序列化对象。
- 与来自源或去往不代表字符的数据流交互。

字符流不表示文本数据。在处理文本数据时建议使用，因为它们考虑了字符编码，这对于国际化至关重要。用例包括：

- 读取或写入包含文本的文件。
- 处理源或目的地基于文本的数据流，例如文档文件或标准 I/O。

### 10.4.3 常见的字节流和字符流类

**字节流类：**

- `FileInputStream` 和 `FileOutputStream` 用于文件的读写。
- `BufferedInputStream` 和 `BufferedOutputStream` 用于缓冲 I/O 操作，通过减少 I/O 操作次数来提高效率。

**字符流类：**

- `FileReader` 和 `FileWriter` 用于读取和写入文本文件。
- `BufferedReader` 和 `BufferedWriter` 为字符输入输出流提供缓冲，使得文本读写更高效。

### 10.4.4 流操作的性能优化

1. **使用缓冲流**：将文件流封装在缓冲流（`BufferedInputStream`、`BufferedOutputStream`、`BufferedReader`、`BufferedWriter`）中，可以通过减少 I/O 操作次数来显著提高性能。
2. **重用对象**：在可能的情况下，在程序中重用 I/O 对象，以尽可能减少创建和销毁资源的开销。
3. **正确关闭资源**：始终使用 `finally` 块或 `try-with-resources` 语句来关闭流，确保所有资源都能释放，底层文件或套接字得到关闭。
4. **限制资源分配**：注意循环或递归调用中的资源分配。在循环内部打开文件而不进行适当关闭会导致资源泄漏。
5. **大数据使用 NIO**：对于处理大文件或需要可扩展 I/O 操作的应用（如读取、写入或传输大文件），可以考虑使用 Java NIO 包，因为其提供的通道和缓冲区可以更高效地处理这些场景。

应用这些性能技巧将产生更高效、可扩展且易于维护的 Java 应用程序，从而充分利用 I/O 流进行数据的读写。

## Java 并发与多线程

## 11.1 Java 线程基础

### 11.1.1 使用 Thread 类和 Runnable 接口创建线程

Java 线程可以通过两种主要方式创建：扩展 `Thread` 类和实现 `Runnable` 接口。

**扩展 Thread 类**：这种方法涉及创建一个继承 `Thread` 的新类并重写其 `run()` 方法。可以创建该类的实例并使用其 `start()` 方法启动它。

```java
class MyThread extends Thread {
    public void run() {
        // 在新线程中运行的代码
        System.out.println("Thread running: " + Thread.currentThread().getName());
    }
}

public class ThreadExample {
    public static void main(String[] args) {
        Thread myThread = new MyThread();
        myThread.start(); // 启动线程
    }
}
```

**实现 Runnable 接口**：在这种方法中，类实现了 `Runnable` 接口及其 `run()` 方法。然后创建一个 `Thread` 实例，并将实现类的实例传递给其构造函数。

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

### 11.1.2 线程生命周期与状态

Java 中的线程可以处于以下状态之一：

1. **新建 (New)**：线程已创建但尚未启动。
2. **可运行 (Runnable)**：线程可能正在运行，或已准备好运行等待资源分配。
3. **阻塞 (Blocked)**：线程被阻塞，等待监视器锁。
4. **等待 (Waiting)**：线程无限期等待另一个线程执行特定操作。
5. **定时等待 (Timed Waiting)**：线程等待另一个线程执行操作的最长为指定的等待时间。
6. **终止 (Terminated)**：线程已完成执行。

### 11.1.3 线程优先级与守护线程

- **线程优先级**：Java 提供了通过 `setPriority(int priority)` 方法为线程分配优先级（最小：1，最大：10）的机制。高优先级线程的执行优于低优先级线程，尽管由于 JVM 和操作系统的依赖性，这并不是严格的保证。
- **守护线程**：Java 中的守护线程是为用户线程提供服务的提供者线程。它的生命取决于用户线程的仁慈，即当所有非守护（用户）线程结束时，虚拟机将终止任何运行中的守护线程。守护线程通常用作用户线程的服务提供者，并在线程启动前通过 `setDaemon(true)` 方法设置。

### 11.1.4 处理 InterruptedException

当线程处于等待、睡眠或其他被占用状态且线程被中断时，会抛出 `InterruptedException`。正确处理此异常对于在被请求停止时停止线程或清理资源至关重要。

```java
class MyRunnable implements Runnable {
    public void run() {
        try {
            Thread.sleep(1000);
            System.out.println("Thread running e");
        } catch (InterruptedException e) {
            System.out.println("Thread was interrupted");
        }
    }
}
```

在处理中断时，调用 `Thread.currentThread().interrupt()` 来恢复中断状态通常是一种良好的做法。

## 11.2 同步与线程间通信

### 11.2.1 Synchronized 关键字与内建锁

Java 中的同步对于确保只有一个线程可以访问资源至关重要，可以防止竞态条件和数据不一致。`synchronized` 关键字可用于标记方法或代码块，以便同一时间只有一个线程可以执行它。

- **同步方法**：当方法声明为 `synchronized` 时，它会锁定调用方法的对象的监视器。在释放之前，其他线程无法执行该对象上的任何同步方法。

```java
public synchronized void increment() {
    count++;
}
```

- **同步块**：同步块比同步方法更灵活，因为允许在不同的对象上锁定并覆盖方法的部分。

```java
synchronized(this) {
    count++;
}
```

### 11.2.2 volatile 关键字与内存可见性

Java 中的 `volatile` 关键字确保变量的变化可以传播到其他线程。当字段声明为 `volatile` 时，编译器和运行时会注意到该变量是共享的，不应对其进行的更改进行缓存或重排序。

**用例**：当变量的值被不同线程修改，但对变量的操作不依赖于其当前值时（例如停止线程的标记）。

```java
private volatile boolean active;

public void stop() {
    active = false;
}
```

### 11.2.3 Wait, Notify 和 NotifyAll 方法

Object 类中的 `wait()`、`notify()` 和 `notifyAll()` 方法用于线程间通信以及多线程之间的协作。

- `wait()`：使当前线程等待，直到另一个线程对该对象调用 `notify()` 或 `notifyAll()`。
- `notify()`：唤醒等待该对象监视器锁的一个线程。
- `notifyAll()`：唤醒等待该对象监视器锁的所有线程。

这些方法必须在有关调用这些对象的同步上下文中（方法或块）中调用。

```java
synchronized(obj) {
    while (<条件不满足>) obj.wait();
    // 执行符合条件的操作
    obj.notifyAll(); // 或 obj.notify();
}
```

### 11.2.4 ReentrantLock 和 Condition

位于 `java.util.concurrent.locks` 包中的 `ReentrantLock` 类提供了 `synchronized` 方法和块的替代方案，并具有更扩展的功能，如可中断的锁获取、锁轮询、定时锁等待和公平性。



```java
private final ReentrantLock lock = new ReentrantLock();
public void method() {
    lock.lock();
    try {
        // 关键区代码
    } finally {
        lock.unlock();
    }
}
```

- 条件：`ReentrantLock` 提供了创建多个 `Condition` 对象的能力

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
        condition.signal(); // 类似于 Object.notify()
    } finally {
        lock.unlock();
    }
}
```

使用 `ReentrantLock` 和 `Condition` 可以对线程的锁定和唤醒提供更细粒度的控制，适用于需要复杂同步策略的场景。

## 11.3 并发工具类

### 11.3.1 java.util.concurrent 包概述

`java.util.concurrent` 包为构建并发应用程序提供了健壮、高性能的工具类。该包于 Java 5 中引入，并在后续版本中得到了显著增强，包含了一系列同步集合、用于管理线程池的执行器接口、原子操作工具类、同步器等等。它的设计通过抽象许多同步的复杂性，显著地简化了并发应用程序的开发。

### 11.3.2 并发集合 (ConcurrentHashMap, BlockingQueue)

`ConcurrentHashMap`：`HashMap` 的线程安全变体，专为并发设计。它允许并发的读取和更新，而不需要同步。通过分段锁机制，`ConcurrentHashMap` 实现了高吞吐量和可扩展性。

```java
ConcurrentHashMap<String, String> map = new ConcurrentHashMap<>();
map.put("key", "value");
```

`BlockingQueue`：表示队列的接口，它额外支持操作：在获取元素时等待队列非空，在存储元素时等待队列有可用空间。`ArrayBlockingQueue`、`LinkedBlockingQueue`、`PriorityBlockingQueue` 和 `SynchronousQueue` 是著名的实现类。

```java
BlockingQueue<String> queue = new ArrayBlockingQueue<>(1024);
queue.put("item");
String item = queue.take();
```

### 11.3.3 原子变量与 Atomic 包

`java.util.concurrent.atomic` 包的这部分提供了一系列类，支持在单个变量上进行无锁线程安全的编程。原子类（如 `AtomicInteger`、`AtomicLong`、`AtomicBoolean` 和 `AtomicReference`）提供了原子更新更新值的机制。

```java
AtomicInteger atomicInt = new AtomicInteger(0);
int oldValue = atomicInt.getAndIncrement(); // 原子性递增 1
```

这些对于计数器、标志位或可以在不需要同步的情况下安全更新的引用特别有用。

### 11.3.4 SynchronousQueue 和 Phaser

`SynchronousQueue`：一种 `BlockingQueue` 变体，其中每个插入操作都必须等待另一个线程相应的移除操作，反之亦然。同步队列没有内部容量，甚至容量为 1 也没有。它适用于你想将数据从一个线程传递给另一个线程的场景。

```java
BlockingQueue<String> syncQueue = new SynchronousQueue<>();
Thread producer = new Thread(() -> syncQueue.put("hello"));
Thread consumer = new Thread(() -> { String received = syncQueue.take(); });
producer.start();
consumer.start();
```

`Phaser`：一种可重用的同步屏障，功能上类似于 `CyclicBarrier` 和 `CountDownLatch`，但更具灵活性。`Phaser` 可以处理注册到它的动态数量参与者（线程），并支持从一个阶段到另一个阶段。每个阶段编号代表一个 r-

```java
Phaser phasor = new Phaser(1); // '1' 用于注册当前线程
int currentPhase;

currentPhase = phaser.arriveAndAwaitAdvance();
// 在所有线程完成后在此执行操作
```

## 11.4 执行器

### 11.4.1 使用执行器与线程池

`Executor` 接口和 `ExecutorService` 子接口提供了管理线程执行的标准方式，将任务提交与线程管理细节解耦。

### 11.4.2 线程池创建与配置

`Executors` 工厂类提供了创建常用线程池的静态方法，但生产环境推荐直接使用 `ThreadPoolExecutor` 以明确配置参数。

```java
ExecutorService executor = new ThreadPoolExecutor(
    corePoolSize, maximumPoolSize, keepAliveTime, TimeUnit.SECONDS,
    new LinkedBlockingQueue<>(), new ThreadFactoryBuilder().setNameFormat("worker-%d").build(),
    new ThreadPoolExecutor.AbortPolicy()
);
```

核心参数说明：
- `corePoolSize`：核心线程数
- `maximumPoolSize`：最大线程数
- `keepAliveTime`：非核心线程空闲存活时间
- `workQueue`：任务队列（如 `LinkedBlockingQueue`、`SynchronousQueue`）
- `threadFactory`：线程工厂（建议设置有意义的线程名）
- `handler`：拒绝策略（`AbortPolicy`、`CallerRunsPolicy` 等）

### 11.4.3 任务提交与结果获取

```java
// 提交 Runnable，无返回值
executor.execute(() -> System.out.println("Task running"));

// 提交 Callable，返回 Future
Future<Integer> future = executor.submit(() -> {
    Thread.sleep(1000);
    return 42;
});

try {
    Integer result = future.get(); // 阻塞等待结果
} catch (InterruptedException | ExecutionException e) {
    Thread.currentThread().interrupt();
}
```

### 11.4.4 线程池关闭与优雅停机

```java
executor.shutdown(); // 禁用新任务提交，已提交任务继续执行
try {
    if (!executor.awaitTermination(60, TimeUnit.SECONDS)) {
        executor.shutdownNow(); // 取消正在执行的任务，尝试停止线程
        if (!executor.awaitTermination(60, TimeUnit.SECONDS)) {
            System.err.println("Pool did not terminate");
        }
    }
} catch (InterruptedException ex) {
    executor.shutdownNow();
    Thread.currentThread().interrupt();
}
```

### 11.4.5 CompletableFuture 与异步编程

`CompletableFuture` 实现了 `Future` 和 `CompletionStage`，支持异步计算的组合、链式调用和异常处理。

```java
CompletableFuture.supplyAsync(() -> "Hello")
    .thenApply(s -> s + " World")
    .thenAccept(System.out::println)
    .exceptionally(ex -> { ex.printStackTrace(); return null; });
```

### 11.4.6 ForkJoinPool 与分治任务

`ForkJoinPool` 专为“分而治之”递归任务设计，使用工作窃取算法提高吞吐量。

```java
ForkJoinPool pool = new ForkJoinPool();
pool.invoke(new RecursiveTask<Integer>() {
    @Override
    protected Integer compute() {
        // 任务拆分与合并逻辑
        return 0;
    }
});
```



```java
abstract class Animal {
    abstract void makeSound();

    void eat() {
        System.out.println("This animal eats food.");
    }
}
```

## 12.1.3 抽象方法及其影响

抽象方法是抽象类中没有方法体的方法。相反，它们仅仅提供一个方法签名。提供这些方法的实际实现是子类的责任。如果一个类中即使只包含一个抽象方法，该类也必须声明为抽象类（`abstract`）。

类中抽象方法的存在标志着该类旨在作为其他类的蓝图或基类。它强制与子类之间执行了一份契约，确保某些基本方法被实现，从而促进了继承类之间统一的使用和行为。

```java
class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Bark");
    }
}
```

## 12.1.4 抽象类的实际用途

在需要为一组子类定义通用框架的场景下，抽象类特别有用，它们可以在确保功能一致性的同时，允许实现上具有灵活性。一些实际用途包括：

- **模板方法**：抽象类可以定义一个“模板方法”，其中包含一系列执行任务的步骤。子类随后可以定义这些步骤的实际实现。
- **代码复用**：通过声明并可能为常用方法提供默认实现，它们允许重大的代码复用，子类可以直接使用这些方法，或者在需要时对其进行重写。
- **设计与文档**：作为未来开发的蓝图，抽象类有助于记录和强制类层次结构，促进良好的设计实践。

总而言之，抽象类和抽象方法提供了一种结构化的方式来封装相关类之间的共同特征，同时确保了某种程度的抽象，并要求子类实现根据其定制的特定功能。

## 12.2 探索接口

### 12.2.1 接口基础

在 Java 中，接口（`interface`）是一种引用类型，类似于类，但仅包含常量、方法签名、默认方法、静态方法和嵌套类型。接口不能包含实例字段或构造函数。接口中的方法默认是抽象的，这意味着它们没有方法体，并且必须由选择实现接口的类来实现它们。

```java
public interface Animal {
    void eat();
    void sleep();
}
```

接口通过在类中使用 `implements` 关键字来实现。实现接口的类必须为该接口中声明的所有抽象方法提供具体的实现。

### 12.2.2 实现多个接口

Java 支持通过接口实现类型的多重继承。这意味着一个类可以实现多个接口，从而从多个源头继承抽象方法。

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

在 Java 8 中引入的默认方法（`default methods`）允许你向已经有实现者的接口中添加新方法，而不会破坏它们的代码。默认方法有方法体且不是抽象的，这与接口中定义的其他方法不同。

```java
public interface Animal {
    void eat();

    default void breathe() {
        System.out.println("Breathing");
    }
}
```

默认方法的引入主要是为了增强 Java 8 中的 Collections API，允许在不影响现有代码的情况下添加新方法。

### 12.2.4 函数式接口与 Lambda 表达式

Java 中的函数式接口（`functional interface`）是一个恰好包含一个抽象方法的接口。它可以有多个方法，但所有其他方法必须有默认实现或是静态的。这些接口的设计初衷主要是为了配合 Lambda 表达式使用，表达式提供了一种清晰的方式。

```java
@FunctionalInterface
interface Greeting {
    void sayHello(String message);
}

public class Demo {
    public static void main(String[] args) {
        Greeting greeting = message -> System.out.println("Hello, " + message);
        greeting.sayHello("World");
    }
}
```

## 12.3 深入理解内部类

### 12.3.1 内部类概览

在 Java 中，内部类是定义在另一个类中的类。内部类根据其用途分为几种类型：成员内部类、局部内部类、匿名内部类和静态嵌套类。它们可以访问外部类的成员，提供了强大的组织机制。

### 12.3.2 成员内部类

成员内部类是非静态的类，定义在类的层级。它需要外部类的实例来实例化。它可以访问外部类的成员。

```java
class OuterClass {
    private String message = "Hello World";

    class InnerClass {
        void display() {
            System.out.println(message);
        }
    }
}
```

### 12.3.3 局部内部类

局部内部类定义在块（通常是方法）内部，并且仅对该块可见。类似于局部变量，局部内部类的作用域局限于该块。

### 12.3.4 匿名内部类

匿名内部类是没有命名的，通常用于即时实例化接口或抽象类，而无需正式声明子类。它们通常只需要使用一次。

```java
Runnable runnable = new Runnable() {
    @Override
    public void run() {
        System.out.println("匿名内部类");
    }
};
```

### 12.3.5 静态嵌套类

与其他内部类不同，静态嵌套类不需要外部类的实例即可创建。它们无法直接访问外部类的非静态成员。它们通常用于将类与另一个类关联，且在静态文中文中。

## 12.4 理解 static 和 final

### 12.4.1 static 关键字：变量和方法

`static` 关键字用于指示特定成员（变量或方法）属于类，而不是类的实例。这意味着该成员只有一个副本，并供所有实例共享。

- **静态变量**：也称为类变量，在类中声明并使用 `static` 关键字。它们在类加载时初始化。
- **静态方法**：可以在创建类实例的情况下调用。静态方法无法直接访问实例变量或方法。

### 12.4.2 final 关键字：不可变状态

`final` 关键字用于声明常量、防止继承以及防止方法被重写。当它应用于变量时，它使其在初始化后变得不可更改。

### 12.4.3 初始化器

非静态初始化块用于初始化实例变量。每当创建类的实例时，这些块就会被执行。

```java
class MyClass {
    // code to be executed when an instance is created
}
```

### 12.4.4 Final 类与方法

- **Final 类**：声明为 `final` 的类不能被子类化。这在创建像字符串类这样的不可变类时特别有用。
- **Final 方法**：声明为 `final` 的方法不能被子类重写。这用于防止无意中重写可能会改变类之关键行为的方法。

```java
final class MyFinalClass {
    // Class body
}

class MyClass {
    final void myFinalMethod() {
        // method body
    }
}
```

正确使用 `static` 和 `final` 关键字可以显著增强 Java 应用的设计和性能，通过提高不可变性、减少开销以及保护关键功能免受修改来实现。

## 关于作者

Programming Hub 是一个先驱平台，它改变了数百万学习者接触编程和计算机科学的方式。凭借让编程对所有人手可及的使命，Programming Hub 已经取得了重要的里程碑，赋予了不同背景的人们探索编程世界的能力。

Programming Hub 应用下载超过 500 万次，在 Play Store 和 App Store 上凭借超过 18 万条评论获得 4.7 高分，被认为是最好的应用程序之一。它是一个全面的学习伴侣，涵盖了广泛的编程语言和主题。从 Python、Java 到 C++ 和 HTML，该应用提供了互动式课程、编程挑战和测验，帮助你磨练技能。其直观的界面和游戏化的学习方法让掌握编程语言变得有趣且易于学习。Programming Hub 曾获得过众多奖项，包括被评为 2017 年 Google 编辑器优选（Google editor’s choice）、2017 年 Google 最佳应用、Google LaunchPad 加速器计划，并在 Product Hunt 上登榜，获得了 Facebook 的 FB Start 支持。

Programming Hub 为用户提供 45 多个应用程序，赢得了全球学习者的赞誉。用户赞扬该应用界面友好、引人入胜的内容以及有效的教学方法。所有年龄和技能水平的学习者都发现 Programming Hub 是他们编程之旅上可靠的伙伴，点燃了他们对编程的热情并释放了他们的潜力。

Programming Hub 用户经常使用的其他应用还有：

1. Python
2. 数字营销 (Digital marketing)
3. Java
4. 黑客技术 (Hacking)
5. 人工智能 (Artificial Intelligence)
6. C++ 编程
7. C 语言

更多

各位魔法师，旅程就此结束，但请记住，这只是开始！请保持关注，并期待这一启发性系列的下一卷，我们将深入探索迷人的编程世界，继续我们的精通之路。冒险远未结束！
