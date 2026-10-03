

# Python 编程最佳实践

![](img/cover0008.jpeg)

## 引言

我想感谢并祝贺你阅读《Python：Python 编程最佳实践》一书。本书包含了如何更有效地进行 Python 编程的经过验证的步骤和策略。当你学习 Python 时，人们会教你如何编写代码，但在很多情况下，他们并不会教你如何整洁地编写代码。

如果你接触任何 Python 程序员，问他们喜欢 Python 的哪里，他们会告诉你它既简单、易读又强大。然而，他们也会告诉你，如果不小心，很容易写出糟糕的代码。本书旨在帮助你避免这些陷阱，并编写地道的 Python 代码。

## 第 1 章：Python 编码通用概念

在进入细节之前，我们需要理解 Python 的核心哲学。

### 显式代码

虽然 Python 允许许多操作，但通常显式比隐式更好。这意味着你的代码应该清楚地说明它正在做什么。

**糟糕的示例：**

**良好的的示例：**

### 一行一个语句

虽然 Python 允许你将多个语句放在同一行，但这通常会让代码更难以阅读和维护。

**糟糕的示例：**

**良好的示例：**

### 返回值

当你发现一个函数的复杂性不断增加时，在函数体中使用多个 `return` 语句并不是罕见的事。然而，如果你想保持清晰的意图和良好的可读性，你应该尝试避免从函数的多个点返回值。

在函数内部返回值时，有两种情况：来自正常处理函数返回的结果，以及指示输入参数错误或由于任何原因函数无法完成计算的错误。

如果你不想在后一种情况下抛出异常，那么可能需要返回如 `False` 或 `None` 等值，作为函数未能正常执行的指示。在这种情况下，最佳实践是在发现错误上下文时立即返回。

**糟糕的示例：**

**良好的示例：**

## 成功时尽量不要返回 `x`

```python
if not x:
    # 对 x 的方案 B 计算
    return x  # 在维护代码时，为值 x 设置一个出口点将很有帮助。
```

## 第 2 章：编程建议

这些是编写 Python 代码的基础建议。如果你希望你的代码更加有效、高效且具有可读性，就应该遵循这些建议。

- 你的代码编写方式不应不利其他 Python 实现，例如 `IronPython`、`Jython`、`PyPy`、`Psyco` 和 `Cython`。例如，你永远不要依赖 `CPython` 中高效的字符串拼接（形式为 `a=a+b` 或 `a+=b`）。这是一种相当脆弱的优化，尽管在 `CPython` 中非常高效，但它并不适用于所有类型，而且在任何不使用引用计数的 Python 实现中都不会存在。相反，当你使用对性能敏感的库部分时，应该使用 `.join()` 形式。这将确保字符串拼接在所有不同的 Python 实现中都是线性的。

- 永远不要使用相等运算符来与 `None` 等单例进行比较。相反，请使用 `is` 或 `not`。当你实际上应该使用 `if is not None` 时，也应该警惕使用 `if x`。这种情况的例子是，当你测试一个默认值为 `None` 的参数或变量是否真的被设置了不同的值时。该另一个值的类型在布尔上下文中可能为假（False）。

- 与其使用 `not...is` 运算符，你应该使用 `is not`。虽然它们在功能上完全等同，但前者的可读性分值较低，因此后者更受青。例如：

使用这种：

```python
if foo is not None:
```

不要使用这种：

```python
if not foo is None
```

- 当你通过富比较（rich comparison）实现排序操作时，你应该实现所有的 6 个操作，而不是依赖其他代码来执行比较。这些操作是 `(__eq__`、`__lt__`、`__ne__`、`__ge__`、`__gt__`、`__le__)`。为了减少工作量一个特定的装饰器有助于生成任何缺失的比较方法。该装饰器是 `functools.total_ordering()`。

风格指南指出 Python 假设了自反性（reflexivity rules）。因此，Python 解释器可能会通过交换 `y > x` 和 `x < y` 来改变内容，或者交换 `y >= x` 和 `x <= y`。你可能发现参数 `x == y` 被交换成了 `x != y`。`min()` 和 `sort()` 操作肯定会使用 `<` 运算符，`max()` 函数将使用 `>` 运算符。然而，作为最佳实践指南，你应该使用所有的操作以防产生混淆。

- 与其使用将 `lambda` 表达式绑定到标识符的赋值语句，不如使用 `def` 语句。

良好的示例：

```python
def f(x): return 2*x
```

一个糟糕的示例：

```python
f = lambda x: 2*x
```

第一个示例显示，给函数对象的名称是 `'f'` 而不是统一的 `<lambda>`。这对于字符串表示以及回溯（tracebacks）是最有用的；通过使用赋值语句，你放弃了 lambda 表达式相比 `def` 语句提供的唯一优势——即它可以被嵌入到更大的语句中。

当你想要派生异常时，请使用 `Exception` 而不是 `BaseException`。后者的继承被留给那些捕获它们几乎总是是错误的异常。

当你设计异常层次结构时，应基于捕获异常时可能需要的性质，而不是抛出异常的位置。始终回答一个问题——“出了什么错误？”而不是仅仅说某事出了问题。使用类命名的规范，但要记住为产生错误的异常类添加 “Error” 后缀。对于不是错误且用作流程控制或其他信号形式的异常，不需要添加任何特殊后缀。

