
System.out.printf("ceil(-9.8) = %1f%n", ceil(-9.8));

System.out.printf("E = %f%n", E);

System.out.printf("PI = %f%n", PI);

}

}

```

```
sqrt(900.0) = 30.0
ceil(-9.8) = -9.0
E = 2.718282
PI = 3.141593
```

# 第8章 类与对象：深入探讨

## 软件工程观察 8.11

将实例变量声明为 `final` 有助于强制最小权限原则。如果一个实例变量不应该被修改，请将其声明为 `final` 以防止修改。例如，在 8.8 中，实例变量 `firstName`、`lastName`、`birthday` 和 `birth` 在初始化后从未被修改，它们应该被声明为 `final`。我们在今后的所有程序中都会执行这一实践。你将在第23章“并发”中看到 `final` 的额外好处。

## 常见编程错误 8.8

初始化后尝试修改 `final` 实例变量会导致编译错误。

## 错误预防技巧 8.5

修改 `final` 实例变量的尝试会在编译时被捕获，而不是导致运行时错误。如果可能，最好在编译时发现 bug，而不是让它们泄露到运行时（经验表明，运行时的报告成本比编译时高得多倍）。

## 软件工程观察 8.12

如果一个 `final` 字段在声明时被初始化为一个永远改变的值，且该值适用于该类的所有对象，那么它也应该声明为 `static`。在初始化之后，我们不需要为类的每个对象都创建一个该字段的单独副本。将字段设为 `static` 可以让该类的所有对象共享该 `final` 字段。

## 8.14 包访问

如果在类中声明方法或变量时没有指定修饰符（`public`、`protected` 或 `private`——将在第9章后讨论），则该方法或变量将具有包访问权限（package access）。在一个只有一个类声明的程序中，没有没有影响。然而，如果一个程序使用了同一个包（即一组类）中的多个类，这些类可以通过对相应类对象的直接引用访问彼此的包成员，或者在静态成员的情况下通过类名访问。包访问权限很少使用。

图 8.15 展示了包访问。该应用程序在一个源文件中包含两个类：包含 `main` 方法（第 5–21 行）的 `Package` 类和 `PackageData` 类（第 24–41 行）。位于同一个源文件中的类属于同一个包的一部分。因此，`PackageData` 允许修改 `PackageData` 对象的包访问权限数据。当你编译此程序时，编译器会生成两个独立的 `.class` 文件——`TestData.class` 和 `PackageData.class`。编译器将这两个 `.class` 文件存放在同一个目录下。你也可以将 `PackageData`（第 24–41 行）放在一个单独的源文件中。

在 `PackageData` 的声明行中，第 26–27 行声明了没有修饰符的实例变量和字符串——因此，这些是包访问实例变量。`PackageData` 类的 `main` 方法创建 `PackageData` 类的实例（第 29 行），以演示直接修改 `PackageData` 实例变量的能力（如第 15–16 行所示）。修改的结果可以在输出窗口中看到。

## 8.15 使用 BigDecimal 进行精确的货币计算

```java
// Fig. 8.15: PackageDataTest.java
// 类的包访问成员可以被同一个包中的其他类访问
```

```java
public class PackageDataTest
{
    public static void main(String[] args) {
        PackageData packageData = new PackageData();

        // 输出 PackageData 的字符串表示
        System.out.printf("After instantiation:%n%s%s\n", packageData);

        // 修改 packageData 对象中的包访问数据
        packageData.number = 77;
        packageData.string = "Goodbye";

        // 输出 packageData 的字符串表示
        System.out.printf("%nAfter changing values:%n%s\n", packageData);
    }
}
```

```java
// 具有包访问实例变量类
class PackageData {
    int number; // 包访问实例变量
    String string; // 包访问实例变量

    // 构造函数
    public PackageData() {
        number = 0;
        string = "Hello";
    }

