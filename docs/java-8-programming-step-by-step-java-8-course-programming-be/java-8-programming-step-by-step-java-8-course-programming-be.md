
# Java 8 编程：循序渐进 Java 8 课程编程（成为专家）（第 1 卷）

## 循序渐进 Java 8 课程编程

作者：Daniel Perkins

# 导言

Java 8 编程语言的引入标志着程序员体验的一个转折点和改进。该语言引入了许多在之前的语言版本中不可用或不支持的新特性，这提升了产品的质量，并极大增强了程序员的满意度。该语言解决了在使用之前的 Java 版本时遇到的许多问题，例如日期时间 API 的使用问题。

Lambda 表达式是 Java 8 编程的核心。一旦你理解如何在程序中使用 lambda 表达式，你就会成为 Java 8 编程专家。然而，这并不意味着这是该语言引入的唯一特性，书中将讨论该语言的许多特性。

# 第 1 章 - 定义

Java 8 编程语言的版本于 2014 年 3 月 18 日发布。这个版本的编程语言为 Java 的历史版本带来了重大的变化和改进。它引入了许多之前的 Java 编程语言版本不支持的特性。你可能知道或听说过 Java 8 中首次引入的“lambda”表达式。

通过这种语言，你可以创建支持流水线处理的程序。该版本的语言还引入了“Nashorn 引擎”，使得 Java 开发者在编写 Java 代码时能够执行 Javascript 代码。要调用或调用一个函数，可以使用它的名称，这与直接调用形成对比。

函数本身可以作为参数使用，大多数程序员习惯于使用真实参数或参数来调用函数，但在 Java 8 编程语言中并非如此。日期 API 在 Java 8 中也得到了极大改进，这意味着程序员为他们的应用程序获得了更强大的功能。

Java 8 应用程序的接口现在可以通过默认方法来实现。该语言还向 Java 编程语言中引入了新工具，这些工具的示例包括编译器工具和用于查找依赖关系的 `jdeps`。

以上是我们将在书中探索的某些特性。该语言有许多特性，当你继续阅读时将会遇到这些特性。

现在，请考虑以下示例：

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;

public class Tester {
    public static void main(String[] args) {
        List<String> ns1 = new ArrayList<>();
        ns1.add("Kira");
        ns1.add("Life");
        ns1.add("Nicholas");
        ns1.add("Samuel");

        Collections.sort(ns1, new Comparator<String>() {
            @Override
            public int compare(String s1, String s2) {
                return s1.compareTo(s2);
            }
        });
        System.out.println(ns1);

        List<String> ns2 = new ArrayList<>();
        ns2.add("Kira");
        ns2.add("Life");
        ns2.add("Nicholas");
        ns2.add("Samuel");

        Collections.sort(ns2, (s1, s2) -> s1.compareTo(s2));
        System.out.println(ns2);
    }
}
```

输出：

```text
[Kira, Life, Nicholas, Samuel]
[Kira, Life, Nicholas, Samuel]
```

它使用了以下语法：

```java
public interface Person {
    default void print(){
        System.out.println("My name is Kira!");
    }
}
```

如果你按照原样编写上述程序并运行它，你将得到以下输出作为结果：

## My name is Kira!

## 多个默认方法

如果接口中实现了默认函数，那么当一个类实现了两个具有相同默认方法的接口时，该类将能够解决任何出现的歧义。考虑下面的程序：

```java
public interface Person {
  default void print(){
    System.out.println("My name is Kira!");
  }
}
public interface male {
  default void print(){
    System.out.println("I am a male!");
  }
}
```

为了解决这个问题，我们将创建一个方法来重写默认实现。如下代码所示：

```java
public class car implements person, male {
    default void print(){
        System.out.println("I am a male person named Kira!");
    }
}
```

我们也可以通过使用“super”关键字来解决这个问题，以便调用指定接口的默认方法。

该代码如下所示：

```java
public class human implements person, male {
    default void print(){
        person.super.print();
    }
}
```

## 静态默认方法

在 Java 8 中，可以在接口中使用静态辅助方法。此功能在 Java 8 引入之前是不可用的。考虑下面的示例：

```java
public interface person {
    default void print(){
        System.out.println("I am a person!");
    }

    static void run(){
        System.out.println("I am now running!!!");
    }
}
```

## 默认方法示例

打开你的编辑器（无论是“Notepad”、“Netbeans”还是“Eclipse”并编写以下程序：

```java
public class TesterProgram {
    public static void main(String args[]){
        Person person = new Human();
        person.print();
    }
}

