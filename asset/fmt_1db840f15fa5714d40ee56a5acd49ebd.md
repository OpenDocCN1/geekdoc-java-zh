
```java
java.util.EmptyStackException
    at java.util.Stack.peek(Unknown Source)
    at java.util.Stack.pop(Unknown Source)
    at Test.main(StackTest.java:34)
```

**图 16.1** 包 `java.util` 类的 `Stack` 类。（第 2 部分，共 2 部分）

> **错误预防技巧 16.1**
>
> 由于 `Stack` 继承自 `Vector`，因此在 `Stack` 对象上可以调用所有公共方法，即使这些方法没有执行传统的栈操作。例如，可以使用 `Vector` 方法在栈的任何位置插入元素——这可能会“破坏”栈。在操作 `Stack` 时，应只使用 `push` 和 `pop` 方法来分别从栈中添加和移除元素。在第 21.5 节中，我们使用组合来创建 `Stack`，以便 `Stack` 在其公共接口中仅提供栈应该允许的能力。

第 10 行创建 `Stack` 类的实例。`Number`（在 `java.lang` 包中）是基本数值类型包装器类（例如 `Integer`、`Double`）的父类。通过创建一个 `Number` 栈，任何继承 `Number` 的类的对象都可以被推入栈中。第 13、16、19 和 22 行调用了每个 `Stack` 方法 `push`，将一个 `Number` 对象推到栈的顶部。请注意字面量 `12L`（第 13 行）和 `1.0F`（第 19 行）。带有后缀 `L` 的任何整数字面量都是 `long` 值。不带后缀的整数字面量是 `int` 值。同样，带有后缀 `F` 的浮点字面量是 `float` 值。不带后缀的浮点数字面量是 `double` 值。你可以在 Java 语言规范的 <http://docs.oracle.com/javase/specs/jls/se/jls-15.8.html> 了解更多关于数值字面量的信息。

一个无限循环（第 32–37 行）调用 `Stack` 方法来移除栈的顶部元素。该方法向被移除的元素返回一个 `Number`。如果栈中没有元素，`pop` 方法将抛出 `EmptyStackException`，这会终止循环。类还声明了 `peek` 方法。此方法返回栈的顶部元素，但不将其从栈中弹出。

方法 `printStack`（第 46–52 行）显示栈的内容。栈的当前顶部（最后推入栈的值）是第一个打印的值。第 48 行调用 `Stack` 方法 `isEmpty`（继承自类 `Vector`）来判断栈是否为空。如果为空，则该方法返回 `true`；否则返回 `false`。

# 16.9 PriorityQueue 和 Queue 接口

回想一下，队列是一种表示等待队列的集合——通常从尾部插入并从头部删除。在第 21.6 节中，我们将讨论并实现一种队列数据结构。在本节中，我们将研究 Java 的 `PriorityQueue`。`PriorityQueue` 是一个根据元素的优先级而不是到达顺序处理元素的集合。优先级最高的元素位于队列头部。

在 `PriorityQueue` 中，优先级由元素的自然排序或 `Comparator` 决定。如果元素没有实现 `Comparable` 接口，则必须向构造函数提供一个 `Comparator`。`PriorityQueue` 的主要操作与 `Queue` 类似：`add`（或 `offer`）、`remove`（或 `poll`）和 `element`（或 `peek`）。

`add` 和 `offer` 方法将元素插入 `PriorityQueue`，并保持排序。`remove` 和 `poll` 方法移除并返回头部元素（优先级最高）。`element` 方法返回头部元素但不将其移除。

`PriorityQueue` 可用于多种场景，例如任务调度、Dijkstra 最短路算法和霍夫曼编码。它是 Java 开发者工具箱中一个强大的工具。

# 16.10 集合 713

元素小于 "orange"。从 `TreeSet` 返回的视图通过 `printSet` 输出。如果对子集进行了任何更改，这些更改也将应用到原始 `TreeSet` 中，因为 `TreeSet` 返回的子集是 `TreeSet` 的视图。

第 25 行调用 `TreeSet` 方法 `tailSet` 以获取每个元素大于或等于 "orange" 的子集，并输出结果。通过 `tailSet` 视图进行的任何更改都会影响原始 `TreeSet`。第 28–29 行分别调用 `SortedSet` 方法 `first` 和 `last` 来获取集合中的最小和最大元素。

方法 `printSet`（第 33–39 行）接受一个 `SortedSet` 作为参数并打印它。第 35–36 行使用增强 `for` 语句打印 `SortedSet` 的每个元素。

