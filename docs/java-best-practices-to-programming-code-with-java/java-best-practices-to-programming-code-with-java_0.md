
# Java 编程最佳实践

![](img/cover0009.jpeg)

阅读本文意味着读者同意，在任何情况下，作者对因使用本文包含的信息而引起的任何直接或间接损失（包括但不限于错误、遗漏或不准确）负责。

## 介绍

感谢并祝贺你阅读我的书籍《Java：使用 Java 编程的最佳实践》。

本书包含了经过验证的步骤和策略，教你如何编写不会产生错误、整洁有序且具有高度可读性的 Java 代码。如果你的代码看起来很眼熟，它将更容易理解，而且易于一眼看出是否有明显的错误。为了确保你的代码看起来很眼熟，有一套你应该遵循的最佳实践指南；这不仅对你有帮助，也会帮助查看你代码的其他开发者。

本书假设你已经对 Java 计算机编程语言有一定程度的了解和经验。我的目标是帮助你进一步增加知识，让你在短时间内像专家一样编程。如果你是该语言的完全新手，请在阅读我的最佳实践指南之前熟悉基础知识。

再次感谢你购买本书，希望你喜欢！

## 第 1 章：代码格式化

老实说，在我们进入细节之前，第一个要着手的地方是如何格式化你的 Java 代码。有几条你应该遵循的“规则”，以确保你的代码是可读且整洁的：

### 缩进

所有的 Java 代码缩进都使用空格（spaces）而不是制表符（tabs），每个缩进为 4 个空格。这是因为，与所有其他计算机编程语言一样，Java 与空格配合良好。有些程序会混合使用空格和制表符，导致某些行使用制表符缩进，某些行使用空格。如果你将制表符设置为 4，而你的文件与一个将其设置为 8 的人共享，那么看起来看起来将是一团糟。

当你使用匹配的大括号时，它们必须在相应的结构下方垂直对齐，位于完全相同的列上。例如：

```java
void foo()
{
    while (bar > 0)
    {
        System.out.println();
        bar--;
    }
    if (Cheese == tasty)
    {
        System.out.println("Cheese is good and it is good for you");
    }
    else if (Cheese == yuck)
    {
        System.out.println("Cheese tastes like rubber");
    }
    else
    {
        System.out.println("please tell me, what is this cheesel'");
    }
    switch (yuckyFactor)
    {
        case 1:
            System.out.println("This is yucky");
            break;
        case 2:
            System.out.println("This is really yucky");
            break;
        case 3:
            System.out.println("This is seriously yucky");
            break;
        default:
            System.out.println("whatever");
            break;
    }
}
```

### 为所有的 `if`、`for` 语句使用大括号

即使它们控制的是单个语句也是如此的。为什么？因为这样你可以保持格式的一致，代码会变得更易读。不仅如此，如果你需要添加或删除代码行，就不需要进行大量的编辑。看看这个例子——前三个显示了错误的方法，而第四个显示了正确的方法：

错误示例：

```java
if (superHero == tock) System.out.println("Fork!"); 
if (superHero == tock)
    System.out.println("Fork!"); 
```

正确示例：

```java
if (superHero == tock) {
    System.out.println("Fork!");
}
if (superHero == tock) {
    System.out.println("Fork!");
}
```

（注：此处原文示例似乎不完整，已根据逻辑翻译并补全格式）

```java
if (Cheese == tasty)
{
    System.out.println("Cheese is good and it is good for you");
}
else if (Cheese == yuck)
{
    System.out.println("Cheese tastes like rubber");
}
else
{
    System.out.println("please tell me, what is this cheesel'");
}
switch (yuckyFactor)
{
    case 1:
        System.out.println("This is yucky");
        break;
    case 2:
        System.out.println("This is really yucky");
        break;
    case 3:
        System.out.println("This is seriously yucky");
        break;
    default:
        System.out.println("whatever");
        break;
}
```

（注：原文存在重复内容）

### 空格

当你有一个方法名时，它应该紧跟一个左括号：

错误示例：

```java
foo (i, j)
```

正确示例：

```java
foo(i, j)
```

左方括号必须紧跟在数组引用之后：

错误示例：

```java
args [0];
```

正确示例：

```java
args[0];
```

确保任何二元运算符的两侧都有空格：

错误示例：

```java
a=b+c;
```

正确示例：

```java
a = b + c;
```

当你使用一元运算符时，它应该紧跟其操作数：

错误示例：

```java
count ++;
```

正确示例：

```java
count++;
```

错误示例：

```java
i --;
```

正确示例：

```java
i--;
```

当你使用分号或逗号时，请在其后紧跟一个空格：

错误示例：

```java
for (int i = 0;i < 10;i++)
```

正确示例：

```java
for (int i = 0; i < 10; i++)
```

错误示例：

```java
getOmelets(EggsQuantity,butterQuantity);
```

