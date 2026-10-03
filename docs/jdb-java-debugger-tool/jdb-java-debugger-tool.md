
# JDB：Java 调试工具

## 关于教程

Java 调试器（通常称为 `jdb`）是一种检测 bug 的有用工具。本教程提供了关于如何在实践中使用它的简要概述。

## 适用群体

本教程对于初学者以及希望在 Java 领域职业发展的专业人士来说都非常有用。

## 前提条件

在开始本教程之前，您需要基础的 Java 知识。

## 1. 引言

Java 调试器（通常称为 `jdb`）是一种检测 bug 的有用工具。本教程提供了关于如何在实践中使用它的简要概述。

### 调试技术

有不同的技术可以调试 Java 程序。旧的调试方法是在每个段落末尾使用打印语句，在控制台上打印轨迹跟踪语句。请看以下代码。

```java
public class Add
{
    public static void main(String ar[])
    {
        int a=ar[0];
        system.out.println("A : " +a);

        int b=ar[1];
        system.out.println("B : " +b);

        int c = a + b;
        system.out.println("C = a + b : " +c);
    }
}
```

在这里，我们有一个计算两个数字并打印输出的程序。注意每一步中，我们都引入了一个打印语句，在控制台上打印程序的状态。这是调试程序的传统方法。

### 2. 安装

### 3. 语法

### 4. 选项

### 5. 会话

- 通过添加类启动会话
- 通过将 JDB 添加到运行中启动会话

### 6. 基本命令

### 7. 断点

### 8. 单步执行

### 9. 异常

### 10. Eclipse 中的 JDB

此外，我们还有可以用于调试程序的高级概念，例如：

- 单步执行 (stepping)
- 断点 (breakpoints)
- 异常或观察点 (exceptions)

### 调试类型

我们可以使用多种方法调试程序：

- 使用 Java 字节码（Java 代码的编译版本）
- 使用程序内部的注释
- 将类挂载到运行中的程序
- 远程调试
- 需需调试
- 优化后的代码调试

### Java 调试器

以下是市面上可用的一些 Java 调试器示例：

- Eclipse、Netbeans 等 IDE 包含它们自带的调试器（Visual cafe, Borland, JBuilder）
- 独立的调试器 GUI（如 Jikes、Java 平台调试器和 JProbe）
- 命令行调试器（Sun 的 `jdb`）
- 记事本或 VI 驱动（堆栈跟踪）

本教程将介绍如何使用命令行调试器 `jdb`。

### JDB

Java 调试器 (JDB) 是一个用于在命令行调试 Java 类的工具。它实现了 Java 平台调试器架构。它通过 Java 调试接口 (JDI) 帮助检测并修复 Java 程序中的错误。

### JDK 中的 JDB

以下架构定义了 JDB 在 JDK 中的角色。它主要包含三个单元：

1. Java 虚拟机工具接口 (JVM TI)
2. Java 调试接线池 (JDWP)
3. Java 调试器接口 (JDI)

JVM TI 是由 VM 实现的本地编程接口。它提供了检查和调试在 VM 上运行的应用状态的方法。它允许实现者（VM 实现者）很容易地封装到调试架构中。它还使用名为 JDWP 的第三方通道进行通信。

### JDWP

它定义了在调试器进程和调试器前端之间传递的信息格式和请求。拥有 Java 调试器 JDWP 的主要目的是允许被调试程序和调试器在不同的 VM 或不同的平台上运行时进行通信。

### JDI

它是一个实现为前端的高级 Java 接口。它定义了用户代码级别的变量信息。建议在所有调试器开发中使用 JDI 层。它使用 JDWP 与被调试的 JVM 通信。

## 2. 安装

本章介绍了如何在 Windows 和 Linux 系统上安装 JDB。JDB 是 JDK 的一部分。因此，只需安装 JDK 即可在命令提示符中使用 JDB。

### 系统要求

以下是安装 JDB 的系统要求：

