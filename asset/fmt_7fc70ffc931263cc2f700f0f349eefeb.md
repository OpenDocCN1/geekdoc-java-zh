
## 57. 下面程序的输出是什么？

```java
final int distance = 2;

public static void main(String[] seaweed) {

    final int distance = 3;

    CanSwim seaTurtle = {

        final int distance = 5;

        @Override

        public void swim(final int distance) {

            System.out.print(distance);

        }

    };

    seaTurtle.swim(7);

}

}
```

+ A. 2
+ B. 3
+ C. 5
+ D. 7
+ E. 代码无法编译。
+ F. 以上都不是。

## 58. 下面程序的输出是什么？

```java
package pet;

public class Puppy {

    public static int wag = 5; // q1

    public void Puppy(int wag) { // q2

        this.wag = wag;

    }

}
```

```java
}

public static void main(String[] tail) {

  System.out.print(new Puppy(2).wag); // q3

}
```

+ A. 2
+ B. 5
+ C. 编译错误的第一行是 q1 行。
+ D. 编译错误的第一行是 q2 行。
+ E. 编译错误的第一行是 q3 行。

## 59. 给定类中使用的以下方法签名，哪些类可以调用它？

```java
void run(String government)
```

+ A. 其他包中的类
+ B. 同一个包中的类
+ C. 不同包中的子类
+ D. 所有类
+ E. 以上都不是

## 60. 哪是第一个无法编译的声明？

```java
package desert;

interface CanBurrow {

  public abstract void burrow();

}
```

```java
@FunctionalInterface interface HasHardShell
extends CanBurrow {}

abstract class Tortoise implements HasHardShell {

  public abstract int toughness();

}
```

```java
public class DesertTortoise extends Tortoise {

  public int toughness() { return 11; }

}
```

+ A. CanBurrow
+ B. HasHardShell
+ C. Tortoise
+ D. DesertTortoise
+ E. 所有声明均可编译。

## 61. 哪是第一个无法编译的行？

```java
interface Building {

    default Double getHeight() { return 1.0; } // m1

}

interface Office {

    public default String getHeight() { return null; } // m2

}

abstract class Tower implements Building, Office {} // m3

public class Restaurant extends Tower {} // m4
```

+ A. m1 行
+ B. m2 行
+ C. m3 行
+ D. m4 行
+ E. 代码片段中以上都不是

## 62. 下述代码段的输出是什么？

```java
public class Nature {

    public static void main(String[] seeds) {

        record Tree() {}

        var tree = "pine";

        int count = 0;

        if (tree.equals("pine")) {

            int height = 55;

            count = count + 1;

        }

        System.out.print(height + count);

    }

}
```

+ A. 1
+ B. 55
+ C. 56
+ D. 无法编译，因为 record 不能嵌套在方法中。
+ E. 无法编译，因为 record 必须至少传递一个值。
+ F. 因为其他原因无法编译。

## 63. 下面哪些是 Java 中有效的注释？（选择三个。）

+ A. /****** TODO */
+ B. # Fix this bug later
+ C. ' Error closing pod bay doors
+ D. / Invalid record /
+ E. /* Page not found */
+ F. // IGNORE ME

## 64. 下面哪些修饰符配对可以同时应用于一个方法？（选择三个。）

+ A. private and final
+ B. abstract and final
+ C. static and private
+ D. private and abstract
+ E. abstract and static
+ F. static and protected

## 65. 给定以下类，应该在两个空白处插入什么内容以确保类数据被正确封装？

```java
package storage;

public class Box {

    public String stuff; ____________________ String () {

        return stuff;

    }

    public void setStuff(String stuff) {

      this.stuff = stuff;

    }

}
```

+ A. private and getStuff
+ B. private and isStuff
+ C. public and getStuff
+ D. public and isStuff
+ E. default and getStuff
+ F. 以上都不是

## 66. 下表中有多少行包含错误？

|  | 成员类型 | 需要方法体？ |
|---|---|---|
| static method | Class | Yes |
| private non-static method | Class | Yes |
| abstract method | Instance | No |
| default method | Instance | No |
| private static method | Class | Yes |

+ A. 零
+ B. 一行
+ C. 两行
+ D. 三行
+ E. 四行
+ F. 五或更多

## 67. 填充空白：___ 用于调用父类中的构造函数，而 ___ 用于引用父类中的成员。

+ A. super, this()
+ B. super, super()
+ C. super(), this
+ D. super(), super
+ E. 以上都不是

## 68. 下面哪些声明可以插入到空白处并使类通过编译？

```java
public sealed class Toy {

    extends Toy {

}
```

+ A. nonsealed class Book
+ B. abstract class Robot
+ C. class ActionFigure
+ D. record Doll()
+ E. interface Game
+ F. non-sealed class Ball
+ G. 以上都不是，因为 Toy 没有包含 permits 子句

## 69. 该程序的输出是什么？