- 当你使用异常链（exception chaining）时，仅在需要的地方使用。当你故意替换内部异常时，请确保将正确的细节重新定位到新的异常中。这些示例包括：在将 `KeyError` 转换为 `AttributeError` 时确保属性名称被保留，或者将原始异常文本嵌入到新异常的消息中。

- 当你使用 Python 2 且抛出异常时，始终使用 `raise ValueError('message')` 而不是 `raise ValueError ‘message’`。这是因为第二个示例在 Python 3 中既不是有效的也不是合法的语法。此外，包含括号的使用意味着当添加字符串格式化或异常参数过长时，不需要在行尾使用续行符。

- 当你捕获异常时，尽可能在可能的地方提到具体的异常，而不是使用裸的 `except:` 子句。

例如：

```python
try:
    import platform_specific_module
except ImportError:
    platform_specific_module = None
```

`KeyboardInterrupt` 和 `SystemExit` 异常会被裸的 `except:` 子句捕获，这使得使用 `CTRL+C` 中断程序变得困难得多，而且它们可能会掩盖存在的其他问题。

如果你想要捕获程序中信号错误的异常，请使用 `except Exception:`。一个通用规则是仅在以下情况之一使用裸的 `except:` 子句：

1. 如果回溯是那样打印的，用户会感知。

2. 如果需要使用 `finally` 进行清理。

当你将捕获的异常绑定到名称时，使用 Python 3 的显式语法：

```python
try:
    process()
except Exception as exc:
    raise DataError(str(exc))
```

- 当你捕获系统错误时，使用异常层次结构而不是值。同样，当你使用任何 `try/except` 子句时，尽量将使用范围限制在最少的代码内。这将减少错误隐藏的风险。

良好的示例：

```python
try:
    value = collection[key]
except KeyError:
    return key_found(key)
else:
    return handle_value(value)
```

一个糟糕的示例：

```python
try:
    # 范围太广了！
    return handle_value(collection[key])
except KeyError:
    # 会捕获来自 handle_value() 的 KeyError
    return key_found(key)
```

- 当你使用特定代码段资源工具时，使用语句确保在使用后立即清理。你也可以使用 `try/finally` 语句。

- 当上下文管理器用于获取和释放资源以外的目的时，始终通过单独的方法或函数调用它们。

良好的示例：

```python
with conn.start_transaction():
    do_something_in_transaction(conn)
```

一个糟糕的示例：

```python
with conn:
    do_something_in_transaction(conn)
```

第二个示例没有提供指示 `__enter__` 和 `__exit__` 方法是否执行了关闭事务之外的操作的信息。在这种情况下，显式化是重要的。

- 返回语句的一致性是重要的。函数的所有返回语句要么返回表达式或值，要么都不返回。如果某个返回语句返回了表达式，那么不返回任何值的语句应该显式声明返回 `None`，并在该函数末尾有一个返回语句。

良好的示例：

```python
def foo(x):
    if x >= 0:
        return math.sqrt(x)
    else:
        return None

def bar(x):
    if x < 0:
        return None
    return math.sqrt(x)
```

一个糟糕的示例：

```python
def foo(x):
    if x >= 0:
        return math.sqrt(x)
```

```python
def bar(x):
    if x < 0:
        return
    return math.sqrt(x)
```

- 不要使用字符串模块（string modules）；请使用字符串方法（string methods）

这些总是更快，并且与 Unicode 字符串共享一个 API。如果你需要与早于 `2.0` 的 Python 实现保持后兼容兼容，可以忽略这条规则。

- 与其使用字符串切片来检查后缀和前缀，请改用 `.startswith()` 和 `.endswith()`

这些方法要整洁得多，而且更不容易出错。

### 一个良好的示例：

```python
if foo.beginswith('bar'):
```

### 一个糟糕的示例：

```python
if foo[:3] == 'bar':
```

- 在比较对象类型时，使用 `isinstance()` 而不是直接比较

### 一个良好的示例：

```python
if isinstance(obj, int):
```

### 一个糟糕的示例：

```python
if type(obj) is type(1):
```

当你检查一个对象是否实际上为字符串时，请记住它也可能是一个 Unicode 字符串。在 Python `2.0` 中，Unicode 和 `str` 共享一个名为 `basestring` 的基类，因此你可以：

```python
if isinstance(obj, basestring):
```

然而，在 Python `3` 中，你找不到 `basestring` 或 `Unicode`，只有 `str` 和 `bytes` 对象不再是字符串，而是整数序列。

对于序列（元组、列表、字符串等）——请利用空序列为假的这一特性。

### 一个良好的示例：

```python
if not seq:
    if seq:
```

### 一个糟糕的示例：

```python
if len(seq):
    if not len(seq):
```

不要包含任何需要大量尾部空格的字符串字面量，因为这是无法区分，某些文本编辑器会删除它们。

不要使用 `==` 来比较布尔值与 `True` 或 `False`：

### 一个良好的示例：

```python
if greeting:
```

### 一个糟糕的示例：

```python
if the greeting == True:
```

### 一个更糟糕的示例：

```python
if greeting is True:
```

# 第 3 章：代码布局

最明显的起点点是如何布局你的代码。我将为你提供代码布局的最佳实践指南，并提供关于如何做以及如何不做的示例。

## 缩进与对齐

每个缩进级别都应该是 4 个空格。

当你使用延续行时，它们应该通过两种方法之一对齐折叠的元素：

- 使用 Python 在花括号、括号和圆括号内部隐式连接行的垂直对齐，或者
- 使用悬挂缩进（hanging indents）

### 一个良好的示例：

