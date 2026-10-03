
# Java：快速学习 Java 编程入门指南（编程、数据库、Java 学者指南、编程书籍、Java 编程）（HTML、Javascript、编程、开发者、编码、CSS、PHP 书籍2）

# 介绍

最重要的点是：使用常识。当无法找到规则或指南时。当规则明显不适用时。当其他手段都失败时：请利用常识，检查 Java 和编码的基本原理。这条规则优于所有其他规则。常识是一项要求。

1. 为人编程，而不是为机器编程。使用命名规范。为你的代码编写文档。分段。如果没人看不懂，那么它就没用。

2. 先设计，后代码。在开始编码之前，花时间考虑代码将如何编写，你一定会花费更少编写时间。通过提前考虑未来的变化，你可以减少这些变化对代码的影响。

3. 分小步进行开发。测试和修复 10 行代码比 1000 行要容易得多、快得多；你可以在编写一个单一 100 行代码块的一半时间内，以每 10 行为增量完成编程、测试并修复 100 行代码，从而完成相同的工作。

4. 保持你的代码简单。以后需要重做的代码是不值得自豪的，所以遵循 KISS 原则：保持简单，愚蠢点（Keep It Simple, Stupid）。

5. 学习常见的模式、反模式和惯用法。有大量的分析可以指导你提高开发生产力、设计和流程模式与反模式，以及编程惯用法。

# 第 1 章 – 通用编程指南

我们将从讨论良好编程风格的通用原则以及定义 Java 健壮设计的原则开始本教程。这些原则中的大部分在 Java 编程入门中已经提到过，但本章将引入许多实用建议，以提高你作为开发者的技能。

## 变量作用域

在 Java 语言中，每个局部变量一旦声明就有一个确定的作用域。该变量从声明处到它所声明的方法或代码块的结束都是可见的。因此，有一条必要的规则：尽可能在变量使用的地方声明局部变量。以下是一些示例：

```java
for(final locale : Locale.getLocales()) {
    // 此处进行某些实现
}

try(InputStream in = new FileInputStream("file.txt")) {
    // 此处进行某些实现
}
```

在每个代码段中，局部变量的作用域仅限于其声明所在的块。当块结束时，局部变量不再可见并超出作用域。这种看起来简洁明了，但随着 Lambda 的引入和 Java 8 的发布，许多使用局部变量的知名惯用法正变得过时。以下是利用 Lambda 对上述示例中的 `forEach` 循环进行的重写：

```java
Arrays.stream(Locale.getLocales()).forEach((locale) -> {
    // 此处进行某些实现
});
```

注意，局部变量变成了此函数的参数，然后作为 `forEach` 方法的参数传递。

## 类字段和局部变量

Java 中的每个方法都属于某个特定的类（在某些情况下属于某些接口，例如 Java 8 中方法被声明为 `default`）。在方法实现中使用的局部变量与类成员之间存在发生冲突的概率。Java 编译器会选择正确的变量，但它可能不是开发者想要使用的那一个。许多现代 IDE 在此类冲突发生时会进行大量工作提醒开发者（红色脚本、高亮），然而，在开发过程中主动处理更好。以下是一个示例：

```java
class LocalVariableAndClassMember {
    private long value;

    public long calculateValue(final long initial) {
        long value = initial;
        value *= 10;
        value += value;
        return value;
    }
}
```

这个示例看起来非常简单，但有一个陷阱。名为 `calculateValue` 方法引入了一个名为 `value` 的局部变量，通过这样做隐藏了同名的类成员。代码本应该累加类成员和局部变量，但在应用中它执行了不同的操作。正确的版本应该是那样的（使用 `this` 关键字）：

```java
class LocalVariableAndClassMember {
    private long value;

    public long calculateValue(final long initial) {
        long value = initial;
        value *= 10;
        value += this.value;
        return value;
    }
}
```

这个简单的实现强调了一个重要问题，在某些情况下，调试该问题可能花费几个小时。

## 方法参数和局部变量

许多初学者经常掉入的另一种场景是将方法参数当作局部变量。Java 允许对非 `final` 方法参数重新赋值另一个值（但对原始值没有影响）。例如：

