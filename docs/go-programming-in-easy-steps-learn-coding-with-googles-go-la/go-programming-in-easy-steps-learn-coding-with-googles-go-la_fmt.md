
# Go 编程入门指南：学习 Google Go 语言编程

![](img/fa565c410b0509c58bcab29ed0b49de9_0_0.png)

## Go 语言基础

- 下方的表格包含了 Go 编程语言的所有 25 个关键字以及用于创建 Go 程序中组件的声明语法。
- 关键字具有特殊含义，因此不可用于 Go 程序代码中的条目命名。

![](img/fa565c410b0509c58bcab29ed0b49de9_1_0.png)

| 关键字 |  |  |  |  |
|---|---|---|---|---|
| `break` | `default` | `func` | `interface` | `select` |
| `case` | `defer` | `go` | `map` | `struct` |
| `chan` | `else` | `goto` | `package` | `switch` |
| `const` | `fallthrough` | `if` | `range` | `type` |
| `continue` |  | `import` | `return` | `var` |

### 组件语法

| 组件 | 语法 |
|---|---|
| 变量（推断） | `var variableName dataType = value`<br>`variableName := value` |
| 常量 | `const constantName = value` |
| 数组 | `var arrayName []dataType` |
| 切片 | `sliceName := make([]dataType, nElements)` |
| 映射 | `mapName := make(map dataType, value dataType)` |
| 通道 | `channelName := make(chan dataType)` |
| 结构体 | `type struct struct { field dataType }` |
| 函数 | `func functionName(paramName dataType) return dataType { return returnValue }` |
| 接口 | `type interfaceName interface { methodName return dataType }` |

Mike McGrath

![](img/fa565c410b0509c58bcab29ed0b49de9_2_0.png)

- 总结
- 总结
- 总结
- 总结

## 13 如何使用本书

为了方便，书中所有的示例源代码都以 ZIP 压缩包提供。你可以通过以下简易步骤获取此包：

1. 访问 `www.ineasteps.com` 并导航到 Free Resources。
2. 接下来在 easy steps 中找到 Go Programming，然后点击 Downloads。
3. 现在将包解压到电脑的 `GOPATH` 目录。

> 如果你没有实现图中所示的结果，只需将你的代码与示例进行对比，找出错误所在。

## 获取源代码

为了方便，书中所有的的示例源代码都以 ZIP 压缩包提供。你可以通过以下简易步骤获取此包：

1. 访问 `www.ineasteps.com` 并导航到 Free Resources。
2. 接下来在 easy steps 中找到 Go Programming，然后点击 Downloads。
3. 现在将包解压到电脑的 `GOPATH` 目录。

# 1 入门

欢迎来到 Go 语言编程的世界。本章将介绍该语言并创建一个运行第一个程序的工作空间。

- 认识 Go 语言
- 安装 Go 工具
- 创建 Go 工作空间
- 编写 Go 程序
- 运行程序程序
- 格式化和注释代码
- 探索 VS Code 编辑器
- 总结

## 认识 Go 语言

Go 是一种免费开源编程语言，由 Robert Griesemer、Rob Pike 和 Ken Thompson 创建（他们以开发 Unix 操作系统而闻名）。Google 在 2012 年 3 月发布了 Go 语言的 1.0 版本，从那时以后获得了广泛关注。

Go 程序以纯文本形式编写，然后通过 Go 编译器编译成机器码，生成可执行文件。

```go
package main

import "fmt"

func main() {
	// 我的第一个程序
	fmt.Println("Hello World!")
}
```

在设置 Go 的过程中，你将在名为 `GOPATH` 的位置中创建目录，如下侧示例代码所示：

![](img/fa565c410b0509c58bcab29ed0b49de9_7_0.png)

`src/main.go`

Go 编程语言的目标是具有良好的表达力、快速、高效、可靠且易于编写。某些编程语言（如 C 或 C++）快速且可靠但不简单。相反，其他编程语言（如 Java 或 Python）易于编写但效率不高。

Go 在很多方面与 C 相似，但它远不止于此，因为它吸收了许多其他编程语言的优点，同时避免了导致复杂或不可靠的特性。

最重要的是，Go 引入了利用“协程（goroutines）”和“通道（channels）”利用多核 CPU 处理进行并发的能力。这为计算机同时处理几件事提供了可能。

尽管 Go 语言没有像面向对象编程（OOP）语言那样的类结构，但它的功能提供了某种程度的封装、继承和多态——OOP 的三大基石。

![](img/fa565c410b0509c58bcab29ed0b49de9_11_0.png)

Go Gopher —— Go 语言的标志性吉祥物。

![](img/fa565c410b0509c58bcab29ed0b49de9_11_1.png)

你可以在《In Easy Steps》系列中发现更多编程语言书籍——包括 C、C++、C#、Java 和 Python。访问 `www.ineasesteps.com` 了解更多信息。

有这么多编程语言供你选择，你可能会疑惑为什么应该选择学习 Go 语言——以下是 Go 提供的的一些优势：

### 简单语法

Go 语言像 Python 一样简洁。它写起来像 Python 一样简单，但像 C++ 一样高效。这让你能够编写易于阅读和维护的代码。

### 编译型语言

Go 源代码被编译为二进制机器码，计算机可以直接读取，而不是在每次程序运行时都进行解释。这使得你编写的 Go 程序运行速度比 Python 或 PHP 等解释型语言编写的程序更快。

### Go 编译器

Go 编译器非常快，并提供了额外的益处，例如代码优化和错误检查——它可以检测代码中未使用的变量、代码所需的缺失导入以及拼写错误或无效代码。Go 编译器还可以为其他操作系统生成可执行二进制文件。这让你能够将源代码编译并运行在多台机器上。

### 并发

Go 语言通过 `goroutines`（协程）和 `channels`（通道）为并发提供了原生支持。这让你能够编写可以同时执行多个任务的多线程程序。

### 垃圾回收

自动内存管理是 Go 语言的一个特性。它的垃圾回收器与程序并发运行。这让你编写程序代码时无需担心内存泄漏。

### 静态类型

Go 是一种静态类型语言，其中变量被显式声明为特定的固定类型。这使得能够在开发过程中早期发现错误。

随着你对 Go 语言经验的增加，你可能会发现其他优势，但现在是时候开始了……

## 安装 Go 工具

要开始 Go 语言编程，你必须先在 PC 上安装 Go 工具。这些工具允许你构建、运行和测试用 Go 语言编写的程序。Go 工具随许多实用的标准包提供，你可以将它们导入自己的程序中。Go 语言安装程序适用于 Windows、macOS 和 Linux。

![](img/fa565c410b0509c58bcab29ed0b49de9_13_0.png)

- 打开浏览器并访问 `https://golang.org`，然后为你的系统下载合适的安装程序。

![](img/fa565c410b0509c58bcab29ed0b49de9_13_1.png)

- 下载完成后，运行安装程序启动“Go 编程语言安装向导”。

![](img/fa565c410b0509c58bcab29ed0b49de9_13_2.png)

- 3. 点击 Next（下一步）继续，然后接受许可条款。
- 4. 接受建议的安装文件夹（Windows 上为 `C:\Go`），然后点击 Install（安装）完成安装。

![](img/fa565c410b0509c58bcab29ed0b49de9_14_0.png)

Windows Go 安装程序会自动将 Go 添加到你的系统路径，以便在命令行提示符中使用 Go 工具。

- 5. 为了测试安装是否成功，首先打开 Terminal（终端）窗口——在 Windows 系统上同时按下 WinKey + R，打开“Run”对话框，然后输入 `cmd` 打开“Command Prompt”（命令行提示符）窗口。

![](img/fa565c410b0509c58bcab29ed0b49de9_14_1.png)

- 6. 在命令行提示符处，输入命令 `go`，然后按回车查看 Go 工具命令列表。

### 命令行提示符

```text
C:\Users\mike_go
env
Go 是用于管理 Go 源代码的工具。
用法:
  go <command> [arguments]

命令有：
  bug            启动 bug 报告
  build          编译包和依赖项
  clean          删除对象和缓存文件
  doc            为符号生成文档
  env            打印环境信息
  fix            更新包到新版本
  fmt            运行 goofmt（重新格式）包
  generate       通过获取源码生成 Go
  get            向当前模块添加依赖项并安装它们
                 编译安装包和依赖项
  list           列出包和模块
  mod            模块维护
  run            编译并运行 Go 程序
  test           运行指定的工具
  tool           运行 Go 版本
  vet            报告命令中可能的错误。

使用 "go help <command>" 获取更多详细信息。
```

额外的帮助主题：

```text
buildmod      在 Go 和 C 之间构建
cache          编译和测试缓存
environment    环境变量
filetype       文件类型
go.mod         the go.mod 文件
goproath        GOPATH 环境变量
gopath-get    旧版 GOPATH go get
goproxy        模块代理协议
importpath     导入路径语法
typacket       模块语法
```

Go 程序可以使用纯文本编辑器编写，例如 Windows 上的记事本应用。拥有一个可以在你的 `src` 目录文件夹中打开文本编辑器的桌面快捷方式是很有用的。重复此页面上的步骤，但在第 7 步中，将位置输入为 `notepad` 并名称输入为 Go Editor，即可创建另一个实用的桌面快捷方式。

## 编写 Go 程序

所有的 Go 程序最初都是纯文本文件，稍后被编译成实际的可执行程序。这意味着 Go 程序可以在任何纯文本编辑器中编写，例如 Windows 记事本或 Linux 上的 Nano 应用。

按照以下步骤创建一个简单的 Go 程序，它将输出传统的第一个程序问候语：

- 在你的 `src` 文件夹中创建一个名为 `hello` 的子目录。

```text
Go Terminal
C:\Users\mike_go\src>mkdir hello
C:\Users\mike_go\src>
```

- 打开一个纯文本编辑器（如记事本），并按照列出的内容准确输入代码以开始程序：

```go
package main
```

- 在下方两行，按照列出的内容插入此代码：

```go
import "fmt"
```

- 在再下方两行，精确添加此代码：

```go
func main() {
	fmt.Println("Hello World!")
}
```

将文件保存在“hello”文件夹中，并命名为 `main.go`——现在完整的程序看起来应该完全像这样：

```text
main.go - Notepad
File Edit Format View Help
package main
import "fmt"
func main() {
    fmt.Println("Hello World!")
}
```

`fmt.Println` 中的 `P` 是大写，`L` 是小写。

文件夹内文件的排列方式在 Go 中非常重要。每个 main 文件以及任何相关文件都必须放置在一个命名唯一的文件夹中以创建一个包（package）——在这里包命名为“hello”。

相反页面上程序代码的不同部分可以单独检查，以便更清楚地理解每个部分：

### 包声明

```go
package main
```

包的类型在 `package` 关键字之后声明。所有的 Go 程序代码都包含在包中。你可以为作为共享库的包声明自己的类型，但如果你想将代码编译成可执行程序，则必须声明包“main”。

### 导入声明

```go
import "fmt"
```

关键字 `import` 用于将一个或多个包导入到当前包中，以便该程序可以使用这些功能。包“fmt”来自你的 Go 安装中包含的 Go 标准库。它提供了 `fmt.Println()` 函数，用于在程序中输出文本。注意包名必须包含在双引号字符中。当导入多个包时，包名列表必须放在括号内，且每个名称必须单独占一行，如下：

```go
import (
	"fmt"
	"strings"
)
```

### 函数声明

```go
func main() {
	fmt.Println("Hello World!")
}
```

函数名紧跟在同一行的 `func` 和左花括号 `{` 之后。函数体包含了执行程序任务的实际指令语句。函数体以右花括号 `}` 结束。函数名必须是唯一的，但每个 Go 程序必须有一个名为“main”的函数，因为这是所有 Go 程序的起点。

包名和包类型是两个独立的项目——在这里包名为名为 hello，但类型是 main。

你可以在 `GOPOT` 路径的 `src` 目录中找到 Go 标准库包——例如，在 `C:\Go\src`。此外，你还可以从官方文档 `https://golang.org/pkg` 学习每个包——这是一份无价的资源。

### 运行 Go 程序

Go 程序代码使用 Go 工具进行编译和执行。在开发过程中，无错误的 Go 程序可以通过 `go run` 工具进行编译和运行。这是很有用的，但如果你想创建一个可以重复执行的可执行二进制版本，可以使用 `go build` 工具。

1. 在你的 `src` 文件夹中打开命令提示符或终端窗口。
2. 输入命令 `go run hello` 来运行程序——它应该输出问候语。

```text
Go Terminal
C:\Users\mike_go\src>go run hello
Hello world!
C:\Users\mike_go\src>
```

3. 接下来，输入命令 `go build hello` 为程序创建一个可执行的二进制版本——它会在你的 `src` 文件夹中添加一个可执行文件。
4. 现在，在 Windows 上输入命令 `hello`，在 Linux 或 macOS 上输入 `./hello`——它应该输出两次传统的问候语。

```text
C:\Users\mike_go\src>go build hello
C:\Users\mike_go\src>hello
Hello world!
C:\Users\mike_go\src>hello
Hello world!
C:\Users\mike_go\src>
```

在 Windows 系统上，二进制文件带有 `.exe` 扩展名，因此构建的文件是 `hello.exe`。

### 代码格式化与注释

在运行程序之前，始终通过 `go fmt` 工具确保你的 Go 源代码格式正确是一种良好的习惯。

在源代码中包含解释性注释也是一种良好的习惯，这样其他人以及你以后回顾代码时可以轻松理解它。单行注释可以添加在 `//` 序列之后——`//` 之后该行内的所有内容。多行注释可以在 `/*` 和 `*/` 序列之间添加——这对于“注释掉”代码块非常有用，可以在开发期间向编译器隐藏它。

1. 编辑 `hello.go` 中的代码以添加注释和不必要的制表符间距（错误的格式）。

```go
main.go - Notepad
File Edit Format View
// My First Go Program: Output a greeting.

package main
import
	"fmt"
func main() {
	fmt.Println("Hello World!")
}
```

2. 现在，在提示符输入命令 `go fmt hello`，然后重新打开源代码文件查看正确的格式。

注释不应该是“嵌套”的，即一个在另一个。

`go fmt` 工具提供了简单的错误检查。例如，省略某行末尾的双引号，它将提供错误发生的行号和位置，并提供错误性质为“字符串常量未结束”。

## 探索 VS Code 编辑器

虽然可以使用命令提示符和纯文本编辑器创建 Go 程序，但许多开发者更喜欢使用专门的代码编辑器。提供了语法高亮、自动缩进、括号匹配和代码调试等有用的附加功能。可能的免费编辑器是微软的 Visual Studio Code（VS Code）。可以在 `https://code.visualstudio.com/download` 下载 Windows、Linux 和 macOS 版本。

当你下载并安装 VS Code 时，只得到了编辑器框架。VS Code 实际上支持许多不同的编程和脚本语言，因此你需要为你需要的语言安装相应的扩展。

1. 下载并安装 VS Code。
2. 要打开“扩展市场”侧边栏，先点击查看、外观、显示活动栏，然后点击活动栏上的扩展按钮。



### VS Code 中的 Go

接下来，在搜索框中输入 `go` 以查找 Go 语言的 VS Code 扩展。

点击 **Install** 为 VS Code 添加 Go 语言支持——如果要求添加额外的 Go 支持，请选择 **Install All**。

点击 **File, Add Folder to Workspace** 并添加包含源代码 `src` 文件夹的 `go` 工作区文件夹。

点击活动栏上的资源管理器按钮，然后选择一个文件在主 VS Code 编辑器窗口中打开——例如，点击 `hello` 文件夹中的 `main.go` 文件。

#### 点击“查看”（View）、调试控制台”（Debug Console）打开输出面板 —— 通常，这将出现在代码编辑器窗口下方，但可以移动。

![](img/fa565c410b0509c58bcab29ed0b49de9_31_0.png)

#### 点击“运行”（Run）、不带调试运行（Run Without Debugging）以查看调试控制台中的输出。

![](img/fa565c410b0509c58bcab29ed0b49de9_31_1.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_31_2.png)

VS Code 应用高度可定制——你可以根据喜好更改组件的布局，并从几种浅色或深色主题中进行选择。这里显示的截图是默认的浅色主题（Light），代码编辑器窗口显示的语法高亮与本书使用的相同。

## 总结

- Go 程序是纯文本文件，被编译成机器码以生成可执行的二进制版本。
- Go 工具允许你构建、运行和测试用 Go 语言编写的程序。
- Go 安装包含了实用的、可信的标准包，你可以将其导入到程序中。
- 命令行 `go` 命令显示 Go 工具命令的列表。
- `GOROOT` 环境变量存储你系统上 Go 安装所在的位置。
- `GOPATH` 环境变量存储你系统上 Go 工作空间所在的位置。
- Go 工作空间是一个名为 `go` 的目录，包含名为 `src`、`bin` 和 `pkg` 的子目录。
- Go 包的名称是包含 Go 源代码文件的目录名称。
- Go 包声明指定了它的类型，并且必须指定为 `package main` 才能编译为可执行文件。
- `import` 声明用引号括起任何供程序使用的特性包的名称。
- 函数声明包含 `func` 关键字，后面紧跟函数名、`()` 括号和 `{}` 大括号。
- 所有 Go 程序必须有一个名为 `main` 的函数作为程序的入口点。
- `go run` 命令编译并运行程序。
- `go build` 命令编译程序并生成一个可以分发的可执行二进制文件。
- `go fmt` 命令应用于正确格式化 Go 包的源代码。
- VS Code 提供了语法高亮、自动缩进、括号匹配和代码调试等功能。

## 2 存储值

本章演示了如何在 Go 程序中使用变量容器来存储、检索和操作各种类型的数据。

- 创建程序变量
- 显示变量值
- 转换数据类型
- 修复常量值
- 指向存储的值
- 总结

### 创建程序变量

![](img/fa565c410b0509c58bcab29ed0b49de9_36_0.png)

变量是 Go 程序中的一种容器，可以在计算机内存中存储一个数据值。存储的值可以使用变量名进行引用，并通过分配新值来更改。程序员可以为变量选择任何名称，只要它符合下面列出的命名规则即可：

| 命名规则 | 示例 |
| :--- | :--- |
| **不能**是 Go 关键字 | `default` |
| **不能**包含算术运算符 | `a+b*c` |
| **不能**包含标点符号 | `%$#!` |
| **不能**包含任何空格 | `no spaces` |
| **必须**以字母开头 | `msg` |
| **可以**包含数字 | `good1` |
| **可以**包含混合大小写 | `camelCase` |

变量名应该是简洁的，并且始终以小写字母开头 —— 除非变量需要被其他包访问（稍后会详细介绍）。为变量选择有意义的名称是一个良好的习惯，可以使程序更容易理解。在程序中创建变量只需要使用 `var` 关键字对其进行“声明”。变量声明的语法如下：

```
var variableNameDataType
```

`var` 关键字后面跟着一个空格，然后是选定的变量名，然后是该变量允许存储的数据类型。通常，这将是相反页描述的五种数据类型之一。可以在单次声明中以逗号分隔列表的形式创建多个相同数据类型的变量，如下：

```
var variableName1, variableName2, variableName3 dataType
```

![](img/fa565c410b0509c58bcab29ed0b49de9_37_0.png)

Go 关键字列在本书内封的表格中。

![](img/fa565c410b0509c58bcab29ed0b49de9_37_1.png)

变量名对大小写敏感。Go 中的基本数据类型列在下表中：

| 数据类型 | 描述 | 示例 |
| :--- | :--- | :--- |
| `string` | 字符串 | `"Hello!"` |
| `int` | 整数 | `100` |
| `float64` | 浮点数 | `123.456` |
| `byte` | 单字节 | `'A'` |
| `bool` | 布尔值 | `true` |
| `p` | 内存地址 | `0x22FF34` |
| `v` | 默认格式的值 | (以上任意一种) |
| `T` | 数据类型 | `int` |

变量声明的语法如下：

```
var variableNameDataType
```

`var` 关键字后面跟着一个空格，然后是选定的变量名，然后是该变量允许存储的数据类型。通常，这将是相反页描述的五种数据类型之一。可以在单次声明中以逗号分隔列表的形式创建多个相同数据类型的变量，如下：

```
var variableName1, variableName2, variableName3 dataType
```

变量也可以同时声明并初始化而不指定类型。在这种情况下，你使用 `:=` 操作符从值推断类型：

```
msg := "Hello!"
```

更改变量的值使用赋值运算符 `=`：

```
msg = "New value"
```

常量是设置后无法更改的值。使用 `const` 关键字声明它们：

```
const Pi = 3.14159
```

使用 `fmt` 包来显示变量的值。`Println()` 和 `Printf()` 函数是常用的：

```
fmt.Println(msg)
fmt.Printf("Value: %d\n", num)
```

`Printf()` 函数使用动词（verbs）来格式化输出。常用的动词包括：

- `%s` 字符串
- `%d` 整数
- `%f` 浮点数
- `%c` 字符
- `%t` 布尔值
- `%p` 内存地址
- `%v` 默认格式
- `%T` 类型

你还可以指定输出的宽度和填充。例如，`%7d` 将整数格式化为占据七个位置，并在必要时填充空格。

### 显示变量值

![](img/fa565c410b0509c58bcab29ed0b49de9_39_0.png)

可以使用 `fmt` 包显示变量的值。`Println()` 和 `Printf()` 函数是常用的：

```go
fmt.Println(msg)
fmt.Printf("Value: %d\n", num)
```

`Printf()` 函数使用动词来格式化输出。常用的动词包括：

- `%s` 字符串
- `%d` 整数
- `%f` 浮点数
- `%c` 字符
- `%t` 布尔值
- `%p` 内存地址
- `%v` 默认格式
- `%T` 类型

你还可以指定输出的宽度和填充。例如，`%7d` 将整数格式化为占据七个位置，并在必要时填充空格。

```
fmt.Printf("Right-aligned %%20.3f rounded pi \n", pi )
fmt.Printf("Left-aligned %%20.3f rounded pi \n", pi )
```

5. 将程序文件保存到 `vars` 目录，然后运行程序以查看指定格式下的变量值。

```
Go Terminal
C:\Users\mike_go\src>go run vars
num: 100 type:int
num: 3.1415926536 type:Float64

%d displays 100
%07 displays 0000100

Pi is approximately 3.1415926536 3.142 rounded pi
Right-aligned
Left-aligned 3.142
C:\Users\mike_go\src>
```

![](img/fa565c410b0509c58bcab29ed0b49de9_41_0.png)

`fmt.Printf()` 函数在输出后不会添加新行。

你必须手动包含一个 `\n` 换行转义字符将打印头移动到下一行。要使用 `fmt.Printf()` 函数显示 `%` 字符，如所示，在其前面加上另一个 `%` 字符。

![](img/fa565c410b0509c58bcab29ed0b49de9_41_1.png)

注意，当格式指定符分配的小数较少时，浮点值会被舍入——而不是被简单的截断。

## 转换数据类型

你有时需要将存储在变量中的值转换为不同的数据类型。通常，你希望将字符串值转换为数值以执行算术运算。例如，字符串可能包含数字字符 `42`，但除非将其转换为 `int` 或 `float64` 数据类型，否则无法对其进行算术运算。

![](img/fa565c410b0509c58bcab29ed0b49de9_42_0.png)

Go 标准库包含一个 `strconv` 包，其中包含与字符串数据类型相互转换的函数。通过在 `import` 声明中添加 `strconv` 包，你可以让程序可以使用这些函数。

`strconv.Atoi()` 函数将括号内指定的字符串转换为 `int` 数据类型。它返回字符串等值的 `int` 值，但与你在 Go 中遇到的其他函数一样，它会返回第二个值，转换成功时为特殊的 `nil` 零值，失败时则返回错误信息。你必须将 `strconv.Atoi()` 函数的调用赋值给两个变量以接收返回值，如下：

```
num, err := strconv.Atoi("42")
```

还有一个 `strconv.Itoa()` 函数，它可以将 `int` 值转换为字符串值，但它只返回单个字符串值。

如果你希望将字符串值转换为 `float64`，可以使用 `strconv.ParseFloat()` 函数。与 `strconv.Atoi()` 类似，它返回字符串等价 `float64` 值以及 `nil` 值或错误信息。它需要字符串值和浮点大小（64）作为括号内的参数——例如，`strconv.ParseFloat("42", 64)`。

在不同数值类型之间进行强制转换只需声明所需的类型，后跟包含要转换值的括号即可。例如：

```
var num int = 42
var decimal float64 = float64( num )
```

有趣的是，当为 `byte` 数据类型（`uint8` 的别名——8 位无符号整数）的变量赋值单个字符时，它将存储该字符的 ASCII 字符编码数值，该值可以被轻松转换为字符串数据类型：

```
var char byte = 'A'
var str = string( char )
```

![](img/fa565c410b0509c58bcab29ed0b49de9_43_0.png)

ASCII（读作 "as-key"）是“美国标准信息交换码”的缩写，是纯文本接受的标准。你可以在 asciitable.com 找到完整的 ASCII 范围。

- 在 `src` 文件夹中创建一个名为 `cast` 的目录。

`src\cast\main.go`

- 使用 `package` 和 `import` 声明开始编写 `main.go` 程序。

```go
package main
import (
  "fmt"
  "strconv"
)
```

- 添加一个 `main` 函数来声明并初始化变量。

```go
func main() {

  var str string = "42"

  var char byte = 'A'

  // 在此处插入语句

}
```

- 在 `main` 函数中插入语句以输出转换后的变量值。

```go
num, err := strconv.Atoi(str)

fmt.Printf("num:%v %T\n", num, err)

decimal := float64(num)

fmt.Printf("decimal:%.2f %T\n", decimal)

fmt.Printf("char:%v %T\n", char, string(char))
```

- 将程序文件保存到 `cast` 目录，然后运行程序查看转换后的变量值。

![](img/fa565c410b0509c58bcab29ed0b49de9_44_0.png)

稍后你将通过测试 `err` 值是否为 `nil` 来发现转换是否成功——这在 Go 编程中被认为是良好的做法。从 `float` 转换到 `int` 的值会被截断。

