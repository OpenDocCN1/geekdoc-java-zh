
# Java 到 Python 转换指南

## 10. 字符串

## 16. 使用 Python 构建网站

# 作者寄语

Python 与 Java 相似，有时看起来更简单。

该语句位于类之外、所有方法之外，当 Python 运行文件 `pythonAnything.py` 时首先执行，无需显式调用。在 `if` 语句内部，我创建了类 `SimpleProgram` 的实例，它会自动执行位于类 `SimpleProgram` 内部的初始化方法。在初始化方法中，我调用了 `printHelloWorld()`，它会在屏幕上打印出“Hello World”。

初始化方法是在类实例创建时自动执行的方法。它始终以相同的格式编写：`def __init__(self):`。这个方法非常有用，可以作为一个设置方法，在用户调用和运行类的其他方法之前，自动执行某些段代码。

在 Java 中，我显式地指定该方法为 public（公开的）。相比之下，Python 中的所有方法默认都是公开的，消除了指定的必要。要让 Python 中的方法设为私有，我在方法名称前面添加双下划线。因此，我的初始化方法 `__init__(self):` 是私有方法。但我的 `def printHelloWorld(self):` 方法是公开的。如果我想把它变成类的私有成员，我会在它的名字前面添加两个下划线，如下例所示：

```python
def __printHelloWorld(self):
```

这将改变我从初始化方法调用该方法的方式：

```python
def __init__(self):
    self.__printHelloWorld()
```

Java 中的类名具有 `java` 扩展，但在 Python 中，文件名带有 `.py` 扩展。需要记住的一个非常重要的点是，在 Java 中，类文件名必须与类名相同，但在 Python 中，类文件名可以与文件中定义的类名不同。

在 Java 中，类的所有内容——方法、循环、if 语句、switch 等——都包含在由大括号 `{}` 包围的块中。在 Python 中不存在大括号，相反，所有代码都通过缩进表示。

在 Java 中：

```java
if(x>y){
    x=y++;
}
```

对于 Python 中相同的过程，只需删除大括号但保留缩进。使用一个 Tab 或四个空格作为第一级缩进。第二级缩进使用两个 Tab 或八个空格；第三级缩进使用三个 Tab 或 12 个空格，以此类推。

## 在 Python 中：

```python
if x>y:
    x = y + 1
```

Java 中使用分号来结束一个语句，但在 Python 中这是没有必要的。

## 在 Java 中：

```java
System.out.print("Hello World");
```

## 在 Python 中：

```python
print("Hello World")
```

然而，要在 Python 中换新行打印字符串，你需要在字符串的开头、中间或结尾添加换行字符 `\n`，准确在你想要插入换行的地方。

## 在 Java 中：

```java
System.out.println("Hello World");
```

## 在 Python 中：

```python
print("HelloWorld\n")
```

接下来，示例 1.2 展示了 Java 和 Python 在类和方法结构语法上的差异。

### 示例 1.2

在 Java 中：

```java
class AnyClass {
    public void anyMethod() {
        System.out.println("Hello World");
    }
}
```

在 Python 中：

```python
class AnyClass:
    def anyMethod(self):
        print("Hello World\n")
```

## 2. 编译程序

在运行 Java 程序之前，它首先需要由 Java 编译器编译，并转换为一组 JVM 可以理解并执行的字节码。在 Python 中，这不是必要的，因为程序可以作为解释型程序运行，尽管有一种方法可以将 Python 程序编译为可执行文件。

`main()` 方法在 Java 应用中用于在当 Java 编译后的 `.jar` 文件执行以启动程序时定义应用程序的起点。在 Python 中，没有 `main()` 方法，因为程序没有编译，而且我可以访问程序的所有文件。因此，我可以通过运行 `python` 命令并传递给它的第一个参数的文件名来启动程序。因此，应用程序的任何一个文件都可以作为程序开始运行的起点。

如果你看过 Python 程序的代码，你可能会注意到下面这行代码：

```python
if __name__ == "__main__":
```

不要让这困扰你。这不同于 Java 中存在的那种 `main()`。Python 的 `if __name__ == "__main__":` 条件用于防止类在被另一个类导入时被执行，但当它通过 `python` 命令直接调用时，它将执行。示例 2.1 和 2.2 展示了带有 `if __name__ == "__main__":` 条件的 Python 代码与不带该条件的代码之间的语法差异。

### 示例 2.1

```python
### 程序开始
class SimpleProgram:
    def __init__(self):
        self.printHelloWorld()

    def printHelloWorld(self):
        print("Hello World\n")

run = SimpleProgram()
### 程序结束
```

### 示例 2.2

```python
### 程序开始
class SimpleProgram:
    def __init__(self):
        self.printHelloWorld()

    def printHelloWorld(self):
        print("Hello World\n")

if __name__ == "__main__":
    run = SimpleProgram()
### 程序结束
```

## 3. 变量

Python 中的变量的定义与 Java 相同。变量是虚拟内存中的一个存储位置，可以赋予某些值。变量的值可以在程序执行期间被更改，也可以保持为常数。下一个程序展示了如何声明变量以及如何为其赋值。

在 Python 中，变量的作用方式与 Java 相同，但同样更简单。在 Java 中，所有变量必须用特定的数据类型声明，例如整数、字符串或布尔值。Python 再次消除了指定变量数据类型的必要性。你只需要给变量一个名称并为其分配一个值。Python 会自动检测赋值的值是整数、字符串还是任何其他数据类型，并自动为变量分配正确的数据类型。

当用整数值创建一个变量时，它就变成了一个整数类型的变量。因此，如果以后某个时候你想将变量转换为另一种类型……

类似的概念也适用于 Python 中的其他变量数据类型。在示例 3.1 中，我将介绍每种数据类型并演示 Python 如何进行类型转换。

让我们创建一个新文件 `pythonAnythingTwo.py`，并将示例 3.1 中的代码放入其中：

### 示例 3.1

```python
### 程序开始
class SimpleProgram:
    def variablesInPython(self):
        strVariableOne = "String One"
        strVariableTwo = "98876"
        strVariableThree = "9999.99"
        intVariable = 0
        booleanVariable = True
        longVariable = long(9223372036854775807)
        floatVariable = 123.123

        # 使用 Python 的函数 type()，查看 Python 为每个变量分配了什么数据类型。
        print("Types:")
        print type(strVariableOne)
        print type(strVariableTwo)
        print type(strVariableThree)
        print type(intVariable)
        print type(booleanVariable)
        print type(longVariable)
        print type(floatVariable)

        print "\nConverting strVariableTwo to an Integer"
        convertedVariable = int(strVariableTwo)
        print convertedVariable
        print type(convertedVariable)

        print "\nConverting strVariableThree to an Integer"
        convertedVariable = int(float(strVariableThree))
        print convertedVariable
        print type(convertedVariable)

        print "\nConverting strVariableTwo to a Float"
        convertedVariable = float(strVariableTwo)
        print convertedVariable
        print type(convertedVariable)

        print "\nConverting strVariableThree to a Float"
        convertedVariable = float(strVariableThree)
        print convertedVariable
        print type(convertedVariable)

        print "\nConverting intVariable to a Long"
        convertedVariable = long(intVariable)
        print convertedVariable
        print type(convertedVariable)

        print "\nConverting longVariable to an Int"
        convertedVariable = int(longVariable)
        print convertedVariable
        print type(convertedVariable)

        print "\nConverting floatVariable to a String"
        convertedVariable = str(floatVariable)
        print convertedVariable
        print type(convertedVariable)

        print "\nConverting booleanVariable to a String"
        convertedVariable = str(booleanVariable)
        print convertedVariable
        print type(convertedVariable)

        print "\nConverting booleanVariable to an Integer"
        convertedVariable = int(booleanVariable)
        print convertedVariable
        print type(convertedVariable)

        print "\nUsing intVariable as a Boolean"
        if intVariable:
            print "True"
        else:
            print "False"

        print "\nConcatenating all data types into one string variable"
        concatenatedVariable = strVariableOne + \
            str(intVariable) + \
            str(booleanVariable) + \
            str(longVariable) + \
            str(floatVariable)
        print concatenatedVariable

run = SimpleProgram()
run.variablesInPython()
### 程序结束
```

从示例 3.1 可以看出，要将变量转换为整数，我使用了 Python 的函数 `int()`。

要转换为字符串，我使用了 Python 的函数 `str()`。

要转换为浮点数（或在 Java 中尽可能多的双精度类型），我使用了 Python 的函数 `float()`。

要转换为长型，我使用了 Python 的函数 `long()`。

在示例 3.1 的“将 strVariableThree 转换为整数”部分中，我先将字符串变量转换为浮点数，然后将变量转换为整数。这就是 Python 中的工作原理。如果字符串变量的数字之间包含小数点，则无法直接转换为整数。但通过一个小技巧，我仍然实现了这一目标。

```python
convertedVariable = int(float(strVariableThree))
```

在示例 3.1 的“将 intVariable 用作布尔值”部分，我得到的输出是“False”。这是因为我的整数变量等于 0。在 Python 中，0 始终为 False，1 始终为 True。因此，在程序中，与其显式返回 True 或 False，你可以返回 0 或 1，这可以在布尔语境中使用。

我使用了 Python 的函数 `type()` 来查看 Python 为我的变量分配了什么类型。这是一个非常有用的函数，因为在很多情况下（特别是调试时），你无法仅仅通过代码判断变量类型。然而，Python 3.x 使得重新定义变量类型成为可能，尽管在 Python 3.x 中没有必要重新定义类型。Python 2.7 不支持声明变量类型；它是自动完成的。

在“将所有数据类型合并到一个字符串变量”部分，我使用 Python 的函数 `str()` 显式转换了所有变量。正如我之前提到的，字符串拼接不像 Java 那样会自动将其他数据类型转换为字符串。因此，在连接到字符串之前，所有非字符串变量都需要显式转换。

Python 中类型转换的另一个很好的示例是：

```python
a = "5"
b = 2
print(int(a) + b)
```

输出结果为：7

我的 `pythonAnythingTwo.py` 程序的运行应该如图 3.1 所示。

在示例 4.3.1 中，我在给定循环的每次迭代中打印了变量 `x` 的值。在 Python 中，`range(0, 5)` 函数基本上创建一个从 0 到 5 的整数列表，与 Java 的增强型循环格式类似，通过冒号来打印列表中的每一个值。

在示例 4.3.2 中，我创建了一个包含三个值的数组。使用 Java 的增强型循环格式，我打印数组的每一个值并将其赋值给变量 `x`。再次，Python 的增强型循环格式与 Java 非常相似。在 Java 中，值被大括号包围，而在 Python 中，冒号替换了大括号。在 Java 中，使用一对大括号来定义代码块，而在 Python 中，在循环头之后添加冒号，并通过额外的缩进来指定循环内要执行的内容。

注意，Python 的循环语法略有不同。在 Java 中，循环值被大括号包围，而在 Python 中则是方括号。我将介绍关于 Python 数组的细节。

在示例 4.3.3 中，我使用了循环来打印字符串的每一个字符。Python 将所有字符串视为数组，因此使用相同的方法进行迭代：

### 示例 4.3.4

```python
for letter in "anyWord":
    print letter
```

示例 4.3.4 展示了如何手动将 `anyWord` 字符串拆分为一个字母数组。在示例 4.3.5 中，我使用了循环引用 `letterArray`，这与 Java 是一样的：

### 示例 4.3.5

```python
letterArray = ["a", "n", "y", "W", "o", "r"]
for letter in letterArray:
    print letter
```

## 4.4 continue 语句



现在 `continue` 语句在 Python 中变得有点复杂。在 Java 中，你被允许标记循环并使用 `continue` 语句从一个循环跳转到另一个嵌套循环。在 Python 中，这理论上是不可能的。`continue` 语句只会带你回到循环的顶部。示例 4.4 展示了 Python 中 `continue` 语句的情况：

### 示例 4.4

Java:

```java
int b = 10;
for (int number = 0; number < b; number++) {
    if (number == 8) {
        continue;
    }
    System.out.println(number);
}
```