```java
public String sanitize(String str) {
    if(!str.isEmpty()) {
        str = str.trim();
    }
    str = str.toLowerCase();
    return str;
}
```

这并不是最整洁的代码，但它突出了一个问题：方法参数 `str` 被重新赋值了一个不同的值（并被用作局部变量）。在这些情况下（无一例外地），应该避免这种编码模式，可以通过将方法参数声明为 `final` 来避免。

以下是此情况的示例：

```java
01 | public String sanitize( final String str ) {
02 |     String sanitized = str;
03 |
04 |     if( !str.isEmpty() ) {
05 |             sanitized = str.trim();
06 |     }
07 |
08 |     sanitized = sanitized.toLowerCase();
09 |     return sanitized;
10 | }
```

遵循这一简单规则的代码通常更容易理解和推理。即使以引入局部变量为代价也是如此的。

## 装箱与拆箱（Boxing and unboxing）

装箱和拆箱是 Java 技术，允许原始类型（`int`、`long`、`double`）与相应的原始类型包装类（`Integer`、`Long`、`Double`）之间的转换。

尽管 Java 编译器试图通过执行自动装箱（autoboxing）来隐藏这些转换，但这可能会使情况恶化，有时会导致随机结果。

以下是一个示例：

```java
01 | public static void calculate( final long value ) {
02 |     // 在此处进行实现
03 | }
1 | final Long value = null;
2 | calculate( value );
```

这段代码片段可以编译，但在执行 `Long` 和 `long` 之间的转换时会在 `02` 行抛出 `NullPointerException`。这里的最佳建议是使用原始类型（但正如我们所知，某些情况下是不可能的）。

## 接口（Interfaces）

尽可能，接口应优于具体类。这些真实的示例应该能让你至少优先考虑接口。

接口仅与默认方法绑定，而不与任何特定的实现绑定。它们仅仅作为合同运行，在履行合同的方式上提供了许多自由和灵活性。如果实现涉及外部服务或系统，这种灵活性将变得更加重要。

以下是一个简单接口及其可能的实现的示例：

```java
1 | public interface TimezoneService {
2 |     TimeZone getTimeZone( final double lat, final double lon) throws IOException;
3 | }
01 | public class TimezoneServiceImpl implements TimezoneService {
02 |     @Override
03 |     public TimeZone getTimeZone(final double lat, final double lon) throws IOException {
04 |             final URL url= new URL( String.format(
05 |                 "[http://api.geonames.org/timezone?lat=%.2f&lng=%.2f&username=demo",
06 |                 lat, lon
07 |             ) );
08 |             final HttpURLConnection connection = ( HttpURLConnection )url.openConnection();
09 |
10 |             connection.setRequestMethod( "GET" );
11 |             connection.setConnectTimeout( 1000 );
12 |             connection.setReadTimeout( 1000 );
13 |             connection.connect();
14 |
15 |             int status = connection.getResponseCode();
16 |             if (status == 200) {
17 |                 // 在此处做一些事情
18 |             }
19 |
20 |             return TimeZone.getDefault();
21 |     }
22 | }
```

上述代码演示了一种常见的接口/实现模式。该实现专门使用一个外部 HTTP 服务来获取所查询位置的时区。但由于是由接口驱动的，引入另一个使用扁平文件或数据库的实现并不困难。提供这个空实现（也称为 stub 或 mock）是有意义的：

```java
1 | public class TimezoneTestImpl implements TimezoneService {
2 |     @Override
3 |     public TimeZone getTimeZone(final double lat, final double lon) throws IOException {
4 |         return TimeZone.getDefault();
5 |     }
6 | }
```

上面的实现可以使用每个需要 `timezoneService` 的地方，这使得测试场景与依赖隔离开。Java 标准库内部（`Collection`、`Set`）适当使用接口的示例，所有接口都有多个实现支持，当首选合同时，这些实现可以相互且无缝地替换。以下是此的示例：

```java
1 | public static< T > print( final Collection< T > collection ) {
2 |     for( final T element : collection ) {
3 |         System.out.println( element );
4 |     }
5 | }
1 | print( new HashSet< Object >() ) );
2 | print( new ArrayList< Integer >() ) );
3 | print( new TreeSet< String >() ) );
4 | print( new Vector< Long >() ) );
```

