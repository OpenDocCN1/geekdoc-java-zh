
# Java 初学者 50 题练习

## 引言

本书适用于 Java 学习者，特别是初级和中级人员。本书涵盖了以下内容。Java 版本为 8。

在学习基础概念和语法之后，下一步是阅读和理解代码。书中的代码包含了上述类的各种方法。

共有 50 道题。刚开始时题目比较简单，但难度会逐渐增加到最后。

本书的主要目的是提高代码理解能力，而不是详细的语法理论之类的内容。

请注意，为了教学目的，书中包含了一些容易混淆的问题（不建议在实际开发中使用）。

题目从下一页开始。

希望你从中学习并发现新知识。

## 第 1 题

选择描述该程序编译并运行结果的陈述。

```java
public class Question_1 {
    public static void main(String[] args) {
        int a = 1;
        int b = 2;
        int c = 3;

        if (a + b == c) {
            System.out.println(method1()[0]);
        }
    }

    private static String[] method1() {
        String[] array = new String[1];
        StringBuilder sb = new StringBuilder();
        sb.append("Be a ");
        sb.append("Java ");
        sb.append("Programmer");
        array[0] = sb.toString();
        return array;
    }
}
```

- (A) 输出 Be a Java Programmer
- (B) 输出为空
- (C) 编译错误
- (D) 运行时异常

**答案：(A) 输出 "Be a Java Programmer"**

`method1()` 返回 `String` 类型的数组，并将来自 `StringBuilder` 对象的字符串设置到 `array[0]`。

因此，该程序在无任何错误的情况下输出 "Be a Java Programmer"。

### 注意：

1.  **语句中的条件**

    在学习过程中你可能已经见过像 `a == 1` 这样的简单条件，你也可以在条件括号中进行计算，例如题目中第 7 行的 `a + b == c`。

2.  **StringBuilder**

    `StringBuilder` 在 Java 编程中被频繁使用，因为它比仅使用 `String` 对象进行拼接要快。

    在之后的很多情况下，为了将 `StringBuilder` 对象转换为 `String` 对象，程序员会使用 `toString()` 方法。

    初始化 `StringBuilder` 时，你有两种方式。

    首先，初始化一个空的 `StringBuilder` 对象，如题目中第 15 行所示：`StringBuilder sb = new StringBuilder();`；其次，你也可以像这样使用一个字符串来初始化：`StringBuilder sb = new StringBuilder("text")`。

    如果你决定先追加第一个字符串，可以使用这种方法来简化代码。

## 第 2 题

```java
public class Question_2_1 {
    private String a = "str";
    private Long b = 1L;
    private int c = 0;
}
```

选择描述继承上述程序的程序在编译并运行结果的陈述。

```java
public class Question_2_2 extends Question_2_1 {
    public static void main(String[] args) {
        for (int i = 0; i < 5; i++) {
            if (true) {
                if (true) {
                    System.out.println(a);
                    System.out.println(b);
                }
            }
            System.out.println(c);
        }
    }
}
```

- (A) 输出 str10
- (B) 输出 0
- (C) 编译错误
- (D) 运行时异常

**答案：(C) 编译错误**

父类 `Question_2_1` 的字段访问修饰符全是 `private` 且非 `static`。如果它们都是 `public static`，如下面的代码所示，就不会发生编译错误。

```java
public class Question_2_1 {
    public static String a = "str";
    public static Long b = 1L;
    public static int c = 0;
}
```

而且，子类可以使用父类的字段，因为它继承了 `Question_2_2`。

### 注意

1.  **if 语句中的条件**

    `if` 语句中的条件需要布尔类型，所以你可以在里面写 `true` 或 `false`。如果你写 `true`，则内部代码将始终执行；如果写 `false`，则内部代码将永远不会执行。

    这被称为“不可达语句”。

    还有一点，像这道题一样，在实际编码场景中不建议在 `if` 条件中写 `true`，因为如果内部代码始终会执行，你就不需要使用 `if` 语句了。

2.  **System.out.println()**

    你可能已经见过用它输出 `String`，但你也可以用它输出其他类型，如 `Long`、`int` 等。

## 第 3 题

选择描述该程序编译并运行结果的陈述。

```java
public class Question_3 {
    public static void main(String[] args) {
        LocalDateTime ldt1 = LocalDateTime.now();
        LocalDateTime ldt2 = ldt1.plusDays(0);
        if (!ldt2.isAfter(ldt1)) {
            System.out.println("ldt1 and ldt2");
        } else if (ldt2.isBefore(ldt1)) {
            System.out.println("ldt1 and not same");
        }
    }

    private static boolean isTime(LocalDateTime ldt) {
        boolean flg = true;
        return flg;
    }
}
```

- (A) 输出 ldt1 and ldt2
- (B) 输出 ldt1 and not same
- (C) 输出为空
- (D) 运行时异常

**答案：(A) 输出 "ldt1 and ldt2"**

在这段代码中，`flg` 为 `true` 是因为 `ldt1` 是一个对象。

### 注意

1.  **LocalDateTime**

    这是从 Java 8 开始的。你可以使用格式 `yyyy-MM-dd`。

2.  **return**

    有两种方法使用它。

3.  **instanceof**

    此运算符检查参数是否为某个类。在第 21 行。

## 第 4 题

选择作为 "// code" 的代码输出 "JAVA" 的陈述。

```java
public class Question_4 {
    public static void main(String[] args) {
        LinkedHashMap<String, String> map = new LinkedHashMap<>();

        map.put("1", "J");
        map.put("2", "A");
        map.put("3", "V");
        map.put("4", "A");

        if (true) {
            map.entrySet().stream().forEach(e -> {
                System.out.print(e.getKey());
            });
        } else {
            map.entrySet().stream().forEach(e -> {
                System.out.print(e.getValue());
            });
        }
    }
}
```

- (A) boolean flg = true;
- (B) boolean flg = false;
- (C) Boolean flg = null;
- (D) Object flg = null;

**答案：(B) boolean flg = false;**

在这段代码中，创建 `map` 对象并存入键值。目标是按添加顺序输出 `map` 对象中的值。

在第 15 行的 `if` 条件中，如果 `flg` 为 `true`，程序将输出所有键；如果是 `false`，则输出所有值。所以答案是 (B)。

### 注意

1.  **LinkedHashMap**

    当你开始学习 Java 时，大多数情况下先学 `HashMap`。在这种情况下，我们需要按添加顺序输出所有值。`HashMap` 不保证顺序，所以这就是为什么这段代码使用 `LinkedHashMap`。

2.  **关于 (C) 和 (D)**

    关于 (C)：如果你在代码中写 `Boolean flg = null;`，不会发生编译错误，但如果你在代码中写 `boolean flg = null;`，就会发生。

    这是基本类型和对象之间的区别。基本类型是值本身。对象提供引用，`null` 表示没有引用。因此对象是可以为空的。

    关于 (D)：`Object` 类封装了所有类，所以如果你在代码中写它就不会发生编译错误。

3.  **forEach**

    这是 Java 8 添加的 StreamAPI 中的一个方法。它对流中的所有元素执行操作。

    对于初学者来说，最好将其视为编写集合 `for` 循环的替代方法。严格来说，它们并不相同，但起初足够了。

## 问题 5

```java
public class Question_5_1 {
    public Integer number;
    public Integer getNumber() { return number; }
    public void setNumber(Integer number) { this.number = number; }
}
```

选择一个描述使用上述程序的编译和运行后的结果的语句。

```java
public class Question_5_2 {
    public static void main(String[] args) {
        Question_5_1 instance1 = new Question_5_1();
        Question_5_1 instance2 = new Question_5_1();
        instance1.setNumber(0);
        instance2.setNumber(0);

        if (instance1.getNumber() == instance2.getNumber()) {
            System.out.print("true");
            if (instance1.equals(instance2)) {
                System.out.print(" " + "true");
            } else {
                System.out.print(" " + "false");
            }
        }
    }
}
```

- (A) 输出 true true
- (B) 输出 true false
- (C) 输出无
- (D) 编译错误或运行时异常

**答案：(B) 输出 true false**

在此代码的第 8 行，正在比较两个 `Question_5_1` 实例的字段的设置值。

它返回 `true`，所以程序无论如何都会输出，这就是为什么选项 (C) 是错误的。第 10 行的条件返回 `false`，因此选项 (B) 是正确的。

### 注意事项

1.  **不在花括号内另起行**

    在花括号内另起行在 Java 编程中非常常见。

    当然，如果存在多个语句，这样做可以提高代码的可读性，但如果花括号内只有一个语句，不另起行是编写代码的好方法。

    **比较**

    ```java
    <不另起行>
    { // 此处有某些代码; }

    <另起行>
    {
      // 此处有某些代码;
    }
    ```

2.  **Object 类的 equals 方法**

    在第 10 行，正在比较两个实例是否为同一个“实例”。

    正如你在第 5 行和第 6 行所示，字段的值相同，但它们是不同的实例。这就是为什么条件返回 `false` 的原因。

## 问题 6

选择一个描述此程序编译和运行后的结果的语句。

```java
public class Question_6 {
    public static void main(String[] args) {
        while (!false) {
            System.out.print("A");
            Integer.parseInt("Hello World");
        } catch (Exception e) {
            System.out.print("B");
            break;
        } finally {
            System.out.print("C");
        }

        System.out.print("D");
    }
}
```

- (A) 输出 AD
- (B) 输出 ABD
- (C) 输出 ABCD
- (D) 输出 ABDC

**答案：(C) 输出 ABCD**

在第 5 行，`!false` 等于 `true`，所以循环开始。

在第 8 行发生了一个异常，因为参数不是数字，所以 `catch` 和 `finally` 块中的语句将被执行。

### 注意事项：

1.  **Integer.parseInt()**

    这是 `Integer` 类的一个静态方法。它将 `String` 参数转换为 `int` 值，在 Java 编程中非常常见。

    当参数不是数字（作为值，而不是作为类型）时，会发生 `NumberFormatException`。这是与 `NullPointerException` 一样著名的异常之一。