```python
if foo.beginswith('bar'):
```

### 一个糟糕的示例：

```python
if foo[:3] == 'bar':
```

- 当比较对象类型时，使用 `isinstance()` 而不是直接比较

### 一个良好的示例：

```python
if isinstance(obj, int):
```

### 一个糟糕的示例：

```python
if type(obj) is type(1):
```

当你检查一个对象是否实际上为字符串时，请记住它也可能是一个 Unicode 字符串。在 Python `2.0` 中，Unicode 和 `str` 共享一个名为 `basestring` 的基类，因此你可以：

```python
if isinstance(obj, basestring):
```

然而，在 Python `3` 中，你找不到 `basestring` 或 `Unicode`，只有 `str` 和 `bytes` 对象不再是字符串，而是整数序列。

对于序列（元组、列表、字符串等）——请利用空序列为假的这一特性。

### 一个良好的示例：

```python
if not seq:
    if seq:
```

### 一个糟糕的示例：

```python
if len(seq):
    if not len(seq):
```

不要包含任何需要大量尾部空格的字符串字面量，因为这是无法区分，某些文本编辑器会删除它们。

不要使用 `==` 来比较布尔值与 `True` 或 `False`：

### 一个良好的示例：

```python
if greeting:
```

### 一个糟糕的示例：

```python
if the greeting == True:
```

### 一个更糟糕的示例：

```python
if greeting is True:
```

# 第 3 章：代码布局

最明显的起点点是如何布局你的代码。我将为你提供代码布局的最佳实践指南，并提供关于如何做以及如何不做的示例：

## 缩进与对齐

每个缩进级别都应该是 4 个空格。

当你使用延续行时，它们应该通过两种方法之一对齐折叠的元素：

- 使用 Python 在花括号、括号和圆括号内部隐式连接行的垂直对齐，或者
- 使用悬挂缩进（hanging indents）

### 一个良好的示例：

```python
if foo.beginswith('bar'):
```

### 一个糟糕的示例：

```python
if foo[:3] == 'bar':
```

- 当比较对象类型时，使用 `isinstance()` 而不是直接比较

### 一个良好的示例：

```python
if isinstance(obj, int):
```

### 一个糟糕的示例：

```python
if type(obj) is type(1):
```

当你检查一个对象是否实际上为字符串时，请记住它也可能是一个 Unicode 字符串。在 Python `2.0` 中，Unicode 和 `str` 共享一个名为 `basestring` 的基类，因此你可以：

```python
if isinstance(obj, basestring):
```

然而，在 Python `3` 中，你找不到 `basestring` 或 `Unicode`，只有 `str` 和 `bytes` 对象不再是字符串，而是整数序列。

对于序列（元组、列表、字符串等）——请利用空序列为假的这一特性。

### 一个良好的示例：

```python
if not seq:
    if seq:
```

### 一个糟糕的示例：

```python
if len(seq):
    if not len(seq):
```

不要包含任何需要大量尾部空格的字符串字面量，因为这是无法区分，某些文本编辑器会删除它们。

不要使用 `==` 来比较布尔值与 `True` 或 `False`：

### 一个良好的示例：

```python
if greeting:
```

### 一个糟糕的示例：

```python
if the greeting == True:
```

### 一个更糟糕的示例：

```python
if greeting is True:
```

# 第 3 章：代码布局

最明显的起点点是如何布局你的代码。我将为你提供代码布局的最佳实践指南，并提供关于如何做以及如何不做的示例：

## 缩进与对齐

每个缩进级别都应该是 4 个空格。

当你使用延续行时，它们应该通过两种方法之一对齐折叠的元素：

- 使用 Python 在花括号、括号和圆括号内部隐式连接行的垂直对齐，或者
- 使用悬挂缩进（hanging indents）

### 一个良好的示例：

```python
if foo.beginswith('bar'):
```

### 一个糟糕的示例：

```python
if foo[:3] == 'bar':
```




当比较对象类型时，使用`isinstance()`而不是直接比较。

### 一个良好的示例

```python
if isinstance(obj, int):
```

### 一个糟糕的示例

```python
if type(obj) is type(1):
```

当你检查一个对象是否实际上为字符串时，请记住它也可能是一个 Unicode 字符串。在 Python `2.0` 中，Unicode 和`str`共享一个名为`basestring`的基类，因此你可以：

```python
if isinstance(obj, basestring):
```

然而，在 Python `3` 中，你找不到`basestring`或`Unicode`，只有`str`和`bytes`对象；它们不再是字符串，而是整数序列。

对于序列（元组、列表、字符串等），请利用空序列为假的这一特性。

### 一个良好的示例

```python
if not seq:
    if seq:
```

### 一个糟糕的示例

```python
if len(seq):
    if not len(seq):
```

不要包含任何需要大量尾部空格的字符串字面量，因为这是无法区分的，某些文本编辑器会删除它们。

不要使用`==`来比较布尔值与`True`或`False`。

### 一个良好的示例

```python
if greeting:
```

### 一个糟糕的示例

```python
if the greeting == True:
```

### 一个更糟糕的示例

```python
if greeting is True:
```

# 第 3 章：代码布局

最明显的起点是如何布局你的代码。我将为你提供代码布局的最佳实践指南，并提供关于如何做以及如何不做的示例。

## 缩进与对齐

每个缩进级别都应该是 4 个空格。

当你使用延续行时，它们应该通过以下两种方法之一对齐折叠的元素：

