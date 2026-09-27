
# Java 核心：从初学者到开发者 (2024)

## 如何联系我们？

请将关于本书的意见和问题邮寄至以下地址：

Rightsol Private Limited

Platinum Palm Woods, Sector- 38, Nerul Office No. 5 and 6, Plot No. 15 B

Navi Mumbai, Maharashtra, 400706 India

可以通过以下平台与我们联系：

- Facebook: https://www.facebook.com/programminghub/
- LinkedIn: www.linkedin.com/company/pro-programming-hub
- Twitter: twitter.com/prghub?lang=en
- Instagram: https://www.instagram.com/programminghub_app_official/

如需对本书进行评论或提出技术问题，请发送邮件至：Hello@programminghub.io

有关更多关于我们产品和课程的信息，请访问我们的网站：https://programminghub.io/

## 前言

欢迎来到结构化且稳健的 Java 编程世界！《Java 基础》旨在为开启计算机科学与工程领域冒险的学生们提供一盏明亮的灯塔。本书特别针对处于学习初期的读者，旨在为 Java 编程打下坚实的基础，Java 语言以其可靠性、效率以及跨平台的广泛适用性而闻名。

Java 是现代软件开发领域的支柱之一，其在构建企业级应用、Android 应用和 Web 应用中的作用进一步凸显了它的重要性。

## 欢迎来到 Java

### 1.1 探索 Java：特性与架构

#### 1.1.1 Java 简介：一种强大的编程语言

Java 是一种多功能且强大的编程语言。自 1995 年由 Sun Microsystems 公司（现隶属于 Oracle 公司）创立以来，它在软件开发领域一直占据重要地位。Java 设计遵循“编写一次，到处运行”（Write Once, Run Anywhere, WORA）的原则，允许开发者编写可以在任何支持 Java 的设备上运行的代码，而无需重新编译。它的广泛应用证明了其健壮性、可移植性和易用设计。

#### 1.1.2 Java 的核心特性：简单、面向对象和安全

Java 的设计原则旨在使其成为一种简单、安全且可靠的编程语言。它的基础特性之一是“面向对象”，这种设计关注数据（对象）以及操作这些对象的方法，促进了更整洁、模块化的编码方法。安全是另一个基石，内置的机制可以最大限度地减少病毒攻击以及对数据和系统的未经授权访问。简化的语法和缺乏低级编程功能使得 Java 对初学者易上手，同时对经验丰富的开发者来说依然强大。

#### 1.1.3 理解 Java 架构：JVM、JRE 和 JDK

Java 的架构充分说明了它在不同平台之间的可移植性和效率。它由以下部分组成：

- `JVM`（Java 虚拟机）：执行 Java 字节码的运行时引擎，确保了 WORA 原则的实现。它从 Java 中抽象出底层的操作系统和硬件。
- `JRE`（Java 运行环境）：包含 `JVM` 以及运行 Java 程序所需的核心类库和组件。它不包含编译器或调试器等开发工具。
- `JDK`（Java 开发工具包）：用于 Java 开发的完整套件，包含 `JRE` 和开发工具。

#### 1.1.4 “编写一次，到处运行”(WORA) 哲学

WORA 哲学是 Java 认同的核心，强调了在任何配备 `JVM` 的设备上运行 Java 编写软件的能力。这种跨平台的兼容性是一个巨大的优势，让开发者不受特定平台编码的限制，并实现了更高效的开发和部署流程。

### 1.2 编写你的第一个 Java 程序

#### 1.2.1 准备工作：搭建你的开发环境

在开始编码之前，准备开发环境至关重要。这个过程涉及安装 `JDK` 以及你选择的集成开发环境（IDE），例如 IntelliJ IDEA、Eclipse 或 NetBeans。通过检查命令行版本或使用 `java -version` 命令确保 Java 已正确安装在系统上。设置包括配置环境变量（如 `PATH`），以便从命令行轻松运行 Java 程序。

#### 1.2.2 Hello, World!：理解 Java 结构

任何旅程都始于足下，在 Java 中，这一步就是“Hello, World!”程序。一个简单的 Java "Hello, World!" 程序展示了基本的 Java 语法和结构，包括公共类（`public class`）声明、`main` 方法声明以及用于向控制台输出的 `System.out.println` 语句。这个程序不仅是学习新编程语言的传统，更是对 Java 程序语法和功能的入门介绍。

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

#### 1.2.3 编译并运行你的第一个程序

Java 程序是用纯文本编写的，因此可以使用任何文本编辑器来编写代码。要让你的 Java 程序变成可以运行的内容，你首先需要使用 Java 编译器（`javac`）将其编译为字节码。这个过程会将你的 `.java` 文件转换为 Java 虚拟机（`JVM`）可以执行的 `.class` 文件。在命令行中编译和运行你的程序的基本命令为：

```bash
javac HelloWorld.java
java HelloWorld
```

第一条命令将 `HelloWorld.java` 源文件编译为 `HelloWorld.class` 字节码文件。第二个命令在 `JVM` 上运行编译后的字节码。

#### 1.2.4 常见错误与排除

在刚开始时，遇到错误是很典型的。最常见的类型包括：

- 语法错误：缺少分号、括号不匹配或关键词拼写错误。
- 运行时错误：在程序执行期间发生的错误，通常由于逻辑错误引起（例如除以零）。
- 编译错误：编译过程中出现的问题。

### 1.3 探索 Java 开发工具包 (JDK)

#### 1.3.1 什么是 JDK？全面概述

Java 开发工具包（`JDK`）是一个用于开发 Java 应用程序的全功能软件套件。它包含了 Java 运行环境（`JRE`）以及编码、调试和运行程序所需的工具。

#### 1.3.2 安装 JDK：分步指南

1. 下载 JDK：访问官方网站或 OpenJDK 变体，选择适合你操作系统的版本。
2. 运行安装程序：执行下载的文件并按照屏幕说明操作，同意许可协议。
3. 设置环境变量：为了在命令行中使用 JDK，你需要设置 `PATH` 环境变量以包含 JDK 的 `bin` 目录。在 Windows 上，你可能还需要设置 `JAVA_HOME` 变量指向 JDK 目录。
4. 验证安装：打开命令提示符或终端并输入 `java -version` 和 `javac -version`。如果 JDK 安装得正确，你应该能分别看到 Java 和 `javac` 的版本号。

#### 1.3.3 JDK 的核心组件

JDK 不仅仅是一个编译器；它包含了几个对 Java 开发至关重要的关键组件：

- `javac`：Java 编译器，将源代码转换为字节码。
- `java`：Java 启动工具，在 `JVM` 上执行你的 Java 程序。
- `jar`：Java 归档工具，将多个文件合并为一个 JAR（Java 归档）文件。
- `javadoc`：文档生成器，根据 Java 源码注释生成 HTML 格式的文档。
- `debugger`：用于调试 Java 程序的工具，包括命令行工具和 IDE 集成。

#### 1.3.4 导航 JDK 文档

JDK 文档是开发者非常宝贵的资源。它涵盖了 Java 的各个方面，从平台的全面概述到 Java 海量 API（应用程序接口）的详细描述。以下是导航 JDK 文档的一些小技巧：

- 从概览开始：文档概览页提供了内容摘要，可以帮助你找到所需信息。
- API 文档：熟悉 API 文档的结构。它按包、类和接口组织，并对每个方法和字段都有详细说明。
- 教程和指南：除了参考材料外，JDK 文档还包含复杂主题或特定功能的教程、指南和文章。
- 示例代码：留意文档中的示例代码段，它们有助于澄清各种类和方法的用法。

`JVM`（Java 虚拟机）：执行 Java 字节码的关键部分。

### 1.4 Java 的演变：版本与发行

#### 1.4.1 Java 的历史历程

Java 自诞生以来已经走了很长的道路。它最初由 James Gosling 在 1991 年于 Sun Microsystems 公司构思为一个名为“Oak”的项目，设计初衷是用于机顶盒和电视机等数字设备。然而，互联网的兴起为 Java 的繁荣提供了完美的环境。Sun Microsystems 于 1995 年正式发布了 Java 1.0，其“编写一次，到处运行”（Write Once, Run Anywhere）的承诺吸引了全球开发者的想象。多年来，Java 经历了重大的演变，每个版本都不断添加新功能并改进。

#### 1.4.2 Java SE vs Java EE vs Java ME 的区别

Java 技术分为几个版本，针对不同的应用环境和需求：

- `Java SE`（标准版）：Java 编程的基础，提供了核心功能，包括用于 UI、数据库访问、安全等基础 API。
- `Java EE`（企业版）：基于 `Java SE` 之上，增加了用于开发大规模、多层、可扩展且安全网络应用程序的企业级 API。
- `Java ME`（微型版）：针对移动和嵌入式设备进行了优化，提供了健壮且灵活的 Java 环境。

#### 1.4.3 从 Java 到最新版本的亮点与特性

Java 的演变以每个版本的重大新增和改进为标志。以下是一些亮点：

- **Java 1.0 (1996)**：起点，引入了带有垃圾回收等特性的 Java 语言。
- **Java 5 (2004)**：引入了重大增强，包括泛型（generics）、注解、自动装箱/拆箱（autoboxing/unboxing）以及并发工具。
- **Java 8 (2014)**：里程碑式的发布，引入了 Lambda 表达式、Stream API 以及日期/时间 API。
- **Java 11 (2018)**：第一个长期支持（LTS）版本，带来了新特性如本地变量语法、`HTTP Client API` 以及更多。
- **Java 17 (2021)**：最新的 LTS 版本，引入了密封类（sealed classes）、模式匹配（pattern matching）以及废弃了 Applet API。

#### 1.4.4 如何关注 Java 动态

通过以下渠道获取 Java 动态信息：

- **Java 官方博客和邮件列表**：订阅以接收新闻和更新。
- **Java 社区进程 (JCP)**：参与 JCP 以查看未来的方向和提案。
- **开发者大会**：参加 Oracle One 或本地 Java 用户组会议。
- **关注专家和影响者**：社交媒体平台和 Java 意见领袖是见解的好来源。

## 设置你的 Java 环境

### 2.1 配置环境变量

#### 2.1.1 Java 环境变量简介

计算中的环境变量是影响计算机运行进程行为的动态值。它们可以指定系统文件的位置或软件设置。对于 Java 开发，设置环境变量至关重要，因为它们指导哪里寻找 Java 编译器（`javac`）和 Java 运行时（`java`）。这允许开发者从任何目录运行 Java 命令，而无需指定 Java 可执行文件的完整路径。

#### 2.1.2 设置 JAVA_HOME 和更新 PATH

**设置 JAVA_HOME**：`JAVA_HOME` 环境变量指向 JDK 的安装目录。应用程序使用此变量来查找 Java 库。

- **Windows**：
  1. 右键点击“此电脑”并选择“属性”。
  2. 导航到“高级系统设置” > “环境变量”。
  3. 点击“新建”创建一个新的环境变量。命名为 `JAVA_HOME` 并将其值设置为 JDK 安装路径（例如：`C:\Program Files\Java\jdk-17`）。

- **macOS/Linux**：
  1. 打开终端。
  2. 编辑你的 shell 配置文件（`.bash_profile`, `.bashrc`, `.zshrc` 等）。例如，你可以用 `nano ~/.bashrc` 打开它。
  3. 添加此行：`export JAVA_HOME=$(/usr/libexec/java_home)`。
  4. 保存更改并关闭编辑器。

**更新 PATH**：为了从命令行方便运行 Java 可执行文件，将 JDK 的 `bin` 目录添加到系统的 `PATH` 中。

- **Windows**：按照上述步骤进入“环境变量”，找到 `PATH` 变量并选择“编辑”。追加 JDK 的 `bin` 目录路径（例如：`C:\Program Files\Java\jdk-17\bin`）。
- **macOS/Linux**：像之前一样打开 shell 配置文件，并添加行：`export PATH=$PATH:$JAVA_HOME/bin`。

#### 2.1.3 在 Windows、macOS 和 Linux 中验证配置

设置 `JAVA_HOME` 并更新 `PATH` 后，验证配置情况：

- 打开一个新的终端或命令提示符（更改可能不会应用于已打开的终端）。
- 输入 `java -version` 和 `javac -version`。如果安装成功，你应该能看到每个命令对应的已安装 Java 版本。

**Windows**：
- 如果配置错误，`java` 或 `javac` 命令可能无法识别。请双检查系统设置中的环境变量。

**macOS/Linux**：
- 确保你已将更改保存到配置文件，并通过 `source ~/.bashrc` 刷新文件或重新打开终端。如果命令无法识别，请检查环境变量中设置的路径。

正确配置这些环境变量可以简化 Java 开发，使其能够通过命令行从任何目录编译和运行 Java 应用程序。

### 2.2 将构建工具集成到你的 IDE

#### 2.2.1 构建工具概览：Maven 和 Gradle

Maven 和 Gradle 是 Java 开发中最常用的两种构建自动化工具。它们帮助进行项目创建、依赖管理和构建生命周期管理。