正确示例：

```java
getOmelets(EggsQuantity, butterQuantity);
```

编写所有的类型转换时不要带空格：

错误示例：

```java
(MyClass ) v.get(3);
( MyClass )v.get(3);
```

正确示例：

```java
(MyClass)v.get(3);
```

当你在表达式中使用括号时，不要仅仅用它们来规定优先级；它们还应该被用作简化问题的方法。

## 第 2 章：命名规范

在 Java 中，正确地命名方法、变量和类非常重要，这里是一些比较常见的规范，如果你学习并遵循这些规范，将帮助你的代码变得清晰得多：

*   当你命名包（packages）时，名称应该用小写，例如 `mypackage`。

*   所有代表类型（types）的名称必须是名词，并采用混合驼峰写法，以大写字母开头，例如 `AudioSystem`、`Line`。

*   所有变量名必须采用混合驼峰并以小写字母开头，例如 `audioSystem`、`line`。这有助于区分变量和类型，并解决任何潜在的命名冲突。

*   如果一个名称代表常量（constant）或最终变量（final variable），必须全大写，并用下划线分隔每个单词，例如 `COLOR_BLUE`、`SAM_ITERATIONS`。通常情况下，这些常量的使用应保持最少，而且通常情况下，通过方法来实现值更好，例如：

    ```java
    Int getSamIterations() // ：SAM_ITERATIONS = 25
    {
        return 25;
    }
    ```

    这样更易读，而且还能确保类值具有统一的接口。



*   如果一个名称代表方法，它必须是一个动词，并且必须是以小写字母开头的混合写法，例如 `computeTotalLenght()`、`getNames()`。这与变量完全相同，但因为它们有特定的形式，Java 方法已经很容易与变量区分开来。

*   当将缩写词或简称作名称使用时，永远不要使用大写，例如：

    良好示例：

    ```java
    exportHtmlSource();
    ```

    错误示例：

    ```java
    exportHTMLSource();
    ```

    良好示例：

    ```java
    openDvdPlayer();
    ```

    错误示例：

    ```java
    openDVDPlayer();
    ```

    之所以这样做是因为如果你对基础名称使用全大写字母，你会发现它与在本章中讨论过的命名规范发生冲突。例如，如果你有这样的变量，你需要将其命名为 `hTML` 或 `dVD`，正如你所看到的，这些并不非常易读。另一个问题是——当将名称与另一个名称连接时，可读性会大大降低，缩写词后面的单词并不会凸显。

*   所有私有类变量都应该以下划线结尾，例如：

    ```java
    class Person
    {
      private String name_;
      ...
    }
    ```

    除了类型和名称之外，任何变量最重要的特征是它的作用域（scope）。使用下划线表示类的作用域可以让你轻松区分类变量和局部临时变量（scratch variable）。之所以这很重要，是因为类变量被认为比方法变量重要，因此你应该小心对待它。

    使用下划线规范的一个副作用是它解决了为 setter 方法寻找良好变量名的问题。例如：

    ```java
    void setName(String name)
    {
      name_ = name;
    }
    ```

    关于下划线应该是后缀还是前缀存在一个争议。这两种都很常用，但建议将其作为后缀，因为它是保持名称可读性的最佳方式。

    请注意，变量的作用域识别长期以来一直是一个具有争议的问题，但最终，使用下划线后缀的做法现在正在获得动力，并在专业 Java 开发领域中更受接受。

*   所有泛型变量（generic variables）的命名必须与其类型相同。例如：

    良好示例：

    ```java
    void getTopic(Topic topic)
    ```

    错误示例：

    ```java
    void getTopic(Topic value)
    void getTopic(Topic aTopic)
    void getTopic(Topic t)
    ```

    良好示例：

    ```java
    void connect(Database database)
    ```

    错误示例：

    ```java
    void connect(Database db)
    void connect(Database oracleDB)
    ```

    这是一个良好的实践，因为它通过减少使用的名称和术语的数量来帮助降低复杂性。它也更容易根据名称判断变量的类型。如果这个规范不符合你的编程习惯，这说明你选择了一个糟糕的类型名称。

*   所有非泛型变量都被分配了特定的角色，你通常可以使用类型和角色的组合来命名它们。例如：

    ```java
    Point startingPoint, centerPoint;
    Name loginName;
    ```

*   对所有名称使用英语。这是首选语言，你唯一偏离此点的唯一理由是你百分之百确定你的程序永远不会被任何不会说或读写你所语言的人看到或阅读。

*   作用域和名称应该匹配。如果你有一个作用域较大的变量，可以给它一个较长的名称；相反，作用域较小的变量可以给较短的名字。

    如果你使用临时变量作为索引或临时存储，请保持它们简短。阅读你的代码并看到这些变量的程序员应该能够假设这些变量是在一小段代码之外被使用的。某些用于整数的临时变量有 `i, j, k, m, n`，通常用于整数的是 `cand, d`。

