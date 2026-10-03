
## 代码片段 1

```java
final List<String> people = new ArrayList<>();

people.add("Bob");
people.add("bob");
people.add("Tina");
people.add("Louise");

final Filterobs f = new Filterobs();

f.process(q -> {
    q.remove(second);
    q.forEach(first);
}, people);
```

- A. 打印了两行。
- B. 打印了三行。
- C. 一行代码无法编译。
- D. 两行代码无法编译。
- E. 三行代码无法编译。
- F. 代码编译但在运行时抛出异常。

## 22. 下列有多少声明可以编译？

```java
import java.util.*;

public class ListOf {

    public void create() {
        List<?> n = new ArrayList<>();
        List<? extends Exception> o = new ArrayList<>();
        List<? super Exception> p = new ArrayList<>();
        List<List<? extends Exception>> r = new ArrayList<>();
        List<List<? super Exception>> s = new ArrayList<>();
    }
}
```

- A. 无
- B. 一个
- C. 两个
- D. 三
- E. 四
- F. 五

## 23. 运行以下程序的结果是什么？

```java
package fun;

public class Sudoku {

    static int[][] game;

    public static void main(String[] args) {
        game[3][3] = 6;
        Object[] obj = game;
        obj[3] = 'X';
        System.out.println(game[3][3]);
    }
}
```

- A. 6
- B. x
- C. 代码无法编译。
- D. 代码编译但在运行时抛出 `NullPointerException`。
- E. 代码编译但在运行时抛出不同的异常。
- F. 输出无法保证。

## 24. 哪些命令可以包含以下输出？（选择两个。）

```text
JDK Internal API 建议替换
sun.misc.Unsafe http://openjdk.java.net/jeps/260
```

- A. `jdeps sneaky.jar`
- B. `jdeps -j sneaky.jar`
- C. `jdeps -s sneaky.jar`
- D. `jdeps --internals sneaky.jar`
- E. `jdeps -jdkinternals sneaky.jar`
- F. `jdeps --jdk-internals.jar`

## 25. 假设以下类被许多线程并发访问，关于 `CountSheep` 的哪个陈述是正确的？

```java
package fence;

import java.util.concurrent.atomic.*;

public class CountSheep {

    private static AtomicInteger counter = new AtomicInteger();
    private Object lock = new Object();

    public synchronized int increment1() {
        return counter.incrementAndGet();
    }

    public static synchronized int increment2() {
        return counter.getAndIncrement();
    }

    public int increment3() {
        synchronized(lock) {
            return counter.getAndIncrement();
        }
    }
}
```

- A. 该类只有在移除 `increment1()` 后才是线程安全的。
- B. 该类只有在移除 `increment2()` 后才是线程安全的。
- C. 该类只有在移除 `increment3()` 后才是线程安全的。
- D. 该类已经是线程安全的。
- E. 代码无法编译。
- F. 代码编译但可能抛出异常。

## 26. main 方法中有多少行编译失败？

```java
public class Transport {

    static interface Vehicle {}
    static class Bus implements Vehicle {}

    public static void main(String[] args) {
        Bus bus = new Bus();
        System.out.println(null instanceof Bus);
        System.out.println(bus instanceof Vehicle);
        System.out.println(bus instanceof Bus);
        System.out.println(bus instanceof ArrayList);
        System.out.println(bus instanceof Collection);
    }
}
```

- A. 无
- B. 一个
- C. 两个
- D. 三
- E. 四
- F. 五

## 27. 以下应用的输出结果是什么？

```java
package fly;

public class Helicopter {

    public int adjustPropellers(int length, String[] type) {
        length++;
        type[0] = "LONG";
        return length;
    }
}
```

```java
public static void main(String[] args) {
    final var h = new Helicopter();
    var length = 5;
    var type = new String[1];
    length = h.adjustPropellers(length, type);
    System.out.print(length + "," + type[0]);
}
```

- A. 5, LONG
- B. 6, LONG
- C. 5,null
- D. 6,null
- E. 代码无法编译。
- F. 代码可以编译但在运行时抛出异常。

## 28. 以下代码的输出是什么？

```java
var dice = new LinkedList<Integer>();
dice.offer(3);
dice.offer(2);
dice.offer(4);
System.out.print(dice.stream().filter(n -> n != 4));
```

- A. 2
- B. 3
- C. [3 2]
- D. 代码无法编译。
- E. 以上都不是。

## 29. 这些类中有多少个类会导致编译错误？

```java
final class Chimp extends Primate { }
non-sealed class Bonabo extends Primate { }
final class Gorilla { }

public abstract sealed class Primate permits Chimp, Bonabo {
    abstract String getName();
}
```

- A. 无
- B. 一个
- C. 两个
- D. 三
- E. 四

## 30. 关于 requires 指令，哪些描述是正确的？（选择两个。）

- A. 将其更改为 requires 直接指令总是允许的。
- B. 将其更改为 requires 直接指令永远不允许。
- C. 将其更改为 requires 直接指令有时允许。
- D. 包含 requires java.base 是允许的，但是冗余的。
- E. 包含 requires java.base 永远不允许。
- F. 包含 requires java.base 有时需要更改文件的含义。

