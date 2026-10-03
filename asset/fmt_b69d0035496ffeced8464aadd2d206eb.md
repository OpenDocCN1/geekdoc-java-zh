
## 9. 给定以下代码，在 P1 处可以访问多少个变量？

```java
static String weight = "A lot";

double ageMonths = 5, ageDays = 2;

private static boolean success = true;

public void compete() {

    final String retries = "1";

    // P1

}
```

| 变量类型 | 在 P1 处访问的变量数量 |
|---|---|
| 类 (Class) | |
| 实例 (Instance) | |
| 局部变量 (Local) | |

+ A. 2, 0, 1
+ B. 2, 2, 1
+ C. 1, 0, 2
+ D. 0, 2, 0
+ E. 2, 1, 1
+ F. 类无法编译。

## 10. 给定以下代码，按顺序插入空白行的哪些值可以使代码编译？（选择两项。）

```java
agent;

public ________ Banker {

    private static getMaxWithWithdrawal() {

        return 10;

    }

}
```

+ A. package, new, int
+ B. package, class, long
+ C. import, class, null
+ D. //, class, int
+ E. import, interface, void
+ F. package, class, void

## 11. 下面哪些是正确的？（选择两项。）

```java
public class Phone {

    private int size;

    // LINE X

    public static void sendHome(Phone p, int newSize) {

        p = new Phone(newSize);

        p.size = 4;

    }

    public static final void main(String... params) {

        final var phone = new Phone(3);

        sendHome(phone, 7);

        System.out.print(phone.size);

    }

}
```

### A. 在 LINE X 处插入此构造函数：

```java
public static Phone create(int size) {

    return new Phone(size);

}
```

### B. 在 LINE X 处插入此构造函数：

```java
public static Phone newInstance(int size) {

    return new Phone(size);

}
```

### C. 在 LINE X 处插入此构造函数：

```java
public Phone(int size) {

    size = this.size;

}
```

### D. 在 LINE X 处插入此构造函数：

```java
public void Phone(int size) {

    size = this.size;

}
```

+ E. 使用正确的构造函数，输出是 θ。
+ F. 使用正确的构造函数，输出是 3。
+ G. 使用正确的构造函数，输出是 7。

## 12. 给定以下类结构，哪些行可以独立地插入到空白处并使该类通过编译？（选择两项。）

```java
public class Dinosaur {

    class Pterodactyl extends Dinosaur {

        public void roar() {

            var dino = new Dinosaur();

        }

    }

}
```

+ A. `dino.Pterodactyl()`
+ B. `Dinosaur.new Pterodactyl()`
+ C. `dino.new Pterodactyl()`
+ D. `new Dino().new Pterodactyl()`
+ E. `new Dinosaur().Pterodactyl()`
+ F. `new Dinosaur.Pterodactyl()`

## 13. 该计算机程序的输出是什么？

```java
class Laptop extends Computer {

    public void startup() {

        System.out.print("laptop-");

    }

}

public class Computer {

    public void startup() {

        System.out.print("computer-");

    }

    public static void main(String[] args) {

        Computer computer = new Laptop();

        Laptop laptop = new Laptop();

        computer.startup();

        laptop.startup();

    }

}
```

+ A. computer-laptop
+ B. laptop-computer-
+ C. laptop-laptop-
+ D. 代码无法编译。
+ E. 以上都不是。

## 14. 以下代码输出了多少行内容？

```java
public class Cars {

    private static void drive() {

        {

            System.out.println("zoom");

        }

        System.out.println("fast");

    }

    static { System.out.println("faster"); }

    public static void main(String[] args) {

        drive();

        drive();

    }

}
```

+ A. 一行
+ B. 两行
+ C. 三行
+ D. 四行
+ E. 五行
+ F. 六行或更多
+ G. 以上都不是。代码无法编译。

## 15. 关于静态接口方法的陈述哪些是正确的？（选择三项。）

+ A. 静态接口方法可以是 `final` 的。
+ B. 静态接口方法可以声明为 `private`。
+ C. 静态接口方法可以声明为包级访问（package access）。
+ D. 静态接口方法可以声明为 `public`。
+ E. 静态接口方法可以声明为 `protected`。
+ F. 静态接口方法可以在不使用访问修饰符的情况下声明。

## 16. 不计算 `Planet` 的声明，有多少个声明可以通过编译？假设它们都声明在同一个 `.java` 文件中。

```java
public abstract sealed class Planet permits Mercury, Venus, Earth {}

non-sealed class Venus {}

non-sealed class Mars extends Planet {}

non-sealed class Mercury {}

abstract
```

+ A. 零
+ B. 一个
+ C. 两个
+ D. 三
+ E. 四

## 17. 执行以下代码的结果如何？

```java
class Canine {

    public String woof(int bark) {

        return "1";

    }

    public String woof(Integer bark) {

        return "2";

    }

    public String woof(Object bark) {

        return "3";

    }

    public static void main(String[] args) {

        System.out.println(woof((short)5));

    }

}
```

+ A. 15
+ B. 25
+ C. 35
+ D. One
+ E. Two
+ F. 代码无法编译。

## 18. 关于 `final` 的描述正确？

+ A. 局部变量是 `final`。
+ B. 静态变量是 `final`。
+ C. 引用在初始化后不可更改。
+ D. 引用在赋值后不可更改。
+ E. 以上都不是。

## 19. `Turnip` 类的输出是什么？