*   对象名称是隐式的，且不应该在方法名中使用。例如：

    良好示例：

    ```java
    line.getLength();
    ```

    错误示例：

    ```java
    line.getLength();
    ```

## 特定命名规范

*   当直接访问属性时，必须使用 `get` 和 `set` 术语。例如：

    `employee.getName();`

    `employee.setName(name);`

    `matrix.getElement(2, 4);`

    `matrix.setElement(2, 4, value);`

*   对所有布尔方法和变量使用 `is` 前缀。例如：

    `isSet`

    `isVisible`

    `isFinished`

    `isOpen`

    使用这个前缀将解决选择 `flag` 或 `status` 等糟糕名称的问题。用于布尔值的 setter 方法应该有 `set` 前缀，如：

    ```java
    void setFound(boolean isFound);
    ```

    有一些替代方案可以代替 `is` 前缀，某些某些情况下效果更好。你可以使用的另外三个前缀是 `has`, `should`, `can`：

    `boolean hasLicense();`

    `boolean canEvaluate();`

    `boolean shouldAbort = false;`

*   当名称代表对象集合时，使用复数形式：

    ```java
    Collection<Point> points;
    int[] values;
    ```

    这立即提高了代码的可读性，因为用户可以看到变量类型以及对元素执行的操作。

# 第 3 章：注释

注释非常有用，用于标记程序。这些注释是给程序的读者的，帮助他们理解你的程序或程序的某些部分。作为一条原则，代码用于告诉计算机和程序员要做什么，而注释用于告诉程序员为什么要这样做。

注释可以出现在程序中任何允许空白字符的地方，Java 编译器不会注意到它们——前提是它们写得是正确的。如果你不按照正确的格式编写注释，不仅你的程序会抛出错误，你的代码看起来也会非常混乱困惑。

让我们看看不同类型的注释以及它们如何编写：

*   行内注释 - 当你写行尾注释时，应该以一对双斜杠（`//`）开始，它将在双斜杠所在的行的行尾结束。编译器将忽略 `//` 到行尾之间的任何内容。

## 块注释 (Block Comments)

- 块注释 – 块注释以正斜杠加星号 `/*` 开始，以星号加正斜杠 `*/` 结束，例如 `/*这是一个块注释*/`。这两个分隔符之间的任何文本都会被忽略，即使它跨越了多行。

- 粗体注释 - 这些是特殊的块注释类型，设计目的是为了吸引者的注意。例如：

```
/*---------------------------------------------------------

*  这是一个会引起人们对其自身
*  注意的块注释。

*---------------------------------------------------------*/
```

- Javadoc 注释 – 这是另一种特殊的块注释，它以正斜杠开头，后跟着一对星号 `/**`。这些注释通常用作自动生成类 API 的方法，以下是编写 Javadoc 注释的通用指南：

并没有实际上固成不变的规则，因为优秀的程序员会编写良好的代码，使代码能够自我文档。

- 确保你的注释与代码一致；如果你更新了代码，必须记住同样更新注释。

- 永远不要写只重复代码内容的注释。注释应该描述代码做了什么以及为什么这样做，而不是如何实现的：

```java
g++;      // 将 g 增加 1
```

- 如果你有可能引起困惑的代码，要么对其进行注释，或者更好的是重写它使其看起来不困惑。

- 在每个文件的开头，添加一个粗体注释，其中包含你的名字、日期、程序的用途以及如何执行：

```
/*----------------------------------------------------------------

*  作者：       Sharon Stone

*  编写时间：    5/12/2014
*  最后更新：12/17/2006
*

*  编译：       javac HelloWorld.java
*  执行：       java HelloWorld
* 

*  打印 "Hello, World"。这是每个人
*  都会学习的第一个程序
*  % java HelloWorld
*  Hello, World

*

*----------------------------------------------------------------*/
```

- 在任何你重要的变量名（包括实例变量）处，使用 `//` 注释进行说明，并确保注释在垂直方向上对齐。

```java
private double rx, ry;    // 位置
private double q;         // 电荷
```

- 每个方法都必须编写注释，说明该方法的功能，包括它需要什么输入、输出是什么以及是否有任何副作用——如果有，请列出。你的注释必须包含参数名。

```java
/**
*  此方法将使用 Knuth 的洗牌算法来
*  以随机顺序重新排列数组中的所有元素

 *
*  如果为 null，将抛出 NullPointerException
*/
public static void shuffle(String[] a)
```

# 第 4 章：Java 文件

Java 中另一个为了效率而必须正确处理的要部分是如何使用文件。首先，每个 Java 文件必须有 `.java` 扩展名。在本章中，我们还将简要查看语句、类、方法、类型、变量和数字的布局。如果你想让你的代码有效，还必须正确处理以下几点：

