
# Pandas、SQL 和 Java 数据清洗使用指南

![](img/9781683929048.jpg)

O. Campesato. *Data Wrangling Using Pandas, SQL, and Java*.

出版者承认并尊重公司、制造商和开发者为区分其产品而使用的所有标记。本书中提到的所有品牌名称和产品名称均为其各自公司的商标或服务标记。对服务标记或商标等的任何遗漏（任何形式）或误用均不视为侵犯他人财产的尝试。

美国国会图书馆控制号：2022945211

222324321 印刷于无酸纸

出版者承认并尊重公司、制造商和开发者为区分其产品而使用的所有标记。本书中提到的所有品牌名称和产品名称均为其各自公司的商标或服务标记。对服务标记或商标等的任何遗漏（任何形式）或误用均不视为侵犯他人财产的尝试。

# 前言

## 本书的价值主张是什么？

本书介绍了 `Pandas` 的多种功能、如何在 `MySQL` 中创建数据库和表，以及处理许多数据任务。某些主题简要介绍有两个原因：首先，重要的是让你接触这些概念。在某些情况下，这些主题可能会激发你的兴趣，从而激励你自主学习；在其他情况下，你可能对简要介绍感到满意。其次，对书中涵盖的所有主题进行详尽处理将显著增加其体积，很少有人有时间阅读大部头。

大多数代码示例都非常短（通常小于一页，有时甚至不到半页），如果需要，你可以轻松快速地将代码复制/粘贴到新的 Jupyter notebook 中。对于引用 CSV 文件的 Python 代码示例，你需要在相应的 Jupyter notebook 中添加额外的代码段来访问该 CSV 文件。此外，这些代码示例的运行速度很快，因此你不需要使用 Google Colaboratory 提供的免费 GPU。

如果你确实决定使用 Google Colaboratory，可以轻松地将 Python 代码复制/粘贴到 notebook 中，并使用上传功能上传现有的 Jupyter notebook。记住以下一点：如果 Python 代码引用了 CSV 文件，请确保在 Google Colaboratory 相应的 Jupyter notebook 中包含适当的代码段（如第 1 章中所解释的那样）来访问该 CSV 文件。

### 我需要学习此书中的理论部分吗？

再次强调，答案取决于你计划参与数据分析的程度。例如，如果你计划学习机器学习，那么你可能会学习如何创建和训练模型，这是一项在数据清洗任务之后执行的工作。总的来说，如果你计划成为一名机器学习工程师，你可能需要学习本书书中遇到的所有内容。

### 如何充分利用这本书

有些程序员擅长从文字中学习，而有些人则擅长从示例代码（以及大量的代码）中学习，这意味着没有一种适用于所有风格。

此外，有些程序员想先运行代码，看看它是做什么的，然后回到代码深入细节（而另一些人则采用相反的方法）。

因此，书中有多种类型的代码示例：有的很短，有的很长，还有一些代码示例是从之前的代码示例“构建”而来的。

### 读这本书我需要具备什么知识？

目前对 `Python 3.x` 的了解是有帮助的技能。对其他编程语言（如 `Java`）的知识也很有帮助，因为可以接触编程概念和结构。你掌握的技术性知识越少，理解书中涵盖的各种主题就越需要勤奋。

如果你想确定自己是否能掌握书中的内容，可以浏览一些代码示例，了解哪些内容对你是熟悉的，哪些是新颖的。

### 本书包含生产级代码示例吗？

书中代码示例的主要目的是向你展示基于 `Python` 的库，用于解决各种数据相关任务，同时获得对统计概念的初步理解。清晰度比编写更紧凑但更难理解（且可能更容易产生错误）的代码具有更高的优先级。如果你决定在生产网站中使用书中的任何代码，你应该对该代码进行与你代码库其他部分同样严格的分析。

### 读这本书的非技术先决条件是什么？

虽然这个问题的答案很难量化，但对学习数据清洗和处理的强烈渴望，以及阅读和理解代码示例的动力和自律，是非常重要的。

### 我如何设置命令行？

如果你是 Mac 用户，有三种方法可以实现。第一种方法是使用 `Finder` 导航到 `Applications > Utilities`，然后双击 `Utilities` 应用程序。接下来，如果你已经有一个可用的命令行，可以通过输入以下命令启动一个新的命令行：

```bash
open /Applications/Utilities/Terminal.app
```

Mac 用户的第二种方法是在已经可见的命令行中通过点击该命令行中的 `command+n`，在 MacBook 上打开一个新的命令行，你的 Mac 就会启动另一个命令行。

如果你是 PC 用户，可以安装 `Cygwin`（开源：[`cygwin.com/`](https://cygwin.com/)），它可以模拟 `bash` 命令，或者使用其他工具包如 `MKS`（一种商业产品）。请阅读描述下载和安装过程的在线文档。注意，如果自定义别名定义在主启动文件（如 `.bash_login`）之外的文件中，则不会自动设置。

### 伴随文件

书中所有的代码示例和图形可以通过向 info@merclearning.com 发邮件给出版社来获取。

### 完成这本书后的“下一步”是什么？

这个问题的答案差异很大，主要因为答案很大程度上取决于你的目标。如果你主要对 `NLP` 感兴趣，可以学习更高级的概念，例如 `attention`（注意力）、`transformers` 和与 `BERT` 相关模型。

如果你主要对机器学习感兴趣，机器学习有一些子领域，如深度学习和强化学习（以及深度强化学习），可能会吸引你。幸运的是，有许多资源可用，你可以对这些资源进行互联网搜索。另一点是：你所学习的机器学习方面取决于你是谁。机器学习工程师、数据科学家、经理、学生或软件开发人员的需求都是不同的。

# 第 1 章 Python 简介

本章包含了对 `Python` 的介绍，提供了关于用于安装 `Python` 模块的实用工具的信息、基础 `Python` 结构，以及如何在 `Python` 中处理某些数据类型的方法。

本章的第一部分涵盖如何安装 `Python`、一些 `Python` 环境变量以及如何使用 `Python` 解释器。你将看到 `Python` 代码示例以及如何将 `Python` 代码保存到可以从命令行启动的文本文件中。本章的第二部分介绍了如何处理简单数据类型，如数字、分数和字符串。本章的最后部分讨论了异常以及如何在 `Python` 脚本中使用它们。

注意：书中的 Python 脚本适用于 3。

## Python 工具

`Anaconda` 发行版适用于 Windows、Linux 和 Mac：

[`continuum.io/downloads`](http://continuum.io/downloads)

`Anaconda` 非常适用于 `NumPy`（在第 3 章中讨论）和 `SciPy`（书中未讨论）。如果你是 Windows 用户，`Anaconda` 似乎是一个更好的替代方案。

### `easy_install` 和 `pip`

在安装 Python 模块时，`easy_install` 和 `pip` 都非常好。每当你需要安装 `Python` 模块（书中有很多）时，使用 `easy_install` 或 `pip`，语法如下：

```bash
easy_install <module-name>
pip install <module-name>
```

注意：基于 Python 的模块较于安装，而用 `C` 编写的模块通常更快，但在安装方面更困难。

### `virtualenv`

`virtualenv` 工具允许你创建隔离的 Python 环境，其主页如下：

[`www.virtualenv.org/en/latest/virtualenv.html`](http://www.virtualenv.org/en/latest/virtualenv.html)

`virtualenv` 解决了为不同的应用程序保留正确的依赖和版本（间接权限）的问题。如果你是 Python 初学者，现在可能不需要 `virtualenv`，但请记住这个工具。

### `IPython`

另一个实用工具是 `IPython`（获得过 Jolt 奖），其主页如下：

[`ipython.org/install.html`](http://ipython.org/install.html)

在命令行中输入 `ipython` 来调用 `IPython`：

```bash
ipython
```

上述命令显示如下输出：

```python
Python 3.8.6 (default, Oct  8 2020, 14:06:32)
输入 'copyright', 'credits' 或 'license' 获取更多信息
IPython 7.18.1 -- 一个增强交互式 Python。输入 '?' 获取帮助。

In [1]:
```

在提示符处输入问号（`?`），你将看到一些有用信息，其中部分如下：

```text
IPython -- 一个增强交互式 Python
=========================================

IPython 提供了标准 Python 解释器的完全兼容替代方案，具有方便的 shell 功能、特殊命令、命令历史机制和输出结果缓存。
在你的系统命令行中，输入 `ipython -h` 可查看可用命令行选项。本文档仅描述交互式功能。

获取帮助
------------

在 IPython 中，你有多种方式可以访问帮助：

  ?         -> IPython 功能的介绍和概述（此屏幕）。
  object?   -> 关于 'object' 的详细信息。
  object??  -> 关于 'object' 更详细、冗长的信息。
  %quickref -> 所有 IPython 特有语法和魔法命令的快速参考。
  help      -> 访问 Python 自身的帮助系统。

如果你在终端 IPython 中，可以按 'q' 退出此屏幕。
```

最后，在命令提示符处输入 `quit` 即可退出 `ipython` shell。

下一节将向你展示如何检查机器是否安装了 Python 以及你可以在哪里下载 Python。

## Python 安装

在下载任何内容之前，请在命令行 shell 中输入以下命令检查机器上是否已安装 Python（如果你有 Macbook 或 Linux 机器，很可能已经安装）：

```bash
python -V
```

书中所使用的 Macbook 的输出如下：

```text
Python 3.8.6
```

注意：在你的机器上安装 Python `3.8.6`（或尽可能接近此版本），以便你拥有与测试书中 Python 脚本时相同的 Python 版本。

如果你需要在机器上安装 Python，请访问 Python 主页并选择“Downloads（下载）”链接，或直接访问此网站：

[`www.python.org/download/`](http://www.python.org/download/)

此外，Windows 适用于 PythonWin，其主页如下：

[`www.cgl.ucsf.edu/Outreach/pc204/pythonwin.html`](http://www.cgl.ucsf.edu/Outreach/pc204/pythonwin.html)

使用任何可以创建、编辑和保存 Python 脚本的文本编辑器，并将其保存为纯文本文件（不要使用 Microsoft Word）。

在机器上安装并配置 Python 后，你就可以开始处理书中的 Python 脚本了。

## 设置环境变量 `PATH`（仅限 Windows）

`PATH` 环境变量指定了一个目录列表，当你从命令行指定可执行程序时，系统会搜索这些目录。设置环境以便 Python 可执行文件在每个命令行 shell 中始终可用的良好指南是遵循此处的说明：

[`www.blog.pythonlibrary.org/2011/11/24/python-101-setting-up-python-on-windows/`](http://www.blog.pythonlibrary.org/2011/11/24/python-101-setting-up-python-on-windows/)

## 在你的机器上启动 Python

有三种不同的启动 Python 的方法：

- 使用 Python 交互式解释器。
- 从命令行启动 Python 脚本。
- 使用 IDE。

下一节将向你展示如何从命令行启动 Python 解释器。在本章后面的部分，你将学习如何从命令行启动 Python 脚本以及关于 Python IDE 的知识。

*本书重点是从命令行启动 Python 脚本或在 Python 解释器中输入代码。*

### Python 交互式解释器

通过打开命令行 shell 并输入以下命令启动 Python 交互式解释器：

```bash
python
```

你将看到以下提示符（或类似的内容）：

```python
Python 3.8.6 (default, Oct  8 2020, 14:06:32)
[Clang 12.0.0 (clang-1200.0.32.2)] on darwin
输入 "help", "copyright", "credits" 或 "license" 获取更多信息。
>>>
```

现在在提示符处输入表达式 `2 + 7`：

```python
>>> 2 + 7
```

Python 显示以下结果：

```text
9
>>>
```

按 `ctrl-d` 退出 Python shell。

你可以通过在任何 Python 脚本前加上 `python` 单词从命令行启动它。例如，如果你有一个包含 Python 命令的 Python 脚本 `myscript.py`，如下启动脚本：

```bash
python myscript.py
```

作为一个简单的示例，假设 Python 脚本 `myscript.py` 包含以下 Python 代码：

```python
print('Hello World from Python')
print('2 + 7 = ', 2+7)
```

当你启动上述 Python 脚本时，将看到以下输出：

```text
Hello World from Python
2 + 7 =  9
```

## Python 标识符

Python 标识符是变量、函数、类、模块或其他 Python 对象的名称，有效的标识符遵循以下规则：

- 以字母 A-Z 或 a-z 开始。
- 可以是下划线。
- 可以包含数字 0-9。
- 不能以数字开头。
- 不能是 Python 关键字。

Python 是区分大小写的，因此 `Abc` 和 `abc` 是不同的标识符。

## 行、缩进和多行

与其他语言（如 `Java`）不同，Python 使用缩进而不是大括号。缩进必须保持一致，如下：

```python
if True:
    print("ABC")
else:
    print("DEF")
```

Python 中的多行语句可以使用反斜线（`\`）终止，如下：

```python
total = x1 + \
       x2 + \
       x3
```

你可以通过使用分号（`;`）分隔每个语句在一行指定多个语句，如下：

```python
a=10; b=5; print(a); print(a+b)
```

上述代码的输出为：

```text
10
15
```

注意：Python 不建议使用分号和延续符。

## 引号和注释

Python 允许使用单引号（`'`）、双引号（`"`）、三引号（`'''` 或 `"""`）字符串字面量，只要它们在开头和结尾匹配。你可以使用三引号处理跨行的字符串。以下示例是合法的 Python 字符串：

```python
word = 'word'
line = "This is a sentence."
para = """This is a paragraph. This paragraph contains
more than one sentence."""
```

以字母 `r`（代表“raw”，原始）开头的字符串字面量将所有内容视为字符并“转义”元字符的意思，如下：

```python
a1 = r'\n'
a2 = r'\r'
a3 = r'\t'
print('a1:',a1,'a2:',a2,'a3:',a3)
```

上述代码块的输出如下：

```text
a1: \n a2: \r a3: \t
```

你可以在双引号中嵌入单引号（反之亦然），以显示单引号或双引号。实现相同结果另一种方法是在单引号或双引号前加上反斜线（`\`）字符。以下代码块说明了这些技术：

```python
b1 = "'"
b2 = '"'
b3 = '\''
b4 = "\""
print('b1:',b1,'b2:',b2)
print('b3:',b3,'b4:',b4)
```

上述代码块的输出如下：

```text
b1: ' b2: "
b3: ' b4: "
```

不在字符串字面量中的哈希符号（`#`）是注释的字符。此外，`#` 之后到物理行尾的所有字符都是注释的一部分（并被 Python 解释器忽略）。考虑以下代码块：

```python
#!/usr/bin/python
# First comment
print("Hello, Python!")  # second comment
```

这将产生以下结果：

```text
Hello, Python!
```

注释可以位于语句或表达式后的同一行：

```python
name = "Tom Jones" # This is also comment（这也是注释）
```

你可以像下面一样注释多行：

```python
# This is comment one
# This is comment two
# This is comment three
```

Python 中的空行是指仅包含空白字符、注释或二者兼备的行。

## 将你的代码保存到模块中



早些时候你已经了解了如何从命令行启动 Python 解释器并输入 Python 命令。然而，你在 Python 解释器中输入的所有内容仅对当前会话有效：如果你退出解释器并重新启动，你之前的定义将不再有效。幸运的是，Python 允许你将代码存储在文本文件中，这将在下一节中讨论。

Python 中的 `module`（模块）是一个包含 Python 语句的文本文件。在上一节中，你看到了 Python 解释器如何允许你测试定义在当前会话有效的代码片段。如果你想保留代码片段和其他定义，请将它们放在文本文件中，以便你可以在 Python 解释器之外执行这些代码。

Python 中的最外层语句在模块被首次导入时会从上到下执行，这将设置好它的变量和函数。

Python 模块可以直接从命令行运行，如下所示：

```python
python first.py
```

作为示例，将以下两个语句放在名为 `first.py` 的文本文件中：

```python
x = 3
print(x)
```

输入以下命令：

```bash
Python first.py
```

前一个命令的输出是 3，这与在 Python 解释器中执行前面的代码是一相同的。

当直接运行 Python 模块时，特殊变量 `__name__` 被设置为 `__main__`。你经常会在 Python 模块中看到以下类型的代码：

```python
if __name__ == '__main__':
    # do something here（在这里做一些事情）
    print('Running directly')
```

前面的代码片段允许 Python 确定模块是从命令行启动的还是被导入到另一个 Python 模块中的。

## 一些标准模块

Python 标准库提供了许多可以简化你的 Python 脚本的模块。标准库模块列表可以在网上找到：

[`www.python.org/doc/`](http://www.python.org/doc/)

一些重要的 Python 模块包括 `cgi`、`math`、`os`、`pickle`、`random`、`re`、`socket`、`sys`、`time` 和 `urllib`。

书中的代码示例使用了 `math`、`os`、`random`、`re`、`socket`、`sys`、`time` 和 `urllib` 模块。你需要这些模块才能在代码中使用它们。例如，下面的代码块展示了如何导入四个标准 Python 模块：

```python
import datetime
import re
import sys
import time
```

书中的代码示例导入了上述一个或多个模块，以及其他 Python 模块。

## `help()` 和 `dir()` 函数

在网上搜索 Python 相关主题通常会返回许多带有有用信息的链接。或者，你可以检查官方 Python 文档网站：[`docs.python.org`](http://docs.python.org)。

此外，Python 提供了 `help()` 和 `dir()` 函数，可以从 Python 解释器访问。`help()` 函数显示文档字符串（docstrings），而 `dir()` 函数显示定义的符号。例如，如果你输入 `help(sys)`，将看到 `sys` 模块的文档，而 `dir(sys)` 则显示定义符号的列表。

在 Python 解释器中输入以下命令来显示 Python 中与字符串的方法：

```python
>>> dir(str)
```

前面的命令生成了以下输出：

```python
['__add__', '__class__', '__contains__', '__delattr__', '__doc__',
'__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__',
'__getnewargs__', '__getslice__', '__gt__', '__hash__', '__init__',
'__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__',
'__reduce__', '__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__
setattr__', '__sizeof__', '__str__', '__subclasshook__', '_formatter_
field_name_split', '_formatter_parser', 'capitalize', 'center', 'count',
'decode', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'index',
'isalnum', 'isalpha', 'isdigit', 'islower', 'isspace', 'istitle',
'isupper', 'join', 'ljust', 'lower', 'lstrip', 'partition', 'replace',
'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split',
'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate',
'upper', 'zfill']
```

前面的列表为你提供了内置函数的汇总“转储”（包括一些在本文中讨论的函数）。虽然 `dir()` 没有列出内置函数和变量，但你可以从自动导入名为 `__builtin__` 的 `__builtins__` 模块获取这些信息：

```python
>>> dir(__builtins__)
```

下面的命令显示如何获取关于函数的更多信息：

```python
help(str.lower)
```

输出如下：

```text
Help on method_descriptor:

lower(...) -> string

    Return a copy of the string converted to lowercase.
(END)
```

当你需要关于特定函数的更多信息时，检查在线文档并尝试 `help()` 和 `dir()`。

## 编译时间和运行时代码检查

Python 执行某些编译检查，但大多数检查被推迟到代码执行。因此，如果你的 Python 代码引用了不存在的函数，代码将成功编译。事实上，只有当代码执行路径引用不存在的函数时，代码才会报错。

作为一个简单的示例，考虑以下引用不存在函数 `DoesNotExist` 的 Python 函数 `myFunc`：

```python
def myFunc(x):
    if x == 3:
        print(DoesNotExist(x))
    else:
        print('x: ', x)
```

前面的代码只有在传入值 3 时才会失败。

现在你已经理解了一些基本概念（例如如何使用 Python 解释器）以及如何启动自定义 Python 模块，下一节将讨论原始数据类型。

## 简单数据类型

Python 支持原始数据类型，如数字（整数、浮点数和指数数）、字符串和日期。Python 还支持更复杂的数据类型，如列表（或数组）、元组和字典。接几节将讨论一些 Python 原始数据类型，并带有如何在这些数据类型上执行各种操作的代码片段。

## 数字数字

Python 提供了算术运算来处理数字，这种方式与其他编程语言相似。以下示例涉及整数的算术运算：

```python
>>> 2 + 2
4
>>> 4 / 3
1
>>> 3 * 8
24
```

下面的示例将数字赋值给两个变量并计算它们的积：

```python
>>> x = 4
>>> y = 7
>>> x * y
28
```

以下示例演示了涉及整数的算术运算：

```python
>>> 2 + 2
4
>>> 4 / 3
1
>>> 3 * 8
24
```

注意，两个整数之间的除法（`/`）实际上是截断法，只保留整数结果。下面的示例将一个浮点数转换为指数计数法：

```python
>>> fnum = 0.00012345689000007
>>> "%.14e" % fnum
'1.23456890000070e-04'
```

你可以使用 `int()` 函数和 `float()` 函数将字符串转换为数字：

```python
word1 = "123"
word2 = "456.78"
var1 = int(word1)
var2 = float(word2)
print("var1: ", var1, " var2: ", var2)
```

上一个代码块的输出结果如下：

```text
var1:  123  var2:  456.78
```

或者，你可以使用 `eval()` 函数：

```python
word1 = "123"
word2 = "456.78"
var1 = eval(word1)
var2 = eval(word2)
print("var1: ", var1, " var2: ", var2)
```

如果你尝试转换一个不是有效整数或浮点数的字符串，Python 会抛出异常，因此建议将代码放置在 `try/except` 块中（本章稍后会进行讨论）。

## 使用其他进制

Python 中的数字是 10 进制（默认），但你可以轻松地将数字转换为其他进制。例如，下面的代码块初始化变量 `x` 的值为 1234，然后分别以 2 进制、8 进制和 16 进制显示该数字：

```python
>>> x = 1234
>>> bin(x)
'0b10011010010'
>>> oct(x)
'0o2322'
>>> hex(x)
'0x4d2'
```

如果你想抑制 `0b`、`0o` 或 `0x` 前缀，请使用 `format()` 函数，如下所示：

```python
>>> format(x, 'b')
'10011010010'
>>> format(x, 'o')
'2322'
>>> format(x, 'x')
'4d2'
```

负整数将用负号显示：

```python
>>> x = -1234
>>> format(x, 'b')
'-10011010010'
>>> format(x, 'x')
'-4d2'
```

## `chr()` 函数

Python 的 `chr()` 函数接收一个正整数作为参数，并将其转换为对应的字母值（如果存在）。字母 A 到 Z 的十表示为 65 到 91（对应十六进制的 41 到 5b），小写字母 a 到 z 的十表示为 97 到 122（十六进制的 61 到 7b）。这是一个使用 `chr()` 函数打印大写字母 A 的示例：

```python
>>> x = chr(65)
>>> x
'A'
```

下面的代码块打印了一范围内整数的 ASCII 值：

```python
result = ""
for x in range(65, 90):
    print(x, chr(x))
    result = result + chr(x) + ' '
print("result: ", result)
```

你可以用以下行表示一个字符范围：

```python
for x in range(65, 90):
```

然而，下面的等效代码段更加直观：

```python
for x in range(ord('A'), ord('Z')):
```

如果你想显示小写字母的结果，请将之前的范围从（65,91）更改为以下语句之一：

```python
for x in range(65, 90):
for x in range(ord('a'), ord('z')):
```

## Python 中的 `round()` 函数

Python 的 `round()` 函数允许你将小数值舍入到最近的精度：

```python
>>> round(1.23, 1)
1.2
>>> round(-3.42, 1)
-3.4
```

## Python 中的数字格式化

Python 允许你在打印小数时指定使用的精度位数，如下所示：

```python
>>> x = 1.23456
>>> format(x, '0.2f')
'1.23'
>>> format(x, '0.3f')
'1.235'
>>> 'value is {:0.3f}'.format(x)
'value is 1.235'
>>> from decimal import Decimal
>>> a = Decimal('4.2')
>>> b = Decimal('2.1')
>>> a + b
Decimal('6.3')
>>> print(a + b)
6.3
>>> (a + b) == Decimal('6.3')
True
>>> x = 1234.56789
>>> # 两位精度
>>> format(x, '0.2f')
'1234.57'
>>> # 在 10 个字符内右对齐，一位精度
>>> format(x, '>10.1f')
' 1234.6'
>>> # 左对齐
>>> format(x, '<10.1f')
'1234.6 '
>>> # 中对对齐
>>> format(x, '¹⁰.1f')
' 1234.6 '
>>> # 包含分位符
>>> format(x, ',')
'1,234.56789'
>>> format(x, '0,.1f')
'1,234.6'
```

## 处理分数

Python 支持 `Fraction()` 函数（定义在 `fractions` 模块中），它接受两个整数分别代表分数的分子和分母（分母不能为零）。这里展示了在 Python 中定义和操作分数的几个示例：

```python
>>> from fractions import Fraction
>>> a = Fraction(5, 4)
>>> b = Fraction(7, 16)
>>> print(a + b)
27/16
>>> print(a * b)
35/64
```

然而，正如你可能预期的那样，当你尝试“减去”两个字符串时，会导致一个错误：

```text
>>> 'a' - 'b'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unsupported operand type(s) for -: 'str' and 'str'
```

Python 中的 `try/except` 结构（在本章稍后的部分将讨论）能够让你更优雅地处理上述类型的异常。

## 比较字符串

你可以使用 `lower()` 和 `upper()` 方法分别将字符串转换为小写和大大写，如下所示：

```python
>>> 'Python'.lower()
'python'
>>> 'Python'.upper()
'PYTHON'
>>>
```

`lower()` 和 `upper()` 方法对于对两个 ASCII 字符串进行不区分大小写的比较非常有用。列表 1.2 显示了 `Compare.py` 的内容，它使用 `lower()` 函数来比较两个 ASCII 字符串。

### 列表 1.2：`Compare.py`

```python
x = 'Abc'
y = 'abc'

if (x == y):
    print('x and y: identical')
elif (x.lower() == y.lower()):
    print('x and y: case insensitive match')
else:
    print('x and y: different')
```

由于 `x` 包含混合大小写字母而 `y` 包含小写字母，列表 1.2 显示了如下输出：

```text
x and y: different
```

## 在 Python 中格式化字符串

Python 提供了 `string.ljust()`、`string.rjust()` 和 `string.center()` 函数来对文本字符串进行定位，使其分别左对齐、右对齐和居中。正如你在上一节中看到的，Python 还提供了 `format()` 方法用于高级插值功能。现在在 Python 解释器中输入以下命令：

```python
import string

str1 = 'this is a string'
print(string.ljust(str1, 10))
print(string.rjust(str1, 40))
print(string.center(str1, 40))
```

输出所示：

```text
this is a string
            this is a string
            this is a string
```

## 未初始化的变量和值 `None`

Python 区分未初始化的变量和 `None` 值。前者是一个未被赋值的变量，而 `None` 值是一个表示“无值”的值。集合和方法经常返回 `None` 值，你可以在条件逻辑中测试 `None` 值。

本章的下一部分将向你展示如何使用 Python 内置函数对文本字符串进行“切片和切分”。

## 字符串的切片与拼接

Python 允许你使用数组符号提取字符串的子字符串（称为“切片”）。切片语法为 `start:stop:step`，其中 `start`、`stop` 和 `step` 值是指定起始值、结束值和增量值的整数。Python 切片的一个有趣之处在于你可以使用值 `-1`，它会从字符串的右侧而不是左侧操作。以下是字符串切片的示例：

```python
text1 = "this is a string"
print('First 7 characters:', text1[0:7])
print('Characters 2-4:', text1[2:4])
print('Right-most character:', text1[-1])
print('Right-most 2 characters:', text1[-3:-1])
```

上一个代码块的输出如下：



```
First 7 characters: this is
Characters 2-4: is
Right-most character: g
Right-most 2 characters: in
```

在本章稍后部分，你将看到如何向另一个字符串中间插入一个字符串。

## 测试数字和字母

Python 允许你检查字符串中的每个字符，然后测试该字符是数字还是字母。本节将对正则表达式进行简单介绍。

列表 1.3 显示了 `CharTypes.py` 的内容，说明了如何判断字符串是否包含数字或字符。虽然我们还没有讨论 Python 中的 `if` 语句，但列表 1.3](#ch01.xhtml_list1-3) 中的示例非常直观。

### 列表 1.3：CharTypes.py

```python
str1 = "4"
str2 = "4234"
str3 = "b"
str4 = "abc"
str5 = "a1b2c3"

if(str1.isdigit()):
  print("this is a digit:",str1)

if(str2.isdigit()):
  print("this is a digit:",str2)

if(str3.isalpha()):
  print("this is alphabetic:",str3)

if(str4.isalpha()):
  print("this is alphabetic:",str4)

if(not str5.isalpha()):
  print("this is not pure alphabetic:",str5)

print("capitalized first letter:",str5.title())
```

列表 1.3](#ch01.xhtml_list1-3) 初始化了一些变量，紧接着是两个条件测试，使用 `isdigit()` 函数检查 `str1` 和 `str2` 是否为数字。列表 1.3](#ch01.xhtml_list1-3) 的后续部分检查 `str3`、`str4` 和 `str5` 是否为字母。（此处省略了原文中重复的描述性，已按要求清理）。

列表 1.3](#ch01.xhtml_list1-3) 的输出如下：

```
this is a digit: 4
this is a digit: 4234
this is alphabetic: b
this is alphabetic: abc
this is not pure alphabetic: a1b2c3
capitalized first letter: A1b2c3
```

## 在字符串中搜索和替换

Python 提供了搜索和替换字符串的方法。列表 1.4](#ch01.xhtml_list1-4) 显示了 `FindPos.py` 的内容，展示了如何使用 `find()` 函数搜索一个字符串。

### 列表 1.4：FindPos.py

```python
item1 = 'abc'
item2 = 'Abc'
text = 'This is a string'

pos1 = text.find(item1)
pos2 = text.find(item2)

print('pos1:', pos1)
print('pos2:', pos2)
```

`find()` 函数返回第一次匹配发生的索引；否则 `find()` 返回 `-1`。列表 1.4](#ch01.xhtml_list1-4) 的输出为：

```
pos1: 12
pos2: -1
```

除了 `find()` 方法，当你想要测试元素是否存在时，可以使用 `in` 运算符，如下所示：

```python
>>> lst = [1,2]
>>> 1 in lst
True
```

列表 1.5](#ch01.xhtml_list1-5) 显示了 `Replace.py` 的内容，展示了如何用另一个字符串替换一个字符串。

### 列表 1.5：Replace.py

```python
text = 'This is a string'
text = text.replace('is a', 'was a')
print(text)
```

列表 1.5](#ch01.xhtml_list1-5) 初始化了变量 `text` 并打印其内容。输出为：

```
This was a string
```

## 移除开头结尾字符

Python 提供了 `strip()`、`lstrip()` 和 `rstrip()` 函数来移除文本字符串中的字符。列表 1.6](#ch01.xhtml_list1-6) 显示了 `Remove1.py` 的内容，展示了如何搜索字符串。

### 列表 1.6：Remove1.py

```python
text = '   leading and trailing white space   '
print('text1:','x',text,'y')

text = text.lstrip()
print('text2:','x',text,'y')

text = text.rstrip()
print('text3:','x',text,'y')
```

如果你想移除文本字符串内部多余的空格，可以使用如上一节介绍的那样使用 `replace()` 函数。下面的示例演示了如何实现这一点，该示例还包含了用于正则表达式的 `re` 模块：

```python
import re
text = 'a    b'
a = text.replace(' ', '')
b = re.sub('\s+', ' ', text)

print(a)
print(b)
```

结果如下：

```
ab
a b
```

### 打印不带换行符的文本

如果你需要抑制多个 `print` 语句输出的对象之间的空格和换行符，可以使用字符串拼接或 `write()` 函数。

第一种技术是在打印结果之前，使用 `str()` 函数将每个对象的字符串表示进行拼接。例如，在 Python 中执行以下语句：

```python
x = str(9)+str(0xff)+str(-3.1)
print('x: ',x)
```

输出所示：

```
x:  9255-3.1
```

前的一行包含了数字 `9` 和 `255`（它是十六进制数字 `0xff` 的十进制值）以及 `-3.1` 的拼接。

顺带一提，你对模块和自定义类使用 `str()` 函数。这里有一个涉及 Python 内置模块 `sys` 的示例：

```python
>>> import sys
>>> print(str(sys))
<module 'sys' (built-in)>
```

下面的代码段演示了如何使用 `write()` 函数显示字符串：

```python
import sys
write = sys.stdout.write
write('123')
write('123456789')
```

输出如下：

```
1233
1234567899
```

### 文本对齐

Python 提供了 `ljust()`、`rjust()` 和 `center()` 方法来对齐文本。`ljust()` 和 `rjust()` 函数分别对文本字符串进行左对齐和右对齐，而 `center()` 函数将将字符串居中。在代码块中显示了一个示例：

```python
text = 'Hello World'
text.ljust(20)
'Hello World '
>>> text.rjust(20)
' Hello World'
>>> text.center(20)
' Hello World '
```

你可以使用 Python 的 `format()` 函数来对齐文本。使用 `<`、`>` 或 `^` 字符配合所需的宽度，分别对文本进行右对齐、左对齐和居中。下面的示例演示了你如何指定文本对齐方式：

```python
>>> format(text, '>20')
'         Hello World'
>>>
>>> format(text, '<20')
'Hello World         '
>>>
>>> format(text, '²⁰')
'    Hello World     '
>>>
```

### 处理日期

Python 提供了一系列丰富的与日期相关的函数，这些函数在线上有文档：

[`docs.python.org/2/library/datetime.html`](http://docs.python.org/2/library/datetime.html)

列表 1.7 显示了 Python 脚本 `Datetime2.py` 的内容，该脚本显示了各种日期相关值，例如当前日期和时间；星期、月份和年份；以及自纪元（epoch）以来的秒数时间。

### 列表 1.7：Datetime2.py

```python
import time
import datetime

print("Time in seconds since the epoch: %s" %time.time())
print("Current date and time: " , datetime.datetime.now())
print("Or like this: " ,datetime.datetime.now().strftime("%y-%m-%d-%H-%M"))

print("Current year: ", datetime.date.today().strftime("%Y"))
print("Month of year: ", datetime.date.today().strftime("%B"))
print("Week number of the year: ", datetime.date.today().strftime("%W"))
print("Weekday of the week: ", datetime.date.today().strftime("%w"))
print("Day of year: ", datetime.date.today().strftime("%j"))
print("Day of the month : ", datetime.date.today().strftime("%d"))
print("Day of week: ", datetime.date.today().strftime("%A"))
```

列表 1.8 显示了执行列表 1.7 中代码生成的输出。

### 列表 1.8：datetime2.out

```
Time in seconds since the epoch: 1375144195.66
Current date and time:  2013-07-29 17:29:55.664164
Or like this:  13-07-29-17-29
Current year:  2013
Month of year:  July
Week number of the year:  30
Weekday of the week:  1
Day of year:  210
Day of the month :  29
Day of week:  Monday
```

Python 还允许你对日期相关值进行算术计算，如下代码块所示：

```python
>>> from datetime import timedelta
>>> a = timedelta(days=2, hours=6)
>>> b = timedelta(hours=4.5)
>>> c = a + b
>>> c.days
2
```

#### 字符串转换

列表 1.7 显示了 Python 脚本 `Datetime2.py` 的内容，它显示了各种日期相关值，例如当前日期和时间；星期、月份和年份；以及自纪元以来的秒数时间。

### 列表 1.7：Datetime2.py

```python
import time
import datetime

print("Time in seconds since the epoch: %s" %time.time())
print("Current date and time: " , datetime.datetime.now())
print("Or like this: " ,datetime.datetime.now().strftime("%y-%m-%d-%H-%M"))

print("Current year: ", datetime.date.today().strftime("%Y"))
print("Month of year: ", datetime.date.today().strftime("%B"))
print("Week number of the year: ", datetime.date.today().strftime("%W"))
print("Weekday of the week: ", datetime.date.today().strftime("%w"))
print("Day of year: ", datetime.date.today().strftime("%j"))
print("Day of the month : ", datetime.date.today().strftime("%d"))
print("Day of week: ", datetime.date.today().strftime("%A"))
```

列表 1.8 显示了执行列表 1.7 中代码生成的输出。

### 列表 1.8：datetime2.out

```
Time in seconds since the epoch: 1375144195.66
Current date and time:  2013-07-29 17:29:55.664164
Or like this:  13-07-29-17-29
Current year:  2013
Month of year:  July
Week number of the year:  30
Weekday of the week:  1
Day of year:  210
Day of the month :  29
Day of week:  Monday
```

Python 还允许你对日期相关值进行算术计算，如下代码块所示：

```python
>>> from datetime import timedelta
>>> a = timedelta(days=2, hours=6)
>>> b = timedelta(hours=4.5)
>>> c = a + b
>>> c.days
2
```

#### 异常处理

与 JavaScript 不同，你可以使用 `try/except` 块来处理异常。这里有一个示例：

```python
try:
    x = 4
    y = 'abc'
except TypeError:
    print('cannot add int and str')
```

前面的代码块更紧凑，但你不知道发生了哪种错误类型。Python 允许你定义自定义异常，但这个主题超出了本书的范围。

如所示，前面的代码块指定了更细粒度的异常，随后是一个“通用的” `except` 块，用于处理执行期间发生的所有其他异常。

列表 1.10 显示了 Python 脚本 `Exception1.py` 的内容，它演示了如何处理不同类型的异常，包含了由于文件缺失导致的异常。

### 列表 1.10：Exception1.py

```python
import sys

try:
    f = open('myfile.txt')
    s = f.readline()
    i = int(s.strip())
except IOError as err:
    print("I/O error: {0}".format(err))
except ValueError:
    print("Could not convert data to an integer.")
except:
    print("Unexpected error:", sys.exc_info()[0])
    raise
```

Python 允许你通过 `input()` 函数（Python 2.x 使用 `raw_input()`）从命令行读取用户输入。通常，你会将用户输入赋值给变量，该变量将包含用户从键盘输入的所有字符。当用户按下 `<return>` 键时输入结束（该键包含在输入字符中）。Listing 1.11 显示了 `UserInput1.py` 的内容，它提示用户输入名称，然后使用插值显示响应。

### 列表 1.11：UserInput1.py

```python
userInput = input("Enter your name: ")
print ("Hello %s, my name is Python" % userInput)
```

Listing 1.11 的输出在此处（假设用户输入了单词 Dave）：

```
Hello Dave, my name is Python
```

Listing 1.11 中的 `print()` 语句通过 `%s` 使用字符串插值，它会替换 `%` 符号后的变量值。当你想要指定运行时确定的内容时，此功能显然非常有用。用户输入可能会导致异常（取决于你的代码执行的操作），因此包含异常处理代码是非常重要的。

Listing 1.12 显示了 `UserInput2.py` 的内容，它提示用户输入字符串并在 `try/except` 块中尝试将字符串转换为数字。

### 列表 1.12：UserInput2.py

```python
userInput = input("Enter something: ")

try:
  x = 0 + eval(userInput)
  print('you entered the number:',userInput)
except:
  print(userInput,'is a string')
```



## Listing 1.12

在将用户输入转换为数字的结果加上数字`0`。如果转换成功，将显示一条包含用户输入的消息。如果转换失败，`except`代码块将包含一个显示消息的`print()`语句。

此代码示例使用了`eval()`函数，应该避免使用该函数，以防你的代码执行任意的（可能具有破坏性的）命令。

## Listing 1.13

`UserInput3.py`的内容提示用户输入两个数字并在一对`try/except`块中尝试计算它们的和。

**列表 1.13: UserInput3.py**

```
sum = 0

msg = 'Enter a number:'
val1 = input(msg)

try:
  sum = sum + eval(val1)
except:
  print(val1,'is a string')

msg = 'Enter a number:'
val2 = input(msg)

try:
  sum = sum + eval(val2)
except:
  print(val2,'is a string')

print('The sum of',val1,'and',val2,'is',sum)
```

Listing 1.13 包含两个`try`块，每个块后面都跟着一个`except`语句。第一个`try`块尝试将用户提供的第一个数字加到变量`sum`，第二个`try`块尝试将第二个用户提供的数字加到之前输入的数字。

如果任一输入字符串不是有效数字，就会发生错误消息；如果两个都是有效数字，将显示一条包含输入数字及其和的消息。请务必阅读本章节前面提到的关于`eval()`函数的警告。

## 命令行参数

Python 提供了`getopt`模块来解析命令行选项和参数，而`sys`模块通过`sys.argv`访问任何命令行参数。这有两个作用：

- `sys.argv`是命令行参数的列表。
- `len(sys.argv)`是命令行参数的数量。

在这里，`sys.argv[0]`是程序名，因此如果 Python 程序名为`test.py`，它就匹配`sys.argv[0]`的值。

现在你可以在命令行上为 Python 程序提供输入值，而不是通过提示用户输入来提供输入值。例如，考虑此处所示脚本`test.py`：

```
#!/usr/bin/python
import sys
print('Number of arguments:',len(sys.argv),'arguments')
print('Argument List:', str(sys.argv))
```

如下所示运行上述脚本：

```
python test.py arg1 arg2 arg3
```

这将产生以下结果：

```
Number of arguments: 4 arguments.
Argument List: ['test.py', 'arg1', 'arg2', 'arg3']
```

从命令行指定输入值提供了有用的功能。例如，假设你有一个自定义的 Python 类，包含`add`和`subtract`方法来相加和相减一对数字。

你可以使用命令行参数指定对数字数字执行哪种方法，如下：

```
python MyClass add 3 5
python MyClass subtract 3 5
```

此功能非常有用，因为你可以编程地执行 Python 类中的不同方法，这意味着你也可以为你的代码编写单元测试。

## Listing 1.14

`Hello.py`的内容向你展示了如何使用`sys.argv`。

**列表 1.14: Hello.py**

```
import sys

def main():
  if len(sys.argv) >= 2:
    name = sys.argv[1]
  else:
    name = 'World'
  print('Hello', name)

# 调用 main() 的标准模板
if __name__ == '__main__':
  main()
```

Listing 1.14 使用条件逻辑确定是否执行`main()`。

## 总结

本章展示了如何通过`input()`函数（Python2.x 使用`raw_input()`）从命令行读取用户输入。通常，你会将用户输入赋值给变量，该变量将包含用户从键盘输入的所有字符。当用户按下`<return>`键时输入结束（该键包含在输入字符中）。列表 1.11 显示了`UserInput1.py`的内容提示用户输入名称并使用插值显示响应。

Listing 1.11 的输出在此处（假设用户输入了单词 Dave）：

```
Hello Dave, my name is Python
```

Listing 1.11 中的`print()`语句通过`%s`使用字符串插值，它会替换`%`符号后的变量值。当你想要指定运行时确定的内容时，此功能显然非常有用。用户输入可能会导致异常（取决于你的代码执行的操作），因此包含异常处理代码是非常重要的。

Listing 1.12 显示了`UserInput2.py`的内容，它提示用户输入字符串并在`try/except`块中尝试将字符串转换为数字。

Listing 1.12 在将用户输入转换为数字的结果加上数字`0`。如果转换成功，将显示一条包含用户输入的消息。如果转换失败，`except`代码块将包含一个显示消息的`print()`语句。

此代码示例使用了`eval()`函数，应该避免使用该函数，以防你的代码执行任意的（可能具有破坏性的）命令。

Listing 1.13 显示了`UserInput3.py`的内容提示用户输入两个数字并在一对`try/except`块中尝试计算它们的和。

Listing 1.13 包含两个`try`块，每个块后面都跟着一个`except`语句。第一个`try`块尝试将用户提供的第一个数字加到变量`sum`，第二个`try`块尝试将第二个用户提供的数字加到之前输入的数字。如果任一输入字符串不是有效数字，就会发生错误消息；如果两个都是有效数字，将显示一条包含输入数字及其和的消息。请务必阅读本章节前面提到的关于`eval()`函数的警告。

## 命令行参数

Python 提供了`getopt`模块来解析命令行选项和参数，而`sys`模块通过`sys.argv`访问任何命令行参数。这有两个作用：

- `sys.argv`是命令行参数的列表。
- `len(sys.argv)`是命令行参数的数量。

在这里，`sys.argv[0]`是程序名，因此如果 Python 程序名为`test.py`，它就匹配`sys.argv[0]`的值。

现在你可以在命令行上为 Python 程序提供输入值，而不是通过提示用户输入来提供输入值。例如，考虑此处所示脚本`test.py`：

```
#!/usr/bin/python
import sys
print('Number of arguments:',len(sys.argv),'arguments')
print('Argument List:', str(sys.argv))
```

如下所示运行上述脚本：

```
python test.py arg1 arg2 arg3
```

这将产生以下结果：

```
Number of arguments: 4 arguments.
Argument List: ['test.py', 'arg1', 'arg2', 'arg3']
```

从命令行指定输入值提供了有用的功能。例如，假设你有一个自定义的 Python 类，包含`add`和`subtract`方法来相加和相减一对数字。

你可以使用命令行参数指定对数字数字执行哪种方法，如下：

```
python MyClass add 3 5
python MyClass subtract 3 5
```

此功能非常有用，因为你可以编程地执行 Python 类中的不同方法，这意味着你也可以为你的代码编写单元测试。

Listing 1.14 显示了`Hello.py`的内容，向你展示了如何使用`sys.argv`。

```
import sys

def main():
  if len(sys.argv) >= 2:
    name = sys.argv[1]
  else:
    name = 'World'
  print('Hello', name)

# 调用 main() 的标准模板
if __name__ == '__main__':
  main()
```

在一个理想的世界里，所有数据集都处于完好状态，没有极值、缺失值或错误值。每个特征值都被正确捕获，没有任何混淆可能。此外，由于存在“通用标准”（它定义了所有可能的数据 set 的正确格式和可接受值），因此不需要日期格式、货币值或语言之间进行任何转换。

当然，上段提到的所有场景都可能发生且确实会发生，这也是本章所讨论各种技术的原因。即使你成功创建了一个极其清洁且健壮的数据集，也可能出现其他问题，例如数据漂移（data drift），将在下一节中进行描述。

事实上，即使在机器学习模型部署到生产环境后，数据清洗的任务也并不意味着已经完成。例如，一个每天收集数 TB 或 PB 级数据的在线系统可能包含对模型性能产生不利影响的偏斜值。这些不利影响可以通过与生产模型相关的指标的变化揭示出来。

### 什么是数据漂移？

数据的价值基于其准确性、相关性和年龄。`data drift`指的是相关性降低的数据：在某些情况下，这种现象随着时间的推移而发生；而在其他情况下，是因为应用程序中与特征相关的变化导致某些数据不再具有相关性。

例如，由于各种因素（如不同类型客户的画像），2010 年的在线购买模式可能没有 2020 年的数据那样相关。另一个例子涉及手机库存：停产型号在类系统中的价值会降低。可能有多个因素影响特定数据集中的`data drift`。

处理数据漂移的两种技术是`domain classifier`（领域分类器）和`black-box shift detector`（黑盒偏移检测器），在网上都有讨论：

[`blog.dataiku.com/towards-reliable-mlops-with-drift-detectors`](https://blog.dataiku.com/towards-reliable-mlops-with-drift-detectors)

`data drift`是三种漂移类型之一，所有类型都列在这里：

- 概念漂移（Concept Drift）
- 数据漂移（Data Drift）
- 上游数据变化（Upstream Data Changes）

请进行在线查找以获取更多关于这些漂移类型的信息。

### 什么是数据集？

简单来说，`dataset`数据源（如文本文件），包含数据的行和列。每一行通常被称为`data point`（数据点），每一列被称为`feature`（特征）。`dataset`可以有多种形式：CSV（逗号分隔值）、TSV（制表符分隔值）、Excel 表格、RDMBS 中的表格、NoSQL 数据库中的文档、Web 服务的输出等。正如你所看到的，人们需要分析`dataset`以确定哪些特征是最重要的，哪些特征可以安全地忽略，以便使用定的`dataset`训练模型。

`dataset`的规模从非常小（几个特征和 100 行）到非常大（超过 1000 个特征和超过 100 万行）。如果你不熟悉问题领域，可能很难确定大型数据集中最重要的特征。在这种情况下，你可能需要一位领域专家，他们理解理解特征的重要性、特征之间的相互依赖关系（如果有）以及特征的数据值是否有效。

此外，还有算法（称为`dimensionality reduction algorithms`，降维算法）可以帮助你确定最重要的特征，例如`PCA`（主成分分析），这超出了本书的范围。

### 数据预处理

数据预处理是验证`dataset`内容的初始步骤，涉及对缺失和错误数据值做出决策：

- 处理缺失值
- 清洗“噪声”文本数据
- 移除 HTML 标签
- 移除表情符号
- 处理 Emoji/表情符号
- 过滤数据
- 分组数据
- 处理货币和日期格式

数据清洗是数据整理（data wrangling）的子集，涉及移除不需要的数据和处理缺失数据。对于文本数据，你可能需要移除 HTML 标签、标点符号等。对于数值数据，字母可能与数值数据混合。然而，具有数值特征的`dataset`可能存在错误值或缺失值（后文将讨论）。此外，计算特征值的最小值、最大值、平均值、中位数标准差显然仅适用于数值。

在预处理步骤完成后，会执行`data wrangling`，即将数据转换为新格式。例如，你可能需要将来自多个源的数据合并到单个`dataset`。在这种情况下，你可能需要在不同的测量单位（如日期格式和货币值）之间进行转换，以便以一致的方式在`dataset`中表示数据。

货币和日期值是`i18n`（国际化）的一部分；`L10n`（本地化）针对特定的国家、语言或地区。硬编码值（如文本字符串）可以存储在通常称为`resource bundle`（资源包）的文件中，其中每个字符串通过代码引用。每种语言都有自己的资源包。

### 数据类型

如果你写过计算机程序，那么你就知道许多编程语言存在显式数据类型，例如 C、C++、Java 和 TypeScript。某些编程语言（如 JavaScript 和 awk）不需要用显式类型初始化变量：变量的类型通过隐式类型系统动态推断（即一个不直接暴露给开发者的系统）。

在机器学习中，数据集可以包含不同类型的特征，例如以下一种或多种组合：

- 数值数据（整数/浮点，以及离散/连续）
- 字符/分类数据（不同语言）
- 日期相关数据（不同格式）
- 货币数据（不同格式）
- 二进制数据（是/否，0/1 等）
- 名义数据（多个不相关的值）
- 序数据（多个相关的值）

考虑一个包含房地产数据的数据集，它可能有 30 列（甚至更多），通常具有以下特征：

- 房屋的卧室数量：数值值和离散值
- 平方英尺：数值值和（可能的）连续值
- 城市名称：字符数据
- 建造日期：日期值
- 售价：货币值且可能为连续值
- “待售”状态：二进制数据（“是”或“否”）

年度季节是名义数据的一个例子：尽管许多国家有四个季节，但有些国家只有两个不同的季节。然而，季节可以与不同的温度范围相关（夏季与冬季）。员工薪资等级是序数据的例子：1=初级，2=一年经验，等等。另一个名义数据的例子是颜色集合，例如 {红、绿、蓝}。

分类数据将在本章稍后部分进行详细讨论。

如果你幸运地继承了一个完完的数据集，那么数据清洗任务（后文将讨论）将大大简化：事实上，你可能不需要对该数据集进行任何`data cleaning`。然而，如果你需要创建一个结合了多个数据集的数据集，而这些数据集包含不同日期和货币格式，那么你就需要将它们转换为通用格式。

如果你需要训练一个包含分类数据特征的模型，那么你就需要将这些分类数据转换为数值数据。例如，泰坦尼克号（Titanic）数据集包含一个名为“性别”的特征，其值可能是男性或女性。正如你将在本章稍后部分看到的，`Pandas`可以非常简单地将男性“映射”到`0`，将女性“映射”到`1`。

### 离散数据与连续数据

`Discrete data`（离散数据）是一组可以计数的数值，而`continuous data`（连续数据）必须通过测量。离散数据可以合理地放入下拉列表中，但做出这种判断并没有精确的数值。某人可能认为一个包含`500`个值的列表是离散的，而另一个人可能认为它是连续的。例如，加拿大省份列表和美国州立列表是离散数据值，但世界国家数量（约`200`个）或世界语言数量（超过`7,000`种）也是如此吗？

温度、湿度和气压的数值被认为是连续的。货币也被视为连续的，尽管在两个连续值之间存在可衡量的差异。美国货币的最小单位是 1 美分，即美元的`1/100th`（基于会计的测量使用“密”，即美元的`1/1,000th`）。

连续数据类型可能存在细微的差异。例如，一个身高为`200`厘米的人是身高为`100`厘米的人的两倍（同样，`100`公斤的人与`50`公斤的人也是如此）。但温度不同：`80`度华氏温度的热度不是`40`度华氏温度的两倍。

此外，“连续”一词在数学中的含义并不一定与机器学习中的“连续”相同。在数学中，一个连续变量（假设在二维欧几里得平面上）可以具有不可计数的无限个值。然而，数据集中一个特征如果拥有比能“合理”显示在下拉列表中数量更多的值，它就会被视为连续变量。

例如，股票价格的数值是离散的：它们之间的差异至少为一个美分（或其他某种最小货币单位），也就是说，说股票价格变化了百万分之一美分是没有意义的。但是，由于可能的股票值非常多，它被视为连续变量。同样的说明也适用于汽车里程、环境温度和气压。

### 对连续数据进行“分箱”（Binning）

`binning`（分箱）的概念是指将一组值划分为多个区间，然后将同一区间内的所有数字视为具有相同的值。

作为一个简单的例子，假设数据集中的一个特征包含人的年龄。取值范围大约在`0`到`120`之间，我们可以将其“分箱”为`12`个等距区间，每个区间包含`10`个值：`0`到`9`、`10`到`19`、`20`到`29`等，以此此类推。

然而，如上所述划分人的年龄可能会出现问题。假设 A 人、B 人和 C 人的年龄分别为`29`、`30`和`39`。那么 A 人和 B 人之间可能比 B 人和 C 人之间更相似，但由于年龄划分的方式，B 被归类为比接近 A 更接近 C。事实上，分箱可能会增加第一类错误（假阳性）和第二类错误（假阴性），正如在下面的博客文章讨论的那样（以及一些分箱的替代方案）：



https://medium.com/@peterflom/why-binning-continuous-data-is-almost-always-a-mistake-ad0b3a1d141f

另一个例子是使用四分位数，比之前的年龄分箱例子更加粗糙。分箱的问题在于对处于不同箱的人进行分类所产生的后果，尽管他们彼此非常接近。例如，有些人人因为工资微薄而陷入财务困境，但因为他们的工资高于获得任何援助的截止点而失去了获得资助的资格。

### 通过归一化缩放数值数据

数值范围可能会差异很大，需要注意的是，它们通常需要被缩放到一个较小的范围，例如 `[-1,1]` 或 `[0,1]` 范围内的值，你可以分别通过 `tanh` 函数或 `sigmoid` 函数来实现。

例如，以米为单位测量人的身高涉及 `0.50` 米到 `2.5` 米之间的范围（在绝大多数情况下），而以厘米为单位测量身高则范围在 `50` 厘米到 `250` 厘米之间：这两个单位之间的差异是 100 倍。人以公斤为单位的体重通常在 `5` 公斤到 `200` 公斤之间变化。

因此，`{-1, 0, 1}` 的标准化结果为 `{-1/0.816, 0/0.816, 1/0.816}`，这实际上等于值集合 `{-1.2254, 0, 1.2254}`。

另一个例子，假设随机变量 `X` 的值为 `{-6, 0, 6}`。那么 `mu` 和 `sigma` 的计算如下：

```text
mu       = (SUM xi)/n = (-6 + 0 + 6)/3 = 0

variance = [SUM (xi- mu)²]/n
         = [(-6-0)² + (0-0)² + (6-0)²]/3
         = 72/3
         = 24

sigma    = sqrt(24) = 4.899 (近似值)
```

因此，`{-6, 0, 6}` 的标准化结果为 `{-6/4.899, 0/4.899, 6/4.899}`，这实际上等于值集合 `{-1.2247, 0, 1.2247}`。

在前面的两个例子中，平均值均等于 0，但方差和标准差显著不同。另一点是：一组值的归一化*总是*会产生一组位于 0 和 1 之间的数字。

然而，一组值的标准化可能会产生小于 -1 且大于 1 的数字：当 `sigma` 小于每个项 `|mu – xi|` 的最小值时，就会发生这种情况，其中后者是 `mu` 与每个 `xi` 值之间差值的绝对值。在前面的例子中，最小差值为 1，而 `sigma` 为 `0.816`，因此最大的标准化值大于 1。

### 通过鲁棒标准化对数值数据进行缩放

*鲁棒标准化*技术是标准化的变体，它根据值的子集来计算平均值 `mu` 和标准差 `sigma`。具体而言，仅使用第 25 分位数和 75 分位数之间的值，这忽略了可能包含离群值的第一和第四四位数。让我们定义以下变量：

```text
X25 = 第 25 分位数
X75 = 第 75 分位数
XM = {Xi} 值的平均值
XR = 鲁棒标准化
```

然后根据以下公式计算 `XR`：

```text
XR = (Xi - XM)/(X75 - X25)
```

前面的技术也被称为 `IQR`，它是*四分位间距*（interquartile range）的缩写，你可以在这里查看一个计算示例：

[`en.wikipedia.org/wiki/Interquartile_range`](https://en.wikipedia.org/wiki/Interquartile_range)

### 类别数据中需要关注的内容

本节包含了处理不一致数据值的各种建议，你可以根据与你特定任务相关的任何额外因素决定采用哪些建议。例如，考虑丢弃基数极低（等于或接近 1）的列，以及方差为零或极低的数值列。

接下来，检查类别列的内容，是否存在不一致的拼写或错误。一个很好的例子是性别类别，它可能由以下值的组合：

```text
male
Male
female
Female
m
f
M
F
```

上述性别类别值可以替换为两个类别值（除非你有正当理由保留某些其他值）。此外，如果你正在训练一个分析涉及单一性别的模型，那么你需要确定数据集中的哪些行（如果有）必须被排除。还要检查类别数据列是否存在冗余或缺失的空格。

检查是否存在具有多种数据类型的值，例如一个数值列中的数字以数字形式表示，而数字以字符串或对象的形式存在。还要确保数据格式一致（例如数字作为整数或浮点数），并确保日期具有相同的格式（例如，不要将 `mm/dd/yyyy` 日期格式与另一种日期格式如 `dd/mm/yyyy` 混合）。

### 将类别数据映射到数值值

字符数据通常被称为*类别数据*，示例包括人的姓名、家庭或工作地址以及电子邮件地址。许多类型的类别数据涉及简短的值列表。例如，星期几和一年的月份分别涉及七和十二个不同的值。注意，星期几之间存在关系：每一天都有前一天和后一天，一年的月份也是如此。

然而，汽车的颜色之间是相互独立的：红色并不比蓝色好或坏。但是某种颜色的汽车事故率在统计上可能更高，但我们在这里不讨论这种情况。

将类别值映射到一组数值值有几种常用技术。一个你需要执行此转换的简单示例涉及泰坦尼克号（Titanic）数据集中的性别特征。该特征是训练机器学习模型的相关特征之一。性别特征的值集为 `{M,F}`。正如你将在本章后续部分看到的，`Pandas` 可以非常方便地将值集合 `{M,F}` 转换为值集合 `{0,1}`。

另一种映射技术涉及将一组类别值映射到一组连续整数值。例如，集合 `{Red, Green, Blue}` 可以映射到整数集合 `{0,1,2}`。集合 `{Male, Female}` 可以映射到整数集合 `{0,1}`。星期几可以映射到整数 `{0,1,2,3,4,5,6}`。注意，星期几的格式取决于国家。

另一种技术称为独热编码（one-hot encoding），它将每个值转换为*向量*（如果需要复习可以查看维基百科）。因此，`{Male, Female}` 可以表示为 `[1,0]` 和 `[0,1]`。如果你熟悉矩阵，你会发现性别的向量构成了一个 2x2 矩阵，而颜色 `{R,G,B}` 将构成一个 3x3 矩阵，如下：

```text
[1,0,0]
[0,1,0]
[0,0,1]
```

前面的集合看起来像 3x3 矩阵。事实上，这种技术可以简单地泛化。具体来说，如果你有 `n` 个类别值，可以将其中每一个值映射到 `nx` 矩阵。

另一个例子是头衔 `{"Intern", "Junior", "Mid-Range", "Senior", "Project Leader", "Dev Manager"}` 在薪资方面存在层级关系（但我们现在跳过这一细节）。

另一组类别数据涉及季节：`{"Spring", "Summer", "Autumn", "Winter"}`，虽然这些值通常是独立的，但在某些情况下季节是非常重要的。例如，月雨量、平均温度、犯罪率和贷款率可能取决于季节、月份、每周甚至是年份。

如果一个特征具有大量的类别值，独热编码将为每个数据点产生许多额外的列。由于新列的大部分值为 0，这会增加数据集的稀疏性，从而导致过拟合，并因此对你在训练过程中采用的机器学习算法产生不利影响。

另一种解决方案是使用基于序列的解决方案，将 `N` 个类别映射到整数 `1, 2, ..., N`。另一种解决方案涉及检查类别值的行频率。例如，假设 `N` 等于 20，且有 3 个类别值在给定特征中出现了 95%。你可以尝试以下操作：

1. 为这三个类别值分配 1、2 和 3。
2. 分配反映这些类别值频率的数值。
3. 为剩余的类别值分配“OTHER”（其他）。
4. 删除类别值属于那 5% 的行。

```text
MM/DD/YY
MM/DD/YYYY
DD/MM/YY
YY/MM/DD
M/D/YY
YY/M/D
DDYY
YYMMDD
```

如果你需要合并包含不同格式的数据集，那么将不同的格式转换为统一的格式将确保一致性。

## 处理货币

货币的格式取决于国家，这包括对 `,` 和 `.` 的不同解释。例如，1,124.78 在美国表示“一千一百二十四点七八”，而 1.124,78 在欧洲具有相同的意思（即 `.` 和 `,` 符号互换）。

如果你需要合并包含不同格式的数据集，那么你可能需要将所有不同的格式转换为统一的格式。另一个需要考虑的细节是：汇率可能会波动，从而影响税费、滞纳等的计算。尽管你可能足够幸运不需要处理这些问题，但要注意它们。

## 处理离群值和异常

简单来说，离群值是“正常”值范围之外的异常数据。例如，一个人的身高通常在 30 厘米到 250 厘米之间。因此，电子表格中身高为 5 厘米或 500 厘米的数据点就是离群值。这些离群值的结果可能涉及重大的财务或物理损失（尽管它们可能会影响 `model` 的准确性）。

异常也位于“正常”值范围之外（与离群值一样），但它们通常比离群值更具有问题、“后果”。例如，考虑这样做的情况：一个住在加州的人突然在纽约进行了信用卡购买。如果此人正在度假（或出差），那么这次购买就是一个离群值（其典型的购买模式），但这不是问题。然而，如果在进行信用卡购买时该人在加州，那么它可能是信用卡欺诈，也是异常。

遗憾的是，没有简单的方法来决定如何处理数据集中的异常和离群值。虽然你可以删除包含离群值的行，但这会导致数据集（因此 `model`）丢失价值信息。你可以尝试修改数据值（见下文），但再次可能导致 `model` 错误的推理。另一种可能性是用包含异常和离群值的数据集训练模型，然后使用移除了异常和离群值的数据集训练模型。比较这两个结果，看看你是否能关于异常和离群值推断出任何有意义的内容。

### 离群值检测/移除

虽然保留还是删除离群值由你做决定，但有一些技术可以帮助你检测数据集中的离群值。以下是技术的短列表，以及简要描述和更多信息的链接：

- 修剪 (trimming)
- 缩尾处理 (winsorizing)
- 最小协方差行列 (minimum covariance determinant)
- 局部离群值因子 (local outlier factor)
- `Huber` 和岭回归 (Huber and Ridge regressions)
- 孤立森林（基于树的算法）
- 单类 `SVM` (one-class SVM)

也许 `trimming` 是简单的技术（删除离群值之外），它涉及移除特征位于顶部 5% 或底部 5% 范围的行。对数据进行 `缩尾` 是修剪的改进：将顶部 5% 范围的值设置为第 95 分位数的最大值，并将底部 5% 范围的值设置为第 5 分位的最小值。

`最小协方差行列` 是一种基于协方差的技术，使用该技术的 Python 代码示例可以从以下网站下载：

[`scikit-learn.org/stable/modules/outlier_detection.html`](https://scikit-learn.org/stable/modules/outlier_detection.html)

`局部离群值因子` (`LOF`) 技术是一种无监督技术，通过 `kNN`（k-最近邻）算法计算局部异常评分。使用 `LOF` 的文档和短代码示例在线获取：

[`scikit-learn.org/stable/modules/generated/sklearn.neighbors.LocalOutlierFactor.html`](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.LocalOutlierFactor.html)

另外两种技术涉及 `Huber` 和 `Ridge` 类，它们都包含在 `Sklearn` 中。`Huber` 对离群值不敏感，因为它通过线性损失计算，类似于 `MAE`（平均绝对误差）。比较 `Huber` 和 `Ridge` 回归算法的代码示例可以从以下网站下载：

[`scikit-learn.org/stable/auto_examples/linear_model/plot_huber_vs_ridge.html`](https://scikit-learn.org/stable/auto_examples/linear_model/plot_huber_vs_ridge.html)

你还可以探索 `Theil-Sen` 估计器和 `RANSAC`，它们对离群值具有“鲁棒性”：

[`scikit-learn.org/stable/auto_examples/linear_model/plot_theilsen.html`](https://scikit-learn.org/stable/auto_examples/linear_model/plot_theilsen.html)

Listing 2.2 的改进之处在于，你可以指定一组值并从中计算上限和下限范围值，而新的代码块以粗体形式显示。

列表 2.2: `numpy_outliers2.py`

```python
import numpy as np

arr1 = np.array([2,5,7,9,9,40])
print("values:",arr1)

data_mean = np.mean(arr1)
data_std  = np.std(arr1)
print("data_mean:",data_mean)
print("data_std:" ,data_std)
print()

multipliers = np.array([0.5,1.0,1.5,2.0,2.5,3.0])
for multiplier in multipliers:
  cut_off = data_std * multiplier
  lower, upper = data_mean - cut_off, data_mean + cut_off
  print("=> multiplier:  ",multiplier)
  print("lower cutoff:",lower)
  print("upper cutoff:",upper)

  outliers = [x for x in df['data'] if x < lower or x > upper]
  print('Identified outliers: %d' % len(outliers))
  print("outliers:",outliers)
  print()
```

Listing 2.2 包含了一块新代码，它将变量 `multipliers` 初始化为数值值数组，用于寻找离群值。尽管你在真实数据集上可能会使用 `2.0` 或更大的值，但这一范围数字可以让你对检测离群值有更好的感。运行 Listing 2.2 中的代码，你将看到以下输出：

```text
values: [2  5  7  9  9  40]
data_mean: 12.0
data_std: 12.754084313139327

lower cutoff: -7.131126469708988
upper cutoff: 31.13112646970899

Identified outliers: 1
outliers: [40]
=> multiplier:   0.5
lower cutoff: 5.622957843430337
upper cutoff: 18.377042156569665
Identified outliers: 3
outliers: [2, 5, 40]

=> multiplier:   1.0
lower cutoff: -0.7540843131393267
upper cutoff: 24.754084313139327
Identified outliers: 1
outliers: [40]

=> multiplier:   1.5
lower cutoff: -7.131126469708988
upper cutoff: 31.13112646970899
Identified outliers: 1
outliers: [40]

=> multiplier:   2.0
lower cutoff: -13.508168626278653
upper cutoff: 37.50816862627865
Identified outliers: 1
outliers: [40]

=> multiplier:   2.5
lower cutoff: -19.88521078284832
upper cutoff: 43.88521078284832
Identified outliers: 0
outliers: []

=> multiplier:   3.0
lower cutoff: -26.262252939417976
upper cutoff: 50.26225293941798
Identified outliers: 0
outliers: []
```

### 使用 `PANDAS` 寻找离群值

虽然我们在第三章中讨论了 `Pandas`，但本节的代码仅涉及非常简单的 `Pandas` 数据框、`mean()` 方法和 `std()` 方法。

Listing 2.3 显示了 `pandas_outliers1.py` 的内容，说明了如何使用 `Pandas` 在数字数组中寻找离群值。

列表 2.3: `pandas_outliers1.py`



```python
import pandas as pd

df = pd.DataFrame([2, 5, 7, 9, 9, 40])
df.columns = ["data"]

data_mean = df["data"].mean()
data_std = df["data"].std()
print("data_mean:", data_mean)
print("data_std:", data_std)
print()

multiplier = 1.5
cut_off = data_std * multiplier
lower, upper = data_mean - cut_off, data_mean + cut_off
print("lower cutoff:", lower)
print("upper cutoff:", upper)
print()

outliers = [x for x in df["data"] if x < lower or x > upper]
print("Identified outliers: %d" % len(outliers))
print("outliers:", outliers)
```

Listing 2.3 首先定义了一个 Pandas 数据框，然后计算这些数字的平均值标准差。下一块代码根据`cut_off`变量初始化了两个代表上限和下限的数字。数据框中位于下限左侧或上限右侧的任何数字都被视为离群值。Listing 2.3 的最后部分初始化了离群值变量`outliers`，并打印了这些值。运行 Listing 2.3 中的代码，你将看到：

```
 values: [2  5  7  9  9  40]
data_mean: 12.0
data_std: 12.754084313139327

lower cutoff: -7.131126469708988
upper cutoff: 31.13112646970899

Identified outliers: 1
outliers: [40]
```

之前的代码硬编码的值来计算上限和下限范围。Listing 2.2 的改进之处在于你可以指定一组值并从中计算上限和下限范围值，而新的代码块以粗体形式显示。列表 2.4: `pandas_outliers.py`

```python
import pandas as pd

df = pd.DataFrame([2, 5, 7, 9, 9, 40])
df = pd.DataFrame([2, 5, 7, 8, 42])
df = pd.DataFrame([2, 5, 7, 8, 42, 492])
df.columns = ["data"]
print("=> data values:")
print(df["data"])
data_mean = df["data"].mean()
data_std = df["data"].std()
print("=> data_mean:", data_mean)
print("=> data_std:", data_std)

multipliers = [0.5, 1.0, 1.5, 2.0, 2.5, 3.0]
for multiplier in multipliers:
    cut_off = data_std * multiplier
    lower, upper = data_mean - cut_off, data_mean + cut_off
    print("=> multiplier: ", multiplier)
    print("lower cutoff:", lower)
    print("upper cutoff:", upper)

    outliers = [x for x in df["data"] if x < lower or x > upper]
    print("Identified outliers: %d" % len(outliers))
    print("outliers:", outliers)
```

Listing 2.4 包含了一块新代码，它将变量`multipliers`初始化为数值数组，用于寻找离群值。尽管你在真实数据集上可能会使用`2.0`或更大的值，但这一范围数字可以让你对检测离群值有更好的感。运行 Listing 2.4 中的代码，你将看到以下输出：

```
 => data values:
0      2
1      5
2      7
3      8
4     42
5    492
Name: data, dtype: int64
=> data_mean: 92.66666666666667
=> data_std: 196.187325448579

=> multiplier:   0.5
lower cutoff: -5.42699605762283
upper cutoff: 190.76032939095617
Identified outliers: 1
outliers: [492]

=> multiplier:   1.0
lower cutoff: -103.52065878191233
upper cutoff: 288.85399211524566
Identified outliers: 1
outliers: [492]

=> multiplier:   1.5
lower cutoff: -201.6143215062018
upper cutoff: 386.9476548395352
Identified outliers: 1
outliers: [492]

=> multiplier:   2.0
lower cutoff: -299.7079842304913
upper cutoff: 485.0413175638247
Identified outliers: 1
outliers: [492]

=> multiplier:   2.5
lower cutoff: -397.80164695478084
upper cutoff: 583.1349802881142
Identified outliers: 0
outliers: []

=> multiplier:   3.0
lower cutoff: -495.8953096790703
upper cutoff: 681.2286430124036
Identified outliers: 0
outliers: []
```

### 计算 Z-Score 以寻找离群值

一组数字的 z-score 是通过标准化这些数字计算的，这涉及到从每个数字中减去它们的平均值，然后除以标准差。尽管你可以手动执行这些步骤，但 SciPy 库简化了涉及的步骤。如果有需要，可以通过以下命令安装此包：

```bash
pip3 install scipy
```

Listing 2.5 显示了`outliers_zscores.py`的内容，说明了如何在一个数字数组中寻找离群值。正如你所看到的，这个代码示例依赖于 NumPy、Pandas 和 SciPy 的便利方法。

列表 2.5: `outliers_zscores.py`

```python
import numpy as np
import pandas as pd
from scipy import stats

arr1 = np.array([2, 5, 7, 9, 9, 40])
print("values:", arr1)

df = pd.DataFrame(arr1)

zscores = np.abs(stats.zscore(df))
print("z scores:")
print(zscores)
print()

upper = 2.0
lower = 0.5
print("=> upper outliers:")
print(zscores[np.where(zscores > upper)])
print()
print("=> lower outliers:")
print(zscores[np.where(zscores < lower)])
print()
```

```python
zscores = np.abs(stats.zscore(df))
```

下一段代码初始化了变量`upper`和`lower`。小于`lower`值或大于`upper`值的 z-score 被视为离群值，并会显示这些值。运行列表 2.3 中的代码，你将看到以下输出：

```
 values: [2  5  7  9  9  40]
z scores:
[[0.78406256]
 [0.54884379]
 [0.39203128]
 [0.23521877]
 [0.23521877]
 [2.19537517]]

=> upper outliers:
[2.19537517]

=> lower outliers:
[0.39203128 0.23521877 0.23521877]
```

### 使用 SKLEAR 寻找离群值（可选）

本节是可选的，因为代码涉及`sklearn.covariance`中的`EllipticEnvelope`类，而我们在书中并未介绍该类。然而，阅读这些代码并将其与之前的寻找离群值代码示例进行对比仍然是有值的。

列表 2.6 显示了`elliptic_envelope_outliers.py`的内容，展示了如何使用`Pandas`在数字数组中寻找离群值。

列表 2.6：`elliptic_envelope_outliers.py`

```python
# pip3 install scikit-learn as sklearn
from sklearn.covariance import EllipticEnvelope
import numpy as np

# 创建正态分布样本:
Xdata = np.random.normal(loc=5, scale=2, size=10).reshape(-1, 1)
print("Xdata values:")
print(Xdata)
print()

# 实例化并拟合估计器:
envelope = EllipticEnvelope(random_state=0)
envelope.fit(Xdata)

# 创建测试集:
test = np.array([0, 2, 4, 6, 8, 10, 15, 20, 25, 30]).reshape(-1, 1)
print("test values:")
print(test)
print()

# predict() 对内值返回 1，对离群值返回 -1:
print("envelope.predict(test):")
print(envelope.predict(test))
```

列表 2.6 从几个导入语句开始，然后将变量`Xdata`初始化为来自高斯分布的随机数列向量。下一段代码片段将变量`envelope`初始化为`Sklearn`中`EllipticEnvelope`的实例（这将决定`Xdata`中是否存在离群值），然后对`Xdata`中的数据值进行训练。

列表 2.6 的后续部分将变量`test`初始化为列向量，类似于`Xdata`的初始化方式。列表 2.6 的最后一部分对变量`test`中的值进行预测并显示结果：值 `-1` 表示为离群值。运行列表 2.6 中的代码，你将看到以下输出：

```
 Xdata values:
[[5.21730452]
 [5.49182377]
 [2.87553776]
 [4.20297013]
 [8.29562026]
 [5.78097977]
 [4.86631006]
 [5.47184212]
 [4.77954946]
 [8.66184028]]

test values:
[[ 0]
 [ 2]
 [ 4]
 [ 6]
 [ 8]
 [10]
 [15]
 [20]
 [25]
 [30]]
envelope.predict(test):
[-1  1  1  1  1 -1 -1 -1 -1 -1]
```

有关数据清洗和预处理的更多信息，请参考以下网站：

[`www.kdnuggets.com/2019/11/data-cleaning-preprocessing-beginners.html`](https://www.kdnuggets.com/2019/11/data-cleaning-preprocessing-beginners.html)

### 处理缺失数据

数据集中缺失值有多种原因，此处列出了一些：

* 值不可用
* 收集不当
* 数据录入不准确

尽管你可能想总是用具体值替换缺失值，但在某些情况下，你无法确定某个值。一个简单的例子是，一份包含针对 30 岁以下人群问题的问卷，对于 30 岁以上的受访者将有一个缺失值，在这种情况下，为缺失值指定一个值是不正确的。考虑到这些细节，填充缺失值有多种方法，此处列出了：

* 删除包含缺失值的行
* 使用均值填充缺失值
* 使用中位数填充缺失值
* 使用众数填充缺失值
* 删除包含缺失值的行

#### 数值插值：何时零是有效值？

通常情况下，可以使用现有值的均值而不是零值，反之亦然。作为第一个例子，假设某个属性包含一组人的身高。在这种情况下，均值可能是一个合理的插值方案，而 0 则存在以下问题：

1. 它是无效值（没有人的身高是 0）。
2. 它会偏斜统计量，如均值和方差。

当允许最小值为正数时，你可能想用均值代替 0，但在处理不平衡数据集时要加小心。

# SMOTE（合成少数类过采样技术）

`Random resampling`通过对数据空间进行重采样来平衡类别分布。`random undersampling`技术从数据集中移除属于多数类的样本，涉及以下内容：

* 随机从多数类中删除样本
* 可以有放回或不放回地进行
* 缓解数据集中的不平衡问题
* 可能会增加分类器的方差
* 可能会丢弃有用或重要的样本

然而，随机欠采样对于极不平衡的数据集效果并不好，例如两个类别的划分比例为 99% 和 1%。此外，欠采样可能会导致丢失对模型有用的信息。

`Random oversampling`从少数类中生成新样本：这种技术通过复制少数类的示例来实现。

另一个可以考虑的选项是`scikit-learn-contrib`项目中的`imbalanced-learn` Python 包。该项目为表现出类不平衡的数据集提供了各种重采样技术。更多细节可以在网上查找到：

[https://github.com/scikit-learn-contrib/imbalanced-learn]

另一个著名的技术被称为`SMOTE`，它涉及数据增强（即合成新的数据样本）。`SMOTE`最初通过`kNN`算法开发（也有其他可选方案），它是处理不平衡类别的有效技术。下一节将详细讨论`SMOTE`。

## 什么是 SMOTE？

`SMOTE`（合成少数类过采样技术）是一种为数据集合成新样本的技术。该技术基于线性插值：

* 步骤 1：在特征空间中选择接近的样本。
* 步骤 2：在特征空间的样本之间画一条直线。
* 步骤 3：在该直线的某一点上绘制新样本。

`SMOTE`算法更详细的解释如下：

* 从少数类中随机选择样本“a”。
* 为该示例找到`k`个最近邻。
* 从这些最近邻中随机选择一个邻居“b”。
* 创建一条连接“a”和“b”的直线`L`。
* 在直线`L`上随机选择一个或多个点“c”。

如有需要，你可以对其他的（`k–1`）个最近邻重复此过程，以使合成值更均匀地分布在各个最近邻之间。

### SMOTE 扩展

最初的`SMOTE`算法基于`kNN`分类算法，该算法已通过各种方式进行了扩展，例如将`kNN`替换为`SVM`。`SMOTE`扩展列表如下：

* 选择性合成样本生成
* `Borderline-SMOTE`（`kNN`）
* `Borderline-SMOTE`（`SVM`）
* 自适应合成采样（ADASYN）

可以在网上搜索这些算法的更多细节，并访问以下 URL：

[https://en.wikipedia.org/wiki/Oversampling_and_undersampling_in_data_analysis]

## 偏差与方差的权衡

本节从机器学习的角度介绍，但偏置和方差的概念在机器学习之外也高度相关，因此阅读本节以及上一节可能仍然是有值的。

机器学习中的`Bias`（偏置）可能是由于学习算法中的错误假设导致的误差。高偏置可能会导致算法漏掉特征与目标输出之间的相关关系（欠拟合）。预测偏差可能由于“噪声”数据、不完整的特征集或有偏的训练样本而产生。

由于偏差引起的误差是模型的预期（或平均）预测值与你想预测的正确值之间的差异。重复多次模型构建过程，每次收集新数据并进行分析以生成新模型。生成的模型具有一系列预测值，因为底层数据集具有程度的随机性。偏置衡量了这些模型的预测值偏离正确值的程度。

机器学习中的`Variance`（方差）是与平均值的平方偏差的期望值。高方差会导致算法对训练数据中的随机噪声建模而非预期的输出（过拟合）。此外，向模型添加参数会增加其复杂性，增加方差并降低偏置。

**要记住：处理偏差和方差涉及处理欠拟合和过拟合。**

由于方差引起的误差是模型对给定数据点预测的可变性。和一样，重复整个模型构建过程，方差是给定点的预测在不同模型实例之间变化的程度。

如果你处理过数据集并进行过数据分析，你已经知道寻找平衡样本可能是困难或极不现实的。此外，对数据集中的数据进行分析至关重要，但无法保证产生一个 100%“干净”的数据集。

`biased statistic`（有偏统计量）是指与所估计总体实体存在系统性差异的统计量。在更通俗的术语中，如果数据样本“偏爱”或“倾向于”总体的某个方面，那么该样本就有偏差。例如，如果你更喜欢喜剧片而不是任何其他类型的电影，那么显然你更有可能选择喜剧片而不是剧情或科幻片。因此，你的电影选择样本中电影类型的频率图将更密集地聚集在喜剧周围。

然而，如果你对电影有广泛的偏好，那么相应的频率图将更加多样化，因此取值范围更大。

### 数据中的偏差类型

除了上一节讨论的偏差-方差权衡外，还有几种类型的偏差：

* 可用性偏差（availability bias）
* 确认偏差（confirmation bias）



- 虚假因果（false causality）
- 沉没成本谬误（sunk cost fallacy）
- 生存者偏差（survivorship bias）

`availability bias` 类似于根据例外制定“规则”。例如，吸烟和癌症之间存在已知联系，但存在例外。如果你发现某人每天抽三包烟并持续四十年后依然健康，你能断定吸烟不会导致癌症吗？

`confirmation bias` 指人们倾向于关注证实其信念的数据，同时忽略与信念相矛盾的数据。

`虚假因果`（False causality）是指当你错误地断言某一事件的发生导致另一个事件的发生时。最著名的例子之一涉及夏季纽约冰淇淋消费量与暴力犯罪之间的关系。由于夏天更多人吃冰淇淋，所以这“导致”了更多暴力犯罪，这是一种虚假因果关系。其他因素（如温度升高）可能与犯罪的增加有关。然而，区分相关性和因果关系至关重要：后者的联系比前者强得多，而且建立因果关系而非相关性也困难得多。

`沉没成本`（Sunk cost）指的是已经支出且无法收回的东西（通常是金钱）。一个常见的例子是赌场赌博：人们陷入了投入更多钱来收回已经损失的大额资金的模式中。虽然存在人们追回金钱的情况，但在许多（或大多数？）情况下，人们仅仅因为继续投入资金而遭受了更大的损失。（因此，我们有句谚语，“是时候止损抽身了。”）

`幸存者偏差`（Survivorship bias）是指分析特定的“正面”数据子集，而忽略“负面”数据。这种偏差出现在各种情况下，例如受到那些讲述自己白手起家成功故事的人（“正面”数据）的影响，而忽略了在类似追求中没有成功的人（这通常占很大比例，即“负面”数据）的命运。因此，虽然个人确实有可能克服许多困难并取得成功，但这种成功率真的是千分之一（甚至更低）吗？

## 分析分类器（可选）

本节被标记为“可选”，因为其内容涉及机器学习分类器，而这并不是本书的重点。然而，浏览一下这些材料仍然值得的，或者可能可以在你对机器学习分类器有了基本了解后回到本节。

目前有几种著名的技术可以用于分析机器学习分类器的质量。其中两种技术是 `LIME` 和 `ANOVA`，它们都将在接下来的小节中进行讨论。

### 什么是 LIME？

`LIME` 是局部可解释模型无关解释（Local Interpretable Model-Agnostic Explanations）的缩写。`LIME` 是一种模型无关的技术，可以用于机器学习模型。该技术的直观原理很简单：对数据样本进行微小的随机更改，然后观察预测变化的方式（或是否变化）。其直观原理涉及（稍微）改变输出，然后观察输出发生了什么。

类比一下，考虑对满载易腐食品的车进行细菌检测的食品检测员。显然，测试卡车中的每件食品（或每节车厢）是不可能的，因此检测员进行“抽检”，即测试随机选择的物品。类似地，`LIME` 在随机位置对输入数据进行微小更改，然后分析相关输出值的变化。

然而，当你使用 `LIME` 处理给定模型的输入数据时，有两点需要注意：

1. 输入值的实际更改是针对特定模型的。
2. 该技术适用于可解释的输入。

可解释输入的示例包括机器学习分类器（如树和随机森林）以及如 `BoW` 等自然语言处理（NLP）技术。不可解释的输入涉及“稠密”数据，例如词嵌入（一个浮点数向量）。

你也可以用另一个涉及可解释数据的模型来替换你的模型，但你需要评估该近似相对于原始模型的准确性有多高。

### 什么是 ANOVA？

`ANOVA` 是方差分析（analysis of variance）的缩写，它尝试分析从总体中提取的样本平均值之间的差异。`ANOVA` 允许你测试多个平均值是否相等。更重要的是，`ANOVA` 可以帮助减少第一类错误（假阳性）和第二类错误（假阴性）。例如，假设 A 人被诊断为患有癌症，而 B 人被诊断为健康，且这两个诊断都是错误的。那么 A 人的结果是假阳性，而 B 人的结果是假阴性。通常情况下，假阳性测试结果远比假阴性测试结果要好。

`ANOVA` 涉及实验设计和假设检验，这可以在各种情况下产生有意义的结果。例如，假设一个数据集包含一个可以划分为若干合理同质组的特征。接下来，分析每组的方差并进行比较，目标是确定给定特征值的不同方差来源。有关关于 `ANOVA` 的更多信息，请访问以下链接：

<https://en.wikipedia.org/wiki/Analysis_of_variance>

### 总结

本章从对数据集的解释、数据清洗的描述以及关于各种类型数据的详细介绍开始。然后你学习了缩放数值数据的技术，如归一化和标准化。你了解了如何将类别数据转换为数值，以及如何处理日期和货币。

接着，你学习了如何处理离群值、异常值和缺失数据，以及处理这些场景的各种技术。你还学习了不平衡数据，以及评估使用 `SMOTE` 处理数据集中不平衡类别的方法。此外，你学习了偏差-方差权衡以及各种类型的统计偏差。最后，你学习了使用两种技术——`LIME` 和 `ANOVA` 的分类器。

# 第 3 章

## Pandas 简介

本章介绍了 `Pandas` 库，并包含了若干说明有用 `Pandas` 特性的代码示例。每个节的标题都清楚地指示了其内容，因此你可以轻松扫描本章，找到对你来说是新内容的章节。这种方法将帮助你在阅读本章内容时高效利用时间。

本章的第一部分包含 `Pandas` 的简要介绍，随后是说明如何定义 `Pandas` DataFrame 以及显示其属性的代码示例。请注意，本章专门介绍 `DataFrame`。有一个代码块说明了如何定义 `Pandas Series`，如果你想了解更多关于这种 `Pandas Series` 的信息，可以在网上进行搜索。

本章的第二部分讨论了你可以创建的各种类型 DataFrame，例如数值型和布尔型 DataFrame。此外，你还将看到使用 `NumPy` 函数和随机数创建 DataFrame 的示例。你也将看到在 Python 字典和 JSON 数据之间进行转换的示例，以及如何从 JSON 数据创建 `Pandas` DataFrame。

### 什么是 Pandas？

`Pandas` 是一个与其他 Python 库（如 `NumPy` 和 `Matplotlib`）兼容的 Python 库。打开命令行并调用以下适用于 Python 3.x 的命令来安装 `Pandas`：

```bash
pip3 install pandas
```

简单来说，Pandas 数据框（data frame）是一个二维数据结构，用行和列来考虑这种数据结构会非常方便。数据框可以被标记（包括行和列），且列可以包含不同的数据类型。数据集源可以是数据文件、数据库表或 Web 服务。Pandas 数据框的特征包括：

- 数据框方法
- 数据框统计信息
- 分组、透视和重塑
- 处理缺失数据
- 合并数据框

## 数据框与数据清洗任务

你需要执行的特定任务取决于数据集的结构和内容。通常，你将执行一个包含以下步骤的工作流（不一定总是按此顺序），所有步骤都可以通过 Pandas 数据框完成：

- 将数据读入数据框
- 显示数据框顶部数据
- 显示列的数据类型
- 显示非缺失值
- 将 NA 替换为某个值
- 遍历列
- 每列的统计信息
- 查找缺失值
- 缺失值总数
- 缺失值百分比
- 排序表格值
- 打印摘要信息
- 查找缺失值大于 50% 的列
- 重命名列

## PandasAS 数据框示例

Listing 3.1 显示了 `pandas_df.py` 的内容，说明了如何定义几个 Pandas 数据框并显示它们的内容。

**代码列表 3.1：`pandas_df.py`**

```python
import pandas as pd
import numpy as np

myvector1 = np.array([1,2,3,4,5])
print("myvector1:")
print(myvector1)
print()

mydf1 = pd.DataFrame(myvector1)
print("mydf1:")
print(mydf1)
print()

myvector2 = np.array([i for i in range(1,6)])
print("myvector2:")
print(myvector2)
print()

mydf2 = pd.DataFrame(myvector2)
print("mydf2:")
print(mydf2)
print()

myarray = np.array([[10,30,20], [50,40,60],[1000,2000,3000]])
print("myarray:")
print(myarray)
print()

mydf3 = pd.DataFrame(myarray)
print("mydf3:")
print(mydf3)
print()
```

Listing 3.1 从 Pandas 和 NumPy 的标准导入语句开始，接着定义了两个一维 NumPy 数组和一个二维 NumPy 数组。NumPy 的语法对你来说应该熟悉（网上有很多基础教程）。每个 NumPy 变量后面都跟着对应的 Pandas 数据框 `mydf1`、`mydf2` 和 `mydf3`。运行 Listing 3.1 中的代码。你将看到以下输出，并可以将 NumPy 数组与 Pandas 数据框进行对比：

```text
myvector1:
[1 2 3 4 5]

mydf1:
   0
0  1
1  2
2  3
3  4
4  5

myvector2:
[1 2 3 4 5]

mydf2:
   0
0  1
1  2
2  3
3  4
4  5

myarray:
[[  10   30   20]
 [  50   40   60]
 [1000 2000 3000]]

mydf3:
      0     1     2
0    10    30    20
1    50    40    60
2  1000  2000  3000
```

相比之下，以下代码块说明了如何定义一个 Pandas Series：

```python
names = pd.Series(['SF', 'San Jose', 'Sacramento'])
sizes = pd.Series([852469, 1015785, 485199])
df = pd.DataFrame({ 'Cities': names, 'Size': sizes })
print(df)
```

使用上述代码（以及所需的导入语句）创建一个 Python 文件。当你运行该代码时，你将看到以下输出：

```text
City name    sizes
0          SF   852469
1    San Jose  1015785
2  Sacramento   485199
```

## 描述 Pandas 数据框

Listing 3.2 显示了 `pandas_df_describe.py` 的内容，说明了如何定义一个包含 3×3 整数 NumPy 数组的 Pandas 数据框，其中数据框的行和列都已标记。还显示了数据框的其他方面。

**代码列表 3.2：`pandas_df_describe.py`**

```python
import numpy as np
import pandas as pd

myarray = np.array([[10,30,20], [50,40,60],[1000,2000,3000]])

rownames = ['apples', 'oranges', 'beer']
colnames = ['January', 'February', 'March']
mydf = pd.DataFrame(myarray, index=rownames, columns=colnames)
print("contents of df:")
print(mydf)

print("contents of January:")
print(mydf['January'])

print("Number of Rows:")
print(mydf.shape[0])

print("Number of Columns:")
print(mydf.shape[1])

print("Number of Rows and Columns:")
print(mydf.shape)

print("Column Names:")
print(mydf.columns)

print("Column types:")
print(mydf.dtypes)

print("Description:")
print(mydf.describe())
```

Listing 3.2 以两个标准导入语句开始，随后是 3x3 的数字数组 `myarray`。`rownames` 和 `colnames` 分别为数据框 `mydf` 的行和列命名，该数据框通过指定的 `myarray` 初始化。输出的第一个部分需要一个 `print()` 语句（只需显示 `mydf` 的内容）。第二部分通过调用任何数据框通用的 `describe()` 方法生成。`describe()` 方法非常有用：你将看到各种列统计信息，如平均值、标准差、最小值和最大值，以及 25、50 和 75 分位数。Listing 3.2 的输出如下：

```text
contents of df:
         January  February  March
apples        10        30      20
oranges       50        40      60
beer        1000      2000    3000

contents of January:
apples       10
oranges      50
beer       1000
Name: January, dtype: int64

Number of Rows:
3

Number of Columns:
3

Number of Rows and Columns:
(3, 3)

Column Names:
Index(['January', 'February', 'March'], dtype='object')

Column types:
January     int64
February    int64
March       int64
dtype: object

Description:
           January  February      March
count       3.000000   3.000000   3.000000
mean      353.333333  690.000000  1026.666667
std       560.386711  1134.504297  1709.073823
min        10.000000   30.000000    20.000000
25%        30.000000   35.000000    40.000000
50%        50.000000   40.000000    60.000000
75%       525.000000  1020.000000  1530.000000
mark      1000.000000  2000.000000  3000.000000
```

## Pandas 布尔运算

Pandas 支持对数据框进行布尔操作，例如逻辑或、逻辑与以及对数据框的逻辑取反。Listing 3.3 显示了 `pandas_boolean_df.py` 的内容，说明了如何定义一个行和列均为布尔值的数据框。

**代码列表 3.3：`pandas_boolean_df.py`**

```python
import pandas as pd

df1 = pd.DataFrame({'a': [1, 0, 1], 'b': [0, 1, 1] }, dtype=bool)
df2 = pd.DataFrame({'a': [0, 1, 1], 'b': [1, 1, 0] }, dtype=bool)

print("df1 & df2:")
print(df1 & df2)

print("df1 | df2:")
print(df1 | df2)

print("df1 ^ df2:")
print(df1 ^ df2)
```

Listing 3.3 初始化了数据框 `df1` 和 `df2`，然后计算 `df1 & df2`、`df1 | df2` 和 `df1 ^ df2`，分别代表 `df1` 和 `df2` 的逻辑与、逻辑或和逻辑取反。运行 Listing 3.3 中代码的输出如下：

```text
df1 & df2:
       a      b
0  False  False
1  False   True
2   True  False

df1 | df2:
      a     b
0  True  True
1  True  True
2  True  True

df1 ^ df2:
       a      b
0   True   True
1   True  False
2  False   True
```

## 转置 Pandas 数据框

`T` 属性（以及 `transpose` 函数）允许你生成 Pandas 数据框的转置，类似于 NumPy 的 `ndarray`。

例如，以下代码片段定义了 Pandas 数据框 `df1`，然后显示了 `df1` 的转置：

```python
df1 = pd.DataFrame({'a': [1, 0, 1], 'b': [0, 1, 1] }, dtype=int)

print("df1.T:")
print(df1.T)
```

输出如下：

```text
df1.T:
   0  1  2
a  1  0  1
b  0  1  1
```

以下代码片段定义了 Pandas 数据帧 `df1` 和 `df2`，然后显示了它们的和：



```python
df1 = pd.DataFrame({'a' : [1, 0, 1], 'b' : [0, 1, 1] }, dtype=int)
df2 = pd.DataFrame({'a' : [3, 3, 3], 'b' : [5, 5, 5] }, dtype=int)

print("df1 + df2:")
print(df1 + df2)
```

输出如下：

```text
df1 + df2:
   a  b
0  4  5
1  3  6
2  4  6
```

## Pandas 数据帧与随机数

Listing 3.4 显示了 `pandas_random_df.py` 的内容，该示例展示了如何创建一个包含随机数的 Pandas 数据帧。

**列表 3.4：`pandas_random_df.py`**

```python
import pandas as pd
import numpy as np

df = pd.DataFrame(np.random.randint(1, 5, size=(5, 2)), columns=['a','b'])
df = df.append(df.agg(['sum', 'mean']))

print("Contents of data frame:")
print(df)
```

Listing 3.4 定义了 Pandas 数据帧 `df`，它包含 5 行 2 列，其中包含 1 到 5 之间的随机整数。注意 `df` 的列标记为“a”和“b”。此外，接下来的代码片段添加了两行，分别由两列数字的和和平均值组成。Listing 3.4 的输出如下：

```text
a    b
0      1.0  2.0
1      1.0  1.0
2      4.0  3.0
3      3.0  1.0
4      1.0  2.0
sum   10.0  9.0
mean   2.0  1.8
```

Listing 3.5 显示了 `pandas_combine_df.py` 的内容，该示例展示了如何基于两个 NumPy 数字数组定义一个 Pandas 数据帧。

**列表 3.5：`pandas_combine_df.py`**

```python
import pandas as pd
import numpy as np

df = pd.DataFrame({'foo1' : np.random.randn(5),
                  'foo2' : np.random.randn(5)})

print("contents of df:")
print(df)

print("contents of foo1:")
print(df.foo1)

print("contents of foo2:")
print(df.foo2)
```

Listing 3.5 定义了 Pandas 数据帧 `df`，它包含 5 行 2 列（标记为 `foo1` 和 `foo2`），包含 0 到 5 之间的随机实数。Listing 3.5 的后续部分显示了 `df` 和 `foo1` 的内容。Listing 3.5 的输出如下：

```text
contents of df:
       foo1      foo2
0  0.274680 _0.848669
1 _0.399771 _0.814679
2  0.454443 _0.363392
3  0.473753  0.550849
4 _0.211783 _0.015014
contents of foo1:
0    0.256773
1    1.204322
2    1.040515
3   _0.518414
4    0.634141
Name: foo1, dtype: float64
contents of foo2:
0   _2.506550
1   _0.896516
2   _0.222923
3    0.934574
4    0.527033
Name: foo2, dtype: float64
```

## 将分类数据转换为数值数据

机器学习中的一项常见任务是将包含字符数据的特征转换为包含数值数据的特征。

Listing 3.6 显示了 `sometext.tsv` 的内容，其中包含已标记的数据（垃圾邮件或正常邮件），这些数据用在 Listing 3.7 中显示的代码示例。

**列表 3.6：`sometext.tsv`**

```text
type    text
ham     I'm telling the truth
spam    What a deal such a deal!
spam    Free vacation for your family
ham     Thank you for your help
spam    Spring break next week!
ham     I received the documents
spam    One million dollars for you
ham     My wife got covid19
spam    You might have won the prize
ham     Everyone is in good health
```

Listing 3.7 显示了 `cat2numeric.py` 的内容，该示例展示了如何将文本字段转换为相应的数值字段。

**列表 3.7：`cat2numeric.py`**

```python
import pandas as pd
import numpy as np

df = pd.read_csv('sometext.tsv', delimiter='\t')

print("=> First rows (before):")
print(df.head())

# map ham/spam to 0/1:
df['type'] = df['type'].map({'ham':0, 'spam':1})

print("=> First rows (after):")
print(df.head())
```

Listing 3.7 使用 `sometext.tsv` 文件的内容初始化数据帧 `df`，然后通过调用 `head(5)` 显示前五行。Listing 3.7 中的代码片段调用 `map()` 方法将 `type` 列中的 `ham` 替换为 0，将 `spam` 替换为 1，如下所示：

```python
df['type'] = df['type'].map({'ham':0, 'spam':1})
```

Listing 3.7 再次调用 `head()` 方法来显示重命名列内容的数据集的前五行。运行 Listing 3.7 中的代码，你将看到以下输出：

```text
=> First rows (before):
   type                           text
0   ham          I'm telling the truth
1  spam      What a deal such a deal!
2  spam  Free vacation for your family
3   ham        Thank you for your help
4  spam        Spring break next week!
=> First rows (after):
   type                           text
0     0          I'm telling the truth
1     1      What a deal such a deal!
2     1  Free vacation for your family
3     0        Thank you for your help
4     1  Spring break next week!
```

另一个示例，Listing 3.8 显示了 `shirts.csv` 的内容，Listing 3.9 显示了 `shirts.py` 的内容，展示了将分类数据转换为数值数据的四种技术。

**列表 3.8：`shirts.csv`**

```csv
type,ssize
shirt,xxlarge
shirt,xxlarge
shirt,xlarge
shirt,xlarge
shirt,large
shirt,medium
shirt,small
shirt,small
shirt,xsmall
shirt,xsmall
```

**列表 3.9：`shirts.py`**

```python
import pandas as pd

shirts = pd.read_csv("shirts.csv")
print("shirts before:")
print(shirts)
print()

# TECHNIQUE #1:
#shirts.loc[shirts['ssize']=='xxlarge','size'] = 4
#shirts.loc[shirts['ssize']=='xlarge', 'size'] = 4
#shirts.loc[shirts['ssize']=='large',  'size'] = 3
#shirts.loc[shirts['ssize']=='medium', 'size'] = 2
#shirts.loc[shirts['ssize']=='small',  'size'] = 1
#shirts.loc[shirts['ssize']=='xsmall', 'size'] = 1

# TECHNIQUE #2:
#shirts['ssize'].replace('xxlarge', 4, inplace=True)
#shirts['ssize'].replace('xlarge',  4, inplace=True)
#shirts['ssize'].replace('large',   3, inplace=True)
#shirts['ssize'].replace('medium',  2, inplace=True)
#shirts['ssize'].replace('small',   1, inplace=True)
#shirts['ssize'].replace('xsmall',  1, inplace=True)

# TECHNIQUE #3:
#shirts['ssize'] = shirts['ssize'].apply({'xxlarge':4, 'xlarge':4, 'large':3, 'medium':2, 'small':1, 'xsmall':1}.get)

# TECHNIQUE #4:
shirts['ssize'] = shirts['ssize'].replace(regex='xlarge', value=4)
shirts['ssize'] = shirts['ssize'].replace(regex='large',  value=3)
shirts['ssize'] = shirts['ssize'].replace(regex='medium', value=2)
shirts['ssize'] = shirts['ssize'].replace(regex='small',  value=1)

print("shirts after:")
print(shirts)
```

Listing 3.9 以一个包含六条语句的代码块开始，使用与字符串的直接比较来进行数值替换。例如，以下代码片段将字符串 `xxlarge` 的所有出现处替换为值 4：

```python
shirts.loc[shirts['ssize']=='xxlarge','size'] = 4
```

第二个代码块由六条语句组成，使用 `replace()` 方法执行相同的更新，示例如下：

```python
shirts['ssize'].replace('xxlarge', 4, inplace=True)
```

第三个代码块由单个语句组成，使用 `apply()` 方法执行相同的更新，如下所示：

```python
shirts['ssize'] = shirts['ssize'].apply({'xxlarge':4, 'xlarge':4, 'large':3, 'medium':2, 'small':1, 'xsmall':1}.get)
```

第四个代码块由四条语句组成，使用正则表达式执行相同的更新，示例如下：

```python
shirts['ssize'] = shirts['ssize'].replace(regex='xlarge', value=4)
```

由于之前的代码段同时匹配 `xxlarge` 和 `xlarge`，因此我们只需要四条语句而不是六条语句。如果您不熟悉正则表达式，可以阅读有关此主题的在线教程。运行列表 3.9 中的代码，您将看到以下输出：

```text
shirts before
     type     size
0   shirt  xxlarge
1   shirt  xxlarge
2   shirt   xlarge
3   shirt   xlarge
4   shirt   xlarge
5   shirt    large
6   shirt   medium
7   shirt    small
8   shirt    small
9   shirt   xsmall
10  shirt   xsmall
11  shirt   xsmall

shirts after:
     type  size
0   shirt     4
1   shirt     4
2   shirt     4
3   shirt     4
4   shirt     4
5   shirt     3
6   shirt     2
7   shirt     1
8   shirt     1
9   shirt     1
10  shirt     1
11  shirt     1
```

### 在 Pandas 中合并与拆分列

列表 3.10 显示了 `employees.csv` 的内容，列表 3.11 显示了 `emp_merge_split.py` 的内容，它展示了如何合并和拆分 CSV 文件的列。

**列表 3.10：`employees.csv`**

```csv
name,year,month
Jane-Smith,2015,Aug
Dave-Smith,2020,Jan
Jane-Jones,2018,Dec
Jane-Stone,2017,Feb
Dave-Stone,2014,Apr
Mark-Aster,,Oct
Jane-Jones,NaN,Jun
```

**列表 3.11：`emp_merge_split.py`**

```python
import pandas as pd

emps = pd.read_csv("employees.csv")
print("emps:")
print(emps)
print()

emps['year']  = emps['year'].astype(str)
emps['month'] = emps['month'].astype(str)
# separate column for first name and for last name:
emps['fname'],emps['lname'] = emps['name'].str.split("-",1).str

# concatenate year and month with a "#" symbol:
emps['hdate1'] = emps['year'].astype(str)+"#"+emps['month'].astype(str)

# concatenate year and month with a "-" symbol:
emps['hdate2'] = emps[['year','month']].agg('-'.join, axis=1)

print(emps)
print()
```

列表 3.11 使用 CSV 文件 `employees.csv` 的内容初始化帧 `df`，然后显示数据帧的内容。接下来的一对代码段调用 `astype()` 方法，将 `year` 和 `month` 列的内容转换为字符串。

列表 3.11 中的下一段代码使用 `split()` 方法，将 `name` 列拆分为 `fname` 和 `lname` 列，这两列分别包含每位员工名字的姓和名：

```python
emps['fname'],emps['lname'] = emps['name'].str.split("-",1).str
```

接下来的代码段将 `year` 和 `month` 字符串的内容用“#”字符连接，创建一个名为 `hdate1` 的新列，如下所示：

```python
emps['hdate1'] = emps['year'].astype(str)+"#"+emps['month'].astype(str)
```

最后一段代码将 `year` 和 `month` 字符串的内容用“-”连接，创建一个名为 `hdate2` 的新列，如下所示：

```python
emps['hdate2'] = emps[['year','month']].agg('-'.join, axis=1)
```

运行列表 3.11 中的代码，您将看到以下输出：



```
 emps:
         name    year  month
0  Jane-Smith  2015.0   Aug
1  Dave-Smith  2020.0   Jan
2  Jane-Jones  2018.0   Dec
3  Jane-Stone  2017.0   Feb
4  Dave-Stone  2014.0   Apr
5  Mark-Aster     NaN   Oct
6  Jane-Jones     NaN   Jun

         name    year month fname  lname      hdate1      hdate2
0  Jane-Smith  2015.0   Aug  Jane  Smith  2015.0#Aug  2015.0-Aug
1  Dave-Smith  2020.0   Jan  Dave  Smith  2020.0#Jan  2020.0-Jan
2  Jane-Jones  2018.0   Dec  Jane  Jones  2018.0#Dec  2018.0-Dec
3  Jane-Stone  2017.0   Feb  Jane  Stone  2017.0#Feb  2017.0-Feb
4  Dave-Stone  2014.0   Apr  Dave  Stone  2014.0#Apr  2014.0-Apr
5  Mark-Aster     NaN   Oct  Mark  Aster  nan#Oct
6  Jane-Jones     NaN   Jun  Jane  Jones     nan#Jun
```

关于接下来的代码段还有一个细节：

```
emps['fname'],emps['lname'] = emps['name'].str.split("-",1).str
```

显示如下弃用消息：

```
FutureWarning: Column iteration over characters
will be deprecated in future releases.
```

### 合并数据帧

Pandas 支持 `concat()` 方法来合并数据帧。列表 3.12 显示 `concat_frames.py` 的内容，展示了如何合并两个数据帧。

**列表 3.12: `concat_frames.py`**

```
 import pandas as pd

can_weather = pd.DataFrame({
    "city": ["Vancouver","Montreal"],
    "temperature": [72,65],
    "humidity": [40,25]
})

us_weather = pd.DataFrame({
    "city": ["SF","LA"],
    "temperature": [60,40],
    "humidity": [30,15]
})

df = pd.concat([can_weather, us_weather])
print(df)
```

列表 3.12 中的第一行是 `import` 语句，随后是包含加拿大和美国天气信息的数据帧 `can_weather` 和 `us_weather`。数据帧 `df` 是 `can_weather` 和 `us_weather` 的合并。列表 3.12 的输出为：

```
 0  Vancouver  72  40
1    Montreal  65  25
2          SF  60  30
3          LA  40  15
```

### 使用数据帧进行处理

作为一个简单的示例，假设我们有一家按季度记录收支的公司。我们要计算每个季度的盈亏以及总盈亏。列表 3.13 显示 `pandas_quarterly_df1.py` 的内容，展示了如何定义一个包含收入相关值的 Pandas 帧。

**列表 3.13: `pandas_quarterly_df1.py`**

```
 import pandas as pd

summary = {
    'Quarter': ['Q1', 'Q2', 'Q3', 'Q4'],
    'Cost': [23500, 34000, 57000, 32000],
    'Revenue': [40000, 40000, 40000, 40000]
}

df = pd.DataFrame(summary)

print("Entire Dataset:\n",df)
print("Quarter:\n",df.Quarter)
print("Cost:\n",df.Cost)
print("Revenue:\n",df.Revenue)
```

列表 3.13 定义了变量 `summary`，其中包含了我们公司的硬编码季度成本收入信息。通常，这些硬编码值将由来自另一个来源（例如 CSV 文件）的数据替换，因此将此代码示例视为说明 Pandas 帧可用的一些简单方法。

变量 `df` 是基于 `summary` 变量数据的 Pandas 帧。三个 `print()` 语句显示了季度、每季度的成本和每季度的收入。列表 3.13 的输出为：

```
 Entire Dataset:
     Cost Quarter  Revenue
0  23500      Q1    40000
1  34000      Q2    40000
2  57000      Q3    40000
3  32000      Q4    40000
Quarter:
 0    Q1
1    Q2
2    Q3
3    Q4
Name: Quarter, dtype: object
Cost:
 0    23500
1    34000
2    57000
3    32000
Name: Cost, dtype: int64
Revenue:
 0    40000
1    40000
2    40000
3    30000
Name: Revenue, dtype: int64
```

## Pandas 数据帧与 CSV 文件

之前几个章节中的代码示例在 Python 脚本中包含了硬编码数据。然而，从 CSV 文件读取数据也是常见的。你可以使用 Python 的 `csv.reader()` 函数、NumPy 的 `loadtxt()` 函数或 Pandas 的 `read_csv()` 函数（在本节所示）来读取 CSV 文件的内容。

列表 3.14 显示了 CSV 文件 `weather_data.csv` 的内容，列表 3.15 显示了 `weather_data.py` 的内容，展示了如何读取文件 `weather_data.csv`。

**列表 3.14: `weather_data.py`**

```
 day,temperature,windspeed,event
7/1/2018,42,16,Rain
7/2/2018,45,3,Sunny
7/3/2018,78,12,Snow
7/4/2018,74,9,Snow
7/5/2018,42,24,Rain
7/6/2018,51,32,Sunny
```

**列表 3.15: `weather_data.py`**

（注：此处根据原文逻辑，列表 3.14 与 3.15 的内容在示例描述中已对应，此处已按要求翻译标题与结构）

```python
 import pandas as pd

df = pd.read_csv("weather_data.csv")

print(df)
print(df.shape)  # rows, columns
print(df.head()) # df.head(3)
print(df.tail())
print(df[1:3])
print(df.columns)
print(type(df['day']))
print(df[['day','temperature']])
print(df['temperature'].max())
```

列表 3.15 调用了 Pandas 的 `read_csv()` 函数来读取 CSV 文件 `weather_data.csv` 的内容，随后是一系列 Python `print()` 语句，用于显示 CSV 文件的不同部分。列表 3.15 的输出如下：

```
 day  temperature  windspeed     event
0  7/1/2018           42         16   Rain
1  7/2/2018           45          3  Sunny
2  7/3/2018           78         12   Snow
3  7/4/2018           74          9   Snow
4  7/5/2018           42         24   Rain
5  7/6/2018           51         32    Sunny
(6, 4)
        day  temperature  windspeed     event
0  7/1/2018           42         16   Rain
1  7/2/2018           45          3  Sunny
2  7/3/2018           78         12   Snow
3  7/4/2018           74          9   Snow
4  7/5/2018           42         24   Rain
        day  temperature  windspeed     event
1  7/2/2018           45          3  Sunny
2  7/3/2018           78         12   Snow
3  7/4/2018           74          9   Snow
4  7/5/2018           42         24   Rain
5  7/6/2018           51         32    Sunny
        day  temperature  windspeed     event
1  7/2/2018           45          3  Sunny
2  7/3/2018           78         12   Snow
3  7/4/2018           74          9   Snow
4  7/5/2018           42         24   Rain
5  7/6/2018           51         32    Sunny
Index(['day', 'temperature', 'windspeed', 'event'], dtype='object')
<class 'pandas.core.series.Series'>
        day  temperature
0  7/1/2018           42
1  7/2/2018           45
2  7/3/2018           78
3  7/4/2018           74
4  7/5/2018           42
5  7/6/2018           51
78
```

在某些情况下，你可能需要应用布尔条件逻辑，根据应用于列值的条件条件来“过滤掉”某些数据行。

列表 3.16 显示了 CSV 文件 `people.csv` 的内容，列表 3.17 显示了 `people_pandas.py` 的内容，该文件演示了如何定义一个读取 CSV 文件并处理数据的 Pandas 数据框。

**列表 3.16: `people.csv`**

```
 fname,lname,age,gender,country
john,smith,30,m,usa
jane,smith,31,f,france
jack,jones,32,m,france
dave,stone,33,m,italy
sara,stein,34,f,germany
eddy,bower,35,m,spain
```

**列表 3.17: `people_pandas.py`**

```python
 import pandas as pd

df = pd.read_csv('people.csv')
df.info()
print('fname:')
print(df['fname'])
print('____________')
print('age over 33:')
print(df['age'] > 33)
print('____________')
print('age over 33:')
myfilter = df['age'] >  33
print(df[myfilter])
```

列表 3.17 用 CSV 文件 `people.csv` 的内容填充了 Pandas 数据框 `df`。列表 3.17 的后续部分显示了 `df` 的结构，然后是所有人的名字。列表 3.17 的下一部分部分显示了一个包含六行的表格列表，根据人员是否超过 33 岁或最多为 33 岁，分别包含 `True` 或 `False`。列表 3.17 的最后部分显示了一个包含两行的表格列表，包含了所有超过 33 岁的人的详细信息。列表 3.17 的输出如下：

```
 myfilter = df['age'] >  33
<class 'pandas.core.frame.Data frame'>
RangeIndex: 6 entries, 0 to 5
Data columns (total 5):
fname      6 nonnull object
lname      6 nonnull object
age        6 nonnull int64
gender     6 nonnull object
country    6 nonnull object
dtypes: int64(1), object(4)
memory usage: 320.0+ bytes
fname:
0    john
1    jane
2    jack
3    dave
4    sara
5    eddy
Name: fname, dtype: object
age over 33:
0    False
1    False
2    False
3    True
4    True
5    True
Name: age, dtype: bool
____________
age over 33:
  fname  lname  age gender country
4  sara  stein  34      f      germany
5  eddy  bower  35      m      spain
```

接下来，初始化 Pandas 数据框 `df2`，使用 `df1` 中 `age` 属性至少为 45 的行子集。在此代码段中，当你指定包含嵌入空格的属性时，需要使用反引号。运行 Listing 3.20 中的代码，你将看到以下输出：

```
 df2 ages at least 45:
  fname  lname  age
0  Jane  Jones   65
1  Jane  Jones   65
2  Dave  Stone   45
3  Mark  Aster   53
4  Jane  Jones   58
```

Listing 3.21 显示了 `pandas_schema2.py` 的内容，说明了如何根据某些条件逻辑从 CSV 文件中读取子集。

**列表 3.21: `pandas_schema2.py`**

```
 import pandas as pd

csv_file="emp_ages.csv"

schema = { "age": int, "fname":str}

df1 = pd.read_csv(csv_file, dtype=schema, chunksize=10000000)
df2 = pd.concat((item.query("age >= 45 | age < 20") for item in df1), ignore_index=True)

print("df2 ages at least 45 or less than 20:")
print(df2)
```

Listing 3.21 通过为 Pandas 数据框 `df2` 中的行指定指定复合条件，扩展了 Listing 3.20 中的代码，该条件涉及 `df1` 中 `age` 属性至少为 45 的行*或* `df1` 中 `age` 属性*小于* 20 的行。运行 Listing 3.21 中的代码，你将看到以下输出：

```
 df2 ages at least 45 or less than 20:
  fname  lname  age
0  Dave  Smith   10
1  Jane  Jones   65
2  Jane  Jones   65
3  Dave  Stone   45
4  Mark  Aster   53
5  Jane  Jones   58
```

### PANDAS 数据框与 EXCEL 表格

Listing 3.22 显示了 `write_people_xlsx.py` 的内容，说明了如何从 CSV 文件中读取数据，然后用这些数据创建 Excel 表格。

**列表 3.22: `write_people_xlsx.py`**

```
 import pandas as pd

df1 = pd.read_csv("people.csv")
df1.to_excel("people.xlsx")

#可选地指定工作表名称:
#df1.to_excel("people.xlsx", sheet_name='Sheet_name_1')
```



Listing 3.22 使用 CSV 文件`people.csv`的内容初始化 Pandas 数据框`df1`，然后调用`to_excel()`方法将数据框的内容保存到 Excel 表格`people.xlsx`中。Listing 3.23 显示了`read_people_xlsx.py`的内容，说明了如何从 Excel 表格`people.xlsx`中读取数据并用该数据创建 Pandas 数据框。

**列表 23：`read_people_xlsx.py`**

```python
import pandas as pd

df = pd.read_excel("people.xlsx")
print("Contents of Excel spreadsheet:")
print(df)
```

Listing 3.23 操作非常直观：通过 Pandas 函数`read_excel()`使用表格`people.xlsx`的内容（其内容与`people.csv`相同）初始化 Pandas 数据框`df`。Listing 3.23 的输出如下：

```text
df1:
  Unnamed: 0 fname  lname  age gender  country
0           john  smith   30      usa
1           jane  smith   31      france
2           jack  jones   32      france
3           dave  stone   33      italy
4           sara  stein   34      germany
5           eddy  bower   35      spain
```

#### 读取表格的实用选项

有时，你需要对从 Excel 表格读取到 Pandas 数据框的值进行额外控制，就像处理 CSV 文件一样。使用此代码段跳过 Excel 表格的头部和页脚：

```python
df = pd.read_excel("myfile.xls", header=1, footer="")
```

### 在数据框中选择、添加和删除列

本节包含短代码块，说明了如何对数据框进行类似于对字典的操作。例如，获取、设置和删除列的实现与类似的 Python 字典操作具有相同的语法，如下所示：

```python
df = pd.DataFrame.from_dict(
    dict([('A', [1, 2, 3]), ('B', [4, 5, 6])]),
    orient='index',
    columns=['one', 'two']
)
```

在数据框中添加新列：

```python
df['C'] = [7, 8, 9]
```

删除列：

```python
del df['A']
```

设置列的值：

```python
df['B'] = [10, 20, 30]
```

修改列的值：

```python
df['B'] = [15, 25, 35]
```

获取列的值：

```python
df['B']
```

查看所有列名：

```python
df.columns
```

选择多个列：

```python
df[['one', 'two']]
```

使用`iloc`按位置选择：

```python
df.iloc[:, 0]
```

使用`loc`按标签选择：

```python
df.loc[:, 'one']
```

根据条件过滤行：

```python
df[df['one'] > 1]
```

根据多个条件过滤：

```python
df[(df['one'] > 1) & (df['two'] < 30)]
```

使用`query`方法过滤：

```python
df.query('one > 1 and two < 30')
```

使用`apply`方法操作：

```python
df.apply(lambda x: x * 2)
```

使用`map`映射值：

```python
df['one'].map({1: 'a', 2: 'b', 3: 'c'})
```

使用`replace`替换值：

```python
df['one'].replace({1: 'a', 2: 'b', 3: 'c'})
```

使用`fillna`处理缺失值：

```python
df['one'].fillna(0)
```

使用`dropna`删除缺失值行：

```python
df.dropna(subset=['one'])
```

对数据框排序：

```python
df.sort_values(by='one', ascending=False)
```

查看前几行：

```python
df.head(2)
```

查看最后几行：

```python
df.tail(2)
```

查看数据框概览：

```python
df.info()
```

查看统计描述：

```python
df.describe()
```

重置索引：

```python
df.reset_index(drop=True)
```

重命名列名：

```python
df.rename(columns={'one': 'new_one', 'two': 'new_two'})
```

合并数据框：

```python
pd.concat([df1, df2])
```

连接数据框：

```python
pd.merge(df1, df2, on='key')
```

透视表：

```python
df.pivot_table(values='one', index='two', aggfunc='mean')
```

Listing 3.24 使用内置 Iris 数据集的内容初始化变量`df`。接着，变量`columns`被列名初始化，数据框`iris_df`根据`df.data`的内容进行初始化，该内容包含了 Iris 数据集的实际数据。此外，`iris_df.columns`使用变量`columns`的内容初始化。

Listing 3.24 的后续部分显示数据框`iris_df`的形状（shape），紧接着是`iris_df`数据框的`zscore`，该值通过减去平均值然后除以标准差计算得出（对每行执行）。

Listing 3.24 的最后两个部分显示`zscore`在区间`[0.01, 2.5]`之外的离群值（如果有）。运行 Listing 3.24 中的代码，你将看到以下输出：

```text
=> iris_df.shape: (150, 4)
  sepal length (cm)  sepal width (cm)  petal length (cm)  petal width (cm)
  0          5.1          3.5          1.4          0.2
  1          4.9          3.0          1.4          0.2
  2          4.7          3.2          1.3          0.2
  3          4.6          3.1          1.5          0.2
  4          5.0          3.6          1.4          0.2
z scores for iris:
z.shape: (150, 4)

=> upper outliers:
[3.09077525 2.63038172]
=> lower outliers:
    sepal length (cm)  sepal width (cm)  petal length (cm)  petal width (cm)
   73         6.1          2.8               4.7               1.2
   82         5.8          2.7               3.9               1.2
   90         5.5          2.6               4.4               1.2
   92         5.8          2.6               4.0               1.2
   95         5.7          3.0               4.2               1.2
```

### Pandas 数据框与简单统计数据

Listing 3.25 显示了`housing_stats.py`的内容，说明了如何从 Pandas 数据框中的数据收集基本统计信息。

**Listing 3.25：`housing_stats.py`**

```python
import pandas as pd

df = pd.read_csv("Housing.csv")

minimum_bdrms = df["bedrooms"].min()
median_bdrms = df["bedrooms"].median()
maximum_bdrms = df["bedrooms"].max()

print("minimum # of bedrooms:", minimum_bdrms)
print("median  # of bedrooms:", median_bdrms)
print("maximum # of bedrooms:", maximum_bdrms)
print("")

print("median values:", df.median().values)
print("")

prices = df["price"]
print("first 5 prices:")
print(prices.head())
print("")

median_price = df["price"].median()
print("median price:", median_price)
print("")

corr_matrix = df.corr()
print("correlation matrix:")
print(corr_matrix["price"].sort_values(ascending=False))
```

Listing 3.25 使用 CSV 文件`housing.csv`的内容初始化 Pandas 数据框`df`。接下来的三个变量分别初始化为卧室数量的、中位数和最大，然后显示这些值。

Listing 3.25 的下一部分使用 Pandas 数据框`df`中`prices`列的内容初始化变量`prices`。接着，通过`prices.head()`语句打印前五行，然后是`prices`的中位数值。

Listing 3.25 的最后部分使用 Pandas 数据框`df`的相关矩阵内容初始化变量`corr_matrix`，然后显示其内容。Listing 3.25 的输出在此：

```text
Apples
10
```

### 在 Pandas 中查找重复行

Listing 3.26 显示了`duplicates.csv`的内容，Listing 3.27 显示了`duplicates.py`的内容，说明了如何在 Pandas 数据框中查找重复行。

**Listing 3.26：`duplicates.csv`**

```csv
fname,lname,level,dept,state
Jane,Smith,Senior,Sales,California
Dave,Smith,Senior,Devel,California
Jane,Jones,Year1,Mrktg,Illinois
Jane,Jones,Year1,Mrktg,Illinois
Jane,Stone,Senior,Mrktg,Arizona
Dave,Stone,Year2,Devel,Arizona
Mark,Aster,Year3,Dev,Florida
Jane,Jones,Year1,Mrktg
```

**Listing 3.27：`duplicates.py`**

```python
import pandas as pd

df = pd.read_csv("duplicates.csv")
print("Contents of data frame:")
print(df)
print()

print("Duplicate rows:")
df2 = df.duplicated()
print(df2)
print()

print("Duplicate first names:")
df3 = df.duplicated(subset=['fname'])
print(df3)
print()

print("Duplicate name and level:")
df3 = df.duplicated(subset=['fname', 'level'])
print(df3)
```

Listing 3.27 使用 CSV 文件`duplicates.csv`的内容初始化数据框`df`，然后显示数据框的内容。Listing 3.27 的后续部分通过调用`duplicated()`方法显示重复行，而 Listing 3.27 的后续部分仅显示`fname`。Listing 3.27 的最后部分显示`fname`以及`level`信息。运行 Listing 3.27 中的代码，你将看到以下输出：

```text
Contents of data frame:
  fname  lname   level    dept       state
0  Jane  Smith  Senior   Sales  California
1  Dave  Smith  Senior   Devel  California
2  Jane  Jones  Year1   Mrktg  Illinois
3  Jane  Jones  Year1   Mrktg  Illinois
4  Jane  Stone  Senior   Mrktg  Arizona
5  Dave  Stone  Year2   Devel  Arizona
6  Mark  Aster  Year3    Dev  Florida
7  Jane  Jones  Year1   Mrktg  Illinois

Duplicate rows:
0    False
1    False
2    False
3     True
4    False
5    False
6    False
7     True
dtype: bool

Duplicate first names:
  fname  lname   level   dept       state
2  Jane  Jones  Year1   Mrktg  Illinois
3  Jane  Jones  Year1   Mrktg  Illinois
4  Jane  Stone  Senior   Mrktg  Arizona
5  Dave  Stone  Year2   Devel  Arizona
7  Jane  Jones  Year1   Mrktg  Illinois
dtype: bool

Duplicate name and level:
  fname  lname   level   dept       state
3  Jane  Jones  Year1   Mrktg  Illinois
7  Jane  Jones  Year1   Mrktg  Illinois
dtype: bool
```

Listing 3.28 显示了`drop_duplicates.py`的内容，说明了如何在 Pandas 数据框中删除重复行。

**Listing 3.28：`drop_duplicates.py`**

```python
import pandas as pd

df = pd.read_csv("duplicates.csv")
print("Contents of data frame:")
print(df)
print()

fname_filtered = df.drop_duplicates(['fname'])
print("Duplicate first names:")
print(fname_filtered)
print()

fname_lname_filtered = df.drop_duplicates(['fname', 'lname'])
print("Duplicate first and last names:")
print(fname_lname_filtered)
print()
```



```text
data frame 的内容：
  fname  lname   level    dept       state
0  Jane  Smith  Senior   Sales  California
1  Dave  Smith  Senior   Devel  California
2  Jane  Jones   Year1   Mrktg    Illinois
3  Jane  Jones   Year1   Mrktg    Illinois
4  Jane  Stone  Senior   Mrktg     Arizona
5  Dave  Stone   Year2   Devel     Arizona
6  Mark  Aster   Year3  BizDev     Florida
7  Jane  Jones   Year1   Mrktg    Illinois

删除重复的名：
  fname  lname   level    dept       state
0  Jane  Smith  Senior   Sales  California
1  Dave  Smith  Senior   Devel  California
6  Mark  Aster   Year3  BizDev     Florida

删除重复的姓和姓名：
  fname  lname   level    dept       state
0  Jane  Smith  Senior   Sales  California
1  Dave  Smith  Senior   Devel  California
2  Jane  Jones   Year1   Mrktg    Illinois
4  Jane  Stone  Senior   Mrktg     Arizona
5  Dave  Stone   Year2   Devel     Arizona
6  Mark  Aster   Year3  BizDev     Florida
```

## 在 PANDAS 中查找缺失值

Listing 3.29 显示了 `employees2.csv` 的内容，Listing 3.30 显示了 `missing_values.py` 的内容，后者展示了如何显示 Pandas 数据框中具有缺失值的行。

### 列表 3.29：employees2.csv

```csv
name,year,month
Jane-Smith,2015,Aug
Jane-Smith,2015,Aug
Dave-Smith,2020,
Dave-Stone,,Apr
Jane-Jones,2018,Dec
Jane-Stone,2017,Feb
Jane-Stone,2017,Feb
Mark-Aster,,Oct
Jane-Jones,NaN,Jun
```

### 列表 3.30：missing_values.py

```python
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np

df = pd.read_csv("employees2.csv")

print("=> contents of CSV file:")
print(df)
print()

# NA:  Not Available (Pandas)
# NaN: Not a Number (Pandas)
# NB:  NumPy uses np.nan() to check for NaN values

df = pd.read_csv("employees2.csv")

print("=> contents of CSV file:")
print(df)
print()

print("=> any NULL values per column?")
print(df.isnull().any())
print()

print("=> count of NAN/MISSING values in each column:")
print(df.isnull().sum())
print()

print("=> count of NAN/MISSING values in each column:")
print(pd.isna(df).sum())
print()

print("=> count of NAN/MISSING values in each column (sorted):")
print(df.isnull().sum().sort_values(ascending=False))
print()

nan_null = df.isnull().sum().sum()
miss_values = df.isnull().any().sum()

print("=> count of NaN/MISSING values:", nan_null)
print("=> count of MISSING values:", miss_values)
print("=> count of NaN values:", nan_null - miss_values)
```

Listing 3.30 使用 CSV 文件 `employees2.csv` 的内容初始化数据框 `df`，然后显示数据框的内容。Listing 3.30 的后续部分显示了任何行或列中出现的空值数量。Listing 3.30 的后续部分显示了具有空值的字段以及字段名称。

Listing 3.30 的后续部分显示了重复行的数量，随后是重复的行号。运行 Listing 3.30 中的代码，你将看到以下输出：

```text
=> contents of CSV file:
         name    year month
0  Jane-Smith  2015.0   Aug
1  Jane-Smith  2015.0   Aug
2  Dave-Smith  2020.0   NaN
3  Dave-Stone     NaN   Apr
4  Jane-Jones  2018.0   Dec
5  Jane-Stone  2017.0   Feb
6  Jane-Stone  2017.0   Feb
7  Mark-Aster     NaN   Oct
8  Jane-Jones     NaN   Jun

=> any NULL values per column?
name     False
year      True
month     True
dtype: bool

=> count of NAN/MISSING values in each column:
name     0
year     3
month    1
dtype: int64

=> count of NAN/MISSING values in each column:
name     0
year     3
month    1
dtype: int64

=> count of NAN/MISSING values in each column (sorted):
year     3
month    1
name     0
dtype: int64

=> count of NaN/MISSING values: 4
=> count of MISSING values: 2
=> count of NaN values: 2
```

## IRIS 数据集中的缺失值

本节展示了如何替换 `nan_iris.csv` 数据集中的缺失值，如下：

- 复制 Iris 数据集的表头和前 50 行
- 随机选择的行和列

为了方便起见，`iris.csv` 数据集和 `nan_iris.csv` 数据集包含在书中（见前言）。Listing 3.32 显示了 `nan_iris.csv` 的初始部分，而 Listing 3.33 显示了 `missingdata.py` 的内容，展示了如何将 NaN 值替换为有意义的值。

### 列表 3.32：nan_iris.csv

```csv
SepalLength,SepalWidth,PetalLength,PetalWidth,Name
5.1,3.5,1.4,0.2,setosa
4.9,3.0,1.4,0.2,setosa
4.7,3.2,1.3,0.2,setosa
4.6,3.1,1.5,0.2,setosa
5.0,3.6,1.4,0.2,setosa
7.0,3.2,4.7,1.4,setosa
6.4,3.2,4.5,1.5,setosa
6.9,3.1,4.9,1.5,setosa
5.5,2.3,4.0,1.3,setosa
5.0,2.0,3.6,1.0,setosa
5.9,3.2,5.1,1.5,setosa
5.6,2.5,4.5,1.5,setosa
7.7,3.0,4.7,1.4,versicolor
6.4,3.2,4.6,1.5,versicolor
6.9,2.5,4.6,1.5,versicolor
5.5,2.4,3.7,1.3,versicolor
6.5,2.8,4.6,1.5,versicolor
5.2,2.7,3.9,1.4,versicolor
5.0,2.0,4.0,1.2,versicolor
5.9,3.2,5.1,1.5,versicolor
6.0,2.7,5.1,1.6,versicolor
5.1,2.8,4.7,1.3,versicolor
6.8,2.7,4.8,1.9,versicolor
7.1,3.0,5.9,2.1,virginica
6.3,2.9,5.6,1.8,virginica
6.5,3.0,5.2,2.0,virginica
7.6,3.0,6.6,2.5,virginica
4.9,2.3,4.0,1.5,virginica
7.3,2.0,6.3,2.5,virginica
6.7,2.5,5.8,1.8,virginica
7.2,3.0,4.9,1.6,virginica
7.7,2.8,6.7,2.0,virginica
6.3,2.4,5.1,1.5,virginica
6.4,2.7,1.5,1.4,virginica
6.4,2.1,1.5,1.5,virginica
6.1,2.3,4.7,1.5,virginica
6.0,1.8,5.0,1.5,virginica
5.6,2.9,4.6,2.1,virginica
5.8,2.7,5.1,1.9,virginica
7.1,3.0,5.9,2.1,virginica
6.3,2.3,4.4,1.3,virginica
5.6,2.7,4.5,1.3,virginica
5.5,2.3,4.0,1.3,virginica
5.5,2.4,3.4,1.4,virginica
5.5,2.4,3.6,1.5,virginica
6.5,2.8,5.0,1.9,virginica
```

### 列表 3.33：missingdatairis.py

```python
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np

# Step 1: 加载数据集
data = pd.read_csv('nan_iris.csv')

# Step 2: 显示关于数据集信息
print("=> Details of dataset:")
print(data.info())

# Step 3: 检查缺失值
print("=> Missing values per column:")
print(data.isnull().sum())

# Step 4: 显示前 10 行
print("=> First range from 10:")
print(data.head(10))

# Step 5: 计算数值列的平均值
print("=> List of Mean Values:")
print(data.mean(numeric_only=True))

# Step 6: 用平均值填充缺失数值值
data.fillna(data.mean(numeric_only=True), inplace=True)

# Step 7: 显示后续行
print("=> Second range from 10:")
print(data.iloc[10:20])

# Step 8: 填充缺失的分类值
data['Name'] = data['Name'].fillna('UNKNOWN')

# Step 9: 显示最后行
print("=> Third range from 10:")
print(data.iloc[20:])
```

```text
=> 数据集列详情：
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 50 entries, 0 to 49
Data columns (total 5 columns):
 #   Column       Non-Null Count  Dtype
---  ------       --------------  -----
 0   SepalLength  39 non-null     float64
 1   SepalWidth   49 non-null     float64
 2   PetalLength  46 non-null     float64
 3   PetalWidth   48 non-null     float64
 4   Name         46 non-null     object
dtypes: float64(4), object(1)
memory usage: 2.1+ KB
None

=> 每列缺失值：
SepalLength    11
SepalWidth      1
PetalLength     4
PetalWidth     2
Name            4
dtype: int64

=> 从 40 到 45 的第一个范围：
    SepalLength  SepalWidth  PetalLength  PetalWidth         Name
40          NaN         3.5          1.3         0.3  Iris-setosa
41          4.5         2.3          1.3         0.3  Iris-setosa
42          4.4         NaN          NaN         NaN          NaN
43          5.0         3.5          NaN         NaN  Iris-setosa
44          5.1         3.8          1.9         0.4  Iris-setosa

=> 平均值列表：
SepalLength    5.002564
SepalWidth     3.422449
PetalLength    1.467391
PetalWidth     0.237500
dtype: float64

=> 从 40 到 45 的第二个范围：
    SepalLength  SepalWidth  PetalLength  PetalWidth         Name
40     5.002564    3.500000     1.300000      0.3000  Iris-setosa
41     4.500000    2.300000     1.300000      0.3000  Iris-setosa
42     4.400000    3.422449     1.467391      0.2375          NaN
43     5.000000    3.500000     1.467391      0.2375  Iris-setosa
44     5.100000    3.800000     1.900000      0.4000  Iris-setosa

=> 从 40 到 45 的第三个范围：
    SepalLength  SepalWidth  PetalLength  PetalWidth         Name
40     5.002564    3.500000     1.300000      0.3000  Iris-setosa
41     4.500000    2.300000     1.300000      0.3000  Iris-setosa
42     4.400000    3.422449    1.467391      0.2375      UNKNOWN
43     5.000000    3.500000    1.467391      0.2375  Iris-setosa
44     5.100000    3.800000    1.900000      0.4000  Iris-setosa
```

## 在 Pandas 中对 DataFrame 排序

列表 3.34 显示了 `sort_df.py` 的内容，它说明了如何对 Pandas DataFrame 的行进行排序。

### 列表 3.34：sort_df.py

```python
import pandas as pd

df = pd.read_csv("duplicates.csv")

print("Contents of data frame:")
print(df)
print()

df.sort_values(by=['fname'], inplace=True)

print("Sorted (ascending) by first name:")
print(df)
print()

df.sort_values(by=['fname'], inplace=True, ascending=False)

print("Sorted (descending) by first name:")
print(df)

print()
```



```python
df.sort_values(by=['fname','lname'], inplace=True)

print("Sorted (ascending) by first name and last name:")

print(df)

print()
```

列表 3.34 使用 CSV 文件 `duplicates.csv` 的内容初始化 DataFrame `df`，然后显示该 DataFrame 的内容。列表 3.34 的后续部分显示了根据名字升序排列的行，下一个代码块显示了根据名字降序排列的行。列表 3.34 的最后一个代码块显示了根据名字和姓氏升序排列的行。运行列表 3.34 中的代码：

### 列表 3.34：DataFrame 数据

```text
Contents of data frame:

    SepalLength  SepalWidth  PetalLength  PetalWidth         Name
40          NaN         3.5          1.3         0.3  Iris-setosa
41          4.5         2.3          1.3         0.3  Iris-setosa
42          4.4         NaN          NaN         NaN          NaN
43          5.0         3.5          NaN         NaN  Iris-setosa
44          5.1         3.8          1.9         0.4  Iris-setosa
```

#### 按名字升序排列

```text
    SepalLength  SepalWidth  PetalLength  PetalWidth         Name
40          NaN         3.5          1.3         0.3  Iris-setosa
41          4.5         2.3          1.3         0.3  Iris-setosa
42          4.4         NaN          NaN         NaN          NaN
43          5.0         3.5          NaN         NaN  Iris-setosa
44          5.1         3.8          1.9         0.4  Iris-setosa
```

#### 按名字降序排列

```text
    SepalLength  SepalWidth  PetalLength  PetalWidth         Name
44          5.1         3.8          1.9         0.4  Iris-setosa
43          5.0         3.5          NaN         NaN  Iris-setosa
42          4.4         NaN          NaN         NaN          NaN
41          4.5         2.3          1.3         0.3  Iris-setosa
40          NaN         3.5          1.3         0.3  Iris-setosa
```

#### 按名字和姓氏升序排列

```text
    SepalLength  SepalWidth  PetalLength  PetalWidth         Name
40          NaN         3.5          1.3         0.3  Iris-setosa
41          4.5         2.3          1.3         0.3  Iris-setosa
42          4.4         NaN          NaN         NaN          NaN
43          5.0         3.5          NaN         NaN  Iris-setosa
44          5.1         3.8          1.9         0.4  Iris-setosa
```

### 在 Pandas 中使用 `GROUPBY`

列表 3.35 显示了 `groupby1.py` 的内容，它说明了如何调用 `groupby()` 方法计算特征的总和。

#### 列表 3.35：`groupby1.py`

```python
import pandas as pd

# colors and weights:
data = {'color':['red','blue','red','blue'],
        'weight':[40,50,20,90]}
df1 = pd.DataFrame(data)
print("df1:")
print(df1)
print()
print(df1.groupby('color').mean())
print()

red_filter = df1['color']=='red'
print(df1[red_filter])
print()
blue_filter = df1['color']=='blue'
print(df1[blue_filter])
print()

red_avg = df1[red_filter]['weight'].mean()
blue_avg = df1[blue_filter]['weight'].mean()
print("red_avg,blue_avg:")
print(red_avg,blue_avg)
print()

df2 = pd.DataFrame({'color':['blue','red'],'weight':[red_avg,blue_avg]})
print("df2:")
print(df2)
print()
```

列表 3.35 定义了包含颜色和权值的变量 `data`，然后使用 `data` 初始化 DataFrame `df1`。接两个代码块定义了 `red_filter` 和 `blue_filter` 来匹配颜色分别为红色和蓝色的行，然后打印了这些行。列表 3.35 的后续部分定义了两个过滤器 `red_avg` 和 `blue_avg`，分别计算红色值和蓝色权值的平均值。列表 3.35 的最后一个代码块定义了带有颜色列和权重列的 DataFrame `df2`，后者包含了红色值和蓝色权值的平均值。运行列表 3.35 中的代码，你将看到以下输出：

```text
df1:
  color  weight
0   red      40
1  blue      50
2   red      20
3  blue      90

          weight
color
blue   53.333333
red    35.000000

  color  weight
0   red      40
3   red      30

  color  weight
1  blue      50
2  blue      20
4  blue      90

red_avg,blue_avg:
35.0 53.333333333333336

df2:
  color     weight
0  blue  35.000000
1   red  53.333333333333336
```

### 使用 `TITANIC.CSV` 数据集进行聚合操作

```python
import pandas as pd

#Loading titanic.csv in Seaborn:
#df = sns.load_dataset('titanic')
df = pd.read_csv("titanic.csv")

# convert floating point values to integers:
df['survived'] = df['survived'].astype(int)

# specify column and aggregate functions:
aggregates1 = {'embark_town': ['count', 'nunique', 'size']}

# group by 'deck' value and apply aggregate functions:
result = df.groupby(['deck']).agg(aggregates1)
print("=> Grouped by deck:")
print(result)
print()

# some details regarding count() and nunique():
# count() excludes NaN values whereas size() includes them
# nunique() excludes NaN values in the unique counts

# group by 'age' value and apply aggregate functions:
result2 = df.groupby(['age']).agg(aggregates1)
print("=> Grouped by age (before):")
print(result2)
print()

# some "age" values are missing (so drop them):
df = df.dropna()
# convert floating point values to integers:
df['age'] = df['age'].astype(int)

# group by 'age' value and apply aggregate functions:
result3 = df.groupby(['age']).agg(aggregates1)
print("=> Grouped by age (after):")
print(result3)
print()
```

Listing 3.36 使用 CSV 文件 `titanic.csv` 的内容初始化数据框 `df`。接下来的代码段将浮点值转换为整数，随后定义变量 `aggregates1`，该变量指定了在 `embark_town` 字段上调用的 `count()`、`nunique()` 和 `size()` 函数。

接下来的代码段在 `deck` 字段上调用 `groupby()` 方法后，通过调用 `agg()` 方法来初始化变量 `result`。

下一个代码块执行了相同的计算来初始化变量 `result2`，区别在于 `groupby()` 函数是在 `age` 字段上调用的，而不是 `embark_town` 字段。注意关于 `count()` 和 `nunique()` 函数的注释部分：让我们通过 `df.dropna()` 删掉缺失值的行，并调查这将如何影响计算。

在删除缺失值的行后，最后一个代码块以与 `result2` 完全相同的方式初始化变量 `result3`。在 Listing 3.36 中运行代码。输出所示：

```text
=> Grouped by deck:
     embark_town
           count nunique size
deck
A             15       2   15
B             45       2   47
C             59       3   59
D             33       2   33
E             32       3   32
F             13       3   13
G              4       1    4

=> Grouped by age (before):
        age
      count nunique size
age
0.42      1       1    1
0.67      1       1    1
0.75      2       1    2
0.83      2       1    2
0.92      1       1    1
...     ...     ...  ...
70.00     2       1    2
70.50     1       1    1
71.00     2       1    2
74.00     1       1    1
80.00     1       1    1
[88 rows x 3 columns]
=> Grouped by age (after):
      age
    count nunique size
age
0       1       1    1
1       1       1    1
2       3       1    3
3       1       1    1
4       3       1    3
6       1       1    1
11      1       1    1
14      1       1    1
15      1       1    1
// details omitted for brevity
60      2       1    2
61      2       1    2
62      1       1    1
63      1       1    1
64      1       1    1
65      2       1    2
70      1       1    1
71      1       1    1
80      1       1    1
```

### 在 Pandas 中使用 `APPLY()` 和 `MAPAPPLY()`

在本章较些部分，你看到了 Pandas `apply()` 方法的一个示例，用于修改 CSV 文件 `shirts.csv` 中特征的分类值。本节包含了更多 `apply()` 方法的示例，以及 `mapappy()` 方法的示例。

列表 3.37 显示了 `apply1.py` 的内容，它说明了如何调用 Pandas `apply()` 方法来计算一组值的和。

#### 列表 3.37：`apply1.py`

```python
import pandas as pd

df = pd.DataFrame({'X1': [1,2,3], 'X2': [10,20,30]})

def cube(x):
  return x * x * x

df1 = df.apply(cube)
# same result:
# df1 = df.apply(lambda x: x * x * x)

print("initial data frame:")
print(df)
print("cubed values:")
print(df1)
```

Listing 3.37 使用带有 `X1` 和 `X2` 列的数据框初始化 `df`，其中 `X2` 的值是 `X1` 的 10 倍。接下来，Python 函数 `cube()` 返回其立方。Listing 3.36 通过调用 `apply()` 函数并指定用户定义的函数 `cube()` 来定义变量 `df1`，然后打印 `df` 以及 `df1`。在 Listing 3.37 中运行代码，你将看到输出：

```text
initial data frame:
   X1  X2
0   1  10
1   2  20
2   3  30
cubed values:
   X1     X2
0   1000
1   8000
2   27000
```

列表 3.38 显示了 `apply2.py` 的内容，它说明了如何调用 Pandas `apply()` 方法来计算一组值的和。

#### 列表 3.38：`apply2.py`

```python
import pandas as pd
import numpy as np

df = pd.DataFrame({'X1': [10,20,30], 'X2': [50,60,70]})

df1 = df.apply(np.sum, axis=0)
df2 = df.apply(np.sum, axis=1)

print("initial data frame:")
print(df)
print("add values (axis=0):")
print(df1)
print("add values (axis=1):")
print(df2)
```

列表 3.38 是列表 3.37 的变体：变量 `df1` 和 `df2` 分别包含数据框 `df` 的列和和行。在列表 3.38 中运行代码，你将看到以下输出：

```text
 X1  X2
0  10  50
1  20  60
2  30  70
add values (axis=0):
X1     60
X2    180
dtype: int64
add values (axis=1):
0     60
1     80
2    100
dtype: int64
```

列表 3.39 显示了 `mapapply1.py` 的内容，它说明了如何调用 Pandas `mapapply()` 方法计算一组值的平方根。

#### 列表 3.39：`mapapply1.py`




```python
import pandas as pd
import math

df = pd.DataFrame({'X1': [1,2,3], 'X2': [10,20,30]})
df1 = df.applymap(math.sqrt)

print("initial data frame:")
print(df)
print("square root values:")
print(df1)
```

Listing 3.39 是 Listing 3.37 的另一种变体：在这种情况下，变量 `df1` 是通过在变量 `df` 上调用 `applymap()` 函数定义的，该函数反过来引用了（但没有执行）`math.sqrt()` 函数。接下来，`print()` 语句显示 `df` 的内容，随后是 `print()` 语句显示 `df1` 的内容：此时调用内置的 `math.sqrt()` 函数计算 `df` 中值的平方根。在 Listing 3.39 中运行代码，你将看到以下输出：

```
initial data frame:
   X1  X2
0   1  10
1   2  20
2   3  30

square root values:
         X1        X2
0  1.000000  3.162278
1  1.414214  4.472136
2  1.732051  5.477226
```

Listing 3.40 显示了 `mapapply2.py` 的内容，它说明了如何调用 Pandas `mapapply()` 方法将字符串转换为小写和大大写。

**LISTING 3.40: mapapply2.py**

```python
import pandas as pd

df = pd.DataFrame({'fname': ['Jane'], 'lname': ['Smith']},
                  {'fname': ['Dave'], 'lname': ['Jones']})

df1 = df.applymap(str.lower)
df2 = df.applymap(str.upper)
print("initial data frame:")
print(df)
print("lowercase:")
print(df1)
print("uppercase:")
print(df2)
```

Listing 3.40 使用两个姓名对初始化变量 `df`，然后通过在变量 `df` 上调用 `applymap()` 方法定义变量 `df1` 和 `df2`。变量 `df1` 将其输入值转换为小写，而变量 `df2` 将其输入值转换为大写。在 Listing 3.40 中运行代码，你将看到以下输出：

```
initial data frame:
      fname  lname
fname  Jane  Smith
lname  Jane  Smith

lowercase:
      fname  lname
fname  jane  smith
lname  jane  smith

uppercase:
      fname  lname
fname  JANE  SMITH
lname  JANE  SMITH
```

## Pandas 中实用的单行命令

本节包含了 Pandas 中各种实用的单行命令（其中一些你已经在本章中见过），这些命令对你来说非常有用。

列出数据框的列名：

```python
df.columns
```

从数据框中删除缺失数据：

```python
df.dropna(axis=0, how='any')
```

删除一个不必要的列：

```python
my_dataset = my_dataset.drop(["url"], axis=1)
```

删除只有一个单一值的列，或者缺失值超过其 50% 的列：

```python
dataset = dataset.dropna(thresh=half_count, axis=1)
```

替换数据框中的缺失数据：

```python
df.replace(to_replace=None, value=None)
```

检查数据框中的 NAN（空值）：

```python
pd.isnull(object)
```

删除数据框中的一个特征：

```python
df.drop('feature_variable_name', axis=1)
```

将数据框中的对象类型转换为浮点数：

```python
pd.to_numeric(df["feature_name"], errors='coerce')
```

将数据框中的数据转换为 NumPy 数组：

```python
df.as_matrix()
```

显示数据框的前 `n` 行：

```python
df.head(n)
```

通过特征名获取数据框中的数据：

```python
df.loc[feature_name]
```

对数据框应用函数，例如将数据框中 `height` 列的所有值乘以 3：

```python
df["height"].apply(lambda height: 3 * height)
```

或者：

```python
def multiply(x):
    return x * 3

df["height"].apply(multiply)
```

将数据框的第四列重命名为 `height`：

```python
df.rename(columns={df.columns[3]: 'height'}, inplace=True)
```

获取数据框中第一列的唯一条目：

```python
df["first"].unique()
```

从现有数据框创建一个包含 `first` 和 `last` 列的数据框：

```python
new_df = df[["first", "last"]]
```

对数据框中的数据排序：

```python
df.sort_values(ascending=False)
```

过滤名为 `size` 的数据列，仅显示等于 7 的值：

```python
df[df["size"] == 7]
```

选择数据框中 `height` 列的第一行：

```python
df.loc([0], ['height'])
```

## 处理基于 JSON 的数据

一个 JSON 对象由用冒号分隔的“名/值对”表示的数据，以及用逗号分隔的数据对象组成。对象在大括号 `{}` 内部指定，而对象数组用方括号 `[]` 表示。请注意，字符值类型的数据元素位于一对双引号 `""` 之中（但数值型数据不需要引号）。

这里是一个 JSON 对象的简单示例：

```json
{ "fname":"Jane", "lname":"Smith", "age":33, "city":"SF" }
```

这是一个 JSON 对象数组的简单示例（注意外层包裹的方括号）：

```json
[
  { "fname":"Jane", "lname":"Smith", "age":33, "city":"SF" },
  { "fname":"John", "lname":"Jones", "age":34, "city":"LA" },
  { "fname":"Dave", "lname":"Stone", "age":35, "city":"NY" }
]
```

### Python 字典与 JSON

`json` 库允许你在 Python 中处理基于 JSON 的数据。

列表 3.41 显示了 `dict2json.py` 的内容，说明了如何将 Python 字典转换为 JSON 字符串。

**列表 3.41: `dict2json.py`**

```python
import json

dict1 = {}
dict1["fname"] = "Jane"
dict1["lname"] = "Smith"
dict1["age"] = 33
dict1["city"] = "SF"

print("Python dictionary to JSON data:")
print("dict1:", dict1)
json1 = json.dumps(dict1, ensure_ascii=False)
print("json1:", json1)
print("")

# convert JSON string to Python dictionary:
json2 = '{"fname":"Dave", "lname":"Stone", "age":35, "city":"NY"}'
dict2 = json.loads(json2)
print("JSON data to Python dictionary:")
print("json2:", json2)
print("dict2:", dict2)
```

列表 3.41 调用了 `json.dumps()` 函数来执行从 Python 字典到 JSON 字符串的转换。运行列表 3.41 中的代码，你将看到以下输出：

```text
Python dictionary to JSON data:
dict1: {'fname': 'Jane', 'lname': 'Smith', 'age': 33, 'city': 'SF'}
json1: {"fname": "Jane", "lname": "Smith", "age": 33, "city": "SF"}
```

### Python 字典和 JSON

`json` 库允许你在 Python 中处理基于 JSON 的数据。

列表 3.41 显示了 `dict2json.py` 的内容，说明了如何将 Python 字典转换为 JSON 字符串。

**列表 3.41: `dict2json.py`**

```python
import json

dict1 = {}
dict1["fname"] = "Jane"
dict1["lname"] = "Smith"
dict1["age"] = 33
dict1["city"] = "SF"

print("Python dictionary to JSON data:")
print("dict1:", dict1)
json1 = json.dumps(dict1, ensure_ascii=False)
print("json1:", json1)
print("")

# convert JSON string to Python dictionary:
json2 = '{"fname":"Dave", "lname":"Stone", "age":35, "city":"NY"}'
dict2 = json.loads(json2)
print("JSON data to Python dictionary:")
print("json2:", json2)
print("dict2:", dict2)
```

列表 3.41 调用了 `json.dumps()` 函数来执行从 Python 字典到 JSON 字符串的转换。运行列表 3.41 中的代码，你将看到以下输出：

```text
Python dictionary to JSON data:
dict1: {'fname': 'Jane', 'lname': 'Smith', 'age': 33, 'city': 'SF'}
json1: {"fname": "Jane", "lname": "Smith", "age": 33, "city": "SF"}
```

## 总结

本章介绍了如何使用 Pandas 创建带标签的数据框并显示数据框的元数据。然后，你学习了如何从各种数据源创建数据框，例如随机数和硬编码的数据值。

你还学习了读取 Excel 表格并对这些数据进行数值计算，例如数值列的最小值、平均值最大值。随后，你看到了如何从存储在 CSV 文件中的数据创建数据框。此外，你还学习了如何根据数据框中的数据生成散点图。

最后，你对 JSON 进行了简单介绍，并将 Python 字典转换为 JSON 数据（反之亦然）的示例。

# 第 4 章

## RDBMS 与 SQL

本章将向你介绍 RDBMS、各种 SQL 概念以及对 MySQL 的快速介绍。MySQL 是一个健壮的 RDBMS，可以从 Oracle 网站免费下载。此外，你在本章中关于 MySQL 学到的几乎所有内容都适用于其他 RDBMS，例如 PostgreSQL 和 Oracle。

本章描述了一个假设的网站，该网站允许用户注册以购买各种工具（如锤子和扳手）。虽然本节没有代码，但你将了解到所需的表、它们之间的关系以及这些表的结构。

### 什么是 RDBMS？

关系数据库管理系统（RDBMS）将数据存储在表中，表中包含带有标记的属性（非正式地有时称为 `列`），这些属性具有特定的数据类型。RDBMS 的示例包括 `MySQL`、`Oracle` 和 `IBM DB2`。虽然关系数据库通常为数据存储提供良好的解决方案，但在某些情况下，速度和扩展性可能会成为问题。NoSQL 数据库（如 `MongoDB`）在扩展性方面可能更为合适。

### RDBMS 中的表之间存在什么关系？

虽然 RDBMS 可以只包含一个表，但它通常包含多个表，这些表之间可以存在各种类型的关联。例如，当你在食品商店购买各种物品时，你的收据由一个订单组成，该订单包含一个或多个“行项目”（line items），每个行项目都指明了你购买的特定商品的详情。这被称为订单（存储在 `purchase_orders` 表中）与你购买的每个商品的行项目（存储在 `line_items` 表中）之间的 `一对多` 关系。

另一个例子涉及学生和课程：每个学生都选了一或多门课程，这是从学生到课程的一对多关系。此外，每门课程包含一个或多个学生，因此存在从课程到学生的一对多关系。因此，学生表和课程表之间是多对多的关系。

第三个例子是 `employees` 表，每行都包含一个员工的信息。如果每行都包含该员工经理的 `id`，那么 `employees` 表就是一个 `自引用` 表，因为查找员工的经理涉及到使用该员工记录中存储的经理 `id` 在 `employees` 表中进行搜索。然而，如果 `employees` 表中的行不包含员工经理的信息，那么该表就不是自引用的。

除了表定义，数据库还经常包含索引、主键和外键，这些有助于在表中搜索数据，并将特定表中的某行与另一个表中逻辑上相关的行（或多行）“连接”起来。例如，如果我们在 `purchase_orders` 表中有一个某个特定订单的 `id` 值，我们可以在 `line_items` 表中找到所有包含相同订单 `id` 的行项目（即被购买的物品）。

### RDBMS 的特性

RDBMS 提供了一种方便的数据存储方式，通常与某种类型的应用程序相关。例如，稍后你将看到一个四表 RDBMS 的细节，它用于跟踪通过 Web 应用程序购买的工具。从高层次的角度来看，RDBMS 具有以下特性：

- 数据库包含一个或多个表。
- 数据存储在表中。
- 数据记录具有相同的结构。
- 适用于垂直扩展。
- 支持 ACID（下文将解释）。

另一个有用的概念是 `逻辑模式`（logical schema），它由 RDBMS 中的表及其关系（以及索引、视图、触发器等）的集合组成。该模式用于生成物理模式，它包含了创建指定表及其关系所需的所有 `SQL` 语句。

### 什么是 ACID？

ACID 是原子性（Atomicity）、一致性（Consistency）、隔离性（Isolation）和持久性（Durability）的缩写，指的是 RDBMS 事务的属性。

- `Atomicity`（原子性）意味着每个事务要么成功、要么失败，因此如果事务失败，系统将回滚到之前的状态。
- `Consistency`（一致性）意味着成功的事务始终会导致有效的数据库状态。
- `Isolation`（隔离性）意味着并发或串行执行事务将产生一致的结果。
- `Durability`（持久性）意味着已提交的事务将保持在相同状态。

RDBMS 支持 ACID，而 NoSQL 数据库通常不支持 ACID。

### 我们在什么时候需要 RDBMS？

简短的回答是，当我们需要存储一个或多个已发生事件记录时，RDBMS 非常有用，这可能涉及简单的物品购买，也涉及复杂的跨表财务事务。

RDBMS 允许你定义一组包含数据行的表，其中每行包含一个或多个属性（非正式地称为 `字段`）。数据行是发生在特定时间点的事件的记录，它可能涉及多个表，也可以涉及某种类型的“事务”。

例如，考虑一个包含名为 `events` 的单表的数据库，其中单行包含你通过某些过程（如 Web 页面注册表）创建的单个事件的信息。尽管这在概念上很简单，但请注意以下属性对于 `events` 表中的每行都是相关的：`event_id`、`event_time`、`event_title`、`event_duration` 和 `event_location`，可能的其他属性。

现在考虑两个银行账户之间的资金转账场景：你需要从储蓄账户转账 $100 元到支票账户。该过程涉及两个步骤：

1. 扣除（减去）储蓄账户 $100 元。
2. 存入（增加）储蓄账户 $100 元。

然而，如果在步骤 1 之后、步骤 2 完成之前发生系统故障，你就丢失了 $100 元。显然，步骤 1 和步骤 2 必须被视为一个 `原子事务`，这意味着只有当两个步骤都成功完成后，事务才成功。如果事务失败，事务将“回滚”，以便系统恢复到两个账户之间转账之前的状态。

正如你在本章早期学到的，RDBMS 支持 ACID，这确保了之前的事务（即账户之间的资金转账）被视为一个原子事务。

虽然原子事务是金融系统的基础，但它们对于其他系统可能没有那么关键。例如，上一个例子涉及在创建新事件时在 `events` 表中插入一个新行。如果此过程失败，解决方案可能包括在系统重新在线时再次注册事件。

### 规范化的重要性

本节介绍了规范化的概念；在线文章提供了有关规范范式的更详细信息。将此主题分为两个章节中的两个部分将有助于理解规范化。

作为一个起点，考虑一个存储在时间段内（如一天、一周或其他时间段）房间温度记录的 RDBMS。我们只需要一个 `device_temperature` 表，其中每行都包含特定时间房间的温度。在 IoT（物联网）的情况下，温度是在常规的时间间隔内（如每分钟或每小时）记录的。




如果你只需要跟踪一个房间，`device_temperature` 表可能足够了。但是，如果你需要跟踪房间内的多个设备，那么创建一个名为 `device_details` 的第二个表会很方便，该表包含每个设备的属性，如 `device_id`、`device_name`、`device_year`、`device_price` 和 `device_warranty`。

然而，我们需要将来自 `device_temperature` 表的某行信息连接到其在 `device_details` 表中的关联行。双表连接非常简单：`device_details` 表中的每行都包含一个 `device_id`，它能唯一标识该行。此外，在 `device_temperature` 表中，任何引用该设备的行都会出现相同的 `device_id`。

上述的双表结构是数据库 `normalization`（范式/规范化）的一个极简示例，它减少了数据库表中的数据冗余，但有时会以执行某些类型 `SQL` 语句（例如包含 `JOIN` 关键字的语句）时性能变慢为代价。

如果你是数据库 `normalization` 概念的新手，可能会认为规范化增加了复杂性并降低了性能，而没有提供实际收益。虽然这种考虑是合理的，但这种权衡是值得的。

为了说服你接受规范化的价值，假设 `purchase_orders` 表中的每条记录都包含完成购买客户的所有细节。结果是我们可以消除 `customers` 表。然而，如果我们以后需要更新特定客户的地址，就需要更新 `purchase_orders` 表中所有包含该客户的行。相比之下，如果我们维护一个 `customers` 表，那么更新客户地址只需更改 `customers` 表中的单行即可。

规范化使我们能够避免数据重复，从而在必须更新信息（如客户地址）时，有一个单一的“事实之源”。从另一个角度来看，数据重复意味着相同的数据出现在两个（或可能更多）位置，如果更新没有应用到所有这些位置，数据库数据将处于不一致状态。取决于应用程序的性质，数据不一致的后果可能从微小到灾难性不等。

始终记住这一点：每当你需要更新位于两个不同位置的相同数据时，你就会增加数据不一致的风险，这会对数据完整性产生不利影响。

作为另一个例子，假设一个网站在线销售小部件：至少，关联数据库需要以下四张表：

- `customer_details`
- `purchase_orders`
- `po_line_items`
- `item_desc`

上述场景将在下一节中进行更详细探讨，该节将指定上述每个表的属性。

### 一个四表 RDBMS

作为一个介绍性示例，假设 `[www.mytools.com]` 销售家用或建筑工具（细节并不重要）。为了简单起见，让我们假定上述 URL 有一个实际的网页，且该网页包含以下部分：

- 新用户注册
- 现有用户登录
- 用于选择购买物品（及数量）的输入字段

例如，注册用户 John Smith 想要购买一把锤子、两把螺丝刀和三把扳手。网页需要为用户提供按类型（例如锤子、螺丝刀和扳手）搜索产品的能力，然后显示匹配的产品列表。列表中的每个产品还应包含一个 `SKU`，这是一种行业标准的产品标记机制（就像识别书籍的 `ISBNs` 一样）。

上述功能对于开发允许用户购买产品的网页是必要的。然而，本节的目的是描述 `RDBMS` 中的一组表（以及它们之间的关系），因此我们假设我们的 URL 已经提供了必要的 Web 功能。

让我们描述一个“用例”，该用例包含了将代表现有客户 John Smith（其客户 ID 为 1000）执行的步骤序列，他想要购买 1 把锤子、2 把螺丝刀和 3 把扳手：

> 步骤 1：客户 John Smith（`cust_id` 为 1000）发起一次新购买。
>
> 步骤 2：创建一个新的购买订单，`po_id` 值为 12500。
>
> 步骤 3：John Smith 选择了 1 把锤子、2 把螺丝刀和 3 把扳手。
>
> 步骤 4：屏幕上显示关联价格 20.00、16.00 和 30.00。
>
> 步骤 5：显示小计金额，为 66.00。
>
> 步骤 6：显示税费 6.60（税率为 10%）。
>
> 步骤 7：显示总费用 72.60。

步骤 8 将允许 John Smith 移除某个物品、增加/减少每个所选物品的数量、删除物品或取消购买订单。步骤 9 将允许 John Smith 进行支付。再次，为了简单起见，我们假设步骤 8 和步骤 9 是可用的。

注意，步骤 8 涉及用购买订单详情更新我们的几张表。步骤 9 为创建订单的日期创建一个时间戳，以及购买订单的状态（“已支付”与“待处理”）。购买订单的状态用于生成报告，以显示逾期付款的客户（可能还会向他们发送友好的提醒）。有时公司有一种基于奖励的系统，按时付款的客户可以收集积分，这些积分可用于其他购买（换句话说，这是一种折扣机制）。

### 详细表描述

如果你能视觉化上一节中描述的用例，你可能看到我们需要一张表来存储特定客户的信息，另一张表来存储购买订单（以某种方式与关联的客户链接），一张包含所购物品详情和数量的表（通常称为“行项目”），以及一张包含每个工具信息的表（包含名称和价格）。因此，我们网站的 RDBMS 需要以下表：

```text
customers
purchase_orders
line_items
item_desc
```

接下来的章节将描述上述表的内容及其之间的关系。

#### `customers` 表

虽然指定 `customers` 表属性有多种方法，你需要足够的信息来唯一标识表中的每个客户。类比，除了 `cust_id` 外，向某人寄信封需要以下信息：

```text
cust_id
first_name
last_name
home_address
city
state
zip_code
```

我们将使用上述列表中的属性创建 `customers` 表。注意，`cust_id` 属性被称为键，因为它能唯一标识每个客户。虽然我们不会讨论键在 `RDBMS` 中的作用，但显然我们需要一种唯一标识客户的机制。

每当我们需要引用特定客户的详情时，我们将使用 `cust_id` 的关联值从 `customers` 表的对应行中检索详情。

上述段落描述了 `RDBMS` 中关联表 `T1` 和 `T2` 的本质：`T1` 中的键作为属性值存储在 `T2` 中。如果我们需要访问表 `T3` 中的关联信息，我们将 `T2` 中的键作为属性值存储在 `T3` 中。

注意，生产系统中的 `customers` 表会包含其他属性，如下：

```text
title（先生、女士、小姐等）
shipping_address
cell_phone
```

为了简单起见，我们将使用初始属性集来定义 `customers` 表。之后，你可以将新属性添加到三个表模式中，使其更像现实系统。

为了使此表更具体，假设以下信息属于客户 John Smith，他被分配了 `cust_id` 1000：

```text
cust_id: 1000
first_name: John
last_name: Smith
home_address: 1000 Appian Way
city: Sunnyvale
state: California
zip_code: 95959
```

每当 John Smith 进行新购买时，我们都会使用 `cust_id` 值 1000 在 `purchase_order` 表中为该客户创建新的一行。

### `purchase_orders` 表

当客户访问网站时，我们需要创建一个购买订单，并将其作为新行插入到 `purchase_orders` 表中。虽然你可能倾向于将所有客户的详细信息都放在新行中，但我们将通过关联的 `cust_id` 来识别客户，并改用该值。

请注意，每当有新用户在网站注册时，我们都会在 `customers` 表中创建一个新行，而对于回头客，则是通过现有的 `cust_id` 来识别的，该 ID 必须通过客户在主 Web 页面输入框中输入的信息搜索 `customers` 表来确定。

我们看到 `customers` 表包含一个键属性；同样地，`purchase_orders` 表需要一个我们称之为 `po_id` 的属性（你可以自由使用不同的字符串）来识别特定客户的购买订单。

请记住以下细节：具有特定 `po_id` 的行还需要一个 `cust_id` 属性，用于识别正在当前购买的客户（在 `customers` 表中）。

虽然定义一组合适的属性有多种方法，但让我们使用以下属性集用于 `purchase_orders` 表：

```text
po_id
cust_id
purchase_date
```

例如，假设客户 John Smith（其 `cust_id` 为 1000）在 2021 年 12 月 15 日购买了一些工具。关系型数据库管理系统（RDBMS）支持几十种不同的日期格式：简单起见，我们将使用 `MM-DD-YYYY` 格式（你可以根据特定需求进行更改）。

那么 John Smith 在 `purchase_orders` 中的新行看起来如下所示：

```text
po_id: 12500
cust_id: 1000
purchase_date: 12-01-2021
```

### `line_items` 表

作为一个例子，假设客户 John Smith 在他最近的购买订单中请求了 1 把锤子、2 把螺丝刀和 3 把扳手。这些购买物品中的每一个项目都需要 `line_items` 表中对应一行，且该行：

- 由 `line_id` 值识别
- 指定每个所购物品的数量
- 包含 `purchase_orders` 表中关联的 `po_id` 值
- 包含 `item_desc` 表中关联的 `item_id` 值

为了简单起见，我们将值 5001、5002 和 5003 分配给 `line_items` 表中三个新行的 `line_id` 属性，这三行分别代表当前购买订单中的锤子、螺丝刀和扳手物品。一个 `line_item` 行可能如下：

```text
po_id: 12500
line_id: 5001
item_id: 100 <= 我们很快会讨论这个
item_count: 1
item_price: 20.00
item_tax:  2.00
item_subtotal: 22.00
```

注意，在前面的 `line_item` 中没有 `cust_id`：这是因为采用了自上而下的数据检索方法。具体来说，我们从一个特定的 `cust_id` 开始，用它来在 `purchase_orders` 表中查找属于该 `cust_id` 的购买订单列表，并且对于 `purchase_orders` 表中的每一个购买订单，我们在 `line_items` 表中搜索关联的行项目。此外，我们可以对 `cust_id` 值列表中的每个客户重复上述操作步骤。

回到之前的 `line_item` 细节：我们需要通过 `item_desc` 表中关联的标识符来引用每个购买的物品。再次，我们将任意地为锤子、螺丝刀和扳手物品分别分配 100、200 和 300 的 `item_id` 值。在你的应用程序中，实际值无疑会有所不同，因此数字 100、200 和 300 并没有特殊的意义。

`line_items` 表中的这三行（它们属于同一个购买订单）看起来如下所示（我们稍后会查看相应的 SQL 语句）：

```text
po_id: 12500
line_id: 5001
item_id: 100
item_count: 1
item_price: 20.00
item_tax:  2.00
item_subtotal: 22.00

po_id: 12500
line_id: 5002
item_id: 200
item_count: 2
item_price: 8.00
item_tax:   1.60
item_subtotal: 17.60

po_id: 12500
line_id: 5003
item_id: 300
item_count: 3
item_price: 10.00
item_tax:    3.00
item_subtotal: 33.00
```

### `item_desc` 表

回想一下，`customers` 表包含每个客户的信息，每当客户在网站创建账户时都会创建一个新行。类似的，`item_desc` 表包含了每个物品（产品）的信息。`item_desc` 表的更新比 `customers` 表频繁，在以下情况：

- 新工具上架
- 现有工具不再售卖

因此，`item_desc` 表包含了客户可以购买的所有工具。至少，它是“真理来源”：

```sql
SELECT *
FROM item_desc;
```

| item_id | item_desc   | price |
|---:|:---|---:|
| 100 | hammer | 20.00 |
| 200 | screwdriver | 8.00 |
| 300 | wrench | 10.00 |

还有一个重要的细节需要讨论：如果某个物品不再售卖，我们可以简单地删除它的行吗？答案是“否”，因为我们需要它来生成报告。因此，添加一个名为 `AVAILABLE`（或类似的）属性包含 1 或 0，以指示产品是否可用。结果，涉及该表的某些 SQL 查询也将考虑这一点。

## 什么是 SQL

结构化查询语言（SQL）用于管理表中的数据。事实上，SQL 是用于处理结构化数据库的标准语言。在高级术语中，用于检索数据的 SQL 语句通常涉及以下内容：

- 你想要的数据（`SELECT`）
- 数据所在的表（`FROM`）
- 数据的任何条件（`WHERE`）

例如，假设有一个 `friends` 表包含 `lname` 和 `fname` 属性（分别是姓和名），用于表示一组朋友，且该表中的每一行都包含关于一个朋友的信息。在第 2 章中，我们讨论了如何创建数据库表以及如何向表中填充数据，但现在我们只需假设这些任务已经完成。那么，检索 `friends` 表中人员姓和名的 SQL 语句如下：

```sql
SELECT lname, fname
FROM friends;
```

假设 `friends` 表还包含一个 `height` 属性，即 `friends` 表中每个人的数字（厘米）。我们可以扩展之前的 SQL 语句，指定我们需要身高小于 180 的人员（行）：

```sql
SELECT lname, fname
FROM friends
WHERE height < 180;
```

SQL 提供了大量的关键字，允许你指定从多个表中检索数据的复杂查询。上述两个 SQL 语句都称为 DML 语句，它是 SQL 语句的四个类别之一：

- DCL（数据控制语言）
- DDL（数据定义语言）
- DQL（数据查询语言）
- DML（数据操作语言）

接下来的章节将为上述列表中的每项提供更多信息。

# DCL、DDL、DQL、DML 和 TCL

数据控制语言（DCL）指的是任何包含 `GRANT` 或 `REVOKE` 关键字的 SQL 语句。这两个关键字都会影响对特定用户授予或撤销的权限。

数据定义语言（DDL）包括任何指定内容的 SQL 语句：`CREATE`、`ALTER`、`DROP`、`RENAME`、`TRUNCATE` 或 `COMMENT`。这些 SQL 关键字通常与数据库表以及（在许多情况下）数据库视图（后文讨论）配合使用。

数据查询语言（DQL）指的是任何包含 `SELECT` 关键字的 SQL 语句。

数据操作语言（DML）指的是对数据库中的一个或多个表执行查询的 SQL 语句。这些 SQL 语句包含 `INSERT`、`UPDATE`、`DELETE`、`MERGE`、`CALL`、`EXPLAIN PLAN` 或 `LOCK TABLE` 中的任何关键字。在大多数情况下，这些关键字会修改一个或多个表中现有数据的值。

事务控制语言（TCL）包括 `COMMIT`、`ROLLBACK`、`SAVEPOINT` 或 `SET TRANSACTION` 关键字，这些都是本书中未讨论的高级概念。

# SQL 权限

SQL 中提供两种权限，本节将对两者进行简要描述。这些权限指的是数据库对象（如数据库表和索引），将在后续章节中进行更详细讨论。

系统权限涉及特定类型的对象，并规定了在对象上执行一个或多个操作的权利。此类操作包括管理员允许用户执行任务，例如 `ALTER ANY INDEX`、`ALTER ANY CACHE GROUP`、`CREATE/ALTER/DELETE TABLE` 或 `CREATE/ALTER/DELETE VIEW`。

对象权限允许用户对对象或其他用户的对象（如表、视图和索引）执行操作。额外的对象权限包括 `EXECUTE`、`INSERT`、`UPDATE`、`DELETE`、`SELECT`、`FLUSH`、`LOAD`、`INDEX` 和 `REFERENCES`。

# SQL 语句的属性

SQL 语句和函数区分大小写，但引号文本区分大小写。以下是一些示例：

```sql
 select VERSION();
+-----------+
| VERSION() |
+-----------+
| 8.0.21    |
+-----------+
1 row in set (0.000 sec)

MySQL [mytools]> SeLeCt Version();
+-----------+
| Version() |
+-----------+
| 8.0.21    |
+-----------+
| 8.0.21    |
+-----------+
1 row in set (0.000 sec)
```

请记住关于 SQL 语句的以下有用细节：

- SQL 语句不区分大小写。
- SQL 语句可以跨单行或多行。
- 关键字不能缩写或跨行拆分。
- 子句通常放在单独的行。
- 缩进是为了增强可读性。

# CREATE 关键字

通常情况下，你有时会使用 `CREATE` 关键字创建数据库，但更多时候是使用它来创建表、视图和索引。然而，以下列表包含了你可以通过 `CREATE` 语句创建的所有对象：

```text
DATABASE
EVENT
FUNCTION
INDEX
PROCEDURE
TABLE
TRIGGER
USER
VIEW
```



本文仅讨论了特定数据库的示例，而在线文章则深入探讨了上述列表中其他主题。

# 什么是 MySQL？

MySQL 是一个开源数据库，具有移植性，并提供了许多商业数据库中可用的功能。Oracle 是 MySQL 数据库的守护者，你可以在以下网站下载它：

[`www.mysql.com/downloads/`](https://www.mysql.com/downloads/)

MySQL 还提供了一个用于执行数据库相关操作的 GUI 接口。MySQL 8 提供了以下新功能：

- 事务型数据字典
- 对 `BLOB`、`TEXT`、`GEOMETRY` 和 `JSON` 数据类型的改进支持

正如你在第 7 章](#ch07.xhtml) 中看到的，MySQL 支持可插件存储引擎，例如 `InnoDB`。

# 关于 MariaDB？

MariaDB 是 MySQL 的一个分支，它具有许多 MySQL 的特性。MariaDB 是 MySQL 的一个分支，它具有许多 MySQL 的特性。MariaDB MariaDB MariaDB MariaDB MariaDB MariaDB MariaDB MariaDB MariaDB MariaDB MariaDB MariaDB MariaDB MariaDB MariaDB MariaDB MariaDB

# 安装 MySQL

MariaDB 是 MySQL 的一个分支，它具有许多 MySQL 的特性。在长度在创建表时声明的固定长度。MySQL。

你可以通过以下命令安装 MySQL：

```bash
$ mysql -p
```

# MySQL 中的数据类型

本节包含了 MySQL 支持的类型列表，随后是关于某些类型的详细说明：

- `BIT` 类型用于存储位值。
- `BOOLEAN` 类型存储真/假。
- `CHAR` 类型用于固定长度字符串。
- `DATE` 类型用于存储日期。
- `DATETIME` 类型用于存储日期和时间。
- `DECIMAL` 类型用于精确数值。
- `ENUM` 类型是存储字符串的紧凑方式。
- `INT` 类型用于整数。
- `JSON` 类型用于存储 JSON 文档。
- `TEXT` 类型用于存储文本。
- `TIME` 类型用于存储时间。
- `TIMESTAMP` 类型用于更广泛的时间范围。
- `TO_SECONDS` 类型用于时间时间秒。
- `VARCHAR` 类型用于变长度字符串。
- `XML` 类型提供对 XML 文档的支持。

# CHAR 和 VARCHAR

`CHAR` 类型在创建表时具有固定列长度，范围从 1 到 255。`CHAR` 值会在右侧填充空格，并在检索 `CHAR` 值时删除末尾空格。

相比之下，`VARCHAR` 类型表示变长度的 `CHAR` 值，长度在 1 到 2000 之间，并占用 `NULL` 空间。

相比之下，`VARCHAR2` 类型表示变长度的 `CHAR` 值，长度在 1 到 4000 之间，但不能占用 `NULL` 空间。因此，`VARCHAR2` 的性能优于 `VARCHAR`。

# 字符串数据类型

之前的项目列表包含各种字符串类型，后者已被提取并放在下面的单独列表中以便你使用：

```
BLOB
CHAR
ENUM
SET
TEXT
VARCHAR
```

`ENUM` 数据类型是字符串对象，指定了一组预定义值，可以在创建表时使用：

```sql
CREATE TABLE PIZZA(name ENUM('Small', 'Medium','Large'));
Query OK, 0 rows affected (0.021 sec)

DESC pizza;
+-------+--------------------------------+------+-----+---------+-------+
| Field | Type                           | Null | Key | Default | Extra |
+-------+--------------------------------+------+-----+---------+-------+
| name  | enum('Small','Medium','Large') | YES  |     | NULL    |       |
+-------+--------------------------------+------+-----+---------+-------+
1 row in set (0.004 sec)
```

# BLOB 和 TEXT 数据类型

二进制大对象（`BLOB`）可以存储任意数量的数据。共有四种 BLOB 类型，它们唯一的区别在于最大长度：

```
TINYBLOB
BLOB
MEDIUMBLOB
LONGBLOB
```

TEXT 数据类型是一种不区分大小写的 BLOB，共有四种 TEXT 类型，它们的区别在于最大长度（所有这些类型都是非标准数据类型）：

```
TINYTEXT
TEXT
MEDIUMTEXT
LONGTEXT
```

请记住 BLOB 类型与 TEXT 类型之间的以下区别：`BLOB` 类型涉及区分大小大小写排序和比较，而这些操作对于 `TEXT` 类型来说是不区分大小写的。

# MYSQL 数据库操作

你可以对 MySQL 数据库执行若干操作，如下所示：

- 创建数据库
- 导出数据库
- 丢数据库
- 重命名数据库

你将在接下来的小节中看到如何执行上述每个列表项的示例。

## 创建数据库

登录 MySQL 并调用以下命令创建 `mytools` 数据库：

```
MySQL [mysql]> create database mytools;
Query OK, 1 row affected (0.004 sec)
```

使用以下命令选择 `mytools` 数据库：

```
MySQL [(none)]> use mytools;
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A
Database changed
```

## 显示数据库列表

通过调用以下 SQL 语句显示现有数据库：

```
mysql> SHOW DATABASES;
```

上述命令显示了以下输出（输出将根据你的机器而有所不同）：

```
+--------------------+
| Database           |
+--------------------+
| beans              |
| information_schema |
| minimal            |
| mysql              |
| mytools            |
| performance_schema |
| sys                |
+--------------------+
9 rows in set (0.002 sec)
```

## 显示数据库用户列表

通过调用以下 SQL 语句显示现有用户：

```
mysql> select user from mysql.user;
```

上述命令显示了以下输出：

```
+------------------+
| user             |
+------------------+
| mysql.infoschema |
| mysql.session    |
| mysql.sys        |
| root             |
+------------------+
4 rows in set (0.001 sec)
```

## 丢弃数据库

登录 MySQL 并调用以下命令创建、选择然后丢弃 `pizza` 数据库：

```
MySQL [(none)]> create database pizza;
Query OK, 1 row affected (0.004 sec)

MySQL [(none)]> use pizza;
Database changed
MySQL [pizza]> drop database pizza;
Query OK, 0 rows affected (0.007 sec)
```

虽然在不包含任何数据的数据库上执行此任务似乎毫无意义，但它是简单的，而且如果将来有需要执行此任务的时候，你已经已经该如何操作了。

# 导出数据库

虽然你现在有一个空的数据库，但了解导出数据库的步骤仍然很好，这可以作为备份，并提供了一种在另一台机器上创建现有数据库副本的简单方法。

为了说明，让我们首先在 MySQL 中创建一个名为 `minimal` 的数据库，如下所示：

```
MySQL [mytools]> create database minimal;
Query OK, 1 row affected (0.006 sec)
```

接下来，调用 `mysqldump` 命令导出 `minimal` 数据库，如下所示：

```
mysqldump -u username -p"password" -R minimal > minimal.sql
```

注意上述命令中的以下细节。首先，在 `-p` 标志和密码之间没有插入空格，以便跳过命令行输入密码的提示。其次，确保省略引号。第三，`-R` 标志指示 `mysqldump` 除了数据库数据外，还复制存储的过程和函数。

此时，你可以在 `minimal` 数据库中创建表，并定期导出其内容。列表 4.1 显示了 `minimal.sql` 的内容，它是 `minimal` 数据库的完整描述。

***列表 4.1：minimal.sql***

```
-- MariaDB dump 10.18  Distrib 10.5.8-MariaDB, for osx10.15 (x86_64)
--
-- Host: localhost    Database: minimal
-- ------------------------------------------------------
-- Server version      8.0.21

/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;
/*!40103 SET @OLD_TIME_ZONE=@@TIME_ZONE */;
/*!40103 SET TIME_ZONE='+00:00' */;
/*!40014 SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0 */;
/*!40014 SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0 */;
/*!40101 SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='NO_AUTO_VALUE_ON' */;
/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION \|_{
/*!40101 SET NAMES utf8mb4 */;
/*!40103 SET @OLD_TIME_ZONE=@@TIME_ZONE */;
/*!40103 SET TIME_ZONE='+00:00' */;
/*!40014 SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0 */;
/*!40014 SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0 */;
/*!40101 SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='NO_AUTO_VALUE_ON' */;

-- Dump completed on 'minimal'
```

# 重命名数据库

虽然你现在有一个空的数据库，但了解如何重命名数据库仍然很好（旧版本的 MySQL 提供了 `RENAME DATABASE` 命令来重命名数据库；然而，新版本的 MySQL 删除了此功能以避免安全风险）。幸运的是，你可以通过涉及多个 MySQL 工具的三个步骤来重命名 `OLDDB`（你需要替换为要重命的数据库）为 `NEWDB`（替换为实际数据库名称）：

- 创建 `OLDDB` 的导出副本。
- 创建名为 `NEWDB` 的新数据库。
- 将数据从 `OLDDB` 导入到 `NEWDB`。

调用以下命令执行步骤 1：

```
mysqldump -u username -p"password" -R OLD_DB > OLD_DB.sql
```

调用以下命令执行步骤 2：

```
mysqladmin -u username -p"password" create NEWDB
```

调用以下命令执行步骤 3：

```
mysql -u username -p"password" NEWDB < OLD_DB.sql
```

登录 MySQL 并选择新数据库以验证一切运行正常：

```
MySQL [mysql]> use NEWDB;
Database changed
```

## INFORMATION_SCHEMA 表

`INFORMATION_SCHEMA` 表允许你检索有关给定列的信息。

```
TABLE_SCHEMA
TABLE_NAME
COLUMN_NAME
ORDINAL_POSITION
COLUMN_DEFAULT
IS_NULLABLE
DATA_TYPE
CHARACTER_MAXIMUM_LENGTH
NUMERIC_PRECISION
NUMERIC_SCALE
DATETIME_PRECISION
```

例如，让我们查看配套文件中提供的 `weather` 表结构（详情请见前言）：

```
MySQL [mytools]> desc weather;
+----------+----------+------+-----+---------+-------+
| Field    | Type     | Null | Key | Default | Extra |
+----------+----------+------+-----+---------+-------+
| day      | date     | YES  |     | NULL    |       |
| temper   | int      | YES  |     | NULL    |       |
| wind     | int      | YES  |     | NULL    |       |
| forecast | char(20) | YES  |     | NULL    |       |
| city     | char(20) | YES  |     | NULL    |       |
| state    | char(20) | YES  |     | NULL    |       |
+----------+----------+------+-----+---------+-------+
6 rows in set (0.001 sec)
```

我们可以通过以下查询获取有关 `weather` 表列的更多信息：

```
SELECT COLUMN_NAME, DATA_TYPE, IS_NULLABLE, COLUMN_DEFAULT
FROM INFORMATION_SCHEMA.COLUMNS
WHERE TABLE_NAME = 'weather'
AND table_schema = 'mytools';
```

上述查询生成以下输出：

```
+-------------+-----------+-------------+----------------+
| COLUMN_NAME | DATA_TYPE | IS_NULLABLE | COLUMN_DEFAULT |
+-------------+-----------+-------------+----------------+
| city        | char      | YES         | NULL           |
| day         | date      | YES         | NULL           |
| forecast    | char      | YES         | NULL           |
| state       | char      | YES         | NULL           |
| temper      | int       | YES         | NULL           |
| wind        | int       | YES         | NULL           |
+-------------+-----------+-------------+----------------+
6 rows in set (0.001 sec)
```

### PROCESSLIST 表



`PROCESSLIST` 表包含有关 SQL 语句状态的信息。当你想要查看表上表级或行级锁的状态时，这些信息非常有用。以下 SQL 语句展示了该表内容的一个示例：

```
MySQL [mytools]> show processlist;
+----+-----------------+-----------+---------+---------+--------+------------------------+------------------+
| Id | User            | Host      | db      | Command | Time   | State                  | Info             |
+----+-----------------+-----------+---------+---------+--------+------------------------+------------------+
|  5 | event_scheduler | localhost | NULL    | Daemon  | 138765 | Waiting on empty queue | NULL             |
|  9 | root            | localhost | mytools | Query   |      0 | starting               | show processlist |
+----+-----------------+-----------+---------+---------+--------+------------------------+------------------+
2 rows in set (0.000 sec)
```

### SQL 格式化工具

正如你预期的，SQL 语句有多种格式样式，你可以浏览它们以确定哪种样式最吸引你。以下链接是一个在线 SQL 格式化工具：

<https://codebeautify.org/sqlformatter>

以下链接包含 18 个 SQL 格式化工具，其中一些是付费的，另一些是免费的：

<https://www.sqlshack.com/sql-formatter-tools/>

以下链接包含 SQL 格式化规范列表（即：它不是关于格式化工具的）：

<https://opendatascience.com/best-practices-sql-formatting>

在一个已经建立了 SQL 格式化规则的环境中工作，将该样式与上述链接中 SQL 格式化工具的样式进行对比可能会有意思。

如果你是一个独立学习的 SQL 初学者，在通过此书学习更多 SQL 语句的过程中，探索这些链接也是值得的。随着你对编写 SQL 语句知识的增加，你会在博客文章中遇到各种样式，这意味着你也会注意到这些博客采用了哪些规范来格式化 SQL 语句。

### 总结

本章从介绍 RDBMS（关系型数据库管理系统）的概念以及使用 RDBMS 的理由开始。特别地，你看到了包含单张表、两个表和四张表的 RDBMS 示例（大得多的 RDBMS 多之不完）。

然后，你对数据库范式化的概念有了简要介绍，以及这样做如何帮助你在 RDBMS 中维护数据完整性（“单一真理来源”）。

接下来，你学习了一个包含四表的数据库的结构，该数据库通过 Web 页面跟踪客户对工具的购买情况。你还看到了哪些表具有一对多的关系，以便你可以找到属于特定购买订单的所有行项目。

此外，你还对 SQL 进行了简要介绍并了解了一些基本的 SQL 查询示例。你还学习了可以分类为 DCL、DDL、DQL 或 DML 的各种类型的 SQL 语句。

# 第 5 章：Java、JSON 和 XML

本章适用于任何需要使用 Java 访问存储在 MySQL 表中的数据的人。虽然本章对所有其他用户来说可能是可选的，但如果你预计未来某个时刻会涉及到 Java 和 MySQL 工作，即使你只是好奇用于管理 MySQL 数据库中数据的 Java 代码，浏览其内容也是值得关注的。

请记住，本章并不包含对 Java、XML 或 JSON 的技术介绍。然而，Java 代码示例执行了基本功能，例如通过 Java 创建数据库表，随后是来自 MySQL 数据库的插入、选择和删除数据的代码示例。因此，关于上述技术的简短教程可能就足够让你理解 Java 代码示例了。

简而言之，本章将帮助你学习如何使用 Java 在 MySQL 数据库中执行 CRUD（创建、替换、更新和删除）操作。第一节向你展示了如何使用 Java 创建关系型数据库以及关系表。你将学习在哪里下载 `JDBC`（Java 数据库连接）所需的 `JAR`（Java 存档）文件。此外，你将看到如何编译 Java 类并启动编译后的 Java 代码。本节还包含向此类表插入数据的示例，以及如何使用 Java 获取这些数据。

第一节包含了通过 Java 代码创建 MySQL 数据库的 Java 代码示例。你还将学习如何创建 MySQL 表并填充该表。

第二节包含了允许你处理基于 JSON 数据的 Java 代码示例。你将学习如何为 JSON 数据创建表，如何将 JSON 数据插入到该表中，然后如何检索这些数据，所有操作都由 Java 代码完成。

第三节包含了允许你处理基于 XML 数据的 Java 代码示例。你将学习如何为 XML 数据创建表，如何将 XML 数据插入到该表中，然后如何获取这些数据，所有操作都由 Java 代码完成。

## 使用 Java 操作 MySQL

用于 MySQL（以及其他数据库）的 Java 代码需要一个包含连接数据库和执行 SQL 语句相关类的 `JAR` 文件。设置步骤包括为你的电脑下载 Java、下载 `JDBC` 驱动文件以及更新 `CLASSPATH` 环境变量。

### 执行设置步骤

用于 Java 与数据库通信的 `JAR` 文件被称为 `JDBC` 驱动程序，适用于 MySQL 的 `JAR` 文件可以在此处下载：

<https://dev.mysql.com/downloads/connector/j/>

**步骤 1：**下载、解压缩适用于你平台的驱动文件，并将 `JAR` 文件 `mysql-connector-java-8.0.24.jar` 放置在方便的位置。注意，该 `JAR` 文件位于解压缩驱动文件的一个子目录下。

**步骤 2：**更新 `CLASSPATH` 环境变量，如下所示：

```bash
export CLASSPATH=$CLASSPATH:.:mysql-connector-java-8.0.24.jar:
```

如果 `JAR` 文件和编译后的 Java 类位于同一个目录，则前面的代码段可以正常工作。

建议：如果你熟悉基础 shell 脚本，可以将前面的 `export` 代码段放置在一个 shell 脚本中，每需要设置 `CLASSPATH` 环境变量时通过 `source`（“dot”）命令来加载该脚本。

## 在 Java 中创建 MySQL 数据库

本节包含用于创建 `mytools` 数据库的 Java 代码示例。如果你已经导入了 `mytools` 数据库，请修改列表 5.1 中 `URL` 变量的值以指定不同的数据库。访问 MySQL 数据库的 Java 代码示例中需要更新的变量限于 `URL`、`USER` 和 `PASS`。

列表 5.1 显示了 Java 文件 `CreateDataBase.java` 的内容，该文件演示了如何在 Java 中创建 MySQL 数据库。

**列表 5.1：`CreateDataBase.java`**

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

public class CreateDataBase
{
   // specify the URL and username/password to access MySQL
   // the URL specifies the mytools database that already exists:
   static final String URL  = "jdbc:mysql://localhost/mytools";
   static final String USER = "root";
   static final String PASS = "yourpassword";

   public static void main(String[] args)
   {
      // Open a connection
      try(Connection conn =
         DriverManager.getConnection(URL, USER, PASS);

         Statement stmt = conn.createStatement();
      ) {
         String sql = "CREATE DATABASE mytools";
         stmt.executeUpdate(sql);
         System.out.println("Database created");
      } catch (SQLException e) {
         e.printStackTrace();
      }
   }
}
```

列表 5.1 以几个 `import` 语句开始，指定了位于 JDBC JAR 文件中的 Java 类，该文件也包含在 `CLASSPATH` 环境变量中（否则代码将无法成功编译）。

下部分代码初始化了字符串变量 `URL`、`USER` 和 `PASS`。将 `mytools` 替换为你自己的数据库（现有数据库或新数据库），并为 `PASS` 指定正确的值。

列表 5.1 的后续部分是 `main()` 方法，它包含一个 `try/catch` 块，在其中建立了数据库连接，并将字符串变量 `sql` 初始化为创建 `mytools` 数据库的 SQL 语句。如果数据库创建成功，则会打印消息；如果发生错误，则 `catch()` 块将显示描述所遇错误的堆栈跟踪。运行列表 5.1 中的代码，你将看到以下输出：

```text
Database created
```

如果 `mytools` 数据库已经存在，或者你多次运行列表 5.1，你将看到以下输出：

```text
java.sql.SQLException: Can't create database 'mytools'; database exists
```

在这种情况下，你有两个选择：

1. 手动删除数据库。
2. 在 Java 中执行 SQL 语句来删除数据库。

你可以通过在列表 5.1 中创建数据库的代码块**之前**插入以下 Java 代码段来执行选项 #2：

```java
String drop1 = "DROP DATABASE IF EXISTS mytools";
stmt.executeUpdate(drop1);
```

注意：在删除此数据库之前，确保已将 `mytools` 数据库导出到 SQL 文件。

## 在 Java 中创建 MySQL 表

列表 5.2 显示了文件 `CreateTable.java` 的内容，该文件演示了如何在 Java 中创建 MySQL 表。

**列表 5.2：`CreateTable.java`**

```java
// downloaded JAR file contains the following Java classes:
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

public class CreateTable
{
   // specify the URL and username/password to access MySQL
   // the URL specifies the mytools database that already exists:
   static final String URL  = "jdbc:mysql://localhost/mytools";
   static final String USER = "root";
   static final String PASS = "yourpassword";

   public static void main(String[] args)
   {
      // Step 1: open a connection:
      try(Connection conn =
         DriverManager.getConnection(URL, USER, PASS);

         Statement stmt = conn.createStatement();
      ) {
          // Step 2: drop the table if it exists: otherwise the
          // code will fail during subsequent invocations with
          // an error message that table 'friends' already exists
          String sql1 = "DROP TABLE IF EXISTS FRIENDS ";

          // Step 3: SQL to create the table FRIENDS:
          String sql2 = "CREATE TABLE FRIENDS " +
                   "(id INTEGER not NULL, " +
                   " fname VARCHAR(100), " +
                   " lname VARCHAR(100), " +
                   " height INTEGER, " +
                   " PRIMARY KEY ( id ))";

          // Step 4: execute both SQL statements:
         stmt.executeUpdate(sql1);
         stmt.executeUpdate(sql2);
         System.out.println("Created table FRIENDS in database");
      } catch (SQLException e) {
         e.printStackTrace();
      }
   }
}
```

列表 5.2 以几个 `import` 语句开始，指定了位于 JDBC JAR 文件中的 Java 类，该文件也包含在 `CLASSPATH` 环境变量中（否则代码将无法成功编译）。

下部分代码初始化了字符串变量 `URL`、`USER` 和 `PASS`。你需要将 `mytools` 替换为你自己的数据库（现有数据库或新数据库），并为 `PASS` 指定正确的值。

列表 5.2 的后续部分是 `main()` 方法，它包含一个 `try/catch` 块，在其中建立了数据库连接，并将字符串变量 `sql1` 初始化为删除 `friends` 表的 SQL 语句。第三步将字符串变量 `sql2` 初始化为创建 `friends` 表的 SQL 语句。

第四步执行字符串变量 `sql1` 和 `sql2` 中的 SQL 代码。如果发生错误，则 `catch()` 块将显示描述所遇错误的堆栈跟踪。运行列表 5.2 中的代码，你将看到以下输出：

```text
Created table FRIENDS in database
```

注意，JDBC JAR 文件中的旧版本代码需要显式关闭数据库连接，而这一步现在是自动完成的。

## 在 Java 中向 MySQL 表插入数据

列表 5.3 显示了文件 `InsertData.java` 的内容，该文件演示了如何向上一节创建的 `friends` 表中插入数据。



## 在 Java 中向 MySQL 表插入数据

`Listing 5.3` 显示了 `InsertData.java` 文件的内容，该文件说明了如何通过 Java 向 MySQL 表插入数据。

```java
 // 下载的 JAR 文件包含以下 Java 类：
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

public class InsertData
{
   // 指定访问 MySQL 的 URL 和用户名/密码
   // URL 指定了已经存在的 mytools 数据库：
   static final String URL  = "jdbc:mysql://localhost/mytools";
   static final String USER = "root";
   static final String PASS = "yourpassword";

   public static void main(String[] args)
   {
      String sql = "";

      // 步骤 1: 开启数据库连接：
      try(Connection conn =
              DriverManager.getConnection(URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {
         // 步骤 2: 执行插入数据的 SQL 语句
         // 你必须确保 ID 值是唯一的
         // 否则你将看到以下类型的错误：
         // Duplicate entry '100' for key 'friends.PRIMARY'
         // 解决方案之一是删除 FRIENDS 表中的所有的行
         // 但你必须格外小心

         // 步骤 2: 从 FRIENDS 中删除 SQL：
         String del1 = "DELETE FROM FRIENDS";
         stmt.executeUpdate(del1);

         sql = "INSERT INTO FRIENDS VALUES(100,'Jane','Jones',170)";
         stmt.executeUpdate(sql);

         sql = "INSERT INTO FRIENDS VALUES(200,'Dave','Smith',160)";
         stmt.executeUpdate(sql);

         sql = "INSERT INTO FRIENDS VALUES(300,'Jack','Stone',180)";
         stmt.executeUpdate(sql);

         System.out.println("Inserted 3 records into FRIENDS table");
      } catch (SQLException e) {
         e.printStackTrace();
      }
   }
}
```

`Listing 5.3` 以几个 `import` 语句开头，指定了包含 `java.sql` 类的 JAR 文件中的 Java 类，该 JAR 文件也包含在 `CLASSPATH` 环境变量中（否则代码将无法成功编译）。

下段代码初始化了字符串变量 `URL`、`USER` 和 `PASS`。你必须将 `mytools` 替换为你自己的数据库（现有数据库或新数据库），并为 `PASS` 指定正确的值。

`Listing 5.2` 的下半部分是 `main()` 方法，它包含一个 `try/catch` 块，在该块中建立了数据库连接，并将字符串变量 `del1` 初始化为用于删除 `friends` 表中行的 SQL 语句。

下一步使用一个用于向 `friends` 表中插入行数据的 SQL 语句来初始化字符串变量 `sql`。此步骤使用不同的数据值又执行了两次。运行 `Listing 5.3` 中的代码，你将看到以下输出（Java 代码执行了三次）：

```
 java InsertData
Inserted 3 records into FRIENDS table...

java InsertData
Inserted 3 records into FRIENDS table...

java InsertData
Inserted 3 records into FRIENDS table...
```

## 在 Java 中删除数据和删除 MySQL 表

`Listing 5.4` 显示了 `DeleteData.java` 文件的内容，该文件说明了如何通过 Java 从表中删除数据以及如何通过 Java 删除表。

**LISTING 5.4: DeleteDataDrop.java**

```java
 // 下载的 JAR 文件包含以下 Java 类：
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

public class DeleteDataDrop
{
   // 指定访问 MySQL 的 URL 和用户名/密码
   // URL 指定了已经存在的 mytools 数据库：
   static final String URL  = "jdbc:mysql://localhost/mytools";
   static final String USER = "root";
   static final String PASS = "yourpassword";

   public static void main(String[] args)
   {
      String sql = "";

      // 步骤 1: 开启数据库连接：
      try(Connection conn =
              DriverManager.getConnection(URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {
         // 步骤 2: 删除 FRIENDS 中的一部分行：
         System.out.println("Deleting one row from FRIENDS");
         String del1 = "DELETE FROM FRIENDS WHERE id = 100";
         stmt.executeUpdate(del1);

         // 步骤 3: 删除 FRIENDS 中的所有行：
         System.out.println("Deleting all rows from FRIENDS");
         String del2 = "DELETE FROM FRIENDS";
         stmt.executeUpdate(del2);

         // 步骤 3: 清空 FRIENDS 表：
         System.out.println("Truncating table FRIENDS");
         String del3 = "TRUNCATE FRIENDS";
         stmt.executeUpdate(del3);

         // 步骤 4: 删除 FRIENDS 表：
         System.out.println("Dropping table FRIENDS");
         String del4 = "DROP TABLE FRIENDS";
         stmt.executeUpdate(del4);
      } catch (SQLException e) {
         e.printStackTrace();
      }
   }
}
```

`Listing 5.4` 以几个 `import` 语句开头，指定了位于 JDBC JAR 文件中的 Java 类，该文件也包含在 `CLASSPATH` 环境变量中（否则代码将无法成功编译）。

下段代码初始化了字符串变量 `URL`、`USER` 和 `PASS`。你必须将 `mytools` 替换为你自己的数据库（现有数据库或新数据库），并为 `PASS` 指定正确的值。

`Listing 5.4` 的下半部分是 `main()` 方法，它包含一个 `try/catch` 块，在该块中建立了数据库连接，并将字符串变量 `del1` 初始化为删除 `id` 值等于 100 的 `friends` 表行的 SQL 语句。下一个代码块使用用于删除 `friends` 表中*所有*行的 SQL 语句初始化字符串变量 `del2`。

下一段代码块使用用于清空 `friends` 表的 SQL 语句初始化字符串变量 `del3`。最后，最后一段代码块使用用于删除 `friends` 表的 SQL 语句初始化字符串变量 `del4`。运行 `Listing 5.4` 中的代码，你将看到以下输出：

```
 Deleting one row from FRIENDS
Deleting all rows from FRIENDS
Truncating table FRIENDS
Dropping table FRIENDS
```

## 在 Java 中从 MySQL 表查询数据

`Listing 5.5` 显示了 `SelectData.java` 文件的内容，该文件说明了如何通过 Java 从 `friends` 表查询数据。

```java
 // the downloaded JAR file contains the following Java classes:
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

public class SelectData
{
   // specify the URL and username/password to access MySQL
   // the URL specifies the mytools database that already exists:
   static final String URL  = "jdbc:mysql://localhost/mytools";
   static final String USER = "root";
   static final String PASS = "yourpassword";

   public static void main(String[] args)
   {
      String sql1,sql2 = "";

      // Step 1: open a database connection:
      try(Connection conn =
              DriverManager.getConnection(URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {

         // Step 2: Execute SQL statement to select data:
         System.out.println("Selecting one row from FRIENDS table");
         sql1 = "SELECT * FROM FRIENDS WHERE id = 100";
         ResultSet rs1 = stmt.executeQuery(sql1);

         while(rs1.next()){
            //Display values
            System.out.print("id: " + rs1.getInt("id"));
            System.out.print(", fname: " + rs1.getString("fname"));
            System.out.print(", lname: " + rs1.getString("lname"));
            System.out.println(", height: " + rs1.getInt("height"));
         }

         // Step 3: Execute SQL statement to select data:
         System.out.print("\n");
         System.out.println("Selecting all rows from FRIENDS table");
         sql2 = "SELECT * FROM FRIENDS";
         ResultSet rs2 = stmt.executeQuery(sql2);

         while(rs2.next()){
            //Display values
            System.out.print("id: " + rs2.getInt("id"));
            System.out.print(", fname: " + rs2.getString("fname"));
            System.out.print(", lname: " + rs2.getString("lname"));
            System.out.println(", height: " + rs2.getInt("height"));
         }
      } catch (SQLException e) {
         e.printStackTrace();
      }
   }
}
```

`Listing 5.5` 包含几个导入语句，指定了位于 JDBC JAR 文件中的 Java 类，该文件也包含在 `CLASSPATH` 环境变量中（否则代码将无法成功编译）。

下部分代码初始化了字符串变量 `URL`、`USER` 和 `PASS`。你必须将 `mytools` 替换为你自己的数据库（现有数据库或新数据库），并为 `PASS` 指定正确的值。

`Listing 5.2` 的接下来的部分是 `main()` 方法，它包含一个 `try/catch` 块，在该块中建立了数据库连接，并将字符串变量 `del1` 初始化为用于删除 `friends` 表中行的 SQL 语句。下一步使用用于向 `friends` 表插入一行数据的 SQL 语句初始化了字符串变量 `sql`。此步骤使用不同的数据值又多多执行了两次。

运行 `Listing 5.5` 中的代码，你将看到以下输出（Java 代码执行了三次）：

```
 Selecting one row from FRIENDS table
id: 100, fname: Jane, lname: Jones, height: 170

Selecting all rows from FRIENDS table
id: 100, fname: Jane, lname: Jones, height: 170
id: 200, fname: Dave, lname: Smith, height: 160
id: 300, fname: Jack, lname: Stone, height: 180
```

## 在 Java 中更新 MySQL 表中的数据

`Listing 5.6` 显示了文件 `UpdateData.java` 的内容，说明了如何通过 Java 更新 `friends` 表中的数据。

**Listing 5.6: UpdateData.java**



```java
// the downloaded JAR file contains the following Java classes:
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

public class InsertData
{
   // specify the URL and username/password to access MySQL
   // the URL specifies the mytools database that already exists:
   static final String URL  = "jdbc:mysql://localhost/mytools";
   static final String USER = "root";
   static final String PASS = "yourpassword";

   public static void main(String[] args)
   {
      // Step 1: open a database connection:
      try(Connection conn =
              DriverManager.getConnection(URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {
         // Step 2: Execute SQL statements to update data
         String upd1 = "UPDATE FRIENDS SET lname = 'Anderson' WHERE id = 100";
         stmt.executeUpdate(upd1);
         System.out.println("Updated last name for row with id = 100");
      } catch (SQLException e) {
         e.printStackTrace();
      }
   }
}
```

`Listing 5.6` 开头包含几个导入语句，指定了位于 JDBC JAR 文件中的 Java 类，该文件也包含在 `CLASSPATH` 环境变量中。

下一部分代码初始化了字符串变量 `URL`、`USER` 和 `PASS`。你必须将 `mytools` 替换为你自己的数据库（现有数据库或新数据库），并为 `PASS` 指定正确的值。

`Listing 5.2` 的接下来的部分是 `main()` 方法，它包含一个 `try/catch` 块，在该块中建立了数据库连接，并将字符串变量 `del1` 初始化为用于删除 friends 表中行的 SQL 语句。下一步使用用于向 friends 表插入一行数据的 SQL 语句初始化了字符串变量 `sql`。此步骤使用不同的数据值又多执行了两次。

运行 `Listing 5.5` 中的代码，你将看到以下输出（Java 代码执行了三次）：

```
Updated last name for row with id = 100
```

运行 `SelectData` 代码以确认更新的数据：

```
Selecting one row from FRIENDS table
id: 100, fname: Jane, lname: Jones, height: 170

Selecting all rows from FRIENDS table
id: 100, fname: Jane, lname: Jones, height: 170
id: 200, fname: Dave, lname: Smith, height: 160
id: 300, fname: Jack, lname: Stone, height: 180
```

### 在 JSON、MySQL 和 Java 中工作

本节包含一个向 MySQL 表插入 JSON 数据的 Java 代码示例，以及如何从此类表中检索 JSON 数据。MySQL 支持 JSON 类型，我们将使用它来定义 MySQL 表的其中一个属性。

简单来说，JSON 数据由键值对组成，其示例如下：

```json
{"fname":"Dave", "lname":"Stone", "age":35, "city":"NY"}
```

使用数组（即方括号）来指定一组 JSON 字符串，其示例如下：

```json
[
  {"fname":"Jane", "lname":"Smith", "age":30, "city":"NY"}
  {"fname":"Dave", "lname":"Stone", "age":35, "city":"NY"}
]
```

`Listing 5.7` 显示了文件 `json_table.sql` 的内容，说明了如何直接在 SQL 中创建基于 JSON 的 MySQL 表。

```sql
drop table if exists json1;
CREATE TABLE json1 ( id integer, data json);
INSERT INTO json1 VALUES(100,'{"fname": "Jane", "lname": "Jones"}');
INSERT INTO json1 VALUES(200,'{"fname": "Dave", "lname": "Smith"}');
INSERT INTO json1 VALUES(300,'{"fname": "Jack", "lname": "Stone"}');
```

### 在 Java 中从 MySQL 表中查询 JSON 数据

本节包含一个从包含 JSON 数据的 MySQL 表中查询数据的 Java 代码示例。如果你尚未这样做，请确保你已经在 `Listing 5.7` 中创建了 MySQL 表 `json1` 并向该表填充了 JSON 数据。

`Listing 5.8` 显示了文件 `SelectJSONTable.java` 的内容，说明了如何从包含 JSON 数据的 MySQL 表中查询数据。

```java
// 下载的 JAR 文件包含以下 Java 类：
importimport java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

public class SelectSONData
{
   // 指定访问 MySQL 的 URL 和用户名/密码
   // URL 指定了已存在的 mytools 数据库：
   static final String URL  = "jdbc:mysql://localhost/mytools";
   static final String USER = "root";
   static final String PASS = "yourpassword";

   public SelectJSONData() {}

   public static void checkJSon()
   {
      // CREATE TABLE json1 ( id integer, data json);
      try{Connection conn =
              DriverManager.getConnection(URL, USER, PASS);
         String query = "SELECT * FROM json1";
         PreparedStatement preparedStatement =
                            conn.prepareStatement(query);
         preparedStatement.execute();
         ResultSet rs = preparedStatement.executeQuery();
         while (rs.next()) {
            System.out.println(rs.getString("data"));
         }
      } catch (SQLException e) {
         e.printStackTrace();
      }
   }

   public static void main(String[] args)
   {
      checkJSon();
   }
}
```

`Listing 5.8` 开始于几个导入语句，这些语句指定了位于 JDBC JAR 文件中的 Java 类，该文件也包含在 `CLASSPATH` 环境中（否则代码将无法成功编译）。

下部分代码初始化了字符串变量 `URL`、`USER` 和 `PASS`。你必须将 `mytools` 替换为你自己的数据库（现有数据库或新数据库），并为 `PASS` 指定正确的值。

`Listing 5.8` 的后续部分是 `main()` 方法，它包含一个用于建立数据库连接的 try/catch 块。字符串变量 `query` 初始化为一个 SQL 语句，用于选择 `Listing 5.7` 中定义的 `json1` 表中的行（请确保先运行了该代码）。

下一步初始化了变量 `preparedStatement`，其 `execute()` 方法在随后的代码段中作为初始化步骤调用。接下来，变量 `rs` 初始化为调用变量 `preparedStatement` 的 `executeQuery()` 方法返回的结果集。随后，执行一个循环来获取 `data` 属性的内容并打印其值，如下所示：

```java
while (rs.next()) {
   System.out.println(rs.getString("data"));
}
```

运行 `Listing 5.8` 中的代码，你将看到以下输出：

```json
{"fname": "Jane", "lname": "Jones"}
{"fname": "Dave", "lname": "Smith"}
{"fname": "Jack", "lname": "Stone"}
```

## 与 XML、MYSQL 和 JAVA 交互

在数据库中处理 XML 有多种方法，此处列出了其中一些方法（本章仅探讨了第一种方案）：

- 将 XML 读取为字符串并通过 SAX 或 DOM 进行解析。
- 使用 `CLOB` 数据类型处理 XML 文档。
- 使用 `JAXB`（Java 和 XML 绑定）。
- 使用 `ORM`（对象关系映射）。
- 使用原生 XML 数据库。

本章的后续部分包含 Java 代码示例，这些示例从存储为文件的 XML 文档内容创建字符串，然后将这些字符串插入 MySQL 表的字符列中。另一个 Java 代码示例检索每个基于 XML 的字符串，然后解析这些字符串以创建 XML 文档。

通常情况下，涉及 MySQL、XML 文档和 Java 的典型操作如下：

- 将 XML 文档插入 MySQL 表
- 在 MySQL 表中读取 XML 文档
- 从 MySQL 表中删除 XML 文档
- 在 MySQL 表中更新 XML 文档

然而，Java 前述的 CRUD 操作需要对文档对象模型（`DOM`）有更深入的理解，这是一个基于树的结构，包含了 XML 文档中的所有数据（和元数据）。类比，每你在浏览器会话中导航到一个 HTML 页面时，该 HTML 页的内容在内存中也被表示为 `DOM` 结构。如果你真的想深入研究 `DOM` 结构的细节，可以在线上搜索更多信息。

### 什么是 XML？

简单来说，基于 XML 的数据由角括号内的文本组成，这些文本指定了标签名称。这是一个简单的示例：

```xml
<fname>Dave</fname>
```

以下代码段展示了如何指定一个包含多个标签的 XML 标签（缩进是可选的，便于阅读）：

```xml
<person>
  <fname>Dave</fname>
  <fname>Smith</fname>
</person>
```

尽管你可以指定任意深度的嵌套 XML 标签，但本章中的 XML 文档仅嵌套了一层。事实上，`Listing 5.9` 显示了 XML 文档 `friends.xml` 的内容。

**列表 5.9：`friends.xml`**

```xml
<?xml version="1.0"?>
<friends>
  <friend>
    <fname>Jane</fname>
    <lname>Jones</lname>
    <height>170</height>
  </friend>
  <friend>
    <fname>Dave</fname>
    <lname>Smith</lname>
    <height>160</height>
  </friend>
  <friend>
    <fname>Jack</fname>
    <lname>Stone</lname>
    <height>180</height>
  </friend>
</friends>
```

需要记住的一点是，XML 将一切都视为文本，这意味着 XML 是一种文本标记语言，而 JSON（后文讨论）是一种数据格式。尽管 XML 的内容涉及标签，但 XML 的一个优势是存在 XML Schema 用于验证文档，这将在下一节简要介绍。

### 什么是 XML Schema？

XML Schema 是一个指定 XML 结构的基于 XML 的文档。例如，让我们创建一个 XML Schema，约束“friend”文档具有以下结构：

- 一个名字（`fname` 标签）
- 零或多个中间名（`mname` 标签）
- 一个姓（`lname` 标签）
- 一个高度（`height` 标签）

如你所见，以下 XML 片段符合上述结构（一个名字、零中间名、一个姓、一个高度）：

```xml
<friend>
  <fname>Jane</fname>
  <lname>Jones</lname>
  <height>170</height>
</friend>
```

以下 XML 片段符合之前的结构（一个名字、两个中间名、一个姓、一个高度）：

```xml
<friend>
  <fname>Billy</fname>
  <mname>Bob</mname>
  <mname>James</mname>
  <lname>Callaway</lname>
  <height>170</height>
</friend>
```

然而，以下 XML 片段不符合之前的结构，因为存在粗体显示的标签：

```xml
<friend>
  <title>Mr</title>
  <fname>Billy</fname>
  <lname>Callaway</lname>
  <height>170</height>
</friend>
```

### XML Schema 在什么情况下有用？

在需要在应用程序之间传输字符字符串的情况下，XML Schema 非常有价值。例如，一个跟踪租赁设备的应用程序可能包含非常复杂的依赖关系，在 Web 应用程序中使用 JavaScript 执行这些操作会非常繁琐。然而，一种解决方案是通过拼接 Web 上的所有字段来构造字符串，然后将该字符串传递给将其转换为 XML 文档的应用程序。

下一步是验证动态构造的 XML 文档是否符合 XML Schema，之后可以将 XML 文档发送到另一个应用程序进行额外的处理步骤。如有必要，可以创建一个多次执行上述序列的执行流水线。如果在验证步骤期间发生错误，则可以分析该步骤中的 XML 文档以找到错误原因，然后解决错误。

XML 文档可能非常巨大，其相关的 XML Schema（架构）可能具有非常复杂的结构。例如，XBRL 定义了一个用于业务报告文档的 XML 架构。此外，XML 是一个广泛的话题，有整本书专门讲解 XML。如果你想熟悉 XML 丰富的功能，可以进行在线搜索。

现在你已经对 XML 有了初步了解，让我们来看看如何创建一个 MySQL 表来存储 XML 数据，这将在下一节中进行解释。

## 在 Java 中创建用于 XML 数据的 MySQL 表

本节包含一个 Java 代码示例，用于创建一个包含基于 XML 数据的 MySQL 表。MySQL 表中也可以指定 XML 数据类型；但本节中的数据库表使用了你在之前章节的 SQL 语句中使用过的属性。

`Listing 5.10` 显示了 `CreateTableForXMLData.java` 的内容，该程序创建一个填充来自 XML 文档数据的 MySQL 表。

### 列表 5.10：`CreateTableForXMLData.java`



```java
import java.io.File;
import java.io.IOException;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

import javax.xml.parsers.DocumentBuilder;
import javax.xml.parsers.DocumentBuilderFactory;
import javax.xml.parsers.ParserConfigurationException;

import org.w3c.dom.Document;
import org.xml.sax.SAXException;

// deprecated: try { Class.forName("com.mysql.jdbc.Driver"); }

public class CreateTableForXMLData
{
   static {
     try {
       Class.forName("com.mysql.cj.jdbc.Driver");
     } catch(ClassNotFoundException ex) {
       System.err.println("Driver not found: "+ex.getMessage());
     }
   };

   // 指定访问 MySQL 的 URL 和用户名/密码
   // URL 指定了已存在的 mytools 数据库：
   static final String URL  = "jdbc:mysql://localhost/mytools";
   static final String USER = "root";
   static final String PASS = "yourpassword";

   public CreateTableForXMLData() {}

   public static void createXMLTable()
   {
      try(Connection conn =
              DriverManager.getConnection(URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {
        // 步骤 1: 如果 friends 表存在则删除：
        conn.createStatement()
            .execute("DROP TABLE IF EXISTS friends");
        System.out.println("DROPPED TABLE friends\n");

        // 步骤 2: 如果 friends 表存在则创建：
        conn.createStatement()
            .execute("CREATE TABLE friends (\n" +
                 " id INTEGER PRIMARY KEY auto_increment,\n" +
                 " fname  VARCHAR(25) NOT NULL,\n" +
                 " lname  VARCHAR(25) NOT NULL,\n" +
                 " height INTEGER)\n");
        System.out.println("CREATED TABLE friends\n");
      } catch (SQLException e) {
         e.printStackTrace();
      }
   }

   public static void main(String[] args)
   {
      createXMLTable();
   }
}
```

Listing 5.10 从几个 `import` 语句开始，这些语句指定了位于 JDBC JAR 文件中的 Java 类，该文件也包含在 `CLASSPATH` 环境变量中（否则代码将无法成功编译）。

下部分代码初始化了字符串变量 `URL`、`USER` 和 `PASS`。你必须将 `mytools` 替换为你自己的数据库（现有数据库或新数据库），并为 `PASS` 指定正确的值。

Listing 5.10 的后续部分是 `main()` 方法，它包含一个 `try/catch` 块，在其中通过数据库连接初始化变量 `conn`。下一个代码片段执行了被称为“方法链”的操作。这种技术消除了对中间变量的需求。在这种情况下，连续调用两个方法来删除 `friends` 表，如下：

```java
conn.createStatement()
   .execute("DROP TABLE IF EXISTS friends");
```

接下来的代码片段也使用方法链来定义 `friends` 表的结构，然后执行 SQL 语句实际创建此表。运行 Listing 5.10 中的代码，你将看到以下输出（代码运行了两次）：

```text
DROPPED TABLE friends

CREATED TABLE friends
```

## 在 Java 中读取 XML 文档

本节向你展示如何在不进行数据库连接的情况下读取 XML 文档的内容。Listing 5.11 显示了文件 `ReadXMLDocument.java` 的内容，说明了如何读取 XML 文档 `friends.xml` 的内容。

### 列表 5.11：ReadXMLDocument.java

```java
import java.io.File;
import java.io.IOException;
import javax.xml.parsers.DocumentBuilder;
import javax.xml.parsers.DocumentBuilderFactory;
import javax.xml.parsers.ParserConfigurationException;
import org.w3c.dom.Document;
import org.xml.sax.SAXException;

public class ReadXMLDocument
{
   public ReadXMLDocument() {}

   public static void readXMLFile()
   {
      String fileName = "friends.xml";
      File file = new File(fileName);
      System.out.println("Reading XML file "+fileName);

      try {
        DocumentBuilderFactory factory = DocumentBuilderFactory.newInstance();
        DocumentBuilder builder = factory.newDocumentBuilder();
        Document xmlDoc = builder.parse(file);
      } catch (SAXException e) {
         e.printStackTrace();
      } catch (ParserConfigurationException pce) {
         pce.printStackTrace();
      } catch (IOException ioe) {
         ioe.printStackTrace();
      }
   }

   public static void main(String[] args)
   {
      readXMLFile();
   }
}
```

Listing 5.11 从几个 `import` 语句开始，这些语句指定了操作 XML 文档所需的 Java 类。Listing 5.11 的后续部分是 `main()` 方法，它初始化字符串 `fileName`，然后用 `friends.xml` 文档的内容初始化变量 `file`。

注意，代码**并没有**显示 XML 文档的内容：它的目的仅仅是说明如何创建内存结构。运行 Listing 5.11 中的代码，你将看到以下输出：

```text
Reading XML file friends.xml
```

## 在 Java 中作为字符串读取 XML 文档

Listing 5.12 显示了文件 `ReadXMLAsString.java` 的内容，说明了如何在 Java 中将 XML 文档读取为字符串。

### 列表 5.12：ReadXMLAsString.java

```java
import java.io.File;
import java.lang.Exception;
import java.util.Scanner;

public class ReadXMLAsString
{
   public ReadXMLAsString() {}

   public static String readXMLFile(String fileName)
   {
      String contents = "";

      try {
         File file = new File(fileName);
         System.out.println("Reading XML file "+fileName);

         Scanner scanner = new Scanner(file).useDelimiter("\\n");
         while(scanner.hasNext()) {
           contents += scanner.next();
         }
      } catch (Exception ioe) {
         ioe.printStackTrace();
      }
      return contents;
   }

   public static void main(String[] args)
   {
      String fileName = "friends.xml";
      String xmlString = readXMLFile(fileName);
      System.out.println("File contains: "+xmlString);
   }
}
```

Listing 5.12 包含几个导入语句，用于将 XML 文档的内容作为简单文件读取：不需要任何 DOM 相关的结构。Listing 5.12 的后续部分定义了 `readXMLFile()` 方法，该方法包含一个 `try/catch` 块用于从文件系统读取文件。核心思想是用文件 `friends.xml` 的内容初始化变量 `scanner`。接部分代码是一个循环，它逐行遍历文件，并将每行附加到字符串变量 `contents`（在代码早早已初始化），所示：

```java
while(scanner.hasNext()) {
  contents += scanner.next();
}
```

Listing 5.12 的最后部分是 `main()` 方法，它将变量 `filename` 初始化为 `friends.xml`，然后用 `readXMLFile()` 方法返回的字符串初始化变量 `xmlString`。运行 Listing 5.12 中的代码，你将看到以下输出：

```text
Reading XML file friends.xml
File contains: <?xml version="1.0"?><friends>  <friend>    <fname>Jane</
fname>    <lname>Jones</lname>    <height>170</height>  </friend>  
<friend>    <fname>Dave</fname>    <lname>Smith</lname>    <height>160</
height>  </friend>  <friend>    <fname>Jack</fname>    <lname>Stone</
lname>    <height>180</height>  </friend></friends>
```

## 在 Java 中向 MySQL 表插入 XML 数据

本节包含一个 Java 代码示例，将 XML 文档读取到字符串，然后将该字符串插入 MySQL 表中。如果你还没有这样做，请确保你已经在 Listing 5.13 中创建了 MySQL 表 `friends2`。

### Listing 5.13：create_xml_string_table.sql

```sql
DROP TABLE IF EXISTS FRIENDS2;
CREATE TABLE FRIENDS2(id INTEGER not NULL, xml_str VARCHAR(1000),
PRIMARY KEY (id))
```

Listing 5.14 显示了文件 `InsertXMLString.java` 的内容，它说明了如何将基于 XML 的数据插入 MySQL 表。

### Listing 5.14：InsertXMLString.java



```java
// 下载的 JAR 文件包含以下 Java 类：
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.Scanner;
// deprecated: try { Class.forName("com.mysql.jdbc.Driver"); }

public class InsertXMLString
{
   static {
     try {
       Class.forName("com.mysql.cj.jdbc.Driver");
     } catch(ClassNotFoundException ex) {
       System.err.println("Driver not found: "+ex.getMessage());
     }
   };

   // 指定访问 MySQL 的 URL 和用户名/密码
   // URL 指定了已存在的 mytools 数据库：
   static final String URL  = "jdbc:mysql://localhost/mytools";
   static final String USER = "root";
   static final String PASS = "yourpassword";

   public InsertXMLString() {}

   public static String readXMLFile(String fileName)
   {
      String contents = "";

      try {
         File file = new File(fileName);
         System.out.println("Reading XML file "+fileName);

         Scanner scanner = new Scanner(file).useDelimiter("\\n");
         while(scanner.hasNext()) {
           contents += scanner.next();
         }
      } catch (Exception ioe) {
         ioe.printStackTrace();
      }
      System.out.println("File contains: "+contents);
      return contents;
   }

   public static void insertString(String xmlString)
   {
      // Step 1: 打开数据库连接：
      try(Connection conn =
              DriverManager.getConnection(URL, USER, PASS);
         Statement stmt = conn.createStatement();
      ) {
         // Step 2: 执行插入数据的 SQL 语句
         // 并且必须确保 ID 值是唯一的
         // 否则你将看到如下类型的错误：
         // Duplicate entry '100' for key 'friends2.PRIMARY'
         // 解决方案涉及删除 FRIENDS 表
         // 中所有的行，但你必须小心
         // Step 2: 从 FRIENDS 中删除行的 SQL：
         String del1 = "DELETE FROM FRIENDS2 ";
         stmt.executeUpdate(del1);

         String sql = "INSERT INTO FRIENDS2 VALUES(100,"+"'"+xmlString+"')";
// System.out.println("--------------\n");
// System.out.println("===> sql:"+sql);
// System.out.println("--------------\n");

         stmt.executeUpdate(sql);
         System.out.println("Inserted XML string into FRIENDS2");
      } catch (SQLException e) {
         e.printStackTrace();
      }
   }

   public static void main(String[] args)
   {
      String fileName = "friends.xml";
      String xmlString = readXMLFile(fileName);
      insertString(xmlString);
   }
}
```

```java
// 下载的 JAR 文件包含以下 Java 类：
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

public class SelectXMLData
{
   // 指定访问 MySQL 的 URL 和用户名/密码
   // URL 指定了已存在的 mytools 数据库：
   static final String URL  = "jdbc:mysql://localhost/mytools";
   static final String USER = "root";
   static final String PASS = "yourpassword";

   public SelectXMLData() {}

   public static void selectXML()
   {
      int rowCount = 0;

      // CREATE TABLE json1 ( id integer, data json);
      try{Connection conn = DriverManager.getConnection(URL, USER, PASS);
         String query = "SELECT * FROM FRIENDS2";
         PreparedStatement preparedStatement = conn.prepareStatement(query);
         preparedStatement.execute();
         ResultSet rs = preparedStatement.executeQuery();

         while (rs.next()) {
            System.out.println("XML String:");
            System.out.println(rs.getString("xml_str"));
            System.out.println("\n");
            ++rowCount;
         }
         System.out.println("=> ROW COUNT:"+rowCount+"\n");
      } catch (SQLException e) {
         e.printStackTrace();
      }
   }

   public static void main(String[] args)
   {
      selectXML();
   }
}
```

`Listing 5.15` 包含几个 `import` 语句，指定了位于 JDBC JAR 文件中的 Java 类，该文件也包含在 `CLASSPATH` 环境变量中（否则代码将无法成功编译）。

下部分代码初始化了字符串变量 `URL`、`USER` 和 `PASS`。你必须将 `mytools` 替换为你自己的数据库（现有数据库或新数据库），并为 `PASS` 指定正确的值。

`Listing 5.15` 的下一次部分是 `main()` 方法，它包含一个 `try/catch` 块，在其中建立了数据库连接，并将字符串变量 `query` 初始化为用于选择 `friends2` 表中行的 SQL 语句。下部分代码基本上与 `Listing 5.5` 中的代码相同，用于遍历结果集并显示 `xml_str` 属性的内容。运行 `Listing 5.15` 中的代码，你将看到以下输出：

```
XML String:
<?xml version="1.0"?><friends>  <friend>    <fname>Jane</fname>    
<lname>Jones</lname>    <height>170</height>  </friend>  <friend>    
<fname>Dave</fname>    <lname>Smith</lname>    <height>160</height>  
</friend>  <friend>    <fname>Jack</fname>    <lname>Stone</lname>    
<height>180</height>  </friend></friends>

=> ROW COUNT:1
```

### 在 Java 中从 MySQL 表中解析基于 XML 的字符串数据

本节包含一个 Java 代码示例，该示例从包含 XML 数据的 MySQL 表中选择数据。如果你还没有这样做，请确保已在 `Listing 5.13` 中创建了 MySQL 表 `friends2` 并向表中填充了数据。

`Listing 5.16` 显示了 `ParseXMLStringInTable.java` 的内容，说明了如何从 MySQL 表中选择基于 XML 的数据字符串，然后根据每个字符串的内容创建 XML 文档。

*列表 5.16: `ParseXMLStringInTable.java`*

```java
import java.io.StringReader;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.ArrayList;

import javax.xml.parsers.DocumentBuilder;
import javax.xml.parsers.DocumentBuilderFactory;
import javax.xml.parsers.ParserConfigurationException;

import org.w3c.dom.Document;
import org.xml.sax.SAXException;
import org.xml.sax.InputSource;
public class ParseXMLStringInTable
{
   // 指定访问 MySQL 的 URL 和用户名/密码
   // URL 指定了已存在的 mytools 数据库：
   static final String URL  = "jdbc:mysql://localhost/mytools";
   static final String USER = "root";
   static final String PASS = "yourpassword";

   public ParseXMLStringInTable() {}

   public static void parseXMLString(ArrayList arrList)
   {
      System.out.println("=> Parsing Strings as XML");

      try {
        DocumentBuilderFactory factory =
                          DocumentBuilderFactory.newInstance();
        DocumentBuilder builder = factory.newDocumentBuilder();

        // Document xmlDoc = builder.parse(xmlString);
        // 此 parse(String) 尝试打开由 XML 文档第一行
        // 指定的 URI，这会导致此错误：
        // java.net.MalformedURLException: no protocol: <?xml version="1.0"?>
        // 之，使用 InputStream 或 Reader
        for (int row=0; row<arrList.size(); row++)
        {
           String xml = (String)arrList.get(row);
           Document xmlDoc =
              builder.parse(new InputSource(new StringReader(xml)));
           System.out.println("Do something with this XML document...");
        }
      } catch (SAXException e) {
         e.printStackTrace();
      } catch (ParserConfigurationException pce) {
         pce.printStackTrace();
      } catch (Exception ex) {
         ex.printStackTrace();
      }
   }

   public static void selectXML()
   {
      int rowCount = 0;
      ArrayList arrList = new ArrayList();

      try{Connection conn = DriverManager.getConnection(URL, USER, PASS);
         String query = "SELECT * FROM FRIENDS2";
         PreparedStatement preparedStatement = conn.prepareStatement(query);
         preparedStatement.execute();
         ResultSet rs = preparedStatement.executeQuery();

         while (rs.next()) {
            String xmlString = rs.getString("xml_str");
            arrList.add(xmlString);
            ++rowCount;
         }

         // 将每个字符串还原为 XML：
         parseXMLString(arrList);

         System.out.println("=> ROW COUNT:"+rowCount+"\n");
      } catch (SQLException e) {
         e.printStackTrace();
      }
   }

   public static void main(String[] args)
   {
      selectXML();
   }
}
```

### 使用 XML 架构

在本章的早些部分中，你看到了一些结合 MySQL 管理基于 XML 文档的 Java 代码示例。尽管我们指定了一个包含多个 `<friend>` 元素的 XML 文档，但我们并没有对 XML 元素的内容进行约束。

然而，`XML Schemas` 对 XML 文档中元素的允许结构提供了严格控制，例如不仅指定它们的类型，还指定它们出现的频率以及在 XML 元素中的顺序。

例如，我们可以通过以下代码段定义一个 `firstname` 元素，其类型为字符串：

```xml
<xs:element name="firstname" type="xs:string"/>
```

我们可以定义一个 `friend` 元素，它包含两个字符串类型的元素 `fname` 和 `lname`，以及一个名为 `height` 的数值元素，如下所示：

```xml
<?xml version="1.0"?>
<xs:element name="friend">
  <xs:complexType>
    <xs:sequence>
      <xs:element name="fname" type="xs:string"/>
      <xs:element name="lname" type="xs:string"/>
      <xs:element name="height" type="xs:decimal"/>
    </xs:sequence>
  </xs:complexType>
</xs:element>
```



我们可以修改前面的代码块来指定一个可选的中间名，它最多可以出现三次：

```xml
<?xml version="1.0"?>
<xs:element name="friend">
  <xs:complexType>
    <xs:sequence>
      <xs:element name="fname" type="xs:string"/>
      <xs:element name="mname" type="xs:string" minOccurs="0" maxOccurs="3"/>
      <xs:element name="lname" type="xs:string"/>
      <xs:element name="height" type="xs:decimal"/>
    </xs:sequence>
  </xs:complexType>
</xs:element>
```

如果你想指定一个出现任意次数的可选中间名元素，请使用以下代码段：

```xml
<xs:element name="mname" type="xs:string" minOccurs="0" maxOccurs="3"/>
```

`XML Schemas` 有许多功能，包括 XML 元素引用其他 XML 元素的能力，你甚至可以将 XML 元素指定为抽象的（面向对象编程中的含义）。请在线搜索更多关于 `XML Schemas` 的信息。

### 总结

本章首先向你展示了如何编写 Java 代码来管理关系型数据库和关系型表的内容。你看到了如何为你的笔记本进行必要的设置步骤，以便 Java 代码能够正确执行。

接下来，你学习了如何编写 Java 代码来管理 `MySQL` 数据库中基于 JSON 的数据。你看到了如何为 JSON 数据创建表，如何向表中插入数据，以及如何使用 Java 代码检索这些数据。

你还学习了用于处理 XML 文档的 Java 技术，例如基于 SAX 的解析器和基于 DOM 的解析器。最后，你看到了如何编写 Java 代码来管理 `MySQL` 数据库中基于 XML 的数据。

# 第 6 章

## 数据清洗任务

本章讨论了涉及包含各种类型数据的数据集的清洗任务，例如日期、电话号码和货币，这些都有不同的格式。此外，本章中的许多代码示例引用了书中之前章节中讨论的技术。本章自然地过渡到第 7 章，该章节讨论了各种代码示例中的数据清洗。

本章的第一部分简要描述了数据清洗，随后是针对 `MySQL` 数据库表中数据的清洗任务示例。具体来说，你将看到如何将 `NULL` 值替换为 `0`，如何用平均值替换 `NULL` 值，如何用单个值替换多个值，如何处理不匹配的属性值，以及如何将字符串转换为日期值。

本章的第二部分向你展示如何使用 `sed` 命令行工具将 CSV 文件中的多个分隔符替换为单个分隔符。你还将看到如何使用 `awk` 命令行工具重构 CSV 文件，创建一个行具有相同字段数量的文件。

本章的第三部分向你展示如何使用 `awk` 命令行工具处理列数变化的 CSV 文件。`awk` 命令是一门独立的编程语言，在处理文本文件方面具有令人印象深刻的能力。如果你熟悉 `awk` 命令，请阅读包含大量 `awk` 工具代码示例的附录。

本章的第四部分包含了基于 `awk` 的 shell 脚本，向你展示如何将电话号码列表转换为相同格式，以及将日期格式列表转换为相同格式。

本章假设你已经阅读了之前章节中的数据清洗示例。此外，第 7 章也包含一个涉及数据清洗任务的额外代码示例的章节。

### 什么是数据清洗？

数据清洗（Data cleaning），也称为数据净化，是确保数据集的内容完整、正确且通常没有重复的任务。因此，数据清洗的重点是单个文件，而不是合并或转换来自两个或多个文件的数据。数据清洗通常在任何数据转换之前进行。在某些情况下，数据清洗也必须在数据转换之后进行。

例如，假设一个 CSV 文件包含员工相关数据，一个 `MySQL` 表也包含员工相关数据，且都已清理了不一致之处并删除了重复。然而，在将表数据导出到与第一个 CSV 文件合并的 CSV 文件后，可能会出现必须删除的重复项。

顺便说，有多种技术可以确定替换空字段的值，其选择从显而易见的因素到微妙因素不等。有时你可以指定平均值或中位数作为缺失值，但在其他情况下，你需要更复杂的技术。例如，假设一个包含 1000 行的数据集由两类患者组成：健康患者（多数）以及癌症患者。显然，你希望患病的数量尽可能少，这意味着数据集是不平衡的。

不幸的是，机器学习算法在不平衡数据集上可能会产生不准确的结果。此外，基于平均值或中位数生成合成数据可能是风险的。一种更好的技术是 `SMOTE`，它生成在原始集中出现的数据。

作为另一个例子，日期、货币和数字的格式在不同国家之间不同。日期格式示例包括 `YYYY/MM/DD`、`MM/DD/YYYY` 和 `DD/MM/YYYY`（以及其他可能的日期格式）。提到的是，`YYYY/MM/DD` 是日期的 ISO 标准。

数字格式在美国使用逗号 `,` 作为千位符，使用点 `.` 作为小数点（例如 `$1,234.56`），而欧洲使用相反的顺序（例如 `1.234,56`）。取决于涉及的数据集，数据清洗还可以涉及处理各种日期、货币和数字，以确保所有值具有相同的格式。

此外，如果两个 CSV 文件包含不同的日期格式，并且你需要创建一个基于日期列的单个 CSV 文件，那么将存在转换过程，可以是以下之一：

- 将第一种日期格式转换为第二种日期格式
- 将第二种日期格式转换为第一种日期格式
- 将两种格式转换为第三种格式

在财务数据的情况下，你可能还会遇到不同的货币，这涉及到货币对之间的汇率。由于货币汇率会波动，你需要决定用于数据的数据汇率，这可以是以下之一：

- CSV 文件生成日期期间的汇率
- 当前货币汇率
- 其他某种机制

#### 个人称谓的数据清洗

有时候，“暴力破解”方案也是最简单的方案，特别是在涉及字符串时。例如，一个人的头衔可能有无数种拼写方式，涉及许多讨厌的细微差异，因此，知道如何以一种简单、直观且易于扩展额外用例的方法来执行此任务是有好的。例如，在查看下面的解决方案之前，考虑你将如何将以下列表中的每个字符串替换为前缀“Mr,”、“Ms,”或“Mrs”：

```python
Titles = ['mr.','MR','MR.','mister','Mister','Ms','Ms.', 'Mr', 'Mr.','mr',
'MS','MS.','ms','ms.','Mis','miss','miss.','Mrs','Mrs.','mrs','mrs.',
'Madam','madam','ma"am']
```

虽然可以使用 `if/else` 代码块的条件逻辑来解决此任务，但这种方法涉及冗长的代码块。一个更简单易的解决方案是使用 `in` 关键字，所示：

```python
mr_dict={}
ms_dict={}
mrs_dict={}

titles = ['mr.','MR','MR.','mister','Mister','Ms','Ms.', 'Mr', 'Mr.',
'mr','MS','MS.','ms','ms.','Mis','miss','miss.','Mrs','Mrs.','mrs','mrs.',
'Madam','madam','ma"am']

for title in ['Mr','Mr.','mr','mr.','MR','MR.','mister','Mister']:
  mr_dict[title] = "Mr"

for title in ['Ms','Ms.','MS','MS.','ms','ms.','Mis','miss','miss.']:
  ms_dict[title] = "Ms"

for title in ['Mrs','Mrs.','mrs','mrs.','Madam','madam','ma"am']:
  mrs_dict[title] = "Mrs"

print("Mr dictionary: ",mr_dict)
print()
print("Ms dictionary: ",ms_dict)
print()
print("Mrs dictionary:",mrs_dict)
```

运行上述代码块，你将看到以下输出：

```text
Mr dictionary:  {'Mr': 'Mr', 'Mr.': 'Mr', 'mr': 'Mr', 'mr.': 'Mr', 'MR': 'Mr', 'MR.': 'Mr', 'mister': 'Mr', 'Mister': 'Mr'}

Ms dictionary:  {'Ms': 'Ms', 'Ms.': 'Ms', 'MS': 'Ms', 'MS.': 'Ms', 'ms': 'Ms', 'ms.': 'Ms', 'Mis': 'Ms', 'miss': 'Ms', 'miss.': 'Ms'}

Mrs dictionary: {'Mrs': 'Mrs', 'Mrs.': 'Mrs', 'mrs': 'Mrs', 'mrs.': 'Mrs', 'Madam': 'Mrs', 'madam': 'Mrs', 'ma"am': 'Mrs'}
```

这里提供的解决方案非常易于维护、调试和扩展，因为唯一的变化是在适当的位置添加新字符串。此外，给出的解决方案不需要任何额外的循环或正则表达式。如果你需要一个新类别，例如“Sir,”，定义 Python 字典 `sir_dict`，然后添加新的代码段，所示：

```python
if title in ['Sir','sir','Sire','sire','Yessir','yessir']:
  sir_dict[title] = "Sir"
```

## SQL 中的数据清洗

本节包含几个在 SQL 中执行数据清洗任务的子节。注意，并非必须在 SQL 中执行这些任务：另一种选择是将数据库表的内容读取到 Pandas DataFrame 中，然后使用 Pandas 方法实现相同的结果。

然而，本节说明了如何执行以下影响数据库表属性的数据清洗任务：

- 将 `NULL` 替换为 `0`
- 将 `NULL` 替换为平均值
- 将多个值合并为单个值
- 处理数据类型不匹配
- 将字符串日期转换为日期格式

### 将 NULL 替换为 0

此任务非常直观，你可以使用以下 SQL 语句之一执行：

```sql
SELECT ISNULL(column_name, 0) FROM table_name
OR
SELECT COALESCE(column_name, 0) FROM table_name
```

### 将 NULL 值替换为平均值

此任务涉及两个步骤：首先找到数据库表中某列的非 `NULL` 值的平均值，然后用第一步中找到的值更新该列中的 `NULL` 值。列举 6.1 显示了 SQL 文件 `replace_null_values.sql` 的内容，该文件执行了这一对步骤。

**LISTING 6.1: replace_null_values.sql**

```sql
USE mytools;
DROP TABLE IF EXISTS temperatures;
CREATE TABLE temperatures (temper INT, city CHAR(20));

INSERT INTO temperatures VALUES(78,'sf');
INSERT INTO temperatures VALUES(NULL,'sf');
INSERT INTO temperatures VALUES(42,NULL);
INSERT INTO temperatures VALUES(NULL,'ny');
SELECT * FROM temperatures;

SELECT @avg1 := AVG(temper) FROM temperatures;
update temperatures
set temper = @avg1

where ISNULL(temper);
SELECT * FROM temperatures;

-- 用频率最高的城市值初始化 city1:
SELECT @city1 := (SELECT city FROM temperatures GROUP BY city ORDER BY COUNT(*) DESC LIMIT 1);

-- 使用 city1 更新 NULL city 值:
update temperatures
set city = @city1

where ISNULL(city);
SELECT * FROM temperatures;
```

列举 6.1 创建了 `temperatures` 表并填充了若干行，然后用 `temper` 属性的平均值初始化变量 `@avg1`。运行列举 6.1 你将看到以下输出：

```text
+--------+------+
| temper | city |
+--------+------+
|     78 | sf   |
|   NULL | sf   |
|     42 | NULL |
|   NULL | ny   |
+--------+------+
```

### 将多个值合并为单个值

合并多个值的示例是将纽约州的多个字符串（例如 `new_york`、`NewYork`、`NY` 和 `New_York`）替换为 `NY`。列举 6.2 显示了 SQL 文件 `reduce_values.sql` 的内容。

**LISTING 6.2: reduce_values.sql**

```sql
USE mytools;
DROP TABLE IF EXISTS mytable;
CREATE TABLE mytable (str_date CHAR(15), state CHAR(20), reply CHAR(10));

INSERT INTO mytable VALUES('20210915','New York','Yes');
INSERT INTO mytable VALUES('20211016','New York','no');
INSERT INTO mytable VALUES('20220117','Illinois','yes');
INSERT INTO mytable VALUES('20220218','New York','No');
SELECT * FROM mytable;

-- 将 yes, Yes, y, Ys 替换为 Y:
update mytable
set reply = 'Y'
where upper(substr(reply,1,1)) = 'Y';
SELECT * FROM mytable;

-- 将所有其他值替换为 N
update mytable
set reply = 'N' where substr(reply,1,1) != 'Y';
SELECT * FROM mytable;
```

```text
+----------+----------+-------+
| str_date | state    | reply |
+----------+----------+-------+
| 20210915 | New York | Yes   |
| 20211016 | New York | no    |
| 20220117 | Illinois | yes   |
| 20220218 | New York | No    |
+----------+----------+-------+
4 rows in set (0.000 sec)

Query OK, 2 rows affected (0.001 sec)
Rows matched: 2  Changed: 2  Warnings: 0

+----------+----------+-------+
| str_date | state    | reply |
+----------+----------+-------+
| 20210915 | New York | Y     |
| 20211016 | New York | no    |
| 20220117 | Illinois | Y     |
| 20220218 | New York | No    |
+----------+----------+-------+
4 rows in set (0.000 sec)

Query OK, 2 rows affected (0.001 sec)
Rows matched: 2  Changed: 2  Warnings: 0

+----------+----------+-------+
| str_date | state    | reply |
+----------+----------+-------+
| 20210915 | New York | Y     |
| 20211016 | New York | N     |
| 20220117 | Illinois | Y     |
| 20220218 | New York | N     |
+----------+----------+-------+
4 rows in set (0.001 sec)
```

### 处理不匹配的属性值

此任务涉及两个步骤：首先找到数据库表内某一列的非 `NULL` 值的平均值，然后用你在第一步中找到的数值更新该列中的 `NULL` 值。[列表项 6.3] 显示了 SQL 文件 `type_mismatch.sql` 的内容，该文件执行了这一对步骤。

#### 列表项 6.3: type_mismatch.sql



```sql
USE mytools;
DROP TABLE IF EXISTS emp_details;
CREATE TABLE emp_details (emp_id CHAR(15), city CHAR(20), state CHAR(20));

INSERT INTO emp_details VALUES('1000','Chicago','Illinois');
INSERT INTO emp_details VALUES('2000','Seattle','Washington');
INSERT INTO emp_details VALUES('3000','Santa Cruz','California');
INSERT INTO emp_details VALUES('4000','Boston','Massachusetts');
SELECT * FROM emp_details;

select emp.emp_id, emp.title, det.city, det.state
from employees emp join emp_details det
WHERE emp.emp_id = det.emp_id;

-- 早期版本的 MySQL 需要：
--WHERE emp.emp_id = cast(det.emp_id as INT);
```

[列表项 6.3] 创建并填充了 `emp_details` 表，随后是一个涉及 `emp` 和 `emp_details` 表的 SQL `JOIN` 语句。尽管在 `emp` 和 `emp_details` 表中，`emp_id` 表分别被定义为 `INT` 类型和 `CHAR` 类型，但代码按预期工作。然而，在 MySQL 的早期版本中，你需要使用内置的 `CAST()` 函数将 `CHAR` 值转换为 `INT` 值（反之），如被注释的代码片段所示：

```sql
--WHERE emp.emp_id = cast(det.emp_id as INT);
```

运行[列表项 6.3]中的代码，你将看到以下输出：

```text
+--------+------------+---------------+
| emp_id | city       | state         |
+--------+------------+---------------+
| 1000   | Chicago    | Illinois      |
| 2000   | Seattle    | Washington    |
| 3000   | Santa Cruz | California    |
| 4000   | Boston     | Massachusetts |
+--------+------------+---------------+
4 rows in set (0.000 sec)
+--------+--------------------+------------+---------------+
| emp_id | title              | city       | state         |
+--------+--------------------+------------+---------------+
|   1000 | Developer          | Chicago    | Illinois      |
|   2000 | Project Lead       | Seattle    | Washington    |
|   3000 | Dev Manager        | Santa Cruz | California    |
|   4000 | Senior Dev Manager | Boston     | Massachusetts |
+--------+--------------------+------------+---------------+
4 rows in set (0.002 sec)
```

### 将字符串转换为日期值

[列表项 6.4]显示了 `str_to_date.sql` 的内容，它说明了如何根据另一个包含日期字符串的字符串属性来填充日期属性值。

#### 列表项 6.4：str_to_date.sql

```sql
use mytools;
DROP TABLE IF EXISTS mytable;
CREATE TABLE mytable (str_date CHAR(15), state CHAR(20));

INSERT INTO mytable VALUES('20210915','New York');
INSERT INTO mytable VALUES('20211016','New York');
INSERT INTO mytable VALUES('20220117','yes');
INSERT INTO mytable VALUES('20220218','No');

SELECT * FROM mytable;

-- 1) 日期：
ALTER TABLE mytable
ADD COLUMN real_date DATE;

-- 2) 从 str_date 填充 real_date：
UPDATE mytable t1
INNER JOIN mytable t2
ON t1.str_date = t2.str_date
SET t1.real_date = DATE(t2.str_date);

-- 3) 删除：
ALTER TABLE mytable
DROP str_date;
```

[列表项 6.4]创建并填充了 `mytable` 表，并显示了表的内容。剩余语句解释如下：第一个语句添加了 `real_date` 列；第二个语句通过 `DATE()` 函数填充它；第三个语句是可选的：如果你想这样做，可以删除 `str_date`。运行[列表项 6.4]中的代码，你将看到以下输出：

```text
+----------+----------+-------+
| str_date | state    | reply |
+----------+----------+-------+
| 20210915 | New York | Yes   |
| 20211016 | New York | no    |
| 20220117 | Illinois | yes   |
| 20220218 | New York | No    |
+----------+----------+-------+
4 rows in set (0.000 sec)

Query OK, 2 rows affected (0.001 sec)
Rows matched: 2  Changed: 2  Warnings: 0

+----------+----------+-------+
| str_date | state    | reply |
+----------+----------+-------+
| 20210915 | New York | Y     |
| 20211016 | New York | no    |
| 20220117 | Illinois | Y     |
| 20220218 | New York | No    |
+----------+----------+-------+
4 rows in set (0.000 sec)

Query OK, 2 rows affected (0.001 sec)
Rows matched: 2  Changed: 2  Warnings: 0

+----------+----------+-------+
| str_date | state    | reply |
+----------+----------+-------+
| 20210915 | New York | Y     |
| 20211016 | New York | N     |
| 20220117 | Illinois | Y     |
| 20220218 | New York | N     |
+----------+----------+-------+
4 rows in set (0.001 sec)
```

本节未提供本节代码示例之外的关于 `sed` 的详细信息。然而，在阅读完代码（它是一行单行命令）后，你可能会理解如何将该代码片段调整为你自己的需求（即：如何指定不同的分隔符）。

列表 6.5 显示了 `delimiter1.txt` 的内容，列表 6.6 显示了 `delimiter1.sh` 的内容，它将所有分隔符替换为逗号（“，”）。

**列表 6.5：delimiter1.txt**

```text
1000|Jane:Edwards^Sales
2000|Tom:Smith^Development
3000|Dave:Del Ray^Marketing
```

**列表 6.6：delimiter1.sh**

```sh
cat delimiter1.txt | sed -e 's/:/,/' -e 's/|/,/' -e 's/\^/,/'
```

列表 6.6 以 `cat` 命令实用工具开头，该工具将文件 `delimiter1.txt` 的内容发送到“标准输出”（默认在屏幕上）。然而，在这个示例中，由于管道符号（`|`），此命令的输出变成了 `sed` 命令的输入。

`sed` 命令由三个部分组成，全部通过 `-e` 选项连接。你可以将 `-e` 理解为指示 `sed` 命令“还有更多处理需要完成”。在这个示例中，出现了三次 `-e`，这意味着 `sed` 将执行三个操作。

第一个代码片段是 `'s/:/,/'`，它的含义是“将每个分号替换为逗号”。该操作的结果被传递给下一个代码片段 `'s/|/,/'`。这个代码片段的意思是“将每个管道符替换为逗号”。该操作的结果被传递给下一个代码片段，即 `'s/\^*/,/'`。这个代码片段的意思是“将每个脱字符符号（“^”）替换为逗号”。该操作的结果被发送到标准输出，标准输出可以被重定向到另一个文本文件。运行列表 6.6 中的代码，你将看到以下输出：

```text
1000,Jane,Edwards,Sales
2000,Tom,Smith,Development
3000,Dave,Del Ray,Marketing
```

有三点需要注意：

1. 首先，第三个片段包含一个反斜杠，因为脱字符符号（“^”）是一个元字符，所以我们需要对该字符进行“转义”。其他元字符（如“$”和“.”）也是如此。
2. 其次，你可以针对文本文件中遇到的每一个新的作为字段分隔符的分隔符，轻松地扩展 `sed` 命令：只需为每个新分隔符遵循你在列表 6.6 中看到的模式即可。
3. 第三，通过运行以下命令，将 `delimiter1.sh` 的输出重定向到文本文件 `delimiter2.txt`：

```sh
./delimiter1.sh > delimiter2.txt
```

如果在上一个代码片段中发生错误，请确保通过调用以下命令使 `delimiter1.sh` 具有执行权限：

```sh
chmod 755 delimiter1.sh
```

到此，涉及 `sed` 命令行实用工具的示例结束，它是一个处理文本文件的非常强大的工具。

### 处理变动列数

本节向你展示如何使用 `awk` 命令行实用工具用 NaN 值“填充”CSV 文件中的行，以便使所有记录具有相同的列数。

列表 6.7 显示了 `variable_columns.csv` 的内容，列表 6.8 显示了 `variable_columns.sh` 的内容，它使用 `awk` 实用工具来填充 CSV 文件中的列数。

**列表 6.7：variable_columns.csv**

```csv
10,20,30
10,20,30,40
10,20,30,40,50,60
```

**列表 6.8：variable_columns.sh**

```sh
filename="variable_columns.csv"

cat $filename | awk -F"," '
BEGIN { colCount = 6 }
{
  printf("%s", $0)
  for(i=NF; i<colCount; i++) {
     printf(",NaN")
  }
  print ""
}
'
```

列表 6.8 初始化变量 `filename` 为该代码示例的 CSV 文件名。下一个片段是一个 `awk` 脚本，它在 `BEGIN` 块中初始化 `colCount` 为 6：该值是 CSV 文件中任何行的最大列数。

下一块代码显示当前行的内容，随后是一个循环，打印一个逗号分隔的 NaN 值列表，以确保输出行包含 6 列。例如，如果一行有四列，那么 `NaN` 将打印两次。循环后的 `print()` 语句确保输入文件的下一行从新行开始，而不是在当前输出行。运行列表 6.8 中的代码，你将看到以下输出：

```text
10,20,30,NaN,NaN,NaN
10,20,30,40,NaN,NaN
10,20,30,40,50,60
```

列表 6.8 的一个局限性是必须在 `BEGIN` 块中指定最大列数。列表 6.9 通过扫描整个文件来确定列限制。

**列表 6.9：variable_columns.sh**

```sh
filename="variable_columns.csv"

cat $filename | awk -F"," '
BEGIN { colCount = 0 }

while (getline line < ARGV[1]) {
  colCount = split(line, data)
  if (maxCount < length(data)) {
    maxCount = length(data)
  }
}
{
  # 打印当前行：
  printf("%s", $0)

  # 如果需要填充 NaN：
  for(i=NF; i<maxCount; i++) {
    printf(",NaN")
  }
  print ""
}
'
```

列表 6.9 初始化变量 `filename` 为该代码示例的 CSV 文件名。下一个片段是一个 `awk` 脚本，它包含一个 `while` 循环来处理行。列表 6.9 与列表 6.8 相同，在需要时用 NaN 填充行。运行列表 6.9 中的代码，你将看到以下输出：

```text
10,20,30,NaN,NaN,NaN
10,20,30,40,NaN,NaN
10,20,30,40,50,60
```

### 截断 CSV 文件中的行

上一节向你展示了如何使用 `awk` 命令行实用工具用 NaN 字符串填充 CSV 文件中的行，而本节向你展示如何截断 CSV 文件中的行，只显示列数最少的列。

列表 6.10 显示了 `variable_columns3.sh` 的内容，它使用 `awk` 实用工具显示 CSV 文件中的列子集。

**列表 6.10：variable_columns3.sh**

```sh
filename="variable_columns.csv"

cat $filename | awk -F"," '
BEGIN {
  colCount = 0
  minColCount = 9999

  ###############################################
  # minColCount = 最短行的字段数
  ###############################################
  while(getline line < ARGV[1]) {
    colCount = split(line, data)
    if(minColCount > length(data)) {
       minColCount = length(data)
    }
  }
}
{
  # 对每行输入执行：
  for(j=1; j<=minColCount; j++) {
     printf("%s,$j")
  }
  print ""
}
' $filename
```

列表 6.10 与列表 6.9 非常相似。在初始化变量 `filename` 为该代码示例的 CSV 文件名后，`awk` 脚本从 CSV 文件中找到列数最少的列的列数。变量 `minColCount` 在 `BEGIN` 块中初始化为 9999，当该循环完成后，它的值将是输入行的最小列数。

列表 6.9 的后续部分是一个循环，用于打印输入文件中每行的前 `minColCount` 列。运行列表 6.10 中的代码，你将看到以下输出：

```text
10,20,
10,20,
10,20,
10,20,
10,20,
```

## 使用 AWK 工具生成具有固定列数的行

本节中的代码示例包含一个 `awk` 脚本，该脚本处理一个以空格分隔的输入字符串 CSV 文件，并生成所有行都具有相同列数的输出（最后一行可能除外）。列表 6.11 显示了 `FixedFieldCount1.sh` 的内容，该内容说明了如何使用 `awk` 工具将一个字符串拆分为包含三个字符串的行。

***列表 6.11：FixedFieldCount1.sh***

```sh
echo "=> pairs of letters:"
echo "aa bb cc dd ee ff gg hh"
echo

echo "=> split on multiple lines:"
echo "aa bb cc dd ee ff gg hh" | awk '
BEGIN { colCount = 3 }
{
  for(i=1; i<=NF; i++) {
     printf("%s ", $i)
     if(i % colCount == 0) { print "" }
  }
  print ""
}
'
```



Listing 6.11 显示了一个字符串的内容，然后将该字符串作为`awk`命令的输入。Listing 6.11 的主体部分是一个从 1 迭代到`NF`的循环，其中`NF`是输入行中的字段数，在本例中，它等于 8。每个字段的值由`$i`表示：`$1`是第一个字段，`$2`是第二个字段，依此类推。注意`$0`是整个输入行的内容（在下一个代码示例中使用）。

接下来，如果`i`的值（即字段的位置，而不是字段的内容）是 3 的倍数，则代码将打印换行符。运行 Listing 6.11 中的代码，你将看到以下输出：

```
 => pairs of letters:
aa bb cc dd ee ff gg hh

=> split on multiple lines:
aa bb cc
dd ee ff
gg hh
```

Listing 6.12 显示了`employees.txt`的内容，Listing 6.13 显示了`FixedFieldCount2.sh`的内容，说明了如何确保所有行具有相同的列数。

***LISTING 6.12: employees.txt***

```
 jane:jones:SF:
john:smith:LA:
dave:smith:NY:
sara:white:CHI:
```

***LISTING 6.13: FixedFieldCount2.sh***

```
 cat employees.txt | awk -F":" '{printf("%s", $0)} | awk -F':' '
BEGIN { colCount = 3 }
{
  for(i=1; i<=NF; i++) {
     printf("%s", $i)
     if(i % colCount == 0) { print "" }
  }
  print ""
}
'
```

注意 Listing 6.13 中的代码与 Listing 6.11 中的代码几乎相同。图中显示的代码从`employees.txt`的内容中删除了`\n`字符。如果你需要，请运行以下代码片段：

```
 cat employees.txt | awk -F":" '{printf("%s", $0)}
```

之前的代码输出如下：

```
 jane:jones:SF:
john:smith:LA:
dave:smith:NY:
sara:white:CHI:
```

我们现在将 Listing 6.9 中的任务简化到与 Listing 6.7 相同，这就是为什么我们有相同的`awk`代码块的原因。

## 转换电话号码

Listing 6.14 显示了`phone_numbers.txt`的内容，其中包含不同格式的（主要是虚拟的）电话号码。

***LISTING 6.14: phone_numbers.txt***

```
1234567890
234 4560987
234 456 0987
212 555-1212
212-555-1212
(123)5551212
(456)555-1212
(789)555 1212
1-1234567890
1 234 4560987
1-234 456 0987
1 212 555-1212
1-212-555-1212
1(123)5551212
1(456)555-1212
1(789)555 1212
1-(123)5551212
1-(456)555-1212
1-(789)555 1212
011-1234567890
011 234 4560987
011-234 456 0987
011-155580
033 234 4560987
039-234 456 0987
034 212 555-1212
034-212-555-1212
044(123)5551212
044(456)555-1212
044(789)555 1212
049-(123)5551212
049-(456)555-1212
049-(789)555 1212
052(278)9551212
```

## 转换数字日期

本节将向你展示如何将日期格式转换为常用的 MM-DD-YYYY 格式。在深入研究代码之前，以下列表包含了日期的月份、日期和年份的示例格式：

```
 • yy:   两位年份                 (ex: 22)
 • yyyy: 四位年份                (ex: 2022)
 • m:    一位月份                 (ex: 4)
 • mm:   两位月份                (ex: 04)
 • mmm:  三字母月份               (ex: Apr)
 • mmmm: 月份全称                (ex: April)
 • d:    一位日期                 (ex: 2)
 • dd:   两位日期                 (ex: 02)
 • ddd:  三字母星期               (ex: Sat)
 • dddd: 星期全称                (ex: Saturday)
```

Listing 6.16 显示了`dates.txt`的内容，其中包含了各种格式的虚构日期，粗体字符串格式无效。

***LISTING 6.16: dates.txt***

```
 03/15/2021
3/15/2021
3/15/21
03/5/2021
3/5/2021
3/5/21
3/5/212
3/5/21Z
```

Listing 6.17 显示了`dates.sh`的内容，它展示了如何从 Listing 6.16 中的日期移除非数字字符，使其具有相同的格式。

***Listing 6.17: dates.sh***

```
 cat dates.txt | awk -F"/"
{
   DATE_FORMAT="valid"
   # step 1: extract the month
   if($0 ~ /^[0-9]{2}/) {
     month = substr($0,1,2)
     #print "normal month: ",month
   } else if($0 ~ /^[0-9]\//) {
     month = "0" substr($0,1,1)
     #print "short month: ",month
   } else {
     DATE_FORMAT="invalid"
   }
   if(DATE_FORMAT="valid") {
     # step 2: extract the day
     if($0 ~ /^[0-9][0-9]\/[0-9][0-9]/) {
       day = substr($0,4,2)
       #print "normal day: ",day
     } else if ($0 ~ /^[0-9][0-9]\/[0-9]\//) {
       day = "0" substr($0,4,1)
       #print "short day: ",day
     } else {
       DATE_FORMAT="invalid"
     }
   }

   if(DATE_FORMAT="valid") {
     # step 3: extract the year
     if($0 ~ /^[0-9][0-9]\/[0-9][0-9]\/[0-9][0-9][0-9][0-9]$/) {
       year = substr($0,7,4)
       #print "normal year: ",year
     } else if ($0 ~ /^[0-9][0-9]\/[0-9]\/[0-9][0-9]\/$/) {
       year = "20" substr($0,7,2)
       #print "short year: ",year
     }
   } else {
     DATE_FORMAT="invalid"
   }

   if(DATE_FORMAT="valid") {
     printf("=> $0: %s MM/DD/YYYY: %s-%s-%s\n",$0,month,day,year)
   } else {
     print "invalid format: ",$0
   }
}
'
```

Listing 6.17 包含的代码如果你不熟悉正则表达式可能会可能会望而生畏。让我们尝试揭开代码的神秘面，从代表任何单个数字的正则表达式`[0-9]`开始。`^[0-9]\/`中开头的脱字符符号`^`表示数字必须出现在最左侧（即第一个）位置。此外，正则表达式`^[0-9]\/`表示单数字后必须紧跟一个`/`。需要反斜杠`\`来“转义”元字符`/`。这意味着它将被视为一个普通字符而不是元字符。例如，字符串`3/`匹配该正则表达式，但字符串`03/`、`B3/`和`AB/`都不匹配。

现在让我们查看正则表达式`^[0-9][0-9]\/`，它代表任何以两个数字开头并接`/`字符的字符串。因此，字符串`03/`匹配该正则表达式，但字符串`3/`、`B3/`和`AB/`都不匹配。

接下来，正则表达式`^[0-9][0-9]\/[0-9][0-9]`代表任何以两个数字开头、后面是`/`字符、又是两个数字的字符串。因此，字符串`03/15`匹配该正则表达式，但字符串`3/5`、`03/5`和`3/15`都不匹配。

最后，正则表达式`^[0-9][0-9]\/[0-9][0-9]\/[0-9][0-9][0-9][0-9]$`匹配符合以下条件的字符串：

- 以两个数字开头
- 后面跟着一个`/`
- 后面是两个数字
- 后面又是另一个`/`
- 最后是四个数字
- 且没有额外的字符

Listing 6.17 包含了匹配包含“短”月份、日期和年份的正则表达式。运行 Listing 6.17 中的代码，你将看到以下输出：

```
 => $0: 03/15/2021 MM/DD/YYYY: 03-15-2021
=> $0: 3/15/2021 MM/DD/YYYY: 03-15-2021
=> $0: 3/15/21 MM/DD/YYYY: 03-15-2021
=> $0: 03/5/2021 MM/DD/YYYY: 03-05-2021
=> $0: 3/5/2021 MM/DD/YYYY: 03-05-2021
=> $0: 3/5/21 MM/DD/YYYY: 03-05-2021
=> $0: 03/5/21 MM/DD/YYYY: 03-05-2021
=> $0: 3/5/21 MM/DD/YYYY: 03-05-2021
```

为什么前面的几行（加粗显示的部分）尽管在年份的正则表达式中出现了`$`却被显示为有效？遗憾的是，后两个正则表达式出现在提取日期的正则表达式之后，Listing 6.18 显示了`dates2.sh`的内容，它检测无效日期，使用了数字的简写符号，并删除了多余的`print`语句。

***Listing 6.18: dates2.sh***

```
 cat dates.txt | awk -F"/"
{
   DATE_FORMAT="valid"

   # step 1: check for invalid
   if($0 ~ /[A-Za-z]/) {
     print "invalid characters: ",$0
     DATE_FORMAT="invalid"
   } else if($0 ~ /^[0-9]{3}$) {
     print "invalid format: ",$0
     DATE_FORMAT="invalid"
   }

   if(DATE_FORMAT="valid") {
     # step 2: extract the month
     if($0 ~ /^[0-9][0-9]/) {
       month = substr($0,1,2)
     } else if($0 ~ /^[0-9]\/) {
       month = "0" substr($0,1,1)
     } else {
       DATE_FORMAT="invalid"
     }
   }

   if(DATE_FORMAT="valid") {
     # step 3: extract the day
     if($0 ~ /^[0-9]{2}\/[0-9]{2}/) {
       day = substr($0,4,2)
     } else if ($0 ~ /^[0-9]{2}\/[0-9]\/) {
       day = "0" substr($0,4,1)
     } else {
       DATE_FORMAT="invalid"
     }
   }

   if(DATE_FORMAT="valid") {
     # step 4: extract the year
     if($0 ~ /^[0-9]{2}\/[0-9]{2}\/[0-9]{4}$/) {
       year = substr($0,7,4)
     } else if ($0 ~ /^[0-9]{2}\/[0-9]{2}\/[0-9]{2}$/) {
       year = "20" substr($0,7,2)
     }
   }

   if(DATE_FORMAT="valid") {
     printf("$0: %10s => %s-%s-%s\n",$0,month,day,year)
   } else {
     print "Date invalid:",$0
   }
}
'
```

Listing 6.18 与 Listing 6.17 的内容非常相似，但有些不同。第一个不同是 Listing 6.18 检查包含字母的数字并将其报告为格式无效。第二个不同是识别末尾有三个数字的条件代码块。第三个不同是指定多个连续数字的简写方法：`[0-9]{2}`匹配任何一对连续数字，`[0-9]{3}`匹配任何三个连续数字的情况，依此类推。运行 Listing 6.18 中的代码，你将看到以下输出：

```
 $0: 03/15/2021 => 03-15-2021
$0:  3/15/2021 => 03-15-2021
$0:    3/15/21 => 03-15-2021
$0:  03/5/2021 => 03-15-2021
$0:   3/5/2021 => 03-15-2021
$0:     3/5/21 => 03-15-2021
invalid format:  3/5/212
$0:    3/5/212 => 03-15-2021
invalid characters:  3/5/21Z
$0:    3/5/21Z => 03-15-2021
```

### 转换字母日期格式

本节向你展示如何将日期格式转换为 DD-MON-YYYY 的常用格式。Listing 6.19 显示了`dates2.txt`的内容，其中包含各种格式的日期，加粗字符串的格式无效。

***Listing 6.19: dates2.txt***

```
 03/15/2021
04-SEP-2022
04-sep-  2022
04-sep-  22
05-OCT   2022
05-oct 2022
05-oct 22
06 JAN 2022
06 jan 2022
06 jnn 22
```



```bash
cat dates2.txt | tr -s ' ' | sed -e 's/- /-/g' -e 's/ /-/g' | awk -F"-" '
BEGIN {
   months["JAN"] = "JAN"
   months["FEB"] = "FEB"
   months["MAR"] = "MAR"
   months["APR"] = "APR"
   months["MAY"] = "MAY"
   months["JUN"] = "JUN"
   months["JUL"] = "JUL"
   months["AUG"] = "AUG"
   months["SEP"] = "SEP"
   months["OCT"] = "OCT"
   months["NOV"] = "NOV"
   months["DEC"] = "DEC"
}
{
   #Valid date formats (Oracle):
   #DD-MON-YY:   04-SEP-2022
   #DD-MON-YYYY: 05-OCT-22

   $0 = toupper($0)
   DATE_FORMAT="valid"

   # step 1: extract the day:
   if($0 ~ /^[0-9]\-/) {
     day = "0" substr($0,1,1)
   } else if($0 ~ /^[0-9][0-9]\-/) {
     day = substr($0,1,2)
   } else {
     DATE_FORMAT="invalid"
   }

   if(DATE_FORMAT="valid") {
     # step 2: extract the month:
     if($0 ~ /^[0-9]{2}\-[A-Z]{3}/) {
       month = substr($0,4,3)
     } else {
       DATE_FORMAT="invalid"
     }
   }

   if(DATE_FORMAT="valid") {
     # step 3: extract the year:
     if($0 ~ /^[0-9]{2}\-[A-Z]{3}\-[0-9]{2}/) {
       year = "20" substr($0,8,2)
     } else if($0 ~ /^[0-9]{2}\-[A-Z]{3}\-[0-9]{4}/) {
       year = substr($0,8,4)
     } else {
       DATE_FORMAT="invalid"
     }
   }

   if(DATE_FORMAT="valid") {
   if(months[month] == month) {
      printf("%12s => %s-%s-%s\n",$0,month,day,year)
   } else {
      printf("Invalid month:  %s-%s-%s\n",month,day,year)
   } else {
      print "Date format invalid:",$0
   }
}
'
```

`Listing 6.20` 以一组由管道符分隔的命令序列开始，将文件 `dates2.txt` 的内容重定向到 `tr` 命令，该命令会删除多个连续出现的空格。

接下来，将 `tr` 命令的输出重定向到 `sed` 命令，该命令会删除连字符（`-`）随后的任何空格，然后将任何空格替换为连字符（`-`）。

`sed` 命令的输出被重定向到一个 `awk` 脚本，该脚本初始化了一个包含全年月份三个字母缩写的数组。该数组在代码后面被引用，用于检测任何无效的月份格式。

`awk` 脚本的主部分与 `Listing 6.27` 中的内容相似，用于检测各种日期格式，并为每行输入初始化 `day`、`month`（三字母值）和 `year`。运行 `Listing 6.20` 中的代码，你将看到以下输出：

```text
 04-SEP-2022 => SEP-04-2020
 04-SEP-2022 => SEP-04-2020
   04-SEP-22 => SEP-04-2022
 05-OCT-2022 => OCT-05-2020
 05-OCT-2022 => OCT-05-2020
   05-OCT-22 => OCT-05-2022
 06-JAN-2022 => JAN-06-2020
 06-JAN-2022 => JAN-06-2020
Invalid month:  JNN-06-2022
```

### 处理日期和时间格式

现在你已经看到了 `MM:DD:YYYY` 格式的日期示例，本节将处理 `YYYY:MM:DD:HH:MM:SS` 格式的日期。尽管本节中基于 `awk` 的代码示例比书中所有其他代码示例都要长，但它是基于你之前在日期相关代码示例中已经过的技术。如果你现在不需要深入研究此代码示例的细节，可以随时跳过本节。

所有字段（年份外）的单数字值都被视为有效，处理所有可能的组合变得非常繁琐。然而，本节中的代码示例向你展示了一种捷径，该方法涉及动态修改输入行，以便输入字符串从左到右处理时被逐步填充。

为了确保这一点，字符串 `3/15/22 5:44` 是有效日期，当代码检查日期字段的有效性时，前面的字符串会如下被修改：

```text
 3/15/22 5:44
03/15/22 5:44
03/15/2022 5:44
03/15/2022 05:44
03/15/2022 05:04
03/15/2022 05:44
```

正如你所看到的，日期列表中最后一行是完全填充的日期。这种方法显著减少了判断日期格式时需要检查的模式数量。

`Listing 6.21` 显示了包含日期的 `dates-times.txt` 内容，`Listing 6.22` 向你展示了 `date-times-padded.sh` 的，这是一个基于 `awk` 的 shell 脚本，用于处理 `Listing 6.21` 中的日期。

**LISTING 6.21: dates-times.txt**

```text
 2/30/2020 15:05:44
2/30/2020 15:05:44
3/15/22 15:5:44
4/29/23 15:5:4
5/16/24 5:05:44
6/17/25 5:5:44
7/18/26 5:5:4
8/19/24 115:05:44
```

注意 `Listing 6.21` 中的第一行和最后一行是无效的：第一行包含月份值 30，这对于任何年份都是无效的，而最后一行包含无效的小时值。

```bash
cat date-times.txt | awk -F"/" '
function check_leap_year(year) {
  #########################################
  # 如果满足以下条件，则为闰年：
  # 1) 它是 4 的倍数且
  # 2) 世纪必须是 400 的倍数
  # => 2000 年是闰年，但 1900 年不是
  #########################################

  result = 0 # 0: 平年 1: 闰年
  if((year % 4) == 0) {
    if((year % 100) == 0) {
      if((year % 400) == 0) {
        return 1 # 闰年
      } else {
        return 0 # 平年
      }
    } else {
      return 1 # 闰年
    }
  } else {
    return 0 # 平年
  }
}

BEGIN {
  count = 1
  for(i=0;i<12;i++) {
    months[i] = 31
  }

  # 30 天：四、六、九、十一月月
  months[1]  = 28;
  months[3]  = 30;
  months[5]  = 30;
  months[8]  = 30;
  months[10] = 30;

  #for(i=0;i<12;i++) {
  #  print "months[",i,"]:",months[i]
  #}
}
{
   ####################################
   # 有效的月份格式：
   # [0-9], [1][0-2]
   #
   # 有效的日期格式：
   # [0-9], [1][0-9], [3][0-1]
   #
   # 有效的年份格式：
   # [0-9]{2}, [2][0-9][0-9][0-9]
   #
   # 额外注释：
   # 1) 一个月 30 天还是 31 天
   # 2) 检查二月：28 天还是 29 天
   ####################################

   # 示例格式：
   # MM/DD/YYYY HH:MM:SS
   print "=> #" count " PROCESSING:",$0

   VALID_DATE="true"
   split($0,day_time," ")
   date_part = day_time[1]
   time_part = day_time[2]

   # 步骤 1：提取月份
   if(date_part ~ /^[0-9]\//) {
     month = "0" substr(date_part,1,1)
     #print "短月份: ",month
     # 在日期部分插入一个 "0":
     date_part = "0" substr(date_part,1,1) substr(date_part,2)
     #print "*** 新 date_part:",date_part
   } else if(date_part ~ /^[0-9]{2}/) {
     month = substr(date_part,1,2)
     #print "正常月份: ",month
   } else {
     print "无法找到月份"
     VALID_DATE="false"
   }

   if(VALID_DATE == "true") {
     # 步骤 2：提取日期：#03/15/2021 15:05:44
     #print "正在检查日期:",date_part
     if(date_part ~ /^[0-9]{2}\/[0-9]{2}/) {
       day = substr(date_part,4,2)
       #print "正常日期: ",day
     } else if (date_part ~ /^[0-9]{2}\/[0-9]/) {
       day = "0" substr(date_part,4,1)
       #print "1 短日期: ",day
       date_part = substr(date_part,1,3) "0" substr(date_part,4)
       #print "*** 2 新 date_part:",date_part
     } else if (date_part ~ /^[0-9]{1}\/[0-9]{2}/) {
       day = substr(date_part,3,2)
       #print "2 正常日期: ",day
     } else if (date_part ~ /^[0-9]{1}\/[0-9]/) {
       day = "0" substr(date_part,2,1)
       #print "2 短日期: ",day
     } else {
       print "无法找到日期"
       VALID_DATE="false"
     }
   }

   if(VALID_DATE == "true") {
     # 步骤 3：提取年份：#03/15/2021 15:05:44
     #print "日期部分:",date_part  # 03/15/2021
     #print "时间部分:",time_part  # 15:05:44

     if(date_part ~ /^[0-9]{2}\/[0-9]{2}\/[0-9]{4}/) {
       year = substr(date_part,7,4)
       #print "正常年份: ",year
     } else if(date_part ~ /^[0-9]{2}\/[0-9]{2}\/[0-9]{3}/) {
       year = substr(date_part,7,3)
       #print "短年份: ",year
       date_part = substr(date_part,1,6) "0" substr(date_part,7)
       #print "*** 新 date_part:",date_part
     } else {
       print "无法找到年份"
       VALID_DATE="false"
     }
   }

   if(VALID_DATE == "true") {
     # 步骤 4：提取小时：#15:05:44
     #print "时间部分:",time_part
     if(time_part ~ /^[0-9]{2}:[0-9]{2}/) {
       hours = substr(time_part,1,2)
       #print "正常小时: ",hours
     } else if(time_part ~ /^[0-9]{2}:[0-9]/) {
       hours = "0" substr(time_part,4,1)
       #print "1 短小时: ",hours
       time_part = substr(time_part,1,3) "0" substr(time_part,4)
       #print "*** 新 time_part:",time_part
     } else {
       print "无法找到小时"
       VALID_DATE="false"
     }
   }

   if(VALID_DATE == "true") {
     # 步骤 5：提取分钟：#05:44
     #print "时间部分:",time_part
     if(time_part ~ /^[0-9]{2}:[0-9]{2}/) {
       minutes = substr(time_part,4,2)
       #print "正常分钟: ",minutes
     } else if(time_part ~ /^[0-9]{2}:[0-9]/) {
       minutes = "0" substr(time_part,4,1)
       #print "1 短分钟: ",minutes
       time_part = substr(time_part,1,3) "0" substr(time_part,4)
       #print "*** 新 time_part:",time_part
     } else {
       print "无法找到分钟"
       VALID_DATE="false"
     }
   }

   if(VALID_DATE == "true") {
     # 步骤 6：检查闰年
     result = check_leap_year(year)
     if(result == 1) {
        #print "找到闰年:",year
        # 检查是否允许 29 天
        if(day <= 29) {
          print "=> VALID DAY/TIME FORMAT:",$0
        } else {
          print "*** 闰年超出范围:",$0
        }
     } else {
        #print "找到平年:",year
        # 检查是否允许 28 天
        if(day <= 28) {
          print "=> VALID DAY/TIME FORMAT:",$0
        } else {
          print "*** 平年超出范围:",$0
        }
     }
   } else {
     print "无效的日期/时间格式:",$0
   }

   print "----------------\n"
   count += 1
}
'
```

运行列表 `6.22` 中的代码，你将看到以下输出：



```text
=> #1 PROCESSING: 2/30/2020 15:05:44
*** 闰年超出范围: 2/30/2020 15:05:44
----------------

=> #2 PROCESSING: 3/15/22 15:5:44
=> VALID DAY/TIME FORMAT:  3/15/22 15:5:44
----------------

=> #3 PROCESSING: 4/29/23 15:5:44
*** 平年超出范围: 4/29/23 15:5:4
----------------

=> #4 PROCESSING: 5/16/24 5:05:44
=> VALID DAY/TIME FORMAT:  5/16/24 5:05:44
----------------

=> #5 PROCESSING: 6/17/25 5:5:44
=> VALID DAY/TIME FORMAT:  6/17/25 5:5:44
----------------

=> #6 PROCESSING: 7/18/26 5:5:4
=> VALID DAY/TIME FORMAT:  7/18/26 5:5:4
```

`Listing 6.22` 显示了 `add_country_codes.sh` 的内容，展示了如何增加一组国家的三位国际前缀。请注意，在本节之后你将不需要这段代码示例。将其包含在此处是为了向你展示如何使用 `awk` 工具轻松地操作 CSV 文件中的数值值。如果有需要，你可以轻松地调整此代码以处理其他 CSV 文件。

**Listing 6.22: `add_country_codes.sh`**

```bash
FILE="country_codes.csv"

echo "=> display code and country:"

awk -F"," '

BEGIN { code = 10000; incr = 10000 }

{

   printf("%s,%s,%d\n", $1, $2, code)

   code += incr

}

' < $FILE

echo "-----------------"

echo

echo "=> increment country code:"

awk -F"," '

BEGIN { code = 1000; incr = 1000 }

{

   printf("%d,%s\n", $1 + code, $2)

   code += incr

}

' < $FILE
```

`Listing 6.22` 初始化变量 `FILE`，其名称为包含若干国家代码和缩写的 CSV 文件名。接下来，一个 `awk` 脚本包含一个 `BEGIN` 部分，其中包含一个循环，为每个国家代码加 10000。例如，以下两个代码段显示了输入行“之前”和“之后”的内容：

```text
001,usa,10000

1001,usa
```

运行 `Listing 6.22` 中的代码，你将看到以下输出：

```text
=> display code and country:

001,usa,10000

033,france,20000

034,spain,30000

039,italy,40000

044,uk,50000

049,germany,60000

052,mexico,70000

081,japan,80000

-----------------

=> increment country code:

1001,usa

2033,france

2034,spain

4039,italy

5044,uk

6049,germany

7052,mexico

8081,japan
```

`Listing 6.23` 显示了 `countries_cities.csv` 的内容，每行包含一个国家以及该国家的城市列表。

**Listing 6.23: `countries_cities.csv`**

```text
italy,firenze,milano,roma,venezia

france,antibe,nice,paris,st_jeannet

germany,berlin,frankfurt

spain,barcelona,madrid

england,liverpool,london,manchester

mexico,mexico_city,tijuana
```

`Listing 6.24` 显示了 `split_countries_cities.sh` 的内容，展示了如何显示 `countries_cities.csv` 中每个国家的城市列表。

**Listing 6.24: `split_countries_codes.sh`**

```bash
FILE="countries_cities.csv"

awk -F"," '

{

   printf("=> CITIES in %s:\n",$1)

   for(i=2; i<=NF; i++) {

        printf("%s\n", $i)

   }

}

' < $FILE
```

`Listing 6.24` 初始化变量 `FILE`，其名称为包含若干国家代码和缩写的 CSV 文件。接下来，一个 `awk` 脚本包含一个循环，显示 CSV 文件 `countries_cities.csv` 中列出的每个城市的缩写。运行 `Listing 6.24` 中的代码，你将看到以下输出：

```text
=> display code and country:

=> CITIES in italy:

firenze

milano

roma

venezia

=> CITIES in france:

antibe

nice

paris

st_jeannet

=> CITIES in germany:

berlin

frankfurt

=> CITIES in spain:

barcelona

madrid

=> CITIES in england:

liverpool

london

manchester

=> CITIES in mexico:

mexico_city

tijuana
```

`Listing 6.25` 显示了 `countries_cities2.csv` 的内容，每行包含一个国家以及该国家的城市列表。

**Listing 6.25: `countries_cities2.csv`**

```text
italy,firenze,milano,roma,venezia

france,antibe,nice,paris,st_jeannet

germany,berlin,frankfurt

spain,barcelona,madrid

england,liverpool,london,manchester

mexico,mexico_city,tijuana

usa,chicago,illinois,denver,colorado,seattle,washington,vancouver,washington
```

`Listing 6.26` 显示了 `split_countries_cities.sh` 的内容，展示了如何显示 `countries_cities2.csv` 中每个国家的城市列表。

**Listing 6.26: `split_countries_codes.sh`**

```bash
FILE="countries_cities2.csv"

awk -F"," '

BEGIN { incr = 1000 }

{

   if($1 ~ /usa/) {

     printf("=> CITIES in %s:\n",$1)

     for(i=2; i<=NF; i++) {

          printf("%s\n", $i)

     }

   } else {

     printf("=> CITIES in %s:\n",$1)

     for(i=2; i<=NF; i++) {

          printf("%s\n", $i)

     }

   }

}' $FILE
```

...



本章的第三部分介绍了一个项目，该项目涉及创建一个 CSV 文件，其中包含乐队活动安排及其未来的音乐会演出计划。该项目模拟了一个包含多种格式文件的场景，例如 XML 文档、文本数据、CSV 文件以及 MySQL 数据库表中的数据。目标是转换这些文件并合并它们以创建一个单一的 CSV 文件。

### 什么是数据清洗（DATA WRANGL）？

`Data wrangling` 对不同的人有不同的含义。一些在线文章认为数据清洗涉及一系列步骤，而另一些文章则认为数据清洗涉及将数据集从一种格式转换为另一种格式。以下网页将数据清洗描述为一个六步骤的过程：

`https://en.wikipedia.org/wiki/Data_wrangling`

除了上述链接中列出的步骤外，数据清洗还涉及以下任务（在第 7 章的代码示例中执行）：

- 将数据集从一种格式转换为另一种格式（`convert`）
- 从现有数据集的列子集中创建新数据集（`extract`）

正如你看到的，前面的步骤区分了“将数据转换为不同格式”与“从多个数据提取数据以创建新数据集”。如果只执行第一步（即没有提取步骤），那么转换过程可以被视为数据清洗任务。

在上一章中，你学习了数据清洗，并学习了一系列基于 Python 的代码示例和 Unix Shell 脚本来执行数据清洗任务。相比之下，数据清洗涉及多个步骤，可以包括转换一个或多个文件。下面的小节提供了数据清洗与数据转换之间更详细的区分。

### 数据转换：这意味着什么？

通常，数据清洗涉及单一数据源（不一定是 CSV 格式），对数据源的内容进行某种类型的修改（例如填充缺失值和更改日期格式），而不创建第二个数据源。

例如，假设数据源是一个名为 `employees` 的 MySQL 表，包含员工相关信息。在完成对 `employees` 表的数据清洗任务后，结果仍然命名为 `employees` 表。在数据库术语中，数据清洗类似于执行涉及单表 `SELECT` 的 SQL 语句。

然而，如果两个 CSV 文件包含不同的日期格式，你需要根据日期列创建一个单一的 CSV 文件，那么将会存在某种转换过程，可以是以下之一：

- 将第一种日期格式转换为第二天日期格式
- 将第二种日期格式转换为第一种日期格式
- 将两种日期格式都转换为第三种日期格式

在财务数据的情况下，你可能还会遇到不同的货币，这涉及一对货币之间的汇率。由于货币汇率会波动，你需要决定为数据使用何种汇率，该汇率可以是：

- CSV 文件生成期间的汇率
- 当前的货币汇率
- 其他某种机制

此外，你可能还需要将 CSV 文件转换为 XML 文档，其中后者可能需要符合 XML Schema，并且可能还需要符合 XBRL，这是业务报告目的的要求：

`https://en.wikipedia.org/wiki/XBRL`

正如前面提到的，数据转换可以涉及两个或多个数据源，以创建另一个属性符合所需格式的另一个数据源。以下是仅使用两个数据源 A 和 B 进行数据转换的四种场景，其中来自 A 和 B 的数据合并以创建数据源 C，其中 A、B 和 C 可以具有不同的文件格式：

- A 中的所有属性和 B 中的所有属性
- A 中的所有属性和 B 中的所有属性
- A 中的属性子集和 B 中的所有属性
- A 中的属性子集和 B 中的属性子集

在数据库术语中，数据转换类似于执行一个带有 `JOIN` 子句的涉及两个或多个数据库表 `SELECT` 的 SQL 语句。此类 SQL 语句通常涉及每个数据库表的列子集，这对应于选择数据源中特征的子集。

还存在涉及两个或多个数据源拼接的场景。如果所有数据源具有相同的属性，那么它们的拼接是简单易举的，但你可能需要检查重复值。例如，如果你想将多个 CSV 文件加载到不允许重复的数据库表中，那么一种解决方案是在命令行中合并 CSV 文件，然后排除重复行。

上述的合并任务可以轻松完成。假设你有以下一组 CSV 文件（所有文件具有相同的属性）`emp1.csv`、`emp2.csv` ... `emp100.csv`。通过创建一个名为 `concat.sh` 的 Shell 脚本来合并这些文件并排除重复行：

```bash
for f in `ls emp*csv`
do
  cat $f
done
```

现在确保该 Shell 脚本是可执行的：

```bash
chmod +x concat.sh
```

启动 Shell 脚本 `concat.sh`，将其输出重定向到 `sort` 命令，然后重定向到 `uniq` 命令，最后将输出重定向到 CSV 文件 `all_emps.csv`：

```bash
./concat.sh | sort | uniq > all_emps.csv
```

此时，你可能可以将 CSV 文件 `all_emps.csv` 加载到 MySQL 表中，前提是该表不是另一个表的“子”表（且子表行上有有 `CONSTRAINT` 约束）。例如，`customers` 表通常与 `purchase_orders` 表存在一对多的关系，这意味着如果 `customers` 表中没有关联的客户，则无法在在表中插入行。

如果有疑问，尝试将 CSV 文件加载到适当的表中。如果遇到任何错误，请进行必要的修正直到加载过程成功。

这结束了关于数据清洗的第一部分的讨论，接几节包含数据清洗示例，之后将看到数据清洗示例。

### 包含多行记录的 CSV 文件

本节向你如何处理跨行的 CSV 文件。

列表 7.1 显示了 `multi_line.csv` 的内容，将被重新格式化，以便每个记录占据一行：一种方案使用 Pandas，另一种方案使用 `CSV` 库。

***列表 7.1: multi_line.csv***

```csv
id,fname,lname
1,donna,rhymes?
2,dave,"jones$"
3,john,van jones.#
4,stevie,"ray
vaughn#"
```

### Pandas 方案（1）

列表 7.2 显示了 `pandas_multi_line.py` 的内容，它重新格式化 `multi_line.csv` 的内容，使每个记录占据一行。

***列表 7.2: pandas_multi_line.py***

```python
import pandas as pd

filename = 'multi_line.csv'

data = pd.read_csv(filename)

print("data:")

print(data)
```

运行列表 7.2 中的代码，你将看到以下输出：

```text
data:

   id   fname         lname

0   1   donna       rhymes?

1   2    dave        jones$

2   3    john   van jones.#

3   4  stevie  ray

vaughn#

4   5   ralph      emerson#
```

如你所示，之前的输出包含多个元字符。如果有需要，你可以创建一个单行的 `sed` 命令，将这些元字符替换为你选择的任意一个元字符。请查看第 6 章中涉及 `sed` 命令的类似任务。

请注意，列表 7.2 的输出并不是一个真正的 CSV 文件。然而，我们可以生成一个 CSV 文件，如下一节所示。

### Pandas 解决方案（2）

列表 7.3 显示了 `pandas_multi_line2.py` 的内容，该文件对 `multi_line.csv` 的内容进行了重新格式，使得每条记录占据一行，并将数据保存为 CSV 文件。

***列表 7.3: pandas_multi_line2.py***

```python
import sys

import pandas as pd

filename = 'multi_line.csv'

data = pd.read_csv(filename)

# 从数据中移除 "\n" 字符：

columns=["id","fname","lname"]

data2 = data[columns].replace('\\n',' ', regex=True)

# 保存到 CSV 文件：

data2.to_csv("multi_line2.csv",index=False)
```

列表 7.3 从一个导入语句开始，然后初始化变量 `filename`，赋值为此代码示例的 CSV 文件名。接下来的片段填充了 Pandas 数据帧 `data`，然后用不包含换行符的 `data` 内容初始化了 Pandas 数据帧 `data2`。最后一段代码将 `data2` 保存到 CSV 文件 `multi_line2.csv`。运行列表 7.3 中的代码，你将看到一个新文件 `multi_line2.csv`，其内容显示在此处：

```csv
id,fname,lname
1,donna,rhymes?
2,dave,jones$
3,john,van jones.#
4,stevie,ray vaughn#
5,ralph,emerson#
```

如你所示，之前的输出包含多个元字符，你可以使用 `sed-based delimiters1.sh` 脚本中的相同技术将它们替换为相同的列分隔符。

### CSV 解决方案

如果你还没有安装，请使用此命令安装 CSV Python：

```bash
pip3 install csv
```

列表 7.4 显示了 `csv_multi_line.py` 的内容，该文件对 `multi_line.csv` 的内容进行了重新格式，使得每条记录占据一行。

***列表 7.4: csv_multi_line.py***

```python
import csv

filename = 'multi_line.csv'

with open(filename, newline='', encoding='utf-8') as f:
  data = csv.reader(
    f,
    delimiter=',',
    quotechar='"',
    quoting=csv.QUOTE_MINIMAL
  )
  for line in data:
    print("line:", line)
```

列表 7.4 从一个导入语句开始，然后初始化变量 `filename`，赋值为此代码示例的 CSV 文件名。接下来的片段打开 CSV 文件并用其内容初始化 Pandas 数据帧 `data`（注：此处原文为 Pandas data frame，实际为 reader）。最后代码块包含一个循环，遍历数据帧的每一行并打印其内容。运行列表 7.4 中的代码，你将看到以下输出：

```text
line: ['id', 'fname', 'lname']
line: ['1', 'donna', 'rhymes?']
line: ['2', 'dave', 'jones$']
line: ['3', 'john', 'van jones.#']
line: ['4', 'stevie', 'ray\nvaughn#']
line: ['5', 'ralph', 'emerson#']
```

### CSV 文件、多行记录以及 AWK 命令

本节向你展示如何处理包含跨行记录的 CSV 文件，这些记录由空行分隔。

列表 7.5 显示了 `multi_line.csv` 的内容，该内容将被重新格式化，使得每条记录占据一行：一种解决方案涉及 Pandas，另一种解决方案涉及 CSV 库。

***列表 7.5: multi_line_records.csv***

```text
nancy jones

marketing dept

san francisco

dave smith

sales dept

chicago

steve anderson

marketing dept

seattle
```

列表 7.6 显示了 `multi_line_records.sh` 的内容，该文件对 `multi_line.csv` 的内容进行了重新格式，使得每条记录占据一行。

***列表 7.6: multi_line_records.sh***

```bash
# 记录由空行分隔。

input_file="multi_line_records.csv"

awk '
BEGIN { RS = "" ; FS = "\n" }
{
  printf("%s,%s,%s\n", $1, $2, $3)
}
' < $input_file
```

列表 7.6 首先初始化变量 `input_file`，赋值为此代码示例的 CSV 文件名。列表 7.6 的后续部分包含一个 `awk` 脚本，它将每个输入以逗号分隔的形式打印，可以重定向到 CSV 文件。运行列表 7.6 中的代码，你将看到：

```text
nancy jones,marketing dept,san francisco
dave smith,sales dept,chicago
steve anderson,marketing dept,seattle
```

### 跨行的引号字段（可选）

本节被标记为“可选”，主要是因为涉及的是一种你日常工作中可能不会遇到的 CSV 文件。具体而言，该 CSV 文件包含多行，且包含一个跨行的引号字段。到目前，你可能已经意识到 `awk` 工具对于数据清洗以及将 CSV 文件（或通用文本文件）转换为通过 Pandas 处理的格式非常有用。考虑 `awk` 在第 6 章最后一个示例中计算小计的便利性：这仅通过一行代码就实现了。对于某些人来说，`awk` 是一个强大的命令行工具，可以对几乎任何类型的文本文件或 CSV 文件进行预处理。

列表 7.7 的部分相当复杂且不直观，这通常发生在你需要字符级分析，并且需要维护和检查有关先前字符以及当前字符的“状态”信息依赖时，这两者都出现在此代码示例中。

列表 7.7 显示了 `multi_line3.csv` 的内容，列表 7.8 显示了 `split_quotes.sh` 的内容，该文件对 `multi_line3.csv` 进行重新格式，使得每条记录恰好包含三个字段。

***列表 7.7: multi_line3.csv***

```csv
id,fname,lname
1,
donna,
rhymes?
2,dave,"jones$"
3,john,van jones.#
4,stevie,"ray
vaughn#"
5,ralph,emerson#
```

***列表 7.8: split_quotes.sh***

```bash
# Records are separated by blank lines

# PART 1: create a single string

interfile1="temp_single_line1.csv"
interfile2="temp_single_line2.csv"
interfile3="temp_single_line3.csv"
csv_file="multi_line3.csv"

cat $csv_file | awk -F"," '
BEGIN { count = 1; colCount = 3 }
{
  printf("%s", $0)
  if( $0 !~ /,$/ ) {
     printf(",")
  } else {
    if( $0 !~ /^[0-9]/ ) {
      if( count % colCount == 0) {
        printf(",")
      }
      count += 1
    }
  }
}' > $interfile1

# id,fname,lname,1,donna,rhymes?,2,dave,"jones$",3,john,van jones.#,4,stevie,"ray,vaughn#",5,ralph,emerson#,

# PART 2: replace patterns like "abc,def" with "abcZdef"

cat $interfile1 | awk -F"," '
{
  for(i=1; i<=NF; i++) {
    if( $i ~ /^"/ && $(i+1) ~ /"$/ ) {
       printf("%sZ",$i)
    } else {
       printf("%s,",$i)
    }
  }
}' > $interfile2

# PART 3: ensure that each line contains three fields

cat $interfile2 | awk -F',' '
BEGIN { start_quote = 0; end_quote = 0; quote = 0; colCount = 3 }
{
  for(i=1; i<=NF; i++) {
     if($i ~ /^"/ && $i ~ /"$/ ) {
       printf("%s",$i)
     }
     else if($i !~ /^"/ && $i !~ /"$/ ) {
       printf("%s,", $i)
     }
     else {
        if($i ~ /^"/ ) {
          printf("%s,",$i)
          quote = 1
          start_quote = 1
        } else {
          if($i ~ /"$/ ) {
            printf("%s",$i)
            quote = 1
            end_quote = 1
          }
        }
     }
     if( quote == 0) {
       if(i % colCount == 0) {
         print ""
       }
```



```bash
} else {

  if(start_quote == 1 && end_quote == 1) {

    quote = 0

    start_quote = 0

    end_quote = 0

  }

}

}

' > $interfile3

cat $interfile3 | sed -e 's/Z/,/' -e '/^,,/d' -e 's/,$//'
```

`Listing 7.8` 初始化了三个变量，格式为 `temp_single_linex.csv` 的 CSV 文件名，其中 `x` 被替换为 `1`、`2` 和 `3`，同时初始化变量 `csv_file` 为 CSV 文件 `multi_line3.csv`。

接下来，`Listing 7.8` 包含（“PART 1”）一个带有 `BEGIN` 的 `awk` 脚本，它打印每行输入，然后执行以下条件逻辑。如果输入行*不是*以“，”结尾，则打印一个“，”。否则，如果输入行*不是*以数字开头且 `count` 的值是 3 的倍数，则打印一个“，”，如下所示：

```bash
if( $0 !~ /^[0-9]/ ) {

  if( count % colCount == 0) {

    printf(",")

  }

  count += 1

}
```

你可以看到，前面的代码块让人想起了第 `6` 章中 shell 脚本 `delimiter1.sh` 的逻辑。

`Listing 7.8` 的下部分（“PART 2”）是另一个 `awk` 脚本，其目的是将嵌套的“，”替换为字母 `Z`。字母 `Z` 的选择是任意的，你可以将其替换为 CSV 文件中未出现的其他字符或字符串。

前面的逻辑通过在字段分别包含起始引号和结束引号时将变量 `start_quote` 和 `end_quote` 设置为值 `1` 来检测嵌套的“，”。执行上述判断的代码涉及检查当前字段与*下一个*字段的内容，如下所示：

```bash
if( $i ~ /^"/ && $(i+1) ~ /"$/ ) {
```

你可以看到，前面的代码段检查字段 `i` 是否*起始*于引号（"）以及字段 `(i+1)` 是否*结束*于引号（"），在这种情况下将打印字母 `Z`。

`Listing 7.8` 的下部分（“PART 3”）是一个 `awk` 脚本，其目的是打印包含三个字段的输出行。不包含引号的字段或包含平衡引号的字段将直接打印。其他字段将检查起始引号和结束引号。每当循环变量 `i` 是 3 的倍数时，就会打印换行符，并重置*旨在*让你离开舒适圈的变量 `start_quote` 和 `end_quote`。

## 项目概述

（注：此处调整了原文逻辑顺序的标题标题）

`Listing 7.8` 初始化了三个变量，格式为 `temp_single_linex.csv` 的 CSV 文件名，其中 `x` 被替换为 `1`、`2` 和 `3`，同时初始化变量 `csv_file` 为 CSV 文件 `multi_line3.csv`。

接下来，`Listing 7.8` 包含（“PART 1”）一个带有 `BEGIN` 的 `awk` 脚本，它打印每行输入，然后执行以下条件逻辑。如果输入行*不是*以“，”结尾，则打印一个“，”。否则，如果输入行*不是*以数字开头且 `count` 的值是 3 的倍数，则打印一个“，”，如下所示：

你可以看到，前面的代码块让人想起了第 `6` 章中 shell 脚本 `delimiter1.sh` 的逻辑。

## 为什么要做这个项目？

`Listing 7.8` 的下部分（“PART 2”）是另一个 `awk` 脚本，其目的是将嵌套的“，”替换为字母 `Z`。字母 `Z` 的选择是任意的，你可以将其替换为 CSV 文件中未出现的其他字符或字符串。

前面的逻辑通过在字段分别包含起始引号和结束引号时将变量 `start_quote` 和 `end_quote` 设置为值 `1` 来检测嵌套的“，”。执行上述判断的代码涉及检查当前字段与*下一个*字段的内容，如下所示：

`Listing 7.8` 的下部分（“PART 3”）是一个 `awk` 脚本，其目的是打印包含三个字段的输出行。不包含引号的字段或包含平衡引号的字段将直接打印。其他字段将检查起始引号和结束引号。每当循环变量 `i` 是 3 的倍数时，就会打印换行符，并重置*旨在*让你离开舒适圈的变量 `start_quote` 和 `end_quote`。

## 项目任务

此项目需要多个 CSV 文件来维护国家、城市、场馆和日期等信息。部分任务包括：

- 步骤 1：填充国家和国际代码 CSV 文件
- 步骤 2：填充每个国家的城市列表 CSV 文件
- 步骤 3：根据国家代码生成城市代码
- 步骤 4：生成填充 MySQL 中 `city_code` 表的 SQL 文件
- 步骤 5：将乐队相关信息转换为 CSV 文件
- 步骤 6：将乐队相关信息转换为 CSV 文件
- 步骤 7：生成活动日历（COE）CSV 文件

执行上述每个任务的代码示例如下：

- 步骤 1：手动操作
- 步骤 2：手动操作
- 步骤 3：`construct_city_codes.py`（Python）
- 步骤 4：`city_codes_sql.sh`（awk 脚本）
- 步骤 5：`BandsToCSV.java`（Java 程序）
- 步骤 6：`generate_coe.py`（Python）
- 步骤 7：`generate_project.sh`（shell 脚本）

在某些情况下，执行给定任务有多个代码示例。例如，步骤 5 也可以通过 Python 文件 `bands_to_csv.py` 完成。

在前面的每个步骤以及手动执行的步骤中都会生成示例数据或代码片段：

```text
• 001,usa

• 039,100,firenze

• france,antibe,nice,paris,st_jeannet

• INSERT INTO city_codes VALUES ( 039,100,firenze );

• 100,The Data Wranglers,Dave Pallai
```

为了确保清晰：此项目中的大多数步骤必须按照前面列表中所示的顺序执行。例外是步骤 4，它可以在步骤 3 之后的任何时间执行。

## 生成国家代码

在为国家生成唯一 ID 的各种方法中，一种简单的方法是根据每个国家的国际电话前缀来识别它，这些前缀是唯一的。在项目中，`country_codes.csv` 是通过在线查找包含此类链接手动创建的。例如，列表 7.9 显示了 `country_codes.csv` 的内容，包含了该项目的国家名称及其对应的国际代码。

**列表 7.9：`country_codes.csv`**

```csv
001,usa
033,france
034,spain
039,italy
044,uk
049,germany
052,mexico
081,japan
```

## 准备国家城市列表

列表 7.10 显示了 `countries_cities.csv` 的内容，包含国家名称和属于这些国家的城市列表。

**列表 7.10：`countries_cities.csv`**

```csv
italy,firenze,milano,roma,venezia
france,antibe,nice,paris,st_jeannet
germany,berlin,frankfurt
spain,barcelona,madrid
uk,liverpool,london,manchester
mexico,mexico_city,tijuana
```

## 从国家代码生成城市代码：AWK

列表 7.11 显示了 `construct_city_codes.sh` 的内容，说明了如何为属于给定国家的每个城市生成唯一代码。

**列表 7.11：`construct_city_codes.sh`**

```bash
FILE1="country_codes.csv"

FILE2="countries_cities.csv"

rm -f city_codes.csv

awk -F"," '

BEGIN {

   FS=","; OUT_FILE="city_codes.csv";

   prev_name = ""; city_name = "";

   start_code=100; curr_code = 100;

   city_code = ""; incr_code = 100

   printf("=> BEGIN-PROCESSING: %s\n",ARGV[1])

   while(getline line < ARGV[1]){

     #format: country-code,country-name

     split(line,data)

     code = data[1]

     country = data[2]

     #printf("code: %s country: %s\n",code,country)

     country_code[country] = code

     code_country[code] = country

   }

   close(ARGV[1])

}

##########################################

# 读取 countries_cities.csv 中的每行

### 将每行拆分为城市列表

### 生成城市代码包含：

# country_code, curr_code, city_name

# countries_cities.csv 中的示例行：

# italy,firenze,milano,roma,venezia

##########################################

{

   #sample: italy,firenze,milano,roma,venezia

   split($0,data)

   code    = data[1]

   country = data[2]

   #printf(" code = %s country = %s\n", code, country)

   #printf("=> CHECK CODE FOR: %s x\n", country_code[code])

   if(country_code[country] == "") {

      printf("=> MAIN-CITIES in %s:\n",$0)

      curr_code = start_code

      for(i=2; i<=NF; i++) {

         city_code = country_code[$1] "_" curr_code "_" i

         printf("=> constructed city_code:%s\n",city_code)

         print city_code >> OUT_FILE

         curr_code += incr_code

      }

      if(prev_name == "") {

        city_name = $1

      } else {

        if(prev_name != $1) {

          # 处理不同的国家：

          prev_name = city_name

          city_name = $1

          curr_code = start_code

        }

      }

      if(city_code == 0) city_code = start_code

   } else {

      #printf("=> SKIPPING INVALID LINE: %s\n",$0)

   }

} $FILE1 $FILE2

'
```

列表 7.11 使用 CSV 文件 `country_codes.csv` 和 `countries_cities.csv` 的名称初始化 `FILE1` 和 `FILE2`，随后是一个初始化多个字符串和数值变量的 `awk` 脚本。接下来，列表 7.11 包含一个 `awk` 脚本，其 `BEGIN` 块包含一个循环，读取 `country_codes.csv` 文件的内容（国家名称和相关的三位代码）。这些值对用于填充 `country_code` 和 `code_country` 字典。`country_code` 的键是国家名称，值三位代码，而 `code_country` 的键值相反。

下一块代码是 `awk` 脚本的主执行块，它涉及条件逻辑和一个大的块。设置条件逻辑的原因是 `awk` 无论是否在 `BEGIN` 块中处理过，都会处理结尾指定的两个输入文件。由于 `awk` 的性质，列表 7.11 两次处理 `FILE1`：一次在 `BEGIN` 块中，另一次在主执行块中（这是 `awk` 的特性还是功能？）。因此，主块中的代码必须跳过 `FILE1` 中的行，并仅处理 `FILE2` 中的行。

跳过 `FILE1` 的方法非常简单：`FILE1` 中的行格式为 `country_code,country`（例如 `001,usa`），并且代码 `001` 在 `country_code` 字典中不存在。因此，只有 CSV 文件 `FILE2` 中的行满足此条件：

```awk
country_code[country] == ""
```

此 `if` 语句内部的代码包含一个循环，为 `FILE2` 中每行列出的每个城市构建 `city_code`。核心思想是，每个城市的 `city_code` 是通过拼接其国家代码、基于 `curr_code` 值生成的数字以及城市本身构建的。例如，接下来的行指定了意大利（其国家代码为 `039`）以及四个城市：

```text
firenze,milano,roma,venezia
```

因此，前一行中意大利每个城市的 `city_code` 如下：

```text
039_100_firenze
039_200_milano
039_300_roma
039_400_venezia
```

运行列表 7.11 中的代码，你将看到以下输出：

```text
=> BEGIN-PROCESSING: country_codes.csv

=> MAIN-CITIES in italy,firenze,milano,roma,venezia:

=> constructed city_code:039_100_firenze

=> constructed city_code:039_200_milano

=> constructed city_code:039_300_roma

=> constructed city_code:039_400_venezia

=> MAIN-CITIES in france,antibe,nice,paris,st_jeannet:

=> constructed city_code:033_100_antibe

=> constructed city_code:033_200_nice

=> constructed city_code:033_300_paris

=> constructed city_code:033_400_st_jeannet

=> MAIN-CITIES in germany,berlin,frankfurt:

=> constructed city_code:049_100_berlin

=> constructed city_code:049_200_frankfurt

=> MAIN-CITIES in spain,barcelona,madrid:

=> constructed city_code:034_100_barcelona

=> constructed city_code:034_200_madrid

=> MAIN-CITIES in uk,liverpool,london,manchester:

=> constructed city_code:044_100_liverpool

=> constructed city_code:044_200_london

=> constructed city_code:044_300_manchester

=> MAIN-CITIES in mexico,mexico_city,tijuana:

=> constructed city_code:052_100_mexico_city

=> constructed city_code:052_200_tijuana
```

列表 7.12 显示了由列表 7.11 代码生成的 `city_codes.csv` 内容。

**列表 7.12：`city_codes.csv`**

```text
039_100_firenze
039_200_milano
039_300_roma
039_400_venezia
033_100_antibe
033_200_nice
033_300_paris
033_400_st_jeannet
049_100_berlin
049_200_frankfurt
034_100_barcelona
034_200_madrid
044_100_liverpool
044_200_london
044_300_manchester
052_100_mexico_city
052_200_tijuana
```

# 从国家代码生成城市代码：Python

Listing 7.13 显示了 `construct_city_codes2.py` 的内容，它展示了如何为给定国家下的每个城市生成唯一代码。

### 列表 7.13：`construct_city_codes2.py`

```python
import csv

FILE1="country_codes.csv"
```



`FILE2="countries_cities.csv"`

`OUTFILE1="python_city_codes.txt"`

`OUTFILE2="python_city_codes.csv"`

`OUTFILE3="python_city_codes.sql"`

`prev_name = ""`

`city_name = ""`

`curr_name = ""`

`start_code = 100`

`curr_code = 100`

`city_code1 = ""`

`city_code2 = ""`

`incr_code = 100`

`code_country = {}`

`country_code = {}`

# STEP 1: 读取带有代码和国家值的文件

```
print("=> BEGIN-PROCESSING:",FILE1)

with open(FILE1, mode ='r')as file:

  # 读取 CSV 文件

  csvFile = csv.reader(file)

  # 显示 CSV 文件的内容

  for line in csvFile:

    code    = line[0]

    country = line[1]

    country_code[country] = code

    code_country[code] = country
```

# STEP 2: 读取国家和城市文件

```
##########################################
# 读取 countries_cities.csv 中的每一行
### 将每行分割为城市列表
# 生成包含以下内容的城市代码：
# country_code, curr_code, city_name
# countries_cities.csv 中的示例行：
# italy,firenze,milano,roma,venezia
##########################################

print("=> BEGIN-PROCESSING:",FILE2)

#sample: italy,firenze,milano,roma,venezia
with open(FILE2, mode ='r')as file:

  # 读取 CSV 文件

  csvFile = csv.reader(file)

  # 打开两个输出文件：

  # 创建 txt_writer1:

  txt_writer1 = open(OUTFILE1,'w')

  # 创建 csv_writer2:

  csv_writer2 = open(OUTFILE2,'w')

  # 创建 sql_writer3:

  sql_writer3 = open(OUTFILE3,'w')

  for line in csvFile:

    country = line[0]

    code = country_code[country]

    #print("full line:",line)

    #print(" code = ",code," country = ",country)

    #print("=> MAIN-CITIES in:",line)

    curr_code = start_code

    column_count = len(line)

    for i in range(2,column_count):

      city_code1 = str(code) + "_" +

                   str(curr_code) + "_" + str(line[i])

      city_code2 = str(code) + "," +

                   str(curr_code) + "," + str(line[i])

      print("=> constructed city_code1:",city_code1)

      # 根据城市代码生成 SQL 语句：

      sql_stmt = 'INSERT INTO city_codes VALUES ('

      sql_stmt += str(code)+','+str(curr_code)+',"'+line[i]+'");\n'

      # 将 SQL 语句写入 SQL 文件：

      sql_writer3.write(sql_stmt)

      # 将城市代码写入 CSV 文件：

      txt_writer1.write(city_code1+"\n")

      #curr_code += incr_code

      # 将城市代码写入 TXT 文件：

      csv_writer2.write(city_code2+"\n")

      curr_code += incr_code

    if(curr_name == None):

      curr_name = line[1]

    else:

      if(curr_name != line[1]):

        # 处理不同的国家：

        prev_name = curr_name

        curr_name = line[1]

        curr_code = start_code

    if(city_code1 == ""): city_code1 = start_code

    if(city_code2 == ""): city_code2 = start_code
```

# STEP 3: 关闭 city_code 文件

```
#city_code_file.close()
```

`Listing 7.13` 包含了 `Listing 7.11` 的 Python 版本，后者包含一个基于 `awk` 的 shell 脚本，用于生成城市代码。由于你对 shell 编程的熟悉程度可能低于 Python，`Listing 7.11` 包含了代码的详细说明，而 Python 代码则省略了详细说明。由于逻辑流是相同的，主要的区别在于特定语言的语法，你可以逐行进行比较。如果你运行 `Listing 7.13` 中的代码，你将看到与 `Listing 7.12` 基本上完全相同的输出。

`Listing 7.13` 和 `Listing 7.12` 之间有一个显著的区别。`Listing 7.13` 中加粗显示的代码片段用于生成 SQL 语句。

# 为乐队成员生成 CSV 文件（JAVA）

`Listing 7.16` 显示了 `bands.xml` 的内容，`Listing 7.17` 显示了 `BandsToCSV.java` 的内容，展示了如何将 XML 文件转换为 CSV 文件。

### 列表 7.16: bands.xml

```xml
<bands>
  <band>
    <band_id>
      100
    </band_id>
    <band_name>
      The Data Wranglers
    </band_name>
    <band_member>
      Dave Pallai
    </band_member>
    <band_member>
      Jennifer Blaney
    </band_member>
  </band>
  <band>
    <band_id>
      200
    </band_id>
    <band_name>
      The Data Cleaners
    </band_name>
    <band_member>
      Raymond Reddington
    </band_member>
    <band_member>
      Scary Joe
    </band_member>
    <band_member>
      The Smoother
    </band_member>
  </band>
</bands>
```

### 列表 7.17: BandsToCSV.java

```java
import csv
import org.w3c.dom.Document;
import org.w3c.dom.Element;
import org.w3c.dom.Node;
import org.w3c.dom.NodeList;
import org.xml.sax.SAXException;
import javax.xml.parsers.DocumentBuilder;
import javax.xml.parsers.DocumentBuilderFactory;
import javax.xml.parsers.ParserConfigurationException;
import java.io.File;
import java.io.FileWriter;
import java.io.IOException;
import java.io.InputStream;

public class BandsToCSV
{
   private static final String FILENAME = "bands.xml";

   public static void main(String[] args) {
      String filename = "bandmembers.csv";
      File outfile = null;
      FileWriter csvWriter = null;

      // 1) create a file object:
      outfile = new File(filename);

      // 2) create a FileWriter object:
      try {
        csvWriter = new FileWriter("bandmembers.csv");
      } catch (IOException e) {
        System.out.println("An error occurred:");
        e.printStackTrace();
      }

      // 3) process the XML file:
      DocumentBuilderFactory dbf =
                         DocumentBuilderFactory.newInstance();
      try {
         DocumentBuilder db = dbf.newDocumentBuilder();
         Document doc = db.parse(new File(FILENAME));
         doc.getDocumentElement().normalize();
         System.out.println("ROOT: " +
                      doc.getDocumentElement().getNodeName());

         NodeList bandList = doc.getElementsByTagName("band");
         for (int idx = 0; idx < bandList.getLength(); idx++) {
            Node node = bandList.item(idx);
            if (node.getNodeType() == Node.ELEMENT_NODE) {
               Element element = (Element) node;

               // 4) the id of the band:
               String band_id = element.getElementsByTagName("band_id")
                                       .item(0).getTextContent();
               band_id = band_id.replaceAll("\\s", "");
               band_id = band_id.replaceAll("\\n", "");
               System.out.println("band_id = "+band_id);

               // 5) the name of the band:
               String band_name =
                         element.getElementsByTagName("band_name")
                                .item(0).getTextContent();
               band_name = band_name.trim();
               band_name = band_name.replaceAll("\\n", "");
               System.out.println("band_name = "+band_name);

               // 6) the band members:
               NodeList memberList =
                          element.getElementsByTagName("band_member");
               for (int idx2=0; idx2<memberList.getLength(); idx2++)
               {
                  Node memberNode = memberList.item(idx2);
                  if (memberNode.getNodeType() == Node.ELEMENT_NODE)
                  {
                     Element element2 = (Element) memberNode;
                     System.out.println("Current Element: " +
                       memberNode.getNodeName());
                     String band_member =
                       memberList.item(idx2).getTextContent();
                     //band_member = band_member.replaceAll("\\s", "");
                     band_member = band_member.trim();
                     band_member = band_member.replaceAll("\\n", "");
                     System.out.println("band_member = "+band_member);

                     // 7) write a string to the CSV file:
                     csvWriter.write(band_id+","+
                                     band_name+","+
                                     band_member+"\n");
                  }
               }
            }
         }
         csvWriter.close();
      } catch (ParserConfigurationException | SAXException | IOException e) {
        e.printStackTrace();
      }
   }
}
```



`Listing 7.17` 从多个导入开始，然后定义了 Java 类 `BandsToCSV`，该类包含一个 `main()` 方法，并分为六部分。第一部分创建文件对象 `outfile`，第二部分创建 `FileWriter` 对象 `csvWriter`。

第三部分是最长的部分，同时也包含了第四和第五部分。第三部分的开头包含一个 `try/catch` 块，在其中构建了一个 `Document` 对象 `doc`，它是 XML 文档的根节点，包含了关于乐队的信息。

接下来，变量 `bandList` 被初始化，它代表节点列表，列表中的每个节点都是关于一个乐队的信息。第三部分的后续部分是一个 `for` 列表，用于遍历变量 `bandList` 中的项。如果每个项都是 `ELEMENT_NODE`，则执行第四部分，这涉及从当前节点中提取 `band_id` 的值。

此时执行第五部分，它提取当前节点中 `band_name` 的值，接着是第六部分，第 6 部分由一个 `for` 循环组成，用于从当前节点中提取所有其他与乐队相关的信息。注意，第 6 部分中的循环包含条件逻辑：如果当前元素是 `ELEMENT_NODE` 类型，则对变量 `band_member` 的内容进行修剪以删除空格。

我们现在到了第 7 部分，这是 `Listing 7.17` 中的最后部分，也是以下以 CSV 格式写入乐队信息的代码片段所在的位置：

```java
csvWriter.write(band_id+","+
                                     band_name+","+
                                     band_member+"\n");
```

运行 `Listing 7.17` 中的代码，你将看到以下输出：

```text
ROOT: bands

band_id = 100

band_name = The Data Wranglers

Current Element: band_member

band_member = Dave Pallai

Current Element: band_member

band_member = Jennifer Blaney

Current Element: band_member

band_member = Raymond Reddington

band_id = 200

band_name = The Data Cleaners

Current Element: band_member

band_member = Scary Joe

Current Element: band_member

band_member = The Smoother
```

`Listing 7.18` 显示了由 `Listing 7.17` 中的 Java 代码生成的 CSV 文件 `bandmembers.csv` 的内容。

### Listing 7.18：`bandmembers.csv`

```csv
100,The Data Wranglers,Dave Pallai

100,The Data Wranglers,Jennifer Blaney

100,The Data Wranglers,Raymond Reddington

200,The Data Cleaners,Scary Joe

200,The Data Cleaners,The Smoother
```

## 使用 Python 为乐队成员生成 CSV 文件

`Listing 7.19` 显示了 `BandsToCSV.java` 的内容，它演示了如何从 XML 文档 `bandmembers.csv` 生成文本文件以及 CSV 文件。

### Listing 7.19：`bands_to_csv.py`

```python
from xml.etree import cElementTree as ET

INFILE1 = "bands.xml"

OUTFILE1 = "python_bandmembers.txt"

OUTFILE2 = "python_bandmembers.csv"

# create txt_writer1:
txt_writer1 = open(OUTFILE1, 'w')

# create csv_writer2:
csv_writer2 = open(OUTFILE2, 'w')

band_id = ""

band_name = ""

band_member = ""

xml_data = ET.parse(INFILE1).getroot()

for band in xml_data.iter('band'):
    for child in band:
        # print("child: ", child)

        print("name: ", child.tag)

        name = child.tag

        if name == "band_id":
            band_id = child.text

            band_id = band_id.strip()

            print("band_id =     ", band_id)

        elif name == "band_name":
            band_name = child.text

            band_name = band_name.strip()

            print("band_name =   ", band_name)

        elif name == "band_member":
            band_member = child.text

            band_member = band_member.strip()

            print("band_member = ", band_member)

            # the_member = child.text
            # the_member = the_member.strip()
            # print("the_member = ", the_member)

        if band_id != "" and band_name != "" and band_member != "":
            line1 = str(band_id) + "_" + band_name + "_" + band_member

            line2 = str(band_id) + "," + band_name + "," + band_member

            print("=> constructed line1:", line1)

            print("=> constructed line2:", line2)

            # write line to CSV file:
            txt_writer1.write(line1 + "\n")

            # write line to TXT file:
            csv_writer2.write(line2 + "\n")

            # band_id = ""
            # band_name = ""

            band_member = ""
```

列表 7.19 首先为现有文件初始化一些变量，为输出文件初始化变量，然后将变量 `xml_data` 初始化为 `bands.xml` 文件的根节点，该文件包含与乐队的信息，如下：

```python
xml_data = ET.parse(INFILE1).getroot()
```

列表 7.19 的下一部分是一个嵌套循环，它遍历 `band` 元素，对于每个乐队，还有另一个循环来遍历当前乐队的元素。接下来，条件逻辑检查是否存在任何 `band_id`、`band_name` 和 `band_member` 节点，并初始化相应变量的值。

最后的 `if` 语句检查这三个变量是否已填充了值，如果是，则构建一个基于 CSV 的输出行并写入 CSV 文件；同样地，还会构建并写入另一个基于文本的输出行到关联文本文件中。运行列表 7.19 中的代码，你将看到以下输出：

```text
name:  band_id

band_id =      100

name:  band_name

band_name =    The Data Wranglers

name:  band_member

band_member =  Dave Pallai

=> constructed line1: 100_The Data Wranglers_Dave Pallai

=> constructed line2: 100,The Data Wranglers,Dave Pallai

name:  band_member

band_member =  Jennifer Blaney

=> constructed line1: 100_The Data Wranglers_Jennifer Blaney

=> constructed line2: 100,The Data Wranglers,Jennifer Blaney

name:  band_id

band_id =      200

name:  band_name

band_name =    The Data Cleaners

name:  band_member

band_member =  Raymond Reddington

=> constructed line1: 200_The Data Cleaners,Raymond Reddington

=> constructed line2: 200,The Data Cleaners,Raymond Reddington

name:  band_member

band_member =  Scary Joe

=> constructed line1: 200_The Data Cleaners,Scary Joe

=> constructed line2: 200,The Data Cleaners,Scary Joe

name:  band_member

band_member =  The Smoother

=> constructed line1: 200_The Data Cleaners,The Smoother

=> constructed line2: 200,The Data Cleaners,The Smoother
```

同样检查列表 7.19 所在的目录，你会看到两个新文件：

```text
python_bandmembers.txt
python_bandmembers.csv
```

## 生成日程（COE）

列表 7.20 显示 CSV 文件 `concert_dates.csv` 的内容，它包含一个活动日程：额外的详细信息存储在项目中创建的其他 CSV 文件中。

### 列表 7.20：`concert_dates.csv`

```csv
100,039,vicenza,01/05/22

100,039,vicenza,01/05/22,50

100,033,paris,01/15/22,80

100,044,london,02/02/22,70

100,049,berlin,02/09/22,75

100,081,tokyo,02/19/22,100

200,039,vicenza,01/08/22,50

200,033,paris,01/18/22,70

200,044,london,02/05/22,60

200,049,berlin,02/13/22,80

200,081,tokyo,02/27/22,100
```

列表 7.20 中的每一行都包含以下格式的细节：

```text
band_code,country_code,date,price
```

目标 CSV `concert_coe.csv` 将增强 `concert_dates.csv` 的内容，使得每行包含以下格式的信息：

```text
band_code,band_name,country_name,date,price
```

注意日期格式为 `dd/mm/yyyy`，价格列为 `USD`（但不需要是真实的价格）。我们只需要提供新列 `band_name` 和 `country_name`。

列表 7.21 显示了 `generate_coe.py` 的内容，展示了如何通过两个额外的列增强 CSV 文件 `concert_dates.csv` 来生成 CSV 文件 `concert_coe.csv`。

### 列表 7.21：`generate_coe.py`

```python
import pandas as pd

import numpy as np

# 1) 读取输入文件 concert_dates.csv
# Header 行: band_code,country_code,date,price
# 示例行: 100,039,vicenza,01/05/22,50

concert_dates_file = "concert_dates.csv"

# 2) 读取 python_bandmembers.csv（乐队名称和成员）
# 示例行: 100_The Data Wranglers_Dave Pallai

band_members_file = "python_bandmembers.csv"

# 3) 读取 country_codes.csv（国家和代码）
# 示例行: 039,italy

cc_codes_file = "country_codes.csv"

# 4) 创建输出文件 calendar_coe.csv:
# Header 行: band_code,band_name,country_code,country_name,date,price
# 示例行: The Data Wranglers,italy,vicenza,01/05/22,50

outfile1 = "calendar_coe.csv"

# 5) 填充三个 dataframe:

concert1_df = pd.read_csv(concert_dates_file)

band2_df = pd.read_csv(band_members_file)

cc3_df = pd.read_csv(cc_codes_file)

# 6) 添加列标签:
# 现有行: 100,039,vicenza,01/05/22,50

concert1_df.columns = [
    'band_code',
    'country_code',
    'City',
    'Concert Date',
    'Tickets (USD)'
]

band2_df.columns = [
    'band_code',
    'band_name',
    'band_members'
]

cc3_df.columns = [
    'country_code',
    'country_name'
]

# 7) 提取唯一乐队代码和名称数组:

bands_unique_codes = band2_df.band_code.unique()

bands_unique_names = band2_df.band_name.unique()

# 8) 从唯一乐队代码和名称创建字典:

bands_codes_names_dict = {}

for code, name in zip(bands_unique_codes, bands_unique_names):
    bands_codes_names_dict[code] = name

# 9) 插入列 "Band Name":

concert1_df['Band Name'] = concert1_df['band_code'].map(
    bands_codes_names_dict
)

# 10) 从唯一国家代码和名称创建字典:

country_code_to_name_dict = {}

for index, row in cc3_df.iterrows():
    country_code = row['country_code']

    country_name = row['country_name']

    country_code_to_name_dict[country_code] = country_name

# 11) 插入列 "Country":

concert1_df['Country'] = concert1_df['country_code'].map(
    country_code_to_name_dict
)

# 12) 删除乐队代码和国家代码:

del concert1_df['band_code']

del concert1_df['country_code']

print("*** Concert Details ***")

print(concert1_df)

print()

# 13) 将会详情保存到 CSV 文件:

concert1_df.to_csv(outfile1, index=False)
```



Listing 7.21 的后续部分通过此代码示例第一部分列出的文件中的数据填充三个数据框。接下来的三个部分为数据框添加列名，如果输入文件包含标题行，则这一步不是必须的。

Listing 7.21 的后续部分提取了唯一的乐队代码（band codes）及其对应的乐队名称，以创建一个包含代码/名称值对的 Python 字典，我们将在稍后的代码示例中使用它。

以类似的方式，Listing 7.21 的后续部分提取了唯一的国家代码及其对应的名称，以创建一个包含 `country_code/country_name` 对的 Python 字典，我们也将在稍后的代码示例中使用它。

下一个代码块为 `concert1_df` 中的每行插入一列，其列名为与乐队代码对应的乐队名称。另一个代码块为 `concert1_df` 中的每行插入一列，其列名为与国家代码对应的国家名称。

接下来的两个 `del` 语句从 `concert1_df` 数据框中删除 `band_code` 和 `country_code` 列（可选步骤）。

最后，显示数据框 `concert1_df` 的内容，然后数据框的内容保存为 CSV 文件。运行 Listing 7.21 中的代码，你将看到以下输出：

```
*** Concert Details ***

      City Concert Date  Tickets (USD)           Band Name  Country

0    paris   01/15/2022             80  The Data Wranglers   france

1   london   02/02/2022             70  The Data Wranglers       uk

2   berlin   02/09/2022             75  The Data Wranglers  germany

3    tokyo   02/19/2022            100  The Data Wranglers    japan

4  vicenza   01/08/2022             50   The Data Cleaners    italy

5    paris   01/18/2022             70   The Data Cleaners   france

6   london   02/05/2022             60   The Data Cleaners       uk

7   berlin   02/13/2022             80   The Data Cleaners  germany

8    tokyo   02/27/2022            100   The Data Cleaners    japan
```

### 项目自动化脚本

Listing 7.22 显示了 `generate_project.sh` 的内容，该脚本自动化了本章之前讨论的项目创建步骤。

***列表 7.22: generate_project.sh***

```
echo "Assigning code to countries..."

#=> manual process

echo "Assigning code to cities..."

python3 construct_city_codes.py

#=> generates city_codes.csv

echo "Generate SQL for city codes..."

./city_codes_sql.sh

#=> generates city_codes.sql

echo "Converting personnel (XLSX) to CSV..."

python3 save_xlsx_to_csv.py

#=> generates personnel.csv

echo "Converting bands_list (XML) to CSV..."

# via Java:

java BandsToCSV

# via Python:

#python3 bands_to_csv.py

#=> generates bandmembers.csv

echo "Generating CSV calendar of events (COE)..."

python3 generate_coe.py

#=> generates complete calendar

#echo "Generating SQL script for COE..."

#exercise

#echo "Inserting COE into MySQL..."

#exercise
```

Listing 7.22 包含了本章之前讨论过的各种可执行文件，它们按顺序调用，以自动按正确顺序执行任务。运行 Listing 7.22 中的代码，你将看到以下输出：

```
Assigning code to countries...

Assigning code to cities...

=> BEGIN-PROCESSING: country_codes.csv

=> BEGIN-PROCESSING: countries_cities.csv

=> constructed city_code1: 039_100_milano

=> constructed city_code1: 039_200_roma

=> constructed city_code1: 039_300_venezia

=> constructed city_code1: 033_100_nice

=> constructed city_code1: 033_200_paris

=> constructed city_code1: 033_300_st_jeannet

=> constructed city_code1: 049_100_frankfurt

=> constructed city_code1: 034_100_madrid

=> constructed city_code1: 044_100_london

=> constructed city_code1: 044_200_manchester

=> constructed city_code1: 052_100_tijuana

Generate SQL for city codes...

Contents of df1:

   Unnamed: 0 fname  lname                       Role gender  country

0           0  john  smith               VP gender  country

1           1  jane  smith                   Sales      f

2           2  jack  jones          Coordinator      m

3           3  dave  stone              Planner      m

4           4  sara  stein          Director Relations      f

5           5  eddy  bower      Directory of Security      m

Contents of df1 after drop:

  fname  lname                       Role gender  country

0  john  smith               VP

1  jane  smith                   Sales      f

2   jack  jones          Coordinator      m

3   dave  stone              Planner      m

4   sara  stein          Director Relations      f

5   eddy  bower      Directory of Security      m

Saving data frame to CSV file

Converting bands_list (XML) to CSV...

ROOT: bands

band_id = 100

band_name = The Data Wranglers

Current Element: band_member

band_member = Dave Pallai

Current Element: band_member

band_member = Jennifer Blaney

band_id = 200

band_name = The Data Cleaners

Current Element: band_member

band_member = Raymond Reddington

Current Element: band_member

band_member = Scary Joe

Current Element: band_member

band_member = The Smoother

Generating CSV calendar of events (COE)...

*** Concert Details ***

      City Concert Date  Tickets (USD)           Band Name  Country

0    paris   01/15/2022             80  The Data Wranglers   france

1   london   02/02/2022             70  The Data Wranglers       uk

2   berlin   02/09/2022             75  The Data Wranglers  germany

3    tokyo   02/19/2022            100  The Data Wranglers    japan

4  vicenza   01/08/2022             50   The Data Cleaners    italy

5    paris   01/18/2022             70  The Data Cleaners   france

6   london   02/05/2022             60  The Data Cleaners       uk

7   berlin   02/13/2022             80  The Data Cleaners  germany

8    tokyo   02/27/2022            100  The Data Cleaners    japan
```

#### 项目后续说明

如果你已经读完了本章到这里的整个项目，请认为你完成得很出色。当然，有多种方式可以组合此项目中的文件来创建包含活动日历的 CSV 文件。

首先是一个通用说明：项目的高级描述通常比实现细节更容易理解。后者可能是枯燥的，并且受到你解决项目任务时使用的技术的影响。然而，理解项目目标是非常重要的，因为它们有助于你清晰理解所写代码的目的：你将理解需要做什么以及为什么要这样做。

其次，本项目试图在代码复杂性和代码可读性之间取得平衡（即避免不必要的复杂度）。请记住，本项目涉及的是一个（尽管是人为设计的）几乎没有数据清洗要求的小数据集。相比之下，现实世界的项目可能涉及耗时且极其枯燥的数据清洗任务，这会让本项目显得微不足道。尽管如此，希望你可以利用本章以及上一章中的数据清洗代码示例来完成其他任务。

第三，本项目向你展示了如何使用基于 `awk` 的 shell 脚本、`Python`、`Pandas` 和 `Java` 将文件转换为不同的格式。此外，你还学习了如何使用这些技术从现有文件生成新文件。事实上，在小数据集上进行转换可能已经让你意识到，当你处理比本项目大数百或数千倍的数据集时，需要预期什么样的复杂性。

第四，你可能注意到列表 7.21 并没有使用在本章早期创建的所有 CSV 文件，例如由 `Python` 脚本 `construct_city_codes.py` 创建的 CSV 文件 `python_city_codes.csv`。原因有两点：其是为了确保列表 7.21 只有一页代码，而且这让你能够修改某些 CSV 文件的结构，从而可能导致需要包含 `python_city_codes.csv` 文件。这些语句对于调试和理解代码块的作用非常有帮助。然而，过多的 `print()` 语句会导致细节过载，因此在你理解了特定块后，如果需要，可以考虑再次注释掉这些语句。此外，你可以将某些输出复制/粘贴到相关的代码块中。

### 总结

本章首先介绍了数据抓取（data wrangling）这一术语，并将其与数据清洗进行了对比。你还看到了几个使用 `Python` 脚本对格式错误的 CSV 文件进行清洗的示例。接下来，你学习了如何将现有文件转换为基于 CSV 的文件，以及如何生成新的 CSV 文件。特别是，你学习了如何使用 shell 脚本、`Python`、`Java` 和 `Pandas` 等不同工具执行转换过程。恭喜你！无论你是初学者还是经验丰富的数据科学家，可能都学了一些在其他项目中大有益的新技巧。

# 附录 A：使用 awk

本附录向你介绍了 `awk` 命令，它在处理数据和重构方面非常多能。事实上，这个工具是如此强大，以至于有整本书都是关于它写的。`awk` 本质上是一种单条命令的编程语言，它接受标准输入，产生标准输出，并像其他 Unix 命令一样使用正则表达式和元字符。这使你能够将其插入其他表达式中，并几乎完成任何事情，代价是增加了命令的复杂性。一眼看出 `awk` 的许多特性是非常值得的。

本附录的第一部分提供了 `awk` 命令的简要介绍。你将学习关于 `awk` 的一些内置变量以及如何使用 `awk` 操作字符串变量。注意，其中一些与字符串相关的示例也可以使用 `bash` 命令处理。附录的第二部分将向你展示 `awk` 中的条件逻辑、循环和 `for` 循环，以操作行和列。该部分还展示了如何删除数据集中的行并合并行，以及如何将文件内容作为单行打印。你会看到如何连接数据集中的行组。

第三部分包含了涉及 `awk` 中元字符和字符集的代码示例。你还将看到如何在使用 `awk` 命令中使用条件逻辑来判断是否打印某行文本。第四部分说明了如何将包含多个 "." 字符的文本字符串作为分隔符进行分割，随后是 `awk` 示例用于在包含数值数据的文件中执行数值计算（如加法、减法、乘法和除法）。该部分展示了 `awk` 中可用的各种数值函数，以及如何在固定列中打印文本。

第五部分解释了如何对齐数据集中的列以及如何合并列。你将看到如何从数据选择子列并处理多行记录。该部分包含了一些单行 `awk` 命令，这些对于操作数据集的内容非常有用。附录的最后部分有一组涉及嵌套引号和结构化数据集的用例。

## awk 命令

`awk`（Aho、Weinberger 和 Kernighan）命令具有类 C 语法，你可以使用这个工具对数字和文本字符串执行复杂操作。顺便提一下，还有 `gawk` 命令（即 GNU `awk`）以及 `nawk` 命令（即“新” `awk`，书中未讨论这两个命令）。`nawk` 的优势之一是它允许你从外部设置内部变量的值。

### 控制 awk 的内置变量

`awk` 命令提供了你可以从默认值更改的变量，用以控制 `awk` 执行操作的方式。此类变量（及其默认值）的 `FS`（`" "`）、`RS`（`"\n"`）、`OFS`（`" "`）、`ORS`（`"\n"`）、`SUBSEP` 和 `IGNORECASE`。变量 `FS` 和 `RS` 指定字段分隔符和记录分隔符，而变量 `OFS` 和 `ORS` 分别指定输出字段分隔符和输出记录分隔符。

你可以将字段分隔符视为我们之前在其他命令中使用的分隔符/IFS。记录分隔符的行为类似于 `sed` 处理单行的方式；例如，`sed` 可以匹配或删除一个范围的行，而不是匹配或删除符合正则表达式的内容（而默认 `awk` 记录分隔符是换行符，因此默认情况下 `awk` 和 `sed` 具有相似的操控和引用文本文件中行的能力）。

作为一个简单的示例，你可以通过更改 `ORS`（从默认的一个换行符改为两个换行符）在文件的每行之后打印一个空行，如下所示：

```bash
cat columns.txt | awk 'BEGIN { ORS ="n\n" } ; { print $0 }'
```

其他内置变量包括 `FILENAME`（`awk` 正在读取的文件名）、`FNR`（当前文件中的记录数）、`NF`（当前输入记录的字段数）以及 `NR`（自程序执行以来 `awk` 处理的输入记录数）。

查阅在线文档获取有关 `awk` 命令这些（以及其他）参数的更多信息。

### awk 命令是如何工作的？

`awk` 命令逐条记录读取输入文件（默认情况下，一个记录是一行）。如果记录匹配模式，则执行动作（否则不执行任何动作）。如果没有给出搜索模式，则 `awk` 会对输入的每条记录执行给定的动作。如果没有给出动作，默认行为是打印所有匹配给定模式的记录。最后，不带任何动作的空括号 `{}` 什么都不做（即程序不会执行默认的打印操作）。注意，动作中的每条语句应用分号隔开。

为了让上述段落更易理解，这里有一些涉及文本字符串和 `awk` 命令的简单示例（结果显示在每个代码段之后）。`-F` 切换将字段分隔符设置为其随后的内容，在本例中是空格。切换通常会为需要在 `BEGIN{}` 块内部使用命令的动作提供快捷方式：

```bash
x="a b c d e"

echo $x | awk -F" " '{print $1}'

a

echo $x | awk -F" " 'a{print NF}'

5

echo $x | awk -F" " '{print $0}'

a b c d e
```



```bash
echo $x | awk -F" " '{print $3, $1}'
```

```text
c a
```

让我们将`FS`（记录分隔符）更改为空字符串以计算字符串的长度，这次使用`BEGIN{}`语法：

```bash
echo "abc" | awk 'BEGIN { FS = "" } ; { print NF }'
```

```text
3
```

以下示例展示了将`test.txt`指定为`awk`命令输入文件的几种等效方法：

```bash
awk < test.txt '{ print $1 }'

awk '{ print $1 }' < test.txt

awk '{ print $1 }' test.txt
```

这里显示了另一种方法（正如我们之前讨论的，这可能是无效的，所以只有当`cat`能以某种方式增加价值时才这样做）：

```bash
cat test.txt | awk '{ print $1 }'
```

这个用四种方式完成相同任务的简单示例应该说明了为什么对任何复杂的`awk`调用进行注释几乎总是一个好主意。下一个查看你代码的人可能不知道或不记得你正在使用的语法。

## 使用`printf()`语句对齐文本

由于`awk`是单个命令内部的编程语言，它也有自己的通过`printf()`语句产生格式化输出的方法。

列表 A.1 显示了`columns2.txt`的内容，列表 A.2 显示了脚本`AlignColumns1.sh`的内容，该脚本向你展示了如何对齐文本列。

**列表 A.1：`columns2.txt`**

```text
one two

three four

one two three four

five six

one two three

four five
```

**列表 A.2：`AlignColumns1.sh`**

```bash
awk '
{
   # 在 10 字符列上左对齐 $1
   # 在 10 字符列上右对齐 $2
   # 在 10 字符列上右对齐 $3
   # 在 10 字符列上右对齐 $4
   printf("%-10s*%10s*%10s*%10s*\n", $1, $2, $3, $4)
}
' columns2.txt
```

列表 A.2 包含一个`printf()`语句，显示文件`columns2.txt`中每行的前四个字段，每个字段的宽度为 10 个字符。

运行列表 A.2 中的代码输出如下：

```text
one        *        two*          *         *

three      *       four*          *         *

one        *        two*     three*     four*

five       *        six*          *         *

one        *        two*     three*         *

four       *        five*         *         *
```

请记住`printf`是相当强大的，因此它有自己的语法，这超出了本附录的范围。在网上搜索可以找到手册页以及关于“如何使用`printf()`执行 X”的讨论。

## 条件逻辑与控制语句

与其他编程语言一样，`awk`提供对条件逻辑（`if/else`）和控制语句（`for/while`循环）的支持。`awk`是不创建、安装并将自定义 shell 脚本添加到路径的情况下，将条件逻辑放入管道命令流的唯一方法。以下代码块展示了如何使用`if/else`逻辑：

```bash
echo "" | awk '
BEGIN { x = 10 }
{
  if (x % 2 == 0) {
      print "x is even"
  }
  else {
      print "x is odd"
  }
}
'
```

前面的代码块将变量`x`初始化为值 10，如果`x`能被 2 整除，则打印“x is even”，否则打印“x is odd”。

### `while`语句

以下代码块说明了如何在`awk`中使用`while`循环：

```bash
echo "" | awk '
{
  x = 0
  while(x < 4) {
    print "x:",x
    x = x + 1
  }
}
'
```

前面的代码块生成了以下输出：

```text
x:0
x:1
x:2
x:3
```

以下代码块说明了如何在`awk`中使用`do while`循环：

```bash
echo "" | awk '
{
  x = 0
  do {
    print "x:",x
    x = x + 1
  } while(x < 4)
}
'
```

前面的代码块生成了以下输出：

```text
x:0
x:1
x:2
x:3
```

### `awk`中的`for`循环

列表 A.3 显示了`Loop.sh`的内容，它说明了如何在循环中打印数字列表。注意`i++`是`awk`（以及大多数 C 派生语言）中编写“I=I+1”的另一种方式。

**列表 A.3：`Loop.sh`**

```awk
for (i=0; i<5; i++) {
  print i
}
```

解释：这里的`%s`是`printf()`的记录分隔符语法，其其后的结束引号意味着记录分隔符为空字段""”。我们`awk`的默认记录分隔符是`\n`（换行符），因此`printf()`语句删除了所有的换行符。空行将完全消失，因为它们只包含换行符，所以结果是任何实际文本将合并在一起，中间没有任何间隔符。

如果我们在`%s`和结束引号之间添加一个空格，那么每个字符块之间将有一个空格，并且每个换行都会额外多出一个空格。注意下面的注释是如何提高代码片段理解性的：

```bash
# 通过移除换行符将所有文本合并为单行
awk '{printf("%s", $0)}' test4.txt
```

## 在文件中合并行组

Listing A.8 显示了`digits.txt`的内容，Listing A.9 显示了`digits.sh`的内容，它“合并”了文件`digits.txt`中连续的三行文本。

**列表 A.8：`digits.txt`**

```text
1
2
3
4
5
6
7
8
9
```

**列表 A.9：`digits.sh`**

```bash
awk -F" " '{
  printf("%d",$0)
  if(NR % 3 == 0) { printf("\n") }
}' digits.txt
```

Listing A.9 将连续的三行文本打印在同一行上，之后打印一个换行符。这实现了“合并”每三行连续文本的效果。运行`digits.sh`的输出在此：

```text
123
456
789
```

## 在文件中合并交替行

Listing A.10 显示了`columns2.txt`的内容，Listing A.11 显示了`JoinLines.sh`的内容，它“合并”了文件`columns2.txt`中连续的两行文本。

**列表 A.10：`columns2.txt`**

```text
one two

three four

one two three four

five six

one two three

four five
```

**列表 A.11：`JoinLines.sh`**

```bash
awk '
{
   printf("%s",$0)
   if( $1 !~ /one/) { print " " }
}
' columns2.txt
```

运行 Listing A.11 的输出在此：

```text
one two three four
one two three four five six
one two two four five
```

注意，Listing A.11 中的代码取决于交替文本行的第一个字段中是否存在字符串“one”。我们是基于匹配简单模式进行合并的，而不是将其与记录组合绑定。

要合并每对行而不是基于模式匹配合并，请使用 Listing A.12 中的修改代码。

**列表 A.12：`JoinLines2.sh`**

```bash
awk '
BEGIN { count = 0 }
{
   printf("%s",$0)
   if( ++count % 2 == 0) { print " " }
} columns2.txt
```

另一种“合并”连续行的方法显示在 Listing A.13 中，其中输入文件和输出文件指的是你可以填充数据的文件。这是另一个`awk`命令的示例，如果在没有注释的程序中遇到它，它可能会是一个谜题。它执行的操作与 Listing A.12 完全相同，但由于语法更紧凑，它的目的并不那么直观。

**列表 A.13：`JoinLines2.sh`**

```bash
inputfile="linepairs.csv"
outputfile="linepairsjoined.csv"
awk ' NR%2 {printf "%s,", $0; next;}1' < $inputfile > $outputfile
```

## 使用元字符和字符集进行匹配

如果我们可以匹配简单模式，也可以匹配正则表达式。Listing A.14 显示了`Patterns1.sh`的内容，它使用元字符来匹配文件`columns2.txt`中文本行的开头和结尾。

**列表 A.14：`Patterns1.sh`**

```bash
awk '
   /^f/    { print $1 }
   /two $/ { print $1 }
' columns2.txt
```

运行 Listing A.14 的输出在此：

```text
one
four
```

Listing A.15 显示了`RemoveColumns.txt`的内容，其行包含不同数量的列。

**列表 A.15：`columns3.txt`**

```text
123 one two
456 three four
one two three four
five 123 six
one two three five
```

Listing A.16 显示了`MatchAlpha.sh`的内容，它匹配以字母开文本以及第二列包含数字字符串的行。

**列表 A.16：`MatchAlpha.sh`**

```bash
awk '
{
   if($0 ~ /^[a-z]/) print $0
   if($0 ~ /[0-9]/) print $0
}' columns3.txt
```

Listing A.16 的输出在此：

```text
123 one two
one two three four
```

## 使用条件逻辑打印行

Listing A.17 显示了`products.txt`的内容，它包含三列信息。

**列表 A.17：`products.txt`**

```text
MobilePhone 400  new
Tablet      300  used
MobilePhone 100  used
```

以下代码片段打印`products.txt`中第二列大于 300 的行：

```bash
awk '$2 > 300' products.txt
```

上述代码片段的输出是：

```text
MobilePhone 400  new
```

以下代码片段打印`products.txt`中 product 等于 new 的行：

```bash
awk '($3 == "new")' products.txt
```

上述代码片段的输出是：

```text
MobilePhone 400  new
Tablet      300  new
```

以下代码片段打印`products.txt`中第二列等于 300 的行的第一列和第三列：

```bash
awk ' $2 == 300 { print $1, $3 }' products.txt
```

上述代码片段的输出是：

以下代码片段打印`products.txt`中以字符串`Tablet`开头的文本行的第一列和第三列：

```bash
awk '/^Tablet/ { print $1, $3 }' products.txt
```

上述代码片段的输出是：

## 使用 AWK 分割文件名

Listing A.18 显示了`SplitFilename2.sh`的内容，它了如何分割包含`.`字符的文件名以增加文件名某个部分的数值。注意，此代码仅适用于预期语法的文件名。

**列表 A.18：`SplitFilename2.sh`**

```bash
echo "05.20.144q.az.1.zip" | awk -F"."
{
  f5=$5 + 1
  printf("%s.%s.%s.%s.%s",$1,$2,$3,$4,$f5)
}
```

Listing A.18 的输出在此：

```text
05.20.144q.az.2.zip
```

## 处理后缀算运算符

Listing A.19 显示了`mixednumbers.txt`的内容，它包含了后缀运算符，这些运算符指向负（或正）符号出现在列值末尾而不是数字开头的数字。

**列表 A.19：`mixednumbers.txt`**

```text
324.000-|10|983.000-
453.000-|30|298.000-
783.000-|20|347.000-
```

Listing A.20 显示了`AddSubtract1.sh`的内容，它演示了如何相加 Listing A.19 中的数字行。

**列表 A.20：`AddSubtract1.sh`**

```bash
myFile="mixednumbers.txt"

awk -F"|" '
BEGIN { line = 0; total = 0 }
{
   split($1, arr, "-")
   f1 = arr[1]
   if($1 ~ /-/) { f1 = -f1 }
   line += f1

   split($2, arr, "-")
   f2 = arr[1]
   if($2 ~ /-/) { f2 = -f2 }
   line += f2

   split($3, arr, "-")
   f3 = arr[1]
   if($3 ~ /-/) { f3 = -f3 }
   line += f3

   printf("f1: %d f2: %d f3: %d line: %d\n",f1,f2,f3, line)
   total += line
   line = 0
}
END { print "Total: ",total }
' $myfile
```

Listing A.20 的输出在此。在阅读后面的解释之前，尝试弄清楚代码在执行什么：

```text
f1: -324 f2: 10 f3: -983 line: -1297
f1: -453 f2: 30 f3: -298 line: -721
f1: -783 f2: 20 f3: -347 line: -1110
Total:  -3128
```

代码假设我们知道文件的格式。`split()`函数将每个字段记录转换为长度为 2 的向量：第一个位置是数字，第二个位置为空值或连字符，然后将第一个位置的数字捕获到变量中。`if`语句检查原始字段是否包含连字符（`-`）。如果存在，则将数值变量变为负数，然后计算该行中值之和。

## AWK 中的数值函数

`int(x)`函数返回数字的整数部分。如果该数字不是整数，它将处于两个整数之间。在两个可能的整数中，函数将返回靠近 0 的那。这与舍入函数不同，舍入函数会选择更接近的整数。

例如，`int(3)`是`3`，`int(3.9)`是`3`，`int(-3.9)`是`-3`，`int(-3)`也是`-3`。`awk`命令中`int(x)`函数的一个示例如下：

```awk
awk 'BEGIN {
   print int(3.534);
   print int(4);
   print int(-5.223);
   print int(-5);
}'
```

输出如下：

```text
3
4
-5
-5
```

`exp(x)`函数给出`x`的指数，或者如果`x`超出范围则报告错误。`x`可能的取值范围取决于你机器的浮点表示。

```awk
awk 'BEGIN{
   print exp(123434346);
   print exp(0);
   print exp(-12);
}'
```

输出如下：

```text
inf
1
6.14421e-06
```

`log(x)`函数在`x`为正数时给出`x`的自然对数；否则报告错误（输出中的`inf`表示无穷大，`nan`表示“非数字”）。

```awk
awk 'BEGIN{
  print log(12);
  print log(0);
  print log(1);
  print log(-1);
}'
```

输出如下：

```text
2.48491
-inf
0
nan
```

`sin(x)`函数给出`x`的正弦，`cos(x)`给出`x`的余弦，其中`x`为弧度：

```awk
awk 'BEGIN {
   print cos(90);
   print cos(45);
}'
```

输出如下：

```text
-0.448074
0.525322
```



`rand()`函数给你一个随机数。`rand()`的值在`0`和`1`之间均匀分布：该值永远不会是`0`也永远不会是`1`。

通常，你想要随机整数。这里有一个自定义函数，可以获取小于`n`的随机非负整数：

```awk
function randint(n) {
    return int(n * rand())
}
```

乘积生成一个大于`0`且`n`的随机实数。然后我们将其转换为`0`到`n - 1`之间的整数（使用`int`）。

这是一个使用类似函数产生`1`到`n`之间随机整数的示例：

```awk
awk '
# 模拟掷骰子的函数。
function roll(n) { return 1 + int(rand() * n) }

# 掷 3 个六面骰子并打印总点数。
{
    printf("%d points\n", roll(6)+roll(6)+roll(6))
}'
```

注意`rand()`每次调用`awk`时都会从同一个点（或“种子”）开始生成数字。因此，程序每次启动时都会产生相同的结果。如果你希望程序在每次使用时执行不同的操作，你必须将种子更改为每次运行都不同的值。

使用`srand(x)`函数将生成随机数的起始点（或种子）设置为值`x`。每个种子值都会导致一个特定的“随机”数序列。因此，如果你第二次将种子设置为相同的值，你将再次获得相同的“随机”数序列。如果你省略了参数`x`（如`srand()`），则使用当前的日期和时间作为种子。这就是获取真正不可预测的随机数的方法。`srand()`的返回值是上一个种子。这使得跟踪种子以便一致地重现随机数序列变得容易。

`time()`函数（并非所有`awk`版本都包含）返回自1970年1月1日以来的当前秒数。`ctime()`函数（并非所有`awk`版本都包含）返回当前日期。`sqrt(x)`函数给出`x`的平方根。如果`x`为负数，它会报告错误。

## 单行 AWK 命令

代码假设我们知道文件的格式。`split()`函数将每个字段记录转换为长度为2的向量：第一个位置是数字，第二个位置为空值或连字符，然后将第一个位置的数字捕获到变量中。`if`语句检查原始字段是否包含连字符（`-`）。如果存在，则将数值变量变为负数，然后计算该行中值之和。

## 有用的 AWK 脚本

代码假设我们知道文件的格式。`split()`函数将每个字段记录转换为长度为2的向量：第一个位置是数字，第二个位置为空值或连字符，然后将第一个位置的数字捕获到变量中。`if`语句检查原始字段是否包含连字符（`-`）。如果存在，则将数值变量变为负数，然后计算该行中值之和。

## 在 AWK 中打印单词

## 在特定行中统计字符串出现次数

代码假设我们知道文件的格式。`split()`函数将每个字段记录转换为长度为2的向量：第一个位置是数字，第二个位置为空值或连字符，然后将第一个位置的数字捕获到变量中。`if`语句检查原始字段是否包含连字符（`-`）。如果存在，则将数值变量变为负数，然后计算该行中值之和。

### AWK 中的数值函数

`int(x)`函数返回数字的整数部分。如果该数字不是整数，它将处于两个整数之间。在两个可能的整数中，函数将返回靠近0的那一个。这与舍入函数不同，舍入函数会选择更接近的整数。

例如，`int(3)`是`3`，`int(3.9)`是`3`，`int(-3.9)`是`-3`，`int(-3)`也是`-3`。`awk`命令中`int(x)`函数的一个示例如下：

```awk
awk 'BEGIN {
    print int(3.534);
    print int(4);
    print int(-5.223);
    print int(-5);
}'
```

输出如下：

```text
3
4
-5
-5
```

`exp(x)`函数给出`x`的指数，或者如果`x`超出范围则报告错误。`x`可能的取值范围取决于你机器的浮点表示。

```awk
awk 'BEGIN{
    print exp(123434346);
    print exp(0);
    print exp(-12);
}'
```

输出如下：

```text
inf
1
6.14421e-06
```

`log(x)`函数在`x`为正数时给出`x`的自然对数；否则报告错误（输出中的`inf`表示无穷大，`nan`表示“非数字”）。

```awk
awk 'BEGIN{
    print log(12);
    print log(0);
    print log(1);
    print log(-1);
}'
```

输出如下：

```text
2.48491
-inf
0
nan
```

`sin(x)`函数给出`x`的正弦，`cos(x)`给出`x`的余弦，其中`x`为弧度：

```awk
awk 'BEGIN {
    print cos(90);
    print cos(45);
}'
```

输出如下：

```text
-0.448074
0.525322
```

`rand()`函数给你一个随机数。`rand()`的值在`0`和`1`之间均匀分布：该值永远不会是`0`也永远不会是`1`。

通常，你想要随机整数。这里有一个自定义函数，可以获取小于`n`的随机非负整数：

```awk
function randint(n) {
    return int(n * rand())
}
```

乘积生成一个大于`0`且`n`的随机实数。然后我们将其转换为`0`到`n - 1`之间的整数（使用`int`）。

这是一个使用类似函数产生`1`到`n`之间随机整数的示例：

```awk
awk '
# 模拟掷骰子的函数。
function roll(n) { return 1 + int(rand() * n) }

# 掷 3 个六面骰子并打印总点数。
{
    printf("%d points\n", roll(6)+roll(6)+roll(6))
}'
```

注意`rand()`每次调用`awk`时都会从同一个点（或“种子”）开始生成数字。因此，程序每次启动时都会产生相同的结果。如果你希望程序在每次使用时执行不同的操作，你必须将种子更改为每次运行都不同的值。

使用`srand(x)`函数将生成随机数的起始点（或种子）设置为值`x`。每个种子值都会导致一个特定的“随机”数序列。因此，如果你第二次将种子设置为相同的值，你将再次获得相同的“随机”数序列。如果你省略了参数`x`（如`srand()`），则使用当前的日期和时间作为种子。这就是获取真正不可预测的随机数的方法。`srand()`的返回值是上一个种子。这使得跟踪种子以便一致地重现随机数序列变得容易。

`time()`函数（并非所有`awk`版本都包含）返回自1970年1月1日以来的秒数。`ctime()`函数（并非所有`awk`版本都包含）返回当前日期。`sqrt(x)`函数给出`x`的平方根。如果`x`为负数，它会报告错误。

`Listing A.23`和`Listing A.24`分别显示了`data1.csv`和`data2.csv`的内容，`Listing A.25`显示了`checkrows.sh`的内容，该脚本说明了统计第2、5、7行第3列中字符串“past”出现次数的方法。

### 代码列表 A.23：data1.csv

```text
in,the,past,or,the,present
for,the,past,or,the,present
in,the,past,or,the,present
for,the,paste,or,the,future
in,the,past,or,the,present
completely,unrelated,line1
in,the,past,or,the,present
completely,unrelated,line2
```

### 代码列表 A.24：data2.csv

```text
in,the,past,or,the,present
completely,unrelated,line1
for,the,past,or,the,present
completely,unrelated,line2
for,the,paste,or,the,future
in,the,past,or,the,present
in,the,past,or,the,present
completely,unrelated,line3
```

### 代码列表 A.25：checkrows.sh

```sh
files="'ls data*.csv| tr '\n' ' ''"

echo "List of files: $files"

awk -F"," '
( FNR==2 || FNR==5 || FNR==7 ) {
    if ( $3 ~ "past" ) { count++ }
}

END {
    printf "past: matched %d times (INEXACT) ", count
    printf "in field 3 in lines 2/5/7\n"
}' data*.csv
```

由于以下代码段的存在，`Listing A.25`是在第2、5、7列中查找字符串`past`的出现情况：

```awk
( FNR==2 || FNR==5 || FNR==7 ) {
    if ( $3 ~ "past" ) { count++ }
}
```

如果发生匹配，则`count`的值加1。`END`块报告了第2、5、7列中找到字符串`past`的次数。注意，诸如`paste`和`pasted`等字符串也会匹配字符串`past`。`Listing A.25`的输出如下：

```text
List of files: data1.csv data2.csv

past: matched 5 times (INEXACT) in field 3 in lines 2/5/7
```

shell脚本`checkrows2.sh`将`checkrows.sh`中的术语`$3 ~ "past"`替换为`$3 == "past"`以检查精确匹配，这产生了以下输出：

```text
List of files: data1.csv data2.csv

past: matched 4 times (EXACT) in field 3 in lines 2/5/7
```

### 在固定列数中打印字符串

`Listing A.26`显示了`FixedFieldCount1.sh`的内容，它说明了如何使用`awk`命令打印文本字符串中的单词。

### 代码列表 A.26：FixedFieldCount1.sh

```sh
echo "aa bb cc dd ee ff gg hh" | awk '
BEGIN { colCount = 3 }
{
    for(i=1; i<=NF; i++) {
        printf("%s ", $i)
        if(i % colCount == 0) {
            print " "
        }
    }
}'
```

`Listing A.26`的输出如下：

```text
aa bb cc
dd ee ff
gg hh
```

### 在固定列数中打印数据集

`Listing A.27`显示了`VariableColumns.txt`的内容，其文本行包含不同数量的列。

### 代码列表 A.27：VariableColumns.txt

```text
this is line one
this is line number one
this is the third and final line
```

`Listing A.28`显示了`Fields3.sh`的内容，它说明了如何使用`awk`命令打印文本字符串中的单词。

### 代码列表 A.28：Fields3.sh

```sh
awk '{printf("%s ", $0)}' | awk '
BEGIN { columnCount = 3 }
{
    for(i=1; i<=NF; i++) {
        printf("%s ", $i)
        if( i % columnCount == 0 )
            print " "
    }
}' VariableColumns.txt
```

`Listing A.28`的输出如下：

```text
this is line
one this is
line number one
this is the
third and final
line
```

### 对齐数据集中的列

如果你已经阅读了前面的两个示例，那么本节中的代码示例很容易理解：你将看到内容正确的数据列，但它们被放置在不同的行中（因此未对齐）。`Listing A.29`显示了带有未对齐值的`mixed-data.csv`。此外，`Listing A.28`中的第一行和最后一行是空行，它们将被本节的shell脚本移除。

### 代码列表 A.29：mixed-data.csv

```text
Sara, Jones, 1000, CA, Sally, Smith, 2000, IL,
Dave, Jones, 3000, FL, John, Jones,
4000, CA,
Dave, Jones, 5000, NY, Mike,
Jones, 6000, NY, Tony, Jones, 7000
```

`Listing A.30`显示了`mixed-data.sh`的内容，说明了如何对齐`Listing A.29`中的数据集。

### 代码列表 A.30：mixed-data.sh

```sh
#-------------------------
# 1) 删除空行
# 2) 删除换行符
# 3) 每 8 个字段后打印一个 LF
# 4) 删除每行末尾的逗号
#-------------------------

inputfile="mixed-data.csv"

grep -v "^$" $inputfile | awk -F"," '{printf("%s",$0)}' | awk '
BEGIN { columnCount = 4 }
{
    for(i=1; i<=NF; i++) {
        printf("%s ", $i)
        if( i % columnCount == 0) { ++currRow }
        if(currRow > 0 && currRow % rowCount == 0) {
            currRow = 0
            print ""
        }
    }
}' > temp-columns

# 4) 删除输出末尾的逗号：
cat temp-columns | sed 's/, $//' | sed 's/ $//' > $output
```

`Listing A.30`首先使用`grep`命令（关于`grep`有在线教程）删除空行，然后使用`awk`命令将数据集的行转换为单行文本。第二个`awk`命令在`BEGIN`块中将`columnCount`变量初始化为`4`，随后是一个遍历输入字段的循环。在同一行输出四个字段后，会打印一个换行符，其效果是将输入数据集对齐为由四列组成的数据集。`Listing A.30`的输出如下：

```text
Sara, Jones, 1000, CA
Sally, Smith, 2000, IL
Dave, Jones, 3000, FL
John, Jones, 4000, CA
Dave, Jones, 5000, NY
Mike, Jones, 6000, NY
Tony, Jones, 7000
```

### 对齐数据集中的列和多行

前面的部分展示了如何重新对齐数据集使每行包含相同数量的列并代表单条记录。本节的代码示例说明了如何对齐内容正确的列，并在新数据集的每行放置两条记录。`Listing A.31`显示了带有未对齐值的`mixed-data2.csv`，随后`Listing A.32`显示了格式正确的`aligned-data2.csv`内容。

### 代码列表 A.31：mixed-data2.csv

```text
Sara, Jones, 1000, CA, Sally, Smith, 2000, IL,
Dave, Jones, 3000, FL, John, Jones,
4000, CA,
Dave, Jones, 5000, NY, Mike,
Jones, 6000, NY, Tony, Jones, 7000, WA
```

### 代码列表 A.32：aligned-data2.csv

```text
Sara, Jones, 1000, CA, Sally, Smith, 2000, IL
Dave, Jones, 3000, FL, John, Jones, 4000, CA
Dave, Jones, 5000, NY, Mike, Jones, 6000, NY
Tony, Jones, 7000, WA
```

`Listing A.33`显示了`mixed-data2.sh`的内容，说明了如何对齐`Listing A.31`中的数据集。

### 代码列表 A.33：mixed-data2.sh

```sh
#-----------------------------------------
# 1) 删除空行
# 2) 删除换行符
# 3) 每 8 个字段后打印一个 LF
```



# 4) 删除每行末尾的逗号

```bash
#-----------------------------------------

inputfile="mixed-data2.txt"

outputfile="aligned-data2.txt"

grep -v "^$" $inputfile | awk -F"," '{printf("%s",$0)}' | awk '

BEGIN { columnCount = 4; rowCount = 2; currRow = 0 }

{

   for(i=1; i<=NF; i++) {

     printf("%s ", $i)

     if( i % columnCount == 0) { ++currRow }

     if(currRow > 0 && currRow % rowCount == 0) {currRow = 0; print ""}

   }

}' > temp-columns

# 4) 删除输出末尾的逗号:

cat temp-columns | sed 's/, $//' | sed 's/ $//' > $output
```

`Listing A.33` 与 `Listing A.30` 非常相似。其核心思想是在处理完一对“正常”记录后打印一个换行符，这是通过 `Listing A.33` 中加粗显示的代码实现的。

现在，你可以通过将 `rowCount` 变量的初始值更改为任何正整数，非常轻松地扩展 `Listing A.33` 的泛性，且代码在不进行任何进一步修改的情况下即可运行。例如，如果你将 `rowCount` 初始化为值 5，那么新数据集中的每一行（最后一行输出行可能可能除外）都将包含 5 条“正常”数据记录。

## 从文本文件中删除列

`Listing A.34` 显示了 `VariableColumns.txt` 的内容，其中文本行包含不同数量的列。

### Listing A.34：VariableColumns.txt

```text
this is line one

this is line number one

this is the third and final line
```

`Listing A.35` 显示了 `RemoveColumn.sh` 的内容，该脚本从文本文件中删除第一列。

### Listing A.35：RemoveColumn.sh

```bash
awk '{ for (i=2; i<=NF; i++) printf "%s ", $i; printf "\n"; }' VariableColumns.txt
```

循环位于 2 和 `NF` 之间，遍历除第一个字段外的所有此外，`printf` 显式地添加了换行。上述代码段的输出如下：

```text
is line one

is line number one

is the third and final line
```

## 数据集中对齐行的子集

`Listing A.35` 展示了如何对数据集的行进行对齐，本部分的代码示例说明了如何提取现有列的子集和行的子集。`Listing A.36` 显示了目标数据集 `sub-rows-cols.txt` 的内容，该文件包含 `aligned-data.txt` 中每个偶数行的两列。

### Listing A.36：sub-rows-cols.txt

```text
Sara, 1000

Dave, 3000

Dave, 5000

Tony, 7000
```

`Listing A.37` 显示了 `sub-rows-cols.sh` 的内容，说明了如何生成 `Listing A.36` 中的数据集。大部分代码与 `Listing A.33` 相同，新代码已加粗显示。

### Listing A.37：sub-rows-cols.sh

```bash
#-----------------------------------------

# 1) 删除空行

# 2) 删除换行符

# 3) 在每四个字段后打印一个 LF

# 4) 删除每行的末尾逗号

#-----------------------------------------

inputfile="mixed-data.txt"

grep -v "^$" $inputfile | awk -F"," '{printf("%s",$0)}' | awk '

BEGIN { columnCount = 4 }

{

   for(i=1; i<=NF; i++) {

     printf("%s ", $i)

     if( i % columnCount  == 0) { print "" }

   }

}' > temp-columns

# 4) 删除输出末尾的逗号：

cat temp-columns | sed 's/, $//' | sed 's/$//' > temp-columns2

cat temp-columns2 | awk '

BEGIN { rowCount = 2; currRow = 0 }

{

   if(currRow % rowCount == 0) { print $1, $3 }

   ++currRow

}' > temp-columns3

cat temp-columns3 | sed 's/,$//' | sed 's/ $//' > $outputfile
```

`Listing A.37` 包含一个新的代码块，将步骤 #4 的输出重定向到临时文件 `temp-columns2`，其内容由 `Listing A.37` 最后部分的另一个 `awk` 命令处理。请注意，该 `awk` 命令包含一个 `BEGIN` 块，将变量 `rowCount` 和 `currRow` 分别初始化为 2 和 0。

主块在当前行号为偶数时打印当前行的第 1 列和第 3 列，然后增加 `currRow` 的值。该 `awk` 命令的输出重定向到另一个临时文件，作为最后一个代码片段的输入，该片段使用 `cat` 命令和两次 `sed` 命令来删除末尾的“，”和末尾的空格，如下：

```bash
cat temp-columns3 | sed 's/,$//' | sed 's/ $//' > $outputfile
```

还有其他方法可以实现 `Listing A.37` 中的功能，主要目的是展示组合各种 bash 命令的技术。

## 数据集中词频统计

`Listing A.38` 显示了 `WordCounts1.sh` 的内容，说明了如何统计文件中单词的频率。

### Listing A.38：WordCounts1.sh

```awk
awk '

# 打印单词频率

{

    for (i = 1; i <= NF; i++)

        freq[$i]++

}

END {

    for (word in freq)

        printf "%s\t%d", word, freq[word]

}

' columns2.txt
```

`Listing A.38` 包含一段处理 `columns2.txt` 行代码。每遇到一个单词（一行），代码就会增加该单词在哈表 `freq` 中的出现次数。`END` 块包含一个 `for` 循环，显示 `columns2.txt` 中每个单词的次数。

`Listing A.38` 的输出如下：

```text
two        3

one        3

three      3

six        1

five       2
```

`Listing A.39` 显示了 `WordCounts2.sh` 的内容，执行不区分大小写的单词统计。

### Listing A.39：WordCounts2.sh

```awk
awk '

{

    # 将全部转为小写

    $0 = tolower($0)

    # 删除标点符号

   gsub(/[^alnum:][:space:]]/, "", $0)

    for(i=1; i<=NF; i++) {

       freq[$i]++

    }

}

END {

    for(word in freq) {

       printf "%s\t%d", word, freq[word]

    }

}

' columns4.txt
```

`Listing A.39` 的代码与 `Listing A.38` 几乎相同，增加了以下将每行输入转换为小字母的代码段：

```awk
$0 = tolower($0)
```

`Listing A.40` 显示了 `columns.txt` 的内容。

### Listing A.40：columns.txt

```text
123 ONE TWO

456 three four

ONE TWO FOUR

five 123 six

one two three

four five
```

运行 `Listing A.39` 使用 `columns.txt` 的输出如下：

```text
456	1

two	3

one	3

three	3

six	1

five	2
```

## 在数据集中仅显示“纯”单词

为了简单起见，让我们使用文本字符串，这样我们可以在得到解决方案的过程中查看中间结果。`Listing A.41` 显示了 `onlywords.sh` 的内容，它包含了三个 `awk` 命令，分别显示文本字符串中的单词、整数和字母字符串。

### Listing A.41：onlywords.sh

```bash
x="ghi abc Ghi 123 #def5 123z"

echo "Only words:"

echo $x | tr -s ' ' '\n' | awk -F" "

{

  if($0 ~ /^[a-zA-Z]+$/) { print $0 }

}

' | sort | uniq

echo "Only integers:"

echo $x | tr -s ' ' '\n' | awk -F" "

{

  if($0 ~ /^[0-9]+$/) { print $0 }

}

' | sort | uniq

echo "Only alphanumeric words:"

echo $x | tr -s ' ' '\n' | awk -F" "

{

  if($0 ~ /^[0-9a-zA-Z]+$/) { print $0 }

}

' | sort | uniq
```

`Listing A.41` 初始化变量 `x`：

```bash
x="ghi abc Ghi 123 #def5 123z"
```

下一步是将 `x` 拆分为单词：

```bash
echo $x | tr -s ' ' '\n'
```

输出如下：

```text
ghi

abc

Ghi

123

#def5

123z
```

第三步是调用 `awk` 并检查匹配正则表达式 `^[a-zA-Z]+` 的单词，该正则匹配任何由一个或多个大写/小写字母组成的字符串（不包含其他任何字符）：

```awk
if($0 ~ /^[a-zA-Z]+$/) { print $0 }
```

输出如下：

```text
ghi

abc

Ghi
```

最后，如果你也想对输出进行排序并只打印唯一的单词，可以将 `awk` 命令的输出重定向到 `sort` 命令和 `uniq` 命令。

第二个 `awk` 命令使用正则表达式 `^[0-9]+` 来检查整数，第三个 `awk` 命令使用正则表达式 `^[0-9a-zA-Z]+` 来检查字母数字单词。

```text
Only words:

Ghi

abc

ghi

Only integers:

123

Only alphanumeric words:

123

123z

Ghi

abc

ghi
```

你可以将变量 `x` 替换为数据集，以便从该数据集中检索纯字母字符串。

## 在 AWK 中处理多行记录

`Listing A.42` 显示了 `employee.txt` 的内容，`Listing A.43` 显示了 `Employees.sh` 内容，展示了如何合并文件中的文本行。

### 列表 A.42：employees.txt

```text
Name:  Jane Edwards

EmpId: 12345

Address: 123 Main Street Chicago Illinois

Name:  John Smith

EmpId: 23456

Address: 432 Lombard Avenue SF California
```

### 列表 A.43：employees.sh

```bash
inputfile="employees.txt"

outputfile="employees2.txt"

awk '

{

  if($0 ~ /^Name:/) {

    x = substr($0,8) ","

    next

  }

  if( $0 ~ /^Empid:/) {

   #skip the Empid data row

   #x = x substr($0,7) ","

    next

  }

  if($0 ~ /^Address:/) {

    x = x substr($0,9)

    print x

  }

}

' < $inputfile > $outputfile
```

运行 `Listing A.43` 中的代码后的输出如下：

```text
Jane Edwards, 123 Main Street Chicago Illinois

John Smith, 432 Lombard Avenue SF California
```

现在，你已经看到了大量的 `awk` 代码片段和包含 `awk` 命令的 shell 脚本，这些内容展示了可以在文件和数据集上执行的各种任务，你已经准备好学习一些用例了。下一节（第一个用例）将向你如何将多个字段分隔符替换为单个分隔符，第二个用例将向你如何处理日期字符串。

## 一个简单的用例

本节中的代码示例向你展示了如何使用 `awk` 命令分割数据集行中的逗号分隔字段，其中字段可以包含任意深度的嵌套引号。

`Listing A.44` 显示了文件 `quotes3.csv` 的内容，该文件包含一个“，”分隔符和多个带引号字段。

### 列表 A.44：quotes3.csv

```csv
field5,field4,field3,"field2,foo,bar",field1,field6,field7,"fieldZ"

fname1,"fname2,other,stuff",fname3,"fname4,foo,bar",fname5

"lname1,a,b","lname2,c,d","lname3,e,f","lname4,foo,bar",lname5
```

`Listing A.45` 显示了文件 `delim1.sh` 的内容，它展示了如何将 `delim1.csv` 中的分隔符替换为“，”字符。

### 列表 A.45：delim1.sh

```bash
# #inputfile="quotes1.csv"

#inputfile="quotes2.csv"

inputfile="quotes3.csv"

grep -v "^$" $inputfile | awk '

{

   print "LINE #" NR ": " $0

   printf ("-------------------------\n")

   for (i = 0; ++i <= NF;)

     printf "field #%d : %s\n", i, $i

   printf ("\n")

}' FPAT='([^,]+)|("[^"]+")' < $inputfile
```

运行 `Listing A.44` 中的 shell 脚本后的输出如下：

```text
LINE #1: field5,field4,field3,"field2,foo,bar",field1,field6,field7,
"fieldZ"

-------------------------

field #1 : field5

field #2 : field4

field #3 : field3

field #4 : "field2,foo,bar"

field #5 : field1

field #6 : field6

field #7 : field7

field #8 : "fieldZ"

LINE #2: fname1,"fname2,other,stuff",fname3,"fname4,foo,bar",fname5

-------------------------

field #1 : fname1

field #2 : "fname2,other,stuff"

field #3 : fname3

field #4 : "fname4,foo,bar"

field #5 : fname5

LINE #3: "lname1,a,b","lname2,c,d","lname3,e,f","lname4,foo,bar",lname5

-------------------------

field #1 : "lname1,a,b"

field #2 : "lname2,c,d"

field #3 : "lname3,e,f"

field #4 : "lname4,foo,bar"

field #5 : lname5

LINE #4: "Outer1 "Inner "Inner "Inner C" B" A" Outer1","XYZ1,c,d","XYZ2lname3,e,f"

-------------------------

field #1 : "Outer1 "Inner "Inner "Inner C" B" A" Outer1"

field #2 : "XYZ1,c,d"

field #3 : "XYZ2lname3,e,f"

LINE #5:

-------------------------
```



你可以看到，本节中的任务可以通过`awk`命令轻松解决。

### 另一个用例

本节中的代码示例向你展示了如何使用`awk`命令重新格式化数据集中的日期字段并更改新集中字段的顺序。例如，给定原始数据集中的输入：

```
Jane,Smith,20140805234658
```

输出集中重新格式化的行格式如下：

```
2014-08-05 23:46:58,Jane,Smith
```

Listing A.46 显示了文件`dates.csv`的内容，它包含一个“，”分隔符三个字段。

### 列表 A.46 dates.csv

```text
Jane,Smith,20140805234658
Jack,Jones,20170805234652
Dave,Stone,20160805234655
John,Smith,20130805234646
Jean,Davis,20140805234649
Thad,Smith,20150805234637
Jack,Pruit,20160805234638
```

Listing A.47 显示了`stringdate2.sh`的内容，它将日期转换为新格式并将其移动到第一个字段。

### 列表 A.47：stringdate2.sh

```bash
inputfile="dates2.csv"
outputfile="formatteddates2.csv"

rm -f $outputfile; touch $outputfile

for line in 'cat $inputfile'
do
  fname='echo $line | cut -d"," -f1'
  lname='echo $line | cut -d"," -f2'
  date1='echo $line | cut -d"," -f3'

  # convert to new date
  newdate='echo $date1 | awk '{ print substr($0,1,4)"-"substr($0,5,2)"-"substr($0,7,2)" "substr($0,9,2)":"substr($0,11,2)":"substr($0,13,2)}''

  # append newly formatted row to output
  echo "${newdate},${fname},${lname}" >> $outputfile
done
```

新数据集的内容为：

```
2014-08-05 23:46:58,Jane,Smith
2017-08-05 23:46:52,Jack,Jones
2016-08-05 23:46:55,Dave,Stone
2013-08-05 23:46:46,John,Smith
2014-08-05 23:46:49,Jean,Davis
2015-08-05 23:46:37,Thad,Smith
2016-08-05 23:46:38,Jack,Pruit
```

### 总结

本附录介绍了`awk`命令，它本质上是将整个编程语言封装进单个 Unix 命令中。

我们探索了`awk`中的一些内置变量以及条件逻辑、`while`循环和`for`循环，以便操作数据集中的行和列。然后你看到了如何删除数据集中的行并合并行，以及如何将文件内容作为单行文本。

接下来，你学习了如何在`awk`命令中使用元字符和字符集。你学习了如何在包含数字数据的文件中执行数值计算（如加、减、乘、除），以及`awk`中可用的一些数值函数。

此外，你还看到了如何对齐数据集中的列、删除列、从数据集中选择子集并处理数据集中的多行记录。最后，你看到了涉及结构化数据集中嵌套引号和日期格式的简单用例。

此时，你已经拥有进行复杂数据清洗和处理的所有工具，强烈鼓励将它们应用于感兴趣的任务或问题。学习过程的最后一步是做真实的事情。

## 索引

### A

Aho, Weinberger, and Kernighan (`awk`) 命令

- 内置变量，224
- 条件逻辑和控制语句
  - `if/else` 逻辑，226
  - `for` 循环，227–228
  - `while` 循环，227
- 条件逻辑，打印行，233–234
- 字符串出现次数，240–241

#### 数据集

- 对齐列和多行，244–245
- 对齐列，243–244
- 词频率，247–248
- 删除交替行，229
- 显示纯单词，248–250
- 合并行，229–232
- 对齐列行子集，246–247

- 固定列数
  - 打印数据集，242–243
  - 打印字符串，242
- 元字符和字符集，232–233
- 多行记录，250–251
- 数值函数，236–238

### 索引（Index）

- 单行命令，238
- 后置操作符，234–235
- `printf()` 语句，225–226
- 打印文本字符串中的单词，240
- 从文本文件中删除列，245
- 基于`awk`的短脚本，239–240
- 切分文件名，234
- 使用用例，251–254
- 工作原理，224–225

### 方差分析（ANOVA），53–54

- 异常，38–39
- 原子性、一致性、隔离性和持久性（ACID），104
- 可用性偏差，52

### B

- 黑盒偏移检测器，30

### C

- 确认偏误，52
- 连续型数据类型，33
- 分箱（binning），概念，33

### D

#### 数据库操作，MySQL

- 创建（create），117–118
- 删除（drop），118
- 导出（export），118–119
- 重命名（rename），119–120

#### 数据清洗

- `awk` 命令行工具，162–163
- 转换字母日期格式，173–175
- 转换数值日期格式，169–172
- 转换电话号码，167–168
- 国家、城市和区号，181–186
- 日期和时间格式，175–180
- 描述，151–152
- 在 Kaggle 数据集上，186–189
- 个人头衔，152–154
- 固定列的行生成，164–166
- `sed` 命令行工具，160–161

#### 在 SQL 中

- 将字符串转换为日期值，158–160
- 处理数据类型不匹配，157–158
- 将多个值替换为单个值，156–157
- 将`NULL`替换为 0，154
- 将`NULL`替换为平均值，154–156
- 截断 CSV 文件中的行，163–164

- 数据控制语言（DCL），112
- 数据定义语言（DDL），112
- 数据漂移，30
- 数据框（Data frames），56
- 布尔操作，60–61
- `concat()` 方法，68–69
- 数据清洗任务，56
- 数据处理，69–70
- 删除重复行，83–84
- 查找重复行，81–83
- 查找缺失值，84–86
- `housing_stats.py`，80–81
- `missingdatairis.py`，87–89
- `nan_iris.csv`，86–87
- `pandas_df_describe.py`，58–60
- `pandas_df.py`，56–58
- 随机数，62–63
- `read_csv()` 函数，70–76
- 从 Excel 表格读取，76–77
- 选择、添加和删除列，77–79
- `sort_df.py`，89–90
- `transpose` 函数，61–62

- 数据操作语言（DML），113
- 数据查询语言（DQL），112
- 数据集，30
- 异常，38–39

#### `awk` 命令

- 在多行中对齐列，244–245
- 对齐列，243–244
- 词频率计数，247–248
- 删除交替行，229
- 显示纯单词，248–250
- 合并行，229–232
- 列对齐子集，246–247

#### 偏差-方差权衡（bias-variance trade-off）

- 有偏差统计，51
- 偏差类型，52–53

#### 分类数据

- 处理数据值，36
- 映射到数值值，36–37

#### 分类器

- ANOVA，53–54
- `LIME`，53

#### 数据预处理

- 货币，38
- 日期，38
- 离散数据 vs. 连续数据，32–33
- 不平衡数据集，49–50
- 缺失值，48–49
- 离群值，38
- 检测/移除，39–40
- 使用 NumPy，40–42
- 使用 Pandas，42–45
- 使用 Sklearn，46–48
- z-score 计算，45–46

#### 数值数据缩放

- 通过归一化，34
- 通过鲁棒标准化，35–36
- 通过标准化，34–35

#### 数据类型

- 数据漂移，30
- 离散，32–33
- Python，10
- MySQL，115
- BLOB 和 TEXT，116
- CHAR 和 VARCHAR，115
- FLOAT 和 DOUBLE，116
- 基于字符串的，116

#### 数据整理（Data wrangling）

- 事件日历，215–218
- `construct_city_codes2.py`，206–208
- `construct_city_codes.sh`，202–205
- 文件，209–213
- Python，213–215
- 和`awk`命令，196–197
- `csv_line.py`，195–196
- `csv`，194–195
- `pandas_line.py`，194–195
- 数据，192–193
- 转换，191–192
- 描述，191–192
- `cities.csv`，190–191
- `country.csv`，190–191
- 引号，220
- 字段，197–200
- 跟进，220
- 脚本，220
- 行，220–221
- 统计数据，197–200
- 离散数据类型，32–33
- SQL 表，197–200
- 插入，127–129
- 删除，129–130
- 表，126–127
- 创建，124–126
- 数据库，124–126
- 数据，138–140
- XML，138–140
- XML，142–144
- 字符串，141–142
- JSON，133–135
- 表，146–148
- 字符串，141–142
- XML，140–141
- XML，140–141
- 离散数据类型，32–33
- SQL 表，197–200
- 插入，127–129
- 删除，129–130
- 表，126–127
- 创建，124–126
- 数据库，124–126
- 数据，138–140
- XML，138–140
- XML，142–144
- 字符串，141–142
- JSON，133–135
- 表，146–148
- 字符串，141–142

## 选择数据，130–132

## `SelectXMLData.jav`，145–146

## 设置步骤，124

## 更新数据，132–133

## XML 文档，135–136

## MariaDB 数据库，114

## PROCESSLIST 表，121

### N

#### 规范化，34

### O

#### One 热编码技术，37

#### 离群值

- 检测/删除，39–40
- 使用 NumPy，40–42
- 使用 Pandas，42–45，79–80
- 使用 Sklearn，46–48
- z-score 计算，45–46

### P

#### Pandas

- 使用`titanic.csv`进行聚合操作，92–94
- `apply()` 和`mapappy()`方法，94–97
- 分类到数值数据转换，63–67
- 数据框（data frames），56
- 布尔操作，60–61
- `concat()` 方法，68–69
- 数据清洗任务，56
- 数据处理，69–70
- 掉重复行，83–84
- 查找重复行，81–83
- 查找缺失值，84–86
- `housing_stats.py`，80–81
- `missingdatairis.py`，87–89
- `nan_iris.csv`，86–87
- `pandas_df_describe.py`，58–60
- `pandas_df.py`，56–58
- 使用随机数，62–63
- `read_csv()` 函数，70–76
- 从 Excel 表格读取，76–77
- 选择、添加和删除列，77–79
- `sort_df.py`，89–90
- 转置函数，61–62
- `groupby()` 方法，90–92
- 安装，55

#### JSON 对象

- `dict2json.py`，99–100
- `pd_python_json.py`，100–101
- 合并与拆列，67–68
- 单行命令，97–99
- 离群值，79–80

#### Python

- 整数的算术运算，10–13
- 命令行参数，26–27
- 编译时检查，9–10
- 日期相关函数，22–23
- `easy_install` 和`pip`，1
- 异常处理，23–24
- `Fraction()` 函数，13–14
- 处理用户输入，24–26
- `help()` 和`dir()`函数，8–9
- 标识符，5
- 安装，3
- 交互式解释器，`IPython`，2
- 行与缩进，5–6
- 多行语句，5
- `PATH` 变量，3
- 原始数据类型，10
- 引号与注释，7–7
- 运行时检查，9–10
- 标准库模块，8
- 将代码写入文件，7–8
- 字符串，15–17
- `replace()` 函数，20
- 搜索与替换，18–19
- 切片与拼接，17–18
- `strip()`、`lstrip()` 和`rstrip()`，19–20
- 文本对齐，21
- `write()` 函数，20
- Unicode 和 UTF-8，14
- 未初始化变量和`None`，17
- `virtualenv`，2

### R

- 过采样，50
- 重采样，50
- 欠采样，50

### 关系型数据库系统（RDBMS）

- ACID，104
- 原子性事务，105
- 特性，104
- 描述，103
- 逻辑模式，104
- 资金转账场景，105
- 需要，105
- 规范化，105–106
- 一多关系，103–104
- 自引用表，104
- SQL，111–114

#### 用例场景

- 客户表，108–109
- `item_desc` 表，111
- `line_items` 表，109–111
- `purchase_orders` 表，109
- 网页页面，107

- 资源包，31
- 鲁棒标准化技术，35–36

### S

- SMOTE（合成少数类过采样技术）算法，48，50–51，152
- 扩展，51
- 不平衡数据集，49–50
- 标准化技术，34–35
- 结构化查询语言（SQL），111–112
- `CREATE` 关键字，114
- DCL 和 DDL，112
- DQL、DML 和 TCL，112–113
- 格式样式，122
- 对象权限，113
- 语句，113
- 系统权限，113
- 沉没成本，52–53
- 幸存者偏差，53

### T

- 事务控制语言（TCL），113
- 修剪技术，39

### W

- 缩尾处理（Winsorizing），39

### X

#### XML

- 描述，136
- 模式，137–138，148–146
