
- A. 仅 line x
- B. 仅 line y
- C. line x 和 y 都是
- D. 代码可以编译。

- 12. 在 `javac` 命令中，哪些选项名称与 `-p` 和 `-cp` 等效？（选择两个.）
- A. `--module-path` 和 `-classpath`
- B. `--module-path` 和 `-class-path`
- C. `--module-path` 和 `--class-path`
- D. `--path` 和 `-classpath`
- E. `--path` 和 `--class-path`
- F. `--path` 和 `--class-path`

- 13. 要使此方法通过编译，最少需要修改或删除几行？

```java
11: public void colors() {
12:     var yellow = "";
13:     yellow = null;
14:
15:     var red = null;
16:
17:     var blue = """
18: blue = 1;
19:
20:     var var = "";
21:     var = "";
22:
23:     var pink = 1;
24: }
```

- A. 零
- B. 一
- C. 两
- D. 三
- E. 四
- F. 五

- 14. 下述程序的输出是什么？

```java
package ballroom;

public class Dance {

    public static void swing(int... beats)
        throws ClassCastException {

        try {
            System.out.print("1" + beats[2]); // p1
        } catch (RuntimeException e) {
            System.out.print("2");
        } catch (Exception e) {
            System.out.print("3");
        } finally {
            System.out.print("4");
        }
    }

    public static void main(String[] music) {
        new Dance().swing(0,0); // p2
        System.out.print("5");
    }
}
```

- A. 145
- B. 1045
- C. 24，随后是堆栈跟踪信息
- D. 245
- E. 代码因为 line p1 无法编译。
- F. 代码因为 line p2 无法编译。

- 15. 下述程序的输出是什么？

```java
1:   interface HasHue {String getHue()};
2:   enum COLORS implements HasHue {
3:     red {
4:       public String getHue() { return "FF0000";}
5:     }, green {
6:       public String getHue() { return "00FF00";}
7:     }, blue {
8:       public String getHue() { return "0000FF";}
9:     }
10:  private COLORS() {}
11: }
12: class Book {
13:   static void main(String[] pencils) {
14:   }
15:   final public class ColoringBook extends Book {
16:   final void paint(COLORS c) {
17:     System.out.print("Painting: " + c.getHue());
18:   }
19:   final static void main(String[] crayons) {
20:     new ColoringBook().paint(green);
21:   }}
```

- A. Painting: 00FF00
- B. 恰好有一行代码无法编译。
- C. 恰好有行代码无法编译。
- D. 三或更多代码无法编译。
- E. 代码可以编译但在运行时抛出异常。
- F. 以上都不是。

- 16. 对于返回匹配行计数的 SQL 查询，以下哪些方法可以无错误地运行？

```java
private static void choices(PreparedStatement ps,
  String sql) throws SQLException {
  try (var rs = ps.executeQuery()) {
    System.out.println(rs.getInt(1));
  }
}
```

```java
private static void moreChoices(PreparedStatement ps,
  String sql throws SQLException {
  try (var rs = ps.executeQuery()) {
    rs.next();
    System.out.println(rs.getInt(1));
  }
}
```

```java
private static void stillChoices(PreparedStatement ps,
  String sql throws SQLException {
  try (var rs = ps.executeQuery()) {
    if (rs.next()) {
      System.out.println(rs.getInt(1));
    }
  }
}
```

- A. `moreChoices()`
- B. `stillMoreChoices()`
- C. `choices()` and `stillMoreChoices()`
- D. `moreChoices()` and `stillMoreChoices()`
- E. 所有三个方法
- F. 以上都不是

- 17. 在美国大部分地区，夏令时间于 11 月 6 日 02:00 结束，我们会重复那个小时。以下代码的输出是什么？

```java
var locals = LocalDate.of(2022, NOVEMBER, 6);
var localTime = LocalTime.of(1, 0);
var zone = ZoneId.of("America/New_York");
var z = ZonedDateTime.of(locals, localTime, zone);
var offset = z.getOffset();
for (int i = 0; i < 6; i++) {
  z = z.plusHours(1);
}
System.out.print(z.getHour() + " " + offset.equals(z));
```

- A. 5 false
- B. 5 true
- C. 6 false
- D. 6 true
- E. 7 false
- F. 7 true
- G. 代码无法编译。
- H. 代码编译但在运行时抛出异常。

- 18. 程序的输出是什么？

```java
package physics;

class Wave {
    public int size = 7;
}

public class Light extends Wave {
    public int size = 5;
    public static void main(String[] args) {
        Light v1 = new Light();
        Light v2 = new Light();
        Wave v3 = new Light();
        System.out.println(v1.size + "," + v2.size + "," + v3.size);
    }
}
```

- A. 5,5,5
- B. 5,5,7
- C. 7,7,7
- D. 7,7,7
- E. 代码无法编译。
- F. 以上都不是。

