
# Python 核心速查表

# Java Geeks CHEATSETS

# 2

## 序言

本指南旨在作为 Python 编程的快速参考，涵盖了常用的语法和功能，包括数据类型、控制结构、函数和库。无论你是 Python 初学者，还是想要快速复习的资深程序员，本指南都能为你提供帮助。

## 模块与包

## 数据操纵与分析

### NumPy

NumPy 是用于科学计算的强大包。它提供了对多维数组和矩阵的支持，以及用于处理数据的数学函数。NumPy 是 Python 科学计算的基础包，在数据科学和机器学习领域被广泛使用。

### Pandas

Pandas 是用于数据处理和分析的库。它提供了高效存储和查询数据的结构，以及用于转换数据的一系列函数。Pandas 是数据科学家和分析师使用的关键工具。

### 引言

Python 是一种高级解释型语言，以其简单、易读和多功能著称。它由 Guido van Rossum 于 1991 年发布，已成为全球最流行的语言之一。

Python 的语法强调可读性，使用空白和缩进来定义代码块。它是一种解释型语言，这意味着代码是逐行执行的，而不是编译成机器码。这使得编写和测试代码变得非常简单，无需担心底层硬件细节。

### SciPy

SciPy 是一个用于科学和技术计算的 Python 库。它提供了一系列数学算法和函数，用于优化、积分、插值、信号处理、线性代数等任务。

Python 是一种通用语言，意味着它可以用于各种应用程序，从 Web 开发到科学计算，再到人工智能和机器学习。它的简单易用使其成为初学者的首选，而其强大和灵活性也深受资深开发者的喜爱。

## 数据可视化

### Matplotlib

Matplotlib 是 Python 的绘图库。它提供了一系列用于创建高质量数据可视化的函数，包括折图、散点图、直方图等。Matplotlib 在科学计算、数据可视化和机器学习中被广泛使用。

### Seaborn

Seaborn 是一个 Python 数据可视化库，构建在流行的可视化库 Matplotlib 之上。它提供了一个高层接口，用于创建美观且丰富的统计图表。Seaborn 设计用于处理 Pandas DataFrame 中的数据，并提供了可视化变量间关系的各种工具。

## 机器学习

### Arcade

Arcade 是一个用于创建 2D 机风格游戏的 Python 库。它基于 Pygame 库构建，为构建具有现代图形和音效的游戏提供了一个易于使用的框架。它支持跨平台（可在 Windows、Mac 和 Linux 上运行）、支持 2D 和 3D 图形，并且拥有活跃的开发者社区，他们不断创建新游戏并使用该库。

### Scikit-learn

Scikit-learn 是 Python 中的一个机器学习库。它提供了用于分类、回归、聚类和降维的一系列函数，并带有用于模型选择和评估的工具。Scikit-learn 是 Python 中构建和部署机器学习模型的流行选择。

### TensorFlow

TensorFlow 是一个用于构建和训练机器学习模型的库，特别是对构建和训练神经网络提供了深度支持，并带有一系列用于模型评估和部署的工具。TensorFlow 在机器学习和数据科学社区被广泛使用。

## 安装新包

### 使用 `pip`

`pip` 是 Python 的包安装器。你可以通过在终端或命令提示符中运行以下命令来安装新库：

```bash
pip install library-name
```

将 `<library-name>` 替换为你想要安装的库名。例如，要安装 numpy 库，运行：

```bash
pip install numpy
```

### 使用 Anaconda

如果你使用 Anaconda 作为 Python 分发版，可以使用 Anaconda Navigator 或命令行界面安装新库。例如，要安装 numpy 库，运行：

```bash
conda install numpy
```

## Web 开发

### Flask

Flask 是一个 Python 的微 Web 框架。它提供了构建 Web 应用的工具，包括路由、模板和请求处理。Flask 是一个轻量且灵活的框架，广泛用于构建 Python Web 应用和 API。

### Django

Django 是一个 Python 的高级 Web 框架，遵循模型-视图-控制器（MVC）架构模式。它提供了一套强大的工具用于构建 Web 应用，包括一个强大的对象关系映射（ORM）系统、模板引擎以及处理用户验证和授权的内置支持。

## 游戏开发

### 手动

你可以从其网站或 GitHub 仓库下载库的源代码，并按照库提供的安装说明手动安装。

### Pygame

Pygame 是一组用于创建视频游戏和多媒体应用的 Python 模块。它提供了对图形、声音、输入和网络的支持，使得创建游戏和交互应用程序变得简单。

一旦安装了新库，你可以使用 `import` 语句将其导入到 Python 代码中。例如，要导入 numpy 库，你可以使用：

```python
import numpy
```

或者可以使用库名使用别名以进行更短的引用：