- **Maven**：以使用基于 XML 的 `pom.xml`（项目对象模型）文件闻名。它遵循“约定优于配置”的方法，简化了项目设置，但在复杂配置上灵活性较低。
- **Gradle**：另一方面，它使用基于 Groovy 的配置脚本（`build.gradle` 文件），提供了更高的可扩展性和灵活性。Gradle 的性能常被视为其优势，在许多情况下比 Maven 更快。两种工具都与 Eclipse 和 IntelliJ IDEA 等主流 IDE 集成。

#### 2.2.2 在 Eclipse 和 IntelliJ 中设置 Maven

**在 Eclipse 中**：
1. Eclipse 的最新版本都集成了 Maven。要创建一个新的 Maven 项目，前往 `File > New > Other... > Maven > Maven Project`。
2. 按照向导指定 Group ID、Artifact ID 和架构。

**在 IntelliJ IDEA 中**：
1. 打开 IntelliJ IDEA，导航到 `File > New > Project`。
2. 在左侧选择 Maven。IntelliJ IDEA 会提示你指定项目的 SDK（软件开发工具包）以及其他 Maven 参数。

两个 IDE 会根据 `pom.xml` 文件自动处理依赖解析，无需手动下载和配置库。

#### 2.2.3 在你的 Java 项目中配置 Gradle

不同 IDE 配置 Gradle 的差异不大，因为 Eclipse 和 IntelliJ IDEA 对 Gradle 都提供了良好的支持。

**在 Eclipse 中**：
1. 如果你的 Eclipse 版本未包含，你需要安装 Buildship Gradle Integration 插件。可以通过 Eclipse Marketplace 进行。
2. 要创建一个新的 Gradle 项目，前往 `File > New > Other... > Gradle > Gradle Project` 并按照向导操作。

**在 IntelliJ IDEA 中**：
1. IntelliJ IDEA 内置了 Gradle 支持。要启动一个新的 Gradle 项目，只需导航到 `File > New > Project`，然后从左侧栏选择 Gradle。

对于 Maven 和 Gradle 来说，在设置好项目后，IDE 都会根据构建配置（`pom.xml` 或 `build.gradle`）显示项目结构，允许你通过 IDE 的用户界面运行、调试和管理依赖。

将 Maven 或 Gradle 集成到你的开发环境中可以显著增强项目管理、依赖解析和构建自动化，并无缝集成到 Java 开发者使用的 IDE 中。

### 2.3 版本控制系统：Git 与 Java

#### 2.3.1 Java 开发者 Git 简介

对于 Java 开发者来说，理解和利用版本控制系统（VCS）是必不可少的，而 Git 是当今开发领域应用最广泛的 VCS。Git 帮助管理代码更改、与其他开发者协作，并维护项目演进的历史记录。从简单的代码存储到复杂的协作开发项目，它的作用都至关重要。

Git 基于“快照”原理运行，每个提交（commit）都代表项目在特定时间点的快照。这种模型允许强大的分支和合并操作，能够在互不干扰的情况下实现并行开发流。

#### 2.3.2 使用 Git 克隆你的第一个 Java 项目

克隆（Cloning）是创建 Git 仓库本地副本的过程。要克隆你的第一个 Java 项目：

1. 找到仓库：找到你想要克隆的 Git 仓库 URL。这可能位于 GitHub、GitLab、Bitbucket 或任何 Git 服务器上。



- 2. 打开终端或命令提示符：切换目录（`cd`）到你想要克隆仓库的路径。
- 3. 克隆仓库：使用 `git clone` 命令并后跟仓库的 URL。

例如：

- 4. 复制代码

```
git clone https://github.com/example/project.git
```

- 5. 该命令将项目下载到与项目名称同名的本地文件夹中。
- 6. 使用 IDE 打开：使用你喜爱的 IDE（例如 Eclipse 或 IntelliJ IDEA）将克隆的目录作为既有项目打开。大多数 IDE 会自动识别 Git 仓库并启用 VCS 支持。

### 2.3.3 在 Java 项目中提交和推送更改

在对 Java 项目进行更改后，你可能希望将这些更改保存到 Git 仓库中。

提交（Committing）和推送（Pushing）是实现此点的两个主要操作。

#### 提交更改（Committing Changes）

- 1. 审核更改：使用 `git status` 可以查看哪些文件已更改。要详细查看特定更改，使用 `git diff`。
- 2. 暂存文件准备提交：在提交之前，你需要使用 `git add` 暂存更改。可以使用 `git add .` 暂存所有更改的文件，或使用 `git add filename` 暂存单个文件。
- 3. 提交：使用 `git commit -m "Your commit message"` 提交暂存的更改。提交信息应该是更改的简短描述。

#### 推送更改（Pushing Changes）

- 1. 如果你在克隆的仓库上工作，它连接到了远程仓库。使用 `git push` 将提交的更改推送到远程仓库。
- 2. 第一次推送时，你可能需要使用 `git push --upstream origin branch_name` 设置上游分支，将 `branch_name` 替换为当前分支。

通过掌握 Git 中克隆、提交和推送的基础知识，Java 开发者可以有效地管理和协作软件项目，确保更改能够被安全地存储并在团队成员之间共享。

## 2.4 调试 Java

### 2.4.1 Java 调试基础

调试是开发过程中的关键阶段，允许开发者诊断并修复其 Java 程序中的错误。它涉及识别 bug 的来源、理解它们发生的原因以及确定纠正它们的最佳方法。有效的调试可以节省时间和精力，确保应用程序运行良好且符合预期。

Java 提供了一系列调试工具和 IDE 功能，例如堆栈跟踪分析、断点、单步执行和变量检查，以促进这一过程。理解这些工具以及如何利用它们可以显著提高开发者快速诊断和解决问题的能力。

### 2.4.2 设置断点和检查变量

**设置断点（Setting Breakpoints）**：断点会在代码的特定行临时暂停程序的执行。这允许你检查程序在那一刻的状态，这对于诊断问题非常有价值。在大多数 Java IDE 中设置断点：

- 1. 打开你想要暂停执行的源代码。
- 2. 点击行号左侧的边缘区域或直接点击代码行。标记或高亮显示的行表示已设置断点。
- 3. 以调试模式运行你的程序（通常通过点击“小虫虫”图标或从运行菜单中选择“Debug”）。执行将在断点处暂停。

**检查变量（Inspecting Variables）**：在断点处暂停时，你可以检查变量的当前值：

- 1. 大多数 IDE 会在调试窗口中显示变量列表及其值。
- 2. 你通常可以在代码编辑器中悬停在变量上以弹出其值。
- 3. 一些 IDE 允许你在调试期间修改变量的值，以测试更改如何影响程序执行。

### 2.4.3 常见调试场景和解决方案

**场景 1：空指针异常（Null Pointer Exception）**

- 问题：尝试使用具有 null 值的对象引用。
- 解决方案：使用 IDE 调试工具识别 null 值的来源，并确保对象引用在使用前已初始化。

**场景 2：数组下标越界（Array Index Out of Bounds）**

- 问题：尝试使用超过数组大小的索引访问数组元素。
- 解决方案：在访问元素之前使用 `.length` 属性检查数组长度。使用断点。

**场景 3：死循环（Infinite Loops）**

- 问题：永不终止的循环。
- 解决方案：使用断点检查循环条件。

**场景 4：并发问题（Concurrency Issues）**

- 问题：源自多线程的问题。
- 解决方案：使用同步块或锁来管理共享资源。

调试既是艺术也是门科学。通过熟悉调试工具和常见场景，你可以使 Java 开发更加高效。

# Java 编程基础

## 3.1 理解变量和数据类型

### 3.1.1 什么是变量？

**变量简介**：变量是在执行过程中存储数据的基本容器。它们之所以被称为变量，是因为其中的数据在执行过程中可以改变（变化）。在 Java 中，每个变量都有特定的类型，决定了大小、可以存储的值范围以及可以的操作。

**变量命名规范**：Java 对变量命名遵循某些约定和规则：

- 变量名应以小写字母开头并遵循驼峰命名法（`camelCase`）。
- 它可以包含字母、数字、下划线和美元符号，但不能以数字开头。
- 选择反映变量用途的有意义命名是重要的。
- Java 关键字不能作为变量名。

### 3.1.2 原生数据类型

**原生类型概述**：原生数据类型由语言预定义并用关键字命名。它们代表了基本数据类型。

**数值数据类型**：`int`、`short`、`long`、`byte`

- `byte`：非常小的整数，范围从 -128 到 127。适用于在大数组中节省内存。
- `short`：小型整数，范围从 -32,768 到 32,767。
- `int`：默认整数类型，范围从 -2^31 到 2^31-1。
- `long`：大型整数，范围从 -2^63 到 2^63-1，当 `int` 不够大时使用。

**浮点类型**：`float`、`double`

- `float`：单精度 32 位浮点。它不应被用于精确值，例如货币。
- `double`：双精度 64 位 IEEE 754 浮点。它通常是小数值的默认选择。

**布尔类型和字符类型**

- `boolean`：该类型代表 1 位信息，但其“大小”并不是一个精确定义的值。值为 `true` 或 `false`。
- `char`：单个 16 位 Unicode 字符。它的最小值为 `'\u0000'`（或 0），最大值为 `'\uffff'`（或 65535，包含在内）。

### 3.1.3 引用数据类型

**理解引用变量**：引用变量用于引用对象。与存储实际值的原始数据类型不同，引用变量存储的是实际数据的内存地址或引用。

**字符串与数组**

- **字符串（Strings）**：`String` 类不是原始数据类型，而是一种可以存储字符序列的引用类型。
- **数组（Arrays）**：数组是存储相同类型多个项的引用类型。原始类型和对象都可以存储在数组中。

### 3.1.4 类型转换与强制转换

**隐式转换与显式转换**

- **隐式转换（宽转换）**：当源类型的大小小于目标类型时，发生这种情况。例如，Java 会隐式地将一个 `int` 赋值给 `long`。
- **显式转换（窄转换）**：当你将尺寸较大的类型赋值给较小的类型时（例如将 `double` 转换为 `int`），就需要这样做。这需要使用强制转换运算符。

数据类型之间的转换在执行涉及不同类型值的操作时，可能需要数据类型之间的转换。在转换时，请注意潜在的数据丢失风险（窄转换），并确保转换是必要且刻意的，以维护数据的准确性和完整性。

## 3.2 深入研究运算符与表达式

### 3.2.1 算术运算符

**基本操作：加法、减法等**：Java 提供了几种算术运算符来执行常见的数学运算：

- `+`（加法）：合并两个值。
- `-`（减法）：从另一个值中减去一个值。
- `*`（乘法）：两个值相乘。
- `/`（除法）：一个值除以另一个。如果两个操作数都是整数，结果也将是整数，舍弃任何余数。
- `%`（模运算符）：返回除法运算的余数。

**模运算符**：由 `%` 表示的模运算符对于寻找余数、判断数字是偶数还是奇数（通过模 2）以及在特定阈值处循环值特别有用。

### 3.2.2 关系运算符与逻辑运算符

**比较值：关系运算符**：关系运算符比较两个值并确定它们之间的关系。主要的关系运算符有：

- `==`（等于）
- `!=`（不等于）
- `>`（大于）
- `<`（小于）
- `>=`（大于等于）
- `<=`（小于等于）

这些运算符返回布尔结果（`true` 或 `false`）。

**组合条件：与、或、非**：逻辑运算符用于构建更复杂的条件表达式：

- `&&`（逻辑与）：只有当两个操作数都为 `true` 时才返回 `true`。
- `||`（逻辑或）：只要至少有一个操作数为 `true`，就返回 `true`。
- `!`（逻辑非）：反转布尔值，将 `true` 变为 `false`，反之亦然。

### 3.2.3 赋值运算符

**简单赋值**：简单赋值运算符 `=` 用于将其右侧的值赋值给左侧的操作数。

**复合赋值运算符**：复合赋值运算符一步到位完成操作和赋值。示例包括 `+=`、`-=`、`*=`、`/=` 和 `%=`。例如，`x += y` 等同于 `x = x + y`。

### 3.2.4 一元运算符、三元运算符与运算符优先级

**自增与自减**：自增（`++`）和自减（`--`）分别增加或减少变量的值。它们作为前缀和后缀形式使用，这会影响操作在表达式中执行的时机。

**使用三元运算符进行条件赋值**：三元运算符 `? :` 为 `if-else` 语句提供了快捷方式，用于条件赋值。语法为 `condition ? valueTrue : valueFalse`。

**理解运算符优先级与结合性**：运算符优先级决定了表达式中项的组合。这影响表达式的评估方式。某些运算符的优先级高于其他运算符；例如，乘法的优先级高于加法和减法。结合性定义了执行方向是从左到右还是从右到左，当表达式中出现具有相同优先级的运算符的多个操作时，这一点至关重要。

## 3.3 用于决策的条件语句

### 3.3.1 if 语句

**基本 if 结构**：`if` 语句是 Java 中最基本的控制流语句之一。它允许程序根据条件的真假执行不同的操作。其基本语法如下：

```
if (condition) {
  // 如果条件为真，则执行代码块
}
```

**if-else 和 if-else-if 阶梯**：对于需要在条件为真时执行一个操作、为假时执行另一个操作的情况，使用了 `if-else` 结构：

