

# Java 中的左修剪和右修剪替代方法

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-trim-alternatives>

## 1. 概览

`String.trim()`方法删除尾部和前导空白。但它不支持只做L-Trim或R-Trim。

在本教程中，我们将看到实现这一点的几种方法；最后比较它们的性能。

## 2. 使用`while`循环

最简单的解决方案是使用几个`while`循环遍历字符串。

对于L-Trim，我们从左向右读取字符串，直到遇到一个非空白字符：

```java
int i = 0;
while (i < s.length() && Character.isWhitespace(s.charAt(i))) {
    i++;
}
String ltrim = s.substring(i);
```

`ltrim`是从第一个非空白字符开始的子字符串。

或者对于R-Trim，我们从右向左读取字符串，直到遇到非空白字符：

```java
int i = s.length()-1;
while (i >= 0 && Character.isWhitespace(s.charAt(i))) {
    i--;
}
String rtrim = s.substring(0,i+1);
```

`rtrim`是一个子字符串，从开头开始，到第一个非空白字符结束。

## 3. 使用`String.replaceAll()`配合正则表达式

另一个选择是使用`String.replaceAll()`和正则表达式：

```java
String ltrim = src.replaceAll("^\\s+", "");
String rtrim = src.replaceAll("\\s+$", "");
```

`(\\s+)`是匹配一个或多个空白字符的正则表达式。正则表达式开头和结尾的插入符号（`^`）和（`$`）匹配一行的开头和结尾。

## 4. 使用`Pattern.compile()`和`.matcher()`

我们可以重用带有`java.util.regex.Pattern`的正则表达式：

```java
private static Pattern LTRIM = Pattern.compile("^\\s+");
private static Pattern RTRIM = Pattern.compile("\\s+$");

String ltrim = LTRIM.matcher(s).replaceAll("");
String rtim = RTRIM.matcher(s).replaceAll("");
```

## 5. Apache Commons

此外，我们可以利用Apache Commons的`StringUtils#stripStart`和`stripEnd`方法来删除空白。

为此，首先添加`commons-lang3`依赖：

```java
<dependency>
    <groupId>org.apache.commons</groupId>
    <artifactId>commons-lang3</artifactId>
    <version>3.12.0</version>
</dependency>
```

根据文档，我们传入`null`来去除空白：

```java
String ltrim = StringUtils.stripStart(src, null);
String rtrim = StringUtils.stripEnd(src, null);
```

## 6. Guava

最后，利用Guava的`CharMatcher#trimLeadingFrom`和`trimTrailingFrom`方法获得相同的结果。

再次添加合适的Maven依赖，这次是`guava`：

```java
<dependency>
    <groupId>com.google.guava</groupId>
    <artifactId>guava</artifactId>
    <version>31.0.1-jre</version>
</dependency>
```

在Guava中，这与Apache Commons中的做法非常相似，只是方法名更具体：

```java
String ltrim = CharMatcher.whitespace().trimLeadingFrom(s);
String rtrim = CharMatcher.whitespace().trimTrailingFrom(s);
```

## 7. 性能比较

让我们看看这些方法的性能。像往常一样，利用开源框架[Java微基准测试工具](/web/20221007082754/https://www.baeldung.com/java-microbenchmark-harness)（JMH）来比较不同方案在纳秒级的性能。

### 7.1. 基准设置

对于基准的初始配置，我们使用五个分支和以纳秒为单位的平均时间计算时间：

```java
@Fork(5)
@State(Scope.Benchmark)
@BenchmarkMode(Mode.AverageTime)
@OutputTimeUnit(TimeUnit.NANOSECONDS)
```

在`setup`方法中，我们初始化原始消息字段和结果字符串，以便进行后续比较：

```java
@Setup
public void setup() {
    src = "       White spaces left and right          ";
    ltrimResult = "White spaces left and right          ";
    rtrimResult = "       White spaces left and right";
}
```

所有基准测试先删除左边空白，再删除右边空白，最后将结果与预期的字符串进行比较。

### 7.2. `while`循环基准

对于第一个基准测试，使用`while`循环方法：

```java
@Benchmark
public boolean whileCharacters() {
    String ltrim = whileLtrim(src);
    String rtrim = whileRtrim(src);
    return checkStrings(ltrim, rtrim);
}
```

### 7.3. `String.replaceAll()`配合正则表达式基准

接下来测试`String.replaceAll()`：

```java
@Benchmark
public boolean replaceAllRegularExpression() {
    String ltrim = src.replaceAll("^\\s+", "");
    String rtrim = src.replaceAll("\\s+$", "");
    return checkStrings(ltrim, rtrim);
}
```

### 7.4. `Pattern.compile().matches()`基准

之后是`Pattern.compile().matches()`：

```java
@Benchmark
public boolean patternMatchesLTtrimRTrim() {
    String ltrim = patternLtrim(src);
    String rtrim = patternRtrim(src);
    return checkStrings(ltrim, rtrim);
}
```

### 7.5. Apache Commons基准

第四，测试Apache Commons：

```java
@Benchmark
public boolean apacheCommonsStringUtils() {
    String ltrim = StringUtils.stripStart(src, " ");
    String rtrim = StringUtils.stripEnd(src, " ");
    return checkStrings(ltrim, rtrim);
}
```

### 7.6. Guava基准

最后，测试Guava：

```java
@Benchmark
public boolean guavaCharMatcher() {
    String ltrim = CharMatcher.whitespace().trimLeadingFrom(src);
    String rtrim = CharMatcher.whitespace().trimTrailingFrom(src);
    return checkStrings(ltrim, rtrim);
}
```

### 7.7. 结果分析

我们应得到类似以下的结果：

```java
# Run complete. Total time: 00:16:57

Benchmark                               Mode  Cnt     Score    Error  Units
LTrimRTrim.apacheCommonsStringUtils     avgt  100   108,718 ±  4,503  ns/op
LTrimRTrim.guavaCharMatcher             avgt  100   113,601 ±  5,563  ns/op
LTrimRTrim.patternMatchesLTtrimRTrim    avgt  100   850,085 ± 17,578  ns/op
LTrimRTrim.replaceAllRegularExpression  avgt  100  1046,660 ±  7,151  ns/op
LTrimRTrim.whileCharacters              avgt  100   110,379 ±  1,032  ns/op
```

看起来赢家是`while`循环、Apache Commons和Guava！

## 8. 结论

在本教程中，我们研究了多种不同的方法来删除`String`开头和结尾的空白字符。

我们使用了`while`循环、`String.replaceAll()`、`Pattern.matcher().replaceAll()`、Apache Commons和Guava来实现这一目标。

和往常一样，代码可在[GitHub](https://web.archive.org/web/20221007082754/https://github.com/eugenp/tutorials/tree/master/core-java-modules/core-java-string-operations-2)上获取。