Python:

```python
b = 10
for number in range(b):
    if number == 8:
        continue
    print(number)
```

总结，示例 4.4 会打印 0 到 9，但会跳过 8。这是因为 `continue` 语句会让程序回到循环开头，而不执行语句下方的代码。

## 4.5 pass 语句

Python 有一个额外的语句 `pass` 语句，这在 Java 中是不存在的，但它很容易理解，因为它自其明。在 Java 中，你可以简单创建一个空方法，以后再完成。你可以留在那里，知道它不会影响你的程序。但在 Python 中，如果类中有一个空方法，程序将无法运行。因此引入了 `pass` 语句。它允许你在程序内部创建一个空方法——一个空语句或空循环。示例 4.5 展示了如何实现这一点。

### 示例 4.5

Python:

```python
class MyPythonClass:
    def methodOne(self):
        pass

    def methodTwo(self):
        b = 10
        for number in range(b):
            if number == 8:
                pass
            print(number)
        while b == 10:
            pass
```

## 4.6 while 循环语句

`while` 循环的概念是 Java 和 Python 另一个相似点。`while` 循环有一个布尔条件。当该条件为真时，`while` 循环内部的代码会被执行。当布尔条件为假时，`while` 循环停止并进入程序的下一步。

### 示例 4.6.1

Java:

```java
int a = 1;
int b = 10;
while (a < b) {
    System.out.println("a is smaller than b");
}
```

Python:

```python
a = 1
b = 10
while a < b:
    print("a is smaller than b")
```

如果需要创建一个无限循环，示例 4.6.2 展示了在 Python 中具体的实现方式。

### 示例 4.6.2

Java:

```java
while (true) {
    System.out.println("running infinitely");
}
```

Python:

```python
while True:
    print("running infinitely")
```

## 4.7 do-while 循环语句

`do-while` 循环在 Python 中不存在。然而，由于我正在逐步探索并发现如何在 Python 中模拟 Java 的 `do-while` 循环，请看示例 4.7。与 Java 一样，当条件满足时，循环至少执行一次。

### 示例 4.7

Java:

```java
int a = 1;
int b = 10;
do {
    System.out.println("a is smaller than b");
    a++;
} while (a < b);
```

Python:

```python
a = 1
b = 10
while True:
    print("a is smaller than b")
    a += 1
    if not (a < b):
        break
```

## 4.8 switch 语句

与其他语言不同，Python 没有 `switch` 语句。但再次，我发现了一种使用字典在独立方法中构建 `switch` 方法，它可以返回指定键的值。

### 示例 4.8.1

Java:

```java
private String stringSwitch(String argument) {
    String valueOut = "";
    switch (argument) {
        case "OneIn": valueOut = "OneOut";
            break;
        case "TwoIn": valueOut = "TwoOut";
            break;
        case "ThreeIn": valueOut = "ThreeOut";
            break;
        case "FourIn": valueOut = "FourOut";
            break;
        default: valueOut = "Invalid Value";
            break;
    }
    return valueOut;
}
```

Python:

```python
def __stringSwitch(argument):
    return {
        "OneIn": "OneOut",
        "TwoIn": "TwoOut",
        "ThreeIn": "ThreeOut",
        "FourIn": "FourOut",
    }.get(argument, "Invalid Value")
```

### 示例 4.8.2

Java:

```java
private String integerSwitch(int argument) {
    String valueOut = "";
    switch (argument) {
        case 1: valueOut = "One";
            break;
        case 2: valueOut = "Two";
            break;
        case 3: valueOut = "Three";
            break;
        case 4: valueOut = "Four";
            break;
        default: valueOut = "Invalid Value";
            break;
    }
    return valueOut;
}
```

Python:

```python
def __integerSwitch(argument):
    return {
        1: "One",
        2: "Two",
        3: "Three",
        4: "Four",
    }.get(argument, "Invalid Value")
```

```python
array = ["one", "two", "three"]
for value in array:
    print(value)
```

```python
for letter in "anyWord":
    print(letter)
```

```python
def __stringSwitch(self, argument):
    return {
        "OneIn": "OneOut",
        "TwoIn": "TwoOut",
        "ThreeIn": "ThreeOut",
        "FourIn": "FourOut",
    }[argument]
```

```python
def __integerSwitch(self, argument):
    return {
        1: "One",
        2: "Two",
        3: "Three",
        4: "Four",
    }[argument]
```

```bash
python_programs - bash - 82x21
bash
ishishnevskiyffacBookPro:python_programs ivishnevskiy$ python pythonanythingThree.py
X is smaller than Y
0
1
2
3
4
one
two
three
a
y
wo
or
d
Two00t
Three
ishishnevskiyffacBookPro:python_programs ivishnevskiy$|
```

图 4.1

在后续章节中，我将不再展示代码结果截图。但我鼓励你运行每个示例，并亲眼观察它们是如何工作的。自己尝试一下，就像我目前所做的那样，你会发现自己学会 Python 有多快。

## 5. 运算符

## 5.1 基本算术运算符

Java 和 Python 中的基本算术运算符大部分是相同的。我会尽量保持这个章节简短，只描述少数几个差异。

表格 5.1.1

| 运算符 | 结果 |
| --- | --- |
| `+` | 加法 |
| `-` | 减法 |
| `*` | 乘法 |
| `/` | 除法 |
| `%` | 取模 |
| `+=` | 加法赋值 |
| `-=` | 减法赋值 |
| `*=` | 乘法赋值 |
| `/=` | 除法赋值 |
| `%=` | 取模赋值 |

Python 不支持 Java 中那种格式的自增和自减：

```
x++
++x
x--
--x
```

相反，在 Python 中你可以使用以下方式进行自增和自减：

```python
x += 1
x -= 1
```

## 5.2 关系和逻辑运算符

表格 5.2.1

| 运算符 | 结果 |
| --- | --- |
| `==` | 等于 |
| `is` | 等于 |
| `!=` | 不等于 |
| `is not` | 不等于 |
| `in` | 包含 |
| `not in` | 不包含 |
| `not` | 布尔非 |
| `and` | 布尔与 |
| `or` | 布尔或 |
| `>` | 大于 |
| `<` | 小于 |
| `>=` | 大于等于 |
| `<=` | 小于等于 |

示例 5.2.1 展示了 Python 中与 Java 不同的某些关系运算符。

### 示例 5.2.1

Java:

```java
String stringOne = "Hello World";
String stringTwo = "Goodbye World";
```

```java
boolean returnValue;
if (stringOne.contains("World")) {
    System.out.println("string contains word World");
} else if (!stringOne.contains("World")) {
    System.out.println("string does not contain word World");
}
```

```java
if (stringOne.equals("Hello World")) {
    System.out.println("String is Hello World");
}
```

```java
if (!stringOne.equals("Hello World")) {
    System.out.println("String is not Hello World");
}
```

```java
if (stringOne.contains("Hello") && stringTwo.contains("Goodbye")) {
    returnValue = true;
}
```

```java
if (stringOne.contains("Hello") || stringTwo.contains("Goodbye")) {
    returnValue = true;
}
```

Python:

```python
stringOne = "Hello World"
stringTwo = "Goodbye World"
if "World" in stringOne:
    print("string contains word World")
elif "World" not in stringOne:
    print("string does not contain word World")
```

```python
if stringOne == "Hello World":
    print("String is Hello World")
```

```python
if stringOne != "Hello World":
    print("String is not Hello World")
```

```python
if "Hello" in stringOne and "Goodbye" in stringTwo:
    returnValue = True
```

```python
if "Hello" in stringOne or "Goodbye" in stringTwo:
    returnValue = True
```

## 5.3 三元运算符

Python 中不存在像 Java 那样的三元（三路）运算符 `?`，但从 Python 2.5 版本开始，可以通过稍微不同的语法来实现三元条件。其概念与 Java 相同。见下面的示例 5.3.1。

### 示例 5.3.1

Java:

```java
int b = 8;
int x = b > 8 ? 4 : 9;
```

Python:

```python
b = 8
x = 4 if b > 8 else 9
```

## 6. 类

与 Java 类似，类是对象的模板。一旦创建，就可以使用类的实例。示例 6.0 展示了 Java 和 Python 的区别。

### 示例 6.0

Java:

```java
class NameOfTheClass {
    String instanceVar = "Hello World";

    public void method() {
        System.out.println(instanceVar);
    }
}
```

Python:

```python
class NameOfTheClass:
    def __init__(self):
        self.instanceVar = "Hello World"

    def method(self):
        print(self.instanceVar)
```

在方法之外但在类头部下定义的变量默认是类变量。在 Java 中，除非声明为 `static`，否则它们是实例变量。

### 示例 6.1

Java:

```java
class NameOfTheClass {
    static String classVar = "Hello World";

    public void method() {
        System.out.println(classVar);
    }
}
```

Python:

```python
class NameOfTheClass:
    classVar = "Hello World"

    def method(self):
        print(self.classVar)
```

## 6.2 局部变量

在 Java 中，局部变量只能在定义的方法内部访问。在其他方法中访问是实例变量的任务。

在 Python 中，局部变量也是方法内部定义的变量。局部变量可以像在 Java 中一样工作，仅在定义它的的方法内部访问，或者通过在任何局部变量名前加上 `self` 可以在给定类内的所有方法之间访问。

### 示例 6.2.1

Java:

```java
class NameOfTheClass {
    public String instanceVar = "Hello Universe";

    public void nameOfTheMethodOne() {
        System.out.println(instanceVar);
    }

    public void nameOfTheMethodTwo() {
        System.out.println(instanceVar);
    }
}
```

Python:

```python
class NameOfTheClass:
    def __init__(self):
        self.localVar = "Hello Universe"

    def nameOfTheMethodOne(self):
        print(self.localVar)

    def nameOfTheMethodTwo(self):
        print(self.localVar)
```

```python
def nameOfTheMethodOne(self):
    print(localVar)
```

```python
def nameOfTheMethodTwo(self):
    print(localVar)
```

显然，`self` 已从变量名中移除，局部变量变成了真正属于其声明方法的局部变量，就像在 Java 中一样。示例 6.2.2 演示了这一点。

### 示例 6.2.2

Java:



## 6.3 类的方法

方法可以从类的外部访问，也可以从它们所在的类内部访问。

如果你注意到了，在示例 6.2.1 和 6.2.2 中，Python 的方法将 `self` 指定为参数。这是是有意为之。要让一个给方法成为类的成员，你必须将 `self` 作为该方法的第一个参数传递。要从同一类内部的其他方法访问任何方法，你必须在方法名称之前指定 `self`。Python 的 `self.` 行为非常像 Java 中的这种方式。

### 示例 6.3.1

Java:

```java
class NameOfTheClass {

    public void nameOfTestMethodOne() {
        String trulyLocalVar = "Hello Universe";
        System.out.println(trulyLocalVar);
    }

    public void nameOfTestMethodTwo() {
        nameOfTestMethodOne();
    }
}
```

Python:

```python
class NameOfTheClass():

    def nameOfTestMethodOne(self):
        trulyLocalVar = "Hello Universe"
        print(trulyLocalVar)
```

```python
def nameOfTestMethodTwo(self):
    self.nameOfTestMethodOne()
```

方法也可以通过类的实例从另一个类内部进行访问，这与 Java 中的做法类似。示例 6.3.2 演示了 Java 和 Python 之间的这些之处：

### 示例 6.3.2

Java:

```java
class NameOfTheClass {
    public void nameOfTheMethod() {
        System.out.println("Hello World");
    }
}

class SomeOtherClass {
    public void someOtherMethod() {
        NameOfTheClass instanceOfTheClass = new NameOfTheClass();
        instanceOfTheClass.nameOfTheMethod();
    }
}
```

Python:

```python
class NameOfTheClass:
    def nameOfTheMethod(self):
        print("Hello World")

class SomeOtherClass:
    def someOtherMethod(self):
        instanceOfClassOne = NameOfTheClass()
        instanceOfClassOne.nameOfTheMethod()
```

## 6.4 构造函数