```python
import numpy as np
```

# 数据类型和变量

Python 是一种动态类型语言。这意味着变量的数据类型是在运行时根据赋值给它的值决定的。换句话说，在声明变量时不需要指定数据类型，并且可以将不同数据类型的值赋值给同一个变量。

```python
x = 5          # x 是整数
x = "hello"    # x 现在是字符串
x = 3.14       # x 现在是浮点数
```

- 整数（Integers）：不带小数点的整数。例如 `1`、`2`、`3`、`4`、`5`
- 浮点数（Floats）：带有小数点的数字。例如 `3.14`、`4`、`5`、`6`、`0`
- 字符串（Strings）：字符序列。例如 `"hello"`、`'world'`
- 布尔值（Booleans）：存储值的容器。例如 `x = 10`、`y = "hello"`

## 字符串

字符串是用单引号 `' '` 或双引号 `" "` 包围的字符序列。它是 Python 中的基本数据类型之一，用于表示文本和其他可以表示为字符序列的其他类型的数据。

以下是一些可以在字符串上执行的基本操作：

```python
# 创建字符串
my_string = "hello world"

# 获取字符串的长度
len = len(my_string)  # 输出: 11

# 访问单个字符
first_char = my_string[0]   # 输出: "h"
last_char = my_string[-1]   # 输出: "d"

# 字符串切片
substring = my_string[0:5]  # 输出: "hello",

# 连接字符串
new_string = my_string + "!"  # 输出: "hello world!",

# 重复字符串
repeat_string = my_string * 3  # 输出: "hello world hello world hello world"
```

Python 中的字符串是不可变的，这意味着当你创建一个字符串时，不能更改它的内容。但是，你可以创建一个包含修改后内容的新字符串。

字符串格式化是 Python 中的另一个重要功能，允许你将值插入到特定的格式中。

```python
name = "Alice"
age = 30
greeting = "My name is {} and I am {} years old.".format(name, age)
print(greeting)  # 输出: My name is Alice and I am 30 years old
```

## 运算符

- 算术运算符：`+`、`-`、`/`、（模）、`%`（幂）
- 比较运算符：`==`（等于）、`!=`（不等于）、`>`、`<=`、`>=`、`!=`
- 逻辑运算符：`and`、`or`、`not`

## 序列解包

序列解包是 Python 中的一个功能，允许你将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

。序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许将序列（如元组或列表）的元素赋值给变量。

序列解包 允许。

```python
def function_name(parameters):
    return value
```

## 函数调用

```python
result = function_name(argument1, argument2, ...)
```

### 可选参数

```python
result = def function_name(parameter1, parameter2=default_value, ...):
    # function body
    return value
```

### 可变参数

```python
def function_name(*args):
    # function body
    return value
```

### 关键字参数

```python
def function_name(parameter1, parameter2, ..., keyword1=value1, keyword2=value2, ...):
    # function body
    return value
```

### 默认参数值

```python
def function_name(parameter1, parameter2=default_value):
    # function body
    return value
```

### 匿名函数（Lambda 函数）

```python
lambda arguments: expression
```

## 变量作用域

```python
# 全局变量
variable_name = value

def function_name():
    # 局部变量
    variable_name = value
```

## 列表

有序的项集合。

```python
my_list = [item1, item2, item3]
```

### 列表方法

```python
my_list.append(item)  # 将项添加到列表末尾
my_list.insert(index, item)  # 在指定索引插入项
my_list.pop()  # 删除并返回
```

列表中的最后一项。

`my_list.remove(item)` 移除项的第一次出现。

返回一个新集合，其中包含两个集合共有的项。

## 字典

键值对的无序集合。

```python
my_dict = {"key1": value1, "key2": value2, "key3": value3}
```

### 输入

允许用户向程序输入数据。

```python
input_string = input("Enter a value:")
```

### 字典方法

```python
my_dict.keys()  # 返回键的列表
my_dict.values()  # 返回值的列表
my_dict.items()  # 返回键值对列表的列表
```

### 输出

向用户显示数据。

```python
print("Hello, world!")
```

## 文件处理

### 元组

不可更改（不可变）的项有序集合。

```python
my_tuple = (item1, item2, item3)
```

### 打开文件

```python
file = open("filename.txt", "r")  # 以只读模式打开文件
file = open("filename.txt", "w")  # 以写入模式打开文件
```

### 从文件读取

```python
file_contents = file.read()  # 读取整个文件
file_contents = file.readline()  # 读取文件一行
```

## 集合

唯一项的无序集合。

```python
my_set = {item1, item2, item3}
```

### 集合方法

### 写入文件



```python
my_set.add(item) # 向集合添加一个项
my_set.remove(item) # 从集合中移除一个项
my_set.union(other_set) # 返回包含两个集合所有唯一项的新集合
my_set.intersection(other_set) #
```

