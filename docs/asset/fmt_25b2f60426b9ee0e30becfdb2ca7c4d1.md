
- D. 2022-05-13T14:00:00:00Z[America/Los_Angeles]
- E. 2022-05-13T14:00:00:00Z
- F. 2022-05-13T17:00:00:00Z

### 43. 下述程序的输出是什么？

```java
package transporter;
public class Rematerialize {
    public static void main(String[] input) {
        int init = 11;
        int split = 3;
        int partA = init / split;
        int partB = init % split;
        int result = split * (partB + partA);
        System.out.print(result);
    }
}
```

- A. 9
- B. 11
- C. 12
- D. 15
- E. 代码无法编译。
- F. 以上都不是

### 44. 下列代码的输出是什么？

```java
var math = new Math();
var sum = 0;
sum += math.min(3, 5);
sum += math.floor(8);
sum += math.round(5);
System.out.println(sum);
```

- A. 9
- B. 9.0
- C. 10
- D. 10.0
- E. 11
- F. 11.0
- G. 以上都不是

### 45. 下列代码的输出是什么？

```java
var date = LocalDate.of(2022, Month.JULY, 17);
var time = LocalTime.of(10, 0);
var zone = ZoneId.of("America/New_York");
var iceCreamDay = ZonedDateTime.of(date, time, zone);
time = time.plusMonths(1);
System.out.println(iceCreamDay.getMonthValue());
```

- A. 6
- B. 7
- C. 8
- D. 9
- E. 代码无法编译。

### 46. 下列哪些项可以替换 `isEmpty()` 和 `trim()` 以产生相同的输出？（选择两个）

```java
String curious = "george likes bananas \n";
System.out.println(curious.isEmpty());
System.out.println(curious.trim());
```

- A. empty()
- B. isBlank()
- C. isMissing()
- D. removeBlanks()
- E. shorten()
- F. strip()

### 47. 下列代码的结果是什么？

```java
var sb = new StringBuilder("radical");
sb.insert(sb.length(), "robots");
System.out.println(sb);
```

- A. radicarobots
- B. radicalrobots
- C. radical robots
- D. 代码无法编译。
- E. 代码可以编译但在运行时抛出异常。

### 48. 给定下面的代码，执行后 `dinner` 的值是多少？

```java
int time = 9;
int day = 3;
dinner = ++time>= 10 ? day-- <= 2 ? "Takeout" : "Salad" : "Leftovers";
```

- A. Takeout
- B. Leftovers
- C. Salad
- D. 代码无法编译，但加上括号就可以编译。
- E. 以上都不是。

### 49. `waffleDay` 的结果是什么？

```java
1: var waffleDay = LocalDate.of(2022, Month.MARCH, 25);
2: var period = Period.ofYears(1).ofMonths(6).ofDays(3);
3: var later = waffleDay.plus(period);
4: later.plusDays(1);
5: var thisOne = LocalDate.of(2022, Month.SEPTEMBER, 28);
6: var thatOne = LocalDate.of(2022, Month.SEPTEMBER, 29);
7: System.out.println(later.isBefore(thisOne) + " " + later.isBefore(thatOne));
```

- A. false false
- B. false true
- C. true true
- D. true false
- E. 代码无法编译。

### 50. 可以移除多少对括号并让代码打印 6？

```java
System.out.println((((1+1))*((1+2))));
```

- A. 无
- B. 一对
- C. 两对
- D. 三对
- E. 四对
- F. 五对
- G. 以上都不是

### 51. 下列代码的输出是什么？

```java
var teams = new String("694");
teams.concat(" 155");
teams.concat(" 265");
teams.concat(" 269");
System.out.println(teams);
```

- A. 694
- B. 694 155 265 269
- C. 代码可以编译但输出 else。
- D. 代码无法编译。

### 52. 下列哪项不是包装类？

- A. Boolean
- B. Char
- C. Double
- D. Integer
- E. Long
- F. 以上所有都是包装类。

### 53. 下列代码的输出是什么？

```java
var date = LocalDate.of(2022, Month.JULY, 17);
var time = LocalTime.of(10, 0);
var zone = ZoneId.of("America/New_York");
var iceCreamDay = ZonedDateTime.of(date, time, zone);
date = date.plusMonths(1);
System.out.println(iceCreamDay.getMonthValue());
```

- A. 6
- B. 7
- C. 代码无法编译。
- E. 运行时抛出异常。

### 54. 下列有多少行输出是相同的？

```java
6: var phrase = "prickly \nporcupine";
7: System.out.println(phrase.length());
8: System.out.println(phrase.indent(1).length());
9: System.out.println(phrase.indent(0).length());
10: System.out.println(phrase.indent(-1).length());
```

- A. 无
- B. 一
- C. 两
- D. 三
- E. 四
- F. 代码无法编译。

### 55. 下列有多少行可以编译？

```java
bool b = null;
Bool bl = null;
int i = null;
Integer in = null;
String s = null;
```

- A. 无
- B. 一
- C. 两
- D. 三
- E. 四
- F. 五

### 56. 这段代码打印多少行？

```java
System.out.print(""ape"
"baboon"
"gorilla" """");
```

- A. 三行
- B. 四行
- C. 五行
- D. 代码无法编译。

### 57. 下列哪项可以填充空白使这段代码编译？

```java
public boolean isBirthday(LocalDate dateTime) {
    return now.getMonth() == dateTime.getMonth()
    && now.getDayOfMonth() == dateTime.getDayOfMonth();
}
```

- A. LocalDate now = LocalDate.now()
- B. LocalDate now = new LocalDate()
- C. ZonedDateTime now = ZonedDateTime.now()
- D. ZonedDateTime now = new ZonedDateTime()

