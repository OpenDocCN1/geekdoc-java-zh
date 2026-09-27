
# IBM SPSS Statistics Java 插件用户指南

> **注意**
>
> 在使用此信息及其支持的产品之前，请阅读第 27 页“注意事项”中的信息。

# 产品信息

本版本适用于 IBM SPSS Statistics 的第 26 版本发布 0、修改 0，以及后续的所有发布版本和修改，除非新版另有说明。

## 第 1 章 开始使用 Java 集成插件

IBM SPSS Statistics - Java 集成插件™ 允许开发人员创建 Java 应用程序，这些应用程序可以调用并控制 IBM SPSS Statistics 处理器，或者在 Java 中实现可以在 IBM SPSS Statistics 内部运行的扩展命令。扩展命令是使用外部语言（Python、R 或 Java）实现的 IBM Statistics 命令，它允许精通 Java 的用户与标准 IBM Statistics 语法的用户共享外部函数。

通过 IBM SPSS Statistics - Java 集成插件，你可以执行以下操作：

- 从活动数据集执行 IBM SPSS 命令。
- 从活动数据集读取数据。
- 获取有关活动数据集内数据的信息。
- 向活动数据集添加新变量并追加个案。
- 从语法命令获取输出结果。
- 创建以透视表和文本块形式存在的自定义输出。

IBM Statistics - Java 集成插件随 IBM SPSS Statistics 和 IBM Statistics Server 一起安装，无需单独安装或配置。对于 IBM SPSS Statistics 第 26 版本，IBM Statistics - Java 集成插件支持 Java 7 版本。

IBM SPSS Statistics - Java 集成插件旨在为开发者提供一个与 SPSS Statistics 引擎交互的 API。

### 从外部应用程序调用 IBM SPSS Statistics

以下是一个使用 IBM Statistics 创建数据集、计算描述统计并生成输出的简单示例。

```java
import com.ibm.statistics.plugin.*;

public class demo {
    public static void main(String[] args) {
        try {
            StatsUtil.start();
            String[] command = {
                "OMS", "FORMAT=HTML OUTPUT=output.html",
                "DATA LIST /salary.",
                "NEW DATA",
                "DESCRIPTIVES salary."
            };
            StatsUtil.submit(command);
            StatsUtil.stop();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

- 元素 `import com.ibm.statistics.plugin.*` 导入了 `com.ibm.statistics.plugin` 包中的所有类。
- `StatsUtil.start()` 方法启动 IBM Statistics 处理器。
- 字符串数组指定了 IBM Statistics 语法用于创建一个数据集并运行 `DESCRIPTIVES` 过程。命令语法通过 `StatsUtil.submit` 方法提交给 IBM Statistics。`DESCRIPTIVES` 过程的输出通过 `OMS` 命令路由到 HTML 文件。
- `StatsUtil.stop()` 方法停止 IBM Statistics 处理器，并应调用它以正确结束 IBM Statistics 会话。
- `Exception` 类是原生 `Exception` 类的子类，用于处理特定于 IBM Statistics - Java 集成插件的异常。可以继承该类为你的应用程序定义自定义异常。

### 在 Java 中创建 IBM Statistics 扩展命令

本主题描述了在 Java 中实现扩展命令的各个方面。关于创建扩展命令的详细信息，请参阅“Writing IBM Statistics Extension Commands”文章，该文章可在 IBM Statistics Predictive Analytics 社区获取：https://developer.ibm.com/predictiveanalytics/。

实现代码由 JAR 文件或类文件组成。

- 当使用 JAR 文件时，JAR 文件名必须与扩展命令相同且全为大写。对于多单词命令名称，在构造 JAR 文件名时应将单词之间的空格替换为下划线。JAR 文件必须包含一个与 JAR 同名的类文件，且该类不能属于任何包。
- 当使用独立的类文件时，必须有一个类与扩展命令名称相同且全为大写的类文件。

无论是使用 JAR 文件还是独立的 Java 类，与扩展命令具有同名的类文件都应包含以下内容：

- 一个该类的构造方法，该方法不带参数。
- 一个名为 `Run` 的公共静态方法，接受单个 `Hashtable` 参数，其指定方式如下：
  `Hashtable<String, Hashtable<String, Object>>`
- 一个实现命令的公共方法。

#### XML 命令语法规范

- 对于在 Java 中实现的扩展命令，`Command` 元素的 `Language` 属性应被设置为 "Java"。
- 对于使用 JAR 文件实现的 Java 命令，`Command` 元素的 `Mode` 属性应被设置为 "Package"。

#### Java 类示例

以下是一个用于扩展命令 `DEMO` 的 Java 类示例，该类仅简单地接收一个变量列表作为输入并打印该列表。它展示了实现代码的基本结构，以及值从命令语法（用户提交）传递到实现命令的方法的方法。同时也提供了 `DEMO` 命令的 XML 命令语法规范。

```java
import java.util.Arrays;
import java.util.HashSet;
import java.util.ArrayList;
import java.util.Hashtable;
import java.util.List;
import com.ibm.statistics.plugin.*;

public class DEMO() {
    public DEMO() {
        System.out.println("This is the constructor method");
    }