```java
interface GameItem {

    int sell();

}

abstract class Vegetable implements GameItem {

    public int sell() { return 5; }

}

public class Turnip extends Vegetable {

    public int sell() { return 3; }

    public static void main(String[] args) {

        System.out.print(new Turnip().sell());

    }

}
```

+ A. 3
+ B. 5
+ C. 代码无法编译。
+ D. 代码编译但在运行时抛出异常。
+ E. 以上都不是。

## 20. 以下代码的输出是什么？

```java
package holiday;

enum DaysOff {

    Thanksgiving, PresidentsDay, ValentinesDay

}

public class Vacation {

    public static void main(String[] args) {

        final DaysOff input = DaysOff.Thanksgiving;

        switch(input) {

            default:

            case ValentinesDay:

                System.out.print("1");

            case DaysOff.PresidentsDay:

                System.out.print("2");

        }

    }

}
```

+ A. 1
+ B. 2
+ C. 12
+ D. 代码无法编译。
+ E. 代码编译但在运行时抛出异常。
+ F. 以上都不是。

## 21. 以下程序的输出是什么？

```java
record Animal(boolean isMammal) {}

record Panda(String name) extends Animal {

    public Panda() {

        this(true);

    }

    public Panda {

        name = name.toLowerCase();

    }

    public static void main(String[] args) {

        System.out.print(new Panda().name());

    }

}
```

+ A. TaiShan
+ B. taishan
+ C. 程序需要修改一行才能编译。
+ D. 程序需要修改两行才能编译。
+ E. 程序需要修改三或更多行才能编译。
+ F. 代码编译但打印异常。

## 22. 关于实例关键字的哪些是正确的？（选择两项。）

+ A. `that` 关键字可以读取直接父类的公共成员。
+ B. `this` 关键字可以读取类中声明的所有成员。
+ C. `super` 关键字可以读取父类中声明的所有成员成员。
+ D. `that` 关键字可以读取另一个类的成员。
+ E. `this` 关键字可以读取直接父类的公共成员。
+ F. `super` 关键字可以在静态方法中使用。

## 23. 填充空白：类 ________ 接口并 ________ 抽象类。________ 另一个接口。

+ A. extends, extends, implements
+ B. extends, implements, extends
+ C. extends, implements, extends
+ D. implements, extends, extends
+ E. implements, extends, implements
+ F. implements, implements, extends

## 24. 假设你有以下代码。在 `main` 方法结束之前，哪些图像最代表引用 `c1`、`c2` 和 `c3` 的状态，假设垃圾回收尚未运行？每个框代表一个具有数量鸡蛋的鸡对象。

```java
public class Chicken {

    private Integer eggs = 2;

    { this.eggs = 3; }

    public Chicken(int eggs) {

        this.eggs = eggs;

    }

    public static void main(String[] r) {

        var c1 = new Chicken(1);

        var c2 = new Chicken(2);

        var c3 = new Chicken(3);

        c1.eggs = c2.eggs;

        c2 = c1;

        c3.eggs = null;

    }

}
```

## 选项 A

## 选项 B

![](img/e0249ee409e157651f035d8c59357695_84_0.png)

## 选项 C

## 选项 D

![](img/e0249ee409e157651f035d8c59357695_84_1.png)

+ A. 选项 A
+ B. 选项 B
+ C. 选项 C
+ D. 选项 D
+ E. 代码无法编译。
+ F. 以上都不是。

## 25. 下面应用程序的输出结果是什么？

```java
package musical;

interface Speak { default int talk() { return 7; } }

interface Sing { default int talk() { return 5; } }

public class Performance implements Speak, Sing {

    public int talk(String... x) {

        return x.length;

    }

    public static void main(String[] notes) {

        System.out.print(new Performance().talk());

    }

}
```

+ A. 7
+ B. 5
+ C. 代码无法编译。
+ D. 代码可以正常编译，但在运行时之前无法确定输出。
+ E. 以上都不是。

## 26. 下面应用程序的输出结果是什么？

```java
package ai;

interface Pump { public abstract String toString(); }

interface Bend extends Pump { void bend(double tensileStrength); }

public class Robot {

    public static final void apply(Bend instruction, double input) {

        instruction.bend(input);

    }

    public static void main(String... future) {

        final Robot r = new Robot();

        r.apply(x -> System.out.print(x+" bent!"), 5);

    }

}
```

+ A. 5 bent!
+ B. 5.0 bent!
+ C. 代码无法编译，因为 `Bend` 不是一个函数式接口。
+ D. 代码无法编译，因为 `apply()` 的声明。
+ E. 以上都不是。

## 27. 关于提供最广泛允许访问的同时进行封装，哪种说法是正确的？

+ A. 变量是私有的，方法也是私有的。
+ B. 变量是私有的，方法是公共的。
+ C. 变量是公共的，方法是私有的。
+ D. 变量都是公共的。
+ E. 变量是私有的，方法是保护的。
+ F. 以上都不是。

## 28. 填空：________ 意味着对象的状态不能改变，而 ________ 意味着它可以改变。

+ A. 封装，工厂方法
+ B. 不变性，可变性
+ C. 刚性，灵活性
+ D. 静态，实例
+ E. 紧耦合，松耦合
+ F. 以上都不是

## 29. 关于以下接口的哪种说法正确？

```java
public interface Swimming {

    String DEFAULT = "Diving"; // k1

    abstract int breath();

    private static void stroke() {

        if(breath()==1) { // k2

            System.out.print("Go!");

        } else {

            System.out.print(dive()); // k3

        }

    }

    static String dive() {

        return DEFAULT; // k4

    }

}
```