```python
file.write("Hello, world!") # 将字符串写入文件
```

### 关闭文件

```python
file.close() # 关闭文件
```

## 异常处理

程序执行期间期间的错误。

```python
try:
    # 可能会抛出异常的代码
except Exception:
    # 发生异常时执行的代码
finally:
    # 无论是否发生异常都会执行的代码
```

```python
person1 = Person("Alice", 25)
person2 = Person("Bob", 30)

person1.say_hello()
person2.say_hello()
```

## `@classmethod` 装饰器

在 Python 中，`@classmethod` 装饰器用于定义类方法。类方法绑定到类，而不是类的实例。它可以在类本身上调用，而不是在类的实例上调用。

```python
class MyClass:
    class_var = "This is a class variable"

    def __init__(self, x):
        self.x = x

    @classmethod
    def class_method(cls):
        print(cls.class_var)

MyClass.class_method()
```

## 类与对象

### 类

在 Python 中，类是创建对象的蓝图。它定义了对象将拥的一组属性和方法。当你创建一个类的实例时，你就创建了一个与类具有相同属性和方法的新对象。

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    def say_hello(self):
        print(f"Hello, my name is {self.name}, and I'm {self.age}, years old.")
```

### 对象

具有特定属性值的类实例。要创建 `Person` 类的实例，我们使用构造方法 `__init__`，它会初始化对象的属性。然后我们调用 `say_hello` 方法来打印问候信息。要定义一个类方法，我们在方法定义之前使用 `@classmethod` 装饰器。类方法的第一个参数总是 `cls`，它引用类。你可以使用 `cls` 来访问类变量和方法。

### 继承

类也可以继承其他类的属性和方法。

```python
class Student(Person):
    def __init__(self, name, age, grade):
        super().__init__(name, age)
        self.grade = grade

    def say_hello(self):
        print(f"Hello, my name is {self.name}, I am {self.age} years old")
```

### 魔术方法

Python 还支持许多特殊方法，被称为“魔法方法”或“dunder 方法”（双下划线方法），它们允许你自定义类的行为。这些方法以双下划线开头和结尾。

- `__init__(self, ..)` 初始化类的新实例
- `str__(self)` 定义对象的字符串表示
- `__repr__(self)` 定义对象的官方字符串表示
- `__eq__(self, other)` 使用 `==` 运算符比较两个对象的相等性
- `__lt__(self, other)` 使用 `<` 运算符比较两个对象是否小于另一个
- `__len__(self)` 定义对象的 `len()` 函数行为
- `__getitem__(self, key)` 使用方括号 `[]` 访问对象
- `__setitem__(self, key, value)` 使用方括号 `[]` 修改对象
- `__delitem__(self, key)` 使用 `del` 关键字删除对象
- `__getattr__(self, name)` 访问对象的属性
- `__setattr__(self, name, value)` 在对象上设置属性
- `__delattr__(self, name)` 从对象中删除属性
- `__call__(self, ..)` 允许对象像函数一样被调用

## 注释与文档字符串

注释和文档字符串（docstrings）是 Python 中记录代码的两种重要方式。注释用于对特定行或块提供解释，而文档字符串用于为函数、类和模块提供说明。

### 注释

Python 中的注释以 `#` 符号开头，用于对特定代码行提供解释：

```python
#### 这是注释
x = 1 # 这是另一个注释
```

在这个示例中，我们使用注释来解释代码的作用。Python 解释器会忽略注释，不会执行它们。

### 文档字符串

文档字符串用于记录函数、类和模块。它们包含在三引号 `"""` 中，并应该描述函数的功能、参数以及返回值：

```python
def add_numbers(a, b):
    """
    此函数相两个数字并返回结果。
    参数:
    a (int): 第一个数字
    b (int): 要加的第二个数字。
    返回:
    int: a 和 b 的和。
    """
    return a + b
```

在这个示例中，我们定义了一个名为 `add_numbers` 的函数，并提供了描述该函数功能、参数和返回值的文档字符串。文档字符串应该放在函数定义之后。

## 核心 Python

文档字符串很重要，因为它们让其他程序员（以及未来的你自己）更容易理解代码的功能以及如何使用它。可以使用 `help()` 函数或使用内置的 `__doc__` 属性来访问。

```python
my_list = [x**2 for x in range(5)]
#### 创建0-4数字的平方列表
```

```python
even_numbers = [x for x in my_list
if x % 2 == 0] # 从 my_list 创建偶数列表
```

## 模块与包

### 模块

包含 Python 代码的文件，可以在其他程序中导入使用。

```python
import my_module

my_module.my_function() # 调用模块中的函数
```

### 生成器