```
if (condition) {
  // 如果条件为真，则执行代码块
} else {
  // 如果条件为假，则执行代码块
}
```

对于多个条件，`if-else-if` 阶梯非常有用：

### 3.3.2 switch 语句

**语法与用例**：`switch` 语句提供了一种简单的方法，根据表达式的值将执行分发到代码的不同部分。与顺序评估条件的 `if-else-if` 阶梯不同，`switch` 语句根据匹配执行一个 case：

```
switch(expression) {
  case value1:
    // 当表达式匹配 value1 时执行代码块
    break;
  case value2:
    // 当表达式匹配 value2 时执行代码块
    break;
  default:
    // 如果没有匹配项，执行默认代码
}
```

`switch` 语句可以处理 `byte`、`short`、`char` 和 `int` 原始类型。

**Java 新的 switch 表达式**：Java 引入了增强的 switch 表达式，简化了 switch 语句的使用，消除了对 `break` 语句的需求，并允许直接从 switch 表达式返回结果。

### 3.3.3 实践中的条件逻辑

**组合条件**：逻辑运算符 `&&`、`||`、`!` 允许在 `if` 语句中组合多个条件，创建特定的路径：

```
if (condition1 && condition2) {
  // 如果 condition1 和 condition2 都为真
}
```

**嵌套条件语句**：条件语句可以相互嵌套以进一步细化决策路径。这涉及到在另一个 `if` 或 `switch` 语句内部放入一个：

```
if (condition1) {
    // 如果 condition1 为真
    if (condition2) {
        // 如果 condition1 和 condition2 都为真
    }
}
```

合理使用条件语句使开发者能够编写灵活且可扩展的 Java 程序，根据各种条件做出决策。

## 3.4 循环机制：for、while 和 do-while 循环

### 3.4.1 for 循环

Java 中的 `for` 循环用于固定次数地执行代码块。基础 `for` 循环的语法如下：

```
for(初始化; 条件; 更新) {
    // 执行的代码块
}
```

- **初始化**：通常用于初始化计数变量。
- **条件**：只要该条件为真，循环就会继续。
- **更新**：在每次迭代后执行；通常用于更新计数变量。

**用于数组和集合的增强 for-each 循环**：Java 5 引入了增强 `for` 循环，使得遍历数组和集合中的元素变得简单：

```
for(dataType item : arrayOrCollection) {
    // 对每个 item 执行的代码
}
```

这种形式消除了维护索引或直接使用迭代器的需要。

### 3.4.2 while 循环

当循环开始前不知道迭代次数时，应使用 `while` 循环。只要指定的条件为 `true`，循环就会继续。

```
while(condition) {
    // 执行的代码块
}
```

**无限循环与循环控制**：无限循环发生在循环条件永远不变为假的情况下。它有时会被刻意地配合 `break` 语句使用，根据循环体内部的条件来退出循环。

### 3.4.3 do-while 循环

**与 while 循环的区别**：`do-while` 循环与 `while` 循环相似，主要区别在于 `do-while` 循环保证至少执行一次。这是因为条件是在执行循环体之后才进行检查的。

```
do {
  // 要执行的代码块
} while(condition);
```

**实际用法示例**：当循环体在评估条件之前需要至少执行一次时，`do-while` 循环非常有用，例如在用户输入循环中显示菜单时。

### 3.4.4 循环控制语句

**循环中的 break 和 continue**

- `break` 语句用于立即退出循环，跳过所有剩余迭代。
- `continue` 语句跳过当前迭代，并继续循环的下一次迭代。

**嵌套循环**：嵌套循环是指循环内部的循环。它们通常用于遍历多维数组等任务。`break` 和 `continue` 等循环控制语句可以应用于嵌套循环中，影响内层和外层循环的流程。准确地控制和理解循环对于创建有效处理重复任务的高效 Java 程序至关重要。

# 第 4 章：深入探索：数组与字符串

## 4.1 数组操作

### 4.1.1 数组简介：定义与声明

数组是一个存储固定数量单类型值的容器对象。数组的长度在创建时确定，且不能更改。Java 中的数组是基于零索引的，这意味着数组的初始元素通过索引 0 访问。

在 Java 中声明数组，你需要指定它将包含的元素类型，后面跟着方括号，然后是数组名称：

```
int[] myArray;
String[] myString;
```

你也可以将括号放在数组名称之后：

```
int myArray[];
String myString[];
```

然而，为了一致性，前一种声明更常用且推荐。

### 4.1.2 初始化和访问数组元素

要为数组分配内存并对其初始化，使用 `new` 关键字，后跟数组元素的类型及其大小：

```
myArray = new int[10]; // 初始化一个可以容纳十个整数的数组
```

数组也可以在声明时通过在大括号 `{}` 中包含值来初始化：

访问数组元素是直观的；你使用数组名称，后跟方括号中的元素索引：

```
int firstElement = myArray[0]; // 访问第一个元素
myArray[4] = 20; // 修改第五个元素的值
```

### 4.1.3 遍历数组

要对数组的每个元素执行操作，可以使用循环遍历数组。`for` 循环常用于此目的：

```
for(int i = 0; i < myIntVar.length; i++) {
    System.out.println(myIntVar[i]); // 打印数组中的每个元素
}
```

Java 还提供了增强型 for 循环（也称为 "for-each" 循环）来遍历数组，这使得代码更简洁、更易读：

```
for(int element : myIntVar) {
    System.out.println(element); // 打印数组中的每个元素
}
```

### 4.1.4 多维数组：概念与用法

多维数组是数组的数组，主数组的每个元素持有另一个数组。最常见的形式是二维数组，或矩阵。二维数组通过指定两组方括号来声明、分配和访问：

```
int[][] myMatrix = new int[3][4]; // 一个 3x4（行 x 列）的数组
```

使用值初始化二维数组：

访问元素需要指定每个维度的索引：

```
int firstRowThirdColumn = myMatrix[0][2];
```

遍历多维数组通常涉及嵌套循环：

有效理解和使用数组是 Java 编程的基础，它有助于高效且逻辑化地存储和操作数据集。

## 4.2 在 Java 中处理字符串

### 4.2.1 String 类概览

Java 中的 `String` 类用于存储和操作字符序列。字符串是不可变的，这意味着一旦创建了 `String` 对象，其内容就无法更改。如果你执行任何修改字符串的操作，Java 会创建一个新的 `String` 对象来存储结果。

Java 在 `String` 类中提供了丰富的方法来执行各种操作，如比较、拼接、分割、搜索以及检查字符串中的单个字符。

### 4.2.2 创建和初始化字符串

在 Java 中有两种创建字符串的方法：通过使用字符串字面量或使用 `new` 关键字。

- **使用字符串字面量**

```
String greeting = "Hello";
```



当使用字符串字面量创建字符串时，Java 会首先检查字符串池。如果字符串已经存在，它将返回相同实例的引用。通过这种方式，Java 节省了内存。

- 使用 `new` 关键字

```java
String str1 = "Hello";
String str2 = "Hello";
boolean result = str1.equals(str2); // true
```

### 4.2.3 比较字符串：方法

Java 提供了几种方法来比较字符串：

- `equals()`：此方法比较实际内容。如果字符串相等则返回 `true`，否则返回 `false`。

```java
String str1 = "Hello";
String str2 = "World";
int result = str1.compareTo(str2); // 负值
```

- `equalsIgnoreCase()`：此方法与 `equals()` 类似，但在比较时忽略大小写。

```java
String str1 = "hello";
String str2 = "Hello";
boolean result = str1.equalsIgnoreCase(str2); // true
```

- `compareTo()`：此方法按字典顺序比较两个字符串并返回一个整数值。值为 `0` 表示两个字符串相等。值小于 `0` 表示调用字符串小于参数字符串。值大于 `0` 则表示相反。

```java
String str1 = "Hello";
String str2 = "World";
int result = str1.compareTo(str2); // 负值
```

### 4.2.4 字符串拼接与分割

- 拼接：可以使用 `+` 运算符或 `concat()` 方法拼接字符串。

```java
String greeting = "Hello";
String name = "John";
String message = greeting + ", " + name + "!"; // 使用 + 运算符
String anotherMessage = greeting.concat(", ").concat(name); // 使用 concat()
```

- 分割：`split()` 方法用于根据指定的正则表达式将字符串分割为字符串数组。

```java
String fruits = "apple, banana, cherry";
String[] fruitsArray = fruits.split(", ");
// fruitsArray 包含 ["apple", "banana", "cherry"]
```

处理字符串是 Java 编程中的常见任务。`String` 类提供了许多用于字符串比较、拼接和分割的方法，便于管理和修改 Java 程序中的字符串。

## 4.3 高级数组概念

### 4.3.1 动态数组及其用法

在 Java 中，数组的大小是固定的。然而，有时我们需要根据需要增长或缩小的数据结构。Java 集合框架提供了 `ArrayList`，这是一种实现动态数组的类，它可以自动调整容量。

```java
import java.util.ArrayList;
ArrayList<Integer> dynamicArray = new ArrayList<>();
dynamicArray.add(10); // 添加元素
dynamicArray.add(20);
System.out.println(dynamicArray.get(0)); // 访问元素
```

当元素数量未知时，动态数组特别有用。它们提供了高效添加、删除和搜索元素的方法。

### 4.3.2 Arrays 类：排序与搜索

`java.util.Arrays` 类提供了静态方法，用于对数组进行排序和搜索。这些工具极显著简化了数组的操作。

- 排序

要对数组排序，可以使用 `Arrays.sort()` 方法。它会直接对数组进行修改，将元素按升序排列。

```java
import java.util.Arrays;
int[] numbers = {5, 3, 9, 1};
Arrays.sort(numbers); // numbers 数组现在已经排序
```

- 搜索

对数组进行排序后，可以使用 `Arrays.binarySearch()` 方法进行二分查找。如果找到了目标值，则返回该值的索引；否则返回一个负数。

```java
int[] numbers = {1, 3, 5, 5, 9}; // 二分查找必须先排序
int index = Arrays.binarySearch(numbers, 5); // 返回 2
```

### 4.3.3 数组转换：从数组到集合以及反之

Java 提供了在数组和集合（如 `List`、`Set` 和 `Map`）之间进行转换的机制，允许你利用集合框架提供的工具。

- 数组转集合

你可以使用 `Arrays.asList()` 方法将数组转换为列表。集合可以使用 `toArray()` 方法转换回数组。

```java
String[] color = new String[colorList.size()];
colorList.toArray(color); // 将 List 转回数组
```

### 4.3.4 实际用例与示例

动态数组结合 `Arrays` 类提供的数组操作工具广泛应用于各个领域：

- 数据聚合：为报告或分析收集并汇总数据，通常涉及集合的动态调整大小、排序和搜索操作。
- 系统管理：解析和处理日志文件、配置文件或用户输入，可能涉及数组与集合类型之间的转换，以便于操作。
- 游戏开发：管理游戏中的实体（如角色、障碍物和道具），通常需要动态数组来灵活地添加和删除元素。

示例：寻找最大值和最小值

```java
int[] numbers = {4, 1, 13, 0, 6};
Arrays.sort(numbers); // 对数组排序
int min = numbers[0]; // 第一个元素是最小的
int max = numbers[numbers.length - 1]; // 最后一个元素是最大的
System.out.println("Minimum: " + min + ", Maximum: " + max);
```

示例：从列表中去重

高级数组概念（包括动态数组和 `Arrays` 类提供的工具）是开发高效健壮的 Java 程序的基础。

## 4.4 String 类函数与操作

### 4.4.1 数据类型转字符串

将各种数据类型转换为字符串是一个常见需求。在 Java 中，可以通过几种方法实现：

- `String.valueOf()`：此静态方法可以将各种数据类型（`int`、`long`、`float`、`double`、`char`、`char` 数组等）转换为字符串。

```java
int num = 100;
String str = String.valueOf(num); // "100"
```

- 使用 `toString()` 方法：Java 中的每个类都从 `Object` 类继承了 `toString()` 方法，可以重写它以以字符串的形式表示对象。

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

- 大小写转换（Case Conversion）：转换字符串的大小。

```java
String str = "Java Programming";
String lowerStr = str.toLowerCase(); // "java programming"
String upperStr = str.toUpperCase(); // "JAVA PROGRAMMING"
```

### 4.4.3 String 方法：长度、字符提取与模式匹配

- 长度（Length）：返回字符串中的字符数量。

```java
String str = "Hello";
int length = str.length();
```

- 字符提取（Character Extraction）：获取指定索引处的字符。

```java
String str = "Hello";
char ch = str.charAt(0); // 'H'
```

- 模式匹配（Pattern Matching）：检查字符串是否包含特定序列。

```java
String str = "Java Programming";
boolean contains = str.contains("Java"); // true
```

可用的。当你定义一个方法时，你将其参数列表作为其声明的一部分。当你调用该方法时，你提供与这些参数对应的参数。Java 方法通过“按值传递”来接收参数，这意味着方法接收的是原始数据的拷贝。

```java
public static void greet(String name) {
    System.out.println("Hello, " + name);
}

public static void main(String[] args) {
    greet("Alice"); // 将 "Alice" 作为参数传递给 greet 方法
}
```