- 每个文件的内容必须控制在 80 列以内。这是打印机、终端模拟器、编辑器和调试器的通用标准。如果你的文件要与其他开发者共享，你必须遵守这一限制，否则可读性将变得很差——当你将一个不符合此标准的文件传递给其他开发者时，会出现一些你可能并不希望存在的换行。

- 避免使用特殊字符，如分页符和 `TAB`。当这些特殊字符在跨开发者和跨平台共享的文件运行时，会给调试器、编辑器、终端模拟器和打印机带来麻烦。

- 如果折行未完成，必须使其显而可见。例如：

```java
totalSum = a + b + c +
           d + e;

method(param1, param2,
      param3);

setText ("长行拆分为" +
          "两个部分。");

for (int tableNo = 0; tableNo < nTables;
      tableNo += tableStep) {
  ...
}
```

当你超过 80 列的限制时就会发生折行，虽然很难给出关于如何折行的精确规则，但上面的示例应该给你一些直。。根据经验法则：

- 换行应该出现在逗号之后

- 换行应该出现在运算符之后

- 新行应该与前一行中表达式的起始位置对齐

## 语句 (Statements)

### 导入和包语句 (Import and Package Statements)

- 包语句（Package statements）始终是文件中的第一个语句，每个文件必须属于一个指定的包。通过将所有文件放在指定的包（而不是默认 Java 包）中，可以强制执行 Java 的面向对象编程。

- 导入语句必须放在包语句之后。它们还应该进行排序，使得基础包在前面，然后是所有相关的包。每组之间应留一个空行：

```java
import java.io.IOException;
import java.net.URL;
import java.rmi.RmiServer;
import java.rmi.server.Server;
import javax.swing.JPanel;
import javax.swing.event.ActionEvent;
import org.linux.apache.server.SoapServer;
```

导入语句的位置将由 Java 强制执行。通过对包进行排序，当导入很多时更容易浏览，也更容易确定对当前包的任何依赖关系。将包分组在一起可以使其不复杂。

- 始终显式列出导入的类：

**正确示例：**

```java
import java.util.List;
```

**错误示例：**

```java
import java.util.*;
import java.util.ArrayList;
import java.util.HashSet;
```

当你显式导入类时，你为类提供了更好的文档价值，同时也使其更容易理解和维护。

### 接口和类 (Interfaces and Classes)

确保所有的接口和类声明按以下方式组织：

- 接口或类文档

- 接口或类语句

- 静态或类变量，顺序为：Public; Protected; 无访问修饰符; Private

- 实例变量，顺序为：Public; Protected; 无访问修饰符; Private

- 构造函数

- 方法

使类元素的位置可预测，从而降低复杂度。

### 方法 (Methods)

按此顺序放置方法修饰符：

- `<访问> static synchronized <特殊> final`

如果有，第一个修饰符始终应该是 `<访问修饰符>`：

**正确示例：**

```java
public static double square(double a);
```

**错误示例：**

```java
static public double square(double a);
```

访问修饰符是 `public`、`private` 或 `protected`，特殊修饰符包括 `transient` 和 `volatile`。在所有这些内容中，最重要的学习点是将访问修饰符放在开头 —— 这是一个非常重要的修饰符，它必须在你的方法声明中突出。其他修饰符的顺序并不重要。

### 类型 (Types)

- 所有类型转换都应该是显式进行的；你不应该依赖隐式转换：

**正确示例：**

```java
floatValue = (int) intValue;
```

**错误示例：**

```java
floatValue = intValue;
```

通过这样做，你表明你完全意识到正在使用的所有不同类型，并且这种混合是有意为之。

- 将数组修饰符附加到类型上，而不是变量：

**正确示例：**

```java
int[] a = new int[20];
```

**错误示例：**

```java
int a[] = new int[20]
```

数组性不是变量的特征，不知道为什么 Java 允许这样做，它本应该附加到基本类型上。

这是为了确保变量始终有效。在某些情况下，可以在声明变量的位置将其初始化为适当的值——在这种情况下，请让变量保持未初始化状态，而不是将其初始化为一个假值。

*   永远不要让你的变量具有双重含义

    通过这样，你所有的概念都将被唯一表示，并且错误出现的概率会降低。

*   永远不要将类变量声明为公有

    Java 的核心概念之一是隐藏和封装信息。将类变量声明为 `public` 违反了这一点，因此请使用访问函数和私有变量。这其中只有一个例外——如果一个类是一个没有行为的数据结构。在这种情况下，你可以将实例变量设为公有。

*   在声明数组时，将括号放在类型旁边：

    良好的示例：

    ```
    double[] vertex;
    ```

    坏的示例：

    ```
    double vertex[];
    ```

    良好的示例：

    ```
    int[] count;
    ```

    坏的示例：

    ```
    int count[];
    ```

    良好的示例：

    ```java
    public static void main(String[] arguments)
    public double[] computeVertex()
    ```

    有两个原因。第一，正如我们之前提到的，数组性并不是变量的特性，它是附属于类的。第二，当从方法返回数组时，你不能将括号放在类型以外的任何地方。