| 项目 | 数值 |
| :--- | :--- |
| JDK | Java SE 2 JDK 1.5 或更高 |
| 内存 | 1 GB RAM（推荐） |
| 磁盘空间 | 无最低要求 |
| 操作系统版本 | Windows XP 或更高版本，Linux |

按照给出的简单步骤在你的系统上安装 JDB。

### 步骤 1：验证 Java 安装

首先，你需要在系统中安装 Java 软件开发包 (SDK)。要验证这一点，请根据你所工作的平台执行以下两个命令中的任意一个。

如果 Java 安装正确，它将显示 Java 安装的当前版本和规范。下表给出了示例输出：

| 平台 | 命令 | 示例输出 |
| :--- | :--- | :--- |
| Windows | 打开命令控制台并输入：`java -version` | Java version "1.7.0_60"<br>Java (TM) SE Run Time Environment (build 1.7.0_60-b19)<br>Java Hotspot (TM) 64-bit Server VM (build 24.60-b09, mixed) |
| Linux | 打开终端并输入：`java -version` | java version "1.7.0_25"<br>OpenJDK Runtime Environment (rhel-2.3.10.4.elx86_64)<br>OpenJDK 64-Bit Server VM (build 23.7-b01, mixed mode) |

假设本教程的读者系统中已安装 Java SDK 1.7.0_60。如果没有 Java SDK，请从 `http://www.oracle.com/techn/java/javase/downloads.html` 下载并安装。

### 步骤 2：设置 Java 环境

将环境变量 `JAVA_HOME` 指向安装 Java 的目录。例如：

| 平台 | 描述 |
| :--- | :--- |
| Windows | `set JAVA_HOME=C:\ProgramFiles\java\jdk1.7.0_60` |
| Linux | `export JAVA_HOME=/usr/local/java` |

将 Java 编译器的完整路径添加到系统 PATH。

| 平台 | 描述 |
| :--- | :--- |
| Windows | 在 PATH 末尾添加 `C:\Program Files\Java\jdk1.7.0_60\bin` |
| Linux | `export PATH=$PATH:$JAVA_HOME/bin/` |

从命令提示符执行 `java -version` 命令。

### 步骤 3：验证 JDB 安装

按照如下方式验证 JDB 版本：

| 平台 | 命令 | 示例输出 |
| :--- | :--- | :--- |
| Windows | 打开命令控制台并输入：`jdb -version` | This is JDB version 1.6 (Java SE version 1.7.0_60) |
| Linux | 打开终端并输入：`jdb -version` | This is JDB version 1.6 (Java SE version 1.7.0_60) |

## 3. 语法

本章介绍了 `jdb` 命令的语法。语法包含四个部分：

- `jdb`
- `option`
- `class`
- `arguments`

### 语法

`jdb` 的语法如下：

```
jdb [ option ] [ class ] [ arguments ]
```

### JDB

`jdb` 的语法如下：

```
jdb [ option ] [ class ] [ arguments ]
```

### Options

`jdb` 的语法如下：

```
jdb [ option ] [ class ] [ arguments ]
```

### Class

`jdb` 的语法如下：

```
jdb [ option ] [ class ] [ arguments ]
```

### Arguments

`jdb` 的语法如下：

```
jdb [ option ] [ class ] [ arguments ]
```

## 4. 选项

本章介绍了 JDB 中可用的选项。

| 名称 | 描述 |
| :--- | :--- |
| `-help` | 显示帮助信息。 |
| `-sourcepath` | 如果未指定，则对源文件使用给定路径，当前目录。 |
| `-attach` | 将调试器挂载到运行中的 VM。 |
| `-listen` | 等待运行中的 VM 使用标准连接器连接。 |
| `-listenany` | 等待运行中的 VM 使用任何连接器连接。 |
| `-launch` | 立即启动调试程序。 |
| `-listconnectors` | 列出此 VM 中可用的连接器。 |
| `-connect` | 使用命名连接器连接到目标 VM。 |
| `-dbtrace` | 调试 jdb 的信息。 |
| `-tclient` | 在 Java Hotspot VM (客户端) 中运行应用程序。 |
| `-tserver` | 在 Java Hotspot VM (服务器) 中运行应用程序。 |
| `-Joption` | 将选项传递给运行 JDB 的虚拟机。 |

