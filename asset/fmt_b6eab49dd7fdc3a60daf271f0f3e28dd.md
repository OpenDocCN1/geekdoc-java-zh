
*(注：原文中注释符号包含乱码，按原样翻译)*

- A. `/** Insert next */`
- B. `/* Find */`
- C. `// Is this bug?`
- D. `$ Begin method()`
- F. `# Updated code by Patti`

### 4. 假设 pandas 表有一行 name Mei Xiang 且 location DC。以下代码输出什么？

```java
import java.sql.*;

var url = "jdbc:hsqdb:file:mammals";

var sql = "SELECT name FROM pandas WHERE location = ?";

try (var conn = DriverManager.getConnection(url)) {
    var stmt = conn.prepareStatement(sql); // s1
    stmt.setString(1, "DC");
    var rs = stmt.executeQuery();
    if (rs.next()) {
        System.out.println(rs.getString("name")); // s2
    } else
        System.out.println("No match");
}
```

- A. Xiang
- B. No match
- C. s1 处的代码无法编译。
- D. s2 处的代码无法编译。
- E. 其他行无法编译。
- F. 运行时抛出异常。

### 5. 以下代码打印什么？

```java
// Hare.java
package com.animal;

public class Hare {
    void init() {
        System.out.print("init");
    }

    protected void race() {
        System.out.print("hare");
    }
}

// Tortoise.java
package com.animal;

public class Tortoise {
    protected void race(Hare hare) {
        hare.init(); // x1
        hare.race(); // x2
        System.out.print("tortoise-");
    }

    public static void main(String[] args) {
        var tortoise = new Tortoise();
        var hare = new Hare();
        tortoise.race(hare);
    }
}
```

- A. init-hare-tortoise
- B. init-hare
- C. x1 处的行有编译错误。
- D. x2 处的行有编译错误。
- E. 其他行无法编译。
- F. 运行时抛出异常。

### 6. 以下哪些 Lambda 表达式可以传递给接收 `IntUnaryOperator` 参数的方法？（选择三个）

```java
v -> {System.out.print("Hello!"); return 2%1;}
(Integer w) -> w.intValue()
(int j) -> (int) 30L
(int q) -> q / 3.1
(long x) -> (int) x
z -> z
```

- A. `v -> {System.out.print("Hello!"); return 2%1;}`
- B. `(Integer w) -> w.intValue()`
- C. `(int j) -> (int) 30L`
- D. `(int q) -> q / 3.1`
- E. `(long x) -> (int) x`
- F. `z -> z`

### 7. 以下哪个是 Java 中合法的方法名？（选择两个）

- A. `____`
- B. `%run`
- C. `check-Activity`
- D. `Hum2`
- E. `sing`
- F. `put`

### 8. 关于此模块声明，以下哪项是正确的？

```java
1: module com.mammal {
2: exports com.mammal.cat;
3: exports com.mammal.mouse to com.mice;
4: uses com.animal;
5: }
```

- A. 第一个编译失败行是第 1 行。
- B. 第一个编译失败行是第 2 行。
- C. 第一个编译失败行是第 3 行。
- D. 第一个编译失败行是第 4 行。
- E. 代码编译通过。

### 9. 需要编译多少行？

```java
class Roller<E extends Wheel> {
    public void roll(E e) { }
}

class Wheel { }

class CartWheel extends Wheel { }
```

```java
public class RollingContest {
    Roller<CartWheel> wheel1 = new Roller<CartWheel>();
    Roller<Wheel> wheel2 = new Roller<Wheel>();
    Roller<?? extends Wheel> wheel3 = new Roller<CartWheel>();
    Roller<?? extends Wheel> wheel4 = new Roller<Wheel>();
    Roller<?? super Wheel> wheel5 = new Roller<CartWheel>();
    Roller<?? super Wheel> wheel6 = new Roller<Wheel>();
}
```

- A. 一行
- B. 两行
- C. 三行
- D. 四行
- E. 五行
- F. 六行

### 10. 给定以下内容，关于 `First` 的子类型 `Chicken` 和 `Egg`，我们可以推断出什么？（选择两个。）

```java
public sealed interface First permits Chicken, Egg { }
```

- A. `Chicken` 和 `Egg` 必须是接口。
- B. `Chicken` 和 `Egg` 可以是类或接口。
- C. `Chicken` 和 `Egg` 必须位于 `First` 以外的文件。
- D. `Chicken` 和 `Egg` 必须与 `First` 位于同一个文件中。
- E. `Chicken` 和 `Egg` 必须作为 `First` 的嵌套类存在。
- F. `Chicken` 和 `Egg` 可能与 `First` 位于同一个文件中，也可能位于不同的文件中。

### 11. 下列代码的输出是什么？

```java
var listing = new String[][] { { "Book", "34.99" },
    {"Game", "29.99"}, { "Pen", ".99" } };
System.out.println(listing.length + " " + listing[0].length);
```

- A. 2 2
- B. 2 3
- C. 3 2
- D. 3 3
- E. 代码无法编译。
- F. 代码编译但在运行时抛出异常。

### 12. 下列代码的作用是什么？

```java
public class Player {
    interface Basket {
        boolean needAim(double angle);
    }

    static void prepare(double angle, Basket t) {
        boolean ready = t.needToAim(angle); // k1
        System.out.println(ready);
    }

    public static void main(String[] args) {
        prepare(45, d -> d > 5 || d < -5); // k2
    }
}
```

- A. 它打印 true。
- B. 它打印 false。
- C. 由于第 k1 行导致无法编译。
- D. 由于第 k2 行导致无法编译。
- E. 由于其他行导致无法编译。