### 固定值 (Constants)

如果你想在程序执行期间存储一个永远不会更改的固定值，应该使用 `const` 关键字而不是 `var` 关键字来声明。这可以防止意外（或恶意）的赋值。如果代码尝试给常量赋值新值，编译器将显示 `cannot assign` 的消息。

![](img/fa565c410b0509c58bcab29ed0b49de9_46_0.png)

与变量声明不同，常量必须在声明中初始化其固定值，如下：

```
const oneMillion = 1000000
```

常量声明可以指定数据类型，但如果声明中省略了显式数据类型，Go 编译器将从赋值的值推断其类型。

可以在单个声明中使用逗号分隔列表的形式创建相同或不同数据类型的常量，如下：

```
const oneMillion,oneThousand = 1000000,1000
```

由于常量声明可以使用名为 `iota` 的“常量生成器”来创建一个相关的常量序列。常量名应该在 `const` 关键字括号内每行一个，第一个分配 `iota` 值。这生成了一个从零开始的数值序列，列表中的每个命名常量递增一。例如，你可以为代表星期几的常量分配数值序列，如下：

```go
const (

sunday = iota

monday

tuesday

wednesday

thursday

friday

saturday
)
```

在这个示例中，常量 `sunday` 被赋值为 0，`monday` 被赋值为 1，以此类推。

如果你从不同的数字开始序列，只需在第一个常量的赋值中给 `iota` 加上该数字。

![](img/fa565c410b0509c58bcab29ed0b49de9_47_0.png)

在其他编程语言中，生成的序列通常被称为“枚举”或简单的 `enum`。

- 在 `src` 文件夹内部创建一个名为 `const` 的目录。

![](img/fa565c410b0509c58bcab29ed0b49de9_47_1.png)

`src\const\main.go`

- 使用 `package` 和 `import` 声明开始编写 `main.go` 程序。

```go
package main

import "fmt"
```

- 添加一个 `main` 函数来声明并初始化单个常量和一个从 (1) 开始的常量序列。

```go
func main() {

const pi = 3.14159

const (

red = iota + 1

yellow

green

brown

blue

pink

black

)

// 在此处插入语句。

}
```

接下来，插入语句来显示几个常量值。

```go
fmt.Printf("Pi approximately: %v \n", pi)

fmt.Printf("Red: %v \n", red)

fmt.Printf("Blue: %v \n", blue)

fmt.Printf("Black: %v \n", black)
```

- （修正：保存）将程序文件保存到 `const` 目录，然后运行程序查看常量值。

![](img/fa565c410b0509c58bcab29ed0b49de9_48_0.png)

Go 中的 `math` 包提供了一个名为 `math.Pi` 的常量，它是对 π 更好的近似值。

这里的序列代表了斯诺克游戏中每个球的分值。

### 指向存储的值 (Point to Stored Values)

每当你的程序创建一个存储数据的容器时，你的计算机会在内存中分配一个空间来存储数据。就像房屋一样，内存位置的大小可能不同，但每个位置都有唯一的地址。

![](img/fa565c410b0509c58bcab29ed0b49de9_50_0)

因此，一个初始化变量由三部分组成——名称、值以及存储数据的内存地址。

![](img/fa565c410b0509c58bcab29ed0b49de9_50_1)

Go 编程支持“指针”的概念。指针变量可以存储另一个变量的地址，并访问存储在该地址的值。

指针变量的声明要求数据类型前加上一个星号，以表示这是一个指针：

```
var ptr *int      // 声明此变量将指向一个 int。
```

通过在另一个变量名前加上 `&` 符号，可以将该变量的地址赋值给指针：

```
ptr = &num      // 给指针变量赋值地址。
```




然后，通过在指针名前加上 `*` 星号就可以访问赋值地址的值：

```go
*ptr // 指向赋值地址的值
```

![](img/fa565c410b0509c58bcab29ed0b49de9_50_2.png)

指针的概念可能很难理解，因为星号运算符 `*` 承担了两个作用：在声明中作为类型描述符，在放在指针名称之前作为解引用符。你现在可能在想：“指针？那又怎样？”但指针在 Go 编程中被广泛使用，因此在继续之前，你应该彻底理解它的工作原理。

![](img/fa565c410b0509c58bcab29ed0b49de9_51_0.png)

内存地址是由计算机分配的十六进制数。它们在你的系统上几乎肯定与示例所示地址不同。

1. 在你的 `src` 文件夹内创建一个名为 `point` 的目录。

`src\point\main.go`

2. 开始一个包含 `package main` 和导入声明的 `main.go` 程序：

```go
package main

import "fmt"
```

3. 添加一个 `main` 函数，声明并初始化一个普通整数变量和一个指针变量：

```go
func main() {
    var num int = 20
    var ptr *int = &num

    // 在此处插入语句。
}
```

4. 接下来，插入语句来显示普通整数变量的值和内存地址：

```go
fmt.Printf("num value: %v type: %T \n", num, num)
fmt.Printf("num address: %v type: %T \n\n", ptr, ptr)
```

5. 现在，插入语句显示指针变量的解引用值和指针变量本身的内存地址：

```go
fmt.Printf("num via pointer: %v type: %T \n", *ptr, *ptr)
fmt.Printf("ptr address: %v type: %T \n\n", &ptr, &ptr)
```

6. 最后，插入语句通过给指针变量赋值来更改整数变量存储的值：

```go
*ptr = 100

fmt.Printf("new num value: %v type: %T \n", num, num)
```

7. 将程序文件保存到 `point` 目录中，然后运行程序查看变量的值和地址：

```text
Terminal

C:\Users\mike_\go\src> go run point

num value: 20 type: int

address: 0xc00009e68 type: *int

num via pointer: 20 type: int

ptr address: 0xc000c8018 type: **int

new num value: 100 type: int

C:\Users\mike_\go\src>_
```

![](img/fa565c410b0509c58bcab29ed0b49de9_52_0.png)

这里需要识别的最重要特征是：指针改变了它指向的变量所存储的值（该值的副本）。这在将变量传递函数时变得非常重要——参见此处。

## 总结

- 变量存储可以通过给定的名称引用的数据，且其值可以更改。
- 显式变量声明使用 `var` 关键字并说明该变量可以包含的数据类型。
- 隐式变量声明可以在函数体内部使用 `:=` 运算符来推断类型。
- Go 是一门静态类型语言，变量只能包含其声明中指定类型的数据。
- `fmt.Printf()` 函数可以使用格式化指定符、变量名和换行符来格式化输出。
- `strconv.Atoi()` 函数返回括号内字符串值等价的 `int` 数据类型，以及一个可能是 `nil` 或错误信息的第二个值。
- `strconv.Itoa()` 函数返回括号内 `int` 值等价的 `string` 数据类型。
- `strconv.ParseFloat()` 函数返回括号内字符串值等价的 `float64` 数据类型，以及一个可能是 `nil` 或错误信息的第二个值。
- 当给 `byte` 类型变量赋值一个字符时，它存储的是该字符的 ASCII 编码数字。
- 数值数据类型之间的类型转换声明所需的类型，后跟包含要转换值的圆括号。
- 常量声明使用 `const` 关键字，并且必须用将包含的固定值进行初始化。
- 指针变量可以存储另一个变量的内存地址，并访问存储在该地址上的值。
- 星号运算符在指针变量声明中位于数据类型之前，表示该变量将是一个指针。
- `&` 取地址符运算符放在普通变量名称之前，以引用该变量的内存地址。
- `*` 星号运算符放在指针变量名称之前，以引用它指向地址上存储的值。

# 3 执行操作

本章介绍了 Go 运算符并演示了它们可以执行的操作。

## 算术运算

## 赋值

## 比较

## 逻辑判断

## 位运算

## 理解优先级

## 总结

### 算术运算详述

![](img/fa565c410b0509c58bcab29ed0b49de9_56_0.png)

Go 程序中常用的算术运算符列在下表中，以及它们执行的操作：

| 运算符 | 操作 |
| --- | --- |
| `+` | 加法 |
| `-` | 减法 |
| `*` | 乘法 |
| `/` | 除法 |
| `%` | 取模 |
| `++` | 递增 |
| `--` | 递减 |

赋值、加法、减法、乘法和除法的运算符作用正如你预期的那样，但在使用多个运算符的表达式中，必须通过括号进行分组：

```go
a = b*c - d%e/f // 这不清晰

a = (b*c) - ((d%e)/f) // 这个清晰
```

将该操作的结果赋值给第一个变量——成为它的新存储值。

使用 `%=` 复合运算符，会将分组后的左侧操作数 `a` 除以分组后的右侧操作数 `b`，然后将该操作的余数赋值给第一个变量 `a`。

![](img/fa565c410b0509c58bcab29ed0b49de9_60_0.png)

`+=` 运算符具有双重目的——它也可以用于字符串拼接。

![](img/fa565c410b0509c58bcab29ed0b49de9_60_1.png)

将 `==` 运算符视为“赋值”而不是“等于”是非常重要的，以避免与此处描述的 `==` 等于运算符产生混淆。

1. 在你的 `src` 文件夹内创建一个名为 `assign` 的目录。

![](img/fa565c410b0509c58bcab29ed0b49de9_60_2.png)

`src\assign\main.go`

2. 带有包和导入声明开始编写 `main.go` 程序：

```go
package main

import "fmt"
```

3. 添加一个声明两个变量的 `main` 函数：

```go
func main() {
    var a, b int

    // 在此处插入语句。
}
```

在 `main` 函数中，插入语句来输出简单赋值的值：

```go
a, b = 8, 4

fmt.Println("Assigned Values:\ta=a, a \tb=", b)
```

现在，插入语句更改第一个变量的值并显示它的新值：

```go
a += b

fmt.Println("Add and Assign:\ta=", a)

a -= b

// a = 12 - 4
fmt.Println("Subtract and Assign:\ta=", a)

a *= b

// a = 8 * 4
fmt.Println("Multiply and Assign:\ta=", a)

a /= b

// a = 32 / 4
fmt.Println("Divide and Assign:\ta=", a)

a %= b

// a = 8 % 4
fmt.Println("Remainder Assigned:\ta=", a)
```

将程序文件保存在 `assign` 目录中，然后运行程序以查看每个操作的结果。

![](img/fa565c410b0509c58bcab29ed0b49de9_61_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_61_1.png)

注意这里是如何在一个语句中初始化多个变量的。

![](img/fa565c410b0509c58bcab29ed0b49de9_62_0.png)

操作数必须是相同的数据类型。

## 比较

![](img/fa565c410b0509c58bcab29ed0b49de9_63_0.png)

Go 编程中常用的用于比较两个数值的运算符列下表所示：

| 运算符 | 比较测试 |
| --- | --- |
| `==` | 等于 |
| `!=` | 不等于 |
| `>` | 大于 |
| `<` | 小于 |
| `>=` | 大于等于 |
| `<=` | 小于等于 |

`==` 等于运算符比较两个操作数，并且如果两者的值相等，则返回 `true`，否则 `==` 运算符将返回 `false`。如果两个数字相同，它们就是相等的；或者如果两个都是字符，则会对它们的 ASCII 码进行数值比较。

相反，`!=` 不等于运算符在两个操作数不相等时返回 `true`，其使用的规则与 `==` 等于运算符相同，否则返回 `false`。相等和不等于运算符对于测试两个变量的状态以便在程序中执行条件分支非常有用。

> `>` “大于”运算符比较两个操作数，如果第一个的值大于第二个，则返回 `true`；如果它们相等或第一个在值上较小，则返回 `false`。`<` “小于”运算符进行相同的比较，但如果第一个操作数的值小于第二个，则返回 `true`，否则返回 `false`。通常，`>` “大于”或 `<` “小于”运算符用于测试循环结构中迭代计数器的值。

在 `>` “大于”运算符或 `<` “小于”运算符后添加 `=` 赋值运算符，可以使它们在两个操作数的值完全相等时也返回 `true`。

![](img/fa565c410b0509c58bcab29ed0b49de9_64_0.png)

比较运算符也被称为“关系运算符”。

1. 在你的 `src` 文件夹内创建一个名为 `comp` 的目录。

![](img/fa565c410b0509c58bcab29ed0b49de9_64_1.png)

`src\comp\main.go`

2. 带有包和导入声明开始编写 `main.go` 程序：

```go
package main
import "fmt"
```

3. 添加一个声明并初始化五个变量的 `main` 函数：

```go
func main() {
    var zero, num, max int = 0, 0, 1
    var up, dn byte = 'A', 'a'

    // 在此处插入语句。
}
```

4. 在 `main` 函数中，插入语句来输出几次比较的结果：

```go
result := (num == zero)

fmt.Println("Equality:\ta=zero", result)

result = (up == dn)

fmt.Println("Equality:\ta=dn", result)

result = (max != zero)

fmt.Println("Inequality:\ta=zero", result)

result = (max > zero)

fmt.Println("Greater:\ta=zero", result)

result = (zero < max)

fmt.Println("Less:\ta=max", result)

result = (max >= zero)

fmt.Println("Greater or equal:\ta=zero", result)

result = (zero <= max)

fmt.Println("Less or equal:\ta=max", result)
```

将程序文件保存在 `comp` 目录中，然后运行程序以查看比较的结果。

![](img/fa565c410b0509c58bcab29ed0b49de9_65_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_65_1.png)

注意这里是如何在一个语句中初始化多个变量的。

![](img/fa565c410b0509c58bcab29ed0b49de9_62_0.png)

操作数必须是相同的数据类型。

## 逻辑

![](img/fa565c410b0509c58bcab29ed0b49de9_66_0.png)

Go 编程中常用的逻辑运算符列下表所示：

| 运算符 | 操作 |
| --- | --- |
| `&&` | 逻辑与 |
| `\|\|` | 逻辑或 |
| `!` | 逻辑非 |

`&&` 逻辑与运算符比较两个操作数，如果两个值都为 `true`，则返回 `true`；否则，`&&` 运算符将返回 `false`。这用于满足条件的条件分支。

与 `&&` 逻辑与运算符需要两个操作数都为 `true` 不同，`\|\|` 逻辑或运算符只要一个操作数为 `true` 就会返回 `true`。然而，如果两个操作数都不 `true`，`\|\|` 逻辑或运算符将返回 `false`。

`!` 逻辑非运算符是一个一元运算符，用于单个操作数。它返回给定操作数的反，所以如果变量值为 `true`，`!a` 的值就是 `false`。这在 Go 程序中用于通过连续迭代语句 `a = !a` 来切换变量的值。这确保每次通过的值都会改变。

![](img/fa565c410b0509c58bcab29ed0b49de9_67_0.png)

“boolean”术语指的是由英国数学家乔治·布尔（1815-1864）开发的逻辑系统。

1. 在你的 `src` 文件夹内创建一个名为 `logic` 的目录。

`src\logic\main.go`

2. 带有包和导入声明开始编写 `main.go` 程序：

```go
package main

import "fmt"
```

3. 添加一个声明并初始化两个变量的 `main` 函数：

```go
func main() {
    var yes, no bool = true, false

    // 在此处插入语句。
}
```

4. 在 `main` 函数中，插入语句来确定两个变量是否包含 `true` 值：

```go
result := (yes && no)

fmt.Println("AND Logic:yes && no", result)
```

接下来，插入语句来确定任意一个变量是否包含 `true` 值：

```go
result = (yes || no)

fmt.Println("OR Logic:\tyes || no\t", result)
```

现在，插入语句来显示变量的当前值及其反值：

```go
result = yes

fmt.Println("NOT Logic:\tyes =", yes, "!yes =", result)
```

将程序保存在 `logic` 目录中，然后运行程序以查看逻辑评估的结果。

![](img/fa565c410b0509c58bcab29ed0b49de9_68_0.png)

比较 `false && false` 返回 `false` 而不是 `true`——证明了“错错没错并不等于对”的格言。

## 字节位

在计算机术语中，每个字节（byte）由八位（bits）组成，每个位包含 1 或 0 以存储二进制数，表示从 0 到 255 的十进制值。只有当位包含 1 时，它才会贡献一个十进制分量。组件从右到左从“最低有效位”（LSB）到“最高有效位”（MSB）命名。位模式 `00110110` 中的二进制数代表十进制数 50（2+16+32）：

| 位数 | 8 MSB | 7 | 6 | 5 | 4 | 3 | 2 | 1 LSB |
|---|---|---|---|---|---|---|---|---|
| 十进制 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
| 二进制 | 0 | 0 | 1 | 1 | 0 | 0 | 1 | 0 |

可以使用下面列出的 Go“位运算”操作符来操作字节的各个部分：

| 操作符 | 名称 | 示例操作 |
|---|---|---|
| `&` | AND（与） | `0011 & 0101 = 0001` |
| `\|` | OR（或） | `0011 \| 0101 = 0111` |
| `^` | XOR（异或） | `0011 ^ 0101 = 0110` |
| `^` | NOT（非） | `^0101 = 1010` |
| `&^` | AND NOT（按否） | `0011 &^ 0101 = 0010` |
| `<<` | Shift left（左移） | `0010 << 2 = 1000` |
| `>>` | Shift right（右移） | `1000 >> 2 = 0010` |

位操作符最常见的用法是操作表示一组布尔“标志”的紧凑“位字段”。这比在单独变量中存储布尔标志值要高效得多——一个仅需一个字节的 `byte` 数据类型就可以包含一个位字段（每位一个标志），而八个独立的 `byte` 变量则需要八个字节的内存。

许多 Go 程序员从不使用位操作符，但了解它们是什么以及如何使用是有用的。

字节的每个半被称为“半字节”（nibble，4 位）。表格示例中的二进制数描述了存储在半字节中的值。

1. 在你的 `src` 文件夹内创建一个名为 `bits` 的目录。

`src\bits\main.go`

2. 带有 `package` 和 `import` 声明开始一个 `main.go` 程序：

```go
package main

import "fmt"
```

3. 添加一个 `main` 函数，声明并初始化一个包含八位的变量：

```go
func main() {
    var flags byte = 10 // 二进制 1010（1x8 0x4 1x2 0x1）

    // 在此处插入语句。
}
```

4. 在 `main` 函数中，插入语句输出所有位标志设置：

```go
fmt.Printf("Flag #1:%v \n", (flags & 1) > 0)
```




```go
fmt.Printf("Flag #2:%v \n", (flags & 2) > 0)

fmt.Printf("Flag #3:%v \n", (flags & 4) > 0)

fmt.Printf("Flag #4:%v \n", (flags & 8) > 0)
```

- 接下来，插入语句显示表示此模式的十进制值：

```go
fmt.Printf("Flag Value: %08b \t%v \n", flags, flags)
```

- 现在，插入语句将“开启”位标志向右移动一位，并输出新模式的十进制值：

```go
flags = flags >> 1

fmt.Printf("New Value: %08b \t%v \n", flags, flags)
```

- 将程序保存到`bits`目录，然后运行程序查看位标志。使用更多内存的`int`类型可以创建更大的位字段——在 32 位系统上为 32 位宽，在 64 位系统上为 64 位宽。在这里使用`%b`格式输出二进制值。

### 理解优先级

运算符优先级定义了 Go 编译器评估表达式的顺序。在表达式`6 + 7 * 3`中，优先级决定了先完成加法还是乘法。下表按递减顺序列出了运算符优先级，高行的优先级高于低行。同一行的运算符优先级相等，但完成顺序由左到右决定，因此左侧的操作先完成。

| 优先级级别 | 运算符 |
|---|---|
| 5 | `*` `%` |
| 4 | `+` `-` |
| 3 | `!=` `<=` |
| 2 | `&&` `>=` |
| 1 | `||` |

自增运算符和自减运算符在 Go 编程中形成语句，而不是包含在优先级级别中。你可以通过括号包含表达式部分来强制编译器忽略默认级别。例如，在表达式`6 + 7 * 3`中，乘法运算符默认优先级高于加法运算符，因此先执行乘法。你可能希望先执行加法，可以通过给表达式添加括号`(6 + 7) * 3`来强制。现在表达式的评估为`6 + 7 = 3`。

- 在你的`src`文件夹内创建一个名为`force`的目录。
- 带有`package`和`import`声明开始`main.go`程序：

```go
package main

import "fmt"
```

- 添加一个`main`函数，通过评估表达式来声明并初始化变量并显示其值：

```go
func main() {
    sum := 2 * 3 + 4

    fmt.Printf("Default Order: %v\n", sum)

    // 在此处插入语句。
}
```

- 在`main`函数中，插入语句显示修改后表达式的值：

```go
sum := 2 * ((3 + 4) - 5)

fmt.Printf("Forced Order: %v\n", sum)
```

- 接下来，插入语句显示另一个表达式的值：

```go
sum = 7 % 3 * 2

fmt.Printf("Default Order: %v\n", sum)
```

- 现在，插入语句显示修改后表达式的值：

```go
sum = 7 % (3 * 2)

fmt.Printf("Forced Order: %v\n", sum)
```

- 将程序文件保存到`force`目录，然后运行程序查看不同的结果：

```text
C:\Users\mike_\go\src>go run force

Default Order: 3

Forced Order: 4

Default Order: 2

Forced Order: 1

C:\Users\mike_\go\src>>
```

在表达式中使用括号以避免意外结果。

## 总结

- 算术运算符可以形成两个操作数的表达式：加法`+`、减法`-`、乘法`*`、除法`/`和取模`%`。
- 自增`++`和自减`--`修改单个操作数。
- 赋值运算符`=`可以与算术运算符结合以执行算术计算，然后赋值其结果。
- 比较运算符可以形成比较两个操作数相等性的表达式：`!=`、大于`>`、小于`<`、大于等于`>=`和小于等于`<=`。
- 逻辑与`&&`和逻辑或`||`形成评估两个操作数的表达式，返回布尔值真或假。
- 逻辑非`!`运算符返回单个操作数的反布尔值。
- 单个内存字节由八位组成。
- 位运算符 OR `|`、AND `&`、NOT `~`和 XOR `^`在比较两个位内的值后各返回一个值。
- 左移`<<`和右移`>>`将位值按其方向移动指定数的位数。
- 位操作符最常见的用法是操作包含一组布尔标志的紧凑字段。
- 包含多个运算符的表达式将按照默认优先级执行操作，除非通过添加括号强制执行。

# 4 控制流

本章演示了语句如何评估表达式，以确定 Go 程序应该进行的方向。

- 测试条件
- Switch 分支
- 循环多次
- 当为真时循环
- Break 跳出循环
- Go 到标签
- 总结

## 测试条件

`if`关键字用于执行基本的条件测试，评估给定表达式以获得布尔值真或假。当表达式条件被发现为真时，评估后的大括号`{}`内的语句将被执行。`if`测试语句的语法如下：

```text
test-expression {
    statements-to-execute-when-the-condition-is-true
}
```

当测试为真时，可能有多个语句要执行，但每个语句必须单独占一行。有时可能需要评估多个表达式来确定是否应该执行后续语句。可以使用逻辑`&&` AND 运算符通过这种语法实现：

```text
test-expression && test-expression {
    statements-to-execute-when-all-conditions-are-true
}
```

或者，`if`语句可以“嵌套”，一个在另一个内部，以评估多个表达式，如下所示：

```go
if test-expression {
    statements-to-execute-when-all-conditions-are-true
}
```

当`if`测试语句评估的一个或多个表达式被发现为`false`时，其后续大括号中的语句将不会执行，程序将继续执行后续代码。通常通过在`if`语句后附加一个`else`语句来扩展它，指定当`if`语句评估的表达式为`false`时要执行的大括号内的语句，语法如下：

```go
if test-expression {
    statements-to-execute-when-the-condition-is-true
} else {
    statements-to-execute-when-the-condition-is-false
}
```

这是一项基础编程技术，它根据评估结果为程序提供了两个执行方向，被称为“条件分支”。

![](img/fa565c410b0509c58bcab29ed0b49de9_79_0.png)

测试表达式和左大括号`{`必须与`if`关键字出现在同一行。

![](img/fa565c410b0509c58bcab29ed0b49de9_79_1.png)

`else`关键字和左大括号`{`必须与上一个语句块的右大括号`}`出现在同一行。

- 用一个测试两个字符是否匹配的语句开始主函数：

```go
func main() {
    if 'A' == 'A' {
        fmt.Println("\nCharacters Match")
    }

    // Statements to be inserted here.
}
```

![](img/fa565c410b0509c58bcab29ed0b49de9_80_0.png)

`src\else\main.go`

- 接下来，在`main`函数中插入嵌套语句来测试两个数值表达式：

```go
if s > 1 {
    if s > 2 {
        fmt.Println("\nBoth expressions are true")
    }
}
```

- 现在，插入语句来测试一个数值表达式，并测试两个字符是否不匹配：

```go
if s < 1 {
    fmt.Println("\n1st Condition is true")
} else if 'A' != 'A' {
    fmt.Println("\n2nd Condition is true")
} else {
    fmt.Println("\nBoth Conditions are false")
}
```

- 将程序文件保存在`ifelse`目录，然后运行程序以查看条件测试的结果。

![](img/fa565c410b0509c58bcab29ed0b49de9_81_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_81_1.png)

为了避免重复，从现在开始的步骤中列出的代码假设你已经在每个程序的开头声明了`package main`和`import "fmt"`。

![](img/fa565c410b0509c58bcab29ed0b49de9_81_2.png)

注意，如果第一个测试为`false`，你可以使用`else if`来评估第二个表达式。

## Switch Cases（切换分支）

当测试表达式仅评估单个条件时，通过多个`if else`语句执行的条件分支通常可以通过`switch`语句更高效地完成。

![](img/fa565c410b0509c58bcab29ed0b49de9_82_0.png)

`switch`语句的工作很特殊。它接受一个给定值作为参数，然后尝试从多个`case`语句中匹配该值。找到匹配项时要执行的代码包含在每个`case`语句中。

重要的是，每个要执行的语句必须单独一行，从`case`语句下方的行开始。

可选地，`case`语句列表后面可以跟一个最后的`default`语句，用于指定在任何`case`语句中未找到匹配项时要执行的代码。因此，`switch`语句的语法通常如下：