2.  **break 语句和 finally 块的处理顺序**

    正如你在第 11 行所示，程序将因此退出 `while` 循环。

    `finally` 块将优先执行，然后退出 `while` 循环。

3.  **catch 块**

    在此代码中，你只看到一个 `catch` 块，但你可以通过编写多个 `catch` 块来处理每个异常。

    如果你希望根据每个异常得到不同的结果，你应该这样写代码：

    ```java
    } catch (NullPointerException e) {
      // 此处有某些代码;
    } catch (NumberFormatException e) {
      // 此处有某些代码;
    }
    ```

## 问题 7

选择一个描述此程序编译和运行后的结果的语句。

```java
public class Question_7 {
    public static void main(String[] args) {
        String str1 = "Hello";
        String space = " ";
        Question_7 question_7 = new Question_7();
        question_7.method1(str1 + space);
    }

    private void method1(String str1) {
        String str2 = "World";
        str1 += str2;
    }
}
```

- (A) 输出 Hello
- (B) 输出 Hello World
- (C) 编译错误
- (D) 运行时异常

**答案：(A) 输出 Hello**

在第 9 行，向 `method1` 传递参数 "Hello "。

在 `method1` 中，`str1` 从 "Hello " 变为 "Hello World"，但这段代码输出 "Hello"。

让我们从下面详细查看。

### 注意事项：

1.  **值传递**

    在第 9 行传递给 `method1` 的参数是值，因此 `main` 方法中的变量 `str1` 与 `method1` 中的 `str1` 不同。它只是一个副本。

    `method1` 中的变量 `str1` 发生了变化，正如你在第 17 行所示，但这段代码输出 "Hello"。

## 问题 8

选择一个描述此程序编译和运行后的结果的语句。



## 问题 8

```java
public class Question_8 {
    public static void main(String[] args) {
        List<String> list1 = new ArrayList<>();
        list1.add("This ");
        list1.add("list ");
        list1.add("is ");
        System.out.println(list1.size());
    }
}
```

- (A) 输出 7
- (B) 输出 14
- (C) 输出 16
- (D) 输出 18

答案：(C) 16

在第 5 行，`list1` 被初始化。

## 问题 9

选择一个描述此程序编译和运行后的结果的语句。

```java
public class Question_9 {
    public static void main(String[] args) {
        HashMap<Integer, Integer> map = new HashMap<>();
        map.put(1, 2);
        map.put(3, 4);
        map.clear();
        if (map.isEmpty()) {
            map.put(1, 1);
            map.put(1, 2);
        }
        System.out.println(map.get(1) > map.size());
    }
}
```

- (A) 输出 true
- (B) 输出 false
- (C) 编译错误
- (D) 运行时异常

答案：(A) 输出 true

在第 17 行，`map.get(1)` 返回 2，`map.size()` 返回 1，所以程序输出 true。

## 问题 10

选择一个描述该程序编译并运行结果的语句。

```java
public class Question_10 {
    public static void main(String[] args) {
        Integer a = method1("1");
        if (a == 0 && a != null) {
            System.out.println(a);
        }
    }
    private static Integer method1(String str) {
        if (Integer.parseInt(str) > 0) {
            return null;
        } else {
            return 100;
        }
    }
}
```

- (A) 输出 null
- (B) 输出 100
- (C) 编译错误
- (D) 运行时异常

答案：(D) 运行时异常

在第 12 行，`method1` 返回 `null`，因为参数大于 0。

之后，在第 6 行发生了运行时异常，因此答案是 (D)。

### 备注

- (1) `NullPointerException`（空指针异常）

  此异常是 Java 编程中最为著名的异常之一。在大多数情况下，Java 程序员至少会遇到这种异常一次。

  ```java
  if (a == 0 && a != null)
  ```

  在这段代码的第 6 行，使用运算符 `==` 比较 `null` 和 0，这就是发生异常的原因。

  为了同时评估 `a == 0` 和 `a != null` 两个条件，请调换它们的顺序。这样做，你可以先进行空检查，如果是 `null`，则返回 `false` 且不会发生运行时异常。

  ```java
  if (a != null && a == 0)
  ```

  这种异常经常出现。例如，有人急于发布应用程序，在没有进行空检查的情况下编写了代码。应用程序发布后，由于代码缺少空检查，程序因 `NullPointerException` 而停止。如果有足够的时间进行测试，这种情况就不会发生，但有时没有时间。所以，这不是一个奇怪的情况，而是正常发生的。

## 问题 11

选择一个描述该程序编译并运行结果的语句。

```java
public class Question_11 {
    public static void main(String[] args) {
        String fileName = "file1.csv";
        String fileNameNoExtension =
            fileName.substring(0, fileName.indexOf("."));

        if (method1(fileName)) {
            System.out.println(fileNameNoExtension +
                " is csv file");
        } else {
            System.out.println(fileNameNoExtension +
                " isn't csv file");
        }
    }

    public static boolean method1(String value) {
        return value.endsWith(".csv");
    }
}
```

- (A) 输出 file1.csv is csv file
- (B) 输出 file1.csv isn't csv file
- (C) 输出 file1 is csv file
- (D) 输出 file1 isn't csv file

答案：(C) 输出 file1 is csv file

该程序的作用是检查 `file1` 是否为 csv 文件，并输出不带扩展名的文件名结果。你可以从中学习 `String` 类的几种方法。

### 备注

- (1) `String`

  - `indexOf()`：此方法返回参数在 `String` 中出现的索引。它的计数方式与数组元素相同，`file1.csv` 包含 8 个字符，而 `.` 出现的索引是 5。

  - `substring()`：此方法返回按指定范围截取的字符串。以下是理解方式：

    | f | i | l | e | 1 | . | c | s | v |
    |---|---|---|---|---|---|---|---|---|
    | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 |

    如果你获取上述范围 0 到 5 的截取字符串，就可以像本题第 5 行代码中那样获得不带扩展名的 `fileName`。

  - `endsWith()`：与上述两种相比，这个方法很容易理解。通过阅读方法名就可以猜测它是检查字符串是否以参数结尾。如果是，它返回 `true`；否则返回 `false`。

## 问题 12

选择一个描述该程序编译并运行结果的语句。

```java
public class Question_12 {
    public static void main(String[] args) {
        String str = "123";
        if (method1(str)) {
            Object a = Integer.parseInt(str);
            System.out.println((String) a);
        }
    }

    public static boolean method1(String value) {
        try {
            Integer.parseInt(value);
            return true;
        } catch (NumberFormatException e) {
            return false;
        }
    }
}
```

- (A) 输出 123
- (B) 输出无
- (C) 编译错误
- (D) 运行时异常

答案：(D) 运行时异常

在第 7 行，`if` 条件返回 `true`，因为 `value` 是数字。然而，在第 9 行发生了运行时异常，因为 `a` 是 `Integer` 类型。

### 备注

- (1) `ClassCastException`（类型转换异常）

  当将对象转换为没有继承关系的类型时发生此异常。第 8 行的 `String` 和 `Integer` 是这种异常的很好的例子。

  <at line 8>

  在第 8 行，当初始化 `a` 时，编译器直到程序运行才知道 `a` 的类型。以下是该代码中第 8 行的两种写法：

  - 1. `Object a = Integer.parseInt(str);`
  - 2. `Integer a = Integer.parseInt(str);`

  如果你用方式 2 重写第 8 行，则在第 9 行发生编译错误，因为初始化 `a` 告诉了编译器 `a` 的类型。

- (2) `method1`

  在第 14 行，`method1` 是名字。然而，在实际编码情况下，这种类型的名称通常以 `is` 开头。例如 `isString`、`isNumber`、`isFile`。你应该像上面那样命名方法，如果检查某些内容并返回 `boolean` 值。

## 问题 13

选择一个描述该程序编译并运行结果的语句。

```java
public class Question_13 {
    public static void main(String[] args) {
        String[] array = { "a", "b", "c" };
        for (int i = 0; i < array.length; i++) {
            if (isEmpty(array)) {
                return;
            }
            System.out.println(array[i].toUpperCase());
        }
    }
    public static boolean isNotEmpty(String[] array) {
        return array.length == 0;
    }
}
```

- (A) 输出 C
- (B) 输出 null
- (C) 编译错误
- (D) 运行时异常

答案：(D) 运行时异常

这段代码似乎输出了最后一个元素，但在输出转换为大写的最后一个元素时使用 `array.length` 是错误的。

### 备注

- (1) `toUpperCase`

  此方法在第 10 行。它非常简单易于理解。它将小写转换为大写。

- (2) `array`

  - <operate all elements>

    在第 6 到 11 行，这个循环经常用于操作所有元素，所以 `array` 如下所示变为大写。

    ```
    before : { "a", "b", "c" }
    after : { "A", "B", "C" }
    ```

  - <get the last element>

    代码中，因为有三个元素，`array.length` 返回 3。然而，获取最后一个元素需要写 `array[2]`。在第 13 行，`array[3]` 等于 3，所以发生了运行时异常。

- (3) `ArrayIndexOutOfBoundsException`（数组越界异常）

  这是程序运行时发生的异常。最好记住这个异常，因为在编码情况下经常会看到。

## 问题 14

选择一个描述该程序编译并运行结果的语句。

```java
public class Question_14 {
    public static void main(String[] args) {
        Random random = new Random();
        int a = 0;
        for (int i = 0; i < 10000; i++) {
            a = random.nextInt(10);
            if (a > 9) {
                System.out.println("abc");
                return;
            }
        }
        System.out.println("ABC");
    }
}
```

- (A) 输出 abc
- (B) 输出 ABC
- (C) 编译错误
- (D) 运行时异常

答案：(B) 输出 ABC

在第 7 到 16 行，`a` 大于 9 的可能性不存在（10000 次）。然而，`a` 不可能大于 9，因为第 9 行的 `nextInt()` 方法返回 0 到 9 之间的随机数。结果，该程序输出 ABC。