```java
// Fig. 16.17: SortedSet.java
// Using SortedSets and TreeSets
import java.util.Arrays;
import java.util.SortedSet;
import java.util.TreeSet;
public class SortedSet {
    public static void main(String[] args) {
        // create TreeSet from array colors
        String[] colors = {"yellow", "green", "black", "tan", "grey", "white", "orange", "red", "green"};
        SortedSet<String> tree = new TreeSet<>(Arrays.asList(colors));
        System.out.print("sorted set: ");
        printSet(tree);
        // get headSet based on "orange"
        System.out.print("headSet(\"orange\"); ");
        printSet(tree.headSet("orange"));
        // get tailSet based on "orange"
        System.out.print("tailSet(\"orange\"); ");
        printSet(tree.tailSet("orange"));
        // get first and last elements
        System.out.printf("first: %s\n", tree.first());
        System.out.printf("last : %s\n", tree.last());
    }
    // output SortedSet using enhanced for for statement
    private static void printSet(SortedSet<String> set) {
        for (String s : set) {
            System.out.printf("%s ", s);
        }
        System.out.println();
    }
} // end class SortedSet
```

**Fig. 16.17** | 使用 SortedSets 和 TreeSets。（2 部分中的第 1 部分。）

```
sorted set: black grey orange red tan white yellow
headSet("orange"): black grey green
tailSet("orange"): orange red tan white yellow
first: black
last : yellow
```

**Fig. 16.17** | 使用 SortedSets 和 TreeSets。（2 部分中的第 2 部分。）

# 16.11 映射

`Map` 将键与值关联起来。`Map` 中的键必须是唯一的，但关联的值不需要唯一。如果一个 `Map` 同时包含唯一的键和唯一的值，则称它实现了一对一映射。如果键是唯一的，则称 `Map` 实现多对一映射——多个键可以映射到一个值。

`Map` 与 `Set`（集合）的区别在于，`Map` 包含键和值，而 `Set` 仅包含值。实现该接口的几个类中包括 `Hashtable`、`HashMap` 和 `TreeMap`。`Hashtable` 和 `HashMap` 将元素存储在哈希表中。本节将讨论哈希表，并提供了一个使用 `HashMap` 存储键值对的示例。`SortedMap` 扩展了 `Map` 并保持其键的排序顺序——可以是元素的自然顺序，也可以由 `Comparator`（比较器）指定的顺序。`TreeMap` 类实现了 `SortedMap`。

## 使用哈希表实现 Map

当程序创建对象时，它可能需要存储并检索它们。如果你的某些数据与键值匹配，且键是唯一的且紧密排列的，那么这种检索将是高效的。如果你有 100 名拥有九位社会安全号的员工，并想通过社会安全号作为键来存储和检索员工数据，该任务将需要一个超过 8 亿条目的数组，因为根据社会安全局网站，九位社会安全号必须以 001-899 开头（排除 666）。

> <http://www.security.gov/employer/randomization.html>

对于几乎所有使用社会安全号作为键的应用程序来说，这都是不实际的。程序如果有一个巨大的数组，仅仅通过使用社会安全号作为数组索引，来实现员工记录的高性能存储和检索。

许多应用程序都有这个问题——即要么键的类型错误（例如，不是可以转换为数组下标的正整数），要么类型正确但分布在一个巨大的范围内。我们需要的是一种高速方案，将像社会安全号、库存零件号之类的键转换为唯一的数组索引。然后，当应用程序需要存储某些东西时，该方案可以快速将应用程序的键转换为索引，记录就可以存储在数组的该槽位。检索的方法也是一样的：一旦应用程序获取了要检索数据记录的键，应用程序就对该键应用相同的转换版本——产生存储和检索该数据的数组索引。

我们在这里描述的方案是这种称为“哈希”（hashing）的技术的基础。为什么呢？当我们把一个键转换为数组索引时，我们实际上是在打乱位，形成一种“杂乱的”或已哈希的数字。这个数字在存储和检索特定数据记录的实用性之外，实际上没有真正的意义。

方案中的故障被称为“冲突”（collision）——当两个不同的键“哈希到”同一个单元格时就会发生。我们无法在同一个空间内存储两个值，因此我们需要为所有值找到一个替代方案。处理哈希表冲突最流行的方法是让表的每个单元格成为一个“桶”，通常是哈希到该单元格的键值对的链表。这种解决方案是 Java 的 `Hashtable` 和 `HashMap` 类（来自 `java.util`）实现的。`Hashtable` 和 `HashMap` 都实现了 `Map` 接口。它们的主要区别在于 `HashMap` 是不同步的（多个线程不应并发修改 `HashMap`）并且允许空键和空值。

表的负载因子影响哈希方案的性能。负载因子是哈希表中被占据单元格与总单元格数的比例。该比例越接近 1.0，冲突的可能性越大。

> ### 性能提示 16.2
>
> 哈希表中的负载因子是经典的空间/执行时间权衡；通过增加负载因子，我们获得了更好的内存利用率，但由于哈希冲突增加，程序运行变慢。通过降低负载因子，由于哈希减少，我们获得了更好的速度，但内存利用率较差。

