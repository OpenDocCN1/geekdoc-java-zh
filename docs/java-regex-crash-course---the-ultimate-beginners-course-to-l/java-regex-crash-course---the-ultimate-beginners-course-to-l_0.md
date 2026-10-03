
# Java：正则表达式速成班——在 12 小时内学习 Java 正则表达式的终极初学者指南

![](img/cover.jpeg)

© 版权所有 2015

版权所有。未经出版者许可，不得以机械、电子或任何其他方式（包括复印）复制本书的任何部分。

## 免责声明

本书中提供的信息旨在为所讨论的主题提供有用的参考。作者的书仅旨在为读者提供 Java 正则表达式的基础知识，对于学生是否能够整合和应用所提供的所有信息不作任何保证。尽管作者将尽最大努力分享其见解，但本书或作者的任何书籍均不构成将在特定时间内学会 Java 正则表达式的承诺。书中插图仅供参考。

# 第 19 章：Eclipse 中的正则表达式

# 第 20 章：结语

# 《Python 快速入门教程》预览 - 在不到 12 小时内学会 Python 编程的终极初学者课程

# 关于作者

献给那些对生活有更高追求并下决心实现目标的人。

永不停学习，

![C:\Users\Usuario\Documents\kdp\Bastiat books\Logo Eprogramy final.jpg](http://www.amazon.com/Eprogramy/e/B00Y9CTNTO)

# 在亚马逊上查看完整的编程系列

## Java 速成 - 在 12 小时内学会 Java 编程的终极初学者课程

![Java 速成](http://www.amazon.com/Java-Ultimate-Beginners-Learning-Programming-ebook/dp/B00Y96U1D2)

## JavaScript 速成 - 在 12 小时内学会 JavaScript 编程的终极初学者课程

![JavaScript 速成](http://www.amazon.com/JavaScript-Ultimate-Beginners-Learning-Programming-ebook/dp/B00YQB5JPK/)

## C 速成 - 在 12 小时内学会 C 编程的终极初学者课程

![C 速成](http://www.amazon.com/Course-Ultimate-Beginners-Learning-Programming-ebook/dp/B012C4AO02)

## SQL 速成 - 在 12 小时内学会 SQL 编程的终极初学者课程

![SQL 速成](http://www.amazon.com/SQL-Ultimate-Beginners-Learning-Programming-ebook/dp/B0113EC6CG/)

[这些只是我们的书籍的一部分。点击此处查看完整系列！](http://www.amazon.com/Eprogramy/e/B00Y9CTNTO)

# 引言：欢迎来到正则表达式终极速成课程

所以，你决定学习 Java 正则表达式了吗？很好，恭喜你，欢迎来到你的速成语言课程！你会喜欢它的！

在 Eprogramy，我们相信，良好教育的基础是提供能够开启未来之门的工具。不可否认，世界已经进入了一个我们一切触手可及的时代。社会需求发生了变化。因此，今天的通信也发生了变化。通信开启了大门，所以学习如何通信是我们的挑战。在 Eprogramy，我们希望你学会用一种新语言通信：编程语言。这种语言允许我们使用电脑或笔记本电脑进行创作。

也许道路是艰难的，但我们将为读者提供工具，让学习变得愉快且富有成效。我们将展示学习编程的所有必要方面。从基础知识到解决最常见的编程问题以及更多更多。我们将辅以大量的示例，这将有助于更好地理解。

我们清楚自己在做什么，并相信你完全有能力吸收我们的教学。

未来的大门已经开启。让我们一起一步来。

让我们开始吧！

Eprogramy 团队

# 第 1 章：我们的 Java 正则表达式第一步

## 什么是正则表达式？

在当今世界，几乎所有的应用程序都需要处理文本用于搜索和验证。这个过程通常涉及复杂的逻辑，并可能导致许多复杂且混乱的代码，非常难以理解。

正则表达式或 `REGEX` 被解释为特定的文本模式，可以用于许多高级应用程序，并适用于任何编程语言。它们被用于搜索、编辑和处理数据。

例如，使用正则表达式我们可以验证特定的输入字符串是否匹配给定的文本模式，或者从大量字符中找到一组字符。它们还用于替换和重排文本块，或将大块数据分成较小的子集。正则表达式通常不是特定语言的，在大多数编程语言中遵循类似的模式，但会有细微差异。

正则表达式是强大的工具，可以减少处理时间。通过熟练地使用它们，我们可以完成原本无法实现的任务。

示例：

假设我们需要验证以下电子邮件。

```
emailid = "xyz@abc.com"
```

验证所需的步骤：

1. 必须有一个 `@` 符号。

2. `@` 之前的文本必须只包含字符、数字、下划线和连字符。

3. 电子邮件中不有两个 `@` 符号。

4. 在 `@` 符号之后的域名中应该有一个 `.`。

5. 它应该以 2 或 3 个字符结束。

如果你需要在不使用正则表达式的情况下验证上面的电子邮件，程序将需要数百行代码。

```java
package com.sample.regexsample;

public class Validte {
    public static void main(String[] args) {
        String str1 = "myname@abc.com";
        int x = str1.indexOf("@"); // 返回子字符串第一个字符的索引
        System.out.println("index = " + x);
    }
}
```

输出：

`Index = 6.`

一旦获取索引，还需要进一步的计算来确定域名中是否有一个或多个字符，后面跟着 `.` 符号。这就是正则表达式发挥重要作用的地方。我们可以使用正则表达式模式仅一行代码即可完成它。

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class EmailValidator {
    public static void main(String[] args) {
        String input = "^[_A-Za-z0-9\\+]+([\\.[A-Za-z0-9-]+)*@[A-Za-z0-9-]+(\\.[A-Za-z0-9]+)*(\\.[A-Za-z]{2})$";
        String emailAddress ="xyz@abc.com";
        Pattern p = Pattern.compile(input);
        Matcher m = p.matcher(emailAddress);
        System.out.println ("The email 1 matches:" + m.matches());
    }
}
```

## 常见用途

正则表达式广泛用于各种文本处理任务，更广泛用于字符串处理，其中数据不需要是文本。常见的应用包括数据验证、数据爬取、数据清洗、简单解析、语法高亮系统的生成以及许多其他任务。

虽然正则表达式在网络搜索引擎中非常有用，但根据 `regex` 的复杂性和设计，在整个数据库中处理它们可能会消耗大量的计算机资源。

正则表达式的一些重要用途包括：

1. URL 验证

2. 邮箱验证

3. 数字、字符和特殊字符的验证

4. 互联网地址

5. 从文本中提取信息，如代码、日志文件、电子表格或文档。

6. 字符串的搜索与替换

**注意：**

- 请记住，在使用正则表达式时，本质上一切都是字符，我们正在编写模式来匹配特定的字符序列（也称为字符串）。

- 通常提供的模式是 ASCII 字符，包括字母、数字、标点符号和其他键盘符号 `%#@`。

- Unicode 字符用于匹配任何类型的文本。

## 理解正则表达式引擎

最重要的事情之一是观察正则表达式的工作原理，因为了解引擎如何工作将帮助我们更容易编写更好的 `regexes`。这有助于理解特定的 `regex` 如何以预期的方式工作，从而节省大量的猜测。编写复杂的 `regexes`。

正则表达式有两种：

1. 文本驱动型引擎（text-directed engines）

2. 正则驱动型引擎（regex-directed engines）

大多数 `regex` 变体都基于正则驱动型引擎。因为某些非常有用的功能，如懒惰量化（lazy quantifiers）和反引用（back references），只能在正则驱动型引擎中实现。

你可以轻松判断要使用的 `regex` 变体是文本驱动还是正则驱动的。如果可以使用反引用或懒惰量化，你可以确定引擎是正则驱动的。

你可以通过将 `regex` 应用于字符串 `text` 来进行测试，如果结果是 `text`，那么它是文本驱动的。如果结果是 `text`，那么它是正则驱动的。这背后的原因是正则驱动型引擎是一个起点。

在查看示例之前，理解正则表达式的工作原理将让你能够利用其全部功能并避免常见的错误。

### 正则驱动型引擎始终返回最左匹配

在处理引擎时，需要注意一些重要点：

- 正则驱动型引擎始终返回最左匹配，即使以后可以找到合适的匹配。

- 当将 `regex` 应用于字符串时，引擎将从字符串的第一个字符开始。它将尝试正则表达式在第一个字符的所有变。只有当所有可能性都尝试过并失败后，引擎才会继续处理第二个字符。

- 再次，它将按照相同的顺序尝试 `regex` 的所有变，直到找到匹配。

- 结果是正则驱动型引擎将返回最左匹配。

- 让我们考虑这个例子，搜索 `book` 到 `He bought a bookshelf for his.`。引擎将尝试在第一个字符匹配 `regex` `b`。这失败了。`regex` 没有其他可能的，因为它仅仅由字面字符序列组成。所以正则表达式引擎尝试用 `e` 匹配 `b`。这也失败了，正如用空格匹配 `b` 一样。到达匹配的第 4 个字符，`b` 匹配了 `b`。引擎将尝试匹配第二个 token `o` 到第 5 个字符 `o`。这也成功了。但随后，`o` 无法匹配 `u`。在这一点，引擎知道无法从第 4 个字符开始匹配 `regex`。它将继续第 5 个：`a`。再次，`b` 在此处无法匹配，引擎继续。在匹配的第 30 个字符处，`b` 再次匹配了 `b`。

- 引擎接着尝试在第 30 个字符处匹配 `regex` 的剩余部分，发现 `o` 匹配 `o`，再次 `o` 匹配 `o` 且 `k` 匹配 `k`。完整的 `regex` 可以从第 30 个字符开始匹配。引擎是报告匹配的起点。因此它会将 `catfish` 的前三个字母作为有效匹配。引擎不会继续此后以查看是否有“更好”的匹配。在引擎内部的第一个示例中，我们的正则表达式引擎看起来运行就像一个普通的文本搜索程序。

文本驱动型引擎也会返回相同的结果。然而，重要的是你可以在脑海中遵循引擎采取的步骤。在接后的示例中，引擎的工作方式会对它找到的匹配产生深远影响。某些结果可能会令人惊讶。但一旦你知道引擎如何工作，它们总是符合逻辑且预先定的。

## 正则表达式使用的算法

在使用 `regex` 时，至少有三种不同的算法来决定给定的正则表达式是否以及如何匹配字符串。

### 将 NFA 转换为 DFA

这是第一个且最快的方法。它基于形式语言理论中的结果，该结果允许每个非确定性有限自动机（NFA）变为确定性有限自动机（DFA）。可以显式构建 `DFA`，然后对生成的输入字符串逐一个符号地运行。

### 直接模拟 NFA（DFA/NFA 算法）

一种方法是直接模拟 `NFA`，根据需要构建每个 `DFA` 状态，然后在下一个执行步骤将其丢弃。这种方法保持 `DFA` 隐式，避免了构建成本的指数级增长，但带来了运行成本增加到 `O(m n)` 的开销。显式和隐式方法分别称为 `DFA` 算法和 `NFA` 算法。

### 回溯

第三种也是最后的算法是通过回溯与输入字符串匹配模式。这种算法通常被称为 `NFA`，但这个术语有时会引起混淆。这被用于简单的实现，体现在匹配如 `(a|aa)*b` 这种包含交替和无界量化的表达式时。这种处理可能会强制算法考虑数量指数级增长的子用例。这可能还会导致被称为“正则表达式拒绝服务”（ReDoS）的安全问题。

# 第 2 章 正则表达式使用的基本字符

## 常见的正则表达式语法

正则表达式是底部表示文本的字符串模式。这些描述可以用多种方式应用。基础语言结构包括字符类、量化符和元字符。下面的章节解释了定义正则表达式的各种选项。

### 1.1 字符串字面量

字符串字面量用于在文本中搜索特定的匹配。例如，如果我们搜索文本 `test`，可以简单地写代码：这里文本和正则是相同的。

```
Pattern.matches("test", "test")
```

### 1.2 字符类

字符类用于将输入文本中的单个字符匹配字符类中的多个允许字符。字符类与 Java 中的类构造或类文件没有关系。

示例：

1. `[Tt]est` 将匹配字符串 `test` 的所有出现，无论是小写还是大写的 `T`。

2. `"WEB@JDOJO.COM"` 匹配模式 `[ABC]@`，因为 `@` 前面是 `B`。

3. 字符串 `"A@BAND@YEA@U"` 两次匹配模式 `[ABC]@.`，即使字符串包含三个 `@` 符号。

4. 第二个 `@` 不是匹配的一部分，因为它前面是 `D` 而不是 `A, B, 或 C`。

更多示例：

`Pattern.matches("[pqr]", "abcd");` 将返回 false，因为文本中没有 p、q 或 r。

`Pattern.matches("[pqr]", "r");` 返回 true，因为找到了 r。

`Pattern.matches("[pqr]", "pq");` 返回 false，因为文本中可以包含其中一个，但不能两个都包含。

元字符 `[` 和 `]`（左括号和右括号）用于在正则表达式中指定字符类。有时，我们将产生匹配的字符限制在一个特殊的字符集内。以下是各种字符类构造的示例列表：

1. **简单（Simple）**：由一组并排设置的字符组成，仅匹配这些字符。例如：`[abc]` 匹配字符 a、b 和 c。

   让我们来看下面的例子：

   `[csw]` cave 匹配 `[csw]` 中的 `c`，对应 `cave` 中的 `c`。

2. **否定（Negation）**：以元字符 `^` 开头，仅匹配不在该类中的字符。

   例如：`[^abc]` 匹配除 a、b 和 c 以外的所有字符字符。

   我们来看第二个例子：

   `[^csw]` cave 匹配 `a`、`v` 和 `e`，对应 `cave` 中的对应字符。

3. **范围（Range）**：涉及从连字符元字符（`-`）左侧字符到连字符元字符右侧字符的所有字符，仅匹配该范围内的字符。

   例如：`[a-z]` 匹配所有小写字母。

   我们来看另一个例子：

   `[a-c]` clown 匹配 `[a-c]` 中的 `c`，对应 `clown` 中的 `c`。

4. **并集（Union）**：涉及多个嵌套的字符类，并匹配所有符合结果并集的字符。

   例如：`[a-d[m-p]]` 匹配从 `a` 到 `d` 以及 `m` 到 `p` 的字符。

   我们来看第二个例子：

   `[ab[c-e]]` abcdef 匹配 `a`、`b`、`c`、`d` 和 `e`，对应 `abcdef` 中的对应字符。

5. **交集（Intersection）**：涉及所有嵌套类中常见的字符，并仅匹配共同字符。

   例如：`[a-z&&[d-f]]` 匹配字符 `d`、`e` 和 `f`。

   其他例子：

   `[aeiouy&&[y]]` party 匹配 `[aeiou&&[y]]` 中的 `y`，对应 `party` 中的 `y`。

6. **减法（Subtraction）**：涉及所有字符减去嵌套否定字符类中指定的字符，并匹配剩余字符。

   例如：`[a-z&&[^m-p]]` 匹配从 `a` 到 `l` 以及 `q` 到 `z` 的字符。

   以下命令行提供了第二个例子：

   `[a-f&&[^a-c]&&[^e]]` abcdefg 匹配 `d` 和 `f`，对应 `abcdefg` 中的对应字符。

## 预字符类

| 字符 | 解释 |

| :--- | :--- |

| `.` | 等于点，任意字符（可能匹配也可能不匹配终止符） |

| `\d` | 等于数字：`[0-9]` |

| `\D` | 等于非数字：`[⁰-9]` |

| `\s` | 等于空白字符：`[ \t\n\x0B\f\r]` |

| `\S` | 等于非空白字符：`[^\s]` |

| `\w` | 等于单词字符 |

| `\W` | 等于非单词字符 |

| `\A` | 等于字符串开头。 |

| `\Z` | 等于字符串结尾。 |

然而；在 Java 中，你需要对这些反斜杠进行“双重转义”。

`String pattern = "\\d \\D \\W \\w \\S \\s";`

例如：

`Pattern.matches("\\d", "1");` 将返回 true。

`Pattern.matches("\\D", "z");` 返回 true。

`Pattern.matches(".p", "qp");` 返回 true，点(`.`) 代表任意字符。

## 边界匹配器

| 表达式 | 解释 |

| :--- | :--- |

| `^` | 等于行开头。 |

| `$` | 等于行结尾。 |

| `\b` | 等于单词边界。 |

| `\B` | 等于非单词边界。 |

| `\A` | 等于输入文本的开头。 |

| `\G` | 等于上一次匹配的结尾 |

| `\Z` | 等于输入文本的结尾除去最后的终止符 |

| `\z` | 等于输入文本的结尾 |

例如：

`Pattern.matches("^Hello$", "Hello")`: 返回 true，以 Hello 开头并结尾



`Pattern.matches("^Hello$", "Namaste!")`: 返回 false，不以 Hello 开头

`Pattern.matches("^Hello$", "Hello Namaste!")`: 返回 false，不以 Hello 结尾

## 量词

量词是一种将数值值与模式绑定的正则表达式构造。量词会对其左侧的表达式进行循环。该数值值确定了匹配模式的次数。我们有六种主要的量词，可以在三个类别中重复出现：贪婪、懒惰和占有。

### 贪婪量词（Greedy Quantifiers）

贪婪量词将匹配与模式最长的字符串。

| 量词 | 解释 |
| :--- | :--- |
| `?` | 一次或无 |
| `*` | 零或多次 |
| `+` | 一次或多次 |
| `{n}` | 精确 n 次 |
| `{n,}` | 至少 n 次 |
| `{n,m}` | n 次到 m 次 |

### 懒惰量词（Reluctant Quantifiers）

懒惰量词用于匹配最短的字符串。

| 量词 | 解释 |
| :--- | :--- |
| `??` | 一次或无 |
| `*?` | 零或多次 |
| `+?` | 一次或多次 |
| `{n}?` | 精确 n 次 |
| `{n,}?` | 至少 n 次 |
| `{n,m}?` | n 次到 m 次 |

### 占有量词（Possessive Quantifiers）

占有量词将匹配整个字符串。

| 量词 | 解释 |
| :--- | :--- |
| `?+` | 一次或无 |
| `*+` | 零或多次 |
| `++` | 一次或多次 |
| `{n}+` | 精确 n 次 |
| `{n,}+` | 至少 n 次 |
| `{n,m}+` | n 次到 m 次 |

### 量词示例代码

```java
package sample.regex;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForQuantifiers {
    static void main(String[] args) {
        String regex = "a?"; // 一次或无
        String regex1 = "a*"; // 零或多次
        String regex2 = "a+"; // 一次或多次
        String regex3 = "a{2}"; // 精确 n 次
        String regex4 = "a{2,}"; // 至少 n 次
        String regex5 = "a{2,4}"; // n 次到 m 次
        String regex6 = "a+"; // 

        System.out.println(Pattern.matches(regex, "ab")); // 返回 true，匹配一个 a 
        System.out.println(Pattern.matches(regex1, "aaaa")); // 返回 true，匹配多个 a
        System.out.println(Pattern.matches(regex2, "b")); // 返回 false，没有 a

        // 贪婪与懒惰的对比
        String text = "aaaaa";
        Matcher m1 = Pattern.compile("a*").matcher(text);
        while (m1.find()) {
            System.out.println(m1.group()); // 贪婪会匹配尽可能多的
        }

        Matcher m2 = Pattern.compile("a*?").matcher(text);
        while (m2.find()) {
            System.out.println(m2.group()); // 懒惰会匹配最少的
        }
    }
}
```

```java
System.out.println("Start index-->"+m3.start()+"End index-->"+m3.end());
}
System.out.println("-----------------------------------------------");
while(m4.find()) {
    System.out.println("Start index-->"+m4.start()+"End index-->"+m4.end());
}
System.out.println("-----------------------------------------------");
while(m5.find()) {
    System.out.println("Start index-->"+m5.start()+"End index-->"+m5.end());
}
System.out.println("-----------------------------------------------");
while(m6.find()) {
    System.out.println("Start index-->"+m6.start()+"End index-->"+m6.end());
}
System.out.println("-----------------------------------------------");
while(m7.find()) {
    System.out.println("Start index-->"+m7.start()+"End index-->"+m7.end());
}
System.out.println("-----------------------------------------------");
while(m8.find()) {
    System.out.println("Start index-->"+m8.start()+"End index-->"+m8.end());
}
System.out.println("-----------------------------------------------");
```

## 特殊构造

| 构造 | 解释 |
| :--- | :--- |
| `(?<name>X)` | `X`，作为命名捕获组 |
| `(?:X)` | `X`，作为非捕获组 |
| `(?flags)` | 无，但用于开启或关闭标记 |
| `(?flags:X)` | `X`，作为带有给定标记的非捕获组 |
| `(?=X)` | `X`，通过零宽正向断言 |
| `(?!X)` | `X`，通过零宽负向断言 |
| `(?<=X)` | `X`，通过零宽正向后逆推 |
| `(?<!X)` | `X`，通过零宽负向后逆推 |
| `(?>X)` | `X`，作为独立的非捕获组 |

## 正则示例

### 表达式

在 Java 中，每个字符串都是正则表达式。例如，字符串 `"I have a car"` 是一个正则，它会匹配文本 `"I have a car"`，而忽略其他所有内容。

如果我们想让别人知道更多我们拥有的东西怎么办？我们可以将单词 `car` 替换为字符类表达式，它可以匹配任何字符：`I have a \w+`。

你会注意到，在这个模式中同时使用了字符类和量词。`\w` 表示匹配一个单词字符，而 `+` 表示匹配一个或多个。结合在一起时，该模式的意思是“匹配一个或多个单词字符”。现在，该模式将匹配替代 `car` 的任何单词，例如 `"I have a book"` 或 `"I have a dress"`。

但如果我们需要验证 `"I have a: boat"`，它将无法匹配，因为存在 `:` 符号，而它不是一个单词字符。如果我们想让表达式能够处理这种情况，那么我们需要做一个微小的更改：`I have a:?\w+`。

现在，该表达式将允许一个可选的 `:`，紧接着是单词 'a'。

#### 分组

分组是正则表达式中的一个重要事项。它是将模式的部分组合起来并提供不同匹配的能力。以下元字符是正则表达式的重要部分：

| 分选择 (`or` 语句) | 分组 |
| :--- | :--- |
| `\|` | `()` |

例如，在第一个例子中，我们有一辆车。如果我们知道需要告诉世界的对象列表且外无其他内容呢？让我们使用分组 `()` 配合 `\|` 元字符来设置一个允许的表达式列表：`I have a:?(car\|dress\|pen)`。

现在新表达式等于起点 `"I have a"`，一个可选的 `:`，然后是由 `\|` 分隔的表达式之一；`car`、`dress` 或 `pen` 中的任何一个都将匹配。

- `I have a car` 匹配
- `I have books` 匹配（不需要 `s`，被忽略了）
- `I have: car` 匹配
- `I have- car` 不匹配（模式中不允许出现 `-`）
- `I have: bo` 不匹配（需要完整的 `book`）

#### 示例

```java
package com.sample.regexsample;
import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class DemoGrouping {
    public static void main(String[] args) {
        String text = "John writes about this, and John writes about that, and John writes about everything.";
        String patternString1 = "(John)";
        Pattern pattern = Pattern.compile(patternString1);
        Matcher matcher = pattern.matcher(text);
        while(matcher.find()) {
            System.out.println("found: " + matcher.group(1));
        }
    }
}
```

**输出：**

```
found: John
found: John
found: John
```

### 匹配/验证

使用正则表达式，可以找到匹配特定模式的文本实例，并在找到/未找到模式时返回一个布尔值。

#### 示例：

```java
package com.sample.regexsample;
import java.util.ArrayList;
import java.util.List;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class ValidateSSN {
    public static void main(String[] args) {
        List<String> input = new ArrayList<String>();
        input.add("123-45-6789");
        input.add("9876-5-4321");
        input.add("987-65-4321 (attack)");
        input.add("987-65-4321 ");
        input.add("192-83-7465");
        String patternString = "^(\\d{3}-?\\d{2}-?\\d{4})$";
        Pattern pattern = Pattern.compile(patternString);
        for (String ssn : input) {
            if (ssn.matches("^(\\d{3}-?\\d{2}-?\\d{4})$")) {
                Matcher m = pattern.matcher(ssn);
                if (m.find()) {
                    System.out.println("Found good SSN: " + ssn);
                }
            }
        }
    }
}
```

这是使用了正则类的 `Pattern` 和 `Matcher` 方法的代码。

**输出：**

```
Found good SSN: 123-45-6789
Found good SSN: 192-83-7465
```

示例中所使用的模式解释：

`^(\\d{3}-?\\d{2}-?\\d{4})$`

- `^` 等于行的开头
- `()` 将括号内的所有内容作为第 1 组
- `$` 等于行的结尾
- `\d{n}`: 等于 `n` 个数字，其中 `n` 是大于或等于零的数字
- `-?`: 可选匹配一个连字符
- `$`: 匹配行尾

### 提取/捕获

正则表达式可以用于从大型复杂的文本正文中选择特定的值。

#### 示例代码：

```java
package com.sample.regexsample;

import java.util.ArrayList;
import java.util.List;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class SampleGrouping {
    public static void main(String[] args) {
        String input = "I have a kindle, but I like to read book better.";
        Pattern p = Pattern.compile("(kindle|read|book|wolf|bear|human)");
        Matcher m = p.matcher(input);
        List<String> animals = new ArrayList<String>();
        while (m.find()) {
            System.out.println("Found a " + m.group() + ".");
            animals.add(m.group());
        }
    }
}
```

**输出：**

```
Found a kindle.
Found a read.
Found a book.
```

所用模式的解释：

`"(kindle|read|book|wolf|bear|human)"`

- `()` 将括号内的所有内容捕获为第 1 组
- `kindle`: 匹配文本 ‘kindle’
- `\|`: 分选择：匹配此组中的任意一个部分
- `read`: 匹配文本 ‘read’
…… 依此类推

### 修改/替换

使用正则表达式，可以将文本中的值替换为新值。让我们看看，你可以将所有 `userId=` 后面跟数字的实例替换为“***masked***”以隐藏原始文本。

#### 示例代码：

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class MaskingDemo {
    public static void main(String[] args) {
        String input = "User userId=23421\\. Some more userId=33432\\. This is userNum=100";
        Pattern p = Pattern.compile("(userId=)(\\d+)");
        Matcher m = p.matcher(input);
        StringBuffer result = new StringBuffer();
        while (m.find()) {
            System.out.println("Masking: " + m.group(2));
            m.appendReplacement(result, m.group(1) + "***masked***");
        }
        m.appendTail(result);
        System.out.println(result);
    }
}
```

**输出：**

```
Masking: 23421
Masking: 33432
User userId=***masked***. Some more userId=***masked***. This is userNum=100
```

#### 模式解释

`(userId=)(\\d+)`

- `(userId=)` 将括号内的所有内容捕获为第 1 组
- `userId=` 等于文本 `userId=`
- `(\\d+)` 将括号内的所有内容捕获为第 2 组
- `\d+` 等于一个或多个数字

### 匹配多个中的其一

使用 `[]` 元字符和不同的字符组合，我们可以匹配存在的字符中的一个。例如，让我们创建一个正则表达式来匹配像 cat、bat、rat 这样的拼写。

示例：`(b|m|r)[a][ts]`

#### 示例代码：



```java
package com.sample.regexsample;
import java.util.ArrayList;
import java.util.List;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class SampleGrouping {
    public static void main(String[] args) {
        String input = "I have a cat, dog, mat and rat.";
        Pattern p = Pattern.compile("(c|d|r)[a][ts]");
        Matcher m = p.matcher(input);
        List<String> animals = new ArrayList<String>();
        while (m.find()) {
            System.out.println("Found a " + m.group() + ".");
            animals.add(m.group());
        }
    }
}
```

输出:

```
Found a cat.
Found a mat.
Found a rat.
```

### 使用特殊构造

当我们需要在字符串中查找某段文本出现在另一个模式之前的文本时，或者查找一段后面没有跟随另一个片段的文本时，就会使用特殊构造。通常，使用标准字符串搜索，我们需要编写相当复杂的函数来执行你想要精确的操作。然而，使用正则表达式可以在一行内完成所有这些操作。

### 前瞻与后溯

向前瞻和向后后溯的操作与分组类似，但这些模式不会捕获值。因此，使用这些构造时，没有值会被存储供以后使用，而且它们不会影响分组编号。前瞻操作向前看，从它们在模式中的位置开始，一直到输入的结束。后溯表达式不向后搜索，而是从模式的开始继续向上/直到后溯表达式。

例如：

我们需要确保输入字符串中必须存在 `incident` 单词，但在任何地方都不应该找到 `theft` 单词。我们可以使用否定前瞻来确保没有出现。

`(?!.*theft).*incident.*`

此表达式表现出以下行为：

- `"There was a crime incident"` 匹配
- `"The incident involved a theft"` 不匹配
- `"The theft was a serious incident"` 不匹配

前瞻和后溯的类型有：正向前瞻和否定前瞻。

### 正向前瞻

当我们要查找某段文本出现在字符串中另一个模式之前的文本时，使用正向前瞻。

#### 正向前瞻示例

```java
package com.sample.regexsample;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoPositiveAhead {
    public static void main(String[] args) {
        String regex = "(?=²⁵⁵).*";
        Pattern p = Pattern.compile(regex);
        String candidate = "255.0.1";
        Matcher m = p.matcher(candidate);
        String ip = "not found";
        if (m.find()) {
            ip = m.group();
            String msg = "ip: " + ip;
            System.out.println(msg);
        }
    }
}
```

输出：

```
ip: 255.0.1
```

#### 模式解释

`(?=²⁵⁵).*`

- `(?=²⁵⁵)` 表示正向前且以 255 开始
- `.*` 可以跟随任何内容

### 否定向前瞻

当我们要匹配后面没有跟随某内容的文本时，使用否定向前瞻。

#### 否定向前瞻示例代码

```java
package com.sample.regexsample;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoNegativeAhead {
    public static void main(String[] args) throws Exception {
        String regex = "John (?!Heins)[A-Z]\\w+";
        Pattern p = Pattern.compile(regex);
        String candidate = "I think that John Heins is a fictional character. His real name might be John Jackson, John Westling, or John Holmes for all we know.";
        Matcher m = p.matcher(candidate);
        String tmp = null;
        while (m.find()) {
            tmp = m.group();
            System.out.println("MATCH:" + tmp);
        }
    }
}
```

输出

```
MATCH:John Jackson
MATCH:John Holmes
```

#### 解释模式

`"John (?!Heins)[A-Z]\\w+"`

- `John`: 模式以 John 开始
- `(?!Heins)`: 它不包含 Heins 单词
- `[A-Z]\\w+`: John 后面应该跟一个以大写字母开头的单词，随后是任意单词。

### 正向后溯

当我们要匹配一个前面应该是某些模式或字符串的文本时，使用正向后溯。

#### 正向后溯示例

```java
package com.sample.regexsample;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemooforPositiveLookBehind {
    public static void main(String[] args) {
        String reg = "(?<=http://)\\S+";
        Pattern p = Pattern.compile(reg);
        String str = "http://www.a.com. My name";
        Matcher m = p.matcher(str);
        while (m.find()) {
            String msg = ":" + m.group() + ":";
            System.out.println(msg);
        }
    }
}
```

输出:

```
:www.a.com.:
```

#### 解释模式

`(?<=http://)\\S+`

> 后行查找——从 `http://` 开始直到遇到空白字符。即要检查的字符串前面应该是 `http://`。

### 否定向后零视

当你想要匹配前面不是某某些内容的内容时，就会使用否定向后零视。

#### 否定向后零视示例

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForNegativelookBehind {
    public static void main(String[] args) {
        Pattern p = Pattern.compile("(?<!Y.{0,40})X");
        String txt = "Y less than 40 before X"; // 因为你想要'不'，所以这应该匹配失败。
        Matcher m = p.matcher(txt);
        System.out.println(m.find());
        txt = "Y less ddddddddddddddddddddddddd than 40 before X"; // 因为你想要“不”，所以这应该匹配
        m.reset(txt);
        System.out.println(m.find());
    }
}
```

输出:

```
false
true
```

#### 解释模式

`"(?<!Y.{0,40})X"`

> 如果在 `X` 之前的 0 到 N 个字符之间不存在 `Y`，则找到模式 `X`。

# 第 3 章：Java 正则表达式类

在 Java 中，当我们处理复杂项目时，会遇到许多输入，这些通常需要代码将文本与模式进行匹配。这种能力经常被用于邮件标头验证、文本搜索以及从通用文本创建自定义文本等。

## Java 字符串方法

在进入 `java.util.regex` 包之前，让我们先看看 `java.lang.String` 类提供的几个用于使用正则表达式的方法。这些方法可以用于一些简单的验证。但如果我们打算频繁使用正则表达式，这些方法将会产生性能开销。

### `matches()` 方法

`sampleString.matches("regex")` 返回 true 或 false，取决于该字符串是否可以被正则表达式完全匹配。需要记住的一个重要点是，`String.matches()` 只有在整个字符串都能被匹配时才返回 true。

#### 示例

```java
package com.sample.regexsample;

public class DemoForStringMatches {
    public static void main(String[] args) {
        // 准备一个正则表达式来表示模式
        String regex = ".@.";
        // 尝试用正则表达式匹配许多字符串
        DemoForStringMatches.matchIt("a@k", regex);
        DemoForStringMatches.matchIt("webmaster@jdojo.com", regex);
        DemoForStringMatches.matchIt("r@j", regex);
        DemoForStringMatches.matchIt("a%N", regex);
        DemoForStringMatches.matchIt(".@.", regex);
    }
    public static void matchIt(String str, String regex) {
        // 测试模式匹配
        if (str.matches(regex)) {
            // 使用 String 的 match 方法
            System.out.println(str + " matches the regex " + regex);
        } else {
            System.out.println(str + " does not match the regex " + regex);
        }
    }
}
```

输出:

```
a@k matches the regex .@.
webmaster@jdojo.com does not match the regex .@.
r@j matches the regex .@.
a%N does not match the regex .@.
.@ matches the regex .@.
```

### `replaceAll()`

`sampleString.replaceAll("regex", "replacement")` 将字符串内部所有的正则表达式匹配项替换为替换字符串。字符串中所有匹配 `regex` 的部分都会替换。

#### 示例

```java
package com.sample.regexsample;

public class DemoForAll {
    public static void main(String[] args) {
        // 准备一个正则表达式来表示模式
        String regex = ".@.";
        String replacementString = "***";
        // 尝试用正则表达式匹配许多字符串
        DemoForAll.replaceMatch("webd@koj", regex, replacementString);
    }
    public static void replaceMatch(String str, String regex, String replacementString) {
        // 测试模式匹配
        String newStr = str.replaceAll(regex, replacementString);
        System.out.println(regex + " replaced " + newStr);
    }
}
```

输出:

```
.@ replaced ***oj
```

### `replaceFirst()`

`replaceFirst()` 方法将第一个出现的匹配项替换为 `replacementString`。它返回替换后的新字符串。

#### 示例

```java
package com.sample.regexsample;

public class DemoForReplaceFirst {
    public static void main(String[] args) {
        // 准备一个正则表达式来表示模式
        String regex = ".@.";
        String replacementString = "***";
        // 尝试用正则表达式匹配许多字符串
        DemoForReplaceFirst.replaceMatch("A@BandH@G", regex, replacementString);
    }
    public static void replaceMatch(String str, String regex, String replacementString) {
        // 测试模式匹配
        String newStr = str.replaceFirst(regex, replacementString);
        System.out.println(regex + " replaced " + newStr);
    }
}
```

输出:

```
.@ replaced ***BandH@G
```

### `split()`

`sampleString.split("regex")` 根据正则表达式匹配分割字符串。该方法的返回值是一个字符串数组，其中的元素是两个匹配项之间的原始字符串。

#### 示例

```java
package com.sample.regexsample;

public class DemoForSplit {
    public static void main(String[] args) {
        String str = "one-two-three";
        String[] temp; // 分隔符
        String delimiter = "-"; // 字符串按提供的参数进行分割
        temp = str.split(delimiter); // 打印子字符串
        for (int i =0; i < temp.length; i++) {
            System.out.println(temp[i]);
        }
    }
}
```

输出:

```
one
two
three
```

## Java Util

`java.util.regex` 主要由以下三个类组成：（来源：Oracle Java 文档，www.docs.oracle.com）

*   `Pattern` 类：正则表达式的编译表示。`Pattern` 类没有公共构造函数。要创建模式，必须首先调用它的公共静态 `compile()` 方法，然后将返回一个 `Pattern` 对象。这些方法接受正则表达式作为参数。
*   `Matcher` 类：`Matcher` 对象是解释模式并对输入字符串执行匹配操作的引擎。与 `Pattern` 类一样，`Matcher` 没有定义公共构造函数。你通过在 `Pattern` 对象上调用 `matcher()` 方法来获取 `Matcher` 对象。
*   `PatternSyntaxException`：`PatternSyntaxException` 对象是一个异常，指示正则表达式中的语法错误。

#### 示例



```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class PatternSample {
    public static void main(String[] args) {
        Pattern pattern = Pattern.compile(".ab.");
        Matcher matcher = pattern.matcher("WabY");
        Matcher m1 = pattern.matcher("WxxY");
        System.out.println("Input String matches regex - " + matcher.matches());
        System.out.println("Input String matches regex - " + m1.matches());
    }
}
```

上述代码的输出如下：

```
Input String matches regex - true
Input String matches regex - false
```

示例代码解释：

在上面的示例中，`Pattern` 类的 `compile()` 方法被用于编译需要验证的正则表达式。然后，使用 `pattern.matcher()` 方法传递要验证的字符串，以便对已编译的正则进行比对。

上述示例中使用的正则模式为 `.ab.`，它表示 `ab` 之前有一个字符，之后有一个字符，并且 `ab` 在它们之间存在。任何遵循此特定模式的字符串在匹配时将返回 `true`。因此，在上面的示例中，第一个模式 `WabY` 匹配并返回 `true`，而 `WxxY` 则不匹配并返回 `false`。

## Pattern 类方法

### Pattern.compile()

`Pattern.compile()` 方法用于编译正则表达式，如果我们需要频繁搜索某个表达式的出现，或者在执行搜索时需要添加任何额外参数（例如不忽略大小写的搜索）。

该方法在该场景下的用法：

```java
String content = "This is a my regex";
String patternString = ".*reGeX";
Pattern pattern = Pattern.compile(patternString, Pattern.CASE_INSENSITIVE);
```

在这个代码示例中，我们使用了标志 `Pattern.CASE_INSENSITIVE` 进行不忽略大小写的搜索，还有其他几个标志可以用于不同的目的。下表给出了这些标志列表及其嵌入字符。

| 标志 | 解释 |
| :--- | :--- |
| `Pattern.CANON_EQ` | 用于启用规范化等效性。当我们需要仅在两个表达式的规范化分解匹配时才匹配它们，使用此标志。 |
| `Pattern.CASE_INSENSITIVE` | 用于在执行搜索或匹配时不考虑表达式的大小。 |
| `Pattern.COMMENTS` | 允许在模式中使用空白和注释。通过使用此标志，可以忽略表达式中的空格和以 `#` 开头的注释。 |
| `Pattern.DOTALL` | 用于启用点模式（dotall mode）。在此模式下，`.` 代表任何字符，包括换行符。 |
| `Pattern.LITERAL` | 用于启用给定表达式的字面解析。使用此标志时，用于验证的整个表达式被视为字面字符，而不是整个字符串。 |
| `Pattern.MULTILINE` | 用于启用多行模式。默认情况下，元字符 `^` 和 `$` 匹配表达式的开头和结尾。但使用此标志时，这些字符匹配换行符之前和之后。 |
| `Pattern.UNICODE_CASE` | 此标志与 `CASE_INSENSITIVE` 标志结合使用，当我们想要比较 Unicode 大写时（通常只比较 ASCII 字符）。 |
| `Pattern.UNIX_LINES` | 此标志启用 Unix 行模式。在此模式下，`\n` 被视为换行符。 |

这些标志可以作为字符本身嵌入正则表达式中。下表给出了这些标志的嵌入等效值。

| 标志 | 嵌入等效值 |
| :--- | :--- |
| `Pattern.CANON_EQ` | 无 |
| `Pattern.CASE_INSENSITIVE` | `(?i)` |
| `Pattern.COMMENTS` | `(?x)` |
| `Pattern.MULTILINE` | `(?m)` |
| `Pattern.DOTALL` | `(?s)` |
| `Pattern.LITERAL` | 无 |
| `Pattern.UNICODE_CASE` | `(?u)` |
| `Pattern.UNIX_LINES` | `(?d)` |

### Pattern.matches()

该方法是使用正则表达式在文本中搜索 `String` 最简单、方便的方法。例如，考虑下面的代码片段：

```java
package com.sample.regexsample;

import java.util.regex.Pattern;

public class PatternSample {
    public static void main(String[] args) {
        String content = "This is my regex sample";
        String patternString = ".*regex.*";
        boolean isMatch = Pattern.matches(patternString, content);
        System.out.println("The text contains 'tutorial'? " + isMatch);
    }
}
```

输出：

`The text contains 'regex': true`

如示例所示，我们使用了 `Pattern` 类的 `matches()` 方法在给定文本中搜索模式。模式 `.*regex.*` 允许在字符串 `regex` 的开头和结尾有零或多个字符。

**缺点：** 使用此方法我们可以在文本中搜索模式的单次出现。但如果我们需要检查多次出现的匹配，应该结合 `Pattern.compile()` 方法（在上一节讨论过）和 `Pattern.matcher()` 方法使用。

### Pattern.matcher() 方法

此方法用于返回 `Matcher` 类的实例，用于执行多次验证或在使用分组时。

考虑下面的示例：

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class PatternSample {
    public static void main(String[] args) {
        String content = "This is my regex sample";
        String patternString = ".*rEgeX.*";
        Pattern pattern = Pattern.compile(patternString, Pattern.CASE_INSENSITIVE);
        Matcher matcher = pattern.matcher(content);
        boolean isMatched = matcher.matches();
        System.out.println("Is it a? " + isMatched);
    }
}
```

输出：

`Is it a? true`

#### 多分组

在下面的代码中，`compile` 和 `matcher` 方法用于从分组中查找字符串。

```java
package com.sample.regexsample;

import java.util.ArrayList;
import java.util.List;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class PatternSample {
    public static void main(String[] args) {
        String input = "I have a cat, but I like dog.";
        String patternString = "(mouse|dog)|bear|human";
        Pattern p = Pattern.compile(patternString);
        Matcher m = p.matcher(input);
        List<String> animals = new ArrayList<>();
        while (m.find()) {
            System.out.println("Found a " + m.group());
            animals.add(m.group());
        }
    }
}
```

输出：

`Found a cat`

`Found a dog`

#### split

此方法根据分隔符（使用正则表达式指定）将给定文本分割为多个字符串。示例显示了该方法如何工作。

```java
package com.sample.regexsample;

import java.util.ArrayList;
import java.util.List;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class PatternSample {
    public static void main(String[] args) {
        String text = "ItIsRegexSample.ItProvidedByMe";
        String patternString = "is";
        Pattern pattern = Pattern.compile(patternString, Pattern.CASE_INSENSITIVE);
        String[] myStrings = pattern.split(text);
        for (String temp : myStrings) {
            System.out.println(temp);
        }
        System.out.println("Number of split strings: "+myStrings.length);
    }
}
```

输出：

`It`

`RegexSample.It`

`ProvidedByMe`

`Number of split strings: 3`

## Matcher 类方法

在上一节讨论 `Pattern` 类的 `matcher()` 方法时，我们创建了 `Matcher` 类的实例。它用于多次搜索和分组搜索。下面提供了代码示例供参考。

### 创建 Matcher 实例

```java
String content = "Some text";
String patternString = ".*somestring.*";
Pattern pattern = Pattern.compile(patternString);
Matcher matcher = pattern.matcher(content);
```

### Matches() 方法

此方法用于在创建 Matcher 实例时，对传递给 `Pattern.matcher()` 方法的整个字符串进行正则表达式匹配。

```java
Pattern pattern = Pattern.compile(patternString, Pattern.CASE_INSENSITIVE);
Matcher matcher = pattern.matcher(content);
boolean isMatched = matcher.matches();
```

### lookingAt()

此方法与 `matches()` 方法类似，不同之处在于它只从文本的开头匹配正则表达式，而 `matches()` 则在整个文本中搜索。

代码片段：

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class PatternSample {
    public static void main(String[] args) {
        String REGEX = "Saa";
        String INPUT = "SaaaaaaaS";
        Pattern pattern = Pattern.compile(REGEX);
        Matcher matcher = pattern.matcher(INPUT);
        System.out.println("Current REGEX is: "+REGEX);
        System.out.println("Current INPUT is: "+INPUT);
        System.out.println("lookingAt(): "+matcher.lookingAt());
        System.out.println("matches(): "+matcher.matches());
    }
}
```

输出：

```
Current REGEX is: Saa
Current INPUT is: SaaaaaaaS
lookingAt(): true
matches(): false
```

在上面的示例中，`lookingAt()` 方法返回 `true`，而 `matches()` 方法返回 `false`，因为后者匹配的是整个字符串，而另一个方法只比较开头。

### find()

此方法用于在文本中搜索正则表达式的出现情况。当我们在海量数据中搜索字符串的多次出现时，经常使用此方法。

代码片段：

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class PatternSample {
    public static void main(String[] args) {
        String REGEX = "too";
        String INPUT = "too";
        Pattern p = Pattern.compile(REGEX);
        Matcher m = p.matcher(INPUT); // 获取一个匹配器对象
        while(m.find()) {
            System.out.println("start(): "+m.start());
            System.out.println("end(): "+m.end());
        }
    }
}
```

输出：

```
start(): 0
end(): 3
```

### find(int start)

此方法尝试从指定的索引开始，在输入序列中找到与模式匹配的子序列。

#### start() 和 end()

这两个方法通常与 `find()` 方法结合使用。`start` 方法用于获取使用 `find()` 方法搜索的字符串或匹配项的起始索引，`end` 方法用于获取结束索引。此方法返回 `int` 值。

代码片段：

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class PatternSample {
    public static void main(String[] args) {
        String content = "I have a big and beautiful house and a good car";
        String string = "and";
        Pattern pattern = Pattern.compile(string);
        Matcher matcher = pattern.matcher(content);
        while(matcher.find()) {
            System.out.println("Found at: "+ matcher.start() + " - " + matcher.end());
        }
    }
}
```

输出：

```
Found at: 13 - 16
Found at: 33 - 36
```

#### start(int group) 和 end(int group)

这些是 `start` 和 `end` 的重载方法。当使用分组从特定组查找表达式的起始或结束索引时，可以使用这些方法。

代码片段：



```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class PatternSample {
    public static void main(String[] args) {
        String REGEX = "(cat)(s)";
        String INPUT = "cat cat cat";
        Pattern p = Pattern.compile(REGEX);
        Matcher m = p.matcher(INPUT); // 获取一个匹配器对象
        int count = 0;
        while(m.find()) {
            count++;
            System.out.println("start(1): "+m.start(1));
            System.out.println("end(1): "+m.end(1));
            System.out.println("start(2): "+m.start(2));
            System.out.println("end(2): "+m.end(2));
        }
    }
}
```

输出：

```
start(1): 8
end(1): 11
start(2): 11
end(2): 19
```

### `appendReplacement(StringBuffer sb, String replacement)`

它从插入位置开始从输入序列中读取字符，并将其添加到指定的缓冲区。之后，它将指定的字符串添加到字符串缓冲区以创建一个新文本。

代码片段：

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class PatternSample {
    public static void main(String[] args) {
        Pattern p = Pattern.compile("dog");
        Matcher m = p.matcher("one dog dogs in the house");
        StringBuffer sb = new StringBuffer();
        while (m.find()) {
            m.appendReplacement(sb, "rabbit");
        }
        m.appendTail(sb);
        System.out.println(sb.toString());
    }
}
```

输出：

```
one rabbit rabbits in the house
```

### `appendTail(StringBuffer)`

此方法配合 `appendReplacement()` 方法使用，用于替换后形成新的字符串。

### `replaceAll(String replacement)`

此方法用提供的替换字符串替换输入字符串中匹配模式的所有子集。

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class PatternSample {
    public static void main(String[] args) {
        String input = "aaahorsebbccse";
        String patternString = "horse";
        String output="";
        Pattern p = Pattern.compile(patternString);
        Matcher m = p.matcher(input);
        output = m.replaceAll("dog");
        System.out.println("Input:"+input);
        System.out.println("Output:"+output);
    }
}
```

输出：

```
Input:aaahorsebbccse
Output:aaadogbbog
```

### `replaceFirst(String replacement)`

此方法用替换字符串替换输入字符串中第一个匹配模式的子集。

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class PatternSample {
    public static void main(String[] args) {
        String input = "aaahorsebbccse";
        String patternString = "horse";
        String output="";
        Pattern p = Pattern.compile(patternString);
        Matcher m = p.matcher(input);
        output = m.replaceFirst("dog");
        System.out.println("Input:"+input);
        System.out.println("Output:"+output);
    }
}
```

输出：

```
Input:aaahorsebbccse
Output:aaadogbbccse
```

### `quoteReplacement(String s)`

此方法为指定的输入字符串返回字面替换字符串。该字面替换字符串可以作为字面替换用于 `Matcher` 类的 `appendReplacement` 方法。

### `PatternSyntaxException` 类

`PatternSyntaxException` 是一种表示正则表达式语法错误的运行时异常。`PatternSyntaxException` 类提供了以下方法来解决不准确之处：

1. `public String getDescription()` 提供错误描述
2. `public int getIndex()` 获取错误索引
3. `public String getPattern()` 恢复错误的正则表达式模式
4. `public String getMessage()` 返回一个包含语法错误描述及其索引、错误的正则模式以及模式内错误索引的视觉指示的多行字符串

示例代码：

```java
package com.sample.regexsample;

import java.io.Console;
import java.util.regex.Matcher;
import java.util.regex.Pattern;
import java.util.regex.PatternSyntaxException;

public class DemoForPatternSyntaxexception {
    public static void main(String[] args){
        Pattern pattern = null;
        Matcher matcher = null;
        String regex = "?i)foo";
        while (true) {
            try{
                pattern = Pattern.compile(regex);
                matcher = pattern.matcher("FOO");
            } 
            catch(PatternSyntaxException pse){
                System.out.println("There is a problem" +
                " with the regular expression!%n");
                System.out.println("The pattern in question is: %s%n"+pse.getPattern());
                System.out.println("The description is: %s%n"+pse.getDescription());
                System.out.println("The message is: %s%n"+pse.getMessage());
                System.out.println("The index is: %s%n"+pse.getIndex());
                System.exit(0);
            }
            boolean  found = false;
            while (matcher.find()) {
                System.out.println("I found the text" +
                " \"%s\" starting at " +
                "index %d and ending at index %d.%n"+
                matcher.group()+
                matcher.start()+
                matcher.end());
                found = true;
            }
            if(!found){
                System.out.println("No match found.%n");
            }
        }
    }
}
```

输出:

```
There is a problem with the regular expression!%n
The pattern in question is: %s%n?i)foo
The description is: %s%nDangling meta character '?'
The message is: %s%nDangling meta character '?' near index 0
?i)foo
^
The index is: %s%n0
```

从此输出中，我们可以发现语法错误是索引 0 处有一个悬挂的元字符（问号）。缺失的左括号是罪魁祸首。

# 第 4 章

## 用户名正则表达式

此语法解释了如何使用正则表达式来验证用户名。这是在各种网站和应用程序中常用的常用模式。

### 语法

```
^[a-z0-9_-]{3,15}$
```

### 解释：

- `^`: 行首
- `[a-z0-9_-]`: 列表中的字符，`a-z`、`0-9`、下划线、连字符
- `{3,15}`: 长度至少 3 个字符，最大长度为 15
- `$`: 行尾

整个组合意味着 3 到 15 个字符，仅包含任何小写字母、数字或特殊符号 `_-`。如果我们需要添加大写字母 `A-Z`。如果我们需要增加最大字符数，将 15 修改为相应值。

### 名字示例代码：

```java
package com.sample.regex;
import java.util.regex.Matcher;
import java.util.regex.Pattern;
public class UserNameValidator {
    static void main(String[] args) {
        String input = "^a-z0-9_-]{3,15}$";
        String userName ="Karen_3";
        String userName1="MyName";
        Pattern p = Pattern.compile(input);
        Matcher m = p.matcher(userName);
        Matcher m2 = p.matcher(userName1);
        System.out.println ("The user name 1:"+ m.matches());
        System.out.println ("The user name 2:"+ m2.matches());
    }
}
```

输出:

```
The user name 1 matches:true
The user name 2 matches:false
```

## 测验

编写类和测试用例来验证以下用户名。使用字符串数组或 `ArrayList` 传递整个值集：

1. `myname34`
2. `myname_2015`
3. `myname-2015`
4. `my_name-2020`
5. `my`
6. `my@name`
7. `myname_1234_myname`

## 解决方案

### 类：

```java
package com.sample.RegexExamples;
import java.util.regex.Matcher;
import java.util.regex.Pattern;
public class UserNameValidator {
    private Pattern pattern;
    private Matcher matcher;
    private static final String USERNAME_PATTERN = "^(?i)[a-z0-9_-]{3,15}$";
    // 与解释中给模式的简单变体是增加了 (?i)，它会在不区分大小写的情况下检查用户名。
    public UserNameValidator(){
        pattern = Pattern.compile(USERNAME_PATTERN);
    }
 /**
    * 使用正则表达式验证用户名
    * @param username 用于验证的用户名
    * @return true 有效用户名，false 无效用户名
     */
    public boolean validate(final String username){
        matcher = pattern.matcher(username);
        return matcher.matches();
    }
}
```

### 单元测试用例：

```java
package com.sample.RegexTest;
import static org.junit.Assert.*;
import org.junit.Assert;
import org.junit.Before;
import org.junit.Test;
import com.sample.RegexExamples.UserNameValidator;
public class UserNameValidatorTest {
    private UserNameValidator usernameValidator;
    @Before
    public void initData(){
        usernameValidator = new UserNameValidator();
    }
    @Test
    public void ValidUsernameTest() {
        String Username[] = new String[] {
        "myname34", "myname_2015","myname-2015" ,"my3-4_Name","LastName_25","LAstNaMe-78"
        };
        for(String temp : Username){
            boolean valid = usernameValidator.validate(temp);
            System.out.println("username is valid : " + temp + " " + valid);
            assertEquals(true, valid);
        }
    }
    @Test
    public void InUsernameTest() {
        String Username1[] = new String[] {
        "mymymy@LastName","my1224455aaaaaaaaaaaavwerwe"
        };
        for(String temp : Username1){
            boolean valid = usernameValidator.validate(temp);
            System.out.println("username is valid : " + temp + " " + valid);
            assertEquals(false, valid);
        }
    }
}
```

输出:

```
myname34 , true
myname_2015 , true
myname-2015 , true
my3-4_Name , true
LastName_25 , true
LAstNaMe-78 , true
my , false
my@LastName , false
my12345678_- , false
lastName@12345 , false
aaaaaaaaaaaavwerwe , false
```

# 第 5 章

## 密码正则表达式

### 语法



# 密码正则表达式

## 正则表达式
```
((?=.*\d)(?=.*[a-z])(?=.*[A-Z])(?=.*[@#$%]).{6,20})
```

## 解释
- `(`：开始
- `(?=.*\d)`：包含一个 0-9 数字
- `(?=.*[a-z])`：包含一个小写字母
- `(?=.*[A-Z])`：包含一个大写字母
- `(?=.*[@#$%])`：包含特殊符号 `@#$%`
- `.`：任意字符
- `{6,20}`：长度至少 6 个字符，最大 20 个
- `)`：结束

`?=` 表示应用断言条件，本身没有意义，总是与其他组合工作。

整个正则表达式组合意味着 6 到 20 个字符的字符串，至少包含一个数字、一个大写字母、一个小写字母和一个特殊符号（`@#$%`）。

## 示例代码

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class PasswordValidator {

    public static void main(String[] args) {
        String input = "((?=.*\\d)(?=.*[a-z])(?=.*[A-Z])(?=.*[@#$%]).{6,20})";
        String userName = "myname1A@";
        String userName1 = "mY1A@";

        Pattern p = Pattern.compile(input);
        Matcher m = p.matcher(userName);
        Matcher m2 = p.matcher(userName1);

        System.out.println("The password 1 matches:" + m.matches());
        System.out.println("The password 2 matches:" + m2.matches());
    }
}
```

## 核心验证类

```java
private Matcher matcher;
private Pattern pattern;
private static final String PASSWORD_PATTERN = "((?=.*\\d)(?=.*[a-z])(?=.*[A-Z])(?=.*[@#$%]).{6,20})";

public PasswordValidator() {
    pattern = Pattern.compile(PASSWORD_PATTERN);
}

/**
 * 使用正则表达式验证密码
 * @param password 用于验证的密码
 * @return true 有效密码，false 无效密码
 */
public boolean validate(final String password) {
    matcher = pattern.matcher(password);
    return matcher.matches();
}
```

## 单元测试

```java
package com.sample.RegexTest;

import static org.junit.Assert.*;
import org.junit.Assert;
import org.junit.Before;
import org.junit.Test;
import com.sample.RegexExamples.PasswordValidator;

public class PasswordValidatorTest {

    private PasswordValidator passwordValidator;

    @Before
    public void initData() {
        passwordValidator = new PasswordValidator();
    }

    @Test
    public void ValidPasswordTest() {
        String[] password = new String[]{"mynameA@34", "myName12@", "myNaME@12$", "lastName2$"};
        for (String temp : password) {
            boolean valid = passwordValidator.validate(temp);
            System.out.println("Password is valid : " + temp + " , " + valid);
            Assert.assertEquals(true, valid);
        }
    }

    @Test
    public void InValidPasswordTest() {
        String[] password = new String[]{"mY1A@", "myname12@ ", "myName12*", "LASTNAME12$", "LASTNAme$"};
        for (String temp : password) {
            boolean valid = passwordValidator.validate(temp);
            System.out.println("Password is valid : " + temp + " , " + valid);
            Assert.assertEquals(false, valid);
        }
    }
}
```

## 输出
```
Password is valid : mY1A@ , false
Password is valid : myname12@ , false
Password is valid : myName12* , false
Password is valid : LASTNAME12$ , false
Password is valid : LASTNAme$ , false
Password is valid : mynameA@34 , true
Password is valid : myName12@ , true
Password is valid : myNaME@12$ , true
Password is valid : lastName2$ , true
```

# 第 6 章

## 邮箱正则表达式

### 正则表达式
```
^[_A-Za-z0-9\-+]+(\.[A-Za-z0-9-]+)*@[A-Za-z0-9-]+(\.[A-Za-z0-9]+)*(\.[A-Za-z]{2,})$
```

### 解释
- `^`：行的开头
- `[_A-Za-z0-9\-+]+`：必须以 `[_A-Za-z0-9\-+]` 开头，包含一个或多个（`+`）
- `(\.[A-Za-z0-9-]+)*`：后跟一个 `.` 和字符串 `[A-Za-z0-9-]`，包含一个或多个（`+`），组 #1 是可选的（`*`）
- `@`：必须包含一个 `@` 符号
- `[A-Za-z0-9-]+`：后跟 `[A-Za-z0-9-]` 中的字符串，包含一个或多个（`+`）
- `(\.[A-Za-z0-9]+)*`：组 #2 - 第一级 TLD 检查（如 `.com`, `.net`），后跟一个 `.` 和字符串 `[A-Za-z0-9]`，包含一个或多个（`+`），组 #2 是可选的（`*`）
- `(\.[A-Za-z]{2,})`：组 #3 - 第二级 TLD 检查（如 `.com.au`, `.com.my`），后跟一个 `.` 和 `[A-Za-z]` 中的字符串，最小长度为 2（`{2}`）
- `$`：行的结尾

该正则表达式组合意味着，邮箱地址必须以 `[_A-Za-z0-9\-+]` 开头，可选后跟 `.[A-Za-z0-9-]`，并以 `@` 符号结尾。邮箱的域名必须以 `A-Za-z0-9-` 开头，后跟第一级 TLD（`.[A-Za-z0-9]`）以及可选后跟第二级 TLD（`.[A-Za-z]{2,}`），其中第二级 TLD 必须以点 `.` 开头且长度大于等于 2 个字符。

### 示例

```java
package com.sample.regex;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class EmailValidator {

    public static void main(String[] args) {
        String input = "^[_A-Za-z0-9\\+]+(\\.[A-Za-z0-9-]+)*@[A-Za-z0-9-]+(\\.[A-Za-z0-9]+)*(\\.[A-Za-z]{2,})$";
        String emailAddress = "myName@gmail.com";
        String emailAddress2 = "myName@gmail.c";
        String emailAddress3 = "mylastName@yahoo.co.in";

        Pattern p = Pattern.compile(input);
        Matcher m = p.matcher(emailAddress);
        Matcher m2 = p.matcher(emailAddress2);
        Matcher m3 = p.matcher(emailAddress3);

        System.out.println("Email 1 matches:" + m.matches());
        System.out.println("Email 2 matches:" + m2.matches());
        System.out.println("Email 3 matches:" + m3.matches());
    }
}
```

输出：
```
Email 1 matches:true
Email 2 matches:false
Email 3 matches:true
```

## 练习
编写类并测试以下邮箱地址：
1. `name@abc`
2. `forget@te`
3. `lastnam@co.in`
4. `myName12*`
5. `user$$my`
6. `LASTNAME2@test`

## 答案

### 代码

```java
package com.sample.Examples;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class EmailValidator {

    private Pattern pattern;
    private Matcher matcher;
    private static final String EMAIL_PATTERN = "^[_A-Za-z0-9\\+]+(\\.[A-Za-z0-9-]+)*@[A-Za-z0-9-]+(\\.[A-Za-z0-9]+)*(\\.[A-Za-z]{2,})$";

    public EmailValidator() {
        pattern = Pattern.compile(EMAIL_PATTERN);
    }

    /**
     * 使用正则表达式验证邮箱
     * @param email 用于验证的邮箱
     * @return true 有效邮箱，false 无效邮箱
     */
    public boolean validate(String email) {
        matcher = pattern.matcher(email);
        return matcher.matches();
    }
}
```

### 单元测试

```java
package com.sample.RegexTest;

import org.junit.Assert;
import org.junit.Before;
import org.junit.Test;
import com.sample.Examples.EmailValidator;

public class EmailValidatorTest {

    private EmailValidator emailValidator;

    @Before
    public void initData() {
        emailValidator = new EmailValidator();
    }

    String[] ValidEmailProvider = {
        "name@abc.com",
        "forget@100.net",
        "lastnam@co.in",
        "myName12@test.com",
        "user@my.com.au",
        "123@gmail.com"
    };

    String[] InvalidEmailProvider = {
        "name@.com.my",
        "forget@100",
        "lastnam123@gmail.a",
        "myName12*",
        "user$$my",
        ".name@test.com",
        "name@%*.com",
        "name..test.com",
        "name.@test.com",
        "LASTNAME2@test.com.1a"
    };

    @Test
    public void ValidEmailTest() {
        for (String temp : ValidEmailProvider) {
            boolean valid = emailValidator.validate(temp);
            System.out.println("Email is valid : " + temp + " , " + valid);
            Assert.assertEquals(true, valid);
        }
    }

    @Test
    public void InvalidEmailTest() {
        for (String temp : InvalidEmailProvider) {
            boolean valid = emailValidator.validate(temp);
            System.out.println("Email is valid : " + temp + " , " + valid);
            Assert.assertEquals(false, valid);
        }
    }
}
```



```
Email is 有效 : mkyong , false
Email is 有效 : mkyong@.com.my , false
Email is 有效 : mkyong123@gmail.a , false
Email is 有效 : mkyong123@.com , false
Email is 有效 : mkyong123@com.com , false
Email is 有效 : .mkyong@mkyong.com , false
Email is 有效 : mkyong()*@gmail.com , false
Email is 有效 : mkyong@%*.com , false
Email is 有效 : mkyong..2002@gmail.com , false
Email is 有效 : mkyong.@gmail.com , false
Email is 有效 : mkyong@mkyong@gmail.com , false
Email is 有效 : mkyong@gmail.com.1a , false
Email is 有效 : mkyong@yahoo.com , true
Email is 有效 : mkyong-100@yahoo.com , true
Email is 有效 : mkyong.100@yahoo.com , true
Email is 有效 : mkyong111@mkyong.com , true
Email is 有效 : mkyong-100@mkyong.net , true
Email is 有效 : mkyong.100@mkyong.com.au , true
Email is 有效 : mkyong@1.com , true
Email is 有效 : mkyong@gmail.com.com , true
Email is 有效 : mkyong+100@gmail.com , true
Email is 有效 : mkyong-100@yahoo-test.com , true
```

# 第 7 章：正则颜色编码

## 十进制颜色代码正则表达式模式

`^#([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})$`

### 描述

- `^` : 行首
- `#` : 必须包含 "#" 符号
- `(` : 组 #1 开始
- `[A-Fa-f0-9]{6}` : 列表中的任意字符串，长度为 6
- `|` : ..或
- `[A-Fa-f0-9]{3}` : 列表中的任意字符串，长度为 3
- `)` : 组 #1 结束
- `$` : 行尾

颜色编码字符串意味着：以 `#` 符号开头，后面紧跟一个 `a` 到 `f`、`A` 到 `Z` 的字母或 `0` 到 `9` 的数字，长度恰好为 6 或 3。

### 示例代码

```java
package com.sample.regex;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class HexCode {

    public static void main(String[] args) {

        String input = "^([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})$";

        String hexCode1 = "#1f1F";

        String hexCode2 = "#2345";

        Pattern p = Pattern.compile(input);

        Matcher m = p.matcher(hexCode1);

        Matcher m2 = p.matcher(hexCode2);

        System.out.println("The hexCode 1 matches:" + m.matches());

        System.out.println("The hexCode 2 matches:" + m2.matches());

    }

}
```

输出：
```
hexCode 1 matches:true
hexCode 2 matches:false
```

# 第 8 章：图片文件的正则表达式

## 图片扩展名正则表达式模式

`([^\s]+\.(?i)(jpg|png|gif|bmp))`

### 描述

- `(` : 组 #1 开始
- `[^\s]+` : 包含一个或多个任意字符（空格除外）
- `\.` : 后面跟着一个点 "."
- `(?i)` : 忽略后续字符的大小写敏感
- `(` : 组 #2 开始
- `jpg` : 包含字符 "jpg"
- `|` : ..或
- `png` : 包含字符 "png"
- `|` : ..或
- `gif` : 包含字符 "gif"
- `|` : ..或
- `bmp` : 包含字符 "bmp"
- `)` : 组 #2 结束
- `$` : 字符串结束

该正则表达式意味着：必须有 1 个或多个字符串（非空格），后面跟着一个点并以 `jpg` 或 `png` 或 `gif` 或 `bmp` 结尾，且文件扩展名忽略大小写。这个正则表达式非常适用于许多扩展名检查示例，你可以修改最后的组合 `(jpg, png, gif, bmp)` 以满足你的需求。

### 示例代码

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForImageFile {

    public static void main(String[] args) {

        String input = "([^\\s]+\\.(?i)(jpg|png|gif|bmp))$";

        String file1 = "Karen_3.gif";

        String file2 = "My";

        Pattern p = Pattern.compile(input);

        Matcher m = p.matcher(file1);

        Matcher m2 = p.matcher(file2);

        System.out.println("The file 1 matches:" + m.matches());

        System.out.println("The file 2 matches:" + m2.matches());

    }

}
```

输出：
```
The file 1 matches:true
The file 2 matches:false
```

# 第 9 章：IP 地址的正则表达式

## IP 地址正则表达式模式

`^([01]?\d\d?|2[0-4]\d|25[0-5])(\.([01]?\d\d?|2[0-4]\d|25[0-5])){3}$`

### 描述

该正则表达式匹配 0 到 255 的格式。

- `^` : 行首
- `(` : 组 #1 开始
- `[01]?\d\d?|2[0-4]\d|25[0-5]` : 匹配 0-255 的数字
- `)` : 组 #1 结束
- `(\.([01]?\d\d?|2[0-4]\d|25[0-5])){3}` : 重复 3 次（点加数字）
- `$` : 行尾

### 示例代码

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForIp {

    public static void main(String[] args) {

        String IPADDRESS_PATTERN = "^([01]?\\d\\d?|2[0-4]\\d|25[0-5])(\\.([01]?\\d\\d?|2[0-4]\\d|25[0-5])){3}$";

        String ipAddress1 = "192.2.1";

        String ipAddress2 = "100.23.255";

        Pattern p = Pattern.compile(IPADDRESS_PATTERN);

        Matcher m = p.matcher(ipAddress1);

        Matcher m2 = p.matcher(ipAddress2);

        System.out.println("The ip 1 matches:" + m.matches());

        System.out.println("The ip 2 matches:" + m2.matches());

    }

}
```

输出：
```
The ip 1 matches:false
The ip 2 matches:true
```

# 第 10 章：时间格式的正则表达式

## 12 小时制时间正则表达式

`(1[012]|[1-9]):[0-5][0-9](\s)?(?i)(am|pm)`

### 描述

- `(` : 组 #1 开始
- `1[012]` : 10, 11, 12
- `|` : ..或
- `[1-9]` : 1,2,...9
- `)` : 组 #1 结束
- `:` : 后面跟着一个冒号 (:)
- `[0-5][0-9]` : 后面跟着 0..5 和 0..9，意味着 00 到 59
- `(\s)?` : 可选空格
- `(?i)` : 忽略大小写
- `(am|pm)` : 包含 am 或 pm

整个正则表达式的意思是：12 小时制格式从 1-12 开始，然后是一个冒号（`:`），紧接着是 00-59，可选空格，并以 am 或 pm 结束。

### 示例代码

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForTimeFormat {

    public static void main(String[] args) {

        String input = "(1[012]|[1-9]):[0-5][0-9](\\s)?(?i)(am|pm)";

        String time1 = "10:15 pm";

        String time2 = "12:45 a.m";

        String time3 = "01:45 am";

        String time4 = "2:45 am";

        Pattern p = Pattern.compile(input);

        Matcher m = p.matcher(time1);

        Matcher m2 = p.matcher(time2);

        Matcher m3 = p.matcher(time3);

        Matcher m4 = p.matcher(time4);

        System.out.println("The time 1 matches:" + m.matches());

        System.out.println("The time 2 matches:" + m2.matches());

        System.out.println("The time 3 matches:" + m3.matches());

        System.out.println("The time 4 matches:" + m4.matches());

    }

}
```

**输出：**
```
The time 1 matches:true
The time 2 matches:false
The time 3 matches:false
The time 4 matches:true
```

## 24 小时制时间正则表达式

`([01]?[0-9]|2[0-3]):[0-5][0-9]`

### 描述

- `(` : 组 #1 开始
- `[01]?[0-9]` : 以 0-9, 1-9, 00-09, 10-19 开始
- `|` : 或
- `2[0-3]` : 以 20-23 开始
- `)` : 组 #1 结束
- `:` : 跟着一个冒号（:）
- `[0-5][0-9]` : 跟着 0..5 和 0..9，意味着 0 到 59

24 小时制格式的正则表达式是从 0-23 开始，然后是一个冒号（:），后面跟着 00-59。

### 示例代码

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForFormat2 {

    public static void main(String[] args) {

        String input = "([01]?[0-9]|2[0-3]):[0-5][0-9]";

        String time1 = "10:15";

        String time2 = "12:45";

        String time3 = "25:45";

        String time4 = "23:45";

        Pattern p = Pattern.compile(input);

        Matcher m = p.matcher(time1);

        Matcher m2 = p.matcher(time2);

        Matcher m3 = p.matcher(time3);

        Matcher m4 = p.matcher(time4);

        System.out.println("The time 1 matches:" + m.matches());

        System.out.println("The time 2 matches:" + m2.matches());

        System.out.println("The time 3 matches:" + m3.matches());

        System.out.println("The time 4 matches:" + m4.matches());

    }

}
```

**输出：**
```
The time 1 matches:true
The time 2 matches:true
The time 3 matches:false
The time 4 matches:true
```

# 第 11 章：日期格式正则表达式

## 日期格式 (dd/mm/yyyy) 正则表达式模式

`(0?[1-9]|[12][0-9]|3[01])/(0?[1-9]|1[012])/((19|20)\d\d)`

### 描述

- `(` : 组 #1 开始
- `0?[1-9]` : 01-09 或 1-9
- `|` : 或
- `[12][0-9]` : 10-19 或 20-29
- `|` : 或
- `3[01]` : 30, 31
- `)` : 组 #1 结束
- `/` : 跟着一个 "/"
- `(` : 组 #2 开始
- `0?[1-9]` : 01-09 或 1-9
- `|` : 或
- `1[012]` : 10, 11, 12
- `)` : 组 #2 结束
- `/` : 跟着一个 "/"
- `(` : 组 #3 开始
- `(19|20)\d\d` : 19[0-9] 或 20[0-9]
- `)` : 组 #3 结束

上面的正则用于验证日期格式“dd/mm/yyyy”，通常你可以根据需要对此正则表达式进行调整。无论如何，验证闰年、某月份有 30 天还是 31 天会有点复杂，让我们看看如何做到。

### 示例代码

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class HexCodeValidator {

    public static void main(String[] args) {

        String input = "(0?[1-9]|[12][0-9]|3[01])/(0?[1-9]|1[012])/((19|20)\\d\\d)";

        String date1 = "31/08/2016";

        String date2 = "12345";

        Pattern p = Pattern.compile(input);

        Matcher m = p.matcher(date1);

        Matcher m2 = p.matcher(date2);

        System.out.println("The date 1 matches:" + m.matches());

        System.out.println("The date 2 matches:" + m2.matches());

    }

}
```

**输出：**
```
The date 1 matches:true
The date 2 matches:false
```

## 练习

使用命名分组（special construct）验证闰年的日期格式。

## 解决方案

### 代码示例

```java
package com.sample.regexsample;

import java.text.DateFormat;
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.ArrayList;
import java.util.Date;
import java.util.List;
import java.util.regex.Matcher;
```



```java
import java.util.regex.Pattern;

public class DemoForDateValidation {

    public static void main(String[] args) {

        String input = "^(?<month>[0-3]?[0-9])/(?<day>[0-3]?[0-9])/(?<year>(?:[0-9]{2})[0-9]{2})$";

        List<String> dates = new ArrayList<String>();

        dates.add("02/31/2011");

        dates.add("02/27/2011");

        Pattern p = Pattern.compile(input);

        for (String date : dates) {

            Matcher matcher = p.matcher(date);

            if (matcher.matches()) {

                String day = matcher.group(2);

                String month = matcher.group(1);

                String year = matcher.group(3);

                String formattedDate = month + "/" + day + "/" + year;

                System.out.println("Date to check: " + formattedDate);

                try {

                    DateFormat df = new SimpleDateFormat("MM/dd/yyyy");

                    df.setLenient(false);

                    Date d = df.parse(date);

                    System.out.println("Parsed: " + d);

                } catch (ParseException e) {

                    System.out.println("Parsed: Invalid");

                }

            }

        }

    }

}
```

**输出：**

```
Date to check: 02/31/2011

Parsed: Invalid

Date to check: 02/27/2011

Parsed: Sun Feb 27 00:00:00 2011
```

整体上的正则表达式意思是：HTML 标签以起始标签“<”开头，后跟着双引号 `"string"` 或单引号 `'string'`，但不允许单个双引号 (`"`) `"string"`、单个单引号 (`'`) `'string` 或没有单双引号包裹的结束标签 `>`。最后，以结束标签“>”结尾。

### 示例：

```java
package com.sample.regexsample;

import java.util.regex.Matcher;

import java.util.regex.Pattern;

public class DemoForHTMLTag {

    public static void main(String[] args) {

        String HTML_PATTERN = "<(\"[^\"]*\"|'[^']*'|[^'\">])*>";

        String htmlTag = "<br>";

        Pattern p = Pattern.compile(HTML_PATTERN);

        Matcher m = p.matcher(htmlTag);

        System.out.println ("The html tag matches:"+ m.matches());

    }

}
```

输出：
`The html tag matches:true`

# 第 13 章

# 用于查找 HTML 链接的正则表达式

## 提取 A 标签的正则表达式模式
`(?i)<a([^>]+)>(.+?)</a>`

## 从 A 标签中提取链接的正则表达式模式
`\s*(?i)href\s*=\s*(\"([^"]*\")|'[^']*'|([^'">\s]+));`

### 描述
```

(                                # 第 1 组开始

?i                              # 所有检查不区分大小写

)                                # 第 1 组结束

<a                              # 以 "<a" 开头

(                                # 第 2 组开始

[^>]+                           # 匹配除(">")以外的任意字符，至少一个

)                                # 第 2 组结束

>                               # 紧跟 ">"

(.+?)                           # 匹配任意内容

</a>                            # 以 "</a>" 结尾

\s*                             # 可以以空格开头

(?i)                            # 所有检查不区分大小写

href                            # 后跟 "href" 单词

\s*=\s*                         # 允许等号两边有空格

(                                # 第 1 组开始

"([^"]*")                       # 允许带双引号的字符串 - "string"

|

'[^']*'                         # ..或者带单引号的字符串 - 'string'

|

([^'">\s]+)                     # ..或者不包含单引号、双引号、">

)                                # 第 1 组结束

```

### 代码：
```java
package com.sample.regexsample;

import java.util.Vector;

import java.util.regex.Matcher;

import java.util.regex.Pattern;

public class DemoForLink {

    String HTML_A_TAG_PATTERN = "(?i)<a([^>]+)>(.+?)</a>";

    String HTML_A_HREF_TAG_PATTERN = "\\s*(?i)href\\s*=\\s*(\"[^\"]*\")|'[^']*|([^'">\\s]+))";

    Pattern patternTag = Pattern.compile(HTML_A_TAG_PATTERN);

    Pattern patternLink = Pattern.compile(HTML_A_HREF_TAG_PATTERN);

    Matcher matcherTag, matcherLink;

    /**

    * 使用正则表达式验证 html

    * @param html 用于验证的内容

    * @return 链接和文本的 Vector

     */

    public void grabHTMLLinks(final String html) {

        matcherTag = patternTag.matcher(html);

        while (matcherTag.find()) {

            String href = matcherTag.group(1);

            String linkText = matcherTag.group(2);

            matcherLink = patternLink.matcher(href);

            while (matcherLink.find()) {

                String link = matcherLink.group(1);

                System.out.println("Link is "+link);

                System.out.println("Linktext is "+linkText);

            }

        }

    }

    public static void main(String[] args) {

        String TEST_LINK = "http://www.google.com";

        DemoForLink htmlLinkExtractor = new DemoForLink();

        String html = "abc hahaha <a href='" + TEST_LINK + "'>google</a>";

        htmlLinkExtractor.grabHTMLLinks(html);

    }

}
```

输出：
`Link is 'http://www.google.com'`
`Linktext is google`

# 第 14 章

# 用于 URL 的正则表达式

## 表达式
`^(?i)(https?|ftp|file|www)://[-a-zA-Z0-9+&@#/%?=~_|!:,.;]*[-a-zA-Z0-9+&@#/%=~_|]`

### 描述
```

(                                # 第 1 组开始

?i                              # 所有检查不区分大小写

)                                # 第 1 组结束

(

https?                           # 包含 http 或 https

|                                #或者

ftp                             # 包含 ftp

|                                #或者

file                            # 包含 file

|                                #或者

www                             # 包含 www

)                                                               # 第 2 组结束

://                              # 包含 : 后面跟 //

[-a-zA-Z0-9+&@#/%?=~_|!:,.;]*# 匹配 A-Z、数字 0-9 之间的任意字符以及给出的符号列表（可选）

[-a-zA-Z0-9+&@#/%=~_|]         # 匹配 A-Z、数字 0-9 之间的任意字符以及给出的符号列表（此组也是可选的）

```

### 示例：
```java
package com.sample.regexsample;

import java.util.regex.Matcher;

import java.util.regex.Pattern;

public class DemoForURL {

    public static void main(String[] args) {

        String lRegex = "^(https?|ftp|file|www)://[-a-zA-Z0-9+&@#/%?=~_|!:,.;]*[-a-zA-Z0-9+&@#/%=~_|]";

        String htmlTag = "www://mysiteindex.com";

        Pattern p = Pattern.compile(lRegex);

        Matcher m = p.matcher(htmlTag);

        System.out.println ("The html tag matches:"+ m.matches());

    }

}
```

输出：
`The html tag matches:true`

# 第 15 章

# 用于电话号码的正则表达式

## 正则表达式
`^\(?([0-9]{3})\)?[-.\s*]?([0-9]{3})[-.\s*]?([0-9]{4})$`

### 解释：
```

^                               # 断言位于字符串开头。

\(                              # 匹配字面量 "("

?                               # 零到一次。

(                               # 捕获匹配的内容作为反向引用 1:

[0-9]{3}                        # 匹配三个数字

)                                # 捕获组结束

\)                              # 匹配字面量 ")"

[-.\s*]?                        # 匹配连字符、点、空格或星号（零次或一次）

([0-9]{3})                      # 匹配三个数字

[-.\s*]?                        # 匹配连字符、点、空格或星号（零次或一次）

([0-9]{4})                      # 匹配四个数字

$                               # 断言位于字符串结尾。

```

### 示例：
```java
package com.sample.regexsample;

import java.util.regex.Matcher;

import java.util.regex.Pattern;

public class DemoForURL {

    public static void main(String[] args) {

        String lRegex = "^\\(?([0-9]{3})\\)?[-.\\s*]?([0-9]{3})[-.\\s*]?([0-9]{4})$";

        String phoneNumber1 = "123-456-7890";

        String phoneNumber2 = "(123)456-7890";

        String phoneNumber3 = "123 456 7890";

        String phoneNumber4 = "1234567890";

        String phoneNumber5 = "+1234567890";

        Pattern p = Pattern.compile(lRegex);

        Matcher m1 = p.matcher(phoneNumber1);

        Matcher m2 = p.matcher(phoneNumber2);

        Matcher m3 = p.matcher(phoneNumber3);

        Matcher m4 = p.matcher(phoneNumber4);

        Matcher m5 = p.matcher(phoneNumber5);

        System.out.println ("The html tag matches:"+ m1.matches());

        System.out.println ("The html tag matches:"+ m2.matches());

        System.out.println ("The html tag matches:"+ m3.matches());

        System.out.println ("The html tag matches:"+ m4.matches());

        System.out.println ("The html tag matches:"+ m5.matches());

    }

}
```

输出：
`The html tag matches:true`
`The html tag matches:true`
`The html tag matches:true`
`The html tag matches:true`
`The html tag matches:false`

# 第 16 章

# 用于国际号码的正则表达式

## 正则表达式
`^\+(?:[0-9]\s*?){6,14}[0-9]$`

### 解释
```

^                               # 断言位于字符串开头。
```



# 国际电话号码验证

模式：
```
^\+(?:[0-9]\s*?){6,14}[0-9]$
```

解释：
- `\+` # 匹配字面量 "+" 字符。
- `(?:` # 非捕获分组：
  - `[0-9]` # 匹配一个数字
  - `\s*` # 匹配空格
  - `?` # 零到一次。
- `)` # 非捕获分组结束。
- `{6,14}` # 重复分组 6 到 14 次。
- `[0-9]` # 匹配一个数字
- `$` # 断言位于字符串结尾。

### 示例

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForIntPhone {

    public static void main(String[] args) {
        String regex = "^\\+(?:[0-9]\\s*?){6,14}[0-9]$";

        String phoneNumber1 = "+91 1234567890";
        String phoneNumber2 = "(123)456-7890";
        String phoneNumber3 = "+891234567890";

        Pattern p = Pattern.compile(regex);
        Matcher m = p.matcher(phoneNumber1);
        Matcher m1 = p.matcher(phoneNumber2);
        Matcher m2 = p.matcher(phoneNumber3);

        System.out.println("The html tag matches:" + m.matches());
        System.out.println("The html tag matches:" + m1.matches());
        System.out.println("The html tag matches:" + m2.matches());
    }
}
```

**输出：**
```
The html tag matches:true
The html tag matches:false
The html tag matches:true
```

# 第 17 章：其他常用模式

## 验证仅字母数字模式

模式：
`^[a-zA-Z0-9]*$`

解释：
- `^` # 模式开始
- `[` # 字符类开始
- `a-zA-Z0-9` # 包含 a 到 z 的字符（不区分大小写）以及从 0 到 9 的数字
- `]` # 字符类结束
- `*` # 零个或多个字母或数字
- `$` # 模式结束

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForAlphaNumericCheck {

    public static void main(String[] args) {
        String patternString = "^[a-zA-Z0-9]*$";

        String name1 = "Teststring123";
        String name2 = "lastname";
        String name3 = "12345";
        String name4 = "la12345@";

        Pattern pattern = Pattern.compile(patternString);
        Matcher matcher1 = pattern.matcher(name1);
        Matcher matcher2 = pattern.matcher(name2);
        Matcher matcher3 = pattern.matcher(name3);
        Matcher matcher4 = pattern.matcher(name4);

        System.out.println("YAy found out alphanumeric  " + matcher1.matches());
        System.out.println("YAy found out alphanumeric  " + matcher2.matches());
        System.out.println("YAy found out alphanumeric  " + matcher3.matches());
        System.out.println("YAy found out alphanumeric  " + matcher4.matches());
    }
}
```

**输出：**
```
YAy found out alphanumeric  true
YAy found out alphanumeric  true
YAy found out alphanumeric  true
YAy found out alphanumeric  false
```

## 浮点数

模式：
`^[-+]?[0-9]*\.?[0-9]+$`

解释：
- `^` # 模式开始
- `[-+]?` # 可选符号
- `[0-9]*` # 紧跟一系列数字（可选）
- `\.?` # 紧跟可选的 "." 符号
- `[0-9]+` # 紧跟一系列数字（至少一个）
- `$` # 模式结束

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForPointNumber {

    public static void main(String[] args) {
        String patternString = "^[-+]?[0-9]*\\.?[0-9]+$";

        String num1 = "123";
        String num2 = "lastname";
        String num3 = "12.345";
        String num4 = "la12345@";

        Pattern pattern = Pattern.compile(patternString);
        Matcher matcher1 = pattern.matcher(num1);
        Matcher matcher2 = pattern.matcher(num2);
        Matcher matcher3 = pattern.matcher(num3);
        Matcher matcher4 = pattern.matcher(num4);

        System.out.println("Found out floating number  " + matcher1.matches());
        System.out.println("Found out floating number  " + matcher2.matches());
        System.out.println("Found out floating number  " + matcher3.matches());
        System.out.println("Found out floating number  " + matcher4.matches());
    }
}
```

**输出：**
```
Found out floating number  true
Found out floating number  false
Found out floating number  true
Found out floating number  false
```

### 另一个模式

`[-+]?([0-9]*\.[0-9]+|[0-9]+)`
该正则等同于一个可选的符号，后面跟着零或多个数字后跟一个点以及一个或多个数字（带有可选整数部分的浮点数），或者后面跟着一个或多个数字（整数）。

### 进一步优化

我们可以将此正则表达式优化为：`[-+]?[0-9]*\.?[0-9]+([eE][-+]?[0-9]+)?`。
解释：`[-+]?[0-9]*\.?[0-9]+([eE][-+]?[0-9]+)?`。指数部分通过将其分组在一起使其变为可选，而不是将指数部分中的每个元素都设置为可选。

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForFloatingPointNumber {

    public static void main(String[] args) {
        String patternString = "[-+]?[0-9]*\\.?[0-9]+([eE][-+]?[0-9]+)?";

        String num1 = "123";
        String num2 = "lastname";
        String num3 = "12.345";
        String num4 = "la12345@";

        Pattern pattern = Pattern.compile(patternString);
        Matcher matcher1 = pattern.matcher(num1);
        Matcher matcher2 = pattern.matcher(num2);
        Matcher matcher3 = pattern.matcher(num3);
        Matcher matcher4 = pattern.matcher(num4);

        System.out.println("Found out floating number  " + matcher1.matches());
        System.out.println("Found out floating number  " + matcher2.matches());
        System.out.println("Found out floating number  " + matcher3.matches());
        System.out.println("Found out floating number  " + matcher4.matches());
    }
}
```

**输出：**
```
Found out floating number  true
Found out floating number  false
Found out floating number  true
Found out floating number  false
```

### 示例代码

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForFloatingPointNumber {

    public static void main(String[] args) {
        String patternString = "[-+]?([0-9]*\\.[0-9]+|[0-9]+)";

        String num1 = "123";
        String num2 = "lastname";
        String num3 = "+12.345";
        String num4 = "la12345@";
        String num5 = "-2.3";
        String num6 = "-12";

        Pattern pattern = Pattern.compile(patternString);
        Matcher matcher1 = pattern.matcher(num1);
        Matcher matcher2 = pattern.matcher(num2);
        Matcher matcher3 = pattern.matcher(num3);
        Matcher matcher4 = pattern.matcher(num4);
        Matcher matcher5 = pattern.matcher(num5);
        Matcher matcher6 = pattern.matcher(num6);

        System.out.println("Found out floating number  " + matcher1.matches());
        System.out.println("Found out floating number  " + matcher2.matches());
        System.out.println("Found out floating number  " + matcher3.matches());
        System.out.println("Found out floating number  " + matcher4.matches());
        System.out.println("Found out floating number  " + matcher5.matches());
        System.out.println("Found out floating number  " + matcher6.matches());
    }
}
```

**输出：**
```
Found out floating number  true
Found out floating number  false
Found out floating number  true
Found out floating number  false
Found out floating number  true
Found out floating number  true
```

### 进一步优化（支持科学计数法）

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForFloatingPointNumber {

    public static void main(String[] args) {
        String patternString = "[-+]?[0-9]*\\.?[0-9]+([eE][-+]?[0-9]+)?";

        String num1 = "123";
        String num2 = "lastname";
        String num3 = "+12.345";
        String num4 = "la12345@";
        String num5 = "-2.3e6";
        String num6 = "-12e45";

        Pattern pattern = Pattern.compile(patternString);
        Matcher matcher1 = pattern.matcher(num1);
        Matcher matcher2 = pattern.matcher(num2);
        Matcher matcher3 = pattern.matcher(num3);
        Matcher matcher4 = pattern.matcher(num4);
        Matcher matcher5 = pattern.matcher(num5);
        Matcher matcher6 = pattern.matcher(num6);

        System.out.println("Found out floating number  " + matcher1.matches());
        System.out.println("Found out floating number  " + matcher2.matches());
        System.out.println("Found out floating number  " + matcher3.matches());
        System.out.println("Found out floating number  " + matcher4.matches());
        System.out.println("Found out floating number  " + matcher5.matches());
        System.out.println("Found out floating number  " + matcher6.matches());
    }
}
```



## 删除重复单词

模式：
`\b(\w+)\b\s+\b\1\b`

解释：
- `\b`：单词边界
- `(\w+)`：需要查找重复的单词
- `\b`：单词结束
- `\s+`：可选空白符
- `\b`：单词边界
- `\1`：引用第一个分组捕获的匹配，即第一个单词
- `\b`：单词结束

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForDuplication {

    public static void main(String args[]) throws Exception {
        String input = "This This is my pen pen and pencil pencil text another another";
        String output = "";

        Pattern p = Pattern.compile("\\b(\\w+)\\b\\s+\\b\\1\\b", Pattern.MULTILINE + Pattern.CASE_INSENSITIVE);
        Matcher m = p.matcher(input);

        if (!m.find()) {
            output = "No duplicates found, no changes made to data";
        } else {
            while (m.find()) {
                if (output == "") {
                    output = input.replaceFirst(m.group(), m.group(1));
                } else {
                    output = output.replaceAll(m.group(), m.group(1));
                }
            }

            input = output;
            m = p.matcher(input);

            while (m.find()) {
                output = "";
                if (output == "") {
                    output = input.replaceAll(m.group(), m.group(1));
                } else {
                    output = output.replaceAll(m.group(), m.group(1));
                }
            }
        }

        System.out.println("After removing duplicate the final string is " + output);
    }
}
```

**输出：**
删除重复项后的最终字符串是：this is my pen and pencil text another

## 验证 SSN（社会安全号码）

### 模式
`^\d{3}-\d{2}-\d{4}$`

### 解释：
- `^`：字符串开始
- `\d{3}`：应该以 3 位数字开头
- `-`：后面是一个连字符
- `\d{2}`：后面是 2 位数字
- `-`：后面是一个连字符
- `\d{4}`：后面是 4 位数字
- `$`：字符串结束

### 示例代码：
```java
package com.sample.regexsample;

import java.util.ArrayList;
import java.util.List;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForSSN {

    public static void main(String args[]) {
        String patternString = "^(\\d{3}-\\d{2}-\\d{4})$";

        List<String> input = new ArrayList<String>();
        input.add("123-45-6789");
        input.add("9876-5-4321");
        input.add("987-65-4321 (attack)");
        input.add("987-65-4321 ");
        input.add("192-83-7465");

        Pattern pattern = Pattern.compile(patternString);

        for (String ssn : input) {
            Matcher m = pattern.matcher(ssn);
            if (m.matches()) {
                System.out.println("Found SSN: " + ssn);
            }
        }
    }
}
```

**输出：**
找到 SSN: 123-45-6789
找到 SSN: 192-83-7465

## 测验

编写一个程序来根据以下条件验证 SSN：
1. 社会安全号码的任何一组**不能**包含全零（例如 `000-##`，`###-00-`，`###-##-0000`）
2. 以 `666` 开头
3. 以 `900-999` 之间的任何值开头

### 解决方案：
```java
package com.sample.regexsample;

import java.util.ArrayList;
import java.util.List;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForSSN {

    public static void main(String args[]) {
        String patternString = "^(?!666|000|9\\d{2})\\d{3}-(?!00)\\d{2}-(?!0{4})\\d{4}$";

        List<String> input = new ArrayList<String>();
        input.add("123-45-6789");
        input.add("9876-5-4321");
        input.add("987-65-4321 (attack)");
        input.add("987-65-4321 ");
        input.add("192-83-7465");
        input.add("666-83-7465");
        input.add("999-83-7465");
        input.add("000-83-7465");

        Pattern pattern = Pattern.compile(patternString);

        for (String ssn : input) {
            Matcher m = pattern.matcher(ssn);
            if (m.matches()) {
                System.out.println("Found good SSN: " + ssn);
            } else {
                System.out.println("Found bad SSN: " + ssn);
            }
        }
    }
}
```

**输出：**
找到有效的 SSN: 123-45-6789
bad SSN: 9876-5-4321
bad SSN: 987-65-4321 (attack)
bad SSN: 987-65-4321 
找到有效的 SSN: 192-83-7465
bad SSN: 666-83-7465
bad SSN: 999-83-7465
bad SSN: 000-83-7465

## 验证邮政编码

```java
// 有效邮政编码
CANzips.add("K1A 0B1");
CANzips.add("B1Z 0B9");
CANzips.add("K1A 0D1");
CANzips.add("W1A 0B1");
CANzips.add("Z1A 0B1");

// 有效邮政编码
INDzips.add("400 117");
INDzips.add("600 117");
INDzips.add("623 4315");
INDzips.add("400050");

// 无效邮政编码
INDzips.add("0200");
INDzips.add("7312=-3535");
INDzips.add("2415 4545");
INDzips.add("320645");

// 有效邮政编码
UKzips.add("SW1W 0NY");
UKzips.add("PO16 7GZ");
UKzips.add("GU16 7HF");
UKzips.add("L1 8JQ");

// 无效邮政编码
UKzips.add("Z1A 0B1");
UKzips.add("A1A 0B11");

// 有效邮政编码
AUzips.add("0200");
AUzips.add("7312");
AUzips.add("2415");
AUzips.add("3206");

// 无效邮政编码
AUzips.add("0300");
AUzips.add("7612");
UKzips.add("2915");
UKzips.add("12345-67890");

String regexUK = "^[A-Z]{1,2}[0-9R][0-9A-Z]? [0-9][ABD-HJLNP-UW-Z]{2}$";
String regexIndia = "^\\d{3}\\s?\\d{3}$";
String regexAu = "^(0[289][0-9]{2})|([1345689][0-9]{3})|(2[0-8][0-9]{2})|(290[0-9])|(291[0-4])|(7[0-4][0-9]{2})|(7[8-9][0-9]{2})$";
String regexCAN = "^(?!.*[DFIOQU])[A-VXY][0-9][A-Z] ?[0-9][A-Z][0-9]$";

Pattern pattern = Pattern.compile(regexUK);
Pattern pattern2 = Pattern.compile(regexIndia);
Pattern pattern3 = Pattern.compile(regexAu);
Pattern pattern4 = Pattern.compile(regexCAN);

for (String zip : CANzips) {
    Matcher matcher = pattern4.matcher(zip);
    if (matcher.matches()) {
        System.out.println("ZIPCODE " + zip + " Matches " + matcher.matches());
    } else {
        System.out.println("ZIPCODE " + zip + " does not match " + matcher.matches());
    }
}

for (String zip : UKzips) {
    Matcher matcher = pattern.matcher(zip);
    if (matcher.matches()) {
        System.out.println("ZIPCODE " + zip + " Matches " + matcher.matches());
    } else {
        System.out.println("ZIPCODE " + zip + " does not match " + matcher.matches());
    }
}

for (String zip : INDzips) {
    Matcher matcher = pattern2.matcher(zip);
    if (matcher.matches()) {
        System.out.println("ZIPCODE " + zip + " Matches " + matcher.matches());
    } else {
        System.out.println("ZIPCODE " + zip + " does not match " + matcher.matches());
    }
}

for (String zip : AUzips) {
    Matcher matcher = pattern3.matcher(zip);
    if (matcher.matches()) {
        System.out.println("ZIPCODE " + zip + " Matches " + matcher.matches());
    } else {
        System.out.println("ZIPCODE " + zip + " does not match " + matcher.matches());
    }
}
```

**输出：**
ZIPCODE K1A 0B1 Matches true
ZIPCODE B1Z 0B9 Matches true
ZIPCODE K1A 0D1 does not match false
ZIPCODE W1A 0B1 does not match false
ZIPCODE Z1A 0B1 does not match false
ZIPCODE SW1W 0NY Matches true
ZIPCODE PO16 7GZ Matches true
ZIPCODE GU16 7HF Matches true
ZIPCODE L1 8JQ Matches true
ZIPCODE Z1A 0B1 does not match false
ZIPCODE A1A 0B11 does not match false
ZIPCODE 2915 does not match false
ZIPCODE 12345-67890 does not match false
ZIPCODE 400 117 Matches true
ZIPCODE 600 117 Matches true
ZIPCODE 623 4315 does not match false
ZIPCODE 400050 Matches true
ZIPCODE 0200 does not match false
ZIPCODE 7312=-3535 does not match false
ZIPCODE 2415 4545 does not match false
ZIPCODE 320645 Matches true
ZIPCODE 0200 Matches true
ZIPCODE 7312 Matches true
ZIPCODE 2415 Matches true
ZIPCODE 3206 Matches true
ZIPCODE 0300 does not match false
ZIPCODE 7612 does not match false

## 限制文本长度

模式：
`^(?i)[A-Z]{1,10}$`

解释：
- `^`：匹配字符串的起始位置
- `(?i)`：忽略大小写
- `[A-Z]`：匹配 A 到 Z 之间的任意一个字母
- `{1,10}`：在 1 到 10 次之间

### 示例代码：
```java
package com.sample.regexsample;

import java.util.ArrayList;
import java.util.List;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class Example {

    public static void main(String[] args) {
        String regex = "^(?i)[A-Z]{1,10}$";
        Pattern pattern = Pattern.compile(regex);
        // ... 逻辑 ...
    }
}
```



## 限制输入文本的数量

### 模式
```regex
^\W*(?:\w+\b\W*){2,10}$
```

### 解释
- `^`：匹配字符串的起始位置。
- `\W*`：可选的非单词字符。
- `\w+`：单词字符。
- `\b`：边界字符。
- `\W*`：再次可选非单词字符。
- `{2,10}`：限制在 2 到 10 次之间。
- `$`：匹配字符串的结束位置。

### 示例代码
```java
System.out.println("The input " + input + " matches " + matcher.matches());
```

### 输出
```text
The input KAREN matches false
The input JAVA CRAZY matches true
The input KAREN NEX FROM ITALY matches true
The input test whether number of words in input text is between some minimum and maximum limit matches false
```

## 限制文本中的行数

### 模式
```regex
^(?>[^\r\n]*(?>\r\n?|\n)){0,3}[^\r\n]*$
```

### 解释
- `^`：断言位于字符串的开头位置。
- `(?>`：分组但不捕获或保留回溯位置：
    - `[^\r\n]*`：匹配零或多个除 CR（回车符）和 LF（换行符）以外的字符。
    - `(?>`：分组但不捕获或保留回溯位置：
        - `\r\n?`：匹配一个 CR，后面可选跟随一个 LF (CRLF)。
        - `|`：或者：
        - `\n`：匹配一个独立的 LF 字符。
    - `)`：结束非捕获的原子分组。
- `){0,4}`：结束分组；重复零到四次。
- `[^\r\n]*`：匹配零或多个除 CR 和 LF 以外的字符。
- `$`：断言位于字符串的结尾位置。

### 示例代码：验证零到三行输入
```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForInputLines {

    public static void main(String[] args) {

        StringBuilder builder = new StringBuilder();

        StringBuilder builder1 = new StringBuilder();
        builder1.append("Test Line 1");
        builder1.append("\n");
        builder1.append("Test Line 2");
        builder1.append("\n");

        StringBuilder builder2 = new StringBuilder();
        builder2.append("Test Line 1");
        builder2.append("\n");
        builder2.append("Test Line 2");
        builder2.append("\n");
        builder2.append("Test Line 3");
        builder2.append("\n");
        builder2.append("Test Line 4");
        builder2.append("\n");

        String regex = "\\A(?>[^\r\n]*(?>\r\n?|\n)){0,3}[^\r\n]*\\z";

        Pattern pattern = Pattern.compile(regex);

        Matcher matcher = pattern.matcher(builder.toString());
        System.out.println("Input 1 Zero lines  " + matcher.matches());

        Matcher matcher1 = pattern.matcher(builder1.toString());
        System.out.println("Input 2 Zero lines   " + matcher1.matches());

        Matcher matcher2 = pattern.matcher(builder2.toString());
        System.out.println("Input 3 Four lines   " + matcher2.matches());
    }
}
```

### 输出
```text
Input 1 Zero lines true
Input 2 Zero lines true
Input 3 Four lines false
```

### 验证
1. 编写程序验证 6 行和 8 行输入流。

### 答案
#### 6 行的示例代码
```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForInputLines {

    public static void main(String[] args) {

        StringBuilder builder = new StringBuilder();

        StringBuilder builder1 = new StringBuilder();
        builder1.append("Test Line 1");
        builder1.append("\n");
        builder1.append("Test Line 2");
        builder1.append("\n");

        StringBuilder builder2 = new StringBuilder();
        builder2.append("Test Line 1");
        builder2.append("\n");
        builder2.append("Test Line 2");
        builder2.append("\n");
        builder2.append("Test Line 3");
        builder2.append("\n");
        builder2.append("Test Line 4");
        builder2.append("\n");

        StringBuilder builder3 = new StringBuilder();
        builder3.append("Test Line 1");
        builder3.append("\n");
        builder3.append("Test Line 2");
        builder3.append("\n");
        builder3.append("Test Line 3");
        builder3.append("\n");
        builder3.append("Test Line 4");
        builder3.append("\n");
        builder3.append("Test Line 5");
        builder3.append("\n");
        builder3.append("Test Line 6");
        builder3.append("\n");

        StringBuilder builder4 = new StringBuilder();
        builder4.append("Test Line 1");
        builder4.append("\n");
        builder4.append("Test Line 2");
        builder4.append("\n");
        builder4.append("Test Line 3");
        builder4.append("\n");
        builder4.append("Test Line 4");
        builder4.append("\n");
        builder4.append("Test Line 5");
        builder4.append("\n");
        builder4.append("Test Line 6");
        builder4.append("\n");
        builder4.append("Test Line 7");
        builder4.append("\n");

        String regex = "\\A(?>[^\r\n]*(?>\r\n?|\n)){0,3}[^\r\n]*\\z";

        Pattern pattern = Pattern.compile(regex);

        Matcher matcher = pattern.matcher(builder.toString());
        System.out.println("Input 1 Zero lines  " + matcher.matches());

        Matcher matcher1 = pattern.matcher(builder1.toString());
        System.out.println("Input 2 Zero lines   " + matcher1.matches());

        Matcher matcher2 = pattern.matcher(builder2.toString());
        System.out.println("Input 3 Four lines   " + matcher2.matches());
    }
}
```

#### 扩展验证代码
```java
Matcher matcher = pattern.matcher(builder.toString());
System.out.println("Input 1 Zero lines  " + matcher.matches());

Matcher matcher1 = pattern.matcher(builder1.toString());
System.out.println("Input 2 Two lines  " + matcher1.matches());

Matcher matcher2 = pattern.matcher(builder2.toString());
System.out.println("Input 3 Four lines  " + matcher2.matches());

Matcher matcher3 = pattern.matcher(builder3.toString());
System.out.println("Input 4 Six lines  " + matcher3.matches());

Matcher matcher4 = pattern.matcher(builder4.toString());
System.out.println("Input 5 Seven lines  " + matcher4.matches());

Matcher matcher5 = pattern.matcher(builder5.toString());
System.out.println("Input 6 eight lines  " + matcher5.matches());

Matcher matcher6 = pattern.matcher(builder6.toString());
System.out.println("Input 7 nine lines  " + matcher6.matches());
```

#### 输出
```text
Input 1 Zero lines  true
Input 2 Two lines  true
Input 3 Four lines  true
Input 4 Six lines  true
Input 5 Seven lines  true
Input 6 eight lines  true
Input 7 nine lines  false
```

## 在行的开头和/或结尾匹配内容

### 模式
```regex
^wordToSearch
```

### 解释
- `^`：指定字符串行开头的位置。
- `wordToSearch`：要搜索的单词。

### 模式
```regex
wordToSearch$
```

### 解释
- `wordToSearch`：要搜索的单词。
- `$`：指定字符串行结尾的位置。

## 多行搜索模式

### 模式
```regex
(?m)^wordToSearch
```

### 解释
- `(?m)`：启用多行模式。
- `^`：指定字符串行开头的位置。
- `wordToSearch`：要搜索的单词。

### 模式
```regex
(?m)wordToSearch$
```

### 解释
- `(?m)`：启用多行模式。
- `wordToSearch`：要搜索的单词。
- `$`：指定字符串行结尾的位置。

### 单行模式示例代码
```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForMultiLineSearch {

    public static void main(String[] args) {

        String content = "begin here to start, and go there to end\n" +
                         "come here to begin, and end there to finish\n" +
                         "begin here to start, and go there to end";

        String regex = "^begin";
        String regex2 = "end$";

        Pattern pattern = Pattern.compile(regex, Pattern.CASE_INSENSITIVE);
        Matcher matcher = pattern.matcher(content);

        System.out.println("Finding a word at beginning");
        while (matcher.find()) {
            System.out.print("Start index: " + matcher.start());
            System.out.print(" End index: " + matcher.end() + " ");
            System.out.println(matcher.group());
        }

        Pattern pattern2 = Pattern.compile(regex2, Pattern.CASE_INSENSITIVE);
        Matcher matcher2 = pattern2.matcher(content);

        System.out.println("Finding a word at end");
        while (matcher2.find()) {
            System.out.print("Start index: " + matcher2.start());
            System.out.print(" End index: " + matcher2.end() + " ");
            System.out.println(matcher2.group());
        }
    }
}
```

### 输出
```text
Finding a word at beginning
Start index: 0 End index: 5 
Finding a word at end
Start index: 22 End index: 25 
```

### 多行模式示例代码
```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForLineSearch2 {
```



# 使用边界匹配完整单词

这主要用于在日志文件等文本中搜索单词。

## 模式

`\bword\b`

## 解释

`\b` 表示要搜索的边界。关于 `\b` 的工作原理，它通常匹配以下位置：

1. 数据开头，如果第一个字符是单词字符。
2. 数据末尾，如果最后一个字符是单词字符。
3. 数据中两个字符之间，且其中一个是单词字符而另一个不是。

## 示例代码

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForBoundary {

    static void main(String[] args) {

        String data1 = "Today, java is oriented language";

        String regex = "\\bjava\\b";

        Pattern pattern = Pattern.compile(regex, Pattern.CASE_INSENSITIVE);

        Matcher matcher = pattern.matcher(data1);

        while (matcher.find()) {

            System.out.print("Start index: " + matcher.start());
            System.out.print(" End index: " + matcher.end() + " ");
            System.out.println(matcher.group());

        }

    }

}
```

输出：

```
Start index: 7 End index: 11 java
```

# 验证商标 ™ 符号

## 模式

`\u2122`

## 解释

这是商标符号的 Unicode 字符。

## 示例代码

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForTrademark {

    public static void main(String[] args) {

        String data1 = "Searching in trademark character ™ is so easy when you know it.";

        String regex = "\u2122";

        Pattern pattern = Pattern.compile(regex, Pattern.CASE_INSENSITIVE);

        Matcher matcher = pattern.matcher(data1);

        while (matcher.find()) {

            System.out.print("Start index: " + matcher.start());
            System.out.print(" End index: " + matcher.end() + " ");
            System.out.println(matcher.group());

        }

    }

}
```

输出：

```
Start index: 33 End index: 34 ™
```

# 验证货币符号

## 模式

`\p{Sc}`

## 解释

用于货币符号的 Unicode 符号。

## 示例代码

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForCurrency {

    public static void main(String[] args) {

        String content = "Let's find the symbols or currencies : $ Dollar, € Euro, ¥ Yen";

        String regex = "\\p{Sc}";

        Pattern pattern = Pattern.compile(regex, Pattern.CASE_INSENSITIVE);

        Matcher matcher = pattern.matcher(content);

        while (matcher.find()) {

            System.out.print("Start index: " + matcher.start());
            System.out.print(" End index: " + matcher.end() + " ");
            System.out.println(" : " + matcher.group());

        }

    }

}
```

输出：

```
Start index: 39 End index: 40  : $
Start index: 49 End index: 50  : €
Start index: 57 End index: 58  : ¥
```

# 第 18 章：使用正则表达式时的常见错误

以下是我们使用 `REGEX` 时常见的错误：

## 使用简单字符串匹配时的错误

例如，让我们考虑想要在字符串 `asdfdfdasdfdfdf` 中搜索 `dfd` 的出现次数。如果我们查看该字符串，它显示我们可以在 `String` 中找到 4 次。

让我们使用正则表达式来评估并找出我们的小型 Java 程序是如何输出的。

### 示例代码

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForMistakes {

    public static void main(String[] args) {

        String source = "asdfdfdasdfdfdf";

        Pattern pattern = Pattern.compile("dfd");

        Matcher matcher = pattern.matcher(source);

        int hits = 0;

        while (matcher.find()) {

            hits++;

        }

        System.out.println(hits);

    }

}
```

输出：

```
2 而不是 4
```

那么问题所在在哪里？要么我们的代码错了，要么逻辑运行方式与预期不同。事实上，情况确实如此。

在 Java 中使用正则表达式时的第一个重要规则是：搜索从左到右运行，如果一个字符已经在搜索中使用过，它将不会被重复使用。所以，当我们看到 `dfdfd` 时，我们使用了前三个字母进行匹配，只剩下 `fd`，这是无法匹配的。因此，在编写需要评估的表达式时，我们需要小心。

## 对 `\` 字符的谨慎使用

让我们考虑我们的应用程序想要从服务接收到的长文本中读取 IP 地址。首先要考虑的点是 IP 地址格式的定义。我们有 4 组由点分隔的数字，范围从 0 到 255。让我们将其写成正则表达式。如果你有更好或更优雅的解决方案，欢迎随时评论。

Pattern: `\b(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.{3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\b`

基本上，它获取了前三个由点分隔的允许数字，并重复了 3 次，最后一个块具有相同的模式，但没有末尾的点。

### 示例代码（错误版本）

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForIPMistake {

    public static void main(String[] args) {

        String logtext = "asdfesgew 215.2.125.32 alkejo 234 oij982jld" + "kja.lkwech . 24.33.125.234 kadfjeladkj";

        String regexpatter = "\b(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.{3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\b";

        Pattern pattern = Pattern.compile(regexpatter);

        Matcher matcher = pattern.matcher(logtext);

        while (matcher.find()) {

            System.out.println(logtext.substring(matcher.start(), matcher.end()));

        }

    }

}
```

输出：

它什么都不会打印，因为 `\b` 字符没有使用反斜杠，且边界没有定义。

### 正确的代码

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForIPMistake {

    public static void main(String[] args) {

        String logtext = "asdfesgew 215.2.125.32 alkejo 234 oij982jld" + "kja.lkwech . 24.33.125.234 kadfjeladkj";

        String regexpatter = "\\b(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\\.{3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\\b";

        Pattern pattern = Pattern.compile(regexpatter);

        Matcher matcher = pattern.matcher(logtext);

        while (matcher.find()) {

            System.out.println(logtext.substring(matcher.start(), matcher.end()));

        }

    }

}
```

输出：

```
215.2.125.32
24.33.125.234
```



## `\` 字符的谨慎使用

让我们考虑我们的应用程序想要从服务接收到的长文本中读取 IP 地址。首先要考虑的点是 IP 地址格式的定义。我们有 4 组由点分隔的数字，范围从 0 到 255。让我们将其写成正则表达式。如果你有更好或更优雅的解决方案，欢迎随时评论。

Pattern: `\b(?:25[0-5]|2[0-4][0-9]|[01?[0-9][0-9]?)\.{3}(?:25[0-5]|2[0-4][0-9]|[01?[0-9][0-9]?)\b`

基本上，它获取了前三个由点分隔的允许数字，并重复了 3 次，最后一个块具有相同的模式，但没有末尾的点。

示例代码：

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForIPMistake {

    public static void main(String[] args) {

        String logtext = "asdfesgew 215.2.125.32 alkejo 234 oij982jld" + "kja.lkwech . 24.33.125.234 kadfjeladkj";

        String regexpatter = "\b(?:25[0-5]|2[0-4][0-9]|[01?[0-9][0-9]?)\.{3}(?:25[0-5]|2[0-4][0-9]|[01?[0-9][0-9]?)\b";

        Pattern pattern = Pattern.compile(regexpatter);

        Matcher matcher = pattern.matcher(logtext);

        while (matcher.find()) {

            System.out.println(logtext.substring(matcher.start(), matcher.end()));

        }

    }

}
```

Output:

它什么都不会打印，因为 `\b` 字符没有使用反斜杠，且边界没有定义。

正确的代码：

```java
package com.sample.regexsample;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class DemoForIPMistake {

    public static void main(String[] args) {

        String logtext = "asdfesgew 215.2.125.32 alkejo 234 oij982jld" + "kja.lkwech . 24.33.125.234 kadfjeladkj";

        String regexpatter = "\\b(?:25[0-5]|2[0-4][0-9]|[01?[0-9][0-9]?)\\.{3}(?:25[0-5]|2[0-4][0-9]|[01?[0-9][0-9]?)\\b";

        Pattern pattern = Pattern.compile(regexpatter);

        Matcher matcher = pattern.matcher(logtext);

        while (matcher.find()) {

            System.out.println(logtext.substring(matcher.start(), matcher.end()));

        }

    }

}
```

## 字符类的用法

大多数正则用户犯的一个常见错误是尝试使用字符类来节省字符。乍看之下这对于允许大小写字母非常有用。然而 `[A-z]` 实际上等同于 `[A-Za-z]` 包含了某些标点符号。

### 1. `java.lang.IllegalStateException`: 使用命名组时未匹配

这种异常在我们尝试从 matcher 中获取命名组时，如果没有进行匹配将会发生。

错误日志显示如下：

```
Exception in thread "main" java.lang.IllegalStateException: No match found
    at java.util.regex.Matcher.group(Unknown Source)
```

该错误的根源在于，我们可能没有在获取命名组之前使用 `matcher.matches()`。

让我们考虑下面的代码段：

```java
List<String> dates = new ArrayList<String>();

dates.add("02/31/2011"); // 无效日期
dates.add("02/27/2011"); // 有效日期

String regex = "^(?<month>[0-3]?[0-9])/(?<day>[0-3]?[0-9])/(?<year>(?:0-9]{2})?[0-9]{2})$";

Pattern pattern = Pattern.compile(regex);

for (String date : dates) {

    Matcher matcher = pattern.matcher(date);

    // 这一步如果没有执行，就会得到异常！
    matcher.matches();

    // 获取日期部分
    String day = matcher.group(2);
    String month = matcher.group(1);
    String year = matcher.group(3);

    String formattedDate = month + "/" + day + "/" + year;

    System.out.println("检查检查日期 : " + formattedDate);

}
```



# 第 20 章：结语

简而言之，正则表达式提供了一个极其灵活且强大的文本处理系统。我们将正则表达式描述为用于在文本中搜索的文本模式。我们通过将正则表达式与文本进行“匹配”来实现这一点。将正则表达式与文本进行匹配的结果是一个 `true` / `false` 值（用于指定正则表达式是否匹配了文本），或者一组匹配项——文本中发现的每一个正则表达式出现都对应一个匹配项。

例如，我们可以使用正则表达式在 HTML 页面中搜索电子邮件地址、URL、电话号码等。这是通过将不同的正则表达式与 HTML 页面进行匹配来实现的。每个正则表达式与 HTML 页面匹配的结果将是一组匹配项——每个正则表达式对应一组匹配项（每个正则表达式可能会匹配多次）。

但我们需要理解：

1. 正则表达式起初并不容易使用
   - 每一个组成部分并不难，但需要大量的练习（甚至会流泪，为什么不呢？）才能学会正确地将它们组合在一起
2. 正则表达式构成了一种微型编程语言
   - 它与 `Java` 是不同类型的编程语言，需要你学习新的思维模式
   - 在 `Java` 中你不能直接使用正则表达式；你必须先创建 `Patterns` 和 `Matchers`
   - `Java` 的 `String` 常量语法也没有什么帮助
   - 尽管如此，正则表达式为 `String` 操作带来了如此强大的功能和便利，因此它们非常值得投入精力学习。

总结一下，想象一下如果所有的计算机问题或项目都是这样：你遇到的每一个问题，无论简单还是复杂，都只用英文写，因为没有人能看懂那些符号。这会让我们疯掉，即使你完全不知道编程的基础知识。

幸运的是，人类发明了符号来简洁地描述那些符号最擅长描述的事物，并将人类语言留来描述其他事物。符号语言充当构建块，在短的空间内构建复杂的结构，而这些结构用一整本书的英文才能描述。

Eprogramy

附：还有一件事。在 Eprogramy，我们想送你一份礼物。如果你像我们一样喜欢 `Java Regex`，那么你可能也会喜欢 Python。因此，在接下来的章节中，你将看到我们的预告——《PYTHON CRASH COURSE - The Ultimate Beginner’s Course to Learning Python Programming in Under 12 Hours》。

我知道你会喜欢它的！

你可以在亚马逊上找到它，搜索我们的名字 Eprogramy，或者点击此链接：

![](http://www.amazon.com/Python-Ultimate-Beginners-Learning-Programming-ebook/dp/B00ZCRSCFG/)

[`http://www.amazon.com/Python-Ultimate-Beginners-Learning-Programming-ebook/dp/B00ZCRSCFG/`]

# 《Python 速成班 - 在 12 小时内学习 Python 编程的终极初学者课程》预告

# 引言：欢迎来到你的新编程语言

所以，你决定学习 Python 编程了？很好，祝喜并欢迎来到你的新编程语言！你会喜欢它的！

在 Eprogramy，我们相信，良好教育的基础是提供能够开启未来之门的工具。不可否认的是，世界已经进入了一个我们一切都触手可及的时代。社会需求发生了变化。因此，今天的通信也发生了变化。沟通开启了大门，所以学习如何沟通是我们的挑战。在 Eprogramy，我们希望你学习如何用一种新语言交流：编程语言。这种语言允许我们使用电脑或笔记本电脑进行创作。

也许道路是艰难且艰辛的，但我们将为读者提供工具让学习变得有趣且富有成效。我们将展示学习如何编程所需的所有方面。从基础字母到解决最常见的编程问题，以及更多、更多内容。始终会有大量示例的帮助，这将有助于更好地理解。

我们知道自己在做什么，并相信你完全有能力吸收我们的教学。

未来的门已经开启。让我们一起一步步前进吧。

让我们开始吧！

Eprogramy 团队

# 第 1 章：Python 编程语言

## Python 的历史

Python 被称为初学者的首选语言，因为它被全球计算机程序员推荐为适合初学者学习的好门语言。这不应被误认为是基于它的强大。

Python 语言由 Guido Von Rossum 于 1990 年在荷兰的数学中心（Stichting Mathematisch Centrium）创建。该语言实际上是由一个大型志愿者团队开发的，并开放修改。在它所处的开发阶段，它已经包含了具有继承关系的类、异常处理、函数以及 `list`、`dict`、`str` 等核心数据类型。

2000 年 5 月，Guido 和 Python 开发团队移动到 BeOpen.com 组成 BeOpen PythonLabs 团队。同年，PythonLabs 团队移动到 Digital Creations，现在被称为 Zope Corporation。

Python `2.0` 于 2000 年 10 月 16 日发布，其特性包括垃圾回收器，这有助于维护编程中的内存处理相关问题。Python 的伟大之处在于它有社区的支持，并且在利用 Python 的用户背后有一套透明的机制。

之后，Python `3.0` 作为一个重大的不后兼容版本在经过长时间测试后，于 2008 年 12 月 3 日发布。`3.0` 的主要特性也回移植到了 Python `2.6` 和 `2.7`。

Python 版本发布日期：

- Python `1.0` - 1994 年
- Python `1.5` - 1997 年 12 月 31 日
- Python `1.6` - 2000 年 9 月 5 日
- Python `2.0` - 2000 年 10 月 16 日
- Python `2.1` - 2001 年 4 月 17 日
- Python `2.2` - 2001 年 12 月 21 日
- Python `2.3` - 2003 年 7 月 29 日
- Python `2.4` - 2004 年 11 月 30 日
- Python `2.5` - 2006 年 9 月 19 日
- Python `2.6` - 2008 年 10 月 1 日
- Python `2.7` - 2010 年 7 月 3 日
- Python `3.0` - 2008 年 12 月 3 日
- Python `3.1` - 2009 年 6 月 27 日
- Python `3.2` - 2011 年 2 月 20 日
- Python `3.3` - 2012 年 9 月 29 日
- Python `3.4` - 2014 年 3 月 16 日

## 什么是 Python？

Python 是一种免费提供的面向对象、高级且具有动态语义的编程语言。许多程序员对 Python 赞誉有加，因为它提供了更高的生产力，因为编辑-测试-调试循环非常快。

Python 语言具有简单、易于学习的语法，通过大量的英语单词提高了可读性和效率。在 Python 中编写代码，感觉更像是在用自己的想法写出解决方案，而不是在引用语言为了实现某些功能时所需的模糊符号。

Python 可用于自动化测量和交互式处理数据。与其他许多编程语言相比，Python 能够轻松处理大型数据库并计算大量数字。它可以作为内部脚本语言，供其他程序执行特定功能。通过学习 Python，你将能够编写复杂的软件，如复杂的网络爬虫。

Python 的伟大之处在于它拥有庞大的网络爬虫库，并因其网页抓取能力而被广泛使用。网络爬虫简单来说就是一个根据其设定的参数在网络上进行导航，并抓取你希望它抓取内容的程序。

而言之，无论你是编程初学者还是其他语言的资深人士，Python 都非常上手。它是一门快速、友好且易于学习的语言，但不要因此误以为它不那么强大。

# 第 2 章

## Python 的安装

为了在机器上安装 Python，你必须下载以下内容：

1. Python 解释器
2. Python IDE

下载这两个工具将开启你通往 Python 程序员的道路。IDE（集成开发环境）是程序员使用的程序化应用程序，因为它包含了处理和执行代码所需的工具。一个 IDE 包含一个代码编辑器、一个编译器、一个调试器和一个图形用户界面（GUI）。IDE 有许多不同类型，但最常用的是 Python 的 `PyCharm`。在从 JetBrains 获取 `PyCharm` IDE 之前，你必须先在你的系统上安装好 `Python` 解释器（`IDLE` 版本 3.4），以便 `PyCharm` 能够检测到计算机上的 Python。

在本指南中，推荐使用 `PyCharm`，因为本文将使用它。如果你使用相同的 IDE，可以更容易跟上我的思路。下载 Python 解释器，请使用以下链接：

[`www.python.org/downloads/`](https://www.python.org/downloads/)

进入此链接后，你需要找到这个：

![`puu.sh/hTvWC/e539a9177f.png`](img/00008.jpeg)

然后，点击 download，文件将相应下载。一旦拥有此文件，执行它并按照向导中的指令安装 Python 解释器。

一旦安装了 Python 解释器，我们就可以开始下载 `PyCharm`。安装 `PyCharm`，请访问以下链接：

[`www.jetbrains.com/pycharm/download/`](https://www.jetbrains.com/pycharm/download/)

![`puu.sh/hTw3f/dd49e7ad1c.png`](img/00009.jpeg)

你现在应该处于这个屏幕（或类似的界面）——点击“Download Community”按钮并继续下载 `PyCharm`。在此过程中，它会自动检测 Python 3.4 `IDLE`，但在少数情况下，你可能需要指定你安装 Python 的目录。

一旦完成 PyCharm 和 Python 3.4 `IDLE` 的安装，进入 `File`（文件）`New Project`（新建项目）。你将看到此屏幕：

![`puu.sh/hTwox/5ba1669ce6.png`](img/00010.jpeg)

你可以将 `Location`字段中的“untitled”部分重命名为特定的项目名称。然后点击“Create”（创建）按钮，你将进入一个空项目。我们必须做的下一件事是创建一个新的 Python 文件，你可以通过以下路径实现：

`File`（文件）`New`（新建）`Python File`（Python 文件）

相应设置你的 Python 文件名，它将显示在项目资源管理器（Project Explorer）中的项目名称下。现在双击文件，你将进入一个可以开始编写 Python 代码的页面。

它看起来应该是这样的：

![`puu.sh/hTwx1/74b6154739.png`](img/00011.jpeg)

你已成功安装了 Python！

# 第 3 章

## Python 语言结构

我们将通过以下示例代码作为示例，学习 Python 作为一种编程语言的结构：

```python
import math

class Program:

    def Execute(self):

        x = math.sqrt(25)

        print(x)

run = Program()

run.Execute()
```

输出：

![`puu.sh/hTy3s/931081aeed.png`](img/00012.jpeg)

为了实际执行代码，你必须使用快捷键 `alt + shift + f10`，或者使用 `PyCharm` 主导航栏中的 `Run`（运行）菜单项执行。

第一行 `import math` 使用了一个特殊的关键字 `import`，它允许程序员从 Python 库中导入在编码时默认不包含的工具。在关键字 `import` 之后——程序员指定了 Python 库中的某个特定目录。在本例中，我们指定了 `math` 目录；如果我们想专门指定 `System` 目录中的内容，我们将添加一个点分隔符（period），然后添加子目录名称。如果库的文件夹更加复杂，你必须使用如下符号：

```python
import bs4 from BeautifulSoup
```

`BeautifulSoup` 库就是这样一个例子，我们希望从 `BeautifulSoup` 目录库中导入 `bs4` 目录，这就是为什么在程序开头使用了 `from` 关键字。

在我们案例中，我们导入了 `math` 模块，因为它包含了函数（你将在指南的后续部分学习更多关于它们的知识——它们可以定义为函数或方法）。为了简要说明，函数只是一个包含系列步骤以完成特定功能的代码块，可以被调用来为我们计算数字。

需要注意的是，代码中的空格至关重要。如果你正在创建一个类，该类的内容需要使用 Tab 键进行一次缩进，以便解释器理解该类所管辖的代码是其下方的缩进代码。任何没有在类下方缩进的代码都不属于该类的一部分。对于你创建的任何函数也是如此。如上例所示，函数通过冒号定义，并在下方紧跟缩进的内容，表示它是该函数的一部分。

Python 的工作机制是它拥有类，类是章节，而函数是类的子章节。这些类可以像主程序中声明的那样在类声明后进行声明，然后通过它们内部携带的函数进行调用。在这种情况下，它是 `Execute`。同样，这在现在可能听起来没意义，但在指南的后续章节将会变得清晰。

# 关于作者

![Dagny Taggart.jpg](img/00013.jpeg)

Eprogramy Academy 由来自不同 IT 领域的专业人士创建，其目标只有一个：为 3.0 时代提供知识。

教育正随着社会需求而变化。在当今的信息时代，教育应该提供在 3.0 世界中创建和解决问题的工具。

在 Eprogramy，我们理解这一点并努力在这种背景下给予人们恰当的回。秉持这一目标，我们提供了各种课程来教授许多编程语言的基础知识。我们相信任何人都可以学习编程语言并应用课程来解决问题。在我们的学院中，我们提供必要的工具，让每个人都能将编程获得的一系列解决方案融入日常生活中。

可能性和解决方案是无限的。

简而言之，在 Eprogramy，我们致力于帮助每个人解码未来的信息。