### 备注

- (1) `Random`

  - `nextInt()`：如上所述，此方法返回 0 到参数之间的随机数。

  <Rock, Paper, Scissors Game>

  下面是使用此方法的另一个示例，该程序是简单的剪刀石头布游戏。

  ```java
  public static void main(String[] args) {
      String[] array = {
          "Rock",
          "Paper",
          "Scissors"
      };
      System.out.println(array[new Random().nextInt(3)]);
  }
  ```

  创建一个包含 Rock, Paper, Scissors 字符串的数组。输出数组成员时，通过 `nextInt()` 方法提供随机数作为数组索引。因此，该程序在编译并运行时会随机输出 Rock、Paper 或 Scissors。

## 问题 15

在目录 `C:/Users/user/Desktop/` 中有三个文本文件。

<directory (C:/Users/user/Desktop/)>

- 1 file1.txt
- 2 file2.txt
- 3 file3.txt

请选择一个描述该程序在编译并运行结果的陈述。

```java
public class Question_15 {

    public static void main(String[] args) {

        File dir = new File("C:/Users/user/Desktop/");

        Arrays.stream(dir.listFiles()).forEach(file -> {
            System.out.print(file.getName() + " ");
        });

    }

}
```

- (A) 输出 file1.txt file2.txt file3.txt
- (B) 输出 null
- (C) 编译错误
- (D) 运行时异常

答案：(A) 输出 file1.txt file2.txt file3.txt

该程序的功能如下：

- 1. 获取目录 `C:/Users/user/Desktop/` 中的所有文件
- 2. 输出所有文件的名称

### 备注

- (1) `File`

  - <create file object>

    `File` 类是操作文件对象的良好选择。如第 5 行所示，如果你想通过向 `File` 类的构造函数传递文件路径来创建目录对象，也可以使用 `File` 类。

  - `listFiles()`：这个方法非常常见。在第 7 行，它将目录中的所有文件以 `File` 类型数组的形式返回。

  - `getName()`：在第 8 行，你可以看到这个方法。它只返回文件名。如果你输出 `file` 而不是 `file.getName()`，它将输出带有完整路径每个文件对象。

- (2) `Arrays`

  在第 7 行，`forEach()` 方法与问题 4 中的方法相同。它属于 StreamAPI，但 `File` 类型的数组没有 `stream()` 方法，因此该程序第 7 行到第 9 行的操作如下：

  - 1. 创建 `File` 类型数组的流
  - 2. 使用流的 `forEach()` 方法
  - 3. 输出每个元素

  箭头 (`->`) 之前的参数 `file` 是流中的单个元素。

## 问题 16

请选择一个描述该程序在编译并运行结果的陈述。



```java
public class Question_16 {
    public static void main(String[] args) {
        String str1 = "a";
        String str2 = "b";
        String str3 = "c";
        List<String> list = Arrays.asList("a", "b", "c");
        list.stream().forEach(e -> {
            switch (e) {
                case str1:
                    System.out.println("switch");
                    break;
                case str2:
                    break;
                case str3:
                    break;
            }
        });
    }
}
```

- (A) 输出 switch
- (B) 无输出
- (C) 编译错误
- (D) 运行时异常

答案：(C) 编译错误

在第 4 行到第 6 行，都是变量。

然而，`switch` 语句中的 `case` 子句需要 `final` 变量，因此在第 12 行、15 行、17 行发生编译错误。

备注：

### (1) `switch` 语句

与 `if` 语句相比，如果有很多条件，`switch` 语句是更好的选择。

## <使用 `if-else` 语句的三个条件>

```java
1 if (condition1) {
2   return;
3 } else if (condition2) {
4   return;
5 } else {
6   return;
7 }
```

## <使用 `switch` 语句的三个条件>

```java
1 switch ("*) {
2 case condition1 : break;
3 case condition2 : break;
4 default : break;
5 }
```

上述代码第 4 行的 `default` 与 `if` `switch` 语句中的 `else` 相同。

另一个选择 `if` 语句或 `switch` 语句的点取决于条件是简单还是复杂。

`switch` 语句需要 `final` 变量并且看起来简单，但 `if` 语句可以比 `switch` 语句更容易地评估复杂的条件。

## 问题 17

以下是文件 (`C:/Users/user/Desktop/abc.properties`) 的内容。

```properties
1 key=value
2
```

请选择一个描述该程序在编译并运行结果的陈述。

```java
1 public class Question_17 {
2     public static void main(String[] args) throws Exception {
3      Properties property = new Properties();
4      File file = new File("C:/Users/user/Desktop/abc.properties");
5      InputStream stream = new FileInputStream(file);
6      String str = "key";
7
8      property.load(stream);
9      property.clear();
10      property.setProperty(str, "java");
11
12      System.out.println(property.getProperty(str));
13
14      stream.close();
15     }
16 }
```

- (A) 输出 value
- (B) 输出 java
- (C) 输出 null
- (D) 编译错误或运行时异常

答案：(B) 输出 java

### (1) 该程序的功能如下

1. 从 properties 文件创建 `FileInputStream`。
2. 加载并使其为空。
3. 设置键值并输出。
4. 关闭流（避免内存泄漏）。

备注：

### (1) properties 文件

这种文件以 `.properties` 扩展名结尾。

这只是简单的键值对内容，用于存储 Java 程序的配置。

### (2) `Properties`

此类用于操作上述的 properties 文件。

#### `<method load()>`

在第 8 行，此方法用于加载 properties 文件。你只需要通过向此方法传递 `FileInputStream` 来加载它即可。

#### `<method clear()>`

在加载 properties 文件后，对象 `property` 在这种情况下有一个 "key" 和 "value" 条目。如果你使用此方法，对象 `property` 将没有条目集。它将是空的。

#### `<method setProperty() and getProperty()>`

这两个方法都非常易于理解。你可以设置键值内容，或者通过键获取它。如果 `property` 对象中没有条目，`getProperty()` 方法将返回 `null`。

## 问题 18

请选择一个描述 "//condition here" 的陈述，使下面代码的 `shuffleText()` 方法永远不返回相同的值。

```java
public class static Question_18 {
    public static void main(String[] args) {
        System.out.println(shuffleText("java"));
    }

    public static String shuffleText(String text) {
        while (true) {
            List<String> list = new ArrayList<>();
            StringBuilder sb = new StringBuilder();

            for (char character : text.toCharArray()) {
                list.add(String.valueOf(character));
            }

            Collections.shuffle(list);
            list.forEach(e -> sb.append(e));

            if (condition here) {
                return sb.toString();
            }
        }
    }
}
```

- (A) `sb.toString().equals(text)`
- (B) `!sb.toString().equals(text)`
- (C) `true`
- (D) `false`

答案：(B) `!sb.toString().equals(text)`

该程序的 `shuffleText` 方法的功能如下：

1. 循环直到返回与参数不同的文本
2. 创建列表并添加参数的每个字符
3. 将列表转换为 `StringBuilder`
4. 从 `StringBuilder` 返回字符串

备注：

### (1) `toCharArray()`

这个方法在第 11 行到第 13 行操作 `String` 的每个字符时非常常见。

在第 12 行使用 `String.valueOf()` 记得转换为字符串。

### (2) `Collections.shuffle()`

这个方法非常有用。如果你想打乱列表的元素，只需编写此并传递列表作为参数即可。

### (3) 本题答案

条件 (B) `!sb.toString().equals(text)` 检查打乱后的字符串是否与参数不同。

如果是，则返回（因为此代码本不应该返回相同的值）。

然而，使用第 18 行的条件 (A) `sb.toString().equals(text)` 此代码将只返回相同的值。

在此代码中，它始终返回 "java"。

## 问题 19

`Character.isLetter()` 方法在参数是字母时返回 `true`。

请选择一个描述 "// code here" 的陈述，使下面代码的 `isAlphabet()` 方法在方法参数是字母时返回 `true`。

```java
public class Question_19 {
    public static void main(String[] args) {
        List<String> list = Arrays.asList("abc", "def", "123");
        for (String str : list) {
            if (!isAlphabet(str)) {
                System.out.println(str);
            }
        }
    }
    public static boolean isAlphabet(String text) {
        int cnt = 0;
        for (char character : text.toCharArray()) {
            if (!Character.isLetter(character)) {
                cnt++;
            }
        }
        return // code here;
    }
}
```

- (A) `cnt < 1`
- (B) `cnt > 1`
- (C) `cnt < 2`
- (D) `cnt > 2`

答案：(A) `cnt < 1`

此程序的 `isAlphabet()` 方法的作用如下：

1. 从参数创建 `charArray`
2. 对其中的所有字符进行操作
3. 如果不是字母，则 `cnt` 加1
4. 如果 `cnt` 小于1（从未增加），则返回

## 注意：

### (1) 在编码场景中何时使用这段代码

#### `<method isAlphabet()>`

`isAlphabet()` 方法根据检查参数的结果返回布尔值。

这种类型的方法用于验证。

例如，来自用户输入的参数发送的消息、目录内的文件名、数据库中的某列等。

### <第 5 行到 8 行>

在实际编码场景中，这段代码可以用于输出或存储所有非字母字符串作为错误消息。

如果第 4 行列表的元素是文件名，用户就可以知道特定应用程序的所有错误文件名。

然而，如果验证在仅发现一个元素不是字母后就立即返回错误消息，用户将无法得知所有的元素。

因此，这种编码风格在输出错误消息时非常有用。

## 问题 20

下面是 zip 文件内部 (`C:/Users/user/Desktop/file.zip`)。

- 1 file1.txt
- 2 file2.txt
- 3 file3.txt

选择一个描述该程序编译并运行结果的语句。