### 使用命令配合选项

以下命令演示了如何使用上述某些选项：

#### -help

以下命令获取使用 JDB 的 `-help` 信息。

```
jdb -help
```

#### -attach

以下命令将调试器挂载到指定的 VM（端口号：1099）。

```
jdb -attach 1099
```

#### -listen

以下命令让运行在当前 VM 上的 JDB 进程等待标准连接器（端口 8008 的 VM）。

```
jdb -listen 8008
```

#### -listenany

以下命令让运行在当前 VM 上的 JDB 进程等待任何连接器（在当前运行端口的 VM）。

```
jdb -listenany
```

#### -tclient

以下命令在 Java Hotspot(™) VM(客户端) 中执行应用程序。

```
jdb -tclient
```

#### -tserver

以下命令在 Java Hotspot(™) VM(服务器) 中执行应用程序。

```
jdb -tserver
```

## 5. 会话

本章介绍了如何以不同的方式启动 JDB 会话。启动 JDB 是启动 JDB 会话的最常用技术。

启动 JDB 会话有两种不同的方式：

- 通过向添加类（主类名）来启动 JDB 会话。
- 将 JDB 添加到运行中的 JVM 以启动会话。

### 通过添加类启动会话

以下命令启动一个 JDB 会话：

#### 语法

```
jdb <classname>
```

#### 示例

假设我们有一个名为 `TestClass` 的类。以下命令从 `TestClass` 启动 JDB 会话。

```
jdb TestClass
```

如果你执行了此命令，它将启动一个带有任何指定参数的新 Java 虚拟机。随后，它会加载该类并在执行类的第一条语句之前停止。

### 通过将 JDB 添加到运行中的 JVM 启动会话

下面是通过将 JDB 添加到运行中的 JVM 来启动 JDB 会话的语法和示例。

#### 语法

以下语法用于 JDB 会话：

```
-agentlib:jdwp=transport=dt_shmem,address=<add>,server=y,suspend=n
```

#### 示例

假设主类名是 `TestClass` 且 JVM 允许后续连接它。以下是将 JDB 添加到 JVM 的命令：

```
-agentlib:jdwp=transport=dt_shmem,address=jdbconn,server=y,suspend=n TestClass
```

现在你可以使用以下命令将 JDB 连接到 JVM：

```
jdb -attach jdbconn
```

**注意：** 在这里，`TestClass` 没有添加到 `jdb` 命令中，因为 JDB 是连接到运行中的虚拟机，而不是启动一个新的虚拟机。

## 6. 基本命令

本章将带你了解 JDB 的基本命令。启动会话后，这些命令用于调试程序。

以下是用于调试的命令列表。

| 名称 | 描述 |
| --- | --- |
| `help` 或 `?` | 最重要的 JDB 命令；它显示已识别的命令列表及其简要描述。 |
| `run` | 在启动 JDB 并设置必要的断点后，你可以使用此命令启动执行并调试应用程序。 |
| `cont` | 在断点、异常或单步后继续执行调试的应用程序。 |
| `print` | 显示 Java 对象和基本类型值。 |
| `dump` | 对于基本类型值，此命令与 `print` 相同。对于对象，它打印对象中定义的每个字段的当前值。包含静态字段和实例字段。 |
| `threads` | 列出当前运行的线程。 |
| `thread` | 选择一个线程作为当前线程。 |
| `where` | 转储当前线程的栈。 |

### 示例

假设我们有一个名为 `Add` 的示例类用于以下示例：

**Add.java**

```java
public class Add
{
    public int addition(int x, int y)
    {
        int z = x+y;
        return z;
    }

    public static void main(String ar[] )
    {
        int a = 5, b = 6;
        Add ob = new Add();
        int c = ob.addition(a,b);
        System.out.println("Add: "+c);
    }
}
```

使用以下命令编译此 `Add.java` 类：

```
javac Add.java
```

### 运行