- 使用 Python 在花括号、方括号和圆括号内部隐式连接行的垂直对齐方式；
- 使用悬挂缩进。

### 一个良好的示例

```python
if foo.beginswith('bar'):
```

### 一个糟糕的示例

```python
if foo[:3] == 'bar':
```

当比较对象类型时，使用`isinstance()`而不是直接比较。

### 一个良好的示例

```python
if isinstance(obj, int):
```

### 一个糟糕的示例

```python
if type(obj) is type(1):
```

当你检查一个对象是否实际上为字符串时，请记住它也可能是一个 Unicode 字符串。在 Python `2.0` 中，Unicode 和`str`共享一个名为`basestring`的基类，因此你可以：

```python
if isinstance(obj, basestring):
```

然而，在 Python `3` 中，你找不到`basestring`或`Unicode`，只有`str`和`bytes`对象；它们不再是字符串，而是整数序列。

对于序列（元组、列表、字符串等），请利用空序列为假的这一特性。

### 一个良好的示例

```python
if not seq:
    if seq:
```

### 一个糟糕的示例

```python
if len(seq):
    if not len(seq):
```

不要包含任何需要大量尾部空格的字符串字面量，因为这是无法区分的，某些文本编辑器会删除它们。

不要使用`==`来比较布尔值与`True`或`False`。

### 一个良好的示例

```python
if greeting:
```

### 一个糟糕的示例

```python
if the greeting == True:
```

### 一个更糟糕的示例

```python
if greeting is True:
```

# Chapter 3: Code Layout

The most obvious place to start with is how to lay out your code. I will be giving you the best-practice guidelines for code layout, along with examples of how to do it and how not to do it.

## Indentation and Alignment

Every indent level should be 4 spaces.

When you use continuation lines, they should align the wrapped elements using one of two methods:

- Vertically, using Python’s implicit way of joining lines inside braces, brackets, and parentheses;
- With hanging indents.

### A Good Example

```python
if foo.beginswith('bar'):
```

### A Bad Example

```python
if foo[:3] == 'bar':
```

When you are comparing object types, use`isinstance()`instead of direct comparisons.

### A Good Example

```python
if isinstance(obj, int):
```

### A Bad Example

```python
if type(obj) is type(1):
```

When you check to see if an object is actually a string, remember that it could be a Unicode string as well. In Python `2.0`, Unicode and`str`share the base class called`basestring`, so you could do:

```python
if isinstance(obj, basestring):
```

However, in Python `3`, you won’t find`basestring`or`Unicode`; only`str`and`bytes`objects are available. They are no longer strings, but instead represent sequences of integers.

For a sequence—tuples, lists, strings, and so on—make use of the fact that an empty sequence is false.

### A Good Example

```python
if not seq:
    if seq:
```

### A Bad Example

```python
if len(seq):
    if not len(seq):
```

Don’t include any string literals that require significant levels of trailing whitespace, because this is not distinguishable and some text editors will remove it.

Don’t use`==`to compare a Boolean value to`True`or`False`.

### A Good Example

```python
if greeting:
```

### A Bad Example

```python
if the greeting == True:
```

### An Even Worse Example

```python
if greeting is True:
```

# Chapter 3: Code Layout

The most obvious place to start with is how to lay out your code. I will be giving you the best-practice guidelines for code layout, along with examples of how to do it and how not to do it.

## Indentation and Alignment

Every indent level should be 4 spaces.

When you use continuation lines, they should align the wrapped elements using one of two methods:

- Vertically, using Python’s implicit way of joining lines inside braces, brackets, and parentheses;
- With hanging indents.

### A Good Example

```python
if foo.beginswith('bar'):
```

### A Bad Example

```python
if foo[:3] == 'bar':
```

When you are comparing object types, use`isinstance()`instead of direct comparisons.

### A Good Example

```python
if isinstance(obj, int):
```

### A Bad Example

```python
if type(obj) is type(1):
```

When you check to see if an object is actually a string, remember that it could be a Unicode string as well. In Python `2.0`, Unicode and`str`share the base class called`basestring`, so you could do:

```python
if isinstance(obj, basestring):
```

However, in Python `3`, you won’t find`basestring`or`Unicode`; only`str`and`bytes`objects are available. They are no longer strings, but instead represent sequences of integers.

For a sequence—tuples, lists, strings, and so on—make use of the fact that an empty sequence is false.

### A Good Example

```python
if not seq:
    if seq:
```

### A Bad Example

```python
if len(seq):
    if not len(seq):
```

Don’t include any string literals that require significant levels of trailing whitespace, because this is not distinguishable and some text editors will remove it.

Don’t use`==`to compare a Boolean value to`True`or`False`.

### A Good Example

```python
if greeting:
```

### A Bad Example

```python
if the greeting == True:
```

### An Even Worse Example

```python
if greeting is True:
```

## Additional Guidelines

- 不要使用字符串模块（string modules），请使用字符串方法（string methods）。这些方法总是更快，并且与 Unicode 字符串共享一个 API。如果你需要与早于 `2.0` 的 Python 实现保持后兼容，可以忽略这条规则。
- 与其使用字符串切片来检查后缀和前缀，请改用`.startswith()`和`.endswith()`。这些方法更整洁，也更不容易出错。

### 一个良好的示例

```python
if foo.startswith('bar'):
```

### 一个糟糕的示例

```python
if foo[:3] == 'bar':
```



```python
if greeting is True:
```

# 第 3 章：代码布局