### 5.2.2 基本类型 vs. 引用参数

在 Java 中，方法参数是按值传递的。这个概念在基本类型和引用类型中的表现不同。

- 基本类型参数：对于基本数据类型（例如 `int`、`double`、`char`），方法接收的是该值的拷贝。修改此值不会影响原始变量。

```java
public static void increment(int number) {
    number++;
    System.out.println("Number inside method: " + number);
}

public static void main(String[] args) {
    int value = 5;
    increment(value); // value 在方法外部保持为 5
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

### 5.2.3 返回类型详解

方法的返回类型决定它可以返回给调用者的值的类型。返回类型在声明中紧跟方法方法之前。方法可以返回任何类型的数据，包括基本类型、对象，甚至没有数据（`void`）。如果方法声明了返回类型（`void` 除外），则它必须使用 `return` 语句来返回该类型的值。

```java
public static double getAverage(int sum, int count) {
    return (double) sum / count;
}
```

### 5.2.4 从方法返回多个值

Java 方法只能返回一个值。然而，你可以通过数组或对象来封装多个值，从而绕过这一限制。

- 使用数组：适用于返回相同类型的多个值。

```java
public static int[] minMax(int[] numbers) {
  int[] result = {numbers[0], numbers[0]}; // 假设数组不空
  for (int num : numbers) {
    if (num < result[0]) result[0] = num; // 更新 num
    if (num > result[1]) result[1] = num; // 更新最大值
  }
  return result; // 包含最小值和最大值的数组
}
```

- 使用对象：适用于返回不同类型的值或当你需要返回结构化数据时。

```java
class MinMax {
  int min;
  int max;

  MinMax(int min, int max) {
    this.min = min;
    this.max = max;
  }

  public static MinMax findMinMax(int[] numbers) {
    return new MinMax(/* 最小值的计算 */, /* 最大值的计算 */);
  }
}
```

理解参数及其类型，掌握返回机制，是开发高效灵活的 Java 应用程序的必备技能。

## 5.3 方法重载

### 5.3.1 方法重载的概念

方法重载是 Java 的一种特性，允许在同一个类中存在多个相同名称的方法，只要它们在参数上有所不同（参数的数量、参数类型或两者均不同）。这不涉及方法的返回类型；它完全是由参数驱动的。重载实现了多态，使得方法在处理不同的输入场景时更加灵活，而无需为每种变体创建唯一的方法名。

### 5.3.2 使用不同参数类型重载方法

Java 允许根据不同的参数类型对方法进行重载。这意味着你可以拥有接受不同类型参数的多个版本。它允许方法在同一个方法名下通过相同的逻辑操作处理不同类型的输入。

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

在上面的示例中，`add` 方法被重载以同时处理整数和双精度加法，使得 `Calculator` 在处理输入类型时更加灵活。

### 5.3.3 使用不同参数数量重载方法

方法重载也可以基于参数的数量。这种变体对于输入数量不同的方法非常有用，你可以拥有相同名称但参数数量不同的方法。

```java
public class Calculator {
    public int multiply(int a, int b) {
        return a * b;
    }

    public int multiply(int a, int b, int c) {
        return a * b * c;
    }
}
```

### 5.3.4 方法重载的最佳实践

虽然重载增加了灵活性，但请考虑以下几点：

1. 谨慎使用重载：在合理的情况下重载。
2. 保持逻辑一致性：确保重载的方法执行相似的任务。
3. 使用清晰且具描述性的参数：这有助于明确。
4. 对于相同类型的多个参数考虑可变参数（varargs）：当需要处理数量不定的参数时，考虑使用可变参数。

## 5.4 理解作用域与可见性

### 5.4.1 方法变量的作用域

变量的作用域决定了在代码的什么位置可以被访问。方法变量（称为局部变量）定义在方法内部，仅在该方法内可用。它们在方法执行完成后就会消失。这种有限的作用域有助于减少命名冲突和内存占用，因为这些变量是临时的。

```java
public void myMethod() {
    int local = 5; // 局部变量，在此可用
}
```

### 5.4.2 全局变量与局部变量

- 局部变量：这些定义在方法内部，只能在该方法内访问。它们在每次调用方法时初始化，并且在方法外部不可见。

```java
public void someMethod() {
    int localVar = 10; // 局部变量。在此可用
}
```

- 全局变量：在 Java 语言中，全局变量通常被称为字段或类变量。这些变量可以从类的任何方法访问（取决于访问修饰符）。它们定义在方法之外，通常在类的顶部。

```java
public class MyClass {
    int globalVar = 20; // 字段，类内任何方法均可访问

    public void anotherMethod() {
        System.out.println(globalVar); // 访问全局变量
    }
}
```

### 5.4.3 访问修饰符及其影响

Java 中的访问修饰符控制类字段（变量）和方法对其他类及程序部分的可见性。理解它们对于控制访问级别和保护对象至关重要。

- 私有（`private`）：私有修饰符将可见性限制在声明类内部。这是封装的核心原则，防止数据被意外访问和修改。
- 默认（无修饰符）：允许在包内访问字段和方法。它比私有的更开放，但仍然提供了受限的访问级别。
- 保护（`protected`）：与默认访问类似，但子类（即使在不同的包中）也可以访问受保护的成员。
- 公共（`public`）：`public` 修饰符允许字段和方法被应用程序中的任何其他类访问。



```java
public class ModifierExample {
    private int privateVar = 1;
    int defaultVar = 2;
    protected int protectedVar = 3;
    public int publicVar = 4;
}
```

## 5.4.4 封装与受保护的访问

封装是面向对象编程的一个 fundamental 原则。它涉及将数据（属性）和操作这些数据的方法（函数）封装成一个单一的单元（即类），并限制对数据具体细节的访问。

实现封装：在字段上使用 `private` 修饰符，并提供公共的 `public` getter 和 setter 方法来访问和更新值。

```java
public class Encapsulated {
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

受保护的访问：`protected` 访问通常在继承的范围内使用。它允许子类访问父类的字段和方法，同时与 `public` 访问相比仍保持受限的级别。

```java
public class Base {
    protected int baseNumber;
}

public class Derived extends Base {
    public void show() {
        baseNumber = 10; // 由于 protected 可以访问
        System.out.println("Base number: " + baseNumber);
    }
}
```

理解作用域和访问性的细微差别可以显著影响 Java 应用的设计和健壮性。

## 6.1 面向对象编程基础

### 6.1.1 面向对象编程简介

面向对象编程（OOP）是一种基于“对象”概念的编程范式，对象以字段（通常称为属性）的形式包含数据，以方法的形式包含代码。OOP 的核心概念包括：

- 类：创建对象的模板，定义了它们的结构和行为。
- 对象：类的实例，代表特定的实体。
- 继承：一种从现有类创建新类的机制，增强了代码的重用性。
- 多态：在不同的对象上调用同一个方法并让每个对象以其自己的方式做出响应的能力。
- 封装：将数据和操作数据的方法封装在一个单元内，限制对某些组件的访问。

### 6.1.2 面向对象编程的优势

- 模块化：对象的源代码可以独立与其他对象的源代码进行编写和维护。这使得管理大型应用程序变得更容易。
- 代码重用：通过继承，可以从现有类派生出新类，导致大量的代码重用。
- 可扩展性：OOP 允许开发者通过增量添加对象来构建程序，使得处理更大的项目变得可行。
- 维护：通过封装，对象可以隐藏其内部状态并在不影响其他代码部分的情况下进行更改，从而有助于维护。
- 设计：OOP 方法论鼓励规划和思维过程，从而实现更灵活、模块化和抽象的设计。

### 6.1.3 OOP 与 过程化编程

虽然 OOP 对象和数据组织代码，但过程化编程以过程或例程为中心。主要区别包括：

- 状态和行为：在 OOP 中，数据（状态）和操作（行为）被封装在一起，而在过程化编程中，过程对传递它们的数据进行操作。
- 模块化和维护：OOP 为程序提供了更清晰的模块化结构，使得跟踪程序元素、增强它们和修复错误变得更容易。
- 可重用性和可扩展性：得益于继承和多态，面向对象的程序鼓励软件组件的重用，而这在过程化方法中是不太自然的。

### 6.1.4 OOP 中的关键术语：类、对象、方法和属性

- 类：创建对象的蓝图。类定义了对象的初始状态以及对象可以采取的一系列动作（方法）。
- 对象：类的实例。每个对象都有自己的实例。
- 方法：与类相关的程序，定义对象可以执行的操作。
- 属性：对象的特征，描述对象的某些特性。

这些基本概念和优势使得 OOP 成为设计软件的热门选择。

## 6.2 类与对象的操作

### 6.2.1 在 Java 中定义类

在 Java 中，类是创建对象的模板，包含属性和方法。类使用 `class` 关键字定义并在大括号内。

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

`Car` 类有两个属性（`model` 和 `year`）和一个方法（`displayInformation`）。

### 6.2.2 创建和使用对象

对象是使用 `new` 关键字创建的类的实例。一旦创建了对象就可以访问它的属性并调用它的方法。

```java
public class TestCar {
    public static void main(String[] args) {
        // 创建 Car 对象
        Car myCar = new Car();
        myCar.model = "Toyota";
        myCar.year = 2020;

        // 使用类的方法
        myCar.displayInformation();
    }
}
```

### 6.2.3 实例变量和方法

实例变量和方法属于类的实例。对于从类创建的每个对象都有自己的变量副本和使用方法的能力。要调用实例方法，我们需要使用 `new` 关键字创建一个对象。

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

- 静态变量：也称为类变量，它们在类的实例之间共享。静态变量的任何更改都会反映在所有实例中。
- 静态方法：无需创建对象即可调用的方法。它们可以访问静态变量并更改值。

```java
public class Counter {
    static int count = 0; // 静态变量

    static void increment() { // 静态方法
        count++;
    }
}
```

## 6.3 理解构造函数

### 6.3.1 Java 中构造函数的作用

在 Java 中，构造函数是在实例化对象时调用的特殊方法。构造函数的名称与类名相同，且没有返回值（即使是 void）。构造函数的主要用途是在新创建的对象使用之前对其进行初始化，通常是为其字段分配初始值。

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

### 6.3.2 构造函数的类型：默认与参数化

- 默认构造函数：如果类中没有显式定义构造函数，Java 会自动提供一个没有参数的默认构造函数，它除了实例化对象外什么都不做。然而，如果类中显式声明了任何其他构造函数，则不再提供默认构造函数。

```java
public class Example {
    // Java 将在这里创建一个默认构造函数。
}
```

- 参数化构造函数：包含参数的构造函数用于创建时使用特定状态初始化对象。使用参数化构造函数，你可以在创建对象时为其提供不同的值。

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

构造函数重载是 Java 中的一项特性，一个类可以有多个构造函数，它们接受的参数有所不同。这允许你根据创建对象时可用的信息以不同的方式创建对象。

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

### 6.3.4 构造函数链

构造函数链指的是相对于当前对象从一个构造函数调用另一个构造函数的过程。可以通过 `this()` 和 `super()` 调用来实现。使用 `this()` 允许从同类的另一个重载构造函数调用构造函数，而 `super()` 则调用父类的构造函数。

```java
public class Student {
    String name;
    int age;

    // 1个参数的构造函数
    Student(String name) {
        this(name, 18); // 调用带 2 个参数的构造函数
    }

    // 2个参数的构造函数
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

构造函数链通过允许构造函数利用另一个构造函数的初始化过程来简化代码并消除冗余。

## 6.4 OOP 的支柱：封装、继承与多态

### 6.4.1 封装：使用访问修饰符保护数据

封装是面向对象编程中的一个基本概念，它将数据（属性）和对数据操作的代码（方法）封装成一个单元。此外，它限制了对对象某些组件的直接访问，这是防止意外修改数据的一种手段。对限制组件的访问通常通过 getter 和 setter 方法实现。

Java 使用访问修饰符来保护变量和方法。常见的访问修饰符有：

- Private（私有）：成员仅在所属类内部可访问。
- Protected（受保护）：成员在所属包内以及子类中可访问。
- Public（公有）：成员可以从任何其他类访问。

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

### 6.4.2 继承：扩展类与代码复用

继承允许一个类继承另一个类的方法和字段。在 Java 中，继承用于促进代码复用并建立类与类的关系。

#### 创建子类

要继承一个类，你需要使用 `extends` 关键字。被继承的类被称为父类，继承的类被称为子类。

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

#### 方法重写与 super 关键字

方法重写发生在子类为父类已经提供的方法提供了特定实现时。`super` 关键字用于访问被重写的方法。

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
        System.out.println("The pig says: wee wee");
    }
}
```

### 6.4.3 多态：静态与动态

Java 中的多态有两种类型：编译时（静态）和运行时（动态）。

#### 方法重载

方法重载（静态多态）发生在同一个类中，当两个或多个方法具有相同名称但参数不同时。

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

#### 方法重写与动态方法分派

方法重写（动态多态）允许子类重写其父类中的方法。动态方法分派是一种机制，通过对重写方法的调用在运行时而非编译时进行解析。

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