*   尽可能缩短变量的寿命

    这有助于更容易控制副作用和变量的影响。

## 循环

*   仅在 `for()` 结构中包含循环控制语句：

    良好的示例：

    ```
    sum = 0;
    ```

    坏的示例：

    ```java
    for (i = 0, sum = 0; i < 100; i++)
    for (i = 0; i < 100; i++)
    sum += value[i];
    sum += value[i];
    ```

    这增加了可读性并使维护变得更容易。始终明确区分循环内部的内容和控制循环的内容。

*   不要在循环紧开始前才初始化循环变量

    良好的示例：

    ```
    isDone = false;
    ```

    坏的示例：

    ```java
    bool isDone = false;
    while (!isDone) {
    }
    ```

*   避免使用 `do-while` 循环

    这些循环没有普通的 `while` 和 `for` 循环那样易读，因为条件位于底部。这意味着读者必须扫描整个循环才能理解其作用域。你实际上不需要使用 `do-while` 循环，因为它们可以很容易地写成标准的 `while` 或 `for` 循环。减少使用的构造结构数量可以增强可读性。

*   避免在循环中使用 `continue` 和 `break`

    你应该使用它们的唯一理由是它们比更结构化的等效代码具有更好的可读性。

### 条件判断



*   避免使用复杂的条件表达式；更好的选项是使用临时布尔变量

良好的示例：

```java
bool isFinished = (elementNo < 0) || (elementNo > maxElement);
bool isRepeatedEntry = elementNo == lastElement;
if (isFinished || isRepeatedEntry) {
}
```

坏的示例：

```java
if ((elementNo < 0) || (elementNo > maxElement) || elementNo == lastElement) {
}
```

当你将布尔变量赋值给一个表达式时，你的程序就获得了自动文档，它的结构会更合理，更容易阅读和调试。

*   将名义情况放在`if`语句的`if`部分，将异常情况放在`else`部分

```java
boolean isOk = readFile(fileName);
if (isOk) {
}
else {
}
```

确保异常情况不会覆盖执行应该采取的正常路径；这是一个重要的点，不仅是为了可读性，也是为了性能。

*   将条件判断放在另起一行

良好的示例：

```
if (isDone)
```

坏的示例：

```
if (isDone) doCleanup();
doCleanup();
```

我们这样做是为了调试的考虑。如果你将它们放在同一行，将无法清楚测试结果是真是假。

*   避免在条件语句中使用可执行的语句

良好的示例：

```java
InputStream stream = open(fileName, "w");
if (stream != null) {
}
```

坏的示例：

```java
if (stream = open(fileName, "w")) {
}
```

### 数字

*   避免使用魔数字。除`0`之外的任何数字都应该是命名常量

良好的示例：

```
final int TEAM_SIZE = 11;
```

坏的示例：

```
players = 11;
```

*   始终在小数点前放置一个数字

良好的示例：

```
double total = 0.5;
```

坏的示例：

```
double total = .5;
```

*   使用类名引用静态方法或变量

良好的示例：

```
Thread.sleep(1000);
```

坏的示例：

```
thread.sleep(1000);
```

### 空格

空白符是编码的另一个重要部分，特别是知道在何时使用它。通用规则是：

*   始终在运算符周围留空格

*   在保留字后后留一个空格

*   在逗号后留一个空格

*   在冒号周围留空格

*   在`for`语句中的分号后留一个空格

良好的示例：

```
a = (b + c) * d;
```

坏的示例：

```
a=(b+c)*d;
```

良好的示例：

```
while (true) {
}
```

坏的示例：

```
while(true){
}
```

良好的示例：

```
doSomething(a, b, c, d);
```

坏的示例：

```
doSomething(a,b,c,d);
```

良好的示例：

```
case 100 :
```

坏的示例：

```
case 100:
```

良好的示例：

```
for (i = 0; i < 10; i++) {
}
```

坏的示例：

```
for(i=0;i<10;i++){
}
```

通过执行所有这些，你让每个语句的组成部分脱颖而出，增加了可读性。虽然很难为你提供一份完整的空格使用列表，但上面的示例应该给你一些启发。

*   如果方法名后面还有另一个名称，在方法名后使用一个空格

```
doSomething (currentFile);
```

这确保了每个单独名称都脱颖而出并更容易阅读。如果方法名后面没有名称，请省略空格，因为名称是显而易见的。

```
(doSomething())
```

这里还有另一种方法——在左括号后留一个空格。某些这样做的人会在右括号前也留一个空格，但这并不是真正需要的。尽管它确实能让事物更加突出，但这样做并没有害。