```java
public class Question_20 {
    public static void main(String[] args) throws Exception {
        File file = new File("C:/Users/user/Desktop/file.zip ");
        ZipInputStream stream = new ZipInputStream(new FileInputStream(file));
        ZipEntry entry = stream.getNextEntry();
        while (entry != null) {
            System.out.print(entry.getName());
            entry = stream.getNextEntry();
        }
        stream.close();
    }
}
```

- (A) 输出 file1.txtfile2.txtfile3.txt
- (B) 输出为空
- (C) 编译错误
- (D) 运行时异常

答案：(A) 输出 file1.txtfile2.txtfile3.txt

此程序的作用如下：

1. 从 zip 文件创建 `ZipInputStream`
2. 循环判断如果元素不为空则输出文件名

注意：

### (1) zip 文件处理

该代码循环只检查标准 Java 库，不包含任何外部库，是 Java 中处理 zip 文件的基础代码。

下面是详细的处理顺序：

1. 创建 `ZipInputStream` 后，创建 `ZipEntry` 对象。该对象是 zip 文件中的一个元素（文件）。
2. 在 `while` 循环中，检查 `ZipEntry` 对象是否为空，输出 `fileName`，并在每次循环关闭 `ZipEntry` 对象。并在循环最后像增加数字一样将下一个 `ZipEntry` 对象赋值给变量 `entry`。
3. 像第 11 行和第 15 行一样关闭 `ZipEntry` 对象和 `ZipInputStream`。

### (2) 嵌套流

你可能发现了为什么这段代码没有关闭第 5 行的 `FileInputStream`。很好的观点。

在 Java 中，如果流是嵌套的，你不需要关闭每个流。你只需要关闭包装流。

在这段代码中，它是 `ZipInputStream`。当你关闭它时，嵌套的流 `FileInputStream` 也会关闭。

## 问题 21

选择一个描述该程序编译并运行结果的语句。

```java
public class Question_21 {
    public static void main(String[] args) {
        String str1 = "A B C, ABC ";
        String[] array = str1.split(",");

        for (String str : array) {
            method1(str.toLowerCase().trim());
        }

        for (String str : array) {
            method1(str);
        }
    }

    private static void method1(String value) {
        System.out.print(value);
    }
}
```

- (A) 输出 a b cabcA B C ABC
- (B) 输出 a b cabca b c abc
- (C) 输出 abcabcABCABC
- (D) 输出 abcabcabcabc

答案：(A) 输出 a b cabcA B C ABC

1. 创建元素为 "A B C" 的数组
2. 通过两种方式输出它们中的每一个：转换为小写并移除末尾空格，以及原样输出。

注意

### (1) `toLowerCase()`

此方法简单地将 `String` 中的大写字母转换为小写字母。

### (2) `trim()`

此方法移除开头和结尾的空格，因此空格会保留。

这就是为什么选项 (C) 和 (D) 是错误的原因。

### (3) 方法链

在第 9 行，`toLowerCase()` 和 `trim()` 上有多个方法调用。这被称为“方法链”。

### (4) 为什么选项 (B) 是错误的

`String` 是不可变的。

在第 9 行，看起来改变了 `str` 的值，但实际上是错误的。

`str` 的值永远不会改变，所以如果你想保留它，就需要将其赋值给另一个变量。

如果 `String` 是可变的，答案就是 (B)。

## 问题 22

选择一个描述该程序编译并运行结果的语句。

```java
public class Question_22 {
    public static void main(String[] args) {
        String str1 = null;
        String str2 = str1 == null ? "" : "";

        try {
            System.out.print(str2.trim());
        } catch (Exception e) {
            System.out.print(str2 == null ? 0 : 1);
        }

        finally {
            System.out.print(str2 == null ? 0 : 1);
        }
    }
}
```

- (A) 输出 0
- (B) 输出 1
- (C) 输出 0
- (D) 输出 1

答案：(C) 输出 0

此题的重点是 `finally` 块会被执行。

## 注意：

### (1) 停止应用程序的方法

#### `<return>`

如果代码中有 `return` 语句，你可以停止方法。但这意味着返回到调用者，所以应用程序会继续运行。

如果你将第 13 行的代码从 `System.exit(1)` 重写为 `return`，答案是 (A)。

#### `<System.exit()>`

相反，此方法会停止应用程序。

这就是为什么 `finally` 块中的语句没有执行，所以答案是 (C)。

此外，此方法的参数通常是 0 和 1，0 表示程序结束。

### (2) 三元运算符

在第 6 行和 16 行存在三元运算符。下面是这样思考这段代码：

1. 在条件之前，返回一个布尔值



- 2. 在其之后，返回 `0 : 1`
- 3. 如果条件为真返回 `0`；如果条件为假返回 `1`。

这很有用，例如：

## 问题 23

选择一个描述该程序编译并运行结果的语句。

```java
public class Question_23 {
    public static void main(String[] args) {
        List<String> list1 = Arrays.asList("a", "b");
        List<String> list2 = Arrays.asList("c", "d");
        List<String> list3 = Arrays.asList("e", "f");
        List<List<String>> lists = Arrays.asList(list1, list2, list3);

        List<String> concatenatedList = concatList(lists);
        concatenatedList.forEach(e -> System.out.print(e));
    }

    public static List<String> concatList(List<List<String>> lists) {
        List<String> list = new ArrayList<>();

        for (List<String> e : lists) {
            for (String str : e) {
                list.add(str);
            }
        }
        return list;
    }
}
```

- (A) 输出 abcdef
- (B) 输出 fedcba
- (C) 输出为空
- (D) 编译错误或运行时异常

答案：(A) 输出 abcdef

此题的重点是合并多个列表。

与其他问题相比，你可能认为这很困难，所以让我们看看这段代码是如何工作的。

### (2) 使用 Stream API

下面是写在第 15 行到 19 行的替代代码。

```java
lists.forEach(x -> {
    x.forEach(y -> {
        list.add(y);
    });
});
```

## 问题 24

选择一个描述该程序编译并运行结果的语句。

```java
public class Question_24 {
    public static void main(String[] args) {
        List<Integer> list1 = Arrays.asList(1, 2, 3, 4, 5, 6);
        List<Integer> list2 = list1.stream()
            .filter(e -> e % 2 == 0)
            .collect(Collectors.toList());
        System.out.println(add(list2));
    }

    public static int add(List<Integer> list) {
        int number = 0;
        for (int e : list) {
            number += e;
        }
        return number;
    }
}
```

- (A) 输出 10
- (B) 输出 20
- (C) 输出 12
- (D) 输出 24

答案：(C) 输出 12

此第一个列表代码的作用如下：

- 1. 创建包含元素 1, 2, 3, 4, 5, 6 的第一个列表
- 2. 创建包含第一个列表中偶数元素的第二个列表
- 3. 将它们的所有元素相加并输出计算结果

备注：

(1) Stream API

<method filter()>

此方法返回布尔值。你可以编写条件来过滤流中的元素，如此代码第 7 行所示。

以下是第 7 行的替代代码。你也可以这样写：

```java
.filter(e -> {
    return e % 2 == 0;
})
```

以下是获取奇偶数的简单代码。你可以直接使用它们。

奇数：`number % 2 != 0`
偶数：`number % 2 == 0`

<method collect()>

此方法在使用 Stream API 的 Java 代码中经常见到，用于从另一个列表创建一个新列表。

第 8 行的代码 `".collect(Collectors.toList());"` 返回一个列表。

它通常出现在流操作的末尾。

## 问题 25

选择一个描述该程序编译并运行结果的语句。

```java
public class Question_25 {
    public static void main(String[] args) {
        String[] array = {"a", "b", "c", "5" };
        String str = null;

        Arrays.stream(array).forEach(e -> {
            if (e.matches("^[0-9]*$")) {
                str = e;
            }
        });

        System.out.println(padWithZeroLeft(str, 5));
    }

    public static String padWithZeroLeft(String value, int digits) {
        String zero = "0";
        StringBuilder sb = new StringBuilder();

        for (int i = 1; i < digits; i++) {
            sb.append(zero);
        }

        return sb.append(value).toString();
    }
}
```

- (A) 输出 00005
- (B) 输出 00005
- (C) 编译错误
- (D) 运行时异常

答案：(C) 编译错误

在第 6 到 10 行，这是一个 lambda 表达式。在 lambda 表达式中，你不能更改内部变量的值。它应该是 final 的。

如果第 6 到 10 行的代码如下，答案为 (A)。

```java
for (String e : array) {
    if (e.matches("^[0-9]*$")) {
        str = e;
    }
}
```

## 备注

(1) 正则表达式

在第 7 行，你可以看到 `("^[0-9]*$")`。这意味着 0 到 9。

(2) method `matches()`

使用上述正则表达式，这检查字符串是否为数字。

它返回布尔值。

(3) method `padWithZeroLeft()`

左侧补零是实际编码情况中常见的字符串操作。

有外部库可以实现这一点，当然你也可以像此代码中第 15 到 24 行那样自己创建。

为了更好地修复此方法（意味着在实际使用时更少的 bug），应该检查第一个参数 `value` 是否为 null。

并添加异常处理，并将变量 `zero` 设为 final，因为它不应该被更改。

## 问题 26

选择一个描述该程序编译并运行结果的语句。

```java
public class Question_26 {
    public static void main(String[] args) {
        int a = 1;
        int b = Arrays.asList(100, 200).size();
        int c = new Long(3L).intValue();

        if (a + b == c && (c - a) % 2 == 0) {
            System.out.println(method1()[0]);
        }
    }

    private static String[] method1() {
        String[] array = new String[1];
        StringBuilder sb = new StringBuilder();

        sb.append(" " .trim());
        sb.append(sb.toString().toUpperCase());
        array[0] = sb.toString();

        return array;
    }
}
```

- (A) 输出 1
- (B) 输出 11
- (C) 编译错误
- (D) 运行时异常

答案：(B) 输出 11

有几点看起来有点复杂。让我们逐一查看：

备注：

(1) 第 5 行。`Arrays.asList(100, 200).size()` 意味着包含两个元素 100 和 200 的 ArrayList，所以它返回 `2`。