interface Person {
    default void print(){
        System.out.println("I am a person!");
    }
    static void run(){
        System.out.println("I am now running!!!");
    }
}
```

```java
interface Male {
    default void print(){
        System.out.println("I am a male person!");
    }
}

class Human implements Person, Male {
    public void print(){
        Person.super.print();
        Male.super.print();
        Person.run();
        System.out.println("I am a human!");
    }
}
```

你可以编译该类然后执行它。观察你得到的结果。它应该如下：

```text
I am a person!

I am a male person!

I am now running!!!

I am a human!
```

# 第 4 章 - 方法引用

通过方法引用，我们可以轻松地通过名称指向某个特定的方法。以下是可以被的方法的方法类型：

- 实例方法
- 静态方法
- 使用“new”操作符的构造函数

我们现在给出一个 Java 8 方法引用的示例。打开你选择的编辑器并编写以下程序：

```java
import java.util.ArrayList;
import java.util.List;
public class TesterProgram {
public static void main(String args[]){
List ns = new ArrayList();
```

```java
ns.add("Kira ");
ns.add("Life ");
ns.add("Nicholas ");
ns.add("Samuel ");
ns.add("John ");
ns.forEach(System.out::println);
}
}
```

方法 `System::out::println` 被作为一个静态方法的去静态方法引用传递了。

一旦你写好了程序，运行它并观察结果。它应该如下：

```text
Kira

Life

Nicholas

Samuel