    // 重写 rectangle 的 area
    double area() {
        System.out.println("Inside Area for Rectangle.");
        return dim1 * dim2;
    }
}
```

### 6.4.4 抽象类与接口：强制规范

抽象类：抽象类不能被实例化，可以包含抽象方法，即没有方法体的方法。当你想在多个相关类之间共享代码时，可以使用它们。

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

接口：接口是一个用于一组带有空方法的方法的“完全抽象类”。类可以实现多个接口，克服了单继承的限制。

示例：

```java
interface Animal {
    void sound(); // 接口方法（没有方法体）
}

class Pig implements Animal {
    public void sound() { // 在此处提供 sound() 的主体
        System.out.println("The pig says: wee wee");
    }
}
```

## 7.1 继承基础

### 7.1.1 理解继承的基础

继承允许一个新类（称为子类或派生类）吸收另一个类（称为父类或基类）的成员（字段、方法和构造函数）。其主要优势是可以定义一个公共基类，以便在多个派生类之间共享代码。

核心概念包括：

- 父类与子类：父类是被其他类继承的类，而子类是继承自父类的类。
- `extends` 关键字：在 Java 中，类使用 `extends` 关键字来声明它继承自另一个类。

### 7.1.2 创建和扩展父类



# 创建父类

创建父类涉及定义一个普通类，其他类将继承自该类。使用 `extends` 关键字对该类进行扩展。例如，如果 `Animal` 是一个父类，创建一个继承自 `Animal` 的子类 `Dog` 可以如下所示：通过扩展 `Animal`，`Dog` 继承了 `eat` 方法，并且也可以定义定义自己的方法，例如 `bark`。

# 7.1.3 利用保护访问修饰符

`protected` 访问修饰符在继承中起着至关重要的作用。父类中声明为 `protected` 的成员可以被子类访问（包括包外的子类），但无法被包外的类访问。

该修饰符有助于封装父类的成员，允许对它们进行受控的访问，而不是 `public` 访问（可能会暴露过多的父类内部细节）或 `private` 访问（这将阻止子类访问重要的成员）。

# 7.1.4 探索继承层次结构和多重继承问题

当一个类继承自一个子类时，就会形成继承层次结构，创建一个具有多个级的类“族谱”。这允许在每个子类层级实现更具体的分类和行为。

Java 不支持通过类进行多重继承，以避免“菱问题”，即一个类继承自两个具有相同方法签名方法的类。这可能会让编译器产生困惑，不知道该调用哪种方法。然而，Java 通过允许类实现多个接口来解决多重继承的需求。

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

在这里，`Bat` 继承自 `Mammal`，`Mammal` 又继承自 `Animal`，形成了一个层次结构。通过理解并适当实现继承，开发者可以创建灵活且易于维护的代码。

# 7.2 使用 'super' 和方法重写

`super` 关键字的使用和方法重写的概念在 Java 继承实现中起着重要作用，增强了功能性和多态。

## 7.2.1 'super' 关键字访问父类成员的作用

Java 中的 `super` 关键字是一个引用变量，用于引用直接父类对象。它可以用于访问在子类中重写或隐藏的父类方法和构造函数。

- 访问父类方法：`super` 可以调用在子类中被重写的父类方法。当你希望从子类中同时访问父类和子类版本的方法时，这特别有用。
- 调用父类构造函数：`super()` 可以调用父类构造函数。`super()` 的调用必须是子类每个构造函数的第一个语句。如果子类构造函数没有显式调用父类构造函数，Java 编译器会自动插入对父类无参数构造函数的调用。

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

方法重写发生在类重新定义父类方法时。重写允许子类提供父类方法的具体实现。

重写规则：方法必须完全匹配父类方法。

重写的示例：

```java
class Vehicle {
  void run() {
    System.out.println("Vehicle is running");
  }
}

class Car extends Vehicle {
  @Override
  void run() {
    System.out.println("Car is running");
  }
}
```

## 7.2.3 重写的规则与最佳实践

1. 签名匹配：方法名和参数必须与父类。
2. 访问级别：访问级别不能比父类方法更严格。
3. 返回类型：必须与父类相同或为子类型。
4. 对父类的调用：有时需要在子类中调用父类的版本。

## 7.2.4 @Override 注解的重要性

`@Override` 注解表示该方法意图重写父类中的方法。如果方法没有实际重写父类方法，编译器会报错。此注解增强了代码的安全性，并确保子类正确重写了预期的方法。

# 7.3 接口与抽象类

接口和抽象类是 Java 中实现抽象和多重继承（通过接口）的两个概念。它们为类设定蓝图，指导它们实现哪些方法。

## 7.3.1 定义和实现接口

Java 接口是一种引用类型，类似于类，但只包含常量、方法签名、默认方法、静态方法和嵌套类型。接口不包含实例字段。接口中的方法默认是抽象的。

要定义接口，使用 `interface` 关键字。类实现接口并必须为接口中的抽象方法提供具体实现。

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

接口和抽象类都可以拥有抽象方法，但存在关键区别：

- 抽象类：可以包含带有实现的方法的方法。子类只能继承一个抽象类。
- 接口：在 Java 8 之前，接口只能包含没有实现的抽象方法。从 Java 8 开始，它们可以包含带有主体的默认和静态方法。类可以实现多个接口。

当子类共享带有实现的方法时使用抽象类。接口通常用于定义一组通用功能，任何类都可以提供这些功能。

## 7.3.3 在接口中使用默认和静态方法

Java 8 引入了通过默认和静态方法在接口中定义具体方法的能力。这允许向接口中添加新功能，而不影响实现这些接口的类。

- 默认方法：允许在接口内部实现方法。实现接口的类可以重写默认方法。

```java
interface Vehicle {
  default void print() {
    System.out.println("I am a vehicle!");
  }
}
```

- 静态方法：可以在接口内声明，不能被实现类重写。

```java
interface Animal {
  static void test() {
    System.out.println("Static method in interface");
  }
}
```

## 7.3.4 应用接口多重继承

在 Java 中，多重继承——一个类从多个父类继承行为的能力——是不被直接支持的（为了避免“菱形问题”）。然而，Java 允许通过接口实现多重继承。一个类可以实现多个接口，从而继承多个源的抽象方法。

多重继承的示例：

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

# 7.4 多态的实应用

多态是面向对象编程中的核心概念，允许根据执行操作的实际对象以不同的方式运行。它增强了灵活性并在不修改代码的情况下扩展代码的能力。Java 中的多态有两种类型：静态（编译时）和动态（运行时）。

## 7.4.1 演示静态和动态多态

- **静态多态**通过方法重载实现。它发生在编译时。在静态多态中，响应是在编译时确定的。

方法重载的示例：

```java
class Display {
    void show(int x) {
        System.out.println("Integer value: " + x);
    }

    void show(String s) {
        System.out.println("String value: " + s);
    }
}
```

- **动态多态**通过方法重写实现。它发生在运行时。在动态多态中，响应是在运行时确定的。

方法重写的示例：

```java
class Animal {
    void sound() {
        System.out.println("Animal sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Bark");
    }
}
```

## 7.4.2 方法重载与方法重写

- 方法重载（静态多态）：允许在同一个类中定义多个具有相同名称但参数不同的方法。它在编译时确定。
- 方法重写（动态多态）：允许子类为父类中提供的方法提供特定的实现。它在运行时确定。

## 7.4.3 动态分发

动态分发是一种在运行时而非在编译时解析对被重写方法调用的机制。这是 Java 运行时多态的基础。

## 7.4.4 现实世界示例

- 图形用户界面 (GUI)：按钮点击或按键按下等事件根据触发它们的组件以不同的方式进行处理。
- 处理系统：不同类型的数据可能使用相同的方法名进行处理，但对每种数据类型有不同的实现。

# 异常处理

异常是程序执行过程中发生的中断正常流程的事件。恰当处理异常允许程序继续运行或优雅地终止。

## 8.1.1 什么是异常？

异常可以是执行过程中遇到的任何错误状况或意外行为。当出现此类情况时，会创建一个代表该错误的对象并将其抛出。如果该方法没有处理该异常，它将沿调用栈传递。

## 8.1.2 异常的类型

Java 中的异常主要分为两类：检异常（checked exceptions）和未检异常（unchecked exceptions）。

### 检异常

检异常是在编译时被检查的异常，这意味着编译器要求代码要么处理这些异常，要么使用 `throws` 声明它们。检异常的存在标志着预期中但不可避免的问题，合理的应用程序应该预见到并从中恢复。检异常的示例是 `FileNotFoundException`。

### 未检异常

未检异常表示程序中的缺陷（bug）。这些异常在编译时不进行检查，而是在运行时检查。由于它们反映了编程错误，通常不会预见到处理它们。示例包括 `NullPointerException` 和 `ArrayIndexOutOfBoundsException`。

## 8.1.3 异常层次结构

所有异常类都是 `Throwable` 类的后代。`Throwable` 类分为两个主类：`Error`（用于普通应用程序不应尝试捕获的错误状况）和 `Exception`，后者进一步细分为检异常和运行时异常（未检异常）。

# 8.2 try, catch 和 finally 块

try、catch 和 finally 块构成了 Java 异常处理机制的核心。它们共同工作以受控的方式捕获并处理异常，确保程序能够从错误恢复并执行必要的清理操作。

## 8.2.1 try 块

`try` 块允许你定义代码块并在执行时对其进行错误测试。

### 在 try 块中编写易异常代码

任何预期抛出异常的代码都应该封装在 `try` 块中。例如，处理文件操作、解析或网络连接的代码经常遇到异常情况，是包含在 `try` 块中的理想选择。

示例：

```java
try {
    // 可能会抛出异常的代码
    FileReader fr = new FileReader("file.txt");
    // 使用文件...
} catch (FileNotFoundException e) {
    // 处理异常
}
```

## 8.2.2 catch 块

`catch` 块用于处理异常。它必须在 `try` 块之后使用。在括号内，你指定想要捕获的异常类型。

### 处理不同的异常

不同类型的异常可以被捕获并进行不同的处理。良好的做法是先捕获特定异常，然后是更通用的异常，以提供更详细的错误处理。

### 多个 catch 块

一个 `try` 块可以跟随多个针对不同类型异常的 `catch` 块。这允许对每个异常类型进行特定处理。

示例：

```java
try {
    // 可能会抛出多个异常的代码
} catch (ArithmeticException e) {
    // ArithmeticException 的特定处理
} catch (NullPointerException e) {
    // NullPointerException 的特定处理
}
```

## 8.2.3 finally 块

`finally` 块包含在 `try` 和 `catch` 块执行后必须执行的代码，无论是否捕获了异常。

### 保证资源释放

`finally` 块适用于清理工作，例如关闭流或释放连接，确保资源不泄漏。

`try`、`catch` 和 `finally` 块的组合提供了一种健壮的机制来确保你的程序能够优雅地处理错误并维护完整性。

# 8.3 创建自定义异常

自定义异常允许开发者创建特定的错误条件，通过定义特定于应用程序的异常来增加错误处理的清晰度。

## 8.3.1 为什么要创建自定义异常？

自定义异常具有多个益处：

- 增强语义：它们通过清晰地指示发生的问题，使代码更具可读性和理解性。
- 一致的错误报告：允许在整个应用程序中进行统一的错误报告。
- 特定异常处理：能够创建精细匹配应用程序需求的异常处理机制。

## 8.3.2 扩展 Exception 类

在 Java 中创建自定义异常，只需扩展 `Exception` 类或其任何子类。

示例：

```java
public class MyCustomException extends Exception {
    public MyCustomException(String message) {
      super(message);
    }
}
```

如果你倾向于创建运行时异常，也可以扩展 `RuntimeException`。

## 8.3.3 实现异常逻辑

在创建自定义异常时，你可以添加额外的字段和方法提供更多关于错误状况的信息。

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

## 8.3.4 在应用程序中使用自定义异常

自定义异常可以像其他异常一样用在应用程序中，优点是更具表现力。

示例：

```java
public class DatabaseService {
    public void connectToDatabase(String dbName) throws DatabaseConnectionException {
        if (dbName == null || dbName.isEmpty()) {
            throw new DatabaseConnectionException(dbName, "Database name cannot be empty");
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
            System.err.println("Failed to connect to database " + e.getDbName() + ": " + e.getMessage());
        }
    }
}
```

在这个示例中，抛出并捕获了自定义异常，可以极大提高错误处理代码的清晰度和可维护性，使应用程序更加健壮且用户友好。

# 8.4 异常处理中的最佳实践

适当的异常处理对于维护软件的可靠可读性至关重要。遵循最佳实践不仅让你的代码更健壮，而且更容易维护。

## 8.4.1 避免常见陷阱



某些异常处理实践会导致代码难以维护或调试。避免这些陷阱对于编写整洁有效的异常处理代码至关重要。

## 捕获通用异常

捕获基类 `Exception`（或 `Throwable`）可能会使诊断困难，因为可能会捕获比预期更多的异常，包括你可能希望向上抛出或以不同方式处理的异常。尽可能捕获特定异常。

### 糟糕的做法

```
try {
  // 风险代码
} catch (Exception e) {
  // 通用处理
}
```

### 更好的方法

```
try {
  // 风险代码
} catch (SpecificException e) {
  // 特定处理
}
```

## 忽略异常

静默地捕获并忽略异常可能会让程序处于不可预测的状态，导致难以诊断问题。

### 糟糕的做法

```
try {
  // 风险代码
} catch (Exception e) {
  // 忽略
}
```

### 更好的方法

始终以有意义的方式处理异常，或者至少记录它。

```
try {
  // 风险代码
} catch (Exception e) {
  log.error("发生了一个错误", e);
}
```

## 8.4.2 使用 finally 进行清理

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

## 8.4.3 记录异常行为

使用 JavaDoc 中的 `@throws`（或 `@exception`）标签记录你的方法可能抛出的异常。这些文档对于使用你方法的其他开发者来说至关重要，让他们了解他们涉及的风险以及如何处理潜在问题。

```java
/**
 * 连接到指定的数据库。
 *
 * @param dbName 数据库名称。
 * @throws DatabaseConnectionException 如果连接失败。
 */