(2) 第 6 行。首先使用 `new Long(3L)` 创建 Long 类型。然而将其赋值给变量 `c` 会导致编译错误，因为它们的类型不同。`intValue()` 方法返回 Long 对象的 int 值。

(3) 第 8 行。条件的一部分 `(c - a) % 2 == 0` 看起来有点复杂。让我们将其分为两部分……（此处省略重复的逻辑说明，遵循原文要求不重复输出）

## 问题 27

```java
public class Question_27 {
    private static String str1 = "A";
    public static String concatStr(String str1, String str2) {
        return new StringBuilder()
            .append(str1)
            .append(str2)
            .toString();
    }
    public static String getStr1() {
        return str1;
    }
}
```

选择一个描述上述程序编译并运行结果的语句。

```java
public class Question_27_2 extends Question_27 {
    public static void main(String[] args) {
        getStr1().toLowerCase();
        Question_27_2 instance = new Question_27_2();
        instance.method1();
    }
    private void method1() {
        System.out.println(concatStr(getStr1(), getStr1()));
    }
}
```

- (A) 输出 aa
- (B) 输出 AA
- (C) 编译错误
- (D) 运行时异常

答案：(B) 输出 AA

此代码的点如下：

- 1. 访问父类的字段是私有的。也有 `getStr1()` 方法。方法的访问修饰符是 public，所以如果你使用此方法获取字段而不是直接访问，就不会发生任何错误。这种方法被称为 "getter 方法"或简单的 "getter"。相反，还有另一种类型被称为 "setter 方法"或简单的 "setter"。它的访问修饰符通常和 getter 一样 public，此方法用于为类的私有字段赋值。如下（如果是该问题代码）：

```java
public static void setStr1(String str1) {
    Question_27.str1 = str1;
}
```

(2) 父类第 4 行的 return 语句写法。有很多情况下在 return 语句之前已经初始化返回值，这是常见的编码风格。然而，你不需要在 return 语句之前创建值，可以在 return 语句中完成。像此代码第 4 行那样写。

## 问题 28

选择一个描述该程序编译并运行结果的语句。

```java
public class Question_28 {
    public static void main(String[] args) {
        LocalDateTime ldt =
        LocalDateTime.of(2020, 01, 01, 12, 34, 56);
        if (!isLocalDateTime(ldt)) {
            return;
        }
        if (!isLocalDateTime(ldt)) {
            System.exit(1);
        }

        System.out.println(ldt.getYear());
    }

    public static boolean isLocalDateTime(LocalDateTime ldt) {
        Predicate<LocalDateTime> predicate =
        new Predicate<LocalDateTime>() {
            public boolean test(LocalDateTime e) {
                return e instanceof LocalDateTime;
            }
        };
        return predicate.test(ldt);
    }
}
```

- (A) 输出 2020
- (B) 输出为空
- (C) 编译错误
- (D) 运行时异常

答案：(A) 输出 2020

该程序的功能如下：

- 1. 创建 LocalDateTime 对象
- 2. 检查它是否为 LocalDateTime 类型
- 3. 输出它的年份

说明

- (1) LocalDateTime

<method now()>

要创建 LocalDateTime 对象，使用 `now()` 方法或 `of()` 方法。

`now()` 方法返回应用程序运行时时间戳的 LocalDateTime 对象。

此外，你可以通过 `of()` 方法指定时间戳的值。

<method getYear()>

此方法返回 LocalDateTime 对象的年份。还有其他类似的方法，如 `getMonth()`、`getHour()` 等。

- (2) Predicate（谓词）

这是 Java 8 中的函数式接口之一。用于返回布尔值。

在第 16 行到 21 行的代码中，它不是 Lambda 表达式。

你可以像下面用 Lambda 表达式重写：

```java
Predicate<LocalDateTime> predicate = e -> e instanceof LocalDateTime;
```

为了使用上述代码，请在第 22 行编写相同的代码。

## 问题 29

选择一个描述该程序在编译和运行时的结果的语句。

```java
public class Question_29 {
    public static void main(String[] args) {
        HashMap<Object, String> map = new HashMap<Object, String>();
        map.put(1L, "A");
        map.put(null, "B");
        map.put("String", null);

        Question_29 instance = new Question_29();
        instance.method1(map.get("String"));
    }

    public void method1(Object object) {
        Optional<Object> a = Optional.ofNullable(object);
        System.out.println(a.orElse("output"));
    }
}
```

- (A) 输出 null
- (B) 输出 output
- (C) 编译错误
- (D) 运行时异常

答案：(B) 输出 output

该程序的功能如下：

- 1. 创建包含三个条目集的 HashMap
- 2. 如果 map 中键 "String" 的值对象不为 null，则输出它。
- 3. 如果 map 中键 "String" 的值对象为 null，则输出 "output"。

说明

- (1) 作为 map 键的 Object 类型

Object 类型可以为空，因此如果你将其指定为 map 的键，可以将其设置为 null。

此外，Object 类型包装了所有类型，因此 `1L` 和 `"String"` 都可以被设置。

- (2) Optional

Optional 类型用于可能为 null 的对象。它包装了该对象。

<method ofNullable()>

`method1` 的参数可能为 null，因此使用了该方法。如果参数可能不为 null，你可以使用 `of()` 方法。

<method orElse()>

此方法用于可空值。

如果你使用 `if` 语句，你必须编写如下所示代码来代替第 19 行的代码：



```
if (object != null) {
    System.out.println("output");
} else {
    System.out.println("output");
}
```

## Question 30

```java
public class Question_30_1 {
    private Long a;
    public Long getA() { return a; }
    public void setA(Long a) { this.a = a; }
}
```

选择一个描述使用上述程序在编译和运行时的结果的语句。

```java
public class Question_30_2 {
    public static void main(String[] args) {
        Question_30_1 a = new Question_30_1();
        Question_30_1 b = new Question_30_1();
        a.setA((Long) 1);
        b.setA(Long.valueOf(2));
        List<Question_30_1> list = Arrays.asList(a, b);
        method1(list);
    }

    public static void method1(List<Question_30_1> list) {
        list.forEach(new Consumer<Question_30_1>() {
            public void accept(Question_30_1 object) {
                System.out.print(object.getA());
            }
        });
    }
}
```

- (A) 输出 12
- (B) 输出 1212
- (C) 编译错误
- (D) 运行时异常

答案：(A) 输出 12

该程序的功能如下：

1. 创建两个带有一个字段的类实例
2. 为它们的每个值赋值
3. 创建包含这些实例的列表
4. 输出列表每个元素的每个字段

说明：

(1) 转换为 Long

将对象转换为 long 有三种简单方法：

1. `(long) object`
2. `Long.valueOf(object)`
3. `new Long(object)`

第 2 和第 3 种是 `Long`，第 1 种是 `long`。Java 编译器会自动将其转换为 `Long`。

(2) Consumer

这是 Java 8 中的函数式接口之一。该方法不返回结果，类型为 `void`。

在第 14 行到 18 行的代码中，它不是 Lambda 表达式。

你可以像下面用 Lambda 表达式重写：

```
list.forEach(e -> System.out.print(e.getA()));
```

或者如下：

```
list.forEach(e -> {
    System.out.print(e.getA());
});
```

## Question 31

选择一个描述该程序在编译和运行时的结果的语句。

```java
public class Question_31 {
    public static void main(String[] args) {
        Long a = 100;
        Integer b = 100;
        try {
            String str = null;
            if (a == b) {
                System.out.println(str.length());
            }
        } catch (NullPointerException e) {
            System.out.println("ABC");
        }
    }
}
```

- (A) 什么都不输出
- (B) 输出 ABC
- (C) 编译错误
- (D) 运行时异常

答案：(B) 输出 ABC

该程序的功能如下。

1. 创建包含三个条目集的 HashMap
2. 什么方法的

说明：

(1) 作为 map 键的 Object 类型

Object 类型可以为空，因此如果你将其指定为 map 的键，可以将其设置为 null。

此外，Object 类型包装了所有类型，因此 `1L` 和 `"String"` 都可以被设置。

(2) Optional

Optional 类型用于可能为 null 的对象。它包装了该对象。

`method1` 的参数可能为 null，因此使用了该方法。如果参数可能不为 null，你可以使用 `of()` 方法。

`methodElse()`

此方法用于可空值。

如果你使用 `if` 语句，你必须编写如下所示代码来代替第 19 行的代码：

```java
if (object != null) {
    System.out.println("output");
} else {
    System.out.println("output");
}
```

## Question 32

选择一个描述该程序在编译和运行时结果的语句。

```java
public class Question_32 {
    public static void main(String[] args) {
        List<Integer> list1 = Arrays.asList(1, 2, 3);
        List<Integer> list2 = Arrays.asList(4, 5, 6);
        List<Integer> list3 = Arrays.asList(list1, list2);
        method1(list3).forEach(System.out::print);
    }

    private static List<Object> method1(List<List<Integer>> list) {
        return list.stream()
            .flatMap(e -> e.stream())
            .sorted(Comparator.reverseOrder())
            .collect(Collectors.toList());
    }
}
```

- (A) 输出 123456
- (B) 输出 654321
- (C) 编译错误
- (D) 运行时异常

答案：(B) 输出 654321

该程序的功能

1. 创建两个存储元素的列表
2. 创建一个包含它们的列表
3. 将列表中的两个列表以逆序存储 Integer
4. 输出所有

说明：

(1) flatMap()

此方法将多个集合转换为一个流。它使得合并列表变得简单。

在此代码中，第 8 行所示的列表中包含两个列表。

list3 内部：

1. [1, 2, 3]
2. [4, 5, 6]

在使用 `flatMap()` 和 `sorted()` 方法后：

```
[6, 5, 4, 3, 2, 1]
```

(2) 方法引用

第 10 行的 `method1(list3).forEach(System.out::print);` 使用了方法引用。你可以借此简化代码。