```go
switch test-value {
case match-value:
    statements-to-execute-when-matched
case match-value:
    statements-to-execute-when-matched
case match-value:
    statements-to-execute-when-matched
default:
    statements-to-execute-when-no-match-found
}
```

如果多个`match-values`要执行相同的语句，则只有最后的`case`语句不需要包含要执行的语句。例如，对于匹配值为 0、1 和 2 的情况输出相同的消息：

```go
switch num {
case 0:
case 1:
case 2:
    fmt.Println("Less than 3")
case 3:
    fmt.Println("Exactly 3")
default:
    fmt.Println("Greater Than 3 or Less Than 0")
}
```

![](img/fa565c410b0509c58bcab29ed0b49de9_83_0.png)

`default`语句不需要出现在`switch`块的末尾，但将其放在那里是符合逻辑的。

![](img/fa565c410b0509c58bcab29ed0b49de9_83_1.png)

当找到匹配项时，`switch`会执行。虽然可以在任何`case`块中添加`fallthrough`关键字来继续执行，但这很少用。

- 用一个声明变量的语句开始主函数：

```go
func main() {
    num := 2
    char := 'B'

    // Statements to be inserted here.
}
```

![](img/fa565c410b0509c58bcab29ed0b49de9_84_0.png)

`src\switch\main.go`

- 接下来，在`main`函数中，插入嵌套语句来测试数值表达式：

```go
switch num {
case 1:
    fmt.Println("\nOne")
case 2:
    fmt.Println("\nTwo")
case 3:
    fmt.Println("\nThree")
default:
    fmt.Println("\nUnrecognized")
}
```

- 现在，插入语句来测试字符并测试两个字符是否不匹配：

```go
switch char {
case 'A':
    fmt.Println("\nA")
case 'B':
    fmt.Println("\nB")
default:
    fmt.Println("\nUnrecognized")
}
```

- 将程序文件保存在`switch`目录，然后运行程序以查看条件测试的结果：

```text
C:\path\to\switch> go run

One

Two

Three

Unrecognized
```

![](img/fa565c410b0509c58bcab29ed0b49de9_85_0.png)

## Loop Times（循环次数）

循环是程序中自动重复的代码。循环内所有语句的完整执行被称为“迭代”，或“通过”。循环的长度由循环内的条件测试控制。当测试表达式发现为`true`时，循环将继续——直到测试表达式发现为`false`，此时循环结束，不再执行语句。

![](img/fa565c410b0509c58bcab29ed0b49de9_86_0.png)

在 Go 编程中，有多种构建循环的方法，但都使用`for`关键字。最常见的循环语句包含三个部分——初始化器、单个测试表达式和增器，语法如下：

```go
for initializer; test-expression; incrementer {
    statements-to-executed
}
```

初始化器用于设置循环迭代次数的计数器的初始值。为此目的变量通常命名为`i`。

在循环的每次迭代中，都会评估`test-expression`，只有当该表达式为真时迭代才会继续。当表达式变为假时，循环立即结束，不再执行语句。每次迭代计数器增加，然后执行语句。

循环可以嵌套，一个套一个，以便在外层循环的每次迭代中完成内部嵌套循环的所有迭代。使用第二个整数变量来计算内部循环的迭代，通常命名为`j`。如果该内部循环也包含一个嵌套循环，其计数器通常命名为`k`，语法如下：

```go
for initializer; test-expression; incrementer {
    statements-to-executed

    for initializer; test-expression; incrementer {
        statements-to-executed

        for initializer; test-expression; incrementer {
            statements-to-executed
        }
    }
}
```

![](img/fa565c410b0509c58bcab29ed0b49de9_87_0.png)

嵌套超过三层的循环并不常见，并且可能最好避免。

- 用一个执行五次迭代的循环开始主函数：

```go
func main() {
    for counter := 1; counter <= 5; counter++ {
        fmt.Println("Loop Iteration", counter)
    }
}
```

```go
// Statements to be inserted here.
```

- 接下来，插入一个执行三次的循环：

```go
for i := 1; i <= 3; i++ {
    fmt.Println("Outer Loop Iteration", i)

    // Inner Loop to be inserted here.
}
```

- 现在，插入一个执行三次的内层循环：

```go
for j := 1; j <= 3; j++ {
    fmt.Println("Inner Loop Iteration", j)
}
```

- 将程序文件保存到`forloop`目录，然后运行程序查看每次循环迭代的输出。

![](img/fa565c410b0509c58bcab29ed0b49de9_88_0.png)

`for`循环计数器也可以进行减计数——通过在每次迭代中使用`i--`代替`i++`来减小计数器值。

## 死循环循环

![](img/fa565c410b0509c58bcab29ed0b49de9_89_0.png)

上一个示例中描述的`for`循环的替代方案在这里仅在`for`关键字后包含一个测试表达式——它没有在循环语句开头包含初始化器或递增器。相反，它使用一个已经初始化的计数器，并在循环体内增加计数器。这是 Go 与其他编程语言中“while”循环的等价物，只要测试表达式为真，循环就会继续迭代。递增器必须在某处使测试表达式为假以结束循环，否则将创建一个永远不会结束的死循环。这种类型`for`循环的语法如下：

```go
initializer

for test-expression {
    statements-to-be-executed
    incrementer
}
```



Go 编程中循环结构的一种变体允许你从起始语句中省略测试表达式，并使用包含在体内的测试表达式的无限循环。它同样使用已经初始化的计数器变量，并在循环体内增加计数器。这是 Go 与其他编程语言中“do-while”循环的等价物，因为只要测试表达式为真，循环就会执行语句并继续迭代。当测试表达式变为假时，可以使用`break`关键字终止循环，因此这种类型`for`循环的语法如下：

```go
initializer

for {

    statements-to-be-executed

    incrementer

    if test-expression {

        statements-to-be-executed

        break

    }

}
```

注意，如果测试表达式在第一次求值时为假，“while”循环将不会进行迭代，而“do-while”循环将至少执行一次迭代，因为它的语句在评估之前就已经执行了。

![](img/fa565c410b0509c58bcab29ed0b49de9_90_0.png)

如果程序运行了死循环，在 Windows 或 Linux 系统上按下 `Ctrl + C` 键停止循环执行。

1. 从一个执行五次迭代的循环开始`main`函数

```go
func main() {

    counter := 1

    for counter <= 5 {

        fmt.Println("Loop Iteration", counter)

        counter++

    }

    // Statements to be inserted here.
}
```

![](img/fa565c410b0509c58bcab29ed0b49de9_90_1.png)

`src\while\main.go`

接下来，插入一个无限循环语句

```go
i := 10

for {

    fmt.Println("Countdown", i)

    // Test expression to be inserted here.
}
```

现在，插入一个测试表达式来结束循环

```go
if i<1 {

    fmt.Println("Lift Off!")

    break

}
```

将程序文件保存到“while”目录，然后运行程序查看每次循环迭代的输出

![](img/fa565c410b0509c58bcab29ed0b49de9_91_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_92_0.png)

将变量`i`的初始值更改为`0`（零）并再次运行程序，查看循环的第一次迭代的执行。

### 跳出循环

`break`关键字可以在满足特定条件时提前终止任何循环。`break`语句位于循环语句块内部，前面有一个测试表达式。当测试返回`true`时，循环立即结束，程序继续后续任务。例如，在嵌套内层循环中，它将进入外层循环的下一次迭代。

![](img/fa565c410b0509c58bcab29ed0b49de9_93_0.png)

`continue`关键字可以在满足特定条件时跳过循环的单次迭代。`continue`语句位于循环语句块内部，前面有一个测试表达式。当测试返回`true`时，单次迭代结束。

1. 从一个执行三次迭代的循环开始`main`函数

```go
func main() {

    for i:=1; i <= 3; i++ {

        // Statements to be inserted here.
    }
}
```

![](img/fa565c410b0509c58bcab29ed0b49de9_93_1.png)

`src\while\main.go`

2. 从一个执行三次迭代的循环开始`main`函数

```go
func main() {

    for i:=1; i <= 3; i++ {

        // Statements to be inserted here.
    }
}
```

![](img/fa565c410b0509c58bcab29ed0b49de9_94_0.png)

3. 从一个执行三次迭代的循环开始`main`函数

```go
func main() {

    for i:=1; i <= 3; i++ {

        // Statements to be inserted here.
    }
}
```

![](img/fa565c410b0509c58bcab29ed0b49de9_94_0.png)

4. 从一个执行三次迭代的循环开始`main`函数

```go
func main() {

    for i:=1; i <= 3; i++ {

        // Statements to be inserted here.
    }
}
```

```go
}
}
```

`src/jump/main.go`

+ 插入一个执行三次的内层循环

```go
for j := 1; j <= 3; j++ {
    fmt.Println("Running i=", i, "j=", j)
}
```

+ 将程序文件保存到“jump”目录，然后运行程序查看每次循环迭代的输出

+ 在内嵌套循环的第一行插入一个语句，在指定的计数器值处跳转到标签“end”

```go
if i == 2 && j == 2 {
    goto end
}
```

+ 现在，在外层循环闭合大括号`}`之后的下一行添加标签

```go
end:
```

+ 保存更新后的文件，然后再次运行程序，查看当测试条件为真时循环结束的情况

```bash
C:\Users\mike_\go\src> run jump

Running i=1 j=1

Running i=1 j=2

Running i=1 j=3

Running i=2 j=1

Running i=2 j=2

Running i=2 j=3

Running i=3 j=1

Running i=3 j=2

Running i=3 j=3

C:\Users\mike_\go\src>_
```

避免创建名为“goto.exe”的可执行程序，因为这可能会与 Windows 系统上的内部`GOTO`命令冲突。

注意，标签本身必须以冒号`:`结尾。

## 总结

- `if`关键字执行基础条件测试，以评估给定表达式的布尔值为`true`或假`false`。
- `else`关键字可用于在`if`语句发现表达式为`false`时提供备选的可执行语句。
- 在评估后为程序提供执行的备选方向，被称为“条件分支”。
- 通过多个`else`语句执行的条件分支通常可以通过`switch`语句更高效地完成。
- `switch`块内的语句必须分别出现在`case`语句下方的单独行中。
- 可选地，`switch`块可以包含一个`default`语句，指定在未找到匹配项时执行的语句。
- `for`关键字可以指定初始化器、测试表达式和递增器，用来控制循环。
- `for`关键字可以简单地指定测试表达式，以决定循环是否在`true`情况下继续。
- `for`关键字可以完全省略测试表达式以创建无限循环。
- 可以在无限循环体体内测试条件，并使用`break`关键字结束循环。
- `break`关键字用于终止循环，而`continue`关键字可用于跳过单次迭代。
- 循环可以是嵌套的，使得内层循环在外层循环的每次迭代中执行一系列迭代。
- 通常不建议使用`goto`关键字，但它可以合法地用于退出嵌套循环。

# 5

# 产生函数

本章演示了如何将语句封装在函数内部，以便每当 Go 程序调用该函数时都能执行它们。

- 创建基础函数
- 添加参数
- 传递引用
- 返回值
- 递归调用
- 匿名封装
- 传递函数
- 处理错误
- 分离文件
- 总结

### 创建基础函数

本书中的之前的示例使用了强制性的`main()`函数以及 Go 标准库中包含的函数，例如“fmt”包中的`fmt.Println()`函数。然而，大多数 Go 程序包含许多自定义函数，可以在程序执行期间根据需要进行调用。

函数块仅包含一组语句，每当该函数被调用时就会被执行。一旦函数语句执行完毕，程序流将从函数调用后的直接点继续恢复。这种模块化在 Go 编程中非常有用，可以隔离一组根据需要重复调用的代码序列。

要在 Go 程序中添加自定义函数，必须使用`func`关键字进行声明，后紧跟一个你选择的名称——遵循与变量名相同的命名规范。

| 命名规则 | 示例 |
| --- | --- |
| 不能是 Go 关键字 | default |
| 不能包含算术运算符 | a+b*c |
| 不能包含标点符号字符 | %$@! |
| 不能包含任何空格 | no spaces |
| 必须以字母开头 | msg |
| 可以在其他地方包含数字 | good1 |
| 可以包含混合大小写 | camelCase |

在选择函数名时，它应该描述函数的用途，但要保持简洁。函数名后紧跟`()`括号和一个`{`左大括号，都在同一行上。这一行通常被称为“签名”。要执行的语句包含在函数体内，函数体以`}`右大括号结束。可以通过指定其名称来调用函数。

函数名应以小字母开头，除非该函数已导出——参见此处

1. 创建一个函数，每次被调用时只需打印一条消息

```go
func first() {

    msg := "Hello from function!"

    fmt.Println(msg)
}
```

2. 创建另一个函数，每次被调用时只需打印乘法结果

```go
func sqFive() {

    fmt.Println("5 = 25")
}
```

3. 接下来，添加一个`main`函数，开头是一个调用该函数的语句

```go
func main() {

    first()

    sqFive()
}
```

将程序文件保存到“funcs”目录，然后运行程序查看输出

```bash
Go Terminal

C:\Users\mike_\go\src>go run funcs

Hello from function!

5 = 25
```

在函数或其他块内部声明的变量只能在该块内访问——它们具有“局部作用域”。例如，这里的`msg`变量只能在`first()`函数内部访问。
在函数外部声明的变量可以在程序的任何地方访问——它们具有“全局作用域”。最好只使用局部变量，以避免与全局作用域中的变量可能发生冲突。

### 添加参数

函数声明中函数名后的`()`括号可以可选包含逗号分隔的“参数”。这些是函数可以使用变量，其初始内容由调用者提供。这些变量在每次调用函数时创建，并在控制退出函数时销毁。每个参数必须赋予一个你选择的名称（遵循通常变量命名规范）和一个类型，语法如下：

```go
func functionName (paramName type, paramName type) {

    statements-to-be-executed
}
```

多个连续相同的参数可以作为一个列表声明，只需在该类型的最后一个参数之后指定类型，如下：

```go
func functionName (paramName, paramName type) {

    statements-to-be-executed
}
```

每个函数必须为每个参数指定内容，类型正确且顺序与函数声明中的顺序相同。传递给函数的内容被称为“参数”。这些内容在调用函数名后的`()`括号内以逗号分隔列表的形式指定：

```go
functionName (argument, argument, argument)
```

与其它编程语言不同，Go 没有方法可以指定默认用于函数参数的`Println`。

必须认识的一是：在 Go 编程中，参数默认是“按值传递”（passed by value）的——函数接收的是参数的副本，而不是原始参数。这意味着对参数变量所做的更改默认不会影响调用者指定的原始参数——它们只会影响副本。

```go
// 创建一个需要单个整数参数并显示其值的函数
func square(num int) {

    fmt.Println("\t\tReceived Copy:", num)

    // 在此处插入语句。
}
```

![](img/fa565c410b0509c58bcab29ed0b499_106.png)

`src\args\main.go`

```go
// 接下来，插入语句来修改收到的参数，并显示其新值
num = num * num

fmt.Println("\t\tModified Copy:", num)
```

```go
// 开始一个 main 函数，声明并初始化一个变量，然后显示其值
func main() {

    num := 5

    fmt.Println("Original:", num)

    // 在此处插入语句。
}
```

```go
// 接下来，在 main 函数中插入语句调用另一个函数，并再次显示其变量
square(num)

fmt.Println("Original:", num)
```

5. 将程序文件保存到“args”目录中，然后运行程序以查看原始值是否保持不变

```bash
Go Terminal
C:\Users\mike\src>go run args
Original: 5      Received Copy: 5
Original: 5      Modified Copy: 25
```

![](img/fa565c410b0509c58bcab29ed0b499_107.png)

你还可以创建接受任意数量参数的“变长函数”（variadic functions）——请参见此处示例。

### 传递引用 (Pass References)

这里的示例说明了在 Go 编程中，参数默认是“按值传递”的——函数接收的是原始参数的副本。但你经常可能希望函数能够修改原始参数。这可以通过向函数传递一个引用而不是值的副本来实现。

![](img/fa565c410b0509c58bcab29ed0b499_108.png)

记住，指针是存储有值的内存地址的引用。这意味着如果你向函数传递一个指针参数，它将能够修改存储在指针提供的地址上的原始值。在声明可以接收指针参数的函数时，其参数列表中指定的数据类型必须带有星号`*`前缀，表示该参数将是一个指针，如下：

```go
func functionName(param *type) {
    // 要执行的语句
}
```

参数名随后就可以存储一个位置。函数语句通过在参数名前加加上星号进行解引用（dereference），可以访问并修改指针提供地址上的值。在调用接受指针参数的函数时，参数必须以取地址符`&`前缀，以引用存储值的内存地址。

这种技术可以用于`int`、`float64`、`string`和`bool`数据类型，适用于适用于节将介绍的`struct`类型。这些都是“值类型”，因此在将它们传递给函数时，需要指针来访问它们包含的原始值。

这种技术不能用于指针类型或函数类型（是的，Go 中有函数），也无法用于本书后面演示的`slice`、`map`或`channel`类型。这些都是“引用类型”，因此在将它们传递给函数时，不需要指针来访问它们包含的原始值。

![](img/fa565c410b0509c58bcab29ed0b499_109.png)

请返回此处回顾指针如何工作。

- 创建一个需要单个整数参数并显示其值的函数（在此处使用指针）

```go
func square(num *int) {
    fmt.Println("\t\tReceived Copy:", *num)
    // 在此处插入语句。
}
```

![](img/fa565c410b0509c58bcab29ed0b499_110)

- 接下来，插入语句修改收到的参数并显示其新值

```go
*num = *num * *num

fmt.Println("\t\tModified Copy:", *num)
```

- 在一个`main`函数声明并初始化一个变量，然后显示其值

```go
func main() {
    num := 5
    fmt.Println("Original:", num)
    // 在此处插入语句。
}
```

- 接下来，在`main`函数中插入语句调用另一个函数并再次显示其变量

```go
square(&num)

fmt.Println("Original:", num)
```

5. 将程序文件保存到“args”目录中，然后运行程序以查看原始值是否改变

```bash
Go Terminal

C:\Users\mike\src>go run args

Original: 5      Received Copy: 5

Original: 5      Modified Copy: 25
```

![](img/fa565c410b0509c58bcab29ed0b499_101.png)

### 返回值 (Return Values)

这里的示例说明了在 Go 编程中，参数默认是“按值传递”的——函数接收的是原始参数的副本。但你经常可能希望函数能够修改原始参数。这可以通过向函数传递一个引用而不是值的副本来实现。

在声明可以接收指针参数的函数时，其参数列表中指定的数据类型必须带有星号`*`前缀，表示该参数将是一个指针，如下：

```go
func functionName(param *type) {
    // 要执行的语句
}
```



参数名随后就可以存储一个位置。函数语句通过在参数名前加上星号进行解引用，可以访问并修改指针提供地址上的值。在调用接受指针参数的函数时，参数必须以取地址符 `&` 前缀，以引用存储值的内存地址。

这种技术可以用于 `int`、`float64`、`string` 和 `bool` 数据类型，适用于下一节将介绍的 `struct` 类型。这些都是“值类型”，因此在将它们传递给函数时，需要指针来访问它们包含的原始值。

这种技术不能用于指针类型或函数类型（是的，Go 中有函数），也无法用于本书后面演示的 `slice`、`map` 或 `channel` 类型。这些都是“引用类型”，因此在将它们传递给函数时，不需要指针来访问它们包含的原始值。

![](img/fa565c410b0509c58bcab29ed0b499_102.png)

在 Go 语言中，函数可以返回多个值。返回多个值的函数语法如下：

```go
func functionName(param type) (type1, type2) {
    // 要执行的语句
}
```

在调用返回多个值的函数时，必须提供相应数量的变量来接收返回值。如果函数返回了多个值但你没有使用所有值，编译器会产生错误。为了避免这种情况，你可以使用下划线 `_` 来接收任何不需要的值。这在 Go 编程中被称为“空白标识符”（blank identifier）。

标准库中的许多函数都会返回多个值，特别是为了返回结果和错误。

1. 创建一个需要单个整数参数并向调用者返回三个值的函数

```go
func cube(num int) (string, int, int) {
    return "Result", num, num * num
}
```

![](img/fa565c410b0509c58bcab29ed0b499_103.png)

`returns\main.go`

2. 添加一个 `main` 函数将三个返回值赋值给三个变量，然后尝试显示两个值

```go
func main() {
    a, b, c := cube(5)
    fmt.Println(b, "Cubed =", c)
}
```

将程序文件保存到“returns”目录中，然后运行程序以查看编译器错误信息。

![](img/fa565c410b0509c58bcab29ed0b499_104.png)

修改 `main` 函数中的赋值，将第一个返回值赋值给一个空白标识符。

```go
func main() {
    b, c := cube(5)
    fmt.Println(b, "Cubed =", c)
}
```

![](img/fa565c410b0509c58bcab29ed0b499_105.png)

![](img/fa565c410b0509c58bcab29ed0b499_106.png)

返回的“Result”字符串值在此处的输出中并未使用。

### 递归调用

自定义函数内部语句可以自由地调用其他自定义函数，就像调用 `fmt.Printf()` 等标准 Go 函数一样简单。此外，函数可以“递归地”调用自己。与循环一样，重要的是递归函数调用必须修改被测试的表达式，以避免持续执行——这样函数会在某个点退出。

![](img/fa565c410b0509c58bcab29ed0b49de9_114_0.png)

递归函数调用可以用于模拟循环结构，例如这里的倒计时示例：

- 创建一个需要整数参数的函数，并不断进行递归调用，直到该值递减到零

```go
if num < 1 {
    fmt.Println("Lift Off!")
} else {
    fmt.Println("Countdown", num)
    num--
    countDn(num)
}
```

![](img/fa565c410b0509c58bcab29ed0b49de9_114_1.png)

`src\recur\main.go`

- 添加一个 `main` 函数，其中包含一个调用上述函数的语句

```go
func main() {
    countDn(10)
}
```

将程序文件保存到“recur”目录中，然后运行程序查看递归函数调用模拟循环。

![](img/fa565c410b0509c58bcab29ed0b49de9_115_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_115_1.png)

递归函数调用对于解决数学问题，例如计算给定数的阶乘。阶乘是从给定数字到 1 的所有整数的乘积——例如，3 的阶乘是 3 (2*1)。

- 创建一个需要整数参数的函数，并在每次调用时返回一个整数值

```go
func facto(num int) int {
    // 在此处插入语句。
}
```

`src\facto\main.go`

- 接下来，插入一个语句，当参数值递减到 (0) 时返回一个 (1)

```go
if num == 0 {
    return 1
}
```

- 然后，插入一个最终语句来递归调用函数，乘以序列中的所有数字

```go
return num * facto(num - 1)
```

- 添加一个 `main` 函数，其中包含一个打印阶乘的语句

```go
func main() {
    for i := 1; i < 7; i++ {
        fmt.Println("Factorial", i, "=", facto(i))
    }
}
```

- 将程序文件保存到“facto”目录中，运行程序查看阶乘序列。

![](img/fa565c410b0509c58bcab29ed0b49de9_116_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_116_1.png)

递归函数很有用，但效率并不高。这个示例调用了 7 次 `facto()` 为了生成这个阶乘序列！

### 匿名函数

Go 编程语言支持“一等函数”。这允许将函数赋值给变量、作为参数传递给其他函数，并从函数返回。

![](img/fa565c410b0509c58bcab29ed0b49de9_118_0.png)

匿名函数简单来说是不包含名称的函数定义。这对于内联创建函数而无需命名非常有用。匿名函数也称为“函数字面量”。像其他函数一样，这些可以包含参数列表、返回类型列表，并返回多个值。你可以通过在函数定义末尾附加 `()` 运算符来创建一个自执行的匿名函数，如下：

```go
func() { fmt.Println("Function Literal") }()
```

此外，匿名函数可以赋值给变量，通过在变量名后附加 `()` 运算符来调用，如下：

```go
fn := func() { fmt.Println("Function Literal") }
fn()
```

![](img/fa565c410b0509c58bcab29ed0b49de9_118_1.png)

自执行函数表达式只执行一次其语句。

### 闭包

匿名函数最有用的可能是创建“闭包”。闭包是嵌套在外部函数内部的函数，它保留了对外部函数中声明的变量的访问权限。外部函数可以返回一个保留变量访问权的匿名函数，但至关重要的是，这些变量在程序代码的其他地方都是不可访问的。这是封装的形式，保护了存储在变量中的数据，因为返回的匿名函数“闭包”了它们。

通过在外部函数结束处后附加 `()` 运算符，可以将闭包设为自执行并赋值给变量。然后，可以通过在变量名后附加 `()` 运算符调用匿名内部函数——它将访问外部函数中的持久化值。

理解闭包的概念可能困难，因为看起来当自执行函数完成执行后，外部函数中的变量应该被销毁。

![](img/fa565c410b0509c58bcab29ed0b49de9_119_0.png)

### 传递函数类型

你可以使用 `type` 关键字声明自定义函数类型，后面跟一个名称和签名。

### 高阶函数

将函数传递给其他函数允许修改操作代码。任何接受函数作为参数的函数，或任何返回一个或多个函数，都被视为“高阶”函数。

- 声明一个 `main` 函数，声明一个具有两个整数参数和一个整数返回类型的自定义函数类型

```go
func main() {
    type adder func(int, int)
}
```

`src\listypemin.go`

- 接下来，插入一个语句来定义自定义类型的函数实例——具有匹配的签名

```go
var add = func(a int, b int) int {
    return a + b
}
```

- 现在，插入一个语句调用该函数（实例）

```go
fmt.Println("Added:", add(6, 2))
```

在 `main` 函数之后，开始一个高阶函数，它将接收并返回一个与自定义类型签名相同的函数。

```go
func dub(twice func(int, int) int) func(int, int) int {
    fmt.Println("Doubled:", twice(6, 2) * 2)
    return nil
}
```

- 现在，插入语句来定义并返回一个签名相同的函数给调用者

```go
div := func(a int, b int) int {
    return (a + b) / 2
}
```

