
```java
    }

    public static void main(String[] args) {

        System.out.println(new Oak().getWater());

    }

}
```

+ A. 8
+ B. p1 行包含错误。
+ C. p2 行包含错误。
+ D. 以上都不是

21. 以下可以填充空白使代码编译？（选择两个。）

+ A. class extends
+ B. class implements
+ C. A 和 B 都不。
+ D. interface extends
+ E. interface implements

22. 关于以下方法，哪个是正确的？

```java
public void setColor(String color) {
  color;
}
```

+ A. 这是一个正确的访问方法（accessor method）。
+ B. 这是一个正确的修改方法（mutator method）。
+ C. 这是一个错误的访问方法。
+ D. 这是一个错误的修改方法。
+ E. 以上都不是。

23. 在构造函数中调用 `this()` 的以下哪些陈述正确？（选择三个。）

+ A. 如果为 `this()` 提供了参数，必须有一个接收这些参数的父类。
+ B. 如果为 `this()` 提供了参数，则必须有一个无参数构造函数。
+ C. 如果没有调用无参数构造函数，则必须显式定义。
+ D. 如果构造函数中同时使用了 `super()` 和 `this()`，`super()` 必须在 `this()` 之后的行。
+ E. 如果构造函数中同时使用了 `super()` 和 `this()`，`this()` 必须在 `super()` 之后的行。
+ F. 如果使用了 `this()`，它必须是构造函数的第一行。

24. 编译并执行以下类的结果是什么？

```java
public class Skates {
    static int wheels = 1;
    int tracks = 5;
    public static void main(String[] args) {
        Skates s = new Skates();
        int feet = 4, tracks = 15;
        System.out.print(feet + tracks);
    }
}
```

+ A. 代码无法编译。
+ B. 4
+ C. 5
+ D. 10
+ E. 20

25. 关于以下程序的哪些陈述是正确的？（选择两个。）

```java
package vessel;

class Problem extends Exception {
    abstract class Danger {
        protected void isDanger() throws Problem; // m1
    }
    public class SeriousDanger extends Danger { // m2
        protected void isDanger() throws Exception { // m3
            throw new RuntimeException(); // m4
        }
        public static void main(String[] w) throws Throwable { // m5
            var sd = new SeriousDanger().isDanger(); // m6
        }
    }
}
```

+ A. 代码因为 m1 无法编译。
+ B. 代码因为 m2 无法编译。
+ C. 代码因为 m3 无法编译。
+ D. 代码因为 m4 无法编译。
+ E. 代码因为 m5 无法编译。
+ F. 代码因为 m6 无法编译。

26. 关于顶层类和成员内部类，哪些陈述是正确的？（选择三个。）

+ A. 都可以标记为 `protected`。
+ B. 只有顶层类可以声明为 `final`。
+ C. 都可以声明构造函数。
+ D. 成员内部类不能标记为 `private`。
+ E. 成员内部类可以访问其定义的顶层类的私有变量。
+ F. 它们都可以标记为 `abstract`。

27. 定义一个 Java 类文件需要什么？

+ A. 类声明
+ B. `package` 语句
+ C. `import` 语句
+ D. 类声明和 `package` 语句
+ E. 类声明和至少一个 `import` 语句
+ F. `public` 修饰符

28. 在 `main()` 方法结束前夕，有多少个对象可以被垃圾回收？

```java
1: public class Person {
2: public Person youngestChild;
3:
4: public static void main(String... args) {
5:     Person elena = new Person();
6:     Person janeice = new Person();
7:     elena.youngestChild = janeice;
8: }
9:
```
```java
8: janeice = null;
9: Person zoe = new Person();
10: elena.youngestChild = zoe;
11: zoe = null;
12: } }
```

- A. 无
- B. 一个
- C. 二
- D. 三
- E. 代码无法编译。

29. 下一个程序的输出是什么？

```java
package race;

interface Drive {
    int SPEED = 5;
    default Integer getSpeed() { return SPEED; }
}

interface Hover {
    String MAX_SPEED = "10";
    default String getSpeed() { return MAX_SPEED; }
}

public class Car implements Drive, Hover {
    @Override public Object getSpeed() { return 15; }
    public static void main(String[] gears) {
        System.out.print(new Car().getSpeed());
    }
}
```

- A. 5
- B. 10
- C. 15
- D. 代码无法编译。
- E. 代码可以编译但在运行时抛出异常。
- F. 根据给出信息无法确定答案。

30. 下一个程序的输出是什么？（选择两个。）

```java
1: public class ChooseWisely {
2: public ChooseWisely() { super(); }
3: public int choose(int choice) { return 5; }
4: public int choose(short choice) { return 2; }
5: public int choose(long choice) { return 11; }
6: public int choose(double choice) { return 6; }
7: public int choose(Float choice) { return 8; }
8: public static void main(String[] path) {
9: ChooseWisely c = new ChooseWisely();
10: System.out.println(c.choose(2f));
11: System.out.println(c.choose((byte)2+1));
12: } }
```

A. 2
B. 3
C. 5
D. 6
E. 8
F. 11

31. 以下程序中有多少行无法编译？

```java
1: public enum Color {
2: RED(1,2) { void toSpectrum() {} },
3: BLUE(2) { void toSpectrum() {} void printColor() {} },
4: ORANGE() { void toSpectrum() {} },
5: GREEN(4);
6: public Color(int color) {}
7: abstract void toSpectrum();
8: final void printColor() {}
9: }
```