    public static void Run(Hashtable<String, Hashtable<String, Object>> args) {
        try {
            List<TemplateClass> testlist = Arrays.asList(testlist);
            Extension.Template("VARIABLES", "*vars", "existinglist", true);
            
            SyntaxObj obj = Extension.Syntax(testlist);
            Extension.processcmnd(obj, args, "printvars");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }

    public void printvars(@ParamName("var") ArrayString variables) {
        System.out.println("variables = " + variables);
    }
}
```

简而言之，`Run`、`Syntax` 和 `processcmnd` 方法的功能如下：

- IBM Statistics 解析用户提交的命令语法，并将指定的值通过单个参数 `args` 传递给 `Run` 函数（在本示例中）。
- `Run` 函数调用 `Extension.Syntax`、`Extension.Template` 和 `Extension.processcmnd` 方法，这些方法旨在协同工作。

`Extension.Template` 指定了处理扩展命令语法中特定关键字所需的详细信息。在本示例中，该扩展命令使用了单一关键字 `VARIABLES`。

`Extension.Syntax` 根据为关键字指定的模板对传递给 `Run` 函数的值进行验证。

`Extension.processcmd` 解析传递给 `Run` 函数的值，并调用实际实现命令的方法——在本示例中，即 `printvars` 方法。

注解机制还要求实现方法被定义为对象类型而非基本数据类型。特别是，你必须使用对象类型 `Integer`、`Short`、`Long`、`Float`、`Double`、`Byte`、`Character` 和 `Boolean`，而不是基本类型 `int`、`short`、`long`、`float`、`double`、`char` 和 `boolean`。在上面的示例中，`printvars` 方法是一个字符串数组，并定义为 `ArrayList` 对象。

`DEMO` 命令的 XML 规范如下：

```xml
<Command xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:noNamespaceSchemaLocation="http://example.com/XML-Schema.xsd"
         Name="DEMO" Language="Java">
  <Subcommand Name="">
    <Parameter Name="VARIABLES" ParameterType="VariableNameList"/>
  </Subcommand>
</Command>
```

- 顶层元素 `Command` 指定扩展命令的名称和实现语言。`Mode` 属性设置为 "Source"，表示实现代码包含在 Java 类文件中而不是 JAR 文件。
- `Subcommand` 元素指定该扩展命令的唯一子命令。在这个简单的示例中，子命令没有名称。
- `Parameter` 元素指定该扩展命令的唯一参数。该参数名为 `VARIABLES`，它指定了一个变量名列表。

#### 部署扩展命令

要部署扩展命令，最好是创建一个扩展包（JAR 文件或 Java 类文件），并将指定命令语法的 XML 包含在该其中。你可以将扩展包（spv）文件分发给其他用户，他们可以安装并开始使用你的扩展命令。更多信息请参阅帮助系统中的“Core System > Extensions > Creating and editing bundles”。

## 第 2 章 运行 IBM SPSS 命令

### 运行 IBM Statistics 命令

使用 `Util` 类的 `submit` 方法将语法命令提交到 IBM SPSS Statistics 进行处理。它接收一个解析为完整语法命令的字符串，或者解析为一个或多个语法命令的字符串数组。语法命令的输出可以写入标准输出或外部文件。它也可以指向内存工作区，并在其中存储，可以使用 XPath 表达式进行检索。参见第 15 页的“Retrieving output from syntax commands”主题。

#### 提交单个命令

你通过提供命令的字符串表示向 IBM SPSS Statistics 提交单个命令。以这种方式提交单个命令时，命令末尾的点号是可选的。

```java
Util.submit("GET FILE=/data/Employee.sav.");
```

#### 使用数组提交命令

你可以使用字符串数组来使用多个命令，其中每个元素都是一个语法命令的表示。每个命令的字符串必须以句号结束。

```java
String[] commands = {"GET FILE=/data/Employee.sav.", "LIST."};
Util.submit(commands);
```



无论是使用 JAR 文件还是独立的 Java 类，与扩展命令具有同名的类文件都应包含以下内容：

- 一个该类的构造方法，该方法不带参数。
- 一个名为 `Run` 的公共静态方法，接受单个 `Hashtable` 参数，其指定方式如下：
  `Hashtable<String, Hashtable<String, Object>>`
- 一个实现命令的公共方法。

## XML 命令语法规范

- 对于在 Java 中实现的扩展命令，`Command` 元素的 `Language` 属性应被设置为 "Java"。
- 对于使用 JAR 文件实现的 Java 命令，`Command` 元素的 `Mode` 属性应被设置为 "Package"。

## Java 类示例

以下是一个用于扩展命令 DEMO 的 Java 类示例，该类仅简单地接收一个变量列表作为输入并打印该列表。它展示了实现代码的基本结构，以及值从命令语法（用户提交）传递到实现命令的方法的方法。同时也提供了 DEMO 命令的 XML 命令语法规范。

```java
import java.util.Arrays;
import java.util.HashSet;
import java.util.ArrayList;
import java.util.Hashtable;
import java.util.List;
import com.ibm.statistics.plugin.*;

public class DEMO() {
    public DEMO() {
        System.out.println("This is the constructor method");
    }