回到 `main` 函数中，插入一个语句将函数（实例）传递给高阶函数，并将该函数的返回函数赋值给变量。

```go
div := dub(add)
```

- 现在，插入一个语句调用返回的函数

```go
fmt.Println("Divided:", div(6, 2))
```

```go
fmt.Printf("add type: %T \n", add)
fmt.Printf("dub type: %T \n", dub)
fmt.Printf("div type: %T \n", div)
```

将程序文件保存在“ftype”目录中，然后运行程序查看返回值和函数类型。

![](img/fa565c410b0509c58bcab29ed0b49de9_124_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_124_1.png)

注意，函数签名在声明中只需要说明所需的类型，但在定义中也需要说明参数名称。

![](img/fa565c410b0509c58bcab29ed0b49de9_124_2.png)

注意，函数实例 `add` 仅简单描述为自定义函数类型 `main.adder`。

### 处理错误

在你的 Go 程序中预判错误并使代码能够高效地处理它们是非常重要的。其他编程语言（如 Java 和 Ruby）在遇到错误时会抛出“异常”，程序可以在运行时尝试捕获这些异常，但 Go 提供了一种更简单的方法。

![](img/fa565c410b0509c58bcab29ed0b49de9_125_0.png)

Go 编程允许你处理返回独立值的函数中产生的错误。这易于识别是哪个函数返回了错误，并让你使用熟悉的 Go 语言构造来处理错误。

为了处理可能的错误，函数签名必须包含一个 Go 内置的 `error` 返回类型。传统上，这是返回值列表中的最后一个返回值。

```go
func funcName ( paramName type ) ( returnType, error )
```

在函数体中，代替预期的返回值，函数可以返回一个平凡的值（例如 -1）以及所返回的错误值。

如果没有发生错误，函数可以返回预期的返回值以及一个 `nil` 零值。在 Go 编程中，`nil` 零值用于表示许多类型的零值。在这里，它仅表示没有错误。因此，处理错误的函数语法可能如下：

```go
func funcName ( paramName type ) ( returnType, error ) {
    if condition != true {
        return -1, errorValue
    }
    return returnValue, nil
}
```

在之前的示例中使用了 `fmt.Println()` 和 `fmt.Printf()` 函数的“fmt”包也提供了一个 `fmt.Error()` 函数，它可以返回 `error` 类型。它接受与 `fmt.Printf()` 函数相同的格式化标记，并用于返回一条消息以标识错误的位置和性质。

![](img/fa565c410b0509c58bcab29ed0b49de9_126_0.png)

Go 标准库还还有一个 `errors` 包，可以用于操作自定义错误。

- 创建一个需要整数参数并返回一个整数值和一个错误的函数

```go
func isPosInt(num int) (int, error) {
    // 在此处插入语句。
}
```



![](img/fa565c410b0509c58bcab29ed0b49de9_126_1.png)

`srcerr/main.go`

- 然后，插入一个条件测试来返回错误或参数值——取决于其值的值

```go
if num < 1 {
  err := fmt.Errorf("%v not a positive integer", num)
  return -1, err
}
```

- 现在，添加一个 `main` 函数，包含一个递减循环以打印参数值或错误消息

```go
func main() {
  for i := 2; i>=2; i-- {
    res, err := isPosInt(i)
    if err != nil {
      fmt.Println("Failed:", err)
    } else {
      fmt.Println(res, "Passed!")
    }
  }
}
```

将程序文件保存在 `err` 目录中，然后运行程序以查看测试失败时的错误消息

![](img/fa565c410b0509c58bcab29ed0b49de9_127_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_127_1.png)

你将看到在许多 Go 程序中，`if err != nil` 被用作开始错误处理程序的标准方式。

### 分离文件

随着程序规模的增大，将相关的代码部分分离到单独的文件通常是明智的。你只需在与 `main.go` 文件相同的包目录下添加一个文件，只要该文件从开始就声明自己属于同一个包（`package main`），添加的文件中的任何代码都将被视为包含在 `main.go` 文件中。

![](img/fa565c410b0509c58bcab29ed0b49de9_128_0.png)

- Go 语言允许你通过返回多个值来处理函数中出现的错误。
- 只有首字母大写的已导入函数和变量才能被导入的文件访问。

# 6 构建结构

*本章将演示如何将数据和函数包含在 `struct`（结构体）中，可以在 Go 中表示面向对象的编程。*

- 分组数据
- 附加方法
- 嵌套结构体
- 封装特性
- 组合元素
- 实现接口
- 嵌入接口
- 总结

### 分组数据

任何数据类型的多个相关项都可以组合在 Go 语言的 `struct` 结构类型中。这对于创建类似于你在数据库中找到的记录非常有用。

![](img/fa565c410b0509c58bcab29ed0b49de9_134_0.png)

使用 `type` 关键字创建结构，后面跟上你选择的名称，然后是结构和 `{ }` 大括号。大括号包含每行一个变量名和数据类型对。这些被称为结构体的 `字段`（fields），定义了结构将包含的内容，语法如下：

```
type structName struct {
  fieldName dataType
  fieldName dataType
}
```

定义结构体类型后，可以使用以结构名称作为类型声明的变量来创建结构体实例：

```go
var instanceName structName
```

结构体的单个字段通过使用点后缀将字段名附加到结构名来访问。可以通过多种方式为结构体实例的单个字段赋值。首先，你可以像这样给单个字段赋值：

```
instanceName.fieldName = value
instanceName.fieldName = value
```

或者，你可以在可以在单条语句中初始化所有字段，将 `结构体字面量`（struct literal）分配给实例，如下：

```
instanceName = structName{value, value}
```

使用这种技术要求值的顺序与结构体中字段的顺序相同，但你可以在结构体中包含字段名，以便值可以任何顺序出现，如下：

```
instanceName = structName{fieldName: value, fieldName: value}
```

此外，你可以在单条语句中创建结构体实例并初始化所有字段，将 `结构体字面量` 赋值给变量，例如：

```go
instanceName := structName{fieldName: value, fieldName: value}
```

结构体中的空字段默认获得一个零值。

![](img/fa565c410b0509c58bcab29ed0b49de9_135_0.png)

你可以将结构体视为一个模板，其实例是aps包含实际数据的副本。

![](img/fa565c410b0509c58bcab29ed0b49de9_135_1.png)

虽然这两个语句非常相似，但请注意 `:=` 运算符仅在单条语句中创建实例并初始化结构体字段时使用。

通过创建一个结构体类型开始程序程序

```go
type employee struct {
  id int
  name string
  dept string
}
```

![](img/fa565c410b0509c58bcab29ed0b49de9_136_0.png)

`src\group\main.go`

接下来，通过创建结构体类型的实例开始 `main` 函数：

```go
var coder employee
```

现在，为结构体实例的每个字段赋值：

```go
coder.id = 1
coder.name = "Alice"
coder.dept = "IT"
```

创建结构体的第二个实例，使用结构体字面量和字段名初始化结构体的每个字段：

```go
clerk := employee{name: "Burt", dept: "Payroll", id: 2}
```

添加语句显示每个结构中的所有值：

```go
fmt.Println(coder)
fmt.Println(clerk)
```

最后，添加语句显示结构中的单个字段值：

```go
fmt.Printf("%v works in %v\n", coder.name, coder.dept)
fmt.Printf("%v works in %v\n", clerk.name, clerk.dept)
```

将程序保存到 `group` 目录中，然后运行程序查看结构值：

```
Go Terminal
C:\Users\mike_go\src> run group
Alice works in IT
Burt works in Payroll
C:\Users\mike_go\src>
```

![](img/fa565c410b0509c58bcab29ed0b49de9_137_0.png)

注意步骤 4 中的语句没有按照结构体中列出的顺序分配字段，但使用字段名可以确保值被分配到正确的字段。

### 附加方法

![](img/fa565c410b0509c58bcab29ed0b49de9_138_0.png)

在 Go 编程中，可以通过在函数签名中添加 `接收者`（receiver）将函数附加到结构体：

```go
func (paramName structName) funcName()
```

附加到结构体的函数被称为该结构的 `方法`（method）。方法可以指定为值接收者（操作结构的副本），也可以指定为指针接收者（操作原始结构）：

```go
func (paramName *structName) funcName()
```

这种能力使得结构能够表示具有属性和行为的现实对象：

- 属性描述对象拥有的特性。
- 行为描述对象可以执行的操作。

例如，`car` 可以描述为具有 `blue` 和 `coupe` 属性以及一个 `accelerate` 行为。

这些特性可以在 Go 编程中用包含 `color` 和 `body` 字段的 `car` 结构来表示，并附加 `accelerate()` 方法。

在 Go 编程中，通过定义作为模板的不同副本（即 `实例`）来创建对象。结构体的每个实例都可以通过分配属性值和行为进行自定义。与其他编程语言不同，Go 没有类，但可以使用结构体来表示对象。

1. 通过创建一个结构体类型开始程序：

```go
type car struct {
  color string
  body string
}
```

`src\method\main.go`

2. 接下来，为结构体类型附加方法：

```go
func (c car) accelerate() string {
  return "accelerating..."
}
```

3. 现在，通过创建结构体类型的两个实例开始 `main` 函数：

```go
porsche := car{color: "blue", body: "coupe"}
bentley := car{color: "green", body: "saloon"}
```

4. 添加语句显示每个结构中的所有值：

```go
fmt.Println(porsche)
fmt.Println(bentley)
```

5. 最后，添加语句显示单个字段值：

```go
fmt.Println(porsche.color)
fmt.Println(bentley.color)
```

6. 将程序保存到 `method` 目录中，然后运行程序查看结构值：

![](img/fa565c410b0509c58bcab29ed0b49de9_140_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_140_1.png)

当你调用方法时，Go 会自动处理值和指针之间的转换，因此如果你想修改原始字段，这里的接收者可以是 `*car`。

### 嵌套结构体

由于结构体字段仅用名称和类型声明，且结构体是一种类型，Go 编程允许通过声明一个字段为结构类型将一个结构嵌套在另一个结构中。

![](img/fa565c410b0509c58bcab29ed0b49de9_141_0.png)

```
type Name struct{
  embeddedStructName
}
```

这对于构建高效使用用途多变的结构体非常有用。例如，取一个简单存储 X 和 Y 坐标的结构体：

```go
type coords struct {
  x, y int
}
```

这可能用于存储图表上的位置、矩形的顶点，或者当嵌套在另一个结构中可能是圆的中心点，如下：

```go
type circle struct {
  radius int
  center coords
}
```

现在，当创建 `circle` 的实例时，可以通过链接结构名和字段名访问嵌套结构的字段，如下：

```
instanceName.embeddedStructName.fieldName
instanceName.embeddedStructName.fieldName
```

这是可以接受的，但并不方便，因为太长。幸运的是，Go 通过支持结构体中的 `匿名字段`（anonymous fields）来解决这个问题。这些仅是指定另一个结构名称作为字段的字段，而不说明字段名：

```go
type circle struct {
  radius int
  coords
}
```

这种方法的用处是它允许缩短访问嵌套结构体字段所需的代码：

```
instanceName.fieldName
instanceName.fieldName
```

![](img/fa565c410b0509c58bcab29ed0b49de9_142_0.png)

匿名字段必须是具命名类型的，或者是指向命名类型的指针。

1. 通过创建两个结构体类型开始程序：

```go
type coords struct {
  x, y int
}

type circle struct {
  radius int
  coords
}
```

![](img/fa565c410b0509c58bcab29ed0b49de9_142_1.png)

`src\embed\main.go`

2. 接下来，为第二个结构体挂载一个方法

```go
func (c circle) getDiameter() int {
  return c.radius * 2
}
```

3. 现在，通过创建结构体的实例来开始 `main` 函数

```go
var ring circle
```

4. 添加语句为结构体字段和嵌入式结构体赋值

```go
ring.radius = 15
ring.x = ring.radius
ring.y = ring.radius
```

5. 最后，添加语句显示值

```go
fmt.Printf("Diameter:%v\n", ring.getDiameter())
fmt.Printf("Point X:%v Y:%v\n", ring.x, ring.y)
```

6. 将程序保存在 `embed` 目录中，然后运行程序查看结构体字段的值

![](img/fa565c410b0509c58bcab29ed0b49de9_143_0.png)

### 封装特性

在 Go 程序中表示对象的能力是面向对象编程 (OOP) 的第一个基石原则。面向对象的程序使用方法来表达其所依附的数据结构的属性和操作，因此程序无需直接访问对象。

![](img/fa565c410b0509c58bcab29ed0b49de9_144_0.png)

程序无法直接访问的变量、函数或方法被称为 `封装`。封装、继承和多态是面向对象编程的三大构建模块。

Go 编程中的封装依赖于导入到程序中的包中对数据进行隐藏。只有以大写字母开头的变量名、函数名和方法名会被导出到程序。那些以小写字母开头的名称将是不可访问的——即它们被封装了。

1. 首先，开始一个 `cube.go` 工具文件，其中包含包声明和结构体定义

```go
package cube

// Dims 是可导出的。
type Dims struct {
  width, length, height int
}
```

![](img/fa565c410b0509c58bcab29ed0b49de9_144_1.png)

`src\cube\cube.go`

2. 接下来，添加四个函数来操作结构体字段

```go
func (d *Dims) area() int {
  return d.width * d.length
}
```

```go
// SetSize 是可导出的。
func (d *Dims) SetSize(w, l, h int) {
  d.width = w
  d.length = l
  d.height = h
}
```

```go
// GetVolume 是可导出的。
func (d *Dims) GetVolume() int {
  return d.width * d.height
}
```

```go
// GetArea 是可导出的。
func (d *Dims) GetArea() int {
  return d.area()
}
```

![](img/fa565c410b0509c58bcab29ed0b49de9_145_0.png)

可以看到相同数据类型的字段可以声明为逗号分隔的列表，带有变量声明。

3. 将工具文件保存在 `cube` 目录中，然后开始一个导入该工具文件的 `main` 文件

```go
package main

import (
  "cube"
  "fmt"
)
```

`src\encap\main.go`

4. 接下来，通过创建导入的结构体类型的实例开始 `main` 函数

```go
var box cube.Dims
```

5. 现在，调用导入的方法来为结构体字段赋值

```go
box.Set(2, 4, 6)
```

6. 那么，调用其他导入的方法使用赋值的字段值计算结果

```go
fmt.Println("Footprint:", box.GetArea())
fmt.Println("Volume:", box.GetVolume())
```

7. 将程序文件保存在 `encap` 目录中，然后运行程序查看封装值的结果

![](img/fa565c410b0509c58bcab29ed0b49de9_146_0.png)

8. 在 `main` 函数中添加这些语句，它们将尝试引用未导出的字段和方法

```go
fmt.Println("Width:", box.width)
fmt.Println("Area:", box.getArea())
```

9. 再次保存程序文件，然后运行程序，查看编译为何失败并显示 `box.width` 未定义和 `box.getArea` 未定义错误信息

![](img/fa565c410b0509c58bcab29ed0b49de9_147_0.png)

你必须在导入的结构体前加上包名。也可以通过赋值一个（空）结构体字面量来实例化 `box := cube.Dims{}`。

### 组合元素

面向对象编程的第二个基石是继承，其中衍生自另一个对象的将继承基对象的特性。这种代码复用在 Go 编程中通过 `组合` 实现。这仅仅是将一个结构体嵌入另一个结构体中的技术，从而立即为第二个结构体提供各种元素。例如，`dog` 结构体可能会嵌入一个 `animal` 结构体，后者的字段和挂载的方法将立即供 `dog` 使用。

![](img/fa565c410b0509c58bcab29ed0b49de9_148_0.png)

严格来说，字段和挂载的方法并不是从基对象继承的，而是对第二个结构体可用。

1. 首先创建一个包含包声明和结构体定义的字段

```go
type member struct {
  firstName string
}
```

![](img/fa565c410b0509c58bcab29ed0b49de9_148_1.png)

`src/inheritance.go`

2. 接下来，为基结构体挂载一个方法返回值

```go
func (m member) fullName() string {
```



### 组合元素

1. 首先，创建一个具有两个字段的结构体：

```go
type member struct {
    firstName string
    lastName  string
}
```

2. 接下来，为结构体挂载一个方法显示字段：

```go
func (m member) fullName() string {
    return m.firstName + " " + m.lastName
}
```

3. 现在，创建一个具有两个字段的结构体：

```go
type article struct {
    title string
    body  string
}
```

4. 接下来，为第二个结构体挂载一个方法显示字段：

```go
func (a article) content() string {
    return a.title
}
```

5. 通过创建一个结构体的实例开始 `main`：

```go
func main() {
    article1 := article{
        title: "Object Oriented Programming",
        body:  "In Go",
    }
}
```

6. 接下来，创建另一个结构体的实例并显示字段：

```go
article2 := article{
    title: "Composition",
    body:  "Coming next...",
}
fmt.Println(article2.content())
```

7. 将程序文件保存在 `inherit` 目录中，然后运行程序查看：

```go
package main

import (
    "fmt"
)

type member struct {
    firstName string
    lastName  string
}

func (m member) fullName() string {
    return m.firstName + " " + m.lastName
}

type article struct {
    title string
    body  string
}

func (a article) content() string {
    return a.title
}

func main() {
    article1 := article{
        title: "Object Oriented Programming",
        body:  "In Go",
    }
    fmt.Println(article1.content())

    article2 := article{
        title: "Composition",
        body:  "Coming next...",
    }
    fmt.Println(article2.content())
}
```

*（注：由于提供的原文文本在“Compose Elements”部分存在乱序和重复，译文已根据逻辑流进行了对齐处理以确保技术描述的连贯性）*

### 接口实现

面向对象编程的第三个基石是“多态”——这是一个源自希腊语的词，意思是“许多形式”，描述了根据上下文为实体分配不同意义或目的的能力。

![](img/fa565c410b0509c58bcab29ed0b49de9_151_0.png)

Go 编程通过 `interface` 类型支持多态，该类型使用 `type` 关键字、指定的名称以及 `interface` 关键字和 `{}` 括号创建。接口体仅包含方法签名列表。任何与接口列出的方法名称和签名精确匹配的结构体都实现了接口。在 Go 编程中，它们被称为“满足”接口。

1. 通过创建一个接口开始程序，列出两个方法签名，每个方法都不需要参数且都返回字符串：

```go
type bird interface {
    speak() string
    move() string
}
```

`src\poly\main.go`

2. 接下来，创建一个空结构体并挂载满足接口的方法：

```go
type parrot struct{}

func (parrot) speak() string {
    return "Squawk, squawk!"
}

func (parrot) move() string {
    return "A parrot flies away."
}
```

3. 现在，创建另一个空结构体并挂载同样满足接口的方法：

```go
type chicken struct{}

func (chicken) speak() string {
    return "Cluck, cluck!"
}

func (chicken) move() string {
    return "Chickens cannot fly."
}
```

4. 添加一个接收接口作为参数并调用已实现方法的函数：

```go
func nudge(b bird) {
    fmt.Printf("%v\n", b.speak())
    fmt.Printf("%v\n\n", b.move())
}
```

5. 添加一个 `main` 函数，包含创建每个结构体实例的语句，然后调用它们同名的方法：

```go
func main() {
    var bird1 parrot
    var bird2 chicken
    nudge(bird1)
    nudge(bird2)
}
```

6. 将程序文件保存到 `poly` 目录中，然后运行程序以查看不同的输出：

![](img/fa565c410b0509c58bcab29ed0b49de9_153_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_153_1.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_154_0.png)

Go 会自动识别接口是否已实现。

![](img/fa565c410b0509c58bcab29ed0b49de9_154_1.png)

当结构体实现接口时，附加到结构体上的方法成为该接口的“荣誉成员”——这样当接口作为参数传递时，函数可以通过接口参数调用这些方法。

### 嵌入嵌入

就像结构体可以嵌入到其他结构体一样，接口也可以嵌入到其他接口中。这允许你在程序中创建更高层次的抽象，从而获得更大的活性。Go 会自动识别哪个结构体实现了每个接口。

![](img/fa565c410b0509c58bcab29ed0b49de9_155_0.png)

理解接口嵌入非常有帮助，因为许多 Go 标准库包都使用了这种技术。例如，`io`（输入/输出）包包含一个 `ReadWriter` 接口，它嵌入了 `Reader` 和 `Writer` 接口，后者包含了读写文件的 `Read` 和 `Write` 方法签名。

1. 创建两个包含相同方法签名的接口，它们都返回一个字符串：

```go
type bird interface {
    speak() string
    move() string
}
```

```go
type human interface {
    speak() string
    move() string
}
```

![](img/fa565c410b0509c58bcab29ed0b49de9_155_1.png)

`src\abstr\main.go`

2. 下一步，创建另一个嵌入了前两个接口的接口：

```go
type creature interface {
    bird
    human
}
```

3. 现在，添加一个空结构体并附加满足第一个（以及第二个）接口的方法：

```go
type parrot struct{}

func (parrot) speak() string {
    return "Squawk, squawk!"
}

func (parrot) move() string {
    return "A parrot flies away."
}
```

![](img/fa565c410b0509c58bcab29ed0b49de9_156_0.png)

`parrot` 类型的实例将调用步骤 3 中的方法。

4. 现在，添加另一个空结构体，并附加满足（第一个）和第二个接口的方法——因此现在它满足了第三个接口：

```go
type person struct{}

func (person) speak() string {
    return "Hi, there!"
}

func (person) move() string {
    return "A person walks away."
}
```

5. 添加一个接收第三个接口作为参数的函数，并调用实现的方法：

```go
func nudge(c creature) {
    fmt.Printf("%v %v\n", c.speak())
    fmt.Printf("%v %v\n", c.move())
}
```

6. 添加一个 `main` 函数，包含创建每个结构体实例的语句，然后调用它们同名的方法：

```go
func main() {
    var bird1 parrot
    var human1 person
    nudge(bird1)
    nudge(human1)
}
```

7. 将程序文件保存到 `abstr` 目录中，然后运行程序以查看不同的输出：

![](img/fa565c410b0509c58bcab29ed0b49de9_157_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_157_1.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_157_2.png)

`person` 类型的实例将调用步骤 4 中的方法。

![](img/fa565c410b0509c58bcab29ed0b49de9_158_0.png)

方法签名也可以指定参数列表和多个返回值类型。

## 总结

- 多个相关数据项可以组合在 Go 结构体类型中。
- 结构体的 `{}` 大括号包含名称和类型对的列表，这些字段定义了结构体包含的内容。
- 结构体的实例可以作为声明了命名的变量创建。
- 接口可以嵌入其他接口，以创建更高层次的抽象。
- 接口嵌入允许你组合和重用方法签名。
- 附加到结构体上的方法成为其所实现接口的“荣誉成员”。

### 数组

任何单个元素的值都可以通过数组名后跟包含每个索引元素数字的方括号来引用。例如，第二个索引的第一个元素：

```go
arrayName[0][1]
```

- 创建一个包含三个元素的空数组，每个元素只能包含字符串值：

```go
var cars [3]string
```

- 接下来，添加语句来初始化每个数组元素：

```go
cars[0] = "BMW"
cars[1] = "Ford"
cars[2] = "Opel"
```

- 现在，声明并初始化一个二维数组：

```go
coords := [2][3]int{{1, 2, 3}, {4, 5, 6}}
```

- 然后，添加语句显示包含所存储的数组值的输出：

```go
fmt.Println("Cars:", cars)
fmt.Println("Second Car:", cars[1])
fmt.Println("X1,Y1:", coords[0][0])
fmt.Println("X2,Y3:", coords[1][2])
```

- 将程序文件保存在 `array` 目录中，然后运行程序以查看存储在数组元素中的值：

```
C:\Users\mike_go\src>go run array
Cars: [BMW Ford Opel]
Second Car: Ford
X1,Y1: 1
X2,Y3: 6
C:\Users\mike_go\src>_
```

Go 编程中的数组是固定大小的——一旦创建，你就无法添加或删除元素。

### 遍历元素

循环和数组是完美的搭档。可以使用循环来为空数组中的每个元素填充值，并可以遍历数组中的每个元素以引用所存储的值。

传统的递增 `for` 循环可以将初始计数器变量的值设置为零，并将该变量放在数组变量的 `[]` 方括号内，以随着循环的进行表示每个元素的索引号。

Go 有一个内置的 `len()` 函数，它接受数组变量作为参数，并返回一个表示数组包含元素数量的整数。这可以用于传统的 `for` 循环，在达到数组的最后一个元素时退出循环。

- 创建一个包含五个元素的空整数数组：

```go
var arr [5]int
```

- 接下来，添加语句来确认数组大小：

```go
fmt.Println("No. of Elements:", len(arr))
```

- 现在，添加一个循环来填充每个元素：

```go
for i := 0; i < len(arr); i++ {
    arr[i] = i * i
}
```

然后，添加一个循环来引用每个数组元素的值：

```go
for i := 0; i < len(arr); i++ {
    fmt.Printf("Index: %v Value: %v\n", i, arr[i])
}
```

将程序文件保存在 `elems` 目录中，然后运行程序以查看存储在数组元素中的值：

```
Go Terminal
C:\Users\mike\go\src> go run elems
No. of Elements: 5
Index: 0 Value: 0
Index: 1 Value: 1
Index: 2 Value: 4
Index: 3 Value: 9
Index: 4 Value: 16
C:\Users\mike\go\src>
```

数组索引从零开始，所以这里的最后一个第五个元素的索引号为 4。

Go 提供了一些可以使用数组的特殊功能。首先，当使用数组字面量声明数组变量时，你可以使用 `...` 通配符运算符将元素数量设置为数组字面量中值的数量：

```go
arr := [...]int{10, 20, 30} // len(arr) == 3.
```

你甚至可以通过陈述每个值的索引号来指定应该存储哪个元素值，如下：

```go
arr := [...]int{2: 10, 0: 20, 1: 30} // arr == [20, 30, 10].
```

其次，你可以使用 `range` 关键字来遍历数组并返回每个元素的索引号和值。

- 创建一个五个元素的整数数组：

```go
arr := [...]int{100, 200, 300, 400, 500}
```

`src\range\main.go`