public void connectToDatabase(String dbName) throws DatabaseAccessException {
    // 实现
}
```

## 8.4.4 异常处理与应用程序设计决策

异常处理应该是初始设计阶段的一部分，而不是事后补救。尽早决定哪些异常应该是受检的（非检的，如何使用自定义异常提供更清晰的错误报告，并建立应用程序不同层级处理异常的指南。

设计良好的异常处理可以极地提高应用程序的健壮性、可维护性和用户体验。它是整个软件生命周期中影响架构和设计决策的关键方面。

# 深入理解 Java 集合框架

## 9.1 Java 集合概述

Java 集合框架 (JCF) 是一组实现常用复用集合数据结构的类和接口。它是 Java 最强大且最灵活的 API 之一，包含了可以动态存储对象的各种数据结构。

### 9.1.1 集合框架简介

### 9.1.2 Collection 接口

框架的核心是 `Collection` 接口，它为所有集合类型提供了标准功能。`Collection` 接口是 `List`、`Set` 和 `Queue` 等接口的基础，每个接口都对应不同的抽象数据类型。实现类必须提供添加、删除和查询集合大小等常用操作的功能。

### 9.1.3 集合的主要特性

集合的主要特性包括：

- **动态大小**：与数组不同，集合的大小可以动态增长或缩小，根据需要容纳更多元素。
- **类型安全**：泛型允许集合强制执行类型安全，确保只存储指定类型的对象，从而减少运行时错误。
- **可迭代性**：可以使用迭代器或增强型 for 循环对集合进行迭代，使得遍历和操作元素变得更容易。
- **数据操作**：集合提供了添加、删除和搜索元素的方法，比基本数据类型或数组具有更大的灵活性。

### 9.1.4 集合、数组与基本数据类型的比较

集合与数组及基本数据类型在多个方面不同：

- **大小与灵活性**：集合是动态的，而数组具有固定大小。集合比数组提供了更多的灵活性功能。
- **性能**：对于添加或删除元素等某些操作，由于额外的抽象，集合可能比数组慢。然而，某些集合类型针对特定操作进行了优化。
- **类型安全与实用性**：集合支持泛型，相比数组增强了类型安全。此外，集合框架提供了排序和搜索等常用任务的实用方法，而这些任务使用数组处理会非常繁琐。

### 9.1.5 选择正确的集合

选择正确的集合类型取决于几个因素：

- **顺序**：如果你需要维护插入顺序，考虑 `ArrayList` 或 `LinkedHashSet`。
- **重复**：如果集合不能包含重复，使用 `HashSet` 等 `Set` 实现。
- **键值对**：为了高效检索而以键值对的形式存储数据，请使用 `HashMap` 等 `Map` 实现。
- **访问**：如果你需要通过索引快速访问元素，请使用 `ArrayList` 等 `List` 实现。
- **并发**：在多线程环境中工作时，考虑使用 `java.util.concurrent` 包中的线程安全或并发集合。

选择合适的集合类型可以同时优化代码的性能和可读性，使集合框架成为高效 Java 开发的基石。

## 9.2 List、Set 和 Queue

Java 集合框架将它的数据结构划分为几个核心接口，每个接口都有不同的数据管理目的。其中，`List`、`Set` 和 `Queue` 接口是基础性的，每个满足特定的需求。

### 9.2.1 理解 List 接口

Java 中的 `List` 接口允许元素的有序集合，包括重复元素。`List` 在元素插入顺序很重要或需要对元素进行直接位置访问的场景下表现出色。

#### ArrayList

- **描述**：一种基于可调整大小数组的 `List` 接口实现。它通过索引快速访问元素。
- **用途场景**：适用于插入和删除操作极少但访问操作频繁的场景。
- **关键特性**：自动调整大小，快速的随机访问。

#### LinkedList

- **描述**：`List` 和 `Deque` 接口的双向链表实现。它允许在列表的开头或结尾进行常数时间级别的插入和删除。
- **用途场景**：适用于频繁插入和删除的应用。
- **关键特性**：每个元素（节点）都包含指向下一个节点和上一个节点的引用。

#### Vector 和 Stack

- **Vector 描述**：一种同步的、可调整大小的 `List` 接口实现。比 `ArrayList` 慢，但适用于线程安全操作。
- **Stack 描述**：扩展自 `Vector` 的对象后进先出 (LIFO) 栈。它实现了传统的栈操作。
- **用途场景**：`Vector` 用于需要动态数组的线程安全应用程序。`Stack` 用于深度优先搜索算法和撤销机制。

### 9.2.2 探索 Set 接口

`Set` 接口模拟了数学中的集合抽象，适用于存储不重复元素而无需担心它们的顺序。

#### HashSet

- **描述**：实现 `Set` 接口，以哈希表为基础。
- **用途场景**：当需要唯一性且不在乎顺序时是理想选择。
- **关键特性**：基本操作具有常数时间性能。

#### LinkedHashSet

- **描述**：`HashSet` 的有序版本，使用双向链表维护插入顺序。
- **用途场景**：当你需要唯一性但同时也需要可预测的迭代顺序时有用。
- **关键特性**：由于维护开销，比 `HashSet` 略慢。

#### TreeSet

- **描述**：实现 `NavigableSet` 接口并根据元素的值组织元素。
- **用途场景**：对于排序和范围搜索很重要的集合是理想选择。
- **关键特性**：保证基本操作具有 log(n) 时间复杂度。

### 9.2.3 使用 Queue 接口

`Queue` 支持典型的队列操作：提供元素 (offering)、取出元素 (polling) 和检查元素，主要满足 FIFO (先进先出) 顺序。

#### PriorityQueue

- **描述**：一种基于优先级堆的无界优先级队列。
- **用途场景**：在根据优先级而非插入顺序处理元素的场景中非常有用。
- **关键特性**：不允许 `null` 元素。

#### Deque 接口

一种支持在两端插入和移除元素的线性集合。它是栈和队列的泛化。

#### ArrayDeque

- **描述**：一种基于可调整大小数组的 `Deque` 接口实现。
- **用途场景**：作为栈 (LIFO) 还是队列 (FIFO) 都是高效的。
- **关键特性**：当用这些结构使用时，比 `Stack` 和 `LinkedList` 快。

#### LinkedList as Deque

- **描述**：虽然主要是列表，但 `LinkedList` 也实现了 `Deque` 接口。
- **用途场景**：当同时需要列表和队列功能时适用。
- **关键特性**：在两端进行常数时间级别的插入和删除。

## 9.3 Map 接口及实现类

### HashMap

- **描述**：实现了 `Map` 接口，使用哈希表。它允许 `null` 值和一个 `null` 键，在哈希函数在桶中分布良好的情况下，基本操作（`get` 和 `put`）具有常数时间性能。
- **使用场景**：当插入顺序不重要且需要快速访问元素时，使用效果最佳。
- **关键特性**：对 `HashMap` 视图（键、值、条目）的迭代取决于哈希表的容量和键值对的数量。

### LinkedHashMap

- **描述**：一种带有贯穿其中的链表列表的 `HashMap`，因此它维护了插入顺序（或可选的访问顺序）。除了排序行为外，它的特性与 `HashMap` 相同。
- **使用场景**：适用于需要保留插入/访问顺序的场景。
- **关键特性**：由于为了维护顺序而增强了结构，其在迭代方面的性能略低于 `HashMap`。

### TreeMap

- **描述**：实现了 `NavigableMap` 接口，并根据键的自然顺序或指定的 `Comparator` 对键进行排序。它基于红黑树结构。
- **使用场景**：当需要提取键的范围或要求键进行排序时是理想选择。
- **关键特性**：为 `containsKey`、`get`、`put` 和 `remove` 操作提供保证的 log(n) 时间成本。

### 9.3.2 比较 Map 实现类

| 特性/Map 类型 | HashMap | LinkedHashMap | TreeMap |
| :--- | :--- | :--- | :--- |
| 排序 | 无序 | 插入/访问顺序 | 排序顺序 |
| Get/Put 时间 | O(1) 平均 | O(1) 平均 | O(log n) |
| 迭代顺序 | 随机 | 插入/访问顺序 | 键的升序 |
| 键的可空性 | 允许一个 null 键 | 允许一个 null 键 | 不允许 null 键（如果使用自然排序） |
| 使用场景 | 需要映射的最常见场景 | 访问顺序很重要时 | 需要排序顺序或范围搜索时 |

### 9.3.3 特殊 Map 实现类

#### WeakHashMap

- **描述**：`HashMap` 的变体，将键存储为弱引用。当 `WeakHashMap` 中的键不再被普通使用时，该条目将被自动移除。
- **使用场景**：适用于缓存和元数据存储，其中存储数据的生命周期取决于对键的外部引用。
- **关键特性**：当键不再被引用时，垃圾回收器会自动删除条目。

#### EnumMap

- **描述**：一种用于枚举（enum）类型键的特殊 `Map` 实现。`EnumMap` 中的所有键必须源于创建 map 时显式或隐式指定的单个枚举类型。
- **使用场景**：当使用枚举进行基于键的数据访问时，它是极高效率且紧凑的。
- **关键特性**：map 的迭代顺序遵循枚举键的自然顺序。

#### Hashtable（遗留）

- **描述**：map 数据结构的早期实现，它是同步的，这意味着它是线程安全的，但在单线程场景下的性能比 `HashMap` 低。
- **使用场景**：现在被认为是遗留类，在已经存在 `ConcurrentHashMap`（用于线程安全的 map） 的下，很少推荐使用它。
- **关键特性**：与 `HashMap` 不同，不允许 null 键或值。

选择正确的 `Map` 实现类可以极大地影响 Java 应用程序的性能和资源消耗，特别是在处理大型数据集或性能关键型应用程序时。

## 9.4 Collection 类工具方法

Java 集合框架不仅提供了各种数据结构，还通过 `Collections` 类包含了一组强大的工具方法。这些工具方法提供了用于排序、搜索、修改和转换集合的方法，增强了高效管理和操作数据的能力。

### 9.4.1 集合排序

排序是集合的基本操作，允许将其元素按特定顺序排列。

#### 使用 Comparable

- **描述**：`Comparable` 接口提供了一个单一的 `compareTo` 方法，定义了对象的自然顺序。实现此接口的类可以很容易地排序。
- **工作原理**：将对象与另一个对象进行比较以确定顺序，根据该对象小于、等于还是大于指定对象，返回负整数、零或正整数。

#### 使用 Comparator

- **描述**：`Comparator` 接口定义了一个 `compare` 方法，允许在对象外部控制对象的顺序。当类无法修改以实现 `Comparable` 时，或者当需要多个排序顺序时，它特别有用。
- **工作原理**：它比较它的两个参数以确定顺序，根据该对象小于、等于还是大于指定对象，返回负整数、零或正整数。

### 9.4.2 在集合中搜索

- `binarySearch()` 方法用于在集合中查找特定元素。它要求集合必须预先进行排序才能正常工作。

### 9.4.3 将集合转换为数组

- `asList()` 方法创建一个由数组支持的固定大小列表。
- `toArray()` 方法将集合转换为数组。

### 9.4.4 Collections 类工具方法概述

- `sort()`：根据元素的自然顺序或指定的 `Comparator` 排序列表中的元素。
- `reverse()`：反转列表中的元素顺序。
- `shuffle()`：随机化列表中的元素顺序。

### 9.4.5 使用线程安全

- `synchronizedList()`、`synchronizedSet()` 和 `synchronizedMap()`：这些方法返回所提供集合的线程安全包装器，确保多线程访问时的安全性。

### 9.4.6 不可修改包装器

- `unmodifiableList()`、`unmodifiableSet()` 和 `unmodifiableMap()`：这些方法为集合提供只读访问。任何尝试修改它们的行为都会抛出 `UnsupportedOperationException`。
- `singletonList()`、`singletonSet()` 和 `singletonMap()`：创建包含单个元素的不可变集合。
- `emptyList()`、`emptySet()` 和 `emptyMap()`：返回不可变的空集合，有助于节省内存。

# 10 Java I/O 与 NIO

## 10.1 文件处理基础

### 10.1.4 Try-with-Resources 和 AutoCloseable 接口

文件处理和流操作中的一个重要关注的问题是确保资源在使用后被正确关闭，以防止资源泄漏。Java 7 引入的 `try-with-resources` 语句简化了这项任务。它在语句执行结束时自动管理资源的关闭。为了与该语句兼容，资源必须实现 `AutoCloseable` 接口，该接口包含了几乎所有的流和相关资源。以下是其用法的一个简洁示例：

在这个示例中，`FileReader` 是一个实现了 `AutoCloseable` 的资源。一旦退出 `try` 块（无论是正常退出还是由于异常），它都会被自动关闭，显著减少了样板代码并最小化了资源泄漏的风险。

## 10.2 NIO 包

### 10.2.1 Java NIO 简介

Java NIO（新输入/输出）在 Java 1.4 中引入，作为标准 Java I/O API 的替代和补充。它提供了非阻塞 IO 操作、面向缓冲区的数据处理方法，以及通过单个线程管理多个网络连接的能力。NIO 的核心组件包括通道（Channels）、缓冲区（Buffers）、选择器（Selectors）和字符集，能够实现更快速、更具扩展性的 I/O 操作，特别是对于需要同时管理大量连接的应用程序（例如 Web 服务器）。

### 10.2.2 缓冲区：NIO 的核心

缓冲区（Buffers）是 NIO 中的核心概念，代表一段连续的内存块，数据在 I/O 操作期间临时存储。与传统 I/O 模型中以线性、顺序方式处理数据的流不同，缓冲区允许对数据进行随机读写。Java NIO 中的缓冲区是类型化的；也就是说，不同的数据类型有对应的缓冲区类，如 `ByteBuffer`、`CharBuffer`、`IntBuffer` 等。这些缓冲区在 `flip` 机制下工作，即缓冲区从写模式切换到读模式，确保了高效的数据访问和处理。

### 10.2.3 通道：处理 IO 的新方式

通道（Channels）可以被认为是管道，数据在缓冲区和外部实体（例如文件或网络套接字）之间传输。它们提供了一个统一的 API 来管理各种类型的 I/O 操作，如从文件读写数据以及网络通信。主要的通道类型包括用于 I/O 的 `FileChannel`、用于 TCP 网络 I/O 的 `SocketChannel` 以及用于 UDP 网络 I/O 的 `DatagramChannel`。与流相比，通道支持在同一个实例上同时进行读取和写入，从而提供了更灵活、更强大的数据处理能力。

### 10.2.4 选择器：使用 NIO 进行多路复用



选择器（Selector）组件是一种机制允许单个线程监控多个通道的事件，例如数据到达、连接打开或读/写就绪。这种能力使得开发高可扩展性的网络应用程序成为可能，而无需为每个连接分配一个线程，显著减少了资源消耗并提高了性能。通过向选择器注册多个通道，应用程序可以以非阻塞的方式高效地管理数个打开连接，检查 I/O 事件并在事件发生时进行处理。这对于处理许多并发连接的服务器（如 Web 服务器或应用服务器）特别有用。

Java NIO 引入缓冲区、通道和选择器标志着 Java I/O 能力的重大增强，为开发者提供了构建高可扩展且高效的网络和文件 I/O 应用程序的工具。从基于流的模型转向面向缓冲区的模型，使得数据处理方式具有更多的控制和灵活性，使 Java NIO 成为现代 Java 应用开发中不可或缺的组件。

## 10.3 在 Java 中读写文件

### 10.3.1 使用 FileInputStream 和 FileOutputStream

`FileInputStream` 和 `FileOutputStream` 是用于读取和写入文件的类。

- `FileInputStream`：它是用于读取文件的。它按字节读取，非常适合处理二进制数据。

```java
FileInputStream fis = new FileInputStream("example.txt");
int i;
while ((i = fis.read()) != -1) {
    System.out.print((char) i);
}
fis.close();
```

- `FileOutputStream`：它是用于写入文件的。类似于 `FileInputStream`，它按字节操作，特别适合处理二进制数据。

```java
FileOutputStream fos = new FileOutputStream("output.txt");
String data = "Hello World!";
fos.write(data.getBytes());
fos.close();
```

### 10.3.2 Reader 和 Writer 类

对于字符数据（如文本文件），Java 提供了 `Reader` 和 `Writer` 类。

- `FileReader` 和 `FileWriter`：这些是用于读取和写入字符文件的类。与字节流不同，它们设计用于处理字符。

### 10.3.3 使用 Files 类

`java.nio` 包中的 `Files` 类提供了一组操作文件和目录的静态方法，这些方法使用 `Path` 对象。

- 读取文件：

```java
Path path = Paths.get("example.txt");
byte[] fileArray = Files.readAllBytes(path);
```

- 写入文件：

```java
Path newPath = Paths.get("newfile.txt");
byte[] data = "Sample text".getBytes();
Files.write(newPath, data, StandardOpenOption.CREATE);
```

### 10.3.4 Path 和 Paths：NIO 增强

在 Java 7 中引入的 NIO.2 文件 API 增加了 `Path` 接口和 `Paths` 工具类，提供了更全面的文件系统处理方法。

- `Path`：代表依赖系统的文件路径。它是用于定位文件系统中文件的对象，提供了检查、定位和操作文件系统对象的方法。

- `Paths`：一个工具类，包含静态方法可以通过路径字符串或 URI 返回 `Path`。

采用 `Files` 类以及 `Path`/`Paths` 接口可以使文件 I/O 操作的代码更具可读性和维护性，提供了符号链接处理、文件属性访问和目录遍历等高级功能，这些在传统的流中无法直接实现的。

## 10.4 理解字节流和字符流

### 10.4.1 字节流与字符流的区别

Java I/O 流分为两大类：字节流和字符流。字节流（`InputStream` 和 `OutputStream` 子类）主要用于处理原始二进制数据，例如图像文件、音频文件和序列化对象。它们按字节读写数据。字符流（`Reader` 和 `Writer` 子类）则设计用于处理字符数据，如文本文件。它们按字符读写数据，自动处理字符编码和解码，从而抽象了字符与字节转换的复杂性。

### 10.4.2 何时使用字节流而非字符流

当处理原始数据或不一定代表字符的二进制文件时，应使用字节流。示例包括：

- 读取写入二进制文件（如图像、视频）。
- 处理序列化对象。
- 与来自源或发送到目的地的非字符数据流交互。

不表示文本数据。在处理文本数据时推荐使用它们，因为它们考虑了字符编码，这对于国际化至关重要。用例包括：

- 读取或写入包含文本的文件。
- 处理源或目的地是基于文本的数据流，例如文档文件或标准 I/O。

## 10.4.3 常见的字节流和字符流类

字节流类：

- `FileInputStream` 和 `FileOutputStream` 用于从文件读取和写入。`BufferedInputStream` 和 `BufferedOutputStream` 用于缓冲 I/O 操作，通过减少所需的 I/O 操作次数来提高效率。

字符流类：

- `FileReader` 和 `FileWriter` 用于读取和写入文本文件。`BufferedReader` 和 `BufferedWriter` 为字符输入输出流提供缓冲，使得文本的读写更加高效。

## 10.4.4 流操作的性能提示

1. 使用缓冲流：将文件流封装在缓冲流（`BufferedInputStream`、`BufferedOutputStream`、`BufferedReader`、`BufferedWriter`）中可以通过减少 I/O 操作次数显著提高性能。
2. 重用对象：在可能的情况下，在程序中重用 I/O 对象，以最小化创建和销毁资源的开销。
3. 正确关闭资源：始终使用 `finally` 块或 `try-with-resources` 语句关闭流，以确保所有资源释放，并且底层文件或套接字关闭。
4. 限制资源分配：注意循环或递归调用中的资源分配。在循环内部打开文件而不正确关闭会导致资源泄漏。
5. 大数据量使用 NIO：对于处理大文件或需要可扩展 I/O 操作（如读取、写入或传输大文件）的应用程序，可以考虑使用 Java NIO 包，因为它提供了可以更高效处理这些场景的通道（channels）和缓冲区（buffers）。

应用这些性能提示将带来更高效、可扩展且易于维护的 Java 应用程序，利用 I/O 流充分读写数据。

# Java 并发与多线程

## 11.1 Java 线程基础

### 11.1.1 使用 Thread 类和 Runnable 接口创建线程

Java 中的线程可以通过两种主要方式创建：通过扩展 `Thread` 类和实现 `Runnable` 接口。

扩展 `Thread` 类：这种方法涉及创建一个自 `Thread` 的新类并重写其 `run()` 方法。可以创建该类的实例并使用其 `start()` 方法启动它。

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

实现 `Runnable` 接口：在这种方法中，类实现了 `Runnable` 接口及其 `run()` 方法。然后创建一个 `Thread` 实例，并将实现该类的实例传递给其构造函数。

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

1. 新 (New)：线程已创建但尚未启动。
2. 可运行 (Runnable)：线程可能正在运行或已准备好运行等待资源分配。
3. 阻塞 (Blocked)：线程被阻塞，等待监视器锁。
4. 等待 (Waiting)：线程无限地等待另一个线程执行特定操作。
5. 定时等待 (Timed Waiting)：线程等待另一个线程执行操作，最长持续指定的时间。
6. 终止 (Terminated)：线程已完成执行。

### 11.1.3 线程优先级与守护线程

- 优先级：Java 允许通过 `setPriority(int)` 方法（1-10）为线程设置优先级。高优先级的线程通常会优先于低优先级的线程执行。
- 守护线程：通过 `setDaemon(true)` 方法设置守护线程。当所有非守护线程结束时，守护线程也会被终止。

### 11.1.4 处理 InterruptedException

`InterruptedException` 在线程等待、睡眠或处于阻塞状态时抛出。妥善处理此异常至关重要，以便清理资源。

```java
class MyRunnable implements Runnable {
    public void run() {
        try {
            Thread.sleep(1000);
            System.out.println("Thread running");
        } catch (InterruptedException e) {
            System.out.println("Thread was interrupted");
        }
    }
}
```

在处理中断时，通常通过调用 `Thread.currentThread().interrupt()` 中断状态。

## 11.2 同步与线程间通信

### 11.2.1 synchronized 关键字与内置锁

Java 中的同步用于确保一次只有一个线程可以访问资源，防止竞态条件和数据不一致。`synchronized` 关键字可以标记方法或代码块，以便只有一个线程可以执行它。

- 同步方法：当方法声明为 `synchronized` 时，它会锁定调用的对象。在锁释放之前，其他线程无法执行该对象的任何同步方法。

```java
public synchronized void increment() {
    count++;
}
```

- 同步块：同步块比同步方法更灵活，因为它们允许锁定不同的对象并可以覆盖方法的一部分。

```java
synchronized(this) {
    count++;
}
```

### 11.2.2 volatile 关键字与内存可见性

`volatile` 关键字在 Java 中确保变量的变化可以预测地传播到其他线程。当字段被声明为 `volatile` 时，编译器和运行时会被该变量是共享的，不应对其进行缓存或重排序。

- 用例：当变量的值被不同线程修改，但对变量的操作不依赖其当前值时（例如停止线程的标志），使用 volatile 变量。

```java
private volatile boolean active;

