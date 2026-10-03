
# Will's Elided Java Api 编译器用户指南

![](img/3f127f0d4692a2f206a3e304f384e615_0_0.png)

![](img/3f127f0d4692a2f206a3e304f384e615_1_0.png)

# 前言

为什么还需要另一个 Java 编译器？很简单——为了选项使用的简便性以及错误报告的一致性。

WEJAC 是 `Will's Elided Java Api Compiler` 的缩写。这个名字解释了编译器的用途；核心词是“elided”（精简的），源自“elision”，意为“省略或不予考虑”。WEJAC 省略了通过 Java 编译器 API (JSR 199) 访问的底层 Java 编译器中数量令人眼花缭乱的选项。使用 WEJAC 编译 Java 源代码的选项数量比 `javac` 编译器要简单得多。

WEJAC 在错误报告方面也保持一致。Java 编译器的某些错误（如弃用）需要重新编译——这是另一个编译器选项。WEJAC 始终提供错误报告、行号、位置以及源代码片段，以说明错误原因在整个 Java 源代码中的位置。因此，它包含了错误信息、位置和说明性的原因。

`javac` 编译器有许多选项和功能——而 WEJAC 提供了使用其他 `javac` 编译器选项的选项。但通常，我认为更简单的编译器参数选项集才是。WEJAC 是一个软件开发工程师想要更简单工具的例子，随后对其实现、部署、共享，并在现在——编写了它。

祝编译愉快！

William Gilreath

2019年7月

# 第 1 章 编译器安装

WEJAC 用 Java 编写，并编译为 `.jar` 文件。因此，编译器是使用 Java Compiler API 使用其所编译的编程语言进行“自举”的。因此，任何平台（Windows/Linux/macOS）都可以下载、安装、配置和使用 WEJAC。

WEJAC 由作为 JAR 文件的二进制字节码执行文件（Java 归档文件）以及一个包装“启动”脚本或批处理文件组成，后者在 Java 虚拟机 (JVM) 上执行 JAR 文件，并将命令行参数传递给 Java 虚拟机。

## 安装前步骤

### 1. 检查 OpenJDK

为了使用 WEJAC 编译器，系统必须先安装 OpenJDK。不同的供应商提供了许多 OpenJDK 下载。最简单的方法是打开控制台或终端窗口，输入以下命令：

```bash
$ java -version
```

如果已安装 OpenJDK，将显示如下：

```bash
$ java -version
openjdk version "12.0.x" ...
OpenJDK Runtime Environment ...
```

如果没有安装，则需要安装 JDK。WEJAC 运行环境版本大于或等于 7。

### 2. 下载 WEJAC 包

WEJAC 软件包从 GitHub 下载。下载地址如下：

https://github.com/wilreath

### 3. 解压 WEJAC 包

使用你喜欢的 ZIP 工具解压 WEJAC 软件包。

## 安装步骤

WEJAC 提供了使用其他 `javac` 编译器选项的选项，但通常情况下，我认为更简单的参数选项集是最好的。WEJAC 是一个软件开发工程师想要更简单工具的例子，随后对其实现、部署、共享，并在现在——编写了它。

### 1. 安装启动脚本

在终端或控制台中，执行以下命令来安装 WEJAC：

```bash
chmod +x wejac
sudo mv wejac /usr/local/bin/
```

### 2. 安装 JAR 文件

将 `wejac.jar` 移动到合适的目录：

```bash
sudo cp wejac.jar /usr/local/lib/
```

### 3. 配置环境变量

为了在任何地方运行 WEJAC，可以将其添加到你的 `.bashrc` 或 `.zshrc`：

```bash
export PATH=$PATH:/usr/local/bin
```

## 安装后步骤

1. 验证安装是否成功。

在终端或控制台中运行帮助信息：

```bash
wejac help
```