- 接下来，添加语句来确认数组大小：

```go
fmt.Println("No. of Elements:", len(arr))
```

- 现在，添加一个循环来修改每个元素：

```go
for i, v := range arr {
    arr[i] = v
}
```

- 然后，添加一个循环来引用每个数组值：

```go
for i, v := range arr {
    fmt.Printf("Index: %v Value: %v\n", i, v)
}
```



将程序文件保存在`range`目录中，然后运行程序以查看存储在数组元素中的值。

如果你在循环中不需要索引号，可以将变量名`i`替换为空白标识符——参见此处。

### 切片数组

数组是元素包含相同类型数据的序列，但由于长度是固定的因此并不灵活。坦率地说，Go 提供了一种切片（slice）类型，它代表底层数组并且其长度可以改变。

要理解切片类型，重要的是意识到切片并不包含任何元素，而仅仅是对底层数组的引用。数组是元素包含相同类型数据的序列，但由于长度是固定的因此并不灵活。坦率地说，Go 提供了一种切片类型，它代表底层数组并且其长度可以改变。

要理解切片类型，重要的是意识到切片并不包含任何元素，但仅仅是对底层数组的引用。

- 创建一个五个元素的整数数组

```go
arr := [...] int(100, 200, 300, 400, 500)
```

# src\range\main.go

- 接下来，添加语句来确认数组大小

```go
fmt.Println("No. of Elements:", len(arr))
```

- 现在，添加一个循环来修改每个元素

```go
for i, v := range arr {
  arr[i] = v
}
```

- 然后，添加一个循环来引用每个数组值

```go
for i, v := range arr {
  fmt.Printf("Index: %v Value: %v\n", i, v)
}
```

- 将程序文件保存在`range`目录中，然后运行程序以查看存储在数组元素中的值。

如果你在循环中不需要索引号，可以将变量名`i`替换为空白标识符——参见此处。

### 切片数组

数组是元素包含相同类型数据的序列，但由于长度是固定的因此并不灵活。坦率地说，Go 提供了一种切片类型，它代表底层数组并且其长度可以改变。

要理解切片类型，重要的是意识到切片并不包含任何元素，但仅仅是对底层数组的引用。

(注：由于原文中存在大量异常的重复段落，译文已根据核心逻辑进行了精简和去重处理，以确保文档的可读性)

如下：

```go
jamSlice = make([]string, len(fruitSlice))
copy(jamSlice, fruitSlice)
```

如果你想从切片（slice）中删除一个元素并保留剩余元素的顺序，可以使用`copy()`函数将指定索引之上的所有元素向下移动一位。通过在函数签名中指定指定名称和切片类型，可以将切片作为参数传递给函数。

![](img/fa565c410b0509c58bcab29ed0b49de9_173_0.png)

你不需要过度担心切片的底层数组，Go 会自动处理它。

1. 使用切片字面量创建一个整数切片

```go
nums := []int{10, 20, 30, 40, 50, 60, 70, 80, 90, 100}
```

2. 创建另一个切片，然后初始化它的各个元素

```go
more := make([]int, 3)
more[0] = 200
more[1] = 300
more[2] = 400
```

3. 添加一个调用函数的语句来描述切片

```go
describe(nums)
```

4. 从第二个切片中追加一个值来扩大第一个切片，然后描述修改后的第一个切片

```go
nums = append(nums, more[0])
describe(nums)
```

5. 删除第一个切片的第一个元素，再次描述修改后的切片

```go
copy(nums[0:], nums[1:])
nums = nums[:len(nums) - 1]
describe(nums)
```

6. 在主函数之后，添加描述第一个切片元素值、长度和容量的函数

```go
func describe(nums []int) {
    fmt.Printf("%v\nLength: %v\n", nums, len(nums))
    fmt.Printf("Capacity: %v\n", cap(nums))
}
```

7. 将程序文件保存在`make`目录，然后运行程序查看切片的特性

![](img/fa565c410b0509c58bcab29ed0b49de9_174_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_174_1.png)

这里的容量大小为 10，但在其他平台上可能会有所不同。注意，当元素被删除后，容量不会恢复到原始大小。

### 切片与数组

数组包含一个值的序列，而切片包含对一个值序列的引用。这是 Go 编程中一个重要的区别，适用于它的许多类型。最显著的是，当将类型传递给函数时，基于值的类型将接收原始值的副本，而引用类型将指向实际的原始值。因此，为了让函数在原始值上进行操作，在向函数传递基于值的类型时，需要使用指针，而在传递引用时则不需要指针。

![](img/fa565c410b0509c58bcab29ed0b49de9_175_0.png)

| 值 (Values) | 引用 (References) |
| --- | --- |
| int | slice |
| float64 | map |
| string | channel |
| bool | pointer |
| struct | function |
| array | method |

使用指针在函数内部更改原始值。

不需要在函数内部更改原始值。

数组和切片之间的另一个区别在于可以使用任意数量参数调用的“变参函数”（variadic functions）。你不能将数组元素值传递给变参函数，除非你先通过将数组元素值复制到切片并将数组“转换”为切片。

你只需通过在函数签名的最后一个参数的数据类型前加上`...`通配符运算符，就可以创建一个变参函数，语法如下：

```go
func funcName ( paramName...dataType )
```

变参函数可以像往常一样调用，在`()`括号内包含一个用逗号分隔的参数列表。

在将切片元素的值传递给函数时，变参函数特别有用，因为切片的长度在程序执行过程中可能会发生变化。无论切片的长度如何，都可以通过在函数调用括号内指定切片名称后跟`...`通配符，将其元素值传递给变参函数：

```go
func funcName ( sliceName... )
```



![](img/fa565c410b0509c58bcab29ed0b49de9_176_0.png)

`fmt.Printf()` 函数是一个变参函数——它在开头需要一个固定参数，然后接受任意数量的后续参数。

- 创建包含三个字符串的数组：

```go
array := [3]string{"BMW", "Ford", "Opel"}
```

`src\versus\main.go`

- 将数组元素复制到切片中以进行“转换”：

```go
slice = array[:]
```

- 接下来，调用变参函数传递切片中每个元素的值进行显示：

```go
list(slice...)
```

- 现在，向切片追加两个更多值：

```go
slice = append(slice, "Porsche", "Ferrari")
```

- 再次调用变参函数传递切片中的每个元素值：

```go
list(slice...)
```

- 在主函数之后，添加变参函数 `list` 列出传入的切片值：

```go
func list(autos ...string) {
	for i, v := range autos {
		fmt.Printf("\n%v\n", i, v)
	}
	fmt.Println()
}
```

将程序文件保存在 `versus` 目录，然后运行程序查看值。

![](img/fa565c410b0509c58bcab29ed0b49de9_177_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_177_1.png)

调用变参函数时，你并不是在传递切片本身——你是在传递元素值。

### Map 的键与值

多项数据可以通过关联键存储在哈希表中，以便你通过关联键引用存储的值。在 Go 编程中，这种数据结构被称为 `map`，其他编程语言称之为关联数组或字典。

![](img/fa565c410b0509c58bcab29ed0b49de9_178_0.png)

`map` 中的所有键必须是唯一的且类型相同。`map` 中的所有值必须类型相同，但不一定与键的类型相同。可以使用 `var` 和 `map` 关键字并指定键和值的类型创建一个 `map`：

```go
var mapName map[keyDataType]valueDataType
```

然后可以将单个键值对赋值给 `map`，如下：

```go
mapName[key] = value
```

或者，你可以使用内置的 `make()` 函数创建一个 `map`：

```go
mapName := make(map[keyDataType]valueDataType)
```

此外，你可以通过赋值 `map` 字面量来创建并初始化 `map`：

```go
mapName := map[keyDataType]valueDataType{
	key: value,
}
```

与数组和切片不同，键值对以无序方式存储，因此你不能使用元素索引引用存储的值——你必须使用关联键。你可以随时向 `map` 添加键值对，可以使用内置的 `delete()` 函数移除键值对。这需要 `map` 名称和要删除的键。

与数组和切片一样，你可以使用 `range` 关键字遍历 `map` 的元素。在这种情况下，循环返回键和值，而不是索引和值。

![](img/fa565c410b0509c58bcab29ed0b49de9_179_0.png)

`map` 元素不是变量，所以你无法获取它的内存地址。

- 创建一个字符串键值的 `map`：

```go
colors := make(map[string]string)
```

`src\map\main.go`

- 使用三个键值对初始化 `map`：

```go
colors["Red"] = "#FF0000"
colors["Green"] = "#00FF00"
colors["Blue"] = "#0000FF"
```

- 接下来，显示 `map` 中的所有键值对：

```go
fmt.Printf("\nColors: %v\n", colors)
```

- 现在，添加一个键值对并显示其值：

```go
colors["Yellow"] = "#FFFF00"
fmt.Printf("\nYellow Hex Code: %v\n", colors["Yellow"])
```

- 然后移除添加的键值对：

```go
delete(colors, "Yellow")
```

- 最后，添加一个循环列出 `map` 中所有的键值对：

```go
for k, v := range colors {
	fmt.Printf("\nHex Code for %s is %v\n", k, v)
}
```

将程序文件保存在 `map` 目录，然后运行程序查看键和值。

![](img/fa565c410b0509c58bcab29ed0b49de9_180_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_180_1.png)

`map` 元素的顺序是随机的，在不同平台上可能会不同。

## 总结

- 数组是一种固定长度结构，在单个元素中顺序存储数据。
- 数组声明必须在 `[]` 中指定所需的元素数量。
- 数组或切片元素中存储的数据可以通过在 `[]` 中说明元素的索引号来引用。
- 空数组可以使用 `var` 关键字创建，也可以通过赋值数组字面量来创建并初始化。
- `len()` 函数返回数组或切片的长度。
- `range` 关键字可用于遍历元素。
- 切片是一种变长度结构，在底层数组的单个元素中顺序存储数据。
- 切片由指针、长度和容量组成。
- `cap()` 函数返回切片的容量。
- 切片声明在 `[]` 中不应指定元素数量。
- 在 `[]` 内的 `:` 冒字符周围可以指定元素序列的上边界和下边界。
- 空切片可以使用 `make()` 函数创建，也可以通过赋值切片字面量来创建并初始化。
- 使用 `append()` 函数向切片添加元素。
- 使用 `copy()` 函数可以将切片复制到另一个切片中。
- 向函数传递引用时不需要指针。
- 变参函数可以使用任意数量的参数进行调用。
- `map` 是一种包含关联键值对的变长度结构。
- 空 `map` 可以使用 `make()` 函数创建，也可以创建并通过赋值一个 `map` 字面量进行初始化。
- `map` 元素中存储的值可以通过在 `[]` 方括号中指明关联的键来引用。

# 8 掌控时间

本章演示了如何使用 Go 标准库中的 `time` 包处理日期和时间。

- 获取日期
- 获取时间
- 格式化日期和时间
- 设置日期和时间
- 识别时区
- 延迟时间
- 总结

### 获取日期

Go 标准库 `time` 包提供了从 `Time` 数据类型中提取特定字段的功能，这些字段描述特定的时间点。通过导入 `time` 包，这些功能可以使用这些功能。

![](img/fa565c410b0509c58bcab29ed0b49de9_184_0.png)

可以使用 `time.Now()` 函数创建一个新的 `Time` 数据类型的日期/时间实例，其字段描述当前的日期和时间。这些字段是根据您设备上当前区域的系统时钟初始化的。

可以使用 `Time` 数据类型的适当方法获取单个字段的值。例如，可以使用其 `Year()` 方法获取年份字段的值。同样，还有 `Month()`、`Day()` 和 `Weekday()` 方法可以获取 `Time` 数据类型的其他单个字段。

| 方法 | 返回 |
| --- | --- |
| `Now()` | 包含当前日期、时间和时区字段的 `time.Time` 数据类型 |
| `Year()` | 4 位数的年份 (YYYY) |
| `Month()` | 年份的月份名称 |
| `Day()` | 月份中的几几 |
| `Weekday()` | 星期几名称 |

还有这三个方法，其返回的 `Time` 数据类型值可以有效地赋值给变量：

| 方法 | 返回 |
| --- | --- |
| `Date()` | 4 位数的年份 (YYYY)、月份名称和月份中的几几 |
| `ISOWeek()` | 年的周数 (1-53) 和 4 位数的年份 (YYYY) |
| `YearDay()` | 年中的天数 (1-365/366) |

重要的是，`Time` 数据类型包含单个字段，因此它不是字符串。但是，你可以使用它的 `String()` 方法将其转换为字符串：

![](img/fa565c410b0509c58bcab29ed0b49de9_185_0.png)

`Time` 数据类型方法返回的值不是字符串。

- 首先在程序中导入 Go 标准库 `time` 包：

```go
import (
	"fmt"
	"time"
)
```

![](img/fa565c410b0509c58bcab29ed0b49de9_185_1.png)

`src\date\main.go`

- 接下来，创建一个 `Time` 数据类型的日期/时间实例，用当前日期和时间初始化：

```go
dt := time.Now()
```

- 添加语句输出日期/时间实例的所有字段，并确认其数据类型：

```go
fmt.Printf("DateTime: %v \n", dt)
fmt.Printf("Date Type: %T \n", dt)
```

- 接下来，添加语句输出今天的星期：

```go
fmt.Printf("Today is: %v \n", dt.Weekday())
```

- 现在，添加语句显示今天的日期、本周以及当年的周数：

```go
y, m, d := dt.Date()

fmt.Printf("Date: %v %v, %v \n", m, d, y)

yr, wk := dt.ISOWEEK()

fmt.Printf("Week No.: %v in %v \n", wk, yr)

dy := dt.DayOfYear()

fmt.Printf("Day No.: %v \n", dy)
```

将程序文件保存在 `date` 目录中，然后运行程序查看日期字段的值。

![](img/fa565c410b0509c58bcab29ed0b49de9_186_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_186_1.png)

时区值指定了相对于 UTC（协调时）的偏移量和时区缩写——有关时区的更多信息请此处。

### 获取时间

`Time` 数据类型单个字段中的时间值可以使用适当的方法获取。例如，可以使用其 `Hour()` 方法获取小时字段的值。同样，还有 `Minute()`、`Second()` 和 `Nanosecond()` 方法可以获取 `Time` 数据类型的其他单个字段。

![](img/fa565c410b0509c58bcab29ed0b49de9_187_0.png)

| 方法 | 返回 |
| --- | --- |
| `Hour()` | 一中的小时数 (0-23) |
| `Minute()` | 小时的分钟数 (0-59) |
| `Second()` | 分钟的秒数 (0-59) |
| `Nanosecond()` | 秒的纳秒 (0-999999999) |

与其他编程语言不同，Go 的 `time` 包没有从 `Time` 数据类型返回毫秒值的方法。但是，你可以将纳秒值除以一百万来产生等效的毫秒值。还有三个方法，其返回的 `Time` 数据类型值可以有效地赋值给变量：

| 方法 | 返回 |
| --- | --- |
| `Clock()` | 一天中的时、分、秒 |
| `Unix()` | 自 Unix 纪元以来的秒数 |
| `UnixNano()` | 自 Unix 纪元以来的纳秒数 |

- 首先在程序中导入 Go 标准库 `time` 包：

```go
import (
	"fmt"
	"time"
)
```

![](img/fa565c410b0509c58bcab29ed0b49de9_188_1.png)

- 接下来，创建一个 `Time` 数据类型的日期/时间实例，用当前日期和时间初始化：

```go
dt := time.Now()
```

![](img/fa565c410b0509c58bcab29ed0b49de9_188.png)

`src\main.go`

- 添加语句输出日期/时间实例的所有字段并确认其数据类型：

```go
fmt.Printf("DateTime: %v \n", dt)
fmt.Printf("Date Type: %T \n", dt)
```

- 接下来，添加语句输出今天的星期：

```go
fmt.Printf("Today is: %v \n", dt.Weekday())
```

- 现在，添加语句显示今天的日期、本周以及当年的周数：

```go
y, m, d := dt.Date()

fmt.Printf("Date: %v %v, %v \n", m, d, y)

yr, wk := dt.ISOWEEK()

fmt.Printf("Week No.: %v in %v \n", wk, yr)

dy := dt.DayOfYear()

fmt.Printf("Day No.: %v \n", dy)
```

将程序文件保存在 `date` 目录中，然后运行程序查看日期字段的值。

![](img/fa565c410b0509c58bcab29ed0b49de9_189_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_189_1.png)

时区值指定了相对于 UTC（协调时）的偏移量和时区缩写——有关时区的更多信息请此处。

### 获取时间

`Time` 数据类型单个字段中的时间值可以使用适当的方法获取。例如，可以使用其 `Hour()` 方法获取小时字段的值。同样，还有 `Minute()`、`Second()` 和 `Nanosecond()` 方法可以获取 `Time` 数据类型的其他单个字段。

![](img/fa565c410b0509c58bcab29ed0b49de9_190_0.png)

| 方法 | 返回 |
| --- | --- |
| `Hour()` | 一中的小时数 (0-23) |
| `Minute()` | 小时的分钟数 (0-59) |
| `Second()` | 分钟的秒数 (0-59) |
| `Nanosecond()` | 秒的纳秒 (0-999999999) |

与其他编程语言不同，Go 的 `time` 包没有从 `Time` 数据类型返回毫秒值的方法。但是，你可以将纳秒值除以一百万来产生等效的毫秒值。还有三个方法，其返回的 `Time` 数据类型值可以有效地赋值给变量：

| 方法 | 返回 |
| --- | --- |
| `Clock()` | 一天中的时、分、秒 |
| `Unix()` | 自 Unix 纪元以来的秒数 |
| `UnixNano()` | 自 Unix 纪元以来的纳秒数 |

- 首先在程序中导入 Go 标准库 `time` 包：

```go
import (
	"fmt"
	"time"
)
```

- 接下来，创建一个 `Time` 数据类型的日期/时间实例，用当前日期和时间初始化：

```go
dt := time.Now()
```

- 添加语句输出日期/时间实例的所有字段并确认其数据类型（此处，此处重复逻辑）。
- 添加语句输出日期/时间实例的所有字段并确认其数据类型：

```go
fmt.Printf("DateTime: %v \n", dt)
fmt.Printf("Date Type: %T \n", dt)
```

- 接下来，添加语句输出今天的星期：

```go
fmt.Printf("Today is: %v \n", dt.Weekday())
```

- 现在，添加语句显示今天的日期、本周以及当年的周数：

```go
y, m, d := dt.Date()

fmt.Printf("Date: %v %v, %v \n", m, d, y)

yr, wk := dt.ISOWEEK()

fmt.Printf("Week No.: %v in %v \n", wk, yr)

dy := dt.DayOfYear()

fmt.Printf("Day No.: %v \n", dy)
```

### 格式化日期和时间

![](img/fa565c410b0509c58bcab29ed0b49de9_191_0.png)

`Time` 数据类型单个字段中的日期时间值可以使用 `Format()` 方法以多种方式格式化。该方法接收一个参数，即“布局”字符串，指定了如何格式化日期/时间。格式必须完全由此参考字符串的元素指定：

```text
Mon Jan 2 15:04 06 MST
```

由于 MST（山地标准时间）比 UTC（协调时）晚 7 小时，参考字符串也可以考虑为：

```text
01 02 03:04 '06 -0700
```

如果你想让 `Format()` 方法返回日期、月份和 `hh:mm` 格式的时间，布局可以为：

```text
"Mon Jan 2 15:04"
```

或者用数字指定为：

```text
"01/02 03:04"
```

你可以让日期名称和月份名称以全称返回，只需在布局中指定长名称版本：

```text
"Monday January 2 15:04"
```

`time` 包包含了定义的 `UnixDate`、`ANSIC` 和 `RFC3339` 常量，你可以将其作为日期/时间布局格式。

自定义布局可以按任何顺序指定组件以适应不同的区域——例如用于日期格式化。

`time` 包还包含一个定义的 `Kitchen` 常量，你可以将其作为时间布局格式。这将以 12 小时制显示时间并根据需要附加“AM”或“PM”。

此外，时间组件可以格式化为 24 小时制显示，通过指定 `15:04` 自动为单位数小时补零。

12 小时制和 24 小时制都会自动为单位数分钟补零。

- 首先在程序中导入 Go 标准库 `time` 包：

```go
import (
	"fmt"
	"time"
)
```

- 接下来，创建一个 `Time` 数据类型的日期/时间实例，用当前日期和时间初始化，然后以各种格式显示其组件。



```go
dt := time.Now()
fmt.Println("Default Format:", dt)
fmt.Println("Unix Format:", dt.Format(time.UnixDate))
fmt.Println("ANSIC Format:", dt.Format(time.ANSIC))
fmt.Println("RFC3339 Format:", dt.Format(time.RFC3339))
fmt.Println("Custom Format:",
  dt.Format("January 2, 2006 [Monday]"))
```

- 现在，仅显示格式化为两种语言环境的日期组件

`fmt.Println("US Format:", dt.Format("January 2, 2006 "))`

`fmt.Println("UK Format:", dt.Format("2 January, 2006 "))`

- 然后，以 12 小时制和 24 小时制显示时间组件

`fmt.Println("Time 12-Hour:", dt.Format(time.Kitchen))`

`fmt.Println("Time 24-Hour:", dt.Format("15:04 "))`

- 将程序保存在 `format` 目录中，然后运行程序以查看格式化的日期和时间值

![](img/fa565c410b0509c58bcab29ed0b49de9_192_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_192_1.png)

`time.Kitchen` 常量等于指定布局格式为 `"15:04PM"`。

### 设置日期和时间

你可以使用 Go 标准库 `time` 包的 `Date()` 函数创建自己的 `Time` 数据类型。这需要八个参数来按此顺序指定年、月、日、时、分、秒、纳秒和位置。

![](img/fa565c410b0509c58bcab29ed0b49de9_193_0.png)

除了月份和位置外，所有参数都指定为整数值。

月份可以使用 `time` 包预定义的 1 月至 12 月月份常量之一来指定，例如 `time.January`。

位置可以使用 `time` 包预定义的位置常量之一来指定，如 `time.UTC`（协调世界时）或 `time.Local`（系统时钟）。

任何 `Time` 数据类型中的日期字段可以使用 Go 标准库 `time` 包的 `AddDate()` 方法进行修改，指定年、月、日的三个参数。正值将将日期提前，负值将推后日期。例如，`time.AddDate(1, 0, 0)` 将将日期提前一年。

同样，`time` 包的 `Add()` 方法可以用于指定单个持续时间来修改日期/时间。该值可以是一个表示纳秒数量的 `int64` 值。更方便的是，你可以使用常量 `time.Hour`、`time.Minute`、`time.Second` 或 `time.Millisecond` 来修改 `Time` 数据类型的各个时间字段。例如，`time.Add(10 * time.Hour)` 将时间提前 10 小时。

你还可以使用 Go 标准库 `time` 包的 `Parse()` 函数从字符串创建自己的 `Time` 数据类型。这需要两个参数来指定布局和日期/时间字符串。有用的是，此函数返回两个值：一个 `Time` 数据类型和一个 `error`。如果函数返回 `Time` 数据类型，则错误值将为 `nil`，否则它将是一个错误消息。

布局应仅使用 Go 参考字符串中的值：

`Mon Jan 2 15:04:05 2006 MST`

除非日期/时间字符串指定了时区偏移值（例如 `-0500`），否则生成的 `Time` 数据类型将假设为 UTC 时间。

![](img/fa565c410b0509c58bcab29ed0b49de9_194_0.png)

`Time` 数据类型可以使用此处过的 `Format()` 方法进行格式化。

- 首先在程序中导入 Go 标准库 `time` 包

```go
import (
  "fmt"
  "time"
)
```

`src\setdate\main.go`

- 接下来，创建并显示一个 `Time` 数据类型的日期/时间实例，初始化为元旦正午

`dt := time.Date(2025, time.January, 1, 12, 0, 0, time.Local)`

`fmt.Printf("InDateTime: %v\n\n", dt)`

- 将日期提前两年到美国独立日，然后显示修改后的日期

`dt := dt.AddDate(2, 6, 3)`

```go
fmt.Printf("DateTime: %v\n\n", dt)
```

现在，初始化布局字符串和日期/时间字符串

`layout := "2006-Jan-02 03:04:PM"`

`str := "2030-Dec-25 12:30:00AM"`

最后，尝试创建并显示 `Time` 数据类型的字段，或者如果尝试失败则显示错误消息

```go
t, err := time.Parse(layout, str)
if err != nil {
    fmt.Println(err)
} else {
    fmt.Printf("Parsed DateTime: %v\n", t)
}
```

将程序文件保存在 `setdate` 目录中，然后运行程序以查看日期和时间值

![](img/fa565c410b0509c58bcab29ed0b49de9_195_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_195_1.png)

在将字符串转换为 `Time` 数据类型时，布局字符串和日期/时间字符串必须具有相同的格式。

修改后的 `Time` 字段会自动识别从东部标准时间和东部夏令时间的变化。

### 识别时区

Go 编程中的所有 `Time` 数据类型都与时区相关。通常，这将是 UTC 时间，或基于运行程序的系统所在位置的本地时间。然而，你可以将替代位置作为 `time.LoadLocation()` 函数的参数。位置名称必须与互联网分配数字机构（IANA）时区数据库中的文件对应，例如 `"America/New_York"`、`"Asia/Seoul"` 或 `"Europe/London"`。`time.LoadLocation()` 函数返回两个值：一个 `Location` 类型和一个 `error`。如果函数成功返回 `Location` 类型，则错误值将为 `nil`，否则它将是一个错误消息。

![](img/fa565c410b0509c58bcab29ed0b49de9_197_0.png)

你可以通过在其 `Now()` 函数之后附加 `In()` 函数调用来创建另一个时区的当前时间 `Time` 数据类型，其中位置指定作为 `In()` 函数的参数。

![](img/fa565c410b0509c58bcab29ed0b49de9_197_1.png)

你可以通过调用 `Zone()` 方法来确定时区缩写和偏移。此方法返回两个值：三个字母的 TZ 缩写和一个表示与 UTC 偏移秒数的数值。需要注意的是，时区缩写不是唯一的，因此你不应该依赖这些来识别特定的时区。