最明显的起点是如何布局你的代码。我将为你提供代码布局的最佳实践指南，并提供关于如何做以及如何不做的示例：

## 缩进与对齐

每个缩进级别都应该是 4 个空格。

当你使用延续行时，它们应该通过两种方法之一对齐折叠的元素：

* 使用 Python 在花括号、括号和圆括号内部隐式连接行的垂直对齐，或者

* 使用悬挂缩进（hanging indents）

现在，这两个函数看起来完全一样，仅仅是因为 `lookup_set` 利用了 Python 集合（sets）是哈希表这一事实。然而，每个示例中 `lookup` 的性能是不同的。为了判断一个特定项目是否包含在列表中，Python 必须搜索每一个项目，直到找到匹配的项为止。这需要时间，特别是当你的列表很长时。使用集合，每个项目都有一个哈希值，它能告诉 Python 去哪里查找匹配的项。这使得即使集合很大，搜索速度也会快得多。你也可以以相同的方式搜索字典。由于性能存在差异，在以下情况下，使用集合或字典比使用列表更好的主意：

* 当集合包含大量项时

* 当你需要频繁地在集合中查找项时

* 没有重复项时

对于较小的集合或那些不太可能频繁搜索的集合，建立哈希表所需的额外内存和时间，通常会超过你通过提高搜索速度所节省的时间。

## 第 5 章：注释

由于你已经有了一些 Python 编程的经验，你会知道注释在程序运行时是不可见的。注释的作用是帮助编码员和其他阅读代码的人理解做了什么以及为什么要这样做。现在，有些人认为，因为注释是不可见的，所以没必要写它们；而另一些人写的注释毫无意义且与他们的代码矛盾。我必须告诉你，在这两者之间，拥有一个矛盾的注释比完全不写要糟糕得多，因此，每当你对代码进行更改时，都必须确保更新你的注释。

当你写一条注释时，确保它是一个带有正确结尾的完整句子。正如你写任何内容一样，你的注释（无论是句子还是短语）必须大写字母开头。该规则的唯一例外是它是以小写字母开头的标识符——这里的黄金法则是你**永远不要**改变标识符的大小写！

如果你使用短注释，可以省略结尾的句号。如果你在写块注释，这些注释通常由至少一段组成，有时更多，且每一段都由完整的句子组成。这些句子中的每一个都必须有一个句号。每个句号后面应该有 2 个空格，且所有注释都应该用英文编写。唯一的例外是你 200% 确定你的代码永远不会被不通或不读你母语的人阅读。

## 块注释

块注释倾向于适用于其后的部分或全部代码。注释的缩进方式必须与它所引的代码完全一致，且每个块的每一行必须以一个 `#` 和一个空格开头。唯一的例外是你是在注释内部使用了缩进文本。每个块注释中的所有段落必须用一个包含一个 `#` 的行隔开。

## 行内注释

这些应该尽可能少地使用。作为回顾，行内注释是放置在语句同一行的注释。行内注释必须与语句之间至少有两个空格隔开，并且它们必须以一个 `#` 和一个空格开头。

诚实地说，你应该避免使用行内注释，因为它们并不是真正必要的，并且可能会引起意外的干扰。

例如，你永远不要这样做：

```python
x = x + 1              # Increment x
```

然而，有时这可能是很有用的：

```python
x = x + 1              # Compensate for the border
```

## 第 6 章：规范

为了让你的 Python 代码变得更好，请遵循这些规范：检查你的变量是否等于常量。没有必要对值与 `0`、`None` 或 `True` 进行显式比较；相反，你可以将其加入 `if`-语句中。看以下示例：

### 糟糕的示例

```python
if attr == True:
    print 'True!'

if attr == None:
    print 'attr is None!'
```

### 良好的示例

```python
# 只看它的值
if attr:
    print 'attr is the best!'

## 或者检查相反的情况是什么
if not attr:
    print 'attr is the worst!'

## 或者，由于 None 被视为假，确保你对它运行了显式检查
if attr is None:
    print 'attr is None!'
```

## 如何访问字典元素

不要使用 `dict.has_key()` 方法，请使用 `x in d` 语法或使用 `dict.get()` 来传递默认参数。

### 糟糕的示例

```python
d = {'hello': 'world'}

if d.has_key('hello'):
    print d['hello']    # prints 'world'
else:
    print 'the_default_value'
```

### 良好的示例

```python
d = {'hello': 'world'}
print d.get('hello', 'default_value') # prints 'world'
print d.get('thingy', 'default_value') # prints 'default_value'
```

### 或者：

```python
if 'hello' in d:
```

## 简便操作列表

对于较小的集合或那些不太可能频繁搜索的集合...使用列表推导式或 `map()`。

### 糟糕的示例

```python
a = [5, 4, 3]
for i in a:
    print i
```

### 良好的示例

```python
a = [5, 4, 3]
b = [i + 3 for i in a]
```

## 读取文件

当你想要从文件中读取内容时，最好使用 `with` 语法，因为它会自动关闭文件。

### 糟糕的示例

```python
f = open('file.txt')
a = f.read()
print a
f.close()
```

### 良好的示例

```python
with open('file.txt') as f:
    for line in f:
        print line
```

话虽如此，如果你发现自己必须不断拆分长行，这说明你正尝试做太多的事情，这将会影响代码的可读性。

# 第 7 章：方法和函数参数

对于任何实例方法的第一个参数，始终使用 `self`；对于任何类方法的第一个参数，始终使用 `cls`。