2. 编译简单的 Java 源代码。使用你喜欢的文本编辑器编写 Java 源代码：

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!!!");
        System.exit(0);
    }
}
```

在终端或控制台中，编译 `HelloWorld.java`：

```bash
wejac HelloWorld.java
```

使用 `-echo` 选项确认 WEJAC 编译器成功编译：

```bash
wejac -echo HelloWorld.java
```

编译 `HelloWorld.java` 的结果是：成功。

3. 贡献代码。WEJAC 是开源的，充满动力且好奇的软件开发者都可以做出贡献。与其他分享你使用 WEJAC 编译器的经验。

# 第 2 章 编译器参数

WEJAC 设计为为编译 Java 源代码提供更少的命令行选项。这些选项被分为不同的种类。总体而言，WEJAC 只有九个选项。

## 参数种类

WEJAC 有四种选项：

- 编译
- 错误报告
- 帮助或信息
- javac

### 编译

编译选项用于编译 Java 源代码。编译器选项有：

- `-echo` 打印 Java 编译器选项以及成功或失败结果。
- `-final` 编译不带调试信息的最终发布版本。
- `-time` 打印编译源文件的总耗时。

### 错误报告

编译 Java 源代码时的错误报告选项。错误报告选项有：

- `-brief` 仅打印编译消息的简要计数。
- `-hush` 禁用错误以外的所有编译消息。
- `-mute` 禁用所有编译消息。

### 帮助或信息

获取 WEJAC Java 编译器的帮助或信息的选项。有两个选项，但参数不同：

- `-help` 打印选项列表并退出。
- `-info` 打印编译器版本信息并退出。

### javac 参数

`-javac` 选项指定后续参数是标准的 Java 编译器选项，它将原样传递给 WEJAC 编译器。这允许在无需检查或向 WEJAC 添加 `javac` 选项的情况下灵活使用 `javac` 编译器选项。

# 第 3 章 编译器选项

本章包含了所有 WEJAC 编译器选项的列表，并附有简短示例以说明这些编译器选项在实践中的作用。

## brief

`-brief` 编译器选项用于指定错误诊断信息的简要摘要或数量。

```bash
wejac -brief HelloWorld.java
1 Diagnostic messages:
1 Error
```

## echo

`-echo` 编译器选项指定编译器“回显”传递的 `javac` 编译器参数以及 Java 源文件的编译最终结果。

当使用 `-echo` 选项通过 WEJAC 编译器编译 `HelloWorld.java` 时：

```bash
wejac -echo HelloWorld.java

Java Compile Options: [-g]

Compiler result for file: 'HelloWorld.java' is: Success.
```

当使用 `-echo` 选项通过 WEJAC 编译器编译 `HelloWorldBad.java` 时：

```bash
$ wejac -echo HelloWorldBad.java

Java Compile Options: [-g]

Error: HelloWorldBad.java.
Line 4 At 24: unclosed string literal
System.out.println("Hello, World!!!");

Compiler result for file: 'HelloWorldBad.java' is: Failure!
```

## final

`-final` 编译器选项指定对 Java 源文件进行非调试的最终发布版本编译。使用 `-echo` 选项时会显示 `javac` 编译器参数。

当使用 `-final` 选项通过 WEJAC 编译器编译 `HelloWorld.java` 时：

```bash
$ wejac -echo -final HelloWorld.java

Java Compile Options: [-g:none]

Compiler result for file: 'HelloWorld.java' is Success.
```

## help

`-help` 编译器选项会打印 WEJAC Java 编译器各种命令行选项的帮助信息，并退出不进行编译。

```bash
$ wejac -help
Usage: wejac (option)* [ -javac (javac-options)+ ] (java-file)+ | ( -help |info )
WEJAC OPTIONS:
Compiler Options: [ -echo ] | [ -final ] | [ -time ]
-echo 打印 Java 编译器选项以及成功或失败。
-final 编译不带调试信息的最终发布版本。
-time 打印编译源文件的总耗时。

Error Reporting Option: [ -brief | -hush | -mute ]

-brief 仅打印编译信息的简要摘要。
-hush 禁用错误之外的所有编译信息。
-mute 禁用所有编译信息。

Help or Version: [ -help | ? ] | ( -info | -v )