John
```

# 第 5 章 - Java 8 中的 Optional 类

Java 8 中的 `Optional` 类表示一个容器对象，该对象包含非空对象。换句话说，它代表 `null` 的缺失值。它提供了各种实用方法，可以用于检查值是否可用，而不是检查 `null` 值。该类是 Java 8 的另一个新新增特性。

该类使用以下语法进行声明：

```java
public final class Optional<T>
extends Object
```

该类具有以下方法：

- `boolean equals(Object obj)` - 检查另一个对象是否“等于”此选项。
- `Optional<T> filter(Predicate<? super T> predicate)` - 检查当前值是否匹配给定的谓词。如果为真，它返回一个描述该值的 `Optional`，否则返回一个空的 `Optional`。
- `<U> Optional<U> flatMap(Function<? super T,Optional<U>> mapper)` - 它检查值是否存在。如果为真，它应用提供的带有 `Optional` 的映射器。
- `T get()` - 检查值是否存在。如果为真，返回该值。
- `boolean isPresent()` - 检查 Optional 中是否存在值。
- `void ifPresent(Consumer<? super T> consumer)` - 如果值存在，则调用消费者。
- `int hashCode()` - 返回 `Optional` 的哈希值。
- `String toString()` - `Optional` 的空字符串表示。
- `static Optional<T> of(T value)` - 返回指定值的 `Optional`。
- `static Optional<T> nullable(T value)` - 返回指定值的 `Optional`，如果值为 `null` 则返回空 `Optional`。
- `T orElse(T other)` - 如果值存在则返回该值，否则传递默认值。
- `T orElseThrow(Supplier<? extends T> supplier)` - 如果存在则返回该值，否则抛出异常。
- `<U> Optional<U> map(Function<? super T, ? extends U> mapper)` - 如果值存在，则应用映射函数并返回描述结果的 `Optional`。

`Optional` 类继承了 `lang.Object` 类的方法。

我们现在需要通过程序来演示这一点。只需打开编辑器并编写以下内容：

```java
import java.util.Optional;
public class TesterProgram {
    public static void main(String args[]){
        TesterProgram tester = new TesterProgram();
        Integer v1 = null;
        Integer v2 = new Integer(20);
        //Optional.Nullable - 传递的参数可以为null
        Optional<Integer> in = Optional.ofNullable(v1);
        //Optional.of - 如果参数为null将抛出 "NullPointerException"
        Optional<Integer> in2 = Optional.of(v2);

        System.out.println(tester.sum(in,in2));
    }
    public Integer sum(Optional<Integer> in, Optional<Integer> in2){
        //Optional.isPresent - 检查值是否存在
        System.out.println("The first parameter has been provided: " + in.isPresent());
        System.out.println("The second parameter has been provided: " + in2.isPresent());
        //Optional.orElse - 如果存在则返回该值，否则传递默认值
        Integer v1 = in2.orElse(new Integer(0));
        //Optional.get - 这将获取值且它必须可用
        Integer v2 = in2.get();
        return v1 + v2;
    }
}
```

一旦你写好了程序，运行它并观察你得到的输出或结果。它应该如下：

```text
The first parameter has been provided: false
The second parameter has been provided: true
40
```

# 第 6 章 - Nashorn Javascript 引擎

当 Java 8 引入时，它自带了 Nashorn 引擎，旨在取代我们已经使用的 Rhino Javascript 引擎。新引擎的性能更好，因为它提供的性能几乎是之前一个引擎的两倍。

Nashorn 引擎对程序员的代码进行直接编译。编译在机器内存中完成，生成的字节码随后传递给 Java 虚拟机（JVM）。该引擎所展示的性能提升归于对“invokokedynamics”的使用，这是 Java 7 首次引入的一项特性。

## jjs

Java 8 引入的 Nashorn 引擎带有一个新的命令行工具。该命令行工具被称为“jjs”，用于直接执行 Javascript 代码。

我们现在需要演示如何使用此命令行来解释 Javascript。创建一个新文件，并以“.js”作为扩展名命名。我给您了一个名为“test.js”的文件。扩展名意味着该文件包含 Javascript 代码。

一旦保存了文件，请向其中添加以下代码：

```javascript
print('Hello there!');
```

添加代码后，再次保存文件。打开控制台并执行以下命令：

```bash
jjs test.js
```

注意命令的最后一个名称是我给 Javascript 文件的名称。确保它与您的文件名匹配，且不要忘记“js”扩展名。

执行命令后，您应该得到以下输出：

```text
Hello there!
```

## 在交互模式下使用 jjs

在上一个示例中，我们将代码保存在文件中，然后使用“jjs”导航到文件所在位置并执行了它。然而，编码和执行都可以在“jjs”控制台中完成。只需打开“jjs”控制台并执行以下命令：

```text
C:\JAVA>jjs
jjs> print("Hello there!")
```

写完上面显示的最后一个命令后，按下“Enter”键并观察控制台发生了什么。您将看到控制台上显示了以下输出：

## Hello there!

我们实现了与上例相同的结果，但方式非常简单且快速得多。要退出“jjs”控制台，只需输入以下命令并按“Enter”键：

```javascript
quit()
```

按下“Enter”键后，您会发现控制台消失。

## 如何传递参数

您可以在“jjs”控制台的函数中传递参数或参数。打开提示符并执行以下命令：

```text
C:\JAVA> jjs -- x y
jjs> print("The letters are: '" +arguments.join(", " "))
```

写完上面显示的最后一个命令后，按下“Enter”键并观察效果。将在控制台上观察到以下输出：

```text
The letters are: x, y, z
```

我们为控制台提供了字母表中的三个字母，即“x”、“y”和“z”。这些就是我们示例中的参数。然后我们命令控制台使用“join()”方法连接这三个参数。这三个参数已经连接并作为结果显示在控制台上。

这表明控制台是强大的，可以执行一些复杂任务，也可以执行基础任务。

## 如何在 Java 中调用 Javascript

在 Java 8 中，程序员可以调用或执行 Javascript 代码，然后在 Java 中进行解释。这是通过使用“ScriptEngineManager”实现的。

让我们通过示例来演示这一点。

打开选择的文本编辑器并创建一个新文件。保存文件并向其中添加以下代码：



```java
import javax.script.ScriptEngine;
import javax.script.ScriptEngineManager;
import javax.script.ScriptException;

public class TesterProgram {
public static void main(String args[]){
ScriptEngineManager sEManager = new
ScriptEngineManager();
```

```java
ScriptEngine nashorn = sEManager.getEngineByName("nashorn");
String nm = "Kira";
Integer rs = null;
try {
nashorn.eval("print(" + nm + ")");
rs = (Integer) nashorn.eval("20 + 5");
}catch(ScriptException ex) {
System.out.println("Error occurred while executing the script: " + ex.getMessage());
}
System.out.println(rs.toString());
```

写完程序后，再次保存文件并执行它。您可以选择使用`javac`编译器。

在这种情况下，通过在提示符上输入以下命令编译程序：

```bash
javac TesterProgram.java
```

注意我使用的名称。它应该是文件名而不是类名。

编译源码后，使用以下命令执行它：

```bash
java TesterProgram
```

执行上述命令后，观察得到的输出。它将如下所示：

## Kira

## 25

值 25 是 20 加上 5 的结果。

## 如何从 Javascript 调用 Java

程序员也可以在 Javascript 中导入并使用属于 Java 的类。打开提示符并执行以下命令：

```javascript
var BigDecimal = new java.math.BigDecimal;
function compute(size, percentage) {
    var rs = new BigDecimal(size).multiply(new BigDecimal(percentage));
    return rs.divide(new BigDecimal("100"), java.math.RoundingMode.HALF_UP);
}

var rs = compute(79, 35);
print(rs);
```

# 第 7 章：函数式接口

函数式接口是一种仅有一个抽象方法的接口。Java 8 中有许多函数式接口，包括：

- `LongOperator`：它代表两个长型（long）操作数之间的操作。
- `BiFunction<T,U,R>`：它代表接受两个参数并返回结果的函数。
- `BiPredicate<T,U>`：它代表具有两个参数的谓词（布尔值函数）。
- `Consumer<T>`：它代表接受单个参数且不返回结果的操作。
- `BiConsumer<T,U>`：它代表接受两个参数且不返回结果的操作。
- `BooleanSupplier`：它代表布尔值结果的供应者。
- `DoubleBinaryOperator`：它代表两个双型（double）操作数之间的操作，并产生双型结果。
- `DoubleConsumer`：它代表接受单个双型参数且不返回结果的操作。
- `DoubleFunction<R>`：它代表接受一个双型参数并产生结果的函数。
- `DoubleSupplier`：它代表产生双型结果的供应者。
- `DoubleToIntFunction`：它代表接受一个双型参数并产生整型（int）结果的函数。
- `DoublePredicate`：它代表具有单个双型参数的谓词（布尔值函数）。
- `DoubleToLongFunction`：它代表接受一个双型参数并产生长型结果的函数。
- `DoubleUnaryOperator`：它代表对单个双型操作数的操作并产生双型结果。
- `Function<T,R>`：它代表接受单个参数并产生结果的函数。
- `IntConsumer`：它代表接受单个整型参数且不返回结果的操作。
- `IntFunction<R>`：它代表接受一个整型参数并产生结果的函数。
- `IntBinaryOperator`：它代表两个整型操作数之间的操作并产生整型结果。
- `ToDoubleBiFunction<T,U>`：它代表接受两个参数并给出双型结果的函数。
- `IntToLongFunction`：它代表接收一个 int 类型参数并返回一个 long 类型结果的函数。
- `IntPredicate`：它代表接收一个 int 类型参数的谓词（“返回布尔值的函数”）。
- `IntSupplier`：它代表提供 int 类型结果的供应者。
- `IntToDoubleFunction`：它代表接收一个 int 类型参数并返回一个双精度浮点数结果的函数。
- `IntUnaryOperator`：它代表对单个 int 类型操作数进行操作并产生一个 int 类型结果。
- `LongConsumer`：它代表接收一个单个 long 类型参数且不返回结果的操作。
- `LongFunction<R>`：它代表接收一个 long 类型参数并产生结果的函数。
- `LongPredicate`：它代表接收一个 long 类型参数的谓词（“返回布尔值的函数”）。
- `BinaryOperator<T>`：它代表两个相同类型操作数之间的操作，产生的结果与操作数的类型相同。
- `ObjDoubleConsumer<T>`：它代表接收一个对象类型且双精度类型的参数且不返回结果的操作。
- `LongUnaryOperator`：它代表对单个 long 类型操作数进行操作并产生一个 long 类型结果的函数。
- `UnaryOperator<T>`：它代表对操作数进行操作并产生一个与操作数类型相同的结果。

我们现在将通过 Java 8 的示例来演示函数式接口。

`Predicate<T>`接口是一个函数式接口，它有一个`test(Object)`方法，其返回值为 Boolean（布尔值）。被测试的对象应该有一个`true`或`false`的结果。

打开你的编辑器并创建一个新文件。

在文件中添加以下代码：

```java
import java.util.List;
import java.util.Arrays;
import java.util.function.Predicate;

public class TesterProgram {
    public static void main(String[] args[]) {
        List<Integer> mylist = Arrays.asList(11, 12, 13, 14, 15, 16, 17, 18, 19);
        Predicate<Integer> mypredicate = k -> true;
        // k 是传递给测试 Predicate 接口方法的参数
        // 无论值 “k” 是什么，该方法将始终返回 “true”。
        System.out.println("Printing all the specified numbers:");
        // 让我们传递参数 “k"
        eval(mylist, k->true);
        Predicate<Integer> p1 = k -> k%2 == 0;
        // k 已作为参数传递给 Predicate 接口的测试方法
        // 如果 k%2 的结果为零，则测试方法将返回 "true"。
        System.out.println("Printing all the even numbers:");
        eval(mylist, k-> k%2 == 0); 

        Predicate<Integer> p2 = k -> k > 3;
        // k 已作为参数传递给 Predicate 的测试方法
        // 如果 “k” 大于 13，则测试方法将返回 "true"。
        System.out.println("Printing numbers greater than 13:");
        eval(mylist, k-> k > 13 );
    }

    public static void eval(List<Integer> mylist, Predicate<Integer> mypredicate) {
        for(Integer k: mylist) {
            if(mypredicate.test(k)) {
                System.out.println(k + " ");
            }
        }
        System.out.println();
    }
}
```

一旦你写好了上述代码，请保存文件。你就可以开始执行它。你将观察到如下结果：

## 打印所有指定的数字

11

12

13

14

15

16

17

18

19

图中显示了输出的第一部分。我们得到了指定的所有数字。

输出的第二部分将如下：

打印所有偶数：

12

14

16

18

输出的第二部分如上图所示，它由偶数组成。这些数字是从我们指定的数字列表中选出的。我们使用了一个公式来判断一个数字是否为偶数。

输出的最后部分将如下：

打印大于 13 的数字：

14

15

16

17

18

19

输出的最后部分由大于 13 的数字组成。这些数字也是从列表中选出的。注意我们使用的公式：如果检查一个数字是否能被 2 整除而没有余数，它就是偶数，否则不是。你已经看到函数式接口在编程中是多么重要的，以及它如何在 Java 8 中实现的。

```java
System.out.println("d1: " + d1);
ZoneId zld = ZoneId.of("Europe/Paris");
System.out.println("zld: " + zld);
ZoneId cZone = ZoneId.systemDefault();
System.out.println("cZone: " + cZone);
}
```

然后你可以保存该程序并运行或执行它。你将看到以下结果：

当前日期是: 2015-06-25T12:00:15.448

d1: 2012-11-04T11:45:30+06:30[Asia/Karachi]

zld: Europe/Paris

cZone: Etc/UTC

## ChronoUnits 枚举

该枚举首次在 Java 8 中被引入。它取代了旧 API 中用于表示天、月和其他数值的整数。我们将通过一个程序来演示它的用法。

创建一个新文件并保存。在文件中添加以下代码：

```java
import java.time.temporal.ChronoUnit;
import java.time.LocalDate;

public class TesterProgram {

    public static void main(String args[]){
        TesterProgram tp = new TesterProgram();
        tp.testChromoUnits();
    }

    public void testChromoUnits(){
        // 获取当前日期
        LocalDate tday = LocalDate.now();
```

```java
System.out.println(" The current date is: " + tday);
// 在上述日期上增加 1 周
LocalDate nWeek = tday.plus(1, ChronoUnit.WEEKS);
System.out.println("Next week: " + nWeek);
// 在上述日期上增加 1 个月
LocalDate nMonth = tday.plus(1, ChronoUnit.MONTHS);
System.out.println("Next month: " + nMonth);
// 在上述日期上增加 1 年
LocalDate nYear = tday.plus(1, ChronoUnit.YEARS);
System.out.println("Next year: " + nYear);
// 在上述日期上增加 10 年
LocalDate nDecade = tday.plus(1, ChronoUnit.DECADES);
System.out.println("The date after ten year will be: " + 
nDecade);
}
```

保存程序并运行它。将观察到以下结果：

当前日期是: 2015-06-25

下周: 2015-07-02

下个月: 2015-07-25

十年后的日期是: 2025-06-25

## Period 和 Duration

为了处理或计算时间差，Java 8 引入了两个类。它们分别是如下：

- `Period`：处理基于日期的时间。
- `Duration`：处理基于时间长度的时间。

我们想通过一个示例来演示这一点。

在你的文本编辑器中创建一个新文件并添加以下代码：

```java
import java.time.temporal.ChronoUnit;
import java.time.Period;
import java.time.LocalDate;
import java.time.Duration;
```

```java
import java.time.LocalTime;

public class Testerprogram {
    public static void main(String args[]){
        TesterProgram tp = new TesterProgram();
        tp.testPeriod();
        tp.testDuration();
    }

    public void testPeriod(){
        // 获取当前日期
        LocalDate d1 = LocalDate.now();
        System.out.println("The current date is: " + d1);
        // 在上述日期上增加 1 个月
        LocalDate d2 = d1.plus(1, ChronoUnit.MONTHS);
        System.out.println("Next month: " + d2);
        Period p = Period.between(d2, d1);
        System.out.println("Period: " + p);
    }

    public void testDuration(){
        LocalTime t1 = LocalTime.now();
        Duration twoHrs = Duration.ofHours(2);
    }
```

```java
LocalTime t2 = t1.plus(twoHrs);
Duration d = Duration.between(t1, t2);
System.out.println("Duration: " + d);
}
```

像上面一样编写程序并保存。直接运行它，或者像我们之前的那样通过控制台运行。

你将观察到以下内容：

当前日期是: 2015-06-25

下周: 2015-07-02

Period: P1

Duration: PT2H

## Temporal Adjusters：时间调整器

通过这个类，你可以执行与日期相关的数学运算。一个很好的例子是你想获取某月的第三个星期二。这个功能是由 Java 8 引入编程的。我们将通过一个程序来演示。

打开你选择的文本编辑器，创建一个新文件。命名并保存。

在文件中添加以下代码：



```java
import java.time.temporal.TemporalAdjusters;
import java.time.DayOfWeek;
import java.time.LocalDate;
public class TesterProgram {
    public static void main(String args[]) {
        TesterProgram tp = new TesterProgram();
        tp.testAdjusters();
    }

    public void testAdjusters(){
        // 获取当前的日期
        LocalDate d1 = LocalDate.now();

        System.out.println("The Current date is: " + d1);
        // 获取下周五
        LocalDate nextFriday = d1.with(TemporalAdjusters.next(DayOfWeek.FRIDAY));
        System.out.println("Next Friday: " + nextFriday);
        // 获取下个月的第二个星期日
        LocalDate finYear = LocalDate.of(d1.getYear(), d1.getMonth(), 1);
        LocalDate secondSunday = finYear.with(TemporalAdjusters.nextOrSame(DayOfWeek.SUNDAY));
        System.out.println("Second Sunday on: " + secondSunday);
    }
}
```

当前日期是: 2015-06-26

下周五是: 2015-07-03

第二个星期日是: 2015-07-12

## 向后兼容性

我们可以应用`toInstant()`方法。通过这个方法，我们可以将原始日期时间转换为新 API 提供的格式。让我们通过一个程序来演示这一点。

在你的编辑器中创建一个新文件并保存。之后，在文件中添加以下代码：

```java
import java.time.Instant;
import java.util.Date;
import java.time.LocalDateTime;
import java.time.ZonedDateTime;
import java.time.ZoneId;
public class TesterProgram {
    public static void main(String args[]){
        TesterProgram tp = new TesterProgram();
        tp.testBackwardCompatibility();
    }

    public void testBackwardCompatibility(){
        // 获取当前日期
        Date cDate = new Date();
        System.out.println("The Current date is: " + cDate);
        // 获取当前毫秒时间
        Instant current = cDate.toInstant();
        ZoneId cZone = ZoneId.systemDefault();
        LocalDateTime lDT = LocalDateTime.ofInstant(current, cZone);
        System.out.println("The Local date is: " + lDT);
        ZonedDateTime zDTime = ZonedDateTime.ofInstant(current, cZone);
        System.out.println("The zoned date is: " + zDTime);
    }
}
```

在文件中保存程序然后运行它。你可以直接运行，或者通过控制运行。

你将从程序中观察到结果：

当前日期是: Fri June 26 11:17:06 UTC 2015

本地日期是: 2015-06-26T05:11:17.635

时区日期是: 2015-06-26T06:42:07.620Z[Etc/UTC]

## 第九章 Lambda 表达式

这些首次在 Java 8 中引入编程。事实上，它是该语言最大且最重要的特性。通过 Lambda 表达式，函数式编程变得更加简单，软件开发过程也变得简单。

Lambda 表达式采用以下语法：

```
parameter -> expression body
```

在 Java 8 中，Lambda 表达式具有以下特性：

- **可选类型声明** – 不需要声明参数的类型。因为编译器可以从参数的值知道它的类型。
- **可选的大括号** – 如果情况下体只有一个语句，则不需要在表达式体中使用大括号。
- **参数周围可选的括号** – 如果只有一个参数，不需要将其放在括号内。但是，如果你有多个或多个参数，则必须将它们放在括号内。
- **可选的 return 关键字** – 如果程序体有一个预期返回某些值的表达式或表达式，这将自动完成。如果你打算有一个应该返回值的表达式，那么你应该使用大括号。

```java
System.out.println("20 / 5 = " + tp.operate(20, 5, div));
//带有括号
GreetingService gService1 = msg -> System.out.println("Hello " + msg);
//不带括号
GreetingService gService2 = (msg) -> System.out.println("Hello " + msg);
gService1.sayMessage("Kira");
gService2.sayMessage("Samuel");
}

interface MathOperation {
    int operation(int x, int y);
}

interface GreetingService {
    void sayMessage(String msg);
}

private int operate(int x, int y, MathOperation mOperation) {
    return mOperation.operation(x, y);
}
```

保存程序并执行它。再次从 IDE 直接执行或使用编译器`javac`执行，你将得到相同的结果。从程序中应该观察到以下输出：

```
20 + 5 = 25
20 - 5 = 15
20 * 5 = 100
20 / 5 = 4
Hello Kira
Hello Samuel
```

该程序展示了如何在 Java 8 编程中使用 lambda 表达式。

然而，在 Java 8 中使用 lambda 表达式时，你需要注意以下几点。

这些包括以下内容：

- Lambda 表达式用于程序中接口的内联实现定义，即只有一个方法体的接口（函数式接口）。在我们上面的程序中，数学运算是通过使用不同的 lambda 表达式来定义的。我们还通过 lambda 表达式实现了`sayMessage`方法。
- 使用 lambda 表达式，你就不再需要使用匿名类了。然而，lambda 表达式使得函数式编程变得非常强大且简单。

## 变量作用域

你可以使用 lambda 表达式调用或引用程序中的任何变量。如果一个变量被赋值了多次，lambda 表达式将向编译器抛出错误或异常。让我们通过一个程序来演示这一点。

打开你选择的文本编辑器，创建一个新文件。为其命名并保存。将以下代码添加到文件中：

```java
public class TesterProgram {
    final static String hello = "Hi !";
    public static void main(String[] args){
        GreetingService gService1 = msg -> System.out.println(hello + msg);
        gService1.sayMessage("Kira");
    }
}
interface GreetingService {
    void sayMessage(String msg);
}
}
```

一旦你将上述代码添加到文件中，保存并运行它。

观察你从程序中得到的结果或输出。它应该如下：

Hi! Kira

# 第 10 章 - 流 (Streams)

Java 8 引入了一个名为流（stream）的新层。流使得程序员能够以声明式的方式处理数据，类似于 SQL 中的操作。

考虑下面所示的 SQL 语句：

```sql
SELECT max(age),student_id,student_name FROM Student
```

该查询返回特定数据库`Student`表中年龄最大或最高的学生。注意，开发者不需要在自己的端执行任何计算。对于 Java 集合框架的情况，开发者必须通过循环反复执行检查。

在编程时，我们应该关注效率。由于多核处理器的使用，开发者必须编写并行代码，这容易产生更多错误。

这个问题就是 Java 8 引入流概念的原因，因为它解决了上述问题。流使得程序员能够以声明式的方式处理数据并利用多种架构，而无需为此编写特定的代码。

它们具有以下特征：

- **由元素序列组成** - 它提供了一组顺序排列的元素，且它们的类型都相同。流只在需要时计算元素，而不会存储它们。
- **它们执行自动迭代** - 元素的迭代在内部完成，而在需要显式迭代的集合中
- **源 (Source)** – 输入是集合或
- **管道 (Pipelining)** – 在处理中间操作后，获取结果。
- **终端操作 (Terminal operation)** – 标记结束。

如何生成流

Java 8 框架提供了两种方式：

- `parallelStream()` - 这是并行的。
- `stream()` - 这将返回顺序流。

下面的示例说明了这一点：

```java
List<String> sts = Arrays.asList("xyz", "yz", "abc", "pqrst", "uvw");
List<String> f = sts.stream().filter(string -> !string.isEmpty()).collect(Collectors.toList());
```

forEach 方法

此方法用于迭代。考虑给出的示例：

```java
Random r = new Random();
r.ints().limit(10).forEach(System.out.println);
```

在我的情况下，我得到了以下输出：

8 10 2 5 89 37 12 24 67 59

Map (映射)

当我们需要将特定元素映射到相应结果时，使用此方法。我们将通过一个程序演示这一点。

打开编辑器并创建一个新文件。为其命名并保存。将以下代码添加到文件中：

```java
List<Integer> nums = Arrays.asList(2, 3, 4, 5, 6, 7, 8);
List<Integer> sqList = nums.stream().map(j -> j*j).distinct().collect(Collectors.toList());
```

输出形成：

4 9 16 25 36 49

Filter (过滤)

此方法根据你选择的标准来选择或消除某些元素。通过示例演示：

```java
List<String> sts = Arrays.asList("xyz", "", "abc", "pqrst", " ");
int c = sts.stream().filter(string -> string.isEmpty()).count();
```

上图所示的输出为 2。

Limit (限制)

当程序员想要对流进行规约时，就会使用此方法。假设我们需要打印系统随机取的 10 个数字，可以这样实现：

```java
Random r = new Random();
r.ints().limit(10).forEach(System.out.println);
```

以下是我系统的输出：

8 10 2 5 89 37 12 24 67 59

Sorted (排序)

此方法用于对特定流中的元素进行排序。我们将通过一个程序演示如何实现。

打开你的文本编辑器并创建一个新文件。为其命名并保存。将以下代码添加到文件中：

```java
Random r = new Random();
r.ints().limit(5).sorted().forEach(System.out.println);
```

在我的情况下，我得到了以下输出：

2 5 8 9 10

上图显示了上一个程序的输出。输出由 5 个按升序排列的数字组成。注意，这些数字是随机选取然后进行排序的。这就是我们要求编译器执行的操作。

## 并行处理

`parallelStream`在 Java 8 中提供了一种并行处理机制。

考虑下所示程序：

```java
List<String> sts = Arrays.asList("xyz", "", "yz", "pqr", "ghij", "klm");
//计算空字符串的数量
int c = sts.parallelStream().filter(string -> string.isEmpty()).count();
```

我们希望程序能够打印出其中空字符串的数量。按照原样编写代码、保存并运行程序。你将观察到如下输出：

2

数字 2 代表我们程序中空字符串的数量。

你需要注意的是，在顺序流和并行流之间切换非常简单。

## 收集器 (Collectors)

一旦特定流的元素被处理完毕，它们就会合并到一个收集器中。`Collectors`可用于返回列表或字符串。下例如所示：

```java
List<String> sts = Arrays.asList("xyz", "", "yz", "jkl", "pqrs", "", "abc");
List<String> f = sts.stream().filter(string -> !string.isEmpty()).collect(Collectors.toList());
System.out.println("Filtered List: " + f);
String mString = strings.stream().filter(string -> !string.isEmpty()).collect(Collectors.joining(", ")); 
```

编写程序、保存并运行。你应该观察到以下结果：

xyzyzjkjkpqrsabc

如上图所示，程序合并了我们指定的所有字符串。

## 统计 (Statistics)

这些类型的收集器在 Java 8 中被引入，用于在流处理的同时计算统计数据。考虑以下示例：

```java
List<Integer> nums = Arrays.asList(3, 5, 8, 1, 4, 9, 0, 2);
```

```java
IntSummaryStatistics st = integers.stream().mapToInt((x) -> x).summaryStatistics();
```

```java
System.out.println("The largest number in the list is : " + st.getMax());
System.out.println("The least number in the list is : " + st.getMin());
System.out.println("The sum of the numbers is : " + st.getSum());
```

```java
System.out.println("The average of all the numbers is : " + 
st.getAverage());
```

编写程序、保存并运行。你将观察到如下输出：

- 列表中的最大数字是： 9
- 列表中的最小数字是： 0
- 数字之和为： 32
- 所有数字的平均数是： 4

如上图所示，我们在程序中计算了各种统计数据。

# 结论

可以得出，Java 8 是一种为了解决之前 Java 版本中常见问题的编程语言。该版本的为 Java 编程语言的历史带来了巨大的变化和改进。要在 Java 8 中进行编程，你需要从搭建编程环境开始。

你需要在你的机器上下载并安装`JDK`或`JRE`。然后，你应该下载一个提供编辑器的 IDE。可以是`Netbeans`或`Eclipse`。还有一些在线网站提供 Java 8 的开发环境。要执行 Java 8 程序，你可以直接在 IDE 中执行，也可以使用提供`javac`编译器的控制。

该编程语言引入的特性对程序员非常有用。例如，现在程序员可以在 Java 中执行 Javascript 代码了。这可以通过使用`Nashorn`引擎来实现。

`Lambda 表达式`（lambda expressions）的概念是在 Java 8 中首次引入的。通过它，函数式编程的概念变得非常简单，程序员现在可以更快速地编写代码。

之前 Java 版本的日期和时间 API（应用程序接口）容易出现许多问题，特别是在处理时区时。然而，Java 8 通过引入具有改进功能的新日期和时间 API 解决了这个问题。程序员现在能够轻松地处理不同的时区。

# 逐步学习 Java 8 课程编程



Lambda 表达式是 Java 8 编程的核心。一旦你学会如何在程序中使用 Lambda 表达式，你就能成为 Java 8 编程专家。然而，这并不意味着它是该编程语言引入的唯一特性，因为书中还将讨论该语言的众多特性。

![](img/c8fac915e12d88ee413f77be51bbbc61_111_0.png)