### 13. `ServiceLocator.load(ChocolateLab.class)` 返回什么？

- A. `Collection`
- B. `List`
- C. `Stream`
- D. 以上都不是

### 14. 当作为 `java EchoFirst.java seed flower plant` 运行时，以下代码的输出是什么？

```java
import java.util.*;

public class EchoFirst {
    public static void main(String[] args) {
        var result = Arrays.binarySearch(args, args[0]);
        System.out.println(result);
    }
}
```

- A. 0
- B. 1
- C. 2
- D. 代码无法编译。
- E. 代码编译但在运行时抛出异常。
- F. 输出不保证。

### 15. 哪项是模块的一部分并具有 `requires` 指令？

- A. Consumer
- B. Service locator（服务定位器）
- C. Service provider（服务提供者）
- D. Service interface（服务接口）
- E. 以上都不是

### 16. 从 `DoubleOperator` 开始向下填充表格中的值。签名指的是与每个函数式接口关联的抽象方法。

| 函数式接口 | 方法签名中的参数 |
|---|---|
| `DoubleOperator` | |
| `LongToIntFunction` | |
| `ToLongFunction` | |
| `IntSupplier` | |
| `ObjLongConsumer` | |

- A. 1, 0, 0, 2
- B. 1, 2, 1, 0
- C. 2, 1, 0, 2
- D. 2, 1, 1, 0
- E. 2, 1, 2, 0
- F. 3, 0, 2, 1

### 17. 下列代码的结果是什么？

```java
import java.time.*;
import java.time.format.*;

public class PiDay {
    public static void main(String[] args) {
        LocalDateTime pi = LocalDateTime.of(2022, 3, 14, 59);
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("m.ddHMM");
        System.out.print(formatter.format(pi));
    }
}
```

- A. 3.14059
- B. 3.14MM
- C. 591403
- D. 5901MM
- E. 以上都不是

### 18. 假设 cats 是一个空表。代码执行完成后，表中有多少行？

```java
try (var conn = DriverManager.getConnection(url)) {
    conn.setAutoCommit(false);
    String insert = "INSERT INTO cats VALUES (?, ?)";
    var sp1 = conn.setSavepoint();
    try (var stmt = conn.prepareStatement(insert)) {
        stmt.setInt(1, 1);
        stmt.setString(2, "Kitty");
        stmt.executeUpdate();
    }
    var sp2 = conn.setSavepoint();
    conn.rollback(sp1);
    try (var stmt = conn.prepareStatement(insert)) {
        stmt.setInt(1, 2);
        stmt.setString(2, "Beverly");
        stmt.executeUpdate();
    }
    conn.rollback(sp2);
    conn.commit();
}
```

- A. 零
- B. 一行
- C. 两行
- D. 代码无法编译。
- E. 代码抛出异常。

### 19. 给定的类结构，在 `bake()` 方法内部创建 `Spinner` 实例哪些方式是有效的？（选择三个。）

```java
public class Kitchen {
    class Mixer {
        class Spinner {
            public void bake() {
                // 在此处插入代码
            }
        }
    }
}
```

- A. `var a = new Kitchen().new Mixer().new Spinner();`
- B. `Mixer.Spinner b = Mixer.new Spinner();`
- C. `var c = new Spinner();`
- D. `var d = new Mixer().new Spinner();`
- E. `Kitchen.Mixer.Spinner e = new Kitchen().new Mixer().new Spinner();`
- F. `Spinner f = new Kitchen().new Mixer().new Spinner();`

### 20. 哪些行可以删除既不影响编译又能保持相同的输出？（选择三个。）

```java
String race = ""
outer:
do {
    inner:
    do {
        race += "x"
    } while (race.length() <= 4);
} while (race.length() < 4);
System.out.println(race);
```

- A. 第 15 行和第 17 行
- B. 第 16 行和第 23 行
- C. 第 17 行、第 18 行和第 22 行
- D. 第 17 行
- E. 第 23 行
- F. 第 23 行

### 21. 这些模块声明中有几个是有效的？

```java
module com.apple { exports com.apple; }
module com.4apple { requires com.apple; }
module com.apple4 { declares com.apple; }
module com.apple-four { }
module com.apple$ { }
```

- A. 零
- B. 一个
- C. 两个
- D. 三个
- E. 四个
- F. 五个

### 22. 假设编译时使用了 `-g:vars` 以包含调试信息，以下代码段的输出是什么？

```java
Double tea = null;
Object coffee = (Integer)null;
String juice = "";
if(coffee instanceof Integer x) {
    System.out.println(x.intValue());
} else if (tea < juice.length()) {
    System.out.println(tea);
}
```

- A. 栈跟踪中指向 `tea` 的 `NullPointerException`
- B. 栈跟踪中指向 `coffee` 的 `NullPointerException`
- C. 栈跟踪中指向 `juice` 的 `NullPointerException`
- D. 栈跟踪中指向 `tea` 和 `coffee` 的 `NullPointerException`
- E. 以上都不是

### 23. 为了打破循环依赖，最少需要移除多少 `requires` 指令？

```java
module com.animal {
    exports com.animal;
    requires com.plant;
}

module com.plant {
    exports com.plant;
    requires com.animal;
}

module com.worm {
    exports com.worm;
    requires com.animal;
    requires com.plant;
}

module com.hedgehog {
    exports com.hedgehog;
    requires com.animal;
    requires com.plant;
}
```

- A. 无需，因为没有循环依赖
- B. 1
- C. 2
- D. 4

### 24. 以下哪些 lambda 表达式可以插入到两个空白处并仍允许应用程序编译？（选择三个。）

```java
package spooky;
```