    public static void Run(Hashtable<String, Hashtable<String, Object>> args) {
        try {
            List<TemplateClass> testlist = Arrays.asList(testlist);
            Extension.Template("VARIABLES", "*vars", "existinglist", true);
            
            SyntaxObj obj = Extension.Syntax(testlist);
            Extension.processcmnd(obj, args, "printvars");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }

    public void printvars(@ParamName("var") ArrayString variables) {
        System.out.println("variables = " + variables);
    }
}
```

简而言之，`Run`、`Syntax` 和 `processcmnd` 方法的功能如下：

- IBM Statistics 解析用户提交的命令语法，并将指定的值通过单个参数 `args` 传递给 `Run` 函数（在本示例中）。
- `Run` 函数调用 `Extension.Syntax`、`Extension.Template` 和 `Extension.processcmnd` 方法，这些方法旨在协同工作。

`Extension.Template` 指定了处理扩展命令语法中特定关键字所需的详细信息。在本示例中，该扩展命令使用了单一关键字 `VARIABLES`。

`Extension.Syntax` 根据为关键字指定的模板对传递给 `Run` 函数的值进行验证。

`Extension.processcmd` 解析传递给 `Run` 函数的值，并调用实际实现命令的方法——在本示例中，即 `printvars` 方法。

注解机制还要求实现方法被定义为对象类型而非基本数据类型。特别是，你必须使用对象类型 `Integer`、`Short`、`Long`、`Float`、`Double`、`Byte`、`Character` 和 `Boolean`，而不是基本类型 `int`、`short`、`long`、`float`、`double`、`char` 和 `boolean`。在上面的示例中，`printvars` 方法是一个字符串数组，并定义为 `ArrayList` 对象。

DEMO 命令的 XML 规范如下：

```xml
<Command xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:noNamespaceSchemaLocation="http://example.com/XML-Schema.xsd"
         Name="DEMO" Language="Java">
  <Subcommand Name="">
    <Parameter Name="VARIABLES" ParameterType="VariableNameList"/>
  </Subcommand>
</Command>
```

- 顶层元素 `Command` 指定扩展命令的名称和实现语言。`Mode` 属性设置为 "Source"，表示实现代码包含在 Java 类文件中而不是 JAR 文件。
- `Subcommand` 元素指定该扩展命令的唯一子命令。在这个简单的示例中，子命令没有名称。
- `Parameter` 元素指定该扩展命令的唯一参数。该参数名为 `VARIABLES`，它指定了一个变量名列表。

## 部署扩展命令

要部署扩展命令，最好是创建一个扩展包（JAR 文件或 Java 类文件），并将指定命令语法的 XML 包含在该其中。你可以将扩展包（spv）文件分发给其他用户，他们可以安装并开始使用你的扩展命令。更多信息请参阅帮助系统中的“Core System>Extensions>Creating and editing bundles”。

## 第2章 运行 IBM SPSS 命令

### 运行 IBM Statistics 命令

使用 `Util` 类的 `submit` 方法将语法命令提交到 IBM SPSS Statistics 进行处理。它接收一个解析为完整语法命令的字符串，或者解析为一个或多个语法命令的字符串数组。语法命令的输出可以写入标准输出或外部文件。它也可以指向内存工作区，并在其中存储，可以使用 XPath 表达式进行检索。参见第15页的“Retrieving output from syntax commands”主题。

#### 提交单个命令

你通过提供命令的字符串表示向 IBM SPSS Statistics 提交单个命令。以这种方式提交单个命令时，命令末尾的点号是可选的。

```
Util.submit("GET FILE=/data/Employee.sav.");
```

`submit` 方法被调用两次；首先提交一个 GET 命令，然后提交一个。

#### 使用数组提交命令

你可以使用字符串数组来使用多个命令，其中每个元素都是一个语法命令的表示。每个命令的字符串必须以句号结束。

```java
Util.submit("GET FILE=/data/Employee.sav.");
```



注：由于用户提供的待翻译文本中存在大量段落重复，译文已根据“一定不要重复输出原文”的指令，仅保留了唯一的逻辑内容。

Running IBM SPSS commands



### 运行 IBM Statistics 命令

使用 `Util` 类的 `submit` 方法将语法命令提交到 IBM SPSS Statistics 进行处理。它接收一个解析为完整语法命令的字符串，或者解析为一个或多个语法命令的字符串数组。语法命令的输出可以写入标准输出或外部文件。它也可以指向内存工作区，并在其中存储，可以使用 XPath 表达式进行检索。参见第15页的“Retrieving output from syntax commands”主题。

#### 提交单个命令

你通过提供命令的字符串表示向 IBM SPSS Statistics 提交单个命令。以这种方式提交单个命令时，命令末尾的点号是可选的。

```
Util.submit("GET FILE=/data/Employee.sav.");
```

`submit` 方法被调用两次；首先提交一个 GET 命令，然后提交一个。

#### 使用数组提交命令

你可以使用字符串数组来使用多个命令，其中每个元素都是一个语法命令的表示。每个命令的字符串必须以句号结束。

```java
Util.submit("GET FILE=/data/Employee.sav.");
```

### 在活动数据集中处理案例数据

IBM Statistics - Java 集成插件提供了从活动数据集中读取案例数据、在活动数据集中创建新变量以及向活动数据集中追加新案例的功能。读取和写入活动数据集的功能由 `Cursor` 类提供。`Cursor` 实例会创建一个打开的游标，该游标提供了对活动数据集的访问。由于以下规则适用：

- 当数据游标打开时，你不能使用 `Util` 类中的 `submit` 方法。你必须先使用 `close` 方法关闭游标。特别地，如果你需要将对活动数据集的更改保存到外部文件，请在关闭游标后使用 `submit` 方法提交 `SAVE` 命令。

- 应用程序在任何时刻只能打开一个数据游标。要定义一个新的数据游标，你必须先关闭上一个。

虽然 `Cursor` 类提供了访问活动数据集的全部方法，但更简单的 `DataUtil` 类是 `Cursor` 类的封装，提供了读取案例、创建新变量和追加案例的能力。本节中的示例使用了 `DataUtil` 类。`DataUtil` 类是 `Cursor` 类的封装，对游标也有适用于 `DataUtil` 对象的限制。适用规则如下：

- 当 `DataUtil` 对象存在时，你不能使用 `Util` 类中的 `submit` 方法。你必须使用 `release` 方法释放与对象相关的资源。与游标类似，如果你需要将对活动数据集的更改保存到外部文件，请在释放 `DataUtil` 对象后使用 `submit` 方法提交 `SAVE` 命令。

- 一时间只能存在一个 `DataUtil` 对象。要创建一个新的 `DataUtil` 对象，你必须先释放上一个。

注意：要创建一个新数据集，请使用 `Util` 类中的 `submit` 方法提交 `DATA LIST`。

### 读取案例数据

你使用 `DataUtil` 类中的 `fetchCases` 方法检索案例。你可以一次顺序检索一个案例，也可以通过单次调用 `fetchCases` 方法检索多个案例（包括所有案例）。

- 系统缺失值始终作为 Java 的 `null` 返回；但是，你可以指定用户缺失值是处理为有效值还是返回为 `null`。请参见缺失数据的示例。

- 默认情况下，从代表日期或时间的变量检索出来的值被给为自 1582 年 10 月 14 日以来的秒数。你可以通过后续示例所示的 `setConvertDataTypes` 指定从具有日期或时间格式的 IBM Statistics 变量中检索到的值转换为 `Calendar` 对象。

- 在检索案例时，将遵循任何通过 `FILTER` 或 `USE` 命令指定的案例过滤条件。

示例：

```
DataUtil dataUtil = new DataUtil("file/demo.sav");
if(format == CellValue.DOUBLE) {
    numvar = onecase.getDoubleValue(i);
} else if(format == CellValue.STRING) {
    strvar = onecase.getStringValue(i);
} else if(format == CellValue.DATE) {
    datevar = onecase.getDateValue(i);
}
dataUtil.release();
```

- 你创建了一个 `DataUtil` 类的实例。在这个示例中，变量 `datautil` 是一个 `DataUtil` 对象。

- `convertDateTypes` 方法指定从具有日期或日期/时间格式的 IBM SPSS Statistics 变量中读取的值将转换为 Java `Calendar` 对象。

- `fetchCases` 方法从活动数据集中检索所有案例。第一个参数指定用户缺失值将被处理为缺失值并转换为 Java `null` 值。第二个参数指定从 0 开始从活动数据集中检索。你可以通过为第二个参数指定不同的值来从任意数字开始检索案例。你还可以使用 `fetchCases` 的重载形式，通过第三个参数指定要检索的案例数量。

- `fetchCases` 方法返回一个 `Case` 对象，该对象代表案例数组。数组中每个元素的项包含来自活动数据集（按文件顺序）中特定案例的数据值。你可以通过 `Case` 对象的 `getCellValueNumber` 方法获取每个案例中的项数。

- 案例中每个项的值类型可以通过 `Case` 对象的 `getCellValue` 方法获取。通过针对每种值类型的方法从 `Case` 对象中检索值，此处显示了数值、字符串和日期值的示例。

#### 将检索数据的变量子集

你可以指定一个将从其中检索数据的变量子集。你可以通过变量名称或它们在活动数据集中的索引位置来指定变量集。索引位置从文件顺序中的第一个变量从 0 开始：

```
DataUtil.subset("FILE/data/employee data.csv");
dataUtil1 = new DataUtil();
String[] varNames = new String[]("educ","salary");
dataUtil1.subset(varNames, true);
Case[] data = dataUtil1.fetchCases(false, 0);
```

`variableFilterMethod` 指定了将检索数据的变量子集。在这个示例中，将仅检索 `id`、`educ` 和 `salary` 变量的数据。

### 缺失数据

`fetchCases` 方法的第一个参数指定用户缺失值是转换为 Java `null` 值还是被视为有效数据。系统缺失值始终转换为 Java `null` 值。

```
String command="GET DATA LIST ('','/NumVar (') string Var (a4).";
"BEGIN DATA"
"0"
"1"
"2"
"3"
"4"
END DATA.
"MISSING VALUES (9).";
dataUtil.submit(command);
dataUtil1 = new DataUtil();
Case[] data = dataUtil1.fetchCases(false, 0);
```

将 `fetchCases` 的第一个参数设置为 `false`，用户缺失值将转换为 Java `null` 值。从 IBM Statistics 变量读取的值为：

1

a

b

null

通过将 `fetchCases` 的第一个参数设置为 `true`，可以指定用户缺失值视为有效数据。数据为：

1

a

b

### 处理带分层的数据

`DataUtil` 类的 `getSplit` 方法允许在读取具有分层的数据集时检测分层变化。



进入`/path/to/xxx`目录，找到`xxx.json`。

在表达式`cvar = avar + bvar`中，加法运算符（`+`）将`avar`与`bvar`相加，得到它们的和`cvar`。

在`List.of(arg0, arg1, arg2)`中，`List`接口的工厂方法`of()`接受一系列的元素，返回包含它们的只读列表。

之后我们这样调用`cmd`命令：`cmd arg0 arg1 arg2`。

```
if (condVar > someVal) {console.log("xxx")}
```

---

### 代码示例 1：数据分层处理

```java
String[] command = {
    "*DATA LIST /salary (F) jobcat (F).*",
    "*BEGIN DATA;",
    "*21400 1;",
    "*45000 2;",
    "*30000 2;",
    "*10375 3;",
    "*72000 3;",
    "*57000 3;",
    "*END DATA;",
    "*SPLIT TO."
};
dataUtil.submit(command);
StatUtil.sumfile(command);
DataUtil dataut = new DataUtil();
int splitindex = dataut.getSplitIndex(0);
while (splitindex != -1) {
    System.out.println("new split begins at: " + splitindex);
    splitindex = dataut.getSplitIndex(splitindex);
}
dataut.release();
```

- `dataut.getSplitIndex()` 获取指定案例之后的第一个分层的编号。对于示例中使用的数据集，在读取第 3 和第 5 个案例时跨越了边界。案例从 0 开始。
- 如果在指定案例后没有边界，则 `dataut.getSplitIndex()` 返回 -1。

### 在活动数据集中创建新变量

`DataUtil` 允许向活动数据集中添加新变量及其案例值。

#### 示例

在此示例中创建一个字符串变量、一个数值变量和一个新的日期变量，并为它们填充案例值。

```java
String[] command = {
    "*DATA LIST FREE /case (AS5).*",
    "*BEGIN DATA;",
    "*case;",
    "*case;",
    "*case3;",
    "*END DATA;"
};
StatUtil.sumfile(command);
Variable numvar = new Variable("numvar", 0);
Variable strvar = new Variable("strvar");
Variable datevar = new Variable("datevar", 0);
datevar.setFormat(Variable.FORMAT_DATE);
Double[] doubles = new Double[]{1, 0.2, 0.3};
String[] strings = new String[]{"%a", "%b", "%c"};
Calendar calendar = Calendar.getInstance();
datevar.set(Calendar.YEAR, 2023);
datevar.set(Calendar.MONTH, Calendar.JANUARY);
datevar.set(Calendar.DAY_OF_MONTH, 1);
DataUtil dataUtil = new DataUtil();
dataUtil.addVariableWithValue(numvar, doubles, 0);
dataUtil.addVariableWithValue(strvar, strings, 0);
dataUtil.addVariableWithValue(datevar, calendar, 0);
dataUtil.release();
```

- `Variable` 类为要添加到活动数据集中的新变量创建规范。构造函数的第一个参数是变量名，第二个参数是指定变量类型的整数。数值变量的变量类型为 0，字符串变量的变量类型等于字符串定义的长度（最大为 32767 字节）。
- `DataUtil` 的 `addVariableWithValue()` 方法向活动数据集中添加一个新变量。该方法的第一个参数是 `Variable` 对象，用于指定变量的属性。第二个参数是一个数组，用于指定活动数据集中每个用例要填充的值。第三个参数指定开始填充变量值的用例索引。活动数据集中第一个用例的索引从 0 开始。
- 对于数值变量，未填充的用例将被设置为系统缺失值。对于字符串变量，未填充的用例将被设置为空值。在这个示例中，变量 `variableVar` 只填充了第一个用例。
- 在 IBM SPSS Statistics 中，表示日期或时间的变量是具有日期或日期时间格式的数值型变量。在上面的示例中，变量 `datevar` 是一个数值变量，其格式通过 `Variable` 对象的 `setFormat()` 方法设置为 `DATE`。设置用例的值时，请如示例所示使用 Java `Calendar` 对象。

> **注意**：要将修改后的数据集保存到外部文件，请使用 `submit()` 方法（在 `release()` 方法之后）提交 `SAVE` 命令：
> ```java
> StatsUtil.submit("SAVE OUTPUT='/data/mydata.sav'");
> ```

### 示例：多次数据扫描

有时需要对数据进行多次扫描，在下面的示例中进行了两次数据扫描。第一次扫描用于读取数据并计算汇总统计。第二次扫描用于向活动数据集中添加摘要。

```java
String[] command = {
    "DATA LIST FREE /var (F).",
    "BEGIN DATA.",
    "40000",
    "21900",
    "Data",
    "END DATA."
};
StatsUtil.submit(command);
Double total = 0;
DataUtil dataUtil = new DataUtil();
Case[] data = dataUtil.fetchCases(false, 0);
for (Case oncase : data) {
    total += oncase.getDouble(0);
}
Double mean = total / data.length;
Variable meanVar = new Variable("mean", 0);
double[] means = new double[data.length];
for (int i = 0; i < data.length; i++) {
    means[i] = mean;
}
dataUtil.addVariableWithValue(meanVar, means, 0);
dataUtil.release();
```

### 追加新用例

`DataUtil` 允许你向活动数据集中添加新的用例。

#### 示例

在本示例中，向活动数据集中添加了一个单个用例。

```java
String[] command = {
    "DATA LIST FREE /var (F) value (A) date(DATE).",
    "BEGIN DATA.",
    "01/01/2012",
    "END DATA."
};
StatsUtil.submit(command);
Case newCase = new Case(3);
DataUtil dataUtil = new DataUtil();
Calendar date = Calendar.getInstance();
date.set(Calendar.MONTH, Calendar.JANUARY);
date.set(Calendar.DAY_OF_MONTH, 1);

newCase.setValue(0, 2);
newCase.setValue(1, "q1");
newCase.setValue(2, date);
dataUtil.appendCase(newCase);
dataUtil.release();
```

- 要向活动数据集中追加用例，你需要创建一个表示单个用例的 `Case` 对象，并用该用例的变量值来填充它。变量值通过 `Case` 对象的 `setValue()` 方法进行填充。该方法的第一个参数是关联变量的索引（变量索引为 0，变量值索引为 1，变量日期索引为 2）。`setValue()` 方法的第二个参数是给定用例的变量值。
- 要指定具有日期或日期时间格式的变量值，请如示例所示使用 Java `Calendar` 对象。
- `DataUtil` 对象的 `appendCase()` 方法用于追加用例。其唯一参数是指定该用例的 `Case` 对象。
- 如果 `Case` 对象中未指定数值变量的值，则其将被设置为系统缺失值。如果 `Case` 对象中未指定字符串变量的值，则其将具有一个空值。除非你显式地定义该变量的空值为缺失值，否则该值将是有效的。你还可以使用 `setValue()` 方法的重载形式将 `Case` 对象中指定单元格的值设置为 Java `null` 值，在这种情况下，它的处理方式等同于单元格值未指定。

## 第 5 章 从语法命令获取输出

### 从语法命令获取输出

你可以通过 IBM Statistics 命令获取输出，而无需将输出写入外部文件。这是通过输出管理系统（OMS）将输出路由到内存中的一个区域实现的，并作为 XML 工作区存储，该工作区是一个符合 IBM SPSS Statistics XML 架构的 XPath DOM。使用采用 XPath 表达式函数从此工作区检索输出。

构建 XPath 表达式（IBM SPSS Statistics 目前支持 XPath 1.0）需要理解输出 XML 架构。架构 `spss-output-1.xsd` 随 IBM SPSS Statistics 一起发布。文档包含在 IBM Statistics 帮助系统中。

#### 示例

```java
String[] commands = {
    "GET FILE '/data/employee.data.sav';",
    "OMS",
    "/IF COMMANDS=['DESCRIPTIVES'] SUBTYPES=['Descriptive Statistics']",
    "/DESTINATION FORMAT=XML,WORKSPACE='desc_table';",
    "/TAG='out'.",
    "DESCRIPTIVES VARIABLES=salary, salbegin, datetime, jobtime",
    "/OMEND TAG='out.'"
};
StatusResult result = status1.execute(commands);
String handle = "desc_table";
String xpath = "//pivotTable[@Type='Descriptive Statistics']" +
               "//Dimension[@Row='salary']" +
               "//Dimension[@Column='Mean']" +
               "//Cell[@Name='Mean']";
Cell result = status1.evaluateXPath(handle, xpath);
status1.deleteXPathHandle(handle);
```

- OMS 命令用于从命令输出到 XML 工作区。`DESTINATION` 子命令中的 `XMLWORKSPACE` 关键字配合 `FORMAT=XML` 指定 XML 工作区作为输出目标。此处使用 `desc_table` 是一个良好的习惯，以免干扰可能运行的其他 OMS 命令。在 OMS 命令中使用的 `COMMANDS` 和 `SUBTYPES` 标识符可以在 OMS 标识符框中找到。

```xml
<category number="474" text="474"/>
<category>
    <category text="Mean">
        <cell decimals="2" format="$dollar" number="3419.567510548">$3419.57</cell>
    </category>
</category>
```

将关联输出的图像检索到 XML 工作区。在本示例中，我们将从 Frequencies 过程中检索关联的条形图输出。

```java
String[] command = {"GET FILE '/data/Employee data.csv'."};
```

- OMS 命令将 `FREQUENCIES` 命令的输出路由到句柄名为 `demo` 的输出 XPath DOM 中。

## 第 6 章 创建自定义输出

### 创建自定义输出

IBM SPSS Statistics - Java 集成插件提供了以自定义透视表和文本块形式创建输出的能力。使用输出管理系统 (OMS)，可以将输出渲染为 HTML、文本或 XML 等多种格式，这些格式符合 SPSS Statistics 输出架构。如果您正在生成部分 Java 实现的扩展程序，则输出将默认在查看器中显示。

### 创建透视表

下图显示了透视表的基本组件。对于 SPSS Statistics 版本 26，Java 集成插件支持具有一维一列的透视表。每个维度包含一组用于标记元素的类别，行维度的行标签。表格中的每个单元格都可以通过类别值的组合指定。在所示的示例中，指定的单元格通过*性别* 维度的 *Male* 值以及*职业类别* 维度的 *Custodial* 值来指定。

| 行维度 | 列维度 |
|---|---|
| | Employment Category | Custodial |
| Gender | Manager |
| Female | 186 |
| Male | 110 |

**图 1. 透视表结构**

透视表是通过 `PivotTable` 类创建的，如下例所示。此示例假设您正在为一个将调用 SPSS Statistics 的外部应用程序生成输出，并使用 OMS 对该输出进行路由。

```java
String[] command = {
    "OMS",
    "/SELECT TABLES",
    "/IF SUBTYPES=['PivotTableDemo']",
    "/DESTINATION FORMAT=HTML OUTFILE='/pivottable.html'"
};
StatsUtil.submit(command);

Object[] rows = new Object[]{"row1", "row2"};
Object[] columns = new Object[]{"columnA", "columnB"};
Object[][] cells = new Object[][]{{"1A", "1B"}, {"2A", "2B"}};

// 创建一个示例透视表
String template = "PivotTableDemo";
String caption = "";
String rowDim = "Dimension";
String colDim = "Column dimension";
boolean hiddenRowDimTitle = false;
boolean hiddenColDimTitle = false;
boolean hiddenColDimLabel = false;
PivotTable table = new PivotTable(cells, rows, columns, rowDim, template, "", caption, colDim, hiddenRowDimTitle, false, hiddenColDimTitle, hiddenColDimLabel, null);
table.createSimplePivotTable();
StatsUtil.submit("OMEND");
```

#### 结果

| 行维度 | columnA | columnB |
|---|---|---|
| row1 | 1A | 1B |
| row2 | 2A | 2B |

**图 2. 示例透视表**

- 在此示例中，透视表输出通过 OMS（输出管理系统）路由到外部 HTML 文件。OMS 指定仅包含在下方定义的表子类型为 `PivotTableDemo` 的表格。OMS 指定了输出文件的路径并规定输出将渲染为 HTML 格式。
- OMS 命令的语法被作为参数传递给 SPSS Statistics。这启动了一个 OMS 会话。通过 `OMEND` 命令关闭会话，并将输出写入目标文件。
- 作为使用 OMS 路由输出的替代方案，可以使用 `StatsUtil.start()` 方法的重载形式来指定输出格式和目标，该方法接受带有输出规格的字符串。OMS 提供了更大的灵活性，但对于简单的应用程序，在启动方法上指定输出可能足够了。
- 要创建透视表，您必须创建 `PivotTable` 类的实例。参数如下：
  - **cells**: 此参数指定透视表单元格的值，必须以二维数组的形式给出，其中数组的每个元素指定透视表某行中的单元格。此处只能指定 `Double` 和 `String` 对象。
  - **rowLabels**: 行维度的类别的一维分类数组。此处只能指定 `Double` 和 `String` 对象。
  - **colLabels**: 列维度的类别的一维分类数组。此处只能指定 `Double` 和 `String` 对象。
  - **title**: 指定表格标题的字符串。
  - **templateName**: 指定此处 OMS（输出管理系统）表子类型的字符串。此值必须以字母开头，最大长度为 64 字节。表子类型用于 OMS 命令的 `TYPES` 关键字（如此处所示），以便将此透视表包含在指定子类型的输出中。
  - **注意**：通过在 `startProcedure()`-`endProcedure()` 块中创建透视表实例，可以将透视表输出与命令名称关联，并作为语法生成的透视表输出。命令名称被路由到 `startProcedure()` 函数，并与 OMS 命令的 `COMMAND` 关键字配合使用，将透视表包含在指定命令集的输出中（同时可选地如上文一样指定子类型）。
  - **outline**: 指定表格可选标题的字符串。当使用 OMS 将输出路由到文件时，或为 Java 实现的扩展命令在查看器中生成输出时，透视表将嵌套在具有 outline 名称的项目下。当输出路由到 OXML 格式时，outline 指定一个可以为透视表提供说明的标签。
  - **caption**: 指定行维度标签的字符串。
  - **columnDim**: 指定列维度标签的字符串。
  - **hideRowDimTitle**: 指定是否隐藏行维度的布尔值。
  - **hideRowDimLabels**: 指定是否隐藏行标签的布尔值。



- `hideColDimTitle`: 指定是否隐藏维度标题的布尔值。

- `hideColDimLabels`: 指定是否隐藏标签的布尔值。

- `format`: 用于显示数值的格式，包括值列、行和列标签。该参数作为 `formatSpec` 枚举指定。

### 创建文本块

文本块通过 `StatsUtil` 方法创建。

```java
String[] command = {
    "OMS SELECT",
    "LABELS-text block",
    "DESTINATION=HTML OUTPUT=/pivottable.html"
};
execute(command);

StatsUtil.addTextBlock("text name", "第一行文本。");
StatsUtil.addTextBlock("text name", "第二行文本。");
StatsUtil.submit("OMEND");
```

- 在与其他输出一起创建文本块的情况下，您可能在使用 OMS 路由输出（除非您正在为 Java 实现的扩展程序创建文本块）。

- `addTextBlock` 方法允许向文本块添加行。

- `OMSEND` 命令用于关闭会话并写入输出。

```java
columnDim,hideRowDim,hideDimLabel,
table.createSimplePivotTable(hideColDimTitle,hideColDimLabel,FormatSpec.COEFFICIENT);
StatsUtil.endProcedure();
```

- `startProcedure` 的参数指定了与生成输出相关的名称，它是该输出在 `PivotTable` 中进行分组的标题名称。

- 虽然在此示例中未使用，但 `PivotTable` 方法的 `outline` 参数指定了透视表出现的标题。此标题将嵌套在由 `startProcedure` 方法参数指定的标题下。当省略该参数时（如本示例所示），透视表将直接显示在由 `startProcedure` 方法参数指定的标题下。

- 必须调用 `endProcedure` 方法来结束该块。

## 7. 从 Java 运行 Python 和 R 程序

IBM SPSS Statistics `BEGIN PROGRAM` 命令提供了将外部编程语言的能力与 IBM Statistics 命令语法集成的功能。支持的语言包括 Python 编程语言和 R。这允许你利用 Python 和 R 语言提供的大量科学和统计编程库来创建可以应用于你数据的自定义算法。结果可以写入数据集或 XML 工作空间，并由你的 Java 程序检索。

### Python 程序

一旦安装了 IBM SPSS Statistics - Integration Plug-in for Python，你就可以通过 `BEGIN PROGRAM PYTHON-END PROGRAM` 块（命令语法内）使用 Python 代码完全访问块结构编程语言，并使用 `StatsUtil` 类中的 `submit` 方法提交命令。例如：

```java
String[] command = {"BEGIN PROGRAM PYTHON.",
"import spss",
"<Python code>",
"END PROGRAM."};
```

```java
StatsUtil.submit(command);
```

- Python 系统 `import spss` 导入 Python 模块（随 IBM SPSS Statistics Plug-in for Python 安装），这些模块允许 Python 处理器与 IBM SPSS Statistics 交互。你的 Python 语言代码紧接在 import 语句之后。

- 你可以省略关键字 `ON- BEGIN PROGRAM`，它是默认值。

关于 IBM SPSS Statistics - Plug-in for Python 功能的完整文档可以在 SPSS Statistics 帮助系统的“Integration Plug-in for Python”下找到。

### R 程序

一旦安装了 IBM SPSS Statistics - Integration Plug-in for R，你就可以通过 `BEGIN PROGRAM R-END PROGRAM` 块（命令语法内）使用 R 编程语言完全访问 R，并使用 `StatsUtil` 类中的 `submit` 方法提交命令。例如：

```java
String[] command = {"BEGIN PROGRAM R.",
"<R code>",
"END PROGRAM."};
```

```java
StatsUtil.submit(command);
```

关于 IBM SPSS Statistics - Plug-in for R 功能的完整文档可以在 SPSS Statistics 帮助系统的“Integration Plug-in for R”下找到。

### 从命令文件中插入程序

你可以使用 SPSS Statistics `INSERT` 命令来包含在命令语法文件中的 `BEGIN PROGRAM-END PROGRAM` 块。这允许你将程序存储为单独的代码文件，并在需要时包含它们。

```java
StatsUtil.submit("INSERT FILE=/myprograms/program_block.sps");
```

文件 `/myprograms/program_block.sps` 将包含一个 `BEGIN PROGRAM` 块，如下：

```python
BEGIN PROGRAM PYTHON.
import spss
<Python code>
END PROGRAM.
```

## 8. 部署外部 Java 应用

通过 IBM SPSS Statistics - Integration Plug-in for Java 外部调用 IBM SPSS 的 Java 必须部署在拥有已许可的 IBM SPSS Statistics 应用程序的机器上。有关许可或分发安排的信息，请直接联系 IBM Corp。IBM Statistics - Integration Plug-in for Java 的支持从版本 21 开始引入。

正如第 1 章第 1 页“Getting started with the Integration Plug-in for Java”所示，包含 IBM SPSS Statistics - Plug-in for Java 程序包的 JAR 文件位于 IBM Statistics 安装目录，因此你的应用程序必须能够找到此目录。为此提供了随 IBM Statistics - Programmability SDK 一起分发的实用程序。软件开发工具包（SDK）可以从 http://www.ibm.com/developers/spssdevcentral 获取。

该实用程序提供了获取 IBM Statistics 安装目录的两种方法。你可以运行脚本将最新版本 IBM SPSS Statistics 的位置写入 `.ini` 文件，或者导入一个文件来获取该位置或所有已安装版本（从 21 开始）的位置。该实用程序的组件可以在解压包含 IBM Statistics - Programmability SDK 的压缩包后的 `StatisticsUtil` 文件夹找到。

### 使用 ini 文件

要将最新版本 IBM SPSS Statistics（从 21 开始）的位置写入 `.ini` 文件，请运行 `StatsUtil.bat`（Windows 平台）或 `StatsUtil.sh`（非 Windows 平台）。脚本将 IBM SPSS Statistics 的位置写入脚本所在文件夹中的 `Statistics.ini` 文件。具体而言，它会创建一个 `STATISTICS_PATH` 为键、位置为值的键值对，例如：`STATISTICS_PATH=C:\Program Files\IBM\SPSS\Statistics\21`。如果 `Statistics.ini` 已存在，脚本将更新该文件。如果不存在，脚本将创建它。

### 使用 JAR 文件中的方法

`StatsUtil.Latest` 在类中提供了以下两个方法：

- `getStatisticsLocation()` 返回包含最新版本 IBM SPSS Statistics（从 21 开始）路径的字符串。

- `getStatisticsLocationAll()` 返回一个包含所有已安装版本 IBM SPSS Statistics（从 21 开始）路径的字符串数组。

### 注意事项

- 对于 IBM Statistics 客户端实例，“最新”意味着版本号最高。

- 对于 UNIX 平台上的 IBM Statistics 服务器实例，由于可能存在多个版本相同的实例，“最新”是指时间戳最晚的一个。

本程序的被许可者若希望获取相关信息以实现：(i) 独立创建的程序与其他程序（包括本程序）之间的信息交换，以及 (ii) 对所交换信息的相互使用，请通过以下方式联系：

IBM Director of Licensing

IBM Corporation

North Castle, MD-NC119

Armonk, NY 10540-1785

此类信息可能可用，但须遵守适当的条件，在某些情况下可能需要付费。

本文档描述的许可程序及其所有可用的许可材料均由 IBM 根据《IBM 客户协议》、《IBM 国际程序许可协议》或我们之间的任何同等协议提供。

所引用的性能数据和客户示例仅供参考。实际性能结果可能根据特定的配置和运行条件而异。

有关非 IBM 产品的信息获取自其产品供应商、其发布的公告或公开来源。IBM 未对这些产品进行测试，无法确认与非 IBM 产品相关的性能、兼容性或任何其他声明的准确性。关于非 IBM 产品功能的问题，应咨询此类产品的供应商。

IBM 对未来发展方向或意图的表述可能会在不另通知的情况下更改或撤回，且仅代表目标和目的。

此信息包含日常业务运营中使用的数据和报告示例。为了尽可能说明这些内容，示例包含了个人、公司、品牌和产品的名称。所有这些内容均为虚构，与实际人物或企业的任何相似之处完全属巧合。

## 版权许可

此信息包含源代码形式的示例程序，展示了在各种操作系统平台上的编程技术。您可以以任何形式复制、修改和分发这些示例程序而无需向 IBM 付费，用于开发、使用、营销或分发符合示例程序所在操作平台的应用程序。这些示例未在所有条件下经过彻底测试，因此 IBM 不保证或暗示这些程序的可靠性、可用性或功能。示例程序按“原样”提供，不提供任何形式的保证。IBM 对您使用示例程序而产生的任何损害概不负责。

这些示例程序的副本或任何部分或其衍生作品，必须包含以下版权声明：

© IBM 2019. 此代码的部分源自 IBM Corp. Sample Programs。

© Copyright IBM Corp. 1989 - 2019. 版权所有。

## 商标

IBM、IBM 标志和 ibm.com 是国际商业机器公司（International Business Machines Corp.）的商标或注册商标，已在全球许多司法辖区注册。其他产品和服务名称可能是 IBM 或公司的商标。IBM 商标的当前列表可在 www.ibm.com/legal/copytrade.html 的“版权和商标信息”页面在网上获取。

Adobe、Adobe 标志、PostScript 和 PostScript 标志均为美国及/或其他国家 Adobe Systems Incorporated 的注册商标或商标。

Intel、Intel 标志、Intel Inside、Intel Inside 标志、Intel Centrino、Intel Centrino 标志、Celeron、Intel Xeon、Intel SpeedStep、Itanium 和 Pentium 是 Intel Corporation 及其子公司在美国及其他国家的商标或注册商标。

Linux 是 Linus Torvalds 在美国、其他国家或两者的注册商标。

Microsoft、Windows、Windows NT 和 Windows 标志是 Microsoft Corporation 在美国、其他国家或两者的商标。

UNIX 是 Open Group 在美国和其他国家的注册商标。

Java 以及所有基于 Java 的商标和标志均为 Oracle 和/或其关联公司的商标或注册商标。

## 索引

## D

- 附加案例 9, 12

- 创建新变量 9, 11

- 从 Java 9 读取活动数据集

dictionary (字典)

- 从读取字典信息

- Java 7

## J

Java

- `DataUtil` 类 9

- `evaluateXPath` 方法 15

- `Submit` 方法 5

## O

output (输出)

- 从 Java 15 读取输出结果

- 从 Java 15 读取输出 XML

OXML

## P

- 透视表 19

## R

- 从 Java 5 运行命令语法

## X

- XML 工作区 15

- XPath 表达式 15

![](img/7b14907fb29e3ededa26614548c41a2e_37_0.png)

美国印制