如果一个函数的参数名与某个保留关键字相同，那么最好在末尾添加一个下划线，这比使用错误的拼写或缩写要好。因此，你应该使用 `class_` 而不是 `clss`。也许比引起冲突更好的方法是使用同义词。

## 函数参数

有 4 种向函数传递参数的方法：

1. **位置参数（Positional Argument）** – 这些是强制性的，且不包含任何默认值。位置参数是最简单的参数形式，用于作为函数含义完整组成部分的参数；它们还具有自然顺序，因此，在下面的示例中，函数 `user` 应该很容易记住这两个函数需要 2 个参数，并且它们应该记住顺序：

`Send(message, recipient)` 和 `point(x, y)`

在这两种情况下，你可以在调用函数时使用参数名，通过这样做，你可以更改参数的顺序。例如，你可以调用 `send(recipient='world', message='Hello')` 和 `point(y=2, x=1)`。然而，正如你所看到的，这并不非常可读，而且里面的单词远超我们的需要。将该版本与更直观的版本——`send('Hello', 'World')` 和 `point(1,2)` 进行比较，你可以立即看出可读性的差异。

2. **关键字参数（Keyword Argument）** – 这些参数包含默认值，且不是强制性的。关键字参数有时用于发送到函数的可选参数。当一个函数包含至少 2 或 3 个（最好更多）位置参数时，很容易被记住。使用带有默认值的关键字参数会更有帮助。例如，你可以定义一个完整的 `send` 函数为 `send(message, to, cc=None, bcc=None)`。`cc` 和 `bcc` 的使用是可选的，如果给它们赋予其他值，它们的值都为 `None`。

在 Python 中，有几种方法可以使用关键字参数调用函数。例如，你可以遵循定义中的参数顺序，而不显式地命名这些参数；例如，`send('Hello', 'World', 'Galactus', 'God')`。在这里，你正在向 Galactus 发送消息的抄送，并向 God 发送盲抄。你也可以以不同的顺序命名参数，例如，`send('Helloagain', 'World', bcc='God', cc='Galactus')`。除非你有非常充分的理由不尽可能遵循正确的语法，否则这两个示例最好被避免；它们既冗长又不可读。最好的方法，即最接近函数定义的方法，是 `send('Hello', 'World', cc='Galactus', bcc='God')`。

3. **任意参数列表（Arbitrary Argument List）** - 这是向函数传递参数的另一种方法。有时，函数的意图通过具有数量位置参数的签名来表达更好，这个数量是可以扩展的。在这种情况下，最好使用 `*args` 结构来定义它。在参数体中，`args` 是所有剩余位置参数的元组。例如，你可以使用 `send(message, *args)` 并将所有接收者列为单独参数：`send('Hello', 'Galactus', 'Dad', 'God')` —— 在函数体内，`args` 等于 `('Galactus', 'Dad', 'God')`。

然而，你应该非常谨慎地使用这种结构，因为它确实有一些缺点。如果向函数发送了一个包含具有相同或相似性质参数的列表，更好的定义是一个带有单个参数的函数；该单个参数将是一个序列或列表。例如，如果 `send` 有几个接收者，你使用显式定义更好：`send('Hello', 'God', 'Dad', 'Galactus')`，然后通过 `send('Hello', ['God', 'Dad', 'Galactus'])` 来调用它。这样，函数用户可以提前更改接收者列表，这为传递任何无法解包的序列提供了可能，包括迭代器。

4. **任意关键字参数字典（Arbitrary Keyword Argument Dictionary）** - 这是向函数传递参数的最后方法。如果函数需要一个未知的命名参数数组，你可以使用 `**kwargs` 结构。在函数体内，`**kwargs` 是一个字典，包含了所有传递且未被函数签名中另一个关键字参数捕获的命名参数。

然而，你应该采取像对待任意参数列表时那样的谨慎程度，因为原因几乎相同。这些是强大的技术，只有当你证明有必要使用它们时才应该使用。如果有更清晰、更简单的结构可以完成工作，绝对不应该使用它们。

这完全取决于你，程序员，决定哪些函数参数是可选关键字，哪些是位置参数，并决定是否应该使用更高级的技术来传递参数。

保持简单并遵循这些编写 Python 函数的规则：

* 是可读的 – 名称和参数不需要任何解释

* 易于更改 – 你可以添加关键字参数而不会破坏其他代码。

# 第 8 章：命名规范

老实说，Python 的命名规范像是一团糟，所以我们永远无法做到完全一致。然而，有一些推荐的命名标准，所有新的包和模块（包括任何第三方框架）必须遵循这些标准。尽管如此，要学习最重要的原则是，当你使用可见 API 名称时，必须使用反映其使用的规范，而不是其实现。

## 描述性

有许多不同的命名样式，因此识别在使用哪种样式是有帮助的。以下是区分常用的命名样式：

* `B` – 单字母大写

* `b` – 单字母小写

* `lowercase_with_underscores`

* `lowercase`

* `UPPERCASE_WITH_UNDERSCORES`

* `UPPERCASE`

* `CapitalizedWords` – 通常称为 CamelCase，因为字母看起来像

* `mixedCase` – 与 CamelCase 不同，因为首字母是小写

* `Capital_Words_With_Underscore` – 不是一种漂亮的样式！

* 在 CamelCase 中使用缩写时，你应该确保所有的缩写字母都大写。例如，与其使用 `HttpServerError`，不如使用 `HTTPSError`。