示例——两个空格：

```
doSomething( currentFile );
```

示例——一个空格：

```
(doSomething( currentFile))
```

*   用空行分隔代码块中的所有逻辑单元

```java
// 创建一个新的单位矩阵
Matrix4x4 matrix = new Matrix4x4();

// 为了提高效率预计算角度
double cosAngle = Math.cos(angle);

double sinAngle = Math.sin(angle);
```

```
// 将矩阵指定为旋转变换

matrix.setElement(1, 1, cosAngle);
matrix.setElement(1, 2, sinAngle);
matrix.setElement(2, 1, -sinAngle);
matrix.setElement(2, 2, cosAngle);

// 应用旋转

transformation.multiply(matrix);
```

通过在每个逻辑单元之间留白，你可以让代码更具可读性。块通常以注释开头，如上方所示。

*   使用三个空行来分隔每个方法

    通过将间距扩大到方法内部间距，所有的方法将脱颖而出

*   在声明中将变量左对齐

```java
TextFile  file;
int       nPoints;
double     x, y;
```

这使得代码更易读，而且由于它们是对对齐的，你能够更好地看到变量类型。

*   在任何让代码更具可读的地方对语句对齐

```java
if      (a == lowValue)    compueSomething();
else if (a == mediumValue) computeSomethingElse();
else if (a == highValue)  computeSomethingElseYet();

value = (potential        oilDensity)  / constant1 +
        (depth               * waterDensity) / constant2 +
        (zCoordinateValue * gasDensity)  / constant3;

minPosition     = computeDistance(min,     x, y, z);
averagePosition = computeDistance(average, x, y, z);

switch (phase) {
  case PHASE_OIL  : text = "Oil";  break;
  case PHASE_WATER : text = "Water"; break;
  case PHASE_GAS  : text = "Gas";  break;
}
```

Java 代码中有很多地方可以添加空格来提高可读性，即使这样做会导致违反常见的通用指南。这些地方中的许多都与代码对齐有关，虽然很难提供通用指南的完整列表，但上面的示例应该对你有所帮助。

# 第 6 章：编码规范与禁忌

这些只是另外一些要做和不要的事，可以帮助你成为一名更高效的程序员：

*   只在方法的末尾使用`return`，绝不要在中间使用

    如果你在中间使用`return`，那么以后如果你想将该方法拆分成更小的方法，将会非常费力。它还会迫使你查看一个方法中的多个出口点。

*   不要使用`continue`

    同样，这会使以后将一个结构拆分为更小的结构或方法变得困难，并迫使你查看一个结构中的多个终点。

    原因：使用`continue`会导致以后很难将该结构拆分为更小的结构或方法。它还迫使开发者考虑一个结构的多个终点。

*   使用单独的行进行自增或自减；永远不要将它们组合

    将自增或自减运算符组合到方法调用中会增加阅读难度，对于修改代码方面经验较少的程序员来说是不利的。

    坏的示例：

    ```java
    foo(x++);
    ```

    良好的示例：

    ```java
    foo(x);
    x++;
    ```

    坏的示例：

    ```java
    y += 100 * x++;
    ```

    良好的示例：

    ```java
    y += 100 * x;
    x++;
    ```

*   尽可能在变量要使用的地方附近声明它。

    示例 1：

    ```java
    int totalWide;
    int firstWide = 20;
    int secondWide = 12;
    firstWide = doFoo(firstWide, secondWide);
    doBar(firstWide, secondWide);
    totalWide = firstWide + secondWide;      // 错误！
    ```

    示例 2：

    ```java
    int firstWide = 20;
    int secondWide = 12;
    firstWide = doFoo(firstWide, secondWide);
    doBar(firstWide, secondWide);
    int totalWide = firstWide + secondWide;      // 正确！
    ```

    示例 3：

    ```java
    int secondWide = 12;
    int firstWide = doFoo(20, secondWide);
    doBar(firstWide, secondWide);
    int totalWide = firstWide + secondWide;      //更好！
    ```

    引用：

    “任何傻瓜都能写出计算机能懂的代码。优秀的程序员写出人类能懂的代码。” - Martin Fowler

    与其试图记录一个复杂算法是如何执行的，不如从一开始通过添加标识符让算法更具可读性。如果将来算法被更改但文档没有更新，这将非常有帮助。

    示例：

    与其这样做：

    ```java
    if (hero == theTick) && (sidekick == arthur) || (sidekick == speak) )
    ```

    不如这样做：

    ```java
    boolean isTickkick = (sidekick == arthur) || (sidekick == speak);
    if (hero == theTick) && isTickkick )
    ```

    或者，与其这样做：

    ```java
    public static void happyBirthday(int age) {
      // 如果你在美国，某些生日是特殊的：
      // 16 (甜蜜 16 岁)
      // 21 (成年)
      // 25, 50, 75 (世纪纪念)
      // 30, 40, 50, 75
      if (age == 16 || age == 21 || age == 25 || age == 50 || age == 75 || age == 30 || age == 40) {
        // 某些逻辑
      }
    }
    ```

    （注：原文示例中`birthday`部分似乎不完整，此处已根据语境翻译并补全逻辑结构）

    注：由于您提供的文本在`birthday`处截断，上述翻译保持了逻辑的连贯性。

    *注：由于您提供的原始文本在结尾处截断，我已根据上下文逻辑进行了翻译和对齐。*