public void stop() {
  active = false;
}
```

### 11.2.3 wait, notify 和 notifyAll 方法

Object 类中的 `wait()`、`notify()` 和 `notifyAll()` 方法用于线程间通信以及多个线程之间的协调。

- `wait()`：使当前线程等待，直到另一个线程对对象调用 `notify()` 或 `notifyAll()`。
- `notify()`：唤醒等待该对象监视器的一个线程。
- `notifyAll()`：唤醒等待该对象监视器的所有线程。

这些方法必须在有关该对象的同步上下文中（方法或块）中调用。

```java
synchronized(obj) {
    while (<条件不成立>) obj.wait();
    // 执行符合条件的操作
    obj.notifyAll(); // 或 obj.notify();
}
```

### 11.2.4 可重入锁和条件

`java.util.concurrent.locks` 包中的 `ReentrantLock` 类提供了对使用 `synchronized` 方法和块的替代方案，并具有更扩展的功能，例如可中断的锁获取、锁轮询、定时锁等待以及公平性。

```java
private final ReentrantLock lock = new ReentrantLock();
public void method() {
    lock.lock();
    try {
        // 临区代码
    } finally {
        lock.unlock();
    }
}
```

- 条件：ReentrantLock 提供了创建多个 Condition 对象的能力，允许线程等待特定条件的变为真。

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

使用 ReentrantLock 和 Condition 可以对线程的锁定和唤醒提供更细粒度的控制，适用于需要复杂同步策略的场景。

## 11.3 并发工具类

### 11.3.1 java.util.concurrent 包概述

`java.util.concurrent` 包为构建并发应用程序提供了健壮、高性能的工具类。该包于 Java 5 引入，并在后续版本中得到了显著增强，包含了一系列同步集合、用于管理线程池的执行器接口、用于原子操作的工具类、同步器等。它的设计通过抽象许多同步的复杂性，显著简化了并发应用程序的开发。

### 11.3.2 并发集合 (ConcurrentHashMap, BlockingQueue)

ConcurrentHashMap：一种 HashMap 的线程安全变体，专为并发设计。它允许并发的读取和更新，而不需要同步。通过分段锁机制，ConcurrentHashMap 实现了高吞吐量和可扩展性。

```java
ConcurrentHashMap<String, String> map = new ConcurrentHashMap<>();
map.put("key", "value");
```

BlockingQueue：表示队列的接口，它额外支持以下操作：在获取元素时等待队列变为非空，在存储元素时等待队列空间可用。ArrayBlockingQueue、LinkedBlockingQueue、PriorityBlockingQueue 和 SynchronousQueue 是其著名的实现类。

```java
BlockingQueue<String> queue = new ArrayBlockingQueue<>(1024);
queue.put("item");
String item = queue.take();
```

### 11.3.3 原子变量和 Atomic 包

`java.util.concurrent.atomic` 包提供了一系列支持在单个变量上无锁线程安全编程的类。原子类（如 AtomicInteger、AtomicLong、AtomicBoolean 和 AtomicReference）提供了原子性更新其值的机制。

```java
AtomicInteger atomicInt = new AtomicInteger(0);
int oldValue = atomicInt.getAndIncrement(); // 原子性递增 1
```

这些类对于计数器、标志位或可以在不需要同步的情况下安全更新的引用特别有用。

### 11.3.4 SynchronousQueue 和 Phaser

SynchronousQueue：一种 BlockingQueue，其中每个插入操作都必须等待另一个线程执行相应的移除操作，反之亦然。同步队列没有任何内部容量，甚至容量为 1 也没有。它适用于你想将数据从一个线程传递给另一个线程的场景。



```java
BlockingQueue<String> syncQueue = new SynchronousQueue<>();
Thread producer = new Thread(() -> syncQueue.put("hello"));
Thread consumer = new Thread(() -> String received = syncQueue.take());
producer.start();
consumer.start();
```

## Phaser

`Phaser`：一种可重用的同步屏障，功能上类似于 `CyclicBarrier` 和 `CountDownLatch`，但更具灵活性。`Phaser` 可以处理注册到它的动态数量参与者（线程），并支持从一个阶段推进另一个阶段。每个阶段编号代表一个 r

```java
Phaser phaser = new Phaser(1); // '1' 用于注册当前线程
int currentPhase;