还可以使用另一种样式，即放置一个唯一的前缀（短的），将一组相关的名称放在一起。这在 Python 中并不常用，但我提到它是为了让你知道它的存在。一个例子是 `os.stat()` 函数 —— 它将返回一个元组，其中包含的项目如 `st_size`, `st_mode`, `st_mtime` 等。

这些是一些使用末尾下划线或前导下划线的形式，通常可以与任何大小规范结合：

* `_one_leading_underscore` – 这通常是“内部使用”的指示，但并不强。

* `One_trailing_underscore_` – 通常用于防止与 Python 关键字冲突，例如：`tkinter.Toplevel(master, class_='ClassName')`

* `__two_leading_underscores` – 当你命名类属性时，这会引发名称修饰（mangling），例如：（在类 `FootBar` 内部，`__boo`）会变成 `(_FootBar__boo)`

* `two_leading_and_two_trailing_underscores` 是属性或“魔法”对象，存在于用户控制的命名空间中。例如：`__init__`、`__file__` 或 `__import__`。

## 规范性

这些是你应该避免使用的名称：

在编写单字符变量名时，永远不要使用 `O`（大写字母）、`l`（小写 L）或 `I`（大写 i）。取决于你所使用的字体，这些字符可能与数字 `0` 和 `1` 混淆——如果你发现自己想用 `l`，请改用大写的 `L`。

## 模块和包的命名

所有的模块名称都应该是简短且全小写的。你可以在模块名中使用下划线，但仅当它能提高可读性时才。Python 包也是如此——使用简短且全小写的名称——但不要使用下划线。

当你有一个用 C 或 C++ 编写的扩展模块，并且它配有一个具有面向对象接口的 Python 模块时，C 或 C++ 模块将以下划线开头，例如 `_socket`。

## 类名

类名通常使用 CapWords（大驼峰法）或 CamelCase（驼峰法）约定。

内置名称有它们单独的约定，通常是一个单词或两个单词合并为一个，例如 `Hello` 或 `HelloWorld`。CamelCase 约定倾向于用于内置常量和异常名称。

## 类型变量

类型变量的名称通常使用 CamelCase，并且优于使用短名称，例如 `Num`、`AnyStr`。你应该为变量添加后缀（`_co` 或 `_contra`）来声明反变或协变行为。例如：

```python
Import TypeVar
```

```python
VT_co = TypeVar('VT_co', covariant=True)
KT_contra = TypeVar('KT_contra', contravariant=True)
```

## 异常命名

异常是类，因此你应该使用类的命名约定进行命名。尽管如此，如果异常是一个错误，请确保在名称中使用 `Error` 后缀。

## 全局变量

只要变量在单个模块内部使用，其命名规范与函数命名规范相同。

## 函数

所有函数名均为小写，并在需要提高可读性的地方用下划线分隔单词。`mixedCase` 约定仅在已以此风格的语境中使用，以保持向后兼容性。

## 实例变量和方法名

同样，函数的命名规范也适用于这里——使用小写并间歇使用下划线。如果你正在使用实例变量或非公共方法，应该使用单个前缀下划线。为了防止名称与子类冲突，应该使用两个前缀下划线，以触发 Python 中的名称修饰（name mangling）规则。

当这些规则被触发时，名称会与类名进行修改。例如，`class Foo` 包含一个名为 `__a` 的属性。无法通过 `Foo.__a` 访问它。按照规则，只有当名称可能与设计为子类的类属性发生冲突时，才使用双前缀下划线。

## 常量

这些通常定义在模块级，且全大写并用下划线分隔，例如 `MAX_OVERFLOW`。

## 继承设计

必须遵守的规则之一是确定实例变量或类方法是非公开的还是公共的。如果你无法决定，请选择非公开，因为你可以以后轻松将其改为公共，而将公共改为非公开并不那么容易。

公共属性是指与类无关的客户端会使用的属性，而非公开属性是不供第三方使用的。对于公共属性，你保证了从开始到结束的向后兼容；而对于非公开属性，你不需要，并且可以移除或更改该属性。注意，不使用“私有”一词，这是因为 Python 语言中没有真正的私有属性。

另一个属性类别是保护属性（protected attribute）。在 Python 中，它们属于子类 API。有些类专门设计为供继承的，无论是为了扩展还是修改某些行为方面。当你设计这样的类时，务必确保对属性做出显式决策——它们是公共的、仅供基类使用的，还是属于子类 API？

结合以上所有点，这些是 Pythonic 的准则：

* 公共属性不能有前缀下划线。

* 如果公共属性与关键字（保留字）冲突，请在属性名称末尾添加一个下划线。这是比使用拼写错误或缩写更优的方法。

* 对于公共数据属性，最好的方法是只暴露属性名称，而不使用任何复杂的修改器（mutator）或访问器（accessor）方法。如果简单的属性需要扩展其功能行为，Python 可以轻松实现。

* 如果你正在使用一个将被子类的类，并且你也使用了不会被子类的属性，考虑添加 2 个前缀下划线，但不要添加任何末尾下划线。这将触发名称修饰，并有助于降低子类具有相同名称属性时发生冲突的风险。

## 第 9 章：在语句和表达式中使用空格

首先，一些关于空格令人不悦的点：

在以下情况下不要使用不必要的空格：

* 紧邻大括号、中括号或圆括号内部

良好的示例：



```python
ham(spam[1], {eggs: 2})
```

错误的示例：

```python
ham( spam[ 1 ], { eggs: 2 } )
```