另一个常见的错误；由于 Java 是一种区分大小写的语言，如果你使用了错误的大小写，它将无法识别。例如，如果你写了`string`而不是`notString`，你将得到类似这样的错误信息：

`Line nn: Class xxxx not found in type declaration.`

在这里，`xxxx`是大小写错误的类名。

## 在变量中使用错误的大小写

同样的情况也适用于这里；变量也是区分大小写的，如果你尝试将一个名为`linkEdit`的变量声明为`int`，然后尝试在类中引用它，你将得到类似这样的错误信息：

`Line nn: Undefined variable: xxxx`

在这里，`xxxx`是拼错误的变量名。

## 编写类方法时使用了错误的格式

类方法总是以这种形式编写：

`ClassName.MethodName(Argument(s))`

最常见的错误之一是漏掉类名，这将抛出类似这样的信息：

`Line nn: '}' expected`

## 错误地指定方法参数

在定义类时，每个参数都应该以类名作为前缀

```java
public void tryIt(int a, int b, URL c)
```

比较常见的错误之一（特别是如果你是从其他编程语言转向 Java 的话）是没有为**所有**参数加上类型前缀。例如取：

```java
public void tryIt(int a, b URL c)
```

这将生成类似这样的错误信息：

`Line nn: Identifier expected`

## 忘记向对象发送消息

这是另一个对于面向对象编程（oop）或面向对象编程的新手来说常见的错误。假设你有一个`tryIt`方法；它有两个`int`参数并将其返回一个`int`值。如果假设该方法是向一个对象发送消息，我们会这样写：

```java
int newVal = destination.tryIt(arg1, arg2)
```

这些参数（即`ints`）在这段代码中已经声明了，但如果你像下一个示例那样写：

```java
int newVal = tryIt(destination, arg1, arg2)
```

你将得到类似这样的错误信息：

`Line nn: ')' expected`

## 将 == 视为值等价性

我们使用`==`来比较标量的值，而当你将其应用于对象时，它将改为比较地址。例如，让我们看一个`if`语句：

```java
if(newObj1 == newObj2){
    ...
}
```

这执行由 …表示的代码，但**仅**当第一个对象与第二个对象具有相同地址时才会执行。当它们的地址不同但实例变量值相同时，你将得到 false 的评估结果。这不会产生任何语法错误，但你会在执行程序时看到它。

## 没有在方法中放入 void

如果一个方法执行了某个操作但不返回任何结果，你需要在方法名之前插入`void`关键字。如果你不这样做，你可能会看到类似下面的错误信息：

`Line nn: Invalid method declaration; return type required`

## 没有在 case 语句中放入 break

这在过程化语言和面向对象的语言中都很常见。如果你想让 case 语句结束并退出，你必须在 case 语句的末尾放置一个`break`语句。如果你不放置`break`语句，执行将继续到你漏掉`break`语句的下方分支。

## 没有在方法中放入 return

如果一个方法返回一个值，方法体中至少应该有一个`return`语句返回正确的类型类型。这样做不当会导致类似这样的错误信息：

`Line nn: Return required at end of xxxx`

在这种情况下，`xxxx`是没有返回的方法。

## 将实例变量声明为 private 并在另一个类中通过名称引用它

当你将实例变量声明为`private`时，你无法在类外部通过其名称访问它。唯一的方法是使用在定义实例变量的类内部声明的方法。你将看到类似这样的错误信息：

`Line nn: Variable xx in class xxxx not accessible from class yyyy`

在这个示例中，`xx`是私有变量，`xxxx`是定义变量的类，`yyyy`是引用该变量的类。

## 在赋值之前使用变量

这是过程化和面向对象语言中的另一个常见错误。在 Java 中，标量被初始化为默认值或零，因此不会指示任何错误。如果有错误，它们将通过超出边界的数组或 false 结果显示出来。对象被初始化为`null`，如果你尝试引用一个未初始化的对象，它将在运行时被捕获。

## 假设消息将生成错误的值类型

这是使用 Java 包时的另一个常见错误。一个例子是使用一个会交付带有数字的字符串的方法，但将其处理为整数。`java.lang.Integer`内部的`getInteger`方法将交付整数，如果你尝试将该值作为`int`使用（例如），你会看到类似这样的错误信息：

`Line nn: Incompatible type for declaration can't convert xxxx to yyyy`

