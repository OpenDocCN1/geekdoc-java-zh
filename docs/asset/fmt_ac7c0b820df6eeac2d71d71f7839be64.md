
其中 `width` 是 width-length 字段中的值，`dashes` 是一个包含一个元素的数组，其值为在 dash-length 字段中指定的长度。`Panel` 和 `Stroke` 对象的构造函数在 `DrawPanel` 中创建形状时被新实例化。

## 改变差异

**13.32（针对视力障碍者的大字体显示器）** 随着这些工具在我们的职业和私人生活中发挥着重要作用，计算机和互联网对所有人（无论是否残障）的无障碍性变得越来越重要。根据世界卫生组织（www.who.int/mediacentheets/f28）最近的估算，全球有 2400 万人视力障碍。通过 web.com 上基于 GUI 的视力障碍模拟了解更多关于视力障碍的信息。视力障碍者在阅读电子文档和网页时倾向于使用更大的字体。Java 在使用 `Serif`、`Sans-serif` 和 `Monospaced` 时内置了“逻辑”字体。我们编写了一个使用 `JTextArea` 的 GUI 应用，用户可以在其中输入文本。允许用户从 `JComboBox` 中选择 `Serif`、`Sans-serif` 或 `Monospaced`。提供一个加粗复选框（Checkbox），如果勾选，则文本加粗。包含“增大字体”和“减小字体”的 `JButtons`，允许用户每次一磅地向上放大或缩小字体大小。从 18 磅字体开始。为了本次练习的目的，将 `JComboBox`、`JButtons` 和 `JCheckBox` 上的字体设置为 20 磅，以便视力障碍者能够阅读文本。

## 字符串、字符与正则表达式

> 亨利·金（Henry King）的主要缺陷是喜欢嚼小段绳子。
> —Hilaire Belloc
>
> 有力的写作是简洁的。一个句子不应包含不必要的单词，一个段落不应包含不必要的句子。
> —William Strunk, Jr.
>
> 我把这封信写得比平时长，是因为我没有时间把它写短。
> —Blaise Pascal

## 目标

在本章中，你将：

- 创建并操作 `String` 类的不可变字符串对象。
- 创建并操作 `StringBuilder` 类的可变字符串对象。
- 创建并操作 `Character` 类的对象。
- 使用字符串方法 `split` 将 `String` 对象拆分为标记。
- 使用正则表达式验证应用程序输入的 `String` 数据。

![](img/6851b408bcf88c7702f7d951642252f8_639_0.png)

## 14.1 引言

本章介绍了 Java 的字符串和字符处理能力。这里讨论的技术适用于验证输入、向用户显示信息以及其他文本处理。它们也适用于文本编辑器、文字处理器、排版软件、计算机排字系统和其他文本处理软件。我们在前面的章节中介绍了一些字符串处理能力。本章讨论了 `java.lang` 包中 `String`、`StringBuilder` 和 `Character` 类的细节——这些类提供了 Java 中字符串和字符操作的基础。本章还讨论了提供了输入验证能力的正则表达式，它们位于 `java.util.regex` 包中的 `Matcher` 和 `Pattern` 类。

## 14.2 字符与字符串的基础

字符是 Java 的基本单元。每个程序由一组字符组成——当有意义分组时——由编译器解释。字符串可能包含字母、数字以及如 `+`、`$` 等各种字符。字符串用双引号括起来。

| String | 说明 |
| :--- | :--- |
| "John. Doe" | 姓名 |
| "999 Main Street" | 地址 |
| "Waltham, Massachusetts" | 城市和州 |
| "(201) 555-1212" | 电话 |

字符是一个表示字符的对象。例如，`'z'` 代表字符 z，`'\t'` 代表制表符。字符串 `"blue"` 是字符串字面量的示例。字符串 `"blue"` 是字符序列。为了节省内存，Java 字符串字面量引用 `String` 对象。

![](img/6851b408bcf88c7702f7d951642252f8_641_0.png)

## 14.3 String 类

`String` 用于在 Java 中表示字符串。接下来的章节将涵盖 `String` 的功能。

### 14.3.1 String 构造函数

`String` 提供了多种初始化 `String` 对象的构造函数，如图 14.1 所示。

```java
// Fig.14.1: StringConstructors.java
// String 构造函数

public class StringConstructors {
    public static void main(String[] args) {
        char[] charArray = {'b', 'i', 'r', 't', 'h', ' ', 'd', 'a', 'y'};
        String s = new String("hello");

        // 使用 String 构造函数
        String s1 = new String();
        String s2 = new String(s);
        String s3 = new String(charArray);
        String s4 = new String(charArray, 6, 3);

        System.out.printf("s1 = %s%ns2 = %s%ns3 = %s%ns4 = %s%n", s1, s2, s3, s4);
    }
}
```

```
s1 = 
s2 = hello
s3 = birth day
s4 = day
```

图 14.1 | String 构造函数。

第 12 行使用 `String` 的无参构造函数实例化一个新的 `String`，并将其引用赋值给 `s1`。新的 `String` 对象不包含任何字符（即空字符串 `""`）且长度为 0。第 13 行使用接收 `String` 对象的构造函数实例化一个新的 `String` 对象，并将其引用赋值给 `s2`。新的 `String` 对象包含与作为参数的 String 相同的字符序列。

> **性能提示 14.2**
> 复制现有的 String 是必要的。String 对象是不可变的，因为 `String` 类没有提供在创建后修改 `String` 对象内容的方法。