## 31. 在 `transformation()` 方法结束之前，以下哪些是正确的？（选择两个。）

```java
public static void transformation() {
    String state1 = new String("ice");
    String state2 = new String("water");
    String state3 = new String("mist");
    state1 = state2;
    state2 = state3;
    state3 = state1;
}
```

- A. 没有对象符合垃圾回收条件。
- B. 有一个对象符合垃圾回收条件。
- C. 有两个对象符合垃圾回收条件。
- D. 没有对象保证会被垃圾回收。
- E. 有一个对象保证会被垃圾回收。
- F. 有两个对象保证会被垃圾回收。

## 32. 假设有一个名为 peacock 的表，包含两列：name 和 rating。如果表是空的，以下代码的输出是什么？

```java
8: var url = "jdbc:sqldb:file:birds";
9: var sql = "SELECT name FROM peacocks WHERE name = ?";
10: try (var conn = DriverManager.getConnection(url);
11: var stmt = conn.prepareStatement(sql,
12: ResultSet.TYPE_FORWARD_ONLY,
13: ResultSet.CONCUR_READ_ONLY) {
14:
15: stmt.setString(1, "Feathers");
16:
17: try (var rs = stmt.execute()) {
18: System.out.println(rs.next());
19: }
20: }
```

- A. false
- B. true
- C. 由于第 10–13 行代码无法编译。
- D. 由于第 17–18 行代码无法编译。
- E. 由于其他行代码无法编译。
- F. 代码在运行时抛出异常。

## 33. 以下代码打印哪两个数字？（选择两个。）

```java
10: int numWorms = 0;
11: ++numWorms;
12: System.out.println(numWorms++);
13: int mask = ~numWorms;
14: System.out.println(mask);
```

- A. 1
- B. 2
- C. 3
- D. -1
- E. -2
- F. -3

## 34. Bill 想要创建一个使用 NIO.2 读取他所有书籍所有行的程序。遗憾的是，Bill 在编写程序时可能犯了几个错误。以下代码中有多少行包含编译错误？

```java
1: package bookworm;
2: import java.io.*;
3: import java.nio.file.*;
4: public class ReadEverything {
5: public void readFile(Path p) {
6:     try {
7:         Files.readAllLines(p)
8:         parallel()
9:         forEach(System.out::println);
10:    } catch (Exception e) {
11:    }
12: public void read(Path directory) throws Exception {
13:     Files.walk(directory)
14:     filter(p -> File.isRegularFile(p))
15:     forEach(x -> read(x));
16: }
17: } public static void main(String[] b) throws IOException {
18:     Path p = Path.get("collection");
19:     new ReadEverything().read(p);
20: }
```

- A. 无。Bill 的实现是正确的。
- B. 一个
- C. 两个
- D. 三
- E. 五

## 35. 在空白处填入可以编译且不产生异常的组合。（选择三个。）

```java
var x = new ArrayDeque<>();
x.offer(1);
x____;
```

- A. peek, peek
- B. peekFirst,Last
- C. poll, poll
- D. pop, remove
- E. remove,First

## 36. 以下代码的输出是什么？

```java
public class InitOrder {

    static {
        System.out.print("2");
    }

    public InitOrder() {
        System.out.print("3");
    }

    public static void callMe() {
        System.out.print("4");
    }

    public static void main(String[] args) {
        new InitOrder();
        callMe();
        System.out.print("5");
    }
}
```

- A. 2345
- B. 245
- C. 2345
- D. 2345

## 37. 以下哪些异常需要被处理或声明？（选择两个。）

- A. `FileNotFoundException`
- B. `ArithmeticException`
- C. `IOException`
- D. `IllegalArgumentException`
- E. `RuntimeException`
- F. `Exception`

## 38. 假设 FileNotFoundException 是 IOException 的子类，以下代码的输出是什么？

```java
package materials;

import java.io.*;

class CarbonStructure {
    protected long count;
    protected Long getCount() throws IOException { // q1
        return count;
    }
}

public class Diamond extends CarbonStructure {
    public Diamond(int count) { this.count = count; } // q2
    public static void main(String[] args) {
        try {
            CarbonStructure ring = new Diamond(15); // q3
            System.out.print(ring.getCount()); // q4
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

- A. null
- B. 15
- C. 第 q1 行无法编译。
- D. 第 q2 行无法编译。
- E. 第 q3 行无法编译。
- F. 第 q4 行无法编译。

## 39. 以下哪些是有效的 Locale 格式？（选择两个。）

- A. iw
- B. UA
- C. it_ch
- D. JA_JP
- E. th_TH
- F. ES_hn

## 40. 关于大多数模块化的步骤，哪些描述是正确的？（选择两个。）

- A. 自下向上迁移，自动模块变为命名模块。
- B. 自下向上迁移，命名模块变为自动模块。
- C. 自下向上迁移，未命名模块变为命名模块。
- D. 自上向下迁移，自动模块变为命名模块。
- E. 自上向下迁移，命名模块变为自动模块。
- F. 自上向下迁移，未命名模块变为自动模块。

## 41. 结果代码的结果是什么？

```java
import java.util.*;

public class Museums {
    public static void main(String[] args) {
        String[] array = {"Natural History", "Art"};
    }
}
```