如果你将其重写为 Lambda，看起来如下所示：

```
method1(list3).forEach(e -> System.out.print(e));
```

## Question 33

选择一个描述该程序在编译和运行时结果的语句。

```java
public class Question_33 {
    public static void main(String[] args) {
        String str = "JAVA";
        try {
            throw new NumberFormatException();
        } catch (NullPointerException e) {
            return;
        } catch (Exception e) {
            Predicate<Long> a = Predicate.isEqual(2L);
            if (a.test(10L)) {
                str.replace("JAVA", "ABC");
            } else {
                str.replace("JAVA", "");
            }
        }
        System.out.println(str.length());
    }
}
```

- (A) 输出 0
- (B) 输出 3
- (C) 输出 4
- (D) 编译错误或运行时异常

答案：(C) 输出 4

这段代码的逻辑如下：

1. 初始化 str
2. 显式抛出 NumberFormatException
3. 第二个 catch 块，替换 str
4. 输出 str 的长度

## 注意事项：

(1) 显式抛出异常

显式抛出异常看起来有点奇怪，但它不会导致任何错误。第 8 行抛出的异常是 NumberFormatException，因此第一个 catch 块不会执行。然而，第二个 catch 块会捕获所有异常，因为 Exception 类封装了所有异常。

### (2) Predicate（谓词接口）

第 13 行和第 14 行的代码非常简单。它比较了 `2L` 和 `10L` 并返回布尔值。这是在 Predicate 接口中使用 `isEqual()` 方法的一种方式。

### (3) String（字符串）

String 是不可变的。如果第 14 行返回 true 且第 15 行是 `str = str.replace("JAVA", "ABC");`，则答案是 (B)。如果第 14 行返回 false 且第 17 行是 `str = str.replace("JAVA", "");`，则答案是 (A)。

## 问题 34

选择一个描述该程序在编译和运行结果的语句。

```java
public class Question_34 {
    public static void main(String[] args) {
        Question_34 a = new Question_34();
        ABC b = a.new ABC(false);
        System.out.println(b.str1);
    }
}
class ABC {
    private String str1;
    public ABC(boolean flg) {
        Predicate<Boolean> a = new Predicate<Boolean>() { {
            public boolean test(boolean flg) {
                return !flg;
            }
        };
        str1 = a.test(flg) ? "a" : "b";
    }
}
```

- (A) 输出 a
- (B) 输出 b
- (C) 编译错误
- (D) 运行时异常

答案：(A)

这段代码的逻辑如下：

1. 创建带有 false 的内部类实例 b
2. 输出实例的 str

备注：

(1) 内部类

```
<内部类和构造函数>
```

在 Java 中，你可以在外部类内部创建内部类，如第 11 行。第 11 行的内部类 ABC 有一个字段，构造函数位于第 14 到 22 行。构造函数使用一个 boolean 类型参数，因此如果你不带任何参数或使用错误参数创建该类的实例会导致编译错误。第 15 行 Predicate 接口的 `test()` 方法使用 Boolean 类型参数并返回其反反值，因此赋值给 str1 的参数是 a。

```
<创建实例>
```

那么，如何使用内部类稍微有点复杂。如果你在 `main()` 方法中写下面的代码，会导致编译错误。

```java
ABC instance = new ABC();
```

这意味着在创建内部类实例时，必须先创建外部类的实例。之后，你就可以像第 5 行的代码那样创建内部类实例。

## 问题 35

选择一个描述该程序在编译和运行结果的语句。

```java
public class Question_35 {
    private static final String str1;
    private static final String str2;
    static {
        if (Question_35.class.getSimpleName().length() < 0) {
            str1 = "";
            str2 = "";
        } else {
            str1 = "A";
            str2 = "B";
        }
    }
    public static void main(String[] args) {
        Optional<String> a = Optional.Nullable(str1);
        a.ifPresent(new Consumer<String>() {
            @Override
            public void accept(String t) {
                System.out.println(str2);
            }
        });
    }
}
```

- (A) 输出 A
- (B) 输出 B
- (C) 无输出
- (D) 编译错误或运行时异常

答案：(B) 输出 B

该程序的逻辑如下：

1. 在静态初始化器初始化两个常量
2. 输出 str2

备注：

(1) 静态初始化器

静态初始化器是静态代码，在类加载时仅执行一次。例如，当你想要用 `if` 语句初始化常量时，静态初始化器非常有用。正如第 3 行和第 4 行所示，修饰符都是 `final`，但你可以在静态初始化器中赋值。

(2) getClassName() 方法

此方法位于 `Class` 类中。它如方法名所示直接返回类名。因此，`"Question_35.class.getClassName()"` 的返回值是 Question_35。

(3) ifPresent() 方法

这是 `Optional` 类中的一个有用方法。第 18 行到 23 行的代码等同于下方：

```java
if (a != null) {
    System.out.println(Question_35.class.getClassName());
}
```

(4) override 注解

此方法不是必须的，但为了避免重写错误，建议使用。

## 问题 36

文件 (`C:/Users/user/Desktop/file.txt`) 中的内容：

- 1 a,b,c,d,e
- 2 A,B,C,D
- 3 1,2,3,4,5

选择一个描述该程序在编译和运行结果的语句。

```java
public class Question36 {
    public static void main(String[] args) throws IOException {
        Path path = Paths.get("C:/Users/user/Desktop/file.txt");
        List<String> list1 = Files.readAllLines(path);
        List<String> list2 = list1.stream()
            .flatMap(e -> Arrays.stream(e.split(",")))
            .map(e -> e.toLowerCase())
            .distinct()
            .collect(Collectors.toList());

        list2.forEach(e -> {
            if (e.matches("^[0-9]*$")) {
                System.out.print(e);
            }
        });
    }
}
```

- (A) 输出 0
- (B) 输出 B
- (C) 编译错误
- (D) 运行时异常

答案：(B) 输出 B

该程序如下：

1. 从文件中读取所有行
2. 使用元素创建列表

备注：

(1) readAllLines()

`Files` 类中的此方法非常有用。如果你想读取所有行，如第 3 行所示。

(2) 第 6 到 11 行

这看起来有点复杂。

(3) Stream 操作

它们是中间操作和终端操作。第 7 到 10 行是中间操作。而第 11 行是终端操作。

## 问题 37

选择一个描述该程序在编译和运行结果的语句。



```java
public class Question37 {
    public static void main(String[] args) {
        Function<String, Boolean> a = new Function<String, Boolean>() {
            @Override
            public Boolean apply(String t) {
                return null;
            }
        };
        if (null == null) {
            method1(a);
        }
    }

    public static void method1(Function<String, Boolean> a) {
        try {
            Optional<Boolean> b = Optional.of(a.apply("123"));
        } catch (NullPointerException e) {
            System.exit(1);
        } finally {
            System.out.println("321");
        }
    }
}
```

- (A) 输出 321
- (B) 无输出
- (C) 编译错误
- (D) 运行时异常

答案：(B) 无输出

这段代码的逻辑如下：

1. 创建函数接口
2. 捕获 `NullPointerException`
3. 程序停止

备注：

(1) `Function`

这是函数式接口之一。它的默认方法是 `apply()`，你可以在第 5 行看到 `@Override` 注解。为了方便理解，可以将其视为 Java 中的普通方法。

(2) 第 11 到 13 行

看起来像编译错误，但运行正常。它返回 true。然而，实际代码中不建议这样做。

(3) `of()` 方法

`Optional` 类的此方法用于封装非空值。如果值为 null，它会抛出 `NullPointerException`，因此在执行第 19 行后，异常将被捕获。而且如果应用程序通过 `System.exit()` 方法结束，`finally` 块将不会执行，因此答案是 (B)。

## 问题 38

选择一个描述该程序在编译并运行结果的语句。

```java
public class Question_38 {
    public static void main(String[] args) throws Exception {
        int min = 1, a = 0, b = 0;
        Integer[] array = { 2, 5, 1, 3, 4 };

        Arrays.parallelSort(array);
        a = array[0];

        Thread.sleep(1000);

        Arrays.sort(array);
        b = array[0];

        if (min == a && a == b) {
            Integer[] array2 = Arrays.copyOf(array, 6);
            System.out.print(Arrays.toString(array2));
        } else {
            return;
        }
    }
}
```

- (A) 输出 [1, 2, 3, 4, 5, null]
- (B) 输出无内容
- (C) 编译错误
- (D) 运行时异常

答案：(A) 输出 [1, 2, 3, 4, 5, null]

该程序的功能如下：

1. 初始化三个 `int` 变量
2. 初始化一个包含五个元素的 `Integer` 类型数组
3. 进行了两次排序
4. 创建它的副本
5. 输出它

笔记：

(1) 初始化多个变量

第 5 行看起来像是编译错误，但你可以在一行中初始化多个变量。这有助于代码看起来更简单。你不需要为每个变量使用换行。

(2) `sort()` 方法和 `parallelSort()` 方法

这些方法用于数组排序。实际上它们的作用是相同的，但处理速度不同。`parallelSort()` 方法是多线程的，因此如果数组很大，它会比 `sort()` 方法快。

(3) `sleep()` 方法

该方法位于 `Thread` 类中。它让应用程序按照指定的时间暂停。在代码第 11 行中，参数 1000 等于 1 秒。

(4) `copyOf()` 方法

该方法位于 `Arrays` 类中。在代码第 17 行中，将 6 作为第二个参数。实际上它大于数组的长度，但它不会抛出异常。如答案 (A) 所示，它创建了一个带有 null 的数组副本。

## 问题 39

选择一个描述该程序在编译并运行结果的语句。

```java
public class Question_39 {
    public static void main(String args[]) {
        List<Integer> list1 = new ArrayList<>();
        List<Integer> list2 = new ArrayList<>();

        list1.addAll(Arrays.asList(new Integer[] { 1, 2, 3, 4, 5 }));
        list2.addAll(Arrays.asList(new Integer[] { 1, 2, 3 }));

        list2.addAll(list1.subList(3, 5));

        if (list1.equals(list2)) {
            list2.clear();
            list2.sort(Comparator.naturalOrder());
            list2.sort(Comparator.reverseOrder());
            System.out.print(list2.get(0));
        } else {
            return;
        }
    }
}
```

