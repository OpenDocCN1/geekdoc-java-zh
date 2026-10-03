
# 计算机编程全集：初学者编码指南：从零开始学习 Python、Java、SQL、C、C++、C#、HTML 和 CSS 的逐步进阶指南

## 第 1 本书：初学者 Python

进入编程领域的权威初学者指南，向你介绍 Python 编程语言

### 引言

Python 编码语言是你通过学习更多计算机、学习如何编码、甚至制作一些游戏和应用程序来开启之旅的极佳方法。这是最适合入门的语言之一，因为它简单、基于英语，而且许多决定开始学习编程语言的人自然地会喜欢它。本指南将花费一些时间讨论 Python 语言，并帮助你学习一些相关的基础知识，以帮助你上手。

虽然 Python 语言是一种简单且基础、非常适合初学者的语言，但它也拥有强大的功能，当你编写代码时会从中获得乐趣。在本指南中，你将学习入门 Python 语言所需的所有知识，并使其满足你的需求。这本书主要面向对编程较新的人群，更具体地说，是那些想要探索 Python 世界的人。这本书将带你了解编程和 Python 的基础知识。计算机编程听起来很可怕，但其实并不是。最难的部分是选择你想学习哪种语言，因为有太多的选择了。Python 是所有计算机编程语言中最简单的之一；事实上，你需要的一切就在那里，供你调遣。你所做的就是学习如何使用程序提供的内容来编写程序。请继续读完整本书，获取知识，并了解关于这一特定主题需要的关键事项。如果你像我一样对学习一切 Python 以及如何用它编程感到兴奋，那么让我们开始吧。

### 第 1 章：Python 中的数据类型

Python 数据类型

接下来我们需要查看的是 Python 数据类型。Python 中的每个值都有其特定的数据类型。

#### Python 数字

我们可以处理的 Python 数据类型的第一种选择包括 Python 数字。这些将包括复数、浮点数，甚至是整数等内容。它们在 Python 中分别被定义为 `complex`、`float` 和 `int` 类。例如，我们可以使用 `type()` 函数来识别一个值或变量属于哪个类别，然后使用 `isinstance()` 函数来审计一个对象是否存在于特定的类。

当我们处理整数时，它们可以是任意长度的，限制仅在于计算机上可用内存的大小。然后是浮点数。这种数字的精度可以达到 15 位小数，你也可以选择较小的位数。浮点数通过小数点分隔。`1` 是一个整数，而 `10` 将是一个浮点数。

最后，我们有复数。这些数字通常被写为 `x + y` 的形式，其中 `x` 是实部，而 `y` 是虚部。我们需要将这两部分结合起来构成这种数字所需的复数。

#### Python 列表

Python 列表是一个系列有序的项。它是 Python 中使用最频繁的数据类型之一，且具有极高的响应性。列表中显示的所有项可以是相似的，但这不是强制要求。你可以在列表中处理许多不同类型的项，而不需要它们相同，这样更容易操作。

声明列表是一个我们可以使用的简单直接的过程。项之间用逗号分隔，然后只需要将它们包含在这样的括号中，例如：`[]`。我们还可以使用切片运算符来帮助我们从列表中获取某部分或一组项。

Python 中的索引从 0 开始。在处理这些列表时，我们必须记住列表是**可变**（mutable）的。这意味着你列表上的元素值可以被更改或更新。

Python 中的列表是最基本的数据结构，因为它们属于序列。列表内部的元素都被分配了一个数字。换句话说，它们都有一个被分配的位置。列表不仅简单，而且功能多变。在创建列表时，对象之间用逗号分隔，所有这些对象都将位于一组方括号内。列表中的项不需要具有相同的数据类型。

##### 示例

```python
First list = ['science', 'history', 2002, 2030] ;
Second list = [2, 4, 6, 8, 10];
Third list = ["b", "d", "e,", "g"]
```

列表的索引从零开始，你将能够对其进行切片，以便在想要获取列表内部的值时创建子列表，从而在特定的索引处进行切片。

##### 示例

```python
#! usr bin/python
First list = ['science', 'history', 2002, 2030] ;
Second list = [2, 4, 6, 8, 10];

print(First list[2])
print(Second list[2:4])
```

**输出**

```
First list [2]: 2002
Second list [2:4]: [6, 8]
```

#### Python 字符串

Python 字符串是封装在引号内的字符序列。在 Python 中可以使用任何类型的引号，单引号、双引号或三引号。要访问字符串元素，我们使用从索引 0 开始的切片运算符，这意味着第一个字符位于索引 0。这在你需要访问字符时非常有用。在 Python 中拼接字符串我们使用 `+` 运算符，而星号 `*` 则用于重复。

示例：

```python
#! Usbin/python3
Thanks = 'thank you'
print(thanks) # 打印完整字符串
print(thanks[0]) # 打印字符串的第一个字符
print(thanks[2:7]) # 打印字符串的第 3 到第 7 个字符
print(thanks[4:]) # 从字符串的第 5 个字符开始打印
print(thanks * 2) # 打印两次字符串
print(thanks + " again!") # 打印一个拼接后的字符串
```

程序将输出以下内容：

![Image0003.jpg](img/Image0003.jpg)

注意我们有以 `#` 符号开头的文本。该符号表示注释的开始。python `print` 不会对从符号到行尾的文本执行操作。注释旨在通过解释来增强代码的可读性。定义了一个名为 `thanks` 的字符串，值为 `thank you`。`thanks[0]` 帮助我们访问字符串的第一个字符。你还会注意到两个单词之间的空格被算作一个字符。

我们可以使用单引号或双引号来显示我们的字符串，但我们需要确保开头使用的引号类型与结束时使用的类型一致，否则会导致编译器产生一些困惑。我们甚至可以使用三引号来处理多行字符串。

正如我们在上面讨论的元组或列表所看到的，切片运算符也可以用于字符串。而且正如我们在元组中看到的那样，字符串是**不可变**（immutable）的。

#### Python 集合

列表中的下一个是 Python 集合。集合是 Python 中的一个选项，包含一个无序的唯一集合。集合由逗号分隔的值来定义。集合中的元素是没有顺序的，因此我们可以按照任何方式使用它们。

我们可以同时对两个集合执行并集或交集操作。我们处理的集合将是唯一值，它们将确保消除重复项，因为集合是一个无序编译。因此切片运算符不适用于这种选项。

#### Python 列表

列表由封装在方括号（`[]`）内的项组成，项之间用逗号（`,`）分隔。它们类似于 C 语言的数组。虽然数组元素必须属于相同类型，但列表支持在单个列表中存储属于不同类型的项。

![Image00004.jpg](img/Image00004.jpeg) 这里的，上述代码的操作内容与之前处理字符串的代码没有太大区别。执行时，程序输出：

在“print lista” 语句中，我们打印了 `lista` 的内容。注意，每个元素都被视为其对应索引上的一个整体，例如，元素‘john’被视为索引为 0 的列表中的单个元素。

#### Python 元组 (Tuples)

元组与列表的相似之处在于，它们都是对象的序列，但元组是**不可变**的（immutable）。

你可以使用圆括号来创建元组，也可以不使用括号，你只需要确保在元组中想要包含的不同对象之间使用逗号即可。

##### 示例：

```python
Tup1 = ('science', 'history', 2002, 2030)
Tup2 = (5, 9, 7, 4, 2)
Tup3 = "f", "b", "e,", "t"
```

要写一个返回空元组的元组，需要使用 `tuple()` 函数和一组空圆括号。

我们也可以处理所谓的 Python 元组。元组是一个有序的组件序列，与列表是重复的，但有时很难看出它们之间的相似之处和不同之处。

我们将看到的元组和列表之间巨大的差异在于，元组是**不可变**的。元组一旦创建，就是无法修改的。

元组用于写保护数据，而且它们的运行速度通常比列表更快，因为它们不能主动移动。元组通过圆括号 `()` 确定，就像列表一样，项之间也用逗号分隔。

我们然后可以使用切片运算符（slicing operator）来帮助我们选取想要某些组件，但在编写代码或运行程序时，我们仍然无法更改值。

Python 元组与列表相似，区别在于创建元组后；你无法添加、删除或更改元组元素。元组元素应该包含在圆括号 `()` 内。示例：

```python
#!/usr/bin/python3

T1 = () # 创建一个空元组，没有数据
T2 = (22, 34, 55)
T3 = tuple([10, 23, 78, 110, 89]) # 从数组创建元组
T4 = tuple("xyz") # 从字符串创建元组

print(t1)
print(t2)
print(t3)
```

![Image00005.jpg](img/Image00005.jpeg) `print(t4)`

将打印这 4 个元组的值：

有许多函数可以应用于元组上。示例：

```python
#!/usr/bin/python3

T1 = (23, 11, 35, 19, 98)

print("the minimum element in the tuple is", min(t1))
print("the sum of tuple elements is", sum(t1))
print("the maximum element in the tuple is", max(t1))
print("the tuple has a length of", len(t1))
```

执行时，它得到如下结果：

![Image00006.jpg](img/Image00006.jpeg)

首先，我们调用了 `min()` 函数，它返回元组中的最小元素。然后我们调用了 `sum()` 函数，它返回元组元素的总和。`max()` 函数返回了元组中的最大元素。`len()` 函数统计了元组中的所有元素并返回数量。

你可以使用切片运算符访问元组的某些元素，而不是全部。示例：

```python
#!/usr/bin/python3

t = (23, 26, 46, 59, 64)
```

![Image00007.jpg](img/Image00007.jpeg) `print(t[0:2])`

执行时，它打印：我们使用切片运算符访问元组中从索引 0 到 2 的元素，注意元素从索引 0 开始。

#### Python 字典 (Dictionaries)

Python 字典用于存储键值对。通过字典，你可以使用键（key）来检索、删除或修改值（value）。字典也是可变的，意味着一旦声明，你就可以修改它们的值。

要创建字典，我们使用大括号 `{}`。每个字典项都有一个键，后跟一个值，项之间用逗号分隔。示例：

```python
#!/usr/bin/python3

classmates = {
    'john': '234-221-323',
    'alice': '364-32-141'
}
```

我们创建了一个名为 `classmates` 的包含两个项的字典。注意键必须是可哈希类型（hashable），但你可以使用任何值。每个字典键必须是唯一的，第一个元素 john 是键，后面是值；第二个元素 alice 是键。要访问字典元素，请使用字典名和键。示例：

```python
#!/usr/bin/python3

classmates = {
    'john': '234-221-323',
    'alice': '364-32-141'
}

print("the number for john is", classmates['john'])
```

![Image00008.jpg](img/Image00008.jpeg) `print("the number for alice is", classmates['alice'])`

最后两个元素帮助我们访问字典值。它打印：要知道字典的长度，请如下所示运行 `len()` 函数：

```python
len(classmates)
```

上述操作将返回 2，因为字典只有两个元素。

在用 Python 工作时，字典在大括号内定义，每个组件都是 `key: value` 形式的组合。键和值可以根据你想要编写的代码类型是任何类型。我们也可以使用键来帮助检索所需的相应值，但我们完全无法反过来以那种方式进行工作。

处理不同类型的数据对于你在 Python 编码中进行的所有工作都至关重要，并且在处理数据科学时可以为你提供帮助。看看 Python 语言提供的不同数据类型。

#### 类型转换 (Datatype conversion)

Python 允许将数据从一种类型转换为另一种。从一种数据类型转换为另一种的过程被称为类型转换（type casting）。

如果你需要将整数类型转换为浮点类型，可以调用 `float()` 函数。示例：

```python
#!/usr/bin/python3

height = 20

print("the value of height in int is", height)
print("the value of height in float", float(height))
```

在上述示例中，`height` 初始化为 20。我们调用了 `float()` 函数并将 `height` 作为参数。整数值 20 已转换成浮点值 20.0。程序打印如下：

![Image00009.jpg](img/Image00009.jpeg)

要将浮点转换为整数，可以调用 `int()` 函数。示例：

```python
#!/usr/bin/python3

height = 20.0

print("the value of height in float is", height)
```

![Image00010.jpg](img/Image00010.jpeg) `print("the value of height in int is", int(height))`

程序打印如下：我们调用了 `int()` 函数并将参数 `height` 传递给它。它将 20.0 转换成了 20，这是一个浮点到整数的转换。

如果你需要将数字转换为字符串，可以调用 `str()` 函数。该数字随后将被转换为字符串。示例：

```python
#!/usr/bin/python3

num = 20

print("the value of num in int is", num)
```

![Image00011.jpg](img/Image00011.jpeg) `print("the value of num in string is", str(num))`

程序输出：虽然值相同，但 Python 解释器处理它的方式不同。浮点到字符串的转换也可以类似地进行。

### 第 2 章：变量、运算符、类型及其用途

运算符是表示特定过程实现的符号。它们被用于操作程序中的数据。Python 使用不同类型的运算符。

#### 算术运算符

##### 加法 (+)

加法运算符 `+` 将运算符两侧的操作数相加：

```python
>>> 12 + 8
20
```

##### 减法 (-)

减法运算符 `-` 从左侧操作数的值中减去右侧操作数的值。

```python
>>> 40 – 3
37
```

##### 乘法 (*)

乘法运算符 `*` 将运算符左侧和右侧的值相乘：

```python
>>> 20 * 3
60
```

##### 除法 (/)

除法运算符 `/` 将左操作数除以右操作数的值：

```python
>>> 20 / 5
4.0
```

##### 幂 (**)

幂运算符 `**` 将第一个操作数提升到第二个操作数所指定的幂。

```python
>>> 4**4
256
```

##### 取模 (%)

取模运算符 `%` 返回左操作数除以右操作数后的余数。

```python
>>> 38%5
3
```

##### 整除 (//)

整除运算符 `//` 执行左操作数除以右操作数的除法，并返回整数商，同时舍弃小数部分。

```python
>>> 35//3
11
```

![Image00012.jpg](img/Image00012.jpeg)

#### 比较运算符

#### 逻辑运算符

Python 支持 3 逻辑运算符：

- **或 (Or)**: `x or y`，如果 `x` 为假，则计算 `y`；否则，返回 `x` 的求值。

- **与 (And)**: `x and y`，如果 `x` 为假，则返回 `x` 的求值；否则，如果 `x` 为真，则计算 `y`。

- **非 (Not)**: `not x`，如果 `x` 为假，返回 `true`；否则，如果 `x` 为真，返回 `false`。

#### 输入与输出

##### 输入

许多程序需要用户输入才能运行。输入可以来自键盘、鼠标点击、数据库、外部存储或互联网。键盘是收集用户输入最常用的通道。因此，python 特有一个内置的 `input()` 函数来识别键盘输入。

##### `input()` 函数

Python 的 `input()` 函数通过一个名为 `prompt string`（提示字符串）的可选参数交互式地收集键盘输入。每当调用 `input` 函数时，程序都会显示该 `prompt string`。程序执行会暂停，直到用户对提示输入响应。

为了说明，这里有一个从用户收集收集和年龄信息的简单程序：



```python
name = input("please type your name: ")
print("welcome, " + name + "!")
age = input("how old are you, " + name + "? ")
print("thank you. you are " + name + " and you’re " + age + " years old.")
```

当你运行程序并为姓名输入 `marky`，为年龄输入 `24` 时，屏幕按行显示的内容如下：

```
please type your name: marky
welcome, marky!
How old are you, marky? 24
Thank you. you are marky, and you’re 24 years old.
```

#### 输出

Python 的内置 `print()` 函数用于将数据输出到屏幕（屏幕是标准输出设备）。`print` 命令的语法为：`print(value,)`。

以下是它的用法示例：

```python
>>> print("i am a programming student.")
I am a programming student.
>>> print(25)
25
>>> print(4**3)
64
>>> xyz = 50
>>> print('the value of xyz is', xyz)
The value of xyz is 50
>>> animal = "rhinoceros"
>>> print(animal)
Rhinoceros
```

Python 允许打印多个值或变量，这些值必须在括号内用逗号分隔。例如，以下是一系列赋值：

```python
A = "under"
B = "16 years old"
C = "result"
>>> print("job:", A, B, C)
job: under 16 years old result
```

#### 输出字符串格式化

格式化选项允许用户创建更具读性的输出。Python 提供了 `.format()` 方法来格式化字符串。使用花括号 `{}` 作为格式化值的占位符。

如果参数在 `.format()` 中的位置与你期望的顺序一致，你可以在打印语句中使用空花括号：

```python
x = 50
y = 100
>>> print("the value of x is {} and y is {}".format(x, y))
The value of x is 50 and y is 100.
```

但是，如果你希望参数出现的顺序与它们在 `.format()` 语句中的位置不同，你需要在花括号内指定索引。第一个参数的索引为 `0`，第二个参数索引为 `1`，依此类推。

```python
x = 50
y = 100
>>> print("the value of y is {1} and x is {0}".format(x, y))
The value of y is 100 and x is 50.
```

这里是其他示例。这次给出的是值，而不是存储在变量中：

这些运算符用于比较操作数的值并识别它们之间的关系。它们包括等于（`==`）、不等于（`!=`）、小于（`<`）、大于（`>`）、大于等于（`>=`）和小于等于（`<=`）。

### 示例：

```python
#!/usr/bin/python3

N1 = 6
N2 = 5

If (n1 == n2):
    print("the two numbers have equal values")
else:
    print("the two numbers are not equal in value")

If (n1 != n2):
    print("the two numbers are not equal in value")
else:
    print("the two numbers are equal in value")

If (n1 < n2):
    print("n1 is less than n2")
else:
    print("n1 is not less than n2")

If(n1 > n2 ):
    print("n1 is greater than n2")
else:
    print("n1 is not greater than n2")

N1,n2=n2,n1 #the value of n1 and n2 will be swapped. n1=5, n2=6

If ( n1 <= n2 ):
    # The code will print the following:
    ![Image00014.jpg](img/Image00014.jpeg)
```

`n1` 的值为 6，而 `n2` 的值为 5。在两个操作数上使用等于运算符（`==`）将返回假值，因为两个操作数不相等。这将导致执行 `else` 部分。不等于运算符（`!=`）将返回真，因为两个操作数的值不相等。在这种情况下，唯一可能看起来复杂的逻辑是值的交换。`n1` 的值从 6 变为 5，而 `n2` 的值变为 6。该交换语句下方的语句将使用这两个新值进行操作。

### 赋值运算符

这些运算符是赋值运算符（`=`）与其他运算符的组合。赋值运算符的一个很好的例子是 `+=`。表达式 `p+=q` 意味着 `p=p + q`。表达式 `p/=q` 意味着 `p=p / q`。赋值运算符涉及将赋值运算符与其他运算符相结合。

### 示例：

```python
#!/usr/bin/python3

N1 = 6
N2 = 5
N3 = 0

N3 = n1 + n2
print("the value of n3 is: ", n3)

N3 += n1
print("the value of n3 is: ", n3 )

N3 *= n1
print("the value of n3 is: ", n3 )

N3 /= n1
print("the value of n3 ", n3 )

N3 = 2
N3 %= n1
print("the value of n3 is: ", n3)

N3 **= n1
print("the value of n3 is: ", n3)

N3 //= n1
![Image00015.jpg](img/Image00015.jpeg)
print("the value of n3 is: ", n3)
```

代码执行时将打印以下内容：

语句 `n3 = n1 + n2` 非常直观，因为我们只是将 `n1` 的值加到 `n2` 的值上。在表达式 `n3 += n1` 中，我们将 `n3` 的值加到 `n1` 的值上并将结果赋值给 `n3`。然而，请注意在上一个语句中，在将 `n1` 加到 `n2` 后，`n3` 的值变为 `11`。因此我们有 11+6，得到 17。之后，变量 `n3` 的新值将是 17。表达式 `n3 = n1` 意味着 `n3= n3 n1`。这将是 17 * 6，结果为 12。这就是这些运算符在 Python 中的工作方式！

### 成员运算符

这些是用于测试是否属于元素序列成员的运算符。元素序列可以是字符串、列表或元组。两个连接符包括 `in` 和 `not in`。如果在序列中找到你指定的值，则 `in` 运算符返回真，如果在序列中未找到指定的值，则 `not in` 将求值为真。

### 示例：

```python
#!/usr/bin/python3

N1 = 7
N2 = 21
Ls = [10, 20, 30, 40, 50]

If ( n1 in ls ):
    print("n1 was found in the list")
else:
    print("n1 was not found in the list")

If ( n2 not in ls ):
    print("n2 was not found in the list")
else:
    print("n2 was found in the list")

N3=n2/n1
If ( n3 in ls ):
    print("n1 was found in the list")
else:
    ![Image00016.jpg](img/Image10016.jpeg)
    print("n1 was not found in the list")
```

代码执行后将打印以下内容：

`n1` 的值为 7。这并不是列表的一部分；这就是为什么使用 `in` 运算符返回假值。这导致了 `else` 部分的执行。`n2` 的值为 21。这不在列表中。这就是为什么使用 `in` 运算符返回假值。这导致了 `else` 部分的执行。

### 标识运算符

这些运算符用于比较两个内存地址。Python 有一个名为 `id()` 方法返回对象的唯一标识符。`is`：如果两个操作数指向相同的对象，则求值为真。`is not`：如果两个操作数不指向相同的对象，则求值为真。

### 示例：

```python
#!/usr/bin/python3

N1 = 45
N2 = 45
print('the initial values are, n1=',N1, ':id=',id(N1), 'n2=',N2, ':id=',id(N2))

If ( n1 is n2 ):
    print("1. n1 and n2 share an identity")
else:
    print("2. n1 and n2 do not share an identity")

If ( id(n1) == id(n2) ):
    print("3. n1 and n2 share an identity")
else:
    print("4. n1 and n2 do not share an identity")

N2 = 100
print('the variable values are, n1=',N1, ':id=',id(N1), 'n2=',N2, ':id=',id(N2))

If ( n1 is not n2 ):
    print("5. n1 and n2 do not share an identity")
else:
    ![Image00017.jpg](img/Image00017.jpeg)
    print("6. n1 and n2 share an identity")
```

除了执行特定任务并退出的程序外，所有程序都至少包含一个循环。通常，这是一个主循环，程序在其中不断循环，等待用户或对象的输入以对其进行操作。

此外，循环可以用于使用一组紧凑的指令对对象执行重复过程。

Python 提供了两种循环：`for` 循环和 `while` 循环。它们都允许对特定操作进行重复循环，但在测试循环是否应该继续（待处理）方面有所不同。

### `for` 循环

在 `for` 循环中，循环将在给定的项目范围 own 执行。

例如：

```python
for x in range(0,3):
    print(x)
```

```text
0
1
2
```

在这个示例中，有几点需要注意：

- 首先，其语法与我们之前介绍过的 `if` 语句相似。
- `for` 循环以冒号 `:` 结尾。
- 如果 `for` 循环中只有一条指令，我们可以将该指令直接写在冒号后的同一行。其其后的 `return` 将缩进到 `for` 循环之外的下一条指令。
- 如果 `for` 命令包含多条指令，请将这些指令写在下一行；它们将缩进以显示它们包含在循环内部。
- 在最后输入一个空行将关闭循环，并让缩进回退，以便处理循环之外的后续指令。

#### `range` 命令

接下来，我们有 `range()` 命令。

`range` 命令是一个 Python 内置方法，用于生成数字范围，它并不是 `for` 循环语法的明确部分。它只是为了生成要迭代的数字。像 Python 中的其他范围一样，提供的数字并不代表从 0 到 3 的范围；它们代表从 0 开始输出三个数字，即我们得到了 0、1 和 2。`range` 中不会输出 3。

这与你可能在其他语言中熟悉的 `for` 循环略有不同。在那些语言中，给定的范围通常包含定义的最后一个数字——例如，`for x=1` 到 `10` 将输出 1 到 10，而不是 1 到 9。

虽然我们使用 `range()` 函数来生成 `for` 循环中迭代的数字，但这绝不是唯一的选择。我们可以从任何可迭代源中提取数值并对该源进行迭代。例如，我们可以使用列表、元组或字符串的 `length` 来处理该项目。

```python
x = ['apples', 'oranges', 'bananas', 'peaches', 'plums']
for y in x:
    print(y)
```

```text
apples
oranges
bananas
peaches
plums
```

在这种情况下，重要的是，我们正在顺序遍历列表值并将 `y` 设置为这些值。我们没有将 `y` 设置为 0 到 4 的位置值。如果我们使用 `print(x[y])`——打印列表中位置 `y` 处的字符串——将得到一个说明 `y` 不能为字符串（`str`）的异常。要使用位置数字遍历列表，我们必须将 `y` 设置为数值范围并以这种方式进行迭代。

```python
for y in range(0, len(x)):
    print(x[y])
```

```text
apples
oranges
bananas
peaches
plums
```

这种方法可以更容易获取列表中的每个 `x` 值。`range` 方法包含一个 `step` 值属性，允许我们以非 1 的步长遍历列表。例如，要获取列表中的每隔一个项目，我们将使用：

```python
for y in range(0, len(x), 2):
    print(x[y])
```

```text
apples
bananas
plums
```

或者，反向获取列表：

```python
for y in range(len(x)-1, -1, -1):
    print(x[y])
```

```text
plums
peaches
bananas
oranges
apples
```

### `while` 循环

当指定条件为真时，`while` 循环将继续。

例如：

```python
y = 1

while y <= 10:
    print(y)
    y += 1
```

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
10
```

在这种情况下，只要 `y` 小于等于 10，循环就会继续。与指定在特定范围内执行的 `for` 循环不同，`while` 循环只要条件真就会继续；否则循环可能会变成无限循环。为了防止这种情况，必须在循环内部包含使条件变为假的代码。在这种情况下，每次循环运行时都会执行 `y += 1`。如果你出错了且程序陷入了无限循环，可以通过按 `ctrl-c` 退出程序。

#### `break` 命令

`break` 是优雅退出循环的另一种额外方法。`break` 命令强制终止循环。在许多情况下，可以使用 `break` 有条件地退出循环。

### 函数、类和方法

处理这种情况的更好方法是将其转换为函数。理想情况下，编写的函数应该是完全自足的。函数是一个执行特定任务并可以被调用的代码块。函数所需的任何值都应该从调用代码传递。

所以，在这种情况下，我们需要设置函数来接受半径和高度，它们产生的任何结果都应该返回给调用源。通过将代码放在函数中，我们可以编写一次并在需要时使用。

Python 函数的结构语法使得这变得简单：

```python
def functionname(arg1, arg2..):
    # 执行的代码
    return return_value
```

函数名可以是任何不是保留字或程序已使用的引用名称。函数所需的参数应该像所示：

```python
import math

### 赋值变量

r = 5 # 半径
h = 10 # 高度
v = 0 # 体积

### 计算圆柱体积

v = (math.pi * math.pow(r, 2)) * h # 体积=(π*r²)*h

### 输出结果

print(v)
```

这些参数将是函数的局部变量，并遵循 Python 中任何变量的相同规则。

函数不需要这些参数，但在大多数情况下它们会被使用。

要运行的代码是任何 Python 代码，这些代码是函数执行任务所必需的。末尾的 `return` 命令会将你指定的任何变量的值传回给调用代码。

`return` 调用不是必须的，但在大多数情况下都会使用。

因此，将我们的圆柱体积计算转换为函数，它看起来像这样：

```python
### import math

Import math

### define function

def cylindervol(r, h): # r=radius, h=height
    V=(math.pi*math.pow(r,2))*h # volume=(π*r²)*h
    return v # return the volume

### output the result

Print(cylindervol(5, 10)) # print 圆柱体积，r=5, h=10
```

所以，我们所做的工作是提取实际计算所需的重复代码，并将其放入我们命名为 `cylindervol` 的函数中。

该函数接受两个参数——`r` 表示半径，`h` 表示高度。这两个参数就是完成计算所需的全部内容。

然后我们进行计算并将结果存放在 `v` 中，随后将其返回给调用者。

与其简单地在 `print()` 语句中调用函数，我们可以像这样给调用赋值一个变量：

```python
Vol = cylindervol(5,10)
```



`Vol` 将等于 `785.3981633974483` —— 或者说是函数的返回值。

由于此函数仅依赖于调用者传递的值，因此它是完全可移植的，只要以相同的方式调用，就可以在任何程序中使用它。这一事实允许我们构建到下一个层次，即类（`class`）。

类通常被定义为一组相关的函数。

我们目前已经建立了计算圆柱体积的代码。我们可以在此基础上扩展，创建一个体积类，其中包含计算圆柱体积和立方体体积的函数。

```python
### import math

Import math

### define class

class volume(object):

    def cylindervol(self, r, h): # r=radius, h=height

        self.v=(math.pi*math.pow(r,2))*h # volume=(π*r²)*h

        return self.v

    def cube_vol(self, l, w, h):

        self.v=(l*w*h)

        return self.v

### output the result

Vi=volume() #创建 volume 类的一个实例

V=vi.cylindervol(5,10) #通过调用 volume 类中的 cylindervol 设置 v

Print(v) #打印结果

V=vi.cube_vol(5,10,10) #通过调用 volume 类中的 cube_vol 设置 v

Print(v) #打印结果
```

在这个例子，我们创建了一个名为 `volume` 的类。

在类内部，我们定义了两个方法——在类中，函数被称为方法（`methods`）——一个用于 `cylindervol`，另一个用于 `cube_vol`。

这些方法与我们用于对应的独立函数使用的参数相同，唯一的例外是第一个参数 `self`。

在面向对象编程中，`self` 的值通常用于引用由类创建的对象的实例。

在我们上面的代码中，我们首先通过给变量赋值来创建类的实例（`vi=volume()`）。

`self` 术语用于访问分配给 `vi` 变量实例的类特定值。这允许不同的实例对相同的变量具有不同的值，并允许我们测试这些值。

一个更清晰的例子可能是如果我们正在创建一个赛车游戏，我们可以有一个汽车类。该类可以拥有方法，用于为“汽车”对象分配品牌、型号、速度、颜色或其他变量。

如果通过通过调用 `cara=car()` 和 `carb=car()` 创建了两辆汽车，那么 `cara` 的 `self` 属性将指向一个与 `carb` 的 `self` 属性不同的汽车对象。

这两个对象可以为类中定义的品牌、型号、速度和颜色变量存储不同的值。

一旦创建了对象，我们就可以相同地调用它的方法。

唯一的区别是我们使用点符号表示 `vi.cylindervol(5,10)`。由于此函数仅依赖于调用者传递的值，因此它是完全可移植的，只要以相同的方式调用，就可以在任何程序中使用它。这一事实允许我们构建到下一个层次，即类。

为了提高易用性，请在循环中始终包含计数器和 `break` 语句。

无限循环是永远不会停止的循环。由于它们永远不会停止，它们很容易让你的程序无响应、崩溃或耗尽计算机的所有资源。这里有一个无限循环的示例：

```python
while (true):

    print("this will never end until you stop it")
```

为了避免这种情况，请在你的循环中始终包含计数器和 `break` 语句：

```python
counter = 0

while (true):

    print(counter)

    counter += 1

    if counter == 5:

        break
```

`continue` 关键字用于跳过当前迭代的剩余代码并返回循环开始。

`continue` 关键字类似于 `break` 的软版本。`break` 是跳出整个循环，而 `continue` 只是跳出一次迭代并返回循环语句。

```python
password = "secret"

input = ""

while (input != password):

    input = input()

    continue

print("this will not get printed.")
```

在示例中，如果输入错误，则打印语句将被跳过，循环将持续直到用户输入正确的密码。

这是一个实用的应用，可以让你更容易理解 `continue` 语句的作用。

```python
carbrands = ["toyota", "volvo", "mitsubishi", "volkswagen"]

for brands in carbrands:

    if (brands == "volvo"):

        continue

    print("i have, a " + brands)
```

输出：

```
I have, a toyota
I have, a mitsubishi
I have, a vol
```

当你正在解析或循环一个序列时，会有一些你不想处理的项。你可以使用 `continue` 语句来跳过那些不想处理的项。在上面的示例中，当选中 "volvo" 时，程序命了 `continue`，因此没有打印“i have, a volvo”。这导致程序返回并处理列表中的下一个汽车品牌。

## 函数的语法

函数的语法看起来如下所示：

```python
def function_name(parameters):

    """docstring"""

    statement(s)

    return [expression]
```

以下是函数语法的详细拆解：

- `def` 关键字：这标记了函数头的开始。
- `function_name:`：这是一个唯一标识函数的名称。函数名的命名规则几乎与我们在书开头学到的变量规则相似。
- `parameters`（参数）或 `arguments`（参数）：值通过放在括号 `()` 中传递给函数。`parameters` 是可选的。
- 冒号 `:` 标记了函数头的结束。
- `"""docstring"""`：（`docstring`）是一个可选的文档字符串。它描述了函数的用途。
- `statement(s)`（语句）：必须有一个或多个有效语句来组成函数体。注意，这些语句是缩进的（通常是制表符或四个空格）。
- 可能有一个可选的 `return` 语句，用于从函数返回一个值或多个值。

## 创建和调用函数

要在脚本中使用你创建的函数，你需要从 Python 提示符、程序或函数中调用它。

## 练习 55：创建一个函数

```python
def greeting(name,):

    """当人的名字作为参数传递时，此函数向用户问问候"""

    print ("greetings,", name + "!")
```

你可以只需通过输入函数名称以及相应的参数来调用函数。修改之前的练习 55 代码，看看如何调用函数 `greeting`。

## 练习 56：调用函数

```python
def greeting(name,):

    """当人的名字作为参数传递时，此函数向用户问候"""

    print ("greetings,", name + "!")

username = str(input("enter your name,: "))

greeting(username,)
```

练习 55 中的代码首先定义了一个名为 `greeting` 的函数，它需要一个参数 `name,`。它会提示用户输入一个字符串，该字符串将赋值给变量 `username`，并在调用函数 `greeting` 时作为参数使用。

## Docstring

紧接函数头后的第一个字符串被称为文档字符串，或简称为 `docstring`。函数的这部分是可选的，简要解释函数的功能。每当你创建一个新函数时，包含一个描述性的 docstring 是一个良好的习惯，因为以后你或另一个查看阅你代码的程序员可能需要它来理解函数的作用。务必记录你的代码！

我们已经详尽地解释了 `greeting` 函数的作用。如你所见，我们使用了三引号字符串来使描述扩展到多行。在函数的属性中，docstring 可以 `__doc__` 获取。例如，`greeting` 函数会在练习 57 所示的 Python `print()` 函数中出现。

## 打印 docstring

```python
def greeting(name):

    """当名字作为参数传递时，此函数向用户问候."""

    print ("greetings,", name + "!")

print (greeting.__doc__)
```

函数中可选的 `return` 语句用于作为出口返回到调用它的地方。`return` 语句的语法如下：

```python
return [expression list]
```

`return` 语句可以包含被求值的表达式以返回一个值。如果语句中没有表达式，或者没有包含 `return` 语句，定义的函数在调用时将返回一个 `None` 对象。我们在练习 55 到 57 中的 `greeting` 函数返回 `None` 值，是因为我们没有包含 `return` 语句。

## 函数参数

在 Python 中，你可以使用以下四种形式参数的任意一种调用函数：

- `default arguments`（默认参数）
- `required arguments`（必需参数）
- `keyword arguments`（关键字参数）
- `variable-length arguments`（变长参数）

### 默认参数

如果在函数调用参数中没有指定值，默认参数将假设默认值。

```python
def studentinfo(name, gender="male",):

    """此函数打印传递给函数参数中的信息."""

    print ("name:", name,)

    print ("gender:", gender)

    return;

studentinfo (name ="john")

studentinfo (name ="mary", gender="female")
```

在练习 59 中，你可以看到我们如何将参数 `gender` 的默认值指定为 "male,"当我们不在某个值中定义 `gender` 时，将使用默认值。

### 必需参数

必需参数必须按照精确的位置顺序传递给函数，以匹配函数定义。如果按错误的顺序传递参数，或者传递的参数多于或少于定义的数量，将遇到语法错误。

### 关键字参数

函数调用与关键字参数有关。这意味着当在函数中使用关键字参数时，调用者应通过参数名称来标识参数。使用这些参数，你可以乱序放置参数甚至完全跳过它们，因为 Python 解释器能够将提供的值与提供的关键字匹配。

```python
def studentinfo(name, age):

    """此函数打印传递给函数参数中的信息."""

    print ("name:", name,)

    print ("age:", age)

return;

studentinfo (age =21, name ="john")
```

注意，在练习 60 中使用关键字参数，参数的顺序并不重要。

### 变长参数

在某些情况下，函数可能需要比你定义时指定的更多的参数。这些变量被称为变长参数。与必需和默认参数不同，变长参数可以包含在函数定义中无需分配名称。

注意，逗号放置在持有非关键字变量参数的元组名称之前。如果在调用函数时没有定义额外的参数，则该元组将保持为空。

## 第 4 章：文件操作

一个文件是一个可以用于存储数据的名称和内存位置。保存文件可以让你在将来需要时访问它们。Python 通过 `file` 对象对象来处理文件管理。

### 文件操作

Python 支持 4 种基本的文件相关操作，即：

1. 打开文件
2. 读取文件
3. 写入文件
4. 关闭文件

### 文件打开模式

可以使用不同的模式打开 python 文件。熟悉这些模式对于确保文件的安全和完整性至关重要。

以下模式可用于二进制格式访问文件：

- `rb+` 以读和写的模式打开一个文件。
- `wb+` 以写和读的模式打开一个文件：会覆盖同名文件，或创建一个新文件。
- `ab+` 以追加和读的模式打开一个文件。

这些是文件打开语句的示例：

```python
file_obj = open("myfile.txt") # 以默认模式打开文件

file_obj = open("myfile.txt", "w") # 以写模式打开文件

file_obj = open("pict.bmp", "rb+") # 以读和写模式打开二进制文件
```

### 关闭文件

关闭文件是 python 文件管理和维护中重要的一步。关闭打开的文件可以释放已使用的资源，防止对数据的意外修改或删除，并指示 python 将数据写入你的文件。

这里是打开和关闭文件的语法：

```python
file_obj = open("myfile.txt") # 打开 myfile.txt 文件

file_obj.close() # 关闭已打开的文件
```

### 写入文件

本节将说明你如何向 python 文件写入数据。

首先，要构建一个文件，使用 `'w'`（写）模式打开一个新文件，并创建一个新的文件对象以便访问文件：

```python
>>> file_obj = open("afile.txt",""w") # 打开名为 ‘afile.txt’ 的新文件
```

现在，使用 `write()` 方法将字符串写入 `afile.txt`：

```python
>>> file_obj.write("a file is used to store important information.\n") 47
```

注意，它返回字符串中的字符数。同样，字符串写入时带有一个换行符 `\n`，告诉 python 将其保存为单独行。

```python
>>> file_obj.write("you will use a file object to handle python files.\n") 51

>>> file_obj.write("you can store program information on a file.\n") 45
```

现在你已经完成了对 `afile.txt` 的写入，你必须关闭文件：

```python
>>> file_obj.close()
```

### 读取文件

在 python 中有多种方法读取文本文件：

1. `readlines()` 方法
2. `while` 语句
3. 使用迭代器
4. `with statement`

### `readlines()` 方法

`readlines()` 方法是 python 中打开文件最简单的方法之一。它利用 `file` 对象来访问并读取整个文件。然后，你将创建一个变量来存储读取的文件，并使用 `print` 查看文件。

为了说明，用以下方式打开 `afile.txt`：

```python
file_obj = open('afile.txt', "r")
```

现在，创建一个变量 `lines` 来存储来自 `readlines()` 方法的文本：

```python
>>> lines = file_obj.readlines()
```

要访问文件内容，在提示符输入 `lines`：

```python
>>> lines['a file is used to store important information.\n', 'you will use a file object to handle python files.\n', 'you can store program information on a file.\n']
```

### 使用 `while` 循环逐行读取

简单的 `while` 循环是按行读取文件的更高效的方法。这里是一个简单的 `while` 循环：

```python
file_obj = open('myfile.txt') # 只读模式

line = file_obj.readline() # 读取第一行

while line:

    print(line)

    line = file_obj.readline()
```

文件被用于存储重要信息。你将使用文件对象来处理 python 文件。你可以在文件上存储程序信息。这里是运行 `while` 循环时的输出：

### 使用迭代器逐行读取

使用迭代器是另一种按行读取文本文件的方法。这里有一个你可以用来遍历 `myfile` 的简单 `for` 循环：

```python
fo = open('myfile.txt')

for line in fo:

    print(line)

fo.close()
```

你的输出将与 `while` 循环逐行的输出类似：文件被用于存储重要信息。你将使用文件对象来处理 python 文件。你可以在文件上存储程序信息。

### 使用 `with statement`

`with` 结构有助于安全打开文件并允许 python 在不使用 `close()` 方法的情况下自动关闭文件。你也可以用它来读取文件的每一行。

这里有一个可以用于读取 `myfile` 每一行的 `with` 块：

```python
line_count = 0

with open('myfile.txt', 'r') as newfile:

    for line in newfile:

        line_count += 1

        print('{:>3} {}'.format(line_count, line))
```




当你运行代码时将获得如下输出：

1. 文件被用于存储重要信息。
2. 你将使用文件对象来处理 Python 文件。
3. 你可以在文件上存储程序信息。

### 处理文件

程序是考虑到输入和输出的。为了学习处理文件，你需要了解`open()`函数。`open()`函数有一个必需参数和两个可选参数。必需参数是文件名。第二个参数是访问模式，第三个参数是缓冲大小。文件名参数需要字符串数据。访问模式需要字符串数据，但默认为`"r"`。缓冲参数需要整数且默认为`0`。

为了练习，使用`open()`函数在你的 Python 目录下创建一个名为`sample_file.txt`的文件。

尝试这段代码：

```python
>>> file_1 = open("sample_file.txt")
>>> _
```

注意，`file`函数返回一个文件对象。示例中的语句将文件对象赋值给变量`file_1`。

`file`对象有多个属性，三个三个：

- `Name`：FileName。
- `Mode`：包含访问文件时使用的模式。
- `Closed`：如果文件已打开则返回`false`，如果文件关闭则返回`true`。当你使用`open()`函数时，文件被设置为打开。

现在，访问这些属性：

```python
>>> file_1 = open("sample_file.txt")
>>> file_1.name
'sample_file.txt'
>>> file_1.mode
'r'
>>> file_1.closed
False
>>> _
```

当你完成文件操作后，使用`close()`方法关闭它们。

```python
>>> file_1 = open("sample_file.txt")
>>> file_1.closed
False
>>> file_1.close()
>>> file_1.closed
True
>>> _
```

记住，关闭文件不会删除变量或对象。要重新打开文件，只需打开并重新分配文件对象。例如：

```python
>>> file_1 = open("sample_file.txt")
>>> file_1.close()
>>> file_1 = open(file_1.name)
```

```python
>>> file1.close(d)
False
>>> _
```

### 从文件中读取

在继续之前，请在你的文本编辑器中打开`sample_file.txt`。在其中输入“hello world”并保存。回到 Python。

要读取文件内容，请使用`read()`方法。例如：

```python
>>> file1 = open("sample_file.txt")
>>> file1.read()
'hello world'
>>> _
```

#### 文件指针

每当你访问一个文件时，Python 都会设置文件指针。文件指针就像你文字处理器中的光标。对文件进行的任何操作都从文件指针所在的位置开始。

当你打开一个文件，并且它被设置为默认访问模式（即“r”，只读）时，文件指针被设置在文件的开头。要了解文件指针的当前位置，你可以使用`tell()`方法。例如：

```python
>>> file1 = open("sample_file.txt")
>>> file1.tell()
0
>>> _
```

你对文件执行的大多数操作都会移动文件指针。例如：

```python
>>> file1 = open("sample_file.txt")
>>> file1.tell()
0
>>> file1.read()
'hello world'
>>> file1.tell()
11
>>> file1.read()
''
>>> _
```

要将文件指针移动到指定的位置，你可以使用`seek()`函数。例如：

```python
>>> file1 = open("sample_file.txt")
>>> file1.tell()
0
>>> file1.read()
'hello world'
>>> file1.tell()
11
>>> file1.seek(0)
0
>>> file1.read()
'hello world'
>>> file1.seek(1)
1
>>> file1.read()
'ello world'
>>> _
```

`seek()`方法有两个参数。第一个是`offset`，它根据第二个参数设置指针的位置。此外，该参数是提供参数的。

第二个参数是可选的。它是`when`，决定了“寻址”从哪里开始。它的默认值为`0`。

如果设置为`0`，Python 将指针的位置设置为`offset`参数的值。

如果设置为`1`，Python 将指针的位置相对于指针当前的位置，或在当前位置的基础上设置。

如果设置为`2`，Python 将指针的位置相对于文件末尾，或在文件末尾的基础上设置。

注意，最后两个选项要求访问模式具有二进制权限。如果访问模式没有二进制权限，最后两个选项将用于确定指针的当前位置`seek(0, 1)`和文件末尾的位置`seek(0, 2)`。例如：

```python
>>> file1 = open("sample_file.txt")
>>> file1.tell()
0
>>> file1.seek(1)
1
>>> file1.seek(0, 1)
0
>>> file1.seek(0, 2)
11
>>> _
```

#### 文件访问模式

要向文件写入内容，你需要了解更多 Python 中的文件访问模式。有三种文件操作：读取、写入和追加。

读取允许你访问并复制文件内容的任何部分。写入允许你覆盖文件内容并创建一个新文件。追加允许你在保持其他内容完整的同时向文件写入。

访问模式有两种类型：字符串和二进制。字符串访问允许你像打开文本文件一样访问文件内容。二进制访问允许你以原始形式（二进制）访问文件。在你的示例文件中，使用字符串访问允许你读取行“hello world”。使用二进制访问文件将允许你以二进制读取“hello world”，结果将是`b'hello world'`。例如：

```python
>>> x = open("sample_file.txt", "rb")
>>> x.read()
```

字符串访问对于编辑文本文件有用。二进制访问对于任何其他内容，如图片、可执行文件。在书中，你只会学习如何处理文本文件。在`open()`函数的`mode`参数中，你可以输入多个值。但你不需要记忆组合。你只需要知道这些组合。每个字母和符号都代表一种访问和操作。例如：

- `R` = 只读——文件在开头
- `R+` = 读和写
- `A` = 追加——文件在末尾
- `A+` = 读取和追加
- `W` = 覆盖——由于你创建了文件，文件被重置为 0
- `W+` = 读取和覆盖
- `B` = 二进制

默认情况下，访问模式设置为字符串。你需要添加`b`来允许二进制访问。例如，“rb”。

向文件写入：

在向文件写入内容时，你必须始终记住 Python 是覆盖文件而不是插入文件。例如：

```python
>>> x = open("sample_file.txt", "r+")
>>> x.read()
'hello world'
>>> x.tell()
0
>>> x.write("text")
4
>>> x.tell()
4
>>> x.read()
'o world'
>>> x.seek(0)
0
>>> x.read()
'text world'
>>> _
```

你可能期望结果文本是“texthello world”。`file`对象的`write`方法会从指针的当前位置开始逐个替换每个字符。

##### 练习题

为了练习，你需要完成以下任务：

1. 创建一个名为`test.txt`的新文件。
2. 在文件中写入完整的练习题说明。
3. 关闭文件并重新打开。
4. 读取文件并将光标设回 0。
5. 关闭文件并使用追加访问模式打开它。
6. 在文件末尾添加这些说明的重写版本。
7. 创建一个新文件，通过复制`test.txt`文件的内容在其中放入类似的内容。

## 第 5 章：面向对象编程

### 类与面向对象编程

Python 是一种面向对象的编程语言。这意味着它侧重于处理统称为“对象”的数据结构。对象可以是 Python 中可以命名的任何东西，包括字符串、函数、整数、类、浮点数、文件和方法。对象可以引用利用它们的数据和方法。它们可以用多种方式使用。它们可以作为参数传递，并赋值给变量、列表、元组、字典。Python 中几乎一切都是对象。

类是一种数据类型，类似于字符串、列表、浮点数或整数。类属于一个名为`type`的类型。存储在类对象中的数据称为属性，而与之相关的函数称为方法。类仅仅是创建、组织和管理对象的一种。当你从类创建对象时，该对象被称为类的实例。

#### 定义类

类定义从关键字`class`开始，后面跟着类标识符和一个冒号。按照惯例，类名大写字母开头。提供类简短描述的文档字符串通常位于类定义之后。这是一个类定义的示例：

```python
Class Furniture:
    #这是一个类定义的示例。
    pass
```

以下定义了一个接受对象的类：

```python
Class Members(obj):
    #我刚刚定义了一个接受对象的类。
    pass
```

当你使用关键字`class`创建一个新类时，Python 的响应方式是创建一个与类标识符同名的新类对象。这个新类对象包含了类的所有属性的定义。因此，你可以使用它来访问类的属性并实例化新对象。

为了说明，创建一个新类并将其命名为`myclass`：

```python
class myclass:
    “这是一个独立的类。”
    Y = 100

    def greet(self):
        print('welcome, guest!')
```

要访问`myclass`的属性：

```python
>>> myclass.y
100
```

要访问`myclass`的函数属性：

```python
>>> myclass.get
<function myclass.get at 0x03025d20>
```

要访问`myclass`的文档字符串（docstring）：

```python
>>> myclass.__doc__
'this is an independent class.'
```

### 类实例化

与类一起创建的类对象可以用于创建类的实例。创建一个新对象非常简单；你只需要使用像下面的语句将对象赋值给类：

```python
>>> object_a = myclass()
```

要访问对象的属性，你将使用对象名作为点`.`之前的前缀，并在点之后使用属性名。对象的属性可以是方法，也可以是数据属性。方法指的是类的函数。为了说明，你可以使用上面的`myclass`类定义，并基于它创建一个对象：

```python
obj = myclass()
```

`myclass.get`是`myclass()`的一个属性，是一个方法对象，因为它为所有从`myclass`创建的对象定义了一个函数。因此，`obj.get`是一个方法对象。

```python
>>> obj.get
<bound method myclass.get of <__main__.myclass object at 0x0328db90>>
```

在`myclass`函数定义中，你可能注意到单词`self`被用作参数。然而，在上面的示例中，调用方法`obj.get`时没有传递参数。这是因为当对象调用其方法时，对象本身会变成第一个参数。按照惯例，使用`self`来指该对象。如果有其他参数，你可以将它们放在`self`之后。

### `__init__`方法

`__init__`方法是一个特殊的类构造器方法，用于初始化它创建的对象。每当你创建一个该类的新实例时，Python 都会调用这个初始化方法。`__init__`方法至少接受一个参数`self`，用于标识每个对象。

### 示例

类`performers`：

```python
def __init__(self):
    pass
```

类`performers(object)`：

```python
class performers(object):
    def __init__(self, name, skills, salary):
        pass
```

该类定义表明，每当创建`performers`类的实例时，每个实例都将拥有通过`__init__`方法初始化的变量副本。

为了说明，你可以使用这些表达式实例化`performers`类的成员：

```python
mem_1 = performers("dolly", "singer", 5000.00)
mem_2 = performers("jayne", "dancer", 5000.00)
mem_3 = performers("lizah", "pole dancer", 4750.00)
```

使用`print()`函数查看初始化的变量与实例变量之间的连接：

```python
print(mem_1.name, mem_1.skills, mem_1.salary)
print(mem_2.name, mem_2.skills, mem_2.salary)
print(mem_3.name, mem_3.skills, mem_3.salary)
```

这是你将在屏幕上看到的内容：

```text
Dolly singer 5000.0
Jayne dancer 5000.0
Lizah pole dancer 4750.0
```

## 第 6 章：Python 列表基础

### 什么是列表？

列表是一个包含在方括号`[]`中并用逗号分隔的有序项序列。列表是可变的，这意味着其项的值及其索引位置都可以更改。

```python
list = [1, 2, 3, 4]
```

列表是 Python 中最重要的数据结构之一，它们是有序的。正如我们在上一节中看到的，列表可以通过索引访问（从 0 开始，-1 表示最后一个项）。

### 创建列表

要创建一个列表，只需在方括号中包含多个用逗号分隔的值：

```python
subjects = ["math", "physics", "chemistry", "biology"]
```

你是否注意到第二个列表中包含另一个列表吗？这种类型被称为嵌套列表，它可以包含多个列表。

```python
subjects = ["math", "physics", "chemistry", "biology"]
mylists = ["fruits", ["science", "art"]]

print(subjects)
print(mylists)
```

### 访问列表值

我们将使用方括号通过引用其位置来切片列表。

```python
subjects = ["math", "physics", "chemistry", "biology", "art"]

print(subjects[0:2])
print(subjects[2:])
print(subjects[-3:-1])
```

正如我们已经提到过，Python 列表是可变的，这意味着我们可以更新其内容和顺序。你可以使用赋值运算符（`=`）更新列表的单个或多个元素，将列表名和索引作为左操作符，将新值作为右操作符。

```python
subjects = ["math", "physics", "chemistry", "biology", "art"]

print("current list items:", subjects)

subjects[3] = "government"
subjects[1] = "french"
del subjects[-1]

print("new list items:", subjects)
```

当你运行练习 14 时，你会注意到`"government"`被添加到索引 3 以替换`"biology"`，而第二个项`"physics"`被替换为`"french"`。我们还使用了`del`语句删除了列表中的最后一个项。从列表中删除元素的替代方法是使用`remove()`方法，我们将在下面简要介绍。

### 使用内置函数和方法进行基础列表操作

我们对列表还可以执行许多操作，包括拼接（使用`+`合并）和迭代（使用星号`*`）。

#### 列表的更多操作

这个练习将通过将其应用于列表，帮助你强化对序列的知识。

```python
cont = ["asia", "africa", "america", "europe", "australia"]
oceans = ["pacific", "indian", "atlantic"]

print("length of list 1:", len(cont))

cont[2] = "north america"
cont.append("south america")

print("new length of list 1:", len(cont))
print("list 1 + list 2:", cont + oceans)

oceans.remove("indian")

print(oceans)
print("list 2 * 3:", oceans * 3)
print("are the 'ia' in either of the lists?", 'ia' in cont or oceans)
```





### 元组（Tuples）

元组与列表相似，创建它们非常简单；只需用逗号分隔值，这些值也可以包含在括号中。例如：`tup1 = ('chemistry', 'physics', 1998, 2000)`；`tup2 = (7, 8, 9)`；`tup3 = "x", "y", "z"`。

以下是元组的一些基本特征：

- 编写空元组使用两个括号——`tup1 = ()`。
- 即使元组包含单个值，也要包含逗号——`tup1 = (50,)`。
- 元组索引从 `0` 开始，也可以进行切片。
- 使用方括号访问元组中的值。
- 不可以更改或更新元组中的值。
- 不可以删除元组元素；但可以使用 `del` 删除整个元组。
- 可以使用所有的运算符。有一些内置的元组函数，如：
  - 比较不同的元素：`cmp(tuple1, tuple2)`
  - 查找元组的总长度：`len(tuple)`
  - 将列表转换为元组：`tuple(seq)`
  - 找到最大值：`max(tuple)`
  - 最小值：`min(tuple)`

### 什么是元组？

元组用于将任意数量的项目分组为一个单一的顺序复合值。列表用于长度未知或未固定的情况，而元组（因为它的顺序元素不能更改）则用于每个元素的位置对列表的使用至关重要的情况。

### 创建元组

在 Python 中创建元组对象的过程与创建任何其他类型的对象（如我们已经涵盖过的数字、字符串或列表）相同。只需放置用逗号分隔的值并将它们包含在括号中。

语法格式如下：

`元组标识符 = (item1, item2, item3, … , item-2, item-1)`

`元组标识符 = item1, item2, item3, … , item-2, item-1`

创建元组并非强制使用圆括号，正如我们在下方的练习 17 中所示。事实上，序列中任何用逗号分隔且不使用如方括号（用于标识列表）的标识符号的值集，默认都是元组。然而，良好的做法是始终将序列项包含在圆括号中。

### 创建元组

```python
1 weekdays = ("sun", "mon", "tue," "wed", "thu", "fri", "sat")

2 weekends = "sun", "mon"

3 years = (2017,) 4 decade = ()5

6 print(type(weekdays), type(weekends), type(years), type(decade,))
```

注意，当你创建一个包含单个元素的元组时，它必须有一个逗号，就像练习 17 中的 `years` 元组一样。你可以通过识别一对不包含任何内容的圆括号来创建一个空元组，正如我们在上一个练习中创建 `decade` 元组一样。

### 访问元组值

与字符串和列表一样，元组的值是顺序排列的，并且可以通过从 `0`（第一个项目）到 `-1`（最后一个项目）的索引来访问。我们使用方括号 `[]` 进行切片，并以与列表相同的方式操作元组。

在下一个练习中，你将学习像处理字符串和列表一样访问和操作元组数据类型的元素。

### 访问元组的值

```python
1 weekdays = ("sun", "mon", "tue," "wed", "thu", "fri", "sat")

2 print(weekdays)

4 print("first day of weekdays", weekdays[0])

5 print("items [2:]", weekdays[2:])

6 print("what is item [-1]?", weekdays[-1])

7 print("print from second last items:", weekdays[:-2])
```

你可以从练习 23 中看到，我们通过字符串引入的索引系统仍然用于元组。记住，第一个项目的位置是 `0` 而不是 `1`，访问项目 `[0:3]` 意味着从第一个（包含）到第四个（不包含）的项。例如，将访问元组的第 `0`、`1` 和 `2` 项。

### 更新元组值

我们已经学过元组是一个不可变的数据类型，这意味着它的值不能被更改、更新或删除。然而，如果你需要更改元组的值，你将不得不从现有元组中提取所需的项目部分，并创建一个新的。让我们在练习 24 中尝试一下。

### 从现有元组的值创建新元组对象

```python
1 tuple1 = (2002, 2006, 2010, 2014)

2 tuple2 = ("brazil", "italy", "spain", "germany")

4 # tuple1[0] = 2000  # 此语句将产生错误。

6 tuple3 = tuple1 + tuple2

7 print(tuple3)
```

上面的练习 24 展示了你如何组合两个元组的值创建一个新的元组。脚本的第 4 行被注释掉了。尽管如此，如果你取消注释并重新运行，你将得到一个类型错误：`'tuple'` 对象不支持赋值。练习像我们在此练习中所做，从特定的值索引创建新元组，而不是整个元组。

### 使用内置函数的基本元组操作

Python 自带了一些元组函数和方法，你应该在练习中发现它们。你可以使用加运算符 `+` 来连接元组，并使用星号 `*` 进行迭代，就像字符串和列表一样，这种操作的结果是一个元组，而不是字符串。下面的表格总结了它们是什么以及如何使用。

### 基本元组操作

你可以尝试这些操作来理解它们是如何工作的。

![Image0021](img/imagesImage0021.jpg)

## 第 8 章：类（classes）

### Python 类和对象

Python 是一种面向对象的编程语言。这意味着 Python 程序员可以利用类等面向对象的特性。

类可以定义为数据和操作这些数据的方法的组合。这意味着类具有数据和方法，对方法的访问是通过使用点符号完成的。

### 类定义

在 Python 中定义类，我们使用 `class` 关键字。后面应该跟着一个冒号。

```python
testclass():
```

一旦定义了类，你就可以在里面创建方法和函数。这些有助于数据操作。

```python
#!/usr/bin/python3

class pythonmaths:

    def add(ax, bx):

        addition = ax + bx

        print(addition)

    def subtract(ax, bx):

        subt = ax - bx

        print(subt)

    def multiply(ax, bx):

        multiplication = ax * bx

        print(multiplication)

    def division(ax, bx):

        div = ax / bx

        print(div)
```

我们定义了一个类名 `pythonmaths`。类可以有一些方法。要访问类的任何方法，你必须使用类名、点 `.` 和方法名。

要访问上述 `pythonmaths` 类中的 `add` 方法，在 Python 终端输入以下内容：

```python
Pythonmaths.add(2, 3)
```

注意类名在前，后面是方法名，然后是括号内的参数。函数期望两个参数值，即参数 `ax` 和 `bx` 的值。如果你传递了两个两个参数的值甚至一个参数的值，将返回错误。

注意类中的所有内容都缩进了。这应该是总是这样的。如果没有，将会生成错误消息。

类的方法（class methods）也可以从类内部被调用。这意味着我们需要创建一个类的实例，并用于访问这些类方法。示例：

```python
#!/usr/bin/python3

class class2():

    def firstmethod(self):

        print("the first method")

    def secondmethod(self, astring):

        print("second method, string alongside:" + astring)

    def main():

        # 实例化类并调用方法

        C = class2()

        C.firstmethod()

        C.secondmethod(" we are now testing")

if __name__ == "__main__":

    main()
```

代码执行时会打印以下内容：

![Image00022.jpg](img/Image00022.jpeg)

`self` 参数通常指的是对象本身。这就是为什么我们使用 `self` 这个词，它是 Python 中的一个关键字。当在方法内部使用时，`self` 指向被操作的对象的特定实例。每当你在 Python 中看到 `self` 关键字时，就知道它指的是实例方法的第一个参数。它被用于访问成员对象。然而，你会注意到在调用我们代码中的两个方法 `firstmethod()` 和 `secondmethod()` 时，我们从未指定过 `self` 关键字，因为 Python 会替我们完成这一点。在调用实例方法后，Python 知道如何自动传递 `self` 参数，无论它是否被提供。这意味着你可以选择提供或不提供。我们创建了 `class2` 类的实例，并命名为 `C`。这是通过以下行完成的：

```python
C = class2()
```

`C` 是 `class2` 类的一个对象。这意味着我们可以使用该对象来访问类的所有的方法和属性。你只需要关注非 `self` 参数（non-self-arguments）即可。注意 `secondmethod` 中是如何将字符串追加到初始文本的。

### 内置属性

某些内置属性被所有类保留，为了访问它们，我们使用与其他属性类似的点运算符（`.`）。这些包括：

- `__dict__`：这是一个包含类命名空间的字典。
- `__doc__`：类的文档字符串，如果未定义则为 `None`。
- `__name__`：类的名称。
- `__module__`：定义类所在的模块名称。在交互模式下，该属性变为 `__main__`。
- `__bases__`：这是一个元组（tuple），可能为空，按照类在类中出现的顺序包含了父类。示例：

```python
#!/usr/bin/python3

class worker:

    '所有实例通用的基类'

    count = 0

    def __init__(self, name, age):

        self.name = name

        self.age = age

        worker.count += 1

    def showcount(self):

        print("total workers %d" % worker.count)

    def showworker(self):

        print("name : ", self.name, ", age: ", self.age,)

worker1 = worker("gish", 26)

worker2 = worker("ether", 24)

print(worker1.__doc__, worker2.__doc__)

print(worker1.__name__, worker2.__name__)

print(worker1.__module__, worker2.__module__)

print(worker1.__bases__, worker2.__bases__)

print(worker1.__dict__, worker2.__dict__)
```

代码打印以下内容：

![Image0023.jpg](img/Image0023.jpeg)

### 垃圾收集

有时内存可能会被不再定义的对象占用。Python 会自动从内存中清理，这一过程被称为垃圾收集（garbage collection）。通过这种方式 Python 可以回收不再使用的内存块。垃圾回收器在程序执行时启动，并在一个对象的引用计数（reference count）达到零时运行。对象的引用计数会随着指向它的别名数量的变化而变化。当分配一个新名称或将其添加到元组（tuple）、列表（list）或字典等容器时，对象的引用计数会增加。一旦使用 `del` 语句删除对象，计数值将减少，或者当其引用超出作用域，或者当引用被重新赋值时。示例：

```python
Ax = 5  # 创建对象

Bx = Ax  # 增加 <5> 的引用计数

Bz = [Bx]  # 增加 <5> 的引用计数

del Ax  # 减少 <5> 的引用计数

Bx = 70  # 减少 <5> 的引用计数

Bz[0] = -1  # 减少 <5> 的引用计数
```

人们无法察觉垃圾回收器何时销毁了一个孤立的实例。然而在 Python 中，类可以实现一个名为 `__del__()` 的析构方法，它会在特定对象即将被销毁时被调用。任何未被实例使用的非内存资源都可以通过此方法进行清理。`__del__()` 析构方法通常显示即将销毁的实例的类名。示例：

```python
#!/usr/bin/python3

class region:

    def __init__(self, ax=0, bx=0):

        self.ax = ax

        self.bx = bx

    def __del__(self):

        class_name = self.__class__.__name__

        print(class_name, "already destroyed")

rg1 = region()

rg2 = rg1

rg3 = rg1

print(id(rg1), id(rg2), id(rg3))  # 打印 id

del rg1

del rg2

del rg3
```

代码打印：

![Image0024.jpg](img/Image0024.jpeg)

### 继承

允许你在不同的文件中创建类。你可以使用 `import` 语句将它们导入到主程序中。假设上面的代码创建在 `region.py` 文件中并带有属性，我们可以这样做：

```python
#!/usr/bin/python3

import region

rg1 = region.region()
```

继承让你不需要从头创建类，而是可以从父类继承。由于父类拥有某些属性，子类允许使用它们。子类还可以覆盖（override）父类的方法。继承采用以下语法：示例：

```python
#!/usr/bin/python3

### 关于类操作示例

class parentclass():

    def firstmethod(self):

        print("the first method in parentclass")

    def secondmethod(self, astring):

        print("we are testing" + astring)

class childclass(parentclass):

    # 覆盖 firstmethod

    def firstmethod(self):

        parentclass.firstmethod(self)

    def secondmethod(self):

        print("childclass secondmethod")

def main():

        # 测试类方法

        C = childclass()

        C.firstmethod()

        C.secondmethod()

if __name__ == "__main__":

    main()
```

代码打印：

![Image00025.jpg](img/Image00025.jpeg)

在 `childclass` 中我们没有定义 `firstmethod`，但我们从父类获取了它。这就是 Python 中工作的方式。子类从父类继承了一个方法。另一个示例：

```python
#!/usr/bin/python3

### 关于工作类的示例

class worker:

    '所有工人通用的基类'

    count = 0

    def __init__(self, name, age):

        self.name = name

        self.age = age

        worker.count += 1

    def showcount(self):

        print("total workers %d" % worker.count)

    def showworker(self):

        print("name : ", self.name, ", age: ", self.age)

worker1 = worker("bosco", 2500)

worker2 = worker("june", 3000)

worker1.showworker()

worker2.showworker()
```

```python
Print("total workers %d" % worker.work, worker.count)
```




上述代码清晰地演示了如何创建一个类的实例，并使用它来访问父类的成员或方法。执行后，它将得到以下结果：

![Image00026.jpg](img/Image00026.jpeg)

我们创建了`worker`类的两个实例，即`worker1`和`worker2`。这些实例每一个都是`worker`，第一个是`bosco`，第二个是`june`。我们使用这些实例来访问类中定义的`showworker`方法。该方法返回`worker`的名称和工资。

## 多重继承

在`python`中，一个可以同时继承多个类。这在`java`和`c#`等其他语言中是不行的。`python`的多重继承采用以下语法：

```python
Class childclass(parentclass1, parentclass2, …):

    # 初始化函数

    # 方法
```

### python 多重继承示例：

```python
#!usr/bin/python3

Class parentclass1():

    Def supermethod1(self):

        Print(“calling supermethod1”)

Class parentclass2():

    Def supermethod2(self):

        Print(“calling supermethod2”)

Class childclass(parentclass1, parentclass2):

    Def childmethod(self):

        Print(“the child method”)

Ch = childclass()

Ch.supermethod1()

Ch.supermethod2()
```

代码将打印：

![Image00027.jpg](img/Image00027.jpeg)

我们定义了两个方法，一个在第一个父类中，另一个在第二个父类中。子类继承了这两个类。它访问了在这两个类中定义的方法。这就是我们如何在`python`中继承多个类的方法。

## Python 构造函数

构造函数是指一种类函数，用于实例化对象并赋予某些预定义的值。它应该以双下划线（`__`）开头。它是`__init__()`方法。示例：

```python
#!usr/bin/python3

Class worker:

    workername = “”

    Def __init__(self, workername):

        self.workername = workername

    Def sayhello(self):

        Print(“welcome to our company, " + self.workername,)

Worker1 = worker(“june,”)

Worker1.sayhello()
```

代码执行时将打印以下内容：

![Image00028.jpg](img/Image00028.jpeg)

我们所做的是使用构造函数来获取用户名。

## 重写类方法

在编写`python`代码时，我们允许重写父类中定义的方法。你可能在子类中需要不同的功能，这就是重写父方法的良好理由。要重写该方法，我们只需要向它传递不同的参数，如下所示：

```python
#!usr/bin/python3

Class parentclass: # 定义父类

    Def firstmethod(self):

        Print (‘a call to parent method’)

Class childclass(parentclass): # 定义子类

    Def firstmethod(self):

        Print (‘a call to child method’)

C = childclass() # 子类的实例

C.firstmethod() # 子类调用被重写的方法
```

代码执行后将打印以下内容：

![Image00029.jpg](img/Image00029.jpeg)

方法名`firstmethod`已经在父类中定义。该函数在子类中定义，但这次打印的内容与在父类中打印的内容不同。我们实现了方法重写。

### 示例 2：

```python
#!usrbin/python3

Class ab():

    Def __init__(self):

        self.ax = 2

    Def method1(self):

        Print(“method1 from class”)

Class bc(ab):

    Def __init__(self):

        self.bx = 2

    Def method1(self):

        Print(“method1 from class”)

Bc = bc()
```

![Image0030.jpg](img/Image0030.jpeg)

`Bc.method1()`

代码执行后将打印以下内容：

重写类是基于之前的类（也称为父类或超类）创建的新类。如果你没有跟上，请不要担心。这是`python`的高级用法，仅供教学目的演示。重写类的输出与普通类相似。不同之处在于：在定义父类的函数中创建了另一个类（例如`c2 =`），将返回父类并返回重写类的信息。请遵循下方的练习示例（在`aptana studio 3`中完成），并思考过程以理解上述状态。

输入代码：

![Image0031.jpg](img/Image0031.jpeg)

返回的输出：

![Image0032.jpg](img/Image0032.jpeg)

### 创建新类

```python
Class newclass:

    """这是我们的第一个类。它的作用

    是显示字符串文本和变量名的值,"""

    Name = str(input(“输入你的名字,: “))

    Def greeting(name):

        Print (“hello”, name,)

    Print (newclass.name,)

    Print (newclass.greeting)
```

当你运行脚本 61 时，控制台会显示什么？

### 创建对象

到为止，我们学习了如何使用类名访问类的不同属性。我们还可以使用这些对象来实例化该类，这非常类似于调用函数。

```python
object = newclass()
```

在上面的示例中，创建了一个名为`object`的新对象。该对象可以使用类名前缀来访问`newclass`的属性。在这种情况下，属性可能包括方法和变量。对象的方法是类的对应函数，这意味着类定义对象的方法。例如，因为`newclass.greeting`是函数对象且`newclass`的属性，`object.greeting`将是一个方法对象。

### 构造函数

在`python`中，`__init__()`函数是特殊的，因为它在实例化新对象时被调用。该对象也被称为构造函数，因为它用于初始化所有变量。

```python
object.greeting() # class complexnumbers:

    Def __init__(self, x = 0, y = 0):

        self.real = x

        self.imagined = y

    Def getnumbers(self):

        Print (“复数是,: {0}+{1}j”.format(self.real, self.imagined))

object1 = complexnumbers(2, 3) # 创建一个新的 complexnumbers 对象

object1.getnumbers() # 调用 getnumbers() 函数

object2 = complexnumbers(10) # 创建另一个 complexnumbers 对象

object2.attr = 20 # 创建新属性 ‘attr’

Print ((object2.real, object2.imagined, object2.attr))

object1.attr # 生成错误，因为 c1 对象没有属性 ‘attr’
```

在上面的练习中，我们定义了一个表示复数的数类。我们定义了两个函数：`__init__()`函数初始化变量，`getnumbers()`函数用于正确显示数字。注意，练习对象的属性是动态创建的。

### 删除属性和对象

你可以使用`del`语句随时删除对象的属性，甚至删除对象本身。

```python
object,object2 = complexnumbers(10) # creates another complexnumbers object

object2.attr = 20 # creates a new attribute ‘attr’

Print((object2.real, object2.imaginary, object2.attr))

del complexnumbers.getnumbers()

object1.getnumbers()
```

当你在练习_64中运行脚本时得到的错误表明属性`getnumbers()`已删除。但请注意，由于在创建对象的新实例时内存中会创建一个新实例，即使对象被删除，它可能继续存在于内存中，直到垃圾回收器自动销毁未引用的对象。

# 第 9 章：流程控制

## 流程控制

循环是一种程序控制结构，它有助于复杂的执行路径以及对语句或一系列语句的重复处理。

## for 循环

`for`循环用于迭代顺序数据类型（如字符串、列表或元组）中的项。

**语法：**

```
For val in sequence:

    Statement(s)
```

在“for循环”中，变量在每次迭代中持有序列中项的值。循环将一直进行，直到所有项都被处理。

**示例：**

**遍历字符串的 for 循环：**

```python
For letter in ‘programming’: # iterate over a string

    Print('<<*', letter, '*>>’)
```

如果你运行上面的代码，输出如下：

```
<<* p *>>

<<* r *>>

<<* o *>>

<<* g *>>

<<* r *>>

<<* a *>>

<<* m *>>

<<* m *>>

<<* i *>>

<<* n *>>

<<* g *>>
```

注意，当“for循环”到达字符串中的最后一个字母时，打印结束。

**遍历列表的 for 循环：**

```python
### iterate over a list

Dogs = ['rottweiler’, ‘pug’, ‘bulldog’, ‘beagle’, ‘poodle,’]

For name, in dogs:

    Print('happy dog :', name,)

    Print("lovely dogs!")
```

这是运行程序时的输出：

```
Happy dog : rottweiler

Happy dog : pug

Happy dog : bulldog

Happy dog : beagle,

Happy dog : poodle,

Lovely dogs!
```

### 在 for 循环中使用`range()`函数

`range()`函数是一个内置函数，可以与“for循环”配合使用以获取所需的数字。例如，如果你需要 1 以及从 1 到 10 的所有数字，你可以用此程序创建一个“for循环”

```python
x = 10

Total = 0

For num in range(1, x+1):

    Total = total + num

Print("sum of 1 up to %d: %d” % (x, total))
```

你的输出将是：

`Sum of 1 up to 10: 55`

## while 循环

当测试表达式为真且需要重复执行语句或一组语句时，使用“while循环”。当它不再为真时，控制传递到循环后的行。

**语法：**

```
While condition:

    Statement(s)
```

**示例：**

```python
#program adds number up to a number

#specified by the user

#total = 1+2+3+4…+number

Num = int(input(“enter a number: “))

#initialize total and counter

Total = 0

Y = 1

While y <= num:

    Total = total + y

    Y = y+1 #update counter

#print the total

Print(“the total is: “, total)
```

Enter a number: 3
`The total is: 6 #1+2+3`

Enter a number: 7
`The total is: 28 #1+2+3+4+5+7`

### break 语句

`break`语句终止循环并将控制传递到循环后的第一个语句。它通常用于需要快速退出的情况。

**语法：**

```
Break
```

**示例：**

```python
#loop ends once a specified color is reached

Colors = [blue,” “pink”, “red”, “green”, “yellow”]

For x in colors:

    If x == ‘green’:

        Break

    Print('color :', x)

    Print(“amazing loop!”)
```

运行程序查看结果：

```
color : blue

color : pink

color : red

amazing loop!
```

注意，当到达颜色‘green’时，它跳过了打印语句并打印了列表中的下一个项。

### continue 语句

`continue`语句跳过当前迭代中的语句并将控制传递到下一次迭代。

**语法：**

```
Continue
```

为了说明，你可以将上述示例中的`break`语句替换为`continue`语句。

```python
Colors = [blue,” “pink”, “red”, “green”, “yellow”]

For x in colors:

    If x == ‘green’:

        Continue

    Print('color :', x)

    Print(“amazing loop!”)
```

运行程序时，输出如下：

```
color : blue

color : pink

color : red

color : yellow

amazing loop!
```

注意，当到达颜色‘green’时，它跳过了打印语句并打印了列表中的下一个项。

### pass 语句

`pass`是 Python 中的空操作。解释器读取`pass`语句但不执行任何操作。它通常用作语法要求语句时的占位符。这允许他们在测试完整语句的同时避免完整语句产生错误消息。

**语法：**

```
Pass
```

# 第 10 章：python 字典

字典（或简称`dict`）虽然也包含顺序数据，但它是一种以键作为值的映射键的关联数组类型。它包含的数据可能是顺序的，但它们并不是排序的。

字典的元素是可变的，可以是任何其他数据类型。每个元素都由冒号（`:`）匹配的键:值对组成，就像列表和元组一样，用逗号分隔。字典的语法是一个由花括号`{}`包围的一个或多个元素组成的标识对象。

语法采用此格式：

```
Mdict = {key1:value1, key2:value2, key3:value3}
```

与列表类似，字典是可变的，可以包含混合内容，包括元组（假设所有值都是相同类型）、列表、字符串、整数等。

键值对模型的作用在于存储在字典中的每个键都是唯一的。实际上，字典设计用于存储唯一项或属性列表。

给定以下内容是正确的：

- 在添加或创建字典时，所有条目必须是键:值对格式。如果缺少键或值，将抛出异常。
- 如果向字典添加键:值对且该键已存在，则将丢弃旧的键值并使用新条目。
- 只有在提供键时才能更新值。
- 列表不能用作键。

这里是一些常用的字典操作：

**创建一个空字典：**

```python
x={}
```

**创建一个字典：**

```python
x=dict(name=’john’, age=35, height=6)

print(x)
```

**测试键是否存在：**

```python
if ‘age,’ in x.keys():

    Print('found it！)
```

**获取键的值：**

```python
y=x[‘height’]

print(‘height = ' + str(y))
```

**列出所有键：**

```python
For y in x.keys():

    Print(y)
```

**打印键和值：**

```python
For y in x.keys():

    V=x[y]

    If type(v)!=‘str’:

        V=str(v)

    Print(y + ‘=’ + v)
```

**更新键的值：**

```python
x[‘age,’]=40

print(x)
```

**删除键:值对：**

```python
del(x[‘height’])

print(x)
```



**添加键:值对：**

```python
x['height'] = 6
print(x)
```

**将所有键或值转为列表：**

```python
list(x.keys())  # keys as a list
# ['name', 'age', 'height']

list(x.values())  # values as a list
# ['john', 40, 6]
```

## 创建字典

在 Python 中创建字典对象最流行的方法是像我们在书中创建其他对象类型一样，为一个空字典对象命名。一旦创建了字典，你就可以根据需要添加键值对。

### 创建字典并向其添加键值对

```python
1 mydict = {}
2
3 mydict["name"] = "jane"
4 mydict["age"] = 21
5 mydict["city"] = "london"
6 mydict["hobbies"] = "cycling", "coding", "cooking", "gaming"
7
8 print(mydict)
```

在本次练习中，我们在脚本的第一行创建了一个名为`mydict`的空字典。从第三行到第六行，我们向该空字典添加了键值对，最后在末尾打印了字典`mydict`的内容。

创建字典的另一种方法是像练习 27 那样，为命名的字典对象赋值键值对。

### 通过赋值键值对创建字典

```python
1 mydict = {"name": "jane", "age": 21, "gender": "f", "city": "london"}
2
3 print(mydict)
```

你会注意到，键值对输入字典的顺序并不重要，因为它们是通过键而不是索引来访问的，它们总是以不同的顺序被打印出来。

创建字典时必须遵守的一条规则是：键必须是唯一的，但值不需要唯一。键是不可变的，而值可能是可变的数据类型，如字符串、数字或列表。

### 访问字典键值对

字典数据不是排序的；因此，可以像我们处理字符串、列表和元组那样，无需索引即可独立访问。字典是一种复合对象类型，不能进行切片或索引操作。

Python 使用复杂的算法来映射字典的键。这种过程被称为哈希（hashing），它使得访问、检索和更新字典键值对的速度比其他顺序对象类型快得多。

键用于访问字典的键值对。下一个练习将演示我们如何访问字典的值。

### 访问字典键值对

```python
1 weather = {"mon": "cloudy", "tue": "sunny", "wed": "rainy"}
2
3 print(weather["wed"])
```

如果你尝试访问不存在的键的键值对，你将遇到错误`KeyError: [key]`。

### 更新字典

你可以向字典添加新的键值对，并修改或删除现有条目的值，正如下一个练习所示。

### 更新字典

```python
1 weather = {"mon": "cloudy", "tue": "sunny", "wed": "rainy"}
2
3 weather["thu"] = "hot"
4 weather["wed"] = "gloomy"
5 del weather["mon"]
6
7 print(weather["wed"])
```

在本次练习中，我们创建了一个名为`weather`的字典，包含日期:天气类型的键值对，如你所见。在第 3 行，我们添加了一个新的键值对；在第 4 行，我们更新了`"wed"`键的值；在第 5 行，我们删除了`"mon"`键值对。你的脚本运行正常吗？

`del`语句用于显式删除字典中的单个项目；要删除整个字典，也可以使用它。

### 使用内置函数和方法进行基础字典操作

你下一个练习中的表格总结了在此阶段你对 Python 字典可以执行的重要操作。你会发现，我们已经遇到过之前涵盖的大多数对象类型。永远不要试图理解所有的字典操作，只需理解每个操作是如何应用的。

#### 字典函数和方法

```python
1 jane_doe = {"id": 7234, "height": "5.5", "weight": "212"}
2 johnoe = {"id": 2932, "height": "6.0", "weight": "190"}
```

![Image0033.jpg](img/Image0033.jpeg)

## 第 11 章：编写你的代码

### 练习 1：字典演示

```python
Color = {0: "red", 1: "yellow", 2: "green", 3: "white"}
V = color.values()
For c in v:
    print(c)
```

输出：
Red
Yellow
Green
White

解释：
`color={0: "red", 1: "yellow", 2: "green", 3: "white"}`是一个字典。
`open("tryfile.txt", "w")`以`"w"`模式打开`tryfile.txt`。
`"w"`模式以写入模式打开文件。
`F.write("i am learning python programming!")`将指定的文本写入文件对象`f`。
`F=open("tryfile.txt", "r")`以`"r"`模式打开`tryfile.txt`。
`F.read()`读取文件对象`f`中的数据。

### 练习 2：isalpha() 演示

```python
Name = raw_input("please enter your last name: ")
isalpha = name.isalpha()
if is:
    print("ok! valid last name!")
else:
    print("no good! invalid last name!")
```

输出（假设输入为`"swift"`）：
please enter your last name: swift
Ok! valid last name!

解释：
如果所有字符都是字母，`isalpha()`返回 true。如果用户输入数字或符号，`isalpha()`将返回 false。在这里，用户输入了`"swift"`，`isalpha()`返回 true。

### 练习 3：写入与读取文件

```python
F = open("tryfile.txt", "w")
F.write("i am learning python programming!")
F.close()

F = open("tryfile.txt", "r")
print(f.read())
F.close()
```

输出：
am learning python programming!

解释：
`open("tryfile.txt", "w")`以`"w"`模式打开`tryfile.txt`。
`"w"`模式以写入模式打开文件。
`F.write("i am learning python programming!")`将指定的文本写入文件对象`f`。
`F=open("tryfile.txt", "r")`以`"r"`模式打开`tryfile.txt`。
`F.read()`读取文件对象`f`中的数据。

### 练习 4：导入模块演示

```python
### program001.py
def red():
    print("this flower is red")

def yellow():
    print("this flower is yellow")

def green():
    print("this flower is green")
```

将文件保存为`program001.py`，应与以下运行文件位于同一目录下。

```python
### program002.py
import program001

program001.red()
program001.yellow()
program001.green()
```

输出：
this flower is red
this flower is yellow
this flower is green

### 练习 5：类与对象

```python
class flower:
    def __init__(self, name, color):
        self.name = name
        self.color = color

f = flower("rose", "red")
print("the flower name is " + f.name)
print("the flower color is " + f.color)
```



```text我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。输出：
the flower name is rose
the flower color is red
```

## 解释

`class flower` 创建了一个名为 `flower` 的类。

`def __init__(self,)` 定义了一个构造函数。

构造函数用于初始化变量。

`self` 是一个变量，指的是当前对象 `f`。

## 结

本书旨在帮助初级程序员学习 Python。通过这本书，你应该能够编写基础程序，甚至是编写包含多个对象的更复杂的程序。

对于希望在面向对象编程方面打下良好基础，并向 Python 编程的中级和高级主题进的初学者来说，本书是完美的跳板。考虑到你已经走过的这段路，你正处于成为 Python 编程专家的正确道路上——无论你是为了提升职业生涯，还是为了成为一名精通编程的爱好者。

我希望这本书能够帮助你快速、轻松地学习 Python 编程的基础知识，并激发你创造有意义的程序和实际应用程序。

下一步是通过参加 Python 编程的高级课程将你的学习提升到水平，并掌握开发更大、更复杂且实用的程序所需的技能，从而利用这种编程语言的许多强大特性。

祝你好运！

# 第 2 本书：Python 数据科学

面向自学者的 Python 编程全面指南

Vera Poe

## 引言

本书的目的是教你数据科学的过程，同时为你提供支持你学习过程的所有基础技能和工具。本书 intended 针对寻找简单方法理解数据科学基础的完全初学者。

由于对编程和数学知识的要求，使用 Python 学习数据科学有时可能会令人敬畏。

结果往往难以交流，因为它们可能是一长串数字，初学者很难理解。你将学习一些基础工具，这些工具可以帮助你创建交互式图表，让你能够与他人分享结果。

请记住，为了从书中获得最大的收益，你应该完成每个章节中展示示例。如果你在理解某些示例时遇到困难，请逐行拆解，并缓慢推进直到你理解这些概念。每一章都将教你所需的工具，教你如何安装它们，并提供足够的信息以便你也能独立操作。务必练习你读过的所有内容，因为没有实践性工作，你将无法完全理解理论。

在数据科学方面，我们有很多选项可以处理，几乎所有的企业都能够处理这种过程并从中获得益处。如果你想更多地了解你的客户以及他们对你和你的业务期待什么，那么数据科学过程将是帮助你的最佳选择。

为了开始本指南，我们将看看数据科学到底是什么，它为什么重要，以及为什么我们最初想要处理这个过程。然后，我们将花一些时间学习数据科学的生命周期，以及我们如何通过一系列步骤，如寻找正确的数据、准备数据、建立正确的模型等。

然后，我们将花时间查看 Python 语言自带的基础知识，以及我们如何利用它来帮助我们的数据科学项目。在数据科学方面，有很多很棒的编程语言可以使用，但也有很多很的库可以帮助我们完成数据科学项目。我们还将花时间查看一些处理数据时的库，包括 `numpy`、`seaborn` 和 `matplotlib`。

这只是我们在数据科学方面可以做的一些事情的开始。我们还将花时间看看机器学习到底是什么，以及我们如何利用它来发现模式。许多行业都会涉及此，你会发现随之而来的许多好处。当你准备好处理数据科学时，请务必查看本指南以开始。

## 第 1 章：什么是数据科学

### 什么是数据科学？

数据科学是你至少听过一次的术语。如果你正在经营公司，并需要查看可以采取的步骤来提高效率并降低风险，你可能会关注数据科学。但这并不能解释很多我们可以用它做什么。这正是本书派上用场的地方。

随着世界开始产生大数据，使用这些数据的存储需求变成了一个问题。直到几年前，这都是行业中发生的主要挑战和关注之一。

现在，得益于我们拥有的技术某些变化，这不再是一个大问题。这意味着我们可以进行一些调整，并在过程中处理更多的数据。你会发现，将这一切结合起来并帮助我们从所有数据中发现模式的“秘密配方”就是数据科学。

许多公司正寻求进入数据科学领域，因为它们知道随之带来的所有好处。当你准备好处理数据科学时，请务必查看本指南以开始。

当我们在这里开展工作时，首先需要考虑的是为什么数据科学如此重要，以及为什么公司在过程中可能需要与数据科学流程合作。

第一个问题是这些数据在现代世界中的组织方式，特别是将其与过去的方式相比时。传统上，公司能够获取的数据规模通常较小，而且在整个过程中都是结构化的。这使得我们能够使用简单的业务智能工具来分析正在发生的情况。

然而，情况已不再如此。诚然，这同时也带来了一些优点和负面影响。它让我们有机会更深入地了解现状，因为我们可以收集数据并通过更多数据获得更深层次的理解。但通常，这些数据是非结构化的，这使得分类和理解它们也变得更加困难。

与传统系统中发现的某些数据（即我们今天结构化且易于处理的数据）不同，我们会发现绝大多数数据是非结构化的，或者至少是半结构化的。这会让处理变得更加困难，并花费更长的时间。但因为我们可以找到更多信息来帮助做出决策，所以这并不一定总是一件坏事。

这些数据将产生许多不同的来源，包括仪器、传感器、多媒体形式、文本文件，甚至是过程中的某些财务日志。由于我们从所有这些来源获取数据，至关重要的一点是我们无法使用某些简单的业务智能工具，因为它们无法处理所有数据。这就是为什么开展数据科学、使用更先进且复杂的算法和分析工具至关重要。这确保了我们能够真正从数据中分析并处理出有意义的见解。

根据汽车可以收集的数据，它可以在数据科学和先进机器学习算法的帮助下做出决策，帮助它决定何时加速、何时减速，甚至何处转弯。

我们甚至可以利用数据科学的概念来帮助预测分析。例如，我们可以开展天气预报等方面的工作。来自卫星、雷达、飞机、船只等设备的数据可以被分析，以帮助我们建立某些模型。当我们能够预测天气的同时，还能预测我们想要的任何自然灾害的发生时，这些模型将非常有用。它还能帮助我们在发现这些情况时提前采取正确的措施，并在此过程中帮助我们拯救许多生命。

### 我该如何使用数据科学？

![Image00034.jpg](img/Image00034.jpeg)

当我们涉及到数据科学时，最初的问题之一就是如何使用它。学习它看起来像是一件美妙的事，似乎我们可以为了好玩而使用它，但无论你处于什么行业或计划如何使用它，使用数据科学都会带来许多实际用途。我们依赖数据科学的不同方式包括：

它可以帮助营销。营销完全关乎数据，当我们能够利用所有生成的数据时，我们会发现自己可以更深入地了解如何在正确的地方触达客户。公司有不同的方式利用数据科学来保持领先，并且它可以帮助将客户置于合适的位置。

这有助于公司学习更多。算法处理数据的次数越多，它在识别客户需求方面的表现就越得好。通过设置应用程序需要满足的几个不同标准，系统可以过滤掉一些。如果应用程序符合某些要求，它将是一个很好的考虑对象。贷款员将收到这些申请并对其做出最终判定。但如果贷款申请不符合要求，它将被忽略且完全不会看到。这有助于加速贷款申请流程，并让贷款员有机会跟上工作进度。

这也是数据科学大显身手的地方。通过许多不同的因素（例如对过去的交易进行训练），识别交易是否为欺诈变得更容易。如果金融机构在处理数据时不小心，欺诈可能会给他们带来巨大的财务损失。使用数据科学来打击欺诈每年可以为他们节省数百万美元。

它以多种方式为医疗领域提供帮助。数据科学流程可以通过许多方式帮助到医疗领域。首先，我们可以看到数据科学将帮助医生完成他们的手术。通过使用数据科学自带的机器学习和其他算法，医生将能够做出准确的切口，以最少的问题完成手术，并缩短康复时间。

此外，这些算法将帮助医生对患者进行预后。考虑到医生们日益繁重的工作量以及与每位患者交流的时间有限，拥有这些工具将大有益处。他们可以利用数据科学查看现有的图像（如扫描图和 X 光射线），然后迅速获得诊断。

最后，在涉及医疗领域的行政任务时，我们甚至可以找到数据科学的应用。这些机器可以与客户交流，询问几个问题，并判断患者问题的严重程度，并将他们引导至正确的地点。对于那些人手短缺无法处理某些患者需求的领域，这非常有帮助。

它能帮助公司更多地了解其目前的竞争对手和所在的行业。如果你想击败目前的某些竞争对手，你就需要尽可能多获取关于行业和竞争对手的信息。你需要观察他们在做什么、客户如何反应，以及你如何利用这些来取得优势。

当你掌握了所有这些信息后，你会发现更容易看出哪些做法是有效的，哪些是无效的。然后你可以直接投入并对业务模型进行必要的调整。你可能会发现一种其他人尚未使用的触达客户的新方法。你可能对他人正在使用的某种技术进行改进，从而改进你自己的业务。

制造业公司将与数据科学合作，因为它允许他们做出可以节省资金的预测。首先，你可以使用这类算法来确定机器上的某个部件何时可能损坏，或者你何时需要维护。然后你可以将这些工作安排在非工作时间进行，确保机器始终准时运行，并且在你们解决问题期间生产不会中断。

![Image00035.jpg](img/Image00035.jpeg)

当需要寻找减少现有浪费的方法时，这些算法也适用于几乎任何业务。每家公司都会某种程度的浪费，弄清楚如何减少和处理这些浪费将使你能够以竞争性的价格提供产品，同时尽可能获得利润。这只需要通过数据科学找出这些浪费产生的地方，以及你如何将它们降到最低。

当你在在线购物并看到网站上有推荐标签页时，我们正看到数据科学和机器学习走进现实。这些功能在许多网站上非常流行，因为它们可以帮助客户更容易对下一个想看什么、想买什么或其他内容做出明智的决策；而企业也会喜欢它们，因为有了这些推荐系统，客户更有可能再次购买，从而增加该公司的底线。

列表上的下一项是语音识别过程。如果你曾对你的智能手机说话并提问，或者使用过像 Cortana 这样流行的设备，你就能看出这个功能是多么有趣，而且它是根据数据科学的一些原理运行的。

事实上，我们在数据科学方面能找到的一些最好的例子就是语音识别。如果你目前不方便输入信息，你仍然可以对着机器或设备说话并提问，这可能执行得并不准确，尤其是在开始阶段。这意味着我们可能需要花时间研究程序并教它如何识别我们说的一些内容，这就是该过程背后的机器学习——通过经验和时间，它可以学会更快、更高效地识别语音。

如果你曾经用过某些帮助比较价格的网站，你也见过数据科学的运作。在基础层面上，你会发现这些网站是由大量数据驱动的，你可以通过 Feed 和 API 获取这些数据。它们可以利用这些信息计算来自不同网站和来源的相同产品的价格，以便你做出最佳决策并节省资金。这可以用于许多行业，帮助你比较价格并找出对你最好的选择。

当我们谈论如航空公司航线规划这类内容时，我们也可以看看这种技术是如何工作的。这个行业如果不小心，将会遭受巨大的损失。除了少数几公司外，许多公司都在挣扎维持所需的客座率并获取利润。再加上目前燃油价格上涨以及对许多客户提供丰厚折扣的需求，情况正在慢慢变糟。

没多久，这些航空公司就开始开始与数据科学合作，看看他们如何在不惊走客户的情况下增加利润并赚更多钱。这帮助他们确定了现在可以采取的一些战略性改进，包括：

- 对航班延误做出更好的预测。
- 决定应该投资哪种舱位的飞机。
- 决定是应该直接降落在目的地，还是在中途停靠。
- 帮助推动客户可以加入的某些忠诚度计划。

接受这些变化的两家航空公司包括美国航空和西南航空，它们现在是世界上利润率最高的航空公司之一。

借助数据科学，这些公司以及更多企业已经能够确定最佳的运输路线、最佳交付时间，以及对它们最有效的运输方式。这有助于它们在整个过程中获得更高的成本效益和更多的利润。此外，这些公司通过安装的 `gps` 单元产生的数据，可以为他们提供探索更多可能性所需的数据，并在过程中通过数据科学学习更多知识。

当谈到公司使用数据科学时，我们可以看到许多益处。在很多情况下，如果你不至少使用一点数据科学，你会发现自己会落后。无论你正试图解决什么种业务问题，或者你想在业务中解决什么问题，你都会发现运用数据科学是帮助你解决最好且最有效的方法之一。

### 数据分析

![Image00036.jpg](img/Image00036.jpeg)

既然谈到了使用数据科学，我们还需要看一看一些数据分析。这基本上是数据科学的一个子集，我们在这里处理从许多不同来源收集的数据，然后使用算法来帮助我们理解所有这些数据的含义。

你可以使用我们想要的所有数据，如果愿意的话，我们可以填充许多数据仓库，但如果你不理解数据在告诉我们什么，那么这些数据就不会那么重要，你的公司也无法利用它们。这就是我们能够获取数据分析过程并使其发挥作用的地方。

为了帮助我们开始，数据分析是指处理我们拥有的原始数据并对其分析，以帮助我们对所有信息得出良好结论的过程或科学。与此相关的许多技术和过程已经自动化为算法和其他机械过程，这些过程可以在数据以原始形式存在进行处理，然后将其转换为比以前更易读和理解的内容。

当数据分析被恰当使用时，它将帮助我们看到某些在其他情况下可能会错过的指标和趋势，因为我们要收集和持有的数据太多了。这些信息随后可以被用来优化流程，以帮助提高系统或业务的整体效率。

现在我们已经了解了数据分析的广义含义，是时候进入它的不同部分以及我们如何利用它来取得自己的优势了。“数据分析”这个术语非常广泛，它包含了许多不同类型的数据分析。任何可以接受数据分析技术处理以深入研究，然后供人类用于改进其业务某些方面的信息，都属于这个范畴。

让我们来看一个例子。许多制造公司会花时间记录所用不同机器的工作队列、停机时间和运行时间。然后他们将利用包含这些信息的数据来更好地规划工作负载应该如何以及何时发生。这有助于机器尽可能达到其峰值容量，在此过程中节省了时间和金钱。

这只是数据分析能够帮助的任务之一，尽管防止生产中的瓶颈是一个值得关注的好事。游戏公司可以利用这一过程为玩家设置正确的奖励计划，这种方式确保了大多数玩家保持在游戏中活跃，而不是流失并很少使用它。另一个例子是内容公司。他们可以利用数据分析的不同部分来吸引客户不断点击、观看，甚至重新组织内容，以获得所需的点击量和观看量。

在我们处理这一过程中，始终要记住，我们正在处理的数据是一个非常复杂的过程，如果你不这样做，最终将错过重要信息。在收集数据时，遵循正确的步骤可以产生影响，接下来的步骤包括：

我们首先确定我们所需数据的需求，因为这将组织数据。数据有许多方式可以根据收入和年龄等因素进行分组。的第二步是从不同的环境（如在线调查和社交媒体）收集数据的过程。一旦数据收集完毕并且你确定拥有了这些数据，就是时候对它们进行组织，以便我们快速阅读了。

在组织数据时，你可以选择想要使用的方法。一旦你按照喜欢的方式组织好数据，就是时候对它们进行清理。这意味着数据科学家必须检查并确保数据是不完整的。

在这里，我们需要花点时间来看一下为什么这些数据分析将如此重要，以及为什么企业会希望通过这些算法及更多手段，从他们最初收集到的数据中学习。这些公司发现，他们可以使用数据中的洞察和预测，但当数据量如此巨大，且所有这些数据都来自各种来源时，就需要大量的工作来梳理——工作量大到无法通过人工操作来完成。

数据分析的过程对任何企业（无论他们处于哪个行业）都是有的，因为它可以帮助他们优化性能。它还可以帮助他们完善业务模式，并让他们更容易识别出某些更高效的方法来降低成本和解决问题。除了这些之外，公司还能通过这些数据分析做出有助于他们迈向未来的决策。这种分析还将帮助他们更多地了解现有的一些客户趋势，并帮助你提供对客户同样有效的新服务和产品。

### 数据分析的类型

我们在这里需要花时间考虑的下一件事是确定哪些类型的分析可以供你。数据分析有很多变体，你可以选择最适合你需求的那种。这些类型有很多，但我们将重点关注你在初次开始整个过程时最可能用到的几种。数据分析初学者可以关注的、且大多数数据科学家都会涉及的四种基本类型包括：

#### 描述性分析（Descriptive analytics）

这种类型花时间描述在选定期间内数据中发生了什么。你可能会查看诸如访问量是否有所增加，或者你公司某产品的销售额是比上个月高还是低。

#### 诊断性分析（Diagnostic analytics）

这种类型更多地关注为什么发生了某些事情，或者你业务状况的根源。这种方法很有帮助，但它涉及更多元化的数据输入，并在过程中需要一些假设。例如，某某周销售缓慢是因为天气糟糕导致没人出门购物吗？还是因为你的某次营销活动出了问题，导致销售额陷入了困境？

#### 预测性分析（Predictive analytics）

这种类型将用于根据我们目前掌握的信息，帮助预测很快最可能发生什么。去年夏天暖和时销售额如何？有多少个天气模型会告诉我们今年将有一个热夏天，我们应该为过去观察过的情况做更多准备？

我们可以看到，尽管这些之间存在某些差异，但它们都侧重于处理数据并帮助我们从数据中收集一些用的洞察。尽管目前还没有足够的专业人士来处理所有的工作，但通过分析以准确且及时的方式处理这些数据并执行操作的需求将更高。即使没有这方面的专业人士，公司也可以学习如何让数据分析发挥作用，并借此利用海量数据并从中学习。公司正在看到此带来的所有益处，这将帮助他们做出明智的决策。决策是由数据驱动的，因此他们能够看到很多收益并学会如何战胜竞争。

### 数据分析的益处是什么？

当开始处理数据时，你不会花费太长时间就能意识到，这将带来很多益处。无论你是哪种公司、目标是什么，你在这个过程中也能获得很多益处。这个过程似乎有很多步骤，你可能会花费太多时间在上面工作而得不值，但如果你花时间去了解数据以及它能为你做的所有酷事，那么它是非常值得的。带着这种心态，你将获得的一些益处包括：

- 它帮助你更好地理解客户。所有企业都希望理解他们的客户。这是增加销售和提高收入的最佳方式。但你真的知道客户想要什么、什么能说服他们来到你的商店吗？这种数据分析可以从客户调查和习惯中获取信息，并帮助你做出更多决策以提供更好的客户服务。
- 它帮助你了解你的业务应该遵循的趋势。任何市场总有趋势，但这些趋势往往以非常快的速度移动和变化，难以跟上。使用数据分析可以帮助你提前捕捉到某些趋势，让你更容易满足客户的需求。
- 它帮助你更好地了解你的产品。有时这种数据分析可以帮助你了解哪些产品表现最好以及为什么。你可能会发现某个产品的表现比你想象的要好，或者你应该开始销售更多类似的产品来增加销售。
- 它可以帮助从整体上做出更明智的决策。如果你能为你公司做出的所有决策都有数据和信息支持，那是最好的。数据分析帮助你梳理所有信息，并在对公司做出任何决策之前了解现有情况。这种数据分析过程将是你战胜竞争的最佳方式之一。那些愿意查看数据并愿意观察其中有什么洞察和趋势的公司，将能够比竞争对手更快地发现这些东西，并在他们的行业中获胜。

你会发现，这些益处将帮助你的公司，这也是为什么这种数据分析对整个公司如此有利，以及为什么它在几乎每个行业都有如此需求的主要原因。对于一些较小的公司，那些可能没有选择这种流程的公司会发现，他们仍然可以在局部进行进行处理并获得一些结果。数据分析有很多益处，能够弄清楚如何让它发生，以及你可以做什么来从数据中所看到一些结果，对你来说也是非常重要的。确保你回顾我们在本章中讨论的一些步骤。在本指南的剩余部分中，你会发现你也可以让它适应你的需求。

## 第 2 章：`numpy` 简介

### `n` 数组

你可以使用内存构建复杂的数据结构，因为它们在存储数据方面非常强大；然而，它们在处理这些数据方面并不出色。在处理能力和速度上，它们并不是最优选择，而这在处理复杂算法时至关重要。这就是为什么我们要使用 `numpy` 及其 `ndarray` 对象，它的全称是“n 维数组”。让我们来看 `numpy` 数组的属性：

- 它在传输数据方面是优异且快速的。当你处理复杂数据时，你希望内存能够高效地处理，而不是成为瓶颈。
- 你可以进行向量化。换句话说，你可以进行线性代数计算和特定的元素操作，而不需要强制使用 `for` 循环。这对 `numpy` 来说是一个巨大的优势，因为 Python 的 `for` 循环消耗大量资源，使得使用大量循环而不是 `ndarray` 的成本很高。
- 在数据科学操作中，你将不得不使用一些工具或库，例如 `scipy` 和 `scikit-learn`。如果没有数组你就无法使用它们，因为数组是所需的输入，否则函数将无法按预期执行。

话虽如此，这里有几种创建 `ndarray` 的方法：

- 取一个已存在的数据结构并将其转换为数组。
- 从头开始数组并在后添加值。
- 即使数据存储在磁盘上，你也可以将其上传到数组中。

将列表（list）转换为一维数组是数据科学过程中相当常见的操作。请记住，你必须考虑列表所包含的对象的类型。这将影响结果的维度。这里有一个仅包含整数的列表的示例：

```python



In: `import numpy as np`

`Int_list = [1,2,3]`

`Array_1 = np.array(int_list)`

In: `array_1`

Out: `array([1, 2, 3])`

你可以像在 Python 中访问列表一样访问数组。你只需要使用索引，而且和在 Python 中一样，它从 0 开始计数。这种操作看起来是这样的：

```python
In: array_1[1]

Out: 2
```

现在，你可以这样获取关于数组内部对象的更多信息：

```python
In: type(array_1)

Out: numpy.ndarray

In: array_1.dtype,

Out: dtype('int64')
```

`dtype` 的结果与你运行的操作系统类型有关。在这个示例中，我们使用的是 64 位操作系统。

接下来，让我们看看如何从文件加载数组。n 维数组可以从文件中包含的数据中创建。这里有一个代码示例：

```python
In: import numpy as np

Cars = np.loadtxt('regression-datasets.csv', delimiter=', dtype=float)
```

在这个示例中，我们通过提供文件名、分隔符和数据类型，利用 `loadtxt` 方法告诉我们的工具从文件创建一个数组。

## numpy 数组的重要性

![Image00038.jpg](img/Image00038.jpeg)

当你开始处理那些与 Python 配合使用的不同库时，你会很快发现，许多库都将基于 numpy 数组。这意味着我们需要至少花一点时间来学习这些数组，以及我们如何让它们满足我们的某些需求。这些数组将引导我们完成数据科学中想要做的许多其他部分，因此学习如何让它们工作以及它们能做什么将产生重远影响。

我们首先需要查看的是 numpy 数组到底是什么。我们经常会处理所谓的“结构化 numpy 数组”（structured numpy array）。这是一种结构体数组，类似于我们在 C 语言中看到的结构体。我们还会发现这些数组是同质的（homogeneous），这意味着它们只能包含相同类型的数据。因此，与其创建一个整数或浮点数数组，我们也可以创建一个创建一个包含某些其他同质结构的这类数组。

现在，如果你有时间处理它们，你可能会观察到它们与我们所看到的有何不同，这有几个原因，我们将使用其中一些。首先，numpy 中的数组会比列表更紧凑。此外，你会发现从读写方面来说，访问数组比访问列表要快得多，而且你会发现它处理起来要容易得多。

如果你正在处理 4 GB 的数据，而 Python 单独处理可能至少需要 12 GB 才能完成，许多人会说这需要两倍的空间甚至更多。我们可以想象，我们需要使用的空间越大，列表对你来说就越好，你会发现它要好得多，你也会发现 numpy 数组要快得多，当你处理这些数组时，你会发现这对你非常有利，从远来看，你会发现这一切都是有用的。

现在，刚开始，如果你只是处理百万级的数据，这可能并不重要，但当你处理像十亿个单元这样庞大的东西时，它就变得了。这两种方法都无法适应基于 32 位的架构。尽管如此，如果你使用的是 64 位系统，你可以使用 numpy 进行构建并在约 4 GB 内完成所有工作。

进一步来说，你不仅会享受这些数组带来的便利，还会喜欢它们的高效性、功能性以及速度。在处理总数百万甚至数十亿个数据点时，在此过程中能够以快速且高效的方式完成工作至关重要。这正是 `numpy` 数组能够帮助我们实现这一点。

### 特性

这里首先要关注的是功能性。在使用 `numpy` 数组时，你可以构建出很多内容。例如，你可以处理线性代数、基础统计学、快速搜索、`ffts`、卷积和直方图等（仅举例）。如果没有这些重要部分的加入，你该如何处理你想做的某些数据科学项目呢？

另外，你在使用 `numpy` 数组时会注意到并喜欢的一点是，它具有极高的速度。当你处理一个没有包含大量数据点的较小项目时，这种速度可能并不明显。但当你处理一个包含大量数据点的大型项目时，你会很快发现这是一个非常重要的特性，也是 `numpy` 数组能够提供的优势。

### 益处

当你决定在某些数据分析项目中使用 `numpy` 数组而不是 `python` 列表时，你还将获得以下其他方面的益处：

`numpy` 中出现的数组在创建时是固定大小的。这与我们看到的 `python` 列表不同，列表可以动态地改变和增长。在数组完成后更改其大小，仅仅会创建一个全新的数组供你使用。

你在某些数组中看到的元素告诉我们，它们必须是相同的数据类型。我们有时也可以处理异构类型，但这会导致我们无法执行你想进行的某些数学操作。由于这让你无法通过数组完成你想实现的某些数据科学部分，因此通常不建议这样做。然而，由于你在整个过程中使用了相同类型的对象，你会发现在你编写代码的内存中，所有这些对象的大小都是相同的。

在需要处理大量数据时，我们所操作的数组将有助于高级数学和其他其他类型的操作。通常情况下，这些操作的执行效率更高，而且代码量通常比我们在 `python` 中看到的某些内置序列要少。

在使用 `numpy` 库时，你会注意到的最后一点是，许多与 `python` 配合的其他专业库（包括用于深度学习、机器学习、数据科学和数据分析的库）都是基于这些 `numpy` 数组的。如果没有先准备 `numpy` 数组，很难实现与这些主题相关的任何功能。为了做到这一点，我们需要确保该库已经安装好并准备就绪。

### 操作

正如我们在这里所看到的，在处理其中一个 `numpy` 数组时，我们将看到许多益处和用途。它们被设计用于在处理我们的数据科学时处理许多不同的选项，学习如何正确地让它们工作对于我们整个过程中能取得多少成功至关重要。确保在你想处理某些数据科学项目时安装 `numpy` 库。这将确保我们能从所有事物中获得最佳结果，并使我们在项目完成后更容易获得我们想要的结果。在处理多维数组时进行 `numpy` 数组操作时，你可能想要添加新的行或列来表示新数据。这种操作被称为数组堆叠（array stacking），`numpy` 渲染这些信息并不需要长时间。从创建一个新数组开始：

```python
import numpy as np

dataset = np.arange(50).reshape(10,5)
```

接下来，添加一个新行和几行将合并的行：

```python
single_line = np.arange(1*5).reshape(1,5)

multiple_lines = np.arange(3*5).reshape(3,5)
```

现在让我们使用 `vstack` 方法（代表垂直堆叠 vertical stack）来添加新的单行：

```python
np.vstack((dataset,single_line))
```

如果我们想添加几行，此命令同样有效：

```python
np.vstack((dataset,multiple_lines))
```

接下来，让我们看看如何向数组添加一个变量。这是通过 `hstack` 方法（代表水平堆叠 horizontal stack）完成的。这是一个示例：

```python
bias = np.ones(10).reshape(10,1)

np.hstack((dataset,bias))
```

在这行代码中，我们为之前创建的数组添加了偏置值（bias）。作为一名有志的数据科学家，你只需要知道如何向数组添加新的行和列。在大多数项目中，你不需要做得更多，所以请练习操作多维数组和 `numpy`，因为这个工具已经深根于数据科学之中。

## 字体 Numpy 库

现在是时候让我们查看一下在使用 `python` 时可以帮助我们数据分析良好运行的优秀库之一。`numpy` 是我们首先查看的库之一，而且它非常出色。它是我们之后将讨论的其他重要库或其他数据分析库的基础，所以花时间了解它它是值得的。

首先，`numpy` 是一个用于 `python` 的库。我们可以出于几种不同的原因使用它，包括在需要时进行数值计算和科学计算。但在大多数情况下，它被用于帮助我们快速、高效地计算数组。它是基于 `python` 和 `c` 语言编写而成的。

尽管这种语言也适用于 `c` 语言，但它将成为我们在使用 python 时使用的一个基础数据分析库。`numpy` 这个词代表数值 Python（numerical python）。我们将引入这个库来帮助我们处理任何所需的同质多维数组。

当我们需要处理这些数组时，它是科学计算的核心库之一，并集成了一些非常有用的工具。

### 深入了解 numpy

这个库非常基础，但在处理我们想要用 Python 进行的某些科学计算时，它仍然至关重要。此外，在从事数据科学和数据分析工作没不了多久，你就会发现这个库将是其他数据分析库所依赖的库。

其他一些重要的库将依赖 numpy 中的数组（arrays）作为它们的输入和输出。此外，它还将提供一些函数，允许开发者执行他们想要的所有基础和高级功能，无论我们是在讨论统计学还是数学，特别是当我们在处理多维数组和矩阵时，不需要编写大量的代码就能完成所有工作。

当我们将这些数组与之前讨论过的 Python 列表（lists）进行比较时，你会发现数组的速度要快得多。但 Python 列表确实比数组更有优势，因为它们更灵活，而在我们处理数组时，每一列中你只能存储相同类型的数据。

当你开始使用 numpy 库时，你会喜欢其中的一些功能。你最喜欢的一些主要特性包括：

- numpy 库是 Python 和 C 语言的结合。
- 它由同质且多维的数组组成。`ndarray` 是其中的一部分，它也是 n 维数组。
- 如果你愿意，它可以对数组进行许多不同的函数操作。
- 它还可以帮助我们重塑（reshape）数组。它还让 Python 有了作为 matlab 的替代方案。

我们有很多理由想要使用 numpy，而不是在其他现有库中挑选一个。我们将在 Python 工作中使用 numpy 数组而不是列表。这 le 其中的一些原因包括：它使用起来很方便，它的执行速度比其他方法更快，而且总体使用的内存更少。

当我们尝试执行数据分析中需要的某些算法时，所有这些都是重要的。而且大多数情况下，你会注意到当开始使用这个库时，数组是我们利用的首要内容。

在如何使用 numpy 库方面，我们还需要探索其他一些事情。首先，numpy 数组比其他选项占用的空间少得多。另一方面，我们可以创建一个数组，它只占用大约 4 mb。如果你在过程中需要使用许多不同的数组，它们将更适合你的内存空间。当你以后对它们进行读写时，数组也更容易访问。

此外，在速度方面，你会发现 numpy 数组非常棒。在计算方面，它的执行速度会比 Python 列表快得多。因为这个库被认为是开源的，所以你不需要支付任何费用即可开始使用。它具有与流行的 Python 语言协作的优点，该语言对于你想要完成几乎所有任务都有高质量的库。

这些都是工作时的巨大益处。你会发现这是一个高质量的库，将帮助我们完成工作。你可以让它与你需要的库匹配，它是免费的，并且可以处理你想要做的许多数据分析项目。它还是一个简单的库，可以将 C 语言中已有的代码通过 Python 解释器连接起来，以便你完成工作。

当你想要使用 numpy 库时，将会出现很多优势，你会发现你在进行数据分析时，它是你想要编写许多代码和算法的基础。学习如何使用这种语言以及它能为你做什么，将对你长期的成就产生巨大影响，为了完成你的项目，花时间了解更多它是值得的。

## 第 3 章：使用 pandas 操作数据

### Pandas

Pandas 构建在 numpy 之上，它们旨在一起使用。这使得从数据框（data frames）中提取数组变得极其容易。一旦提取出这些数组，它们就可以转换为数据框。让我们来看一个例子：

```python
import pandas as pd

import numpy as np

marketing_file_name = 'regression-datasets-marketing.csv'

marketing = pd.read_csv(marketing_file_name, header=none)
```

在这个阶段，我们将数据上传到数据框中。接下来，我们将使用 `value` 方法提取一个与数据框类型相同的数组。

```python
marketing_array = marketing.value
```

在速度方面，你会发现 numpy 数组非常棒。在计算方面，它的执行速度会比 Python 列表快得多。

当你想要使用 numpy 库时，将会出现很多优势，你会发现你在进行数据分析时，它是你想要编写许多代码和算法的基础。

```python
[65, 66, 67, 68, 69], [85, 86, 87, 88, 89]]
```

我们已经成功地对行和列进行了切片。但如果我们尝试使用负索引会发生什么呢？这样做会反转数组。这里是使用负索引时之前的数组的样子。

In: `m[2:9:2,5::-1]`

Out: `array([[25, 24, 23, 22, 21, 20], [45, 44, 43, 42, 41, 40], [65, 64, 63, 62, 61, 60], [85, 84, 83, 82, 81, 80]])`

还有其他切片和索引数组的方法方法，但对于这本书来说，知道如何执行之前提到的步骤足够了。然而，请记住，这个过程只是查看数据的一种方式。如果你想通过创建新数据来进一步使用这些视图，你就不能对原始数组进行任何修改。如果你这样做，可能会导致一些负面的副作用。在这种情况下，你想要使用“copy”方法。这将创建一个数组的副本，你可以按照你意愿的方式修改它。这里是 copy 方法的代码行：in: `n = m[2:9:2,5:].copy()`

Pandas 是基于 numpy 构建的，它们的设计初衷是一起使用。这使得从 dataframe 中提取数组变得极其简单。一旦提取了这些数组，它们就可以转换为 dataframe。让我们来看一个例子：

```python
import pandas as pd

import numpy as np

marketing_file_name = 'regression-datasets-marketing.csv'

marketing = pd.read_csv(marketing_file_name, header=None)
```

在这个阶段，我们正在将数据上传到 dataframe 中。接下来，我们将使用“values”方法来提取一个与 dataframe 中包含的数据类型相同的数组。

In: `marketing_array = marketing.values`
`marketing_array.dtype`

Out: `dtype('float64')`

我们可以看到我们有一个浮点类型的数组。你可以通过首先使用“dtype”方法来预判数组的类型。这将确定指定 dataframe 对象正在使用哪些类型。在提取数组之前执行此操作。此操作看起来如下：

In: `marketing.dtypes`

Out:
```text
0 float64

1 int64

2 float64

3 int64

4 float64

5 float64

6 float64

7 float64

8 int64

9 int64

10 int64

11 float64

12 float64

13 float64
```
Dtype: object

### 矩阵运算

这包括矩阵计算，例如矩阵之间的乘法。让我们创建一个二维数组。

这是一个从 0 到 24 的数字二维数组。接下来，我们将一个系数向量和一个将该向量及其反转堆叠的列。它的样子应该是这样：

```python
coeffs = np.array([1., 0.5, 0.5, 0.5, 0.5])

coeffs_matrix = np.column_stack((coeffs, coeffs[::-1]))

print(coeffs_matrix)
```

Out:
```text
[[1.  0.5]

[0.5 0.5]

[0.5 0.5]

[0.5 0.5]

[0.5 1.]]
```

现在我们可以进行乘法。这里是数组与向量相的例子：

In: `np.dot(m, coeffs)`
Out: `array([5., 20., 35., 50., 65.])`

这里是数组与系数之间相法的例子：

In: `np.dot(m, coeffs_matrix)`
Out:
```text
array([[5., 7.],

[20., 22.],

 [35., 37.],

 [50., 52.],

 [65., 67.]])
```

在这两个操作中，我们使用了 `np.dot` 函数来实现 m。

### 切片与索引

索引非常适合通过发送列或行的切片来查看数组。让我们从创建一个 10x10 的数组开始。它最初是二维的。

```python
import numpy as np

m = np.arange(100, dtype=int).reshape(10,10)
```

接下来，让我们从 2 到 8 提取行，但只提取偶数行。

In: `m[2:9:2,:]`
Out:
```text
array([[20, 21, 22, 23, 24, 25, 26, 27, 28, 29],

 [40, 41, 42, 43, 44, 45, 46, 47, 48, 49],

 [60, 61, 62, 63, 64, 65, 66, 67, 68, 69],

 [80, 81, 82, 83, 84, 85, 86, 87, 88, 89]])
```

现在让我们提取从 5 的列，但只提取偶数。

In: `m[2:9:2,5:]`
Out:
```text
array([[25, 26, 27, 28, 29],

 [45, 46, 47, 48, 49],

 [65, 66, 67, 68, 69],

 [85, 86, 87, 88, 89]])
```



我们可以使用切片我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。行和列进行索引。如果尝试使用负索引，数组中的元素顺序将被反转。下面是使用负索引后的数组：

In: `m[2:9:2,5::-1]`

Out:

```python
array([[25, 24, 23, 22, 21, 20],
       [45, 44, 43, 42, 41, 40],
       [65, 64, 63, 62, 61, 60],
       [85, 84, 83, 82, 81, 80]])
```

不过请记住，这个过程只是查看数据的一种方式。如果你想通过创建新数据来进一步使用这些视图，就不能对原始数组进行任何修改，否则可能会导致负面影响。在这种情况下，应使用`copy()`方法。该方法会创建数组的副本，你可以按照需要修改它。下面是使用`copy()`方法的代码：

In: `n = m[2:9:2,5:].copy()`

Pandas 是基于 NumPy 构建的，二者的设计初衷是一起使用。这使得从`DataFrame`中提取数组变得极其简单。提取数组后，还可以将其转换回`DataFrame`。

```python
import pandas as pd
import numpy as np

marketing_file_name = 'regression-datasets-marketing.csv'
marketing = pd.read_csv(marketing_file_name, header=None)
```

在这个阶段，我们正在将数据加载到`DataFrame`中。接下来，将使用`values`属性提取一个与`DataFrame`中数据类型相同的数组。

In: `marketing_array = marketing.values`

`marketing_array.dtype`

Out: `dtype('float64')`

我们可以看到，这是一个浮点类型数组。你可以先使用`dtypes`属性预判数组的类型。该属性可以确定指定`DataFrame`对象使用的类型，应在提取数组之前执行此操作：

In: `marketing.dtypes`

Out:

```text
0 float64
1 int64
2 float64
3 int64
4 float64
5 float64
6 float64
7 float64
8 int64
9 int64
10 int64
11 float64
12 float64
13 float64
```

Dtype: object

## 矩阵运算

矩阵运算包括矩阵之间的乘法。下面创建一个二维数组。

这是一个包含 0 到 24 的数字二维数组。接下来，我们将创建一个系数向量，以及一个将该向量与其反转版本堆叠起来的矩阵：

```python
coeffs = np.array([1., 0.5, 0.5, 0.5, 0.5])
coeffs_matrix = np.column_stack((coeffs, coeffs[::-1]))

print(coeffs_matrix)
```

Out:

```text
[[1.  0.5]
 [0.5 0.5]
 [0.5 0.5]
 [0.5 0.5]
 [0.5 1.]]
```

现在可以执行乘法。下面是数组与向量相乘的示例：

In: `np.dot(m, coeffs)`

Out: `array([5., 20., 35., 50., 65.])`

下面是数组与系数矩阵相乘的示例：

In: `np.dot(m, coeffs_matrix)`

Out:

```text
array([[5., 7.],
       [20., 22.],
       [35., 37.],
       [50., 52.],
       [65., 67.]])
```

在这两个操作中，我们使用`np.dot()`函数实现了`m`与其他对象的乘法。

## 切片与索引

索引非常适合通过指定列或行的切片来查看数组。让我们从创建一个 10×10 的二维数组开始：

```python
import numpy as np

m = np.arange(100, dtype=int).reshape(10, 10)
```

接下来，从第 2 行到第 8 行提取数据，但只提取偶数行：

In: `m[2:9:2,:]`

Out:

```text
array([[20, 21, 22, 23, 24, 25, 26, 27, 28, 29],
       [40, 41, 42, 43, 44, 45, 46, 47, 48, 49],
       [60, 61, 62, 63, 64, 65, 66, 67, 68, 69],
       [80, 81, 82, 83, 84, 85, 86, 87, 88, 89]])
```

现在提取第 5 列之后的列，但只提取偶数行：

In: `m[2:9:2,5:]`

Out:

```text
array([[25, 26, 27, 28, 29],
       [45, 46, 47, 48, 49],
       [65, 66, 67, 68, 69],
       [85, 86, 87, 88, 89]])
```

我们成功地对行和列进行了切片。如果尝试使用负索引，数组中的元素顺序将被反转。下面是使用负索引后的数组：

In: `m[2:9:2,5::-1]`

Out:

```text
array([[25, 24, 23, 22, 21, 20],
       [45, 44, 43, 42, 41, 40],
       [65, 64, 63, 62, 61, 60],
       [85, 84, 83, 82, 81, 80]])
```

不过请记住，这个过程只是查看数据的一种方式。如果你想通过创建新数据来进一步使用这些视图，就不能对原始数组进行任何修改，否则可能会导致负面影响。在这种情况下，应使用`copy()`方法。该方法会创建数组的副本，你可以按照需要修改它。下面是使用`copy()`方法的代码：

In: `n = m[2:9:2,5:].copy()`

## 使用 pandas 进行数据清洗

现在你已经准备好了所有工具，并拥有了整洁的环境，是时候开始数据科学中的数据清洗（data munging）过程了。这个过程有时也被称为数据整理（data wrangling），是整个数据科学流水线中最重要的步骤之一。

其基本概念是处理一组数据，以便将其与其他数据集结合使用或对其进行分析。你必然需要对原始数据集进行充分修改，使其符合特定目标。为了更好地理解这一点，可以想象你有一组数据，并想对其应用分类算法。然而，你还无法执行这一步，因为数据集由连续变量和分类变量混合组成。这意味着你必须修改某些变量，使其符合正确的格式。

挑战在于，你正在处理原始数据，尚未能够对其进行分析。首先，需要使用各种数据清洗技术和工具清洗数据。在大多数现实场景中，你将处理大量原始数据，这与用于学习和练习的数据集不同。因此，数据清洗可能会花费大量时间。许多数据科学家花费在准备数据上的时间，超过了编写代码或运行各种算法的时间。

那么，如何准备数据呢？一种常用方法是使用`pandas`库进行数据分析和处理。正如前面提到的，该库的目的是帮助你更快速地分析现实世界中的数据。

请记住，数据清洗（data munging）的目的是收集足够的信息，以检测其中的模式。此外，数据必须准确，才能对数据科学家或分析师有用，从而减少产生有意义结果所需的时间和资源。

考虑到这一点，第一步是获取数据。毕竟，没有数据就什么也做不了。然而，在获取访问权限之前，需要理解所有数据项各不相同，而且它们的生成质量也不尽相同。识别具有特定来源的真实数据时，经常会遇到问题。

第二步是在从各个来源提取数据后进行合并。在这一阶段，需要修改数据，然后将其组合，以便后续分析。

最后一步是清洗数据，这是整个过程的核心阶段。你需要修改数据，使其符合可用格式。还可能需要执行一些可选步骤，例如纠正会对结果产生负面影响的噪声数据或错误数据。

如你所见，这一步至关重要，尽管它可能枯燥且耗时。然而，有时无法避免。必须确保拥有相关、最新且不包含空值的信息，以便只选择感兴趣的数据进行分析。幸运的是，Python 配合`pandas`是辅助数据清洗的强大工具之一。

### 流程

你可以通过许多方式收集数据，例如从数据库、图像、电子表格以及任何存储信息的数字源中提取数据。然而，这些都是原始数据，不能直接用于适当分析，因为其中可能存在缺失信息和损坏数据。

首先，需要使用 Python 数据结构为混乱建立秩序，将原始信息转换为由格式正确的变量组成的组织化数据集，然后借助各种算法处理该数据集。

接下来，可以检查数据，得出稍后将进行测试的初步观察。通过处理现有变量获得新变量，并利用图分析等技术推进数据科学流水线，从而揭示最有价值的变量。

现在可以创建第一个数据模型了。不过，测试阶段可能会表明必须对数据进行修正，此时需要返回数据清洗过程，重新处理每一步。请记住，在大多数情况下，预期输出不会完全反映实际输出。理论并不总是会引导你得到预期结果，因此需要处理许多不同场景并进行测试，以确定哪些方法有效。

### 导入数据集

在进行任何操作之前，需要准备实际数据。为了导入数据集，我们将使用`pandas`访问来自各种数据库或电子表格的表格信息。本质上，该工具会构建一个数据结构，为表格文件的每一行建立索引，同时分离变量，以便我们操作数据。

在 Jupyter 中输入以下命令，将`pandas`导入当前环境并访问 CSV 文件：

```python
import pandas as pd

iris_file_name = 'datasets-ucl-iris.csv'

iris = pd.read_csv(
    iris_file_name,
    sep=',',
    decimal='.',
    header=None,
    names=['sepal_length', 'sepal_width', 'petal_length', 'petal_width', 'target']
)
```

（来源：鸢尾花数据集 https://scikit-learn.org/stable/auto_examples/datasets/plot_iris_dataset.html，检索于 2019 年 10 月）

如你所见，第一步是导入将要使用的工具。无论打算使用`pandas`还是`scikit-learn`，仅在系统上安装它们是不够的，还需要将其导入项目，才能访问其中的函数。

接下来，我们创建一个新文件并命名，同时定义作为分隔符的字符。在这个示例中，新文件包含一个具有特征的数据集。该数据集命名为`iris`，包含 150 个样本。

我们创建了一个`DataFrame`，这在前面已经介绍过。它类似于字典，但带有特征。接下来，探索其中包含的内容：

```python
iris.head()
```

这是一条简单的指令。如果未指定参数，默认显示前五行。接下来查看列数：

```python
iris.columns
```

输出：

```text
Index(['sepal_length', 'sepal_width', 'petal_length', 'petal_width', 'target'], dtype='object')
```

接下来获取目标列：

```python
y = iris['target']
```

此时，`y`几乎与数组相同。接下来提取几列：

```python
x = iris[['sepal_length', 'sepal_width']]
```

现在得到一个`DataFrame`，它是一个矩阵而不是序列（Series）。之所以是矩阵，是因为我们要求一次提取多个列。

现在获取所有维度：

```python
print(x.shape)  # (150, 2)
print(y.shape)  # (150)
```

结果是一个元组，我们可以分析数组在任一维度上的尺寸。这些是操作新数据集和进行探索的基础知识。接下来处理数据，以便后续使用。

### 数据处理

现在你已经知道如何加载数据集，接下来探索处理其中所有信息时需要采取的步骤。

首先，假设需要对某些行执行特定操作。为了使用相关函数，首先需要设置一个掩码（mask）。在这种情况下，掩码是一组布尔值，用于决定选定哪些行。下面通过实际示例说明这一概念：

```python
mask_feature = iris['sepal_length'] > 7.0

print(mask_feature)
```



```
输出:
0    False
1    False
...
146   True
147   True
148   True
149   False
Name: sepal_length, dtype: bool
```

正如你所见，我们只选择了包含独立长度值且大于七的行。这些观测值是用布尔值声明的。接下来，我们将应用掩码（mask）来修改 `iris virginica` 目标并为它创建一个新标签：

入：`mask_target = iris['target'] == 'iris-virginica'`

入：`iris.loc[mask_target, 'target'] = 'mylabel'`

任何旧的 `iris virginica` 标签出现的地方，现在都将被替换为新标签 "mylabel"。请注意，对于此操作，我们需要使用 `loc` 函数来通过索引访问数据。现在，让我们迈向下一步，查看 `target` 列中包含的标签：

入：`iris['target'].unique()`

输出：`array(['iris-setosa', 'iris-versicolor', 'new label'], dtype=object)`

现在让我们对所有列进行分组：

入：`grouped_targets_mean = iris.groupby(['target']).mean()`

输出：`grouped_targets_var`

入：`grouped_targets_var = iris.groupby(['target']).var()`

输出：`grouped_targets_var`

通过这一步，我们使用 `groupby` 函数对列进行了分组。请注意，这类似于 SQL 中的 "group by" 命令。在下一行中，我们还应用了 `mean` 函数，该函数计算平均值。记住，我们可以将此方法同时应用于单列或多列。此外，我们还可以使用方差（variance）、计数（count）或求和（sum）函数来获取不同的值。请注意，获得的结果也是一个 pandas dataframe，这意味着你可以连接所有这些操作。在这个示例中，我们根据标签对所有观测进行分组，以便分析组之间的差异。但如果我们还有时间序列需要处理会呢？如果你不熟悉时间序列，你应该知道它们意味着对一组顺序出现的数据项进行分析。这种顺序是按时间顺序决定的。本质上，你处理的是一组分布在时间中的点，每个点之间有等距间隔。你会经常遇到时间序列，因为它们被用于许多领域，通常与分析有关。例如，当你必须处理天气数据时，你会发现关于预测或太阳黑子检测的时间序列。

下一个挑战是处理包含噪声的数据项。请记住，虽然这些训练数据集已经经过了多年的记录和处理，但它们往往非常干净，实际上实际上量的处理和清洗。然而，在现实世界中，你会经常遇到噪声数据。在这种情况下，我们可以做的第一件事是使用滚动函数（rolling function），它如下：

入：`smooth_time_series = pd.rolling_mean(time_series, 5)`

在这个过程中，我们再次应用了 `mean` 函数。记住，你不一定得使用 `mean`。你也可以选择 `median`（中位数）值。此外，你会注意到我们请求访问五个样本。接下来，我们将使用 `apply` 函数对我们的列和行执行一些操作。这是一个可以用于多个用途的函数，让我们让我们从确定每行有多少个非零项开始：

入：`iris.apply(np.count_nonzero, axis=1).head()`

输出：
```
0 5
1 5
2 5
3 5
4 5
dtype: int64
```

最后，`applymap` 函数用于对元素本身执行操作。假设我们需要获取每个单元格内每个字符串表示的长度值：

入：`iris.applymap(lambda el: len(str(el))).head()`

为了获得这些值，单元格被转换为字符串，然后我们就可以确定长度。

现在你已经有了关于使用 pandas 进行数据处理的想法，让我们也借助同一个工具讨论数据选择的话题。

### 数据选择

当我们谈到数据选择时是指什么意思？假设你有一个想要访问和处理的数据集。为了这个例子，我们将对所有的分组：

```
100
101
102
103
104
```

正如你所见，第一行是 0，其索引是 100。在任何需要将数据从其余部分分离的地方，我们将使用：

`dataset = pd.read_csv('data.csv', 0)`

例如，当你必须处理天气数据时，你会发现关于预测或太阳黑子检测的时间序列。下一个挑战是处理包含噪声的数据项。请记住，虽然这些数据集已经经过了多年的记录和处理，但它们往往非常干净，实际上只需要很少的处理和清洗。然而，在现实世界中，你会经常遇到噪声数据。在这种情况下，我们可以做的第一件事是使用滚动函数，它如下：

`smooth_time_series = pd.rolling_mean(time_series, 5)`

在这个过程中，我们再次应用了 `mean` 函数。记住，你不一定得使用 `mean`。你也可以选择 `median`（中位数）值。此外，你会注意到我们请求访问五个样本。接下来，我们将使用 `apply` 函数对我们的列和行执行一些操作。这是一个可以用于多个用途的函数，让我们从确定每行有多少个非零项开始：

`iris.apply(np.count_nonzero, axis=1).head()`

最后，`applymap` 函数用于对元素本身执行操作。假设我们需要获取每个单元格内每个字符串表示的长度值：

`iris.applymap(lambda el: len(str(el))).head()`

为了获得这些值，单元格被转换为字符串，然后我们就可以确定长度。

现在你已经有了关于使用 pandas 进行数据处理的想法，让我们也借助同一个工具讨论数据选择的话题。

### 数据选择

当我们谈到数据选择时是指什么意思？假设你有一个想要访问和处理的数据集。为了这个例子，我们将对所有的分组：

```
100
101
102
103
104
```

正如你所见，第一行是 0，其索引是 100。在任何需要将数据从其余部分分离的地方，我们将使用：

`dataset = pd.read_csv('data.csv', 0)`

由于 python 在很多情况下会被用于机器学习，像 numpy 和 matplotlib 这样的资源将在很多情况下被用于帮助我们机器学习需要的某些模型，并确保我们可以处理这些技术。

在这种情况下，我们可以做的第一件事是使用滚动函数，它如下：

`smooth_time_series = pd.rolling_mean(time_series, 5)`

在这个过程中，我们再次应用了 `mean` 函数。记住，你不一定得使用 `mean`。你也可以选择 `median`（中位数）值。此外，你会注意到我们请求访问五个样本。接下来，我们将使用 `apply` 函数对我们的列和行执行一些操作。这是一个可以用于多个用途的函数，让我们从确定每行有多少个非零项开始：

`iris.apply(np.count_nonzero, axis=1).head()`

最后，`applymap` 函数用于对元素本身执行操作。假设我们需要获取每个单元格内每个字符串表示的长度值：

`iris.applymap(lambda el: len(str(el))).head()`

为了获得这些值，单元格被转换为字符串，然后我们就可以确定长度。

我们想要实现的想法是，程序员可以访问这些库来处理 `python` 庞大环境中的某些关键任务。它能够遍历并将结果与程序中的所有其他元素和功能集成，用于机器学习、神经网络以及我们想要使用的其他更高级选项。

你会发现，我们通过这个库（以及通过 `numpy`）看到的一些实用程序将主要围绕数字展开。`matplotlib` 的实用性将专门用于可视化绘图工具。因此，从某种意义上说，这些资源更多是分析性的，而非生成性的。然而，我们通过这个库看到的所有基础设施，只要使用得当，都能支持机器学习程序，并为人类操作者提供正确的结果。

考虑到这些信息，我们需要更详细地查看一下 `matplotlib` 库。首先，它是 `python` 软件包的一部分，用于帮助处理 2D 图形。当你想要在数据科学项目中处理一些视觉效果及更多内容时，学习如何高效地使用此类库将至关重要。

### 什么是 matplotlib？

这是你在 `python` 中可以使用最好的绘图库之一，尤其是当你想要处理像 2D 图形之类的内容时。它可以与其他许多不同的地方配合，例如 Web 应用服务器、python shell、python 脚本以及其他一些图形用户界面的工具包。

会有一些可用的工具包，可以帮助扩展我们在 `matplotlib` 中看到的某些功能，并确保我们能够在短时间内用该程序完成更多事情。其中一些需要单独下载，另一些可以在该库的源代码中找到，但必须依赖 `python` 或该库未包含的其他方面。当我们需要扩展 `matplotlib` 的功能时，可以关注并使用的的一些不同扩展包括：

- **Basemap**：这是一个地图绘图工具包，如果你想在项目中使用它，它将会非常有帮助。如果你想处理政治边界、海岸线甚至整个地图投影，它是一个很好的选择。
- **Natgrid**：这是一个指向 `natgrid` 库的接口。当我们想要处理间距数据的不规则网格化时，它最合适。
- **Mplot3d**：当你想要将 `matplotlib` 的 2D 函数扩展为更具 3D 性质的内容时，这将非常有帮助。
- **Excel tools**：该库将为我们提供在需要时与 microsoft excel 交换数据所需的实用程序。
- **Cartopy**：这是我们可以使用的映射库之一，它可以帮助我们处理地图投影的定义，以及一些点、线、多边形和图像转换能力，这只是我们可以依靠的一些特征。

在在此过程中，我们还可以利用许多不同的选项来处理该库的某些功能。它适用于处理我们想要看到的大多数功能，以及对于这类数据科学重要的大多数图表。例如，你可能会发现，当我们想要处理饼图、折线图、直方图、柱状图、面积图、散点图等内容时，该库运行得很好。

如果你在在此期间需要创建图表或图形来处理你正在处理的一些数据，那么使用 `matplotlib` 库将是最好的选择之一。它缺少一些你可能需要的 3D 功能，因此根据你的数据，这是需要考虑的因素。但对于你想要加入混合的某些基础部分，以及对于你想要关注的大多数视觉效果，你会发现 `matplotlib` 库能够胜任。

## 第 5 章：什么是机器学习？

现在是时候让我们来看一下与机器学习相关的基础知识了。回想一下你经历过的几种情况，例如，你是否注意到当你在上网时，机器机会为你为你做推荐？另一个例子是，当你接到银行或其他金融公司的电话，要求你办理新的保单或贷款时；这些金融机构是不可能浪费时间的。

所以，让我们仔细观察一下机器学习的本质。机器学习是人工智能的一部分，主要关注从经验中学习；机器可以根据发生过的事情做出预测。

### 机器学习是做什么的？

它使计算机系统根据数据做出决策，而不是让程序员编写所有的代码来完成任务。这些程序或算法的设计方式与我们过去发现的不同，因为当我们能够将它们暴露给新数据时，它们可以随着推移不断学习和改进。这正是它们变得如此强大，并擅长分析你正在工作的数据的原因。

在我们今天工作的世界里，机器在真正开始遵循你想要的任何指令之前，仍然必须经过编程。但如果将来，机器能够像我们一样，开始从工作和经验中自己学习呢？这不是我们现在就可以使用的东西，但这是一个值得考虑的有趣部分，帮助我们以后实现机器学习的一些目标。

### 机器学习在数据科学中如何工作

机器学习是一个有趣的选项，它可以与数据科学结合，为我们提供所需的信息。这种选项将让网络或系统根据经验和示例进行工作，而无需针对每种情况编写其行为的代码。

这意味着，程序员不再需要花费时间编写他们想要的代码，而是花费时间将数据输入到通用算法中。从那里开始，算法机器将根据给定的数据构建出逻辑。机器学习包含许多部分，弄清楚我们如何与其协作，以及更多内容，将确保我们在这一过程中充分发挥其价值。

在许多应用场景中，我们已经看到机器学习正在飞速增长。如果你曾经使用过搜索引擎在网上查找东西，那么我们对机器学习可以完成的一些工作就很熟悉了。如果你用过某种语音激活设备，无论是在手机上还是那些个人助手设备，那么你会发现自己也接触过机器学习。而且这些仅仅是我们通过机器学习能做的事情的开端。

在未来，这项技术可能会进入新的行业，并为我们提供今天无法想象的新产品和技术。它已经能够为我们做很多事情了，当我们思考这项技术的未来时，随着越来越多的人加入并学习如何使用它，我们确信会看到一些惊人的事情。考虑到这一点，让我们花些时间更多地了解机器学习，以及我们如何利用它来满足我们的需求。

## 机器学习是做什么的？

我们可以在机器学习使用的算法将在我们预留的训练数据的帮助下进行训练，以创建我们想要的模型。当我们向此算法输入一些新的输入数据时，它将使用某些模型作为基础，在过程中为我们提供所需的某些预测。

算法为我们提供的预测将对其准确性进行评估。如果我们发现准确性是可以接受的，那么这个带有机器学习的算法将被部署。如果我们认为准确性水平不够，那么该算法将再次进行训练，直到达到我们想要的准确率为止。

机器学习有很多方法可以帮助我们。很多时候，我们数据科学项目的分析部分将通过机器学习完成，这也会对我们在过程中发现的洞察力产生影响。而且，我们在这里可以使用的所有绝佳技术和方法，将确保我们获得所需的结果。

### 机器学习的不同类型

接下来我们需要花时间研究我们可以处理的机器学习的不同类型。我们可以处理的机器学习主要有三种类型。这些包括监督学习、无监督学习和强化学习。我们将花时间查看每种类型，并看看我们可以对每种类型做些什么来帮助我们实现目标。

首先，我们需要看看监督学习到底是什么。当我们谈论监督学习时，我们说的是可以使用标记数据和示例来帮助算法运行的那种。我们可以将这种方式看作是由老师引导的算法。我们将有一组数据充当老师，而这个老师或数据集的作用就是训练我们正在工作的模型或机器。一旦我们能够完成并训练模型，我们就可以在以后提供新数据时，使用它来开始做出一些预测或决策。

然后我们也可以处理无监督学习的想法。这与我们习惯的监督学习略有不同，但在我们需要处理机器学习工作时，它将增加一些我们正在寻找的功能。无监督模型通过大量的观察进行学习；在观察的帮助下，它可以发现某些结构。

一旦模型被赋予我们想要的数据集，它能够自动发现数据中的某些关系和模式。假设我们有一组想要分组的数据，无监督学习能够将它们分成不同的类。这与监督学习非常不同，监督学习需要数据带有标签，但当我们希望在不预先告诉模型要找什么的情况下发现数据中包含哪些模式时，无监督学习非常有用。

最后，我们可以处理强化学习的想法。主要的区别在于，强化学习看起来很像我们上面提到的，但它将基于试错的想法进行学习，在我们深入研究之前帮助我们。正如我们所见，机器学习包含许多部分，当我们从事任何种类的数据科学时，这将是一个重要的选项。

## 机器学习以及它如何与数据科学结合

只要我们正确使用它，机器学习就可以是数据科学过程中的重要部分。记住，在我们经历这一过程中，数据科学的一个部分是处理数据。这有助于我们处理沿收集的大量数据，并实际上看到其中的洞察力。为了实现这一点，我们需要能够创建模型（可以筛选所有数据）、发现隐藏的模式并为我们提供洞察力。

机器学习是一个过程，通过它我们可以让我们正在使用的系统或机器以人类的方式进行思考。这使得算法能够以人类能够的方式处理并发现隐藏的模式，但它的执行速度比任何人类手动操作都要快得多、高效得多。

想象一下，对于任何个人，甚至是一组试图处理所有这些数据的人来说，手动完成这些工作将有多困难。可能需要多年时间才能处理完所有数据并找到他们需要的见解。而且，考虑到数据生成和收集的速度之快，在我们达到那个时间点时，那些预测和见解已经毫无价值了。

机器学习可以让这个过程变得简单得多。它让我们有一种思考数据的方法，并发现内部符合我们需求的隐藏模式和见解。通过正确的机器学习算法，我们可以学习该过程是如何运作的，以及为了实现这一目标所需的所有步骤。考虑到这些，是时候仔细研究机器学习，以及我们为了满足自身需求而需要涉及的所有部分了。

### 机器学习是如何处理数据的？

现在我们对机器学习的工作原理以及它的重要性有了更浅的了解，是时候更具体地看看机器学习如何出现并帮助我们了。在数据分析方面，我们可以使用机器的原因有很多，因此花时间研究我们如何使用它非常重要。机器学习将成为在此过程中我们想要创建的所有算法的底层过程。无论你的算法简单还是复杂，随之而来的许多编码和机制将由我们将讨论的机器来运行。在 python 的帮助下，你可以编写一些惊人的算法来帮助我们筛选数据。

所以，如果你希望通过这个数据分析过程来筛选你的数据并理解其内部发现，你需要预先学习一些机器学习。这方面的消息是，机器学习能够与我们说过的 python 配合工作，确保尽管机器学习涉及的理念会复杂一些，但我们仍然可以通过简单的代码来完成任务。

### 监督机器学习

我们需要关注的第一类学习被称为监督机器学习。这将是我们可以处理的最基础的机器学习形式，但它将为我们提供一些不同的组成部分，以保持事物持续运行，并帮助我们快速高效地训练算法。

首先，监督学习简单来说就是帮助算法将输入映射到特定输出的过程。我们将在花时间处理这件事，同时向算法展示大量带有相应答案的示例，希望它能发现联系并进行学习。训练完成后，算法将能够在没有相应输出的情况下查看新输入，并独立给出正确答案。

这整个过程将在我们处理之前收集的标记数据集时实现。如果映射正确，算法将能够成功学习。如果在这里没有达到目标，这意味着我们必须对算法进行一些更改，帮助它学习如何对未来获取的新数据做出良好的预测。

这将类似于我们在老师与学生的场景中看到的流程。会有一位老师引导学生从书籍和其他材料中良好学习。学生将接受测试，如果他们的答案是正确的，学生将通过。如果不是，老师将改变方法并帮助学生学得更好，以便他们能从过去的错误中汲取教训变得更好。这些就是使用监督机器学习的基础知识。

### 无监督机器学习

我们可以处理的第二类机器学习被称为无监督学习。这是我们可以在数据分析中使用的一种方法，因为它允许机器在不提供任何信息的情况下处理并分类实体和无形对象。

我们的机器将要分类的对象将是多样的，例如对银行的攻击行为。我们希望在这种机器学习看到的核心思想是，我们能够花一段时间的时间从数据中学习。对于一个需要学习如何理解海量数据的系统来说，这非常常见。

记住这一切，我们会发现监督学习在每种情况下并不适用，例如当我们正在处理的系统需要关于新数据的恒定信息时。例如，即使你无法通过这种机器学习使其工作，无监督学习也能让机器提前学习。

## 引言

我们需要关注的第三种机器学习被称为强化学习（reinforcement machine learning）。这与我们看到的其他两种相比会有所不同，但在很多时候，我们可以使用这种学习方法来帮助我们筛选数据，包括我们的数据分析。让我们深入探讨强化学习的基础知识，以及我们如何利用它来满足需求。

### 强化学习基础

### 什么是强化学习？

首先，在人工智能的背景下，强化学习是一种动态规划类型，它根据算法在获得正确答案时给予“奖励”、获得错误答案时给予“惩罚”的想法来训练算法。

使用强化学习的算法或智能体（agent）能够学习如何与周围的环境进行交互。当智能体执行正确时，它会接收某种奖励。但当它执行不当时，在过程中将会获得某种惩罚或损失。智能体通过这些奖励和惩罚，可以在没有任何人类干预的情况下学习，通过最大化其奖励并找出最小化其所面临惩罚的最佳方法。

当算法有机会学习正确的行为和错误的行为方式时，它就能成功。当它通过奖励学习正确的行为方式时，它将继续执行那些动作或猜测以获得更多奖励。而当它因做错事而受到惩罚时，它也会记住这一点，并在过程中学习如何避免这些情况。

### 强化学习背后的心理学

强化学习是我们在机器学习中可以使用的方法之一，其灵感源于行为主义心理学。我们可以以类似于孩子学习新任务的方式来看待。这种学习方式与其他机器学习选项处理问题的方式有所不同，因为这种特定的算法不会被明确告知它应该如何执行任务。它必须独立学习并解决这个问题。

### 智能体与环境

作为一个智能体（例如用于下国际象棋的程序或自动驾驶汽车），它将与周围的环境进行交互，并根据其表现优坏接收类型的奖励状态。例如，如果游戏成功赢得了国际象棋，它将获得奖励。

反之亦然。如果智能体没有按照应该的方式执行，无论是意味着它在应该赢的时候没有赢，还是根据程序执行了其他错误操作，它将获得某种惩罚。在游戏案例中，它会被将死而非获胜，并可以在过程中从中学习。

智能体通过更多的练习和时间的推移，能够通过动态规划做出一些良好的决策，以最大化其奖励并减少受到惩罚的次数。使用这种方法的优势（特别是当我们处理人工智能时）在于，它允许我们的 AI 程序进行学习，而无需在编程时遍历并详细说明智能体应该如何完成其任务。

### 展望

正如我们所见，机器学习的概念由许多不同的部分组成，探索其中一些内容以及我们对三种主要机器学习类型所能做什么，将取决于我们希望如何在自己的数据分析中使用它们至关重要。请花时间更仔细地观察我们如何利用所有类型的机器学习来满足自己的需求，并从此开始利用它来帮助挑选出我们实现成功所需的算法。

## 结论

感谢阅读本书。下一步是开始了解数据科学如何为你的业务服务。你会发现，有许多不同的方法可以利用所有数据来确保获得洞察，而这只是第一步。

越来越多的数据分析工具将会出现，其中一些工具可能不需要分析师。数据科学所需的人员将继续扩大，需要从科学家、分析师、架构师到数据管理领域的专家等各类人才。然而，大数据人才的短缺需要特别关注，因为如果没有这些人才，数据将只会呆在那里。

数据科学是为业务增添的一项佳事，它可以帮助你确保高客户满意度、低浪费、赚取更多钱，甚至帮助对未来进行预测，例如你开发并推向市场的产品。但学习这一切并不是自然发生的。投身数据科学并学习一些 Python 及其包含的各种库可以产生质变。当你准备好了解更多关于数据分析能为你做什么，以及你如何结合 Python 和机器学习与数据分析一起工作以获得最佳结果时，是时候看看本指南所提供的内容了！

许多公司正在加入这一行列，学习更多如何与数据科学工作，以及这一过程能为他们带来什么。通过本指南的帮助，你也能完成同样的事情。当你准备好加入并学习更多关于数据科学的知识，以及你和你的业务如何从这一过程中受益时，请务必查看本指南以开始。

数据科学正在接管商业世界，许多公司无论处于什么种行业，都发现这种过程正是他们所需的——不仅可以收集他们已有的数据，还可以对其进行清理和分析，以发现内部的洞察和预测。当数据科学被正确使用，并且我们加入一些 `python` 来帮助创建模型和其他所需的内容时，我们将能够能够找到做出业务决策的最佳方法，从而提升我们在行业中的地位。

数据科学包含许多不同的部分，将它们整合在一起可以帮助我们更好地服务客户、寻找新产品推向市场等。通过本指南的帮助，我们希望能够找到战胜竞争的最佳方法，并看到适用于我们的结果。这需要一些时间，以及来自 `python` 的正确算法进行良好的数据分析，但它可以是为你的业务做出明智稳妥决策的最佳方式之一。

许多公司将利用数据科学的理念来获得尽可能多的利益。每家公司都能以不同的方式使用它，并发现它可以帮助他们增加底线、提高利润，并以新颖创新的方式触达客户。当你准备好学习更多关于数据科学如何运作以及相关的各种不同部分时，请务必查看本指南以开始。

# 第 3 册：初学者 SQL

掌握编程艺术与数据库管理的全面指南

vera Poe

## 引言

`sql` 是一种代表“结构化查询语言”的编程语言，考虑到它允许同一系统中的不同数据库进行交互，因此是一种很容易学习的语言。这种数据库系统最早出现于 70 年代，但当 IBM 推出这种编程语言的原型后，它的流行程度开始增长，商业世界也开始关注。

IBM 最初使用的 `sql` 版本（当时被称为 Oracle）非常成功，以至于其背后的团队最终离开了 IBM 并成立了自己的公司。`Oracle` 得益于它与 `sql` 的工作方式，仍然是编程语言的领导者之一，并且不断变化，以跟上编程和数据库管理领域的所有需求。

`sql` 是一组你可以用来与关系型数据库进行交互的指令。虽然有很多语言可以实现此操作，但 `sql` 是大多数数据库都能理解的唯一语言。每当你准备好与这些数据库之一交互时，软件就会进入并翻译你提供的命令，无论你是通过表单输入还是鼠标点击提供的。这些内容将转换为数据库已经能够解释的 `sql` 语句。

如果你曾经工作过数据库驱动的软件程序，那么你过去很可能用过某种形式的 `sql`。尽管如此，你可能甚至不知道自己在这样做。例如，许多动态网页都是由数据库驱动的。这些页面会从你进行的表单和点击中获取用户输入，然后使用这些信息来组合 `sql` 查询。该查询将通过数据库中检索数据，以执行诸如切换到新页面的操作。

为了说明这是如何运作的，想象一个允许搜索的简单在线目录。搜索页面通常会包含一个只有一个文本框的表单。你可以使用表单输入想要搜索的物品名称，然后只需点击搜索按钮。你一点击搜索按钮，搜索就会遍历数据库以查找与搜索相关的内容。它会将那些内容带回来。

对于那些没有时间学习编程语言且不愿学习的人来说，`sql` 中的命令设计语法都符合英语，起初这看起来很复杂，你可能担心设置需要花费多少工作。但当你开始操作几个命令时，你会发现它并没有那么难。看看代码：

## 第 1 章：什么是 sql

什么是 `mysql`？

`mysql` 是一个使用 `sql` 语法管理数据库的工具（数据库服务器）。它是一个 `rdbms`（关系型数据库管理系统），你可以用它来方便对数据库进行操作。

如果你正在使用 `mysql` 管理网站，请确保你的网站主机也支持 `mysql`。

以下是在微软 Windows 中安装 `mysql` 的方法。我们将使用 Windows，因为它是计算机中最常用的应用程序。

结构化查询语言（SQL，简称 SQL）是一种计算机编程语言，通常用于存储、检索和操作存储在关系型数据库中的数据。它是 `oracle`、`mysql` 和 `ms access` 等许多关系型数据库管理系统（RDBMS）的标准计算机编程语言。尽管如此，这些系统使用的版本可能有所不同。例如，`oracle` 使用 `pl/sql`，而 `ms sql server` 则使用 `t-sql`。

IBM 的 Ted C（广誉为关系型数据库之父）在 1970 年提出了数据库关系型模型概念，一切由此此开始。四年后的 1974 年，`sql` 出现了。这最初只是一个想法，在 1978 年以 system/r 的形式概念化，并由 `ibm` 发布。`ansi` 标准和关系型数据库原型于 1986 年首次发布，被称为 `oracle`。这次发布也归功于 `ibm`。

## 为什么选择 SQL？

`Sql` 有许多优势，使其成为数据库领域的标准且流行的编程语言。这些优势包括：

- `Sql` 编程语言可用于访问 `rdbmss` 中的数据。
- 它也可以用于描述数据。
- 数据的定义及其操作也是 `sql` 支持的。
- 通过将 `sql` 模块嵌入其他语言的代码、预编译器和库中，`Sql` 可以与其他编程语言一起使用。
- 可以使用这种编程语言创建和删除数据库。
- 它可以用于设置视图、表和存储过程的权限。
- 最后，它可以用于创建视图、过程和函数。

### 流程

每当你向系统发出命令时，`sql` 进程就会启动。系统确定执行任务的最佳方式，并由 `sql` 引擎进行解释。过程中涉及的不同组件如下：

### 优化引擎

- `Sql query engine`
- `Classic query engine`
- `Query dispatcher`

`sql query engine` 对处理 `sql` 查询进行了基准测试，不管理逻辑文件。`classic query engine` 处理这些文件和非 sql 查询。`sql` 架构如图所示。

### 命令

下面列出了你在与关系型数据库交互期间将要使用和遇到的一些基础 `sql` 命令。它们将在书中后后的部分进行详细解释。通常，`sql` 中的命令被分为三类，即 `ddl`（数据定义语言）、`dml`（数据操作语言）和 `dcl`（数据控制语言）。`ddl` 类下的命令如下：

### `Create`

此命令用于创建对象、表或视图。

### `Alter`

此命令通常用于修改现有的数据库对象。在大多数情况下，该对象是一个表。

### `Drop`

使用 `create` 创建的对象、表和视图可以使用 `drop` 命令删除或移除。

下一组命令是属于 `dml`（即数据操作语言）的命令。这些命令如下：

### `Select`

此命令用于从一个或多个表中检索一组记录。

### `Delete`

此命令用于删除记录。

### `Update`

此命令用于修改或更新记录。

### `Insert`

此命令用于插入记录。

最后一类命令属于 `dcl`（即数据控制语言）。这些命令如下：

### `Grant`

可以使用 `grant` 命令授予用户权限。

### `Revoke`

可以使用 `revoke` 命令收回赋予给用户的权限。

`Sql` 是我们在满足某些需求时可以工作的一个令人兴奋的选项。`Structured query language` 是一种在数据管理和存储设计中标准化的编程语言。正因如此，懂一点的人也可以轻松地操作和创建任何类型的数据。

## SQL 查询类型

在编程世界中，问题被正式称为“查询”（query）。数据库中的查询可以是两种类型：操作（action）或选择（selection）。通过操作查询，会请求关于信息的如删除、刷新等额外任务，而选择查询（select query）则有助于移除信息。

在数据库方面，查询是一种非常有用的工具，因为它们通过结构被客户端定期调用。客户端在表中查找信息后使用它们来获取信息，根据需要进行许多不同的计算并参与各种活动。

对于参与其中的人员来说，幸运的是 `ms access` 允许实现多种类型的查询，但主要类型包括操作查询和选择查询。你可以轻松地将它们视为数据库的另一个部分——类似于宏或表。

当需要在数据库中创建查询时，你可以利用两种两种不同的方法：

- 你可以自己编写 `sql` 查询，或
- 你可以使用 `ms access's query wizard`

### 查询语言

查询语言用于数据库以创建查询，所有其他语言遵循的标准是 `structured query language`。在 `sql` 的伞下，只有少数语言变体，包括 `odb`、`oracle` 和 `mysql`。不同的数据库也有特定的查询，如 `xquery`、数据挖掘扩展、`neo4j's cipher` 以及 `cassandra query language` (`cql`)，这些被 `nosql` 数据库和图数据库整合。

### `Select query`

这种查询类型在进行询问时仅提供极小的难度，因此它是所有 `ms access` 数据库中最常用的类型。这种利用可以从我们的表系列中选出所需信息。

最后，客户端是选择准则并告知数据库的人，以便这些准则找到结果。在调用 `select query` 后，会创建一个表，允许你逐条记录更改信息。

### `Action query`

一旦你调用操作查询，数据库中就会根据查询指示的内容发生相应的活动。这允许整合多项内容，包括创建新记录、刷新它们、删除行或创建一个新表。

当与 microsoft access 配合使用时，“参数查询”可以使用多种查询来实现你所需的结果。正因如此，当使用此类查询时，你可以将参数发送到另一个查询，例如 `select` 或活动查询。这些参数可以是条件或估值，以便查询明确知道需要完成哪些内容。

由于无论是否有交换框它们都会被选中，终端用户可以在每次运行查询时在参数中输入任何值。参数查询本质上只是被修改过的 `select` 查询。

### 聚合查询

聚合查询是一种独特的查询类型。它可以像参数查询一样对其他查询（如 `parameter`、`activity` 或 `choice`）进行更改，但它不同于传递给不同查询的参数，因为该参数将与从其他组中选出的其他项进行聚合。

求和最终是在你选择的表属性内进行的。它可以转换为可衡量的和，例如标准差或中点。

# 准备编写代码

就像任何其他编程语言一样，在深入学习之前，你需要理解你尝试学习的语言的本质。对 SQL 的优势做一个的笔记，并记录你可能会遇到的常见错误。

列出需要安装的应用程序列表，并检查所有这些软件的系统要求。

# 安装 mysql 应用程序

MySQL 是微软为无数组织和小型企业提供的工具之一。目前有几种昂贵的认证课程，可以让你更好地理解这些数据库的管理。在书中，我们在解释了可用的 SQL Server 版本后，连贯地向你解释安装步骤。

## SQL Server 软件类型

微软提供了广泛的软件选择以便更好地部署服务。如果没有足够的数据，购买巨大的资源是没用的。对于海量数据，依赖较少的资源也没有意义，因为会导致持续的停机，这可能会骚扰你的服务用户。正因如此，MySQL 有如下所示的不同类型。

### Express（精简版）

这是一个小型综合版本，包含个人或小型企业运行所需的简单资源和工作台工具。

### Standard（标准版）

标准版通常建议处理中等数据的小企业使用。与 Express 版相比，它可以快速监控操作并处理数据。

### Enterprise（企业版）

企业版是全球最常用的 SQL 服务器之一。它具有广泛的功能，可供中大型使用。它包含许多服务，如报告、分析和审计。由于其复杂性，企业版的费用比标准版贵得多。

### Developer（开发版）

此版本的 SQL Server 主要供开发人员在环境中测试和操作功能。所有开发者都使用此版本来对他们处理的逻辑实体进行实验。你可以通过点击轻松将开发版的许可证转换为企业版。

### Web（Web 版）

此版本的 SQL Server 主要为处理 Web 应用程序而开发。许多中间托管服务使用此版本存储少量数据。

# SQL 软件包含哪些组件？

SQL Server 软件由需要安装的各种组件组成。以下是一些常用的 SQL 服务器管理器。

## 服务器管理系统

这是最关键的组件，服务器管理系统运行时，数据库处于关闭状态。这是管理员与数据库交互的界面。

### 服务器配置

此组件帮助我们提供有关服务器配置的信息。

### 服务器配置文件

这是监控所有正在运行查询的组件。

# 安装之前需要考虑什么？

对软件进行彻底搜索，你可以在文档中找到参数查询。了解组件，充分理解数据库需求。由于无法使用其他三种方法关闭数据库，这种方法是对数据库实例的管理。

# 启动和停止数据库实例

启动 Oracle 数据库实例的过程分为三个步骤：启动实例、加载数据库和打开数据库。

以下将解释几种启动方法：

### 1. nomount 模式

代码和结果如下：



`startup nomount`

### 2. mount 模式

此模式启动实例并保持数据库关闭状态。代码和结果如下：

```
startup mount
```

### 3. open 模式

此模式启动实例并打开数据库，这是正常启动方式。要在数据库上执行操作的用户必须使用 open 模式启动数据库。

就像启动数据库一样，关闭数据库实例也分为三个步骤，即关闭数据库、卸载数据库和停止 Oracle 实例。

关闭的 SQL 语句如下：

### `Shutdown` [输入参数]

### 1. normal approach（正常方式）

这种方法被称为正常关闭。如果对关闭数据库的时间没有限制，通常用于关闭数据库。

代码和结果如下：

```
shutdown normal
```

### 2. transactional approach（事务方式）

这种方法被称为事务关闭。其首要任务是确保所有当前活动事务都能提交，并在最短时间内关闭数据库。

### 3. abort mode（终止模式）

这种方法被称为终止关闭方法，是强制且具有破坏性的。使用这种方法将强制中断任何数据库操作，这可能会丢失某些信息并影响数据库的完整性。由于无法使用其他三种方法关闭数据库，应尽量避免使用这种方法。

MySQL Workbench 是一款可视化的数据库设计软件，由 MySQL 发布，其前身是 OracleForce 的 MySQL Designer。MySQL Workbench 是一一个为开发者、数据库管理员（DBA）和数据库架构师设计的统一可视化工具。它提供了高级数据建模、灵活的 SQL 编辑器以及全面的管理工具。它可以运行在 Windows、Linux 和 Mac 上。

要在 Windows 上使用它，请点击 SQL Server Studio 并选择 `workbench` 选项打开界面。如果你使用的是 Linux 和 Mac，需要在进入 SQL 实例后输入命令 `workbench`。

# 如何在微软 Windows 上安装 mysql

### 访问 MySQL 网站

访问 `www.mysql.com` 并浏览应用程序以选择 MySQL。确保你从官方网站获取 MySQL，以防止下载病毒，病毒可能会对你的电脑产生危害。

### 选择“download”（下载）选项

接下来，点击下载选项。这将带你 MySQL 社区服务器（MySQL Community Server）和 MySQL 社区版（MySQL Community Edition）。点击“download”。

![Image00039.jpg](img/Image00039.jpeg)

### 选择你的 windows 处理器版本

通过仔细页面上的详细信息选择你的 windows 处理器版本。从“other downloads”（其他下载）标签中选择。你可以选择 32 位或 64 位。

点击 windows (x86, 32-bit) zip 存档或 windows (x86, 64-bit) zip 存档的下载按钮，取决于适用于你的电脑。

![Image00040.jpg](img/Image00040.jpeg)

### 在网站注册

在下载你选择的版本之前，你会被要求通过填写 Oracle 账户登录表单进行注册。你不需要回答选择性问题。你也可以点击“no thanks”（不用，谢谢）按钮。另一个选项是在不注册直接下载服务器。尽管如此，你将无法享受某些免费福利，例如下载白皮书和技术信息、更快地访问 MySQL 下载和其他服务。

### 登录你的 mysql 账户

注册后，你现在可以登录新账户。将出现一个新页面，你可以通过显示的旗帜图像选择你的区域。之后，你可以点击下载按钮将其保存到电脑上。这可能需要几分钟时间。

### 为下载的文件命名

下载文件后，你可以为你的 MySQL 文件命名并将其保存到桌面或 `C` 盘。这取决于你的决定，随你的喜好即可。

### 安装你的 mysql 服务器

点击文件打开它，然后点击“install”（安装）在你的电脑上安装 MySQL。这将打开一个小窗口，电脑会询问你是否想要打开并安装该程序。只需点击“ok”按钮。

### 浏览你的 mysql 包

将出现 MySQL Enterprise Server 页面，提供有关你的 MySQL 包包含内容的信息。有些包需要付费，但由于我们只对社区服务器感兴趣，只需点击“next”（下一步）直到到达“finish”（完成）按钮。

取消勾选“register the mysql server now”（现在注册 mysql 服务器）框。向导完成设置后，会出现一个框要求你配置并注册你的 MySQL 服务器。取消“register the mysql server now”框，并勾选“configure the mysql server now”（现在配置 mysql 服务器）的小框。然后点击“finish”。

### 在配置向导中点击“next”

将出现一个窗口，你只需点击 next。

### 选择配置类型

将出现一个窗口要求你选择配置类型。勾选“detailed configuration”（详细配置）的小圆圈，而不是“standard”（标准）。点击“next”按钮。

### 选择服务器类型

会有三个选择：developer machine（开发者机器）、server machine（服务器）和专用 MySQL 服务器机。选择 server machine，因为它具有中等负载，非常适合像你这样想要学习更多 MySQL 的初学者。developer machine 使用内存极少，可能无法让你充分利用内存。另一方面，MySQL server machine 是为数据库程序员或全职用户准备的。它将使用电脑中所有的可用内存，因此不适合你。

### 选择数据库用途

对于数据库用途，有三个选择：multifunctional database（多功能数据库）、事务型数据库（transactional database）和非事务型数据库（non-transactional database）。选择多功能数据库，因为你的目的是通用用途。事务型和非事务型用于更特定的目的。点击框底部的“next”按钮。

### 选择 innodb 驱动器

如果你不想使用默认设置，可以从电脑中选择存储 `innodb` 数据的驱动器。选择你喜欢的驱动器并点击“next”。

### 设置服务器并发连接数

这将指示同时连接到服务器的用户数量。选项包括支持 OLAP、在线事务处理（OLTP）以及手动设置。建议你选择 OLAP 选项，因为你不需要高并发连接。OLTP 适用于高负载服务器，而手动设置则可以现在设置。

### 设置网络选项

通过勾选前面的小框来启用 TCP/IP 网络。在下方添加你的端口号，并勾选小框以启用设置服务器 SQL 模式。点击“next”。

### 选择默认字符集

最推荐的是标准字符集，因为它适用于英语和其他语言。它也是英语的默认设置。另外两个选项，即多语言支持和手动默认字符集，最适合非英语语言的用户。勾选标准字符集的小圆圈并点击“next”。

### 设置 windows 选项

勾选显示的两个选项：install as windows server（作为 windows 服务安装）和将 `bin` 目录添加到 windows 路径。这将允许你从命令行操作 MySQL。选择作为 windows 服务将自动显示服务名称。服务名称下方的小框也必须勾选。点击“next”。

### 设置安全选项

设置你的密码。框将指示你输入密码的地方。点击“next”。

### 执行你的配置

你只需点击“execute”（执行），你的电脑将根据你的规范自动进行配置。一旦配置完成且所有框都已勾选，点击“finish”。

### 设置验证过程

进入开始菜单，输入 `cmd` 并按回车。这将带你进入命令行面板。输入以下：

```
mysql -u root -p
```

按回车。注意 `mysql` 和 `-u` 之间有空格，`-u` 和 `root` 之间有空格，`root` 和 `-p` 之间也有空格。命令行面板将提示密码。输入你的密码并按回车。将出现 MySQL 提示符。你可以输入任何 SQL 命令来显示数据库。记得在 SQL 语句结束添加分号。

好了，你的控制面板已打开。

恭喜你！！你成功地在机器上安装并配置了 mysql。现在是时候行动了。

使用你的 mysql 可以激励你学习更多其他相关的应用程序，如 php 和类似产品。

重要的是，你首先需要学习 sql 的基础知识。

你可以开始学习的一些命令：

![Image00041.jpg](img/Image00041.jpeg)

现在是时候让我们深入学习使用这种编程语言可以做的有趣事情了。我们将查看在处理 sql 语言时可以执行的一些命令，以及我们如何搜索数据库并尽可能查看里面包含哪些信息。在本章中，我们将查看如何使用 sql，以及一些可以使用来满足我们需求的基础命令。

这些命令非常有帮助，因为它们会让你更容易操作数据库中我们需要的不同部分。我们会其中一些命令是很容易操作的，然后我们可以转向一些更困难、更复杂的命令，这样我们就能看到处理这种语言时展现出的威力。

当你需要学习 sql 中提供的一些更基础的命令时，你会发现处理它们的最好方法是将它们划分为六个独立的类别。所有这些类别都基于你可以在所选系统内部它们的用途。以下是 sql 语言中可以使用的六种命令类别，将帮助你完成代码任务。

### 数据定义命令

我们将查看的第一类命令被称为 `ddl`，即数据定义语言（data definition language）。这是 sql 语言内部的一个方面，它可以让我们在按照意愿的方式进行安排之前，更容易在数据库中生成对象。例如，你将可以使用 sql 系统的这部分来帮助我们在创建的表中删除或添加对象。这里与 `ddl` 类别一起的一些不同命令包括：

- `drop view`（删除视图）
- `drop index`（删除索引）
- `Alter the index`（修改索引）
- `Create the index`（创建索引）
- `Alter the table in some manner`（以某种方式修改表）
- `Create the table`（创建表）
- `Drop the table`（删除表）

### 数据操作语言

我们在这里查看的第二个部分被称为 `dml`，即数据操作语言（data manipulation language）。这是在我们想要修改正在使用的数据库中找到对象的某些信息时可以使用的 sql 方面。这将使得删除对象、更新这些对象或在数据库中插入新内容变得更容易。当我们确保对数据库中信息的正确更改被添加，而无需为该数据库创建表的新部分时，这将为我们提供很大的自由。

### 数据查询语言

现在我们需要转向数据查询语言，或者你最可能听它被称为 `dql`。这种语言将是你通过 sql 看到的最强大的方面之一，特别是当你为业务使用一个更现代的系统时。

这一个会很棒，因为你只需要处理一个简单的命令就可以从数据库中选择你想要的内容，命令就是 `select` 命令。你可以使用 `select` 命令在任何关系型数据库需要时运行某些查询。如果你希望输出的结果更详细，则可以通过并添加一些选项或子句来让这一切顺利运行。

### 数据控制语言

列表中的下一个是 `dcl`，即数据控制语言（data control language）。当你想要控制谁可以使用该数据库或谁可以访问该数据库时，你可以随时选择使用这个命令。`dcl` 命令在某些情况下用于生成与访问权限相关的数据库对象。如果你想控制访问访问员，这是一好事，这包括：

- `Revoke`（撤销权限）
- `Grant`（授权）

### 数据命令

当你需要学习 sql 中提供的一些更基础的命令时，你会发现处理它们的最好方法是将它们划分为六个独立的类别。所有这些类别都基于你可以在所选系统内部它们的用途。以下是 sql 语言中可以使用的六种命令类别，将帮助你完成代码任务。

- `Drop view`（删除视图）
- `Drop index`（删除索引）
- `Alter the index`（修改索引）
- `Create the index`（创建索引）
- `Alter table in some manner`（以某种方式修改表）
- `Create table`（创建表）
- `Drop table`（删除表）

例如，假设我们要为工资低于 3000 的员工发放 2 个月的奖金，而为工资高于此标准的员工发放 1 个月的奖金？

为了实现这一点，我们需要使用控制流工具。这些工具包括 `if`、`case` 和循环语句。

在本节中，我们将使用许多示例来解释所讨论的概念。

准备好了吗？

# If statement

让我们从 `if` 语句开始。`if` 语句的语法如下：

```sql
If condition 1 is met then do task a;
Else if condition 2 is met then do task b;
Else if condition 3 is met then do task c;
Else do task z;
End if;
```

`if` 语句首先检查第一个条件是否满足。如果满足，它将执行任务 a。如果不满足，它将移动到第一个 `else if` 语句。如果该条件满足，将执行任务 b。如果不满足，它将继续向下检查 `else if` 语句，直到找到满足的条件。如果没有条件被满足，它将执行任务 z。

可以根据需要包含任意数量的 `else if` 语句。

此外，`else if` 和 `else` 语句都是可选的。如果没有其他条件需要检查，你不需要包含它们。

然而，如果你省略了 `else` 语句，并且存在未被任何 `if` 和 `else if` 语句满足的情况，`mysql` 将向你返回错误。

现在让我们来看 `if` 语句的一些示例。

## Example 1

```sql
Delimiter $$
Create function if_demo_a(x int) returns varchar(255) deterministic
Begin
If x > 0 then return ‘x is positive,’;
Else if x = 0 then return ‘x is zero’;
Else return ‘x is negative,’;
End if;
End $$
Delimiter;
```

这个 `if` 语句首先检查输入 `(x)` 是否大于零。如果大于，它返回‘x is positive’。

如果不大于，它检查 `x` 是否等于零。如果等于，它返回‘x is zero’。

如果前两个条件都不满足，它将移动到 `else` 语句并返回‘ x is negative,’。

要运行此函数，我们写道：

```sql
Select if_demo_a(2);
```

我们将得到‘x is positive’。

如果我们将输入从 2 改为 0 或 -1，我们将分别得到‘x is zero’和‘x is negative,’。

## Example 2

```sql
Delimiter $$
Create function if_demo_b(x int) returns varchar(255) deterministic
Begin
If x > 0 then return ‘x is positive,’;
Else if x = 0 then return ‘x is zero’;
End if;
End $$
Delimiter;
```

这个示例与上一个相似，但我们省略了 `else` 语句。如果我们现在运行该函数，将得到以下输出：

```sql
Select if_demo_b(2);
```

Output:
X is positive,

```sql
Select if_demo_b(-1);
```

Output:
Error code,: 1321. function if_demo_b ended without return

你可以看到，如果我们向函数传递一个它无法处理的值（在本例中为负数），函数将返回错误。

# Case statement

接下来，让我们转向 `case` 语句。`case` 语句与 `if` 语句非常相似，通常可以互换使用。在大多数情况下，选择 `if` 还是 `case` 取决个人偏好。

语法为：

```sql
Case case_variable
When value_1 then task a;
When value_2 then task b;
…
Else do task z;
End case;
```

或者

```sql
Case
When condition 1 is met then task a;
When condition 2 is met then task b;
…
Else do task z;
End case;
```

让我们来看一些示例。

### Example 1

```sql
Delimiter $$
Create function case_demo_a(x int) returns varchar(255) deterministic
Begin
Case x
When 1 then return ‘x is 1’;
When 2 then return ‘x is 2’;
Else return ‘x neither 1 nor 2’;
End case;
End $$
Delimiter;
```

调用函数：

```sql
Select case_demo_a(1);
```

Output:

X is 1

```sql
Select case_demo_a(5);
```

Output:

X neither 1 nor 2

### Example 2



```sql
Delimiter $$
Create function case_demo_b(x int) returns varchar(255) deterministic
Begin
Case
When x > 0 then return ‘x is positive,’;
When x = 0 then return ‘x is zero’;
Else return ‘x is negative,’;
End case;
End $$
Delimiter;
```

这第二个示例使用了第二种语法，并测试`x`的范围而不是单个值。

调用函数：

```sql
Select case_demo_b(1);
```

Output:

X is positive,

```sql
Select case_demo_b(-1);
```

Output:

X is negative,

## While statement

下一个控制语句是`while`语句。该语句允许在条件有效时重复执行任务。

语法为：

```sql
[name of while statement] while condition is true do
Some tasks
End while;
```

### Example

```sql
Delimiter $$
Create function while_demo(x int, y int) returns varchar(255) deterministic
Begin
Declare z varchar(255);
Set z = ‘’
while_example: while x<y do
Set x = x + 1;
Set z = concat(z, x);
End while;
Return z;
End $$
Delimiter;
```

在这里，我们首先声明了一个变量`z`并将其初始化为空字符串（空字符串是一个字符串）。

接下来，我们声明了一个`while`语句，并标记为`while_example`。

接下来，`while`条件检查`x`是否小于`y`（`x`和`y`都是函数的输入参数）。当`x`小于`y`时，`while`语句执行以下操作：

首先，它将`x`加 1。

接着，它使用`concat()`函数将结果连接到`z`。

记住`concat()`是一个连接两个字符串的内置函数。如果值中的任何一个是数字，它会在连接之前将其转换为字符串。在`while`语句之后，我们简单返回`z`的值。

如果我们使用以下语句运行函数：

```sql
Select while_demo(1, 5);
```

你将得到输出 2345。这是因为循环开始，`x = 1` `y = 5`，`while`语句将`x`加 1（现在`x = 2`）并将结果连接到`z`。`z`变为‘2’。

接下来，循环重复。它将`x`加 1（现在`x = 3`）并将结果连接到`z`。`z`变为‘23’。

将`x`加 1 和结果连接到`z`的任务重复执行，直到`x < y`条件不再成立。

## Repeat statement

接下来，让我们看看`repeat`语句。`repeat`语句也用于执行任务，直到满足停止条件。

语法为：

```sql
Repeat
Do some tasks
Until stop condition
End repeat;
```

### Example

```sql
Delimiter $$
Create function repeat_demo(x int, y int) returns varchar(255) deterministic
Begin
Declare z varchar(255);
Set z = ‘’
Repeat
Set x = x + 1;
Set z = concat(z, x);
Until x>=y
End repeat;
Return z;
End $$
Delimiter;
```

这个`repeat`语句重复两个任务（`set x = x + 1`和`set z = concat(z, x)`），直到满足`x >= y`条件。

如果我们使用以下语句运行函数：

```sql
Select repeat_demo(1, 5);
```

你将得到与之前的`while`语句相同的输出：2345

区别在于`repeat`语句在检查条件*之前*执行任务，而`while`语句在执行任务*之前*检查条件。如果条件一开始为假，`repeat`语句仍至少执行一次，而`while`语句可能完全不执行。

## Leave statement

下一个控制语句是`leave`语句。该语句用于提前退出循环或块。语法为：

```sql
Leave label_name;
```

使用`leave`语句必须有一个标签。

### Example

```sql
Delimiter $$
Create function leave_demo(x int, y int) returns varchar(255) deterministic
Begin
Declare z varchar(255);
Set z = ‘’
loop_label: while x<y do
Set x = x + 1;
If x = 3 then
Leave loop_label;
End if;
Set z = concat(z, x);
End while;
Return z;
End $$
Delimiter;
```

在这个示例中，我们有一个标记为`loop_label`的`while`循环。在循环内部，如果`x`达到 3，就会调用`leave`语句，立即退出`loop_label`循环。

如果我们运行此函数：

```sql
Select leave_demo(1, 5);
```

Output:

23

注意当`x`达到 3 时循环停止，尽管`y`为 5。

## Continue statement

`next`语句用于跳过循环当前迭代的剩余部分并进入下一次迭代。语法为：

```sql
Continue label_name;
```

### Example

```sql
Delimiter $$
Create function next_demo(x int, y int) returns varchar(255) deterministic
Begin
Declare z varchar(255);
Set z = ‘’
loop_label: while x<y do
Set x = x + 1;
If x = 3 then
Continue loop_label;
End if;
Set z = concat(z, x);
End while;
Return z;
End $$
Delimiter;
```

在这个示例中，当`x`达到 3 时，调用`next`语句，跳过循环的剩余部分（`Set z = concat(z, x)`部分）并进入循环的下一次迭代。

如果我们运行此函数：

```sql
Select next_demo(1, 5);
```

Output:

245

注意值 3 没有被添加到`z`中，因为`next`语句跳过了循环的循环。

## Handler statement

`handler`语句用于定义发生特定错误时采取的操作。语法为：

```sql
Handler condition DO action;
```

### Example

```sql
Delimiter $$
Create function handler_demo() returns varchar(255) deterministic
Begin
Declare msg varchar(255);
DECLARE HANDLER FOR SQLEXCEPTION SET msg = 'An error occurred';
-- 可能会触发错误的代码
SELECT 1 / 0;
Return msg;
End $$
Delimiter;
```

在这个示例中，定义的`handler`用于捕获任何`SQLEXCEPTION`。当发生错误（如除以零）时，触发处理器，将`msg`设置为‘An error occurred’，函数返回该消息而不是崩溃。

## Declare statement

`declare`语句用于在块或函数中定义变量。语法为：

```sql
Declare variable_name datatype [DEFAULT value];
```

### Example

```sql
Delimiter $$
Create function declare_demo() returns int
Begin
Declare myvar int DEFAULT 10;
Declare othervar int;
Set othervar = myvar + 20;
Return othervar;
End $$
Delimiter;
```

此外，另一个重要的区别是`repeat`语句始终至少执行一次任务。这是因为检查（例如，直到`x>=y`）是在任务完成后完成的。

因此，如果你运行以下语句：

```sql
Select repeat_demo(5, 1);
```

你将得到结果 6，因为即使`repeat`条件（直到`x>=y`）已经满足，`repeat`语句内部的两个任务至少执行一次，因为检查是在任务完成后完成的。

清楚了吗？

## 循环语句

最后但最重要的，让我们来看看循环语句。此语句与`while`和`repeat`语句非常相似，区别在于它没有用于退出循环的条件。

相反，我们使用`iterate`或`leave`关键字来退出循环。

循环语句的语法为：

```sql
[name, of loop statement :] loop
    Some tasks
    End loop;
```

让我们来看几个例子。

### 示例 1

```sql
DELIMITER $$
CREATE FUNCTION loop_demo_a(x int, y int) RETURNS varchar(255) DETERMINISTIC
BEGIN
    DECLARE z varchar(255);
    SET z = '';
    simple_loop: LOOP
        SET x = x + 1;
        IF x > y THEN
            LEAVE simple_loop;
        END IF;
        SET z = concat(z, x);
    END LOOP;
    RETURN z;
END $$
DELIMITER ;
```

在这里，我们定义了一个名为`simple_loop`的循环。为循环语句提供名称通常是必要的，因为之后我们需要该名称来使用`leave`或`iterate`语句。

在循环内部，我们执行以下操作：

首先，我们将`x`的值加 1。接下来，我们检查`x`是否大于`y`。如果是，我们就离开循环。

要退出循环，我们写：

```sql
Leave simple_loop;
```

`leave`是 MySQL 中的一个关键字，表示我们要退出循环。我们必须提供要退出的循环名称。在示例中，我们正在退出`simple_loop`。

如果没有满足`leave`条件，我们将留在循环中并将`z`与`x`拼接。

如果你现在使用以下语句运行函数：

```sql
Select loop_demo_a(1, 5);
```

你将得到输出 2345。

### 示例 2

除了使用`leave`关键字外，我们还可以使用`iterate`关键字。与完全退出循环的`leave`关键字相比，`iterate`关键字仅跳过循环的一次迭代。

让我们来看一个例子：

```sql
DELIMITER $$
CREATE FUNCTION loop_demo_b(x int, y int) RETURNS varchar(255) DETERMINISTIC
BEGIN
    DECLARE z varchar(255);
    SET z = '';
    simple_loop: LOOP
        SET x = x + 1;
        IF x = 3 THEN ITERATE simple_loop;
        ELSEIF x > y THEN LEAVE simple_loop;
        END IF;
        SET z = concat(z, x);
    END LOOP;
    RETURN z;
END $$
DELIMITER ;
```

在这里，我们在循环语句中又增加了一个`if`条件。这个`if`条件使用了`iterate`关键字。

如果你使用以下语句运行函数：

```sql
Select loop_demo_b(1, 5);
```

你将得到输出 245。因为条件的存在，迭代`x = 3`被跳过了：

```sql
If x = 3 then iterate simple_loop;
```

清楚了吗？很好！通过这个例子，我们已经到了本章的末。

## if 语句

在 Python 中，你可以使用各种语句。然而，你必须确保遵循语法规则和缩进。规则之一是在进入代码时，在`if`和`else`语句后提供缩进。只需按一次 Tab 键即可提供缩进。无论如何，程序都会帮助你确定语法中的错误。如果是错误，它将显示错误以及问题所在。如果你在语言中迷失了，也可以按键寻求帮助。因此，请放松并享受体验。

## 函数

`if-else`语句用于执行代码，通常用于比较值或确定正确性。当条件为`true`时，执行`if`；当条件为`false`时，执行`else`。通用代码如下：

```python
if expression:
    statement
else:
    statement
```

示例：首先分配一个基础语句。假设你正在教大一学生化学，并希望鼓励他们参加你的辅导。你可以编写这段 Python 代码：

```python
Hours = float(input('how many hours can you allot for chemistry?'))
if hours < 1:
    print('you need more time to study.')
else:
    print('great! keep it up!')
print('chemistry needs more of your time.')
```

## While 语句

`while`语句是主要的循环语句，大多数用于需要简单迭代的地方。它的结构如下：

```python
counter = 10

while counter > 0:

    print(counter)

    counter = counter - 1

print('backward counting from 10 to 1')
```



这个简单的`while`循环不断检查`while`条件，直到条件变为`false`为止。在条件变为`false`之前，每次循环都会通过循环体。在条件变为`false`后，解释器恢复最近的活动，并继续执行循环之后的程序语句。下图说明了`while`控制的流程。

![Image00042.jpg](img/Image0042.jpeg)

## Case 语句

Ruby 语言在组织中常用于 Web 应用开发。Ruby on Rails 是一个允许快速开发的框架，使业务团队专注于其他过程而不是从零开始编写函数。该框架提供了一个被称为 MVC 结构（模型-视图-控制器）的分隔器。MVC 为分离用户界面和业务提供了支持。

另一方面，Python 拥有最流行的 MVC 框架，用于 Web 开发的 Django。此外，Python 在 Web 应用领域之外也很有用。例如，`pandas`库有助于数据准备。其他库如`numpy`和`stats-model`在这种情况下也是支持。`matplotlib`是用于数据可视化的强大 Python 库。`tensorflow`以机器学习任务和项目而闻名。此外，`scipy`是 Python 的另一个开源库，用于科学计算和解决曾让工程学生流汗的数学函数。

MySQL 的开发始于 1994 年，科学家 David Axmark 和 Michael Wakefield 被誉为 1995 年该 DBMS 首个内部版本的发布者。该 DBMS 的 Windows 版本出现得较晚，是在 1998 年。最初，MySQL 项目由 MySQL AB 所有。2008 年，项目所有权转移到太阳微系统（Sun Microsystems），随后发布了 MySQL 5.1 版本。该数据库管理系统的主要特性包括：

- 灵活性
- 高可用
- 可扩展性
- 高性能
- Web 优势
- 健壮的事务支持
- 数据仓库优势
- 全面的应用开发
- 强力保护
- 开源自由
- 管理方便
- 最低的总拥有成本
- 24x7 全候支持

### MS SQL Server

微软以 MS SQL Server 的形式推出了其关系型数据库管理系统，使用 ANSI SQL 和`T-SQL`作为其主要查询语言。Sybase 在 1987 年发布了该 DBMS 的第一个版本。Sybase 与 Aston-Tate 以及微软合作将`SQL Server`移植到`OS/2`，并于 1989 年发布了`SQL Server` 1.0，随后 Aston-Tate 退出了 SQL 开发，微软发布了`SQL Server` 2000。MS SQL Server 的主要特性包括：

- 高可用
- 数据库快照
- 高性能
- 数据库镜像
- 服务代理 (Service broker)
- CLR 集成
- 排名函数
- DDL 触发器
- XML 集成
- 基于行版本的隔离级别
- 数据库邮件
- Try…catch

### Oracle

Oracle 是目前市场上最流行、最大的多用户 DBMS 之一。如名所示，Oracle 由“Oracle 公司”（Oracle Corporation）拥有并创建。Oracle 的核心特性在于它能够高效管理资源，这些资源是许多客户端通过网络访问的数据库。

考虑到 Oracle 的基础架构，它被认为最适合客户端服务器计算。此外，它支持 Unix、Windows、Linux 和 macOS 等许多平台。Oracle 的起源追溯到 1977 年，当时 Ed Oats、Bob Miner 和 Larry Ellison 创立了“软件开发实验室”（Software Development Laboratory）。当 2.0 版本于 1979 年发布时，Oracle 成为第一个商业 SQL 数据库管理系统。

同年，公司名称更改为 Relational Software Inc. (RSI)。由于该公司进行的大部分开发都与 Oracle 有关，其名称在 1982 年再次更改，并获得了现在的身份 Oracle 公司（Oracle Corporation）。

在随后的几年里，Oracle 获得了其多功能特性。例如，跨平台的 Oracle 3.0 版本于 1983 年发布，而 4.0 和 5.0 版本中加入了并发控制等功能。Oracle 的主要特性包括：

- 读取一致性
- 并发
- 数据库静止 (Quiesce database)
- 锁定机制
- 自管理数据库
- 可移植性
- ASM
- `SQL*Plus`
- 资源管理器
- 调度器
- 物化视图
- 数据仓库
- 表格压缩
- 位图索引
- 分析型 SQL
- 并行执行
- 分区
- 数据挖掘

Access 是微软的一款基础数据库管理系统，用于入门，这使其成为最受欢迎的产品之一。它受欢迎的其他原因还包括价格低廉以及为小型项目创建健壮解决方案的能力。此外，微软旗舰性的高度直观且易于使用的图形界面增加了该产品的声誉。

这里需要提到的是 Access 使用了`T-SQL`，这是 SQL 的变体。这种 SQL 方言专门用于 Access 数据库引擎的数据库操作。Access 的第一个版本于 1992 年发布，多年来经历了许多改进和新增。目前，Access 作为 MS Office 产品的一部分提供。该管理系统的主要特性包括：Access 允许用户创建表单、报告和查询。此外，它支持从 Oracle、Excel 等格式导入数据并导出到特殊的`mdb`格式。该工具还支持 SQL Server，并通过`ADO`或`DAO`进行连接。需要注意的是，Access 并不是客户端服务器数据库，因此它不实现存储过程、事务日志或触发器。它实际上是一个文件数据库。

### SQL 工具类型

市场上有多种类型的 SQL 工具。在选择这些工具时，需要考虑多种因素，包括：

- 你想要管理的：例如，为了管理 SQL Server 实例，建议选择 Azure Data Studio。
- 数据库代码的创建和维护：你需要 SQL Server Data Tools (SSDT)。
- 使用命令行查询 SQL Server：你可以选择`mysqlcli`。
- 编写 T-SQL 脚本：你应该使用 Visual Studio Code 和 MySQL 扩展。

本节旨在评估 SQL Server 管理中常用的工具如下：

#### Interbase

这是一种快速且嵌入的 SQL 数据库工具，具有企业级的安全性、灾难恢复能力以及顺畅处理变更的能力。工具具有以下特性：

- 遵循 SQL 标准：这些工具兼容所有 SQL 标准，识别 Unicode，并适用于任何字符。
- 提供多 Unicode、实时告警和更改跟踪。
- 轻量级：它适用于当前的 CPU，并适用于各种系统。
- 快速恢复：适用于快速灾难恢复。

#### DbForge Studio for SQL Server

这是最好的 IDE 工具之一，执行多种功能，包括服务器管理、管理、数据报告、分析等。该工具具有以下特性：

- 能够管理数据库
- 提供高质量的代码支持
- 高质量的 SQL Server 报告
- 保护：它提供了最佳的信息保护

#### Dbwatch

该工具提供全面的数据库管理支持，适用于 Oracle、SQL Server、Azure 等多种数据库。该工具用于不同环境（包括混合和云）的维护工作。它具有以下特点：

- 协助监控性能并生成重要报告。
- 实现 SQL Server 的常规内存最小化。
- 轻量级：它适用于当前的 CPU，并适用于各种系统。
- 快速恢复：适用于快速灾难恢复。

这是提供 SQL 数据库监控服务的最佳工具之一。它可以处理不断增长的业务工作负载。由于对高性能数据的需求日益增长，许多公司正在使用此工具。`sql entry`具有以下特性：

- 协助性能指标的收集和展示。
- 分析和调优能力——该工具具备启用 SQL 查询分析和高级调优的功能。
- 它被评为最佳 DBA 解决方案。

## Admin

这是一个提供各种解决方案的数据管理工具。这些解决方案包括数据库、表、列、关系等的管理。该工具以单个 PHP 文件的形式出售，并支持不同系统上的各种数据库，包括 ms sql、oracle 和`mysql`。你可以下载文件形式的各种版本。`Admin`具有各种特性，包括：

- 执行数据表列表操作并具有多种功能，包括排序、搜索等。
- 它有多种自定义选项。
- 指示过程并销毁它们。

## Dbcompare

这是一个易于使用的数据库比较设备，可以对数据库结构进行分析并提供见解。该工具允许你比较不同的对象，包括表、外键、角色等。`Dbcompare`具有不同的功能，如：

- 定期对比各种数据库结构。
- 为评估提供不同的选择。
- 它内置了可视化树，用于自发地表示差异。

## Ms sql manager lite for sql server

此工具用于创建 SQL 数据库对象并允许执行各种编辑任务。该工具拥有最好的界面并加载了实用的功能。它可以替代`ssms`。

- 支持特性——该工具支持多种 SQL 特性，包括 azure、sql database、unicode 等。
- 提供查询构建工具——该工具为查询开发提供了视觉化和文本设备。
- 比较——该数据库工具有助于比较和同步各种数据库结构。
- 内置 SQL 调试器——该工具带有一个 SQL 调试器，可以跟踪进程、函数和脚本。

## Firebird

这是一个高效的 SQL 工具，在 Windows 和 Linux 上均运行良好。Firebird 具有各种特性，包括：

- 过程完全支持——该工具对各种过程提供完全支持，包括标准事务、多种访问方式、支持增量备份等。
- 复杂的应用——该工具应用了最新技术，如`fb25`和`fb30`。这意味着它提供了高质量的服务。
- 云支持——该工具可以识别云基础设施。

## Squirrel sql

此工具支持 Java 数据库的管理。通过此工具，你可以查看 SQL 数据库并提供命令。该工具可在不同的数据库上运行，包括 ibm、sql、oracle 等。它的核心特性包括：

- 弹出菜单——通过此菜单，你可以执行编辑等各种功能。
- 对象树显示——这向你展示了季节窗口。
- 图表——它显示表的图形以及它们如何连接。

## Sqlite database browser

该工具开源，有助于创建和编辑数据库中的各种文件。`Sql database browser`具有各种特性，包括：

- 数据库的创建和修改——通过此工具，你可以创建和编辑各种数据库、表等。
- SQL 命令——该工具有一个日志，显示已发布的所有 SQL 命令及其使用情况。
- 创建简单图表——该工具可以根据表中的数据绘制图表。

## Beaver

该工具开源，被数据库管理员用于支持`mysql`和 ibm 等数据库。该工具的主要作用是创建和修改 SQL 脚本、数据导出等。该工具具有各种特性，包括：

- 数据创建：创建和修改插件的能力——该工具提供了插件。

## Db visualize

这是一个开源的通用数据库工具，有助于管理 oracle、sybase 等数据库。该工具具有一个用于浏览对象的浏览器。它有助于对象的形成和修改。`db visualize`的核心特性包括：

- 特定对象的管理
- 模式（Schema）辅助
- 配合查询操作

当你设置好想要使用的查询时，你会发现你正在向已设置的数据库发送查询。你会发现有几种方法可以实现此操作，但`select`命令将是实现此操作的最佳选项之一，并能根据搜索立即返回我们所需的信息。例如，如果你正在处理一个包含所有待售产品的表，你可以使用`select`命令来查找最畅销的产品或你当时拥有的产品。结果将直接显示在数据库中存储的任何信息上，你会发现当我们谈论关系型数据库时，这些是正常完成的。

“数据库”一词的含义在过去的几十年里发生了巨大的变化，某些人将其指的是书籍或列表中包含的任何数量的项目。对其他人来说，它指的是结构化数据或记录的存储库，可以通过计算机系统访问。我们将关注第二个定义，它也包含了 sql。请记住，在这种情况下，记录指的是项的表示。例如，你正在经营自己的业务，因此你会为每个唯一的客户创建一个记录。这些记录将包含描述该对象的若干特征。例如，你可以包括名称、电话号码、地址等数据。

然而，数据库并不仅仅包含数据。它还包含元数据，其目的是定义数据库内部的信息结构。为什么这很重要？因为如果你知道数据是如何组织的，你就可以访问、管理、维护和修改它。这意味着数据库是自描述的，因为它包含了关于数据对象之间连接的信息。元数据被保留在所谓的“数据字典”中。该词典描述了数据库的组成部分，即表、行、列等。顺便提一下，你应该知道扁文件系统不包含元数据。这意味着处理这些文件的程序需要具有某种形式的等效集成。

数据库的大小也根据其包含的记录数量而异。例如，你可以拥有从几十个到数百万个不等的数据对象。目前，你不必担心任何此类限制。但是，数据库可以用三种不同的方式分类：

个人数据库是最小的。它们存储在用户的个人计算机上，以基本数据结构为特征。

另一方面，群组数据库要复杂得多。它们旨在供部门或团队使用，这意味着它们包含的数据比个人数据库要多得多。这意味着它们还需要能够同时从多个设备进行访问。

最后，我们还有企业版数据库。它们规模庞大、复杂，需要最可靠的设备来安全地存储和维护。

正如你所看到的，你可以通过三个属性对数据库进行分类：它的大小、有多少人需要访问它以及它需要什么种技术设备。

# 数据库管理系统

为了管理数据库以及任何访问它的的应用程序，我们需要使用数据库管理系统。请记住，数据库无非一个设计用于包含信息的结构。我们需要一个能够实际创建该结构并允许我们访问、维护或修改其中数据的工具。目前有许多此类程序，可以免费提供，也可以收取特定费用。

然而，并非所有数据管理系统都是同质的。你需要的系统取决于你的目标和需求。例如，某些程序设计用于在专业的企业级设备上运行并处理海量数据库；而另一些程序则设计用于在基础个人笔记本电脑上运行。但是，请记住，这些工具有时需要在运行不同操作系统的不同硬件设置上同时运行。此外，我们还要考虑云存储作为一种选项。如今，你可以通过亚马逊和微软等组织提供的服务获得公共在线存储。

云是你在任何技术领域经常听到的术语之一，由于如今许多企业对计算机处理能力和存储能力的需求巨大增长。你现在需要了解（如果你不知道的话）的是，云是计算机的集合，通过互联网向任何人提供其资源。这意味着任何人都可以从家里舒适地访问这些服务，而无需物理上连接到数据中心。在这种情况下，具有云能力的数据库管理系统可以为你提供远程管理数据库的功能。

数据库管理系统确保无论系统类型和数据库大小如何，用户与系统之间的数据流始终保持一致。

# 数据库类型

最早的数据库模型是基于分级结构的构建的。这导致了许多问题，由于缺乏灵活性，此类数据库极难修改和维护。结构性问题和各种冗余问题导致了网络型数据库的发展。它的目的是消除此类缺陷。它们确实提供了几乎没有冗余的优势；然而，为了实现这种特性，必须做出另一个牺牲。网络模型数据库的结构非常复杂，因此导致了另一组问题。

随着关系型数据库的发展，这些技术问题很快得到了解决方案。其结构简单，最小冗余是其主要特征之一。这种新类型的创建，其目的是将关系型数据库变为革命性的东西，并让其他模型变得无足。

# 关系型数据库

有了新类型的数据库，就需要一种新的数据库管理系统。这就是 Oracle 的诞生：一个小型初创公司给出的新答案。此时，关系型数据库成为主流。这使得在不改变其他地方使用的程序设计的情况下修改该模型的结构成为可能。例如，要在数据库内部创建更多列，你只需要添加它们，而无需任何耗时的修改。依赖于数据库的应用程序不需要任何更改。

另一个强大的优势是某些数据可以存储在一个表中，而另一些数据可以存储在另一个表中。这两个表不需要以任何方式连接；因此，你可以更改一个表的信息而不会对另一个表产生负面影响。关系模型和对象模型提供了一系列优势。幸运的是，当时的开发者考虑了从对象数据库的力量中获利的可能性，以及关系模型提供的兼容性。关系型数据库就是这样产生的：本质上，它利用了我们已经讨论的关系模型，并在此基础上增加了对象模型的功能。对象特性通过 SQL 实现，因此允许所有数据库管理系统适应并变为关系型数据库管理系统。请记住，它们仍然保留了与原始关系模型的兼容性。自 90 年代以来，随着编程技术和语言的不断发展，关系型数据库通过引入越来越多的对象特性逐渐扩展。然而，在这种数据库类型的核心，关系模型保持不变，尽管它在多年里受到了许多扩展。

关系型数据库的流行开始下降，转而采用我们今天使用的标准 SQL 数据库。现代问题需要对象特性才能提供的复杂 SQL 解决方案。

## 第 4 章：表

### 使用命令行创建第一个数据库和表

你也可以使用 SQL 命令和语句来创建数据库和表。对于 SQL Server Management Studio，情况同样适用，但命令和语句用于指示系统执行给的功能。要构建第一个数据库，你使用命令`select database (database_name)`并点击执行按钮来创建程序。因此，屏幕上的信息应该是“command(s) completed successfully”，显示你的数据库已创建。

要使用数据库，运行命令`use (database_name)`，这告诉查询窗口运行新的数据库程序。另一方面，创建一个新表涉及运行命令`create table (table_name)`。输入数据紧随命令`insert data into (table_name), values (table_name)`，并对你所有的数据集重复相同的过程。同样的方法允许查看你保存的数据，并包括格式命令`select * from (table_name)`。上述所有命令在操作不同的 SQL 数据库时都是关键命令。因此，学习每个 SQL 基础命令以从容执行程序是至关重要的。

### 创建表

以下是简单的步骤：

输入关键字`create table`

这些关键字将表达你的意图并引导你脑海中的操作。

### 创建表

示例：`create table`

输入表名

在你的`create table`关键字之后，添加表名。表名应该是具体的且唯一的，以便日后方便、快速地访问。

示例：`create table "table_name,"`

你的表名不能让任何人轻易猜到。你可以通过包含你的姓名缩字母和出生日期来实现这一点。例如，如果你的名字是 henry sheldon，出生日期是 1964 年 10 月 20 日，你可以将这些信息添加到表名中。

假设你想让你的表关于你网站的流量来源；你可以将表命名为`"traffic_hs2064"`。

请注意，所有的 SQL 语句必须以分号（`;`）结束。所有数据变量也必须包含在引号（ ” ）中。

示例：`create table traffic_hs2064`

在下一行添加左括号

括号将表示你想要创建的列的引入。

示例：`create table "table_name,"`

`(`

让我们将步骤应用于我们的特定示例中。

示例：`create table traffic_hs2064`

`(`

在某些情况下，并不使用括号。

### 添加第一个列名

你想给你的第一列起什么名字？这应该与你想为该表收集的数据或信息相关。始终用逗号分隔你的列定义。

示例：`create table "table_name,"`

`(`
`"column_name," "data type,"`

### 定义数据类型

在我们的示例中，该表的重点是你网站的流量来源。因此，你可以将第一列命名为`"country"`。

示例：`create table traffic_hs2064`

`(country`

## 根据数据添加更多列

如果你需要更多关于该表的数据，可以添加更多列；这取决于你。所以，如果你想再添加四列，你的 SQL 语句将如下所示。

示例：`create table "table_name,"`

`(`
`"column_name,1" "data type,"`
`"column_name,2" "data type,"`
`"column_name,3" "data type,"`
`"column_name,4" "data type,"`
`);`

假设你已经决定为第 2 列添加用于搜索网站的关键词，为第 3 列添加访问者在你网站上花费的分钟数，为第 4 列添加该人员访问的特定帖子。这是你的 SQL 语句的样子。

### 注意：

表名或列名必须以字母开头；后面可以跟数字、下划线或另一个字母。字符数不应超过 30 个。

你也可以使用`varchar`（可变字符）数据类型来帮助创建列。

常见的数据类型有：
- `Date` – 指定的日期或值
- `Number(size,)` – 你应该在左右括号内指定列数字的最大最大位数
- `Char(size,)` – 你应该在左右括号内指定固定长度的大小。
- `Varchar(size,)` – 你应该在左右括号内指定最大大小。这用于条目的变长长度。
- `Number(size, d)` – 这与`Number(size,)`类似，区别在于`d`代表数字右侧（从小数点开始）的最大数字位数。

因此，如果你想让你的列显示 10.21，你的数字类型将是：`Number(2,2)`

示例：`create table traffic_hs2064`

`(country varchar (40),`
`Key varchar (30),`
`Time number (2),`
`Post varchar (40));`

约束是应用于特定列的规则。如果你愿意，可以添加约束。最常见的约束是：
- `not null` – 表示列不应包含空白
- `unique` – 表示所有添加的条目必须是唯一的，且与列中的任何项目不重复。

总之，使用 SQL 语句创建表将从`create table`开始，加上`table name`、左括号、`column names`、`data type`（在每个列后添加逗号）、添加任何`constraints`。

### 删除表

使用适当的 SQL 语句可以轻松从数据库中删除表、行或列。这是你必须掌握的命令之一。

删除表的步骤如下：选择`delete`命令。在你的显示器上，选择`delete`命令并指定关键字。下载 MySQL 数据库和 MySQL 连接器可以方便你的操作。

SQL 专家可能会笑说这些步骤不应该包含在书中，但对于初学者来说，具体说明应该执行哪些步骤是关重要的。想象你正在学习一种新语言，例如，你就会明白我的意思。通过添加单词`from`和表名来指示你可以从哪个表执行此操作：`delete from "table_name,"`。

通过添加`where`指定特定的列或行。如果你没有指定`where`，所有的文件都将被删除，所以请确保你的语句是完整的。

示例：`delete from "table_name,"` `where column_name,`

因此，如果你想删除整个表，只需选择：`delete from "table_name,"` `where time = (10)`
`delete from traffic_hs2064` `where time = (5);`

通过添加必要的变量完成你的`delete`语句。

示例：`delete from "table_name,"` `where column_name,` 运算符 `"value,"` [或 `"column"`运算符 `"value,"];

从数据库中删除错误的表可能会导致问题，因此确保你输入了正确的 SQL 语句。

### 向表中插入数据

你可以通过以下步骤向现有表插入新数据：输入关键字`insert into`。选择关键字`insert into`。与 SQL 兼容的最常见程序是 Windows MySQL。你可以使用它向你的表插入数据。

添加表名。现在你可以添加表名了。确保它是正确的表。

示例：`insert into "table_name,"`

使用我们的表：示例 `insert into traffic_hs2064`

添加左括号。你现在可以在表名之后、列名之前添加左括号。记住在每个列后添加逗号。

示例：`insert into "table_name,"` `(`

使用我们自己的表：示例 `insert into traffic_hs2064` `(`

指定列。指定你打算插入数据的列。

示例：`insert into "table_name,"` `("column_name," ... "column_name,")`

用右括号关闭列。不要忘记添加右括号。这将指示你已相应地识别了列。

示例：`insert into "table_name,"` `("first_columnname," ... "last_columnname,")`

添加关键字`values`。values 关键字将帮助你的选择更具体。值的列表随其。这些值也必须包含在括号内。

示例：`insert into "table_name,"` `("first_columnname," ... "last_columnname,")` `values(first_value, ... last_value,)`

添加右括号。记得向你的 SQL 语句添加右括号。这将指示该列不再进一步延伸。

示例：`insert into "table_name,"` `("first_columnname," ... "last_columnname,")` `values(first_value, ... last_value);`

请注意，字符串必须包含在单引号中，而数字则不需要。

使用我们的示例表，你可以编写此 SQL 语句：

```sql



Example: `insert into "traffic_hs2064" (country, keyword, time) Values ('america', 'marketing', 10);`

你可以安全地插入更多数据，而不影响其他表。只需确保你正在使用正确的 SQL 命令或语句即可。

## 删除表 (Dropping a table)

你只需在键盘上敲击几下即可删除一个表。但在你决定删除表之前，请考虑一下如果以后需要它，你可能需要花费额外的时间来恢复。因此，请谨慎使用此命令。

删除表与删除表中的记录/数据不同。当你删除一个表时，你删除的是表的定义以及表中的所有记录/数据。

```sql
Example: drop table "table_name";
```

使用我们的表，SQL 语句如下：

```sql
Example: drop table traffic_hs2064;
```

只要你能够编写出正确的 SQL，删除表是非常简单的。

## 使用 `alter table` 查询 (Using the alter table query)

在某些情况下，你需要使用 `alter table` 命令。这在你需要编辑、删除或修改表和约束时。

该查询的基本 SQL 语句为：

```sql
Example: alter table "table_name" Add "column_name" data type;
```

你可以使用此基础表作为你的演示表：

`Traffic_hs2064`

![Image00043.jpg](img/Image00043.jpeg)

如果你的基础表是上面的表，并且你想添加另一个标记为 `city` 的列，你可以通过这种方式创建 SQL 查询：

```sql
Examples: alter table traffic_hs2064 Add city char(30);
```

输出的表将如下所示：

`Traffic_hs2064`

![Image00044.jpg](img/Image00044.jpeg)
![Image00045.jpg](img/Image00045.jpeg)

你也可以修改表以添加诸如非空（`not null`）之类的约束。

```sql
Example: alter table traffic_hs2064 Modify city not null;
```

这将修改所有非为空的条目。你也可以修改表以删除列，例如：

```sql
Example: alter table traffic_hs2064 drop column time;
```

使用第二个表执行此查询，结果表将是：

`Traffic_hs2064`

![Image00046.jpg](img/Image00046.jpeg)

你可以通过添加唯一约束（`unique constraint`）来修改表。你可以通过这种方式构建查询：

```sql
Example: alter table traffic_hs2064 Add constraint country unique;
```

除了这些用途外，`alter table` 还可以用于删除约束（`drop constraint`），例如：

```sql
Example: alter table traffic_hs2064 Drop constraint city;
```

以下是约束的示例：

**非空 (Not null)**：此约束表示存储表中的列中不应存在空值。

**检查 (Check)**：这将确保所有参数的值都符合标准。

**唯一 (Unique)**：这确保列中的所有值都是互不相同或唯一的。

**主键 (Primary key)**：这表示两个或多个列中的值必须同时不为空。

**外键 (Foreign key)**：这将确保不同表之间的列值相匹配。

**默认 (Default)**：列有一个指定的默认值。这可能显示为空白或显示为空。

确保妥善使用这些约束，以充分发挥你的 SQL 查询的作用。

**表 (Table)**：表是关系型数据库管理系统（RDBMS）用于存储数据的对象。通常，表是包含数据条目的行和列的集合。这是数据存储最的形式。下面是表的示例。该表包含公司员工的数据。数据字段包括 ID 号、姓名、性别工资。

![Image00047.jpg](img/Image00047.jpeg)

## 第 5 章：学习函数 (learning function)

### 内置函数与计算 (Built-in functions & calculations)

关于 SQL，内置函数可以定义为编程的一部分，它接受零或任何其他输入并返回答案。内置函数有不同的角色。这些包括执行计算、获取系统值以及在文本数据处理中的应用。这部分旨在检查各种 SQL 内置函数、函数分类、函数的优缺点以及内置函数的类型。

### SQL 函数类型 (Types of sql functions)

SQL 函数分为两类：聚合函数和标量函数。配合 `group by` 使用，聚合函数在不同的记录上运行并提供摘要。而标量函数则独立地运行在不同的记录上。

如下：

**单行函数 (Single row functions)**：它们为任何查询表提供单行返回。它们出现在 `select` 列表中、以 `where` 子句开头以及其他。单行函数的示例包括 `numeric_`、`data_mining`、`date_time_`、`conversion_` 和 `xml_functions`。

**聚合函数 (Aggregate function)**：应用此类函数时，你会看到基于不同行的单行返回。聚合函数存在于 `select` 列表、`order by` 和 `having` 子句中。它们与 `group by` 子句和 `select` 语句配合使用。其中许多函数不关注空值。空值通常会被忽略。

**分析函数 (Analytic function)**：它们用于计算位于特定行组的聚合值。当你运行此函数时，它会返回多行。分析函数是查询中最后出现的。分析函数的示例包括 `analytic` 和 `order_by`。

**模型函数 (Model functions)**：这些出现在 `select` 语句中。模型函数的示例包括 `previous`。

**用户定义函数 (User-defined function)**：它们用于 SQL 以提供通常出现在表达式处的函数。例如，你可以在 `select` 列表中找到它们。

**SQL 计数函数 (Sql count function)**：它用于提供表的行数。

### 函数分类 (Categories of functions)

函数根据它们在数据库中扮演的角色进行分类。以下是一些范畴：

**聚合函数 (Aggregate functions)**：它们对一组特定的值进行计算并交付单个值。聚合值用于 `select` 列表和 `having` 子句。聚合函数被认为是确定性的。这意味着它们在相同输入值上运行时会返回相同的值。

**分析函数 (Analytic function)**：它们根据一组行计算聚合值。它们为不同的组返回多行。分析函数可用于执行不同的计算，如运行总计、百分比等。

**排名函数 (Ranking functions)**：它们为每个分区行提供排名值。这类类型的函数被认为是非确定性的。

**结果集函数 (ResultSet functions)**：它们用于返回一个可以应用的对象。

SQL Server 中存在的函数要么是确定性的，要么是非确定性的。确定性函数在执行时提供相同的答案。相反，非确定性函数在应用时会产生不同的结果。

### SQL 计算

SQL Server 内置了各种数学函数。这些函数可以分为 4 大类，包括科学和三角函数、舍入函数、符号函数和随机数。虽然每类中都有许多数学函数，但并不是所有的都会经常使用。下面重点介绍并解释了这些类别：

### 科学和三角函数

在此类别下，有多个子类。包括 `pi`、`sqrt` 和 `square`。`pi` 函数用于计算圆的周长和面积。工作原理如下：

```sql
select 2 * 10
```

`sqrt` 表示平方根。该函数最常用。它能够识别任何可以转换为 `float` 数据类型的数字。例如：

```sql
select sqrt (36)
```

返回 6。`square` 意味着将任何数字乘以自身。这里勾股定理的概念非常有用。这意味着 `a²+b²=c²`。这可以通过以下方式实现：

```sql
select sqrt (square (a) + square(b)) as c
```

### 舍入函数

在此类下，有不同的类别，包括 `ceiling` 和 `floor`。在处理浮点数或小数时，`ceiling` 函数很有帮助。你的目标是找到最高或最低的整数。`ceiling` 是最大的整数，而 `floor` 代表最小的整数。当你想要将数字舍入到特定的位数时，则应用 `round` 函数。这表示为 `round (value, number of decimal places)`。

### 符号

某些情况下你需要获取数字的绝对值。例如 -7 的绝对值是 7。绝对值不包含任何符号。为了帮助你完成此任务，使用 `abs` 函数是必须的。

### `Cos (x)`

此函数将弧度表示的角度作为参数。操作后，你会得到一个余弦值。

### `Sin (x)`

此函数识别弧度角。计算后，它返回一个正弦值。

### `Sign`

当你需要负值、正值或零值时，可以使用 `sign` 函数。

### SQL 内置函数和数学应用的重要性

内置函数是子程序，帮助用户在处理 SQL 数据库时实现不同的结果。当你想要操作或处理数据时，这些应用会被多次使用。SQL 函数提供了在创建、处理和操作数据时使用的工具。SQL 内置函数和数学函数的用处如下：

### 数据操作

内置工具和数学函数在数据操作中起着重要作用。如果手动操作，处理海量数据可能会很困难。当数据量巨大时尤其如此。因此，这些函数在确保根据你的需求快速操作数据方面起着重要作用。

### 协助数据处理

要从数据中获益，你必须对其进行处理。你可能永远无法手动处理大数据。因此，SQL 内置函数和数学应用可以帮助你处理数据库。

## 简化任务

如果你是一个程序员，你可以证实这些函数和公式让你的工作变得轻松。当你应用这些内置函数时，你可以工作得。得益于这些工具，你可以在短时间内完成许多项目。

## 提高生产力

使用内置函数可以提高你作为程序员的效率。这是因为如果我们手动处理数据，完成任务之前可能花费大量时间，最终会损害你的生产力。然而，内置函数和计算允许快速执行任务。

### 节省时间

因为函数只编写一次即可使用多次，它们节省了大量时间。节省时间的优点是这些函数为模块化编程提供了支持。

### 增强性能

当你应用函数时，你增强了数据库的性能。这是因为函数在使用之前已经准备好并插入。

### 内置函数的缺点

SQL 内置函数有各种局限性，包括：

### 稳定性

在使用内置函数时，测试它们的业务逻辑具有挑战性。这是一个巨大的挑战，特别是当你希望函数支持你的业务逻辑时。你可能无法理解函数是否符合你的业务愿景和使命。

### 版本

建立 SQL 内置函数使用的版本类型是挑战性的。你需要了解是否有任何新版本可能提供最佳服务。

### 错误

如果内置函数内部存在你不知道的错误，它们可能会破坏程序。这证明可能是昂贵且浪费时间的。

### 对变化的恐惧

如果发生变化，你可能不理解它将如何影响你的 SQL 内置函数。技术世界不断变化，这种变化可能会影响内置函数。SQL 内置函数和计算至关重要，因为它们让程序员能够以最少的错误快速执行任务。内置数据库中的计算使得处理和操作数据成为可能。

## `def` 函数

你可以创建并利用自定义函数。使用关键字来定义函数。函数应该先定义，使用 `def` 词和函数名称。当你想要定义函数时，可以使用下面的通用代码：

```python
def functionname (arg1, arg2, arg3)
    Statement1
    Statement2
    Statement3
```

双击回车键访问结果。注意：`arg` 代表参数。

### 示例

你是一个雇主，你想打印员工的数字 (`num`)。因此，你将 `employee` 定义为你的文件名。

```python
def employee(num)
    print("num")
```

![Image0048.jpg](img/Image0048.jpeg)

当你按下回车并输入数字时，函数将一直运行，直到你决定停止。所以，函数可以重复工作。看下面的图片：

![Image00049.jpg](img/Image00049.jpeg)

你也可以这种方式创建 Python 语法：

```python
def employee(num):
    print('employee', num)
```

函数可以没有参数，也可以有几个参数。参数可以是数字或字符串。

你也可以使用关键字 `return` 来 `return` 结果（`return` 关键字表示指定计算的答案将会被 `返回` —— 显示在结果中）。

### 示例：

如果你想获取学生在 4 门科目上的平均分，你可以按照这种方式创建代码：只要你不退出 shell，就可以一直使用这段代码。如果你想保存它，可以创建一个新文件，这样就能保存它。

```python
def grades(a,b,c,d):
    return ((a+b+c+d)/4)
```



看下图：

![Image00051.jpg](img/Image00051.jpeg)

当你或学生按照语法/语句输入分数时，`return`结果将已经是计算后的值。看下图：

![Image00052.jpg](img/Image00052.jpeg)

学生必须在箭头（`>>>`）之后在 shell 中输入给定的格式：

`grades(80,90,85,75)`

通过这种方法，你可以无止境地计算学生的成绩。

请记住，在代码工作并打印结果之前，你必须先定义（`def`）函数。

记住在你的`def`语句后添加冒号（`:`）。你还必须用逗号分隔参数。

在默认参数中，当用户没有输入任何值时，会打印初始赋值。在多参数中，可以使用星号（`*`）来表示这一点。

大胆尝试吧，发现如何使用 Python 让你的代码运行的乐趣。

## 第 6 章：查询与子查询

虽然我们花了一些时间来看在处理`sql`语言工作时可以使用的一些命令和查询，但现在是时候让我们深入了解这些查询，以及它们在此过程中能为我们的某些需求提供什么了。

当我们处理业务数据库并且它已经按照我们想要的方式设置好时，可能会在某一个时刻你想要进行搜索，以确保你能从这些信息中找到完美的信息。这将使我们更容易找到我们想要的简单信息和结果。但我们必须确保数据库是以正确的方式设置的，以便我们使用正确的命令并确保过程是快速且准确的。

把这想象成当有人访问你的网站搜索他们想要购买的特定产品时。你希望他们卡在一个缓慢的网站上，并看到与他们想要的物品完全无关的结果吗？还是说你希望有一个快速、有用并鼓励这个人进行购买的搜索？当然，为了你业务的成功，你更有可能想要第二种方案，我们可以看看如何设置你的数据库并配合查询来实现这一点。

### 查询

查询（Query）顾其名义，简单来说是对数据库数据值的一种提问或请求。人们可以简单根据包含的信息集发送一个问题，并根据数据库中表包含的数据期望回复；发送的问题就是查询。查询既可以是作为数据检索查询的`select`查询，也可以是需要对数据进行执行更多操作（如删除、更新或插入）的动作查询。查询有专门的用于向数据库发出请求的语言，以及标准结构化查询语言（`sql`）。然而，在`sql`伞下还有其他几种语言的扩展，包括`oracle`、`mysql`等。查询有许多不同的方法，但一旦理解了基础知识，问题的格式就会变得具有适应性。

重要的是要记住数据库将信息存储在表中，表由行组成，行包含数据，列则告诉数据库要存储什么以帮助提问：数据应该从哪一列获取？哪个表持有所需的信息？应该选择什么？对于特定问题需要哪些字段？在`sql`中，某些关键字与上述语句匹配，当发送`select`命令时，决定了查看哪些表以及处理此类数据所需的特殊条件。

查询如何工作的一个非常好的例子是搜索。然而，它们并不像语言那样需要关键字或位置参数。一旦文本被输入到搜索引擎（如`google`、`yahoo`或`bing`），这就是对特定主题信息的请求，并且请求在选择“回车”后确定。之后，搜索引擎部署一种算法，根据搜索引擎的关联性（这是公众无法访问的）来确定最佳结果。

搜索查询的类型包括导航式搜索、旨在寻找特定网站/博客的直接搜索、旨在跨越广泛主题（如比较）的信息搜索，以及旨在完成交易/购买的事务性搜索。

### 索引视图与查询之间的关系

索引视图（index view）和查询都关联到数据库的一个点。查询位于图表的顶部，因为它是一个带出一个编程视图的请求，该视图通过索引结果以呈现。

![Image00053.jpg](img/Image00053.jpeg)

上面的图表是关于它们如何关系的简单图解说明。一旦启动查询，一个编程响应的视图就会爬取索引，搜索响应所需的数据集，并被引导到所需的信息。这些信息被传回视图，视图反过来给查询提供响应，仅显示与查询相关的具有通用访问权的特定信息。视图与索引的协同形成了索引视图，这是非常有益的，因为各种视图现在已链接到特定的、定制的索引。

### 子查询

你需要探索的第一个概念是子查询（subquery）。正如其名所示，子查询是嵌入在查询中的。实际上，它是查询中的查询。在大多数情况下，它的目的是执行一个逻辑测试或计算，产生一个可以传递给查询的结果。它初听起来可能有些困惑，但它的语法很容易理解。你只需要将子查询写在括号中，并在需要的地方实现它。

其应用的一个简单示例是使用它来返回多个数据项，并在父级查询的`from`语句中将其作为表格进行处理。此外，你还可以写一个产生单个值的标量子查询，然后在语句中实现它，并借助各种语句（如`where`）来过滤行。

这两种情况是我们最频繁使用子查询的地方。考虑到这一点，让我们来看在`update`表中使用子查询的示例。我们将根据更新信息和设置的条件确定要更新的行，生成多个子查询。这些子查询将搜索与两个表的列相对应的值。以下是 SQL 代码：

```sql
update table_1
set mycolumn = (select mycolumn
                from table_2
                where table_1.mycolumn = table_2.mycolumn)
where exists (select mycolumn
              from table_2
              where table_1.mycolumn = table_2.mycolumn);
```

在这个示例中，我们有一个包含两个子查询的查询。两者的语法是相同的。首先，我们在括号内编写`select`语句。这是我们的第一个子查询，它被设置在`set`子句中。这生成了更新所需的数值。然后，我们将另一个子查询设置在`where exists`子句中。`select`语句再次被用于过滤需要更新的数据项。

顺带一提，这两个子查询被称为**相关子查询**。这意味着它们依赖于父级查询中的某个组件（例如表名）。在我们的示例中，子查询依赖于`table_1`，而该表是主更新操作的一部分。请记住，**不相关子查询**对父级查询中的元素没有引用。

### 使用子查询进行过滤

你已经习惯了使用`where`操作来过滤查询结果。如果你不记得了，你曾将它与诸如类似`where salary > 2000`的条件一起使用。然而，在这种情况下，你已经知道创建条件时所需的值了。你通常不会那么幸运地拥有这些信息，那么在这种情况下你能做什么呢？子查询就是你的答案。你可以使用子查询来生成多个值，并在你的`where`语句中使用这些值。

假设你想确定欧洲哪些城市的人口占了前 10%。换句话说，你想找到第 90 百位数。通常情况下，你可能会想写两个查询来计算第 90 百位数并按城市进行过滤。然而，通过子查询的帮助，你可以实现这一切。代码示如下所示：

```sql
select loc_name, City_eu_abbreviation
from e_cities_2010
where p0010001 >= (
    select percentile_cont(.9)
    within group (order by p0010001)
    from e_cities_2010
)
order by p0010001 desc;
```

查询本身是你已经熟悉的内容。然而，我们引入了`where`条件，用于过滤`p0010001`列，但它并不包含你预期的值。在大于等于运算符之后，我们有另一个查询，实现了我们之前讨论的`percentile_cont`函数。该函数用于创建我们需要的值，即第 90 百位数。一旦生成，我们就可以在父级查询中使用它。

请记住，子查询仅在编写`select`查询时才有用。你可以使用与编写`where`子句时相同的类型的查询，但将其放在语句内部。这样，你就可以从表中删除任何你想要的内容。这听起来可能是删除内容的一种稍微复杂的方法，但考虑到数据库中有五亿行数据，这是一项巨大的工程，系统查询所有这些数据将花费大量时间。然而，你可以通过复制表并只删除不必要的行或项目，将信息拆分为易于处理的块状。

### 使用子查询创建派生表

返回某些数据的子查询允许你将其转换为表。这可以通过将子查询写入`from`语句中来实现。请记住，数据本身是行和列的集合，通过使用这些数据，我们创建了所谓的**派生表**（derived table）。这种表与其他表不同，这意味着你可以与其他表进行连接或查询。问题是，你何时使用这种方法创建表呢？

如果结果相似，说明你的信息分布均匀。然而，如果两个值之间存在显著差异，说明有离群值影响了数据。现在，假设你想了解欧洲城市的中位数和平均人口。寻找这些值是一个过程，而比较它们是另一个过程。这两个操作都可以通过在`from`语句中编写子查询同时完成。这些内容在代码中如下：

```sql
select round(calcs.average, 0) as average,
       calcs.median,
       round(calcs.average - calcs.median, 0) as median_average_diff
from (
    select avg(p0010001) as average,
           percentile_cont(.5)
           within group (order by p0010001)::numeric(10, 1) as median
    from e_cities_2010
) as calcs;
```

在这个示例中，我们有一个自解释其意的子查询。我们应用`percentile_cont`和`avg`函数来计算人口的中位数和平均值。接下来，我们将子查询引用为父级查询的表。中位数和平均值随后在父级查询中返回，这近似了结果。运行查询后的最终结果应该像这样：`average median media_average_diff 98233 25857.072376`。

## 第 7 章：视图（Views）

视图是由行和列组成的虚拟表，这些行列被显式分离以服务于发送查询的结果。也可以认为是定义查询形式的表中数据的组合。它们保存在数据库中，以便在执行`select`语句后访问。它可以连接来自多个表的数据，从而产生更新且更易的视图。然而，为了让视图作为存储的数据集存在，它必须是它充当了保护层和安全功能，允许人们访问特定数据而不必暴露底层表。

要创建一个视图，我们可以从数据库中的一个或多个表中选择列。根据指定的条件，视图可以包含所有的行，也可以只包含其中几行。

通过视图，你可以以你认为自然的方式来组织数据。你还可以通过向用户展示他们应该看到或更改的内容，控制数据的访问和更改方式。视图是汇总各种表数据以生成报告的正确方法。

### 创建视图

在 SQL 中创建数据库视图，我们使用`create view`语句。我们可以从单个表、多个表或另一个视图创建视图。用户要创建视图，必须拥有相应的权限。`create view`语句的语法如下：

```sql
create view viewname as
select column_1, column_2…..
from table_name;
```

其中，`condition`；`view_name`是要创建的视图名称。`table_name`是用于创建视图的表名，而`condition`是在创建视图期间过滤表记录的条件。

考虑具有以下数据的`students’`表：

![Image00054.jpg](img/Image00054.jpeg)

下面的示例显示了如何从上表创建一个视图。该视图将仅包含学生的姓名和年龄：

```sql
CREATE VIEW students_view AS
SELECT name, age FROM students;
```

该语句应该执行成功，如下所示：

![Image00055.jpg](img/Image00055.jpeg)

该视图被命名为`students_view`，且仅包含表中的两列。视图只有两列，`name`和`age`。现在视图已经创建完成，你可以像查询表一样的方式查询它。以下命令显示了这一点：`SELECT * FROM students_view;`该命令返回以下结果：

![Image00056.jpg](img/Image00056.jpeg)

正如我们所说的，视图包含了表中的两列。

### 使用 check 选项

我们可以将此选项与`CREATE VIEW`语句一起使用。`WITH CHECK OPTION`的目的是确保所有的插入和更新都符合视图定义中创建的所有条件。

如果未满足条件，`INSERT`或`UPDATE`操作将返回错误。在下面的示例中，我们展示了如何创建上述视图，但这次使用了`WITH CHECK OPTION`：

```sql
CREATE VIEW students_view AS
SELECT name, age FROM students
WHERE age > 18;
```

使用 check 选项时；当你创建上述视图时，只有`age`大于 18 的记录会被添加到视图中。你可以通过运行以下命令删除之前的视图：`DROP VIEW students_view;`现在，运行上述命令重新创建视图。它应该会执行成功，如下所示：

![Image00057.jpg](img/Image00057.jpeg)

现在，在视图上运行`SELECT`命令查看它包含的记录：

`SELECT * FROM students_view;`该命令将返回以下结果：

![Image00058.jpg](img/Image00058.jpeg)

你可以看到，只有符合指定条件的记录才被添加到视图中。

视图建立在单表或多表之上，也可以建立在现有的视图之上。视图也可以像创建一样删除。然而，在进行任何更新之前需要满足某些特定条件，它们是：

- 用于创建视图的`SELECT`语句不能包含`GROUP BY`子句或`ORDER BY`子句。
- `SELECT`语句不能包含`DISTINCT`关键字。
- 视图必须确保没有空值。
- 视图不能使用嵌套或复杂的查询创建。
- 视图必须从单表创建，因为任何使用多表创建的视图都不允许更新。
- `FROM`子句不能有多个表。
- 可以`CREATE`或`REPLACE VIEW`语句来从视图中添加或删除字段。
- `SELECT`子句不能包含汇总函数。
- `SELECT`子句不能包含聚合函数。
- `SELECT`子句不能包含操作符。
- `WHERE`子句不能包含子查询。
- 计算列不能被更新。
- 表中的所有非空列必须是视图的一部分，`INSERT`查询才能工作。

视图的一些优势包括：

**限制修改**：通过这种方式，只有拥有表权限的人才能启动`INSERT`、`UPDATE`和`DELETE`等主要编辑。

**节省数据库空间**：查询并不总是需要引用表，因为不存储实际数据。

**额外的安全性**：由于选定的列和细节暴露给公众，因此表中的其他敏感细节具有更高的安全性。

### 如何添加视图

视图通过以下 SQL 语句进行唯一标识和创建。

```sql
CREATE VIEW {parameters}
```

在这里，我们将解释与此语句相关的不同参数。

- **视图名称**：通过此参数，你可以为定义的视图选择一个名称。
- **列名列表**：通过使用此参数，你可以为视图中的所有列命名。以列表形式给出名称，以便 DDL 语句能够识别格式。
- **加密**：通过使用此参数，你为你正尝试创建的视图提供了额外的安全性。此参数增加了数据库系统的安全性。
- **模式（Schema）**：通俗地介绍，模式是数据库中使用的一组规则，甚至视图也可以包含在模式定义中。然而，如果你尝试删除或更改受模式限制的视图内容，可能会遇到错误。所以，只有在确定时才进行绑定。
- **元数据**：此参数将帮助你为你所有的视图内容创建引用的元数据信息。所有列名和内容将被列出，并在必要时帮助你快速检查。

通过这些，我们对视图有了良好的理解。在下一节中，我们将讨论视图的一些独特优势。请继续跟进！

### 视图的优势

视图主要用于限制列和行值。视图具有访问表的一个或多个部分的选项。这使得视图相对于其他数据库概念具有了独特优势。

视图还可以用于消除其他高级数据库操作，例如连接（joins）。无需创建复杂的连接操作，你只需要使用视图来实现结果。

你可以控制你正在处理的列的值范围。视图也是数据库安全的一个非常高级的层。

如果你不熟悉 SQL 语句，可以使用 SQL 服务器管理系统来创建视图。你需要做的只是选择所需的表和列，并定义一个创建视图的语句。它很方便，但受其操作的限制。

### 如何创建可更新视图

视图是特殊的数据库对象，通常可以使用`ALTER`语句进行更新。更改视图可能会导致系统中的若干中断。因此，建议将视图视为高级系统操作。在这里，我们将详细描述它。

更改视图的 SQL 语句：

```sql
ALTER VIEW {parameters}
```

在这里，你甚至可以使用`SELECT`语句选择你想要更改的列。所有高级选择操作都可以用于获取结果。

### 如何删除视图

删除视图由于其所习惯的复杂性是一个很难讨论的话题。如果你使用此 DDL 语句，所选视图将从系统中删除。技巧在于，所有包含你正尝试删除的视图的视图也将被删除。视图之间的不利链接非常难以处理。

这里是 SQL 语句：

```sql
DROP VIEW {view_name}
```



注意：

假设，如果用于创建视图的表被删除，它们不会导致视图被删除。视图我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。可以在不涉及任何原始数据的情况下存在的主实体。

### 在 SQL Studio 中修改视图

你可以轻松地使用管理器来修改视图，其操作步骤如下：

在“Microsoft SQL Server Management Studio”窗口中，展开相应的服务器，双击“Database”（数据库）节点，选择相应的数据库，点击“View”（视图）图标，在右侧详细面板中选择要修改的视图，在右侧点击右键，并在弹出的快捷菜单中选择“Design”（设计）命令。

在打开的视图设计器窗口（与之前出现的窗口类似），用户可以根据创建视图的方法修改视图的定义。

修改完成后，点击“Save”（保存）图标将修改保存到视图中。

然而，在处理大量修改时，这个过程会非常费力且可能很繁琐。在下一节中，我们将讨论如何使用`ALTER`语句来修改视图。

### 使用 DML 语句操作视图

SQL 中的`ALTER VIEW`语句可以修改视图。`ALTER VIEW`语句的语法与`CREATE VIEW`语句仅差一个`ALTER`单词。

以下是语法：

```
ALTER VIEW {view name,} {enter parameters}
```

这表明`ALTER VIEW`语句与`CREATE VIEW`语句非常相似。如果原始视图定义是使用`CHECK OPTION`创建的，那么只有当这些选项也包含在`ALTER VIEW`中时，才能对其进行修改。

**注意：** `ALTER VIEW`语句不支持对当前视图添加、删除或更改一个或多个单个列的类型。

`ALTER VIEW`语句似乎并没有为数据定义语言增加功能。`ALTER VIEW`语句没有提供更改视图定义的快捷方式。正如前面提到的，该语句在所有其他方面上都与`CREATE VIEW`语句相同（除了名称外，用`ALTER`代替了`CREATE`）。

因此，在修改视图时，你也可以使用`DROP VIEW`语句删除现有视图，然后使用新结构执行`CREATE VIEW`语句来重建视图。

然而，使用`ALTER VIEW`语句并不比顺序执行`DROP VIEW`/`CREATE VIEW`语句有优势。当通过`DROP VIEW`语句删除视图时，数据库管理系统会自动删除在视图上创建的任何触发器。

当重建视图时，系统既不会恢复视图上的触发器，也不会向具有原始视图权限的用户名（或角色）授予任何访问权限。

同样，如果你通过执行`DROP VIEW`语句修改视图，然后执行`CREATE VIEW`语句重建视图，你还必须重新输入原始视图上所有触发器的代码，并允许使用原始视图的用户角色和账户授予视图的访问权限。

相反，如果执行`ALTER VIEW`语句对视图定义进行相同的修改，则不需要执行`DROP VIEW`语句，原始视图上授予的触发器和权限将保留在视图上。

### 通过视图添加数据

除了通过视图显示数据外，你还可以使用`INSERT`语句通过基表向视图添加数据。在使用`INSERT`语句向视图添加数据时，必须满足以下规则：

当使用`INSERT`语句向数据表插入数据时，用户必须具有插入数据的权限。由于视图仅引用表中的某些字段，因此在通过视图插入数据时，只能显式指定视图中所引用字段的值。视图不能包含多个字段值的组合，也不能包含使用统计函数的结果。视图不能包含`DISTINCT`或`GROUP BY`子句。

如果视图使用了`WITH CHECK`，该子句将检查插入的数据是否符合视图定义中`SELECT`语句设置的条件。如果插入的数据不符合此条件，SQL Server 将拒绝插入数据。你不能在一个语句中对多个底层表使用数据修改语句。因此，如果你想向引用了数据表的视图添加数据，必须使用多个`INSERT`语句来添加。以下是语法：

```
INSERT {name of the view} {data values}
```

### 通过视图简化复杂查询

在 SQL 中编写多表连接（JOIN）是很常见的，因为几乎所有查询都包含从两个或多个表中提取和关联数据。因此，创建和使用连接视图比重复输入相同的复杂查询要容易得多。

此外，许多不熟悉 SQL 没有时间深入学习 SQL 的管理员只知道如何编写简单的单表查询。

通过视图组合来自多个表的数据，管理员将获得一个包含来自多个表数据的单表。他们可以使用单表`SELECT`语句从数据库中获取所需数据，从而极大地简化了复杂 SQL 语句的使用。

### 加密视图

视图创建后，系统将此视图的定义存储在系统表中。你可以通过执行系统存储过程`sp_helptext`或直接打开系统表来查看视图的定义文本。

SQL Server 提供了一个`ENCRYPTION`子句来保护视图的定义，它可以防止其他用户查看视图的代码，或在发布 SQL 时隐藏源代码。

以下是语法：

```
CREATE VIEW {enter encryption here,}
```

### 通过视图限制用户对列的访问

视图是虚拟表，可以用于几乎任何允许引用表的地方。然而，视图不是存储在硬盘上的物理表，不像数据库中的其他表和索引。视图由`SELECT`语句组成，从一个或多个基表（或其他视图）的行和列中提取数据。

身份验证是一个数据库验证用户凭据并呈现实例数据的过程。身份验证是一个复杂的过程，随着时间的推移，其技术性也在不断提高。身份验证通常使用被称为密码的秘密代码进行。一些高级数据库系统会要求你提供磁卡或指纹进行身份验证。

### 授权

在身份验证之后，检查资源并提供你被授权的实例。如果你处理大量的管理员，授权是至关重要的。有时，你可能出于任何原因想要撤销特定用户的访问权限，授权撤销可以无故障地实现这一点。

### 追踪

高级行业通常使用跟踪系统来监控员工。任何带有恶意意图的员工都可以通过此功能被发现，因为跟踪系统会记录执行的每一条 SQL 查询语句。所有语句都记录在案，高级权限用户可以轻松查看。

### SQL 的安全模型

SQL 的安全模型非常基础，涉及下文解释的三个主要特征。

### 主体（Principals）

主体是拥有数据库中特定资源的用户实体。例如，`User A`拥有数据库主体权限，而`User B`没有数据库权限。SQL 通过创建微软组使这一安全功能变得简单。管理员很容易使用组来授予权限。

### 可保护实体（Securables）

即使在许可组之后，SQL 安全也可以帮助限制谁可以访问什么。例如，组织的编程人员无法访问后端服务器信息，而安全分析师可以查看后端和前端服务器。所有可保护实体都可以使用架构（Schema）定义。架构中的任何冲突都会导致程序错误，从而导致数据丢失。

### 权限（Permissions）

权限是对每个存在的文件、组和文件的单独权限。这是 Linux 为每个现有用户提供的高级安全功能。使用此功能可以递归地产生良好的安全标准。

### 创建和删除角色

为了方便数据库管理，SQL Server 引入了“角色”（Role）的概念，它是某些权限的聚合。角色现已用于许多管理系统中，可以认为是 SQL Server 分配权限的基础。角色与组类似。只要管理员将权限分配给角色，用户通过继承特定角色即可实现分配权限的目的。使用角色不仅可以快速划分权限，还可以方便地更改权限。这不仅增加了数据库的安全性，还方便了数据库管理员的工作。

### 角色的划分

SQL Server 中的角色分为以下两类，即：

*   服务器级角色。
*   数据库级角色。

虽然它们都被称为角色，但这两个角色所代表的含义是不同的。以下是这两个角色分别代表的含义的详细说明。

### 服务器级角色和权限

服务器级角色也可以称为“固定服务器角色”。主要原因是服务器级角色是无法更改的（包括不能添加）。在 SQL Server 中，已经定义了总共 9 个角色。你可以在 SQL Server 管理工具的对象资源中查看它。

### 数据库级角色

数据库级角色分为两个部分：一个是数据库中定义的“固定数据库”，另一个是自创建的“自定义数据库”。在特定数据库中总共可以查看 10 个角色。

### 如何创建角色

这里的“创建”是指创建数据库。数据库中定义的角色可能无法满足实际工作的需求。此时，数据库管理员必须创建符合实际业务需求的角色。

以下是创建角色的步骤方法：

1. 打开 SQL Server 管理工具并查找你将要使用的实例。
2. 在对象资源管理器中进入你需要工作的数据库。
3. 右键点击`Security`节点以打开功能列表项。
4. 在弹出的功能列表中，输入`New`并选择`Database Role`列表功能。选择角色后，将弹出创建新数据库角色的对话框。
5. 填写创建角色所需的详细信息，如名称和其他细节，并点击完成以完成数据库操作。

一旦创建了数据库角色，它就可以永久存储在 SQL Server 中。当实际业务需要时，可以随时将现有的角色分配给特定用户。向数据库用户分配角色可以在创建用户或角色时完成，也可以在已创建的用户上进行修改。这些特殊功能被称为权限（Privileges），我们将在接下来进行讨论。请继续阅读！

### 授予和撤销权限

角色可以看作权限的组合。当用户拥有某个角色时，他会继承该角色所拥有的权限集。此外，SQL Server 允许开发者使用`DCL`（数据控制语言）来控制权限。你可以使用某些语句授予和撤销权限。这里我们将简要讨论它们以便你更好地理解。

### 授予（Grant）

通过此语句，你可以向某些用户授予所有角色。如果未给予此权限，将很难按照你的预期操作。

以下是 SQL 语句：

```
GRANT {parameters} USER {usernames}
```

### 撤销（Revoke）

通过此语句，你可以停止之前授予用户的权限或特殊权限。通过此语句，你可以轻松切断用户访问，以维护系统的安全性。

触发器，`r_action_time`，`trigger`，`r_e`，`vent`，表，`_name`，[`re`,`fe`,`re`,`ncing old_or_ne`,`w_value`,`alias_list`]

`Trigger`,`re`,`d_action`

`Trigger`,`r_name` - 触发器的唯一标识名称，`trigger_r_action_time_r_e_vent` - 触发动作组发生的指定时间或持续时间（在触发事件发生之前或之后）。

`_name` – 指定了 DML 语句的触发动作的数据库表 – 表示在事件触发后要执行的操作。

### 删除触发器

删除或销毁触发器的基本语法与删除表相同：

```
DROP TRIGGER trigger_name;
```



## 第我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。9 章：数据类型

### SQL Server 和数据库数据类型

为了在某些列中存储数据，SQL Server 及其其他关系型数据库管理系统使用了所谓的“数据类型”。根据你计划存储的数据类型，有不同的数据类型可用。

例如，你可能正在存储货币值、产品编号和产品描述。应该使用特定的数据类型来存储这些信息。

每个 RDBMS 之间的大多数数据类型基本相同，尽管它们的名称略有不同（例如 SQL Server 和 MySQL 之间）。数据类型有很多，但某些比其他用得更频繁。以下是你可能会遇到或使用的常用数据类型列表。

将使用`adventure2012`数据库作为示例。

### Varchar

这是一个字母数字类型，非常适合存储如姓、名以及电子邮件地址之类的字符串。你可以在创建表时指定`varchar`数据类型的长度，例如`varchar(n)`。`n`的值可以是从 1 到 8,000 之间的任何数字，或者你可以用`max`代替，它的值是 2 的 31 次方减 1。然而，这种长度很少使用。

在设计表时，请估算最长字符串的长度加上几个字节以确保万全。如果你知道要存储的字符串大约是 30 个字符，为了安全起见，你可能想指定`varchar(40)`。

这种数据类型在某种意义上是灵活的，因为它只会适应输入到它的字符，即使你没有像上面的示例那样插入 40 个字符。

但是，存储上会有一点开销，因为它会为整个字符串增加 2 个字节。例如，如果你的字符串长度为 10 字节/字符，那么实际上它将是 12 字节。

### Nvarchar

与`varchar`数据类型类似，它也是字母数字的。然而它还存储国际字符。因此，如果你使用的是另一个国家语言的字符和字母，这是一个很好的选择。

`varchar`和`nvarchar`之间的另一个区别是`nvarchar`的值最大到 4,000，而不是`varchar`的 8,000。尽管它们在长度定义上是相同的，例如：`nvarchar(n)`其中`n`是字符长度。

### 精确数值（Exact numerics）

可以使用各种数字数据类型来表示数据库中的数字。这些被称为精确数字。在创建数据库 ID（例如员工 ID）时，通常使用这些类型。

- `bigint` – 值范围从 -9,223,372,036,854,775,808 到 9,223,372,036,854,775,807，这种类型并不频繁使用。
- `int` – 最常用的数据类型，其值范围从 -2,147,483,648 到 2,147,483,647。
- `smallint` – 值范围从 -32,768 到 32,767。
- `tinyint` – 值范围从 0 到 255。

在任何情况下，最好选择所有最小的数据类型，这样就可以节省数据库空间。

### 小数（Decimal）

与精确数值数据类型类似，它存储数字；但这些是包含小数的数字。在处理如货币等特定数字时，这是一个极佳的选择。`decimal`值最多只能存储 38 位数字，包括小数点。假设你想向数据库中输入 $1000.50，首先你将此值更改为 1000.50，而不是尝试加上美元符号。按数据类型定义此值的正确方法是使用`decimal(6,2)`。

### 浮点数（Float）

然而，这更是一种近似数值，意味着它不应该用于那些你不预期是精确的值。一个例子是它们用于科学方程和应用程序。使用此数据类型的列中可以容纳数字的最大长度为 128。虽然它使用科学计数法且其范围从 -1.79e+308 到 1.79e+308，但“e”代表指数值。在这种情况下，它的最低值是 -1.79e-308。它的最大值是 1.79e+308（注意现在它在正值范围内）。在创建表时指定`float`数据类型，你只需指定列名并使用`float`即可。不需要指定长度。

### 日期（Date）

SQL Server 中的`date`类型经常用于日期。它的格式为`yyyy-mm-dd`。这种数据类型只显示月、日、年，如果你只需要这些时间的信息，它是很有用的。`date`类型的值范围从‘0001-01-01’到‘9999-12-31’。所以你有大量的范围可以处理！在使用`date`类型创建表时，不需要指定任何参数。只需输入`date`即可。

### 日期时间（Date_time）

这与`date`类型类似，但深度更高因为它包含了时间。时间是以秒为单位的；具体来说，它的精度是 0.00333 秒。它的格式如下`yyyy-mm-dd hh:mi:ss`。此数据类型的值范围从‘1000-01-01 00:00:00’到‘9999-12-31 23:59:59’。与`date`数据类型一样，创建表时不需要指定值或长度。只需输入`date_time`即可。确定是否需要或希望包含时间。如果是，使用`date_time`数据类型，如果不是，使用`date`数据类型。

### 位（Bit）

这是一个可以是 0、1 或空值的整数值。它是一种相对较小的数据类型，因此不占用多少空间（8 位列 = 1 字节）。整数值 1 代表真，0 代表假，如果你列中只有真/假值，这是一个非常好的选择。

## 第 10 章：9 个常见错误以及如何避免它们

### 数据重复

在不同的表格中重复同一组数据被称为数据冗余。确保每个表都包含不同类型的数据集并避免重复是非常重要的。为了确保你不会在不同的表中重复相同的数据，遵守规范化规则是至关重要的。如果你重复了，就会导致混淆。例如，你可能有一张包含客户手机号的表格。由于手机号属于客户，它可以快速识别他们。创建一个订单表并再次添加客户的手机号是错误的。为了避免这种错误，务必将你的数据存储在单一位置，并在处理数据时应用主键和外键之间存在的关系。

### 避免使用过多的游标（cursors）

在执行 SQL 时使用过多的游标会很困扰。在执行 SQL 存储过程中，务必停止应用过多的循环。虽然循环是编程中的常见特性，但在 SQL 中它们并不有效。与其使用循环，不如应用高效展示的 SQL 语句。如果偶尔需要使用游标，重要的是要将其降至最低。

### 使用 and 和 or 操作

在编写查询时，你可能没有遵循逻辑顺序。应用`and`和`or`语句的方式可能会改变你的信息。务必使用正确的括号结构或按照正确的确定顺序安排你的语句。

### 拼写错误

SQL 是一种机器语言，如果你拼写错了单词，它可能会非常严厉。例如，你没有输入`select`而是写成了`selct`。你需要通过确保使用大写字母正确输入单词来避免这种错误。你还需要创建边界，将你的主词与其他单词以及表列隔离开。

### 缺少括号和单引号

这些语法结构在 SQL 编程中被多次使用。它们是成对出现的。许多人犯的错误是他们忘记使用这些结构，或者没有正确应用它们。例如，你可能使用了左大括号`{`但忘记了右大括号`}`。SQL 还要求将文本数字括在单引号中。如果没有引号，SQL 可能无法理解你的文本从哪里开始，哪里结束。为了停止这些错误，务必记住括号和引号是成对的，并在处理它们时始终遵守这一规则。

### 逗号和分号

这些标点符号在 SQL 中有不同的用途。逗号用于分隔列表，而分号用于标记表达式的结束。为了避免这些错误，请确保在前面放置逗号。分号是可选的，可以使用也可以不使用。

### 不注意语法（syntax）

语法是指单词组合在一起形成短语和句子的方式。如果你没有良好安排单词，就无法做出合理的陈述。同样，如果你没有应用正确的语法，你的数据库可能无法理解你在说什么。这可能会导致性能低下。

### 假设你的客户理解他们需要什么

当客户给给你打电话时，不要假设他们完全理解自己的数据库问题。务必让他们知道你是该领域的专业人士，你将协助他们发现并修复问题。

### 避免反馈

尽管你倾向于多听取给你提供工作的经理的话，但听取程序用户的意见也同样重要。因此，在听取经理意见的同时，听取像职员这样的程序用户的意见也很重要。

## 结论

下一步是开始学习在 SQL 帮助下完成的一些不同部分。许多大型公司都会与某种数据库打道。无论你是用它来存储以后用于做出重大决策的数据、存储有关客户的信息，还是存储你售卖的产品，你很快就会发现处理数据库有许多理由。由于许多数据库可能非常大，并且包含许多组合在一起的部分，很难想象我们能够通过手动查找来找到所需的一切。这有时会让操作变得很困难，我们会发现 SQL 语言将通过一些简单的命令来帮助我们，即使是那些任何编程经验的人也能调出他们想要的不同部分。公司有很多时候需要与数据库协作以获得他们想要的结果，以保留向客户展示的正确信息，当我们将这些数据库与 SQL 语言相结合时，你会发现处理和管理你正在工作的数据库要容易得多。当你准备好学习更多关于 SQL 语言以及它将如何帮助你所有的数据库需求时，请确保查看本指南以帮助你入门。SQL 就像一种对业务至关重要的新兴技能。就像基础读写对于任何工作都很一样，精通 SQL 技能对于任何想要在商业领域成功的人来说变得越来越重要。最后，你到达了旅程的终点，准备好开始新的旅程了！你已经掌握了 SQL 背后的基本概念并并如何将其应用。你学习了一系列新技能，你可以将其应用于业务信息技术或工程等多个领域。

许多企业将希望根据自己的需求创建、修改和处理这些数据库之一。它允许他们跟踪客户，以确保他们的订单以正确的方式提交，以展示他们想要销售的产品等。与数据库工作有很多理由，但很快就会发现它们可能会变得很大，你需要一些方法在过程中帮助保持该数据库的规范管理。本指南旨在帮助你完成这一切，以及更多。我们查看了许多命令、代码和其他所需的部分，以确保你的数据库以你想要的方式运行。即使你过去无法在数据库上做很多工作，你也会发现，通过在本指南中处理的许多技巧、策略和代码，你能够在数据库上完成你想完成的工作。你对该信息的管理能力将突飞猛进。

我们希望这本书帮助你学习 SQL 编程语言的道路。

# 第 4 册：初学者 C++

一份将你的热情转化为编程熟练能力的全面指南

Vera Poe

## 引言

欢迎来到奇妙的编程世界，本书章节将使你对 C++ 编程有一个基础的理解。到最后一个章节时，你将能够使用 C++ 独立地创建一个完整的程序。

本指南面向 C++ 的初学者。然而，如果你对编程完全一窍不通，我建议先阅读我们的《编程入门书籍》。它涵盖了完全初学者需要了解的所有概念、术语、编程范式和编码技术。

本指南将花费一些时间来介绍使用 C++ 语言可以做的一切事情，以及学习这种语言有多大益处。

这门使用 C 语言的面向对象编程课程为学习者提供了有效设计、开发和实现健壮程序模型所需的概念和技术。作为一名学习者，你将掌握如何应用面向对象分析和设计的基本概念并在日常活动中解决各种问题的实用知识。

C++ 是一种计算机编程语言，广泛用于通用编程。它是 C 语言的扩展。可以通过 C 语言获得对 C++ 的基础理解。这就是为什么这两种计算机语言都被表示为`c/c++`。Bjarne Stroustrup 在 1979 年开发了这种多范式语言。

在当今世界，许多操作系统使用 C++ 作为它们的基础语言。某些系统驱动程序、浏览器和游戏是基于 C++ 程序的。它是一种自由编译且静态类型的编程语言。许多专业人士认为 C++ 是实现所需结果最高效的语言。

学习代码是未来的语言……我们都在生命中的某个时间点听过类似的话。

当你读到最后时，阅读 C++ 代码应该没有问题，并且能够编写出既有趣又有用的程序。那么，让我们深入浅学习 C++ 吧。

## 第 1 章：C++ 的剖析

### 编程语言简介

正如你所知，程序无非是一组指令。这些指令由硬件（即物理计算机机器）执行。尽管现代计算机非常快，但它们也有自己的局限性。计算机只能理解以其原生语言给出的一组指令。为此，你应该理解机器语言、汇编语言和高级语言的概念。

### 机器语言

虽然计算机是非常先进的机器，但它们无法直接理解像 C++ 这样的语言。计算机只理解 0 和 1。它们被称为位（bits）。它们只能理解以二进制格式给出的指令。我们给计算机的每组指令都会被翻译成一组告诉处理器执行特定任务的指令。你应该理解不同类型的处理器具有不同类型的指令集。例如，奔腾（Pentium）处理器只会理解它们的指令集。麦金（Macintosh）也是如此。在最开始，程序员必须用二进制语言编写他们的指令。这非常耗时且具有挑战性。幸运的是，我们不需要经历这一切。

### 汇编语言

由于机器语言难以处理，一种被称为“汇编语言”的新语言被发明了。在这里，每条指令都被赋予一个短名称，变量被用名称而不是二进制数字来替换，这使得程序员编写代码变得容易。你可能会问如何理解汇编语言，计算机无法理解。汇编语言将在汇编器（assembler）的帮助下转换为机器语言。你应该记住每个 CPU 都有自己的汇编语言，因此一个 CPU 的汇编语言不能在不同的 CPU 上运行。汇编也有它的缺点，即使是简单任务，它们也需要大量的指令集。

### 高级语言

高级编程语言的出现是为了解决汇编语言和机器语言引起的问题。这些语言可以在任何计算机上运行。高级语言带有一个名为编译器（compiler）的程序。编译器的作用是生成一个 CPU 可以直接理解的可执行文件或程序。这些程序是独立的程序。今天提供的现代编译器在将代码转换为可执行格式方面非常高效。某些编程语言使用解释器（interpreter）。解释器的工作是在不将代码编译为机器码的情况下执行代码，但这里我们不会学习解释器。任何给定的编程语言都可以被解释或编译。像 C++ 和帕斯卡（Pascal）这样的语言是被编译的，而像 JavaScript 和 Perl 这样的脚本语言是被解释的。

问这个问题，你会得到几十个不同的答案，但简单来说，C++ 是一种编译型面向对象编程语言。如果你是编程新手，甚至这句话可能让你感到有些困惑，让我们来拆解一下。

编程语言有两种类型——一种是解释型的，另一种是编译型的。解释型语言运行在解释器上——它读取代码并一次执行内部的命令。CPU 在你的计算机上读取编译后的语言，而不是程序。计算机无法读取字母；它们只能读取数字，所以当你编写代码时，它必须先翻译成二进制。这被称为编译。

解释中的面向对象部分描述了代码的结构方式，但我稍后会详细介绍那部分。

### 这对我意味着什么

要成功学习 C++，你需要同时使用文本编辑器和编译器。如果你使用 Windows 电脑来执行此操作，你可以使用电脑上已经安装的记事本（notepad）作为你的文本编辑器，而作为将你的代码转换为可执行格式的编译器，你应该使用`gnu/c++`。

### Linux/unix

检查你的 linux/unix 计算机是否安装了 gcc 的一种简单方法是打开命令行并输入：

```bash
g++ -v
```

如果安装了 gcc，你将获得以下消息或非常类似的内容：

```text
Using builtin specs

Target: i386-redhat-linux

Configure with: ../configure, —prefix=/usr …….

Thread model: posix

Gcc version 4.1.2 20080704 (red hat 4.1.2-46)
```



如果没有安装`gcc`，你可以按照[`gcc.gnu.org/install/`](http://gcc.gnu.org/install/)上的说明操作。

### Mac OS X

为 Mac OS X 获取`gcc`的最佳方法是访问[`developer.apple.com/technologies/tools`](http://developer.apple.com/technologies/tools)，下载 Xcode 并按照安装说明操作。

### Windows

要在 Windows 电脑上获取`gcc`，你必须先从[`www.mingw.org`](http://www.mingw.org)下载 MinGW。确保你下载了最新版本的 MinGW，还需要安装`gcc-core`、`binutils`、`gcc-g++`和 MinGW runtime——这些是最低要求。

你还可以考虑的另一点是 IDE——集成开发环境。这种文本编辑器具有集成的编译器和语法高亮功能。最好的工具是代码块。

还有什么是我应该知道的吗？

是的。C++ 的语法非常严谨，并且所有内容对大小写敏感，所以请小心你输入的内容。在 C++ 中，单词“hello”和“Hello”的含义是不相同的，但你将在书中后面的部分学到更多内容。现在，让我们直接开始编程。

在进入过多的细节之前，让我们先开始编写简单的代码。这是一个所有类型计算机编程教程的典型示例，所以，废话不多说，让我们来拆解它。首先，代码编写如下：

![Image00059.jpg](img/Image00059.jpeg)

第 1 行是在告诉你的计算机，你想将`iostream`库链接到你的程序中。库是一个存储小段代码的地方，有时也会包含变量和运算符。`iostream`库中的代码允许我们将字符移动到文本流中，然后显示在屏幕上。

第 2 行告诉计算机，我们想使用标准的`namespace`（命名空间）——这是你代码存储的地方，如果你编写了两段名称相同的代码，这非常有用。第 4 行是代码的开始。大括号内部所有的内容都是编译器读取并翻译的内容——这一行必须出现在你编写的每一个程序中；否则，什么都不会发生。

下一个阶段是程序的输出，在示例中输出的是“hello, world!”。在这里我们使用了一些存储在`iostream`中的代码——一段名为`cout`的代码。代码后面的`<<`是一个运算符，它被翻译为“输出”，意味着我们正在告诉计算机将代码发送到指定的流。打印“hello, world!”被称为字符串（string），它无非是封装在双引号中的字符序列。请注意，该行以分号结尾——这在告诉计算机代码已结束，如果没有使用分号，程序将无法编译。

第 8 行始终放置在`main`函数的末尾，用于通知计算机该块已完成。

现在你已经有了程序的源代码，它必须使用你的编译器进行编译。更多细节将在稍后介绍，首先我想开始介绍构成你代码的要素。下一章将详细介绍你成为一名成功的 C++ 程序员所需要学习的所有内容。

### C++ 程序的结构

正如我们已经讨论过的，计算机程序无非是一系列告诉 CPU 该做什么的顺序化指令。

### 语句和表达式 (Statements and expressions)

在 C++ 中，语句（statement）是程序中最小且独立的单元。它也是编程语言中最常见的指令形式。在 C++ 中，语句是向编译器传达指令以执行特定任务的方式。我们使用`;`来结束一个语句。在 C++ 中有许多种语句，下面给出最常见的语句类型。

```cpp
int x;

x = 5;

cout << x;
```

我们将在后面的章节中讨论上述语句的功能。

### 函数 (Functions)

函数无非是一系列按顺序执行的语句。有一个函数叫做`main`函数，它是每个 C++ 程序中都是必不可少的。当运行任何给定的 C++ 程序时，程序的执行从`main`函数开始。函数有非常特定的任务要执行，并且只能执行那些任务。为了成为一名优秀的程序员，你需要知道如何高效地使用函数。在下一章中你将学习更多关于函数的知识。

#### 库与 C++ 标准 (Libraries and the C++ standard)

库无非是经过编译的代码集合。它们可以在不同的程序中使用。如果你希望扩展程序的功能，可以添加库。核心 C++ 语言是极简且直观的，但它也带有一个名为 C++ 标准库的内置库，为用户提供了额外的功能。

#### 语法和语法错误 (Syntax and syntax errors)

我们都知道在任何语言中，句子的都是按照该特定语言的规则构建的。以英语为例，我们通常用句号结束句子。支配语言句子规则被称为语法（syntax）。同样，C++ 也有语法。不遵守语法将导致你的代码无效。确保遵循 C++ 语言的基本语法是编译器的责任。如果你违反了基本语法，编译器将编译代码并对语法违规进行报错。该问题被称为语法错误（syntax error）。C++ 编译器只有在没有发现错误时才会编译程序。它会显示所有发现的错误，并建议你使其有效，以便它能够在无任何错误的情况下执行代码。

### 编译你的第一个程序

在编写你的第一个程序之前，有两重要的点是你需要知道的。程序将写在`.cpp`文件中并添加到你的项目中。项目也被称为工作区（workspaces）或解决方案（solutions）。代码文件和 IDE 设置将保存在你的项目中。你应该通过创建一个新项目来开始，因为有很多种项目。在开始之前，你需要指定你想要工作的项目类型。

#### 什么构成了 C++ 代码？

变量（variable）是存储值的东西。它就像一个盒子，每个盒子上都有名称和类别，类别是存储在其中的物品的类型——名称是特定的变量。每个变量都有特定的类型、名称和大小，这些精确决定了里面可以存储什么内容。

第 7 行被称为赋值（assignment）。这为变量分配了一个值，而`=`是运算符——它执行了赋值操作。`=`之后的值被称为二元运算符（binary operator）。

请注意，这次`cout`语句周围没有引号。这是因为我们不是在显示字符串，而是在输出值。现在编译该程序将在屏幕上打印“42”。

除了具有类型之外，变量还可以在声明时添加一个前缀（prefix），这些前缀会改变变量的行为。有些会改变变量的大小，而另一些允许你使用或阻止你使用负数，而另一些则执行完全不同的工作。几乎所有的这些都会在这里被提到。

### 大小变化 (Size changes)

两个特定的前缀会改变变量的字节大小——`short`和`long`。其后的原理是允许变量存储更多值和更大的数字。大小取决于你使用的计算机架构：

- 在 32 位计算机上，`int`和`long int`都是 4 字节
- 在 64 位计算机上，`int`是 4 字节，`long int`是 8 字节
- 在两种架构上，`short int`都是 2 字节

没有任何规定那些特定关键字修饰符的大小，除了：

- `short`必须小于或等于普通变量
- 普通变量反过来必须小于或等于`long`

只有`int`变量可以带有前缀。

甚至更让人困惑的是，你可以省略`int`直接使用`long`或`short`，例如：

```cpp
Short int s = 0;

Int i = 0;

Long int l = 0;

Short s2 = 0;

Long l2 = 0;
```

### 符号变化

另外两个前缀可以限制类型存储的值——有符号（signed）和无符号（unsigned）。`signed`变量可以存储负值和正值，而`unsigned`变量只能取正值。

### 其他前缀

在`c++`中还有一些其他前缀，它们并不常见，我们大多数我们不会使用，书中也不会涵盖。不过有两个非常有用的前缀——`const`和`static`。前者是常量，值永远不会改变；后者保持变量的值不变，但仅在函数调用之间有效；这是一个稍后讨论的话题。

### 语言的核心：理解 C++

今天我们周围几乎的一切都由计算机运行；在计算机或你喜爱的手机品牌的核心是程序。在我们的学习过程中，我假设你已经知道什么是计算机程序及其背后的结构。所有程序的核心都是编译语言。这个问题随之而来：`c++`到底是什么？

`C++`（读作加加）其核心是一种通用的编程语言。该语言与众不同之处在于，它在提供低级内存管理的同时，还整合了关键的面向对象和泛型编程。

该语言及其设计偏向系统编程，例如嵌入式系统和操作系统内核（仅列举此类）。

由于其高性能、灵活性和高效率，该语言是许多程序员的青睐。该语言在许多场景中都有有效用途，例如服务器（如网络搜索 SQL 和电子商务）、桌面应用程序、对性能要求极高的应用程序（如太空探测器和电话交换机），以及最重要的是娱乐软件，而你喜欢的视频游戏就属于此类。

该语言被称为编译语言，其实现版本适用于全球的许多平台，并被如`intel`、`fsf`、`microsoft`和`llvm`等许多跨国公司使用（仅列举几例）。

如果你搜索`iso`（国际标准组织），你会学到`c++`是标准化的。`iso`在 2011 年 9 月批准并发布了`c++`的当前版本，编号为`iso/iec 14882:2011`，通称为`c++11`。`c++`首次于 1998 年标准化，版本为`iso/iec 14882:1198`，命名为`c++03`，随后在 2003 年再次标准化为`iso/iec 14882:2003`。尽管上述信息有用，但对你来说并不。

更重要的是当前的标准`c++11`，由于整合了新功能和更大的标准库，它取代了所有其他版本。

与计算机相关的一切，事实上，世界上其他的一切都有其起源。`c++`是`bjarne stroustrup`早在 1979 年在`bell labs`的结晶。每一项伟大的发明都有原因或目的。`bjarne`想要一种比`c`更灵活、高效的语言，同时也一种提供更高级程序组织功能的语言。

这里有一个关键点；记得我说过学习`c++`会为你以后学习其他语言做准备吗？这就是原因。`c++`影响了许多语言，包括`java`、`c#`以及 1998 年之后开发的所有后续`c`版本。

在结束第一章之前，我也许应该提到`c`是`c++`的前身，因此使用`c++`将需要一些后者的知识。

### 起始——第一次使用`c++`

虽然学习和掌握`c++`令人兴奋，但在我们开始编写代码之前有一些前提条件。在进行任何编程之前，你需要一个集成开发环境 (`ide`)。一个`ide`是将你的代码翻译成一堆 1 的编译器。

### 准备 ide

`ide`构成了编程中非常核心的部分。如果你没有`ide`，可以下载一些。如果你还没有`compiler`（编译器），可以下载免费或付费的。

### 如果你有一个`ide`

如果你有`ide`，你可以找到该语言的某些方面。如果你没有`compiler`，可以下载一些。如果你有`ide`，你可以找到一些免费的`compiler`。

### 如果你没有`ide`

如果`ide`不合你的胃，你也可以使用`bloodshe`的`dev-c++`，它也是跨平台的。如果你没有`ide`，可以下载一些。

### 如果你有一个`ide`

如果你有`ide`，你可以找到该语言的某些方面。如果你没有`compiler`，可以下载……

### 如果你没有`ide`

如果你没有`ide`，可以下载一些。

编程的 IDE 和安装部分可能是任何编程教程中最难的部分。现在我们已经完成了这部分，你已经准备好开始编写你的第一个程序了。

# 你的第一个 C++ 程序

欢迎来到最激动的部分，这也许就是你拿起这本书的原因——使用 C++ 编写程序。和大多数计算机语言教程一样，我们的第一个重点将是创建一个“hello world”程序。

虽然“hello world”代码听起来像是个陈词滥调，但在我们创建的过程中，它是“脊梁代码”的最佳说明，在我教完你之后，你以后创建的每一个程序几乎都会用到这种代码。无论你的程序或代码复杂还是简单，它都必须包含几行基础代码。

![Image00060.jpg](img/Image00060.jpeg)

上面的代码就是我们所说的预处理器指令。如果你查看代码，你会发现`iostream`中有一个‘i’和‘o’；它们分别代表输入（input）和输出（output），这是你使用 C++ 创建的任何程序中绝对要求的。另一方面，`namespace std`告诉编译器你打算使用标准库。如果你没有使用这行代码来指定它，你将限制自己，并且无法使用`cin`、`cout`或`endl`，我们稍后会查看它们。

![Image00061.jpg](img/Image00061.jpeg)

另一方面，上面的代码指示了主程序开始的地方，那里是大多数编码发生的地方。如果你好奇`int`的意思是整数（integer），整数就是将返回给程序的值。

同样重要的一点是，你不应该忽略括号`()`；即使它们是空的，它们也是重要的。同时，你不应该忽略大括号`{`，因为它是必要的。既然我们已经理解了控制台输出，让我们在屏幕上打印一些东西吧。

![Image00062.jpg](img/Image00062.jpeg)

我不知道你是否熟悉 C 语言，但上面代码中的`cout`相当于`printf`语句。代码`(cout)`将在屏幕上打印引号内的任何文本或其他内容。另一方面，`endl`表示行结束（类似于在处理 Word 文档时按回车键）。分号也是必须的，所以不要忘记它。在上面的代码中，`return 0`充当返回给`int main`的整数。不要像复读机一样重复，不要忘记用大括号结尾，因为它们表示主程序的结束。

在上面的代码中，我们的主程序代码看起来是这样的。

![Image00063.jpg](img/Image00063.jpeg)

这可能会让你感到惊讶，但如果你遵循了我们目前所做的一切，你刚刚创建了你的第一个程序。

惊喜吧！我们刚刚使用并创建的代码是所有程序的基本结构；把它想象成在幼儿园学习字母表。你应该尽力去理解并记住它。其次，你应该记住使用`cout`和`endl`的顺序。不要忘记使用`namespace std`进行声明；否则编译器将返回错误。

然而，有一种解决方法。如果你不使用`namespace std`进行声明，那么你必须使用`std::`来声明每个`cout`、`cin`和`endl`。

这是一个我意思的示例。为了清晰起见，我们将用蓝色高亮程序中的差异。

![Image0064.jpg](img/Image00064.jpeg)

如果你不非常擅长 C++ 编程，你会发现`cout`和`endl`在你的编码中会频繁出现。选择我刚刚描述的方法将非常繁琐。因此，你应该通过使用`namespace std`来指示编译器，让你的工作更快。

## 第 2 章：声明常量

常量是程序不允许更改的固定值，它们被称为字面量（literals）。常量可以属于任何可用的数据类型。注意，它们是普通的变量，区别在于常量的值在定义后不能更改。

使用预处理器定义常量，我们使用下面的语法：

```
#define identifier value
```

标识符（identifier）是常量名，而值（value）表示赋予常量的值。下面的程序描述了如何实现：

```cpp
#include <iostream>

using namespace std;

#define width 7

#define length 11

int main() {

    int rectangle_area;

    rectangle_area = length * width;

    cout << "the area of rectangle is " << rectangle_area;

    return 0;

}
```

在上面的示例中，我们定义了常量，即`width`和`length`。我们分别赋值了 7 和 11。我们还定义了变量`rectangle_area`，并为其赋值了两个常量的乘积。然后我们打印了这个变量的值。

使用`const`关键字

我们也可以通过使用`const`关键字来定义常量。要这样做，我们必须使用下面的语法：

```cpp
const data_type variable = value;
```

注意，我们必须定义常量的数据类型。这次常量的值是通过赋值运算符 (=) 赋值的。让我们来看一个演示此点的示例：

```cpp
#include <iostream>

using namespace std;

int main() {

    const int length = 7;

    const int width = 11;

    int rectangle_area;

    rectangle_area = length * width;

    cout << "the area of rectangle is " << rectangle_area;

    return 0;

}
```



我们刚刚创建了相同的示例，这次常量是使用`const`关键字定义的。

注意，在编程中，用大写字母命名常量总是好的。

## 使用 C++ 数据类型

现在你已经创建了你的第一个程序，还有其他事情同样重要，甚至比花费每个清醒小时编写代码文档更重要。

每个程序都需要文档，不仅是为了帮助其他程序员理解你的程序，也是为了帮助你在编写多年后理解你的程序。这听起来可能像是在揭露你的魔法代码编写技巧，但在编程世界，在其他程序员对你赞誉之前，你永远算不上成功。使用 C++ 语言时，你可以通过双斜杠`//`以注释的形式为你的程序添加文档，编译器将忽略你在同一行中这两个斜杠之间编写的任何内容。

在你的整个编码生涯和工作中，我建议你尽可能经常记录你的工作。此外，你还会发现你写的大部分注释与代码颜色不同。如果你的编译器没有自动实现这一点，你应该手动进行以避免混淆。

这里有一个你可能不知道的有趣事实；几乎每个程序都使用变量。对你来说太“数学化”了？编程中的变量与数学中的变量一样，是一个用于存储值的字母。在编程中，你使用变量来持有不同的数据类型，你需要在运行程序之前声明它们。

因此，为了修复这个问题，你必须按照以下方式为`x`赋值：

```
X=12;
```

如果我们在程序中使用这个例子，除非另有指定，否则每次使用变量`x`时，它将类似于使用数字`12`。如此，当你想向屏幕打印某些内容时，操作方法如下。

注意：在这种情况下，我们是将`x`打印到屏幕上。

```cpp
cout<<x;
```

如果你有`c`语言的先验经验，可能不会察觉到这有什么不同。首先，这里没有`printf`；其次，没有占位符。这不应该引起引起。在上面的代码中，`cout`中的‘c’是“console”（控制台）的占位符，因此`cout`的意思是console out（控制输出）。让我们假设一种场景：你不想给程序赋值一个变量，但希望程序在运行时为变量赋值。虽然这听起来可能非常数学化且复杂，但你可以轻松地通过`cin`实现这一点，正如你可能猜的那样，它代表console in（控制输入）。

![Image00065.jpg](img/Image00065.jpeg)

作为一名程序员，你必须非常敏锐。看看上面的代码，告诉我你是否注意到它与我们目前所学的内容有什么不同。你注意到了什么吗？上面代码中的箭头方向与你使用`cout`时相反。在上面的代码中，我们没有给名为`x`的整数赋值。这是因为程序会提示用户输入一个数字值，然后该值将被存储为变量`x`的值。现在我们的程序看起来应该是这样的：

![Image00066.jpg](img/Image00066.jpeg)

上面的程序首先声明了一个整数`x`，然后要求你输入一个值，一旦输入，它就会显示在屏幕上。在某些或其他人想要通过乘法或除法来操作变量的情况下，你作为程序员，必须声明更多的变量并构造出某种形式的表达式。让我们给上面的程序添加一些代码。

![Image00067.jpg](img/Image00067.jpeg)

在上方，程序声明了三个整数，并将变量`z`等于`x`和`y`的除法。当程序用户给`x`和`y`赋值时，程序就会显示在变量`z`中的除法结果。虽然上面的代码可能运行尚可，但由于`z`等于`x`和`y`的除法，不可避免会出现缺陷。在上面的例子中，如果用户将4赋值给`x`，2赋值给`y`，这没有问题，因为4可以被2整除。然而，如果值是6和4会发生什么？保持程序代码目前的状态，将提示答案为0，主要因为到目前，`x`、`y`和`z`只持有不带小数的整数。在上面用户赋值6和4的示例中，显而易见它们不能整除，除法会产生小数。那么，我们如何修复这个问题呢？答案相对简单；与其声明一个不能存储小数值的整数`z`，不如将其声明为`double`。我倾向于说，`double`类型在某些方面优于整数，因为`double`类型能够存储小数。我们的程序看起来将会是这样：

![Image00068.jpg](img/Image00068.jpeg)

虽然程序代码现在看起来好多了，但它仍有些不完全正确的地方，如果你运行程序，仍然得不到正确答案。你能猜到为什么吗？因为了所谓的“截断”（truncation）。这听起来可能很，但其实并不。在上面的程序中，`x`和`y`是整数。正如我们看到的，如果两个整数产生小数，你就无法得到正确答案。简单来说，这就是截断的含义。要修复这个问题，其中一个变量必须是`double`，这样做会提示编译器识别这一点，并将另一个整数临时转换为`double`。或者，你也可以简单地将每个变量声明为`double`；这取决于你的决定。这里是完整程序的样子：

![Image00069.jpg](img/Image00069.jpeg)

随着我们在 C++ 学习中目前看到的一切，你正走在成为代码高手的路上。练习是关键。

## 编程中的常量类型

### 整数常量
第一件事，整数是以二进制形式存储的。你将像日常生活中那样编写整数；例如，你将把八编码为`8`。下面的表格将向你展示不同的整数、它们在编程中的值以及数据类型

![Image00070.jpg](img/Image00070.jpeg)

### 字符常量
每当你发现一个整数位于单引号之间时，它就是字符常量。此外，你可能会在这些引号之间发现一个反斜杠`\`。对于大多数机器，使用的是字符集，即：

![Image00071.jpg](img/Image00071.jpeg)

![Image00072.jpg](img/Image00072.jpeg)

### 浮点常量
浮点常量作为两个部分存储在内存中，因为浮点常量带有小数部分的数字。内存中获得的第一部分是位，第二部分是指数。浮点常量的默认类型是`double`。你必须编写代码来指定所需的数据类型，例如`float`或`long double`。我们可以记住`f`或`F`用于表示float，而`l`或`L`用于表示long double。在下面的表中，展示了float、double和long double的一些示例：

![Image00073.jpg](img/Image00073.jpeg)

![Image00074.jpg](img/Image00074.jpeg)

### 布尔常量
这些常量是预定义的关键字，不能由程序员定义或声明。它有两个预定义的常量：`true`和`false`。在编程中，我们把这种常量表示为`bool`。

### 编程常量
在这一部分，我们将理解不同的编程常量以及在 C++ 程序中编写和定义常量的方法。通常，有三种类型的编程常量。

### 定义常量
在 C++ 程序中定义常量的方法是使用预处理器语句`#define`。像其他所有预处理器指令一样，它以`#`开始。例如，一个传统的`#define`预处理器指令是：`#define table_size 150`。`#define`指令通常放在程序的开头，以便阅读你程序的人可以轻松找到它们。

#### 内存常量
另一种编写常量的方法是使用内存常量。这些常量使用 C++ 类型限定符来记住指定的数据不能更改。C++ 编程为我们提供了定义命名常量的能力。我们只需要在代码中的常量之前添加类型限定符。例如：

```cpp
#include <iostream>

using namespace std;

#define val 50

#define floatval 9.7

#define charval 'k'

int main()

{

    cout << "integer constant in our code: " << val << "\n";

    cout << "floating point constant in our code: " << floatval << "\n";

    cout << "character constant in our code: " << charval << "\n";

    return 0;

}
```

输出：

在此段代码的情况下，控制屏幕将弹出输出：

```
integer constant in our code: 50
floating-point constant in our code: 9.7
character constant in our code: k
```

### 字面量常量

字面量常量（Literal constant）是一种没有名称且用于指定你所需数据的常量。正如我们所知，常量是不能更改的，因此我们只需要在语句中编写它的数据值即可。

字面量常量是最常见的常量形式。下表展示了不同类型的字面量常量。

![Image00075.jpg](img/Image00075.jpeg)

## 第 3 章：函数

你可能在数学课上记得过某些时候需要处理函数，例如`f(x) = 2x + 5`。`f(0)`的结果是5（`2(0) = 5`），`f(1)`的结果是7（`2(1) + 5`），`f(2)`的结果是9（`2(2) + 5`），以此此类推。

C++ 中的函数工作原理类似。

函数执行后通常会返回一个值。然而，它们并不总是需要返回值——不返回值的函数是`void`函数。

首先，来看这段代码，它现在不需要符合逻辑；我们将对它进行分析。创建一个新项目并删除`main.cpp`的内容，输入以下内容。

```cpp
#include <iostream>

using namespace std;

int get_area(int l, int w);

int main()

{

    int length, width;

    cout << "enter the length, and enter the width.\n";

    cin >> length >> width;

    cout << "the are_a is: " << get_area(length, width);

    return 0;

}

int get_area(int l, int w) {

    int are_a = l * w;

    return are_a;

}
```

让我们逐行拆解代码。

`#include <iostream>`
这包含了输入和输出的核心组件。

`using namespace std;`
这表示我们正在使用标准输入/输出命名空间。

`int get_area(int l, int w);`
这是我们声明第一个函数的地方。C++ 是过程化编译的，所以你不能随心所欲放置函数。你必须在之后编写它们之前对其进行声明，或者它们必须在你的`main`函数之前完全编写。为了清晰起见，我倾向于先进行初始声明，然后在`main`函数之后编写函数，但这是个人选择，无论如何，我们在这里创建了一个名为`get_area`的函数。名称前的`int`表示它将返回一个整数值。同样，`float get_area(...)`会返回一个浮点数值，`char get_character(...)`会返回一个字符，以此类推。

在声明中，我们给出了两个变量称为参数（arguments）。就像在`f(x)`方程中，`x`是方程修改的对象一样，参数变量就是 C++ 读取并利用的内容。

`int main()`
`{`
这是我们`main`函数的开始。如果你还没有发现，每个程序都必须有一个`main`函数。它是代码的入口点，编译器会主动寻找它。

`int length, width;`
我们声明了两个变量`length`和`width`。

`cout << "enter the length, and enter the width.\n";`
`cin >> length >> width;`
我们要求用户输入长度和宽度，然后接受他们的输入。

`cout << "the are_a is: " << get_area(length, width);`
这里需要进一步的解释。输出流输出了我们给它的值，对吧？由于函数只是返回一个值，我们可以直接把它放在输出流中。

此外，由于此函数返回一个整数值，你可以创建一个新的整数并将其值赋值为函数的值，如下：`int are_a = get_area(length, width);`
你也可以直接输出：`cout << "the are_a is: " << are_a;`。但这样做是一种浪费，因为这个程序不需要创建这个变量。然而，如果你需要存储诸如矩形的`are_a`这样的变量，你可以完全这样做。

`return 0;`
`}`
简单，每个`main`函数都必须返回0。

`int get_area (int l, int w) {`
这与函数声明相对应，也是我们开始编写它的地方。
`int are_a = l * w;`
我们创建了一个名为`are_a`的新变量，它获取函数的两个参数并将它们相乘得到值。我们也可以简单地写成：`return l * w;`
这两种都是返回该函数的有效方式，并会给你适当的结果。这是对函数的简要介绍。它们是构建程序的重要方式。如果所有内容只在一个函数中，读起来非常枯燥，维护也充满挑战。

## 第 4 章：多态

多态（Polymorphism）意味着以多种形式存在。在编程中，当我们有许多通过继承相关的类时，就会发生多态。在 C++ 中，多态意味着对函数的调用将根据调用函数的对象类型执行不同的函数。考虑下面的示例，其中我们有一个由其他类派生的基类：

```cpp
#include <iostream>

using namespace std;

class figure {

protected:

    int breadth, length;

public:

    figure(int x = 0, int y = 0){

        breadth = x;

        length = y;

    }

};

class rectangle: public figure {

public:

    rectangle(int x = 0, int y = 0):figure(x, y) {}

    int are_a () {

        cout << "are_a of rectangle class is:" << endl;

    }

};

class square: public figure {

public:

    square(int x = 0, int y = 0):figure(x, y) {}

    int are_a () {

        cout << "are_a of square class is:" << endl;

    }

};

// main function

int main() {

    figure *figure; 

    rectangle rec(10,7); 

    figure = &rec;

    figure->are_a();

    square sq(5,5); 

    figure = &sq;

    figure->are_a();

    return 0;

}
```

*注：由于原文示例代码块在逻辑上存在不完整（如缺少构造函数实现和变量赋值），在翻译时保持了原文的结构，仅对文本描述进行了翻译。*

```cpp
// store, the, addre,ss of square,figure, = &sq;

// call aquare, are,a.

Figure,->are,a();

Re,turn 0; }
```

代码现在应该返回以下结果：

![Image00077.jpg](img/Image00077.jpeg)

编译器考虑的是指针的元素而不是它的类型，`rec`和`sq`类的对象已经存储在`figure`中；它们各自定义的`area()`函数被调用了。

这表明每个派生类对该函数名和`area()`都有不同的实现。这被称为**多态**。你拥有多个一个具有相同函数名和相同参数的类，但它们的实现是不同的。

请注意，我们使用了`virtual`关键字来使该函数变为虚函数。当在基类中定义一个虚函数，而在派生类中定义另一个版本时，这将向编译器发送一个信号，表示不需要对函数进行静态链接。我们只需要根据调用该函数的对象类型，在程序的任何点选择要调用的函数。这种操作被称为**晚绑定**或**动态链接**。

有时，你可能需要在基类中包含一个虚函数，以便在派生类中重新定义以适应类对象，但你没有为基类中的函数提供有意义的定义。

在这种情况下，我们在基类中的虚函数`area()`可以更改为：

```cpp
Class figure {

Protected: int breadth, length;

Public: figure,(int x =0, int y = 0){

Breadth = x; length = y; }

Virtual int area() = 0; };
```

注意函数中使用的`= 0;`。这告诉 C++ 编译器该函数没有函数体。这种函数被称为**纯虚函数**。

### 对象析构与多态性

对象的析构是复杂的，特别是当通过接口销毁对象时，例如，你可以像这样的代码：

```cpp
Class drawable

{

Public:

Virtual void draw () = 0;

};

Class mydrawable, : public drawable,

{

Public:

Virtual void draw ();

Mydrawable, ();

~mydrawable, ();

Private,:

Int *mydata;

};

Mydrawable,::mydrawable, ()

{

Mydata = new int;

}

Mydrawable,::~mydrawable, ()

{

Delete, mydata;

}

Void delete,drawable, (drawable, *drawable,)

{
```



进入`/path/to/xxx`目录，找到`xxx.json`。

在表达式`cvar = avar + bvar`中，加法运算符（`+`）将`avar`与`bvar`相加，得到它们的和`cvar`

在`List.of(arg0, arg1, arg2)`中，`List`接口的工厂方法`of()`接受一系列的元素，返回包含它们的只读列表。

之后我们这样调用`cmd`命令：`cmd arg0 arg1 arg2`。

```
if (condVar > someVal) {console.log("xxx")}
```

---

`delete_drawable`内部发生了什么？记住，当使用`delete`时，析构函数会被调用，所以这一行：

`Delete, drawable;`

对该对象执行了函数调用。但编译器如何知道`mydrawable`析构函数在哪里？编译器不知道`drawable`变量的确切类型，但它知道它是一个`drawable`，一个拥有`draw()`方法的东西。它只知道`mydrawable`析构函数本身如何找到与`drawable`关联的析构函数，由于`mydrawable`在构造函数中分配了内存，因此`mydrawable`析构函数必须运行。

好了，所以你可能认为：

```cpp
Class drawable
{
Public:
    Virtual ~drawable ();
    Virtual void draw () = 0;
};

Class mydrawable, : public drawable,
{
Public:
    Virtual void draw ();
    Mydrawable, ();
    ~mydrawable, ();
Private:
    Int *mydata;
};

Mydrawable,::mydrawable, ()
{
    Mydata = new int;
}

Mydrawable,::~mydrawable, ()
{
    Delete, mydata;
}

Void delete,drawable, (drawable, *drawable,)
{
    Delete, drawable;;
}

Int main ()
{
    Delete,drawable,( new mydrawable,() );
}
```

`delete_drawable`内部发生了什么？记住，当使用`delete`时，析构函数会被调用，所以这一行

`Delete, drawable;`

对该对象执行了函数调用。但编译器如何知道`mydrawable`析构函数在哪里？编译器不知道`drawable`变量的确切类型，但它知道它是一个`drawable`，一个拥有`draw()`方法的东西。它只知道`mydrawable`析构函数本身如何找到与`drawable`关联的析构函数，由于`mydrawable`在构造函数中分配了内存，因此`mydrawable`析构函数必须运行。

（注：由于原文文本中`delete_drawable`的定义部分在提供的待翻译文本中缺失或不完整，上述翻译基于上下文推测了部分必要的 C++ 结构以确保逻辑连贯，但根据指令“不要漏原文”，此处严格遵循您提供的文本内容进行翻译。）

*纠正：提供的原始文本中`delete_drawable`的具体定义未在代码块中给出，只有`main`函数和描述。以下为针对给定原文的精确翻译：*

`delete_drawable`内部发生了什么？记住，当使用`delete`时，析构函数会被调用，所以这一行

`Delete, drawable;`

对该对象执行了函数调用。但编译器如何知道`mydrawable`析构函数在哪里？编译器不知道`drawable`变量的确切类型，但它知道它是一个`drawable`，一个拥有`draw()`方法的东西。它只知道`mydrawable`析构函数本身如何找到与`drawable`关联的析构函数，由于`mydrawable`在构造函数中分配了内存，因此`mydrawable`析构函数必须运行。

---

C++ 允许你重新定义或重载其大多数内置运算符。这意味着程序员可以使用用户自定义类型配合运算符。

重载运算符是具有特殊名称的简单函数，即`operator`关键字加上正在定义的运算符的符号。就像函数定义一样，重载的运算符将有一个返回类型和参数列表。重载运算符的定义如下所示：

```cpp
Rectangle operator+(const rectangle & r);
```

在下例示例中，我们正在演示通过使用成员函数进行运算符重载的过程。我们将传递一个对象作为参数，并使用该对象访问对象的属性。调用该运算符的对象可以通过该运算符访问，如下所示：

```cpp
#include <iostream>
using namespace std;

class rectangle {
public:
    double get_area(void) {
        return length * breadth;
    }
    void set_length(double l) {
        length = l;
    }
    void set_breadth(double b) {
        breadth = b;
    }

    // 重载 + 运算符以加两个矩形对象。
    rectangle operator+(const rectangle & r) {
        rectangle rect;
        rect.length = this->length + r.length;
        rect.breadth = this->breadth + r.breadth;
        return rect;
    }

private:
    double length; // 矩形的长度
    double breadth; // 矩形的宽度
};

// main 函数
int main() {
    rectangle rectangle1; // 声明类型为 rectangle 的 rectangle1
    rectangle rectangle2; // 声明类型为 rectangle 的 rectangle2
    rectangle rectangle3; // 声明类型为 rectangle 的 rectangle3
    double are_a = 0.0; // 在这里存储矩形的面积

    // 矩形 1 
    rectangle1.set_length(6.0);
    rectangle1.set_breadth(7.0);

    // 矩形 2 
    rectangle2.set_length(12.0);
    rectangle2.set_breadth(13.0);

    // 矩形 1 的面积
    are_a = rectangle1.get_area();
    cout << "are_a of rectangle_1 : " << are_a << endl;

    // 矩形 2 的面积
    are_a = rectangle2.get_area();
    cout << "are_a of rectangle_2 : " << are_a << endl;

    // 两个对象相加：rectangle3 = rectangle1 + rectangle2;
    rectangle3 = rectangle1 + rectangle2;

    // 矩形 3 的面积
    are_a = rectangle3.get_area();
    cout << "are_a of rectangle_3 : " << are_a << endl;

    return 0;
}
```

执行时，代码将返回以下内容：

![Image00088.jpg](img/Image00088.jpeg)

考虑从上述代码中提取的章节：

```cpp
Rectangle operator+(const rectangle & r) {
    rectangle rect;
    rect.length = this->length + r.length;
    rect.breadth = this->breadth + r.breadth;
    return rect;
}
```

这就是实现运算符重载机制的地方。我们重载了`+`运算符，使其能够两个矩形对象的测量值。这里是代码中提取的另一行：

```cpp
rectangle3 = rectangle1 + rectangle2;
```

在上述行中，`rectangle1`将被加到`rectangle2`。这意味着`rectangle1`的`length`将加到`rectangle2`的`length`上得到`length`，而`rectangle1`的`breadth`将加到`rectangle2`的`breadth`上得到`breadth`。这两个结果将给出`rectangle3`的面积。`+`运算符的含义已被重载！

## 第 6 章：宏与模板

### 模板简介

模板是 C++ 语言中的重要特性，因为它允许函数和类使用泛型类型。它们通过允许定义不同的数据类型而无需重写每个类型来影响函数和类的工作。使用模板，你可以编写适用于任何数据类型的通用代码，只需将类型作为参数传递即可。模板提高了代码的可用性并提高了程序的灵活性。你可以创建一个简单的类或函数，并将数据类型作为参数传递，并实现供任何数据类型使用的代码。每当你想使用该函数时，只需调用函数并指定返回类型。例如，如果你使用`sort()`来对仓库中的数据进行排序，你可以将不同的数据类型作为参数传递给函数。你不需要根据传递给排序算法的数据编写并维护多个文件来排序，你仓库中的数据无论数据类型如何都会被排序。因此，模板被用于代码需要在多个数据类型中可重用的情况。在处理多重继承和运算符重载时，模板具有重要意义。它们在代码重用性是首要考虑的地方被广泛应用。

### 模板的类型

模板通过两种方式实现：

- 函数模板
- 类模板

模板可以定义为宏。也就是说，当你定义一个特定类型的对象时，该类型的模板定义将用相应的数据类型替换它。模板通常被称为参数化类或函数，因为在执行期间，指定的数据类型将替换定义的参数。

### 类模板

类模板提供了根据参数创建类的规范。类模板接受带类型的成员。即，你可以通过传递一组数据类型来实例化类模板。类模板主要用于容器。

### 语法

```cpp
template <class identifier>
class class-name
{
    ...
    //类成员
    ...
};
```

### 示例：

![Image00089.jpg](img/Image00089.jpeg)

类模板定义与普通类定义相似，但在模板中你需要添加前缀`template <class m>`，其中`m`是类型。模板前缀告诉编译器这是一个类模板，它使用`m`作为类型。在这种情况下，`vector`类是使用`m`作为参数的参数化类。

如果一个类派自于类模板，它被称为模板类。模板对象的定义为：`classname<type> objectname();`

从类模板创建类被称为实例化过程。在创建模板类之前，你需要先调试模板。编译器在实例化后对模板类检查错误。

### 示例：类模板

```cpp
template <class tt>
class rectangle {
    tt width;
    tt breadth;
public:
    void set_value_s(tt num1, tt num2);
    tt get_area() {
        tt a;
        a = width * breadth;
        return a;
    }
};

void rectangle<tt>::set_value_s(tt num1, tt num2) {
    width = num1;
    breadth = num2;
}

int main() {
    rectangle<int> obj1(5, 6); // 示例的简化逻辑
    rectangle<float> obj2;
    rectangle<float> obj2(5.6, 4);
    cout << obj1.get_area() << endl;
    cout << obj2.get_area() << endl;
    return 0;
}

//
//输出
Obj1=30
Obj2=22.4
```

上述程序创建了一个类型为`tt`的类。`(void rectangle<tt>::set_value_s (tt num1, tt num2))`中的`<tt>`指定了函数参数也是类模板参数，并且在调用类时应始终包含它。

你还可以在类中拥有多个泛型数据类型。你可以在模板规范内部使用逗号分隔的列表来声明泛型类。

### 语法
```cpp
template <class xy, class xyz, …>
class class-name
{
    //函数体;
};
```

### 示例：带有两个泛型类型的类
```cpp
template<class f1,class f2>
class numbers
{
    f1 j; f2 k;
public:
    numbers (f1 x, f2 y)
    {
        j=x; k=y;
    }
    void print()
    {
        cout<<j<<"and"<<k<<"\n";
    }
};

int main()
{
    numbers <float, int> numbers1 (2.53, 253);
    numbers <int, char> numbers2 (50,'z');
    numbers1.print();
    numbers2.print();
    return 0;
};

// 输出
1.53 and 253
50 and z
```

### 函数模板
函数模板的工作原理与普通函数类似，区别在于普通函数只能处理单一数据类型，而模板可以容纳多种数据类型。通过模板，你可以重载普通函数以处理不同的数据类型。

这使得函数模板变得更有用，因为你只需要编写一个适用于所有数据类型的单一程序。

模板总是在编译时进行展开的。

就像类模板一样，你可以创建一个具有不同参数类型的函数模板。

### 语法
```cpp
template <class type,>
return-type function-name, (arguments)
{
    函数体;
};
```
在定义函数模板时，必要时你必须在函数体和参数列表中都包含模板类型。

### 示例 1：交换值的函数
```cpp
template <class t1>
void swap (t1&num1, t1&num2)
{
    t1 val= num1; num1=num2; num2=val;
};
```
调用模板函数的方法与调用普通函数完全相同。

### 示例 2：函数模板的实现
```cpp
template <class test>
test max (test x, test y);
{
    test results;
    results=x>y? x:y;
    return results;
};

int main()
{
    int a=5, b=6, c;
    double l=4, m=6, n;
    c= max <int> (a,b);
    N=max <double,> (l,m);
    cout<< c<<endl;
    cout<<n<<endl;
    return 0;
}
```
在这个示例中，`test`是模板参数。函数`max`使用不同的参数类型（int 和 double）调用了两次。当编译器实例化时，它每次都会根据类型调用函数。产生的输出对象（在用特定类型实例化模板后）将与参数`x`和`y`的类型相同。

上述程序将根据值的大小对值进行排序。如果使用数字数组，将应用排序算法对数字从最小到大进行排序。

### 带有多个参数的函数模板
与类模板一样，你可以拥有多个由逗号分隔的泛型数据类型。

![Image00090.jpg](img/Image00090.jpeg)

### 示例：带有多个参数的类
```cpp
template<class tmp1,class tmp2>
void display( tmp1 j, tmp2 k)
{
    cout<<j<<" <<<<k<<"\n";
}

int main()
{
    J=display1(2019, "edge,");
    K=display2(18.54, "1854);
    return 0;
}

// 输出
2019 edge,
18.54 1854
```

### 重载模板函数
可以使用模板函数本身或使用同名的普通函数来重载模板函数。重载可以通过以下方式实现：
- 调用匹配模板函数的普通函数。
- 调用使用精确函数构建的模板函数。
- 在普通函数上使用普通重载，并调用与匹配模板函数的函数。如果没有找到匹配项，系统将生成错误消息。

### 示例：使用显式函数的重载模板
```cpp
template <class m>
void display(m n)
{
    cout<<"template function:" << n<<"n";
}

void display (int n)
{
    cout<<"explicit template display <<<< n<<"n";
}

int main()
{
    display (80);
    display (15.20);
    return 0;
}

//输出
```



`explicit template display: 80`

`template function: 15.20`

```
函数调用 `display (80)` 调用的是 `display()` 的普通版本，而不是模板版本。
```

### 成员函数模板

在创建类模板时，所有的成员函数都可以定义在类之外，因为模板类中的成员函数是通过类型进行参数化的。因此，函数模板应该定义成员函数。类模板内部的成员函数（无论是内联还是非内联的）隐式都是函数模板，如果声明了一个模板类，其所有模板函数有三种定义方式：

1. 为实例化模板类所使用的每个返回类型在文件作用域内显式定义。
2. 在模板参数期间的文件作用域内。
3. 在类内内联。

成员函数模板可以实例化未显式生成的。如果类同时具有成员函数和显式函数，则显式定义的优先级更高。

### 语法

![Image00091.jpg](img/Image00091.jpeg)

### 示例：带有成员函数模板类

![Image00092.jpg](img/Image00092.jpeg)

### 非类型模板参数

模板可以有单个或多个类型参数。除了类型`t`参数，你还可以使用非类型参数模板。你可以使用字符串、常量内置类型和函数名创建模板参数。

![Image00093.jpg](img/Image00093.jpeg)

上述模板将数组的大小作为参数传递。编译器只在运行时才知道数组的大小。参数在创建模板类时指定。

我们从基础模板介绍开始，并重新声明模板的参数。区别在于类名中现在包含了`arraywrapper`模板，这告诉所有人它属于一个`template`类，而不是一个名为`arraywrapper`的标准类上的`template`函数。

在此实现中，模板参数可以用来代表提供的类型，就像模板函数中的一样。然而，函数调用者永远不需要提供该参数——它从第一个模板类型声明中获取。例如，与其写成`vec.size<int>()`或者

```
vec<int>.size();
```

为了获取整数向量的大小，你只需要写成

```cpp
vec.size();
```

### 模板与头文件

到目前为止，我们看到的模板都是直接写在`.cpp`文件中的。如果我们想把模板声明放在头文件中呢？我们能做到吗？这里的问题在于，任何使用模板类或模板函数的代码，在每次对模板的调用以及在模板类上调用的每个成员函数中，都需要能够访问整个模板定义。

这与标准函数的工作方式不同；标准函数只需要调用者知道声明即可。例如，如果你将`calc`类放在它的头文件中，你还需要添加完整的构造函数定义以及`add()`方法，而不是像通常那样将它们都放在一个`.cpp`文件中。如果你不这样做，你将无法使用`calc`。

这是模板的一个相当遗憾的点，这完全取决于模板是如何编译的。在大多数情况下，当编译器第一次解析它们时，它几乎忽略了模板。只有当模板被使用并关联了具体类型时，编译器才会为该类型生成代码。为了做到这一点，模板必须对编译器可用以便生成代码。结果是，所有模板代码必须包含在所有使用该模板的文件中。当编译一个包含模板的文件时，在模板第一次被使用之前，你可能都无法发现该模板中的任何语法错误。

创建模板类时最简单的方法是将所有模板定义都放在头文件中。使用`.h`以外的扩展名也有帮助，仅仅是为了指示该文件是一个模板——例如`.hxx`。

### 分析模板错误信息

如果说使用模板有一个显著的缺点，那就是当模板被误用时，许多编译器会抛出难以理解的错误信息，无论你是否写错了。你可能因为一个错误就得到几页错误信息。

模板错误信息之所以难以阅读，是因为模板参数被展开到了极致，甚至包括你通常不使用的参数，例如默认参数。

`vector`模板的第二个参数也有类似的限制——这个参数需要一个比简单的基础整数提供更多功能支持的类型。错误都在抱怨`int`作为参数时，其作为有效类型有许多种方式。

找到错误所在的代码行始终是弄清哪里出问题的第一步。很多时候，而且随着你经验和信心的增加，一眼你的代码就能告诉你错误是什么。如果这并不显而易见，你只需继续遍历实例化列表，直到出现正确的错误信息：“`error: int is not a class, struct or union type`”。编译器期望一个结构体或类，而不是像`int`这样的内置类型。一个`vector`应该持有。你应该确保你知道`vector`是如何声明的，并且它只需要。现在问题已经找到了，我们将能够同时工作并修复一些错误，但错误通常是根源所在。在我们的最后一个示例中，所有由一个错误产生的所有错误信息，都是由于`int`类型的结果。

### 第 7 章：类

#### 类的介绍

所有类的核心在于你创建并利用的对象概念，这有助于模块化和易用性。在早期的迭代中，有一种被称为`struct`的原始类型。`struct`仍然存在，但主要被废弃，转而使用`class`。`struct`与 C++ 中的`struct`不同。

在我们深入讨论之前，让我们简要讨论访问权限。我们讨论过像`int`、`string`和`float`等内置类型。然而，你可以创建一个由数据片段和固有函数组成的整个类型。这被称为对象。

`Public`意味着对象及其内部数据可以被程序中的任何代码访问和修改。

`Protected`意味着对象及其内部数据可以被它的派生类访问（当我们学习继承和多态时，这就有意义了）。

`Private`意味着只有对象本身可以访问其数据。这对于安全和清晰至关重要。

开发者倾向于将`struct`看作功能有限的未保护对象，而倾向于将`class`看作功能强大且结构良好的对象。因此，除非你的对象功能很少且仅包含很少的数据，否则通常创建类更好。

看看这个`struct`声明。

```cpp
struct animal {

    int legs;

    string name;

    enum die_t { herbivore, omnivore, carnivore };

    die_t naturaldie_t;

};
```

```cpp
int main() {

    animal dog;

    dog.legs = 4;

    dog.name = "dog";

    dog.naturaldie_t = dog.carnivore;

    return 0;

}
```

这是声明新对象最简单的方法。你不应该在现有的函数内部声明它们。

让我们把那个结构体（`struct`）替换为类（`class`），因为以后我们将一直使用类，因为它们通常比结构体更安全、更好的选择。

在代码块中创建一个名为“animalsimulator”的新项目。虽然这不是最有创意的标题，但它能胜任我们需要的任务。清空`main.cpp`的内容，导入`iostream`并创建你的`main`方法。

在`main`方法上方，让我们声明一个名为`animal`的类。你的操作方式和声明结构体非常相似。为了方便说明，让它看起来像这样：

```cpp
Class animal {

    String name;

};
```

然后在你的`main`方法中，声明一个实例，并将它的`name`实例设置为你最喜欢的动物的名字。之后尝试构建。

你应该会收到一个显示为“`error: string animal::name is private`”的错误。

完美。这种情况应该是发生的，因为我们现在必须修复它。这就涉及到整个访问修饰符的概念。

修改你的类，使其看起来像下面所示：

```cpp
Class animal {

    Public:

    String name;

}
```

然后尝试构建。这次应该可以正常运行了。这是因为我们把字符串“name”设为了公共（`public`），这意味着类本身之外的其他方法/函数可以访问它。

尽管这通常被认为是一种坏习惯，因此我们将这样重写类：

```cpp
Class animal {

    Private:

    String name;

}
```

在类内部修改值的最佳实践是使用 get/set 方法。如果实现了 get/set 方法，类看起来会是这样：

```cpp
Class animal {

    Private:

    String name;

    Public:

    String getname() {

        Return this->name;

    }

    Void setname(string name) {

        this->name = name;

    }

}
```

现在，在你的`main`方法中，在声明任何动物实例后，不要直接修改它的名字，而是应该像这样使用 get/set 方法（假设你的实例`animal`称为“dog”）：

```cpp
Dog.setname("dog");
```

然后你可以通过在`main`方法中打印名字来测试这一点：

```cpp
Cout << “the name of my favorite animal is: “ << dog.getname() << "\n";
```

这些方法的工作原理是通过类内部的方法返回或设置变量的值。`this->`被称为`this指针`，它指向类给定实例的变量。每个对象都有访问其变量的权限，并且可以通过`this指针`直接修改它们。

不管怎样，你的代码运行非常完美。但如果你不想为每个类的每个实例都通过 get/set 来处理呢？我们将使用一种所谓的初始化函数（initializer function）。

修改你的类，使其看起来像下面所示：

```cpp
Class animal {

    Private:

    String name;

    Public:

    Animal(string name) {

        this->name = name;

    }

    String getname() {

        Return this->name;

    }

    Void setname(string name) {

        this->name = name;

    }

}
```

现在，在你的`main`函数中，删掉显示`animal x`后面跟着`x.setname(“name”)`函数的代码块。当你创建一个初始化函数时，你可以从一开始就设置某些变量。

例如，由于你的初始化函数接受参数`name`，你可以在声明变量时进行声明，并绕过整个`setname`操作。看这个代码作为示例：

```cpp
Animal dog("dog");

Animal elephant("elephant");

Animal bird("bird");
```

这些都是类`animal`的独立实例，得益于初始化函数，它们的名字在没有使用`setname`的情况下就被设置了。它可以接受你需要的任意数量的参数。这使得创建新对象变得极其简单而且非常精简。

现在我们已经简单讨论了声明对象之类的内容，让我们更多地谈谈对它们进行的具体操作。这里的`animal`代表动物。我们可以为整个类提供一组它们可以执行的方法。

让我们思考一下每种动物都会做什么。每种动物都会睡觉、进食和喝水，对吧？所以将这些内容包含在我们的类中，让类的每个成员对象都能执行，这并不算太奇怪。

假设我们有两种食物：肉类和植物，它们也都由各自的对象表示。我们可以为此创建两个不同的函数：

```cpp
Void eat(plant p) {

    // 此处写代码

}

Void eat(meat m) {

    // 此处写代码

}
```

尽管它们共享相同的名称，但你可以根据你放入的对象类型来调用其中任何一个，两者都会根据你包含的参数执行它们各自的代码。这被称为函数重载（function overloading）。它是面向对象编程中一项至关重要的技术，将帮助你创建功能强大且清晰的代码集，便于人们使用和理解。在下一章中，我们将开始探索对类可以做的一些更深层次的内容，包括使它们在面向对象编程中极其有用且实用的内部属性。

因为在我们学习类之初，要创建大量的类型，让我们先把“eat”留为一个不接受参数的空（`void`）函数吧。你的代码应该是这样的：

```cpp
Class animal {

    Private:

    String name;

    Public:

    Animal(string name) {

        this->name = name;

    }

    String getname() {

        Return this->name;

    }

    Void setname(string name) {

        this->name = name;

    }

    Void eat() {

        // 吃东西

    }

}
```

在下一章中，我们将涵盖更多关于类的深入概念。

### 对象与类

类是 C++ 的一项特性，它将 C++ 用于面向对象编程。记住，C++ 不是一种纯面向对象的语言，因为在纯面向对象中我们无法执行任何功能，但在 C++ 中是可以的。

### 类

它是一种用户定义的类型，拥有数据成员和成员函数，只有在为类创建了实例后才能访问它们。通常来说，类是表示类实例（即对象）状态和行为的蓝图。

数据成员在类定义中定义为变量，成员函数定义为函数。

C++ 中的`Class`与 C 语言中的`structure`相似，唯一的区别在于，默认情况下`classes`的访问控制权限是私有的，而`structure`是公开的。

C++ 通过`classes`提供了所有面向对象编程的重要特性，如封装、抽象和继承等。

类的每个对象都拥有其独立的数据成员拷贝，我们可以根据需要为该类创建任意数量的对象。

### 对象 (Objects)

类仅仅是一个蓝图。定义一个类时，不会为其分配内存。只有在为该类创建对象后，才会分配内存。这些对象是实例，拥有在该类中声明的数据变量，该类的成员函数在这些实例上运行。

对象通过特殊的构造函数进行初始化——这些是我们稍后会学习的特殊方法。析构函数是另一种特殊函数，在对象超出作用域时销毁对象。

```cpp
Class mobiles{

    Int price;

    Void calling (){}

    Void messaging (){}

};

Void main(){

    Mobile m1; // 为类 mobiles 创建的对象

}
```

### 构造函数 (Constructors)

构造函数是类似于类成员函数的特殊函数，承担着对象初始化的重要任务。当对象被创建时，编译器会调用构造函数。构造函数在为特定对象提供存储空间后，通过初始化其成员来初始化创建的对象。一个类至少有一个构造函数。如果类中没有显式定义构造函数，就会产生一个没有参数的默认构造函数。

```cpp
Class test

{

    Char c;

    Public:

    Test(); // 构造函数

};

Class test

{

    Int a;

    Public:

    Test(); // 构造函数的声明

    Test::Test() // 定义构造函数

    {

        A=1;

    }

};
```

### 析构函数 (Destructors)

析构函数是特殊的类函数，负责在对象超出作用域时销毁对象。当对象超出作用域时，编译器会自动调用析构函数。

析构函数的语法与构造函数相同，唯一的区别是使用波浪符号`~`进行声明。此外，析构函数没有参数。

```cpp
Class test

{

    Public:

    ~test(); // test 的析构函数

};
```

### 调用构造函数和析构函数的示例

```cpp
Class test

{

    Test()

    {

        cout << "a constructor been called";

    }

    ~test()

    {

        cout << "a destructor been called";

    }

};

Int main()

{

    Test test1; // 构造函数被调用

    Int a=1;

    If(a)

    {

        Test test2; // 再次调用构造函数

    } // test2 超出作用域，并调用了它的析构函数

}
```

在创建类时，你希望它们尽可能易于使用。任何类都可能需要提供一些基本操作：

- 它需要初始化自己
- 它需要清理内存和/或资源
- 它需要复制自己

所有这些对于创建良好的数据类型都非常重要。我们将使用测试来演示这一点。字符串必须能够即使在为空时也能进行初始化。它们应该依赖外部代码来实现这一点。一旦字符串被声明，就可以立即使用。当你完成它的操作后，它必须能够清理，因为所有字符串都分配了内存。当类被使用时，不需要调用另一个方法来完成；类会自动完成。最后，它必须能够像整数在变量之间复制一样，从一个变量复制到另一个变量。所有这些功能都应该是类的一部分，以便能够被轻松使用。

我们将逐个处理这三个特性，并看看 C++ 如何让这一切变得简单。

### 对象构造 (Object construction)

你可能已经注意到，我们在棋盘接口（代码的公开部分）中没有任何用于初始化棋盘的代码。我们现在可以修复这个问题。当声明一个类变量时，该变量需要能够被初始化：

```cpp
Chessboard board;
```



当声明一个对象时，运行它的代码被称为构造函数，它应该设置好对象，使其不需要初始化。构造函数也可以接受参数——你在声明特定大小的`vector`时已经见过了：`vector<int> v(10 );`。

`vector`构造函数被调用时值为`10`；新`vector`通过构造函数初始化，使其能够立即容纳`10`个整数。创建一个构造函数无非是声明一个与类名同名、没有参数且没有返回值的函数。你甚至不需要给它一个`void`值；返回值不提供任何类型：`enum space { empty_square, white_pawn /* and others */ };`, `enum playercolor { pc_white, pc_black };`。

```cpp
Class chessboard
{
    Public:
    Chessboard (); // 完全没有返回值！
    playercolor getmove ();
    space getpiece (int x, int y);
    Void make_move (int from_x, int from_y, int to_x, int to_y);
    Private:
    space _board[ 8 ][ 8 ];
    playercolor whose_move;
};

Chessboard::Chessboard () // 没有返回值
{
    Whose_move = pc_white;
    // 首先清空整个棋盘，然后添加棋子
    For ( int i = 0; i < 8; i++ )
    {
        for (int j = 0; j < 8; j++ )
        {
            // ... 代码
        }
    }
}
```

现在注意上面的构造函数位于公开部分。如果我们不把它设为私有，我们就无法创建任何对象实例。构造函数在创建对象的同一行被调用：

`Chessboard board; // 调用构造函数`

或者在分配内存时：

`Chessboard *board = new chessboard; // 这在内存分配时调用构造函数`

当声明多个对象时，构造函数按照对象声明的顺序运行：

`Chessboard a;`
`Chessboard b;`

像这样传递参数给构造函数：

`Chessboard board( 8 ); // 8 是 chessboard 构造函数的参数`

当你使用`new`关键字时，传递参数看起来调用了构造函数。可以通过参数类型进行重载，如果存在不同的初始化方法。例如，可以为`chessboard`创建第二个构造函数来接收棋盘大小：

```cpp
Class chessboard
{
    Chessboard ();
    Chessboard (int board_size);
};
```

函数的定义与任何类方法相同：

```cpp
Chessboard::Chessboard (int board_size)
{
    // ... 代码
}
```

关于语法的说明：虽然括号用于传递参数，但你不能用它们来声明无参数构造函数的对象。

你不能这样做：

`Chessboard board();`

正确的格式是：

`Chessboard board;`

然而，在使用`new`关键字时，可以使用括号：

`Chessboard *board = new board();`

这是`c++`解析中一个令人遗憾的小缺陷，因为这些细节被隐藏得非常晦涩。只需在声明带有无参数构造函数的对象时**不要**使用括号即可。

那么，如果没有声明构造函数会发生什么呢？

如果没有声明构造函数，`c++`会创建一个。它不会接受参数，也不会初始化`ints`、`chars`或任何其他原始类型，但它会通过调用每个类的默认构造函数来初始化每个类字段。

通常情况下，你应该创建构造函数以确保所有内容都得到妥善初始化。一旦声明了构造函数，`c++`就不会为你生成默认构造函数了。编译器假设你完全清楚自己在做什么，并且你将会创建你所需的构造函数。特别是，如果你创建了带参数的构造函数，代码将不再拥有默认构造函数，除非你显式地声明一个。

这可能会导致意外的后果。如果使用了自动生成的构造函数，然后你添加了一个带参数的非默认构造函数，那么依赖于自动构造函数的代码将无法编译。提供默认构造函数是你的责任，因为编译器不会为你做这件事。

### 初始化列表和 const 字段

如果类字段被声明为`consts`，则必须在列表中初始化：

```cpp
Constholder
{
Public:
    Constholder (int val);
Private:
    Const int _val;
};

Constholder::Constholder ()
: _val( val )
{}
```

`Const`字段不能通过赋值来初始化，因为这些字段一旦设置就无法更改。类尚未完全形成的唯一地方就是初始化列表，因此不可变对象可以在那里安全地设置。出于相同的原因，如果一个字段是引用，它也必须在列表中初始化。

## 第 8 章：库

### 标准模板库 (STL)

能够编写自己的数据结构是件好事。然而，正如你可能已经意识到的，这并不常见。但你并不是无缘无故之前的所有内容。你现在已经学习了许多如何根据需要构建数据结构，以及一些在编写数据结构时可能用到的更常用的结构。

不过，`c++`有一个非常酷的功能：一个可以复用的巨大代码库。它被称为标准模板库（`stl`），包含了最常见的数据结构，包括基于二叉树和链表的构建结构。这些结构允许你在创建它们时指定它们将存储什么数据类型，以便它们可以用于任何地方——结构化数据、字符串、`ints`等。

因为你拥有这种灵活性，`stl`在很多情况下可以消除你构建自己数据结构的需求。使用它可以从以下几个方面提升你的代码水平：

- 你可以开始根据所需的结构来思考代码，而不是必须亲自思考如何构建和实现它们。
- 你可以免费且方便地访问最佳数据结构实现，其空间使用和性能都针对大多数问题进行了优化。
- 你不再需要担心数据结构内存的分配和释放。

然而，像万事万物一样，使用该库也有其权衡：

- 你需要学习`stl`接口以及应该如何使用它们。
- 当你使用`stl`遇到编译器错误时，它们极其难以阅读和理解。
- 你无法在库中找到所有的数据结构。

彻底讨论`stl`需要一整本书，所以我只会为你概括你将从`stl`中使用的最常用结构。

#### Vectors (向量)

`stl`中包含一种数组的替代品——`vector`。这非常像数组，但它是自动调整大小的；你不再需要担心分配内存和移动元素。然而，`vector`的语法与标准数组不同。

数组的语法是：
```cpp
int_array[10];
```

而`vector`的语法是：

```cpp
#include <vector>
using namespace std;
vector<int> vector(10);
```

必须包含`vector`头文件以及`namespace std`。这是因为像`cout`和`cin`一样，`vector`是标准库的一部分。此外，当声明`vector`时，你必须提供存储在`vector`中的数据类型。这是通过角括号`<>`完成的：

```cpp
vector<int>
```

这利用了`c++`的一种名为模板（templates）的功能。`vector`代码的编写方式允许存储任何数据类型。你所做的就是告诉编译器`vector`正在存储什么类型。这实际上意味着我们这里有两种类型：数据结构类型（它决定了数据组织组织的方式）以及在数据结构中持有的数据类型。使用模板允许你在数据结构内部将不同的结构类型与不同的数据类型结合起来。

最后，当提供`vector`大小时，它必须放在括号中而不是中括号：

```cpp
vector<int> vector(10);
```

这是用于某些变量类型初始化的语法。为此，`10`的值被传递给称为构造函数的初始化函数，它设置了`vector`的大小。在我们引导学习的过程中，你将学习构造函数以及带有构造函数的对象。

一旦创建了`vector`，就可以像数组一样访问单个元素：

```cpp
for ( int i = 0; i < 10; i++ )
{
    vector[i] = 0;
    _array[i] = 0;
}
```

### 在 vector 上调用方法

`vector`提供的功能比数组多得多。你可以进行各种操作，例如在`vector`末尾添加元素。`vector`提供了函数来帮助此类操作，但函数的语法与我们之前使用的语法不同。

`vector`使用了一种名为方法（methods）的`c++`功能，如下所示：

```cpp
vector.size();
```

这是在`vector`上调用`size()`方法，它返回该大小。这非常像访问结构体字段，但你是在调用与结构体相关的方法。虽然方法对`vector`做了某些操作，但`vector`不需要作为参数传递给方法。语法已经知道要把`vector`作为隐式参数传递到`size`方法中。

下面的语法
`<variable>.<function call>(<args>);`

可以被认为调用一个与变量类型相关的函数。换句话说，它有点像写成：
`<function call>(<variable>, <args>);`

在示例`vector.size();`中：

它就像是写成：
`Size(vector);`

其他 vector 特性

`vector`还可以让增加存储的项数变得非常容易，而不需要重新分配内存。例如，向`vector`中添加额外的项可以如下所示：

```cpp
A_vector.push_back( 10 );
```

这在`vector`的末尾添加了另一个值为`10`的项。`vector`会自动处理大小调整工作。如果你想用数组实现此操作，则必须分配内存、复制值并添加新项。虽然`vector`确实会进行内存分配和复制，但它是以一种智能的方式完成此的，使其不需要在每次添加新项时都重新调整大小。

然而，尽管你可以使用`push_back`向`vector`的末尾添加项，但单独使用括号的操作效果是不相同的。括号让你只能处理已经分配过的数据，这主要是为了防止在你不自知晓的情况下进行内存分配。

所以，像下面这样的代码：

```cpp
Vector<int> a_vector( 10 );
A_vector[ 10 ] = 10; // 最后一个有效元素是 9
```

是无法运行的，并且可能导致程序崩溃。更不用说，它是危险的。像这样写：

```cpp
Vector<int> a_vector( 10 );
A_vector.push_back( 10 ); // 为 vector 添加一个新元素
```

就可以调整`vector`的大小了。

# 映射 (Maps)

我们之前提到过`map`使用一个值来查找另一个值，这在编程中很常见，例如当你想实现一个邮箱地址簿（通过名称查找地址），或者一个通过账户号码查找账户或允许用户登录游戏的程序。

STL 为我们提供了`map`类型，允许我们指定键（key）类型和值类型。一个示例是存储邮箱地址簿的数据结构；可以如下实现：

```cpp
#include <map>
#include <string>
Using namespace std;
Map<string, string> name_to_email;
```

我们必须告诉该结构有两种类型：`string`作为键，另一个`string`作为值（在此例中，是邮箱地址）。

这些`map`的有用功能之一是，当使用`map`时，语法也可以像数组一样使用。如果你想添加值，它非常像数组，区别是使用键类型代替整数：

```cpp
name_to_email[ “billy bunter” ] = “billybunterthise.mailaddress.com”;
```

从`map`中获取值也大相同：

```cpp
Cout << name_to_email[ “billy bunter” ];
```

你获得了数组的简单性，同时拥有了存储任何想要类型的能力。更棒的是，与`vector`不同，`map`的大小在使用`[]`运算符添加元素之前不需要设置。

从`map`中移除项也同样简单。假设你和`billy bunter`闹翻了，想从从你的地址簿中移除他。你可以使用`erase`方法来做到：

```cpp
name_to_email.erase( “billy bunter” );
```

你可以使用`size()`方法来检查`map`的大小：

```cpp
name_to_address.size();
```

使用`empty()`方法查看`map`是否为空：

```cpp
If ( name_to_address.empty() )
{
Cout << “地址簿是空的。我希望你没有删掉它。”;
}
```

不要将此与清空`map`的方法混淆。清空是使用`clear()`方法完成的：

```cpp
name_to_address.clear();
```

由于 STL 中命名规范的一致性，相同的方法也可以用于`vector`。

## 迭代器 (Iterators)

除了数据存储和单独访问的能力外，你还可以通过数组或`vector`遍历数据结构中的所有项，这只是使用长度来读取每个元素的一种情况。但对于`map`，因为它们同时具有数值型和非数值型的键，你不能总是通过计数器进行迭代。为了解决这个问题，STL 为我们提供了迭代器，它是一个允许你访问数据结构元素的变量，即使该数据结构通常没有很好的方法可以做到这一点。我们将从查看如何在`vector`中使用迭代器开始，然后转向元素。其思想是迭代器将存储结构中的位置，以便你可以使用该位置来访问元素。当你调用迭代器上的方法移动到下一个元素时。

声明迭代器需要一些特殊的语法。对于一个整数型`vector`，它看起来像这样：

```cpp
Vector<int>::iterator
```

这句话的意思是你有一个`vector`，并且想要一个适用于特定类型的迭代器，这就是为什么我们使用`::iterator`。因为迭代器标记了结构中的位置，所以是从数据中请求迭代器：

```cpp
vector<int> c;
c.push_back( 1 );
c.push_back( 2 );
vector<int>::iterator itr = c.begin();
```

`begin()`方法调用将返回一个允许你访问`vector`第一个元素的迭代器。迭代器可以被类似于指针——提到结构中的元素位置，或使用它来获取元素。在我们的情况下，我们使用这种语法读取`vector`的第一个元素：

```cpp
Cout << *itr; // 输出 vector 的第一个元素
```

我们使用`*`运算符与指针相同；考虑到两者都存储位置，这是合乎逻辑的。如果你想要下一个元素，则递增迭代器：

```cpp
Itr++;
```

这让迭代器知道它需要移动到下一个元素。也可以使用前缀运算符：

```cpp
++itr;
```

你可以通过与迭代器和`end`迭代器进行比较来判断是否已到达末尾；要这样做，请调用：

```cpp
c.end();
```

如果你想要遍历整个`vector`的代码，它看起来像这样：

```cpp
For ( vector<int>::iterator itr = c.begin(); itr != c.end(); ++itr )
{
Cout << *itr << endl;
}
```

我们可以使用类似的方法遍历`map`，但请记住`map`不存储单值；它存储键/值对。当对迭代器解引用时，它有两个字段——一个键，一个值：

```cpp
Int key = itr->first; // 从迭代器获取键
Int value = itr->second; // 从迭代器获取值
```

下面的代码是以易读的格式显示`map`的内容：

```cpp
Void displaymap (map<string, string> map_to_print)
{
For ( map<string, string>::iterator itr = map_to_print.begin(), end = map_to_print.end(); itr != end; ++itr )
{
Cout << itr->first << " —> " << itr->second << endl;
}
}
```

这段代码与遍历`vector`非常相似；区别在于使用了`map`数据结构以及迭代器的第一个和第二个字段。

# 检查 map 中的值

有时你想能够查看给定的键是否已存储在`map`中。假设你正在地址簿中查找某人。你使用`find()`方法查看指定值是否存在，如果存在，则检索它。返回一个迭代器，它要么具有指定键的对象位置，要么在未找到对象时为结束迭代器。

```cpp
Map<string, string>::iterator itr = name_to_email.find( “billy bunter” );
If ( itr != name_to_email.end() )
{
Cout << “再次见到 billy 的感觉真。他的邮箱是: " << itr->second;
}
```



我仅触及了`stl`的基础，但你现在已经有了足够的信息来使用该库中的一些基础类型。`vector`可以完全取代数组，如果你不想花时间进行插入和修改，`vector`也可以用来替代链表。一旦掌握了`vector`类型，你几乎没有理由使用数组，而这些理由中的大多数都是高级用法，例如在处理文件输入输出（file i/o）时，我们将在指南的末尾讨论这一点。

最实用的单一数据类型是`map`。使用`map`可以轻松编写复杂的程序，而无需过多担心数据结构的创建；相反，你的注意力可以集中在解决问题上。在某些方面，`map`可以替代基础的二叉树。大多数情况下，你不需要深入研究二叉树的实现，除非有特定的性能需求或你明确需要树形结构。

这正是`stl`真正的威力所在：在80%的时间里，它为你提供了所需的内核结构，让你能够自由编写解决问题的代码。而在其余的时间，你需要相关知识来构建和实现自己的数据结构。

有些程序员更倾向于使用自己的代码而不是现成的代码。大多数时候，你不应该使用自己的数据结构；内置的结构更快、更好且更完整。然而，了解如何构建确实会让你对使用它们有更深刻的见解。

那么，你什么时候可能想使用自己的结构呢？假设你想要一个计算器，允许用户输入算术表达式，然后按照正确的运算顺序对输入进行求值。例如`4*9+8/3`，其评估方式是在加法之前完成除法和乘法。

这种结构可以很容易用树来考虑。你可以这样表示`4*9+8/3`：

```
        +
       / \
      *   /
     / \ / \
    4  9 8  3
```

每个节点通过两种方式之一进行评估：

- 如果节点是数字，则返回该值。
- 如果节点是操作符，则计算两个子树的值并执行操作。

构建这样一棵树需要一个原始数据结构；你不能只用`map`。如果你只有`stl`，处理这个问题将会很困难。然而，一旦你理解了递归和二叉树，就会变得简单得多。

# 第 9 章：stl

## 容器、算法、迭代器

一个常见的误区是将 C++ 标准库称为`stl`。`stl`，或标准模板库，是过去某个时候开发的标准。C++ 标准库是一组模板，其中许多是从`stl`中采纳。`stl`现在已经被弃用，但仍保留了一些极其实用的模板。

标准库以容器（containers）的形式为这个问题提供了解决方案。容器管理相同类型的数据集。它们包括`vectors`、`sets`和`lists`等。

`vectors`与数组非常相似，但它们会处理自己的存储和大小。

就像字符串一样，你需要导入`vector`库来使用该模板：

```cpp
#include <vector>
```

现在你能够访问有关`vectors`的所有内容。你可以这样声明一个模板：

```cpp
template<type> name;
```

假设我们回到之前的示例，创建一个自动调整大小的成绩数组。我们会这样声明它：

```cpp
vector<int> grades;
```

如果你使用了推送（push）和弹出（pop）的概念，那么向模板中添加值非常简单。你向`vector`中`push`一个新值，或者从它中`pop`出一个值。假设你想添加的第一个成绩是`55`，我们可以这样做：

```cpp
grades.push_back(55);
```

你现在已经向`vector`添加了你的第一个值。如果你想添加一组值呢？幸运的是，在 C++ 中，你也可以以类似于在数组中使用`vector.insert()`初始化一组值的方式来插入一组`vector`。这接受两个参数：你开始插入的索引以及你想要插入的值。如果你在`vector`中有多个值，你可以直接使用`vector.end()`来找到插入点。

```cpp
grades.insert(grades.end(), {96, 64, 75});
```

在之前的版本中，你需要创建一个临时数组来插入数据。

```cpp
int[] tmp = {96, 64, 75};
grades.insert(grades.end(), tmp + 4);
```

为了遍历列表中的每一个项，你可以使用其他语言中被称为`for each`循环的东西。如果我们想打印列表中的每一个项，我们将执行以下操作：

```cpp
for (int i : grades) {
    cout << i << "\n";
}
```

如果我们使用的不是原始数据类型，而是对象呢？这有支持，我们将使用一种称为迭代器（iterators）的东西。通过迭代器的使用，你可以访问对象的方法（例如字符串的`.length()`或`.substr()`）。假设我们有一个名为`j`的字符串`vector`，并且想要打印每个字符串的长度，那么：

```cpp
for (string i : j) {
    cout << i << " - string length: " << i.length() << "\n";
}
```

你可以对创建的任何对象执行此操作，但我们将在下一章实际开始创建对象时更显式地讨论这一点。

另一种类型的容器`lists`的功能与`vectors`非常相似。这两种之间的具体差异对于初学者来说是难以理解的。尽管如此，关于这两种容器的通用规则是：通常情况下应该使用`vector`，除非你必须在容器末尾以外的地方不断添加或删除元素。

另一种类型的容器称为关联容器（associative container），它以键值对和映射值进行格式化。它通常根据键进行排序。最著名的关联容器类型被称为`map`。当你需要将一组数据与特定特征关联起来时，这非常棒。一个现实世界的例子是，商店的库存系统可以用`map`来维护，其中 SKU 代码（整数 - 键）和物品名称（字符串 - 映射数据）。

为此，你需要导入`<map>`并通过以下方式声明`map`：

```cpp
map<int, string> inventory;

inventory[00400030] = "tamagotchi, blue";
inventory[00400031] = "tamagotchi, white";
inventory[00324359] = "twilight, dvd";
inventory[44539294] = "dark souls, xbox 360";
```

如果你想在代码后面调用某个特定元素，可以执行类似的操作：

```cpp
cout << "inventory[00400030] is: " << inventory[00400030] << "\n";
```



调用`inventory[00400030]`将打印映射值，这里是"tamagotchi, blue"。

另一种关联容器是`set`。`set`的功能与`map`非常相似，只是它们不允许重复。`map`允许重复的值，但不允许重复的键。

我们已经读到了本书的末尾，但这只是你编程生活这段漫长且果实累累旅程的开始。掌握了`C++`的基础知识，现在是时候开始真正的学习了。开始编写那些程序吧！开始实现数据结构和算法吧。

如果你喜欢学习`C++`，那么这门奇妙的语言还有很多可以学习和做的内容。请务必通过本系列的第二本书继续你的旅程，它在保持对初友好的同时，涵盖了稍微复杂一些的话。

`C++`编程语言是一种具有竞争性的通用平台，它借用了命令式编程范式的一些特性，并可以在任何平台上运行。它被称为一种命令式编程语言，因为它通过步步为营的过程来实现其目标。该语言使用面向对象编程的概念来设计和实现复杂程序。

下一步是开始用`C++`语言编写你想要的一些不同程序和代码。

即使你只是刚起步，只想花时间练习本指南中的一些代码，你仍然处于正确的道路上，能够使用这种语言取得出色的成效。

在旅程中，你通过自己的编码实践获得的练习越多，编写和创建你自己的代码就会变得越容易。

`C++`语言是一个独特的工作选择，它能帮助我们创建一些真正强大且高效的代码，而这种语言中发现的功能与我们能够使用的任何其他语言都不同。

所有这些在你旅程途中想要编写某些代码时可能都很重要，当我们完成本指南时，你应该觉得已经准备好处理这些内容并将它们添加到你自己的代码中了。

正如我们所看到的，在使用`C++`语言方面，我们可以做的事情非常多。

无论你是初学者，还是已经在编程编码领域工作了长期的人，它都是世界上最好的编程语言之一。

当你准备好开始自己的编码旅程，并希望在短时间内创建出一些自己的程序时，`C++`编程语言利用OOP范式的特性来开发和执行程序。这些特性包括使用对象、类、数据抽象和封装、继承以及多态。

程序侧重于使用数据而非过程来解决现实世界的问题。程序试图通过提高程序的数据安全性、促进代码重用性以及利用继承特性来编写高效程序，从而消除其他传统编程语言的缺点。

与许多其他OOP语言一样，`C++`支持各种构建块。在本教程中，你学习了在处理简单到复杂的程序时如何使用各种内置数据类型。数据类型分为基本数据类型、派生数据类型和抽象数据类型。你不仅学习了如何使用基本或标准数据类型，还学习了如何定义你自己的自定义数据类型。

享受你的旅程。如果你在编程时并不快乐，那么它就不适合你。让它变得有趣，让它变得兴奋，让它成为你早晨起床的。

祝你的旅程顺利。

# 第 5 册：初学者 C#

一本构建真实项目和应用的全面指南

vera Poe

## 引言

欢迎学习`C#`编程，非常感谢你选择这本书！

无论你是经验丰富的程序员还是一个完全的新手，这本书的编写都是为了帮助你快速学习`C#`编程。

到书结束时，你应该能够毫无问题地编写自己的`C#`程序。事实上，我们将作为书末项目的一部分一起编写一个简单的薪资软件。准备好开始了吗？

大多数人害怕学习新的编码语言。他们知道这会为他们使用电脑做的事情打开很多大门，但他们担心编码本身对他们来说太难学习和上手工作。如果你不花适当的时间学习一种新的编程语言，整个编程过程可能会很困难。但当涉及到寻找一种帮助你编写任何想要代码的好语言时，是时候看看`C#`了。这本书将带你了解一些。

## `C#`有什么特别之处？

涉及到一种语言时，你可能首先想了解的是为什么`C#`是特别的，以及你想学习它的原因。有很多语言可供选择，但你会发现`C#`带来了许多好处，我们将在本指南中探索其中一些。虽然在你想要开始时有很多不同的选择，但没有哪一个像`C#`一样优秀。

选择`C#`的一些好处包括：

### 它能够利用大型库

作为初学者，你会在学习过程中学习很多代码部分，但你可以配合`C#`使用的库是一个极大的资源。你甚至可以对代码进行一些更改，使其按照你想要的方式运行。

### 自动释放函数

当你使用其他编程语言时，你必须检查并移除你拥有的项。这会占用你的时间并可能是一个麻烦。`C#`会为你完成所有这些工作，让事情变得更快更简单。

### 易于学习

`C#`被广泛认为是你可以学习如何上手的最简单语言之一。虽然有少数部分比某些其他语言更复杂，但这并不是一个困难的，随着你继续使用，你会很快开始识别出代码的不同部分。

### 兼容 Windows 计算机以及其他系统

这种编程语言最初是为了在Windows计算机上运行并帮助你为它们设计程序而创建的。但只要在上面下载`.NET`，它也可以在mac、linux等其他操作系统上良好地运行。Windows有许多易于使用的优秀产品，特别是对于初学者来说，所以一旦你开始，一定会获得出色的结果。

### 与 .NET 工作

这使得使用此程序变得非常容易，并可以在学习其他程序之前掌握基础知识。即使你选择坚持使用这种编程语言，你会发现它足够强大，可以完成你想要的大部分编码，而不会像在其他程序中可能会遇到的那些烦恼。

准备好进入`c#`编程的世界了吗？让我们开始吧。

# 第 1 章：c# 的剖析

### c# 简介

学习编码将在这一过程中为你带来许多益处。它将让你创建理想的程序和应用程序变得更加容易。它将通过许多简单易用的选项帮助你提升职业生涯，让我们能够充分发挥新技能，并获得更多收入。此外，在某些时候，学习如何使用`c#`是至关重要的，因为它能让我们更深入地了解计算机以及它们的工作原理。

在进行编程时，有很多很棒的选择。许多语言是为了用于于不同的项目而开发的，有时它们也适用于不同类型的进程和应用程序。虽然根据你最初想用该语言实现的目标，其中许多语言都很有用，但我们将观察如何使用`c#`语言，以及这种语言对于我们的需求有多大。让我们深入研究`c#`语言，以及如何让它满足我们的编程需求。

我们首先需要查看的是`c#`语言。`c#`是一种优雅且面向对象的语言，它非常有帮助，因为它允许程序员编写并构建各种健壮且安全的应用程序，而所有这些程序都将在`.net`框架上运行。你可以在多种项目中使用`c#`，包括Windows客户端应用程序、Web服务、客户端/服务器应用程序、XML数据库应用程序等。

当我们使用`c#`工作时，我们会发现从视觉上看，它为我们提供了一个高级代码编辑器，以及一些更易用的用户界面设计器、一个集成的调试器以及其他一些确保基于此语言开发应用程序变得更容易工具。

`c#`语言的奇妙之处在于，它不仅具有很高的表达能力，能够帮助我们处理许多想要处理的复杂代码，而且易于学习且简单。`c#`语法中的大括号看起来会很熟悉，特别是如果你以前用过`java`、`c++`和`c`的话。熟悉这些语言的开发者会发现，由于相似性，学习`c#`并不需要长时间。

`c#`非常有用，因为它可以简化一些在`c++`语言中出现的问题，并为我们提供一些强大的功能，包括可以为null的值类型委托、枚举、lambda表达式和直接内存访问。这些功能在`java`等语言中都是无法直接提供的。

此外，你会发现`c#`语言能够支持一些泛型方法和类型，这将有助于我们提供更高的类型安全性和性能。它带有一些迭代器，允许集合类的实现者定义自定义的迭代行为，这些行为客户端代码可以轻松使用。

由于这种语言属于面向对象的范畴，它能够支持许多属于该类别的主题和选项，我们稍后将详细探索这些内容，包括多态、继承和封装。我们使用的所有方法和变量都封装在这些类定义中。类可以直接继承自一个父类，但可以设置为实现任意数量的接口。

该语言中的方法可以被重写；当我们使用`c#`时，`struct`类似于类，但这意味着它是一个栈分配类型，并且支持继承。

除了我们刚刚查看的一些基本原则外，你会发现`c#`会让开发某些组件变得更容易，这些组件包括：

大多数常见功能，如数据结构、浏览、版本控制甚至调试，都存在那里，帮助开发者执行操作而无需在不同的应用程序之间来回。

属性（Attributes）提供运行时关于某些类型的元数据。

`Linq`代表集成查询（Integrated Query），它是非常有用的，因为无论我们处理什么种数据源，它都能为我们提供查询能力。

在学习`c#`时，我们可以获得许多益处。它是一种面向对象的语言，当我们利用稍后将讨论的`.net`平台时，它让我们更容易组织和将事物保持在一起。

在详细介绍如何编码以及我们能用`c#`做什么之前，我们需要更好地了解什么是IDE以及为什么要用它。首先，IDE是一个集成开发环境，它是我们可以使用来帮助应用程序开发的程序。通常，这是一种GUI或图形用户界面，旨在让任何开发者的构建工作变得更容易。

IDE背后的概念演变自某些基于命令的软件，而在当时，这种软件并没有菜单驱动的软件那样实用。一些现代IDE将更多地用于我们的视觉化编程背景，而这些应用程序将通过移动代码节点或编程构建块（这将生成流程图和结构化图）来快速高效地创建。然后，根据你对该过程的预期，对它们进行编译或解释。

花时间选择一个良好的IDE是非常重要的，在这一过程中，有几个因素是我们需要考虑。例如，我们需要花时间查看语言支持、操作系统需求以及一些成本。有时我们想要使用的IDE是免费的，但有时这些版本的功能是有限的。这通常取决于你想用该语言设计什么，以及哪些功能对你的编码需求很重要。

目前有几种适用于`C#`语言的优秀IDE。进行研究并了解更多关于它们如何运作的，以及哪些具有你希望获得最佳结果的功能，是非常重要的。当你能做到这一点时，编写你想要的代码将变得容易得多。

### 如何在 linux 和 mac 上使用 C#

虽然`C#`被认为是一种Windows语言，但我们也可以在linux和mac电脑上运行并使用它。我们可能需要额外执行几个步骤，而且有时我们在Windows上习惯看到的某些功能将会消失，但在其他操作系统上使用此选项我们仍然会看到很多好处。

对于linux系统，作为mono项目一部分的monvelop ide应该是你在linux电脑上开发某些`C#`代码正需要的工具。你安装它最简单的方法是使用为ubuntu开发的monvelop包。有时推荐使用winforms工具包，但这个工具的运行起来不会那么高效，也不如易于操作。

我们还可以设置该语言在mac电脑上运行。第一步是下载一个IDE，visual studio code通常是这里的最佳选择，因为它与mac配合良好，并且在保持易用性的同时仍能提供你所需的功能。只需访问visual studio网站，然后确保点击下载mac版的按钮。这应该以zip文件的形式下载你需要的内容。

一旦完成设置，你就可以解压文件并将其拖到应用程序（Applications）文件夹。你应该可以在那里运行它。下一步是进入并下载`C#`扩展。你可以进入visual studio code，并打开实现该功能所需的扩展。

现在，当你在此过程中进行操作时，你会发现扩展视图的顶部有一个搜索栏。你可以在这里输入"C#"。你需要的是由微软提供的，所以请确保点击这。点击安装，你就可以准备就绪。

但请记住这个过程：`C#`语言是为在Windows系统上运行得最好而开发的。因此，如果你在Windows系统上，你可能发现这种语言易于使用，而且你在编码中寻找的所有功能和特性更有可能出现在你预期的地方。

这并不意味着你完全无法在mac电脑上运行它。它仅仅意味着你需要额外花几个步骤来完成设置，而且实现你想要的某些事情可能没有那么容易。花时间在linux或mac电脑上熟悉`C#`语言，对于帮助你在过程中获得最佳结果非常重要。

### 如何获取 C# 编译器

有几种良好的`C#` IDE选项可以使学习变得简单顺畅；在本书中，我们将使用visual studio 10自带的版本。也可以使用旧版本。

如果我们无法获取visual studio 19的专业版，一个选项是社区版，即visual studio community。它是免费的，并可以直接从门户网站下载：`https://www.microsoft.com/vs/express`。一旦下载了编译器，我们可以从开始菜单中选择它来启动程序。

界面分为两个部分：左侧是搜索栏，我们可以在那里找到最近的项目；在主页的右侧，我们将看到创建新项目、打开文件夹或克隆仓库的选项。安装完成后，我们就能看到界面。

在右侧，有解决方案管理器（solution explorer），它提供了有关我们正在开发的项目的信息。我们将在本书后面的某些窗口中看到显示的细节。

![Image00094](img/Image00094.jpeg)

在底部，我们找到了另一个窗口；在这个区域，通常是编译器用来与我们通信的部分。例如，我们将看到指示程序错误的窗口；在窗口的顶部，我们将看到菜单和工具栏。

如果由于任何原因我们关闭了源代码编辑器，或者它没有出现在我们的界面中，那么找到它最简单的方法是通过解决方案管理器。只需进入代表你源代码的文档并双击它；显示源代码编辑器的窗口就会出现。

编辑区域允许我们编辑程序，如果我们知道如何使用microsoft word或记事本等任何类型的文本编辑器，这非常简单。

为了更熟悉`C#` Visual Studio，最好的方法是创建第一个项目并进行操作。我们将生成一个小型程序，它会在控制台中向我们发送消息，然后我们将添加其他元素，以便探索用户界面的不同窗口。

## 在 Visual Studio 2019 中创建新项目

在Visual Studio 2019中创建新项目主要有两种方法。第一种仅需点击Visual Studio主界面右下角的`create new project`。

随后在搜索框中输入`console`，并选择`Console App (.NET Framework)`选项，然后如下所示点击`next`按钮。

![Image00095.jpg](img/Image00095.jpeg)

然后通过名称和位置配置你的新项目，保存，并点击`create`按钮。一切就绪，Visual Studio将立即为你创建一个新项目。

另一种创建项目的方法是选择`File`菜单，然后我们点击下图所示的`new project`选项；通过这种我们可以看到一个显示某些相关选项的对话框。

![Image00096.jpg](img/Image00096.jpeg)

在对话框的右侧，列出了我们可以创建的不同类型的项目；对于本示例，我们必须选择由`Console Application`指定的项并点击`next`按钮。

**注意：** 如果由于某种原因，我们关闭了源代码编辑器或它没有出现在我们的用户界面中，找到它最简单的方法是通过`Solution Explorer`（解决方案管理器）。只需转到代表源代码的文档并双击它；源代码编辑器的窗口就会出现。

![Image00097.jpg](img/Image00097.jpeg)

在左侧，我们将编写项目的名称，在这种情况下为`myproject`。我们创建的每个新项目都有自己的名称；然后我们只需按下`create`按钮。

![Image00098.jpg](img/Image00098.jpeg)

几秒钟后，`C#` express会为我们创建项目。Visual Studio和社区版使用解决方案和项目。一个解决方案可以包含多个项目，例如，Office拥有Word、Excel和PowerPoint等不同产品。Office是一个解决方案，每个产品都是一个项目。项目可以是独立程序或库，可以包含一个或多个文档，这些文档可以是源代码和附加资源。

![Image00099.jpg](img/Image00099.jpeg)

我们可以看到用户界面发生了一点变化；窗口已经向我们显示信息，我们还可以看到编辑区域显示了我们程序的骨架。

![Image00100.jpg](img/Image00100.jpeg)

`Solution Explorer`以逻辑方式向我们展示有关解决方案的信息；如果观察的话，它像一棵小树。在根部，我们找到解决方案；解决方案中的每个项目都将是一个分支；每个项目反过来也有自己的划分。在我们的案例中，我们看到了三个元素：其中两个元素是文件夹；在其中一个，我们保留了项目的属性，在另一个中是引用（在书中我们将使用这些文件夹）。第四个元素是一个名为`program.cs`的文档；它代表我们保存应用程序源代码的文档。我们看到`C#`程序的扩展名是`.cs`。

在编辑区域中，我们可以看到有一个骨架，从那里我们可以创建程序。要理解我们拥有什么，需要了解一个概念：命名空间（namespace）。命名空间是一种逻辑分组；例如，所有与数学相关的代码都可以组在命名空间内。命名空间的另一个用途是解决名称冲突；例如，假设我们有一个巨大的项目，几个程序在上面工作。两个或多个程序可能创建了同名的方法；这会产生冲突，因为程序不知道使用哪一个。解决此问题是每个程序都有自己的命名空间，并根据我们想要使用的版本进行引用。.NET framework为我们提供了各种命名空间，其中已经创建了数千个类和方法供我们使用。当我们想要使用其他程序或我们自己在命名空间中找到资源时，我们必须使用名为`using`的`C#`命令。

正如我们在代码顶部看到的，我们对应用程序所需的命名空间有多个引用；如果我们需要添加更多命名空间，将在该部分进行。以下是定义我们项目的正确命名空间；操作如下：

```csharp
namespace myproject

{

}
```



我们正在创建的命名空间称为`myproject`。正如我们看到的，命名空间使用`{}`作为分隔符；这被称为代码块，放置在`{}`之间的一切都属于该命名空间。在这里将需要编写与应用程序相应的代码。

在代码块内部，我们找到了类的声明。C# 是一种面向对象的语言，这就是为什么它需要我们为应用程序声明一个类。类有自己的代码块，在我们的应用程序中它将被称为`program`。类的概念将在本书的第 10 章介绍。所有程序都需要一个起点，一个指示程序执行从何开始的地方。在 C# 中，与其他语言一样，起点是`main()`函数；该函数也有自己的代码块。在这个函数内部，我们通常会放置应用程序的主代码，尽管可能有更多的函数或方法以及类。函数的各个和特征将在本书的第 5 章介绍。

现在是创建我们的第一个应用程序了。我们将如下所示修改函数代码。当我们在`main()`内部添加语句时，必须注意它发生在点号放置之后立即。

### 编译应用程序

一旦我们完成了程序的编写，就可以像之前学的那样进行编译；这将生成运行时执行时使用的程序集。

要编译应用程序，我们必须选择`Build`菜单然后`Build Solution`或简单地按下`F6`按钮。编译器将开始工作，在状态栏中，我们将看到解决方案已成功编译。

### 运行应用程序

一旦编译成功，我们就可以运行程序并查看它是如何运行的。为此，我们有两个选项：带调试运行和不带调试执行。在快速版中，只显示带调试的执行，但我们可以使用按键`Ctrl+F5`不带调试执行，或通过`Tools`菜单添加。

调试器是一个帮助我们纠正运行时错误以及逻辑错误的程序。我们最好使用不带调试的执行，仅在需要时才使用带调试的执行。现在我们将运行应用程序；为此，我们按下`Ctrl + F5`键。

当程序执行时，会弹出一个窗口，我们称之为控制台，它显示程序的执行情况。通过这种方式，我们可以读取我们在示例中放置的消息。

由于这是一本 C# 编程的入门书籍，我们将在控制台中运行所有程序。一旦你理解了核心概念，就可以学习如何用 C# 编写形状、形式和图形界面。这种编程并不困难，但它需要对象对象编程的基础知识。

### 如何检测程序中的错误

有时我们可能会写错程序；当发生时，应用程序将无法编译或执行；如果发生这种情况，我们必须更改错误的地方。

让我们故意写一个错误，以便我们观察编译器的行为。

在程序中，我们将`console`更改为`consoli`并重新排列了`namespace`和`helloworld`的顺序；这将导致错误；现在，我们可以尝试再次编译并看看发生了什么。

![Image00101.jpg](img/Image00101.jpeg)

正如我们所知道的，用户界面底部出现的窗口是编译器用于通信的；我们看到出现了一个列出错误列表的窗口。在下一本书中，我们将学习如何使用它；现在，我们只需要知道，解决列表中的第一个问题是必要的，而且我们可以通过双击它直接跳转到错误处。

### 类视图

现在我们要检查类视图。在此视图中，我们可以获取有关正在创建解决方案的信息，但与解决方案资源管理器不同，这些信息按逻辑排列的。

通过此视图，我们可以快速找到解决方案的命名空间，以及它们包含的类；如果我们愿意，还可以查看每个类中的方法。此视图不仅让我们能够观察逻辑信息，还让我们具备在代码中快速导航的可能性。

在社区版中，没有预先配置的选项，因此有必要向视图（View）菜单添加命令。

要显示类视图，我们必须进入视图（View）菜单，然后选择类视图（Class View），或者只需按下`ctrl + w`，用户界面中就会出现一个窗口。

![Image00102.jpg](img/Image00102.jpeg)

类视图窗口分为两个部分；上部分显示元素的逻辑和层次关系，而下部分显示组成特定类的方法。

![Image00103.jpg](img/Image00103.jpeg)

在树的根节点，我们找到了项目；它将包含必要的引用和`helloworld`的命名空间。如果有更多命名空间，它们会在打开`helloworld`命名空间时出现在那里；在其中我们可以找到未声明的类。在这种情况下，我们只有一个`program`类；如果我们选择它，将看到底部显示在内部声明的元素。在我们的示例中，我们有`main()`方法。

如果此时我们双击任何方法，我们将自动跳转到定义它的代码处。由于我们的程序非常小，我们可能看不到这种做法的优势，但在具有数千行代码的程序中，能够快速导航是一个巨大的优势。

### 配置编译器菜单

为了在菜单中添加所需的选项，我们必须遵循一系列非常简单的步骤。首先，进入工具（Tools）菜单并选择自定义（Customize）选项。

弹出一个对话框，在其中我们必须选择命令；在此部分，我们可以选择想要向其添加命令的菜单，例如视图（View）菜单。

![Image00104.jpg](img/Image00104.jpeg)

列出了当前的菜单命令，我们点击想要插入新命令的区域，并按下添加（Add）命令按钮。这将弹出一个新的对话框，显示了分类后我们可以添加的所有可能的命令。

在类别中我们选择视图（View），在类视图（Class View）命令中，该命令就是让我们拥有类视图的命令。无调试启动（Start Without debugging）命令位于调试（Debug）类别中。

![Image00105.jpg](img/Image00105.jpeg)

到此为止，我们分析了最重要的基本概念，从下一章开始，我们将开始学习 C#。

### C# 的主要功能

C# 是一种新的面向对象的语言，它使程序员能够在 Microsoft 上编写各种应用程序。Microsoft 提供了一系列工具来最大化利用 C#，这 是一种高级语言。C# 的功能主要为以下内容设计：

- Windows 设计
- 控制台设计
- 移动设计
- Web 设计
- 服务设计
- Windows 控制

C# 是一种强大的语言，具有以下特征，是 Web 开发的理想选择。

### C# 的主要特性

C# 语言几乎结合了当前高级语言的优点，并具有：

### 简洁的语法

C# 语言像 Java 一样使用统一的运算符来消除复杂的表达式并使其形式简单。

### 面向对象的设计

C# 语言根据面向对象的思想设计，因此它具有封装、继承和多态。C# 只允许单继承，这意味着一个类没有多个基类。在 C# 中没有全局函数或全局变量。所有常量、属性、方法和事件必须封装在类中，这使得代码更具可读性。

### 与 Web 的深度集成

在 C# 中，复杂的 Web 编程和其他网络编程更像操作对象，从而简化了大规模和分布式开发。内置的 C# 组件可以方便地为 Web 服务，并被运行在任何系统上的任何语言调用。

### 完善的安全错误处理

语言的安全错误处理能力是衡量一种语言的重要基础。C# 可以消除软件开发中的许多常见错误，并提供完整的安全性能。

默认情况下，从互联网和内部网下载的代码不允许访问任何本地文件和资源。C# 不允许未初始化的变量，并提供了如方便检查和溢出检查等功能。

### 版本处理技术

C# 语言内置了版本控制功能，例如处理函数重载和执行以及特性支持等，以确保复杂软件的便利开发和升级。

### 灵活性与兼容性

在托管状态下，C# 语言不能使用指针，而是使用`delegate`来模拟指针的功能。如果你需要在`classes`或类的方法中使用指针，只需要将这些内容声明为`unsafe`即可。此外，尽管 C# 语言不支持`classes`的多继承，但可以通过继承`interfaces`来实现。

兼容性意味着 C# 语言允许与 C/C++ 语言风格的`api`集成（这需要传递指针类型参数），并允许 C# 语言组件与其他语言组件进行集成。

## 业务流程与软件实现之间更好的对应关系

如果一个企业的业务计划要付诸实践，必须在抽象的业务流程与具体的软件实现之间建立紧密的对应关系。这在大多数语言中很难做到。

C# 语言允许类型定义的扩展元数据。这些元数据可以应用于任何对象。项目构建者定义领域特定的属性并将其应用于任何语言元素，例如`classes`和`interfaces`。

简而言之，C# 是一种现代面向对象的语言，它使程序员能够基于`microsoft .net`平台快速方便地创建解决方案。该框架使得 C# 组件能够轻松转换为`xml`网络服务，以便任何平台调用。这提高了 C# 组件的效率。同时，它致力于消除可能导致严重错误的编程，让`c/c++`程序员在保持所需灵活性的同时能够快速开发。

通过此，我们对 C# 的重要性和应用进行了简要介绍。在书的下一章中，我们将讨论用于开发环境的数据类型以了解更多信息。

## 第 2 章：数据类型

### 数据类型

在 C 编程语言中，数据类型指的是用于声明变量或函数的类型。变量类型决定了它将占据的空间大小以及在系统中如何存储。数据类型的基本分类如下：

- 基础类型：它们包括以下类型：(a) 整数类型和 b) 浮点类型。
- 枚举类型：它们再次用于表示离散数值。
- `void`类型：关键字`void`表示没有可以赋值的值。
- 派生类型：它们包括 (a) 数组、(b) 指针、(c) 联合体、(d) 结构体和 (e) 函数。

数组和结构数据类型也被称为聚合类型。类型定义了函数返回的值。我们将讨论后续的数据类型。

### 整数类型

以下是属于该类别的数据类型列表。此外，它们占据的空间及其范围也已指定：

- `char`：分配 1 字节，范围为 -128 到 127
- `signed char`：分配 1 字节，范围为 -128 到 127
- `unsigned char`：分配 1 字节，范围为 0 到 255
- `int`：分配 2 或 4 字节，范围为 -32768 到 2147483647
- `short`：分配 2 字节，范围为 -32768 到 32767
- `unsigned short`：分配 2 字节，范围为 0 到 65535
- `unsigned int`：分配 2 或 4 字节，范围为 0 到 65535 或 4294967295
- `long`：分配 4 字节，范围为 -2147483648 到 2147483647
- `unsigned long`：分配 4 字节，范围为 0 到 4294967295

要获取变量或数据类型的精确大小，可以使用`sizeof`运算符。`sizeof(<data type>)`产生数据类型或变量的字节数。下面是一个说明该概念的示例：

```c
#include <limits.h>
#include <stdio.h>

int main() {
    printf("data type char (size in bytes): %d \n", sizeof(char));
    return 0;
}
```

编译并执行此代码，你将得到以下输出：data type char（字节）：1

### 浮点数据类型

以下是属于该类别的数据类型列表。此外，它们占据的空间、范围和精度值也已指定：

- `float`：分配 4 字节，范围为 1.2e-38 到 3.4e+38，精度为 6 位小数
- `double`：分配 8 字节，范围为 2.3e-308 到 1.7e+308，精度为 15 位小数
- `long double`：分配 10 字节，范围为 3.4e-4932 到 1.1e+4932，精度为 19 位小数

名为`float.h`的头文件定义了宏，允许你使用这些数据类型的值。以下代码允许你找到系统中相关数据类型分配的精确字节数：

```c
#include <float.h>
#include <stdio.h>

int main(){
    printf("allocated memory for float : %d \n", sizeof(float));
    printf("precision: %d\n", flt_dig);
    printf("max range value,: %e\n", flt_max);
    printf("min range value,: %e\n", flt_min);
    return 0;
}
```

编译并执行此代码，你将得到以下输出：float 的分配内存: 4，精度: 6，最大范围值: 3.402823e+38，最小范围值: 1.175494e-38

### void 类型

`void`数据类型表示没有可访问的值。它被用于以下三种情况：

- 函数返回`void`：你可能经常注意到将数据类型`void`作为函数的返回类型。如果没有，随着你 C 经验的增加，你会看到大量使用。`void`数据类型表示函数不会返回任何内容。这种实现的示例是：

  ```c
  void print(int)
  ```

- 作为`void`的函数参数：C 语言中有不同的函数，它们不接受任何参数。没有参数的函数可以识别为`void`。这种实现的示例是：

  ```c
  int print(void)
  ```

- `void`指针：类型`void *`的指针表示变量的位置。例如，考虑以下声明：`void *malloc(size_t size);`该函数返回一个`void`指针。换句话说，该函数可以返回任何类型的内存指针。

变量简单就是分配给存储区域的名称。我们的程序能够操作此类存储区域。每个`C#`变量都与一个类型相关，该类型决定了在内存中为该变量分配的空间。这也决定了适用于变量的操作类型。例如，你不能对字符串变量进行乘法运算。

在`C#`中，变量声明应使用以下语法：

`<data_type> <variable_list>;`

上述语法中的`data_type`必须是 C# 中的有效类型，如`int`、`string`、`float`等。`variable_list`可以是多个用逗号分隔的变量名。

以下是有效变量声明的示例：

`int a, b, c; char c, d; float x, salary; double y;`

变量可以在声明时进行初始化。

例如：`int x = 40;`

### 变量初始化

变量初始化是指给变量赋值的过程。在`C#`中，这是通过使用等号后跟常量表达式来实现的。这里是初始化的通用语法：`variable_name = value;`；正如我们之前提到的，变量可以在声明时进行初始化。这里有更多示例：

- `int x = 1, y = 6; /* 初始化 x 和 y. */`
- `byte f = 22; /* 初始化 f. */`
- `double pi = 3.14159; /* 声明 pi 的近似值. */`
- `char a = 'a'; /* 变量 a 的值为 'a'. */`

变量初始化应该正确；否则程序可能会产生意外的结果。

例如：

```csharp
using System;

namespace variableDeclaration {
    class myprogram {
        static void main(string[] args) {
            short x; int y; double z; /* 变量实际初始化 */
            x = 5; y = 10; z = x + y;
            Console.WriteLine("x = {0}, y = {1}, z = {2}", x, y, z);
            Console.ReadLine();
        }
    }
}
```

代码返回以下输出：

`X=5, y=10, z=15`

### 获取用户输入

`System`命名空间下的`Console`类有一个名为`ReadLine()`的方法，允许我们从用户那里获取输入。用户的输入被读取并存储在变量中。下面的示例演示了如何使用该方法：

```csharp
using System;

namespace userinputapp {
    class myprogram {
        static void main(string[] args) {
            string firstname = "nicholas"; string lastname = "samuel";
            Console.WriteLine("your name is: " + firstname + " " + lastname);
            Console.WriteLine("please enter a different first name:");
            firstname = Console.ReadLine();
            Console.WriteLine("your new name is: " + firstname + " " + lastname);
            Console.ReadLine();
        }
    }
}
```

提示输入新的名字时，输入并按回车键。你会发现你的名字已经改变。

### 运算符

运算符是指令编译器执行特定逻辑或数学操作的符号。`C#`拥有多种运算符。让我们讨论一下它们。

### 算术运算符

这些用于执行各种数学运算。它们可以像下面的示例所示使用：

```csharp
using System;

namespace arithmeticoperatorsapp {
    class myprogram {
        static void main(string[] args) {
            int x = 31; int y = 10; int z;

            z = x + y;
            Console.WriteLine("1: z equals to {0}", z);

            z = x - y;
            Console.WriteLine("2: z equals to {0}", z);

            z = x * y;
            Console.WriteLine("3: z equals to {0}", z);

            z = x / y;
```



```csharp
Console.WriteLine("4: z equals to {0}", z);

z = x % y;

Console.WriteLine("5: z equals to {0}", z);

z = x++;

Console.WriteLine("6: z equals to {0}", z);

z = x--;

Console.WriteLine("7: z equals to {0}", z);

Console.ReadLine();

}

}

}

```

上述大多数运算符都是为人知的，除了其中少数几个。`++` 是递增运算符，每次执行后变量的值加 1。`--` 是递减运算符，每次执行后变量的值减 1。`%` 被称为取运算运算符，返回除法后的余数。代码返回输出：

### 逻辑运算符

`C#` 还有许多逻辑运算符。让我们简要讨论一下：

- `&&`：如果两个操作数都为真，则条件为真。
- `||`：如果任一操作数为真，则条件为真。
- `!`：该运算符反转状态。如果条件为真，此运算符将使其变为假。

下面的示例演示了如何使用上述运算符：

```csharp
using System;

namespace logicaloperators
{
    class myprogram
    {
        static void main(string[] args)
        {
            bool x = true;
            bool y = true;

            if (x && y)
            {
                Console.WriteLine("1: the condition is true");
            }

            if (x || y)
            {
                Console.WriteLine("2: the condition is true");
            }

            /* 改变 x 和 y 的值 */

            x = false;
            y = true;

            if (x && y)
            {
                Console.WriteLine("3: the condition is true");
            }
            else
            {
                Console.WriteLine("3: the condition is not true");
            }

            if (!(x && y))
            {
                Console.WriteLine("4: the condition is true");
            }

            Console.ReadLine();
        }
    }
}
```

### 赋值运算符

`C#` 赋值运算符可以如下示例所示：

```csharp
class myprogram
{
    static void main(string[] args)
    {
        int x = 31;
        int z;

        z = x;
        Console.WriteLine("1: = value of z is {0}", z);

        z += x;
        Console.WriteLine("2: += the value of z is {0}", z);

        z -= x;
        Console.WriteLine("3: -= the value of z is {0}", z);

        z *= x;
        Console.WriteLine("4: *= the value of z is {0}", z);

        z /= x;
        Console.WriteLine("5: /= the value of z is {0}", z);

        z = 100;
        z %= x;
        Console.WriteLine("6: %= the value of z is {0}", z);

        z <<= 2;
        Console.WriteLine("7: <<= the value of z is {0}", z);

        z >>= 2;
        Console.WriteLine("8: >>= the value of z is {0}", z);

        z &= 2;
        Console.WriteLine("9: &= the value of z is {0}", z);

        z ^= 2;
        Console.WriteLine("10: ^= the value of z is {0}", z);

        z |= 2;
        Console.WriteLine("11: |= the value of z is {0}", z);

        Console.ReadLine();
    }
}
```

## 第 4 章：string 和 list

### List

`List<t>` 是所有集合类中最频繁使用的集合类。它是一个可以通过索引访问元素的类型。正如之前所说的，`list` 类属于 `System.Collections.Generic` 命名空间。`list` 类提供了许多用于列表和元素操作的方法。其中一些包括搜索、排序等。它被用于创建许多不同类型的集合。它可以是整数、字符串等更多类型的集合。对于引用类型，`list` 允许空值作为元素。也可以在任何列表集合中插入重复值。数组与列表相似，但列表可以动态调整大小，而数组不能。

### String

`c#` 中的 `String` 数据类型是一种表示文本并与文本变量一起工作的类型。它是一个字符数组。通过 `string` 关键字来声明字符串数据类型。当使用 `string` 关键字时，意味着它引用了 `System.String` 类。有很多扩展方法可以用于某些字符串变量上。其中最流行的包括 `concat`：用于拼接两个字符串；`contains`：用于判断字符串是否包含作为参数传入的给定字符串；`equals`：用于判断两个字符串是否具有相同的值等。默认的字符串数据类型是空字符串。

## 第 5 章：语法

### 循环结构语句

在现实生活中，我们经常多次重复做同一件事。例如，当你在进行眼部操的第四轮并揉眼睛时，你会重复揉眼睛的动作。在打乒乓球时，你会重复挥拍动作等等。在 `c#` 中，有一种语句可以重复执行相同的代码块，这被称为循环语句（circular statement）。循环语句分为三种：`while` 循环语句、`do...while` 循环语句和 `for` 循环语句。

### While 循环语句

`while` 循环语句与上节提到的条件判断语句有些相似，它根据条件判断来决定是否执行 `{}` 中的执行语句。区别在于，`while` 语句会反复判断条件。只要条件为真，`{}` 中的语句就会一直执行，直到条件不再为真，`while` 循环结束。

`while` 循环语句的语法结构如下：

```
While (cyclic condition)
{
    Execute statement
    ...
}
```

在上述语法结构中，`{}` 中的执行语句被称为循环体，循环体是否执行取决于循环条件。当循环条件为真时，执行循环体。当循环体执行完毕后，它将继续判断循环条件。如果条件仍然为真，它将继续执行，直到循环条件为假，整个循环过程才会结束。

接下来，用一个案例打印从 1 到 4 的自然数，如下例所示。

`program11.cs`

```csharp
Public class program11
{
    Public static void //这里需要你输入逻辑
    {
        Int firstsample = 1;//定义变量 ‘firstsample,’，初始值为 1

        While (firstsample <= 4) //循环条件
        {
            Console.WriteLine("firstsample = " + firstsample);

            //如果条件成立，则打印 firstsample 的值。
            Firstsample++; //firstsample 自增
        }

        Console.ReadKey();
    }
}
```

运行结果显示在计算机屏幕上。例如，`x` 的初始值为 1，如果满足循环条件 `x <= 4`，循环将反复执行，打印 `x` 的值，并且 `x` 会自动增加。因此，打印结果中 `x` 的值分别为 1、2、3 和 4。值得注意的是，示例中第 9 行的代码用于在每次循环中改变 `x` 的值，以实现改变循环条件。如果没有这一行，整个循环将进入死循环。

### Do-while 循环语句

`do-while` 循环语句的功能与 `while` 语句相似。它们之间的区别在于 `while` 语句需要先判断循环条件，根据循环条件的结果决定是否执行 `{}` 中的代码。相比之下，`do-while` 语句在判断循环条件之前需要先执行一次 `{}` 中的代码。它的语法结构如下：

```
Do
{
    Execute statement
    ...
} while (cyclic condition);
```

在上述语法结构中，关键字 `do` 之后的 `{}` 里的执行语句是循环体。`do-while` 循环将循环条件放在循环体之后。这意味着循环将无条件地执行一次，然后根据循环条件决定是否继续执行。

接下来，使用 `do-while` 语句重写示例，如下例所示。

`program12.cs`

```csharp
Public class classicprogram
{
    Public static void //我们通常在这里输入选项
    {
        Int secondinstance = 1;//定义变量 ‘secondinstance,’，初始值为 1

        Do
        {
            Console.WriteLine("firstinstance= " + secondinstance); //打印‘firstinstance,’的值
            secondinstance++; //‘firstinstance,’自增
        } While (firstinstance <= 4); //循环条件

        Console.scan();
    }
}
```

运行结果将显示在计算机屏幕上。上面的示例具有相同的运行结果，说明 `do-while` 循环和 `while` 循环可以实现相同的功能。然而，这两种语句在程序运行过程中存在差异。如果循环语句开始时不满足条件，`while` 循环的循环体将不会执行一次，但 `do-while` 循环的循环体仍会执行一次。如果示例中的循环条件 `x<=4` 改为 `x < 1`，示例 2-12 将打印 `x=1`，而示例 2-11 将什么都不打印。

### For 循环语句

`while` 循环和 `do-while` 循环在上节中已经解释。在程序开发中，另一种常用的循环语句是 `for` 循环语句，它通常用于循环次数已知的情况，其语法格式如下：

```
For (initialization expression; circulation conditions; operation expression)
{
    Execute statement
    ...
}
```

在上述语法结构中，`for` 关键字后的 `()` 包含三个部分：初始化表达式、循环条件和操作表达式，用 `;` 分隔；`{}` 中的执行语句是循环体。接下来，初始化表达式、循环条件、操作表达式和循环体分别用数字表示，并通过序号详细分析 `for` 循环的执行流。

```
For (1; 2; 3)
{
    4
}
```

接下来，通过一个案例求加 1~4 的自然数，如下所示。

`program13.cs`

```csharp
Public class classicprogram
{
    Public static void //我们通常在这里输入选项
    {
        Int secondinstance = 1;//定义变量 ‘secondinstance,’，初始值为 1

        Do
        {
            Console.WriteLine("firstinstance= " + secondinstance); //打印‘firstinstance,’的值
            secondinstance++; //‘firstinstance,’自增
        } While (firstinstance <= 4); //循环条件

        For (int first = 1; first <= 4;the, value, of first++) //first 将从 1 变到 4
        {
            Sum += first; //实现 sum 和 i 的累加
        }
    }
}
```



在示例中，变量`i`的初始值为 1，如果判断条件`i<=4`为真，将执行循环`sum+= i`。执行完成后，将执行操作表达式`i++`，此时`i`的值将变为 2。然后继续判断条件并开始下次循环，直到`i=5`且条件`i<=4`为假，结束循环，执行 for 循环后的代码并打印“sum=10”。

## 第 6 章：类

### 类与对象

在`c#`编程语言中，每个组件都与类和对象相关联，这些代表了面向对象编程的基本概念。类类似于原型，用户从原型创建对象。类代表一个单一、唯一的单元，拥有所有的成员、属性和功能。

对象是现实中的内存实体。当实例化时，它们会分配一些内存空间并拥有对该空间的引用。创建的每个对象必须是类类型。

### 类

类代表了任何面向对象软件内部唯一的编程组件。类通过其访问修饰符、`class`关键字和唯一名称来定义。在某些类内部，可能有多个成员，如字段、属性和方法。类的默认访问修饰符是`internal`。这意味着如果没有指定访问修饰符，则该类将被视为`internal`。下面写了一个类的类的示例：

![Image00109.jpg](img/Image00109.jpeg)

该类包含其访问修饰符 – `public`，它包含关键字`class`；它有一个唯一名称`tshirt`。在此类内部定义了多个成员：有一个私有字段`color`、一个公共属性`color`、一个定义的构造函数（带有一个参数）以及一个公共方法`about`。

除了普通类之外，还有一种特殊的类 - 抽象类（abstract class）。抽象类是一种特殊的类，不能对其进行实例化。抽象类主要用于在层次结构中定义基类，也被称为不完整的类。抽象类通常代表基类，它的设计目标是让派生类来实现抽象定义。在抽象类中，也可以有抽象方法或非抽象方法。抽象方法以及每个标记为抽象的类成员都必须在派生类中实现。标记有`abstract`关键字的类其目的是为派生类提供原型。抽象类可以实现构造函数。下面提供了一个示例：

![Image00110.jpg](img/Image00110.jpeg)

在提供的示例中，我们可以看到一个名为`animal`的抽象类。该类中只有一个成员，即一个抽象空方法`legsnumber()`。当方法被标记为抽象时，意味着派自该类的每个类（在本例中为`animal`类）必须对该方法的重写实现。在抽象类下面还有两个类，它们是“普通”类。这两个类都对`animal`有重写实现。这在章节中定义，但这是可能的，因为`animal`是抽象的。

*(自纠：原文包含许多冗余的逗号和拼写错误，如“e,xample,,。”我已经清理了标点符号以提高可读性，同时保留了所要求的语义内容。）*

**修正后的版本：**

在示例中，变量`i`的初始值为 1，如果判断条件`i<=4`为真，将执行循环`sum+= i`。执行完成后，将执行操作表达式`i++`，此时`i`的值将变为 2。然后继续判断条件并开始下次循环，直到`i=5`且条件`i<=4`为假，结束循环，执行 for 循环后的代码并打印“sum=10”。

## 第 6 章：类

### 类与对象

在`c#`编程语言中，每个组件都与类和对象相关联，这些代表了面向对象编程的基本概念。类类似于原型，用户从原型创建对象。类代表一个单一、唯一的单元，拥有所有的成员、属性和功能。

对象是现实中的内存实体。当实例化时，它们会分配一些内存空间并拥有对该空间的引用。创建的每个对象必须是类类型。

### 类

类代表了任何面向对象软件内部唯一的编程组件。类通过其访问修饰符、`class`关键字和唯一名称来定义。在某些类内部，可能有多个成员，如字段、属性和方法。类的默认访问修饰符是`internal`。这意味着如果没有指定访问修饰符，则该类将被视为`internal`。下面写了一个类的类的示例：

![Image00109.jpg](img/Image00109.jpeg)

该类包含其访问修饰符 – `public`，它包含关键字`class`；它有一个唯一名称`tshirt`。在此类内部定义了多个成员：有一个私有字段`color`、一个公共属性`color`、一个定义的构造函数（带有一个参数）以及一个公共方法`about`。

除了普通类之外，还有一种特殊的类 - 抽象类（abstract class）。抽象类是一种特殊的类，不能对其进行实例化。抽象类主要用于在层次结构中定义基类，也被称为不完整的类。抽象类通常代表基类，它的设计目标是让派生类来实现抽象定义。在抽象类中，也可以有抽象方法或非抽象方法。抽象方法以及每个标记为抽象的类成员都必须在派生类中实现。标记有`abstract`关键字的类其目的是为派生类提供原型。抽象类可以实现构造函数。下面提供了一个示例：

![Image00110.jpg](img/Image00110.jpeg)

在提供的示例中，我们可以看到一个名为`animal`的抽象类。该类中只有一个成员，即一个抽象空方法`legsnumber()`。当方法被标记为抽象时，意味着派自该类的每个类（在本例中为`animal`类）必须对该方法的重写实现。在抽象类下面还有两个类，它们是“普通”类。这两个类都对`animal`有重写实现。这在章节中定义，但这是可能的，因为`animal`是抽象的。

等待，这个`the, the, the, the`是`the`是`true`还是`false`？`false` `the, the,`是逻辑的结果。

*(自纠：原文包含许多冗余的逗号和拼写错误，如“e,xample,,。”我已经清理了标点符号以提高可读性，同时保留了所要求的语义内容。）*

**清理后的版本：**

在示例中，变量`i`的初始值为 1，如果判断条件`i<=4`为真，将执行循环`sum+= i`。执行完成后，将执行操作表达式`i++`，此时`i`的值将变为 2。然后继续判断条件并开始下次循环，直到`i=5`且条件`i<=4`为假，结束循环，执行 for 循环后的代码并打印“sum=10”。

## 第 6 章：类

### 类与对象

在`c#`编程语言中，每个组件都与类和对象相关联，这些代表了面向对象编程的基本概念。类类似于原型，用户从原型创建对象。类代表一个单一、唯一的单元，拥有所有的成员、属性和功能。

对象是现实中的内存实体。当实例化时，它们会分配一些内存空间并拥有对该空间的引用。创建的每个对象必须是类类型。

### 类

类代表了任何面向对象软件内部唯一的编程组件。类通过其访问修饰符、`class`关键字和唯一名称来定义。在某些类内部，可能有多个成员，如字段、属性和方法。类的默认访问修饰符是`internal`。这意味着如果没有指定访问修饰符，则该类将被视为`internal`。下面写了一个类的类的示例：

![Image00109.jpg](img/Image00109.jpeg)

该类包含其访问修饰符 – `public`，它包含关键字`class`；它有一个唯一名称`tshirt`。在此类内部定义了多个成员：有一个私有字段`color`、一个公共属性`color`、一个定义的构造函数（带有一个参数）以及一个公共方法`about`。

除了普通类之外，还有一种特殊的类 - 抽象类（abstract class）。抽象类是一种特殊的类，不能对其进行实例化。抽象类主要用于在层次结构中定义基类，也被称为不完整的类。抽象类通常代表基类，它的设计目标是让派生类来实现抽象定义。在抽象类中，也可以有抽象方法或非抽象方法。抽象方法以及每个标记为抽象的类成员都必须在派生类中实现。标记有`abstract`关键字的类其目的是为派生类提供原型。抽象类可以实现构造函数。下面提供了一个示例：

![Image00110.jpg](img/Image00110.jpeg)

在提供的示例中，我们可以看到一个名为`animal`的抽象类。该类中只有一个成员，即一个抽象空方法`legsnumber()`。当方法被标记为抽象时，意味着派自该类的每个类（在本例中为`animal`类）必须对该方法的重写实现。在抽象类下面还有两个类，它们是“普通”类。这两个类都对`animal`有重写实现。这在章节中定义，但这是可能的，因为`animal`是抽象的。

*(自纠：输入文本带有大量逗号。我将删除它们以形成连贯的句子，同时严格遵守变量和代码块的格式规则。）*

接口,

面向对象编程中的另一个重要组件是`interface`（接口）。接口代表了某些功能的多个声明。一个类可以实现一个或多个接口，但它只能继承一个类或抽象类。这揭示了 C# 编程语言的另一个特性——它不支持多继承。实现某些接口的类必须提供所有接口成员的完整定义。

在接口的使用中，不涉及访问修饰符的操作，因为所有接口成员都被认为是`public`（公共的）。因为接口的存在完全在于其供其他类实现的功能。如果某个类必须实现接口成员，就意味着这些接口成员必须是`public`的，以便被其他类实现。

接口是一个面向对象的组件，它包含声明，但不能有定义（实现）。如果你尝试在接口中插入某些实现，将会出现编译时错误。接口可以包含属性和方法——即任何可以实现的内容。它不能包含字段和构造函数，因为它不是类，而且无法被实例化。在实现接口时，类必须实现所有的接口成员。如前所述，C# 不支持多继承，但可以通过接口的使用来实现多继承，因为一个类可以实现多个接口。

示例：

![Image00113.jpg](img/Image00113.jpeg)

这里，我们定义了一个接口。它内部有三个布尔属性。实现此接口的类必须拥有所有这些成员的定义。

![Image00114.jpg](img/Image00114.jpeg)

程序包含一个类，即`person`类。该类实现了已声明的`iperson`接口。该类有两个私有字符串字段，分别为`_firstname`和`_lastname`。它还有一个构造函数，在其中为这些字段赋值。此外，该类包含了`iperson`接口的三个成员的定义——`isRunning`、`isStanding`和`isTouching`属性。编译器接受这一点，因为没有错误。但是，如果我们从`person`类中删除这三个属性中的任何一个，编译器就会报告错误。例如：

![Image00115.jpg](img/Image00115.jpeg)

在这里，我们注释掉了`person`类内部的`isRunning`属性。编译器报告错误，指出`person`类没有实现该属性，程序无法构建。之后，我们将取消该属性的注释，恢复到程序的有效状态。让我们创建一个内部带有`main`方法的程序类。在那里，我们将创建一个`person`类的实例并运行程序，检查一切是否运行正常。

![Image00116.jpg](img/Image00116.jpeg)

现在，运行程序：

![Image00117.jpg](img/Image001111.jpeg)

一切进展顺利。

## 第 7 章：LINQ 查询操作符 – LINQ

集成查询（称为 LINQ）代表了 C# 编程语言中的查询语法，用于不同对象的检索和过滤。LINQ 为各种类型的对象提供了单一的查询接口。这种查询语法集成到了 C# 编程语言以及 Visual Basic 中。为了更好地理解，我们将提供一个示例进行进一步说明。因此，你有 SQL 这种结构化查询语言，SQL 用于从数据库中获取和保存数据，它是一种旨在与数据库紧密工作的语言。

与 SQL 类似，LINQ 用于获取和过滤不同的数据源，如集合、数据集等。有很多方法可以使用 LINQ；它被用于查询集合、XML 文档、实体框架数据集，并允许使用面向对象的方法处理数据。使用 LINQ 时，你不需要担心将设置转换为对象。LINQ 提供了一种查询任何来源数据的方法。它支持编译时语法检查，如果你在编写 LINQ 代码时出错，编译器会立即通知你。LINQ 允许你查询每个集合，如列表、数组等。

现在进入示例部分：

在这个示例中，我们有一个名为`car`的类。在`car`类中，有三个属性：`trunkCapacity`、`isAutomatic`和`isTurboCharged`。每个属性代表一个只读属性，它们的初始状态在`car`构造函数设置。构造函数接受三个参数并将它们的值赋予上述属性。在`main`方法中，我们正在创建一个`car`对象的列表。`car`对象的列表在声明部分填充，创建了五个具有不同`trunkCapacity`、`isAutomatic`和`isTurboCharged`值的`car`对象。之后，我们将过滤列表，只保留具有自动挡箱的汽车。这将通过使用 LINQ 查询完成。我们创建了一个名为`carsAreAutomatic`的对象并使用 LINQ 过滤`cars`列表。然后我们执行`where` LINQ 扩展方法来获取所需的对象。它是如何工作的？在`where`方法中，我们声明了一个迭代变量，将用于过滤条件。

示例中的变量是`s`。因此，接下来的过滤操作是：对于`cars`列表中的每个`s`对象，它将为我们提供`s.isAutomatic`属性等于 true 的对象。这将创建一个过滤后的列表。为了让这成为显式类型对象的列表，我们将对过滤后的列表执行简单的`toList()`方法。这将创建一个`list<car>`类型的对象，并将其置于`carsAreAutomatic`对象。现在，我们拥有了所需的数据。最后，我们将遍历新创建的`car`对象集合，并将消息打印到控制输出。对于列表中的每个对象，我们将打印“后备箱容量为 {certain capacity} 的汽车是自动的”。我们知道这一点，是因为我们过滤了汽车并只取了具有自动挡的汽车。

另一个示例见下方：

在这个示例中，我们有一个名为`person`的类。该类有三个属性，分别是`salary`、`firstname`和`lastname`。每个`person`类代表一个包含其基本信息的员工。对象的属性是在构造函数中赋值的。

在`main`方法中，创建了一个包含`person`类类型对象的列表。我们添加了五个`person`对象，每个对象都有不同的`salary`金额、`firstname`和`lastname`。经理想要筛选出所有`salary`大于 3000 的人员，这些人员将被标记为`seniors`（资深员工）。我们将通过 LINQ 查询来实现这一目标。

与上一个示例一样，我们使用`where`扩展方法对人员列表进行过滤。在该方法中，我们声明只需要`salary`大于 3000 的`person`对象。在完成检索后，`toList()`方法将过滤后的可枚举列表转换为`person`对象列表。现在，我们得到了一个包含`person`类类型的列表对象，它只包含`salary`大于 3000 的人员。该变量命名为`seniors`。

现在，经理要求获取所有资深员工薪资的总和。我们将通过创建一个资深薪资列表，然后将所有值相加存一个变量，最后将其打印到标准输出。`seniorsalaries`列表的创建通过执行`select` LINQ 扩展方法完成。当需要从对象集合中获取某些属性值时，就会使用`select`方法。情况下，我们需要从`seniors`列表中的每个对象获取`salary`属性值。

`select`方法的操作如下：对于`seniors`列表中的每个`x`对象，获取`x.salary`值。这创建了一个可枚举列表。执行`toList()`方法后，我们成功创建了一个包含资深员工薪资元素的`List<int>`对象。然后，我们创建了一个变量来存储所有资深员工薪资的总和——`seniorsalariessum`。完成这一步后，我们还有最后一条语句来完成工作。通过`foreach`方法遍历`seniorsalaries`列表，将所有薪资收集并累加到变量`seniorsalariessum`中。最后，程序将结果——`seniorsalariessum`的值打印到标准输出。该程序的输出看起来如下：

![Image00121.jpg](img/Image00121.jpeg)

这个逻辑和问题的解决方案可以简单得多，资深薪资总和只需要一行代码即可。那行代码看起来像这样：

![Image00122.jpg](img/Image00122.jpeg)

在执行`where`方法后，将执行`select`方法，随后将创建一个列表，我们可以使用`foreach`扩展方法遍历该列表并进行求和计算。这将产生完全相同的结果。在初始解决方案中，为了便于理解，这个长语句被分成几个较小的语句。让我们用最后一个示例来结束这个 LINQ 章节：

![Image00123.jpg](img/Image00123.jpeg)

在这个示例中，我们修改了上一个示例中的`person`类。现在，`person`类包含了`salary`属性和`personinformation`类属性，两者都在`person`类中赋值。`personinformation`类包含三个只读属性。这些属性是`firstname`、`lastname`和`id`，其中`id`的数据类型为`int`。这三个属性在实例化`personinformation`对象时在构造函数中进行赋值。

现在，让我们进入`person`类的`main`方法。在这里，我们再次创建一个对象列表，这与上一个示例相同，尽管由于类的修改，这次会略有不同。我们正在创建五个`person`对象，每个对象都分配了`salary`和`personinformation`对象。对于每一个人，我们都创建一个`personinformation`对象来正确地实例化`person`对象。每个`personinformation`对象在实例化时都传递了`firstname`、`lastname`和`id`。通过这种方式，我们创建了一个稍微复杂的对象，它内部包含了另一个对象。好了，我们准备好了。

经理要求我们找到所有被视为资深员工且`id`小于 150 的员工的名字（firstname）。从上一个示例中，我们知道资深员工是指`salary`大于三千 (3000) 的人员。我们正在进行与上一个示例类似的操作，但这次`person`类发生了变化。它的结构与上一个示例不同，因此我们必须先分析类结构并创建一个解决方案。

第一步是，必须从人员列表中过滤出`salary`大于 3000 的`person`对象。之后，我们必须从每个`person`对象中提取`personinformation`对象，找到所有资深员工的名字。当收集`personinformation`对象时，我们必须对其进行过滤，只保留`id`小于 150 的对象。完成该任务后，我们就可以`select`所有资深员工的`firstname`属性，创建一个列表，遍历该列表并打印名字值。这一切都是在一个复杂的 LINQ 查询中完成的，我们从中创建了`seniorslt150`列表变量。

第一个`where`方法创建了一个可枚举列表`seniors`。然后，`select`方法从`seniors`列表中获取`personinformation`对象，并创建一个资深员工`personinformation`对象的枚举列表。第二个`where`方法作用于之前创建的枚举列表中的`personinformation`对象，并在那里过滤出`id`属性小于 150 的`personinformation`对象。从那里，我们执行`select`方法，为每个`id`小于 150 的资深员工`personinformation`对象收集`firstname`属性值。最后，我们对创建的最终枚举结果执行`toList()`方法，最终产物是一个包含每个资深员工名字的字符串列表。

同样，有很多问题需要我们了解某个条件，或者对如何解决它们做出决策。在`c#`中，实现这一点很容易，因为该语言为许多不同的工具来处理这些问题。我们将必须使用表达式，而这些表达式将被求值。在这种情况下，我们将使用关系表达式和逻辑表达式，它们会被求值，并根据求值的结果执行算法的特定步骤或其他操作。让我们先了解我们所需的表达式。

### 做出选择和决策

当我们使用`c#`语言时，我们需要花一些时间来处理决策控制语句或条件语句。这些代码类型可以接收用户的输入，并将其与你在代码中设置的条件进行比较，然后代码将根据这两者自主做出一些重要的决策。

在某些时候，你写了代码，并希望确保此程序能够独立处理某些决策。你可以选择编写代码，以便在代码中预先找到特定的条件，然后代码可以根据用户输入到计算机的内容做出响应。

关于这一点的好消息是，对于这些条件语句，你有几个选项可以选择。根据你希望从程序中获得什么，以及你希望它如何响应用户的不同输入，每种语句的工作方式都略有不同。在我们学习不同的选项时，你能够更好地看到每种语句是如何工作的，以及为什么在此过程中选择其中一个对你来说是一个极佳的选择。让我们深入看看`c#`语言中可用的一些主要条件语句，学习每一个将如何工作，并探索使用它们进行编码的一些基础知识。

观察 if 语句

我们在这里想要查看的第一种条件语句被称为`if`语句。在我们将要查看的所有条件语句中，这一个是最基础的。它缺少了一些我们将在这些语句中看到的功能，但它确实帮助我们学习更多关于条件语句的知识并在某些情况下也很有用，因此学习它是非常重要的。

当你处理这个`if`语句时，你会发现当它运行时，只有当用户提供的输入与代码中设置的条件匹配时，代码才会我们提供回复。当这种情况发生时，代码将能够执行，通常取决于程序员在代码中输入的内容，输出某种消息。有时你还会设置它执行其他操作。

然而，如果用户输入的输入与我们设置的条件不匹配，那么屏幕上将什么都不显示。这可能会导致一些问题，这就是为什么`if`语句可能没有其他某些选项那么常用。

这一切中的好消息是，即使是初学者，也会发现这些`if`语句很容易设置和使用。让我们来看下面的代码，看看我们如何在`c#`语言中创建一个这样的`if`语句：

```



##我是由深度求索（DeepSeek）研发的 deepseek-v4-flash-0731 智能大模型。条件语句与程序流程

```csharp
if (x > 0)
{
    Console.write("the value is positive.");
}
```

通过我们在上面列出的示例，某些事情需要发生。如果用户输入的值大于零，程序被设置为打印“the value is positive”，但如果该表达式结果为假，或者输入小于零，程序将忽略 `Console.write` 之后的整个语句并继续运行。

## 观察 `else` 语句

正如我们在处理语句时很快发现的那样，在很多情况下，这些语句无法以我们想要的方式帮助我们完成任务。设置一种代码，让用户输入某些内容而程序直接结束，是一个好主意，在这里我们将查看一种名为 `else` 的新条件语句。

`else` 语句将是一个非常好用的工具，因为它在为我们正在编写的代码增添大量功能的同时，允许我们添加多个选项，并处理用户可能添加的几乎任何内容。直入正题，我们需要查看 `else` 语句的语法，以便更好地理解它在 `c#` 语言中将如何工作。这种语句的一个很好的语法示例是：

```csharp
if (expression)
{
    Console.write("the statement you want to run if result is true");
}
else
{
    Console.write("the statement you want to run if result is false");
}
```

正如你已经从这个中看到的，`else` 语句将带来更多力量。这是 `else` 语句的一个基础选项，但你可以添加更多行来让它更强大。通过这些语句，如果答案为假，你的代码将继续执行语句的下部分以检查该部分是否为真。如果有两个以上的选项，它将继续向下执行 `else` 语句，直到答案变为真，然后它将显示出现的消息。

现在我们已经花了一些时间讨论它，是时候看一个它是如何工作的示例了，这样你就可以在代码中使用它：

```csharp
if (x > 0)
{
    Console.write("this value will be positive.");
}
else
{
    Console.write("the value is less than or equal to zero.");
}
```

你会发现，当我们处理上面的示例时，`else` 子句将是非常重要的，或者至少在布尔表达式结果为假之前是隐藏的。它在过程需要 `else` 语句时就在那里。但如果我们最终得到了真值，那么第一个语句将是显示的那个，这样我们完全不需要 `else` 语句了。

## 嵌套条件语句是什么

每当我们查看 `c#` 附带的一些新代码时，你应该发现，使用我们上面那两个语句会更容易，或者你也可以将它们结合起来，为你的某些代码制作一个嵌套条件语句。通过嵌套条件语句，我们将采取上述条件语句之一，并将其放在另一个语句内部。

在处理任何嵌套条件语句时，我们必须关注的主要点是：如果你在编写语句时出现任何错误，将会导致整个部分出错，并且花费一些时间来修复。这使得在开发过程中处理和操作它们变得有些困难，请务必小心。

不过，它们的独特之处，也是让它们非常有吸引力的一点在于，允许我们根据需要添加尽可能多或尽可能少的层级。尽管如此，大多数语言专业人士仍建议嵌套语句保持在三层或以内，以免它们在处理过程中变得过于混乱。

如果你在编写这些语句时最终超过了第三层，你可能会得到一个不受控且行为不符合预期的结果，甚至可能无法运行。作为一名初学者，请坚持三层，并随着编程水平的提高再增加层数。

你可以编写出许多依赖于这些条件语句的代码。它们可以帮助你让代码更健壮，并确保我们能够处理用户提供的某些输入，即使我们无法提前预测用户将向程序输入什么答案。这些语句可以根据我们设置的任何条件基于输入，并确保程序将按照我们期望的方式运行。这使得我们更容易看到结果，并确保程序按照我们想要的方式工作。

# 第 9 章：.net

## .net 框架

在这种框架下编写的程序能够在软件环境中执行，而不是硬件环境，该环境被称为 `clr` 或“公共语言运行时”（common language runtime）。`cls` 是一个应用程序虚拟机，它将帮助我们提供一些不同的服务，包括安全性、异常处理和内存管理。正因如此，用此框架编写的代码被称为托管代码（managed code）。我们提到过的 `cls` 和 `fcl` 共同构成了我们所讨论的 .net 框架。

首先，`fcl` 将非常重要。它为我们提供了一些用户界面、数据库连接、数据访问、Web 应用程序开发、算法、网络通信等。程序员可以将他们正在编写的源代码与 .net 框架以及其他可用库结合，从而产出软件。

这是一个设计用于与我们在 Windows 平台上想要创建的大多数新应用程序良好协作的框架。此外，微软还将推出一个专门为 .net 软件设计的 IDE（集成开发环境），称为 Visual Studio。

在涉及 .net 框架方面，我们有很多可以处理的内容。开发的一些方法不仅可以在 Windows 系统上运行，也可以在其他操作系统上运行，包括 Linux 和 Mac。它还可以帮助我们使用多种语言（特别是 C#），同时保持可移植性、安全性、高性能，并良好地管理我们在编写特定代码时所需的内存。

为了能够用 C# 进行有效编程，人们需要一些关于所谓 .net 框架的理论背景知识。这就是为什么 .net 框架是本书不可或缺的一部分。在我们更深入接触 .net 框架之前，你应该知道它是 .net 技术中不可或缺的一部分。

运行时环境的任务本质上是执行用相应编程语言开发的代码。但在过去，通常必须为每种编程语言（在某种程度上也为每个版本）提供单独运行时库（`runtime library`），以便执行相应的程序。例如，C++ 的 `msvcrt.dll` 文件。运行时环境的概念今天仍然适用，并提供了 .net 的核心优势：

- 只需要一个框架。
- 可以根据知识水平和偏好使用不同的语言。
- 所有语言的运行时环境都是同一个框架。
- 跨语言支持是一个主要优势。
- 跨语言异常处理允许定义程序在发生错误时的反应方式。
- 运行时可以控制改进的安全性。
- 简化的版本控制，允许存在多个版本。

由于 .net 框架提供了跨语言运行时，它确保了不同组件之间的最佳协作。

你现在知道 .net 框架是 .net 技术的一部分以及它的职责。.net 框架由三个主要组件组成：
- 公共运行时 (`clr`)
- 程序集 (Assembly)
- 公共中间语言 (`cil`)

在本书中，我们将详细介绍这些组件：公共运行时、程序集和公共中间语言。它们将在 Web 服务的上下文中再次出现。

.net 框架是开发中涉及的所有问题的解决方案。.net 框架的这两个组件也被称为基础框架：公共运行时和库。

当我们有一个用 `.net` 语言编写的程序并对其编译时，会生成程序集（assembly）。程序集包含了编译后程序中的 `cil`，还包含了程序中使用的所有类型的信息。

## CIL

`.net` 程序不会直接编译成编译器的汇编代码；而是被编译成一种名为 `cil` 的中间语言。这种语言由 `runtime` 读取并执行。`cil` 和 `runtime` 的使用赋予了 `.net` 极大的灵活性和跨平台能力。

`.net` 框架拥有通用语言规范，即 `cls`。这些规范是任何想要使用 `.net` 的语言都必须遵守的指南，以便与 `runtime` 配合。此的优势之一是，如果我们的代码符合 `cls` 编译，我们就可以与其他语言实现互操作性；例如，可以在 `c#` 中创建一个库，而 Visual Basic `.net` 程序员可以毫无问题地使用它。

这些指南中最重要的点之一是 `cts`，即公共类型系统。在编程语言中，当我们想要保存信息时，会将其放在变量中，变量的类型取决于要保存的信息，例如，类型可以是 `integer`（整数），另一个是存储带小数的数字，另一个是保存短语或单词。这样做的问题是，每种语言存储信息的方式不同。某些语言使用 16 位内存存储整数，而另一些语言使用 32 位；甚至某些语言（如 `c` 和 `c++`）没有用于存储字符串或短语的类型。

为了解决这个问题，`.net` 框架通过 `cts` 定义了类型在它们环境中如何工作。任何与 `.net` 工作的语言都必须使用 `cts` 中概述的类型。现在我们已经了解了基本概念，并可以看到所有这一切是如何整合在一起的。

## 如何创建 .net 应用程序

我们可以使用编程语言来创建一个 `.net` 应用程序。为了这个目的，我们将使用 `c#`；通过这种编程语言，我们可以创建程序的源代码（告诉程序应该做什么的指令）。

当我们完成源代码后，就必须使用编译器。编译器获取源代码并为我们创建一个程序集。这个程序集将包含我们代码等等的内容，但是用 `cil` 编写的，这引导我们发现了 `.net` 的另一个优势——编译器可以针对我们将使用程序的平台对代码进行优化，这意味着同一个程序可以针对移动设备、普通 PC 或服务器进行优化，而无需对其进行任何更改。

`.net` 框架可以在许多平台上运行，不仅仅是 Windows。这意味着我们可以在特定平台上进行编程，如果另一个平台拥有 `runtime`，我们的程序就可以毫无问题地运行。在 Windows 中开发的 `.net` 程序可以在 `linux` 中执行，只要它有相应的 `runtime`。

当我们想要调用程序时，`runtime` 会开始介入，读取程序集并为我们创建整个环境。`runtime` 开始从程序集中读取 `cil` 指令，并在读取的同时将其编译为运行该程序的计算机的微处理器可以识别的代码；这被称为 `jit` 或即时编译。通过这种方式，程序在执行过程中推进，并被编译；所有这一切对用户来说都是透明的。

`jit` 编译器也被称为 `jitter`。它是 `runtime` 的一部分，如果程序需要重新运行已经编译的代码，`jitter` 将不会重新编译，而是运行已经编译的内容，从而提高了性能和对用户的响应时间。

对于正在运行的程序，`.net` 框架提供了内存管理和垃圾回收的服务。在 `c` 和 `c++` 等非托管语言中，程序员负责内存管理。在大型程序中，这可能是一项复杂的任务，会导致程序执行期间出错。幸运的是，像 `c#` 这样的托管语言有一种模型，使得我们这些程序员不再需要负责内存管理，垃圾回收器负责移除不再使用的对象。垃圾回收器会自动工作，但对于某些情况（例如数据库连接），我们必须显式指示它们何时需要被释放。

# 第 10 章：enum 和 struct

## enum

`enum` 是一种特殊的数据类型，允许程序员为一组常量提供有意义的名字。要声明一个 `enum`，我们使用 `enum` 关键字后跟 `enum` 的名称。`enum` 的成员定义在花括号内，用逗号分隔。一个示例是：

```csharp
enum DaysOfWeek
{
    Sun, Mon
}
```

注意，在声明 `enum` 后，我们不在右大括号结束加分号。默认情况下，`enum` 的每个成员都是从 0 开始的整数。如果我们想为 `enum` 成员分配不同的值，可以如下操作：

```csharp
enum DaysEnum
{
    Sun = 5, Mon = 10
}
```

现在，`Sun` 被赋值为 5，`Mon` 被赋值为 10。如果我们没有赋值值，`enum` 成员将是连续的整数，例如：

```csharp
enum DaysEnum
{
    Sun, Mon
}
```

`Sun` 被赋值为 0，`Mon` 被赋值为 1。如果我们想将 `enum` 强制转换为 `int`，可以这样做：

```csharp
Console.WriteLine((int)daysEnum);
```

```csharp
Console.WriteLine(daysEnum);
```

使用 `enums` 有两个主要原因。第一个是提高代码的可读性。语句：

```csharp
daysEnum = DaysEnum.Mon;
```

比：

```csharp
daysEnum = 1;
```

更具解释性。

第二个原因是限制变量可以取的值。如果我们有一个存储星期几的变量，我们可能会不小心地给它赋值 10。通过使用 `enum` 可以防止这一点，因为我们只能将 `enum` 预定义的成员赋值给变量。

```csharp
enum DaysEnum : byte
{
    Sun = 300
}
```

由于 `byte` 的范围是 0 到 255，这将失败。

## Struct

现在，让我们看看 `struct` 数据类型。`struct` 在许多方面与 `class` 相似。像类一样，它们包含属性、构造函数、方法和字段，并允许将相关的成员分组到一个包中，以便你可以作为一个组来操作它们。

要声明一个 `struct`，你使用 `struct` 关键字。一个示例是：

```csharp
struct MyStruct
{
    //fields
    private int x, y;
    private anotherClass myclass;
}
```

```csharp
private days mydays;

//constructor
public mystruct(int a, int b, int c)
{
    myclass = new anotherclass();
    myclass.number = a;
    x = b;
    y = c;
    mydays = days.mon;
}

//method
public void printstate()
{
    console.WriteLine("x = {0}, y = {1}, mydays = {2}", x, y, mydays);
}
}

class anotherclass
{
    public int number;
}

enum days { mon, tue, s, wed }
```

`mystruct` 定义在第 1 到 23 行。在第 4 行，我们为结构体声明了两个私有的 `int` 字段。第 5 行，我们声明了另一个名为 `myclass` 的私有字段。该字段是 `anotherclass` 类的一个实例。第 6 行，我们声明了一个 `enum` 变量 `mydays`。这两个字段（`myclass` 和 `mydays`）在该示例中被特别包含，用于演示如何将类实例和 `enum` 变量作为结构体的字段。

在声明字段之后，我们声明了结构体的构造函数（第 9 到 16 行），随后是一个用于打印 `x`、`y` 和 `mydays` 取值的方法（第 19 到 22 行）。

在声明结构体之后，我们在第 25 到 28 行声明了 `anotherclass` 类，并在第 30 行声明了 `enum days`。在这个示例中，我们将类和 `enum` 声明在结构体 `mystruct` 外部。然而，我们可以在结构体内部声明 `enum` 或类。`enum`、结构体或类可以嵌套在另一个结构体或类内部。当我们处理书末尾的项目时，将查看一个在类内部声明 `enum` 的示例。

要使用上面的结构体，我们可以在 `main()` 方法中添加以下代码：

```csharp
Mystruct example = new mystruct(2, 3, 5);
example.printstate();
```



如果我们运行代码，将得到：
`X = 3, y = 5, mydays = mon`

结构体（struct）和类（class）之间有两个主要区别。首先，结构体数据类型不支持继承。因此，你不能从一个结构体派生另一个结构体。然而，结构体可以实现接口。实现方法与类相同。更多信息请参阅第 8 章。

结构体和类的第二个区别是结构体是值类型，而类是引用类型。

有关结构体和类区别的完整列表，请查看以下页面：
`https://msdn.microsoft.com/en-us/library/saxz13w4.aspx`

# 第 11 章：常见错误以及如何避免它们

本指南花费了一些时间来了在使用 C# 语言编写代码时需要了解的所有不同编码部分。

在学习这门语言时，有很多不同的方面需要留意，但当我们把所有内容整合在一起时，我们会发现在这个过程中可以创建一些很棒的代码和程序。尽管许多旨在为初学者简化编程的现代编程语言在刚开始学习时，仍然会有许多挑战出现。

初学者在这一过程中必须做的事情之一是，他们需要通过练习，并从编码中出现的错误和一些问题中学习。即使是休息一下通常也足够帮助你继续进行，并确保你不会在过程中精疲力竭并遇到困难。你应该避免的一些错误如下：

### 练习不足

本指南中有很多大量的代码、建议和需要学习的内容，但如果你不亲自打开 C# 编译器并尝试其中的一些内容，你将无法获得让这些技术为你服务的所需的技能（以及更多内容）。这就是为什么我们需要遵循的第一条规则是玩玩代码并尽可能多地练习。对于我们在任何语言中想要探索和学习任何新主题，我们越快能把手弄脏并开始捣鼓代码，就能越快地学习一些概念。你不能在不实际使用信息的情况下通读它们，并指望记住这些信息并能够将代码应用到你的程序中。你必须弄弄代码并观察它是如何工作的。现在，你会发现开始这一工作的最好地方就是打开我们的 C# 编译器并立即开始编写我们想要的代码。取本指南中的一些示例并随便弄一下。即使只是从开始将它们输入编译器也是朝着正确方向迈出的一步，并将确保我们能够通过练习、工作和探索来获得正确的结果。

### 忽略基础

尽管有时基础知识看起来太基础了而无法使用，你可能觉得应该不加思考地快速跳过，但花时间学习这些是如何运作仍然很重要。尽管它们很简单，但良好运用它们非常重要。我们越能良好地处理这些基础知识，掌握随后出现的某些高级内容就越容易。那些试图进入编程语言并快速跳过起始部分、不在某些基础知识上花费适当时间的程序员，将在需要过渡到某些高级材料时成为第一批被住的人。

所以，在错过我们这里需要的一些课程并跳过所有这些中重要的基础知识之前，请确保在过程中学习更多关于基础知识以及我们能用它做什么。

### 不写出来

想要开始编程、打开编译器并开始编码是正常的。虽然这是使用的方法之一，但有时尝试不同的方式并手写而不是一直尝试输入，将是帮助我们完成任务的秘诀。拿出笔和纸写下我们的代码是有帮助的。

如果你计划在大学期间或为了新工作而使用这种方法，那么能够写出你正在使用的 `codes` 并将其用于你的需求，对于你所预见到的成功将非常重要。

你投入越多的时间和练习来手写编写一些 `codes`，你对编码以及通过它能做的一切事情的理解就会越深刻。

它迫使程序员慢下来，并真正关注他们想让 `codes` 执行什么。

然后你可以利用这种方法来发现自己的错误，并学习什么对你最有效，什么又无效。

### 不要拒绝帮助

当我们刚开始以这种方式编写 `codes` 时，你可能对事情将如何运作以及你将如何成为历史上最伟的代码编写者有一许多宏伟的想法。

你可能认为这不会出现任何任何问题，而且你可以在短时间内处理好一切。

在我们想要在这里完成的工作中，出现的最大的误解之一，就是我们假设自己完全不需要为编程寻求任何帮助。

虽然在没有任何帮助的情况下独立开始学习任何语言编程（即使是 `c#`）是非常棒的，但我们必须面对现实，并记住，当我们有正确的同伴反馈和导师来帮助时，我们的学习速度会更快、更高效。

那些在你独自操作时看起来是无法解决的错误，或者看起来是无法学习的主题，你会发现，当有更有经验的人介入并提供帮助时，事情会变得简单得多，你实际上可以学到新东西。

无论是在线寻求帮助，还是能够找到可以面对面来到你并提供建议的人，你永远不要害怕向别人寻求帮助。

现在所有更高级的程序员都曾处于你现在所处的位置。

而且大多数开发者都会喜欢他们能获得再次编码的机会，并且非常愿意帮助你解决你想要帮助的某些编码。

当然，我们需要对此保持谨慎，在整个过程中绝不要利用这种机会。

在这里应该遵循的最好规则是：让别人帮助你解决代码中的某个问题的时间不要超过 20 分钟。

而且，在提前花费至少 20 分钟时间尝试学习它是如何运作的以及你能够用它做什么之前，你不应该寻求帮助。

### 不要不要休息

会有当你正在用 `c#` 语言编写你想做的某些 `codes` 时，然后你会在某些问题上卡住。

你会在上面上花一些时间，但这似乎只会让整件事变得更糟。

你不断尝试、不断工作，实际上是在让问题变得更糟，或者根本找不到问题所在，你的挫败感会不断上升。

你想解决问题并继续你的编码，但在过程中你只是变得越来越愤怒，而 `codes` 也变得变得越来越杂乱。

当这种情况发生时（而且这是每个人都可能发生的事情），我们必须花时间来休息一下。

这可能是我们在处理 `c#` 语言和我们的一些 `codes` 时最不想担心的事，但它将允许我们从问题中抽身，呼吸一下新鲜空气，或者至少做一段时间其他的事情。

而且，通常在你休息完并重新回到问题面前时，你会发现开始时看起来无法解决的问题实际上非常容易修复。

当人们在这个过程中投入了这么多时间和精精力后，没有人想要放弃，但从长远来看，它可以减少挫败感，并确保你能在短时间内修复你的代码。

### 忽视 c# 社区

当我们开始用 `c#` 语言及更多内容进行编码时，我们会发现的有趣事情之一，就是由不同的程序员和开发者组成的庞大社区。

当你准备好开始学习新的编程语言时，你会发现只要避开这些错误，你就能有一个良好的开端。

## 结论

如果你已经决定 `c#` 语言是适合你工作的语言，那么你并不孤单。

世界上有许多程序员都在使用这门语言，现在你已经读完了这本指南，你可以像我们一样，现在加入这一者的行列了。

本指南中包含了极其丰富的知识和信息，供我们学习使用，你会发现，在处理 `c#` 语言时，这是我们能够利用的最佳选择之一。

`c#` 易用性的得益于减少了某些 `c++` 特性，并且不再使用宏、模板和多重继承。特别是对于企业级开发者来说，上述特性带来的麻烦远多于收益。让编程变得更容易的新特性包括严格的类型安全、版本控制、垃圾回收等。所有这些功能的目的是为了开发面向组件的软件。

你学习 `c#` 的努力是一项巨大的投资，因为 `c#` 设计初衷是作为编写应用程序的主要语言。你会发现许多在 `c++` 中可以实现或需要费力实现的功能，在 `c#` 中仅仅是一些基础函数。对于企业级编程语言，新的财务数据类型非常受欢迎。你使用了一种专用于财务计算的新型数据类型 `decimal`。如果你不喜欢这种简单、现成的类型，可以根据应用程序的特殊需求轻松创建一个新的数据类型。

`c#` 为你提供了便利的函数，如垃圾回收、类型安全、版本控制等。唯一的“代价”是代码操作默认是类型安全的，并且不允许使用指针。这完全关乎类型安全。然而，如果你需要指针，仍然可以在非安全代码中使用它们，且在调用非安全代码时不能使用列集。

`c#` 是一门易于的编程语言，即使对于编程初学者来说也很友好。你只需要搭建环境并开始编写和运行你的 `c#` 代码。你可以单独使用 `c#` 开发一个完整的计算机应用程序。

作为一名初学者，你将通过本指南实现惊的目标，并在学习如何使用 `c#` 语言的过程中获得宝贵的知识。我们探索了与该语言相关的许多不同主题，例如如何使用条件语句、如何使用类以及操作符的原理等等。本指南将帮助你熟悉 `c#` 语言，让你学会编写自己的代码。

如果你觉得已经准备好学习一种新的编程语言并开始编程，`c#` 是一个很棒的选择。务必查看本指南，学习在短时间内创建真正实用的代码所需的所有基础知识。

祝你好运，编程愉快！

# 第 6 册：树莓派

一本计算机技术领域独立学习、无缝设置和项目精通的初学者指南

vera Poe

## 引言

我们可以找到许多不同的编程语言来编写代码，也有许多不断涌入并帮助我们完成任务的工具和配件。随着技术的不断发展和变化，有时会让初学者觉得自己落后了太多，认为应该放弃而不是尝试。他们担心工作对他们来说太难无法完成。很棒的一是，`raspberry pi`（树莓派）将帮助解决这个问题。这是一块小型计算板，大小大约相当于信用卡，可以连接到电脑显示器或你的电视。

首先，`raspberry pi` 设备可以执行我们对传统桌面电脑所要求的任何操作，例如处理不同的语音、上网、创建表格、玩游戏、播放高清视频等。不仅如此，我们还会发现该设备还具有与世界交互的能力。

正如你所看到的，在需要工作时，我们需要了解关于 `raspberry pi` 的很多。

接下来的章节将讨论 `raspberry pi`。`raspberry pi` 越来越受欢迎。但为什么呢？这么多人爱上 `raspberry pi` 到底引起了什么轰动？这本书将关注所有原因，我们还将学习如何用 Python 编程以及你可以使用的不同工具。

如果你观察 `raspberry pi` 的结构，你首先注意到的是它非常小。`raspberry pi` 的尺寸与典型的信用卡相似。`raspberry pi` 的这种小外形本身就是设备的一个特性，尽管它从箱子里取出时看起来完全完全成品。

与现代主板相比，`raspberry pi` 是一种以微型外形、低廉的价格以及通常全尺寸 PC 预期的功能面向普通消费者的计算机。此外，互联网上还有一个整个 `raspberry pi` 社区，致力于帮助人们解决有关该设备的疑问。无论你是刚买了第一台 `raspberry pi` 需要帮助设置，还是在项目正在使用 `raspberry pi`，你都会对社区如此积极、快速地加入讨论，并对你的问题给出建议和反馈感到惊讶。

树莓派（Raspberry Pi）的诞生源于这样一个理念：制造一种尺寸紧凑、功能齐全的计算机并以合理的价格提供给普通消费者。这不仅能促进教育行业的发展，还能让计算机技术在各种项目中易于实施和定制（教育项目、DIY 项目或任何可以发挥树莓派威力的实验）；简而言之，其前景几乎是无限的。树莓派基金会成立于 2012 年，在限量产后，其 Beta 测试取得了巨大的成功。如今，树莓派已成为领先的设备，在各种人类交互环境中立了稳固的足，包括家庭、办公室、智能工厂、数据中心、交互式教室以及其他充分利用小型手持电脑功能的场所。

当我们想到计算机时，通常会发现一个显示器、键盘、鼠标和 CPU。但树莓派是一个功能齐全的计算机系统，它嵌入在一个只有信用卡大小的小电路板上，成本比你找到的大多数视频游戏还要便宜。通过它，人们可以完成许多事情，如制作机器人、学习编程以及各种迷人且奇异的项目。

社会现在对程序员的需求比以往任何时候都大，树莓派的发布引发了人们对计算机技术和科学的新一轮热爱。

树莓派作为主电脑可能不是一个绝佳选择，因为它只有 512MB 到 1GB 的内存，且存储目的是使用 SD 卡；但它还可以用于许多其他用途，从为家庭自制的机器人提供动力、开发复古视频游戏，到成为家庭备用电脑以及连接网络的气象站。

如果你正在寻找开启自己的树莓派之旅的动力，那么你来对地方这里了，因为我们安排了可能是最好的用例来给你提供一些思路。

## 第一章：树莓派基础

![Image00125.jpg](img/Image00125.jpeg)

### 什么是树莓派？

树莓派是由总部位于英国的慈善机构树莓派基金会开发的低成本单板计算机。树莓派可以连接到显示器或电视机，并可以使用 USB 鼠标和键盘进行操作。该设备的尺寸与信用卡相当，且运行功耗低。它包含了通用计算机中常用的所有接口，如 USB 端口、音频接口、HDMI 输出端口、以太网端口等。除了这些标准接口外，该设备还提供了一些通用输入/输出（GPIO）端口。这些 GPIO 引脚可以配置为输入或输出端口，从而使设备能够作为一个低功耗、高性能的嵌入式系统运行。市场上有多个版本的树莓派，取决于其提供的功能。

树莓派基金会在英国开发了树莓派，第一台设备于 2012 年初发布。截至今日，已经发布了多个版本的树莓派，并随着每个版本的推出不断改进。甚至还有工业型号和越来越小的版本，如树莓派 Zero（Raspberry Pi zero）。到 2017 年底，树莓派销量已超过 1700 万台。

### 开发目标

树莓派基金会的目标向年轻人介绍硬件和软件，并促进他们进入编程领域。树莓派购买价格相对便宜，因此使用树莓派开发的门槛非常低。树莓派独特之处在于，这张信用卡大小的小隐藏了一台完整的计算机。

同时，可以轻松实现许多日常生活和职业项目。树莓派基金会也发挥着重要作用。在 raspberrypi.org 网站上，你可以找到许多可以轻松构建的宏大项目的建议。树莓派基金会还开展许多学校项目，向青少年学生介绍编程。由于有许多基于树莓派的不同软件和硬件项目，我想在下一章中展示其中的一些。

这里还有很多话想说，因为现在已经有了基于树莓派的整个业务和商业设备。这表明树莓派已经变得非常普及，不再仅仅是年轻人的学习设备。

### 硬件规格

你的树莓派具有以下硬件规格：

- `Bcmquad-core` 64 位`arm a53` CPU，主频 `1.4ghz`
- 用于无线和蓝牙的 `cypress 4345` 芯片
- `400 mhz` 视频核心 GPU
- `1 gb lpdr22-900 sdram`
- `802.11 ac` 无线局域网
- 蓝牙 `4.2` 芯片

### 电源

- `2.5 amp` 电源输入
- 增加了 `poe` 连接

### 上网

你可以通过以太网线或无线连接将树莓派连接到互联网。要连接 WiFi，查看屏幕右上角。你会看到一个带有红色叉的图标。从下拉菜单中选择正确的网络。提供 WiFi 连接密码，你的树莓派就连接到互联网了。

### 树莓派用来做什么？

树莓派笔记本电脑可以像任何其他 Linux 系统一样使用。该系统的“硬盘”很小——它没有使用传统的硬盘，而是使用微 SD 卡。你可以轻松地处理办公文档、运行游戏并播放视频。

你可以从任何计算机通过安全外壳（`ssh`）连接到树莓派的命令行界面。`ssh`是一种网络协议，为管理员提供了一种安全访问远程计算机的方法。在这种情况下，你不会从连接中获得图形界面。但是，你可以从另一台计算机上的终端应用程序执行命令。这些命令将通过`ssh`执行在你的树莓派上。

如果远程访问树莓派并且还需要图形界面，可以通过虚拟网络共享（VNC）来实现。这将会是一个缓慢的过程，但它可以让你在需要时视觉连接到树莓派。

### 使用树莓派 3b+模型还需要什么

为了让树莓派充分作为台式计算机工作，你需要将以下设备连接到前面列出的端口和连接：

电源：你需要一根`usb-a`转`micro-usb`线。`5.1 伏`的微 USB 电源为其供电。最好的选择是从当地零售商处购买一个`300 瓦`的电源。这将为你的树莓派提供足够的功率，使你无需进一步升级即可进行工作。确保你不要过载电源。仔细查看电源上提供的规格，可以让你对系统的电源处理能力有一个大致的了解。

### 键盘和鼠标
键盘和鼠标：树莓派允许你连接任何 USB 或无线键盘或鼠标。该设备带有 4 个 USB 端口，在连接键盘和鼠标后，还有两个空闲的 USB 端口

### 显示器
原始树莓派支持 `hdmi` 和 `rca` 端口。树莓派 3 拥有 `hdmi` 和神奇的 `3.5mm` 媒体端口。每个版本的树莓派都兼容 `hdmi`，这意味着你可以轻松将其连接到家中的兼容 hdmi 的电视上。

### Micro sd 卡
如果你想在树莓派上使用自己的 micro sd 卡，你需要获取 `noobs` 安装程序。`noobs` 代表“开箱即用的软件”，这可能是一个相对复杂的过程，因此建议购买制好的 micro sd 卡。制好的 micro sd 卡并不贵，而且可能会为你节省大量的时间、金钱和精力。如果你坚持要准备自己的 sd 卡，请访问 [www.raspberrypi.org/downloads](http://www.raspberrypi.org/downloads)。在准备卡片时，你可以选择广泛的操作系统发行版，这对于 Linux 新手来说是一个巨大的优势；然而，最好使用 `noobs` 安装程序并使用它提供的标准 Raspbian 操作系统。

### 外壳
你的树莓派只是一个主板。它没有外壳，这就是它价格如此低的原因。建议为该设备购买一个外壳以保护它免受磨损并延长其寿命。

### 从 noobs 启动
如果你购买了预装了 `noobs` 的 micro sd 卡树莓派，你的设置将简单得多。连接到显示器后，它将显示安装程序已加载。点击“安装”，安装将在短时间内完成。

树莓派提供了一个 Linux 桌面，你可以像使用其他电脑 一样使用它。如果你熟悉 Windows 环境，它很容易使用和导航。

现在你的树莓派已经完全安装并配置完成，我们可以开始详细地探索它了。准备好深入吧！

### 附件

### 摄像头
回到 2013 年，树莓派基金会及其发行商发布了固件更新，允许树莓派使用摄像头。摄像头是一条扁平线，你可以将其插入 `csi` 接口。当你查看 Raspbian 时，你需要确保通过配置摄像头选项在开发板上启用摄像头。树莓派摄像头可以拍摄高达 1080p 的照片或拍摄 640 x 480p 的视频，三年后，800 万像素版本向公众发布。

### Getboard
基金会制作此附件仅用于教育目的，以便扩展 `gpio` 引脚，从而可以使用一系列开关和传感器来控制接口。

### 红外摄像头
这款摄像头本将作为不包含红外滤镜的摄像头模块的一部分，它被称为 pi noir。

### 软件

## 操作系统
如前所述，你将尝试坚持使用 Raspbian 操作系统，它是 Linux 的扩展。如果你不想使用基于 Linux 的操作系统，还有其他操作系统供可以使用。

### 驱动 API
用于图形处理器的 `videoicore iv` 将使用一个二进制二进制文件（binary blob），在其中你可以从 sd 卡启动图形处理，并仅在启动后添加额外的软件。驱动程序中完成的大部分工作将通过处理器及其相关代码的闭源来完成。任何软件使用都将运行其闭源，但你可以下载某些特定应用程序在内核内部打开原始代码。内核的 API 将为库文件设计，以确保树莓派处理正确且代码不会构建可能导致树莓派无法正常运行。

### 固件
树莓派使用的所有固件都将是闭源并使用可以自由分发的二进制文件。你无法为树莓派找到很多开源的固件。

## 第 2 章：设置

### 设置你的树莓派
在本章中，我们将概述设置树莓派需要进行的所有工作。这将包括让它启动并运行所需的所有内容，所以请注意。起初很困难，但从这里开始会变得容易！本指南假设你正在使用树莓派 3 型，这是最新的型号。然而，如果你使用的是旧型号，整个过程中的情况在很大程度上将保持不变。

首先，你需要以下内容来设置你的 pi 以其作为台式电脑运行：
- 显示器（显而易见的）
- 键盘和鼠标
- Micro sd 卡
- 操作系统

### 选择操作系统
你应该在你的树莓派上使用什么操作系统？这个问题有许多不同的答案。许多不同的公司已经制作了可以在树莓派软件上运行的操作系统版本，甚至微软也发布了可以在树莓派硬件上运行的 Windows 版本。所以请记住这一切，在你的树莓派上具体应该使用什么软件？

无论你想使用什么操作系统，noobs 都会提供支持，并且是一个出色的操作系统安装程序。虽然我建议你安装 raspbian，但最终你对决定在 pi 上安装什么内容拥有自主权，让我们现在谈谈设置过程。

![Image00126.jpg](img/Image00126.jpeg)

### 安装 noobs
这些指令将告诉你如何设置 raspbian。如果你决定安装不同的操作系统，那么此书将无法帮助你。然而，只要通过 noobs 安装，过程对于所有操作系统来说都是相同的。因此，安装时不应该遇到任何问题。话如此，让我们先安装 noobs。

为了用操作系统设置树莓派，你需要获取你的 sd 卡并将其插入电脑。

搜索 `sd formatter 4.0`。下载并安装它。（由于格式化与链接兼容性不好，所以我无法为你提供链接，遗憾。）它是由一个名为 sd association 的组织发布的，所以只要你是从他们的网站获取的，就应该是安全的。

安装软件并启动 sd formatter 程序。选择你的 sd 卡磁盘驱动器，然后按照默认设置指示进行格式化，

如果一切顺利，你现在应该可以将你的树莓派接入电源并开始一些高强度的开发了。如果你使用的是较新的树莓派型号，它应该内置了 wifi。然而，旧型号则需要你通过以太网连接互联网，或者插入与树莓派兼容的 wifi 适配器。

当树莓派上的指示灯闪烁时，你就知道树莓派已启动。此时，你就能知道一切是否运行良好，因为指示灯会亮起，并且你的显示器上应该显示视频画面。

# 安装 Raspbian

既然我们安装了 noobs，就可以继续安装 Raspbian 或你喜欢的其他操作系统。再次强调，本书将只讨论 Raspbian。尽管如此，安装操作系统的过程对于树莓派可以使用的所有其他操作系统来说都是相同的。

在操作系统启动后的主界面上，确保选中了 Raspbian。这是大多数社区推荐的操作系统，特别是对于树莓派的新手来说。

点击 install（安装），然后点击 yes（是）确认覆盖你的 SD 卡。

稍等片刻后，你的操作系统就会安装完成。正如我所说，这是一个非常直接的过程。

你的树莓派将重启，并带你进入 Raspbian 操作系统的主界面。

![Image00127.jpg](img/Image00127.jpeg)

# 起始

现在你已经进入 Raspbian 的主界面，是时候让奇迹发生了。这是你与树莓派冒险之旅的开始。可以随便点弄，看看它能提供什么。你从一开始就能看到，它内置了许多旨在帮助你学习各种技能的程序，这揭示了树莓派的初衷——旨在帮助弱势群体学习计算机科学以及通用的编程。

现在，你面对着你的操作系统。如果你以前从未用过 Linux 操作系统，你可能会有很多疑问。此外，即使你以前用过 Linux 操作系统，如果你主要一直使用 KDE 发行版，那么这可能和你以前用过的完全不同。所以，让我们先回答一些问题。

## 我在看什么？

这个问题的答案很简单：Raspbian。Raspbian 是 Linux 操作系统的一种发行版，你很可能以前听说过它。它是一个流行的 Linux 发行版 Debian 的分支。还有许多其他的 Linux 发行版，其中之一是 Ubuntu。Raspbian 的设计旨在完美匹配树莓派的硬件需求及其特定的 CPU 架构。

### 什么是 Linux？

Linux 本身是很久很久以前的另一个操作系统 Unix 的分支。Unix 因为各种原因而极其闻名，以至于单单关于它就可以写一本书（而且已经有很多了，写得非常好）。

Unix 本身启发了人们每天使用的许多操作系统，包括 Linux（Linux 本身又启发了极其流行的 Android 移动操作系统）和 macOS（iOS 移动操作系统即源于此）。换句话说，如果你有一部手机或一台非 Windows 电脑，你已经在使用受 Unix 启发的计算机了。由于它在 80 年代的无处不在，加上诸如 Linux 和 FreeBSD 等操作系统非常契合黑客文化（在信息和软件自由方面，即既像言论一样自由，也像啤酒一样免费的自由），Unix 在很长一段时间内一直是软件开发领域的王者。这段很长的一时期导致了今天：你正坐在一个陌生的操作系统面前，不知道不知道该做什么。

![Image0128.jpg](img/Image0128.jpeg)

让我们仔细看一眼我们的操作系统。首先，Linux 系统最重要的部分是终端（terminal）。如果你用苹果设备，你可能已经在终端里弄过几次了。终端是 Unix 使用最频繁的功能之一，因为它提供了一种获取包、管理系统以及进行更多操作的极其简单的方法。现在依然如此。理解系统意味着理解终端是如何工作的，以及你用它能做的所有不同事情。所以，如果你想了解 Linux 是如何工作的，请读读一本旨在教你终端如何运作的指南。

Linux 的主要吸引力之一是它是完全免费的，而且这确实如此。你可以摆弄你的系统信息，并对计算机及其主板拥有完全的控制权。这就是为什么像我这样的许多极客喜欢 Raspbian 的原因：它既易于使用，又提供了 Linux 发行版所具备的所有控制功能。

你会发现 Raspbian 内置了相当多的不同的东西。值得注意的是一个旨在帮助你解决代数相关问题的程序，名为 matmatica。你还会注意到里面包含了一个 Chromium 版本。这个浏览器和 Google Chrome 非常相似，它只是 Google Chrome 的开源版本。不过，Chromium 标准版本与这个版本之间是有区别的；这个版本比其他版本轻得多，因此它在树莓派精密的架构上运行得好得多。你可以打开任何你想打开的标签！（别真的按你想打开的那么多标签，那样结果不会好的。）

最后一点值得注意的是，该操作系统带有一个版本的 Minecraft，被称为 Minecraft Pi。这和 Minecraft 非常像，只不过它旨在帮助孩子学习如何编程。不过，如果你去点弄并尝试一下，可能会觉得它挺有趣的。此外，这是一本大书，所以给自己留一点时间玩游戏并无妨。

Linux 是折腾者（tinkerers）的最佳选择。原因有很多。首先是由于它降低了折腾的整体成本，因为 Linux 的文化支持开源和免费软件的使用。这意味着你可以在获取软件上花费更少的钱，并花费更多时间使用你的软件。完全开放这一点也非常棒了，因为如果你的编程水平足够高，你可以破解源代码并按你的意愿进行修改。那里没有秘密，你清楚自己正在面对什么。此外，也许最大的吸引力在于作为 Linux 程序员，你有许多开源工具可供。

从技术上来说，并没有所谓的“嵌入式 Linux”。当我们谈论嵌入式 Linux 时，我们将其作为一个统术语，用来指代运行 Linux 的嵌入式系统。嵌入式系统是指为单一、特定应用设计的计算硬件。相比之下，个人电脑有多种用途——浏览互联网、玩视频游戏或编写关于树莓派的电子书。然而，最近区分通用计算设备和嵌入式系统的界限变得模糊了。树莓派作为本书的主题，可以被归类为这两种者。这取决于你赋予它的用途。

明确的是，嵌入式系统仍然与通用计算机不同。它们拥有独有的特性，包括以下：

*   它们的目的非常明确，并且通常专为此目的而设计。
*   它们通常性能过剩。它们往往缺乏个人电脑通常拥有的强劲动力。
*   它们在大系统中运行，作为其他传感器和其他设备的枢纽。这与通常独立运行的 PC 形成对比。
*   它们的角色通常非常重要，因此被分配了特定的任务。
*   它们能够实时处理事务。

你可以通过在 raspbian 终端中疯狂操作来建立一个嵌入式 Linux 环境。这个设置是一个复杂的过程，并且假设你已经对技术方面略有所知。请随时自行研究。我们关于树莓派还有更多需要学习的内容。

# 第 3 章：如何使用树莓派

你可以在树莓派上运行多种类型的软件，特别是在各种操作系统中——你可以通过它们运行你的电脑。在所有可用的操作系统，最流行的是 raspbian，它是树莓派基金会的官方操作系统。Raspbian 基于 debian linux，专为树莓派制作，配备了一系列预装的插件，将帮助你快速上手。

### 欢迎向导

当你第一次运行 raspbian 时，你将遇到欢迎向导。这个工具将允许你配置 raspbian 的设置，以便树莓派的行为完全符合或接近于你的意愿。

**注意：** 如果你想关闭欢迎向导，只需点击向导底部的“取消”按钮即可。然而，我们建议不要这样做，因为某些某些功能（包括无线网络）在回答第一组问题之前将无法工作。

点击“下一步”按钮后，将出现一个语言、国家和时区的下拉框，你需要根据自己的地理位置进行点击。还有一个复选框允许你选择合适的键盘布局；例如，如果你使用的是美式布局（us-layout）的键盘，务必勾选 us-layout 选框。如果英语不是你的第一语言，但你仍然倾向于使用英语而不是母语，请点击“使用英语语言”复选框。完成后点击“下一步”。

下一个屏幕是关于更改默认密码，密码是‘raspberry’——这完全出于安全考虑，创建一个新密码是一个好主意，这样黑客和机器人就无法轻易破解并访问你的账户等。在提供的空间内输入你的新密码。如果你使用的是复杂密码并想查看它的样子，点击“隐藏字符”旁边的按钮显示密码，并将其写在只有你可以访问的纸张或额外的记笔记本上。记住，为了安全起见，你必须输入密码。完成所有这些操作后，你可以点击“下一步”。

下一个屏幕将让你设置 wifi 网络。你可以从键盘或鼠标已列出的系列网络中选择。在点击“下一步”之前，点击你想要的网络名称。为了确保你的无线网络安全，你需要插入其预共享密钥（即密码）；这通常写在路由器底部或随附附的卡片上。当你点击“下一步”时，就可以连接到网络。如果你不想选择无线网络，可以点击“跳过”。

**注意：** 只有树莓派 3、pi 4 和 zero 系列具有内置无线网络功能。如果你在使用上述任何其他型号并需要网络功能，你需要购买一个 usb wifi 适配器。

在下一个屏幕中，你必须为 raspbian 操作系统以及你树莓派板上的任何其他软件安装更新。你可以点击“下一步”安装更新，或者如果你想以后安装，可以点击“跳过”。注意，下载和安装更新可能需要几分钟，请耐心等待。更新安装后，会出现一个显示“系统已最新”的对话框，之后你只需要点击“确定”按钮。

最后，欢迎向导的最后一个屏幕是一个通称为“重启”的简单过程，你需要重启树莓派以便某些更改生效。你只需要点击“重启”按钮，你的树莓派系统将重启，这一次欢迎向导将不再出现。话虽如此，是时候行动了。

### 使用桌面

如今许多树莓派型号上安装的 raspbian 操作系统被称为“带有树莓派桌面的 raspbian”，这是系统的主要图形用户界面。桌面将配有一个背景纸，一些你将要使用的基础程序会出现在壁纸之上。你会在桌面顶部找到一个任务栏，它允许你加载任何想要打开的程序；任务栏中的任务代表这些程序。

菜单栏的右侧是系统托盘所在。如果树莓派连接了任何可移动的存储设备（如 usb 内存棒），你需要点击弹出符号来安全地弹出并移除它们。在最右侧，你会找到计时器，点击它可以调出一个数字日历。

计时器旁边是扬声器图标；使用鼠标左键点击图标可以调整系统音量，或者你可以点击鼠标右键选择你希望系统使用的输出设备。紧挨旁边的是网络图标；当你看到网络信号强度以一系列条显示时，你就知道自己连接到了无线网络，但如果你连接的是有线网络，则只会显示两个箭头。你可以点击网络图标列出附近的网络列表，旁边的蓝牙图标将允许你连接到附近的任何蓝牙设备。

在菜单栏的左侧，你会找到启动器，可以在这里运行安装在 Raspbian 操作系统上的所有程序。某些程序将以快捷图标的形式出现，而另一些隐藏在菜单某处的程序可以通过点击位于右侧的树莓图标来打开。

菜单中的每个程序都分为不同的类别，并根据其用途明确命名：例如，“编程”类别包含允许我们编写程序的软件——我们将在后面的章节中详细介绍——而“游戏”类别则允许你玩列出的任何游戏。请注意，本指南并没有涵盖所有的程序，因此非常欢迎你根据自己的意愿自行查看。

## Chromium

开始使用树莓派板时，要做的第一件事是打开 `chromium` 浏览器：在菜单的左上角，你需要点击树莓图标。将鼠标光标移动到“Internet”类别，然后点击 `chromium` 网页浏览器即可打开它。

Chromium 并不难上手，那些在其他电脑上使用过谷歌 Chrome 浏览器的人会发现它的操作非常相似。像任何其他网络浏览器一样，chromium 允许你打开并查看网站，使用社交媒体平台、聊天网站和表单与世界各地的人进行交流，以及玩游戏和观看视频。

为了获得更好的体验，我们建议最大化 `chromium` 浏览器的窗口：在 chromium 窗口标题栏的右上侧你会你会三个图标。你需要点击中间的向上箭头图标，这将窗口最大化以填充整个屏幕。最大化左侧的按钮是任务栏上的最小化按钮，点击它会隐藏窗口。最大化的右侧是关闭功能，它当然会关闭窗口。

注意：你必须在关闭窗口之前保存你的工作。虽然大多数程序在你点击关闭按钮时会弹出保存工作的警告，但其他程序并没有这个功能。

位于 chromium 窗口左上角带有放大镜的大型白条是地址栏。点击地址栏，输入 `www.raspberrypi.org`，然后按下键盘上的回车键。树莓派官方网站将打开。你也可以通过直接在地址栏输入“raspbian”、“educational computing”或“raspberry pi”来进行其他搜索。

当你第一次加载 chromium 时，窗口顶部会显示几个标签页。如果你想查看另一个标签页，点击它；如果你想在不关闭浏览器本身的情况下关闭标签页，点击标签右边缘的交叉号。要打开新标签页，你可以点击标签最右侧的标签按钮，也可以按住键盘上的 `ctrl` 键并在松开 ctrl 之前按下 `t` 键。

如果你想关闭浏览器，只需点击窗口右上角的关闭按钮即可。

### 文件管理器

你保存的任何文件，无论是你编写的程序、创建的视频还是从网上下载的图像——都会直接进入你的主目录。要查看主目录，再次点击树莓图标弹出菜单，将鼠标悬停在“附件”（accessories）上，然后点击“文件管理器”加载它。

通过文件管理器，你可以浏览树莓派 microSD 卡或任何连接到板接口的可移动设备（如 USB 闪盘）中的各种文件夹（也称为目录）和文件。当你第一次打开它时，主目录会自动打开。在这里，你会发现许多文件夹（也称为目录）——与菜单类似——按类别组织。你会找到的主要目录包括：

- Documents（文档）：你创建的大部分文件（从故事等）都将保存在这里。
- Desktop（桌面）：当你首次加载 raspbian 时，这将是你看到的文件夹；如果你如果你在这个文件夹中创建并保存文件，它将出现在你的桌面上，使其更容易查找。
- Magpi：此文件夹包含树莓派基金会官方杂志《Magpi》的电子版。
- Downloads（下载）：使用 chromium 浏览器在网上下载的任何文件将自动保存到下载文件夹中。
- Pictures（图片）：此文件夹专门用于存储技术上称为图像文件的图片。
- Music（音乐）：任何在树莓派板上放置或创建的音乐都将存储在此文件夹中。
- Videos（视频）：此文件夹留用于从外部存储设备上传或从 chromium 浏览器下载的任何视频。
- Public（公共）：尽管其他树莓用户有自己的账户，你存储在此文件夹中的任何文件或文件夹对其他树莓用户可用。

你会发现文件管理器窗口被分为两个窗格：左窗格显示你的树莓派目录，而右窗格显示左侧窗格中所选目录的文件和目录。如果你将可移动存储设备插入板载的 USB 端口，会弹出一个对话框询问你是否想在文件管理器中打开它；通过点击确定按钮，你将能够查看该设备中的文件和目录。

你可以轻松地在树莓派的 microSD 卡和其上的可移动设备之间复制文件，甚至将它们从 microSD 卡传输到你的可移动设备。当你两个单独的文件管理器窗口中同时打开了可移动设备和主目录时，点击并按住鼠标左键选择想要移动的文件，将其滑动到另一个窗口，然后松开鼠标按钮。这个过程被称为拖放。

另一种方法是点击一次文件，选择“编辑”菜单，选择“复制”，点击另一个窗口，选择“编辑”菜单，然后点击“粘贴”。

从编辑菜单找到“移动”选项在执行上类似，只不过它在被复制后会从原始位置删除文件。更快的方法是使用快捷键 `ctrl+c` 复制，或使用 `ctrl+x` 剪切并通过 `ctrl+v` 粘贴。

注意：使用快捷键如 `ctrl+c` 复制文本、文件或文件夹；你需要先按住 `ctrl` 键，然后按下第二个键 `c` 最后再松开它们。

完成操作后，点击窗口左上角的关闭按钮关闭文件管理器。如果有其他打开的窗口，你需要关闭所有窗口。如果树莓派板连接了可移动设备，你需要在拔掉它之前点击屏幕右上角的弹出按钮将其弹出。

注意：在拔掉外部存储设备之前务必点击弹出按钮。如果不这样做，存储设备中的文件可能会损坏或无法使用。

Libreoffice，办公套件，

如果你想写文档、文章、诗歌或其他任何内容，LibreOffice Writer 就是你所需要的。如果你用过 Microsoft Office 或 Google Docs，那么你已经对如何使用 LibreOffice 的文字处理器有了很好的了解。

有一点需要，并不是每个 Raspbian OS 镜像都默认安装了 LibreOffice。如果情况确实是这样，你可以使用推荐的软件工具来安装它们。

除了能够编写文档之外，此文字处理器还允许你以各种创意方式对其进行格式设置：你可以更改字体颜色、大小，插入图像、表格、图表，添加效果以及你选择的任何其他类型的内容。与其他文字处理程序一样，LibreOffice Writer 会在你输入时检查你写的所有内容是否有错误，并分别用红色和绿色标出拼写和语法错误。

如果你不知道写什么，我们建议你写一段关于你到为止学到的关于树莓派开发板以及其中安装的软件的所有内容。窗口顶部有几个图标，你可以尝试一下看看它们的作用：看看你是否可以增大字体大小以及更改颜色。如果你不确定如何操作，可以将鼠标光标悬停在每个图标上，查看“工具 tip”，它会让你知道图标的含义及其功能。如果你对写的内容满意，点击文件菜单，然后选择保存选项来保存你的所有工作。为你的文件命名，最后点击保存按钮。

**注意：** 你应该始终保持保存工作的的良好素养，因为你永远不知道何时会遇到停电、短路或其他任何干扰你在树莓派开发板工作的意外情况。

LibreOffice Writer 是你在 LibreOffice 办公套件中找到的许多程序之一。该套件中包含的其他办公软件包括：

* `LibreOffice Calc`：用于创建图表、图形和处理数字的电子表格。
* `LibreOffice Base`：用于存储、快速查找和分析信息的数据库。
* `LibreOffice Impress`：用于创建演示灯片以及播放幻灯片的工具。
* `LibreOffice Draw`：一个插图程序，你可以在其中创建图表和图片。
* `LibreOffice Math`：用于创建格式适当的数学公式的工具，也可以用于其他文档。

LibreOffice 也适用于其他计算机和操作系统。如果你倾向于在 Pi 系统上使用它，可以访问 `libreoffice.org`，下载文件并将其安装在任何操作系统上，无论是 Linux、Apple Mac OS 还是 Microsoft Windows。

如果你想了解更多关于如何使用 LibreOffice，请点击帮助菜单。如果你不再需要它，可以指向并点击窗口右上角的关闭按钮来关闭 LibreOffice Writer。

**注意：** 许多程序都有帮助菜单，你可以通过它了解某个特定程序以及如何使用它。如果你在操作程序时遇到困难，这会非常有用。

### 推荐软件工具

虽然你已经通过 Raspbian 操作系统可以使用了广泛的预装软件集合，但如果你喜欢，也可以获取更多软件。这就是推荐软件工具发挥用场的地方，因为它包含了你所找到的一些优秀的软件系列。

请注意，推荐软件工具需要连接互联网才能操作。一旦连接，点击树莓派菜单图标，将光标移动到“首选项”（preferences），然后点击“推荐软件”（recommended software）。这将打开该工具并开始下载任何可用软件的信息。几秒钟后会出现一些兼容软件包的列表。像树莓派菜单一样，这些也被组织在几个类别中。点击左窗格中的任何类别来查看该类别下的软件，或者点击“全选”查看所有内容。如果你看到任何软件旁边有勾选标记，意味着它已经安装在你的操作系统上。如果框内没有勾选，使用左鼠标点击复选框，以便为安装做准备。你可以标记尽可能多想要准备安装的编号，但要确保你的 microSD 卡中有足够的空间存放这些程序；否则，你将限制安装。

同样，你也可以通过这种方式卸载软件：寻找任何复选框中有勾选的软件并点击该框取消勾选。但如果你改变了主意或犯了错，可以回到上一个部分重新勾选。当你准备就绪后，点击 OK 按钮开始安装或卸载你选择的软件。在你下载并安装了区域内的任何软件后，会出现一个对话框；点击 OK 按钮退出推荐工具。

“添加/删除软件”工具是另一个可以帮助你安装或卸载软件的工具。它位于 Raspbian 菜单中相同的“首选项”类别下。这里有大量的软件可用，但它们都没有经过树派派基金会的批准。

### 树莓派配置工具

你会发现它的功能与你最初使用的欢迎向导类似：你将更改 Raspbian 操作系统中的许多设置。首先，点击树莓派图标，将鼠标光标移动到“首选项”，并选择加载“树莓派配置”（Raspberry configuration）。

该工具分为四个标签页，每个标签页控制 Raspbian 的一部分。工具首次加载时你看到的第一个是“系统”（system）：你可以设置主机名——这是树莓派开发板在你的有线或无线网络上使用的名称——更改账户密码以及许多其他设置，尽管这些设置中的大多数不需要更改。

**注意：** 此概述旨在帮助你熟悉该工具以及如何使用它。

将鼠标光标移动到“接口”（interfaces）标签页并用左鼠标点击它以调出下一个类别。你会看到许多被禁用的设置。只有当你向树莓派中引入新软件（包括树莓派摄像头模块）并且按照硬件制造商的指示时，你才能更改这些设置。这里唯一的例外包括 `vnc`，它启用“虚拟网络计算机”，允许你通过 vnc 客户端从网络上的另一台电脑查看并控制 Raspbian 桌面；`remote gpio`，你可以从网络上的另一台电脑使用树莓派的 gpio 引；以及 `ssh`，它启用“安全外壳”，允许你通过网络上的另一台电脑使用 ssh 客户端登录树莓派。

当你点击 `performance` 标签卡时，可以查看第三类别。在这里，你可以配置树莓派图形处理器（`gpu`）使用的内存量，并且根据某些型号，可以通过一种名为 `overclocking`（超频）的过程提高你开发板的性能。不过，除非你需要更改这些设置，否则保持原样更好。

最后，你可以通过点击 `localization` 标签卡查看最后一个类别。在这里，你可以设置区域语言（locale），其中你可以控制数字的显示方式、Raspbian 使用的语言、更改键盘布局、更改时区，并为 Wi-Fi 功能设置国家。然而，到目前，你需要点击 `cancel` 按钮退出工具，而不进行任何进一步更改。

**警告：** 不同国家对 Wi-Fi 无线电使用的频率类型有不同的规定。例如，如果你在树莓派配置工具中将 Wi-Fi 国家设置为你当前所在地以外的国家，这会让你的设备产生困惑，并在连接网络时遇到困难。更糟糕的是，这在无线电许可法下可能是非法的。换句话说，不要这样做。

### 关机

在探索了 Raspbian 桌面并熟悉了它之后，是时候学习如何安全地关闭树莓派了。和人们使用的任何计算机一样，树莓派将你的文件存储在易性内存中——这种内会在系统掉电后被清空。对于你创建的每一个文档，在输入时进行保存至关重要——你的文件将在这里传输到非易性内存中，即 microSD 卡——这样你就可以检索保存的文件并继续工作。

但你正在处理的文档并不是唯一打开的文件。操作系统 Raspbian 在运行期间会打开几个文件，如果由于任何原因，在文件仍打开时将电源线从树莓派主板上拔掉，可能会导致整个操作系统损坏。你将不得不重新安装。

因此，为了防止这种情况的发生，你需要指示 Raspbian 保存你所有的文件和文档，并为关机时机做好准备——这个过程被称为关机。

**警告：** 记住，在先关机之前不要从树莓派主板上拔掉电源线。如果你这样做，它会损坏 Raspbian，你可能会丢失创建或下载的任何文件。

要关机，点击桌面左上角的树莓派图标并选择 `shutdown`。会弹出一个带有三个选项的对话框：`shutdown`（关机）、`logout`（注销）和 `reboot`（重启）。`shutdown` 是你最常用的选项，点击它将指示操作系统关闭所有打开的文件和软件，关闭整个系统。当你看到显示器变黑，距离树莓派上的绿色闪烁灯消失还有几秒钟时，就可以安全地关闭电源了。

如果你想重新开启树莓派，只需要断开然后重新连接电源线，或者切换墙上插座的电源开关。`remote`过程与关机类似，它会关闭你的每一个文件，但不是关机，而是重启你的树莓派——类似于你使用了 `shutdown` 选项并必须断开重新连接电源线。你对树莓派所做的某些更改需要重启才能生效——例如安装某些软件——或者软件崩溃导致你的操作系统处于不可用状态。

最后是 `logout` 功能，如果你的树莓派上有多个账户，这个功能非常有用：它会关闭你当前运行的任何程序，并立即显示登录界面，你可以使用用户名和密码访问另一个账户。如果你不小心按了注销，只需输入 `pi` 作为你的用户名即可回来。

# 数据和变量

我们将首先查看的是数学运算以及你如何执行这些运算。然而，为了理解这一点，你需要了解关于数据的一点点。Python 以一种相对独特的方式理解数据，但所有编程语言都以这种方式理解数据是有原因的。数据是用于表示某些概念的任何单一信息。任何单独的数据单元被称为 `value`（值），值可以采取多种不同的形式。

然而，并不是所有的计算机都能真正理解这些不同形式；相反，计算机理解的是 0 和 1 的原始概念，即在计算机底层运行的二进制计算。在二进制代码之上有一层被称为 `assembly code`（汇编代码）的抽象层，它在代表单个值的位或不同二进制代码集上进行操作。在它之上是另一层被称为操作系统的抽象层。还有第三层抽象层，即正在使用的编程语言。它与操作系统配合，将我们能理解的东西转换为汇编语言，然后计算机的处理器将其转换为一组不同的计算。这一切都是在微秒甚至纳秒级内完成的。

这一切的关键点是，计算机是以 0 和 1 来理解事物的，而我们看到值的方式对计算机来说没有任何意义。为了解决这个问题，程序员们在很久以前就决定让计算机将不同的值分为不同的类型。这些数据类型告诉计算机如何以及以什么方式对给定的值执行操作，因为它们对应 0 和 1。这是一个非常复杂的架构，所以如果它没有立即让你完全理解，不要觉得太抱歉。

总之，为了正确理解这一切，我们必须稍微拆解这些数据类型，并用比现在更抽象的眼光来看它们，让我们这样做吧。我们将做的下一步是仔细查看在 Python 中使用的不同类型的数据。

## 整数 (Integer)

`integer` 数据类型指的是在我们的抽象理解中对应整数的数据单元。因此，这些将是如 `7`、`39` 或 `-3` 等数字。

### 浮点数 (Float)

`float` 数据类型指的是在我们的抽象理解中对应小数的数据单元，例如如 `3.141569` 或 `94.3332`。

## 双精度浮点数 (Double)

Double 代表“双精度”数字，指的是一种非常特殊的数字。你现在不需要深入理解它，因为在 Python 中，`float` 和 `double` 的作用是非常等同的。这种区别可以追溯到计算机内存和处理能力远低于现在的时代，但对于我们的目的来说，你完全可以忽略这一点。

## 布尔值 (Boolean)

# 布尔值（Boolean）代表 `true`（真）或 `false`（假）。等我们开始讨论程序逻辑以及逻辑在计算机科学中的实际作用时，这会有很多意义。

## 字符（Character）
`character` 代表可以在控制台中打印的任何单个字母数字或符号字符。这些可以是像 `3` 或 `$` 之类的字符。不过这种理解是微妙的，因为字符与 `ascii value` 相关，这意味着任何给定的字符也都有一个数值整数值。因此，如果你有一个字符 `"3"` 和一个整数 `3` 并尝试判断它们是否相同，它们并不相同。在编程时请记住这一点。

## 字符串（String）
我们稍后会深入讨论字符串，但字符串本质上是组合在一起的长字符链。任何字符值的集合都是字符串，无论长度是 2 个字符还是 2000 个字符。

然而，这些并不是 Python 中供你使用的所有值。但它们是你最可能立即用到的值，因此由于这个原因，我们专门在这里涵盖了它们。这些值可以在 Python 的任何表达式中表示。例如：

```python



```python
Print(3 + 3)
```

# 将打印 6

```python
Print("hey there!\n")
```

# 向控制台打印字符串

```python
Print('c')
```

# 向控制台打印字符

换句话说，这些构成了你在编程中将进行的所有操作的核心。你写的每一段代码都将与这些值打交道，并以某种方式对它们进行操作。随着你处理的代码越来越多，你会发现自己多么频繁地使用所有这些内容，并且程序中的每条语句都是以某种方式对数据进行操作。这就是编程的本质，无论好坏。

## 变量（Variables）

有时，你想要记住这些数据片段，以便在以后某个点回想起它们或更改它们。为此你可以做什么呢？答案很简单，你可以使用变量。变量提供了一种方法，让你在运行程序时很长时间内跟踪值。

回想我们之前讨论过数据类型。数据类型在 Python 中特别有用且比其他语言更多样，因为 Python 尽力让事情变得简单；然而，所有这些值都存储在计算机内存中，并根据任何给定数据类型占用的空间存储在预分配大小的盒子中。

计算机内存中的这些单独盒子可以被称为变量。把它想象成某个城市的俯视图。你可能有一堆可以放置房屋的地块。然后你通过地址引用任何给定的地块。地块就像变量本身，而地址就是变量名。

因此，你实际上可以将所有这些值存储在变量中，由你决定用什么名称引用它。假设你有一个名字类似于`dogage`的变量。如果你的狗是 4 岁，那么你可以这样设置：

```python
Dogage = 4
```

如果你的狗的名字叫 lucky，那么你可以设置一个字符串变量，如下：

```python
Dogname = "lucky"
```

Python 让命名和声明变量变得极其简单。某些语言在这一过程中会有很多障碍，但 Python 没有。这为什么这会是一件坏事呢？对于一个没有处理不同类型丰富经验的程序员来说，这可能会令人困惑，你可能会忘记并尝试对两个不同类型的数据片段进行比较，从而以相同的方式搞乱你的数据。这就是你实际上想要学习数据类型是什么的原因，它将帮助你意识到字符串`"34"`和整数`34`不是同一个，并且如果你不注意这一点，它可能会解释为什么你的比较在某一点可能会出错。

当然，如果你实际上对数据进行操作，使用变量会有用得多——在这一节中，我们将探索你处理数据的不同方式。记住，你可以回溯变量。例如，如果你想打印保存在变量中的字符串，你可以这样做：

```python
Print(dogname)
```

或者，如果你野心勃勃，想同时打印你狗的名字和年龄，你可以这样做：

```python
Print("my dog’s name is " + dogname + " and they are " + dogage + " years old.")
```

但如果发生了变化呢？例如，如果你的狗老了一岁呢？你能做什么？你可能想要在你狗的年龄上加 1。但你如何做到这一点呢？你通过实际上给它分配一个新值来实现。你可以对变量重新赋值，并像最初设置和初始化它们那样对这些变量进行操作。这个过程在很大程度上是类似的。例如，假设我们想给变量`dogage`加 1。我们可以这样做：

```python
Dogage = dogage + 1
```

变量`dogage`将取`dogage`的旧值`4`并在其基础上加 1，并将此设置为变量`dogage`的新值。理解吗？因此，如果你现在打印变量`dogage`，它将打印数字 5：

```python
Print(dogage)
```

## Python 数学（Python Math）

Python 有许多不同的运算符可以用于数学计算。Python 的数学运算符如下：

`C + d`

这是加法运算符。它用于将一个数字加上另一个。

`C - d`

这是减法运算符。它用于从一个数字中减去另一个。

`C * d`

这是乘法运算符。它用于将一个数字乘以另一个。

`C / d`

这是除法运算符。它用于将一个数字除以另一个。

`C % d`

这是取模运算符。它用于计算`c`除以`d`的余数。例如，`7 % 3`将得到 1，因为 7 除以 3 余数为 1。

这些是你需要了解的 Python 主要数学运算符。使用这些知识，你可以在 Python 中执行复杂的数学运算并产生一些非常酷的事情。但这只是开始！

让我们注意一下，我们之前重新赋值的方法并不一定是最好的方法。也就是说，语句`dogage = dogage + 1`可以很容易地缩短，并使其更易于阅读和理解。Python 中有几种不同的赋值赋值运算符。它们如下：

```python
C += d

# 这仅仅意味着 c = c + d.

C -= d

# 这仅仅意味着 c = c - d.

C *= d

# 这意味着 c = c * d.

C /= d

# 这意味着 c = c / d.

C %= d

# 这意味着 c = c % d.
```

## 注释

注释对于编程来说至关重要，除非你想在自己的代码中迷失。在与团队工作时，这一点尤为重要。注释是代码的一部分，从计算机的角度来看，它们完全没有任何作用。那么，为什么它们很重要呢？注释之所以，是因为你可以在代码中插入文本，而不会影响程序本身。你可以利用这些注释告诉你的同事不要碰代码的某部分，因为在你尝试修复代码的另一部分时，那里只是一个权宜之计。对于我们的目的来说，你可以将其作为自己的指南，这样你就知道代码的哪个部分负责什么以及是如何实现的。

## 格式化

如果你曾经用其他语言编写过程序，那么你现在应该注意到，Python 在很多方面都非常不同。其中最不相同的之一就是 Python 处理格式的方式。许多流行语言对空格的态度是模糊的；分号分隔语句，如果你真的想做，甚至可以把整个程序放在同一行。在像`c`和`java`这样的语言中，甚至有人通过比赛来混淆代码，并尽可能使其漂亮，但是以牺牲可读性为代价的。另一方面，Python 非常重视空格。Python 中的空白——即换行符、空格和制表符——向 Python 表明代码的层次结构。这是 Python 真正开始理解你代码的主要引擎，因此你需要密切关注你的空格。确保你的缩进和我的一一样，并注意缩进实际上如何影响代码的流程，以及代码的整体运行方式。

## 用户输入和类型转换

在这里，我们将花几分钟时间讨论获取用户输入。在很多时候，你需要从用户那里获取信息。例如，你可能会要求用户提供文件名或程序所需的某些数据。如果你正在编写类似库或记账程序，这甚至可能是像书名这样无害的内容。无论如何，程序的繁荣不仅是因为它们的存在，更是在于它们与用户交互以及让事情发生的能力。

正因如此，你必须理解 Python 中的用户输入是如何工作的。它相对简单。

Python 中的所有用户输入——至少使用控制台——都是通过`input`方法处理的。`input`方法允许你从控制台获取信息。它会读取直到按下回车键的所有内容，并将这些信息作为字符串返回。

`input`方法的工作方式如下：

```python
Input("prompt text")
```

你可以将`prompt text`设置为任何想要的内容，或者完全省略它。所有`prompt text`仅表示，作为参数传递给`input`方法的文本将显示给相关用户。

你可以将`input`方法赋值给变量，这会将用户输入的任何内容都设置为该变量的值。例如，如果我的文本如下：

```python
Food = input("what is the last thing you ate?")
```

如果用户输入了 nachos，那么`food`的值就是`nachos`。因此，如果我们打印变量`food`，它将打印为 nachos：

```python
Print(food)

# would print as nachos
```

但是，有时这并不是终点。假设你正在写一个计算器程序，你需要接受用户输入的数字。当然，`input`方法返回的是字符串。从我们之前讨论过数据类型如何工作，你知道字符串并不是我们目前需要的数据类型；不，我们需要一个`float`（浮点数）值或`integer`（整数）值。那么，我们如何将用户输入的任何内容转换为这些值之一呢？

你可以通过类型转换（casting）来实现。类型转换简单是将一种数据类型转换为另一种数据类型。在 Python 中，变量可以持有任何数据类型，所以你实际上只需要将转换后的数据类型设置为旧变量的新值，但你并不想仅仅为了保持代码整洁和成为一名优秀的程序员而这样做。（注：原文此处有重复错误，我将在保留类型转换概念的同时清理逻辑）。

类型转换修正：简单地将转换后的数据类型设置为旧变量的新值。

类型转换示例：

```python
number = float(input("Enter a number: "))
```



## 第 4 章：硬件接口

在本章中，你将学习 GPIO 和接口。理解这些基础知识对于定制电路的形成至关重要。树莓派有 40 个引脚。以下是其中：

| 引脚 | 功能 | 引脚 | 功能 |
| :--- | :--- | :--- | :--- |
| 1 | 3.3V | 19 | GPIO 5 |
| 2 | 5V | 20 | GPIO 6 |
| 3 | GPIO 2 (SCL) | 21 | GPIO 9 |
| 4 | 5V | 22 | GPIO 25 |
| 5 | GPIO 3 | 23 | GPIO 10 (SDA) |
| 6 | GPIO 14 (TXD) | 24 | GPIO 21 |
| 7 | GPIO 17 | 25 | GPIO 11 |
| 8 | Ground | 26 | GPIO 12 |
| 9 | Ground | 27 | GPIO 8 (SCLK) |
| 10 | 5V | 28 | Ground |
| 11 | GPIO 18 | 29 | GPIO 24 |
| 12 | Ground | 30 | Ground |
| 13 | GPIO 23 | 31 | GPIO 6 |
| 14 | Ground | 32 | GPIO 19 (SDA) |
| 15 | 3.3V | 33 | GPIO 13 |
| 16 | Ground | 34 | Ground |
| 17 | GPIO 27 | 35 | GPIO 19 |
| 18 | GPIO 24 | 36 | Ground |
| 19 | 5V | 37 | GPIO 16 |
| 20 | Ground | 38 | Ground |
|  |  | 39 | GPIO 20 |
|  |  | 40 | Ground |

树莓派是一个强大的工具，通过学习如何与它交互，你可以创建各种奇的项目。

![Image00132.jpg](img/Image00132.jpeg)

## 面包板

面包板是你在制作电子原型时使用的基础。在树莓派上尝试之前，请先在面包板上进行尝试。确保买到优质的！

### 分立元件

#### 二极管

二极管是一种半导体元件，它允许电流向一个方向流动，而不能向另一个方向。

##### 发光二极管（leds）

![Image00133.jpg](img/Image00133.jpeg)

LED 的作用与二极管相似，只是当电流按正确的方向流动时它会发光。这些元件具有许多形状、尺寸和颜色。引脚的长度决定了哪一个引脚是正极（阴极），哪个是负极（阳极）。

#### 电容

![Image00134.jpg](img/Image00134.jpeg)

电容器是一种可以存储电能的元件。当它的两个极板之间存在电压差时，它会存储能量。一旦电压差消失，它就会释放存储的能量。

#### 三极管

![Image00135.jpg](img/Image00135.jpeg)

三极管是一种半导体元件，用于放大或开关电流或电信号。

#### 光学耦合器

这些是数字开关设备，允许将一个电路与另一个电路隔离。

#### 按钮和开关

![Image00136.jpg](img/Image00136.jpeg)

这些是非常言而易懂的。这些是你与之交互以让电路执行操作的输入设备。它们的基本功能是开启或关闭电路。根据你的需求，它们有不同的形状和形式。

### 通信协议

为了嵌入式系统和谐工作，它们之间需要通信。这就是数据在嵌入式系统之间传输的方式。设定了特定的标准以确保通信的持续性和连贯性，这些就是通信协议。

存在许多通信协议，如果你先学习以下几个概念，将更好地理解它们之间的区别：

#### 比特率（Bit rate）

比特率描述单位时间内发送的比特数。这通常以 `bits/sec`（比特/秒）描述。

#### 波特率（Baud rate）

比特率描述的是单位时间内发送的符号数，而波特率描述的是单位时间内发送的符号数。每个符号可以是任意数量的比特。这取决于设计。如果符号只有 1 个比特，那么波特率就等于比特率。

#### 并行通信（Parallel communication）

在并行通信中，多个比特同时发送。

#### 串行通信（Serial communication）

在串行通信中，比特逐个发送。

#### 同步串行通信（Synchronous serial communication）

这描述了一种串行通信协议，数据以恒定的速率以稳定、连续流发送。这要求两个嵌入式系统的内部时钟以相同的速率同步，以便接收方以发送方使用的相同间隔接收信号。

#### 异步串行通信（Asynchronous serial communication）

这种形式的串行通信不需要同步的内部时钟。数据流在传输前后分别包含起始和停止信号。当接收方接收到起始信号时，它会为数据流做准备。当它接收到停止信号时，它重置为之前的状态以接收新的数据流。

现在你已经学习了它们之间的基本概念，我们现在可以学习不同的通信协议。

#### `i2c`

`i2c` 是集成电路（integrated circuit）的缩写。它是一种使用两根线的异步串行通信协议：一根用于数据（`sda`），另一根用于时钟（`scl`）。它是一种多主多从的串行总线。它的大多数用途限于将低速外围电路连接到处理器和微控制器。

由于其工作方式，`i2c` 必须通过评估 `scl` 为高电平时 `sda` 上的数据是否变化来验证通过的数据。`sda` 上的数据应仅在 `scl` 为低电平时变化；否则数据无效。`i2c` 支持宽电压范围。`i2c` 是半双的。`i2c` 可以支持高达 100kbps 的串行 8 位数据传输。这是 `scl` 的标准速度。`i2c` 还能支持更高的比特率：400 kbps（快速模式）和 3.4 mbps（高速模式）。`i2c` 主要用于短距离通信。

![Image00137.jpg](img/Image00137.jpeg)

#### `uart`

`uart` 是通用异步收发器（universal asynchronous receiver）的缩写。在该协议中，一根线用于传输，另一根线用于接收。`uart` 使用串行通信类型；因此，比特在单根线上传输。`uart` 支持通过 `rs232` 通信。`uart` 标准波特率包括 110、300、600、1200、4800 和 9600。`uart` 在任何时刻只能支持两个设备之间的通信。因为它是点对点的通信协议。

#### `spi`

`spi` 是串行外设接口（serial peripheral interface）的缩写。它是一种用于短距离通信的串行通信接口协议。它可以与一个主设备和多个从设备工作。`spi` 是一种全双工类型的通信协议。`spi` 协议对消息大小没有限制，使其非常灵活。

### 使用 `arduino` 进行实时接口

如果你不熟悉，`arduino` 是一个强大的微控制器。你可以将其与树莓派配合使用创建一些令人深刻的项目。显然，为了实现这些功能你需要一个 `arduino`。你需要大量的编程知识以及对接口的精通以利用这些功能，而解释这些内容会让这本书比实际需要的还要长，所以请务必对这个主题进行进一步的研究。不过，我会讨论几个关键点。

你可以使用上述讨论的任何通信协议（`i2c`、`uart` 和 `spi`）与 `arduino` 接口。你可以将 `arduino` 配置为 `i2c` 从设备，这意味着你可以将多个 `arduino` 连接到一个树莓派上。直接的 `uart` 连接一次只能支持一个从设备。如果你需要 `arduino` 和 `pi` 之间进行快速、高级的交互，将 `arduino` 配置为 `spi` 从设备将是最佳选择。这是因为 `arduino` 的时钟速度只会限制 `spi` 连接。

![Image00138.jpg](img/Image00138.jpeg)

#### 输入和输出

你可能已经了树莓派板顶部边缘的一排引脚。这些是 `gpio` 引脚。`gpio` 是通用输入输出（general purpose input/output）的缩写。通过软件，你可以指定这些引脚中的每一个是输入还是输出。你可以用它们做很多事情。这两个引脚是 `5v`，另外两个是 `3.3v`。还有几个地引脚，你是无法配置它们的。其余的是通用 `3.3v` 引脚。

## 第 5 章：下载操作系统

在没有下载操作系统之前，你将无法运行树莓派。

你可以在 [www.raspberrypi.org](http://www.raspberrypi.org) 找到你需要的软件。

### `Noobs`

`Noobs` 是一个非常适合树莓派初者的程序。`noobs` 一词代表着“开箱即用的软件”（new out of the box software）。如果你愿意，可以在任何销售树莓产品的零售商处购买预装了 `noobs` 的卡。或者，你可以去树莓派官网从那里下载它……

`Noobs` 易于使用，它预装了 `Raspbian` 操作系统供你选择，也可以从互联网下载一个操作系统到你的电脑上。

`Noobs lite` 使用相同的安装程序，但不需要下载 `Raspbian`。其他所有内容都是一样的。

#### `Raspbian`

这是由基金会创建的官方操作系统，可以使用 `noobs` 安装，你也可以独立安装。

大多数 `Raspbian` 都会预装你需要的软件，这样你就可以进行比在 `noobs` 上更多的教育类编程。`Raspbian` 还会随附安装几种不同的编程语言。

`Raspbian` 操作系统的 zip 文件中包含一个像素镜像，你所有的功能都将归档在其中，但我们以前用来解压这些文件的旧工具将不再支持所有平台。

如果下载的 `raspbian` 文件损坏或无法正常打开，在尝试重新安装之前，尝试使用 `7zip` 或解压工具。

## 第 6 章：项目

### `Librelec` 媒体中心

`Librelec` 是一个多媒体中心，可以将几乎任何电视变成智能电视。你可以用它下载应用、访问硬盘，并在电视上播放来自远程 PC 的电影文件。

你还可以接收网络广播并将其流传输到你的音系统中。此外，如果你有账户，`librelec` 还有一个 `spotify` 应用。这是一个让树莓派在日常生活中变得实用的项目。

### `Homebridge`

智能家居领域一个令人兴奋的项目是 `homebridge` 项目（`homebridge.io`）。这个基于软件的项目实现起来相对容易。通过使用 `homebridge`，即使是非苹果认证的智能家居设备也可以与苹果的 `homekit` 使用，且无需任何额外应用即可控制。

整个过程可以通过树莓派非常轻松地实现。它的实用之处在于软件相对易于安装和控制。这意味着你只需要添加不同制造商的插件，然后就可以通过苹果的 `homekit` 直接控制它们。

下面的图片显示了两个可以直接开关的虚拟灯泡。稍后你可以通过简单的二维码在 `homekit` 中轻松添加此类设备。只需用照片应用扫描代码，你就可以从 iPhone、iPad 甚至你的 Mac 控制该设备。

![Image00139.jpg](img/Image00139.jpeg)

而且整个过程安装非常简单。这将在本手册稍后部分讨论。

### `Magicmirror`

智能家居领域的另一个有趣项目是 `magicmirror` 项目（`magicmirror.builders`）。该软件相对易于安装。你可以用它在镜子上设置一个显示器，并将其挂在家里或公寓里。在镜子里，你可以显示各种信息，如时间和天气。镜子还可以连接到其他智能家居设备。因此，这个项目是一个非常棒的，通过稍微调整就能轻松实现。

### `Pi-hole` 广告拦截器

我们在书中看到的另一个实用项目是 `pi-hole` 项目（`pi-hole.net`）。`pi-hole` 是一个网络级广告过滤器，可以安装在树莓派上。

如果你将路由器的互联网设置重定向到 `pi-hole`，所有的网络流量将通过树莓派进行过滤。从现在起，`pi-hole` 服务器将确保例如每个设备上的大部分广告被过滤掉。我们将在书的后面详细查看它的工作原理。

### `Retropi` 游戏机

这是一个特殊的操作系统，可以在树莓派上模拟并运行旧游戏。这个项目是一个利用闲时间重温经典的好机会。

## 第 7 章：带有 `Python` 和 `Linux` 的树莓派

### 带有 `Linux` 的树莓派

涉及到启动时间至关重要。例如，当你的目标是在按下按钮后五秒内启动你喜欢的节目时。那么，如何开发一个启动速度快且不像其他类型的程序呢？

如果你想启用树莓派的启动，必须访问 SD 卡并向其加载某些文件。你可以通过 GPIO 引脚直接访问硬件。这意味着你的树莓派可以作为一个操作系统运行。

所谓的开发系统究竟是什么？它们通常是为特定目的创建的。例如，在操作系统发明之前，并不是所有系统都是可用的。现在，开发系统对于特殊应用仍然可用。

此外，由于其优势，开发编程对于你的空闲时间来说是理想的。想想你自己的电脑，按下电源键后启动需要多长时间？

大部分的启动时间受你所用操作系统复杂性的影响。此外，当你使用操作系统环境时，它会花费大量工作来运行若干个后台进程。

通过开发系统，你可以从性能限制中解脱出来。你去掉了操作系统并直接从硬盘运行程序。这让设备能够利用硬件性能在短时间内完成启动。

这可能看起来非常有吸引力。你甚至会奇怪为什么不是所有程序都以此方式运行。便利性是一个关键因素。也应该考虑系统的需求。这就是为什么在微软和苹果进入市场之前，很多电脑并没有出名。

图形界面的开发使用户能够相对轻松地使用计算机。操作系统虽然消耗性能且加载缓慢，但它是有用且方便的。事实上，许多人（包括开发者们）都对其优势感到惊讶。

此外，使用操作系统的计算机通常是多用途设备。许多人必须进行电子表格、文字处理、数学计算和网页浏览等活动。他们需要一种能够让他们仅用一台机器完成所有这些任务。

这种多样性需要一个更复杂的系统，利用各种硬件来实现各种用途。另一方面，嵌入式系统倾向于专注于处理单一设备，其功能范围较窄。

## 如何编写嵌入式系统

相反，你必须使用计算机能够理解的东西。你需要使用一种对它们来说听起来母语的语言进行通信。

你需要将你的汇编编译到 `raspberry pi` 会读取的内核中，而不是常用的 `raspbian` 内核。为了实现这一点，你必须从 `raspberry pi` 的 `sd card` 中删除所有数据。你需要一个来加载内核。请务必始终保留数据的备份。

内核通常充当软件与硬件之间的桥梁。`raspbian` 内核让用户更容易从显示器或键盘获取数据并对其进行处理。

然而，在嵌入式系统中，你不需要与大多数硬件进行通信。也不需要图形用户界面（`gui`）。你可以在不使用它的情况下操作。

嵌入式设计通常是针对特定目的进行编程的。例如，你可能想让几个 `led` 闪烁。因此，你需要一个对启动时间敏感的系统，因为你必须移除任何为了让 `led` 闪烁不需要的内容。

### `Linux` 使用

#### 命令

它们指的是在 `linux` 中使用的高级和基础命令。

#### 文本编辑器

这些指的是一组用于 `raspberry pi` 的文本编辑器。

#### Root（根）

前缀 `sudo` 和用户 `root`。

#### 用户

允许在 `raspberry pi` 系统上设置多个用户。

#### 脚本

它指的是组合命令来执行复杂的操作。

#### `Crontab/cron`

它设置了预定的任务。

#### `.bash` 和 `.bashrc` 别名

它们是你的别名和 shell 配置。

#### `Rc.local`

指的是初始化配置。

## 给初学者的额外帮助

以下是 `Linux` 一些基本用法的解释，以及在 `raspberry pi` 上进行操作的命令。

### `Linux` 文件系统

这是存放文件、安装软件以及看到危险区域的地方。它包含了 home、整个文件系统和备份。

#### Home

这是存放文件的地方。它是主目录。

#### 整个文件系统

它指的是 `Linux` 文件系统的其余部分。

#### 备份

它备份文件以及操作系统镜像。

### `Raspberry pi` 和 `Python`

`Python` 语言呈现出一种高级语法；我们之所以说这样是因为它的编写形式非常接近人类语言。此外，`Python` 支持面向对象。

从根本上说，`Python` 要求精确地编写代码。尽管如此，它还提供了一个友好的界面，应用程序本身会引导你编写代码（在代码中标记错误并提供实用的建议）。

这个专门为 `Python` 设计的集成开发环境有两种模式：普通模式和简单模式（模式）。简单模式让事情对初学者变得简单，在这份指南中，我们将参考这种的简单模式。这是你在应用程序简单模式下看到的工具栏。在工具栏上每个友好的图标下方，你会看到它们的用途。这是应用程序的脚本。其目的与 `scratch` 应用程序完全相似。我们在其中编写代码，左侧指示了行号。随着你不断编写代码，它会自动进行索引。在你的代码遇到错误的情况下，你将知道错误指的是哪一行代码，因为每一行都经过了索引，你可以快速导航到错误的代码行并修复它。这种索引可以非常有用且节省时间。这是 shell。它提供了关于应用程序当前运行代码的信息，你可以输入单行代码并按回车键执行它们。这是变量。它显示了你为特定程序创建的所有变量的信息（名称和值）。

## 使用 `Python` 编程：制作程序

启动 `Python` 后，你注意到的第一点是，与 `scratch` 不同，这里没有彩色的块。这是因为 `Python` 更多像是一种传统的语言，依赖于手动编写代码（当然，不能有写写错误或故障！）。

从 `raspberry pi` 菜单打开 `Python` 并等待 `thny ide` 加载（`thonny` 将默认以简单模式启动）。转到 `python shell` 并输入：

```python
Print("good morning!")
```

在输入以下指令后，你只需要按回车键，你就会在指令下方看到显示出的“good morning”消息。我们刚刚创建了第一个程序。它就是这么简单！

一旦你击回回车，代码就会执行。另一方面，当你写完一行代码后按回车键而不是执行该行代码时，你只是得到了一个新的空白行来编写更多代码。要执行脚本中的代码，你需要点击工具栏上的 `run` 图标来执行（当你点击运行按钮时，`thonny` 会提示你先保存当前程序，只需为程序命名并点击保存）。注意，当你从脚本运行已保存的程序时，这次 shell 中的消息有点不同：

```python
>>> %run 'name you used to save the program.py.'

Good morning!
```



你也可以在脚本中编写相同的代码，但这次我们将使用一个不同的、更流行的短语，`"hello world!"`，并在保存时将其命名为`hello world.py`。

（这是你在 shell 中看到的消息）

```python
>>> %run 'hello world.py'

Hello, world!
```

第一行指示器执行刚刚保存的程序，第二行是运行该程序的结果或输出，在我们的案例中显示了一条消息。我们成功地在 Python 中编写了第一个程序并在交互和脚本模式下运行了它。

## 使用循环和代码，缩进

缩进基本上是 Python 控制代码执行顺序的方式。在 scratch 编程中，我们会使用彩色的块并按照我们想要的顺序将它们堆在一起，但在 Python 中，我们需要使用缩进来告诉计算机这些代码的运行顺序。

点击工具栏上的`new`图标打开新项目。这会为你打开一个独立的新窗口进行工作。在脚本中输入以下代码行：

```python
Print("loop starting!")

For i in range (10):
```

在上面的代码行中，第一行的工作原理与`print("good morning")`示例所示的完全相同。然而，第二行非常有趣。这一行启动了一个确定性循环序列，定义的限制由`range`后面跟随的整数设置。`i`是循环计数器，它将计算程序循环的次数；在这种情况下，它将一直向上计数到 9，因为停止指令是数字 10；一旦完成第 9 次循环，循环就会退出。此外，注意行末尾的冒号`:`。它告诉计算机，接下来的几行代码实际上是循环的一部分。

此外，在 scratch 中，我们看到要添加到循环函数中的指令可以直接放置在循环块上。但在 python 中，我们通过冒号（`:`）对指令代码进行缩进。缩进的特征是在新行开头左留四个空格；当你在缩进缩进后按下回车键时，ide 应用程序会自动完成这一操作。

```python
Print("loop starting!")

For i in range (10):

    Print("loop number", i)
```

正是这种缩进让 python 能够区分不包含在循环中的指令和要包含在循环中的指令（这种缩进代码被称为嵌套）。

此缩进之后的所有行都将自动包含四个空格，因为它假设接下来的代码也将也是循环的一部分。这将一直持续，直到你写完所有属于循环的指令。若要结束缩进，只需创建一个新的缩进空行并按退格键，这会将该行恢复为正常状态。现在，按照描述结束缩进并编写以下代码行：

```python
Print("loop finished!")
```

代码行的顺序应该如下：

```python
Print("loop starting!")

For i in range (10):

    Print("loop number", i)

Print("loop finished!")
```

在这个程序中，第一行和最后一行都在循环之外，因为它们没有缩进。第二行是循环开始的地方，并且包含了缩进，这使得第三行成为了了循环的一部分。

让我们将此程序保存为`indentation`并运行它。在 shell 区域，我们将看到以下输出：

```text
Loop starting!

Loop number 0

Loop number 1

Loop number 2

Loop number 3

Loop number 4

Loop number 5

Loop number 6

Loop number 7

Loop number 8

Loop number 9

Loop finished!
```

python 从零开始计数而不是从一开始的原因是，python 被设计为一种零索引语言。这意味着它将 0 视为起始整数而不是 1。你可以通过指定`range`指令为`range(1, 11)`而不是`range(10)`来改变这种行为。通过这样，循环将从 1 开始计数到 10。你可以对任何你数字这样做。

就像我们在 scratch 中使用确定性循环和无限循环一样，在 python 中也可以这样做。要使用无限循环（永远运行的循环），你只需要编辑上面程序的第 2 行代码。

```python
Print("loop starting!")

While true:

    Print("loop running!")

Print("loop finished!")
```

你现在创建了一个无限循环。这是因为循环的结束条件没有指定；每当打印`"loop running!"`消息时，程序都会将代码导回开头，整个过程不断重复，直到程序终止。要终止程序，只需点击`stop`图标。程序将终止，而永远无法到达最后一行代码。

## 使用条件和变量

点击`new`图标打开一个新项目，并在脚本中输入以下代码行：

```python
username = input("what is your name?")
```

保存程序并运行它。该程序的输出是显示一条询问你名字的消息。在消息结束后，点击空隙处，输入一个名字并按回车。程序中不会发生任何事情，但如果你将注意力转移到右侧的变量窗口，你将看到`username`被赋值了你刚刚输入的值。

为了演示如何在 python 中使用变量，我们将`username`变量与一个条件配对。在这次演示中，程序将询问我们的名字，并根据我们的答案给出特定的答复：

```python
If username == "clark kent":

    Print("you are superman!")

Else:

    Print("you are not superman!")
```

现在保存并运行程序，注意输出。在第一种情况下，当程序询问我们的名字时，它会将它与变量值`"clark kent"`进行比较以查看是否匹配。如果我们的名字与变量中的名字匹配，则该条件为真（true）；如果不匹配，则该条件为假（false）。根据结果的真或假，条件指示程序执行以下代码行之一。

![Image0140.jpg](img/Image0140.jpeg)

此外，注意我们没有使用单个等号`=`，而是使用了双等号`==`。这是因为单等号是给变量赋值，或者简单来说是让此值等于该变量；而双等号符号则是进行直接比较。一个是赋值运算符，而另一个是比较运算符。

此外，引号中的文本被称为字符串（string）。带有或不带引号的数字被称为整数（integer）。当你组合两个不同类型的信息时，例如将文本`"how old are you?"`与回复 22 组合，你必须将整数转换为字符串才能进行组合。

在处理数字时，你还可以使用大于`>`和小于`<`比较运算符。但要使用等号运算符，你必须使用`==`。同样，大于等于`>=`和小于等于`<=`也可以使用。我们现在将在之前使用的循环示例中使用一些比较运算符：

```python
While username != "clark kent":

    Print("you are not superman – try again!")

    username = input("what is your name,")

Print("you are superman!")
```

在运行此程序后，你会发现当你告诉你不是超人后，程序并没有退出，而是会一直询问你的名字，直到确认你确实是超人。

## 第 8 章：树莓派型号

### Model a/b

第一代树莓派型号被称为 model a 和 model b（如上图所示）。这两种型号内部都集成了博通`bcm2835 soc`，但规格不同：例如，model a 具有 256 mb 内存、一个 USB 端口且没有任何网络功能；而 model b 根据购买日期，具有 256 mb 或 512 mb 内存、一个 10/100 有线网络端口和两个 USB 端口。

这些型号之所以易于区分，是因为它们的 GPIO 端口比通常的要，只有 26 个引脚，而较大、更先进的型号有 40 个引脚。这两个型号都拥有全尺寸 SD 卡存储空间，而不是较新型号标配的紧凑 microSD 卡。尽管它们已不再生产，但`model a`和`model b`仍然兼容大多数为新机型设计的软件，只是它们不使用基于 hat 标准的扩展硬件。

### Model a+/b+

原始型号被证明非常受欢迎，但很快被一种名为 plus 的新板子设计所取代。这些后来的迭代版本带有 40 引脚 GPIO 插针，同时改进了其他一些功能。然而，它们并没有偏离`bcm 2835 soc`，这意味着 plus 型号与旧型号之间的性能没有太大区别。

`model a+`和`model b+`之间的硬件差异与之前的`model a`和`model b`相似：`a+`型的占用空间比`a`型小，根据产品发布时的零网络能力，它具有 256 mb 或 512 mb 的内存，并且只有一个 usb 端口；`model b+`则具有 512 mb 内存、一个 10/100 有线网络端口和四个 usb 端口。

`A+`和`b+`与本指南中提到的每种软件和设备都非常兼容，并且与如今较新的型号具有相同的 gpio 布局。如果你拥有其中任何一个型号，升级的唯一理由是为了获得额外的内存、享受内置的无线功能或提高性能。

### Raspberry pi 2

虽然 plus 以及之前的其他板子使用相同的`bcm 2835 soc processor`，但新的 raspberry pi 2 使用了新的`bcm 2836 soc processor`。与原始版本的单核不同，新处理器具有四个以上的内核，性能是原始型号的 4 到 8 倍——这使得从文字处理到编译代码的每一个过程都变得快得多。这个新版本还包含超过 1gb (1024 mb) 的内存，是前一个的两倍，这使得内存密集型应用程序和多任务处理运行更加流畅，响应也更快。

在布局方面，与`model b`相比没有太大变化。例如，raspberry pi 2 具有相同的四个 usb 端口、40 引脚 gpio 插针、10/100 有线网络端口以及其他端口。如果你确实有一个与`model b`兼容的扩展设备或外壳，它在 raspberry pi 2 上也能运行良好——只是速度更快。

新板子比之前的版本具有更大的软件兼容性：即使是专有的操作系统`raspbian`也可以运行如 windows 10 iot core 和 ubuntu 等操作系统，而这些在之前的代代中是不提供的。

### Raspberry pi 3

在第四代迭代之前的最后一个型号 raspberry pi 3，在发布时配备了全新的处理器：broadcom`bcm 2837`。由于是 64 位处理器而非 32 位，新处理器的速度比 raspberry pi 2 中的`bcm 2836`快得多，而后者在当时对于原始和系列中的`bcm 2835`来说是一次巨大的升级。raspberry pi 3 还是第一个内置无线支持的型号，包括一个连接到 2.4 ghz wi-网络和蓝牙设备的无线电器。

像 pi 2 一样，布局没有太大变化：你将获得与最后几个型号相同的四个 usb 端口、40 引脚 gpio 插针、10/100 有线网络端口以及其他端口。唯一的细微变化在于板子与特定扩展设备交互的方式，所以如果你不确定某个设备是否兼容 pi 3，你应该在购买前联系供应商，以确保软件已考虑在内。

新 pi 3 的一个大优势除了内置功能和当然还有改进的性能外，是它的 64 位处理器。切换到这个型号意味着你将比之前型号的 32 位具有更好的软件兼容性和安全性。

### Raspberry zero

raspberry zero 到目前不仅是整个树莓派家族中最小的板子，也是最便宜的。尽管尺寸只有几块叠在一起的口香糖大小，但 raspberry zero 几乎并不缺少其他型号具备的特性：它具有相同的`bcm 2835 soc`以及与 raspberry model b+ 一样的 512 mb 内存，并且运行速度略快以获得更好的性能。

然而，pi zero 在时需要某些限制。例如，mini-hdmi 端口和单个 micro-usb 端口在连接到标准外围设备之前需要适配器；没有 dsi 端口；3.5 mm av 接口消失了，需要适配器；虽然有 gpio 插针，但引脚需要额外购买并焊接到位置才能使用。

如果你是初学者，我们不推荐 pi zero。但如果你是经验丰富的用户并希望为嵌入式项目带来更多智能——特别是当你在成本、功耗和尺寸上遇到麻烦时——pi zero 就是你需要的那个板子。

### Raspberry pi 4 model b

现在，我们将研究最新的 raspberry pi 4 model b，看看它是由什么制成的以及你如何让它工作。尽管这块小板子上似乎有很多东西，但我们向你保证树莓派板子非常容易理解——尤其是它的组件。

有一个由黑色塑料封装芯片表示的 USB 控制器，它位于板底边缘，紧邻中间一组 USB 端口后方。该组件负责运行所有的四个 USB 端口。还有一个更小的网络控制器芯片，处理电路板的以太网网络端口。最后，是一个最小的黑色芯片，位于板左上角的 USB Type-C 电源接口稍上方的位置，这被称为电源管理集成电路（`pmic`）。该芯片负责将 micro USB 端口的电转换为树莓派运行所需的电。

## 结语

感谢阅读本书。下一步就是利用你在书中所学到的知识，开始使用树莓派进行编程了。你将能够创建许多项目，让你的生活变得更加舒适便利。

树莓派确实是一项技术奇迹，这台微型机器所能做到的一切将始终让你感到惊讶。这个“小怪兽”不仅在性能和能力方面表现出色，而且树莓派在对各种可能应用的适应性方面也是独一无帜的。

正如树莓派的实用性没有限制，也没有定义的边界，我们在本入门级书籍中能学的知识是有限的。关于树莓派及其功能，以及我们如何充分利用它的能力，仍有整座岛屿般的知识等待探索。然而，本书已经涵盖了所有核心概念的基础形式，使读者在想要将树莓派作为口袋电脑或项目组件使用时，能够应对遇到的任何问题。

在处理任何万事时请保持谦虚。不要害怕承认自己错了，或者承认自己并没有你预想的那么能力，并在社区中寻求帮助。树莓派绝对是目前最酷的技术产品之一，它可以做很多事情。尽管如此，它对程序员来说也可能是令令人沮丧的，因为它的能力完全取决于程序员让它做到什么程度。

树莓派确实是一个奇妙的设备。它小巧手手，你可以随身携带。它价格低廉且易于获得，你可以轻松在不超出预算的情况下购买几十个。对于你的项目来说，树莓派设备越多越好。

如果你想精进技能、释放创造力并创造出有用且独特的东西，你就应该继续努力和实践。记住，你还可以从其他树莓派用户那里获得提示和建议，并分享你的想法。你甚至可以从在线社区建立友谊。

树莓派的廉价和普及可以帮助你同时进行多个项目。如果你犯了错，可以重新尝试。你甚至可以对作品申请专利并出售。从简单的设备开始，你可以开发出让全世界受益的工具。机会是无限的，在树莓派的帮助下，你可以实现你的梦想。

与其看电视、刷社交媒体或无目的地上网来消磨时间，不如变得高效起来，使用树莓派实验项目。

树莓派确实是当今最伟发明之一。凭借如此微小的设备，可以成就伟业。

顶尖程序员不会在途中放弃。加油实践吧，将你在书中学到的所有想法概念化。记住，学习（包括树莓派在内）的准则是：实践；毫无疑问：熟能生巧。

祝你好运！