有时程序在创建对象时需要向类传递一些值。在 Java 中，构造函数就是为此而设立。Python 没有与 Java 相同的构造函数概念，但有一种使用 Python 的初始化方法（initializer）来模拟它。

Python 中的初始化方法会在类对象初始化时执行其包含的逻辑，因此得名，或者简写为 `__init__()`。初始化方法基本上是类的另一个方法（`def __init__(self):`）：它可以包含任何类中其他方法可以拥有的任何逻辑和或变量。初始化方法和其他任何方法一样，具有接受参数的能力。因为它在创建该类引用的那一刻执行，在您调用该类的任何方法之前，为 `__init__(parameterOne, parameterTwo)` 指定的参数就变成了强制性的。这就是初始化方法在 Python 中开始扮演构造函数的作用。示例 6.4.1 演示了 Java 以及 Python 中构造函数的实现。

### 示例 6.4.1

Java:

```java
class NameOfTheClass {
    String parameterOne;
    int parameterTwo;

    public NameOfTheClass(String parameterOne, int parameterTwo) {
        this.parameterOne = parameterOne;
        this.parameterTwo = parameterTwo;
    }
    public void nameOfMethod() {
        System.out.println(parameterOne);
    }
}

class SomeOtherClass {
    public void someOtherMethod() {
        String argOne = "Hello World";
        int argTwo = 1;
        NameOfTheClass instanceOfTheClass = new NameOfTheClass(argOne, argTwo);
        instanceOfTheClass.nameOfMethod();
    }
}
```

Python:

```python
class NameOfTheClass:
    def __init__(self, parameterOne, parameterTwo):
        self.parameterOne = parameterOne
        self.parameterTwo = parameterTwo
```

```python
def nameOfTheMethod(self):
    print self.parameterOne
```

```python
class SomeOtherClass():
    def someOtherMethod(self):
        argOne = "Hello World"
        argTwo = 1
        instanceOfClassOne = NameOfTheClass(argOne, argTwo)
        instanceOfClassName.nameOfTheMethod()
```

从示例 6.4.1 中你需要记住两点：

1. `__init__()` 方法可以简单地作为一个给定步骤序列的设置执行器，在继续执行从其所在类中调用的任何方法之前执行该序列。

2. 如果为方法指定了参数，初始化方法就开始在 Python 中扮演构造函数的作用。示例 6.4.1 演示了 Java 以及 Python 中构造函数的实现。

## 6.5 嵌套类

Java 和 Python 都支持嵌套类，只是在语法上略有不同，在 Python 中也可以同样容易地实现。示例 6.5.1 演示了 Java 和 Python 的这些相似之处。

### 示例 6.5.1

Java:

```java
class OuterClass {
    String message = "Our message";

    class InnerClass {
        public String printMessage() {
            return message;
        }
    }

    public static void main(String args[]) {
        OuterClass outerInstance = new OuterClass();
        OuterClass.InnerClass innerInstance = outerInstance.new InnerClass();
        System.out.println(innerInstance.printMessage());
    }
}
```

Python:

```python
class OuterClass:
    message = "Our message"

    class InnerClass:
        def printMessage(self):
            return OuterClass.message

def main():
    outer_instance = OuterClass()
    inner_instance = outer_instance.InnerClass()
    print(inner_instance.printMessage())
```

## 6.6 从方法返回

从方法返回在 Java 和 Python 中是相同的方式。

## 6.7 finalize() 方法

`finalize()` 方法在 Java 中是为了在对象被销毁前执行某些操作而存在的。

### 示例 6.7.1

Java:

```java
class NewClass {
    public String someMethod() {
        String argOne = "Hello World";
        return argOne;
    }

    @Override
    protected void finalize() throws Throwable {
        try {
            // cleanup logic
        } finally {
            super.finalize();
        }
    }
}
```

Python:

```python
class SomeClass():
    def someMethod(self):
        argOne = "Hello World"
        return argOne
```

```python
def __enter__(self):
    return self
```

```python
def __exit__(self, exc_type, exc_val, tb):
    # cleanup logic
    return
```

## 6.8 方法重载

方法重载在 Python 和 Java 中以类似的方式实现。根据给定方法的参数列表和/或参数的数据类型来选择运行哪个方法。在 Python 中，如果你创建了多个同名方法并尝试调用它们，其他方法将抛出异常，说明提供的参数数量与这些方法指定的参数不匹配。基本上，Python 每次都会尝试运行所有同名方法。但仍然有一种重载方法。当为方法指定了参数时，Python 允许为参数设置默认值。一旦设置了默认值，在调用该方法时就不需要提供该参数——它将简单地获取默认值。在方法内部，使用条件语句，可以根据参数设置的值来选择方法应该执行的步骤序列。示例 6.8.1 演示了如何在 Python 中实现类似 Java 的重载。

### 示例 6.8.1

Java:

```java
class SomeClass {
    public void someMethod() {
        System.out.println("Running sequence one");
    }
    public void someMethod(String valueOne) {
        System.out.println("Running sequence two");
    }

    public void someMethod(int valueTwo, Boolean valueTree) {
        System.out.println("Running sequence three");
    }
}
```

Python:

```python
class SomeClass():
    def someMethod(self, valueOne=None, valueTwo=None, valueThree=False):
        if valueOne != None:
            print "Running sequence two"
        elif valueTwo != None and valueThree:
            print "Running sequence three"
        else:
            print "Running sequence one"
```

从上面的示例可以看出，调用 `someMethod()` 不带任何参数、带一个参数或带三个参数都是有效的。示例 6.8.2 展示了通过传递不同的参数集调用 `methodName()` 的变化。

### 示例 6.8.2

Python:

```python
run = SomeClass()
run.someMethod()
run.someMethod("valueOneStr")
run.someMethod(None, "valueTwoStr", True)
```

## 6.9 重载构造函数

与我重载方法的方式非常，我可以重载 Python 的构造函数，我之前提到过它在 Python 中被称为“初始化器”。记得 `__init__()` 方法吗？如果不记得，请参考“6.4 构造函数”章节。

在示例 6.8.1 和 6.8.2 中，我为方法的参数设置了默认值，然后进行了重载。同样，`__init__()` 也是一个方法，因此相同的概念也可以适用于它。在初始化器的 `then` 块中，我使用条件语句来选择程序执行的路径。让我们来看示例 6.9.1，它展示了如何在 Python 中重载初始化器。

### 示例 6.9.1

Python:

```python
class SomeClass():

    def __init__(self, valueOne=None, valueTwo=None, valueThree=False):
        if valueOne != None:
            self.methodTwo()
        elif valueTwo != None and valueThree:
            self.methodThree()
        else:
            self.methodOne()
```

```python
def methodTwo(self):
    print "Running sequence two"
```

```python
def methodThree(self):
    print "Running sequence three"

runOne = SomeClass()
runTwo = SomeClass("valueOneStr")
runThree = SomeClass(None, "valueTwoStr", True)
```

## 6.10 使用对象作为参数

由于在 Python 中我不需要为预期传递给方法的参数指定数据类型，因此我可以将任何数据类型的对象作为参数传递给这些方法。（注意，在之前的大多数示例中，我没有指定对象的类型类型，无论它是什么。）

下面的示例演示了如何将 `NameOfClass()` 类的对象作为参数，从 `SomeOtherClass()` 类中的 `someOtherMethod(self):` 方法传递到 `someMethodTwo(self, objectAsParameter)` 方法，其中我使用传递的对象调用了 `NameOfTheClass` 类中的 `nameOfTheMethod()`。

同样，任何方法都可以返回对象，就像 `someMethodTwo(self, objectAsParameter):` 方法返回对象 `objectAsParameter` 一样。

### 示例 6.10.1

Python:

```python
class NameOfClass():
    def __init__(self, parameterOne, parameterTwo):
        self.parameterOne = parameterOne
        self.parameterTwo = parameterTwo

    def nameOfTheMethod(self):
        print self.parameterOne
```

```python
class SomeOtherClass():
    def someOtherMethod(self):
        argOne = "Hello World"
        argTwo = 1
        instanceOfClass = NameOfClass(argOne, argTwo)
        self.someMethodTwo(instanceOfClass)
```



```python
def someMethodTwo(self, objectAsParameter):
    objectAsParameter.nameOfTheMethod()
    return objectAsParameter
```

## 6.11 递归

Java 和 Python 中的递归具有相同的含义——方法调用自身来重新执行其步骤序列。示例 6.11.1 中的代码如果运行将无限循环。因此，它不是现实生活中递归实用的最佳案例，但它展示了 Java 和 Python 中方法调用自身的相似技术。

### 示例 6.11.1

```java
public class SomeClass {
    public void someMethod() {
        someMethod();
    }
}
```

```python
class SomeClass:
    def someMethod(self):
        self.someMethod()
```

## 6.12 访问控制

还记得吗，公共的 getter 和 setter 可以访问其类的私有方法和/或变量？Python 也支持相同的概念，允许我将某些易感的方法设置为私有，仅允许其所在类中的其他方法访问。在 Java 中，你在声明私有方法时需要在方法头显式输入 `private`，在声明公共方法时输入 `public`。在 Python 中，默认情况下所有方法都是公共的。要创建一个私有方法，你需要在方法名之前添加两个下划线，如下示例 6.12.1 所示。

### 示例 6.12.1

```java
public class SomeClass {
    public void firstMethod() {
        System.out.println("Hello public method");
    }
    private void secondMethod() {
        System.out.println("Hello private method");
    }
    public void thirdMethod() {
        //Calling public method:
        firstMethod();
        //Calling private method:
        secondMethod();
    }
}
```

```python
class SomeClass:
    def firstMethod(self):
        print("Hello public method")

    def __secondMethod(self):
        print("Hello private method")

    def thirdMethod(self):
        # Calling public method:
        firstMethod()
        # Calling private method:
        self.__secondMethod()
```

## 6.13 静态方法

静态方法在 Java 和 Python 中的作用是相同的。然而，语法是不同的。在 Java 中，你使用 `static` 关键字。在 Python 中，你使用 `@staticmethod` 装饰器。示例 6.13.1 展示了这些差异。

### 示例 6.13.1

```java
public class StaticExample {
    public static void someMethod() {
        System.out.println("Static method");
    }
}
```

```python
class StaticExample:
    @staticmethod
    def someMethod():
        print("Static method")
```

```python
class VarArgsExample:
    def methodName(*varName):
        for counter, element in enumerate(varName):
            print("Argument" + str(counter) + ": " + element)
```

## 6.17 继承

与 Java 一样，Python 允许继承彼此的属性。一个主要的区别是，在 Java 中，一个类在同一时间只能扩展另一个类，而 Python 消除了这一限制，允许一个类扩展多个其他类，一次性继承多个类的属性。下面的示例 6.17.1 阐述了这种差异。

### 示例 6.17.1

```java
class MainClass {
    public static void main(String[] args) {
        SomeClass scRef = new SomeClass();
        scRef.someMethod();
    }
}
```

```java
class SomeClass {
    public void someMethod() {
        System.out.println("Inside SomeClass");
    }
}
```

```java
class SomeOtherClass extends SomeClass {
    public void someMethod() {
        System.out.println("Inside SomeOtherClass");
    }
}
```

```python
class MainClass:
    def __init__(self):
        scRef = SomeClass()
        scRef.someMethod()
        scRef.methodOfClass()
```

```python
class SomeClass:
    def someMethod(self):
        print("Inside Some Class")

    def methodOfClass(self):
        print("Method of SomeClass")
```

```python
class ThirdClass:
    def methodOfThirdClass(self):
        print("Extended this one too")
```

```python
class SomeOtherClass(SomeClass, ThirdClass):
    def someOtherMethod(self):
        print("Inside SomeOtherClass")
```

如示例 6.17.1 所示，在 Python 中，类 `SomeOtherClass` 扩展了类 `SomeClass`。虽然这与 Java 中的继承相同，但在 Python 示例中，我额外添加了一个类 `ThirdClass`，它也被 `SomeOtherClass` 扩展了。这演示了在 Python 中如何扩展多个类，这在 Java 中是不可能的。