```java
1:   class SmartWatch extends Watch {

2:   private String getType() { return "smart watch"; }

3:   public String getName(String suffix) {

4:   return getType() + suffix;

5:     }

6:   public class Watch {

7:   private String getType() { return "watch"; }

8:   public String getName(String suffix) {

9:   return getType() + suffix;

10:  }

11:  public static void main(String[] args) {

12:    var watch = new Watch();

13:    var smartWatch = new SmartWatch();

14:    System.out.print(watch.getName(","));

15:    System.out.print(smartWatch.getName(","));

16:  }
```

+ A. smart watch,watch
+ B. watch,smart watch
+ C. watch,watch
+ D. 代码无法编译
+ E. 运行时打印出异常
+ F. 以上都不是

## 70. 程序的输出是什么？

```java
package theater;

class Cinema {

    private String name = "Sequel";

    public Cinema(String name) {

        this.name = name;

    }

}

class Movie extends Cinema {

    private String name = "adaptation";

    public Movie(String name) {

        this.name = name;

    }

    public static void main(String[] args) {

        System.out.print(new Movie("Trilogy").name);

    }

}
```

+ A. Sequel
+ B. Trilogy
+ C. Remake
+ D. Adaptation
+ E. null

## 71. 哪个语句最能描述这个类？

```java
import java.util.*;

public final class Ocean {

    private final List<String> algae;

    private final double wave;

    private int sun;

    public Ocean(double wave) {

        this.wave = wave;

        this.algae = new ArrayList<>();

    }

    public int getSun() {

      return sun;

    }

    public void setSun(int sun) {

      sun = sun;

    }

    public double getWave() {

      return wave;

    }

    public List<String> getAlgae() {

      return new ArrayList<>(algae);

    }

}
```

+ A. 可以序列化。
+ B. 它是良好封装的。
+ C. 它是不可变的。
+ D. 它是既良好封装又不可变的。
+ E. 以上都不是，代码无法编译。

## 72. 给定所示的 Magnet.java，独立插入哪行 `var color;`会导致代码无法编译？

```java
// line a1

public class Magnet {

  // line a2

  public void attach() {

    // line a3

  }

  // line a4

}
```

+ A. a2
+ B. a3
+ C. a2 和 a3
+ D. a1, a2, a3 和 a4
+ E. 以上都不是

## 73. 下面哪个结果不是该程序的可能输出？

```java
package sea;

enum Direction { north, south, east, west };

class Ship {

    public static void main(String[] compass) {

        System.out.print(Direction.valueOf(compass[0]));

    }

}
```

+ A. 打印 WEST。
+ B. 打印 south。
+ C. 运行时抛出 ArrayIndexOutOfBoundsException。
+ D. 运行时抛出 IllegalArgumentException。
+ E. 以上所有皆。

## 74. 下述应用的输出是什么？

```java
package radio;

public class Song {

    public void playMusic() {

        System.out.print("Play!");

    }

    private static void playMusic() {

        System.out.print("Music!");

    }

    private static void playMusic(String song) {

        System.out.print(song);

    }

    public static void main(String[] tracks) {

        new Song().playMusic();

    }

}
```

+ A. Play!
+ B. Music!
+ C. 代码无法编译。
+ D. 代码可以编译，但在运行时之前无法确定。

## 75. 关于方法重写的以下哪些说法是正确的？（选择三个。）

+ A. 返回类型必须是协变的（covariant）。
+ B. 子类中方法的修饰符必须与父类方法相同或更窄。
+ C. 返回类型必须相同。
+ D. 父类方法声明的受检异常必须在子类方法中被声明。
+ E. 子类方法声明的受检异常必须与父类方法声明的异常相同或更窄。
+ F. 子类中方法的修饰符必须与父类相同或更宽。

## 76. 下述代码中有多少行无法编译？

```java
10:   interface Flavor {

11:     public default void happy() {

12:       printFlavor("Rocky road")

13:     }

14:     private static void excited() {

15:       printFlavor("Peanut butter")

15:     }

17:     private static void printFlavor(String f) {

18:       System.out.println("Favorite Flavor is: "+f);

19:     }

20:     public static void sad() {

21:       printFlavor("Butter pecan")

22:     }

23:   }

24:   public class IceCream implements Flavor {

25:     @Override public void happy() {

26:       printFlavor("Cherry chocolate chip")

27:     }

28:   }
```

+ A. 零，全部可以编译。
+ B. 一行
+ C. 两行
+ D. 三行
+ E. 四行
+ F. 五或更多

## 77. 下一个程序的输出是什么？

```java
1:   public record Disco(int beats) {

2:   public Disco(String beats) {

3:      this(20);

4:   }

5:   public Disco {

6:      beats = 10;

7:   }

8:   public int getBeats() {

9:      return beats;

10:  }

11:  public static void main(String[] args) {

12:     System.out.print(new Disco(30).beats());

13: }
}
```