### 58. 下列有多少行输出两行？

```java
18: System.out.println("cheetah\ncub")
19: System.out.println("cheetah\ncub")
20: System.out.println("cheetah\ncub".translateEscapes());
21: System.out.println("cheetah\ncub".translateEscapes());
```

- A. 无
- B. 一
- C. 两
- D. 三
- E. 四
- F. 代码无法编译。

### 59. 下述代码片段的输出是什么？

```java
int height = 2, length = 3;
boolean w = height==1 | --length < 4;
var x = height!=2 ? length++ : height;
boolean z = height % length == 0;
System.out.println(w + "-" + x + "-" + z);
```

- A. true-2-true
- B. false-2-false
- C. true-2-false
- D. true-3-false
- E. true-3-false
- F. false-3-false

### 60. 可以移除多少个反斜杠而不改变文本块的值？

```java
12: var quotes = ""
13: \" Quotes that"
14: """
15: """;
```

- A. 无
- B. 一个
- C. 
- D. 三
- E. 四
- F. 代码无法编译。

```java
38: Long.valueOf(88).byteValue();
```

- A. 无
- B. 一个
- C. 二
- D. 三
- E. 四

## 64. 哪一个陈述是正确的？

- A. 如果 `s.contains("abc")` 为 true，那么 `s.equals("abc")` 也为 true。
- B. 如果 `s.contains("abc")` 为 true，那么 `s.startsWith("abc")` 也为 true。
- C. 如果 `s.startsWith("abc")` 为 true，那么 `s.equals("abc")` 也为 true。
- D. 如果 `s.startsWith("abc")` 为 true，那么 `s.contains("abc")` 也为 true。

## 65. 以下代码可能的输出是什么？

```java
var date = LocalDate.of(2022, 5, 13);
var time = LocalTime.of(10, 0);
var trainDay = LocalDateTime.of(date, time);
var instant = trainDay.toInstant();
instant = instant.plus(1, ChronoUnit.DAYS);
System.out.println(instant);
```

- A. 2022-05-14T10:00-07:00[America/Los_Angeles]
- B. 2022-05-14T17:00:00Z
- C. 代码无法编译。
- D. 代码可以编译但在运行时抛出异常。

## 66. 关于这个文本块，哪个陈述是正确的？

```java
var block = """
      green
      yellow
    "\";"
``````
```

- A. 只有必要的空白符。
- B. 只有偶然的空白符。
- C. 同时有必要偶然的空白符。
- D. 代码无法编译。

## 67. 以下代码段的输出是什么？

```java
boolean carrot = true;
Boolean potato = false;
var broccoli = true;
carrot = carrot & potato;
broccoli = broccoli ? carrot : potato;
potato = broccoli ^ carrot;
System.out.println(carrot + "," + potato + "," + broccoli);
```

- A. true, false, true
- B. true, true, true
- C. false, false, false
- D. false, true, false
- E. false, false, true
- F. 代码无法编译。

## 68. 夏令时于 2022 年 11 月 6 日凌晨 2 点结束，此时小时数会重复。假设我们有一个 `ZonedDateTime`，在调用 `toString()` 时显示为 `2012-11-06T01:00-04:00[America/New_York]`。在此值基础上增加一小时后得到的 `ZonedDateTime` 可能的值是什么？

- A. 2022-11-06T01:00-04:00[America/New_York]
- B. 2022-11-06T02:00-04:00[America/New_York]
- C. 2022-11-06T01:00-05:00[America/New_York]
- D. 2022-11-06T02:00-05:00[America/New_York]

## 69. 以下类的类的输出是什么？

```java
1: package rocket;
2: public class Countdown {
3: public static void main(String[] fuel) {
4: var builder = new StringBuilder("54321");
5: builder.substring(2);
6: System.out.println(builder.charAt(1));
```

- A. 1
- B. 2
- C. 3
- D. 4
- E. 5
- F. 不编译

## 70. 以下代码的输出是什么？

```java
var sum = 0.0;
sum = sum + Math.min(3, 5);
sum = sum + Math.floor(8);
sum = sum + Math.round(5.6);
System.out.println(sum);
```

- A. 9
- B. 9.0
- C. 10
- D. 10.0
- E. 11
- F. 11.0
- G. 以上都不是

## 第 2 章 程序流

本次测试涵盖的考点包括：

✓ 程序流

*   包含 `if/else`、`switch` 语句和表达式、循环以及 `break` 和 `continue` 语句的流控制

### 1. 以下哪些语句是正确的？（选择两个）

```java
public class Penguins {
    public static void main(String[] args) {
        var pen = new Penguins();
        pen.length("penguins");
        pen.length(5);
        pen.length(new Object());
    }
    public void length(Object obj) {
        if (obj instanceof String x)
            System.out.println(x.length());
    }
}
```

- A. 代码可以直接编译。
- B. 一行导致编译器错误。
- C. 两行导致编译器错误。
- D. 删除不编译的行后，代码不输出任何内容。
- E. 删除不编译的行后，代码输出一行。
- F. 删除不编译的行后，代码输出两行。

### 2. 以下声明为类型的变量在 `switch` 语句中是不允许的？（选择两个）

- A. var
- B. double
- C. int
- D. String
- E. char
- F. Object

### 3. 什么时候可以省略 `switch` 中的 `default`？（选择两个）

- A. 当枚举的所有值都已覆盖时
- B. 没有返回值时
- C. 当类型为 Boolean
- D. 当类型为 Byte
- E. 当类型为 Boolean 或 Byte

### 4. 运行以下代码会发生什么？