-help 打印编译器选项列表并退出。
-info 打印编译器版本信息并退出。

注意：所有 -javac 选项都会原样传递给编译器。
```

## hush

`-hush` 编译器选项会“静音”所有的编译器诊断信息，编译器错误除外。

其他编译器诊断如警告、备注和强制警告将被抑制。

当使用 WEJAC 编译器编译 `Unchecked.java` 时，它会生成一个弃用警告：

```bash
$ wejac Unchecked.java
Error: Unchecked.java.
Unchecked.java uses or overrides a deprecated API.

Error: Unchecked.java.
Recompile with -Xlint:deprecation for details.
```

当使用 `-hush` 选项并通过 WEJAC 编译器编译 `Unchecked.java` 时，将没有警告：

```bash
$ wejac -hush Unchecked.java
$
```

## info

`-info` 编译器选项提供关于编译器的信息——例如发布版本、版本、版权和软件许可。

```bash
$ wejac -info
```

## javac

`-javac` 编译器选项允许将 Java 编译器选项传递给底层的 Java 编译器。

当使用 WEJAC 编译器编译 `Unchecked.java` 时，会生成一个弃用警告：

```bash
$ wejac Unchecked.java
Error: Unchecked.java.
Unchecked.java uses or overrides a deprecated API.

Error: Unchecked.java.
Recompile with -Xlint:deprecation for details.
```

当使用 WEJAC 编译器编译 `Unchecked.java` 并使用 `-javac -Xlint:deprecation` 选项时，会给出弃用警告的详细信息：

```bash
$ wejac -javac -Xlint:deprecation Unchecked.java
Error: Unchecked.java.
Line 29 At 18: [deprecation] Date(int,int,int) in java.util.Date has been deprecated
      Date d = new Date(86, 04, 05);      // May 5, 1986
                               ^
```

## mute

`-mute` 编译器选项会抑制或“静音”WEJAC 编译器的所有编译器诊断信息。当使用 `-mute` 选项编译 `HelloWorldBad.java` 时：

```bash
$ wejac -mute HelloWorldBad.java
$
```

## time

`-time` 编译器选项提供使用 WEJAC 编译器编译 Java 源文件的总时间（毫秒级）。当使用 `-time` 选项编译 `HelloWorld.java` 时：

```bash
$ wejac -time HelloWorld.java
Time: 409-ms for: HelloWorld.java
$
```

## 多重编译器选项

WEJAC 编译器允许混合使用编译器选项，但只能使用一种错误报告选项。考虑使用 `-echo -time` 选项通过 WEJAC 编译器编译 `HelloWorld.java`：

```bash
$ wejac -echo -time HelloWorld.java

Java Compile Options: [-g]

Time: 411-ms for: HelloWorld.java
Compiler result for file: 'HelloWorld.java' is: Success.
$
```

# 结语

WEJAC 的作者和创建者欢迎用户的意见、问题、错误报告和想法。请随时通过电子邮件（`wfgilreath@yahoo.com`）主题写“WEJAC”与我们联系。

# 后记

封面上的可爱动物是一只“Weajack”，Weajack（或更常被称为 Fisher）是一种原产于北美洲的小型哺乳动物。

# 作者

WEJAC 编译器由 Will 或 William F. Gilreath 创建并开发。Will 是一位软件开发工程师、计算机科学家、数学家、作家和诗人。Will 在孩提时期使用 Sinclair ZX-81 时就开始编写 64 C-BASIC 代码，随后转向 Commodore 64 C-BASIC，并在后来的在 Tandy 1000EX 上使用 GW-BASIC。Java 是他喜爱的编程语言，Will 想要一个更简单的编译器——因此有了 WEJAC。

访问 Will 的个人主页：

https://gilreath.github.io/WillHome.html

# 贡献

WEJAC 是 `javac` 编译器 API 的开源前端。因此，如果读者想为 WEJAC 贡献并参与——我们非常欢迎！鼓励测试用例、错误修复以及对 WEJAC 源代码的贡献。
