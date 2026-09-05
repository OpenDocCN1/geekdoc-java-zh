
# Core Java 第二卷：高级特性：2（Core 系列）

![封面](img/cover.jpeg)

## 关于本电子书

ePUB 是一种开放的行业标准电子书格式。然而，不同阅读设备和应用程序对 ePUB 及其许多功能的支持程度不同。可以使用您的设备或应用设置来根据喜好自定义显示效果。您可以自定义的设置通常包括字体、字体大小、单栏或双栏、横屏或竖屏模式，以及可以点击或触摸放大的图片。有关阅读设备或应用设置和功能的更多信息，请访问设备制造商网站。

许多标题包含编程代码或配置示例。为了优化这些元素的显示效果，请在单栏横屏模式下查看电子书并将字体大小调整为最小。除了以重流文本格式显示代码和配置外，我们还包含了代码图像，以模仿印刷书籍中的显示效果；因此，当重流格式可能会影响代码列表的显示时，您将看到“点击此处查看代码图像”的链接。点击链接可查看高真代码图像。要返回之前查看的页面，请点击设备或应用上的返回按钮。

![Image](img/00001.jpeg)

波士顿 • 哥伦布 • 印第纳波利斯 • 纽约 • 旧金山 • 阿姆斯特丹 • 开普敦

迪拜 • 伦敦 • 马德里 • 米兰 • 慕尼黑 • 巴黎 • 蒙特利尔 • 多伦多 • 德里 • 墨西哥城

圣保罗 • 悉尼 • 香港 • 首尔 • 新加坡 • 台北 • 东京

作者和出版商已努力准备本书，但不提供任何形式的明示或隐含保证，且不对错误或遗漏负责。对于与本文包含的信息或程序相关的偶然或后果性损害不承担责任。

如需批量购买此书或获取特殊销售机会（可能包括电子版本；定制封面设计以及针对您的业务、培训目标、营销重点或品牌兴趣的特定），请联系我们的企业销售部门：corpsales@pearsoned.com 或 `(800) 382-3419`。

政府销售垂询请联系 governmentsales@pearsoned.com。

美国以外的销售问题，请联系 intlcs@pearson.com。

访问我们的网站：[`informit.com/ph`](http://informit.com/ph)

美国国会图书馆编目号：2016952666

版权所有 © 2017 Oracle 和/其关联公司。保留所有权利。

500 Oracle Parkway, Redwood Shores, CA 94065

部分 © 2017 Cay S. Horstmann

保留所有权利。美国印刷。本出版物受版权法保护，在进行任何受限的复制、存储在检索系统中或以任何形式或通过任何手段（电子、机械、录制或类似方式）传输之前，必须获得出版商的许可。有关许可的相关信息以及 Pearson 全球权利部门内部适当的联系人，请访问 [`www.pearsoned.com/permissions/`](http://www.pearsoned.com/permissions/)。Oracle America Inc. 对本文中包含的任何信息的准确性或完整性不作任何陈述或保证，不对任何错误或遗漏负责。

ISBN-13: 978-0-13-41729-8

ISBN-10: 0-13-41729-0

美国印刷。16

点击此处查看代码图片

```java
String result = optionalString.orElseThrow(IllegalStateException::new);
// 提供一个能返回异常对象的方法
```

你刚刚看到了在没有值存在时如何产生一个备选方案。处理 `optional` 值的另一种策略是仅在值存在时才对该值进行消费。

`ifPresent` 方法接受一个函数（函数接口）。如果该 `optional` 值存在，它就会被传递给该函数。否则，什么都不会发生。

点击此处查看代码图片

```java
optionalValue.ifPresent(v -> Process v);
```

例如，如果你想在值存在时将其添加到集合中，可以调用：

点击此处查看代码图片

```java
optionalValue.ifPresent(v -> results.add(v));
```

或者简单地使用：

点击此处查看代码图片

```java
optionalValue.ifPresent(results::add);
```

当调用 `ifPresent` 时，函数不会返回任何值。如果你想处理函数的结果，请使用 `map`：

点击此处查看代码图片

```java
Optional<Boolean> added = optionalValue.map(results::add);
```

现在，`added` 拥有三个值之一：如果 `optionalValue` 存在，则是一个包装在 `Optional` 中的 `true` 或 `false`；否则，是一个空的 `Optional`。

> **注意**
>
> 这个 `map` 方法与 `Stream` 接口中的 `map` 方法类似，你在第 9 页的第 1.3 节“`filter`、`map` 和 `flatMap` 方法”中见过它。只需简单地将 `optional` 值想象成大小为零或一的流。结果的大小也为零或一，在后一种情况下，函数已被应用。

### `java.util.Optional`

- `T orElse(T other)`：返回此 `Optional` 的值，如果此 `Optional` 为空，则返回 `other`。
- `T orElseGet(Supplier<? extends T> other)`：返回此 `Optional` 的值，如果此 `Optional` 为空，则返回调用 `other` 的结果。
- `<X extends Throwable> T orElseThrow(Supplier<? extends X> exceptionSupplier)`：返回此 `Optional` 的值，如果此 `Optional` 为空，则抛出调用 `exceptionSupplier` 的结果。
- `void ifPresent(Consumer<? super T> consumer)`：如果此 `Optional` 不空，则将其值传递给 `consumer`。
- `<U> Optional<U> map(Function<? super T,? extends U> mapper)`：如果此 `Optional` 不空且结果不为 `null`，则返回此 `Optional` 的值传递给 `mapper` 的结果；否则返回空的 `Optional`。

## 1.7.2 如何错误地使用 Optional 值

如果你不正确使用 `Optional` 值，你就无法获得比过去“某个值或 `null`”方法更好的任何益处。

`get` 方法在 `Optional` 值存在时获取其包装的元素，如果不存在，则抛出 `NoSuchElementException`。因此：

点击此处查看代码图片

```java
Optional<T> optionalValue = . . .;
optionalValue.get().someMethod();
```

这种写法的安全性并不比：

点击此处查看代码图片

```java
T value = . . .;
value.someMethod();
```

`isPresent` 方法报告 `Optional<T>` 对象是否有值。但是：

点击此处查看代码图片

```java
if (optionalValue.isPresent()) optionalValue.get().someMethod();
```

这种写法并不比：

点击此处查看代码图片

```java
if (value != null) value.someMethod();
```

更容易。

### `java.util.Optional`

- `T get()`：返回此 `Optional` 的值，如果为空，则抛出 `NoSuchElementException`。
- `boolean isPresent()`：如果此 `Optional` 不空，则返回 `true`。

## 1.7.3 创建 Optional 值

为止，我们讨论了如何消费别人创建的 `Optional` 对象。如果你想写一个创建 `Optional` 对象的方法，有几个静态方法用于此目的，包括 `Optional.of(result)` 和 `Optional.empty()`。例如：

点击此处查看代码图片

```java
public static Optional<Double> inverse(Double x) {
    return x < 0 ? Optional.empty() : Optional.of(x);
}
```

`ofNullable` 方法旨在作为可能的 `null` 值到 `optional` 值的桥梁。`Optional.ofNullable(obj)` 如果 `obj` 不为 `null` 则返回 `Optional.of(obj)`；否则返回 `Optional.empty()`。

### `java.util.Optional`

- `static <T> Optional<T> of(T value)`：返回包含给定值的 `Optional`。如果 `value` 为 `null`，则抛出 `NullPointerException`。
- `static <T> Optional<T> ofNullable(T value)`：如上。
- `static <T> empty()`：返回一个空的 `Optional`。

## 1.7.4 使用 flatMap 组合 Optional 值

假设有一个返回 `Optional<T>` 的方法 `f`，且方法 `g` 返回 `Optional<U>`。如果它们是普通方法，你可以通过调用 `s.f().g()` 来组合它们。但由于 `f()` 返回的是 `Optional<T>`，这种组合行不通，因为 `Optional` 没有 `g` 方法。相反，使用：

点击此处查看代码图片

```java
Optional<U> result = s.f().flatMap(g);
```

如果 `s.f()` 存在，则将 `g` 应用于它。否则，返回空的 `Optional`。显然，如果你有返回 `Optional` 的方法或 Lambda 表达式，可以通过链式调用 `flatMap` 来构建管道。例如，考虑前面的 `inverse` 方法的平方根：

点击此处查看代码图片

```java
Optional<Double> result = inverse(4.0).flatMap(Math::sqrt);
```

或者，如果你更喜欢，使用：

点击此处查看代码图片

```java
Optional<Double> result = Optional.of(4.0).flatMap(MyMath::inverse).flatMap(Math::sqrt);
```

如果 `inverse` 方法或 `squareRoot` 方法返回 `Optional.empty()`，则结果就是空的。

```java
String result = optionalString.orElse("N/A");

System.out.println("result: " + result);
result = optionalString.orElseGet(() -> Locale.getDefault().getDisplayName());
System.out.println("result: " + result);
try
{
    result = optionalString.orElseThrow(IllegalStateException::new);
    System.out.println("result: " + result);
}
catch (Throwable t)
{
    t.printStackTrace();
}

optionalValue = wordList.stream()
    .filter(s -> s.contains("red"))
    .findFirst();
optionalValue.ifPresent(s -> System.out.println(s + " contains red"));

Set<String> results = new HashSet<>();
optionalValue.ifPresent(results::add);
Optional<Boolean> added = optionalValue.map(results::add);
System.out.println(added);

System.out.println(inverse(4.0).flatMap(OptionalTest::squareRoot));
System.out.println(inverse(-1.0).flatMap(OptionalTest::squareRoot));
System.out.println(inverse(0.0).flatMap(OptionalTest::squareRoot));
Optional<Double> result2 = Optional.of(-4.0)
    .flatMap(OptionalTest::inverse).flatMap(OptionalTest::squareRoot);
System.out.println(result2);

public static Optional<Double> inverse(Double x)
{
    return x == 0 ? Optional.empty() : Optional.of(1 / x);
}

public static Optional<Double> squareRoot(Double x)
{
    return x < 0 ? Optional.empty() : Optional.of(Math.sqrt(x));
}
```

### `java.util.Optional`

- `<U> Optional<U> flatMap(Function<? super T,Optional<U>> mapper)`：将 `mapper` 应用于此 `Optional` 的值产生的结果；如果此 `Optional` 为空，则返回一个空的 `Optional`。

## 1.8 收集结果

当你完成一个流（stream）的操作后，通常想要查看它的元素。你可以调用 `iterator` 方法，它产生一个旧式的迭代器，你可以用它来访问元素。

或者，你可以调用 `forEach` 方法将函数应用到每个元素：

```java
stream.forEach(System.out::println);
```

在并行流（parallel stream）上，`forEach` 方法以任意顺序遍历元素。如果你想按照流的顺序处理它们，请改用 `forEachOrdered`。当然，你可能会因此放弃部分或全部并行带来的优势。

但大多数情况下，你可能希望将结果收集到数据结构中。你可以调用 `toArray` 并获取流元素的数组。

由于在运行时无法创建泛型数组，表达式 `stream.toArray()` 返回的是一个 `Object[]` 数组。如果你需要正确类型的数组，请传入数组构造函数：

```java
String[] result = stream.toArray(String[]::new);
// stream.toArray() 的类型为 Object[]
```

为了将流元素收集到另一个目标中，有一个方便的 `collect` 方法，它接收一个 `Collector` 接口的实例。`Collectors` 类为常用的收集器提供了大量的工厂方法。要将流收集到列表或集合，只需调用：

```java
List<String> result = stream.collect(Collectors.toList());
```

或者：

```java
Set<String> result = stream.collect(Collectors.toSet());
```

如果你想控制获取什么种类型的集合，请使用以下调用：

```java
TreeSet<String> result = stream.collect(Collectors.toCollection(TreeSet::new));
```

假设你想通过拼接收集流中所有的字符串。你可以调用：

```java
String result = stream.collect(Collectors.joining());
```

如果你想在元素之间使用分隔符，请将其传递给 `joining` 方法：

```java
String result = stream.collect(Collectors.joining(", "));
```

如果你的流中包含字符串以外的对象，你需要先将它们转换为字符串，如下所示：

```java
String result = stream.map(Object::toString).collect(Collectors.joining(", "));
```

如果你想将流的结果归纳为总和、平均值、最小值，请使用 `summarizingInt`、`summarizingLong` 或 `summarizingDouble` 方法之一。这些方法接收一个将流对象映射为数字的函数并产生类型为 `IntStatistics`、`LongStatistics` 或 `DoubleStatistics` 的结果，同时计算总和、计数、平均值和最大值。

```java
IntStatistics summary = stream.collect(Collectors.summarizingInt(String::length));
double averageLength = summary.getAverage();
double maxLength = summary.getMax();
```

### `java.util.stream.BaseStream`



- `Iterator<T> iterator()` 返回一个用于此流元素的迭代器。这是一个终端操作。

列表 1.4 中的示例展示了如何从流中收集元素。

#### 列表 1.4：`CollectingResults.java`

```java
package collecting;

import java.io.*;
import java.nio.charset.*;
import java.nio.file.*;
import java.util.*;
import java.util.stream.*;

public class Collecting
{
    public static Stream<String> noVowels() throws IOException
    {
        String contents = new String(Files.readAllBytes(Paths.get("../gutenberg/alice.txt")), StandardCharsets.UTF_8);
        List<String> wordList = Arrays.asList(contents.split("\\s+"));
        Stream<String> words = wordList.stream();
        return words.map(s -> s.replaceAll("[aeiouIOU]", ""));
    }

    public static <T> void show(String label, Set<T> set)
    {
        System.out.print(label + ": " + set.getClass().getName());
        System.out.println("[" + set.stream().limit(10).map(Object::toString).collect(Collectors.joining(", ")) + "]");
    }

    public static void main(String[] args) throws IOException
    {
        Iterator<Integer> iter = Stream.iterate(0, n -> n + 1).limit(10).iterator();
        while (iter.hasNext())
            System.out.println(iter.next());

        Object[] numbers = Stream.iterate(0, n -> n + 1).limit(10).toArray();
        System.out.println("Object array:" + numbers); // 注意它是一个 Object[] 数组

        try
        {
            Integer number = (Integer) numbers[0]; // OK
            System.out.println("number: " + number);
            System.out.println("The following statement throws an exception:");
            Integer[] numbers2 = (Integer[]) numbers; // 抛出异常
        }
        catch (ClassCastException ex)
        {
            System.out.println(ex);
        }

        Integer[] numbers3 = Stream.iterate(0, n -> n + 1).limit(10).toArray(Integer[]::new);
        System.out.println("Integer array: " + numbers3); // 注意它是一个 Integer[] 数组

        Set<String> noVowelSet = noVowels().collect(Collectors.toSet());
        show("noVowelSet", noVowelSet);

        TreeSet<String> noVowelTreeSet = noVowels().collect(Collectors.toCollection(TreeSet::new));
    }
}
```

```java
show("noVowelTreeSet", noVowelTreeSet);

String result = noVowels().limit(10).collect(Collectors.joining());
System.out.println("Joining: " + result);
result = noVowels().limit(10).collect(Collectors.joining(", "));
System.out.println("Joining with commas: " + result);

IntSummaryStatistics summary = noVowels().collect(Collectors.summarizingInt(String::length));
double averageWordLength = summary.getAverage();
double maxWordLength = summary.getMax();
System.out.println("Average word length: " + averageWordLength);
System.out.println("Max word length: " + maxWordLength);
System.out.println("forEach:");
noVowels().limit(10).forEach(System.out::println);
```

### `java.util.stream.Stream`

- `void forEach(Consumer<? super T> action)` 在流的每个元素上调用 `action`。这是一个终结操作。

- `Object[] toArray()`

- `<A> A[] toArray(IntFunction<A[]> generator)` 当传入构造方法引用 `A[]::new` 时，产生对象数组或类型为 `A` 的数组。这些都是终结操作。

- `<R,A> R collect(Collector<? super T,A,R> collector)` 使用给定的收集器收集流中的元素。`Collectors` 类为许多收集器提供了工厂方法。

### `java.util.stream.Collectors`

- `static <T> Collector<T,?,List<T>> toList()`

- `static <T> Collector<T,?,Set<T>> toSet()` 产生将元素收集到列表或集合的收集器。

- `static <T,C extends Collection<T>> Collector<T,?,C> toCollection(Supplier<C> collectionFactory)` 产生一个将元素收集到任意集合的收集器。传入构造方法引用，例如 `TreeSet::new`。

- `static Collector<CharSequence,?,String> joining()`

- `static Collector<CharSequence,?,String> joining(CharSequence delimiter)`

- `static Collector<CharSequence,?,String> joining(CharSequence delimiter, CharSequence prefix, CharSequence suffix)` 产生一个连接字符串的收集器。分隔符置于字符串之间，前缀位于第一个字符串之前，后缀位于最后一个字符串之后。如果未指定，这些将为空字符串。

- `static <T> Collector<T,?,IntSummaryStatistics> summarizingInt(ToIntFunction<? super T> mapper)`

- `static <T> Collector<T,?,LongSummaryStatistics> summarizingLong(ToLongFunction<? super T> mapper)`

- `static <T> Collector<T,?,DoubleSummaryStatistics> summarizingDouble(ToDoubleFunction<? super T> mapper)` 产生 `Int`、`Long` 或 `Double` `SummaryStatistics` 对象的收集器，通过该对象可以获取 `mapper` 应用于每个元素的结果计数、总和、平均值、最大值和最小值。

### `IntSummaryStatistics`、`LongSummaryStatistics`、`DoubleSummaryStatistics`

- `long getCount()` 产生统计元素的计数。

- `int`、`long` 或 `double` `getSum()`

- `double getAverage()` 产生统计元素的总和或平均值，如果没有元素则返回 0。

- `int`、`long` 或 `double` `getMax()`

- `int`、`long` 或 `double` `getMin()` 产生统计元素的最大值或最小值，如果没有元素则返回 `Integer.MAX_VALUE`、`Integer.MIN_VALUE`、`Long.MAX_VALUE`、`Long.MIN_VALUE`、`Double.MAX_VALUE` 或 `Double.MIN_VALUE`。

### 1.9 收集到 `Map`

假设你有一个 `Stream<Person>`，并且想要将元素收集到 map 中，以便稍后可以根据 ID 查找人员。`Collectors.toMap` 方法有两个参数，用于生成 map 的键和值。例如：

```java
Map<Integer, String> idToName = people.collect(Collectors.toMap(Person::getId, Person::getName));
```

在值应该是实际元素本身的常见情况下，请为第二个函数使用 `Function.identity()`。

```java
Map<Integer, Person> idToPerson = people.collect(Collectors.toMap(Person::getId, Function.identity()));
```

如果存在多个具有相同键的元素，则发生冲突，收集器将抛出 `StateException`。你可以通过提供第三个参数来覆盖该行为，该参数根据现有值和新值解析冲突并确定键的值。你的函数可以返回现有值、新值或它们的组合。

在这里，我们构建了一个 map，对于可用区域（locales）中的每种语言，将其在默认区域中的名称（例如 `"German"`）作为键，并将本地化名称（例如 `"Deutsch"`）作为值。

```java
Stream<Locale> locales = Stream.of(Locale.getAvailableLocales());
Map<String, String> languageNames = locales.collect(Collectors.toMap(Locale::getDisplayLanguage, l -> l.getLanguage(l), (existingValue, newValue) -> existingValue));
```

我们不在乎同一种语言可能出现两次（例如德国和瑞士），所以只保留第一个条目。在本章中，我们使用 `Locale` 类作为有趣集合的来源。关于区域的更多信息请参见第 7 章。

现在，假设我们知道某个国家所有的语言。那么我们需要一个 `Map<String, Set<String>>`。例如，`"Switzerland"` 的值是集合 `[French, German, Italian]`。起初，我们为每种语言存储一个单元素集合。每当为国家发现新语言时，我们将现有集合和新集合取并。

```java
Map<String, Set<String>> countryLanguageSets = locales.collect(Collectors.toMap(Locale::getCountry, l -> Collections.singleton(l.getLanguage()), (a, b) -> { // 取并 a 和 b
    Set<String> union = new HashSet<>(a);
    union.addAll(b);
    return union;
}));
```

你将在下一节看到获取此 map 的更简单方法。如果你需要 `TreeMap`，请作为第四个参数提供。你必须提供合并函数。这是本节开头的示例之一，产生 `TreeMap`：

```java
Map<Integer, Person> idToPerson = people.collect(Collectors.toMap(Person::getId, Function.identity(), (existingValue, newValue) -> { throw new IllegalStateException(); }, TreeMap::new));
```

对于每个 `toMap` 方法，都有相应的 `toConcurrentMap` 方法，产生并发 map。在并行收集过程中使用单个并发 map。在使用并行流时，共享 map 比合并 map 效率更高。注意元素不再按流的顺序收集，但这通常没有影响。

列表 1.5 中的示例程序提供了流结果收集到 map 的示例。

**列表 1.5**：`collecting/CollectingIntoMaps.java`

```java
package collecting;

import java.io.*;
import java.util.*;
import java.util.function.*;
import java.util.stream.*;

public class CollectingIntoMaps {
    static class Person {
        private int id;
        private String name;

        Person(int id, String name) {
            this.id = id;
            this.name = name;
        }

        public int getId() {
            return id;
        }

        public String getName() {
            return name;
        }
    }
}
```

```java
public String toString()
{
    return getClass().getName() + "[id=" + id + ",name=" + name + "]";
}
```

```java
public static Stream<Person> people()
{
    return Stream.of(new Person(1001, "Peter"), new Person(1002, "Paul"),
            new Person(1003, "Mary"));
}
```



```java
public static void main(String[] args) throws IOException
{
    Map<Integer, String> idToName = people().collect(
            Collectors.toMap(Person::getId, Person::getName));
    System.out.println("idToName: " + idToName);

    Map<Integer, Person> idToPerson = people().collect(
            Collectors.toMap(Person::getId, Function.identity()));
    System.out.println("idToPerson: " + idToPerson.getClass().getName()
            + idToPerson);

    idToPerson = people().collect(
            Collectors.toMap(Person::getId, Function.identity(), (
                    existingValue, newValue) -> {
        throw new IllegalStateException();
            }, TreeMap::new));
    System.out.println("idToPerson: " + idToPerson.getClass().getName()
            + idToPerson);

    Stream<Locale> locales = Stream.of(Locale.getAvailableLocales());
    Map<String, String> languageNames = locales.collect(
            Collectors.toMap(
                Locale::getDisplayLanguage,
                l -> l.getDisplayLanguage(l),
                (existingValue, newValue) -> existingValue));
    System.out.println("languageNames: " + languageNames);

    locales = Stream.of(Locale.getAvailableLocales());
    Map<String, Set<String>> countryLanguageSets = locales.collect(
            Collectors.toMap(
                Locale::getCountry,
                l -> Collections.singleton(l.getLanguage()),
                (a, b) -> { // union of a and b
                    Set<String> union = new HashSet<>(a);
                    union.addAll(b);
                    return union;
                }));
    System.out.println("countryLanguageSets: " + countryLanguageSets);
}
```

`java.util.stream.Collectors`

- `static <T,U> Collector<T,?,Map<K,U>> toMap(Function<? super T,? extends K> keyMapper, Function<? super T,? extends U> valueMapper)`

- `static <T,U> Collector<T,?,Map<K,U>> toMap(Function<? super T,? extends K> keyMapper, Function<? super T,? extends U> valueMapper, BinaryOperator<U> mergeFunction)`

- `static <T,U,M extends Map<K,U>> Collector<T,?,M> toMap(Function<? super T,? extends K> keyMapper, Function<? super T,? extends U> valueMapper, BinaryOperator<U> mergeFunction, Supplier<M> mapSupplier)`

- `static <T,U> Collector<T,?,ConcurrentMap<K,U>> toConcurrentMap(Function<? super T,? extends K> keyMapper, Function<? super T,? extends U> valueMapper)`

- `static <T,U> Collector<T,?,ConcurrentMap<K,U>> toConcurrentMap(Function<? super T,? extends K> keyMapper, Function<? super T,? extends U> valueMapper, BinaryOperator<U> mergeFunction)`

- `static <T,U,M extends ConcurrentMap<K,U>> Collector<T,?,M> toConcurrentMap(Function<? super T,? extends K> keyMapper, Function<? super T,? extends U> valueMapper, BinaryOperator<U> mergeFunction, Supplier<M> mapSupplier)`返回一个产生 map 或并发 map 的收集器。`keyMapper` 和 `valueMapper` 函数被应用于每个收集到的元素，产生结果 map 的键/值条目。默认情况下，当两个元素产生相同的键时，会抛出 `IllegalStateException`。你可以提供一个 `mergeFunction` 来合并具有相同键的值。默认情况下，结果是 `HashMap` 或 `ConcurrentHashMap`。你可以提供一个 `mapSupplier` 来产生所需的 map 实例。

### 1.10 分组与分区

在上一节中，你已经看到了如何收集某个国家的所有语言。但这个过程有点过于琐碎。你必须为每个 map 值生成一个单例集合，然后指定如何合并现有值和新值。将具有相同特征的值进行分组是非常常见的，而 `groupingBy` 方法直接支持这种操作。

让我们看看按国家对 locale 进行分组的问题。首先，构建这个 map：

```java
Map<String, List<Locale>> countryToLocales = locales.collect(
    Collectors.groupingBy(Locale::getCountry));
```

`Locale::getCountry` 函数是分组的分类函数。你现在可以查找给定国家代码的所有 locale，例如

```java
List<Locale> swissLocales = countryToLocales.get("CH");
// 产生 locales [it_CH, de_CH, fr_CH]
```

![Image](img/00002.jpeg) 注意

快速回顾 locale（语言区域）：每个 locale 都有一个语言代码（例如英语的 `en`）和一个国家代码（例如美国的 `US`）。locale `en_US` 描述的是在美国使用的英语，而 `en_IE` 描述的是爱尔兰的英语。有些国家有多个 locale。例如，`ga_IE` 是爱尔兰的盖尔语，JVM 知道瑞士三个 locale。

当分类函数是一个谓词函数时（即返回布尔值的函数），流元素会被分区。在这种情况下，使用 `partitioningBy` 代替 `groupingBy` 更高效。例如，在这里我们将所有 locale 分为使用英语的和和其他：

```java
Map<Boolean, List<Locale>> englishOtherLocales = locales.collect(
    Collectors.partitioningBy(l -> l.getLanguage().equals("en")));

List<Locale> englishLocales = englishOtherLocales.get(true);
```

![Image](img/00002.jpeg) 注意

调用 `groupingByConcurrent` 方法，得到的可以在并行流中并发填充的并发 map。这与 `toConcurrentMap` 方法完全对应。

`java.util.stream.Collectors`

- `static <T,K> Collector<T,?,Map<K,U>> groupingBy(Function<? super T,? extends K> classifier)`

- `static <T,K> Collector<T,?,ConcurrentMap<K,U>> groupingByConcurrent(Function<? super T,? extends K> classifier)`返回一个产生 map 或并发 map 的收集器。

- `static <T> Collector<T,?,Map<Boolean,List<T>>> partitioningBy(Predicate<? super T> predicate)`返回一个产生 map 的收集器，其键为 `true`/`false`，值为满足/不满足谓词的元素列表。

### 1.11 下游收集器

`groupingBy` 方法产生的 map 的值是列表。如果你想以某种方式处理这些列表，可以提供一个“下游收集器”。例如，如果你想要集合而不是列表，可以使用上一节中见过的 `Collectors.toSet` 收集器：

```java
Map<String, Set<Locale>> countryToLocaleSet = locales.collect(
    Collectors.groupingBy(Locale::getCountry, toSet()));
```

![Image](img/00002.jpeg) 注意 在本节及剩余的示例中，我们假设静态导入了 `java.util.stream.Collectors.*`，以便使表达式更易读。

提供了几个收集器将分组后的元素还原为数字：

- `counting` 产生收集元素的计数。例如，

```java
Map<String, Long> countryToLocaleCounts = locales.collect(
    Collectors.groupingBy(Locale::getCountry, counting()));
```

统计每个国家有多少个本地语言（locales）。

- `summing(Int|Long|Double)` 接收一个函数参数，将该函数应用于下游元素，并产生它们的和。例如：

```java
Map<String, Integer> stateToCityPopulation = cities.collect(
    groupingBy(City::getState, summingInt(City::getPopulation)));
```

在城市流中计算每个州的人口总和。

- `maxBy` 和 `minBy` 接收一个比较器（comparator），并产生下游元素中的最大值和最小值。例如：

```java
Map<String, Optional<City>> stateToLargestCity = cities.collect(
    groupingBy(City::getState,
        maxBy(Comparator.comparing(City::getPopulation))));
```

产生每个州最大的城市。

`mapping` 方法产生一个收集器（collector），该收集器对下游结果应用函数，并将函数的返回值传递给另一个收集器。例如：

```java
Map<String, Optional<String>> stateToLongestCityName = cities.collect(
    groupingBy(City::getState,
        mapping(City::getName,
            maxBy(Comparator.comparing(String::length)))));
```

在这里，我们按州对城市分组。在每个州内部，我们产生城市名称并按最大长度进行归约。

`mapping` 方法还为前一节的问题提供了一个更优解决方案——收集一个国家内所有语言的集合。

```java
Map<String, Set<String>> countryToLanguages = locales.collect(
    groupingBy(Locale::getDisplayCountry,
        mapping(Locale::getDisplayLanguage,
            toSet())));
```

在上一节中，我们使用 `toMap` 代替 `groupingBy`。在这种形式下，你不需要担心合并各个集合。

如果分组函数或映射函数的返回类型为 `int`、`long` 或 `double`，你可以将元素收集到一个摘要统计对象（summary statistics object）中，如第 1.8 节“收集结果，”第 19 页 所示。例如：

```java
Map<String, IntSummaryStatistics> stateToCityPopulationSummary = cities.collect(
    groupingBy(City::getState,
        summarizingInt(City::getPopulation)));
```

然后你可以从每个组的摘要统计对象中获取函数值的和、计数、平均值、最小值和最大值。

***

![Image](img/00002.jpeg) 注意

还存在三个版本的 `reducing` 方法，用于执行通用的归约操作，如第 1.12 节“归约操作，”第 33 页 所示。

***

组合收集器是一种强大方法，但也可能导致非常复杂的表达式。它们的最佳用法是配合 `groupingBy` 或 `partitioningBy` 来处理“下游”映射值。否则，请直接在流上应用 `map`、`reduce`、`count`、`max` 或 `min` 等方法。

代码列表 1.6 中的示例程序演示了下游收集器。

**列表 1.6** `collecting/DownstreamCollectors.java`

***



```java
package collecting;

import static java.util.stream.Collectors.*;

import java.io.*;
import java.nio.file.*;
import java.util.*;
import java.util.stream.*;

public class DownstreamCollectors {

    public static class City {
        private String name;
        private String state;
        private int population;

        public City(String name, String state, int population) {
            this.name = name;
            this.state = state;
            this.population = population;
        }

        public String getName() {
            return name;
        }

        public String getState() {
            return state;
        }

        public int getPopulation() {
            return population;
        }
    }

    public static Stream<City> readCities(String filename) throws IOException {
        return Files.lines(Paths.get(filename))
            .map(l -> l.split(", "))
            .map(a -> new City(a[0], a[1], Integer.parseInt(a[2])));
    }

    public static void main(String[] args) throws IOException {
        Stream<Locale> locales = Stream.of(Locale.getLocales());
        locales = Stream.of(Locale.getLocales());
        Map<String, Set<String>> countryToLanguages = locales.collect(
            groupingBy(Locale::getDisplayCountry,
                mapping(Locale::getDisplayLanguage,
            toSet()));
        System.out.println("countryToLanguages: " + countryToLanguages);

        locales = Stream.of(Locale.getLocales());
        Map<String, Long> countryToCounts = locales.collect(
            groupingBy(Locale::getCountry, counting()));
        System.out.println("countryToCounts: " + countryToCounts);

        Stream<City> cities = readCities("cities.txt");
        Map<String, Integer> stateToPopulation = cities.collect(groupingBy(
            City::getState, summingInt(City::getPopulation)));
        System.out.println("stateToPopulation: " + stateToPopulation);

        cities = readCities("cities.txt");
        Map<String, Optional<String>> stateToLongestCity = cities.collect(groupingBy(
            City::getState, mapping(City::getName,
                maxBy(Comparator.comparing(String::length)))));
        System.out.println("stateToLongestCity: " + stateToLongestCity);

        cities = readCities("cities.txt");
        Map<String, IntSummaryStatistics> stateToPopulationSummary = cities.collect(
            groupingBy(City::getState, summarizingInt(City::getPopulation)));
        System.out.println("stateToPopulationSummary: " + stateToPopulationSummary.get("NY"));

        cities = readCities("cities.txt");
        Map<String, String> stateToCityNames = cities.collect(groupingBy(
            City::getState, mapping(City::getName, joining(", "))))));
        System.out.println("stateToCityNames: " + stateToCityNames);
    }
}
```

产生一个收集器，用于计算所收集元素的最大值或最小值，并使用`comparator`指定的排序。

- `static <T,U,A,R> Collector<T,?,R> mapping(Function<? super T,? extends U> mapper, Collector<? super U,A,R> downstream)`

产生一个收集器，其产生一个映射，其键是将`mapper`应用于收集的元素，其值是使用`downstream`收集器对相同键的元素进行收集的结果。

### 1.12 还原操作 (Reduction Operations)

`reduce`方法是从流中计算值的通用机制。最简单的形式接收一个二元函数并从前两个元素开始持续应用它。如果该函数是加法，那么解释起来就很简单：

```java
List<Integer> values = . . .;

Optional<Integer> sum = values.stream().reduce((x, y) -> x + y);
```

在这种情况下，`reduce`方法计算`v[0] + v[1] + v[2] + . . .`，其中`v[i]`是流的元素。该方法返回一个`Optional`，因为如果流为空，则没有有效的结果。

> **注意**
> 在这种情况下，你可以使用`reduce(Integer::sum)`代替`reduce((x, y) -> x + y)`。

通常情况下，如果`reduce`方法有一个还原操作`op`，则还原将产生`v[0] op v[1] op v[2] op . . .`，其中我们用`v[i] op v[i+1]`表示函数调用`op(v[i], v[i+1])`。该操作应该是**结合律的**（associative）：以什么种顺序组合元素并不重要。在数学表示法中，`(x op y) op z`必须等于`x op (y op z)`。这允许使用并行流进行高效还原。

实践中可能有许多有用的结合律操作，例如求和、乘积、字符串拼接、最大值和最小值、集合并集和交集。减法是一个不是结合律的操作示例。例如，`(6 – 3) – 2 ≠ 6 – (3 – 2)`。

通常存在一个恒等值`e`使得`e op x = x`，可以使用该元素作为计算的起点。例如，`0`是加法的恒等值。然后调用`reduce`的第二形式：

```java
List<Integer> values = . . .;

Integer sum = values.stream().reduce(0, (x, y) -> x + y)
// 计算 0 + v0 + v1 + v2 + . . .
```

如果流为空，则返回恒等值，你不再需要处理`Optional`类。

现在假设你有一个对象流，并想要形成某些属性的和，例如字符串流中所有的长度。你不能使用`reduce`的简单形式。它需要一个函数`(T, T) -> T`，其参数和结果类型相同。但在这种情况下，你有两种类型：流元素类型为`String`，而累积结果是整数。有一种`reduce`形式可以处理这种情况。

首先，你提供一个“累加器”函数`(total, word) -> total + word.length()`。该函数被重复调用，形成累积总和。但当计算并行化时，会有多个此类计算，你需要合并它们的结果。你为此目的提供了第二个函数。完整的调用为：

```java
int result = words.reduce(0,
    (total, word) -> total + word.length(),
    (total1, total2) -> total1 + total2);
```

> **注意**
> 在实践中，你可能不会频繁使用`reduce`方法。通常更容易将其映射到数字流，并使用其方法之一计算和、最大值或最小值。（我们将在第 1.13 节“基元类型流，”在第 36 页中讨论数字流。）在这个特定的示例中，你可以调用`words.mapToInt(String::length).sum()`，这既更简单又高效，因为不涉及装箱（boxing）。

> **注意**
> 有时`reduce`并不足够通用。例如，假设你想将结果收集到`BitSet`中。如果收集是并行的，你不能直接将元素放入单个`BitSet`，因为`BitSet`对象不是线程安全的。由于这个原因，`IntStream`无法使用`reduce`。相反，使用`collect`。它接受三个参数：
> 1. 一个创建新实例的`supplier`。
> 2. 一个将元素添加到其中的`accumulator`。
> 3. 一个合并结果的`combiner`。
>
> 以下是`IntStream`如何为`BitSet`工作：
>
> ```java
> BitSet result = stream.collect(BitSet::new, BitSet::add, BitSet::or);
> ```

`Optional<T> reduce(BinaryOperator<T> op)`

`T reduce(T identity, BinaryOperator<T> op)`

`T reduce(T identity, BiFunction<? super T, ? extends T> accumulator, combiner)`

### 1.13 基元类型流 (Primitive Type Streams)

到为止，我们一直在`Stream<Integer>`中收集整数，尽管将每个整数包装成对象显然是低效的。对于其他基元类型也是如此：`double`、`float`、`long`、`short`、`char`、`byte`和`boolean`。流库有专门类型`IntStream`、`LongStream`和`DoubleStream`，它们直接存储基元。如果你想存储`short`、`char`、`byte`和`boolean`，请使用`IntStream`，对于`float`使用`DoubleStream`。

要创建`IntStream`，调用`IntStream.of`和`Arrays.stream`方法：

```java
IntStream stream = IntStream.of(1, 2, 3);
stream = Arrays.stream(values); // values 是 int[]
```

与对象流一样，你也可以使用静态的`generate`和`iterate`方法。此外，`IntStream`和`LongStream`有静态方法`range`和`rangeClosed`，生成步长为一的整数范围：

```java
IntStream zeroToNine = IntStream.range(0, 10); // 不包含边界
IntStream zeroToHundred = IntStream.rangeClosed(0, 100); // 包含边界
```

`CharSequence`接口有`codePoints`和`chars`方法，产生字符 Unicode 码或 UTF-16 编码代码单元的`IntStream`。（细节请参见第 2 章。）

```java
String sentence = "\uD835\uDD46 is the set of octonions.";
// \uD835\uDD46 是字母 ![Image](img/00006.jpeg) 的 UTF-16 编码，unicode U+1D546
IntStream codes = sentence.codePoints();
```

```java
Stream<String> words = . . .;
```

```java
IntStream lengths = words.mapToInt(String::length);
```

要将原始类型流转换为对象流，请使用`boxed`方法：

```java
Stream<Integer> integers = IntStream.range(0, 100).boxed();
```

通常情况下，原始类型流上的方法与对象流流上的方法是类似的。以下是它们显著的差异：

- `toArray`方法返回原始类型数组。
- 返回可选结果的方法返回`OptionalInt`、`OptionalLong`或`OptionalDouble`。这些类与`Optional`类类似，但它们具有`getAsInt`、`getAsLong`和`getAsDouble`方法，而不是`get`方法。
- 存在`sum`、`average`、`max`和`min`方法，分别返回和、平均值、最大值和最小值。这些方法在对象流中没有定义。
- `summaryStatistics`方法产生`IntSummaryStatistics`、`LongSummaryStatistics`或`DoubleSummaryStatistics`类型的对象，该对象可以同时报告流的和、平均值、最大值和最小值。

> **注意**
> `Random`类具有`ints`、`longs`和`doubles`方法，用于返回随机数的原始类型流。

Listing 1.7 中的程序提供了原始类型流 API 的示例。

**Listing 1.7** `streams/PrimitiveTypeStreams.java`



```java
package streams;

import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.util.stream.Collectors;
import java.util.stream.IntStream;
import java.util.stream.Stream;

public class PrimitiveTypeStreams
{
    public static void show(String title, IntStream stream)
    {
        final int SIZE = 10;
        int[] firstElements = stream.limit(SIZE + 1).toArray();
        System.out.print(title + ": ");
        for (int i = 0; i < firstElements.length; i++)
        {
            if (i > 0) System.out.print(", ");
            if (i < SIZE) System.out.print(firstElements[i]);
            else System.out.print("...");
        }
        System.out.println();
    }

    public static void main(String[] args) throws IOException
    {
        IntStream is1 = IntStream.generate(() -> (int) (Math.random() * 100));
        show("is1", is1);
        IntStream is2 = IntStream.range(5, 10);
        show("is2", is2);
        IntStream is3 = IntStream.rangeClosed(5, 10);
        show("is3", is3);

        Path path = Paths.get("../gutenberg/alice.txt");
        String contents = new String(Files.readAllBytes(path), StandardCharsets.UTF_8);
        Stream<String> words = Stream.of(contents.split("\\s"));
        IntStream is4 = words.mapToInt(String::length);
        show("is4", is4);
        String sentence = "the set of objects.";
        System.out.println(sentence);
        IntStream codes = sentence.codePoints();
        System.out.println(codes.mapToObj(c -> String.format("%X ", c)).collect(Collectors.joining()));
        Stream<Integer> integers = IntStream.range(0, 100).boxed();
        IntStream is5 = integers.mapToInt(Integer::intValue);
        show("is5", is5);
    }
}
```

### `java.util.stream.IntStream`

- `static IntStream range(int startInclusive, int endExclusive)`
- `static IntStream rangeClosed(int startInclusive, int endInclusive)`

  产生包含给定范围内整数的 `IntStream`。

- `static IntStream of(int... values)`

  产生包含给定元素的 `IntStream`。

- `int[] toArray()`

  产生一个包含此流元素的数组。

- `int sum()`
- `OptionalDouble average()`
- `OptionalInt max()`
- `OptionalInt min()`
- `IntSummaryStatistics summaryStatistics()`

  产生此流中元素的和、平均值、最大值或最小值，或者产生一个可以从中获得这四个结果的对象。

- `Stream<Integer> boxed()`

  产生一个包含此流中元素的包装对象的流。

### `java.util.stream.LongStream`

- `static LongStream range(long startInclusive, long endExclusive)`
- `static LongStream rangeClosed(long startInclusive, long endInclusive)`

  产生包含给定范围内整数的 `LongStream`。

- `static LongStream of(long... values)`

  产生包含给定元素的 `LongStream`。

- `long[] toArray()`

  产生一个包含此流元素的数组。

- `long sum()`
- `OptionalDouble average()`
- `OptionalLong max()`
- `OptionalLong min()`
- `LongSummaryStatistics summaryStatistics()`

  产生此流元素的和、平均值、最大值或最小值，或者产生一个可以从中获得这四个结果的对象。

- `Stream<Long> boxed()`

  产生一个包含此流中元素的包装对象的流。

### `java.util.stream.DoubleStream`

- `static DoubleStream of(double... values)`

  产生包含给定元素的 `DoubleStream`。

- `double[] toArray()`

  产生一个包含此流元素的数组。

- `double sum()`
- `OptionalDouble average()`
- `OptionalDouble max()`
- `OptionalDouble min()`
- `DoubleSummaryStatistics summaryStatistics()`

  产生此流的和、平均值、最大值或最小值，或者产生一个可以从中获得这四个结果的对象。

- `Stream<Double> boxed()`

  产生一个包含此流中元素的包装对象的流。

### `java.lang.CharSequence`

- `IntStream codePoints()`

  产生字符串所有 Unicode 代码点的流。

### `java.util.Random`

- `IntStream ints()`
- `IntStream ints(int randomNumberOrigin, int randomNumberBound)`
- `IntStream ints(long streamSize)`
- `IntStream ints(long streamSize, int randomNumberOrigin, int randomNumberBound)`
- `LongStream longs()`
- `LongStream longs(long randomNumberOrigin, long randomNumberBound)`
- `LongStream longs(long streamSize)`
- `LongStream longs(long streamSize, long randomNumberOrigin, long randomNumberBound)`
- `DoubleStream doubles()`
- `DoubleStream doubles(double randomNumberOrigin, double randomNumberBound)`
- `DoubleStream doubles(long streamSize)`
- `DoubleStream doubles(long streamSize, double randomNumberOrigin, double randomNumberBound)`

  产生随机数流。如果提供了 `streamSize`，则流是具有给定数量的。如果提供了边界，元素位于 `randomNumberOrigin`（包含）和 `randomNumberBound`（不包含）。

### `java.util.Optional (Int|Long|Double)`

- `static Optional(Int|Long|Double) of(int|long|double value)`

  产生一个带有提供的原始类型值的 Optional 对象。

- `int|long|double getInt|Long|Double()`

  产生此 Optional 对象的值，如果为空则抛出 `NoSuchElementException`。

- `int|long|double orElse(int|long|double other)`
- `int|long|double orElseGet((Int|Long|Double) Supplier other)`

  产生此 Optional 对象的值，如果此对象为空，则产生备选值。

- `void ifPresent((Int|Long|Double) Consumer consumer)`

  如果此 Optional 对象不为空，将其值传递给 `consumer`。

### `java.util.(Int|Long|Double) SummaryStatistics`

- `long getCount()`
- `int|long|double getSum()`
- `double getAverage()`
- `int|long|double getMax()`
- `int|long|double getMin()`

返回收集元素的计数、总和、平均值、最大值最小值。

## 1.14 并行流

流使得批量操作的并行化变得简单。该过程大部分是自动的，但你需要遵循几条规则。首先，你必须有一个并行流。你可以通过 `Collection.parallelStream()` 方法从任何集合中获取并行流：

点击此处查看代码图片

```java
Stream<String> parallelWords = words.parallelStream();
```

此外，`parallel` 方法可以将任何顺序流转换为并行流。

点击此处查看代码图片

```java
Stream<String> parallelWords = Stream.of(wordArray).parallel();
```

只要在执行终端操作方法时流处于并行模式，所有的中间流操作都将是并行化的。

当流操作以并行方式运行时，其意图是返回与串行执行相同的的结果。操作可以按任意顺序执行，这一点非常重要。

这里有一个你不能做的事情示例。假设你想统计字符串流中所有短单词的数量：

点击此处查看代码图片

```java
int[] shortWords = new int[12];

words.parallelStream().forEach(
    s -> { if (s.length() < 12) shortWords[s.length()]++; });
    // –竞态条件！

System.out.println(Arrays.toString(shortWords));
```

这是非常、非常糟糕的代码。传递给 `forEach` 的函数在多个线程中并发运行，每个线程都在更新一个共享数组。正如我们在第一卷第 14 章解释的那样，那是经典的竞态条件。如果你多次运行此程序，很可能在每次运行中得到不同的计数序列——而且每一个都是错误的。

确保你传递给并行流操作的任何函数在并行执行时都是安全的，是你的责任。最好的方法是避免可变状态。在这个示例中，如果你按长度对字符串进行分组并计数，就可以安全地进行并行化计算。

点击此处查看代码图片

```java
Map<Integer, Long> shortWordCounts =
    words.parallelStream()
      .filter(s -> s.length() < 10)
      .collect(groupingBy(
          String::length,
          counting()));
```

### 注意：非阻塞操作

![Image](img/00004.jpeg) 注意

你传递给并行流操作的函数不应该阻塞。并行流使用 fork-join 池来操作流的分段。如果多个流操作阻塞，池可能无法执行任何工作。

### 排序

默认情况下，来自有序集合（数组和列表）、范围、生成器、迭代器或调用 `Stream.sorted` 的流是有序的。结果按原始元素的顺序积累，并且完全完全预测的。如果你运行两次相同的操作，将得到完全相同的结果。

排序并不排除高效并行化。例如，在计算 `stream.map(fun)` 时，流可以被分为 *n* 段，每段都被并发处理。然后按顺序重新组合结果。

当放弃排序要求时，某些操作可以更有效地并行化。通过在流上调用 `unordered` 方法，你表示你对排序不感兴趣。一个可以从中受益的操作是 `Stream.distinct`。在有序流上，`distinct` 保留所有相等元素中的第一个。这阻碍了并行化——处理某段的线程在前面的段被处理之前，并不知道要丢弃哪些元素。如果保留任何一个唯一元素是可以接受的，则所有段都可以并发处理（使用共享的集合来跟踪重复项）。

你也可以通过放弃排序来加速 `limit` 方法。如果你只需要从流中的任何 *n* 个元素，且不在乎得到的是哪几个，请调用：

点击此处查看代码图片

```java
Stream<String> sample = words.parallelStream().unordered().limit(n);
```

正如在第 1.9 节“收集到 Map”中讨论的，第 24 页所示，合并 Map 是昂贵的。因此，`Collectors.groupingByConcurrent` 方法使用共享的并发 map。为了从并行中受益，map 值的顺序将与流顺序不同。

点击此处查看代码图片

```java
Map<Integer, List<String>> result = words.parallelStream().collect(
    Collectors.groupingByConcurrent(String::length));
    // 值不是按流顺序收集的
```

当然，如果你使用与排序无关的下游收集器，你将不在乎，例如：

点击此处查看代码图片

```java
Map<Integer, Long> wordCounts = words.parallelStream()
      .collect(
          groupingByConcurrent(
              String::length));
```

### 注意：干扰

![Image](img/00004.jpeg) 注意

传递给并行流操作的函数不应该阻塞。并行流使用 fork-join 池来操作流的分段。如果多个流操作阻塞，池可能无法执行任何工作。

非常重要的一点是，在执行流操作时，不要修改支持流的集合（即使是线程安全的）。JDK 文档将这种要求称为干扰。确切地说，由于流操作是惰性的，你可以在执行终端操作方法之前修改集合。如果你确实修改了该集合，流操作的结果将是定义。例如，以下代码虽然绝对不推荐，但仍然可以工作：

点击此处查看代码图片

```java
List<String> wordList = ..

Stream<String> words = wordList.stream();

wordList.add("END");

long n = words.distinct().count();
```

这段代码是错误的：

点击此处查看代码图片

```java
Stream<String> words = wordList.stream();

words.forEach(s -> if (s.length() < 12) wordList.remove(s));

// –干扰
```

```java
if (s.length() < 10) shortWords[s.length()]++;

});

System.out.println(Arrays.toString(shortWords));

// 再次尝试——结果可能会不同（而且也是错的）

Arrays.fill(shortWords, 0);

wordList.parallelStream().forEach(s ->

  {
    if (s.length() < 10) shortWords[s.length()]++;
  });
```



```java
System.out.println(Arrays.toString(shortWords));

// 修复：分组并计数

Map<Integer, Long> shortWordCounts = wordList.parallelStream()
    .filter(s -> s.length() < 10)
    .collect(groupingBy(String::length, counting()));

System.out.println(shortWordCounts);

// 下游顺序是不确定的

Map<Integer, List<String>> result = wordList.parallelStream().collect(
    Collectors.groupingByConcurrent(String::length));

System.out.println(result.get(14));

result = wordList.parallelStream().collect(
    Collectors.groupingByConcurrent(String::length));

System.out.println(result.get(14));

Map<Integer, Long> wordCounts = wordList.parallelStream().collect(
    groupingByConcurrent(String::length, counting()));

System.out.println(wordCounts);
}
```

### `java.util.stream.BaseStream<T,S extends BaseStream<T,S>>` (8)

- `S parallel()`：返回一个与此流具有相同元素的并行流。
- `S unordered()`：返回一个与此流具有相同元素的无序流。

### `java.util.Collection<E>` (1.2)

- `Stream<E> parallelStream()`：返回一个包含该集合元素的并行流。

在本章中，你已经学习了如何使用 Java 8 流式库。下一章将介绍另一个重要主题：输入和输出。

## 第 2 章 输入与输出

在本章，我们将介绍：

- **2.1 输入/输出流**
- **2.2 文本输入输出**
- **2.3 读取和写入二进制数据**
- **2.4 对象输入/输出流与序列化**
- **2.5 文件操作**
- **2.6 内存映射文件**
- **2.7 正则表达式**

在本章中，我们将介绍用于输入输出的 Java 应用程序接口（API）。你将学习如何访问文件，以及如何以二进制和文本格式读写数据。本章还将展示序列化机制，它让你像存储文本或数值数据一样方便地存储对象。接下来我们将转向文件操作。我们将通过对正则表达式的讨论结束本章，尽管它们实际上与输入输出没有关系。

### 2.1 输入/输出流

在 Java API 中，可以从其读取字节序列的对象被称为 `input stream`（输入流）。可以向其写入字节序列的对象被称为 `output stream`（输出流）。这些源和目的地可以是——而且通常是——文件、网络连接甚至是内存。抽象类 `InputStream` 和 `OutputStream` 成了输入/输出（I/O）类的基础。

![Image](img/00002.jpeg)

注意：这些输入/输出流与你在上一章中看到的流无关。为了清晰起见，当我们讨论用于输入输出的流时，每当使用 `input stream`、`output stream` 或 `input/output stream` 术语。

面向字节的输入/输出流对于处理存储在 Unicode 中的信息并不方便（回想 Unicode 每个字符使用多个字节）。因此，一个单独的层次结构提供了继承自 `Reader` 和 `Writer` 的类用于处理 Unicode 字符。这些类具有基于 UTF-16 代码单元而非 `byte` 值的读和写操作。

#### 2.1.1 读取和写入字节

`InputStream` 类有一个抽象方法：

```java
abstract int read()
```

该方法读取一个字节并返回所读取的字节，如果遇到输入源的末尾，则返回 `-1`。具体输入类的设计者重写（override）此方法以提供有用的功能。例如，在 `FileInputStream` 类中，此方法从文件中读取一个字节。`System.in` 是 `InputStream` 子类的一个预定义对象，允许你从“标准输入”（即控制台或重定向的文件）读取信息。

`InputStream` 类还拥有非抽象方法，用于读取字节数组或跳过数个字节。这些方法调用抽象的 `read` 方法，因此子类只需要重写一个方法。

同样，`OutputStream` 类定义了抽象方法：

```java
abstract void write(int b)
```

它将一个字节写入输出位置。`read` 和 `write` 方法都会阻塞，直到该字节被实际读取或写入。这意味着如果无法立即访问输入流（通常是因为网络连接正忙），当前线程将阻塞。这为其他线程在方法等待输入流再次可用时提供了做用用工作的机会。

`available` 方法允许你检查当前可用于读取的字节数。这意味着像下方的代码片段不太可能会阻塞：

```java
int bytesAvailable = in.available();

if (bytesAvailable > 0) {
    byte[] data = new byte[bytesAvailable];
    in.read(data);
}
```

当你完成对输入/输出流的读取或写入后，通过调用 `close` 方法将其关闭。此调用会释放供应有限的操作系统资源。如果一个应用程序打开了太多的输入/输出流而不关闭它们，系统资源可能会耗尽。关闭输出流还会刷新其使用的缓冲区：任何存放在缓冲区中以便作为较大的数据包交付的字节都会发送出去。特别是，如果你不关闭文件，最后一个数据包可能永远无法交付。你也可以通过 `flush` 方法手动刷新输出。

即使输入/输出流类提供了处理原始 `read` 和 `write` 函数的具体方法，应用程序程序员也很少使用它们。你感兴趣的数据可能包含数字、字符串和对象，而不是原始字节。与其处理字节，你可以使用许多派自基本的 `InputStream` 和 `OutputStream` 类的输入/输出流类。

### `java.io.InputStream` (1.0)

- `abstract int read()`：读取一个字节数据并返回读取的字节；在输入流末尾返回 `-1`。
- `int read(byte[] b)`：读取到字节数组并返回实际读取的字节数，或在输入流末尾返回 `-1`；此方法最多读取 `b.length` 字节。
- `int read(byte[] b, int off, int len)`：读取到字节数组并返回实际读取的字节数，或在输入流末尾返回 `-1`。

![Image](img/00007.jpeg)

- `long skip(long n)`：在输入流中跳过 `n` 个字节，返回实际跳过的字节数（如果遇到输入流末尾，该值可能小于 `n`）。
- `int available()`：返回可用的字节数，且不阻塞（注意，阻塞意味着当前线程将失去它的执行机会）。
- `void close()`：关闭输入流。
- `void mark(int readlimit)`：在输入流的当前位置放置一个标记（并非所有的流都支持此功能）。如果从输入流中读取的字节数超过了 `readlimit`，则允许流遗忘该标记。
- `void reset()`：返回到上一个标记。后续对 `read` 的调用将重新读取这些字节。如果没有当前标记，则输入流将不会重置。
- `boolean markSupported()`：如果输入流支持标记功能，则返回 `true`。

---

### `java.io.OutputStream` 1.0

- `abstract void write(int n)`：写入一个字节的数据。
- `void write(byte[] b)`
- `void write(byte[] b, int off, int len)`：写入数组 `b` 中的所有字节或某个范围的字节。

![Image](img/00007.jpeg)

- `void close()`：刷新并关闭输出流。
- `void flush()`：刷新输出流——即将任何缓冲区数据发送到其目标。

---

#### 2.1.2 完整的流动物园

与 C 语言仅需单一类型 `FILE*` 就能良好运行不同，Java 拥有超过 60 种 (!) 不同的输入/输出流类型（参见图 2.1 和 2.2）。

![Image](img/00008.jpeg)

**图 2.1** 输入和输出流层次结构

![Image](img/00009.jpeg)

**图 2.2** 读取器和写入器层次结构

让我们根据用途对输入输出流动物园中的动物分类。处理字节和字符的类有独立的层次结构。正如你所看到的，`InputStream` 和 `OutputStream` 类允许你读写单个字节和字节数组。这些类构成了图 2.1 所示层次结构的基础。为了读写字符串和数字，你需要更功能强大的子类。例如，`DataInputStream` 和 `DataOutputStream` 允许你以二进制格式读写所有 Java 原始类型。最后，还有一些执行有用操作输入输出流；例如，`ZipInputStream` 和 `ZipOutputStream` 允许你以熟悉的 ZIP 压缩格式读写文件。

另一方面，对于 Unicode 文本，可以使用抽象类 `Reader` 和 `Writer` 的子类（参见图 2.2）。`Reader` 和 `Writer` 类的基本方法与 `InputStream` 和 `OutputStream` 。

点击此处查看代码图像

```java
abstract int read()

abstract void write(int c)
```

`read` 方法返回一个 UTF-16 代码单元（作为 `0` 到 `65535` 之间的整数），或者在到达文件末尾时返回 `-1`。`write` 方法带有一个 Unicode 代码单元调用。（有关 Unicode 代码单元的讨论，请参见第一卷第 3 章。）

还有四个额外的接口：`Closeable`、`Flushable`、`Readable` 和 `Appendable`（参见图 2.3）。前两个接口非常简单，拥有方法：

```java
void close() throws IOException
```

![Image](img/00010.jpeg)

**图 2.3** `Closeable`、`Flushable`、`Readable` 和 `Appendable` 接口

以及：

```java
void flush()
```

分别。`InputStream`、`OutputStream`、`Reader` 和 `Writer` 类都实现了 `Closeable` 接口。

---

![Image](img/00002.jpeg) 提示

`java.io.Closeable` 接口继承了 `java.lang.AutoCloseable` 接口。因此，你可以对任何 `Closeable` 使用 `try`-with-resources 语句。为什么要两个接口？`Closeable` 接口的 `close` 方法只抛出 `IOException`，而 `AutoCloseable.close` 方法可能会抛出任何异常。

---

`OutputStream` 和 `Writer` 实现了 `Flushable` 接口。

`Readable` 接口有一个单一方法：

```java
int read(CharBuffer cb)
```

`CharBuffer` 类具有用于顺序和随机读/写访问的方法。它代表一个内存缓冲区或内存映射文件。（参见第 2.6.2 节，“缓冲区数据结构””，详见第 124 页。）

对于 Unicode 文本，你可以使用抽象类 `Reader` 和 `Writer` 的子类（参见图 2.2）。`Reader` 和 `Writer` 类的基本方法与 `InputStream` 和 `OutputStream` 类似。

点击此处查看代码图像

```java
abstract int read()

abstract void write(int c)
```

`read` 方法返回一个 UTF-16 代码单元（作为 `0` 到 `65535` 之间的整数），或者在到达文件末尾时返回 `-1`。`write` 方法带有一个 Unicode 代码单元调用。（有关 Unicode 代码单元的讨论，请参见第一卷第 3 章。）

还有四个额外的接口：`Closeable`、`Flushable`、`Readable` 和 `Appendable`（参见图 2.3）。前两个接口非常简单，拥有方法：

```java
void close() throws IOException
```

![Image](img/00010.jpeg)

**图 2.3** `Closeable`、`Flushable`、`Readable` 和 `Appendable` 接口

以及：

```java
void flush()
```

分别。`InputStream`、`OutputStream`、`Reader` 和 `Writer` 类都实现了 `Closeable` 接口。

---

![Image](img/00002.jpeg) 提示

`java.io.Closeable` 接口继承了 `java.lang.AutoCloseable` 接口。因此，你可以对任何 `Closeable` 使用 `try`-with-resources 语句。为什么要两个接口？`Closeable` 接口的 `close` 方法只抛出 `IOException`，而 `AutoCloseable.close` 方法可能会抛出任何异常。

---

`OutputStream` 和 `Writer` 实现了 `Flushable` 接口。

`Readable` 接口有一个单一方法：

```java
int read(CharBuffer cb)
```

`CharBuffer` 类具有用于顺序和随机读/写访问的方法。它代表一个内存缓冲区或内存映射文件。（参见第 2.6.2 节，“缓冲区数据结构”，详见第 124 页。）

对于 Unicode 文本，你可以使用抽象类 `Reader` 和 `Writer` 的子类（参见图 2.2）。`Reader` 和 `Writer` 类的基本方法与 `InputStream` 和 `OutputStream` 类似。

点击此处查看代码图像

```java
abstract int read()

abstract void write(int c)
```

`read` 方法返回一个 UTF-16 代码单元（作为 `0` 到 `65535` 之间的整数），或者在到达文件末尾时返回 `-1`。`write` 方法带有一个 Unicode 代码单元调用。（有关 Unicode 代码单元的讨论，请参见第一卷第 3 章。）

还有四个额外的接口：`Closeable`、`Flushable`、`Readable` 和 `Appendable`（参见图 2.3）。前两个接口非常简单，拥有方法：

```java
void close() throws IOException
```

![Image](img/00010.jpeg)

**图 2.3** `Closeable`、`Flushable`、`Readable` 和 `Appendable` 接口

以及：

```java
void flush()
```

分别。`InputStream`、`OutputStream`、`Reader` 和 `Writer` 类都实现了 `Closeable` 接口。

---

![Image](img/00002.jpeg) 提示

`java.io.Closeable` 接口继承了 `java.lang.AutoCloseable` 接口。因此，你可以对任何 `Closeable` 使用 `try`-with-resources 语句。为什么要两个接口？`Closeable` 接口的 `close` 方法只抛出 `IOException`，而 `AutoCloseable.close` 方法可能会抛出任何异常。

---

`OutputStream` 和 `Writer` 实现了 `Flushable` 接口。

`Readable` 接口有一个单一方法：

```java
int read(CharBuffer cb)
```

`CharBuffer` 类具有用于顺序和随机读/写访问的方法。它代表一个内存缓冲区或内存映射文件。（参见第 2.6.2 节，“缓冲区数据结构”，详见第 124 页。）

对于 Unicode 文本，你可以使用抽象类 `Reader` 和 `Writer` 的子类（参见图 2.2）。`Reader` 和 `Writer` 类的基本方法与 `InputStream` 和 `OutputStream` 类似。

点击此处查看代码图像

```java
abstract int read()

abstract void write(int c)
```

`read` 方法返回一个 UTF-16 代码单元（作为 `0` 到 `65535` 之间的整数），或者在到达文件末尾时返回 `-1`。`write` 方法带有一个 Unicode 代码单元调用。（有关 Unicode 代码单元的讨论，请参见第一卷第 3 章。）

还有四个额外的接口：`Closeable`、`Flushable`、`Readable` 和 `Appendable`（参见图 2.3）。前两个接口非常简单，拥有方法：

```java
void close() throws IOException
```



![Image](img/00010.jpeg)

**图 2.3** `Closeable`、`Flushable`、`Readable` 和 `Appendable` 接口，以及：

```java
void flush()
```

分别。`InputStream`、`OutputStream`、`Reader` 和 `Writer` 类都实现了 `Closeable` 接口。

### 2.1.3 组合输入输出过滤器

`FileInputStream` 和 `FileOutputStream` 提供了连接到磁盘文件的输入输出流。你需要将文件名或完整路径传递给构造函数。例如，点击此处查看代码图像：

```java
FileInputStream fin = new FileInputStream("employee.data");
```

在用户目录中查找名为 `employee.data` 的文件。

![Image](img/00003.jpeg)

> **提示**
>
> 所有 `java.io` 中的类都将相对路径解释为从用户目录开始。可以通过调用 `System.getProperty("user.dir")` 获取此目录。

![Image](img/00004.jpeg)

> **注意**
>
> 由于反斜杠字符是 Java 字符串中的转义字符，请确保对 Windows 风格路径使用 `\\`（例如 `C:\\Windows\\win.ini`）。在 Windows 中，你也可以使用单个正斜杠（`C:/Windows/win.ini`），因为大多数 Windows 文件处理调用会将正斜杠解释为文件分隔符。但不建议这样做——这种行为可能会改变。相反，对于可移植程序，请使用运行程序平台的文件分隔符。可以通过常量字符串 `java.io.File.separator` 获取。

与抽象 `InputStream` 和 `OutputStream` 类一样，这些类仅支持字节级别的读写。也就是说，我们只能从对象 `fin` 读取字节和字节数组。

```java
byte b = (byte) fin.read();
```

正如我们在下一节中将看到的，如果我们只有一个 `DataInputStream`，我们就可以读取数值类型：

```java
DataInputStream din = . . .;

double x = din.readDouble();
```

但正如 `FileInputStream` 没有读取数值类型的方法一样，`DataInputStream` 也没有从文件获取数据的方法。

Java 使用了一种巧妙的机制来分离两种不同的职责。某些输入流（例如 `FileInputStream` 和通过 `URL` 类的 `openStream` 方法返回的流）可以从文件和其他更奇特的位置检索字节。其他输入流（例如 `DataInputStream`）则可以将字节组装成更有用的数据类型。Java 程序员必须将两者结合起来。例如，为了能够从文件中读取数字，首先创建一个 `FileInputStream`，然后将其传递给 `DataInputStream` 的构造函数。

点击此处查看代码图片：

```java
FileInputStream fin = new FileInputStream("employee.dat");

DataInputStream din = new DataInputStream(fin);

double x = din.readDouble();
```

如果你再次查看图 2.1，你可以看到 `FilterInputStream` 和 `FilterOutputStream` 这两个类。这些类的子类被用于为处理字节的输入/输出流添加额外的功能。

你可以通过嵌套过滤器来添加多个功能。例如，默认情况下，输入流是没有缓冲的。也就是说，每次调用 `read` 都会请求操作系统分发另一个字节。相反，请求块块数据并将其存储在缓冲区中更高效。如果你既需要缓冲又需要文件的数据输入方法，你就需要使用下面这一串相当怪异的构造函数：

点击此处查看代码图片：

```java
DataInputStream din = new DataInputStream(
    new BufferedInputStream(
        new FileInputStream("employee.dat")));
```

注意，我们将 `DataInputStream` 放在构造函数链的最后，因为我们想要使用 `DataInputStream` 的方法，并且我们希望这些方法使用缓冲的 `read` 方法。

有时，当你将流链式连接时，可能需要跟踪中间输入流。例如，在读取输入时，你通常需要查看下一个字节，看它是否是你预期的值。Java 提供了 `PushbackInputStream` 用于此目的。

点击此处查看代码图片：

```java
PushbackInputStream pbin = new PushbackInputStream(
    new BufferedInputStream(
        new FileInputStream("employee.dat")));
```

现在你可以推测性地读取下一个字节：

```java
int b = pbin.read();
```

如果它不是你想要的，就将其推回：

```java
if (b != '<') pbin.unread(b);
```

然而，读取和推回是适用于回退（pushback）输入流的唯一方法。如果你想向前查看并同时读取数字，那么你既需要一个回退输入流引用和一个数据输入流引用。

点击此处查看代码图片：

```java
DataInputStream din = new DataInputStream(
    pbin = new PushbackInputStream(
        new BufferedInputStream(
            new FileInputStream("employee.dat"))));
```

当然，在其他编程语言的输入输出库中，缓冲和前瞻等等便利功能会自动被处理，因此在 Java 中诉诸组合流过滤器有点麻烦。然而，通过混合和匹配过滤器类来构建真正实用的输入/输出流序列的能力确实赋予了你巨大的灵活性。例如，你可以使用以下输入流序列从压缩的 ZIP 文件中读取数字（参见图 2.4）：

点击此处查看代码图片：

```java
ZipInputStream zin = new ZipInputStream(new FileInputStream("employee.zip"));

DataInputStream din = new DataInputStream(zin);
```

![Image](img/00011.jpeg)

**图 2.4** 一系列过滤后的输入流

（更多关于 Java 处理 ZIP 文件的信息，请参见第 2.3.3 节，第 77 页上的“ZIP 归档，”。）

### `java.io.FileInputStream` 1.0

- `FileInputStream(String name)`
- `FileInputStream(File file)`

使用由 `name` 字符串或 `file` 对象指定的路径名的文件创建一个新的文件输入流。（`File` 类在本章的末尾有描述。）非绝对路径名将相对于虚拟机启动时设置的工作目录进行解析。

### `java.io.FileOutputStream` 1.0

- `FileOutputStream(String name)`
- `FileOutputStream(String name, boolean append)`
- `FileOutputStream(File file)`
- `FileOutputStream(File file, boolean append)`

创建一个由 `name` 字符串或 `file` 对象指定的新的文件输出流。如果 `append` 参数为 `true`，则任何现有文件都不会被删除。

### `java.io.BufferedInputStream` 1.0

- `BufferedInputStream(InputStream in)`

创建一个缓冲输入流。缓冲输入流从流中读取字节。当缓冲区为空时读取数据。

### `java.io.BufferedOutputStream` 1.0

- `BufferedOutputStream(OutputStream out)`

创建一个缓冲输出流。缓冲输出流收集要写入的字节。当缓冲区满时，写入数据。

### `java.io.PushbackInputStream` 1.0

- `PushbackInputStream(InputStream in)`
- `PushbackInputStream(InputStream in, int size)`
- `void unread(int b)`

构造一个带有单字节前瞻的输入流；推回一个下次调用的字节。

## 2.2 文本输入与输出

保存数据时，你有二进制和文本格式可供。例如，如果整数 1234 以二进制保存，它被写入字节序列 `00 00 04 D2`。在文本格式下，它被保存为字符串 `"1234"`。虽然二进制 I/O 快速高效，但人类难以阅读。我们首先讨论文本 I/O，并在 2.3.3 节介绍二进制 I/O。

在保存文本字符串时，你需要考虑字符编码。在 Java 内部使用的 UTF-16 编码中，字符串 `"José"` 被编码为 `00 4A 00 6F 00 73 00 E9`（十六进制）。然而，许多程序期望文本文件以不同的编码格式存储。在互联网上最常用的 UTF-8 编码中，该字符串将被写入为 `4A 6F 73 C3 A9`，前三个字母没有零字节，而 é 字符有两个字节。

`OutputStreamWriter` 类将 Unicode 代码单元的输出流通过所选字符编码转换为字节流。相反，`InputStreamReader` 类将包含字节（以某种字符编码指定字符）的输入流转换为输出 Unicode 代码单元的读取器。

例如，这里是创建一个从控制台读取按键并将其转换为 Unicode 的读取器的方法：

```java
Reader in = new InputStreamReader(System.in);
```

此输入流读取器假设主机系统使用的默认字符编码。在桌面操作系统上，那可能是 Windows 1252 或 MacRoman 等古老的编码。你应该始终在 `InputStreamReader` 的构造函数中选择一个特定的编码，例如：

```java
Reader in = new InputStreamReader(
    new FileInputStream("data.txt"),
    StandardCharsets.UTF_8);
```

关于字符编码的更多信息，请参见第 2.2.4 节“字符编码”或第 67 页。

### 2.2.1 如何编写文本输出

对于文本输出，请使用 `PrintWriter`。该类具有以文本格式打印字符串和数字的方法。它有一个用于向文件打印的便利构造函数。该语句：

```java
PrintWriter out = new PrintWriter("employee.txt", "UTF-8");
```

等于：

```java
PrintWriter out = new PrintWriter(
    new FileOutputStream("employee.txt"), "UTF-8");
```

要向写入器写入内容，请使用与在 `System.out` 中相同的 `print`、`println` 和 `printf` 方法。你可以使用这些方法打印数字（`int`、`short`、`long`、`float`、`double`）、字符、`boolean` 值、字符串和对象。

例如，考虑这段代码：

```java
String name = "Harry Hacker";

double salary = 75000;

out.print(name);

out.print(' ');

out.println(salary);
```

这会将字符 `Harry Hacker 75000.0` 写入写入器 `out`。随后，这些字符会被转换为字节并存储在文件 `employee.txt` 中。

`println` 方法会在行尾添加目标系统正确的换行符（Windows 上为 `"\r\n"`，UNIX 上为 `"\n"`）。这是通过调用 `System.getProperty("line.separator")` 获取的字符串。

如果写入器被设置为自动刷新（autoflush）模式，则每当调用 `println` 时，缓冲区中的所有字符都会发送到目的地。（打印写入器始终带缓冲的。）默认情况下，未启用自动刷新。你可以通过 `PrintWriter(Writer writer, boolean autoFlush)` 构造函数启用或禁用自动刷新：

```java
PrintWriter out = new PrintWriter(
    new OutputStreamWriter(
        new FileOutputStream("employee.txt"), "UTF-8"),
    true); // autoflush
```

`print` 方法不会抛出异常。你可以调用 `checkError` 方法来查看输出流是否出现错误。

![Image](img/00002.jpeg)

> **注意事项**
>
> Java 老兵们可能会好奇 `PrintStream` 类和 `System.out` 到底发生了什么。在 Java 1.0 中，`PrintStream` 类简单地通过丢弃高字节将所有 Unicode 字符截断为 ASCII 字符。（此时，Unicode 仍然是 16 位的编码）。显然，这不是一种整洁或可移植的方法，并在 Java 1.1 引入读取器（readers）和写入器（writers）得到了解决。为了兼容现有代码，`System.in`、`System.out` 和 `System.err` 仍然是输入/输出流，而不是读取器和写入器。但现在，`PrintStream` 类内部以与 `PrintWriter` 相同的方式将 Unicode 字符转换为默认的主机编码。当使用 `print` 和 `println` 方法时，`PrintStream` 对象的行为与打印写入器完全相同，但与打印写入器不同，它们允许你通过 `write(int)` 和 `write(byte[])` 方法输出原始字节。

### `java.io.PrintWriter` 1.1

- `PrintWriter(Writer out)`
- `PrintWriter(Writer writer)`

创建一个新的 `PrintWriter`，向给定的写入器写入内容。

- `PrintWriter(String filename, String encoding)`
- `PrintWriter(File file, String encoding)`

创建一个新的 `PrintWriter`，使用给定的字符编码向给定文件写入内容。

- `void print(Object obj)`

通过打印 `toString` 产生的字符串来打印对象。

- `void print(String s)`

打印包含 Unicode 编码单元的字符串。

- `void println(String s)`

打印字符串后跟一个换行终止符。如果输出流处于自动刷新模式，则刷新输出流。

- `void print(char[] s)`

打印给定数组中的所有 Unicode 编码单元。

- `void print(char c)`

打印一个 Unicode 编码单元。

- `void print(int i)`
- `void print(long l)`
- `void print(float f)`
- `void print(double d)`
- `void print(boolean b)`

- `void printf(String format, Object... args)`

按照格式字符串指定的打印给定值。格式字符串的规范请参见第一卷第 3 章。

- `boolean checkError()`

如果发生格式化或输出错误，则返回 `true`。一旦输出流遇到错误，它就会被污染，所有对 `checkError` 的调用将返回 `true`。

### 2.2.2 如何读取输入

处理任意文本简单的方法是我们在第一卷中广泛使用的 `Scanner` 类。你可以从任何输入流构造 `Scanner`。或者，你可以像这样将文件读取到字符串：

```java
String content = new String(Files.readAllBytes(path));
```

但如果你想将文件作为行的序列，请调用：

```java
List<String> lines = Files.readAllLines(path, charset);
```

在 Java 的早期版本中，唯一的输入是 `BufferedReader`。它的 `readLine()` 方法产生一行，或者在没有输入时返回 `null`。典型的循环如下：

```java
InputStream inputStream = ...

try (BufferedReader in = new BufferedReader(
        new InputStreamReader(
            inputStream, StandardCharsets.UTF_8))) {

    String line;

    while ((line = in.readLine()) != null) {
        // 处理 line
    }
}
```



`BufferedReader` 类还有一个产生 `Stream<String>` 的 `lines()` 方法。然而，与 `Scanner` 不同，`BufferedReader` 没有读取数字的方法。

## 2.2.3 以文本格式对象

在本节中，我们将通过一个示例程序将 `Employee` 记录数组存储在文本文件中。每个记录存储在单独的一行。实例字段通过分隔符分离。我们使用竖线 `|` 作为我们的分隔符。（冒号 `:` 也是另一个流行选择。有趣的地方在于每个人使用不同的分隔符。）自然地，我们不考虑保存的字符串中出现 `|` 可能发生的问题。

这里是一组示例记录：

```text
Harry Hacker|35000|1989-10-01
Carl Cracker|75000|1987-12-15
Tony Tester|38000|1990-03-15
```

写入记录很简单。由于我们要写入文本文件，因此使用 `PrintWriter` 类。我们只需写入所有字段，后面跟一个 `|`，或者对于最后一个字段跟 `\n`。这项工作由添加到 `Employee` 类中的以下 `writeData` 方法完成：

```java
public static void writeEmployee(PrintWriter out, Employee e) {
    out.println(e.getName() + "|" + e.getSalary() + "|" + e.getHireDay());
}
```

为了读取记录，我们逐行读取并分离字段。我们使用 `Scanner` 读取每行，然后使用 `String.split` 方法将行分为标记。

```java
public static Employee readEmployee(Scanner in) {
    String line = in.nextLine();
    String[] tokens = line.split("\\|");
    String name = tokens[0];
    double salary = Double.parseDouble(tokens[1]);
    LocalDate hireDate = LocalDate.parse(tokens[2]);
    int year = hireDate.getYear();
    int month = hireDate.getMonthValue();
    int day = hireDate.getDayOfMonth();
    return new Employee(name, salary, year, month, day);
}
```

```java
return new Employee(name, salary, year, month, day);
}
```

`split` 方法的参数是一个描述分隔符的正则表达式。我们将在本章末尾详细地讨论正则表达式。事实上，竖线字符 `|` 在正则表达式中具有特殊含义，因此需要用 `\` 字符进行转义。该字符本身需要用另一个 `\` 进行转义，从而产生 `"\\|"` 表达式。

完整的程序在列表 2.1 中。静态方法：

```java
void writeData(Employee[] e, PrintWriter out)
```

首先写入数组的长度，然后写入每条记录。静态方法：

```java
Employee[] readData(BufferedReader in)
```

首先读取数组的长度，然后读取每条记录。这似乎有点棘手：

```java
int n = in.nextInt();
in.nextLine(); // consume newline

Employee[] employees = new Employee[n];

for (int i = 0; i < n; i++) {
    employees[i] = new Employee();
    employees[i].readData(in);
}
```

对 `nextInt` 的调用读取了数组长度，但没有读取最后的换行符。我们必须消耗掉换行符，以便 `readData` 方法在调用 `nextLine` 方法时获取下一行输入。

**列表 2.1** `textFile/TextFileTest.java`

```java
1   package textFile;

2

3   import java.io.*;

4   import java.time.*;

5   import java.util.*;

6

7   /**
8    * @version 1.14 2016-07-11
9    * @author Cay Horstmann
10   */
11  public class TextFileTest
12  {
13      public static void main(String[] args) throws IOException
14      {
15          Employee[] staff = new Employee[3];
16
17          staff[0] = new Employee("Carl Cracker", 75000, 1987, 12, 15);
18          staff[1] = new Employee("Harry Hacker", 50000, 1989, 10, 1);
19          staff[2] = new Employee("Tony Tester", 40000, 1990, 3, 15);
20
21          // 保存所有员工记录到文件 employee.dat
22          try (PrintWriter out = new PrintWriter("employee.dat", "UTF-8"))
23          {
24              writeData(staff, out);
25          }
26
27          // 将所有记录读取到新数组
28          try (Scanner in = new Scanner(
29                  new FileInputStream("employee.dat"), "UTF-8"))
30          {
31              Employee[] newStaff = readData(in);
33
34              // 新读取的员工记录
34              for (Employee e : newStaff)
35                  System.out.println(e);
36          }
37      }
38
39      /**
40       * 将数组中的所有员工写入打印器
41       * @param employees 员工数组
42       * @param out 打印器
43       */
44      private static void writeData(Employee[] employees, PrintWriter out) throws IOException
45      {
46          // 员工人数
47          out.println(employees.length);
48
49          for (Employee e : employees)
50              writeEmployee(out, e);
53
      /**
54      * 从扫描器读取员工数组
55      * @param in 扫描器
56      * @return 员工数组
57      */
58      private static Employee[] readData(Scanner in)
59      {
60          // 获取数组大小
61          int n = in.nextInt();
62          in.nextLine(); // 消耗换行符
63
64          Employee[] employees = new Employee[n];
65          for (int i = 0; i < n; i++)
66          {
67              employees[i] = readEmployee(in);
68          }
69          return employees;
71      }
71
      /**
73       * 将员工数据写入打印器
74       * @param out 打印器
75       */
76      public static void writeEmployee(PrintWriter out, Employee e)
77      {
78          out.println(e.getName() + "|" + e.getSalary() + "|" + e.getHireDay());
81
      /**
82       * 从缓冲读取读取员工数据
83       * @param in 扫描器
84       */
85      public static Employee readEmployee(Scanner in)
86      {
87          String line = in.nextLine();
88          String[] tokens = line.split("\\|");
89          String name = tokens[0];
90          double salary = Double.parseDouble(tokens[1]);
91          LocalDate hireDate = LocalDate.parse(tokens[2]);
92          int year = hireDate.getYear();
93          int month = hireDate.getMonthValue();
94          int day = hireDate.getDayOfMonth();
95          return new Employee(name, salary, year, month, day);
96      }
97}
```

## 2.2.4 字符编码

输入和输出流用于处理字节序列，但在许多情况下，你将处理文本——即字符序列。这时，如何将字符编码为字节就变得重要了。

Java 使用 Unicode 标准来处理字符。每个字符或“代码点”都有一个 21 位的整数。字符如何编码为字节至关重要。

Java 使用 Unicode 标准来处理字符。

输入和输出流用于处理字节序列，但在许多情况下，你将处理文本——即字符序列。这时，如何将字符编码为字节就变得重要了。

Java 使用 Unicode 标准来处理字符。每个字符或“代码点”都有一个 21 位的整数。字符如何编码为字节至关重要。

最常见的编码是 UTF-8，它将 Unicode 代码点编码为一到四个字节（参见表 2.1）。UTF-8 的优势在于 ASCII 字符集中的字符只占用一个字节。

![图片](img/00013.jpeg)

**表 2.1** UTF-8

另一种常见的编码是 UTF-16，它将 Unicode 代码点编码为一个或两个字节（参见表 2.2）。这是 Java 字符串使用的编码。实际上，UTF-16 有两种形式，被称为“大端”和“小端”。为了指示使用的是哪一种，文件可以以“字节顺序标记” `0xFF` 开始。在大端格式下，高位字节在前：`0x21` 后跟 `0x22`。在小端格式下，则相反：`0x22` 后跟 `0x21`。读取器可以使用此值确定字节序并将其丢弃。

![图片](img/00014.jpeg)

**表 2.2** UTF-16

![图片](img/00004.jpeg) 注意

某些程序（包括记事本）会在 UTF-8 头部添加字节顺序标记。显然，这是没有，因为 UTF-8 没有字节序问题。但 Unicode 标准允许这样做，甚至建议这是一个好主意，因为它减少了对编码的疑问。在读取 UTF-8 文件时应该移除该标记。遗憾的是，Java 没有这样做，针对该问题的错误报告已被关闭为“不修复”。最好的办法是在输入中删除任何领先的 `\uFEFF`。

除了 UTF 编码外，还有适用于特定用户群的字符范围的部分编码。例如，ISO 8859-1 是一种包含西欧语言使用的重音字符的单字节编码。Shift-JIS 是日语字符的变长编码。大量此类编码仍在使用中。

没有可靠的方法可以从字节流中自动检测字符编码。某些 API 方法允许你使用“默认字符集”——计算机操作系统偏好的字符编码。这正是你的字节源所使用的编码吗？这些字节可能源自世界的其他地方。因此，你应该显式指定编码。例如，在读取网页时，检查 `Content-Type` 头部。

![图片](img/00002.jpeg) Note

平台编码由静态方法 `Charset.defaultCharset()` 返回。静态方法 `Charset.availableCharsets()` 返回所有可用的 `Charset` 实例，以从规范名称到 `Charset` 对象的映射形式。

![Image](img/00004.jpeg) 注意事项

Java 的 Oracle 实现包含一个系统属性 `file.encoding` 用于覆盖平台默认设置。这不是一个官方支持的属性，且 Oracle 的 Java 库实现中的所有部分并不都一致遵循它。你不应该设置它。

`StandardCharsets` 类具有类型为 `Charset` 的静态变量，用于每个 Java 虚拟机必须支持的字符编码：

```java
StandardCharsets.UTF_8
StandardCharsets.UTF_16
StandardCharsets.UTF_16BE
StandardCharsets.UTF_16LE
StandardCharsets.ISO_8859_1
StandardCharsets.US_ASCII
```

要获取另一种编码的 `Charset`，请使用静态方法 `forName`：

```java
Charset shiftJIS = Charset.forName("Shift-JIS");
```

在读取或写入文本时使用 `Charset` 对象。例如，你可以将字节数组转换为字符串，如下：

```java
String str = new String(bytes, StandardCharsets.UTF_8);
```



![Image](img/00003.jpeg) 提示

某些方法允许你使用 `Charset` 对象或字符串来指定字符编码。选择 `StandardCharsets` 常量，这样就不必担心拼写是否正确了。例如，`new String(bytes, "UTF 8")` 是不可接受的，并且会导致运行时错误。

![Image](img/00004.jpeg) 注意事项

如果不指定任何编码，某些方法（如 `String(byte[])` 构造函数）将使用默认平台编码；而其他方法（如 `Files.readAllLines`）则使用 UTF-8。

### 2.3 读取和写入二进制数据

文本格式便于测试和调试，因为它是人类可读的，但不如以二进制格式传输数据那样高效。在接下来的章节中，你将学习如何对二进制数据进行输入输出。

#### 2.3.1 `DataInput` 和 `DataOutput` 接口

`DataOutput` 接口定义了以下方法用于以二进制格式写入数字、字符、`boolean` 值或字符串：

点击此处查看代码图片

- `writeChars`
- `writeByte`
- `writeInt`
- `writeShort`
- `writeLong`
- `writeFloat`
- `writeDouble`
- `writeChar`
- `writeBoolean`
- `writeUTF`

例如，`writeInt` 无论数字位数多少，总是将整数作为 4 字节的二进制量写入，而 `writeDouble` 总是将 `double` 写入 8 字节的二进制量。生成的输出不是人类可读的，但对于给定类型的每个值所需的空间是相同的，且将其读回比解析文本更快。

![Image](img/00002.jpeg) 注意

在内存中存储整数和浮点数有两种不同的方法，取决于你所使用的处理器。例如，假设你正在处理一个 4 字节的 `int`，例如十进制数字 1234 或十六进制的 4D2（1234 = 4 × 256 + 13 × 16 + 2）。该值可以这样存储：内存中四个字节中的第一个持有数值的高有效字节（MSB）：`00 00 04 D2`。这就是所谓的大端序。或者，我们可以从最低有效字节（LSB）开始：`D2 04 00 00`。这很自然地被称为小端序。例如，SPARC 使用大端序；Pentium 使用小端序。这可能会导致问题。当从 C 或 C++ 文件保存文件时，数据是完全按照处理器存储的方式保存的。这使得即使是最简单的数据文件从一个平台移动到另一个平台也具有挑战性。在 Java 中，无论处理器如何，所有值都以大端序方式写入。这使得 Java 数据文件与平台无关。

`writeUTF` 方法使用修改版的 8 位 Unicode 转换格式写入字符串数据。它不是简单地使用标准的 UTF-8 编码，而是首先将 Unicode 代码单元序列表示为 UTF-16，然后使用 UTF-8 规则对结果进行编码。这种修改编码对于代码高于 `0xFFFF` 的字符是不同的。它是为了与在 Unicode 增长到 16 位之前构建的虚拟机兼容。

由于没有其他人使用这种修改过的 UTF-8，你应该只使用 `writeUTF` 方法写入用于 Java 虚拟机的字符串——例如，在生成字节码的程序中。其他用途请使用 `writeChars` 方法。

要读回数据，请使用 `DataInput` 接口中定义的以下方法：

点击此处查看代码图片

- `readInt`
- `readShort`
- `readLong`
- `readFloat`
- `readDouble`
- `readChar`
- `readBoolean`
- `readUTF`

`DataInputStream` 类实现了 `DataInput` 接口。要从文件读取二进制数据，请将 `DataInputStream` 结合 `FileInputStream`：

点击此处查看代码图片

```java
DataInputStream in = new DataInputStream(new FileInputStream("employee.dat"));
```

同样，写入二进制数据，使用实现 `DataOutput` 接口的 `DataOutputStream` 类：

点击此处查看代码图片

```java
DataOutputStream out = new DataOutputStream(new FileOutputStream("employee.dat"));
```

### `java.io.DataInput` 1.0

- `readBoolean()`
- `readByte()`
- `readChar()`
- `readDouble()`
- `readFloat()`
- `readInt()`
- `readLong()`
- `readShort()`

读取给定类型的值。

- `readFully(byte[] b)`

读取数组 `b` 直到所有字节读完。

- `readFully(byte[] b, int off, int len)`

读取数组 `b` 直到所有字节读完。

- `readUTF()`

读取修改 UTF-8 格式的字符串。

- `skipBytes(int n)`

跳过 `n` 个字节直到所有字节都跳过。

### `java.io.DataOutput` 1.0

- `writeBoolean(boolean b)`
- `writeByte(int b)`
- `writeChar(int c)`
- `writeDouble(double d)`
- `writeFloat(float f)`
- `writeInt(int i)`
- `writeLong(long l)`
- `writeShort(int s)`

写入给定类型的值。

- `writeChars(String s)`

写入字符串中的所有字符。

- `writeUTF(String s)`

写入修改 UTF-8 格式的字符串。

#### 2.3.2 随机访问文件

`RandomAccessFile` 类允许文件的任何地方读写数据。磁盘文件是随机访问的，但与网络套字通信的输入输出不是。你可以以只读或读写方式打开随机访问文件；通过在构造函数的第二个参数中使用字符串 `"r"`（读取访问）或 `"rw"`（读写访问）来指定选项。

点击此处查看代码图片

```java
RandomAccessFile in = new RandomAccessFile("employee.dat", "r");

RandomAccessFile inOut = new RandomAccessFile("employee.dat", "rw");
```

当你作为 `RandomAccessFile` 打开一个现有文件时，它不会被删除。

随机访问文件有一个文件指针，指示下一个要读取或写入的字节的位置。`seek` 方法可以将文件指针设置到文件内的任意字节位置。`seek` 的参数是介于零和文件字节长度之间的 `long` 整数。

`getFilePointer` 方法返回文件指针的当前位置。

`RandomAccessFile` 类同时实现了 `DataInput` 和 `DataOutput` 接口。要从随机访问文件读写，请使用我们在前一节中讨论过的 `readInt`/`writeInt` 以及 `readChar`/`writeChar` 等方法。

让我们来看一个示例程序，该程序在随机访问文件中存储了员工记录。每条记录的大小都相同。这使得读取任意记录变得非常容易。假设你想将文件指针定位到第三条记录。只需将文件指针设置为相应的字节位置并开始读取即可。

点击此处查看代码图片

```java
long n = 3;

in.seek((n - 1) * RECORD_SIZE);

Employee e = new Employee();

e.readData(in);
```

如果您想修改记录并将其保存回相同的位置，请记住将文件指针设回记录的开头：

点击此处查看代码图片

```java
in.seek((n - 1) * RECORD_SIZE);

e.writeData(out);
```

要确定文件的总字节数，请使用 `length` 方法。记录总数是文件长度除以每条记录的大小。

点击此处查看代码图片

```java
long nbytes = in.length(); // 字节数长度

int nrecords = (int) (nbytes / RECORD_SIZE);
```

整数和浮点值在二进制格式下具有固定的大小，但对于字符串，我们必须花费更多努力。我们提供了两个辅助方法，用于写入和读取固定长度的字符串。

`writeFixedString` 从字符串的开始处写入指定数量的代码单元。如果代码单元太少，该方法将使用零值对字符串进行填充。

点击此处查看代码图片

```java
public static void writeFixedString(String s, int size, DataOutput out)
    throws IOException
{
    for (int i = 0; i < size; i++)
    {
        char ch = 0;
        if (i < s.length()) ch = s.charAt(i);
        out.writeChar(ch);
    }
}
```

`readFixedString` 方法从输入流中读取字符，直到消耗了 `size` 个代码单元或遇到值为零值的字符。然后，它会跳过输入字段中剩余的零值。为了提高效率，该方法使用 `StringBuilder` 类来读取字符串。

点击此处查看代码图片

```java
public static String readFixedString(int size, DataInput in)
    throws IOException
{
    StringBuilder b = new StringBuilder(size);
    int i = 0;
    boolean more = true;
    while (more && i < size)
    {
        char ch = in.readChar();
        i++;
        if (ch == 0) more = false;
        else b.append(ch);
    }
    in.skipBytes(2 * (size - i));
    return b.toString();
}
```

我们将 `writeFixedString` 和 `readFixedString` 方法放置在 `DataIO` 辅助类中。

要写入一个固定大小的记录，我们只需以二进制形式写入所有字段。

点击此处查看代码图片

```java
DataIO.writeFixedString(e.getName(), Employee.NAME_SIZE, out);

out.writeDouble(e.getSalary());

LocalDate hireDay = e.getHireDay();

out.writeInt(hireDay.getYear());

out.writeInt(hireDay.getMonthValue());

out.writeInt(hireDay.getDayOfMonth());
```

读回数据同样简单。

点击此处查看代码图片

```java
String name = DataIO.readFixedString(Employee.NAME_SIZE, in);

double salary = in.readDouble();

int y = in.readInt();

int m = in.readInt();

int d = in.readInt();
```

让我们计算每条记录的大小。我们将为姓名字符串使用 40 个字符。因此，每条记录包含 100 个字节：

- 40 个字符 = 80 字节用于姓名
- 1 个 `double` = 8 字节用于薪水
- 3 个 `int` = 12 字节用于日期

Listing 2.2 所示的程序向数据文件写入三条记录，然后按反序从文件中读取它们。为了高效实现这一点需要随机访问——我们需要获取最后一条记录。

**Listing 2.2** `randomAccess/RandomTest.java`

点击此处查看代码图片

```java
package randomAccess;

import java.io.*;
import java.util.*;
import java.time.*;

/**
 * @version 1.13-07-01
 * @author Caymann
 */
public class RandomTest
{
    public static void main(String[] args) throws IOException
    {
        // ... (实现代码)
    }
}
```

读取 `in` 的内容：

```java
zin.closeEntry();

}

zin.close();
```

要写入 ZIP 文件，请使用 `ZipOutputStream`。对于你想要放入 ZIP 文件的每个条目（entry），创建一个 `ZipEntry` 对象。将文件名传递给 `ZipEntry` 构造函数；它会设置文件日期和解压缩方法等其他参数。如果你需要，可以重写这些设置。然后，调用 `ZipOutputStream` 的 `putNextEntry` 方法开始写入一个新文件。将文件数据发送到 ZIP 输出流。完成后，调用 `closeEntry`。对你想要存储的所有文件重复此操作。以下是一个代码框架：

点击此处查看代码图片

```java
FileOutputStream fout = new FileOutputStream("test.zip");

ZipOutputStream zout = new ZipOutputStream(fout);

for all files
{
    ZipEntry ze = new ZipEntry(filename);

    zout.putNextEntry(ze);

    // send data to zout

    zout.closeEntry();
}

zout.close();
```



**注意**

JAR 文件（在第一卷第 13 章中讨论过）仅仅是带有特殊条目的 ZIP 文件——即所谓的清单文件（manifest）。使用`JarInputStream`和`JarOutputStream`类来读取和写入清单文件条目。

ZIP 输入流是流抽象能力强大的一个极佳示例。当你读取以压缩形式存储的数据时，你不需要担心数据在被请求时正在被解压缩。此外，ZIP 流中字节的源头不必非是一个文件——ZIP 数据可以来自网络连接。事实上，每当 applet 的类加载器读取 JAR 文件时，它都是从网络上读取并解压缩数据的。

**注意**

第 2.5.8 节，“ZIP 文件系统”位于第 115 页，展示了如何使用 Java SE 7 的`FileSystem`类在无需特殊 API 的情况下访问 ZIP 存档。

### java.util.zip.ZipInputStream **1.1**

- `ZipInputStream(InputStream in)`
  创建一个`ZipInputStream`，允许你从给定的`InputStream`膨胀出数据。
- `ZipEntry getNextEntry()`
  返回下一个条目的`ZipEntry`对象，如果没有更多条目，则返回`null`。
- `void closeEntry()`
  关闭 ZIP 文件中当前打开的条目。然后你可以通过`getNextEntry()`读取下一个条目。

### java.util.zip.ZipOutputStream **1.1**

- `ZipOutputStream(OutputStream out)`
  创建一个`ZipOutputStream`，你可以用它将压缩数据写入指定的`OutputStream`。
- `void putNextEntry(ZipEntry ze)`
  将给定的`ZipEntry`中的信息写入输出流，并为数据准备好流的位置。然后可以通过调用`write()`方法写入数据。
- `void closeEntry()`
  关闭 ZIP 文件中当前打开的条目。使用`putNextEntry`方法开始下一个条目。
- `void setLevel(int level)`
  设置后续`DEFLATED`条目的默认压缩级别。默认值是`Deflater.DEFAULT_COMPRESSION`。如果级别无效，则抛出`IllegalArgumentException`。
- `void setMethod(int method)`
  为此`ZipOutputStream`的任何未指定方法的条目设置默认压缩方法。

### java.util.zip.ZipEntry **1.1**

- `ZipEntry(String name)`
  使用给定名称构造一个 zip 条目。
- `long getCrc()`
  返回此`ZipEntry`的 CRC32 校验和。
- `String getName()`
  返回此条目的名称。
- `long getSize()`
  返回此条目的未压缩前的大小，如果未知未压缩大小，则返回`-1`。
- `boolean isDirectory()`
  如果此条目是一个目录，则返回`true`。
- `void setMethod(int method)`
- `void setSize(long size)`
  设置此条目的大小。只有当压缩方法为`STORED`时才需要。
- `void setCrc(long crc)`
  设置此条目的 CRC32 校验和。使用`CRC32`类计算此校验和。只有当压缩方法为`STORED`时才需要。

### java.util.zip.ZipFile **1.1**

- `ZipFile(String name)`
- `ZipFile(File file)`
  为从给定的`File`读取而创建一个`ZipFile`。
- `Enumeration entries()`
  返回一个枚举所有条目的`Enumeration`。
- `ZipEntry getEntry(String name)`
  返回对应名称的条目，如果没有则返回`null`。
- `InputStream getInputStream(ZipEntry ze)`
  返回给定条目的`InputStream`。
- `String getName()`
  返回文件的路径。

## 2.4 对象输入输出流与序列化

使用固定长度格式对于需要存储相同类型的数据是一个很好的选择。然而，面向对象程序中创建的对象很少是相同类型。幸运的是，Java 语言支持一种通用的机制，称为*序列化*，它可以将任何对象写入输出流并再次读取。（你将在本章看到“序列化”这一术词的来源。）

### 2.4.1 保存与加载对象

要保存对象数据，你首先需要打开`ObjectOutputStream`：

```java
ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream("employee.dat"));
```

现在，要保存一个对象，只需如下片段所示使用`ObjectOutputStream`的`writeObject`方法：

```java
Employee harry = new Employee("Harry Hacker", 50000, 1989, 10, 1);
Manager boss = new Manager("Carl Cracker", 80000, 1987, 12, 15);
out.writeObject(harry);
out.writeObject(boss);
```

要读回对象，首先获取一个`ObjectInputStream`对象：

```java
ObjectInputStream in = new ObjectInputStream(new FileInputStream("employee.dat"));
```

然后，按照写入的顺序使用`readObject`方法检索对象：

```java
Employee e1 = (Employee) in.readObject();
Employee e2 = (Employee) in.readObject();
```

然而，对于任何想要保存到输出流并从对象输入流恢复的类，你都需要进行一个更改。该类必须实现`Serializable`接口：

```java
class Employee implements Serializable { . . . }
```

`Serializable`接口没有方法，因此你不需要以任何方式更改你的类。在这方面，它与我们在第一卷第 6 章中讨论过的`Cloneable`接口相似。然而，为了使类可克隆，你仍然需要重写`Object`类的`clone`方法。要使一个类可序列化，你不需要做其他任何操作。

在后台，`ObjectOutputStream`会查看对象的所有字段并保存其内容。例如，在写入一个`Employee`对象时，名称、日期和薪水字段会被写入输出流中。

然而，我们仍然需要考虑一种重要情况：当一个对象作为多个对象状态的一部分被多个对象共享时，会发生什么呢？

为了说明这个问题，让我们对`Manager`类进行细微修改。假设每个经理都有一位秘书：

```java
class Manager extends Employee
{
   private Employee secretary;
   . . .
}
```

现在每个`Manager`对象都包含一个指向描述秘书的`Employee`引用。当然，两个经理可以共享同一个秘书，正如图 2.5 和下面的代码所示：

```java
harry = new Employee("Harry Hacker", . . .);
Manager carl = new Manager("Carl Cracker", . . .);
carl.setSecretary(harry);
Manager tony = new Manager("Tony Tester", . . .);
tony.setSecretary(harry);
```

**图 2.5** 两个经理可以共享同一个员工。

保存这样一个对象网络是一项挑战。当然，我们无法保存并恢复秘书对象的内存地址。当一个对象被重新加载时，它占据的内存地址可能与原始完全不同。

相反，每个对象都是通过`serial number`（序列号）来保存的，因此这种机制被称为“对象序列化”。以下是其算法：

1. 为你遇到的每个对象引用关联一个序列号（如图 2.6 所示）。
2. 当第一次遇到某个对象引用时，将对象数据保存到输出流中。
3. 如果之前已经保存过，只需写入“与之前保存的序列号为`x`的对象相同”。

在读回对象时，过程是反过来的。

1. 当在对象输入流中第一次指定某个对象时，构造它，用流数据对其进行初始化，并记住序列号与对象引用之间的关联。
2. 当遇到标签“与之前保存的序列号为`x`的对象相同”时，获取该序列号对应的对象引用。

**图 2.6** 对象序列化的示例

**注意**

在本章中，我们将使用序列化将一组对象保存到磁盘文件中，并完全按照我们存储的方式将其检索。另一个非常重要的应用是跨网络连接将一组对象传输到另一台计算机。正如同原始内存地址在文件中没有意义，它们在与不同的处理器通信时也同样无效。通过用序列号替换内存地址，序列化允许对象集合从一台机器传输到另一台机器。

代码列表 2.3 是一个保存并重新加载`Employee`和`Manager`对象网络的程序（其中某些对象共享同一个员工作为秘书）。注意，重新加载后秘书对象是唯一的——当`newStaff[1]`获得薪时，这会反映在经理的`secretary`字段中。

**代码列表 2.3** `objectStream/ObjectStreamTest.java`

```java
1   package objectStream;
2
3   import java.io.*;
4
5   /**
6    * @version 1.10 17 Aug 1998
7    * @author Cay Horstmann
8    */
9   class ObjectStreamTest
10  {
11     public static void main(String[] args) throws IOException, ClassNotFoundException
12     {
13         Employee harry = new Employee("Harry Hacker", 50000, 1989, 10, 1);
14         Manager carl = new Manager("Carl Cracker", 80000, 1987, 12, 15);
15         carl.setSecretary(harry);
16         Manager tony = new Manager("Tony Tester", 40000, 1990, 10, 1);
17         tony.setSecretary(harry);
18
19         Employee[] staff = new Employee[3];
20
21         staff[0] = carl;
22         staff[1] = harry;
23         staff[2] = tony;
24
25         // save all records to the file
26         try (ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream("employee.dat")))
27         {
28             out.writeObject(staff);
29         }
30
31         // retrieve all records into an array
32         try (ObjectInputStream in = new ObjectInputStream(new FileInputStream("employee.dat")))
33         {
34             Employee[] newStaff = (Employee[]) in.readObject();
35
36             // print the newly read records
37             for (Employee e : newStaff) {
38                 System.out.println(e);
39             }
40         }
41     }
42 }
```

`SHA`是一种快速算法，用于为较大的信息块生成一个“指纹”。无论原始数据的大小如何，该指纹始终是一个 20 字节的数据包。它是通过对数据进行一系列巧妙的位操作创建的，这使得我们几乎百分之百确定，如果信息发生任何变化，指纹就会随之改变。（有关`SHA`的更多细节，请参考 William Stallings 编写的 *Cryptography and Network Security, Seventh Edition*，Prentice Hall, 2016。）然而，序列化机制仅使用`SHA`码的前八字节作为类的指纹。如果数据字段或方法发生变化，类指纹极有可能也会发生变化。

在读取对象时，会将将其指纹与类的当前指纹进行比较。如果它们不匹配，则意味着在对象写入之后类定义发生了变化，并且会产生一个异常。当然，在实践中，类确实会演进，程序可能需要读取旧版本的对象。我们将在第 2.4.5 节中的“版本控制，”（第 95 页）讨论这个问题。

```java
static final byte SC_WRITE_METHOD = 1;
   // 类中有一个 writeObject 方法，用于写入额外数据
static final byte SC_SERIALIZABLE = 2;
   // 类实现了 Serializable 接口
static final byte SC_EXTERNALIZABLE = 4;
   // 类实现了 Externalizable 接口
```

我们将在在本章稍后讨论`Externalizable`接口。`Externalizable`类提供了自定义的读写方法，用于接管其实例字段的输出。我们编写的类实现了`Serializable`接口，其标志值将为`02`。可序列化的`java.util.Date`类定义了自己的`readObject`/`writeObject`方法，标志位为`03`。

每个数据字段描述符的格式如下：

- 1 字节类型代码
- 2 字节的字段名长度
- 字段名
- 类名（如果字段是对象）

类型代码是以下之一：

```
B      byte
C      char
D      double
F      float
I      int
J      long
L      object
S      short
Z      boolean
       array
```



当类型代码为 `L` 时，字段名后紧跟着字段类型。类名和字段名字符串不以字符串代码 `74` 开头，但字段类型是。字段类型使用与其名称略有不同的编码——即原生方法所使用的格式。

例如，`Employee` 类的 `salary` 字段被编码为：

`D 00 06 salary`

这里是 `Employee` 类的完整类描述符：

![Image](img/00030.jpeg)

这些描述符相当长。如果文件中需要同一个类描述符，则使用缩写形式：

![Image](img/00031.jpeg)

序列号指向上一个显式类描述符。我们将在稍后讨论该编号方案。

对象以如下方式存储：

![Image](img/00032.jpeg)

例如，这里是 `Employee` 对象的存储方式：

![Image](img/00033.jpeg)

如你所见，数据文件包含了恢复 `Employee` 对象所需的信息。

数组按照以下格式保存：

![Image](img/00034.jpeg)

类描述符中的数组类名与原生方法使用的格式相同（与其它类描述符中类名使用的格式略有不同）。在这种格式中，类名以 `L` 开头并以分号结尾。

例如，一个包含三个 `Employee` 对象的数组开头如下：

![Image](img/00035.jpeg)

注意，`Employee` 对象数组的指纹与 `Employee` 类本身的指纹是不同的。

所有对象（包括数组和字符串）以及所有类描述符在保存时都会被赋予序列号。序列号从 `00 7E` 开始。序列号指向上一个显式类描述符。我们将在稍后讨论该编号方案。

我们将在本章稍后讨论 `Externalizable` 接口。`Externalizable` 类提供了自定义的读写方法，用于接管其实例字段的输出。我们编写的类实现了 `Serializable` 接口，其标志值将为 `02`。可序列化的 `java.util.Date` 类定义了自己的 `readObject`/`writeObject` 方法，标志位为 `03`。

## 2.4.3 修改序列化机制

某些数据字段不应被序列化——例如存储文件句柄的整数值或对原生方法有意义的窗口句柄。当你重新加载对象或将其传输到不同的机器时，这些信息保证是无用的。事实上，此类字段的不正确值实际上会导致原生方法崩溃。

Java 有一种简单的机制可以防止此类字段被序列化：使用 `transient` 关键字标记它们。序列化机制允许单个类在默认的读写行为中添加验证或其他任何操作。可序列化类可以定义签名如下的方法：

点击此处查看代码图片

```java
private void readObject(ObjectInputStream in) throws IOException, ClassNotFoundException;

private void writeObject(ObjectOutputStream out) throws IOException;
```

然后，数据字段不再被自动序列化，而是调用这些方法。

这是一个典型的示例。`java.awt.geom` 包中的许多类（如 `Point2D.Double`）不是可序列化的。现在假设你想序列化一个存储 `String` 和 `Point2D.Double` 的 `LabeledPoint` 类。首先，你需要将 `Point2D.Double` 字段标记为 `transient` 以避免 `NotSerializableException`。

点击此处查看代码图片

```java
public class LabeledPoint implements Serializable
{
    private String label;

    private transient Point2D.Double point;

    // ...
}
```

在 `writeObject` 方法中，我们首先通过 `defaultWriteObject` 方法来写入对象描述符和 `String` 类型的字段 `label`。这是 `ObjectOutputStream` 类的一个特殊方法，只能在可序列化类的 `writeObject` 方法内部调用。然后，我们使用标准的 `DataOutput` 调用写入点坐标。

点击此处查看代码图片

```java
private void writeObject(ObjectOutputStream out)
   throws IOException
{
   out.defaultWriteObject();
   out.writeDouble(point.getX());
   out.writeDouble(point.getY());
}
```

在 `readObject` 方法中，我们反向执行该过程：

点击此处查看代码图片

```java
private void readObject(ObjectInputStream in)
   throws IOException
{
   in.defaultReadObject();
   double x = in.readDouble();
   double y = in.readDouble();
   point = new Point2D.Double(x, y);
}
```

另一个例子是 `java.util.Date` 类，它提供了自己的 `readObject` 和 `writeObject` 方法。这些方法将日期作为从纪元（UTC 时间 1970 年 1 月 1 日午夜）开始的毫秒数写入。`Date` 类有一个复杂的内部表示，同时存储一个 `Calendar` 对象和一个毫秒计数，以优化查找。`Calendar` 的状态是冗余的，不需要保存。

`readObject` 和 `writeObject` 方法只需要保存和加载它们的数据字段。它们不应该关心父类数据或任何其他类信息。

与其让序列化机制来保存和恢复对象数据，不如类可以定义它自己的机制。要做到这一点，类必须实现 `Externalizable` 接口。这又要求它定义两个方法：

点击此处查看代码图片

```java
public void readExternal(ObjectInputStream in)
   throws IOException, ClassNotFoundException;

public void writeExternal(ObjectOutputStream out)
   throws IOException;
```

与上一节描述的 `readObject` 和 `writeObject` 方法不同，这些方法完全负责保存和恢复整个对象，包括父类数据。在写入对象时，序列化机制仅在输出流中记录对象的类类型。在读取一个可外部化对象时，对象输入流会使用无参数构造函数创建一个对象，然后调用 `readExternal` 方法。以下是你可以为 `Employee` 类实现这些方法：

点击此处查看代码图片

```java
public void readExternal(ObjectInput s)
   throws IOException
{
   name = s.readUTF();
   salary = s.readDouble();
   hireDay = LocalDate.ofEpochDay(s.readLong());
}

public void writeExternal(ObjectOutput s)
   throws IOException
{
   s.writeUTF(name);
   s.writeDouble(salary);
   s.writeLong(hireDay.toEpochDay());
}
```

> **注意**
>
> 与私有的且只能由序列化机制调用的 `readObject` 和 `writeObject` 方法不同，`readExternal` 和 `writeExternal` 方法是公共的。特别是，`readExternal` 可能会允许修改现有对象的状态。

## 2.4.4 序列化单例和类型安全枚举

你必须特别注意被假设为唯一的对象的序列化和反序列化。这通常在你实现单例模式和类型安全枚举时发生。

如果你使用 Java 语言的 `enum` 结构，你就不需要担心序列化问题——它能正常工作。但是，假设你维护的遗留代码包含一个类似枚举的枚举类型，例如：

点击此处查看代码图片

```java
public class Orientation
{
   public static final Orientation HORIZONTAL = new Orientation(1);

   public static final Orientation VERTICAL = new Orientation(2);

   private int value;

   private Orientation(int v) { value = v; }
}
```

这种惯用法在 Java 语言添加枚举之前很常见。注意，构造函数是私有的。因此，除了 `Orientation.HORIZONTAL` 和 `Orientation.VERTICAL` 之外，无法创建任何对象。特别是，你可以使用 `==` 运算符来测试对象的相等性：

点击此处查看代码图片

```java
if (orientation == Orientation.HORIZONTAL) . . .
```

当类型安全枚举实现 `Serializable` 接口时，有一个你需要记住的重要转折点。默认的序列化机制并不合适。假设我们写入一个 `Orientation` 的值并再次读取它：

点击此处查看代码图片

```java
Orientation original = Orientation.HORIZONTAL;

ObjectOutputStream out = . . .;

out.write(original);

out.close();

ObjectInputStream in = . . .;

Orientation saved = (Orientation) in.read();
```

现在 `if (saved == Orientation.HORIZONTAL)` 会失败。事实上，`saved` 是一个与任何定义的常量都不相等的新对象。即使构造函数是私有的，序列化机制也能创建对象！

为了解决这个问题，你需要定义另一个特殊方法 `readResolve`。在对象反序列化后，如果定义了 `readResolve` 方法，它会被调用。它返回的对象将作为 `readObject` 方法的结果。在本例中，`readResolve` 方法将检查 `value` 字段并返回相应的常量：

点击此处查看代码图片

```java
protected Object readResolve()
{
   if (value == 1) return Orientation.HORIZONTAL;

   if (value == 2) return Orientation.VERTICAL;

   throw new ObjectStreamException();
}
```

为你遗留代码中的所有类型安全枚举以及遵循单例模式的类添加 `readResolve` 方法。

## 2.4.5 版本控制

如果你使用序列化来保存对象，你需要考虑程序演进时会发生什么。版本 1.1 能读取旧文件吗？使用 1.0 的用户能读取新版本生成的文件吗？显然，如果对象文件能够处理类的演进将会理想。

当类发生任何变化时，其指纹也会发生变化，你知道对象输入流将拒绝读取指纹不同的对象。然而，类可以指示它与早期版本兼容。要做到这一点，你必须先获取早期版本的指纹。使用 JDK 部分的独立 `serialver` 程序获取此数字。例如，运行 `serialver Employee` 会打印：

点击此处查看代码图片

```text
Employee: static final long serialVersionUID = -181423982551734065L;
```

如果你带有 `-show` 启动 `serialver` 程序，程序会弹出一个图形对话框（参见图 2.7）。

![Image](img/00037.jpeg)

**图 2.7** `serialver` 程序的图形界面

类的所有后续版本必须定义与原始指纹相同的 `serialVersionUID` 常量。

点击此处查看代码图片

```java
class Employee implements Serializable // 版本 1.1
{
   . . .

   public static final long serialVersionUID = -1814239825517340645L;
}
```

当类有一个名为 `serialVersionUID` 的静态数据成员时，它将不再手动计算指纹，而是使用该值。

一旦该静态数据成员被放置在类内部，序列化系统现在就可以读取该类的不同版本的对象。

如果仅类的方法发生了变化，那么读取新对象的数据没有问题。然而，如果数据字段发生了变化，你可能会遇到问题。例如，旧文件对象的数据字段可能比程序中的字段多或少，或者数据字段的类型可能不同。在这种情况下，对象输入流会尽力将序列化对象转换为该类的当前版本。

对象输入流会将类当前版本的数据字段与序列化对象中对应版本的数据字段进行比较。当然，对象输入流只考虑非瞬态（`nontransient`）和非静态（`nonstatic`）的数据字段。如果两个字段的名称相同但类型不同，对象输入流不会尝试将一种类型转换为另一种类型——这些对象是不兼容的。

如果序列化对象具有当前版本中不存在的数据字段，则对象输入流将忽略这些额外的数据。如果当前版本具有序列化对象中不存在的数据字段，则新增的字段将被设置为它们的默认值（对象为 `null`，数字为 `0`，`boolean` 值为 `false`）。

这里有一个示例。假设我们之前使用类的原始版本（1.0）在磁盘上保存了一些员工记录。现在我们通过添加一个名为 `department` 的数据字段将 `Employee` 类更改为版本 2.0。图 2.8 显示了当 1.0 对象被到使用 2.0 对象的程序时会发生什么。`department` 字段被设置为 `null`。图 2.9 显示了相反的情况：一个使用 1.0 对象的程序读取一个 2.0 对象。额外的 `department` 字段被忽略。

![Image](img/00038.jpeg)

**图 2.8** 读取数据字段较少的对象

![Image](img/00039.jpeg)

**图 2.9** 读取数据字段较多的对象

这个过程安全吗？这取决于情况。丢弃一个数据字段似乎无害的——接收方仍然拥有所有它知道如何操作的数据。但将数据字段设置为 `null` 可能并不那么安全。许多类都努力在所有构造函数中将所有数据字段初始化为非 `null` 值，这样方法就不需要准备处理 `null` 数据。类类设计者在 `readObject` 方法中实现额外的代码来修复版本不兼容问题，或者确保方法足够健壮以处理 `null` 数据。

## 2.4.6 使用序列化进行克隆

序列化机制有一个有趣的用途：只要类是可序列化的，它就为你提供了一种克隆对象的简单方法。只需将其序列化到输出流，然后将其读回即可。结果是一个是现有对象的深拷贝的新对象。你不需要将对象写入文件——可以使用 `ByteArrayOutputStream` 将数据保存到字节数组中。

如列表 2.4 所示，要免费获得 `clone` 方法，只需扩展 `SerialCloneable` 类即可完成。

你应该意识到，这种方法虽然很聪明，但通常会比显式构造新对象并复制或克隆数据字段的 `clone` 方法慢得多。

**列表 2.4** `serialClone/SerialCloneTest.java`

点击此处查看代码图像

```java
package serialClone;

/**
   * @version 1.21 13 Jul 2016
   * @author Cay Horstmann
 */

import java.io.*;
import java.util.*;
import java.time.*;

public class SerialCloneTest
{
    public static void main(String[] args) throws CloneNotSupportedException
    {
        Employee harry = new Employee("Harry Hacker", 35000, 1989, 10, 1);

        // clone harry
        Employee harry2 = (Employee) harry.clone();

        // mutate harry
        harry.raiseSalary(10);

        // now harry and the clone are different
        System.out.println(harry);
        System.out.println(harry2);
    }
}

/**
 * 一个克隆方法使用序列化的类。
 */

class SerialCloneable implements Cloneable, Serializable
{
    public Object clone() throws CloneNotSupportedException
    {
        try {
            // save the object to a byte array

            ByteArrayOutputStream bout = new ByteArrayOutputStream();
```



```java
try (ObjectOutputStream out = new ObjectOutputStream(bout)) {
    out.writeObject(this);
}

// read a clone of the object from the byte array
try (InputStream bin = new ByteArrayInputStream(bout.toByteArray())) {
    ObjectInputStream in = new ObjectInputStream(bin);
    return in.readObject();
}
```

```java
catch (IOException | ClassNotFoundException e) {
    CloneNotSupportedException e2 = new CloneNotSupportedException();
    e2.initCause(e);
    throw e2;
}
```

```java
/**
 * 熟悉的类，重新定义以扩展
 * SerialCloneable 类。
 */
class Employee extends SerialCloneable {
    private String name;
    private double salary;
    private LocalDate hireDay;

    public Employee(String n, double s, int year, int month, int day) {
        name = n;
        salary = s;
        hireDay = LocalDate.of(year, month, day);
    }

    public String getName() {
        return name;
    }

    public double getSalary() {
        return salary;
    }

    public LocalDate getHireDay() {
        return hireDay;
    }

    /**
     * 提高此员工的薪水。
     * @byPercent 增加的百分比
     */
    public void raiseSalary(double byPercent) {
        double raise = salary * byPercent / 100;
        salary += raise;
    }

    public String toString() {
        return getClass().getName()
            + "[name=" + name
            + ",salary=" + salary
            + ",hireDay=" + hireDay
            + "]";
    }
}
```

## 操作文件

你已经学习了如何从文件读取和写入数据。然而，文件管理不仅仅是读写。`Path` 接口和 `Files` 类封装了与用户文件系统工作的功能。例如，`Files` 类可以用于删除或重命名文件，或者查找文件的最后修改时间。换句话说，输入输出流类关注文件的内容，而这里讨论的类关注文件在磁盘上的存储。

`Path` 接口和 `Files` 类是在 Java SE 7 中引入的。它们比追溯到 JDK 1.0 的 `File` 类要方便得多。我们预计它们会受 Java 程序员欢迎，并进行深入讨论。

### 2.5.1 路径

`Path` 是目录名称的序列，可选地跟随着一个文件名。路径的第一个组件可以是*根组件*，例如 `/` 或 `C:\`。允许的根组件取决于文件系统。以根组件开头的路径是*绝对路径*。否则，它是*相对路径*。例如，在这里我们构造了一个绝对路径和一个相对路径。对于绝对路径，我们假设了一个 UNIX 风格的文件系统。

点击此处查看代码图像：

```java
Path absolute = Paths.get("/home", "harry");
```

```java
Path relative = Paths.get("myprog", "conf", "user.properties");
```

静态方法 `Paths.get` 接收一个或多个字符串，并使用默认文件系统的路径分隔符将其连接起来（类 Unix 文件系统使用 `/`，Windows 使用 `\`）。然后它会解析结果，如果结果在给定的文件系统中不是有效路径，则抛出 `InvalidPathException`。结果是一个 `Path` 对象。

`get` 方法可以获取一个包含多个组件的单个字符串。例如，你可以像这样从配置文件中读取路径：

点击此处查看代码图片：

```java
String baseDir = props.getProperty("base.dir");

// 可能是形如 /opt/myprog 或 c:\Program Files\myprog 的字符串
Path basePath = Paths.get(baseDir); // baseDir 包含分隔符是允许的
```

![Image](img/00002.jpeg) 注意

路径并不对应于实际存在的文件。它仅仅是名称的抽象序列。正如你在下一节中看到的，当你想要创建一个文件时，首先创建一个路径，然后调用方法来创建相应的文件。

组合或 `resolve` 路径是非常常见的。调用 `p.resolve(q)` 根据以下规则返回一个路径：

- 如果 `q` 是绝对路径，则结果为 `q`。
- 否则，根据文件系统的规则，结果为 `p` 后接 `q`。

例如，假设你的应用程序需要相对于从配置文件读取的给定基目录查找其工作目录，如前面的示例所示。

点击此处查看代码图片：

```java
Path workRelative = Paths.get("work");
Path workPath = basePath.resolve(workRelative);
```

`resolve` 方法有一个快捷方法，可以接收字符串而不是路径：

点击此处查看代码图片：

```java
Path workPath = basePath.resolve("work");
```

有一个便利方法 `resolveSibling`，它可以相对于路径的父目录进行解析。例如，如果 `workPath` 是 `/opt/myapp/work`，调用以下代码将创建 `/opt/myapp/temp`。

```java
Path tempPath = workPath.resolveSibling("temp");
```

`resolve` 的相反操作是 `relativize`。调用 `p.relativize(r)` 产生路径 `q`，该路径与 `p` 解析后会产生 `r`。例如，相对于 `/home/input.txt` 对 `/home/harry` 进行相对化得到 `../input.txt`。这里假设 `..` 表示文件系统中的父目录。

`normalize` 方法移除任何 `.` 和 `..` 组件（或文件系统认为冗余的任何）。例如，将路径 `/home/harry/../fred/./input.txt` 规范化得到 `/home/fred/input.txt`。

`toAbsolutePath` 方法产生给定路径的绝对路径，从根组件开始，例如 `/home/fred/input.txt` 或 `c:\Users\fred\input.txt`。

`Path` 接口有许多拆解路径的有用方法。此代码示例显示了其中一些常用的：

点击此处查看代码图片：

```java
Path p = Paths.get("/home", "fred", "myprog.properties");

Path parent = p.getParent(); // 路径 /home/fred
Path file = p.getFileName(); // 路径 myprog.properties
Path root = p.getRoot(); // 路径
```

正如你已经在第一卷中所看到的，你可以从 `Path` 对象构造一个 `Scanner`：

点击此处查看代码图片：

```java
Scanner in = new Scanner(Paths.get("/home/fred/input.txt"));
```

![Image](img/00002.jpeg) 注意

偶尔，你可能需要与使用 `File` 类而不是 `Path` 接口的遗留 API 进行交互。`Path` 接口有一个 `toFile` 方法，而 `File` 类有一个 `toPath` 方法。

**java.nio.file.Paths (7)**

- `static Path get(String first, String... more)` 通过连接给定的字符串创建路径。

**java.nio.file.Path (7)**

- `Path resolve(Path other)`
- `Path resolve(String other)` 如果 `other` 是绝对路径，则返回 `other`；否则返回连接 `this` 和 `other` 得到的路径。
- `Path resolveSibling(Path other)`
- `Path resolveSibling(String other)` 如果 `other` 是绝对路径，则返回 `other`；否则返回连接 `this` 的父目录和 `other` 得到的路径。
- `Path relativize(Path other)` 返回相对路径，该路径与 `this` 解析后产生 `other`。
- `Path normalize()` 移除冗余路径元素如 `.` 和 `..`。
- `Path toAbsolutePath()` 返回等于此路径的绝对路径。
- `Path getParent()` 返回父目录，如果此路径没有父目录则返回 `null`。
- `Path getFileName()` 返回此路径的最后一个组件，如果此路径没有组件则返回 `null`。
- `Path getRoot()` 返回此路径的根组件，如果此路径没有根组件则返回 `null`。
- `toFile()` 从此路径创建一个 `File`。

**java.io.File (1.0)**

- `Path toPath()` (7) 从此文件创建一个 `Path`。

### 2.5.2 读取和写入文件

`Files` 类可以快速处理常见的文件操作。例如，你可以轻松地读取文件的全部内容：

点击此处查看代码图片：

```java
byte[] bytes = Files.readAllBytes(path);
```

如果你想将文件作为字符串读取，调用 `readAllBytes` 然后是：

点击此处查看代码图片：

```java
String content = new String(bytes);
```

但如果你想将文件作为行序列，调用：

点击此处查看代码图片：

```java
List<String> lines = Files.readAllLines(path, charset);
```

相反，如果你想写入字符串，调用：

点击此处查看代码图片：

```java
Files.write(path, content.getBytes(charset));
```

要追加到给定文件，使用：

点击此处查看代码图片：

```java
Files.write(path, content.getBytes(charset), StandardOpenOption.APPEND);
```

你还可以使用 `Files.write(path, lines)` 写入集合。

这些简单方法适用于处理中等文本的文件。如果你的文件很大或是二进制文件，仍然可以使用熟悉的输入/输出流或读者/写入器：

```java
InputStream in = Files.newInputStream(path);
OutputStream out = Files.newOutputStream(path);
Reader in = Files.newBufferedReader(path, charset);
Writer out = Files.newBufferedWriter(path, charset);
```

这些便利方法避免了处理 `FileInputStream`、`FileOutputStream`、`BufferedReader` 或 `BufferedWriter` 的麻烦。

**java.nio.file.Files (7)**

- `static byte[] readAllBytes(Path path)`
- `static List<String> readAllLines(Path path, Charset charset)` 读取文件内容。
- `static Path write(Path path, byte[] contents, OpenOption... options)`
- `static Path write(Path path, Iterable<? extends CharSequence> contents, OpenOption options)` 将给定内容写入文件并返回 `path`。
- `static InputStream newInputStream(Path path, OpenOption... options)`
- `static OutputStream newOutputStream(Path path, OpenOption... options)`
- `static BufferedReader newBufferedReader(Path path, Charset charset)`
- `static BufferedWriter newBufferedWriter(Path path, Charset charset, OpenOption... options)` 打开文件以读取或写入。

### 2.5.3 创建文件和目录

创建新目录调用 `Files.createDirectory(path)`。

路径中最后一个组件以外的所有部分必须已存在。要创建中间目录，请使用 `Files.createDirectories(path)`。

可以使用 `Files.createFile(path)` 创建空文件。

如果文件已存在，调用将抛出异常。存在性检查和创建是原子的。如果文件不存在，它将在其他人有机会执行之前被创建。

提供了便捷方法，可以在给定位置或系统特定位置创建临时文件或目录。

点击此处查看代码图像：

```java
Path newPath = Files.createTempFile(dir, prefix, suffix);
```

```java
Path newPath = Files.createTempFile(prefix, suffix);
```

```java
Path newPath = Files.createTempDirectory(dir, prefix);
```

```java
Path newPath = Files.createTempDirectory(prefix);
```



在这里，`dir` 是一个 `Path`，而 `prefix`/`suffix` 是可能为 `null` 的字符串。例如，调用 `Files.createTempFile(null, ".txt")` 可能返回一个类似 `/tmp/1234405522364837194.txt` 的路径。

创建文件或目录时，你可以指定属性，例如所有者或权限。然而，细节取决于文件系统，我们在这里不介绍这些内容。

***

`java.nio.file.Files` **7**

- `static Path createFile(Path path, FileAttribute<?>... attrs)`
- `static Path createDirectory(Path path, FileAttribute<?>... attrs)`
- `static Path createDirectories(Path path, FileAttribute<?>... attrs)`

创建一个文件或目录。`createDirectories` 方法还会创建任何中间目录。

- `static Path createTempFile(String prefix, String suffix, FileAttribute<?>... attrs)`
- `static Path createTempFile(Path parentDir, String prefix, String suffix, FileAttribute<?>... attrs)`
- `static Path createTempDirectory(String prefix, FileAttribute<?>... attrs)`
- `static Path createTempDirectory(Path parentDir, String prefix, FileAttribute<?>... attrs)`

在适合临时文件的位置或给定的父目录中创建临时文件或目录。返回所创建的文件或目录的路径。

***

#### 2.5.4 复制、移动和删除文件

要将文件从一个位置复制到另一个位置，只需调用：

```java
Files.copy(fromPath, toPath);
```

移动文件（即复制并删除原始文件），调用：

```java
Files.move(fromPath, toPath);
```

如果目标存在，则复制或移动将失败。如果你想覆盖已有的目标，使用 `REPLACE_EXISTING` 选项。如果你想复制所有文件属性，使用 `COPY_ATTRIBUTES` 选项。你可以像这样提供两个选项：

点击此处查看代码图像

```java
Files.copy(fromPath, toPath, StandardCopyOption.REPLACE_EXISTING,
    StandardCopyOption.COPY_ATTRIBUTES);
```

你可以指定移动应该是原子的。这样你就能确保移动要么成功完成，要么源文件依然。使用 `ATOMIC_MOVE` 选项：

点击此处查看代码图像

```java
Files.move(fromPath, toPath, StandardCopyOption.ATOMIC_MOVE);
```

你也可以将输入流复制到 `Path`，这意味着只需将输入流保存到磁盘。同样，你可以将 `Path` 复制到输出流。使用以下调用：

点击此处查看代码图像

```java
Files.copy(inputStream, toPath);
Files.copy(fromPath, outputStream);
```

与其他 `copy` 调用一样，你可以根据需要提供复制选项。

最后，要删除文件，只需调用：

```java
Files.delete(path);
```

如果文件不存在，此方法会抛出异常，因此你可能更想使用：

点击此处查看代码图像

```java
boolean deleted = Files.deleteIfExists(path);
```

删除方法也可以用于删除空目录。

查看表 2.3 以获取文件操作可用选项的摘要。

![图像](img/00040.jpeg)

**表 2.3** 文件操作的标准选项

***

`java.nio.file.Files` **7**

- `static Path copy(Path from, Path to, CopyOption... options)`
- `static Path move(Path from, Path to, CopyOption... options)`

将 `from` 复制或移动到给定的目标位置并返回 `to`。

- `static long copy(InputStream from, Path to, CopyOption... options)`
- `static long copy(Path from, OutputStream to, CopyOption... options)`

从输入流复制到文件或从文件复制到输出流，返回复制的字节数。

- `static void delete(Path path)`
- `static boolean deleteIfExists(Path path)`

删除给定的文件或空目录。如果文件或目录不存在，第一个方法会抛出异常。在这种情况下，第二个方法返回 `false`。

***

#### 2.5.5 获取文件信息

以下静态方法返回 `boolean` 值以检查路径的属性：

- `exists`
- `isHidden`
- `isReadable`
- `isWritable`
- `isExecutable`
- `isRegularFile`
- `isDirectory`
- `isSymbolicLink`

`size` 方法返回文件的字节数。`getOwner` 返回文件的所有者，作为 `java.nio.file.attribute.UserPrincipal` 的实例。基础属性封装在 `BasicFileAttributes` 中，它报告：

- 文件创建、最后访问、最后修改的时间（`FileTime` 实例）
- 是否为普通文件、目录、符号链接
- 文件大小

要获取这些属性，调用：

```java
BasicFileAttributes attributes = Files.readAttributes(path, BasicFileAttributes.class);
```

如果你知道文件系统是 POSIX 标准的，可以获取 `PosixFileAttributes` 实例：

```java
PosixFileAttributes attributes = Files.readAttributes(path, PosixFileAttributes.class);
```

然后你可以找到文件的组、所有者和权限。我们不讨论这些许多跨操作系统的细节。

***

`java.nio.file.Files` **7**

- `static boolean exists(Path path)`
- `static boolean isHidden(Path path)`
- `static boolean isReadable(Path path)`
- `static boolean isWritable(Path path)`
- `static boolean isExecutable(Path path)`
- `static boolean isRegularFile(Path path)`
- `static boolean isDirectory(Path path)`
- `static boolean isSymbolicLink(Path path)`

检查路径给定的属性。

- `static long size(Path path)`
- `static A readAttributes(Path path, Class<A> type, LinkOption... options)`

读取类型 `A` 的文件属性。

***

`java.nio.file.attribute.BasicFileAttributes` **7**

- `FileTime creationTime()`
- `FileTime lastAccessTime()`
- `FileTime lastModifiedTime()`
- `boolean isRegularFile()`
- `boolean isDirectory()`
- `boolean isSymbolicLink()`
- `long size()`
- `Object fileKey()`

获取请求的属性。

***

#### 2.5.6 访问目录项

静态 `Files.list` 方法返回一个读取目录内容的 `Stream<Path>`。目录是延迟读取的，使得处理具有大量条目的目录是可能的。由于读取目录涉及需要关闭的系统资源，你应该使用 `try` 块：

点击此处查看代码图像

```java
try (Stream<Path> entries = Files.list(pathToDirectory)) {
    // . . .
}
```

`list` 方法不会进入子目录。要处理目录的所有后代，请改用 `Files.walk` 方法。

点击此处查看代码图像

```java
try (Stream<Path> entries = Files.walk(pathToRoot)) {
    // 包含所有后代，按深度优先顺序访问
}
```

这里是解压后 `src.zip` 树的示例遍历：

```text
java
java/nio
java/nio/DirectCharBufferU.java
java/nio/ByteBufferAsShortBufferRL.java
java/nio/MappedByteBuffer.java
. . .
java/nio/ByteBufferAsDoubleBufferB.java
java/nio/charset
java/nio/charset/CoderMalfunctionError.java
java/nio/charset/CharsetDecoder.java
java/nio/charset/UnsupportedCharsetException.java
java/nio/charset/spi
java/nio/charset/spi/CharsetProvider.java
java/nio/charset/StandardCharsets.java
java/nio/charset/Charset.java
. . .
java/nio/charset/CoderResult.java
java/nio/HeapFloatBufferR.java
. . .
```

如你所见，每当遍历产生目录时，它会在继续处理其兄弟节点之前进入该目录。

你可以通过调用 `Files.walk(pathToRoot, depth)` 来限制想要访问的树深度。两个 `walk` 方法都有一个类型为 `FileVisitOption...` 的变长参数，但你只能提供一个选项：`FOLLOW_LINKS` 用于跟踪符号链接。

***

![Image](img/00002.jpeg) 注意

如果你对 `walk` 返回的路径进行过滤，并且你的过滤标准涉及与目录一起存储的文件属性，例如大小、创建时间或类型（文件、目录、符号链接），请使用 `find` 方法而不是 `walk`。调用该方法时，传入一个接受路径和 `BasicFileAttributes` 对象的谓词函数。唯一的优势是效率。因为目录正在被读取，这些属性是可以直接获取的。

***

这段代码片段使用 `Files.walk` 方法将一个目录复制到另一个目录：

点击此处查看代码图片

```java
Files.walk(source).forEach(p -> {
    try {
        Path q = target.resolve(source.relativize(p));

        if (Files.isDirectory(p))
            Files.createDirectory(q);
        else
            Files.copy(p, q);
    }
    catch (IOException ex) {
        throw new UncheckedIOException(ex);
    }
});
```

遗憾的是，你不能轻松使用 `Files.walk` 方法来删除目录树，因为你需要在删除父节点之前先删除子节点。下一节将向你展示如何解决这个问题。

### 2.5.7 使用目录流（Directory Streams）

正如你在上一节看到的，`Files.walk` 方法产生一个遍历目录后代的 `Stream<Path>`。有时，你需要对遍历过程进行更细粒度的控制。在这种情况下，请使用 `Files.newDirectoryStream` 对象。它产生一个 `DirectoryStream`。注意，这并不是 `java.util.stream.Stream` 的子接口，而是一个专门为目录遍历设计的接口。它是 `Iterable` 的子接口，因此你可以在增强型 `for` 循环中使用目录流。其用法模式如下：

点击此处查看代码图片

```java
try (DirectoryStream<Path> entries = Files.newDirectoryStream(dir)) {
    for (Path entry : entries) {
        Process entries
    }
}
```

`try-with-resources` 块确保目录流被正确关闭。

目录条目的访问顺序没有特定的规定。

你可以使用 `glob` 模式来过滤文件：

点击此处查看代码图片

```java
try (DirectoryStream<Path> entries = Files.newDirectoryStream(dir, "*.java"))
```

表 2.4 显示了所有的 `glob` 模式。

![Image](img/00041.jpeg)

**表 2.4** Glob 模式

***

![Image](img/00004.jpeg) 注意

如果你在 Windows 上使用 `glob` 语法，必须对反斜杠进行*两次*转义：第一次是为了 `glob` 语法，第二次是为了 Java 字符串语法：`Files.newDirectoryStream(dir, "C:\\\\").`。

***

如果你想访问目录的所有后代，请调用 `walkFileTree` 方法并提供一个类型为 `FileVisitor` 的对象。该对象会被通知：

- 当遇到文件时：`FileVisitResult visitFile(T path, BasicFileAttributes attrs)`
- 在处理目录之前：`FileVisitResult preVisitDirectory(T dir, IOException ex)`
- 在处理目录之后：`FileVisitResult postVisitDirectory(T dir, IOException ex)`
- 当尝试访问文件或目录时发生错误时（例如尝试在没有相应权限的情况下打开目录）：`FileVisitResult visitFileFailed(T path, IOException ex)`

在每种情况下，你可以指定想要：

- 继续访问下一个文件：`FileVisitResult.CONTINUE`
- 继续遍历，但不访问此目录中的条目：`FileVisitResult.SKIP_SUBTREE`
- 继续遍历，但不访问该文件的兄弟节点：`FileVisitResult.SKIP_SIBLINGS`
- 终止遍历：`FileVisitResult.TERMINATE`

如果任何一个方法抛出异常，遍历也将终止，并且该异常将从 `walkFileTree` 方法抛出。

***

![Image](img/00002.jpeg) 注意

`FileVisitor` 接口是一个泛型，但你可能想要 `FileVisitor<Path>` 之外的东西。`walkFileTree` 方法愿意接受 `FileVisitor<Path>`，但 `Path` 并没有多余。

***

一个 `SimpleFileVisitor` 实现了 `FileVisitor` 接口。除了 `visitFileFailed` 方法之外都不执行并继续。`visitFileFailed` 方法抛出导致失败的异常。例如，这里是你可以打印给定目录的所有子目录的方法：

点击此处查看图片

```java
Files.walkFileTree(Paths.get("/"), new SimpleVisitor<Path>() {
    public FileVisitResult preVisitDirectory(
            Path path, BasicAttributes attrs) throws IOException {
        System.out.println(path);
        return FileVisitResult.CONTINUE;
    }

    public FileVisitResult postVisitDirectory(
            Path dir, IOException e) throws IOException {
        if (e != null) throw e;

        Files.delete(dir);
        return FileVisitResult.CONTINUE;
    }
});
```



注意我们需要重写 `postVisitDirectory` 和 `visitFileFailed`。否则，一旦遇到无法打开的目录或无法访问的文件就会失败。此外，注意路径的属性是作为参数传递给 `preVisitDirectory` 和 `visitFile` 方法的。访问者已经需要进行 OS 调用来区分文件和目录。通过这种方式，你不需要再次调用。

这是删除目录树的完整代码：

点击此处查看代码图片

```java
// 删除从 root 开始的目录树

Files.walkFileTree(root, new SimpleVisitor<Path>() {

    public FileVisitResult visitFile(Path file, BasicAttributes attrs) throws IOException {

        Files.delete(file);

        return FileVisitResult.CONTINUE;

    }

    public FileVisitResult postVisitDirectory(Path dir, IOException e) throws IOException {

        if (e != null) throw e;

        Files.delete(dir);

        return FileVisitResult.CONTINUE;

    }

});
```

---

## `java.nio.file.Files`

- `static DirectoryStream<Path> newDirectoryStream(Path path)`
- `static DirectoryStream<Path> newDirectoryStream(Path path, String glob)`

获取给定目录中文件和目录的迭代器。第二个方法仅接受给定 glob 模式的条目。

- `static Path walkFileTree(Path start, FileVisitor<? super Path> visitor)`

遍历给定路径的所有后代，对所有后代应用访问者。

---

## `java.nio.file.SimpleFileVisitor<T>`

- `static FileVisitResult visitFile(T path, BasicFileAttributes attrs)`

当访问文件或目录时被调用，返回 `CONTINUE`、`SKIP_SUBTREE`、`SKIP_SIBLINGS` 或 `TERMINATE` 之一。默认实现不做任何操作并继续。

- `static FileVisitResult preVisitDirectory(T dir, BasicFileAttributes attrs)`
- `static FileVisitResult postVisitDirectory(T dir, BasicFileAttributes attrs)`

在访问目录之前和之后被调用。默认实现不做任何操作并继续。

- `static FileVisitResult visitFileFailed(T path, IOException exc)`

如果在尝试获取给定文件的信息时抛出异常，则调用此方法。默认实现重新抛出该异常，导致访问在该异常终止。如果你想继续，请重写该方法。

### 2.5.8 ZIP 文件系统

`Paths` 类在默认文件系统（用户本地磁盘上的文件）中查找路径。你也可以拥有其他文件系统。其中一个非常有用的系统是 ZIP 文件系统。如果 `zipname` 是一个 ZIP 文件的名称，那么调用：

点击此处查看代码图片

```java
FileSystem fs = FileSystems.newFileSystem(Paths.get(zipname), null);
```

将建立一个包含 ZIP 存档中所有文件的文件系统。如果你知道它的名称，从该存档中拷贝文件是非常容易的：

点击此处查看代码图片

```java
Files.copy(fs.getPath(sourceName), targetPath);
```

在这里，`fs.getPath` 是任意文件系统的 `Paths.get` 的类比方法。

要列出 ZIP 存档中的所有文件，请遍历文件树：

点击此处查看代码图片

```java
FileSystem fs = FileSystems.newFileSystem(Paths.get(zipname), null);

Files.walkFileTree(fs.getPath("/"), new SimpleFileVisitor<Path>()
   {
      public FileVisitResult visitFile(Path file, BasicFileAttributes attrs) throws IOException
      {
          System.out.println(file);
          return FileVisitResult.CONTINUE;
      }
   });
```

这比第 2.3.3 节中描述的“ZIP 存档，”在第 77 页上的 API 要好，后者为了处理 ZIP 存档需要一组新类。

---

#### `java.nio.file.FileSystem`

- `static FileSystem newFileSystem(Path path, ClassLoader loader)`

遍历已安装的文件系统提供者，并且在 `loader` 不为 `null` 的情况下，返回给定类加载器可以加载的文件系统。返回由第一个接受给定路径的文件系统提供者创建的文件系统。默认情况下，有一个用于 ZIP 文件系统的提供者，接受以 `.zip` 或 `.jar` 结尾的文件。

---

#### `java.nio.file.FileSystem`

- `static Path getPath(String first, String... more)`

通过连接给定的字符串创建一个路径。

## 2.6 内存映射文件

大多数操作系统都可以利用虚拟内存实现将文件（或文件的某个区域）“映射”到内存中。然后就可以像访问内存数组一样访问文件，这比传统的文件操作要快得多。

### 2.6.1 内存映射文件的性能

在本节末尾，你可以找到一个程序，它分别使用传统文件输入和内存映射文件计算文件的 CRC32 校验和。在某机器上，当计算 JDK 中 `jre/lib` 目录下 37MB 文件 `rt.jar` 的校验和时，我们得到了表 2.5 所示的时间数据。

![图像](img/00042.jpeg)

**表 2.5** 文件操作计时数据

如你所见，在特定的机器上，内存映射比使用缓冲顺序输入快一点，并且比使用 `RandomAccessFile` 快得多。

当然，精确值在不同机器之间会有很大差异，但显而易见，与随机访问相比，性能提升是巨大的。另一方面，对于大小文件的顺序读取，没有理由使用内存映射。

`java.nio` 包使得内存映射变得非常简单。以下是操作步骤。

首先，获取文件的通道（channel）。通道是磁盘文件的抽象，允许你访问操作系统特性，如内存映射、文件锁定和文件之间的快速数据传输。

点击此处查看代码图片

```java
FileChannel channel = FileChannel.open(path, options);
```

然后，通过调用 `FileChannel` 的 `map` 方法从通道获取一个 `ByteBuffer`。指定你想要映射的文件区域。支持三种映射模式：

- `FileChannel.MapMode.READ_ONLY`：缓冲区是只读的。尝试写入缓冲区将抛出 `ReadOnlyBufferException`。
- `FileChannel.MapMode.WRITE`：缓冲区是可写的，更改会传播到文件。
- `FileChannel.MapMode.PRIVATE`：缓冲区是私有的，更改仅对缓冲区可见。

一旦拥有了缓冲区，就可以使用 `ByteBuffer` 类和 `Buffer` 超类读取和写入数据。缓冲区具有随 `get` 和 `put` 操作移动的位置。例如，你可以顺序遍历缓冲区的所有字节：

点击此处查看代码图片

```java
while (buffer.hasRemaining())
{
   byte b = buffer.get();
}
```

或者，你可以使用随机访问：

点击此处查看代码图片

```java
for (int i = 0; i < buffer.limit(); i++)
{
   byte. =.i(
}
```

你还可以通过以下方法读取和写入字节数组：

点击此处查看代码图片

```java
get(byte[] bytes)

((byte int int offset, int length)
```

`get` 方法用于读取以二进制值存储在文件中的原始类型值。正如我们已经提到的，Java 使用大端序二进制数据。然而，如果你需要处理包含小端序的文件，只需调用：

点击此处查看代码图片

```java
buffer.order(ByteOrder.LITTLE_ENDIAN);
```

要获取缓冲区当前的字节序，调用：

```java
ByteOrder b = buffer.order();
```

---

![图像](img/00004.jpeg) 注意

这对方法没有使用 `set/get` 命名规范。

---

向缓冲区写入数字，使用以下方法之一：

点击此处查看代码图片

```java
putInt

putLong

putShort

putChar

putFloat

putDouble
```

在某处，特别是当通道关闭时，这些更改会被写回文件。

列表 2.5 计算文件的 32 位循环冗余校验和（CRC32）。该校验和通常用于确定文件是否已损坏。文件的损坏很可能导致校验和改变。`java.util.zip` 包包含一个 `CRC32` 类，用于计算字节序列的校验和，使用以下循环：

点击此处查看代码图片

```java
CRC32 crc = new CRC32();

while (more bytes)
{
   crc.update(next byte);
}

long checksum = crc.getValue();
```

---

![图像](img/00002.jpeg) 备注

关于 CRC 算法的精彩解释，请参阅 `www.relisoft.com/Science/CrcMath.html`。

---

CRC 计算的细节并不重要。我们只是将其作为一个有用的文件操作的示例。（在实践中，你会一次读取并更新较大块的数据，而不是一个字节一个字节地。那样速度差异就不会那么显著了。）

按如下方式运行程序：

点击此处查看代码图片

```bash
java memoryMap.MemoryMapTest filename
```

**Listing 2.5** `memoryMap/MemoryMapTest.java`

点击此处查看代码图片

```java
package memoryMap;

import java.io.*;

import java.nio.*;

import java.nio.channels.*;

import java.nio.file.*;

import java.util.zip.*;

/**
 * 此程序通过四方式计算文件的 CRC 和。
 * 使用方法: java memoryMap.MemoryMapTest filename
 * @version 1.01 2012-05-30
 * @author Cay Horstmann
 */

public class MemoryMapTest
{
    public static long checksumInputStream(Path filename) throws IOException
    {
        try (InputStream in = Files.newInputStream(filename))
        {
            CRC32 crc = new CRC32();
            int c;
            while ((c = in.read()) != -1)
                crc.update(c);
            return crc.getValue();
        }
    }

    public static long checksumBufferedInputStream(Path filename) throws IOException
    {
        try (InputStream in = new BufferedInputStream(Files.newInputStream(filename)))
        {
            CRC32 crc = new CRC32();
            int c;
            while ((c = in.read()) != -1)
                crc.update(c);
            return crc.getValue();
        }
    }

    public static long checksumRandomAccessFile(Path filename) throws IOException
    {
        try (RandomAccessFile file = new RandomAccessFile(filename.toFile(), "r"))
        {
            long length = file.length();
            CRC32 crc = new CRC32();
            for (long p = 0; p < length; p++)
            {
                file.seek(p);
                int c = file.readByte();
                crc.update(c);
            }
            return crc.getValue();
        }
    }

    public static long checksumMappedFile(Path filename) throws IOException
    {
        try (FileChannel channel = FileChannel.open(filename))
        {
            CRC32 crc = new CRC32();
            int length = (int) channel.size();
            MappedByteBuffer buffer = channel.map(FileChannel.MapMode.READ_ONLY, 0, length);
            for (int p = 0; p < length; p++)
            {
                int c = buffer.get(p);
                crc.update(c);
            }
            return crc.getValue();
        }
    }

    public static void main(String[] args) throws IOException
    {
        System.out.println("Input Stream:");

        long start = System.currentTimeMillis();

        Path filename = Paths.get(args[0]);

        long crcValue = checksumInputStream(filename);

        long end = System.currentTimeMillis();

        System.out.println(Long.toHexString(crcValue));

        System.out.println((end - start) + "milliseconds");

        System.out.println("Buffered Input Stream:");

        start = System.currentTimeMillis();

        crcValue = checksumBufferedInputStream(filename);

        end = System.currentTimeMillis();

        System.out.println(Long.toHexString(crcValue));

        System.out.println((end - start) + " milliseconds");

        System.out.println("Random Access File:");

        start = System.currentTimeMillis();



```java
crcValue = checksumRandomAccessFile(filename);

end = System.currentTimeMillis();

System.out.println(Long.toHexString(crcValue));

System.out.println((end - start) + " milliseconds");

System.out.println("Mapped File:");

start = System.currentTimeMillis();

crcValue = checksumMappedFile(filename);

end = System.currentTimeMillis();

System.out.println(Long.toHexString(crcValue));

System.out.println((end - start) + " milliseconds");

}
}
```

### API 引用

- `java.io.FileInputStream`：`FileChannel getChannel()` 返回一个用于访问输入流的通道。
- `java.io.FileOutputStream`：`FileChannel getChannel()` 返回一个用于访问输出流的通道。
- `java.io.RandomAccessFile`：`FileChannel getChannel()` 返回一个用于访问文件的通道。
- `java.nio.channels.FileChannel`：`static FileChannel open(Path path, OpenOption... options)` 为给定路径打开文件通道。默认情况下通道以可读方式打开。`MappedByteBuffer map(FileChannel.MapMode mode, long position, long size)` 将文件的区域映射到内存。
- `java.nio.Buffer`：`boolean hasRemaining()` 如果当前缓冲区位置尚未到达限制（limit），则返回 `true`。`int limit()` 返回限制位置——即不再有可用值的第一个位置。
- `java.nio.ByteBuffer`：
  - `byte get()` 从当前位置获取一个字节并将当前位置移动到下一个字节。
  - `byte get(int index)` 从指定索引获取一个字节。
  - `ByteBuffer put(byte b)` 在当前位置放入一个字节并将当前位置移动到下一个字节。
  - `ByteBuffer put(int index, byte b)` 在指定索引放入一个字节。
  - `ByteBuffer get(byte[] destination)` 或 `ByteBuffer get(byte[] destination, int offset, int length)` 用缓冲区字节填充字节数组或字节数组区域，并将当前位置移动读取的字节数。如果缓冲区剩余字节不足，则抛出 `BufferUnderflowException`。
  - `ByteBuffer put(byte[] source)` 或 `ByteBuffer put(byte[] source, int offset, int length)` 将字节数组或字节数组区域的所有字节放入缓冲区，并将当前位置移动读取的字节数。如果缓冲区空间不足，则抛出 `BufferOverflowException`。
  - `Xxx` 代表 `get()` 和 `put()` 的原始类型。
  - `ByteBuffer order(ByteOrder order)` 和 `ByteOrder order()` 设置或获取字节序。`order` 的值为 `ByteOrder` 类常量 `BIG_ENDIAN` 或 `LITTLE_ENDIAN` 之一。
  - `static ByteBuffer allocate(int capacity)` 构建具有给定容量的缓冲区。
  - `static ByteBuffer wrap(byte[] values)` 构建由给定数组支持的缓冲区。
  - `CharBuffer asCharBuffer()` 构建由此缓冲区支持的字符缓冲区。对字符缓冲区的更改将反映在此缓冲区中，但字符缓冲区有自己的位置、限制和标记。
- `java.nio.CharBuffer`：
  - `char get()` 或 `CharBuffer get(char[] destination)` 或 `CharBuffer get(char[] destination, int offset, int length)` 获取一个 `char` 值或一系列 `char` 值，从缓冲区位置开始并移动位置通过已读取的字符。后两个方法返回 `this`。
  - `CharBuffer put(char c)` 放入一个 `char`。
  - `CharBuffer put(char[] source)`
  - `CharBuffer put(char[] source, int offset, int length)`
  - `CharBuffer put(String source)`
  - `CharBuffer put(CharBuffer source)`

放入一个 `char` 值或一个范围的 `char` 值，从缓冲区的位置（position）开始，并将位置移动到已写入字符之后。当从 `CharBuffer` 读取时，将读取所有剩余字符。所有方法均返回 `this`。

### 2.6.2 缓冲区数据结构

当你使用内存映射（memory mapping）时，你会创建一个跨越文件或你感兴趣的文件区域的缓冲区。你也可以使用缓冲区来读写更小规模的信息块。

在本节中，我们简要描述了 `Buffer` 对象的各种操作。缓冲区是相同类型值的数组。`Buffer` 类是一个抽象类，其具体的子类有：`ByteBuffer`、`CharBuffer`、`DoubleBuffer`、`FloatBuffer`、`IntBuffer`、`LongBuffer` 和 `ShortBuffer`。

![Image](img/00002.jpeg)

> 注意
>
> `StringBuffer` 类与这些缓冲区无关。

在实践中，你最常用的是 `ByteBuffer` 和 `CharBuffer`。如图 2.10 所示，缓冲区具有：

![Image](img/00047.jpeg)

**图 2.10** 缓冲区

- 一个永远不会的 `capacity`（容量）
- 用于读取或写入下一个值的 `position`（位置）
- 越后读写将没有意义的 `limit`（限制）
- 可选的，用于重复读写操作的 `mark`（标记）

这些值满足以下条件：

`0 = mark = position = limit = capacity`

缓冲区的主要目的是“先写后读”循环。在开始时，缓冲区的位置为 `0`，限制为容量。持续调用 `put` 向缓冲区添加值。当数据耗尽或达到容量时，就可以切换到读取模式了。

调用 `flip` 将 `limit` 设置为当前位置并将 `position` 设置为 `0`。现在继续调用 `get`，只要 `remaining` 方法（返回 `limit – position`）为正值。当你读完缓冲区中的所有值后，调用 `clear` 为下一个写入周期准备缓冲区。`clear` 方法将 `position` 重置为 `0` 并将 `limit` 重置为容量。

如果你想重新读取缓冲区，请使用 `rewind` 或 `mark/reset`（详情请参见 API 注释）。

要获取缓冲区，请调用静态方法如 `ByteBuffer.allocate` 或 `ByteBuffer.wrap`。

然后，你可以从通道（channel）填充缓冲区，或将其内容写入通道。例如：

点击此处查看代码图片

```java
ByteBuffer buffer = ByteBuffer.allocate(RECORD_SIZE);

channel.read(buffer);

channel.position(newpos);

buffer.flip();

channel.write(buffer);
```

这可以作为随机访问文件（random-access file）的一种有用替代方案。

#### `java.nio.Buffer` 1.4

- `Buffer clear()`

  通过将 `position` 设置为 `0` 并将 `limit` 设置为容量来为此缓冲区做好写入准备；返回 `this`。

- `Buffer flip()`

  在写入后通过将 `limit` 设置为 `position` 并将 `position` 设置为 `0` 为此缓冲区做好读取准备；返回 `this`。

- `Buffer rewind()`

  通过将 `position` 设置为 `0` 并保持 `limit` 不变，为重新读取相同值做好此缓冲区准备；返回 `this`。

- `Buffer mark()`

  将此缓冲区的 `mark` 设置为 `position`；返回 `this`。

- `Buffer reset()`

  将此缓冲区的 `position` 设置为 `mark`，从而允许再次读取或写入被标记的部分；返回 `this`。

- `int remaining()`

  返回剩余可读或可写值的数量——即 `limit` 与 `position` 之间的差值。

- `int position()`
- `void position(int newValue)`

  获取并设置此缓冲区的 `position`。

- `int capacity()`

  返回此缓冲区的容量。

### 2.6.3 文件锁

当多个同时执行的程序需要修改同一个文件时，它们需要以某种方式进行通信，否则文件很容易损坏。文件锁可以解决这个问题。文件锁控制对文件或文件内某个字节范围的访问。

假设你的应用程序保存了一个带有用户偏好设置的文件。如果用户调用了应用程序的两个实例，可能会出现它们都想同时写入配置文件的情况。在这种情况下，第一个实例应该锁定文件。当第二个实例发现文件被锁定时，它可以决定等待文件被解锁，或者简单地跳过写入过程。

要锁定文件，请调用 `FileChannel` 类的 `lock` 或 `tryLock` 方法。

点击此处查看代码图片

```java
FileChannel = FileChannel.open(path);

FileLock lock = channel.lock();
```

或者：

点击此处查看代码图片

```java
FileLock lock = channel.tryLock();
```

第一次调用会阻塞，直到锁可用。第二次调用会立即返回，返回锁对象或 `null`。

### 2.7 正则表达式

正则表达式用于指定字符串模式。每你需要定位匹配特定模式的字符串时，就可以使用正则表达式。例如，我们的一个示例程序通过查找模式为 `<a href=". . .">.` 的字符串来定位 HTML 文件中的所有超链接。

当然，在指定模式时，`. . .` 表示法并不精确。你需要使用特殊的语法来描述模式，并精确指定哪种字符序列是合法的匹配项。

这是一个简单的示例。正则表达式：

```text
[Jj]ava.+
```

匹配任何以下形式的字符串：

- 第一个字母是 `J` 或 `j`。
- 接下来的三个字母是 `ava`。
- 字符串的剩余部分由一个或多个任意字符组成。

例如，字符串 `"javanese"` 此特定的正则表达式，但字符串 `"Core Java"` 不匹配。

如你所见，你需要了解一些语法才能理解正则表达式的含义。幸运的是，对于大多数用途，几个简单的结构就足够了。

- `A*字符类` 是一组字符备选方案，括在方括号中，例如 `[Jj]`、`[0-9]`、`[A-Za-z]` 或 `[⁰-9]`。这里，`-` 表示范围（所有 Unicode 值落在两个边界之间的字符），`^` 表示取反（除指定字符以外的所有字符）。
- 要在字符类中包含 `-`，请将其放在第一个或最后一个项。要包含 `]`，请将其放在第一个项。要包含 `^`，将其放在开头以外任何位置。你只需要转义 `` 和 `\`。
- 有许多预定义的字符类，例如 `\d`（数字）或 `\p{Sc}`（Unicode 货币符号）。参见表 2.6 和 2.7。

![Image](img/00049.jpeg)![Image](img/00050.jpeg)![Image](img/00051.jpeg)

**表 2.6** 正则表达式语法

![Image](img/00052.jpeg)

**表 2.7** 配合 `\p` 使用的预定义字符类名称

- 大多数字符匹配其自身，例如前面示例中的 `ava` 字符。
- `.` 符号匹配任何字符（可能不包括行终止符，取决于标志设置）。
- 使用 `\` 作为转义字符。例如，`\.` 匹配点，`\\` 匹配反斜杠。
- `^` 和 `$` 分别匹配行的开头和结尾。
- 如果 `X` 和 `Y` 是正则表达式，那么 `XY` 意味着“任何 `X` 的匹配后跟着 `Y` 的匹配”。`X | Y` 意味着“任何 `X` 或 `Y` 的匹配”。
- 你可以对表达式 `X` 应用量符 `X+`（1 个或多个）、`X**`（0 个或多个）和 `X?`（0 或 1）。
- 默认情况下，量符匹配使整体匹配成功的最大重复次数。你可以通过后缀修改该行为：`?`（懒惰匹配，或吝啬匹配：匹配最小的重复次数）和 `+`（占有匹配，或贪婪匹配：即使这会导致整体匹配失败，也匹配最大的次数）。

例如，字符串 `cab` 匹配 `[a-z]*ab` 但不匹配 `[a-z]*+ab`。在第一情况下，表达式 `[a-z]*` 仅匹配字符 `c`，因此字符 `ab` 匹配模式的剩余部分。但贪婪版本的 `[a-z]*+` 匹配字符 `cab`，导致模式的剩余部分无法匹配。

- 你可以使用 `groups` 定义子表达式。将组括在 `( )` 中，例如 `([+-]?)([0-9]+)`。然后你可以要求匹配器返回每个组的匹配项，或通过 `*n` 引用组（其中 `n` 是组编号，从 `\1` 开始）。

例如，这里有一个相当复杂但潜在有用的正则表达式，描述十进制或十六进制整数：

```text
[+-]?[0-9]+|0[Xx][0-9A-Fa-f]+
```

遗憾的是，正则表达式语法在各种程序和库之间并没有完全标准；虽然基本结构有共识，但在细节上存在许多令人恼的差异。Java 正则表达式类使用的语法与 Perl 语言使用的语法相似但不完全相同。表 2.6 显示了 Java 语法的所有构造。关于正则表达式语法的更多信息，请参考 `Pattern` 类的 API 文档或 Jeffrey E. F. Friedl 的著作《Mastering Regular Expressions》（O’Reilly and Associates, 2006）。

正则表达式简单的用法是测试特定字符串是否匹配它。以下是在 Java 中编写该测试的方法。首先，从包含正则表达式的字符串构建 `Pattern` 对象。然后，从模式获取 `Matcher` 对象并调用其 `matches` 方法：

点击此处查看代码图片

```java
Pattern pattern = Pattern.compile(patternString);

Matcher matcher = pattern.matcher(input);

if (matcher.matches()) { ... }
```

匹配器的输入是实现 `CharSequence` 的任何类的对象，例如 `String`、`StringBuilder` 或 `CharBuffer`。在编译模式时，你可以设置一个或多个标志，例如：

点击此处查看代码图片

```java
Pattern pattern = Pattern.compile(patternString);

Pattern pattern = Pattern.compile(patternString, Pattern.CASE_INSENSITIVE + Pattern.UNICODE_CASE);
```

或者你可以在模式内部指定它们：

点击此处查看代码图片

```java
String regex = "(?i:expression)";
```

以下是这些标志：

- `Pattern.CASE_INSENSITIVE` 或 `i`：不区分大小写匹配字符。默认情况下，此标志仅考虑 ASCII 字符。
- `Pattern.UNICODE_CASE` 或 `u`：选择 Unicode 字符类而非 POSIX。意味着 `CASE_INSENSITIVE`。
- `Pattern.MULTILINE` 或 `m`：使 `^` 和 `$` 匹配行的开头和结尾，而不是整个输入。
- `Pattern.UNIX_LINES` 或 `d`：在匹配模式下，仅 `'\n'` 是行终止符。
- `Pattern.DOTALL` 或 `s`：使 `.` 符号匹配所有字符，包括终止符。
- `Pattern.COMMENTS` 或 `x`：忽略空白和注释（从 `#` 到行尾）。
- `Pattern.LITERAL`：模式被字面处理并必须精确匹配，除非考虑大小写。
- `Pattern.CANON_EQ`：考虑 Unicode 字符的规范等性。例如，`u` 后跟 `¨` 会匹配 `ü`。

最后两个标志无法在正则表达式内部指定。

如果你想匹配集合或流中的元素，将模式转换为谓词：

点击此处查看代码图片

```java
Stream<String> strings = ...;

Stream<String> result = strings.filter(pattern.asPredicate());
```

结果包含匹配正则表达式的所有字符串。

如果正则表达式包含组，`Matcher` 对象可以揭示组的边界。这些方法：

```java
int start(int groupIndex)

int end(int groupIndex)
```



产生特定组的起始索引和结束后的索引。

你可以通过调用`String group(int groupIndex)`直接提取匹配的字符串。

组 0 是整个输入；第一个实际组的组索引是 1。调用`groupCount`方法获取总数。对于命名组，使用这些方法：

点击此处查看代码图片

```java
int start(String groupName)
int end(String groupName)
String group(String groupName)
```

嵌套组根据左括号进行排序。例如，给定模式：

点击此处查看代码图片

```regex
(([1-9]|1[0-2]):([0-5][0-9]))[ap]m
```

以及输入：

```text
11:59am
```

匹配器报告以下组：

![Image](img/00053.jpeg)

[列表 2.6] 提示一个模式，然后是要匹配的字符串。它会输出输入是否匹配该模式。如果输入匹配且模式包含组，程序将以圆括号的形式打印组的边界，例如：

```text
((11):(59))am
```

**列表 2.6** `regex/RegexTest.java`

点击此处查看代码图片

```java
package regex;

import java.util.*;
import java.util.regex.*;

/**
 * 此程序测试正则表达式匹配。输入一个模式和要匹配的字符串，
 * 或按取消退出。如果模式包含组，则会在匹配结果中显示
 * 的边界。
 * @version 1.02 2012-06-02
 * @author Cay Horstmann
 */

public class RegexTest
{
    public static void main(String[] args) throws PatternSyntaxException
    {
        Scanner in = new Scanner(System.in);

        System.out.println("Enter pattern: ");
        String patternString = in.nextLine();
        Pattern pattern = Pattern.compile(patternString);

        while (true)
        {
            System.out.println("Enter string to match: ");
            String input = in.nextLine();

            if (input == null || input.equals("")) return;

            Matcher matcher = pattern.matcher(input);

            if (matcher.matches())
            {
                System.out.println("Match ");

                int g = matcher.groupCount();

                if (g > 0)
                {
                    for (int i = 0; i < input.length(); i++)
                    {
                        // Print any empty groups
                        for (int j = 1; j <= g; j++)
                            if (i == matcher.start(j) && i == matcher.end(j))
                                System.out.print("()");

                        // Print 从此处开始的非空组
                        for (int j = 1; j <= g; j++)
                            if (i == matcher.start(j) && i != matcher.end(j))
                            {
                                System.out.print('(');
                                System.out.print(input.charAt(i));
                            }

                        // Print 从此处结束的非空组的 )
                        for (int j = 1; j <= g; j++)
                            if (i + 1 != matcher.start(j) && i + 1 == matcher.end(j))
                                System.out.print(')');
                    }

                    System.out.println();
                }
            }
            else
                System.out.println("No match");
        }
    }
}
```

通常，你不想让整个输入与正则表达式匹配，而是要在输入中找到一个或多个匹配子字符串。使用`Matcher`类的`find`方法来查找下一个匹配。如果它返回`true`，使用`start`和`end`方法找到匹配的范围，或者使用不带参数的`group`方法获取匹配的字符串。

```java
while (matcher.find())
{
    int start = matcher.start();
    int end = matcher.end();
    String match = input.group();
    ...
}
```

[列表 2.7] 使用了这一机制。它定位网页中所有的超文本引用并打印它们。要运行该程序，请在命令行提供一个 URL，例如：

```bash
java match.HrefMatch http://horstmann.com
```

**列表 2.7** `match/HrefMatch.java`

```java
package match;

import java.io.*;
import java.net.*;
import java.nio.charset.*;
import java.util.regex.*;

/**
 * 此程序通过匹配描述 <a href...> 标签的正则表达式
 * 显示网页中所有的 URL。以如下方式启动程序：
 * java match.HrefMatch URL
 * @version 1.02 2016-07-4
 * @author Cay Horstmann
 */

public class HrefMatch
{
    public static void main(String[] args)
    {
        try
        {
            // 从命令行获取字符串或使用默认值
            String urlString;

            if (args.length > 0)
                urlString = args[0];
            else
                urlString = "http://java.sun.com";

            // 打开 URL 的读取器
            InputStreamReader in = new InputStreamReader(
                new URL(urlString).openStream(),
                StandardCharsets.UTF_8);

            // 将内容读入器
            StringBuilder input = new StringBuilder();
            int ch;

            while ((ch = in.read()) != -1)
                input.append((char) ch);

            // 搜索模式的所有出现处
            String patternString = "<a\\s+href\\s*=\\s*(\"["]*|[^\\s>]*)\\s*>";
            Pattern pattern = Pattern.compile(
                patternString,
                Pattern.CASE_INSENSITIVE);

            Matcher matcher = pattern.matcher(input);

            while (matcher.find())
            {
                String match = matcher.group();
                System.out.println(match);
            }
        }
        catch (IOException | PatternSyntaxException e)
        {
            e.printStackTrace();
        }
    }
}
```

`Matcher`类的`replaceAll`方法将正则表达式的所有出现处替换为替换字符串。例如，以下指令将所有数字序列替换为`#`字符：

```java
Pattern pattern = Pattern.compile("[0-9]+");

Matcher matcher = pattern.matcher(input);
String output = matcher.replaceAll("#");
```

替换字符串可以包含对模式组的引用：`$n`被替换为第 n 组，`${name}`被替换为指定名称组。使用`\$`在替换文本中包含`$`字符。如果你有一个可能包含`$`和`\`的字符串且不希望它们被解释为组替换，请调用`matcher.replaceAll(Matcher.quoteReplacement(str))`。

`replaceFirst`方法只替换第一次出现处。

最后，`Pattern`类有一个`split`方法，可以将输入分割为字符串数组，使用正则表达式匹配作为边界。例如，以下指令将输入分割为标记，分隔符是带有可选空格的标点符号：

```java
Pattern pattern = Pattern.compile("\\s*\\p{Punct}\\s*");

String[] tokens = pattern.split(input);
```

如果有很多标记，可以懒性地获取：

```java
Stream<String> tokens = commas.splitAsStream(input);
```

将输入字符串拆分为标记（tokens），其中模式指定了分隔符的形式。返回标记的数组或流。分隔符不是标记的一部分。

![Image](img/00055.jpeg)

`java.util.regex.Matcher` `1.4`

- `boolean matches()`

  如果输入匹配模式，则返回`true`。

- `boolean lookingAt()`

  如果输入的开头匹配模式，则返回`true`。

- `boolean find()`
- `boolean find(int start)`

  尝试查找下一个匹配项，如果找到了另一个匹配，则返回`true`。

![Image](img/00056.jpeg)

- `int start()`
- `int end()`

  返回当前匹配的起始位置或结束后的位置。

- `String group()`

  返回当前匹配项。

- `int groupCount()`

  返回输入模式中的组数。

- `int start(int groupIndex)`
- `int end(int groupIndex)`

  返回当前匹配中给定组的起始位置或结束后的位置。

![Image](img/00057.jpeg)

- `String group(int groupIndex)`

  返回匹配给定组的字符串。

![Image](img/00058.jpeg)

- `String replaceAll(String replacement)`
- `String replaceFirst(String replacement)`

  返回从匹配器输入通过将所有匹配项（或第一个匹配项）替换为替换字符串得到的字符串。

![Image](img/00059.jpeg)

- `static String quoteReplacement(String str)` `5.0`

  对`str`中所有的`\`和`$`进行转义。

- `Matcher reset()`
- `Matcher reset(CharSequence input)`

  重置匹配器状态。第二个方法使匹配器在不同的输入上工作。这两个方法都返回此。

你现在已经了解如何在 Java 中执行输入输出操作，并对作为“新 I/O”规范部分的正则表达式包有了概述。在下一章，我们将转向 XML 数据的处理。

## 第 3 章：XML

### 本章内容

- 3.1 介绍 XML
- 3.2 解析 XML 文档
- 3.3 验证 XML 文档
- 3.4 使用 XPath 定位信息
- 3.5 使用命名空间
- 3.6 流式解析器
- 3.7 生成 XML 文档
- 3.8 XSL 变换

Don Box 等人编写的《Essential XML》（Addison-Wesley, 2000）序言中半开玩笑地写道：“可扩展标记语言（XML）已经取代 Java、设计模式和对象技术，成为软件行业解决全球饥饿的方案。”事实上，正如你在本章看到的，XML 是一种描述结构化信息的非常有用的技术。XML 工具可以轻松处理和转换这些信息。

然而，XML 并不是万灵药。你需要特定领域的标准和代码库来有效地使用它。此外，XML 远没有让 Java 过时，它与 Java 配合得非常好。自 20 世纪 90 年代后期以来，IBM、Apache 等在生产高质量的 XML 处理 Java 库方面发挥了重要作用。许多库现在已集成到 Java 平台中。

本章介绍了 XML 并涵盖了 Java 库中的 XML 特性。一如既往，我们会在过程中指出何时围绕 XML 的炒作是合理的——何时你必须对其保留意见，并尝试通过传统方法通过良好的设计和代码来解决问题。

### 3.1 介绍 XML

在第一卷的第 13 章中，你已经见过使用*属性文件*（property files）来描述程序的配置。属性文件包含一组键/值对，例如：

```properties
fontname=Times Roman
fontsize=12
windowsize=400 200
color=0 50 100
```

你可以使用`Properties`类通过单个方法调用来读取此类文件。这是一个很棒的功能，但它真的还不够。在许多情况下，你想要描述的信息比属性文件格式能够舒适处理的具有更多结构。考虑示例中的`fontname/fontsize`条目。如果有一个单一条目会更符合面向对象：

```properties
font=Times Roman 12
```

但这样解析字体描述就会变得糟糕，因为你必须弄清楚字体名称何时结束，字体大小何时开始。

属性文件具有单一的扁平层次结构。你经常看到程序员通过键/值对来绕过这个限制。

- 在 HTML 中，你可以拥有没有值的属性名，例如`<input type="radio" name="language" value="Java" checked>`。在 XML 中，所有属性必须有值，例如`checked="true"`或（哎呀）`checked="checked"`。

#### 3.1.1 XML 文档的结构

XML 文档应该以头部开始，例如：

```xml
<?xml version="1.0"?>
```

或者：

```xml
<?xml version="1.0" encoding="UTF-8"?>
```

严格来说，头部是可选的，但强烈建议使用。

> **备注**
>
> 由于 SGML 是为了处理真实文档而创建的，XML 文件被称为*文档*（documents），尽管其中许多文件描述的是人们通常不会称为文档的数据集。

头部之后可以跟一个*文档类型定义*（DTD），例如：

```xml
<!DOCTYPE web-app PUBLIC
   "-//Sun Microsystems, Inc.//DTD Web Application 2.2//EN"
   "http://java.sun.com/j2ee/dtds/web-app_2_2.dtd">
```




DTDs 是确保文档正确性的重要机制，但不是强制要求的。我们将在本章后面部分讨论它们。

最后，XML 文档的主体包含*根元素*（root element），它包含其他元素。例如：

```xml
<?xml version="1.0"?>

<!DOCTYPE configuration . . .>

<configuration>
   <title>
      <font>
         <name>Helvetica</name>
         <size>36</size>
      </font>
   </title>
   . . .
</configuration>
```

元素可以包含*子元素*、文本或两者兼有。在前面的示例中，`font` 元素有两个子元素，`name` 和 `size`。`name` 元素包含了文本 `"Helvetica"`。

---

![Image](img/00003.jpeg) 提示

最好构造你的 XML 文档，使得元素*要么*包含子元素*要么*包含文本。换句话说，你应该避免出现所示的情况：

```xml
<font>
   Helvetica
   <size>36</size>
</font>
```

这在 XML 规范中被称为*混合内容*（mixed content）。正如你将在本章后面看到的，如果你避免混合内容，就可以简化解析过程。

---

XML 元素可以包含属性，例如：

```xml
<size unit="pt">36</size>
```

XML 设计者之间对于何时使用元素以及何时使用属性存在一些分歧。例如，描述一个字体似乎比：

```xml
<font name="Helvetica" size="36"/>
```

比：

```xml
<font>
   <name> Helvetica</name>
   <size>36</size>
</font>
```

更容易。

然而，属性的活性小得多。假设你想为大小值添加单位。如果你使用属性，你将不得不将单位添加到属性值中：

```xml
<font name="Helvetica" size="36 pt"/>
```

哎呀！现在你必须解析字符串 `"36 pt"`，这正是 XML 设计旨在避免的此类麻烦。在 `size` 元素上添加属性要干净得多：

```xml
<font>
   <name>Helvetica</name>
   <size unit="pt">36</size>
</font>
```

一个常用的经验法则是，属性应仅用于修改对值的解释，而不是指定值。如果你发现自己陷入了关于某个特定设置是否为对值解释的修改形上学讨论，只需对属性说“不”，并贯穿使用元素。许多实用的 XML 文档根本不使用属性。

---

![Image](img/00002.jpeg) 备注

在 HTML 中，属性的使用规则非常简单：如果它没有在网页上显示，它就是属性。例如，考虑超链接：

```html
<a href="http://java.sun.com/Java Technology</a>
```

字符串 `Java Technology` 显示在页面上，但 URL 没有。

由于 SGML 是为了处理真实文档而创建的，XML 文件被称为*文档*，尽管其中许多文件描述的是人们通常不会称为文档的数据集。

---

头部之后可以跟一个*文档类型定义*（DTD），例如：

```xml
<!DOCTYPE web-app PUBLIC
   "-//Sun Microsystems, Inc.//DTD Web Application 2.2//EN"
   "http://java.sun.com/j2ee/dtds/web-app_2_2.dtd">
```

DTDs 是确保文档正确性的重要机制，但不是强制要求的。我们将在本章后面讨论它们。

最后，XML 文档的主体包含*根元素*，它可以包含其他元素。例如：

```xml
<?xml version="1.0"?>

<!DOCTYPE configuration . . .>

<configuration>
   <title>
      <font>
         <name>Helvetica</name>
         <size>36</size>
      </font>
   </title>
   . . .
</configuration>
```

元素可以包含*子元素*、文本或两者兼有。在前面的示例中，`font` 元素有两个子元素，`name` 和 `size`。`name` 元素包含了文本 `"Helvetica"`。

---

最好构造你的 XML 文档，使得元素*要么*包含子元素*要么*包含文本。换句话说，你应该避免出现所示的情况：

```xml
<font>
   Helvetica
   <size>36</size>
</font>
```

这在 XML 规范中被称为*混合内容*。正如你将在本章后面看到的，如果你避免混合内容，就可以简化解析过程。

---

XML 元素可以包含属性，例如：

```xml
<size unit="pt">36</size>
```

XML 设计者之间对于何时使用元素以及何时使用属性存在一些分歧。例如，描述一个字体似乎比：

```xml
<font name="Helvetica" size="36"/>
```

比：

```xml
<font>
   <name> Helvetica</name>
   <size>36</size>
</font>
```

然而，属性的活性小得多。假设你想为大小值添加单位。如果你使用属性，你将不得不将单位添加到属性值中：

```xml
<font name="Helvetica" size="36 pt"/>
```

哎呀！现在你必须解析字符串 `"36 pt"`，这正是 XML 设计旨在避免的此类麻烦。在 `size` 元素上添加属性要干净得多：

```xml
<font>
   <name>Helvetica</name>
   <size unit="pt">36</size>
</font>
```

一个常用的经验法则是，属性应仅用于修改对值的解释，而不是指定值。如果你发现自己陷入了关于某个特定设置是否为对值解释的修改形上学讨论，只需对属性说“不”，并贯穿使用元素。许多实用的 XML 文档根本不使用属性。

---

在 HTML 中，属性的使用规则非常简单：如果它没有在网页上显示，它就是属性。例如，考虑超链接：

```html
<a href="http://java.sun.com/Java Technology</a>
```

字符串 `Java Technology` 显示在页面上，但 URL 没有。

由于 SGML 是为了处理真实文档而创建的，XML 文件被称为*文档*，尽管其中许多文件描述的是人们通常不会称为文档的数据集。

---

头部之后可以跟一个*文档类型定义*（DTD），例如：

```xml
<!DOCTYPE web-app PUBLIC
   "-//Sun Microsystems, Inc.//DTD Web Application 2.2//EN"
   "http://java.sun.com/j2ee/dtds/web-app_2_2.dtd">
```

DTDs 是确保文档正确性的重要机制，但不是强制要求的。我们将在本章后面讨论它们。

最后，XML 文档的主体包含*根元素*，它可以包含其他元素。例如：

```xml
<?xml version="1.0"?>

<!DOCTYPE configuration . . .>

<configuration>
   <title>
      <font>
         <name>Helvetica</name>
         <size>36</size>
      </font>
   </title>
   . . .
</configuration>
```

元素可以包含*子元素*、文本或两者兼有。在前面的示例中，`font` 元素有两个子元素，`name` 和 `size`。`name` 元素包含了文本 `"Helvetica"`。

---

最好构造你的 XML 文档，使得元素*要么*包含子元素*要么*包含文本。换句话说，你应该避免出现所示的情况：

```xml
<font>
   Helvetica
   <size>36</size>
</font>
```

这在 XML 规范中被称为*混合内容*。正如你将在本章后面看到的，如果你避免混合内容，就可以简化解析过程。

---

XML 元素可以包含属性，例如：

```xml
<size unit="pt">36</size>
```

XML 设计者之间对于何时使用元素以及何时使用属性存在一些分歧。例如，描述一个字体似乎比：

```xml
<font name="Helvetica" size="36"/>
```

比：

```xml
<font>
   <name> Helvetica</name>
   <size>36</size>
</font>
```

然而，属性的活性小得多。假设你想为大小值添加单位。如果你使用属性，你将不得不将单位添加到属性值中：

```xml
<font name="Helvetica" size="36 pt"/>
```

哎呀！现在你必须解析字符串 `"36 pt"`，这正是 XML 设计旨在避免的此类麻烦。在 `size` 元素上添加属性要干净得多：

```xml
<font>
   <name>Helvetica</name>
   <size unit="pt">36</size>
</font>
```

一个常用的经验法则是，属性应仅用于修改对值的解释，而不是指定值。如果你发现自己陷入了关于某个特定设置是否为对值解释的修改形上学讨论，只需对属性说“不”，并贯穿使用元素。许多实用的 XML 文档根本不使用属性。

### 3.2 解析 XML 文档

要处理一个 XML 文档，你需要对其进行*解析*。解析器是一个读取文件、确认其格式正确、将其拆分为组成元素并允许程序员访问这些元素的程序。Java 库提供了两种解析器：

- 树解析器，例如文档对象模型（DOM）解析器，它将 XML 文档读入树结构。
- 流式解析器，例如 XML 简单 API（SAX）解析器，它在读取 XML 文档时生成事件。

大多数情况下，DOM 解析器更容易使用，我们首先解释它。如果你处理的文档非常导致树结构占用大量内存，或者你只对少数元素感兴趣而不关心它们的上下文，你可以考虑使用流式解析器。更多信息请参见第 3.6 节，“流式解析器”第 199 页。

DOM 解析器接口由万维网联盟（W3C）标准化。`org.w3c.dom` 包包含了 `Document` 和 `Element` 等接口类型的定义。不同的供应商（如 Apache 组织和 IBM）编写了实现这些接口的 DOM 解析器类。Java XML 处理 API（JAXP）库实际上使得接入任何这些解析器成为可能。但 JDK 也附带了一个源自 Apache 解析器的 DOM 解析器。

要读取 XML 文档，你需要从 `DocumentBuilderFactory` 获取一个 `DocumentBuilder` 对象：

```java
DocumentBuilderFactory factory = DocumentBuilderFactory.newInstance();

DocumentBuilder builder = factory.newDocumentBuilder();
```

现在你可以从文件读取文档：

```java
File f = . . .

Document doc = builder.parse(f);
```

或者，你也可以使用 URL：

```java
URL u = . . .

Document doc = builder.parse(u);
```

你甚至可以指定任意输入流：

```java
InputStream in = . . .

Document doc = builder.parse(in);
```

---

![Image](img/00002.jpeg) 事项

如果你使用 `InputStream` 作为输入源，`parser` 将无法定位相对于 `document` 所在引用的其他文件，例如同一目录下的 `DTD`。你可以安装一个“实体解析器”（entity resolver）来解决这个问题。更多信息，请参阅 `www.xml.com/pub/a/2004/03/03/catalogs.html` 或 `www.ibm.com/developerworks/xml/library/x-mxd3.html`。

`Document` 对象是 `XML` 文档树结构的内存中的表示。它由实现 `Node` 接口及其各种子接口的类对象组成。图 3.1 显示了子接口的继承层次结构。

![Image](img/00060.jpeg)

**图 3.1** `Node` 接口及其子接口

通过调用 `getDocumentElement` 方法开始分析文档内容。它返回根元素。

```java
Element root = doc.getDocumentElement();
```

例如，如果你正在处理一个文档：

```xml
<?xml version="1.0"?>

<font>
   . . .
</font>
```

那么调用 `getDocumentElement` 就会返回 `font` 元素。

`getTagName` 方法返回元素的标签名。在前面的示例中，`root.getTagName()` 返回字符串 `"font"`。

要获取元素的子节点（可能是子元素、文本、注释或其他节点），请使用 `getChildNodes` 方法。该方法返回一个类型为 `NodeList` 的集合。该类型在标准 Java 集合之前就已经标准化了，因此它有不同的访问协议。`item` 方法根据给定索引获取项目，`getLength` 方法给出项目的总数。因此，你可以像这样枚举所有子节点：

```java
NodeList children = root.getChildNodes();

for (int i = 0; i < children.getLength(); i++)
{
   Node child = children.item(i);
   . . .
}
```

在分析子节点时要小心。例如，假设你正在处理文档：

```xml
<font>
   <name>Helvetica</name>
   <size>36</size>
</font>
```

你可能期望 `font` 元素有两个子节点，但解析器报告了五个：

- `<font>` 和 `<name>` 之间的空白字符
- `name` 元素
- `</name>` 和 `<size>` 之间的空白字符
- `size` 元素
- `</size>` 和 `</font>` 之间的空白字符

图 3.2 显示了 DOM 树。

![Image](img/00061.jpeg)

**图 3.2** 一个简单的 DOM 树

如果你只需要子元素，可以忽略空白字符：

```java
for (int i = 0; i < children.getLength(); i++)
{
   Node child = children.item(i);
   if (child instanceof Element)
   {
      Element childElement = (Element) child;
      . . .
   }
}
```

现在你只看两个标签名为 `name` 和 `size` 的元素。正如你将在下一节中看到的，如果你的文档有 DTD，你可以做得更好。这时解析器就知道哪些元素没有文本节点作为子节点，它可以为你过滤掉空白字符。在分析 `name` 和 `size` 元素时，你想检索它们包含的文本字符串。这些文本字符串本身包含在类型为 `Text` 的子节点中。你知道这些 `Text` 节点是唯一的子节点，因此你可以使用 `getFirstChild` 方法而不需要遍历另一个 `NodeList`。然后，使用 `getData` 方法检索存储在 `Text` 节点中的字符串。

以下代码展示了遍历子节点的基本结构：

```java
for (int i = 0; i < children.getLength(); i++)
{
   Node child = children.item(i);
   if (child instanceof Element)
   {
      Element childElement = (Element) child;
      . . .
   }
}
```




```java
Text textNode = (Text) childElement.getFirstChild();

String text = textNode.getData();

if (childElement.getTagName().equals("name"))

    name = text;

else if (childElement.getTagName().equals("size"))

    size = Integer.parseInt(text);
```

实际上，查看所提供的：

---

![Image](img/00003.jpeg) 提示

建议对`getData`的返回值调用`trim`。

---

你还可以使用`getLastChild`获取最后一个孩子，并使用`getNextSibling`获取节点的下一个兄弟。因此，遍历子节点的另一种方式是：

```java
Node childNode = element.getFirstChild();

while (childNode != null)

{

    ...

    childNode = childNode.getNextSibling();

}
```

或者，如果你知道属性名称，可以直接检索对应的值：

```java
String unit = element.getAttribute("unit");
```

你现在已经了解如何分析 DOM 树。列表 3.1](#part0008_split_000.html_ch03list01) 将这些技术付诸实践。你可以使用 `File → Open` 菜单读取 XML 文件。`DocumentBuilder` 对象解析文件并产生 `Document` 对象。程序将 `Document` 对象作为树显示（见图 3.3](#part0008_split_000.html_ch03fig03)）。

![Image](img/00062.jpeg)

**图 3.3** XML 文档的解析树

树显示清晰展示子元素是如何被包含在空白文本中的。为了更清晰，程序将换行符和返回符替换为 `\n` 和 `\r`。

在第 10 章中，你将学习该程序用于显示树和属性表的技术。`DOMTreeModel` 类实现了 `TreeModel` 接口。`getRoot` 方法返回文档的根元素。`getChild` 方法获取节点列表并返回请求索引的项目。树单元渲染器显示以下内容：

- 对于元素，显示元素标签名和所有属性表格。
- 对于字符数据，显示接口（`Text`、`Comment` 或 `CDATASection`），随后是数据，换行符和返回符替换为 `\n` 和 `\r`。
- 对于所有其他节点类型，显示类名后跟 `toString` 的结果。

**列表 3.1** `dom/TreeViewer.java`

点击此处查看代码图像。

---

```java
package dom;

import java.awt.*;
import java.io.*;
```

```java
import javax.swing.*;
import javax.swing.event.*;
import javax.swing.table.*;
import javax.swing.tree.*;
import javax.xml.parsers.*;
import org.w3c.dom.*;
import org.w3c.dom.CharacterData;

/**
 * 此程序以树的形式显示 XML 文档。
 * @version 1.13 2016-04-27
 * @author Cay Horstmann
 */
public class TreeViewer
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() ->
            {
                JFrame frame = new DOMTreeFrame();
                frame.setTitle("TreeViewer");
                frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
                frame.setVisible(true);
            });
    }
}

/**
 * 此框架包含一个用于显示 XML 文档内容的树。
 */
class DOMTreeFrame extends JFrame
{
    private static final int DEFAULT_WIDTH = 400;
    private static final int DEFAULT_HEIGHT = 400;
    private DocumentBuilder builder;

    public DOMTreeFrame()
    {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

        JMenu fileMenu = new JMenu("File");
        JMenuItem openItem = new JMenuItem("Open");
        openItem.addActionListener(event -> openFile());
        fileMenu.add(openItem);

        JMenuItem exitItem = new JMenuItem("Exit");
        exitItem.addActionListener(event -> System.exit(0));
        fileMenu.add(exitItem);

        JMenuBar menuBar = new JMenuBar();
        menuBar.add(fileMenu);
        setJMenuBar(menuBar);
    }

    /**
     * 打开文件并加载文档。
     */
    public void openFile()
    {
        JFileChooser chooser = new JFileChooser();
        chooser.setCurrentDirectory(new File("dom"));
        chooser.setFileFilter(new javax.swing.filechooser.FileNameFilter("XML files", "xml"));

        int r = chooser.showDialog(this);
        if (r != JFileChooser.APPROVE_OPTION) return;

        final File = chooser.getSelectedFile();

        new SwingWorker<Document, Void>()
        {
            protected Document doInBackground() throws Exception
            {
                if (builder == null)
                {
                    DocumentBuilderFactory factory = DocumentBuilderFactory.newInstance();
                    builder = factory.newDocumentBuilder();
                }

                return builder.parse(file);
            }

            protected void done()
            {
                try
                {
                    Document doc = get();
                    JTree tree = new JTree(new DOMTreeModel(doc));
                    tree.setCellRenderer(new DOMTreeCellRenderer());
                    setContentPane(new JScrollPane(tree));
                    validate();
                }
                catch (Exception e)
                {
                    JOptionPane.showMessageDialog(DOMTreeFrame.this, e);
                }
            }
        }.execute();
    }
}

/**
 * 此树模型描述了 XML 文档的结构。
 */
class DOMTreeModel implements TreeModel
{
    private Document doc;

    /**
     * 构造一个文档模型。
     * @param doc 文
     */
    public DOMTreeModel(Document doc)
    {
        this.doc = doc;
    }

    public Object Root()
    {
        return doc.getDocumentElement();
    }

    public int getChildCount(Object parent)
    {
        Node node = (Node) parent;
        NodeList list = node.getChildNodes();
        return list.getLength();
    }

    public Object getChild(Object parent, int index)
    {
        Node node = (Node) parent;
        NodeList list = node.getChildNodes();
        return list.item(index);
    }

    public int getIndexOfChild(Object parent, Object child)
    {
        Node node = (Node) parent;
        NodeList list = node.getChildNodes();

        for (int i = 0; i < list.getLength(); i++)
            if (getChild(node, i) == child) return i;

        return -1;
    }

    public boolean isLeaf(Object node)
    {
        return getChildCount(node) == 0;
    }

    public void valueForPathChanged(TreePath path, Object newValue) {}

    public void addTreeModelListener(TreeModelListener l) {}

    public void removeTreeModelListener(TreeModelListener l) {}
}

/**
 * 此类渲染 XML 节点。
 */
class DOMTreeCellRenderer extends DefaultTreeCellRenderer
{
    public Component getTreeCellRendererComponent(
        JTree tree,
        Object value,
        boolean selected,
        boolean expanded,
        boolean leaf,
        int row,
        boolean hasFocus)
    {
        Node node = (Node) value;

        if (node instanceof Element)
            return elementPanel((Element) node);

        super.getCellRendererComponent(tree, value, expanded, leaf, row, hasFocus);

        if (node instanceof CharacterData)
            setText(characterString((CharacterData) node));
        else
            setText(node.getClass() + ": " + node.toString());

        return this;
    }

    public static JPanel elementPanel(Element e)
    {
        JPanel panel = new JPanel();
        panel.add(new JLabel("Element: " + e.getTagName()));

        final NamedNodeMap map = e.getAttributes();

        panel.add(new JTable(new AbstractTableModel()
        {
            public int getRowCount()
            {
                return map.getLength();
            }

            public int getColumnCount()
            {
                return 2;
            }

            public Object getValueAt(int r, int c)
            {
                return c == 0
                    ? map.item(r).getNodeName()
                    : map.item(r).getNodeValue();
            }
        }));

        return panel;
    }

    private static String characterString(CharacterData node)
    {
        StringBuilder builder = new StringBuilder(node.getData());

        for (int i = 0; i < builder.length(); i++)
        {
            if (builder.charAt(i) == '\r')
            {
                builder.replace(i, i + 1, "\\r");
                i++;
            }
            else if (builder.charAt(i) == '\n')
            {
                builder.replace(i, i + 1, "\\n");
                i++;
            }
            else if (builder.charAt(i) == '\t')
            {
                builder.replace(i, i + 1, "\\t");
                i++;
            }
        }

        if (node instanceof CDATASection)
            builder.insert(0, "CDATASection: ");
        else if (node instanceof Text)
            builder.insert(0, "Text: ");
        else if (node instanceof Comment)
            builder.insert(0, "Comment: ");

        return builder.toString();
    }
}
```



# `org.w3c.dom.Document` 1.4

- `Element getDocumentElement()`

  返回文档的根元素。

## `org.w3c.dom.Element` 1.4

- `String getTagName()`

  返回元素的名称。

- `String getAttribute(String name)`

  返回给定名称属性的值，如果不存在该属性则返回空字符串。

## `org.w3c.dom.Node` 1.4

- `NodeList getChildNodes()`

  返回一个包含此节点所有子节点的列表。

- `Node getFirstChild()`
- `Node getLastChild()`

  获取此节点的第一个或最后一个子节点，如果该节点没有子节点则返回 `null`。

- `Node getNextSibling()`
- `Node getPreviousSibling()`

  获取此节点的下一个或上一个兄弟节点，如果该节点没有兄弟节点则返回 `null`。

- `Node getParentNode()`

  获取此节点的父节点，如果该节点是文档节点则返回 `null`。

- `NamedNodeMap getAttributes()`

  返回一个包含 `Attr` 节点的节点映射，这些节点描述了该节点的所有属性。

- `String getNodeName()`

  返回此节点的名称。如果节点是 `Attr` 节点，则名称为属性名称。

- `String getNodeValue()`

  返回此节点的值。如果节点是 `Attr` 节点，则值为属性属性的值。

## `org.w3c.dom.CharacterData` 1.4

- `String getData()`

  返回存储在此节点中的文本。

## `org.w3c.dom.NodeList` 1.4

- `int getLength()`

  返回此列表中的节点数量。

- `Node item(int index)`

  返回给定索引的节点。索引范围在 `0` 到 `getLength() - 1` 之间。

## `org.w3c.dom.NamedNodeMap` 1.4

- `int getLength()`

  返回映射中的节点数量。

- `Node item(int index)`

  返回给定索引的节点。索引范围在 `0` 到 `getLength() - 1` 之间。

# 3.3 验证 XML 文档

在上一节中，你已经了解了如何遍历 DOM 文档的树形结构。然而，如果你简单地遵循那种方法，你将不得不进行大量繁琐的编程和错误检查。你不仅需要处理元素之间的空白字符，还需要检查文档是否包含了你预期的节点。

例如，假设你正在读取一个元素：

```xml
<font>
    <name>Helvetica</name>
    <size>36</size>
</font>
```

你获取了第一个子节点。哎……它是一个包含空白字符 `"\n` 的文本节点。你跳过了文本节点并找到了第一个元素节点。然后，你需要检查它的标签名称是否为 `"name"`，以及它是否包含一个类型为 `Text` 的子节点。你移动到下一个非空白子节点并进行相同的检查。

如果文档的作者交换了子节点的顺序或者添加了另一个子元素会怎样？编写所有这些错误检查的代码是繁琐的——但跳过检查是轻率的。

幸运的是，XML 解析器的主要优点之一是它可以自动验证文档是否具有正确的结构。这样，解析过程就会变得简单得多。例如，如果你知道 `font` 片段已经通过了验证，你只需获取两个孙子节点，将它们强制转换为 `Text` 节点并获取文本数据，而无需任何进一步的检查。

要指定文档结构，你可以提供 DTD 或 XML Schema 定义。DTD 或 schema 包含了规则，解释了文档应该如何形成，通过指定每个元素合法的子元素和属性。

例如，DTD 可能会包含如下规则：

```xml
<!ELEMENT font (name,size)>
```

该规则表示 `font` 元素必须始终有两个子元素，即 `name` 和 `size` 元素。XML Schema 语言以以下方式表达相同的约束：

```xml
<xsd:element name="font">
    <xsd:sequence>
        <xsd:element name="name" type="xsd:string"/>
        <xsd:element name="size" type="xsd:int"/>
    </xsd:sequence>
</xsd:element>
```

XML Schema 比 DTD 能够表达更复杂的验证条件，例如 `size` 元素必须包含整数。与 DTD 语法不同，XML Schema 语法本身使用 XML，这在需要处理 schema 文件时是一个优势。

在接下来的节中，我们将详细讨论 DTD，然后简要介绍 XML Schema 支持的基础知识。最后，我们将展示一个完整的应用程序，演示验证如何简化 XML 编程。

## 3.3.1 文档类型定义

提供 DTD 有几种方法。你可以像如下所示在 XML 文档中包含 DTD：

```xml
<?xml version="1.0"?>

<!DOCTYPE configuration [
    <!ELEMENT configuration (any*)>
]>

<configuration>
</configuration>
```

如你所示，规则包含在 `DOCTYPE` 块中。文档类型必须与根元素的名称匹配。

在 XML 文档内部提供 DTD 并不常见，因为 DTD 可能会变得很大。将 DTD 存储在外部更有意义。可以使用 `SYSTEM` 声明来实现这一点：

```xml
<!DOCTYPE configuration SYSTEM "config.dtd">
```

如果你为 DTD 使用相对 URL，例如 `config.dtd`，请给解析器提供一个 `File` 或 `URL` 对象，而不是 `InputStream`。

最后，识别已知 DTD 的机制源于 SGML。这里有一个示例：

```xml
<!DOCTYPE web-app PUBLIC "-//Sun Microsystems, Inc.//DTD Web Application 2.2//EN" "web-app_2_2.dtd">
```

如果 XML 处理器知道如何通过标识符定位 DTD，它就不需要访问 URL。

如果你使用 DOM 解析器并希望支持 `PUBLIC` 标识符，请调用 `DocumentBuilder` 类的 `setEntityResolver` 方法来安装实现 `EntityResolver` 接口的类对象。这是一个典型实现的概述：

```java
class MyEntityResolver implements EntityResolver {
    public InputSource resolveEntity(String publicID, String systemID) {
        if (publicID.equals(known ID)) {
            return new InputSource(DTD data);
        } else {
            return null; // 使用默认行为
        }
    }
}
```

可以通过 `InputStream`、`Reader` 或字符串构造输入源。

现在你已经看到了解析器如何定位 DTD，让我们来考虑各种规则。

`ELEMENT` 规则规定了元素可以包含哪些子元素。使用表 3.1 所示的组件组成的正则表达式。（part0008_split_000.html_ch03tab01）

这里有几个简单但典型的示例。以下规则规定 `menu` 元素包含 0 或多个 `item` 元素：

```xml
<!ELEMENT menu (item)*>
```

这组规则表示字体由一个名称后跟一个大小来描述，每个部分都包含文本：

```xml
<!ELEMENT font (name,size)>
<!ELEMENT name (#PCDATA)>
<!ELEMENT size (#PCDATA)>
```

`PCDATA` 缩写表示*已解析的字符数据*（parsed character data）。之所以被称为“已解析”，是因为解析器会解释文本字符串，寻找表示新标签开始的 `<` 字符或表示实体开始的 `&` 字符。

元素规范可以包含嵌套且复杂的正则表达式。例如，这里有一条描述书中章节组成构造的规则：

```xml
<!ELEMENT chapter (intro,(heading,(para|image|table|note)+)+)>
```

每个章节都以引言开始，随后是一个或多个节，每个节由一个标题以及一个多个段落、图像、表格或注释组成。

然而，在一种常见情况下，你无法将规则定义得如你那样灵活。当元素可以包含文本时，只有两种有效情况：元素仅包含文本，例如：

```xml
<!ELEMENT name (#PCDATA)>
```

或者元素包含文本和标签的任意顺序的组合，例如：

```xml
<!ELEMENT para (#PCDATA|em|strong|code)*>
```

指定任何其他包含 `#PCDATA` 的规则类型都是非法的。例如，以下是非法的：

```xml
<!ELEMENT captionedImage (image,#PCDATA)>
```

你必须重写此类规则，可以通过引入另一个 `caption` 元素，或者允许 `image` 元素与文本的任意组合。

这种限制简化了 XML 解析器处理*混合内容*（标签与文本的混合体）的工作。由于允许混合内容会失去一些控制权，最好设计 DTD 时，使得所有元素要么包含其他元素，要么仅包含文本。

> ![图像](img/00002.jpeg) **注意**
>
> 实际上，在 DTD 规则中可以指定元素的任意正则表达式并不是完全准确的。XML 解析器可能会拒绝某些导致非确定性解析的复杂规则集。例如，正则表达式 `((x,y)|(x,z))` 是非确定性的。当解析器看到 `x` 时，它不知道选择两个备选中的哪一个。此表达式可以重写为确定性形式 `(x,(y|z))`。然而，某些表达式无法重构，例如 `((x,y)*|x?)`。
>
> Java XML 库中的解析器在遇到模糊 DTD 时不会给出警告；它在解析时仅选择第一个匹配的备选项，这会导致它拒绝一些正确的输入。解析器有权这样做，因为 XML 标准允许解析器假设 DTD 是无歧的。
>
> 在实践中，这不是一个你需要为此失眠的问题，因为大多数 DTD 非常简单，你永远不会遇到歧义问题。

你还可以指定规则来描述元素的合法属性。通用语法为：

```xml
<!ATTLIST element attribute type default >
```

表 3.2 显示了法的属性类型，表 3.3 显示了默认值的语法。

![图像](img/00064.jpeg)

**表 3.2 属性类型**

![图像](img/00065.jpeg)

**表 3.3 属性默认**

以下是两个典型的属性规范：

```xml
<!ATTLIST font style (plain|bold|italic|bold-italic) "plain">
<!ATTLIST size unit CDATA #IMPLIED>
```

第一个规范描述了 `font` 元素的 `style` 属性。共有四个法的属性值，默认值为 `plain`。第二个规范表示 `size` 元素的 `unit` 属性可以包含任何字符数据序列。

> ![图像](img/00002.jpeg) **注意**
>
> 我们通常建议使用元素而非属性来描述数据。因此，字体样式应该是一个独立的元素，例如 `<font><style>plain</style>. . .</font>`。然而，属性对于枚举类型具有不可否认的优势，因为解析器可以验证值是否是合法的。例如，如果字体样式是一个属性，解析器会检查它是否为四个允许值之一，并在未给值时提供默认值。

处理 `CDATA` 属性值的处理与你之前看到的 `#PCDATA` 处理略有不同，且与 `<![CDATA[. . .]]>` 部分完全无关。属性值首先会被*归一化*——也就是说，解析器处理字符和实体引用（如 `&#233;` 或 `&lt;`）并将空白替换为空格。

`NMTOKEN`（或名称令牌）与 `CDATA` 类似，但不允许非字母数字字符和内部空白，且解析器会移除首尾空白。`NMTOKENS` 是一个由空格分隔的令牌列表。

（注：后续重复内容已根据高级文档工程师准则进行去重）

此处 DTD 的介绍结束。现在你已经了解了如何使用 DTD，可以配置解析器来利用它们。

首先，告诉文档生成器开启验证：

```java
factory.setValidating(true);
```

验证最有用的处是忽略元素内容中的空白。例如，考虑 XML 片段：

```xml
<font>
  <name>Helvetica</name>
  <size>36</size>
</font>
```

非验证解析器会报告 `font`、`name` 和 `size` 元素之间的空白，因为它无法知道 `font` 的子元素是：

```text
(name,size)
(#PCDATA,name,size)*
```

或者是：

```text
ANY
```

一旦 DTD 指定子元素为 `(name,size)`，解析器就知道它们之间的不是文本。调用：

```java
factory.setIgnoringContentWhitespace(true);
```

生成器将停止报告文本节点中的空白。这意味着你现在可以*依赖* `font` 节点有两个子元素。你不再需要编写一个枯燥的循环：

```java
for (int i = 0; i < children.getLength(); i++) {
    Node child = children.item(i);
    if (child instanceof Element) {
        Element childElement = (Element) child;
        if (childElement.getTagName().equals("name")) // . .
        else if (childElement.getTagName().equals("size")) // . .
    }
}
```

相反，你可以直接访问第一个和第二个子元素：

```java
Element nameElement = (Element) children.item(0);
Element sizeElement = (Element) children.item(1);
```

这就是为什么 `DTDss` 如此实用。你不需要在程序中载入大量的规则检查代码——在你获取文档之前，解析器已经完成了完成了这些工作。

![Image](img/00003.jpeg) **提示**

许多开始使用 XML 的程序员对验证感到不习惯，最终只能在运行时分析 DOM 树。如果你需要说服同事使用经过验证文档的好处，请向他们展示这两种编码方案——这应该能说服他们。

当解析器报告错误时，你的应用程序将希望对其进行处理——记录日志、显示给用户，或者抛出异常以放弃解析。因此，每当你使用验证功能时，都应该安装一个错误处理器。提供一个实现 `ErrorHandler` 接口的对象。该接口有三个方法：

```java
void warning(SAXParseException exception)
void error(SAXParseException exception)
void fatalError(SAXParseException exception)
```

使用 `DocumentBuilder` 类的 `setErrorHandler` 方法安装错误处理器：

```java
builder.setErrorHandler(handler);
```



### `javax.xml.parsers.DocumentBuilder` **1.4**

- `void setEntityResolver(EntityResolver resolver)` 设置解析器，以定位正在解析的 XML 文档中引用的实体。
- `void setErrorHandler(ErrorHandler handler)` 设置处理器以报告解析过程中发生的错误和警告。

### `org.xml.sax.EntityResolver` **1.4**

- `public InputSource resolveEntity(String publicID, String systemID)` 返回一个包含给定 ID 引用数据的输入源，或者返回 `null` 表示该解析器不知道如何解析该特定名称。如果未提供公共 ID，`publicID` 参数可能为 `null`。

### `org.xml.sax.InputSource` **1.4**

- `InputSource(InputStream in)`
- `InputSource(Reader in)`
- `InputSource(String systemID)` 从流、读取器或系统 ID（通常是相对或绝对 URL）构造输入源。

### `org.xml.sax.ErrorHandler` **1.4**

- `void fatalError(SAXParseException exception)`
- `void error(SAXParseException exception)`
- `void warning(SAXParseException exception)` 重写这些方法为致命错误、非致命错误和警告提供处理器。

### `org.xml.sax.SAXParseException` **1.4**

- `int getLineNumber()`
- `int getColumnNumber()` 返回导致异常的已处理输入的行号和列号。

### `javax.xml.parsers.DocumentBuilderFactory` **1.4**

- `boolean isValidating()`
- `void setValidating(boolean value)` 获取或设置工厂的 `validating` 属性。如果设置为 `true`，则该工厂生成的解析器将验证其输入。
- `boolean isIgnoringElementContentWhitespace()`
- `void setIgnoringElementContentWhitespace(boolean value)` 获取或设置工厂的 `ignoringElementContentWhitespace` 属性。如果设置为 `true`，则该工厂生成的解析器将忽略没有混合内容（即元素和 `#PCDATA` 的混合）的元素节点之间的空白。

### 3.3.2 XML Schema

XML Schema 比 DTD 语法复杂得多，因此我们只涵盖基础知识。欲需更多信息，我们建议查看 `www.w3.org/TR/xmlschema-0` 教程。

要在文档中引用 Schema 文件，可以在根元素上添加属性，例如：

```xml
<?xml version="1.0"?>
<configuration xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
      xsi:noNamespaceSchemaLocation="config.xsd">
    . . .
</configuration>
```

此声明表示应使用 schema 文件 `config.xsd` 来验证文档。如果你的文档使用了命名空间，语法会复杂一些——详情请参见 XML Schema 教程。（前缀 `xsi` 是命名空间别名；更多信息请参阅 第 3.5 节 中的使用命名空间](#part0008_split_000.html_ch03lev1sec5)以及 第 196 页）。

schema 为每个元素定义了一个*类型*。该类型可以是*简单类型*——一个带有格式限制的字符串——也可以是*复杂类型*。某些简单类型是内置在 XML Schema 中的，包括：

```xml
xsd:string
xsd:int
xsd:boolean
```

![Image](img/00002.jpeg) 我们使用前缀 `xsd:` 来表示 XML Schema 命名空间。有些作者使用前缀 `xs:`。

你可以定义自己的简单类型。例如，这是一个枚举类型：

```xml
<xsd:simpleType name="StyleType">
  <xsd:restriction base="xsd:string">
    <xsd:enumeration value="PLAIN" />
    <xsd:enumeration value="BOLD" />
    <xsd:enumeration value="ITALIC" />
    <xsd:enumeration value="BOLD_ITALIC" />
  </xsd:restriction>
</xsd:simpleType>
```

当定义元素时，你需要指定其类型：

```xml
<xsd:element name="name" type="xsd:string"/>
<xsd:element name="size" type="xsd:int"/>
<xsd:element name="style" type="StyleType"/>
```

类型限制了元素的内容。例如，元素：

```xml
<size>10</size>
<style>PLAIN</style>
```

可以正确验证，但元素：

```xml
<size>default</size>
<style>SLANTED</style>
```

会被解析器拒绝。

你可以将类型组合成复杂类型，例如：

```xml
<xsd:complexType name="FontType">
  <xsd:sequence>
    <xsd:element ref="name"/>
    <xsd:element ref="size"/>
    <xsd:element ref="style"/>
  </xsd:sequence>
</xsd:complexType>
```

`FontType` 是 `name`、`size` 和 `style` 元素的序列。在类型定义中，我们使用 `ref` 属性来引用其他处的定义。你也可以这样嵌套定义：

```xml
<xsd:complexType name="FontType">
  <xsd:sequence>
    <xsd:element name="name" type="xsd:string"/>
    <xsd:element name="size" type="xsd:int"/>
    <xsd:element name="style" type="StyleType">
      <xsd:simpleType>
        <xsd:restriction base="xsd:string">
          <xsd:enumeration value="PLAIN" />
          <xsd:enumeration value="BOLD" />
          <xsd:enumeration value="ITALIC" />
          <xsd:enumeration value="BOLD_ITALIC" />
        </xsd:restriction>
      </xsd:simpleType>
    </xsd:element>
  </xsd:sequence>
</xsd:complexType>
```

注意 `style` 元素的*匿名类型定义*。

`xsd:sequence` 构造是 DTD 中拼接表示法的等价物。`xsd:choice` 构造是 `|` 运算符的等价物。例如：

```xml
<xsd:complexType name="contactinfo">
  <xsd:choice>
    <xsd:element ref="email"/>
    <xsd:element ref="phone"/>
  </xsd:choice>
</xsd:complexType>
```

这是 DTD 类型 `email|phone` 的等价物。

要允许重复元素，使用 `minoccurs` 和 `maxoccurs` 属性。例如，DTD 类型 `item*` 的等价物是：

```xml
<xsd:element name="item" type="..." minoccurs="0" maxoccurs="unbounded">
```

要指定属性，在 `complexType` 定义中添加 `xsd:attribute` 元素：

```xml
<xsd:element name="size">
   <xsd:complexType>
      . . .
      <xsd:attribute name="unit" type="xsd:string" use="optional" default="cm"/>
   </xsd:complexType>
</xsd:element>
```

这等同于 DTD 语句：

```xml
<!ATTLIST size unit CDATA #IMPLIED "cm">
```

将你的 schema 的元素定义和类型定义封装在 `xsd:schema` 元素中：

```xml
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema">
   . . .
</xsd:schema>
```

使用 schema 解析 XML 文件与使用 DTD 解析文件类似，但有三点不同：

1. 你需要开启命名空间支持，即使你在 XML 文件中没有使用它们。

```java
factory.setNamespaceAware(true);
```

2. 你需要准备工厂来处理 schema，使用以下“魔法咒语”：

```java
final String JAXP_SCHEMA_LANGUAGE = "http://java.sun.com/xml/jaxp/properties/schemaLanguage";
final String W3C_XML_SCHEMA = "http://www.w3.org/2001/XMLSchema";
factory.setAttribute(JAXP_SCHEMA_LANGUAGE, W3C_XML_SCHEMA);
```

3. 解析器`不会丢弃元素内容的空白符`。这是一个非常困扰的问题，关于这是否是一个真正的 bug 业界存在争议。请参阅第 185 页 上 列表 3.4 中的代码获取解决方案。

### 3.3.3 实际示例

在本节中，我们将通过一个实际示例来展示 XML 在真实场景中的用法。回想第一卷 第 12 章，`GridBagLayout` 是 Swing 组件中最实用的布局管理器。然而，人们对其望畏有之——不仅是因为它的复杂性，还因为编程时的繁琐。如果能将布局描述放入文本文件中，而不是产生大量的重复代码，将会方便得多。在本节中，你将看到如何使用 XML 来描述 grid bag 布局以及如何解析这些布局文件。

grid bag 由行和列组成，非常类似于 HTML 表。类似于 HTML 表格，我们将其描述为一系列行，每行都包含单元格：

```xml
<gridbag>
   <row>
      <cell>. . .</cell>
      <cell>. . .</cell>
      . . .
   </row>
   <row>
      <cell>. . .</cell>
      <cell>. . .</cell>
      . . .
   </row>
   . . .
</gridbag>
```

`gridbag.dtd` 规定了这些规则：

```xml
<!ELEMENT gridbag (row)*>
<!ELEMENT row (cell)*>
```

某些单元格可以跨越多行多列。在 grid bag 布局中，这是通过将 `gridwidth` 和 `gridheight` 约束设置为大于 `1` 的值来实现。我们将使用同名的属性：

```xml
<cell gridwidth="2" gridheight="2">
```

同样，我们可以使用属性来处理其他的 grid bag 约束 `fill`、`anchor`、`gridx`、`gridy`、`weightx`、`weighty`、`ipadx` 和 `ipady`。（我们没有处理 `insets` 约束，因为它的值不是简单类型，但支持它并不困难）。例如：

```xml
<cell fill="HORIZONTAL" anchor="NORTH">
```

对于这些属性中的大部分，我们提供的默认值与 `GridBagConstraints` 类的无参构造函数相同：

```xml
<!ATTLIST cell gridwidth CDATA "1">
<!ATTLIST cell gridheight CDATA "1">
<!ATTLIST cell fill (NONE|BOTH|HORIZONTAL|VERTICAL) "NONE">
<!ATTLIST cell anchor (CENTER|NORTH|NORTHEAST|EAST|SOUTHEAST|SOUTH|SOUTHWEST|WEST|NORTHWEST) "CENTER">
. . .
```

`gridx` 和 `gridy` 值受到了特殊处理，因为手动指定它们会非常繁琐且容易出错。提供它们是可选的：

```xml
<!ATTLIST cell gridx CDATA #IMPLIED>
<!ATTLIST cell gridy CDATA #IMPLIED>
```

如果没有提供这些值，程序将根据以下启发算法确定它们：在第 0 列中，`gridx` 为 `0`；否则，它是前面的 `gridwidth`。`gridy` 总是前面的数字。因此，如果一个组件跨越多列，你必须指定 `gridx` 和 `gridy`。

程序通过使用 `BeanInfo` 类来设置属性。`BeanInfo` 列举了 bean 的属性描述符。我们寻找名称匹配的属性，然后使用提供的值调用其设置方法（setter method）。

当我们的程序读取用户界面描述时，它拥有足够的信息来构建和安排用户界面组件。但当然，界面本身不是活跃的——没有绑定任何事件监听器。为了添加事件监听器，我们必须定位这些组件。因此，我们为每个 bean 都提供了一个类型为 `ID` 的可选属性：

```xml
<!ATTLIST bean id ID #IMPLIED>
```

例如，这里有一个带有 ID 的组合框：

```xml
<bean id="face">
  <class>javax.swing.JComboBox</class>
</bean>
```

请记住，解析器会检查 ID 是否是唯一的。

程序员可以这样绑定事件处理器：

```java
gridbag = new GridBagPane("fontdialog.xml");
setContentPane(gridbag);
JComboBox face = (JComboBox) gridbag.get("face");
face.addListener(listener);
```

***

![Image](img/00002.jpeg) 备注

在此示例中，我们仅使用 XML 来描述组件布局，并留给程序员在 Java 代码中绑定事件处理器。你可以更进一步，将代码直接添加到 XML 描述中。最有前景的方法是使用 JavaScript 等脚本语言来编写代码。如果你想添加该增强，请查看第 8 章中描述的 Nashorn JavaScript 解释器](#part0013.html_ch08)。

***

Listing 3.2 中的程序展示了如何使用 `GridBagPane` 类来完成设置 grid bag 布局的所有枯燥工作。布局定义在 Listing 3.4 中；图 3.4 显示了结果。程序只初始化了组合框（对于 `GridBagPane` 支持的 bean 属性设置机制来说太复杂了）并绑定了事件监听器。Listing 3.3 中的 `GridBagPane` 类解析 XML 文件、构建组件并进行布局。Listing 3.5 显示了 DTD。

如果你选择了一个包含字符串 `-schema` 的文件，程序也可以处理 schema 而不是 DTD。

Listing 3.6 包含了该 schema。

这个示例是 XML 的典型用法。XML 格式足够健壮，可以表达复杂的关系。XML 解析器通过接管有效性检查的常规工作并提供默认值来增加价值。

### Listing 3.2 `read/GridBagTest.java`

```java
package read;

import java.awt.*;
import java.awt.event.*;
```



```java
import java.io.*;

import javax.swing.*;

/**
 * 此程序展示了如何使用 XML 文件来描述 gridbag 布局。
 *
 * @version 1.12 2016-04-27
 * @author Cay Horstmann
 */
public class GridBagTest
{
  public static void main(String[] args)
  {
    EventQueue.invokeLater(() ->
        {
          JFileChooser chooser = new JFileChooser(".");
          chooser.showOpenDialog(null);
          File file = chooser.getSelectedFile();

          JFrame frame = new FontFrame(file);
          frame.setTitle("GridBagTest");
          frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
          frame.setVisible(true);
        });
  }

  /**
   * 此框架包含一个由 XML 文件描述的字体选择。
   *
   * @param filename 对话框的用户界面组件
   */
  class FontFrame extends JFrame
  {
    GridBagPane gridbag;
    JComboBox<String> face;
    JComboBox<String> size;
    CheckBox bold;
    CheckBox italic;

    @SuppressWarnings("unchecked")
    public FontFrame(File file)
    {
      gridbag = new GridBagPane(file);
      add(gridbag);

      face = (JComboBox<String>) gridbag.get("face");
      size = (JComboBox<String>) gridbag.get("size");
      bold = (JCheckBox) gridbag.get("bold");
      italic = (JCheckBox) gridbag.get("italic");

      face.setModel(new DefaultComboBoxModel<String>(new String[] {
          "Serif", "SansSerif", "Monospaced", "Dialog", "DialogInput"
      }));

      size.setModel(new DefaultComboBoxModel<String>(new String[] {
          "8", "10", "12", "15", "18", "24", "36", "48"
      }));

      ActionListener listener = event -> setSample();

      face.addActionListener(listener);
      size.addActionListener(listener);
      bold.addActionListener(listener);
      italic.addActionListener(listener);

      setSample();
      pack();
    }

    /**
     * 此方法根据选定的字体设置 sample。
     */
    public void setSample()
    {
      String fontFace = face.getItemAt(face.getSelectedIndex());
      int fontSize = Integer.parseInt(size.getSelectedIndex());
      JTextArea sample = (JTextArea) gridbag.get("sample");

      int fontStyle = (bold.isSelected() ? Font.BOLD : 0)
          + (italic.isSelected() ? Font.ITALIC : 0);

      sample.setFont(new Font(fontFace, fontStyle, fontSize));
      sample.repaint();
    }
  }
}
```

### 列表 3.3：`read/GridBagPane.java`

点击此处查看代码图片。

```java
package read;

import java.awt.*;
import java.beans.*;
import java.io.*;
import java.lang.reflect.*;

import javax.swing.*;
import javax.xml.parsers.*;

import org.w3c.dom.*;

/**
 * 此面板使用 XML 文件来描述其组件和 bag 布局。
 */
public class GridBagPane extends JPanel
{
  GridBagConstraints constraints;

  /**
   * 构造一个 grid bag 面。
   *
   * @param filename 描述面板组件及其位置的 XML 文件名
   */
  public GridBagPane(File file)
  {
    setLayout(new GridBagLayout());
    constraints = new GridBagConstraints();

    try
    {
      DocumentBuilderFactory factory = DocumentBuilderFactory.newInstance();
      factory.setValidating(true);

      if (file.toString().contains("-schema"))
      {
        factory.setNamespaceAware(true);

        final String JAXP_SCHEMA_LANGUAGE =
            "http://java.sun.com/xml/jaxp/properties/schemaLanguage";
        final String W3C_XML_SCHEMA =
            "http://www.w3.org/2001/XMLSchema";

        factory.setAttribute(JAXP_SCHEMA_LANGUAGE, W3C_XML_SCHEMA);
      }

      factory.setIgnoringElementContentWhitespace(true);

      DocumentBuilder builder = factory.newDocumentBuilder();
      Document doc = builder.parse(file);
      parseGridbag(doc.getDocumentElement());
    }
    catch (Exception e)
    {
      e.printStackTrace();
    }
  }
}
```

此处省略了 `parseGridbag()` 方法的具体实现，以符合提供的代码片段逻辑。

```java
public Component get(String name)
{
  Component[] components = getComponents();

  for (int i = 0; i < components.length; i++)
  {
    if (components[i].getName().equals(name))
    {
      return components[i];
    }
  }

  return null;
}
```

```java
/**
 * 解析一个 gridbag 元素。
 *
 * @param e gridbag 元素
 */
private void parseGridbag(Element e)
{
  NodeList rows = e.getChildNodes();

  for (int i = 0; i < rows.getLength(); i++)
  {
    Element row = (Element) rows.item(i);
    NodeList cells = row.getChildNodes();

    for (int j = 0; j < cells.getLength(); j++)
    {
      Element cell = (Element) cells.item(j);
      parseCell(cell, i, j);
    }
  }
}

/**
 * 解析一个单元格元素。
 *
 * @param e 单元格元素
 * @param r 单元格的行
 * @param c 单元格的列
 */
private void parseCell(Element e, int r, int c)
{
  // 获取属性
  String value = e.getAttribute("gridx");

  if (value.length() == 0) // 使用默认值
  {
    if (c == 0)
    {
      constraints.gridx = 0;
    }
    else
    {
      constraints.gridx += constraints.gridwidth;
    }
  }
  else
  {
    constraints.gridx = Integer.parseInt(value);
  }

  value = e.getAttribute("gridy");

  if (value.length() == 0) // 使用默认值
  {
    constraints.gridy = r;
  }
  else
  {
    constraints.gridy = Integer.parseInt(value);
  }

  constraints.gridwidth = Integer.parseInt(e.getAttribute("gridwidth"));
  constraints.height = Integer.parseInt(e.getAttribute("height"));
  constraints.weightx = Integer.parseInt(e.getAttribute("weightx"));
  constraints.weighty = Integer.parseInt(e.getAttribute("weighty"));
  constraints.ipadx = Integer.parseInt(e.getAttribute("ipadx"));
  constraints.ipady = Integer.parseInt(e.getAttribute("ipady"));

  // 使用反射获取静态字段的值
  Class<GridBagConstraints> cl = GridBagConstraints.class;

  try
  {
    String name = e.getAttribute("fill");
    Field f = cl.getField(name);
    constraints.fill = f.getInt(cl);

    name = e.getAttribute("anchor");
    f = cl.getField(name);
    constraints.anchor = f.getInt(cl);
  }
  catch (Exception ex) // 反射方法可能会抛异常
  {
    ex.printStackTrace();
  }

  Component comp = (Component) parseBean((Element) e.getFirstChild());
  add(comp, constraints);
}

/**
 * 解析一个 bean 元素。
 *
 * @param e bean 元素
 */
private Object parseBean(Element e)
{
  try
  {
    NodeList children = e.getChildNodes();
    Element classElement = (Element) children.item(0);
    String className = ((Text) classElement.getFirstChild()).getData();

    Class<?> cl = Class.forName(className);
    Object obj = cl.newInstance();

    if (obj instanceof Component)
    {
      ((Component) obj).setName(e.getAttribute("id"));
    }

    for (int i = 1; i < children.getLength(); i++)
    {
      Node propertyElement = children.item(i);
      Element nameElement = (Element) propertyElement.getFirstChild();
      String propertyName = ((Text) nameElement.getFirstChild()).getData();

      Element valueElement = (Element) propertyElement.getLastChild();
      Object value = parseValue(valueElement);

      BeanInfo beanInfo = Introspector.getBeanInfo(cl);
      PropertyDescriptor[] descriptors = beanInfo.getPropertyDescriptors();

      boolean done = false;

      for (int j = 0; !done && j < descriptors.length; j++)
      {
        if (descriptors[j].getName().equals(propertyName))
        {
          descriptors[j].getWriteMethod().invoke(obj, value);
          done = true;
        }
      }
    }

    return obj;
  }
  catch (Exception ex) // 反射方法可能会抛异常
  {
    ex.printStackTrace();
    return null;
  }
}

/**
 * 解析一个值元素。
 *
 * @param e 值元素
 */
private Object parseValue(Element e)
{
  Element child = (Element) e.getFirstChild();

  if (child.getTagName().equals("bean"))
  {
    return parseBean(child);
  }

  String text = ((Text) child.getFirstChild()).getData();

  if (child.getTagName().equals("int"))
  {
    return new Integer(text);
  }
  else if (child.getTagName().equals("boolean"))
  {
    return new Boolean(text);
  }
  else if (child.getTagName().equals("string"))
  {
    return text;
  }
  else
  {
    return null;
  }
}
```

### 列表 3：`dialog.xml`



```xml
<?xml version="1.0"?>
<!DOCTYPE gridbag SYSTEM "gridbag.dtd">
<gridbag>
  <row>
    <cell anchor="EAST">
      <bean>
        <class>javax.swing.JLabel</class>
        <property>
          <name>text</name>
          <value>Face: </string></value>
        </property>
      </bean>
    </cell>
    <cell fill="HORIZONTAL" weightx="100">
      <bean id="face">
        <class>javax.swing.JComboBox</class>
      </bean>
    </cell>
    <cell height="4" fill="BOTH" weightx="100" weighty="100">
      <bean id="sample">
        <class>javax.swing.JTextArea</class>
        <property>
          <name>text</name>
          <value>The quick brown fox jumps over the lazy dog</string></value>
        </property>
        <property>
          <name>editable</name>
          <value>false</boolean></value>
        </property>
        <property>
          <name>rows</name>
          <value><int>8</int></value>
        </property>
        <property>
          <name>columns</name>
          <value><int>20</int></value>
        </property>
        <property>
          <name>lineWrap</name>
          <value>true</boolean></value>
        </property>
        <property>
          <name>border</name>
          <value>
            <bean>
              <class>javax.swing.border.EtchedBorder</class>
            </bean>
          </value>
        </property>
      </bean>
    </cell>
  </row>
</gridbag>
```

```xml
      </cell>
  </row>
  <row>
    <cell gridwidth="2" weighty="100">
      <bean id="bold">
        <class>javax.swing.JCheckBox</class>
        <property>
          <name>text</name>
          <value><string>Bold</string></value>
        </property>
      </bean>
    </cell>
  </row>
  <row>
    <cell gridwidth="2" weighty="100">
      <bean id="italic">
        <class>javax.swing.JCheckBox</class>
        <property>
          <name>text</name>
          <value><string>Italic</string></value>
        </property>
      </bean>
    </cell>
  </row>
</gridbag>
```

**列表 3.5** `read/gridbag.dtd`

点击此处查看代码图片

```dtd
1   <!ELEMENT gridbag (row)*>
2   <!ELEMENT row (cell)*>
3   <!ELEMENT cell (bean)>
4   <!ATTLIST cell gridx CDATA #IMPLIED>
5   <!ATTLIST cell gridy CDATA #IMPLIED>
6   <!ATTLIST cell gridwidth CDATA "1">
7   <!ATTLIST cell gridheight CDATA "1">
8   <!ATTLIST cell weightx CDATA "0">
9   <!ATTLIST cell weighty CDATA "0">
10  <!ATTLIST cell fill (NONE|BOTH|HORIZONTAL|VERTICAL) "NONE">
11  <!ATTLIST cell anchor
12      (CENTER|NORTH|NORTHEAST|EAST|SOUTHEAST|SOUTH|SOUTHWEST|WEST|NORTHWEST) "CENTER">
13  <!ATTLIST cell ipadx CDATA "0">
14  <!ATTLIST cell ipady CDATA "0">
15
16  <!ELEMENT bean (class, property*)>
17  <!ATTLIST bean id ID #IMPLIED>
18
19   <!ELEMENT class (#PCDATA)>
20   <!ELEMENT property (name, value)>
21   <!ELEMENT name (#PCDATA)>
22   <!ELEMENT value (int|string|boolean)>
23   <!ELEMENT int (#PCDATA)>
24   <!ELEMENT string (#PCDATA)>
25   <!ELEMENT boolean (#PCDATA)>
```

**列表 3.6** `read/gridbag.xsd`

点击此处查看图片

```xml
1   <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema">
2
3   <xsd:element name="gridbag" type="GridType"/>
4
5   <xsd:element name="bean" type="BeanType"/>
6
7   <xsd:complexType name="GridType">
8     <xsd:sequence>
9       <xsd:element name="row" type="RowType" minOccurs="0" maxOccurs="unbounded"/>
10    </xsd:sequence>
11   </xsd:complexType>
12
13  <xsd:complexType name="RowType">
14    <xsd:sequence>
15      <xsd:element name="cell" type="CellType" minOccurs="0" maxOccurs="unbounded"/>
16    </xsd:sequence>
17  </xsd:complexType>
18
19  <xsd:complexType name="CellType">
20    <xsd:sequence>
21      <xsd:element ref="bean"/>
22    </xsd:sequence>
23    <xsd:attribute name="gridx" type="xsd:int" use="optional"/>
24    <xsd:attribute name="gridy" type="xsd:int" use="optional"/>
25    <xsd:attribute name="gridwidth" type="xsd:int" use="optional" default="1" />
26    <xsd:attribute name="gridheight" type="xsd:int" use="optional" default="1" />
27    <xsd:attribute name="weightx" type="xsd:int" use="optional" default="0" />
28    <xsd:attribute name="weighty" type="xsd:int" use="optional" default="0" />
29    <xsd:attribute name="fill" use="optional" default="NONE">
30      <xsd:simpleType>
31        <xsd:restriction base="xsd:string">
32          <xsd:enumeration value="NONE" />
33          <xsd:enumeration value="BOTH" />
34          <xsd:enumeration value="HORIZONTAL" />
35          <xsd:enumeration value="VERTICAL" />
36        </xsd:restriction>
37      </xsd:simpleType>
38    </xsd:attribute>
39    <xsd:attribute name="anchor" use="optional" default="CENTER">
40      <xsd:simpleType>
41        <xsd:restriction base="xsd:string">
42          <xsd:enumeration value="CENTER" />
43          <xsd:enumeration value="NORTH" />
44          <xsd:enumeration value="NORTHEAST" />
45          <xsd:enumeration value="EAST" />
46          <xsd:enumeration value="SOUTHEAST" />
47          <xsd:enumeration value="SOUTH" />
48          <xsd:enumeration value="SOUTHWEST" />
49          <xsd:enumeration value="WEST" />
50          <xsd:enumeration value="NORTHWEST" />
51        </xsd:restriction>
52      </xsd:simpleType>
53    </xsd:attribute>
54    <xsd:attribute name="ipadx" type="xsd:int" use="optional"/>
55    <xsd:attribute name="ipady" type="xsd:int" use="optional"/>
56  </xsd:complexType>
57
58  <xsd:complexType name="BeanType">
59    <xsd:sequence>
60      <xsd:element name="class"/>
61      <xsd:element name="property" type="PropertyType" minOccurs="0" maxOccurs="unbounded"/>
62    </xsd:sequence>
63    <xsd:attribute name="id" type="xsd:ID" use="optional"/>
64  </xsd:complexType>
67
68  <xsd:complexType name="PropertyType">
69    <xsd:sequence>
70      <xsd:element name="name"/>
71      <xsd:element name="value"/>
72    </xsd:sequence>
73  </xsd:complexType>
74
75  <xsd:complexType name="ValueType">
76    <xsd:choice>
77      <xsd:element name="int" type="xsd:int"/>
78      <xsd:element name="string" type="xsd:string"/>
79      <xsd:element name="boolean" type="xsd:boolean"/>
80    </xsd:choice>
81  </xsd:complexType>
82
</xsd:schema>
```

### 3.4 使用 XPath 定位信息

如果你想在 XML 文档中定位特定的信息，遍历树结构可能会比较麻烦。XPath 语言让这一切变得简单。例如，假设有以下 XML 文档：

点击此处查看图片

```xml
<configuration>
  <database>
    <username>dbuser</username>
    <password>secret</password>
  </database>
</configuration>
```

你可以通过评估 XPath 表达式获取数据库用户名：

点击此处查看图片

`/configuration/database/username`

这比纯 DOM 方法简单得多：

1. 获取文档节点。
2. 遍历子元素。
3. 定位`database`元素。
4. 在其子元素中定位`username`元素。
5. 在其子元素中定位文本节点。
6. 获取数据。

XPath 可以描述 XML 文档中的节点集。例如，XPath `/gridbag/row` 描述了`gridbag`根元素的所有`row`元素。你可以使用`[]`操作选择特定的元素：`/gridbag/row[1]`是第一行。（索引从 1 开始。）

使用`@`操作获取属性值。XPath 表达式描述了`gridbag`根元素下所有`row`元素中`cell`元素的`anchor`属性节点。

XPath 还有许多有用的函数。例如，`count(/gridbag/row)`返回`gridbag`根元素的`row`子元素的数量。还有更多复杂的 XPath 表达式；请参阅规范`www.w3c.org/TR/xpath`或优秀的在线教程`www.zvon.org/xxl/XPathTutorial/General/examples.html`。

Java SE 5.0 增加了评估 XPath 表达式的 API。首先，从`XPathFactory`创建`XPath`对象：

```java
XPathFactory xpfactory = XPathFactory.newInstance();
path = xpfactory.newXPath();
```

然后，调用`evaluate`方法来评估 XPath 表达式：

点击此处查看代码图片

```java
String username = path.evaluate("/configuration/database/username", doc);
```

你可以使用同一个`XPath`对象来评估多个表达式。

这种形式的`evaluate`方法返回一个字符串结果。它适用于获取文本，例如获取上一个示例中`username`节点的文本。如果 XPath 表达式产生一个节点集（node set），请调用如下所示的方法：

点击此处查看代码图片

```java
NodeList nodes = (NodeList) path.evaluate("/gridbag/row", doc, XPathConstants.NODESET);
```

如果结果是单个节点，请使用`XPathConstants.NODE`代替它：

点击此处查看代码图片

```java
Node node = (Node) path.evaluate("/gridbag/row[1]", doc, XPathConstants.NODE);
```

如果结果是一个数字，请使用`XPathConstants.NUMBER`：

点击此处查看代码图片

```java
int count = ((Number) path.evaluate("count(/gridbag/row)", doc, XPathConstants.NUMBER)).intValue();
```

你不需要从文档根节点开始搜索；你可以从任何节点或节点列表开始。例如，如果你有一个从上一次评估得到的节点，可以调用：

点击此处查看代码图片

```java
result = path.evaluate(expression, node);
```



## XPath 表达式的评估

Listing 3.7 中的程序演示了 XPath 表达式的评估。加载一个 XML 文件并输入一个表达式。选择表达式类型并点击 `Evaluate` 按钮。表达式的结果显示在框架底部（参见图 3.5）。

![Image](img/00067.jpeg)

**图 3.5** 评估 XPath 表达式

**Listing 3.7** `xpath/XPathTester.java`

点击此处查看代码图片

```java
package xpath;

import java.awt.*;
import java.awt.event.*;
import java.io.*;
import java.nio.file.*;
import java.util.*;
import javax.swing.*;
import javax.swing.border.*;
import javax.xml.namespace.*;
import javax.xml.parsers.*;
import javax.xml.xpath.*;
import org.w3c.dom.*;
import org.xml.sax.*;

/**
 * 此程序评估 XPath 表达式。
 * @version 1.02 2016-05-10
 * @author Cay Horstmann
 */
public class XPathTester
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() ->
        {
            JFrame frame = new XPathFrame();
            frame.setTitle("XPathTest");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}

/**
 * 此框架显示一个 XML 文档、一个输入表达式的面板以及一个显示
 * 的文本字段。
 */
class XPathFrame extends JFrame
{
    private DocumentBuilder builder;
    private Document doc;
    private XPath path;
    private JTextField expression;
    private JTextField result;
    private JTextArea docText;
    private JComboBox<String> typeCombo;

    public XPathFrame()
    {
        JMenu fileMenu = new JMenu("File");
        JMenuItem openItem = new JMenuItem("Open");
        openItem.addActionListener(event -> openFile());
        fileMenu.add(openItem);

        JMenuItem exitItem = new JMenuItem("Exit");
        exitItem.addActionListener(event -> System.exit(0));
        fileMenu.add(exitItem);

        MenuBar menuBar = new JMenuBar();
        menuBar.add(fileMenu);
        setMenuBar(menuBar);

        ActionListener listener = event -> evaluate();
        expression = new JTextField(20);
        expression.addActionListener(listener);
        JButton evaluateButton = new JButton("Evaluate");
        evaluateButton.addActionListener(listener);

        typeCombo = new JComboBox<String>(new String[] {
            "STRING", "NODE", "NODESET", "NUMBER", "BOOLEAN"
        });
        typeCombo.setSelectedItem("STRING");

        JPanel panel = new JPanel();
        panel.add(expression);
        panel.add(typeCombo);
        panel.add(evaluateButton);
        docText = new JTextArea(10, 40);
        result = new JTextField();
        result.setBorder(new TitledBorder("Result"));

        add(panel, BorderLayout.NORTH);
        add(new JScrollPane(docText), BorderLayout.CENTER);
        add(result, BorderLayout.SOUTH);

        try
        {
            DocumentBuilderFactory factory = DocumentBuilderFactory.newInstance();
            builder = factory.newDocumentBuilder();
        }
        catch (ParserConfigurationException e)
        {
            JOptionPane.showMessageDialog(this, e);
        }

        XPathFactory xpfactory = XPathFactory.newInstance();
        path = xpfactory.newXPath();
        pack();
    }

    /**
     * 打开文件并加载文档。
     */
    public void openFile()
    {
        JFileChooser chooser = new JFileChooser();
        chooser.setCurrentDirectory(new File("xpath"));
        chooser.setFileFilter(new javax.swing.filechooser.FileNameFilter("XML files", "xml"));
        int r = chooser.showDialog(this);
        if (r != JFileChooser.APPROVE_OPTION) return;
        File file = chooser.getSelectedFile();
        try
        {
            docText.setText(new String(Files.readAllBytes(file.toPath())));
            doc = builder.parse(file);
        }
        catch (IOException e)
        {
            JOptionPane.showMessageDialog(this, e);
        }
        catch (SAXException e)
        {
            JOptionPane.showMessageDialog(this, e);
        }
    }

    public void evaluate()
    {
        try
        {
            String typeName = (String) typeCombo.getSelectedItem();
            QName returnType = (QName) XPathConstants.class.getField(typeName).get(null);
            Object evalResult = path.evaluate(expression.getText(), doc, returnType);
            if (typeName.equals("NODESET"))
            {
                NodeList list = (NodeList) evalResult;
                // 因为 NodeList 不是 Iterable，所以不能使用 String.join
                StringJoiner joiner = new StringJoiner(",", "}");
                for (int i = 0; i < list.getLength(); i++)
                {
                    joiner.add("" + list.item(i));
                }
                result.setText("" + joiner);
            }
            else result.setText("" + evalResult);
        }
        catch (XPathExpressionException e)
        {
            JOptionPane.showMessageDialog(this, e);
        }
        catch (Exception e) // 反射异常
        {
            e.printStackTrace();
        }
    }
}
```

### `javax.xml.xpath.XPathFactory` 5.0

- `static XPathFactory newInstance()` 返回一个用于创建 `XPath` 对象的 `XPathFactory` 实例。
- `XPath newXpath()` 构建一个用于评估 XPath 表达式的 `XPath` 对象。

### `javax.xml.xpath.XPath` 5.0

- `String evaluate(String expression, Object startingPoint)` 从给定的起点开始评估表达式。起始点可以是节点或节点列表。如果结果是节点或节点集，返回的字符串由所有文本节点的数据组成。
- `Object evaluate(String expression, Object startingPoint, QName resultType)` 从指定的起始点开始评估表达式。起始点可以是一个节点或节点列表。`resultType` 是 `XPathConstants` 类中的常量 `STRING`、`NODE`、`NODESET`、`NUMBER` 或 `BOOLEAN` 之一。返回值是一个 `String`、`Node`、`NodeList`、`Number` 或 `Boolean`。

## 3.5 使用命名空间

Java 语言使用包（packages）来避免命名冲突。只要不在同一个包中，程序员就可以为不同的类使用相同的名称。XML 对于元素和属性名称也有一套类似的 `namespace（命名空间）` 机制。

命名空间由统一资源标识符（URI）标识，例如：

点击此处查看代码图像

`http://www.w3.org/2001/XMLSchema`

`uuid:1c759aed-b748-475c-ab68-10679700c4f`

`urn:com:books-r-us`

HTTP URL 形式是最常见的。注意，URL 仅用作标识符字符串，而不是文档的定位符。例如，这些命名空间标识符：

点击此处查看代码图像

`http://www.horstmann.com/corejava`

`http://www.horstmann.com/corejava/index.html`

表示`不同的`命名空间，尽管 Web 服务器会为这两个 URL 提供相同的文档。

命名空间 URL 处并不一定有任何文档——XML 解析器不会尝试在该位置查找任何内容。然而，为了帮助遇到可能不熟悉的命名空间的程序员，惯常做法是在该 URL 位置放置一个解释该命名空间用途的文档。例如，如果你将浏览器指向 XML Schema 命名空间的空间 URL（`http://www.w3.org/2001/XMLSchema`），你将看到一个描述 XML Schema 标准的文档。

为什么使用 HTTP URL 作为命名空间标识符？这很容易确保它们的唯一性。如果你选择了一个真实的 URL，主机部分的唯一性由域名系统保证。然后，你的组织可以安排 URL 剩余部分的唯一性。这与 Java 包名中使用反向域名的原理是相同的。

当然，虽然长的命名空间标识符有利于唯一性，但你并不希望尽可能避免处理长的标识符。在 Java 编程语言中，你使用 `import` 机制来指定包的长名称，然后只使用短类名。在 XML 中，有一个类似的机制：

点击此处查看代码图像

```xml
<element xmlns="namespaceURI">
    children
</element>
```

该元素及其子元素现在是给定命名空间的一部分。

子元素可以提供自己的命名空间，例如：

点击此处查看代码图像

```xml
<element xmlns="namespaceURI1">
    <child xmlns="namespaceURI2">
      grandchildren
    </child>
    more children
</element>
```

那么，第一个子元素和孙子元素属于第二个命名空间。

如果你只需要单个命名空间，或者命名空间是自然嵌套的，这种简单的机制就能很好工作。否则，你可能希望使用在 Java 中没有对应的第二机制。你可以为命名空间设置一个 `prefix（前缀）`——你为特定文档选择的短标识符。这里有一个典型的例子——XML Schema 文件中的 `xsd` 前缀：

点击此处查看代码图像

```xml
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <xsd:element name="gridbag" type="GridBagType"/>
    . . .
</xsd:schema>
```

属性 `xmlns:prefix="namespaceURI"` 定义了一个命名空间和一个前缀。在我们的示例中，前缀是字符串 `xsd`。因此，`xsd:schema` 实际上是指命名空间 `http://www.w3.org/2001/XMLSchema` 中的 `schema`。

![Image](img/00002.jpeg)

> **注意**
>
> 只有子元素继承其父元素的命名空间。没有显式前缀的属性永远不会命名空间的一部分。考虑这个人为构造的例子：

点击此处查看代码图像

```xml
<configuration xmlns="http://www.horstmann.com/corejava"
    xmlns:si="http://www.bipm.fr/enus/3_SI/si.html">
    <size value="210" si:unit="mm"/>
    . . .
</configuration>
```

在这个示例中，元素 `configuration` 和 `size` 属于 URI 为 `http://www.horstmann.com/corejava` 的命名空间。属性 `si:unit` 属于 URI 为 `http://www.bipm.fr/enus/3_SI/si.html` 的命名空间。然而，属性 `value` 不属于任何命名空间。

你可以控制解析器如何处理命名空间。默认情况下，Java XML 库的 DOM 解析器不是命名空间感知的。要开启命名空间处理，请调用 `DocumentBuilderFactory` 的 `setNamespaceAware` 方法：

点击此处查看代码图像

```java
factory.setNamespaceAware(true);
```

现在，工厂产生的所有构建器都支持命名空间。每个节点都有三个属性：

- `qualified name（限定名）`，带有前缀，由 `getNodeName`、`getTagName` 等返回。
- 命名空间 URI，由 `getNamespaceURI` 方法返回。
- `local name（本地名）`，不带前缀或命名空间，由 `getLocalName` 方法返回。

这是一个例子。假设解析器看到以下元素：

点击此处查看代码图像

```xml
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema">
```

它随后报告如下内容：

- Qualified name = `xsd:schema`
- Namespace URI = `http://www.w3.org/2001/XMLSchema`



- Local name = `schema`

---

![Image](img/00002.jpeg) 注意

如果关闭了命名空间感知，`getNamespaceURI` 和 `getLocalName` 将返回 `null`。

---

## org.w3c.dom.Node

- `String getLocalName()` 返回本地名（不带前缀），如果解析器不是命名空间感知的则返回 `null`。
- `String getNamespaceURI()` 返回命名空间 URI，如果节点不是命名空间的一部分则返回 `null`。

## javax.xml.parsers.DocumentBuilderFactory

- `boolean isNamespaceAware()`
- `void setNamespaceAware(boolean value)` 获取或设置工厂的 `namespaceAware` 属性。设置为 `true` 时，工厂生成的解析器感知命名空间。

### 3.6 流式解析器

DOM 解析器将整个 XML 文档读入树结构。对于大多数实际应用，DOM 工作良好。但如果文档很大且你的处理算法足够简单，可以在查看整个树的情况下分析节点，在这种情况下你应该使用流式解析器。

在接下来的章节中，我们将讨论提供的流式解析器：经典的 SAX 解析器和添加到 Java6 中更现代的 StAX 解析器。SAX 解析器使用事件回调，而 StAX 解析器提供对解析事件的迭代。后者通常更方便一点。

#### 3.6.1 使用 SAX 解析器

SAX 解析器在解析 XML 输入组件时报告事件，但它并不以任何方式存储文档——构建数据结构是事件处理器的任务。事实上，DOM 解析器是构建在 SAX 解析器之上的。它在接收解析事件时构建 DOM 树。

每当你使用 SAX 解析器时，都需要一个处理器来定义各种解析事件的操作。`ContentHandler` 接口定义了几个解析器在解析文档时执行的回调方法。这里是最重要的：

- `startElement` 和 `endElement` 在每次遇到起始标记或结束标记时调用。
- `characters` 在每次遇到字符数据时调用。
- `startDocument` 和 `endDocument` 分别调用一次，分别在文档开始和结束时。

例如，当解析以下片段时：

```xml
<font>
    <name>Helvetica</name>
    <size units="pt">36</size>
</font>
```

解析器执行以下回调：

1. `startElement`，元素名：`font`
2. `startElement`，元素名：`name`
3. `characters`，内容：`Helvetica`
4. `endElement`，元素名：`name`
5. `startElement`，元素名：`size`，属性：`units="pt"`
6. `characters`，内容：`36`
7. `endElement`，元素名：`size`
8. `endElement`，元素名：`font`

你的处理器需要重写这些方法，并在解析文件时执行你想的操作。本节末尾程序会打印 HTML 文件中所有的链接 `<a href=". . .">`。它简单地重写了处理器的 `startElement` 方法，以检查名称为 `a` 且属性名为 `href` 的链接。这对于实现“网络爬虫”（一个通过跟随链接访问越来越多的网页的程序）可能非常有用。

> ![Image](img/00002.jpeg) 备注
>
> HTML 不定是有效的 XML，许多网页偏离标准的 XML 很多，以至于示例程序将无法解析它们。然而，大多数 W3C 编写的页面都是 XHTML（一种符合标准 XML 的 HTML 方言）。你可以使用这些页面测试示例程序。例如，如果你运行：
>
> ```bash
> java SAXTest http://www.w3c.org/MarkUp
> ```
>
> 你将看到该页面所有链接的 URL 列表。

示例程序是使用 SAX 的良好范例。我们完全不在乎 `a` 元素出现在什么环境中，也没有必要存储树结构。

以下是获取 SAX 解析器的方法：

```java
SAXParserFactory factory = SAXParserFactory.newInstance();
SAXParser parser = factory.newSAXParser();
```

你现在可以处理文档了：

```java
parser.parse(source, handler);
```

在这里，`source` 可以是一个文件、URL 字符串或输入流。`handler` 属于 `DefaultHandler` 的子类。`DefaultHandler` 类为四个接口定义了空方法：

- `ContentHandler`
- `DTDHandler`
- `EntityResolver`
- `ErrorHandler`

示例程序定义了一个处理器，它重写了 `ContentHandler` 接口的 `startElement` 方法，以监控带有 `href` 属性的 `a` 元素：

```java
DefaultHandler handler = new DefaultHandler()
{
    public void startElement(String namespaceURI, String lname, String qname, Attributes attrs)
        throws SAXException
    {
        if (lname.equalsIgnoreCase("a") && attrs != null)
        {
            for (int i = 0; i < attrs.getLength(); i++)
            {
                String aname = attrs.getLocalName(i);
                if (aname.equalsIgnoreCase("href"))
                    System.out.println(attrs.getValue(i));
            }
        }
    }
};
```

`startElement` 方法有三个描述元素名称的参数。`qname` 参数报告格式为 `prefix:localname` 的限定名。如果开启了命名空间处理，那么 `namespaceURI` 和 `lname` 参数将提供命名空间和本地（未限定）名称。

与 DOM 解析器一样，命名空间处理默认关闭。要激活命名空间处理，请调用工厂类的 `setNamespaceAware` 方法：

```java
SAXParserFactory factory = SAXParserFactory.newInstance();
factory.setNamespaceAware(true);
SAXParser parser = factory.newSAXParser();
```

在这个程序中，我们处理另一个问题。XHTML 文件以一个包含 DTD 引用的标签开头，解析器会想要加载它。可以理解，W3C 并不乐意提供数十亿份类似 `www.w3.org/TR/xhtml1/xhtml1-strict.dtd` 的副本。在某段时间，他们完全拒绝了，但在本文写作期间，他们正以极缓慢的速度提供该 DTD。如果你不需要验证文档，只需调用：

```java
factory.setFeature("http://apache.org/xml/features/nonvalidating/load-external-dtd", false);
```

列表 `3.8` 包含了网络爬虫的代码。在本章稍后的部分，你将看到 SAX 的另一种用法。将非 XML 数据源转换为 XML 的简单方法是报告 XML 解析器会报告的 SAX 事件。详情请参见第 22 页第 3.8 节“XSL 转换”。

#### 列表 3.8：`sax/SAXTest.java`

```java
package sax;

import java.io.*;
import java.net.*;
import javax.xml.parsers.*;
import org.xml.sax.*;
import org.xml.sax.helpers.*;

/**
 * 此程序演示了如何使用 SAX 解析器。该程序打印 XHTML 页面的所有超链接。
 * 使用方法: java sax.SAXTest URL
 * @version 1.0 2001-09-29
 * @author Cay Horstmann
 */
public class SAXTest
{
    public static void main(String[] args) throws Exception
    {
        String url;
        if (args.length == 0)
        {
            url = "http://www.w3c.org";
            System.out.println("Using " + url);
        }
        else url = args[0];

        DefaultHandler handler = new DefaultHandler()
        {
            public void startElement(String namespaceURI, String lname, String qname,
                Attributes attrs)
            {
                if (lname.equals("a") && attrs != null)
                {
                    for (int i = 0; i < attrs.getLength(); i++)
                    {
                        String aname = attrs.getLocalName(i);
                        if (aname.equalsIgnoreCase("href"))
                            System.out.println(attrs.getValue(i));
                    }
                }
            }
        };

        SAXParserFactory factory = SAXParserFactory.newInstance();
        factory.setNamespaceAware(true);
        SAXParser parser = factory.newSAXParser();
        InputStream in = new URL(url).openStream();
        parser.parse(in, handler);
    }
}
```

在元素的开始或结束时调用。

![Image](img/00068.jpeg)

- `void characters(char[] data, int start, int length)`

  当解析器报告字符数据时调用。

![Image](img/00069.jpeg)

### org.xml.sax.Attributes 1.4

- `int getLength()`

  返回存储在此属性集合中的属性的数量。

- `String getLocalName(int index)`

  返回给定索引的属性的本地名称（不包含前缀），如果解析器不感知命名空间，则返回空字符串。

- `String getURI(int index)`

  返回给定索引属性的命名空间 URI，如果该节点不是命名空间的一部分或者解析器不感知命名空间，则返回空字符串。

- `String getQName(int index)`

  返回给定索引属性的限定名（包含前缀），如果解析器没有报告该限定名，则返回空字符串。

- `String getValue(int index)`
- `String getValue(String qname)`
- `String getValue(String uri, String lname)`

  从给定的索引、限定名或命名空间 URI + 本地名称返回属性值。如果值不存在，则返回 `null`。

### 3.6.2 使用 StAX 解析器

StAX 解析器是一个“拉取式解析器”（pull parser）。你不需要安装事件处理器，只需通过以下基础循环直接迭代事件即可：

```java
InputStream in = url.openStream();
XMLInputFactory factory = XMLInputFactory.newInstance();
XMLStreamReader parser = factory.createXMLStreamReader(in);
while (parser.hasNext())
{
   int event = parser.next();
   // 调用解析器方法获取事件详情
}
```

例如，当解析以下片段时：

```xml
<font>
    <name>Helvetica</name>
    <size units="pt">36</size>
</font>
```

解析器会产生以下事件：

1. `START_ELEMENT`，元素名：`font`
2. `CHARACTERS`，内容：空白
3. `START_ELEMENT`，元素名：`name`
4. `CHARACTERS`，内容：`Helvetica`
5. `END_ELEMENT`，元素名：`name`
6. `CHARACTERS`，内容：空白
7. `START_ELEMENT`，元素名：`size`
8. `CHARACTERS`，内容：`36`
9. `END_ELEMENT`，元素名：`size`
10. `CHARACTERS`，内容：空白
11. `END_ELEMENT`，元素名：`font`

要分析属性值，请调用 `XMLStreamReader` 类的相应方法。例如：

```java
String units = parser.getAttributeValue(null, "units");
```

获取当前元素的 `units` 属性。

默认情况下，启用了命名空间处理。你可以通过修改工厂来禁用它：

```java
XMLInputFactory factory = XMLInputFactory.newInstance();
factory.setProperty(XMLInputFactory.IS_NAMESPACE_AWARE, false);
```

列表 `3.9` 包含了使用 StAX 解析器实现的网络爬虫程序代码。如你所示，代码比等效的 SAX 代码简单，因为你不需要担心事件处理。

#### 列表 3.9：`stax/StAXTest.java`

```java
package stax;

import java.io.*;
import java.net.*;
import javax.xml.stream.*;

/**
 * 此程序演示了如何使用 StAX 解析器。程序会打印 XHTML 网页中的所有超链接。<br>
 * 使用方法: java stax.StAXTest URL
 * @author Cay Horstmann
 * @version 1.0 2007-06-23
 */
public class StAXTest
{
    public static void main(String[] args) throws Exception
    {
      String urlString;
      if (args.length == 0)
      {
         urlString = "http://www.w3.org";
         System.out.println("Using " + urlString);
      }
      else urlString = args[0];
      URL url = new URL(urlString);
      InputStream in = url.openStream();
      XMLInputFactory factory = XMLInputFactory.newInstance();
      XMLStreamReader parser = factory.createXMLStreamReader(in);
      while (parser.hasNext())
      {
         int event = parser.next();
         if (event == XMLStreamConstants.START_ELEMENT)
         {
            if (parser.getLocalName().equals("a"))
            {
               String href = parser.getAttributeValue(null, "href");
               System.out.println(href);
            }
         }
      }
    }
}
```



在元素的开始或结束时调用。

![Image](img/00068.jpeg)

- `void characters(char[] data, int start, int length)`

当解析器报告字符数据时调用。

![Image](img/00069.jpeg)

---

### `org.xml.sax.Attributes` 1.4

- `int getLength()`

  返回此属性集合中存储的属性数量。

- `String getLocalName(int index)`

  返回给定索引属性的本地名称（不包含前缀），如果解析器不感知命名空间，则返回空字符串。

- `String getURI(int index)`

  返回给定索引属性的命名空间 URI，如果该节点不是命名空间的一部分或者解析器不感知命名空间，则返回空字符串。

- `String getQName(int index)`

  返回给定索引属性的限定名（包含前缀），如果解析器没有报告该限定名，则返回空字符串。

- `String getValue(int index)`

- `String getValue(String qname)`

- `String getValue(String uri, String lname)`

  从给定的索引、限定名或命名空间 URI + 本地名称返回属性值。如果值不存在，则返回 `null`。

---

### 3.6.2 使用 StAX 解析器

StAX 解析器是一个“拉取式解析器”。你不需要安装事件处理器，只需通过以下基础循环直接迭代事件即可：

点击此处查看代码图片

```java
InputStream in = url.openStream();
XMLInputFactory factory = XMLInputFactory.newInstance();
XMLStreamReader parser = factory.createXMLStreamReader(in);
while (parser.hasNext())
{
   int event = parser.next();
   // 调用解析器方法获取事件详情
}
```

例如，当解析以下片段时：

点击此处查看代码图片

```xml
<font>
    <name>Helvetica</name>
    <size units="pt">36</size>
</font>
```

解析器产生以下事件：

1. `START_ELEMENT`，元素名：`font`
2. `CHARACTERS`，内容：空白
3. `START_ELEMENT`，元素名：`name`
4. `CHARACTERS`，内容：`Helvetica`
5. `END_ELEMENT`，元素名：`name`
6. `CHARACTERS`，内容：空白
7. `START_ELEMENT`，元素名：`size`
8. `CHARACTERS`，内容：`36`
9. `END_ELEMENT`，元素名：`size`
10. `CHARACTERS`，内容：空白
11. `END_ELEMENT`，元素名：`font`

要分析属性值，请调用 `XMLStreamReader` 类的相应方法。例如：

点击此处查看代码图片

```java
String units = parser.getAttributeValue(null, "units");
```

获取当前元素的 `units` 属性。

默认情况下，启用了命名空间处理。你可以通过修改工厂来禁用它：

点击此处查看代码图片

```java
XMLInputFactory factory = XMLInputFactory.newInstance();
factory.setProperty(XMLInputFactory.IS_NAMESPACE_AWARE, false);
```

`Listing 3.9` 包含了使用 StAX 解析器实现的网络爬虫程序代码。如你所示，代码比等效的 SAX 代码简单，因为你不需要担心事件处理。

**列表 3.9** `stax/StAXTest.java`

点击此处查看代码图片

```java
package stax;

import java.io.*;
import java.net.*;
import javax.xml.stream.*;

/**
 * 此程序演示了如何使用 StAX 解析器。程序会打印 XHTML 网页中的所有超链接。<br>
 * 使用方法: java stax.StAXTest URL
 * @author Cay Horstmann
 * @version 1.0 2007-06-23
 */
public class StAXTest
{
    public static void main(String[] args) throws Exception
    {
      String urlString;
      if (args.length == 0)
      {
         urlString = "http://www.w3.org";
         System.out.println("Using " + urlString);
      }
      else urlString = args[0];
      URL url = new URL(urlString);
      InputStream in = url.openStream();
      XMLInputFactory factory = XMLInputFactory.newInstance();
      XMLStreamReader parser = factory.createXMLStreamReader(in);
      while (parser.hasNext())
      {
         int event = parser.next();
         if (event == XMLStreamConstants.START_ELEMENT)
         {
            if (parser.getLocalName().equals("a"))
            {
               String href = parser.getAttributeValue(null, "href");
               System.out.println(href);
            }
         }
      }
    }
}
```

### 3.7 生成 XML 文档

你现在已经了解了如何编写读取 XML 的 Java 程序。现在让我们转向相反的过程：产生 XML 输出。当然，你可以通过简单地调用一系列 `print` 方法来编写 XML 文件，打印元素、属性和文本内容，但这并不是一个好主意。代码相当冗长，而且如果不注意属性值和文本内容中的特殊符号（如 `"` 或 `<`），很容易出错。

更好的方法是构建一个包含文档内容的 DOM 树，然后输出树的内容。接下来的章节将讨论细节。

#### 3.7.1 不带命名空间的文档

要构建 DOM 树，你从空文档开始。通过调用 `DocumentBuilder` 类的 `newDocument` 方法可以获取空文档：

```java
Document doc = builder.newDocument();
```

使用 `Document` 类的 `createElement` 方法来构造文档的元素：

点击此处查看代码图像

```java
Element rootElement = doc.createElement(rootName);

Element childElement = doc.createElement(childName);
```

使用 `createTextNode` 方法构建文本节点：

点击此处查看代码图像

```java
Text textNode = doc.createTextNode(textContents);
```

将根元素添加到文档，并将子节点添加到它们的父元素中：

点击此处查看代码图像

```java
doc.appendChild(rootElement);
rootElement.appendChild(childElement);
childElement.appendChild(textNode);
```

在构建 DOM 树时，你可能还需要设置元素属性。只需调用 `Element` 类的 `setAttribute` 方法即可：

点击此处查看代码图像

```java
rootElement.setAttribute(name, value);
```

#### 3.7.2 带命名空间的文档

如果你使用命名空间，创建文档的步骤略有不同。

首先，将构建器工厂设置为命名空间感知，然后创建构建器：

点击此处查看代码图像

```java
DocumentBuilderFactory factory = DocumentBuilderFactory.newInstance();
factory.setNamespaceAware(true);
builder = factory.newDocumentBuilder();
```

然后使用 `createElementNS` 代替 `createElement` 来创建任何节点：

点击此处查看代码图像

```java
String namespace = "http://www.w3.org/2000/svg";
Element rootElement = doc.createElementNS(namespace, "svg");
```

如果你的节点具有带有命名空间前缀的限定名，那么任何必要的 `xmlns` 前缀属性将自动创建。例如，如果你需要在 XHTML 中使用 SVG，可以像这样构建元素：

点击此处查看代码图像

```java
Element svgElement = doc.createElement(namespace, "svg:svg")
```

当元素被写入时，它会变为：

点击此处查看代码图像

```xml
<svg:svg xmlns:svg="http://www.w3.org/2000/svg">
```

如果你需要设置名称位于命名空间中的元素属性，请使用 `Element` 类的 `setAttributeNS` 方法：

点击此处查看代码图像

```java
rootElement.setAttributeNS(namespace, qualifiedName, value);
```

#### 3.7.3 写入文档

奇怪的是，将 DOM 树写入输出流并不是那么容易。最简单的方法是使用扩展样式表语言转换（XSLT） API。有关 XSLT 的更多信息，请参阅 3.8 节以及第 222 页上的“XSL 转换”。现在，请将下面的代码视为产生 XML 输出的魔咒。

我们对文档应用无操作转换，并捕获其输出。为了在输出中包含 `DOCTYPE` 节点，我们还需要将 `SYSTEM` 和 `PUBLIC` 标识符设置为输出属性。

点击此处查看代码图像

```java
// 构建无操作转换器
Transformer t = TransformerFactory.newInstance().newTransformer();
// 设置输出属性以获取 DOCTYPE 节点
t.setOutputProperty(OutputKeys.DOCTYPE_SYSTEM, systemIdentifier);
t.setOutputProperty(OutputKeys.DOCTYPE_PUBLIC, publicIdentifier);
// 设置缩进
t.setOutputProperty(OutputKeys.INDENT, "yes");
t.setOutputProperty(OutputKeys.METHOD, "xml");
t.setOutputProperty("{http://xml.apache.org/xslt}indent-amount", "2");
// 应用无操作转换并将输出发送到文件
t.transform(new DOMSource(doc), new StreamResult(new FileOutputStream(file)));
```

另一种方法是使用 `LSSerializer` 接口。要获取实例，你必须使用以下魔咒：

点击此处查看代码图像

```java
DOMImplementation impl = doc.getImplementation();
DOMImplementationLS implLS = (DOMImplementationLS) impl.getFeature("LS", "3.0");
LSSerializer ser = implLS.createLSSerializer();
```

如果你想要空格和换行，请设置此标记：

点击此处查看代码图像

```java
ser.getConfig().setParameter("format", true);
```

然后将文档转换为字符串：

点击此处查看代码图像

```java
String str = ser.serialize(doc);
```

如果你想将输出写入文件：

点击此处查看代码图像

```java
LSOutput out = implLS.createOutput();
out.setStream(file);
```

### 3.7.4 示例：生成 SVG

点击此处查看代码图像

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.0//EN" "http://www.w3.org/Graphics/SVG/1.0/svg">
<svg xmlns="http://www.w3.org/2000/svg" width="300" height="150">
  <rect x="10" y="10" width="100" height="50" fill="red"/>
  <rect x="10" y="70" width="100" height="50" fill="green"/>
  <rect x="10" y="130" width="100" height="50" fill="blue"/>
</svg>
```

正如你看到的，每个矩形都是一个 `rect` 节点。位置、宽度和填充颜色都是属性。

Image

SVG 大量使用属性。事实上，某些属性是复杂的。例如，这里有一个路径：

点击此处查看代码图像

```xml
<path d="M100 100 L 300 100 L 200 300 z"/>
```

`M` 表示“移动到”，“L”表示“连到”，而 `z` 表示“关闭路径”。显然，这种格式的设计者对使用 XML 来表示数据没有信心。在自己的 XML 格式中，你可能希望使用元素而不是复杂的属性。

Image

**图 3.6** 现代

点击此处查看代码图像

```xml
<svg xmlns="http://www.w3.org/2000/svg" width="300" height="150">
  <rect x="10" y="10" width="100" height="50" fill="red"/>
  <rect x="10" y="70" width="100" height="50" fill="green"/>
  <rect x="10" y="130" width="100" height="50" fill="blue"/>
</svg>
```

**列表 3.10**

```xml
<!DOCTYPE svg PUBLIC "-//W3C//DTD SVG 1.0//EN" "http://www.w3.org/Graphics/SVG/1.0/svg.dtd">
<svg xmlns="http://www.w3.org/2000/svg" width="300" height="150">
  <rect x="10" y="10" width="100" height="50" fill="red"/>
  <rect x="10" y="70" width="100" height="50" fill="green"/>
  <rect x="10" y="130" width="100" height="50" fill="blue"/>
</svg>
```

设置一个输出属性。标准输出属性的列表请参见 `www.w3.org/TR/xslt#output`。此处显示了最实用的属性：

![Image](img/00073.jpeg)

- `void transform(Source from, Result to)`

  转换 XML 文档。

`javax.xml.transform.dom.DOMSource` 1.4

- `DOMSource(Node n)`

  从给定的节点构造源。通常，`n` 是一个文档节点。

`javax.xml.transform.stream.StreamResult` 1.4

- `StreamResult(File f)`
- `StreamResult(OutputStream out)`
- `StreamResult(Writer out)`
- `StreamResult(String systemID)`

从文件、流、写入器或系统 ID（通常是相对或绝对 URL）构造流结果。

### 3.7.5 使用 StAX 写入 XML 文档

在这一节中，你已经了解了如何通过写入 DOM 树来生成 XML 文档。如果你对 DOM 树没有其他用途，那么这种方法的效率并不高。

StAX API 允许你直接写入 XML 树。从 `OutputStream` 构造一个 `XMLStreamWriter`：

点击此处查看代码图片



要生成 XML 头部，调用`writer.writeStartDocument()`。

然后调用`writer.writeStartElement(name)`。

通过调用添加属性：`writer.writeAttribute(name, value)`。

现在你可以再次调用`writeStartElement`来添加子元素，或使用以下方法写入字符：`writer.writeCharacters(text)`。

当你写完所有子节点后，调用`writer.writeEndElement()`，这会导致当前元素关闭。

要写入一个没有子元素的元素（例如 `<img . ./>`），请使用调用`writer.writeEmptyElement(name)`。

最后，在文档结束处调用`writer.writeEndDocument()`，此调用会关闭任何已打开的元素。

你仍然需要关闭`XMLStreamWriter`，并且你需要手动完成，因为`XMLStreamWriter`接口没有实现`AutoCloseable`接口。

与 DOM/XSLT 方法类似，你不担心属性值和字符数据中的字符转义问题。然而，可能会产生格式不正确的 XML，例如具有多个根节点的文档。此外，StAX 的当前版本不支持生成缩进输出。

程序示例 3.10 向你展示了写入 XML 的两种方法。示例 3.11 和 3.12 展示了用于矩形绘制的框架和组件类。

**示例 3.10** `write/XMLWriteTest.java`

```java
package write;

import java.awt.*;
import javax.swing.*;

/**
 * 此程序展示了如何写入 XML 文件。它保存了一个描述 SVG 格式现代绘图的文件。
 * @version 1.12 2016-04-27
 * @author Cay Horstmann
 */
public class XMLWriteTest
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() ->
        {
            JFrame frame = new XMLWriteFrame();
            frame.setTitle("XMLWriteTest");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}
```

**示例 3.11** `write/XMLWriteFrame.java`

```java
package write;

import java.io.*;
import java.nio.file.*;
import javax.swing.*;
import javax.xml.stream.*;
import javax.xml.transform.*;
import javax.xml.transform.dom.*;
import javax.xml.transform.stream.*;
import org.w3c.dom.*;

/**
 * 一个带有用于显示现代绘图组件的框架。
 */
public class XMLWriteFrame extends JFrame
{
    private RectangleComponent comp;
    private JFileChooser chooser;

    public XMLWriteFrame()
    {
        chooser = new JFileChooser();
        // 将组件添加到框架
        comp = new RectangleComponent();
        add(comp);
        // 设置菜单栏
        JMenuBar menuBar = new JMenuBar();
        setJMenuBar(menuBar);
        JMenu menu = new JMenu("File");
        menuBar.add(menu);
        JMenuItem newItem = new JMenuItem("New");
        menu.add(newItem);
        newItem.addActionListener(event -> comp.newDrawing());
        JMenuItem saveItem = new JMenuItem("Save with DOM/XSLT");
        menu.add(saveItem);
        saveItem.addActionListener(event -> saveDocument());
        JMenuItem saveStAXItem = new JMenuItem("Save with StAX");
        menu.add(saveStAXItem);
        saveStAXItem.addActionListener(event -> saveStAX());
        JMenuItem exitItem = new JMenuItem("Exit");
        menu.add(exitItem);
        exitItem.addActionListener(event -> System.exit(0));
        pack();
    }

    /**
     * 使用 DOM/XSLT 以 SVG 格式保存绘图。
     */
    public void saveDocument()
    {
        try
        {
            if (chooser.showDialog(this) != JFileChooser.APPROVE_OPTION) return;
            File file = chooser.getSelectedFile();
            Document doc = comp.buildDocument();
            Transformer t = TransformerFactory.newInstance().newTransformer();
            t.setOutputProperty(OutputKeys.DOCTYPE_SYSTEM, "http://www.w3.org/TR/2000/SVG-2000082/DTD/svg-2000082.dtd");
            t.setOutputProperty(OutputKeys.DOCTYPE_PUBLIC, "-W3C//DTD 2000082//EN");
            t.setOutputProperty(OutputKeys.INDENT, "yes");
            t.setOutputProperty(OutputKeys.METHOD, "xml");
            t.setOutputProperty("{http://xml.apache.org/xslt}indent-amount", "2");
            t.transform(new DOMSource(doc), new StreamResult(Files.newOutputStream(file.toPath())));
        }
        catch (TransformerException | IOException ex)
        {
            ex.printStackTrace();
        }
    }

    /**
     * 使用 StAX 以 SVG 格式保存绘图。
     */
    public void saveStAX()
    {
        if (chooser.showDialog(this) != JFileChooser.APPROVE_OPTION) return;
        File file = chooser.getSelectedFile();
        XMLOutputFactory factory = XMLOutputFactory.newInstance();
        try
        {
            XMLStreamWriter writer = factory.createXMLStreamWriter(Files.newOutputStream(file.toPath()));
            try
            {
                comp.writeDocument(writer);
            }
            finally
            {
                writer.close(); // Notloseable
            }
        }
        catch (XMLStreamException | IOException ex)
        {
            ex.printStackTrace();
        }
    }
}
```

```java
private static final Dimension PREFERRED_SIZE = new Dimension(300, 200);

private java.util.List<Rectangle2D> rects;
private java.util.List<Color> colors;
private Random generator;
private DocumentBuilder builder;

public RectangleComponent()
{
    rects = new ArrayList<>();
    colors = new ArrayList<>();
    generator = new Random();

    DocumentBuilderFactory factory = DocumentBuilderFactory.newInstance();
    factory.setNamespaceAware(true);
    try
    {
        builder = factory.newDocumentBuilder();
    }
    catch (ParserConfigurationException e)
    {
        e.printStackTrace();
    }
}

/**
 * 创建一个新的随机绘制。
 */
public void newDrawing()
{
    int n = 10 + generator.nextInt(20);
    rects.clear();
    colors.clear();
    for (int i = 1; i <= n; i++)
    {
        int x = generator.nextInt(getWidth());
        int y = generator.nextInt(getHeight());
        int width = generator.nextInt(getWidth() - x);
        int height = generator.nextInt(getHeight() - y);
        rects.add(new Rectangle(x, y, width, height));
        int r = generator.nextInt(256);
        int g = generator.nextInt(256);
        int b = generator.nextInt(256);
        colors.add(new Color(r, g, b));
    }
    repaint();
}

public void paintComponent(Graphics g)
{
    if (rects.size() == 0) newDrawing();
    Graphics2D g2 = (Graphics2D) g;

    // 绘制所有矩形
    for (int i = 0; i < rects.size(); i++)
    {
        g2.setPaint(colors.get(i));
        g2.fill(rects.get(i));
    }
}

/**
 * 创建当前绘制的 SVG 文档。
 * @return SVG 文档的 DOM 树
 */
public Document buildDocument()
{
    String namespace = "http://www.w3.org/2000/svg";
    Document doc = builder.newDocument();
    Element svgElement = doc.createElementNS(namespace, "svg");
    doc.appendChild(svgElement);
    svgElement.setAttribute("width", getWidth());
    svgElement.setAttribute("height", getHeight());
    for (int i = 0; i < rects.size(); i++)
    {
        Color c = colors.get(i);
        Rectangle2D r = rects.get(i);
        Element rectElement = doc.createElementNS(namespace, "rect");
        rectElement.setAttribute("x", r.getX());
        rectElement.setAttribute("y", r.getY());
        rectElement.setAttribute("width", r.getWidth());
        rectElement.setAttribute("height", r.getHeight());
        rectElement.setAttribute("fill", String.format("#06x", c.getRGB() & 0xFFFFFF));
        svgElement.appendChild(rectElement);
    }
    return doc;
}

/**
 * 写入当前绘制的 SVG 文档。
 * @param writer 文档目标
 */
public void writeDocument(XMLStreamWriter writer) throws XMLStreamException
{
    writer.writeStartDocument();
    writer.writeDTD("<!DOCTYPE svg PUBLIC \"-//W3C//DTD SVG 2000802//EN\" + \"http://www.w3.org/TR/2000/CR-SVG-20000802/DTD/svg-20000802.dtd\">");
    writer.writeStartElement("svg");
    writer.writeDefaultNamespace("http://www.w3.org/2000/svg");
    writer.writeAttribute("width", getWidth());
    writer.writeAttribute("height", getHeight());
    for (int i = 0; i < rects.size(); i++)
    {
        Color c = colors.get(i);
        Rectangle2D r = rects.get(i);
        writer.writeEmptyElement("rect");
        writer.writeAttribute("x", r.getX());
        writer.writeAttribute("y", r.getY());
        writer.writeAttribute("width", r.getWidth());
        writer.writeAttribute("height", r.getHeight());
    }
}
```

假设我们想要将带有员工记录的 XML 文件转换为 HTML 文档。考虑此输入文件：



```xml
<staff>
    <employee>
        <name>Carl Cracker</name>
点击此处查看代码图像
        <salary>75000</salary>
        <hiredate year="1987" month="12" day="15"/>
    </employee>
    <employee>
        <name>Harry Hacker</name>
        <salary>50000</salary>
        <hiredate year="1989" month="10" day="1"/>
    </employee>
    <employee>
        <name>Tony Tester</name>
        <salary>40000</salary>
        <hiredate year="1990" month="3" day="15"/>
    </employee>
</staff>
```

期望的输出是一个 HTML 表格：

点击此处查看代码图像

```html
<table border="1">
    <tr>
        <td>Carl Cracker</td><td>$75000.0</td><td>1987-12-15</td>
    </tr>
    <tr>
        <td>Harry Hacker</td><td>$50000.0</td><td>1989-10-1</td>
    </tr>
    <tr>
        <td>Tony Tester</td><td>$40000.0</td><td>1990-3-15</td>
    </tr>
</</table>
```

带有转换模板的样式表（此处为 XSLT）形式如下：

点击此处查看代码图像

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">
    <xsl:output method="html"/>
    template[1]
    template[2]
    . . .
</xsl:stylesheet>
```

在我们的示例中，`xsl:output` 元素指定方法为 HTML。其他有效的方法是 `xml` 和 `text`。这里是一个典型的模板：

点击此处查看代码图像

```xml
<xsl:template match="/staff/employee">
    <tr><xsl:apply-templates/></</tr>
</xsl:template>
```

`match` 属性的值是一个 XPath 表达式。该模板规定：每当你在 XPath 集合`/staff/employee`中看到一个节点时，都执行以下操作：

1. 输出字符串`<tr>`。
2. 在处理其子节点时继续应用模板。
3. 在完成所有子节点后，输出字符串`</tr>`。

换句话说，此模板在每个员工记录周围生成 HTML 表格行标记。

XSLT 处理器通过检查根元素开始处理。每当节点匹配其中一个模板时，它就会应用该模板。（如果多个模板匹配，将使用匹配程度最佳的一个；详细细节请参见`www.w3.org/TR/xslt`上的规范。）如果没有模板匹配的模板，处理器将执行默认操作。对于文本节点，默认操作是将内容包含在输出中。对于元素，默认操作是不创建任何输出，而是继续处理子节点。

这里是一个用于转换员工文件中`name`节点的模板：

点击此处查看代码图像

```xml
<xsl:template match="/staff/employee/name">
    <td><xsl:apply-templates//></td>
</xsl:template>
```

如你所见，该模板产生了`<td>. . .</td>`分隔符，并要求处理器递归地访问`name`元素的子节点。这里只有一个子节点——文本节点。当处理器访问该节点时，它会输出文本内容（当然，前提没有其他匹配的模板）。

如果你想将属性值复制到输出中，则需要多花一点功夫。这是一个示例：

点击此处查看代码图像

```xml
<xsl:template match="/staff/employee/hiredate">
    <td><xsl:value-of select="@year"/>-<xsl:value-of select="@month"/>-<xsl:value-of select="@day"/></td>
</xsl:template>
```

在处理`hiredate`节点时，此模板输出：

1. 字符串`<td>`。
2. `year`属性的值。
3. 一个连字符。
4. `month`属性的值。
5. 一个连字符。
6. `day`属性的值。
7. 字符串`</td>`。

`xsl:value-of`语句计算节点的值。`select`属性指定要选择的内容。在这种情况下，`xsl:value-of`计算节点的值。`xsl:value-of`语句计算节点的值。`select`属性指定要选择的内容。在这种情况下，`xsl:value-of`计算节点的值。`xsl:value-of`语句计算节点的值。`select`属性指定要选择的内容。在这种情况下，`xsl:value-of`计算节点的值。`xsl:value-of`语句计算节点的值。`select`属性指定要选择的内容。在这种情况下，`xsl:value-of`计算节点的值。`xsl:value-of`语句计算节点的值。`select`属性指定要选择的内容。在这种情况下，`xsl:value-of`计算节点的值。`xsl:value-of`语句计算节点的值。`select`属性指定要选择的内容。在这种情况下，`xsl:value-of`计算节点的值。`xsl:value-of`语句计算节点的值。`select`属性指定要选择的内容。在这种情况下，`xsl:value-of`计算节点的值。`xsl:value-of`语句计算节点的值。`select`属性指定要选择的内容。在这种情况下，`xsl:value-of`计算节点的值。`xsl:value-of`语句计算节点的值。`select`属性指定要选择的内容。在这种情况下，`xsl:value-of`计算节点的值。`xsl:value-of`语句计算节点的值。`select`属性指定要选择的内容。在这种情况下，`xsl:value-of`计算节点的值。`xsl:value-of`语句计算节点的值。`select`属性指定要选择的内容。在这种情况下，`xsl:value-of`计算节点的值。`xsl:value-of`语句计算节点的值。`select`属性指定要选择的内容。在这种情况下，`xsl:value-of`计算节点的值。`xsl:value-of`语句计算节点的值。`select`属性指定要选择的内容。。，，`xsl:value-of`计算节点`。`xsl:value-of`value-of```select`属性。要。`。在这种情况下，`xsl:value-of`。节点。。`xsl:value-of`计算节点的值。`select`属性。要选择`。。情况下，`xsl:value-of`节点`。`xsl:value-of`-节点。。`select`属性属性。。`。。。，，，`xsl:value-of`节点`。`xsl:value-of`节点`。`select`属性。。，，`xsl:value-of`-value-of-。`select`属性。。，`xsl:value-of`节点`。`xsl:value-of`节点`。`select`属性。。，，`xsl:value-of`节点`。`value-of`。。`select`属性。。-。`xsl:value-of`节点`。-value-of-。`xsl:value-of`。。，`xsl:value-of`节点`。`xsl:value-of`节点`。`select`属性。。，`xsl:value-of`节点`。`xsl:value-of`节点`。`select`属性。。，`xsl:value-of`节点`。-





```java
t.transform(new SAXSource(new EmployeeReader(),
    new InputSource(new FileInputStream(filename))), result);
```

这是一个将非 XML 遗留数据转换为 XML 的巧妙技巧。当然，大多数 XSLT 可能已经拥有了 XML 输入数据，你只需要在`StreamSource`上直接调用`transform`方法即可：

点击此处查看代码图片

```java
t.transform(new StreamSource(file), result);
```

转换结果是一个实现了`Result`接口的类对象。Java 库提供了三个类：

点击此处查看代码图片

- `DOMResult`
- `SAXResult`
- `StreamResult`

要将结果存储在 DOM 树中，请使用`DocumentBuilder`生成一个新的文档节点并将其封装到`DOMResult`中：

点击此处查看代码图片

```java
Document doc = builder.newDocument();

t.transform(source, new DOMResult(doc));
```

要将输出保存到文件中，请使用`StreamResult`：

点击此处查看代码图片

```java
t.transform(source, new StreamResult(file));
```

Listing 3.15 包含了完整的源代码。

### 列表 3.13 `transform/makehtml.xsl`

点击此处查看代码图片

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>

<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">

    <xsl:output method="html"/>

    <xsl:template match="/staff">

        <table border="1"><xsl:apply-templates/></table>

    </xsl:template>

    <xsl:template match="/staff/employee">

        <tr><xsl:apply-templates/></</tr>>

    </xsl:template>

    <xsl:template match="/staff/employee/name">

        <td><xsl:apply-templates/></td>

    </xsl:template>

    <xsl:template match="/staff/employee/salary">

        <td>$<xsl:apply-templates/></td>

    <///xsl:template>

    <xsl:template match="/staff/employee/hiredate">

        <td><xsl:value-of select="@year"/>-<xsl:value-of select="@month"/>-<xsl:value-of select="@day"/></td>

    </xsl:template>

</xsl:stylesheet>
```

### 列表 3.14 `transform/makeprop.xsl`

点击此处查看代码图片

```xml
<?xml version="1.0"?>

<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">

    <xsl:output method="text" omit-xml-declaration="yes"/>

    <xsl:template match="/staff/employee">

        employee.<xsl:value-of select="position()"/>.name=<xsl:value-of select="name/text()"/>

        employee.<xsl:value-of select="position()"/>.salary=<xsl:value-of select="salary/text()"/>

        employee.<xsl:value-of select="position()"/>.hiredate=<xsl:value-of select="hiredate/@year"/>-<xsl:value-of select="hiredate/@month"/>-<xsl:value-of select="hiredate/@day"/>

    </xsl:template>

</xsl:stylesheet>
```

### 列表 3.15 `transform/TransformTest.java`

点击此处查看代码图片

```java
package transform;

import java.io.*;
import java.nio.file.*;
import java.util.*;

import javax.xml.transform.*;
import javax.xml.transform.sax.*;
import javax.xml.transform.stream.*;

import org.xml.sax.*;
import org.xml.sax.helpers.*;

/**
 * 此程序演示了 XSL 转换。它对一组记录应用了转换。
 * 这些记录存储在 employee.dat 文件中，并转换为 XML 格式。
 * 在命令行上指定样式表，例如：
 * java TransformTest transform/makeprop.xsl
 * @version 1.0 2016-4-27
 * @author Caymann
 */
public class TransformTest {

    public static void main(String[] args) throws Exception {
        Path path;

        if (args.length > 0) path = Paths.get(args[0]);
        else path = Paths.get("transform", "makehtml.xsl");

        try (InputStream styleIn = Files.newInputStream(path)) {
            StreamSource styleSource = new StreamSource(styleIn);
            Transformer t = TransformerFactory.newInstance().newTransformer(styleSource);

            t.setOutputProperty(OutputKeys.INDENT, "yes");
            t.setOutputProperty(OutputKeys.METHOD, "xml");
            t.setOutputProperty("{http://xml.apache.org/xslt}indent-amount", "2");

            try (InputStream docIn = Files.newInputStream(Paths.get("transform", "employee.dat"))) {
                t.transform(
                    new SAXSource(new EmployeeReader(), new InputSource(docIn)),
                    new StreamResult(System.out)
                );
            }
        }
    }
}

/**
 * 此类读取扁平文件 employee.dat 并报告 SAX 解析器事件，
 * 以模拟解析一个 XML 文件。
 */
class EmployeeReader implements XMLReader {

    private ContentHandler handler;

    public void parse(InputSource source) throws IOException, SAXException {
        InputStream stream = source.getByteStream();
        BufferedReader in = new BufferedReader(new InputStreamReader(stream));
        String rootElement = "staff";
        AttributesImpl atts = new AttributesImpl();

        if (handler == null) throw new SAXException("No content handler");
```



```java
handler.startDocument();

handler.startElement(rootElement, null, atts);

String line;

while ((line = in.readLine()) != null) {
    handler.startElement("employee", null, atts);

    StringTokenizer t = new StringTokenizer(line, "|");

    handler.startElement("name", null, atts);

    String s = t.nextToken();

    handler.characters(s.toCharArray(), 0, s.length());

    handler.endElement("name");

    handler.startElement("salary", null, atts);

    s = t.nextToken();

    handler.characters(s.toCharArray(), 0, s.length());

    handler.endElement("salary");

    atts.addAttribute("year", "CDATA", t.nextToken());
    atts.addAttribute("month", "CDATA", t.nextToken());
    atts.addAttribute("day", "CDATA", t.nextToken());

    handler.startElement("hiredate", null, atts);

    handler.endElement("hiredate");

    atts.clear();

    handler.endElement("employee");
}

handler.endElement(rootElement);

handler.endDocument();
}

public void setContentHandler(ContentHandler newValue) {
    handler = newValue;
}

public ContentHandler getContentHandler() {
    return handler;
}

// 以下方法仅为空占位实现

public void parse(String systemId) throws IOException, SAXException {}

public void setErrorHandler(ErrorHandler handler) {}

public ErrorHandler getErrorHandler() {
    return null;
}

public void setDTDHandler(DTDHandler handler) {}

public DTDHandler getDTDHandler() {
    return null;
}

public void setEntityResolver(EntityResolver resolver) {}

public EntityResolver getEntityResolver() {
    return null;
}

public void setProperty(String name, Object value) {}

public Object getProperty(String name) {
    return null;
}
}
```

```java
public void setFeature(String name, boolean value) {}

public boolean getFeature(String name) {
    return false;
}
}
```

### `javax.xml.transform.TransformerFactory` 1.4

- `Transformer newTransformer(Source styleSheet)`

返回一个从给定源读取样式表的 `Transformer` 类的实例。

### `javax.xml.transform.stream.StreamSource` 1.4

- `StreamSource(File f)`
- `StreamSource(InputStream in)`
- `StreamSource(Reader in)`
- `StreamSource(String systemID)`

从文件、流、读取器或系统 ID（通常是相对路径或绝对 URL）构建一个流式源。

### `javax.xml.transform.sax.SAXSource` 1.4

- `SAXSource(XMLReader reader, InputSource source)`

构建一个 SAX 源，从给定的输入源获取数据并使用指定的读取器解析输入。

### `org.xml.sax.XMLReader` 1.4

- `void setContentHandler(ContentHandler handler)`

设置处理器，在解析输入时，解析事件会通知该处理器。

- `void parse(InputSource source)`

从给定的输入源解析输入，并将解析事件发送给内容处理器。

### `javax.xml.transform.dom.DOMResult` 1.4

- `DOMResult(Node n)`

从给定的节点构建一个源。通常，`n` 是一个新的文档节点。

### `org.xml.sax.helpers.AttributesImpl` 1.4

- `void addAttribute(String uri, String lname, String qname, String type, String value)`

向此属性集合添加一个属性。

![Image](img/00075.jpeg)

- `void clear()`

从此属性集合中移除所有属性。

本示例结束了我们对 Java 库中 XML 支持的讨论。你现在应该对 XML 的主要优势有一个良好的认识——特别是在自动化解析和验证方面，以及作为一种强大的转换机制。当然，只有当你设计好 XML 格式时，这些技术才能为你发挥作用。你需要确保格式足够丰富以表达你所有的业务需求，确保它们随时间推保持稳定，并且你的业务伙伴愿意接受你的 XML 文档。这些问题可能比处理解析器、DTD 或转换要挑战得多。

在下一章中，我们将讨论 Java 平台上的网络编程，从网络套接字的基础开始，然后转向电子邮件和万维网网的高级协议。

## 第 4 章：网络编程

### 本章内容

- 4.1 连接到服务器
- 4.2 实现服务器
- 4.3 可中断套接字
- 4.4 获取 Web 数据
- 4.5 发送电子邮件

本章将从回顾基础网络概念开始，然后编写连接网络服务的 Java 程序。我们将向你展示如何实现网络客户端和服务器。最后，你将看到如何从 Java 程序发送电子邮件，以及如何从 Web 服务器上采集信息。

### 4.1 连接到服务器

在接下来的节中，你将连接到服务器，首先通过手动和使用 `telnet` 连接，然后通过 Java 程序连接。

#### 4.1.1 使用 Telnet

`telnet` 程序是网络编程的极佳调试工具。你应该能够通过在命令行 shell 中输入 `telnet` 来启动它。

![Image](img/00002.jpeg)

> **备注**
>
> 在 Windows 中，你需要激活 `telnet`。进入控制面板，选择“程序”，点击“启用或关闭 Windows 功能”，并勾选“Telnet 客户端”复选框。Windows 防火墙还会阻止我们在本章中使用的许多网络端口；你可能需要管理员账户来解除这些阻止。

你可能用过 `telnet` 连接到远程计算机，但你也可以用它与 Internet 主机提供的其他服务进行通信。以下是一个你可以操作的示例。输入：

```bash
telnet time-a.nist.gov 13
```

如图 4.1 所示，你应该得到类似如下的返回：

```text
57488 16-04-10 04:23:00 50 0 0 610.5 UTC(NIST) *
```

![Image](img/00076.jpeg)

**图 4.1** “时间”服务的输出

发生了什么？你连接到了大多数 UNIX 机器上持续运行的“时间”服务。你连接的特定服务器由美国国家标准与技术研究院（NIST）运行，提供铯原子钟的测量值。（当然，由于网络延迟，报告的时间并不完全准确。）

按照惯例，“时间”服务始终连接到“端口”号 13。

![Image](img/00002.jpeg)

> **备注**
>
> 在网络术语中，端口不是物理设备，而是一种促进服务器与客户端之间通信的抽象（见图 4.2）。

![Image](img/00077.jpeg)

**图 4.2** 客户端连接到服务器

服务器在远程机器上持续运行，等待任何想要与端口 13 聊天的网络流量。

```java
String line = in.nextLine();
System.out.println(line);
}
}
}
```

这个简单程序的关键语句如下：

```java
Socket s = new Socket("time-a.nist.gov", 13);
InputStream inStream = s.getInputStream();
```

第一行代码打开了一个套接字（socket），它是一种网络软件抽象，允许程序与外部进行通信。我们将远程地址和端口号传递给套接字构造函数。如果连接失败，将抛出一个 `UnknownHostException`。如果发生其他问题，则会抛出一个 `IOException`。由于 `UnknownHostException` 是 `IOException` 的子类，且这是一个示例程序，我们只需捕获父类即可。

一旦套接字打开，`java.net.Socket` 中的 `getInputStream()` 方法返回一个 `InputStream` 对象，你可以像使用任何其他流一样使用它。一旦获取了流，此程序就会将每行输入打印到标准输出。此过程一直持续，直到流结束且服务器断开连接。

此程序仅适用于非常简单的服务器，例如“时间”服务。在更复杂的网络程序中，客户端向服务器发送请求数据，而服务器可能在响应结束时不立即断开连接。你将在本章的几个示例中看到如何实现这种行为。

`Socket` 类非常悦用且易于使用，因为 Java 库隐藏了建立网络连接和跨其发送数据的复杂性。

`java.net` 包本质上为你提供了与处理文件操作时完全相同的编程接口。

![Image](img/00002.jpeg)

> **注意**
>
> 在本书中，我们只涵盖了传输控制协议（TCP）。Java 平台还支持用户数据报协议（UDP），它可以用于发送数据包（也称为数据报，datagrams），且其开销比 TCP 小得多。缺点是数据包不需要按顺序交付给接收端应用程序，甚至可能被完全丢弃。将数据包排序以及请求重传丢失的数据包由接收方决定。UDP 非常适用于可以容忍丢包的应用——例如音频或视频流或连续测量值。

### `java.net.Socket` 1.0

- `Socket(String host, int port)` 构建一个套接字以连接到指定的主机和端口。
- `InputStream getInputStream()`
- `OutputStream getOutputStream()` 获取从套接字读取数据或向套接字写入数据的流。

### 4.1.3 Socket 超时

从套接字读取数据会阻塞，直到数据可用。如果主机不可达，你的应用程序将等待很长时间，你只能听命于底层操作系统最终超时。

你可以决定对于你的特定应用程序哪个超时值是合理的。然后，调用 `setSoTimeout()` 方法设置超时值（毫秒）。

```java
Socket s = new Socket(. . .);

s.setSoTimeout(10000); // 10 秒后超时
```

如果为套接字设置了超时值，当在操作完成工作之前达到超时时，所有后续的读、写操作都将抛出 `SocketTimeoutException`。你可以捕获该异常并对超时做出反应。

```java
try {
    InputStream in = s.getInputStream(); // 从 in 读取
    . . .
} catch (InterruptedIOException exception) {
    // 对超时做出反应
}
```

你还需要解决一个额外的超时问题。构造函数 `Socket(String host, int port)` 可能会无限阻塞直到建立与主机的初始连接。

你可以通过先构造一个未连接的套接字，然后带有超时进行连接来解决这个问题：

```java
Socket s = new Socket();

s.connect(new InetSocketAddress(host, port), timeout);
```

有关如何允许用户随时中断套接字连接，请参阅 p. 250 上的第 4.3 节“可中断的套接字（Interruptible Sockets）”。

### `java.net.Socket` 1.0

- `Socket()` **1.1** 创建一个尚未连接的套接字。
- `void connect(SocketAddress address)` **1.4** 将此套接字连接到指定的地址。
- `void connect(SocketAddress address, int timeoutInMilliseconds)` **1.4** 将此套接字连接到指定的地址，或者在时间间隔过期后返回。
- `void setSoTimeout(int timeoutInMilliseconds)` **1.1** 设置此套接字读请求的阻塞时间。如果超时，将抛出 `InterruptedIOException`。
- `boolean isConnected()` **1.4** 如果套接字已连接则返回 `true`。
- `boolean isClosed()` **1.4** 如果套接字已关闭则返回 `true`。

### 4.1.4 IP 地址

通常你不需要太担心 IP 地址——即由 4 字节（对于 IPv6 为 16 字节）组成的数值型主机地址，例如 `129.6.15.28`。然而，如果你需要在主机名和 IP 地址之间进行转换，可以使用 `InetAddress` 类。

`java.net` 包支持 IPv6 地址，只要主机操作系统支持。静态方法 `getByName()` 返回主机的 `InetAddress` 对象。例如，`InetAddress address = InetAddress.getByName("time-a.gov")` 返回一个封装了 `129.6.15.28` 的 `InetAddress` 对象。你可以通过 `getAddress()` 方法访问字节。

某些主机名对应多个 IP 地址以便负载均衡。例如，在编写时，`google.com` 对应十二个地址。访问时随机选择一个。你可以通过 `getAllByName()` 获取所有主机。

最后，你有时需要本地主机地址。如果你只需请求 `localhost`，你总是得到回环地址 `127.0.0.1`，它无法被他人使用。相反，使用静态方法 `getLocalHost()` 获取本地主机地址。

列表 4.2 是一个简单的程序，如果你不指定任何命令行参数，它将打印本地主机的 IP 地址；如果你在命令行指定了主机名，它将打印另一个主机的所有 IP 地址，例如 `java inetAddress/InetAddressTest google.com`。

```java
package inetAddress;

import java.io.*;
import java.net.*;

/**
 * 此程序演示了 InetAddress 类。提供主机名作为命令行参数，
 * 或在不带命令行参数运行时查看本地主机地址。
 * @version 1.02 2012-06-05
 * @author Cay Horstmann
 */
public class InetAddressTest {
    public static void main(String[] args) throws IOException {
        if (args.length > 0) {
            String host = args[0];
```

```java
InetAddress[] addresses = InetAddress.getAllByName(host);
```



```java
for (InetAddress a : addresses) {
    System.out.println(a);
} else {
    InetAddress localHostAddress = InetAddress.getLocalHost();
    System.out.println(localHostAddress);
}
```

### `java.net.InetAddress` 1.0

- `static InetAddress getByName(String host)`  
  构造一个 `InetAddress`...
- `static InetAddress[] getAllByName(String host)`  
  为给定的主机名构造一个 `InetAddress` 或所有 Internet 地址数组。
- `static InetAddress getLocalHost()`  
  为本地主机构造一个 `InetAddress`。
- `byte[] getAddress()`  
  返回一个包含数值地址的字节数组。
- `String getHostAddress()`  
  返回一个用点分隔的进制数字字符串，例如 `"129.6.15.28"`。
- `String getHostName()`  
  返回主机名。

### 4.2 实现服务器

现在我们已经实现了一个从 Internet 接收数据的基础网络客户端，让我们来编写一个可以向客户端发送信息的简单服务器。在上一节中，我们已经实现了一个从 Internet 接收数据的基础网络客户端。在接下来的章节中，我们将编写一个可以向客户端发送信息的简单服务器。

#### 4.2.1 服务端套接字（Server Sockets）

服务器程序启动后会等待客户端连接其端口。对于我们的示例程序，我们选择了端口号 8189，它没有被任何标准服务使用。`ServerSocket` 类建立了一个套接字。在我们的情况下，命令

```java
ServerSocket s = new ServerSocket(8189);
```

建立了一个监控 8189 端口的服务器。命令

```java
Socket incoming = s.accept();
```

告诉程序无限等待，直到客户端连接到该端口。一旦有人通过在网络发送正确的请求连接到此端口，该方法将返回一个表示已建立连接的 `Socket` 对象。你可以使用此对象来获取输入和输出流，如下代码所示：

```java
InputStream inStream = incoming.getInputStream();
OutputStream outStream = incoming.getOutputStream();
```

服务器发送到服务器输出流的所有内容将成为客户端程序的输入，而客户端程序的所有输出都会进入服务器的输入流。

在本章的所有示例中，我们都通过套接字传输文本。因此，我们将流转换为扫描器（Scanner）和写入器（Writer）。

```java
Scanner in = new Scanner(inStream, "UTF-8");

PrintWriter out = new PrintWriter(
    new OutputStreamWriter(outStream, "UTF-8"),
    true /* autoFlush */);
```

给客户端发送一个问候：

```java
out.println("Hello! Enter BYE to exit.");
```

当你使用 `telnet` 连接到端口 8189 服务器程序时，你会在终端屏幕上看到这个问候。

在这个简单的服务器中，我们只是逐行读取客户端的输入并将其回显（echo）。这证明了程序接收到了输入。一个真实的服务器显然会根据输入计算并返回答案。

```java
String line = in.nextLine();

out.println("Echo: " + line);

if (line.trim().equals("BYE")) done = true;
```

最后，我们关闭了传入的套接字。

```java
incoming.close();
```

就是这些了。每个服务器程序（例如 HTTP Web 服务器）都会持续执行此循环：

1. 它通过输入数据流从客户端接收命令（“get 给我这条信息”）。
2. 它解码客户端命令。
3. 它收集客户端请求的信息。
4. 它通过输出数据流将信息发送给客户端。

**代码列表 4.3** `server/EchoServer.java`

```java
package server;

import java.io.*;
import java.net.*;
import java.util.*;

/**
 * 此程序实现了一个简单的服务器，它监听 8189 端口并回显
 * 所有客户端的输入。
 * @version 1.2 2022-05-19
 * @author Cay
 */
public class EchoServer {
    public static void main(String[] args) throws IOException {
        // 建立服务器套接字
        try (ServerSocket s = new ServerSocket(8189)) {
            // 等待客户端连接
            try (Socket incoming = s.accept()) {
                InputStream inStream = incoming.getInputStream();
                OutputStream outStream = incoming.getOutputStream();

                try (Scanner in = new Scanner(inStream, "UTF-8")) {
                    PrintWriter out = new PrintWriter(
                        new OutputStreamWriter(outStream, "UTF-8"),
                        true /* autoFlush */);

                    out.println("Hello! Enter BYE to exit.");

                    // 回显客户端输入
                    boolean done = false;
                    while (!done && in.hasNextLine()) {
                        String line = in.nextLine();
                        out.println("Echo: " + line);

                        if (line.trim().equals("BYE")) done = true;
                    }
                }
            }
        }
    }
}
```

#### 4.2.2 服务多个客户端

前面的示例中的简单服务器存在一个问题。假设我们允许多个客户端同时连接到我们的服务器。通常，服务器持续运行在服务器计算机上，来自 Internet 各地的客户端可能想同时使用它。拒绝多个连接允许任何一个客户端通过长时间连接来垄断服务。我们可以通过线程的魔力做得更好。

每当我们知道程序建立了新的套接字连接时——也就是说，每当 `accept()` 调用返回一个套接字时——我们都会启动一个新线程来处理服务器与*该*客户端之间的连接。主程序将返回并等待下一次连接。为了实现这一点，服务器的主循环应该如下所示：

`ThreadedEchoHandler` 类实现了 `Runnable` 接口，并在其 `run` 方法包含了与客户端的通信循环。

点击此处查看代码图片

```java
class ThreadedEchoHandler implements Runnable {
    . . .

    public void run() {
        try (InputStream inStream = incoming.getInputStream();
             OutputStream outStream = incoming.getOutputStream()) {
            Process input and send response
        } catch (IOException e) {
            Handle exception
        }
    }
}
```

当每个连接启动一个新线程时，多个客户端同时连接到服务器。你可以轻松地测试这一点。

1. 编译并运行服务器程序（Listing 4.4）。
2. 打开几个 telnet 窗口，如图 4.5 所示。

![Image](img/00080.jpeg)

**图 4.5** 多个同时通信的 telnet 窗口

3. 在窗口之间切换并输入命令。注意，你可以同时通过所有窗口进行通信。
4. 完成后，切换到启动服务器程序的窗口，并按下 `Ctrl+C` 将其杀死。

---

![Image](img/00002.jpeg)

**注意**

在此程序中，我们为每个连接创建了一个独立的线程。这种方法对于高性能服务器来说并不理想。你可以通过使用 `java.nio` 包的特性来实现更高的服务器吞吐量。更多信息请参阅 `www.ibm.com/developerworks/java/library/j-javaio`。

---

**Listing 4.4** `threaded/ThreadedEchoServer.java`

点击此处查看代码图片

```java
1   package threaded;

2

3   import java.io.*;

4   import java.net.*;

5   import java.util.*;

6

7   /**

8    * 此程序实现了一个多线程服务器，监听 8189 端口并回显

9    * 所有客户端的输入。

10   * @author Cay Horstmann

11   * @version 1.22 2016-04-27

12   */

13   public class ThreadedEchoServer

14   {

15      public static void main(String[] args )

16      {

17          try (ServerSocket s = new ServerSocket(8189))

18          {

19              int i = 1;

20

21              while (true)

22              {

23                  Socket incoming = s.accept();

24                  System.out.println("Spawning " + i);

25                  Runnable r = new ThreadedEchoHandler(incoming);

26                  Thread t = new Thread(r);

27                  t.start();

28                  i++;

29              }

30          }

31          catch (IOException e)

32          {

33              e.printStackTrace();

34          }

35      }

36  }

37

38  /**

39   * 此类处理一个服务器连接的客户端输入

40   */

41  class ThreadedEchoHandler implements Runnable

42  {

43      private Socket incoming;

44

45      /**

46       构造一个处理器。

47       @param incomingSocket 输入的 socket

48      */

49      public ThreadedEchoHandler(Socket incomingSocket)

50      {

51          incoming = incomingSocket;

52      }

53

54      public void run()

55      {

56          try (InputStream inStream = incoming.getInputStream();

57               OutputStream outStream = incoming.getOutputStream())

58          {

59              Scanner in = new Scanner(inStream, "UTF-8");

60              PrintWriter out = new PrintWriter(

61                  new OutputStreamWriter(outStream, "UTF-8"),

62                  true /* autoFlush */);

63

64              out.println( "Hello! Enter BYE to exit." );

65

66              // 回显客户端输入

67              boolean done = false;

68              while (!done && in.hasNextLine())

69              {

70                  String line = in.nextLine();

71                  out.println("Echo: " + line);

72                  if (line.trim().equals("BYE"))

73                    done = true;

74              }

75          }

76          catch (IOException e)

77          {

78              e.printStackTrace();

79          }

80      }

81  }
```



#### 4.2.3 半关闭（Half-Close）

“半关闭”允许 socket 连接的一端在终止输出的同时仍接收数据。这里有一个典型场景：你向服务器传输数据，但在开始时你并不知道自己有多少量数据。然而，如果你关闭了 socket，就会丢失输入。

- `shutdownOutput()` 设置输出流为“end of stream”。
- `shutdownInput()` 设置输入流为“end of stream”。
- `isOutputShutdown()` 返回 `true` 表示输出已关闭。
- `isInputShutdown()` 返回 `true` 表示输入已关闭。

### 4.3 可中断的 socket

当你连接到 socket 时，当前线程会阻塞，直到连接建立或超时。同样，当你通过 socket 读取或写入数据时，当前线程会阻塞，直到操作成功或超时。

在交互式应用程序中，你希望给用户一个取消看似无响应的连接的机会。然而，如果线程在无响应的 socket 上阻塞，无法调用`interrupt`来解除阻塞。

要中断 socket 操作，请使用`SocketChannel`，它是`java.nio`包的一个特性。按如下方式打开`SocketChannel`：

```java
SocketChannel channel = SocketChannel.open(new InetSocketAddress(host, port));
```

通道没有关联流。相反，它有`read`和`write`方法，这些方法使用了`Buffer`对象。（有关 NIO 缓冲器的更多信息请参见第 2 章。）

如果你不想处理缓冲区，可以使用`Scanner`类从`SocketChannel`读取，因为`Scanner`有一个带有`ReadableByteChannel`参数的构造函数：

```java
Scanner in = new Scanner(channel, "UTF-8");
```

要将通道转换为输出流，使用静态方法`Channels.newOutputStream`：

```java
OutputStream outStream = Channels.newOutputStream(channel);
```

这就是你需要做的一切。每当线程在打开、读取或写入操作期间被中断时，操作不会阻塞，而是以异常的方式终止。

Listing 4.5 中的程序对比了可中断套字和阻塞套字。服务器发送数字，并在发送第十个数字后假装被卡住。点击任意一个按钮都会启动一个线程连接到服务器并打印输出。第一个线程使用可中断套字；第二个线程使用阻塞套字。如果你在前十个数字内点击`Cancel`按钮，你可以中断任意线程。

然而，在第十个数字之后，你只能中断第一个线程。第二个线程将一直阻塞，直到服务器最终关闭连接（参见图 4.6）。

![Image](img/00081.jpeg)

**图 4.6** 中断 socket

**Listing 4.5** `interruptible/InterruptibleSocketTest.java`

```java
package interruptible;

import java.awt.*;

import java.awt.event.*;

import java.util.*;

import java.net.*;

import java.io.*;

import java.nio.channels.*;

import javax.swing.*;

/**
 * 此程序展示了如何中断 socket 通道。
 * @author Cay Horstmann
 * @version 1.04 2016-04-27
 */

public class InterruptibleSocketTest
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() ->
            {
                JFrame frame = new InterruptibleSocketFrame();
                frame.setTitle("InterruptibleSocketTest");
                frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
                frame.setVisible(true);
            });
    }
}

class InterruptibleSocketFrame extends JFrame
{
    private Scanner in;
    private JButton interruptibleButton;
    private JButton blockingButton;
    private JButton cancelButton;
    private JTextArea messages;
    private TestServer server;
    private Thread connectThread;

    public InterruptibleSocketFrame()
    {
        JPanel northPanel = new JPanel();
        add(northPanel, BorderLayout.NORTH);

        final int TEXT_ROWS = 20;
        final int TEXT_COLUMNS = 60;

        messages = new JTextArea(TEXT_ROWS, TEXT_COLUMNS);
        add(new JScrollPane(messages));

        interruptibleButton = new JButton("Interruptible");
        blockingButton = new JButton("Blocking");

        northPanel.add(interruptibleButton);
        northPanel.add(blockingButton);

        interruptibleButton.addActionListener(event ->
        {
            interruptibleButton.setEnabled(false);
            blockingButton.setEnabled(false);
            cancelButton.setEnabled(true);

            connectThread = new Thread(() ->
                {
                    try
                    {
                        connectInterruptibly();
                    }
                    catch (IOException e)
                    {
                        messages.append("\nInterruptibleSocketTest.connectInterruptibly: " + e);
                    }
                });

            connectThread.start();
        });

        blockingButton.addActionListener(event ->
        {
            interruptibleButton.setEnabled(false);
            blockingButton.setEnabled(false);
            cancelButton.setEnabled(true);

            connectThread = new Thread(() ->
                {
                    try
                    {
                        connectBlocking();
                    }
                    catch (IOException e)
                    {
                        messages.append("\nInterruptibleSocketTest.connectBlocking: " + e);
                    }
                });

            connectThread.start();
        });

        cancelButton = new JButton("Cancel");
        cancelButton.setEnabled(false);
        northPanel.add(cancelButton);

        cancelButton.addActionListener(event ->
        {
            connectThread.interrupt();
            cancelButton.setEnabled(false);
        });

        server = new TestServer();
        new Thread(server).start();
        pack();
    }

    /**
     * 使用可中断 I/O 连接到测试服务器。
     */
    public void connectInterruptibly() throws IOException
    {
        messages.append("Interruptible:\n");

        try (SocketChannel channel = SocketChannel.open(new InetSocketAddress("localhost", 8189)))
        {
            in = new Scanner(channel, "UTF-8");

            while (!Thread.currentThread().isInterrupted())
            {
                messages.append("Reading ");

                if (in.hasNextLine())
                {
                    String line = in.nextLine();
                    messages.append(line);
                    messages.append("\n");
                }
            }
        }
        finally
        {
            EventQueue.invokeLater(() ->
                {
                    messages.append("Channel closed\n");
                    interruptibleButton.setEnabled(true);
                    blockingButton.setEnabled(true);
                });
        }
    }

    /**
     * 使用阻塞 I/O 连接到测试服务器。
     */
    public void connectBlocking() throws IOException
    {
        messages.append("Blocking:\n");

        try (Socket sock = new Socket("localhost", 8189))
        {
            in = new Scanner(sock.getInputStream(), "UTF-8");

            while (!Thread.currentThread().isInterrupted())
            {
                messages.append("Reading ");

                if (in.hasNextLine())
                {
                    String line = in.nextLine();
                    messages.append(line);
                    messages.append("\n");
                }
            }
        }
        finally
        {
            EventQueue.invokeLater(() ->
                {
                    messages.append("Socket closed\n");
                    interruptibleButton.setEnabled(true);
                    blockingButton.setEnabled(true);
                });
        }
    }

    /**
     * 多线程服务器，监听端口 189 并向客户端发送数字，
     * 在发送 10 个数字后模拟挂起。
     */
    class TestServer implements Runnable
    {
        public void run()
        {
            try (ServerSocket s = new ServerSocket(189))
            {
                while (true)
                {
                    Socket incoming = s.accept();
                    Runnable r = new TestServerHandler(incoming);
                    Thread t = new Thread(r);
                    t.start();
                }
            }
            catch (IOException e)
            {



```java
messages.append("\nTestServer.run: " + e);
```

```java
class TestServerHandler implements Runnable
{
    private Socket incoming;
    private int counter;

    public TestServerHandler(Socket i)
    {
        incoming = i;
    }

    public void run()
    {
        try
        {
            OutputStream outStream = incoming.getOutputStream();
            PrintWriter out = new PrintWriter(
                new OutputStreamWriter(outStream, "UTF-8"),
                true /* autoFlush */);

            while (counter < 100)
            {
                counter++;

                if (counter <= 10)
                    out.println(counter);

                Thread.sleep(100);
            }
        }
        finally
        {
            incoming.close();
            messages.append("Closing server\n");
        }
        catch (Exception e)
        {
            messages.append("\nTestServerHandler.run: " + e);
        }
    }
}
```

### `java.net.InetSocketAddress` 1.4

- `InetSocketAddress(String hostname, int port)` 根据给定的主机名和端口构造一个地址对象，并在构造期间解析主机名。如果无法解析主机名，则地址对象的 `unresolved` 属性被设置为 `true`。
- `boolean isUnresolved()` 如果此地址对象无法被解析，则返回 `true`。

### `java.nio.channels.SocketChannel` 1.4

- `static SocketChannel open(SocketAddress address)` 打开套接字通道并连接到远程地址。

### `java.nio.channels.Channels` 1.4

- `static InputStream newInputStream(ReadableByteChannel channel)` 构造一个从给定通道读取的输入流。
- `static OutputStream newOutputStream(WritableByteChannel channel)` 构造一个向给定通道写入的输出流。

## 4.4 获取 Web 数据

要在 Java 程序中访问 Web 服务器，你可能需要比套接字连接和 HTTP 请求更高的层次的操作。在接下来的章节中，我们将讨论 Java 库为此目的提供的类。

### 4.4.1 URLs 和 URIs

`URL` 和 `URLConnection` 类封装了从远程站点检索信息的大部分复杂性。你可以从字符串构造一个 `URL` 对象：

```java
URL url = new URL(urlString);
```

如果你只是想获取资源的内容，请使用 `URL` 类的 `openStream` 方法。该方法产生一个 `InputStream`。按照通常的方式使用它——例如，构造一个 `Scanner`：

```java
InputStream in = url.openStream();

Scanner in = new Scanner(in, "UTF-8");
```

`java.net` 包对 URL（统一资源定位符）和 URI（统一资源标识符）进行了有用的区分。URI 是一个纯粹的句法结构，包含了指定 Web 资源的字符串各个部分。URL 是一种特殊的 URI，即具有足够信息来定位资源的 URI。其他 URI，例如 `mailto:horstmann.com`，并不是定位符——没有数据可以从该标识符中进行定位。这样的 URI 被称为 URN（统一资源名称）。

在 Java 库中，`URI` 类没有用于访问标识符所指定资源的方法——它的唯一用途是解析。相比之下，`URL` 类可以打开一个指向资源的流。由于这个原因，`URL` 类仅与 Java 库知道如何处理的方案工作，例如 `http:`、`https:`、`ftp:`、本地文件系统（`file:`）和 JAR 文件（`jar:`）。

为了理解为什么解析并非易事，请考虑 URI 可能有多么复杂。例如，`http://google.com?q=Beach&ftp://username:password@ftp.yourserver.com/pub/file.txt`。URI 规范规定了这些标识符的组成规则。URI 的语法如下：

```text
scheme:schemeSpecificPart#fragment
```

在这里，`...` 表示可选部分，而 `:` 和 `#` 字面包含在标识符中。如果存在 `scheme:` 部分，则该 URI 称为 `absolute`（绝对）。否则，它被称为 `relative`（相对）。

如果 `schemeSpecificPart` 不以 `/` 开头，例如 `mailto:horstmann.com`，则绝对 URI 是 `opaque`（不透明的）。所有的非透明绝对 URI 和所有的相对 URI 都是 `hierarchical`（分级的）。例如，`http://horstmann.com/index.html../../java/net/Socket.html`。

分级 URI 的 `schemeSpecificPart` 具有结构 `//authority][path][?query]`，其中 `...` 再次可选部分。对于基于服务器的 URI，`authority` 部分的形式为 `user-info@host[:port]`。`port` 必须是一个整数。

标准化 URI 的 RFC 2396 还支持一种基于注册的的机制，在其中 `authority` 具有不同的格式，但这并不常用。

`URI` 类的一个用途是解析标识符并将其拆分为各个组件。你可以通过以下方法检索它们：

```java
getScheme
getSchemeSpecificPart
getAuthority
getUserInfo
getHost
getPort
getPath
getQuery
getFragment
```

`URI` 类的另一个用途是处理绝对和相对标识符。如果你有一个绝对 URI，如 `http://docs.mycompany.com/api/java/net/ServerSocket.html` 和一个相对 URI，如 `../../java/net/Socket.html`，你可以将两者合并为一个绝对 URI：

```text
http://docs.mycompany.com/api/java/net/Socket.html
```

这个过程被称为对相对 URL 进行 `resolving`（解析）。相反的过程被称为 `relativization`（相对化）。例如，假设你有一个基础 URI `http://docs.mycompany.com/api` 和一个 URI `http://docs.mycompany.com/api/java/lang/String.html`，那么相对化后的 URI 是 `java/lang/String.html`。

`URI` 类支持这两种操作：

```java
relative = base.relativize(combined);

combined = base.resolve(relative);
```

### 4.4.2 使用 `URLConnection` 获取信息

如果你想获取关于 Web 额外信息，你应该使用 `URLConnection` 类，它比基础的 `URL` 类提供了更多的控制。在处理 `URLConnection` 对象时，你必须仔细安排你的步骤。

1. 调用 `URL` 类的 `openConnection` 方法获取 `URLConnection` 对象：

   ```java
   URLConnection connection = url.openConnection();
   ```

2. 使用以下方法设置任何请求属性：

   ```java
   setDoInput
   setDoOutput
   setIfModifiedSince
   setUseCaches
   setAllowUserInteraction
   setRequestProperty
   setConnectTimeout
   setReadTimeout
   ```

   我们在本节后面以及 API 注释中讨论这些方法。

3. 调用 `connect` 方法连接到远程资源：

   ```java
   connection.connect();
   ```

   除了建立服务器连接外，该方法还会查询服务器头部信息。

4. 连接到服务器后，你可以查询头部信息。两个方法 `getHeaderFieldKey` 和 `getHeaderField` 可以列出头部所有的字段。`getHeaderFields` 方法获取一个包含头部字段的标准 `Map` 对象。为了方便起见，以下方法查询标准字段：

   ```java
   getContentType
   getContentLength
   getContentEncoding
   getDate
   getExpiration
   getLastModified
   ```

5. 最后，你可以访问资源数据。使用 `getInputStream` 方法获取一个用于读取信息的输入流。（这与 `URL` 类的 `openStream` 方法返回的输入流是相同的。）另一个方法 `getContent` 在实践中并不好用。由 `text/plain` 和 `image/gif` 等标准内容类型返回的对象需要 `com.sun` 层次结构中的类进行处理。你可以注册自己的内容处理程序，但我们书中书中书中讨论这种技术。

![Image](img/00004.jpeg) **注意**

某些程序员在在使用 `URLConnection` 类时会形成错误的心理认知，认为 `getInputStream` 和 `getOutputStream` 方法与 `Socket` 类的方法相似。但事实并非完全如此。`URLConnection` 类在背后执行了大量的“魔法”操作——特别是对请求头和响应头的处理。因此，遵循连接的设置步骤是非常关重要的。

## 连接方法

现在让我们详细查看 `URLConnection` 的一些方法。有几个方法在连接到服务器之前设置连接的属性。最重要的方法是 `setDoInput` 和 `setDoOutput`。默认情况下，连接会产生一个用于从服务器读取的输入流，但没有用于写入的输出流。如果你需要一个输出流（例如，向 Web 服务器发布数据），你需要调用：

```java
connection.setDoOutput(true);
```

接下来，你可能想要设置一些请求头。请求头会随请求命令一起发送到服务器。这里是一个示例：

```text
GET www.server.com/index.html HTTP/1.0
Referer: http://www.somewhere.com/links.html
Proxy-Connection: Keep-Alive
User-Agent: Mozilla/5.0 (X11; U; Linux i686; en-US; rv:1.8.1.4)
Host: www.server.com
Accept: text/html, image/gif, image/jpeg, image/png, /**
Accept-Language: en
Accept-Charset: iso-8859-1,*,utf-8
Cookie: orangemilano=192218887821987
```

`setIfModifiedSince` 方法告诉连接，你只对自某个日期以来修改的数据感兴趣。

`setUseCaches` 和 `setAllowUserInteraction` 方法应该只在 applet 内部调用。`setUseCaches` 方法引导浏览器首先检查浏览器缓存。`setAllowUserInteraction` 方法允许 applet 弹出对话框，用于查询受密码保护资源的用户名和密码（参见图 4.7）。

![Image](img/00082.jpeg) **图 4.7** 网络密码对话框

最后，你可以使用通用的 `setRequestProperty` 方法来设置任何对特定协议有意义的键/值对。关于 HTTP 请求头的格式，请参阅 RFC 2616。这些参数中的一些并没有良好的文档，是在程序员之间口口相传的。例如，如果你想访问一个受密码保护的网页，必须执行以下操作：

1. 将用户名、冒号和密码拼接。

   ```java
   String input = username + ":" + password;
   ```

2. 计算结果字符串的 Base64 编码。（Base64 编码将字节序列编码为可打印的 ASCII 字符序列。）

   ```java
   Base64.Encoder encoder = Base64.getEncoder();

   String encoding = encoder.encodeToString(input.getBytes(StandardCharsets.UTF_8));
   ```

3. 调用 `setRequestProperty` 方法，名称为 `"Authorization"`，值为 `"Basic " + encoding`：

   ```java
   connection.setRequestProperty("Authorization", "Basic " + encoding);
   ```

![Image](img/00003.jpeg) **提示**

你刚刚看到了如何访问受密码保护的网页。若要通过 FTP 访问受密码保护的文件，请使用完全不同的方法：构造如下形式的 URL：

```text
ftp://username:password@ftp.yourserver.com/pub/file.txt
```

## 响应头头部

一旦调用了 `connect` 方法，就可以查询响应头信息。首先，让我们看看如何枚举所有的响应头字段。该类的实现者认为有必要通过引入另一种迭代协议来表达他们的个性。调用：

```java
String key = connection.getHeaderFieldKey(n);
```

从响应头中获取第 `n` 个键，其中 `n` 从 `1` 开始！如果 `n` 为 0 或大于头字段的总数，则返回 `null`。没有方法可以返回字段的数量；你只需要不断调用 `getHeaderField` 直到得到 `null`。同样，调用：

```java
String value = connection.getHeaderField(n);
```

返回第 `n` 个值。`getHeaderFields` 方法返回一个响应头字段的 `Map`。

```java
Map<String, List<String>> headerFields = connection.getHeaderFields();
```

这里是一个典型 HTTP 请求的响应头组：

```text
Date: Wed, 27 Aug 2008 00:15:48 GMT
Server: Apache/2.2.2 (Unix)
Last-Modified: Sun, 22 Jun 2008 20:53:38 GMT
Accept-Ranges: bytes
Content-Length: 4813
Connection: close
Content-Type: text/html
```

为了方便起见，有六个方法查询最常见头部类型的值并在适当的情况下转换为数值类型。`表 4.1` 显示了这些便利方法。类型为 `long` 的方法返回自 GMT 1970 年 1 月 1 日以来的秒数。

![Image](img/0083.jpeg) **表 4.1** 响应值的便利方法

`Listing 4.6` 中的程序允许你实验 URL 连接。在运行程序时，在命令行提供一个 URL 以及可选的用户名和密码，例如：

```text
java urlConnectionTest http://www.yourserver.com password
```

程序将打印：

- 头部所有的键和值
- `表 4.1` 中六个便利方法的返回值
- 请求资源的前十行

**Listing 4.6** `urlConnection/URLConnectionTest.java`

```java
package urlConnection;

import java.io.*;
import java.net.*;
import java.nio.charset.*;
import java.util.*;

/**
 * 此程序连接到 URL 并显示响应头数据以及请求数据的前 10 行。
 *
 * 在命令行上提供 URL 以及可选的用户名和密码（用于 HTTP 身份验证）。
 * @version 1.11 2007-06-26
 * @author Cay Horstmann
```



```java
public class URLConnectionTest {

    public static void main(String[] args) {

        try {

            String urlName;

            if (args.length > 0) urlName = args[0];

            else urlName = "http://horstmann.com";

            URL url = new URL(urlName);

            URLConnection connection = url.openConnection();

            // 如果命令行指定了则设置用户名、密码

            if (args.length > 2) {

                String username = args[1];

                String password = args[2];

                String input = username + ":" + password;

                Base64.Encoder encoder = Base64.getEncoder();

                String encoding = encoder.encodeToString(input.getBytes(StandardCharsets.UTF_8));

                connection.setRequestProperty("Authorization", "Basic " + encoding);
            }

            connection.connect();

            // print header fields

            Map<String, List<String>> headers = connection.getHeaderFields();

            for (Map.Entry<String, List<String>> entry : headers.entrySet()) {

                String key = entry.getKey();

                for (String value : entry.getValue())

                    System.out.println(key + ": " + value);
            }

            // print convenience functions

            System.out.println("---------- ");

            System.out.println("getContentType: " + connection.getContentType());

            System.out.println("getContentLength: " + connection.getContentLength());

            System.out.println("getContentEncoding: " + connection.getContentEncoding());

            System.out.println("getDate: " + connection.getDate());

            System.out.println("getExpiration: " + connection.getExpiration());

            System.out.println("getLastModifed: " + connection.getLastModified());

            System.out.println("---------- ");

            String encoding = connection.getContentEncoding();

            if (encoding == null) encoding = "UTF-8";

            try (Scanner in = new Scanner(connection.getInputStream(), encoding)) {

                // print first ten lines of contents

                for (int n = 1; in.hasNextLine() && n <= 10; n++)

                    System.out.println(in.nextLine());

                if (in.hasNextLine()) System.out.println(". . .");
            }
        }
        catch (IOException e) {

            e.printStackTrace();
        }
    }
}
```

## `java.net.URL`

- `InputStream openStream()`：打开一个读取资源数据的输入流。
- `URLConnection connect()`：返回一个管理与资源连接的 `URLConnection` 对象。

## `java.net.URLConnection`

- `void setDoInput(boolean doInput)` / `boolean getDoInput()`：如果 `doInput` 为 `true`，用户可以从此 `URLConnection` 接收输入。
- `void setDoOutput(boolean doOutput)` / `boolean getDoOutput()`：如果 `doOutput` 为 `true`，用户可以向此 `URLConnection` 发送输出。
- `void setIfModifiedSince(long time)` / `long getIfModifiedSince()`：`ifModifiedSince` 属性配置此 `URLConnection` 仅获取自给定时间以来修改过的数据。时间为自 1970 年 1 月 1 日午夜以来的秒数。
- `void setUseCaches(boolean useCaches)` / `boolean getUseCaches()`：如果 `useCaches` 为 `true`，则可以从本地缓存检索数据。注意 `URLConnection` 本身并不维护此类缓存。缓存必须由外部程序（如浏览器）提供。
- `void setAllowUserInteraction(boolean allowUserInteraction)` / `boolean getAllowUserInteraction()`：如果 `allowUserInteraction` 为 `true`，则可以询问用户获取密码。注意 `URLConnection` 本身没有执行此类查询的机制。查询必须由浏览器或插件等外部程序执行。
- `void setConnectTimeout(int timeout)` / `int getConnectTimeout()`：设置或获取连接超时时间（以毫秒为单位）。如果在建立连接之前已超时，关联输入流的 `connect` 方法将抛出 `SocketTimeoutException`。
- `void setReadTimeout(int timeout)` / `int getReadTimeout()`：设置或获取读取数据的超时时间（以毫秒为单位）。如果在读取操作成功之前已超时，`read` 方法将抛出 `SocketTimeoutException`。
- `void setRequestProperty(String key, String value)`：设置请求头字段。
- `Map<String, List<String>> getRequestProperties()`：返回请求属性的映射。相同键的所有值都放在列表中。
- `void connect()`：连接到远程资源并获取响应头信息。
- `Map<String, List<String>> getHeaderFields()`：返回响应头的映射。相同键的所有值都放在列表中。
- `String getHeaderFieldKey(int n)`：获取第 `n` 个响应头字段的键，如果 `n` ≤ 0 或大于响应头字段的数量，则返回 `null`。
- `String getHeaderField(int n)`：获取第 `n` 个响应头字段的值，如果 `n` ≤ 0 或大于响应头字段的数量，则返回 `null`。
- `int getContentLength()`：如果可用，获取内容长度；如果未知则返回 `-1`。
- `String getContentType()`：获取内容类型，例如 `text/plain` 或 `image/gif`。
- `String getContentEncoding()`：获取内容编码，例如 `gzip`。此值并不常用，因为默认的 `identity` 编码不应在 `Content-Encoding` 头部中指定。
- `long getDate()`、`long getExpiration()`、`long getLastModifed()`：获取资源的创建、过期和最后修改日期。日期指定为自 1970 年 1 月 1 日午夜以来的秒数。
- `InputStream getInputStream()`、`OutputStream getOutputStream()`：返回用于从资源读取或向资源写入的流。
- `Object getContent()`：选择适当的内容处理器来读取资源数据并将其转换为对象。除非你安装了自定义的内容处理器，否则此方法对于读取 `text/plain` 或 `image/gif` 等标准类型没有用。

### 4.4.3 提交表单数据

在前面的节中，你已经了解了如何从 Web 服务器读取数据。现在我们将向你展示程序如何向 Web 服务器发送数据，并发送给调用的程序。

要将信息从浏览器发送到 Web 服务器，用户需要填写*表单*，如图 4.8。

**图 4.8** HTML 表单

当用户点击提交按钮时，文本框中的内容以及复选框、单选按钮和其他输入元素的设置将被发送回 Web 服务器。Web 服务器调用程序处理用户输入。

许多技术允许 Web 服务器调用程序。常见的 Java Servlet、JavaServer Faces、Microsoft Active Server Pages (ASP) 以及通用网关接口（CGI）脚本。

服务端程序处理表单数据并产生由 Web 服务器传回另一个 HTML 页面。这一序列如图 4.9。响应页面可以包含新信息（例如信息搜索程序），也可以只是一个确认。浏览器随后显示响应页面。

![Image](img/00085.jpeg)

**图 4.9** 执行服务端程序期间的数据流

我们在书中并不讨论服务端的实现。我们的兴趣仅在于编写与现有服务端程序交互的客户端程序。

当表单数据发送到 Web 服务器时，无论数据是由 Servlet、CGI 脚本还是其他服务端技术解释并不重要。客户端以标准格式发送数据到 Web 服务器，由 Web 服务器负责将其传递给生成响应的程序。

有两个命令被称为 `GET` 和 `POST`，常用于向 Web 服务器发送信息。

在 `GET` 命令中，你只需将查询参数附加到 URL 的末尾。URL 的格式为 `http://host/path?query`。

每个参数的格式为 `name=value`。参数之间用 `&` 字符分隔。参数值使用*URL 编码*方案进行编码，遵循以下规则：

- 保持字符 `A` 到 `Z`、`a` 到 `z`、`0` 到 `9` 以及 `. - ~ _` 不变。
- 将所有空格替换为 `+` 字符。
- 将所有其他字符编码为 UTF-8，并对每个字节使用 `%` 后跟一个两位十六进制数字进行编码。

例如，为了传输*San Francisco, CA*，你使用 `San+Francisco%2c+CA`，其中十六进制数字 `2c` 是字符 `','` 的 UTF-8 编码。

这种编码可以防止任何中间程序干扰空格并解释其他特殊字符。

例如，在本文期间，Google Maps 网站（`www.google.com/maps`）接受名为 `q` 和 `hl` 的查询参数，其值分别为位置查询和响应的人类语言。要获取位于旧金山 1 Market Street 的地图，并使用德语响应，请使用以下 URL：

![代码图像](img/00000.jpeg)

```text
http://www.google.com/maps?q=1+Market+Street+San+Francisco&hl=de
```

非常长的查询字符串在浏览器中看起来并不美观，而且旧版浏览器和代理对 `GET` 请求中包含的字符数量有限制。因此，包含大量数据的表单通常使用 `POST` 请求。在 `POST` 请求中，你不需要将参数附加到 URL。相反，你从 `URLConnection` 获取一个输出流，并将键值对写入输出流中。你仍然需要对值进行 URL 编码，并用 `&` 字符将它们分隔。

让我们详细查看此过程。要向服务器端程序发布数据，首先建立一个 `URLConnection`：

![代码图像](img/00000.jpeg)

```java
URL url = new URL("http://host/path");

URLConnection connection = url.openConnection();
```

然后，调用 `setDoOutput` 方法为输出设置连接：

```java
connection.setDoOutput(true);
```

接下来，调用 `getOutputStream` 获取一个可以通过该流向服务器发送数据的流。如果你正在向服务器发送文本，将该流封装进 `PrintWriter` 中非常方便。

![代码图像](img/00000.jpeg)

```java
PrintWriter out = new PrintWriter(connection.getOutputStream(), "UTF-8");
```

现在你已经准备好向服务器发送数据了：

![代码图像](img/00000.jpeg)

```java
out.print(name1 + "=" + URLEncoder.encode(value1, "UTF-8") + "&");

out.print(name2 + "=" + URLEncoder.encode(value2, "UTF-8"));
```

关闭输出流：

```java
out.close();
```

最后，调用 `getInputStream` 并读取服务器响应。

让我们运行一个实际示例。`https://www.usps.com/zip4/` 网站包含一个用于查找街道地址邮政编码的表单（参见第 268 页上的图 4.8）。要在 Java 程序中使用此表单，你需要知道 `POST` 请求的 URL 和参数。

你可以通过查看表单的 HTML 代码获取这些信息，但通常使用网络监控器“监视”请求更为简单。大多数浏览器的开发工具包中包含网络监控器。例如，图 4.10 显示了向我们的示例网站提交数据时 Firefox 网络监控器的屏幕截图。你可以找到提交的 URL 以及参数名和参数值。

![图像](img/00086.jpeg)

**图 4.10** 一个 HTML 表单

在发布表单数据时，HTTP 头部包含内容类型和内容长度：

![代码图像](img/00000.jpeg)

```http
Content-Type: application/x-www-form-urlencoded
```

你也可以以其他格式发布数据。例如，当使用 JavaScript 对象表示法 (JSON) 发送数据时，将内容类型设置为 `application/json`。

`POST` 的头部还必须包含内容长度，例如：

```http
Content-Length: 124
```

Listing 4.7 中的程序向任何服务器端程序发送 `POST` 表单数据。将数据放入如下的 `.properties` 文件中：

![代码图像](img/00000.jpeg)

```properties
url=https://tools.usps.com/go/ZipLookupAction.action

tAddress=1 Market Street

tCity=San Francisco

sState=CA

...
```

程序移除 `url` 条目，并将所有其他条目发送到 `doPost` 方法。

在 `doPost` 方法中，我们首先打开连接，调用 `setDoOutput(true)` 并打开输出流。然后我们列出所有的键和值。对于每一个项，我们发送 `key`、`=` 字符、`value` 和 `&` 分隔符：

![代码图像](img/00000.jpeg)

```java
out.print(key);

out.print('=');

out.print(value);

out.print('&');
```



- 将所有空格替换为 `+` 字符。
- 将所有其他字符编码为 UTF-8，并对每个字节使用 `%` 后跟一个两位十六进制数字进行编码。

例如，为了传输 *San Francisco, CA*，你使用 `San+Francisco%2c+CA`，其中十六进制数字 `2c` 是字符 `,` 的 UTF-8 编码。

这种编码可以防止任何中间程序干扰空格并解释其他特殊字符。

例如，在本文期间，Google Maps 网站（`www.google.com/maps`）接受名为 `q` 和 `hl` 的查询参数，其值分别为位置查询和响应的人类语言。要获取旧金山 1 Market Street 的地图并使用德语响应，请使用以下 URL：

```text
http://www.google.com/maps?q=1+Market+Street+San+Francisco&hl=de
```

非常长的查询字符串在浏览器中看起来并不美观，而且旧版浏览器和代理对 `GET` 请求中包含的字符数量有限制。因此，包含大量数据的表单通常使用 `POST` 请求。在 `POST` 请求中，你不需要将参数附加到 URL。相反，你从 `URLConnection` 获取一个输出流，并将键值对写入输出流中。你仍然需要对值进行 URL 编码，并用 `&` 字符将它们分隔。

让我们详细查看此过程。要向服务器端程序发布数据，首先建立一个 `URLConnection`：

```java
URL url = new URL("http://host/path");

URLConnection connection = url.openConnection();
```

然后，调用 `setDoOutput` 方法为输出设置连接：

```java
connection.setDoOutput(true);
```

接下来，调用 `getOutputStream` 获取一个可以通过该流向服务器发送数据的流。如果你正在向服务器发送文本，将该流封装进 `PrintWriter` 中非常方便。

```java
PrintWriter out = new PrintWriter(connection.getOutputStream(), "UTF-8");
```

现在你已经准备好向服务器发送数据了：

```java
out.print(name1 + "=" + URLEncoder.encode(value1, "UTF-8") + "&");

out.print(name2 + "=" + URLEncoder.encode(value2, "UTF-8"));
```

关闭输出流。

```java
out.close();
```

最后，调用 `getInputStream` 并读取服务器响应。

让我们运行一个实际示例。`https://www.usps.com/zip4/` 网站包含一个用于查找街道地址邮政编码的表单（参见第 268 页上的图 4.8）。要在 Java 程序中使用此表单，你需要知道 `POST` 请求的 URL 和参数。

你可以通过查看表单的 HTML 代码获取这些信息，但通常使用网络监控器“监视”请求更为简单。大多数浏览器的开发工具包中包含网络监控器。例如，图 4.10 显示了向我们的示例网站提交数据时 Firefox 网络监控器的屏幕截图。你可以找到提交的 URL 以及参数名和参数值。

![图像](img/00086.jpeg)

**图 4.10** 一个 HTML 表单

在发布表单数据时，HTTP 头部包含内容类型和内容长度：

```http
Content-Type: application/x-www-form-urlencoded
```

你也可以以其他格式发布数据。例如，当使用 JavaScript 对象表示法（JSON）发送数据时，将内容类型设置为 `application/json`。

`POST` 的头部还必须包含内容长度，例如：

```http
Content-Length: 124
```

列表 4.7 中的程序向任何服务器端程序发送 `POST` 表单数据。将数据放入如下的 `.properties` 文件中：

```properties
url=https://tools.usps.com/go/ZipLookupAction.action

tAddress=1 Market Street

tCity=San Francisco

sState=CA

...
```

程序移除 `url` 条目，并将所有其他条目发送到 `doPost` 方法。

在 `doPost` 方法中，我们首先打开连接，调用 `setDoOutput(true)` 并打开输出流。然后我们列出所有的键和值。对于每一个项，我们发送 `key`、`=` 字符、`value` 和 `&` 分隔符。

在这种情况下，获取 `Location` 响应头以获得重定向的 URL。然后断开连接并对新 URL 建立另一个连接：

```java
String location = connection.getHeaderField("Location");

if (location != null)
{
   URL base = connection.getURL();

   connection.disconnect();

   connection = (HttpURLConnection) new URL(base, location).openConnection();

   . . .
}
```

该程序所演示的技巧在你需要从现有网站查询信息时都非常有用。只需找到你需要发送的参数，然后从回复中剥离 HTML 标签和其他不需要的信息即可。

---

![Image](img/00002.jpeg)

> **注意事项**
>
> 如你所见，可以使用 Java 库类与网页进行交互，但这并不方便。请考虑使用如 Apache HttpClient（`http://hc.apache.org/httpcomponents-client-ga`）等库。

---

#### 列表 4.7：`post/PostTest.java`

```java
package post;

import java.io.*;

import java.net.*;

import java.nio.file.*;

import java.util.*;

/**
 * 此程序演示了如何使用 URLConnection 类进行 POST 请求。
 *
 * @version 1.40 2016-04-24
 * @author Cay Horstmann
 */
public class PostTest
{
   public static void main(String[] args) throws IOException
   {
      String propsFilename = args.length > 0 ? args[0] : "post/post.properties";

      Properties props = new Properties();

      try (InputStream in = Files.newInputStream(Paths.get(propsFilename)))
      {
         props.load(in);
      }

      String urlString = props.remove("url").toString();

      Object userAgent = props.remove("User-Agent");

      Object redirects = props.remove("redirects");

      CookieHandler.setDefault(new CookieManager(null, CookiePolicy.ACCEPT_ALL));

      String result = doPost(new URL(urlString), props,
            userAgent == null ? null : userAgent.toString(),
            redirects == null ? -1 : Integer.parseInt(redirects.toString()));

      System.out.println(result);
   }

   /**
    * 执行一个 HTTP POST。
    *
    * @param url 要发送 POST 的 URL
    * @param nameValuePairs 查询参数
    * @param userAgent 要使用的用户代理，或为 null 以使用默认用户代理
    * @param redirects 要手动跟随的重定向数量，或 -1 表示自动重定向
    * @return 从服务器返回的数据
    */
   public static String doPost(URL url, Map<Object, Object> nameValuePairs, String userAgent,
      int redirects)
      throws IOException
   {
      HttpURLConnection connection = (HttpURLConnection) url.openConnection();

      if (userAgent != null)
         connection.setRequestProperty("User-Agent", userAgent);

      if (redirects >= 0)
         connection.setInstanceFollowRedirects(false);

      connection.setDoOutput(true);

      try (PrintWriter out = new PrintWriter(connection.getOutputStream()))
      {
         boolean first = true;

         for (Map.Entry<Object, Object> pair : nameValuePairs.entrySet())
         {
            if (first)
               first = false;
            else
               out.print('&');

            String name = pair.getKey().toString();
            String value = pair.getValue().toString();

            out.print(name);
            out.print('=');
            out.print(URLEncoder.encode(value, "UTF-8"));
         }
      }

      String encoding = connection.getContentEncoding();

      if (encoding == null)
         encoding = "UTF-8";

      if (redirects > 0)
      {
         int responseCode = connection.getResponseCode();

         if (responseCode == HttpURLConnection.HTTP_MOVED_PERM
               || responseCode == HttpURLConnection.HTTP_MOVED_TEMP
               || responseCode == HttpURLConnection.HTTP_SEE_OTHER)
         {
            String location = connection.getHeaderField("Location");

            if (location != null)
            {
               URL base = connection.getURL();

               connection.disconnect();

               return doPost(new URL(base, location), nameValuePairs, userAgent, redirects - 1);
            }
         }
      }
      else if (redirects == 0)
      {
         throw new IOException("Too many redirects");
      }

      StringBuilder response = new StringBuilder();

      try (Scanner in = new Scanner(connection.getInputStream(), encoding))
      {
         while (in.hasNextLine())
         {
            response.append(in.nextLine());
            response.append("\n");
         }
      }
      catch (IOException e)
      {
         InputStream err = connection.getErrorStream();

         if (err == null)
            throw e;

         try (Scanner in = new Scanner(err))
         {
            response.append(in.nextLine());
            response.append("\n");
         }
      }

      return response.toString();
   }
}
```

---

#### `java.net.HttpURLConnection` 1.0

- `InputStream getErrorStream()` 返回一个可以读取错误消息的流。

---

#### `java.net.URLEncoder` 1.0

- `static String encode(String s, String encoding)` 使用指定的编码返回字符串 `s` 的 URL 编码形式。（推荐方案是 `"UTF-8"`。）在 URL 编码中，字符 `'A'`–`'Z'`、`'a'`–`'z'`、`'0'`–`'9'`、`'-'`、`'_'`、`'.'`、`'~'` 保持不变。空格被编码为 `'+'`，所有其他字符被编码为 `%XY` 序列，其中 `XY` 是字节的十六进制值。

---

#### `java.net.URLDecoder` 1.2

- `static String decode(String s, String encoding)` 使用指定的编码解码 URL 字符串 `s`。

---

### 4.5 发送电子邮件

在过去，编写一个通过连接 25 端口来发送电子邮件的程序是简单的。简单邮件传输协议（SMTP）描述了电子邮件的格式。一旦连接到服务器，就可以发送邮件头（易于生成），然后是邮件内容。

以下是详细信息：

1. 打开到主机的连接。

   ```java
   Socket s = new Socket("mail.yourserver.com", 25); // 25 是 SMTP

   PrintWriter out = new PrintWriter(s.getOutputStream(), "UTF-8");
   ```

2. 向打印流发送以下信息：

   ```text
   HELO sending host

   MAIL FROM: sender e-mail address

   RCPT TO: recipient e-mail address

   DATA

   Subject: subject

   （空行）

   mail message (任意行)

   .

   QUIT
   ```



SMTP 规范（RFC 821）规定行必须以 `\r` 后跟 `\n` 终止。

以前 SMTP 服务器通常愿意路由任何人的电子邮件。然而，在如今垃圾邮件泛滥的时代，大多数服务器都有内置检查，并且只接受来自信任的用户或 IP 地址范围的请求。身份验证通常在安全的套接字连接上进行。

手动实现这些身份验证方案将非常麻烦。相反，我们将展示如何使用 JavaMail API 从 Java 程序发送电子邮件。

从 `www.oracle.com/technetwork/java/javamail` 下载 JavaMail，并将其解压到硬盘上的某个位置。

要使用 JavaMail，你需要设置一些依赖于你邮件服务器的属性。例如，使用 GMail 时，你使用：

`mail.transport.protocol=smtps`

`mail.smtps.auth=true`

`mail.smtps.host=smtp.gmail.com`

`mail.smtps.user=cayhorstmann@gmail.com`

我们的示例程序从属性文件中读取这些内容。

出于安全考虑，我们没有将密码放在属性文件中，而是通过提示让用户输入。

读取属性文件，然后按照如下方式获取邮件会话：

```java
Session mailSession = Session.getDefaultInstance(props);
```

创建一个包含所需的发送者、接收者、主题和邮件正文的消息：

```java
MimeMessage message = new MimeMessage(mailSession);

message.setFrom(new InternetAddress(from));

message.addRecipient(RecipientType.TO, new InternetAddress(to));

message.setSubject(subject);

message.setText(builder.toString());
```

然后发送它：

```java
Transport tr = mailSession.getTransport();

tr.connect(null, password);

tr.sendMessage(message, message.getAllRecipients());

tr.close();
```

Listing 4.8 中的程序从格式如下的文本文件中读取消息：

发送者 接收者 主题 邮件正文（任意行数）

要运行该程序，输入：

```bash
java -classpath .:path/to/mail.jar path/to/message.txt
```

在这里，`mail.jar` 是随 JavaMail 分发一起的 JAR 文件。（Windows 用户：记住在 classpath 中使用分号代替冒号。）

在编写本文时，GMail 并不检查信息的真实性——你可以提供任何你喜欢的发送者。（当你下次收到来自 `president@whitehouse.gov` 的邮件，邀请你参加白宫草坪上的正式晚装舞会时，请记住这一点。）

***

![Image](img/00003.jpeg) 提示

如果你无法确定为什么你的邮件连接无法工作，请调用：

```java
mailSession.setDebug(true);
```

并检查输出的消息。此外，JavaMail API FAQ 包含一些实用的提示。

***

**Listing 4.8** `mail/MailTest.java`

***

```java
package mail;

import java.io.*;
import java.nio.charset.*;
import java.nio.file.*;
import java.util.*;
import javax.mail.*;
import javax.mail.internet.*;
import javax.mail.internet.MimeMessage.RecipientType;

/**
 * 此程序演示了如何使用 JavaMail 发送邮件消息。
 * @author Cay Horstmann
 * @version 1.00 2012-06-04
 */
public class MailTest
{
  public static void main(String[] args) throws MessagingException, IOException
  {
      Properties props = new Properties();
      try (InputStream in = Files.newInputStream(Paths.get("mail", "mail.properties")))
      {
          props.load(in);
      }
      List<String> lines = Files.readAllLines(Paths.get(args[0]), Charset.forName("UTF-8"));

      String from = lines.get(0);
      String to = lines.get(1);
      String subject = lines.get(2);

      StringBuilder builder = new StringBuilder();
      for (int i = 3; i < lines.size(); i++)
      {
          builder.append(lines.get(i));
          builder.append("\n");
      }

      Console console = System.console();
      String password = new String(console.readPassword("Password: "));

      Session mailSession = Session.getDefaultInstance(props);
      // mailSession.setDebug(true);
      MimeMessage message = new MimeMessage(mailSession);
      message.setFrom(new InternetAddress(from));
      message.addRecipient(RecipientType.TO, new InternetAddress(to));
      message.setSubject(subject);
      message.setText(builder.toString());
      Transport tr = mailSession.getTransport();
      tr.connect(null, password);
      tr.sendMessage(message, message.getAllRecipients());
      tr.close();
  }
}
```

该组织遵循了微软非常成功的 `ODBC` 模型，该模型为数据库访问提供了一个 C 语言接口。`JDBC` 和 `ODBC` 都基于相同的理念：根据 API 编写程序与驱动程序管理器通信，而驱动程序管理器又使用驱动程序与实际数据库通信。

这意味着 `JDBC` API 是大多数程序员需要处理的所有内容。

### 5.1.1 JDBC 驱动程序类型

`JDBC` 规范将驱动程序分类为以下类型：

- `第 1 型驱动程序（type 1 driver）`将 `JDBC` 翻译为 `ODBC`，并依赖 `ODBC` 驱动程序与数据库通信。Java 的早期版本包含了这样一个驱动程序，即 `JDBC/ODBC 桥接`。然而，该桥接需要部署并正确配置 `ODBC` 驱动程序。当 `JDBC` 最初发布时，该桥接对于测试非常方便，但它从未用于生产环境。此时，已经有了许多更好的驱动程序可用，且 Java 8 不再提供 `JDBC/ODBC 桥接`。

- `第 2 型驱动程序（type 2 driver）`部分用 Java 编写，部分用本地代码编写；它与数据库的客户端 API 通信。使用此类驱动程序时，除了 Java 库外，你必须在客户端安装某些针对特定平台的代码。

- `第 3 型驱动程序（type 3 driver）`是一个纯 Java 客户端库，它使用与数据库无关的协议将请求发送到服务器组件，由该组件将请求翻译为特定数据库的协议。这简化了部署，因为特定平台的代码仅位于服务器上。

- `第 4 型驱动程序（type 4 driver）`是一个纯 Java 库，它直接将 `JDBC` 请求翻译为特定数据库的协议。

***

![Image](img/00002.jpeg) 注意

`JDBC` 规范可以在 `http://download.oracle.com/otndocs/jcp/jdbc-4_2-mrel2-spec/` 找到。

***

大多数数据库供应商都会随其数据库提供`第 3 型`或`第 4 型`驱动程序。此外，还有许多第三方公司专门生产具有更好标准合规性、更多平台支持、更好性能，或者在某些情况下仅仅比数据库供应商提供的驱动程序更具可靠性的驱动程序。

总结来说，`JDBC` 的最终目标是实现以下目标：

- 程序员可以使用 Java 语言编写应用程序，使用标准 SQL 语句（甚至是 SQL 的特殊扩展）访问任何数据库，同时仍然遵循 Java 语言规范。
- 数据库供应商和数据库工具供应商可以提供底层驱动程序。这样，他们就可以针对自己的特定产品优化驱动程序。

***

![Image](img/00002.jpeg) 注意

如果你好奇 Java 为什么不直接采用 `ODBC` 模型，根据 1996 年 JavaOne 大会给出的理由：

- `ODBC` 很难学习。
- `ODBC` 的某些命令带有许多复杂的选项。Java 编程语言的优选风格是拥有简单且直观的方法，并且要尽可能多。
- `ODBC` 依赖于 `void*` 指针和其他 C 语言特性，这些特性在 Java 编程语言中并不自然。
- 基于 `ODBC` 的解决方案本质上安全性较低，且比纯 Java 解决方案更难部署。

***

#### 5.1.2 JDBC 的典型用途

传统的客户端/服务器模型在客户端拥有丰富的 GUI，在服务器拥有数据库（参见图 5.1）。在这种模型中，`JDBC` 驱动程序部署在客户端上。

![Image](img/00087.jpeg)

**图 5.1** 传统的客户端/服务器应用程序

然而，现在更常见的是三层模型，客户端应用程序不进行数据库调用。相反，它调用服务器上的中间件层，由中间件层执行数据库查询。三层模型有几个优势。它将`视觉呈现`（在客户端）与`业务逻辑`（在中间层）以及原始数据（在数据库中）分离开。因此，可以从多个客户端（如 Java 桌面应用程序、网页浏览器或移动应用）访问相同的数据和相同的业务规则。

客户端与中间层之间的通信通常通过 HTTP 进行。`JDBC` 管理中间层与后端数据库之间的通信。图 5.2 显示了基本架构。

![Image](img/00088.jpeg)

**图 5.2** 三层应用程序

## 5.2 结构化查询语言

`JDBC` 让你可以使用 SQL 与数据库通信，SQL 是本质上所有现代关系型数据库的命令语言。桌面数据库通常具有允许用户直接操作数据的 GUI，但基于服务器的数据库纯粹通过 SQL 访问。

`JDBC` 包可以被认为仅仅是向数据库通信 SQL 语句的 API。我们将在本节中简要介绍 SQL。如果你以前从未见过 SQL，你可能觉得这些材料不够。如果是这样，请转向该主题的许多学习资源之一；我们推荐 Alan Beaulieu 编写的 *Learning SQL*（O’Reilly, 2009）或位于 `http://sql.learncodethehardway.org/` 的在线书籍 *Learn SQL The Hard Way*。

你可以将数据库想象成一组带有行和列的命名表。每一列都有一个`列名`。每行都包含一组相关数据。

作为本书的示例数据库，我们使用了一组描述计算机科学书籍的表（参见表 5.1 到 5.4）。

![Image](img/00089.jpeg)

**表 5.1** Authors 表

![Image](img/00090.jpeg)

**表 5.2** Books 表

![Image](img/00091.jpeg)

**表 5.3** Books 表

![Image](img/00092.jpeg)

**表 5.4** Publishers 表

图 5.3 显示了 `Books` 表的视图。图 5.4 显示了该表与 `Publishers` 表连接的结果。`Books` 表和 `Publishers` 表各包含一个出版者的标识符。当我们根据出版者代码对两者连接时，我们得到了由连接表组成的`查询结果`。结果中的每行都包含有关书籍的信息，以及出版者名称和网页 URL。注意，由于有许多行相同的出版者，出版者名称和 URL 在多行中重复。

![Image](img/00093.jpeg)

**图 5.3** 包含书籍的示例

![Image](img/00094.jpeg)

**图 5.4** 连接的两个表

按照惯例，SQL 关键字使用大写字母，尽管这并非必须。

`SELECT` 语句非常灵活。你可以仅通过以下查询选择 `Books` 表中的所有行：

```sql
SELECT * FROM Books
```

每个 SQL `SELECT` 语句都必须包含 `FROM` 子句。它告诉数据库应该检查哪些表来查找数据。

你可以选择你需要的列：

```sql
SELECT ISBN, Price, Title
FROM Books
```

你可以使用 `WHERE` 子句来限制结果中的行数：

```sql
SELECT ISBN, Price, Title
FROM Books
WHERE Price <= 29.95
```

请注意“等号”比较。SQL 使用 `=` 和 `<>` 进行等性测试，而不是像 Java 编程语言中的 `==` 或 `!=`。

***

![Image](img/00002.jpeg) 注意

某些数据库供应商支持使用 `!=` 进行不等性测试。这并不是标准 SQL，因此我们建议不要使用。

***

`WHERE` 子句还可以通过 `LIKE` 算符使用模式匹配。然而，通配符并不是通常的 `*` 和 `?`。使用 `%` 表示零或多个字符，使用 `_` 表示单个字符。例如：

```sql
SELECT ISBN, Price, Title
FROM Books
WHERE Title NOT LIKE '%x%'
```

这会排除包含 Unix 或 Linux 等单词的书籍。注意，字符串包含在单引号中，而不是双引号。字符串内部的单引号用一对单引号表示。例如：

```sql
SELECT Title
FROM Books
WHERE Title LIKE '%''%'
```

这会报告所有包含单引号的标题。

你可以从多个表中选择数据：

```sql
SELECT * FROM Books, Publishers
```

如果没有 `WHERE` 子句，这个查询将毫无意义。它列出了两个表的行组合。在我们的案例中，`Books` 有 20 行，`Publishers` 有 8 行，结果是一个包含 20 × 8 条记录的行集，并且有大量重复。我们真的希望限制查询，说明我们只对与其对应的书籍感兴趣：

```sql
SELECT * FROM Books, Publishers
WHERE Books.Publisher_Id = Publishers.Publisher_Id
```

该查询有 20 行，每本书对应一行，因为每本书在 `Publisher` 表中都对应一个出版社。

每当你在查询中使用多个表时，相同的列名可能会出现在两个不同的地方。这在我们的示例中就发生了。`Books` 和 `Publishers` 表中都有一个名为 `Publisher_Id` 的列。当产生歧义时，你必须使用所属表的名称作为每个列名的前缀，例如 `Books.Publisher_Id`。

你也可以使用 SQL 来更改数据库内部的数据。例如，假设你想将所有标题中包含“C++”的书籍当前价格降低 5.00 美元：

```sql
UPDATE Books
SET Price = Price - 5.00
WHERE Title LIKE '%C++%'
```

同样，要删除所有的 C++ 书籍，请使用 `DELETE` 查询：

```sql
DELETE FROM Books
WHERE Title LIKE '%C++%'
```




SQL 带有内置函数，用于计算平均值、查找列中的最大值和最小值等，我们在这里不进行讨论。通常，要向表中插入值，你可以使用 `INSERT` 语句：

点击此处查看代码图片

```sql
INSERT INTO Books
VALUES ('A Guide to the SQL Standard', '0-201-96426-0', '0201', 47.95)
```

对于表中插入的每行，你都需要单独的 `INSERT` 语句。

当然，在查询、修改和插入数据之前，你必须有一个存储数据的地方。使用 `CREATE TABLE` 语句创建一个新表。为每列指定名称和数据类型。例如：

点击此处查看代码图片

```sql
CREATE TABLE Books
(
   Title CHAR(60),
   ISBN CHAR(13),
   Publisher_Id CHAR(6),
   Price DECIMAL(10,2)
)
```

表 5.5 显示了常见的 SQL 类型。

![Image](img/0009.jpeg)

**表 5.5 常见数据类型**

使用 `CREATE TABLE` 语句创建一个新表。为每列指定名称和数据类型。例如：

### 5.3 配置

在查询、修改和插入数据之前，你必须有一个存储数据的地方。使用 `CREATE TABLE` 语句创建一个新表。为每列指定名称和数据类型。例如：

### 5.3.3 启动数据库服务器

1. 找到 `derbyrun.jar` 文件。在某些版本的 JDK 中，它位于 `jdk/db/lib` 目录下。如果那里没有，请在 Apache Derby 安装目录下查找该 JAR 文件。我们将包含 `lib/derbyrun.jar` 的目录标记为 `derby`。

2. 运行命令：

```bash
java -jar derby/lib/derbyrun.jar server start
```

3. 再次检查数据库是否运行正常。创建一个名为 `ij.properties` 的文件，其内容包含以下几行：

```properties
ij.driver=org.apache.derby.jdbc.ClientDriver
ij.protocol=jdbc:derby://localhost:1527/
ij.database=COREJAVA;create=true
```

在另一个命令行窗口中，执行以下命令运行 Derby 的交互式脚本工具（称为 `ij`）：

```bash
java -jar derby/lib/derbyrun.jar ij -p ij.properties
```

现在你可以发布如下 SQL 命令：

```sql
CREATE TABLE Greetings (Message CHAR(20));
INSERT INTO Greetings VALUES ('Hello, World!');
SELECT * FROM Greetings;
DROP TABLE Greetings;
```

注意，每个命令必须以分号结束。如需退出，请输入：

```sql
EXIT;
```

4. 完成数据库操作后，使用命令停止服务器：

```bash
java -jar derby/lib/derbyrun.jar server shutdown
```

如果你使用其他数据库，需要查阅文档以了解如何启动和停止你的数据库，以及如何连接它并发布 SQL 命令。

#### 5.3.4 注册驱动类

许多 JDBC JAR 文件（例如 Java SE 8 包含的 Derby 驱动）会自动注册驱动类。在这种情况下，你可以跳过在本节中描述的手动注册步骤。如果 JAR 文件包含文件 `META-INF/services/java.sql.Driver`，则它可以自动注册驱动类。你只需简单地解压驱动程序的 JAR 文件进行检查。

> **注意**：![Image](img/00002.jpeg) 此注册机制使用了 JAR 规范中一个鲜为人知的部分；请参见 `http://docs.oracle.com/javase/8/docs/technotes/guides/jar/jar.html#Service%20Provider`。自动注册是 JDBC4 兼容驱动程序的要求。

如果你的驱动程序 JAR 文件不支持自动注册，你需要找到供应商所使用的 JDBC 驱动类名称。典型的驱动程序名称为：

```text
org.apache.derby.jdbc.ClientDriver
org.postgresql.Driver
```

通过 `DriverManager` 注册驱动有两种方法。一种方法是在你的 Java 程序中加载驱动类。例如：

```java
Class.forName("org.postgresql.Driver"); // 强制加载驱动类
```

该语句会导致驱动类被加载，从而执行用于注册驱动的静态初始化器。

或者，你可以设置 `jdbc.drivers` 属性。你可以通过命令行参数指定该属性，例如：

```bash
java -Djdbc.drivers=org.postgresql.Driver ProgramName
```

或者，你的应用程序可以通过如下调用设置系统属性：

```java
System.setProperty("jdbc.drivers", "org.postgresql.Driver");
```

你也可以提供多个驱动程序；用冒号分隔，例如：

```text
org.postgresql.Driver:org.apache.derby.jdbc.ClientDriver
```

#### 5.3.5 连接到数据库

在你的 Java 程序中，如下打开数据库连接：

```java
String url = "jdbc:postgresql:COREJAVA";
String username = "dbuser";
String password = "secret";
Connection conn = DriverManager.getConnection(url, username, password);
```

驱动管理器会遍历已注册的驱动，以寻找可以使用数据库 URL 中指定的子协议的驱动程序。

`getConnection` 方法返回一个 `Connection` 对象。在接下来的章节中，你将看到如何使用 `Connection` 对象来执行 SQL 语句。

要连接数据库，你需要数据库的用户名和密码。

> **注意**：![Image](img/00002.jpeg) 默认情况下，Derby 允许使用任何用户名连接，且不检查密码。为每个用户都会生成一套独立的表。默认用户名为 `app`。

列表 5.1 中的测试程序演示了这些步骤。它从名为 `database.properties` 的文件中加载连接参数并连接到数据库。示例代码提供的 `database.properties` 文件包含 Derby 数据库的连接信息。如果你使用不同的数据库，请将特定数据库的连接信息放入该文件。以下是连接 PostgreSQL 数据库的示例：

```properties
jdbc.drivers=org.postgresql.Driver
jdbc.url=jdbc:postgresql:COREJAVA
jdbc.username=dbuser
jdbc.password=secret
```

连接到数据库后，测试程序执行以下语句：

```sql
CREATE TABLE Greetings (Message CHAR(20))
INSERT INTO Greetings VALUES ('Hello, World!')
SELECT * FROM Greetings
```

`SELECT` 语句的结果将被打印出来，你应该看到输出 `Hello, World!`。然后通过执行语句 `DROP Greetings` 移除表。

要运行此测试，请启动之前描述的数据库，并启动程序：

```bash
java -classpath .:JAR test.TestDB
```

（一如既往，Windows 用户需要使用 `;` 代替 `:` 来分隔路径元素。）

> **提示**：![Image](img/00003.jpeg) 调试 JDBC 相关问题的方法是启用跟踪。调用 `DriverManager.setWriter` 方法将跟踪消息发送 `PrintWriter`。跟踪输出包含了详细列表。大多数 JDBC 驱动实现都提供了额外的跟踪机制。例如，对于 Derby，你可以在 JDBC URL 中添加 `traceFile` 选项：`jdbc:derby://localhost:1527/COREJAVA;create=true;traceFile=trace.out`。

**列表 5.1** `test/TestDB.java`

```java
package test;

import java.nio.file.*;
import java.sql.*;
import java.io.*;
import java.util.*;

/**
 * 该程序测试数据库和 JDBC 驱动是否配置正确。
 * @version 1.0 2012-06-05
 * @author Cay Horstmann
 */
public class TestDB
{
    public static void main(String args[]) throws IOException
    {
        try {
            runTest();
        } catch (SQLException ex) {
            for (Throwable t : ex)
                t.printStackTrace();
        }
    }

    /**
     * 通过创建表、添加值、显示表内容和移除表来
     * 运行测试。
     */
    public static void runTest() throws SQLException, IOException
    {
        try (Connection conn = getConnection();
             Statement stat = conn.createStatement())
        {
            stat.executeUpdate("CREATE TABLE Greetings (Message CHAR(20))");
            stat.executeUpdate("INSERT INTO Greetings VALUES ('Hello, World!')");

            try (ResultSet result = stat.executeQuery("SELECT * FROM Greetings"))
            {
                if (result.next())
                    System.out.println(result.getString(1));
            }

            stat.executeUpdate("DROP TABLE Greetings");
        }
    }

    /**
     * 从 database.properties 文件指定的属性获取数据库连接。
     * @return 数据库连接
     */
    public static Connection getConnection() throws SQLException, IOException
    {
        Properties props = new Properties();

        try (InputStream in = Files.newInputStream(Paths.get("database.properties")))
        {
            props.load(in);
        }

        String drivers = props.getProperty("jdbc.drivers");
        if (drivers != null)
            System.setProperty("jdbc.drivers", drivers);

        String url = props.getProperty("jdbc.url");
        String username = props.getProperty("jdbc.username");
        String password = props.getProperty("jdbc.password");

        return DriverManager.getConnection(url, username, password);
    }
}
```

`java.sql.DriverManager`

**1.1**

- `static Connection getConnection(String url, String user, String password)` 建立到给定数据库的连接并返回一个 `Connection` 对象。

### 5.4 使用 JDBC 语句

在后续章节中，你将看到如何使用 JDBC `Statement` 来执行 SQL 语句、获取结果并处理错误。然后我们将向你展示一个用于填充数据库的简单程序。

#### 5.4.1 执行 SQL 语句

要执行 SQL 语句，首先需要创建一个 `Statement` 对象。要创建语句对象，请使用从调用 `DriverManager.getConnection` 获取的 `Connection` 对象。

点击此处查看代码图片

```java
Statement stat = conn.createStatement();
```

接下来将你想执行的语句放入字符串中，例如：

点击此处查看代码图片

```java
String command = "UPDATE Books"
    + " SET Price = Price - 5.00"
    + " WHERE Title NOT LIKE '%Introduction%'";
```

然后调用 `Statement` 接口的 `executeUpdate` 方法：

```java
stat.executeUpdate(command);
```

`executeUpdate` 方法返回受该 SQL 语句影响的行数，对于不返回行数的语句则返回 0。例如，上一个示例中的 `executeUpdate` 调用返回了价格降低了 5.00 美元的行数。

`executeUpdate` 方法可以执行如 `INSERT`、`UPDATE` 和 `DELETE` 等操作，以及数据定义语句（如 `CREATE TABLE` 和 `DROP TABLE`）。然而，你需要使用 `executeQuery` 方法来执行 `SELECT` 查询。还有一个通用的 `execute` 语句可以执行任意的 SQL 语句。它通常仅用于执行用户交互式提供的查询。

当你执行查询时，你感兴趣的是结果。`executeQuery` 方法返回一个类型为 `ResultSet` 的对象，你可以用它来逐行遍历结果。

点击此处查看代码图片

```java
ResultSet rs = stat.executeQuery("SELECT * FROM Books");
```

分析结果集的基本循环如下：

点击此处查看代码图片

```java
while (rs.next()) {
    // 处理结果
}
```




`ResultSet` 接口与 `java.util.Iterator` 有细微不同。`next` 方法将光标移动到下一行。你必须调用 `next` 才能移动到第一行。

返回或更新给定列索引或标签的列的值，并将其转换为指定的类型。列标签是 SQL `AS` 子句中指定的标签，或者在未使用 `AS` 时使用列名。

- `int findColumn(String columnName)`  
  返回与列名关联的列索引。
- `void close()`  
  立即关闭当前的结果集。
- `boolean isClosed()` **6**  
  如果此语句已关闭，则返回 `true`。

---

#### 5.4.2 管理连接、语句和结果集

每个 `Connection` 对象都可以创建一个或多个 `Statement` 对象。你可以对同一个 `Statement` 对象执行多个互不相关的命令和查询。然而，一个语句最多只能打开一个结果集。如果你并发发布了多个查询并同时分析它们的分析结果，那么你需要多个 `Statement` 对象。

不过请注意，至少有一个常用的数据库（Microsoft SQL Server）的 JDBC 驱动程序一次只允许运行一个活动语句。请使用 `DatabaseMetaData` 接口的 `getMaxStatements` 方法来查找你的 JDBC 驱动程序支持的并发打开语句的数量。

这听起来很有限制性，但在实践中，你可能不需要纠结于多个并发的结果集。如果结果集之间是相关的，你应该能够发布一个组合查询并分析单个结果。让数据库合并查询要比让 Java 程序遍历多个结果集要高效得多。

当你完成对 `ResultSet`、`Statement` 或 `Connection` 的使用后，应该立即调用 `close` 方法。这些对象使用了大型数据结构，消耗数据库服务器的有限资源。

`Statement` 对象的 `close` 方法在语句具有已打开的结果集时，会自动关闭关联的结果集。同样，`Connection` 类的 `close` 方法会关闭该连接的所有所有语句。

相反，从 Java SE 7 开始，你可以在 `Statement` 上调用 `closeOnCompletion` 方法，它会在所有结果集都关闭后自动关闭该语句。

如果你的连接是短命的，你就不需要担心关闭语句和结果集了。为了绝对确保连接对象不会保持打开状态，请使用 `try`-with-resources 语句：

```java
try (Connection conn = . . .)
{
    Statement stat = conn.createStatement();
    ResultSet result = stat.executeQuery(queryString);
    process query result
}
```

---

![Image](img/00003.jpeg) 提示

使用 `try`-with-resources 块仅关闭连接，并使用独立的 `try`/`catch` 块来处理异常。分离 `try` 块使你的代码更容易于读和维护。

---

#### 5.4.3 分析 SQL 异常

每个 `SQLException` 都有一个 `SQLException` 对象链，可以通过 `getNextException` 方法获取。这个异常链是在每个异常都拥有的 `Throwable` 对象“原因”链之外的。（有关 Java 异常的细节请参见第一卷第 11 章）。需要两个嵌套循环才能完全枚举所有这些异常。幸运的是，Java SE 6 增强了 `SQLException` 类以实现 `Iterable<Throwable>` 接口。`iterator()` 方法产生一个 `Iterator<Throwable>`，它可以遍历这两个链：从遍历第一个 `SQLException` 的原因链开始，然后移动到下一个 `SQLException`，以此依此类推。你可以简单地使用增强型 `for` 循环：

```java
for (Throwable t : sqlException)
{
    do something with t
}
```

你可以在 `SQLException` 上调用 `getSQLState` 和 `getErrorCode` 来进一步分析它。第一个方法产生一个由 X/Open 或 SQL:2003 标准化的字符串。（调用 `DatabaseMetaData` 接口的 `getSQLStateType` 方法可以确定你的驱动程序使用的是哪种标准。）错误代码是厂商特定的。

SQL 异常组织在继承树中（见图 5.5](#part0010.html_ch05fig05)）。这允许你以独立厂商的方式捕特定的错误类型。

![Image](img/00096.jpeg)

**图 5.5** SQL 异常类型

此外，数据库驱动程序可以将非致命条件报告为警告。你可以从连接、语句和结果集中检索警告。`SQLWarning` 类是 `SQLException` 的子类（尽管 `SQLWarning` 不会作为异常抛出）。调用 `getSQLState` 和 `getErrorCode` 获取有关警告的进一步信息。与 SQL 异常类似，警告也是链状的。要检索所有警告，请使用此循环：

```java
SQLWarning w = stat.getWarning();

while (w != null)
{
    do something with w
    w = w.nextWarning();
}
```

`SQLWarning` 的子类 `DataTruncation` 用于从数据库读取数据时发生意外截断的情况。如果在更新语句中发生数据截断，则会作为异常抛出 `DataTruncation`。

##### `SQLException`

- `getNextException()`  
  获取链在此异常之后的下一个异常，或在链的末尾返回 `null`。
- `iterator()`  
  产生链式异常及其原因。
- `String getSQLState()`  
  获取“SQL state”——一个标准的错误代码。
- `int getErrorCode()`  
  获取厂商特定的错误代码。

##### `SQLWarning`

- `getNextWarning()`  
  返回与此警告链在下一个警告，或在链的末尾返回 `null`。

##### `Connection`、`Statement`、`ResultSet`

- `getWarnings()`  
  返回第一个警告，如果没有挂起的警告则返回 `null`。

##### `DataTruncation`

- `boolean getParameter()`  
  如果截断适用于参数则返回 `true`，如果适用于列则返回一个 `false`。
- `int getIndex()`  
  返回截断参数或列的索引。
- `int getDataSize()`  
  返回应该传输的字节数，如果未知则返回 `-1`。
- `int getTransferSize()`  
  返回实际传输的字节数，如果未知则返回 `-1`。

---

#### 5.4.4 填充数据库

我们现在准备好编写第一个 JDBC 程序了。当然，如果能尝试我们之前讨论的那些复杂的查询就好了，但我们遇到了一个问题：目前数据库中没有数据。我们需要填充数据库，而使用一组 SQL 指令来创建表并向其中插入数据是一种简单的方法。

因此，我们将使用 JDBC 创建一个简单的程序，读取 SQL 指令文件（每行一条指令）并执行它们。

具体来说，程序从格式如下的文本文件中读取数据：

```sql
CREATE TABLE Publishers (Publisher_Id CHAR(6), Name CHAR(30), URL CHAR(80));

INSERT INTO Publishers VALUES ('0201', 'Addison-Wesley', 'www.aw-bc.com');

INSERT INTO Publishers VALUES ('0471', 'John Wiley & Sons', 'www.wiley.com');
```

列表 5.2 包含了读取 SQL 语句文件并执行这些语句程序代码。你不需要阅读代码；我们只是提供该程序以便你可以填充数据库并运行本章剩余部分的示例。

请确保你的数据库服务器正在运行，并按照以下方式运行程序：

```bash
java -classpath driverPath:. exec.ExecSQL Books.sql
java -classpath driverPath:. exec.ExecSQL Authors.sql
java -classpath driverPath:. exec.ExecSQL Publishers.sql
java -classpath driverPath:. exec.ExecSQL BooksAuthors.sql
```

在运行程序之前，请检查 `database.properties` 文件是否已为你的环境正确配置（参见第 5.3.5 节“连接到数据库，”，位于第 294 页）。

---

![Image](img/00002.jpeg) **注意**

你的数据库可能也有一个直接读取 SQL 文件的工具。例如，使用 Derby，你可以运行：

```bash
java -jar *derby*/lib/derbyrun.jar ij -p ij.properties Books.sql
```

（`ij.properties` 文件在第 5.3.3 节“启动数据库，”位于第 293 页中。）

在 `ExecSQL` 命令的数据格式中，我们允许在每行末尾可选分号，因为大多数数据库工具都期望这种格式。

以下步骤简要描述了 `ExecSQL` 程序：

1. 连接到数据库。`getConnection` 方法读取 `database.properties` 文件中的属性，并将 `jdbc.drivers` 属性添加到系统属性中。驱动管理器使用 `jdbc.drivers` 属性加载相应的数据库驱动程序。`getConnection` 方法使用 `jdbc.url`、`jdbc.username` 和 `jdbc.password` 属性打开数据库连接。
2. 打开包含 SQL 语句的文件。如果没有提供文件名，则提示用户在控制台上输入语句。
3. 使用通用的 `execute` 方法执行每个语句。如果返回 `true`，则该语句有一个结果集。我们为书籍数据库提供的四个 SQL 文件都以 `SELECT *` 语句结束，以便你可以看到数据已成功插入。
4. 如果存在结果集，则打印结果。由于这是一个通用的结果集，我们需要使用元数据来确定结果有多少列。欲需更多信息，请参见第 5.8 节“元数据，”，位于第 333 页。
5. 如果发生任何 SQL 异常，打印该异常以及其中可能包含任何链异常。
6. 关闭与数据库的连接。

列表 5.2 显示了程序的代码。

**列表 5.2** `exec/ExecSQL.java`

```java
package exec;

import java.io.*;

import java.nio.file.*;

import java.util.*;

import java.sql.*;

/**
 * 执行文件中所有的 SQL 语句。按如下调用此程序
 * java-classpath driverPath:. ExecSQL commandFile <br>
 *
 * @version 1.32 2016-04-27
 * @author Cay Horstmann
 */

class ExecSQL
{
    public static void main(String args[]) throws IOException
    {
        try (Scanner in = args.length == 0 ? new Scanner(System.in)
                : new Scanner(Paths.get(args[0]), "UTF-8"))
        {
            try (Connection conn = getConnection();
                  Statement stat = conn.createStatement())
            {
                while (true)
                {
                    if (args.length == 0) System.out.println("Enter command or EXIT to exit:");
                    if (!in.hasNextLine()) return;

                    String line = in.nextLine().trim();

                    if (line.equalsIgnoreCase("EXIT")) return;

                    if (line.endsWith(";")) // remove semicolon
                    {
                        line = line.substring(0, line.length() - 1);
                    }

                    try
                    {
                        boolean isResult = stat.execute(line);

                        if (isResult)
                        {
                            try (ResultSet rs = stat.getResultSet())
                            {
                                showResultSet(rs);
                            }
                        }
                        else
                        {
                            int updateCount = stat.getUpdateCount();
                            System.out.println(updateCount + " rows updated");
                        }
                    }
                    catch (SQLException ex)
                    {
                        for (Throwable e : ex)
                        {
                            e.printStackTrace();
                        }
                    }
                }
            }
        }
        catch (SQLException e)
        {
            for (Throwable t : e)
            {
                t.printStackTrace();
            }
        }
    }

    /**
     * 从 database.properties 文件获取连接。
     * @return the connection
     */

    public static Connection getConnection() throws SQLException, IOException
    {
        Properties props = new Properties();

        try (InputStream in = Files.newInputStream(Paths.get("database.properties")))
        {
            props.load(in);
        }

        String drivers = props.getProperty("jdbc.drivers");
        if (drivers != null) System.setProperty("jdbc.drivers", drivers);

        String url = props.getProperty("jdbc.url");
        String username = props.getProperty("jdbc.username");
        String password = props.getProperty("jdbc.password");

        return DriverManager.getConnection(url, username, password);
    }

    /**
     * 打印结果集。
     * @param result the result set to be printed
     */
```



```java
public static void showResultSet(ResultSet rs) throws SQLException {
    ResultSetMetaData metaData = rs.getMetaData();
    int columnCount = metaData.getColumnCount();

    while (rs.next()) {
        for (int i = 1; i <= columnCount; i++) {
            if (i > 1) System.out.print(", ");
            System.out.print(rs.getString(i));
        }
        System.out.println();
    }
}
```

### 5.5 查询执行

在本节中，我们将编写一个针对 `COREJAVA` 数据库执行查询的程序。为了使此程序运行，你按照前面的章节所述为 `COREJAVA` 数据库填充了表。

查询数据库时，你可以选择作者和出版社，或者任选其一为 `Any`。

你还可以更改数据库中的数据。选择一个出版社并输入金额。该出版社的所有价格将根据你输入的金额进行调整，程序将显示更新了多少行。更改价格后，你可能想运行查询来验证新价格。

#### 5.5.1 准备语句

在这个程序中，我们使用了一个新特性：准备语句。考虑对特定出版社（不考虑作者）书籍的查询。SQL 语句如下：

```sql
SELECT Books.Price, Books.Title
FROM Books, Publishers
WHERE Books.Publisher_Id = Publishers.Publisher_Id
AND Publishers.Name = the name from the list box
```

与其在每次用户启动此类查询时都构建一个独立的查询语句，不如 `prepare` 一个带有宿主机变量的查询，并多次使用它，每次为该变量填充不同的字符串。这种技术有利于提高性能。每当数据库执行查询时，它会首先计算出如何高效执行的策略。通过准备查询并重用它，你可以确保规划步骤只执行一次。

预处理查询中的每个宿主机变量都用 `?` 标出。如果有多个变量，在设置值时你必须跟踪 `?` 的位置。例如，我们的预处理查询变为：

点击此处查看代码图像

```java
String publisherQuery =
    "SELECT Books.Price, Books.Title" +
    " FROM Books, Publishers" +
    " WHERE Books.Publisher_Id = Publishers.Publisher_Id AND Publishers.Name = ?";

PreparedStatement stat = conn.prepareStatement(publisherQuery);
```

在执行预处理语句之前，你必须使用 `set` 方法将宿主机变量绑定到实际值。与 `ResultSet` 接口的 `get` 方法一样，针对不同的类型有不同的 `set` 方法。在这里，我们想要为出版社名称设置一个字符串。

```java
stat.setString(1, publisher);
```

第一个参数是我们想要设置的宿主机变量的位置数字。位置 `1` 表示第一个 `?`。第二个参数是我们想要赋值给宿主机变量的值。

如果你重用一个已经执行过的预处理查询，除非你使用 `set` 方法更改它们或调用 `clearParameters` 方法，否则所有宿主机变量都将保持绑定状态。这意味着你只需要对那些在从一次查询到下一次查询之间发生变化的宿主机变量调用 `setXxx` 方法。

一旦所有变量都绑定了值，你就可以执行该预处理语句了：

点击此处查看代码图像

```java
ResultSet rs = stat.executeQuery();
```

> **提示**
>
> 通过拼接字符串手动构建查询是枯燥且具有潜在危险的。你必须担心引号等特殊字符，如果你的查询涉及用户输入，你还必须防范注入攻击。因此，当你的查询涉及变量时，你应该使用预处理语句。

价格更新功能是通过一个 `UPDATE` 语句实现的。注意我们调用的是 `executeUpdate` 而不是 `executeQuery`，因为 `UPDATE` 语句不返回结果集。`executeUpdate` 的返回值是被修改的行数。

点击此处查看代码图像

```java
int r = stat.executeUpdate();
System.out.println(r + " rows updated");
```

> **注意**
>
> `PreparedStatement` 对象在关联的 `Connection` 对象关闭后失效。然而，许多数据库会自动缓存预处理语句。如果同一个查询被准备了两次，数据库只会重用该查询策略。因此，不要担心调用 `prepareStatement` 的开销。

下面的列表简要描述了示例程序的结构。

- 作者和出版社数组通过运行两个查询来填充，这两个查询返回数据库中所有的作者和出版社名称。
- 涉及作者的查询是复杂的。一本书可以有多个作者，因此 `BooksAuthors` 表存储了作者与书之间的对应关系。例如，ISBN 为 `0-201-96426-0` 的书有两个代码为 `DATE` 和 `DARW` 的作者。`BooksAuthors` 表有以下行：

点击此处查看代码图像

```text
0-201-96426-0, DATE, 1
0-201-96426-0, DARW, 2
```

第三列列出了作者的顺序。（我们不能直接使用表中的行位置，因为关系型表中没有固定的行顺序。）因此，查询必须连接 `Books`、`BooksAuthors` 和 `Authors` 表，将作者名称与用户选择的名称进行比较。

点击此处查看代码图像

```sql
SELECT Books.Price, Books.Title
FROM Books, BooksAuthors, Authors, Publishers
WHERE Authors.Author_Id = BooksAuthors.Author_Id
AND BooksAuthors.ISBN = Books.ISBN
AND Books.Publisher_Id = Publishers.Publisher_Id
AND Authors.Name = ?
AND Publishers.Name = ?
```

> **提示**
>
> 一些 Java 程序员会避免像这样复杂的 SQL 语句。一种意料之外但非常低效的变通是编写大量的 Java 代码来遍历多个结果集。但数据库执行查询代码的能力比 Java 程序要强得多——这是数据库的核心竞争力。一个法则是：如果你可以在 SQL 中完成，就不要在 Java 中完成。

- `changePrices` 方法执行一个 `UPDATE` 语句。注意 `UPDATE` 语句的 `WHERE` 子句需要出版社代码，而我们只知道出版社名称。这个问题通过嵌套子查询解决：

点击此处查看代码图像

```sql
UPDATE Books
SET Price = Price + ?
WHERE Books.Publisher_Id = (
    SELECT Publisher_Id
    FROM Publishers
    WHERE Name = ?
)
```

Listing 5.3 是完整的程序代码。

**Listing 5.3** `query/QueryTest.java`

```java
while (rs.next()) {
    publishers.add(rs.getString(1));
}

boolean done = false;
while (!done) {
    System.out.print("Q)uery C)hange prices E)xit: ");
    String input = in.next().toUpperCase();

    if (input.equals("Q"))
        executeQuery(conn);
    else if (input.equals("C"))
        changePrices(conn);
    else
        done = true;
}

catch (SQLException e) {
    for (Throwable t : e)
        System.out.println(t.getMessage());
}

/**
 * 执行选定的查询。
 * @param conn 数据库连接
 */
private static void executeQuery(Connection conn) throws SQLException {
    String author = select("作者:", authors);
    String publisher = select("Publishers:", publishers);
    PreparedStatement stat;

    if (!author.equals("Any") && !publisher.equals("Any")) {
        stat = conn.prepareStatement(authorPublisherQuery);
        stat.setString(1, author);
        stat.setString(2, publisher);
    } else if (!author.equals("Any") && publisher.equals("Any")) {
        stat = conn.prepareStatement(authorQuery);
        stat.setString(1, author);
    } else if (author.equals("Any") && !publisher.equals("Any")) {
        stat = conn.prepareStatement(publisherQuery);
        stat.setString(1, publisher);
    } else {
        stat = conn.prepareStatement(allQuery);
    }

    try (ResultSet rs = stat.executeQuery()) {
        while (rs.next())
            System.out.println(rs.getString(1) + ", " + rs.getString(2));
    }
}

/**
 * 执行更新语句更改价格。
 * @param conn 数据库连接
 */
public static void changePrices(Connection conn) throws SQLException {
    String publisher = select("出版社:", publishers.subList(1, publishers.size()));
    System.out.print("通过以下项更改价格: ");
    double priceChange = in.nextDouble();

    PreparedStatement stat = conn.prepareStatement(priceUpdate);
    stat.setDouble(1, priceChange);
    stat.setString(2, publisher);

    int r = stat.executeUpdate();
    System.out.println(r + " 条记录已更新.");
}

/**
 * 请求用户选择一个字符串。
 * @param prompt 要显示的提示信息
 * @param options 用户可以从中选择的选项
 * @return 用户选择的选项
 */
public static String select(String prompt, List<String> options) {
    while (true) {
        System.out.println(prompt);

        for (int i = 0; i < options.size(); i++)
            System.out.printf("%2d) %s%n", i + 1, options.get(i));

        int sel = in.nextInt();
        if (sel > 0 && sel <= options.size())
            return options.get(sel - 1);
    }
}

/**
 * 从 database.properties 文件指定的属性获取连接。
 * @return 数据库连接
 */
public static Connection getConnection() throws SQLException, IOException {
    Properties props = new Properties();

    try (InputStream in = Files.newInputStream(Paths.get("database.properties"))) {
        props.load(in);
    }

    String drivers = props.getProperty("jdbc.drivers");
    if (drivers != null)
        System.setProperty("jdbc.drivers", drivers);

    String url = props.getProperty("jdbc.url");
    String username = props.getProperty("jdbc.username");
    String password = props.getProperty("jdbc.password");

    return DriverManager.getConnection(url, username, password);
}
```

### `java.sql.Connection`

- `prepareStatement(String sql)` 返回一个包含 `sql` 语句的 `PreparedStatement` 对象。

### `java.sql.PreparedStatement`

- `setXXX(int n, XXX)` 设置第 `n` 个参数的值 `XXX`（例如 `String`、`double` 等）。
- `clearParameters()` 清除所有参数。
- `ResultSet executeQuery()` 执行查询并返回 `ResultSet` 对象。
- `int executeUpdate()` 执行更新并返回受影响的行数。

#### 5.5.2 读取和写入 LOB

除了数字、字符串和日期外，许多数据库还可以存储大对象（LOB），在 SQL 中，二进制对象被称为 BLOB，字符对象被称为 CLOB。

要读取 LOB，需要对 `ResultSet` 对象调用 `getBlob` 或 `getClob` 方法。如果你有包含图片的表，可以这样获取图像：

```java
PreparedStatement stat =
    conn.prepareStatement("SELECT Cover FROM Covers WHERE ISBN?");
// ...
stat.set(1, isbn);

try (ResultSet result = stat.executeQuery()) {
    if (result.next()) {
        Blob coverBlob = result.getBlob(1);
        Image coverImage = ImageIO.read(coverBlob.getBinaryStream());
    }
}
```

同样，如果你检索 `Clob` 对象，可以通过调用 `getSubString` 或 `getCharacterStream` 获取字符数据。

要将 LOB 放入数据库，可以在 `Connection` 对象上调用 `createBlob` 或 `createClob`，获取输出流或写入器到 LOB 并写入数据。以下是存储图像的示例：

```java
Blob coverBlob = connection.createBlob();
int offset = 0;
OutputStream out = coverBlob.setBinaryStream(offset);
ImageIO.write(coverImage, "PNG", out);

PreparedStatement stat =
    conn.prepareStatement("INSERT INTO Cover VALUES (?, ?)");
stat.set(1, isbn);
stat.set(2, coverBlob);
stat.executeUpdate();
```

### `java.sql.ResultSet`

- `getBlob(int columnIndex)`
- `getBlob(String columnLabel)`



`getClob(int columnIndex)` 和 `getClob(String columnLabel)` 用于获取指定列的 BLOB 或 CLOB。

### `java.sql.Blob`

- `length()` 获取该 BLOB 的长度。
- `byte[] getBytes(long startPosition, long length)` 获取该 BLOB 指定范围的数据。
- `InputStream getBinaryStream()` 和 `InputStream getBinaryStream(long startPosition, long length)` 返回一个从该 BLOB 或其指定范围读取数据的流。
- `OutputStream setBinaryStream(long startPosition)` 返回一个写入该 BLOB 的输出流，从指定位置开始。

### `java.sql.Clob`

- `length()` 获取该 CLOB 的字符数。
- `String getSubString(long startPosition, long length)` 获取该 CLOB 指定范围的字符。
- `Reader getCharacterStream()` 和 `Reader getCharacterStream(long startPosition, long length)` 返回一个读取器（而非流），用于从此 CLOB 或指定范围读取字符。
- `Writer setCharacterStream(long startPosition)` **1.4** 返回一个写入器（而非流），用于从指定位置开始向此 CLOB 写入。

---

`java.sql.Connection` **1.1**

- `Blob createBlob()` **6**
- `Clob createClob()` **6**

创建一个空的 BLOB 或 CLOB。

### 5.5.3 SQL 转义 (SQL Escapes)

“转义”语法功能通常被数据库支持，但它们使用了特定于数据库的语法变体。JDBC 驱动程序的职责是将转义语法翻译为特定数据库的语法。

针对以下功能提供了转义支持：

- 日期和时间字面量
- 调用标量函数
- 调用存储过程
- 外连接
- `LIKE` 子句中的转义字符

日期和时间字面量在不同数据库之间差异很大。要嵌入日期或时间字面量，请指定 ISO 8601 格式的值（`www.cl.cam.ac.uk/~mgk25/iso-time.html`）。驱动程序将将其转换为原生格式。使用 `d`、`t`、`ts` 分别对应 `DATE`、`TIME` 或 `TIMESTAMP` 值：

```
{d '2008-01-24'}
{t '23:59:59'}
{ts '2008-01-24 23:59:59.999'}
```

*标量函数*（scalar function）是返回单个值的函数。许多函数在数据库中可用，但名称各异。JDBC 规范提供了标准名称并将其翻译为特定数据库的名称。要调用函数，请按如下方式嵌入标准函数名和参数：

```
{fn left(?, 20)}
{fn user()}
```

你可以在 JDBC 规范中找到支持的函数名完整列表。

*存储过程*（stored procedure）是在数据库中执行的程序，使用特定数据库的语言编写。要调用存储过程，请使用 `call` 转义。如果过程没有参数，则无需提供括号。使用 `=` 来捕获返回值：

```
{call PROC1(?, ?)}
{call PROC2}
{call ? = PROC3(?)}
```

两个表的*外连接*（outer join）并不要求每个表的行都根据连接条件匹配。例如，查询：

```
SELECT * FROM {oj Books LEFT OUTER JOIN Publishers ON Books.Publisher_Id = Publisher.Publisher_Id}
```

该查询包含了某些 `Publisher_Id` 在 `Publishers` 表中没有匹配的书籍，并用 `NULL` 值表示不存在匹配项。你需要 `RIGHT OUTER JOIN` 来包含没有匹配书籍的出版者，或者使用 `FULL OUTER JOIN` 来返回两者。之所以需要转义语法，是因为并不是所有数据库都为这些连接使用标准表示法。

最后，`_` 和 `%` 字符在 `LIKE` 子句中有特殊含义——用于匹配单个字符或字符序列。目前没有标准的方法可以字面地使用它们。如果你想匹配所有包含 `_` 的字符串，请使用此结构：

```
... WHERE ? LIKE %!_% {escape '!'}
```

在这里，我们将 `!` 定义为转义字符。组合 `!_` 表示字面量上的下划线。

### 5.5.4 多重结果

查询可能会返回多个结果。这发生在执行存储过程时，或者在允许在单次查询中提交多个 `SELECT` 语句的数据库中。以下是获取所有结果集的方法：

1. 使用 `execute` 方法执行 SQL 语句。
2. 获取第一个结果或更新计数。
3. 重复调用 `getMoreResults` 方法以移动到下一个结果集。
4. 当没有更多结果集或更新计数时结束。

如果链中的下一个项是结果集，则 `execute` 和 `getMoreResults` 方法返回 `true`。如果链中的下一个项不是更新计数，则 `getUpdateCount` 方法返回 `-1`。

以下循环遍历了所有结果：

```java
boolean isResult = stat.execute(command);
boolean done = false;

while (!done)
{
    if (isResult)
    {
        ResultSet result = stat.getResultSet();
        // 对 result 进行操作
    }
    else
    {
        int updateCount = stat.getUpdateCount();
        if (updateCount >= 0)
        {
            // 对 updateCount 进行操作
        }
        else
        {
            done = true;
        }
    }
    isResult = stat.getMoreResults();
}
```

`java.sql.Statement` **1.1**

- `boolean getMoreResults()`
- `boolean getMoreResults(int current)` **6**

获取下一个结果。`current` 参数为 `CLOSE_CURRENT`、`KEEP_CURRENT` 或 `CLOSE_ALL` 之一。如果下一个项存在且是结果集，则返回 `true`。

---

`java.sql.Statement` **1.1**

- `boolean execute(String statement, int autogenerated)` **1.4**
- `int executeUpdate(String statement, int autogenerated)` **1.4**

执行给语句，如前所述。如果 `autogenerated` 设置为 `Statement.RETURN_GENERATED_KEYS` 且语句是 `INSERT`，则第一列包含生成的键。

### 5.5.5 获取生成的键

大多数数据库支持某种生成键的机制。遗憾的是，厂商之间的差异很大。

正如你所看到的，`ResultSet` 接口的 `next` 方法遍历结果集的行。这对于需要分析数据的程序是足够的。然而，考虑显示表格或查询结果的可视化数据（如图 5.4 第 288 页），你通常希望用户能够在*可滚动*的集集中在前后移动，甚至跳转到任何位置。

此外，一旦用户看到了结果集的内容，他们可能会想要编辑它。在*可更新*的结果集中，你可以通过编程更新记录，以便数据库自动更新。我们将在后续章节中讨论这些功能。

### 5.6. 可滚动结果集

默认情况下，结果集是不可滚动且不可更新的。要从查询获取可滚动的结果集，你必须使用方法获取不同的 `Statement` 对象：

```java
Statement stat = conn.createStatement(type, concurrency);
```

对于准备语句，使用调用：

```java
PreparedStatement stat = conn.prepareStatement(command, type, concurrency);
```

`type` 和 `concurrency` 的可能值列在表 5.6 和 5.7 中。你有以下选择：

- 你是否希望结果集是可滚动的？如果不是，使用 `ResultSet.TYPE_FORWARD_ONLY`。
- 如果结果集是可滚动的，你是否希望它反映在产生它的查询之后发生的数据库更改？（在我们的讨论中，假设可滚动结果集使用 `ResultSet.TYPE_SCROLL_INSENSITIVE` 设置。这假设结果集不会“感知”执行查询后的数据库变化。）
- 你想要通过编辑结果集来更新数据库吗？（详情请参见下一节。）

![Image](img/00097.jpeg)

### 表 5.6 `ResultSet` 类型值

![Image](img/00098.jpeg)

### 表 5.7 `ResultSet` 并发值

例如，如果你只是想要滚动查看结果集但不想编辑其数据，请点击此处查看代码图像

```java
Statement stat = conn.createStatement(
      ResultSet.TYPE_SCROLL_INSENSITIVE, ResultSet.CONCUR_READ_ONLY);
```

所有通过方法调用返回的结果集点击此处查看代码图像

```java
ResultSet rs = stat.executeQuery(query);
```

现在它们都是可滚动的。可滚动的结果集有一个指示当前位置的 `cursor`（游标）。

---

![Image](img/00002.jpeg) 注意

并不是所有的数据库驱动都支持可滚动或可更新的结果集（`DatabaseMetaData` 接口的 `supportsResultSetType` 和 `supportsResultSetConcurrency` 方法将告诉你使用特定驱动程序的特定数据库支持哪些类型和并发模式）。即使数据库支持所有结果集模式，特定的查询也可能无法产生包含你请求的所有属性的结果集（例如，复杂查询的结果集可能是不可更新的）。在这种情况下，`executeQuery` 方法会返回一个能力较弱的 `ResultSet`，并向连接对象添加一个 `SQLWarning`。（[第 5.4.3 节”位于第 302 页](#part0010.html_page_302) 显示了如何检索警告。）或者，你可以使用 `ResultSet` 接口的 `getType` 和 `getConcurrency` 方法来查找结果集实际上处于什么模式。如果你没有检查结果集的能力并执行了不支持的操作（例如在不可滚动的结果集上执行 `previous`），该操作将抛出 `SQLException`。

---

滚动非常简单。使用

```java
if (rs.previous()) . . .
```

向后滚动。如果游标位于实际的行上，该方法返回 `true`；如果它现在位于第一行之前，则返回 `false`。

你可以通过调用

```java
rs.relative(n);
```

将游标向前后移动若干行。如果 `n` 为正数，游标向前移动。如果 `n` 为负数，游标向后移动。如果 `n` 为零，则调用不起作用。如果你尝试将游标移动到当前行范围之外，它将被指向最后一行之后或第一行之前，取决于 `n` 的符号。然后，方法返回 `false` 且游标不移动。如果游标位于实际的行上，方法返回 `true`。

或者，你可以将游标设置为特定的行号：

```java
rs.absolute(n);
```

要获取当前行号，调用

```java
int currentRow = rs.getRow();
```

结果集中的第一行编号为 `1`。如果返回值为 `0`，则游标当前不在某行上——它要么位于第一行之前，要么位于最后一行之后。

便利方法 `first`、`last`、`beforeFirst` 和 `afterLast` 将游标移动到第一行、最后一行、第一行之前或最后一行之后。

最后，方法 `isFirst`、`isLast`、`isBeforeFirst` 和 `isAfterLast` 测试游标是否位于这些特殊位置之一。

使用可滚动的结果集非常简单。缓存查询数据的繁重工作由数据库驱动在后台完成。

#### 5.6.2 可更新的结果集

如果你想编辑结果集中的数据并让更改自动反映在数据库中，创建一个创建一个更新的结果集。可更新的结果集不必是滚动的，但如果你向用户展示数据以便编辑，你通常也希望允许滚动。

要获取可更新的结果集，请如下方式创建语句：点击此处查看代码图像

```java
Statement stat = conn.createStatement(
    ResultSet.TYPE_SCROLL_INSENSITIVE, ResultSet.CONCUR_UPDATABLE);
```

调用 `executeQuery` 返回的结果集将是可更新的。

---

![Image](img/00002.jpeg) 注意

并不是所有的查询都返回可更新的结果集。如果你的查询涉及多个表的连接，结果可能是不可更新的。然而，如果你的查询只涉及单表，或者你通过主键连接了多个表，你应该预期结果集是可更新的。调用 `ResultSet` 接口的 `getConcurrency` 方法可以最终确定。

---

例如，假设你想提高某些书的价格，但你没有用于发布 `UPDATE` 语句的简单标准。那么，你可以遍历所有书籍并更新价格。点击此处查看代码图像

```java
String query = "SELECT * FROM Books";
ResultSet rs = stat.executeQuery(query);

while (rs.next()) {
    if (rs.previous()) {
        double price = rs.getDouble("Price");
        rs.updateDouble("Price", price + increase);
        rs.updateRow();
    }
}
```

前面的示例显示了如何修改现有行。如果你想向数据库添加新行，首先使用 `moveToInsertRow` 方法将游标移动到插入位置。然后，通过发布 `update` 指令在插入位置构建新行。当你完成后，调用 `insertRow` 方法将新行交付数据库。插入完成后，调用 `moveToCurrentRow` 将游标移回当前位置。这是一个示例：点击此处查看代码图像

```java
rs.moveToInsertRow();
rs.updateString("Title", title);
rs.updateString("ISBN", isbn);
rs.updateString("Publisher_Id", pubid);
rs.updateDouble("Price", price);
rs.insertRow();
rs.moveToCurrentRow();
```

注意，你无法影响新数据添加到结果集或数据库的位置。

如果你没有插入行中指定列值，它将被设置为 SQL `NULL`。然而，如果该列有 `NOT NULL` 约束，将抛出异常且不会插入该行。

最后，你可以删除游标下的行：

```java
rs.deleteRow();
```

`deleteRow` 方法会立即从结果集和数据库中删除该行。

`ResultSet` 接口的 `updateRow`、`insertRow` 和 `deleteRow` 方法提供了与执行 `UPDATE`、`INSERT` 和 `DELETE` SQL 语句相同的功能。然而，Java 程序员可能会觉得通过结果集操作数据库内容比构建 SQL 语句更自然。

如果你不小心，可能会使用可更新的结果集写出效率极低的代码。执行一个 `UPDATE` 语句比执行查询并遍历结果、在此过程中更改数据要 `much` 得多。可更新的结果集对于用户可以进行任意更改的交互式程序是有意义的，但对于大多数程序化的更改，SQL `UPDATE` 更为合适。

![Image](img/00002.jpeg) 备注

JDBC 2 对结果集提供了进一步的增强，例如如果数据已被另一个并发数据库连接修改，则具有使用最新数据更新结果集的能力。JDBC 3 进一步添加了另一项改进，指定了在提交事务时结果集的行为。然而，这些高级功能超出了本介绍章节的范围。有关更多信息，请参考由 Maydene Fisher、Jon Ellis 和 Jonathan Bruce 编写的 *JDBC™ API Tutorial and Reference, Third Edition*（Addison-Wesley, 2003）以及 JDBC 规范。

## `java.sql.Connection` **1.1**

- `Statement createStatement(int type, int concurrency)` **1.2**
- `PreparedStatement prepareStatement(String command, int type, int concurrency)` **1.2**

创建一个产生给定类型和并发性结果集的语句或预编译语句。

![Image](img/00099.jpeg)



## java.sql.ResultSet **1.1**

- `int getType()` **1.2**

返回此结果集的类型——`TYPE_FORWARD_ONLY`、`TYPE_SCROLL_INSENSITIVE` 或 `TYPE_SCROLL_SENSITIVE` 之一。

- `int getConcurrency()` **1.2**

返回此结果集的并发性设置——`CONCUR_READ_ONLY` 或 `CONCUR_UPDATABLE` 之一。

- `boolean previous()` **1.2**

将光标移动到前一行。如果光标位于某行，则返回 `true`；如果光标位于第一行之前，则返回 `false`。

- `int getRow()` **1.2**

获取当前行号。行从 `1` 开始编号。

- `boolean absolute(int r)` **1.2**

将光标移动到第 `r` 行。如果光标位于某行，则返回 `true`。

- `boolean relative(int d)` **1.2**

将光标移动 `d` 行。如果 `d` 为负数，则光标向后移动。如果光标位于某行，则返回 `true`。

- `boolean first()` **1.2**

- `boolean last()` **1.2**

将光标移动到第一行或最后一行。如果光标位于某行，则返回 `true`。

- `void beforeFirst()` **1.2**

- `void afterLast()` **1.2**

将光标移动到第一行之前或最后一行之后。

- `boolean isFirst()` **1.2**

- `boolean isLast()` **1.2**

测试光标是否在第一行或最后一行。

- `boolean isBeforeFirst()` **1.2**

- `boolean isAfterLast()` **1.2**

测试光标是否在第一行之前或最后一行之后。

- `void moveToInsertRow()` **1.2**

将光标移动到插入行。插入行是一个特殊行，用于通过 `updateXXX` 和 `insertRow` 方法插入新数据。

- `void moveToCurrentRow()` **1.2**

将光标从插入行移回调用 `moveToInsertRow` 方法时所占据的行。

- `void insertRow()` **1.2**

将插入行的内容插入到数据库和结果集中。

- `void deleteRow()` **1.2**

从数据库和结果集中删除当前行。

- `void updateXxx(int column, Xxx data)` **1.2**

- `void updateXxx(String columnName, Xxx data)` **1.2**

（`Xxx` 是如 `int`、`double`、`String`、`Date` 等类型）

更新结果集当前行中的一个字段。

- `void updateRow()` **1.2**

将当前行的更新发送到数据库。

- `void cancelRowUpdates()` **1.2**

取消当前行的更新。

## java.sql.DatabaseMetaData **1.1**

- `boolean supportsResultSetType(int type)` **1.2**

如果数据库支持给定的类型的结果集，则返回 `true`；`type` 是 `ResultSet` 接口的常量 `TYPE_FORWARD_ONLY`、`TYPE_SCROLL_INSENSITIVE` 或 `TYPE_SCROLL_SENSITIVE` 之一。

- `boolean supportsResultSetConcurrency(int type, int concurrency)` **1.2**

如果数据库支持给定的类型和并发性组合的结果集，则返回 `true`。

![Image](img/00100.jpeg)

### 5.7 Row Sets

可滚动的结果集是强大的，但它们有一个主要的缺点：你需要在整个用户交互期间保持数据库连接打开。然而，用户可能会离开电脑很长时间，导致连接被占用。这并不好——数据库连接是稀缺资源。在这种情况下，请使用 `RowSet`。`RowSet` 接口扩展了 `ResultSet`，但不必绑定到数据库连接。

#### 5.7.1 构建 Row Sets

`javax.sql.rowset` 包提供了以下扩展 `RowSet` 的接口：

- `CachedRowSet` 允许离线操作。我们将在下节讨论缓存结果集。

- `WebRowSet` 是一种可以保存到 XML 文件的缓存结果集。`FilteredRowSet` 和 `JoinRowSet` 支持等于 `SELECT` 和 `JOIN` 的操作。

- `JdbcRowSet` 是对 `ResultSet` 的薄封装。它增加了 `RowSet` 接口的有用方法。

从 Java 7 开始，获取结果集的标准方法是：

```java
SetFactory factory = RowSetProvider.newFactory();
CachedRowSet crs = factory.createCachedRowSet();
```

在 Java 7 之前，有特定厂商的方法创建结果集。此外，JDK 在 `com.sun.rowset` 中提供了参考实现。类名以 `Impl` 结尾，例如 `CachedRowSet`。如果你无法使用 `RowSetProvider`，可以使用这些类：

```java
CachedRowSet crs = new com.sun.rowset.CachedRowSetImpl();
```

#### 5.7.2 Cached Row Sets

缓存结果集包含了结果集的所有数据。由于 `CachedRowSet` 是 `ResultSet` 接口的子接口，你可以像使用结果集一样使用缓存结果集。缓存结果集带来了一个重要的优势：你可以关闭连接并继续使用结果集。正如我们在示例列表 5.4 中所示，这极大简化了交互式应用程序的实现。每个用户命令只需打开数据库连接、执行查询、将结果放入缓存结果集并关闭连接。

可以修改缓存结果集中的数据。当然，修改不会立即反映在数据库中；你需要显式请求接受积累的更改。`CachedRowSet` 然后会重新连接到数据库并执行 SQL 语句写入这些更改。

你可以从结果集填充 `CachedRowSet`：

```java
ResultSet result = . . .;
RowSetFactory factory = RowSetProvider.newFactory();
CachedRowSet crs = factory.createCachedRowSet();
crs.populate(result);
conn.close(); // 现在可以关闭数据库连接
```

或者，你可以让 `CachedRowSet` 对象自动建立连接。

```java
crs.setURL("jdbc:derby://localhost:1527/COREJAVA");
crs.setUsername("dbuser");
crs.setPassword("secret");
```

然后设置查询语句和任何参数。

```java
crs.setCommand("SELECT * FROM Books WHERE Publisher_ID = ?");
crs.setString(1, publisherId);
```

最后，用查询结果填充行集：

```java
crs.execute();
```

此调用会建立数据库连接、发布查询、填充行集并断开连接。

如果你的查询结果非常大，你可能不希望将其全部放入行集中。毕竟，你的用户可能只会查看几行。在这种情况下，请指定页面大小：

```java
CachedRowSet crs = . . .;
crs.setCommand(command);
crs.setPageSize(20);
. . .
crs.execute();
```

现在你只会得到 20 行。要获取下一批行，请调用

```java
crs.nextPage();
```

你可以使用与处理结果集相同的方法来检查和修改行集。如果你修改了行集的内容，必须通过调用以下方法将其写回数据库：

```java
crs.acceptChanges(conn);
```

或者

```java
crs.acceptChanges();
```

第二次调用只有在你为行集配置了连接数据库所需的信息（如 URL、用户名和密码）时才起作用。

在第 5.6.2 节中的“可更新的结果集”（第 324 页），你看到并不是所有的结果集都是可更新的。同样，包含复杂查询结果的行集将无法将其更改写回数据库。如果你的行集包含来自单个表的数据，那么通常是安全的。

***

![Image](img/00004.jpeg) 警告

如果你从结果集填充行集，则行集不知道要更新的表名。你需要调用 `setTableName` 来设置表名。

***

如果在你填充行集之后，数据库中的数据发生了变化，就会出现另一个复杂性。这显然是出现问题的迹象，可能导致数据不一致。参考实现会检查原始行集值（即编辑前的值）是否与数据库中的当前值相同。如果是，它们将被替换为编辑后的值；否则，将抛出 `SyncProviderException` 且任何更改都不会被写入。其他实现可能会使用其他的策略进行同步。

***

### javax.sql.RowSet 1.4

- `String getURL()`

- `void setURL(String url)`

获取或设置数据库 URL。

- `String getUsername()`

- `void setUsername(String username)`

获取或设置连接数据库的用户名。

- `String getPassword()`

- `void setPassword(String password)`

获取或设置连接数据库的密码。

- `String getCommand()`

- `void setCommand(String command)`

获取或设置用于填充此行集的执行命令。

- `void execute()`

通过发布用 `setCommand` 设置的语句来填充此行集。为了让驱动管理器获取连接，必须设置 URL、用户名和密码。

***

### javax.sql.rowset.CachedRowSet 5.0

- `void execute(Connection conn)`

通过发布用 `setCommand` 设置的语句来填充此行集。此方法使用了给定的连接*并将其关闭*。

- `void populate(ResultSet result)`

用来自给定结果集的数据填充此缓存行集。

- `String getTableName()`

- `void setTableName(String tableName)`

获取或设置填充此缓存行集的表名。

- `int getPageSize()`

- `void setPageSize(int size)`

获取或设置页面大小。

- `boolean nextPage()`

- `boolean previousPage()`

加载下一页或上一页行。如果有下一页或上一页，则返回 `true`。

- `void acceptChanges()`

- `void acceptChanges(Connection conn)`

重新连接到数据库并写入编辑行集产生的更改。如果因为数据库数据已更改而无法写回数据，可能会抛出 `SyncProviderException`。

***

### javax.sql.rowset.RowSetProvider 7

- `static RowSetFactory newFactory()`

创建一个行集工厂。

***

### javax.sql.rowset.RowSetFactory 7

- `CachedRowSet createCachedRowSet()`

- `FilteredRowSet createFilteredRowSet()`

- `JdbcRowSet createJdbcRowSet()`

- `JoinRowSet createJoinRowSet()`

- `WebRowSet createWebRowSet()`

创建指定类型的行集。

***

### 5.8 元数据

在前面的章节中，你已经看到了如何填充、查询和更新表。然而，JDBC 可以提供有关数据库的额外信息。例如，你可以获取表列表。这种信息对于编写适用于数据库的工具非常有用。

在 SQL 中，描述数据库的数据被称为*元数据*。你可以获取三种元数据：关于数据库的、关于结果集的以及关于准备语句的。

要获取更多关于数据库的信息，从连接请求一个 `DatabaseMetaData` 类型的对象。

```java
DatabaseMetaData meta = conn.getMetaData();
```

现在你准备好获取一些元数据了。例如，调用

```java
ResultSet mrs = meta.getTables(null, null, null, new String[] { "TABLE" });
```

返回包含所有表信息的结果集。参数请见本节末尾的 API 注释。

结果集的每一行包含一个表的信息。第三列是表名。以下循环收集所有的表名：

```java
while (mrs.next())
    tableNames.add(mrs.getString(3));
```

元数据的另一个重要用途。数据库是复杂的，标准留下了大量的变空间。`DatabaseMetaData` 接口中的一百多个方法可以查询数据库，包括具有此类奇特名称的调用：

```java
meta.supportsCatalogsInPrivilegeDefinitions()
```

以及

```java
meta.nullPlusNonNull()
```

显然，这些是面向特殊需求的高级用户的——特别是需要编写高度可移植代码的用户。

第二个元数据接口 `ResultSetMetaData` 报告结果集的信息。每当你从查询获得结果集时，就可以查询列数以及列的名称、类型和字段宽度。这是一个典型的循环：

```java
ResultSet rs = stat.executeQuery("SELECT * FROM " + tableName);
ResultSetMetaData meta = rs.getMetaData();
for (int i = 1; i <= meta.getColumnCount(); i++) {
    String columnName = meta.getColumnLabel(i);
    int columnWidth = meta.getColumnDisplaySize(i);
    ...
}
```

在本节中，我们将向你展示如何编写这样一个简单的工具。列表 5.4 中的程序使用元数据让你能够浏览数据库中的所有表。程序还阐明了缓存行集的使用。

顶部的组合框显示数据库中的所有表。选择其中一个，框架的中心就会填充该表的字段名和第一行的值，如图 5.6 所示。点击“下一个”（Next）和“上一个”（Previous）可以滚动查看表中的各行。你还可以删除一行并编辑行值。点击“保存”（Save）按钮将更改保存到数据库。

![Image](img/00101.jpeg)

**图 5.6** `ViewDB`

***

![Image](img/00002.jpeg) 注意

许多数据库都带有很多更复杂的工具来查看和编辑表。如果你的数据库没有，请查看 iSQL-Viewer (`http://isql.sourceforge.net`) 或 SQuirreL (`http://squirrel-sql.sourceforge.net`)。这些程序可以查看任何 JDBC 数据库中的表。我们的示例程序并不是为了替代这些工具，而是向你展示了如何实现一个用于处理任意表的工具。

***

**列表 5.4** `view/ViewDB.java`

***



```java
package view;

import java.awt.*;
import java.awt.event.*;
import java.io.*;
import java.nio.file.*;
import java.sql.*;
import java.util.*;

import javax.sql.*;
import javax.sql.rowset.*;
import javax.swing.*;

/**
 * 此程序使用元数据显示数据库中的任意表。
 *
 * @version 1.33 2016-04-27
 * @author Cay Horstmann
 */
public class ViewDB
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() ->
            {
                JFrame frame = new ViewDBFrame();
                frame.setTitle("ViewDB");
                frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
                frame.setVisible(true);
            });
    }
}

/**
 * 持有数据面板和导航按钮的帧。
 */
class ViewDBFrame extends JFrame
{
    private JButton previousButton;
    private JButton nextButton;
    private JButton deleteButton;
    private JButton saveButton;
    private DataPanel dataPanel;
    private Component scrollPane;
    private JComboBox<String> tableNames;
    private Properties props;
    private CachedRowSet crs;
    private Connection conn;

    public ViewDBFrame()
    {
        tableNames = new JComboBox<String>();

        try
        {
            readDatabaseProperties();
            conn = getConnection();
            DatabaseMetaData meta = conn.getMetaData();
            try (ResultSet mrs = meta.getTables(null, null, null, new String[] { "TABLE" }))
            {
                while (mrs.next())
                    tableNames.addItem(mrs.getString(3));
            }
        }
        catch (SQLException ex)
        {
            for (Throwable t : ex)
                t.printStackTrace();
        }
        catch (IOException ex)
        {
            ex.printStackTrace();
        }

        tableNames.addActionListener(
            event -> showTable((String) tableNames.getSelectedItem(), conn));
        add(tableNames, BorderLayout.NORTH);
        addWindowListener(new WindowAdapter()
        {
            public void windowClosing(WindowEvent event)
            {
                try
                {
                    if (conn != null) conn.close();
                }
                catch (SQLException ex)
                {
                    for (Throwable t : ex)
                        t.printStackTrace();
                }
            }
        });

        JPanel buttonPanel = new JPanel();
        add(buttonPanel, BorderLayout.SOUTH);

        previousButton = new JButton("Previous");
        previousButton.addActionListener(event -> showPreviousRow());
        buttonPanel.add(previousButton);

        nextButton = new JButton("Next");
        nextButton.addActionListener(event -> showNextRow());
        buttonPanel.add(nextButton);

        deleteButton = new JButton("Delete");
        deleteButton.addActionListener(event -> deleteRow());
        buttonPanel.add(deleteButton);

        saveButton = new JButton("Save");
        saveButton.addActionListener(event -> saveChanges());
        buttonPanel.add(saveButton);

        if (tableNames.getItemCount() > 0)
            showTable(tableNames.getItemAt(0), conn);
    }

    /**
     * 为显示新表准备文本字段，并显示第一行。
     *
     * @param tableName 要显示的表名
     * @param conn 数据库连接
     */
    public void showTable(String tableName, Connection conn)
    {
        try (Statement stat = conn.createStatement();
             ResultSet result = stat.executeQuery("SELECT * FROM " + tableName))
        {
            // 获取结果
            // 拷贝到行结果集中
            RowFactory factory = RowSetProvider.newFactory();
            crs = factory.createCachedRowSet();
            crs.setTableName(tableName);
            crs.populate(result);

            if (scrollPane != null) remove(scrollPane);
            dataPanel = new DataPanel(crs);
            scrollPane = new JScrollPane(dataPanel);
            add(scrollPane, BorderLayout.CENTER);
            pack();
            showNextRow();
        }
        catch (SQLException ex)
        {
            for (Throwable t : ex)
                t.printStackTrace();
        }
    }

    /**
     * 移动到上一个表行。
     */
    public void showPreviousRow()
    {
        try
        {
            if (crs == null || crs.isFirst()) return;
            crs.previous();
            dataPanel.showRow(crs);
        }
        catch (SQLException ex)
        {
            for (Throwable t : ex)
                t.printStackTrace();
        }
    }

    /**
     * 移动到下一个表行。
     */
    public void showNextRow()
    {
        try
        {
            if (crs == null || crs.isLast()) return;
            crs.next();
            dataPanel.showRow(crs);
        }
        catch (SQLException ex)
        {
            for (Throwable t : ex)
                t.printStackTrace();
        }
    }

    /**
     * 删除当前行。
     */
    public void deleteRow()
    {
        if (crs == null) return;

        new SwingWorker<Void, Void>()
        {
            public void doInBackground() throws SQLException
            {
                crs.deleteRow();
                crs.accept(conn);
                if (crs.isLast())
                    crs = null;
            }

            public void done()
            {
                dataPanel.showRow(crs);
            }
        }.execute();
    }

    /**
     * 保存所有更改。
     */
    public void saveChanges()
    {
        if (crs == null) return;

        new SwingWorker<Void, Void>()
        {
            public void doInBackground() throws SQLException
            {
                crs.acceptChanges(conn);
                return null;
            }
        }.execute();
    }

    private void readDatabaseProperties() throws IOException
    {
        props = new Properties();
    }
}
```

```java
try (InputStream in = Files.newInputStream(Paths.get("database.properties")))
{
    props.load(in);
}

String drivers = props.getProperty("jdbc.drivers");
if (drivers != null) System.setProperty("jdbc.drivers", drivers);
```

/**
 * 从 `database.properties` 文件指定的属性中获取数据库连接。
 *
 * @return 数据库连接
 */
private Connection getConnection() throws SQLException
{
    String url = props.getProperty("jdbc.url");
    String username = props.getProperty("jdbc.username");
    String password = props.getProperty("jdbc.password");

    return DriverManager.getConnection(url, username, password);
}

/**
 * 此面板显示结果集的内容。
 */
class DataPanel extends JPanel
{
    private java.util.List<JTextField> fields;

    /**
     * 构造数据面板。
     *
     * @param rs 此面板要显示的结果集
     */
    public DataPanel(RowSet rs) throws SQLException
    {
        fields = new ArrayList<>();
        setLayout(new GridBagLayout());

        GridBagConstraints gbc = new GridBagConstraints();
        gbc.gridwidth = 1;
        gbc.gridheight = 1;

        ResultSetMetaData rsmd = rs.getMetaData();
        for (int i = 1; i <= rsmd.getColumnCount(); i++)
        {
            gbc.gridy = i - 1;
            String columnName = rsmd.getColumnLabel(i);

            gbc.gridx = 0;
            gbc.anchor = GridBagConstraints.EAST;
            add(new JLabel(columnName), gbc);

            int columnWidth = rsmd.getColumnDisplaySize(i);
            JTextField tb = new JTextField(columnWidth);

            if (!rsmd.getColumnClassName(i).equals("java.lang.String"))
                tb.setEditable(false);

            fields.add(tb);
            gbc.x = 1;
            gbc.anchor = GridBagConstraints.WEST;
            add(tb, gbc);
        }
    }

    /**
     * 通过向所有文本字段填充列值来显示数据库行。
     */
    public void showRow(ResultSet rs)
    {
        try
        {
            if (rs == null) return;

            for (int i = 1; i <= fields.size(); i++)
            {
                String field = rs == null ? "" : rs.getString(i);
                JTextField tb = fields.get(i - 1);
                tb.setText(field);
            }
        }
        catch (SQLException ex)
        {
            for (Throwable t : ex)
                t.printStackTrace();
        }
    }

    /**
     * 将更改的数据更新到行集的当前行。
     */



```java
public void setRow(RowSet rs) throws SQLException
{
    for (int i = 1; i <= fields.size(); i++)
    {
        String field = rs.getString(i);
        JTextField tb = fields.get(i - 1);

        if (!field.equals(tb.getText()))
            rs.updateString(i, tb.getText());
    }

    rs.updateRow();
}
```

### `java.sql.Connection`

- `DatabaseMetaData getMetaData()`

  返回以 `DatabaseMetaData` 对象表示的连接元数据。

### `java.sql.DatabaseMetaData`

- `ResultSet getTables(String catalog, String schemaPattern, String tableNamePattern, String types[])`

  返回目录中符合模式模式、表名模式以及类型标准的所有表的描述。（`schema`（模式）描述了一组相关的表和访问权限。`catalog`（目录）描述了一组相关的模式。这些概念对于构建大型数据库结构至关重要。）

  `catalog` 和 `schemaPattern` 参数可以为 `""` 以检索不带目录或模式的表，或者为 `null` 以返回不分目录或模式的表。

  `types` 数组包含要包含的表类型名称。常见的类型有 `TABLE`、`VIEW`、`SYSTEM TABLE`、`GLOBAL TEMPORARY`、`LOCAL TEMPORARY`、`ALIAS` 和 `SYNONYM`。如果 `types` 为 `null`，则返回所有类型的表。

  结果集有五列，所有类型均为 `String`。

![Image](img/00102.jpeg)

- `int getJDBCMajorVersion()`
- `int getJDBCMinorVersion()`

  返回建立数据库连接的驱动程序的 JDBC 主版本或次版本号。例如，JDBC 3.0 驱动的主版本号为 3，次版本号为 0。

- `int getMaxConnections()`

  返回允许此数据库的最大并发连接数。

- `int getMaxStatements()`

  返回每个连接允许的最大并发打开的语句数量，如果未知则返回 `0`。

- `int getCount()`

  返回 `ResultSet` 中的列数。

- `int getColumnDisplaySize(int column)`

  返回列的建议宽度。

- `String getColumnLabel(int column)`

  返回列的建议标题。

- `String getColumnName(int column)`

  返回与该列关联的列名。

点击此处查看代码图像：

```java
Statement stat = conn.createStatement(); // 开始事务; rollback() 在此处调用

stat.executeUpdate(command1);

Savepoint svpt = conn.setSavepoint(); // 设置保存点; rollback(svpt) 在此处调用

stat.executeUpdate(command2);

if (. . ...) conn.rollback(svpt); // 撤销 command2 的效果

. . .

conn.commit();
```

当你不再需要某个保存点时，应该释放它：

```java
conn.releaseSavepoint(svpt);
```

### 5.9.3 批量更新

假设一个程序需要执行许多 `INSERT` 语句来填充数据库表。你可以通过使用“批量更新”（batch update）来提高程序的性能。在批量更新中，一组语句会被收集起来并作为一个批次提交。

---

![图像](img/00002.jpeg) 备注

使用 `DatabaseMetaData` 接口的 `supportsBatchUpdates()` 方法来确定你的数据库是否支持此功能。

---

批次中的语句可以是如 `INSERT`、`UPDATE` 或 `DELETE` 等操作，也可以是数据定义语句如 `CREATE TABLE` 或 `DROP TABLE`。如果你向批次中添加 `SELECT` 语句，将抛出异常。（从概念上讲，`SELECT` 语句在批次中没有意义，因为它返回的是结果集而不更新数据库。）

要执行批处理，首先按照通常方式创建一个 `Statement` 对象：

点击此处查看代码图像：

```java
Statement stat = conn.createStatement();
```

现在，不要调用 `executeUpdate`，而是调用 `addBatch` 方法：

点击此处查看代码图像：

```java
String command = "CREATE TABLE . . ..."

stat.addBatch(command);

while (. . .)
{
    command = "INSERT INTO . . . VALUES (" + . . . + ")";
    stat.addBatch(command);
}
```

最后，提交整个批次：

点击此处查看代码图像：

```java
int[] counts = stat.executeBatch();
```

调用 `executeBatch` 返回一个包含所有提交语句的行数的数组。

为了在批量模式下进行适当错误处理，请将批量执行视为单条事务。如果批次在中间失败，你希望回到批次开始之前的状态。

首先，关闭自动提交（autocommit）模式，然后收集批次、执行它、提交它，最后恢复原始的自动提交模式：

点击此处查看代码图像：

```java
boolean autoCommit = conn.getAutoCommit();

conn.setAutoCommit(false);

Statement stat = conn.getStatement();

. . .

// 继续调用 stat.addBatch(. . .);

. . .

stat.executeBatch();

conn.commit();

conn.setAutoCommit(autoCommit);
```

---

#### `java.sql.Connection` 1.1

- `boolean getAutoCommit()`
- `void setAutoCommit(boolean b)`

  获取或设置此连接的自动提交模式为 `b`。如果自动提交为 `true`，所有语句在执行完成后将立即提交。

- `void commit()`

  提交自上次提交以来发布的所有语句。

- `void rollback()`

  撤销自上次提交以来发布的所有所有语句的效果。

- `Savepoint setSavepoint()` 1.4
- `Savepoint setSavepoint(String name)` 1.4

  设置一个未命名的或命名的保存点。

- `void rollback(Savepoint svpt)` 1.4

  回滚到指定的保存点。

- `void releaseSavepoint(Savepoint svpt)` 1.4

  释放指定的保存点。

---

#### `java.sql.Savepoint` 1.4

- `int getSavepointId()`

  获取此未命名保存点的 ID，如果这是命名保存点，则抛出 `SQLException`。

- `String getSavepointName()`

  获取此保存点的名字，如果这是未命名保存点，则抛出 `SQLException`。

---

#### `java.sql.Statement` 1.1

- `void addBatch(String command)` 1.2

  将命令添加到此语句的当前命令批次。

- `int[] executeBatch()` 1.2
- `long[] executeLargeBatch()` 8

  执行当前批次中的所有命令。返回数组中的每个值对应于批次语句之一。如果是非负值，则为行数。如果是值 `SUCCESS_NO_INFO`，则语句执行成功但没有可用的行数。如果是 `EXECUTE_FAILED`，则语句失败。

---

#### `java.sql.DatabaseMetaData` 1.1

- `boolean supportsBatchUpdates()` 1.2

  如果驱动程序支持批量更新，则返回 `true`。

---

### 5.10 高级 SQL 类型

表 5.8

![图像](img/0010.jpeg)

**表 5.8** SQL 类型及其对应的 Java 类型

`ARRAY` 是一个序列。`getArray` 方法从数据库返回 `java.sql.Array` 类型的对象。`ROWID` 描述行的位置以便可以快速检索。JDBC 4 引入了 `java.sql.RowId`。国家字符字符串（NCHAR 及其变体）使用本地编码存储字符串。JDBC 4 提供了在 `String` 对象和国家字符字符串之间转换的方法。某些数据库存储用户定义的结构类型。JDBC 3 提供了将结构类型自动映射到 Java 对象的机制。某些数据库为 XML 数据提供原生存储。JDBC 4 引入了 `SQLXML` 接口，可以在内部 XML 表示和 DOM/Result 接口之间进行调解。我们不再进一步讨论这些高级 SQL 类型。你可以在 JDBC 教程中找到这些主题的更多信息。

之前章节描述的带有 `database.properties` 文件的简单数据库连接设置适用于小型程序，但不适用于大型应用程序。

当 JDBC 应用部署在 Web 或企业环境中时，数据库连接的管理与 JNDI 集成。跨企业的数据源属性存储在目录中。使用目录允许集中管理用户名、密码、数据库名称和 JDBC URL。

在这种环境中，可以使用以下代码建立数据库连接：

点击此处查看代码图像：

```java
Context jndiContext = new InitialContext();

DataSource source = (DataSource) jndiContext.lookup("java:comp/env/jdbc/corejava");

Connection conn = source.getConnection();
```

注意 `DriverManager` 不再参与。相反，JNDI 服务定位数据源。数据源是一个接口，允许简单的 JDBC 连接以及更高级，例如涉及多个数据库的分布式事务。`DataSource` 接口定义在 `javax.sql` 标准扩展包中。

---

![图像](img/0002.jpeg) 备注

在 Java EE 容器中，甚至不需要编写 JNDI 查找。只需在 `DataSource` 字段上使用 `@Resource` 注解，数据源引用就会在应用程序加载时被设置：

```java
@Resource(name="jdbc/corejava")
private DataSource source;
```

---

当然，需要在某处配置数据源。如果你编写了运行在 `Apache Tomcat` 等 Servlet 容器或 `GlassFish` 等应用服务器中执行的数据库程序，请将数据库配置（包括 JNDI 名称、`JDBC URL`、用户名和密码）放在配置文件中，或在管理 GUI 中设置。

用户名和登录名的管理只是需要特别关注的问题之一。另一个问题涉及建立数据库连接的成本。我们的示例数据库程序使用了两种策略来获取数据库连接。代码列表 5.3 中的 `QueryDB` 程序在程序开始时建立了一个单一数据库连接，并在程序结束时关闭。代码列表 5.4 中的 `ViewDB` 程序在每次需要时都会打开新连接。

然而，这两种方法都不尽如人意。数据库连接是有限的资源。如果用户离开应用程序一段时间，连接不应该保持打开状态。相反，为每个查询都获取连接并在之后关闭它，成本是非常高的。

解决方案是*池化*（pool）连接。这意味着数据库连接不会被物理关闭，而是保留在队列中并重复使用。连接池是一项重要服务，`JDBC` 规范为实现者提供了提供的钩子。然而，`JDK` 本身没有提供任何实现，数据库供应商通常也不会在其 `JDBC` 驱动中包含。相反，Web 容器和应用服务器的供应商提供了连接池实现。

使用连接池对程序员来说是完全透明的。通过获取数据源并调用 `getConnection` 从连接池源获取连接。当你完成连接的使用后，调用 `close`。这不会关闭物理连接，而是告诉池你已不再使用它。连接池通常还会尝试对预处理语句进行池化。

你现在已经学习了 `JDBC` 基础知识，并拥有足够实现简单数据库应用程序的知识。然而，正如我们在章节开头提到的，数据库是复杂的，相当多的高级主题超出了本介绍章节的范围。欲了解高级 `JDBC` 能力的概览，请参考*JDBC API Tutorial and Reference* 或 `JDBC` 规范。

在本章中，你学习了如何在 Java 中与关系型数据库交互。下一章将介绍 Java 8 日期时间库。

## 第 6 章：日期和时间 API

---

### 本章内容

- 6.1 时间线
- 6.2 本地日期
- 6.3 调整器
- 6.4 本地时间
- 6.5 时区时间
- 6.6 格式化与解析
- 6.7 与旧代码互操作

---

时光飞逝，我们可以轻松地设置一个起点并按秒向前或向后计数。那么为什么处理时间如此困难呢？问题在于人。如果我们能直接互相说：“在 1523793600 见我，不要迟到！”，一切都会变得简单。但我们希望时间与日光和季节相关。这正是事情变得复杂的地方。Java 1.0 有一个 `Date` 类，从事后看来看，它是天真的，而且在 Java 1.1 引入 `Calendar` 类时，它的大部分方法都被弃用了。它的 API 并不完美，其实例是可变的，而且它没有处理闰秒等问题。第三次是幸运，在 Java SE 8 中引入的 `java.time` API 弥补了过去的缺陷，并且应该为我们服务很长一段时间。在本章中，你将学习为什么时间计算如此令人烦恼，以及日期和时间 API 如何解决这些问题。

### 6.1 时间线

从历史上看，基本时间单位——秒，源于地球绕自轴的旋转。一个整转有 24 小时或 24 × 60 × 60 = 86400 秒，因此精确定义一秒似乎只是天文学测量的问题。遗憾的是，地球会轻微晃动，需要更精确的定义。1967 年，根据 133 铯原子的固有属性推导出了与历史定义匹配的新型精确秒定义。从那时起，原子钟网络维持着官方时间。

官方计时员经常将绝对时间与地球的自转进行同步。起初，官方秒会经过微调，但从 1972 年开始，偶尔会插入“闰秒”（在理论上，偶尔可能移除一秒，但这种情况尚未发生过）。目前有关于再次更改系统的说法。显然，闰秒很痛苦，许多计算机系统改为使用“平滑”处理，即在闰秒之前人为地减慢或加速时间，保持每天 86,400 秒。这之所以有效，是因为计算机上的本地时间并不精确，而且计算机被用于与外部时间服务进行同步。

Java 日期和时间 API 规范要求 Java 使用的时间尺度：

- 每天 86,400 秒。
- 在午夜精确匹配。
- 在其他地方密切匹配。

在 Java 中，`Instant` 代表时间线上的一个点。一个称为*纪*（epoch）的起点被任意设置在 1970 年 1 月 1 日午夜，即穿过格尼治皇家天文台的经午线。这是 UNIX/POSIX 使用的约定。从该起点开始，时间以纳秒测量。`Instant` 值可以追溯到十亿年前（`Instant.MIN`）。这无法表示宇宙年龄（约 135 亿年），但对于所有实际目的已经足够。毕竟，十亿年前地球被冰雪覆盖，居住着植物动物的祖先。

静态方法 `Instant.now()` 提供当前实例。你可以按照通常使用 `equals` 和 `compareTo` 方法比较两个实例，因此你可以将实例作为时间戳。

要找到两个实例之间的差异，使用静态方法 `Duration.between`。例如，这是测量算法运行时间的方法：

```java
Instant start = Instant.now();

runAlgorithm();

Instant end = Instant.now();

Duration timeElapsed = Duration.between(start, end);

long millis = timeElapsed.toMillis();
```

`Duration` 是两个实例之间的时间。你可以通过调用 `toNanos`、`toMillis`、`getSeconds`、`toMinutes`、`toHours` 或 `toDays` 获取常规单位下的 `Duration` 长度。

它们的内部存储需要一个 `long` 值。秒数存储在 `long` 中，纳秒数存储在额外的 `int` 中。如果你想进行纳秒级精度的计算，并且实际上需要整个 `Duration` 的范围，可以使用表 6.1 中的一种方法。否则，你只需调用 `toNanos` 并使用 `long` 值进行计算。

**表 6.1** 时间实例和持续时间的算术运算

---

**注意**：`long` 需要近 300 年的纳秒才会溢出。

---

例如，如果你想检查一个算法是否比另一个快至少十倍，你可以计算：

点击此处查看代码图像：

```java
Duration timeElapsed2 = Duration.between(start2, end2);

boolean overTenTimesFaster =
```



```java
timeElapsed.multipliedBy(10).minus(timeElapsed2).isNegative();
```

或者：

```java
timeElapsed.toNanos() * 10 < timeElapsed2.toNanos()
```

![Image](img/00002.jpeg)

> 注意
>
> `Instant` 和 `Duration` 类是不可变的，所有方法（如 `multipliedBy` 或 `minus`）都会返回一个新实例。

在 Listing 6.1 中的示例程序中，你可以了解如何使用 `Instant` 和 `Duration` 类对两个算法进行计时。

**Listing 6.1** `timeline/TimeLine.java`

点击此处查看代码图像

```java
package timeline;

import java.time.*;
import java.util.*;
import java.util.stream.*;

public class Timeline {
    public static void main(String[] args) {
        Instant start = Instant.now();

        runAlgorithm();

        Instant end = Instant.now();
        Duration timeElapsed = Duration.between(start, end);
        long millis = timeElapsed.toMillis();

        System.out.printf("%d milliseconds\n", millis);

        Instant start2 = Instant.now();

        runAlgorithm2();

        Instant end2 = Instant.now();
        Duration timeElapsed2 = Duration.between(start2, end2);

        System.out.printf("%d milliseconds\n", timeElapsed2.toMillis());

        boolean overTenTimesFaster = timeElapsed.multipliedBy(10)
                .minus(timeElapsed2).isNegative();

        System.out.printf(
                "The first algorithm is %smore than ten times faster",
                overTenTimesFaster ? "" : "not ");
    }

    public static void runAlgorithm() {
        int size = 10;

        List<Integer> list = new Random().ints()
                .map(i -> i % 100)
                .limit(size)
                .boxed()
                .collect(Collectors.toList());

        Collections.sort(list);
        System.out.println(list);
    }

    public static void runAlgorithm2() {
        int size = 10;

        List<Integer> list = new Random().ints()
                .map(i -> i % 100)
                .limit(size)
                .boxed()
                .collect(Collectors.toList());

        IntStream.range(1, list.size()).allMatch(
                i -> list.get(i - 1).compareTo(list.get(i)) <= 0);

        Collections.shuffle(list);
        System.out.println(list);
    }
}
```

## 6.2 本地日期

现在让我们从绝对时间转向人类时间。Java API 中有两种类人类时间：`本地日期/时间`（local date/time）和 `时区时间`（zoned time）。`本地日期/时间` 包含日期和一天中的时间，但没有关联的时区信息。

本地日期的一个示例是 `1903 年 6 月 14 日`（lambda 表达式发明者阿隆佐·丘奇的生日）。由于该日期既没有时间也没有时区信息，因此并不对应于精确的时间点。

相比之下，`1969 年 7 月 16 日 09:32:00 EDT`（阿波罗 11 号的发射）是一个时区日期/时间，代表时间轴上的一个精确瞬间。

许多计算不需要时区，在某些情况下，时区甚至会成为障碍。假设你安排了每周 10:00 召开一次会议。如果你在上一个时区时间的基础上增加 7 天（即 7 × 24 × 60 秒），并恰好跨越夏令时边界，会议将提前一小时或推迟一小时！

出于此原因，API 设计者建议你除非真的想表示绝对时间，否则不要使用时区时间。生日、节日、日程时间等最适合用本地日期或本地时间表示。

`LocalDate` 是一个包含年、月、日的日期。要构造一个，你可以使用 `now` 或 `of` 静态方法：

点击此处查看代码图像

```java
LocalDate today = LocalDate.now(); // 今天的日期

LocalDate alonzosBirthday = LocalDate.of(1903, 6, 14);

alonzosBirthday = LocalDate.of(1903, Month.JUNE, 14); // 使用 Month 枚举
```

与 UNIX 和 `java.util.Date` 中不规则的约定（其中月份从 0 开始，年份从 1900 年计算）不同，你提供普通的月份数字。或者，你也可以使用 `Month` 枚举。

表 6.2 显示了处理 `LocalDate` 对象最有用的方法。

![Image](img/00108.jpeg)

**表 6.2** `LocalDate` 方法

例如，*程序员节*是每年的第 256 天。

```java
System.out.println("alonzosBirthday: " + alonzosBirthday);

LocalDate programmersDay = LocalDate.of(2018, 1, 1).plusDays(255);

// 9 月 13 日，但如果是闰年，则是 9 月 12 日

System.out.println("programmersDay: " + programmersDay);

LocalDate independenceDay = LocalDate.of(2018, Month.JULY, 4);

LocalDate christmas = LocalDate.of(2018, Month.DECEMBER, 25);

System.out.println("Until christmas: " + independenceDay.until(christmas));

System.out.println("Until christmas: "
        + independenceDay.until(christmas, ChronoUnit.DAYS));

System.out.println(LocalDate.of(2016, 1, 31).plusMonths(1));

System.out.println(LocalDate.of(2016, 3, 31).minusMonths(1));

DayOfWeek startOfLastMillennium =
        LocalDate.of(1900, 1, 1).getDayOfWeek();

System.out.println("startOfLastMillennium: " + startOfLastMillennium);

System.out.println(startOfLastMillennium.getValue());

System.out.println(DayOfWeek.SATURDAY.plus(3));
```

## 6.3 日期调整器（Date Adjusters）

对于调度应用程序，你通常需要计算如“每个月的第一个星期二”之类的日期。`TemporalAdjusters` 类提供了许多用于常用调整的静态方法。你将调整方法的结果传递给 `with` 方法。例如，可以这样计算一个月的第一个星期二：

点击此处查看代码图片

```java
LocalDate firstTuesday = LocalDate.of(year, month, 1).with(
        TemporalAdjusters.nextOrSame(DayOfWeek.TUESDAY));
```

一如既往，`with` 方法返回一个新的 `LocalDate` 对象，而不修改原始对象。表 6.3 显示了可用的调整器。

![Image](img/00109.jpeg)

**表 6.3** `TemporalAdjusters` 类中的日期调整器

你也可以通过实现 `TemporalAdjuster` 接口来创建自己的调整器。这里是一个计算下一个工作日的调整器。

点击此处查看代码图片

```java
TemporalAdjuster NEXT_WORKDAY = w -> {
    LocalDate result = (LocalDate) w;

    do {
        result = result.plusDays(1);
    } while (result.getDayOfWeek().getValue() >= 6);

    return result;
};

LocalDate backToWork = today.with(NEXT_WORKDAY);
```

注意 lambda 表达式的参数类型为 `Temporal`，必须强制转换为 `LocalDate`。你可以使用 `ofDateAdjuster` 方法来避免这种转换，该方法接受类型为 `UnaryOperator<LocalDate>` 的 lambda 表达式。

点击此处查看代码图片

```java
TemporalAdjuster NEXT_WORKDAY = TemporalAdjusters.ofDateAdjuster(w -> {
    LocalDate result = w; // 无需转换

    do {
        result = result.plusDays(1);
    } while (result.getDayOfWeek().getValue() >= 6);

    return result;
});
```

## 6.4 本地时间（Local Time）

`LocalTime` 代表一天中的某个时间，例如 15:30:00。你可以通过 `now` 或 `of` 方法创建实例：

点击此处查看代码图片

```java
LocalTime rightNow = LocalTime.now();

LocalTime bedtime = LocalTime.of(22, 30); // 或者 LocalTime.of(22, 30, 0)
```

表 6.4 显示了本地时间的常用操作。`plus` 和 `minus` 操作会在 24 小时内循环。例如：

点击此处查看代码图片

```java
LocalTime wakeup = bedtime.plusHours(8); // wakeup 是 6:30
```

![Image](img/00002.jpeg)

> 注意
>
> `LocalTime` 不考虑上午/下午。这种无谓的处理留给了格式化器——参见第 365 页的第 6.6 节，“格式化与解析](#part0011.html_ch06levsec6)”。

![Image](img/00110.jpeg)

**表 6.4** `LocalTime` 方法

有一个 `LocalDateTime` 类表示日期和时间。该类适用于存储固定时区中的时间点——例如用于活动时间表。然而，如果你需要进行跨夏令时间的计算，或者需要处理不同地区的用户，则可以使用 `ZonedDateTime`。

## 6.5 时区时间（Zoned Time）

`ZonedDateTime` 表示一个日期、时间以及对应的时区。它比 `LocalDateTime` 更强大，因为它包含了时区信息以及夏令时规则。

许多 `ZonedDateTime` 的方法与 `LocalDateTime` 相同（见表 6.5）。大多数方法都很直观，但夏令时引入了一些复杂性。

你可以通过 `ZoneId` 将 `LocalDateTime` 转换为 `ZonedDateTime`。例如：

```java
ZonedDateTime zdt = LocalDateTime
        .of(2023, 10, 27, 10, 30)
        .atZone(ZoneId.of("America/New_York"));
```

你也可以通过 `Instant` 创建 `ZonedDateTime`。例如：

```java
Instant now = Instant.now();

ZonedDateTime zdt = now.atZone(ZoneId.of("Europe/Paris"));
```

`toZoneInstant` 方法可以将 `ZonedDateTime` 转换为 UTC 时间。

```java
ZonedDateTime utcTime =
        zdt.withZoneSameInstant(ZoneId.of("UTC"));
```

你也可以将 `ZonedDateTime` 转换为 `Instant`。

```java
Instant instant = zdt.toInstant();
```

`ZonedDateTime` 还提供了许多方法来获取时区和偏移量。例如：

```java
ZoneId zone = zdt.getZone();

ZoneOffset offset = zdt.getOffset();

boolean isDaylight = zdt.isDaylightSavings();
```

```java
ZonedDateTime ambiguous = ZonedDateTime.of(
        LocalDate.of(2013, 10, 27), // 夏令时结束日
        LocalTime.of(2, 30),
        ZoneId.of("Europe/Berlin"));

// 2013-10-27T02:30+02:00[Europe/Berlin]

ZonedDateTime anHourLater = ambiguous.plusHours(1);

// 2013-10-27T02:30+01:00[Europe/Berlin]
```

一小时后，小时和分钟保持不变，但区域偏移量发生了变化。

在跨越夏令时边界调整日期时，也需要注意。例如，如果你为下周安排了一个会议，不要添加七天的持续时间：

点击此处查看代码图片

```java
ZonedDateTime nextMeeting = meeting.plus(Duration.ofDays(7));

// 注意！在夏令时期间将不起作用
```

相反，请使用 `Period` 类。

点击此处查看代码图片

```java
ZonedDateTime nextMeeting = meeting.plus(Period.ofDays(7)); // OK
```

![Image](img/00004.jpeg)

> 注意
>
> 还有一个 `OffsetDateTime` 类，它表示带有与 UTC 偏移量的时间，但不包含时区规则。该类旨在用于特定明确不需要这些规则的特殊应用程序，例如某些网络协议。对于人类使用的时间，请使用 `ZonedDateTime`。

Listing 6.3 中的示例程序演示了 `ZonedDateTime` 类。

**Listing 6.3** `zonedtimes/ZonedTimes.java`

点击此处查看代码图片

```java
package zonedtimes;

import java.time.*;

public class ZonedTimes {
    public static void main(String[] args) {
        ZonedDateTime apollo11launch = ZonedDateTime.of(
                1969, 7, 16, 9, 32, 0, 0,
                ZoneId.of("America/New_York"));

        // 1969-07-16T09:32-04:00[America/New_York]

        System.out.println("apollo11launch: " + apollo11launch);

        Instant instant = apollo11launch.toInstant();

        System.out.println("instant: " + instant);
    }
}
```



```java
ZonedDateTime zonedDateTime = instant.atZone(ZoneId.of("UTC"));

System.out.println("zonedDateTime: " + zonedDateTime);

ZonedDateTime skipped = ZonedDateTime.of(
    LocalDate.of(2013, 3, 31),
    LocalTime.of(2, 30),
    ZoneId.of("Europe/Berlin")
);

// 构建 3 月 31 日 3:30
System.out.println("skipped: " + skipped);

ZonedDateTime ambiguous = ZonedDateTime.of(
    LocalDate.of(2013, 10, 27),
    // 夏令时结束
    LocalTime.of(2, 30),
    ZoneId.of("Europe/Berlin")
);

// 2013-10-27T02:30+02:00[Europe/Berlin]
ZonedDateTime anHourLater = ambiguous.plusHours(1);

// 2013-10-27T02:30+01:00[Europe/Berlin]
System.out.println("ambiguous: " + ambiguous);
System.out.println("anHourLater: " + anHourLater);

ZonedDateTime meeting = ZonedDateTime.of(
    LocalDate.of(2013, 10, 31),
    LocalTime.of(14, 30),
    ZoneId.of("America/Los_Angeles")
);

System.out.println("meeting: " + meeting);

ZonedDateTime nextMeeting = meeting.plus(Duration.ofDays(7));

// 注意！在夏令时期间不起作用
System.out.println("nextMeeting: " + nextMeeting);

nextMeeting = meeting.plus(Period.ofDays(7)); // OK
System.out.println("nextMeeting: " + nextMeeting);
```

### 6.6 格式化与解析

`DateTimeFormatter` 类提供了三种类型的格式化，用于打印日期和时间：

- 预定义的标准格式化（参见表 6.6）
- 区域语言特定的格式化
- 带有自定义模式的格式化

![Image](img/00112.jpeg)

**表 6.6** 预定义格式化

要使用其中一种标准格式化，只需调用其 `format` 方法即可：

```java
String formatted =
    DateTimeFormatter.ISO_OFFSET_DATE_TIME.format(apollo11launch);
// 1969-07-16T09:32-04:00
```

标准格式化主要用于机器可读的时间戳。为了向人类读者展示日期和时间，请使用区域语言特定的格式化。日期和时间都有四种样式：`SHORT`、`MEDIUM`、`LONG` 和 `FULL`，参见表 6.7。

静态方法 `ofLocalizedDate`、`ofLocalizedTime` 和 `ofLocalizedDateTime` 创建此类格式化器。例如：

```java
DateTimeFormatter formatter =
    DateTimeFormatter.ofLocalizedDateTime(FormatStyle.LONG);

String formatted = formatter.format(apollo11launch);
// July 16, 1969 9:32:00 AM EDT
```

![Image](img/00113.jpeg)

**表 6.7** 区域语言特定格式化

这些方法使用默认区域。要切换到不同的区域，只需使用 `withLocale` 方法。

```java
formatted = formatter.withLocale(Locale.FRENCH).format(apollo11launch);
// 16 juillet 1969 09:32
```

`DayOfWeek` 和 `Month` 枚举具有 `getDisplayName` 方法，用于以不同的区域和格式显示星期和月份名称。

```java
for (DayOfWeek w : DayOfWeek.values()) {
    System.out.print(
        w.getDisplayName(TextStyle.SHORT, Locale.ENGLISH) + " "
    ); // Mon Wed Fri
}
```

关于区域的更多信息请参见第 7 章。

![Image](img/00002.jpeg)

> 注意
>
> `java.time.format.DateTimeFormatter` 类旨在替换 `java.util.DateFormat`。如果你需要后者的实例，请调用 `format()`。

最后，你可以通过指定模式来自定义日期格式。例如：

```java
formatter = DateTimeFormatter.ofPattern("E yyyy-MM-dd HH:mm");
// 格式 1969-07-16 09:32
```

每个字母代表不同的时间字段，字母重复的次数选择特定的格式，这些规则随时间推演变得复杂。表 6.8 显示了最常用的模式元素。

![Image](img/00114.jpeg)

**表 6.8** 常用的日期/时间格式符号

要从字符串解析日期和时间值，请使用静态 `parse` 方法之一。例如：

```java
LocalDate churchsBirthday = LocalDate.parse("1903-06-14");

ZonedDateTime apollo11launch = ZonedDateTime.parse(
    "1969-07-16 03:32:00-0400",
    DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ssxx")
);
```

第一次调用使用标准的 `ISO_LOCAL_DATE` 格式化，第二次使用自定义格式化。

Listing 6.4 中的程序演示了如何格式化和解析日期与时间。

```java
package formatting;

import java.time.*;
import java.time.format.*;
import java.util.*;

public class Formatting {
    public static void main(String[] args) {
        DateTimeFormatter formatter =
            DateTimeFormatter.ofLocalizedDateTime(FormatStyle.LONG);

        ZonedDateTime apollo11launch = ZonedDateTime.of(
            1969, 7, 16, 9, 32, 0, 0,
            ZoneId.of("America/New_York")
        );

        String formatted = formatter.format(apollo11launch);
        System.out.println(formatted);
    }
}
```

```java
formatted = formatter.withLocale(Locale.FRENCH).format(apollo11launch);
// 16 juillet 1969 09:32:00 EDT
System.out.println(formatted);

formatter = DateTimeFormatter.ofPattern("E yyyy-MM-dd HH:mm");
formatted = formatter.format(apollo11launch);
System.out.println(formatted);

LocalDate churchsBirthday = LocalDate.parse("1903-06-14");
System.out.println("churchsBirthday: " + churchsBirthday);

apollo11launch = ZonedDateTime.parse(
    "1969-07-16 03:32:00-0400",
    DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ssxx")
);

System.out.println("apollo11launch: " + apollo11launch);

for (DayOfWeek w : DayOfWeek.values()) {
    System.out.print(
        w.getDisplayName(TextStyle.SHORT, Locale.ENGLISH) + " "
    );
}
```

### 6.7 与旧代码相互操作

作为一个全新的产物，Java 日期和时间 API 必须与现有类进行交互，特别是无处不在的 `java.util.Date`、`java.util.GregorianCalendar` 以及 `java.sql.Date`、`Time` 和 `Timestamp`。

`Instant` 类是 `java.util.Date` 的类比。在 Java SE 8 中，该类新增两个方法：将 `Date` 转换为 `Instant` 的 `toInstant` 方法，以及用于反向转换的静态方法 `from`。

同样，`ZonedDateTime` 是 `java.util.GregorianCalendar` 的类对应物，且该类在 Java SE 8 中获得了转换方法。`toZonedDateTime` 方法将 `GregorianCalendar` 转换为 `ZonedDateTime`，而静态方法 `from` 则执行相反转换。

`java.sql` 包中的日期和时间类还提供了另一组转换方法。你也可以将 `DateTimeFormatter` 传递给使用 `java.text.Format` 的旧代码。表 6.9 总结了这些转换。

![Image](img/00115.jpeg)

**表 6.9** `java.time` 类与旧类之间的转换

你现在已经知道如何使用 Java 8 日期时间库来处理世界各地的日期和时间值。下一章将进一步讨论面向国际观众的编程。你将看到如何按照客户习惯的方式格式化程序消息、数字和货币，无论他们身在何处。

# 第 7 章 国际化

## 本章内容

- 7.1 Locale
- 7.2 数字格式
- 7.3 货币
- 7.4 日期和时间
- 7.5 排序与归一化
- 7.6 消息格式化
- 7.7 文本输入输出
- 7.8 资源包
- 7.9 完整示例

世界很大；我们希望有很多居民对你的软件感兴趣。毕竟，互联网毫不费力地跨越了……之间的障碍。

### 7.1 Locale

世界很大；我们希望有很多居民对你的软件感兴趣。毕竟，互联网毫不费力地跨越了……之间的障碍。

## 区域设置概述

区域设置（Locales）的规则由互联网工程任务组的“最佳当前实践”备忘录 `BCP 47`（`http://tools.ietf.org/html/bcp47`）规定。你可以在 `www.w3.org/International/articles/language-tags` 找到更易读的摘要。

语言和国家代码看起来有些随机，因为其中一些源自本地语言。德语在德语中是 `Deutsch`，中文在中文里是 `zhongwen`：因此是 `de` 和 `zh`。瑞士是 `CH`，源自代表瑞士联邦的拉丁术语 *Confoederatio Helvetica*。

区域设置通过标签描述，即由连字符连接的区域元素组成的字符串，例如 `en-US`。

在德国，你会使用区域设置 `de-DE`。瑞士有四种官方语言：德语、法语、意大利语和罗曼什语。瑞士的一位德语使用者希望使用区域设置 `de-CH`。该区域设置使用德语的规则，但货币值以瑞士法郎表示，而不是欧元。

如果你只指定语言（例如 `de`），那么该区域设置将无法用于特定国家的问题，如货币。

## 创建区域设置对象

你可以像这样从标签字符串构造 `Locale` 对象：

```java
Locale usEnglish = Locale.forLanguageTag("en-US");
```

`toLanguageTag` 方法产生给定区域设置的语言标签。例如，`Locale.US.toLanguageTag()` 返回字符串 `"en-US"`。

### 预定义的区域设置对象

为了方便起见，程序库为各种国家提供了预定义的区域设置对象：

```java
Locale.CANADA
Locale.CANADA_FRENCH
Locale.CHINA
Locale.FRANCE
Locale.GERMANY
Locale.ITALY
Locale.JAPAN
Locale.KOREA
Locale.PRC
Locale.TAIWAN
Locale.UK
Locale.US
```

若干预定义的区域设置仅指定语言而未指定位置：

```java
Locale.CHINESE
Locale.ENGLISH
Locale.FRENCH
Locale.GERMAN
Locale.ITALIAN
Locale.JAPANESE
Locale.KOREAN
Locale.SIMPLIFIED_CHINESE
Locale.TRADITIONAL_CHINESE
```

最后，静态方法 `getAvailableLocales` 返回一个包含虚拟机所有区域设置的数组。

## 获取区域设置对象

除了构造区域设置或使用预定义的区域设置，你还有另外两种方法获取区域设置对象。

`Locale` 类的静态方法 `getDefault` 最初获取由本地操作系统存储的默认区域设置。你可以通过调用 `setDefault` 来更改默认 Java 区域设置；但该更改只影响你的程序，而不影响操作系统。

所有依赖于区域设置的工具类都可以返回它们支持的区域设置数组。例如：

```java
Locale[] supportedLocales = NumberFormat.getAvailableLocales();
```

返回 `NumberFormat` 类可以处理的所有区域设置。

> 提示
>
> 如果你想测试一个仅有语言和国家设置的区域设置，可以在启动程序时在命令行中提供它们。例如，在这里我们将默认区域设置为 `de-CH`：

```bash
java -Duser.language=de -Duser.region=CH MyProgram
```

一旦你有了区域设置，你用它能做什么呢？事实证明，没多少。`Locale` 类中唯一实用的方法是那些识别语言代码和国家代码的方法。最重要的方法是 `getDisplayName`。它返回一个描述区域设置的字符串。这个字符串不包含晦涩的两个字母代码，而是一种可以呈现给用户的形式，例如：

```text
German (Switzerland)
```

实际上，这里存在一个问题。显示名称是用默认区域设置显示的。这可能并不合适。如果你的用户已经选择了德语作为首选语言，你可能希望以德语呈现该字符串。你可以通过传递德语区域设置作为参数来实现。代码如下：

```java
Locale loc = new Locale("de", "CH");
System.out.println(loc.getDisplayName(Locale.GERMAN));
```



# 打印结果

## Deutsch (Schweiz)

这个示例展示了你为什么需要 `Locale` 对象。你将它们传递给感知区域设置的方法，产生呈现给不同位置用户的文本。你将在后续章节中看到许多此类示例。

---

### `java.util.Locale` 1.1

- `Locale(String language)`
- `Locale(String language, String country)`
- `Locale(String language, String country, String variant)` 使用给定的语言、国家和变体构造区域设置。不要在新代码中使用变体——请改用 IETF BCP 47 语言标签。
- `static Locale forLanguageTag(String languageTag)` 根据语言标签构造区域设置。
- `static Locale getDefault()` 获取默认区域设置。
- `static void setDefault(Locale loc)` 设置默认区域设置。
- `String getDisplayName()` 返回描述当前区域设置的名称。
- `String getDisplayName(Locale locale)` 返回给定区域设置的名称。
- `String getLanguage()` 返回语言代码，小写的两个字母 ISO。
- `String getDisplayLanguage()` 返回当前语言的显示名称。
- `String getLanguage(Locale locale)` 返回给定区域设置的语言。
- `String getCountry()` 返回国家代码，大写的两个字母 ISO。
- `String getDisplayCountry()` 返回当前位置的显示名称。
- `String getCountry(Locale locale)` 返回给定区域设置的国家。
- `String toLanguageTag()` 返回 IETF BCP 47 语言标签，例如 `"de-CH"`。
- `String toString()` 返回由下划线分隔的区域设置描述（例如 `"de_CH"`）。仅将此方法用于调试。

---

## 7.2 数字格式

我们已经提到数字格式化高度取决于区域设置。Java 库提供了一组可以格式化数值的格式对象。按照以下步骤对特定区域设置进行格式化：

1. 获取上述的区域设置对象。
2. 使用“工厂方法”获取格式化对象。
3. 使用格式化对象进行格式化和解析。

工厂方法是 `NumberFormat` 类的静态方法，接受 `Locale` 参数。有三个工厂方法：`getNumberInstance`、`getCurrencyInstance` 和 `getPercentInstance`。这些方法分别返回可以格式化和解析数字、货币和百分比的对象。例如，这里是如何使用德语格式化货币：

点击此处查看代码图片

```java
Locale loc = Locale.GERMAN;

NumberFormat currFmt = NumberFormat.getCurrencyInstance(loc);

double amt = 123456.78;

String result = currFmt.format(amt);
```

结果为：

`123.456,78 €`

注意货币符号 `€` 位于字符串末尾。注意小数点和逗号的反转。

相反，要读取按照特定区域设置输入或存储的数字，请使用 `parse` 方法。例如，以下代码解析了用户输入文本框的值。`parse` 方法可以处理小数点和逗号，以及其他语言的数字。

点击此处查看代码图片

```java
TextField inputField;

. . .

NumberFormat fmt = NumberFormat.getNumberInstance();

// 获取默认区域设置的数字格式器
Number input = fmt.parse(inputField.getText().trim());

double x = input.doubleValue();
```

`parse` 的返回类型是抽象类型 `Number`。返回的对象是 `Double` 或 `Long` 包装对象，取决于所解析的数字是否为浮点数。如果你不在乎这种区别，可以简单地使用 `Number` 类的 `doubleValue` 方法来获取被封装的数字。

![Image](img/00004.jpeg)

> **注意**
>
> `Number` 类型的对象不会自动拆箱——你不能简单地将 `Number` 对象赋值给原始数据类型。相反，请使用 `doubleValue` 或 `intValue` 方法。

如果数字的文本格式不正确，该方法将抛出 `ParseException`。例如，字符串开头的空格是不允许的。（请调用 `trim` 来移除它）。然而，字符串中数字之后的任何字符都会直接被忽略，因此不会抛出异常。

请注意，`getXxxInstance` 工厂方法返回的类实际上并不是 `NumberFormat` 类型。`NumberFormat` 是一个抽象类，实际的格式化器属于它的某个子类。工厂方法仅知道如何定位属于特定区域设置（locale）的对象。

你可以使用静态方法 `getAvailableLocales` 获取当前支持的区域设置列表。该方法返回一个可以获取数字格式化器对象的区域设置数组。

本节的示例程序让你能够实验数字格式化器（参见图 7.1）。图中顶部的组合框包含了所有带有数字格式化器的区域设置。你可以在数字、货币和百分比格式化器之间进行选择。每当你做出另一个选择，文本框中的数字就会重新格式化。如果你遍历几个区域设置，就可以对数字或货币值的多种格式化方式有一个良好的印象了。你还可以输入一个不同的数字并点击 Parse 按钮来调用 `parse` 方法，该方法会尝试解析你输入的内容。如果输入解析成功，将将其传递给 `format` 并显示结果。如果解析失败，文本框中将显示“Parse error”消息。

![Image](img/00119.jpeg)

**图 7.1** `NumberFormatTest` 程序

代码如列表 7.1 所示，非常直观。在构造函数中，我们调用了 `NumberFormat.getAvailableLocales`。对于每个区域设置，我们调用 `getDisplayName` 并用 `getDisplayName` 方法返回的字符串填充组合框。（这些字符串没有排序；我们将在第 7.5 节“排序与规范化”中解决这个问题，参见第 393 页。）每当用户选择另一个区域设置或点击单选按钮时，我们都会创建一个格式化器对象并更新文本框。当用户点击 Parse 按钮时，我们调用 `parse` 方法根据选定的区域设置进行实际解析。

![Image](img/00002.jpeg)

> **注意**
>
> 你可以使用 `Scanner` 来读取本地化的整数和浮点数。调用 `useLocale` 方法设置区域设置。

**列表 7.1** `numberFormat/NumberFormatTest.java`

点击此处查看代码图像

```java
package numberFormat;

import java.awt.*;
import java.awt.event.*;
import java.text.*;
import java.util.*;
import javax.swing.*;

/**
 * 此程序演示了不同区域设置下的数字格式化。
 * @version 1.14 2016-05-06
 * @author Cay Horstmann
 */
public class NumberFormatTest
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() ->
            {
                JFrame frame = new NumberFormatFrame();
                frame.setTitle("NumberFormatTest");
                frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
                frame.setVisible(true);
            });
    }
}

/**
 * 此框架包含用于选择数字格式的单选按钮、用于选择区域设置的组合框、
 * 用于显示格式化数字的文本框，以及用于解析文本框的按钮。
 */
class NumberFormatFrame extends JFrame
{
    Locale[] locales;
    double currentNumber;
    JComboBox<String> localeCombo = new JComboBox<>();
    JButton parseButton = new JButton("Parse");
    JTextField numberText = new JTextField(30);
    JRadioButton numberRadioButton = new JRadioButton("Number");
    JRadioButton currencyRadioButton = new JRadioButton("Currency");
    JRadioButton percentRadioButton = new JRadioButton("Percent");
    ButtonGroup rbGroup = new ButtonGroup();
    NumberFormat currentNumberFormat;

    public NumberFormatFrame()
    {
        setLayout(new GridBagLayout());
        ActionListener listener = event -> updateDisplay();
        JPanel p = new JPanel();

        add(p, numberRadioButton, rbGroup, listener);
        add(p, currencyRadioButton, rbGroup, listener);
        add(p, percentRadioButton, rbGroup, listener);
        add(new JLabel("Locale:"), new GBC(0, 0).setAnchor(GBC.EAST));
        add(p, new GBC(1, 1));
        add(parseButton, new GBC(0, 2).setInsets(2));
        add(localeCombo, new GBC(1, 0).setAnchor(GBC.WEST));
        add(numberText, new GBC(1, 2).setFill(GBC.HORIZONTAL));

        locales = (Locale[]) NumberFormat.getAvailableLocales().clone();
        Arrays.sort(locales, Comparator.comparing(Locale::getDisplayName));

        for (Locale loc : locales)
            localeCombo.addItem(loc.getDisplayName());

        localeCombo.setSelectedItem(Locale.getDefault().getDisplayName());
        currentNumber = 123456.78;
        updateDisplay();

        localeCombo.addActionListener(listener);
        parseButton.addActionListener(event ->
            {
                String s = numberText.getText().trim();

                try
                {
                    Number n = currentNumberFormat.parse(s);

                    if (n != null)
                    {
                        currentNumber = n.doubleValue();
                        updateDisplay();
                    }
                    else
                    {
                        numberText.setText("Parse error: " + s);
                    }
                }
                catch (ParseException e)
                {
                    numberText.setText("Parse error: " + s);
                }
            });

        pack();
    }

    /**
     * 向容器中添加单选按钮。
     * @param p 放置按钮的容器
     * @param b 按钮
     * @param g 按钮组
     * @param listener 按钮监听器
     */
    public void addRadioButton(Container p, JRadioButton b, ButtonGroup g, ActionListener listener)
    {
        b.setSelected(g.getButtonCount() == 0);
        b.addActionListener(listener);
        g.add(b);
        p.add(b);
    }

    /**
     * 根据用户设置更新显示并格式化数字。
     */
    public void updateDisplay()
    {
        Locale currentLocale = locales[localeCombo.getSelectedIndex()];
        currentNumberFormat = null;

        if (numberRadioButton.isSelected())
            currentNumberFormat = NumberFormat.getNumberInstance(currentLocale);
        else if (currencyRadioButton.isSelected())
            currentNumberFormat = NumberFormat.getCurrencyInstance(currentLocale);
    }
}
```

```java
else if (percentRadioButton.isSelected()) {
    currentNumberFormat = NumberFormat.getPercentInstance(currentLocale);
    String formatted = currentNumberFormat.format(currentNumber);
    numberText.setText(formatted);
}
```




### `java.text.NumberFormat` 1.1

- `static Locale[] getAvailableLocales()`

  返回一个 `NumberFormat` 格式器可用的 `Locale` 对象数组。

- `static NumberFormat getNumberInstance()`
- `static NumberFormat getNumberInstance(Locale l)`
- `static NumberFormat getCurrencyInstance()`
- `static NumberFormat getCurrencyInstance(Locale l)`
- `static NumberFormat getPercentInstance()`
- `static NumberFormat getPercentInstance(Locale l)`

  返回用于当前区域或给定区域的数字、货币金额或百分比值的格式器。

- `String format(double x)`
- `String format(long x)`

  返回对给定的浮点数或整数格式化后的字符串。

- `Number parse(String s)`

  解析给定的字符串并返回数值。如果输入字符串描述的是浮点数，则返回 `Double`，否则返回 `Long`。字符串的开头必须包含数字；不允许有前导空格。数字后面可以跟随其他字符，这些字符会被忽略。如果解析失败，则抛出 `ParseException`。

- `void setParseIntegerOnly(boolean b)`
- `boolean isParseIntegerOnly()`

  设置或获取标记，用于指示此格式器是否仅解析整数值。

- `void setGroupingUsed(boolean b)`
- `boolean isGroupingUsed()`

  设置或获取标记，用于指示此格式器是否生成并识别分组分隔符（例如 `100,000`）。

- `void setMinimumIntegerDigits(int n)`
- `int getMinimumIntegerDigits()`
- `void setMaximumIntegerDigits(int n)`
- `int getMaximumIntegerDigits()`
- `void setMinimumFractionDigits(int n)`
- `int getMinimumFractionDigits()`
- `void setMaximumFractionDigits(int n)`
- `int getMaximumFractionDigits()`

  设置或获取数字整数部分或小数部分允许的最大或最小位数。

### 7.3 货币

要格式化货币值，可以使用 `NumberFormat.getCurrencyInstance` 方法。然而，该方法并不灵活——它返回一个单一货币的格式器。假设你为一位美国客户准备一份发票，其中某些金额是美元，另一些是欧元。你不能简单地使用两个格式器：

```java
NumberFormat dollarFormatter = NumberFormat.getCurrencyInstance(Locale.US);

NumberFormat euroFormatter = NumberFormat.getCurrencyInstance(Locale.GERMANY);
```

你的发票看起来会非常奇怪，某些值格式化为 `$100,000`，而另一些则为 `100.000 €`。（注意，欧元值使用的是小数点而不是逗号。）

相反，请使用 `Currency` 类来控制格式器使用的货币。你可以通过将货币标识传递给静态方法 `Currency.getInstance` 来获取 `Currency` 对象。然后为每个格式器调用 `setCurrency` 方法。以下是你如何为你的美国客户设置欧元格式器：

```java
NumberFormat euroFormatter = NumberFormat.getCurrencyInstance(Locale.US);

euroFormatter.setCurrency(Currency.getInstance("EUR"));
```

货币标识由 ISO 4217 定义（参见 `www.currency-iso.org/iso_index/ iso_tables/iso_tables_a1.htm`）。表 7.3 提供了部分列表。

![Image](img/00120.jpeg)

**表 7.3** 货币标识

### `java.util.Currency` 1.4

- `static Currency getInstance(String currencyCode)`
- `static Currency getInstance(Locale locale)`

  返回用于给定 ISO 4217 货币代码或给定区域对应国家的 `Currency` 实例。

- `String toString()`
- `String getCurrencyCode()`

  获取此货币的 ISO 4217 货币代码。

- `String getSymbol()`
- `String getSymbol(Locale locale)`

  获取此货币在默认区域或给定区域的格式化符号。例如，USD 的符号可以是 `$` 或 `US$`，取决于区域。

- `int getDefaultFractionDigits()`

  获取此货币的默认小数位数。

- `static Set<Currency> getAvailableCurrencies()`

  获取所有可用的货币。

### 7.4 日期和时间

当你格式化日期和时间时，你应该关注四个与区域相关的问题：

- 月份和星日的名称应以本地语言呈现。
- 年、月、日的顺序会有不同的偏好。
- 格列哥历可能不是本地历法。
- 必须考虑时区。

`java.time` 中的 `DateTimeFormatter` 类处理这些问题。选择 `FormatStyle.SHORT`、`FormatStyle.MEDIUM`、`FormatStyle.LONG` 或 `FormatStyle.FULL` 之一。

```java
FormatStyle style = FormatStyle.SHORT;

DateTimeFormatter dateFormatter = DateTimeFormatter.ofLocalizedDate(style);

DateTimeFormatter timeFormatter = DateTimeFormatter.ofLocalizedTime(style);

DateTimeFormatter dateTimeFormatter = DateTimeFormatter.ofLocalizedDateTime(style);
```

**表 7.4** 日期和时间样式

这些格式器使用当前区域。要使用不同的区域，请使用 `withLocale`：

```java
ZonedDateTime appointment = dateFormatter.withLocale(locale).format(appointment);
```

这里我们使用 `java.time` 中的 `DateTimeFormatter`。还有旧版的 `java.text.DateFormatter`，它与 `Date` 和 `Calendar` 对象配合。

你可以使用 `LocalDate`、`LocalDateTime`、`LocalTime` 或 `ZonedDateTime` 的静态 `parse` 方法来解析字符串中的日期或时间：

```java
LocalTime time = LocalTime.parse("9:32 AM", formatter);
```

这些方法不适用于解析人类输入，至少在没有预处理的情况下。例如，美国的短时间格式器可以解析 `"9:32 AM"`，但不能解析 `"9:32AM"` 或 `"9:32 am"`。

注意日期格式器会解析不存在的日期（例如 11 月 31 日），并将其调整为该月的最后一天。

有时，你需要显示星日的月份名称，例如在日历应用程序中。调用 `DayOfWeek` 和 `Month` 枚举的 `getDisplayName` 方法。

```java
// （此处省略代码内容）
```

[表 7.5] 显示了文本样式。`STANDONE` 版本用于格式化日期之外的显示。例如，在芬兰语中，一月在日期内部是“tammikuuta”，但独立显示时是“tammikuu”。

每周的第一天可以是周六、周日或周一，取决于区域。你可以通过以下方式获取：

```java
DayOfWeek first = WeekFields.of(locale).getFirstDayOfWeek();
```

列表 7.2 展示了 `DateFormat` 类的用法。你可以选择一个本地区域（locale），并查看世界各地日期和时间是如何格式化的。

图 7.2 显示了程序（安装中文字体后）。如你所示，它正确地显示了输出。

![Image](img/00123.jpeg)

**图 7.2** `DateFormatTest` 程序

你也可以尝试解析。输入日期、时间或日期/时间，然后点击 Parse（解析）按钮。

我们使用了一个辅助类 `EnumCombo` 来解决一个技术问题（参见列表 7.3）。我们希望在组合框中填充 `Short`、`Medium` 和 `Long` 等值，然后将用户的选择自动转换为值 `FormatStyle.SHORT`、`FormatStyle.MEDIUM` 和 `FormatStyle.LONG`。我们没有编写重复的代码，而是使用了反射：我们将用户的选择转换为大写，将所有空格替换为下划线，然后找到具有该名称的静态字段的值。（反射的更多细节，请参见第一卷第 5 章。）

**列表 7.2** `dateFormat/DateTimeFormatterTest.java`

点击此处查看代码图片

```java
package dateFormat;

import java.awt.*;

import java.awt.event.*;

import java.time.*;

import java.time.format.*;

import java.util.*;

import javax.swing.*;

/**
 * 此程序演示了在不同本地区域格式化日期。
 * @version 1.00 2016-05-06
 * @author Cay Horstmann
 */
public class DateTimeFormatterTest
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() ->
        {
            JFrame frame = new DateTimeFormatterFrame();
            frame.setTitle("DateFormatTest");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}

/**
 * 此框架包含用于选择本地区域、日期和时间格式的组合框，
 * 用于显示格式化后的日期和时间的文本字段，用于解析文本字段内容的按钮，以及一个“宽松”的复选框。
 */
class DateTimeFormatterFrame extends JFrame
{
    private Locale[] locales;

    private LocalDate currentDate;

    private LocalTime currentTime;

    private ZonedDateTime currentDateTime;

    private DateTimeFormatter currentDateFormat;

    private DateTimeFormatter currentTimeFormat;

    private DateTimeFormatter currentDateTimeFormat;

    private JComboBox<String> localeCombo = new JComboBox<>();

    private JButton dateParseButton = new JButton("Parse");

    private JButton timeParseButton = new JButton("Parse");

    private JButton dateTimeParseButton = new JButton("Parse");

    private JTextField dateText = new JTextField(30);

    private JTextField timeText = new JTextField(30);

    private JTextField dateTimeText = new JTextField(30);

    private EnumCombo<FormatStyle> dateStyleCombo =
        new EnumCombo<>(FormatStyle.class, "Short", "Medium", "Long");

    private EnumCombo<FormatStyle> timeStyleCombo =
        new EnumCombo<>(FormatStyle.class, "Short", "Medium");

    private EnumCombo<FormatStyle> dateTimeStyleCombo =
        new EnumCombo<>(FormatStyle.class, "Short", "Medium", "Long");

    public DateTimeFormatterFrame()
    {
        setLayout(new GridBagLayout());

        add(new JLabel("Locale"), GBC(0, 0).setAnchor(GBC.EAST));

        add(localeCombo, GBC(1, 0, 2, 1).setAnchor(GBC.WEST));

        add(new JLabel("Date"), GBC(0, 1).setAnchor(GBC.EAST));

        add(dateStyleCombo, GBC(1, 1).setAnchor(GBC.WEST));

        add(dateText, GBC(2, 1, 2, 1).setFill(GBC.HORIZONTAL));

        add(dateParseButton, GBC(4, 1).setAnchor(GBC.WEST));

        add(new JLabel("Time"), GBC(0, 2).setAnchor(GBC.EAST));

        add(timeStyleCombo, GBC(1, 2).setAnchor(GBC.WEST));

        add(timeText, GBC(2, 2, 2, 1).setFill(GBC.HORIZONTAL));

        add(timeParseButton, GBC(4, 2).setAnchor(GBC.WEST));

        add(new JLabel("Date and time"), GBC(0, 3).setAnchor(GBC.EAST));

        add(dateTimeStyleCombo, GBC(1, 3).setAnchor(GBC.WEST));

        add(dateTimeText, GBC(2, 3, 2, 1).setFill(GBC.HORIZONTAL));

        add(dateTimeParseButton, GBC(4, 3).setAnchor(GBC.WEST));

        locales = (Locale[]) Locale.getAvailableLocales().clone();

        Arrays.sort(locales, Comparator.comparing(Locale::getDisplayName));

        for (Locale loc : locales)
            localeCombo.addItem(loc.getDisplayName());

        localeCombo.setSelectedItem(Locale.getDefault().getDisplayName());

        currentDate = LocalDate.now();

        currentTime = LocalTime.now();

        currentDateTime = ZonedDateTime.now();

        updateDisplay();

        ActionListener listener = event -> updateDisplay();

        localeCombo.addActionListener(listener);

        dateStyleCombo.addActionListener(listener);

        timeStyleCombo.addActionListener(listener);
```




```java
dateTimeStyleCombo.addActionListener(listener);

dateParseButton.addActionListener(event ->
{
    String d = dateText.getText().trim();

    try
    {
        currentDate = LocalDate.parse(d, currentDateFormat);
        updateDisplay();
    }
    catch (Exception e)
    {
        dateText.setText(e.getMessage());
    }
});

timeParseButton.addActionListener(event ->
{
    String t = timeText.getText().trim();

    try
    {
        currentTime = LocalTime.parse(t, currentTimeFormat);
        updateDisplay();
    }
    catch (Exception e)
    {
        timeText.setText(e.getMessage());
    }
});

dateTimeParseButton.addActionListener(event ->
{
    String t = dateTimeText.getText().trim();

    try
    {
        currentDateTime = ZonedDateTime.parse(t, currentDateTimeFormat);
        updateDisplay();
    }
    catch (Exception e)
    {
        dateTimeText.setText(e.getMessage());
    }
});

pack();
}

/**
 * 根据用户设置更新显示并格式化日期。
 */
public void updateDisplay()
{
    Locale currentLocale = locales[localeCombo.getSelectedIndex()];

    FormatStyle dateStyle = dateStyleCombo.getValue();
    currentDateFormat = DateTimeFormatter.ofLocalizedDate(dateStyle).withLocale(currentLocale);
    dateText.setText(currentDateFormat.format(currentDate));

    FormatStyle timeStyle = timeStyleCombo.getValue();
    currentTimeFormat = DateTimeFormatter.ofLocalizedTime(timeStyle).withLocale(currentLocale);
    timeText.setText(currentTimeFormat.format(currentTime));

    FormatStyle dateTimeStyle = dateTimeStyleCombo.getValue();
    currentDateTimeFormat = DateTimeFormatter.ofLocalizedDateTime(dateTimeStyle).withLocale(currentLocale);
    dateTimeText.setText(currentDateTimeFormat.format(currentDateTime));
}
```

点击此处查看代码图像

```java
package dateFormat;

import java.util.*;
import javax.swing.*;

/**
 * 一个组合框，允许用户从构造函数中给出的静态字段
 * 的值中进行选择。
 *
 * @version 1.15 2016-05-06
 * @author Cay Horstmann
 */
public class EnumCombo<T> extends JComboBox<String>
{
    private Map<String, T> table = new TreeMap<>();

    /**
     * 构造一个产生类型 T 值的 EnumCombo。
     *
     * @param cl 一个类
     * @param labels 一个字符串数组，用于描述 cl 中类型为 T 的
     *              静态字段的名称
     */
    public EnumCombo(Class<?> cl, String... labels)
    {
        for (String label : labels)
        {
            String name = label.toUpperCase().replace(' ', '_');

            try
            {
                java.lang.reflect.Field f = cl.getField(name);
                @SuppressWarnings("unchecked")
                T value = (T) f.get(cl);
                table.put(label, value);
            }
            catch (Exception e)
            {
                label = "(" + label + ")";
                table.put(label, null);
            }

            addItem(label);
        }

        setSelectedItem(labels[0]);
    }

    /**
     * 返回用户选择字段的值。
     *
     * @return 静态字段值
     */
    public T getValue()
    {
        return table.get(getSelectedItem());
    }
}
```

### `java.time.format.DateTimeFormatter`

- `static DateTimeFormatter ofLocalizedDate(FormatStyle dateStyle)`
- `static DateTimeFormatter ofLocalizedTime(FormatStyle dateStyle)`
- `static DateTimeFormatter ofLocalizedDateTime(FormatStyle dateTimeStyle)`
- `static DateTimeFormatter ofLocalizedDate(FormatStyle dateStyle, FormatStyle timeStyle)` 返回使用指定样式格式化日期、时间或日期和时间的 `DateTimeFormatter` 实例。
- `DateTimeFormatter withLocale(Locale locale)` 返回此格式化器的副本，使用指定的 locale。
- `String format(TemporalAccessor temporal)` 返回对给定日期/时间格式化后的字符串。
- `java.time.LocalDate`
- `java.time.LocalTime`
- `java.time.ZonedDateTime`
- `static parse(CharSequence text, DateTimeFormatter formatter)` 解析给定字符串并返回其中描述的 `LocalDate`、`LocalTime` 或 `ZonedDateTime`。如果解析失败，则抛出 `DateTimeParseException`。

### 7.5 排序与规范化

大多数程序员知道如何使用 `String` 类的 `compareTo` 方法比较字符串。遗憾的是，在与人类交互时，这个方法并没有用。`compareTo` 方法使用字符串的 UTF-16 编码值，这会导致荒谬的结果，即使在英语中也是如此。例如，以下字符串根据 `compareTo` 排序：

```
America
zebra
Ångström
```

对于字典排序，你可能希望大写和小写是等价的。对于英语使用者来说，示例单词列表的顺序应该是：

```
America
Ångström
zebra
```

然而，这种顺序对于瑞典用户来说是不可接受的。在瑞典语中，字母 `Å` 与字母 `A` 不同，并且排在字母 `Z` 之后！也就是说，瑞典用户希望单词按以下顺序排序：

```
America
zebra
Ångström
```

要获取一个区域敏感的排序器，请调用静态的 `Collator.getInstance` 方法：点击此处查看代码图像

```java
Collator coll = Collator.getInstance(locale);

words.sort(coll); // Collator 实现 Comparator<Object>
```

由于 `Collator` 类实现了 `Comparator` 接口，你可以将 `Collator` 对象传递给 `List.sort(Comparator)` 方法来对字符串列表进行排序。

排序器有几个高级设置。你可以设置排序器的 `strength`（强度）来选择它的选择性程度。字符差异被分类为 `primary`（初）、`secondary`（次级）或 `tertiary`（三级）。例如，在英语中，“A”和“Z”之间的差异被视为初级的，“A”和“Å”之间的差异被视为次级的，而“A”和“a”之间的差异是三级的。

通过将排序器的强度设置为 `Collator.PRIMARY`，你告诉它只关注初级差异。通过将强度设置为 `Collator.SECONDARY`，你指示排序器考虑次级差异。也就是说，当强度设置为“次级”或“三级”时，两个字符串更有可能被认为是不同的，如表表 7.6](#part0012.html_ch07tab06) 所示。

![图像](img/00124.jpeg)

**表 7.6 不同强度的排序（英语区域）**

当强度被设置为 `Collator.IDENTICAL` 时，不允许有任何差异。此设置主要与一种相当有技术性的排序器设置——分解模式（decomposition mode）结合使用，我们将在接下来讨论它。

偶尔，一个字符或字符序列在 Unicode 中可以用多种方式进行描述。例如，“Å”可以是 Unicode 字符 `U+00C5`，也可以表示为普通的 `A`（`U+0065`）后跟一个 `°`（“组合环形符号”；`U+030A`）。或许令人惊讶的是，字母序列“ffi”可以用单个字符“拉丁小写连字 ffi”（代码为 `U+FB03`）来描述。（有人认为这是一个显示问题，本应该产生不同的 Unicode 字符，但我们不制定规则。）

Unicode 标准为字符串定义了四种规范化形式（D、KD、C 和 KC）。详情请参阅 `www.unicode.org/unicode/reports/tr15/tr15–23.html`。在规范化形式 C 中，带重音的字符总是组合的。例如，A 和组合环形符号 `°` 的序列组合成单个字符 `Å`。在形式 D 中，带重音的字符总是分解为它们的基础字母和组合重音：`Å` 转换为 `A` 后跟 `°`。形式 KC 和 KD 也会分解诸如连字或商标符号之类的字符。

你可以选择希望排序器使用的规范化程度。`Collator.NO_DECOMPOSITION` 值完全不对字符串进行规范化。此选项更快，但可能不适用于以多种形式表示的文本。默认的 `Collator.CANICAL_DECOMPOSITION` 使用规范化形式 D。这对于包含重音但不包含连字的文本很有用。最后，“全分解”使用规范化形式 KD。示例请参见表 7.7。

![图像](img/00125.jpeg)

**表 7.7 分解模式之间的差异**

多次分解字符串是浪费资源的。如果一个字符串与其他字符串进行多次比较，你可以将分解结果保存在排序键对象中。`getCollationKey` 方法返回 `CollationKey` 对象，你可以用它进行后续的快速比较。这是一个示例：点击此处查看代码图像

```java
String a = . . .;

CollationKey aKey = coll.getCollationKey(a);

if (aKey.compareTo(coll.getCollationKey(b)) == 0) // 快速比较

. . .
```

最后，即使你不进行排序，可能也希望将字符串转换为规范化形式——例如在数据库中存储字符串或与其他程序通信时。`java.text.Normalizer` 类执行规范化过程。例如，点击此处查看代码图像

```java
String name = "Ångström";

String normalized = Normalizer.normalize(name, Normalizer.Form.NFD); // 使用规范化形式 D
```

归一化字符串包含十个字符。“Å”和“ö”被替换为“A°”和“o¨”序列。

然而，这通常不是存储和传输的最佳形式。规范化形式 C（Normalization form C）首先应用分解，然后按照标准顺序将重音符号组合回去。根据 W3C 的规定，这是在互联网上传输数据的推荐模式。

列表 7.4 中的程序允许你对排序顺序进行实验。在文本字段中输入单词并点击“Add”按钮将其添加到单词列表中。每当你添加另一个单词，或者更改语言区域、强度或分解模式时，单词列表都会重新排序。`=` 号表示被认为相同的单词（请参见图 7.3）。

![Image](img/00126.jpeg)

**图 7.3** `CollationTest` 程序

组合框中的语言区域使用默认语言区域的比较器按排序顺序显示。如果你使用美国英语语言区域运行此程序，请注意“Norwegian (Norway,Nynorsk)”排在“Norwegian (Norway)”之前，尽管逗号字符的 Unicode 值大于右括号的 Unicode 值。

**列表 7.4** `collation/CollationTest.java`

点击此处查看代码图像

```java
package collation;

import java.awt.*;
import java.awt.event.*;
import java.text.*;
import java.util.*;
import java.util.List;
import javax.swing.*;

/**
 * 此程序演示了在不同语言区域下的字符串排序。
 *
 * @version 1.15 2016-05-06
 * @author Cay Horstmann
 */
public class CollationTest
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() ->
        {
            JFrame frame = new CollationFrame();
            frame.setTitle("CollationTest");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }

    /**
     * 此框架包含用于选择语言区域、排序强度和分解规则的组合框，
     * 用于添加新字符串的文本字段和按钮，以及用于列出排序字符串的文本区域。
     */
    class CollationFrame extends JFrame
    {
        private Collator collator = Collator.getInstance(Locale.getDefault());
        private List<String> strings = new ArrayList<>();
        private Collator currentCollator;
        private Locale[] locales;
```



```java
private JComboBox<String> localeCombo = new JComboBox<>();

private JTextField newWord = new JTextField(20);

private JTextArea sortedWords = new JTextArea(20, 20);

private JButton addButton = new JButton("Add");

private EnumCombo<Integer> strengthCombo = new EnumCombo<>(Collator.class, "Primary", "Secondary", "Tertiary", "Identical");

private EnumCombo<Integer> decompositionCombo = new EnumCombo<>(Collator.class, "Canonical Decomposition", "Full Decomposition", "No Decomposition");

public CollationFrame()
{
    setLayout(new GridBagLayout());

    add(new JLabel("Locale"), GBC(0, 0).setAnchor(GBC.EAST));

    add(new JLabel("Strength"), GBC(0, 1).setAnchor(GBC.EAST));

    add(new JLabel("Decomposition"), GBC(0, 2).setAnchor(GBC.EAST));

    add(addButton, GBC(0, 3).setAnchor(GBC.EAST));

    add(localeCombo, GBC(1, 0).setAnchor(GBC.WEST));

    add(strengthCombo, GBC(1, 1).setAnchor(GBC.WEST));

    add(decompositionCombo, GBC(1, 2).setAnchor(GBC.WEST));

    add(newWord, GBC(1, 3).setFill(GBC.HORIZONTAL));

    add(new JScrollPane(sortedWords), GBC(0, 4, 2, 1).setFill(GBC.BOTH));

    locales = (Locale[]) Collator.getAvailableLocales().clone();

    Arrays.sort(locales, (l1, l2) -> collator.compare(l1.getDisplayName(), l2.getDisplayName()));

    for (Locale loc : locales)
        localeCombo.addItem(loc.getDisplayName());

    localeCombo.setSelectedItem(Locale.getDefault().getDisplayName());

    strings.add("America");

    strings.add("able");

    strings.add("Zulu");

    strings.add("zebra");

    strings.add("\u00C5ngstr\u00F6m");

    strings.add("A\u030angstro\u0308m");

    strings.add("Angstrom");

    strings.add("Able");

    strings.add("office");

    strings.add("o\uFB03ce");

    strings.add("Java\u2122");

    strings.add("JavaTM");

    updateDisplay();

    addButton.addActionListener(event ->
    {
        strings.add(newWord.getText());

        updateDisplay();
    });

    ActionListener listener = event -> updateDisplay();

    localeCombo.addActionListener(listener);

    strengthCombo.addActionListener(listener);

    decompositionCombo.addActionListener(listener);

    pack();
}

/**
 * 根据用户更新显示并排序字符串。
 */
public void updateDisplay()
{
    Locale currentLocale = locales[localeCombo.getSelectedIndex()];

    localeCombo.setLocale(currentLocale);

    currentCollator = Collator.getInstance(currentLocale);

    currentCollator.setStrength(strengthCombo.getValue());

    currentCollator.setDecomposition(decompositionCombo.getValue());

    Collections.sort(strings, currentCollator);

    sortedWords.setText("");

    for (int i = 0; i < strings.size(); i++)
    {
        String s = strings.get(i);

        if (i > 0 && currentCollator.compare(s, strings.get(i - 1)) == 0)
            sortedWords.append("= ");

        sortedWords.append(s + "\n");
    }

    pack();
}
```

## `java.text.Collator`

- `static Locale[] getAvailableLocales()` 返回可用 `Collator` 对象的语言区域数组。
- `static Collator getInstance()`
- `static Collator getInstance(Locale l)` 返回默认语言区域或指定语言区域的比较器。
- `int compare(String a, String b)` 如果 `a` 在 `b` 之前返回负值，如果被认为相同则返回 `0`，否则返回正值。
- `boolean equals(String a, String b)` 如果 `a` 和 `b` 被认为相同返回 `true`，否则返回 `false`。
- `void setStrength(int strength)`
- `int getStrength()` 设置或获取比较器的强度。越强的比较器区分单词越多。强度值为 `Collator.PRIMARY`、`Collator.SECONDARY` 和 `Collator.TERTIARY`。
- `void setDecomposition(int decomp)`
- `int getDepositon()` 设置或获取比较器的分解模式。比较器分解字符串越多，在判断两个字符串是否相同时就越严格。分解值为 `Collator.NO_DECOMPOSITION`、`Collator.CANONICAL_DECOMPOSITION` 和 `Collator.FULL_DECOMPOSITION`。
- `CollationKey getCollationKey(String a)` 返回一个包含字符分解形式的比较键，可以快速与另一个比较键进行比较。

## `java.text.CollationKey`

- `int compareTo(CollationKey b)` 如果此键在 `b` 之前返回负值，如果被认为相同则返回 `0`，否则返回正值。

## `java.text.Normalizer`

- `static String normalize(CharSequence str, Normalizer.Form form)` 返回 `str` 的归一化形式。`form` 值是 `ND`、`NKD`、`NC` 或 `NKC` 之一。

`java.text.MessageFormat` 类用于格式化带有变量文本的消息。它与使用 `printf` 方法格式化类似，但支持区域以及数字和日期的格式。我们将在接下来的章节中检查该机制。

### 7.6.1 格式化数字和日期

这是一个典型的消息格式字符串：

> “在{2}，一次{0}摧毁了{1}房屋，造成了{3}的损失。”

大括号中的数字是实际名称和值的占位符。静态方法 `MessageFormat.format` 允许你为变量替换值。这是一个“可变参数”（varargs）方法，因此你可以如下地提供参数：

```java
String msg = MessageFormat.format(
    "On {2}, a {0} destroyed {1} houses and caused {3} of damage.",
    "hurricane",
    99,
    new GregorianCalendar(1999, 0, 1).getTime(),
    10.0E8
);
```

在这个示例中，占位符 `{0}` 被替换为 `"hurricane"`，`{1}` 被替换为 `99`，依此类推。

我们示例的结果是字符串：

> 1/1/99 12:00 AM，一次飓风摧毁了 99 栋房屋，造成了 100,000,000 的损失。

这只是一个开始，但并不完美。我们不想显示时间“12:00 AM”，并且希望损失金额以货币值的形式打印。我们实现此点的方法为某些占位符提供可选的格式：

> “在{2,date,long}，一次{0}摧毁了{1}房屋，造成了{3,number,currency}的损失。”

此示例代码打印出：

> January 1, 1999，一次飓风摧毁了 99 栋房屋，造成了 $100,000,000 的损失。

通常，占位符索引后可以跟随一个*类型*（type）和一个*样式*（style）。用逗号分隔索引、类型和样式。类型可以是以下任何一种：

- `number`（数字）
- `time`（时间）
- `date`（日期）
- `choice`（选择）

如果类型是 `number`，则样式可以是：

- `integer`（整数）
- `currency`（货币）
- `percent`（百分比）

或者是一个数字格式模式，如 `$,##0`。（有关可能格式的更多信息，请参 `DecimalFormat` 类的文档。）

如果类型是 `time` 或 `date`，则样式可以是：

- `short`（短）
- `medium`（中）
- `long`（长）
- `full`（全）

或者是一个日期格式模式，如 `yyyy-MM-dd`。（有关可能格式的更多信息，请参阅 `SimpleDateFormat` 类的文档。）

> **注意**
>
> 静态方法 `MessageFormat.format` 使用当前区域（locale）来格式化值。要使用任意区域进行格式化，你需要额外努力，因为没有可以直接使用的“可变参数”方法。你需要将要格式化的值放入一个 `Object[]` 数组中，如下：

```java
MessageFormat mf = new MessageFormat(pattern, loc);

String msg = mf.format(new Object[] { values });
```

## `java.text.MessageFormat` 1.1

- `MessageFormat(String pattern)`
- `MessageFormat(String pattern, Locale loc)`  
  使用指定的模式和区域构造消息格式对象。
- `void applyPattern(String pattern)`  
  将消息格式对象的模式设置为指定的模式。
- `void setLocale(Locale loc)`
- `Locale getLocale()`  
  设置或获取用于消息中占位符的区域。该区域*仅*用于你通过调用 `applyPattern` 方法设置的后续模式。
- `static String format(String pattern, Object... args)`  
  使用 `args[i]` 作为占位符 `{i}` 的输入格式化模式字符串。
- `StringBuffer format(Object args, StringBuffer result, FieldPosition pos)`  
  格式化此 `MessageFormat` 的模式。`args` 参数必须是一个对象数组。格式化后的字符串附加到 `result` 中，并返回 `result`。如果 `pos` 等于 `new FieldPosition(MessageFormat.Field.ARGUMENT)`，它的 `beginIndex` 和 `endIndex` 属性被设置为替换 `{1}` 占位符文本的位置。如果你对位置信息感兴趣，提供 `null`。

## `java.text.Format` 1.1

- `String format(Object obj)`  
  根据此格式化器的规则格式化给定的对象。此方法调用 `format(obj, new StringBuffer(), new FieldPosition(1)).toString()`。

### 7.6.2 选择格式（Choice Formats）

让我们仔细观察前一节：

> “在{2}，一次{0}摧毁了{1}房屋，造成了{3}的损失。”

大括号中的数字是实际名称和值的占位符。静态方法 `MessageFormat.format` 允许你为变量替换值。这是一个“可变参数”方法，因此你可以如下地提供参数：

```java
String msg = MessageFormat.format(
    "On {2}, a {0} destroyed {1} houses and caused {3} of damage.",
    "hurricane",
    99,
    new GregorianCalendar(1999, 0, 1).getTime(),
    10.0E8
);
```




在这个示例中，占位符`{0}`被替换为`"hurricane"`，`{1}`被替换为`99`，依此类推。

我们示例的结果是字符串：

点击此处查看代码图片

```
1/1/99 12:00 AM，一次飓风摧毁了 99 栋房屋，造成了 100,000,000 的损失。
```

这只是一个开始，但并不完美。我们不想显示时间“12:00 AM”，并且希望损失金额以货币值的形式打印。我们实现此点的方法为某些占位符提供可选的格式：

点击此处查看代码图片

```
“在{2,date,long}，一次{0}摧毁了{1}房屋，造成了{3,number,currency}的损失。”
```

此示例代码打印出：

点击此处查看代码图片

```
January 1, 1999，一次飓风摧毁了 99 栋房屋，造成了$100,000,000 的损失。
```

通常，占位符索引后可以跟随一个*类型*和一个*样式*。用逗号分隔索引、类型和样式。类型可以是以下任何一种：

- `number`
- `time`
- `date`
- `choice`

如果类型是`number`，则样式可以是：

- `integer`
- `currency`
- `percent`

或者是一个数字格式模式，如`$,##0`。（有关可能格式的更多信息，请参阅`DecimalFormat`类的文档。）

如果类型是`time`或`date`，则样式可以是：

- `short`
- `medium`
- `long`
- `full`

或者是一个日期格式模式，如`yyyy-MM-dd`。（有关可能格式的更多信息，请参阅`SimpleDateFormat`类的文档。）

---

![图像](img/00004.jpeg) 注意

静态方法`MessageFormat.format`使用当前区域来格式化值。要使用任意区域进行格式化，你需要额外努力，因为没有可以直接使用的“可变参数”方法。你需要将要格式化的值放入一个`Object[]`数组中，如下：

```java
MessageFormat mf = new MessageFormat(pattern, loc);

String msg = mf.format(new Object[] { values });
```

---

### 7.6.2 选择格式（Choice Formats）

选择格式是一序列对，每个对包含：

- 一个*下限*（lower limit）
- 一个*格式字符串*（format string）

下限和格式字符串通过`#`字符分隔，对之间通过`|`字符分隔。

例如：

`{1,choice, 0#no houses|1#one house|2#{1} houses}`

`choice`格式是为此目的设计的。当消息格式对占位符`{1}`应用选择格式且其值为`2`时，选择格式返回`"{1} houses"`。该字符串随后会被消息格式再次格式化。

点击此处查看代码图片

-∞<no houses|0<one house|2≤{1} houses

或者，使用 Unicode 转义字符：

点击此处查看代码图片

-\u221E<no houses|0<one house|2\u2264{1} houses

让我们完成自然灾害场景的编写工作。如果我们把选择字符串放在原始消息字符串内部，就会得到如下的格式指令：

点击此处查看代码图片

```java
String pattern = "On {2,date,long}, {0} destroyed {1,choice,0#no houses|1#one house|2#{1} houses}"
      + "and caused {3,number,currency} of damage.";
```

或者，用德语表示：

点击此处查看代码图片

```java
String pattern = "{0} zerstörte am {2,date,long} {1,choice,0#kein Haus|1#ein Haus|2#{1} Häuser}"
      + "und richtete einen Schaden von {3,number,currency} an.";
```

注意，德语中的单词顺序不同，但你传递给`format`方法的对象数组是相同的。格式字符串中占位符的顺序会处理词序顺序的变化。

### 7.7 文本输入与输出

如你所知，Java 编程语言本身是完全基于 Unicode 的。然而，Windows 和 Mac OS X 仍然支持旧的字符编码，例如西欧国家的 Windows-1252 或 Mac Roman，或者台湾的 Big5。因此，通过文本与用户进行通信并不像想象中的那么简单。接下来的章节将讨论你可能会遇到的复杂情况。

#### 7.7.1 文本文件

如今，使用 UTF-8 保存和加载文本文件是最佳选择。但你可能需要处理旧文件。如果你知道预期的字符编码，可以在读写文本文件时指定它：

点击此处查看代码图片

```java
PrintWriter out = new PrintWriter(filename, "Windows-1252");
```

为了猜测要使用的最佳编码，可以通过调用来获取“平台编码”：

点击此处查看代码图片

```java
Charset platformEncoding = Charset.defaultCharset();
```

#### 7.7.2 行结束符

这不是本地化问题，而是平台问题。在 Windows 上，文本文件每行尾尾使用`\r\n`，而基于 UNIX 的系统只需要一个`\n`字符。如今，大多数 Windows 程序可以只处理`\n`。一个显著的例外是记事本（Notepad）。如果你认为用户能够双击由你的应用程序生成的文本文件并在记事本中查看对你很重要，请确保该文本文件具有正确的行结束符。

使用`println`方法写入的任何行都会被正确终止。唯一的问题是如果你打印了包含`\n`字符的字符串。它们不会被自动修改为平台的行结束符。

与其在字符串中使用`\n`，你可以使用`printf`和`%n`格式说明符来产生取决于平台的行结束符。例如：

```java
out.printf("Hello%nWorld%n");
```

在 Windows 上产生：

```text
Hello\r\nWorld\r\n
```

在其他地方产生：

```text
Hello\nWorld\n
```

#### 7.7.3 控制台

如果你编写通过`System.in`/`System.out`或`System.console()`与用户通信的程序，你必须面对控制台使用的字符编码与`Charset.defaultCharset()`报告的平台编码不同的可能性。这在 Windows 上使用`cmd`命令行外壳时尤为明显。在美国版本中，命令行 shell 使用过时的`IBM437`编码，它起源于 1982 年的 IBM 个人计算机。没有官方的 API 来显示该信息。`Charset.defaultCharset()`方法将返回`Windows-1252`字符集，这与之完全不同。例如，欧元符号 € 存在于`Windows-1252`中，但在`IBM437`中不存在。当你调用：

```java
System.out.println("100 €");
```

控制台将显示：

```text
100 ?
```

你可以建议用户切换控制台的字符编码。在 Windows 中，可以通过`chcp`命令实现。例如：

```bash
chcp 1252
```

将控制台更改到`Windows-1252`代码页。

理想情况下，你的用户应该将控制台切换到 UTF-8。在 Windows 中，命令是：

```bash
chcp 65001
```

遗憾的是，这不足以让 Java 在控制台中使用 UTF-8。还有必要通过非官方的`file.encoding`系统属性来设置平台编码：

点击此处查看代码图片

```bash
java -Dfile.encoding=UTF-8 My
```

#### 7.7.4 日志文件

当`java.util.logging`消息发送到控制台时，如果使用的字符编码与`Charset.defaultCharset()`报告的平台编码不同，你必须面对这种可能性。在前面的节中我们已经讨论了如何控制它。然而，日志文件中的`FileHandler`默认使用平台编码。要将其更改为 UTF-8，需要在日志配置文件中设置：

点击此处查看代码图片

```properties
java.util.logging.FileHandler.encoding=UTF-8
```

#### 7.7.5 UTF-8 字节序标记

正如前面提到的，对于文本文件使用 UTF-8 是一个好主意。如果你的应用程序读取由其他程序创建的 UTF-8 文件，你会遇到另一个问题。在字节序标记开头添加 U+FEFF 是完全合法的。在 UTF-16 编码中，每个代码单元是双字节，字节序标记告诉读者文件使用的是“大端”还是“小端序”。UTF-8 是单字节编码，因此不需要指定字节序。但如果文件以 0xEF 0xBB 0xBF（U+FEFF 的 UTF-8 编码）开头，这强烈表明它使用的是 UTF-8。由于这个原因，Unicode 标准鼓励这种做法。任何读者都应该忽略初始字节序标记。

这里只有一个障碍。Oracle Java 实现固执地拒绝遵循 Unicode 标准，理由是兼容性问题。这意味着你，程序员，必须做平台不去做的事。当你读取文本文件并遇到 U+FEFF 时，请忽略它。

---

![图片](img/0004.jpeg) 警告

遗憾的是，JDK 实现者没有遵循这一建议。当你向`javac`编译器传递一个带有字节序标记的有效 UTF-8 源文件时，编译会失败并报错“非法字符：65279”。

#### 7.7.6 源文件的字符编码

你，程序员需要与 Java 编译器进行通信——你通过本地系统上的工具来实现这一点。例如，你可以使用中文版记事本编写 Java 源代码。生成的源文件是不可移植的，因为使用了本地字符编码（取决于你使用的中文操作系统，是 GB 或 Big5）。只有编译后的类文件是可移植的——它们会自动为标识符和字符串使用修改后的 UTF-8 编码。这意味着当程序编译和运行时，涉及到三种编码：

- 源文件：平台编码
- 类文件：修改后的 UTF-8
- 虚拟机：UTF-16

（请参见第 2 章提示。）

你可以使用`-encoding`标志指定源文件的字符编码，例如：

点击此处查看代码图片

```bash
javac -encoding UTF-8 Myfile.java
```

为了使你的源文件具有可移植性，请限制自己使用纯 ASCII 编码。也就是说，将所有非 ASCII 字符转换为等效的 Unicode 转义字符。例如，不要使用字符串`"Häuser"`，而是使用`"H\u0084user"`。JDK 包含一个名为`native2ascii`的工具，你可以用它将本地字符编码转换为纯 ASCII。该工具简单地将输入中的每个非 ASCII 字符替换为`\u`后跟 Unicode 值的四个十六进制数字。要使用`native2ascii`程序，请提供输入和输出文件名。

点击此处查看代码图像

```bash
native2ascii Myfile.java Myfile.temp
```

你可以通过`-reverse`选项反向转换：

点击此处查看代码图像

```bash
native2ascii -reverse Myfile.temp Myfile.java
```

你可以使用`-encoding`选项指定另一种编码：

点击此处查看代码图像

```bash
native2ascii -encoding UTF-8 Myfile.java Myfile.temp
```

### 7.8 资源包（Resource Bundles）

在本地化应用程序时，你可能会面临海量的消息字符串、按钮标签等，所有内容都需要翻译。为了使这项任务可行，你可能需要将消息字符串定义在外部位置，通常称为*资源*（resource）。执行翻译的人只需简单地编辑资源文件，而无需触碰程序的源代码。

在 Java 中，你可以使用属性文件来指定字符串资源，并为其他类型的资源实现类。

![Image](img/00002.jpeg) 备注

Java 技术资源与 Windows 或 Macintosh 资源不同。Macintosh 或 Windows 可执行程序在与程序代码独立的区域存储资源，如菜单、对话框、图标和消息。资源编辑器可以检查并更新这些资源，而不影响程序代码。

![Image](img/00002.jpeg) 备注

第一卷第 13 章描述了 JAR 文件资源的概念，数据文件、声音和图像可以放置在 JAR 文件中。`Class`类的`getResource`方法可以找到文件、打开它并返回指向资源的 URL。通过将文件放入 JAR 文件中，你将查找文件的工作交给了类加载器，类加载器已经知道如何定位 JAR 文件中的项目。然而，该机制没有本地化支持。

#### 7.8.1 定位资源包

在本地化应用程序时，你将产生一组*资源包*（resource bundles）。每个包都是一个属性文件或一个描述特定本地化项（如消息、标签等）的类。对于每个包，你必须为你想要支持的所有本地语言提供版本。

你需要对这些资源包使用特定的命名约定。例如，特定于德国的资源放入`bundleName_de_DE`文件中，而所有德语国家共享的资源放入`bundleName_de`中。通常情况下，使用：

`bundleName_language_country`

用于所有特定国家的资源，并使用：

`bundleName_language`

用于所有特定语言的资源。最后，作为后备，你可以将默认值放在一个没有任何后缀的文件中。

要加载资源包，请使用命令：

点击此处查看代码图像

```java
ResourceBundle currentResources = ResourceBundle.getBundle(bundleName, currentLocale);
```

`getBundle`方法尝试加载与当前本地化语言和国家匹配的包。如果没有成功，则依次丢弃国家和语言。然后对默认本地化应用相同的搜索，最后查询默认资源包文件。如果即使该尝试也失败，该方法将抛出`MissingResourceException`。

也就是说，`getBundle`方法尝试加载以下资源包：

- `bundleName_currentLocaleLanguage_currentLocaleCountry`
- `bundleName_currentLocaleLanguage`
- `bundleName_currentLocaleLanguage_defaultLocaleCountry`
- `bundleName_defaultLocaleLanguage`
- `bundleName`

一旦`getBundle`方法定位了一个资源包（例如`bundleName_de_DE`），它仍将继续查找`bundleName_de`和`bundleName`。如果这些包存在，它们将成为*资源层级结构*（resource hierarchy）中`bundleName_de_DE`包的*父包*（parents）。之后在查找资源时，如果在当前包中查找不成功，则会搜索父包。也就是说，如果在`bundleName_de_DE`中没有找到特定资源，则也会查询`bundleName_de`和`bundleName`。

这显然是一个非常有用的服务——而且通过手动编程它将非常繁琐。Java 编程语言的资源包机制会自动定位与给定本地化最匹配的项。在现有程序中添加越来越多的本地化是很容易的——你只需要创建额外的资源包即可。

![Image](img/00002.jpeg) 备注

我们简化了对资源包查找的讨论。如果一个本地化语言具有脚本或变体，查找过程将复杂得多。请参见方法`ResourceBundle.getCandidateLocales`的文档。

![Image](img/00002.jpeg) 提示

你不需要将应用程序的所有资源放在一个包中。你可以为标签准备一个包，为消息准备一个包，等等。

#### 7.8.2 属性文件

字符串本地化非常直观。你将所有字符串放入如`MyProgramStrings`的属性文件中。这是一个每行包含一个键值对的文本文件。一个典型的文件如下：

点击此处查看代码图像

```properties
computeButton=计算
colorName=black
defaultPaperSize=210×297
```

然后按照前面的节所述命名你的属性文件，例如：

点击此处查看代码图像

```text
MyProgramStrings.properties
MyProgramStrings_en.properties
MyProgramStrings_de_DE.properties
```

你可以像下面一样加载包：

点击此处查看代码图像

```java
ResourceBundle bundle = ResourceBundle.getBundle("MyProgramStrings", locale);
```

查找特定字符串，调用：

点击此处查看代码图像

```java
String computeButtonLabel = bundle.getString("computeButton");
```

![Image](img/00004.jpeg) 注意

存储属性的文件始终是 ASCII 文件。如果你需要在属性文件中放入 Unicode 字符，请使用`\uxxxx`编码。例如，为了指定`"colorName=Grün"`，请使用：

```properties
colorName=Gr\u00FCn
```




你可以使用`native2ascii`工具生成这些文件。

#### 7.8.3 包类

为了提供不是字符串的资源，定义继承`ResourceBundle`的类。使用标准命名约定命名你的类，例如：

点击此处查看代码图像

```
MyProgramResources.java

MyProgramResources_en.java

MyProgramResources_de_DE.java
```

使用用于加载属性文件的相同`getBundle`方法加载类：

点击此处查看代码图像

```
ResourceBundle bundle = ResourceBundle.getBundle("MyProgramResources", locale);
```

![Image](img/00004.jpeg) 注意

在搜索包时，当两个名称相同时，类包将优于属性文件。

每个资源包类实现了一个查找表。你需要为每个想要本地化的设置提供一个键字符串，并使用该键字符串来获取设置。例如：

点击此处查看代码图像

```
Color backgroundColor = (Color) bundle.getObject("backgroundColor");

double[] paperSize = (double[]) bundle.getObject("defaultPaperSize");
```

实现资源包类（resource bundle classes）简单的方法是扩展`ListResourceBundle`类。`ListResourceBundle`让你将所有资源放入一个对象数组中，然后它为你执行查找。遵循以下代码大纲：

点击此处查看代码

```java
public class bundleName_language_country extends ListResourceBundle
{
   private static final Object[][] contents =
    {
        { key1, value2 },
        { key2, value2 },
        . . .
    }

   public Object[][] getContents() { return contents; }
}
```

例如，

点击此处查看代码

```java
public class ProgramResources_de extends ListResourceBundle
{
   private static final Object[][] contents =
    {
        { "backgroundColor", Color.black },
        { "defaultPaperSize", new double[] { 210, 297 } }
    }

   public Object[][] getContents() { return contents; }
}

public class ProgramResources_en_US extends ListResourceBundle
{
   private static final Object[][] contents =
    {
        { "backgroundColor", Color.blue },
        { "defaultPaperSize", new double[] { 216, 279 } }
    }

   public Object[][] getContents() { return contents; }
}
```

***

![Image](img/00002.jpeg) 注意

纸张尺寸以毫米为单位。除了美国和加拿大外，地球上的每一个人都使用 ISO 216 纸张尺寸。更多信息，请参阅`www.cl.cam.ac.uk/~mgk25/iso-paper.html`。

***

或者，你的资源包类也可以扩展`ResourceBundle`类。这时，你需要实现两个方法：一个用于列出所有键（keys），另一个用于根据给定的键对应的值：

点击此处查看代码

```java
Enumeration<String> getKeys()

Object handleGetObject(String key)
```

`ResourceBundle`类的`getObject`方法会调用你提供的`handleGetObject`方法。

***

`java.util.ResourceBundle` **1.1**

- `static ResourceBundle getBundle(String baseName, Locale loc)`
- `static ResourceBundle getBundle(String baseName)`  
  加载给定名称、针对给定语言环境（locale）或默认语言环境的资源包类，以及其父类。如果资源包类位于包中，则基名必须包含全包名，例如`"intl.ProgramResources"`。资源包类必须是`public`的，以便`getBundle`方法可以访问它们。
- `Object getObject(String name)`  
  从资源包或其父类中查找对象。
- `String getString(String name)`  
  从资源包或其父类中查找对象并将其强制转换为字符串。
- `String[] getStringArray(String name)`  
  从资源包或其父类中查找对象并强制转换为字符串数组。
- `Enumeration<String> getKeys()`  
  返回一个枚举对象，用于枚举此资源包的键。它也会枚举父资源包中的键。
- `Object handleGetObject(String key)`  
  如果你定义了自己的资源查找机制，则应该重写此方法以查找与给定键相关的资源值。

***

### 7.9 完整示例

在本节中，我们将应用本章的材料来本地化一个退休计算器。该程序计算你是否为退休储蓄了足够的资金。你输入年龄、每月储蓄的金额等（参见图 7.4）。

![Image](img/00128.jpeg)

**图 7.4** 英文退休计算器

文本区域和图表显示每年退休账户的余额。如果数字在生活后期变为负数，且图中的条形出现在`x`轴下方，你需要做些什么——例如，存更多的钱、推迟退休、早点去世，或者年轻一点。

该退休计算器支持三种语言环境（英语、德语和中文）运行。以下是国际化的一些亮点：

- 标签、按钮和消息被翻译成了德语和中文。你可以在`RetireResources_de`和`RetireResources_zh`类中找到它们。英语作为备选回退——参见`RetireResources`文件。为了生成中文消息，我们首先在运行中文版 Windows 的系统中使用记事本输入了该文件，然后使用`native2ascii`工具将字符转换为 Unicode。
- 每当语言环境改变时，我们会重置标签并重新格式化文本字段的内容。
- 文本字段以本地格式处理数字、金额和百分比。
- 计算字段使用`MessageFormat`。格式字符串存储在每个语言的资源包中。
- 仅仅展示这是可行的，我们根据用户选择的语言为条形图使用不同的颜色。代码列表`7.5`到`7.8](#part0012.html_ch07list08)`显示了代码。代码列表`7.9`到`7.11](#part0012.html_ch07list11)`是本地化字符串的属性文件。图`7.5`和`7.6](#part0012.html_ch07fig06)`分别显示了德语和中文输出。为了查看中文，请确保已安装并配置了字体。否则，中文将显示为“缺失字符”图标。

![Image](img/0129.jpeg)

**图 7.5** 德语退休计算器

![Image](img/0130.jpeg)

**图 7.6** 中文退休计算器

**代码列表 7.5** `retire/Retire.java`

```java
private NumberFormat numberFmt;

private NumberFormat percentFmt;

public RetireFrame()
{
    setLayout(new GridBagLayout());

    add(languageLabel, new GBC(0, 0).setAnchor(GBC.EAST));
    add(savingsLabel, new GBC(0, 1).setAnchor(GBC.EAST));
    add(contribLabel, new GBC(2, 1).setAnchor(GBC.EAST));
    add(incomeLabel, new GBC(4, 1).setAnchor(GBC.EAST));
    add(currentAgeLabel, new GBC(0, 2).setAnchor(GBC.EAST));
    add(retireAgeLabel, new GBC(2, 2).setAnchor(GBC.EAST));
    add(deathAgeLabel, new GBC(4, 2).setAnchor(GBC.EAST));
    add(inflationPercentLabel, new GBC(0, 3).setAnchor(GBC.EAST));
    add(investPercentLabel, new GBC(2, 3).setAnchor(GBC.EAST));

    add(localeCombo, new GBC(1, 0, 3, 1));
    add(savingsField, new GBC(1, 1).setWeight(100, 0).setFill(GBC.HORIZONTAL));
    add(contribField, new GBC(3, 1).setWeight(100, 0).setFill(GBC.HORIZONTAL));
    add(incomeField, new GBC(5, 1).setWeight(100, 0).setFill(GBC.HORIZONTAL));
    add(currentAgeField, new GBC(1, 2).setWeight(100, 0).setFill(GBC.HORIZONTAL));
    add(retireAgeField, new GBC(3, 2).setWeight(100, 0).setFill(GBC.HORIZONTAL));
    add(deathAgeField, new GBC(5, 2).setWeight(100, 0).setFill(GBC.HORIZONTAL));
    add(inflationPercentField, new GBC(1, 3).setWeight(100, 0).setFill(GBC.HORIZONTAL));
    add(investPercentField, new GBC(3, 3).setWeight(100, 0).setFill(GBC.HORIZONTAL));

    add(retireCanvas, new GBC(0, 4, 4, 1).setWeight(100, 100).setFill(GBC.BOTH));
    add(new JScrollPane(retireText), new GBC(4, 4, 2, 1).setWeight(0, 100).setFill(GBC.BOTH));

    computeButton.setName("computeButton");

    computeButton.addActionListener(event ->
    {
        getInfo();
        updateData();
        updateGraph();
    });

    add(computeButton, new GBC(5, 3));

    retireText.setEditable(false);
    retireText.setFont(new Font("Monospaced", Font.PLAIN, 10));

    info.setSavings(0);
    info.setContrib(9000);
    info.setIncome(60000);
    info.setCurrentAge(35);
    info.setRetireAge(65);
    info.setDeathAge(85);
    info.setInvestPercent(0.1);
    info.setInflationPercent(0.05);

    int localeIndex = 0; // 默认使用美国区域

    for (int i = 0; i < locales.length; i++)
        // 如果选项中包含当前区域，则选择它
        if (getLocale().equals(locales[i])) localeIndex = i;

    setCurrentLocale(locales[localeIndex]);

    localeCombo.addActionListener(event ->
    {
        setCurrentLocale((Locale) localeCombo.getSelectedItem());
        validate();
    });

    pack();
}

/**
 * 设置当前区域。
 * @param locale 所需的区域设置
 */
public void setCurrentLocale(Locale locale)
{
    currentLocale = locale;
    localeCombo.setLocale(currentLocale);
    localeCombo.setSelectedItem(currentLocale);

    res = ResourceBundle.getBundle("retire.RetireResources", currentLocale);
    resStrings = ResourceBundle.getBundle("retire.RetireStrings", currentLocale);

    currencyFmt = NumberFormat.getCurrencyInstance(currentLocale);
    numberFmt = NumberFormat.getNumberInstance(currentLocale);
    percentFmt = NumberFormat.getPercentInstance(currentLocale);

    updateDisplay();
    updateInfo();
    updateData();
    updateGraph();
}

/**
 * 更新显示中所有的标签。
 */
public void updateDisplay()
{
    languageLabel.setText(resStrings.getString("language"));
    savingsLabel.setText(resStrings.getString("savings"));
    contribLabel.setText(resStrings.getString("contrib"));
    incomeLabel.setText(resStrings.getString("income"));
    currentAgeLabel.setText(resStrings.getString("currentAge"));
    retireAgeLabel.setText(resStrings.getString("retireAge"));
    deathAgeLabel.setText(resStrings.getString("deathAge"));
    inflationPercentLabel.setText(resStrings.getString("inflationPercent"));
    investPercentLabel.setText(resStrings.getString("investPercent"));
    computeButton.setText(resStrings.getString("computeButton"));
}

/**
 * 更新文本字段中的信息。
 */
public void updateInfo()
{
    savingsField.setText(currencyFmt.format(info.getSavings()));
    contribField.setText(currencyFmt.format(info.getContrib()));
    incomeField.setText(currencyFmt.format(info.getIncome()));
    currentAgeField.setText(numberFmt.format(info.getCurrentAge()));
    retireAgeField.setText(numberFmt.format(info.getRetireAge()));
    deathAgeField.setText(numberFmt.format(info.getDeathAge()));
    investPercentField.setText(percentFmt.format(info.getInvestPercent()));
}
```



```java
inflationPercentField.setText(percentFmt.format(info.getInflationPercent()));

}

/**
 * 更新文本区域中的数据。
 */
public void updateData()
{
    retireText.setText("");

    MessageFormat retireMsg = new MessageFormat("");
    retireMsg.setLocale(currentLocale);
    retireMsg.applyPattern(resStrings.getString("retire"));

    for (int i = info.getCurrentAge(); i <= info.getDeathAge(); i++)
    {
        Object[] args = { i, info.getBalance(i) };
        retireText.append(retireMsg.format(args) + "\n");
    }
}

/**
 * 更新图表。
 */
public void updateGraph()
{
    retireCanvas.setColor((Color) res.getObject("Pre"));
    retireCanvas.setColor((Color) res.getObject("Gain"));
    retireCanvas.setColor((Color) res.getObject("Loss"));
    retireCanvas.setInfo(info);
    repaint();
}

/**
 * 从文本字段读取输入内容。
 */
public void getInfo()
{
    try
    {
        info.setSavings(currencyFmt.parse(savingsField.getText()));
        info.setContrib(currencyFmt.parse(contribField.getText()));
        info.setIncome(currencyFmt.parse(incomeField.getText()));
        info.setCurrentAge(numberFmt.parse(currentAgeField.getText()));
        info.setRetireAge(numberFmt.parse(retireAgeField.getText()));
        info.setDeathAge(numberFmt.parse(deathAgeField.getText()));
        info.setInvestPercent(percentFmt.parse(investPercentField.getText()));
        info.setInflationPercent(percentFmt.parse(inflationPercentField.getText()));
    }
    catch (ParseException ex)
    {
        ex.printStackTrace();
    }
}

}

/**
 * 计算退休收入数据所需的信息。
 */
class RetireInfo
{
    private double savings;
    private double contrib;
    private double income;
    private int currentAge;
    private int retireAge;
    private int deathAge;
    private double inflationPercent;
    private double investPercent;
    private int age;
    private double balance;

  /**
   * 获取指定年份的可用余额。
   * @param year 要计算余额的年份
   * @return 该年份可用（或需要）的金额
   */
  public double getBalance(int year)
  {
      if (year < currentAge) return 0;
      else if (year == xcurrentAge)
      {
          age = year;
          balance = savings;
          return balance;
      }
      else if (year == age) return balance;

      if (year != age + 1) getBalance(year - 1);

      age = year;

      if (age < retireAge) balance += contrib;
      else balance -= income;

      balance = balance * (1 + (investPercent - inflationPercent));
      return balance;
  }

  /**
   * 获取之前的存款金额。
   * @return 存款金额
   */
  public double getSavings()
  {
      return savings;
  }

  /**
   * 设置之前的存款金额。
   * @param newValue 存款金额
   */
  public void setSavings(double newValue)
  {
      savings = newValue;
  }

  /**
   * 获取退休账户的年度投入金额。
   * @return 投入金额
   */
  public double getContrib()
  {
      return contrib;
  }

  /**
   * 设置退休账户的年度投入金额。
   * @param newValue 投入金额
   */
  public void setContrib(double newValue)
  {
      contrib = newValue;
  }

  /**
   * 获取年度收入。
   * @return 收入金额
   */
  public double getIncome()
  {
      return income;
  }

  /**
   * 设置年度收入。
   * @param newValue 收入金额
   */
  public void setIncome(double newValue)
  {
      income = newValue;
  }

  /**
   * 获取当前年龄。
   * @return 年龄
   */
  public int getCurrentAge()
  {
      return currentAge;
  }

  /**
   * 设置当前年龄。
   * @param newValue 年龄
   */
  public void setCurrentAge(int newValue)
  {
      currentAge = newValue;
  }

  /**
   * 获取期望的退休年龄。
   * @return 年龄
   */
  public int getRetireAge()
  {
      return retireAge;
  }

  /**
   * 设置期望的退休年龄。
   * @param newValue 年龄
   */
  public void setRetireAge(int newValue)
  {
      retireAge = newValue;
  }

  /**
   * 获取预期死亡年龄。
   * @return 年龄
   */
  public int getDeathAge()
  {
      return deathAge;
  }

  /**
   * 设置预期死亡年龄。
   * @param newValue 年龄
   */
  public void setDeathAge(int newValue)
  {
      deathAge = newValue;
  }

  /**
   * 获取预估的通胀率。
   * @return 百比
   */
  public double getInflationPercent()
  {
      return inflationPercent;
  }

  /**
   * 设置预估的通胀率。
   * @param newValue 百比
   */
  public void setInflationPercent(double newValue)
  {
      inflationPercent = newValue;
  }

  /**
   * 获取预估的投资收益率。
   * @return 百比
   */
  public double getInvestPercent()
  {
      return investPercent;
  }

  /**
   * 设置预估的投资收益率。
   * @param newValue 百比
   */
  public void setInvestPercent(double newValue)
  {
      investPercent = newValue;
  }
}

/**
 * 该组件绘制投资结果的图表。
 */
class RetireComponent extends JComponent
{
    private static final int PANEL_WIDTH = 400;
    private static final int PANEL_HEIGHT = 200;
    private static final Dimension PREFERRED_SIZE = new Dimension(800, 600);
    private RetireInfo info = null;
    private Color colorPre;
    private Color colorGain;
    private Color colorLoss;

    RetireComponent()
    {
        setSize(PANEL_WIDTH, PANEL_HEIGHT);
    }

    /**
     * 设置要绘制的退休信息。
     * @param newInfo 新的退休信息
     */
    public void setInfo(RetireInfo newInfo)
    {
        info = newInfo;
        repaint();
    }

    public void paintComponent(Graphics g)
    {
        Graphics2D g2 = (Graphics2D) g;

        if (info == null) return;

        double minValue = 0;
        double maxValue = 0;
        int i;

        for (i = info.getCurrentAge(); i <= info.getDeathAge(); i++)
        {
            double v = info.getBalance(i);

            if (minValue > v) minValue = v;
            if (maxValue < v) maxValue = v;
        }

        if (maxValue == minValue) return;

        int barWidth = getWidth() / (info.getDeathAge() - info.getCurrentAge() + 1);
        double scale = getHeight() / (maxValue - minValue);

        for (i = info.getCurrentAge(); i < info.getDeathAge(); i++)
        {
            int x1 = (i - info.getCurrentAge()) * barWidth + 1;
            int y1;
            double v = info.getBalance(i);
            int height;
            int yOrigin = (int) (maxValue * scale);

            if (v >= 0)
            {
                y1 = (int) ((maxValue - v) * scale);
                height = yOrigin - y1;
            }
            else
            {
                y1 = yOrigin;
                height = (int) (-v * scale);
            }

            if (i < info.getRetireAge()) g2.setPaint(colorPre);
            else if (v >= 0) g2.setPaint(colorGain);
            else g2.setPaint(colorLoss);

            Rectangle2D bar = new Rectangle2D.Double(x1, y1, barWidth - 2, height);
            g2.fill(bar);
            g2.setPaint(Color.black);
            g2.draw(bar);
        }
    }

    /**
     * 设置退休前的使用的颜色。
     * @param color 所需的颜色
     */
    public void setColorPre(Color color)
    {
        colorPre = color;
        repaint();
    }

    /**
     * 设置退休后余额为正时使用的颜色。
     * @param color 所需的颜色
     */
    public void setColorGain(Color color)
    {
        colorGain = color;
        repaint();
    }

    /**
     * 设置退休后账户余额为负时使用的颜色。
     * @param color 所需的颜色
     */
    public void setColorLoss(Color color)
    {
        colorLoss = color;
        repaint();
    }

    public Dimension getPreferredSize()
    {
        return PREFERRED_SIZE;
    }
}
```

这些是退休计算器的英文非字符串资源。

```java
/**
 * @version 1.21 2001-08-27
 * @author Cay Horstmann
 */
public class RetireResources extends java.util.ListResourceBundle
{
    private static final Object[][] contents = {
        // BEGIN LOCALIZE
        { "colorPre", Color.blue },
        { "colorGain", Color.white },
        { "colorLoss", Color.red }
        // END LOCALIZE
    };

    public Object[][] getContents()
    {
        return contents;
    }
}
```

**Listing 7.7** `retire/RetireResources_de.java`

点击此处查看代码图片



```java
package retire;

import java.awt.*;

/**
 * 这些是退休计算器的德语非字符串资源。
 * @version 1.21 2001-08-27
 * @author Cay Horstmann
 */
public class RetireResources_de extends java.util.ListResourceBundle
{
    private static final Object[][] contents = {
        // BEGIN LOCALIZE
            { "colorPre", Color.yellow }, { "colorGain", Color.black }, { "colorLoss", Color.red }
        // END LOCALIZE
    };

    public Object[][] getContents()
    {
        return contents;
    }
}
```

**Listing 7.8** `retire/RetireResources_zh.java`

点击此处查看代码图片

```java
package retire;

import java.awt.*;

/**
 * 这些是退休计算器的中文非字符串资源。
 * @version 1.21 2001-08-27
 * @author Cay Horstmann
 */
public class RetireResources_zh extends java.util.ListResourceBundle
{
    private static final Object[][] contents = {
        // BEGIN LOCALIZE
            { "colorPre", Color.red }, { "colorGain", Color.blue }, { "colorLoss", Color.yellow }
        // END LOCALIZE
    };

    public Object[][] getContents()
    {
        return contents;
    }
}
```

**Listing 7.9** `retire/RetireStrings.properties`

点击此处查看代码图片

```properties
language=Language
computeButton=Compute
savings=Prior Savings
contrib=Annual Contribution
income=Retirement Income
currentAge=Current Age
retireAge=Retirement Age
deathAge=Life Expectancy
inflationPercent=Inflation
investPercent=Investment Return
retire=Age: {0,number} Balance: {1,number,currency}
```

**Listing 7.10** `retire/RetireStrings_de.properties`

点击此处查看代码图片

```properties
language=Sprache
computeButton=Rechnen
savings=Vorherige Ersparnisse
contrib=Jährliche Einzahlung
income=Einkommen nach Ruhestand
currentAge=Jetziges Alter
retireAge=Ruhestandalter
deathAge=Lebenserwartung
inflationPercent=Inflation
investPercent=Investitionsgewinn
retire=Alter: {0,number} Guthaben: {1,number,currency}
```

**Listing 7.11** `retire/RetireStrings_zh.properties`

点击此处查看代码图片

```properties
language=语言
computeButton=计算
savings=之前的储蓄
contrib=年度贡献
income=退休收入
currentAge=当前年龄
retireAge=退休年龄
deathAge=寿命
inflationPercent=通胀
investPercent=投资回报
retire=年龄：{0,number} 余额：{1,number,currency}
```

你已经了解了如何使用 Java 语言的国际化功能。你现在可以使用资源包（resource bundles）提供多语言的翻译，并使用格式化器（formatters）和比较器（collators）来处理特定区域的文本。在下一章中，我们将深入研究脚本、编译和注解。

# 第 8 章 脚本、编译与注解处理

## 在本章中

- 8.1 Java 平台的脚本化
- 8.2 编译器 API
- 8.3 使用注解
- 8.4 注解语法
- 8.5 标准注解
- 8.6 源码级注解处理
- 8.7 字节码工程

本章介绍了处理代码的三种技术。脚本 API 允许你在像 JavaScript 或 Groovy 等脚本语言中调用代码。当你想要在应用程序内部编译 Java 代码时，可以使用编译器 API。注解处理器（Annotation processors）则对代码进行操作。

## 8.1 Java 平台的脚本化

脚本 API 允许你在像 JavaScript 或 Groovy 等脚本语言中调用代码。当你想要在应用程序内部编译 Java 代码时，可以使用编译器 API。注解处理器则对代码进行操作。

脚本语言具有许多优势：

- 快速迭代
- 在运行期间更改程序
- 允许用户自定义

另一方面，大多数脚本语言缺乏 Java 语言具备的特性，例如强类型、封装和模块化。因此，将脚本语言与 Java 结合非常有吸引力。通过在运行时解释文本，避免了传统的 edit/compile/link/run（编辑/编译/链接/运行）循环。脚本 API 允许你做到这一点。Java 平台的脚本 API 允许你运行使用 JavaScript、Groovy、Ruby 甚至是 Scheme 和 Haskell 等语言编写的脚本。例如，Renjin 项目（https://www.renjin.org）提供了 R 编程语言的 Java 实现，常用于统计编程的脚本“引擎”。

在接下来的章节中，我们将展示如何选择特定语言的引擎、如何执行脚本，以及如何使用某些引擎提供的高级功能。

### 8.1.1 获取脚本引擎

脚本引擎是一个可以执行特定语言脚本的库。当虚拟机启动时，它会发现所有用的脚本引擎。要列出这些引擎，请构造一个 `ScriptEngineManager` 并调用 `getEngineFactories()` 方法。你可以询问每个工厂支持的引擎名称、MIME 类型和文件扩展名。表 8.1 显示了典型值。

![图像](img/00131.jpeg)

**表 8.1** 脚本引擎工厂

通常你知道你需要哪个引擎，可以通过名称、MIME 类型或扩展名直接请求。例如：

点击此处查看代码图片

```java
ScriptEngine engine = manager.getEngineByName("nashorn");
```

Java SE 8 包含了 Oracle 开发的 JavaScript 解释器 Nashorn。通过在类路径上提供必要的 JAR 文件来添加更多语言。

```java
javax.script.ScriptEngineManager

- `List<ScriptEngineFactory> getEngineFactories()` 获取所有发现的引擎工厂列表。
- `ScriptEngine getEngineByName(String name)`
- `ScriptEngine getEngineByExtension(String extension)`
- `ScriptEngine getEngineByMimeType(String mimeType)`

根据给定的名称、脚本文件扩展或 MIME 类型获取脚本引擎。
```

```java
javax.script.ScriptEngineFactory

- `List<String> getNames()`
- `List<String> getExtensions()`
- `List<String> getMimeTypes()`

获取该工厂已知的名称、脚本文件扩展和 MIME 类型。
```

### 8.1.2 脚本评估与绑定

一旦获取了引擎，你可以通过简单调用来执行脚本：

```java
Object result = engine.eval(scriptString);
```

如果脚本存储在文件中，请打开一个 `Reader` 并调用：

```java
Object result = engine.eval(reader);
```

你可以在同一个引擎上调用多个脚本。如果一个脚本定义了变量、函数或类，大多数脚本引擎会保留这些定义以供后续使用。例如：

```java
engine.eval("n = 1728");

Object result = engine.eval("n + 1");
```

将返回 `1729`。

> **注意**
>
> 要确定在多线程中并发执行脚本是否安全，请调用：
>
> ```java
> Object param = factory.getParameter("THREADING");
> ```
>
> 返回的值是以下内容之一：
>
> - `null`：并发执行是不安全的。
> - `"MULTITHREADED"`：并发执行是安全的。一个线程的影响可能对另一个线程可见。
> - `"THREAD-ISOLATED"`：除了 `"MULTITHREADED"` 之外，每个线程还维护了不同的变量绑定。
> - `"STATELESS"`：除了 `"THREAD-ISOLATED"` 之外，脚本不会更改变量绑定。

你通常想向引擎添加变量绑定。绑定由名称和一个关联的 Java 对象组成。例如，考虑以下语句：

```java
engine.put("k", 1728);

Object result = engine.eval("k + 1");
```

脚本代码从“引擎作用域”中的绑定中读取 `k` 的定义。这特别重要，因为大多数脚本语言都可以访问 Java 对象，通常使用的语法比 Java 语法更简单。例如：

```java
engine.put("b", new JButton());

engine.eval("b.text = 'Ok'");
```

相反，你可以检索到由脚本语句绑定的变量：

```java
engine.eval("n = 1728");

Object result = engine.get("n");
```

除了引擎作用域外，还有一个全局作用域。你添加到 `ScriptEngineManager` 的任何绑定对所有引擎都可见。

与其向引擎或全局作用域添加绑定，不如将它们收集在类型为 `Bindings` 的对象中，并将其传递给 `eval` 方法：

```java
Bindings scope = engine.createBindings();

scope.put("b", new JButton());

engine.eval(scriptString, scope);
```

如果一组绑定不应持续到后续对 `eval` 方法的调用，则很有用。

> **注意**
>
> 你可能希望拥有引擎和全局作用域之外的作用域。例如，Web 容器可能需要请求和会话作用域。然而，你需要自为。你需要编写一个实现 `ScriptContext` 接口的类，来管理作用域集合。每个作用域由一个整数标识，数字较小的作用域应先被搜索。（标准库提供了一个 `SimpleScriptContext` 类，但它只持有全局和引擎作用域。）

### `javax.script.ScriptEngine`

- `Object eval(String script)`
- `Object eval(Reader reader)`
- `Object eval(String script, Bindings bindings)`
- `Object eval(Reader reader, Bindings bindings)`

根据给定的绑定评估由字符串或 `Reader` 提供的脚本。

- `Object get(String key)`
- `void put(String key, Object value)`

在引擎作用域中获取或放入绑定。

- `Bindings createBindings()`

创建一个适用于此引擎的空 `Bindings` 对象。

### `javax.script.ScriptEngineManager`

- `Object get(String key)`
- `void put(String key, Object value)`

在全局作用域中获取或放入绑定。

### `javax.script.Bindings`

- `Object get(String key)`
- `void put(String key, Object value)`

向此 `Bindings` 对象表示的作用域获取或放入绑定。

### 8.1.3 重定向输入和输出

你可以通过调用脚本上下文的 `setReader()` 和 `setWriter()` 方法来重定向脚本的标准输入和输出。例如：

```java
StringWriter writer = new StringWriter();

engine.getContext().setWriter(new PrintWriter(writer, true));
```

任何使用 JavaScript `print` 或 `println()` 函数写入的输出都将发送到 `writer`。

`setReader()` 和 `setWriter()` 方法仅影响脚本引擎的标准输入和输出源。例如，如果你执行 JavaScript 代码：

```javascript
println("Hello");

java.lang.System.out.println("World");
```

只有第一个输出被重定向了。

Nashorn 引擎没有标准输入源的概念。调用 `setReader()` 没有效果。

### `javax.script.ScriptEngine`

- `ScriptContext getContext()`

获取此引擎的默认脚本上下文。

### `javax.script.ScriptContext`

- `Reader getReader()`
- `void setReader(Reader reader)`
- `Writer getWriter()`
- `void setWriter(Writer writer)`
- `Writer getErrorWriter()`
- `void setErrorWriter(Writer writer)`

获取或设置普通输出或错误输出的 `Reader` 或 `Writer`。

### 8.1.4 调用脚本函数和方法

对于许多脚本引擎，你可以在不评估实际代码的情况下调用脚本语言中的函数。如果你允许用户用脚本语言实现服务，这就会很有用。

提供此功能的脚本引擎实现了 `Invocable` 接口。特别是，Nashorn 引擎实现了 `Invocable`。

要调用函数，请调用 `invokeFunction()` 方法并传入函数名，随后是函数参数：

```javascript
// 在 JavaScript 中定义 greet 函数
function greet(how, whom) { return how + ', ' + whom + '!' }
```

使用参数 `"Hello"`、`"World"` 调用函数：

```java
result = ((Invocable) engine).invokeFunction("greet", "Hello", "World");
```

如果脚本语言是面向对象的，调用 `invokeMethod()`：

```javascript
// 在 JavaScript 中定义 Greeter 类
function Greeter(how) { this.how = how }
Greeter.prototype.welcome = "
+ function(whom) { return this.how + ', ' + whom + '!' }"
```

实例化：

```java
Object yo = engine.eval("new Greeter('Yo')");
```

在实例上调用 `welcome()` 方法：

```java
result = ((Invocable) engine).invokeMethod(yo, "welcome", "World");
```

> **注意**
>
> 关于如何在 JavaScript 中定义类的更多信息，请参见 Douglas Crockford 的 *JavaScript—The Good Parts*（O’Reilly, 2008）。



![Image](img/00002.jpeg) 注意事项

如果脚本引擎没有`Invocable`接口，你仍然可以使用语言无关的方法调用方法。`ScriptEngineFactory`接口的`getMethodCallSyntax`方法产生一个传递给`eval`方法的字符串。然而，所有方法参数必须绑定到名称，而`invokeMethod`可以带任意值调用。

你可以更进一步要求脚本引擎实现 Java 接口。这样你就可以使用 Java 方法调用语法调用脚本函数和方法了。

细节取决于脚本引擎，但通常你需要为接口的每个方法提供一个函数。例如，考虑一个 Java 接口：

```java
public interface Greeter
{
  String welcome(String whom);
}
```

如果你在`Nashorn`中定义了一个同名的全局函数，你可以通过此接口调用它。

```javascript
// 在 JavaScript 中定义 welcome 函数
engine.eval("function welcome(whom) { return 'Hello, ' + whom + '!' }");

// 获取 Java 对象并调用 Java 方法
Greeter g = ((Invocable) engine).getInterface(Greeter.class);
result = g.welcome("World");
```

在面向对象的脚本语言中，你可以通过匹配的 Java 接口来访问脚本类。例如，这里展示了如何使用 Java 语法调用 JavaScript 的`SimpleGreeter`类对象：

```java
Greeter g = ((Invocable) engine).getInterface(yo, Greeter.class);
result = g.welcome("World");
```

总结来说，如果你想从 Java 调用脚本代码而不必担心脚本语言的语法，`Invocable`接口非常有用。

`javax.script.Invocable` **6**

- `Object invokeFunction(String name, Object... parameters)`
- `Object invokeMethod(Object implicitParameter, String name, Object... explicitParameters)`

使用给定的名称调用函数或方法，传递给定的参数。

- `<T> T getInterface(Class<T> iface)`

返回给定接口的实现，通过脚本引擎中的函数实现这些方法。

- `<T> T getInterface(Object implicitParameter, Class<T> iface)`

返回给定接口的实现，通过给定对象的方法实现这些方法。

#### 8.1.5 编译脚本

某些脚本引擎可以将脚本代码编译为中间形式以便于高效执行。这些引擎实现了`Compilable`接口。下面的示例显示了如何编译和评估脚本文件中的代码：

```java
Reader reader = new FileReader("myscript.js");
CompiledScript script = null;
if (engine implements Compilable)
    script = ((Compilable) engine).compile(reader);
```

一旦脚本被编译，你就可以执行它。以下代码在编译成功时执行编译后的脚本，或者如果引擎不支持编译，则执行原始脚本：

```java
if (script != null)
    script.eval();
else
    engine.eval(reader);
```

当然，只有在你需要重复执行脚本时，编译脚本才有意义。

`javax.script.Compilable` **6**

- `CompiledScript compile(String script)`
- `CompiledScript compile(Reader reader)`

根据字符串或 reader 编译给脚本。

`javax.script.CompiledScript` **6**

- `Object eval()`
- `Object eval(Bindings bindings)`

评估此脚本。

### 8.1.6 示例：脚本化 GUI 事件

为了说明脚本 API，我们将编写一个示例程序，允许用户在他们选择的脚本语言中指定事件处理器。

查看 Listing 8.1 中的程序，它为任意框架类添加了脚本功能。默认情况下，它读取 Listing 8.2 中的`ButtonFrame`类，这与第一卷中的事件处理演示类似，但有两个不同：

- 每个组件都有一个属性。

```javascript
#part0026_split_017.html_ch08pro17a)
```

```properties
#part0026_split_018.html_ch08pro18a)
```

例如，如果你选择 JavaScript，如代码所示：

```properties
yellowButton.action=java.awt.Color.YELLOW
blueButton.action=java.awt.Color.BLUE
redButton.action=java.awt.Color.RED
```

如果脚本是使用 Nashorn 完成的。

引擎包含一个将`"panel"`绑定到`JPanel`对象的绑定。当事件发生时，面板的`setBackground`方法被执行，颜色发生改变。

你可以通过执行以下命令使用带有 JavaScript 事件处理器来运行此程序：

```bash
java ScriptTest
```

如果指定了语言。

```properties
#part0026_split_020.html_ch08pro20a
```

对于 Groovy 处理器，使用：

```properties
yellowButton.action=java.awt.Color.YELLOW
blueButton.action=java.awt.Color.BLUE
redButton.action=java.awt.Color.RED
```

对于 R 处理器，使用：

```bash
java -classpath ./lib ScriptTest
```

对于 Scheme 处理器，使用：

```bash
java -classpath ./rlib ScriptTest
```

```java
        }
        else language = args[0];
        final ScriptEngine engine = manager.getEngineByName(language);
        if (engine == null)
        {
            System.err.println("No engine for " + language);
            System.exit(1);
        }
        final String frameClassName = args.length < 2 ? "buttons1.ButtonFrame" : args[1];
        JFrame frame = (JFrame) Class.forName(frameClassName).newInstance();
        InputStream in = frame.getClass().getResourceAsStream("init." + language);
        if (in != null) engine.eval(new InputStreamReader(in));
        Map<String, Component> components = new HashMap<>();
        getComponentBindings(frame, components);
        components.forEach((name, c) -> engine.put(name, c));
        final Properties events = new Properties();
        in = frame.getClass().getResourceAsStream(language + ".properties");
        events.load(in);
        for (final Object e : events.keySet())
        {
            String[] s = ((String) e).split("\\.");
            addListener(s[0], s[1], (String) events.get(e), engine, components);
        }
        frame.setTitle("ScriptTest");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }
    catch (ReflectiveOperationException | IOException | ScriptException | IntrospectionException ex)
    {
        ex.printStackTrace();
    }
/**
 * 获取容器中所有命名的组件。
 * @param c 组件
 * @param namedComponents 一个用于存储组件名称和组件的 map
 */
private static void getComponentBindings(Component c, Map<String, Component> namedComponents)
{
    String name = c.getName();
    if (name != null) { namedComponents.put(name, c); }
    if (c instanceof Container)
    {
        for (Component child : ((Container) c).getComponents())
            getComponentBindings(child, namedComponents);
    }
}
/**
 * 向对象添加监听器，该监听器方法执行一个脚本。
 * @param beanName 需要添加监听器的 bean 名称
 * @param eventName 监听类型的名称，例如 "action" 或 "change"
 * @param scriptCode 要执行的脚本代码
 * @param engine 执行代码的引擎
 * @param bindings 执行时的绑定关系
 * @throws IntrospectionException
 */
private static void addListener(String beanName, String eventName, final String scriptCode,
    final ScriptEngine engine, Map<String, Component> components)
    throws ReflectiveOperationException, IntrospectionException
{
    Object bean = components.get(beanName);
    EventSetDescriptor descriptor = getEventSetDescriptor(bean, eventName);
    if (descriptor == null) return;
    descriptor.getAddListenerMethod().invoke(bean,
        Proxy.newProxyInstance(null, new Class[] { descriptor.getListenerType() },
        (proxy, method, args) ->
        {
            engine.eval(scriptCode);
            return null;
        }));
}
private static EventSetDescriptor getEventSetDescriptor(Object bean, String eventName)
throws IntrospectionException
{
    for (EventSetDescriptor descriptor : Introspector.getBeanInfo(bean.getClass()).getEventSetDescriptors())
        if (descriptor.getName().equals(eventName)) return descriptor;
    return null;
}
```

#### 8.2 `buttons1/ButtonFrame.java`

```java
package buttons1;
import javax.swing.*;
/**
 * 带有按钮面板的框架。
 * @version 1.00 2007-11-02
 * @author Cay Horstmann
 */
public class ButtonFrame extends JFrame
{
    private static int DEFAULT_WIDTH = 300;
    private static int DEFAULT_HEIGHT = 200;
    private JPanel panel;
    private JButton yellowButton;
    private JButton blueButton;
    private JButton redButton;
    public ButtonFrame()
    {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);
        panel = new JPanel();
        panel.setName("panel");
        add(panel);
        yellowButton = new JButton("Yellow");
        yellowButton.setName("yellowButton");
        blueButton = new JButton("Blue");
        blueButton.setName("blueButton");
        redButton = new JButton("Red");
        redButton.setName("redButton");
        panel.add(yellowButton);
        panel.add(blueButton);
        panel.add(redButton);
    }
}
```

### 8.2 编译器 API

在前面的章节中，你已经了解如何与脚本语言中的代码交互。现在我们转向一个不同的场景：编译 Java 代码的 Java 程序。有很多工具需要调用 Java 编译器，例如：

- 开发环境
- Java 教学和辅导程序
- 构建和测试自动化工具
- 处理 Java 代码段的模板工具，例如 JavaServer Pages (JSP)

在过去，应用程序通过调用`tools.jar`库中未公开的类来调用 Java 编译器。如今，编译的公共 API 已是 Java 平台的一部分，不再需要使用`tools.jar`。本节将介绍编译器 API。

#### 8.2.1 简易编译

调用编译器非常简单。这里有一个示例：

```java
JavaCompiler compiler = ToolProvider.getSystemJavaCompiler();
OutputStream outStream = . . .;
OutputStream errStream = . . .;
int result = compiler.run(null, outStream, errStream, "-sourcepath", "src", "Test.java");
```



结果值为`0`表示编译成功。

编译器将输出和错误消息发送到指定的流。你可以将这些参数设置为`null`，此时使用`System.out`和`System.err`。`run`方法的第一个参数输入流。由于编译器不需要控制输入，你可以始终将其留为`null`。

#### 8.2.2 使用编译任务

你可以通过`CompilationTask`对象对编译过程进行更多的控制。具体来说，你可以：

- 控制程序代码的来源——例如，通过构建器提供代码而非文件
- 控制类文件的存放——例如，将其存储在数据库中
- 在编译期间监听错误和警告消息
- 在后台运行编译器

源文件和类文件的位置由`JavaFileManager`控制。它负责为源文件和类文件确定`JavaFileObject`实例。

要监听错误消息，请安装一个`DiagnosticListener`。当编译器报告警告或错误消息时，该监听器会接收一个`Diagnostic`对象。`DiagnosticCollector`类实现了此接口。它简单地收集所有的诊断信息，以便你在编译完成后对它们进行迭代。

`Diagnostic`对象包含有关问题位置的信息（包括文件名、行号和列号）以及一个人类可读的描述。

要获取`CompilationTask`对象，请调用`JavaCompiler`类的`getTask`方法。你需要指定：

- 一个`Writer`用于任何未以`Diagnostic`形式报告的编译器输出，或者传入`null`以使用`System.err`
- 一个`JavaFileManager`，或者传入`null`使用编译器的标准文件管理器
- 一个`DiagnosticListener`
- 选项字符串，或者在无选项时传入`null`
- 用于注解处理的类名，或者在未指定时传入`null`（我们将在本章稍后部分讨论注解处理）
- 用于源文件的`JavaFileObject`实例

你需要将最后三个参数作为`Iterable`对象提供。例如，一组选项可以这样指定：

```java
Iterable<String> options = Arrays.asList("-g", "-d", "classes");
```

或者，你也可以使用任何集合类。

如果你想让编译器从磁盘读取源文件，可以请求`StandardJavaFileManager`将文件名字符串或`File`对象转换为`JavaFileObject`实例。例如：

```java
StandardJavaFileManager fileManager = compiler.getStandardFileManager(null, null, null);

Iterable<JavaFileObject> fileObjects = fileManager.getJavaFileObjectsFromStrings(fileNames);
```

然而，如果你想让编译器从磁盘文件以外的地方读取源代码，则你需要提供自己的`JavaFileObject`子类。`Listing 8.3`显示了包含`StringBuilder`中数据的源文件对象代码。该类扩展了`SimpleJavaFileObject`便利类，并重写了`getCharContent`方法以返回字符串生成器的内容。我们将在示例程序中使用此类，在程序中动态生成 Java 类代码并对其编译。

`CompilationTask`接口扩展了`Callable<Boolean>`接口。你可以将其传递给`Executor`在另一个线程中执行，或者简单地调用`call`方法。返回值为`Boolean.FALSE`表示失败。

```java
Callable<Boolean> task = new JavaCompiler.CompilationTask(null, fileManager, diagnostics,
        options, null, fileObjects);

if (!task.call())
    System.out.println("Compilation failed");
```

如果你只是想让编译器在磁盘上生成类文件，则无需自定义`JavaFileManager`。然而，我们的示例应用程序将在字节数组中生成类文件，并使用特殊的类加载器从内存中读取它们。`Listing 8.4`定义了一个实现`JavaFileObject`接口的类。它的`openOutputStream`方法返回`ByteArrayOutputStream`，编译器将把字节码存其中。

让编译器的文件管理器使用这些文件对象似乎有些棘手。库没有提供实现`StandardJavaFileManager`接口的类。相反，你需要子类化`ForwardingJavaFileManager`类，它将所有调用委托给给定的文件管理器。在我们的情况下，只想更改`getJavaFileForOutput`方法。我们通过以下大纲来实现这一点：

```java
JavaFileManager fileManager = compiler.getStandardFileManager(diagnostics, null, null);

fileManager = new ForwardingJavaFileManager<JavaFileManager>(fileManager)
{
    public JavaFileObject getJavaFileForOutput(Location location, final String className,
            Kind kind, FileObject sibling) throws IOException
    {
        return custom object;
    }
};
```

总结，如果你只是想以通常的方式调用编译器（读写磁盘文件），请调用`JavaCompiler`的`run`方法。你可以捕获输出和错误消息，但你需要对它们进行解析。如果你想对文件处理或错误报告有更多控制，请改用`CompilationTask`接口。它的 API 相当复杂，但你可以控制编译的每一个方面。

### Listing 8.3 `compiler/StringBuilderSource.java`

```java
package compiler;

import java.net.*;

import javax.tools.*;

/**
 * 一个在 string builder 中持有代码的 Java 源文件。
 * @version 1.00 2007-11-02
 * @author Cay Horstmann
 */

public class StringBuilderSource extends SimpleJavaFileObject {
    StringBuilder code;

    /**
     * 构造一个新的 StringBuilderSource。
     * @param name 此对象表示的源文件名
     */

    public StringBuilderSource(String name) {
        super(URI.create("string:///" + name.replace('.', '/')), Kind.SOURCE);
        code = new StringBuilder();
    }

    public CharSequence getCharContent(boolean ignoreErrors) {
        return code;
    }

    public void append(String str) {
        code.append(str);
        code.append('\n');
    }
}
```

### Listing 8.4 `compiler/ByteArrayJavaClass.java`

```java
java
package compiler;

import java.io.*;

import java.net.*;

import javax.tools.*;

/**
 * 一个在字节数组中持有字节码的 Java 类。
 * @version 1.00 2007-11-02
 * @author Cay Horstmann
 */

public class ByteArrayJavaClass extends SimpleJavaFileObject {
    private ByteArrayOutputStream stream;

    /**
     * 构造一个新的 ByteArrayJavaClass。
     * @param name 此文件对象表示的类名
     */

    public ByteArrayJavaClass(String name) {
        super(URI.create("bytes:///" + name), Kind.CLASS);
        stream = new ByteArrayOutputStream();
    }

    public OutputStream openOutputStream() throws IOException {
        return stream;
    }

    public byte[] getBytes() {
        return stream.toByteArray();
    }
}
```

### Tool 6

- `int run(InputStream in, OutputStream out, OutputStream err, String... arguments)`

  使用给定的输入、输出、错误流和参数运行工具。成功返回`0`，失败返回非零值。

### JavaCompiler 6

- `StandardJavaFileManager getStandardFileManager(DiagnosticListener<? super JavaFileObject> diagnosticListener, Locale locale, Charset charset)`

  获取此编译器的标准文件管理器。你可以传入`null`使用默认的错误报告、区域和字符集。

- `JavaCompiler.CompilationTask getTask(Writer out, JavaFileManager fileManager, DiagnosticListener<? super JavaFileObject> diagnosticListener, Iterable<String> options, Iterable<String> classesForAnnotationProcessing, Iterable<? extends JavaFileObject> sourceFiles)`

  获取一个编译任务，调用时将编译给定的源文件。详情见前述节的讨论。

- `Iterable<? extends JavaFileObject> getJavaFileObjectsFromStrings(Iterable<String> fileNames)`
- `Iterable<? extends JavaFileObject> getJavaFileObjectsFromFiles(Iterable<? extends File> files)`

  将文件名序列或文件序列转换为`JavaFileObject`实例序列。

### `javax.tools.JavaCompiler.CompilationTask`

- `Boolean call()`

  执行编译任务。

### `javax.tools.DiagnosticCollector<S>`

- `DiagnosticCollector()`

  构造一个空的收集器。

- `List<Diagnostic<? extends S>> getDiagnostics()`

  获取收集到的诊断信息。

### `javax.tools.Diagnostic<S>`

- `S getSource()`

  获取与此诊断信息相关的源对象。

- `Diagnostic.Kind getKind()`

  获取此诊断信息的类型——`ERROR`、`WARNING`、`MANDATORY_WARNING`、`NOTE`或`OTHER`之一。

- `String getMessage(Locale locale)`

  获取描述此诊断信息中引发的问题的消息。传递`null`使用默认区域区域。

- `long getLineNumber()`
- `long getColumnNumber()`

  获取此诊断信息中引发的问题的位置。

### `javax.tools.SimpleJavaFileObject`

- `CharSequence getCharContent(boolean ignoreEncodingErrors)`

  对于代表源文件并产生源代码的文件对象，重写此方法。

- `OutputStream openOutputStream()`

  对于代表类文件的文件对象，重写此方法以生成一个可以向其写入字节码流。

### `javax.tools.ForwardingJavaFileManager<M extends JavaFileManager>`

- `protected ForwardingJavaFileManager(M fileManager)`

  构造一个`JavaFileManager`，它将所有调用委托给给定的文件管理器。

- `FileObject getFileForOutput(JavaFileManager.Location location, String className, JavaFileObject.Kind kind, FileObject sibling)`

  如果你想用文件对象来写入类文件，请拦截此调用；`kind`是`SOURCE`、`CLASS`、`HTML`或`OTHER`之一。

### 8.2.3 示例：动态 Java 代码生成

在用于动态网页的 JSP 技术中，你可以将 HTML 与 Java 代码段混合使用，例如：

点击此处查看代码图片

```html
<p>当前日期和时间是 <b><%= new java.util.Date() %></b>.</p>
```

`<p>当前日期和时间是 <b><%= new java.util.Date() %></b>.</p>`

JSP 引擎动态将 Java 代码编译为 servlet。在我们的示例应用程序中，我们使用一个更简单的示例，并生成动态 Swing 代码。其思想是使用 GUI 构建器在框架中布局组件，并在外部文件中指定组件的行为。列表 8.5 显示了一个非常简单的框架类示例，列表 8.6 显示了按钮动作的代码。注意框架类的构造函数调用了抽象方法`addEventHandlers`。我们的代码生成器将产生实现`addEventHandlers`方法的子类，为`action.properties`文件中的每一行添加一个动作监听器。（我们将将代码生成扩展到其他事件类型的任务留给读者作为练习。）

我们将子类置于名为`x`的包中，我们希望这个包在程序的其他地方都不被使用。生成的代码形式如下：

点击此处查看代码图片

```java
package x;

public class Frame extends SuperClassName
{
    protected void addEventHandlers()
    {
        componentName[1].addActionListener(new java.awt.event.ActionListener()
        {
            public void actionPerformed(java.awt.event.ActionEvent)
            {
                code for event handler1
            }
        });

        // 重复其他事件监听器 ...
    }
}
```

列表 8.7 程序中的`buildSource`方法构建了此代码并将其放入`StringBuilderJavaSource`对象中。该对象被传递给 Java 编译器。

我们使用带有`getJavaFileForOutput`方法的`ForwardingJavaFileManager`，它为`x`包中的每个类构造一个`ByteArrayJavaClass`对象。这些对象捕获了编译`x.Frame`类时生成的类文件。该方法在返回列表之前会将每个文件对象添加到列表中，以便我们稍后定位字节码。注意，编译`x.Frame`类会为主类生成一个类文件，并为每个监听器类生成一个类文件。

编译完成后，我们构建一个关联类名与字节码数组的 map。简单的类加载器（如列表 8.8）：

```java
Class<?> cl = loader.loadClass("x.Frame");
Frame frame = (JFrame) cl.newInstance();
frame.setVisible(true);
```

当你点击按钮时，背景颜色会以通常的方式变化。要看到这些动作是动态编译的，请更改`action.properties`中的其中一行，例如：

点击此处查看代码图片

```java
yellowButton.setBackground(java.awt.Color.YELLOW);
yellowButton.setEnabled(false);
```

再次运行程序。现在，点击黄色按钮后它将被禁用了。再查看目录。你找不到`x`包中类的任何源文件或类文件。此示例演示了如何使用内存源文件和类文件进行动态编译。

#### 列表 8.5 `buttons2/ButtonFrame.java`

点击此处查看代码图片



```java
package buttons2;

import javax.swing.*;

/**
 * 一个带有按钮面板的框架。
 * @version 1.00 2007-1-02
 * @author Cay Horstmann
 */
public abstract class ButtonFrame extends JFrame
{
   public static final int DEFAULT_WIDTH = 300;
   public static final int DEFAULT_HEIGHT = 200;

   protected JPanel panel;
   protected JButton yellowButton;
   protected JButton blueButton;
   protected JButton redButton;

   protected abstract void addEventHandlers();

   public ButtonFrame()
   {
      setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

      panel = new JPanel();
      add(panel);

      yellowButton = new JButton("Yellow");
      blueButton = new JButton("Blue");
      redButton = new JButton("Red");

      panel.add(yellowButton);
      panel.add(blueButton);
      panel.add(redButton);

      addEventHandlers();
   }
}
```

#### 列表 8.6 `buttons2/action.properties`

点击此处查看代码图片

```properties
yellowButton=panel.setBackground(java.awt.Color.YELLOW);
blueButton=panel.setBackground(java.awt.Color.BLUE);
```

#### 列表 8.7 `compiler/CompilerTest.java`

点击此处查看代码图片

```java
package compiler;

import java.awt.*;
import java.io.*;
import java.util.*;
import java.util.List;
import javax.swing.*;
import java.tools.*;
import javax.tools.JavaFileObject.*;

/**
 * @version 1.01 2016-05-10
 * @author Cay Horstmann
 */
public class CompilerTest
{
   public static void main(final String[] args) throws IOException, ClassNotFoundException
   {
      JavaCompiler compiler = ToolProvider.getSystemJavaCompiler();

      final List<ByteArrayJavaClass> classFileObjects = new ArrayList<>();

      DiagnosticCollector<JavaFileObject> diagnostics = new DiagnosticCollector<>();
```

```java
JavaFileManager fileManager = compiler.getStandardFileManager(diagnostics, null, null);

fileManager = new ForwardingJavaFileManager<JavaFileManager>(fileManager)
{
    public JavaFileObject getJavaFileForOutput(Location location, final String className,
            Kind kind, FileObject sibling) throws IOException
    {
        if (className.startsWith("x."))
        {
            ByteArrayJavaClass fileObject = new ByteArrayJavaClass(className);
            classFileObjects.add(fileObject);
            return fileObject;
        }
        else return super.getJavaFileForOutput(location, className, kind, sibling);
    }
};

String frameClassName = args.length == 0 ? "buttons2.ButtonFrame" : args[0];
JavaFileObject source = buildSource(frameClassName);
JavaCompiler.CompilationTask task = compiler.getTask(null, fileManager,
        null, Arrays.asList(source));
Boolean result = task.call();

for (Diagnostic<? extends JavaFileObject> d : diagnostics.getDiagnostics())
    System.out.println(d.getKind() + ": " + d.getMessage(null));
fileManager.close();
if (!result)
{
    System.out.println("Compilation failed.");
    System.exit(1);
}

EventQueue.invokeLater(() ->
{
    try
    {
        Map<String, byte[]> byteCodeMap = new HashMap<>();
        for (ByteArrayJavaClass cl : classFileObjects)
            byteCodeMap.put(cl.getName().substring(1), cl.getBytes());
        ClassLoader loader = new MapClassLoader(byteCodeMap);
        JFrame frame = (JFrame) loader.loadClass("x.Frame").newInstance();
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setTitle("Test");
        frame.setVisible(true);
    }
    catch (Exception ex)
    {
        ex.printStackTrace();
    }
});

/**
 * 构建实现 addHandlers 的子类的源码。
 * @return 一个包含字符串源码的文件对象
 */
static JavaFileObject buildSource(String superclassName)
throws IOException, ClassNotFoundException
{
    StringBuilderSource source = new StringBuilderSource("x.Frame");
    source.append("package x;\n");
    source.append("public class Frame extends " + superclassName + " {");
    source.append("protected void addHandlers() {");
    Properties props = new Properties();
    props.load(Class.forName(superclassName).getResourceAsStream("action.properties"));
    for (Map.Entry<Object, Object> e : props.entrySet())
    {
        String beanName = (String) e.getKey();
        String eventCode = (String) e.getValue();
        source.append(beanName + ".addActionListener(event -> {");
        source.append(eventCode);
        source.append("});");
    }
    source.append("} }");
    return source;
}
```

#### 列表 8.8 `MapClassLoader.java`

点击此处查看代码图片

```java
package compiler;

import java.util.*;

/**
 * 一个从 map 中加载类的类加载器，该 map 的键是类名，值是
 * 字节码数组。
 * @version 1.00 2007-11-02
 * @author Cay Horstmann
 */
public class MapClassLoader extends ClassLoader
{
    private Map<String, byte[]> classes;

    public MapClassLoader(Map<String, byte[]> classes)
    {
        this.classes = classes;
    }

    protected Class<?> findClass(String name) throws ClassNotFoundException
    {
        byte[] classBytes = classes.get(name);
        if (classBytes == null) throw new ClassNotFoundException(name);
        Class<?> cl = defineClass(name, classBytes, 0, classBytes.length);
    }
}
```

### 8.3 使用注解

注解是插入到代码中的标记，以便某些工具对其进行处理。它们不会改变程序的编译方式。要从注解中受益，你需要工具。以下是注解的一些用途：

- 自动生成辅助文件，例如部署描述符
- 自动生成用于测试、日志、事务语义的代码

#### 8.3.1 注解引言

我们将从基本概念开始讨论注解，并在具体的示例中使用它们：随后我们将详细讨论语法规则，并以两个注解处理的示例结束本章。这是一个简单的注解示例：

```java
public class MyClass
{
    // ...
    @Test public void checkReadions()
}
```

`@Test` 注解标记了 `checkReadions` 方法。在 Java 中，注解类似于修饰符，放置在被注解的项目之前，且没有分号。（修饰符是如 `public` 或 `static` 等关键字）。每个注解的名称前都有 `@` 符号，类似于 Javadoc 注释。

然而，Javadoc 注释出现在 `/** ... */` 分隔符内部，而注解是代码的一部分。

`@Test` 注解本身什么都不做。它需要工具才能发挥作用。例如，JUnit 4 测试工具在测试类时会调用所有标记为 `@Test` 的方法。另一个工具可能会从类文件中移除所有测试方法，以便它们在测试完成后不会随程序发布。

注解可以定义为包含元素，例如：

```java
@Test(timeout="10000")
```

这些元素可以被读取注解的工具进行处理。

每个注解必须由注解接口定义。接口的方法对应于注解的元素。例如，JUnit 的 `Test` 注解由以下接口定义：

```java
@Target(ElementType.METHOD)
@Retention(RetentionPolicy.RUNTIME)
public @interface Test
{
    long timeout() default 0L;
    . . .
}
```

`@interface` 声明创建了一个真正的 Java 接口。处理注解的工具会接收实现该注解接口的对象。工具会调用 `timeout` 方法来获取特定 `Test` 注解的 `timeout` 元素。

`Target` 和 `Retention` 注解是元注解（meta-annotations）。它们作用在 `Test` 注解上，将其标记为只能应用于方法的注解，并且在类文件加载到虚拟机时被保留。我们将在后文的第 8.5.3 节的“元注解，”部分中（位于第 472 页）详细讨论这些内容。

你现在已经了解了程序元数据和注解的基本概念。在下一节中，我们将通过一个注解处理的具体示例进行演示。

#### 8.3.2 示例：为事件处理器添加注解

用户界面编程中较为枯燥的任务之一是将监听器接线到事件源上。许多监听器的形式如下：

点击此处查看代码图像

```java
myButton.addActionListener(() -> doSomething());
```

在这一节中，我们将设计一种注解来反转这种接线方式。该注解定义在代码列表 8.11 中，使用方式如下：

点击此处查看代码图像

```java
@ActionListenerFor(source="myButton") void doSomething() { . . . }
```

程序员不再需要手动调用 `addActionListener`。相反，每个方法都被标记了注解。代码清单 8.10 展示了来自第一卷第 11 章的、用这些注解重新实现的 `ButtonFrame` 类。

我们还需要定义一个注解接口。代码在代码列表 8.11 中。

当然，注解本身并不会做任何事情。它们存在于源文件中。编译器将它们放入类文件中，虚拟机加载它们。我们现在需要一种机制来分析它们并安装监听器。这就是 `ActionListenerInstaller` 类的工作。`ButtonFrame` 构造函数调用了：

```java
ActionListenerInstaller.processAnnotations(this);
```

静态方法 `processAnnotations` 枚举接收对象的所有方法。对于每个方法，它获取 `ActionListenerFor` 注解并进行处理。

```java
Class<?> cl = obj.getClass();
for (Method m : cl.getDeclaredMethods())
{
    ActionListenerFor a = m.getAnnotation(ActionListenerFor.class);
    if (a != null) . . .
}
```

在这里，我们使用了在 `AnnotatedElement` 接口中定义的 `getAnnotation` 方法。`Method`、`Field`、`Class` 和 `Package` 类都实现了该接口。源名称存储在注解中。我们通过调用 `source` 方法获取它，并查找匹配的字段。

```java
String fieldName = a.source();
Field f = cl.getDeclaredField(fieldName);
```

这显示了我们注解的局限性。源元素必须是字段名。它不能是局部变量。

代码其余部分相当技术化。对于每个带注解的方法，我们构造一个实现 `ActionListener` 接口的代理对象，其 `actionPerformed` 方法会调用被注解的方法。（有关代理的更多信息，请参见第一卷第 6 章）。细节并不重要。关键在于注解的功能是由 `processAnnotations` 方法建立的。图 8.1 展示了在本示例中是如何处理注解的。

![Image](img/0132.jpeg)

**图 8.1** 运行时注解

在本示例中，注解是在运行时处理的。也可以在源码级别处理：源代码生成器产生监听器的代码。或者，可以在字节码级别处理：字节码编辑器向构造函数注入 `addActionListener` 调用。这听起来很复杂，但有很多库可以让这项任务变得简单。你可以在第 8.7 节“字节码工程，”（第 481 页）中看到示例。

我们的示例并不是为用户界面程序员设计的正式工具。一个添加监听器的实用方法可能比注解更方便（事实上，`java.beans.EventHandler` 类尝试这样做）。你可以通过提供添加事件处理程序的方法该类变得真正有用）。

然而，这个示例展示了程序注解和分析注解的机制。看到具体示例后，你现在准备好了（我们希望）后续描述注解语法的章节。

**代码列表 8.9** `runtimeAnnotations/ActionListenerInstaller.java`

点击此处查看代码图像




```java
package runtimeAnnotations;

import java.awt.event.*;
import java.lang.reflect.*;

/**
 * @version 1.00 2004-08-17
 * @author Cay Horstmann
 */
public class ActionListenerInstaller
{
    /**
     * 处理对象中所有的 `ActionListenerFor` 注解。
     * @param obj 可能带有 `ActionListenerFor` 注解的对象
     */
    public static void processAnnotations(Object obj)
    {
        try
        {
            Class<?> cl = obj.getClass();
            for (Method m : cl.getDeclaredMethods())
            {
                ActionListenerFor a = m.getAnnotation(ActionListenerFor.class);
                if (a != null)
                {
                    Field f = cl.getDeclaredField(a.source());
                    f.setAccessible(true);
                    addListener(f.get(obj), obj, m);
                }
            }
        }
        catch (ReflectiveOperationException e)
        {
            e.printStackTrace();
        }
    }

    /**
     * 添加一个调用指定方法的监听器。
     * @param source 添加动作监听器的事件源
     * @param param 监听器调用的方法的隐式参数
     * @param m 监听器调用的方法
     */
    public static void addListener(Object source, final Object param, final Method m)
        throws ReflectiveOperationException
    {
        InvocationHandler handler = new InvocationHandler()
        {
            public Object invoke(Object proxy, Method mm, Object[] args) throws Throwable
            {
                return m.invoke(param);
            }
        };

        Object listener = Proxy.newProxyInstance(
            null,
            new Class[] { java.awt.event.ActionListener.class },
            handler
        );
        Method adder = source.getClass().getMethod("addActionListener", ActionListener.class);
        adder.invoke(source, listener);
    }
}
```

```java
public class ButtonFrame extends JFrame
{
    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 200;

    private JPanel panel;
    private JButton yellowButton;
    private JButton blueButton;
    private JButton redButton;

    public ButtonFrame()
    {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

        panel = new JPanel();
        add(panel);

        yellowButton = new JButton("Yellow");
        blueButton = new JButton("Blue");
        redButton = new JButton("Red");

        panel.add(yellowButton);
        panel.add(blueButton);
        panel.add(redButton);

        ActionListenerInstaller.processAnnotations(this);
    }

    @ActionListenerFor(source = "yellowButton")
    public void yellowBackground()
    {
        panel.setBackground(Color.YELLOW);
    }

    @ActionListenerFor(source = "blueButton")
    public void blueBackground()
    {
        panel.setBackground(Color.BLUE);
    }

    @ActionListenerFor(source = "redButton")
    public void redBackground()
    {
        panel.setBackground(Color.RED);
    }
}
```

**Listing 8.11** `runtimeAnnotations/ActionListenerFor.java`

点击此处查看代码图像

```java
package runtimeAnnotations;

import java.lang.annotation.*;

/**
 * @version 1.00 2004-08-17
 * @author Cay Horstmann
 */

@Target(ElementType.METHOD)
@Retention(RetentionPolicy.RUNTIME)
public @interface ActionListenerFor
{
    String source();
}
```

## `java.lang.reflect.AnnotatedElement` 5.0

- `boolean isAnnotationPresent(Class<? extends Annotation> annotationType)` 如果此项目项具有给定类型的注解，则返回 `true`。

- `<T extends Annotation> T getAnnotation(Class<T> annotationType)` 获取给定类型的注解，如果此项目项没有此类注解，则返回 `null`。

- `<T extends Annotation> T[] getAnnotationsByType(Class<T> annotationType)` 8 获取可重复注解类型的所有注解（参见第 8.5.3 节（第 472 页的元注解））。

- `Annotation[] getAnnotations()` 获取此项目项存在的所有注解，包括继承的注解。如果没有注解存在，则返回一个长度为 0 的数组。

- `Annotation[] getDeclaredAnnotations()` 获取此项目项声明的所有注解，不包括继承的注解。如果没有注解存在，则返回一个长度为 0 的数组。

### 8.4 注解语法

在接下来的章节中，我们将介绍关于注解语法你需要需要的所有知识。

#### 8.4.1 注解接口

注解由注解接口定义：点击此处查看代码图像：

```java
modifiers @interface AnnotationName
{
    elementDeclaration;
    elementDeclaration;
}
```

每个元素声明的格式为：

`type elementName();`

或：

`type elementName() default value;`

例如，以下注解具有两个元素，`assignedTo` 和 `severity`：

```java
public @interface BugReport
{
    String assignedTo() default "[none]";
    int severity();
}
```

所有注解接口都隐式地扩展 `java.lang.annotation.Annotation` 接口。该接口是一个普通接口，而不是注解接口。请参见本节末处的 API 注释。该接口提供的方法。你不能扩展注解接口。注解接口的方法没有参数，也没有 `throws` 子句。它们不能是 `default` 或 `static` 方法，并且不能有类型参数。

注解元素的类型是以下类型之一：

- 原始类型（`int`、`short`、`long`、`byte`、`char`、`double`、`float` 或 `boolean`）。
- `String`。
- `Class`（带有可选的类型参数，如 `Class<? extends MyClass>`）。
- `enum` 类型。
- 注解类型。
- 前述类型的数组（数组的数组不是合法的元素）。

这里是有效元素声明的示例：

```java
public @interface BugReport
{
    enum Status { UNCONFIRMED, CONFIRMED, FIXED, NOTABUG };
    boolean showStopper() default false;
    String assignedTo() default "[none]";
    Class<?> testCase() default Void.class;
    Status status() default Status.UNCONFIRMED;
    Reference ref() default @Reference(); // 一个注解类型
    String[] reportedBy();
}
```

## `java.lang.annotation.Annotation` 5.0

- `Class<? extends Annotation> annotationType()` 返回表示此注解对象的注解接口的 `Class` 对象。注意，在注解对象上调用 `getClass` 将返回实际类，而不是接口。
- `boolean equals(Object other)` 如果 `other` 是实现相同注解接口的对象且此对象的所有元素与 `other` 相等，则返回 `true`。
- `int hashCode()` 返回一个与 `equals` 方法兼容的哈希码，源自注解名称和元素值。
- `String toString()` 返回包含注解名称和元素值的字符串表示；例如，`@BugReport(assignedTo=[none], severity=0)`。

#### 8.4.2 注解

每个注解的格式如下：

`@AnnotationName(elementName[1]=value1, elementName[2]=value2, ...)`

例如：

`@BugReport(assignedTo="Harry", severity=10)`

元素的顺序并不重要。注解 `@BugReport(severity=10, assignedTo="Harry")` 与前一个相同。

如果没有指定元素值，则使用声明的默认值。例如，考虑注解：

`@BugReport(severity=10)`

`assignedTo` 元素的值是字符串 `"[none]"`。

![Image](img/00004.jpeg)

**注意**：默认值没有存储在注解中；它们是动态计算的。例如，如果你将 `assignedTo` 元素的默认值改为 `"[]"` 并重新编译 `BugReport` 接口，注解 `@BugReport(severity=10)` 将使用新的默认值，即使是在更改之前编译的类文件中。

两种快捷方式可以简化注解。

如果没有指定元素（是因为注解没有元素，或者是因为所有元素都使用了默认值），则不需要使用括号。例如，`@BugReport` 等于 `@BugReport(assignedTo="[none]", severity=0)`。这种注解被称为标记注解。

另一种快捷方式是单值注解。如果一个元素具有特殊名称 `value` 且没有指定其他元素，你可以省略元素名称和 `=` 符号。例如，如果我们之前节的 `ActionListenerFor` 注解接口定义为：

```java
public @interface ActionListenerFor
{
    String value();
}
```

那么注解可以写为：

`@ActionListenerFor("yellowButton")`

而不是：

`@ActionListenerFor(value="yellowButton")`

一个项目可以有多个注解：

```java
@Test
@BugReport(showStopper=true, reportedBy="Joe")
public void checkRandomInsertions()
```

如果注解的作者将其声明为可重复的（repeatable），则你可以多次使用同一种注解：

```java
@BugReport(showStopper=true, reportedBy="Joe")
@BugReport(reportedBy={"Harry", "Carl"})
public void checkRandomInsertions()
```

![Image](img/00002.jpeg)

**注意**

由于注解是由编译器评估的，所有元素值都必须是编译时常量。例如：

```java
@BugReport(showStopper=true, assignedTo="Harry", testCase=MyTestCase.class,
      status=BugReport.Status.CONFIRMED, . . .)
```

![Image](img/00004.jpeg)

**警告**

注解元素永远不能设置为 `null`。即使是 `default` 为 `null` 也是不允许的。这在实践中可能相当不便。你需要寻找其他的默认值，例如 `""` 或 `Void.class`。

如果元素值是一个数组，请将它的值括在花括号中：

```java
@BugReport(. . ., reportedBy={"Harry", "Carl"})
```

如果该元素只有一个值，你可以省略花括号：

```java
@BugReport(. . ., reportedBy="Joe") // OK，等同于 {"Joe"}
```

由于注解元素可以是另一个注解，因此你可以构建任意复杂的注解。例如：

```java
@BugReport(ref=@Reference(id="3352627"), . . .)
```

![Image](img/00002.jpeg)

**注意**

在注解中引入循环依赖是一个错误。例如，`BugReport` 有一个类型为 `Reference` 的注解元素，因此 `Reference` 不能有一个类型为 `BugReport` 的元素。

#### 8.4.3 声明的注解

注解出现在很多地方。它们分为两类：*声明*（declarations）和*类型使用*（type uses）。声明注解可以出现在以下声明处：

- 包（Packages）。
- 类（Classes，包括 `enum`）。
- 接口（Interfaces，包括注解接口）。
- 方法（Methods）。
- 构造函数（Constructors）。
- 实例字段（Instance fields，包括 `enum` 常量）。
- 局部变量（Local variables）。
- 参数变量（Parameter variables）。
- 类型参数（Type parameters）。

对于类和接口，将注解放在 `class` 或 `interface` 关键字之前：

```java
@Entity public class User { . . . }
```

对于变量，将它们放在类型之前：

```java
@SuppressWarnings("unchecked") List<User> users = . . .; public User getUser(@Param("id") String userId)
```




泛型类或方法中的类型参数可以这样被注解：

点击此处查看代码图像

```java
public class Cache<@Immutable V> { . . . }
```

包在`package-info.java`文件中进行注解，该文件仅包含由注解引导包语句。

点击此处查看代码图像

```java
/**
   包级 Javadoca
 */
@GPL(version="3")
package com.horstmann.corejava;
import org.gnu.GPL;
```

***

![Image](img/00002.jpeg) 注意

局部变量的注解只能在源码级别被处理。类文件不描述局部变量。因此，所有的局部变量注解在类被编译时都会丢弃。同样，包的注解不会在源码级别之外被保留。

***

#### 8.4.4 类型使用的注解

声明注解提供了关于被声明项的一些信息。例如，在如下声明中：

点击此处查看代码图像

```java
public User getUser(@NonNull String userId)
```

它断言`userId`是非空的。

***

![Image](img/00002.jpeg) 注意

`@NonNull`注解是 Checker Framework (`http://types.cs.edu/checker-framework/`) 的一部分。通过该框架，你可以在代码中断言某个参数非空。假设我们有一个类型为`String`并且想表达它是非空的。这就是类型使用注解的用处。类型使用注解可以出现在以下位置：

- 泛型参数：`List<@NonNull String>`
- 数组：`@NonNull String[]`或`String[] @NonNull`
- 超类和实现的接口：`class ... @NonNull Message`
- 构造函数调用：`new @NonNull String(..)`
- 强制转换和`instanceof`：`(@NonNull String)(text instanceof @NonNull String)`
- 异常规范：`public String read() throws @NonNull IOException`
- 通配符和类型边界：`List<?@NonNull ? extends Message>`
- 方法引用：`@NonNull Message::getText`

有些类型位置不能被注解：

点击此处查看代码图像

```java
@NonNull String.class // 错误，类
import java.lang.@NonNull String; // 错误，导入
```

你可以将注解放在`private`或`static`等修饰符之前。习惯上（但不是必须）将类型使用注解放在修饰符之后，将声明注解放在修饰符之前。例如：

```java
private @NonNull text; // 注解类型使用
@Id private String userId; // 注解变量
```

***

![Image](img/00002.jpeg) 注意

注解作者需要指定注解可以出现在哪里。如果一个注解同时允许变量和类型使用，并且它在变量声明中使用，那么变量和类型使用都会被注解。例如，考虑：

（此处原文示例逻辑略乱，已按语意翻译）

***

#### 8.4.5 注解`this`

假设你想注解那些不会被方法修饰的参数。

点击此处查看代码图像

```java
public class Point
{
  public boolean equals(@ReadOnly Object other) { . . . }
}
```

那么一个处理该注解的工具在看到`p.equals(q)`时就会推出`q`没有被改变。

但`p`呢？

当方法被调用时，`this`变量绑定到`p`。但`this`永远不会被声明，因此你不能注解它。

实际上，你可以声明它，使用一种很少使用的语法变体，以便添加注解：

点击此处查看代码图像

```java
public class Point
{
  public boolean equals(@ReadOnly Point this, @ReadOnly Object other) { . . . }
}
```

第一个参数被称为`receiver parameter`（接收器参数）。它必须命名为`this`。它的类型是正在构造的类。

![Image](img/00002.jpeg) 注意

你只能为方法提供接收器参数，而不能为构造函数提供。从概念上讲，构造函数中的`this`引用在构造完成之前并不是给定类型的对象。相反，放置在构造函数上的注解描述了所构造对象的某个属性。

另一个隐藏参数被传递给内部类的构造函数，即指向外部包围类对象的引用。你也可以将该参数显式化：

点击此处查看代码图像

```java
public class Sequence
{
   private int from;
   private int to;
   class Iterator implements java.util.Iterator<Integer>
   {
      private int current;
      public Iterator(@ReadOnly Sequence.this)
      {
          this.current = Sequence.this.from;
      }
      . . .
    }
   . . .
}
```

该参数的命名必须与你引用它时一致，即`EnclosingClass.this`，其类型是该包围类。

### 8.5 标准注解

Java SE 在`java.lang`、`java.lang.annotation`和`javax.annotation`包中定义了许多注解接口。其中四个是元注解（meta-annotations），用于描述注解接口的行为。其他是普通注解，你可以用它们来标记源代码中的项。表 8.2 显示了这些注解。我们将在接下来的两个部分详细讨论它们。

![Image](img/00133.jpeg)

**表 8.2** 标准注解

#### 8.5.1 用于编译的注解

`@Deprecated`注解可以附加到任何不再建议使用的项上。当你使用已弃项时，编译器会警告。该注解的作用与`@deprecated` Javadoc 标签相同。

`@SuppressWarnings`注解告诉编译器抑制特定类型的警告，例如：

点击此处查看代码图片

```java
@SuppressWarnings("unchecked")
```

`@Override`注解仅适用于方法。编译器会检查带有此注解的方法是否真的重写了父类的方法。例如，如果你声明了：

点击此处查看代码图片

```java
public MyClass
{
   @Override public boolean equals(MyClass other);
   . . .
}
```

那么编译器将报告错误。毕竟，`equals`方法并没有重写`Object`类的`equals`方法，因为该方法的参数类型是`Object`，而不是`MyClass`。

`@Generated`注解旨在供代码生成器工具使用。任何生成的源代码都可以被注解，以将其与程序员提供的代码区分开来。例如，代码编辑器可以隐藏生成的代码，或者代码生成器可以移除旧版本的生成代码。每个注解必须包含一个代码生成器的唯一标识符。日期字符串（ISO 8601 格式）和注释字符串是可选的。例如：

点击此处查看代码图片

```java
@Generated("com.horstmann.beanproperty", "2008-01-04T12:08:56.235-0700");
```

#### 8.5.2 用于资源管理的注解

`@PostConstruct`和`@PreDestroy`注解用于控制对象生命周期的环境，例如 Web 容器和应用服务器。标记了这些注解的方法应该在对象构造后立即调用，或在被移除之前立即调用。

`@Resource`注解用于资源注入。例如，考虑访问数据库的 Web 应用。当然，数据库访问信息不应该硬编码在 Web 应用中。相反，Web 容器具有用户界面用于设置连接参数和数据源的 JNDI 名称。在 Web 应用中，你可以这样引用数据源：

点击此处查看代码图片

```java
@Resource(name="jdbc/mydb")
private DataSource source;
```

当包含此字段的对象被构造时，容器会“注入”指向数据源的引用。

#### 8.5.3 元注解

`@Target`元注解应用于注解，限制了注解可以适用的项。例如：

点击此处查看代码图片

```java
@Target({ElementType.TYPE, ElementType.METHOD})
public @interface BugReport
```

表 8.3 显示了所有可能的值。你可以指定任意数量的元素类型，括在大括号内。

![Image](img/0134.jpeg)

**表 8.3** `@Target`的元素类型

没有`@Target`限制的注解可以应用于任何项。编译器会检查你是否仅将注解应用于允许的项。例如，如果你将`@BugReport`应用于字段，将产生编译错误。

`@Retention`元注解指定了注解保留多久。默认值是`RetentionPolicy.CLASS`。表 8.4。

![Image](img/0135.jpeg)

**表 8.4** `@Retention`的保留策略

在列表 8.11 第 461 页，`ActionListenerFor`注解被声明为`RetentionPolicy.RUNTIME`，因为我们使用反射来处理注解。

`@Documented`元注解为像 Javadoc 这样的文档工具提供提示。被文档化的注解应该像`protected`或`static`等修饰符一样被对待。其他注解的使用会被包含在文档中。例如，假设我们将`@ActionListenerFor`声明为文档化注解：

点击此处查看代码图片

```java
@Documented
@Target(ElementType.METHOD)
@Retention(RetentionPolicy.RUNTIME)
public @interface ActionListenerFor
```

现在每个被注解的方法都包含该注解，如图 8.2 所示。

![Image](img/0136.jpeg)

**图 8.2** 文档化的注解

如果注解是瞬时的（如`@BugReport`），可能不应该记录其用法。

***

![Image](img/00002.jpeg) 注意

将注解应用于自身是合法的。例如，`@Documented`注解本身也被标记为`@Documented`。因此，注解的 Javadoc 文档会显示它们是否被文档化。

***

`@Inherited`元注解仅适用于类的注解。当类具有可继承注解时，其所有子类自动具有相同的注解。这使得创建作为标记接口的注解变得简单，例如`Serializable`。

事实上，一个`Serializable`注解比一个没有方法的`Serializable`标记接口更合适。一个类是可序列化的是因为运行时支持读取和写入字段，而不是因为任何面向对象的设计原则。注解描述这一事实比接口继承更准确。当然，`Serializable`接口是在 JDK 1.1 创建的，远早于注解出现。

假设你定义了一个继承注解`@Persistent`，表示类对象可以保存到数据库中。那么持久化类的子类会自动被标记为持久化。

点击此处查看代码图片

```java
@Inherited @interface Persistent { }

@Persistent class Employee { . . . }

class Manager extends Employee { . . . } // 也是 @Persistent
```

当持久化机制搜索要存储在数据库的对象时，它会检测到`Employee`和`Manager`对象。

从 Java SE 8 开始，在某个项上多次应用相同的注解类型是合法的。为了向后兼容，可重复注解的实现者需要提供一个`容器注解`，用数组的形式持有重复的注解。

以下是定义`@TestCase`注解及其容器的方式：

点击此处查看代码图片

```java
@Repeatable(TestCases.class)

@interface TestCase
{
   String params();
   String expected();
}

@interface TestCases
{
   TestCase[] value();
}
```

每当用户提供两个或多个`@TestCase`注解时，它们会被自动封装进`@TestCases`注解中。

***

![Image](img/00004.jpeg) 注意

在处理可重复注解时必须小心。如果你调用`getAnnotation`来查找重复注解，而该注解实际上是重复的，那么你将得到`null`。这是因为重复的注解被封装到了容器注解中。

在这种情况下，你应该调用`getAnnotationsByType`。该调用会“穿透”容器并返回一个重复注解的数组。如果只有一个注解，你将得到一个长度为 1 的数组。通过这种方法，你就不需要担心容器注解了。

***

### 8.6 源码级注解处理

在前面的节中，你已经了解了如何分析运行程序中的注解。注解的另一个用途是对源文件进行自动处理，以生成更多的源代码、配置文件、脚本或任何人们想要生成的内容。

#### 8.6.1 注解处理器

注解处理已集成到 Java 编译器中。在编译期间，你可以通过运行以下命令来`invoke annotation processors`：

点击此处查看代码图片

```bash
javac -processor ProcessorClassName[1],ProcessorClassName[2],. . . sourceFiles
```

编译器会定位源文件的注解。每个注解处理器按顺序执行，并获得它感兴趣的注解。如果某个注解处理器创建了新的源文件，该过程将重复进行。一旦某一轮处理不再产生更多源文件，所有源文件将完成编译。

***

![Image](img/00002.jpeg) 注意

注解处理器只能生成新的源文件。它不能修改现有的源文件。

注解处理器实现了`Processor`接口，通常通过扩展`AbstractProcessor`类来实现。你需要指定你的处理器支持哪些注解。在我们的案例：

点击此处查看代码图片

```java
@SupportedAnnotationTypes("com.horstmann.annotations.ToString")

@SupportedSourceVersion(SourceVersion.RELEASE_8)

public class ToStringAnnotationProcessor extends AbstractProcessor
{
   public boolean process(Set<? extends TypeElement> annotations,
          RoundEnvironment currentRound)
   {
      ...
   }
}
```

处理器可以声称特定的注解类型、通配符（如`"com.horstmann.*"`，表示`com.horstmann`包或任何子包中的所有注解），甚至是`"*"`（表示所有注解）。

`process`方法每轮次会被调用一次，参数是该轮次在任何文件中找到的所有注解集合，以及一个包含当前处理轮信息的`RoundEnvironment`引用。

#### 8.6.2 语言模型 API

使用`language model` API 来分析源码级注解。与反射 API（它提供类和方法的虚拟机表示）不同，语言模型 API 允许你根据 Java 语言的规则分析 Java 程序。

编译器产生一个树，其节点是实现了`javax.lang.model.element.Element`接口及其子接口的类实例：`TypeElement`、`VariableElement`、`ExecutableElement`等。这些是`Class`、`Field`/`Parameter`、`Method`/Constructor`反射类的编译时对应物。

我不想详细介绍该 API，但这里是你在处理注解时需要了解的重点：

- 通过调用以下方法，`RoundEnvironment`可以提供被特定注解标记的所有元素集合：

  点击此处查看代码图像

  ```java
  Set<? extends Element> getElementsAnnotatedWith(Class<? extends Annotation> a)
  ```

- `AnnotateElement`接口的源码等价物是`AnnotatedConstruct`。使用以下方法：

  点击此处查看代码图像

  ```java
  A getAnnotation(Class<A> annotationType)

  A[] getAnnotationsByType(Class<A> annotationType)
  ```

  来获取给定注解类的单个注解或重复注解。

- `TypeElement`代表一个类或接口。`getEnclosedElements`方法产生其字段和方法的列表。

- 在`Element`上调用`getSimpleName`或在`TypeElement`上调用`getQualifiedName`会产生一个`Name`对象。

#### 8.6.3 使用注解生成代码

作为一个示例，我们将使用注解来减少实现`toString`的繁琐工作。我们不能将方法放入原始类中——注解处理器只能产生新类，而不能修改现有类。因此，我们将所有方法添加到工具类`ToStrings`中：

点击此处查看代码图像



```java
class ToStrings
{
   public static String toString(Point obj)
   {
      Generated code
   }
   public static String toString(Rectangle obj)
   {
      Generated code
   }
   ...
   public static String toString(Object obj)
   {
      return Objects.toString(obj);
   }
}
```

我们不想使用反射，所以给访问器方法加上注解：

点击此处查看代码图片

```java
@ToString
public class Rectangle
{
   ...
   @ToString(includeName=false) public Point getTopLeft() { return topLeft; }
   @ToString public int getWidth() { return width; }
   @ToString public int getHeight() { return height; }
}
```

注解处理器随后生成以下源代码：

点击此处查看代码图片

```java
public static String toString(Rectangle obj)
{
   StringBuilder result = new StringBuilder();
   result.append("Rectangle");
   result.append("[");
   result.append(toString(obj.getTopLeft()));
   result.append(",");
   result.append("width=");
   result.append(toString(obj.getWidth()));
   result.append(",");
   result.append("height=");
   result.append(toString(obj.getHeight()));
   result.append("]");
   return result.toString();
}
```

模版代码用灰色表示。以下是为带有`TypeElement`的类产生`toString`方法的方法：

点击此处查看代码图片

```java
private void writeToString(PrintWriter out, TypeElement te)
{
   String className = te.getQualifiedName().toString();
   Print method header and declaration of string builder
   ToString ann = te.getAnnotation(ToString.class);
   if (ann.includeName())
      Print code to add class name
   for (Element c : te.getEnclosedElements())
   {
      ann = c.getAnnotation(ToString.class);
      if (ann != null)
      {
         if (ann.includeName())
            Print code to add field name
         Print code to append toString(obj.methodName ())
      }
   }
   Print code to return string
}
```

这里是注解处理器`process`方法的概要。它为工具类创建一个源文件，并为每个被注解的类写入类头部和一个方法。

点击此处查看代码图片

```java
public boolean process(Set<? extends TypeElement> annotations, RoundEnvironment currentRound)
{
   if (annotations.size() == 0) return true;
   try
   {
      JavaFileObject sourceFile = processingEnv.getFiler().createSourceFile(
              "com.horstmann.annotations.ToStrings");
      try (PrintWriter out = new PrintWriter(sourceFile.openWriter()))
      {
         // 输出 package 和 class 代码
         for (Element e : currentRound.getElementsAnnotatedWith(ToString.class))
         {
             if (e instanceof TypeElement)
             {
                  TypeElement te = (TypeElement) e;
                  writeToStringMethod(out, te);
             }
          }
         // 输出 toString(Object) 代码
      }
      catch (IOException ex)
      {
         processingEnv.getMessager().printMessage(
              Kind.ERROR, ex.getMessage());
      }
   }
   return true;
}
```

关于冗长的细节，请参考书的配套代码。

注意，`process`方法在随后的轮次中会被调用，但此时注解列表为空。它会立即返回，这样就不会重复创建源文件。

首先编译注解处理器，然后按照如下方式编译并运行测试程序：

点击此处查看代码图像

`javac sourceAnnotations/ToStringAnnotationProcessor.java`

`javac -processor sourceAnnotations.ToStringAnnotationProcessor rect/*.java`

`java rect.SourceLevelDemo`

![图像](img/00003.jpeg)

提示：要查看处理轮次，请带有`-XRounds`标志运行`javac`命令：

点击此处查看代码图像

```
Round 1: 输入文件：{rect.Point, rect.Rectangle, rect.SourceLevelDemo} 注解：sourceAnnotations.ToString 上一轮次：false

Round 2: 输入文件：{sourceAnnotations.ToStrings} 注解：[] 上一轮次：false

Round 3: 输入文件：{} 注解：[] 上一轮次：true
```

这个示例演示了工具如何收集源注解以生成其他文件。生成的文件不必是源文件。注解处理器可以选择生成 XML 描述符、属性文件、shell 脚本、HTML 文档等。

![图像](img/00002.jpeg)

注意：有些人建议使用注解来消除那些琐碎的工作。如果能自动生成简单的 getter 和 setter，那不是很好吗？例如，注解点击此处查看代码图像`@Property private String title;`

可以产生方法点击此处查看代码图像`public String getTitle() { return title; }`

`public void setTitle(String title) { this.title = title; }`

然而，这些方法需要添加到同一个类中。这需要编辑源文件，而不仅仅是生成另一个文件，这超出了注解处理器的能力。虽然可以为此构建另一个工具，但这样的工具将超出注解的任务范围。注解的意图是关于代码项的描述，而不是添加或更改代码的指令。

### 8.7 字节码工程

你已经看到注解如何在运行时或源码级别上被处理。有第三种可能性：在字节码级别进行处理。除非注解在源码级别被移除，否则它们存在于类文件中。类文件格式是有文档的（参见`http://docs.oracle.com/javase/specs/jvms/se8/`）。该格式相当复杂，在没有特殊库的情况下处理类文件将具有挑战性。其中一个库是 ASM 库，可以在`http://asm.ow2.org`获取。

#### 8.7.1 修改类文件

在本节，我们使用 ASM 为带有注解的方法添加日志消息。如果一个方法被标记为点击此处查看代码图像`@LogEntry(logger=loggerName)`，那么我们会在方法的开头添加以下语句的字节码：点击此处查看代码图像`Logger.getLogger(loggerName).entering(className, methodName);`

例如，如果你将`Item`类的`hashCode`方法标记为点击此处查看代码图像`@LogEntry(logger="global") public int hashCode()`，那么每当调用该方法时，都会打印出类似所示的消息：点击此处查看代码图像`May 17, 2016 10:57:59 AM Item hashCode

FINER: ENTRY`

为了实现这一点，我们执行以下操作：

1. 加载类文件中的字节码。
2. 定位所有方法。
3. 对于每个方法，检查它是否具有`LogEntry`注解。
4. 如果有，在方法的开头添加以下指令的字节码：点击此处查看代码图像

```text
ldc loggerName
invokestatic java/util/Logger.getLogger:(Ljava/lang/String;)L/util/Logger;
ldc className
ldc methodName
invokevirtual java/util/Logger.entering:(Ljava/lang/String;Ljava/lang/String;)V
```

插入这些字节码听起来很复杂，但 ASM 让它变得非常简单。我们不会详细描述分析和插入字节码的过程。关键点在于程序列表 8.12 编辑了类文件并在注解方法的开头插入了调用。

例如，这里是如何向列表 8.13 中的`Item.java`添加日志指令，其中`asm`是你安装 ASM 库的目录：点击此处查看代码图像

`javac sourceAnnotations/ToStringAnnotationProcessor.java`

`javac -processor sourceAnnotations.ToStringAnnotationProcessor rect/*.java`

`java rect.SourceLevelDemo`

尝试在修改`Item`类后运行`javap -c Item`。你可以看到`hashCode`、`equals`和`compareTo`方法开头插入的指令。

列表 8.14 中的`SetTest`程序将`Item`对象插入哈希集合。当你使用修改后的类文件运行时它，你将看到日志消息。点击此处查看代码图像

```text
May 17, 2016 10:57:59 AM Item hashCode
FINER: ENTRY
May 17, 2016 10:57:59 AM Item hashCode
FINER: ENTRY
May 17, 2016 10:57:59 AM Item hashCode
FINER: ENTRY
May 17, 2016 10:57:59 AM Item equals
FINER: ENTRY
```

这个示例展示了字节码工程的力量。注解用于向程序添加指令，而字节码编辑工具获取指令并修改虚拟机指令。

**列表 8.12** `bytecodeAnnotations/EntryLogger.java`

点击此处查看代码图片

```java
package bytecodeAnnotations;
```



```java
import java.io.*;
import java.nio.file.*;
import org.objectweb.asm.*;
import org.objectweb.asm.commons.*;

/**
 * 为类中带有 LogEntry 注解的所有方法添加“进入”日志。
 * @version 1.20 2016-05-10
 * @author Cay Horstmann
 */
public class EntryLogger extends ClassVisitor
{
    private String className;

    /**
     * 构造 EntryLogger，向给定类的中被注解的方法中插入日志。
     * @param cg 该类
     */
    public EntryLogger(ClassWriter writer, String className)
    {
        super(Opcodes.ASM5, writer);
        this.className = className;
    }

    @Override
    public MethodVisitor visitMethod(int access, String methodName, String desc,
            String signature, String[] exceptions)
    {
        MethodVisitor mv = cv.visitMethod(access,  methodName,  desc,  signature,  exceptions);
        return new AdviceAdapter(Opcodes.ASM5, mv, access, methodName, desc)
        {
            private String loggerName;

            public AnnotationVisitor visitAnnotation(String desc, boolean visible)
            {
                return new AnnotationVisitor(Opcodes.ASM5)
                {
                    public void visit(String name, Object value)
                    {
                        if (desc.equals("LbytecodeAnnotations/LogEntry;") && name.equals("logger"))
                            loggerName = value.toString();
                    }
                };
            }

            public void onMethodEnter()
            {
                if (loggerName != null)
                {
                    visitLdcIn(loggerName);
                    visitMethodInsn(INVOKESTATIC, "java/util/logging/Logger", "getLogger",
                        "(L/lang/String;)L/util/logging/Logger;", false);
                    visitLdcIn(className);
                    visitLdcIn(methodName);
                    visitMethodInsn(INVOKEVIRTUAL, "java/util/logging/Logger", "entering",
                        "(L/lang/String;L/lang/String;)V", false);
                    loggerName = null;
                }
            }
        };
    }

    /**
     * 给给定类添加入口代码。
     * @param args 要修补的类文件名
     */
    public static void main(String[] args) throws IOException
    {
        if (args.length == 0)
        {
            System.out.println("USAGE: java bytecodeAnnotations.EntryLogger classfile");
            System.exit(1);
        }
        Path path = Paths.get(args[0]);
        ClassReader reader = new ClassReader(Files.newInputStream(path));
        ClassWriter writer = new ClassWriter(
            ClassWriter.COMPUTE_MAXS | ClassWriter.COMPUTE_FRAMES);
        EntryLogger entryLogger = new EntryLogger(writer,
            path.toString().replace(".class", "").replaceAll("[/\\\]", "."));
        reader.accept(entryLogger, ClassReader.EXPAND_FRAMES);
        Files.write(Paths.get(args[0]), writer.toByteArray());
    }
}
```

**列表 8.13** `set/Item.java`

点击此处查看代码图片

```java
package set;

import java.util.*;
import bytecodeAnnotations.*;

/**
 * 带有部件编号的项目。
 * @version 1.01 2012-01-26
 * @author Cay Horstmann
 */
public class Item
{
    private String description;
    private int partNumber;

    /**
     * 构造一个项目。
     * @param aDescription 项目的描述
     * @param aPartNumber 项目的编号
     */
    public Item(String aDescription, int aPartNumber)
    {
        description = aDescription;
        partNumber = aPartNumber;
    }

    /**
     * 获取此项的描述。
     * @return 描述
     */
    public String getDescription()
    {
        return description;
    }

    public String toString()
    {
        return "[description=" + description + ", partNumber=" + partNumber + "]";
    }

    @LogEntry(logger = "com.horstmann")
    public boolean equals(Object otherObject)
    {
        if (this == otherObject) return true;
        if (otherObject == null) return false;
        if (getClass() != otherObject.getClass()) return false;
        Item other = (Item) otherObject;
        return Objects.equals(description, other.description) && partNumber == other.partNumber;
    }

    @LogEntry(logger = "com.horstmann")
    public int hashCode()
    {
        return Objects.hash(description, partNumber);
    }
}
```

**列表 8.14** `set/SetTest.java`

点击此处查看代码图片

```java
package set;

import java.util.*;
import java.util.logging.*;

/**
 * @version 1.02 2012-01-26
 * @author Cay Horstmann
 */
public class SetTest
{
    public static void main(String[] args)
    {
        Logger.getLogger("com.horstmann").setLevel(Level.FINE);
        Handler handler = new ConsoleHandler();
        Logger.getLogger("com.horstmann").addHandler(handler);
        Set<Item> parts = new HashSet<>();
        parts.add(new Item("Toaster"));
        parts.add(new Item("Microwave"));
        System.out.println(parts);
    }
}
```

### 8.7.2 在加载时修改字节码

在前面的小节中，你看到一个可以编辑类文件的工具。然而，在构建过程中添加另一个工具可能很繁琐。一个更具吸引力的替代方案是将字节码工程推迟到*加载时*，即当类加载器加载类时进行。

`instrumentation API` 有一个用于安装字节码转换器（transformer）的钩子。该转换器必须在程序的 `main` 方法被调用之前安装。你可以通过定义一个*代理（agent）*来满足这一要求，代理是一个被加载用以某种方式监控程序的库。代理代码可以在 `premain` 方法中执行初始化。

构建一个代理所需的步骤如下：

1. 实现一个包含该方法的类。

   点击此处查看代码图片

   `public static void premain(String arg, Instrumentation instr)`

   该方法在代理加载时被调用。代理可以获取一个命令行参数，该参数通过 `arg` 参数传递。`instr` 参数可以用于安装各种钩子。

2. 创建一个名为 `EntryLoggingAgent.mf` 的清单文件，其中设置 `Premain-Class` 属性，例如：

   点击此处查看代码图片

   `Premain-Class: bytecodeAnnotations.EntryLogger`

3. 将代理代码和清单文件打包成一个 JAR 文件：

   点击此处查看代码图片

   `javac -classpath .:asm/lib/* bytecodeAnnotations/EntryLoggingAgent.java`

   `jar cvfm EntryLoggingAgent.jar bytecodeAnnotations/EntryLoggingAgent.mf \`

   `bytecodeAnnotations/Entry*.class`

要带代理启动 Java 程序，使用以下命令行选项：

点击此处查看代码图片

`java -javaagent:AgentJARFile=agentArgument . . .`

例如，要入口日志代理运行 `SetTest` 程序，调用：

点击此处查看代码图片

`javac set/SetTest.java`

```bash
java -javaagent:EntryLoggingAgent.jar=set.Item -classpath .:asm/lib/* set.SetTest
```

`Item` 参数是代理应该修改的类名。

代码列表 8.15 显示了代理代码。该代理安装了一个类文件转换器（transformer）。转换器首先检查类名是否与代理参数匹配。如果是，它将使用前一节中的 `EntryLogger` 类来修改字节码。然而，修改后的字节码并没有保存到文件中。相反，转换器将它们返回，以便加载到虚拟机中（参见图 8.3）。换句话说，这种技术实现了对字节码的“执行即时”修改。

![Image](img/00137.jpeg)

**图 8.3** 在加载时修改类

**代码列表 8.15** `bytecodeAnnotations/EntryLoggingAgent.java`

点击此处查看代码图像

```java
package bytecodeAnnotations;

import java.lang.instrument.*;

import org.objectweb.asm.*;

/**
 * @version 1.10 2016-05-10
 * @author Cay Horstmann
 */
public class EntryLoggingAgent
{
    public static void premain(final String arg, Instrumentation instr)
    {
        instr.addTransformer((loader, className, cl, pd, data) ->
            {
              if (!className.equals(arg)) return null;
              ClassReader reader = new ClassReader(data);
              ClassWriter writer = new ClassWriter(
              ClassWriter.COMPUTE_MAXS | ClassWriter.COMPUTE_FRAMES);
              EntryLogger el = new EntryLogger(writer, className);
              reader.accept(el, ClassReader.EXPAND_FRAMES);
              return writer.toByteArray();
        });
    }
}
```

在本章中，你已经学习了如何：

- 向 Java 程序中添加注解
- 设计自己的注解接口
- 实现利用注解的工具

你已经看到了处理代码的三种技术：脚本化、编译 Java 程序以及处理注解。前两种相当直观。另一方面，构建注解工具无疑是复杂的，而且并不是大多数开发者需要处理的任务。本章为你理解你将遇到的注解工具的内部工作机制提供了背景，可能激发了你对开发自己的工具的兴趣。

在下一章中，我们将转向一个完全不同的主题：安全。安全一直是 Java 平台的核心特性之一。随着我们生活和进行计算的世界变得越来越危险，对于许多开发者来说，深入理解 Java 安全性将变得日益重要。

## 第 9 章 安全

### 本章内容

- 9.1 类加载器
- 9.2 安全管理器与权限控制
- 9.3 用户身份验证
- 9.4 数字签名
- 9.5 加密

当 Java 技术首次出现时，人们兴奋的焦点并不是一种设计精良的编程语言，而是通过互联网安全地执行 applet 的可能性。显然，只有当接收者能够确定代码不会对他们的机器造成破坏时，提供可执行的 applet 具有实际意义。因此，安全过去和现在都是 Java 技术设计者和用户关注的焦点。这意味着与其他语言和系统不同（在那些系统中，安全通常是事后考虑或作为对入侵的反应而实现的），安全机制是 Java 技术不可或缺的一部分。

三种机制有助于确保安全：

- 语言设计特性（数组的边界检查、无未经检查的类型转换、无指针算术等）。
- 访问控制机制，控制代码可以执行的操作（文件访问、网络访问等）。
- 代码签名，代码作者可以使用标准的加密算法对 Java 代码进行身份验证。然后，代码的用户可以确切判断是谁创建了该代码，以及代码在签名后是否被修改过。

我们将首先讨论`类加载器`，它们在类文件加载到虚拟机时会检查其完整性。我们将演示该机制如何检测到对类文件的篡改。

为了实现最大的安全性，类加载的默认机制和自定义类加载器都需要与`security manager`类配合，由该类控制代码可以执行的操作。

### 9.1 类加载器

Java 编译器将源指令转换为虚拟机的代码。虚拟机代码存储在以`.class`为扩展名的类文件中。每个类文件都包含一个类或接口的定义和实现代码。

#### 9.1.1 类加载过程

虚拟机只加载执行程序时需要的那些类文件。例如，假设执行从`MyProgram.class`开始。以下是虚拟机执行的步骤：



1. 虚拟机有一套加载类文件的机制——例如，通过从磁盘读取文件或从 Web 请求这些文件；它使用这种机制加载`MyProgram`的内容。

2. 如果`MyProgram`类具有另一个类的字段或父类，则这些类的类文件也会被加载。（加载一个给定类所依赖的所有类的过程被称为“解析”。）

3. 虚拟机随后执行`MyProgram`中的`main`方法（由于是静态的，因此不需要创建类的实例）。

4. 如果`main`方法或`main`调用的方法需要额外的类，接下来将加载这些类。

然而，类加载机制并非只使用一个加载器。每个 Java 程序至少有三个加载器：

- 启动类加载器（bootstrap class loader）
- 扩展加载器（extension class loader）
- 系统加载器（system class loader），有时也称为应用程序加载器

启动类加载器加载系统类（通常来自`rt.jar`文件）。它是虚拟机不可或缺的一部分，并且通常用 C 语言实现。没有与启动类加载器对应的`ClassLoader`对象。例如：

```java
String.class.getClassLoader()
```

扩展加载器从`/lib/ext`目录加载标准扩展。你可以将 JAR 文件放入该目录，扩展加载器就能找到其中的类，即使没有设置任何类路径。（某些人建议使用这种机制来避免“类路径地狱”，但请看下面的警告。）

系统加载器加载应用程序类。它在类路径上的目录和 JAR/ZIP 文件中查找类，类路径通过环境变量`CLASPATH`或`-classpath`命令行选项设置。

在 Oracle Java 实现中，扩展加载器和系统加载器是用 Java 实现的。它们都是`URLClassLoader`类的实例。

![Image](img/00004.jpeg)

> **警告**
>
> 如果你将 JAR 文件放到`jre/lib/ext`目录，并且其中的某个类需要加载一个既不是系统类也不是扩展类的类，你可能会遇到麻烦。扩展类加载器`并不使用类路径`。在将扩展目录作为管理类文件各种困恼的方法之前，请务必记住这一点。

![Image](img/00002.jpeg)

> **提示**
>
> 除了已经提到的所有地方外，类还可以从`jre/lib/endorsed`目录加载。这种机制仅用于用新版本替换某些标准 Java 库（例如支持 XML 和 CORBA 的库）。详细信息请参阅`http://docs.oracle.com/javase/8/docs/technotes/guides/standards`。

### 9.1.2 类加载器的层次结构

类加载器之间存在`父/子`关系。除了引导加载器（bootstrap class loader）之外，每个类加载器都有一个父加载器。类加载器应该给父机会加载任何给定的类，只有在父加载失败时才自己加载。例如，当系统类加载器被要求加载系统类（例如`java.util.ArrayList`）时，它首先询问扩展类加载器。该加载器首先询问引导类加载器。引导加载器在`rt.jar`中找到并加载该类，因此其他两个类加载器都不会再继续搜索。

某些程序具有插件架构，代码的某些部分被封装为可选插件。如果插件被封装为 JAR 文件，你可以直接使用`URLClassLoader`的实例来加载插件类。

点击此处查看代码图像

```java
URL url = new URL("file:///path/to/plugin.jar");
URLClassLoader pluginLoader = new URLClassLoader(new URL[] { url });
Class<?> cl = pluginLoader.loadClass("mypackage.MyClass");
```

由于`URLClassLoader`构造函数中没有指定父类，因此`pluginLoader`的父类是系统类加载器。图 9.1 显示了该层次结构。

![Image](img/00138.jpeg)

**图 9.1** 类加载器层次结构

大多数时候，你不需要担心类加载器的层次结构。通常，类的加载是因为它们被其他类需要，而这个过程对你来说是透明的。然而，偶尔你需要干预并指定一个类加载器。考虑这个用例：

- 你的应用程序代码包含一个调用`Class.forName(classNameString)`的辅助方法。
- 该方法是从插件类中被调用的。
- `classNameString`指定了一个包含在插件 JAR 中的类。

插件的作者有理由预期该类应该被加载。然而，辅助方法是由系统类加载器加载的，而`Class.forName`使用的该加载器。插件 JAR 中的类是不可见的。这种现象被称为`类加载器反转`（classloader inversion）。

为了解决这个问题，辅助方法需要使用正确的类加载器。它可以接收类加载器作为参数。或者，它可以要求将正确的类加载器设置为当前线程的`上下文类加载器`（context class loader）。这种策略被许多框架使用（例如我们在第 3 章和第 5 章中讨论过的 JAXP 和 JNDI 框架）。

每个线程都有一个类加载器的引用，称为上下文类加载器。主线程的上下文类加载器是系统类加载器。当创建一个新线程时，它的上下文类加载器设置为创建线程的类加载器。因此，如果你什么都不做，所有线程的上下文加载器都将被设置为系统类加载器。

然而，你可以通过调用设置任何类加载器：

点击此处查看代码图像

```java
Thread t = Thread.currentThread();
t.setContextClassLoader(loader);
```

辅助方法随后可以获取上下文类加载器：

点击此处查看代码图像

```java
Thread t = Thread.currentThread();
ClassLoader loader = t.getContextClassLoader();
Class cl = loader.loadClass(className);
```

当上下文类加载器设置为插件类加载器时，问题仍然存在。应用程序设计者必须做出此决定。通常，在调用用不同类加载器加载的插件类方法时，设置上下文类加载器是一个好主意。或者，辅助方法的调用者可以设置类加载器。

![Image](img/00003.jpeg)

> **提示**
>
> 如果你写了一个按名称加载类的方法，那么为调用者提供传递显式类加载器和使用上下文类加载器的选择是好的。不要简单地使用方法所在类的加载器。

### 9.1.3 使用类加载器作为命名空间

每个 Java 程序员都知道包名用于消除命名冲突。标准库中有两个名为`Date`的类，但它们的真实名显然是`java.util.Date`和`java.sql.Date`。简单名只是为了方便程序员，并且需要包含`import`语句。在运行的程序中，所有类名都包含它们的包名。

然而，可能会让你惊讶的是，你可以在同一个虚拟机中拥有两个具有相同类名和包名的类。类是由其全名和类加载器决定的。这种技术对于从多个来源加载代码有用。例如，浏览器为每个网页使用独立的加载器实例。这允许虚拟机区分不同网页的类，无论它们叫什么。图 9.2 展示了一个示例。假设网页包含两个由不同广告商提供的插件，每个插件都有一个名为`Banner`的类。由于每个插件由不同的加载器加载，这些类是完全不同的且互不冲突。

![Image](img/00139.jpeg)

**图 9.2** 两个类加载器加载相同的类

![Image](img/00002.jpeg)

> **提示**
>
> 这种技术还有其他用途，例如 servlet 和 JavaBean 的“热部署”。更多信息请参阅`http://zerotaround.com/labs/rjc301`。

### 9.1.4 编写自己的类加载器

你可以为了特殊目的编写自己的类加载器。这可以在字节虚拟机之前执行自定义之前。例如，你的类加载器可以拒绝加载未标记为“已付费”的类。

要编写自己的类加载器，只需扩展`ClassLoader`类并重写方法`findClass(String className)`。

`ClassLoader`超类的`loadClass`方法处理了向父类的委托，并且仅在类尚未加载且父加载器无法加载该类时才调用`findClass`。

你对方法的实现必须执行以下操作：

1. 从本地文件系统或其他源加载类的字节码。
2. 调用`ClassLoader`超类的`defineClass`方法将字节码呈现给虚拟机。

在列表 9.1 的程序中，我们实现了一个加载加密类文件的类加载器。程序询问用户要加载的第一个类的名称（即包含`main`方法的类）以及解密密钥。然后它使用特殊的类加载器加载指定的类并调用`main`方法。该类加载器解密指定的类以及其引用的所有非系统类。最后，程序调用加载的类的`main`方法（参见图 9.3）。

![Image](img/00140.jpeg)

**图 9.3** `ClassLoaderTest`程序

为了简单起见，我们忽略了密码学领域 2000 年来的进步，并使用古老的凯撒密码来加密类文件。

![Image](img/00002.jpeg)

> **注意事项**
>
> 大卫·卡恩（David Kahn）的经典著作《密码破解者》（Macmillan, 1967, p. 84）引用苏埃提乌（Suetonius）作为凯撒密码的历史来源。凯撒将罗马字母表中的 24 个字母向后移动 3 个字母，这在当时让他的对手们无所措。
>
> 在本章首次撰写时，美国政府限制强加密方法的出口。因此，我们在示例中使用凯撒方法，因为它在出口方面显然是合法的。

我们版本的凯撒密码其密钥是一个 1 到 255 之间的数字。要解密，只需将该密钥加到每个字节并对 256 取模即可。代码列表 9.2 中的`Caesar.java`程序执行了加密操作。

为了不干扰常规类加载器，我们对加密的类文件使用了不同的扩展名`.caesar`。

要解密，类加载器只需从每个字节中减去密钥。在本书的配套代码中，你会找到使用密钥值 3（这是传统选择）加密的类文件。要运行加密后的程序，你需要使用我们在`ClassLoaderTest`程序中定义的自定义类加载器。

加密类文件有许多实际用途（当然，前提是你使用了某种比凯撒密码更强的方法）。没有解密密钥，类文件就一无用处。它们既无法被标准虚拟机执行，也无法被轻易反编译。

这意味着你可以使用自定义类加载器来验证类的用户身份，或者在允许程序运行之前确保其已支付费用。当然，加密只是自定义类加载器的应用之一。你还可以使用其他类型的类加载器来解决其他问题——例如，将类文件存储在数据库中。

**列表 9.1** `classLoader/ClassLoaderTest.java`

点击此处查看代码图像

```java
package classLoader;

import java.io.*;
import java.lang.reflect.*;
import java.nio.file.*;
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

/**
 * 此程序演示了一个解密类文件的自定义类加载器。
 * @version 1.24 2016-05-10
 * @author Cay Horstmann
 */
public class ClassLoaderTest
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() ->
            {
                JFrame frame = new ClassLoaderFrame();
                frame.setTitle("ClassLoaderTest");
                frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
                frame.setVisible(true);
            });
    }
}

/**
 * 此框架包含两个文本字段，分别用于加载的类名和解密密钥。
 */
class ClassLoaderFrame extends JFrame
{
    private JTextField keyField = new JTextField("3", 4);
    private JTextField nameField = new JTextField("Calculator", 30);
    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 20;

    public ClassLoaderFrame()
    {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);
        setLayout(new GridBagLayout());
        add(new JLabel("Class"), new GBC(0, 0).Anchor(GBC.EAST));
        add(nameField, new GBC(1, 0).Weight(100, 0).Anchor(GBC.WEST));
        add(new JLabel("Key"), new GBC(0, 1).Anchor(GBC.EAST));
        add(keyField, new GBC(1, 1).Weight(100, 0).Anchor(GBC.WEST));
        JButton loadButton = new JButton("Load");
        add(loadButton, new GBC(0, 2, 1));
        loadButton.addActionListener(event -> runClass(nameField.getText(), keyField.getText()));
        pack();
    }

    /**
     * 运行给定类的 main 方法。
     * @param name 类名
     * @param key 类文件的解密密钥
     */
    public void runClass(String name, String key)
    {
        try
        {
            ClassLoader loader = new CryptoClassLoader(Integer.parseInt(key));
            Class<?> c = loader.loadClass(name);
            Method m = c.getMethod("main", String[].class);
            m.invoke(null, (Object) new String[] {});
        }
        catch (Throwable e)
        {
            JOptionPane.showMessageDialog(this, e);
        }
    }
}

/**
 * 此类加载器加载加密的类文件。
 */
class CryptoClassLoader extends ClassLoader
{
    private int key;

    /**
     * 构建一个加密类加载器。
     * @param k 解密密钥
     */
    public CryptoClassLoader(int k)
    {
        key = k;
    }

    protected Class<?> findClass(String name) throws ClassNotFoundException
    {
        try
        {
            byte[] classBytes = null;
            classBytes = loadClassBytes(name);
            Class<?> cl = defineClass(name, classBytes, 0, classBytes.length);
            if (cl == null) throw ClassNotFoundException(name);
            return cl;
        }
        catch (IOException e)
        {
            throw new ClassNotFoundException(name);
        }
    }

    /**
     * 加载并解密类字节。
     * @param name 类名
     * @return 类字节数组
     */
    private byte[] loadClassBytes(String name) throws IOException
    {
        String cname = name.replace('.', '/') + ".caesar";
        byte[] bytes = Files.readAllBytes(Paths.get(cname));
        for (int i = 0; i < bytes.length; i++)
            bytes[i] = (byte) (bytes[i] - key);
        return bytes;
    }
}
```

**列表 9.2** `classLoader/Caesar.java`

点击此处查看代码图像



```java
package classLoader;

import java.io.*;

/**
 * 使用凯撒密码加密文件。
 * @version 1.01 2012-06-10
 * @author Cay Horstmann
 */
public class Caesar
{
    public static void main(String[] args) throws Exception
    {
        if (args.length != 3)
        {
            System.out.println("USAGE: java classLoader.Caesar in out key");
            return;
        }

        try(FileInputStream in = new FileInputStream(args[0]);
             FileOutputStream out = new FileOutputStream(args[1]))
        {
            int key = Integer.parseInt(args[2]);
            int ch;
            while ((ch = in.read()) != -1)
            {
                byte c = (byte) (ch + key);
                out.write(c);
            }
        }
    }
}
```

`java.lang.Class`

`getClassLoader()` 获取此类的类加载器。

`java.lang.ClassLoader`

`getParent()` 返回父类加载器，如果父类加载器是引导类加载器则返回 `null`。

`static Class getSystemClassLoader()` 获取系统类加载器——即用于加载第一个应用程序类的类加载器。

`protected Class findClass(String name)` 应该被类加载器重写，以查找类的字节并通过调用 `defineClass` 方法将其呈现给虚拟机。在类名中，使用 `.` 作为包名分隔符，不要使用 `.class` 后缀。

`defineClass(String name, byte[] byteCodeData, int offset, int length)`

向虚拟机添加新类，其字节码位于给定的数据范围内。

### `java.net.URLClassLoader` `1.2`

- `URLClassLoader(URL[] urls)`

- `URLClassLoader(URL[] urls, ClassLoader parent)`

构造一个从给定 URL 加载类的类加载器。如果 URL 以 `/` 结尾，则认为它是一个目录，否则认为它是一个 JAR 文件。

### `java.lang.Thread` `1.0`

- `ClassLoader getContextClassLoader()` `1.2`

获取此线程的创建者指定的、在执行此线程时最合理的类加载器。

- `void setContextClassLoader(ClassLoader loader)` `1.2`

为此线程中的代码设置一个类加载器，用于检索并加载类。如果线程在启动时没有显式设置上下文类加载器，则使用其父类的上下文类加载器。

### 9.1.5 字节码验证

当类加载器向虚拟机呈现一个新加载的 Java 平台类的字节码时，这些字节码首先会由验证器（`verifier`）进行检查。验证器检查指令无法执行明显具有破坏性的操作。除了系统类外，所有类都会通过验证。

以下是验证器执行的一些检查：

- 变量在使用之前已完成初始化。
- 方法调用与对象引用的类型匹配。
- 没有违反访问私有数据和方法的规则。
- 局部变量访问位于运行时栈范围内。
- 运行时栈不会溢出。

如果任何这些检查失败，该类将被认为已损坏且不会被加载。

***

![Image](img/00002.jpeg) 注释

如果你熟悉哥德尔定理（Gödel’s theorem），你可能会好奇验证器如何证明一个类文件没有类型不匹配、未初始化的变量和栈溢出。哥德尔定理指出，无法设计出一种能够处理程序文件并判断输入程序是否具有特定属性（例如没有栈溢出）的算法。这难道 Oracle 的公关部门与逻辑法则之间的冲突吗？不——事实上，验证器在哥德尔的意义上`不是`一个判定算法。如果验证器接受了一个程序，它确实是安全的。然而，验证器可能会拒绝虚拟机指令，尽管它们实际上是安全的。（当你被迫使用虚拟值初始化变量时，因为验证器无法看到它将要被正确初始化，你可能遇到过这个问题。）

***

这种严格的验证是一项重要的安全考量。意外错误（如未初始化的变量）如果不被捕获，很容易造成破坏性后果。更重要的是，在开放的互联网世界中，你必须防止那些故意制造恶意影响的程序员。例如，通过修改运行时栈上的值或向系统对象的私有数据字段写入数据，程序可以突破浏览器的安全系统。

然而，你可能会想，为什么一个特殊的验证器要检查所有这些特性呢？毕竟，编译器永远不会允许你生成一个使用了未初始化变量或从另一个类访问私有数据字段的类文件。事实上，Java 语言编译器生成的类文件总是通过验证的。但是，类文件中使用的字节码格式有详尽的文档，对于具有汇编编程和十六编辑器经验的人来说，手动生成一个包含 Java 虚拟机有效但不安全指令的类文件很容易。验证器始终是在防止恶意篡改的类文件，而不仅仅检查编译器生成的类文件。

以下是如何构造这样一个被修改的类文件的示例。我们从列表 9.3 中的程序 `VerifierTest.java` 开始。这是一个调用方法并显示方法结果简单程序。该程序既可以作为控制台程序运行，也可以作为 applet。`fun` 方法本身只是计算 `1 + 2`。

点击此处查看代码图像

```java
static int fun()
{
   int m;
   int n;
   m = 1;
   n = 2;
   int r = m + n;
   return r;
}
```

作为一个实验，尝试编译该程序的以下修改版本：

点击此处查看代码图像

```java
static int fun()
{
   int m = 1;
   int n;
   m = 1;
   m = 2;
   int r = m + n;
   return r;
}
```

在这种情况下，`n` 没有初始化，它可能有任何随机值。当然，编译器检测到了这个问题并拒绝编译该程序。要创建一个坏的类文件，我们需要多下点功夫。首先，运行 `javap` 程序找出编译器如何翻译 `fun` 方法。命令

点击此处查看代码图像

```bash
javap -c verifier.VerifierTest
```

显示了助记符形式的字节码。

点击此处查看代码图像

```text
Method int fun()
0: iconst_1
1: istore_0
2: iconst_2
3: istore_1
4: iload_0
5: iload_1
6: iadd
7: istore_2
8: iload_2
9: ireturn
```

将 `istore_1` 改为 `istore_0`。也就是说，局部变量 `0` 被初始化了两次，而局部变量 `1` 没有。我们需要这些指令的十六进制值；这些值可以从 Tim Lindholm 和 Frank Yell (1999) 编写的 *The Virtual Machine, Second Edition* 中轻松获得。

点击此处查看代码图像

```text
0: iconst_1
1: istore_0
2: iconst_2
3: istore_0
4: iload_0
5: iload_1
6: iadd
7: istore_2
8: iload_2
9: ireturn
```

你可以使用任何十六编辑器来执行修改。在图 9.4 中，你看到加载到十六编辑器中的类文件 `VerifierTest.class`，显示了 `fun` 方法的字节码。

![Image](img/00002.jpeg)

**图 9.4** 使用十六编辑器修改字节码

将 `3C` 改为 `3B` 并保存类文件。然后尝试运行 `VerifierTest` 程序。你得到一个错误：

```text
Exception in thread "main" java.lang.VerifyError: (class: VerifierTest, method:fun signature:()I) Access value from uninitialized register 1
```

很好——虚拟机检测到了我们的修改。现在使用 `-nover`（或 `-verify:none`）运行程序。

点击此处查看代码图像

```bash
java -nover verifier.VerifierTest
```

`fun` 方法返回一个看似随机的值。这实际上是存储在变量 `n` 中的碰巧值。这是一个典型的输出：

```text
1 + 2 == 15
```

为了看到浏览器如何处理验证，我们将此程序编写为作为应用程序或 applet。将 applet 加载到浏览器中，使用文件 URL

点击此处查看代码图像

`file:///C:/CoreJavaBook/v2ch9/verifier/VerifierTest.html`

然后你会看到指示验证失败的错误消息（图 9.5）。

**列表 9.5** `验证失败`

```java
public static void main(String[] args)
{
    System.out.println("1 + 2 == " + fun());
}

/**
 * 一个计算 1 + 2 的函数。
 * @return 如果代码没有被损坏，则返回 3
 */
public static int fun()
{
    int m;
    int n;
    m = 1;
    n = 2;
    // 使用十六进制编辑器将类文件修改为 "m = 2"
    int r = m + n;
    return r;
}

public void paint(Graphics g)
{
    g.drawString("1 + 2 == " + fun(), 20, 20);
}
```

![Image](img/00142.jpeg)

**图 9.5** 加载被损坏的类文件会引发方法验证错误。

### 9.2 安全管理器与权限

一旦类被加载到虚拟机并经过验证器的检查，Java 平台的第二种安全机制就会启动作用：`security manager`（安全管理器）。接下来的章节将讨论此的主题。

#### 9.2.1 权限检查

安全管理器控制是否允许执行特定的操作。安全管理器检查的操作包括以下：

- 创建新的类加载器
- 退出虚拟机
- 使用反射访问另一个类的字段
- 访问文件
- 打开套字连接
- 启动打印作业
- 访问系统剪贴板
- 访问 AWT 事件队列
- 弹出一个顶层窗口

Java 库中还有许多其他检查。

运行 Java 应用程序时的默认行为是不安装安全管理器，因此所有这些操作都是允许的。相反，applet 查看器强制执行非常严格的安全策略。例如，applet 不允许退出虚拟机。如果它们尝试调用 `exit` 方法，将抛出一个安全异常（security exception）。以下是详细的发生过程。`Runtime` 类的 `exit` 方法调用安全管理器的 `checkExit` 方法。这里是 `exit` 方法的代码：

```java
public void exit(int status)
{
    SecurityManager security = System.getSecurityManager();
    if (security != null)
        security.checkExit(status);
    exitInternal(status);
}
```

安全管理器现在检查退出请求是来自浏览器还是单个 applet。如果安全管理器同意退出请求，`checkExit` 方法将直接返回并继续正常处理。然而，如果安全管理器不想授予该请求，`checkExit` 方法将抛出 `SecurityException`。只有在没有发生异常的情况下，`exit` 方法才会继续执行。然后它会调用私有的 `exitInternal` 方法来实际终止虚拟机。没有其他方法可以终止虚拟机，而且由于 `exitInternal` 方法是私有的，无法从任何其他类进行调用。因此，任何尝试退出虚拟机的代码都必须通过 `exit` 方法，从而通过 `checkExit` 安全检查，且在不触发安全异常。

显然，安全策略的完整性取决于严谨的代码编写。库中的系统服务提供程序在尝试任何敏感操作之前，必须始终咨询安全管理器。Java 平台的安全管理器允许程序员和系统管理员对单个权限进行细粒度的控制。我们将在接下来的章节中描述这些功能。首先，我们将总结 Java 平台的安全模型。然后，我们将展示你如何使用 `policy files`（策略文件）来控制权限。最后，我们将解释你如何定义自己的权限类型。

![Image](img/00002.jpeg) 注意：可以实现并安装你自己的安全管理器，但除非你是计算机安全专家，否则不应尝试这样做。配置标准的安全管理器安全得多。

#### 9.2.2 Java 平台安全

JDK 1.0 有一个非常简单的安全模型：本地类拥有完全权限，而远程类被限制在 `sandbox`（沙箱）中。就像一个只能在沙箱里玩的孩子，远程代码只允许在屏幕上绘图并与用户交互。applet 安全管理器拒绝对本地资源的所有访问。JDK 1.1 实现了细微修改：受信任实体签名的远程代码被授予与本地类相同的权限。然而，这两个版本的 JDK 都使用了“全或无”的方法。程序要么拥有完全访问权限，要么必须在沙箱中运行。

从 Java SE 1.2 开始，Java 平台拥有了灵活多的机制。`security policy`（安全策略）将 `code sources` 映射到 `permission sets`（见图 9.6）。

`code source`（代码源）由 `code base`（代码基）和一组 `certificates`（证书）指定。`code base` 指定代码的来源。例如，远程 applet 代码的 `code base` 是加载 applet 的 HTTP URL。JAR 文件中代码的 `code base` 是该文件的 URL。如果存在证书，它是某些方对代码未被篡改的保证。我们将在章稍后的部分介绍证书。

![Image](img/00143.jpeg)

**图 9.6** 安全策略

`permission`（权限）是任何被安全管理器检查的属性。Java 平台支持许多权限类，每个类封装了特定权限的细节。例如，以下 `FilePermission` 类的实例表示读写 `/tmp` 目录下的任何文件都是允许的：

```java
FilePermission p = new FilePermission("/tmp/*", "read,write");
```

更重要的是，`Policy` 类的默认实现从 `permission file`（权限文件）读取权限。在权限文件中，相同的读取权限表示为：

```permission java.io.FilePermission "/tmp/*", "read,write";
```

我们将在下一节讨论权限文件。图 9.7 显示了 Java SE 1.2 提供的权限类层次结构。在随后的 Java 版本中，增加了更多的权限类。

![Image](img/00144.jpeg)

**图 9.7** 权限类层次结构的一部分

在前面的章节中，你看到 `SecurityManager` 类具有如 `checkExit` 之类的安全检查方法。这些方法仅是为了方便程序员和向后兼容。它们都映射到标准的权限检查。例如，这里是 `checkExit` 方法的源码：

```java
public void checkExit()
{
    checkPermission(new RuntimePermission("exitVM"));
}
```

每个类都有一个 `protection domain`（保护域）——封装了代码源和权限集合的对象。当 `SecurityManager` 需要检查权限时，它会查看当前调用栈上所有方法的类。然后它获取所有类的保护域，并询问每个保护域的权限集合是否允许正在检查的操作。如果所有域都同意，检查通过。否则，将抛出 `SecurityException`。

为什么调用栈上的所有方法都需要允许特定的操作？让我们来看一个例子。假设 applet 的 `init` 方法想要打开一个文件。它可能会调用：

```java
Reader in = new FileReader(name);
```

`FileReader` 构造函数调用了 `FileInputStream` 构造函数，后者调用安全管理器的 `checkRead` 方法，最后调用带有 `FilePermission(name, "read")` 对象的 `checkPermission` 方法。表 9.1 显示了该调用栈。

![Image](img/00145.jpeg)

**表 9.1** 权限检查期间的调用栈

`FileInputStream` 和 `SecurityManager` 类是*系统类*，它们的 `CodeSource` 为 `null`，且权限由 `AllPermission` 类的实例组成，该类允许所有操作。显然，仅凭它们的权限无法确定检查的结果。如你所见，`checkPermission` 方法必须考虑 applet 类的受限权限。通过检查整个调用堆栈，安全机制确保了一个类永远不会请求另一个类代表自己执行敏感操作。

***

![Image](img/00002.jpeg) 备注



这段对权限检查的简要讨论解释了基本概念。然而，我们在这里省略了许多技术细节。在安全领域，魔鬼隐藏在细节中，我们鼓励你阅读李工的书获取更多信息。对于 Java 平台安全模型的更具批判性的观点，请参考 Gary McGraw 和 Ed W. Felten 编写书籍《Securing Java: Getting Down to Business with Mobile Code, Second Edition》（Wiley, 1999）。你可以在`www.securingjava.com`找到这本书的在线版本。

---

### `java.lang.SecurityManager`（1.0）

- `void checkPermission(Permission p)`（1.2）

检查此安全管理器是否授予指定的权限。如果未授予权限，该方法将抛出`SecurityException`。

---

### `java.lang.Class`（1.0）

- `ProtectionDomain getProtectionDomain()`（1.2）

获取此类的保护域，如果加载此类时没有保护域，则返回`null`。

---

### `java.security.ProtectionDomain`（1.2）

- `ProtectionDomain(CodeSource source, PermissionCollection permissions)`

使用给定的代码源和权限构造一个保护域。

- `CodeSource getCodeSource()`

获取此保护域的代码源。

- `boolean implies(Permission p)`

如果此保护域允许指定的权限，则返回`true`。

---

### `java.security.CodeSource`（1.2）

- `Certificate[] getCertificates()`

获取与此代码源相关的类文件签名证书链。

- `URL getLocation()`

获取与此代码源相关的类文件代码基（code base）。

#### 9.2.3 安全策略文件

*策略管理器*读取*策略文件*，这些文件包含了将代码源映射到权限的指令。这是一个典型的策略文件：

点击此处查看代码图像

```java
grant codeBase "http://www.horstmann.com/classes"
{
    permission java.io.FilePermission "/tmp/*", "read,write";
};
```

该文件向所有从`www.horstmann.com/classes`下载的代码授予读写`/tmp`目录目录下文件的权限。

你可以在标准位置安装策略文件。默认情况下，有两个位置：

- Java 平台主目录下的`java.policy`文件
- 用户主目录下的`.java.policy`文件（注意文件名开头有一个点）

![Image](img/00002.jpeg) 备注

你可以在`jre`/`lib/security`中的`java.security`配置文件中更改这些文件的位置。默认指定如下：

点击此处查看代码图像

```text
policy.url.1=file:${java.home}/lib/security/java.policy
policy.url.2=file:${user.home}/.java.policy
```

系统管理员可以修改`java.security`文件，并指定位于另一个服务器上且用户无法编辑的策略 URL。策略文件中可以包含任意数量的策略 URL（带有连续的数字编号）。所有文件的权限将合并在一起。

如果你想将策略存储在文件系统之外，可以实现`Policy`类的子类来收集权限。然后修改`java.security`配置文件中的行：

点击此处查看代码图像

```text
policy.provider=sun.security.provider.PolicyFile
```

---

在测试期间，我们不喜欢不断修改标准策略文件。因此，我们更倾向于显式指定每个应用程序所需的策略文件。将权限放入单独的文件中——例如`MyApp.policy`。要应用该策略，你有两种选择。你可以在应用程序的`main`方法内部设置系统属性：

点击此处查看代码图像

```java
System.setProperty("java.security.policy", "MyApp.policy");
```

或者，你可以这样启动虚拟机：

点击此处查看代码图像

```bash
java -Djava.security.policy="MyApp.policy"
```

对于 applet，你应该使用：

点击此处查看代码图像

```bash
appletviewer -Jjava.security.policy=MyApp.policy
```

（你可以使用`-J`选项将参数传递给`appletviewer`。）

如果你添加双等号，例如：

点击此处查看代码图像

```bash
java -Djava.security.policy==MyApp.policy
```

那么你的应用程序将仅使用指定的文件，而标准策略将被忽略。

---

![Image](img/00004.jpeg) 注意

在测试期间一个常见的错误是在主目录下意外留下一个授予大量权限（甚至是`AllPermission`）的`.java.policy`文件。默认情况下。

---

正如你之前看到的，Java 应用程序默认不安装安全管理器。因此，在安装它之前，你看不到策略文件的效果。你可以在`main`方法中加入：

```java
System.setSecurityManager(new SecurityManager());
```

或者在启动虚拟机时添加命令行选项`-Djava.security.manager`。

```bash
java -Djava.security.manager -Djava.security.policy=MyApp.policy
```

在本节的剩余部分，我们将详细介绍如何在策略文件中描述权限。我们将描述整个策略文件的格式，代码证书部分将在本章稍后介绍。

策略文件包含一系列`grant`条目。每个条目的格式如下：

点击此处查看代码图像

```java
grant codesource
{
    permission[1];
    permission[2];
    ...
};
```

`codesource`包含代码基（如果条目适用于所有代码源，则可以省略）以及信任的主体和证书签名者的名称（如果条目不需要签名，则可以省略）。

代码基指定为：

`codeBase "*url*"`

如果 URL 以`/`结尾，则指向一个目录。否则，它被视为 JAR 文件的名称。例如：

点击此处查看代码图像

```java
grant codeBase "www.horstmann.com/classes/" { ... };
grant codeBase "www.horstmann.com/classes/MyApp.jar" { ... };
```

代码基是一个 URL，并且应始终使用正斜杠作为文件分隔符，即使在 Windows 的文件 URL 中也是如此。例如：

点击此处查看代码图像

```java
grant codeBase "file:C:/myapps/classes/" { . . . };
```

---

![Image](img/00002.jpeg) 备注

每个人都知道`http` URL 以双斜杠（`http://`）开头。但对于`file` URL 存在足够的困惑，因此策略文件读取器接受两种形式的`file` URL——即`file://localFile`和`file:localFile`。此外，Windows 驱动器字母之前的斜杠是可选的。也就是说，以下所有形式都是接受的：

点击此处查看代码图像

`file:C:/dir/filename.ext`

`file:/C:/dir/filename.ext`

`file://C:/dir/filename.ext`

`file:///C:/dir/filename.ext`

实际上，在我们的测试中，`file:////C:/dir/filename.ext`也是接受的，我们对此没有解释。

---

权限具有以下结构：

点击此处查看代码图像

```java
permission className targetName, actionList;
```

`className`是权限类的完全限定类名（例如`java.io.FilePermission`）。`targetName`是特定于权限的值——例如，用于文件权限的文件或目录名称，或者用于套接权限的主机和端口。`actionList`也是特定于权限的。它是一个操作列表，用逗号分隔，例如`read`或`connect`。某些权限类不需要目标名称和操作列表。表 9.2 列出了常用的权限类及其操作。

![Image](img/00146.jpeg)![Image](img/00147.jpeg)![Image](img/00148.jpeg)![Image](img/00149.jpeg)

**表 9.2** 权限及其关联的目标和操作

如你所见从表 9.2 所示，大多数权限仅仅允许某种特定操作。你可以将该操作视为具有隐含操作`"permit"`的目标。这些权限类都扩展了`BasicPermission`类（参见第 512 页的图 9.7）。然而，文件、套接字和属性权限的目标更为复杂，我们需要详细研究它们。

文件权限目标可以具有以下形式：

![Image](img/00150.jpeg)

例如，以下权限条提供了对`/myapp`目录中所有文件及其任何子目录的访问：

点击此处查看代码图像

```java
permission java.io.FilePermission "/myapp/-", "read,write,delete";
```

你必须使用`\\`转义序列来表示 Windows 文件名中的反斜杠。

点击此处查看代码图像

```java
permission java.io.FilePermission "c:\\myapp\\-", "read,write,delete";
```

套接字权限目标由主机和一个端口范围组成。主机规范具有以下形式：

![Image](img/00151.jpeg)

端口范围是可选的，并具有以下形式：

![Image](img/00152.jpeg)

这是一个示例：

点击此处查看代码图像

```java
permission java.net.SocketPermission "*.horstmann.com:8000-8999", "connect";
```

最后，属性权限目标可以具有两种形式之一：

![Image](img/00153.jpeg)

示例包括`"java.home"`和`"java.vm.*"`。

例如，以下权限条允许程序读取所有以`java.vm`开头的属性：

点击此处查看代码图像

```java
permission java.util.PropertyPermission "java.vm.*", "read";
```

你可以在策略文件中使用系统属性。令牌`${*property}`会被属性值替换。例如，`${user.home}`被替换为用户的家目录。这是该系统属性在权限条目中的典型用法：

点击此处查看代码图像

```java
permission java.io.FilePermission "${user.home}", "read,write";
```

为了创建跨平台的策略文件，使用`file.separator`属性而不是显式的`/`或`\\`分隔符是一个好主意。为了简化，特殊符号`${/}`是`${file.separator}`的快捷方式。例如：

点击此处查看代码图像

```java
permission java.io.FilePermission "${user.home}${/}-", "read,write";
```

是一个授予读取权限的可移植条目。

---

![Image](img/00002.jpeg) 备注

每个人都知道`http` URL 以双斜杠（`http://`）开头。但对于`file` URL 存在足够的困惑，因此策略文件读取器接受两种形式的`file` URL——即`file://localFile`和`file:localFile`。此外，Windows 驱动器字母之前的斜杠是可选的。也就是说，以下所有形式都是接受的：

点击此处查看代码图像

`file:C:/dir/filename.ext`

`file:/C:/dir/filename.ext`

`file://C:/dir/filename.ext`

`file:///C:/dir/filename.ext`

实际上，在我们的测试中，`file:////C:/dir/filename.ext`也是接受的，我们对此没有解释。

---

权限具有以下结构：

点击此处查看代码图像

```java
permission className targetName, actionList;
```

`className`是权限类的完全限定类名（例如`java.io.FilePermission`）。`targetName`是特定于权限的值——例如，用于文件权限的文件或目录名称，或者用于套接权限的主机和端口。`actionList`也是特定于权限的。它是一个操作列表，用逗号分隔，例如`read`或`connect`。某些权限类不需要目标名称和操作列表。表 9.2 列出了常用的权限类及其操作。

![Image](img/00146.jpeg)![Image](img/00147.jpeg)![Image](img/00148.jpeg)![Image](img/00149.jpeg)

**表 9.2** 权限及其关联的目标和操作

如你所见从表 9.2 所示，大多数权限仅仅允许某种特定操作。你可以将该操作视为具有隐含操作`"permit"`的目标。这些权限类都扩展了`BasicPermission`类（参见第 512 页的图 9.7）。然而，文件、套接字和属性权限的目标更为复杂，我们需要详细研究它们。

文件权限目标可以具有以下形式：

![Image](img/00150.jpeg)

例如，以下权限条提供了对`/myapp`目录中所有文件及其任何子目录的访问：

点击此处查看代码图像

```java
permission java.io.FilePermission "/myapp/-", "read,write,delete";
```

你必须使用`\\`转义序列来表示 Windows 文件名中的反斜杠。

点击此处查看代码图像

```java
permission java.io.FilePermission "c:\\myapp\\-", "read,write,delete";
```

套接字权限目标由主机和一个端口范围组成。主机规范具有以下形式：

![Image](img/00151.jpeg)

端口范围是可选的，并具有以下形式：

![Image](img/00152.jpeg)

这是一个示例：

点击此处查看代码图像

```java
permission java.net.SocketPermission "*.horstmann.com:8000-8999", "connect";
```

最后，属性权限目标可以具有两种形式之一：

![Image](img/00153.jpeg)

示例包括`"java.home"`和`"java.vm.*"`。

例如，以下权限条允许程序读取所有以`java.vm`开头的属性：

点击此处查看代码图像

```java
permission java.util.PropertyPermission "java.vm.*", "read";
```

你可以在策略文件中使用系统属性。令牌`${*property}`会被属性值替换。例如，`${user.home}`被替换为用户的家目录。这是该系统属性在权限条目中的典型用法：

点击此处查看代码图像

```java
permission java.io.FilePermission "${user.home}", "read,write";
```

为了创建跨平台的策略文件，使用`file.separator`属性而不是显式的`/`或`\\`分隔符是一个好主意。为了简化，特殊符号`${/}`是`${file.separator}`的快捷方式。例如：

点击此处查看代码图像

```java
permission java.io.FilePermission "${user.home}${/}-", "read,write";
```

是一个授予读取权限的可移植条目。

---

![Image](img/00154.jpeg)

#### 9.2.4 自定义权限

在本节中，你将看到如何提供用户可以在策略文件中使用的自定义权限类。要实现你的权限类，请扩展`Permission`类并提供以下方法：

- 带有两个`String`参数的构造函数，用于目标和操作列表
- `String getActions()`
- `boolean equals(Object other)`
- `int hashCode()`
- `boolean implies(Permission other)`

最后一个方法是最重要的。权限具有顺序，更通用的权限隐含特定的权限。考虑文件权限：

点击此处查看代码图像

```java
p1 = new FilePermission("/tmp/-", "read, write");
```

此权限允许对`/tmp`目录及其任何子目录中的任何文件进行读取和写入。

此权限隐含其他特定的权限：

点击此处查看代码图像



```java
p2 = new FilePermission("/tmp/-", "read");
p3 = new FilePermission("/tmp/aFile", "read, write");
p4 = new FilePermission("/tmp/aDirectory/-", "write");
```

换句话说，文件权限 `p1` 隐含另一个文件权限 `p2`，如果：

1. `p1` 的目标文件集包含了 `p2` 的目标文件集。
2. `p1` 的操作集包含了 `p2` 的操作集。

考虑 `implies` 方法使用的以下示例。当 `FileInputStream` 构造函数想要打开文件进行读取时，它会检查是否有权限这样做。对于该检查，一个特定的文件权限对象被传递给 `checkPermission` 方法：

点击此处查看代码图像

```java
checkPermission(new FilePermission(fileName, "read"));
```

安全管理器现在询问所有相关的权限是否隐含了此权限。如果其中任何一个隐含了它，检查就会通过。

特别是，`AllPermission` 隐含所有权限。

如果你定义了自己的权限类，你需要为你的权限对象定义合适的隐含概念。例如，假设你为 Java 技术的机顶盒定义了一个 `TVPermission`。一个权限：

点击此处查看代码图像

```java
new TVPermission("Tommy:2-12:1900-2200", "watch,record")
```

可能允许 Tommy 在 19:00 到 22:00 之间观看和录制 2-12 号频道。你需要实现 `implies` 方法，使得此权限隐含一个更特定的权限，例如：

点击此处查看代码图像

```java
new TVPermission("Tommy:4:2000-2100", "watch")
```

在下一个示例程序中，我们实现了一种新的权限，用于监控文本区域中文本的插入。该程序确保你无法向文本区域中添加 `sex`、`drugs` 和 `C++` 等坏词。我们使用了一个自定义的权限类，以便在策略文件中提供坏词列表。

以下 `JTextArea` 的子类会询问安全管理器是否可以添加新文本：

点击此处查看代码图片

```java
class WordCheckTextArea extends JTextArea
{
    public void append(String text)
    {
        WordCheckPermission p = new WordCheckPermission(text, "insert");
        SecurityManager manager = System.getSecurityManager();
        if (manager != null) manager.checkPermission(p);
        super.append(text);
    }
}
```

如果安全管理器授予了 `WordCheckPermission`，则文本会被追加。否则，`checkPermission` 方法将抛出异常。

词汇检查权限有两个可能的动作：`insert`（插入特定文本的权限）和 `avoid`（添加任何避开某些坏词的文本的权限）。你应该使用以下策略文件运行此程序：

点击此处查看代码图片

```java
grant
{
    permission permissions.WordCheckPermission "sex,drugs,C++", "avoid";
};
```

该策略文件授予了插入任何避开坏词 `sex`、`drugs` 和 `C++` 文本的权限。

在设计 `WordCheckPermission` 类时，我们必须特别注意 `implies` 方法。以下是控制权限 `p1` 是否隐含权限 `p2` 的规则：

- 如果 `p1` 动作为 `avoid` 且 `p2` 动作为 `insert`，则 `p2` 的目标必须避开 `p1` 中的所有单词。例如，权限：

  `permissions.WordCheckPermission "sex,drugs,C++", "avoid"`

  隐含权限：

  `permissions.WordCheckPermission "Mary had a little lamb", "insert"`

- 如果 `p1` 和 `p2` 的动用均为 `avoid`，则 `p2` 的单词集必须包含 `p1` 单词集中的所有单词。例如，权限：

  `permissions.WordCheckPermission "sex,drugs", "avoid"`

  隐含权限：

  `permissions.WordCheckPermission "sex,drugs,C++", "avoid"`

- 如果 `p1` 和 `p2` 的动用均为 `insert`，则 `p1` 的文本必须包含 `p2` 的文本。例如，权限：

  `permissions.WordCheckPermission "Mary had a little lamb", "insert"`

  隐含权限：

  `permissions.WordCheckPermission "a little lamb", "insert"`

你可以在 Listing 9.4 中找到该类的实现。

注意，要获取权限目标，你需要使用 `Permission` 类中命名容易引起混义的 `getName` 方法。

由于权限在策略文件中是由一对字符串描述的，因此权限类需要准备好解析这些字符串。特别地，我们使用以下方法将 `avoid` 权限的用逗号分隔的坏词列表转换为真正的 `Set`：

点击此处查看代码图片

```java
public Set<String> badWordSet()
{
    Set<String> set = new HashSet<String>();
    set.addAll(Arrays.asList(getName().split(",")));
    return set;
}
```

这段代码允许我们使用 `equals` 和 `containsAll` 方法来比较集合。正如你在第 3 章中所示，集合类的 `equals` 方法会在两个集合以任何顺序包含相同元素时认为它们是相等的。例如，由 `"sex,drugs,C++"` 和 `"C++,drugs,sex"` 产生的集合是相等的。

***

![Image](img/00004.jpeg)

**注意**：确保你的权限类是一个公共类。策略文件加载器无法加载启动类路径之外的具有包可见性的类，并且会静地忽略任何无法找到的类。

***

Listing 9.5 中的程序显示了 `WordCheckPermission` 类是如何运作的。在文本框中输入任何文本并点击 Insert 按钮。如果安全检查通过，文本将追加到文本区域。如果没有通过，则会抛出异常。

```java
Set<String> set = new HashSet<>();
set.addAll(Arrays.asList(getName().split(",")));
return set;
}
```

### 列表 9.5 `permissions/PermissionTest.java`

点击此处查看代码图片

```java
package permissions;

import java.awt.*;
import javax.swing.*;

/**
 * 此类演示了自定义的 WordCheckPermission 使用。
 * @version 1.04 2016-05-10
 * @author Cay Horstmann
 */
public class PermissionTest
{
    public static void main(String[] args)
    {
        System.setProperty("java.security.policy", "permissions/PermissionTest.policy");
        System.setSecurityManager(new SecurityManager());
        EventQueue.invokeLater(() ->
            {
                JFrame frame = new PermissionTestFrame();
                frame.setTitle("PermissionTest");
                frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
                frame.setVisible(true);
            });
    }
}

/**
 * 此框架包含一个文本字段，用于将单词插入到文本区域，
 * 该文本区域受“敏感词汇”的保护。
 */
class PermissionTestFrame extends JFrame
{
    private JTextField textField;
    private WordCheckTextArea textArea;
    private static final int TEXT_ROWS = 20;
    private static final int TEXT_COLUMNS = 60;

    public PermissionTestFrame()
    {
        textField = new JTextField(20);
        JPanel panel = new JPanel();
        panel.add(textField);
        JButton openButton = new JButton("Insert");
        panel.add(openButton);
        openButton.addActionListener(event -> insertWords(textField.getText()));

        add(panel, BorderLayout.NORTH);

        textArea = new WordCheckTextArea();
        textArea.setRows(TEXT_ROWS);
        textArea.setColumns(TEXT_COLUMNS);
        add(new JScrollPane(textArea), BorderLayout.CENTER);
        pack();
    }

    /**
     * 尝试将单词插入到文本区域。如果尝试失败，则显示对话框。
     * @param words 要插入的单词
     */
    public void insertWords(String words)
    {
        try
        {
            textArea.append(words + "\n");
        }
        catch (SecurityException ex)
        {
            JOptionPane.showMessageDialog(this, "抱歉，我无法执行操作。");
            ex.printStackTrace();
        }
    }
}

/**
 * 一个文本区域，其 append 方法执行安全检查，以确保没有添加敏感词汇。
 */
class WordCheckTextArea extends JTextArea
{
    public void append(String text)
    {
        WordCheckPermission p = new WordCheckPermission(text, "insert");
        SecurityManager manager = System.getSecurityManager();
        if (manager != null) manager.checkPermission(p);
        super.append(text);
    }
}
```

### `java.security.Permission` 1.2

- `Permission(String name)` 根据给定的目标名称构造权限。
- `String getName()` 返回此权限的目标名称。
- `boolean implies(Permission other)` 检查此权限是否包含了另一个权限。如果另一个权限描述了一个更具体的条件，且该条件是此权限所描述条件的结果，则情况成立。

## 9.3 用户身份验证

Java API 提供了一个名为 Java 认证与授权服务（JAAS）的框架，它将平台提供的身份验证与权限管理集成。我们将在接下来的章节中讨论 JAAS 框架。

### 9.3.1 JAAS 框架

从名称可以看出，JAAS 框架包含两个组件。“认证”部分负责确定程序用户的身份。“授权”部分负责将用户映射到权限。

JAAS 是一个“可插拔”的 API，它将 Java 应用程序与实现身份验证的具体技术隔离开。它支持 UNIX 登录、NT 登录、Kerberos 认证以及基于证书的认证等。

一旦用户通过了身份验证，你就可以附加一组权限。例如，在这里为 Harry 授予了一组其他用户没有的特定权限：

点击此处查看代码图片

```java
grant principal com.sun.security.auth.UnixPrincipal "harry"
{
    permission java.util.PropertyPermission "user.*", "read";
    ...
};
```

`com.sun.security.auth.UnixPrincipal` 类会检查运行此程序的 UNIX 用户名。其 `getName` 方法返回 UNIX 登录名，我们检查该名称是否等于 `"harry"`。

使用 `LoginContext` 允许安全管理器检查此类授权语句。以下是登录代码的基本结构：

点击此处查看代码图片

```java
try
{
    System.setSecurityManager(new SecurityManager());
    LoginContext context = new LoginContext("Login1"); // 定义在配置中
    context.login();
    // 获取经过身份验证的 Subject
    Subject subject = context.getSubject();
    ...
    context.logout();
}
catch (LoginException exception) // 如果登录未成功则抛出异常
{
    exception.printStackTrace();
}
```

现在 `subject` 表示通过身份验证的个人。`LoginContext` 构造函数中的字符串 `"Login1"` 指向 JAAS 配置中同名的项。这是一个示例配置文件：

点击此处查看代码图片

```java
Login1
{
    com.sun.security.auth.module.UnixLoginModule required;
    whizzbang.auth.module.RetinaModule sufficient;
};

Login2
{
    ...
};
```

当然，JDK 并不包含生物识别登录模块。以下模块在 `com.sun.security.auth.module` 中提供：

- `UnixLoginModule`
- `NTLoginModule`
- `Krb5LoginModule`
- `JndiLoginModule`
- `KeyStoreLoginModule`

一个登录策略由一系列登录模块组成，每个模块被标记为 `required`、`sufficient`、`requisite` 或 `optional`。这些关键字的含义由以下算法给出。

登录认证一个 *subject*（主体），该主体可以有多个 *principal*（主体标识）。一个 principal 描述了主体的某些属性，例如用户名、组 ID 或角色。正如你在 `grant` 语句中看到的，主体标识控制权限。`com.sun.security.auth.UnixPrincipal` 描述 UNIX 登录名，而 `UnixGroupPrincipal` 可以测试是否为 UNIX 组的成员。

`grant` 子句可以测试一个 principal，语法如下：

点击此处查看代码图片

```java
grant principalClass "principalName"
```

例如：

点击此处查看代码图片

```java
grant com.sun.security.auth.UnixPrincipal "harry"
```

当用户登录后，你会在单独的访问控制环境中运行需要检查 principal 代码。使用静态方法 `doAs` 或 `doAsPrivileged` 来启动一个新的 `PrivilegedAction`，其 `run` 方法将执行该代码。

这两个方法都通过调用实现 `PrivilegedAction` 接口的对象的 `run` 方法来执行操作，并使用该主体主体标识的权限：

点击此处查看代码图片



```java
PrivilegedAction<T> action = () ->
    {
        // 使用主体主体标识的权限运行
        ...
    };

T result = Subject.doAs(subject, action); // 或 Subject.doAsPrivileged(subject, action, null)
```

如果动作可能会抛出受检异常，则你需要实现 `PrivilegedExceptionAction` 接口。

`doAs` 和 `doAsPrivileged` 方法之间的区别非常细微。`doAs` 方法从当前的访问控制上下文开始，而 `doAsPrivileged` 方法则从一个新上下文开始。后者允许你将登录代码和“业务逻辑”的权限分离开。在我们的示例应用程序中，登录代码拥有以下权限：

点击此处查看代码图片

`permission javax.security.auth.AuthPermission "createLoginContext.Login1";`

`permission javax.security.auth.AuthPermission "doAsPrivileged";`

经过认证的用户拥有权限：

点击此处查看代码图片

`permission java.util.PropertyPermission "user.*", "read";`

如果我们使用 `doAs` 而不是 `doAsPrivileged`，那么登录代码也需要那个权限！

Listing 9.6 和 9.7 中的程序演示了如何限制某些用户的权限。`AuthTest` 程序对用户用户并运行一个获取系统属性的简单动作。

为了使此示例运行，请将登录和动作的代码封装进两个独立的 JAR 文件：

点击此处查看代码图片

```bash
javac auth/*.java
jar cvf login.jar auth/AuthTest.class
jar cvf action.jar auth/SysPropAction.class
```

如果你查看 Listing 9.8 中的策略文件，你会发现名为 `harry` 的 UNIX 用户具有读取所有文件的权限。将 `harry` 更改为你的登录名。然后运行命令：

点击此处查看代码图片

```bash
java -classpath login.jar:action.jar
    -Djava.security.policy=auth/AuthTest.policy
    -Djava.security.auth.login.config=auth/jaas.config
    auth.AuthTest
```

Listing 9.9 显示了登录配置。

在 Windows 上，请将 `AuthTest.policy` 中的 `UnixPrincipal` 更改为 `NTUserPrincipal`，并将 `jaas.config` 中的 `UnixLoginModule` 更改为 `NTLoginModule`。运行程序时，使用分号分隔 JAR 文件：

点击此处查看代码图片

```bash
java -classpath login.jar;action.jar . . .
```

`AuthTest` 程序现在应该显示 `user.home` 属性的值。然而，如果你用另一个名称登录，应该会抛出安全异常，因为你不再拥有所需的权限。

***

![Image](img/00004.jpeg) 注意事项

请务必严格遵循这些指令。通过做出看似无害的修改，非常容易导致设置错误。

***

## Listing 9.6：`auth/AuthTest.java`

点击此处查看代码图片

***

```java
1    package auth;
2
3    import java.security.*;
4    import javax.security.auth.*;
5    import javax.security.auth.login.*;
6
7    /**
8      * 此程序通过自定义登录认证用户，然后以用户的权限执行 SysPropAction。
9      *
10     * @version 1.01 2007-10-06
11     * @author Cay Horstmann
12     */
13   public class AuthTest
14   {
15      public static void main(final String[] args)
16      {
17          System.setSecurityManager(new SecurityManager());
18          try
19          {
20              LoginContext context = new LoginContext("Login1");
21              context.login();
22              System.out.println("Authentication successful.");
23              Subject subject = context.getSubject();
24              System.out.println("subject=" + subject);
25              PrivilegedAction<String> action = new SysPropAction("user.home");
26              String result = Subject.doAsPrivileged(subject, null);
27              System.out.println(result);
28              context.logout();
29          }
30      catch (LoginException e)
31      {
32          e.printStackTrace();
33      }
34   }
35 }
```

***

## Listing 9.7：`auth/SysPropAction.java`

点击此处查看代码图片

***

```java
1    package auth;
2
3    import java.security.*;
4
5    /**
6      * 查找属性的动作。
7      * @version 1.01 2007-10-06
8      * @author Cay Horstmann
9      */
10   public class SysPropAction implements PrivilegedAction<String>
11   {
12      private String propertyName;
13
14      /**
15        构造一个查找属性的动作。
16        @param propertyName 属性名称，如 "user.home"
17        */
18      public SysPropAction(String propertyName) { this.propertyName = propertyName; }
19
20      @Override
21      public String run()
22      {
23          return System.getProperty(propertyName);
24      }
25   }
```

***

## Listing 9.8：`auth/AuthTest.policy`

点击此处查看代码图片

***

```text
1    grant codebase "login.jar"
2    {
3      permission javax.security.auth.AuthPermission "createLoginContext.Login1";
4      permission javax.security.auth.AuthPermission "doAsPrivileged";
5    };
6
7    grant principal com.security.auth.UnixPrincipal "harry"
8    {
9      permission java.util.PropertyPermission "user.*", "read";
10   };
```

***

## Listing 9.9：`auth/jaas.config`

点击此处查看代码图片

***

```text
1    Login1
2    {
3      com.security.auth.login.UnixLoginModule required;
4    };
```

如果你管理大量的用户，基于角色的身份验证至关重要。将所有合法用户的名称都放入策略文件中是不现实的。相反，登录模块应该将用户映射到“admin”或“HR”等角色，并且权限应该基于这些角色。

登录模块的工作之一是填充正在身份验证的主体（subject）的主委托者集（principal set）。如果登录模块支持角色，它会添加描述角色的 `Principal` 对象。Java 库没有提供用于此目的的类，因此我们编写了自己的类（请参见列表 9.10）。该类简单地存储一个描述/值值对，例如 `role=admin`。它的 `getName` 方法返回该值对，因此我们可以将基于角色的权限添加到策略文件中：

点击此处查看代码图像

```text
grant principal SimplePrincipal "role=admin" { . . . }
```

我们的登录模块在一个文本文件中查找用户、密码和角色，该文件包含如下所示的内容：

点击此处查看代码图像

```text
harry|secret|admin
carl|guessme|HR
```

当然，在真实的登录模块中，你会将这些信息存储在数据库或目录中。

你可以在列表 9.11 中找到 `SimpleLoginModule` 的代码。`checkLogin` 方法检查用户名和密码是否与密码文件中的记录匹配。如果是的话，我们向主体的委托者集添加两个 `SimplePrincipal` 对象：

点击此处查看代码图像

```java
Set<Principal> principals = subject.getPrincipals();
principals.add(new SimplePrincipal("username", username));
principals.add(new SimplePrincipal("role", role));
```

`SimpleLoginModule` 的剩余部分是简单易懂的管道工作。`initialize` 方法接收以下内容：

- 正在身份验证的 `Subject`
- 一个用于检索登录信息的处理器
- 一个可以用于登录模块之间通信的 `sharedState` map
- 一个包含在登录配置中设置的名称/值对的 `options` map

例如，我们如下所示配置我们的模块：

点击此处查看代码图像

```text
SimpleLoginModule required pwfile="password.txt";
```

登录模块从 `options` map 中检索 `pwfile` 设置。登录模块并不收集用户名和密码；那是独立处理器的工作。这种分离允许你使用同一个登录模块，而不必担心登录信息是来自 GUI 对话框、控制台提示符还是配置文件。

处理器在构造 `LoginContext` 时指定，例如：

点击此处查看代码图像

```java
LoginContext context = new LoginContext("Login1",
      new com.sun.security.auth.callback.DialogCallbackHandler());
```

`DialogCallbackHandler` 会弹出一个简单的 GUI 对话框来获取用户名和密码。`com.sun.security.auth.callback.TextCallbackHandler` 类从控制台获取信息。然而，在我们的应用程序中，我们有自己的 GUI 来收集用户名和密码（请参见图 9.10）。我们产生了一个仅仅存储并返回这些信息的简单处理器（请参见列表 9.12）。

```java
  private Map<String, ?> options;

  public void initialize(Subject subject, CallbackHandler callbackHandler,
             Map<String, ?> sharedState, Map<String, ?> options)
  {
    this.subject = subject;
    this.callbackHandler = callbackHandler;
    this.options = options;
  }

  public boolean login() throws LoginException
  {
      if (callbackHandler == null) throw new LoginException("no handler");

      NameCallback nameCall = new NameCallback("username: ");
      PasswordCallback passCall = new PasswordCallback("password: ", false);
      try
      {
          callbackHandler.handle(new Callback[] { nameCall, passCall });
      }
      catch (UnsupportedCallbackException e)
      {
          LoginException e2 = new LoginException("Unsupported callback");
          e2.initCause(e);
          throw e2;
      }
      catch (IOException e)
      {
          LoginException e2 = new LoginException("I/O exception in callback");
          e2.initCause(e);
          throw e2;
      }

      try
      {
          return checkLogin(nameCall.getName(), passCall.getPassword());
      }
      catch (IOException ex)
      {
          LoginException ex2 = new LoginException();
          ex2.initCause(ex);
          throw ex2;
      }
  }

  /**
   * 检查身份验证信息是否有效。如果有效，subject 将获取
   * 用户和角色的主体（principals）。
   * @param username 用户
   * @param password 包含密码的字符数组
   * @return 如果身份验证有效则返回 true
   */
  private boolean checkLogin(String username, char[] password) throws LoginException, IOException
  {
    try (Scanner in = new Scanner(Paths.get("" + options.get("pwfile")), "UTF-8"))
    {
      while (in.hasNextLine())
      {
          String[] inputs = in.nextLine().split("\\|");
          if (inputs[0].equals(username) && Arrays.equals(inputs[1].toCharArray(), password))
          {
              String role = inputs[2];
              Set<Principal> principals = subject.getPrincipals();
              principals.add(new SimplePrincipal("username", username));
              principals.add(new SimplePrincipal("role", role));
              return true;
          }
      }
      return false;
  }

  public boolean logout()
  {
    return true;
  }

  public boolean abort()
  {
    return true;
  }

  public boolean commit()
  {
    return true;
  }
}
```

## 9.12 `jaas/SimpleCallbackHandler.java`

点击此处查看代码图片



```java
package jaas;

import javax.security.auth.callback.*;

/**
 * 这个简单的回调处理器呈现了给定的用户名和密码。
 */
public class SimpleCallbackHandler implements CallbackHandler
{
  private String username;
  private char[] password;

  /**
   * 构造回调处理器。
   * @param username 用户
   * @param password 包含密码的字符数组
   */
  public SimpleCallbackHandler(String username, char[] password)
  {
    this.username = username;
    this.password = password;
  }

  public void handle(Callback[] callbacks)
  {
    for (Callback callback : callbacks)
    {
      if (callback instanceof NameCallback)
      {
          ((NameCallback) callback).setName(username);
      }
      else if (callback instanceof PasswordCallback)
      {
          ((PasswordCallback) callback).setPassword(password);
      }
    }
  }
}
```

### Listing 9.13 `jaas/JAASTest.java`

点击此处查看代码图片。

```java
package jaas;

import java.awt.*;
import javax.swing.*;

/**
 * 该程序通过自定义登录验证用户身份，然后根据用户的
 * 权限查找系统属性。
 * @version 1.02 2016-05-10
 * @author Cay Horstmann
 */
public class JAASTest
{
  public static void main(final String[] args)
  {
    System.setSecurityManager(new SecurityManager());
    EventQueue.invokeLater(() ->
    {
        JFrame frame = new JAASFrame();
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setTitle("JAASTest");
        frame.setVisible(true);
    });
  }
}
```

### Listing 9.14 `jaas/JAASTest.policy`

点击此处查看代码图片。

```
grant codebase "file:login.jar"
{
  permission java.awt.AWTPermission "showWindowWithoutWarningBanner";
  permission java.awt.AWTPermission "accessEventQueue";
  permission javax.security.auth.AuthPermission "createLoginContext";
  permission javax.security.auth.AuthPermission "doAsPrivileged";
  permission javax.security.auth.AuthPermission "modifyPrincipals";
  permission java.io.FilePermission "jaas/password.txt", "read";
  permission java.util.PropertyPermission "*", "read";
};
```

在所有登录模块均成功后调用，适用于需要两阶段提交的登录场景。如果操作成功，则返回 `true`。

- `boolean abort()`

  如果另一个登录模块的失败导致登录过程中止，则调用此方法。如果操作成功，返回 `true`。

- `boolean logout()`

  注销此主体。如果操作成功，返回 `true`。

---

## 9.4 数字签名

正如我们之前说的，applet 是引发 Java 热潮的源头。在实践中，人们发现虽然他们可以编写动画 applet（例如著名的“疯狂文本”），但在 JDK 1.0 安全模型中，applet 无法完成很多有用操作。例如，由于 JDK 1.0 下的 applet 受到严格监控，即使从公司安全的内部网执行 applet 的风险相对较小，它们在公司内网中也做不了什么。Sun 很快意识到，要让 applet 变得真正有用，用户需要能够根据 applet 的来源分配不同级别的安全性。如果 applet 来自信任供应商且未被篡改，该 applet 的用户就可以决定是否赋予其更多权限。

为了给予 applet 更多的信任，我们需要知道两点：

- applet 来自于哪里？
- 代码在传输过程中是否被损坏？

在过去的 50 年里，数学家和计算机科学家开发了复杂的算法来确保数据的完整性和用于电子签名。`java.security` 包包含了许多此类算法的实现。幸运的是，使用 `java.security` 包中的算法不需要理解底层的数学原理。在接下来的章节中，我们将向你展示消息摘要如何检测数据文件的变化，以及数字签名如何证明签名者的身份。

### 9.4.1 消息摘要

消息摘要是数据块的数字指纹。例如，所谓的 SHA-1（安全哈希算法 #1）可以将任何数据块（无论多长）压缩成 160 位（20 字节）的序列。就像真实的指纹一样，人们希望两个消息具有相同的 SHA-1 指纹。当然，这并不可能的——只有 2¹⁶⁰ 个 SHA-1 指纹，因此某些消息必然具有相同的指纹。但 2¹⁶⁰ 是一个巨大的数字，以至于重复发生的概率可以忽略不计。微小到什么程度？根据 James Walsh 在*真实概率：风险如何影响你的日常生活*（Merritt Publishing, 1996）中的说法，你被雷劈死的概率大约是 30,000 分之一。现在，想另外九个人——例如，你最不喜欢的九位经理或教授。你和他们所有人被雷劈死的概率，高于伪造消息与原始消息具有相同 SHA-1 指纹的概率。（当然，会有超过十个人（其中你可能都不认识他们）被雷劈死。然而，我们谈论的是你所选的这特定这些人被消灭的极微小的概率。）

消息摘要有两个基本属性：

- 如果数据的某位或几位发生变化，消息摘要也会随之改变。
- 拥有给定消息的伪造者无法构造出一个与原始消息具有相同摘要的伪消息。

第二个属性同样是一个概率问题。考虑以下这位万富翁父亲发送的消息：

*“在我去世后，我的财产应在孩子们之间平分；然而，我的儿子 George 将一无所有。”*

该消息（带有最后的换行符）的 SHA-1 指纹为：

点击此处查看代码图像。

`12 5F 09 03 E7 31 30 19 2E A6 E7 E4 90 43 84 B4 38 99 8F 67`

不信任他人的父亲将消息交给了一位律师，将指纹给了另一位律师。现在，假设 George 收贿了持有消息的律师。他想修改消息，让 Bill 一无所有。当然，这会将指纹改变为完全不同的位模式：

点击此处查看代码图像。

`7D F6 AB 08 EB 40 EC CD AB 74 ED E9 86 F9 ED 99 D1 45 B1 57`

George 能找到其他匹配该指纹的措辞吗？如果他从地球形成起就拥有一亿台计算机，每台每秒计算百万条消息，他可能还没有找到一个可以替换的消息。

已经有很多算法被设计计算此类消息摘要。其中包括美国国家标准与技术研究院（NIST）开发的安全哈希算法 SHA-1，以及麻理工学院 Ronald Rivest 发明的算法 MD5。这两种算法都以巧妙的方式打乱消息的位。关于这些算法的细节，请参考 William Stallings 写的*密码学与网络安全，第五版》（Prentice Hall, 2011）。然而，在两种算法中都发现了细微的规律性，NIST 建议切换到更强的替代方案，如 SHA-256、SHA-384 或 SHA-512。

Java 编程语言实现了 MD5、SHA-1、SHA-256、SHA-384 和 SHA-512。`MessageDigest` 类是创建对象的工厂。它有一个静态方法 `getInstance`，返回一个类的对象。这意味着 `MessageDigest` 承担了双重职责：

- 作为工厂
- 作为所有算法的父类

例如，以下是获取可以计算 SHA-1 的对象的方法：

```java
MessageDigest alg = MessageDigest.getInstance("SHA-1");
```

要获取可以计算 MD5 的对象，请使用字符串 `"MD5"` 作为 `getInstance` 的参数。在获得一个 `MessageDigest` 对象后，通过重复调用 `update` 方法，将消息中的所有字节输入其中。例如，以下代码将文件中的所有字节传递给 `alg` 对象：

完成后，调用 `digest` 方法。该方法根据算法的要求对输入进行填充，执行计算，并将摘要作为数组返回。

```java
byte[] hash = alg.digest();
```

`Listing 9.16` 中的程序使用 MD5、SHA-1、SHA-256、SHA-384 或 SHA-512 计算消息摘要。以如下方式运行：

```bash
java hash.Digest hash/input.txt MD5
```

---

#### Listing 9.16 `Digest.java`

```java
package hash;

import java.io.*;
import java.nio.file.*;
import java.security.*;

/**
 * 此程序计算文件的消息摘要。
 * @version 1.20 2012-06-16
 * @author Cay Horstmann
 */
public class Digest
{
    /**
     * @param args args[0] 是文件名，args[1] 是可选的算法
     * (SHA-1, SHA-256, 或 MD5)
     */
    public static void main(String[] args) throws IOException, GeneralSecurityException
    {
        String algname = args.length >= 2 ? args[1] : "SHA-1";
        MessageDigest alg = MessageDigest.getInstance(algname);
}
```

```java
byte[] input = Files.readAllBytes(Paths.get(args[0]));
byte[] hash = alg.digest(input);
String d = "";
for (int i = 0; i < hash.length; i++)
{
    int v = hash[i] & 0xFF;
    if (v < 16) d += "0";
    d += Integer.toString(v, 16).toUpperCase() + " ";
}
System.out.println(d);
```

### `java.security.MessageDigest` 1.1

- `static MessageDigest getInstance(String algorithmName)`

  返回一个实现指定算法的 `MessageDigest` 对象。如果未提供算法，则抛出 `NoSuchAlgorithmException`。

- `void update(byte input)`
- `void update(byte[] input)`
- `void update(byte[] input, int offset, int len)`

  使用指定的字节更新摘要。

- `byte[] digest()`

  完成哈希计算，返回计算出的摘要，并重置算法对象。

- `void reset()`

  重置摘要。

### 9.4.2 消息签名

在上一节中，你学习了如何计算消息摘要——即原始消息的“指纹”。如果消息被篡改，修改后消息的指纹将与原始消息的指纹不匹配。如果消息和指纹分开传送，接收者可以检查消息是否被篡改。然而，如果消息和指纹都被截获，那么修改消息并重新计算指纹是一件很容易的事。毕竟，消息摘要算法是公开的，它们不需要密钥密钥。在这种情况下，伪造消息和重新计算指纹的接收者将永远不知道消息已被篡改过。数字签名解决了这个问题。

为了帮助你理解数字签名的工作原理，我们将解释`公钥密码学`领域中的几个概念。公钥密码学基于`public`（公）密钥和`private`（私）密钥的概念。其核心思想是向世界上所有人公布你的公钥。但是，只有你持有私钥，保护好它且不泄露给其他人至关重要。密钥之间通过数学关系进行匹配，尽管这些关系的具体性质对我们来说并不重要。（如果你感兴趣，可以在`www.cacr.math.uwaterloo.ca/hac`查阅《应用密码学手册》。）

密钥非常长且复杂。例如，这里是一对匹配的数字签名算法（DSA）公钥和私钥。

公钥：

点击此处查看代码图像。

`p: fca682ce8e12caba26efccf7110e526db078b05edecbcd1eb4a208f3ae1617ae01f35b91a47e6df63413c5e12ed089`

`9bcd132acd50d99151bdc43ee737592e17`

`q: 962eddcc369cba8ebb260ee6b6a126d9346e38c5`

`g: 678471b27a9cf44ee91a49c5147db1a9aaf244f05a434d6486931d2d14271b9e35030b71fd73da179069b32e293563`

`0e1c2062354d0da20a6c416e50be794ca4`

`y: c0b6e67b4ac098eb1a32c5f8c4c1f0e7e6fb9d832532e27d0bdab9ca2d2a8123ce5a8018b8161a760480fadd040b92`

`7281ddb22cb9bc4df596d7de4d1b977d50`

私钥：

点击此处查看代码图像。

`p: fca682ce8e12caba26efccf7110e526db078b05edecbcd1eb4a208f3ae1617ae01f35b91a47e6df63413c5e12ed089`

`9bcd132acd50d99151bdc43ee737592e17`

`q: 962eddcc369cba8ebb260ee6b6a126d9346e38c5`

`g: 678471b27a9cf44ee91a49c5147db1a9aaf244f05a434d6486931d2d14271b9e35030b71fd73da179069b32e293563`

### 9.4.3 验证签名

JDK 自带 `keytool`，这是一个用于证书和公私钥对的数据库。密钥库中的每个条目都有一个 `alias`（别名）。以下是 Alice 如何创建 `alice.certs` 密钥库并生成别名为 `alice` 的密钥：

```bash
keytool -genkeypair -keystore alice.certs -alias alice
```

在创建或打开密钥库时，会提示输入密钥库密码。对于本示例，只需使用 `secret`。如果你要在任何正式用途中使用 `keytool` 生成的密钥库，你需要选择良好的密码并保护好该文件。

生成密钥时，会提示以下信息：

```
Enter keystore password: secret
Reenter new password: secret
What is your first and last name? Alice Lee
What is the name of your organizational unit? Engineering
What is the name of your organization? ACME Software
What is the name of your City or Locality? San Francisco
What is the name of your State or Province? CA
What is the two-letter country code for this unit? US
Is <CN=Alice Lee, OU=Engineering, O=ACME Software, L=San Francisco, ST=CA, C=US> correct? yes
```

`keytool` 使用 X.500 格式名称，其组件包括通用名称（CN）、组织单元（OU）、组织（O）、位置（L）、州/省（ST）和国家（C），来识别密钥所有者和证书颁发者。

假设 Alice 想将她的公钥发送给 Bob。她需要导出证书文件：

点击此处查看代码图片。

```bash
keytool -exportcert -keystore alice.certs -alias alice -file alice.cer
```

现在 Alice 可以将证书发送给 Bob。当 Bob 收到证书时，可以打印它：

点击此处查看代码图片。

```bash
keytool -printcert -file alice.cer
```

打印结果如下：



点击此处查看代码图片

```text
Owner: CN=Alice Lee, OU=Engineering, O=ACME Software, L=San Francisco, ST=CA, C=US
Issuer: CN=Alice Lee, OU=Engineering, O=ACME Software, L=San Francisco, ST=CA, C=US
Serial number: 470835ce
Valid from: Sat Oct 06 18:26:38 PDT 2007 until: Fri Jan 04 17:26:38 PST 2008
Certificate fingerprints:
    MD5:  BC:18:15:27:85:69:48:B1:5A:C3:0B:1C:C6:11:B7:81
    SHA1: 31:0A:A0:B8:C2:8B:3B:B6:85:7C:EF:C0:57:E5:94:95:61:47:6D:34
Signature algorithm name: SHA1withDSA
Version: 3
```

如果 Bob 想检查他获取的是正确的证书，可以打电话给 Alice，并在电话中验证证书指纹。

---

![Image](img/00002.jpeg)

注意某些证书颁发机构会在网站上发布证书指纹。例如，要检查`jre/lib/security/cacerts`目录密钥库中的 VeriSign 证书，请使用`-list`选项：

点击此处查看代码图片

```bash
keytool -list -v -keystore jre/lib/security/cacerts
```

该密钥库的密码为`changeit`。该密钥库中的一个证书是：

点击此处查看代码图片

```text
Owner: OU=VeriSign Trust Network, OU="(c) 1998 VeriSign, Inc. - For authorized use only",
OU=Class 1 Public Primary Certification Authority - G2, O="VeriSign, Inc.", C=US
Issuer: OU=VeriSign Trust Network, OU="(c) 1998 VeriSign, Inc. - For authorized use only", OU=Class 1 Public Primary Certification Authority - G2, O="VeriSign, Inc.", C=US
Serial number: 4cc7eaaa983e71d39310f83d3a899192
Valid from: Sun May 17 17:00:00 PDT 1998 until: Tue Aug 01 16:59:59 PDT 2028
Certificate fingerprints:
    MD5:  DB:23:3D:F9:69:FA:4B:B9:95:80:44:73:5E:7D:41:83
    SHA1: 27:3E:E1:24:57:FD:C4:F9:0C:55:E8:2B:56:16:7F:62:F5:32:E5:47
```

你可以通过访问网站`www.verisign.com/repository/root.html`来检查你的证书是否有效。

---

一旦 Bob 信任了该证书，就可以将其导入他的密钥库。

点击此处查看代码图片

```bash
keytool -importcert -keystore bob.certs -alias alice -file alice.cer
```

---

![Image](img/00004.jpeg)

注意：永远不要将你不完全信任的证书导入密钥库。一旦证书被添加到密钥库，任何使用该密钥库的程序都会认为该证书可以用于验证签名。

现在 Alice 可以向 Bob 发送签名文档了。`jarsigner`工具用于签名和验证 JAR 文件。Alice 只需将需要签名的文档放入 JAR 文件中。

点击此处查看代码图片

```bash
jarsigner -keystore bob.certs -alias alice -file alice.cer
```

## 9.4 身份验证问题

确定发送者身份的问题被称为*身份验证问题*。

解决此问题的常用方法非常简单。假设陌生人和你有一个都信任的共同熟人。假设陌生人面见了你的熟人，并交了一个包含公钥的磁盘。你的熟人随后与你见面，向你保证该陌生人确实在那家知名公司工作，然后把磁盘给你。这样，你的熟人就为该陌生人的真实性提供了背书。

事实上，你的熟人并不需要和你见面。相反，他可以使用他的私钥对陌生人的公钥进行签名（见图 9.13）。当你获得公钥文件时，验证你朋友的签名，因为你信任他，所以确信他在签名之前检查了陌生人的凭证。

然而，你们可能并没有共同的熟人。某些信任模型假设存在一条“信任链”——一条相互熟人的链——因此你信任该链中的每一个成员。但在实践中，这并不总是如此。你可能信任你的朋友 Alice，你知道 Alice 信任 Bob，但你不认识 Bob，也不确定是否信任他。其他信任模型假设存在一个仁慈的大哥——一家所有人都信任的公司。这类公司中最著名的是 VeriSign, Inc.（`www.verisign.com`）。

然而，你应对实际正在认证的内容保持理性的预期。VeriSign 的首席执行官在认证公钥时，并不会亲自面见每一位个人或公司代表。你只需填写网页表单并支付一小笔费用，即可获得“1 级”ID。密钥将发送到证书中包含的电子邮件地址上。因此，你可以合理地认为该电子邮件地址是真实的，但请求者可能填写了`any`姓名和组织。还有更严格的 ID 级别。例如，对于“3 级”ID，VeriSign 将要求个人请求者出现在公证员面前，并且它会检查企业请求者的财务评级。其他身份验证者会有不同的流程。因此，当你收到一条经过认证的消息时，理解实际上到底认证了什么是非常重要的。

### 9.4.5 证书签名

在第 9.4.3 节的“验证签名”中（见于第 553 页），你看到了 Alice 如何使用自签名证书将公钥分发给 Bob。然而，Bob 需要通过与 Alice 比对指纹来确保该证书的有效性。

假设 Alice 想给她的同事 Cindy 发送一条签名消息，但 Cindy 不想费精力验证大量的签名指纹。现在假设有一个 Cindy 信任的用于验证签名的实体。在这个例子中，Cindy 信任 ACME 公司的信息资源部门。

该部门运行着一个*证书权威*（CA）。ACME 的每个人的密钥库中都有 CA 的公钥，这些公钥是由系统管理员仔细检查过密钥指纹后安装的。CA 对 ACME 员工的密钥进行签名。当他们安装彼此的密钥时，密钥库将隐式地信任这些密钥，因为它们是由受信任的密钥签名的。

以下是你可以模拟这一过程的方法。创建一个密钥库`acmesoft.certs`。生成一个密钥对并导出公钥：

点击此处查看代码图像

```bash
keytool -genkeypair -keystore acmesoft.certs -alias acmeroot
keytool -exportcert -keystore acmesoft.certs -alias acmeroot -file acmeroot.cer
```

公钥被导出到一个“自签名”证书中。然后将其添加到每位员工的密钥库中。

点击此处查看代码图像

```bash
keytool -importcert -keystore cindy.certs -alias acmeroot -file acmeroot.cer
```

为了让 Alice 能向 Cindy 以及 ACME 公司的其他所有人发送消息，她需要将证书带到信息资源部门并进行签名。遗憾的是，`keytool`程序缺少这一功能。在本书的配套代码中，我们提供了一个`CertificateSigner`类来填补这一空白。ACME 公司的授权工作人员将按照如下方式验证 Alice 的身份并生成带签名的证书：

点击此处查看代码图像

```bash
java CertificateSigner -keystore acmesoft.certs -alias acmeroot -infile alice.cer -outfile alice_signedby_acmeroot.cer
```

证书签名程序必须能够访问 ACME 公司的密钥库，且工作人员必须知道密钥库密码。显然，这是一项敏感操作。

Alice 将`alice_signedby_acmeroot.cer`文件交给 Cindy 以及 ACME 公司的其他任何人。或者，ACME 公司也可以简单地将该文件存储在公司目录中。记住，此文件包含了 Alice 的公钥，以及 ACME 公司对该密钥确实属于 Alice 的断言。

现在，Cindy 将带签名的证书导入她的密钥库中：

点击此处查看代码图像

```bash
keytool -importcert -keystore cindy.certs -alias alice -file alice_signedby_acmeroot.cer
```

密钥库验证了该密钥是由密钥库中已存在的信任根密钥签名的。Cindy*并不*被要求验证证书指纹。

一旦 Cindy 添加了根证书以及经常向她发送文档的人的证书，她再也不需要担心密钥库了。

### 9.4.6 证书请求

在前面的章节中，我们用密钥库和`CertificateSigner`工具模拟了 CA。然而，大多数 CA 运行更复杂的软件来管理证书，并且它们使用略有不同的证书格式。本节展示了与这些软件包进行交互所需的额外步骤。

我们将使用 OpenSSL 软件包作为示例。该软件预装在许多 Linux 系统和 Mac OS X 上，也提供了 Cygwin 移植版。你也可以在`www.openssl.org`下载该软件。

要创建一个 CA，请运行`CA`脚本。具体位置取决于你的操作系统。在 Ubuntu 上，运行：

```bash
/usr/lib/ssl/misc/CA.pl -newca
```

该脚本会在当前目录下创建一个名为`demoCA`的子目录。该目录包含一个根密钥对以及用于证书和证书吊销列表的存储空间。

你想要将公钥导入所有员工的 Java 密钥库中，但它是 PEM（隐私增强邮件）格式，而不是密钥库轻松接受的 DER 格式。将`demoCA/cacert.pem`复制为`acmeroot.pem`并用文本编辑器打开。删除`-----BEGIN CERTIFICATE-----`之前和`-----END CERTIFICATE-----`之后的内容。

现在你可以按通常方式将`acmeroot.pem`导入密钥库：

点击此处查看代码图像

```bash
keytool -importcert -keystore cindy.certs -alias alice -file acmeroot.pem
```

`keytool`本身无法执行此操作似乎非常不可思议。

要对 Alice 的公钥签名，首先要生成一个 PEM 格式证书请求：

点击此处查看代码图像

```bash
keytool -certreq -keystore alice.store -alias alice -file alice.pem
```

要对证书签名，运行：

点击此处查看代码图像

```bash
openssl ca -in alice.pem -out alice_signedby_acmeroot.pem
```

如之前一样，从`alice_signedby_acmeroot.pem`中切出`BEGIN CERTIFICATE`和`END CERTIFICATE`标记之外的内容。然后将其导入密钥库：

点击此处查看代码图像

```bash
keytool -importcert -keystore cindy.certs -alias alice -file alice_signedby_acmeroot.cer
```

你可以使用相同的步骤让 VeriSign 等公共证书权威机构对证书签名。

### 9.4.7 代码签名

认证技术的一个常见用途是对可执行程序签名。当你下载一个程序时，自然会担心它可能造成的损害。例如，该程序可能被病毒感染了。如果你知道代码的来源，并且知道它自离开源地以来未被篡改过，你的安全感会高得多。

在本节中，我们将向你如何对 JAR 文件进行签名，以及如何配置 Java 验证签名。此功能是为 Java 插件设计的，它是 applet 和 Java Web Start 应用程序的启动点。这些不再是常用技术，但你可能仍需要在旧产品中支持它们。

当 Java 最初发布时，applet 在加载后立即运行在“沙箱”中，具有有限权限。如果用户想使用可以访问本地文件系统、建立网络连接等的 applet，他们必须明确同意。为了确保 applet 代码在传输过程中未被篡改，必须对其进行数字签名。

这是一个具体的示例。假设你在浏览互联网时，遇到了一个网站，它提供运行一个来自未知供应商的小程序（applet），前提是你授予它相应的权限（参见图 9.14）。该程序由 Java 运行时信任的证书颁发机构颁发的`software developer`证书签名。弹出对话框会识别出软件开发者和证书颁发者。现在，你需要决定是否授权该程序。

![Image](img/00160.jpeg)

**图 9.14** 启动已签名的 applet

你掌握哪些可能影响决策的事实？以下是你已知的信息：

- Thawte 向该软件开发者出售了一份证书。
- 程序确实是用该证书签名的，并且在传输过程中没有被修改过。
- 证书确实是由 Thawte 签名的——它通过本地`cacerts`文件中的公钥进行了验证。

这能告诉你代码是否安全可以运行吗？如果你只知道供应商名称以及 Thawte 向他们出售了软件开发者证书这一事实，你还能信任该供应商吗？人们倾向于认为 Thawte 至少付了努力来确保 ChemAxon Kft. 并不是一个彻底的破解者。然而，没有任何证书颁发机构会对软件供应商的诚实和能力进行全面的审计。他们仅仅验证身份，通常是通过检查营业执照或护照的扫描件来实现。

如你所见，这不是一个满意的解决方案。更好的方法可能是扩展沙箱的功能。当 Java Web Start 技术首次发布时，它超出了沙箱范围，允许用户同意限制的文件和打印机访问。然而，那个概念从未得到进一步开发。相反，发生了相反。当沙箱受到黑客攻击时，Oracle 发现跟上形势太困难，因此完全取消了对未签名 applet 的支持。

如今，applet 已经非常罕见，主要用于遗留目的。如果你需要支持向公众提供的 applet，请使用 Java 运行时环境信任的供应商提供的证书对其签名。

对于内网应用，可以做得更好。可以在本地机器上安装策略文件和证书，这样从受信任源启动代码时不需要用户交互。每当 Java 插件工具加载签名代码时，它都会查询策略文件获取权限，并查询密钥库获取签名。

在本节的剩余部分中，我们将描述如何构建策略文件，以向已知来源的代码授予特定权限。构建和部署这些策略文件并不是为普通用户设计的。然而，系统管理员可以在分发内网程序的准备阶段执行这些任务。

假设 ACME 公司希望员工运行某些需要本地文件访问的程序，并且它希望通过浏览器以 applet 或 Web Start 应用的形式部署这些程序。

正如你在本章前面的部分看到的，ACME 可以通过代码库来识别程序。但这意味着每当程序移动到不同的 Web 服务器时，ACME 都需要更新策略文件。相反，ACME 决定对包含程序代码的 JAR 文件进行`sign`。

首先，ACME 生成一个根证书：

点击此处查看代码图像

```bash
keytool -genkeypair -keystore acmesoft.certs -alias acmeroot
```

当然，包含私根密钥的密钥库必须保存在安全的地方。因此，我们为公钥证书创建了第二个密钥库`client.certs`，并将公钥`acmeroot`证书添加到其中。

点击此处查看代码图像

```bash
keytool -exportcert -keystore acmesoft.certs -alias acmeroot -file acmeroot.cer
keytool -importcert -keystore client.certs -alias acmeroot -file acmeroot.cer
```

要制作已签名的 JAR 文件，程序员按照通常方式将他们的类文件添加到 JAR 文件中。例如：

```bash
javac FileReadApplet.java
jar cvf FileReadApplet.jar *.class
```

然后，ACME 的一名受信任人员运行`jarsigner`工具，指定 JAR 文件和私钥的别名：

```bash
jarsigner -keystore acmesoft.certs FileReadApplet.jar acmeroot
```

已签名的 applet 现在已准备好部署到 Web 服务器上。

接下来，让我们转向客户端机器配置。必须向每个客户端机器分发策略文件。

引用密钥库时，策略文件以以下行开头：

```java
keystore "keystoreURL", "keystoreType";
```

URL 可以是绝对的也可以是相对的。相对 URL 相对于策略文件的位置。如果密钥库是由`keytool`生成的，类型为`JKS`。例如：

```java
keystore "client.certs", "JKS";
```

然后`grant`子句可以带有后缀`signedBy`，例如：

由 Thawte 签名的`grant`子句：

```java
signedBy "Thawte";
```

已签名的 applet 现在已准备好部署到 Web 服务器上。



重启浏览器并加载 `FileReadApplet.html`。你不应该被提示要求接受任何证书。检查你是否可以从 `/etc` 目录以及加载 applet 的目录加载任何文件，但不能从其他目录加载。

完成后，请记住清理你的 `deploydir/security` 目录。删除 `java.policy` 和 `client.certs` 文件。重启浏览器。如果你在清理后再次加载 applet，你将不再能够从本地文件系统读取文件。相反，系统将提示你提供证书。我们将在下一节讨论安全证书。

---

![Image](img/00003.jpeg)

**提示：**

关于配置客户端 Java 安全的更多细节，请参阅《Java Rich Internet Applications Guide》，地址为 `http://docs.oracle.com/javase/8/docs/technotes/guides/jweb/index.html`。

---

### 列表 9.17：`signed/FileReadApplet.java`

点击此处查看代码图片

```java
package signed;

import java.awt.*;
import java.awt.event.*;
import java.io.*;
import java.nio.file.*;
import javax.swing.*;

/**
 * 这个 applet 可以在“沙箱之外”运行并在获得相应权限
 * 时读取本地文件。
 * @version 1.13 2016-05-10
 * @author Cay Horstmann
 */
public class FileReadApplet extends JApplet
{
    private JTextField fileNameField;
    private JTextArea fileText;

    public void init()
    {
        EventQueue.invokeLater(() ->
            {
            fileNameField = new JTextField(20);
            JPanel panel = new JPanel();
            panel.add(new JLabel("File name:"));
            panel.add(fileNameField);
            JButton openButton = new JButton("Open");
            panel.add(openButton);
            ActionListener listener = event -> loadFile(fileNameField.getText());
            fileNameField.addActionListener(listener);
            openButton.addActionListener(listener);
            add(panel, "North");
            fileText = new JTextArea();
            add(new JScrollPane(fileText), "Center");
        });
    }

    /**
     * 将文件内容加载到文本区域中。
     * @param filename 文件名
     */
    public void loadFile(String filename)
    {
        fileText.setText("");
        try
        {
            fileText.append(new String(Files.readAllBytes(Paths.get(filename))));
        }
        catch (IOException ex)
        {
            fileText.append(ex + "\n");
        }
        catch (SecurityException ex)
        {
            fileText.append("I am sorry, but I cannot do that.\n");
            fileText.append(ex + "\n");
            ex.printStackTrace();
        }
    }
}
```

## 9.5 加密

到目前，我们讨论了 Java 安全中实现的一种重要加密技术——即通过数字签名进行身份验证。安全的另一个重要方面是加密。即使经过了身份验证，信息本身也是可见的。数字签名仅仅验证信息没有被更改。相比之下，当信息被加密时，它是不可见的。它只能通过匹配的密钥进行解密。

对于代码签名来说，身份验证已经足够了——不需要隐藏代码。然而，当 applet 或应用程序传输机密信息（如信用卡号和个人数据）时，加密是必要的。过去，专利和出口控制限制了许多公司提供强加密。幸运的是，现在的出口控制已宽松得多，而且重要算法的专利已经过期了。如今，Java SE 作为标准库的一部分提供了极佳的加密支持。

### 9.5.1 对称密码

Java 加密扩展包含一个 `Cipher` 类，它是所有加密算法的父类。要获取加密对象，请调用 `getInstance` 方法：

```java
Cipher cipher = Cipher.getInstance(algorithm);
```

或者：

```java
Cipher cipher = Cipher.getInstance(algorithm, provider);
```

JDK 自带了一个名为 `SunJCE` 的提供者加密。如果你不指定其他提供者，它是默认提供者。如果你需要 Oracle 不支持的特殊算法，可能需要另一个提供者。算法名称是一个类似于 `"AES"` 或 `"DES/CBC/PKCS5Padding"` 的字符串。

数据加密标准（DES）是一种古老的分组密码，密钥长度为 56 位。如今，DES 算法被认为是过时的，因为可以通过暴力破解来破解它。更好的替代方案是它的继任者高级加密标准（AES）。请查看 `www.src.nist.gov/publications/fips/fips-197.pdf` 以获取 AES 算法的详细描述。我们在示例中使用 AES。

一旦你有了加密对象，就可以通过设置模式和密钥来初始化它：

```java
int mode = ...;
cipher.init(mode, key);
```

模式是 `ENCRYPT_MODE`、`DECRYPT_MODE`、`WRAP_MODE`、`UNWRAP_MODE` 之一。封装和解封装模式加密一个密钥——参见下一节的示例。

现在你可以反复调用 `update` 方法来加密数据块：

```java
int blockSize = cipher.getBlockSize();
byte[] inBytes = new byte[blockSize];
int outputSize = cipher.getOutputSize(blockSize);
byte[] outBytes = new byte[outputSize];
int outLength = cipher.update(inBytes, 0, outputSize, outBytes);
```

完成后，你必须调用一次 `doFinal` 方法。如果存在最后的输入数据块（字节数少于 `blockSize`），则调用：

```java
outBytes = cipher.doFinal(inBytes, 0, inLength);
```

如果所有输入数据都已加密，则调用：

```java
outBytes = cipher.doFinal();
```

调用 `doFinal` 是为了对最后一个数据块进行填充。考虑 DES 加密算法。它的分组大小为八字节。假设输入数据的最后一个块少于八字节。当然，我们可以用 `0` 填充剩余的字节，以获得一个八字节的最后一个块并对其进行加密。但当数据块被解密时，结果将在末尾附加几个 `0` 字节，因此与原始输入文件略有不同。

为了避免这个问题，我们需要一种填充方案。常用的填充方案是 RSA Security, Inc. 在公钥加密标准（PKCS）#5 中描述的方案（[`tools.ietf.org/html/rfc2898`](https://tools.ietf.org/html/rfc2898)）。

在这种方案中，最后一个块不是使用零填充，而是使用一个等于填充字节数的填充值填充。也就是说，如果 `L` 是最后一个（不完整的）块，其填充方式如下：

| length(L) | 填充值 |
| :--- | :--- |
| 7 | `01` |
| 6 | `02` |
| 5 | `03` |
| 4 | `04` |
| 3 | `05` |
| 2 | `06` |
| 1 | `07` |

最后，如果输入的长度实际上能被 8 整除，则添加一个块的 `08 08 08 08 08 08 08 08`。

被添加到输入中并进行加密。解密后，明文的最后一个字节是需要丢弃的填充字符计数。

## 9.5.2 密钥生成

要进行加密，你需要生成密钥。每种加密算法的密钥格式都不同，你需要确保密钥生成是随机的。按照以下步骤操作：

1. 为你的算法获取一个 `KeyGenerator`。
2. 使用随机源初始化生成器。如果加密算法的块长度是可变的，还要指定所需的块长度。
3. 调用 `generateKey` 方法。

例如，这里是生成 AES 密钥的方法：

点击此处查看代码图片

```java
KeyGenerator keygen = KeyGenerator.getInstance("AES");
SecureRandom random = new SecureRandom(); // 见下文
keygen.init(random);
Key key = keygen.generateKey();
```

或者，你可以从一组固定的原始数据（可能派自密码或击键计时）产生密钥。像如下所示构造 `SecretKeySpec`（它实现了 `SecretKey` 接口）：

点击此处查看代码图片

```java
byte[] keyData = . . .; // AES 使用 16 字节
SecretKey key = new SecretKeySpec(keyData, "AES");
```

生成密钥时，请确保使用 `truly random`（真正随机）数字。例如，`Random` 类中由当前日期和时间种子的随机数生成器并不足够随机。假设计算机钟精确到 1/10 秒。那么每天最多有 864,000 个种子。如果攻击者知道密钥发放的日期（通常可以从消息日期或证书过期日期推断出来），生成该日期所有可能的种子是非常容易的。

`SecureRandom` 类生成的随机数比 `Random` 类产生的要安全得多。你仍然需要提供一个种子来让数字序列从一个随机位置开始。实现此点的最佳方法是从硬件设备（如白噪声生成器）获取随机输入。另一个合理的随机输入源是让用户在键盘上漫无目的地敲击，每次击键仅为随机种子贡献一或两个比特。一旦你在字节数组中收集了这些随机比特，就将其传递给 `setSeed` 方法：

点击此处查看代码图片

```java
SecureRandom secrand = new SecureRandom();
byte[] b = new byte[20];
// 填充真正的随机比特
secrand.setSeed(b);
```

如果你不为随机数生成器加密，它将通过启动线程、让其睡眠并测量它们唤醒的精确时间来计算自己的 20 字节种子。

---

![Image](img/00002.jpeg)

**注意**

该算法被认为 `not`（不）安全。过去，依赖计算机某些组件（如硬盘访问时间）计时的算法被证明不是完全随机的。

本节末尾的示例程序实现了 AES 加密工作（参见列表 9.18）。列表 9.19 中的 `crypt` 工具方法将在其他示例中重用。要使用该程序，你首先需要生成一个秘密密钥。运行：

点击此处查看代码图片

```bash
java aes.AESTest -genkey secret.key
```

秘密密钥保存在 `secret.key` 文件中。

现在你可以使用命令进行加密：

点击此处查看代码图片

```bash
java aes.AESTest -encrypt plaintextFile encryptedFile secret.key
```

使用命令进行解密：

点击此处查看代码图片

```bash
java aes.AESTest -decrypt encryptedFile decryptedFile secret.key
```

程序非常直观。`-genkey` 选项产生一个新的秘密密钥并将其序列化到给定文件中。该操作需要很长时间，因为安全随机生成器的初始化是非常耗时的。`-encrypt` 和 `-decrypt` 选项都调用了同一个 `crypt` 方法，该方法调用了加密算法的 `update` 和 `doFinal` 方法。

注意，只要输入块是完整的长度，就会调用 `update` 方法，而 `doFinal` 方法要么带有部分输入块调用（然后进行填充），要么在没有额外数据的情况下调用（生成一个填充块）。

### 列表 9.18：`aes/AESTest.java`

点击此处查看代码图片

```java
package aes;

import java.io.*;
import java.security.*;
import javax.crypto.*;

/**
 * 此程序测试 AES 加密。用法：
 * java aes.AESTest -genkey keyfile
 * java aes.AESTest -encrypt plaintextFile encryptedFile
 * java aes.AESTest -decrypt encryptedFile decryptedFile
 * @author Cay Horstmann
 * @version 1.0-06-10
 */
public class AESTest {
    public static void main(String[] args)
            throws IOException, SecurityException, ClassNotFoundException {
        if (args[0].equals("-genkey")) {
            KeyGenerator keygen = KeyGenerator.getInstance("AES");
            SecureRandom random = new SecureRandom();
            keygen.init(random);
            Key key = keygen.generateKey();
            try (ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream(args[1]))) {
                out.writeObject(key);
            }
        } else {
            int mode;
            if (args[0].equals("-encrypt")) mode = Cipher.ENCRYPT_MODE;
            else mode = Cipher.DECRYPT_MODE;

            try (ObjectInputStream keyIn = new ObjectInputStream(new FileInputStream(args[3]));
                 InputStream in = new FileInputStream(args[1]);
                 OutputStream out = new FileOutputStream(args[2])) {
                Key key = (Key) keyIn.readObject();
                Cipher cipher = Cipher.getInstance("AES");
                cipher.init(mode, key);
                crypt(in, out);
            }
        }
    }
}
```

---

**列表 9.19：`aes/Util.java`**



```java
package aes;

import java.io.*;
import java.security.*;
import javax.crypto.*;

public class Util {
    /**
     * 使用加密算法转换输入流中的字节并将转换后的字节
     * 发送到输出流。
     * @param in 输入流
     * @param out 输出流
     * @param cipher 用于转换字节的加密算法
     */
    public static void crypt(InputStream in, OutputStream out, Cipher cipher)
            throws IOException, GeneralSecurityException {
        int blockSize = cipher.getBlockSize();
        int outputSize = cipher.getOutputSize(blockSize);
        byte[] inBytes = new byte[blockSize];
        byte[] outBytes = new byte[outputSize];
        int inLength = 0;
        boolean more = true;
        while (more) {
            inLength = in.read(inBytes);
            if (inLength == blockSize) {
                int outLength = cipher.update(inBytes, 0, blockSize, outBytes);
                out.write(outBytes, 0, outLength);
            } else {
                more = false;
            }
        }
        if (inLength > 0) outBytes = cipher.doFinal(inBytes, 0, inLength);
        else outBytes = cipher.doFinal();
        out.write(outBytes);
    }
}
```

返回一个实现指定算法的 `Cipher` 对象。如果未提供算法，则抛出 `NoSuchAlgorithmException`。

- `int getBlockSize()`

  返回加密块的大小（以字节为单位），如果加密器不是块加密器，则返回 `0`。

- `int getOutputSize(int inputLength)`

  返回如果下一个输入具有给定字节数，则所需的输出缓冲区大小。此方法考虑了加密器对象中任何缓冲的字节。

- `void init(int mode, Key key)`

  初始化加密算法对象。该模式为 `ENCRYPT_MODE`、`DECRYPT_MODE`、`WRAP_MODE` 或 `UNWRAP_MODE` 之一。

- `byte[] update(byte[] in)`

- `byte[] update(byte[] in, int offset, int length)`

- `int update(byte[] in, int offset, int length, byte[] out)`

  变换一块输入数据。前两个方法返回输出结果。第三个方法返回放入 `out` 中的字节数。

- `byte[] doFinal()`

- `byte[] doFinal(byte[] in)`

- `byte[] doFinal(byte[] in, int offset, int length)`

- `int doFinal(byte[] in, int offset, int length, byte[] out)`

  变换最后一块输入数据并刷新该算法对象的缓冲区。前三个方法返回输出结果。第四个方法返回放入 `out` 中的字节数。

### `javax.crypto.KeyGenerator` 1.4

- `static KeyGenerator getInstance(String algorithmName)`

  返回一个实现指定算法的 `KeyGenerator` 对象。如果未提供算法，则抛出 `NoSuchAlgorithmException`。

- `void init(SecureRandom random)`

- `void init(int keySize, SecureRandom random)`

  初始化密钥生成器。

- `SecretKey generateKey()`

  生成新密钥。

### `javax.crypto.spec.SecretKeySpec` 1.4

- `SecretKeySpec(byte[] key, String algorithmName)`

  构造一个密钥规范。

## 9.5.3 加密流（Cipher Streams）

JCE 库提供了一组方便的流类，可以自动对流数据进行加密或解密。例如，以下是加密数据加密到文件的方法：

点击此处查看代码图像

```java
Cipher cipher = . . .;
cipher.init(Cipher.ENCRYPT_MODE, key);
CipherOutputStream out = new CipherOutputStream(new FileOutputStream(outputFileName), cipher);
byte[] bytes = new byte[BLOCKSIZE];
int inLength = getData(bytes); // 从数据源获取数据
while (inLength != -1)
{
   out.write(bytes, 0, inLength);
   inLength = getData(bytes); // 从数据源获取更多数据
}
out.flush();
```

同样地，你可以使用 `CipherInputStream` 从文件中读取并解密数据：

点击此处查看代码图像

```java
Cipher cipher = . . .;
cipher.init(Cipher.DECRYPT_MODE, key);
CipherInputStream in = new CipherInputStream(new FileInputStream(inputFileName), cipher);
byte[] bytes = new byte[BLOCKSIZE];
int inLength = in.read(bytes);
while (inLength != -1)
{
   putData(bytes, inLength); // 将数据放入目的地
   inLength = in.read(bytes);
}
```

加密流类透明地处理了对 `update` 和 `doFinal` 的调用，这显然是一种便利方法。

### `javax.crypto.CipherInputStream` 1.4

- `CipherInputStream(InputStream in, Cipher cipher)`

  构造一个输入流，从 `in` 读取数据并使用给定的 `cipher` 对进行解密或加密。

- `int read()`

- `int read(byte[] b, int off, int len)`

  从输入流读取数据，这些数据会自动被解密或加密。

### `javax.crypto.CipherOutputStream` 1.4

- `CipherOutputStream(OutputStream out, Cipher cipher)`

  构造一个输出流，向 `out` 写入数据并使用给定的 `cipher` 对进行加密或解密。

- `void write(int ch)`

- `void write(byte[] b, int off, int len)`

  向输出流写入数据，这些数据会自动被加密或解密。

- `void flush()`

  刷新加密缓冲区并在必要时执行填充。

## 9.5.4 公钥加密算法（Public Key Ciphers）

你在上一节中看到的 AES 加密算法是一种对称加密。加密和解密使用同一个密钥。对称加密的致命喀斯底是密钥分发。如果 Alice 向 Bob 发送一个加密后的消息，Bob 需要与 Alice 使用相同的密钥。如果 Alice 更改了密钥，她需要向 Bob 发送消息，并且通过安全通道发送新密钥。但也许她没有到 Bob 的安全通道——这正是她起初要给他加密消息的原因。

公钥加密解决了这个问题。在公钥加密算法中，Bob 拥有一由公钥和匹配的私钥组成的密钥对。Bob 可以在任何发布公钥，但他必须严密保护私钥。Alice 只需要使用公钥加密她给 Bob 的消息即可。

实际上，事实并没有那么简单。所有知的公钥算法都比 `DES` 或 `AES` 等对称密钥算法慢得多。使用公钥算法来加密大量数据是不现实的。但是，可以通过以下方式解决这个问题：使用公钥算法来加密对称密钥：

1. Alice 生成一个对称密钥。
2. Alice 使用公钥加密她给 Bob 的消息。
3. Alice 将加密后的密钥发送给 Bob。
4. Bob 使用他的私钥解密对称密钥。

最常用的公钥算法是是由 Rivest、Shamir 和 Adleman 发明的 RSA。直到在 2000 年之前，该算法受专利保护（归属于 RSA 公司）。许可费用并不便宜——每年至少 50,000 美元。现在该算法已进入公共领域。使用公钥算法需要一对密钥。

```java
/**
 * java rsa.RSATest -encrypt plaintext encrypted public
 * java rsa.RSATest -decrypt encrypted decrypted private
 * @author Cay Horstmann
 * @version 1.01 2012-06-10
 */
public class RSATest
{
    private static final int KEYSIZE = 512;

    public static void main(String[] args)
            throws IOException, GeneralSecurityException, ClassNotFoundException
    {
        if (args[0].equals("-genkey"))
        {
            KeyPairGenerator pairgen = KeyPairGenerator.getInstance("RSA");
            SecureRandom random = new SecureRandom();
            pairgen.initialize(KEYSIZE, random);
            KeyPair keyPair = pairgen.generateKeyPair();
            try (ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream(args[1])))
            {
                out.writeObject(keyPair.getPublic());
            }
            try (ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream(args[2])))
            {
                out.writeObject(keyPair.getPrivate());
            }
        }
        else if (args[0].equals("-encrypt"))
        {
            KeyGenerator keygen = KeyGenerator.getInstance("AES");
            SecureRandom random = new SecureRandom();
            keygen.init(random);
            SecretKey key = keygen.generateKey();

            // wrap with RSA public key
            try (ObjectInputStream keyIn = new ObjectInputStream(new FileInputStream(args[3]));
                 DataOutputStream out = new DataOutputStream(new FileOutputStream(args[2]));
                 InputStream in = new FileInputStream(args[1]) )
            {
                Key publicKey = (Key) keyIn.readObject();
                Cipher cipher = Cipher.getInstance("RSA");
                cipher.init(Cipher.WRAP_MODE, publicKey);
                byte[] wrappedKey = cipher.wrap(key);
                out.writeInt(wrappedKey.length);
                out.write(wrappedKey);

                cipher = Cipher.getInstance("AES");
                cipher.init(Cipher.ENCRYPT_MODE, key);
                Util.crypt(in, out);
            }
        }
        else
        {
            try (DataInputStream in = new DataInputStream(new FileInputStream(args[1]));
                 ObjectInputStream keyIn = new ObjectInputStream(new FileInputStream(args[3]));
                 OutputStream out = new FileOutputStream(args[2]))
            {
                int length = in.readInt();
                byte[] wrappedKey = new byte[length];
                in.read(wrappedKey, 0, length);

                // unwrap with RSA private key
                Key privateKey = (Key) keyIn.readObject();
                Cipher cipher = Cipher.getInstance("RSA");
                cipher.init(Cipher.UNWRAP_MODE, privateKey);
                Key key = cipher.unwrap(wrappedKey, "AES", Cipher.SECRET_KEY);

                cipher = Cipher.getInstance("AES");
                cipher.init(Cipher.DECRYPT_MODE, key);
                Util.crypt(in, out);
            }
        }
    }
}
```

你现在已经看到了 Java 安全模型如何允许代码的受控执行，这是 Java 平台一个独特且日益重要的方面。你还看到了 Java 库提供的身份验证和加密服务。我们没有涵盖许多高级和专门的问题，其中：

- 用于“通用安全服务”的 `GSS-API`，它为 `Kerberos` 协议（以及原则上的其他安全消息交换协议）提供了支持。在 `http://docs.oracle.com/javase/7/docs/technotes/security/jgss/tutorials` 有一个教程。
- 对简单身份验证安全层（`SASL`）的支持，它被轻级目录访问协议（`LDAP`）和互联网消息访问协议（`IMAP`）使用。如果你需要在应用程序中实现 `SASL`，请查看 `http://docs.oracle.com/javase/7/docs/technotes/security/sasl/sasl-refguide.html`。
- 对 `SSL` 支持。在 `HTTP` 上使用 `SSL` 对应用程序程序员是透明的；只需使用以 `https` 开头的 URL 即可。如果你想为应用程序添加 `SSL`，请参考 Java 安全套接字扩展（JSSE）参考：`http://java.sun.com/javase/6/docs/technotes/security/jsse/JSSERefGuide.html`。

在下一章中，我们将深入探讨高级编程。



## 第 10 章：高级 Swing

### 本章内容

- 10.1 列表
- 10.2 表
- 10.3 树
- 10.4 文本组件
- 10.5 进度指示
- 10.6 组件组织器和装饰器

在本章中，我们将继续讨论第一卷中介绍的 Swing 用户界面工具包。Swing 是一个丰富的工具包，第一卷仅涵盖了基础和常用的组件。这为我们留下了三个复杂的组件：列表、表格和树，它们的探索占据了本章的大部分内容。然后我们将转向文本组件，超越你在第一卷中看到的简单文本字段和文本区域。我们将向你展示如何在文本字段中添加验证和计数器，以及你如何显示如 HTML 之类的结构化文本。接下来，你将看到若干用于显示活动进度的组件。我们将通过涵盖组织器（如标签页面板和桌面面板）来结束本章。

### 10.1 列表

如果你想向用户展示一组选择，而单选按钮组或复选框组占用了太多空间，你可以使用组合框或列表。组合框在第一卷中介绍过，因为它们很简单。`JList` 组件具有更多功能，其设计与树和表格组件相似。由于这个原因，它是我们复杂 Swing 组件的起点。你会发现列表在常用情况下使用有些笨拙，因为你需要操作一些使通用情况可能的机制。我们将引导你通过简单且最常用的情况——字符串列表框，然后给出一个更复杂的示例来展示列表的灵活性。

#### 10.1.1 `JList` 组件

`JList` 组件在单个框内显示多个项目。图 10.1 显示了一个相当荒唐的例子。用户可以选择狐狸的属性，例如“快速”、“棕色”、“饥饿”、“野性”，由于属性用完了，还有“静态”、“私有”和“最终”。这样就可以让`私有静态最终`狐狸跳过懒狗。

**图 10.1** 列表框

从 Java 7 开始，`JList` 是一个泛型。`type` 参数是用户可以选择的值的类型。在示例中，我们使用 `JList<String>`。

要构造此列表组件，从一个字符串数组开始，并将该数组传递给 `JList` 构造函数：

```java
String[] words= { "quick", "brown", "hungry", "wild", . . . };
JList<String> wordList = new JList<>(words);
```

列表框（List boxes）不会自动滚动。要让列表框滚动，你必须将其插入滚动面板（scroll pane）中：

点击此处查看代码图像

```java
JScrollPane scrollPane = new JScrollPane(wordList);
```

然后，将滚动面板而不是列表本身添加到周围的面板中。

我们不得不承认，列表显示与滚动机制的分离在理论上是优雅的，但在实践中却很痛苦。本质上，我们遇到的几乎所有列表都需要滚动。强迫程序员在默认情况下经历这些繁琐步骤，只为了让他们体会到这种优雅，这似乎是残忍的。

默认情况下，列表组件显示八项内容；使用 `setVisibleRowCount` 方法可以更改该值：

点击此处查看代码图像

```java
wordList.setVisibleRowCount(4); // 显示 4 项
```

你可以将`layout orientation`（布局方向）设置为三个值之一：

- `JList.VERTICAL`（默认）：将所有项目垂直排列。
- `JList.VERTICAL_WRAP`：如果项目多于可见行数，则开始新列（请参见图 10.2）。

![Image](img/00163.jpeg)

**图 10.2** 具有垂直和水平换行功能的列表

- `JList.HORIZONTAL_WRAP`：如果项目多于可见行数，则开始新列，但按水平填充。查看图 10.2 中“quick”、“brown”和“hungry”这些单词的布局，即可看到垂直换行和水平换行之间的区别。

默认情况下，用户可以选择多项。要向选择中添加更多项目，可以在点击每个项目时按住 `Ctrl` 键。要选择连续的项目范围，点击第一项，然后按住 `Shift` 键点击最后一项。

你还可以使用 `setSelectionMode` 方法将用户限制在更有限的选择模式下：

点击此处查看代码图像

```java
wordList.setSelectionMode(ListSelectionModel.SINGLE_SELECTION);
// 一次选择一个项目

wordList.setSelectionMode(ListSelectionModel.SINGLE_INTERVAL_SELECTION);
// 选择一个项目或一个项目范围
```

你可能记得第一卷中，基础用户界面组件在用户激活它们时会发送动作事件（action events）。列表框使用不同的通知机制。与其监听动作事件，你只需要监听列表选择事件（list selection events）。为列表组件添加列表选择监听器，并实现方法：

点击此处查看代码图像

```java
public void valueChanged(ListSelectionEvent evt)
```

在监听器中实现。

当用户选择项目时，会产生大量的列表选择事件。例如，假设用户点击了一个新项目。当鼠标按钮按下时，事件会报告选择的变化。这是一个过渡事件——如果选择尚未确定，调用 `event.getValueIsAdjusting()` 将返回 `true`。然后，当鼠标按钮释放时，会有另一个事件，此时 `getValueIsAdjusting` 返回 `false`。如果你对过渡事件感兴趣，可以等待 `getValueIsAdjusting` 为 `false` 的事件。然而，如果你想在鼠标按钮被点击时立即给用户提供反馈，则需要处理所有事件。

一旦你被通知事件已发生，你将想要找出当前选中了哪些项目。如果你的列表处于单选模式，调用 `getSelectedValue` 以列表元素类型获取值。否则，调用 `getSelectedValuesList` 方法，它会返回一个包含所有被选中项目的列表。你可以像通常一样处理它：

点击此处查看代码图像

```java
for (String value : wordList.getSelectedValuesList())
    // 对 value 进行某些操作
```

***

![Image](img/00002.jpeg)

> 注意
>
> 列表组件对鼠标的双击操作没有反应。正如 Swing 设计者预想的那样，你使用列表来选择一个项目，然后点击按钮执行某些操作。然而，某些界面允许用户双击列表项目，作为选择该项目并调用默认操作的快捷方式。如果你想实现这种行为，必须为列表框添加鼠标监听器，然后如下方式捕获鼠标事件：

点击此处查看代码图像

```java
public void mouseClicked(MouseEvent evt)
{
    if (evt.getClickCount() == 2)
    {
        JList source = (JList) evt.getSource();
        Object[] selection = source.getSelectedValuesList();
        doAction(selection);
    }
}
```

***

列表 10.1 是包含填充了字符串的列表框的框架列表。注意 `valueChanged` 方法如何从选中的项目中构建消息字符串。

**列表 10.1** `list/ListFrame.java`

点击此处查看代码图像

***

```java
package list;

import java.awt.*;

import javax.swing.*;

/**
 * 此框架包含一个单词列表和一个标签，显示由所选
 * 单词组成的句子。注意，你可以通过 Ctrl+点击和 Shift+点击来选择多个单词。
 */
class ListFrame extends JFrame
{
    private static int DEFAULT_WIDTH = 400;
    private static int DEFAULT_HEIGHT = 300;

    private JPanel listPanel;
    private JList<String> wordList;
    private JLabel label;
    private JPanel buttonPanel;
    private ButtonGroup group;
    private String prefix = "The ";
    private String suffix = " jumps over the dog.";

    public ListFrame()
    {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

        String[] words = { "quick", "brown", "hungry", "silent", "huge", "private", "abstract", "static", "final" };
        wordList = new JList<>(words);
        wordList.setVisibleRowCount(4);
        JScrollPane scrollPane = new JScrollPane(wordList);
        listPanel = new JPanel();
        listPanel.add(scrollPane);
        wordList.addSelectionListener(event -> {
            StringBuilder text = new StringBuilder(prefix);
            for (String value : wordList.getSelectedValuesList())
            {
                text.append(value);
                text.append(" ");
            }
            text.append(suffix);
            label.setText(text.toString());
        });

        buttonPanel = new JPanel();
        group = new ButtonGroup();
        makeButton("Vertical", JList.VERTICAL);
        makeButton("Vertical Wrap", JList.VERTICAL_WRAP);
        makeButton("Horizontal Wrap", JList.HORIZONTAL_WRAP);

        add(listPanel, BorderLayout.NORTH);
        label = new JLabel(prefix + suffix);
        add(label, BorderLayout.CENTER);
        add(buttonPanel, BorderLayout.SOUTH);
    }

    /**
     * 创建一个设置布局方向的单选按钮。
     * @param label 标签
     * @param orientation 列表的方向
     */
    private void makeButton(String label, final int orientation)
    {
        JRadioButton button = new JRadioButton(label);
        buttonPanel.add(button);
        if (group.getButtonCount() == 0) button.setSelected(true);
        group.add(button);
        button.addActionListener(event -> {
            wordList.setLayoutOrientation(orientation);
            listPanel.revalidate();
        });
    }
}
```

获取或设置列表中不显示滚动条的情况下显示的首选行数。

- `int getLayoutOrientation()` **1.4**
- `void setLayoutOrientation(int orientation)` **1.4**

获取或设置布局方向。

![Image](img/00164.jpeg)

- `int getSelectionMode()`
- `void setSelectionMode(int mode)`

获取或设置决定是否允许单项或多项选择的模式。

![Image](img/00165.jpeg)

- `void addListSelectionListener(ListSelectionListener listener)`

向列表添加一个监听器，每当选择发生变化时，该监听器都会收到通知。

- `List<E> getSelectedValuesList()` **7**

返回选中的值列表，如果选择为空则返回一个空列表。

- `E getSelectedValue()`

返回第一个选中的值，如果选择为空则返回 `null`。

***

`javax.swing.event.ListSelectionListener` **1.2**

- `void valueChanged(ListSelectionEvent e)`

当列表选择发生变化时调用此方法。

***

#### 10.1.2 List Models

在上一节中，你看到了使用列表组件的最常用方法：

1. 为列表显示指定一组固定的字符串集。
2. 将列表放置在滚动面板中。
3. 捕获列表选择事件。

在本节关于列表的剩余部分中，我们将涵盖需要更多技巧的复杂情况：

- 非常长的长的列表
- 内容不断变化的列表
- 不包含字符串的列表

在第一个示例中，我们构建了一个持有固定字符串集合的 `JList` 组件。然而，列表框中的选项集合并不总是固定的。我们该如何在列表框中添加或删除项目呢？令人惊讶的是，`JList` 类中没有实现此点的方法。相反，你必须更深入地了解列表组件的内部设计。该列表组件使用模型-视图-控制器（MVC）设计模式，将视觉外观（以某种方式渲染的项列）与底层数据（对象集合）分离开。

`JList` 类负责数据的视觉外观。它实际上对数据的如何存储一知之甚少——它只知道可以通过某个实现了 `ListModel` 接口的对象来检索数据：

点击此处查看代码图像

```java
public interface ListModel<E>
{
   int getSize();
   E getElementAt(int i);
   void addListDataListener(ListDataListener l);
   void removeListDataListener(ListDataListener l);
}
```

通过这个接口，`JList` 可以获取元素计数并检索其中任何元素。此外，`JList` 对象可以将自己作为 `ListDataListener` 添加。这样，如果元素集合发生变化，`JList` 就会收到通知以便重绘自己。

为什么这种通用性很有用？为什么 `JList` 对象不直接存储一个对象数组呢？

注意，接口并没有指定对象是如何存储的。特别是，它甚至没有强制它们被存储！`getElementAt` 方法可以在每次被调用时自由地重新计算每个值。如果你想显示一个巨大的集合而无需存储这些值，这可能是非常有用的。

这里有一个有点幼稚的示例：我们让用户在列表框中的所有三字母单词中进行选择（参见图 10.3）。

![Image](img/00166.jpeg)

**图 10.3** 从非常长的选择列表中进行选择

有 26 × 26 × 26 = 17,576 个三字母组合。与其存储所有这些组合，我们在用户滚动查看时按需重新计算它们。

事实证明实现起来非常容易。繁琐的部分（添加和移除监听器）已经由我们扩展的 `AbstractListModel` 类为我们完成了。我们只需要提供 `getSize` 和 `getElementAt` 方法：

点击此处查看代码图像

```java
class WordListModel extends AbstractListModel<String>
{
   public WordListModel(int n) { length = n; }
   public int getSize() { return (int) Math.pow(26, length); }
   public String getElementAt(int n)
   {
      // 计算第 n 个字符串
      . . .
   }
   . . .
}
```

第 n 个字符串的计算有点技术性——你将在清单 10.3 中找到细节。

现在我们有了模型，可以简单地构建一个列表，让用户滚动查看模型提供的元素：

点击此处查看代码图像

```java
JList<String> wordList = new JList<>(new WordListModel(3));
wordList.setSelectionMode(ListSelectionModel.SINGLE_SELECTION);
ScrollPane scrollPane = new JScrollPane(wordList);
```

点在于，这些字符串从未被存储。只有用户实际请求查看的字符串才会被生成。

我们必须进行另一个设置：告诉列表组件所有项的宽度高度。设置尺寸的最简单方法是指定单元格值：

点击此处查看代码图像

```java
PrototypeCellValue("www");
```



单元格值用于确定所有单元格的大小（在大多数字体中，“w”是最宽的字母）。或者，你可以设置固定的单元格大小：

点击此处查看代码图像

```java
wordList.setCellWidth(50);
wordList.setCellHeight(15);
```

如果不设置单元格值或固定单元格大小，列表组件将计算每个项的宽度高度。这可能花费很长时间。清单 10.2 显示了框架类。

从实际角度来看，非常长的列表很少用。让用户滚动浏览巨大的选择是非常痛苦的。因此，我们认为列表控件过度设计了。这种安排将节省程序员处理独立列表模型的痛苦。另一方面，`JList` 类与 `JTree` 和 `JTable` 类一致，这种通用性是有用的。

**清单 10.2** `longList/LongListFrame.java`

点击此处查看代码图像

```java
package longList;

import java.awt.*;
import javax.swing.*;

/**
 * 此框架包含一个长列表和一个由所选单词组成的标签。
 */
public class LongListFrame extends JFrame
{
   private JList<String> wordList;
   private JLabel label;
   private String prefix = "The quick brown ";
   private String suffix = " jumps over the lazy dog.";

   public LongListFrame()
   {
      wordList = new JList<String>(new WordListModel(3));
      wordList.setSelectionMode(ListSelectionModel.SINGLE_SELECTION);
      wordList.setPrototypeCellValue("www");
      ScrollPane scrollPane = new JScrollPane(wordList);

      JPanel p = new JPanel();
      p.add(scrollPane);
      wordList.addSelectionListener(event -> setSubject(wordList.getSelectedValue()));

      Container contentPane = getContentPane();
      contentPane.add(p, BorderLayout.NORTH);
      label = new JLabel(prefix + suffix);
      contentPane.add(label, BorderLayout.CENTER);
      setSubject("fox");
      pack();
   }

   /**
    * 设置标签中的主语。
    * @param word 跳过懒惰狗的新主语
    */
   public void setSubject(String word)
   {
      StringBuilder text = new StringBuilder(prefix);
      text.append(word);
      text.append(suffix);
      label.setText(text.toString());
   }
}
```

### 列表 10.3 `longList/WordListModel.java`

点击此处查看代码

```java
package longList;

import javax.swing.*;

/**
 * 一个动态生成 n 字母单词的模型。
 */
public class WordListModel extends AbstractListModel<String>
{
    private int length;
    public static final char FIRST = 'a';
    public static final char LAST = 'z';

    /**
     * 构造模型。
     * @param n 单词长度
     */
    public WordListModel(int n)
    {
        length = n;
    }

    public int getSize()
    {
        return (int) Math.pow(LAST - FIRST + 1, length);
    }

    public String getElementAt(int n)
    {
        StringBuilder r = new StringBuilder();

        for (int i = 0; i < length; i++)
        {
            char c = (char) (FIRST + n % (LAST - FIRST + 1));
            r.insert(0, c);
            n = n / (LAST - FIRST + 1);
        }
        return r.toString();
    }
}
```

### `javax.swing.JList<E>` 1.2

- `JList(ListModel<E> dataModel)`: 构建一个显示指定模型中元素的列表。

- `E getPrototypeCellValue()`

- `void setPrototypeCellValue(E newValue)`: 获取或设置原型单元格值，用于确定列表中每个单元格的宽度和高度。默认值为 `null`，这将强制测量每个单元格的大小。

- `void setFixedCellWidth(int width)`

- `void setFixedCellHeight(int height)`: 如果宽度或高度大于 0，则指定列表中每个单元格的宽度或高度（像素）。默认值为 `-1`，这将强制测量每个单元格的大小。

### `javax.swing.ListModel<E>` 1.2

- `int getSize()`: 返回模型的元素数量。

- `E getElementAt(int position)`: 返回模型中给定位置的元素。

### 10.1.3 插入和删除值

你不能直接编辑列表值的集合。相反，你必须访问*模型*，然后添加或删除元素。不过，这说起来做起来难。假设你想向列表添加更多值。你可以获取模型的引用：

点击此处查看代码

```java
ListModel<String> model = list.getModel();
```

但这对你没有用处——正如你在上一节中看到的，`ListModel` 接口没有插入或删除元素的方法，因为归根结底，列表模型的整个意义在于它不需要*存储*元素。

让我们尝试反过来这样做。`JList` 的构造构造函数之一接受一个对象向量：

点击此处查看代码

```java
Vector<String> values = new Vector<String>();
values.addElement("quick");
values.addElement("brown");
...
JList<String> list = new JList<>(values);
```

你现在可以编辑该向量并添加或删除元素，但列表并不知道这些正在发生，因此它无法对更改做出反应。特别是，列表不会更新它的视图。因此，这个构造函数是没用的。

相反，你应该构造一个 `DefaultListModel` 对象，用初始值填充它，并与列表关联。`DefaultListModel` 类实现了 `ListModel` 接口并管理对象集合。

点击此处查看代码

```java
DefaultListModel<String> model = new DefaultListModel<>();
model.addElement("quick");
model.addElement("brown");
...
JList<String> list = new JList<>(model);
```

现在你可以从 `model` 对象中添加或删除值。然后 `model` 对象会通知列表更改，列表随之进行重绘。

点击此处查看代码

```java
model.removeElement("quick");
model.addElement("slow");
```

由于历史原因，`DefaultListModel` 类使用的方法名与集合不同。在内部，默认列表模型使用向量来存储值。

![图像](img/00004.jpeg)

> **注意**
>
> 某些 `JList` 构造函数可以从对象数组或向量构建列表。你可能认为这些构造函数使用 `DefaultListModel` 来存储这些值。事实并非如此——这些构造函数构建了一个简单的模型，可以访问这些值，但没有任何通知机制。例如，这里是从 `Vector` 构建 `JList` 的构造函数代码：

点击此处查看代码

```java
public JList(final Vector<? extends E> listData)
{
    this (new AbstractListModel<E>()
    {
        public int getSize() { return listData.size(); }
        public E elementAt(int i) { return listData.elementAt(i); }
    });
}
```

这意味着，如果你在构造后更改向量的内容，列表可能会显示新旧混合的值，直到完全重绘。（前面的构造函数中的 `final` 关键字并没有阻止你修改 `listData`——这是因为内部类使用了 `listData`。）

`javax.swing.JList<E>` 1.2

- `ListModel<E> getModel()`: 获取此列表的模型。

`javax.swing.DefaultListModel<E>` 1.2

- `void addElement(E obj)`: 将对象添加到模型末尾。

- `boolean removeElement(Object obj)`: 从模型中删除对象的首次出现。如果存在于模型则返回 `true`，否则返回 `false`。

#### 10.1.4 渲染值

到目前，你在本章看到的所有列表都包含字符串。显示图标列表同样简单——只需传递一个填充了 `Icon` 对象的数组或向量。更有趣的是，你可以轻松地用任何绘制表示你的列表值。

虽然 `JList` 类可以自动显示字符串和图标，但你需要为所有自定义绘制 `JList` 对象安装*单元格渲染器*。列表单元格渲染器是实现以下接口的任何类：

点击此处查看代码

```java
interface ListCellRenderer<E>
{
    Component getCellRendererComponent(JList<? extends E> list,
    E value, int index, boolean isSelected, boolean cellHasFocus);
}
```

该方法为每个单元格被调用。它返回一个绘制单元格内容的组件。当需要渲染单元格时，该组件会被放置在合适的位置。

实现单元格渲染器的方法是创建一个扩展 `JComponent` 的类，如下：

点击此处查看代码

```java
class MyCellRenderer extends JComponent implements ListCellRenderer<Type>
{
    public Component getCellRendererComponent(JList<? extends Type> list,
    Type value, int index, boolean isSelected, boolean cellHasFocus)
    {
        *存储绘制和尺寸测量所需的信息*
        return this;
    }

    public void paintComponent(Graphics g)
    {
        *绘制代码*
    }

    public Dimension getPreferredSize()
    {
        *尺寸测量代码*
    }

    *实例字段*
}
```

在清单 10.4 中，我们通过显示每个字体的实际外观来图形化地展示字体选择（参见图 10.4）。在`paintComponent` 方法中，我们用自身的字体显示每个名称。我们还需要确保颜色与 `JList` 类外观（look-and-feel）的颜色匹配。我们通过调用 `JList` 类的 `getForeground/getBackground` 以及 `getSelectionForeground/getSelectionBackground` 方法来获取这些颜色。在`getPreferredSize` 方法中，我们需要使用你在第一卷第 10 章中看到的技巧来测量字符串的大小。

![Image](img/00167.jpeg)

**图 10.4** 带有渲染单元格的列表框

要安装单元格渲染器，只需调用 `setCellRenderer` 方法：

点击此处查看代码图像

```
fontList.setCellRenderer(new FontCellRenderer());
```

现在所有列表单元格都使用自定义渲染器进行绘制。

实际上，在许多情况下，编写自定义渲染器的更简单的方法有效。如果渲染的图像仅包含文本、图标以及可能发生的颜色变化，通过配置 `JLabel` 即可满足。例如，要用其自身的字体显示字体名称，我们可以使用以下渲染器：

点击此处查看代码图像

```java
class FontCellRenderer extends JLabel implements ListCellRenderer<Font>

{
   public Component getListCellRendererComponent(JList<? extends Font> list,
           Font value, int index, boolean isSelected, boolean cellHasFocus)
   {
      Font font = (Font) value;
      setText(font.getFamily());
      setFont(font);
      setOpaque(true);
      setBackground(isSelected ? list.getSelectionBackground() : list.getBackground());
      setForeground(isSelected ? list.getSelectionForeground() : list.getForeground());
      return this;
   }
}
```

注意，这里我们没有编写任何 `paintComponent` 或 `getPreferredSize` 方法；`JLabel` 类已经按照我们的要求实现了这些方法。我们所做的只是通过设置文本、字体和颜色来恰当地配置标签。

这段代码对于以下情况是一种方便的快捷方式：即现有组件（在本例中为 `JLabel`）已经提供了渲染单元格值所需的功能。

我们本可以在示例程序中使用 `JLabel`，但我们为你提供了更通用的代码，以便你需要在列表单元格中进行任意绘制时对其进行修改。

![Image](img/00004.jpeg)

> **警告**
>
> 在每次调用 `getListCellRendererComponent` 时构造新组件并不是一个好主意。如果用户滚动查看许多列表项，每次都会构造一个新组件。重新配置现有组件是安全的且高效得多。

**清单 10.4** `listRendering/FontCellRenderer.java`

点击此处查看代码图像



```java
package listRendering;

import java.awt.*;
import javax.swing.*;

/**
 * 用于 Font 对象的单元格渲染器，用其自身的字体渲染字体名称。
 */
public class FontCellRenderer extends JComponent implements ListCellRenderer<Font>
{
    private Font font;
    private Color background;
    private Color foreground;

    public Component getListCellRendererComponent(JList<? extends Font> list,
            Font value, int index, boolean isSelected, boolean cellHasFocus)
    {
        font = value;
        background = isSelected ? list.getSelectionBackground() : list.getBackground();
        foreground = isSelected ? list.getSelectionForeground() : list.getForeground();
        return this;
    }

    public void paintComponent(Graphics g)
    {
        String text = font.getFamily();
        FontMetrics fm = g.getFontMetrics(font);
        g.setColor(background);
        g.fillRect(0, 0, getWidth(), getHeight());
        g.setColor(foreground);
        g.setFont(font);
        g.drawString(text, 0, fm.ascent());
    }

    public Dimension getPreferredSize()
    {
        String text = font.getFamily();
        FontMetrics fm = g.getFontMetrics(font);
        return new Dimension(fm.width(text), fm.getHeight());
    }
}
```

### 10.2 表格

与 `JList` 组件类似，`JTable` 不存储自己的数据，而是从表格模型（table model）获取。这是我们在第一个示例中使用的策略；在本章的后面部分，我们将转向表格模型。

#### 10.2.1 简单表格

`JTable` 构造函数将二维数组封装进默认模型。图 10.5 显示了一个典型的表格，描述了太阳系的属性。（如果一个行星主要由氢和氦组成，它就是气态行星。你应该对“颜色”条目保留意见——添加该列是因为它在后的示例中将很有用。）

正如你从列表 10.5 中的代码中看到的，表格数据是存储为 `Object` 值的二维数组的：

点击此处查看代码图像

```java
Object[][] cells = {
    { "Mercury", 2440.0, 0, false, Color.YELLOW },
    { "Venus", 6052.0, 0, false, Color.YELLOW },
    . .
}
```

在这里，我们利用了自动装箱（autoboxing）。第二、第三和第四列的项会自动转换为 `Double`、`Integer` 和 `Boolean` 类型的对象。

表格简单地调用每个对象的 `toString` 方法来显示它。这就是为什么颜色显示为 `java.awt.Color[r=. . .,g=. . .,b=. . .]`。

通过独立的字符串数组提供列名：

点击此处查看代码图像

```java
String[] columnNames = { "Planet", "Radius", "Moons", "Gaseous", "Color" };
```

然后，通过单元格和列名数组构造一个表格：

点击此处查看代码图片

```java
JTable table = new JTable(cells, columnNames);
```

![Image](img/00002.jpeg)

> **注意**
>
> 请注意，`JTable` 与 `JList` 不同，它不是泛型类型。这有其充分的理由。列表中的元素预期是统一的类型——但通常情况下，整个表格并没有单一的元素类型。在我们的示例中，行星名称是字符串，颜色是 `java.awt.Color` 类型，以此类推。

你可以按照通常的方法添加滚动条——通过将表格封装在 `JScrollPane` 中：

点击此处查看代码图片

```java
JScrollPane pane = new JScrollPane(table);
```

当你滚动表格时，表格表头不会滚出视野。

接下来，点击其中一个列头并向左或向右拖动。观察整个列是如何分离的（参见图 10.6）。你可以将其放置在不同的位置。这仅在视图中重新排列了列。数据模型则不受影响。

![Image](img/00170.jpeg)

**图 10.6** 移动列

要调整列的宽度，只需将光标置于两列之间，直到光标形状变为箭头。然后，将列边界拖到所需的位置（参见图 10.7）。

![Image](img/00171.jpeg)

**图 10.7** 调整列宽

用户可以通过点击行中的任意位置来选择行。被选中的行会被高亮显示；你稍后将看到如何获取选择事件。用户还可以通过点击单元格并输入内容来编辑表格条目。然而，在这个代码示例中，编辑不会改变底层数据。在你的程序中，你应该将单元格设为不可编辑，或者处理单元格编辑事件并更新你的模型。我们将在本节稍后的部分讨论这些主题。

最后，点击列头。行将自动排序。再次点击，排序顺序将反转。这种行为通过以下调用激活：

点击此处查看代码图片

```java
table.setAutoCreateRowSorter(true);
```

你可以通过以下调用打印表格：

```java
table.print();
```

会弹出一个打印对话框，并将表格发送到打印机。我们将在第 11 章中讨论自定义打印选项。

![Image](img/00002.jpeg)

> **注意**
>
> 如果你调整 `TableTest` 的高度使其高于表格高度，你会在表格下方看到灰色区域。与 `JList` 和 `JTree` 组件不同，表格不会填充滚动面板的视口。如果你想支持拖放，这可能会成为一个问题。（关于拖放的更多信息，请参见第 11 章。）在这种情况下，调用：

点击此处查看代码图片

```java
table.setFillsViewportHeight(true);
```

![Image](img/00004.jpeg)

> **注意**
>
> 如果你没有将表格封装到滚动面板中，你需要显式添加表头：

点击此处查看代码图片

```java
add(table.getTableHeader(), BorderLayout.NORTH);
```

**列表 10.5** `table/TableTest.java`

点击此处查看代码图片

```java
package table;

import java.awt.*;
import java.awt.print.*;
import javax.swing.*;

/**
 * 此程序演示了如何显示简单的表格。
 * @version 1.13 2016-05-10
 * @author Cay Horstmann
 */
public class TableTest
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() ->
        {
            JFrame frame = new PlanetFrame();
            frame.setTitle("Test");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}

/**
 * 此框架包含一个数据表格。
 */
class PlanetFrame extends JFrame
{
    private String[] columnNames = { "Planet", "Radius", "Moons", "Color" };
    private Object[][] cells = { "Mercury", 2440.0, 0, Color.YELLOW },
        { "Venus", 6052.0, 0, Color.YELLOW }, { "Earth", 6378.0, 1, Color.BLUE },
        { "Mars", 3397.0, 2, Color.BLUE };

    public PlanetFrame()
    {
        final JTable table = new JTable(cells, columnNames);
        table.setAutoCreateRowSorter(true);
        add(new JScrollPane(table), BorderLayout.CENTER);
        JButton printButton = new JButton("Print");
        printButton.addActionListener(event ->
        {
            try {
                table.print();
            } catch (PrinterException ex) {
                ex.printStackTrace();
            }
        });
        JPanel buttonPanel = new JPanel();
        buttonPanel.add(printButton);
        add(buttonPanel, BorderLayout.SOUTH);
        pack();
    }
}
```

`getRowCount` 和 `getColumnCount` 方法简单返回行数和列数：

点击此处查看代码图片

```java
public int getRowCount() { return years; }

public int getColumnCount() { return maxRate - minRate + 1; }
```

如果你不提供列名，`AbstractTableModel` 的 `getColumnName` 方法将列命名为 A、B、C 等。要更改默认列名，请重写 `getColumnName` 方法。在例子中，我们只是简单地为每一列标记了利率标签。

点击此处查看代码图片

```java
public String getColumnName(int c) { return (c + minRate) + "%"; }
```

你可以在列表 10.6 中找到完整的源代码。

**列表 10.6** `tableModel/InvestmentTable.java`

点击此处查看代码图片

```java
package tableModel;

import java.awt.*;

import javax.swing.*;
import javax.swing.table.*;

/**
 * 此程序展示了如何从表格模型构建表格。
 * @version 1.03 2006-05-10
 * @author Cay Horstmann
 */
public class InvestmentTable
{
    public static void main(String[] args)
    {
        EventQueue.invokeLater(() ->
        {
            JFrame frame = new InvestmentTableFrame();
            frame.setTitle("InvestmentTable");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}

/**
 * 此框架包含投资表格。
 */
class InvestmentTableFrame extends JFrame
{
    public InvestmentTableFrame()
    {
        TableModel model = new InvestmentTableModel(30, 5, 10);
        JTable table = new JTable(model);
        add(new JScrollPane(table));
        pack();
    }
}

/**
 * 此表格模型在每次被请求时计算单元格条目。
 * 表格显示了不同利率下多年投资的增长情况。
 */
class InvestmentTableModel extends AbstractTableModel
{
    private static double INITIAL_BALANCE = 100000.0;

    private int years;
    private int minRate;
    private int maxRate;

    /**
     * 构建一个投资模型。
     * @param y 年数
     * @param r1 要列出的最低利率
     * @param r2 要列出的最高利率
     */
    public InvestmentTableModel(int y, int r1, int r2)
    {
        years = y;
        minRate = r1;
        maxRate = r2;
    }

    public int getRowCount()
    {
        return years;
    }

    public int getColumnCount()
    {
        return maxRate - minRate + 1;
    }

    public Object getValueAt(int r, int c)
    {
        double rate = (c + minRate) / 100.0;
        int nperiods = r;
        double futureBalance = INITIAL_BALANCE * Math.pow(1 + rate, nperiods);
        return String.format("%.2f", futureBalance);
    }

    public String getColumnName(int c)
    {
        return (c + minRate) + "%";
    }
}
```

`javax.swing.table.TableModel` 1.2

- `int getRowCount()`
- `int getColumnCount()` 获取表格模型中的行数和列数。
- `Object getValueAt(int row, int column)` 获取指定行和列的值。
- `void setValueAt(Object newValue, int row, int column)` 在指定的行和列上设置一个新值。
- `boolean isCellEditable(int row, int column)` 如果指定行和列的单元格可编辑，则返回 `true`。
- `String getColumnName(int column)` 获取列标题。

### 10.2.3 操作行和列

在本小节中，你将看到如何操作表格中的行和列。在阅读这些材料时，请记住 Swing 表格是非常不对称的——你可以在行和列上执行的操作是不同的。表格组件经过了优化，用于显示具有相同结构的行信息（例如数据库查询的结果），而不是任意的二维对象网格。你将在整个小节中看到这种不对称性。

#### 10.2.3.1 列类

在下一个示例中，我们再次显示行星数据，但这次我们想为表格提供更多关于列类型的信息。这是通过定义表格模型中的 `Class<?> getColumnClass(int columnIndex)` 方法来返回类。`JTable` 使用此信息来选择渲染器。

![Image](img/00173.jpeg)

**表 10.1** 默认渲染

要渲染其他类型，可以查看 10.2.4 节，第 626 页。

#### 10.2.3.2 获取列

![Image](img/00175.jpeg)

**图 10** 类之间的关系



`JTable` 类将信息存储在`TableColumn`对象中。`ColumnModel`对象管理列。如果你不需要动态插入或删除列，不会经常使用列模型。列模型最常用的用法是获取`TableColumn`对象：

```java
int columnIndex = ...
TableColumn column = table.getColumnModel().getColumn(columnIndex);
```

### 10.2.3.3 调整列

`TableColumn`类让你控制列的调整大小行为。你可以通过以下方法设置首选、最小和最大宽度：

```java
void setPreferredWidth(int width)
void setMinWidth(int width)
void setMaxWidth(int width)
```

这些信息被表格组件用于布局列。

使用方法：

```java
void setResizable(boolean resizable)
```

来控制用户是否允许调整列大小。

可以使用方法编程调整列：

```java
void setWidth(int width)
```

当列被调整大同时，默认是保持表格的总尺寸不变。当然，调整列的宽度增加或减少必须分配给其他列。默认行为是更改被调整列右侧所有列的大小。这是一个很好的默认，因为它允许用户从左到右调整所有列到所需的宽度。

你可以通过表 10.2 中的方法设置另一种行为：

```java
void setAutoResizeMode(int mode)
```

![Image](img/00176.jpeg)

**表 10.2** `JTable`类的自动调整大小模式

### 10.2.3.4 调整行

行的高度由`JTable`类直接管理。如果你的单元格比默认高，你可能需要设置行高：

```java
table.setRowHeight(height);
```

默认情况下，表格所有行的高度都相同。你可以通过调用设置单独行的高度：

```java
table.setRowHeight(row, height);
```

实际的行高等于这些方法设置的行高减去行间距。默认行间距为 1 像素，但你可以通过调用以下方法更改它：

```java
table.setRowMargin(margin);
```

### 10.2.3.5 选择行、列和单元格

根据选择模式，用户可以选择表格中的行、列或单个单元格。默认启用了行选择。点击单元格内部会选中整行（参见第 609 页上的图 10.9）。调用以下方法：

```java
table.setRowSelectionAllowed(false)
```

当启用行选择时，你可以控制是否允许用户选择单行、一组连续行或任意一组行。你需要获取*选择模型*（selection model）并使用它的`setSelectionMode`方法：

```java
table.getSelectionModel().setSelectionMode(mode);
```

在这里，`mode`是三个值之一：

```java
ListSelectionModel.SINGLE_SELECTION
ListSelectionModel.SINGLE_INTERVAL_SELECTION
ListSelectionModel.MULTIPLE_INTERVAL_SELECTION
```

列选择默认是禁用的。你可以通过调用以下方法开启它：

```java
table.setColumnSelectionAllowed(true)
```

同时启用行和列选择等同于启用单元格选择。用户随后将选择单元格区域（参见图 10.11）。你也可以通过调用该方法启用设置：

```java
table.setCellSelectionEnabled(true)
```

![Image](img/00177.jpeg)

**图 10.11** 选择单元格范围

运行代码列表 10.7 中的程序以观察单元格选择的操作。在“选择”（Selection）菜单中启用行、列或单元格选择，并观察选择行为的变化。

你可以通过调用`getSelectedRows`和`getSelectedColumns`方法确定哪些行和列被选中了。这两个方法都返回一个包含选中项索引的`int[]`数组。注意，索引值是表格视图的索引，而不是底层的表格模型。尝试选择行和列，然后将列拖到不同位置并通过点击列头对行进行排序。使用“打印选择”（Print Selection）菜单项查看哪些行和列被报告为已选中。

如果你需要将表格索引值转换为模型索引值，请使用`JTable`的方法`convertRowIndexToModel`和`convertColumnIndexToModel`。

### 10.2.3.6 对行排序

正如我们在第一个表格示例中所看到的，只需调用`setAutoCreateRowSorter`方法即可轻松为`JTable`添加行排序。然而，为了对排序行为进行更细粒度的控制，可以向`JTable`中安装一个`TableRowSorter<M>`对象并对其进行自定义。类型参数`M`表示表格模型；它需要是`TableModel`接口的子类型。

```java
TableRowSorter<TableModel> sorter = new TableRowSorter<TableModel>(model);
table.setRowSorter(sorter);
```

某些列不应该是排序，例如我们行星数据中的图像列。通过调用以下方法关闭排序：

```java
sorter.setSortable(IMAGE_COLUMN, false);
```

你可以为每列安装一个自定义比较器。在示例中，我们将通过优先考虑蓝色和绿色来对“颜色”列中的颜色进行排序。当你点击“颜色”列时，你会发现蓝色的行星到了表格底部。这是通过以下调用实现的：

```java
sorter.setComparator(COLOR_COLUMN, new Comparator<Color>()
{
    public int compare(Color c1, Color c2)
    {
        int d = c1.getBlue() - c2.getBlue();
        return d;
    }
});
```

`RowFilter<M, I>`类有两个类型参数——分别对应模型和行标识符的类型。在处理表格时，模型始终是`TableModel`的子类型，而标识符类型为`Integer`。（在未来的某个某个时刻，其他组件可能也支持行过滤。例如，为了过滤`JTree`中的行，可以使用`RowFilter<TreeModel, TreePath>`。）

行过滤器（row filter）必须实现该方法：

```java
public boolean include(RowFilter.Entry<? extends M, ? extends I> entry)
```

`RowFilter.Entry`类提供了获取模型、行标识符以及指定索引值的方法。因此，你既可以根据行标识符进行过滤，也可以根据行内容进行过滤。

例如，此过滤器每隔一行显示一行：

```java
RowFilter<TableModel, Integer> filter = new RowFilter<TableModel, Integer>()
{
    public boolean include(Entry<? extends TableModel, ? extends Integer> entry)
    {
        return entry.getIdentifier() % 2 == 0;
    }
};
```

如果你只想包含那些具有偶数个卫星的行星，你应该进行如下测试：

```java
((Integer) entry.getValue(MOONS_COLUMN)) % 2 == 0
```

在我们的示例程序中，允许用户隐藏任意行。我们将隐藏的行索引存储在一个集合（set）中。行过滤器包含了所有索引不在该集合中的行。

过滤机制的设计并不是为了标准随时间变化的过滤器。在我们的示例程序中，每当隐藏行集合发生变化时，都会调用：

```java
sorter.setRowFilter(filter);
```

设置过滤器会导致立即生效。

### 10.2.3.8 隐藏和显示列

正如你在上一节中看到的，你可以根据内容或行标识符来过滤表格行。隐藏表格列则使用完全不同的机制。

`JTable`类的`removeColumn`方法从表格视图中移除列。列数据并没有实际上从模型中删除——它们只是在视图中隐藏了。`removeColumn`方法接受一个`TableColumn`参数。如果你有列号（例如通过调用`getSelectedColumns`获取），你需要向表格模型请求实际表格列对象：

```java
TableColumnModel columnModel = table.getColumnModel();
TableColumn column = columnModel.getColumn(i);
table.removeColumn(column);
```

如果你还记得该列，稍后可以将其添加回来：

```java
table.addColumn(column);
```

此方法将列添加到末尾。如果你如果你想让它出现在其他地方，请调用`moveColumn`方法。

你也可以通过添加一个新的`TableColumn`对象来添加一个与表格模型中列索引对应的新列：

```java
table.addColumn(new TableColumn(modelColumnIndex));
```

你可以拥有多个表格列，它们对应模型中的同一列。

列表 10.7 中的程序演示了行和列的选择与过滤。

**列表 10.7** `tableRowColumn/PlanetTableFrame.java`



```java
package tableRowColumn;

import java.awt.*;
import java.util.*;

import javax.swing.*;
import javax.swing.table.*;

/**
 * 此框架包含一个包含行星数据的表格。
 */
public class PlanetTableFrame extends JFrame
{
    private static final int DEFAULT_WIDTH = 600;
    private static final int DEFAULT_HEIGHT = 500;

    public static final int COLOR_COLUMN = 4;
    public static final int IMAGE_COLUMN = 5;

    private JTable table;
    private HashSet<Integer> removedIndices;
    private ArrayList<TableColumn> removedColumns;
    private JCheckBox rowsItem;
    private JCheckBox columnsItem;
    private JCheckBox cellsItem;

    private String[] columnNames = { "Planet", "Radius", "Moons", "Color", "Image" };
    private Object[][] cells = {
        { "Mercury", 440.0, 0, Color.YELLOW, new ImageIcon(getClass().getResource("Mercury.gif")) },
        { "Venus", 6052.0, 0, Color.YELLOW, new ImageIcon(getClass().getResource("Venus.gif")) },
        { "Earth", 6378.0, 1, Color.BLUE, new ImageIcon(getClass().getResource("Earth.gif")) },
        { "Mars", 3397.0, 2, Color.RED, new ImageIcon(getClass().getResource("Mars.gif")) },
        { "Jupiter", 71492.0, 16, Color.ORANGE, new ImageIcon(getClass().getResource("Jupiter.gif")) },
        { "Saturn", 60268.0, 18, Color.ORANGE, new ImageIcon(getClass().getResource("Saturn.gif")) },
        { "Uranus", 25559.0, 17, Color.BLUE, new ImageIcon(getClass().getResource("Uranus.gif")) },
        { "Neptune", 24766.0, 8, Color.BLUE, new ImageIcon(getClass().getResource("Neptune.gif")) },
        { "Pluto", 1137.0, 1, Color.BLACK, new ImageIcon(getClass().getResource("Pluto.gif")) }
    };

    public PlanetTableFrame()
    {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

        TableModel model = new DefaultTableModel(cells, columnNames)
        {
            public Class<?> getColumnClass(int c)
            {
                return cells[0][c].getClass();
            }
        };

        table = new JTable(model);
        table.setRowHeight(100);
        table.getColumnModel().getColumn(COLOR_COLUMN).setMinWidth(250);
        table.getColumnModel().getColumn(IMAGE_COLUMN).setMinWidth(100);

        final RowSorter<TableModel> sorter = new RowSorter<>(model);
        table.setRowSorter(sorter);
        sorter.setComparator(COLOR_COLUMN, Comparator.comparing(Color::getBlue).thenComparing(Color::getGreen).thenComparing(Color::getRed));
        sorter.setSortable(IMAGE_COLUMN, false);
        add(new JScrollPane(table), BorderLayout.CENTER);

        removedIndices = new HashSet<>();
        removedColumns = new ArrayList<>();

        final RowFilter<TableModel, Integer> filter = new RowFilter<TableModel, Integer>()
        {
            public boolean include(Entry<? extends TableModel, ? extends Integer> entry)
            {
                return !removedIndices.contains(entry.getIdentifier());
            }
        };

        // 创建菜单
        MenuBar menuBar = new JMenuBar();
        setMenuBar(menuBar);
        JMenu selectionMenu = new JMenu("Selection");
        menuBar.add(selectionMenu);
        rowsItem = new JCheckBox("Rows");
        columnsItem = new JCheckBox("Columns");
        cellsItem = new JCheckBox("Cells");

        rowsItem.setSelected(table.getRowSelectionAllowed());
        columnsItem.setSelected(table.getColumnSelectionAllowed());
        cellsItem.setSelected(table.getCellSelectionEnabled());

        rowsItem.addActionListener(event ->
        {
            table.clearSelection();
            table.setRowSelectionAllowed(rowsItem.isSelected());
            updateCheckboxMenuItems();
        });

        columnsItem.addActionListener(event ->
        {
            table.clearSelection();
            table.setColumnSelectionAllowed(columnsItem.isSelected());
            updateCheckboxMenuItems();
        });
    }

    private void updateCheckboxMenuItems() {
        // 此处可以根据需要更新菜单状态
    }
}
```

```java
selectionMenu.add(columnsItem);

cellsItem.addActionListener(event ->
{
    table.clearSelection();
    table.setCellSelectionEnabled(cellsItem.isSelected());
    updateCheckboxMenuItems();
});
selectionMenu.add(cellsItem);

JMenu tableMenu = new JMenu("Edit");
menuBar.add(tableMenu);

JMenuItem hideColumnsItem = new JMenuItem("Hide Columns");
hideColumnsItem.addActionListener(event ->
{
    int[] selected = table.getSelectedColumns();
    TableColumnModel columnModel = table.getColumnModel();

    // 从视图中移除列，从最后一个索引开始，
    // 这样列序号就不会受影响
    for (int i = selected.length - 1; i >= 0; i--)
    {
        TableColumn column = columnModel.getColumn(selected[i]);
        table.removeColumn(column);

        // 存储移除的列以便“显示列”命令
        removedColumns.add(column);
    }
});
tableMenu.add(hideColumnsItem);

JMenuItem showColumnsItem = new JMenuItem("Show Columns");
showColumnsItem.addActionListener(event ->
{
    // 恢复所有移除的列
    for (TableColumn tc : removedColumns)
        table.addColumn(tc);
    removedColumns.clear();
});
tableMenu.add(showColumnsItem);

JMenuItem hideRowsItem = new JMenuItem("Hide Rows");
hideRowsItem.addActionListener(event ->
{
    int[] selected = table.getSelectedRows();
    for (int i : selected)
        removedRowIndices.add(table.convertRowIndexToModel(i));
    sorter.setRowFilter(filter);
});
tableMenu.add(hideRowsItem);

JMenuItem showRowsItem = new JMenuItem("Show Rows");
showRowsItem.addActionListener(event ->
{
    removedRowIndices.clear();
    sorter.setRowFilter(filter);
});
tableMenu.add(showRowsItem);

JMenuItem printSelectionItem = new JMenuItem("Print Selection");
printSelectionItem.addActionListener(event ->
{
    int[] selected = table.getSelectedRows();
    System.out.println("Selected rows: " + Arrays.toString(selected));
    int[] columns = table.getSelectedColumns();
    System.out.println("Selected columns: " + Arrays.toString(columns));
});
tableMenu.add(printSelectionItem);
}

private void updateCheckboxMenuItems()
{
    rowsItem.setSelected(table.getRowSelectionAllowed());
    columnsItem.setSelected(table.getColumnSelectionAllowed());
    cellsItem.setSelected(table.getCellSelectionEnabled());
}
```

### `javax.swing.table.TableModel`

- `Class getColumnClass(int columnIndex)`：获取此列中值的类。此信息用于排序和渲染。

### `javax.swing.JTable`

- `TableColumnModel getColumnModel()`：获取描述表格列排列的“列模型”。

- `void setAutoResizeMode(int mode)`：设置表格列自动调整大小的模式。

![Image](img/00178.jpeg)

- `int getRowMargin()`

- `void setRowMargin(int margin)`：获取或设置相邻行单元格之间的空白量。

- `int getRowHeight()`

- `void setRowHeight(int height)`：获取或设置表格所有行的默认高度。

- `int getRowHeight(int row)`

- `void setRowHeight(int row, int height)`：获取或设置表格指定行的高度。

- `ListSelectionModel getSelectionModel()`：返回列表选择模型。你需要该模型来在行、列和单元格选择之间切换。

- `boolean getRowSelectionAllowed()`

- `void setRowSelectionAllowed(boolean b)`：获取或设置 `rowSelectionAllowed` 属性。如果为 `true`，当用户点击单元格时将选中行。

- `boolean getColumnSelectionAllowed()`

- `void setColumnSelectionAllowed(boolean b)`：获取或设置 `columnSelectionAllowed` 属性。如果为 `true`，当用户点击单元格时将选中列。

- `boolean getCellSelectionEnabled()`：如果 `rowSelectionAllowed` 和 `columnSelectionAllowed` 均为 `true`，则返回 `true`。

- `void setCellSelectionEnabled(boolean b)`：将 `rowSelectionAllowed` 和 `columnSelectionAllowed` 都设置为 `b`。

- `void addColumn(TableColumn column)`：将列作为表格视图的最后一列添加。

- `void moveColumn(int from, int to)`：移动表格索引为 `from` 的列，使其索引变为 `to`。仅影响视图。

- `void removeColumn(TableColumn column)`：从视图中移除给定列。

- `int convertRowIndexToModel(int index)`

- `int convertColumnIndexToModel(int index)`：返回给定索引的行或列的模型索引。当行被排序或过滤，或者列被移动或移除时，此值与 `index` 不同。

- `void setRowSorter(RowSorter<? extends TableModel> sorter)`：设置行排序器。

### `javax.swing.table.TableColumnModel`

- `TableColumn getColumn(int index)`：获取给定索引的表格列。

### `javax.swing.table.TableColumn`

- `TableColumn(int modelIndex)`：为查看模型列构造表格列。

- `void setPreferredWidth(int width)`

- `void setMinWidth(int width)`

- `void setMaxWidth(int width)`：将此表格列的首选宽度、最小和最大宽度设置为 `width`。

- `void setWidth(int width)`：将此列的实际宽度设置为 `width`。



- `void setResizable(boolean b)`：如果 `b` 为 `true`，则此列可调整大小。

### `javax.swing.ListSelectionModel`

- `void setSelectionMode(int mode)`

![Image](img/179.jpeg)

### `javax.swing.table.DefaultRowSorter<M, I>`

- `void setComparator(int column, Comparator<?> comparator)`：为给定列设置比较器。
- `void setSortable(int column, boolean enabled)`：启用或禁用给定列的排序。
- `void setRowFilter(RowFilter<? super M, ? super I> filter)`：设置行过滤器。

### `javax.swing.table.TableRowSorter<M extends TableModel>`

- `void setStringConverter(TableStringConverter stringConverter)`：设置用于排序和过滤的字符串转换器。

### `javax.swing.table.TableStringConverter`

- `abstract String toString(TableModel model, int row, int column)`：将给定位置的值转换为字符串；你可以重写此方法。

### `javax.swing.RowFilter<M, I>`

- `boolean include(RowFilter.Entry<? extends M, ? extends I> entry)`：指定保留的行；你可以重写此方法。
- `static <M, I> RowFilter<M, I> numberFilter(RowFilter.ComparisonType type, Number number, int... indices)`：返回一个包含与给定数字匹配的值的过滤器。
- `static <M, I> RowFilter<M, I> dateFilter(RowFilter.ComparisonType type, Date date, int... indices)`：返回一个包含与给定日期匹配的值的行的过滤器。比较类型为 `EQUAL`、`NOT_EQUAL`、`AFTER` 或 `BEFORE` 之一。如果给了任何列模型索引，则只搜索这些列；否则，搜索所有列。对于数字过滤器，单元格值的类必须与 `number` 的类匹配。
- `static <M, I> RowFilter<M, I> regexFilter(String regex, int... indices)`

  返回一个过滤器，包含与给定正则表达式匹配的字符串值的行。如果提供了任何列模型索引，则只搜索这些列；否则，搜索所有列。请注意，匹配的是 `RowFilter.Entry` 的 `getStringValue` 方法返回的字符串。

- `static <M, I> RowFilter<M, I> andFilter(Iterable<? extends RowFilter<? super M, ? super I>> filters)`
- `static <M, I> RowFilter<M, I> orFilter(Iterable<? extends RowFilter<? super M, ? super I>> filters)`

  返回一个过滤器，包含被所有过滤器或至少被一个过滤器包含的条目。

- `static <M, I> RowFilter<M, I> notFilter(RowFilter<M, I> filter)`

  返回一个过滤器，包含不包含给定过滤器的条目。

### `javax.swing.RowFilter.Entry<M, I>`

- `I getIdentifier()`

  返回此行条目的标识符。

- `M getModel()`

  返回此行条目的模型。

- `Object getValue(int index)`

  返回此行指定索引处存储的值。

- `int getValueCount()`

  返回此行中存储的值的数量。

- `String getStringValue()`

  返回此行指定索引处存储的值，并转换为字符串。`TableRowSorter` 产生的条目，其 `getStringValue` 调用会调用排序器的字符串转换器。

## 10.2.4 单元格渲染与编辑

正如你在第 10.2.3.2 节中所看到的，第 610 页上的“访问表格列”，列类型决定了单元格如何渲染。对于 `Boolean` 和 `Icon` 类型有默认的渲染器，用于渲染复选框或图标。对于所有其他类型，你需要安装自定义的渲染器。

### 10.2.4.1 渲染单元格

表格单元格渲染器与你之前看到的列表单元格渲染器类似。它们实现了 `TableCellRenderer` 接口，该接口有一个方法：

点击此处查看代码图片

```java
Component getTableCellRendererComponent(JTable table, Object value, boolean isSelected,
      boolean hasFocus, int row, int column)
```

当表格需要绘制单元格时，会调用该方法。你返回一个组件，该组件的 `paint` 方法将被调用以填充单元格区域。

图 10.12 中的表格包含 `Color` 类型的单元格。渲染器简单地返回一个带有背景色的面板，该背景颜色是存储在单元格中的颜色对象。该颜色作为 `value` 参数传递。

点击此处查看代码图片

```java
class ColorTableCellRenderer extends JPanel implements TableCellRenderer
{
    public Component getTableCellRendererComponent(JTable table, Object value,
          boolean isSelected, boolean hasFocus, int row, int column)
    {
      setBackground((Color) value);
      if (hasFocus)
          setBorder(UIManager.getBorder("Table.focusCellHighlightBorder"));
      else
          setBorder(null);
    return this;
    }
}
```

![Image](img/00180.jpeg)

**图 10.12** 带有单元格渲染器的表格

如你所示，当单元格获得焦点时，渲染器会绘制边框。（我们向 `UIManager` 请求正确的边框。为了找到查找键，我们查看了 `DefaultTableCellRenderer` 类的源代码。）

通常，你还想设置单元格的背景颜色，以指示它当前是否被选中。我们跳过了这一步，因为它会干扰显示的颜色。列表 10.4 中的 `ListRenderingTest` 示例展示了如何在渲染器中指示选择状态。

你需要告诉表格对所有 `Color` 类型的对象都使用此渲染器。`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器：

点击此处查看代码图片

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在用于此表格中所有给定类型的对象。

如果你想根据类型选择渲染器，`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器：

点击此处查看代码图片

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在用于此表格中所有给定类型的对象。

如果你想根据类型选择渲染器，`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器：

点击此处查看代码图片

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在用于此表格中所有给定类型的对象。

如果你想根据类型选择渲染器，`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器：

点击此处查看代码图片

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在用于此表格中所有给定类型的对象。

如果你想根据类型选择渲染器，`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器：

点击此处查看代码图片

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在用于此表格中所有给定类型的对象。

如果你想根据类型选择渲染器，`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器：

点击此处查看代码图片

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在用于此表格中所有给定类型的对象。

如果你想根据类型选择渲染器，`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器：

点击此处查看代码图片

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在用于此表格中所有给定类型的对象。

如果你想根据类型选择渲染器，`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器：

点击此处查看代码图片

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在用于此表格中所有给定类型的对象。

如果你想根据类型选择渲染器，`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器：

点击此处查看代码图片

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在用于此表格中所有给定类型的对象。

如果你想根据类型选择渲染器，`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器：

点击此处查看代码图片

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在用于此表格中所有给定类型的对象。

如果你想根据类型选择渲染器，`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器：

点击此处查看代码图片

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在用于此表格中所有给定类型的对象。

如果你想根据类型选择渲染器，`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器：

点击此处查看代码图片

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在用于此表格中所有给定类型的对象。

如果你想根据类型选择渲染器，`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器：

点击此处查看代码图片

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在用于此表格中所有给定类型的对象。

如果你想根据类型选择渲染器，`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器：

点击此处查看代码图片

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在用于此表格中所有给定类型的对象。

如果你想根据类型选择渲染器，`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器：

点击此处查看代码图片

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在用于此表格中所有给定类型的对象。

如果你想根据类型选择渲染器，`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器：

点击此处查看代码图片

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在用于此表格中所有给定类型的对象。

如果你想根据类型选择渲染器，`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器：

点击此处查看代码图片

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在用于此表格中所有给定类型的对象。

如果你想根据类型选择渲染器，`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器：

点击此处查看代码图片

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在用于此表格中所有给定类型的对象。

如果你想根据类型选择渲染器，`JTable` 类的 `setDefaultRenderer` 方法允许你建立这种关联。提供一个 `Class` 对象和渲染器……

### 10.2.4.2 渲染表头

为了在标题中显示图标，手动设置渲染器——`JTable` 组件不知道哪些值适用于特定类型。对于 Moons 列，我们想要让用户选择 0 到 20 之间的任何值。这里是 Wait... The `setDefaultRenderer` method of the `JTable` class lets you establish this association. Supply a `Class` object and the renderer:



点击此处查看代码图片

```java
table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
```

该渲染器现在用于此表格中所有给定类型的对象。

##### 10.2.4.3 单元格编辑

要启用单元格编辑，模型必须通过定义 `isEditable` 方法指示哪些单元格是可以编辑的。通常，你会子类 `JTable` 并重写该方法。

```java
public boolean isEditable(int r, int c)
{
  return c == PLANET_COLUMN || c == MOONS_COLUMN || c == GASEOUS_COLUMN || c == COLOR_COLUMN;
}
```

如果你运行程序，注意你可以点击 Gaseous 列中的复选框并开启或取消标记。如果你点击 Moons 列中的单元格，会出现一个组合框（参见图 10.13）。你稍后将看到如何安装这样一个组合框作为单元格编辑器。

```java
TableCellEditor moonEditor = new DefaultCellEditor(moonCombo);
table.setCellEditor(MOONS_COLUMN, moonEditor);
```

接下来，我们需要安装编辑器。与颜色单元渲染器不同，此编辑器不依赖于对象的 `type`——我们并不一定想将其应用于所有 `Integer` 类型的对象。相反，我们需要将其安装到特定的列中：

点击此处查看代码图片

```java
moonColumn.setCellEditor(moonEditor);
```

##### 10.2.4.4 自定义编辑器

再次运行示例程序并点击颜色。弹出一个颜色选择器，允许你为行星选择一种新颜色。选择一种颜色并点击确定。单元格颜色将更新（参见图 10.14）。

![Image](img/00182.jpeg)

**图 10.14** 使用颜色选择器编辑单元格颜色

颜色单元编辑器不是标准的表格单元格编辑器，而是自定义的实现。要创建自定义单元格编辑器，需要实现 `TableCellEditor` 接口。该接口有点繁琐，从 Java SE 1.3 开始，提供了一个 `AbstractCellEditor` 类来处理事件处理细节。

`TableCellEditor` 接口的 `getTableCellEditorComponent` 方法请求一个用于渲染单元格的组件。它与 `TableCellRenderer` 接口的 `getTableCellRendererComponent` 方法完全相同，只是没有 `focus` 参数。当单元格正在编辑时，假设它拥有焦点。在编辑进行期间，编辑器组件会临时替换渲染器。在示例中，我们返回了一个没有颜色的空白面板。这向用户指示该单元格当前正在编辑。

接下来，你希望在用户点击单元格时弹出你的编辑器。

`JTable` 类会带带一个事件（如鼠标点击）调用你的编辑器，以确定该事件是否可以启动编辑过程。`AbstractCellEditor` 类定义了接受所有事件的方法。

点击此处查看代码图片

```java
public boolean isCellEditable(EventObject anEvent)
{
   return true;
}
```

然而，如果你重写了此方法并返回 `false`，表格将不会费力插入编辑器组件。

一旦安装了编辑器组件，就会调用 `shouldSelectCell` 方法，推测使用的是相同的事件。你应该在此方法中启动编辑——例如，通过弹出一个外部编辑对话框。

点击此处查看代码图片

```java
public boolean shouldSelectCell(EventObject anEvent)
{
   colorDialog.setVisible(true);
   return true;
}
```

如果用户取消编辑，表格会调用 `cancelCellEditing` 方法。如果用户点击了另一个表格单元格，表格会调用 `stopCellEditing` 方法。在这两种情况下，你都应该隐藏对话框。当你的 `stopCellEditing` 方法被调用时，表格想要使用部分编辑的值。如果当前值有效，你应该返回 `true`。在颜色选择器中，任何值都是有效的。但如果你编辑其他数据，可以确保只从编辑器中获取有效数据。

此外，你应该调用处理事件触发的父类方法——否则编辑将无法被正常取消。

点击此处查看代码图片

```java
public void cancelCellEditing()
{
   colorDialog.setVisible(false);
   super.cancelCellEditing();
}
```

最后，你需要一个方法来产生用户在编辑过程中提供的值：

点击此处查看代码图片

```java
public Object getCellEditorValue()
{
   return colorChooser.getColor();
}
```

总结一下，你的自定义编辑器应该执行以下操作：

1. 继承 `AbstractCellEditor` 类并实现 `TableCellEditor` 接口。
2. 定义 `getTableCellEditorComponent` 方法以提供组件。它可以是一个虚拟组件（如果你弹出一个对话框），也可以用于就地编辑的组件，如组合框或文本字段。
3. 定义 `shouldSelectCell`、`stopCellEditing` 和 `cancelCellEditing` 方法来处理编辑过程的开始、完成和取消。`stopCellEditing` 和 `cancelCellEditing` 方法应该调用父类方法以确保监听器被通知。
4. 定义 `getCellEditorValue` 方法返回编辑过程的结果值。

最后，通过调用 `stopCellEditing` 和 `cancelCellEditing` 方法指示用户已完成编辑。在构建颜色对话框时，我们安装了触发这些事件的接受和取消回调。

点击此处查看代码图片

```java
colorDialog = JColorChooser.createDialog(null, "Planet Color", false, colorChooser,
   EventHandler.create(ActionListener.class, this, "stopCellEditing"),
   EventHandler.create(ActionListener.class, this, "cancelCellEditing"));
```

这就自定义编辑器的实现。

你现在知道如何让单元格变得可编辑，以及如何安装编辑器。还有一个剩余的问题——如何用用户编辑的值更新模型。当编辑完成后，`JTable` 类会调用模型的以下方法：

点击此处查看代码图片

```java
void setValueAt(Object value, int r, int c)
```

你需要重写该方法来存储新值。`value` 参数是单元格编辑器返回的对象。如果你实现了单元格编辑器，你就知道从 `getCellEditorValue` 方法返回的对象类型。在 `DefaultCellEditor` 的情况下，该值有三种可能：如果单元格编辑器是复选框，则为 `Boolean`；如果是文本字段，则为 `String`；如果值来自组合框，则它是用户选择的对象。

如果 `value` 对象没有相应的类型，你需要对其进行转换。这最常见发生在文本字段中编辑数字时。在我们的示例中，我们为组合框填充了 `Integer` 对象，不需要转换。

**列表 10.8** `tableCellRender/TableCellFrame.java`

点击此处查看代码图片

```java
package tableCellRender;

import java.awt.*;
import javax.swing.*;
import javax.swing.table.*;

/**
 * 此框架包含一个行星数据的表格。
 */
public class TableCellFrame extends JFrame
{
   private static final int DEFAULT_WIDTH = 600;
   private static final int DEFAULT_HEIGHT = 400;

   public TableCellFrame()
   {
      setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);
      TableModel model = new PlanetTableModel();
      JTable table = new JTable(model);
      table.setRowSelectionAllowed(false);

      // 设置设置渲染器和编辑器
      table.setDefaultRenderer(Color.class, new ColorTableCellRenderer());
      table.setDefaultEditor(Color.class, new ColorTableCellEditor());

      JComboBox<Integer> moonCombo = new JComboBox<>();
      for (int i = 0; i <= 20; i++)
      {
         moonCombo.addItem(i);
      }

      TableColumnModel columnModel = table.getColumnModel();
      TableColumn moonColumn = columnModel.getColumn(PlanetTableModel.MOONS_COLUMN);
      moonColumn.setCellEditor(new DefaultCellEditor(moonCombo));
      moonColumn.setHeaderRenderer(table.getDefaultRenderer(ImageIcon.class));
      moonColumn.setHeaderValue(new ImageIcon(getClass().getResource("Moons.gif")));

      // 显示表格
      table.setRowHeight(100);
      add(new JScrollPane(table), BorderLayout.CENTER);
   }
}
```

**列表 10.9** `tableCellRender/PlanetTableModel.java`

点击此处查看代码图片

```java
package tableCellRender;

import java.awt.*;
import javax.swing.*;
```

```java
import javax.swing.table.*;

/**
 * 行星表格模型指定了行星数据的值、渲染和编辑属性。
 */
public class PlanetTableModel extends AbstractTableModel
{
    public static final int PLANET_COLUMN = 0;
    public static final int MOONS_COLUMN = 2;
    public static final int GASEOUS_COLUMN = 3;
    public static final int COLOR_COLUMN = 4;

    private Object[][] cells = {
        { "水星", 2440.0, 0, false, Color.YELLOW,
            new ImageIcon(getClass().getResource("Mercury.gif")) },
        { "金星", 6052.0, 0, false, Color.YELLOW,
            new ImageIcon(getClass().getResource("Venus.gif")) },
        { "地球", 6378.0, 1, false, Color.BLUE,
            new ImageIcon(getClass().getResource("Earth.gif")) },
        { "火星", 3397.0, 2, false, Color.RED,
            new ImageIcon(getClass().getResource("Mars.gif")) },
        { "木星", 71492.0, 16, true, Color.ORANGE,
            new ImageIcon(getClass().getResource("Jupiter.gif")) },
        { "土星", 60268.0, 18, true, Color.ORANGE,
            new ImageIcon(getClass().getResource("Saturn.gif")) },
        { "天王星", 25559.0, 17, true, Color.BLUE,
            new ImageIcon(getClass().getResource("Uranus.gif")) },
        { "海王星", 24766.0, 8, true, Color.BLUE,
            new ImageIcon(getClass().getResource("Neptune.gif")) },
        { "冥王星", 1137.0, 1, false, Color.BLACK,
            new ImageIcon(getClass().getResource("Pluto.gif")) } };

    private String[] columnNames = { "行星", "半径", "卫星", "气态", "颜色", "图片" };

    public String getColumnName(int c)
    {
        return columnNames[c];
    }

    public Class<?> getColumnClass(int c)
    {
        return cells[0][c].getClass();
    }

    public int getColumnCount()
    {
        return cells[0].length;
    }

    public int getRowCount()
    {
        return cells.length;
    }

    public Object getValueAt(int r, int c)
    {
        return cells[r][c];
    }

    public void setValueAt(Object obj, int r, int c)
    {
        cells[r][c] = obj;
    }

    public boolean isCellEditable(int r, int c)
    {
        return c == PLANET_COLUMN || c == MOONS_COLUMN || c == GASEOUS_COLUMN || c == COLOR_COLUMN;
    }
}
```

### 列表 10.10 `tableCellRender/ColorTableCellRenderer.java`

点击此处查看代码图片

```java
package tableCellRender;

import java.awt.*;
import javax.swing.*;
import javax.swing.table.*;

/**
 * 此渲染器将颜色值渲染为给定颜色的面板。
 */
public class ColorTableCellRenderer extends JPanel implements TableCellRenderer
{
    public ComponentTableCellTableCellComponent(JTable table, Object value, boolean isSelected, boolean hasFocus, int row, int column)
    {
        setBackground((Color) value);
        if (hasFocus) setBorder(UIManager.getBorder("Table.focusHighlightBorder"));
        else setBorder(null);
        return this;
    }
}
```

### 列表 10.11 `tableCellRender/ColorEditor.java`

点击此处查看代码图片



```java
package tableCellRender;

import java.awt.*;
import java.awt.event.*;
import java.beans.*;
import java.util.*;
import javax.swing.*;
import javax.swing.table.*;

/**
 * 此编辑器会弹出一个颜色对话框来编辑单元格。
 */
public class ColorEditor extends AbstractCellEditor implements TableCellEditor
{
    private JColor colorChooser;
    private JDialog colorDialog;
    private JPanel panel;

    public ColorEditor()
    {
        panel = new JPanel();
        // 准备对话框
        colorChooser = new JColor();
        colorDialog = JColorChooser.createDialog(null, "行星颜色", colorChooser,
            EventHandler.create(ActionListener.class, this, "stopCellEditing"),
            EventHandler.create(ActionListener.class, this, "cancelCellEditing"));
    }

    public ComponentTableCellEditorComponent(JTable table, Object value, boolean isSelected, int row, int column)
    {
        // 这里我们获取当前值。我们将其存储在对话框中，以防用户开始编辑
        colorChooser.setColor((Color) value);
        return panel;
    }

    public boolean shouldSelectCell(EventObject anEvent)
    {
        // 开始编辑
        colorDialog.setVisible(true);
        // 告诉调用者可以选择此单元格
        return true;
    }

    public void cancelCellEditing()
    {
        // 取消编辑--隐藏对话框
        colorDialog.setVisible(false);
        super.cancelCellEditing();
    }

    public boolean stopCellEditing()
    {
        // 编辑完成--隐藏对话框
        colorDialog.setVisible(false);
        super.stopCellEditing();
        // 告诉调用者可以使用该值
        return true;
    }

    public Object getCellEditorValue()
    {
        return colorChooser.getColor();
    }
}
```

### `javax.swing.JTable`

- `getDefaultRenderer(Class<?> type)` 获取指定类型的渲染器。
- `getDefaultEditor(Class<?> type)` 获取指定类型的编辑器。

### `javax.swing.table.TableCellRenderer`

- `getTableCellComponent(JTable table, Object value, boolean selected, boolean hasFocus, int row, int column)` 返回一个其 `paint` 方法用于渲染单元格的组件。

![图片](img/00183.jpeg)

### `javax.swing.table.TableColumn`

- `void setCellEditor(TableCellEditor editor)`
- `void setCellRenderer(TableCellRenderer renderer)` 设置该列所有单元格的编辑器或渲染器。
- `void setHeaderRenderer(TableCellRenderer renderer)` 设置该列头部单元格的渲染器。
- `void setHeaderValue(Object value)` 设置该列头部显示的值。

### `javax.swing.DefaultCellEditor`

- `DefaultCellEditor(JComboBox comboBox)` 构建一个通过组合框选择单元格值的编辑器。

### `javax.swing.table.TableCellEditor`

- `getTableCellEditorComponent(JTable table, Object value, boolean selected, int row, int column)` 返回一个其 `paint` 方法用于渲染单元格的组件。

![图片](img/00184.jpeg)

### `javax.swing.CellEditor`

- `boolean isCellEditable(EventObject event)` 返回 `true` 表示该事件适用于启动单元格的编辑过程。
- `boolean shouldSelectCell(EventObject anEvent)` 开始编辑过程。如果编辑后的单元格应该被选中，则返回 `true`。通常你想返回 `true`，但如果不希望编辑过程改变单元格选择，可以返回 `false`。
- `void cancelCellEditing()` 取消编辑过程。你可以放弃部分编辑。
- `boolean stopCellEditing()` 停止编辑过程，并意图使用结果。如果编辑值处于可以获取的状态，则返回 `true`。
- `Object getCellEditorValue()` 返回编辑结果。
- `void addCellEditorListener(CellEditorListener l)`
- `void removeCellEditorListener(CellEditorListener l)`

添加或移除强制性的单元编辑器监听器。

***

## 10.3 树

每一个使用过分层文件系统的计算机用户都见过树形结构显示。当然，目录和文件只是许多树形结构示例中的一个。日常生活中也存在着许多树形结构，例如图 10.15 所示的国家、州和城市的层级结构。

![Image](img/00185.jpeg)

**图 10.15** 国家、州和城市的层级结构

作为程序员，我们经常需要显示树结构。幸运的是，Swing 库提供了一个 `JTree` 类用于此目的。`JTree` 类（连同它的辅助类）负责树的布局以及处理用户对展开和折叠节点的请求。在本节中，你将学习如何使用 `JTree` 类。

与其他许多复杂的 Swing 组件一样，我们必须关注常见且实用的情况，而无法涵盖每一个细节。如果你想实现某些特殊的功能，我们建议你咨询 David M. Geary 编写的 *Graphic Java™, Third Edition* 或 Kim Topley 编写的 *Core Swing*。

在继续之前，让我们确定一些术语（参见图 10.16）。`tree`（树）由 `nodes`（节点）组成。每个节点要么是 `leaf`（叶节点），要么拥有 `child nodes`（子节点）。除根节点外，每个节点恰好有一个 `parent`（父节点）。树只有一个根节点。有时你有一组树，每棵树都有自己的根节点。这样的集合被称为 `forest`（森林）。

![Image](img/00186.jpeg)

**图 10.16** 树术语

### 10.3.1 简单树

在第一个示例程序中，我们将简单地显示一个带有几个节点的树（参见第 642 页上的图 10.18）。与许多其他 Swing 组件一样，你需要提供一个数据模型，由组件为你显示它。要构造一个 `JTree`，需要在构造函数中提供树模型：

```java
TreeModel model = . . .;
JTree tree = new JTree(model);
```

> **注意**
>
> 还有一些通过元素集合构造树的构造函数：
>
> ```java
> JTree(Object[] nodes)
> JTree(Vector<?> nodes)
> JTree(Hashtable<?, ?> nodes) // 值将成为节点
> ```
>
> 这些构造函数并不好用。它们只是构建了一个树的森林，每棵树只有一个节点。第三个构造函数看起来特别没用，因为节点是根据键的哈希值决定的看似随机的顺序出现的。

如何获取树模型？你可以通过创建一个实现 `TreeModel` 接口的类来构建自己的模型。你将在本章的稍后部分看到如何这样做。现在，我们将使用 Swing 库提供的 `DefaultTreeModel`。

要构造默认树模型，你必须提供一个根节点。

```java
TreeNode root = . . .;
DefaultTreeModel model = new DefaultTreeModel(root);
```

`TreeNode` 是另一个接口。用任何实现该接口的类的对象填充默认树模型。现在，我们将使用 Swing 提供的具体节点类——即 `DefaultMutableTreeNode`。该类实现了 `MutableTreeNode` 接口，它是 `TreeNode` 的子接口（参见图 10.17）。

![Image](img/00187.jpeg)

**图 10.17** 树类

默认可树节点持有一个对象——`user object`（用户对象）。树渲染所有节点的用户对象。除非指定渲染器，否则树将显示 `toString` 方法 get 字符串。

在第一个示例中，我们使用字符串作为用户对象。在实践中，你通常会使用更有意义的用户对象填充树。例如，在显示目录树时，使用 `File` 对象作为节点是合理的。

你可以在构造函数中指定用户对象，也可以之后通过 `setUserObject` 方法设置它。

```java
DefaultMutableTreeNode node = new DefaultMutableTreeNode("Texas");
. . .
node.setUserObject("California");
```

接下来，你需要建立节点之间的父子关系。从根节点开始，使用 `add` 方法添加子节点：

```java
DefaultMutableTreeNode root = new DefaultMutableTreeNode("World");
DefaultMutableTreeNode country = new DefaultMutableTreeNode("USA");
root.add(country);
DefaultMutableTreeNode state = new DefaultMutableTreeNode("California");
country.add(state);
```

图 0.18 展示了树的外观。

![Image](img/00188.jpeg)

**图 10.18** 简单树

以这种方式链接所有节点。然后，用根节点构造一个 `DefaultTreeModel`。最后，用树模型构造一个 `JTree`。

```java
DefaultTreeModel treeModel = new DefaultTreeModel(root);
JTree tree = new JTree(treeModel);
```

或者，作为快捷，你可以直接将根节点传递给 `JTree` 构造函数。这样树会自动构造一个默认树模型：

```java
JTree tree = new JTree(root);
```

Listing 10.12 包含了完整的代码。

**Listing 10.12** `tree/SimpleTree.java`

```java
package tree;

import javax.swing.*;
import javax.swing.tree.*;

/**
 * 此框架包含一个手动构造的简单树。
 */
public class SimpleTree extends JFrame
{
    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 200;

    public SimpleTree()
    {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

        // 设置树数据
        DefaultMutableTreeNode root = new DefaultMutableTreeNode("World");
        DefaultMutableTreeNode country = new DefaultMutableTreeNode("USA");
        root.add(country);
        DefaultMutableTreeNode state = new DefaultMutableTreeNode("California");
        country.add(state);
        DefaultMutableTreeNode city = new DefaultMutableTreeNode("San Jose");
        state.add(city);
        city = new DefaultMutableTreeNode("Cupertino");
        state.add(city);
        state = new DefaultMutableTreeNode("Michigan");
        country.add(state);
        city = new DefaultMutableTreeNode("Ann Arbor");
        state.add(city);
        DefaultMutableTreeNode country = new DefaultMutableTreeNode("Germany");
        root.add(country);
        DefaultMutableTreeNode state = new DefaultMutableTreeNode("Schleswig-Holstein");
        country.add(state);
        city = new DefaultMutableTreeNode("Kiel");
        state.add(city);

        // 构造树并将其放入滚动面板
        JTree tree = new JTree(root);
        add(new JScrollPane(tree));
    }
}
```

当你运行程序时，树最初看起来如图 10.19 所示。只有根节点及其子节点是可见的。点击圆形图标（`handles`，句柄）可以打开子树。从句柄图标伸出的线条在子树折叠时指向右侧，在子树展开时指向下方（参见图 10.20）。我们不知道 Metal 外观（look-and-feel）的设计者是怎么想的，但我们将该图标视为门把手。你按下把手即可打开子树。

![Image](img/00189.jpeg)

**图 10.19** 初始树显示

![Image](img/00190.jpeg)

**图 10.20** 折叠和展开的子树

> **备注**
>
> 当然，树的显示取决于所选的外观。我们刚刚描述了 Metal 外观。在 Windows 外观中，句柄具有更熟悉的样式——框中的“-”或“+”（参见图 10.21）。

![Image](img/00191.jpeg)

**图 10.21** 带有 Windows 外观的树

你可以使用以下“魔法咒语”来关闭连接父节点和子节点的线条（参见图 10.22）：

```java
tree.putClientProperty("JTree.lineStyle", "None");
```

![Image](img/00192.jpeg)

**图 10.22** 无连接线的树

相反，若要确保显示线条，请使用：

```java
tree.putClientProperty("JTree.lineStyle", "Angled");
```

另一种线条样式 `"Horizontal"` 如图 10.23 所示。树在显示时，仅用水平线分隔根节点的子节点。我们不太确定这有什么用。

![Image](img/00193.jpeg)

**图 10.23** 带有水平线条样式的树

默认情况下，没有用于折叠树根节点的句柄。如果你喜欢，可以通过以下调用来添加一个：

```java
tree.setShowsRootHandles(true);
```

图 10.24 显示了结果。现在你可以将整棵树折叠到根节点中。

![Image](img/00194.jpeg)

**图 10.24** 带有根句柄的树



相反，你可以完全隐藏根节点。这将会显示一个*森林*（forest）——一组树，每棵树都有自己的根节点。你仍然必须将森林中的所有树连接到一个公共根节点；然后使用指令隐藏根节点：

点击此处查看代码图片

```java
tree.setRootVisible(false);
```

查看图 10.25。有两个根节点分别标记为“USA”和“Germany”。连接它们的根被隐藏了。

![Image](img/00195.jpeg)

**图 10.25** 森林

让我们从根节点转向树的叶节点。注意叶节点的图标与其他节点不同（参见图 10.26）。

![Image](img/00196.jpeg)

**图 10.26** 叶节点和文件夹图标

当树显示时，每个节点都带有一个图标。实际上有三种图标：叶节点图标、展开的非节点图标和折叠的非节点图标。为了简单起见，我们将后两种称为文件夹图标。

节点渲染器需要知道为每个节点使用什么图标。默认的决策过程如下：如果节点的 `isLeaf` 方法返回 `true`，则使用叶节点图标；否则使用文件夹图标。

`DefaultMutableTreeNode` 类的 `isLeaf` 方法在节点没有子节点时返回 `true`。因此，有子节点的获得文件夹图标，没有子节点的节点获得叶节点图标。

有时，这种行为并不适用。假设我们在示例树中添加了“Montana”节点，但不知道如何让它看起来像一个叶节点。我们可以在子类中重写 `isLeaf` 方法并返回 `true`。

```java
@Override
public boolean isLeaf() {
    return true;
}
```

要实现这一行为，你需要找到当前选中的树节点。`JTree` 类有一种意想不到的方式来识别树中的节点。它处理的不是树节点，而是`对象的路径`，称为“树路径”（tree paths）。一个树路径从根节点开始，由一系列子节点组成（参见图 10.28）。

![Image](img/00199.jpeg)

**图 10.28** 树路径

你可能会奇怪，为什么 `JTree` 类需要整个路径。它不能只获取一个 `TreeNode` 并不断调用 `getParent` 方法吗？事实上，`JTree` 类对 `TreeNode` 接口一无所知。该接口从没有被 `TreeModel` 接口使用；它只被 `DefaultTreeModel` 实现类使用。你可以拥有其他的树模型，在其中节点完全没有实现 `TreeNode` 接口。如果你使用管理其他类型对象的树模型，这些对象可能没有 `getParent` 和 `getChild` 方法。它们当然需要彼此之间有某种其他连接。将节点连接在一起是树模型的工作。`JTree` 类本身对它们连接的性质一无所知。出于这个原因，`JTree` 类始终需要与完整的路径一起工作。

`TreePath` 类管理一系列 `Object`（不是 `TreeNode`！）引用。许多 `JTree` 方法会返回 `TreePath` 对象。当你有一个树路径时，你通常只需要知道末端节点，你可以通过 `getLastPathComponent` 方法获取它。例如，要找到树中当前选中的节点，使用 `JTree` 类的 `getSelectionPath` 方法。你会得到一个 `TreePath` 对象，从那里可以检索实际节点。

点击此处查看代码图像

```java
TreePath selectionPath = tree.getSelectionPath();
DefaultMutableTreeNode selectedNode = (DefaultMutableTreeNode) selectionPath.getLastPathComponent();
```

实际上，由于这种特定的查询非常常见，有一个便利方法可以立即给出选中的节点：

点击此处查看代码图像

```java
DefaultMutableTreeNode selectedNode = (DefaultMutableTreeNode) tree.getLastSelectedPathComponent();
```

此方法没有命名为 `getSelectedNode`，因为树并不知道它包含节点——它的树模型只处理对象的路径。

---

![Image](img/00002.jpeg) Note

树路径是 `JTree` 类描述节点的两种方式之一。相当多的 `JTree` 方法接收或返回一个整数索引——“行位置”（row position）。行位置仅仅是节点在树显示中的行号（从 0 开始）。只有可见节点才有行号，如果一个节点之前的其他节点被展开、折叠或修改，该节点的行号就会改变。出于这个原因，你应该避免使用行位置。所有使用行的 `JTree` 方法都有使用树路径代替的等效方法。

---

### 编辑节点

一旦你获取了选中的节点，就可以对它进行编辑。但是，不要简单地向树节点添加子节点：

点击此处查看代码图像

```java
selectedNode.add(newNode); // 不要！
```

如果你改变了节点的结构，你就改变了模型，但关联的视图不会收到通知。你可以自己发送通知，但如果你使用 `DefaultTreeModel` 类的 `insertNodeInto` 方法，模型类会处理这一点。例如，以下调用会将新节点作为该节点的子节点并通知树：

点击此处查看代码图像

```java
model.insertNodeInto(newNode, node, node.getChildCount());
```

`removeNodeParent` 类似的调用会移除该节点并通知视图：

点击此处查看代码图像

```java
model.removeNodeParent(node);
```

如果你保持结构不变但更改了节点，你应该调用以下方法更新树：

点击此处查看代码图像

```java
model.nodeChanged(node);
```

自动通知是使用 `TreeModel` 的优势之一。如果你提供自己的树模型，必须手动实现它。

---

![Image](img/00004.jpeg) 注意

**注意** `DefaultTreeModel` 类有一个 `reload` 方法，可以刷新整个树。但是，如果树是折叠的，用户必须不断调用 `reload` 才能看到变化，这是相当令人困惑的。

---

```java
/**
 * 一个包含树和用于编辑树按钮的框架。
 */
public class TreeEditFrame extends JFrame
{
    private static final int DEFAULT_WIDTH = 400;
    private static final int DEFAULT_HEIGHT = 200;
    private DefaultTreeModel model;
    private JTree tree;

    public TreeEditFrame()
    {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

        // 构建树
        TreeNode root = makeSampleTree();
        model = new DefaultTreeModel(root);
        tree = new JTree(model);
        tree.setEditable(true);

        // 添加树的滚动面板
        JScrollPane scrollPane = new JScrollPane(tree);
        add(scrollPane, BorderLayout.CENTER);
        makeButtons();
    }

    public TreeNode makeSampleTree()
    {
        DefaultMutableTreeNode root = new DefaultMutableTreeNode("World");
        DefaultMutableTreeNode country = new DefaultMutableTreeNode("USA");
        root.add(country);

        DefaultMutableTreeNode state = new DefaultMutableTreeNode("California");
        country.add(state);

        DefaultMutableTreeNode city = new DefaultMutableTreeNode("San Jose");
        state.add(city);

        city = new DefaultMutableTreeNode("San Diego");
        state.add(city);

        state = new DefaultMutableTreeNode("Michigan");
        country.add(state);

        DefaultMutableTreeNode city = new DefaultMutableTreeNode("Ann Arbor");
        state.add(city);

        country = new DefaultMutableTreeNode("Germany");
        root.add(country);

        state = new DefaultMutableTreeNode("Schleswig-Holstein");
        country.add(state);

        DefaultMutableTreeNode city = new DefaultMutableTreeNode("Kiel");
        state.add(city);

        return root;
    }

    /**
     * 创建用于添加兄弟节点、添加子节点和删除节点的按钮。
     */
    public void makeButtons()
    {
        JPanel panel = new JPanel();

        JButton addSiblingButton = new JButton("Add Sibling");
        addSiblingButton.addActionListener(event ->
        {
            DefaultMutableTreeNode selectedNode =
                (DefaultMutableTreeNode) tree.getLastSelectedPathComponent();
            if (selectedNode == null) return;

            DefaultMutableTreeNode parent =
                (DefaultMutableTreeNode) selectedNode.getParent();
            if (parent == null) return;

            DefaultMutableTreeNode newNode = new DefaultMutableTreeNode("New");
            int selectedIndex = parent.getIndex(selectedNode);
            model.insertNodeInto(newNode, parent, selectedIndex + 1);

            // 现在显示节点
            TreeNode[] nodes = model.getPathToRoot(newNode);
            TreePath path = new TreePath(nodes);
            tree.scrollPathToVisible(path);
        });

        panel.add(addSiblingButton);

        JButton addChildButton = new JButton("Add Child");
        addChildButton.addActionListener(event ->
        {
            DefaultMutableTreeNode selectedNode =
                (DefaultMutableTreeNode) tree.getLastSelectedPathComponent();
            if (selectedNode == null) return;

            DefaultMutableTreeNode newNode = new DefaultMutableTreeNode("New");
            model.insertNodeInto(newNode, selectedNode, selectedNode.getChildCount());

            // 现在显示新节点
            TreeNode[] nodes = model.getPathToRoot(newNode);
            TreePath path = new TreePath(nodes);
            tree.scrollPathToVisible(path);
        });

        JButton deleteButton = new JButton("Delete");
        deleteButton.addActionListener(event ->
        {
            DefaultMutableTreeNode selectedNode =
                (DefaultMutableTreeNode) tree.getLastSelectedPathComponent();
            if (selectedNode == null) return;

            DefaultMutableTreeNode parent =
                (DefaultMutableTreeNode) selectedNode.getParent();
            if (parent == null) return;

            DefaultMutableTreeNode newNode = new DefaultMutableTreeNode("New");
            int selectedIndex = parent.getIndex(selectedNode);
            model.insertNodeInto(newNode, parent, selectedIndex + 1);

            // 现在显示节点
            TreeNode[] nodes = model.getPathToRoot(newNode);
            TreePath path = new TreePath(nodes);
            tree.scrollPathToVisible(path);
        });

        panel.add(deleteButton);
    }
}
```

以下是典型的用法模式：

点击此处查看代码图像

```java
Enumeration breadthFirst = node.breadthFirstEnumeration();

while (breadthFirst.hasMoreElements())
{
    // 对 breadthFirst.nextElement(); 执行某些操作
}
```

最后，一个相关方法 `pathFromAncestorEnumeration` 用于找到从祖先节点到给定节点的路径，并枚举该路径上的节点。这没什么大不了——它只是不断调用 `getParent` 直到找到祖先节点，然后以反序呈现该路径。

在我们的下一个示例程序中，我们将节点枚举付诸实践。该程序将显示类的继承树。在框架底部的文本框中输入一个类的名称。该类及其所有的父类都将**添加到树中（请参阅图 10.32）。

![Image](img/00203.jpeg)

**图 10.32** 继承树

在这个示例中，我们利用了树节点的节点对象可以是任意类型的对象的特性。由于我们的节点描述的是类，因此我们在节点中存储了 `Class` 对象。

我们不想重复添加同一个类对象，因此需要检查树中是否已经存在该类。为了检查在树中是否已经存在该类，我们需要使用以下方法：点击此处查看代码图像

```java
public DefaultTreeTreeNode findUserObject(Object obj)
{
    Enumeration e = root.breadthFirstEnumeration();
    while (e.hasMoreElements())
    {
        DefaultMutableTreeNode node = (DefaultMutableTreeNode) e.nextElement();
        if (node.getUserObject().equals(obj))
            return node;
    }
    return null;
}
```

### 10.3.4 渲染节点

在应用程序中，我们经常需要通过渲染器来更改节点的显示方式。最常见的更改是节点的图标。其他的更改可能涉及字体或背景颜色。`DefaultTreeCellRenderer` 类使用 `TreeTree` 属性来渲染节点。



在这个示例中，我们利用了树节点的节点对象可以是任意类型的特性。由于我们的节点描述的是类，因此我们在节点中存储了`Class`对象。

我们不想重复添加同一个类对象，因此需要检查树中是否已经存在该类。为了检查在树中是否已经存在该类，我们需要使用以下方法：点击此处查看代码图像

```java
DefaultTreeRenderer renderer = new DefaultTreeRenderer();
renderer.setLeafIcon(new ImageIcon("blue.gif")); // 用于叶子节点
renderer.setClosedIcon(new ImageIcon("red.gif")); // 用于折叠节点
renderer.setOpenIcon(new ImageIcon("yellow.gif")); // 用于展开节点
tree.setCellRenderer(renderer);
```

你可以在图 10.32 中看到效果。我们不建议更改整棵树的字体或背景颜色——这实际上是外观（look-feel）的工作。

![Image](img/00002.jpeg)

然而，更改树中某些字体以高亮它们是有用的。如果你仔细观察图 10.32，你会注意到`abstract`类被设置为了斜体。

要更改单个节点的外观，请安装树单元渲染器。单元渲染器与我们在本章之前讨论的列表单元渲染器非常相似。`TreeRenderer`接口有一个方法：点击此处查看代码图像

```java
Component getTreeRendererComponent(JTree tree, Object value, boolean selected,
      boolean expanded, boolean leaf, int row, boolean hasFocus)
```

`DefaultTreeCellRenderer`类的`getTreeRendererComponent`方法返回`this`——换句话说，是一个标签（`DefaultTreeCellRenderer`类继承自`JLabel`类）。要自定义组件，请扩展`DefaultTreeCellRenderer`类。按如下重写`getTreeRendererComponent`方法：调用父类方法以准备标签数据，自定义标签属性，最后返回`this`。

点击此处查看代码图像

```java
class MyTreeCellRenderer extends DefaultTreeCellRenderer
{
    public Component getTreeRendererComponent(JTree tree, Object value, boolean selected,
      boolean expanded, boolean leaf, int row, boolean hasFocus)
    {
        Component comp = super.getTreeRendererComponent(tree, value, selected,
              expanded, leaf, row, hasFocus);
        DefaultMutableTreeNode node = (DefaultMutableTreeNode) value;
        // ... (自定义的逻辑)
        return comp;
    }
}
```

你可以通过三种方式自定义显示：

- 使用`DefaultTreeRenderer`更改图标、字体和背景颜色。
- 安装一个扩展`DefaultTreeRenderer`类的渲染器来更改树的属性。
- 安装一个实现`TreeCellRenderer`接口的渲染器来绘制每个节点的图像。

返回按特定顺序访问树模型中所有节点的枚举对象。在广度优先遍历中，距离根节点较近的节点将在较远的节点之前被访问。在深度优先遍历中，在访问节点的兄弟节点之前，会完全枚举该节点的所有子节点。`postOrderEnumeration`方法是`depthFirstEnumeration`的同义词。前序遍历与后序遍历相同，不同之处在于父节点在子节点之前被枚举。

***

### javax.swing.tree.TreeCellRenderer 1.2

- `Component getTreeCellRendererComponent(JTree tree, Object value, boolean selected, boolean expanded, boolean leaf, int row, boolean hasFocus)`

返回一个组件，其`paint`方法被调用以渲染树单元格。

![Image](img/00204.jpeg)

***

### javax.swing.tree.DefaultTreeCellRenderer 1.2

- `void setLeafIcon(Icon icon)`
- `void setOpenIcon(Icon icon)`
- `void setClosedIcon(Icon icon)`

设置叶子节点、展开节点和折叠节点显示的图标。

***

#### 10.3.5 监听树事件

通常情况下，树组件会与其他组件配合使用。当用户选择树节点时，某些信息会在另一个窗口中显示。参见图 10.33 示例。当用户选择一个类时，该类的实例和静态变量将显示在右侧的文本区域。

![Image](img/00205.jpeg)

**图 10.33** 类浏览器

要获得这种行为，你需要安装一个树选择监听器。该监听器必须实现`TreeSelectionListener`接口——该接口包含一个方法：

点击此处查看代码图片

```java
void valueChanged(TreeSelectionEvent event)
```

每当用户选择或取消选择树节点时，该方法就会被调用。

以普通方式将监听器添加到树中：

点击此处查看代码图片

```java
tree.addTreeSelectionListener(listener);
```

你可以指定是否允许用户选择单个节点、连续的节点范围或任意的可能不连续的节点集。`JTree`类使用`TreeSelectionModel`来管理节点选择。你需要获取该模型以将选择状态设置为`SINGLE_TREE_SELECTION`、`CONTIGUOUS_TREE_SELECTION`或`DISCONTIGUOUS_TREE_SELECTION`之一。（不连续选择模式是默认值。）例如，在我们的类浏览器中，我们只允许选择单个类：

点击此处查看代码图片

```java
int mode = TreeSelectionModel.SINGLE_TREE_SELECTION;

tree.getSelectionModel().setSelectionMode(mode);
```

除了设置选择模式外，你不需要担心树选择模型。

***

![Image](img/00002.jpeg) 注意

用户如何选择多个项目取决于外观（look-and-feel）。在 Metal 外观中，在点击某个项目时按住 Ctrl 键将其添加到选择中，如果它当前已选中则将其移除。在点击某个项目时按住 Shift 键可以选择一个项目范围，从上一个选择的项目扩展到新项目。

***

要查找当前选择，请使用`getSelectionPaths`方法查询树：

点击此处查看代码图片

```java
TreePath[] selectedPaths = tree.getSelectionPaths();
```

在 Metal 外观中，在点击某个项目时按住 Ctrl 键将其添加到选择中，如果它当前已选中则将其移除。在点击某个项目时按住 Shift 键可以选择一个项目范围，从上一个选择的项目扩展到新项目。

***

![Image](img/00002.jpeg) 注意

返回一个组件，其`paint`方法被调用以渲染树单元格。

![Image](img/00004.jpeg) 注意

在广度优先遍历中，距离根节点较近的节点将在较远的节点之前被访问。在深度优先遍历中，在访问该节点的兄弟节点之前，会完全枚举该节点的所有子节点。`postOrderEnumeration`方法是`depthFirstEnumeration`的同义词。前序遍历与后序遍历相同，不同之处在于父节点在子节点之前被枚举。

***

### javax.swing.tree.TreeCellRenderer 1.2

- `Component getTreeCellRendererComponent(JTree tree, Object value, boolean selected, boolean expanded, boolean leaf, int row, boolean hasFocus)`

返回一个组件，其`paint`方法被调用以渲染树单元格。

![Image](img/00204.jpeg)

***

### javax.swing.tree.DefaultTreeCellRenderer 1.2

- `void setLeafIcon(Icon icon)`
- `void setOpenIcon(Icon icon)`
- `void setClosedIcon(Icon icon)`

设置叶子节点、展开节点和折叠节点显示的图标。

***

#### 10.3.5 监听树事件

通常情况下，树组件会与其他组件配合使用。当用户选择树节点时，某些信息会在另一个窗口中显示。参见图 10.33 示例。当用户选择一个类时，该类的实例和静态变量将显示在右侧的文本区域。

![Image](img/00205.jpeg)

**图 10.33** 类浏览器

要获得这种行为，你需要安装一个树选择监听器。该监听器必须实现`TreeSelectionListener`接口——该接口包含一个方法：

点击此处查看代码图片

```java
void valueChanged(TreeSelectionEvent event)
```

每当用户选择或取消选择树节点时，该方法就会被调用。

以普通方式将监听器添加到树中：

点击此处查看代码图片

```java
tree.addTreeSelectionListener(listener);
```

你可以指定是否允许用户选择单个节点、连续的节点范围或任意的可能不连续的节点集。`JTree`类使用`TreeSelectionModel`来管理节点选择。你需要获取该模型以将选择状态设置为`SINGLE_TREE_SELECTION`、`CONTIGUOUS_TREE_SELECTION`或`DISCONTIGUOUS_TREE_SELECTION`之一。（不连续选择模式是默认值。）例如，在我们的类浏览器中，我们只允许选择单个类：

点击此处查看代码图片

```java
int mode = TreeSelectionModel.SINGLE_TREE_SELECTION;

tree.getSelectionModel().setSelectionMode(mode);
```

除了设置选择模式外，你不需要担心树选择模型。

***

![Image](img/00002.jpeg) 注意

用户如何选择多个项目取决于外观（look-and-feel）。在 Metal 外观中，在点击某个项目时按住 Ctrl 键将其添加到选择中，如果它当前已选中则将其移除。在点击某个项目时按住 Shift 键可以选择一个项目范围，从上一个选择的项目扩展到新项目。

***

要查找当前选择，请使用`getSelectionPaths`方法查询树：

点击此处查看代码图片

```java
TreePath[] selectedPaths = tree.getSelectionPaths();
```

```java
int mode = TreeSelectionModel.SINGLE_TREE_SELECTION;

tree.getSelectionModel().setSelectionMode(mode);

// 此文本区域持有类描述
textArea = new JTextArea();

// 添加树和文本区域
JPanel panel = new JPanel();
panel.setLayout(new GridLayout(1, 2));
panel.add(new JScrollPane(tree));
panel.add(new JScrollPane(textArea));

add(panel, BorderLayout.CENTER);

addTextField();
```

```java
/**
 * 添加文本字段和“添加”按钮以添加一个新类。
 */
public void addTextField()
{
    JPanel panel = new JPanel();

    ActionListener addListener = event ->
        {
            // 添加文本字段中名称的类
            try
            {
                String text = textField.getText();
                addClass(Class.forName(text)); // 清空文本字段以表示成功
                textField.setText("");
            }
            catch (ClassNotFoundException e)
            {
                JOptionPane.showMessageDialog(null, "未找到类");
            }
        };

    // 新的类名输入到此文本字段
    textField = new JTextField(20);
    textField.addActionListener(addListener);
    panel.add(textField);

    JButton addButton = new JButton("Add");
    addButton.addActionListener(addListener);
    panel.add(addButton);
    add(panel, BorderLayout.SOUTH);
}
```

```java
/**
 * 在树中查找对象。
 * @param obj 要查找的对象
 * @return 包含该对象的节点，如果对象不在树中则返回 null
 */
@SuppressWarnings("unchecked")
public DefaultMutableTreeNode findUserObject(Object obj)
{
    // 查找包含用户对象的节点
    Enumeration<TreeNode> e = (Enumeration<TreeNode>) root.breadthFirstEnumeration();
    while (e.hasMoreElements())
    {
        DefaultMutableTreeNode node = (DefaultMutableTreeNode) e.nextElement();
        if (node.getUserObject().equals(obj)) return node;
    }
    return null;
}
```

```java
/**
 * 添加一个新类以及任何不在树中的父类
 * @param c 要添加的类
 * @return 新添加的节点
 */
public DefaultMutableTreeNode addClass(Class<?> c)
{
    // 向树中添加新类
    // 跳过非类类型
    if (c.isInterface() || c.isPrimitive()) return null;

    // 如果类已经在树中，返回其节点
    DefaultMutableTreeNode node = findUserObject(c);
    if (node != null) return node;

    // 类不存在——首先递归添加类
    Class<?> s = c.getSuperclass();

    DefaultMutableTreeNode parent;
    if (s == null) parent = root;
    else parent = addClass(s);

    // 将类作为子节点添加到父节点
    DefaultMutableTreeNode newNode = new DefaultMutableTreeNode(c);
    model.insertNodeInto(newNode, parent, parent.getChildCount());

    // 使节点变为可见
    TreePath path = new TreePath(model.getPathToRoot(newNode));
    tree.makeVisible(path);

    return newNode;
}
```



```java
/**
 * 返回类字段的描述。
 * @param c 要描述的类
 * @return 包含所有字段类型和名称的字符串
 */
public static String getFieldDescription(Class<?> c)
{
    // 使用反射查找字段的类型和名称
    StringBuilder r = new StringBuilder();
    Field[] fields = c.getDeclaredFields();
    for (int i = 0; i < fields.length; i++)
    {
        Field f = fields[i];
        if ((f.getModifiers() & Modifier.STATIC) != 0) r.append("static ");
        r.append(f.getType().getName());
        r.append(" ");
        r.append(f.getName());
        r.append("\n");
    }
    return r.toString();
}
```

### 列表 10.15：`treeRender/ClassNameTreeRenderer.java`

```java
package treeRender;

import java.awt.*;
import java.lang.reflect.*;
import javax.swing.*;
import javax.swing.tree.*;

/**
 * 此类以正体或斜体渲染类名。抽象类使用斜体。
 */
public class ClassNameTreeCellRenderer extends DefaultTreeCellRenderer
{
    private Font plainFont = null;
    private italicFont = null;

    public Component getTreeCellRendererComponent(JTree tree, Object value, boolean selected,
        boolean expanded, boolean leaf, int row, boolean hasFocus)
    {
        super.getTreeCellRendererComponent(tree, value, selected, expanded, leaf, row, hasFocus);
        // 获取用户对象
        DefaultMutableTreeNode node = (DefaultMutableTreeNode) value;
        Class<?> c = (Class<?>) node.getUserObject();

        // 第一次时，从正体字体派生斜体字体
        if (plainFont == null)
        {
            plainFont = getFont();
        }

        // 树渲染器有时带有空字体的标签调用
        if (plainFont != null) italicFont = plainFont.deriveFont(Font.ITALIC);

        // 如果类是抽象的，则设置为斜体，否则设为正体
        if ((c.getModifiers() & Modifier.ABSTRACT) == 0) setFont(plainFont);
        else setFont(italicFont);

        return this;
    }
}
```

## 引言

该程序的独特之处在于，该树并没有使用 `DefaultTreeModel`。如果你已经有了层次化组织的数据，你可能不想构建一个重复的树，并担心如何保持两棵树的同步。这正是我们这种情况的情况——被检查的对象已经通过对象引用相互链接，因此没有必要复制这种链接结构。

`TreeModel` 接口只有少数方法。第一组方法允许 `JTree` 通过先获取根节点，然后获取子节点来查找树节点。`JTree` 类仅在用户实际展开节点时才调用这些方法。

点击此处查看代码图像：

```
Object getRoot()

int getChildCount(Object parent)

Object getChild(Object parent, int index)
```

这个示例展示了为什么 `TreeModel` 接口和 `JTree` 类本身一样，不需要显式的节点概念。根节点及其子节点可以是任何对象。`TreeModel` 负责告诉 `JTree` 它们是如何连接的。

`TreeModel` 接口的下一个方法是 `getChild` 的反向操作：

点击此处查看代码图像：

```
int getIndexOfChild(Object parent, Object child)
```

实际上，这个方法可以根据前三个方法来实现——参见代码列表 10.16 中的代码。

树模型告诉 `JTree` 哪些节点应该显示为叶子节点：

点击此处查看代码图像：

```
boolean isLeaf(Object node)
```

如果你的代码更改了树模型，则需要通知树以便其重绘。树将自己作为 `TreeModelListener` 添加到模型中。因此，模型必须支持常用的监听管理方法：

点击此处查看代码图像：

```
void addTreeModelListener(TreeModelListener l)

void removeTreeModelListener(TreeModelListener l)
```

你可以在代码列表 10.17 中看到这些方法的实现。

当模型修改树的内容时，它会调用 `TreeModelListener` 接口的四个方法之一：

点击此处查看代码图像：

```
void treeNodesChanged(TreeModelEvent e)

void treeNodesInserted(TreeModelEvent e)

void treeNodesRemoved(TreeModelEvent e)

void treeStructureChanged(TreeModelEvent e)
```

`TreeModelEvent` 对象描述了更改的位置。组装描述插入或删除事件的树模型事件细节相当技术。当你的树确实可以添加或删除节点时，你才需要担心触发这些事件。在代码列表 10.16 中，我们展示了如何通过用新对象替换根节点来触发一个事件。

***

![Image](img/00003.jpeg) **提示**

为了简化事件触发的代码，请使用收集监听器的 `javax.swing.EventListenerList` 方便类。代码列表 10.17 的最后三个方法展示了如何使用该类。

***

最后，如果用户编辑了树节点，你的模型将被调用并传入更改：

点击此处查看代码图像：

```
void valueForPathChanged(TreePath path, Object newValue)
```

如果你不允许编辑，则此方法永远不会被调用。

如果你不需要支持编辑，构建树模型很容易。实现这三个方法：

点击此处查看代码图像：

```
Object getRoot()

int getChildCount(Object parent)

Object getChild(Object parent, int index)
```

这些方法描述了树的结构。如代码列表 10.16 所示，提供其他五个方法的常规实现即可。然后你就可以准备显示你的树了。

现在让我们转向示例程序的实现。我们的树将包含 `Variable` 类型的对象。

***

![Image](img/00002.jpeg) **注意事项**

如果我们使用了 `DefaultTreeModel`，我们的节点将是类型为 `DefaultMutableTreeNode` 的对象，其用户对象类型为 `Variable` 类型。

***

例如，假设我们检查变量：

```java
Employee joe;
```

该变量类型为 `Employee.class`，名称为 `"joe"`，还有一个值——对象引用 `joe` 的值。在代码列表 10.18 中，我们定义了一个 `Variable` 类。

```java
Variable v = new Variable(Employee.class, "joe");
```

点击此处查看代码图像：

```java
Variable v = new Variable(Employee.class, joe);
```

如果类型是基本类型，你必须使用包装类。

点击此处查看代码图像：

```java
Variable v = new Variable(double.class, salary);
```

如果类型是数组，我们将它们收集在 `ArrayList` 中。使用反射，我们列出超类中的所有字段。`Class` 的 `getFields` 方法返回这些字段。`Variable` 的 `toString` 方法格式化标签。

***

![Image](img/00002.jpeg) **提示**

如果类型是数组，我们不显示元素。

***

让我们来看树。前两个方法非常简单。

点击此处查看代码图像：

```java
Object getRoot() {
    return root;
}

int getChildCount(Object parent) {
    return ((Variable) parent).getFields().size();
}
```

`getChild` 方法返回一个新的 `Variable`，用于描述具有索引的字段。`Field` 的 `getType` 和 `getName` 方法产生类型和名称。通过反射，你可以通过 `f.get(parent)` 读取该字段。该方法可能会抛出 `IllegalAccessException`。然而，我们在 `Variable` 构造函数中使所有内容均可访问，因此这种情况不会发生。

这里是 `getChild` 的完整代码：

点击此处查看代码图像：

```java
Object getChild(Object parent, int index) {
    ArrayList fields = ((Variable) parent).getFields();
    Field f = (Field) fields.get(index);
    Object parentValue = ((Variable) parent).getValue();
    try {
        return new Variable(f.getType(), f.getName(), f.get(parentValue));
    } catch (IllegalAccessException e) {
        return null;
    }
}
```

这三个方法向 `JTree` 组件展示了对象树的结构。其余方法是常规的——参见代码列表 10.17 中的源代码。

关于这个树模型有一个惊人的事实：它实际上描述了一棵*无限树*。你可以通过跟踪一个 `WeakReference` 对象来验证这一点。点击名为 `referent` 的变量。它会直接带回到原始对象。你得到了一个相同的子树，你可以再次打开它的 `WeakReference` 对象，循环往复。当然，你无法*存储*无限节点集；树模型仅在用户展开父时按需生成节点。代码列表 10.16 展示了示例程序的框架类。

### 代码列表 10.16：`treeModel/ObjectInspectorFrame.java`

点击此处查看代码图像：

```java
1 package treeModel;

2
3 import java.awt.*;

4 import javax.swing.*;

5
6 /**
7  * 此框架持有对象树。
8  */
```

```java
public class ObjectInspectorFrame extends JFrame
{
    private JTree tree;
    private static final int DEFAULT_WIDTH = 400;
    private static final int DEFAULT_HEIGHT = 300;

    public ObjectInspectorFrame()
    {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

        // we inspect this frame object
        Variable v = new Variable(getClass(), "this", this);
        ObjectTreeModel model = new ObjectTreeModel();
        model.setRoot(v);

        // construct and show tree
        tree = new JTree(model);
        add(new JScrollPane(tree), BorderLayout.CENTER);
    }
}
```

### 代码列表 10.17：`treeModel/ObjectTreeModel.java`

点击此处查看代码图片。



```java
package treeModel;

import java.lang.reflect.*;
import java.util.*;
import javax.swing.event.*;
import javax.swing.tree.*;

/**
 * 此树模型描述了 Java 对象的树结构。子节点是存储在
 * 变量中的对象。
 */
public class ObjectTreeModel implements TreeModel
{
    private Variable root;
    private EventListenerList listenerList = new EventListenerList();

    /**
     * 构建一个空树。
     */
    public ObjectTreeModel()
    {
        root = null;
    }

    /**
     * 将根设置为指定的变量。
     * @param v 此树描述的变量
     */
    public void setRoot(Variable v)
    {
        Variable oldRoot = v;
        root = v;
        fireTreeStructureChanged(oldRoot);
    }

    public Object getRoot()
    {
        return root;
    }

    public int getChildCount(Object parent)
    {
        return ((Variable) parent).getFields().size();
    }

    public Object getChild(Object parent, int index)
    {
        ArrayList<Field> fields = ((Variable) parent).getFields();
        Field f = (Field) fields.get(index);
        Object parentValue = ((Variable) parent).getValue();
        try
        {
            return new Variable(f.getType(), f.getName(), parentValue);
        }
        catch (IllegalAccessException e)
        {
            return null;
        }
    }

    public int getIndexOfChild(Object parent, Object child)
    {
        int n = getChildCount(parent);
        for (int i = 0; i < n; i++)
            if (getChild(parent, i).equals(child)) return i;
        return -1;
    }

    public boolean isLeaf(Object node)
    {
        return getChildCount(node) == 0;
    }

    public void valueForChanged(TreePath path, Object newValue)
    {
    }

    public void addTreeModelListener(TreeModelListener l)
    {
        listenerList.add(TreeModelListener.class, l);
    }

    public void removeTreeModelListener(TreeModelListener l)
    {
        listenerList.remove(TreeModelListener.class, l);
    }

    protected void fireTreeStructureChanged(Object oldRoot)
    {
        TreeModelEvent event = new TreeModelEvent(this, Object[] { oldRoot });
        for (TreeModelListener l : listenerList.getListeners(TreeModelListener.class))
            l.treeStructureChanged(event);
    }
}
```

**列表 10.18** `treeModel/Variable.java`

点击此处查看代码图片

```java
package treeModel;

import java.lang.reflect.*;
import java.util.*;

/**
 * 具有类型、名称和值的变量。
 */
public class Variable
{
    private Class<?> type;
    private String name;
    private Object value;
    private ArrayList<Field> fields;

    /**
     * 构建一个变量。
     * @param aType 类型
     * @param aName 名称
     * @param aValue 值
     */
    public Variable(Class<?> aType, String aName, Object aValue)
    {
        type = aType;
        name = aName;
        value = aValue;
        fields = new ArrayList<>();

        // 如果有类，则查找所有字段，但我们展开字符串和 null
        if (!type.isPrimitive() && !type.isArray() && !type.equals(String.class) && value != null)
        {
            // 从类及其所有父类中获取字段
            for (Class<?> c = value.getClass(); c != null; c = c.getSuperclass())
            {
                Field[] fs = c.getDeclaredFields();
                Accessible.setAccessible(fs, true);

                // 获取所有非静态字段
                for (Field f : fs)
                    if ((f.getModifiers() & Modifier.STATIC) == 0) fields.add(f);
            }
        }
    }

    /**
     * 获取此变量的值。
     * @return 值
     */
    public Object getValue()
    {
        return value;
    }

    /**
     * 获取该变量的所有非静态字段。
     * @return 描述字段的列表
     */
    public ArrayList<Field> getFields()
    {
        return fields;
    }

    public String toString()
    {
        String r = type + " " + name;
    }
}
```

## 10.4 文本组件

图 10.35 显示了 Swing 库包含的所有文本组件。你已经在第一卷第 9 章中见过三个最常用的组件——`JTextField`、`JPasswordField` 和 `JTextArea`。在接下来的章节中，我们将介绍剩余的文本组件。我们讨论 `JSpinner` 组件，它包含一个格式化文本字段以及用于更改内容的微型“向上”和“向下”按钮。

所有文本组件都渲染并编辑存储在实现 `Document` 接口的类的模型对象中的数据。`JTextField` 和 `JTextArea` 组件使用 `PlainDocument`，它仅存储一个纯文本的行序列，不包含任何格式。

`JEditorPane` 可以以多种格式显示和编辑样式化文本（带有字体、颜色等），最常见的是 HTML；请参见第 10.4.4 节中的“使用 `JEditorPane` 显示 HTML”，其位于第 712 页。`StyledDocument` 接口描述了对样式、字体和颜色的额外要求。`HTMLDocument` 类实现了此接口。

`JEditorPane` 的子类 `JTextPane` 同样持有样式化文本以及嵌入的 Swing 组件。我们在本书中不介绍非常复杂的 `JTextPane`，而是建议你参考 Kim Topley 编写的 *Core Swing* 中的详细描述。对于 `JTextPane` 类的典型用法，请查看 JDK 中包含的 StylePad demo。

### 10.4.1 文本组件中的更改跟踪

`Document` 接口的大多数复杂细节仅在你实现自己的文本编辑器时才具有意义。然而，该接口有一个常见的用途：跟踪更改。

有时，你可能希望在用户编辑文本时更新用户界面的一部分，而无需等待用户点击按钮。这里有一个简单的示例。我们显示了三个用于设置颜色红色、蓝色和绿色部分的文本字段。每当文本字段的内容变化时，颜色就应该被更新。图 10.36 显示了列表 10.19 的运行程序。

![Image](img/00210.jpeg)

**图 10.36** 文本字段中的更改跟踪

首先，注意监控按键并不是一个好主意。某些按键（如方向键）并不会改变文本。更重要的是，可以通过鼠标手势进行更新（例如 X11 中的“鼠标中键粘贴”）。相反，你应该通过安装一个 *文档监听器（document listener）* 来让 *文档*（而不是文本组件）在数据发生变化时通知你：

点击此处查看代码图像

```java
textField.getDocument().addDocumentListener(listener);
```

当文本发生变化时，会调用以下 `DocumentListener` 方法之一：

点击此处查看代码图像

```java
void insertUpdate(DocumentEvent event)

void removeUpdate(DocumentEvent event)

void changedUpdate(DocumentEvent event)
```

前两个方法在字符插入或删除时被调用。第三个方法对于文本字段完全不会被调用。对于更复杂的文档类型，当发生其他更改（如格式更改）时将会调用它。遗憾的是，没有单一的回调函数来通知你文本已更改——通常你并不关心它是如何改变的。也没有适配器类。因此，你的文档监听器必须实现所有三个方法。以下是我们在示例程序中所做的：

点击此处查看代码图像

```java
DocumentListener listener = new DocumentListener()
   {
      public void insertUpdate(DocumentEvent event) { setColor(); }
      public void removeUpdate(DocumentEvent event) { setColor(); }
      public void changedUpdate(DocumentEvent event) {}

    }
```

`setColor` 方法使用 `getText` 方法从文本字段获取当前的用户输入字符串并设置颜色。

我们的程序有一个局限性。用户可以在文本字段中输入格式异常的输入，例如 `"twenty"`，或者留空字段。目前，我们捕获 `parseInt` 方法抛出的 `NumberFormatException`；当文本字段输入不是数字时，我们简单地更新颜色。在下一节中，你将看到如何防止用户从一开始输入无效输入。

> **注意**
>
> 与其监听文档事件，不如为文本字段添加动作事件监听器（action event listener）。每当用户按下回车键时，动作监听器就会通知。我们不推荐这种方法，因为用户在完成数据输入后并不总是记得按回车。如果你使用动作监听器，还应该安装焦点监听器（focus listener），以便跟踪用户离开文本字段的时机。

**列表 10.19** `textChange/ColorFrame.java`

点击此处查看代码图像

```java
1   package textChange;
2

3   import java.awt.*;
4   import javax.swing.*;
5   import javax.swing.event.*;
6
7   /**
8   * 一个带有三个文本字段的框架，用于设置背景颜色。
   */
9   public class ColorFrame extends JFrame
10  private JPanel panel;
11  private JTextField redField;
12  private JTextField greenField;
13  private JTextField blueField;
14
15  public ColorFrame()
16  {
17    DocumentListener listener = new DocumentListener()
18    {
19      public void insertUpdate(DocumentEvent event) { setColor(); }
20      public void removeUpdate(DocumentEvent event) { setColor(); }
21      public void changedUpdate(DocumentEvent event) {}
22    };
23
24    panel = new JPanel();
25
26    panel.add(new JLabel("Red:"));
27    redField = new JTextField("255", 3);
28    panel.add(redField);
29    redField.getDocument().addDocumentListener(listener);
30
31    panel.add(new JLabel("Green:"));
32    greenField = new JTextField("255", 3);
33    panel.add(greenField);
34    greenField.getDocument().addDocumentListener(listener);
35
36    panel.add(new JLabel("Blue:"));
37    blueField = new JTextField("255", 3);
38    panel.add(blueField);
39    blueField.getDocument().addDocumentListener(listener);
40
41    add(panel);
42    pack();
43  }
44
45  /**
46  * 根据文本字段存储的值设置背景颜色。
47  */
48  public void setColor()
49  {
50    try
51    {
52      int red = Integer.parseInt(redField.getText().trim());
53      int green = Integer.parseInt(greenField.getText().trim());
54      int blue = Integer.parseInt(blueField.getText().trim());
55      panel.setBackground(new Color(red, green, blue));
56    }
57    catch (NumberFormatException e)
58    {
59      // 如果输入无法解析，则不设置颜色
60    }
61  }
62}
```

在上一个示例程序中，我们希望用户输入数字而不是任意字符串。也就是说，用户只允许输入数字 `0` 到 `9` 以及一个连字符（`-`）。如果存在连字符，它必须是输入字符串的 `first` 符号。

从表面上看，这个输入验证任务听起来很简单。我们可以为文本字段安装一个按键监听器，并忽略所有不是数字或连字符的按键事件。遗憾的是，这种简单的方法虽然经常推荐用于输入验证，但在实践中效果并不理想。首先，并不是所有有效输入字符的组合都是有效的数字。例如，`--3` 和 `3-3` 是无效的，尽管它们是由有效输入字符组成的。但更重要的是，还有其他更改文本的方法并不涉及输入字符键。根据外观和感觉，某些按键组合可以用于剪切、复制和粘贴文本。例如，在 Metal 外观中，`Ctrl+V` 键组合会将剪贴板的内容粘贴到文本字段中。这意味着，我们还需要监控用户是否粘贴了无效字符。通过过滤按键来防止无效内容看起来像是一项真正的苦差。这显然不是应用程序程序员应该去担心的事情。



可能令人惊讶的是，在 Java SE 1.4 之前，还没有输入数值的组件。从 Core Java 第一版开始，我们提供了一个 `IntTextField` 的实现——一个用于输入格式化整数的文本字段。在随后的版本中，我们更改了实现，以从每个 Java 版本中添加的各种半成品验证方案中提取尽可能有限的优势。最后，在 Java SE 1.4 中，Swing 设计师正面面对这个问题，并提供了一个多用途的 `JFormattedTextField` 类，它不仅可以用于数值输入，还可以用于日期甚至更晦涩的格式化值，如 IP 地址。

## 10.4.2.1 整数输入

让我们从一个简单的案例开始：用于整数输入的文本字段。

点击此处查看代码图像

```java
JFormattedTextField intField = new JFormattedTextField(NumberFormat.getIntegerInstance());
```

`NumberFormat.getIntegerInstance` 返回一个使用当前区域设置格式化整数的格式化对象。在美国区域设置中，逗号用作分隔符，允许用户输入如 `1,729` 这样的值。第 7 章详细解释了如何选择其他区域设置。

与任何文本字段一样，你可以设置列数：

点击此处查看代码图像

```java
intField.setColumns(6);
```

你可以使用 `setValue` 方法设置默认值。该方法接受一个 `Object` 参数，因此你需要将默认的 `int` 值封装在一个 `Integer` 对象中：

点击此处查看代码图像

```java
intField.setValue(new Integer(100));
```

通常，用户会在多个文本字段中提供输入，然后点击按钮读取所有值。当按钮被点击时，你可以使用 `getValue` 方法获取用户提供的值。该方法返回一个 `Object` 结果，你需要将其强制转换为适当类型。如果用户编辑了值，`JFormattedTextField` 会返回一个 `Long` 类型的对象。然而，如果用户没有做任何更改，则返回原始的 `Integer` 对象。因此，你应该将返回值强制转换为通用的父类 `Number`：

点击此处查看代码图像

```java
Number value = (Number) intField.getValue();
int v = value.intValue();
```

在考虑用户提供非法输入会发生什么之前，格式化文本字段并不很有趣。那是下一节的主题。

## 10.4.2.2 失去焦点时的行为

考虑用户向文本字段提供输入时发生的情况。用户输入并最终决定离开字段，可能是通过鼠标点击另一个组件。这时，文本字段`失去焦点`。I 型光标不再显示在文本字段中，按键输入将指向不同的组件。

当格式化文本字段失去焦点时，格式化器查看用户生成的文本字符串。如果格式化器知道如何将文本字符串转换为对象，则文本是有效的。否则它是无效的。你可以使用 `isEditValid` 方法检查文本字段当前的内容是否有效。

失去焦点时的默认行为被称为“提交或撤销”（commit or revert）。如果文本字符串是有效的，则会被`提交`。格式化器将其转换为对象。该对象成为字段的当前值（即你在上一节中看到的 `getValue` 方法的返回值）。然后该值被转换回字符串，成为字段中可见的文本字符串。例如，整数格式化器识别输入 `1729` 为有效，将当前值设置为 `new Long(1729)`，并将其转换回带有小数点逗号的字符串：`1,729`。

相反，如果文本字符串无效，当前值将不会改变，且文本字段将`撤销`到表示旧值的字符串。例如，如果用户输入了错误值，如 `x1`，当文本字段失去焦点时，旧值将恢复。

> ![图像](img/00002.jpeg) **注意**
>
> 整数格式化器如果文本字符串以整数开头，则认为它是有效的。例如，`1729x` 是一个有效字符串。它被转换为数字 1729，然后格式化为字符串 `1,729`。

你可以使用 `setFocusLostBehavior` 方法设置其他行为。`commit` 行为与默认行为有细微差别。如果文本字符串无效，则文本字符串和字段值都保持不变——它们现在处于不同步状态。`persist` 行为更加保守。即使文本字符串是有效的，文本字段或当前值也不会改变。你需要调用 `commitEdit`、`setValue` 或 `setText` 来让它们恢复同步。最后，还有一种 `revert` 行为，它似乎完全没有用：每当失去焦点时，用户输入将被忽略，文本字符串撤销到旧值。

通常，默认的“提交或撤销”行为是合理的。只有一个潜在问题。假设一个对话框包含一个用于整数值的文本字段。用户输入了一个带有前空格的字符串 `"1729"` 并点击了 OK 按钮。前空格导致该数字无效，字段值撤销到旧值。OK 按钮的监听器获取字段值并关闭对话框。用户并不知道新值被拒绝了。在这种情况下，选择 `commit` 行为并让 OK 按钮监听器在关闭对话框之前检查所有字段编辑是否有效是恰当的。

## 10.4.2.3 过滤器

格式化文本字段的基本功能非常简单，足以满足大多数用例。然而，你可以添加一些改进。也许你可能想要完全防止用户输入非数字字符。你可以通过 `document filter`（文档过滤器）来实现这一行为。记住，在模型-视图-控制器（MVC）架构中，控制器将输入事件翻译为修改文本字段底层文档的命令——即存储在 `PlainDocument` 对象中的文本字符串。例如，每当控制器处理导致文本插入到文档的命令时，它会调用“插入字符串”（`insert string`）命令。要插入的字符串可以是单个字符，也可以是剪贴缓冲区的内容。文档过滤器可以拦截此命令并修改字符串，或完全取消插入。

以下是一个过滤器的 `insertString` 方法的代码，该方法分析要插入的字符串，并仅插入数字或负号的字符。（该代码处理了补充 Unicode 字符，如第一卷第 3 章中所示。有关 `StringBuilder` 类，请参阅第 2 章。）

点击此处查看代码图像

```java
public void insertString(FilterBypass fb, int offset, String string, AttributeSet attr)
    throws BadLocationException
{
    StringBuilder builder = new StringBuilder(string);
    for (int i = builder.length() - 1; i >= 0; i--)
    {
        int cp = builder.codePointAt(i);
        if (!Character.isDigit(cp) && cp != '-')
        {
            builder.deleteCharAt(i);
            if (Character.isSupplementaryCodePoint(cp))
            {
                i--;
                builder.deleteCharAt(i);
            }
        }
    }
    super.insertString(fb, offset, builder.toString(), attr);
}
```

你还应该重写 `DocumentFilter` 类的 `replace` 方法——它在文本被选中并替换时被调用。`replace` 方法的实现非常直观——请参阅第 698 页上的列表 10.21。

现在你需要安装文档过滤器。遗憾的是，没有直接的方法来实现。你需要重写格式化器类的 `getDocumentFilter` 方法，并将该格式化器类的对象传递给 `JFormattedTextField`。整数文本字段使用 `InternationalFormatter`，该对象使用 `NumberFormat.getIntegerInstance()` 进行初始化。以下是安装格式化器以产生所需过滤器的方法：

点击此处查看代码图像

```java
JFormattedTextField intField = new JFormattedTextField(new
    InternationalFormatter(NumberFormat.getIntegerInstance())
    {
        private DocumentFilter filter = new IntFilter();
        protected DocumentFilter getDocumentFilter()
        {
            return filter;
        }
    });
```

> ![图像](img/00002.jpeg) **注意**
>
> Java SE 文档指出，`DocumentFilter` 类的发明是为了避免子类化。在 Java SE 1.3 之前，文本字段中的过滤是通过扩展 `PlainDocument` 类并重写 `insertString` 和 `replace` 方法实现的。现在 `PlainDocument` 类使用了一个可插拔的过滤器。这是一个极大的改进。如果过滤器在格式化器类中也是可插拔的，那就更完美了。遗憾的是，并非如此，我们必须对格式化器进行子类化。

尝试本节末尾的 `FormatTest` 示例程序。第三个文本字段安装了过滤器。你可以只插入数字或负号（`-`）。请注意，你仍然可以输入如 `1-2-3` 等无效字符串。通常情况下，通过过滤无法避免所有无效字符串。例如，字符串“`-`”是无效的，但过滤器无法拒绝它，因为它是合法字符串“`-1`”的前缀。尽管过滤器不能提供完美的保护，但使用它们是有意义的。

> ![图像](img/00002.jpeg) **提示**
>
> 过滤的另一个用途是将所有字符转换为大写。在过滤器的 `insertString` 和 `replace` 方法中，将要插入的字符串转换为大写。

## 10.4.2 验证器

另一种潜在有用的机制是提醒用户输入无效内容。你可以为任何 `JComponent` 附加一个验证器（verifier）。如果组件失去焦点，就会查询验证器。如果验证器报告内容无效，组件将立即重新聚焦。以下是一个附加到 `JFormattedTextField` 上的验证器：

点击此处查看代码图像

```java
intField.setInputVerifier(new InputVerifier()
{
    public boolean verify(JComponent component)
    {
        JFormattedTextField field = (JFormattedTextField) component;
        return field.isEditValid();
    }
});
```

尝试输入一个无效数字（如 `x129`）并按下 Tab 键或用鼠标点击另一个文本字段。该字段会立即重新聚焦。然而，如果你点击 OK 按钮，动作监听器会调用 `getValue`，它会报告上一个有效值。验证器并不是万无一失的。用户可能希望在不修复无效输入的情况下点击取消。这样做有一个原因：动作监听器会通知组件。

## 其他标准格式化器

除了整数格式化器，`JFormattedTextField` 还支持其他几种格式化器。`NumberFormat` 类具有静态方法：

点击此处查看代码图像

```java
getNumberInstance
getCurrencyInstance
getPercentInstance
```

产生浮点数、货币值和百分比的格式化器。例如，你可以通过调用以下代码获取用于输入货币值的文本字段：

```java
JFormattedTextField currencyField = new JFormattedTextField(NumberFormat.getCurrencyInstance());
```

要编辑日期和时间，调用 `DateFormat` 类的静态方法之一：

点击此处查看代码图像

```java
getDateInstance
getTimeInstance
getDateTimeInstance
```

例如：

```java
JFormattedTextField dateField = new JFormattedTextField(DateFormat.getDateInstance());
```

此字段以默认或“中等”格式编辑日期，例如 Aug 5, 2007。你也可以通过调用来选择“短”格式，例如 8/5/07：

```java
DateFormat.getDateInstance(DateFormat.SHORT)
```

`DefaultFormatter` 可以格式化任何具有带字符串参数构造函数且匹配的 `toString` 方法的类对象。例如，`URL` 类拥有一个 `URL(String)` 构造函数，可以用于从字符串构造 URL，例如：

点击此处查看代码图片

```java
URL url = new URL("http://horstmann.com");
```

因此，你可以使用 `DefaultFormatter` 来格式化 `URL` 对象。格式化器会在字段值上调用 `toString` 方法来初始化字段文本。当字段失去焦点时，格式化器会使用带有 `String` 参数的构造函数，构建一个与当前值相同类型的新对象。如果该构造函数抛出异常，则该编辑无效。你可以在示例程序中通过输入一个不以 `http:` 等前缀开头的 URL 来尝试一下。

> ![Image](img/00002.jpeg) **注意**
>
> 默认情况下，`DefaultFormatter` 处于 `overwrite mode`（覆盖模式）。这与其他格式化器不同，且并不十分有用。调用 `setOverwriteMode(false)` 可以关闭覆盖模式。

最后，`MaskFormatter` 对于包含某些常量和某些变量字符的固定模式非常有用。例如，社会安全号码（如 078`-`05`-`1120`）可以使用以下方式化：

点击此处查看代码图片

```java
new MaskFormatter("###-##-####")
```

`#` 符号表示单个数字。表 10.3 显示了可以在掩码格式化器使用的符号。

![Image](img/00212.jpeg)

**表 10.3** `MaskFormatter` 符号

可以通过调用 `MaskFormatter` 类的一个方法来限制可以输入字段的字符：

点击此处查看代码图片

```java
setValidCharacters
setInvalidCharacters
```

例如，为了读取一个字母等级（如 `A+` 或 `F`），你可以使用：

点击此处查看代码图片

```java
MaskFormatter formatter = new MaskFormatter("U*");
formatter.setValidCharacters("ABCDF+- ");
```

然而，没有办法指定第二个字符不能是字母。

注意，掩码格式化器格式化的字符串长度与模式完全相同。如果用户在编辑过程中删除了字符，它们将被替换为 `placeholder character`（占位符）。默认占位符字符是空格，但你可以通过 `setPlaceholderCharacter` 方法更改它，例如：

点击此处查看代码图片

```java
formatter.setPlaceholderCharacter('0');
```

默认情况下，掩码格式化器处于覆盖模式（overtype mode），这非常非常直观——请在示例程序中尝试。此外，请注意，光标位置会跳过掩码中的固定字符。

掩码格式化器对于社会安全号码或美国电话号码等刚性模式非常有效。但请注意，掩码模式中不允许任何变化。例如，你不能将掩码格式化器用于位数可变的国际电话号码。

## 10.4.2.6 自定义格式化器

如果没有一个标准格式化器合适，那么定义自己的格式化器是非常容易的。考虑 4 字节 IP 地址，例如：

`130.65.86.66`

你不能使用 `MaskFormatter`，因为每个字节可能由一个、两个或三个数字表示。此外，我们希望在格式化器中检查每个字节的值最多为 255。

要定义自己的格式化器，请扩展 `DefaultFormatter` 类并重写方法：

点击此处查看代码图片

```java
String valueToString(Object value)
Object stringToValue(String text)
```

第一个方法将字段值转换为文本字段中显示的字符串。第二个方法解析用户输入的文本并将其转换回对象。如果任一个方法检测到错误，都应该抛出 `ParseException`。

在我们的示例程序中，我们将 IP 地址存储在长度为 4 的 `byte[]` 数组中。`valueToString` 方法形成一个用点分隔字节的字符串。注意，`byte` 值是有符号的，范围在 –128 到 127 之间。（例如，在 IP 地址 130.65.86.66 中，第一个字节实际上是值为 –126 的字节）。要将负字节值转换为无符号整数值，加上 256。

点击此处查看代码图片



```java
public String valueToString(Object value) throws ParseException
{
    if (!(value instanceof byte[]))
      throw new ParseException("Not a byte[]", 0);
    byte[] a = (byte[]) value;
    if (a.length != 4)
      throw new ParseException("Length != 4", 0);
    StringBuilder builder = new StringBuilder();
    for (int i = 0; i < 4; i++) {
        int b = a[i];
        if (b < 0) b += 256;
        builder.append(String.valueOf(b));
        if (i < 3) builder.append('.');
    }
    return builder.toString();
}
```

相反，`stringToValue` 方法解析字符串，如果字符串有效则产生一个 `byte[]` 对象。如果无效，则抛出 `ParseException`。

点击此处查看代码图片

```java
public Object stringToValue(String text) throws ParseException
{
    StringTokenizer tokenizer = new StringTokenizer(text, ".");
    byte[] a = new byte[4];
    for (int i = 0; i < 4; i++) {
        int b = 0;
        try {
            b = Integer.parseInt(tokenizer.nextToken());
        } catch (NumberFormatException e) {
            throw new ParseException("Not an integer", 0);
        }
        if (b < 0 || b >= 256)
            throw new ParseException("Byte of range", 0);
        a[i] = (byte) b;
    }
    return a;
}
```

尝试示例程序中的 IP 地址字段。如果你输入一个无效地址，字段将恢复到上一个有效地址。完整的格式化器显示在列表 10.22 中。

在列表 10.20 中的程序展示了各种格式化文本字段的操作（参见图 10.37）。点击 OK 按钮从字段中获取当前值。

![Image](img/00213.jpeg)

**图 10.37** `FormatTest` 程序

![Image](img/00002.jpeg)

> **注意**
>
> “Swing Connection”在线通讯报有一篇短文描述了一种可以匹配任何正则表达式的格式化器。参见 `www.oracle.com/technetwork/java/reftf-138955.html`。

**列表 10.20** `textFormat/FormatTestFrame.java`

点击此处查看代码图片

```java
package textFormat;

import java.awt.*;
import java.net.*;
import java.text.*;
import java.util.*;

import javax.swing.*;
import javax.swing.text.*;

/**
 * 带有一组格式化文本字段和一个显示字段值的按钮的框架。
 */
public class FormatTestFrame extends JFrame
{
    private DocumentFilter filter = new IntFilter();
    private JButton okButton;
    private JPanel mainPanel;

    public FormatTestFrame()
    {
        JPanel buttonPanel = new JPanel();
        okButton = new JButton("Ok");
        buttonPanel.add(okButton);
        add(buttonPanel, BorderLayout.SOUTH);

        mainPanel = new JPanel();
        mainPanel.setLayout(new GridLayout(0, 3));
        add(mainPanel, BorderLayout.CENTER);

        JFormattedTextField intField = new JFormattedTextField(NumberFormat.getIntegerInstance());
        intField.setValue(new Integer(100));
        addRow("Number:", intField);

        JFormattedTextField intField2 = new JFormattedTextField(NumberFormat.getIntegerInstance());
        intField2.setValue(new Integer(100));
        intField2.setFocusLostBehavior(JFormattedTextField.COMMIT);
        addRow("Number (Commit behavior):", intField2);
    }
}
```

```java
JFormattedTextField intField3 = new JFormattedTextField(new InternationalFormatter(
    NumberFormat.getIntegerInstance())
{
    protected DocumentFilter getDocumentFilter()
    {
        return filter;
    }
});
intField3.setValue(new Integer(100));
addRow("Filtered Number", intField3);

JFormattedTextField intField4 = new JFormattedTextField(NumberFormat.getIntegerInstance());
intField4.setValue(new Integer(100));
intField4.setInputVerifier(new InputVerifier()
{
    public boolean verify(JComponent component)
    {
        JFormattedTextField field = (JFormattedTextField) component;
        return field.isEditValid();
    }
});
addRow("Verified Number:", intField4);

JFormattedTextField currencyField = new JFormattedTextField(NumberFormat
    .getCurrencyInstance());
currencyField.setValue(new Double(10));
addRow("Currency:", currencyField);

JFormattedTextField dateField = new JFormattedTextField(DateFormat.getDateInstance());
dateField.setValue(new Date());
addRow("Date (default):", dateField);

DateFormat format = DateFormat.getDateInstance(DateFormat.SHORT);
format.setLenient(false);
JFormattedTextField dateField2 = new JFormattedTextField(format);
dateField2.setValue(new Date());
addRow("Date (short, not lenient):", dateField2);

try
{
    DefaultFormatter formatter = new DefaultFormatter();
    formatter.setOverwriteMode(false);
    JFormattedTextField urlField = new JFormattedTextField(formatter);
    urlField.setValue(new URL("http://java.sun.com"));
    addRow("URL:", urlField);
}
catch (MalformedURLException ex)
{
    ex.printStackTrace();
}
try
{
    MaskFormatter formatter = new MaskFormatter("###-##-####");
    formatter.setPlaceholderCharacter('0');
    JFormattedTextField ssnField = new JFormattedTextField(formatter);
    ssnField.setValue("078-05-120");
    addRow("SSN Mask:", ssnField);
}
catch (ParseException ex)
{
    ex.printStackTrace();
}

JFormattedTextField ipField = new JFormattedTextField(new IPAddressFormatter());
ipField.setValue(new byte[] { (byte) 130, 65, 86, 66 });
addRow("IP Address:", ipField);
pack();
}

/**
 * 向主面板添加一行行。
 * @param labelText 字段的标签文本
 * @param field 示例字段
 */
public void addRow(String labelText, final JFormattedTextField field)
{
    mainPanel.add(new JLabel(labelText));
    mainPanel.add(field);
    final JLabel valueLabel = new JLabel();
    mainPanel.add(valueLabel);
    okButton.addActionListener(event ->
    {
        Object value = field.getValue();
        Class<?> cl = value.getClass();
        String text = null;
        if (cl.isArray())
        {
            if (cl.getComponentType().isPrimitive())
            {
                try
                {
                    text = Arrays.class.getMethod("toString", cl).invoke(null, value).toString();
                }
                catch (ReflectiveOperationException ex)
                {
                    // ignore exceptions
                }
            }
            else text = Arrays.toString((Object[]) value);
        }
        else text = value.toString();
        valueLabel.setText(text);
    });
}
```

### 列表 10.21 `textFormat/IntFilter.java`

点击此处查看代码图片

```java
package textFormat;

import javax.swing.text.*;

/**
 * 一个限制输入内容为数字和 '-' 符号的过滤器。
 */
public class IntFilter extends DocumentFilter
{
    public void insertString(FilterBypass fb, int offset, String string, AttributeSet attr)
        throws BadLocationException
    {
        StringBuilder builder = new StringBuilder(string);
        for (int i = builder.length() - 1; i >= 0; i--)
        {
            int cp = builder.codePointAt(i);
            if (!Character.isDigit(cp) && cp != '-')
            {
                builder.deleteCharAt(i);
                if (Character.isSupplementaryCodePoint(cp))
                {
                    i--;
                    builder.deleteCharAt(i);
                }
            }
        }
        super.insertString(fb, offset, builder.toString(), attr);
    }

    public void replace(FilterBypass fb, int offset, int length, String string, AttributeSet attr)
        throws BadLocationException
    {
        if (string != null)
        {
            StringBuilder builder = new StringBuilder(string);
            for (int i = builder.length() - 1; i >= 0; i--)
            {
                int cp = builder.codePointAt(i);
                if (!Character.isDigit(cp) && cp != '-')
                {
                    builder.deleteCharAt(i);
                    if (Character.isSupplementaryCodePoint(cp))
                    {
                        i--;
                        builder.deleteCharAt(i);
                    }
                }
            }
            string = builder.toString();
        }
        super.replace(fb, offset, length, string, attr);
    }
}
```

### 列表 10.22 `textFormat/IPAddressFormatter.java`

点击此处查看代码图片



```java
package textFormat;

import java.text.*;
import java.util.*;
import javax.swing.text.*;

/**
 * 用于 a.b.c.d 格式的 4 字节地址的格式化器
 */
public class IPAddressFormatter extends DefaultFormatter
{
    public String valueToString(Object value)
    {
        if (!(value instanceof byte[])) throw new ParseException("Not byte[]", 0);
        byte[] a = (byte[]) value;
        if (a.length != 4) throw new ParseException("Length != 4", 0);
        StringBuilder builder = new StringBuilder();
        for (int i = 0; i < 4; i++)
        {
            int b = a[i];
            if (b < 0) b += 256;
            builder.append(String.valueOf(b));
            if (i < 3) builder.append('.');
        }
        return builder.toString();
    }

    public Object stringToValue(String text) throws ParseException
    {
        StringTokenizer tokenizer = new StringTokenizer(text, ".");
        byte[] a = new byte[4];
        for (int i = 0; i < 4; i++)
        {
            int b = 0;
            if (!tokenizer.hasMoreTokens()) throw new ParseException("Too few bytes", 0);
            try
            {
                b = Integer.parseInt(tokenizer.nextToken());
            }
            catch (NumberFormatException e)
            {
                throw new ParseException("Not an integer", 0);
            }
        }
        return a;
    }
}
```

```java
if (b < 0 || b >= 256) throw new ParseException("Byte out of range", 0);
a[i] = (byte) b;
if (tokenizer.hasMoreTokens()) throw new ParseException("Too many bytes", 0);
return a;
```

### `javax.swing.JFormattedTextField` 1.4

- `JFormattedTextField(Format fmt)` 构建一个使用指定格式的文本字段。
- `JFormattedTextField(JFormattedTextField.AbstractFormatter formatter)` 构造一个使用指定格式化器的文本字段。注意 `DefaultFormatter` 和 `InternationalFormatter` 是 `JFormattedTextField.AbstractFormatter` 的子类。
- `Object getValue()` 返回字段的当前有效值。注意这可能不对应正在编辑的字符串。
- `void setValue(Object value)` 尝试设置给定对象的值。如果格式化器无法将对象转换为字符串，则尝试失败。
- `void commitEdit()` 尝试从编辑的字符串设置字段的有效值。如果格式化器无法转换字符串，则可能会失败。
- `boolean isEditValid()` 检查编辑的字符串是否代表一个有效值。
- `int getFocusLostBehavior()`
- `void setFocusLostBehavior(int behavior)` 获取或设置“失去焦点”的行为。`behavior` 的合法值是 `JFormattedTextField` 类中的常量 `COMMIT_OR_REVERT`、`REVERT`、`COMMIT` 和 `PERSIST`。

### `javax.swing.JFormattedTextField.AbstractFormatter` 1.4

- `abstract String valueToString(Object value)` 将值转换为可编辑的字符串。如果 `value` 不适合此格式化器，则抛出 `ParseException`。
- `abstract Object stringToValue(String s)` 将字符串转换为值。如果 `s` 不符合相应的格式，则抛出 `ParseException`。
- `DocumentFilter getDocumentFilter()` 覆盖此方法以提供一个限制文本字段输入的文档过滤器。返回 `null` 表示不需要过滤。

### `javax.swing.text.DefaultFormatter` 1.3

- `boolean getOverwriteMode()`
- `void setOverwriteMode(boolean mode)` 获取或设置覆盖模式。如果 `mode` 为 `true`，在编辑文本时新字符将覆盖现有字符。

### `javax.swing.text.DocumentFilter` 1.4

- `void insertString(DocumentFilter.FilterBypass bypass, int offset, String text, AttributeSet attrib)` 在字符串插入文档之前调用。你可以覆盖此方法并修改字符串。你可以通过不调用 `super.insertString` 或调用 `bypass` 方法在不经过过滤的情况下修改文档来禁用插入。

![Image](img/00214.jpeg)

- `void replace(DocumentFilter.FilterBypass bypass, int offset, int length, String text, AttributeSet attrib)` 在文档的部分被新字符串替换之前调用。你可以覆盖此方法并修改字符串。你可以通过不调用 `super.replace` 或调用 `bypass` 方法在不经过过滤的情况下修改文档来禁用替换。

![Image](img/00215.jpeg)

- `void remove(DocumentFilter.FilterBypass bypass, int offset, int length)` 在文档的一部分被删除之前调用。如果需要分析删除的影响，请调用 `bypass.getDocument()` 获取文档。

![Image](img/00216.jpeg)

### `javax.swing.text.MaskFormatter` 1.4

- `MaskFormatter(String mask)` 使用给定的掩码构建掩码格式化器。有关掩码中的符号，请参阅第 692 页上的表 10.3。
- `String getValidCharacters()`
- `void setValidCharacters(String characters)` 获取或设置有效的编辑字符。掩码的变量部分仅接受给定字符串中的字符。
- `String getInvalidCharacters()`。给定字符串中的任何字符都不接受输入。
- `char getPlaceholderCharacter()`
- `void setPlaceholderCharacter(char ch)` 获取或设置用于用户尚未提供的掩码变量字符的占位符。默认占位符是空格。
- `String getPlaceholder()`
- `void setPlaceholder(String s)` 获取或设置占位符字符串。如果用户未提供掩码的所有变量字符，则使用其末尾。如果它为 `null` 或比掩码短，则占位符填充剩余的输入。
- `boolean getValueContainsLiteralCharacters()`
- `void setValueContainsLiteralCharacters(boolean b)` 获取或设置“值包含字面字符”标志。如果此标志为 `true`，字段值包含掩码的字面（非变量）部分。如果为 `false`，则移除字面字符。默认为 `true`。

### 10.4.3 `JSpinner` 组件

`JSpinner` 是包含一个文本字段和侧两个小按钮的组件。点击按钮时，文本字段的值会增加或减少（参见图 10.38）。

![Image](img/00217.jpeg)

**图 10.38** `JSpinner` 组件的若干变体

计数器中的值可以是数字、日期、列表中的值，或者在最通用的情况下任何可以确定前驱和后继的序列。`JSpinner` 类为这些情况定义标准模型。你可以定义自己的模型来描述任意序列。默认情况下，计数器管理整数，并递 1 增加。你可以通过调用 `getValue` 方法获取当前值。该方法返回一个 `Object`。将其强制转换为 `Integer` 并检索值。

此处查看图片

```java
JSpinner defaultSpinner = new JSpinner();
...
int value = (Integer) defaultSpinner.getValue();
```

你可以将增量改为非 1 的值，并提供下界和上限。这是一个起始值为 5、增量为 0.5、边界在 0 到 10 之间的计数器：

此处查看图片

```java
JSpinner boundedSpinner = new JSpinner(new SpinnerNumberModel(5, 0, 10, 0.5));
```

有两个 `SpinnerNumberModel` 构造函数，一个 `int` 参数和一个 `double` 参数。如果任何参数是浮点数，则使用第二个。它将 own 值设置为 `Double` 对象。

计数器不仅限于数值。你可以让计数器遍历任何集合。只需将 `SpinnerListModel` 传递给 `JSpinner` 构造函数。你可以从数组或实现 `List` 接口的类（如 `ArrayList`）构造 `SpinnerListModel`。在我们的示例程序中，显示了一个带有所有可用字体名的计数器。

此处查看图片

```java
String[] fonts = GraphicsEnvironment.getLocalGraphicsEnvironment().getAvailableFontNames();
JSpinner listSpinner = new JSpinner(new SpinnerListModel(fonts));
```

然而，我们发现迭代方向略令人困惑，因为它与组合框相反。在组合框中，较高的值位于较低值下方，因此你会期望向下箭头导航到较高的值。但计数器增加数组索引，使得向上箭头产生较高的值。`SpinnerListModel` 中没有反转遍历顺序的规定，但一个临时的匿名子类产生所需的结果：

此处查看图片

```java
JSpinner reverseListSpinner = new JSpinner(
    new SpinnerListModel(fonts)
    {
        public Object getNextValue() {
            return super.getPreviousValue();
        }
    }
);
```

```java
public Object getPreviousValue()
{
    return super.getNextValue();
}
```

尝试这两种版本，看看你觉得哪一个更直观。

计数器（spinner）的另一个良好用途是用于用户可以递增或减少的日期。你可以通过以下调用获取一个用今天日期初始化的计数器：

点击此处查看代码图片

```java
JSpinner dateSpinner = new JSpinner(new SpinnerDateModel());
```

然而，如果你查看图 10.38，你会发现计数器的文本同时显示了日期和时间，例如：

`8/05/07 9:05 PM`

对于日期选择器来说，时间没有任何意义。事实证明，让计数器只显示日期是困难的。这里是“魔法咒语”：

点击此处查看代码图片

```java
JSpinner betterDateSpinner = new JSpinner(new SpinnerDateModel());
String pattern = ((SimpleDateFormat) DateFormat.getDateInstance()).toPattern();
betterDateSpinner.setEditor(new JSpinner.DateEditor(betterDateSpinner, pattern));
```

使用同样的方法，你也可以制作一个时间选择器：

点击此处查看代码图片

```java
JSpinner timeSpinner = new JSpinner(new SpinnerDateModel());
pattern = ((SimpleDateFormat) DateFormat.getTimeInstance(DateFormat.SHORT)).toPattern();
timeSpinner.setEditor(new JSpinner.DateEditor(timeSpinner, pattern));
```

你可以通过定义自己的计数器模型，在计数器中显示任意序列。在我们的示例程序中，有一个计数器，可以遍历字符串“meat”的所有排列。你可以通过点击计数器按钮切换到“mate”、“meta”、“team”以及其余 24 种排列中的任何一个。

要定义你自己的模型，请扩展 `AbstractSpinnerModel` 类并定义以下四个方法：

点击此处查看代码图片

```java
Object getValue()
void setValue(Object value)
Object getNextValue()
Object getPreviousValue()
```

`getValue` 方法返回模型存储的值。`setValue` 方法设置新值。如果新值不合适，它应该抛出 `IllegalArgumentException`。

***

![Image](img/00004.jpeg) **注意**

`setValue` 方法在设置新值后必须调用 `fireStateChanged` 方法。否则，计数器字段将不会更新。

***

`getNextValue` 和 `getPreviousValue` 方法返回应该位于当前值之后或之前的值，如果已到达遍历末尾，则返回 `null`。

***

![Image](img/00004.jpeg) **注意**

`getNextValue` 和 `getPreviousValue` 方法不应该改变当前值。当用户点击计数器的向上箭头时，会调用 `getNextValue` 方法。如果返回值不为 `null`，则通过调用 `setValue` 来进行设置。

***

在示例程序中，我们使用标准算法来确定下一个和上一个排列（参见列表 10.24）。算法的细节并不重要。

列表 10.23 显示了如何生成各种类型的计数器。点击 OK 按钮查看计数器值。

**列表 10.23** `spinner/SpinnerFrame.java`

点击此处查看代码图片

***



```java
1    package spinner;
2
3    import java.awt.*;
4    import java.awt.event.*;
5    import java.text.*;
6    import javax.swing.*;
7
8    /**
9    * 一个带有多个计数器的面板，以及一个用于显示计数器
10   * 值的框架框（frame）。
11   */
12   public class SpinnerFrame extends JFrame
13   {
14      private JPanel mainPanel;
15      private JButton okButton;
16
17      public SpinnerFrame()
18      {
19          JPanel buttonPanel = new JPanel();
20          okButton = new JButton("Ok");
21          buttonPanel.add(okButton);
22          add(buttonPanel, BorderLayout.SOUTH);
23
24          mainPanel = new JPanel();
25          mainPanel.setLayout(new GridLayout(0, 3));
26          add(mainPanel, BorderLayout.CENTER);
27
28          JSpinner defaultSpinner = new JSpinner();
29          addRow("Default", defaultSpinner);
30
31          JSpinner boundedSpinner = new JSpinner(new NumberModel(5, 10, 0.5));
32          addRow("Bounded", boundedSpinner);
33
34          String[] fonts = GraphicsEnvironment.getLocalEnvironment()
35          .getAvailableFontNames();
36
37          JSpinner listSpinner = new JSpinner(new SpinnerList(fonts));
38          addRow("List", listSpinner);
39
40          JSpinner reverseListSpinner = new JSpinner(new SpinnerList(fonts)
41          {
42              public Object getNextValue() { return super.getPreviousValue(); }
43              public Object getPreviousValue() { return super.getNextValue(); }
44          });
45          addRow("Reverse List", reverseListSpinner);
46
47          JSpinner dateSpinner = new JSpinner(new SpinnerDateModel());
48          addRow("Date", dateSpinner);
49
50          JSpinner betterDateSpinner = new JSpinner(new SpinnerDateModel());
51          String pattern = ((SimpleDateFormat) DateFormat.getDateInstance()).toPattern();
52          betterDateSpinner.setEditor(new JSpinner.DateEditor(betterDateSpinner, pattern));
53          addRow("Better Date", betterDateSpinner);
54
55          JSpinner timeSpinner = new JSpinner(new SpinnerDateModel());
56          pattern = ((SimpleDateFormat) DateFormat.getTimeInstance(DateFormat.SHORT)).toPattern();
57          timeSpinner.setEditor(new JSpinner.DateEditor(timeSpinner, pattern));
58          addRow("Time", timeSpinner);
59
60          JSpinner permSpinner = new JSpinner(new PermutationSpinnerModel("meat"));
61          addRow("Word permutations", permSpinner);
62          pack();
63      }
64
65      /**
66      * 向主面板添加行。
67      * @param labelText 计数器的标签文本
68      * @param spinner 示例计数器
69      */
70      public void addRow(String labelText, final JSpinner spinner)
71      {
72          mainPanel.add(new JLabel(labelText));
73          mainPanel.add(spinner);
74          final JLabel valueLabel = new JLabel();
75          mainPanel.add(valueLabel);
76          okButton.addActionListener(event ->
77          {
78              Object value = spinner.getValue();
79              valueLabel.setText(value.toString());
80          });
81      }
82  }
```

**列表 10.24** `spinner/PermutationSpinnerModel.java` 点击此处查看代码图片

***

```java
1    package spinner;
2
3    import javax.swing.*;
4
5    /**
6    * 一个动态生成排列的模型。
7    */
8    public class PermutationSpinnerModel extends AbstractSpinnerModel
9    {
10      private String word;
11
12      /**
13      * 构造模型。
14      * @param w 要排列的单词
15      */
16      public PermutationSpinnerModel(String w)
17      {
18          word = w;
19      }
20
21      public Object getValue()
22      {
23          return word;
24      }
25
26      public void setValue(Object value)
27      {
28          if (!(value instanceof String)) throw new IllegalArgumentException();
29          word = (String) value;
30          fireStateChanged();
31      }
32
33      public Object getNextValue()
34      {
35          int[] codePoints = toCodePointArray(word);
36          for (int i = codePoints.length - 1; i > 0; i--)
37          {
38              if (codePoints[i - 1] < codePoints[i])
39              {
40                  int j = codePoints.length - 1;
41                  while (codePoints[i - 1] > codePoints[j])
42                  j--;
43                  swap(codePoints, i - 1, j);
44                  reverse(codePoints, i, codePoints.length - 1);
45
46                  return new String(codePoints, 0, codePoints.length);
47              }
48          }
49      }
50  }
```

```java
        }
    }
        reverse(codePoints, 0, codePoints.length - 1);
        return new String(codePoints, 0, codePoints.length);
    }

    public Object getPreviousValue()
    {
        int[] codePoints = toCodePointArray(word);
        for (int i = codePoints.length - 1; i > 0; i--)
        {
            if (codePoints[i - 1] > codePoints[i])
            {
                int j = codePoints.length - 1;
                while (codePoints[i - 1] < codePoints[j])
                    j--;
                swap(codePoints, i - 1, j);
                reverse(codePoints, i, codePoints.length - 1);
                return new String(codePoints, 0, codePoints.length);
            }
        }
        reverse(codePoints, 0, codePoints.length - 1);
        return new String(codePoints, 0, codePoints.length);
    }

    private static int[] toCodePointArray(String str)
    {
        int[] codePoints = new int[str.codePointCount(0, str.length())];
        for (int i = 0, j = 0; i < str.length(); i++, j++)
        {
            int cp = str.codePointAt(i);
            if (Character.isSupplementaryCodePoint(cp)) i++;
            codePoints[j] = cp;
        }
        return codePoints;
    }

    private static void swap(int[] a, int i, int j)
    {
        int temp = a[i];
        a[i] = a[j];
        a[j] = temp;
    }

    private static void reverse(int[] a, int i, int j)
    {
        while (i < j)
        {
            swap(a, i, j);
            i++;
            j--;
        }
    }
```

`javax.swing.JSpinner`（1.4）

- `JSpinner()` 构造一个初始值为 `0`、增量为 `1` 且无边界限制的整数数值计数器。
- `JSpinner(SpinnerModel model)` 构造一个使用给定数据的计数器。
- `getValue()` 获取计数器的当前值。
- `setValue(Object value)` 尝试设置计数器的值。如果模型不接受该值，则抛出 `IllegalArgumentException`。
- `setEditor(JComponent editor)` 设置用于编辑计数器值的组件。

`javax.swing.SpinnerNumberModel`（1.4）

- `SpinnerNumberModel(int initval, int minimum, int maximum, int step)`
- `SpinnerNumberModel(double initval, double minimum, double maximum, double step)`

这些构造函数产生管理 `Integer` 或 `Double` 值的模型。使用 `Integer` 和 `Double` 类的 `MIN_VALUE` 和 `MAX_VALUE` 常量表示无边界值。

`javax.swing.SpinnerListModel`（1.4）

- `SpinnerListModel(Object[] values)`
- `SpinnerListModel(List values)`

这些构造函数产生从给定值列表中选择值的模型。

`javax.swing.SpinnerDateModel`（1.4）

- `SpinnerDateModel()` 构造一个以今天为初始值的日期模型，没有下限或上限，且增量为 `Calendar.DAY_OF_MONTH`。
- `SpinnerDateModel(Date initval, Comparable minimum, Comparable maximum, int step)`

`java.text.SimpleDateFormat`（1.1）

- `toPattern()` 获取此日期格式化编辑模式。典型的模式为 `"yyyy-MM-dd"`。关于模式的更多细节，请参考 Java SE 文档。

`javax.swing.JSpinner.DateEditor`（1.4）

- `DateEditor(JSpinner spinner, String pattern)` 为计数器构造一个日期编辑器。

`javax.swing.AbstractSpinnerModel`（1.4）

- `getValue()` 获取模型的当前值。
- `setValue(Object value)` 尝试为模型设置新值。如果值不可接受，则抛出 `IllegalArgumentException`。在重写此方法时，你应该在设置新值后调用 `fireStateChanged`。
- `getNextValue()` 计算（但不设置）该模型定义的序列中的下一个值。
- `getPreviousValue()` 计算（但不设置）该模型定义的序列中的上一个值。

#### 10.4.4 使用 `JEditorPane` 显示 `HTML`

与在此之前讨论的文本组件不同，`JEditorPane` 可以显示和编辑样式化文本，特别是 HTML 和 RTF。（RTF 是许多微软应用程序用于文档交换的“富文本格式”。这是一种文档记录较少的格式，在微软自己的应用程序之间工作效果并不良好。我们在本书中不涵盖 RTF 的功能。）

坦率地说，`JEditorPane` 的功能并不如人们所希望那样。HTML 渲染器可以显示简单文件，但在处理网络上常见的许多复杂页面时会卡顿。HTML 编辑器功能有限且不稳定。

`JEditorPane` 的一个可行应用是以 HTML 格式显示程序帮助文档。通过控制你提供的帮助文件，你可以避开 `JEditorPane` 无法良好显示的功能。

**注意：** 有关更多工业级帮助系统的信息，请查看 `http://javahelp.java.net` JavaHelp。

`Listing 10.25` 中的程序包含一个显示 HTML 页面内容的编辑器面板。在文本框中输入 URL。URL 必须以 `http:` 或 `file:` 开头。然后点击 `Load` 按钮。选定的 HTML 页面将显示在编辑器面板中（见 `Figure 10.39`）。

该程序实际上是非常简单的浏览器。当然，它不具备你从真实浏览器中预期的缓存或书签列表等舒适功能。超链接是激活的：如果你点击一个链接，应用程序将加载它。后退按钮返回上一个页面。



`JEditorPane` 变得可编辑。你可以输入文本并使用退格键删除文本。该组件还理解 `Ctrl+X`、`Ctrl+C` 和 `Ctrl+V` 剪切、复制和粘贴快捷键。然而，你必须编写大量的代码才能添加对字体和格式的支持。

**提示：** 默认情况下，`JEditorPane` 处于编辑模式。调用 `setEditable(false)` 可以将其关闭。

你在示例中看到的编辑器面板功能易于使用。`setPage` 方法加载一个新的文档。例如：

```java
JEditorPane editorPane = new JEditorPane();
editorPane.setPage(url);
```

API 文档说明 `setPage` 是否在单独线程中加载新文档（这通常是你所需要的——`JEditorPane` 速度并不快）。但是，你可以通过以下咒语强制在单独线程中加载：

```java
AbstractDocument doc = (AbstractDocument) editorPane.getDocument();
doc.setAsynchronousLoadPriority(0);
```

该组件甚至不显示 applet！`JEditorPane` 类继承自 `JTextComponent` 类。因此，你也可以调用 `setText` 方法——它只是显示纯文本。

要监听超链接点击，请添加一个 `HyperlinkListener`。`HyperlinkListener` 接口有一个方法 `hyperlinkUpdate`，当用户移动到链接上或点击链接时就会调用该方法。该方法有一个类型为 `HyperlinkEvent` 的参数。

你需要调用 `getEventType` 方法来确定发生了什么种事件。有三种可能的返回值：

- `HyperlinkEvent.EventType.ACTIVATED`
- `HyperlinkEvent.EventType.ENTERED`
- `HyperlinkEvent.EventType.EXITED`

第一个值表示用户点击了超链接。在这种情况下，你通常想要打开新链接。你可以使用第二个和第三个值在鼠标悬停在链接上时提供一些视觉反馈，例如工具提示。

> **注意：** 完全不知道为什么 `HyperlinkListener` 接口中没有三个独立的方法来处理激活、进入和退出，这真是个大谜团。

`HyperlinkEvent` 类的 `getURL` 方法返回超链接的 URL。例如，这里展示了如何安装一个跟踪用户激活的链接的超链接监听器：

```java
editorPane.addHyperlinkListener(event ->
{
    if (event.getEventType() == HyperlinkEvent.EventType.ACTIVATED)
    {
        try
        {
            // 记住 URL 用于返回
            urlStack.push(event.getURL().toString());
            // 在字段中显示 URL
            url.setText(event.getURL().toString());
            editorPane.setPage(event.getURL());
        }
        catch (IOException e)
        {
            editorPane.setText("Exception: " + e);
        }
    }
});
```

事件处理器简单地获取 URL 并更新编辑器面板。`setPage` 方法可能会抛出 `IOException`。在这种情况下，我们以纯文本的形式显示错误消息。

Listing 10.25 中的程序显示了组合成 HTML 帮助系统所需的所有功能。在底层，`JEditorPane` 比树和表格组件还要复杂。然而，如果你不是在编写文本编辑器或自定义文本格式的渲染器，这种复杂性就对你隐藏了。

**Listing 10.25** `editorPane/EditorPaneFrame.java`

```java
package editorPane;

import java.awt.*;
import java.awt.event.*;
import java.io.*;
import java.util.*;
import javax.swing.*;
import javax.swing.event.*;

/**
 * 此框架包含一个编辑器面板、一个用于输入 URL 并加载文档的字段和按钮，
 * 以及一个用于返回之前加载文档的返回按钮。
 */
public class EditorPaneFrame extends JFrame
{
    private static final int DEFAULT_WIDTH = 600;
    private static final int DEFAULT_HEIGHT = 400;

    public EditorPaneFrame()
    {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

        final Stack<String> urlStack = new Stack<>();
        final JEditorPane editorPane = new JEditorPane();
        final JTextField url = new JTextField(30);

        // 设置超链接监听器
        editorPane.setEditable(false);
        editorPane.addHyperlinkListener(event ->
        {
            if (event.getEventType() == HyperlinkEvent.EventType.ACTIVATED)
            {
                try
                {
                    // 记住 URL 用于返回
                    urlStack.push(event.getURL().toString());
                    // 在字段中显示 URL
                    url.setText(event.getURL().toString());
                    editorPane.setPage(event.getURL());
                }
                catch (IOException e)
                {
                    editorPane.setText("Exception: " + e);
                }
            }
        });

        // 设置用于切换模式的复选框
        final JCheckBox editable = new JCheckBox();
        editable.addActionListener(event -> editorPane.setEditable(editable.isSelected()));

        // 设置 URL 的加载按钮
        ActionListener listener = event ->
        {
            try
            {
                // 记住 URL 用于返回
                urlStack.push(url.getText());
                editorPane.setPage(url.getText());
            }
            catch (IOException e)
            {
                editorPane.setText("Exception: " + e);
            }
        };

        JButton loadButton = new JButton("Load");
        loadButton.addActionListener(listener);
        url.addActionListener(listener);

        // 设置返回按钮和按钮动作
        JButton backButton = new JButton("Back");
        backButton.addActionListener(event ->
        {
            if (urlStack.size() <= 1) return;
            try
            {
                // 从返回获取 URL
                urlStack.pop();
                // 在文本字段中显示 URL
                String urlString = urlStack.peek();
                url.setText(urlString);
                editorPane.setPage(urlString);
            }
            catch (IOException e)
            {
                editorPane.setText("Exception: " + e);
            }
        });

        // 将所有组件放入一个面板
        JPanel panel = new JPanel();
        panel.add(new JLabel("URL"));
        panel.add(url);
        panel.add(loadButton);
        panel.add(backButton);
        panel.add(new JLabel("Editable"));

        add(new JScrollPane(editorPane), BorderLayout.CENTER);
        // 将面板添加到南部
        add(panel, BorderLayout.SOUTH);
    }
}
```

`javax.swing.JEditorPane`

- `void setPage(URL url)` 将 `url` 加载到编辑器面板。
- `void addHyperlinkListener(LinkListener listener)` 为此编辑器面板添加超链接监听器。

`javax.swing.event.HyperlinkListener`

- `void hyperlinkUpdate(HyperlinkEvent event)` 当超链接被选中时被调用。

`javax.swing.event.HyperlinkEvent`

- `URL getURL()` 返回选中超链接的 URL。

### 10.5 进度指示

在后续章节中，我们将讨论三个用于指示进度的类。`JProgressBar` 是一个指示进度的 Swing 组件。`ProgressMonitor` 是一个包含进度条的对话框。`ProgressMonitorInputStream` 在读取流时显示进度监控对话框。

#### 10.5.1 进度条

*进度条*是一个简单的组件——一个部分填充颜色的矩形，用于指示操作的进度。默认情况下，进度由字符串“*n*%”指示。你可以在图 10.41 中看到：

```java
progressBar = new JProgressBar(SwingConstants.VERTICAL, 0, 1000);
```

你还可以使用 `setMinimum` 和 `setMaximum` 方法设置最小和最大。

与滑动条不同，进度条无法由用户调整。你的程序需要调用 `setValue` 来更新它。

进度条计算完成百分比并显示字符串“n%”。如果你想显示不同的字符串，可以使用 `setString` 方法提供它：

```java
if (progressBar.getValue() > 900)
    progressBar.setString("Almost Done");
```

Listing 10.26 中的程序显示了一个监控模拟耗时活动的进度条。

`SimulatedActivity` 类每秒将值 `current` 增加 10 次。当它达到目标值时，活动即完成。我们使用 `SwingWorker` 类来实现该活动，并在 `process` 方法中更新进度条。`SwingWorker` 从事件分发线程（event dispatch thread）调用该方法，因此更新进度条是安全的。（有关 Swing 中线程安全的更多信息，请参见第一卷第 14 章。）

Java SE 1.4 增加了对 `indeterminate`（不确定）进度条的支持，它显示一种表示正在进行某种进度的动画，而不指定完成百分比。这就是你在浏览器中看到的那种进度条——它表示浏览器正在等待服务器，且不知道需要等多久。要显示“不确定等待”动画，请调用 `setIndeterminate` 方法。

Listing 10.26 显示了完整的程序代码。

**Listing 10.26** `progressBar/ProgressBarFrame.java`

```java
package progressBar;

import java.awt.*;
import java.util.List;
import javax.swing.*;

/**
 * 包含一个用于启动模拟活动的按钮、一个进度条以及一个用于
 * 活动输出的文本区域的框架框。
 */
public class ProgressBarFrame extends JFrame
{
    public static final int TEXT_ROWS = 10;
    public static final int TEXT_COLUMNS = 40;

    private JButton startButton;
    private JProgressBar progressBar;
    private JCheckBox checkBox;
    private JTextArea textArea;
    private SimulatedActivity activity;

    public ProgressBarFrame()
    {
        // 此文本区域持有活动输出
        textArea = new JTextArea(TEXT_ROWS, TEXT_COLUMNS);

        // 设置带有按钮和进度条的面板
        final int MAX = 1000;
        JPanel panel = new JPanel();
        startButton = new JButton("Start");
        progressBar = new JProgressBar(0, MAX);
        progressBar.setStringPainted(true);
        panel.add(startButton);
        panel.add(progressBar);

        checkBox = new JCheckBox("indeterminate");
        checkBox.addActionListener(event ->
        {
            progressBar.setIndeterminate(checkBox.isSelected());
            progressBar.setStringPainted(!progressBar.isIndeterminate());
        });
        panel.add(checkBox);

        add(new JScrollPane(textArea), BorderLayout.CENTER);
        add(panel, BorderLayout.SOUTH);

        // 设置动作
        startButton.addActionListener(event ->
        {
            startButton.setEnabled(false);
            activity = new SimulatedActivity(MAX);
            activity.execute();
        });

        pack();
    }

    class SimulatedActivity extends SwingWorker<Void, Integer>
    {
        private int current;
        private int target;

        /**
         * 构建模拟活动，将计数器从 0 增加到给定的目标。
         * @param t 计数器的目标值
         */
        public SimulatedActivity(int t)
        {
            current = 0;
            target = t;
        }
    }
}
```



```java
public SimulatedActivity(int t) {
    current = 0;
    target = t;
}

protected Void doInBackground() throws Exception {
    try {
        while (current < target) {
            Thread.sleep(100);
            current++;
            publish(current);
        }
    } catch (InterruptedException e) {
    }
    return null;
}

protected void process(List<Integer> chunks) {
    for (Integer chunk : chunks) {
        textArea.append(chunk + "\n");
        progressBar.setValue(chunk);
    }
}
```

#### 10.5.2 进度监控器

进度条是一个可以放在窗口内的简单组件。相比之下，`ProgressMonitor` 是一个完整的对话框，其中包含一个进度条（参见 10.42）。该监控器包含一个取消按钮。如果你点击它，对话框就会关闭。通过提供以下内容来构造监控器：

- 对话框应该弹出的父组件
- 显示在对话框中的对象（应该是字符串、图标或组件）
- 显示在对象下方的可选备注
- 最小值和最大值

然而，进度监控器本身无法测量进度或取消活动。你仍然需要通过调用`setProgress`方法设置进度（这等同于`JProgressBar`的`setValue`方法）。当监控的活动结束时，调用`close`方法关闭对话框。你可以通过调用`start`重用同一个对话框。

使用进度监控器最大的问题是处理取消请求。你不能为取消按钮附加事件处理器。相反，你需要定期调用`isCanceled`方法来查看用户是否点击了按钮。如果你的工作线程可以无限阻塞（例如，当从网络读取输入时），它就无法监控取消按钮。在我们的示例程序中，我们将向你展示如何为此目的使用计时器。我们还将让计时器负责更新进度。

如果你运行列表 10.27 中的程序，你可以观察到进度监控器对话框的一个有趣特性。对话框不会立即出现。相反，它等待一段时间，查看活动是否已经完成，或者可能在短于对话框出现所需的时间内完成。

使用`setMillisToPopup`方法设置构造对话框对象和决定是否显示弹出窗口之间等待的毫秒数。默认值为 500 毫秒。`setMillisToPopup`是你对对话框弹出所需时间的估计。Swing 设计师将此值默认设置为 2 秒。显然，他们考虑到了 Swing 对话框并不总是像我们所希望的那样敏捷。你可能不需要触动这个值。

```java
package progressMonitor;

import java.awt.*;
import javax.swing.*;

class ProgressMonitorFrame extends JFrame {
```

```java
public static final int TEXT_ROWS = 10;
public static final int TEXT_COLUMNS = 40;
private Timer cancelMonitor;
private JButton startButton;
private ProgressMonitor progressDialog;
private JTextArea textArea;
private SimulatedActivity activity;

public ProgressMonitorFrame() {
    // 此文本区域用于保存活动输出
    textArea = new JTextArea(TEXT_ROWS, TEXT_COLUMNS);

    // 设置按钮面板
    JPanel panel = new JPanel();
    startButton = new JButton("Start");
    panel.add(startButton);
    add(new JScrollPane(textArea), BorderLayout.CENTER);
    add(panel, BorderLayout.SOUTH);

    // 设置按钮动作监听器
    startButton.addActionListener(event -> {
        startButton.setEnabled(false);
        final int MAX = 1000;

        // 启动活动
        activity = new SimulatedActivity(MAX);
        activity.execute();

        // 启动进度对话框
        progressDialog = new ProgressMonitor(
            ProgressMonitorFrame.this,
            "Waiting for Simulated Activity",
            null,
            0,
            MAX
        );
        cancelMonitor.start();
    });

    // 设置定时器动作
    cancelMonitor = new Timer(500, event -> {
        if (progressDialog.isCanceled()) {
            activity.cancel(true);
            startButton.setEnabled(true);
        } else if (activity.isDone()) {
            progressDialog.close();
            startButton.setEnabled(true);
        } else {
            progressDialog.setProgress(activity.getProgress());
        }
    });

    pack();
}

class SimulatedActivity extends SwingWorker<Void, Integer> {
    private int current;
    private int target;

    /**
     * 构造模拟活动，该计数器从 0 增加到
     * target。
     * @param t 计数器的目标值
     */
    public SimulatedActivity(int t) {
        current = 0;
        target = t;
    }

    protected Void doInBackground() throws Exception {
        try {
            while (current < target) {
                Thread.sleep(100);
                current++;
                textArea.append(current + "\n");
                setProgress(current);
            }
        } catch (InterruptedException e) {
            return null;
        }
    }
}
}
```

#### 10.5.3 监控输入流的进度

`Swing`包包含一个非常有用的流过滤器`ProgressMonitorInputStream`，它会自动弹出一个对话框，监控流已经读取了多少内容。这个过滤器非常易用。只需在你常用的流序列中插入`ProgressMonitorInputStream`即可。关于流的更多信息，请参阅第 2 章。

例如，假设你从一个文件中读取文本。你首先使用`FileInputStream`：

```java
FileInputStream in = new FileInputStream(f);
```

通常情况下，你会将`in`转换为`InputStreamReader`：

```java
InputStreamReader reader = new InputStreamReader(in);
```

然而，为了监控该流，请先将文件输入转换为带有进度监控器的流：

```java
ProgressMonitorInputStream progressIn =
    new ProgressMonitor(parent, caption, in);
```

提供`parent`组件、`caption`以及当然还有要监控的流。进度监控器的`read`方法只是简单地传递字节并更新对话框。现在你可以继续构建你的过滤器序列了：

```java
InputStreamReader reader = new InputStreamReader(progressIn);
```

就是这么简单。当文件被读取时，进度监控器会自动弹出（见图 10.43）。这是流过滤的一个非常好应用。

**图 10.43** 输入流的进度监控器

> 进度监控流使用`InputStream`类的`available`方法来确定流中的总字节数。然而，`available`方法只报告流中在不阻塞的情况下可用的字节数。进度监控器对于文件和 HTTP URL 非常有效，因为它们的长度是预先知的，但它们并不适用于所有流。

列表 10.28 中的程序计算文件的行数。如果你读取一个大文件（例如配套代码中`gutenberg`目录下的《基督罗基督的基督》），进度对话框就会弹出。

如果用户点击“取消（Cancel）”按钮，输入流将关闭。处理输入的代码已经知道如何处理输入结束，因此不需要对编程逻辑进行更改来处理取消。

请注意，该程序没有使用非常高效的方法来填充文本区域。先将文件读取到`StringBuilder`中，然后将文本区域的内容设置为构建器的内容，速度会更快。但在本示例程序中，我们实际上喜欢这种缓慢的方法——它让你有更多时间来欣赏进度对话框。为了避免闪烁，我们在文本区域填充期间不显示它。

**代码列表 10.28** `progressMonitorInputStream/TextFrame.java`

```java
package progressMonitorInputStream;

import java.io.*;
import java.nio.file.*;
import java.util.*;
import javax.swing.*;

/**
 * 一个带有菜单的框架，用于加载文本文件，以及一个显示其内容的文本区域。
 * 文本区域在文件加载时构建，并在加载完成后被设置为框架的内容面板。
 * 这样避免了加载期间的闪烁。
 */
public class TextFrame extends JFrame {
    public static final int TEXT_ROWS = 10;
    public static final int TEXT_COLUMNS = 40;
    private JMenuItem openItem;
    private JMenuItem exitItem;
    private JTextArea textArea;
    private JFileChooser chooser;

    public TextFrame() {
        textArea = new JTextArea(TEXT_ROWS, TEXT_COLUMNS);
        add(new JScrollPane(textArea));

        chooser = new JFileChooser();
        chooser.setCurrentDirectory(new File("."));

        MenuBar menuBar = new JMenuBar();
        setMenuBar(menuBar);

        JMenu fileMenu = new JMenu("File");
        menuBar.add(fileMenu);

        openItem = new JMenuItem("Open");
        openItem.addActionListener(event -> {
            try {
                openFile();
            } catch (IOException exception) {
                exception.printStackTrace();
            }
        });
        fileMenu.add(openItem);

        exitItem = new JMenuItem("Exit");
        exitItem.addActionListener(event -> System.exit(0));
        fileMenu.add(exitItem);

        pack();
    }

    /**
     * 提示用户选择文件，将文件加载到文本区域，并将其设置为
     * 框架的内容面板。
     */
    public void openFile() throws IOException {
        int r = chooser.showOpenDialog(this);
        if (r != JFileChooser.APPROVE_OPTION) {
            return;
        }

        final File f = chooser.getSelectedFile();

        // 设置流和读取器过滤器序列
        InputStream fileIn = Files.newInputStream(f.toPath());
        final ProgressMonitorInputStream progressIn =
            new ProgressMonitorInputStream(
                this,
                "Reading " + f.getName(),
                fileIn
            );

        textArea.setText("");

        SwingWorker<Void, Void> worker = new SwingWorker<Void, Void>() {
            protected Void doInBackground() throws Exception {
                try (Scanner in = new Scanner(progressIn, "UTF-8")) {
                    while (in.hasNextLine()) {
                        String line = in.nextLine();
                        textArea.append(line);
                        textArea.append("\n");
                    }
                }
                return null;
            }
        };
        worker.execute();
    }
}
```

### `javax.swing.JProgressBar` 1.2

- `JProgressBar()`
- `JProgressBar(int direction)`
- `JProgressBar(int min, int max)`
- `JProgressBar(int direction, int min, max)` 创建一个具有方向、最小值和最大值的滑动条。

![Image](img/0026.jpeg)

- `getMinimum()`
- `getMaximum()`
- `setMinimum(int value)`
- `setMaximum(int value)` 设置最小值和最大值。
- `getValue()`
- `setValue(int value)` 设置当前值。
- `getString()`
- `setString(String s)` 设置要在进度条中显示的字符串。如果该字符串为`null`，则显示默认字符串 `"..."`。
- `isStringPainted()`
- `setStringPainted(boolean b)` 设置“绘制字符串”属性。如果该属性为`true`，则会在进度条上绘制绘制字符串。默认为`false`。



- `isIndeterminate()`

- `setIndeterminate(boolean b)` 设置“不确定”属性。如果该属性为 `true`，进度条将变成一个向后和向前移动的块，表示处于未知时间的等待。默认为 `false`。

### javax.swing.ProgressMonitor 1.2

- `ProgressMonitor(Component parent, String note, int min, max)` 创建一个进度监控对话框。

- `setNote(String note)` 更改注释文本。

- `setProgress(int value)` 将进度条值设置为给定值。

- `close()` 关闭此对话框。

- `isCanceled()` 如果用户取消了此对话框，则返回 `true`。

### javax.swing.ProgressMonitorInputStream 1.2

- `ProgressMonitorInputStream(Component parent, Object message, InputStream in)` 创建一个关联进度监控对话框的输入流过滤器。

![Image](img/0028.jpeg)

## 10.6 组织器与装饰器

我们通过介绍有助于组织其他组件的组件来结束对高级 Swing 特性的讨论。这些组件包括 `split pane`（分栏面板），一种将区域划分为多个部分并带有可调整边界的机制；`tabbed pane`（标签页面板），它使用标签分隔符允许用户翻阅多个面板；以及可以用于实现 `internal frames`（内部帧）的 `desktop pane`（桌面面板）。我们将最后讨论 `layers`（层）——即可以叠加在其他组件之上的装饰器。

### 10.6.1 Split Panes

分栏面板将一个组件拆分为两个部分，中间有一个可调整的边界。图 10.44 显示了一个带有两个嵌套分栏面板的框架。外层分栏面板中的组件垂直排列，底部是一个文本区域，顶部是另一个分栏面板。该分栏面板的组件水平排列，左侧是一个列表，右侧是一个包含图像的标签。

![Image](img/0029.jpeg)

**图 10.44** 带有两个嵌套分栏面板的框架

通过指定方向——可以是 `JSplitPane.HORIZONTAL_SPLIT` 或 `JSplitPane.VERTICAL_SPLIT` 之一——后跟两个组件来构造分栏面板。例如：

```java
JSplitPane innerPane = new JSplitPane(JSplitPane.HORIZONTAL_SPLIT, planetList, planetImage);
```

这就是你需要做的所有工作。如果你喜欢，可以在分割器条上添加“一键展开”图标。你可以在图 10.44 顶部的面板中看到这些图标。在 Metal 视觉感知中，它们是小三角形。如果你点击其中一个，分割器将完全移动到三角形指向的方向，从而完全展开其中一个面板。

要添加此功能，请调用：

```java
innerPane.setOneTouchExpandable(true);
```

“连续布局”功能会在用户调整分割器时连续地重绘两个组件的内容。这看起来更高级，但速度可能会慢。通过调用以下代码来开启该功能：

```java
innerPane.setContinuousLayout(true);
```

在示例程序中，我们让底部的分割器保持为默认设置（不使用连续布局）。当你拖动它时，只会移动一个黑色轮廓。当你释放鼠标时，组件才会重新重绘。

列表 10.29 中的简单程序向列表框填充了行星。当用户做出选择时，行星图像显示在右侧，描述位于底部的文本区域。运行该程序，调整分栏，并尝试一键展开和连续布局功能。

**列表 10.29** `splitPane/SplitFrame.java`

（注：原文中 Planet 构造函数和类定义不完整，此处已根据上下文进行了结构化处理。）

```java
JSplitPane innerPane = new JSplitPane(JSplitPane.HORIZONTAL_SPLIT, planetList, planetImage);
innerPane.setContinuousLayout(true);
innerPane.setOneTouchExpandable(true);
JSplitPane outerPane = new JSplitPane(JSplitPane.VERTICAL_SPLIT, innerPane, planetDescription);
add(outerPane, BorderLayout.CENTER);
```

### `javax.swing.JSplitPane` 1.2

- `JSplitPane()`

- `JSplitPane(int direction)`

- `JSplitPane(int direction, boolean continuousLayout)`

- `JSplitPane(int direction, Component first, Component second)`

- `JSplitPane(int direction, boolean continuousLayout, Component first, Component second)` 构造一个新的拆分面板。

![Image](img/00230.jpeg)

- `boolean isOneTouchExpandable()`

- `void setOneTouchExpandable(boolean b)`

获取或设置“一键扩展”（one-touch expandable）属性。当设置此属性时，拆分器将有两个图标，用于完全展开其中一个组件。

- `boolean isContinuousLayout()`

- `void setContinuousLayout(boolean b)`

获取或设置“连续布局”（continuous layout）属性。当设置此属性时，移动拆分器时，组件会持续更新。

- `void setLeftComponent(Component c)`

- `void setTopComponent(Component c)`

这些操作具有相同的效果，将 `c` 设置为拆分面板中的第一个组件。

- `void setRightComponent(Component c)`

- `void setBottomComponent(Component c)`

这些操作具有相同的效果，将 `c` 设置为拆分面板中的第二个组件。

### 10.6.2 标签页面板（Tabbed Panes）

标签页面板是一种熟悉的用户界面设备，可以将复杂的对话框拆分为相关选项的子集。你还可以使用标签页让用户浏览一组文档或图像（参见图 10.45）。这正是我们在示例程序中所做的。

![Image](img/00231.jpeg)

**图 10.45** 一个标签页面板

要创建一个标签页面板，首先构造一个 `JTabbedPane` 对象，然后向它添加标签。

```java
JTabbedPane tabbedPane = new JTabbedPane();
tabbedPane.addTab(title, icon, component);
```

`addTab` 方法的最后一个参数类型为 `Component`。若要在同一个标签页中添加多个组件，请先将它们封装在一个容器中，例如 `JPanel`。

图标是可选的；例如，`addTab` 方法不需要图标：

```java
tabbedPane.addTab(title, component);
```

你还可以使用 `insertTab` 方法在标签页集合的中间插入标签：

```java
tabbedPane.insertTab(title, icon, component, tooltip, index);
```

要从标签页集合中移除标签，请使用：

```java
tabPane.removeTabAt(index);
```

当向标签页集合中添加新标签时，它不会被自动显示。你必须使用 `setSelectedIndex` 方法选中它。例如，这里是显示你刚刚添加到末尾的标签的方法：

```java
tabbedPane.setSelectedIndex(tabbedPane.getTabCount() - 1);
```

如果你有很多标签页，它们会占用相当空间。从 Java SE 1.4 开始，你可以将标签页设置为滚动模式，在这种模式下只显示一行标签页，并带有一组箭头按钮，允许用户滚动标签页集（参见图 10.46）。

![Image](img/00232.jpeg)

**图 10.46** 带有滚动标签页的标签页面板

通过调用以下方法将标签页布局设置为换行或滚动模式：

```java
tabbedPane.setTabLayoutPolicy(JTabbedPane.WRAP_TAB_LAYOUT);
```

或：

```java
tabbedPane.setTabLayoutPolicy(JTabbedPane.SCROLL_TAB_LAYOUT);
```

标签文字可以像菜单项一样带有记忆键（mnemonics）。例如：

```java
int marsIndex = tabbedPane.indexOfTab("Mars");
tabbedPane.setMnemonicAt(marsIndex, KeyEvent.VK_M);
```

现在 M 带有下划线，用户可以通过按 Alt+M 选择标签页。

你可以在标签标题中添加任意组件。首先添加标签，然后调用：

```java
tabbedPane.setTabComponentAt(index, component);
```

在我们的示例程序中，我们为冥王星标签页添加了一个“关闭框”（因为，毕竟，天文学家并不将冥王星视为行星）。这是通过将标签组件设置为包含两个组件的面板来实现的：一个带有图标和标签文本的标签，以及一个带有移除标签动作监听器（action listener）的复选框。

示例程序展示了标签页面板的一种有用技术。有时，你可能想在组件显示之前更新它。在这里，我们只在用户实际点击标签页时才加载行星图像。

为了在用户每次点击标签页时收到通知，请为标签页面板安装一个 `ChangeListener`。注意，你必须为标签页面板本身安装监听器，而不是它的任何一个组件。

```java
tabbedPane.addChangeListener(listener);
```

当用户选择标签页时，标签页面板的 `stateChanged` 方法被调用。你可以获取标签页面板作为事件源。调用 `getSelectedIndex` 方法来确定哪个面板即将显示。

```java
public void stateChanged(ChangeEvent event) {
    int n = tabbedPane.getSelectedIndex();
    loadTab(n);
}
```

在 10.3 中，我们首先将所有组件设置为 `null`。当某个标签被选中时，我们测试它是否仍为 `null`。如果是，我们就用图像替换它（这发生在点击标签页时）。为了好玩，我们将图标从黄色改为红色，以表示面板已被访问。

### TabbedPane.java

```java
package tabbedPane;

import java.awt.*;
import javax.swing.*;

/**
 * 此框架显示了一个标签页面板以及切换
 * 换和滚动布局的单选按钮。
 */
public class TabbedPane extends JFrame {
    private static final DEFAULT_WIDTH = 400;
    private static final DEFAULT_HEIGHT = 300;
    private JTabbedPane tabbedPane;

    public TabbedPane() {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);
        tabbedPane = new JTabbedPane();
        // 将组件设置为 null，直到第一次
        // 使用时
        ImageIcon icon = new ImageIcon(getClass().getResource("yellow-ball.gif"));
        tabbedPane.addTab("Mercury", icon, null);
        tabbedPane.addTab("Venus", icon, null);
        tabbedPane.addTab("Earth", icon, null);
        tabbedPane.addTab("Mars", icon, null);
        tabbedPane.addTab("Jupiter", icon, null);
        tabbedPane.addTab("Saturn", icon, null);
        tabbedPane.addTab("Uranus", icon, null);
        tabbedPane.addTab("Neptune", icon, null);
        tabbedPane.addTab("Pluto", null, null);

        final int plutoIndex = tabbedPane.indexOfTab("Pluto");
        JPanel plutoPanel = new JPanel();
        plutoPanel.add(new JLabel("Pluto", icon, SwingConstants.LEADING));
        JToggleButton plutoCheckBox = new JCheckBox();
        plutoCheckBox.addActionListener(event -> tabbedPane.remove(plutoIndex));
    }
}
```

```java
plutoPanel.add(plutoCheckBox);
tabbedPane.setTabComponentAt(plutoIndex, plutoPanel);
add(tabbedPane, "Center");

tabbedPane.addChangeListener(event ->
  {
    // 检查此标签页是否仍为空组件
    if (tabbedPane.getSelectedComponent() == null)
    {
      // 将组件设置为图像图标
      int n = tabbedPane.getSelectedIndex();
      loadTab(n);
    }
  });

loadTab(0);
JPanel buttonPanel = new JPanel();
ButtonGroup buttonGroup = new ButtonGroup();
JRadioButton wrapButton = new JRadioButton("换行标签");
wrapButton.addActionListener(event ->
    tabbedPane.setTabLayoutPolicy(JTabbedPane.WRAP_TAB_LAYOUT));
buttonPanel.add(wrapButton);
buttonGroup.add(wrapButton);
wrapButton.setSelected(true);
JRadioButton scrollButton = new JRadioButton("滚动标签");
scrollButton.addActionListener(event ->
    tabbedPane.setTabLayoutPolicy(JTabbedPane.SCROLL_TAB_LAYOUT));
buttonPanel.add(scrollButton);
buttonGroup.add(scrollButton);
add(buttonPanel, BorderLayout.SOUTH);
}

/**
 * 加载给定索引的标签页。
 * @param n 要加载的标签索引
 */
private void loadTab(int n)
{
  String title = tabbedPane.getTitleAt(n);
  ImageIcon planetIcon = new ImageIcon(getClass().getResource(title + ".gif"));
  tabbedPane.setComponentAt(n, new JLabel(planetIcon));
  // 表示此标签页已被访问——仅仅是为了好玩
  tabbedPane.setIconAt(n, new ImageIcon(getClass().getResource("red-ball.gif")));
}
```

### `javax.swing.JTabbedPane`

- `JTabbedPane()`

- `JTabbedPane(int placement)` 构建一个标签页面板。

- `void addTab(String title, Component c)`

- `void addTab(String title, Icon icon)`

- `void addTab(String title, Icon icon, String tooltip)` 在标签页面板的末尾添加一个标签。

- `void insertTab(String title, Icon icon, Component c, String tooltip, int index)` 在标签页面板的指定索引处插入一个标签。

- `removeTabAt(int index)` 指定索引处的标签。



- `void setSelectedIndex(int index)` 选中指定索引处的标签。
- `int getSelectedIndex()` 返回所选标签页的索引。
- `Component getSelectedComponent()` 返回所选标签页的组件。
- `String getTitleAt(int index)`
- `void setTitleAt(int index, String title)`
- `Icon getIconAt(int index)`
- `void setIconAt(int index, Icon icon)`
- `Component getComponentAt(int index)`
- `void setComponentAt(int index, Component c)` 获取或设置指定索引处的标题、图标或组件。
- `int indexOfTab(String title)`
- `int indexOfTab(Icon icon)`
- `int indexOfComponent(Component c)` 返回具有给定标题、图标或组件的标签索引。
- `int getTabCount()` 返回此标签页面板中标签的总数。
- `int getTabLayoutPolicy()`
- `void setTabLayoutPolicy(int policy)` 获取或设置标签布局。`policy` 是 `JTabbedPane.WRAP_TAB_LAYOUT` 或 `JTabbedPane.SCROLL_TAB_LAYOUT` 之一。
- `int getMnemonicAt(int index)`
- `void setMnemonicAt(int index, int mnemonic)` 获取或设置指定索引处的快捷键字符。字符指定为 `KeyEvent` 类中的 `VK_X` 常量。`-1` 表示没有快捷键。
- `Component getTabComponent(int index)`
- `void setTabComponentAt(int index, Component c)` 获取或设置渲染指定索引标签标题的组件。如果此组件为 `null`，则渲染标签图标和标题。否则，仅在标签中渲染给定的组件。
- `int indexOfTabComponent(Component c)` 返回具有给定标题组件的标签索引。
- `void addChangeListener(ChangeListener listener)` 添加变化监听器，当用户选择不同的标签时会通知该监听器。

#### 10.6.3 桌面面板和内部帧

许多应用程序在多个窗口中显示信息，而这些窗口都包含在一个大的框架内。如果你最小化应用程序框架，其所有的窗口将同时隐藏。在 Windows 环境中，这种用户界面有时被称为多文档界面（MDI）。图 10.47 显示了一个使用这种界面的典型应用程序。

![Image](img/00234.jpeg)

**图 10.47** 多文档界面应用程序

在一段时间内，这种用户界面风格非常流行，但在最近几年中变得不再常见。如今，许多应用程序仅为每个文档显示一个独立的顶层框架。哪种更好呢？MDI 减少了窗口混乱，但拥有独立的顶层窗口意味着你可以使用宿主窗口系统的按钮和热键来切换你的窗口。

##### 10.6.3.1 显示内部帧

在 Java 世界中，你无法依赖丰富的宿主窗口系统，因此让你的应用程序管理自己的框架非常有意义。

图 10.48 显示了一个带有三个内部帧的 Java 应用程序。其中两个带有装饰框（可以最大化和最小化），而第三个处于最小化状态。

在 Metal 视图中，内部帧具有可以移动窗口的独特“抓取”区域。要实现这种功能，请遵循以下步骤：

1. 使用普通的 `JFrame` 窗口。
2. 将 `JDesktopPane` 添加到 `JFrame`。
3. 构建 `JInternalFrame` 窗口。你可以指定是否想要调整大小、关闭、最大化或最小化。
4. 将组件添加到帧中。
5. 设置帧图标。图标显示在帧的左上角。
6. 设置内部帧的大小。与普通帧一样，内部帧最初的大小为 0 像素。你不希望内部帧堆叠在一起，因此为下一个帧使用变量位置。使用 `reshape` 方法同时设置帧的位置和大小。
7. 与 `JFrame` 实例一样，你需要让帧可见。
8. 将帧添加到 `JDesktopPane`。

你可能想将新帧设置为选中的帧。在桌面上的内部帧中，只有被选中的帧才能接收键盘焦点。在 Metal 这种外观中，被选中的帧具有蓝色标题栏，而其他帧具有灰色的标题栏。使用 `setSelected` 方法来选择帧。

然而，“选中”属性可以被否决（vet）：当前被选中的帧可以拒绝放弃焦点。在这种情况下，`setSelected` 方法会抛出一个 `PropertyVetoException`，你需要处理该异常。

点击此处查看代码图片

```java
try
{
   iframe.setSelected(true);
}
catch (PropertyVetoException ex)
{
   // 尝试被否决
}
```

你可能想将下一个内部帧的位置向下移动，这样它就不会覆盖现有的帧。帧之间的良好距离是标题栏的高度，你可以通过以下方式获取：

点击此处查看代码图片

```java
int frameDistance = iframe.getHeight() - iframe.getContentPane().getHeight();
```

使用该距离来确定下一个内部帧的位置。

点击此处查看代码图片

```java
nextFrameX += frameDistance;
nextFrameY += frameDistance;
if (nextFrameX + width > desktop.getWidth())
    nextFrameX = 0;
if (nextFrameY + height > desktop.getHeight())
    nextFrameY = 0;
```

### 10.6.3.2 层级排列与平铺

在 Windows 中，有标准的窗口层级排列（cascading）和平铺（tiling）命令（参见图 10.49 和图 10.50）。Java 的 `JDesktopPane` 和 `JInternalFrame` 类没有对这些操作的内置支持。在列表 10.31 中，我们展示了如何自己实现这些操作。

![Image](img/00236.jpeg)

**图 10.49** 层级排列的内部帧

![Image](img/00237.jpeg)

**图 10.50** 平铺的内部帧

要对所有窗口进行层级排列，可以将窗口调整为相同的大小并交错排列位置。`JDesktopPane` 类的 `getAllFrames` 方法返回所有内部帧的数组。

点击此处查看代码图片

```java
JInternalFrame[] frames = desktop.getAllFrames();
```

然而，你需要注意帧的状态。内部帧可以处于三种状态之一：

- 图标化（Icon）
- 可调整大小（Resizable）
- 最大化（Maximum）

使用 `isIcon` 方法找出哪些内部帧当前是图标并应该被跳过。然而，如果帧处于最大化状态，你首先需要通过调用 `setMaximum(false)` 将其设置为可调整大小。这是另一个可以被否决的属性，因此你必须捕获 `PropertyVetoException`。

以下循环对桌面上的内部帧进行层级排列：

点击此处查看代码图片

```java
for (JInternalFrame frame : desktop.getAllFrames())
{
   if (!frame.isIcon())
   {
      try
      {
          // 尝试让最大化的帧变为可调整大小；这可能被否决
          frame.setMaximum(false);
          frame.reshape(x, y, width, height);
          x += frameDistance;
          y += frameDistance;
          // 在桌面边缘换回
          if (x + width > desktop.getWidth()) x = 0;
          if (y + height > desktop.getHeight()) y = 0;
      }
      catch (PropertyVetoException ex)
      {}
   }
}
```

平铺帧更为复杂，特别是当帧的数量不是完全平方数时。首先，统计不是图标的帧的数量。计算第一列的行数如点击此处查看代码图片：

```java
int rows = (int) Math.sqrt(frameCount);
```

然后列数是点击此处查看代码图片：

```java
int cols = frameCount / rows;
```

最后剩下的点击此处查看代码图片：

```java
int extra = frameCount % rows;
```

列具有 `rows + 1` 行。这里是桌面上所有帧的循环：

点击此处查看代码图片

```java
int width = desktop.getWidth() / cols;
int height = desktop.getHeight() / rows;
int r = 0;
int c = 0;
for (JInternalFrame frame : desktop.getAllFrames())
{
   if (!frame.isIcon())
   {
      try
      {
         // 让最大化的帧变为可调整大小
         frame.setMaximum(false);
         frame.reshape(c * width, r * height, width, height);
         r++;
         if (r == rows)
         {
            r = 0;
            c++;
         }
      }
      catch (PropertyVetoException ex)
      {}
   }
}
```

（注：此处原文逻辑与前文描述略有出入，翻译遵循原文意图）

修正：根据原文提供的逻辑片段，重新对齐平铺逻辑的对应数据块翻译：

最后 `extra` 列列 `rows + 1`。这是桌面上所有帧的循环：

点击此处查看代码图片

```java
int extra = frameCount % rows;
```

### 10.6.3.3 否决属性设置

现在你已经看到了所有的否决异常，你可能想知道你的帧如何发出否决。`JInternalFrame` 类使用了 JavaBeans 中一种很少使用的机制来监控属性设置。我们不会详细讨论该机制，但将向你展示你的帧如何否决请求。

帧通常不想通过否决来反对图标化或失去焦点，但帧检查是否可以关闭它们是非常常见的。你可以使用 `JInternalFrame` 类的 `setClosed` 方法关闭帧。由于该方法是可否决的，它在执行更改之前会调用所有注册的否决变更监听器。这使得每个监听器有机会抛出 `PropertyVetoException`，从而在更改任何设置之前终止调用。

在我们的示例程序中，我们弹出一个对话框询问用户是否可以关闭窗口（参见图 10.51）。如果用户不同意，窗口将保持打开。

这是实现这种通知的方法：

1. 为每个帧添加监听器。该对象必须属于实现 `VetoableChangeListener` 接口的类。最好在构造帧后立即添加监听器。在我们的示例中，我们使用构造内部帧的帧类。另一个选项是使用匿名内部类。

   点击此处查看代码图片

   ```java
   iframe.addVetoableChangeListener(listener);
   ```

2. 实现 `vetoableChange` 方法，这是 `VetoableChangeListener` 接口唯一要求实现的方法。该方法接收一个 `PropertyChangeEvent` 对象。使用 `getName` 方法可以查找到即将被更改的属性名称（如果用于否决的方法调用是 `setClosed(true)`，则名称为 `"closed"`）。通过移除方法名中的 `"set"` 前缀并将其后的第一个字母改为小写来获取属性名称。

3. 使用 `getNewValue` 方法获取提议的新值。

   点击此处查看代码图片

   ```java
   String name = event.getPropertyName();
   Object value = event.getNewValue();
   if (name.equals("closed") && value.equals(true))
   {
       ask user for confirmation
   }
   ```

4. 只需抛出 `PropertyVetoException` 即可阻止属性更改。如果你不想否决该更改，则正常返回。

   点击此处查看代码图片

   ```java
   class DesktopFrame extends JFrame implements VetoableChangeListener
   {
       . . .
       public void vetoableChange(PropertyChangeEvent event)
           throws PropertyVetoException
       {
           . . .
           if (not ok)
               throw new PropertyVetoException(reason, event);
           // return normally if ok
       }
   }
   ```

### 10.6.3.4 内部帧中的对话框

如果你使用内部帧（internal frames），不应使用 `JDialog` 类来创建对话框。这些对话框有两个缺点：

- 它们是重量级的，因为它们会在窗口系统中创建一个新的帧（frame）。
- 窗口系统不知道如何相对于产生它的内部帧对其进行定位。

相反，对于简单的对话框，请使用 `JOptionPane` 类的 `showInternalXxxDialog` 方法。它们的工作方式与 `showXxxDialog` 方法完全相同，区别在于它们是在内部帧上覆盖了一个轻量级窗口。

对于更复杂的对话框，请使用 `JInternalFrame` 进行构建。遗憾的是，这样你将无法获得模态对话框的内置支持。

在我们的示例程序中，我们使用一个内部对话框来询问用户是否可以关闭一个帧。

点击此处查看代码图片

```java
int result = JOptionPane.showInternalConfirmDialog(
    iframe, "OK to close?", "Select an Option", JOptionPane.YES_NO_OPTION);
```

![Image](img/00002.jpeg) Note

如果你只是想在帧关闭时收到通知，不应该使用否决机制。相反，应该安装 `InternalFrameListener`。内部帧监听器的工作方式与 `WindowListener` 相同。当内部帧正在关闭时，调用的是 `internalFrameClosing` 方法而不是熟悉的 `windowClosing` 方法。其他六个内部帧通知（打开/关闭、最小化/取消最小化、激活/取消激活）也与窗口监听器方法对应。

### 10.6.3.5 轮廓拖动

开发者对内部帧的一个批评是性能并不理想。到目前为止，最慢的操作是在桌面上拖动带有复杂内容的帧。桌面管理器在拖动过程中会不断要求帧重绘自己，这非常缓慢。

实际上，如果你在 Windows 或 X Windows 上使用编写糟糕的视频驱动程序，也会遇到相同的问题。窗口拖动在大多数系统上看起来很快，是因为视频硬件支持通过在拖动过程中将帧内部的图像映射到不同的屏幕位置来完成拖动操作。

为了在不大幅损害用户体验的情况下提高性能，你可以开启“轮廓拖动”。当用户拖动帧时，只有帧的轮廓会持续更新。帧内部的内容只在帧释放到最终停留位置时才会进行重绘。

要开启轮廓拖动，请调用：

点击此处查看代码图片

```java
desktop.setDragMode(JDesktopPane.OUTLINE_DRAG_MODE);
```

此设置等同于 `JSplitPane` 类中的“连续布局”。

![Image](img/00002.jpeg) Note

在 Swing 的早期版本中，你必须使用“魔法咒语”：

点击此处查看代码图片

```java
desktop.putClientProperty("JDesktopPane.dragMode", "outline");
```

来开启轮廓拖动。

在示例程序中，你可以使用 Window → Drag Outline 菜单选择项来切换轮廓拖动的开启或关闭。

![Image](img/00002.jpeg) Note

桌面上的内部帧由 `DesktopManager` 类管理。在普通编程中你不需要了解这个类。通过安装新的桌面管理器可以改变桌面行为，但我们没有涵盖这一点。

Listing 10.31 在桌面上填充了显示 HTML 页的内部帧。File → Open（文件→打开）选项会弹出一个对话框，将本地 HTML 文件读取到新的内部帧中。如果你点击任何链接，关联的文档将在另一个内部帧中显示。尝试 Window → Cascade（级叠）和 Window → Tile（平铺）命令。

**Listing 10.31** `internalFrame/DesktopFrame.java` 点击此处查看代码图片



```java
package internalFrame;

import java.awt.*;
import java.beans.*;
import javax.swing.*;

/**
 * 此帧包含显示 HTML 文档的编辑器面板。
 */
public class DesktopFrame extends JFrame
{
    private static final int DEFAULT_WIDTH = 600;
    private static final int DEFAULT_HEIGHT = 400;
    private static final String[] planets = {"Mercury", "Venus", "Mars", "Jupiter", "Saturn", "Uranus", "Neptune", "Pluto" };
    private JDesktopPane desktop;
    private int nextFrameX;
    private int nextFrameY;
    private int frameDistance;
    private int counter;

    public DesktopFrame()
    {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);
        desktop = new JDesktopPane();
        add(desktop, BorderLayout.CENTER);
        // set up menus
        JMenuBar menuBar = new JMenuBar();
        setJMenuBar(menuBar);
        JMenu fileMenu = new JMenu("File");
        menuBar.add(fileMenu);
        JMenuItem openItem = new JMenuItem("New");
        openItem.addActionListener(event ->
        {
            createInternalFrame(new JLabel(
                new ImageIcon(getClass().getResource(planets[counter] + ".gif"))),
                planets[counter]);
            counter = (counter + 1) % planets.length;
        });
        fileMenu.add(openItem);
        JMenuItem exitItem = new JMenuItem("Exit");
        exitItem.addActionListener(event -> System.exit(0));
        fileMenu.add(exitItem);
        JMenu windowMenu = new JMenu("Window");
        menuBar.add(windowMenu);
        JMenuItem nextItem = new JMenuItem("Next");
        nextItem.addActionListener(event -> selectNextWindow());
        windowMenu.add(nextItem);
        JMenuItem cascadeItem = new JMenuItem("Cascade");
        cascadeItem.addActionListener(event -> cascadeWindows());
        windowMenu.add(cascadeItem);
        JMenuItem tileItem = new JMenuItem("Tile");
        tileItem.addActionListener(event -> tileWindows());
        windowMenu.add(tileItem);
        final JCheckBoxMenuItem dragOutlineItem = newCheckBoxMenuItem("Drag Outline");
        dragOutlineItem.addActionListener(event ->
            desktop.setDragMode(dragOutlineItem.isSelected() ? JDesktopPane.OUTLINE_DRAG_MODE : JDesktopPane.LIVE_DRAG_MODE));
        windowMenu.add(dragOutlineItem);
    }

    /**
     * 在桌面上创建一个内部帧。
     */
}
```

## 内部框架方法

```java
/**
 * @param c 在内部框架中显示的组件
 * @param t 内部框架的标题
 */
public void createInternalFrame(Component c, String t)
{
    final JInternalFrame iframe = new JInternalFrame(t, true, // 可调整大小
        true, // 可关闭
        true, // 可最大化
        true); // 可图标化

    iframe.add(c, BorderLayout.CENTER);
    desktop.add(iframe);

    iframe.setFrameIcon(new ImageIcon(getClass().getResource("document.gif")));

    // 添加监听器以确认框架关闭
    iframe.addVetoableChangeListener(event ->
        {
        String name = event.getPropertyName();
        Object value = event.getNewValue();

        // 我们只检查尝试关闭帧的操作
        if (name.equals("closed") && value.equals(true))
        {
            // 询问用户是否可以关闭
            int result = JOptionPane.showInternalConfirmDialog(iframe, "可以关闭吗?",
                    "选择一个选项", JOptionPane.YES_NO_OPTION);

            // 如果用户不同意，则否决关闭
            if (result != JOptionPane.YES_OPTION)
                throw new PropertyVetoException("用户取消关闭", event);
        }
    });

    // 设置框架的位置
    int width = desktop.getWidth() / 2;
    int height = desktop.getHeight() / 2;
    iframe.reshape(nextFrameX, nextFrameY, width, height);

    iframe.show();

    // 选中帧--可能会被否决
    try
    {
        iframe.setSelected(true);
    }
    catch(PropertyVetoException ex)
    {
    }
    frameDistance = iframe.getHeight() - iframe.getContentPane().getHeight();
    // 计算下一个帧的放置位置
    nextFrameX += frameDistance;
    nextFrameY += frameDistance;
    if (nextFrameX + width > desktop.getWidth()) nextFrameX = 0;
    if (nextFrameY + height > desktop.getHeight()) nextFrameY = 0;
}

/**
 * 使桌面上未图标化的帧呈层叠排列。
 */
public void cascadeWindows()
{
    int x = 0;
    int y = 0;
    int width = desktop.getWidth() / 2;
    int height = desktop.getHeight() / 2;

    for (JInternalFrame frame : desktop.getAllFrames())
    {
        if (!frame.isIcon())
        {
            try
            {
                // 尝试让最大化的帧变为可调整；这可能会被否决
                frame.setMaximum(false);
                frame.reshape(x, y, width, height);

                x += frameDistance;
                y += frameDistance;
                // 在桌面边缘换行
                if (x + width > desktop.getWidth()) x = 0;
                if (y + height > desktop.getHeight()) y = 0;
            }
            catch(PropertyVetoException ex)
            {
            }
        }
    }
}

/**
 * 使桌面上未图标化的帧呈平铺排列。
 */
public void tileWindows()
{
    // 统计不是图标的帧数
    int frameCount = 0;
    for (JInternalFrame frame : desktop.getAllFrames())
        if (!frame.isIcon()) frameCount++;
    if (frameCount == 0) return;
    int rows = (int) Math.sqrt(frameCount);
    int cols = frameCount / rows;
    int extra = frameCount % rows;
    // 带有额外一行的列数
    int width = desktop.getWidth() / cols;
    int height = desktop.getHeight() / rows;
    int r = 0;
    int c = 0;
    for (JInternalFrame frame : desktop.getAllFrames())
    {
        if (!frame.isIcon())
        {
            try
            {
                frame.setMaximum(false);
                frame.reshape(c * width, r * height, width, height);
                r++;
                if (r == rows)
                {
                    r = 0;
                    c++;
                    if (c == cols - extra)
                    {
                        // 开始添加额外的行
                        rows++;
                        height = desktop.getHeight() / rows;
                    }
                }
            }
            catch(PropertyVetoException ex)
            {
            }
        }
    }
}

/**
 * 将下一个未图标化的帧带到最前。
 */
public void selectNextWindow()
{
    JInternalFrame[] frames = desktop.getAllFrames();
    for (int i = 0; i < frames.length; i++)
    {
        if (frames[i].isSelected())
        {
            // 寻找不是图标且可以选中的下一个帧
            int next = (i + 1) % frames.length;
            while (next != i)
            {
                if (!frames[next].isIcon())
                {
                    try
                    {
                        // 所有其他帧都是图标或已选中
                        frames[next].setSelected(true);
                        frames[next].toFront();
                        frames[i].toBack();
                        return;
                    }
                    catch(PropertyVetoException ex)
                    {
                    }
                }
                next = (next + 1) % frames.length;
            }
        }
    }
}
```

## javax.swing.JDesktopPane

- `getAllFrames()`: 获取此桌面面板中的所有内部帧。

- `setDragMode(int mode)`: 将拖动模式设置为活动或轮廓拖动。

![Image](img/0239.jpeg)

## javax.swing.JInternalFrame

- `JInternalFrame()`

- `JInternalFrame(String title)`

- `JInternalFrame(String title, boolean resizable)`

- `JInternalFrame(String title, boolean resizable, boolean closable)`

- `JInternalFrame(String title, boolean resizable, boolean closable, boolean maximizable)`

- `JInternalFrame(String title, boolean resizable, boolean closable, boolean maximizable, boolean iconifiable)`: 一个新的内部帧。

![Image](img/0240.jpeg)

- `isResizable()` / `setResizable(boolean b)`

- `isClosable()` / `setClosable(boolean b)`

- `isMaximizable()` / `setMaximizable(boolean b)`

- `isIconifiable()` / `setIconifiable(boolean b)`: 获取或设置`resizable`、`closable`、`maximizable`和`iconifiable`属性。当属性为`true`时，帧标题中会出现一个图标，用于调整大小、关闭、最大化或图标化内部帧。

- `isIcon()` / `setIcon(boolean b)`

- `isMaximum()` / `setMaximum(boolean b)`

- `isClosed()` / `setClosed(boolean b)`: 获取或设置`icon`、`maximum`或`closed`属性。当此属性为`true`时，内部帧将被图标化、最大化或关闭。

- `moveToFront()`

- `moveToBack()`: 将此内部帧移动到桌面的最前面或最后面。

- `void reshape(int x, int y, int width, int height)` 移动并调整此内部帧的大小。

![Image](img/0241.jpeg)

- `Container getContentPane()` 获取内容面板。



- `void setContentPane(Container c)` 获取或设置内部帧的内容面板。
- `JDesktopPane getDesktopPane()` 获取内部帧的桌面面板。
- `Icon getFrameIcon()` 获取帧图标。
- `void setFrameIcon(Icon anIcon)` 获取或设置显示在标题栏的帧图标。
- `boolean isVisible()` 获取属性。
- `void setVisible(boolean b)` 设置该属性。
- `void show()` 使此内部帧可见并将其置于顶层。

`javax.swing.JComponent`

- `void addVetoChangeListener(VetoChangeListener listener)` 添加一个可否决更改监听器，当尝试更改受限属性时，该监听器会收到通知。

`java.beans.VetoChangeListener`

- `void vetoChange(PropertyChangeEvent event)` 当受限属性的 `set` 方法通知可否决监听器时调用此方法。

`java.beans.PropertyChangeEvent`

- `String getPropertyName()` 返回即将更改的属性的名称。
- `Object getNewValue()` 返回属性的建议值。

`java.beans.PropertyVetoException`

- `PropertyVetoException(String reason, PropertyChangeEvent event)` 构造一个属性异常。

![Image](img/0242.jpeg)

#### 10.6.4 层（Layers）

Java SE 7 引入了一个允许你在另一个组件上方放置一个层的功能。你可以在层上进行绘制，并监听底层组件的事件。你可以使用层为界面添加视觉线索。例如，你可以装饰当前输入、无效输入或禁用的组件。

`JLayer` 类将组件与 `LayerUI` 对象关联起来，该对象负责绘制和事件处理。`LayerUI` 类有一个类型参数，必须与关联的组件匹配。例如，我们为 `JPanel` 添加了一个层：

```java
JPanel panel = new JPanel();
LayerUI<JPanel> layerUI = new PanelLayer();
JLayer layer = new JLayer(panel, layerUI);
frame.add(layer);
```

请注意，你添加到父容器的是层，而不是面板。在这里，`PanelLayer` 是子类：

```java
class PanelLayer extends LayerUI<Panel> {
    public void paint(Graphics g, JComponent c) {
        // ...
    }
}
```

在 `paint` 方法中，你可以绘制任何你想要的内容。确保调用 `super.paint` 以让组件被绘制。在这里，我们在整个组件上绘制了一个透明颜色：

```java
public void paint(Graphics g, JComponent c) {
    super.paint(g, c);
    Graphics2D g2 = (Graphics2D) g.create();
    g2.setComposite(AlphaComposite.getInstance(AlphaComposite.SRC_OVER, .3f));
    g2.setPaint(color);
    g2.fillRect(0, 0, c.getWidth(), c.getHeight());
    g2.dispose();
}
```

为了监听来自关联组件或任何子组件的事件，`LayerUI` 类必须设置层的事件掩码。这应该在 `installUI` 方法中完成，如下所示：

```java
class PanelLayer extends LayerUI<JPanel> {
    public void installUI(JComponent c) {
        super.installUI(c);
        ((JLayer<?>) c).setLayerEventMask(AWTEvent.KEY_EVENT_MASK | AWTEvent.FOCUS_EVENT_MASK);
    }

    public void uninstallUI(JComponent c) {
        ((JLayer<?>) c).setLayerEventMask(0);
        super.uninstallUI(c);
    }
}
```

现在你将在名为 `processXxxEvent` 的方法中接收事件。例如，在我们的示例应用程序中，每次按键后都会重绘该层：

```java
public class PanelLayer extends LayerUI<JPanel> {
    protected void processKeyEvent(KeyEvent e, JLayer<? extends JPanel> l) {
        l.repaint();
    }
}
```

我们在 `Listing 10.32` 中的示例程序有三个用于颜色 RGB 值的输入字段。当用户更改值时，颜色就会以透明的方式显示在面板上。我们还拦截了事件，并用粗字体显示聚焦组件的文本。

**Listing 10.32 `layer/ColorFrame.java`**

```java
package layer;

import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.plaf.*;

/**
 * 一个带有用于设置背景色的文本字段的帧。
 */
public class ColorFrame extends JFrame {
    private JPanel panel;
    private JTextField redField;
    private JTextField greenField;
    private JTextField blueField;

    ColorFrame() {
        panel = new JPanel();
        panel.add(new JLabel("Red:"));
        redField = new JTextField("255");
        panel.add(redField);
        panel.add(new JLabel("Green:"));
        greenField = new JTextField("255");
        panel.add(greenField);
        panel.add(new JLabel("Blue:"));
        blueField = new JTextField("255");
        panel.add(blueField);
        LayerUI<JPanel> layerUI = new PanelLayer();
        JLayer<JPanel> layer = new JLayer<JPanel>(panel, layerUI);
        add(layer);
        pack();
    }

    class PanelLayer extends LayerUI<JPanel> {
        public void installUI(JComponent c) {
            super.installUI(c);
            ((JLayer<?>) c).setLayerEventMask(AWTEvent.KEY_EVENT_MASK | AWTEvent.FOCUS_EVENT_MASK);
        }

        public void uninstallUI(JComponent c) {
            ((JLayer<?>) c).setLayerEventMask(0);
            super.uninstallUI(c);
        }

        protected void processKeyEvent(KeyEvent e, JLayer<? extends JPanel> l) {
            l.repaint();
        }

        protected void processFocusEvent(FocusEvent e, JLayer<? extends JPanel> l) {
            if (e.getID() == FocusEvent.FOCUS_GAINED) {
                Component c = e.getComponent();
                c.setFont(c.getFont().deriveFont(Font.BOLD));
            }

            if (e.getID() == FocusEvent.FOCUS_LOST) {
                Component c = e.getComponent();
                c.setFont(c.getFont().deriveFont(Font.PLAIN));
            }
        }

        public void paint(Graphics g, JComponent c) {
            super.paint(g, c);
            Graphics2D g2 = (Graphics2D) g.create();
            g2.setComposite(AlphaComposite.getInstance(AlphaComposite.SRC_OVER, .3f));
            int red = Integer.parseInt(redField.getText());
            int green = Integer.parseInt(greenField.getText());
            int blue = Integer.parseInt(blueField.getText());
            g2.setPaint(new Color(red, green, blue));
            g2.fillRect(0, 0, c.getWidth(), c.getHeight());
            g2.dispose();
        }
    }
}
```

```java
void uninstallUI(JComponent c)
```

当组件 `c` 的 `LayerUI` 安装或卸载时调用。重写此方法以设置或清除层事件掩码。

```java
void paint(Graphics g, JComponent c)
```

当装饰过的组件被绘制时调用。重写此方法以调用 `super.paint` 并绘制装饰。

```java
void processComponentEvent(ComponentEvent e, JLayer<? extends V> l)
```

```java
void processFocusEvent(FocusEvent e, JLayer<? extends V> l)
```

```java
void processHierarchyBoundsEvent(HierarchyEvent e, JLayer<? extends V> l)
```

```java
void processHierarchyEvent(HierarchyEvent e, JLayer<? extends V> l)
```

```java
void processInputMethodEvent(InputMethodEvent e, JLayer<? extends V> l)
```

```java
void processKeyEvent(KeyEvent e, JLayer<? extends V> l)
```

```java
void processMouseEvent(MouseEvent e, JLayer<? extends V> l)
```

```java
void processMouseMotionEvent(MouseEvent e, JLayer<? extends V> l)
```

```java
void processMouseWheelEvent(MouseWheelEvent e, JLayer<? extends V> l)
```

当指定的事件发送到此 `LayerUI` 时调用。

---

你现在已经了解了如何使用 Swing 框架提供的复杂组件。在下一章中，我们将转向高级 AWT 问题：复杂的绘制操作、图像处理、打印以及与原生窗口系统的交互。

## 第 11 章 高级 AWT

---

### 本章中

- 11.1 渲染流水线
- 11.2 形状
- 11.3 区域
- 11.4 描笔
- 11.5 绘制
- 11.6 坐标变换
- 11.7 裁剪
- 11.8 透明度与合成
- 11.9 渲染提示
- 11.10 图像的读取器与写入器
- 11.11 图像处理
- 11.12 打印
- 11.13 剪贴板
- 11.14 拖放与放置
- 11.15 平台集成

你可以使用 `Graphics` 类的方法来创建简单的图形。这些方法对于简单的 applet 和应用程序足够了，但当你需要创建复杂形状或完全控制图形外观时，它们就显得了。Java 2D API 是一个更复杂的类库，你可以用它来生成高质量的图形。在本章中，我们将为你概述该 API。

然后我们将转向打印主题，并展示如何在程序中实现打印功能。

我们将介绍两种在程序之间传输数据的技术：系统剪贴板和拖放机制。你可以使用这些技术在两个 Java 应用程序之间或 Java 应用程序与原生程序之间传输数据。最后，我们将介绍让 Java 应用程序更像原生应用程序的技术，例如提供启动界面和系统托盘图标。

### 11.1 渲染流水线

原始的 JDK 1.0 拥有一种非常简单的形状绘制机制。你选择颜色和绘制模式，并调用 `Graphics` 类的方法，如 `drawRect` 或 `fillOval`。Java 2D API 支持得更多。

- 你可以轻松地产生各种形状。
- 你可以控制 `stroke`（描笔）——即追踪形状边界的笔。
- 你可以使用纯色、变化的色调和重复图案来填充形状。
- 你可以使用变换来移动、缩放、旋转或拉伸形状。
- 你可以裁剪形状以将其限制在任意区域内。
- 你可以选择合成规则，来描述如何将新形状的像素与现有像素结合。
- 你可以提供渲染提示在速度和绘制质量之间进行权衡。

要绘制形状，请遵循以下步骤：

1. 获取 `Graphics2D` 类的对象。该类是 `Graphics` 类的子类。

2. 要绘制形状，请遵循以下步骤：

   ```java
   Graphics2D g2 = (Graphics2D) g;
   ```

3. 使用 `RenderingHints` 在速度和绘制质量之间进行权衡。

   ```java
   g2.setRenderingHints(hints);
   ```

4. 使用 `setStroke` 设置线条的厚度。

   ```java
   g2.setStroke(stroke);
   ```

5. 使用 `setPaint` 设置绘制源。

   ```java
   g2.setPaint(paint);
   ```

6. 使用 `clip` 设置裁剪区域。

   ```java
   g2.clip(clip);
   ```

7. 使用 `transform` 设置从用户空间到设备空间的变换。

   ```java
   g2.transform(transform);
   ```

8. 使用 `setComposite` 设置合成规则。

   ```java
   g2.setComposite(composite);
   ```

9. 创建一个形状。

   ```java
   Shape shape = ...;
   ```

10. 绘制或填充形状。

    ```java
    g2.draw(shape);
    g2.fill(shape);
    ```

- `void draw(Shape s)`

  用当前画笔绘制给定形状的轮廓。

- `void fill(Shape s)`

  用当前画笔填充给定形状的内部。

---

### 11.2 形状

以下是 `Graphics` 类中用于绘制形状的方法：

点击此处查看代码图像。

- `drawLine`
- `drawRectangle`
- `drawRoundRect`
- `draw3DRect`
- `drawPolygon`
- `drawPolyline`
- `drawOval`
- `drawArc`

还有对应的 `fill` 方法。这些方法从 JDK 1.0 以来就存在于 `Graphics` 类中了。Java 2D API 使用了完全不同的、面向对象的方法。它使用的不是方法，而是类：

点击此处查看代码图像。

- `Line2D`
- `Rectangle2D`
- `RoundRectangle2D`
- `Ellipse2D`
- `Arc2D`
- `QuadCurve2D`
- `CubicCurve2D`
- `GeneralPath`

这些类都实现了 `Shape` 接口，我们将在接后的章节中检查它。

#### 11.2.1 形状类层次结构



`Line2D`、`Rectangle2D`、`RoundRectangle2D`、`Ellipse2D` 和 `Arc2D` 类对应于 `drawLine`、`drawRectangle`、`drawRoundRect`、`drawOval` 和 `drawArc` 方法。（“3D 矩形”的概念已经消失——没有对应的 `draw3DRect` 方法）。Java 2D API 提供了两个额外的类，即二次和三次曲线，我们将在本节中讨论。没有 `Polygon2D` 类；相反，`GeneralPath` 类描述了由直线、二次和三次曲线组成的路径。你可以使用 `GeneralPath` 来描述多边形；我们将在本节稍后的部分展示如何操作。

要绘制形状，首先创建一个实现 `Shape` 接口的类对象，然后调用 `Graphics2D` 类的 `draw` 方法。

### 类

点击此处查看代码图像。

- `Rectangle2D`
- `RoundRectangle2D`
- `Ellipse2D`
- `Arc2D`

都继承自一个公共父类 `RectangularShape`。承认的是，椭圆和弧并不是矩形，但它们有一个*边界矩形*（参见图 11.2）。

![Image](img/00245.jpeg)

**图 11.2** 椭圆和弧的边界矩形

每个以“2D”结尾的类有两个子类，用于用 `float` 或 `double` 数量指定坐标。在第一卷中，你已经遇到过 `Rectangle2D.Float` 和 `Rectangle2D.Double`。

其他类也使用了相同的方案，例如 `Arc2D.Float` 和 `Arc2D.Double`。

在内部，所有图形类都使用 `float` 坐标，因为 `float` 数字占存储空间较少，但对于几何计算来说精度足够。然而，Java 编程语言处理 `float` 数字变得稍微繁琐。出于这个原因，图形类的大多数方法使用 `double` 参数和返回值。只有在构造 2D 对象时，你才需要在带有 `float` 和 `double` 坐标的构造函数之间选择。例如：

```java
Rectangle2D floatRect = new Rectangle2D.Float(5F, 10F, 7.5F, 15F);
Rectangle2D doubleRect = new Rectangle2D.Double(5, 10, 7.5, 15);
```

`Xxx2D.Float` 和 `Xxx2D.Double` 类是 `Xxx2D` 类的子类。在对象构造后，记住子类几乎没有任何好处，你可以像上面的代码示例那样，将构造的对象存储在父类变量中。

从这些奇怪的名字中看出，`Xxx2D.Float` 和 `Xxx2D.Double` 类也是 `Xxx2D` 类的内部类。这只是为了避免外部类名称过于膨胀的一种微小的语法便利。

最后，`Point2D` 类描述了一个带有 `x` 和 `y` 坐标的点。点用于定义形状，但它们本身不是形状。

图 11.3 显示了形状类之间的关系。然而，省略了 `Double` 和 `Float` 子类。来自预 2D 库的旧类用灰色填充标记。

![Image](img/00246.jpeg)

**图 11.3** 形状类之间的关系

### 11.2.2 使用形状类

你已经在第一卷第 10 章中见过如何使用 `Rectangle2D`、`Ellipse2D` 和 `Line2D` 类。在本节中，你将学习如何处理剩余的 2D 形状。

对于 `RoundRectangle2D` 形状，指定左上角、宽度、高度以及 `x` 和 `y` 圆角尺寸（参见图 11.4）。

![Image](img/00247.jpeg)

**图 11.4** 构造 `RoundRectangle2D`

要构造弧，指定边界框、起始角度和封闭类型——参见第 13 页的图 11.5。

![Image](img/00248.jpeg)

**图 11.5** 构造弧

Java 2D API 支持*二次*和*三次*曲线。在本章中，我们不涉及这些曲线的数学。我们建议你通过运行列表 11.1 中的程序来感受曲线的外观。正如图 11.7 和 11.8 所示，二次和三次曲线是由两个*端点*和一个或两个*控制点*指定的。移动控制点会改变曲线的形状。

![Image](img/00250.jpeg)

**图 11.7** 二次曲线

![Image](img/00251.jpeg)

**图 11.8** 三次曲线

```java
CubicCurve2D c = new CubicCurve2D.Double(startX, startY, control1X, control1Y, control2X, control2Y, endX, endY);
```

二次曲线并不灵活，在实践中并不常用。然而，三次曲线（例如由 `CubicCurve2D` 类绘制的贝塞尔曲线）非常常见。通过组合许多三次曲线并使连接处的斜率匹配，你可以创建出复杂且视觉平滑的曲线形状。

欲了解更多信息，请参考由 James D. Foley、Andries van Dam、Steven K. Feiner 等人编写的 *Computer Graphics: Principles and Practice, Second Edition in C*（Addison-Wesley, 1995）。

你可以构建由线段、二次曲线和三次曲线组成的任意序列，并将它们存储在 `GeneralPath` 对象中。使用 `moveTo` 方法指定路径的第一个坐标，例如：

```java
GeneralPath path = new GeneralPath();
path.moveTo(10, 20);
```

然后你可以通过调用 `lineTo`、`quadTo` 或 `curveTo` 方法之一来扩展路径。这些方法通过线段、二次曲线或三次曲线来扩展路径。调用 `lineTo` 时提供终点。对于两个曲线方法，提供控制点，然后提供终点。例如：

```java
path.lineTo(20, 30);
path.curveTo(control1X, control1Y, control2X, control2Y, endX, endY);
```

调用 `closePath` 方法关闭路径。它会绘制一条返回路径起点的线。

要制作一个多边形，只需调用 `moveTo` 到第一个顶点，然后重复调用 `lineTo` 访问其他顶点。最后，调用 `closePath` 关闭多边形。代码列表 11.1 中的程序详细地展示了这一点。

通用路径不必非是连接的。你可以任何时候调用 `moveTo` 来开始一个新的路径段。

最后，你可以使用 `append` 方法将任意的 `Shape` 对象添加到通用路径中。形状的轮廓被添加到路径的末尾。`append` 方法的第二个参数为 `true`，则新形状将与路径上的上一点连接；否则为 `false`。例如：

```java
Rectangle2D r = . . .;
path.append(r, false);
```

这会将矩形的轮廓添加到路径中，但不与现有路径连接。但是：

```java
path.append(r, true);
```

这会从路径的终点画一条直线连接到矩形的起始点，然后将矩形轮廓添加到路径中。

代码列表 11.1 中的程序允许你创建示例路径。图 11.7 和图 11.8 显示了程序的示例运行。你可以从组合框中选择一个形状生成器。程序包含以下形状的生成器：

- 直线
- 矩形、圆矩形和椭圆
- 弧（除了弧本身外，还显示边界矩形以及起始和结束角度的线）
- 多边形（使用 `GeneralPath`）
- 二次和三次曲线

使用鼠标调整控制点。当你移动它们时，形状会不断重绘自己。

程序有点复杂，因为它处理了多种形状并支持拖动控制点。

抽象父类 `ShapeMaker` 封装了形状生成器类的共性。每个形状都有固定数量的控制点，用户可以移动这些点。`getPointCount` 方法返回该值。抽象方法：

```java
Shape makeShape(Point2D[] points)
```

根据控制点的当前位置计算出实际形状。`toString` 方法返回类名，以便 `ShapeMaker` 对象可以简单地放入 `JComboBox` 中。

为了启用控制点的拖动，`ShapePanel` 类处理了鼠标点击和鼠标移动事件。如果在矩形上方按下鼠标，随后的鼠标拖动将移动矩形。

绝大多数形状生成器类都是简单的——它们的 `makeShape` 方法只需构造并返回请求的形状。然而，`ArcMaker` 类需要计算变形后的起始和结束角度。此外，为了证明计算确实是正确的，返回的形状是一个 `GeneralPath`，其中包含了弧本身、边界矩形以及从弧中心到角度控制点的线（见图 11.9）。

### 图 1.9 `ShapeTest`

### 列表 1.1 `shapeTest.java`

```java
package shape;

import java.awt.*;
import java.awt.event.*;
import java.awt.geom.*;
import java.util.*;
import javax.swing.*;

/**
 * 此程序演示了 2D 形状。
 * @version 1.0 2016-5-10
 * @author Caymann
 */
public class ShapeTest {
    public static void main(String[] args) {
        EventQueue.invokeLater(() -> {
            JFrame frame = new ShapeTestFrame();
            frame.setTitle("ShapeTest");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }

    /**
     * 此框架包含一个用于选择形状的组合框和一个用于绘制它的组件。
     */
    class ShapeTestFrame extends JFrame {
        public ShapeTestFrame() {
            final ShapeComponent comp = new ShapeComponent();
            add(comp, BorderLayout.CENTER);
            final JComboBox<ShapeMaker> comboBox = new JComboBox<>();
            comboBox.addItem(new LineMaker());
            comboBox.addItem(new RectangleMaker());
            comboBox.addItem(new RoundRectangleMaker());
            comboBox.addItem(new EllipseMaker());
            comboBox.addItem(new ArcMaker());
            comboBox.addItem(new PolygonMaker());
            comboBox.addItem(new QuadCurveMaker());
            comboBox.addItem(new CubicCurveMaker());
            comboBox.addActionListener(event -> {
                ShapeMaker shapeMaker = comboBox.getItemAt(comboBox.getSelectedIndex());
                comp.setShapeMaker(shapeMaker);
            });
            add(comboBox, BorderLayout.NORTH);
            comp.setShape((ShapeMaker) comboBox.getItem(0));
            pack();
        }
    }
    // ... 其他代码部分保持逻辑一致
}
```

```java
{
    current = -1;
}
addMouseMotionListener(new MouseMotionAdapter()
{
    public void mouseDragged(MouseEvent event) {
        if (current == -1) return;
        points[current] = event.getPoint();
        repaint();
    }
});
current = -1;
}
```

```java
/**
 * 设置一个形状生成器并用随机点集初始化它。
 *
 * @param aShapeMaker 从点集定义形状的形状生成器
 */
public void setShapeMaker(ShapeMaker aShapeMaker) {
    shapeMaker = aShapeMaker;
    int n = shapeMaker.getPointCount();
    points = new Point2D[n];

    for (int i = 0; i < n; i++) {
        double x = generator.nextDouble() * getWidth();
        double y = generator.nextDouble() * getHeight();
        points[i] = new Point2D.Double(x, y);
    }

    repaint();
}

public void paintComponent(Graphics g) {
    if (points == null) return;

    Graphics2D g2 = (Graphics2D) g;

    for (int i = 0; i < points.length; i++) {
        double x = points[i].getX() - SIZE / 2;
        double y = points[i].getY() - SIZE / 2;
        g2.fill(new Rectangle2D.Double(x, y, SIZE, SIZE));
    }

    g2.draw(shapeMaker.makeShape(points));
}

public Dimension getPreferredSize() {
    return PREFERRED_SIZE;
}
```



```java
/**
 * 形状生成器可以根据点集创建一个形状。具体的子类必须在
 * makeShape 方法中返回一个形状。
 */
abstract class ShapeMaker {
    private int pointCount;

    /**
     * 构建形状生成器。
     *
     * @param pointCount 定义此形状所需的点数。
     */
    public ShapeMaker(int pointCount) {
        this.pointCount = pointCount;
    }

    /**
     * 获取定义此形状所需的点数。
     *
     * @return 点数
     */
    public int getPointCount() {
        return pointCount;
    }

    /**
     * 根据给定的点集创建形状。
     *
     * @param p 定义形状的点
     * @return 由这些点定义的形状
     */
    public abstract Shape makeShape(Point2D[] p);

    public String toString() {
        return getClass().getName();
    }
}

/**
 * 创建一条连接两个点的线。
 */
class LineMaker extends ShapeMaker {
    public LineMaker() {
        super(2);
    }

    public Shape makeShape(Point2D[] p) {
        return new Line2D.Double(p[0], p[1]);
    }
}

/**
 * 创建一个连接两个角点的矩形。
 */
class RectangleMaker extends ShapeMaker {
    public RectangleMaker() {
        super(2);
    }

    public Shape makeShape(Point2D[] p) {
        Rectangle2D s = new Rectangle2D.Double();
        s.setFrameFromDiagonal(p[0], p[1]);
        return s;
    }
}

/**
 * 创建一个连接两个角点的圆矩形。
 */
class RoundRectangleMaker extends ShapeMaker {
    public RoundRectangleMaker() {
        super(2);
    }

    public Shape makeShape(Point2D[] p) {
        RoundRectangle2D s = new RoundRectangle2D.Double(0, 0, 0, 0, 20, 20);
        s.setFrameFromDiagonal(p[0], p[1]);
        return s;
    }
}

/**
 * 创建一个包含在带有两个点的边界框内的椭圆。
 */
class EllipseMaker extends ShapeMaker {
    public EllipseMaker() {
        super(2);
    }

    public Shape makeShape(Point2D[] p) {
        Ellipse2D s = new Ellipse2D.Double();
        s.setFrameFromDiagonal(p[0], p[1]);
        return s;
    }
}

/**
 * 创建一个包含在带有两个点的边界框内的弧，其起始和
 * 结束角度由从边界框中心出发并于两个给定点的线
 * 决定。为了显示角度计算的正确性，返回的形状包含了弧、
 * 边界框以及这些线。
 */
class ArcMaker extends ShapeMaker {
    public ArcMaker() {
        super(4);
    }

    public Shape makeShape(Point2D[] p) {
        double centerX = (p[0].getX() + p[1].getX()) / 2;
        double centerY = (p[0].getY() + p[1].getY()) / 2;
        double width = Math.abs(p[1].getX() - p[0].getX());
        double height = Math.abs(p[1].getY() - p[0].getY());

        double skewedStartAngle = Math.toDegrees(Math.atan2(-(p[2].getY() - centerY) * width,
            (p[2].getX() - centerX) * height));
        double skewedEndAngle = Math.toDegrees(Math.atan2(-(p[3].getY() - centerY) * width,
            (p[3].getX() - centerX) * height));
        double skewedAngleDifference = skewedEndAngle - skewedStartAngle;
        if (skewedStartAngle < 0) skewedStartAngle += 360;
        if (skewedAngleDifference < 0) skewedAngleDifference += 360;

        Arc2D s = new Arc2D.Double(0, 0, 0, 0, skewedStartAngle, skewedAngleDifference, Arc2D.OPEN);
        s.setFrameFromDiagonal(p[0], p[1]);

        GeneralPath g = new GeneralPath();
        g.append(s, false);
        Rectangle2D r = new Rectangle2D.Double();
        r.setFrameFromDiagonal(p[0], p[1]); // 注意：此处此处有逻辑
        g.append(r, false);
        Point2D center = new Point2D.Double(centerX, centerY);
        g.append(new Line2D.Double(center, p[2]), false);
        return g;
    }
}

/**
 * 通过六点创建一个多边形。
 */
class PolygonMaker extends ShapeMaker {
    public PolygonMaker() {
        super(6);
    }

    public Shape makeShape(Point2D[] p) {
        GeneralPath s = new GeneralPath();
        s.moveTo((float) p[0].getX(), (float) p[0].getY());
        for (int i = 1; i < p.length; i++) {
            s.lineTo((float) p[i].getX(), (float) p[i].getY());
        }
        s.closePath();
        return s;
    }
}

/**
 * 通过两个端点和一个控制点创建一个二次曲线。
 */
class QuadCurveMaker extends ShapeMaker {
    public QuadCurveMaker() {
        super(3);
    }

    public Shape makeShape(Point2D[] p) {
        return new QuadCurve2D.Double(p[0].getX(), p[0].getY(), p[1].getX(), p[1].getY(),
            p[2].getX(), p[2].getY());
    }
}

/**
 * 通过两个端点和两个控制点创建一个三次曲线。
 */
class CubicCurveMaker extends ShapeMaker {
    public CubicCurveMaker() {
        super(4);
    }

    public Shape makeShape(Point2D[] p) {
        return new CubicCurve2D.Double(p[0].getX(), p[0].getY(), p[1].getX(), p[1].getY(),
            p[2].getX(), p[2].getY(), p[3].getX(), p[3].getY());
    }
}
```

- `RoundRectangle2.Double(double x, double y, double width, double height, double arcWidth, double arcHeight)`

根据给定的边界矩形和弧尺寸构造圆矩形。请参见图 11.4 以获取 `arcWidth` 和 `arcHeight` 参数的解释。

### `java.awt.geom.Arc2D.Double` 1.2

- `Arc2D.Double(double x, double y, double w, double h, double startAngle, double arcAngle, int type)`

根据给定的边界矩形、起始角、弧角和弧类型构造弧。`startAngle` 和 `arcAngle` 的解释见第 773 页。该类型为 `Arc2D.OPEN`、`Arc2D.PIE` 和 `Arc2D.CHORD` 之一。

### `java.awt.geom.QuadCurve2D.Double` 1.2

- `QuadCurve2D.Double(double x1, double y1, double ctrlx, double ctrly, double x2, double y2)`

根据起始点、控制点和终点构造二次曲线。

### `java.awt.geom.CubicCurve2D.Double` 1.2

- `CubicCurve2D.Double(double x1, double y1, double ctrlx1, double ctrly1, double ctrlx2, double ctrly2, double x2, double y2)`

根据起始点、两个控制点和终点构造三次曲线。

### `java.awt.geom.GeneralPath` 1.2

- `GeneralPath()`

构造一个空的通用路径。

### `java.awt.geom.Path2D.Float` 6

- `void moveTo(float x, float y)`

将 `(x`, `y)` 设为*当前点*——即下一个段的起始点。

- `void lineTo(float x, float y)`

- `void quadTo(float ctrlx, float ctrly, float x, float y)`

- `void curveTo(float ctrl1x, float ctrl1y, float ctrl2x, float ctrl2y, float x, float y)`

从当前点到终点 `(x`, `y)` 绘制直线、二次曲线或三次曲线，并将该终点设为当前点。

### `java.awt.geom.Path2D` 6

- `void append(Shape s, boolean connect)`

将给定形状的轮廓添加到通用路径中。如果 `connect` 为 `true`，则用直线将通用路径的当前点连接到所添加形状的起始点。

- `void closePath()`

通过从当前点到路径中的第一个点绘制直线来关闭路径。

## 11.3 区域

在上一节中，你已经看到如何通过构造由直线和曲线组成的通用路径来指定复杂形状。通过使用足够数量的直线和曲线，你可以绘制任何形状。例如，你在屏幕和打印输出上看到的字体字符形状都是由直线和三次曲线组成的。

有时，通过组合*区域*（如矩形、多边形或椭圆）来描述一个形状更为简单。Java 2D API 支持四种*构造性区域几何*操作，可以将两个区域合并为一个新区域。

- `add`：合并后的区域包含位于第一个区域或第二个区域的所有点。
- `subtract`：合并后的区域包含位于第一个区域但不在第二个区域的所有点。
- `intersect`：合并后的区域包含位于第一个区域和第二个区域的所有点。
- `exclusiveOr`：合并后的区域包含位于第一个或第二个区域但不同于两者之中的点。

图 11.10 显示了这些操作。

![Image](img/00253.jpeg)

**图 11.10** 构造性区域几何操作

要构造复杂区域，从一个默认区域对象开始。

```java
Area a = new Area();
```

然后，将区域与任何形状合并。

点击查看代码图像

```java
a.add(new Rectangle2D.Double(. . .));
a.subtract(path);
```

. . .

`Area` 类实现了 `Shape` 接口。你可以使用 `Graphics2D` 类的 `draw` 方法描边区域的边界，或使用 `fill` 方法填充内部。

### `java.awt.geom.Area`

- `void add(Area other)`
- `void subtract(Area other)`
- `void intersect(Area other)`
- `void exclusiveOr(Area other)`

此区域与另一个区域执行构造性区域几何操作，并将此区域设置为结果。

## 11.4 笔触

`Graphics2D` 类的 `draw` 操作通过当前选的*笔触*（stroke）绘制形状的边界。默认情况下，笔触是实线。你可以通过调用 `setStroke` 方法并传递 `Stroke` 对象来更改笔触。`Stroke` 接口定义了形状如何被描边。在本节中，我们将查看 `BasicStroke` 类。

Java 2D API 支持将两个区域合并为一个新区域的四种构造性区域几何操作。

该程序与 Listing 11.1 中的程序类似。鼠标监听器记录了你在线段端点的点击操作，而鼠标移动监听器则监控端点的拖动。一组单选按钮允许用户选择端点样式（cap）、连接样式（join）以及实线或虚线。`StrokePanel` 类的 `paintComponent` 方法构造了一个 `GeneralPath`，该路径由两条线段组成，这两条线段连接了用户可以用鼠标移动的三个点。然后，它根据用户的选择构造一个 `BasicStroke`，最后绘制该路径。

### 列表 11.2 `stroke/StrokeTest.java`

点击此处查看代码



```java
package stroke;

import java.awt.*;
import java.awt.event.*;
import java.awt.geom.*;
import javax.swing.*;

/**
 * 此程序演示了不同的描边类型。
 * @version 1.04 2016-05-10
 * @author Cay Horstmann
 */
public class StrokeTest {
    public static void main(String[] args) {
        EventQueue.invokeLater(() -> {
            JFrame frame = new StrokeTestFrame();
            frame.setTitle("StrokeTest");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}

/**
 * 此框架允许用户选择端点样式、连接和线条样式，并显示生成的描边效果。
 */
class StrokeTestFrame extends JFrame {
    private StrokeComponent canvas;
    private JPanel buttonPanel;

    public StrokeTestFrame() {
        canvas = new StrokeComponent();
        add(canvas, BorderLayout.CENTER);

        buttonPanel = new JPanel();
        buttonPanel.setLayout(new GridLayout(3, 3));
        add(buttonPanel, BorderLayout.NORTH);

        ButtonGroup group1 = new ButtonGroup();
        makeCapButton("Butt Cap", BasicStroke.CAP_BUTT, group1);
        makeCapButton("Round Cap", BasicStroke.CAP_ROUND, group1);
        makeCapButton("Square Cap", BasicStroke.CAP_SQUARE, group1);

        ButtonGroup group2 = new ButtonGroup();
        makeJoinButton("Miter Join", BasicStroke.JOIN_MITER, group2);
        makeJoinButton("Bevel Join", BasicStroke.JOIN_BEVEL, group2);
        makeJoinButton("Round Join", BasicStroke.JOIN_ROUND, group2);

        ButtonGroup group3 = new ButtonGroup();
        makeDashButton("Solid Line", false, group3);
        makeDashButton("Dashed Line", true, group3);
    }

    /**
     * 创建一个用于端点样式的单选按钮。
     * @param label 按钮标签
     * @param style 端点样式
     * @param group 单选按钮组
     */
    private void makeCapButton(String label, int style, ButtonGroup group) {
        boolean selected = group.getButtonCount() == 0;
        JRadioButton button = new JRadioButton(label, selected);
        buttonPanel.add(button);
        group.add(button);
        button.addActionListener(event -> canvas.setCap(style));
        pack();
    }

    /**
     * 创建一个用于连接样式的单选按钮。
     * @param label 按钮标签
     * @param style 连接样式
     * @param group 单选按钮组
     */
    private void makeJoinButton(String label, int style, ButtonGroup group) {
        boolean selected = group.getButtonCount() == 0;
        JRadioButton button = new JRadioButton(label, selected);
        buttonPanel.add(button);
        group.add(button);
        button.addActionListener(event -> canvas.setJoin(style));
    }

    /**
     * 创建一个用于设置实线或虚线的单选按钮。
     * @param label 按钮标签
     * @param style false 表示实线，true 表示虚线
     * @param group 单选按钮组
     */
    private void makeDashButton(String label, boolean style, ButtonGroup group) {
        boolean selected = group.getButtonCount() == 0;
        JRadioButton button = new JRadioButton(label, selected);
        buttonPanel.add(button);
        group.add(button);
        button.addActionListener(event -> canvas.setDash(style));
    }
}

/**
 * 此组件使用描边对象绘制连接的线条，并允许用户
 * 拖动三个点。
 */
class StrokeComponent extends JComponent {
    private static Dimension PREFERRED_SIZE = new Dimension(400, 400);
    private static int SIZE = 0;

    Point2D[] points;
    int current;
    float width;
    int cap;
    int join;
    boolean dash;

    public StrokeComponent() {
        addMouseListener(new MouseAdapter() {
            public void mousePressed(MouseEvent event) {
                Point p = event.getPoint();
                for (int i = 0; i < points.length; i++) {
                    double x = points[i].getX() - SIZE / 2;
                    double y = points[i].getY() - SIZE / 2;
                    Rectangle2D r = new Rectangle2D.Double(x, y, SIZE, SIZE);
                    if (r.contains(p)) {
                        current = i;
                        return;
                    }
                }
            }

            public void mouseReleased(MouseEvent event) {
                current = -1;
            }
        });

        addMouseMotionListener(new MouseMotionAdapter() {
            public void mouseDragged(MouseEvent event) {
                if (current == -1) return;
                points[current] = event.getPoint();
                repaint();
            }
        });

        points = new Point2D[3];
        points[0] = new Point2D.Double(200, 100);
        points[1] = new Point2D.Double(100, 200);
        points[2] = new Point2D.Double(200, 200);
        current = -1;
        width = 8.0F;
    }

    public void paintComponent(Graphics g) {
        Graphics2D g2 = (Graphics2D) g;
        GeneralPath path = new GeneralPath();
        path.moveTo((float) points[0].getX(), (float) points[0].getY());

        for (int i = 1; i < points.length; i++) {
            path.lineTo((float) points[i].getX(), (float) points[i].getY());
        }

        BasicStroke stroke;
        if (dash) {
            float miterLimit = 10.0F;
            float[] dashPattern = {
                10F, 10F, 10F, 10F, 10F, 10F, 30F, 10F,
                30F, 10F, 30F, 10F, 10F, 10F, 10F, 10F, 30F
            };
            float dashPhase =
            stroke = new BasicStroke(width, cap, join, miterLimit, dashPattern, dashPhase);
        } else {
            stroke = new BasicStroke(width, cap, join);
        }

        g2.setStroke(stroke);
        g2.draw(path);
    }

    /**
     * 设置连接样式。
     * @param j 连接样式
     */
    public void setJoin(int j) {
        join = j;
        repaint();
    }

    /**
     * 设置端点样式。
     * @param c 端点样式
     */
    public void setCap(int c) {
        cap = c;
        repaint();
    }
}
```

```java
public void setCap(int c)
{
    cap = c;
    repaint();
}

/**
 * 设置实线或虚线。
 * @param d false 表示实线，true 表示虚线。
 */
public void setDash(boolean d)
{
    dash = d;
    repaint();
}

public Dimension getPreferredSize() { return PREFERRED_SIZE; }
```

### `java.awt.Graphics2D` `1.2`

- `void setStroke(Stroke s)`

将此图形上下文的描边样式设置为实现 `Stroke` 接口的给定对象。

### `java.awt.BasicStroke` `1.2`

- `BasicStroke(float width)`

- `BasicStroke(float width, int cap, int join)`

- `BasicStroke(float width, int cap, int join, float miterlimit)`

- `BasicStroke(float width, int cap, int join, float miterlimit, float[] dash, float dashPhase)`

根据给定属性构造一个描边对象。

![Image](img/00258.jpeg)

### 11.5 Paint

当你填充一个形状时，其内部会被 `paint` 覆盖。使用 `setPaint` 方法将绘制样式设置为一个实现 `Paint` 接口的类的对象。Java 2D API 提供了三个此类类：

- `Color` 类实现了 `Paint` 接口。要用实色填充形状，只需使用 `Color` 对象调用 `setPaint`，例如：

```java
g2.setPaint(Color.red);
```

- `GradientPaint` 类通过在两个给定的颜色值之间插值来改变颜色（参见图 11.15）。

![Image](img/00259.jpeg)

**图 11.15** 渐变绘制

- `TexturePaint` 类通过图像的图像来填充区域（参见图 11.16）。

![Image](img/00260.jpeg)

**图 11.16** 纹理绘制

你可以通过指定两个点以及你想在这两个点处的颜色来构造一个 `GradientPaint` 对象。

点击此处查看代码图像

```java
g2.setPaint(new GradientPaint(p1, Color.RED, p2, Color.YELLOW));
```

颜色沿着连接两个点的直线进行插值。在垂直于该连接线的线线上，颜色保持恒定。超出直线终点的点将赋予该终点的颜色。

另一种，如果你在调用 `GradientPaint` 构造函数并将 `cyclic` 参数设为 `true`，

点击此处查看代码图像

```java
g2.setPaint(new GradientPaint(p1, Color.RED, p2, Color.YELLOW, true));
```

那么颜色变化将变为“循环”，并在终点之外继续变化。

要构造 `TexturePaint` 对象，请指定一个 `BufferedImage` 和一个 `anchor` 矩形。

点击此处查看代码图像

```java
g2.setPaint(new TexturePaint(bufferedImage, anchorRectangle));
```

我们将在在本章后面详细讨论图像时引入 `BufferedImage` 类。获取缓冲图像的最简单方法是读取图像文件：

点击此处查看代码图像

```java
bufferedImage = ImageIO.read(new File("blue-ball.gif"));
```

锚点矩形在 `x` 和 `y` 方向上无限扩展以平铺整个坐标平面。图像被缩放以适应锚点区域，然后复制到每个瓦格中。

### `java.awt.Graphics2D` `1.2`

- `void setPaint(Paint s)`

将此图形上下文的绘制样式设置为实现 `Paint` 接口的给定对象。

### `java.awt.GradientPaint` `1.2`

- `GradientPaint(float x1, float y1, Color color1, float x2, float y2, Color color2)`

- `GradientPaint(float x1, float y1, Color color1, float x2, float y2, Color color2, boolean cyclic)`

- `GradientPaint(Point2D p1, Color color1, Point2D p2, Color color2)`

- `GradientPaint(Point2D p1, Color color1, Point2D p2, Color color2, boolean cyclic)`



构造一个渐变绘制对象，用颜色填充形状，使得起点被 `color1` 填充，终点被 `color2` 填充，中间颜色进行线性插值。在垂直于连接起点和终点的线的线上，颜色保持恒定。默认情况下，渐变绘制不是循环的——也就是说，超出起点和终点的点将与起点和终点相同的颜色。如果渐变绘制是循环的，颜色将继续进行插值，首先返回起点颜色，然后在两个方向上无限重复。

### `java.awt.TexturePaint` 1.2

- `TexturePaint(BufferedImage texture, Rectangle2D anchor)`

创建一个纹理绘制对象。锚点矩形定义了要绘制空间的平铺方式；它在 `x` 和 `y` 方向上无限重复，纹理图像被缩放以填充每个瓦格。

## 11.6 坐标变换

假设你需要画一个对象，例如汽车。根据制造商的规格，你知道它的高度、轴距和总长度。当然，你可以计算出所有的像素位置，假设每米有若干个像素。然而，有一种更简单的方法：你可以要求图形上下文替你完成转换。

点击此处查看代码图像

```java
g2.scale(pixelsPerMeter, pixelsPerMeter);
g2.draw(new Line2D.Double(coordinates in meters)); // 转换为像素并绘制缩放线
```

`Graphics2D` 类的 `scale` 方法将图形上下文的 `coordinate transformation` 设置为缩放变换。该变换将 `user coordinates`（用户指定的单位）转换为 `device coordinates`（像素）。图 11.17 显示了变换如何工作。

![Image](img/00261.jpeg)

**图 11.17** 用户坐标与设备坐标

坐标变换在实践中非常有用。它们允许你使用方便的坐标值。图形上下文负责将它们转换为像素的脏活。有四种基本变换：

- 缩放：放大或缩小相对于固定点的距离
- 旋转：绕固定中心旋转
- 平移：移动所有点的固定距离
- 切变：固定一条直线，并按与其距离成比例的量滑动平行线

图 11.18 显示了这四种基本变换如何作用于正方形。

![Image](img/00262.jpeg)

**图 11.18** 基本变换

`Graphics2D` 类的 `scale`、`rotate`、`translate` 和 `shear` 方法将图形上下文的坐标变换设置为这些基本变换之一。

你可以组合这些变换。例如，你可能想旋转形状并将其大小翻倍；同时提供旋转和缩放变换：

点击此处查看代码图像

```java
g2.rotate(angle);
g2.scale(2, 2);
g2.draw(. . .);
```

在这种情况下，提供变换的顺序并不重要。然而，对于大多数变换，顺序是重要的。例如，如果你想旋转和切变，那么先提供哪种变换会有区别。你需要弄清楚你的意图。图形上下文将按照与你提供的相反的顺序应用变换——也就是说，你最后提供的变换最先应用。

你可以提供任意数量的变换。例如，考虑以下变换序列：

点击此处查看代码图像

```java
g2.translate(x, y);
g2.rotate(a);
g2.translate(-x, -y);
```

最后一次变换（最先应用）将点 `(x, y)` 移动到原点。第二次变换绕原点旋转角度 `a`。最后一次变换将原点移回 `(x, y)`。其整体效果是以点 `(x, y)` 为中心进行旋转——参见图 11.19。由于绕除原点以外的点进行旋转是一个非常常见的操作，因此有一个快捷方法：

```java
g2.rotate(a, x, y);
```

![Image](img/00263.jpeg)

**图 11.19** 组合变换

如果你了解一些矩阵理论，可能已经意识到所有的旋转、平移、缩放、剪切及其组合都可以用如下所示的变换矩阵表示：

![Image](img/00264.jpeg)

这种变换被称为仿射变换（affine transformation）。在 Java 2D API 中，`AffineTransform` 类描述了这种变换。如果你知道特定变换矩阵的分量，可以直接按如下方式构建它：

点击此处查看代码图像

```java
AffineTransform t = new AffineTransform(a, b, c, d, e, f);
```

此外，工厂方法 `getRotateInstance`、`getScaleInstance`、`getTranslateInstance` 和 `getShearInstance` 构建了表示这些变换类型的矩阵。例如，调用：

点击此处查看代码图像

```java
t = AffineTransform.getScaleInstance(2.0F, 0.5F);
```

返回一个对应于矩阵的变换：

![Image](img/00265.jpeg)

最后，实例方法 `setToRotation`、`setToScale`、`setToTranslation` 和 `setToShear` 将变换对象设置为新类型。这里是一个示例：

点击此处查看代码图像

```java
t.setToRotation(angle); // 将 t 设置为旋转
```

你可以将图形上下文的坐标变换设置为一个 `AffineTransform` 对象。

点击此处查看代码图像

```java
g2.setTransform(t); // 替换当前变换
```

然而，在实践中，你不应该调用 `setTransform` 操作，因为它会替换图形上下文可能拥有的任何现有变换。例如，横向模式打印的图形上下文已经包含了一个 90 度的旋转变换。如果你调用 `setTransform`，就会抹掉该旋转。相反，请调用 `transform` 方法。

点击此处查看代码图像

```java
g2.transform(t); // 将当前变换与 t 组合
```

它将现有的变换与新的 `AffineTransform` 对象组合在一起。

如果你只想临时应用某种变换，先获取旧变换，将其与你的新变换组合，最后在完成后恢复旧变换。

点击此处查看代码图像

```java
AffineTransform oldTransform = g2.getTransform(); // 保存旧变换
g2.transform(t); // 应用临时变换
在 g2 上绘图
g2.setTransform(oldTransform); // 恢复旧变换
```

***

### `java.awt.geom.AffineTransform` 1.2

- `AffineTransform(double a, double b, double c, double d, double e, double f)`
- `AffineTransform(float a, float b, float c, float d, float e, float f)`

使用矩阵构建仿射变换。

![Image](img/00266.jpeg)

- `AffineTransform(double[] m)`
- `AffineTransform(float[] m)`

使用矩阵构建仿射变换。

![Image](img/00267.jpeg)

- `static AffineTransform getRotateInstance(double a)`

绕原点旋转角度 `a`（弧度）。变换矩阵为：

![Image](img/00268.jpeg)

如果 `a` 于 0 和 ![Image](img/00269.jpeg) 之间，旋转将正 `x` 轴向正 `y` 轴移动。

- `static AffineTransform getRotateInstance(double a, double x, double y)`

绕点 `(x, y)` 旋转角度 `a`（弧度）。

- `static AffineTransform getScaleInstance(double sx, double sy)`

创建一个缩放变换，将 `x` 轴缩放 `sx` 倍，将 `y` 轴缩放 `sy` 倍。变换矩阵为：

![Image](img/00270.jpeg)

- `static AffineTransform getShearInstance(double shx, double shy)`

创建一个剪切变换，将 `x` 轴剪切 `shx`，将 `y` 轴剪切 `shy`。变换矩阵为：

![Image](img/00271.jpeg)

- `static AffineTransform getTranslateInstance(double tx, double ty)`

创建一个平移，将 `x` 轴移动 `tx`，将 `y` 轴移动 `ty`。变换矩阵为：

![Image](img/00272.jpeg)

- `void setToRotation(double a)`
- `void setToRotation(double a, double x, double y)`
- `void setToScale(double sx, double sy)`
- `void setToShear(double shx, double shy)`
- `void setToTranslation(double tx, double ty)`

***

## 11.7 裁剪

通过在图形文中设置裁剪形状（clipping shape），可以将所有的绘制操作限制在裁剪形状内部。

然而，在实践中，你不希望调用 `setTransform` 操作，因为它会替换图形上下文可能拥有的任何现有变换。例如，正如本章后面所示，打印的图形上下文带有一个裁剪矩形，以确保你不会在页边距绘图。相反，请调用 `clip` 方法。

`clip` 方法将现有裁剪形状与提供的新形状求交。

如果你只想临时应用裁剪区域，应该获取旧裁剪，添加新裁剪，完成后恢复旧裁剪。

图 11.20 中，我们通过一种非常戏剧性的绘制展示了裁剪能力：即用一个复杂的形状裁剪线条图案——具体来说是一组字母的轮廓。

为了获取字符轮廓，你需要一个字体渲染上下文（font render context）。使用 `Graphics2D` 类的 `getFontRenderContext` 方法。

接下来，使用字符串、字体和字体渲染上下文创建一个 `TextLayout` 对象。

此文本布局对象描述了系列字符的布局，这些布局是由特定的字体渲染上下文渲染的。布局取决于字体渲染上下文——相同的字符在屏幕和打印机上的显示会有不同。

对于我们的应用程序而言，更重要的是 `getOutline` 方法返回一个 `Shape` 对象，该对象描述了文本布局中字符轮廓的形状。轮廓形状始于原点 `(0, 0)`，这可能不是你想要的。在这种情况下，请为 `getOutline` 操作提供一个仿射变换（affine transform），以指定你希望轮廓出现的位置。

点击此处查看代码图片

```java
AffineTransform transform = AffineTransform.getTranslateInstance(0, 100);

Shape outline = layout.getOutline(transform);
```

然后，将轮廓添加到裁剪形状（clipping shape）中。

点击此处查看代码图片

```java
GeneralPath clipShape = new GeneralPath();
clipShape.append(outline, false);
```

最后，设置裁剪形状并绘制一组线条。这些线条只出现在字符边界内部。

点击此处查看代码图片

```java
g2.setClip(clipShape);

Point2D p = new Point2D.Double(0, 0);

for (int i = 0; i < NLINES; i++)
{
    double x = . . .;
    double y = . . .;
    Point2D q = new Point2D.Double(x, y);
    g2.draw(new Line2D.Double(p, q)); // 线条被裁剪的
}
```

***

### `java.awt.Graphics` 1.0

- `void setClip(Shape s)` 1.2

  将当前裁剪形状设置为形状 `s`。

- `Shape getClip()` 1.2

  返回当前的裁剪形状。

***

### `java.awt.Graphics2D` 1.2

- `void clip(Shape s)`

  将当前裁剪形状与形状 `s` 取交集。

- `FontRenderContext getFontRenderContext()`

  返回一个构建 `TextLayout` 对象所需的字体渲染上下文。

***

### `java.awt.font.TextLayout` 1.2

- `TextLayout(String s, Font f, FontRenderContext context)`

  从给定的字符串和字体构造文本布局对象，使用字体渲染上下文获取针对特定设备的字体属性。

- `float getAdvance()`

  返回此文本布局的宽度。

- `float getAscent()`
- `float getDescent()`

  返回此文本布局在基线之上和下方的高度。

- `float getLeading()`

  返回此文本布局所用字体中连续行之间的距离。

***

## 11.8 透明度与合成

在标准的 RGB 色彩模型中，每种颜色都通过其红、绿、蓝分量来描述。然而，描述图像中透明或半透明的区域同样方便。当将图像叠加到现有的图形上时，透明像素完全不会遮挡下方的像素，而半透明像素则与下方的像素混合。图 11.21 显示了在图像上叠加一个半透明矩形的效果。你仍然可以看到图像的细节从矩形透出来。

![图像](img/00274.jpeg)

**图 11.21** 在图像上叠加半透明矩形

在 Java 2D API 中，透明度通过 alpha 通道（alpha channel）来描述。每个像素除了红、绿、蓝颜色分量外，还有一个于 0（完全透明）到 1（完全不透明）之间的 alpha 值。例如，图 11.21 中的矩形是用具有 50% 透明度的淡黄色填充的：

点击此处查看代码图片

```java
new Color(0.7F, 0.7F, 0.0F, 0.5F);
```

现在让我们来看看如果叠加两个形状会发生什么。你需要混合或合成源像素和目标像素的颜色以及 alpha 值。Porter 和 Duff 是计算机图形领域的两位研究人员，他们为这种混合过程制定了 12 种可能的合成规则。Java 2D API 实现了所有这些规则。在继续之前，我们想指出，这些规则中只有两个具有实际意义。如果你觉得这些规则深奥或令人困惑，只需使用 `SRC_OVER` 规则即可。它是 `Graphics2D` 对象的默认规则，并能提供最直观的结果。

这里是规则背后的理论。假设你有一个 alpha 值为 `a[S]` 的源像素。在图像中已经有一个 alpha 值为 `a[D]` 的目标像素。你想合成这两个像素。图 11.22 中的图表显示了如何设计合成规则。

![图像](img/00275.jpeg)

**图 11.22** 设计合成规则

（注：原文后续部分似乎存在乱码或重复逻辑错误，已根据上下文进行逻辑性翻译）

Porter 和 Duff 考虑了源像素的 alpha 值为 1 的情况，此时目标颜色不受影响。如果 `a[S]` 为 0，则源完全透明，目标颜色保持不变。

（注：原文后半部分存在大量重复且无意义的字符组合，翻译时已根据技术文档语境进行处理）

随后将矩形涂成蓝色，alpha 值为 0.5。由于组合规则为 `SRC_OVER`，它将透明地叠加在现有图像上。

代码列表 11.3 中的程序允许您探索这些组合规则。从组合框中选择一种规则，并使用滑动块设置 `AlphaComposite` 对象的 alpha 值。

此外，程序还显示了每个规则的文字描述。请注意，这些描述是根据组合规则图计算的。例如，第二行中的 `"DS"` 代表“与目标混合（blends with destination）”。

该程序有一个重要的转折。无法保证对应屏幕的图形上下文具有 alpha 通道。（事实上，它通常没有）。当像素被写入没有 alpha 通道的道区域时，像素颜色将与 alpha 值相乘，并丢弃 alpha 值。现在，若干条 Porter–Duff 规则使用了目标的 alpha 值，这意味着目标的 alpha 通道至关重要。因此，我们使用带有 `ARGB` 颜色模型的 `BufferedImage` 来组合形状。图像组合完成后，我们将结果图像绘制到屏幕上。

点击此处查看代码图像

```java
BufferedImage image = new BufferedImage(getWidth(), getHeight(), BufferedImage.TYPE_INT_ARGB);

Graphics2D gImage = image.createGraphics();

// now draw to gImage

g2.drawImage(image, null, 0, 0);
```

代码列表 11.3 和 11.4 显示了框架和组件类。代码列表 11.5 中的 `Rule` 类为每个规则提供了简要解释——参见图 11.24。在运行程序时，将 alpha 滑动块从左向右移动，以观察对组合形状的影响。特别注意，`DST_IN` 和 `DST_OUT` 规则之间的唯一区别在于当更改源 alpha 时，目标（！）颜色的变化方式。

![Image](img/00278.jpeg)

**图 11.24** `CompositeTest` 程序

**代码列表 11.3** `composite/CompositeTestFrame.java`

***

点击此处查看代码图像

***



```java
package composite;

import java.awt.*;

import javax.swing.*;

/**
 * 此框架包含一个用于选择组合规则的组合框、一个用于源
 * alpha 通道的滑动块，以及一个显示组合结果的组件。
 */
class CompositeTestFrame extends JFrame
{
    private static final int DEFAULT_WIDTH = 400;
    private static final int DEFAULT_HEIGHT = 400;

    private CompositeComponent canvas;
    private JComboBox<Rule> ruleCombo;
    private JSlider alphaSlider;
    private JTextField explanation;

    public CompositeTestFrame()
    {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

        canvas = new CompositeComponent();
        add(canvas, BorderLayout.CENTER);

        ruleCombo = new JComboBox<>(new Rule[] { new Rule("CLEAR", " ", " "),
            new Rule("SRC", " S", " S"), new Rule("DST", " ", "DD"),
            new Rule("SRC_OVER", " S", "DS"), new Rule("DST_OVER", " S", "DD"),
            new Rule("SRC_IN", " ", " S"), new Rule("SRC_OUT", " S", " "),
            new Rule("DST_IN", " ", " D"), new Rule("DST_OUT", " ", "D "),
            new Rule("SRC_ATOP", " ", "DS"), new Rule("DST_ATOP", " S", " D"),
            new Rule("XOR", " S", "D "), });
        ruleCombo.addActionListener(event ->
        {
            Rule r = (Rule) ruleCombo.getSelectedItem();
            canvas.setRule(r.getValue());
            explanation.setText(r.getExplanation());
        });

        alphaSlider = new JSlider(0, 100, 75);
        alphaSlider.addChangeListener(event -> canvas.setAlpha(alphaSlider.getValue()));
        JPanel panel = new JPanel();
        panel.add(ruleCombo);
        panel.add(new JLabel("Alpha"));
        panel.add(alphaSlider);
        add(panel, BorderLayout.NORTH);

        explanation = new JTextField();
        add(explanation, BorderLayout.SOUTH);

        canvas.setAlpha(alphaSlider.getValue());
        Rule r = ruleCombo.getItem(ruleCombo.getSelectedIndex());
        canvas.setRule(r.getValue());
        explanation.setText(r.getExplanation());
    }
}
```

**代码列表 1.4** `composite/CompositeComponent.java`

点击此处查看代码图像

***

```java
package composite;

import java.awt.*;
import java.awt.geom.*;
import java.awt.image.*;
import javax.swing.*;

/**
 * 此组件绘制两个形状，并使用组合规则。
 */
class CompositeComponent extends JComponent
{
    private int rule;
    private Shape shape1;
    private Shape shape2;
    private float alpha;

    public CompositeComponent()
    {
        shape1 = new Ellipse2D.Double(0, 0, 150, 100);
        shape2 = new Rectangle2D.Double(150, 50, 150, 100);
    }

    public void paintComponent(Graphics g)
    {
        Graphics2D g2 = (Graphics2D) g;
        BufferedImage image = new BufferedImage(getWidth(), getHeight(), BufferedImage.TYPE_INT_ARGB);
        Graphics2D gImage = image.createGraphics();
        gImage.setPaint(Color.red);
        gImage.fill(shape1);
        AlphaComposite composite = AlphaComposite.getInstance(rule, alpha);
        gImage.setComposite(composite);
        gImage.setPaint(Color.blue);
        gImage.fill(shape2);
        g2.drawImage(image, null, 0, 0);
    }

    /**
     * 设置组合规则。
     * @param r 规则（AlphaComposite 常量）
     */
    public void setRule(int r)
    {
        rule = r;
        repaint();
    }

    /**
     * 设置源 alpha。
     * @param a 0 到 100 之间的值
     */
    public void setAlpha(int a)
    {
        alpha = (float) a / 100.0F;
        repaint();
    }
}
```

**代码列表 11.5** `composite/Rule.java`

点击此处查看代码图像

***

```java
package composite;

import java.awt.*;

/**
 * 此类描述 Porter-Duff 规则。
 */
class Rule
{
    private String name;
    private String porterDuff1;
    private String porterDuff2;

    /**
     * 构造一个 Porter-Duff 规则。
     * @param n 规则名称
     * @param pd1 Porter-Duff 方格的第一行
     * @param pd2 Porter-Duff 方格的第二行
     */
    public Rule(String n, String pd1, String pd2)
    {
        name = n;
        porterDuff1 = pd1;
        porterDuff2 = pd2;
    }

    /**
     * 获取此规则的解释。
     * @return 解释
     */
    public String getExplanation()
    {
        StringBuilder r = new StringBuilder("Source ");
        if (porterDuff2.equals(" ")) r.append("clears");
        if (porterDuff2.equals(" S")) r.append("overwrites");
        if (porterDuff2.equals("DS")) r.append("blends with");
        if (porterDuff2.equals(" D")) r.append("alpha modifies");
        if (porterDuff2.equals("D ")) r.append("alpha complement modifies");
        if (porterDuff2.equals("DD")) r.append("does not affect");
        r.append(" destination");
        return r.toString();
    }
}
```

```java
if (porterDuff1.equals(" S")) r.append(" and overwrites empty pixels");
r.append(".");
return r.toString();
}

public String toString() {
    return name;
}

/**
 * 获取 AlphaComposite 类中此规则的值。
 * @return AlphaComposite 常量值，如果没有找到匹配的常量，则返回 -1
 */
public int getValue() {
    try {
        return (Integer) AlphaComposite.class.getField(name).get(null);
    } catch (Exception e) {
        return -1;
    }
}
```

### `java.awt.Graphics2D` 1.2

- `void setComposite(Composite s)` 将此图形上下文的复合模式设置为实现了 `Composite` 接口的给定对象。

### `java.awt.AlphaComposite` 1.2

- `static AlphaComposite getInstance(int rule)`

- `static AlphaComposite getInstance(int rule, float sourceAlpha)`

构造一个 Alpha 复合对象。规则可以是 `CLEAR`、`SRC`、`SRC_OVER`、`DST_OVER`、`SRC_IN`、`SRC_OUT`、`DST_IN`、`DST_OUT`、`DST`、`DST_ATOP`、`SRC_ATOP`、`XOR` 之一。

## 11.9 渲染提示 (Rendering Hints)

在前面的章节中你看到渲染过程是非常复杂的。尽管 Java 2D API 在大多数情况下速度很快，但有时你希望控制速度与质量之间的权衡。你可以通过设置 `rendering hints` 实现。`Graphics2D` 类的 `setRenderingHint` 方法允许你设置单个提示。提示的键和值在 `RenderingHints` 类中声明。表 11.2 总结了这些选择。以 `_DEFAULT` 结尾的值表示特定实现所选择的性能与质量之间权衡的默认值。

![Image](img/00279.jpeg)

**表 11.2** 渲染提示

这些设置中最用的是 `antialiasing`（抗锯齿）。这种技术消除了斜线和曲线上的“锯齿”。正如图 11.25 所示，斜线必须以像素的“阶梯状”形式绘制。特别是在低分辨率屏幕上，这种线看起来可能很丑。但如果不是完全将每个像素开启或关闭，而是根据线条覆盖像素的面积比例为部分覆盖的像素填充颜色值，那么结果看起来就会平滑得多。这种技术被称为抗锯齿。当然，抗锯齿需要更长时间，因为它必须计算所有这些颜色值。

![Image](img/00280.jpeg)

**图 11.25** 抗锯齿

例如，这里是如何请求使用抗锯齿：

点击此处查看代码图像

```java
g2.setRenderingHint(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
```

对字体使用抗锯齿也是意义的。

点击此处查看代码图像

```java
g2.setRenderingHint(RenderingHints.KEY_TEXT_ANTIALIASING,
      RenderingHints.VALUE_TEXT_ANTIALIAS_ON);
```

其他的渲染提示并不那么常用。

你也可以将一组键/值提示对放入 map 中，并通过调用 `setRenderingHints` 方法一次性设置所有它们。任何实现 map 接口的集合类都可以，但你也可以使用 `RenderingHints` 类本身。它实现了 `Map` 接口，并在向构造函数传递 `null` 时提供默认的 map 实现。例如，

点击此处查看代码图像

```java
RenderingHints hints = new RenderingHints(null);
hints.put(RenderingHints.KEY_ANTIALIASING, RenderingHints.VALUE_ANTIALIAS_ON);
hints.put(RenderingHints.KEY_TEXT_ANTIALIASING, RenderingHints.VALUE_TEXT_ANTIALIAS_ON);
g2.setRenderingHints(hints);
```

这就是我们在示例 11.6 中使用的技术。程序显示了我们发现的几个渲染提示。注意以下点：

- 抗锯齿使椭圆变得平滑。

- 文字抗锯齿使文本变得平滑。

- 在某些平台上，分数度量（fractional metrics）会让字母稍微靠拢。

- 选择 `VALUE_RENDER_QUALITY` 会使缩后的图像平滑（通过将 `KEY_INTERPOLATION` 设置为 `VALUE_INTERPOLATION_BICUB` 可以获得相同的效果）。

- 当关闭抗锯齿时，选择 `VALUE_STROKE_NORMALI` 会改变椭圆的外观和对角线的位置。

图 1.26 显示了程序的截图。

![Image](img/0281.jpeg)

**图 1.26** 测试渲染提示的效果

**示例 1.6** `RenderQualityTest.java`

点击此处查看代码图像

```java
80            e.printStackTrace();
81        }
82    }
83 }
```

```java
/**
 * 此组件生成一个用于显示渲染提示效果的绘图。
 */
class RenderQualityComponent extends JComponent
{
    private static final Dimension PREFERRED_SIZE = new Dimension(750, 150);

    private RenderingHints hints = new RenderingHints(null);

    private Image image;

    public RenderQualityComponent()
    {
        image = new ImageIcon(getClass().getResource("face.gif")).getImage();
    }

    public void paintComponent(Graphics g)
    {
        Graphics2D g2 = (Graphics2D) g;

        g2.setRenderingHints(hints);
        g2.draw(new Ellipse2D.Double(10, 10, 60, 50));

        g2.setFont(new Font("Serif", Font.ITALIC, 40));
        g2.drawString("Hello", 75, 50);

        g2.draw(new Rectangle2D.Double(200, 10, 40, 40));
        g2.draw(new Line2D.Double(201, 11, 239, 49));

        g2.drawImage(image, 250, 10, 100, 100, null);
    }

    /**
     * 设置提示并重绘。
     * @param h 渲染提示
     */
}
```



```java
public void setRenderingHints(RenderingHints h)
{
    hints = h;
    repaint();
}

public Dimension getPreferredSize() { return PREFERRED_SIZE; }

}
```

`java.awt.Graphics2D` 1.2

- `void setRenderingHint(RenderingHints.Key key, Object value)` 为此图形上下文设置一个渲染提示。
- `void setRenderingHints(Map m)` 设置所有存储在 `map` 中的键值对的渲染提示。

`java.awt.RenderingHints` 1.2

- `RenderingHints(Map<RenderingHints.Key, ?> m)` 构造一个存储渲染提示的渲染提示映射。如果 `m` 为 `null`，则提供一个默认映射实现。

### 11.10 图像的读取器和写入器

`javax.imageio` 包包含了对多种常见文件格式的“开箱即用”支持，以及一个允许第三方为其他格式添加读取器和写入器的框架。它支持 GIF、JPEG、PNG、BMP（Windows 位图）和 WBMP（无线位图）文件格式。

该库的基础非常直观。要加载图像，使用 `ImageIO` 类的静态 `read` 方法：

点击此处查看代码图像

```java
File f = . . .;
BufferedImage image = ImageIO.read(f);
```

`ImageIO` 类根据文件类型选择合适的读取器。为了这个目的，它可能会查询文件扩展名和文件开头的“魔数”。如果找不到合适的读取器，或者读取器无法解码文件内容，则 `read` 方法将返回 `null`。

将图像写入文件同样简单：

点击此处查看代码图像

```java
File f = . . .;
String format = . . .;
ImageIO.write(image, format, f);
```

这里的 `format` 是一个标识图像格式的字符串，例如 `"JPEG"` 或 `"PNG"`。`ImageIO` 类选择合适的写入器并保存文件。

#### 11.10.1 获取图像类型的读取器和写入器

对于超出 `ImageIO` 类静态 `read` 和 `write` 方法的更高级图像读取和写入操作，你首先需要获取合适的 `ImageReader` 和 `ImageWriter` 对象。`ImageIO` 类列出了匹配以下任一内容的读取器和写入器：

- 图像格式（例如 `"JPEG"`）
- 文件后缀名（例如 `"jpg"`）
- MIME 类型（例如 `"image/jpeg"`）

注意 MIME 是多用途邮件邮件扩展（Multipurpose Mail Extensions）标准。MIME 标准将常见数据格式定义为 `"image/jpeg"` 和 `"application/pdf"`。

例如，你可以通过以下方式获取读取 JPEG 文件的读取器：

点击此处查看代码图像

```java
ImageReader reader = null;
Iterator<ImageReader> iter = ImageIO.getImageReadersByName("JPEG");
if (iter.hasNext()) reader = iter.next();
```

`getImageReadersBySuffix` 和 `getImageReadersByIMEType` 方法列出了匹配文件扩展名或 MIME 类型的读取器。`ImageIO` 类可能会找到多个都能读取特定图像类型的读取器。在这种情况下，你必须从中选择一个，但并不清楚该如何决定哪一个是最好的。要了解更多关于读取器的信息，可以获取其服务提供接口：

点击此处查看代码图像

```java
ImageReaderSPI spi = reader.getOriginProvider();
```

然后你就可以获取厂商名称和版本号：

点击此处查看代码图像

```java
String vendor = spi.getVendor();
String version = spi.getVersion();
```

可能这些信息可以帮助你决定在菜单中显示哪一个。在 11.7 中，我们假设第一个读取器是足够的。为了这个目的，我们需要获取所有可用读取器的后缀名。使用静态 `ImageIO.getSuffixes` 方法来实现这一目的，以便在过滤器中使用：

点击此处查看代码图像

```java
String[] extensions = ImageIO.getSuffixes();
chooser.setFileFilter(new FileNameFilter("Image files", extensions));
```

对于保存文件，我们必须更费力。我们想要向用户展示所有支持的图像类型。遗憾的是，`getWriterFormatNames` 返回了一个相当奇怪的重复名称列表，例如：

```text
jpg, BMP, JPG, jpeg, wbmp, png, JPEG, WBMP, GIF
```

这不是人们想要在菜单中展示的内容。需要的是“首选”格式名称。我们为每个格式查找第一个写入器。然后询问它的格式名称，希望它会将最常用的格式列在前面。确实，对于 JPEG 写入器，这样做运行良好——它将 `"JPEG"` 列在其他选项之前。（另一方面，PNG 写入器会将小写的 `"png"` 列在大写的 `"PNG"` 之前。我们希望这种行为在未来得到解决。现在，一旦选择了一个名称，就从原始集合移除所有备用名称。）我们继续，直到处理所有格式名称。

#### 11.10.2 读取和写入包含多个图像的文件

某些文件——特别是 GIF 文件——包含多个图像。`ImageIO` 类的 `read` 方法读取单个图像。要读取多个图像，将输入源转换为 `ImageInputStream`。

点击此处查看代码图像

```java
InputStream in = . . .;
ImageInputStream imageIn = ImageIO.createImageInputStream(in);
```

然后，将图像输入流附加到读取器：

点击此处查看代码图像

```java
reader.setInput(imageIn, true);
```

第二个参数表示输入处于“仅限向前移动”模式。否则，将使用随机访问，通过在读取时缓冲流输入或使用随机文件访问来实现。随机访问对于某些操作是必须的。例如，要确定 GIF 文件中的图像数量，你需要读取整个文件。

这种考虑仅在您从流中读取、输入包含多幅图像，且图像格式的头文件中没有包含您请求的信息（如图像计数）时才重要。如果您从文件读取，只需简单使用：

```java
File f = . . .;
ImageInputStream imageIn = ImageIO.createImageInputStream(f);
reader.setInput(imageIn);
```

一旦你有了读取器，就可以通过调用以下方法读取输入中的图像：

```java
BufferedImage image = reader.read(index);
```

其中 `index` 是图像索引，从 `0` 开始。

如果输入处于“仅允许向前寻”模式，你需要继续读取图像，直到 `read` 方法抛出 `IndexOutOfBoundsException` 为止。否则，你可以调用 `getNumImages` 方法：

```java
int n = reader.getNumImages(true);
```

在这里，参数表示你允许搜索输入以确定图像数量。如果输入处于“仅允许向前寻”模式，该方法将抛出 `IllegalStateException`。或者，你可以将“允许搜索”参数设置为 `false`。这样，无法无法通过搜索的情况下确定图像数量，`getNumImages` 方法将返回 `-1`。在这种情况下，你必须切换到方案 B 并继续读取图像直到获取 `IndexOutOfBoundsException` 异常。

某些文件包含缩略图——用于预览的较小版本图像。你可以通过以下调用获取图像的缩略图数量：

```java
int count = reader.getNumThumbnails(index);
```

然后你可以获取特定索引的缩略图：

```java
BufferedImage thumbnail = reader.getThumbnail(index, thumbnailIndex);
```

有时你可能想在实际获取图像之前先获取图像尺寸——特别是当图像巨大或来自缓慢的网络连接时。使用以下调用：

```java
int width = reader.getWidth(index);
int height = reader.getHeight(index);
```

要写入一个包含多幅图像的文件，首先需要一个 `ImageWriter`。`ImageIO` 类可以列出能够写入特定图像格式的写入器：

```java
String format = . . .;
ImageWriter writer = null;
Iterator<ImageWriter> iter = ImageIO.getImageWritersByFormatName(format);
if (iter.hasNext()) writer = iter.next();
```

接下来，将输出流或文件转换为 `ImageOutputStream` 并将其附加到写入器上。例如：

```java
File f = . . .;
ImageOutputStream imageOut = ImageIO.createImageOutputStream(f);
writer.setOutput(imageOut);
```

你必须将每幅图像封装成 `IIOImage` 对象。你可以可选地提供缩略图列表和图像元数据（如压缩算法和颜色信息）。在示例中，我们两者都使用 `null`；更多信息请参见 API 文档。

```java
IIOImage iioImage = new IIOImage(images[i], null, null);
```

要写入**第一**幅图像，使用 `write` 方法：

```java
writer.write(new IIOImage(images[0], null, null));
```

对于后续图像，使用：

```java
if (writer.canInsertImage(i))
    writer.writeInsert(i, iioImage, null);
```

第三个参数可以包含一个 `ImageWriteParam` 对象，用于设置图像写入细节，如分块和压缩；使用 `null` 使用默认值。

并不是所有文件格式都能处理多幅图像。在这种情况下，当 `i > 0` 时，`canInsertImage` 方法返回 `false`，且仅保存一张图像。

`Listing 11.7` 中的程序允许按 Java 库提供的读取器和写入器的格式加载和保存文件。该程序显示多幅图像（参见 `Figure 11.27`），但没有显示缩略图。

![Image](img/00282.jpeg)

**图 11.27** 一幅动态 GIF 图像

**代码 11.7** `imageIO/ImageIOFrame.java`

```java
package imageIO;

import java.awt.image.*;
import java.io.*;
import java.util.*;
import javax.imageio.*;
import javax.imageio.stream.*;
import javax.swing.*;
import javax.swing.filechooser.*;

/**
 * 此框架显示加载的图像。菜单包含加载和保存文件的项。
 */
public class ImageIOFrame extends JFrame
{
    private static final int DEFAULT_WIDTH = 400;
    private static final int DEFAULT_HEIGHT = 400;
    private static Set<String> writerFormats = getWriterFormats();
    private BufferedImage[] images;

    public ImageIOFrame()
    {
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

        JMenu fileMenu = new JMenu("File");
        JMenuItem openItem = new JMenuItem("Open");
        openItem.addActionListener(event -> openFile());
        fileMenu.add(openItem);

        JMenu saveMenu = new JMenu("Save");
        fileMenu.add(saveMenu);

        Iterator<String> iter = writerFormats.iterator();
        while (iter.hasNext())
        {
            final String formatName = iter.next();
            JMenuItem formatItem = new JMenuItem(formatName);
            saveMenu.add(formatItem);
            formatItem.addActionListener(event -> saveFile(formatName));
        }

        JMenuItem exitItem = new JMenuItem("Exit");
        exitItem.addActionListener(event -> System.exit(0));
        fileMenu.add(exitItem);

        JMenuBar menuBar = new JMenuBar();
        menuBar.add(fileMenu);
        setJMenuBar(menuBar);
    }

    /**
     * 打开文件并加载图像。
     */
    public void openFile()
    {
        JFileChooser chooser = new JFileChooser();
        chooser.setCurrentDirectory(new File("."));

        String[] extensions = ImageIO.getReaderFileSuffixes();
        chooser.setFileFilter(new FileNameExtensionFilter("Image", extensions));

        int r = chooser.showDialog(this);
        if (r != JFileChooser.OK_OPTION) return;

        File f = chooser.getSelectedFile();
        Box box = Box.createVertical();

        try
        {
            String name = f.getName();
            String suffix = name.substring(name.lastIndexOf('.') + 1);
            Iterator<ImageReader> iter = ImageIO.getImageReadersBySuffix(suffix);
            ImageReader reader = iter.next();

            ImageInputStream imageIn = ImageIO.createImageInputStream(f);
            reader.setInput(imageIn);

            int count = reader.getNumImages(true);
            images = new BufferedImage[count];

            for (int i = 0; i < count; i++)
            {
                images[i] = reader.read(i);
                box.add(new JLabel(new ImageIcon(images[i])));
            }
        }
        catch (IOException e)
        {
            JOptionPane.showMessageDialog(this, e);
        }

        setContentPane(new JScrollPane(box));
        validate();
    }

    /**
     * 在文件中保存当前图像。
     */



```java
/**
 * @param formatName 文件格式
 */
public void saveFile(final String formatName) {
    if (images == null) {
        return;
    }
}
```

```java
Iterator<ImageWriter> iter =
    ImageIO.getImageWritersByFormatName(formatName);

ImageWriter writer = iter.next();
JFileChooser chooser = new JFileChooser();
chooser.setCurrentDirectory(new File("."));

String[] extensions = writer.getOriginatingProvider().getFileSuffixes();
chooser.setFileFilter(new FileNameExtensionFilter("Image files", extensions));

int r = chooser.showSaveDialog(this);
if (r != JFileChooser.APPROVE_OPTION) {
    return;
}

File f = chooser.getSelectedFile();

try {
    ImageOutputStream imageOut = ImageIO.createImageOutputStream(f);
    writer.setOutput(imageOut);
    writer.write(new IIOImage(images[0], null, null));

    for (int i = 1; i < images.length; i++) {
        IIOImage iioImage = new IIOImage(images[i], null, null);

        if (writer.canInsertImage(i)) {
            writer.writeInsert(i, iioImage, null);
        }
    }
} catch (IOException e) {
    JOptionPane.showMessageDialog(this, e);
}
```

```java
/**
 * 获取所有图像写入器的“首选”格式名称集合。首选格式名称是
 * 写入器指定的第一个格式名称。
 *
 * @return 格式名称集合
 */
public static Set<String> getWriterFormats() {
    Set<String> writerFormats = new TreeSet<>();
    Set<String> formatNames = new TreeSet<>(
        Arrays.asList(ImageIO.getWriterFormatNames()));

    while (formatNames.size() > 0) {
        String name = formatNames.iterator().next();
        Iterator<ImageWriter> iter =
            ImageIO.getImageWritersByFormatName(name);

        ImageWriter writer = iter.next();
        String[] names = writer.getOriginatingProvider().getFormatNames();
        String format = names[0];

        if (format.equals(format.toLowerCase())) {
            format = format.toUpperCase();
        }

        writerFormats.add(format);
        formatNames.removeAll(Arrays.asList(names));
    }

    return writerFormats;
}
```

### `javax.imageio.ImageIO`

- `static BufferedImage read(File input)`
- `static BufferedImage read(InputStream input)`
- `static BufferedImage read(URL input)`

从 `input` 读取图像。

- `static boolean write(RenderedImage image, String formatName, File output)`
- `static boolean write(RenderedImage image, String formatName, OutputStream output)`

将图像以给定的格式写入 `output`。如果没有找到合适的写入器，则返回 `false`。

- `static Iterator<ImageReader> getImageReadersByFormatName(String formatName)`
- `static Iterator<ImageReader> getImageReadersBySuffix(String fileSuffix)`
- `static Iterator<ImageReader> getImageReadersByMIMEType(String mimeType)`
- `static Iterator<ImageWriter> getImageWritersByFormatName(String formatName)`
- `static Iterator<ImageWriter> getImageWritersBySuffix(String fileSuffix)`
- `static Iterator<ImageWriter> getImageWritersByMIMEType(String mimeType)`

获取所有能够处理给定格式（例如 `"JPEG"``）、文件后缀（例如 `"jpg"`）或 MIME 类型（例如 `"image/jpeg"`）的读取器和写入器。

- `static String[] getReaderFormatNames()`
- `static String[] getReaderMIMETypes()`
- `static String[] getWriterFormatNames()`
- `static String[] getWriterMIMETypes()`
- `static String[] getReaderFileSuffixes()`
- `static String[] getWriterFileSuffixes()`

获取读取器和写入器支持的所有格式名称、MIME 类型名称和文件后缀。

- `static ImageInputStream createImageInputStream(Object input)`
- `static ImageOutputStream createImageOutputStream(Object output)`

从给定的对象创建图像输入或图像输出流。该对象可以是文件、流、`RandomAccessFile` 或其他存在服务提供者的对象。如果没有已注册的服务提供者可以处理该对象，则返回 `null`。

### `javax.imageio.ImageReader`

- `void setInput(Object input)`
- `void setInput(Object input, boolean seekForward)`

设置读取器的输入源。

- `BufferedImage read(int index)`

根据给定的图像索引（从 `0` 开始）读取图像。如果没有此类图像，则抛出 `IndexOutOfBoundsException`。

- `int getNumImages(boolean allowSearch)`

获取此读取器中的图像数量。如果 `allowSearch` 为 `false` 且无法通过向前读取确定图像数量，则返回 `-1`。如果 `allowSearch` 为 `true` 且读取器处于“仅向前查找”模式，则抛出 `IllegalStateException`。

- `int getNumThumbnails(int index)`

获取给定 `index` 图像的缩略图数量。

- `BufferedImage readThumbnail(int index, int thumbnailIndex)`

获取给定 `index` 图像索引为 `thumbnailIndex` 的缩略图。

- `int getWidth(int index)`
- `int getHeight(int index)`

获取图像的宽度和高度。如果没有此类图像，则抛出 `IndexOutOfBoundsException`。

- `ImageReaderSpi getOriginatingProvider()`

获取构建此读取器的服务提供者。

### `javax.imageio.spi.IIOServiceProvider`

- `String getVendorName()`
- `String getVersion()`

获取此服务提供者的供应商和版本。

### `javax.imageio.spi.ImageReaderWriterSpi`

- `String[] getFormatNames()`
- `String[] getFileSuffixes()`
- `String[] getMIMETypes()`

获取此服务提供器创建的读取器或写入器支持的格式名称、文件后缀和 MIME 类型。

### `javax.imageio.ImageWriter`

- `void setOutput(Object output)`

设置此写入器的输出目标。

- `void write(IIOImage image)`
- `void write(RenderedImage image)`

向输出写入单幅图像。

- `void writeInsert(int index, IIOImage image, ImageWriteParam param)`

向多图像写入图像。

- `boolean canInsertImage(int index)`

如果可以在指定的索引插入图像，则返回 `true`。

- `ImageWriterSpi getOriginatingProvider()`

获取构建此写入器的服务提供者。

### `javax.imageio.IIOImage`

- `IIOImage(RenderedImage image, List thumbnails, IIOMetadata metadata)`

从图像、可选缩略图和元数据构造 `IIOImage`。

```java
image = new BufferedImage(
    width,
    height,
    BufferedImage.TYPE_INT_ARGB
);
```

现在，调用 `getRaster()` 方法获取一个类型为 `WritableRaster` 的对象。你将使用此对象来访问并修改图像的像素。

点击此处查看代码：

```java
WritableRaster raster = image.getRaster();
```

`setPixel()` 方法允许你设置单个像素。这里的复杂度在于，你不能简单地将像素设置为 `Color` 值。你必须知道缓冲图像（buffered image）是如何指定颜色值的。这取决于图像的类型。如果你的图像类型为 `TYPE_INT_ARGB`，那么每个像素由四个值描述——红、绿、蓝和 Alpha，每个值都介于 `0` 到 `255` 之间。你必须在一个包含四个整数的数组中提供它们：

点击此处查看代码：

```java
int[] black = { 0, 0, 0, 255 };
raster.setPixel(i, j, black);
```

在 Java 2D API 的术语中，这些值被称为像素的采样值（sample values）。

---

![图像](img/00004.jpeg) 注意

还有接受 `float[]` 和 `double[]` 类型数组参数的 `setPixel()` 方法。然而，你需要放入这些数组中的值不是介于 `0.0` 和 `1.0` 之间的归一化颜色值。

点击此处查看代码：

```java
float[] red = { 1.0F, 0.0F, 0.0F, 1.0F };
raster.setPixel(i, j, red); // 错误
```

无论数组类型是什么，你都必须提供 `0` 到 `255` 之间的值。

---

你可以使用 `setPixels()` 方法批量提供像素。指定要设置的矩形的起始像素位置、宽度和高度。然后，提供一个包含所有像素采样值的数组。例如，如果你的缓冲图像类型为 `TYPE_INT_ARGB`，提供第一个像素的红、绿、蓝、Alpha 值，然后提供第二个像素的红、绿、蓝、Alpha 值，依此类推。

点击此处查看代码：

```java
int[] pixels = new int[4 * width * height];
pixels[0] = . . . // 第一个像素的红色值
pixels[1] = . . . // 第一个像素的绿色值
pixels[2] = . . . // 第一个像素的蓝色值
pixels[3] = . . . // 第一个像素的 Alpha 值
. . .
raster.setPixels(x, y, width, height, pixels);
```

相反，要读取像素，使用 `getPixel()` 方法。提供一个包含四个整数的数组来存储采样值。

点击此处查看代码：

```java
int[] sample = new int[4];
raster.getPixel(x, y, sample);
Color c = new Color(sample[0], sample[1], sample[2], sample[3]);
```

你可以使用 `getPixels()` 方法读取多个像素。

点击此处查看代码：

```java
raster.getPixels(x, y, width, height, samples);
```

如果你使用 `TYPE_INT_ARGB` 以外的图像类型，并且知道该类型如何表示像素值，你仍然可以使用 `getPixel()`/`setPixel()` 方法。然而，你必须知道特定图像类型中采样值的编码。

如果你需要处理具有任意、未知图像类型的图像，那么你必须多花努力。每种图像类型都有一个颜色模型（color model），可以在采样值数组和标准 RGB 颜色模型之间进行转换。

---

![图像](img/00002.jpeg) 注意

RGB 颜色模型并没有像你想中那样标准。颜色值的准确外观取决于成像设备的特性。数字相机、扫描仪、显示器和 LCD 显示器都有其独特之处。因此，相同的 RGB 值在不同设备上看起来可能完全不同。国际色彩联盟（`www.color.org`）建议所有颜色数据都应带有一个 ICC 配置文件，它指定颜色如何映射到标准形式，如 1931 CIE XYZ 颜色规范。该规范由国际委员会（Commission Internationale de l’Eclairage，或 `CIE`（`www.cie.co.at`））设计，这是一个负责为所有照明和色彩事务提供技术指导的国际组织。该规范是一种标准方法，将人眼可以感知的任何颜色表示为称为 X、Y、Z 的三元坐标组。（例如，请参见 James D. Foley、Andries van Dam、Steven K. Feiner 等著的 *Computer Graphics: Principles and Practice, Second Edition in C* 第 13 章，获取更多关于 1931 CIE XYZ 规范的信息。）

然而，ICC 配置文件是复杂的。一种更简单的标准 sRGB（`www.w3.org`）指定了颜色如何映射到标准形式，如 1931 CIE XYZ 颜色规范。该规范由国际委员会（Commission Internationale de l’Eclairage，或 `CIE`（`www.cie.co.at`））设计，这是一个负责为所有照明和色彩事务提供技术指导的国际组织。该规范是一种标准方法，将人眼可以感知的任何颜色表示为称为 X、Y、Z 的三元坐标组。

`getColorModel()` 方法返回一个包含颜色值的 `Object`。颜色模型可以将该对象转换为 RGB 值。`Color` 类的 `getRGB()` 方法产生一个带有 Alpha、绿色和蓝色值的 `int` 值。你可以使用 `Color(int argb, boolean hasAlpha)` 构造函数从该整数构造出一个 `Color` 值：

要将像素设置为特定颜色，请反转这些步骤。`Color` 类的 `getRGB()` 方法产生一个带有 Alpha、绿色和蓝色值的 `int` 值。将该值传递给 `ColorModel` 的 `getDataElements()` 方法。返回值是一个包含颜色值的 `Object`。将该对象传递给 `WritableRaster` 的 `setDataElements()` 方法。

列表 11.8 显示了代码。在这个程序中，我们演示了如何使用 `ColorModel` 类将 `Color` 值转换为像素数据。该过程独立于图像类型。只是为了好玩，将缓冲图像的颜色类型更改为 `TYPE_BYTE_GRAY`。你不需要更改任何代码——图像的颜色模型会自动处理从颜色到样本值的转换。

**列表 11.8** `rasterImage/RasterImageFrame.java`

---

点击此处查看代码图像

---



```java
package rasterImage;

import java.awt.*;
import java.awt.image.*;
import javax.swing.*;

/**
 * 此框架显示了一幅包含曼德博罗集合的图像。
 */
public class RasterImageFrame extends JFrame
{
    private static final double XMIN = -2;
    private static final double XMAX = 2;
    private static final double YMIN = -2;
    private static final double YMAX = 2;
    private static final int MAX_ITERATIONS = 16;
    private static final int IMAGE_WIDTH = 400;
    private static final int IMAGE_HEIGHT = 400;

    public RasterImageFrame()
    {
        BufferedImage image = makeMandelbrot(IMAGE_WIDTH, IMAGE_HEIGHT);
        add(new JLabel(new ImageIcon(image)));
        pack();
    }

    /**
     * 生成曼德博罗图像。
     * @param width 宽度
     * @param height 高
     * @return 图像
     */
    public BufferedImage makeMandelbrot(int width, int height)
    {
        BufferedImage image = new BufferedImage(width, height, BufferedImage.TYPE_INT_ARGB);
        WritableRaster raster = image.getRaster();
        ColorModel model = image.getColorModel();

        Color fractalColor = Color.red;
        int argb = fractalColor.getRGB();
        Object colorData = model.getDataElements(argb, null);

        for (int i = 0; i < width; i++)
            for (int j = 0; j < height; j++)
            {
                double a = XMIN + i * (XMAX - XMIN) / width;
                double b = YMIN + j * (YMAX - YMIN) / height;
                if (!escapesToInfinity(a, b)) raster.setDataElements(i, j, colorData);
            }
        return image;
    }

    private boolean escapesToInfinity(double a, double b)
    {
        double x = 0.0;
        double y = 0.0;
        int iterations = 0;
        while (x <= 2 && y <= 2 && iterations < MAX_ITERATIONS)
        {
            double xnew = x * x - y * y + a;
            double ynew = 2 * x * y + b;
            x = xnew;
            y = ynew;
            iterations++;
        }
        return x > 2 || y > 2;
    }
}
```

`java.awt.image.BufferedImage`

- `BufferedImage(int width, int height, int imageType)`构建一个缓冲图像。
- `ColorModel()`返回此缓冲图像的颜色模型。
- `WritableRaster()`获取用于访问和修改此缓冲图像像素的栅格器。
- `Object getDataElements(int x, int y, Object data)`返回栅格点的样本数据，该数组的元素类型和长度取决于颜色模型。如果`data`不为`null`，则假设它是适合存储样本数据的数组并对其进行填充。如果`data`为`null`，则分配一个新数组。
- `int[] getPixel(int x, int y, int[] sampleValues)`
- `float[] getPixel(int x, int y, int[] sampleValues)`
- `double[] getPixel(int x, int y, int[] sampleValues)`
- `int[] getPixels(int x, int y, int width, int height, int[] sampleValues)`
- `float[] getPixels(int x, int y, int width, int height, int[] sampleValues)`
- `double[] getPixels(int x, int y, int width, int height, int[] sampleValues)`返回栅格点或栅格点矩形的样本值，其数组长度取决于颜色模型。如果`sampleValues`不为`null`，则假设其长度足够样本值并对其进行填充。如果`sampleValues`为`null`，则分配一个新数组。

`java.awt.image.WritableRaster`

- `void setDataElements(int x, int y, Object data)`设置栅格点的样本数据。`data`是一个填充了像素样本数据的数组。其元素类型和长度取决于颜色模型。
- `void setPixel(int x, int y, int[] sampleValues)`
- `void setPixel(int x, int y, float[] sampleValues)`
- `void setPixel(int x, int y, double[] sampleValues)`
- `void setPixels(int x, int y, int width, int height, int[] sampleValues)`
- `void setPixels(int x, int y, int width, int height, float[] sampleValues)`
- `void setPixels(int x, int y, int width, int height, double[] sampleValues)`设置栅格点或栅格点矩形的样本值。

`java.awt.image.ColorModel`

- `int getRGB(Object data)`返回与`data`数组对应的 ARGB 值。其元素类型和长度取决于颜色模型。
- `Object getDataElements(int argb, Object data)`返回样本数据。如果`data`不为`null`，则假设它是适合存储样本数据的数组并对其进行填充。如果`data`为`null`，则分配一个新数组。

`java.awt.Color`

- `Color(int argb, boolean hasAlpha)`如果`hasAlpha`为`true`则创建一个指定的 ARGB；如果`hasAlpha`为`false`则创建指定的 RGB 值。
- `int getRGB()`返回此颜色的 ARGB 值。

## 11.11.2 过滤图像

在前面的节中，你学习了如何从零构建图像。然而，通常你访问图像数据是为了不同的原因：你已经有一幅图像，并想以某种方式对其改进。

当然，你可以使用上一节中看到的`getPixel/getDataElements`方法来读取图像数据、进行处理并写回。但幸运的是，Java 2D API 提供了许多过滤器，可以为你完成常见的图像处理操作。

这些图像操作都实现了`BufferedImageOp`接口。在构造操作后，你只需调用`filter`方法将一个图像转换为另一个。

```java
BufferedImageOp op = ...;
BufferedImage filteredImage = new BufferedImage(image.getWidth(), image.getHeight(), image.getType());
op.filter(image, filteredImage);
```

某些操作可以原地转换图像（`op.filter(image, image)`），但大多数不能。

五个类实现了`BufferedImageOp`接口：

- `AffineTransformOp`
- `RescaleOp`
- `LookupOp`
- `ColorConvertOp`
- `ConvolveOp`

`AffineTransformOp`对像素执行仿射变换。例如，以下是如何绕中心旋转图像：

```java
AffineTransform transform = AffineTransform.getRotateInstance(Math.toRadians(angle), image.getWidth() / 2, image.getHeight() / 2);
AffineTransformOp op = new AffineTransformOp(transform, interpolation);
op.filter(image, filteredImage);
```

`AffineTransformOp`构造函数需要一个仿射变换和一个`interpolation`插值策略。如果源像素被变换到目标像素之间的位置，则需要插值来确定目标图像中的像素。例如，如果你旋转了源像素，它们通常不会正好落在目标像素上。这里有两种插值策略：`AffineTransformOp.TYPE_BILINEAR`和`AffineTransformOp.TYPE_NEAREST_NEIGHBOR`。双线性插值耗时稍长，但效果更好。

列表 11.9 中的程序允许你将图像旋转 5 度（请参见图 11.29）。

![Image](img/00287.jpeg)

**图 11.29** 旋转后的图像

`RescaleOp`执行缩放操作：

`x[new] = a · x + b`

用于图像中的每个颜色分量。（Alpha 分量不受影响。）使用`a > 1`进行缩放的效果是亮图像。通过指定缩放参数和可选渲染提示来构造`RescaleOp`。在列表 11.9 中，我们使用了：

```java
float a = 1.1f;
float b = 20.0f;
RescaleOp op = new RescaleOp(a, b, null);
```

你也可以为每个颜色分量提供单独的缩放值——参见 API 说明。

`LookupOp`操作允许你指定样本值的任意映射。提供一个指定每个值应如何映射的表。在示例程序中，我们计算所有颜色的反色值，将颜色`c`变为`255 – c`。

`LookupOp`构造函数需要一个`LookupTable`类型的对象和一个可选提示的映射。`LookupTable`类是抽象类，有两个具体的子类：`ByteLookupTable`和`ShortLookupTable`。由于 RGB 颜色值是字节型的，因此`ByteLookupTable`应该足够了。但是，由于`http://bugs.sun.com/bugdatabase/view_bug.do?bug_id=6183251`中描述的错误，我们将使用`ShortLookupTable`。以下是示例程序构造`LookupOp`的方式：

```java
short negative[] = new short[256];
for (int i = 0; i < 256; i++) negative[i] = (short) (255 - i);
ShortLookupTable table = new ShortLookupTable(0, negative);
LookupOp op = new LookupOp(table, null);
```

查找分别应用于每个颜色分量，但不会应用于 alpha 分量。你也可以为每个颜色分量提供不同的查找表——参见 API 说明。

> **注意**
>
> 你不能对使用索引颜色模型的图像应用`LookupOp`。（在这些图像中，每个样本值都是颜色调色板的偏移量。）

`ColorConvertOp`用于颜色空间转换。我们在这里不讨论它。

变换中最强大的是`ConvolveOp`，它执行数学上的`convolution`（卷积）。我们不会深入探讨数学细节，但基本思想非常简单。例如，考虑`blur filter`（模糊滤波器，参见图 11.30）。

![Image](img/00288.jpeg)

**图 11.30** 模糊图像

模糊通过将每个像素替换为该像素及其八个邻居的`average`值来实现。直观上，这种操作会让图片变模糊。从数学上讲，平均值可以表示为具有以下`kernel`的卷积操作：

![Image](img/00289.jpeg)

卷积核是一个矩阵，它告诉应该对邻居值应用什么权重。上面的核产生一个模糊图像。不同的核执行`edge detection`（边缘检测），定位颜色变化的区域：

![Image](img/00290.jpeg)

边缘检测是分析摄影图像的重要技术（参见图 11.31）。

![Image](img/00291.jpeg)

**图 11.31** 边缘检测与反色

要构造卷积操作，首先设置一个核值数组并构造一个`Kernel`对象。然后，从核构造一个`ConvolveOp`对象并使用它进行滤波。

```java
float[] elements =
    {
      0.0f, -1.0f, 0.0f,
      -1.0f, 4.f, -1.0f,
      0.0f, -1.0f, 0.0f
    };
Kernel kernel = new Kernel(3, 3, elements);
ConvolveOp op = new ConvolveOp(kernel);
op.filter(image, filteredImage);
```

列表 11.9 中的程序允许用户加载 GIF 或 JPEG 图像并执行图像处理。由于 Java 提供的操作，程序非常简单。

**列表 11.9** `imageProcessing/ImageFrame.java`



```java
package imageProcessing;

import java.awt.*;
import java.awt.geom.*;
import java.awt.image.*;
import java.imageio.*;
import java.io.*;
import javax.swing.*;
import javax.swing.filechooser.*;

/**
 * 此帧有一个菜单来加载图像并指定变换，显示结果图像。
 */
public class ImageFrame extends JFrame
{
    private static int DEFAULT_WIDTH = 400;
    private static int DEFAULT_HEIGHT = 400;

    private BufferedImage image;

    public ImageFrame()
    {
        setTitle("ImageTest");
        setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);
        add(new JComponent()
        {
            public void paintComponent(Graphics g)
            {
                if (image != null) g.drawImage(image, 0, null);
            }
        });
        JMenu fileMenu = new JMenu("File");
        JMenuItem openItem = new JMenuItem("Open");
        openItem.addActionListener(event -> openFile());
        fileMenu.add(openItem);
        JMenuItem exitItem = new JMenuItem("Exit");
        exitItem.addActionListener(event -> System.exit(0));
        fileMenu.add(exitItem);
        JMenu editMenu = new JMenu("Edit");
        JMenuItem blurItem = new JMenuItem("Blur");
        blurItem.addActionListener(event ->
        {
            float weight = 1.0f / 9.0f;
            float[] elements = new float[9];
            for (int i = 0; i < 9; i++)
                elements[i] = weight;
            convolve(elements);
        });
        editMenu.add(blurItem);
        JMenuItem sharpenItem = new JMenuItem("Sharpen");
        sharpenItem.addActionListener(event ->
        {
            float[] elements = { 0.0f, -1.0f, 0.0f, -1.0f, 5.f, -1.0f, 0.0f, -1.0f, 0.0f };
            convolve(elements);
        });
        editMenu.add(sharpenItem);
        JMenuItem brightenItem = new JMenuItem("Brighten");
        brightenItem.addActionListener(event ->
        {
            float a = 1.1f;
            float b = 20.0f;
            RescaleOp op = new RescaleOp(a, b, null);
            filter(op);
        });
        editMenu.add(brightenItem);
        JMenuItem edgeDetectItem = new JMenuItem("Edge detect");
        edgeDetectItem.addActionListener(event ->
        {
            float[] elements = { 0.0f, -1.0f, 0.0f, -1.0f, 4.f, -1.0f, 0.0f, -1.0f, 0.0f };
            convolve(elements);
        });
        editMenu.add(edgeDetectItem);
        JMenuBar menuBar = new JMenuBar();
        menubar.add(fileMenu);
        menubar.add(editMenu);
        setJMenuBar(menubar);
    }

    private void openFile()
    {
        FileChooser chooser = new JFileChooser();
        if (chooser.showOpenDialog(this) == JFileChooser.APPROVE_OPTION)
        {
            try {
                image = ImageIO.read(chooser.getSelectedFile());
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
        repaint();
    }

    private void filter(RescaleOp op)
    {
        if (image != null)
        {
            BufferedImage filteredImage = new BufferedImage(image.getWidth(), image.getHeight(), BufferedImage.TYPE_INT_RGB);
            op.filter(image, filteredImage, null);
            image = filteredImage;
        }
        repaint();
    }
}
    }

    private void convolve(float[] elements)
    {
        if (image != null)
        {
            BufferedImage filteredImage = new BufferedImage(image.getWidth(), image.getHeight(), BufferedImage.TYPE_INT_RGB);
            Kernel kernel = new Kernel(3, 3, elements);
            ConvolveOp op = new ConvolveOp(kernel);
            op.filter(image, filteredImage, null);
            image = filteredImage;
        }
        repaint();
    }
}
    }
}
```

## 11.12 打印

原始的 JDK 完全不支持打印功能。当时无法打印 applet，如果你想从应用程序中打印内容，必须获取第三方库。JDK 1.1 引入了非常轻级的打印支持，只要你对打印质量不是特别挑剔，它就足以生成简单的打印输出。1.1 的打印模型设计目的是允许浏览器厂商打印 applet 在网页上上显示的界面（尽管如此，浏览器厂商并未采纳这一做法）。

Java SE 1.2 引入了健壮打印模型的开端，该模型与 2D 图形完全集成。Java SE 1.4 增加了重要的增强，例如打印机功能发现以及用于服务器端打印管理的流式打印作业（streaming print jobs）。等一下，让我重新检查一下提供的文本。

### 11.12.1 图形打印

在本节中，我们将处理可能最常见的打印情况：打印一个 2D 图形。当然，图形可以包含各种字体的文本，甚至完全由文本组成。

要生成打印输出，你必须处理以下两个任务：

- 提供一个实现了 `Printable` 接口的对象
- 启动打印作业

`Printable` 接口有一个单元方法：

点击此处查看代码图片

`int print(Graphics g, PageFormat format, int page)`

每当打印引擎需要对页面进行格式化时，就会调用该方法。你的代码将要打印的文本和图像绘制到图形上下文中。页面格式告知你纸张大小和打印边距。页码告诉你要渲染哪一页。

要启动打印作业，请使用 `PrinterJob` 类。首先，调用静态方法 `getPrinterJob` 获取打印作业对象。然后设置你想打印的 `Printable` 对象。

点击此处查看代码图片

```java
Printable canvas = . . .;
PrinterJob job = PrinterJob.getPrinterJob();
job.setPrintable(canvas);
```

```java
for (int i = 0; i < 256; i++) {
    negative[i] = (short) (255 - i);
}
ShortLookupTable table = new ShortLookupTable(0, negative);
LookupOp op = new LookupOp(table, null);
filter(op);
});
editMenu.add(negativeItem);

JMenuItem rotateItem = new JMenuItem("Rotate");
rotateItem.addActionListener(event -> {
    if (image == null) return;
    AffineTransform transform = AffineTransform.getRotateInstance(Math.toRadians(5),
        image.getWidth() / 2, image.getHeight() / 2);
    AffineTransformOp op = new AffineTransformOp(transform,
        AffineTransformOp.TYPE_BICUBIC);
    filter(op);
});
editMenu.add(rotateItem);

JMenuBar menuBar = new JMenuBar();
menuBar.add(fileMenu);
menuBar.add(editMenu);
setJMenuBar(menuBar);
}

/**
 * 打开文件并加载图像。
 */
public void openFile() {
    JFileChooser chooser = new JFileChooser(".");
    chooser.setCurrentDirectory(new File(getClass().getPackage().getName()));
    String[] extensions = ImageIO.getReaderFileSuffixes();
    chooser.setFileFilter(new FileNameExtensionFilter("Image files", extensions));
    int r = chooser.showOpenDialog(this);
    if (r != JFileChooser.APPROVE_OPTION) return;

    try {
        Image img = ImageIO.read(chooser.getSelectedFile());
        image = new BufferedImage(img.getWidth(null), img.getHeight(null),
            BufferedImage.TYPE_INT_RGB);
        image.getGraphics().drawImage(img, 0, 0, null);
    } catch (IOException e) {
        JOptionPane.showMessageDialog(this, e);
    }
    repaint();
}

/**
 * 应用过滤器并重绘。
 * @param op 要应用的的图像操作
 */
private void filter(BufferedImageOp op) {
    if (image == null) return;
    image = op.filter(image, null);
    repaint();
}

/**
 * 应用卷积并重绘。
 * @param elements 卷积核（一个包含 9 个矩阵元素的数组）
 */
private void convolve(float[] elements) {
    Kernel kernel = new Kernel(3, 3, elements);
    ConvolveOp op = new ConvolveOp(kernel);
    filter(op);
}
```

### `java.awt.image.BufferedImageOp`

`BufferedImage filter(BufferedImage source, BufferedImage dest)`

将图像操作应用到源图像并将结果存储在目标图像中。如果 `dest` 为 `null`，则创建一个新的目标图像。返回该目标图像。

### `java.awt.image.AffineTransformOp`

`AffineTransformOp(AffineTransform t, int interpolationType)`

构造一个仿变换操作符。插值类型为 `TYPE_BILINEAR`、`TYPE_BICUBIC` 或 `TYPE_NEAREST_NEIGHBOR` 之一。

### `java.awt.image.RescaleOp`

`RescaleOp(float a, float b, RenderingHints hints)`

`RescaleOp(float[] as, float[] bs, RenderingHints hints)`

构造一个缩放操作符，执行缩放操作 `x[new] = a · x + b`。使用第一个构造函数时，所有颜色分量（Alpha 通道除外）使用相同的系数缩放。使用第二个构造函数时，你可以提供每个颜色分量的值（这种情况下 Alpha 通道不受影响），或者提供 Alpha 和颜色分量的值。

### `java.awt.image.LookupOp`

`LookupOp(LookupTable table, RenderingHints hints)`

为指定的查找表构造一个查找操作符。

### `java.awt.image.ByteLookupTable`

`ByteLookupTable(int offset, byte[] data)`

`ByteLookupTable(int offset, byte[][] data)`

构造用于转换 `byte` 值的查找表。在查找之前从输入中减去偏移量。第一个构造函数中的值应用于所有颜色分量，但不包括 Alpha 通道。使用第二个构造函数时，你可以提供每个颜色分量的值（这种情况下 Alpha 通道不受影响），或者提供 Alpha 和颜色分量的值。

### `java.awt.image.ShortLookupTable`

`ShortLookupTable(int offset, short[] data)`

`ShortLookupTable(int offset, short[][] data)`

构造用于转换 `short` 值的查找表。在查找之前从输入中减去偏移量。

`PrintJob` 类处理 JDK 1.1 风格的打印。该类已经过时。请勿将其与 `PrinterJob` 类混淆。

***

在开始打印任务之前，您应该调用 `printDialog` 方法来显示打印对话框（参见图 11.32）。该对话框让用户有机会选择选择要使用的打印机（在有多个打印机的情况下）、需要打印的页范围以及各种打印机设置。

![Image](img/00292.jpeg)

**图 11.32** 跨平台打印对话框

在实现 `PrintRequestAttributeSet` 接口的类对象中收集打印设置，例如 `HashPrintRequestAttributeSet` 类。

点击此处查看代码图片

```java
HashPrintRequestAttributeSet attributes = new HashPrintRequestAttributeSet();
```




添加属性设置并将`attributes`对象传递给`printDialog`方法。

如果用户点击了 OK，`printDialog`方法返回`true`；如果用户取消了对话框，则返回`false`。如果用户接受了，调用`PrinterJob`类的`print`方法开始打印过程。`print`方法可能会抛出`PrinterException`。以下是打印代码的概要：

点击此处查看代码图片

```java
if (job.printDialog(attributes))
{
    try
    {
        job.print(attributes);
    }
    catch (PrinterException exception)
    {
        . . .
    }
}
```

---

![Image](img/00002.jpeg) 注意

在 JDK 1.4 之前，打印系统使用主平台的原生打印和页面设置对话框。要显示原生打印对话框，请不带参数地调用`printDialog`方法。（没有办法在属性集中收集用户设置。）

---

在打印期间，`PrinterJob`类的`print`方法会反复调用与任务相关的`Printable`对象的`print`方法。

由于任务不知道您想要打印多少页，它只是简单地不断调用`print`方法。只要`print`方法返回`Printable.PAGE_EXISTS`值，打印任务就会继续生成页面。当`print`方法返回`Printable.NO_SUCH_PAGE`时，打印任务停止。

---

![Image](img/00004.jpeg) 注意

打印任务传递给`print`方法的页码从页 0 开始。

---

因此，在打印完成之前，打印任务没有准确的页数。由于这个原因，打印对话框无法显示正确的页范围——相反，它显示“页 1 到 1”。您将在下一节中看到如何通过向打印任务提供一个`Book`对象来避免这一缺陷。

在打印过程中，打印任务反复调用`Printable`对象的`print`方法。打印任务允许对同一页进行多次调用。因此，您不应该在`print`方法内部计算页数，而应该始终依赖页码参数。打印任务可能对同一页反复调用`print`方法有一个充分的理由。某些打印机（尤其是针式打印机和喷墨打印机）使用带状打印（banding）。它们一次打印一个带，推进纸，然后打印下一个带。即使对于一次打印整页的激光打印机，打印任务也可能使用带状打印——这为打印任务提供了一种缓存文件大小的方法。

如果打印任务需要`Printable`对象打印一个带，它会将图形上下文的裁剪区域设置为请求的带，并调用`print`方法。它的绘制操作将根据带矩形进行裁剪，只有显示在带中的绘制元素会被渲染。您的`print`方法不需要感知该过程，但有一个例外：它不应该干扰裁剪区域。

---

![Image](img/00004.jpeg) 注意

您的`print`方法获得的`Graphics`对象也对页边距进行了裁剪。如果您替换了裁剪区域，则可以在边距之外绘图。特别是在打印机图形上下文中，必须尊重裁剪区域。调用`clip`而不是`setClip`来进一步限制裁剪区域。如果您必须移除裁剪区域，请确保在`print`方法的开头调用`getClip`并恢复该裁剪区域。

---

`print`方法的`PageFormat`参数包含有关打印页的信息。`getWidth`和`getHeight`方法返回以点（points）为单位的纸张尺寸。

一个点是 1/72 英寸。（1 英寸等于 25.4 毫米）。例如，A4 纸约为 595 × 842 点，美国信号信纸为 612 × 792 点。

点是美国打印行业中常用的测量单位。令世界其他地区困扰的是，打印包使用了点单位。这样做有两个目的：纸张尺寸和页边距是用点测量的，且点是所有打印图形上下文的默认单位。您可以在本节末尾的示例程序中验证这一点。该程序打印了两行间距为 72 个单位的文本。运行示例程序，测量基线之间的距离；它们恰好是 1 英寸寸或 25.4 毫米。

`PageFormat`类的`getWidth`和`getHeight`方法提供完整的纸张尺寸。并不是纸张都是可打印的。用户通常会选择边距，即使他们不选择，打印机边缘也会有一个微小的不可打印区域。`getImageableWidth`和`getImageableHeight`方法告诉您可以填充的区域尺寸。然而，边距并不一定对称，因此您必须知道可打印区域的左上角（参见图 11.33），这可以通过`getImageableX`和`getImageableY`方法获得。

![Image](img/00293.jpeg)

**图 11.33** 页面格式

---

![Image](img/00003.jpeg) 提示

在`print`方法中接收到的图形上下文已被页边距裁剪，但坐标系的原点仍然是纸的左上角。将坐标系移动到可打印区域的左上角是有意义的。只需在`print`方法开始时使用：

```java
g.translate(pageFormat.getImageableX(), pageFormat.getImageableY());
```

---

如果您希望用户在不设置其他属性的情况下选择页边距或切换方向，请调用`PrinterJob`类的`pageDialog`方法：

```java
PageFormat format = job.pageDialog(attributes);
```

---

![Image](img/00002.jpeg) 注意

打印对话框的一个选项卡包含页面设置对话框（参见图 11.34）。您可能仍然想在打印前给用户设置页面格式的机会，特别是当您的程序对要打印的页面提供见即所得的显示时。`pageDialog`方法返回带有用户设置的`PageFormat`对象。

---

![Image](img/00294.jpeg)

**图 11.34** 跨平台页面设置

列表 11.10 和 11.11 中的程序展示了如何在屏幕和打印页面上渲染相同的形状。`JPanel`的子类实现了`Printable`接口。`paintComponent`和`print`方法都调用同一个方法来执行实际绘制。

点击此处查看代码图片

```java
class PrintPanel extends JPanel implements Printable
{
    public void paintComponent(Graphics g)
    {
        super.paintComponent(g);
        Graphics2D g2 = (Graphics2D) g;
        drawPage(g2);
    }
}
```

```java
public int print(Graphics g, PageFormat pf, int page)
    throws PrinterException
{
    if (page >= 1) return Printable.NO_SUCH_PAGE;
    Graphics2D g2 = (Graphics2D) g;
    g2.translate(pf.getImageableX(), pf.getImageableY());
    drawPage(g2);
    return Printable.PAGE_EXISTS;
}

public void drawPage(Graphics2D g2)
{
    // shared drawing code goes here
    . . .
}

. . .
}
```

此示例显示并打印了图 11.20 中在第 805 页上所示的图像——即“Hello, World”消息的轮廓，该轮廓被用线条图案的裁剪区域。

点击`Print`按钮开始打印，或点击`Page setup`按钮打开页面设置对话框。代码列表 11.10 显示了代码。

---

![Image](img/00002.jpeg) 注意

要显示原生页面设置对话框，请向`pageDialog`方法传递默认的`PageFormat`对象。该方法会克隆该对象，根据对话框中的用户选择对其进行修改，并返回克隆的对象。

点击此处查看代码图像

```java
PageFormat defaultFormat = printJob.defaultPage();

PageFormat selectedFormat = printJob.pageDialog(defaultFormat);
```

---

**代码列表 11.10** `print/PrintTestFrame.java`

点击此处查看代码图像

```java
1   package print;

2

3   import java.awt.*;

4   import java.awt.print.*;

5

6   import javax.print.attribute.*;

7   import javax.swing.*;

8

9   /**

10     * 此框架显示了一个带有 2D 图形的面板，以及用于打印图形和设置

11     * 页面格式的按钮。

12     */

13   public class PrintTestFrame extends JFrame

14   {

15      private PrintComponent canvas;

16      private PrintRequestAttributeSet attributes;

17

18      public PrintTestFrame()

19      {

20          canvas = new PrintComponent();

21          add(canvas, BorderLayout.CENTER);

22

23          attributes = new HashPrintRequestAttributeSet();

24

25          JPanel buttonPanel = new JPanel();

26          JButton printButton = new JButton("Print");

27          buttonPanel.add(printButton);

28          printButton.addActionListener(event ->

29              {

30                try

31                {

32                  PrinterJob job = PrinterJob.getPrinterJob();

33                  job.setPrintable(canvas);

34                  if (job.printDialog(attributes)) job.print(attributes);

35                }

36                catch (PrinterException ex)

37                {

38                  JOptionPane.showMessageDialog(PrintTestFrame.this, ex);

39                }

40              });

41

42          JButton pageSetup = new JButton("Page setup");

43          buttonPanel.add(pageSetup);

44          pageSetup.addActionListener(event ->

45              {

46                PrinterJob job = PrinterJob.getPrinterJob();

47                job.pageDialog(attributes);

48              });

49          add(buttonPanel, BorderLayout.NORTH);

50          pack();

51      }

52  }

```

---

**代码列表 1.1** `print/PrintComponent.java`

点击此处查看图像

```java
1   package print;

2

3   import java.awt.*;

4   import java.awt.print.*;

5

6   import javax.print.attribute.*;

7   import javax.swing.*;

8

9   /**

10     * 此组件为显示和打印生成 2D 图形图像。

11     */

12   public class PrintComponent extends JComponent implements Printable

13   {

14      private final Dimension PREFERRED_SIZE = Dimension(300, 300);

15      public void paintComponent(Graphics g)

16      {

17          Graphics2D g2 = (Graphics2D) g;

18          drawPage(g2);

19      }

20

21      public int print(Graphics g, PageFormat pf, int page) throws PrinterException

22      {

23          if (page >= 1) return Printable.NO_SUCH_PAGE;

24          Graphics2D g2 = (Graphics2D) g;

25          g2.translate(pf.getImageableX(), pf.getImageableY());

26          g2.draw(new Rectangle2D.Double(0, 0, pf.getImageableWidth(), pf.getImageableHeight()));

27

28          drawPage(g2);

29          return Printable.PAGE_EXISTS;

30      }

31

32      /**

33        * 此方法在屏幕和打印机图形上下文中都绘制页面。

34        * @param g2 图形上下文

35        */

36      public void drawPage(Graphics2D g2)

37      {

38          FontRenderContext context = g2.getFontRenderContext();

39          Font f = new Font("Serif", Font.PLAIN, 72);

40          GeneralPath clipShape = new GeneralPath();

41

42          TextLayout layout = new TextLayout("Hello", f, context);

43          AffineTransform transform = AffineTransform.getTranslateInstance(0, 72);

44          Shape outline = layout.getOutline(transform);

45          clipShape.append(outline, false);

46

47          layout = new TextLayout("World", f, context);

48          transform = AffineTransform.getTranslateInstance(0, 144);

49          outline = layout.getOutline(transform);

50          clipShape.append(outline, false);

51

52          g2.clip(clipShape);

53      }

54

  }

```

返回`PORTRAIT`、`LANDSCAPE`或`REVERSE_LANDSCAPE`之一。页面朝向对程序员来说是透明的，因为页面格式和图形上下文设置会自动反映页面朝向。

## 11.12.2 多页打印

在实践中，你通常不应该将原始的`Printable`对象传递给打印任务。相反，你应该获取一个实现了`Pageable`接口的类的对象。Java 平台提供了此类这样的类，称为`Book`。一本书由多个部分组成，每个部分都是一个`Printable`对象。要创建一个书籍，请添加`Printable`对象及其页数。

点击此处查看代码图像

```java
Book book = new Book();

Printable coverPage = . . .;

Printable bodyPages = . . .;

book.append(coverPage, pageFormat); // 添加 1 页

book.append(bodyPages, pageFormat, pageCount);
```




然后，使用`setPageable`方法将`Book`对象传递给打印任务。

```java
printJob.setPageable(book);
```

现在，打印任务确切知道要打印多少页，因此打印对话框会显示准确的页范围，用户可以选择整个范围或子范围。

![Image](img/00004.jpeg)

**注意**

当打印任务调用`Printable`部分的`print`方法时，它传递的是`book`的当前页码，而不是每个`section`的当前页码作为当前页码。这是一个巨大的痛苦——每个部分都必须知道之前部分的页数，才能使页码参数具有意义。

从程序员的角度来看，使用`Book`类的最大挑战在于，你必须在打印时知道每个部分将有多少页。你的`Printable`类需要一个布局算法，用于计算材料在打印页面上的布局。在打印开始之前，调用该算法来计算分页页符和总页数。你可以保留布局信息，以便在打印过程中方便使用。

你必须防范用户可能更改了页面格式的情况。如果发生这种情况，即使你想要打印的内容没有变化，你也必须重新计算布局。

Listing 11.13 展示了如何生成多页打印。此程序在若干页上用非常大的字符打印消息（参见图 11.35）。然后你可以修剪边距并将页面胶在一起形成一个横幅。

![Image](img/00296.jpeg)

**图 11.35** 一个横幅

`Banner`类的`layoutPages`方法计算布局。我们首先用 72 点字体布局消息字符串。然后，我们计算结果字符串的高度，并将其与页面的可打印高度进行比较。我们从这两个测量值中派出一个比例因子。在打印字符串时，我们按该比例因子对其放大。

![Image](img/00004.jpeg)

**注意**

为了精确地布局你的信息，你通常需要访问打印机图形上下文。遗憾的是，在打印实际开始之前没有获取该图形上下文。在示例程序中，我们凑使用屏幕图形上下文，并希望屏幕和打印机的字体度量匹配。

`Banner`类的`getPageCount`方法首先调用布局方法。然后，它放大字符串的宽度并将其除以每页的可打印宽度。商的结果（向上取整到下一个整数）即为页数。

听起来打印横幅可能很难，因为字符可能会跨越多个页面。然而，得益于 Java 2D API 的强大，事实证明完全不是问题。当请求特定页面时，我们只需使用`Graphics2D`类的`translate`方法将字符串的左上角向左移动。然后，我们设置一个等于当前页面的裁剪矩形（参见图 11.36）。最后，我们使用布局方法计算的比例因子对图形上下文进行缩放。

![Image](img/00297.jpeg)

**图 11.36** 打印横幅页

这个示例展示了变换的力量。绘制代码保持简单，变换完成了将绘制放置在相应位置的所有工作。最后，裁剪切掉了超出页面的图像部分。在下一节中，你将看到变换的另一个引人注目的用途——显示打印预览。

## 11.12.3 打印预览

大多数专业程序都有打印预览机制，让你可以在屏幕上查看页面，这样你就不会在不喜的打印输出上浪费纸张。Java 平台的打印类没有提供标准的“打印预览”对话框，但很容易设计你自己的（参见图 11.37）。在这一节中，我们将向你展示如何。Listing 11.14 中的`PrintPreviewDialog`类是完全通用的——你可以用它预览任何类型的打印输出。

![Image](img/00298.jpeg)

**图 11.37** 打印预览，显示横幅页

要构造`PrintPreviewDialog`，提供`Printable`或`Book`，以及`PageFormat`对象。对话框包含`PrintPreviewCanvas`（参见 Listing 11.15）。当你翻阅页面时，`paintComponent`方法调用`Printable`对象的`print`方法。通常，`print`方法在打印机图形上下文绘图。然而，我们提供屏幕图形上下文，经过缩放以使整个页面适应屏幕矩形。

`print`方法并不知道它并没有实际产生页面。它只是在屏幕上绘图，产生微缩的打印预览。这是 Java 2D 建模强大引人注目的证明。

```java
JOptionPane.showMessageDialog(BookTestFrame.this, e);
}
});

JButton pageSetupButton = new JButton("页面设置");

buttonPanel.add(pageSetupButton);

pageSetupButton.addActionListener(event ->
{
    PrinterJob job = PrinterJob.getPrinterJob();
    pageFormat = job.pageDialog(attributes);
});

JButton printPreviewButton = new JButton("打印预览");

buttonPanel.add(printPreviewButton);

printPreviewButton.addActionListener(event ->
{
    PrintPreviewDialog dialog = new PrintPreviewDialog(makeBook());
    dialog.setVisible(true);
});

add(buttonPanel, BorderLayout.SOUTH);

pack();
}

/**
 * 创建一个包含封面页和横幅内容页的书。
 */
public Book makeBook()
{
    if (pageFormat == null) {
        PrinterJob job = PrinterJob.getPrinterJob();
        pageFormat = job.defaultPage();
    }

    Book book = new Book();
    String message = text.getText();
    Banner banner = new Banner(message);
    int pageCount = banner.getPageCount((Graphics2D) getGraphics(), pageFormat);
    book.append(new CoverPage(message + " (" + pageCount + " pages)"), pageFormat);
    book.append(banner, pageFormat, pageCount);
    return book;
}
}
```

### 11.13 `book/Banner.java`

点击此处查看代码图片

```java
package book;

import java.awt.*;
import java.awt.font.*;
import java.awt.geom.*;
import java.awt.print.*;

/**
 * 一个在多页上打印文本字符串的横幅。
 */
public class Banner implements Printable
{
    private String message;
    private double scale;

    /**
     * 构造横幅。
     * @param m 消息字符串
     */
    public Banner(String m)
    {
        message = m;
    }

    /**
     * 获取此部分的页数。
     * @param g2 图形上下文
     * @param pf 页面格式
     * @return 需要的页数
     */
    public int getPageCount(Graphics2D g2, PageFormat pf)
    {
        if (message.equals("")) return 0;

        FontRenderContext context = g2.getFontContext();
        Font f = new Font("Serif", Font.PLAIN, 72);
        Rectangle2D bounds = f.getStringBounds(message, context);
        scale = pf.getImageableHeight() / bounds.getHeight();
        double width = scale * bounds.getWidth();
        int pages = (int) Math.ceil(width / pf.getImageableWidth());
        return pages;
    }

    public int print(Graphics g, PageFormat pf, int page) throws PrinterException
    {
        Graphics2D g2 = (Graphics2D) g;

        if (page > getPageCount(g2, pf)) return Printable.NO_SUCH_PAGE;

        g2.translate(pf.getImageableX(), pf.getImageableY());
        drawPage(g2, pf);
        return Printable.PAGE_EXISTS;
    }

    public void drawPage(Graphics2D g2, PageFormat pf, int page)
    {
        if (message.equals("")) return;

        page--; // 考虑到封面
        drawCropMarks(g2, pf);

        g2.clip(new Rectangle2D.Double(
            0,
            0,
            pf.getImageableWidth(),
            pf.getImageableHeight()
        ));

        g2.translate(-page * pf.getImageableWidth(), 0);
        g2.scale(scale, scale);

        FontRenderContext context = g2.getFontContext();
        Font f = new Font("Serif", Font.PLAIN, 72);
        TextLayout layout = new TextLayout(message, f, context);
        AffineTransform transform = AffineTransform.getTranslate(0, layout.getAscent());
        Shape outline = layout.getOutline(transform);
        g2.draw(outline);
    }

    /**
     * 在页面角落绘制 1/2 裁剪线。
     * @param g2 图形上下文
     * @param pf 页面格式
     */
    public void drawCropMarks(Graphics2D g2, PageFormat pf)
    {
        final double C = 36; // 裁剪线长度 = 1/2 英寸
        double w = pf.getImageableWidth();
        double h = pf.getImageableHeight();

        g2.draw(new Line2D.Double(0, 0, 0, C));
        g2.draw(new Line2D.Double(0, 0, C, 0));
        g2.draw(new Line2D.Double(w, 0, w, C));
        g2.draw(new Line2D.Double(w, 0, w - C, 0));
        g2.draw(new Line2D.Double(0, h, 0, h - C));
        g2.draw(new Line2D.Double(0, h, C, h));
        g2.draw(new Line2D.Double(w, h, w, h - C));
        g2.draw(new Line2D.Double(w, h, w, h));
    }
}
```

```java
buttonPanel.add(closeButton);
closeButton.addActionListener(event -> setVisible(false));
add(buttonPanel, BorderLayout.SOUTH);
}
}
```

### 列表 11.15 `book/PrintPreviewCanvas.java`

点击此处查看代码图片

```java
package book;

import java.awt.*;
import java.awt.geom.*;
import java.awt.print.*;
import javax.swing.*;

/**
 * 用于显示打印预览的画布。
 */
class PrintPreviewCanvas extends JComponent
{
    private Book book;
    private int currentPage;

    /**
     * 构造一个打印预览画布。
     * @param b 要预览的图书
     */
    public PrintPreviewCanvas(Book b)
    {
        book = b;
        currentPage = 0;
    }

    public void paintComponent(Graphics g)
    {
        Graphics2D g2 = (Graphics2D) g;
        PageFormat pageFormat = book.getPageFormat(currentPage);

        double xoff; // 页面起始在窗口中的 x 偏移
        double yoff; // 页面起始在窗口中的 y 偏移
        double scale; // 使页面自适应窗口的缩放因子

        double px = pageFormat.getWidth();
        double py = pageFormat.getHeight();
        double sx = getWidth() - 1;
        double sy = getHeight() - 1;

        if (px / py < sx / sy) // 水平居中
        {
            scale = sy / py;
            xoff = 0.5 * (sx - scale * px);
            yoff = 0;
        }
        else // 垂直居中
        {
            scale = sx / px;
            xoff = 0;
            yoff = 0.5 * (sy - scale * py);
        }

        g2.translate((float) xoff, (float) yoff);
        g2.scale((float) scale, (float) scale);

        // 绘制轮廓（忽略页边距）
        Rectangle2D page = new Rectangle2D.Double(0, 0, px, py);
        g2.setPaint(Color.white);
        g2.fill(page);
        g2.setPaint(Color.black);
        g2.draw(page);

        Printable printable = book.getPrintable(currentPage);

        try
        {
            printable.print(g2, pageFormat, currentPage);
        }
        catch (PrinterException e)
        {
            g2.draw(new Line2D.Double(0, 0, px, py));
            g2.draw(new Line2D.Double(px, 0, 0, py));
        }
    }

    /**
     * 根据指定的页数翻页。
     * @param by 要翻页的页数。负值向后翻。
     */
    public void flipPage(int by)
    {
        int newPage = currentPage + by;

        if (0 <= newPage && newPage < book.getNumberOfPages())



```java
{
    currentPage = newPage;
    repaint();
}
```

`java.awt.print.PrinterJob`

- `void setPageable(Pageable p)` 设置一个 `Pageable`（如 `Book`）进行打印。

`java.awt.print.Book`

- `void append(Printable p, PageFormat format)`
- `void append(Printable p, PageFormat format, int pageCount)` 向此图书中添加一个章节。如果未指定页数，则添加第一页。
- `Printable getPrintable(int page)` 获取指定页面的可打印对象。

#### 11.12.4 打印服务

到为止，你已经了解了如何打印 2D 图形。然而，Java SE 1.4 引入的打印 API 提供了更大的灵活性。该 API 定义了多种数据类型，并让你找到能够打印这些数据的打印服务。这些数据类型包括：

- GIF、JPEG 或 PNG 格式的图像
- 文本、HTML、PostScript 或 PDF 格式的文档
- 原始打印机代码数据
- 实现了 `Printable`、`Pageable` 或 `RenderableImage` 的类的对象

数据本身可以存储在字节或字符源中，例如输入流、URL 或数组。`document flavor`（文档口味）描述了数据源和数据类型的组合。`DocFlavor` 类为各种数据源定义了许多内部类。每个内部类都定义了常量来指定这些口味。例如，`DocFlavor.INPUT_STREAM` 描述了从输入流读取的 GIF 图像。表 1.3 用于打印服务的文档口味。

假设你想打印一个位于文件中的 GIF 图像。首先，查找是否存在能够处理该任务的打印服务。`PrintServiceLookup` 类的静态方法 `lookupServices` 返回一个可以处理给定味调的 `PrintService` 对象数组。

```java
DocFlavor flavor = DocFlavor.INPUT_STREAM;

PrintService[] services = PrintServiceLookup.lookupPrintServices(flavor, null);
```

`lookupServices` 方法的第二个参数为 `null`，表示我们不想通过打印机属性来限制搜索。我们将在下一节中介绍属性。如果查询返回的包含多个元素的数组，请从列出的打印服务中进行选择。你可以调用 `PrintService` 类的 `getName` 方法来获取打印机名称并让用户选择。

接下来，从服务获取文档打印作业：

```java
PrintJob job = services[i].createPrintJob();
```

对于打印，你需要一个实现 `Doc` 接口的对象。Java 库提供了 `SimpleDoc` 用于此目的。`SimpleDoc` 构造函数需要数据源、文档口味以及可选的属性集。例如：

```java
InputStream in = new FileInputStream(fileName);

Doc doc = new SimpleDoc(in, flavor, null);
```

最后，你就可以准备打印了：

```java
job.print(doc, null);
```

与之前一样，`null` 参数可以用属性集替换。注意，这个打印过程与前面的节完全不同。没有通过对话框进行用户交互。例如，你可以实现一种服务端打印机制，用户通过 Web 表单提交打印作业。列表 11.16 中的程序演示了如何使用打印服务打印图像文件。

### 列表 11.16 `printService/PrintServiceTest.java`

点击此处查看代码图片。

```java
package printService;

import java.io.*;
import java.nio.file.*;
import javax.print.*;

/**
 * 此程序演示了打印服务的使用。该程序让你将 GIF 图像打印到
 * 支持 GIF 文档口味的任何打印服务上。
 *
 * @version 1.10 2007-08-16
 * @author Cay Horstmann
 */
public class PrintServiceTest {
    public static void main(String[] args) {
        DocFlavor flavor = DocFlavor.URL.GIF;
        PrintService[] services =
            PrintServiceLookup.lookupPrintServices(flavor, null);

        if (args.length == 0) {
            if (services.length == 0) {
                System.out.println("No printer for flavor " + flavor);
            } else {
                System.out.println(
                    "指定一个口味为 " + flavor + " 的文件\n"
                    + "并可选指定所需的打印机编号."
                );

                for (int i = 0; i < services.length; i++) {
                    System.out.println((i + 1) + ": " + services[i].getName());
                }
            }
        }

        System.exit(0);
    }

    String fileName = args[0];
    int p = 1;
}
```

```java
if (args.length > 1) {
    p = Integer.parseInt(args[1]);
}

if (fileName == null) {
    return;
}

try (InputStream in = Files.newInputStream(Paths.get(fileName))) {
    Doc doc = new SimpleDoc(in, flavor, null);
    DocPrintJob job = services[p - 1].createPrintJob();
    job.print(doc, null);
} catch (Exception ex) {
    ex.printStackTrace();
}
```

### `javax.print.PrintServiceLookup` 1.4

- `PrintService[] lookupPrintServices(DocFlavor flavor, AttributeSet attributes)`

查找可以处理给定文档格式和属性的打印服务。

![Image](img/00300.jpeg)

### `javax.print.PrintService` 1.4

- `DocPrintJob createPrintJob()`

为实现 `Doc` 接口的类对象（例如 `SimpleDoc`）创建一个打印打印任务。

### `javax.print.DocPrintJob` 1.4

- `void print(Doc doc, PrintRequestAttributeSet attributes)`

使用给定的属性打印给定的文档。

![Image](img/00301.jpeg)

### `javax.print.SimpleDoc` 1.4

- `SimpleDoc(Object data, DocFlavor flavor, DocAttributeSet attributes)`

构造一个可以使用 `DocPrintJob` 打印的 `SimpleDoc` 对象。

![Image](img/00302.jpeg)

#### 11.12.5 流打印服务

打印服务将打印数据发送到打印机。流打印服务生成相同的打印数据，但将其发送到输出流中，可能是为了延迟打印，或者因为打印数据格式可以被其他程序解释。特别是，如果打印数据格式是 PostScript，那么将打印数据保存到文件中可能是很有用的，因为许多程序都可以处理 PostScript 文件。Java 平台包含一种流打印服务，可以从图像和 2D 图形生成 PostScript 输出。你可以在所有系统上使用该服务，即使没有本地打印机。

枚举流打印服务比查找普通打印服务稍微复杂一点。你需要被打印对象的 `DocFlavor` 还需要输出流的 MIME 类型。然后你将得到一个 `StreamPrintServiceFactory` 工厂数组。

点击此处查看代码图像。

```java
DocFlavor flavor = DocFlavor.SERVICE_FORMATTED.PRINTABLE;

String mimeType = "application/postscript";

StreamPrintServiceFactory[] factories =
    StreamPrintServiceFactory.lookupStreamPrintServiceFactories(
        flavor, mimeType
    );
```

`StreamPrintServiceFactory` 类没有可以帮助我们区分任何一个工厂的方法，所以我们直接取 `factories[0]`。我们调用 `getPrintService` 方法并传入输出流参数来获取 `StreamPrintService` 对象。

点击此处查看代码图像。

```java
OutputStream out = new FileOutputStream(fileName);

StreamPrintService service = factories[0].getPrintService(out);
```

`StreamPrintService` 类是 `PrintService` 的子类。要产生打印输出，只需按照前一节的步骤操作。

### `javax.print.StreamPrintServiceFactory` 1.4

- `StreamPrintServiceFactory[] lookupStreamPrintServiceFactories(DocFlavor flavor, String mimeType)`

查找可以打印给定文档格式并产生给定 MIME 类型输出流的流打印服务工厂。

- `StreamPrintService getPrintService(OutputStream out)`

获取一个将打印输出发送到给定输出流的打印服务。

#### 11.12.6 打印属性

打印服务 API 包含了一组复杂的接口和类用于指定属性。有四个重要的组：

- `PrintRequest attributes`：请求打印机的功能，例如双面。
- `Doc attributes`：仅适用于 `doc` 的属性。
- `PrintService attributes`：提供有关服务的信息，例如品牌和型号。
- `PrintJob attributes`：提供状态信息，例如任务是否已完成。

`Attribute` 接口有四个子接口：

```text
PrintRequestAttribute
DocAttribute
PrintServiceAttribute
PrintJobAttribute
```

`AttributeSet` 超接口有四个子接口：

```text
PrintRequestAttributeSet
DocAttributeSet
PrintServiceAttributeSet
PrintJobAttributeSet
```

这些接口每个都有一个实现类：

- `HashAttributeSet`
- `HashRequestAttributeSet`
- `HashDocAttributeSet`
- `HashPrintServiceAttributeSet`
- `HashPrintJobAttributeSet`

例如，你可以这样构造打印请求属性集：

```java
PrintRequestAttributeSet attributes = new HashRequestAttributeSet();
```

构造好集合后，你就不需要再担心 `Hash` 前缀了。

为什么要所有这些接口？它们使得检查属性的正确用法成为可能。例如，`DocAttributeSet` 只接受实现 `DocAttribute` 的对象。任何添加另一个属性的尝试都会导致运行时错误。

属性集是一种特殊的映射（map），其键的类型为 `Class`，而值属于实现 `Attribute` 接口的类。例如，如果你向属性集中插入一个对象 `new Copies(10)`，那么它的键就是 `Copies.class` `Class` 对象。该键被称为属性的类别（category）。`Attribute` 接口声明了一个方法 `Class getCategory()`，用于返回属性的类别。`Copies` 类定义了返回对象 `Copies.class` 的方法，但并不要求类别与属性的类相同。

要检索属性，你需要使用类别作为键，例如：

```java
AttributeSet attributes = job.getAttributes();

Copies copies = (Copies) attributes.get(Copies.class);
```

最后，属性根据它们可能拥有的值进行组织。`Copies` 属性可以有任何整数值。`Copies` 类继承自 `IntegerSyntax` 类，该类负责处理所有整数值的属性。`getValue` 方法返回属性的整数值，例如：

```java
int n = copies.getValue();
```

这些类：

- `TextSyntax`
- `DateTimeSyntax`
- `URISyntax`

……封装了字符串、日期和时间值或 URI。

最后，许多属性可以取有限数量的值。例如，`PrintQuality` 属性有三个设置：草稿（draft）、普通（normal）和高质（high）。它们由三个常量表示：

```java
PrintQuality.DRAFT
PrintQuality.NORMAL
PrintQuality.HIGH
```

具有有限数量值的属性类继承自 `EnumSyntax` 类，该类提供了许多便利方法，以类型安全的方式设置这些枚举。在使用此类属性时，你不需要担心其内部机制。只需将命名值添加到属性集中即可：

```java
attributes.add(PrintQuality.HIGH);
```

以下是检查属性值的方法：

```java
if (attributes.get(PrintQuality.class) == PrintQuality.HIGH)
    . . .
```



表 11.4 列出了打印属性。第二列列出了属性类的超类（例如，对于 `Copies` 属性为 `IntegerSyntax`）或具有有限值集的属性的枚举值集。最后四列指示属性类是否实现了 `DocAttribute`（DA）、`PrintJobAttribute`（PJA）、`PrintRequestAttribute`（PRA）和 `PrintServiceAttribute`（PSA）接口。

![Image](img/00305.jpeg)![Image](img/00306.jpeg)![Image](img/00307.jpeg)![Image](img/00308.jpeg)![Image](img/00309.jpeg)

**表 11.4** 打印属性

> ![Image](img/00002.jpeg) 注意：如你所示，有很多属性，其中许多非常专门。大多数属性的来源是互联网打印协议 1.1（RFC 2911）。

> ![Image](img/00002.jpeg) 注意：早版本的打印 API 引入了 `JobAttributes` 和 `PageAttributes` 类，其目的与本节涵盖的打印属性相似。这些类现在已经过时了。

### `javax.print.attribute.Attribute` 1.4

- `Class getCategory()`：获取此属性的类别。
- `String getName()`：获取此属性的名称。

### `javax.print.attribute.AttributeSet` 1.4

- `boolean add(Attribute attr)`：向此集合添加属性。如果集合中存在另一个相同类别的属性，则该属性将由给定的属性替换。如果集合由于此操作发生了变化，则返回 `true`。
- `Attribute get(Class category)`：根据指定的类别键检索属性，如果不存在此类属性，则返回 `null`。
- `boolean remove(Attribute attr)`
- `boolean remove(Class category)`：从集合中删除指定的属性，或具有给定类别的属性。如果集合由于此操作发生了变化，则返回 `true`。
- `Attribute[] toArray()`：返回包含集合中所有属性的数组。

### `javax.print.PrintService` 1.4

- `PrintServiceAttributeSet getAttributes()`：获取打印服务的属性。

### `javax.print.DocPrintJob` 1.4

- `PrintJobAttributeSet getAttributes()`：获取打印任务的属性。

我们关于打印的讨论此结束。你现在知道如何打印 2D 图形和其他文档类型，如何枚举打印机和流打印服务，以及如何设置和检索属性。接下来，我们转向两个重要的用户界面问题：剪贴板和拖放机制。

## 11.13 剪贴板

GUI 环境（如 Windows 和 X Window System）中最方便的用户界面机制之一是剪切和粘贴。你在一个程序中选择某些数据并将其剪切或复制到剪贴板。然后切换到另一个程序并将剪贴板内容粘贴到该应用程序。使用剪贴板，你可以将文本、图像或其他数据从一个文档传输到另一个文档，或者从同一个文档的一个地方传输到另一个地方。剪切粘贴是非常自然的，以至于大多数计算机用户从未考虑过它。

尽管剪贴板在概念上很简单，但实现剪贴板服务实际上比你想象的要困难。假设你从文字处理器中复制文本到剪贴板。如果你将该文本粘贴到另一个文字处理器，你期望字体和格式保持完整。也就是说，剪贴板中的文本需要保留格式信息。然而，如果你将文本粘贴到纯文本字段，你期望只粘贴字符，而没有额外的格式代码。为了支持这种灵活性，数据提供者必须能够以多种格式提供剪贴板数据，以便数据消费者可以从中选择一种。

Microsoft Windows 和 Macintosh 的系统剪贴板实现相似，但当然存在细微差异。然而，X Window System 的剪贴板机制要限制得多——对纯文本以外的任何内容的剪切和粘贴仅偶尔支持。在尝试本节中的程序时，你应该考虑这些局限性。

> ![Image](img/00002.jpeg) 注意：查看平台上的 `jre/lib/flavormap.properties` 文件，了解 Java 程序和系统剪贴板之间可以传输哪些对象。

通常，程序需要支持系统剪贴板无法处理的数据类型的剪切和粘贴。数据传输 API 支持在同一虚拟机内传输任意本地引用。在不同的虚拟机之间，你可以传输序列化对象和远程对象的引用。

表 11.5 总结了剪贴板机制的数据传输能力。

![Image](img/00310.jpeg)

**表 11.5** Java 数据传输机制的能力

### 11.13.1 数据传输的类和接口

Java 中的数据传输是在名为 `java.awt.datatransfer` 的包实现的。以下是该包中最重要的类和接口的概述：

- 可以通过剪贴板传输的对象实现了 `Transferable` 接口。
- `Clipboard` 类描述剪贴板。`Transferable` 对象是能够放入或取出剪贴板的唯一项。系统剪贴板是 `Clipboard` 的具体示例。
- `DataFlavor` 类描述可以放在剪贴板上的数据类型（data flavors）。
- `StringSelection` 类是实现 `Transferable` 接口的具体类。它传输文本字符串。
- 如果一个类希望在剪贴板内容被他人覆盖时收到通知，它就必须实现 `ClipboardOwner` 接口。剪贴板所有权实现了复杂数据的“延迟格式化”。如果一个程序传输简单数据（如字符串），它只需设置剪贴板内容并继续运行。然而，如果一个程序向剪贴板放置了可以以多种格式化的复杂数据，那么它可能并不真的想准备所有的格式，因为很有可能大多数格式永远不会被需要。但是，它需要保留剪贴板数据，以便在以后被请求时再创建这些格式。当剪贴板内容变化时，会通过调用其 `lostOwnership` 方法通知剪贴板所有者。这告诉它该信息不再需要了。在示例程序中，我们不需要担心剪贴板所有权。

## 11.13.2 传输文本

熟悉数据传输类的最佳方法是从最简单的情况开始：在系统剪贴板之间传输文本。首先，获取系统剪贴板的引用：

点击此处查看代码图像

```java
Clipboard clipboard = Toolkit.getDefaultToolkit().getSystemClipboard();
```

要将字符串传输到剪贴板，必须将其封装成 `StringSelection` 对象。

点击此处查看代码图像

```java
String text = . . .;

StringSelection selection = new StringSelection(text);
```

实际的传输是通过调用 `setContents` 完成的，该方法接受一个 `StringSelection` 对象和一个 `ClipboardOwner` 作为参数。如果你对指定剪贴板所有者感兴趣，可以将第二个参数设置为 `null`。

点击此处查看代码图像

```java
clipboard.setContents(selection, null);
```

以下是反向操作——从剪贴板读取字符串：

点击此处查看代码图像

```java
DataFlavor flavor = DataFlavor.stringFlavor;

if (clipboard.isDataFlavorAvailable(flavor))
    String text = (String) clipboard.getData(flavor);
```

Listing 1.17 是一个演示 Java 应用程序与系统剪贴板之间剪切粘贴的程序。如果你在文本区域选择一些文本并点击复制，选中的内容就会复制到系统剪贴板。你可以将其粘贴到任何文本编辑器中（参见图 1.40）。相反，当你从文本编辑器复制文本时，可以将其粘贴到我们的示例程序中。

![Image](img/031.jpeg)

**图 1.40** `TextTransfer` 程序  
**Listing 1.17** `transferText/TextFrame.java`

点击此处查看代码图像

```java
package transferText;

import java.awt.*;
import java.awt.datatransfer.*;
import java.awt.event.*;
import java.io.*;
import javax.swing.*;

/**
 * 此框架包含一个文本区域以及用于复制和粘贴文本的按钮。
 */
public class TextTransferFrame extends JFrame {
    private JTextArea textArea;

    private static final int TEXT_ROWS = 20;
    private static final int TEXT_COLUMNS = 60;

    public TextTransferFrame() {
        textArea = new JTextArea(TEXT_ROWS, TEXT_COLUMNS);
        add(new JScrollPane(textArea), BorderLayout.CENTER);

        JPanel panel = new JPanel();

        JButton copyButton = new JButton("Copy");
        panel.add(copyButton);
        copyButton.addActionListener(event -> copy());

        JButton pasteButton = new JButton("Paste");
        panel.add(pasteButton);
        pasteButton.addActionListener(event -> paste());

        add(panel, BorderLayout.SOUTH);
        pack();
    }

    /**
     * 将选中文复制到系统剪贴板。
     */
    private void copy() {
        Clipboard clipboard = Toolkit.getDefaultToolkit().getSystemClipboard();
        String text = textArea.getSelectedText();

        if (text == null) text = textArea.getText();

        StringSelection selection = new StringSelection(text);
        clipboard.setContents(selection, null);
    }

    /**
     * 将系统剪贴板中的文本粘贴到文本区域。
     */
    private void paste() {
        Clipboard clipboard = Toolkit.getDefaultToolkit().getSystemClipboard();
        DataFlavor flavor = DataFlavor.stringFlavor;

        if (clipboard.isDataFlavorAvailable(flavor)) {
            try {
                String text = (String) clipboard.getData(flavor);
                textArea.replaceSelection(text);
            } catch (UnsupportedFlavorException | IOException ex) {
                JOptionPane.showMessageDialog(this, ex);
            }
        }
    }
}
```

- `java.awt.Toolkit`（1.0）：`Clipboard getSystemClipboard()` 获取系统剪贴板。
- `java.awt.datatransfer.Clipboard`（1.1）：`Transferable getContents(Object requester)` 获取剪贴板内容。
- `java.awt.datatransfer.Clipboard`（1.1）：`void setContents(Transferable contents, ClipboardOwner owner)` 将内容放入剪贴板。
- `java.awt.datatransfer.DataFlavor`（5.0）：`boolean isDataFlavorAvailable(DataFlavor flavor)` 如果剪贴板具有该格式的数据，则返回 `true`。
- `java.awt.datatransfer.DataFlavor`（5.0）：`Object getData(DataFlavor flavor)` 获取给定格式的数据，如果没有可用数据，则抛出 `UnsupportedFlavorException`。
- `java.awt.datatransfer.ClipboardOwner`（1.1）：`void lostOwnership(Clipboard clipboard, Transferable contents)` 通知该对象它不再是剪贴板内容的所有者。
- `java.awt.datatransfer.Transferable`（1.1）：
  - `boolean isFlavorSupported(DataFlavor flavor)`：如果指定的格式是支持的数据格式之一，则返回 `true`；否则返回 `false`。
  - `Object getTransferData(DataFlavor flavor)`：返回请求格式格式的数据。如果格式不支持，则抛出 `UnsupportedFlavorException`。

## 11.13.3 `Transferable` 接口与数据格式

`DataFlavor` 由两个特征定义：

- MIME 类型名称（例如 `"image/gif"`）。
- 用于访问数据的表示类（例如 `java.awt.Image`）。

此外，每个数据格式都有一个可读的名称（例如 `"GIF Image"`）。可以通过 MIME 类型中的 `class` 参数指定表示类，例如：

点击此处查看代码图像

```text
image/gif;class=java.awt.Image
```

> ![Image](img/002.jpeg) 注意：这只是语法示例。没有传输 GIF 图像的标准数据格式。

如果没有 `class` 参数，表示类为 `InputStream`。对于本地、序列化和远程 Java 对象定义了三种 MIME 类型：

点击此处查看代码图像

```text
application/x-java-jvm-local-objectref

application/x-java-serialized-object

application/x-java-remote-object
```

> ![Image](img/002.jpeg) 注意：`x-` 前缀表示这是一个实验性名称，不是由分配标准 MIME 类型名称的组织 IANA 认可的。

例如，标准的 `stringFlavor` 数据格式由以下 MIME 类型描述：

点击此处查看代码图像

```text
application/x-java-serialized-object;class=java.lang.String
```

你可以要求剪贴板列出所有可用格式：

点击此处查看代码图片

```java
DataFlavor[] flavors = clipboard.getAvailableDataFlavors();
```



你还可以在剪贴板上安装`FlavorListener`。当剪贴板上的数据类型集合发生变化时，监听器会收到通知。详情请参见 API 备注。

### java.awt.datatransfer.DataFlavor 1.1

- `DataFlavor(String mimeType, String humanPresentableName)`：创建一个描述由 MIME 类型描述的格式中的流数据的数据类型。

![Image](img/00315.jpeg)

- `DataFlavor(Class class, String humanPresentableName)`：创建一个描述 Java 平台类的数据类型。其 MIME 类型为`application/x-java-serialized-object;class=className`。

![Image](img/00316.jpeg)

- `String getMimeType()`：返回此数据类型的 MIME 类型字符串。

- `boolean isMimeTypeEqual(String mimeType)`：测试此数据类型是否具有给定的 MIME 类型。

- `String getHumanPresentableName()`：返回此数据类型数据格式的人类读名称。

- `Class getRepresentationClass()`：返回一个`Class`对象，该对象表示当`Transferable`对象在带有此数据类型调用时返回的对象的类。该类是 MIME 类型的`class`参数或`InputStream`。

### java.awt.datatransfer.Clipboard 1.1

- `DataFlavor[] getAvailableDataFlavors()` 5.0：返回可用数据类型的数组。

- `void addFlavorListener(FlavorListener listener)` 5.0：添加一个监听器，当可用类型集合发生变化时会对其进行通知。

### java.awt.datatransfer.Transferable 1.1

- `DataFlavor[] getTransferDataFlavors()`：返回支持的类型数组。

### java.awt.datatransfer.FlavorListener 5.0

- `void flavorsChanged(FlavorEvent event)`：当剪贴板的可用类型集合发生变化时调用此方法。

### 11.13.4 构建一个图像 Transferable

你想要通过剪贴板传输的对象必须实现`Transferable`接口。`StringSelection`类是 Java 标准库中唯一实现`Transferable`接口的公共类。在本节中，你将看到如何将图像传输到剪贴板。由于 Java 没有提供图像传输的类，你必须自己实现它。

该类非常简单。它只是报告唯一可用的数据格式是`DataFlavor.imageFlavor`，并且持有一个`image`对象。

```java
class ImageTransferable implements Transferable
{
   private Image theImage;

   public ImageTransferable(Image image)
   {
      theImage = image;
   }

   public DataFlavor[] getTransferDataFlavors()
   {
      return new DataFlavor[] { DataFlavor.imageFlavor };
   }

   public boolean isDataFlavorSupported(DataFlavor flavor)
   {
      return flavor.equals(DataFlavor.imageFlavor);
   }

   public Object getTransferData(DataFlavor flavor)
      throws UnsupportedFlavorException
   {
      if(flavor.equals(DataFlavor.imageFlavor))
      {
         return theImage;
      }
      else
      {
         throw new UnsupportedFlavorException(flavor);
      }
   }
}
```

![Image](img/00002.jpeg) 注意

Java SE 提供了`DataFlavor.imageFlavor`常量，并完成了 Java 图像与原生剪贴板图像之间转换的所有繁重工作。然而的是，它并没有提供将图像放置到剪贴板所需的包装类。

Listing 11.18 中的程序演示了 Java 应用程序与系统剪贴板之间的图像传输。程序启动时，它会生成一个包含红色圆形的图像。点击“复制”按钮将图像复制到剪贴板，然后将其粘贴到另一个应用程序中（参见图 11.41）。从另一个应用程序将图像复制到系统剪贴板。然后点击按钮，看到图像被粘贴到示例程序中（参见图 11.42）。

![Image](img/0317.jpeg) 图 11.41 从 Java 程序复制到原生程序

![Image](img/0318.jpeg) 图 11.42 从原生程序复制到 Java 程序

该程序是对文本程序的直接修改。现在数据类型变为了`DataFlavor.imageFlavor`，我们使用`Transferable`类将图像传输到系统剪贴板。**代码列表 11.18** `imageTransfer/ImageTransferFrame.java`

```java
package imageTransfer;

import java.awt.*;
import java.awt.datatransfer.*;
import java.awt.image.*;
import java.io.*;
import javax.swing.*;

/**
 * 此帧包含一个图像标签和用于复制和粘贴图像的按钮。
 */
class ImageTransferFrame extends JFrame
{
   private JLabel label;
   private Image image;
   private static final IMAGE_WIDTH = 300;
   private static final IMAGE_HEIGHT = 300;

   public ImageTransferFrame()
   {
      label = new JLabel();
      image = new BufferedImage(IMAGE_WIDTH, IMAGE_HEIGHT, BufferedImage.TYPE_INT_ARGB);
      Graphics g = image.getGraphics();
      g.setColor(Color.WHITE);
      g.fillRect(0, 0, IMAGE_WIDTH, IMAGE_HEIGHT);
      g.setColor(Color.RED);
      g.fillOval(IMAGE_WIDTH / 4, IMAGE_HEIGHT / 4, IMAGE_WIDTH / 2, IMAGE_HEIGHT / 2);
      label.setIcon(new ImageIcon(image));
      add(new JScrollPane(label), BorderLayout.CENTER);

      JPanel panel = new JPanel();
      JButton copyButton = new JButton("Copy");
      panel.add(copyButton);
      copyButton.addActionListener(event -> copy());

      JButton pasteButton = new JButton("Paste");
      panel.add(pasteButton);
      pasteButton.addActionListener(event -> paste());

      add(panel, BorderLayout.SOUTH);
      pack();
   }

   /**
    * 将当前图像复制到剪贴板。
    */
   private void copy()
   {
      Clipboard clipboard = Toolkit.getDefaultToolkit().getSystemClipboard();
      ImageTransferable selection = new ImageTransferable(image);
      clipboard.setContents(selection, null);
   }

   /**
    * 从系统剪贴板将图像粘贴到标签中。
    */
   private void paste()
   {
      Clipboard clipboard = Toolkit.getDefaultToolkit().getSystemClipboard();
      DataFlavor flavor = DataFlavor.imageFlavor;
      if (clipboard.isFlavorAvailable(flavor))
      {
         try
         {
            image = (Image) clipboard.getData(flavor);
            label.setIcon(new ImageIcon(image));
         }
         catch (UnsupportedFlavorException | IOException ex)
         {
            JOptionPane.showMessageDialog(this, ex);
         }
      }
   }
}
```

你可以在两个 Java 应用之间传输序列化对象（参见图 11.43）。运行两个副本的`SerialTransferTest`程序。在第一个程序中点击“复制”，然后在第二个程序中点击“粘贴”。`Color`对象将从一台虚拟机传输到另一个虚拟机。

![Image](img/00319.jpeg)

**图 11.43** 在两个 Java 实例之间拷贝数据。

为了启用数据传输，Java 平台将序列化对象的二进制数据放在系统剪贴板上。另一个 Java 程序——不一定与生成剪贴板数据的程序相同——可以检索剪贴板数据并反序列化对象。

当然，非 Java 应用程序不知道如何处理剪贴板数据。因此，示例程序以第二种格式提供剪贴板数据——文本。该文本仅仅是对传输的对象应用`toString()`方法的结果。要查看第二种格式，请运行程序，点击一种颜色，然后在你的文本编辑器中选择“粘贴”命令。如下的字符串

```
java.awt.Color[r=255,g=0,b=51]
```

将被插入到你的文档中。

本质上，传输可序列化对象不需要额外的编程。使用 MIME 类型：

```
application/x-java-serialized-object;class=className
```

和之前一样，你必须构建自己的传输包装器——详情请参见示例代码。

**列表 11.19** `serialTransfer/SerialTransferFrame.java`

```java
package serialTransfer;

import java.awt.*;
import java.awt.datatransfer.*;
import java.awt.event.*;
import java.io.*;
import javax.swing.*;

/**
 * 此框架包含一个颜色选择器以及复制和粘贴按钮。
 */
class SerialTransferFrame extends JFrame
{
    private JColorChooser chooser;

    public SerialTransferFrame()
    {
        chooser = new JColorChooser();
        add(chooser, BorderLayout.CENTER);

        JPanel panel = new JPanel();
        JButton copyButton = new JButton("Copy");
        panel.add(copyButton);
        copyButton.addActionListener(event -> copy());

        JButton pasteButton = new JButton("Paste");
        panel.add(pasteButton);
        pasteButton.addActionListener(event -> paste());

        add(panel, BorderLayout.SOUTH);
        pack();
    }

    /**
     * 将选择器的颜色拷贝到系统剪贴板中。
     */
    private void copy()
    {
        Clipboard clipboard = Toolkit.getDefaultToolkit().getSystemClipboard();
        Color color = chooser.getColor();
        SerialTransferable selection = new SerialTransferable(color);
        clipboard.setContents(selection, null);
    }

    /**
     * 从系统剪贴板将颜色粘贴到选择器中。
     */
    private void paste()
    {
        Clipboard clipboard = Toolkit.getDefaultToolkit().getSystemClipboard();
        try
        {
            DataFlavor flavor = new DataFlavor(
                "application/x-java-serialized-object;class=java.awt.Color");
            if (clipboard.isDataFlavorAvailable(flavor))
            {
                Color color = (Color) clipboard.getData(flavor);
                chooser.setColor(color);
            }
        }
        catch (ClassNotFoundException | UnsupportedFlavorException | IOException ex)
        {
            JOptionPane.showMessageDialog(this, ex);
        }
    }

    /**
     * 此类是对象传输的包装器。
     */
    class SerialTransferable implements Transferable
    {
        private Serializable obj;

        /**
         * 构造选择。
         * @param o 可序列化对象
         */
        SerialTransferable(Serializable o)
        {
            obj = o;
        }

        public DataFlavor[] getDataFlavors()
        {
            DataFlavor[] flavors = new DataFlavor[2];
            Class<?> type = obj.getClass();
            String mimeType = "application/x-java-serialized-object;class=" + type.getName();
            try
            {
                flavors[0] = new DataFlavor(mimeType);
                flavors[1] = DataFlavor.stringFlavor;
                return flavors;
            }
            catch (ClassNotFoundException e)
            {
                // 处理异常
            }
            return flavors;
        }
    }
}
```



```java
return new DataFlavor[0];

}

}

public boolean isDataFlavorSupported(DataFlavor flavor)

{

    return DataFlavor.stringFlavor.equals(flavor)
        || "application".equals(flavor.getPrimaryType())
        && "x-java-serialized-object".equals(flavor.getSubType())
        && flavor.getRepresentationClass().isAssignableFrom(obj.getClass());

}

public Object getTransferData(DataFlavor flavor) throws UnsupportedFlavorException

{

    if (!isDataFlavorSupported(flavor)) throw new UnsupportedFlavorException(flavor);

    if (DataFlavor.stringFlavor.equals(flavor)) return obj.toString();

    return obj;

}

}

}

```

### 11.13.6 使用本地剪贴板传输对象引用

偶尔，你可能需要复制和粘贴一种不是系统剪贴板支持的数据类型，且不可序列化的类型。为了在同一个 JVM 内传输任意对象引用，请使用 MIME 类型：

点击此处查看代码图片

`application/x-java-local-objectref;class=className`

你需要为该类型定义一个 `Transferable` 包装器。该过程与前示例中的 `SerialTransferable` 包装器完全相似。

### `java.awt.datatransfer.Clipboard` 1.1

- `Clipboard(String name)`

  构造一个给定名称的本地剪贴板。

### 11.14 拖放

当你使用剪切和粘贴在两个程序之间传输信息时，剪贴板充当了中间媒介。拖放的隐喻去掉了中间人，让两个程序直接通信。Java 平台为拖放提供了基本支持。你可以在 Java 和原生应用程序之间执行拖放操作。本节将向你展示如何编写一个投放目标的 Java 应用程序以及一个作为拖放源的应用程序。

在深入研究 Java 平台对拖放的支持之前，让我们快速查看一下拖放用户界面。我们使用 Windows 资源管理器和 WordPad 程序作为示例——在其他平台上，你可以尝试本地具有拖放功能的可用程序。

你通过 `drag source` 内部的 `gesture` 启动一个 `drag operation`——首先选择一个或多个元素，然后将选择的内容拖离其初始位置。当你于接受投放操作的 `drop target` 上松开鼠标键时，该投放目标会向 `drag source` 查询有关被投放元素的信息，并执行适当的操作。例如，如果你从文件管理器将一个文件图标拖到目录图标上，该文件将移动到该目录中。然而，如果你将其拖到文本编辑器中，文本编辑器将打开该文件。（当然，这要求你使用支持拖放的文件管理器和文本编辑器，例如 Windows 中的 Explorer/WordPad 或 Gnome 中的 Nautilus/gedit。）

如果你在拖动时按住 `Ctrl` 键，投放操作的类型将从 `move action` 变为 `copy action`，并在目录中放置文件的副本。如果你同时按住 `Shift` 和 `Ctrl` 键，则会在目录中放置该文件的 `link`。（其他平台可能使用其他的组合键来实现这些操作。）

因此，有三种不同手势的投放操作类型：

- 移动（Move）
- 复制（Copy）
- 链接（Link）

链接操作的意图是建立指向投放元素的引用。此类链接通常需要宿主操作系统的支持（例如文件的符号链接，或文档组件的对象链接），并且在跨平台程序中通常没有意义。在本节中，我们重点关注使用拖放进行复制和移动。

拖动操作通常会有一些视觉反馈。至少光标形状会发生变化。当光标移动到可能的 `drop targets` 上时，光标形状会指示是否可以投放。如果可以投放，光标形状还会指示投放操作的类型。表 11.6 显示了几种投放光标形状。

![Image](img/00320.jpeg)

**表 11.6** 投放光标形状

你还可以拖动文件图标以外的其他元素。例如，你可以在 WordPad 或 gedit 中选择文本并拖动。尝试将文本片段放入接受投放的目标，观察它们的如何反应。

> **注意**
>
> 这个实验显示了拖放作为一种用户界面机制的缺点。用户很难预测他们可以拖动什么、可以拖到哪里，以及操作后会发生什么。因为默认的“移动”操作可能会删除原始文件，许多用户对尝试拖放感到谨慎是可以理解。

### 11.14.1 Swing 中的数据传输支持

从 Java SE 1.4 开始，多个 Swing 组件内置了对拖放的支持（参见表 11.7）。你可以从多个组件中拖选文本，并将文本放入文本组件中。为了向下兼容，你必须调用 `setDragEnabled` 方法来激活拖动。投放始终是开启的。

![Image](img/00321.jpeg)

**表 11.7** Swing 组件的数据传输支持

> **注意**
>
> `java.awt.dnd` 包提供了一个更底层的拖放 API，它是 Swing 拖放的基础。我们没有在书中讨论该 API。

程序 Listing 11.20 展示了这种行为。当你运行程序时，请注意以下点：

- 你可以在列表、表格或树中选择多个项并拖动它们（参见 Listing 11.21）。
- 从表格中拖动项有点笨拙。你需要先用鼠标选择，松开鼠标，再次点击，然后拖动。
- 当你将项放入文本区域时，你可以看到被拖动的信息是如何格式化的。表格单元格由制表符分隔，每个选中的行单独占一行（参见图 11.44）。

![Image](img/00322.jpeg)

**图 11.44** Swing 拖放测试程序

- 你只能从列表、表格、树、文件选择器或颜色选择器中复制而不能移动项。并不是数据模型都支持从列表、表格或树中移除项。你将在下一节中看到当数据模型可编辑时，如何实现此功能。
- 你无法拖入列表、表格、树或文件选择器。
- 如果你运行程序的两个副本，你可以从一个颜色选择器拖动颜色到另一个。
- 你无法从文本区域中拖出文本，因为我们没有对它调用 `setDragEnabled`。

Swing 包提供了一个可能很有用的机制，可以将组件快速转换为拖动源和投放目标。你可以为特定属性安装 `transfer handler`。例如，在我们的示例程序中，我们调用了：

```java
textField.setTransferHandler(new TransferHandler("background"))
```

现在你可以将颜色拖入文本字段，它的背景就会改变。当投放发生时，transfer handler 会检查数据类型中是否有表示为 `Color`。如果是，它会调用 `setBackground` 方法。

通过向文本字段安装此 transfer handler，你禁用了标准的 transfer handler。你不能再在文本字段中剪切、粘贴、拖动或投放文本。然而，你现在可以从此文本字段拖出颜色。你仍然需要选择一些文本来启动手势。当你拖动文本时，你会发现将其放入颜色选择器并将其改为文本字段的背景颜色。然而，你无法将文本放入区域。

**Listing 11.20** `dnd/SwingDTest.java`

```java
package dnd;

import java.awt.*;

import javax.swing.*;

/**
 * 此程序演示了 Swing 对拖放的基本支持。
 *
 * @version 1.1 2016-05-10
 * @author Horstmann
 */
public class SwingDTest {
    public static void main(String[] args) {
        EventQueue.invokeLater(() -> {
            JFrame frame = new SwingDFrame();
            frame.setTitle("SwingDTest");
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            frame.setVisible(true);
        });
    }
}
```

**Listing 11.21** `dnd/SampleComponents.java`

```java
package dnd;

import java.awt.*;

import javax.swing.*;
import javax.swing.tree.*;

public class SampleComponents {
    public static JTree tree() {
        DefaultMutableTreeNode root = new DefaultMutableTreeNode("World");
        DefaultMutableTreeNode country = new DefaultMutableTreeNode("USA");
        root.add(country);

        DefaultMutableTreeNode state = new DefaultMutableTreeNode("California");
        country.add(state);

        DefaultMutableTreeNode city = new DefaultMutableTreeNode("San Jose");
        state.add(city);

        city = new DefaultMutableTreeNode("Cupertino");
        state.add(city);

        state = new DefaultMutableTreeNode("Michigan");
        country.add(state);

        city = new DefaultMutableTreeNode("Ann Arbor");
        state.add(city);

        country = new DefaultMutableTreeNode("Germany");
        root.add(country);

        state = new DefaultMutableTreeNode("Schleswig-Holstein");
        country.add(state);

        city = new DefaultMutableTreeNode("Kiel");
        state.add(city);

        return new JTree(root);
    }

    public static JList<String> list() {
        String[] words = {
            "quick", "brown", "hungry", "wild", "silent", "huge", "private",
            "abstract", "static", "final"
        };

        DefaultListModel<String> model = new DefaultListModel<>();

        for (String word : words) {
            model.addElement(word);
        }

        return new JList<>(model);
    }

    public static JTable table() {
        Object[][] cells = {
            { "Mercury", 2440.0, 0, false, Color.YELLOW },
            { "Venus", 6052.0, 0, false, Color.YELLOW },
            { "Earth", 6378.0, 1, false, Color.BLUE },
            { "Mars", 3397.0, 2, false, Color.RED },
            { "Jupiter", 71492.0, 16, true, Color.ORANGE },
            { "Saturn", 60268.0, 18, true, Color.ORANGE },
            { "Uranus", 25559.0, 17, true, Color.BLUE },
            { "Neptune", 24766.0, 8, true, Color.BLUE },
            { "Pluto", 1137.0, 1, false, Color.BLACK }
        };

        String[] columnNames = {
            "Planet", "Radius", "Moons", "Gaseous", "Color"
        };

        return new JTable(cells, columnNames);
    }
}
```

### `javax.swing.JComponent` 1.2

- `void setTransferHandler(TransferHandler handler)` 1.4

  设置一个传输处理器以处理数据传输操作（剪切、复制、粘贴、拖动、投放）。

### `javax.swing.TransferHandler` 1.4

- `TransferHandler(String propertyName)`

  构造一个传输处理器，在执行数据传输操作时读取或写入给定名称的 JavaBeans 组件属性。

### `javax.swing.JFileChooser` 1.2

### `javax.swing.JColorChooser` 1.2

### `javax.swing.text.JTextComponent` 1.2

### `javax.swing.JList` 1.2

### `javax.swing.JTable` 1.2

### `javax.swing.JTree` 1.2

- `void setDragEnabled(boolean b)` 1.4

  启用或禁用从此组件拖出数据。

#### 11.14.2 拖动源

在上一节中，你已经看到了如何利用 Swing 的基本拖放支持。在本节中，我们将向你展示如何将任何组件配置为拖动源。在下一节中，我们将讨论投放目标，并提供一个既是图像源又是投放目标的示例组件。

要自定义 Swing 组件的拖放行为，请子类化 `TransferHandler` 类。首先，重写 `getSourceActions` 方法以指示你的组件支持哪些操作（复制、移动、链接）。接下来，重写 `createTransferable` 方法生成一个 `Transferable` 对象，其过程与你用于复制到剪贴板的过程相同。

在我们的示例程序中，我们从填充了图像图标的 `JList` 中拖出图像（参见图 11.45）。以下是 `createTransferable` 方法的实现。选中的图像被放入一个 `ImageTransferable` 包装器中。

```java
protected Transferable createTransferable(JComponent source) {
    JList list = (JList) source;
    int index = list.getSelectedIndex();

    if (index < 0) return null;

    ImageIcon icon = (ImageIcon) list.getModel().getElementAt(index);
    return new ImageTransferable(icon.getImage());
}
```

![Image](img/0323.jpeg)

**图 11.45** 列表拖放应用

在我们的示例中，幸运的是 `JList` 已经连接好用于启动拖动。你只需调用 `setDragEnabled` 方法即可激活该机制。如果你向一个不识别拖动手势的组件添加拖动支持，你需要自己启动传输。例如，以下是如何在 `JLabel` 上启动拖动：

```java
label.addMouseListener(new MouseAdapter() {
    public void mousePressed(MouseEvent evt) {
        int mode;

        if ((evt.getModifiers() & (InputEvent.CTRL_MASK | InputEvent.SHIFT_MASK)) != 0)
            mode = TransferHandler.COPY;
        else
            mode = TransferHandler.MOVE;

        JComponent comp = (JComponent) evt.getSource();
```



```java
TransferHandler th = comp.getTransferHandler();

th.exportAsDrag(comp, evt, mode);

}
});
```

在这里，当用户点击标签时，我们简单地开始传输。更复杂的实现会监控鼠标移动一小段距离的动作。

当用户完成投放动作时，源传输处理器的`exportDone`方法会被调用。在该方法中，如果用户执行了移动操作，则需要移除传输的对象。以下是图像列表的实现：

```java
protected void exportDone(JComponent source, Transferable data, int action)
{
    if (action == MOVE)
    {
        JList list = (JList) source;
        int index = list.getSelectedIndex();

        if (index < 0) return;

        DefaultListModel model = (DefaultListModel) list.getModel();
        model.remove(index);
    }
}
```

总结来说，为了将组件转换为拖动源，你需要添加传输处理器来指定：

- 哪些操作是允许
- 哪些数据被传输
- 移动操作后如何移除原始数据

此外，如果你的拖动源不是表 11.7 中列出的组件，你需要监控鼠标手势并启动传输。

### `javax.swing.TransferHandler`（1.4）

- `int getSourceActions(JComponent c)`：重写以返回允许的源操作（`COPY`、`MOVE`和`LINK`的组合）。
- `protected Transferable createTransferable(JComponent source)`：重写以创建数据的`Transferable`。
- `void exportAsDrag(JComponent comp, InputEvent e, int action)`：从组件启动拖动。动作为`COPY`、`MOVE`或`LINK`。
- `protected void exportDone(JComponent source, Transferable data, int action)`：在传输后重写以调整源。

#### 11.14.3 投放目标

在本节中，我们将向你展示如何实现投放目标。我们的示例再次是一个带有图像图标的`JList`。我们将添加投放支持，以便用户将图像投放到列表中。

要将组件转换为投放目标，请设置`TransferHandler`并实现`canImport`和`importData`方法。

![Image](img/00002.jpeg)

**注意**：你可以为`JFrame`添加传输处理器。这通常用于将文件投放应用程序。有效的投放位置包括框架装饰和菜单栏，但不包括框架内的组件（它们有自己的传输处理器）。

`canImport`方法在用户移动过投放目标组件时会被持续调用。如果允许投放，则返回`true`。此信息会影响提供投放是否允许视觉反馈的光标。

`canImport`方法有一个类型为`TransferHandler.TransferSupport`的参数。通过该参数，你可以获取用户选择的操作、投放位置以及要传输的数据。（在 Java SE 6 之前调用的是不同的`canImport`方法，它只提供数据类型列表。）

在`canImport`方法中，你还可以覆盖用户的投放操作。例如，如果用户选择了移动操作但移除原始文件是不恰的，你可以强制传输处理器使用复制操作。

这里是一个典型的示例。图像列表组件接受文件列表和图像的投放。然而，如果将文件列表拖入组件中，用户选择的`MOVE`操作将被更改为`COPY`操作，这样图像文件就不会被删除。

```java
public boolean canImport(TransferSupport support)
{
    if (support.isDataFlavorSupported(DataFlavor.javaFileListFlavor))
    {
        if (support.getUserDropAction() == MOVE) support.setDropAction(COPY);

        return true;
    }
    else return support.isDataFlavorSupported(DataFlavor.imageFlavor);
}
```

```java
else return support.isDataFlavorSupported(DataFlavor.imageFlavor);
}

public boolean importData(TransferSupport support)
{
    ImageList list = (ImageList) support.getComponent();
    DefaultListModel<ImageIcon> model =
        (DefaultListModel<ImageIcon>) list.getModel();
    Transferable transferable = support.getTransferable();
    List<DataFlavor> flavors =
        Arrays.asList(transferable.getTransferDataFlavors());
    List<Image> images = new ArrayList<>();

    try
    {
        if (flavors.contains(DataFlavor.javaFileListFlavor))
        {
            @SuppressWarnings("unchecked")
            List<File> fileList =
                (List<File>) transferable.getTransferData(
                    DataFlavor.javaFileListFlavor);

            for (File f : fileList)
            {
                try
                {
                    images.add(ImageIO.read(f));
                }
                catch (IOException ex)
                {
                    // couldn't read image--skip
                }
            }
        }
        else if (flavors.contains(DataFlavor.imageFlavor))
        {
            images.add((Image) transferable.getTransferData(
                DataFlavor.imageFlavor));
        }

        int index;

        if (support.isDrop())
        {
            JList.DropLocation location =
                (JList.DropLocation) support.getDropLocation();
            index = location.getIndex();

            if (!location.isInsert()) model.remove(index); // replace
        }
        else index = model.size();

        for (Image image : images)
        {
            model.add(index, new ImageIcon(image));
            index++;
        }

        return true;
    }
    catch (IOException | UnsupportedFlavorException ex)
    {
        return false;
    }
}
```

### `javax.swing.TransferHandler`

- `boolean canImport(TransferSupport support)`：重写以指示目标组件是否可以接受`TransferSupport`参数描述的拖放操作。
- `boolean importData(TransferSupport support)`：重写以执行由`TransferSupport`参数描述的放落或粘贴手势，如果导入成功则返回`true`。

### `javax.swing.JFrame`

- `void setTransferHandler(TransferHandler handler)`：设置一个传输处理器来处理放落和粘贴操作。

### `javax.swing.JList`

### `javax.swing.JTable`

### `javax.swing.JTree`

### `javax.swing.text.JTextComponent`

- `void setDropMode(DropMode mode)`：将此组件的放落模式设置为表 11.8 中指定的值之一。

### `javax.swing.TransferHandler.TransferSupport`

- `Component getComponent()`：获取传输的目标组件。
- `DataFlavor[] getDataFlavors()`：获取要传输数据的数据类型。
- `boolean isDrop()`：如果此传输是放落则返回`true`，如果是粘贴则返回`false`。
- `int getUserDropAction()`：获取用户选择的放落动作（`MOVE`、`COPY`或`LINK`）。
- `int getSourceDropActions()`：获取拖放源允许的放落动作。
- `int getDropAction()`
- `void setDropAction(int action)`：获取或设置传输的放落动作。初始为用户的放落动作，但可以被传输处理器覆盖。
- `DropLocation getDropLocation()`：获取放落的位置，如果此传输不是放落则抛出`IllegalStateException`。

### `javax.swing.TransferHandler.DropLocation`

- `Point getDropPoint()`：获取目标组件中放落的鼠标位置。

### `javax.swing.JList.DropLocation`

- `boolean isInsert()`：如果数据要插入到指定位置之前，则返回`true`；如果要替换现有数据则返回`false`。
- `int getIndex()`：获取插入或替换的模型索引。

### `javax.swing.JTable.DropLocation`

- `boolean isInsertRow()`
- `boolean isInsertColumn()`：如果数据要插入到行或列之前，则返回`true`。
- `int getRow()`
- `int getColumn()`：获取插入或替换的模型行或列索引，如果放落发生在空白区域则返回`-1`。

### `javax.swing.JTree.DropLocation`

- `TreePath getPath()`
- `int getChildIndex()`：返回树路径和子节点，它们结合目标组件的放落模式共同定义了放落位置，如下所示。

![Image](img/0326.jpeg)

## 11.15 平台集成

我们通过几项让 Java 应用程序看起来像原生应用程序的功能结束本章。启动界面（splash screen）功能允许你的应用程序在虚拟机启动时显示启动界面。最后，你现在可以使用系统托盘并像许多原生应用程序一样在其放置图标。

### 11.15.1 启动界面

Java 应用程序的一个常见问题是启动时间过长。虚拟机需要一些时间加载所有类，特别是对于需要引入大量 Swing 和 AWT 库代码的 Swing 应用程序。用户不喜欢花费长时间显示初始界面的程序，如果他们怀疑首次启动失败，甚至可能会尝试多次启动应用程序。解决办法是使用启动界面——一个快速出现的小窗口，告诉用户应用程序已成功启动。

当然，你可以在`main`方法启动时立即弹出一个窗口。然而，`main`方法只有在类加载器加载了所有依赖类后才会启动，这可能需要一些时间。相反，你可以请求虚拟机在启动时立即显示图像。指定该图像有两种机制。你可以使用`-splash`命令行选项：

点击此处查看代码图像

`java -splash:myimage.png MyApp`

或者，你可以在 JAR 文件的清单中指定它：

点击此处查看代码图像

```text
Main-Class: MyApp
SplashScreen-Image: myimage.gif
```

图像会立即显示，并在第一个 AWT 窗口可见时自动消失。你可以提供任何 GIF、JPEG 或 PNG 图像。支持动画（GIF）和透明度（PNG）。

如果你的应用程序在到达`main`方法后就可以就绪，可以跳过本节的剩余部分。然而，许多应用程序使用插件架构，其中小型核心在启动时加载一组插件。Eclipse 和 NetBeans 是典型的例子。在这种情况下，你可以在启动界面上指示加载进度。

有两种方法。你可以直接在启动界面上绘图，也可以用一个内容相同的无边框框架替换它然后在框架内部绘图。我们的示例程序展示了这两种技术。

要在启动界面上直接绘图，请获取启动界面的引用并获取其图形上下文和尺寸：

```java
SplashScreen splash = SplashScreen.getSplashScreen();

Graphics2D g2 = splash.createGraphics();

Rectangle bounds = splash.getBounds();
```

你现在可以按照通常的方式进行绘图。完成后，调用`update`以确保绘图已刷新。我们的示例程序绘制了一个简单的进度条，如图 11.47 左图所示。

点击此处查看代码图像

```java
g.fillRect(x, y, width * percent / 100, height);

splash.update();
```

![Image](img/00327.jpeg)

**图 11.47** 初始启动界面和一个无边框的后续窗口

---

![Image](img/00002.jpeg) 备注

启动界面是一个单例对象。你不能自己构造一个它。如果没有在命令行或清单文件（manifest）中设置启动界面，则`getSplashScreen`方法将返回`null`。

---

直接在启动界面上绘图有一个缺点：计算所有像素位置非常繁琐，而且你的进度指示器将无法与原生进度条匹配。为了避免这些问题，你可以在`main`方法启动后立即将初始启动界面替换为与其大小和内容相同的后续窗口。该窗口可以包含任意 Swing 组件。

我们在列表 11.23 中的示例程序演示了这种技术。图 11.47 中的右图图像显示了一个无边框的框架，其包含一个绘制了启动界面并装有`JProgressBar`的面板。现在，我们拥有对 Swing API 的完全访问权限，并且可以轻松地添加消息字符串，而无需费心处理像素位置。

注意，我们不需要移除初始启动界面。一旦后续窗口变为可见，它就会自动移除。

---

![Image](img/00004.jpeg) 警告

遗憾的是，当启动界面被后续窗口替换时，会出现明显的闪烁。

---

**列表 11.23** `splashScreen/SplashScreenTest.java`

点击此处查看代码图像

```java
package splashScreen;

import java.awt.*;

import java.util.List;

import javax.swing.*;

/**
 * 此程序演示了启动界面 API。
 * @version 1.01 2016-05-10
 * @author Cay Horstmann
 */
public class SplashScreenTest
{
    private static final int DEFAULT_WIDTH = 300;
    private static final int DEFAULT_HEIGHT = 300;
    private static SplashScreen splash;

    private static void drawOnSplash(int percent)
    {
        Rectangle bounds = splash.getBounds();
        Graphics2D g = splash.createGraphics();
        int height = 20;
        int x = 2;
        int y = bounds.height - height - 2;
    }
}
```



```java
int width = bounds.width - 4;

Color brightPurple = new Color(76, 36, 121);

g.setColor(brightPurple);

g.fillRect(x, y, width * percent / 100, height);

splash.update();

}

/**

 * 此方法在启动界面上绘图。

 */

private static void init()

{

    splash = SplashScreen.getSplashScreen();

    if (splash == null)

    {

        System.err.println("你是否通过 splash 或在清单文件中指定了启动界面?");

        System.exit(1);

    }

    try

    {

        for (int i = 0; i<= 100; i++)

        {

            drawOnSplash(i);

            Thread.sleep(100); // 模拟工作

        }

    }

    catch (InterruptedException e)

    {

    }

}

/**

 * 此方法显示一个与启动界面图像相同的框架。

 */

private static void init2()

{

    final Image img = new ImageIcon(splash.getImageURL()).getImage();

    final JFrame splashFrame = new JFrame();

    splashFrame.setUndecorated(true);

    final JPanel splashPanel = new JPanel()

    {

        public void paintComponent(Graphics g)

        {

            g.drawImage(img, 0, 0, null);

        }

    };

    final JProgressBar progressBar = new JProgressBar();

    progressBar.setStringPainted(true);

    splashPanel.setLayout(new BorderLayout());

    splashPanel.add(progressBar, BorderLayout.SOUTH);

    splashFrame.add(splashPanel);

    splashFrame.setBounds(splash.getBounds());

    splashFrame.setVisible(true);

    new SwingWorker<Void, Integer>()

    {

        protected Void doInBackground() throws Exception

        {

            try

            {

                for (int i = 0; i <= 100; i++)

                {

                    publish(i);

                    Thread.sleep(100);

                }

            }

            catch (InterruptedException e)

            {

            }

            return null;

        }

        protected void process(List<Integer> chunks)

        {

            for (Integer chunk : chunks)

            {

                progressBar.setString("Loading module " + chunk);

                progressBar.setValue(chunk);

                splashPanel.repaint(); // 因为 img 是异步加载的

            }

        }

        protected void done()

        {

            splashFrame.setVisible(false);

            JFrame frame = new JFrame();

            frame.setSize(DEFAULT_WIDTH, DEFAULT_HEIGHT);

            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

            frame.setTitle("SplashScreenTest");

            frame.setVisible(true);

        }

    }.execute();

}

public static void main(String[] args)

{

    init();

    EventQueue.invokeLater(() -> init2());

}

}
```

---

## `java.awt.SplashScreen` 6

- `static SplashScreen getSplashScreen()` 获取启动界面引用，如果没有启动界面则返回 `null`。
- `URL getImageURL()`
- `void setImageURL(URL imageURL)` 获取或设置启动界面的 URL。设置图像会更新启动界面。
- `Rectangle getBounds()` 获取启动界面的边界。
- `Graphics2D createGraphics()` 获取用于在启动界面绘制的上下文。
- `void update()` 更新启动界面的显示。
- `void close()` 关闭启动界面。当第一个 AWT 变为可见时，启动界面会自动关闭。

## 11.15.2 启动桌面应用程序

`java.awt.Desktop` 类允许你启动默认浏览器和电子邮件程序。你还可以使用注册了文件类型的应用程序打开、编辑和打印文件。

该 API 非常直接。首先，调用静态 `isDesktopSupported` 方法。如果它返回 `true`，则当前平台支持启动桌面应用程序。然后调用静态 `getDesktop` 方法获取 `Desktop` 实例。

并不是所有的桌面环境都支持所有的操作。例如，在 Linux 的 Gnome 桌面上，可以打开文件，但无法打印它们。（文件关联中没有“动词”支持）。要找出你的平台支持哪些功能，请调用 `isSupported` 方法并传入一个 `Desktop.Action` 枚举中的值。我们的示例程序包含了如下测试：

```java
if (desktop.isSupported(Desktop.Action.PRINT)) printButton.setEnabled(true);
```

要打开、编辑或打印文件，首先要检查该操作是否被支持，然后调用 `open`、`edit` 或 `print` 方法。要启动浏览器，请传递一个 `URI`。（关于 URI 的更多信息，请参阅第 4 章）。你可以直接使用一个包含 `http` 或 `https` URL 的字符串来调用 `URI` 构造函数。

要启动默认电子邮件程序，你需要构建一个特定格式的 `URI`，即：

`mailto:recipient?query`

在这里，`recipient` 是收件者的电子邮件地址，例如 `president@whitehouse.gov`，`query` 包含用 `&` 分隔的 `name=value` 值对，且值经过了百分比编码。（百分比编码在本质上与第 4 章中描述的 URL 编码算法相同，但空格被编码为 `%20` 而不是 `+`）。例如：`subject=dinner%20RSVP&bcc=putin%40kremvax.ru`。该格式记录在 RFC 2368（`www.ietf.org/rfc/rfc2368.txt`）中。遗憾的是，`URI` 类对 `mailto` URI 一无所知，因此你必须自己组装并编码。

我们在代码列表 11.24 中的示例程序允许你打开、编辑或打印你选择的文件、浏览 URL 或启动你的电子邮件程序（参见图 11.48）。

![Image](img/00328.jpeg)

**图 11.48** 启动桌面应用程序

**代码列表 11.24** `desktopApp/DesktopAppFrame.java`

点击此处查看代码图像

---

```java
package desktopApp;

import java.awt.*;

import java.io.*;

import java.net.*;

import javax.swing.*;

class DesktopAppFrame extends JFrame

{

    public DesktopAppFrame()

    {

        setLayout(new GridBagLayout());

        final JFileChooser chooser = new JFileChooser();

        JButton fileChooserButton = new JButton("...");

        final JTextField fileField = new JTextField(20);

        fileField.setEditable(false);

        JButton openButton = new JButton("Open");

        JButton editButton = new JButton("Edit");

        JButton printButton = new JButton("Print");

        final JTextField browseField = new JTextField();

        JButton browseButton = new JButton("Browse");

        final JTextField toField = new JTextField();

        final JTextField subjectField = new JTextField();

        JButton mailButton = new JButton("Mail");

        openButton.setEnabled(false);

        editButton.setEnabled(false);

        printButton.setEnabled(false);

        browseButton.setEnabled(false);

        mailButton.setEnabled(false);

        if (Desktop.isDesktopSupported())

        {

            Desktop desktop = Desktop.getDesktop();

            if (desktop.isSupported(Desktop.OPEN)) openButton.setEnabled(true);

            if (desktop.isSupported(Desktop.EDIT)) editButton.setEnabled(true);

            if (desktop.isSupported(Desktop.PRINT)) printButton.setEnabled(true);

            if (desktop.isSupported(Desktop.BROWSE)) browseButton.setEnabled(true);

            if (desktop.isSupported(Desktop.MAIL)) mailButton.setEnabled(true);

        }

        fileChooserButton.addActionListener(event ->

        {

            if (chooser.showDialog(DesktopAppFrame.this) == JFileChooser.APPROVE_OPTION)

                fileField.setText(chooser.getSelectedFile().getAbsolutePath());

        });

        openButton.addActionListener(event ->

        {

            try {

                Desktop.getDesktop().open(chooser.getSelectedFile());

            } catch (IOException ex)

            {

                ex.printStackTrace();

            }

        });

        editButton.addActionListener(event ->

        {

            try {

                Desktop.getDesktop().edit(chooser.getSelectedFile());

            } catch (IOException ex)

            {

                ex.printStackTrace();

            }

        });

        printButton.addActionListener(event ->

        {

            try {

                Desktop.getDesktop().print(chooser.getSelectedFile());

            } catch (IOException ex)

            {

                ex.printStackTrace();

            }

        });

        browseButton.addActionListener(event ->

        {

            try {

                Desktop.getDesktop().browse(new URI(browseField.getText()));

            } catch (URISyntaxException | IOException ex)

            {

                ex.printStackTrace();

            }

        });

        mailButton.addActionListener(event ->

        {

            try {

                String subject = percentEncode(subjectField.getText());

                URI uri = new URI("mailto:" + toField.getText() + "?subject=" + subject);

                System.out.println(uri);

                Desktop.getDesktop().mail(uri);

            } catch (URISyntaxException | IOException ex)

            {

                ex.printStackTrace();

            }

        });

        JPanel buttonPanel = new JPanel();
```



```java
((FlowLayout) buttonPanel.getLayout()).setgap(2);

buttonPanel.add(openButton);

buttonPanel.add(editButton);

buttonPanel.add(printButton);

add(fileChooserButton, new GBC(0, 0).anchor(GBC.EAST).insets(2));

add(fileField, new GBC(1, 0).fill(GBC.HORIZONTAL));

add(buttonPanel, new GBC(2, 0).anchor(GBC.WEST).insets(2));

add(browseField, new GBC(1, 1).fill(GBC.HORIZONTAL));

add(browseButton, new GBC(2, 1).anchor(GBC.WEST).insets(2));

add(new JLabel("To:"), new GBC(0, 2).anchor(GBC.EAST).insets(5, 2, 2));

add(toField, new GBC(1, 2).fill(GBC.HORIZONTAL));

add(mailButton, new GBC(2, 2).anchor(GBC.WEST).insets(2));

add(new JLabel("Subject:"), new GBC(0, 3).anchor(GBC.EAST).insets(5, 2, 2));

add(subjectField, new GBC(1, 3).fill(GBC.HORIZONTAL));

pack();

}

private static String percentEncode(String s)

{

try

{

return URLEncoder.encode(s, "UTF-8").replaceAll("[+]", "%20");

}

catch (UnsupportedEncodingException ex)

{

return null; // UTF-8 is always supported

}

}

}

```

许多桌面环境都有一个区域用于显示后台运行并偶尔向用户通知事件的程序图标。在 Windows 中，该区域被称为 `system tray`（系统托盘），这些图标被称为 `tray icons`（托盘图标）。Java API 采用了相同的术语。此类程序的一个典型示例是检查软件更新的监控程序。如果有新的可用更新，监控程序可以更改图标的外观，或在图标附近显示消息。

坦率地说，系统托盘有些过度使用了，当计算机用户发现又一个托盘图标时，通常不会感到快乐。我们的示例系统托盘应用程序——一个发放虚拟幸运饼的程序——也并非例外。

`java.awt.SystemTray` 类是连接系统托盘的跨平台通道。与上一节讨论的 `Desktop` 类一样，你首先要调用静态方法 `isSupported` 来检查本地 Java 平台是否支持系统托盘。如果是，你可以通过调用静态方法 `getSystemTray` 获取一个 `SystemTray` 单例。

`SystemTray` 类最重要的方法是 `add` 方法，它允许你添加一个 `TrayIcon` 实例。托盘图标有三个关键属性：

- 图标图像
- 当鼠标悬停在图标上时可见的提示（tooltip）
- 用户用鼠标右键点击图标时显示的弹出菜单

弹出菜单是 AWT 库中 `PopupMenu` 类的实例，代表一个原生弹出菜单，而不是 Swing 菜单。使用 AWT `MenuItem` 实例填充它，每个实例都拥有一个与 Swing 对应项完全相同的动作监听器。

最后，托盘图标可以向用户显示通知（参见图 11.49）。调用 `TrayIcon` 类的 `displayMessage` 方法并指定标题、消息和消息类型。点击此处查看代码图像。

```java
trayIcon.displayMessage("Your Fortune", fortunes.get(index), TrayIcon.MessageType.INFO);
```

![Image](img/00329.jpeg)

**图 11.49** 来自托盘图标的通知

列表 11.25 显示了将幸运饼图标放入系统托盘的应用程序。该程序读取幸运饼文件（来自古老的 UNIX `fortune` 程序），其中每条幸运运都以包含包含 `%` 字符的行结束。它每隔十秒显示一次消息。幸运的是，它有一个带有退出应用程序命令的弹出菜单。如果所有的托盘图标都如此体贴该好了！

**列表 11.25** `systemTray/SystemTrayTest.java`

点击此处查看代码图像。

---

```java
package systemTray;

import java.awt.*;
import java.io.*;
import java.util.*;
import java.util.List;
import javax.swing.*;
import javax.swing.Timer;

/**
 * 此程序演示了系统托盘 API。
 * @version 1.02 2016-05-10
 * @author Cay Horstmann
 */
public class SystemTrayTest
{
    public static void main(String[] args)
    {
        SystemTrayApp app = new SystemTrayApp();
        app.init();
    }
}

class SystemTrayApp
{
    public void init()
    {
        final TrayIcon trayIcon;

        if (!SystemTray.isSupported())
        {
            System.err.println("System tray is not supported.");
            return;
        }

        SystemTray tray = SystemTray.getSystemTray();
        Image image = new ImageIcon(getClass().getResource("cookie.png")).getImage();
        PopupMenu popup = new PopupMenu();
        MenuItem exitItem = new MenuItem("Exit");

        exitItem.addActionListener(event -> System.exit(0));
        popup.add(exitItem);

        trayIcon = new TrayIcon(image, "Your Fortune", popup);
        trayIcon.AutoSize(true);

        trayIcon.addActionListener(event -> {
            trayIcon.displayMessage(
                "How do I turn this off?",
                "Right-click on the fortune cookie and select.",
                TrayIcon.MessageType.INFO
            );
        });

        try
        {
            tray.add(trayIcon);
        }
        catch (AWTException e)
        {
            System.err.println("TrayIcon could not be added.");
            return;
        }

        final List<String> fortunes = readFortunes();

        Timer timer = new Timer(10000, event -> {
            int index = (int) (fortunes.size() * Math.random());
            trayIcon.displayMessage(
                "Your Fortune",
                fortunes.get(index),
                TrayIcon.MessageType.INFO
            );
        });

        timer.start();
    }

    private List<String> readFortunes()
    {
        List<String> fortunes = new ArrayList<>();

        try (InputStream inStream = getClass().getResourceAsStream("fortunes"))
        {
            Scanner in = new Scanner(inStream, "UTF-8");
            StringBuilder fortune = new StringBuilder();

            while (in.hasNextLine())
            {
                String line = in.nextLine();

                if (line.equals("%"))
                {
                    fortunes.add(fortune.toString());
                    fortune = new StringBuilder();
                }
                else
                {
                    fortune.append(line);
                }
            }
        }
        catch (IOException e)
        {
            e.printStackTrace();
        }

        return fortunes;
    }
}
```

## 12. 从 Java 程序中调用 C 函数

- 12.1 数值参数和返回值
- 12.2 字符串参数
- 12.3 访问字段
- 12.4 编码签名
- 12.5 调用 Java 方法
- 12.6 访问数组元素
- 12.7 错误处理
- 12.8 使用调用接口 (Invocation API)
- 12.9 完整示例：访问 Windows 注册表

虽然原则上“100% 纯 Java”的方案很好，但在某些情况下，你可能想要编写（或使用）用其他语言编写的代码。（这类代码通常被称为 `native` 代码。）

特别在 Java 早期，许多人认为使用 `C` 或 `C++` 来加速 Java 应用程序的关键部分是一个好主意。然而，在实践中，这种做法很少有用。1996 年 JavaOne 大会的一场演讲清楚地说明了这一点。太阳微系统公司（Sun Microsystems）加密库的实现者报告说，纯 Java 平台实现的加密函数已经足够足够。虽然代码的速度确实没有 `C` 实现那么快，但事实证明这并不重要。Java 平台的实现远比网络 I/O 快得多，而这才是真正的瓶颈。

当然，使用原生代码（native）也有缺点。如果你的应用程序某部分是用另一种语言编写的，你必须为你想要支持的每个平台提供一个独立的原生库。用 `C` 或 `C++` 编写的代码无法防止因无效指针使用导致的内存覆盖。编写可能会破坏你的程序或感染操作系统的原生方法是轻而易举的。

因此，我们建议只在需要时才使用原生代码。特别是，有三个原因使得原生代码可能是正确的选择：

- 你的应用程序需要访问 Java 平台无法访问的系统功能或设备。
- 你在另一种语言中拥有大量经过测试和调试的代码，并且你知道如何将其迁移到所有预期的目标平台。
- 你通过基准测试发现，Java 代码比另一种语言的等效代码要慢得多。

Java 平台有一个用于与原生 `C` 代码交互的 API，称为 Java Native Interface（`JNI`）。我们将在本章中讨论 JNI 编程。

> ![Image](img/00005.jpeg) C++ 注意：
>
> 你也可以使用 `C++` 代替 `C` 来编写原生方法。这有几个优点——类型检查稍微严格，且访问 `JNI` 函数稍微方便。然而，`JNI` 不支持 Java 类和 `C++` 类之间的任何映射。

### 12.1 从 Java 程序中调用 C 函数

假设你有一个 `C` 函数可以实现你喜欢的功能，并且出于某种原因，你不想费事在 Java 中重新实现它。为了说明起，我们将从一个打印问候信息的简单 `C` 函数开始。

Java 编程语言使用 `native` 关键字来表示原生方法，你显然需要将该方法放在一个类中。结果如代码列表 12.1 所示。

`native` 关键字提醒编译器该方法将在外部定义。当然，原生方法不包含任何 Java 编程语言的代码，且方法头后面紧跟一个结束分号。因此，原生方法的声明看起来与抽象方法的声明相似。

**代码列表 12.1** `helloNative/HelloNative.java`

```java
/**
 * @version 1.11 2007-10-26
 * @author Cay Horstmann
 */
class HelloNative
{
    public static native void greeting();
}
```

> ![Image](img/00002.jpeg) 注意
>
> 与上一章一样，为了保持示例简单，我们在这里没有使用包（packages）。

在这个特定的示例中，原生方法也被声明为 `static`。原生方法可以是静态的，也可以是非静态的。我们将从静态方法开始，因为我们还不想处理参数传递。

你实际上可以编译这个类，但如果你尝试在程序中使用它，虚拟机会告诉你它不知道如何找到 `greeting`——报告一个 `UnsatisfiedLinkError`。要实现原生代码，请编写一个 `C` 函数。你必须按照虚拟机期望的方式精确命名它。规则如下：

1. 使用完整的 Java 名称，例如 `HelloNative`。如果类在包中，请在前面加上包名。
2. 将每个点 `.` 替换为下划线 `_`，并附加 `Java_`。例如 `Java_com_horstmann_HelloNative`。
3. 如果类名包含不是字母或数字的字符——即大于 `\u007F` 的 Unicode 字符——将它们替换为 `_xxxx`，其中 `xxxx` 是该字符 Unicode 值的四位数序列。

要重载方法——如果你有多个同名方法——你必须附加双下划线，后跟参数类型。（我们稍后会描述参数类型的编码。）

实际上没有人手动执行这些操作；而是运行 `javah` 工具。要使用 `javah`，首先编译代码列表 12.1 中的源文件：

```bash
javac HelloNative.java
```

接下来，调用 `javah`，它会生成一个头文件，如代码列表 12.2 所示。`javah` 可执行文件可以在 `bin` 目录下找到。使用类名调用它：

```bash
javah HelloNative
```

**代码列表 12.2** `HelloNative.h`

```c
/* DO NOT EDIT THIS FILE - it machine generated */

#include <jni.h>

/* Header for class HelloNative */

#ifndef _Included_HelloNative

#define _Included_HelloNative

#ifdef __cplusplus

extern "C" {

#endif

/**
 * Class: HelloNative
 * Method: greeting
 * Signature: ()V
 */

JNIEXPORT void JNICALL Java_HelloNative_greeting(JNIEnv *, jclass);

#ifdef __cplusplus

}

#endif

#endif
```

如你所见，此文件包含函数 `Java_HelloNative_greeting` 的声明。（`JNIEXPORT` 和 `JNICALL` 宏在头文件 `jni.h` 中。它们表示来自动态加载库的导出函数的编译器相关限定符。）

现在，只需将头文件的函数原型复制到源文件中，并提供函数的实现代码，如代码列表 12.3 所示。

**代码列表 12.3** `HelloNative.c`

```c
/*
 * @version 1.10 1997-07-01
 * @author Cay Horstmann
 */

#include "HelloNative.h"

#include <stdio.h>
```



```c
JNIEXPORT void JNICALL Java_HelloNative_greeting(JNIEnv* env, jclass cl)
{
    printf("Hello Native World!\n");
}
```

在这个简单的函数中，请忽略`env`和`cl`参数。你将在稍后看到它们的用法。

![Image](img/00005.jpeg)

### C++ 注意事项

你可以使用 C++ 来实现原生方法。但是，你必须将实现原生方法的函数声明为`extern "C"`。（这可以防止 C++ 编译器对方法名进行“符号修饰”（mangling）。）例如：

```cpp
extern "C"

JNIEXPORT void JNICALL Java_HelloNative_greeting(JNIEnv* env, jclass cl)
{
   cout << "Hello, Native World!" << endl;
}
```

将原生 C 代码编译成动态加载库。具体细节取决于你的编译器。

例如，在 Linux 上使用 GNU C 编译器，请使用这些命令：

```bash
gcc -fPIC -I jdk/include -I jdk/include/linux -shared -o libHelloNative.so HelloNative.c
```

在 Solaris 操作系统下使用 Sun 编译器，命令是：

```bash
cc -G -I jdk/include -I jdk/include/solaris -o libHelloNative.so HelloNative.c
```

在 Windows 下使用 Microsoft 编译器，命令是：

```bash
cl -I jdk\include -I jdk\include\win32 -LD HelloNative.c -FeHelloNative.dll
```

在这里，`jdk`是包含 JDK 的目录。

![Image](img/00003.jpeg)

### 提示

如果你从命令行 shell 使用 Microsoft 编译器，请先运行如`vsvars32.bat`或`vcvarsall.bat`的批处理文件。该处理文件会设置编译器所需的路径和环境变量。你可以在`c:\Program Files\Microsoft Visual Studio 14.0\Common7\Tools`目录或类似的复杂路径中找到它。详情请查看 Visual Studio 文档。

你也可以使用从`www.cygwin.com`免费提供的 Cygwin 编程环境。它包含了 GNU C 编译器以及在 Windows 上进行 UNIX 风格编程的库。使用 Cygwin 时，使用命令：

```bash
gcc -mno-cygwin -D __int64="long long" -I jdk/include/ -I jdk/include/win32
   -shared -Wl,--add-stdcall-alias -o HelloNative.dll HelloNative.c
```

在单行中输入整个命令。

![Image](img/00002.jpeg)

### 注意

Windows 头文件`jni_md.h`包含类型声明：

```c
typedef __int64 jlong;
```

它是特定于 Microsoft 编译器的。如果你使用 GNU 编译器，可能需要编辑该文件，例如：

```c
#ifdef __GNUC__
   typedef long long jlong;
#else
   typedef __int64 jlong;
#endif
```

或者，在编译时使用`-D __int64="long long"`，如示例中的编译器调用所示。

最后，在你的程序中添加对`System.loadLibrary`方法的调用。为了确保虚拟机在类第一次使用之前加载库，请使用静态初始化块，如列表 12.4 所示。

图 12.1 提供了原生代码的处理概述。

![Image](img/00330.jpeg)

**图 12.1** 处理原生代码

当你编译并运行此程序后，终端窗口将显示“Hello, Native World!”消息。

**代码 12.4** `helloNative/HelloNativeTest.java`

```java
/**
 * @version 1.11 2007-10-26
 * @author Cay Horstmann
 */
class HelloNativeTest
{
  public static void main(String[] args)
  {
      HelloNative.greeting();
  }

  static
  {
      System.loadLibrary("HelloNative");
  }
}
```

![Image](img/00002.jpeg)

### 注意

如果你运行 Linux，你必须将当前目录添加到库路径。可以设置`LD_LIBRARY_PATH`环境变量：

```bash
export LD_LIBRARY_PATH=.:$LD_LIBRARY_PATH
```

或者设置`java.library.path`属性：

```bash
java -Djava.library.path=. HelloNative
```

当然，这并不令人惊艳。然而，请记住这是跨语言连接的第一步。总结来说，连接原生方法遵循以下步骤：

1. 在 Java 中声明原生方法。
2. 运行`javah`生成头文件。
3. 在 C 中实现该方法。
4. 将其编译为共享库。
5. 在 Java 中加载库。

```c
14      sprintf(fmt, "%%%d.%df", width, precision);
15      ret = printf(fmt, x);
16      fflush(stdout);
17      return ret;
18    }
```

该函数仅在变量`fmt`中组装格式字符串`"%w.%p.f"`，然后调用`printf`。它返回打印的字符数。

列表 12.7 显示了演示`Printf1`类的测试程序。

**列表 12.7** `printf1/Printf1Test.java`

```java
1    /**
  * @version 1.10 1997-07-01
  * @author Cay Horstmann
  */
class Printf1Test
{
    public static void main(String[] args)
    {
        int count = Printf1.print(8, 4, 3.14);
        count += Printf1.print(8, 4, count);
        System.out.println();

        for (int i = 0; i < count; i++)
            System.out.print("-");

        System.out.println();
    }
}
```

### 12.3 字符串参数

接下来，我们想要考虑如何在原生方法之间传输字符串。字符串在两种语言中非常不同：在 Java 中，字符串是 UTF-16 码点的序列，而 C 字符串是空终止终止的字节序列。JNI 有两组函数用于操作字符串：一组将 Java 字符串转换为“修改后的 UTF-8”字节序列，另一组则将它们转换为 UTF-16 值数组——即`jchar`数组。（UTF-8、“修改后的 UTF-8”和 UTF-16 格式在第 2 章中讨论过。记住，UTF-8 和“修改后的 UTF-8”编码保持 ASCII 字符不变，但所有其他 Unicode 字符都被编码为多字节序列。）

![Image](img/00002.jpeg)

### 注意

标准的 UTF-8 编码和“修改后的 UTF-8”编码仅在代码高于 0xFFFF 的“补充”字符上不同。在标准的 UTF-8 编码中，这些字符被编码为 4 字节序列。在“修改后的”编码中，每个这样的字符首先被编码为 UTF-16 编码中的一对“代理字符”，然后每个代理字符都用 UTF-8 编码，总共产生 6 个字节。这种做法很笨拙，但这是一个历史性的偶然——当编写 JVM 规范时，Unicode 仍然仅限于 16 位。

如果你的 C 代码已经使用了 Unicode，你可能会想要使用第二组转换函数。另一方面，如果你所有的字符串都受限于 ASCII 字符，你就可以使用“修改后的 UTF-8”转换函数。

带有`String`参数的原生方法实际上接收一个名为`jstring`的不透明类型的值。返回类型为`String`的原生方法必须返回一个`jstring`类型的值。JNI 函数读取并构造这些`jstring`对象。例如，`NewStringUTF`函数根据包含 ASCII 字符的`char`数组，或更通用地说，“修改后的 UTF-8”编码的字节序列创建一个新的`jstring`对象。

JNI 函数有一种相当奇怪的调用约定。这里有一个对`NewStringUTF`函数的调用：

```c
JNIEXPORT jstraing JNICALL Java_HelloNative_getGreeting(JNIEnv* env, jclass cl)
{
   jstring jstr;
   char greeting[] = "Hello, Native World\n";
   jstr = (*env)->NewStringUTF(env, greeting);
   return jstr;
}
```

![Image](img/00002.jpeg)

### 注意

除非另有说明，本章所有代码都是 C 代码。

所有对 JNI 函数的调用都使用`env`指针，它是每个原生方法的第一个参数。`env`指针是一个指向函数指针表的指针（见图 12.2）。因此，你必须在每个 JNI 调用前加上`(*env)->`以实际对函数指针解引用。此外，`env`是每个 JNI 函数的第一个参数。

![Image](img/00332.jpeg)

**图 12.2** `env`指针

![Image](img/00005.jpeg)

### C++ 注意

在 C++ 中访问 JNI 函数更简单。`JNIEnv`类的 C++ 版本具有内联成员函数，可以为你处理函数指针的查找。例如，你可以这样调用`NewStringUTF`函数：

```c
jstr = env->NewStringUTF(greeting);
```

注意你在调用的参数列表中省略了`JNIEnv`指针。

`NewStringUTF`函数允许你构造一个新的`jstring`。要读取现有`jstring`对象的内容，请使用`GetStringChars`。该函数返回一个指向“修改后的 UTF-8”字符表示的指针。由于 Java 字符串是不可变的，虚拟机自由选择这种字符编码，因此非常重要的是你要调用`ReleaseStringChars`。另一方面，如果虚拟机使用 UTF-16 或 UTF-32 字符作为内部表示，该函数将分配一个新的内存块。虚拟机必须知道你何时结束使用该字符串以便对其进行垃圾回收（垃圾回收在单独线程中运行）。因此，你必须调用`ReleaseUTF`函数。或者，你可以通过调用`GetStringRegion`或`GetStringUTFRegion`方法提供自己的缓冲区来持有字符串。最后，该函数返回所需的字节数。

![Image](img/00002.jpeg)

### 注意

你可以在`http://docs.oracle.com/javase/7/docs/techNotes/guides/jni`找到 API。

### 从 C 代码访问字符串

- `jstring NewStringUTF(JNIEnv* env, const char bytes[])`根据空终止修改后的 UTF-8 字节序列返回 Java 字符串对象，如果无法构造则返回`NULL`。
- `jsize GetStringUTength(JNIEnv* env, jstring string)`返回用于编码所需的字节数（不包括零字节）。
- `const jchar* GetStringChars(JNIEnv* env, jstring string, jboolean* isCopy)`返回指向字符串的 UTF-8 编码的指针，如果无法构造字符数组则返回`NULL`。该指针在调用`ReleaseStringChars`之前有效。`isCopy`指向`jboolean`，如果进行了拷贝则填充为`JNI_TRUE`，否则为`JNI_FALSE`。
- `void ReleaseStringChars(JNIEnv* env, jstring string, const jbyte bytes[])`通知虚拟机原生代码不再需要通过`bytes`（`GetStringChars`返回的指针）访问 Java 字符串。
- `void GetStringRegion(JNIEnv *env, jstring string, jsize start, jsize length, jchar *buffer)`将 UTF-16 双字节序列复制到大小至少为 2 × `length`的用户提供的缓冲区。
- `void GetStringUTFRegion(JNIEnv *env, jstring string, jsize start, jsize length, jbyte *buffer)`将修改后的 UTF-8 字节序列复制到用户提供的缓冲区。缓冲区必须足够容纳这些字节。在坏的情况下，会复制 3 × `length`个字节。
- `jstring NewString(JNIEnv* env, const jchar chars[], jsize length)`根据 Unicode 字符串返回新的 Java 字符串对象，如果无法构造则返回`NULL`。
- `jsize GetStringLength(JNIEnv* env, jstring string)`返回字符串中的字符数。

返回字符串的 Unicode 编码指针，如果无法构建字符数组，则返回`NULL`。该指针在调用`ReleaseStringChars`之前有效。`isCopy`可能是`NULL`或者指向一个`jboolean`，如果进行了复制，则该值被填充为`JNI_TRUE`，否则填充为`JNI_FALSE`。

- `void ReleaseStringChars(JNIEnv* env, jstring string, const jchar chars[])`

通知虚拟机原生代码不再需要通过`chars`（由`GetStringChars`返回的指针）访问 Java 字符串。

---

让我们让这些函数派上用场，编写一个调用 C 函数`sprintf`的类。我们希望像列表 12.8 所示那样调用该函数。

**列表 12.8** `printf2/Printf2Test.java`

```java
/**
 * @version 1.10 1997-07-01
 * @author Cay Horstmann
 */
class Printf2Test {
    public static void main(String[] args) {
        double price = 44.95;
        double tax = 7.75;
        double amountDue = price * (1 + tax / 100);
        String s = Printf2.sprint("Amount due = %8.2f", amountDue);
        System.out.println(s);
    }
}
```

列表 12.9 显示了带有原生`sprint`方法的类。

**列表 12.9** `printf2/Printf2.java`

```java
/**
 * @version 1.10 1997-07-01
 * @author Cay Horstmann
 */
class Printf2 {
    public static native String sprint(String format,

    static {
        System.loadLibrary("Printf2");
    }
}
```

因此，格式化浮点数的 C 函数原型如下：

```c
JNIEXPORT jstring JNICALL Java_Printf2_sprint(JNIEnv* env, jclass cl, jstring format, jdouble x)
```

列表 12.10 显示了 C 实现代码。请注意调用`GetStringUTFChars`来读取格式参数，调用`NewStringUTF`生成返回值，以及调用`ReleaseStringUTFChars`通知虚拟机不再需要访问该字符串。

**列表 12.10** `printf2/Printf2.c`

```c
/**



`@version 1.10 1997-07-01`

`@author Cay Horstmann`

```c
#include "Printf2.h"
#include <string.h>
#include <stdlib.h>
#include <float.h>
```

`@param format` 一个包含 `printf` 格式说明符（例如 `"%8.2f"`）的字符串。子字符串 `"%%"` 将跳过。

`@return` 指向格式说明符的指针（跳过 `'%'`），如果不是唯一的格式说明符则返回 `NULL`。

```c
char* find_format(const char[]) {
    char* p;
    char* q;
    p = strchr(format, '%');
    while (p != NULL && *(p + 1) == '%') /* 跳过 %% */
        p = strchr(p + 2, '%');
    if (p == NULL) return NULL; /* 现在检查 % 是否唯一 */
    p++;
    q = strchr(p, '%');
    while (q != NULL && *(q + 1) == '%') /* 跳过 %% */
        q = strchr(q + 2, '%');
    if (q != NULL) return NULL; /* 不唯一 */
    q = p + strspn(p, " -0+#"); /* 跳过标志 */
    q += strspn(q, "0123456789"); /* 跳过字段宽度 */
    if (*q == '.') { q += strspn(q, "0123456789"); } /* 跳过精度 */
    if (strchr("eEfG", *q) == NULL) return NULL; /* 不是浮点数格式 */
    return p;
}

JNIEXPORT jstring JNICALL Java_Printf2_sprint(JNIEnv* env, jclass cl, jstring format, jdouble x) {
    const char* cformat;
    char* fmt;
    jstring ret;
    cformat = (*env)->GetStringUTFChars(env, format, NULL);
    fmt = find_format(cformat);
    if (fmt == NULL)
        ret = format;
    else {
        char* cret;
        int width = atoi(fmt);
        if (width == 0) width = DBL_DIG + 10;
        cret = (char*) malloc(strlen(cformat) + width);
        sprintf(cret, cformat, x);
        ret = (*env)->NewStringUTF(env, cret);
        free(cret);
    }
    (*env)->ReleaseStringUTFChars(env, format, cformat);
    return ret;
}
```

在这个函数中，我们选择保持简单。我们稍后会展示如何处理异常。

## 12.4 访问字段

在虚拟机中，我们现在考虑字段。到目前为止看到的所有方法都是静态的；非静态方法则对对象进行操作。

### 12.4.1 访问字段

为了了解如何从原生方法访问字段，我们将实现 `salary` 方法。以下是 Java 代码：

```java
public void raiseSalary(double byPercent) {
    salary *= 1 + byPercent / 100;
}
```

让我们将其重写为原生方法。注意第二个参数。它不再是 `jclass` 类型，而是 `jobject` 类型。事实上，它是 `this` 的等效物。静态方法获取类的引用，而非静态方法则获取隐式 `this` 参数的引用。

现在我们访问隐式参数的 `salary` 字段。在 Java 1.0 的“原始”Java 到 C 绑定中，这是很容易的——程序员可以直接访问对象数据。然而，直接访问要求所有虚拟机都暴露其数据布局。出于此原因，JNI 要求程序员通过调用 JNI 函数来获取和设置数据字段的值。

在我们的情况下，我们需要使用 `GetDoubleField` 和 `SetDoubleField` 函数，因为 `salary` 的类型是 `double`。还有其他函数——`GetIntField/SetIntField`、`GetObjectField/SetObjectField` 以及针对其他字段类型的函数。通用语法为：

```c
x = (*env)->GetXxxField(env, this_obj, fieldID);
(*env)->SetXxxField(env, this_obj, fieldID, x);
```

在这里，`fieldID` 是一个特殊类型 `jfieldID` 的值，用于标识结构中的字段，并且 *Xxx* 代表 Java 数据类型（`Object`、`Boolean`、`Byte` 等）。要获取 `fieldID`，你必须先获取表示类的值，你可以通过两种方式之一实现。`GetObjectClass` 函数返回任何对象的类。例如：

```c
jclass class_Employee = (*env)->GetObjectClass(env, this_obj);
```

`FindClass` 函数允许你用字符串指定类名（奇怪的是，它使用 `/` 字符而不是点作为包名分隔符）。

```c
jclass class_String = (*env)->FindClass(env, "java/lang/String");
```

使用 `GetFieldID` 函数来获取 `fieldID`。你必须提供字段名称及其 `signature`（签名），它是该类型的编码。例如，这里是获取 `salary` 字段 ID 的代码：

```c
jfieldID id_salary = (*env)->GetFieldID(env, class_Employee, "salary", "D");
```

字符串 `"D"` 表示类型 `double`。你将在下一节中学习签名编码的完整规则。

你可能在认为访问数据字段非常复杂。JNI 的设计者并不希望直接暴露数据字段，因此他们必须提供用于获取和设置字段值的函数。为了最小化这些函数的开销，从字段名计算字段 ID（这是最耗性能的一步）被提取出来作为一个独立的步骤。这意味着，如果你反复获取和设置某个特定字段的值，你只需要支付一次计算字段标识符的代价。

让我们将所有部分组合在一起。以下代码作为原生方法重新实现了 `raiseSalary` 方法：

```c
JNIEXPORT void JNICALL Java_Employee_raiseSalary(JNIEnv* env, jobject this_obj, jdouble byPercent)
{
    /* get the class */
    jclass class_Employee = (*env)->GetObjectClass(env, this_obj);
    /* get the field ID */
    jfieldID id_salary = (*env)->GetFieldID(env, class_Employee, "salary", "D");
    /* get the field value */
    jdouble salary = (*env)->GetDoubleField(env, this_obj, id_salary);
    salary *= 1 + byPercent / 100;
    /* set the field value */
    (*env)->SetDoubleField(env, this_obj, id_salary, salary);
}
```

**注意**

类引用仅在原生方法返回之前有效。你不能在代码中缓存 `GetObjectClass` 的返回值。*不要*存储类引用以供在后续的方法调用中重用。你必须在每次原生方法执行时都调用 `GetObjectClass`。如果这无法接受，可以通过调用 `NewGlobalRef` 来锁定该引用：

```c
static jclass class_X = 0;
static jfieldID id_a;
. . .
if (class_X == 0)
{
    jclass cx = (*env)->GetObjectClass(env, obj);
    class_X = (*env)->NewGlobalRef(env, cx);
    id_a = (*env)->GetFieldID(env, cls, "a", ". . .");
}
```

现在你可以在随后的调用中使用类引用和字段 ID。当你使用完该类后，请确保调用：

```c
(*env)->DeleteGlobalRef(env, class_X);
```

示例 12.11 和 12.12 展示了测试程序的 Java 代码和 `Employee` 类的代码。示例 12.13 包含了原生 `raiseSalary` 方法的 C 代码。

**示例 12.11** `employee/EmployeeTest.java`

```java
1    /**
2    * @version 1.10 1999-11-13
3    * @author Cay Horstmann
4    */
5
6    public class EmployeeTest
7    {
8      public static void main(String[] args)
9      {
10          Employee[] staff = new Employee[3];
11
12          staff[0] = new Employee("Harry Hacker", 35000);
13          staff[1] = new Employee("Carl Cracker", 75000);
14          staff[2] = new Employee("Tony Tester", 38000);
15
16          for (Employee e : staff)
17            e.raiseSalary(5);
18          for (Employee e : staff)
19            e.print();
20      }
21    }
```

**示例 12.12** `employee/Employee.java`

```java
1    /**
2    * @version 1.10 1999-11-13
3    * @author Cay Horstmann
4    */
5
6    public class Employee
7    {
8      private String name;
9      private double salary;
10
11     public native void raiseSalary(double byPercent);
12
13     public Employee(String n, double s)
14     {
15         name = n;
16         salary = s;
17     }
18
19     public void print()
20     {
21         System.out.println(name + " " + salary);
22     }
23
24     static
25     {
26         System.loadLibrary("Employee");
27     }
28    }
```

**示例 12.13** `employee/Employee.c`

```c
1    /**
2    * @version 1.10 1999-11-13
3    * @author Cay Horstmann
4    */
5
6    #include "Employee.h"
7
8    #include <stdio.h>
9
10   JNIEXPORT void JNICALL Java_Employee_raiseSalary(JNIEnv* env, jobject this_obj, jdouble byPercent)
11   {
12       /* get the class */
13       jclass class_Employee = (*env)->GetObjectClass(env, this_obj);
14       /* get the field ID */
15       jfieldID id_salary = (*env)->GetFieldID(env, class_Employee, "salary", "D");
16       /* get the field value */
17       jdouble salary = (*env)->GetDoubleField(env, this_obj, id_salary);
18
19       salary *= 1 + byPercent / 100;
20
21       /* set the field value */
22       (*env)->SetDoubleField(env, this_obj, id_salary, salary);
23   }
```

### 12.4 访问静态字段

访问静态字段与访问实例字段相似。使用 `GetStaticFieldID` 和 `GetStaticXxxField` 函数，它们与非静态函数几乎相同，但有两个区别：

- 你没有对象，必须使用 `FindClass` 而不是 `GetObjectClass`。
- 访问字段时需要提供类，而不是实例。

例如，这里是获取 `System.out` 的方法：

```c
/* get the class */
jclass class_System = (*env)->FindClass(env, "lang/System");
/* get the field ID */
jfieldID id_out = (*env)->GetStaticFieldID(env, class_System, "out", "Ljava/io/PrintStream;");
/* get the field value */
jobject obj_out = (*env)->GetStaticObjectField(env, class_System, id_out);
```



### 访问字段

- `jfieldID GetStaticFieldID(JNIEnv *env, jclass cl, const char name[], const char fieldSignature[])` 返回类的字段标识符。
- `Xxx GetStaticXxxField(JNIEnv *env, jclass cl, jfieldID id)` 返回静态字段的值。类型 `Xxx` 为 `Object`、`Boolean`、`Byte`、`Char`、`Short`、`Int`、`Long`、`Float` 或 `Double` 之一。
- `void SetStaticXxxField(JNIEnv *env, jclass cl, jfieldID id, Xxx value)` 为静态字段设置新值。类型 `Xxx` 为 `Object`、`Boolean`、`Byte`、`Char`、`Short`、`Int`、`Long`、`Float` 或 `Double` 之一。

### 12.5 签名编码

为了访问实例字段并调用 Java 语言定义的方法，你需要学习数据类型和方法签名的“编码”规则。（方法签名描述了参数和返回类型。）以下是编码方案：

![Image](img/00334.jpeg)

要描述数组类型，请使用 `[`。例如，一个字符串数组是：

```text
[Ljava/lang/String;
```

一个 `float[][]` 被编码为：

```text
[[F
```

对于方法的完整签名，请在一对括号内列出参数类型，然后列出返回类型。例如，接收两个整数并返回一个整数的方法被编码为：

`(II)I`

第 12.3 节中的“String 参数”，在第 949 页上的 `sprint` 方法的混淆签名为：

点击此处查看代码图像

`(Ljava/lang/String;D)Ljava/lang/String;`

也就是说，该方法接收一个 `String` 和一个 `double` 并返回一个 `String`。

请注意 `L` 表达式末尾的分号 `;` 是类型表达式的终止符，而不是参数之间的分隔符。例如，构造函数：

点击此处查看代码图像

`Employee(java.lang.String, double, java.util.Date)`

签名为：

点击此处查看代码图像

`"(Ljava/lang/String;DLjava/util/Date;)V"`

请注意 `D` 和 `Ljava/util/Date;` 之间没有分隔符。同样注意，在这种编码方案中，你必须使用 `/` 代替 `.` 来分隔包名和类名。末尾的 `V` 表示返回类型为 `void`。尽管在 Java 中不需要为构造函数指定返回类型，但你需要在虚拟机签名中添加一个 `V`。

> **提示**
>
> 你可以使用带有 `-s` 选项的 `javap` 命令从类文件中生成方法签名。例如，运行：
>
> ```bash
> javap -s -private Employee
> ```
>
> 你将获得以下输出，显示所有字段和方法的签名：
>
> 点击此处查看代码图像
>
> ```text
> Compiled from "Employee.java"
>
> public class Employee extends java.lang.Object{
>
>   private java.lang.String name;
>
>   Signature: Ljava/lang/String;
>
>   private double salary;
>
>   Signature: D
>
> public Employee(java.lang.String, double);
>
>   Signature: (Ljava/lang/String;D)V
>
> public native void raiseSalary(double);
>
>   Signature: (D)V
>
> public void print();
>
>   Signature: ()V
>
> static {};
>
>   Signature: ()V
>
> }
> ```

> **注意**
>
> 完全没有任何理由强迫程序员在签名中使用这种混淆方案。原生调用机制的设计者本可以同样容易地编写一个函数，读取以 Java 编程语言风格的签名（例如 `void(int,java.lang.String)`），并将其编码为他们偏好的任何内部表示。话虽如此，使用混淆签名让你能够参与到接近虚拟机编程的神秘之中。

### 12.6 调用 Java 方法

当然，Java 编程语言函数可以调用 C 函数——这就是原生方法的用处。我们能反过来操作吗？我们到底为什么要这样做呢？通常情况下，原生方法需要向传递给它的对象请求服务。我们将首先向你展示如何处理实例方法，然后是处理静态方法。

#### 12.6.1 实例方法

作为一个从原生代码调用 Java 方法的示例，让我们增强 `Printf` 类并添加一个工作原理与 C 函数 `fprintf` 的方法。也就是说，它应该能够在任意的 `PrintWriter` 对象上打印字符串。以下是该方法在 Java 中的定义：

点击此处查看代码图像

```java
class Printf3
{
  public native static void fprint(PrintWriter out, String s, double x);

  ...
}
```

我们首先将要打印的字符串组装成 `String` 对象 `str`，正如我们已经实现的 `sprint` 方法中所做的那样。然后，从实现原生方法的 C 函数中，我们将调用 `PrintWriter` 类的 `print` 方法。

你可以使用函数调用从 C 调用任何 Java 方法：

点击此处查看代码图像

```c
(*env)->CallXxxMethod(env, *implicit parameter*, *methodID*, *explicit parameters*)
```

根据方法的返回类型，将 `Xxx` 替换为 `Void`、`Int`、`Object` 等。正如你需要一个 `fieldID` 来访问对象的字段，你需要一个方法 ID（method ID）来调用方法。要获取方法 ID，请调用 JNI 函数 `GetMethodID` 并提供类、方法名和方法签名。

在示例中，我们想要获取 `PrintWriter` 类 `print` 方法的 ID。`PrintWriter` 类有多个名为 `print` 的重载方法。由于这个原因，我们还必须提供字符串 `"(java/lang/String;)V"`。注意 `D` 和 `Ljava/util/Date;` 之间没有分隔符。同样注意，在这种编码方案中，你必须使用 `/` 代替 `.` 来分隔包名和类名。末尾的 `V` 表示返回类型为 `void`。尽管在 Java 中不需要为构造函数指定返回类型，但你需要在虚拟机签名中添加一个 `V`。

#### 12.6.2 静态方法

从原生方法调用静态方法与调用实例方法类似。有两个不同：

- 使用 `GetStaticMethodID` 和 `CallStatic` 函数。
- 调用方法时提供类对象而非隐式参数。

作为一个示例，让我们从原生方法调用静态方法 `System.getProperty("class.path")`。该调用的返回值是类路径的字符串。

首先，我们需要找到使用的类。由于我们没有 `System` 类的对象，因此使用 `FindClass` 而不是 `GetObjectClass`。这里是代码：

点击此处查看代码图像

```c
jclass class_System = (*env)->FindClass(env, "java/lang/System");
```

接下来，我们需要静态方法 `getProperty` 的 ID。该方法的编码签名是 `(Ljava/lang/String;)Ljava/lang/String;`，因为参数和返回值都是字符串。因此，我们如下所示获取方法 ID：

点击此处查看代码图像

```c
jmethodID id_getProperty = (*env)->GetStaticMethodID(
    env,
    class_System,
    "getProperty",
    "(Ljava/lang/String;)Ljava/lang/String;"
);
```

最后，我们可以进行调用。注意类对象被传递给了 `CallStaticObjectMethod` 函数。

点击此处查看代码图像

```c
jobject obj_ret = (*env)->CallStaticObjectMethod(
    env,
    class_System,
    id_getProperty,
    (*env)->NewStringUTF(env, "java.class.path")
);
```

该方法的返回类型为 `jobject`。如果我们想将其作为字符串进行处理，必须将其强制转换为 `jstring`。

点击此处查看代码图片

```cpp
jstring str_ret = (jstring) obj_ret;
```

> **C++ 注意：**
>
> 在 C 语言中，类型 `jstring` 和 `jclass` 以及稍后引入的数组类型，在类型上都等同于 `jobject`。因此，前一个示例中的类型转换在 C 中并不是严格必要的。但在 C++ 中，这些类型被定义为指向“虚拟类”的指针，具有正确的继承层次结构。例如，在 C++ 中，将 `jstring` 赋值给 `jobject` 是合法的，无需转换，但从 `jobject` 赋值给 `jstring` 则需要类型转换。

#### 12.6.3 构造函数

原生方法可以通过调用构造函数来创建一个新的 Java 对象。通过调用 `NewObject` 函数来执行构造函数。

点击此处查看代码图片

```cpp
jobject obj_new = (*env)->NewObject(env, class, methodID, construction parameters);
```

你可以通过 `GetMethodID` 函数获取此调用所需的方法 ID，方法是将方法名指定为 `"<init>"` 以及构造函数的编码后的签名（返回类型为 `void`）。例如，这里展示了原生方法如何创建一个 `FileOutputStream` 对象：

点击此处查看代码图片

```cpp
const char[] fileName = ". . .";

jstring str_fileName = (*env)->NewStringUTF(env, fileName);

jclass class_FileOutputStream =
    (*env)->FindClass(env, "java/io/FileOutputStream");

jmethodID id_FileOutputStream =
    (*env)->GetMethodID(
        env,
        class_FileOutputStream,
        ">init<",
        "(Ljava/lang/String;)V"
    );

jobject obj_stream =
    (*env)->NewObject(
        env,
        class_FileOutputStream,
        id_FileOutputStream,
        str_fileName
    );
```

请注意，构造函数的签名接受一个类型为 `java.lang.String` 的参数，并且返回类型为 `void`。

#### 12.6.4 备用方法调用

可以使用 JNI 函数的几种变体从原生代码调用 Java 方法。这些函数不像我们已经讨论过的函数那样重要，但有时很有用。

`CallNonvirtualXxxMethod` 函数接收一个隐式参数（方法 ID）、一个类对象（该对象必须对应隐式参数的父类）以及显式参数。该函数调用指定类中的方法版本，跳过了常规的动态分发机制。

所有调用函数都有带有后缀“A”和“V”的版本，它们通过数组或 `va_list`（如 C 头文件 `stdarg.h` 中定义）来接收显式参数。

**列表 12.14** `printf3/Printf3Test.java`

点击此处查看代码图片

```java
import java.io.*;

/**
 * @version 1.10 1997-07-01
 * @author Cay Horstmann
 */

class Printf3Test
{
    public static void main(String[] args)
    {
        double price = 44.95;
        double tax = 7.75;
        double amountDue = price * (1 + tax / 100);
        PrintWriter out = new PrintWriter(System.out);
        Printf3.fprint(out, "Amount due = %8.2f\n", amountDue);
        out.flush();
    }
}
```

**列表 12.15** `printf3/Printf3.java`

点击此处查看代码图片

```java
import java.io.*;

/**
 * @version 1.10 1997-07-01
 * @author Cay Horstmann
 */

class Printf3
{
    public static native void f(PrintWriter out, String format, double x);
    static {
```



`System.loadLibrary("Printf3");`

**列表 12.16** `printf3/Printf3.c`

```c
/**
 * @version 1.10 1997-07-01
 * @author Cay Horstmann
 */
#include "Printf3.h"
#include <string.h>
#include <stdlib.h>
#include <float.h>

/**
 * @param format 一个包含 printf 格式说明符的字符串（例如 "%8.2f"）。子字符串 "%%" 将跳过。
 * @return 指向格式说明符的指针（跳过 '%'），或者如果没有唯一的说明符，则返回 NULL。
 */
char* find_format(const char format[])
{
    char* p;
    char* q;

    p = strchr(format, '%');
    while (p != NULL && *(p + 1) == '%') // skip %%
      p = strchr(p + 2, '%');
    if (p == NULL) return NULL;

    p++;
    while (*p && !isspace(*p)) // skip flags
      p++;
    if (*p != '.') return p;

    p++;
    while (*p && isdigit(*p)) // skip precision
      p++;
    return p;
}

JNIEXPORT void JNIC Java_Printf3_fprint(JNIEnv* env, jclass cl,
      jobject out, jstring format, jdouble x)
{
    const char* cformat;
    char* fmt;
    jstring str;
    jclass class_PrintWriter;
    jmethodID id_print;

    cformat = (*env)->GetStringChars(env, format, NULL);
    fmt = find_format(cformat);
    if (fmt != NULL)
    {
        int width = atoi(fmt);
        if (width <= 0) width = 10;
        char* cstr = (char*) malloc(width);
        sprintf(cstr, "%.*f", x);
        str = (*env)->NewStringUTF(env, cstr);
        free(cstr);
    }
    else
    {
        str = (*env)->NewStringUTF(env, "0");
    }
    (*env)->ReleaseStringChars(env, format, cformat);

    // 获取类
    class_PrintWriter = (*env)->GetObjectClass(env, out);
    // 获取方法 ID
    id_print = (*env)->GetMethodID(env, class_PrintWriter, "print", "(Ljava/lang/String;)V");
    // 调用方法
    (*env)->CallVoidMethod(env, out, id_print, str);
}
```

### 执行 Java 方法

`jmethodID GetMethodID(JNIEnv* env, jclass cl, const char name[], const char methodSignature[])` 返回类中的方法标识符。

`CallMethod`、`CallMethodA`、`CallMethodV` 调用方法。返回类型可以是 `Object`、`Boolean`、`Byte`、`Char`、`Short`、`Int`、`Long`、`Float` 或 `Double`。第一个函数具有变数量参数——只需在方法 ID 之后追加方法参数。第二个函数通过 `jvalue` 数组接收方法参数，其中 `jvalue` 是如下定义的联合体：

```c
typedef union jvalue
{
  jboolean z;
  jbyte b;
  jchar c;
  jshort s;
  jint i;
  jlong j;
  jfloat f;
  jdouble d;
  jobject l;
} jvalue;
```

第三个函数通过 `va_list` 接收方法参数，如 C 头文件 `stdarg.h` 中定义。

`CallNonvirtualXxxMethod(JNIEnv* env, jobject obj, jclass cl, jmethodID id, args)`

`CallNonvirtualXxxMethodA(JNIEnv* env, jobject obj, jclass cl, jmethodID id, jvalue args[])`

`CallNonvirtualXxxMethodV(JNIEnv* env, jobject obj, jclass cl, jmethodID id, va_list args)`

调用一个方法，跳过动态分发。返回类型 `Xxx` 是 `Object`、`Boolean`、`Byte`、`Char`、`Short`、`Int`、`Long`、`Float` 或 `Double`。第一个函数具有可变参数——只需在方法 ID 后追加方法参数。第二个函数通过 `jvalue` 数组接收方法参数。第三个函数在 `va_list` 中接收方法参数，该类型在 C 头文件 `stdarg.h` 中定义。

- `jmethodID GetStaticMethodID(JNIEnv *env, jclass cl, const char name[], const char methodSignature[])`

返回类中静态方法的标识符。

- `Xxx CallStaticMethod(JNIEnv *env, jclass cl, jmethodID id, args)`
- `Xxx CallStaticMethodA(JNIEnv *env, jclass cl, jmethodID id, jvalue args[])`
- `Xxx CallStaticMethodV(JNIEnv *env, jclass cl, jmethodID id, va_list args)`

调用静态方法。返回类型 `Xxx` 是 `Object`、`Boolean`、`Byte`、`Char`、`Short`、`Int`、`Long`、`Float` 或 `Double`。第一个函数具有可变参数——只需在方法 ID 后追加方法参数。第二个函数通过 `jvalue` 数组接收方法参数。第三个函数在 `va_list` 中接收方法参数，该类型在 C 头文件 `stdarg.h` 中定义。

- `jobject NewObject(JNIEnv *env, jclass cl, jmethodID id, args)`
- `jobject NewObjectA(JNIEnv *env, jclass cl, jmethodID id, jvalue args[])`
- `jobject NewObjectV(JNIEnv *env, jclass cl, jmethodID id, va_list args)`

调用构造函数。方法 ID 通过 `GetMethodID` 获取，其方法名为 `"<init>"`，返回类型为 `void`。第一个函数具有可变参数——只需在方法 ID 后追加方法参数。第二个函数通过 `jvalue` 数组接收方法参数。第三个函数在 `va_list` 中接收方法参数，该类型在 C 头文件 `stdarg.h` 中定义。

### 12.7 访问数组元素

Java 编程语言的所有数组类型都有对应的 C 类型，如表 12.2 所示。

**表 12.2** Java 数组类型与 C 类型的对应关系

C++ 注意：

在 C 中，所有这些数组类型实际上都是 `jobject` 的类型定义。但在 C++ 中，它们按照图 12.3 所示的继承层次结构排列。类型 `jarray` 表示通用数组。

**图 12.3** 数组类型的继承层次结构

`GetArrayLength` 函数返回数组的长度。

```c
jarray array = . . .;
jsize length = (*env)->GetArrayLength(env, array);
```

如何访问数组中的元素取决于数组存储的是对象还是原始类型的值（`bool`、`char` 或数值类型）。要访问对象数组中的元素，使用 `GetObjectArrayElement` 和 `SetObjectArrayElement` 方法。

```c
jobjectArray array = . . .;
int i, j;
jobject x = (*env)->GetObjectArrayElement(env, array, i);
(*env)->SetObjectArrayElement(env, array, j, x);
```

尽管这种方法很简单，但显然效率很低；你希望能够直接访问数组元素，特别是在进行向量和矩阵计算时。

`GetArrayElements` 函数返回一个指向数组起始元素的 C 指针。与普通字符串一样，你必须记得调用相应的 `ReleaseArrayElements` 函数告诉虚拟机你不再需要该指针。在这里，类型 `Xxx` 必须是原始类型——即不是 `Object`。然后你就可以直接读取和写入数组元素。然而，由于指针可能指向副本，你所做的任何更改在调用相应的 `ReleaseArrayElements` 函数后才能保证反映在原始数组中！

注意：

你可以通过将指向 `jboolean` 变量的指针作为第三参数传递给 `GetArrayElements` 方法来判断数组是否为副本。如果是副本，该变量将被填充为 `JNI_TRUE`。如果你对该信息感兴趣，只需传递一个 `NULL` 指针。

这是一个示例，将 `double` 值数组中的所有元素乘以一个常数。我们获取指向 Java 数组的 C 指针 `a`，然后通过 `a[i]` 访问单个元素。

```c
jdoubleArray array_a = . . .;
double scaleFactor = . . .;
double* a = (*env)->GetArrayElements(array_a, NULL);
for (i = 0; i < (*env)->GetArrayLength(env, array_a); i++)
    a[i] *= scaleFactor;
(*env)->ReleaseArrayElements(array_a, a, 0);
```

虚拟机是否复制数组取决于它如何分配数组。某些“拷贝”垃圾回收器会移动并更新对象引用。`GetArrayElements` 方法用于“拷贝”`boolean` 值的数组。该策略与“固定”（pinning）数组不兼容。

注意：

在 JVM 实现中，`boolean` 数组被表示为紧凑的 32 位字。`GetBooleanArrayElements` 将它们拷贝到解包的数组中。

要访问大数组的少数几个元素，使用 `GetArrayRegion` 和 `SetArrayRegion` 方法，这些方法可以从 Java 数组并回复制范围内的元素。要在原生代码中创建新数组，请指定长度、数组类型和初始元素（通常为 `NULL`）。这里：

```c
jclass class_Employee = (*env)->FindClass("Employee");
jobjectArray array_e = (*env)->NewObjectArray(100, class_Employee, NULL);
```

原始类型数组更简单：只需提供长度。

```c
jdoubleArray array_d = (*env)->NewDoubleArray(env, 100);
```

数组随后被填充为零。

以下方法用于处理“直接缓冲区”：

```c
jobject NewDirectByteBuffer(JNIEnv* env, void* address, jlong capacity);
void* GetDirectBufferAddress(JNIEnv* env, jobject buf);
jlong GetDirectBufferCapacity(JNIEnv* env, jobject buf);
```

直接缓冲区用于 `java.nio` 包以支持更高效的输入输出操作，并减少原生与 Java 数组之间的数据拷贝。

### 操作 Java 数组

- `jsize GetArrayLength(JNIEnv *env, jarray array)`

返回数组中的元素数量。

- `jobject GetObjectArrayElement(JNIEnv *env, jobjectArray array, jsize index)`

返回数组元素的值。

- `void SetObjectArrayElement(JNIEnv *env, jobjectArray array, jsize index, jobject value)`

设置数组元素为新的。

- `Xxx GetArrayElements(JNIEnv *env, jarray array, jboolean* isCopy)`

产生 Java 数组元素的 C 指针。字段类型 `Xxx` 是 `Boolean`、`Byte`、`Char`、`Short`、`Int`、`Long`、`Float` 或 `Double`。在不再需要该指针时必须传递给 `ReleaseArrayElements`。`isCopy` 要为 `NULL` 或指向一个 `jboolean`，如果进行了拷贝，则被填充为 `JNI_TRUE`，否则为 `JNI_FALSE`。

- `void ReleaseArrayElements(JNIEnv *env, jarray array, Xxx elems[], jint mode)`

通知虚拟机通过 `GetXxxArrayElements` 获取的指针不再被需要。`mode` 的值可以是 `0`（在更新数组元素后释放 `elems` 缓冲区）、`JNI_COMMIT`（在更新数组元素后不释放 `elems` 缓冲区）或 `JNI_ABORT`（在不更新数组元素释放 `elems` 缓冲区）。

- `void GetXxxArrayRegion(JNIEnv *env, jarray array, jint start, jint length, Xxx elems[])`

将元素从 Java 数组复制到 C 数组。字段类型 `Xxx` 为 `Boolean`、`Byte`、`Char`、`Short`、`Int`、`Long`、`Float` 或 `Double` 之一。

- `void SetXxxArrayRegion(JNIEnv *env, jarray array, jint start, jint length, Xxx elems[])`

将元素从 C 数组复制到 Java 数组。字段类型 `Xxx` 为 `Boolean`、`Byte`、`Char`、`Short`、`Int`、`Long`、`Float` 或 `Double` 之一。

### 12.8 错误处理

原生方法对 Java 程序构成了重大的安全风险。C 运行时系统对数组越界错误、通过错误的指针进行间接访问等没有保护。原生方法的程序员处理所有错误情况以维护 Java 平台的完整性，这一点尤为重要。特别是当你的原生方法诊断出它无法处理的问题时，它应该向 Java 虚拟机报告该问题。

通常情况下，在这种情况下你会抛出一个异常。然而，C 并没有异常机制。相反，你必须调用 `Throw` 或 `ThrowNew` 函数来创建一个新的异常对象。当原生方法退出时，Java 虚拟机会抛出该异常。

要使用 `Throw` 函数，请调用 `NewObject` 创建一个 `Throwable` 子类的对象。例如，这里我们分配了一个 `EOFException` 对象并抛出它：

```c
jclass class_EOFException = (*env)->FindClass(env, "java/io/EOFException");
jmethodID id_EOFException = (*env)->GetMethodID(env, class_EOFException, "<init>", "()V");
/* 无参数构造函数的 ID */
jthrowable obj_exc = (*env)->NewObject(env, class_EOFException, id_EOFException);
```



```c
(*env)->Throw(env, obj_exc);
```

通常调用`ThrowNew`会更方便，它在给定一个类和一个“修改后的 UTF-8”字节序列的情况下来构造异常对象。

```c
(*env)->ThrowNew(env, (*env)->FindClass(env, "java/io/EOFException"), "Unexpected end of file");
```

`Throw`和`ThrowNew`仅仅是投递异常；它们不会中断原生方法的控制流。只有当方法返回时，Java 虚拟机才会抛出异常。因此，每次调用`Throw`和`ThrowNew`之后都应该紧跟一个`return`语句。

---

![Image](img/00005.jpeg) **C++ 注意：**

如果你在 C++ 中实现原生方法，你不能在 C++ 代码中抛出 Java 异常对象。在 C++ 绑定中，可以实现 C++ 异常与 Java 异常之间的翻译；但目前尚未这样做。请使用`Throw`或`ThrowNew`在原生 C++ 方法中抛出 Java 异常，并确保你的原生方法没有抛出 C++ 异常。

---

通常，原生代码不需要捕获 Java 异常。然而，当原生方法调用 Java 方法时，该方法可能会抛出异常。此外，许多 JNI 函数也会抛出异常。例如，如果索引越界，`SetObjectArrayElement`会抛出`ArrayIndexOutOfBoundsException`；如果存储对象的类不是数组元素类的子类，则会抛出`ArrayStoreException`。

在这些情况下，原生方法应该调用`ExceptionOccurred`方法来确定是否抛出了异常。该调用：

```c
jthrowable obj_exc = (*env)->ExceptionOccurred(env);
```

如果没有挂起的异常，则返回`NULL`，否则返回异常对象的引用。如果你只想检查是否抛出了异常，而不获取异常对象的引用，请使用：

```c
jboolean occurred = (*env)->ExceptionCheck(env);
```

通常，当发生异常时，原生方法应该直接返回，以便虚拟机可以将其传播到 Java 代码。然而，原生方法可能会分析异常对象以确定它是否可以处理该异常。如果可以，则必须调用：

```c
(*env)->ExceptionClear(env);
```

来关闭异常。

在下一个示例中，我们以原生方法应有的所有谨慎程度实现了`fprint`原生方法。以下是我们抛出的异常：

- 如果格式字符串为`NULL`，抛出`NullPointerException`
- 如果格式字符串不包含适用于打印`double`的`%`说明符，抛出`IllegalArgumentException`
- 如果调用`malloc`失败，抛出`OutOfMemoryError`

最后，为了演示如何从原生方法调用 Java 方法时检查异常，我们逐个字符将字符串发送到流，并在每次调用后调用`ExceptionOccurred`。[列表 12.17] 显示了原生方法的代码，[列表 12.18] 显示了包含原生方法的类定义。注意，当调用`PrintWriter.print`发生异常时，原生方法并没有立即终止——它首先释放`cstr`缓冲区。当原生方法返回时，虚拟机再次抛出异常。[列表 12.19]中的测试程序演示了当格式无效时原生方法如何抛出异常。

**列表 12.17**

```c
/**
 * 版本 1997-07
 * 作者 Horstmann
 */

#include <string.h>
#include <stdlib.h>
#include <float.h>

/**
 * @param format 包含 printf 说明符的字符串（例如 "%8f"）
 * @return 说明符指针，如果没有唯一的说明符则返回 NULL
 */

char* find_format(const char format[]) {
    char* p;
    char* q;

    p = strchr(format, '%');
    while (p != NULL && *(p + 1) == '%') // 跳过 %%
        p = strchr(p + 2, '%');

    if (p == NULL) return NULL; // 不是唯一的

    p++;
    q = strspn(p, " -+#"); // 跳过标志
    q += strspn(q, "0123456789"); // 跳过字段宽度

    if (*q == '.') {
        q++;
        q += strspn(q, "0123456789"); // 跳过精度
    }

    if (strchr("eFgG", *q) == NULL) return NULL; // 不是浮点格式

    return p;
}

JNIEXPORT void JNICALL Java_Printf4_fprint(JNIEnv* env, jclass cl, jobject out, jstring format, jdouble x) {
    const char* cformat;
    char* fmt;
    jclass class_PrintWriter;
    jmethodID id_print;
    char* cstr;
    int width;
    int i;

    if (format == NULL) {
        (*env)->ThrowNew(env,
            (*env)->FindClass(env,
            "java/lang/NullPointerException"),
            "Printf4.fprint: format is null");
        return;
    }

    cformat = (*env)->GetStringUTFChars(env, format, NULL);
    fmt = find_format(cformat);
}
```

```c
if (fmt == NULL)
{
  (*env)->ThrowNew(env,
    (*env)->FindClass(env,
    "java/lang/IllegalArgumentException"),
    "Printf4.fprint: format is invalid");
  return;
}

width = atoi(fmt);
if (width == 0) width = DBL_DIG + 10;

cstr = (char*)malloc(strlen(cformat) + width);
if (cstr == NULL)
{
  (*env)->ThrowNew(env,
    (*env)->FindClass(env, "java/lang/OutOfMemoryError"),
    "Printf4.fprint: malloc failed");
  return;
}

sprintf(cstr, cformat, x);

(*env)->ReleaseStringUTFChars(env, format, cformat);

/* 现在调用 ps.print(str) */
/* 获取类 */
class_PrintWriter = (*env)->GetObjectClass(env, out);

/* 获取方法 ID */
id_print = (*env)->GetMethodID(env, class_PrintWriter, "print", "(C)V");

/* 调用方法 */
for (i = 0; cstr[i] != 0 && !(*env)->ExceptionOccurred(env); i++)
  (*env)->CallVoidMethod(env, out, id_print, cstr[i]);

free(cstr);
```

**Listing 12.18** `printf4/Printf4.java`  
点击此处查看代码图像

```java
import java.io.*;

/**
 * @version 1.10 1997-07-01
 * @author Cay Horstmann
 */

class Printf4
{
  public static native void fprint(PrintWriter ps, String format, double x);

  static
  {
    System.loadLibrary("Printf4");
  }
}
```

**Listing 12.19** `printf4/Printf4Test.java`  
点击此处查看代码图像

```java
import java.io.*;

/**
 * @version 1.10 1997-07-01
 * @author Cay Horstmann
 */

class Printf4Test
{
  public static void main(String[] args)
  {
    double price = 44.95;
    double tax = 7.75;
    double amountDue = price * (1 + tax / 100);
    PrintWriter out = new PrintWriter(System.out);

    /* 此调用将抛出异常——注意这一点 */
    Printf4.fprint(out, "Amount due = %.2f", amountDue);
    out.flush();
  }
}
```

### 处理 Java 异常

- `jint Throw(JNIEnv *env, jthrowable obj)`准备一个在退出原生代码时抛出的异常。成功时返回`0`，失败时返回负值。
- `jint ThrowNew(JNIEnv *env, jclass cl, const char msg[])`准备一个类型为`cl`的异常在退出原生代码时抛出。成功时返回`0`，失败时返回负值。`msg`是“修改后的 UTF-8”字节序列，表示异常对象的字符串构造。
- `jthrowable ExceptionOccurred(JNIEnv *env)`如果存在挂起的异常，则返回异常对象，否则返回`NULL`。
- `jboolean ExceptionCheck(JNIEnv *env)`如果存在挂起的异常则返回`true`。
- `void ExceptionClear(JNIEnv *env)`清除任何挂起的异常。

### 12.9 使用调用 API（Invocation API）

到目前，我们考虑的是使用 Java 语言编写并进行了一些 C 调用，这可能是因为 C 速度更快，或者允许访问 Java 无法访问的功能。假设你处于相反的情况：你有一个 C 或 C++ 程序，并希望调用 Java 代码。调用 API 允许你将 Java 虚拟机嵌入 C 或 C++ 程序中。以下是初始化虚拟机所需的最少代码：

```c
JavaVMOption options[1];
JavaVMInitArgs vm_args;
JavaVM *jvm;
JNIEnv *env;

options[0].optionString = "-Djava.class.path=.";

memset(&vm_args, 0, sizeof(vm_args));

vm_args.version = JNI_VERSION_1_2;
vm_args.nOptions = 1;
vm_args.options = options;

JNI_CreateJavaVM(&jvm, (void**) &env, &vm_args);
```

对`JNI_CreateJavaVM`的调用创建了虚拟机并填充指向虚拟机的指针`jvm`以及指向执行环境的指针`env`。

你可以为虚拟机提供任意数量的选项。只需增加`options`数组的大小和`vm_args.nOptions`的值即可。例如：

```c
options[i].optionString = "-Djava.compiler=NONE";
```

这将禁用即时编译器（JIT compiler）。

当你遇到问题且程序崩溃、拒绝初始化 JVM 或无法加载类时，请开启 JNI 调试模式。设置选项为：

```c
options[i].optionString = "-verbose:jni";
```

你将看到关于初始化 JVM 的大量信息。如果你没有看到你的类被加载，请检查路径设置。一旦你设置了虚拟机，就可以按照通常的方式使用`env`指针。目前有四个这样的函数。最重要的是终止虚拟机的函数：

```c
(*jvm)->DestroyJavaVM;
```

遗憾的是，在 Windows 上，由于旧 C 运行时库的变化，动态链接`JNI_CreateJavaVM`函数变得困难。我们的示例程序通过手动加载库解决了这个问题。这是`java`程序所使用的方法——见`src.jar`文件，它是 JDK 的一部分。

**Listing 12.20** `invocation/Invocation.c`

```c
/**
 * @version 1.20 2007-10-26
 * @author Cay Horstmann
 */

#include <jni.h>
#include <stdlib.h>

#ifdef _WINDOWS
#include <windows.h>

static HINSTANCE loadibrary(void);
typedef jint (JALL *CreateJavaVM_t)(JavaVM **, **, JavaInitArgs *);
#endif

int main()
{
  JavaVMOption options[2];
  JavaVMInitArgs vm_args;
  JavaVM *jvm;
  JNIEnv *env;
  long status;
  jclass class_Welcome;
  jclass class_String;
  jobjectArray args;
  jmethodID id_main;

#ifdef _WINDOWS
  HINSTANCE hjvmlib;
  CreateJavaVM_t createJavaVM;
#endif

  options[0].optionString = "-Djava.class.path=.";

  memset(&vm_args, 0, sizeof(vm_args));

  vm_args.version = JNI_VERSION_1_2;
  vm_args.nOptions = 1;
  vm_args.options = options;

#ifdef _WINDOWS
  hjvmlib = loadibrary();
  createJavaVM = (CreateJavaVM_t) GetProcAddress(hjvmlib, "JNI_CreateJavaVM");
  status = (*createJavaVM)(&jvm, (void **) &env, &vm_args);
#else
  status = JNI_CreateJavaVM(&jvm, (void **) &env, &vm_args);
#endif

  if (status == JNI_ERR)
  {
    fprintf(stderr, "Error creating VM\n");
    return 1;
  }

  class_Welcome = (*env)->FindClass(env, "Welcome");
  id_main = (*env)->GetStaticMethodID(env, class_Welcome, "main", "([Ljava/lang/String;)V");
  class_String = (*env)->FindClass(env, "java/lang/String");
  args = (*env)->NewObjectArray(env, 0, class_String, NULL);
}
```

```c
62      (*env)->CallStaticVoidMethod(env, class_Welcome, id_main, args);

64      (*jvm)->DestroyJavaVM(jvm);

66      return 0;
67   }

69   #ifdef _WINDOWS

71   static int GetStringFromRegistry(HKEY key, const char *name, char *buf, jint bufsize)
   {
      DWORD type, size;
      return RegQueryValueEx(key, name, 0, &type, 0, &size) == 0
          && type == REG_SZ
          && size <(unsigned int) bufsize
          && RegQueryValueEx(key, name, 0, 0, buf, &size) == 0;
   }

81   static void GetPublicJREHome(char *buf, jint bufsize)
   {
```



```c
HKEY key, subkey;

char version[MAX_PATH];

/* Find the current version of the JRE */

char *JRE_KEY = "Software\\JavaSoft\\Java Runtime Environment";

if (RegOpenKeyEx(HKEY_LOCAL_MACHINE, JRE_KEY, 0, KEY_READ, &key) != 0)
{
    fprintf(stderr, "Error opening registry key '%s'\n", JRE_KEY);
    exit(1);
}

if (!GetStringFromRegistry(key, "CurrentVersion", version, sizeof(version)))
{
    fprintf(stderr, "Failed reading value of registry key:\n\t%s\\CurrentVersion\n", JRE_KEY);
    RegCloseKey(key);
    exit(1);
}

/* Find directory where the current version is installed. */

if (RegOpenKeyEx(key, version, 0, KEY_READ, &subkey) != 0)
{
    fprintf(stderr, "Error opening registry key '%s\\%s'\n", JRE_KEY, version);
    RegCloseKey(key);
    exit(1);
}

if (!GetStringFromRegistry(subkey, "JavaHome", buf, bufsize))
{
    fprintf(stderr, "Failed reading value of registry key:\n\t%s\\%s\\JavaHome\n", JRE_KEY, version);
    RegCloseKey(key);
    RegCloseKey(subkey);
    exit(1);
}

RegCloseKey(key);
RegCloseKey(subkey);
}

static HINSTANCE loadJVibrary(void)
{
    HINSTANCE h1, h2;

    char msvcdll[MAX_PATH];
    char javadll[MAX_PATH];

    GetPublicJREHome(msvcdll, MAX_PATH);

    strcpy(javadll, msvcdll);
    strcat(msvcdll, "\\bin\\msv71.dll", MAX_PATH - strlen(msvcdll));
    msvcdll[MAX_PATH - 1] = '\0';

    strcat(javadll, "\\bin\\client\\jvm.dll", MAX_PATH - strlen(javadll));
    javadll[MAX_PATH - 1] = '\0';

    h1 = LoadLibrary(msvcdll);

    if (h1 == NULL)
    {
        fprintf(stderr, "Can't load library msv71.dll\n");
        exit(1);
    }

    h2 = LoadLibrary(javadll);

    if (h2 == NULL)
    {
        fprintf(stderr, "Can't load library jvm.dll\n");
        exit(1);
    }

    return h2;
}

#endif
```

在 Linux 下编译此程序，请使用：

```bash
gcc -I jdk/include -I jdk/include/linux -o InvocationTest -L jdk/jre/lib/i86/client -ljvm InvocationTest.c
```

在 Solaris 下，使用：

```bash
cc -I jdk/include -I jdk/include/solaris -o InvocationTest -L jdk/jre/lib/sparc -ljvm InvocationTest.c
```

在 Windows 下使用 Microsoft 编译器编译时，请使用命令行：

```bash
cl -D_WINDOWS -I jdk\include -I jdk\include\win32 InvocationTest.c jdk\lib\jvm.lib advapi32.lib
```

您需要确保`INCLUDE`和`LIB`环境变量包含了 Windows API 头文件和库文件的路径。

使用 Cygwin 编译，使用：

```bash
gcc -D_WINDOWS -mno-cygwin -I jdk\include -I jdk\include\win32 -D__int64="long long" -I c:\cygwin\usr\include\w32api -o InvocationTest
```

在 Linux/UNIX 下运行程序之前，请确保`LD_LIBRARY_PATH`包含共享库的目录。例如，如果您在 Linux 上使用`bash` shell，请执行以下命令：

```bash
export LD_LIBRARY_PATH=jdk/jre/lib/i86/client:$LD_LIBRARY_PATH
```

## Invocation API 函数

- `jint JNI_CreateJavaVM(JavaVM** p_jvm, void** p_env, JavaVMInitArgs* vm_args)` 初始化 Java 虚拟机。如果成功返回`0`，否则返回`JNI_ERR`。

![Image](img/0037.jpeg)

- `jint DestroyJavaVM(JavaVM* jvm)` 销毁虚拟机。成功返回`0`，失败返回负数。

## 12.10 完整示例：访问注册表

在本节中，我们描述一个完整示例，涵盖了讨论过的内容：原生方法、字符串以及错误处理。我们将简单使用注册表，这种程序天生是不可移植的。

### 12.10.1 注册表概述

Windows 注册表是一个存储系统和应用程序配置信息的仓库。它提供了管理和备份中心。缺点是，如果你搞乱了注册表，计算机可能会出现故障甚至无法启动！我们并不建议使用注册表来存储配置参数（参见卷 I 第 13 章）。

查看注册表的主要工具是注册编辑器。由于普通用户可能会出错，注册表没有启动图标。相反，启动 DOS 终端（或打开“运行”对话框）并输入`regedit`。图 12.4 显示了注册编辑器。

![Image](img/0038.jpeg)

**图 12.4** 注册编辑器

左侧显示键，它们以树形结构排列。注意每个键都以以下`HKEY`节点开头：

- `HKEY_CLASSES_ROOT`
- `HKEY_CURRENT_USER`
- `HKEY_LOCAL_MACHINE`

右侧显示与特定键关联的名称值对。例如，如果您安装了 Java SE 7，键`HKEY_LOCAL_MACHINE\Software\JavaSoft\Java Runtime Environment`包含如`CurrentVersion="1.7.0_10"`的名称值对。在这种情况下，值是字符串。值也可以是整数或字节数组。

### 12.10.2 用于访问注册表的 Java 平台接口

我们创建一个简单的接口从 Java 代码访问注册表，然后用原生代码实现该接口。我们的接口允许允许注册操作；为了减少代码体积，我们省略了一些重要的操作，如添加、删除和枚举键。（添加剩余的注册 API 函数很容易。）

即使只有我们提供的有限子集，您也可以：

- 枚举键中存储的所有名称
- 读取与名称关联的值
- 设置与名称关联的值

以下是封装注册键的 Java 类：

```java
public class Win32RegKey
{
    public Win32RegKey(int theRoot, String thePath) { . . . }

    public Enumeration names() { . . . }
}
```

```java
public native Object getValue(String name);

public native void setValue(String name, Object value);

public static final int HKEY_CLASSES_ROOT = 0×80000000;

public static final int HKEY_CURRENT_USER = 0×80000001;

public static final int HKEY_LOCAL_MACHINE = 0×80000002;

. . .
```

`names`方法返回一个包含与该键存储的所有名称的枚举器。你可以使用熟悉的`hasMoreElements`/`nextElement`方法来获取它们。`getValue`方法返回一个对象，该对象可以是字符串、`Integer`对象或字节数组（byte array）。`setValue`方法的`value`参数也必须是是这三种类型之一。

### 12.10.3 使用原生方法实现注册表访问函数

我们需要实现三个操作：

- 获取名称的值
- 设置名称的值
- 遍历键的名称

幸运的是，你已经基本上看过了所有需要的工具，例如 Java 字符串与数组与 C 语言字符串之间的转换。你还看到了在发生错误时如何抛出 Java 异常。

两个问题使得这些原生方法比之前的示例更复杂。`getValue`和`setValue`方法处理`Object`类型，该类型可以是`String`、`Integer`或`byte[]`之一。枚举对象存储了连续调用`hasMoreElements`和`nextElement`之间的状态。

让我们先看看`getValue`方法。该方法（显示在 Listing 12.22）遵循以下步骤：

1. 打开注册表键。为了读取它们的值，注册表 API 要求必须打开键。
2. 查询与名称关联的值的类型和大小。
3. 将数据读入缓冲区。
4. 如果类型是`REG_SZ`（字符串），则调用`NewStringUTF`使用值数据创建一个新字符串。
5. 如果类型是`REG_DWORD`（32 位位整数），则调用`Integer`构造函数。
6. 如果类型是`REG_BINARY`，则调用`NewByteArray`创建一个新的字节数组，然后调用`SetByteArrayRegion`将值数据拷贝到字节数组中。
7. 如果类型不是这些类型之一，或者在调用 API 函数时发生错误，则抛出异常并释放到那时已获取的所有资源。
8. 关闭键并返回已创建的对象（`String`、`Integer`或`byte[]`）。

如你所见，这个示例很好地说明了如何生成不同类型的 Java 对象。

在这一原生方法中，处理泛型返回类型并不困难。`jstring`、`jobject`或`jarray`引用只需作为`jobject`返回。然而，`setValue`方法接收一个`Object`引用，必须确定该`Object`的精确类型，以便将`Object`保存为字符串、整数或字节数组。我们可以通过查询`value`对象的类、找到`java.lang.String`、`java.lang.Integer`和`byte[]`的类引用，并与`IsAssignableFrom`函数进行比较来做出这种判断。

如果`class1`和`class2`是两个类引用，那么调用：

```c
(*env)->IsAssignableFrom(env, class1, class2)
```

当`class1`和`class2`是同一个类，或者`class1`是`class2`的子类时，返回`JNI_TRUE`。在任何情况下，指向`class1`对象的引用都可以强制转换为`class2`。例如，当：

```c
(*env)->IsAssignableFrom(
    env,
    (*env)->GetObjectClass(env, value),
    (*env)->FindClass(env, "[B")
)
```

为`true`时，我们知道`value`是字节数组。

以下是`setValue`方法步骤的概述：

1. 打开写入注册表键。
2. 找到要写入值的类型。
3. 如果类型是`String`，调用`GetStringUTFChars`获取字符指针。
4. 如果类型是`Integer`，调用`intValue`方法获取包装对象中存储的整数。
5. 如果类型是`byte[]`，调用`GetByteArrayElements`获取字节指针。
6. 将数据和长度传递给注册表。
7. **关闭键。**
8. 如果类型是`String`或`byte[]`，释放指向数据的指针。

最后，让我们转向枚举键的原生方法。这些是`Win32RegKeyNameEnumeration`类的方法（参见 Listing 12.21）。当枚举过程开始时，我们必须打开键。在枚举期间，我们必须保留键句柄——即键句柄必须存储在枚举对象中。键句柄类型为`DWORD`（32 位数值），因此它可以存储在 Java 整数中。将其存储在枚举类的`hkey`字段中。当枚举开始时，使用`GetIntField`存储它。

在这个枚举用例中，你已经基本上看过了所有需要的工具，例如 Java 字符串与数组与 C 语言字符串之间的转换。你还看到了在发生错误时如何抛出 Java 异常。

两个问题使得这些原生方法比之前的示例更复杂。`getValue`和`setValue`方法处理`Object`类型，该类型可以是`String`、`Integer`或`byte[]`之一。枚举对象存储了连续调用`hasMoreElements`和`nextElement`之间的状态。

让我们先看看`getValue`方法。该方法（显示在 Listing 12.22）遵循以下步骤：

1. 打开注册表键。为了读取它们的值，注册表 API 要求必须打开键。
2. 查询与名称关联的值的类型和大小。
3. 将数据读入缓冲区。
4. 如果类型是`REG_SZ`（字符串），则调用`NewStringUTF`使用值数据创建一个新字符串。
5. 如果类型是`REG_DWORD`（32 位位整数），则调用`Integer`构造函数。
6. 如果类型是`REG_BINARY`，则调用`NewByteArray`创建一个新的字节数组，然后调用`SetByteArrayRegion`将值数据拷贝到字节数组中。
7. 如果类型不是这些类型之一，或者在调用 API 函数时发生错误，则抛出异常并释放到那时已获取的所有资源。
8. 关闭键并返回已创建的对象（`String`、`Integer`或`byte[]`）。

如你所见，这个示例很好地说明了如何生成不同类型的 Java 对象。

在这一原生方法中，处理泛型返回类型并不困难。`jstring`、`jobject`或`jarray`引用只需作为`jobject`返回。然而，`setValue`方法接收一个`Object`引用，必须确定该`Object`的精确类型，以便将`Object`保存为字符串、整数或字节数组。我们可以通过查询`value`对象的类、找到`java.lang.String`、`java.lang.Integer`和`byte[]`的类引用，并与`IsAssignableFrom`函数进行比较来做出这种判断。

如果`class1`和`class2`是两个类引用，那么调用：

```c
(*env)->IsAssignableFrom(env, class1, class2)
```

当`class1`和`class2`是同一个类，或者`class1`是`class2`的子类时，返回`JNI_TRUE`。在任何情况下，指向`class1`对象的引用都可以强制转换为`class2`。例如，当：

```c
(*env)->IsAssignableFrom(
    env,
    (*env)->GetObjectClass(env, value),
    (*env)->FindClass(env, "[B")
)
```



当`true`时，我们知道`value`是字节数组。

以下是`setValue`方法步骤的概述：

1. 打开写入注册表键。
2. 找到要写入值的类型。
3. 如果类型是`String`，调用`GetStringUTFChars`获取字符指针。
4. 如果类型是`Integer`，调用`intValue`方法获取包装对象中存储的整数。
5. 如果类型是`byte[]`，调用`GetByteArrayElements`获取字节指针。
6. 将数据和长度传递给注册表。
7. 关闭键。
8. 如果类型是`String`或`byte[]`，释放指向数据的指针。

最后，让我们转向枚举键的原生方法。这些是`Win32RegKeyNameEnumeration`类的方法（参见列表 12.21）。当枚举过程开始时，我们必须打开键。在枚举期间，我们必须保留键句柄——即键句柄必须存储在枚举对象中。键句柄类型为`DWORD`（32 位数值），因此它可以存储在 Java 整数中。将其存储在枚举类的`hkey`字段中。当枚举开始时，使用`GetIntField`存储它。

在这个枚举用例中，你已经基本上看过了所有需要的工具，例如 Java 字符串与数组与 C 语言字符串之间的转换。你还看到了在发生错误时如何抛出 Java 异常。

```java
/**
 * @version 1.00 1997-07-01
 * @author Cay Horstmann
 */
public class Win32RegKey {
    public static final int HKEY_CLASSES_ROOT = 0x80000000;
    public static final int HKEY_CURRENT_USER = 0x80000001;
    public static final int HKEY_LOCAL_MACHINE = 0x80000002;
    public static final int HKEY_USERS = 0x80000003;
    public static final int HKEY_CURRENT_CONFIG = 0x80000005;
    public static final int HKEY_DYN_DATA = 0x80000006;

    private int root;
    private String path;

    /**
     * 获取注册表项的值。
     * @param name 条目名称
     * @return 关联的值
     */
    public native Object getValue(String name);

    /**
     * 设置注册表项的值。
     * @param name 条目名称
     * @param value 新值
     */
    public native void setValue(String name, Object value);

    /**
     * 构造注册表项对象。
     * @param theRoot HKEY_CLASSES_ROOT, HKEY_CURRENT_USER, HKEY_LOCAL_MACHINE, HKEY_CURRENT_CURRENT_CONFIG, HKEY_DYN_DATA 其中之一
     * @param thePath 注册表路径
     */
    public Win32RegKey(int theRoot, String thePath) {
        root = theRoot;
        path = thePath;
    }

    /**
     * 枚举此对象描述的路径下的所有注册表项的名称。
     * @return 列出所有条目名称的枚举
     */
    public Enumeration<String> names() {
        return new Win32RegKeyNameEnumeration(root, path);
    }

    static {
        System.loadLibrary("Win32RegKey");
    }
}

class Win32RegKeyNameEnumeration implements Enumeration<String> {
    public native String nextElement();

    public native boolean hasMoreElements();

    private int root;
    private String path;
    private int index = -1;
    private int hkey = 0;
    private int maxsize;
    private int count;

    Win32KeyNameEnumeration(int theRoot, String thePath) {
        root = theRoot;
        path = thePath;
    }
}

class Win32KeyException extends RuntimeException {
    public Win32KeyException() {
    }

    public Win32KeyException(String why) {
        super(why);
    }
}
```

### 列表 12.22：`win32reg/Win32Key.c`

```c
/**
 * @version 1.00 1997-07-01
 * @author Cay Horstmann
 */

#include "Win32RegKey.h"
#include "Win32KeyNameEnumeration.h"
#include <string.h>
#include <stdlib.h>
#include <windows.h>

JNIEXPORT jobject JNICALL Java_Win32Key_getValue(JNIEnv* env, jobject this_obj, jobject name)
{
    const char* cname;
    jstring path;
    const char* cpath;
    HKEY hkey;
    DWORD type;
    DWORD size;
    jclass this_class;
    jfieldID id_root;
    jfieldID id_path;
    HKEY root;
    jobject ret;
    char* cret;

    /* 获取类 */
    this_class = (*env)->GetObjectClass(env, this_obj);

    /* 获取字段 ID */
    id_root = (*env)->GetFieldID(env, this_class, "root", "I");
    id_path = (*env)->GetFieldID(env, this_class, "path", "Ljava/lang/String;");

    /* 获取字段 */
    root = (HKEY)(*env)->GetIntField(env, this_obj, id_root);
    path = (jstring)(*env)->GetObjectField(env, this_obj, id_path);
    cpath = (*env)->GetStringUTFChars(env, path, NULL);

    /* 打开注册表项 */
    if (RegOpenKeyEx(root, cpath, 0, KEY_READ, &hkey) != ERROR_SUCCESS)
    {
        (*env)->ThrowNew(env, (*env)->FindClass(env, "Win32KeyException"), "Open key failed");
        (*env)->ReleaseUTFChars(env, path, cpath);
        return;
    }

    (*env)->ReleaseUTFChars(env, path, cpath);
    cname = (*env)->GetStringUTFChars(env, name, NULL);

    /* 查找值的类型和大小 */
    if (RegQueryValueEx(hkey, cname, NULL, type, size) != ERROR_SUCCESS)
    {
        (*env)->ThrowNew(env, (*env)->FindClass(env, "Win32KeyException"), "Query value failed");
        RegCloseKey(hkey);
        (*env)->ReleaseStringChars(env, cname);
        return;
    }

    /* 分配用于存放值的内存 */
    cret = (char*)malloc(size);

    /* 读取值 */
    if (RegQueryValueEx(hkey, cname, NULL, type, cret) != ERROR_SUCCESS)
    {
        (*env)->ThrowNew(env, (*env)->FindClass(env, "Win32KeyException"), "Query value failed");
        free(cret);
        RegCloseKey(hkey);
        (*env)->ReleaseStringChars(env, cname);
        return;
    }

    /* 根据类型将值存储在字符串、整数或字节数组中 */
    if (type == REG_SZ)
    {
        ret = (*env)->NewStringUTF(env, cret);
    }
    else if (type == REG_DWORD)
    {
        jclass class_Integer = (*env)->FindClass(env, "java/lang/Integer");

        /* 获取构造方法的 ID */
        jmethodID id_Integer = (*env)->GetMethodID(env, class_Integer, "<init>", "(I)V");
        int value = *(int*)cret;

        /* 调用构造函数 */
        ret = (*env)->NewObject(env, class_Integer, id_Integer, value);
    }
    else if (type == REG_BINARY)
    {
        ret = (*env)->NewByteArray(env, size);
        (*env)->SetByteArrayRegion(env, (jarray)ret, 0, size, cret);
    }
    else
    {
        (*env)->ThrowNew(env, (*env)->FindClass(env, "Win32KeyException"), "Unsupported value type");
        ret = NULL;
    }

    free(cret);
    RegCloseKey(hkey);
    (*env)->ReleaseStringChars(env, cname);
    return ret;
}

JNIEXPORT void JNICALL Java_Win32Key_setValue(JNIEnv* env, jobject this_obj, jstring name, jobject value)
{
    const char* cname;
    jstring path;
    const char* cpath;
    HKEY hkey;
    DWORD type;
    DWORD size;
    jclass this_class;
    jclass class_value;
    jclass class_Integer;
    jfieldID id_root;
    jfieldID id_path;
    HKEY root;
    const char* cvalue;
    int ivalue;

    /* 获取类 */
    this_class = (*env)->GetObjectClass(env, this_obj);

    /* 获取字段 ID */
    id_root = (*env)->GetFieldID(env, this_class, "root", "I");
    id_path = (*env)->GetFieldID(env, this_class, "path", "Ljava/lang/String;");

    /* 获取字段 */
    root = (HKEY)(*env)->GetIntField(env, this_obj, id_root);
    path = (jstring)(*env)->GetObjectField(env, this_obj, id_path);
    cpath = (*env)->GetStringUTFChars(env, path, NULL);

    /* 打开注册表项 */
    if (RegOpenKeyEx(root, cpath, 0, KEY_WRITE, &hkey) != ERROR_SUCCESS)
    {
        (*env)->ThrowNew(env, (*env)->FindClass(env, "Win32KeyException"), "Open key failed");
        (*env)->ReleaseUTFChars(env, path, cpath);
        return;
    }

    (*env)->ReleaseUTFChars(env, path, cpath);
    cname = (*env)->GetStringUTFChars(env, name, NULL);
    class_value = (*env)->GetObjectClass(env, value);

    if (class_value == class_Integer)
    {
        ivalue = (*env)->GetIntField(env, (jobject)value);
        type = REG_DWORD;
    }
    else if (class_value == class_String)
    {
        cvalue = (*env)->GetStringUTFChars(env, (jstring)value, NULL);
        type = REG_SZ;
        size = strlen(cvalue) + 1;
    }
    else
    {
        (*env)->ThrowNew(env, (*env)->FindClass(env, "Win32KeyException"), "Unsupported value type");
        RegCloseKey(hkey);
        (*env)->ReleaseStringChars(env, name);
        return;
    }

    /* 写入值 */
    if (RegSetValueValueEx(hkey, cname, 0, type, (const BYTE*)cvalue, size) != ERROR_SUCCESS)
    {
        (*env)->ThrowNew(env, (*env)->FindClass(env, "Win32KeyException"), "Set value failed");
    }

    if (type == REG_SZ)
    {
        (*env)->ReleaseUTFChars(env, (jstring)value, cvalue);
    }

    RegCloseKey(hkey);
    (*env)->ReleaseStringChars(env, name);
}
```

```c
/* 确定值对象的类型 */
```



```c
if ((*env)->IsAssignableFrom(env, class_value, (*env)->FindClass(env, "java/lang/String")))
{
    /* 这是一个字符串--获取一个指向字符的指针 */
    cvalue = (*env)->GetStringUTFChars(env, (jstring) value, NULL);
    type = REG_SZ;
    size = (*env)->GetStringLength(env, (jstring) value) + 1;
}
else if (*env)->IsAssignableFrom(env, class_value, class_Integer))
{
    /* 这是一个整数--调用 intValue 来获取值 */
    jmethodID id_intValue = (*env)->GetMethodID(env, class_Integer, "intValue", "()I");
    ivalue = (*env)->CallIntMethod(env, value, id_intValue);
    type = REG_DWORD;
    cvalue = (char*) ivalue;
    size = 4;
}
else if (*env)->IsAssignableFrom(env, class_value, (*env)->FindClass(env, "[B")))
{
    /* 这是一个字节数组--获取一个指向字节的指针 */
    type = REG_BINARY;
    cvalue = (char*)(*env)->GetByteArrayElements(env, (jarray) value, NULL);
    size = (*env)->GetArrayLength(env, (jarray) value);
}
else
{
    /* 我们不知道如何处理这种类型 */
    (*env)->ThrowNew(env, (*env)->FindClass(env, "Win32RegKeyException"),
        "不支持的值类型");
    RegCloseKey(hkey);
    (*env)->ReleaseStringUTFChars(env, name, cname);
    return;
}

/* 设置值 */
if (RegSetValueEx(hkey, cname, 0, type, cvalue, size) != ERROR_SUCCESS)
{
    (*env)->ThrowNew(env, (*env)->FindClass(env, "Win32RegKeyException"),
        "设置值失败");
}

RegCloseKey(hkey);
(*env)->ReleaseStringUTFChars(env, name, cname);

/* 如果该值是字符串或字节数组，释放指针 */
if (type == REG_SZ)
{
    (*env)->ReleaseStringUTFChars(env, (jstring) value, cvalue);
}
else if (type == REG_BINARY)
{
    (*env)->ReleaseElements(env, (jarray) value, (jbyte*) cvalue, 0);
}

/* 用于开始枚举名称的辅助函数 */
static int startEnumeration(JNIEnv* env, jobject this_obj, jclass this_class)
{
    jfieldID id_index;
    jfieldID id_count;
    jfieldID id_root;
    jfieldID id_path;
    jfieldID id_hkey;
    jfieldID id_maxsize;
    HKEY root;
    jstring path;
    const char* cpath;
    HKEY hkey;
    DWORD maxsize = 0;
    DWORD count = 0;

    /* 获取字段 ID */
    id_root = (*env)->GetFieldID(env, this_class, "root", "I");
    id_path = (*env)->GetFieldID(env, this_class, "path", "java/lang/String;
    id_hkey = (*env)->GetFieldID(env, this_class, "hkey", "I");
    id_maxsize = (*env)->GetFieldID(env, this_class, "maxsize", "I");
    id_index = (*env)->GetFieldID(env, this_class, "index", "I");
    id_count = (*env)->GetFieldID(env, this_class, "count", "I");

    /* 获取字段值 */
    root = (HKEY)(*env)->GetIntField(env, this_obj, id_root);
    path = (jstring)(*env)->GetObjectField(env, this_obj, id_path);
    cpath = (*env)->GetStringUTFChars(env, path, NULL);

    /*打开注册表项 */
    if (RegOpenKeyEx(root, cpath, 0, KEY_READ, &hkey) != ERROR_SUCCESS)
    {
        (*env)->ThrowNew(env, &(*env)->FindClass(env, "Win32RegKeyException"),
            "打开项失败");
        (*env)->ReleaseStringUTFChars(env, path, cpath);
        return -1;
    }

    (*env)->ReleaseStringUTFChars(env, path, cpath);

    /* 查询名称的计数和最大长度 */
    if (RegQueryInfoKey(hkey, NULL, NULL, NULL, NULL, NULL, NULL, &count, &maxsize,
        NULL, NULL) != ERROR_SUCCESS)
    {
        (*env)->ThrowNew(env, (*env)->FindClass(env, "Win32KeyException"),
            "查询信息失败");
        RegCloseKey(hkey);
        return -1;
    }

    /* 设置字段值 */
    (*env)->SetIntField(env, this_obj, id_hkey, (DWORD) hkey);
    (*env)->SetIntField(env, this_obj, id_maxsize, maxsize + 1);
    (*env)->SetIntField(env, this_obj, id_index, 0);
    (*env)->SetIntField(env, this_obj, id_count, count);

    return count;
}

JNIEXPORT jboolean JNICALL Java_Win32KeyNameEnumeration_hasMore(JNIEnv* env,
    jobject this_obj)
{
    jclass this_class;
    jfieldID id_index;
    jfieldID id_count;
    int index;
    int count;

    /* 获取类 */
    this_class = (*env)->GetObjectClass(env, this_obj);

    /* 获取字段 ID */
    id_index = (*env)->GetFieldID(env, this_class, "index", "I");
    id_count = (*env)->GetFieldID(env, this_class, "count", "I");

    index = (*env)->GetIntField(env, this_obj, id_index);

    if (index == -1) /* 第一次 */
    {
        count = startEnumeration(env, this_obj, this_class);
        index = 0;
    }
    else
        count = (*env)->GetIntField(env, this_obj, id_count);

    return index < count;
}

JNIEXPORT jobject JNICALL Java_Win32KeyNameEnumeration_nextElement(JNIEnv* env,
    jobject this_obj)
{
    jclass this_class;
    jfieldID id_index;
    jfieldID id_hkey;
    jfieldID id_count;
    jfieldID id_maxsize;
    HKEY hkey;
    int index;
    int count;
    DWORD maxsize;
    char* cret;
    jstring ret;

    /* 获取类 */
    this_class = (*env)->GetObjectClass(env, this_obj);

    /* 获取字段 ID */
    id_index = (*env)->GetFieldID(env, this_class, "index", "I");
    id_count = (*env)->GetFieldID(env, this_class, "count", "I");
    id_hkey = (*env)->GetFieldID(env, this_class, "hkey", "I");
    id_maxsize = (*env)->GetFieldID(env, this_class, "maxsize", "I");

    index = (*env)->GetIntField(env, this_obj, id_index);

    if (index == -1) /* 第一次 */
    {
        count = startEnumeration(env, this_obj, this_class);
        index = 0;
    }
    else
        count = (*env)->GetIntField(env, this_obj, id_count);

    if (index >= count) /* 已经到达末尾 */
    {
        (*env)->ThrowNew(env, (*env)->FindClass(env, "past end of enumeration");
        return NULL;
    }

    maxsize = (*env)->GetIntField(env, this_obj, id_maxsize);
    hkey = (HKEY)(*env)->GetIntField(env, this_obj, id_hkey);
    cret = (char*)malloc(maxsize);

    /* 寻找下一个名称 */
    if (RegEnumValue(hkey, index, cret, &maxsize, NULL, NULL, NULL) != ERROR_SUCCESS)
    {
        (*env)->ThrowNew(env, (*env)->FindClass(env, "Win32KeyException"),
            "枚举值失败");
        free(cret);
        RegCloseKey(hkey);
        (*env)->SetIntField(env, this_obj, id_index, count);
        return NULL;
    }

    ret = (*env)->NewStringUTF(env, cret);
    free(cret);

    /* 增加索引 */
    index++;
    (*env)->SetIntField(env, this_obj, id_index, index);

    if (index == count) /* 到达结束 */
    {
        RegCloseKey(hkey);
    }

    return ret;
}
```

```java
public class Win32RegKeyTest
{
    public static void main(String[] args)
    {
        Win32RegKey key = new Win32RegKey(
            Win32RegKey.HKEY_CURRENT_USER, "Software\\JavaSoft\\Java Runtime Environment");

        key.setValue("Default user", "Harry Hacker");
        key.setValue("Lucky number", new Integer(13));
        key.setValue("Small primes", new byte[] { 2, 3, 5, 7, 11 });

        Enumeration<String> e = key.names();

        while (e.hasMoreElements())
        {
            String name = e.nextElement();
            System.out.print(name + "=");
            Object value = key.getValue(name);

            if (value instanceof byte[])
                for (byte b : (byte[]) value)
                    System.out.print((b & 0xFF) + " ");
            else
                System.out.print(value);

            System.out.println();
        }
    }
}
```



### 类型查询函数

- `jboolean IsAssignableFrom(JNIEnv *env, jclass cl1, jclass cl2)`：如果第一个类的对象可以赋值给第二个类的对象，则返回 `JNI_TRUE`，否则返回 `JNI_FALSE`。这用于测试类是否相同，或者 `cl1` 是否是 `cl2` 的子类，或者 `cl2` 是否是由 `cl1` 或其任一父类实现的接口。
- `jclass GetSuperclass(JNIEnv *env, jclass cl)`：返回类的超类。如果 `cl` 代表 `Object` 类或接口，则返回 `NULL`。

你现在已经到达了 *Core Java* 第二卷的末尾，完成了一段遇到许多高级 API 的长旅程。我们从每个 Java 程序员都需要了解的主题开始：流、XML、网络、数据库和国际化。三个很长的章节涵盖了图形和 GUI 编程。我们以关于安全、远程方法、注解处理和原生方法的非常技术性的章节作为结束。我们希望你喜欢这次对广阔 Java API 的旅程，并能够将新学到的知识应用到你的项目中。

## 索引

### 数字

- `-`（减号）在权限中，521；在策略文件中，520；在正则表达式中，129；在 URL 中，270
- `_`（下划线）在原生方法名中，941；在 SQL 中，289、319；在 URL 中，270
- `,`（逗号）小数点，372、378、686；在 DTD 中，165
- `;`（分号）在类路径中，292；在方法签名中，962；在 SQL 中，293；不需要的，在注解中，455
- `:`（冒号）作为文本文件的分隔符，63；在类路径中，292；在权限中，521；在 URL 中，258
- `!=` 运算符（SQL），289
- `?`（问号）在 DTD 中，165；在电子邮件 URI 中，927；在 glob 模式中，112–129；在掩码中，692；在预处理查询中，309；在 URL 中，269
- `/`（斜杠）结尾，在 codebase 中，516；在方法签名中，962；在路径中，101；在 URL 中，258
- `.`（点）小数点，372、378、686；在方法签名中，962；在正则表达式中，129–130；在 URL 中，270；在文件开头的，516
- `..`，在路径中，102
- `^`（脱字符）在正则表达式中，129、132
- `~`（波浪号）在 URL 中，270
- `'`（单引号）在掩码中，692
- `'. .'` 在 SQL 中，289
- `". ."` 在 XML 中，146
- `(. . .)` 在方法签名中，962；在正则表达式中，131、133
- ``（左括号）数组代码中，[87、961
- `{. . .}` 在注解中，466；在 glob 模式中，112；在消息格式化中，400–404；在正则表达式中，132
- `[. . .]` 在 `DOCTYPE` 声明中，164；在 glob 模式中，112；在正则表达式中，129–130；在 XPath 中，190
- `@`（at 符号）在注解中，455；在 URI 中，258；在 XPath 中，190
- `$`（美元符号）在原生方法名中，941；在正则表达式中，129–130、132、141
- `${. .}` 在策略文件中，521
- `*`（星号）在 DTD 中，165；在 glob 模式中，112；在掩码中，692；在权限中，521；在策略文件中，520；在正则表达式中，129、132
- `\`（反斜杠）在 glob 模式中，112；在路径中，56、101；在权限（Windows）中，520；在正则表达式中，129–130、141
- `\\|`，在正则表达式中，64
- `&`（和符号）在 CDATA section 中，149；在电子邮件 URI 中，927；在实体引用中，148；解析中，165
- `&&`，在正则表达式中，130
- `&#`、`&#x`，在字符引用中，148
- `#`（数字符号）在掩码中，692；在消息格式化中，403–404；在 URL 中，258
- `%`（百分比符号）在 `fortune` 程序中，933；在区域中，378；在 SQL 中，289、319；在 URL 中，270
- `%20`，在 URI 中，927
- `+`（加号）在 DTD 中，165；在正则表达式中，129、132；在 URL 中，270
- `<`（左角括号）在 CDATA section 中，149；在消息格式化中，404；解析中，165
- `<!--. . .-->`、`<?. . .?>`、`<![CDATA[. . .]]>`，在 XML 中，149
- `<. . .>`，在正则表达式中，131
- `≤` 运算符，404
- `=`、`<>` 运算符（SQL），289
- `==` 运算符，在枚举中，94
- `>`（右角括号），在 XML 中，149
- `|`（垂直线）作为文本文件中的分隔符，63；在 DTD 中，165、167；在消息格式化中，403；在正则表达式中，129、131
- `\0`，在正则表达式中，130
- 1931 CIE XYZ 色彩规范，836
- 2D 图形，765–937
  - 打印，852–862
  - `Xxx2D`、`Xxx2D.Float`、`Xxx2D.Double` 类，770–771

### A

- `A` 在掩码中，692
- `\a`、`\A`，在正则表达式中，130、132
- `abort` 方法（`LoginModule`），546
- `absolute` 方法（`ResultSet`），323、327
- `AbstractCellEditor` 类，629–631
  - `isCellEditable` 方法，630
- `AbstractFormatter` 类
  - `getDocumentFilter` 方法，689、701
  - `stringToValue`、`valueToString` 方法，693、701
- `AbstractListModel` 类，589
- `AbstractProcessor` 类，476
- `AbstractSpinnerModel` 类
  - `fireStateChanged` 方法，706
  - `get/setValue` 方法，705、712
  - `getNextValue`、`getPreviousValue` 方法，705–712
- `AbstractTableModel` 类，605
  - `isCellEditable` 方法，628
- `accept` 方法（`ServerSocket`），242、245
- `acceptChanges` 方法（`CachedSet`），331–332
- `AccessController` 类，`getContext` 方法，536
- Action 监听器，457–462
  - 用于文本字段，683
  - 安装，457
- `action.properties` 文件，449
- `ActionListener` 接口，457
  - `actionPerformed` 方法，458
- `@ActionListenerFor` 注解，457、472
- `ActionListenerInstaller` 类，457
- `Area` 的 `add` 方法，786–788
- `AttributeSet` 的，881
- `DefaultMutableTreeNode` 的，642、650
- `SystemTray` 的，932、936
- 注入框架构造函数的 `addActionListener` 方法，458
- `TrayIcon` 的，937
- 使用注解代替，457
- `AttributesImpl` 的 `addAttribute` 方法，232
- `Statement` 的 `addBatch` 方法，345–347
- `CellEditor` 的 `addCellEditorListener` 方法，638
- `TabbedPane` 的 `addChangeListener` 方法，737、741
- `JTable` 的 `addColumn` 方法，617、622
- `Document` 的 `addDocumentListener` 方法，682、685
- `DefaultListModel` 的 `addElement` 方法，595
- `Clipboard` 的 `addFlavorListener` 方法，894
- `JEditorPane` 的 `addHyperlinkListener` 方法，718
- `JFrame` 的 `addListSelectionListener` 方法，587
- `MimeMessage` 的 `addRecipient` 方法，278
- `TabbedPane` 的 `addTab` 方法，736、740
- `TreeModel` 的 `addTreeModelListener` 方法，672、680
- `JTree` 的 `addTreeSelectionListener` 方法，664
- `JComponent` 的 `addVetoableChangeListener` 方法，759
- `AES`（高级加密标准），生成密钥，568、569
- `aes/AEst.java`，571
- `aes/Util.java`，572
- 像素上的 `Affine` 变换，802
- `AffineTransform` 类，802–804
  - `getInstance` 方法，802–804
  - `setTo` 方法，802、804
- `AffineOp` 类，843、850
  - `TYPE_XXX` 字段，843、850
- `afterLast` 方法（`ResultSet`），323、327
- Agent 代码，458–462
- 别名，命名空间，172、197
- `allMatch` 方法（`Stream`），13
- `allocate` 方法（`ByteBuffer`），123、125
- `AllPermission` 类，513、519、523
- Alpha 通道，807–811
- Alpha 混合模式，817–818
- `AlphaComposite` 类，809
  - `getInstance` 方法，809、817
- `&amp;`，实体引用，148
- 锚点矩形，798
- `andFilter` 方法（`RowFilter`），615、625

#### 注释

- `getAnnotation` 方法，457、462、475、477
- `getAnnotations`、`getDeclaredAnnotations`、`isAnnotationPresent` 方法，462
- `getAnnotationsByType` 方法，462、475、477

##### `Annotation` 接口

- `annotationType` 方法，463
- `equals`、`hashCode`、`toString` 方法，464
- 继承，463

##### 注释接口

- 456、462–463
- 方法的，463
- 定义的，470–475

##### 注释处理器

- 在字节码层面，458、481
- 在运行时，458

##### 注释

- 455–462
- 适用性，472–473
- 文档化的，472、474
- 元素，456、463、466
- 用于编译，471
- 用于局部变量，467
- 用于资源管理，472
- 用于包，467
- 使用注解生成源代码，477–480
- 可继承的，474
- 标记的，465
- 元注解，456、470–475
- 无注解的，468
- 无循环依赖的，466
- 用于处理的工具，455
- 可重复的，475
- 保留的，472
- 单值的，465
- 源码层级，475–480
- 标准的，470–475
- 语法，462–469
- 瞬态的，473
- 与 Javadoc 注释对比，455

##### 抗锯齿

- 817–819

- `ANY` 元素（DTD），165
- `anyMatch` 方法（`Stream`），13
- Apache，143、150
- Apache 数据库，291
  - 连接到，295
  - 默认用户，295
  - 驱动程序的，292
  - 填充，305–309
  - 注册驱动，294
  - 启动，293
- Apache HttpClient，274
- Apache Tomcat，349
- `'` 实体引用，148
- `Appendable` 的 `append` 方法，54–55
- `Book` 的，873
- 形状类，776、786
- `Appendable` 接口，52–55
- `appendChild` 方法（`Node`），209、212

##### Applet

- 访问浏览器缓存，261
- 类的加载器，496
- 代码库，510
- 从安全内域网执行，547
- 不退出 JVM，509
- 弹出对话框，261
- 在浏览器中运行，564
- 其中的安全机制，491–579
- 警告窗口，526
- `appletviewer` 程序，515、564

##### 应用服务器

- 349、472

##### 应用

- 与原生代码通信，903–921
- 配置，144–145
- 之间的数据传输，888
- 桌面，927–932
- 企业级，349–350
- 加载，921
- 本地化，408
- 监控，487–488
- 支付的，499
- 服务端，267–277
- 签名，561–567
- 启动屏，921–926
- 启动插件，922
- 更新，932
- 内部帧，741–744
- `applyPattern` 方法（`MessageFormat`），401
- `apply-templates` 元素（XSLT），224
- `Arc2D` 类，769、772–773
- `Arc2D.Double` 类，785
- `ArcMaker` 类，777

##### 弧

- 边界接矩形，770、772
- 闭合类型，772–773
- 计算角度，773

##### `Area` 类

- `add` 方法，786–788
- `subtract`、`intersect`、`exclusiveOr` 方法，787–788

##### 区域

- 786–788
- ARGB（透明、红、绿、蓝），811、837

##### `ARRAY` 数据类型（SQL），347–348

##### `ArrayIndexOutOfBoundsException`

- 975

##### 数组

- 来自流元素，19
- 从数据库获取，347
- 在注解元素中，466
- 在原生代码中，970–974
- 原始类型，973
- 类型代码，87、961
- 类型使用注解，467
- 与 C 类型对比，970–974
- `Arrays` 类，`stream` 方法，8、36

##### `ArrayStoreException`

- 975

##### `asCharBuffer` 方法（`ByteBuffer`）

- 123
- ASCII 标准，67
- 以及原生代码，950
- 将原生编码转换为，408
- 在属性文件中，410
- 在正则表达式中，133
- ASM 库，481–489
- ASP（Active Server Pages），268
- `ATTLIST` 声明（DTD），167
- `attribute` 元素（XML Schema），174
- `Attribute` 接口，879
  - `getCategory` 方法，881、886
  - `getName` 方法，886
  - 实现，881
- 属性集，881

##### 属性（XML）

- 枚举，154
- 用于枚举类型，168
- 在 XML Schema 中，174
- 合法的，167
- 名称名称，146
- 命名空间的，198
- 值的，146
- 在 XPath 中访问，190
- 使用 XSLT 拷贝，225
- 默认（DTDs），167
- 规范化，168
- 对比元素，147–148、168、212
- `Attributes` 接口，`getXxx` 方法，204–205
- `AttributeSet` 接口，880
  - `add`、`get` 方法，881、886
  - `remove`、`toArray` 方法，886
- `AttributesImpl` 类，`addAttribute`、`clear` 方法，232
- `atZone` 方法（`LocalDateTime`），361
- `AudioPermission` 类，519
- `auth/AuthTest.java`，534
- `auth/AuthTest.policy`，535
- `auth/jaas.config`，535
- `auth/SysPropAction.java`，535
- 身份验证，530–546
  - 问题，556–557
  - 基于角色的，537
  - 与业务逻辑分离，532
  - 通过可信的中间介，557–558
- `AuthPermission` 类，520
- 自动装箱，601
- `AutoCloseable` 接口，`close` 方法，53
- 自动提交（数据库），344
  - 关闭，346
- 自动刷新，61
- 自动生成的键，320–321
- JAR 文件的自动注册，294
- 生成的辅助文件，455
- `available` 方法（`InputStream`），49–50、727
- `average` 方法（`Stream`），37、39–40
- AWT（Abstract Window），65–937
- `AWTPermission` 类，518、526

### B

- `B`（`byte`）类型，87、961
- `\b`、`\B`，在正则表达式中，132
- 边界，854
- `Banner` 类，`getPageCount`、`layoutPages` 方法，863
- 打印，862–864
- `BaseStream` 接口
  - `iterator` 方法，19–20
  - `parallel` 方法，41–45
  - `unordered` 方法，43、45
- `BasicFileAttributes` 接口，108
  - 方法的，109
- `BasicPermission` 类，520
- `BasicStroke` 类，788–796
- 批量更新（数据库），345–347
- 生成的 Bean 类，455
- `BeanInfo` 类，178
- `beforeFirst` 方法（`ResultSet`），323、327
- `between` 方法（`Duration`），352
- Bevel 边缘，788–789
- Bezier 曲线，775
- `BIG_ENDIAN` 常量（`ByteOrder`），123
- 大端序，70、407
- Bilinear 插值，843
- Binary 数据
  - 转换为 Unicode 单元，60
  - 读取，70
  - 对比文本，60
  - 写入，69
- `Bindings` 接口，433
  - `get`、`put` 方法，434
- `BLOB` 数据类型（SQL），291、348
- `Blob` 接口，316
  - `get/setBinaryStream`、`getBytes` 方法，316–317
  - `length` 方法，317
- BLOBs（二进制对象），316
  - 创建空的，318
  - 放入数据库，316
- 阻塞
  - 通过 I/O 方法，49
  - 通过网络连接，234、238、250–257
- Blur 滤镜，844
- BMP 格式，823
- `Book` 类，862
  - `append`、`getPrintable` 方法，873
- `book/Banner.java`，867
- `book/BookTestFrame.java`，865
- `book/PrintPreviewCanvas.java`，871
- `book/PrintPreviewDialog.java`，870
- 书籍，数字数，2
- `BOOLEAN` 数据类型（SQL），291、348
- `boolean` 类型
  - 打印，61
  - 类型代码，87、961
  - 对比 C 类型，947
  - 以二进制格式写入，69
- Bootstrap 类加载器，493
- 边界矩形，770
- `boxed` 方法（流的），36、39–40
- Bray, Tim，146
- 广优先枚举，659
- `breadthFirstEnumeration` 方法（`DefaultMutableTreeNode`），659、663
- `browse` 方法（`Desktop`），932

### 浏览器

- 字节码验证中的，506
- 缓存的，261
- 自定义，713
- 表单中的，267–277
- 从桌面应用启动，927
- 密码保护的页面中的，261
- 响应页面中的，268
- 在 applet 中运行，564

### 缓冲区

- `Buffer` 类，124–126
- `capacity` 方法，126
- `clear` 方法，125–126
- `flip` 方法，125–126
- `hasRemaining` 方法，122
- `limit` 方法，122
- `mark` 方法，125–126
- `position` 方法，126
- `remaining` 方法，125–126
- `reset` 方法，125–126
- `rewind` 方法，125–126
- 缓冲区，124–126
- 容量的，124
- 刷新，49、61
- 内存中的，53
- 限制，124
- 标记中的，124
- 位置中的，117、124
- 遍历……中的所有字节，117
- 对比随机访问，116
- `BufferUnderflowException`，123

### BugReport

- `@BugReport` 注解，473

### 业务

- 逻辑，284

### 按钮

- 按钮容量，788–789
- 框的监听器，688
- `ButtonFrame` 类，437、457
- `buttons1/ButtonFrame.java`，442
- `buttons2/properties`，452
- `buttons2/ButtonFrame.java`，451
- `buttons3/ButtonFrame.java`，460

### 字节

- `BYTE_ARRAY` 类（`Flavor`），875
- 字节标记，407
- `byte` 类型负值和无符号整数，693
- 类型代码，87、961
- 对比类型，947
- `ByteArrayOutputStream` 类，98、445
- `ByteBuffer` 类，117、124–126
  - `allocate` 方法，123、125
  - `asCharBuffer` 方法，123
  - `get` 方法，117、122
  - `getXxx` 方法，117、123
  - `order` 方法，118、123
  - `put` 方法，122
  - `putXxx` 方法，118、123
  - `wrap` 方法，123、125
- `bytecodeAnnotations/EntryLogger.java`，483
- `bytecodeAnnotations/LoggingAgent.java`，488
- 字节码工程，481–489
  - 加载时，486–488
  - 使用十六进制编辑器，507
  - 验证，504–508
- `ByteLookupTable` 类，844
  - 构造函数，850
- `ByteOrder` 类，`BIG_ENDIAN`、`LITTLE_ENDIAN` 常量，123
- 字节定向输入/输出流，48
- 字节读写，48–51

### C

- `C` 类型（`Flavor`），87、961

#### C 语言

- 数组中的，970–974
- 引导器，493
- 调用 Java 方法，963
- 数据库访问，284
- 嵌入 JVM 的，980–985
- `FILE*` 类型，51
- 文件头，942
- 无效位置中的，940
- 字符串中的，949
- 类型对比，947
- 正则表达式，130

#### C++ 语言

- JNI 函数中的，950
- 数组类型，971
- 嵌入 JVM 的，980–985
- 异常中的，975–976
- 原生方法，940、943
- 无效位置中的，940
- 指向空类的指针，965

### 缓存

- 缓存，261
- 缓存行，329–334
- `CachedRowSet` 接口，329–333
  - `acceptChanges` 方法，331–332
  - `execute` 方法，330、332
  - `get/setPageSize` 方法，330、332
  - `get/setTableName` 方法，331–332
  - `nextPage` 方法，330、332
- `populate` 方法，330、332
- `previousPage` 方法，332
- `CachedRowSetImpl` 类，329
- 凯撒密码，498–499
- `Calendar` 类，351
  - 对象的格式化，386
- `call` 转义（SQL），319
- `call` 方法（`CompilationTask`），445、448
- 权限检查期间的调用栈，513
- `Callable` 接口，445
- `Callback` 接口，538
- `CallbackHandler` 接口，`handle` 方法，545
- `CallNonvirtualXxxMethod` 函数（C），966、969
- `CallStaticXxxMethod` 函数（C），964–965、970
- `CallXxxMethod` 函数（C），963、969
- `cancelCellEditing` 方法（`CellEditor`），631–632、638
- `cancelRowUpdates` 方法（`ResultSet`），325、328
- `canImport` 方法（`TransferHandler`），912、918
- `canInsertImage` 方法（`ImageWriter`），827、834
- `capacity` 方法（`Buffer`），126
- 回车字符的显示，154
- 级联窗口，744–745
- 转换中的类型使用注解，468
- 目录，342
- `CDATA` 声明（DTD），167–168
- CDATA 节（XML），149
- 单元格编辑器（Swing），628–629
  - 自定义，629–638
- 单元格渲染器（Swing）
  - 用于列表，595–599
  - 用于表格，609、626
  - 用于树，661–664
- `CellEditor` 接口
  - `add/removeCellListener` 方法，638
  - `cancelCellEditing` 方法，631–632、638
  - `getCellEditorValue` 方法，629、631、638
  - `isCellEditable` 方法，638
  - `shouldSelectCell` 方法，631、638
  - `stopCellEditing` 方法，631–632、638
- 单元格（Swing）
  - 编辑，628–629
  - 渲染，626–638
  - 选择，612–614、626
- 证书，531、553–556
  - 和 Java 插件，563
  - 管理，560–561
  - 发布指纹，555
  - 根证书，563
  - 设置，510
  - 签名，558–561
- `CertificateSigner` 类，559
- CGI（通用网关接口），268
- 信任链，557
- `ChangeListener` 接口，737
- `changeUpdate` 方法（`DocumentListener`），682、685
- 通道，250
  - 用于文件，117
- `Channels` 类
  - `newInputStream` 方法，256
  - `newOutputStream` 方法，250、257
- `char` 类型
  - 用于代码，87、961
  - 对比 C 类型，947
- `CHAR_ARRAY` 类（`Doc`），875
- `Character` 类，129
- `CHARACTER` 数据（SQL），291、348
- 字符编码，60、67–69
  - 转换为 ASCII，408
  - 平台，68–69、404
- 字符引用（XML），148
- `CharacterData` 接口，`getData` 方法，153、162
- 字符
  - 抗锯齿，817
  - 之间的差异，394
  - 转义，64、129
  - 在正则表达式中，133
  - 规范化，394
  - 轮廓，805
  - 打印，61
  - 转换为大写，690
  - 以二进制格式写入，69
- `characters` 方法（`ContentHandler`），200、204
- `charAt` 方法（`String`），9
- `CharBuffer` 类，53–54
  - `get`、`put` 方法，124
- `CharSequence` 接口，54、134
  - `charAt`、`length` 方法，55
- `chars` 方法，36
- `codePoints` 方法，36、40
- 按正则表达式分割，6
- `subSequence`、`toString` 方法，55
- `Charset` 类
  - `defaultCharset` 方法，68、406
  - `forName` 方法，69
- 复选框（Swing），626
- `checked` 属性（HTML、XML），146
- 检查异常，533
- `checkError` 方法（`PrintWriter`），61–62
- `checkExit` 方法（`SecurityManager`），509、512
- `checkLogin` 方法（`SimpleLoginModule`），538
- `checkPermission` 方法（`SecurityManager`），512–513、523–524
- `checkRead` 方法（`SecurityManager`），513
- 子元素（XML），147
  - 获取节点列表的，154
  - 命名空间的，197
- 子节点（Swing），639
  - 添加，642
  - 连接线用于，645–646
- `children` 方法（`TreeNode`），658
- `choice` 元素（XML Schema），173
- `choice` 关键字（消息格式化），403
- Church, Alonzo，355
- `Cipher` 类，567–569
  - `doFinal` 方法，568、571、573、575
  - `getInstance` 方法，567、573
  - `getXxxSize` 方法，573
  - `init` 方法，573
  - `update` 方法，568、571、573、575
  - `XXX_MODE` 模式，568
- `CipherInputStream` 类，`read` 方法，575
- `CipherOutputStream` 类，574
  - 构造函数，575
  - `flush`、`write` 方法，575

#### Ciphers

- 生成密钥，569–574
- 公钥中的，575–579
- 用于流的，574–575
- 对称，567–569
- 注解中的循环依赖，466

#### `Class` 类

- `getClassLoader` 方法，493、503
- `getFields` 方法，674
- `getProtectionDomain` 方法，514
- 实现 `AnnotatedElement`
- 类文件，492
- 损坏的，504–508
- 加密的，498–499
- 格式的，481
- 加载，492
- 定位，444
- 修改，481–486
- 可移植性，407
- 在磁盘上生成，445
- 存储在数据库中，444
- 用于转换器的，487
- 验证，504–508
- 类加载器，450、492–508
  - 作为命名空间，496
  - 启动，493
  - 上下文，495–496
  - 创建，509
  - 扩展，493
  - 层次结构，494–496
  - 每个页面的独立的，496
  - 指定，494
  - 系统，493
  - 写入，497–503
- `class` 参数（IME 类型），892
- 类路径，493
- 原生代码中的类引用，958
- `.class` 扩展名，492

#### Classes

- 添加验证，92
- 注解，456、466、470
- 描述，86
- 可外部化的，87
- 继承树的，660
- 加载，492–494
- 语言区域支持，376
- 不可序列化的，92
- 保护域的，512
- 解析，492
- 每个页面的独立的，496
- 可序列化的，80–81
- 版本化，95–98
- 分类器函数，28
- `ClassLoader` 类，493
  - `defineClass`、`findClass` 方法，498、503
  - 扩展，497
  - `getParent`、`getSystemClassLoader` 方法，503
  - `loadClass` 方法，496、498
- 类加载器反转，494
- `classLoader/Caesar.java`，502
- `classLoader/Test.java`，499
- `CLASSP` 变量，493
- `CLEAR` 组合，810
- `AttributesImpl` 的 `clear` 方法，232
- `Buffer` 的，125–126
- `clearParameters` 方法（`PreparedStatement`），316
- 客户端/服务器应用程序，285
- 安全地客户端，566
- 连接到服务器，236–238
- 多个，245–248
- `clip` 方法（`GraphicsD`），767、805
- `Clipboard`，887–903
  - 访问，509
  - 能力的，888
  - 图像，894
  - 类引用，902
  - 对象，898–902
  - 文本，888–892
- `Clipboard` 类，888
  - `addFlavorListener` 方法，894
  - 构造函数，903
  - `get/setContents` 方法，889、891
  - `getAvailableDataavors` 方法，894
  - `getData` 方法，892
  - `isDataAvailable` 方法，891
- `ClipboardOwner` 接口
  - 实现，888
  - `lostOwnership` 方法，888、892

#### Clipping region

- 打印，854
- 设置，767
- `CLOB` 数据类型（SQL），291、348
- `Clob` 接口，316
  - `get/setCharacterStream` 方法，316、318
  - `getSubString` 方法，316–317
  - `length` 方法，317
- CLOBs（字符大对象），316
  - 创建空对象，318
  - 存入数据库，316
- `clone` 方法，81、98
  - 克隆，98–100
- `close` 方法
  - 来自 `AutoCloseable`，53
  - 来自 `Connection`，299、301、350
  - 来自 `FileLock`，128
  - 来自 `Flushable`，52
  - 来自 `InputStream`，49–50
  - 来自 `OutputStream`，51
  - 来自 `ProgressMonitor`，723、731
  - 来自 `ResultSet`，301
  - 来自 `ServerSocket`，245
  - 来自 `SplashScreen`，926
  - 来自 `Statement`，300–301
  - 来自 `XMLStreamWriter`，222
- `Closeable` 接口，52
  - `close` 方法，52、54
  - `flush` 方法，52
- 关闭的非叶子节点图标，648、661
- `closeEntry` 方法（`ZipXxxStream`），77–78
- `closeOnCompletion` 方法（`Statement`），300
- `closePath` 方法（`Path2D`），776、786
- 闭包类型，772
- `cmd` 壳，406
- 代码库，510、516
- 代码生成，注解，455–462、471
- 代码源，510
- 代码单元（UTF-16），在正则表达式中，130
- 代码破解（Kahn），498
- `codePoints` 方法（`CharSequence`），36、40
- `CodeSource` 类，`getXxx` 方法，514
- 排序，393–400
  - `collation/CollationTest.java`，396
  - `CollationKey` 类，`compareTo` 方法，400
  - `Collator` 类，393
  - `compare`、`equals` 方法，399
  - `get/setDecomposition` 方法，399
  - `get/setStrength` 方法，399
  - `getAvailableLocales` 方法，399
  - `getCollationKey` 方法，395、399
- `getInstance` 方法（`Stream`），19、22、35
- `collecting/CollectingIntoMaps.java`，25
- `collecting/CollectingResults.java`，20
- `collecting/DownstreamCollectors.java`，31
- `Collection` 接口
  - `parallelStream` 方法，2–5、41–46
  - `stream` 方法，2–5
- 集合处理，2–5
  - 与流，3
- `Collections` 类，`sort` 方法，394
- `Collector` 接口，19
- `Collectors` 类
  - `counting` 方法，29
  - `groupingBy` 方法，28–31
  - `groupingByConcurrent` 方法，43
  - `joining` 方法，20、23
  - `mapping` 方法，30、33
  - `maxBy`、`minBy` 方法，30、33
  - `partitioningBy` 方法，28–31
  - `summarizingXxx` 方法，20、23
  - `summingXxx` 方法，29、33
  - `toCollection` 方法，20、23
  - `toConcurrentMap` 方法，25、27
  - `toList` 方法，23
  - `toMap` 方法，24–27
  - `toSet` 方法，20、23
  - `Collectors` 下游，29–33
- 颜色选择器，629、898–902
- `Color` 类，797
  - 构造函数，842
  - `getRGB` 方法，842
  - 将值翻译为像素数据，838
  - 颜色空间转换，844
- `ColorOp` 类，843–844
- `ColorModel` 类，838
  - `getDataElements` 方法，842
  - `getRGB` 方法，837、842
- 颜色
  - 组件，807
  - 组合，808–811
  - 抖动，818
  - 插值，797–798
  - 否定，844
  - 纯色，766
- 列（数据库）
  - 在结果集中按数字访问，299
  - 名称，285
  - 数量，334
- 列（Swing）
  - 访问，610
  - 添加，617
  - 离线，601
  - 隐藏，617–625
  - 名称，606
  - 渲染，609–610
  - 调整大小，602、611–612
  - 选择，612
- `com.sun.rowset` 包，329
- `com.sun.security.auth.module` 包，532
- 组合框
  - 编辑，629
  - 遍历顺序中，704
- 注释（XML），149
- `commit` 方法
  - 来自 `Connection`，344–346
  - 来自 `LoginModule`，546
- 提交或回滚行为，687–688
- `commitEdit` 方法（`JFormattedTextField`），688、701
- `Comparable` 接口，615
- `Comparator` 接口，394
- 比较器，614
- `compare` 方法（`Collator`），399
- `compareTo` 方法
  - `CollationKey` 的，400
  - `Comparable` 的，615
  - `String` 的，393
- `Compilable` 接口，`compile` 方法，437
- 编译任务，443–449
- `CompilationTask` 接口，443–445
  - `call` 方法，445、448
- `compile` 方法（`Pattern`），134、139
- `CompiledScript` 接口，`eval` 方法，437
- 编译器注解用于，471
- 调用，443
- 即时编译，980
- 在磁盘上生成类文件，445
- 编译器 API，443–454
- `compiler/ByteArrayJavaClass.java`，446
- `compiler/CompilerTest.java`，452
- `compiler/MapClassLoader.java`，454
- `compiler/StringBuilderJavaSource.java`，446
- 复杂类型，172
- `complexType`（XML Schema），173
- 复合，809
- `composite/CompositeComponent.java`，814
- `composite/CompositeTestFrame.java`，812
- `composite/Rule.java`，815
- 组合规则，766–767、807–817
- *Computer Graphics: Principles and Practice*（Foley），775、809、836
- `concat` 方法（`Stream`），11
- 机密信息，传输，567
- 配置文件，126
- `connect` 方法
  - `Socket` 的，239
  - `URLConnection` 的，259、262
- `Connection` 接口
  - `close` 方法，299、301、350
  - `commit` 方法，344–346
  - `createBlob`、`createClob` 方法，316、318
  - `createStatement` 方法，298、321、326、344
  - `getAutoCommit` 方法，346
  - `getMetaData` 方法，333、342
  - `getWarnings` 方法，304
  - `prepareStatement` 方法，310、315、322、326
  - `releaseSavepoint` 方法，345–346
  - `rollback` 方法，344–346
  - `setSavepoint` 方法，346
- 连接（数据库）
  - 关闭，302
  - 使用行集后，329
  - 调试，279
  - 池化，350
  - 启动新线程，246
- `console` 方法（`System`），406
- 构造区域几何操作，786
- `Constructor` 类，457
- 构造函数注解，466
  - 从原生代码调用，965–966
  - 在类型中使用注解，468
- `containsAll` 方法（`Collection`），525
- 内容类型，260
- `ContentHandler` 类，199、201
  - `characters` 方法，200、204
  - `start/endDocument` 方法，204
  - `start/endElement` 方法，200–204
- 上下文类加载器，495–496
- 控制点
  - 拖拽，777
  - 曲线的，774
  - 形状的，776
- `convertXxxIndexToModel` 方法（`Table`），614、623
- 卷积操作，844
- `ConvolveOp` 类，843–845
  - 构造函数，851
- 坐标系
  - 自定义，767
  - 翻译，856
- 坐标变换，799–804
- `Copies` 类，879–881
  - `getValue` 方法，882
- `CopiesSupported` 类，879
- `copy` 方法（`Files`），106、108
- CORBA（Common Object Request Architecture）支持，494
- *Core Swing*（Topley），600、639、652、682
- `count` 方法（`Stream`），3–4、12
- *Count of Monte Cristo, The*（Dumas），727
- `counting` 方法（`Collectors`），29
- 国家代码，374
- `CRC32` 类，118
- CRC32 校验和，79、116、118
- `CREATE TABLE` 语句（SQL），290
  - 执行，298、300、316
  - 批量更新，345
- `createBindings` 方法（`ScriptEngine`），433
- `createBlob`、`createClob` 方法（`Connection`），316、318
- `createFile`、`createDirectory`、`createDirectories` 方法（`Files`），105–106
- `createGraphics` 方法（`SplashScreen`），926
- `createImageXxxStream` 方法（`ImageIO`），825、832
- `createPrintJob` 方法（`PrintService`），874、877
- `createStatement` 方法（`Connection`），298–299、321、326、344
- `createTempXxx` 方法（`Files`），105–106
- `createTransferable` 方法（`TransferHandler`），909、912
- `createXMLStreamReader` 方法（`XMLInputFactory`），207
- `createXMLStreamWriter` 方法（`XMLOutputFactory`），214、221
- `createXxx` 方法（`Document`），209、212
- `createXxxRowSet` 方法（`RowSetFactory`），329、333
- `creationTime` 方法（`BasicFileAttributes`），109
- 信用卡号，传输，567
- `crypt` 程序，570
- *Cryptography and Network Security*（Stallings），548、86
- 立方曲线，774–775
- `CubicCurve2D` 类，769、774
- `CubicCurve2D.Double` 类，785
- 货币，384–385
  - 可用，385
  - 格式化，378–383、691
  - 用于的标识符，384
- `Currency` 类，384–385
  - `getAvailableCurrencies` 方法，385
  - `getCurrencyCode` 方法，385
  - `getDefaultFractionDigits` 方法，385
  - `getInstance` 方法，384–385
  - `getSymbol` 方法，385
  - `toString` 方法，385
- 光标，释放形状，904
- `curveTo` 方法（`Path2D.Float`），775、786
- 自定义编辑器，629
- 自定义格式化器，693–703
- 剪切和粘贴，887–903
- Cygwin，944
- 编译 API，984
- 在 OpenSSL 中，560

### D

- `D`（`double`），类型代码，87、961
- `d` 字面量（SQL），318
- `\d`、`D`，在正则表达式中，131
- 虚线，虚线阶段，790
- 数据风味，892–894
- 数据源，349
- 数据传输，887–903
  - 在 Java 和原生代码之间，888
  - 用于的类和接口，888
  - 在 Swing 中，904–921
- 数据类型，87、961
  - 在 Java 与 C 中，947
  - 混淆名称，961
  - 用于打印的服务，874–875
- `database.properties` 文件，305、349
- `DatabaseMetaData` 接口，333–343
  - `getJDBCXxx` 版本，343
  - `getMaxConnection` 方法，343
  - `getMaxStatements` 方法，301、343
  - `getSQLStateType` 方法，302
  - `getTables` 方法，333、342
  - `supportsBatchUpdates` 方法，345、347
  - `supportsResultSetXxx` 方法，323、328
- 数据库，281–350
  - 在 C 语言中，282
  - 自动递增键，320
  - 避免数据重复，287
  - 批量更新，345、347
  - 缓存预处理语句，311
  - 用 SQL 更改数据，290
  - 到连接的，292、294、297
  - 关闭，301、306
  - 在 Web 和企业级应用中，349–350
  - 池化，350
  - 用于的驱动，283–284
  - 错误处理，346
  - 完整性，344
  - LOB 中的，316–318
  - 元数据，333–343
  - 修改，330
  - XML 的原生存储，349
  - 列中的编号，299
  - 外部连接，319
  - 填充，305–309
  - 保存对象到，474
  - 标量函数中，319
  - 架构的，342
  - 设置参数中，330
  - 启动，293
  - 存储过程中的，319
  - 存储：类文件，444；登录，537；结构，285、333；同步，331；用于的工具，334
  - 来自……的截断数据，303
  - URL 的，292
- `DataFlavor` 类，888、892–894
  - 构造函数，893
  - `getHumanPresentableName` 方法，894
  - `getMimeType` 方法，893
  - `getRepresentationClass` 方法，894
  - `imageFlavor` 常量，895
  - `isMimeTypeEqual` 方法，894
  - `javaFileListFlavor` 常量，914
- `DataInput` 接口，70
  - `readFully` 方法，71
  - `readUTF` 方法，70–71
  - `readXxx` 方法，70–71、81
  - `skipBytes` 方法，71
- `DataInputStream` 类，51、56
- `DataIO` 类，`xxxFixedString` 方法，73–74
- `DataOutput` 接口，69
  - `writeUTF` 方法，70、72
  - `writeXxx` 方法，69、72、81
- `DataOutputStream` 类，51
- `DataSource` 接口，349
- `DataTruncation` 类，303
  - `getIndex`、`getParameter` 方法，304
  - `getTransferSize` 方法，305

## 日期时间 API

- 351–370
- 以及遗留代码，369–370

- `Date` 类，87、369
  - 格式化对象，386
  - `read/writeObject` 方法，93
- `DATE` 数据类型（SQL），291、318、348
- 日期选择器，705
- `DateEditor` 类，712
- `dateFilter` 方法（`RowFilter`），615、625
- `DateFormat` 类，387
  - `getXxxInstance`、`setLenient` 方法，691
- `dateFormat/DateTimeFormatterTest.java`，388
- `dateFormat/EnumCombo.java`，391

## 日期

- 计算，358–360
- 编辑，691
- 过滤，615
- 格式化，365–368、372、378–393
- 宽松的，691
- 字面量用于，318
- 本地，355–358
- 解析，367
- `DateTimeFormatter` 类，365–368、385–393
  - 以及遗留类，369
  - `format` 方法，365、392
  - `ofLocalizedXxx` 方法，365、385、392
  - `ofPattern` 方法，367
  - `parse` 方法，367
  - `toFormat` 方法，367
  - `withLocale` 方法，365、392

- `DateTimeSyntax` 类，882
- 夏令时，361–365
- `DayOfWeek` 枚举，357
  - `getDisplayName` 方法，365、386
- `dayOfWeekMonth` 方法（`TemporalAdjusters`），359
- `DDL` 语句（SQL），300、316
- 调试
  - 在 JNI 中，980
  - JDBC 相关问题，296
  - 邮件连接，279
  - 本地化的，377
  - 策略文件，564
  - 流，11
  - 带有 `telnet`，233–236
- `DECIMAL` 数据类型（SQL），291、348
- 小数分隔符，372、378、686
- 声明注解，466–468
- `decode` 方法（`URLDecoder`），277
- 解密密钥，498
- `default` 语句，462
- `DefaultCellEditor` 类，654
  - 构造函数，638
  - 变体，629
- `defaultCharset` 方法（`Charset`），68、406
- `DefaultFormatter` 类
  - 扩展，693
  - `get/setOverwriteMode` 方法，692、702
  - `toString` 方法，691
- `DefaultHandler` 类，201
- `DefaultListModel` 类，594
  - `add/removeElement` 方法，595
- `DefaultMutableTreeNode` 类，641、659–661
  - `add` 方法，642、650
  - 构造函数，650
  - `depth` 方法，357
  - `pathToRoot` 方法，359
  - `setAsksChildren`、`setAsksChildren` 方法，648、650
  - `setAsksChildren` 方法，648
  - `FirstEnumeration`、`OrderEnumeration` 方法，659、663
- `defaultPage` 方法（`Printer`），888
- `DefaultSorter` 类
  - `setSortable` 方法，614、624
  - `setRowFilter` 方法，615、625
- `DefaultTableCell` 类，626、627
- `DefaultTreeRenderer` 类，661–664
  - `setIcon` 方法，664
- `DefaultTreeModel` 类，650、673
  - 自动通知由，652
  - `insertNodeInto` 方法，653、658
  - `isLeaf` 方法，648
  - `nodeChanged` 方法，652、658
  - `nodesChanged` 方法，658
  - `reload` 方法，653、658
  - `removeNodeFromParent` 方法，652、658
- `defaultWriteObject` 方法（`ObjectOutputStream`），92
- `defineClass` 方法（`ClassLoader`），498、503
- 延迟格式化，888

### 代码片段

![Image](img/01094.jpeg#part0013.html_ch08pro01) ![Image](img/01095.jpeg#part0013.html_ch08pro02) ![Image](img/01096.jpeg#part0013.html_ch08pro03) ![Image](img/01097.jpeg#part0013.html_ch08pro04) ![Image](img/01098.jpeg#part0013.html_ch08pro05) ![Image](img/01099.jpeg#part0013.html_ch08pro06) ![Image](img/01100.jpeg#part0013.html_ch08pro07) ![Image](img/01101.jpeg#part0013.html_ch08pro08) ![Image](img/01102.jpeg#part0013.html_ch08pro09) ![Image](img/01103.jpeg#part0013.html_ch08pro10) ![Image](img/01104.jpeg#part0013.html_ch08pro11) ![Image](img/01105.jpeg#part0013.html_ch08pro12) ![Image](img/01106.jpeg#part0013.html_ch08pro13) ![Image](img/01107.jpeg#part0013.html_ch08pro14) ![Image](img/01108.jpeg#part0013.html_ch08pro15) ![Image](img/01109.jpeg#part0013.html_ch08pro16) ![Image](img/01110.jpeg#part0013.html_ch08pro17) ![Image](img/01111.jpeg#part0013.html_ch08pro18) ![Image](img/01112.jpeg#part0013.html_ch08pro19) ![Image](img/01113.jpeg#part0013.html_ch08pro20) ![Image](img/01114.jpeg#part0013.html_ch08pro21) ![Image](img/01115.jpeg#part0013.html_ch08pro22) ![Image](img/01116.jpeg#part0013.html_ch08pro23) ![Image](img/01117.jpeg#part0013.html_ch08lis01) ![Image](img/01118.jpeg#part0013.html_ch08lis01) ![Image](img/01119.jpeg#part0013.html_ch08lis01) ![Image](img/01120.jpeg#part0013.html_ch08lis02) ![Image](img/01121.jpeg#part0013.html_ch08pro24) ![Image](img/01122.jpeg#part0013.html_ch08pro25) ![Image](img/01123.jpeg#part0013.html_ch08pro26) ![Image](img/01124.jpeg#part0013.html_ch08pro27) ![Image](img/01125.jpeg#part0013.html_ch08pro28) ![Image](img/01126.jpeg#part0013.html_ch08lis03) ![Image](img/01127.jpeg#part0013.html_ch08lis04) ![Image](img/01128.jpeg#part0013.html_ch08pro29) ![Image](img/01129.jpeg#part0013.html_ch08pro30) ![Image](img/01130.jpeg#part0013.html_ch08pro31) ![Image](img/01131.jpeg#part0013.html_ch08pro32) ![Image](img/01132.jpeg#part0013.html_ch08lis05) ![Image](img/01133.jpeg#part0013.html_ch08lis06) ![Image](img/01134.jpeg#part0013.html_ch08lis07) ![Image](img/01135.jpeg#part0013.html_ch08lis01) ![Image](img/01136.jpeg#part0013.html_ch08lis01) ![Image](img/01137.jpeg#part0013.html_ch08lis01) ![Image](img/01138.jpeg#part0013.html_ch08lis08) ![Image](img/01139.jpeg#part0013.html_ch08pro33) ![Image](img/01140.jpeg#part0013.html_ch08pro34) ![Image](img/01141.jpeg#part0013.html_ch08pro35) ![Image](img/01142.jpeg#part0013.html_ch08pro36) ![Image](img/01143.jpeg#part0013.html_ch08pro37) ![Image](img/01144.jpeg#part0013.html_ch08pro38) ![Image](img/01145.jpeg#part0013.html_ch08pro39) ![Image](img/01146.jpeg#part0013.html_ch08lis09) ![Image](img/01147.jpeg#part0013.html_ch08lis09) ![Image](img/01148.jpeg#part0013.html_ch08lis01) ![Image](img/01149.jpeg#part0013.html_ch08lis10) ![Image](img/01150.jpeg#part0013.html_ch08lis01) ![Image](img/01151.jpeg#part0013.html_ch08lis11) ![Image](img/01152.jpeg#part0013.html_ch08pro40) ![Image](img/01153.jpeg#part0013.html_ch08pro41) ![Image](img/01154.jpeg#part0013.html_ch08pro42) ![Image](img/01155.jpeg#part0013.html_ch08pro43) ![Image](img/01156.jpeg#part0013.html_ch08pro44) ![Image](img/01157.jpeg#part0013.html_ch08pro45) ![Image](img/01158.jpeg#part0013.html_ch08pro46) ![Image](img/01159.jpeg#part0013.html_ch08pro47) ![Image](img/01160.jpeg#part0013.html_ch08pro48) ![Image](img/01161.jpeg#part0013.html_ch08pro49) ![Image](img/01162.jpeg#part0013.html_ch08pro50) ![Image](img/01163.jpeg#part0013.html_ch08pro51) ![Image](img/01164.jpeg#part0013.html_ch08pro52) ![Image](img/01165.jpeg#part0013.html_ch08pro53) ![Image](img/01166.jpeg#part0013.html_ch08pro54) ![Image](img/01167.jpeg#part0013.html_ch08pro55) ![Image](img/01168.jpeg#part0013.html_ch08pro56) ![Image](img/01169.jpeg#part0013.html_ch08pro57) ![Image](img/01170.jpeg#part0013.html_ch08pro58) ![Image](img/01171.jpeg#part0013.html_ch08pro59) ![Image](img/01172.jpeg#part0013.html_ch08pro60) ![Image](img/01173.jpeg#part0013.html_ch08pro61) ![Image](img/01174.jpeg#part0013.html_ch08pro62) ![Image](img/01175.jpeg#part0013.html_ch08pro63) ![Image](img/01176.jpeg#part0013.html_ch08pro64) ![Image](img/01177.jpeg#part0013.html_ch08pro65) ![Image](img/01178.jpeg#part0013.html_ch08pro66) ![Image](img/01179.jpeg#part0013.html_ch08pro67) ![Image](img/01180.jpeg#part0013.html_ch08pro68) ![Image](img/01181.jpeg#part0013.html_ch08pro69) ![Image](img/01182.jpeg#part0013.html_ch08pro70) ![Image](img/01183.jpeg#part0013.html_ch08pro71) ![Image](img/01184.jpeg#part0013.html_ch08pro72) ![Image](img/01185.jpeg#part0013.html_ch08pro73) ![Image](img/01186.jpeg#part0013.html_ch08pro74) ![Image](img/01187.jpeg#part0013.html_ch08pro75) ![Image](img/01188.jpeg#part0013.html_ch08pro76) ![Image](img/01189.jpeg#part0013.html_ch08pro77) ![Image](img/01190.jpeg#part0013.html_ch08pro78) ![Image](img/01191.jpeg#part0013.html_ch08pro79) ![Image](img/01192.jpeg#part0013.html_ch08pro80) ![Image](img/01193.jpeg#part0013.html_ch08pro81) ![Image](img/01194.jpeg#part0013.html_ch08pro82) ![Image](img/01195.jpeg#part0013.html_ch08pro83) ![Image](img/01196.jpeg#part0013.html_ch08pro84) ![Image](img/01197.jpeg#part0013.html_ch08pro85) ![Image](img/01198.jpeg#part0013.html_ch08pro86) ![Image](img/01199.jpeg#part0013.html_ch08pro87) ![Image](img/01200.jpeg#part0013.html_ch08pro88) ![Image](img/01201.jpeg#part0013.html_ch08pro89) ![Image](img/01202.jpeg#part0013.html_ch08pro90) ![Image](img/01203.jpeg#part0013.html_ch08pro91) ![Image](img/01204.jpeg#part0013.html_ch08pro92) ![Image](img/01205.jpeg#part0013.html_ch08pro93) ![Image](img/01206.jpeg#part0013.html_ch08pro94) ![Image](img/01207.jpeg#part0013.html_ch08pro95) ![Image](img/01208.jpeg#part0013.html_ch08pro96) ![Image](img/01209.jpeg#part0013.html_ch09lis12) ![Image](img/01210.jpeg#part0013.html_ch09lis01) ![Image](img/01211.jpeg#part0013.html_ch09lis01) ![Image](img/01212.jpeg#part0013.html_ch09lis13) ![Image](img/01213.jpeg#part0013.html_ch09lis14) ![Image](img/01214.jpeg#part0013.html_ch09pro97) ![Image](img/01215.jpeg#part0013.html_ch09pro98) ![Image](img/01216.jpeg#part0013.html_ch09pro99) ![Image](img/01217.jpeg#part0013.html_ch09pro100) ![Image](img/01218.jpeg#part0013.html_ch09pro101) ![Image](img/01219.jpeg#part0013.html_ch09lis15) ![Image](img/01220.jpeg#part0014.html_ch09pro01) ![Image](img/01221.jpeg#part0014.html_ch09pro02) ![Image](img/01222.jpeg#part0014.html_ch09pro03) ![Image](img/01223.jpeg#part0014.html_ch09pro04) ![Image](img/01224.jpeg#part0014.html_ch09lis01) ![Image](img/01225.jpeg#part0014.html_ch09lis01) ![Image](img/01226.jpeg#part0014.html_ch09lis01) ![Image](img/01227.jpeg#part0014.html_ch09lis02) ![Image](img/01228.jpeg#part0014.html_ch09pro04) ![Image](img/01229.jpeg#part0014.html_ch09pro05) ![Image](img/01230.jpeg#part0014.html_ch09pro06) ![Image](img/01231.jpeg#part0014.html_ch09pro07) ![Image](img/01232.jpeg#part0014.html_ch09pro08) ![Image](img/01233.jpeg#part0014.html_ch09pro09) ![Image](img/01234.jpeg#part0014.html_ch09pro10) ![Image](img/01235.jpeg#part0014.html_ch09pro11) ![Image](img/01236.jpeg#part0014.html_ch09lis03) ![Image](img/01237.jpeg#part0014.html_ch09pro12) ![Image](img/01238.jpeg#part0014.html_ch09pro13) ![Image](img/01239.jpeg#part0014.html_ch09pro14) ![Image](img/01240.jpeg#part0014.html_ch09pro15) ![Image](img/01241.jpeg#part0014.html_ch09pro16) ![Image](img/01242.jpeg#part0014.html_ch09pro17) ![Image](img/01243.jpeg#part0014.html_ch09pro18) ![Image](img/01244.jpeg#part0014.html_ch09pro19) ![Image](img/01245.jpeg#part0014.html_ch09pro20) ![Image](img/01246.jpeg#part0014.html_ch09pro21) ![Image](img/01247.jpeg#part0014.html_ch09pro22) ![Image](img/01248.jpeg#part0014.html_ch09pro23) ![Image](img/01249.jpeg#part0014.html_ch09pro24) ![Image](img/01250.jpeg#part0014.html_ch09pro25) ![Image](img/01251.jpeg#part0014.html_ch09pro26) ![Image](img/01252.jpeg#part0014.html_ch09pro27) ![Image](img/01253.jpeg#part0014.html_ch09pro28) ![Image](img/01254.jpeg#part0014.html_ch09pro29) ![Image](img/01255.jpeg#part0014.html_ch09pro30) ![Image](img/01256.jpeg#part0014.html_ch09pro31) ![Image](img/01257.jpeg#part0014.html_ch09pro32) ![Image](img/01258.jpeg#part0014.html_ch09pro33) ![Image](img/01259.jpeg#part0014.html_ch09pro34) ![Image](img/01260.jpeg#part0014.html_ch09pro35) ![Image](img/01261.jpeg#part0014.html_ch09pro36) ![Image](img/01262.jpeg#part0014.html_ch09pro37) ![Image](img/01263.jpeg#part0014.html_ch09pro38) ![Image](img/01264.jpeg#part0014.html_ch09pro39) ![Image](img/01265.jpeg#part0014.html_ch09pro40) ![Image](img/01266.jpeg#part0014.html_ch09pro41) ![Image](img/01267.jpeg#part0014.html_ch09pro42) ![Image](img/01268.jpeg#part0014.html_ch09pro43) ![Image](img/01269.jpeg#part0014.html_ch09pro44) ![Image](img/01270.jpeg#part0014.html_ch09pro45) ![Image](img/01271.jpeg#part0014.html_ch09pro46) ![Image](img/01272.jpeg#part0014.html_ch09pro47) ![Image](img/01273.jpeg#part0014.html_ch09pro48) ![Image](img/01274.jpeg#part0014.html_ch09pro49) ![Image](img/01275.jpeg#part0014.html_ch09pro50) ![Image](img/01276.jpeg#part0014.html_ch09lis04) ![Image](img/01277.jpeg#part0014.html_ch09lis04) ![Image](img/01278.jpeg#part0014.html_ch09lis05) ![Image](img/01279.jpeg#part0014.html_ch09lis05) ![Image](img/01280.jpeg#part0014.html_ch09lis05) ![Image](img/01281.jpeg#part0014.html_ch09pro51) ![Image](img/01282.jpeg#part0014.html_ch09pro52) ![Image](img/01283.jpeg#part0014.html_ch09pro53) ![Image](img/01284.jpeg#part0014.html_ch09pro54) ![Image](img/01285.jpeg#part0014.html_ch09pro55) ![Image](img/01286.jpeg#part0014.html_ch09pro56) ![Image](img/01287.jpeg#part0014.html_ch09pro57) ![Image](img/01288.jpeg#part0014.html_ch09pro58) ![Image](img/01289.jpeg#part0014.html_ch09pro59) ![Image](img/01290.jpeg#part0014.html_ch09pro60) ![Image](img/01291.jpeg#part0014.html_ch09pro61) ![Image](img/01292.jpeg#part0014.html_ch09pro62) ![Image](img/01293.jpeg#part0014.html_ch09lis06) ![Image](img/01294.jpeg#part0014.html_ch09lis07) ![Image](img/01295.jpeg#part0014.html_ch09lis08) ![Image](img/01296.jpeg#part0014.html_ch09lis09) ![Image](img/01297.jpeg#part0014.html_ch09lis12) ![Image](img/01298.jpeg#part0014.html_ch09lis01) ![Image](img/01299.jpeg#part0014.html_ch09lis01)