此命令执行主类文件，该文件已添加到 JDB 用于调试。执行以下命令运行 `Add` 类。

```
jdb Add
initializing jdb ...
> run
```

执行这些命令后，你会看到以下输出：

## 7. 断点

本章介绍了断点的概念以及如何在程序中设置断点。断点可以在调试期间特定代码行显式停止或暂停程序的执行。对于获取程序中的变量非常有用。

### 语法

以下命令在特定行设置断点：

```
stop at <class name>:<Line no>
```

以下命令在特定方法或特定变量上设置断点：

```
stop in <class name>:<Method name | Variable name>
```

### 示例

下面的示例演示了如何在类中设置断点。

```java
public class Add
{
    public int addition(int x, int y)
    {
        int z = x+y;
        return z;
    }
    public static void main(String[] )
    {
        int a = 5, b = 6;
        Add ob = new Add();
        int c = ob.addition(a,b);
        System.out.println("Add: "+c);
    }
}
```

使用以下命令编译上述文件：

```
javac Add.java
```

### 调试

让我们进行调试示例。在 `main()` 上设置断点来开始调试。以下是调试过程中的步骤：

#### 步骤 1：启动 JDB 会话

以下命令在 `Add` 类上启动 JDB 会话：

```
jdb Add
```

#### 步骤 2：设置断点

以下命令在 `Add` 类的 `main()` 方法上设置断点。如果断点设置成功，你会在类加载后看到以下输出：

```
stop in Add.main
```

#### 步骤 3：开始调试

以下命令启动类的执行：

```
run Add
```

如果你运行此命令，你会看到以下输出。在输出中你发现执行停止在断点位置，即 `main()` 函数。

```
C:\Windows\system32\cmd.exe - jdb Add
> run
run Add
Caught java.lang.Breakpoint
Caught java.lang.Breakpoint
Started: "thread-main". Add.main(), line=11 bci=0
11 int a=5, b=6;
```

执行停止在 `main` 方法的第一行，即 `int a=5, b=6;` 或代码中的第 11 行。你可以在输出中观察此信息。

#### 步骤 4：继续执行

以下命令继续程序执行：

```
cont
```

它提供了剩余的执行部分和输出：

```
> Add:11
The application exited
>
```

## 8. 单步执行

本章介绍了如何在调试程序中使用单步概念。单步是一种调试器功能，允许你逐行执行代码。使用此功能，你可以检查代码的每一行以确保其符合预期。

单步过程中使用了以下命令：

- `step`：单步到执行的下一行
- `list`：检查你在代码中的位置
- `cont`：继续剩余的执行

### 示例

以下类使用了上一章中的 `Add` 类：



```java
public class Add
{
    public int addition(int x, int y)
    {
        int z = x+y;
        return z;
    }

    public static void main(String ar[] )
    {
        int a = 5, b = 6;
        Add ob = new Add();
        int c = ob.addition(a,b);
        System.out.println("Add: "+c);
    }
}
```

使用以下命令编译上述文件：

```
javac Add.java
```

假设在 `Add` 类的 `main()` 方法上设置了断点。以下步骤显示如何在 `Add` 类中应用单步。

### 步骤 1：执行任务

以下命令开始执行名为 `Add` 的类。

```
run Add
```

如果你执行此命令，你会看到以下输出。在输出中，你可以发现执行停止在断点位置，即 `main()` 方法。

执行停止在 `main` 方法的第一行，即 `int a=5, b=6;` 或代码中的第 11 行。你可以在输出中观察此信息。

### 步骤 2：单步执行代码

以下命令将执行移动到下一行。

```
main[1] step
```

现在执行单步到第 12 行。你会看到以下输出。

### Java 调试器

```
C:\Windows\system32\cmd.exe
main[1] step
Step completed: "thread-main", Add.main(), line=12 bci=5
  Add ob = new Add();
```

### 步骤 3：列出代码

以下命令列出代码：

```
main[1] list
```

你会得到以下输出。`list` 命令用于让你知道程序控制到达的代码行。注意下面截图中显示程序控制当前位置的箭头标记 `=>`。