同样，与 Java 一样，只有公共方法可以被继承。在 Java 中声明一个方法为公共时，我显式地将该方法指定为 `public`。在 Python 中，方法默认是公有的，因此你完全不需要指定它。但要让方法变为私有，你可以在方法名称前添加双下划线。因此，要使以下方法变为私有：

```python
def printHelloWorld(self):
```

所做的就是在方法名称之前添加两个下划线字符，如下所示。

```python
def __printHelloWorld(self):
```

## 6.18 抽象类

抽象类的作用是蓝图，规定了扩展它的类必须实现哪些方法。抽象类在 Java 和 Python 中都存在。你熟悉在 Java 中是如何做的（那非常直观），但在 Python 中，语法变得稍微复杂一些。

在 Python 中，抽象类是使用 `abc` 模块定义的。该模块必须首先导入到存放抽象类的 `.py` 文件中。然后在类的头部下方，需要指定以下内容以使该类成为抽象类：`metaclass = abc.ABCMeta`。方法通过 `@abstractmethod` 装饰器声明为抽象，该装饰器放置在每个抽象方法的头部上方。Python 装饰器的使用方式与 Java 中注解的使用方式类似。请看示例 6.18.1。

### 示例 6.18.1

```java
abstract class AbstractClass {
    abstract String mustHaveMethod();
}
```

```java
public class SomeOtherClass extends AbstractClass {
    public String mustHaveMethod() {
        System.out.println("mustHaveMethod has been implemented");
        return "String";
    }
}
```

```python
import abc

class AbstractClass(object):
    __metaclass__ = abc.ABCMeta

    @abc.abstractmethod
    def mustHaveMethod(self):
        pass

class SomeOtherClass(AbstractClass):
    def mustHaveMethod(self):
        print("mustHaveMethod has been implemented")
        return "String"
```

## 6.19 导入类

在 Python 中导入类使用 `import` 语句。你可以导入整个模块，也可以从模块中导入特定的类。

```python
import moduleName
from moduleName import ClassName
from moduleName import ClassName as AliasName
```

## 6.21 抛出自定义异常

编程中一种非常常见的做法是针对与你的用例相关的异常情况生成自定义异常。这样，你可以只捕获并处理你特定的异常，而让其他可能发生的异常保持未处理状态。这在 Java 和 Python 中都可以实现。示例 6.21.1 演示了如何在两种语言中创建和抛出自定义异常。

### 示例 6.21.1

```java
class YourCustomException extends Exception {
    public YourCustomException(String errorMessage) {
        super(errorMessage);
    }
}
```

```java
class SomeOtherClass {
    public static void main(String args[]) {
        throw new YourCustomException("Your custom error message.");
    }
}
```

```python
class MyException(Exception):
    def __init__(self, message):
        super(MyException, self).__init__(message)

class SomeOtherClass:
    def __init__(self):
        raise MyException("Your custom error message.")
```

## 6.22 @装饰器不是 @注解

Python 有一种外观上与 Java 注解非常类似的替代品。Java 中的注解用于替换基于 XML 的元数据文件，这些文件以前用于保存元数据并在 Java 程序的运行时访问它们。在 Python 中，看起来像注解的东西被称为装饰器。装饰器也指定在它们所属的方法头上方，并且前面有一个 `@` 符号以示区别。它们的目的与 Java 中的注解略有不同。简而言，Python 允许你将函数作为参数传递给其他函数。就像你将变量作为参数传递给方法/函数一样，你也可以传递函数本身。装饰器基本上是告诉被装饰的函数作为参数传递给装饰器函数。

在示例 6.22.1 中，我将函数命名为 `decoratorFunctionName` 和 `decoratedFunctionName` 以区分两者。第一个 `decoratorFunctionName()` 内部有一个嵌套函数 `innerFunctionName`。不要问我为什么；这就是语法。它获取 `decoratedFunctionName()` 返回的值（在这种情况下是 3000），对其加 1 并返回更新后的结果。`decoratorFunctionName()` 返回 `innerFunctionName()` 返回的值。注意，在 `decoratorFunctionName()` 的返回语句中，我只使用了 `innerFunctionName` 的名称，没有加末尾的括号 `()`，因为会导致异常。接下来，`decoratedFunctionName()` 获取 `decoratorFunctionName()` 返回的值，并将其放在变量 `x` 的位置。随后，`print` 语句将该更新后的值输出到控制台。

还要注意，`@` 符号旁名称与装饰器函数的名称完全相同：`decoratorFunctionName() = @decoratorFunctionName`。

请看示例 6.22.1 中装饰器在 Python 中是如何实现的。

### 示例 6.22.1

```python
def decoratorFunctionName(decoratedFunctionName):
    def innerFunctionName():
        x = decoratedFunctionName()
        return x + 1
    return innerFunctionName

@decoratorFunctionName
def decoratedFunctionName():
    return 3000

print(decoratedFunctionName())
```

```python
class SomeOtherClass:
    def someOtherMethod(self):
        instanceOfClassOne = NameOfClassName()

        try:
            instanceOfClassOne.nameOfMethod()
        except Exception as e:
            print("Exception caught")
            print(e)
```



```python
def decoratorFunctionName(decoratedFunctionAsArg):
    def innerFunction():
        result = decoratedFunctionPassedAsArgument() + 1
        return result
    return innerFunction

@decoratorFunctionName
def decoratedFunctionName(x=3000):
    return x

print decoratedFunctionName()
```

注意，在示例 6.23.1 中，我有两个函数在类外部运行。现在让我们看看示例 6.23.2，它展示了如果我的代码封装在一个类中，装饰器是如何实现和使用的。

### 示例 6.23.2

Python:

```python
class SomeClass():
    def decoratorFunctionName(decoratedFunctionAsArg):
        def innerFunction(self):
            result = decoratedFunctionPassedAsArgument(self) + 1
            return result
        return innerFunction

    @decoratorFunctionName
    def decoratedFunctionFunctionName(self, x=3000):
        return x

run = SomeClass()
print(run.decoratedFunctionName())
```

## 7. 数据结构

### 7.1 数组

在 Java 中，数组是固定长度的，但在 Python 中，被称为“列表”（list）的数组作用更像 Java 中的 `ArrayList`。它可以动态地增加或减少大小。另一个区别是，在 Java 中，数组必须使用设置的数据初始化，但在 Python 中，它可以包含一种或混合任意数据类型，甚至是子列表或其他集合类型，我将在后续章节中讨论。示例 7.1.1 和 7.1.2 比较了 Java 的数组结构与 Python 的列表。

#### 示例 7.1.1

Java:

```java
int[] array = new int[5];
array[0] = 123;
array[1] = 321;
array[2] = 999;
array[3] = 764;
array[4] = 987;
```

Python:

```python
array = []
array.append(123)
array.append(321)
array.append(999)
array.append(764)
array.append(987)
```

#### 示例 7.1.2

Java:

```java
int[] array = { 123, 321, 999, 764, 987 };
```

Python:

```python
array = [123, 321, 999, 764, 987];
```

### 7.2 访问数组中的值

Java 和 Python 中访问数组中值的方式相同，甚至在语法上也是。

#### 示例 7.2.1

Java:

```java
int[] array = { 123, 321, 999, 764, 987 };
System.out.print(array[3]);
```

Python:

```python
array = [123, 321, 999, 764, 987]
print array[3];
```

### 7.3 更新数组中的值

Java 和 Python 更新数组中值的方式也几乎相同。

#### 示例 7.3.1

Java:

```java
int[] array = { 123, 321, 999, 764, 987 };
array[3] = 444;
```

Python:

```python
array = [123, 321, 999, 764, 987]
array[3] = 444
```

### 7.4 获取数组的大小

在 Python 中获取数组的大小是通过 `len()` 函数实现的。在 Java 中，则是获取数组的长度。

#### 示例 7.4.1

Java:

```java
int[] array = { 123, 321, 999, 764, 987 };
System.out.print(array.length);
```

Python:

```python
array = [123, 321, 999, 764, 987]
print len(array)
```

### 7.5 数组排序

在 Python 中排序数组的过程与 Java 相似。除了语法上的细微差别外，大部分是相同的。示例 7.5.1 演示了如何在 Java 和 Python 中进行升序和降序排序。

#### 示例 7.5.1

Java:

```java
int[] array = { 123, 321, 999, 764, 987 };
//升序排序
Arrays.sort(array);
//降序排序
Arrays.sort(array, Collections.reverseOrder());
```

Python:

```python
array = [123, 321, 999, 764, 987]
#升序排序
array.sort()
#降序排序
array.sort(reverse=True)
```

### 7.6 计数数组中的值

在 Python 中计数数组元素的出现次数要简单得多。在 Java 中，计数给定数组元素出现的最简单方法是通过循环对每个元素进行条件比较来实现的。Python 则有一个专门的函数：`count()`。让我们在示例 7.6.1 中查看该函数的实际用法。

#### 示例 7.6.1

Java:

```java
int[] array = { 123, 321, 999, 764, 987 };
int count = 0;
int value = 999;
for (int i = 0; i < array.length; i++) {
  if (array[i] == value) {
    count++;
  }
}
```

Python:

```python
array = [123, 321, 999, 764, 987]
count = array.count(999)
```

### 7.7 在数组的特定索引处插入值

假设我有一个五个元素的数组。我想在索引 3 处插入一个值。如果我只想更新索引 3 的值，可以使用 7.3 节（更新数组中的值）中描述的方法。然而，我已经在索引 3 处有一个值并想保留它，示例 7.7.1 演示如何在索引 3 处添加新值并将数组中的所有现有值向右移动一位。

#### 示例 7.7.1

Java:

```java
Integer array[] = { 123, 321, 999, 764, 987 };
ArrayList<Integer> list = new ArrayList<Integer>(Arrays.asList(array));
list.add(3, 555);
```

Python:

```python
array = [123, 321, 999, 764, 987]
array.insert(3, 555)
```

在给定的 Python 列表中返回所需值的索引非常简单。示例 7.8.1 就不言自明，并演示了这一点。

### 7.8 返回数组中值的索引

#### 示例 7.8.1

Java:

```java
int array[] = { 123, 321, 999, 764, 987 };
Arrays.asList(array).indexOf(321);
```

Python:

```python
array = [123, 321, 999, 764, 987]
array.index(321)
```

### 7.9 数组添加（Appending）与扩展（Extending）的区别

在这里我介绍了一个在 Java 的任何数据类型中都不存在的功能。正如我之前提到的，在 Python 中，数组可以包含任何数据类型，甚至是列表。我们将初始数组称为“父列表”，将我想要添加的列表元素称为“子列表”。子列表可以被添加（append）或扩展（extend）到父列表中。如果是 `append`，子列表将作为一个整体列表元素被添加，或者说，作为父列表的一个“子列表”。如果是 `extend`，子列表将被拆分为它的各个值，并且每个值将被分别单独添加到父列表中，从而使每个值都成为父列表的独立元素。这在示例 7.9.1 中得到了说明。由于此功能是 Python 特有的，该示例将仅包含 Python 代码样本。

#### 示例 7.9.1

Python:

```python
parentList = [123, 321, 999, 764, 987]
childList = [2, 4, 6, 2, 8]
parentList.append(childList)
#parentList 将看起来像这样: [123, 321, 999, 764, 987, [2, 4, 6, 2, 8]]
```

```python
parentList = [123, 321, 999, 764, 987]
childList = [2, 4, 6, 2, 8]
parentList.extend(childList)
#parentList 将看起来像这样: [123, 321, 999, 764, 987, 2, 4, 6, 2, 8]
```

### 7.10 通过索引从数组删除元素

在 Java 中，对于复杂的数组操作，你甚至不会使用普通数组。相反，你会使用 `ArrayList`。然而在 Python 中，有一种列表可以充当你在数组中需要的所有功能。在示例 7.10.1 中，我首先将 Java 中的普通整数转换为 `ArrayList`，然后通过索引从 `ArrayList` 中删除项。在 Python 中，通过索引删除元素的函数名称与 Java 相同，名为 `remove()`。