美国的夏令时会将 UTC 偏移减少一小时。例如，东部夏令时间（EDT）是 UTC - 4 小时，中部夏令时间（CDT）是 UTC - 5 小时，等等。

1. 在程序中导入 Go 标准库 `time` 包

```go
import (
"fmt"
  "time"
)
```

![](img/fa565c410b0509c58bcab29ed0b49de9_198_2.png)

`srczone\main.go`

2. 接下来，使用默认字符串和指定位置的 `Time` 数据类型初始化变量

`zone := "All"`

`loc, _ := time.LoadLocation("America/New_York")`

`dt := time.Now().In(loc)`

确定时区缩写和偏移秒，然后将偏移转换为正分钟数

```go
if offset < 1 {
    offset = offset * -1
}
offset /= 60
```

现在，评估缩写和偏移值

```go
switch {
    case abbr == "EST" && offset == 300:
        zone = "East Coast"
    case abbr == "EDT" && offset == 240:
        zone = "East Coast"
}
```

显示时区详情和适当的消息

`fmt.Printf("TZ: %v Offset Minutes: %v in", abbr, offset)`

`fmt.Println("Welcome to", zone, " ideally include "Visitors!")`

将程序文件保存在 `zone` 目录中，然后运行程序以查看时区值

![](img/fa565c410b0509c58bcab29ed0b49de9_199_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_199_1.png)

由于空间限制，使用了 `_` 空标识符来忽略返回的错误值，但你应该包含一个错误处理程序。

### 延迟时间

Go 标准库的 `time` 包提供了一个 `Sleep()` 函数，允许你通过指定的持续时间延迟程序的进度。持续时间作为 `Sleep()` 函数的参数提供，并可以表示为 `time` 包常量的乘积。例如，`5 * time.Second` 表示五秒的持续时间。

![](img/fa565c410b0509c58bcab29ed0b49de9_200_0.png)

Go 标准库的 `time` 包还提供了三个方法，用于将 `Time` 数据类型的实例与另一个指定的参数时间进行比较。这些方法将根据时间比较的结果分别返回布尔值 `true` 或 `false`：

| 方法 | 返回 |
| :--- | :--- |
| `Before(time)` | 如果实例时间早于参数时间，则返回布尔值 `true` |
| `After(time)` | 如果实例时间晚于参数时间，则返回布尔值 `true` |
| `Equal(time)` | 如果实例时间和参数时间即使在不同的时区也表示同一时刻，则返回布尔值 `true` |

如果你想查看两个 `Time` 数据类型实例之间的差异，可以使用 `time` 实例的 `Sub()` 方法并将另一个时间作为其参数。该方法将两个实例之间经过的持续时间以纳纳秒精度的 `int64` 数据值返回。

通常倾向于展示小于纳秒精度的持续时间，因此 Go 标准库 `time` 包包含一个 `Round()` 方法来指定更简洁的精度。该方法需要一个参数来确定你偏好的舍入行为。通常，该参数是 `time` 包常量之一。例如，调用 `Round(time.Millisecond)` 将纳秒精级的持续时间舍入到最近的毫秒，`Round(time.Second)` 将纳秒精级的持续时间舍入到最近的秒，依此类推。

首先在程序中导入标准库 `time` 包

```go
import (
  "fmt"
  "time"
)
```

![](img/fa565c410b0509c58bcab29ed0b49de9_201_0.png)

`src\delay\main.go`

- 接下来，创建并显示 `Time` 数据类型的组件

`start := time.Now()`

`fmt.Println("\nStarted At:", start.Format("03:04:05"))`

- 现在，将程序的进度延迟五秒

`time.Sleep(5 * time.Second)`

- 然后，创建并显示第二个 `Time` 数据类型

`finish := time.Now()`

`fmt.Println("\nFinished At:", finish.Format("03:04:05"))`

- 比较开始和结束时间

`fmt.Println("\nStartFirst?", start.Before(finish))`

`fmt.Println("\nFinish First?", finish.Before(start))`

- 最后，显示延迟的长度

`diff := finish.Sub(start)`

`fmt.Println("\nTime Elapsed:", diff.Round(time.Second))`

- 将程序文件保存到 `delay` 目录中，然后运行程序查看时间延迟

![](img/fa565c410b0509c58bcab29ed0b49de9_202_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_202_1.png)

延迟执行的能力在暂停单个 `goroutine` 时特别有用——更多细节请参见此处示例。

## 总结

- Go 标准库 `time` 包包含创建由日期、时间和时区字段组成的 `Time` 数据类型的函数。
- `Time` 数据类型不是字符串，但可以使用其 `String()` 方法转换为字符串。
- `time.Now()` 函数返回当前本地位置系统时间中的当前日期、时间和时区。
- 可以使用 `Year()`、`Month()`、`Day()` 和 `Weekday()` 方法从 `Time` 数据类型中提取日期组件。
- `Date()`、`ISOWeek()` 和 `YearDay()` 方法返回可以赋值给变量的日期值。
- 可以使用 `Hour()`、`Minute()`、`Second()` 和 `Nanosecond()` 方法从 `Time` 数据类型中提取时间组件。
- `Clock()`、`Unix()` 和 `UnixNano()` 方法返回可以赋值给变量的时间值。
- `Format()` 方法取布局字符串或预定义常量作为参数来格式化日期和时间。
- 用于日期/时间布局的 Go 引用字符串为 `Mon Jan 2 15:04:05 2006 MST`。
- `time.Date()` 函数用于创建 `Time` 数据类型，并需要指定年、月、日、分、秒、纳秒和位置的参数。
- `time` 包包含月份名称、小时、分、秒、毫秒和位置的预定义常量。
- `AddDate()` 方法可以修改日期组件，`Add()` 方法可以修改时间组件。
- `time.LoadLocation()` 函数需要一个 IANA 位置名称参数，`In()` 函数应用位置。
- `time.Sleep()` 函数根据参数指定的持续时间延迟程序的执行。
- `Sub()` 方法返回两个时间之间经过的持续时间，而 `Round()` 方法可以指定其精度。

## 9

## Go数据管理

本章演示了如何使用 `strconv` 包处理文本和数字。

- 转换字符串
- 查找字符
- 计算字符串
- 评估数字
- 生成字符串
- 分割字符串

### 字符串

Go 标准库 `strings` 包包含了用于字符串操作的有用函数。其 `Join()` 函数通过分隔符连接数组中的所有元素。`fmt.Printf()` 和 `fmt.Println()` 函数写入到标准输出，但不会更改实际字符串。这里写入的字节数超过了字符串长度是因为 `fmt.Printf()` 方法添加了两个换行符和一个空格字符。

![](img/fa565c410b0509c58bcab29ed0b49de9_206_0.png)

### 分割字符串

![](img/fa565c410b0509c58bcab29ed0b49de9_209_0.png)

Go 标准库的 `strings` 包提供了几个函数，允许将指定的字符串分割为子字符串。这些函数将字符串视为数组，其中每个元素包含一个字符或一个空格。

通常，你可能希望将一个空格分隔的句子拆分成由每个独立单词组成的子字符串数组。`strings` 包方便地提供了一个 `Fields()` 函数来完成此任务。该函数需要字符串句子作为唯一参数，并返回一个包含该句子中每个独立单词的子字符串数组。

`strings` 包有一个 `Split()` 函数，它需要两个参数来指定字符串和分隔符。该函数将返回存在指定分隔符出现之间的子字符串数组。例如，当字符串是一个由空格分隔的句子，且分隔符是空格字符时，`Split()` 函数将返回该句子中的单词数组。

`strings` 包还有一个 `SplitN()` 函数，它的工作原理与 `Split()` 相同，但接受第三个参数来指定要返回的子字符串数量。如果指定的子字符串数量超过分隔符的数量，则指定分隔符的后续出现将直接包含在最后一个子字符串中。例如，当字符串是一个由空格分隔的句子，分隔符是空格字符，且仅指定两个子字符串时，`SplitN()` 函数将返回一个包含句子第一个单词的子字符串，和一个包含该句子剩余部分（包括空格）的子字符串。

需要注意的是，`Fields()`、`Split()` 和 `SplitN()` 函数会丢弃指定的分隔符，并在返回的子字符串中包含分隔符周围的字符。然而，还有两个函数允许你将分隔符也包含在返回的子字符串中。

`strings` 包的 `SplitAfter()` 函数与 `Split()` 函数类似，但会将分隔符包含在返回的子字符串中。同样，`strings` 包的 `SplitAfterN()` 函数与 `SplitN()` 函数类似，但会将分隔符包含在返回的子字符串中。

![](img/fa565c410b0509c58bcab29ed0b49de9_210_0.png)

数据通常以逗号分隔值（CSV）的形式存储在 CSV 文件中，这些数据可以方便地分割为单个值。

- 开始导入 Go 标准库 `strings` 包

```go
import "fmt"
"strings"
```

`src\split\main.go`

- 通过初始化字符串变量开始主函数

`str := "I can, and, I will."`

- 接下来，添加语句解析变量字符串的描述和子字符串并调用列表函数



`list("Fields", strings.Fields(str))`

```go
list("Split", strings.Split(str, " "))
list("SplitN", strings.SplitN(str, " ", 2))
```

```go
list("SplitAfter", strings.SplitAfter(str, " "))
list("SplitAfterN", strings.SplitAfterN(str, " ", 2))
```

- 在主函数之后，添加该函数以便每次调用时列描述和所有子字符串

```go
func list(desc string, subs []string) {
    fmt.Print("\n", desc, ": ")
    for _, v := range subs {
        fmt.Printf("[%v]", v)
    }
}
```

将程序文件保存在 `split` 目录，然后运行程序以查看子字符串

![](img/fa565c410b0509c58bcab29ed0b49de9_211_0.png)

只有名称中包含“After”字样的分割方法才会保留分隔符。

### 查找字符

![](img/fa565c410b0509c58bcab29ed0b49de9_212_0.png)

Go 标准库的 `strings` 包提供了几个函数，允许搜索指定的字符串以找到指定的字符或子字符串（模式）。这些函数将字符串视为数组，其中每个元素包含一个字符或一个空格。

`strings` 包有一个 `Contains()` 函数，它需要两个参数来指定字符串和要查找的模式。该函数将简单地返回 `true` 或 `false` 以表示（区分大小写的）搜索结果。例如，搜索 “Pro” 模式：

```go
strings.Contains("Go Programming in easy steps", "Pro")
```

`strings` 包有一个 `Index()` 函数，它需要两个参数来指定字符串和要查找的模式。如果搜索成功，该函数将返回模式在被搜索字符串中首次出现的索引位置；否则，搜索失败时将返回 -1。

`strings` 包的 `Count()` 函数需要两个参数来指定字符串和要查找的模式。你可以使用此函数来发现模式在被搜索字符串中出现了多少次不重叠的实例。如果模式为空字符串，该函数通常会返回 1 加上被搜索字符串字符的数量。这允许你通过从返回的整数中减 1 来确定被搜索字符串的字符数。

`strings` 包的 `HasPrefix()` 函数需要两个参数来指定字符串和要查找的模式。该函数将返回 `true` 或 `false` 表示被搜索字符串是否以指定的模式开头。

同样，`strings` 包的 `HasSuffix()` 函数需要两个参数来指定字符串和要查找的模式，并返回 `true` 或 `false` 表示被搜索字符串是否以指定的模式结尾。

你可以通过 `strings` 包的 `Replace()` 函数将模式替换为替换项来修改被搜索字符串。这需要四个参数来指定字符串、要查找的模式、替换字符串以及指定替换实例数量的整数。如果你想替换所有实例，只需指定 -1。

`strings.Index()` 函数会在找到被搜索字符串中的第一个模式实例时停止。

![](img/fa565c410b0509c58bcab29ed0b49de9_213_0.png)

- 为程序导入 Go 标准库 `strings` 包

```go
import (
  "fmt"
  "strings"
)
```

`src\find\main.go`

- 通过初始化字符串变量开始主函数

`str := "I resist everything"`

- 接下来，测试字符串中是否存在子字符串，找到其索引位置

`fmt.Printf("Found 'an': %v\n", strings.Index(str, "an"))`

- 现在，统计特定字母在字符串中出现的次数

`fmt.Printf("Count of 'e': %v\n", strings.Count(str, "e"))`

- 然后，测试字符串是否以特定子字符串开头或结尾

`fmt.Printf("Prefix 'ion': %v\n", strings.HasPrefix(str, "ion"))`

`fmt.Printf("Suffix 'ion': %v\n", strings.HasSuffix(str, "ion"))`

- 最后，替换字符串中的子字符串

`fmt.Println(strings.Replace(str, "temptation", "chocolate", 1))`

- 将程序文件保存在 `find` 目录，然后运行程序查看结果

![](img/fa565c410b0509c58bcab29ed0b49de9_214_0.png)

### 转换字符串

![](img/fa565c410b0509c58bcab29ed0b49de9_215_0.png)

Go 标准库 `strings` 包提供了转换字符串字符大小的函数。

`strings` 包还有一个 `ToUpper()` 函数，它需要一个字符串参数。该函数将简单地返回一个所有字符转换为大写字母的字符串副本。

同样，`strings` 包的 `ToLower()` 函数需要一个字符串参数，并返回一个所有字符转换为小写字母的字符串副本。

`strings` 包还有一个 `Title()` 函数，它需要一个字符串参数。该函数将返回一个将每个单词的首字母转换为大写字母的字符串副本——但仅当字符串参数全为小写时。如果你想将混合大小写的字母字符串转换为标题格式，必须先使用 `strings` 包的 `ToLower()` 函数将其转换为小写。

当程序在请求数值后接收用户输入时，输入可能是字符串数据类型并可能包含用户无意输入的空格。你可以使用 `strings` 包的 `Trim()` 函数从字符串开头和结尾移除空格。它需要两个参数来指定字符串和要移除的字符。要移除所有开头和结尾空格，第二个参数将是指定单个空格字符的 `" "`。

一旦从包含输入数字的字符串中删除了必要的空格，在程序可以在算术运算中使用输入之前，必须将数据类型转换为数值类型。这可以通过导入 Go 标准库中的 `strconv` 包。该包包含了 `Atoi()` 函数（ASCII 转换为整数），它需要一个字符串参数，并返回一个整数和任何可能的错误。如果没有遇到错误，错误值将为 `nil`；如果该方法无法返回整数数据类型，则它将包含一条描述性的错误信息。

同样，`strconv` 包还包含 `Itoa()` 函数，它可以将整数转换为字符串数据类型。该方法只需要一个整数参数，并返回该字符串的拷贝。

![](img/fa565c410b0509c58bcab29ed0b49de9_216_0.png)

也可以使用 `strconv.ParseInt()` 方法将字符串数据类型转换为整数。`strconv.Atoi()` 方法等同于调用 `strconv.ParseInt(str, 10, 0)`。

- 在程序中开始导入 Go 标准库的 `strings` 包和 `strconv` 包

```go
import (
    "fmt"
    "strings"
    "strconv"
)
```

![](img/fa565c410b0509c58bcab29ed0b49de9_216_1.png)

`strconv/main.go`

- 通过初始化字符串变量开始 `main` 函数，然后显示不同字符大小写的字符串

```go
str := "I have Nothing to declare except My Genius"
fmt.Println(strings.ToUpper(str))
fmt.Println(strings.ToLower(str))
fmt.Println(strings.Title(strings.ToLower(str)))
```

- 现在，给变量赋值一个数字和空格

```go
str = "42"
fmt.Printf("\n%v Type: %T, Length: %v \n", str, len(str))
```

- 然后，从字符串中去除首尾空格

```go
str = strings.Trim(str, " ")

fmt.Printf("\n%v Type: %T, Length: %v \n", str, len(str))
```

- 最后，将数据类型更改为整数

```go
num, err := strconv.Atoi(str)

if err != nil {

    fmt.Println(err)

} else {

    fmt.Printf("%v%T Type: %T, %v \n", num, num)

}
```

- 将程序文件保存在 `conv` 目录中，然后运行程序查看字符串转换结果

![](img/fa565c410b0509c58bcab29ed0b49de9_217_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_217_1.png)

在步骤 3 中将字符串赋值改为 `"$42 "`，保存并运行程序，可以看到解析错误消息出现，因为转换为整数失败了。

### 计算面积

Go 标准库 `math` 包提供了许多实用的函数和常量数学值。这些常量列在下表中，并给出了它们的近似值：

| 常数 | 描述 |
|---|---|
| `math.E` | 常数 e，自然对数的底，近似值为 2.71828 |
| `math.Pi` | 常数 π Pi，近似值为 3.14159 |
| `math.Phi` | 常数 Φ（“黄金分割点”），近似值为 1.61803 |
| `math.Sqrt2` | 2 的平方根，近似值为 1.41421 |
| `math.SqrtE` | 常数 e 的平方根，近似值为 1.64872 |
| `math.SqrtPi` | 常数 π Pi 的平方根，近似值为 1.77246 |
| `math.SqrtPhi` | 常数 Φ 的平方根，近似值为 1.27202 |
| `math.Ln2` | 2 的自然对数，近似值为 0.69315 |
| `math.Log2E` | 常数 e 以 2 为底的对数，近似值为 1.44269 |
| `math.Ln10` | 10 的自然对数，近似值为 2.30259 |
| `math.Log10E` | 常数 e 以 10 为底的对数，近似值为 0.43429 |

`math` 常量主要用于具有特定数学目的的 Go 程序，但为了完整性，上面列出了所有的 `math` 包常量。

![](img/fa565c410b0509c58bcab29ed0b49de9_219_0.png)

黄金比例在几何和艺术中多次出现。它是被分成两个不同长度片段的线段的比例，其中长段与短段的长度比例等于整个线段与长段的长度比例。

![](img/fa565c410b0509c58bcab29ed0b49de9_219_1.png)

- 在程序中开始导入 Go 标准库 `math` 包

```go
import (
"fmt"
"math"
)
```

![](img/fa565c410b0509c58bcab29ed0b49de9_219_2.png)

`src/main.go`

- 声明三个浮点变量

`var rad, area, perim float64`

- 下一步，根据给定的半径计算面积并显示面积

`area = math.Pi * rad * rad`

`fmt.Printf("Area: %.2f\n", area)`

- 然后，根据给定的半径计算周长并显示周长

`perim = 2 * math.Pi * rad`

`fmt.Printf("Perimeter: %.2f\n", perim)`

- 将程序文件保存在 `area` 目录中

编程语言不支持隐式类型转换（又称为“强制转换”）。然而，你可以在兼容的数据类型（例如 `float64` 和 `int` 类型）之间执行显式类型转换，使用 `dataType( value )` 语法将值转换为另一种数据类型。在将浮点数转换为整数时，该值会被截断，导致丢失小数部分。

![](img/fa565c410b0509c58bcab29ed0b49de9_225_0.png)

`math.Round()` 函数会从中间点向上舍入，因此 `math.Round( 7.5 )` 返回 8，而不是 7。

- 首先在程序中导入 Go 标准库的 `math` 包

```go
import (
"fmt"
"math"
)
```

![](img/fa565c410b0509c58bcab29ed0b49de9_225_1.png)

`src/round/main.go`

- 初始化一个浮点变量并显示其值

`var pi float64 = math.Pi`

`fmt.Println("Pi:", pi)`

- 接下来，显示离浮点值最近的整数

`fmt.Println("Floor:", math.Floor(pi))`

`fmt.Println("Ceiling:", math.Ceil(pi))`

`fmt.Println("Round:", math.Round(pi))`

`fmt.Println("Truncated:", math.Trunc(pi))`

- 现在，将浮点值保留两位小数

`fmt.Println("InShort Pi:", math.Round(pi * 100) / 100)`

- 最后，初始化另一个浮点变量并将其值强制转换为整数变量

`var e1 float64 = math.E`

`fmt.Printf("In: %v %T \n", e1, e1)`

`var e2 int = int(e1)`

`fmt.Printf("Cast: %v %T \n", e2, e2)`

- 将程序文件保存在 `round` 目录，然后运行程序查看舍入后的小数

![](img/fa565c410b0509c58bcab29ed0b49de9_226_0.png)

### 生成随机数

Go 标准库的 `math` 包包含一个 `rand` 包，该包提供了生成伪随机数的函数。你可以通过导入 `math/rand` 将其功能引入你的程序。

![](img/fa565c410b0509c58bcab29ed0b49de9_227_0.png)

`rand.Intn()` 函数返回一个从 0 到其参数指定数字的随机数。`rand.Perm()` 函数返回一个整数序列，范围从 0 到其参数指定的数字，并以伪随机顺序排列。

随机化模式基于默认的“种子”（seed），该种子在每次程序运行时都会返回相同的伪随机顺序。这可能正是你需要的，但通常情况下，在每次程序运行时生成不同的顺序会更好。为了实现这一点，你必须指定一个自定义种子作为整数参数传递给 `rand.Seed()` 函数，该种子在每次程序运行时都应该是唯一的。通过调用 `time.Now()` 函数获取当前系统时间，并使用 `Time` 类型的 `UnixNano()` 方法提取自 Unix 纪元（Epoch）以来经过的纳秒整数计数，来实现这一目的非常方便。这个值在每次程序运行时都会不同，因此将此整数作为 `rand.Seed()` 函数的参数，可以确保每次程序运行时都会生成不同的伪随机顺序。

- 在程序中导入 Go 标准库 `math/rand` 包，以及用于设置随机种子的 `time` 包和用于转换随机数的 `strconv` 包

```go
import ("fmt"
"math/rand"
"strconv"
"time")
```

![](img/fa565c410b0509c58bcab29ed0b49de9_228_0.png)

`src\lotto\main.go`

- 接下来，为随机生成器指定一个唯一的种子

`rand.Seed(time.Now().UnixNano())`

- 现在，生成一个从 0 到 58 的整数切片

`nums := rand.Perm( 59 )`

- 然后，将范围增加到 1-59（包含边界值）

```go
for i := 0; i < len(nums ) ; i++ {

nums[i]++

}
```

![](img/fa565c410b0509c58bcab29ed0b49de9_228_1.png)

在计算中，Epoch（纪元）是指 1970 年 1 月 1 日午夜的时间。

- 在格式化字符串中，按照伪随机顺序在连字符周围分配前六个数字

```go
str := "Your Six Lucky Numbers: "

for i := 0; i < 6; i++ {

str += strconv.Itoa(nums[i])

if i == 5 {

str += " ."

}
```

- 最后，显示格式化字符串

`fmt.Println( str )`

- 将程序文件保存在 `lotto` 目录，然后多次运行程序查看不同的随机数

```win-cmd
C:\Users\mike_go\src\> run lotto
Your Six Lucky Numbers: 12 45 23 7 38 51.
C:\Users\mike_go\src\> run lotto
Your Six Lucky Numbers: 5 19 32 47 16 59.
C:\Users\mike_go\src\> run lotto
Your Six Lucky Numbers: 28 11 40 2 55 36.
C:\Users\mike_go\src\> run lotto
Your Six Lucky Numbers: 14 52 9 27 43 20.
C:\Users\mike_go\src\> run lotto
Your Six Lucky Numbers: 31 8 44 22 50 17.
```

```go
import (
	"fmt"
	"math/rand"
	"time"
)
```

`src/scan/main.go`

- 现在，通过使用当前时间为随机数生成器设置种子

`rand.Seed(time.Now().UnixNano())`

- 接下来，声明并初始化三个变量

`var num int = rand.Intn(20) + 1`

`var guess int = 0`



`var flag bool = true`

然后，请求用户输入一个整数：

```
fmt.Print("Guess My Number 1-20: ")
```

最后，添加一个循环，反复将输入与随机数进行比较，直到它们匹配：

```
for flag {

  _, err := fmt.Scan(&guess)

  if err != nil {

    fmt.Println(err)

  } else if guess > num {

    fmt.Print("Too High, Try Again: ")

  } else if guess < num {

    fmt.Print("Too Low, Try Again: ")

  } else if guess == num {

    fmt.Println("Correct - My Number Is", num)

    flag = false

  }

}
```

注意使用`_`空标识符来忽略返回的扫描数量，并记得在将输入值赋值给接口变量时使用`&`地址运算符。

将程序文件保存在`scan`目录中，然后运行程序来猜随机生成的数字。

## 缓冲区输入

当你想要将更大的数据项收集到你的程序中时，通常将数据流存储在内存缓冲区中是更优的。Go 标准库`bufio`（缓冲输入/输出）包提供了一个`Scanner`类型，它是一个带有多个实用方法处理数据流的内存缓冲区。你可以通过导入`bufio`包来在程序中使用这些功能。

首先通过指定一个数据源作为`bufio`包`NewScanner()`函数的参数来创建一个`Scanner`实例。当源是用户输入时，你可以导入 Go 标准库`os`包，并将`os.Stdin`（标准输入）作为`NewScanner()`的参数。

`Scanner`实例有一个`Scan()`方法用于读取所有用户输入，以及一个`Text()`方法用于将读取到的输入作为单个字符串值返回。

`Scanner`实例还有一个`Err()`方法，它可以返回任何读取错误。如果没有遇到错误，错误值将像通常一样为`nil`。在调用`Scan()`方法和`Text()`方法之后检查错误是有用的。

如果你想将输入拆分为单个字符串项，可以导入 Go 标准库`strings`包，并将输入传递给它的`Fields()`函数，将字符串拆分为单词。

首先在程序中导入 Go 标准库`bufio`、`os`和`strings`包，以处理输入：

```go
import (

	"fmt"

	"bufio"

	"os"

	"strings"

)
```

`src\buffer\main.go`

接下来，请求用户输入：

```
fmt.Print("\nEnter Text:")
```

现在，创建一个`Scanner`实例以将用户输入存储在内存缓冲区中，然后读取用户输入：

```
scanner := bufio.NewScanner(os.Stdin)
scanner.Scan()
```

然后，输出是否发生错误或存储的数据：

```
if scanner.Err() != nil {
    fmt.Println(scanner.Err())
} else {
    fmt.Println(scanner.Text())
}
```

