
# Java 编程初学者指南：速成课程

## 推荐语

> “我想读的书。” — [Matz](http://twitter.com/yukihiro_matz/status/3875573878)，Ruby 语言的创造者
>
> “我真的很喜欢这本书。” — [Jeremy Ashkenas](http://coffeescript.org/)，CoffeeScript 语言的创造者

想创建一个编程语言，但不想读那些昂贵又无聊的[1000 页书籍](http://amzn.com/0321486811)吗？好吧，你并不孤单……

[点击获取！](http://1071173znfarcld6m3q4q25z32.hop.clickbank.net/)

# 引言

恭喜你下载了 Java，感谢你的支持。

后续章节将讨论 Java 的工作原理以及需要了解的知识，以便你在使用 Java 时获得最佳体验。

编程并非易事，需要花费大量的时间和耐心。如果第一次尝试没有成功，请不要气馁，它最终会成功的。

我想告诉你，Java 将以你可能无法意识到的方式对你有益。Java 可以帮助你找到新工作，甚至在你目前的工作中晋升，因此学习 Java 对你的职业和个人层面都是大有益的。

市场上有许多关于这个主题的书，再次感谢你选择这一本！我们已尽全力确保它包含尽可能有用的信息，请尽情享受！

# 第一章：什么是 Java

我发现学习 Java 最难的部分是在编写我想要写的代码之前需要安装哪些内容。如果我没有所有的程序，那么我就是在给自己找麻烦，因为我将无法正常运行程序。

## 虚拟机 (VM)

Java 有一个可以独立运行的平台，不需要其他程序的辅助。因此，它可以在我想使用的任何操作系统上运行。这归功于 Java 创建者开发的虚拟机。

虚拟机有助于确保我的代码被正确处理。不仅如此，如果没有安装虚拟机，Java 代码将无法运行。

Oracle 是创建 Java 的公司，在他们的网站上提供了任何 Java 相关程序的下载链接，例如 Java 虚拟机，称为 Java 运行环境（`JRE`）。

我首先需要检查电脑是否已经安装了 Java 运行环境，因为很多电脑都预装了 Java。为了做到这一点，我将访问 Oracle 网站并点击写有“我有 Java 吗？”的框。点击此链接将扫描我的电脑并告诉我是否安装了 Java。

如果我没有，我就可以下载并安装到电脑上，这样我就可以编写想要的代码了。

## 软件开发

安装 Java 后，它将像任何其他程序一样在我的电脑上运行。然而，在我编写代码之前，我必须下载开发工具包（`SDK`）。

该工具包将是标准版，并将下载 `NetBeans` 程序。虽然由于文件较大，下载将花费很多时间，但一旦下载完成，代码就可以写入程序中，以便我创建自己的 Java 程序。

## Java 的内部原理

当我为 Java 编写代码时，我将使用文本编辑器。我的代码被称为源代码（`Source code`），当我保存工作时，我会使用 `.java` 后缀进行保存。

保存文件的同时，我将启动 `javac`，这样我就可以创建类文件了。感谢 `NetBeans`，我将使用它自己的软件运行程序，而无需打开多个窗口来输入命令并运行它们来测试我的代码。我可以在一个窗口内完成所有操作。

# 第二章：NetBeans 程序

当我第一次打开 `NetBeans` 时，它会向我展示如何使用。程序加载后，我将看到创建的项目。集成开发环境（`IDE`）允许我查看创建的项目。当我选择项目名称旁的加号时，我将看到所有文件夹。文件夹也会展开，以便我看到代码存储的位置。

我的代码将显示在右侧的文本区域。如果我没有看到代码，我需要双击项目来强制代码出现，以便我对其进行操作。

文件名和类名必须匹配，否则 Java 将无法以预期方式运行程序。在编译代码以使其正常运行时，我最终会遇到错误。

## Java 注释

一旦我创建一个新项目，我将看到一些灰色的文本区域，这些文本通常带有斜杠或星号。灰色文本是程序在运行代码时忽略的注释。我可以在注释中输入任何我想要的内容，这些注释不会被任何编写代码的人看到。大多数情况下，这些注释会解释代码的运行情况，以便其他程序员进行维护。

### 示例

```java
// 我创建了一个注释
// 这是我的注释开始的地方
// 然后在这里继续，因为它是一条长注释
```

```java
/* 我在这里创建了另一种类型的注释

这里它延伸到了另一行

*/
```

我还可以使用 `Javadoc` 注释来输入注释。这些注释将以正斜杠后跟两个星号开头，并以单星号和一个斜杠结束。然而，我创建的每一行前面都必须有一个星号，以便被判定为注释。

`Javadoc` 将使用文档代码中的注释，这样当代码被转换为其他人使用的 `HTML` 页面时，代码就会被解释。

我需要在 `NetBeans` 菜单中生成一个 `Javadoc`，但由于我还没有写任何代码，所以我的窗口里什么都看不见。`NetBeans` 会自动生成注释，以便我看到一个示例，然后我可以删除这些注释，从而插入我自己的注释。

## Java 代码结构

从代码将如何结构来看，当我查看代码时，包名（`package name`）将出现在最前面。这一行将以分号结尾，如果我不加这个分号，程序将无法被编译，因此它将无法运行。列在包名之后的是类名（`class name`）。

类名的写法将像代码段一样被设置。我必须使用大括号 `{ }` 来指示代码从哪里开始到哪里结束。括号内的所有内容都将被视为由 Java 执行的代码段（`code segment`）。

在编写代码时，我需要包含 `main` 关键字，这样 Java 就能知道代码应该从哪里开始执行。这与大括号非常相似。如果我不小心忘了 `main` 关键字，程序将给我返回一条错误信息。

## 运行程序

任何 Java 程序都将在一个输出窗口中运行，该窗口与我输入所有代码的窗口不同。这意味着我不需要打开任何其他窗口就可以运行我的代码。一切都在 `NetBeans` 内部运行。

在 Java 中运行程序最简单的方法是按下 `F6`，这会自动运行程序，这样我就不会意外关闭我的程序。但是，如果不想这样做，我一直可以进入菜单并选择“运行项目”（`run project`）按钮。

如果所有其他方法都失败了，我可以在工具栏上找到一个绿色按钮，运行程序的方式和我可能选择的任何方法相同。不过，我需要确保运行的是正确的代码，特别是当我处理过多个编码项目时。为了做到这一点，我可以右键点击我想要运行的项目。

# 第三章：操作 Java 数据

Java 与任何其他编程语言一样，允许我操作输入到程序中的数据，同时程序将其存储在内存中。这些数据被称为文本（`text`）、对象（`objects`），甚至是数值（`amounts`）。我必须为我使用的任何数据进行命名，而且这些数据可以随时重命名。然而，名称和值将是 Java 变量（`Java variables`）。

## Java 数值

数值可以使用整数或浮点数存储在 Java 内存中。浮点数将用 `float` 关键字存储，而整数将用关键字 `int` 存储。

### 示例

```java
public static void main(String[] args) {
    int last_amount;
    System.out.println("I wrote Java code!");
}
```

我需要与程序通信，以便让它知道我想哪些整数保存到 Java 内存中；为了这样做，我将使用 `int` 关键字并在其后加一个空格。我将输入我想给这个变量命名的名称，但我必须遵循 Java 设定的一系列规则。

1. 我不能在变量名中使用关键字。如果单词在我的代码窗口中变成蓝色，那么这个词就是 Java 的关键字。
2. 我不能使用空格。这样做会导致返回错误代码，但我可以使用下划线和大写字母来像我平时使用空格那样来“分隔”单词。
3. 变量名的第一个字符不能是数字。如果我把数字拼写出来，那么是可以的，但使用实际的数字是不行的。
4. 完全小写的名称与带有大写字母的名称是不同的（区分大小写）。

当我想在变量名后放入一个整数时，我需要使用赋值运算符。

```java
public static void main(String[] args) {
    int last_amount = 10;
    System.out.println("I wrote Java code!");
}
```

浮点数示例：

```java
float first_value, twentieth_value, result;

first_value = 15.3f;
twentieth_value = 95.6f;
```

# 附录：创建你第一种编程语言的最佳系统

## 电子书

一份 100 页的 PDF 文档，详细介绍了核心概念并如何将其应用于 `Ruby` 自定义语言中（包含 `ePub` 和 `Mobi` 格式）。

## 练习题与答案

对语言提出的扩展建议，书末尾附有答案。

## 三种语言

使用 `Ruby` 和 `Java` 编写的三种语言的完整源代码。易于扩展和玩。

## 视频教程

逐步解释如何扩展 `JVM` 语言。



大多数关于编译器的书籍价格超过 100 美元，而且冗长无聊。我的系统包含一本书（有趣且直击要点）、练习题与答案、你可以随意使用的三种语言以及一个视频教程，仅需 39.99 美元。

如果你不满意，我甚至免费送给你。

[在此处获取！](http://1071173znfarcld6m3q4q25z32.hop.clickbank.net/)

# 第四章：数学及更多

## 算术

`Java` 与任何其他编程语言一样，可以用于数学计算。我将能够使用 `Java` 执行一些基础操作，它们的符号非常容易理解。

- 加法 – 加号 `+`
- 减法 – 负号 `-`
- 乘法 – 星号 `*`
- 除法 – 正斜杠 `/`

### 运算符优先级

无论我在 `Java` 中进行什么样的数学运算，我都必须确保将每个值都放在正确的位置，这样我就知道正在执行什么，以及执行的顺序是什么。

### 示例

```java
tenth_value = 5;
fifteenth_value = 654;
twohundredith_value = 54;
result = tenth_value - fifteenth_value + twohundredith_value;
```

该表达式将按照输入 `Java` 的顺序进行求值。发生的情况是，从 `5` 中减去 `654` 得到结果 `-649`，然后加上 `54`，得到总和 `-595`。

当我想让表达式中的某个部分优先时，我会在它周围加上括号。在运算顺序上，乘法和除法总是先执行。

## 字符串变量

`Java` 不仅会在内存中存储值，还会存储分配给变量的文本。当我想要存储一个字符时，我需要将关键字从 `int` 改为 `char`。

我将开始一个新项目，这个项目将用于字符串，因此我会将其命名为类似 `VarsStrings` 的名称，这样我就知道它是存放字符串变量的了。我还想确保勾选“创建主类”的复选框，这样我以后就不必这样做，也不会面临搞乱项目的风险。

一旦打开了文本框，我将删除程序自动在文本框内放置的所有注释，这样我现在就有了一个空白区域来处理了。要创建一个字符串，我需要使用 `String` 关键字，以便在详细编写我的变量名之前，`Java` 能够识别这不仅仅是纯文本。

### 示例

```java
String game_title;
```

字符串的值将通过等号赋值给新变量。我放在等号之后的数据将存储在双引号中。

### 示例

```java
game_title = "Raiders";
```

我也可以将脚本写在一行内，这样我在寻找潜在错误时，我的脚本看起来更易读。

```java
String game_title = "Raiders";
```

我会将这个游戏的创建者放在另一行，这样当它出现在用户所在的网站上时，它将带有游戏标题以及创建者信息，这样他们就能为自己的作品获得荣誉。

### 示例

```java
String creator_name = "Markus";
```

到此时，我就可以按照我希望用户看到的方式组合我的代码了。

```java
System.out.println(game_title + " " + creator_name);
```

我插入括号的内容将是我的变量。`+` 符号表示游戏标题和创建者姓名之间需要一个空格。

`char` 关键字需要小写，以便在内存中只存储单个字符。这也是我需要使用单引号而不是双引号的时候。如果我忘记使用双引号，我将得到程序的错误代码。

### 示例

```java
String game_title = "R";
```

虽然这是正确的输入

```java
char game_title = 'R';
```

但这将返回错误。

# 第五章：输入及以后

`Java` 包含了大型目录，允许我使用它们来确保我的代码被正确执行。当我必须引用目录时，我需要调用该目录的操作。

我发现的一个非常有用的类目录是 `Scanner` 类。只要我使用 `import` 关键字，我就可以从目录中调取任何类并将其用于我的代码中。

### 示例

```java
import java.util.Scanner;
```

这条语句需要放在告诉其他程序员正在使用哪个类的语句之前。

### 示例

```java
import java.util.Scanner;

public class VariablesForStrings {
}
```

脚本的导入部分允许 `Java` 知道它需要调取该类。一旦打开了文本框，我将删除程序自动在文本框内放置的所有注释，这样我现在就有了一个空白区域来处理了。

### 示例

```java
Scanner inputFromUser = new Scanner(System.in);
```

变量不能设置变量沿着字符串。变量。我将……

我将能够将变量放入那个类中。每当我看它时，它只不过是一段代码，在我成功创建一个对象之前，它什么也做不了。

### 示例

```java
String state_name;
state_name = user_response.next();
```

在用户输入了所需数据后，点号将弹出一个包含允许我使用的方法的列表。此时我需要做的是点击我想使用的方法，然后在行末尾输入一个分号。之后它是。

### 示例

```java
String state_name;
System.out.print("Type in the state that you currently reside in: ");
state_name = client_input.next();
```

在尝试从用户获取数据时，我将使用 `print` 而不是 `println` 函数。如果我想使用 `println`，我需要在数据产生结果后将鼠标移动到另一行。然而，使用 `print` 时，我能够留在我操作的同一行。

### 示例

```java
String city_name;
System.out.print("What city are you living in: ");
city_name = client_input.next();
```

虽然代码除了客户端响应外完全相同，但 `Java` 将数据移动到一个新变量中，这样我就不需要自己动手了。

### 示例

```java
String complete_name;
String where_you_live = state_name + " " + city_name;
System.out.println("You are living in " + where_you_live);
```

当我创建的程序运行时，`Java` 将暂停足够的时间让用户输入响应。在数据被放入内存后，输出将显示在屏幕上，为他们提供的体验变得“个性化”。

`Scanner` 类的作用是从用户那里获取信息，同时将用户的输入赋值给它所属的变量。

## 选项

当我尝试从程序用户获取所需的信息时，可以通过 `JOptionPane` 类获得一个选项列表供我使用。该类将出现在屏幕上，允许用户在显示其输入的内容之前输入适当的响应。

### 示例

```java
import javax.swing.JOptionPane;
```

这次我将不得不告诉 Java 我想在 `swing` 目录下使用哪个类。由于我不想修改已经写好的代码，我为这个方法创建了一个新项目。当我把代码放进去时，我注意到 `javax.swing.JOptionPane` 被加了下划线，就像是一个错误一样。但并不是错误，它将把数据重定向到需要存储的变量下。

### 示例

```java
String your_age;
your_age = JOptionPane.showInputDialog("Your age");
```

`JOptionPane` 允许我输入一个句号，这样我的选项列表就会出现。在这个列表中，我将通过双击来选择 `showInputDialog()`。这会在我的代码中放置括号，括号将用于放置我想显示给用户的消息。同样，我也需要使用双引号。

### 示例

```java
String your_age;
your_age = JOptionPane.showInputDialog("your age");
String your_birthday;
your_birthday = "You were born on " + month + " " + day;
JOptionPane.showMessageDialog(null, your_birthday);
```

这是我希望我的对话框再次出现的地方，并带有所有我可以使用的选项。括号中放入了 `null`，以便 Java 知道这个框与我刚刚创建的程序没有关系。最终产品文本中的标点符号将按照我在 Java 中输入的那样显示。

在我代码的末尾，会有一些我没有手动放进去的新代码。这些代码旨在告诉程序何时退出系统，因为它已经完全执行完毕。即使是这样做，存储在 Java 内存中的值和变量也将被存储，供下次使用程序时。

每当我的代码正确执行时，都会弹出窗口，向用户索取不同的数据，例如他们的姓名或年龄。当用户点击“确定”按钮后，输入将显示用户在框中输入的内容。这将导致程序退出系统，因为所有需要做的事情都完成了。

# 第六章：控制 Java 的运行

所有使用 Java 编写的代码都是所谓的“顺序编程”。在这种情况下，代码被输入，程序从上到下读取它，不会跳过我输入的任何行。但是，并不是所有的 Java 程序都是这样运行的。

有些脚本只在设置的条件满足时运行一次。例如，可能我不想让来自特定州的人进入我的网站，因此如果发现此条件为真，则程序将运行；但如果用户来自该州，程序将终止。通过使用条件逻辑，可以控制 Java 的运行。

最常见的条件语句是 `if` 语句。

## If

使用 `if` 语句，每当条件被触发时，代码就会执行，而无需等待用户执行某些操作。`if` 语句将是一个简单的脚本。

```java
if (expression) {
}
```

使用之前的示例，如果用户来自纽约，那么我不希望他们进入我的网站。与其输入实现此功能所需的全部代码，我将缩短脚本，以便我和其他程序员更易阅读。

### 示例

```java
if (clientState.equals("New York")) {
    // 此站点受限制
}
```

所以，如果我的用户不是来自纽约，那么在程序执行时，会有两组括号被 Java 跳过。但是，放在它们之间的任何代码都将被执行，但在此发生之前必须满足我设置的条件。

我学到的另一个简写技巧是，大于符号由一个指向右侧三角形表示。

### 示例

```java
if (clientAge > 18) {
    // 给用户的消息
}
```

即使对于那些不住在纽约的人，代码也是相同的。

## If/else

当 `if` 语句不再足够时，我将使用 `if else` 语句。

```java
if (condition) {
}
else {
}
```

这段代码的第一行将以 `if` 语句开头，后面跟着我设置的参数。括号将划分我的代码，使代码根据我的参数执行。第二部分将跟在 `else` 语句之后。所以，如果没有发生这种情况，就会执行这个。

使用 `if else` 语句与 `if` 语句一样，只是它有第二个表达式，落在新的一组括号之间。如果第一个条件没有满足，代码将被分流并通过第二个表达式运行，以检查它是否满足该条件。如果我漏掉了一个括号，我将收到错误代码。

```java
if (expression_one) {
}
else if (expression_two) {
}
else {
}
```

在 `if else` 内部可以设置的条件如下：

- 大于 (`>`)
- 小于 (`<`)
- 大于等于 (`>=`)
- 小于等于 (`<=`)
- 与 (`&&`)
- 或 (`||`)
- 等于 (`==`)
- 非 (`!`)

在 AND 条件下，将同时测试多个条件。

### 示例

```java
else if (user > 45 && user < 55) {
}
```

## 嵌套的 If

当我将一个表达式放在另一个内部时，我就是在将两者嵌套。这可以通过任何 `if` 表达式完成。

### 示例

```java
if (client < 55) {
    System.out.println("55 or less");
}
```

为了查看客户是否大于 45，我将在另一个放在第一个里面。

### 示例

```java
if (client < 55) {
    if (client > 45 && client < 55) {
        System.out.println("You are 46 to 54");
    }
    else {
        System.out.println("45 or younger");
    }
}
```

## Boolean

布尔值只允许为 `true` 或 `false`。如果是其他任何值，它们就不是布尔值。在处理布尔值时不需要使用 `int`、`String` 或任何其他关键字。相反，只需输入小写的 `boolean`，以确保后面的内容是布尔值。但我必须确保值是 `true` 或 `false`。我将使用两个等号 (`==`) 来评估表达式的值。

### 示例

```java
boolean client = true;
if (client == true) {
    System.out.println("the expression contains the truth");
}
else {
    System.out.println("this expression is false");
}
```

`if` 语句将检查变量以判断它们是否构成真的布尔语句。如果用户输入已经是真的，则将被检查是否为假。不需要说明该值不是假的，因为很容易看出该值实际上是真实的，反之亦然。

非运算符 (`!`) 也会在我创建布尔值时使用。

### 示例

```java
boolean client = true;
if (!client) {
    System.out.println("there is no truth");
}
else {
    System.out.println("this is the truth");
}
```

NOT 布尔语句的唯一区别在于 `!client` 表达式。该运算符将使用感叹号置于变量之前。一如既往，对变量进行测试以检查它是否为负值（假）。

由于 `client` 变量通常被设置为 `true`，因此会对它们进行测试，以检查是否存在任何 `false` 值。如果值被设置为 `false`，情况则完全相反。

# 第七章：分支语句与循环

在编写脚本时，我将使用 `switch` 语句，这样我为所使用的变量设置的值就有更广泛的选择范围。本质上，这些实际上是非常长且有些为复杂的 `if else if` 语句。

一个 `switch` 语句看起来如下：

```java
switch (variable_to_test) {
    case value:
        code_here;
        break;
    case value:
        code_here;
        break;
    default:
        values_not_caught_above;
}
```

用于 `switch` 语句的关键字是 `switch`，后面将紧跟一组括号。我想检查的变量需要放在我 `switch` 语句中括号的中间。不仅变量放在括号之间，语句的其他部分也是如此。`case` 关键字将检查程序需要审查的所有可能情况。

`case` 值将使用冒号而不是分号。程序中将发生的事件需要与值正确对应，以便代码能够按照预期方式运行。每当语句中添加一个新 `case` 时，都会使用 `break` 关键字。

`default` 值可以使用，但我并不一定需要使用。我可以为语句添加任何想要的值，以便在 `switch` 语句中进行评估。

### 示例

```java
public static void main(String[] args) {
    int user = 87;
    switch (user) {
        case 45:
            System.out.println("the price is 45 dollars");
            break;
        case 65:
            System.out.println("the price is 65 dollars");
            break;
        case 88:
            System.out.println("the price is 88 dollars");
            break;
        default:
            System.out.println("the price is 45, 65, or 88 dollars");
    }
}
```

`switch` 语句代码需要测试用户输入的整数。在这个示例中，`user` 变量已设置为 `87`，这告诉程序检查其内部的所有内容。每个 `case` 将被单独检查，以查看是否有与我设置的值匹配。找到匹配的 `case` 后，代码将停止，程序将终止。

超出范围的值即使被放置在 `case` 中，也无法通过测试。

### 示例

```java
case (user >= 55):
```

这个 `case` 无法使用，并将导致 Java 错误。但我可以使用像这样的 `case`：

```java
case 5: case 6: case 7:
```

使用的每个值都需要列出并进行检查。

## 循环

Java 的流是顺序的，就像书写书籍一样向下移动。但可以使用某些函数来改变流变为不同的内容。为了中断 Java 自然使用的流，我将创建一个 `loop`。通过 `loop`，程序将连续运行脚本行，直到被要求停止。

### 示例

```java
int subtraction = 100 - 5 - 3 - 4 - 8 - 6 - 2 - 9;
```

我并不总是想使用这种方法，但 `loop` 将一直运行直到满足我设置的参数。



# Java 循环与数组详解

## 循环结构

### `for` 循环
`for` 循环将使用 `for` 关键字。语法如下：

```java
for (beginning_value; last_value; increment_amount) {
    // code
}
```

### `while` 循环
`while` 循环将使用 `while` 关键字。语法如下：

```java
while (condition) {
    // code
}
```

### `do-while` 循环
`do-while` 循环将使用 `do` 和 `while` 关键字。语法如下：

```java
do {
    // code
} while (condition);
```

## 数组基础

在我正式选择了将使用的数据类型后，普通整数将被放在方括号中。方括号让 Java 知道正在使用的是数组而不是任何其他数据类型。数组使用 `new` 关键字配合类型声明（如 `int[]`），以确保数组被正确设置。之后，任何我想要放入数组的变量都可以被放在其中。

一旦我为数组设置了一个新对象，Java 就会知道我为数组分配了多少个空间。

### 示例：数组初始化

```java
int[] aryNums = new int[55];
```

这告诉 Java 在数组中将分配 55 个空间用于整数。有效索引范围从 0 到 54。

当我开始为这些位置赋值时，我将使用标准的索引赋值方式。

```java
aryNums[8] = 32;
```

数值 32 将赋值给数组中索引为 8 的位置。必须记住，数组索引必须从 0 开始。

### 示例：静态初始化

这样设置我的数组将使我处理起来更加方便。

```java
int[] aryNums = { 8, 5, 6, 2 };
```

这种方法在大括号内创建了数组，第一个值被放置在索引 0 处。类型声明后的方括号（`int[]`）标明这是一个整型数组。当我想使用 `new` 关键字时，这种方法也将用于字符串值和字符。

### 示例：字符串数组

```java
String[] aryStrings = { "Vampires", "Werewolves", "Hybrids", "Witches" };
```

这在 Java 中是可以运行的。

### 示例：布尔数组

```java
boolean[] aryBools = { true, false, false, true }; // 正确写法
```

直接使用 `Boolean[] aryBools = { yes, no, no, yes };` 是不通的（`yes`/`no` 非 Java 关键字，且基本类型 `boolean` 首选）。如果我想使用布尔值，正确的初始化方式如下：

```java
Boolean[] aryBools = new Boolean[] { true, false, false, true };
```

## 数组循环

数组的循环有其特殊的规则。数组中的值将使用数组语法进行赋值和访问。

### 示例：遍历数组赋值

```java
package prjarrays;

public class ArrayTest {
    public static void main(String[] args) {
        int[] ticket_prices = new int[65];
        int i;
        for (i = 0; i < ticket_prices.length; i++) {
            ticket_prices[i] = i + 1;
            System.out.println(ticket_prices[6]);
        }
    }
}
```

上面的数组将包含 65 个整数。循环将持续到达到这个数字为止，并且 `i` 将是一个小于数组大小的值。为了给我想要的位置分配值，我将使用索引赋值代码。

```java
ticket_prices[i] = i + 1;
```

当我将值放在方括号之间时，我使用的值并不是硬编码的，相反，每重复一次循环，索引变量都会增加。数组元素也会随着循环的索引而被依次赋值。循环总是从 0 开始，并在这个示例中一直增加到 64（即 `length - 1`）。

## 排序

我创建的数组可以使用 `Arrays.sort()` 方法进行排序。然而，我必须导入 `java.util.Arrays` 类。将使用 `import` 语句。

```java
import java.util.Arrays;
```

### 示例：数组排序

```java
package prjarrays;

import java.util.Arrays;

public class ArraysTest {
    public static void main(String[] args) {
        int[] aryNums = new int[9];
        aryNums[0] = 65;
        aryNums[1] = 54;
        aryNums[2] = 689;
        aryNums[3] = 654;
        aryNums[4] = 6543;
        aryNums[5] = 55;
        // 数组的库将与 sort 方法一起导入。
        Arrays.sort(aryNums);
    }
}
```

导入 `java.util.Arrays` 后，通过 `Arrays.` 可以访问其静态方法，`sort` 方法用于对数组进行原地排序。

## 字符串数组

字符串也可以放在数组中。

### 示例：字符串数组声明与赋值

```java
String[] aryString = new String[5];

aryString[0] = "I";
aryString[1] = "am";
aryString[2] = "made";
aryString[3] = "java";
aryString[4] = "yay";
```

循环将持续到达到 `aryString` 的长度。值将被显示。

### 示例：综合演示（排序数值数组并打印）

```java
package prjarrays;

import java.util.Arrays;

public class StringArrays {
    public static void main(String[] args) {
        int[] aryNums = new int[9];
        aryNums[0] = 65;
        aryNums[1] = 54;
        aryNums[2] = 689;
        aryNums[3] = 654;
        aryNums[4] = 6543;
        aryNums[5] = 55;
        Arrays.sort(aryNums);

        int i;
        for (i = 0; i < aryNums.length; i++) {
            System.out.println("num: " + aryNums[i]);
        }
    }
}
```

## 多维数组

多维数组以特定的方式排列，以告诉 Java 这是一个多维数组而不是普通数组。

### 语法

```java
int[][] aryAmounts = new int[8][33];
```

数组语法类似于普通数组，但现在有两组方括号让 Java 知道有多少行以及每行有多少列。行索引从 0 开始，列索引同样从 0 开始。

### 示例：二维数组赋值

```java
aryAmounts[0][0] = 60;
aryAmounts[0][1] = 1550;
aryAmounts[0][2] = 324;
aryAmounts[0][3] = 2333;
aryAmounts[0][4] = 23;
aryAmounts[0][5] = 3257;
aryAmounts[0][6] = 3225;
aryAmounts[0][7] = 332514;

aryAmounts[1][0] = 41;
aryAmounts[1][1] = 2035;
aryAmounts[1][2] = 5326;
aryAmounts[1][3] = 5354;
aryAmounts[1][4] = 4654;
aryAmounts[1][5] = 5032;
aryAmounts[1][6] = 653;
aryAmounts[1][7] = 644;

aryAmounts[2][0] = 1632;
aryAmounts[2][1] = 161;
```

### 示例：遍历二维数组（仅遍历第一维）

```java
int i;
for (i = 0; i < aryAmounts.length; i++) {
    System.out.println(aryAmounts[i]);
}
```
*注意：直接打印 `aryAmounts[i]` 会输出该行数组的哈希码/引用地址，通常需要嵌套循环遍历第二维以打印具体数值。*

## `ArrayList` 动态数组

我无法确定数组中的具体大小（或需频繁增删），但我可以使用 `ArrayList`，这样我就可以动态管理数据结构。我列表中的项可以添加或删除。但是，普通数组的大小是固定的，因为对于我创建的内容，我没有能力更改数组的大小。

当我设置一个数组列表时，我将不得不从 Java 的包中导入相关类。

### 语法

```java
import java.util.ArrayList;
```

在我引入了创建新对象所需的类后，我将使用以下语法实例化。

```java
ArrayList<Object> listTest = new ArrayList<>();
```
*注：建议使用泛型 `<Object>` 或具体类型，原文 `new ArrayList()` 为原始类型写法。*

在为列表创建对象时，不需要指定初始大小（不使用方括号指定容量，但可选构造函数参数指定初始容量）。

### 示例：添加元素

```java
listTest.add("and");
listTest.add("for");
listTest.add("but");
listTest.add(8); // 自动装箱为 Integer
```

括号中的任何内容都将被放在我的数组列表中。通过这种方法，我可以添加任何想要的对象。出现在列表中的前三个项是字符串对象。最后一个项是一个整数（自动装箱为 `Integer`）。

我列表中的所有项都可以通过它们的索引值找到。

### 示例：获取元素

```java
listTest.get(5);
```

数字 5 准确地告诉我需要去哪里找到我正在找的东西（索引 5 即第 6 个元素）。索引值总是像 Java 中使用的其他东西一样从零开始。

### 示例：删除元素

```java
listTest.remove(5); // 删除索引 5 处的元素
```

我也可以删除列表中的特定对象值（首次出现）。

```java
listTest.remove("but"); // 删除字符串 "but"
```

在删除项时，列表会自动调整大小（后续元素前移填补空位）。正因如此，我在删除对象时必须非常小心，否则我的列表索引将会发生巨大变化，我将不知道列表中的任何位置。所以，如果我删除了列表中的第二个项（索引 1），那么在删除之后，后面的项将在列表中向上移动（索引减 1）。

## 结论

感谢你读到 Java 的最后，希望它能为你提供启发，并能够为你提供实现目标所需的所有工具，无论你的目标是什么。

下一步是下载 NetBeans（或其他 IDE），并根据我提供的信息开始创建自己的 Java 程序。有些内容可能看起来很困惑，但练习得越多，就会变得越容易。

如果你发现这本书的任何部分让你困惑，请回去重读一遍。正如我在引言中所说的，编程并不容易，它不会在一夜之间让你学会。

不要因为你使用的某段代码不起作用就停止学习 Java。如果你这样做，你就永远不会知道自己哪里搞错了。相反，采取那个错误并从中学习，这样你就不必重复同样的错误了。

最后，如果你觉得这本书在任何方面都有用，非常感谢你在 Amazon 上的评价！

祝你好运！

---

# 加入成千上万创建了自己语言的编码者行列。

![createyourproglang.com/images/real_book.png](http://1.macoaff.pay.clickbank.net/)

## “获得一个涵盖了 JavaScript 95% 功能的语言非常有趣，而且工作量少得惊人。”

— [Jeremy Ashkenas](http://ashkenas.com/)，在阅读这本书后创建了 [CoffeeScript](http://coffeescript.org/)。

## “我喜欢这本书！它帮助我创建了自己的 Awesome-to-PHP 编译器。虽然它还不是一个全功能的编译器，但我编写它时非常有趣，并且学到了很多。”

— [Julien Desrosiers](http://twitter.com/jdesrosiers)，在阅读这本书后创建了 [Phlower](http://github.com/juliend2/phlower)。

## “我在大学期间没有机会学习语言内部原理，虽然我很感兴趣，但我发现它们的运行机制令人生畏。通过这门课程，我发现了一个关于词法器、解析器、解释器和编译器世界的简单但引人入胜的介绍，编程的一个全新世界向我打开了。强烈推荐。”

— [David Bolton](http://davidbolton.net/)

***

### 使用此系统创建的一些语言 ...

![CoffeeScript](http://coffeescript.org/) ![Fancy](http://www.fancy-lang.org/) [Savage](https://bitbucket.org/masonicboom/savage) [Rubby](http://rubby-lang.org/) ![Arendelle](http://web.arendelle.org/)

***

# 要么有效，要么免费。

## 不确定这个系统是否适合你？试一下吧，如果你不满意，我会把钱退给你，并且保留所有东西。

[在此处获取！](http://1071173znfarcld6m3q4q25z32.hop.clickbank.net/)

---

## 免责声明

以下重录的电子书目标是提供尽可能准确可靠的信息。无论如何，购买本电子书可以被视为同意以下事实：本书的出版者和作者对书中所讨论的话题并非专家，书中提出的任何建议或主张仅供娱乐之用。在采取书中支持的任何行动之前，应根据需要咨询专业人士。

此声明被美国律师协会和出版商协会委员会认为是公平且有效的，并在全美范围内具有法律约束力。

此外，传输、复制或复制以下任何作品（包括特定信息）都将被视为非法行为，无论是以电子形式还是印刷形式进行。这延伸到创建作品的二级或三级副本或录制品，只有在获得出版者明确书面许可的情况下才允许。保留所有权利。