#### 示例 7.10.1

Java:

```java
int[] array = { 123, 321, 999, 764, 987 };
ArrayList<Integer> arraylist = new ArrayList<Integer>(Arrays.asList(array));
arraylist.remove(2);
```

Python:

```python
array = [123, 321, 999, 764, 987]
array.remove(2)
```

Python 还提供了另一种通过索引从数组删除值的方法，如示例 7.10.2 所示。

#### 示例 7.10.2

Python:

```python
array = [123, 321, 999, 764, 987]
del array[2]
```

两种方法都能达到效果。使用 `del` 或 `remove()` 会从数组（在 Python 中称为列表）中删除指定的元素。

### 7.11 Python 列表可以包含任何内容

在 Java 中，数组被限制为包含一种特定数据类型的元素。例如，字符串数组只能包含字符串。整数数组只能包含整数。然而在 Python 中，数组可以自由地包含任何支持的数据类型的组合，甚至是列表、元组和字典。示例 7.11.1 演示了一个包含多种数据类型值的有效 Python 列表。

#### 示例 7.11.1

Python:

```python
array = [123, 2, 4, 6, 2, 8], "testString", {"key": "value", "key": "value"}, ("testStringTwo", 123)
```

在上面的示例中，我的数组的第一个元素是整数，第二个是整数列表，第三个是字符串，第四个是字典，第五个是元组。这个数组在 Python 中完全有效。

### 7.12 多维数组

Python 也支持多维数组，尽管在 Python 中处理它们可能比在 Java 中更令人困惑。在 Python 中无法像使用空列表那样简单地创建一个多维数组。在 Python 中，你需要先使用列表推导式创建一个多维数组，我将在本章下一节（7.13）中讨论。当创建一个用默认整数值填充每个行和每列组合的数组时，可以使用嵌套循环来替换这些默认（或任何选定的默认）值。示例 7.12.1 将 Java 的二维数组转换为 Python 的二维列表。

#### 示例 7.12.1

Java:

```java
String[][] twoDimensionalArray = new String[6][5];
for (int counter = 0; counter < 6; counter++) {
    for (int innerCounter = 0; innerCounter < 5; innerCounter++) {
        twoDimensionalArray[counter][innerCounter] = "value";
    }
}
```

Python:

```python
twoDimensionalArray = [[0 for innerCounter in range(5)] for counter in range(6)]
for counter in range(6):
    for innerCounter in range(5):
        twoDimensionalArray[counter][innerCounter] = "value";
```

### 7.13 列表推导式

列表推导式是 Python 数据结构中一个很酷的功能，Java 中并不存在。这个概念非常容易理解。它基本上是使用单行代码在 Python 中构建一个值数组的方法。起初可能会很困惑，但通过练习，你会发现在 Python 中构建数组比在 Java 中简单得多。示例 7.13.1 比较了两者。

#### 示例 7.13.1

Python:

```python
squares = [x**2 for x in range(10)]
### squares 是 [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

Java:

```java
HashMap<Integer, String> dictionary = new HashMap<Integer, String>();
dictionary.put(1, "One");
System.out.println(dictionary.get(1));
dictionary.put(1, "UpdatedOne");
System.out.println(dictionary.get(1));
```

Python:

```python
dictionary = {1 : "One", 2 : "Two", 3 : "Three"}
print(dictionary[1])
dictionary[1] = "UpdatedOne"
print(dictionary[1])
```

## 7.17 向现有字典添加新条目

在 Python 字典中添加新的键值对与更新 Python 列表中的值相似，你提供的不是索引，而是提供一个新的键，并为其分配一个新值。请参考示例 7.17.1。

#### 示例 7.17.1

Java:

```java
HashMap<Integer, String> dictionary = new HashMap<Integer, String>();
dictionary.put(1, "One");
dictionary.put(2, "Two");
dictionary.put(3, "Three");
System.out.println(dictionary.get(1));
dictionary.put(4, "Four");
System.out.println(dictionary.get(4));
```

Python:

```python
dictionary = {1 : "One", 2 : "Two", 3 : "Three"}
print(dictionary[1])
dictionary[4] = "Four"
print(dictionary[4])
```

## 7.18 清空字典（移除其所有值）

清空 Java map 和 Python 字典使用的是完全相同的步骤。两种语言都提供了 `clear()` 方法，它可以从给定的字典数据结构中删除所有的键值对。示例 7.18.1 展示了在两种语言中如何操作。

#### 示例 7.18.1

Java:

```java
HashMap<Integer, String> dictionary = new HashMap<Integer, String>();
dictionary.put(1, "One");
dictionary.put(2, "Two");
dictionary.put(3, "Three");
dictionary.clear();
```

Python:

```python
dictionary = {1 : "One", 2 : "Two", 3 : "Three"}
dictionary.clear()
```

## 7.19 删除整个字典

与 Java 相比，Python 删除整个字典需要不同的过程。在 Java 中，你通常会给 map 对象赋一个 `null` 值，垃圾回收器会识别并移除它；而在 Python 中，`del` 函数将删除整个字典对象。请参考示例 7.19.1。

#### 示例 7.19.1

Java:

```java
HashMap<Integer, String> dictionary = new HashMap<Integer, String>();
dictionary = null;
```

Python:



```python
dictionary = {1 : "One", 2 : "Two", 3 : "Three"}
del dictionary
```

## 7.20 获取字典的大小

字典的大小是通过与获取数组大小完全相同的 Python 函数返回的（见 7.4 获取数组的大小）：`len()`。示例 7.20.1 展示了如何计算 Python 字典的大小。

### 示例 7.20.1

#### Java:

```java
HashMap<Integer, String> dictionary = new HashMap<Integer, String>();
dictionary.put(1, "One");
dictionary.put(2, "Two");
dictionary.put(3, "Three");
dictionary.size();
```

#### Python:

```python
dictionary = {1 : "One", 2 : "Two", 3 : "Three"}
len(dictionary)
```

## 7.21 获取字典的键和值

有三种方法可以获取给定字典中所有的键和值的列表（分开或合并）。

1. `dictionary.items()` 返回给定字典的 (键, 值) 对列表。
2. `dictionary.keys()` 返回给定字典的所有键的列表。
3. `dictionary.values()` 返回给定字典的所有值的列表。

示例 7.21.1 展示了这三种方法在 Java 和 Python 中的实际应用情况。

### 示例 7.21.1

#### Java:

```java
HashMap<Integer, String> dictionary = new HashMap<Integer, String>();
dictionary.put(1, "One");
dictionary.put(2, "Two");
dictionary.put(3, "Three");
dictionary.entrySet();
dictionary.keySet();
dictionary.values();
```

#### Python:

```python
dictionary = {1 : "One", 2 : "Two", 3 : "Three"}
dictionary.items()
dictionary.keys()
dictionary.values()
```

## 7.22 Python 字典对比 JSON

你现在可能已经注意到 Python 字典的格式与 JSON 格式非常相似。你是正确的。在接下来的示例中，我创建了一个字典，然后将其转换为字符串，接着如果你将该字符串保存为名为 `filename.json` 的文本文件，你基本上就得到了 JSON 文件。现在，Python 中有一个 JSON 库，专门用于处理 JSON 格式的数据，示例 7.22.1 展示了另一个同样实用的技巧。

尽管 Python 字典在格式上与 JSON 相似，但两者并非完全相同。例如，区别之一是[JSON 中的键必须是字符串，而在 Python 中，它们可以是任何可哈希类型]。

```python
return 0
else:
    objectToReturn = self__stack[len(self__stack) - 1]
    self__stack.pop(len(self__stack) - 1)
    return objectToReturn
```

```python
def peek(self):
    return self__stack[len(self__stack) - 1]
```

```python
def search(self, object):
    return self__stack.index(object)
```

```python
def size(self):
    return len(self__stack)
```

## 7.26 队列

队列是一个非常有用的数据结构，不仅在 Java 中是，在 Python 中也是。我经常使用它，并将在下面的示例 7.26.1 中包含我的队列数据结构实现。队列的规则？先进先出。

### 示例 7.26.1

#### Python:

```python
class Queue:
    def __init__(self):
        self__queue = []
```

```python
def isEmpty(self):
    return len(self__queue) == 0
```

```python
def push(self, object):
    self__queue.append(object)
```

```python
def pop(self):
    if self.isEmpty():
        return 0
    else:
        objectToReturn = self.__queue[0]
        self.__queue.pop(0)
        return objectToReturn
```

```python
def peek(self):
    return self.__queue[0]
```

```python
def search(self, object):
    return self.__queue.index(object)
```

```python
def size(self):
    return len(self__queue)
```

## 7.27 链表

相比栈或队列数据结构，链表的功能稍微更多。链表有两种形式：单向链表和双向链表。在下面的示例 7.27.1 中，我展示了我用 Python 实现的单向链表，这跨越了材料的五页。示例涵盖了单向链表大部分的重要特性。

### 示例 7.27.1

#### Python:

# 链表实现开始。

```python
class Node():
    def __init__(self, data, next):
        self.data = data
        self.next = next
```

```python
def getData(self):
    return self.data
```

```python
def setData(self, value):
    self.data = value
```

```python
def getNext(self):
    return self.next
```

```python
def setNext(self, newNext):
    self.next = newNext
```

```python
class SinglyLinkedList():
    def __init__(self):
        self.head = None
        self.tail = None
        self.currentSize = 0
```

```python
def add(self, value):
    if(self.isEmpty()):
        self.head = Node(value, None)
        self.tail = self.head
    else:
        self.tail.setNext(Node(value, None))
        self.tail = self.tail.getNext()
    self.currentSize += 1
    return True
```

```python
def isEmpty(self):
    return self.size() == 0
```

```python
def size(self):
    return self.currentSize

def get(self, index):
    if index < 0 or index >= self.currentSize:
        raise IndexError

    if index < self.currentSize - 1:
        current = self.head
        for i in xrange(index):
            current = current.getNext()
            return current.getData()
    return self.tail.getData()
```

```python
def clear(self):
    self.head = None
    self.tail = None
    self.currentSize = 0
```

```python
def removeByIndex(self, index):
    if index < 0 or index >= self.currentSize:
        raise IndexError

    current = self.head
    for i in xrange(0, self.size()-1):
        last = current
        current = current.getNext()
    if i >= index and i < self.size():
        last.setData(current.getData())
    self.tail = last
    self.currentSize -= 1
    return True
```

```python
# 如果元素的一部分包含
# 提供的值，则删除该元素。
def removeValueContains(self, value):
    current = self.head
    for i in range(0, self.size()-1):
        last = current
        current = current.getNext()
        if str(last.getData()).lower().__contains__(str(value).lower()):
            for j in range(i, self.size()-1):
                last.setData(current.getData())
                last = current
                current = current.getNext()
            self.tail = last
            self.currentSize -= 1
            return True
    raise ValueNotFound
    return False
```

```python
# 如果元素等于
# 提供的值。精确匹配。
def removeValueEquals(self, value):
    current = self.head
    for i in range(0, self.size()-1):
        last = current
        current = current.getNext()
        if last.getData() == value:
            for j in range(i, self.size()-1):
                last.setData(current.getData())
                last = current
                current = current.getNext()
            self.tail = last
            self.currentSize -= 1
            return True
```

```python
node.setRightChild(nodeToAddTo)
node.getRightChild().setParent(node)
else:
    self__traverseAndAdd(node.getRightChild(), nodeToAdd)
```

```python
def remove(self, value):
    if self.root != None:
        node = self.findNode(value)
    else:
        return None
    parentNode = node.getParent()
    if node.getLeftChild() != None and node.getRightChild() != None:
        if node.getData() < parentNode.getData():
            parentNode.setLeftChild(node.getRightChild())
            self__traverseAndAdd(self.root, node.getLeftChild())
    else:
        parentNode.setRightChild(node.getLeftChild())
        self__traverseAndAdd(self.root, node.getRightChild())
    elif node.getLeftChild() != None and node.getRightChild() == None:
        if node.getData() < parentNode.getData():
            parentNode.setLeftChild(node.getLeftChild())
        else:
            parentNode.setRightChild(node.getLeftChild())
    elif node.getLeftChild() == None and node.getRightChild() != None:
        if node.getData() < parentNode.getData():
            parentNode.setLeftChild(node.getRightChild())
        else:
            parentNode.setRightChild(node.getRightChild())
    elif node.getLeftChild() == None and node.getRightChild() == None:
        if node.getData() < parentNode.getData(None):
            parentNode.setLeftChild(None)
        else:
            parentNode.setRightChild(None)