    // 返回 PackageData 对象的字符串表示
    public String toString() {
        return String.format("number: %d; string: %s", number, string);
    }
}
```

**图 8.15** 类的包访问成员可以被同一个包中的其他类访问。

## 8.15 使用 BigDecimal 进行精确的货币计算

在前面的章节中，我们演示使用 `double` 类型的值进行货币计算。在第5章中，我们讨论了 `double` 值是近似表示的。任何需要精确浮点数计算的应用程序都应该使用 `BigDecimal`。

### 利息

图 8.16 使用 `NumberFormat` 对象实现了 5.6 示例中的利息计算。在 U.S. 地区，1234.56 会格式化为 "1234.56"，而在欧洲地区它会被格式化为 "1234,56"。

```java
// Interest.java
// 使用 BigDecimal 进行复利计算
import java.math.BigDecimal;
import java.text.NumberFormat;

public class Interest {
    public static void main(String[] args) {
        // 初始本金
        BigDecimal principal = BigDecimal.valueOf(1000.0);

        // 利率
        BigDecimal rate = BigDecimal.valueOf(0.05);

        // 显示标题
        System.out.printf("%s%s%n", "Year", "Amount on deposit");

        // 计算每年的本金金额
        for (int year = 1; year <= 10; year++) {
            // 计算金额
            BigDecimal amount = principal.multiply(rate.add(BigDecimal.ONE)).pow(year);

            // 显示年份和金额
            System.out.printf("%d%s%n", year, NumberFormat.getCurrencyInstance().format(amount));
        }
    }
}
```

| Year | Amount on deposit |
| :--- | :--- |
| 1 | $1050.00 |
| 2 | $1102.50 |
| 3 | $1157.62 |
| 4 | $1215.51 |
| 5 | $1276.28 |
| 6 | $1340.10 |
| 7 | $1407.10 |
| 8 | $1477.46 |
| 9 | $1551.33 |
| 10 | $1628.89 |

**图 8.16** 使用 BigDecimal 进行复利计算。

### 创建 BigDecimal 对象

第 11–12 行使用静态方法 `valueOf` 声明并初始化 `BigDecimal` 变量，该方法接收一个 `double` 参数并返回一个表示精确值的 `BigDecimal` 对象。

### 使用 BigDecimal 执行计算

第 21–22 行使用 `BigDecimal` 方法 `add` 和 `pow` 执行计算。第 22 行的表达式评估如下：

- 首先，表达式 `rate.add(BigDecimal.ONE)` 将 1 加到利率产生包含 1.05 的 `BigDecimal`——这等同于 5.6 中的 `1.0 + rate`。
- 接下来，对前面的结果调用 `pow` 以进行幂运算——这等同于将 `1.0 + rate` 和 `year` 传递给 5.6 中的 `Math.pow`。
- 最后，我们对本金调用 `multiply`，并将前面的结果作为参数。这返回年底金额的 `BigDecimal`。

由于 `rate.add(BigDecimal.ONE)` 在循环的每次迭代中产生相同的值，我们本可以在第 12 行直接将 `rate` 初始化为 `1.05`；但我们选择模仿我们在 5.6 第 19 行中使用的精确计算。

### 使用 NumberFormat 格式化货币值

在循环的每次迭代中，第 26 行

```
NumberFormat.getCurrencyInstance().format(amount)
```

评估如下：

- 首先，表达式使用 `NumberFormat` 的静态方法 `getCurrencyInstance` 获取一个预先配置为将数值格式化为特定地区货币字符串的 `NumberFormat`——例如，在美国地区，数值 `1628.89` 被格式化为 `$1,628.89`。特定地区的格式化是国际化的重要部分——为用户的各种语言和口语地区定制应用程序的过程会调用 `getCurrencyInstance()` 返回的 `Number` 对象对金额值进行格式化。`format` 方法返回特定地区的字符串表示，保留到小数点后两位。

### 舍入 BigDecimal

除了精度计算，`BigDecimal` 还允许你控制如何舍入——默认情况下，所有计算都是精确的，不会发生舍入。如果你不指定如何舍入 `BigDecimal` 值且给定值无法精确表示（例如 1 除以 3 的结果 0.33333333...），则会抛出 `ArithmeticException`。

我们在本示例中未显示，但你可以通过向 `BigDecimal` 类提供 `MathContext` 对象（`java.math` 包）来指定 `BigDecimal` 的舍入模式。

在创建 `BigDecimal` 时使用构造函数。你还可以向各种执行计算的 `BigDecimal` 方法提供 `MathContext`。`MathContext` 类包含了几个预配置的 `MathContext` 对象，你可以了解它们：

```
http://docs.oracle.com/java/7/docs/api/java/math/MathContext.html
```

默认情况下，每个预配置的 `MathContext` 都使用所谓的“银行舍入法”（bankers rounding），正如 `RoundingMode HALF_EVEN` 中解释的那样：

```
http://docs.oracle.com/java/7/docs/api/java/math/RoundingMode.html#HALF_EVEN
```

### BigDecimal 值

`BigDecimal` 的精度（scale）是小数点右后的位数。如果你需要将 `BigDecimal` 舍入到特定的位数，可以调用 `BigDecimal.setScale`。例如，以下表达式返回一个小数点后保留两位并使用银行舍入法的 `BigDecimal`：

```
amount.setScale(2, RoundingMode.HALF_EVEN)
```

## 8.16（可选）GUI 与图形案例研究：在图形中使用对象

到目前为止你看到的大多数图形并没有随着程序的每次执行而变化。6.13 节中的练习 6.2 要求你创建一个随机生成形状和颜色的程序。在那个练习中，系统每次调用 `paintComponent` 时，图形都会改变。为了创建一个每次绘制时都保持不变的一致图形，我们必须创建一个类来存储每个形状的信息。当系统调用 `paintComponent` 时，为了实现这一点，我们将创建这些类的“智能”对象，并使用 `Graphics` 对象来绘制它们。

### MyLine

图 8.17 定义了 `MyLine`，它具有所有这些能力。`MyLine` 类导入了 `Color` 和 `Graphics`（第 3–4 行）。第 8–11 行声明了绘制线条所需的端点坐标实例变量，第 12 行声明了存储线条颜色的实例变量。第 15–22 行的构造函数接收五个参数，对应它初始化的每个实例变量。第 25–29 行的 `draw` 方法需要 `Graphics` 对象以便指定的颜色在两个端点之间绘制线条。

```java
// Fig. 8.17: MyLine.java
// MyLine 类表示一条线条。
import java.awt.Color;
import java.awt.Graphics;