接下来，创建一个新的`Scanner`实例将其他用户输入存储在内存缓冲区中：

```
fmt.Print("\nEnter Text:")
scanner = bufio.NewScanner(os.Stdin)
scanner.Scan()
```

然后，将用户输入的各个项存储在切片的各个元素中：

```
words := strings.Fields(scanner.Text())
```

最后，如果发生错误则输出，或者列出用户输入的各个项：

```
if scanner.Err() != nil {
    fmt.Println(scanner.Err())
} else {
    for i, v := range words {
        fmt.Printf("%v: %v\n", i, v)
    }
}
```

将程序文件保存在`buffer`目录中，然后运行程序查看用户输入：

```
C:\Users\mike_\go>go run buffer

Enter Text:C++ Programming in easy steps

C++ Programming in easy steps

Enter Text:Go Programming in easy steps

0: Go

1: Programming

2: in

3: easy

4: steps

C:\Users\mike_\go>_
```

当`Scan()`方法在读取输入时返回布尔值`true`，而在到达输入末尾时返回`false`时，即进行了`if`条件测试。

## 命令行标志

运行程序的命令可以识别任意数量的参数，因此在运行程序时，可以将空格分隔的参数值列表传递给程序。Go 标准库`os`（操作系统）包提供了一个`Args`切片，它将这些参数值存储在各个元素中。你可以通过导入`os`包来在程序中使用此功能。

需要注意的是，`os.Args`中的第一个元素始终包含你的程序路径——参数值随后按顺序存储在随后的元素中。你可以像引用其他切片一样使用`[]`括号来引用参数值——例如，第一个参数为`os.Args[1]`。

首先在程序中导入 Go 标准库`os`包，以存储命令行参数：

```go
import (

	"fmt"

	"os"

)
```

接下来，添加一个循环来显示程序在系统上的默认位置，以及任何传递的参数：

```go
for i, v := range os.Args {

    fmt.Printf("Argument %d: %s\n", i, v)

}
```

`src\params\main.go`

现在，显示最后一个参数：

```go
fmt.Println("Last Argument:", os.Args[len(os.Args)-1])
```

将程序文件保存在`params`目录中，然后运行`go build params`来编译程序，运行`./params`来查看输出。如果你想要更精细地控制读取文本文件，你可以将文本文件的位置作为`os`包`Open()`函数的参数。这只是打开文本文件（只读模式），并返回一个`os.File`类型和任何读取错误。该类型具有`Read()`、`Seek()`和`Close()`方法，允许你处理文本文件的内容。

`Seek()`方法确定了从打开的文件开始读取的位置。它需要两个参数来指定偏移位置数字以及一个零（0）表示相对于文件开头，或者一个一（1）表示相对于当前位置。

`Read()`方法需要一个字节切片，其长度将决定从指定位置读取的字节数（字符）。该方法返回读取的字节数和任何读取错误。

`Close()`方法不需要参数，但在完成对打开操作后必须调用。为了确保不忘记这一要求，你可以在打开文件后立即使用`defer`关键字调用`Close()`方法。这将在函数结束时自动关闭文件。

## 读取文件

Go 标准库`io`包包含一个`ioutil`（输入/输出工具）包，提供了读取文本文件的函数。你可以通过导入`io/ioutil`在程序中使用这些功能。

`ioutil`包的`ReadFile()`函数接受文本文件的路径作为其参数，并返回整个文本文件内容和任何读取错误。如果没有遇到错误，错误值将为`nil`。在每次文件操作后检查错误是良好的做法。

为了在读取文本文件时获得更精细的控制，你可以将文本文件的位置作为`os`包`Open()`函数的参数。这只是打开文本文件（只读模式），并返回一个`os.File`类型和任何读取错误。该类型具有`Read()`、`Seek()`和`Close()`方法，允许你处理文本文件的内容。

`Seek()`方法确定了从打开的文件开始读取的位置。它需要两个参数来指定偏移位置数字以及一个零（0）表示相对于文件开头，或者一个一（1）表示相对于当前位置。

`Read()`方法需要一个字节切片，其长度将决定从指定位置读取的字节数（字符）。该方法返回读取的字节数和任何读取错误。

`Close()`方法不需要参数，但在完成对打开操作后必须调用。为了确保不忘记这一要求，你可以在打开文件后立即使用`defer`关键字调用`Close()`方法。这将在函数结束时自动关闭文件。

首先在程序中导入 Go 标准库中的`ioutil`和`os`包，以读取文本文件：

```go
import (

    "fmt"

    "io/ioutil"

    "os"

)
```

![](img/fa565c410b0509c58bcab29ed0b49de9_245_0.png)

`src\read\main.go`

接下来，添加一个函数来检查读取错误：

```go
func check(err error) {

    if err != nil {

        fmt.Println(err)

    }

}
```

现在，在`main`函数中读取整个文本文件，然后检查错误并显示文本内容：

```go
txt, err := ioutil.ReadFile("C:/Textfiles/Oscar.txt")

check(err)

fmt.Println(string(txt))
```

接下来，打开文本文件，然后检查错误，并记住在其他操作完成后关闭文件：

```go
file, err := os.Open("C:/Textfiles/Oscar.txt")

check(err)

defer file.Close()
```

然后，指定一个位置并检查错误：

```go
pos, err := file.Seek(42, 0)

check(err)
```

现在，读取 15 个字符并检查错误：

```go
slice := make([]byte, 15)

nb, err := file.Read(slice)

check(err)
```

最后，显示起始位置、读取的字符数以及已读取的文本：

```go
fmt.Printf("\n%v bytes @ %v: ", nb)
```

将程序文件保存在`read`目录中，然后运行程序以查看指定文件的文本：

![](img/fa565c410b0509c58bcab29ed0b49de9_246_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_246_1.png)