```
C:\Windows\system32\cmd.exe
main[1] list
  public static void main(String[] j) {
    int a = 5, b = 6;
    => Add ob = new Add();
    int c = ob.addition(a,b);
    System.out.println("Add:"+c);
  }
```

通常，有三种单步类型：

- 步入 (Step Into)
- 逐行执行 (Step Over)
- 步出 (Step Out)

### 步入 (Step Into)

使用此命令，你可以进入代码的下一行。如果下一行是函数调用，它将通过将控制跳转到函数的顶部来进入函数。

在下面的代码中，箭头标记定义了代码中的控制器。

```java
public class Add
{
    public int addition( int x, int y)
    {
        int z = x+y;
        return z;
    }

    public static void main( String ar[] )
    {
        int a = 5, b = 6;
        -> Add ob = new Add();
        int c = ob.addition(a,b);
        System.out.println("Add: "+c);
    }
}
```

如果你使用步入命令，控制器将移动到下一行，即 `int c = ob.addition(a,b);`。在这一行，有一个函数调用 `addition(int, int)`，因此控制器将移动到带有箭头的 `addition` 函数的最顶部行。

```java
public class Add
{
    public int addition(int x, int y)
    -> {
        int z = x+y;
        return z;
    }

    public static void main(String ar[ ] )
    {
        int a = 5, b = 6;
        Add ob = new Add();
        int c = ob.addition(a,b);
        System.out.println("Add: "+c);
    }
}
```

### 逐行执行 (Step Over)

逐行执行也执行下一行。但如果下一行是函数调用，它会在后台执行该函数并返回结果。

让我们来看一个例子。在下面的代码中，箭头标记定义了代码中的控制。

```java
public class Add
{
    public int addition(int x, int y)
    {
        int z = x+y;
        return z;
    }

    public static void main(String ar[] )
    {
        int a = 5, b = 6;
        Add ob = new Add();
        int c = ob.addition(a,b);
        System.out.println("Add: "+c);
    }
}
```

逐行执行命令将控制移动到下一行，即 `int c = ob.addition(a,b)`。在这一行，有一个函数调用 `addition(int, int)`，因此函数执行在后台完成，结果返回到带有箭头的当前行，如下所示：

```java
public class Add
{
    public int addition(int x, int y)
    {
        int z = x+y;
        return z;
    }

    public static void main(String ar[] )
    {
        int a = 5, b = 6;
        Add ob = new Add();
        -> int c = ob.addition(a,b);
        System.out.println("Add: "+c);
    }
}
```

### 步出 (Step Out)

步出执行下一行。如果下一行是函数调用，它将跳过该调用，函数执行将与代码的剩余行继续。

让我们来看一个例子。在下面的代码中，箭头标记定义了代码中的控制器。

```java
public class Add {
    public int addition(int x, int y) {
        int z = x+y;
        return z;
    }

    public static void main( String ar[] ) {
        int a = 5, b = 6;
        -> Add ob = new Add();
        int c = ob.addition(a,b);
        System.out.println("Add: "+c);
    }
}
```

如果你使用步出命令，控制器将移动到下一行，即 `int c = ob.addition(a,b)`。

```java
public class Add
{
    public int addition( int x, int y)
    {
        int z = x+y;
        return z;
    }

    public static void main( String ar[] )
    {
        int a = 5, b = 6;
        Add ob = new Add();
        int c = ob.addition(a,b);
        System.out.println("Add: "+c);
    }
}
```

## 9. 异常 (Exception)

本章解释了如何使用 JDB 处理异常。通常情况下，当程序在没有 `catch` 语句的情况下产生异常时，VM 会打印异常行并退出。如果带有 `catch` 语句抛出异常，则异常将由 `catch` 语句处理。在使用 JDB 运行类时，它也会抛出未捕获的异常。该异常可以使用 `catch` 命令处理。

### 示例

让我们来看 `dbException` 类的例子：