- 19. 假设有一个名为 `update_data` 的存储过程，它有一个名为 的 IN 参数。填写空白使代码正常运行？

```java
String sql = "{call update_data(?)}";
try (Connection conn = DriverManager.getConnection(url);
     CallableStatement cs = conn.prepareCall(sql)) {
    cs.________________(1, 6);
    var rs = cs.execute();
}
```

- A. `registerInParameter`
- B. `registerIntParameter`
- C. `registerInputParameter`
- D. `setIn`
- E. `setInteger`
- F. 以上都不是

- 20. 此代码可能的输出是什么？（选择两个。）

```java
import java.time.LocalDate;

public class Animal {
    private record Baby(String name, LocalDate birth) {}
    public static void main(String[] args) {
        LocalDate now = LocalDate.now();
        var b1 = new Baby("Teddy", now);
        var b2 = new Baby("Teddy", now);
        System.out.println((b1 == b2) + " " + b1.equals(b2));
        System.out.println(b1);
    }
}
```

- A. false false
- B. false true
- C. true false
- D. true true
- E. Baby[name=Teddy, birth=2022-05-21]
- F. Baby@1deb93

- 21. 调用此方法的输出是什么？

```java
public void countPets() {
    record Pet(int age) {}
    record PetSummary(long count, int sum) {}
    var summary = Stream.of(new Pet(2), new Pet(5), new Pet(8))
        .collect(Collectors.teeing(
            Collectors.counting(),
            Collectors.summingInt(Pet::age),
            (count, sum) -> new PetSummary(count, sum)));
    System.out.println(summary);
}
```

- A. PetSummary[count=1, sum=3]
- B. PetSummary[count=1, sum=15]
- C. PetSummary[count=3, sum=3]
- D. PetSummary[count=3, sum=15]
- E. 因为调用 `teeing()` 代码无法编译。
- F. 因为 record 定义在方法内部代码无法编译。
- G. 因为其他原因代码无法编译。

- 22. 根据以下，关于 `First` 的子类型 `Chicken` 和 `Egg` 可以推断出什么？（选择两个）。

```java
public sealed class First { }
```

- A. `Chicken` 和 `Egg` 必须是类。
- B. `Chicken` 和 `Egg` 可以是类、接口、枚举或记录类（record）。
- C. `Chicken` 和 `Egg` 必须位于 `First` 之外的文件中。
- D. `Chicken` 和 `Egg` 必须位于 `First` 相同的文件中。
- E. `Chicken` 和 `Egg` 必须作为 `First` 的嵌套类存在。
- F. `Chicken` 和 `Egg` 可能位于与 `First` 相同的文件或不同的文件中。

- 23. 关于 try/catch 块的以下哪些是正确的？（选择两个。）

- A. catch 块永远不会出现在 finally 块之后。
- B. try 块必须跟着一个 catch 块。
- C. finally 块永远不会出现在 catch 块之后。
- D. try 块必须跟着一个 finally块。
- E. try 块可以有零或多个 catch 块。
- F. try 块可以有多个一个 finally 块。

- 24. 编译并执行下述程序的运行是什么？

```java
package reptile;

public class Alligator {
    static int teeth;
    double scaleToughness;
    public Alligator() {
        this.teeth++;
    }
    public void snap(int teeth) {
        System.out.print(teeth+" ");
        teeth--;
    }
    public static void main(String[] unused) {
        new Alligator().snap(teeth);
        new Alligator().snap(teeth);
    }
}
```

- A. 0 1
- B. 1 1
- C. 1 2
- D. 2 2
- E. 代码无法编译。
- F. 代码编译但在运行时抛出异常。
- G. 无法提前确定答案。

- 25. 填写空白使此代码通过编译：

```java
String cheese = ServiceLoader.stream(Mouse.class)
  .map(__)
  .map(Mouse::favoriteFood)
  .findFirst()
  .orElse("");
```

- A. `Mouse.get()`
- B. `Mouse::get`
- C. `Provider.get()`
- D. `Provider::get`
- E. 以上均不允许

- 26. 哪几行可以填入空白处使代码编译？（选择两项。）

```java
abstract public class Exam {
    boolean pass;
    protected abstract boolean passed();
    class JavaProgrammerCert extends Exam {
        private Exam part1;
        private Exam part2;
    }
}
```

+ A.

```java
boolean passed() {
    return part1.pass && part2.pass;
}
```

+ B.

```java
boolean passed() {
    return part1.passed() && part2.passed();
}
```

+ C.

```java
private boolean passed() {
    return super.passed();
}
```

+ D.

```java
public boolean passed() {
    return part1.passed() && part2.passed();
}
```

+ E.

```java
public boolean passed() {
    return part1.pass && part2.pass;
}
```

+ F.

```java
public boolean passed() {
    return super.passed();
}
```