## 字符串（Strings）

Java 以及大多数编程语言中使用得广泛的类型之一是 `Strings`。Java 通过简化对字符串的许多例行操作，原生支持拼接和比较。Java 标准库提供了许多独特的类来提高字符串操作的效率。

字符串在 Java 中是不可变对象，并以 UTF-16 格式表示。每当字符串拼接（或执行任何修改原始字符串的操作）时，都会创建一个新的 `String` 类实例。这就是为什么拼接操作会变得低效，启动了许多中间实例（也称为产生垃圾）。

Java 标准库提供了两个有用的类，旨在方便字符串操作：`StringBuilder` 和 `StringBuffer`（主要区别在于 `StringBuffer` 是线程安全的，而 `StringBuilder` 不是）。

以下是使用这些类之一的几个示例：

```java
01 | final StringBuilder sb= new StringBuilder();
02 |
03 | for( int i = 1; i <= 10; ++i ) {
04 |     sb.append( " ");
05 |     sb.append( i );
06 | }
07 |
08 | sb.deleteCharAt( 0 );
09 | sb.insert( 0, "[);
10 | sb.replace( sb.length() - 3, sb.length(), "]" );
```

建议使用 `StringBuilder` / `StringBuffer` 操作字符串，但在拼接两个或三个字符串时可能显得大材小用；在这种情况下，可以使用普通的 `+` 运算符。以下是一个示例：

```java
1 | String userId= "user:" + new Random().nextInt(100);
```