```

```python
def findNode(self, value):
    if self.root != None:
        self__getNodeTraversal(self.root, value)
    else:
        return None
    returnNodeObj = self.__findNodeObj
    self.__findNodeObj = None
    print returnNodeObj.getData()
    return returnNodeObj
```

```python
def __getNodeTraversal(self, node, value):
    if node != None:
        if node.getData() == value:
            self.__findNodeObj = node
            self.__getNodeTraversal(node.getLeftChild(), value)
            self.__getNodeTraversal(node.getRightChild(), value)
```

```python
def contains(self, value):
    if self.root != None:
        self.__containsTraversal(self.root)
    returnBool = self.__containsBool
    self.__containsBool = False
    print returnBool
    return returnBool
```

```python
def __containsTraversal(self, node, value):
    if node != None:
        if node.getData() == value:
            self.__containsBool = True
            self.__containsTraversal(node.getLeftChild(), value)
            self.__containsTraversal(node.getRightChild(), value)
```



# 树的遍历与转换实现

```python
def traverse(self, traversalType):
    if self.root != None:
        if traversalType.replace(" ", "").lower() == "preorder":
            self.__preOrderTraversal(self.root)
        elif traversalType.replace(" ", "").lower() == "inorder":
            self.__inOrderTraversal(self.root)
        elif traversalType.replace(" ", "").lower() == "postorder":
            self.__postOrderTraversal(self.root)
```

```python
def __preOrderTraverse(self, node):
    if node != None:
        print node.getData()
        self.__preOrderTraverse(node.getLeftChild())
        self.__preOrderTraverse(node.getRightChild())
```

```python
def __inOrderTraverse(self, node):
    if node != None:
        self.__inOrderTraverse(node.getLeftChild())
        print node.getData()
        self.__inOrderTraverse(node.getRightChild())
```

```python
def __postOrderTraverse(self, node):
    if node != None:
        self.__postOrderTraverse(node.getLeftChild())
        self.__postOrderTraverse(node.getRightChild())
        print node.getData()
```

```python
def toList(self):
    if self.root != None:
        self.__toListTraversal(self.root)
    returnObj = self.__listObj
    self.__listObj = []
    return returnObj
```

```python
def __toListTraversal(self, node):
    if node != None:
        self.__toListTraversal(node.getLeftChild())
        self.__listObj.append(node.getData())
        self.__toListTraversal(node.getRightChild())
```

```python
def listTree(self, list):
    for item in list:
        self.add(item)
```

# 图的实现

```python
class Node():
    def __init__(self, data=None):
        self.data = data
        self.next = None
        self.edges = []

    def setNext(self, next):
        self.next = next

    def getNext(self):
        return self.next

    def setData(self, data):
        self.data = data

    def getData(self):
        return self.data

    def addEdge(self, edge):
        self.edges.append(edge)

    def getEdges(self):
        return self.edges

    def getSelf(self):
        return self
```

```python
class Graph():
    def __init__(self):
        self.root = None

    def addNode(self, data):
        if self.root == None:
            self.root = Node(data)
        else:
            self.__traverseAndAdd(self.root, data)

    def __traverseAndAdd(self, node, nodeToAdd):
        if node.getRightChild() == None:
            node.setRightChild(Node(nodeToAdd))
            node.getRightChild().setParent(node)
        else:
            self.__traverseAndAdd(node.getRightChild(), nodeToAdd)

    def addEdge(self, startData, endData):
        startNode = self.findNode(startData)
        endNode = self.findNode(endData)
        if startNode != None and endNode != None:
            startNode.addEdge(endNode)

    def findNode(self, value):
        if self.root != None:
            self.__getNodeTraversal(self.root, value)
        else:
            return None
        returnNodeObj = self.__findNodeObj
        self.__findNodeObj = None
        return returnNodeObj

    def __getNodeTraversal(self, node, value):
        if node != None:
            if node.getData() == value:
                self.__findNodeObj = node
            self.__getNodeTraversal(node.getLeftChild(), value)
            self.__getNodeTraversal(node.getRightChild(), value)

    def contains(self, value):
        if self.root != None:
            self.__containsTraversal(self.root)
        returnBool = self.__containsBool
        self.__containsBool = False
        return returnBool

    def __containsTraversal(self, node, value):
        if node != None:
            if node.getData() == value:
                self.__containsBool = True
            self.__containsTraversal(node.getLeftChild(), value)
            self.__containsTraversal(node.getRightChild(), value)

    def isReachable(self, startData, endData):
        startNode = self.findNode(startData)
        if startNode == None:
            return False
        self.numOfEdges = 0
        self.lookedAt = []
        self.__traverseAndEdges(startNode, endData)
        return self.isReBool

    def __traverseAndEdges(self, node, endData):
        for edge in node.getEdges():
            if edge.getData() == endData:
                self.isReBool = True
                return
            if edge not in self.lookedAt:
                self.lookedAt.append(edge)
                self.numOfEdges += 1
                self.__traverseAndEdges(edge, endData)
```

# 8. 多线程与多进程

Java 允许你使用 Java 的线程模型并行运行独立的进程。Python 也提供了这种能力，但通过两种互具独特的变体来实现：“多线程”和“多进程”。两者之间的区别在于独立进程如何共享它们运行的虚拟内存。

## 8.1 多线程

多线程在同一内存空间中运行，并根据可用情况共享内存。例如，如果一个线程占用了 80% 的可用内存，那么只剩下 20% 内存用于运行其他进程，直到被占用的 80% 中有更多内存变得可用。示例 8.1.1 展示了 Java 和 Python 中多线程的实现。我保持了 Java 和 Python 示例之间的类名和方法名相同，以便你比较这两种语言如何实现多线程。

### 示例 8.1.1

**Java:**

```java
class SomeClass {
    public static void main(String args[]) {
        new ThreadNode("First");
        new ThreadNode("Second");
        new ThreadNode("Third");
        new ThreadNode("Fourth");
    }
}

class ThreadNode implements Runnable {
    String threadName;
    Thread threadObj;

    ThreadNode(String threadName) {
        String name = threadName;
        threadObj = new Thread(this, name);
        threadObj.start();
    }

    public void run() {
        for (int counter = 5; counter > 0; counter--) {
            System.out.println(threadName + ": " + counter);
        }
    }
}
```

**Python:**

```python
import threading

class ThreadNode(threading.Thread):

    def __init__(self, threadName):
        threading.Thread.__init__(self)
        self.threadName = threadName

    def run(self):
        for counter in range(5):
            print(self.threadName + ": " + str(counter))

class SomeClass:
    def __init__(self):
        thread1 = ThreadNode("First")
        thread1.start()
        thread2 = ThreadNode("Second")
        thread2.start()
        thread3 = ThreadNode("Third")
        thread3.start()
        thread4 = ThreadNode("Fourth")
        thread4.start()

SomeClass()
```

## 8.2 多线程中的同步

Python 的 `threading` 模块提供了一种概念，即 `Lock()` 可以锁定其他进程并将它们在队列中排队。所有后续线程只有在当前线程完成执行后才会执行。在执行之前，线程需要 `acquire()` 它在队列中的预留位置。当执行完成后，线程必须 `release()` 自己，为队列中的下一个线程开辟路径。示例 8.2.1 详细演示了在 Python 中是如何实现的。

### 示例 8.2.1

**Python:**

```python
import threading

class ThreadNode(threading.Thread):
    def __init__(self, threadName, lockObj):
        threading.Thread.__init__(self)
        self.threadName = threadName
        self.lockObj = lockObj

    def run(self):
        self.lockObj.acquire()
        for counter in range(5):
            print(self.threadName + ": " + str(counter))
        self.lockObj.release()

class SomeClass():
    def __init__(self):
        lockObj = threading.Lock()

        thread1 = ThreadNode("First", lockObj)
        thread1.start()
        thread2 = ThreadNode("Second", lockObj)
        thread2.start()
        thread3 = ThreadNode("Third", lockObj)
        thread3.start()
        thread4 = ThreadNode("Fourth", lockObj)
        thread4.start()

SomeClass()
```

## 8.3 多进程

多进程将内存平均分配给并行运行的进程。每个进程在自己的虚拟内存中运行，不会夺取其他进程的内存。例如，如果我们在四核 CPU 上运行四个进程，那么每个进程都将在自己的核心上运行，而不会干扰其他进程的核心。在 Python 中，可以使用多种方式实现多进程。我在示例 8.3.1 和 8.3.2 中指定了两种方法。两者效果良好，并展示了 Python 的灵活性。

### 示例 8.3.1

**Python:**

```python
from multiprocessing import Process

class ThreadNode:
    def __init__(self, threadName):
        self.threadName = threadName
        Process(target=self.run, args=()).start()

    def run(self):
        for counter in range(5):
            print(self.threadName + ": " + str(counter))

class SomeClass():
    def __init__(self):
        ThreadNode("First")
        ThreadNode("Second")
        ThreadNode("Third")
        ThreadNode("Fourth")

SomeClass()
```

### 示例 8.3.2

**Python:**



```python
from multiprocessing import Process

class ThreadNode:
    def run(self, threadName):
        for counter in range(5):
            print(threadName + ": " + str(counter))

class SomeClass():
    def __init__(self, args):
        # 实现细节似乎在原文中缺失或不完整
        pass
```

## 9.4 写入文件

使用 Python 写入文件的实现方式与读取文件几乎相同。示例 9.4.1 展示了如何操作。请注意，示例 9.4.1 每次执行时都会覆盖现有的文件内容。另外注意，如果文件不存在，程序将创建一个文件，但前提是文件指定的路径存在。如果一个或多个目录不存在，以下程序将抛出异常。

### 示例 9.4.1

Java:

```java
import java.io.*;
class WriteFileContent {
    public static void main(String args[]) {
        String fileNameWithPath = "/path/to/file/filename.txt";
        File fileToWrite = new File(fileNameWithPath);
        if (!fileToWrite.exists()) {
            fileToWrite.createNewFile();
        }
        PrintWriter writer = new PrintWriter(fileNameWithPath, "UTF-8");
        writer.println("text to write");
        writer.close();
    }
}
```

Python:

```python
class WriteFileContent():
    def __init__(self):
        fileToWrite = open("filename.txt", "w")
        fileToWrite.writelines("text to write")
        fileToWrite.close()

WriteFileContent()
```

## 9.5 追加到文件

在写入文件时，通常你需要在同一个文件中追加文本行，同时保留文件的现有内容。通过使用示例 9.4.1 并仅更改函数 `open()` 的第二个参数的一个字符，我可以开始向文件中追加内容，而不是每次访问时覆盖它。请查看示例 9.5.1。`open()` 函数的第二个参数被设置为 `a`，在这种情况下它代表“追加（append）”。

### 示例 9.5.1

Python:

```python
class WriteFileContent():
    def __init__(self):
        fileToRead = open("filename.txt", "a")
        fileToRead.writelines("text to write")
        fileToRead.close()

WriteContent()
```

## 9.6 检查路径是否存在

为了防止程序抛出异常，如果正在读取或写入的文件路径不存在，先对指定路径的存在进行检查很有帮助。为了实现这一点，我首先需要导入 `os` 模块，然后使用它的 `path.exists` 函数，该函数将返回一个布尔值，告知路径是否存在。示例 9.6.1 展示了此检查的实现。

### 示例 9.6.1

Python:

```python
import os

class SomeClass():
    def __init__(self):
        print(os.path.exists("/path/to/bla/bla/"))