public class MyLine
{
    private int x1; // 第一个端点的 x 坐标
    private int y1; // 第一个端点的 y 坐标
    private int x2; // 第二个端点的 x 坐标
    private int y2; // 第二个端点的 y 坐标
    private Color color; // 这条线条的颜色

    // 带有输入值的构造函数
    public MyLine(int x1, int y1, int x2, int y2, Color color)
    {
        this.x1 = x1;
        this.y1 = y1;
        this.x2 = x2;
        this.y2 = y2;
        this.color = color;
    }

    // 以指定的颜色绘制线条
    public void draw(Graphics g)
    {
        g.setColor(color);
        g.drawLine(x1, y1, x2, y2);
    }
} // MyLine 类结束
```

**图 8.17** MyLine 类表示一条线条。

### DrawPanel

在图 8.18 中，我们声明了 `DrawPanel`，它将生成 `MyLine` 类的随机对象。第 12 行声明了 `MyLine[] lines` 数组用于存储要绘制的线条。在构造函数（第 15-37 行）内部，第 17 行将背景设置为 `Color.WHITE`。第 19 行创建一个长度在 5 到 9 之间的随机数组。第 22-36 行的循环为数组中的每个元素创建一个新的 `MyLine`。第 25-28 行为每条线条的端点生成随机坐标，并为线条设置随机颜色。第 35 行使用随机生成的值创建一个新的 `MyLine` 对象并将其存储在数组中。`paintComponent` 方法使用增强语句（第 45-46 行）遍历数组 `lines` 中的 `MyLine` 对象。每次迭代都会调用当前 `MyLine` 对象的 `draw` 方法，并传递 `Graphics` 对象以便在面板上绘制。

```java
// DrawPanel.java
// 使用 MyLine 类
// 绘制随机线条的程序
import java.awt.Color;
import java.awt.Graphics;
import java.security.SecureRandom;
import javax.swing.JPanel;

public class DrawPanel extends JPanel
{
    private SecureRandom randomNumbers = new SecureRandom();
    private MyLine[] lines; // 线条数组

    // 构造函数，创建一个带有随机形状的面板
    public DrawPanel()
    {
        setBackground(Color.WHITE);
        lines = new MyLine[5 + randomNumbers.nextInt(5)];

        // 创建线条
```

**图 8.18** 使用 MyLine 绘制随机线条的程序。