计算机学生在名为“数据结构”和“算法”的课程中学习哈希方案。`Hashtable` 和 `HashMap` 允许你使用哈希而无需自己实现哈希表机制——这是重用的经典示例。这个概念在我们学习面向对象编程时极其重要。正如前面的章节所述，封装并隐藏复杂性（即实现细节），并提供友好的接口。正确构建类以展示行为是面向对象编程领域最受重视的技能之一。图 16.18 使用 `HashMap` 来统计字符串中每个单词的出现次数。

```java
// Fig. 16.18: WordTypeCount.java
// Program counts the number of occurrences of each word in a String.
import java.util.Map;
import java.util.HashMap;
import java.util.Set;
import java.util.TreeSet;
```

```java
import java.util.Scanner;
```

```java
public class WordTypeCount {

    public static void main(String[] args) {

        // create HashMap to store String keys and Integer values
        Map<String, Integer> map = new HashMap<>();

        // display map
        private static void displayMap(Map<String, Integer> map) {
            Set<String> keys = map.keySet();
            // sort keys
            TreeSet<String> sortedKeys = new TreeSet<>(keys);
            System.out.printf("%nMap contains:%n%s%n", "", "");
            // generate output for each key in map
            for (String key : sortedKeys)
                System.out.printf("%-10s%10s%n", key, map.get(key));
        }
    }
}
```

**图 16.18** 程序统计了字符串中每个单词出现的次数。（第 2 部分，共 3 部分）。

```java
        System.out.printf(
          "%nsize: %d%nEmpty: %b%n", map.size(), map.isEmpty());
    }
// end class WordTypeCount
```

输入一个字符串：

```
this is a sample sentence with several words this is another sample
sence with several different words
```

| Map 包含： | 数值 |
| --- | --- |
| a | 1 |
| another | 1 |
| different | 2 |
| is | 2 |
| sample | 2 |
| sentence | 2 |
| several | 2 |
| this | 2 |
| with | 2 |
| words | 2 |

```
size: 10
isEmpty: false
```

**图 16.18** | 程序统计了字符串中每个单词的出现次数。（第 3 部分，共 3 部分。）

第 14 行创建了一个空的 `HashMap`，具有默认的初始容量（16 个元素）和默认负载因子（0.75）——这些默认值是由 `HashMap` 的实现自动构建的。当 `HashMap` 中被占槽位数量大于容量乘以负载因子时，容量会自动翻倍。`HashMap` 是一个泛型类，接受两个类型——键（`String`）和值（`Integer`）。请记住，分配给泛型类的类型必须是引用类型，因此第二个类型参数是 `Integer` 而不是 `int`。

第 16 行调用了 `createMap`（第 21–44 行），它使用 `Map` 来存储字符串中每个单词的出现次数。第 25 行获取用户输入，第 28 行对其进行分词。第 31–43 行将文本转换为小写（第 33 行），然后调用 `Map` 方法 `containsKey`（第 36 行）来确定该单词是否在 map 中（以及是否之前在字符串中出现过）。如果 `Map` 不包含该单词，第 42 行使用 `Map` 方法 `put` 创建一个新条目，键为该单词，值为一个包含 1 的 `Integer` 对象。当程序将 1 传递给 `put` 方法时，会发生装箱，因为 map 以 `Integer` 存储出现次数。如果单词在 map 中，第 38 行使用 `Map` 方法 `get` 获取 map 中与键关联的值（计数）。第 39 行增加该值并使用 `put` 替换键的关联值。`put` 方法返回键的关联值或 `null`。

> **错误预防提示 16.2**
>
> 在 `Map` 中使用不可变键。键决定了相应的值是否被放置。如果键在插入操作后发生了变化，当你随后尝试检索该值时，可能无法找到。在本章的示例中，我们使用 `String` 作为键，而 `String` 是不可变的。

![](img/6851b408bcf88c7702f7d951642252f8_760_0.png)

`displayMap` 方法（第 47–62 行）显示 map 中的所有条目。它使用 `HashMap` 方法 `keySet`（第 49 行）获取键的集合。map 中的键是 `String`，因此方法 `keySet` 返回一个类型参数指定为 `String` 的泛型 `Set`。第 52 行创建了键的 `TreeSet`，在其中键被排序。第 57–58 行的循环处理了 map 中的每个键及其对应的值。第 58 行使用格式说明符 `%-10s` 将每个键左对齐，使用格式 `%10s` 将每个值右对齐。键按升序排列显示。第 61 行调用 `Map` 方法 `size` 来获取 map 中键值对的数量。第 61 行还调用了方法 `isEmpty`，返回一个指示 `Map` 是否为空的布尔值。

## 16.12 Properties 类
