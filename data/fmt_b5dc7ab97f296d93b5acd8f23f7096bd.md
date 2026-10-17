
## Java 代码片段

```java
private void buryBone() { chaseTail(); }

private static void wagTail() { chaseTail(); }

public default String chaseTail() { return "So cute!"; }

}

public class Puppy implements Dog {

    public String chaseTail() throws IllegalArgumentException {

        throw new IllegalArgumentException("Too little!");

    }

    public static void main(String[] t) {

        var p = new Puppy();

        System.out.print(p.chaseTail());

    }

}
```

- A. So cute!
- B. 抛出了带有 Too little! 信息的异常。
- C. 不同的异常。
- D. 因为 `Puppy` 类中没有 `buryBone()`，代码无法通过编译。
- E. 因为 `Puppy` 类中没有 `chaseTail()`，代码无法通过编译。
- F. 以上皆非。

## 01. 如何在某一点强制进行垃圾回收？

- A. 调用 `System.forceGc()`
- B. 调用 `System.gc()`
- C. 调用 `System.requireGc()`
- D. 调用 `GarbageCollection.clean()`
- E. 以上皆非

## 02. 对以下类进行什么修改有助于正确封装数据？

```java
package shield;

public class Protect {

    private String material;

    protected int strength;

    public int getStrength() {

        return strength;

    }

    public void setStrength(int strength) {

        this.strength = strength;

    }

}
```

- A. 为 `material` 添加 getter。
- B. 为 `material` 添加 setter。
- C. 将 `material` 的访问修饰符改为 `protected`。
- D. 将 `strength` 的访问修饰符改为 `private`。
- E. 以上皆非。

## 03. 关于 lambda 的哪些说法是正确的？（选择两个）

- A. 实例变量可以使用，无论它们是否为 final。
- B. 实例变量和局部变量可以使用，无论它们是否为 final。
- C. 实例变量和方法参数必须是 final 才能使用。
- D. 局部变量和方法参数必须是 final 才能使用。
- E. 局部变量和静态变量可以使用，无论它们是否为 final。
- F. 方法参数和静态变量可以使用，无论它们是否为 final。

## 04. 关于以下类的哪个陈述是正确的？

```java
import java.util.*;

final class Faucet {

    private String water;

    private List<Double> pipes;

    public Faucet(String water, List<Double> pipes) {

        this.water = water;

        this.pipes = pipes;

    }

    public String get() { return water; }

    public List<Double> getPipes() { return pipes; }

}
```

```java
final class Spout {

    private String well;

    private List<Boolean> buckets;

    public Spout(String well, List<Boolean> buckets) {

        this.well = well;

        this.buckets = new ArrayList<>(buckets);

    }

    public String getWell() { return well; }

    public List<Boolean> getBuckets() {

        return new ArrayList<>(buckets);

    }

}
```

- A. 只有 `Faucet` 是不可变的。
- B. 只有 `Spout` 是不可变的。
- C. 两个类都是不可变的。
- D. 两个类都不是不可变的。
- E. 以上皆非，其中一个类无法通过编译。

## 05. 给定以下结构，哪些代码段的结果为真？（选择三个）

```java
interface Friendly {

    abstract class Dolphin implements Friendly {}

    class Animal implements Friendly {}

    class Whale extends Object {}

    class Fish {}

    class Coral extends Animal {}

}
```

- A. `new Coral instanceof Friendly`
- B. `null instanceof Object`
- C. `new Coral instanceof Object`
- D. `new Fish() instanceof Friendly`
- E. `new Whale() instanceof Object`
- F. `new Dolphin() instanceof Friendly`

## 06. 关于以下代码，什么是正确的？

```java
public class Eggs {

    enum Animal {

        CHICKEN(21), PENGIN(75);

        private int numDays;

        private Animal(int numDays) {

            this.numDays = numDays;

        }

        public int getNumDays() {

            return numDays;

        }

        public void setNumDays(int numDays) {

            this.numDays = numDays;

        }

    }

    public static void main(String[] args) {

        Animal chicken = Animal.CHICKEN;

        chicken.setNumDays(20);

        System.out.print(chicken.getNumDays());

        System.out.print(" ");

        System.out.print(Animal.CHICKEN.getNumDays());

        System.out.print(" ");

        System.out.print(Animal.PENGIN.getNumDays());

    }

}
```

- A. 它输出 20 20 20。
- B. 它输出 20 20 75。
- C. 它输出 20 21 75。
- D. 它输出 21 21 75。
- E. 由于 `setDays()` 无法通过编译。
- F. 由于其他原因无法通过编译。

## 07. 该接口中第一行无法通过编译的是哪一行？

```java
1: public interface Thunderstorm {

2:     float rain = 1;

3:     char getSeason() { return 'W'; };

4:     boolean isWet();

5:     private static void hail() {}

6:     default String location() { return "Home"; };

7:     private static int getTemp() { return 35; }

8: }
```

- A. 第 2 行
- B. 第 3 行
- C. 第 4 行
- D. 第 5 行
- E. 第 6 行
- F. 第 7 行
- G. 所有行均通过编译

## 08. 下一个应用程序的输出是什么？

```java
package Currency;

enum Currency { DOLLAR, YEN, EURO }

abstract class Provider {

    protected Currency c = Currency.EURO;

}

public class Bank extends Provider {

    protected Currency c = Currency.DOLLAR;

    public static void main(String[] pennies) {

        int value = 0;

        switch(new Bank().c) {

            case 0:

                value--; break;

            case 1:

                value++; break;

        }

        System.out.print(value);

    }

}
```