SomeClass()
```

示例 9.6.2 展示了在路径存在的情况下如何将路径检查与写入文件结合。

### 示例 9.6.2

Python:

```python
class WriteFileContent():
    def __init__(self):
        pathToFile = "/path/to/file/"
        fileName = "filename.txt"
        if os.path.exists(pathToFile):
            fileToRead = open(os.path.join(pathToFile, fileName), "w")
            fileToRead.writelines("text to write")
        fileToRead.close()

WriteFileContent()
```

## 9.7 创建文件路径

当你尝试写入文件但路径不存在时，你可以通过添加缺失路径中所有缺失的目录和子目录来简单地创建它。在 Python 中可以使用 `os` 模块轻松实现这一点，如示例 9.7.1 所示。你可能会注意到我将向文件写入代码移动到了独立的方法中，并为我的条件添加了 `else`，用以检查提供的路径是否存在。如果路径不存在，它将创建路径中所有缺失的目录。`os.makedirs(pathToFile)` 函数为此工作得非常完美，并在示例 9.7.1 中进行了演示。

### 示例 9.7.1

Python:

```python
class WriteFileContent():
    def __init__(self):
        pathToFile = "path/to/file/"
        fileName = "filename.txt"
        if os.path.exists(pathToFile):
            self.write(pathToFile, fileName)
        else:
            os.makedirs(pathToFile)
            self.write(pathToFile, fileName)

    def write(self, pathToFile, fileName):
        fileRead = open(os.path.join(pathToFile, fileName), "w")
        fileRead.writelines("text to write")
        fileRead.close()

WriteFileContent()
```

## 9.8 读取 JSON 文件

为了展示 Python 的强大和简单，让我们来看看如何从 JSON 格式读取和向其写入。首先，我想引起你注意 Python 字典数据结构的格式和 JSON 的格式。你是正确的——它们几乎是完全一样的。唯一的区别是 Python 中的布尔值以大写字母开头（`True` 或 `False`），而在 JSON 中它们是小写的（`true` 或 `false`），且 JSON 的空值在 Python 字典中是 `None`。除了这两个区别外，它们的格式是相同的，并且可以以类似的方式进行迭代。

然而，将 JSON 格式数据转换为 Python 对象需要一个名为 `json` 的模块。（注：原文此处存在大量重复语句，翻译时已清理）。

## 9.10 读取 CSV 文件

CSV 格式非常流行，特别是在大数据开发者中，常被用作数据导出和注入格式。Python 拥有一个非常强大的库，让处理 CSV 变得极其简单。在接下来的示例 9.10.1 中，我演示了如何通过提供 CSV 文件的路径和文件名从 CSV 文件读取内容，然后返回一个 Python 的 CSV 对象，该对象包含给定 CSV 文件的所有内容。与 `json` 模块一样，`csv` 模块需要先导入。请注意，你可以指定不同的分隔符——可以是逗号 (`,`)、管道 (`|`) 或制表符 (`\t`) ——这取决于你尝试读取的 CSV 文件所使用的分隔符。

### 示例 9.10.1

Python:

```python
import csv

class WorkingWithContent:
    def getCSVContentPath(csvFileWithPath="/path/to/file/our_csv_file.csv"):
        with open(csvFileWithPath, 'rb') as csvFile:
            csvContent = csv.reader(csvFile, delimiter=',', quotechar='|')
            return csvContent
```

示例 9.10.2 演示了如何提取和读取 `csvContent` 对象的值。如示例 9.10.2 所示，我添加了 `csvContent` 的迭代，它会输出内容的每一行，然后将其打印到控制台。如果你运行以下示例，你将看到每一行都是 CSV 文件中每行值的数组。由于每行都是一个列表，你可以像从任何数组列表中通过索引提取元素一样，提取它的值。

### 示例 9.10.2

Python:

```python
import csv

class WorkingWithCSV():
    def getCSVContent(self):
        csvFileWithPath = "/path/to/file/our_csv_file.csv"
        with open(csvFileWithPath, 'rb') as csvFile:
            csvContent = csv.reader(csvFile, delimiter=',', quotechar='|')
            for row in csvContent:
                print(row)
```

这还有更多内容。就像 JSON 一样，在 Python 中有多个强大的模块可以处理 CSV 格式。下一个示例演示了 `pandas` 模块，它解决了从给定的 CSV 文件中提取单列值列表的问题。假设我有一个 CSV 文件，列名定义在表头，我需要提取某一个特定列的值列表。下面的示例准确展示了如何在 Python 中实现这一目标。`pandas` 模块在程序中引用和使用之前也需要先导入。请查看示例 9.10.3。

### 示例 9.10.3

Python:

```python
import pandas

class WorkingWithCSV():
    def getCSVContent(self):
        csvFileWithPath = "/path/to/file/our_csv_file.csv"
        csvContent = pandas.read_csv(csvFileWithPath)
        column_values_list = csvContent['column_name']
        return column_values_list
```

## 9.11 写入 CSV 文件

使用相同的 `csv` 模块也可以轻松地写入 CSV。首先，你需要将所有值聚合到数组列表中。将此列表对象传递给 `csv.writer`，它将完成剩下的工作。这听起来非常简单。请注意，你可以指定不同的分隔符，逗号 (`,`)、管道 (`|`) 或制表符 (`\t`)。在示例 9.11.1 中，我为尝试生成的 CSV 文件指定了逗号分隔符。

### 示例 9.11.1

Python:

```python
import csv

class WorkingContentToCSV():
    def writeContentToCSV(self):
        csvFileWithPath = "/path/to/file/our_csv_file.csv"

        values = ["value-one", "value-two", 3, 44:44, "value five"]

        with open(csvFileWithPath, 'w') as csvWrite:
            csvWriter = csv.writer(csvWrite, delimiter=',')
            csvWriter.writerows(values)
```

## 9.12 Lambda 表达式

让我们来看看 lambda，即在运行时没有绑定到生成名称的匿名函数。Java 从 Java 8 开始支持 lambda，Python 也是如此。在这两种语言中，lambda 的概念几乎相同。然而，语法略有不同，但如果你知道 lambda 是什么以及如何在 Java 中使用它们，就很容易理解。顺便说，在两种语言中，lambda 都可以作为参数传递给其他函数。示例 9.12.1 演示了 Java 和 Python 实现相同 lambda 时的语法差异。这是一个非常简单的示例，在比较两个字符串后返回布尔值。

### 示例 9.12.1

Java:

```java
boolean comparingStrings = (String strOne, String strTwo) -> strOne.equals(strTwo);
```

Python:

```python
comparingStrings = lambda strOne, strTwo: strOne == strTwo
```

在运行示例 9.12.1 中的 lambda 函数后，你需要执行以下操作。在示例 9.12.2 中，让我们使用 Java 和 Python 打印上述 lambda 的返回结果。

### 示例 9.12.2

Java:

```java
boolean comparingStrings = (String strOne, String strTwo) -> strOne.equals(strTwo);
System.out.println(comparingStrings);
```

Python:

```python
comparingStrings = lambda strOne, strTwo: strOne == strTwo
```

```python
strOne = "Hello World"
strTwo = "Hello World"
equalsOrNot = strOne == strTwo
```

Java 的 `equalsIgnoreCase()` 可以通过示例 10.3.2 所示的方法在 Python 中模拟。

### 示例 10.3.2

Java:

```java
String strOne = "Hello World";
String strTwo = "hello world";
boolean equalsOrNot = strOne.equalsIgnoreCase(strTwo);
```

Python:

```python
strOne = "Hello World"
strTwo = "hello world"
equalsOrNot = strOne.lower() == strTwo.lower()
```

## 10.4 StartsWith() 和 EndsWith()

这两个方法在 Java 和 Python 中几乎完全相同。示例 10.4.1 解释了一切。

### 示例 10.4.1

Java:

```java
String strOne = "Hello World";
String strTwo = "hello world"
boolean startsWithNot = strOne.startsWith("He");
```

## 10.6 字符串替换 (String Replace)

在 Java 和 Python 中，`replace()` 起的作用完全相同，甚至调用方式也相同。示例 10.6.1 展示了这些相似性。

### 示例 10.6.1

Java:

```java
String strOne = "Hello, Today’s Wonderful World of People’s Happiness.";
String strTwo = strOne.replace("Today", "Yesterday");
```

Python:

```python
strOne = "Hello, Today’s Wonderful World of People’s Happiness."
strTwo = strOne.replace("Today", "Yesterday")
```

## 10.7 Python 中的字符串 trim()

Java 的 `trim()` 在 Python 中被称为 `strip()`。两者的作用完全相同，都是移除字符串前后的空格。示例 10.7.1 展示了 `strip()` 的用法。

### 示例 10.7.1

Java:

```java
String strOne = " Hello, Today’s Wonderful World of People’s Happiness.";
String strTwo = strOne.trim();
```

Python:

```python
strOne = " Hello, Today’s Wonderful World of People’s Happiness."
strTwo = strOne.strip()
```

## 10.8 字符的大小转换

示例 10.8.1 展示了如何在 Java 和 Python 中将所有字符转换为大写或小写。

### 示例 10.8.1

Java:



## 10.9 字符串合并 (Joining Strings)

与 Java 一样，Python 也有一个 `join` 函数，其作用相同且工作方式相似。语法略有不同，但仅是略微不同。请查看示例 10.9.1。

### 示例 10.9.1

**Java:**

```java
String[] strArr = {"WordOne", "WordTwo", "WordThree", "WordFour", "WordFive"};
String joinedStr = String.join("-", strArr);
```

**Python:**

```python
strArr = ["WordOne", "WordTwo", "WordThree", "WordFour", "WordFive"]
joinedStr = "-".join(strArr)
```

在两种情况下，变量 `joinedStr` 将包含值 `WordOne-WordTwo-WordThree-WordFour-WordFive`。

## 10.10 字符串长度 (String Length)

正如我之前提到的，Python 将所有字符串视为字符数组。因此，要获取字符串的长度，你使用的方法与获取数组的大小完全相同：使用 Python 的函数 `len()`。示例 10.10.1 展示了这一点。

### 示例 10.10.1

**Java:**

```java
String strOne = "Hello, Today’s Wonderful World of People’s Happiness."
int maxLength = strOne.length();
```

**Python:**

```python
strOne = "Hello, Today’s Wonderful World of People’s Happiness."
strLength = len(strOne)
```

## 10.11 反转字符串 (Reverse a String)

Python 中有两种反转字符串的方法，如示例 10.11.1 所示，且都是 Python 特有的。方法一使用双重切片语法，这是 Python 中一种非常独特的语法，Java 中没有对应的写法。方法二先反转数组，然后将字符数组合并回单个字符串。

### 示例 10.11.1

**Java:**

```java
String strOne = "Hello, Today’s Wonderful World of People’s Happiness."
String reversedStr = new StringBuilder(strOne).reverse().toString();
```

**Python:**

**方法一：**

```python
strOne = "Hello, Today’s Wonderful World of People’s Happiness."
reversedStr = strOne[::-1]
```

**方法二：**

```python
strOne = "Hello, Today’s Wonderful World of People’s Happiness."
reversedStr = "".join(reversed(strOne))
```

## 11. 排序与搜索算法

### 11.1 插入排序

```python
def insertionSort():
    array = [6, 8, 2, 5, 6, 10, 25, 12, 6, 4, 6]
    for i in range(len(array)):
        key = array[i]
        j = i - 1
        while j >= 0 and array[j] > key:
            array[j + 1] = array[j]
            j -= 1
        array[j + 1] = key
```

### 11.2 冒泡排序

```python
def bubbleSort():
    array = [6, 8, 2, 5, 6, 10, 25, 12, 6, 4, 6]
    for i in range(len(array)):
        for j in range(0, len(array) - i - 1):
            if array[j] > array[j + 1]:
                array[j], array[j + 1] = array[j + 1], array[j]
```

### 11.3 选择排序

```python
def selectionSort():
    array = [6, 8, 2, 5, 6, 10, 25, 12, 6, 4, 6]
    for i in range(len(array)):
        # (省略部分实现逻辑)