## 混淆前置和后置运算符

后置运算符（如` `和`++`）用于获取它们所应用的变量的旧值。前置运算符用于新值。例如，如果`x`是`45`且你有以下语句：

```java
y = ++x
```

`y`将是`46`。然而如果执行以下语句：

```java
y = x++
```

`y`将是`45`。你在编译时会看到这些错误。

## 忘记如果参数是对象，则是按引用传递

当使用对象作为方法参数时，传递的是地址而不是值。这意味着值可以赋值给这些参数。将它们作为值处理不会特别引起错误，但你还没有正确使用对象。

## 忘记标量是按值传递给方法



如果标量是按值传递给方法，它们不能作为值处理。虽然这不会产生语法错误，但如果你编写这样的代码，它将在运行时出现。

## 没有正确为数组和字符串使用 size

`size`是与字符串和数组相关的实例变量。如果你通过编写类似的内容来混淆它们：

```java
arrayVariable.size()
```

或者

```java
stringVariable.size
```

第一个示例将给你一个错误信息：

`Line nn: Method size() not found in class Object`

而第二个示例将给你一个错误信息：

`Line nn: No variable size defined in String`

## 使用不存在的构造函数

使用未定义的构造函数是一个常见错误。例如，你可能有一个类拥有以下构造函数——`one int`、`two int`、`three int`，但你可能使用了`four int`构造函数。你在编译时会看到这个：

`Line nn: No constructor matching xxxx found in class yyyy`

在这个示例中，`xxxx`是该构造函数的签名，`yyyy`是你应该定义它的类。

## 在同名的构造函数中调用构造函数

例如，假设你定义了一个名为`x`的类，带有一个`one int`构造函数和一个`two int`构造函数。在`two int`构造函数你引用了参数`x`，这将引发错误：

`Line nn: Method xxxx not found in yyyy`

在这个示例中，`xxxx`是带有参数的构造函数名，`yyyy`是定义它的类名。解决此问题的答案是使用`this`关键字。

## 假设二维数组将在 Java 中直接实现

会导致错误的代码，如：

```java
int [,] arrayVariable = new [10,20] int
```

在 Java 中，这是非法的，你会看到这样的错误：

`Line nn: Missing term`

和：

`Line nn: ']' expected`

多维数组可以在 Java 中实现，但必须将其处理为包含另一个单维数组的单维数组，以此此类推。

## 将标量视为对象

标量（如`float`和`int`）不是对象，但当你将它们存入`Vector`时，你可能想像对待对象一样对待它们，如下：

```
Vector vec = new Vector();
vec.addElement(12);
```

这将导致如下语法错误：

```
Line nn: No method matching xxxx found in yyyy
```

在此示例中，`xxxx`是方法名，`yyyy`是期望对象的类名。要解决这个问题，请使用`java.lang`中找到的对象包装类将它们转换为对象。

## 混淆标量及其对应的对象类型

当你使用像`int`这样的标量时，编写一段假设它可以被像对象一样处理的代码并不困难。例如：

```java
int y = 22;
Integer x = y;
```

将会抛出如下的错误信息：

```
Line nn: Incompatible type for declaration. Can't convert xxxx to yyyy
```

在此示例中，`yyyy`和`xxxx`都是类名。

## 主方法头部类型不正确

Java 程序的执行需要以以下内容开头的方法声明：

```java
public static void main (String []args){
```

如果该行中的任何内容输入不正确或漏掉了某个关键字，你将在运行时遇到错误。假设你漏掉了`static`关键字，将在运行时生成如下的错误信息：

```
Exception in thread main.....
```

## 结论

感谢感谢阅读本书！

希望这本书能够帮助你理解如何整理你的 Java 代码，以及如何编写更整洁、更规范的代码，以实现更有效高效的编程。

下一步是练习。坚持练习，因为这是你进步的唯一途径。学习像`Java`这样的计算机语言，诀窍在于定期练习，因为技术会过时，新的编码规则和风格每天都会涌现。如果你跟不上节奏，你会发现自己每次都不得不回到基础。

最后，如果你喜欢这本书，我想请你帮个忙，能否请你在 Amazon 上为这本书留个评价？我将不胜感激！

感谢并祝你好运！

## 关于作者

Charlie Masterson 是一位计算机程序员和导师，他开发过多款应用程序和计算机程序。

作为一名计算机科学学生，他很早就对编程产生了兴趣，但对学习极其复杂的课题感到过沮丧。

Charlie 想要一种能够让他轻松学习并提高编程技能的教学方法。他很快发现了一系列让他学得更快、更好的教学课程。

通过同样的方法，Charlie 成功学习了不同的编程语言，现在正通过编写书籍来教授这些知识。

通过他编写的计算机编程书籍，他希望提供巨大的价值，并帮助对计算机相关主题感兴趣的读者。