使用 `yield` 关键字一次返回值，而不是一次性返回所有值。

```python
def my_generator():
  yield 1
  yield 2
  yield 3
```

```python
for value in my_generator():
  # 执行生成器返回的每个值
```

### 包

可以一起导入的相关模块集合。

### 装饰器

```python
import my_package.my_module
```

```python
my_package.my_module.my_function()
#### 调用包中模块的函数
```

修改其他函数行为的函数。

### Lambda 函数

```python
def my_decorator(func):
  def wrapper(*args, **kwargs):
    # 在原函数之前执行的代码
    result = func(*args,
    **kwargs) # 调用原函数
    # 在原函数之后执行的代码
    return result
  return wrapper

@my_decorator
def my_function():
  # 执行的代码
```

可以在单行代码中定义的匿名函数。

```python
my_lambda = lambda x: x**2 # 定义一个对输入平方的 lambda 函数
```

```python
result = my_lambda(3) # 使用输入3调用 lambda 函数
```

### 列表推导式

基于其他列表或序列创建列表的简洁语法。

### MAP, FILTER, AND REDUCE

### 字符串格式化

### MAP

允许以特定格式将值插入到字符串中。

将函数应用于序列中的每个元素，并返回一个包含结果的新序列。

```python
def square(x):
    return x**2

name = "Alice"
age = 30
greeting = "Hello, my name is {} and I am {} years old.".format(name, age) # 创建一个使用大括号插入值的字符串
```

```python
def square(x):
    return x**2

my_list = [1, 2, 3, 4]
squared_list = map(square, my_list)
#### 创建一个包含原始值平方值的新列表
```

### 正则表达式

#### FILTER

正则表达式（也称为 regex 或 regexp）是一系列定义搜索模式的字符序列。它们是 Python 等编程语言中用于文本处理和数据提取的强大工具。在 Python 中，`re` 模块提供了对正则表达式的支持。

将函数应用于序列中的每个元素，并返回一个仅包含通过特定测试元素的新序列。

```python
def is_even(x):
    return x % 2 == 0

my_list = [1, 2, 3, 4]
even_list = filter(is_even, my_list)
#### 创建一个包含原始列表中偶数值的新列表
```

#### FUNCTIONS

- `re.search(pattern, string)`: 在字符串中搜索模式的首次出现，并返回找到的匹配对象。如果没有找到，返回 None。
- `re.findall(pattern, string)`: 在字符串中搜索模式的所有出现，并返回包含所有找到匹配项的列表。
- `re.sub(pattern, repl, string)`: 在字符串中搜索模式的所有出现，并将其替换为 `repl` 字符串。

将函数应用于序列中的元素对，并返回单个结果。

```python
from functools import reduce

def my_function(x, y):
    return x + y

my_list = [1, 2, 3, 4]
result = reduce(my_function, my_list)
#### 相加列表中的所有值以得到单个结果
```

#### 元字符

- `.` (点): 匹配除换行符以外的任何字符。
- `^` (脱帽): 匹配字符串的开头。
- `$` (美元符号): 匹配字符串的结尾。
- `*` (星号): 匹配前一个字符零次或多次。
- `+` (加号): 匹配前一个字符的一次或多次。
- `?` (问号): 匹配前一个字符的零次或一次。

## Java Code Geeks 快速查表

## 12

## 核心 Python

- `[]` (方括号): 匹配括号内的任意一个字符。
- `|` (管道符): 匹配管道符之前或之后的表达式。

```python
import re

#### 在字符串中搜索模式
text = "The quick brown fox jumps over the lazy dog"
match = re.search(r"brown", text)
if match:
    print("Match found!")

#### 在字符串中查找模式的所有出现项
text = "The quick brown fox jumps over the lazy dog"
matches = re.findall(r"the", text, re.IGNORECASE)
print(matches)

#### 替换字符串中模式的所有出现项
text = "The quick brown fox jumps over the lazy dog"
new_text = re.sub(r"the", "that", text, flags=re.IGNORECASE)
print(new_text)
```

JCG 每月向 70 万软件开发者、架构师和决策者提供超过 100 万页内容。JCG 为所有人提供内容，包括新闻、教程、快速查表、研究指南、专题文章、源代码等。

Copyright 2014 Exelius Media P.C. 版权所有。未经出版者事先书面许可，本出版物的任何部分不得通过电子、机械、微缩或复印的方式以任何形式或媒体进行复制、存储在检索系统中或传输。

快速查表反馈

欢迎反馈

`support@javacodegeeks.com`

赞助合作

商业机会

`sales@javacodegeeks.com`

JAVACODEGEEKS.COM | © ELIXEL MEDIA P.C. 访问 JAVACODEGEEKS.COM 获取更多内容！