A. 零
B. 一
C. 二
D. 三
E. 多于三行

32. `Square` 程序的输出是什么？

```java
package shapes;

abstract class Trapezoid {
    private int getEqualSides() {return 0;}
}

abstract class Rectangle extends Trapezoid {
    public static int getEqualSides() {return 2;} // x1
}

public class Square extends Rectangle {
    public int getEqualSides() {return 4;} // x2
    public static void main(String[] corners) {
        final Square myFigure = new Square();
        System.out.print(myFigure.getEqualSides());
    }
}
```

A. 0
B. 2
C. 4
D. 代码因 x1 行无法编译。
E. 代码因 x2 行无法编译。
F. 代码因 x3 行无法编译。

33. 填写什么可以填充空白处，使得 `com.mammal` 包中的所有类都能调用 `play()` 方法，但 `com.mammal.gopher` 包中的不能调用？

```java
package com.mammal;

public class Enrichment {
    void play() {}
}
```

- A. 留空
- B. `private`
- C. `protected`
- D. `public`
- E. 以上都不是

34. 下表中有多少个单元格是错误的？

| 类型 | 允许方法吗？ | 允许常量吗？ | 允许构造函数吗？ |
| --- | --- | --- | --- |
| 抽象类 | 是 | 是 | 否 |
| 具体类 | 是 | 是 | 是 |
| 接口 | 是 | 是 | 是 |

- A. 零
- B. 一
- C. 二
- D. 三
- E. 四
- F. 五
- G. 六

35. 密封类的直接子类允许使用哪些修饰符？（选择三个。）

- A. `void`
- B. `default`
- C. `public`
- D. `private`
- E. `volatile`
- F. `final`
- G. `nonsealed`

36. 关于函数式接口，哪些描述是正确的？（选择三个。）

- A. 可以包含任意数量的抽象方法。
- B. 它必须包含单个抽象方法。
- C. 可以包含任意数量的私有方法。
- D. 它必须包含单个私有方法。
- E. 可以包含任意数量的静态方法。
- F. 它必须包含单个静态方法。

37. 下一个程序的可能输出是什么？

```java
package wrap;

public class Gift {
    private final Object contents;
    protected Object getContents() {
        return contents;
    }
    protected void setContents(Object contents) {
        this.contents = contents;
    }
    public void showPresent() {
        System.out.print("Your gift:"+contents);
    }
    public static void main(String[] treats) {
        var gift = new Gift();
        gift.setContents(gift);
        gift.showPresent();
    }
}
```

A. Your gift: wrap.Gift@29ca2745
B. Your gift: Your gift:
C. 代码无法编译。
D. 代码可以编译但在运行时抛出异常。
E. 以上都不是。

38. 为了使以下代码编译，需要修正多少行？

```java
1: package animal;
2: interface CanFly {
3:     public void fly() {}
4:     int speed = 5;
5: }
6: final class Bird {
7:     public int fly(int speed) {}
8: }
9: public class Eagle extends Bird implements CanFly {
10:    public void fly()
11: }
```

A. 无
B. 一
C. 二
D. 三

39. 以下代码的输出是什么？

```java
public class Bunny {
    static class Rabbit {
        void hop() {
            System.out.print("hop");
        }
    }
    static class FlemishRabbit extends Rabbit {
        void hop() {
            System.out.print("HOP");
        }
    }
    public static void main(String[] args) {
        Rabbit r1 = new FlemishRabbit();
        FlemishRabbit r2 = new FlemishRabbit();
        r1.hop();
        r2.hop();
    }
}
```

A. hop
B. HOP
C. hopHOP
D. HOP
E. 代码无法编译。

40. 以下哪些声明是有效的？（选择三个。）

A. class {}
B. class {}
C. class {}
D. class {}
E. class {}

41. `InfiniteMath` 程序的输出是什么？

```java
class Math {
    public final secret = 2;
}
class ComplexMath extends Math {
    public final secret = 4;
}
public class InfiniteMath {
    public static void main(String[] args) {
        Math math = new ComplexMath();
        System.out.print(math.secret);
    }
}
```

A. 2
B. 4
C. 代码无法编译。
D. 代码可以编译但在运行时抛出异常。

42. 对于以下应用，在调用 `slalom` 方法后，哪个图表最好表示变量的状态？

```java
package zoo;

public class Penguin {
    private int volume = 1;
    private class Chick {
        private static int volume = 3;
        void chick(int volume) {
            System.out.print("Honk" + Penguin.this.volume + "!");
        }
    }
    public static void main(String[] eggs) {
        Penguin pen = new Penguin();
        final Penguin.Chick littleOne = pen.new Chick();
        littleOne.chick(5);
    }
}
```

A. Honk(1)!
B. Honk(3)!
C. Honk(5)
D. 代码无法编译。
E. 代码可以编译，但在运行时无法确定输出。

43. C. `super.Edible.getColor()`
44. D. `super.getColor()`
45. E. 无论在空白处插入什么内容，代码都无法编译。
46. F. 以上都不是。

46. 假定以下两个位于不同包的类，在代码中插入哪行代码允许第二个类通过编译？

```java
package clothes;
```