```java
public class dbException
{
    public static void main(String ar[])
    {
        int a=8, b=0;
        System.out.println("Welcome");
        System.out.println("Ex: "+(a/b));
    }
}
```

使用以下命令编译 `dbException.java`：

```
javac dbException.java
```

按照以下步骤处理异常：

### 步骤 1：运行类

以下命令执行 `dbException` 类：

```
java dbException
run
```

`dbException` 类包含一个异常，因此你会看到以下输出：

### 步骤 2：捕获异常

以下命令捕获异常：

```
catch java.lang.ArithmeticException
```

它将给你以下输出：

```
Set java.lang.ArithmeticException
```

### 步骤 3：继续执行

以下命令继续执行。现在 `catch` 处理算术异常：

```
C:\Windows\system32\cmd.exe
main> cont
Exception in thread "main" java.lang.ArithmeticException: by zero
    at dbException.main(dbException.java:?)
The application exited
C:\Users\Satish Kumar\Desktop\db\>
```

## 10. Eclipse 中的 JDB

本章解释如何在 Eclipse 中使用 JDB。在继续之前，你需要安装 Eclipse。按照以下步骤在你的系统中安装 Eclipse Indigo。

### 步骤 1：下载并安装 Eclipse

你可以从以下链接下载 Eclipse：`https://www.eclipse.org/packages/eclipse-ide-java-developers/indigo`。

### 步骤 2：创建新项目和新类

- 按照 `File -> New -> Java project` 创建一个新的 Java 项目。
- 将其命名为 `sampledebug`。
- 右键点击 `sampledebug` 项目创建一个新类。
- 选择 `new -> class`。
- 将其命名为 `Add.java`。

### Add.java

```java
public class Add
{
    public int addition(int x, int y)
    {
        int z = x+y;
        return z;
    }

    public static void main(String ar[] )
    {
      int a = 5, b = 6;
      Add ob = new Add();
      int c = ob.addition(a,b);
      System.out.println("Add: "+c);
    }
}
```

### 步骤 3：打开调试视图

按照下面的说明打开调试视图。在 Eclipse IDE 中，转到 `Window -> Open perspective -> Debug`。现在你获得了 `Add.java` 程序的调试视图。你会看到以下窗口。

### Java 调试器

### 调试视图中的部分

调试视图中的部分如下：

### 代码部分 (Coding Section)

此部分显示 Java 代码。这是你想要调试的代码，即 `Add.java`。在这里，我们可以通过双击行前方在该行上添加断点。你会发现带有箭头符号的蓝色气泡，指向该行的断点。查看下面的截图；你可以找到用红圈标记为“1”的选中区域。

- 1. 双击可以设置此行断点的地方。

### 断点部分 (Breakpoint Section)

此部分定义了设置在程序代码上的断点列表。在这里我们可以添加、删除、查找和管理断点。下面的截图显示了断点部分。

观察给定截图中的以下选项：

- 1. 使用左侧的复选框，我们可以选择或取消选择断点。在这里，我们使用一个断点，即 `Add` 类的 `main()` 方法。
- 2. 单个交叉图标 `X` 用于删除选定的断点。
- 3. 双重交叉图标 `XX` 用于删除代码中的所有断点。
- 4. 箭头指针用于指向所选断点应用的代码。

### Java 调试器

## 调试章节

本节用于调试过程。它包含了调试时使用的选项。

**开始调试：** 按照下方提供的指令开始调试。

在**代码**上点击右键 -> 选择 **Debug As** -> 点击 **1 Java application**。

调试过程如下截图所示开始。它包含了一些选中的选项，并使用数字进行了高亮显示。

- 用于**恢复**（Resume）调试过程并跳过当前断点。它的作用与 JDB 命令行中的 `cont` 命令类似。
- 用于停止调试过程。
- 它的作用与 JDB 命令行中的 **step in** 过程类似。它被用于将控制权移动到下一行，例如，“1”将移动到下一行。
- 用于查看断点应用在哪一行。

请按照给定的步骤和章节在 Eclipse IDE 中调试您的代码。默认情况下，每个 IDE 都包含此调试过程。