- 在冒号、分号或逗号之前

良好的示例：

```python
if x == 4:
```

错误的示例：

```python
if x == 4 :
```

然而，在切片（slice）中，冒号类似于运算符，应该在两侧都包含等的空格。例外是省略的切片。

良好的示例：

```python
spam[1:8], ham[1:2]
```

错误的示例：

```python
spam[1 : 8], ham[1 : 2]
```

`spam[lower:upper]`

```python
spam[: upper]
```

- 在函数调用参数列表起始圆括号前

良好的示例：

```python
ham(1)
```

错误的示例：

```python
ham (1)
```

- 在切片或索引的起始圆括号前

良好的示例：

```python
dct['key'] = lst[index]
```

错误的示例：

```python
dct ['key'] = lst [index]
```

- 当运算符（如赋值）周围有多个空格以与其他运算符对齐

良好的示例：

```python
x = 1
y = 2
long_variable = 3
```

错误的示例：

```python
x         = 1
y         = 2
long_variable = 3
```

## 其他建议

在代码中避免行尾空格，因为它是不可见的且会引起混淆。例如，如果你放了一个反斜杠并跟着一个空格然后换行——这不会被视为行延续符。事实上，某些文本编辑器不会保留它，并且某些项目包含的提交钩子会直接拒绝它——其中之一就是 CPython。

以下二元运算符应该被单个空格包围——两侧各一个：

- 赋值（`=`）
- 复合赋值（`+=`、`-=` 等）

以下比较运算符的处理方式相同：

- `==`
- `<`
- `>`
- `!=`
- `<>`
- `<=`
- `>=`
- `in`
- `not in`
- `is`
- `is not`

以及这些布尔值：

- `and`
- `or`
- `not`

如果你使用了不同优先级的运算符，请考虑在优先级最低的运算符周围添加空格——此处请根据你的判断来决定。然而，空格不应超过一个空格，并确保运算符两侧的空格数量相同——不要在一侧放 1 个而在另一侧放 2 个：

### 良好的示例

```python
i = i + 1
submitted += 1
x = x*2 - 1
hypot2 = x*x + y*y
c = (a+b) * (a-b)
```

### 糟糕的示例

```python
i=i+1
submitted +=1
x = x * 2 - 1
hypot2 = x * x + y * y
c = (a + b) * (a - b)
```

当你使用 `=` 号来指示参数或关键字参数的默认值时，不要在符号周围添加空格：

### 良好的示例

```python
def complex(real, imag=0.0):
    return magic(r=real, i=imag)
```

### 糟糕的示例

```python
def complex(real, imag = 0.0):
    return magic(r = real, i = imag)
```

对于函数注解中的冒号，使用标准规则，并确保在使用了 `->` 时周围有空格：

### 良好的示例

```python
def munge(input: AnyStr): ...
def munge() -> AnyStr: ...
```

### 糟糕的示例

```python
def munge(input:AnyStr): ...
def munge()->PosInt: ...
```

当结合默认值和参数注解使用时，`=` 号周围应该有空格——除非该参数同时具有默认值和注解，否则不要这样做：

### 良好的示例

```python
def munge(sep: AnyStr = None): ...
def munge(input: AnyStr, sep: AnyStr = None, limit=1000): ...
```

### 糟糕的示例

```python
def munge(input: AnyStr=None): ...
def munge(input: AnyStr, limit = 1000): ...
```

使用复合语句（即在一行内编写多个语句）不是良好的习惯：

### 良好的示例

```python
if foo == 'that':
    do_that_thing()
do_one()
do_two()
do_three()
```

### 尽量不要这样做

```python
if foo == 'that': do_that_thing()
do_one(); do_two(); do_three()
```

偶尔在一行内使用 `if`、`for` 和 `while` 语句是可以的，只要它们的体很小，但你永远不要对包含多个从句的语句这样做。此外，永远不要折叠非常长的行：

### 尽量不要这样做

```python
if foo == 'that': do_that_thing()
for x in lst: total += x
while t < 10: t = delay()
```

### 绝对不要

```python
if foo == 'that': do_that_thing()
else: do_non_that_thing()
try: something()
finally: cleanup()
do_one(); do_two(); do_three(long, argument,
                             list, like, this)
if foo == 'that': one(); two(); three()
```

## 结论

再次感谢你阅读我的书，我真心希望它能帮助你理解如何编写更有效高效的 Python 代码。

从这里开始，下一步简单来说就是实践。你做得越多，就会做得越好，最终，你将像专业人士一样编写 Python 代码！通过研究、加入在线 Python 论坛并加入 Python 社区来学习更多知识并提升你的技能。

最后，如果你觉得这本书有帮助，可以请你帮一个小忙吗？请考虑在 `Amamzon.com` 上给我留评价；这不仅对我有用，对潜在读者也有益。

感谢你，祝你在成为更好的 Python 程序员的道路上顺利。

## 关于作者

Charlie Masterson 是一位计算机程序员和导师，他开发过多个应用程序和计算机程序。

作为一名计算机科学学生，他很早就对编程感兴趣，但在学习极其复杂的科目时感到沮丧。

Charlie 想要一种能够轻松学习并提高编程技能的教学方法。他很快发现了一个让他学得更快、更好的教学系列。

应用同样的方法，Charlie 成功学习了不同的编程语言，现在正通过编写书籍教授这一领域。

通过他写的关于计算机编程的书，他希望提供巨大的价值，并帮助对学习计算机相关话题感兴趣的读者。