- A. -1
- B. 0
- C. 1
- D. `Provider` 类无法通过编译。
- E. `Bank` 类无法通过编译。
- F. 以上皆非。

## 09. 哪些内容可以在 record 中声明？（选择两个）

- A. `hashCode()` 的实现
- B. 实例变量
- C. 静态初始化器
- D. 嵌套类
- E. 静态方法
- F. 构造函数
- G. 实例初始化器

## 10. `var q = 4.0f` 等价于哪个？

- A. `float q = 4.0f;`
- B. `Float q = 4.0f;`
- C. `double q = 4.0f;`
- D. `Double q = 4.0f;`
- E. `Object q = 4.0f;`

## 111. 填空：类可以自动赋值给一个 __________ 引用变量，但在赋值给一个 __________ 引用变量时，需要显式的类型转换。

- A. 子类，外层类
- B. 父类，子类
- C. 具类，子类
- D. 子类，父类
- E. 抽象类，静态类

## 112. 关于函数式接口（functional interfaces），以下哪个陈述是无效的？

- A. 函数式接口可以有任意数量的静态方法。
- B. 函数式接口可以有任意数量的默认方法（default methods）。
- C. 函数式接口可以有任意数量的私有静态方法。
- D. 函数式接口可以有任意数量的抽象方法。
- E. 函数式接口可以有任意数量的私有方法。
- F. 以上全部。

## 113. 假设第 x 行的注释可以替换为任意代码，以下代码可能的输出是什么？

```java
// Mandrill.java
public class Mandrill {

  public int age;

  public Mandrill(int age) {

    this.age = age;

  }

  public String toString() {

    return "" + age;

  }

}
```

```java
// PrintAge.java
public class PrintAge {

    public static void main(String[] args) {

        var mandrill = new Mandrill(5);

        // line X

        System.out.println(mandrill);

    }

}
```

- B. 5
- C. null 或 5
- D. 任意 int 值
- E. 无法编译

## 114. 在 main() 方法结束前夕，有多少个 String 对象可以被垃圾回收？

```java
public static void main(String ohMy) {

    String animal1 = new String("lion");

    String animal2 = new String("tiger");

    String animal3 = new String("bear");

    animal3 = animal1;

    animal2 = animal3;

    animal1 = animal2;

}
```

- A. 否
- B. 一个
- C. 两个
- D. 三个
- E. 以上都不是

## 115. 假设 `Panther` 和 `Cub` 是接口，且它们都不包含任何默认方法。哪些陈述是正确的？（选择两个。）

![](img/e0249ee409e157651f035d8c59357695_128_0.png)

- A. 如果 `Panther` 有一个抽象方法，则 `Cub` 保证是一个函数式接口。
- B. 如果 `Panther` 有一个抽象方法，则 `Cub` 可能是一个函数式接口。
- C. 如果 `Panther` 有一个抽象方法，则 `Cub` 不可能是函数式接口。
- D. 如果 `Panther` 有两个抽象方法，则 `Cub` 保证是一个函数式接口。
- E. 如果 `Panther` 有两个抽象方法，则 `Cub` 可能是一个函数式接口。
- F. 如果 `Panther` 有两个抽象方法，则 `Cub` 不可能是函数式接口。

## 116. 下面输出是什么？

```java
1: public class InitOrder {

2: public String first = "instance";

3: public InitOrder() {

4:     first = "constructor";

5: }

6: { first = "block"; }

7: public void print() {

8:     System.out.println(first);

9: }

10: public static void main(String... args) {

11:    new InitOrder().print();

12: } }
```

- A. block
- B. constructor
- C. instance
- D. 代码无法编译。
- E. 以上都不是。

## 117. 关于以下接口，哪个陈述是正确的？

```java
public interface Tree {

    public static void produceSap() {

        growLeaves();

    }

    public abstract int getNumberOfRings() {

        return getRings();

    }

    private static void growLeaves() {

    }

    private static int getRings() {

        return 10;

    }

}
```

- A. 代码可以编译。
- B. `produceSap()` 方法无法编译。
- C. `getNumberOfRings()` 方法无法编译。
- D. `growLeaves()` 方法无法编译。
- E. `getHeight()` 方法无法编译。
- F. 代码因循环无法编译。

## 118. 关于类型为 `var` 的变量，哪些陈述是正确的？（选择两个。）

- A. 变量可以在初始化时赋值为 null。
- B. 变量可以在初始化后赋值为 null。
- C. 变量永远无法赋值为 null。
- D. 变量只能用于基本类型。
- E. 变量只能用于对象。
- F. 基本类型或对象都可以用于变量。

## 119. 假设有一个带有 protected 变量的 `Bouncer` 类。哪些类可以访问该变量？

- A. `Bouncer` 的任何子类或与 `Bouncer` 同包的类
- B. `Bouncer` 的任何父类
- C. 仅 `Bouncer` 的子类
- D. 仅与 `Bouncer` 同包的类
- E. 以上都不是

## 120. 以下代码的输出是什么？

```java
package forest;

public class Tree {

    static int heat = 10;

    int water = 2;

    static class Oak { // p1

        public int getWater() { // p2

            return water;

        }
```