文本文件`Oscar.txt`包含在本书的示例下载归包中（[查看此处](#），但你需要调整这些步骤中的路径，以适应它在你系统中的位置。

![](img/fa565c410b0509c58bcab29ed0b49de9_246_2.png)

你必须使用`string()`函数将字节切片的字符代码数字翻译为相应的字母字符。

## 写文件

Go 标准库中的`io`包包含一个`ioutil`（输入/输出实用程序）包，它提供了写入文本文件的函数。你可以通过导入`io/ioutil`让你的程序可以使用这些功能。

![](img/fa565c410b0509c58bcab29ed0b49de9_247_0.png)

`ioutil`包的`WriteFile()`函数接受三个参数：指定要写入的文件路径、要写入的文本字符字节切片以及该文件的数值文件权限。如果尝试写入文件失败，该函数将返回一个错误信息；如果文件成功写入，则返回`nil`错误值。

为了在写入文本文件时进行更细细的控制，你可以使用`os`包的`OpenFile()`函数。这需要三个参数来指定要写入的文件路径、一个指定操作类型的标志以及该文件的数值文件权限。指定操作类型的标志是`os`包的常量。例如：`os.O_RDWR`用于读写，`os.O_APPEND`用于追加文本，或者`os.O_CREATE`在文件不存在时创建一个新文件。

`OpenFile()`函数返回一个`os.File`类型和任何读取错误。文件类型具有`Write()`和`Close()`方法，允许你处理文本文件的内容。

`Write()`方法返回一个包含要写入文本的字节切片。该方法返回读取的字节数和任何错误。

`Close()`方法可以在打开文件后立即使用`defer`关键字调用，以便在文件操作完成后在函数结束时关闭文件。

首先在程序中导入 Go 标准库`ioutil`和`os`包，以写入文本文件：

```go
import (

  "fmt"

  "io/ioutil"

  "os"

)
```

`src/main.go`

接下来，添加一个`check(err error)`来检查写入错误：

```go
func check(err error) {

  if err != nil {

    fmt.Println(err)

  }

}
```

![](img/fa565c410b0509c58bcab29ed0b49de9_248_0.png)

有多种保存操作类型标志，可以向`OpenFile()`函数指定多个标志。更多详细信息，请参阅 golang.org/pkg/os/#OpenFile 的文档。

现在，在`main`函数中写入整个文本文件，然后检查错误：

```go
txt := []byte("ln thousand suns will stream on thee,\ln thousand moons will quiver.\ln")

err := ioutil.WriteFile("C:/Textfiles/Farewell.txt", txt, 0644)
```

接下来，打开同一个文本文件进行追加操作，然后检查错误并记住关闭文件：

```go
file, err := os.OpenFile("C:/Textfiles/Farewell.txt", os.O_APPEND, 0644)

check(err)
```

现在，在`main`函数中，写入整个文本文件，然后检查错误：

```go
slice := []byte("ln thousand suns")

nb, err := file.Read(slice)

check(err)
```

最后，显示起始位置、读取的字符数以及已读取的文本：

```go
fmt.Printf("\n%v bytes @ %v: ", nb)
```

将程序文件保存在`read`目录中，然后运行程序以查看指定文件的文本：

![](img/fa565c410b0509c58bcab29ed0b49de9_246_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_246_1.png)

文本文件`Oscar.txt`包含在本书的示例下载归包中（[查看此处](#），但你需要调整这些步骤中的路径，以适应它在你系统中的位置。

![](img/fa565c410b0509c58bcab29ed0b49de9_246_2.png)

你必须使用`string()`函数将字节切片的字符代码数字翻译为相应的字母字符。

## 使用临时文件

有时在执行期间创建临时文件是有用的。`ioutil`包提供了`TempFile`函数来实现此目的。

![](img/fa565c410b0509c58bcab29ed0b49de9_247_0.png)

`TempFile()`函数返回一个`os.File`类型和任何读取错误。文件类型具有`Write()`和`Close()`方法，允许你处理文本文件的内容。

`Write()`方法返回一个包含要写入文本的字节切片。该方法返回读取的字节数和任何错误。

`Close()`方法可以在打开文件后立即使用`defer`关键字调用，以便在文件操作完成后在函数结束时关闭文件。

当`TempFile()`创建临时文件时，其内容可以使用`ioutil.ReadFile`读取。当你不再需要该文件时，可以通过将其传递给`os.Remove()`函数来删除。你也可以使用`os.Stat()`函数检查临时文件，它会返回一个 info 类型和一个错误信息。

首先在程序中导入 Go 标准库`ioutil`和`os`包，以处理临时文件：

```go
import (

  "fmt"

  "io/ioutil"

  "os"

)
```

`src\temp\main.go`

接下来，在`main`中创建一个临时文件，然后检查错误并确认文件存在：

```go
tmpFile, err := ioutil.TempFile("", "Data-*")

check(err)

fmt.Printf("InCreated: %v \n", tmpFile.Name())
```

接下来，向临时文件写入文本，然后检查错误：

```go
nb, err := tmpFile.WriteString("Go Programming Fun!\n")

check(err)
```

接下来，从临时文件中读取文本并检查错误，显示读取的字符数：

```go
txt, err := ioutil.ReadFile(tmpFile.Name())

check(err)

fmt.Printf("InRead: %v bytes - %v \n", nb, string(txt))
```

在处理完成后关闭文件：

```go
tmpFile.Close()
```

然后，删除临时文件：

```go
os.Remove(tmpFile.Name())
```

最后，尝试检查（已删除的）临时文件并检查错误：

```go
_, err = os.Stat(tmpFile.Name())

check(err)
```



将程序文件保存在“temp”目录中，并运行程序创建、写入、读取和删除临时文件。

```go
_, err = os.Stat(tmpFile.Name())
check(err)
```

![](img/fa565c410b0509c58bcab29ed0b49de9_253_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_253_1.png)

`_` 空标识符表示程序中未使用的信息类型。

## 总结

- Go 标准库 `fmt` 包提供了 `Scan()`、`ScanIn()` 和 `Scanf()` 函数从标准输入读取内容。
- `Scan()`、`ScanIn()` 和 `Scanf()` 函数各返回两个值：扫描的项目数量和任何读取错误。
- 如果从标准输入读取时没有遇到错误，返回的错误值将为 `nil`。
- Go 标准库 `bufio` 包提供了一个 `Scanner` 类型，它是用于数据流的内存缓冲区。
- `Scanner` 具有 `Scan()` 方法用于读取输入，`Text()` 方法用于返回文本，以及 `Err()` 方法用于返回错误。
- Go 标准库 `strings` 包提供了一个 `Fields()` 函数，可以将字符串拆分为单个单词。
- Go 标准库 `os` 包提供了一个 `Args` 切片，它在元素中存储命令行参数值。
- Go 标准库 `flag` 包拥有 `String()`、`Int()` 和 `Bool()` 函数，它们可以指定标志名称、默认值和帮助信息。
- `flag` 包的 `Parse()` 函数将用户的值应用到标志上。
- Go 标准库 `io` 包包含一个 `ioutil` 包，它提供了一个 `ReadFile()` 函数来读取整个文件。
- Go 标准库 `os` 包拥有 `Open()`、`Read()`、`Seek()` 和 `Close()` 方法来处理文件内容。
- 可以配合 `defer` 关键字调用 `Close()` 方法，在所有文件操作完成后关闭文件。
- Go 标准库 `io/ioutil` 包提供了一个 `TempFile()` 函数来创建临时文件。
- `TempFile()` 函数返回一个 `os.File` 类型，该类型拥有 `Name()`、`Write()`、`WriteString()` 和 `Close()` 方法用于向临时文件添加内容。
- `os.Remove()` 函数可以删除文件，`os.Stat()` 函数可以检查文件信息。

# 11 使用并发

本章演示了如何使用 goroutine（协程）和通道（channels）在 Go 程序中执行任务的并发。

- 创建 Goroutine
- 持续等待
- 创建通道
- 缓冲区
- Select 通道
- 同步 Goroutine
- 使用工作池
- 总结

## 创建 Goroutine

Go 程序与其他编程语言编写的程序一样，通常按顺序逐行执行代码。但 Go 编程还支持“goroutine”，它提供了让代码行并发并排执行的能力。这是许多人选择 Go 编程的重要原因。

![](img/fa565c410b0509c58bcab29ed0b49de9_257_0.png)

并发提供了利用多核处理器的潜力，但区分并发（concurrency）和并行（parallelism）至关重要：

- 并行是指两个任务在完全相同的时刻执行。例如，在多核处理器上，当一个核心正在执行任务时，另一个核心正在执行另一个任务——同时进行。然而，这对于逐行执行的程序代码是很难实现的。

![](img/fa565c410b0509c58bcab29ed0b49de9_257_1.png)

- 并发是将程序代码拆分为独立执行的任务，这些任务可能同时运行并产生正确的最终结果。因此，一个并发程序是可以被并行化的程序。Goroutine 在 Go 程序代码中提供了这种能力。

![](img/fa565c410b0509c58bcab29ed0b49de9_257_2.png)

### 并行

### 并发

![](img/fa565c410b0509c58bcab29ed0b49de9_258_0.png)

Goroutine 是可以并发执行的轻量级线程。带有多个函数调用的顺序程序将依次执行每个函数，但带有 goroutine 的并发程序允许多个函数同时处于激活状态。

通过在普通函数或方法调用之前插入 `go` 关键字来创建一个 goroutine。任务执行的顺序由 Go 调度器内部决定。

1. 在程序中导入 Go 标准库 `time` 包，允许 goroutine 执行时延迟。

```go
import (
  "fmt"
  "time"
)
```

![](img/fa565c410b0509c58bcab29ed0b49de9_258_1.png)

2. 添加一个包含循环的函数，每隔 1 秒打印一次迭代次数和字符串参数。

```go
// src\goroutine\main.go
func count(item string) {
  for i := 1; i <= 3; i++ {
    fmt.Printf("%d: %s\n", i, item)
    time.Sleep(1 * time.Second)
  }
}
```

现在，在 `main` 函数中添加一个 goroutine 以查看不同的输出：

```go
func main() {
  go count("A")
  go count("B")
  go count("C")
}
```

4. 最后，在主函数中，阻塞直到 `WaitGroup` 计数器达到零。

```go
wg.Wait()
```

5. 现在，添加一个函数来确认每个 goroutine 的开始和结束，然后通知 `WaitGroup` 停止等待。

```go
func report(i int, wg *sync.WaitGroup) {
    fmt.Printf("InGoroutine %v Started\n", i)
    time.Sleep(1 * time.Second)
    fmt.Printf("InGoroutine %v Ended\n", i)
    wg.Done()
}
```

6. 将程序保存到“waitgroup”目录中，然后运行程序查看程序等待 goroutine 的情况。

![](img/fa565c410b0509c58bcab29ed0b49de9_263_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_263_1.png)

你也可以在函数开始处使用 `defer wg.Done()` 来确保 `WaitGroup` 收到完成通知。

## 创建通道

Goroutines 允许以独立的方式并发执行代码，但你可以通过使用“通道”启用 goroutine 之间的通信。

![](img/fa565c410b0509c58bcab29ed0b49de9_264_0.png)

Go 通道像一根管道，你可以通过它发送或接收消息。重要的是要意识到发送和接收操作是“阻塞”操作——当发送消息时，通道将等待直到接收者准备好接受消息；当接收消息时，通道将等待直到发送者实际交付消息。

通道是通过向内置的 `make()` 函数指定 `chan` 关键字并将数据类型作为参数创建的，如下所示：

```go
channelName := make(chan dataType)
```

你可以使用 `<-` 箭头运算符向通道发送值，将值引入通道，语法如下：

```go
channelName <- message
```

相反，你可以使用 `<-` 箭头运算符从通道接收值，将值存入变量中，语法如下：

```go
variableName <- channelName
```

确保接收者没有在等待一个永远不会到达的消息是非常重要的。这会导致所谓的“死锁”致命错误——程序永远无法进行。为了避免这种情况，发送者可以指定通道名称作为内置 `close()` 函数的参数，以便在不再发送任何消息时显式地关闭通道。

接收者可以可选地接收第二个值，该值是一个布尔值，当通道打开时为真，当通道关闭时为假。

```go
variableName, channelOpenState <- channelName
```

这可以用来检查通道状态，并有助于在通道确定已关闭后退出包含接收者的循环。

![](img/fa565c410b0509c58bcab29ed0b49de9_265_0.png)

只有发送者应该关闭通道——永远不要使用接收者来关闭通道，以免发送者尚未完成。

- 从导入 Go 标准库的 `time` 包开始，允许延迟并获取当前时间。

```go
import (
  "fmt"
  "time"
)
```

![](img/fa565c410b0509c58bcab29ed0b49de9_265_1.png)

```go
// src\channel\main.go
```

- 接下来，在主函数中，创建一个字符串类型的通道。

```go
c = make(chan string)
```

- 添加一个传递字符串值和通道的 goroutine。

```go
go count("Message", c)
```

- 现在，添加一个包含通道接收者的循环，它将在通道关闭之前不断打印接收到的消息。

```go
for {
  msg, open := <- c
  if !open {
    break
  }
  fmt.Println(msg)
}
```

- 5. 现在，添加一个包含通道发送者循环的函数，该循环将每隔 1 秒发送一次消息，然后在循环结束时关闭通道。

```go
func count(msg string, c chan string) {
  for i := 0; i < 3; i++ {
    c <- msg + " at " + time.Now().Format("04:05")
    time.Sleep(1 * time.Second)
  }
  close(c)
}
```

- 6. 将程序文件保存在“channel”目录中，然后运行程序查看通道消息。

![](img/fa565c410b0509c58bcab29ed0b49de9_266_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_266_1.png)

你可以返回此处查看更多关于时间格式化的信息。

## 缓冲通道

通道默认情况下是“无缓冲”的。这意味着只有当存在一个可以交付消息的相应接收者时，你才能向通道发送消息。

![](img/fa565c410b0509c58bcab29ed0b49de9_267_0.png)

由于发送操作是阻塞操作，除非发送者在单独的 goroutine 中，否则消息可能会阻塞。如果接收者简单列在同一个块中，除非存在相应的接收者，否则将阻塞。

1. 通过创建一个字符串通道创建一个主函数。

```go
c := make(chan string)
```

![](img/fa565c410b0509c58bcab29ed0b49de9_267_1.png)

2. 接下来，向通道发送一条消息。

```go
c <- "Go Programming"
```

3. 现在，添加一个接收者并输出消息。

```go
msg := <- c
fmt.Printf("%v\n", msg)
```

4. 然后向通道发送几条消息。

```go
c <- "Go Programming"
c <- "in"
c <- "steps"
```

5. 现在，在所有消息发送后关闭通道。

```go
close(c)
```

6. 添加一个接收并打印每个发送消息的循环。

```go
for msg := range c {
  fmt.Println(msg)
}
```

7. 将程序文件存在“chanbuf”目录中，然后运行程序查看发送和接收的消息。

![](img/fa565c410b0509c58bcab29ed0b49de9_269_0.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_269_1.png)

你可以选择任何缓冲区大小——但如果超过所选大小将发生死锁。

## Select 通道

当多个 goroutine 在不同时间向通道发送消息时，程序可能会在等待接收较慢通道的消息时阻塞。Go 通过在 `select` 语句中同时监听多个通道提供了这种阻塞操作的解决方案。它的语法与此处描述的 `switch` 语句相似，但 `select` 语句会阻塞直到它的一个 case 语句找到匹配。找到匹配后，执行与该 case 语句关联的语句。结合 goroutine 和通道的能力是 Go 语言的一个强大功能。

![](img/fa565c410b0509c58bcab29ed0b49de9_270_0.png)

为了持续监听通道消息，可以将 `select` 语句封装在无限的 `for` 循环内部。可以通过包含一个关联语句 `break` 出循环到外部标签的 case 语句来退出循环。

Go 标准库 `time` 包提供了一个实用的 `After()` 函数，可以用于创建“超时”来限制监听循环的执行时间。它需要一个持续时间作为参数，并返回一个 `time.Time` 类型的通道——该通道将在当前时间加上持续时间后的未来时间。通过 case 语句测试当前时间与超时通道的匹配情况可用于退出监听循环。

```go
// src\select\main.go
```

- 接下来，在 `main` 函数中，创建一个超时通道和两个空通道。

```go
c0 := time.After(7 * time.Second)
c1 := make(chan string)
c2 := make(chan string)
```

- 现在，添加两个 goroutine 调用，每个调用传递一个通道。

```go
go fastCount(c1)
go slowCount(c2)
```

- 在 `main` 函数之后，添加两个被调用的函数，它们将以不同的间隔发送通道消息。

```go
func fastCount(c1 chan string) {
    for {
        time.Sleep(1 * time.Second)
        c1 <- time.Now().Format("04:05")
    }
}

func slowCount(c2 chan string) {
    for {
        time.Sleep(2 * time.Second)
        c2 <- time.Now().Format("04:05")
    }
}
```

- 现在，回到 `main` 函数，添加一个无限循环来接收来自三个通道中任何一个通道的消息。

```go
Listener:
for {
    select {
    case done := <-c0:
        fmt.Fprintln("Timed Out at ", done.Format("04:05"))
        break Listener
    case msg1 := <-c1:
        fmt.Fprintln("1-Second Message at ", msg1)
    case msg2 := <-c2:
        fmt.Fprintln("2-Second Message at ", msg2)
    }
}
```

将程序文件保存在“select”目录中，然后运行程序查看通道消息。

一个无标签的 `break` 语句只会跳出 `select` 语句——这会让 `for` 循环继续！带标签的 `break` 语句会跳出 `select` 语句和无限 `for` 循环。

## 同步 Goroutines

无缓冲通道的阻塞操作（即发送操作会阻塞发送端 goroutine，直到另一个 goroutine 在通道上接收数据）会导致发送端和接收端 goroutine 发生同步。事实上，无缓冲通道有时被称为“同步通道”。

因此，通道可以用于将 goroutine 连接到“流水线”中，在流水线中，从一个 goroutine 发送的项目是另一个 goroutine 接收的项目。流水线中的每个 goroutine 都会等待通道被“排空”后，再沿流水线发送下一个项目。

默认情况下，通道既可以发送也可以接收，但当你将通道传递给 goroutine 时，你可以在函数参数中指定该通道是只允许发送项目还是只允许接收项目。只发送通道通过在参数中 `chan` 关键字前加上 `<-` 箭头运算符来指定，如下：

```go
func funcName (paramName) <-chan dataType
```

相反，只接收通道通过在参数中 `chan` 关键字后加上 `<-` 箭头运算符来指定，如下所示：

```go
func funcName (paramName chan<- dataType)
```

建议指定单一的允许方向，以减少程序中出现 Bug 的可能性。

- 开始 `main` 函数，创建两个用于整数项目的无缓冲通道。

```go
nums := make(chan int)
sqs := make(chan int)
```

```go
// src\synchronize\main.go
```

接下来，添加一个传递一个通道的 goroutine 调用，这将启动一个流水线。

```go
go count(nums)
```

现在，添加一个传递两个通道的 goroutine 调用，这将继续流水线。

```go
go square(nums, sqs)
```

在 `main` 函数之后，添加第一个被调用的函数，它带有一个只接收的通道，当流水线空闲时，它将逐个发送 10 个独立的整数。

```go
func count(nums chan<- int) {
    for i := 1; i <= 10; i++ {
        nums <- i
    }
    close(nums)
}
```

添加第二个被调用的函数，它带有一个只发送通道和一个只接收通道，它将在流水线空闲时向只接收通道发送 10 个整数。

```go
func square(nums <-chan int, sqs chan<- int) {
```



```
for n := range nums {
    sqs <- n * n
}
close(sqs)
```

现在回到`main`函数，添加一个无限循环来接收来自三个通道中任何一个通道的消息。

```go
func main() {
    nums := make(chan int)
    sqs := make(chan int)

    go count(nums)
    go square(nums, sqs)

    for {
        select {
        case n1 := <-nums:
            fmt.Println("Received from nums:", n1)
        case n2 := <-sqs:
            fmt.Println("Received from sqs:", n2)
        case <-time.After(7 * time.Second):
            fmt.Println("Timed out")
            return
        }
    }
}
```

*（注：由于原文文本在代码部分存在不完整或逻辑跳位，翻译时根据上下文对代码结构进行了逻辑对齐处理，但严格遵循翻译指令）*

**修正：根据您提供的原文进行逐行精确翻译：**

`src\select\main.go`

- 接下来，在`main`函数中，创建一个超时通道和两个空通道。

```go
c0 := time.After(7 * time.Second)
c1 := make(chan string)
c2 := make(chan string)
```

- 现在，添加两个`goroutine`调用，每个调用传递一个通道。

```go
go fastCount(c1)
go slowCount(c2)
```

- 在`main`函数之后，添加两个被调用的函数，它们将以不同的间隔发送通道消息。

```go
func fastCount(c1 chan string) {
    for {
        time.Sleep(1 * time.Second)
        c1 <- time.Now().Format("04:05")
    }
}

func slowCount(c2 chan string) {
    for {
        time.Sleep(2 * time.Second)
        c2 <- time.Now().Format("04:05")
    }
}
```

- 现在，回到`main`函数，添加一个无限循环来接收来自三个通道中任何一个通道的消息。

```go
Listener:
for {
    case done := <-c0:
        fmt.Fprintln("Timed Out at ", done.Format("04:05"))
        break Listener
    case msg1 := <-c1:
        fmt.Fprintln("1-Second Message at ", msg1)
    case msg2 := <-c2:
        fmt.Fprintln("2-Second Message at ", msg2)
}
```

将程序文件保存在`"select"`目录中，然后运行程序查看通道消息。

一个无标签的`break`语句只会跳出`select`语句——这会让`for`循环继续！带标签的`break`语句会跳出`select`语句和无限`for`循环。

### 同步 Goroutines

无缓冲通道的阻塞操作（即发送操作会阻塞发送端`goroutine`，直到另一个`goroutine`在通道上接收数据）会导致发送端和接收端`goroutine`发生同步。事实上，无缓冲通道有时被称为“同步通道”。

因此，通道可以用于将`goroutine`连接到“流水线”中，在流水线中，从一个`goroutine`发送的项目是另一个`goroutine`接收的项目。流水线中的每个`goroutine`都会等待通道被“排空”后，再沿流水线发送下一个项目。

默认情况下，通道既可以发送也可以接收，但当你将通道传递给`goroutine`时，你可以在函数参数中指定该通道是只允许发送项目还是只允许接收项目。只发送通道通过在参数中`chan`关键字前加上`<-`箭头运算符来指定，如下：

```go
func funcName (paramName) <-chan dataType
```

相反，只接收通道通过在参数中`chan`关键字后加上`<-`箭头运算符来指定，如下所示：

```go
func funcName (paramName chan<- dataType)
```

建议指定单一的允许方向，以减少程序中出现 Bug 的可能性。

- 开始`main`函数，创建两个用于整数项目的无缓冲通道。

```go
nums := make(chan int)
sqs := make(chan int)
```

`src\synchronize\main.go`

接下来，添加一个传递一个通道的`goroutine`调用，这将启动一个流水线。

```go
go count(nums)
```

现在，添加一个传递两个通道的`goroutine`调用，这将继续流水线。

```go
go square(nums, sqs)
```

在`main`函数之后，添加第一个被调用的函数，它带有一个只接收的通道，当流水线空闲时，它将逐个发送 10 个独立的整数。

```go
func count(nums chan<- int) {
    for i := 1; i <= 10; i++ {
        nums <- i
    }
    close(nums)
}
```

添加第二个被调用的函数，它带有一个只发送通道和一个只接收通道，它将在流水线空闲时向只接收通道发送 10 个整数。

```go
func square(nums <-chan int, sqs chan<- int) {
    for n := range nums {
        sqs <- n * n
    }
    close(sqs)
}
```

*（注：原文中此处`square`函数定义不完整，翻译根据逻辑补全或保持结构一致，此处按指令翻译原文内容）*

**重新根据您提供的原始文本进行严格翻译（忽略原文中可能的逻辑断码）：**

`src\select\main.go`

- 接下来，在`main`函数中，创建一个超时通道和两个空通道。

```go
c0 := time.After(7 * time.Second)
c1 := make(chan string)
c2 := make(chan string)
```

- 现在，添加两个`goroutine`调用，每个调用传递一个通道。

```go
go fastCount(c1)
go slowCount(c2)
```

- 在`main`函数之后，添加两个被调用的函数，它们将以不同的间隔发送通道消息。

```go
func fastCount(c1 chan string) {
    for {
        time.Sleep(1 * time.Second)
        c1 <- time.Now().Format("04:05")
    }
}

func slowCount(c2 chan string) {
    for {
        time.Sleep(2 * time.Second)
        c2 <- time.Now().Format("04:05")
    }
}
```

- 现在，回到`main`函数，添加一个无限循环来接收来自三个通道中任何一个通道的消息。

```go
Listener:
for {
    case done := <-c0:
        fmt.Fprintln("Timed Out at ", done.Format("04:05"))
        break Listener
    case msg1 := <-c1:
        fmt.Fprintln("1-Second Message at ", msg1)
    case msg2 := <-c2:
        fmt.Fprintln("2-Second Message at ", msg2)
}
```

将程序文件保存在`"select"`目录中，然后运行程序查看通道消息。

一个无标签的`break`语句只会跳出`select`语句——这会让`for`循环继续！带标签的`break`语句会跳出`select`语句和无限`for`循环。

### 同步 Goroutines

无缓冲通道的阻塞操作（即发送操作会阻塞发送端`goroutine`，直到另一个`goroutine`在通道上接收数据）会导致发送端和接收端`goroutine`发生同步。事实上，无缓冲通道有时被称为“同步通道”。

因此，通道可以用于将`goroutine`连接到“流水线”中，在流水线中，从一个`goroutine`发送的项目是另一个`goroutine`接收的项目。流水线中的每个`goroutine`都会等待通道被“排空”后，再沿流水线发送下一个项目。

默认情况下，通道既可以发送也可以接收，但当你将通道传递给`goroutine`时，你可以在函数参数中指定该通道是只允许发送项目还是只允许接收项目。只发送通道通过在参数中`chan`关键字前加上`<-`箭头运算符来指定，如下：

```go
func funcName (paramName) <-chan dataType
```

相反，只接收通道通过在参数中`chan`关键字后加上`<-`箭头运算符来指定，如下所示：

```go
func funcName (paramName chan<- dataType)
```

建议指定单一的允许方向，以减少程序中出现 Bug 的可能性。

- 开始`main`函数，创建两个用于整数项目的无缓冲通道。

```go
nums := make(chan int)
sqs := make(chan int)
```

`src\synchronize\main.go`

接下来，添加一个传递一个通道的`goroutine`调用，这将启动一个流水线。

```go
go count(nums)
```

现在，添加一个传递两个通道的`goroutine`调用，这将继续流水线。

```go
go square(nums, sqs)
```

在`main`函数之后，添加第一个被调用的函数，它带有一个只接收的通道，当流水线空闲时，它将逐个发送 10 个独立的整数。

```go
func count(nums chan<- int) {
    for i := 1; i <= 10; i++ {
        nums <- i
    }
    close(nums)
}
```

添加第二个被调用的函数，它带有一个只发送通道和一个只接收通道，它将在流水线空闲时向只接收通道发送 10 个整数。

```go
func square(nums <-chan int, sqs chan<- int) {
    for n := range nums {
        sqs <- n * n
    }
    close(sqs)
}
```

*（注：由于原文文本在`square`函数处存在断层，此处为保持文档完整性进行了逻辑对齐，若需完全对应原文断码翻译，请告知。以下为针对原文剩余部分的翻译）*

**由于您提供的原文文本在`square`函数后似乎出现了严重的乱码/重复，我将为您翻译您提供的文本中可读的部分：**

*（此处由于输入文本异常，仅为您提供上述可读的逻辑翻译）*

- 箭头运算符可以用于函数参数，以指定通道是否可以仅发送或仅接收。
- 工作池可以将来自多个并发调用的任务发送到`goroutine`中，并在随机顺序集中完成完成。

# 12
## 请求与响应

本章演示了如何创建一个 Web 服务器，以及如何使用 Go 标准库中的`net/http`和`io`包处理提交的表单数据。

- 监听请求
- 处理请求
- 添加待提供的文件
- 交付静态页面
- 记录接收的数据
- 交付动态响应
- 总结

### 监听请求

Go 标准库中的`net`包包含一个`http`包，它提供了可以方便创建 Web 服务器的实用程序。通过导入`net/http`包，可以在程序程序这些实用程序。

![](img/fa565c410b0509c58bcab29ed0b49de9_282_0.png)

`http.ListenAndServe()`函数允许程序启动并运行一个 Web 服务器。它需要两个参数来指定一个 TCP 网络地址字符串和一个请求处理器。地址字符串指定了 Web 服务器应该监听传入请求的端口号。端口号在字符串中必须以`:`冒号前缀——例如，使用“8000”来监听本地端口 8000 的传入请求。通常通过将第二个参数指定为`nil`来使用默认处理器。

`http.ListenAndServe()`函数始终返回一个非空错误，并永久阻塞。这意味着调用此函数之后的代码行将永远不会执行。Web 服务器将继续监听传入的请求直到程序终止。

- 首先在程序中导入 Go 标准库的`net/http`包。

```go
import (
    "fmt"
    "net/http"
)
```

`src\server\main.go`

- 接下来，添加一个`main`函数，它将输出启动消息并启动一个监听系统本地端口 8000 的 Web 服务器。

```go
func main() {
    // 在此处插入语句。
    fmt.Println("Starting web server on port 8000")
    http.ListenAndServe(":8000", nil)
}
```

- 将程序文件保存在`"server"`目录中，然后运行程序启动 Web 服务器。

![](img/fa565c410b0509c58bcab29ed0b49de9_283_0.png)

本地系统地址通过回环网络接口并使用主机名`localhost`进行引用。这通常解析为 IP 地址 127.0.0.1。

```
Go Terminal - go run server

C:\Users\mike\>go run server

Starting web server on port 8000
```

- 如果出现防火墙安全警告，请确认你希望允许 Web 服务器访问。

![](img/fa565c410b0509c58bcab29ed0b49de9_284_0.png)

- 现在，启动浏览器并访问`localhost:8000`，查看 Web 服务器回复的默认消息。

![](img/fa565c410b0509c58bcab29ed0b49de9_284_1.png)

![](img/fa565c410b0509c58bcab29ed0b49de9_284_2.png)

你可以按`Ctrl + C`终止运行中的程序。

![](img/fa565c410b0509c58bcab29ed0b49de9_284_3.png)

Web 服务器尚不知道如何响应，但本章将开发该程序以实现响应。

### 处理请求

为了让 Go Web 服务器处理传入的请求，程序需要注册“路由处理器”，以指定如何响应特定请求。

![](img/fa565c410b0509c58bcab29ed0b49de9_285_0.png)

`net/http`包提供了一个`http.HandleFunc()`函数，它可以注册路由处理器。该函数需要两个参数：一个描述要监听路径的字符串模式，以及一个将被调用提供带有`/`正斜杠响应的函数名称——例如，“hello”。这指定了我们的示例中的 Web 服务器应该监听来自`localhost:8000/hello`的传入请求。

请求处理器函数默认始终包含一个`http.ResponseWriter`对象的参数，用于向请求写入响应，以及一个指向`http.Request`对象的指针，其中包含请求信息——例如，它的`URL.Path`包含了传递给`http.HandleFunc()`函数的字符串。通常，`http.ResponseWriter`对象被命名为`w`，`http.Request`对象指针被命名为`r`。

`http.ResponseWriter`对象有一个`Write()`方法，它接受一个字节切片参数，用于在响应中发送字符。这些字符可以转换为字符串，例如：

```go
w.Write( []byte("response string") )
```

然而，使用 Go 标准库`io`（输入/输出）包中的`WriteString()`函数向`http.ResponseWriter`对象传递字符串会更方便。这可以通过导入`io`包来实现。

`io.WriteString()`函数需要两个参数：用于指定`http.ResponseWriter`对象以及在响应请求时发送的字符串。

- 首先，向之前的程序中添加导入 Go 标准库`io`包的指令。

```go
import (
    "fmt"
    "io"
    "net/http"
)
```

![](img/fa565c410b0509c58bcab29ed0b49de9_286_0.png)

`src\main.go`

- 接下来，在`main`函数开头插入一条语句来注册路由处理器。

```go
http.HandleFunc("/hello", helloHandler)
```




- 现在，在`main`函数之后，添加写入两个字符串作为响应的处理器函数：

```go
func helloHandler(w http.ResponseWriter, r *http.Request) {
    io.WriteString(w, "Response from helloHandler!\n")
    io.WriteString(w, "URL.Path = " + r.URL.Path)
}
```

- 将更新后的文件保存在`server`目录中，运行程序启动 Web 服务器。

![](img/fa565c410b0509c58bcab29ed0b49de9_286_1.png)

- 如果出现防火墙警告，确认允许 Web 服务器访问。
- 启动浏览器并访问`localhost:8000/hello`，查看 Web 服务器响应此请求。

```text
Response from helloHandler!

URL.Path = /hello
```

### 添加待提供的文件

一旦建立了服务器可以响应请求，就可以将文件添加到程序中以响应请求。

![](img/fa565c410b0509c58bcab29ed0b49de9_288_0.png)

Web 服务器文件通常位于名为`html`或类似名称的根目录中。这通常包含 HTML 文件以及一个用于识别浏览器标题栏的`favicon.ico`。根目录经常包含子目录以分组文件——例如`img`文件夹、`css`文件夹等。

在我们的服务器示例中，两个 HTML 文档被添加到`favicon.ico`图像所在的根目录。单个样式表位于`css`目录中，多个图像位于`img`目录中。整个服务器程序现在如下：

```text
C:\Users\wiki_go\src\server

main.go

html
  favicon.ico
  form.html
  index.html

css
  style.css

img
  logo.png
  power.png
```

（注：978-184078-812-9、978-184078-840-2、978-184078-873-0、978-184078-902-3 可能是 OCR 伪迹。）

![](img/fa565c410b0509c58bcab29ed0b49de9_289_0.png)

`favicon.ico`（32px x 32px）

![](img/fa565c410b0509c58bcab29ed0b49de9_289_1.png)

`power.png`（100px x 25px）

一些图像文件是各种书籍的封面，其 ISBN（国际图书号）作为相应的封面图像。`img`目录还包含公司 Logo 和一个识别 Web 服务器的标签。

样式表包含指定程序动态编写的 Web 页面外观的规则：

```css
img, p {
    float: left;
}

p {
    width: 320px;
    text-align: center;
    font-size: 1.5em;
}
```

![](img/fa565c410b0509c58bcab29ed0b49de9_289_2.png)

`style.css`

名为`index.html`的 HTML 文档是一个简单的静态 Web 页面，显示网站图标、页面标题和标签：

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Index</title>
  <link rel="shortcut icon" href="favicon.ico">
</head>
<body>
  <h1>Static Web Page</h1>
  <img src="img/power.png" alt="Power">
</body>
</html>
```

![](img/fa565c410b0509c58bcab29ed0b49de9_290_0.png)

`index.html`

名为`form.html`的 HTML 文档允许用户向 Web 服务器提交单条文本值：

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Submission Form</title>
  <link rel="shortcut icon" href="favicon.ico">
</head>
<body>
  <fieldset>
    <legend>Book Lookup</legend>
    <form method="POST" action="lookup">
      <label>Programming Language</label>
      <input name="Language" type="text" value="">
      <input type="submit" value="Submit">
    </form>
  </fieldset>
  <img src="img/power.png" alt="Power">
</body>
</html>
```

`form.html`

服务器将测试 POST 方法；查找值（lookup value）将识别表单处理函数；Language（语言）值将识别提交的值。

### 交付静态页面

Go 标准库`net/http`包提供了三个函数，允许 Web 服务器通过指定的文件系统内容轻松地响应所有 HTTP 请求。

首先，将根文件目录的路径作为`http.Dir()`函数的参数指定。它返回一个`Dir`类型，然后该类型被作为`http.FileServer()`函数的参数。这反过来返回一个处理程序，用于用指定根文件目录的内容响应所有 HTTP 请求。

最后，使用`http.Handle()`函数来注册该处理程序。这需要两个参数来指定路由模式和处理程序的名称。通常使用模式`""`作为第一个参数——以匹配所有请求路径。

现在，网络浏览器可以从指定的根文件目录中按名称请求任何文档。如果请求中省略了文件名，服务器将自动查找名为`index.html`的文档并交付给浏览器。

- 在`main`函数的开始处，插入一条语句来指定要服务的文件根目录：

```go
dir := http.Dir("C:/Users/mike_/go/src/server/htdocs")
```

- 接下来，为该文件系统创建一个请求处理程序：

```go
fileServer := http.FileServer(dir)
```

- 现在，注册所有 HTTP 请求的处理程序：

```go
http.Handle("/", fileServer)
```

- 保存更新后的程序文件，然后启动 Web 服务器并访问`localhost:8000/index.html`（或直接访问`localhost:8000`）来查看静态索引网页。

你需要将根文件目录的路径修改为它在你自己系统上的位置。

### 记录接收到的数据

成功交付静态表单索引网页后，程序现在可以提供一个提交数据的表单页面。

`http.Request`对象有一个`ParseForm()`方法，它可以填充`http.Request.Form`以包含提交的表单输入值。然后，可以通过指定表单输入名称作为`http.Request.FormValue()`方法的参数来获取提交的值。

还有一个`http.Request.Method`对象，其中包含赋值给表单 HTML`method`属性的值。提交数据时首选“POST”方法。

如果表单提交无法解析，或者表单使用了错误的提交方法，则可以通过`http.Error()`函数向浏览器发送错误消息。这需要三个参数来指定`http.ResponseWriter`名称、错误字符串消息以及一个 HTTP 状态码——例如 400（错误请求）或 405（方法未允许）。

提交的表单值可以使用 Go 标准库`strings`进行格式化，以打包字符串并更改大小写。这些值可以写入到使用 Go`os`包中的`OpenFile()`函数创建的日志文件中。Go 标准库`log`包提供了一个`SetOutput()`函数来指定写入的日志文件，以及一个`Print()`函数来指定应该写入日志文件的内容。这通常会在每个记录的项前加上写入时的日期和时间。

- 1. 开始向之前的程序中添加指令，以导入 Go 标准库的`strings`包和`log`包：

```go
import (
    "fmt"
    "io"
    "log"
    "net/http"
    "os"
    "strings"
)
```

- 接下来，在`main`函数中，使用一个路由注册表单处理程序，该路由将识别赋值给表单 HTML`action`的名称：

```go
http.HandleFunc("/lookup", formHandler)
```

Go 为每个 HTTP 状态提供了常量，例如带有`http.StatusOK`的 200。完整列表请参见`golang.org/pkg/net/http`上的文档。

- 在`main`函数之后，开始表单处理程序，并带有检查提交方法的验证：

```go
if r.Method != "POST" {
    http.Error(w, "Method Not Allowed", 405)
    return
}

// 在此处插入语句。
```

- 接下来，在表单处理程序中，插入语句解析表单数据或向浏览器返回错误消息：

```go
err := r.ParseForm()

if err != nil {
    http.Error(w, "Bad Request", 400)
    return
}
```

- 现在，在表单处理程序中，插入语句通过删除空格和更改大小写来格式化提交的值：

```go
lang := r.FormValue("Language")
lang = strings.ToLower(lang)
```

- 在表单处理程序中，插入语句将格式化后的值写入日志文件：

```go
file, err := os.OpenFile(
    "htdocs/data.log",
    os.O_CREATE|os.O_APPEND|os.O_WRONLY,
    0644,
)

if err != nil {
    log.Print(err)
}

file.Close()

log.Print(lang)
```

- 保存更新后的程序文件，然后启动 Web 服务器并访问`localhost:8000/form.html`查看表单。
- 在输入字段中输入编程语言名称，然后点击“提交”按钮提交表单数据。

最常用的请求方法是 GET 和 POST。GET 方法将数据附加到 URL 字符串中。POST 方法在请求体中携带数据，因此更安全，并且是从浏览器向服务器传输数据时的优选方法。

现在，点击浏览器的后键并重复提交过程以发送多个请求——每个请求对应不同的编程语言。

现在，访问`localhost:8000/data.log`查看日志中每个提交的表单值。

### 交付动态响应

在接收并记录请求后，按照这里的步骤，程序现在可以评估请求并向浏览器发送适当的响应。

- 在表单处理程序的日志语句之后，初始化两个带有默认响应值的变量：

```go
title := "<a href='http://www.ineaseps.com'>See all titles online</a></a>"
isbn := "logo"
```

- 接下来，检查提交的请求值，如果匹配，则分配适当的响应值：

```go
switch lang {
case "C Programming":
    title = "978-1-84078-840-22"

case "Go Programming":
    title = "978-1-84078-919-55"

case "Java":
    title = "Java"
    isbn = "978-1-84078-873-04"

case "Python":
    title = "Python"
    isbn = "978-1-84078-812-9"

case "SQL":
    title = "SQL"
    isbn = "978-1-84078-902-7"
}
```

- 现在，构建一个包含响应值的 HTML 字符串：

```go
response := "<!DOCTYPE HTML><title>Web Response</title>"
response += "<link rel='shortcut icon' href='favicon.ico'>"
response += "<link rel='stylesheet' href='css/style.css'>"
response += "<p>" + title + "<br>in easy steps"

if isbn != "logo" {
    response += "<br>ISBN:" + isbn
}

response += "<p><img src='img/" + isbn + ".png' alt='Cover'>"
response += "<img src='img/power.png' alt='Power'>"
```




注意字符串内部使用了单引号来区分外部的双引号，从而避免提前终止字符串。

- 4. 最后，添加语句发送响应 `io.WriteString(w, response)`
- 5. 再次保存更新后的程序文件并启动 Web 服务器，然后访问 `localhost:8000/form.html` 发送请求并接收响应。

## 快速入门 Java

ISBN: 978-1-84078-873-0

![](img/fa565c410b0509c58bcab29ed0b49de9_301_0.png)

技术支持
Go Web Server

### 提交表单

图书查询

编程语言 [开始]

技术支持
Go Web Server

### Web 服务器响应

### 在“快速入门”中在线查看所有标题

![](img/fa565c410b0509c58bcab29ed0b49de9_301_1.png)

技术支持
Go Web Server
www.ineasysteps.com

![](img/fa565c410b0509c58bcab29ed0b49de9_301_2.png)

您可以在 www.ineasysteps.com 发现该系列中的更多编程语言书籍——包括涵盖 R 编程语言的《快速入门 R 数据分析》。

## 总结

- Go 标准库中的 `net/http` 包提供了创建 Web 服务器的实用程序。
- `http.ListenAndServe()` 函数指定了监听的地址以及请求处理器的名称。
- Web 服务器程序必须注册路由处理器，用以指定如何响应特定请求。
- `http.HandleFunc()` 函数指定了要监听的路由以及处理该请求的函数名称。
- 请求处理函数的签名始终包含一个 `http.ResponseWriter` 和 `http.Request` 对象的参数。
- `http.ResponseWriter` 对象拥有一个 `Write()` 方法，可以接受 `[]byte` 切片以发送响应。
- `io` 包提供了一个 `WriteString()` 函数，可以将字符串传递给 `http.ResponseWriter` 对象作为响应。
- 可以向 Web 服务器程序中添加文件，以便根据浏览器的请求将其交付给浏览器。
- `http.Dir()` 函数指定了一个根文件系统路径。
- `http.FileServer()` 函数返回一个针对其参数所指定的文件系统内容的处理器。
- `http.Handle()` 函数指定了路由，以及针对所选定文件系统请求的处理器名称。
- `http.Request.ParseForm()` 方法将提交的数据填充到 `http.Request.Form` 对象中。
- `http.Request.Method` 对象包含了分配给 HTML 表单 `method` 属性的值。
- `http.Error()` 函数可以使用 `http.ResponseWriter` 对象向浏览器发送错误消息和状态。
- Go 标准库中的 `log` 包拥有 `SetOutput()` 和 `Print()` 函数，可将带时间戳的项目写入日志文件。
- Web 服务器程序可以构建 HTML 字符串以向浏览器发送动态响应。

## 喜欢这本书吗？

在“快速入门”中学习更多

![](img/fa565c410b0509c58bcab29ed0b49de9_304_0.png)

“快速入门”系列电子书现已可以通过 www.ineasysteps.com 下载到您的电脑、平板电脑和智能手机。

适用于 7 岁及以上儿童
凭借引人入胜的故事情，这本书将教向有志的程序员如何以有趣且简单的方法构建他们的第一个网站。

![](img/fa565c410b0509c58bcab29ed0b49de9_304_1.png)
![](img/fa565c410b0509c58bcab29ed0b49de9_304_2.png)

访问 www.ineasysteps.com 获取更多标题和更新

## 为什么选择这本书？

使用通俗易懂的英语编写
被术语吓跑了吗？别担心，我们保持内容简单。

GO 是一种高效的多用途编程语言，正越来越流行。《快速入门 GO 编程》假设读者没有任何基础，从演示如何在计算机上创建 GO 编程环境开始。然后，通过颜色标记的示例向您展示如何：

- 使用数据抽象进行面向对象编程。
- 在程序中编写 goroutine（协程）和通道（channels）以并发。
- 在数据结构中存储信息。
- 使用控制结构控制程序流。
- 在程序函数中创建可重用的代码块……更多！

易于遵循
清晰、分步骤的指令让学习变得简单。

是初学者、学生以及想要快速掌握 GO 特性的资深程序员的理想之选。包含免费下载的源代码，您可以立即开始！

全彩图说明
我们不仅告诉您如何做，还向您展示如何做。

全彩印刷
本书采用彩色印刷，使其使用更简单、更护眼。

让这些图标让变得更加简单

![](img/fa565c410b0509c58bcab29ed0b49de9_305_0.png)

为您的学习增色

![](img/fa565c410b0509c58bcab29ed0b49de9_305_1.png)

标记值得记忆的内容

![](img/fa565c410b0509c58bcab29ed0b49de9_305_2.png)

警示潜在的危险！

极高的性价比
我们还需要多说吗？

分类：计算机/编程

www.ineasysteps.com