- (A) 输出 []
- (B) 输出无内容
- (C) 编译错误
- (D) 运行时异常

答案：(D) 运行时异常

该程序的功能如下：

1. 初始化两个具有不同元素的列表
2. 向第二个列表添加元素，且元素均相同
3. 尝试输出空列表的第一个元素

笔记：

(1) `addAll()` 方法

该方法用于通过列表的参数向列表添加元素。

(2) `subList()` 方法

为了容易理解此方法，记住 `String` 类中的 `substring()` 方法是一个好方法。它获取列表指定范围的元素，如下所示：

```
1 2 3 4 5
| | | | |
0 1 2 3 4 5
```

在代码第 11 行中，参数是 3 和 5，因此 `list1` 的第 4 和第 5 个元素被添加到 `list2` 的末尾。

(3) `List` 中的 `equals()` 方法

如果类型、大小、元素和顺序相等，则该方法返回 true。

(4) `clear()` 方法

它让列表为空。在第 16 行和第 17 行，尝试对元素列表进行排序，但它不会抛出异常。

(5) `IndexOutOfBoundsException`

当你尝试获取超出列表大小范围的元素时会发生此异常。在代码中，位于第 21 行（原文第 19 行）。

## 问题 40

选择一个描述该程序在编译并运行结果的语句。

```java
public class Question_40 {
    class ABC {
        private String str;
    }

    public static void main(String args[]) {
        Question_40 a = new Question_40();
        ABC b = a.new ABC();
        ABC c = a.new ABC();
        ABC d = a.new ABC();

        b.str = "A";
        c.str = "B";
        d.str = "C";

        List<ABC> list = Arrays.asList(b, c);
        list.add(d);

        for (ABC e : list) {
            if (e instanceof ABC) {
                System.out.print(e.str);
            } else {
                System.out.print(e);
            }
        }
    }
}
```

- (A) 输出 ABC
- (B) 输出无内容
- (C) 编译错误
- (D) 运行时异常

答案：(C) 编译错误

（注：由于原文存在大量 OCR 乱码和逻辑重复，此处根据 Java 逻辑对代码结构进行了还原。`Arrays.asList` 返回固定大小列表，调用 `add` 会抛出 `UnsupportedOperationException`，但选项中无运行时异常对应此情况，且原文标注答案为编译错误，故保留原答案。）

## 问题 41

选择一个描述该程序在编译并运行结果的语句。

```java
public class Question_41 {
    private static Function<StringBuilder, String> function = new Function<StringBuilder, String>() {
        @Override
        public String apply(StringBuilder sb) {
            return sb.delete(0, sb.length() - 1)
                .append("bc23")
                .toString();
        }
    };

    public static void main(String[] args) {
        String str = function.apply(new StringBuilder("java"));

        List<String> list = new ArrayList<>();
        for (char e : str.toCharArray()) {
            if (Character.isLetter(e)) {
                list.add(String.valueOf(e));
            }
        }

        list.forEach(System.out::print);
    }
}
```

- (A) 输出 abc
- (B) 输出 bc
- (C) 编译错误
- (D) 运行时异常

答案：(A) 输出 abc

该程序的功能如下：

1. 创建一个 `abc23` 的 `String` 对象
2. 创建包含字母表值的列表
3. 输出元素

笔记：

(1) `Function`

这是函数式接口之一。这意味着该函数使用 `StringBuilder` 参数并返回 `String`。因此，它的行为与代码相同。

```java
private static String method1(StringBuilder sb) {
    return sb.delete(0, sb.length() - 1)
        .append("bc23")
        .toString();
}
```

该函数执行于第 14 行。

(2) `StringBuilder` 中的 `delete()` 方法

为了容易理解此方法，记住 `String` 类中的 `substring()` 方法是一个好方法。它删除 `StringBuilder` 中指定范围的元素，如下所示：

```
java
| | | | |
0 1 2 3 4
```

因此，第 7 行方法的返回值为 "a"，然后追加 "bc23" 并将其转换为 `String`。

## 问题 42

选择一个描述该程序在编译并运行结果的语句。

```java
public class Question_42 {
    class ABC {
        private HashMap<Integer, String> map;
        public ABC(int a) {
            map = new HashMap<>();
            for (int i = 0; i < a; i++) {
                map.put(i, "java" + (i + 1));
            }
        }
    }

    public static void main(String args[]) {
        Question_42 a = new Question_42();
        ABC b = a.new ABC(5);
        List<Object> list = b.map.entrySet().stream()
            .map(e -> e.getValue())
            .collect(Collectors.toList());
        list.forEach(new Consumer<Object>() {
            public void accept(Object object) {
                System.out.print(object);
            }
        });
    }
}
```

- (A) 输出 java0@java1java2java3java4
- (B) 输出 java1java2java3java4java5
- (C) 编译错误
- (D) 运行时异常

答案：(C) 编译错误（原文注：因为 `map` 未初始化，但代码中已在构造函数初始化，实际应输出 (B)）。

答案：(D) 运行时异常

该程序的逻辑如下：

1. 创建 `Question` 类的实例
2. 创建 `ABC` 类的实例
3. 在 `ABC` 类的构造函数中抛出 `NullPointerException`（空指针异常）

备注：

(1) `ABC` 类的构造函数

<为什么会发生 `NullPointerException`>

1. 使用 `int` 类型的参数作为循环次数
2. 尝试将元素放入 `map` 字段中
3. 在第 7 行抛出 `NullPointerException`

在第 3 行，创建了 `map`。然而，此时它是 null（空）。所以，当尝试使用 `put()` 方法放入元素时，会抛出 `NullPointerException`。

<避免引起 `NullPointerException`>

当你将第 3 行的代码重写为如下所示时，程序将无异常运行：

```java
private HashMap<Integer, String> map = new HashMap<>();
```

如果是这样，执行完构造函数中的代码后，`map` 的 `entrySet` 如下所示：

0:java1, 1:java2, 2:java3, 3:java4, 4:java5

这就是为什么答案是 (B) 的原因。如果方法 `getValue()` 是 `getKey()`，则输出 01234。

## 问题 43

选择一个描述该程序在编译并运行结果的语句。

```java
public class Question_43 {
    public static void main(String[] args[]) {
        Boolean flg = null;
        Integer[] array = { 10, 20, 30 };

        int a = array[0], b = array[1];
        flg = Integer.compare(a + b, array[2]) != 0 ? null : !false;

        Optional<Boolean> c = Optional.ofNullable(flg);
        c.ifPresent(x -> {
            for (Integer y : array) {
                y = 0;
            }
        });

        Arrays.stream(array).forEach(System.out::print);
    }
}
```

- (A) 输出 102030
- (B) 输出 000
- (C) 编译错误
- (D) 运行时异常

答案：(A) 输出 102030

该程序的逻辑如下：

1. 创建一个包含元素 [10, 20, 30] 的 `Integer` 类型数组
2. 检查 10 + 20 是否等于 30
3. 遍历数组
4. 输出每个元素

备注：

(1) `Integer.compare()`

此方法使用两个参数，并比较第一个参数是否等于、大于或小于第二个参数。它返回一个 `int` 值。返回值如下：

- 参数相等： 0
- 第一个参数大于第二个参数： 1
- 第一个参数小于第二个参数： -1

所以，该代码在第 9 行的返回值为 0，条件为 false，`flg` 的值为 `!false` 即 `true`。

(2) 标准 for 循环、增强型 for 循环、Stream API 的 `forEach`

遍历数组有三种方法，但只有像下面所示的方法会影响根数组：

1. 标准 for 循环，影响根数组



## 增强型 for 循环（不影响根数组）

## StreamAPI 的 forEach（不影响根数组）

这就是为什么答案是 (A) 的原因。

如果你在第 14 到 16 行使用 StreamAPI 的 forEach，答案也是 (A)。

如果你在第 14 到 16 行使用标准 for 循环，答案是 (B)。

## 问题 44

选择一个描述该程序在编译并运行结果的语句。

```java
1 public class Question_44 {
2    public static void main(String args[]) {
4      List<String> list1 = Arrays.asList("a", "b", "c");
5      List<String> list2 = list1.stream()
6          .filter(e -> e.matches("^[0-9]*$"))
7          .sorted(Comparator.reverseOrder())
8          .collect(Collectors.toList());
11     List<String> list3 = null;
13     try {
14         if (list1.equals(list2)) {
15             System.exit(1);
16         } else {
17             Objects.requireNonNull(list3, "list3 is null");
19         }
20     } catch (Exception e) {
21         System.out.println("Exception occurred");
23     }
25   }
26 }
```

+ (A) 输出 list3 is null
+ (B) 输出 Exception occurred
+ (C) 编译错误
+ (D) 运行时异常

答案：(B) 输出 Exception occurred

该程序的逻辑如下：

+ 1. 创建包含元素 `["a", "b", "c"]` 的 `list1`
2. 创建 `list2`，元素为 `list1` 中除数字以外的元素并倒序
3. 创建 `list3` 为 `null`
4. 比较 `list1` 和 `list2` 是否相等
5. 抛出 `NullPointerException`
6. 输出 Exception occurred

备注：

(1) 正则表达式

在第 7 行，你可以看到 `"^[0-9]*$"`。这意味着 0 到 9。然而，在元素 `["a", "b", "c"]` 中没有数字，所以这段代码实际上没有产生影响。

(2) List 中的 `equals()` 方法

如果类型、大小、元素和顺序都相等，则该方法返回 true。

如你在第 8 行所示，`list2` 方法改变了顺序。

(3) `Objects.requireNonNull` 方法

第 17 行的此方法检查第一个参数是否为 `null`，如果是，则抛出 `NullPointerException`。