字符串格式化是拼接的替代方案，Java 标准库提供了静态辅助方法 `String.format`。它还支持完整的格式说明符集，包括日期/时间、字符、数字等（参见完整的参考[官方文档](https://docs.oracle.com/javase/7/docs/api/java/util/Formatter.html#syntax)）。

以下通过示例探索格式化的威力：

```text
1 | String.format( "%04d", 1 ) -> 0001
2 | String.format( "%.2f", 15.643624d ) -> 15.64
3 | String.format( "%tR", new Date() ) -> 14:07
4 | String.format( "%tF", new Date() ) -> 2016-20-04
5 | String.format( "%d%%", 22 ) -> 22%
```

在 Java 中，没有理由严格遵守任何特定的命名规范，但有一套易于遵循的规则，使得 Java 代码在标准库或任何其他开源 Java 项目中看起来风格统一。

- 局部变量和方法参数名称使用驼峰命名法：`str`, `newLength`, `minimumCapacity`

- `static final` 字段或枚举常量使用大写，并用下划线 `_` 分隔：`LOG`, `MIN_RADIX`, `INSTANCE`

- 类、`enum`、`interface` 或注解名称使用大写：`StringBuilder`, `Runnable`, `@Override`

- 泛型类型参数名称通常用一个大写字母表示：`T`, `U`, `E`

- 方法或字段名称（`static final` 除外）使用驼峰命名法：`isEmpty`, `format`, `addAll`

- 包名使用小写：`org.junit`, `com.fasterxml.jackson`, `javax.json`

通过这些简单的规范，代码看起来非常简洁，并且与其他库或框架并无二致。

## 标准库

Java 标准库存在一些粗糙之处和奇怪的设计决策，但其中 99% 是由专家编写的高质量代码。熟悉这些资源是值得的。

每个新的 Java 版本都会向现有库添加许多新功能（并可能弃用旧版本），并添加新的库。Java 5 引入了一个新的并发库，整合在 `java.util.concurrent` 包中。Java 6 首次推出了脚本支持 `javax.script` 包和 Java 编译器 API `javax.tools` 包。Java 7 包含了对 `java.util.concurrent` 的改进，在 `java.nio.file` 包引入了新的 I/O 库，并通过 `java.lang.invoke` 包提供了动态语言支持。目前，Java 8 提供了期待已久的日期/时间 API `java.time` 包。

Java 平台正在不断增长和演进；保持对其演变的认知至关重要。每当向项目引入第三方库或框架时，请确保所需的功能在 Java 标准库中尚未提供。

## 不变性

请认真对待不可变性。如果设计的类或实现的方法可以提供不可变性保证，那么它几乎可以通处使用，而无需担心并发修改。这将改善作为开发者和团队成员的生活。

## 测试

测试驱动开发（TDD）在 Java 社区中广泛实践，不断提高代码质量标准。TDD 带来了许多优势，但 Java 标准库目前不包含任何测试框架或脚手架。

测试仍然是现代 Java 开发不可或缺的一部分。在这里我们将使用编写良好的 `JUnit` 框架涵盖一些基础。使用 `JUnit`，每个测试都是一组关于预期对象状态或行为的断言。

优秀的测试是短而简单的，一次只测试一点。让我们通过编写一组测试来验证“字符串”章节中的 `String.format` 函数返回预期的结果：



```java
package com.javacodegeeks.advanced.generic;

import static org.junit.Assert.assertThat;
import static org.hamcrest.CoreMatchers.equalTo;
import org.junit.Test;

public class StringFormatTestCase {
    @Test
    public void testNumberFormattingWithLeadingZeros() {
        final String formatted = String.format("%04d", 1);
        assertThat(formatted, equalTo("0001"));
    }

    @Test
    public void testDoubleFormattingWithTwoDecimalPoints() {
        final String formatted = String.format("%.2f", 12.324234d);
        assertThat(formatted, equalTo("12.32"));
    }
}
```

这些测试具有可读性且执行是例化的。一个 Java 项目包含成百上千个测试例，以便对回归问题或开发中的功能提供快速反馈。

# 第 2 章 - 如何以及何时使用异常

## 引言

Java 中的异常表示程序流中的异常或特殊情况，这些情况可能会阻止程序的继续运行。这些异常情况可能是致命的；即程序无法继续运行并应该终止。或者这些情况是可以恢复的；即程序继续运行但某些功能可能会丢失。

在这里我们将遍历一个使用 Java 异常的典型场景，解释检查异常和未检出异常，并涉及一些边界情况和实用的写法。

## 异常：何时使用它们

简单来说，异常是程序执行过程中发生并中断正常执行流的事件或信号。异常是早期使用的错误代码和状态技术的替代品。现在，异常已被接受为包括 Java 在内的多种语言的标准。异常处理有一个通用的重要规则：不要忽略。每个异常都应该被记录，但绝不能忽略。在极少数情况下，由于对异常无法做处理，异常是可以被忽略的。

Java 中的异常管理是独特的。异常分为两类：检查异常（checked exceptions）和未检出异常（unchecked exceptions）。

未检出异常表示与程序逻辑和假设相关的错误（无效参数、空指针等）。未检出异常不需要调用者定义。其声明如下：

```java
public class NullPointerException extends RuntimeException {
    public NullPointerException() {
        super();
    }

    public NullPointerException(String s) {
        super(s);
    }
}
```

检查异常显示直接控制范围之外的无效条件。检查异常是 `Exception` 的直接子类。与未检出异常不同，检查异常必须由调用者捕获或作为方法签名的一部分列出。`IOException` 是最著名的：

```java
public class IOException extends Exception {
    public IOException() {
        super();
    }

    public IOException(String message) {
        super(message);
    }

    public IOException(String message, Throwable cause) {
        super(message, cause);
    }

    public IOException(Throwable cause) {
        super(cause);
    }
}
```

检查异常和未检出异常引入的样板代码和丑陋的代码模式比解决实际问题要多得多。Java 生态系统中出现的典型模式是，将检查异常隐藏或封装在未检出异常内部。

下面是一个示例：

```java
try {
    // 此处执行某些 I/O 操作
}
```

```java
} catch( final IOException ex ) {
    throw new RuntimeException( "I/O operation failed", ex );
}
```

精心设计的异常层次结构可以减少所需的样板代码量。

Java 中另一类继承自 `Error` 类的额外异常是 `OutOfMemoryError` 或 `StackOverflowError`。这些异常表示致命的执行失败，会导致程序立即终止且没有任何恢复可能。

## 使用 try-with-resources

栈回溯通常是由抛出异常引起的。程序执行流的变异通常以这种方式发生。例如，直接与未关闭的本地资源、网络套接字文件句柄相关的资源泄漏，就是这些抛出异常的结果。

在 Java（7 版本之前）中，一个良好的典型 I/O 操作使用强制的 `finally` 块来执行清理工作：

```java
public void readFile( final File file ) {
    InputStream in = null;
    try {
        in = new FileInputStream( file );
        // Some implementation here
    } catch( IOException ex ) {
        // Some implementation here
    } finally {
        if( in != null ) {
            try {
                in.close();
            } catch( final IOException ex ) {
                /* do nothing */
            }
        }
    }
}
```

`finally` 块没有写得很好（但对输入流调用 `close` 方法也可能导致 `IOException` 异常），关闭输入流（并释放其操作系统资源）的操作将被执行。异常永远不应该被忽略，但 `close` 方法抛出的异常是这一规则的唯一例外。

Java 7 在语言中引入了一种名为 `try-with-resources` 的新结构，使得整体资源管理变得更加简单。

以下是使用 `try-with-resources` 重写的上述代码段：

```java
public void readFile( final File file ) {
    try( InputStream in = new FileInputStream( file ) ) {
        // Some implementation here
    } catch( final IOException ex ) {
        // Some implementation here
    }
}
```

资源需要实现 `AutoCloseable` 接口才能在 `try-with-resources` 块中使用。Java 编译器在后台将此结构扩展为更复杂的内容，而对开发者来说，代码看起来非常易读且简洁。在适当的情况下，这是一种非常方便的技术。

## 异常与 lambda

未捕获异常将按预期工作，但 Java lambda 函数的语法不允许指定检查异常；除非这些异常是由 `@FunctionalInterface` 本身定义的（异常可能被抛出）。

下面的代码段将无法通过编译，产生编译错误‘Unhandled exception type IOException’（该异常可能在第 03 行抛出）：

```java
public void readFile() {
    run( () -> {
        Files.readAllBytes( new File( "some.txt" ).toPath() );
    } );
}

public void run( final Runnable runnable ) {
    runnable.run();
}
```

解决方案是在 lambda 体内部捕获 `IOException` 异常并重新抛出正确的 `RuntimeException`（将原始异常作为原因传递）。以下是一个示例：

```java
public void readFile() {
    run( () -> {
        try {
            Files.readAllBytes( new File( "some.txt" ).toPath() );
        } catch( IOException ex ) {
            throw new RuntimeException( "Error reading file", ex );
        }
    } );
}
```

许多函数式接口已经声明，并能够从其实现中抛出任何 `Exception`，但如果没有（如 `Runnable`），则包装或在未捕获异常内部捕获检查异常是做法。

## 标准异常

Java 标准库提供了关于异常类的丰富信息。这些类专门设计用于涵盖处理过程中发生的大多数通用错误。下表列出了经常使用的异常类，在定义自己的异常之前，务必考虑这些。

| 异常类 | 目的 |
| :--- | :--- |
| `NullPointerException` | 尝试在需要对象的地方使用 null。 |
| `IllegalArgumentException` | 方法传递了非法或不适当的参数。 |
| `IllegalStateException` | 在非法或不恰当的时间调用了方法。 |
| `IndexOutOfBoundsException` | 索引（针对向量、字符串或数组）超出范围。 |
| `UnsupportedOperationException` | 请求的操作不支持。 |
| `ArrayIndexOutOfBoundsException` | 使用非法索引访问数组。 |
| `ClassCastException` | 代码尝试将对象转换为其并非其实例的子类。 |
| `EnumConstantException` | 尝试通过名称访问枚举常量，但类型中不包含该名称的常量。 |
| `NumberFormatException` | 尝试将字符串转换为数值类型之一，但字符串不具有相应的格式。 |
| `StringOutOfBoundsException` | 索引为负数或大于字符串的大小。 |
| `IOException` | 发生了某种 I/O 异常。该类是失败或中断的 I/O 操作产生的异常通用类。 |

## 定义你自己的异常

在 Java 语言中定义异常类非常容易。精心设计的异常层次结构可以管理详细的错误条件，并允许详细的实现。实现正确的平衡至关重要；特别是存在许多异常类时，它们可能会复杂开发，并增加捕获异常或向下栈传递异常所需的代码量。

所有用户定义的异常必须继承自 `RuntimeException` 类，并成为未捕获异常类的一部分，该规则总有一些例外。以下是用于身份验证的定义异常：

```java
public class NotAuthenticatedException extends RuntimeException {
    private static final long serialVersionUID = 207923538133605509L;

    public NotAuthenticatedException() {
        super();
    }

    public NotAuthenticatedException( final String message ) {
        super( message );
    }

    public NotAuthenticatedException( final String message, final Throwable cause ) {
        super( message, cause );
    }
}
```

此异常的目的是在登录过程中对不存在的或无效的用户凭据发出信号，例如：

```java
public void signin( final String username, final String password ) {
    if( !exists( username, password ) ) {
        throw new NotAuthenticatedException(
            "用户名 / 密码组合不被识别"
        );
    }
}
```

随异常一起传递信息丰富的消息有助于排除生产系统的故障。如果异常是由于另一个异常情况的结果重新抛出的，必须使用原因构造函数参数保留初始异常。这将有助于追踪问题来源。

## 文档异常

下一个主题将讨论如何让异常也成为文档的一部分。

作为实现的一部分，可能抛出受检异常（checked exception）的方法应将其作为方法签名的一部分。这通过 `throws` 声明来实现。`@throws` 标签用于在 Java 文档工具中描述这些异常。

以下是一个示例：

```java
/**
 * 从文件系统读取文件。
 * @throws IOException 如果发生 I/O 错误。
 */
public void readFile() throws IOException {
    // Some implementation here
}
```

未受检异常（unchecked exceptions）不声明为方法签名的一部分。请对它们进行文档记录，以便方法的调用者了解可能抛出的异常（使用相同的 `@throws` 标签）。

以下是一个示例：

```java
/**
 * 某些概念的字符串表示。
 * @param str 要解析的字符串
 * @throws IllegalArgumentException 如果指定的字符串无法被正确解析
 * @throws NullPointerException 如果指定的字符串为 null
 */
public void parse( final String str ) {
    // Some implementation here
}
```

始终对方法可能抛出的异常进行文档记录。这将有助于从编码开始实现适当的异常处理和恢复（回退）逻辑，确保它们在生产系统中不受故障排除问题的影响。

## 异常与日志

日志（[http://en.wikipedia.org/wiki/Logfile](http://en.wikipedia.org/wiki/Logfile)）是任何复杂 Java 应用程序、库或框架不可或缺的一部分。它是应用程序事件的日志，而异常是流程中的关键部分。必须正确记录异常并在以后进行分析，以便发现应用程序的问题并进行故障排除。

## 结论

异常是 Java 语言的一项重要特性。异常是 Java 错误管理的基础。异常使处理和信号错误状态变得异常简单，而且与错误代码、标志和状态不同，异常一旦发生就无法被忽略。

这些建议将帮助你更有效地理解书中描述的 Java 编码标准和指南。这些工具也可以用于大多数语言的编码或编程。像 Python、C++、CSS 和 JavaScript 等语言都使用通用格式、继承规则、异常和标准，以确保信息易于理解、编辑和添加，从而开发程序和应用程序的改进和新版本。

1. **理解标准**。花时间通过每种标准和指南来提高生产力。不要仅仅因为被要求就将每个局部变量单独写在一行。这样做是因为你理解这能提高代码的可读性。

2. **相信它们**。遵循标准应该是始终如一的，因为这是编码的最佳方式。

3. **在编码时遵循它们，而不是作为事后补救**。整洁的代码更容易维护，无论是在开发还是维护期间都是如此。遵循标准将在开发期间提高生产力，并使代码更易维护。如果从一开始就产生整洁的代码，你可以在创建过程中从中受益。

4. **将它们成为你质量保证流程的一部分**。确保源代码遵循工作交付方所采用的标准。标准应作为培训和指导开发人员变得更高效的依据。

Java 是一门动态且实用的编码语言，希望这本书能帮助你进一步理解 Java 编码的一些高级方面。

感谢阅读。希望你喜欢。我请求你留下诚实的反馈。