```

### 11.4 二分搜索

```python
def binarySearch(array, target):
    low = 0
    high = len(array) - 1
    while low <= high:
        mid = (low + high) // 2
        if array[mid] == target:
            return mid
        elif array[mid] < target:
            low = mid + 1
        else:
            high = mid - 1
    return -1
```

## 12. 处理压缩模块

路径 `packages/paramiko/` 可以通过运行 Linux 的 `zip` 命令轻松压缩，如下：

```
sudo zip -r zipped_matplotlib.zip /Library/Frameworks/Python.framework/2.7/lib/python2.7/site-packages/paramiko/
```

现在，我已经将 `paramiko` 模块压缩并存储在环境驱动器中，文件名为 `zipped_paramiko.zip`。该文件是一个导出的模块，我需要将其存储在项目工作区的某处。

为了将此模块导入我的项目并能够使用，我需要使用 Python 的 `sys` 模块，该模块作为所有 Python 发行版的一部分预装。通过使用 `sys.path.insert()`，我可以指定压缩模块的路径，然后像安装到环境中一样导入它。示例 12.2.1 演示了如何将压缩模块导入到工作区。

### 示例 12.2.1

**Python:**

```python
import sys
sys.path.insert(0, '/path/to/zipped/module/file/paramiko.zip')
import paramiko
```

```python
class SomeClass():
    def __init__(self):
        port = 22
        host = ""
        username = ""
        password = ""
        transport = paramiko.Transport(host, port)
        transport.connect(username=username, password=password)
        sftp = paramiko.SFTPClient.from_transport(transport)
        sftp.put("local_file", "sftp_path")

run = SomeClass()
```

## 13. 从 Python 运行 Shell 命令

### 13.1 运行单个 Shell 命令

很多时候，你可能需要从 Python 程序之外执行 Shell 命令，例如访问 HDFS 命令。Python 提供了一个名为 `subprocess` 的模块，专门为此目的而设计。命令可以以字符串的形式传递，而且你绝对需要读取日志，不仅是 `stdout`，还有 `stderr`。下一个示例中的方法正演示了这一点。它执行 Shell 命令，然后将 `stdout` 和 `stderr` 流都重定向到一个流中，然后进行捕获并返回。

#### 示例 13.1.1

**Python:**

```python
def runShellCommand(self):
    pass
```

### 13.2 以数组形式运行多个 Shell 命令

有时，你可能需要运行一组 Shell 命令，其中一个设置环境变量，另一个启动特定的进程。为此，你将以数组的形式一次性传递两个或多个命令。示例 13.2.1 演示了如何使用示例 13.1.1 中的功能实现这一目标。

#### 示例 13.2.1

**Python:**

```python
def runShellCommandAsArray(commandAsArray):
    logToReturn = ""
    try:
        popen = subprocess.Popen(commandAsArray, stdout=subprocess.PIPE,
                                 stderr=subprocess.STDOUT)
        lines_iterator = iter(popen.readline, b"")
        for line in lines_iterator:
            print(line)
            logToReturn = logToReturn + str(line) + "\n"
    except Exception as e:
        print(e)
    return logToReturn
```

## 14. 查询数据库

### 14.1 SQLite3

要连接并查询 SQLite3 数据库，Python 提供了一个与数据库本身名称完全相同的模块：`sqlite3`。首先，需要将 `sqlite3` 模块导入到代码所在的文件中。然后，按照示例 14.1.1 中列出的步骤连接到它，执行 `select` 语句并打印前十条选定的记录。

#### 示例 14.1.1

**Python:**

```python
import sqlite3

class QuerySQLite3:
    def __init__(self):
        conn = sqlite3.connect('path/to/db_file.db')
        dbConnection = conn.cursor()
        executeQuery = dbConnection.execute('select * from TABLE_NAME limit 10')
        data = executeQuery.fetchall()
        print(data)
        dbConnection.close()

QuerySQLite3()
```

### 14.2 MySQL

连接 MySQL 的方式与 SQLite3 数据库的情况非常相似。模块是 `MySQLdb`。安装模块后，需要将其导入代码库，并像示例 14.2.1 所示，它连接到 MySQL 数据库，执行 `select` 语句并打印前十条选定的记录。不要忘记提供主机地址、用户名、密码和数据库名称，以便模块连接到你的数据库。

#### 示例 14.2.1

**Python:**

```python
import MySQLdb

class QueryMySQL:
    def __init__(self):
        conn = MySQLdb.connect("host","username","password","database_name")
        dbConnection = conn.cursor()
        executeQuery = dbConnection.execute('select * from TABLE_NAME limit 10')
        data = executeQuery.fetchall()
        print(data)
        dbConnection.close()

QueryMySQL()
```

### 14.3 Oracle

与 Oracle 数据库交互是这三个数据库中最复杂的过程。在 Python 连接到 Oracle 数据库之前（即使是托管在远程的），你也需要设置 Oracle。`cx_Oracle` 模块依赖于 Oracle Instant Client。

以下是设置 Oracle 的步骤：

#### 步骤 1：下载并安装 Oracle Instant Client

首先，运行以下命令查看安装了什么：

```bash
glibc -qa
```

响应应该如下：

```text
glibc-2.12-el6.x86_64
```

`cx_Oracle` 模块依赖于 11.2 或更高的 Oracle Instant Client。

#### 步骤 2：设置环境变量

在你的配置文件中运行以下导出命令：

```bash
export LD_LIBRARY_PATH=/usr/lib/oracle/11.client4/lib
export ORACLE_HOME=/usr/lib/oracle/11.client4
export PATH=$ORACLE_HOME/bin:$PATH
```

#### 步骤 3：安装 cx_Oracle 模块

下载并安装以下版本的 `cx_Oracle`：

https://sourceforge.net/projects/cx-oracle/files/5.1.2/cx_Oracle-5.1.2-11g-py27-1.x86_64.rpm

安装命令为：

```bash
sudo rpm -ivh cx_Oracle
```

在设置 SDK、所有依赖并设置路径后，你需要安装 Python 模块 `cx_Oracle`。根据其网站（http://cx-oracle.sourceforge.net）的说明，可以简单地使用 `pip install cx_Oracle` 安装。然而，根据我的经验，我无法让最新版本运行，最终安装了旧版本。旧版本的 `cx_Oracle` 模块可以在此处找到：https://sourceforge.net/projects/cx-oracle/files/。

安装 `cx_Oracle` 模块后，请确保导入时没有错误。

然后使用示例 14.3.1 运行 `select` 语句并打印前十条记录，就像我在上一节的 SQLite3 和 MySQL 示例中所做的那样。

#### 示例 14.3.1

**Python:**

```python
import cx_Oracle

class OracleDB():
    def getConnected(self):
        conn = cx_Oracle.connect('username/password@host:1251/database_name')
        dbConnection = conn.cursor()
        dbConnection.execute('select * from TABLE_NAME limit 10')
        data = dbConnection.fetchall()
        print(data)
        dbConnection.close()
        conn.close()
```

## 15. 使用 Python 构建独立应用程序

信你不信，你也可以构建一个具有极佳用户界面的全功能桌面应用程序。与 Java 类似，Python 也是一种多平台语言，因此应用程序只需要开发一次，就可以在多个平台（如 Mac OS X、MS Windows 和 Linux）上运行。你可能在某处读过 Python 是一种解释型脚本语言。对我而言并非，Python 是一种功能完备的面向对象的编程语言，它赋予了你运行解释脚本或程序的能力，还能将程序编译成功能完备、独立且多平台的应用程序，这些程序可以在所有主要的桌面操作系统上运行。在我写此书时，Python 尚未进入移动平台世界，但谁知道呢，它可能对你来说指日可待。目前，我列出了三种资源，将帮助你构建基于 Linux、Mac OS 或 Windows 的应用程序。

### 15.1 PyInstaller



# 15. 使用 Python 构建独立可执行程序

## 15.1 PyInstaller

根据 PyInstaller 开发者的介绍，它是一个可以将 Python 程序冻结（打包）为 Windows、Linux、Mac OS X、FreeBSD、Solaris 和 AIX 下独立可执行程序的工具。它与类似工具相比的主要优势在于 PyInstaller 支持 Python 2.7 和 3.3+ —— 它构建的可执行文件比透明压缩更小，它是完全多平台的，并且利用操作系统的支持来加载动态库，确保了完全兼容。PyInstaller 的主要目标是开箱兼容第三方包。这意味着，通过 PyInstaller，所有让外部包运行所需的技巧都已集成在 PyInstaller 中，因此不需要用户干预。你永远不需要在 wiki 中寻找技巧，并对你的文件或设置脚本进行自定义修改。例如，`PyQt`、`Django` 和 `matplotlib` 等库都得到了完全支持，不需要你手动处理插件或外部数据文件。

请访问 PyInstaller 网站获取更多详情和教程：

<http://www.pyinstaller.org/>

## 15.2 py2app

根据 py2app 开发者的介绍，它是一个 Python `setuptools` 命令，允许你为 Mac OS 操作系统从 Python 脚本创建独立的应用程序包（bundles）和插件。py2app 网站提供了一个非常出色的教程，详尽地解释了如何安装 py2app 以及使用它编译 Python 程序。

请访问 py2app 网站获取更多详情和教程：

<https://pythonhosted.org/py2app/tutorial.html>

## 15.3 py2exe

根据 py2exe 开发者的介绍，它是一个 Python `DistUtils` 扩展，可以将 Python 脚本转换为可执行的 Windows 程序，这些程序无需安装 Python 即可运行。py2exe 网站也有一个非常出色的教程，详尽地解释了如何安装 py2exe 以及使用它编译 Python 程序。

请访问 py2exe 网站获取更多详情和教程：

<http://www.py2exe.org/index.cgi/Tutorial>

# 16. 使用 Python 构建网站

Python 还提供了丰富的平台，供你开发全功能、数据库驱动的 Web 应用程序。下面我列出了三个用于用 Python 构建网站的最流行的平台。

## 16.1 Django

Django 平台的开发者将其推为一种高级 Python Web 框架，鼓励快速开发和简洁、务实的设计。它由经验丰富的开发者构建，处理了 Web 开发中的许多繁琐工作，因此你可以专注于编写自己的 Web 应用程序，而不需要重复造轮子。它是免费开源的。Django 是目前为止我最喜欢的平台，也是我用于在线环境的工具。YouTube 和 Django 官方网站上都有大量的免费教程。

请访问 Django 网站获取更多详情和教程：

<https://www.djangoproject.com/>

## 16.2 Flask

Flask 在 Python Web 开发领域也非常受欢迎。然而，Flask 设计是为小型网站设计的，而 Django 则设计用于构建更大、更复杂的网站。

请访问 Flask 网站获取更多详情和教程：

<http://flask.pocoo.org>

## 16.3 Pyramid

Pyramid 是一个非常通用的开源 Python Web 框架。作为一个框架，它的首要任务是让开发者更容易创建任意的 Web 应用程序。创建的应用程序类型并不重要；它可以是一个电子表格、企业内网或社交网络平台。Pyramid 足够通用，可以用于各种情况。

请访问 Pyramid 网站获取更多详情和教程：

<http://www.pylonsproject.org/projects/pyramid/about>

## 作者博客

我希望这本书能帮助你加速从 Java 到 Python 的过渡。当你转向 Python 时，我的博客是另一个资源，因为 Python 的内容确实比这里包含的多得多。Python 已经成为 Java 等强大语言非常强有力的竞争对手，并且不断进化，提供了越来越多的模块，为开发更复杂的系统开启大门。

随着我作为 Python 程序员的经验增加，我会以文章的形式记录并发布在我的博客上。因此，在我的博客上，你将发现 Python 可能实现的额外技巧。我的在线博客所有人免费访问：<http://ToProgramInPython.com>。

我博客上的“联系”页面是一个通信工具，你可以通过它向我提出问题、建议以及对本书的更正。我希望在阅读这本书时，你能看到作为一个 Java 工程师对 Python 已经了解了多少，以及你可以多快地掌握 Python 并成为更强大的软件开发者。