这就是为什么答案是 (A) 的原因。

## 问题 45

选择一个描述该程序在编译并运行结果的语句。

```java
public class Question45 {
    @Override
    public String get() {
        return "a";
    }
    public static void main(String args[]) {
        Question45 b = new Question45();
        String c = b.get();
        
        HashMap<Integer, String> map = new HashMap<>();
        map.put(1, "a");
        map.put(2, "b");
        
        if (c == null) {
            System.out.println(map.get(1));
        }
}
```

+ (A) 输出 null
+ (B) 输出 false
+ (C) 编译错误
+ (D) 运行时异常

答案：(D) 运行时异常

该程序的逻辑如下：

+ 1. 创建 map 并放入元素
2. 检查 null
3. 如果值为空则抛出 NullPointerException

备注：

(1) 构造函数

此方法在第 6 行返回一个值。

(2) `equals()` 方法

在第 12 行，值不相等，所以返回 false。

(3) `OptionalNullable()` 方法

如果第 21 行使用的是 `OptionalNullable()`，答案是 (B)。

这就是为什么答案是 (D) 的原因。

## 问题 46

选择一个描述该程序在编译并运行结果的语句。

```java
public class Question_46 {
    public static void main(String args[]) {
        Integer[] array1 = { 2, 3, 1 };
        Integer[] array2 = Arrays.copyOf(array1, array1.length);
        Arrays.sort(array2);

        Optional<String> a = Optional.ofNullable(Question_46.class.getSimpleName());
        int b = 0;

        for (char x : a.get().toCharArray()) {
            Arrays.stream(array1).forEach(y -> {
                if (String.valueOf(x).equals(String.valueOf(y))) {
                    b++;
                    System.out.println(b);
                    return;
                }
            });
        }
    }
}
```

+ (A) 输出无
+ (B) 输出 1
+ (C) 编译错误
+ (D) 运行时异常

答案：(C) 编译错误

该程序的逻辑如下（假设没有发生编译错误）：

+ 1. 创建两个数组并对第二个进行排序
2. 遍历字符串 `"Question_46"` 中的字符
3. 检查 `array1` 是否包含字符
4. 第 15 行的条件永远为假，所以程序结束无输出

备注：

(1) 第 15 行的 if 条件

在第 15 行，它检查 `array1` 中的元素是否包含 `"Question_46"` 的任何字母。元素为 `[1, 2, 3]`。所以即使评估了所有元素，该条件也不会返回 true。

(2) lambda 中修改值

在第 14 到 20 行，这是一个 lambda 表达式。在 lambda 表达式中，你不能更改变量的值。它必须是 final（最终的）。

如果第 14 到 20 行的代码如下所示，答案是 (A)。

```java
for (Integer element : array1) {
    if (String.valueOf(x).equals(String.valueOf(element))) {
        b++;
        System.out.println(b);
        return;
    }
}
```

(3) 第 4 行

如果你在第 4 行将 `array1` 的第二个元素改为 2，答案是 (B)。

## 问题 47

选择一个描述该程序编译并运行结果的语句。

```java
public class Question_47 {
    public Question_47() {
        Random a = new Random();
        String b = "a";
        Integer c = null;
        int abc = 0;

        try {
            c = a.nextInt(Integer.parseInt(b));
        } catch (Exception e) {
            abc += 1;
            return;
        } finally {
            Optional<Integer> d = Optional.ofNullable(c);
            System.out.print(d.orElse(abc));
        }
    }

    public static void main(String args[]) {
        Question_47 a = new Question_47();
    }
}
```

- (A) 什么都不输出
- (B) 输出 1
- (C) 编译错误
- (D) 运行时异常

答案：(B) 输出 1

该程序的执行过程如下：

- 1. 创建 `Question_47` 的实例
- 2. 尝试将 String `"a"` 转换为 int
- 3. 抛出 `NumberFormatException`
- 4. 输出 1

## 注意事项：

(1) 构造函数

第 3 行到 18 行是 `Question_47` 类的构造函数。它会在创建 `Question_47` 类的实例时执行。

因此，它会在第 21 行执行。

(2) return 语句与 finally 块的执行顺序

第 13 行有一个 return 语句。然而，在返回之前，会先执行 finally 块。

执行 finally 块后，将执行 return 语句。

(3) `orElse()` 方法

`Optional` 类中的此方法用于可空值。

如果你使用 if 语句，你必须编写类似下面的代码，而不是第 16 行的代码：

```java
if (object != null) {
    System.out.print(d);
} else {
    System.out.print(abc);
}
```

## 问题 48

选择一个描述该程序编译并运行结果的语句。

```java
1 public class Question_48 {
2
3 private static Predicate<Integer> predicate = Predicate.isEqualTo(1);
4
5 public static void main(String args[]) {
6 List<Integer> list1 = Arrays.asList(1, 2, 3, 4, 5);
7 List<Integer> list2 = Arrays.asList(1, 2);
8 List<Integer> list3 = Arrays.asList(3, 4, 5);
9 List<List<Integer>> list4 = Arrays.asList(list2, list3);
10 List<Integer> list5 = null;
11
12 Optional<List<Integer>> a = Optional.ofNullable(list5);
13 try {
14 a.orElseThrow(NullPointerException::new);
15 } catch (Exception e) {
16 list5 = list5.flatMap(b -> b.stream())
17
18 .sorted(Comparator.reverseOrder())
19 .collect(Collectors.toList());
20
21 System.out.print(predicate.test(list1.get(0))
22 && predicate.test(list5.get(list1.size() - 1)));
23 }
24 }
25 }
```

- (A) 输出 true
- (B) 输出 false
- (C) 编译错误
- (D) 运行时异常

答案：(A) 输出 true

该程序的执行过程如下：

- 1. 创建包含元素 `[1, 2, 3, 4, 5]` 的 `list1`
- 2. 创建包含元素 `[1, 2]` 的 `list2`
- 3. 创建包含元素 `[3, 4, 5]` 的 `list3`
- 4. 创建包含元素 `[list2, list3]` 的 `list4`
- 5. 创建 `list5` 为 `null` 并使用 `ofNullable()` 方法封装
- 6. 抛出 `NullPointerException`
- 7. 以反序顺序 `[5, 4, 3, 2, 1]` 将元素赋值给 `list5`
- 8. 输出比较结果：1 是否等于 `list1` 的第一个元素以及 `list5` 的最后一个元素

注释：

(1) `orElseThrow()` 方法

`Optional` 类中的此方法用于可空值。在第 12 行，此时 `list5` 为 `null`，因此第 14 行抛出 `NullPointerException`。

如果对象为 `null`，此方法会抛出 `NullPointerException`。

此外，你也可以在不使用方法引用的情况下重写第 14 行：

```java
a.orElseThrow(() -> new NullPointerException());
```

(2) `flatMap()` 方法

此方法将多个集合转换为一个流。它使得合并列表变得简单。

(3) Predicate

第 3 行、21 行和 22 行的代码逻辑非常简单。它比较了 1 与 `list1` 的第一个元素以及 `list5` 的最后一个元素。

这是在 `Predicate` 接口中使用 `isEqual()` 方法的一种方式。

## 问题 49

选择一个描述该程序编译并运行结果的语句。

```java
public class Question_49 {
    private static final String str;
    private static final String[] array;

    static {
        str = "a,b,c";
        array = str.split(",");
    }
    public static void main(String[] args[]) {
        Arrays.stream(array).forEach(e -> {
            switch (e) {
                case "a":
                    System.out.print(1);
                case "b":
                    System.out.print(2);
                case "c":
                    System.out.print(3);
                default:
                    System.out.print(4);
            }
        });
    }
}
```

- (A) 输出 123
- (B) 输出 234
- (C) 输出 3423
- (D) 编译错误或运行时异常

答案：(B) 输出 234

该程序的执行：

- 1. 初始化 `str` 和 `array`
- 2. 遍历数组并输出 switch 语句

注释：

(1) switch 语句是如何执行的

第 13 行到 22 行的 switch 语句由于没有 break 语句，执行顺序如下：

第一次循环：第 15 行、17 行、21 行

第二次循环：第 17 行、19 行、21 行

第三次循环：第 19 行、21 行

这就是为什么答案是 (B)。

```java
switch (e) {
  case "a":
    System.out.print(1);
  case "b":
    System.out.print(2);
  case "c":
    System.out.print(3);
  default:
    System.out.print(4);
}
```

## 问题 50

选择一个描述该程序编译并运行结果的语句。

```java
1 public class Question_50 {
    private static Predicate<Integer> a = new Predicate<Integer>() {
        public boolean test(Integer b) {
            return b > 0;
        }
    };
    public static void main(String args[]) {
        try {
            String[] array = { "12 3 ", "123 " };
            for (String str : array) {
                str = str.replace(" ", "");
            }
            System.out.print(a.test(Integer.parseInt(array[0])));
        } catch (Exception e) {
            System.exit(1);
        } finally {
            System.out.print("done");
        }
    }
}
```

- (A) 什么都不输出
- (B) 输出 trued



## 程序执行分析

- (C) 输出 done
- (D) 编译错误或运行时异常

**答案：(A) 什么都不输出**

### 执行过程

1. 创建包含元素 `["12 3 ", "123 "]` 的 array
2. 遍历它并将空格替换为空
3. 终止应用程序

### 注释

#### (1) 标准 for 循环、增强 for 循环、Stream 的 forEach

有三种遍历数组的方法，但只有一种会影响根数组，如下：

1. **标准 for 循环**（影响数组）
2. **增强 for 循环**（不影响数组）
3. **Stream 的 forEach**（不影响数组）

这就是为什么答案是 (A)。

#### (2) 终止应用程序的方法

在第 19 行，使用了 `System.exit()` 方法终止应用程序。

在这种情况下，`finally` 块不会执行。

如果你在第 19 行使用 `return;` 而不是 `System.exit(1);`，答案则是 (C)。