currentPhase = phaser.arriveAndWaitAdvance();
// 在所有线程到达后在此执行操作
phaser.arriveAndDeregister();
```

`Phaser` 对于一组线程需要定期与彼此进行同步、交换数据或合并来自不同计算阶段结果的场景特别有用。

## 11.4 使用执行器和线程池

### 11.4.1 执行器框架基础

`Executor` 框架是用于在应用程序中显式管理线程的高级替代方案。它通过允许你异步执行任务，在显式线程管理之上提供了一层抽象。主要组件包括：

- `Executor`：表示执行提供的任务对象的接口。
- `Executors`：一个工具类，提供工厂方法来创建常见类型的执行器服务。
- `ExecutorService`：一个执行器，提供了管理终止的方法，以及可以产生 `Future` 以跟踪一个或多个异步任务进度的方法。

#### 简单用法

```java
ExecutorService executor = Executors.newSingleThreadExecutor();
executor.submit(() -> {
    // 要执行的任务
    System.out.println("Asynchronous task");
});
executor.shutdown();
```

### 11.4.2 创建固定大小和缓存线程池

**固定线程池**：具有固定数量线程的线程池。如果没有可用线程处理任务，则任务将放入队列中等待其他任务完成。

```java
ExecutorService fixedThreadPool = Executors.newFixedThreadPool(4);
fixedThreadPool.execute(() -> System.out.println("Task in fixed thread pool"));
```

**缓存线程池**：根据需要创建新线程但重用之前构造的线程的线程池。

```java
ExecutorService cachedThreadPool = Executors.newCachedThreadPool();
cachedThreadPool.execute(() -> System.out.println("Task in cached thread pool"));
```

### 11.4.3 用于任务执行的调度执行器

`ScheduledExecutorService` 允许你在给定的延迟后调度命令或定期执行命令。这对于实现超时、心跳或其他定时行为非常有用。

```java
ScheduledExecutorService scheduler = Executors.newScheduledThreadPool(1);

Runnable task = () -> System.out.println("Task after delay");
ScheduledFuture<?> scheduledFuture = scheduler.schedule(task, 5, TimeUnit.SECONDS);
```

### 11.4.4 通过 ThreadPoolExecutor 定义线程池

如果 `Executors` 类提供的执行器服务不能满足你的需求，可以直接创建并自定义 `ThreadPoolExecutor`。在创建 `ThreadPoolExecutor` 时，你可以指定核心池和最大池大小、空闲存活时间、等待执行任务的阻塞队列，以及用于创建新线程的线程工厂。

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

executor.execute(() -> System.out.println("Task in custom thread pool"));
```

这允许对线程行为、资源分配和任务调度进行精细控制，从而为特定的应用程序需求提供优化性能。

## 高级 OOP 概念

### 12.1 抽象类和方法

#### 12.1.1 抽象简介

抽象是面向对象编程（OOP）中的一个基本概念，旨在隐藏复杂的实现细节，只显示对象的必要特征。它通过允许程序员在更高层次的逻辑上思考来管理复杂性。在 Java 中，可以通过抽象类或接口实现抽象。抽象类可以包含抽象方法（没有体的方法），也可以包含非抽象方法，使其成为在相关类之间共享通用设计的强大工具，同时允许每个类对某些细节有独特的实现。

#### 12.1.2 定义抽象类

Java 中的抽象类使用 `abstract` 关键字声明。它不能被实例化，意味着不能直接从抽象类创建对象。但是，你可以创建继承自抽象类的具体子类的对象。抽象类用于为其他类提供基础模板或架构蓝图。

```java
abstract class Animal {
    abstract void makeSound();

    void eat() {
        System.out.println("This animal eats food.");
    }
}
```

#### 12.1.3 抽象方法及其影响

抽象方法是抽象类中没有方法体的方法。相反，它们仅仅提供了一个方法签名。提供这些方法的具体实现是子类的责任。如果一个类即使包含一个抽象方法，该类也必须声明为抽象类。

类中抽象方法的出现表明，该类旨在作为其他类的蓝图或基类。它强制与子类之间建立一种契约，确保了某些核心方法被实现，从而促进了继承类的统一使用和行为。

```java
class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Bark");
    }
}
```

#### 12.1.4 抽象类的实际用途

抽象类在需要为一组子类定义通用框架的场景中特别有用，它在确保功能一致性的同时，允许在实现上具有灵活性。一些实际用途包括：

- **模板方法**：抽象类可以定义一个带有执行任务的一系列步骤的“模板方法”。子类随后可以定义这些步骤的实际实现。
- **代码复用**：通过声明并可能为常用方法提供默认实现，它们允许重大的代码复用，子类可以直接使用这些方法，或者在需要时重写它们。
- **设计与文档记录**：作为未来开发的蓝图，抽象类有助于记录和强制类层次结构，促进良好的设计实践。

总而言之，抽象类和抽象方法提供了一种结构化的方式来封装相关类之间的共同特征，同时确保了抽象级别，并要求子类实现根据其需求定制的特定功能。

### 12.2 探索接口

#### 12.2.1 接口基础

在 Java 中，接口是一种引用类型，类似于类，但只能包含常量、方法签名、默认方法、静态方法和嵌套类型。接口不能包含实例字段或构造函数。接口中的方法默认是抽象的，这意味着它们没有方法体，必须由选择实现该接口的类来实现。

```java
public interface Animal {
    void eat();
    void sleep();
}
```

接口通过在类中使用 `implements` 关键字来实现。实现接口的类必须为接口中声明的所有抽象方法提供具体的实现。

#### 12.2.2 实现多个接口

Java 通过使用接口支持类型的多重继承。这意味着一个类可以实现多个接口，从而从多个源头继承抽象方法。

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

这种方法允许灵活的设计，而避免了与实现多重继承相关的复杂性和问题。

#### 12.2.3 接口中的默认方法

在 Java 8 中引入的默认方法允许你向已经有实现者的接口中添加新方法，而不会破坏它们的代码。与接口中定义的其他方法不同，默认方法有体且不是抽象的。

```java
public interface Animal {
    void eat();

    default void breathe() {
        System.out.println("Breathing");
    }
}
```

默认方法的引入主要是为了增强 Java 8 中的 Collections API，允许在不影响现有代码的情况下添加新方法。

#### 12.2.4 函数式接口与 Lambda 表达式

Java 中的函数式接口是指恰好包含一个抽象方法的接口。它可以有多个方法，但所有其他方法必须有默认实现或是静态的。这些接口主要用于配合 Lambda 表达式使用，Lambda 表达式提供了一种清晰的方式。

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

### 12.3 深入理解内部类

#### 12.3.1 内部类概览

在 Java 中，内部类是定义在另一个类内部的类。根据用途和声明方式分为不同的类型：成员内部类、局部内部类、匿名内部类和静态嵌套类。内部类允许你根据需要来组织代码。

#### 12.3.2 成员内部类

成员内部类是非静态类，定义在类的相同层级。它可以访问外部类的所有成员，包括私有成员。

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

#### 12.3.3 局部内部类

局部内部类定义在块（通常是方法）内部，可见性仅限于该块。就像局部变量一样，其作用域是限制的。

#### 12.3.4 匿名内部类

匿名内部类没有名称，通常用于现场实例化接口的扩展或抽象类的实现，而无需正式声明子类。

```java
Runnable runnable = new Runnable() {
    @Override
    public void run() {
        System.out.println("Anonymous internal class.");
    }
};
```

#### 12.3.5 静态嵌套类

与其他内部类不同，静态嵌套类不需要创建外部类的实例。它们无法访问实例成员。它们通常用于将类与另一个类关联，且内部类需要在静态上下文中被访问。

### 12.4 理解 static 和 final

#### 12.4.1 static 关键字：变量与方法

`static` 关键字在 Java 中用于指示特定成员（变量或方法）属于类而不是类的实例。这意味着静态成员只有一个副本，并被所有实例共享。

- **静态变量**：也称为类变量，在类中方法之外用 `static` 关键字声明。它们在类加载时初始化。
- **静态方法**：这些方法可以在不创建类实例的情况下调用。静态方法无法直接访问实例变量或方法；必须使用对象引用。

#### 12.4.2 final 关键字：不可变状态

`final` 关键字在 Java 中用于声明常量、防止继承以及防止方法被重写。当应用于变量时，它使变量在初始化后不可更改。

- **final 变量**：这些变量必须在声明时或在构造函数中初始化。一旦赋值，其值就无法改变。

```java
final int finalVariable = 10; // 不能重新赋值
```

#### 12.4.3 静态块与初始化器

**静态块**：静态初始化块用于初始化静态变量。该块只执行一次：类第一次被加载到内存时。

```java
class MyClass {
    static {
        // code to be executed when class is loaded
    }
}
```

**初始化器**：非静态初始化块用于初始化实例变量。这些块在每次创建类的实例时都会执行。

```java
class MyClass {
    {
        // code to be executed when an instance is created
    }
}
```

#### 12.4.4 Final 的类与方法

- **Final 类**：声明为 `final` 的类不能被子类化。这在创建像字符串类这样的不可变类时特别有用。
- **Final 方法**：声明为 `final` 的方法不能被子类重写。这用于防止意外重写方法，因为重写可能会改变类的关键行为。

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

正确使用 `static` 和 `final` 关键字可以显著增强 Java 应用程序的设计和性能，通过促进不可变性、减少开销并保护关键功能免受修改。

## 关于作者

Programming Hub 是一个开创性的平台，它改变了数百万学习者参与编码和计算机科学的方式。Programming Hub 的使命是让所有人都能触及编程，已取得了重要的里程碑，赋予来自不同背景的人探索编程世界的能力。

Programming Hub 拥有超过 500 万次下载，根据超过 18.3 万条评论，在 Play Store 和 App Store 评分均达到 4.7 分，被认为是最好的应用程序之一。它是一个全面的学习伙伴，涵盖了大量的编程语言和主题。从 Python、Java 到 C++ 和 HTML，该应用提供了互动课程、编码挑战和测验，帮助你精进技能。其直观的界面和游戏化的学习方法让掌握编程语言变得有趣且易于学习。Programming Hub 已获得多项奖项，曾被评为 2017 年 Google 编辑选择、2017 年 Google 最佳应用、Google LaunchPad 加速器，并在 Product Hunt 上登顶，获得了 Facebook 的 FB Start 支持。

Programming Hub 为用户提供了 45 多个应用程序，赢得了全球学习者的赞誉。用户赞扬该应用友好型的界面、吸引人的内容和有效的教学方法。所有年龄和技能水平的学习者都发现 Programming Hub 是他们编码之旅中可靠伙伴，点燃了他们对编程的热情并释放了他们的潜力。

Programming Hub 用户经常使用的其他应用包括：

1. Python
2. 数字营销
3. Java
4. 黑客技术
5. 人工智能
6. C++ 编程
7. C 编程
以及更多

各位魔法师们，旅程就此结束，但请记住，这仅仅是开始！请关注并期待这一启迪系列的下一卷，我们将深入探索迷人的编程世界，继续我们的精通之路。冒险远未结束！