第 14 行使用接收 char 数组作为参数的构造函数实例化一个新的 `String` 对象并将其引用赋值给 `s3`。新的 `String` 对象包含数组中字符的拷贝。第 15 行使用接收 `char` 和两个整数作为参数的构造函数实例化一个新的 `String` 对象并将其引用赋值给 `s4`。第二个参数指定了访问数组字符的起始位置（偏移）。记住第一个字符位于位置 0。第三个参数指定了在数组中访问的字符数（计数）。新的 `String` 对象由这些字符形成。如果作为参数的偏移或计数导致元素超出字符数组的边界，将抛出 `StringIndexOutOfBoundsException`。

### 14.3.2 String 方法 length, charAt 和 getChars

`String` 方法 `length`、`charAt` 和 `getChars` 返回字符串的长度、获取字符串中特定位置的字符，并从字符串数组中检索一组字符。图 14.2 展示了这些每个方法。

```java
// Fig.14.2: StringMiscellaneous.java
// 此应用程序演示了 length

public class StringMiscellaneous {
    public static void main(String[] args) {
        String s1 = "hello";
        char[] charArray = new char[5];

        System.out.printf("s1 = %s%nLength of s1: %d%n", s1, s1.length());

        // 反序打印字符串
        for (int count = s1.length() - 1; count >= 0; count--)
            System.out.printf("%c", s1.charAt(count));

        // 将字符从字符串拷贝到字符数组
        s1.getChars(0, 5, charArray, 0);
        System.out.printf("%ncharacter array is: %s%n", new String(charArray));

        for (char character : charArray)
            System.out.print(character);
    }
}
```

```
s1 = hello
Length of s1: 5
olleh
character array is: hello
hello
```

图 14.2 | 字符串方法 length，charAt 和 getChars。

第 15 行使用字符串方法 `length` 来确定字符串 s1 中的字符数量。像数组一样，字符串知道自己的长度。然而，与数组不同，你通过类方法 `length` 来访问字符串的长度。

第 20–21 行按反序打印字符串 s1 的字符。字符串方法 `charAt`（第 21 行）返回字符串中特定位置的字符。`charAt` 方法接收一个整数作为索引，并返回该位置的字符。与数组一样，字符串的第一个元素位于位置 0。

第 24 行使用字符串方法 `getChars` 将字符串的字符拷贝到字符数组中。第一个参数是开始拷贝的字符的起始索引。第二个参数是字符串中要拷贝的最后一个字符之后的索引。第三个参数是待将字符拷贝入的字符数组。最后一个参数是拷贝的字符被放置在目标字符数组中的起始索引。接下来，第 27–28 行逐个字符地打印字符数组的内容。

## 14.3.3 比较字符串

第 19 章讨论了数组的排序和搜索。经常，被搜索的信息由字符串组成，这些字符串必须经过排序以将它们就绪，或者判断某个字符串是否出现在数组（或其他集合）中。`String` 类提供了比较字符串的方法，如接下来两个示例所示。

为了理解一个字符串大于或小于另一个字符串意味着什么，请考虑对一系列名称按字母排序的过程。现在，你不会怀疑 "Jones" 在 "Smith" 之前在字母表中排在 "Smith" 的字母之前。字母表不仅仅是 26 个字母列表——它是一个有序的字符列表。每个字母在列表中都有特定的位置。Z 不仅仅是字母表中的一个字母——它具体是字母表中的第 26 个字母。

计算机如何知道一个字母在另一个“之前”？所有字符在计算机中都用数字代码表示（参见附录 B）。当计算机比较字符串时，它实际上比较的是字符串中字符的数字代码。

图 14.3 展示了使用等等运算符 `==` 比较字符串的字符串方法 `equals`、`equalsIgnoreCase`、`compareTo` 和 `regionMatches`。

```java
// Fig.14.3: StringCompare.java
// 字符串方法 equals, equalsIgnoreCase, compareTo 和 regionMatches

public class StringCompare {
    public static void main(String[] args) {
        String s1 = new String("hello"); // s1 是 "hello" 的拷贝
        String s2 = "goodbye";
        String s3 = "Happy Birthday";
        String s4 = "happy birthday";

        System.out.printf("s1 = %s%ns2 = %s%ns3 = %s%ns4 = %s%n", s1, s2, s3, s4);

        // 测试 equals("hello")
        if (s1.equals("hello")) // true
            System.out.println("s1 equals \"hello\"");
        else
            System.out.println("s1 does not equal \"hello\"");

        // 测试相等性 ==
        if (s1 == "hello") // false;它们不是同一个对象
            System.out.println("s1 is the same object as \"hello\"");
        else
            System.out.println("s1 is not the same object as \"hello\"");

        // 测试 equalsIgnoreCase(忽略大小写)
        if (s3.equalsIgnoreCase(s4)) // true
            System.out.printf("%s equals %s with case ignored%n", s3, s4);
        else
            System.out.println("s3 does not equal s4");

        // 测试 compareTo
        System.out.printf("s1.compareTo(s2) is %d%n", s1.compareTo(s2));
        System.out.printf("s2.compareTo(s1) is %d%n", s2.compareTo(s1));
        System.out.printf("s1.compareTo(s1) is %d%n", s1.compareTo(s1));
        System.out.printf("s3.compareTo(s4) is %d%n", s3.compareTo(s4));
        System.out.printf("s4.compareTo(s3) is %d%n", s4.compareTo(s3));
    }
}
```

图 14.3 | 字符串方法 equals, equalsIgnoreCase, compareTo 和 regionMatches。
