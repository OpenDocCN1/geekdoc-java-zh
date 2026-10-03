
# 200+ 个初学者 Java 程序

![](img/cover.jpg)

![img](img/cover.jpg)

恭喜你！

## 引言

本书是任何想要快速、有效地掌握 Java 的初学者的必备工具。书中包含 200 多个实战项目和易于理解的程序，将引导你从基础一步步到更复杂的项目。

每个程序的设计都旨在挑战你，并将你的技能提升到新的水平。通过逻辑练习、有趣的项目和实用的应用程序，你将学会像程序员一样思考，并编写整洁高效的代码。

## 1. 打印 Hello World

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

```
// Hello, World!
```

## 2. 两个数字相加

```java
import java.util.Scanner;
```

```java
public class Main {
    public static void main(String[] args) {
        // 创建一个扫描器用于用户输入
        Scanner scanner = new Scanner(System.in);
        // 从用户处读取数字
        double num1 = readNumber(scanner, "输入第一个数字: ");
        double num2 = readNumber(scanner, "输入第二个数字: ");
        // 执行加法
        double sumResult = num1 + num2;
        System.out.printf("%.2f 和 %.2f 的和是: %.2f%n", num1, num2, sumResult);
        scanner.close();
    }

    // 从用户处读取数字的函数
    private static double readNumber(Scanner scanner, String prompt) {
        while (true) {
            System.out.print(prompt);
            String input = scanner.nextLine();
            try {
                // 尝试将输入解析为 double
                return Double.parseDouble(input);
            } catch (NumberFormatException e) {
                System.out.println("请输入一个有效的数字.");
            }
        }
    }
}
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 3. 求平方根

![image](img/chapter_title_below.png)

```java
import java.util.Scanner ;

public class Main {
    // 读取用户输入并解析为 double
    public static double readNumber(String prompt) {
        Scanner scanner = new Scanner(System.in);
        while (true) {
            System.out.print(prompt);
            String input = scanner.nextLine();
            try {
                // 尝试将输入解析为 double
                double number = Double.parseDouble(input);
                if (number >= 0) {
                    return number;
                } else {
                    System.out.println("请输入一个非负数.");
                }
            } catch (NumberFormatException e) {
                System.out.println("请输入一个有效的数字.");
            }
        }
    }

    public static void main(String[] args) {
        // 从用户处读取一个数字
        double inputNumber = readNumber("输入一个非负数: ");
        // 计算平方根
        double squareRoot = Math.sqrt(inputNumber);
        System.out.println(inputNumber + " 的平方根是: " + squareRoot);
    }
}
```

```
// 输出示例：

// 输入一个非负数: 3

// 3.0 的平方根是: 1.7320508075688772
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 4. 计算三角形面积

![image](img/chapter_title_below.png)

```java
import java.util.Scanner ;

public class Main {
    // 读取用户输入并解析为正数 double
    public static double readPositiveNumber(String prompt) {
        Scanner scanner = new Scanner(System.in);
        while (true) {
            System.out.print(prompt);
            String input = scanner.nextLine();
            try {
                // 尝试将输入解析为 double
                double number = Double.parseDouble(input);
                if (number > 0) {
                    return number;
                } else {
                    System.out.println("请输入一个有效的正数.");
                }
            } catch (NumberFormatException e) {
                System.out.println("请输入一个有效的数字.");
            }
        }
    }

    public static void main(String[] args) {
        // 从用户处读取底和高
        double base = readPositiveNumber("输入三角形的底: ");
        double height = readPositiveNumber("输入三角形的高: ");
        // 计算三角形面积
        double area = 0.5 * base * height;
        System.out.println("底为 " + base + " 高为 " + height + " 的三角形面积是: " + area);
    }
}
```

```
// 输入三角形的底: 3

// 输入三角形的高: 4

// 底为 3.0 高为 4.0 的三角形面积是: 6.0
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 5. 交换两个变量

![image](img/chapter_title_below.png)

```java
import java.util.Scanner ;

public class Main {
    // 读取用户输入
    public static String readInput(String prompt) {
        Scanner scanner = new Scanner(System.in);
        System.out.print(prompt);
        return scanner.nextLine();
    }
```

```java
try {
    return Double.parseDouble(input);
} catch (NumberFormatException e) {
    System.out.println("请输入一个有效的数字。");
}
}

public static void main(String[] args) {
    // 从用户处读取摄氏度
    double celsius = readNumber("输入摄氏度： ");
    // 将摄氏度转换为华度
    double fahrenheit = (celsius * 9.0) / 5.0 + 32.0;
    System.out.println(celsius + " 摄氏度等于 " + fahrenheit + " 华度。");
}

// 输入摄氏度：33

// 33.0 摄氏度等于 91.4 华度。
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 9. 生成随机数

![image](img/chapter_title_below.png)

```java
import java.util.Random;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // 提示用户输入范围
        System.out.print("输入范围的最小值： ");
        double minRange = scanner.nextDouble();

        System.out.print("输入范围的最大值： ");
        double maxRange = scanner.nextDouble();

        // 检查输入是否有效
        if (minRange < maxRange) {
            // 在范围内生成随机数
            Random random = new Random();
            double randomNumber = minRange + (maxRange - minRange) * random.nextDouble();
            System.out.println(minRange + " 到 " + maxRange + " 之间的随机数是：" + randomNumber);
        } else {
            System.out.println("请输入，确保最小值小于最大值。");
        }
    }
}

// 输入范围的最小值：3

// 输入范围的最大值：4

// 3.0 到 4.0 之间的随机数是：3.9904595784187
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 10. 检查数字是正数、负还是零

![image](img/chapter_title_below.png)

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        // 提示用户输入数字
        System.out.print("输入数字： ");

        Scanner scanner = new Scanner(System.in);

        // 尝试作为浮点数读取
        if (scanner.hasNextDouble()) {
            double number = scanner.nextDouble();

            // 检查数字是正、负还是零
            if (number > 0.0) {
                System.out.println(number + " 是正数。");
            } else if (number < 0.0) {
                System.out.println(number + " 是负数。");
            } else {
                System.out.println("输入的数字是零。");
            }
        } else {
            System.out.println("请输入有效的数字。");
        }

        scanner.close();
    }
}

// 输入数字：3

// 3.0 是正数。
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 11. 检查数字是奇还是偶

![image](img/chapter_title_below.png)

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        // 提示用户输入数字
        System.out.print("输入数字： ");

        Scanner scanner = new Scanner(System.in);

        // 尝试作为整数读取
        if (scanner.hasNextInt()) {
            int number = scanner.nextInt();

            // 检查数字是奇还是偶
            if (number % 2 == 0) {
                System.out.println(number + " 是偶数。");
            } else {
                System.out.println(number + " 是奇数。");
            }
        } else {
            System.out.println("请输入有效的整数.");
        }

        scanner.close();
    }
}

// 输入数字：3

// 3 是奇数。
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 12. 找出三个数中的最大值

![image](img/chapter_title_below.png)

```java
import java.util.Scanner;
```



```java
public class Main {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // 从用户处读取三个数字
        double num1 = readNumber(scanner, "输入第一个数字： ");
        double num2 = readNumber(scanner, "输入第二个数字： ");
        double num3 = readNumber(scanner, "输入第三个数字： ");

        // 寻找最大数
        double largestNumber = Math.max(num1, Math.max(num2, num3));

        System.out.printf("%.2f, %.2f 和 %.2f 之间的最大数是 %.2f\n", num1, num2, num3, largestNumber);

        scanner.close();
    }

    private static double readNumber(Scanner scanner, String prompt) {
        System.out.print(prompt);

        if (scanner.hasNextDouble()) {
            return scanner.nextDouble();
        }

        System.out.println("请输入有效的数字。");
        scanner.next();

        return 0.0;
    }
}
```

```text
// 输入第一个数字：33
// 输入第二个数字：34
// 输入第三个数字：35
// 33.00, 34.00 和 35.00 之间的最大数是 35.00
```

```text
// 37
// 41
// 43
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |
|---|---|---|
| ![image](img/chapter_title_above.png) | | |

## 15. 求数字的阶乘

![image](img/chapter_title_below.png)

```java
import java.util.Scanner;

public class FactorialCalculator {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("输入一个非负整数: ");

        if (scanner.hasNextLong()) {
            long number = scanner.nextLong();

            System.out.println(number < 0 ? "请输入一个非负整数。"
                    : " +阶阶阶乘 "是: " + calculateFactorial(number));
        } else {
            System.out.println("请输入一个有效的非负整数.");
        }

        scanner.close();
    }

    private static long calculateFactorial(long n) {
        long result = 1;

        for (long i = 2; i <= n; i++) {
            result *= i;
        }

        return result;
    }
}
```

––––––––

![image](img/scene_break.png)

```text
// 输入一个非负整数: 11
// 11 的阶乘是: 39916800
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |
|---|---|---|
| ![image](img/chapter_title_above.png) | | |

# 16. 显示相法表

![image](img/chapter_title_below.png)

```java
import java.util.Scanner;

public class MultiplicationTable {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("输入用于相法表的数字: ");

        // 检查输入是否为有效整数
        while (!scanner.hasNextInt()) {
            System.out.println("请输入一个有效的整数.");
            scanner.next(); // 清除无效输入
            System.out.print("输入用于相法表的数字: ");
        }

        int number = scanner.nextInt();
        int rangeVal = 10;

        System.out.printf("%d 的相法表（直至 %d）:%n", number, rangeVal);

        // 显示相法表
        for (int i = 1; i <= rangeVal; i++) {
            int result = number * i;
            System.out.printf("%d x %d = %d%n", number, i, result);
        }

        scanner.close();
    }
}
```

```text
// 输入用于相法表的数字: 2
// 2 的相法表（直至 10）
// 2 x 1 = 2
// 2 x 2 = 4
// 2 x 3 = 6
// 2 x 4 = 8
// 2 x 5 = 10
// 2 x 6 = 12
// 2 x 7 = 14
// 2 x 8 = 16
// 2 x 9 = 18
// 2 x 10 = 20
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |
|---|---|---|
| ![image](img/chapter_title_above.png) | | |

## 17. 打印斐波那契数列

![image](img/chapter_title_below.png)

```java
import java.util.Scanner;

public class FibonacciSequence {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("输入斐波那契数列的项数: ");

        // 验证输入
        while (!scanner.hasNextInt()) {
            System.out.println("请输入一个正整数.");
            scanner.next(); // 清除无效输入
            System.out.print("输入斐波那契数列的项数: ");
        }

        int numTerms = scanner.nextInt();

        if (numTerms <= 0) {
            System.out.println("请输入正整数.");
            scanner.close();
            return;
        }

        // 生成斐波那契数列
        long[] fib = new long[numTerms];

        if (numTerms > 0) {
            fib[0] = 0; // 第一项
        }

        if (numTerms > 1) {
            fib[1] = 1; // 第二项
        }

        for (int i = 2; i < numTerms; i++) {
            fib[i] = fib[i - 1] + fib[i - 2]; // 斐波那契公式
        }

        // 打印斐波那契数列
        System.out.print("斐波那契数列: ");

        for (int i = 0; i < numTerms; i++) {
            System.out.print(fib[i]);

            if (i < numTerms - 1) {
                System.out.print(", ");
            }
        }

        System.out.println();
        scanner.close();
    }
}
```

```text
// 输入斐波那契数列的项数: 5
// 斐波那契数列: 0, 1, 1, 2, 3
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |
|---|---|---|
| ![image](img/chapter_title_above.png) | | |

## 18. 检查阿姆斯特数（Armstrong Number）

![image](img/chapter_title_below.png)

```java
import java.util.Scanner;

public class ArmstrongNumber {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("输入一个数字: ");

        // 验证输入
        while (!scanner.hasNextInt()) {
            System.out.println("请输入一个有效的整数.");
            scanner.next(); // 清除无效输入
            System.out.print("输入一个数字: ");
        }

        int number = scanner.nextInt();

        if (number < 0) {
            System.out.println("请输入正整数.");
            scanner.close();
            return;
        }

        int digits = Integer.toString(number).length();
        int sum = 0;
        int temp = number;

        // 计算各位幂之和
        while (temp > 0) {
            int digit = temp % 10; // 获取末一位
            sum += Math.pow(digit, digits); // 将数字的幂累加
            temp /= 10; // 去移除末一位
        }

        // 检查和是否等于原数字
        if (sum == number) {
            System.out.println(number + " 是阿姆斯特数.");
        } else {
            System.out.println(number + " 不是阿姆斯特数.");
        }

        scanner.close();
    }
}
```

```text
// 输入一个数字: 153
// 153 是阿姆斯特数。
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |
|---|---|---|
| ![image](img/chapter_title_above.png) | | |

## 19. 在区间内寻找阿姆斯特数

![image](img/chapter_title_below.png)

```java
import java.util.Scanner;

public class ArmstrongInInterval {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // 读取区间
        System.out.print("输入起始数字: ");
        int start = getValidInteger(scanner);

        System.out.print("输入结束数字: ");
        int end = getValidInteger(scanner);

        if (start > 0 && start < end) {
            System.out.println("区间 [" + start + ", " + end + "] 内的阿姆斯特数:");

            boolean found = false;

            for (int i = start; i <= end; i++) {
                if (isArmstrong(i)) {
                    System.out.println(i);
                    found = true;
                }
            }

            if (!found) {
                System.out.println("区间内没有找到阿姆斯特数.");
            }
        } else {
            System.out.println("请输入起始数字小于结束数字的有效整数.");
        }

        scanner.close();
    }

    // 验证输入并返回整数
    private static int getValidInteger(Scanner scanner) {
        while (!scanner.hasNextInt()) {
            System.out.println("请输入有效的整数.");
            scanner.next(); // 清除无效输入
        }

        return scanner.nextInt();
    }

    // 检查数字是否为阿姆斯特数
    private static boolean isArmstrong(int num) {
        int originalNum = num;
        int sum = 0;
        int digits = Integer.toString(num).length();

        // 计算各位幂之和
        while (num > 0) {
            int digit = num % 10;
            sum += Math.pow(digit, digits);
            num /= 10;
        }

        return sum == originalNum;
    }
}
```

## 20. 制作简易计算器

（注：原文此处代码不完整，仅翻译了提供的结构性部分）

```java
public class SimpleCalculator {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        double num1 = readNumber(scanner, "输入第一个数字: ");
```



```java
double num2 = readNumber(scanner, "输入第二个数字: ");

String operation = readOperation(scanner);

double result = performCalculation(num1, num2, operation);

if (!Double.isNaN(result)) {
    System.out.printf("结果: %.2f %s %.2f = %.2f%n", num1, operation, num2, result);
}

scanner.close();
```

```java
// 从用户输入读取数字的函数
private static double readNumber(Scanner scanner, String prompt) {
    System.out.print(prompt);

    while (!scanner.hasNextDouble()) {
        System.out.println("无效数字。请重试.");
        scanner.next(); // 清除无效输入
        System.out.print(prompt);
    }

    return scanner.nextDouble();
}

// 从用户输入读取操作符
private static String readOperation(Scanner scanner) {
    System.out.print("输入操作 (+, -, *, /): ");
    return scanner.next().trim();
}

// 根据操作执行计算
private static double performCalculation(double num1, double num2, String operation) {
    switch (operation) {
        case "+":
            return num1 + num2;
        case "-":
            return num1 - num2;
        case "*":
            return num1 * num2;
        case "/":
            if (num2 == 0) {
                System.out.println("不能除以零.");
                return Double.NaN; // 返回 NaN 表示错误
            }
            return num1 / num2;
        default:
            System.out.println("无效操作.");
            return Double.NaN; // 返回 NaN 表示错误
    }
}
```

```text
// 输入第一个数字: 10
// 输入第二个数字: 5
// 输入操作 (+, -, *, /): /
// 结果: 10.00 / 5.00 = 2.00
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 21. 求自然数的和

![image](img/chapter_title_below.png)

```java
import java.util.Scanner;

public class SumOfNaturalNumbers {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // 提示用户输入正整数
        System.out.print("输入一个正整数: ");

        while (!scanner.hasNextLong()) {
            System.out.println("请输入有效的正整数.");
            scanner.next(); // 清除无效输入
            System.out.print("输入一个正整数: ");
        }

        long n = scanner.nextLong();

        // 检查数字是否为正
        if (n <= 0) {
            System.out.println("请输入有效的正整数.");
        } else {
            // 计算自然数的和
            long sumOfNaturalNumbers = (n * (n + 1)) / 2;
            System.out.printf("从 1 到 %d 的自然数和为: %d%n", n, sumOfNaturalNumbers);
        }

        scanner.close();
    }
}
```

```text
// 输入一个正整数: 12
// 从 1 到 12 的自然数和为: 78
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 22. 检查数字的末位数字是否相同

![image](img/chapter_title_below.png)

```java
import java.util.Scanner;

public class SameLastDigit {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        long num1 = readNumber(scanner, "输入第一个数字: ");
        long num2 = readNumber(scanner, "输入第二个数字: ");

        if (Math.abs(num1 % 10) == Math.abs(num2 % 10)) {
            System.out.printf("%d 的末位数字与 %d 的末位数字相同.%n", num1, num2);
        } else {
            System.out.printf("%d 的末位数字与 %d 的末位数字不同.%n", num1, num2);
        }

        scanner.close();
    }

    private static long readNumber(Scanner scanner, String prompt) {
        System.out.print(prompt);

        while (!scanner.hasNextLong()) {
            System.out.println("请输入有效的整数.");
            scanner.next(); // 清除无效输入
            System.out.print(prompt);
        }

        return scanner.nextLong();
    }
}
```

```text
// 输入第一个数字: 2
// 输入第二个数字: 3
// 2 的末位数字与 3 的末位数字不同。
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 23. 求最大公约数 (HCF 或 GCD)

![image](img/chapter_title_below.png)

```java
import java.util.Scanner;

public class HCF {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        long num1 = readPositiveNumber(scanner, "输入第一个正整数: ");
        long num2 = readPositiveNumber(scanner, "输入第二个正整数: ");

        System.out.printf(
            "%d 和 %d 的最大公约数 (GCD) 是 %d%n",
            num1,
            num2,
            gcd(num1, num2)
        );

        scanner.close();
    }

    private static long readPositiveNumber(Scanner scanner, String prompt) {
        System.out.print(prompt);

        while (true) {
            if (scanner.hasNextLong()) {
                long number = scanner.nextLong();

                if (number > 0) {
                    return number;
                } else {
                    System.out.println("请输入一个正整数.");
                }
            } else {
                System.out.println("请输入有效的整数.");
                scanner.next(); // 清除无效输入
            }
        }
    }

    private static long gcd(long a, long b) {
        while (b != 0) {
            long temp = b;
            b = a % b;
            a = temp;
        }

        return a;
    }
}
```

```text
// 输入第一个正整数: 22
// 输入第二个正整数: 33
// 22 和 33 的最大公约数 (GCD) 是 11
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 24. 求最小公倍数 (LCM)

![image](img/chapter_title_below.png)

```java
import java.util.Scanner;

public class LCM {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        long num1 = readPositiveNumber(scanner, "输入第一个正整数: ");
        long num2 = readPositiveNumber(scanner, "输入第二个正整数: ");

        long lcm = (num1 * num2) / gcd(num1, num2);

        System.out.printf("%d 和 %d 的最小公倍数是 %d%n", num1, num2, lcm);

        scanner.close();
    }

    private static long readPositiveNumber(Scanner scanner, String prompt) {
        System.out.print(prompt);

        while (true) {
            if (scanner.hasNextLong()) {
                long number = scanner.nextLong();

                if (number > 0) {
                    return number;
                } else {
                    System.out.println("请输入一个正整数.");
                }
            } else {
                System.out.println("请输入有效的整数.");
                scanner.next(); // 清除无效输入
            }
        }
    }

    private static long gcd(long a, long b) {
        while (b != 0) {
            long temp = b;
            b = a % b;
            a = temp;
        }

        return a;
    }
}
```

```text
// 输入第一个正整数: 22
// 输入第二个正整数: 22
// 22 和 22 的最小公倍数是 22
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 25. 求数字的因数

![image](img/chapter_title_below.png)

```java
import java.util.Scanner;

public class Factors {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        long number = readPositiveNumber(scanner, "输入一个正整数: ");

        System.out.printf("%d 的因数:%n", number);

        findFactors(number);

        scanner.close();
    }

    private static long readPositiveNumber(Scanner scanner, String prompt) {
        System.out.print(prompt);

        while (true) {
            if (scanner.hasNextLong()) {
                long number = scanner.nextLong();

                if (number > 0) {
                    return number;
                } else {
                    System.out.println("请输入一个正整数.");
                }
            } else {
                System.out.println("请输入有效的整数.");
                scanner.next(); // 清除无效输入
            }
        }
    }

    private static void findFactors(long number) {
        for (long i = 1; i <= number; i++) {
            if (number % i == 0) {
                System.out.println(i);
            }
        }
    }
}
```



```java
// 输入一个正整数: 44
// 44 的因数:
// 1
// 2
// 4
// 11
// 22
// 44
```

## 26. 使用递归求自然数的和

![image](img/chapter_title_below.png)

```java
import java.util.Scanner;

public class SumOfNaturalNumbers {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        long number = readPositiveNumber(scanner, "输入一个正整数: ");

        // 使用递归显示和
        System.out.printf("从到 %d 的自然数和为: %d%n", number, sumOfNaturalNumbers(number));

        scanner.close();
    }

    // 计算自然数和的递归函数
    private static long sumOfNaturalNumbers(long n) {
        if (n == 0) {
            return 0;
        } else {
            return n + sumOfNaturalNumbers(n - 1);
        }
    }

    private static long readPositiveNumber(Scanner scanner, String prompt) {
        System.out.print(prompt);

        while (true) {
            if (scanner.hasNextLong()) {
                long number = scanner.nextLong();

                if (number > 0) {
                    return number;
                } else {
                    System.out.println("请输入有效的正整数.");
                }
            } else {
                System.out.println("请输入有效的正整数.");
                scanner.next(); // 清除无效输入
            }

            System.out.print(prompt); // 再次提示
        }
    }
}
```

```text
// 输入一个正整数: 33
// 从到 33 的自然数和为: 561
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 27. 猜随机数字

![image](img/chapter_title_below.png)

```java
import java.util.Random;
import java.util.Scanner;

public class GuessRandomNumber {
    public static void main(String[] args) {
        Random random = new Random();
        int randomNumber = random.nextInt(100) + 1; // 生成一个 1 到 100 之间的随机数
        int attempts = 0;
        Scanner scanner = new Scanner(System.in);

        while (true) {
            Integer guess = getGuess(scanner);

            if (guess == null) {
                System.out.println("请输入有效的数字.");
                continue;
            }

            attempts++;

            if (guess < randomNumber) {
                System.out.println("太小了!");
            } else if (guess > randomNumber) {
                System.out.println("太大了!");
            } else {
                System.out.printf("恭喜！你用了 %d 次尝试猜中了 %d%n", attempts, randomNumber);
                break;
            }
        }

        scanner.close();
    }

    private static Integer getGuess(Scanner scanner) {
        System.out.print("猜随机数字 (1-100): ");

        if (scanner.hasNextInt()) {
            return scanner.nextInt();
        } else {
            scanner.next(); // 清除无效输入
            return null;
        }
    }
}
```

```text
// 猜随机数字 (1-100): 50
// 太小了!

// 猜随机数字 (1-100): 75
// 太大了!

// 猜随机数字 (1-100): 62
// 恭喜！你用了 3 次尝试猜中了 62。
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 28. 洗牌

![image](img/chapter_title_below.png)

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class ShuffleDeckOfCards {
    public static void main(String[] args) {
        List<String> deck = createDeck();
        System.out.println("初始牌组:");
        printDeck(deck);

        Collections.shuffle(deck); // 洗牌

        System.out.println("\n洗牌后的牌组:");
        printDeck(deck);
    }

    private static List<String> createDeck() {
        String[] suits = {"Hearts", "Diamonds", "Clubs", "Spades"};
        String[] ranks = {
            "2", "3", "4", "5", "6", "7", "8", "9", "10",
            "Jack", "Queen", "King", "Ace"
        };

        List<String> deck = new ArrayList<>();

        for (String suit : suits) {
            for (String rank : ranks) {
                deck.add(rank + " of " + suit);
            }
        }

        return deck;
    }

    private static void printDeck(List<String> deck) {
        for (String card : deck) {
            System.out.println(card);
        }
    }
}
```

```text
// 初始牌组:
// 2 of Hearts
// 3 of Hearts
// 4 of Hearts
// 5 of Hearts
// ...

// 洗牌后的牌组:
// 10 of Spades
// 4 of Hearts
// Ace of Diamonds
// ...
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 29. 使用递归显示斐波那契序列

![image](img/chapter_title_below.png)

```java
import java.util.Scanner;

public class FibonacciSequence {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("输入斐波那契序列的项数: ");

        int numTerms = scanner.nextInt();

        if (numTerms < 0) {
            System.out.println("请输入非负整数.");
            return;
        }

        System.out.println(numTerms + " 项斐波那契序列:");

        for (int i = 0; i < numTerms; i++) {
            System.out.println(fibonacci(i));
        }
    }

    private static int fibonacci(int n) {
        if (n <= 1) {
            return n;
        } else {
            return fibonacci(n - 1) + fibonacci(n - 2);
        }
    }
}
```

```text
// 输入斐波那契序列的项数: 5
// 5 项斐波那契序列:
// 0
// 1
// 1
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 30. 使用递归计算数字阶乘

![image](img/chapter_title_below.png)

```java
import java.math.BigInteger;
import java.util.Scanner;

public class FactorialCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("输入一个非负整数: ");

        int number = scanner.nextInt();

        if (number < 0) {
            System.out.println("请输入非负整数.");
            return;
        }

        BigInteger result = factorial(number);
        System.out.println(number + " 的阶乘为: " + result);
    }

    private static BigInteger factorial(int n) {
        if (n == 0 || n == 1) {
            return BigInteger.ONE;
        } else {
            return BigInteger.valueOf(n).multiply(factorial(n - 1));
        }
    }
}
```

```text
// 输入一个非负整数: 22
// 22 的阶乘为: 11240007277776080000
```

## 31. 十进制转二进制

![image](img/chapter_title_below.png)

```java
import java.util.Scanner;

public class DecimalToBinaryConverter {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("输入一个十进制数: ");

        int decimalNumber = scanner.nextInt();

        if (decimalNumber < 0) {
            System.out.println("请输入非负整数.");
            return;
        }

        String binaryEquivalent = decimalToBinary(decimalNumber);
        System.out.println(decimalNumber + " 的二进制为: " + binaryEquivalent);
    }

    private static String decimalToBinary(int num) {
        if (num == 0) {
            return "0";
        }

        StringBuilder binary = new StringBuilder();
        int n = num;

        while (n > 0) {
            binary.insert(0, n % 2);
            n /= 2;
        }

        return binary.toString();
    }
}
```

```text
// 输入一个十进制数: 10
// 10 的二进制为: 1010
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 32. 查找字符的 ASCII 值

![image](img/chapter_title_below.png)

```java
import java.util.Scanner;

public class AsciiValueFinder {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("输入一个字符: ");

        String input = scanner.nextLine().trim();

        if (input.length() == 1) {
            char character = input.charAt(0);
            int asciiValue = (int) character; // 将字符转换为 ASCII 值
            System.out.println(" + character + + 的 ASCII 值为: " + asciiValue);
        } else {
            System.out.println("请输入有效的单字符.");
        }

        scanner.close();
    }
}
```

```text
// 输入一个字符: a
// 'a' 的 ASCII 值为: 97
```



```java
import java.util.Scanner ;

public class PalindromeChecker {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a string: ");
        String input = scanner.nextLine().trim();
        String cleanedString = cleanString(input);
        if (isPalindrome(cleanedString)) {
            System.out.println("\"" + input + "\" is a palindrome.");
        } else {
            System.out.println("\"" + input + "\" is not a palindrome.");
        }
        scanner.close();
    }

    // Function to clean the string by removing non-alphanumeric characters and converting to lowercase
    private static String cleanString(String str) {
        StringBuilder cleaned = new StringBuilder();
        for (char c : str.toCharArray()) {
            if (Character.isLetterOrDigit(c)) {
                cleaned.append(Character.toLowerCase(c));
            }
        }
        return cleaned.toString();
    }

    // Function to check if a string is a palindrome
    private static boolean isPalindrome(String s) {
        String reversed = new StringBuilder(s).reverse().toString();
        return s.equals(reversed);
    }
}
// Enter a string: A man, a plan, a canal, Panama!
// "A man, a plan, a canal, Panama!" is a palindrome.
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 34. 按字母顺序排序单词

![image](img/chapter_title_below.png)

```java
iport java.util.Arrays ;

import java.util.Scanner;

public class SortWords {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        // Prompt user for a sentence or a list of words
        System.out.print("Enter a sentence or a list of words: ");
        String input = scanner.nextLine().trim();
        // Split the input into an array of words
        String[] wordsList = input.split("\\s+");
        // Sort the array of words in alphabetical order
        Arrays.sort(wordsList);
        // Display the sorted words
        System.out.println("Sorted Words:");
        System.out.println(String.join(", ", wordsList));
        scanner.close();
    }
}
// Enter a sentence or a list of words: ad d dwqdwq qw qwd sadasd wqdwq
// Sorted Words:
// ad, d, dwqdwq, qw, qwd, sadasd, wqdwq
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 35. 替换字符串中的字符

![image](img/chapter_title_below.png)

```java
iport java.util.Scanner ;

public class CharacterReplacement {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        // Prompt user for a string
        System.out.print("Enter a string: ");
        String inputString = scanner.nextLine().trim();
        if (inputString.isEmpty()) {
            System.out.println("Please enter a valid string.");
            return;
        }
        // Get target and replacement characters
        String targetChar = promptUser(scanner, "Enter the target: ");
        String replacementChar = promptUser(scanner, "Enter the replacement character: ");
        if (targetChar.length() == 1 && replacementChar.length() == 1) {
            // Replace occurrences of targetChar with replacementChar in inputString
            String modifiedString = inputString.replace(targetChar, replacementChar);
            System.out.println("Modified String: " + modifiedString);
        } else {
            System.out.println("Please enter single characters for target and replacement.");
        }
        scanner.close();
    }

    private static String promptUser(Scanner scanner, String message) {
        System.out.print(message);
        return scanner.nextLine().trim();
    }
}
/*
Enter a string: Hello World!
Enter the target: o
Enter the replacement character: a
Modified String: Hella Warld!
*/
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 36. 反转字符串

![image](img/chapter_title_below.png)

```java
iport java.util.Scanner ;

public class ReverseString {

    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        // Prompt user for a string

        System.out.print("Enter a string: ");

        String inputString = scanner.nextLine().trim(); // Remove trailing newline

        // Check if input is a valid string

        if (!inputString.isEmpty()) {

            // Reverse the string

            String reversedString = new StringBuilder(inputString).reverse().toString();

            // Display the reversed string

            System.out.println("Reversed String: " + reversedString);

        } else {

            System.out.println("Please enter a valid string.");

        }

        scanner.close();

    }

}

/*

Enter a string: Hello, World!

Reversed String: !dlroW ,olleH

*/
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 37. 检查字符在字符串中出现的次数

![image](img/chapter_title_below.png)

```java
iport java.util.Scanner ;

public class CountOccurrences {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        // Prompt user for a string
        System.out.print("Enter a string: ");
        String inputString = scanner.nextLine().trim(); // Remove trailing newline
        // Prompt user for a character to count
        System.out.print("Enter the character to count: ");
        String targetChar = scanner.nextLine().trim(); // Remove trailing newline
        // Check if inputs are valid
        if (!inputString.isEmpty() && targetChar.length() == 1) {
            // Count occurrences of the target character
            long count = inputString.chars()
                .filter(c -> c == targetChar.charAt(0))
                .count();
            // Display the result
            System.out.printf("Number of occurrences of '%s' in '%s': %d%n", targetChar, inputString, count);
        } else {
            System.out.println("Please enter a valid string and a character.");
        }
        scanner.close();
    }
}
/*
Enter a string: Hello, World!
Enter the character to count: o
Number of occurrences of 'o' in 'Hello, World!': 2
*/
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 38. 将字符串的首字母转换为大写

![image](img/chapter_title_below.png)



```java
iport java.util.Scanner;

public class CapitalizeFirstLetter {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        // Prompt user for a string
        System.out.print("Enter a string: ");
        String inputString = scanner.nextLine().trim(); // Remove trailing newline
        // Check if input is a valid string
        if (!inputString.isEmpty()) {
            // Capitalize the first letter
            String resultString = capitalizeFirstLetter(inputString);
            // Display the result
            System.out.println("Original String: " + inputString);
            System.out.println("String with First Letter Uppercase: " + resultString);
        } else {
            System.out.println("Please enter a valid string.");
        }
        scanner.close();
    }

    // Function to capitalize the first letter of a string
    private static String capitalizeFirstLetter(String s) {
        if (s.isEmpty()) {
            return s; // Return the original string if it's empty
        }
        // Capitalize the first character and append the rest of the string
        return s.substring(0, 1).toUpperCase() + s.substring(1);
    }
}
/*
Enter a string: hello world
Original String: hello world
String with First Letter Uppercase: Hello world
*/
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 39. 统计字符串中元音的次数

![image](img/chapter_title_below.png)

```java
iport java.util.Scanner;

public class CountVowels {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        // Prompt user for a string
        System.out.print("Enter a string: ");
        String inputString = scanner.nextLine().trim(); // Remove trailing newline
        // Check if input is a valid string
    }
}
```

```java
if (!inputString.isEmpty()) {
    // 调用函数并显示结果
    int numberOfVowels = countVowels(inputString);
    System.out.println("'" + inputString + "' 中的元音数量为: " + numberOfVowels);
} else {
    System.out.println("请输入一个有效的字符串.");
}

scanner.close();
}

// 统计字符串中元音数的函数
private static int countVowels(String s) {
    String vowels = "aeiouAEIOU";
    return (int) s.chars()
        .filter(c -> vowels.indexOf(c) != -1) // 检查字符是否为元音
        .count();
}
```

```java
/*
输入字符串: asd

'asd' 中的元音数量为: 1
*/
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 40. 检查字符串是否以特定字符开头和结尾

![image](img/chapter_title_below.png)

```java
import java.util.Scanner;

public class CheckStartAndEnd {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        // 提示用户输入字符串
        System.out.print("输入字符串: ");
        String inputString = scanner.nextLine().trim(); // 移除尾部换行
        // 检查输入是否为有效字符串
        if (inputString.isEmpty()) {
            System.out.println("请输入一个有效的字符串.");
            return;
        }
        String startChar = promptUser("输入起始字符: ");
        String endChar = promptUser("输入结束字符: ");
        // 检查字符串是否以指定的字符开头和结尾
        if (inputString.startsWith(startChar) && inputString.endsWith(endChar)) {
            System.out.printf("字符串 '%s' 以 '%s' 开头并以 '%s' 结尾。%n", inputString, startChar, endChar);
        } else {
            System.out.printf("字符串 '%s' 不以 '%s' 开头或以 '%s' 结尾。%n", inputString, startChar, endChar);
        }
        scanner.close();
    }

    // 提示用户输入的方法
    private static String promptUser(String message) {
        System.out.print(message);
        Scanner scanner = new Scanner(System.in);
        return scanner.nextLine().trim();
    }
}
```

```java
/*
输入字符串: asd

输入起始字符: a

输入结束字符: d

字符串 'asd' 以 'a' 开头并以 'd' 结尾。
*/
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 41. 替换字符串的所有出现位置

![image](img/chapter_title_below.png)

```java
public class ReplaceOccurrences {
    public static void main(String[] args) {
        // 示例字符串
        String originalString = "Hello world, world!";
        // 要替换的字符串
        String searchString = "world";
        // 替换字符串
        String replacementString = "universe";
        // 将 searchString 的所有出现替换为 replacementString
        String modifiedString = originalString.replace(searchString, replacementString);
        // 显示结果
        System.out.println("原始字符串: " + originalString);
        System.out.println("修改后的字符串: " + modifiedString);
    }
}
```

```java
/*
原始字符串: Hello world, world!

修改后的字符串: Hello universe, universe!
*/
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 42. 创建多行字符串

![image](img/chapter_title_below.png)

```java
public class MultilineString {
    public static void main(String[] args) {
        // 使用三引号创建多行字符串（Java 13 及更高版本）
        String multilineString = """
        这是一个多行字符串。
        它跨越了多行。
        你可以轻松地包含换行和缩进。
        """;
        System.out.println(multilineString);
    }
}
```

```java
/*
这是一个多行字符串。

它跨越了多行。

你可以轻松地包含换行和缩进。
*/
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 43. 将数字格式化为货币字符串

![image](img/chapter_title_below.png)

```java
import java.text.DecimalFormat;

public class CurrencyFormatter {
    public static void main(String[] args) {
        // 示例数字
        double amount = 1234567.89;
        // 格式化为货币字符串
        String formattedAmount = formatCurrency(amount);
        // 显示结果
        System.out.println("格式化后的金额: " + formattedAmount);
    }

    private static String formatCurrency(double amount) {
        DecimalFormat formatter = new DecimalFormat("$,######.00");
        return formatter.format(amount);
    }
}
```

```java
/*
格式化后的金额: $1,234,567.89
*/
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 44. 生成随机字符串

![image](img/chapter_title_below.png)

```java
import java.util.Random;

public class RandomString {
    private static final String ALPHUMERIC = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789";
    private static final Random random = new Random();

    public static void main(String[] args) {
        // 生成长度为 8 的随机字符串
        String randomString = generateRandomString(8);
        // 显示结果
        System.out.println("生成的随机字符串: " + randomString);
    }

    private static String generateRandomString(int length) {
        StringBuilder sb = new StringBuilder(length);
        for (int i = 0; i < length; i++) {
            // 随机选择一个字符
            int index = random.nextInt(ALPHUMERIC.length());
            sb.append(ALPHUMERIC.charAt(index));
        }
        return sb.toString();
    }
}
```

```java
/*
生成的随机字符串: a1B2c3D4
*/
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 45. 检查字符串是否以特定字符串开头

![image](img/chapter_title_below.png)

```java
public class StringStartsWith {
    public static void main(String[] args) {
        // 示例字符串
        String mainString = "Hello, World!";
        String searchString = "Hello";
        // 检查 mainString 是否以 searchString 开头
        boolean startsWith = mainString.startsWith(searchString);
        // 显示结果
        System.out.println("字符串以 '" + searchString + "' 开头吗? " + startsWith);
    }
}
```

```java
/*
字符串以 'Hello' 开头吗? true
*/
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 46. 去除字符串中的空格

![image](img/chapter_title_below.png)



```java
public class TrimString {
    public static void main(String[] args) {
        // 包含头部和尾空格的示例字符串
        String stringWithSpaces = "  Hello, World! ";
        // 修剪字符串
        String trimmedString = stringWithSpaces.trim();
        // 显示结果
        System.out.println("原始字符串: '" + stringWithSpaces + "'");
        System.out.println("裁剪后的字符串: '" + trimmedString + "'");
    }
}
```

```text
/*
原始字符串: '  Hello, World! '

裁剪后的字符串: 'Hello, World!'

*/
```

| ![image](img/chapter_title_corner_decoration_left.png) |  | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 47. 检查字符串是否包含子字符串

![image](img/chapter_title_below.png)

```java
public class ContainsSubstring {
    public static void main(String[] args) {
        // 示例字符串
        String mainString = "Hello, World!";
        String substringToCheck = "World";
        // 检查 mainString 是否包含 substringToCheck
        boolean containsSubstring = mainString.contains(substringToCheck);
        // 显示结果
        System.out.println("字符串是否包含 '" + substringToCheck + "'? " + containsSubstring);
    }
}
```

```java
System.out.println("字符串是否包含 '" + substringToCheck + "'? " + containsSubstring);
}

}

/*
字符串是否包含 'World'? true
*/
```

## 48. 比较两个字符串

```java
public class CompareStrings {
    public static void main(String[] args) {
        // 字符串
        String string1 = "Hello";
        String string2 = "hello";

        // 区分大小写的比较
        boolean caseSensitiveComparison = string1.equals(string2);

        // 不区分大小写的比较
        boolean caseInsensitiveComparison = string1.equalsIgnoreCase(string2);

        // 显示结果
        System.out.println("区分大小写的比较: " + caseSensitiveComparison);
        System.out.println("不区分大小写的比较: " + caseInsensitiveComparison);
    }
}
```

```text
/*
区分大小写的比较: false
不区分大小写的比较: true
*/
```

## 49. 将字符串编码为 Base64

```java
import java.util.Base64 ;

public class EncodeStringToBase64 {
    public static void main(String[] args) {
        // 原始字符串
        String originalString = "Hello, 你好!";

        // 将字符串编码为 Base64
        String base64EncodedString = Base64.getEncoder().encodeToString(originalString.getBytes());

        // 显示结果
        System.out.println("原始字符串: " + originalString);
        System.out.println("Base64 编码后的字符串: " + base64EncodedString);
    }
}
```

```text
/*
原始字符串: Hello, 你好!
Base64 编码后的字符串: SGVsbG8sIOS9oOWlvSE=
*/
```

## 50. 替换字符串中所有的字符

```java
public class ReplaceCharacterInString {
    public static void main(String[] args) {
        // 示例字符串
        String originalString = "Hello, World!";

        // 要替换的字符
        char charToReplace = 'l';

        // 替换字符
        char replacementChar = 'x';

        // 将所有的 charToReplace 替换为 replacementChar
        String modifiedString = originalString.replace(charToReplace, replacementChar);

        // 显示结果
        System.out.println("原始字符串: " + originalString);
        System.out.println("修改后的字符串: " + modifiedString);
    }
}
```

```text
/*
原始字符串: Hello, World!
修改后的字符串: Hexxo, Worxd!
*/
```

## 51. 将所有的换行符替换为

```java
public class ReplaceLineBreaks {
    public static void main(String[] args) {
        // 带有换行符的示例字符串
        String stringWithLineBreaks = "Hello,\nWorld!\nThis is a new line.";

        // 替换字符串
        String replacementString = "-";

        // 将所有的换行符替换为替换字符串
        String stringWithoutLineBreaks = stringWithLineBreaks.replace("\n", replacementString);

        // 显示结果
        System.out.println("原始字符串:");
        System.out.println(stringWithLineBreaks);
        System.out.println("\n 不带换行符的字符串:");
        System.out.println(stringWithoutLineBreaks);
    }
}
```

```text
/*
原始字符串:
Hello,
World!
This is a new line.
不带换行符的字符串:
Hello,-World!-This is a new line.
*/
```

## 52. 检查闰年

```java
public class LeapYearChecker {
    // 检查年份是否为闰年的方法
    public static boolean isLeapYear(int year) {
        return (year % 4 == 0 && year % 100 != 0) || (year % 400 == 0);
    }

    public static void main(String[] args) {
        // 要检查的年份
        int yearToCheck = 2024;
        // 检查是否为闰年
        if (isLeapYear(yearToCheck)) {
            System.out.println(yearToCheck + " 是闰年.");
        } else {
            System.out.println(yearToCheck + " 不是闰年.");
        }
    }
}
```

```text
/*
2024 是闰年。
*/
```

## 53. 格式化日期

```java
import java.time.LocalDateTime ;
import java.time.format.DateTimeFormatter;

public class DateFormatter {
    public static void main(String[] args) {
        // 获取当前日期
        LocalDateTime currentDate = LocalDateTime.now();
        // 格式日期
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("EEEE, MMMM dd, yyyy");
        String formattedDate = currentDate.format(formatter);
        // 显示结果
        System.out.println("格式化后的日期: " + formattedDate);
    }
}
```

```text
/*
格式化后的日期: Friday, September 20, 2024
*/
```

## 54. 显示当前日期

```java
import java.time.LocalDate ;
import java.time.format.DateTimeFormatter;

public class CurrentDate {
    public static void main(String[] args) {
        // 获取当前日期
        LocalDate currentDate = LocalDate.now();
        // 格式化当前日期
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("MM/dd/yyyy");
        String formattedDate = currentDate.format(formatter);
        // 显示结果
        System.out.println("当前日期: " + formattedDate);
    }
}
```

```text
/*
当前日期: 09/20/2024
*/
```

## 55. 比较两个日期的值

```java
import java.time.LocalDate ;

public class CompareDates {
    public static void main(String[] args) {
        // 解析示例日期
        LocalDate date1 = LocalDate.of(2022, 1, 1);
        LocalDate date2 = LocalDate.of(2023, 1, 1);

        // 比较日期
        if (date1.isBefore(date2)) {
            System.out.println(date1 + " 早于 " + date2);
        } else if (date1.isAfter(date2)) {
            System.out.println(date1 + " 晚于 " + date2);
        } else {
            System.out.println(date1 + " 等于 " + date2);
        }
    }
}
```

```text
/*
2022-01-01 早于 2023-01-01
*/
```

## 56. 创建倒计时器

```java
import java.time.LocalDateTime ;
import java.time.Duration;

public class CountdownTimer {
    public static void main(String[] args) throws InterruptedException {
        // 设置目标日期为现在 1 分钟后
        LocalDateTime targetDate = LocalDateTime.now().plusMinutes(1);

        while (true) {
            // 计算剩余时间
            Duration timeDiff = Duration.between(LocalDateTime.now(), targetDate);

            if (timeDiff.isNegative() || timeDiff.isZero()) {
                break; // 如果倒计时结束则退出循环
            }

            long days = timeDiff.toDays();
            long hours = timeDiff.toHours() % 24;
            long minutes = timeDiff.toMinutes() % 60;
            long seconds = timeDiff.getSeconds() % 60;

            // 显示倒计时
            System.out.printf("倒计时: %dd %dh %dm %ds%n", days, hours, minutes, seconds);

            Thread.sleep(1000); // 睡眠 1 秒
        }

        System.out.println("倒计时结束!");
    }
}
```

```text
倒计时：0d 0h 0m 56s

倒计时结束！

*/
```

| ![image](img/chapter_title_corner_decoration_left.png) |  | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 57. 从数组中移除特定元素

![image](img/chapter_title_below.png)

```java
import java.util.ArrayList;
import java.util.Arrays;

public class RemoveItemFromArray {
    public static void main(String[] args) {
        // 示例列表
        ArrayList<Integer> originalList = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 5));
        int itemToRemove = 3;

        // 查找要删除的元素的位置
        if (originalList.remove(Integer.valueOf(itemToRemove))) {
            System.out.println("原始列表: " + originalList);
        } else {
            System.out.println("列表中未找到该元素.");
        }
    }
}
```

```text
/*
原始列表: [1, 2, 4, 5]

*/
```

| ![image](img/chapter_title_corner_decoration_left.png) |  | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 58. 检查数组是否包含指定值

![image](img/chapter_title_below.png)



```java
import java.util.Arrays;

public class CheckArrayContainsValue {
    public static void main(String[] args) {
        // 示例数组
        int[] myList = {1, 2, 3, 4, 5};
        int valueToCheck = 3;

        // 检查数组是否包含指定值
        boolean containsValue = contains(myList, valueToCheck);

        // 显示结果
        System.out.println("列表是否包含 " + valueToCheck + "? " + containsValue);
    }

    // 检查数组是否包含指定值的方法
    public static boolean contains(int[] array, int value) {
        for (int num : array) {
            if (num == value) {
                return true; // 找到值
            }
        }
        return false; // 未找到值
    }
}
```

```
列表是否包含 3? true
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 59. 在数组中插入元素

![image](img/chapter_title_below.png)

```java
import java.util.ArrayList;

public class InsertItemInArray {
    public static void main(String[] args) {
        // 示例 ArrayList
        ArrayList<Integer> myList = new ArrayList<>();
        myList.add(1);
        myList.add(2);
        myList.add(3);
        myList.add(4);
        myList.add(5);
        int itemToInsert = 6;

        // 将元素插入 ArrayList 的末尾
        myList.add(itemToInsert);

        // 显示结果
        System.out.println("插入后的列表: " + myList);
    }
}
```

```
插入后的列表: [1, 2, 3, 4, 5, 6]
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 60. 从数组中获取随机元素

![image](img/chapter_title_below.png)

```java
import java.util.ArrayList;
import java.util.List;
import java.util.Random;

public class GetRandomItemFromArray {
    public static void main(String[] args) {
        // 示例 ArrayList
        List<Integer> myList = new ArrayList<>();
        for (int i = 1; i <= 10; i++) {
            myList.add(i);
        }

        // 创建随机数生成器
        Random random = new Random();

        // 从 ArrayList 中获取随机元素
        if (!myList.isEmpty()) {
            int randomIndex = random.nextInt(myList.size());
            int randomItem = myList.get(randomIndex);
            // 显示结果
            System.out.println("随机元素: " + randomItem);
        } else {
            System.out.println("列表为空.");
        }
    }
}
```

```
随机元素: 4
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 61. 执行两个数组之间的交集

![image](img/chapter_title_below.png)

```java
import java.util.ArrayList;
import java.util.HashSet;
import java.util.List;
import java.util.Set;

public class ArrayIntersection {
    public static void main(String[] args) {
        // 示例 ArrayList
        List<Integer> list1 = new ArrayList<>();
        List<Integer> list2 = new ArrayList<>();
        // 填充第一个列表
        list1.add(1);
        list1.add(2);
        list1.add(3);
        list1.add(4);
        list1.add(5);
        // 填充第二个列表
        list2.add(3);
        list2.add(4);
        list2.add(5);
        list2.add(7);
        // 从列表创建 HashSets
        Set<Integer> set1 = new HashSet<>(list1);
        Set<Integer> set2 = new HashSet<>(list2);
        // 两个 HashSets 的交集
        set1.retainAll(set2);
        // 显示结果
        System.out.println("交集: " + set1);
    }
}
```

```
交集: [3, 4, 5]
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 62. 将数组拆分为小块

![image](img/chapter_title_below.png)

```java
import java.util.ArrayList;
import java.util.List;

public class ChunkArray {
    public static void main(String[] args) {
        // 示例数组
        List<Integer> myList = List.of(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);
        int chunkSize = 3;

        // 将数组拆分成块
        List<List<Integer>> chunks = chunkList(myList, chunkSize);

        // 显示结果
        System.out.println("拆分后的块: " + chunks);
    }

    // 将列表拆分成块的方法
    public static <T> List<List<T>> chunkList(List<T> list, int size) {
        List<List<T>> chunks = new ArrayList<>();
        for (int i = 0; i < list.size(); i += size) {
            int end = Math.min(i + size, list.size());
            chunks.add(list.subList(i, end));
        }
        return chunks;
    }
}
```

```
拆分后的块: [[1, 2, 3], [4, 5, 6], [7, 8, 9], [10]]
```

![image](img/chapter_title_above.png)

## 65. 生成两个数字之间的随机数

![image](img/chapter_title_below.png)

```java
import java.util.Random;

public class RandomNumberGenerator {
    public static void main(String[] args) {
        int minVal = 1;
        int maxVal = 100;
        int randomNum = getRandomNumber(minVal, maxVal); // 生成一个 1 到 100 之间的随机数
        System.out.println("Random Number: " + randomNum);
    }

    public static int getRandomNumber(int minVal, int maxVal) {
        Random rand = new Random(); // 创建一个 Random 对象
        return rand.nextInt(maxVal - minVal + 1) + minVal; // 在范围 [minVal, maxVal] 内生成一个随机数
    }
}
```

```
Random Number: 48
```

![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png)

![image](img/chapter_title_above.png)

## 66. 最连续登录天数

![image](img/chapter_title_below.png)

```java
public class LongestDailyStreak {
    public static void main(String[] args) {
        // 测试用例
        System.out.println(dailyStreak(new boolean[]{true, true, false, true})); // 输出: 2
        System.out.println(dailyStreak(new boolean[]{false, false, false}));    // 输出: 0
        System.out.println(dailyStreak(new boolean[]{true, true, true, false, true, true})); // 输出: 3
    }

    public static int dailyStreak(boolean[] logins) {
        int maxStreak = 0;
        int currentStreak = 0;
        for (boolean loggedIn : logins) {
            if (loggedIn) {
                currentStreak++; // 如果登录了，增加当前天数
                if (currentStreak > maxStreak) {
                    maxStreak = currentStreak; // 如果需要，更新最大连续天数
                }
            } else {
                currentStreak = 0; // 如果未登录，重置连续天数
            }
        }
        return maxStreak; // 返回找到的最长天数
    }
}
```

```
2

0

3
```

![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png)

![image](img/chapter_title_above.png)

## 67. 验证邮箱地址

![image](img/chapter_title_below.png)

```java
import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class EmailValidator {
    // 验证邮箱地址的方法
    public static boolean validateEmail(String email) {
        // 用于基础邮箱验证的正则表达式
        String emailRegex = "^[^\\s@]+@[^\\s@]+\\.[^\\s@]+$";
        // 编译模式
        Pattern pattern = Pattern.compile(emailRegex);
        // 将邮箱与正则表达式进行匹配
        Matcher matcher = pattern.matcher(email);
        return matcher.matches();
    }

    public static void main(String[] args) {
        // 示例用法
        String emailToValidate = "example@email.com";
        if (validateEmail(emailToValidate)) {
            // 输出: 邮箱有效
            System.out.println("Email is valid");
        } else {
            // 输出: 邮箱无效
            System.out.println("Email is not valid");
        }
    }
}
```

![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png)

![image](img/chapter_title_above.png)

## 68. 记录温度

![image](img/chapter_title_below.png)



```java
import java.util.Arrays;

public class TemperatureRecord {
    // 记录温度的方法
    public static int[][] recordTemps(int[][] record, int[][] current) {
        for (int i = 0; i < current.length; i++) {
            int[] dailyTemps = current[i];
            // 如果当日最低温度比记录的低，则更新记录最低温
            if (dailyTemps[0] < record[i][0]) {
                record[i][0] = dailyTemps[0];
            }
            // 如果当日最高温度比记录的高，则更新记录最高温
            if (dailyTemps[1] > record[i][1]) {
                record[i][1] = dailyTemps[1];
            }
        }
        return record;
    }

    public static void main(String[] args) {
        // 初始温度记录
        int[][] records = {
            {34, 82}, {24, 82}, {20, 89}, {5, 88}, {9, 88}, {26, 89}, {27, 83}
        };
        // 本周的温度
        int[][] currentWeekTemps = {
            {44, 72}, {19, 70}, {40, 69}, {39, 68}, {33, 64}, {36, 70}, {38, 69}
        };
        // 更新记录
        int[][] updatedRecords = recordTemps(records, currentWeekTemps);
        // 输出 [[34, 82], [19, 72], [20, 89], [5, 88], [9, 88], [26, 89], [27, 83]]
        System.out.println(Arrays.deepToString(updatedRecords));
    }
}
```

![image](img/chapter_title_corner_decoration_left.png)  |  | ![image](img/chapter_title_corner_decoration_right.png)

![image](img/chapter_title_above.png)

# 69. 卡普卡数 (Kaprekar Numbers)

![image](img/chapter_title_below.png)

```java
public class KaprekarNumber {
    // 判断数字是否为卡普卡数的方法
    public static boolean Kaprekar(long n) {
        if (n == 0 || n == 1) {
            return true; // 0 和 1 是卡普卡数
        }
        // 计算 n 的平方
        long square = n * n;
        String squareStr = Long.toString(square);
        int len = squareStr.length();
        // 将平方分成左部分和右部分
        String leftStr, rightStr;
        if (len == 1) {
            leftStr = ""; // 只有右部分
            rightStr = squareStr;
        } else {
            int splitIndex = len / 2;
            leftStr = squareStr.substring(0, len - splitIndex);
            rightStr = squareStr.substring(len - splitIndex);
        }
        // 将左右部分转换为数字
        long left = leftStr.isEmpty() ? 0 : Long.parseLong(leftStr);
        long right = rightStr.isEmpty() ? 0 : Long.parseLong(rightStr);
        // 检查左右部分之和是否等于 n
        return left + right == n;
    }

    public static void main(String[] args) {
        // 测试用例
        // 输出: false
        System.out.println("Kaprekar(3) ➞ " + Kaprekar(3));
        // 输出: false
        System.out.println("Kaprekar(5) ➞ " + Kaprekar(5));
        // 输出: true
        System.out.println("Kaprekar(297) ➞ " + Kaprekar(297));
    }
}
```

![image](img/chapter_title_corner_decoration_left.png)  |  | ![image](img/chapter_title_corner_decoration_right.png)

![image](img/chapter_title_above.png)

## 70. 向线程定时函数传递参数

![image](img/chapter_title_below.png)

```java
import java.util.concurrent.Executors;
import java.util.concurrent.ScheduledExecutorService;
import java.util.concurrent.TimeUnit;

public class TimerExample {
    // 接收参数并打印的方法
    public static void myFunction(String parameter) {
        System.out.println("Parameter received: " + parameter);
    }

    public static void main(String[] args) {
        // 定义参数
        String myParameter = "Hello, world!";
        // 创建单线程定时执行服务
        ScheduledExecutorService executor = Executors.newSingleThreadScheduledExecutor();
        // 定义一个延迟执行的任务
        Runnable delayedExecution = () -> myFunction(myParameter);
        // 调度任务，延迟 1 秒执行
        executor.schedule(delayedExecution, 1, TimeUnit.SECONDS);
        // 任务完成后关闭执行器
        executor.shutdown();
    }
}
```

![image](img/chapter_title_corner_decoration_left.png)  |  | ![image](img/chapter_title_corner_decoration_right.png)

![image](img/chapter_title_above.png)

## 71. 生成数字和字符范围

![image](img/chapter_title_below.png)

```java
import java.util.List;
import java.util.ArrayList;

public class RangeGenerator {
    // 生成从开始到结束数字范围的方法
    public static List<Integer> generateNumberRange(int start, int end) {
        List<Integer> numberRange = new ArrayList<>();
        for (int i = start; i <= end; i++) {
            numberRange.add(i);
        }
        return numberRange;
    }

    // 生成从开始到结束字符范围的方法
    public static List<Character> generateCharRange(char start, char end) {
        List<Character> charRange = new ArrayList<>();
        for (char c = start; c <= end; c++) {
            charRange.add(c);
        }
        return charRange;
    }

    public static void main(String[] args) {
        // 生成 1 到 5 的数字
        List<Integer> numberRange = generateNumberRange(1, 5);
        System.out.println("Number Range: " + numberRange);
        // 生成 'a' 到 'e' 的字符
        List<Character> charRange = generateCharRange('a', 'e');
        System.out.println("Character Range: " + charRange);
    }
}
```

## 72. 执行函数重载

```java
public class FunctionOverloading {

    // 无参数方法
    public static void exampleFunction() {
        System.out.println("No arguments");
    }

    // 带有一个数字参数的方法
    public static void exampleFunction(int n) {
        System.out.println("One number argument: " + n);
    }

    // 有字符串和数字参数的方法
    public static void exampleFunction(String s, int n) {
        System.out.println("String and number arguments: " + s + ", " + n);
    }

    public static void main(String[] args) {
        // 调用无参数方法
        exampleFunction();
        // 调用带一个整数参数的方法
        exampleFunction(42);
        // 调用带一个字符串和一个整数参数的方法
        exampleFunction("Hello", 7);
        // 由于方法重载，下行可以正常工作：
        // exampleFunction("world", 7);
    }
}
```

## 73. 翻转图像

```java
import java.util.Arrays;

public class ImageReverser {

    // 翻转二值图像的方法
    public static int[][] reverseImage(int[][] image) {
        int[][] reversedImage = new int[image.length][];
        for (int i = 0; i < image.length; i++) {
            reversedImage[i] = new int[image[i].length];
            for (int j = 0; j < image[i].length; j++) {
                // 翻转像素 (1 -> 0, 0 -> 1)
                reversedImage[i][j] = 1 - image[i][j];
            }
        }
        return reversedImage;
    }

    public static void main(String[] args) {
        //  1
        int[][] image1 = {
            {1, 0, 0},
            {0, 1, 0},
            {0, 0, 1}
        };
        int[][] reversed1 = reverseImage(image1);
        System.out.println(Arrays.deepToString(reversed1));
        // ➞ [[0, 1, 1], [1, 0, 1], [1, 1, 0]]

        // 示例 2
        int[][] image2 = {
            {1, 1, 1},
            {0, 0, 0}
        };
        int[][] reversed2 = reverseImage(image2);
        System.out.println(Arrays.deepToString(reversed2));
        // ➞ [[0, 0, 0], [1, 1, 1]]

        // 示例 3
        int[][] image3 = {
            {1, 0, 0},
            {1, 0, 0}
        };
        int[][] reversed3 = reverseImage(image3);
        System.out.println(Arrays.deepToString(reversed3));
        // ➞ [[0, 1, 1], [0, 1, 1]]
    }
}
```

## 74. 不要大喊

```java
public class NoYelling {

    // 移除句子末尾多余的感叹号或问号的方法
    public static String noYelling(String sentence) {
        // 移除句子末尾的 '!' 或 '?'
        String trimmed = sentence.replaceAll("[!?]+$", "");
        char lastChar = sentence.charAt(sentence.length() - 1);
        // 检查最后一个字符是否为 '!' 或 '?'
        if (lastChar == '!') {
            return trimmed + "!";
        } else if (lastChar == '?') {
            return trimmed + "?";
        } else {
            return sentence;
        }
    }

    public static void main(String[] args) {
        System.out.println(noYelling("What went wrong?????????"));  // ➞ "What went wrong?"
        System.out.println(noYelling("Oh my goodness!!!"));         // ➞ "Oh my goodness!"
        System.out.println(noYelling("I just!!! can!!! not!!! believe!!! it!!!")); // ➞ "I just!!! can!!! not!!! believe!!! it!"
        System.out.println(noYelling("Oh my goodness!"));           // ➞ "Oh my goodness!"
        System.out.println(noYelling("I just cannot believe it.")); // ➞ "I just cannot believe it."
    }
}
```

## 75. 检查数字是浮点数还是整数



```java
public class NumberChecker {

    // 检查数字是整数还是浮点数的方法
    public static void checkType(Object number) {
        if (number instanceof Integer) {
            System.out.println(number + " is an integer.");
        } else if (number instanceof Double) {
            System.out.println(number + " is a float.");
        } else if (number instanceof String) {
            try {
                // 尝试解析字符串为整数
                Integer.parseInt((String) number);
                System.out.println(number + " is an integer.");
            } catch (NumberFormatException e1) {
                try {
                    // 尝试解析字符串为双精度浮
                    Double.parseDouble((String) number);
                    System.out.println(number + " is a float.");
                } catch (NumberFormatException e2) {
                    System.out.println(number + " is a float.");
                }
            }
        } else {
            System.out.println(number + " is a float.");
        }
    }

    public static void main(String[] args) {
        checkType(5);      // 输出: 5 is an integer.
        checkType(5.5);    // 输出: 5.5 is a float.
        checkType("5");    // 输出: 5 is an integer.
        checkType("5.5");  // 输出: 5.5 is a float.
    }
}
```

## 76. 传递函数

```java
import java.util.function.BiFunction;

public class FunctionExample {

    // 接收两个整数和一个 BiFunction
    public static int operateNumbers(int a, int b, BiFunction<Integer, Integer, Integer> operation) {
        return operation.apply(a, b); // 调用传递函数
    }

    public static void main(String[] args) {
        // 使用加法 lambda
        int result1 = operateNumbers(3, 5, (x, y) -> x + y);
        System.out.println("Result of addition: " + result1); // 输出: 8

        // 使用乘法 lambda
        int result2 = operateNumbers(3, 5, (x, y) -> x * y);
        System.out.println("Result of multiplication: " + result2); // 输出: 15
    }
}
```

## 77. 滑行数字

```java
import java.util.ArrayList;
import java.util.List;

public class SlideyNumbers {

    // 检查数字是否为滑行数字
    public static boolean isSlidey(int n) {
        // 将数字转换为字符串并提取数字
        List<Integer> digits = new ArrayList<>();
        for (char c : Integer.toString(n).toCharArray()) {
            digits.add(Character.getNumericValue(c));
        }

        // 单位数被认为是滑行数字
        if (digits.size() <= 1) {
            return true;
        }

        // 检查相邻数字之间的绝对差
        for (int i = 0; i < digits.size() - 1; i++) {
            if (Math.abs(digits.get(i) - digits.get(i + 1)) != 1) {
                return false; // 如果差不是 1，则不是滑行数字
            }
        }

        return true; // 如果通过所有检查，则是滑行数字
    }

    public static void main(String[] args) {
        // 测试用例
        System.out.println(isSlidey(123454321)); // 输出: true
        System.out.println(isSlidey(54345));     // 输出: true
        System.out.println(isSlidey(987654321)); // 输出: true
        System.out.println(isSlidey(1123));      // 输出: false
        System.out.println(isSlidey(1357));      // 输出: false
    }
}
```

## 78. 移除文本中的所有空格

```java
public class RemoveWhitespaces {

    public static void main(String[] args) {
        String textWithWhitespaces = "This is a text with spaces";
        String textWithoutWhitespaces = removeWhitespaces(textWithWhitespaces);

        System.out.println("Original Text: " + textWithWhitespaces);
        System.out.println("Text without Whitespaces: " + textWithoutWhitespaces);
    }

    public static String removeWhitespaces(String inputText) {
        // 将所有空白字符替换为空字符串
        return inputText.replaceAll("\\s", "");
    }
}

// 输出:
// Original Text: This is a text with spaces
// Text without Whitespaces: Thisisatextwithspaces
```

## 79. 写入控制台

```java
public class ConsoleOutput {
    public static void main(String[] args) {
        // 向控制台写入消息
        System.out.println("Hello, world!");

        // 你也可以打印变量或表达式
        int number = 42;
        System.out.println("The answer is: " + number);

        // 可以在一个语句中打印多个值
        String firstName = "John";
        String lastName = "Doe";
        System.out.println("Full Name: " + firstName + " " + lastName);
    }
}

// 输出:
// Hello, world!
// The answer is: 42
// Full Name: John Doe
```

## 80. 将日期转换为数字

```java
public class DateToNumber {
    public static void main(String[] args) {
        // 获取自 Unix 纪以来的当前毫秒数
        long millisecondsSinceEpoch = System.currentTimeMillis();

        // 打印毫秒的数值表示
        System.out.println("Current Time in milliseconds since Unix Epoch: " + millisecondsSinceEpoch);
    }
}

// 输出:
// Current Time in milliseconds since Unix Epoch: 1726202472472
```

## 81. 求两个数字的平均值

```java
public class FindAverage {
    public static double findAverage(double num1, double num2) {
        // 计算两个数的和
        double total = num1 + num2;

        // 通过将和除以 2 来计算平均值
        return total / 2.0;
    }

    public static void main(String[] args) {
        double number1 = 10.0;
        double number2 = 20.0;
        double result = findAverage(number1, number2);

        System.out.println("The average of " + number1 + " and " + number2 + " is: " + result);
    }
}

// 输出:
// The average of 10.0 and 20.0 is: 15.0
```

## 82. 计算圆的面积

```java
public class CircleArea {
    public static double calculateCircleArea(double radius) throws IllegalArgumentException {
        // 检查半径是否有效数字
        if (radius <= 0) {
            throw new IllegalArgumentException("Invalid radius. Please provide a positive number.");
        }

        // 计算面积
        return Math.PI * Math.pow(radius, 2);
    }

    public static void main(String[] args) {
        double radius = 5.0;

        try {
            double area = calculateCircleArea(radius);
            System.out.println("The area of a circle with radius " + radius + " is: " + area);
        } catch (IllegalArgumentException e) {
            System.out.println(e.getMessage());
        }
    }
}

// 输出:
// The area of a circle with radius 5.0 is: 78.53981633974483
```

## 83. 数字字母表

```java
public class NumberedAlphabet {
    public static String alphNum(String s) {
        StringBuilder result = new StringBuilder();

        for (char c : s.toUpperCase()) {
            // 计算在字母表中的位置
            int index = c - 'A';
            result.append(index).append(" ");
        }

        // 去除结尾的空格
        return result.toString().trim();
    }

    public static void main(String[] args) {
        String[] examples = {"XYZ", "ABCDEF", "JAVCRIPT"};

        for (String example : examples) {
            String result = alphNum(example);
            System.out.println(example + "➞ " + result);
        }
    }
}

// 输出:
// XYZ ➞ 23 24 25
// ABCDEF ➞ 0 1 2 3 4 5
// JAVCRIPT ➞ 9 0 21 17 18 15 12 19
```



```java
int[] reversedArray = originalArray.clone(); // 克隆原始数组

reverseArray(reversedArray); // 反转克隆数组

System.out.println("Original Array: " + Arrays.toString(originalArray));

System.out.println("Reversed Array: " + Arrays.toString(reversedArray));

}

}

// 输出:

// Original Array: [1, 2, 3, 4, 5]

// Reversed Array: [5, 4, 3, 2, 1]
```

## 94. 计算单利

```java
public class SimpleInterestCalculator {
    // 计算单利的方法
    public static double calculateSimpleInterest(double principal, double rate, double time) throws IllegalArgumentException {
        // 检查输入是否为有效的正数
        if (principal <= 0.0 || rate <= 0.0 || time <= 0.0) {
            throw new IllegalArgumentException("输入无效。请提供有效的正数。");
        }
        // 计算单利
        return (principal * rate * time) / 100.0;
    }

    public static void main(String[] args) {
        double principalAmount = 1000.0;
        double interestRate = 5.0;  // 5%
        double investmentTime = 2.0; // 2 年
        try {
            double interestAmount = calculateSimpleInterest(principalAmount, interestRate, investmentTime);
            System.out.printf("本金: $%.2f%n", principalAmount);
            System.out.printf("利率: %.2f%%%n", interestRate);
            System.out.printf("投资时间: %.2f 年%n", investmentTime);
            System.out.printf("单利: $%.2f%n", interestAmount);
        } catch (IllegalArgumentException e) {
            System.out.println(e.getMessage());
        }
    }
}
// 输出:
// 本金: $1000.00
// 利率: 5.00%
// 投资时间: 2.00 年
// 单利: $100.00
```

## 95. 微型数独检查

```java
import java.util.HashSet;

public class MiniSudoku {
    // 检查 3x3 网格是否为有效的微型数独
    public static boolean isMiniSudoku(int[][] square) {
        HashSet<Integer> seen = new HashSet<>();
        // 检查网格是否为 3x3
        if (square.length != 3 || square[0].length != 3) {
            return false; // 尺寸无效
        }
        for (int[] row : square) {
            for (int num : row) {
                // 检查数字是否在有效范围内 (1-9)
                if (num < 1 || num > 9) {
                    return false;
                }
                // 检查是否有重复
                if (!seen.add(num)) {
                    return false;
                }
            }
        }
        // 如果所有数字恰好出现一次且在范围内，返回 true
        return true;
    }

    public static void main(String[] args) {
        int[][] validSudoku = {
            {1, 3, 2},
            {9, 7, 8},
            {4, 5, 6}
        };
        int[][] invalidSudoku1 = {
            {1, 1, 3},
            {6, 5, 4},
            {8, 7, 9}
        };
        int[][] invalidSudoku2 = {
            {0, 1, 2},
            {6, 4, 5},
            {9, 8, 7}
        };
        int[][] validSudoku2 = {
            {8, 9, 2},
            {5, 6, 1},
            {3, 7, 4}
        };
        System.out.println("isMiniSudoku(validSudoku) = " + isMiniSudoku(validSudoku)); // true
        System.out.println("isMiniSudoku(invalidSudoku1) = " + isMiniSudoku(invalidSudoku1)); // false
        System.out.println("isMiniSudoku(invalidSudoku2) = " + isMiniSudoku(invalidSudoku2)); // false
        System.out.println("isMiniSudoku(validSudoku2) = " + isMiniSudoku(validSudoku2)); // true
    }
}
// 输出:
// isMiniSudoku(validSudoku) = true
// isMiniSudoku(invalidSudoku1) = false
// isMiniSudoku(invalidSudoku2) = false
// isMiniSudoku(validSudoku2) = true
```

## 96. 检查数字是否为完美数

```java
public class PerfectNumber {
    // 检查一个数字是否为完美数
    public static boolean isPerfectNumber(int number) {
        if (number < 2) {
            return false; // 1 及以下不可能是完美数
        }
        // 计算因数的和
        int sumOfDivisors = 1; // 从 1 开始，因为 1 是任何数字的因子
        int sqrt = (int) Math.sqrt(number);
        for (int i = 2; i <= sqrt; i++) {
            if (number % i == 0) {
                sumOfDivisors += i;
                if (i != number / i) {
                    sumOfDivisors += number / i;
                }
            }
        }
        // 检查因数的和是否等于原数
        return sumOfDivisors == number;
    }

    public static void main(String[] args) {
        int testNumber = 28;
        boolean result = isPerfectNumber(testNumber);
        System.out.println("数字 " + testNumber + " 是完美数吗? " + result);
    }
}
// 输出:
// 数字 28 是完美数吗? true
```

## 97. 计算圆柱体积

```java
public class Cylinder {
    // 计算圆柱体积的方法
    public static double calculateVolume(double radius, double height) {
        if (radius <= 0 || height <= 0) {
            throw new IllegalArgumentException("半径和高度必须为正数");
        }
        return Math.PI * Math.pow(radius, 2) * height;
    }

    public static void main(String[] args) {
        double radius = 5.0;
        double height = 10.0;
        try {
            double volume = calculateVolume(radius, height);
            System.out.printf("圆柱体积: %.2f%n", volume);
        } catch (IllegalArgumentException e) {
            System.out.println(e.getMessage());
        }
    }
}
// 输出:
// 圆柱体积: 785.40
```

## 98. 获取学生列表最高分

```java
import java.util.List;
import java.util.Collections;

class Student {
    private String name;
    private int score;

    public Student(String name, int score) {
        this.name = name;
        this.score = score;
    }

    public int getScore() {
        return score;
    }
}

public class GradeManager {
    // 获取学生列表中最高分的方法
    public static int getHighestScore(List<Student> students) {
        if (students == null || students.isEmpty()) {
            return 0;
        }
        return students.stream()
                .mapToInt(Student::getScore)
                .max()
                .orElse(0);
    }

    public static void main(String[] args) {
        List<Student> students = List.of(
            new Student("Jacek", 85),
            new Student("Ewa", 92),
            new Student("Zygmunt", 78)
        );
        int highest = getHighestScore(students);
        System.out.println("最高分: " + highest);
    }
}
// 输出:
// 最高分: 92
```

## 99. 两个数组的交集

```java
import java.util.ArrayList;
import java.util.HashSet;
import java.util.List;

public class ArrayIntersection {
    // 查找两个数组交集的方法
    public static List<Integer> findIntersection(int[] arr1, int[] arr2) {
        // 将第一个数组转换为 HashSet 以提高查找效率
        HashSet<Integer> set1 = new HashSet<>();
        for (int num : arr1) {
            set1.add(num);
        }
        // 使用 List 收集交集
        List<Integer> intersection = new ArrayList<>();
        for (int num : arr2) {
            if (set1.contains(num)) {
                intersection.add(num);
            }
        }
        return intersection;
    }

    public static void main(String[] args) {
        int[] arr1 = {1, 2, 3, 4, 5};
        int[] arr2 = {3, 4, 5, 6, 7};
        List<Integer> result = findIntersection(arr1, arr2);
        System.out.println("数组交集: " + result);
    }
}
// 输出:
// 数组交集: [3, 4, 5]
```

## 100. 英尺转换为米

```java
public class Main {
    public static double feetToMeters(double feet) {
        // 将英尺转换为米
        return feet * 0.3048;
    }

    public static void main(String[] args) {
        double feetValue = 10.0;
        double metersValue = feetToMeters(feetValue);
        System.out.printf("%.2f feet is equal to %.2f meters%n", feetValue, metersValue);
    }
}
```

输出：`10.00 feet is equal to 3.05 meters`

## 101. 天转换为年、月、天

```java
public class Main {
    public static int[] convertDaysToYearsMonthsDays(int days) {
        // 计算年
        int years = days / 365;
        // 计算年后的剩余天数
        int remainingDaysAfterYears = days % 365;
        // 计算月份
        int months = remainingDaysAfterYears / 30;
        // 计算月后的剩余天数
        int remainingDaysAfterMonths = remainingDaysAfterYears % 30;
        return new int[] { years, months, remainingDaysAfterMonths };
    }

    public static void main(String[] args) {
        int totalDays = 1000;
        int[] result = convertDaysToYearsMonthsDays(totalDays);
        System.out.printf("%d days is approximately %d years, %d months, and %d days.%n", totalDays, result[0], result[1], result[2]);
    }
}
```



// 输出: 1000 days is approximately 2 years, 9 months, and 0 days.

## 102. 查找数组的中位数

```java
import java.util.Arrays;

public class Main {
    public static double findMedian(int[] arr) {
        // 检查列表是否有效
        if (arr.length == 0) {
            throw new IllegalArgumentException("Invalid input. Please provide a non-empty list.");
        }
        // 对数组排序
        Arrays.sort(arr);
        int len = arr.length;
        int middleIndex = len / 2;
        // 计算中位数
        if (len % 2 == 0) {
            // 如果列表有偶数个元素，返回两个中间元素的平均值
            return (arr[middleIndex - 1] + arr[middleIndex]) / 2.0;
        } else {
            // 如果列表有奇数个元素，返回中间元素
            return arr[middleIndex];
        }
    }

    public static void main(String[] args) {
        int[] numbers = {5, 2, 8, 1, 7, 3};
        double median = findMedian(numbers);
        System.out.printf("Median: %.1f%n", median);
    }
}
```

// 输出: Median: 4.0

## 103. 计算两点之间的距离

```java
public class Main {
    public static double calculateDistance(double x1, double y1, double x2, double y2) {
        // 使用距离公式计算距离
        return Math.sqrt(Math.pow(x2 - x1, 2) + Math.pow(y2 - y1, 2));
    }

    public static void main(String[] args) {
        double x1 = 1.0;
        double y1 = 2.0;
        double x2 = 4.0;
        double y2 = 6.0;
        double result = calculateDistance(x1, y1, x2, y2);
        System.out.printf("The distance between (%.1f, %.1f) and (%.1f, %.1f) is %.2f%n", x1, y1, x2, y2, result);
    }
}
```

// 输出: The distance between (1.0, 2.0) and (4.0, 6.0) is 5.00

## 104. 检查数字是否为完全平方数

```java
public class Main {
    public static boolean isPerfectSquare(double number) {
        // 检查数字是非负值
        if (number < 0) {
            return false;
        }
        // 计算数字的平方根
        double squareRoot = Math.sqrt(number);
        // 检查平方根整数部分的平方是否等于该数字
        return squareRoot == Math.floor(squareRoot);
    }

    public static void main(String[] args) {
        double testNumber = 25.0;
        boolean result = isPerfectSquare(testNumber);
        System.out.printf("Is %.1f perfect square? %b%n", testNumber, result);
    }
}
```

// 输出: Is 25.0 perfect square? true

## 105. 计算矩形面积

```java
public class Main {
    public static double calculateRectangleArea(double length, double width) {
        // 检查输入是否为有效数字
        if (length <= 0.0 || width <= 0.0) {
            System.out.println("Invalid inputs. Please provide positive numbers for length and width.");
            return 0.0;
        }
        // 计算矩形的面积
        return length * width;
    }

    public static void main(String[] args) {
        double length = 5.0;
        double width = 8.0;
        double result = calculateRectangleArea(length, width);
        System.out.printf("The area of the rectangle with length %.1f and width %.1f is %.2f%n", length, width, result);
    }
}
```

// 输出: The area of the rectangle with length 5.0 and width 8.0 is 40.00

## 106. 二进制转换为十进制

```java
public class Main {
    public static int binaryToDecimal(String binaryString) throws IllegalArgumentException {
        // 检查字符串只包含 '0' 和 '1'
        if (!binaryString.matches("[01]+")) {
            throw new IllegalArgumentException("Invalid input. Please provide a binary string.");
        }
        // 将二进制字符串转换为十进制
        return Integer.parseInt(binaryString, 2);
    }

    public static void main(String[] args) {
        String binaryNumber = "1101";
        try {
            int decimalResult = binaryToDecimal(binaryNumber);
            System.out.printf("The decimal equivalent of binary %s is %d%n", binaryNumber, decimalResult);
        } catch (IllegalArgumentException e) {
            System.out.println(e.getMessage());
        }
    }
}
```

// 输出: The decimal equivalent of binary 1101 is 13

## 107. 计算句子中的单词数

```java
public class Main {
    public static int countWords(String sentence) throws IllegalArgumentException {
        // 检查输入是否为有效的空字符串
        if (sentence == null || sentence.trim().isEmpty()) {
            throw new IllegalArgumentException("Invalid input. Please provide a valid sentence.");
        }
        // 分句子单词
        String[] words = sentence.trim().split("\\s+");
        return words.length;
    }

    public static void main(String[] args) {
        String sentence = "This is a sample sentence.";
        try {
            int wordCount = countWords(sentence);
            System.out.printf("The sentence \"%s\" has %d words.%n", sentence, wordCount);
        } catch (IllegalArgumentException e) {
            System.out.println(e.getMessage());
        }
    }
}
```

// 输出: The sentence "This is a sample sentence." has 5 words.

## 108. 查找两个数组的并集

```java
import java.util.Arrays;
import java.util.HashSet;
```

```java
public class Main {
    public static <T> HashSet<T> findUnion(T[] arr1, T[] arr2) {
        // Create a HashSet to store the union of both arrays
        HashSet<T> unionSet = new HashSet<>();
        // Insert elements of both arrays into the HashSet
        unionSet.addAll(Arrays.asList(arr1));
        unionSet.addAll(Arrays.asList(arr2));
        return unionSet;
    }

    public static void main(String[] args) {
        Integer[] array1 = {1, 2, 3, 4, 5};
        Integer[] array2 = {3, 4, 5, 6, 7};
        // Get the union of both arrays
        HashSet<Integer> unionResult = findUnion(array1, array2);
        // Display the result
        System.out.println("Union of Arrays: " + unionResult);
    }
}

// 输出: Union of Arrays: [1, 2, 3, 4, 5, 6, 7]
```

| ![image](img/chapter_title_corner_decoration_left.png) |  | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 109. 评分系统

![image](img/chapter_title_below.png)

```java
import java.util.HashMap;

public class ScoringSystem {
    public static int[] calculateScores(String scoreString) {
        // 初始化 Andy (A), Ben (B) 和 Charlotte (C) 的分数
        HashMap<Character, Integer> scores = new HashMap<>();
        scores.put('A', 0);
        scores.put('B', 0);
        scores.put('C', 0);
        // 统计字符串中每个字母的出现次数
        for (char ch : scoreString.toCharArray()) {
            scores.put(ch, scores.getOrDefault(ch, 0) + 1);
        }
        // 按此顺序返回分数: Andy (A), Ben (B), Charlotte (C)
        return new int[] {
            scores.getOrDefault('A', 0),
            scores.getOrDefault('B', 0),
            scores.getOrDefault('C', 0)
        };
    }

    public static void main(String[] args) {
        // 使用示例
        System.out.println(java.util.Arrays.toString(calculateScores("A")));
        System.out.println(java.util.Arrays.toString(calculateScores("ABC")));
        System.out.println(java.util.Arrays.toString(calculateScores("ABCBACC")));
    }
}
```

输出：

```text
[1, 0, 0]

[1, 1, 1]

[2, 2, 3]
```

| ![image](img/chapter_title_corner_decoration_left.png) |  | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 110. 检查数字是否为强数 (Strong Number)

![image](img/chapter_title_below.png)

```java
public class StrongNumberChecker {
    // 计算数字阶乘的方法
    public static int calculateFactorial(int n) {
        int result = 1;

        for (int i = 2; i <= n; i++) {
            result *= i;
        }

        return result;
    }

    // 检查数字是否为强数的方法
    public static boolean isStrongNumber(int num) {
        int originalNumber = num;
        int digitFactorialSum = 0;

        // 计算每个数字阶乘之和
        while (num > 0) {
            int digit = num % 10; // 获取最后一位数字
            digitFactorialSum += calculateFactorial(digit);
            num /= 10; // 去除最后一位数字
        }

        // 检查和是否等于原始数字
        return digitFactorialSum == originalNumber;
    }

    public static void main(String[] args) {
        int testNumber = 145;
        boolean result = isStrongNumber(testNumber);
        System.out.println(testNumber + " is a strong number: " + result);
    }
}
```

输出：

```text
145 is a strong number: true
```



| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 111. 检查数字是否为水政仙数（Narcissistic Number）

![image](img/chapter_title_below.png)

```java
public class NarcissisticNumberChecker {
    // 检查数字是否为水政仙数的方法
    public static boolean isNarcissisticNumber(int num) {
        // 将数字转换为字符串
        String numStr = Integer.toString(num);
        int numDigits = numStr.length();
        // 计算每个数字的位数的幂之和
        int total = 0;
        for (char digitChar : numStr.toCharArray()) {
            int digit = Character.getNumericValue(digitChar);
            total += Math.pow(digit, numDigits);
        }
        // 检查总和是否等于原始数字
        return total == num;
    }

    public static void main(String[] args) {
        int testNumber = 153;
        boolean result = isNarcissisticNumber(testNumber);
        System.out.println(testNumber + " is a narcissistic number: " + result);
    }
}
```

（注：原文中的输入/输出逻辑不一致，我保留了结构。）

# 112. 统计字符串中的辅音数量

![image](img/chapter_title_below.png)

```java
public class ConsonantCounter {
    // 统计辅音的方法
    public static int countConsants(String inputStr) {
        // 定义辅音字符串
        String consonants = "bcdfghjklmnpqrstvwxyz";
        int count = 0;
        // 将输入字符串转换为小写并遍历字符
        for (char c : inputStr.toLowerCase().toCharArray()) {
            // 检查字符是否为辅音
            if (consonants.indexOf(c) != -1) {
                count++;
            }
        }
        return count;
    }

    public static void main(String[] args) {
        String testString = "Hello World";
        int result = countConsants(testString);
        System.out.println("The number of consonants in '" + testString + "' is: " + result);
    }
}
```

输出：

```text
The number of consonants in 'Hello World' is: 7
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 113. 检查数字是否为三角形数（Triangular Number）

![image](img/chapter_title_below.png)

```java
public class TriangularNumberChecker {
    // 检查数字是否为三角形数
    public static boolean isTriangular(int num) {
        // 检查是否为非数
        if (num <= 0) {
            return false; // 零和负数不是三角形数
        }

        int total = 0;
        int n = 1;

        // 遍历自然数直到和超过等于 num
        while (total < num) {
            total += n;
            n++;
        }

        // 检查输入数字是否等于该和
        return total == num;
    }

    public static void main(String[] args) {
        int testNumber = 10;
        boolean result = isTriangular(testNumber);
        System.out.println(testNumber + " is a triangular number: " + result);
    }
}
```

输出：

```text
10 is a triangular number: true
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 114. 寻找梯形的面积

![image](img/chapter_title_below.png)

```java
public class TrapezoidAreaCalculator {
    // 计算梯形面积的方法
    public static double trapezoidArea(double base1, double base2, double height) throws IllegalArgumentException {
        // 检查输入是否有效
        if (base1 <= 0 || base2 <= 0 || height <= 0) {
            throw new IllegalArgumentException("输入无效. 请提供正数.");
        }
        // 计算梯形面积
        return 0.5 * height * (base1 + base2);
    }

    public static void main(String[] args) {
        double base1Length = 5.0;
        double base2Length = 9.0;
        double trapezoidHeight = 4.0;
        try {
            double area = trapezoidArea(base1Length, base2Length, trapezoidHeight);
            System.out.printf("梯形的面积是: %.2f%n", area);
        } catch (IllegalArgumentException e) {
            System.out.println(e.getMessage());
        }
    }
}
```

输出：

```text
梯形的面积是: 28.00
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 115. 缩写唯一吗？

![image](img/chapter_title_below.png)

```java
import java.util.HashMap;
import java.util.List;

public class Main {
    public static boolean uniqueAbbrev(String[] abbreviations, String[] words) {
        // 创建一个映射，每个缩写映射到它可能表示的单词
        HashMap<String, List<String>> abbrevMap = new HashMap<>();

        for (String word : words) {
            String abbrev = word.substring(0, 1); // 使用第一个字符作为缩写
            abbrevMap.computeIfAbsent(abbrev, k -> new java.util.ArrayList<>()).add(word);
        }

        // 检查每个缩写是否是唯一的
        for (String abbrev : abbreviations) {
            List<String> correspondingWords = abbrevMap.get(abbrev);
            if (correspondingWords == null || correspondingWords.size() != 1) {
                return false; // 缩写不是唯一的
            }
        }

        return true; // 所有缩写都是唯一的
    }

    public static void main(String[] args) {
        // 示例用法
        String[] abbreviations1 = {"ho", "h", "ha"};
        String[] words1 = {"house", "hope", "happy"};
        System.out.println("uniqueAbbrev([\"ho\", \"h\", \"ha\"], [\"house\", \"hope\", \"happy\"]) ➞ " + uniqueAbbrev(abbreviations1, words1));

        String[] abbreviations2 = {"s", "t", "v"};
        String[] words2 = {"stamina", "television", "vindaloo"};
        System.out.println("uniqueAbbrev([\"s\", \"t\", \"v\"], [\"stamina\", \"television\", \"vindaloo\"]) ➞ " + uniqueAbbrev(abbreviations2, words2));

        String[] abbreviations3 = {"bi", "ba", "bat"};
        String[] words3 = {"big", "bard", "battery"};
        System.out.println("uniqueAbbrev([\"bi\", \"ba\", \"bat\"], [\"big\", \"bard\", \"battery\"]) ➞ " + uniqueAbbrev(abbreviations3, words3));

        String[] abbreviations4 = {"mo", "ma", "me"};
        String[] words4 = {"moment", "many", "mean"};
        System.out.println("uniqueAbbrev([\"mo\", \"ma\", \"me\"], [\"moment\", \"many\", \"mean\"]) ➞ " + uniqueAbbrev(abbreviations4, words4));
    }
}
```

输出：

```text
uniqueAbbrev(["ho", "h", "ha"], ["house", "hope", "happy"]) ➞ true
uniqueAbbrev(["s", "t", "v"], ["stamina", "television", "vindaloo"]) ➞ false
uniqueAbbrev(["bi", "ba", "bat"], ["big", "bard", "battery"]) ➞ false
uniqueAbbrev(["mo", "ma", "me"], ["moment", "many", "mean"]) ➞ true
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 116. 检查一个数字是否为斐波那契数

![image](img/chapter_title_below.png)

```java
public class Main {
    // 辅助函数：检查一个数字是否为完全平方数
    private static boolean isPerfectSquare(long n) {
        long sqrt = (long) Math.sqrt(n);
        return sqrt * sqrt == n;
    }

    public static boolean isFibonacciNumber(long num) {
        // 一个数字是斐波那契数当且仅当 (5 * num² + 4) 或 (5 * num² - 4) 其中一个是完全平方数时
        long numSquared = num * num;
        return isPerfectSquare(5 * numSquared + 4) || isPerfectSquare(5 * numSquared - 4);
    }

    public static void main(String[] args) {
        long testNumber = 8;
        boolean result = isFibonacciNumber(testNumber);
        System.out.println(testNumber + " 是一个斐波那契数: " + result);
    }
}
```

输出：

```text
8 是一个斐波那契数: true
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 117. 寻找矩形的周长

![image](img/chapter_title_below.png)

```java
public class Main {
    public static double rectanglePerimeter(double length, double width) throws IllegalArgumentException {
        // 检查输入是否为有效数字
        if (length <= 0.0 || width <= 0.0) {
            throw new IllegalArgumentException("输入无效。请提供有效的正数。");
        }

        // 计算矩形的周长
        return 2.0 * (length + width);
    }

    public static void main(String[] args) {
        double length = 5.0;
        double width = 8.0;

        try {
            double perimeter = rectanglePerimeter(length, width);
            System.out.println("矩形的周长为: " + perimeter);
        } catch (IllegalArgumentException e) {



```java
System.out.println(e.getMessage());

}
}
}

// 输出:

// 矩形的周长为: 26.0
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 18. Club Entry

![image](img/chapter_title_below.png)

```java
public class Main {

    public static Integer clubEntry(String word) {

        // 寻找连续的字母

        Character doubledLetter = null;

        for (int i = 0; i < word.length() - 1; i++) {

            if (word.charAt(i) == word.charAt(i + 1)) {

                doubledLetter = word.charAt(i);

                break;
            }
        }

        // 确保找到了连续的字母

        if (doubledLetter == null) {

            return null; // 未找到连续字母
        }

        // 计算字母在字母表中的位置

        int position = doubledLetter - 'a' + 1;

        // 将位置乘以 4

        int result = position * 4;

        return result;
    }

    public static void main(String[] args) {

        String[] words = {"hill", "apple", "bee"};

        for (String word : words) {

            Integer number = clubEntry(word);

            if (number != null) {

                System.out.println(word + " ➞ " + number);

            } else {

                System.out.println(word + " ➞ 无连续字母");
            }
        }
    }
}

// 输出:

// hill ➞ 3

// apple ➞ 4

// bee ➞ 8
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 119. 检查字符串是否为另一个字符串的字母异位

```java
import java.util.HashMap;

public class Main {

    // 统计字符

    private static HashMap<Character, Integer> getCount(String s) {

        HashMap<Character, Integer> count = new HashMap<>();

        for (char c : s.toCharArray()) {

            count.put(c, count.getOrDefault(c, 0) + 1);
        }

        return count;
    }

    public static boolean areAnagram(String str1, String str2) {

        // 获取两个字符串的计数

        HashMap<Character, Integer> count1 = getCount(str1);

        HashMap<Character, Integer> count2 = getCount(str2);

        // 比较频率

        return count1.equals(count2);
    }

    public static void main(String[] args) {

        String string1 = "listen";

        String string2 = "silent";

        boolean result = areAnagram(string1, string2);

        System.out.println(string1 + " 和 " + string2 + " 是字母异位: " + result);
    }
}

// 输出:

// listen 和 silent 是字母异位: true
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 120. 生成杨斯卡三角形

![image](img/chapter_title_below.png)

```java
import java.util.ArrayList;
import java.util.List;

public class Main {

    public static List<List<Integer>> generatePascalsTriangle(int numRows) {

        List<List<Integer>> triangle = new ArrayList<>();

        if (numRows == 0) {

            return triangle;
        }

        // 初始化第一行

        triangle.add(new ArrayList<>());

        triangle.get(0).add(1);

        for (int i = 1; i < numRows; i++) {

            List<Integer> row = new ArrayList<>();

            row.add(1); // 每行的第一个元素都是 1

            // 根据上一行计算值

            List<Integer> prevRow = triangle.get(i - 1);

            for (int j = 1; j < i; j++) {

                row.add(prevRow.get(j - 1) + prevRow.get(j));
            }

            row.add(1); // 每行的最后一个元素都是 1

            triangle.add(row);
        }

        return triangle;
    }

    public static void main(String[] args) {

        int numRows = 5;

        List<List<Integer>> triangle = generatePascalsTriangle(numRows);

        System.out.println("包含 " + numRows + " 行的杨斯卡三角形:");

        for (List<Integer> row : triangle) {

            System.out.println(row);
        }
    }
}

// 输出:

// 包含 5 行的杨斯卡三角形:

// [1]

// [1, 1]

// [1, 2, 1]

// [1, 3, 3, 1]

// [1, 4, 6, 4, 1]
```

# 121. 将十进制转换为罗马数字

![image](img/chapter_title_below.png)

```java
public class Main {

    public static String decimalToRoman(int num) throws IllegalArgumentException {

        if (num <= 0 || num > 3999) {

            throw new IllegalArgumentException("输入无效。请提供 1 到 3999 之间的有效正整数。");
        }

        // 定义罗马数字符号及其值

        String[] romanSymbols = {
            "M", "CM", "D", "CD",
            "C", "XC", "L", "XL",
            "X", "IX", "V", "IV", "I"
        };

        int[] values = {
            1000, 900, 500, 400,
            100, 90, 50, 40,
            10, 9, 5, 4, 1
        };

        StringBuilder result = new StringBuilder();

        // 将十进制转换为罗马数字

        for (int i = 0; i < values.length; i++) {

            while (num >= values[i]) {

                result.append(romanSymbols[i]);

                num -= values[i];
            }
        }

        return result.toString();
    }

    public static void main(String[] args) {

        int decimalNumber = 1984;

        try {

            String romanNumeral = decimalToRoman(decimalNumber);

            System.out.println(decimalNumber + " 的罗马数字表示为：" + romanNumeral);

        } catch (IllegalArgumentException e) {

            System.out.println(e.getMessage());
        }
    }
}

// 输出:

// 1984 的罗马数字表示为：MCMLXXXIV
```

# 1984 的罗马数字表示为：MCMLXXXIV

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 122. 计算平行四形的面积

![image](img/chapter_title_below.png)

```java
public class Main {

    public static double parallelogramArea(double base, double height) throws IllegalArgumentException {

        if (base > 0.0 && height > 0.0) {

            return base * height;

        } else {

            throw new IllegalArgumentException("输入无效。请提供有效的正数。
        }
    }

    public static void main(String[] args) {

        double base = 6.0;

        double height = 8.0;

        try {

            double area = parallelogramArea(base, height);

            System.out.println("平行四形的面积为：" + area);

        } catch (IllegalArgumentException e) {

            System.out.println(e.getMessage());
        }
    }
}

// 输出:

// 平行四形的面积为：48.0
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 123. 超英雄

![image](img/chapter_title_below.png)

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class Main {

    public static List<String> superheroes(String[] names) {

        List<String> filtered = new ArrayList<>();

        // 过滤以 "man" 结尾的名字

        for (String name : names) {

            if (name.toLowerCase().endsWith("man")) {

                filtered.add(name);
            }
        }

        // 对过滤后的列表进行排序

        Collections.sort(filtered);

        return filtered;
    }

    public static void main(String[] args) {

        String[] heroes1 = {"Batman", "Superman", "Spider-man", "Hulk", "Wolverine", "Wonder-Woman"};

        List<String> result1 = superheroes(heroes1);

        System.out.println(result1); // 输出: [Batman, Spider-man, Superman]

        String[] heroes2 = {"Catwoman", "Deadpool", "Dr.Strange", "Captain-America", "Aquaman", "Hawkeye"};

        List<String> result2 = superheroes(heroes2);

        System.out.println(result2); // 输出: [Aquaman]

        String[] heroes3 = {"Wonder-Woman", "Catwoman", "Invisible-Woman"};

        List<String> result3 = superheroes(heroes3);

        System.out.println(result3); // 输出: []
    }
}

// 预期输出:

// [Batman, Spider-man, Superman]

// [Aquaman]

// []
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 124. 应用折扣

![image](img/chapter_title_below.png)

```java
import java.util.ArrayList;
```



```java
import java.util.ArrayList;
import java.util.List;

public class Main {
    public static List<Double> getDiscounts(double[] prices, String discount) {
        // 将折扣提取为 double
        double discountPercentage = Double.parseDouble(discount.replace("%", ""));
        double discountFactor = discountPercentage / 100.0;

        // 计算折扣后的价格
        List<Double> discountedPrices = new ArrayList<>();

        for (double price : prices) {
            discountedPrices.add(price * (1.0 - discountFactor));
        }

        return discountedPrices;
    }

    public static void main(String[] args) {
        // 使用示例
        double[] prices1 = {2.0, 4.0, 6.0, 10.0};
        String discount1 = "50%";
        List<Double> discountedPrices1 = getDiscounts(prices1, discount1);
        System.out.println(discountedPrices1); // 输出: [1.0, 2.0, 3.0, 5.0]

        double[] prices2 = {10.0, 20.0, 40.0, 80.0};
        String discount2 = "75%";
        List<Double> discountedPrices2 = getDiscounts(prices2, discount2);
        System.out.println(discountedPrices2); // 输出: [2.5, 5.0, 10.0, 20.0]

        double[] prices3 = {100.0};
        String discount3 = "45%";
        List<Double> discountedPrices3 = getDiscounts(prices3, discount3);
        System.out.println(discountedPrices3); // 输出: [55.0]
    }
}

// 预期输出:
// [1.0, 2.0, 3.0, 5.0]
// [2.5, 5.0, 10.0, 20.0]
// [55.0]
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 125. 检查数字是否为史密数

![image](img/chapter_title_below.png)

```java
import java.util.ArrayList;
import java.util.List;

public class Main {
    public static boolean isPrime(long num) {
        if (num < 2) return false;

        for (long i = 2; i * i <= num; i++) {
            if (num % i == 0) return false;
        }

        return true;
    }

    public static long sumOfDigits(long num) {
        long sum = 0;

        while (num > 0) {
            sum += num % 10;
            num /= 10;
        }

        return sum;
    }

    public static List<Long> primeFactors(long num) {
        List<Long> factors = new ArrayList<>();

        for (long i = 2; i * i <= num; i++) {
            while (num % i == 0) {
                factors.add(i);
                num /= i;
            }
        }

        if (num > 1) {
            factors.add(num);
        }

        return factors;
    }

    public static boolean isSmithNumber(long num) {
        long originalSum = sumOfDigits(num);
        long primeFactorSum = primeFactors(num)
                .stream()
                .mapToLong(Main::sumOfDigits)
                .sum();

        return originalSum != primeFactorSum && !isPrime(num);
    }

    public static void main(String[] args) {
        long number = 728;

        System.out.println("" + number + " 是史密数吗？ " + isSmithNumber(number));
    }
}

// 输出: 728 是史密数吗？ false
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 126. 基础国际棋盘

![image](img/chapter_title_below.png)

```java
public class Main {
    public static String generateChessboard() {
        int size = 8; // 棋盘大小 (8x8)
        StringBuilder chessboard = new StringBuilder();

        for (int row = 0; row < size; row++) {
            StringBuilder currentRow = new StringBuilder();

            for (int col = 0; col < size; col++) {
                // 使用 'X' 表示黑格，用 ' 表示白格
                char square = (row + col) % 2 == 1 ? 'X' : ' ';
                currentRow.append(square).append(' '); // 在格格之间添加空格
            }

            // 将当前行添加到棋盘并换换行
            chessboard.append(currentRow.toString().trim()).append('\n'); // 去除末尾空格
        }

        return chessboard.toString();
    }

    public static void main(String[] args) {
        String chessboard = generateChessboard();
        System.out.print(chessboard);
    }
}

// 输出:
//  X X X X X X X X
// X X X X X X X X
//  X X X X X X X X
// X X X X X X X X
//  X X X X X X X X
// X X X X X X X X
//  X X X X X X X X
// X X X X X X X X
```

# 127. 哪个数字与众不同

![image](img/chapter_title_below.png)

```java
import java.util.HashMap;
import java.util.Map;

public class Main {
    public static int unique(int[] numbers) {
        Map<Integer, Integer> counts = new HashMap<>();

        // 统计每个数字出现的次数
        for (int num : numbers) {
            counts.put(num, counts.getOrDefault(num, 0) + 1);
        }

        // 寻找唯一的数字
        for (Map.Entry<Integer, Integer> entry : counts.entrySet()) {
            if (entry.getValue() == 1) {
                return entry.getKey();
            }
        }

        // 如果没有找到唯一的数字，返回 0 (作为兜底)
        return 0; // 你可能需要不同的方式处理这种情况
    }

    public static void main(String[] args) {
        int[] numbers1 = {3, 3, 3, 7, 3, 3};
        int[] numbers2 = {0, 0, 77, 0, 0};
        int[] numbers3 = {0, 1, 1, 1, 1, 1, 1, 1};

        System.out.println("Unique number in array 1: " + unique(numbers1)); // 输出: 7
        System.out.println("Unique number in array 2: " + unique(numbers2)); // 输出: 77
        System.out.println("Unique number in array 3: " + unique(numbers3)); // 输出: 0
    }
}
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 128. 查找折扣

![image](img/chapter_title_below.png)

```java
public class Main {
    public static double findDiscount(double originalPrice, int discountPercentage) {
        double discount = originalPrice * (discountPercentage / 100.0);
        return originalPrice - discount;
    }

    public static void main(String[] args) {
        // 使用示例
        System.out.printf("%.2f%n", findDiscount(1500.0, 50)); // 输出: 750.00
        System.out.printf("%.2f%n", findDiscount(89.0, 20));   // 输出: 71.20
        System.out.printf("%.2f%n", findDiscount(100.0, 75));  // 输出: 25.00
    }
}
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 129. 检查字符串是否为全字母句

![image](img/chapter_title_below.png)

```java
public class Main {
    public static boolean isPangram(String inputStr) {
        String alphabet = "abcdefghijklmnopqrstuvwxyz";
        String lowercasedStr = inputStr.toLowerCase();

        for (char ch : alphabet.toCharArray()) {
            if (lowercasedStr.indexOf(ch) == -1) {
                return false;
            }
        }

        return true;
    }

    public static void main(String[] args) {
        // 使用示例
        String inputString = "The quick brown fox jumps over the lazy dog";

        if (isPangram(inputString)) {
            System.out.println("The given string is a pangram! 🎉");
        } else {
            System.out.println("The given string is not a pangram. 😢");
        }
    }
}
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 130. 同轴电缆阻抗

![image](img/chapter_title_below.png)

```java
public class Main {
    public static double impedanceCalculator(double dD, double dC, double eR) {
        // 使用公式计算阻抗
        double logTerm = Math.log10(dD / dC);
        double impedance = 60.0 / Math.sqrt(eR) * logTerm;

        return impedance;
    }

    public static void main(String[] args) {
        // 使用示例
        System.out.printf("%.1f%n", impedanceCalculator(20.7, 2.0, 4.0));
        System.out.printf("%.1f%n", impedanceCalculator(5.3, 1.2, 2.2));
        System.out.printf("%.1f%n", impedanceCalculator(4.48, 1.33, 2.2));
    }
}
```



- 30.4
- 26.1
- 21.3

| ![image](`img/chapter_title_corner_decoration_left.png`) | | ![image](`img/chapter_title_corner_decoration_right.png`) |

![image](`img/chapter_title_above.png`)

# 131. 屏蔽超过四个字符的单词

![image](`img/chapter_title_below.png`)

```java
public static class Main {

    public static String censor(String text) {
        // 将文本分成单词
        String[] words = text.split("\\s+");

        // 转换超过四个字符的单词
        StringBuilder censoredText = new StringBuilder();

        for (String word : words) {
            if (word.length() > 4) {
                // 用星号替换
                String censoredWord = "*".repeat(word.length());
                censoredText.append(censoredWord).append(" ");
            } else {
                censoredText.append(word).append(" ");
            }
        }

        // 返回屏蔽后的单词并去除末尾空格
        return censoredText.trim();
    }

    public static void main(String[] args) {
        // 使用示例
        System.out.println(censor("The code is four"));
        System.out.println(censor("Two plus three is five"));
        System.out.println(censor("aaaaa 1234 2345"));
    }
}
```

- The code is four
- Two plus three is five
- aaaaa 1234 2345

| ![image](`img/chapter_title_corner_decoration_left.png`) | | ![image](`img/chapter_title_corner_decoration_right.png`) |

![image](`img/chapter_title_above.png`)

# 132. 计算椭圆面积

![image](`img/chapter_title_below.png`)

```java
public static class Main {

    public static double calculateEllipse(double semiMajorAxis, double semiMinorAxis) {
        return Math.PI * semiMajorAxis * semiMinorAxis;
    }

    public static void main(String[] args) {
        double semiMajorAxis = 5.0; // 半长轴
        double semiMinorAxis = 3.0; // 半短轴
        double ellipseArea = calculateEllipse(semiMajorAxis, semiMinorAxis);

        System.out.printf("The area of the ellipse is: %.2f%n", ellipseArea);
    }
}
```

- The area of the ellipse is: 47.12

| ![image](`img/chapter_title_corner_decoration_left.png`) | | ![image](`img/chapter_title_corner_decoration_right.png`) |

![image](`img/chapter_title_above.png`)

# 133. 检查字符串是否为二进制回文

![image](`img/chapter_title_below.png`)

```java
public static class Main {

    // 检查数字是否为二进制回文
    public static boolean isBinaryPalindrome(int number) {
        String binaryRepresentation = Integer.toBinaryString(number); // 转换为二进制表示
        String reversedBinary = new StringBuilder(binaryRepresentation).reverse().toString(); // 反转二进制表示

        return binaryRepresentation.equals(reversedBinary); // 检查是否为回文
    }

    public static void main(String[] args) {
        int numberToCheck = 9; // 你想要检查的数字

        if (isBinaryPalindrome(numberToCheck)) {
            System.out.printf("%d is a binary palindrome! 🎉%n", numberToCheck);
        } else {
            System.out.printf("%d is not a binary palindrome. 😢%n", numberToCheck);
        }
    }
}
```

- 9 is a binary palindrome! 🎉

| ![image](`img/chapter_title_corner_decoration_left.png`) | | ![image](`img/chapter_title_corner_decoration_right.png`) |

![image](`img/chapter_title_above.png`)

# 134. 查找菱形面积

![image](`img/chapter_title_below.png`)

```java
public static class Main {

    // 给定对角线计算菱形面积的方法
    public static double calculateRhombusArea(double diagonal1, double diagonal2) {
        return (diagonal1 * diagonal2) / 2.0; // 菱形面积公式
    }

    public static void main(String[] args) {
        double diagonal1Length = 8.0; // 第一条对角线长度
        double diagonal2Length = 6.0; // 第二条对角线长度
        double rhombusArea = calculateRhombusArea(diagonal1Length, diagonal2Length);

        System.out.printf("The area of the rhombus is: %.2f%n", rhombusArea);
    }
}
```

- The area of the rhombus is: 24.00

| ![image](`img/chapter_title_corner_decoration_left.png`) | | ![image](`img/chapter_title_corner_decoration_right.png`) |

![image](`img/chapter_title_above.png`)

# 135. 检查数字是否为卡特兰数

![image](`img/chapter_title_below.png`)

```java
public static class Main {

    // 计算二项式系数 C(n, k)
    public static long binomialCoefficient(long n, long k) {
        long result = 1;

        if (k > n - k) {
            k = n - k; // 利用对称性
        }

        for (long i = 0; i < k; i++) {
            result *= n;
            result /= (i + 1);
            n--;
        }

        return result;
    }

    // 检查数字是否为卡特兰数
}
```

```java
public static boolean isCatalanNumber(long num) {
    long i = 0;

    while (true) {
        long catalan = binomialCoefficient(2 * i, i) / (i + 1);

        if (catalan == num) {
            return true; // 找到匹配
        } else if (catalan > num) {
            return false; // 超过该数字
        }

        i++;
    }
}

public static void main(String[] args) {
    long numberToCheck = 42; // 替换为你想检查的数字

    if (isCatalanNumber(numberToCheck)) {
        System.out.printf("%d 是卡特兰数! 🎉%n", numberToCheck);
    } else {
        System.out.printf("%d 不是卡特兰数。 😢%n", numberToCheck);
    }
}
```

```
// 42 是卡特兰数! 🎉
```

# 136. 查找卢恩算法（Luhn Algorithm）校验位

```java
public class Main {

    // 计算卢恩校验位（check digit）的方法
    public static int calculateLuhnCheckDigit(long input) {
        String inputStr = Long.toString(input);
        int totalSum = 0;
        boolean isEvenPosition = inputStr.length() % 2 == 0;

        // 遍历数字
        for (int i = 0; i < inputStr.length(); i++) {
            int digit = Character.getNumericValue(inputStr.charAt(i));

            // 检查是否处于偶数位
            if (isEvenPosition) {
                // 对于偶数位，数字翻倍
                if (i % 2 == 0) {
                    digit *= 2;

                    if (digit > 9) {
                        digit -= 9; // 如果结果大于 9，则减去 9
                    }
                }
            } else {
                // 对于奇数位，数字翻倍
                if (i % 2 != 0) {
                    digit *= 2;

                    if (digit > 9) {
                        digit -= 9; // 如果结果大于 9，则减去 9
                    }
                }
            }

            totalSum += digit; // 将处理后的数字加到总和
        }

        // 计算校验位
        return (10 - (totalSum % 10)) % 10;
    }

    public static void main(String[] args) {
        long partialNumber = 123456789; // 替换为部分数字
        int checkDigit = calculateLuhnCheckDigit(partialNumber);
        String fullNumber = Long.toString(partialNumber) + checkDigit;

        System.out.println("部分数字: " + partialNumber);
        System.out.println("校验位: " + checkDigit);
        System.out.println("带校验位的完整数字: " + fullNumber);
    }
}
```

```
// 部分数字: 123456789
// 校验位: 3
// 带校验位的完整数字: 1234567893
```

# 137. ATM 密码验证器

```java
public class Main {

    // 检查 PIN 码是否有效
    public static boolean isValidPin(String pin) {
        // 检查长度是否为 4 或 6
        if (pin.length() != 4 && pin.length() != 6) {
            return false;
        }

        // 检查所有字符是否为数字
        for (char c : pin.toCharArray()) {
            if (!Character.isDigit(c)) {
                return false; // 找到非数字字符
            }
        }

        return true; // 所有检查通过
    }

    public static void main(String[] args) {
        // 示例用法
        String[] pins = {"1234", "12345", "a234", "", "123456"};

        for (String pin : pins) {
            System.out.println("PIN '" + pin + "' 是否有效: " + isValidPin(pin));
        }
    }
}
```

```
// PIN '1234' 是否有效: true
// PIN '12345' 是否有效: false
// PIN 'a234' 是否有效: false
// PIN '' 是否有效: false
// PIN '123456' 是否有效: true
```

# 138. 检查某一年是否为魔法年份

```java
public class Main {

    // 检查年份是否为魔法年份
    public static boolean isMagicYear(int year) {
        String yearStr = String.valueOf(year);

        // 检查年份是否恰好为 6 位
        if (yearStr.length() != 6) {
            return false;
        }

        // 从年份中提取月、日和结果
        int month = Integer.parseInt(yearStr.substring(0, 2));
        int day = Integer.parseInt(yearStr.substring(2, 4));
        int result = Integer.parseInt(yearStr.substring(4, 6));

        // 检查月份乘以日期是否等于结果



```java
return month * day == result;

}

public static void main(String[] args) {

    // 示例用法

    int yearToCheck = 1978; // 替换为你想检查的年份

    if (isMagicYear(yearToCheck)) {

        System.out.println(yearToCheck + " 是魔法年份!");

    } else {

        System.out.println(yearToCheck + " 不是魔法年份。😢");

    }

}

}

```

# 139. 等音转换（Enharmonic Equivalents）

```java
import java.util.HashMap;

import java.util.Map;

public class Main {

    // 获取给定音的等音的方法

    public static String getEquivalent(String note) {

        // 定义音到等音的映射

        Map<String, String> enharmonicMap = new HashMap<>();

        enharmonicMap.put("C#", "Db");

        enharmonicMap.put("D#", "Eb");

        enharmonicMap.put("F#", "Gb");

        enharmonicMap.put("G#", "Ab");

        enharmonicMap.put("A#", "Bb");

        // 返回等音，如果不存在则返回“无效音”

        return enharmonicMap.getOrDefault(note, "无效音");

    }

    public static void main(String[] args) {

        // 示例用法

        System.out.println(getEquivalent("C#")); // 输出: Db

        System.out.println(getEquivalent("D#")); // 输出: Eb

        System.out.println(getEquivalent("F#")); // 输出: Gb

        System.out.println(getEquivalent("G#")); // 输出: Ab

        System.out.println(getEquivalent("A#")); // 输出: Bb

        System.out.println(getEquivalent("H")); // 输出: 无效音

    }

}

```

# 140. 计算正多边形的面积

```java
public class Main {

    // 计算正多边形面积的方法

    public static double calculateRegularPolygonArea(int n, double s) {

        double numerator = 1.0 / 4.0 * n * Math.pow(s, 2);

        double denominator = Math.tan(Math.PI / n);

        double area = numerator / denominator;

        return area;

    }

    public static void main(String[] args) {

        int numberOfSides = 6; // 替换为边形的边数

        double sideLength = 5.0; // 替换为边的长度

        double polygonArea = calculateRegularPolygonArea(numberOfSides, sideLength);

        System.out.printf("正多边形的面积: %.2f%n", polygonArea);

    }

}

```

```
// 正多边形的面积: 64.95
```

# 141. 检查某数字是否为盈数（Abundant Number）

```java
public class Main {

    // 计算真因数之和的方法

    public static int getProperDivisorsSum(int number) {

        int divisorSum = 0;

        int limit = number / 2; // 真因数小于数字本身

        for (int i = 1; i <= limit; i++) {

            if (number % i == 0) {

                divisorSum += i; // 将因数加到总和

            }

        }

        return divisorSum;

    }

    // 检查一个数字是否为盈数

    public static boolean isAbundantNumber(int number) {

        int divisorsSum = getProperDivisorsSum(number);

        return divisorsSum > number;

    }

}
```

```java
return divisorsSum > number; // 检查约数和是否大于数字本身

}

public static void main(String[] args) {

    int numberToCheck = 12; // 替换为你想检查的数字

    if (isAbundantNumber(numberToCheck)) {

        System.out.printf("%d 是一个过剩数！🎉%n", numberToCheck);

    } else {

        System.out.printf("%d 不是一个过剩数。😢%n", numberToCheck);

    }

}

}

```

```
// 12 是一个过剩数！🎉
```

| ![image](img/chapter_title_corner_decoration_left.png) |  | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 142. 洗手

![image](img/chapter_title_below.png)

```java
public class Main {

    // 计算洗手花费的总时间的函数

    public static String washHands(int n, int nm) {

        // 洗手花费的总秒数

        int totalSeconds = n * nm * 21;

        // 将秒转换为分钟和秒

        int minutes = totalSeconds / 60;

        int seconds = totalSeconds % 60;

        return String.format("%d minutes and %d seconds", minutes, seconds);

    }

    public static void main(String[] args) {

        // 使用示例

        System.out.println(washHands(8, 7));  // 输出: "588 minutes and 0 seconds"

        System.out.println(washHands(0, 0));  // 输出: "0 minutes and 0 seconds"

        System.out.println(washHands(7, 9));  // 输出: "661 minutes and 30 seconds"

    }

}

```

```
// 588 minutes and 0 seconds
// 0 minutes and 0 seconds
// 661 minutes and 30 seconds
```

| ![image](img/chapter_title_corner_decoration_left.png) |  | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 143. 计算欧拉拉函数

![image](img/chapter_title_below.png)

```java
public class Main {

    // 计算欧拉拉函数的函数

    public static int eulerTotientFunction(int n) {

        if (n <= 0) {

            throw new IllegalArgumentException("输入必须为正整数.");

        }

        int result = n; // 将结果初始化为 n

        int p = 2;

        // 遍历 n 的所有质因子

        while (p * p <= n) {

            // 检查 p 是否为 n 的因数

            if (n % p == 0) {

                // 如果 p 整除 n，则尽可能多次除以 p

                while (n % p == 0) {

                    n /= p;

                }

                result -= result / p; // 应用质因子的公式

            }

            p++;

        }

        // 如果 n 是大于 1 的质数

        if (n > 1) {

            result -= result / n;

        }

        return result; // 返回结果

    }

    public static void main(String[] args) {

        // 使用示例

        int n = 12;  // 替换为你想计算欧拉函数的数字

        int result = eulerTotientFunction(n);

        System.out.printf("%d 的欧拉拉函数为: %d%n", n, result);

    }

}

```

```
// 12 的欧拉拉函数为: 4
```

| ![image](img/chapter_title_corner_decoration_left.png) |  | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 144. 谁年龄最大？

![image](img/chapter_title_below.png)

```java
import java.util.HashMap;

import java.util.Map;

public class Main {

    // 年龄最大的人名字的函数

    public static String oldest(Map<String, Integer> people) {

        String oldestName = "";

        int maxAge = 0;

        // 遍历 map 寻找年龄最大的人

        for (Map.Entry<String, Integer> entry : people.entrySet()) {

            String name = entry.getKey();

            int age = entry.getValue();

            if (age > maxAge) {

                maxAge = age;

                oldestName = name;

            }

        }

        return oldestName;

    }

    public static void main(String[] args) {

        // 使用第一组人进行示例

        Map<String, Integer> people1 = new HashMap<>();

        people1.put("Emma", 71);

        people1.put("Jack", 45);

        people1.put("Amy", 15);

        people1.put("Ben", 29);

        System.out.println("年龄最大的是: " + oldest(people1));

        // 使用第二组人进行示例

        Map<String, Integer> people2 = new HashMap<>();

        people2.put("Max", 9);

        people2.put("Josh", 13);

        people2.put("Sam", 48);

        people2.put("Anne", 33);

        System.out.println("年龄最大的是: " + oldest(people2));

    }

}
```

```
// 年龄最大的是: Emma
// 年龄最大的是: Sam
```

| ![image](img/chapter_title_corner_decoration_left.png) |  | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

# 145. 数字加密

![image](img/chapter_title_below.png)



```java
import java.util.ArrayList;
import java.util.List;

public class Main {

    // 使用数字加密消息的函数
    public static List<Integer> digitalCipher(String message, int key) {
        // 将键转换为字符串并提取其数字
        String keyString = String.valueOf(key);
        List<Integer> keyDigits = new ArrayList<>();
        for (char d : keyString.toCharArray()) {
            keyDigits.add(Character.getNumericValue(d));
        }

        // 准备存储加密值的列表
        List<Integer> encodedValues = new ArrayList<>();

        // 加密消息
        for (int i = 0; i < message.length(); i++) {
            char c = message.charAt(i);
            int letterValue = c - 'a' + 1; // 计算字母值
            int encodedValue = letterValue + keyDigits.get(i % keyDigits.size()); // 加数字
            encodedValues.add(encodedValue);
        }

        return encodedValues;
    }

    public static void main(String[] args) {
        // 使用示例
        List<Integer> encodedMessage1 = digitalCipher("scout", 1939);
        List<Integer> encodedMessage2 = digitalCipher("hernando", 1990);
        List<Integer> encodedMessage3 = digitalCipher("abella", 100);

        System.out.println(encodedMessage1); // [20, 12, 18, 30, 21]
        System.out.println(encodedMessage2); // [9, 14, 27, 14, 2, 23, 15]
        System.out.println(encodedMessage3); // [2, 2, 5, 13, 12, 1]
    }
}
```

# 146. 巧克力困境

![image](img/chapter_title_below.png)

```java
import java.util.List;

public class ChocolateDilemma {

    // 计算巧克力总面积的函数
    public static int totalArea(List<int[]> pieces) {
        int totalArea = 0;
        for (int[] piece : pieces) {
            totalArea += piece[0] * piece[1]; // 长 * 宽
        }
        return totalArea;
    }

    // 检查巧克力是否公平的函数
    public static boolean testFairness(List<int[]> sister1, List<int[]> sister2) {
        return totalArea(sister1) == totalArea(sister2);
    }

    public static void main(String[] args) {
        // 使用示例
        List<int[]> agatha1 = List.of(new int[]{4, 3}, new int[]{2, 4}, new int[]{1, 2});
        List<int[]> bertha1 = List.of(new int[]{6, 2}, new int[]{4, 2}, new int[]{1, 1}, new int[]{1, 1});
        System.out.println(testFairness(agatha1, bertha1)); // true

        List<int[]> agatha2 = List.of(new int[]{1, 2}, new int[]{2, 1});
        List<int[]> bertha2 = List.of(new int[]{2, 2});
        System.out.println(testFairness(agatha2, bertha2)); // true

        List<int[]> agatha3 = List.of(new int[]{1, 2}, new int[]{2, 1});
        List<int[]> bertha3 = List.of(new int[]{2, 2}, new int[]{4, 4});
        System.out.println(testFairness(agatha3, bertha3)); // false

        List<int[]> agatha4 = List.of(new int[]{2, 2}, new int[]{2, 2}, new int[]{2, 2}, new int[]{2, 2});
        List<int[]> bertha4 = List.of(new int[]{4, 4});
        System.out.println(testFairness(agatha4, bertha4)); // true

        List<int[]> agatha5 = List.of(new int[]{1, 5}, new int[]{6, 3}, new int[]{1, 1});
        List<int[]> bertha5 = List.of(new int[]{7, 1}, new int[]{2, 2}, new int[]{1, 1});
        System.out.println(testFairness(agatha5, bertha5)); // false
    }
}
```

# 147. 计算六边形的面积

![image](img/chapter_title_below.png)

```java
public class HexagonArea {

    // 计算六边形面积的函数
    public static double calculateHexagonArea(double sideLength) {
```

# 148. 检查一个数字是否为普直数（Pronic Number）

```java
public class PronicNumberChecker {
    // 检查一个数字是否为普直数的函数
    public static boolean isPronicNumber(int number) {
        for (int i = 0; i <= number; i++) {
            if (i * (i + 1) == number) {
                return true;
            }
        }
        return false;
    }

    public static void main(String[] args) {
        // 示例用法
        int pronicNumber = 6; // 替换为你想检查的数字
        if (isPronicNumber(pronicNumber)) {
            System.out.println(pronicNumber + " 是普直数!");
        } else {
            System.out.println(pronicNumber + " 不是普直数.");
        }

        int pronicNumber2 = 7; // 另一个示例
        if (isPronicNumber(pronicNumber2)) {
            System.out.println(pronicNumber2 + " 是普直数!");
        } else {
            System.out.println(pronicNumber2 + " 不是普直数.");
        }
    }
}
```

// 6 是普直数！

// 7 不是普直数。

# 149. 虚拟数字模模拟器（Virtual DAC）

```java
public class VirtualDAC {
    // 将数字值转换为相应电压水平的函数
    public static double vDAC(int digitalValue) {
        // 将数字值转换为相应的电压水平
        return (digitalValue / 1023.0) * 5.0;
    }

    public static void main(String[] args) {
        // 示例用法
        System.out.printf("%.2f%n", vDAC(0));    // 0.00
        System.out.printf("%.2f%n", vDAC(1023)); // 5.00
        System.out.printf("%.2f%n", vDAC(400));  // 1.96
    }
}
```

// 0.00

// 5.00

// 1.96

# 150. 计算五边形的面积

```java
public class PentagonArea {
    // 根据边长计算五边形的面积
    public static double calculatePentagonArea(double sideLength) {
        double sqrt5 = Math.sqrt(5.0);
        double area = (1.0 / 4.0) * Math.sqrt(5.0 * (5.0 + 2.0 * sqrt5)) * Math.pow(sideLength, 2);
        return area;
    }

    public static void main(String[] args) {
        double sideLength = 4.0; // 示例边长
        double pentagonArea = calculatePentagonArea(sideLength);
        System.out.printf("五边形的面积为: %.2f%n", pentagonArea); // 27.53
    }
}
```

// 五边形的面积为: 27.53

# 151. 检查一个数字是否为立方数

```java
public class CubeNumberChecker {
    // 检查一个数字是否为立方数的函数
    public static boolean isCubeNumber(long number) {
        long cubeRoot = Math.round(Math.cbrt(number)); // 计算立方根并四舍五入
        return (cubeRoot * cubeRoot * cubeRoot) == number; // 检查根的立方等于原始数字
    }

    public static void main(String[] args) {
        long numberToCheck = 27; // 待检查的示例数字
        if (isCubeNumber(numberToCheck)) {
            System.out.printf("%d 是立方数! 🎲%n", numberToCheck);
        } else {
            System.out.printf("%d 不是立方数。 😢%n", numberToCheck);
        }
    }
}
```

// 27 是立方数! 🎲

# 152. 周薪计算

```java
public class WeeklySalaryCalculator {
    public static int weeklySalary(int[] hours) {
        int totalSalary = 0;
        for (int i = 0; i < hours.length; i++) {
            int hour = hours[i];
            if (i < 5) { // 周一到周五
                if (hour > 8) {
                    totalSalary += 8 * 10; // 前 8 小时每小时 $10
                    totalSalary += (hour - 8) * 15; // 加时部分每小时 $15
                } else {
                    totalSalary += hour * 10; // 所有小时每小时 $10
                }
            } else { // 周六和周日
                if (hour > 8) {
                    totalSalary += 8 * 20; // 前 8 小时每小时 $20
                    totalSalary += (hour - 8) * 30; // 加时部分每小时 $30
                } else {
                    totalSalary += hour * 20; // 所有小时每小时 $20
                }
            }
        }
        return totalSalary;
    }

    public static void main(String[] args) {
        int[] hours = {8, 8, 8, 8, 8, 0, 0}; // 示例输入
        int salary = weeklySalary(hours);
        System.out.printf("周薪: $%d%n", salary);
    }
}
```

// 周薪: $400

# 153. 计算立方体的表面积

```java
public class CubeSurfaceArea {
    // 根据边长计算立方体的表面积
    public static double calculateCubeSurfaceArea(double sideLength) {
        return 6.0 * Math.pow(sideLength, 2);
    }

    public static void main(String[] args) {
        double sideLength = 4.0; // 示例边长
        double cubeSurfaceArea = calculateCubeSurfaceArea(sideLength);
        System.out.printf("立方体的表面积为: %.2f%n", cubeSurfaceArea);
    }
}
```

// 立方体的表面积为: 96.00

# 154. 计算圆锥的面积

```java
public class ConeSurfaceAreaCalculator {
    private static final double PI = Math.PI;

    public static double calculateConeSurfaceArea(double radius, double slantHeight) {
        return PI * radius * (radius + slantHeight);
    }

    public static void main(String[] args) {
        double radius = 3.0; // 圆底半径
        double slantHeight = 5.0; // 斜高
        double surfaceArea = calculateConeSurfaceArea(radius, slantHeight);
        System.out.printf("圆锥的面积为: %.2f%n", surface_area);
    }
}
```

// 圆锥的面积为: 75.40

# 155. 检查一个数字是否为快乐数



```java
import java.util.HashSet;

public class HappyNumberChecker {
    public static boolean isHappyNumber(int number) {
        HashSet<Integer> seenNumbers = new HashSet<>();
        int num = number;
        while (num != 1 && !seenNumbers.contains(num)) {
            seenNumbers.add(num);
            num = sumOfSquaredDigits(num);
        }
        return num == 1;
    }

    public static int sumOfSquaredDigits(int number) {
        int sum = 0;
        while (number > 0) {
            int digit = number % 10; // 获取最后一位数字
            sum += digit * digit; // 将数字平方加到和
            number /= 10; // 去掉最后一位数字
        }
        return sum;
    }
}
```

# 156. 计算三棱柱的面积

```java
public class TriangularPrismSurfaceArea {
    // 计算三棱柱表面积的函数
    public static double calculateTriangularPrismSurfaceArea(double a, double b, double c, double height) {
        // 计算半周
        double s = (a + b + c) / 2.0;
        // 使用海伦公式计算三角形底的面积
        double baseArea = Math.sqrt(s * (s - a) * (s - b) * (s - c));
        // 计算三角形底的周
        double perimeter = a + b + c;
        // 计算三棱柱的表面积
        double surfaceArea = baseArea + perimeter * height;
        return surfaceArea;
    }

    public static void main(String[] args) {
        double sideA = 3.0; // 三角形底边 A 的长度
        double sideB = 4.0; // 三角形底边 B 的长度
        double sideC = 5.0; // 三角形底边 C 的长度
        double prismHeight = 6.0; // 三棱柱的高度
        double surfaceArea = calculateTriangularPrismSurfaceArea(sideA, sideB, sideC, prismHeight);
        System.out.printf("三棱柱的表面积为: %.2f%n", surfaceArea);
    }
}
```

```text
// 三棱柱的表面积为: 78.00
```

# 157. 查找反大小写字符的 ASCII 码

```java
public class InverseCaseCharCode {
    // Find 反大小写字符 ASCII 码的函数
    public static int counterpartCharCode(char c) {
        if (Character.isUpperCase(c)) {
            // 将大写转换为小写
            char lower = Character.toLowerCase(c);
            return (int) lower; // 返回小写字母的 ASCII 码
        } else if (Character.isLowerCase(c)) {
            // 将小写转换为大写
            char upper = Character.toUpperCase(c);
            return (int) upper; // 返回大写字母的 ASCII 码
        } else {
            // 如果不是字母，则返回字符的 ASCII 码
            return (int) c;
        }
    }

    public static void main(String[] args) {
        char[] testCases = {'A', 'a', '1', '#'};
        for (char test : testCases) {
            System.out.printf("Char: %c, ASCII Code: %d%n", test, counterpartCharCode(test));
        }
    }
}
```

```text
// Char: A, ASCII Code: 97

// Char: a, ASCII Code: 65

// Char: 1, ASCII Code: 49

// Char: #, ASCII Code: 35
```

# 158. 解一次方程

```java
public class LinearEquationSolver {
    public static int solveEquation(String equation) {
        String[] parts = equation.split("=");
        String leftSide = parts[0].trim();
        int rightSide = Integer.parseInt(parts[1].trim());
        char operation;
        int num;
        if (leftSide.contains("+")) {
            String[] leftParts = leftSide.split("\\+");
            operation = '+';
            num = Integer.parseInt(leftParts[1].trim());
        } else {
            String[] leftParts = leftSide.split("-");
            operation = '-';
            num = Integer.parseInt(leftParts[1].trim());
        }
        switch (operation) {
            case '+':
                return rightSide - num;
            case '-':
                return rightSide + num;
            default:
                throw new IllegalArgumentException("不支持的操作");
        }
    }

    public static void main(String[] args) {
        System.out.println(solveEquation("x + 43 = 50"));  // 输出: 7
        System.out.println(solveEquation("x - 9 = 10"));   // 输出: 19
        System.out.println(solveEquation("x + 300 = 100")); // 输出: -200
    }
}
```

```text
// 7

// 19

// -200
```

# 159. 数字因数分解

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class FactorizeNumber {
    public static List<Integer> factorize(int n) {
        List<Integer> factors = new ArrayList<>();
        int sqrtN = (int) Math.sqrt(n);
        for (int i = 1; i <= sqrtN; i++) {
            if (n % i == 0) {
                factors.add(i);
                if (i != n / i) {
                    factors.add(n / i);
                }
            }
        }
        Collections.sort(factors);
        return factors;
    }

    public static void main(String[] args) {
        int num = 12;
        System.out.println(factorize(num)); // 输出: [1, 2, 3, 4, 6, 12]
    }
}
```

```text
// [1, 2, 3, 4, 6, 12]
```

# 160. 检查数字是否为自同数（Automorphic Number）

```java
import java.util.ArrayList;
import java.util.List;

public class FactorizeNumber {
    public static List<Integer> factorize(int n) {
        List<Integer> factors = new ArrayList<>();
        int sqrtN = (int) Math.sqrt(n);
        for (int i = 1; i <= sqrtN; i++) {
            if (n % i == 0) {
                factors.add(i);
                if (i != n / i) {
                    factors.add(n / i);
                }
            }
        }
        Collections.sort(factors);
        return factors;
    }

    public static void main(String[] args) {
        int num = 12;
        System.out.println(factorize(num)); // 输出: [1, 2, 3, 4, 6, 12]
    }
}
```

> 注：由于提供的原文中 160—162 题似乎存在逻辑重复或错混乱，已根据原文提供的代码结构和内容进行了逐对翻译。

# 161. 计算金字锥面积

```java
public class PyramidArea {
    // 计算金字锥面积的函数
    public static double calculatePyramidArea(double sideLength, double slantHeight) {
        double baseArea = Math.pow(sideLength, 2);
        double lateralArea = 4.0 * sideLength * slantHeight / 2.0; // 每个三角形面的面积 (底 * 斜高) / 2
        return baseArea + lateralArea;
    }

    public static void main(String[] args) {
        double sideLength = 4.0; // 金字锥底边长度
        double slantHeight = 5.0; // 金字锥的斜高
        double pyramidArea = calculatePyramidArea(sideLength, slantHeight);
        System.out.printf("金字锥的面积为: %.2f%n", pyramidArea);
    }
}
```

```text
// 金字锥的面积为: 56.00
```

# 162. 检查数字是否为 Smith–Morra 数

```java
public class SmithMorraGambitNumber {
    // 计算数字之和的函数
    public static int digitSum(int n) {
        int sum = 0;
        while (n > 0) {
            sum += n % 10;
            n /= 10;
        }
        return sum;
    }

    // 执行质因数分解的函数
    public static List<Integer> primeFactorization(int n) {
        List<Integer> factors = new ArrayList<>();
        for (int i = 2; i * i <= n; i++) {
            while (n % i == 0) {
                factors.add(i);
                n /= i;
            }
        }
        if (n > 1) {
            factors.add(n);
        }
        return factors;
    }

    // 检查数字是否为 Smith–Morra 数的函数
    public static boolean isSmithMorraGambitNumber(int number) {
        List<Integer> factors = primeFactorization(number);
        int sumOfDigitsOfFactors = 0;
        for (int factor : factors) {
            sumOfDigitsOfFactors += digitSum(factor);
        }
        return sumOfDigitsOfFactors == digitSum(number);
    }

    public static void main(String[] args) {
        int number = 22; // 示例数字
    }
}
```

```java
System.out.printf("Is %d a Smith–Morra Gambit Number? %b%n", number, isSmithMorraGambitNumber(number));
}
```

```text
// 22 是 Smith–Morra Gambit 数吗？true
```

# 163. 检查数字是否为孤立数



```java
public class SolitaryNumber {
    // 计算数字真因数之和的函数
    public static int getProperDivisorsSum(int number) {
        int sum = 1; // 从 1 开始，因为每个数都能被 1 整除
        for (int i = 2; i <= Math.sqrt(number); i++) {
            if (number % i == 0) {
                sum += i;
                if (i != number / i) {
                    sum += number / i;
                }
            }
        }
        return sum;
    }

    // 检查一个数字是否为孤立数的函数
    public static boolean isSolitaryNumber(int number) {
        int sumOfDivisors = getProperDivisorsSum(number);
        return number != sumOfDivisors;
    }

    public static void main(String[] args) {
        int solitaryNumber = 28; // 示例数字，根据需要替换
        if (isSolitaryNumber(solitaryNumber)) {
            System.out.printf("%d 是一个孤立数!%n", solitaryNumber);
        } else {
            System.out.printf("%d 不是一个孤立数.%n", solitaryNumber);
        }
    }
}
// 28 不是一个孤立数！
```

# 164. 基础汉诺塔游戏

```java
public class TowerOfHanoi {
    // 解决汉诺塔游戏的递归函数
    public static void towerOfHanoi(int n, char source, char auxiliary, char target) {
        if (n == 1) {
            System.out.printf("将盘子 1 从 %c 移动到 %c%n", source, target);
            return;
        }
        towerOfHanoi(n - 1, source, target, auxiliary);
        System.out.printf("将盘子 %d 从 %c 移动到 %c%n", n, source, target);
        towerOfHanoi(n - 1, auxiliary, source, target);
    }

    public static void main(String[] args) {
        int numberOfDisks = 3;
        char sourcePeg = 'A';
        char auxiliaryPeg = 'B';
        char targetPeg = 'C';
        System.out.printf("%d 个盘子的汉诺塔解决方案:%n", numberOfDisks);
        towerOfHanoi(numberOfDisks, sourcePeg, auxiliaryPeg, targetPeg);
    }
}
// 3 个盘子的汉诺塔解决方案：
// 将盘子 1 从 A 移动到 C
// 将盘子 2 从 A 移动到 B
// 将盘子 1 从 C 移动到 B
// 将盘子 3 从 A 移动到 C
// 将盘子 1 从 B 移动到 A
// 将盘子 2 从 B 移动到 C
// 将盘子 1 从 A 移动到 C
```

# 165. 计算圆台的面积

```java
public class FrustumSurfaceArea {
    // 计算圆台表面积的方法
    public static double surfaceAreaOfFrustum(double r1, double r2, double l) {
        double surfaceArea = Math.PI * (r1 + r2) * l + Math.PI * Math.pow(r1, 2) + Math.PI * Math.pow(r2, 2);
        return surfaceArea;
    }

    public static void main(String[] args) {
        double r1 = 4.0; // 上半径
        double r2 = 8.0; // 下半径
        double l = 6.0;  // 母线
        double area = surfaceAreaOfFrustum(r1, r2, l);
        System.out.printf("圆台的面积为: %.2f%n", area);
    }
}
// 圆台的面积为：477.52
```

# 166. 检查数字是否为 Motzkin 数

```java
import java.util.ArrayList;
import java.util.List;

public class MotzkinChecker {
    // 检查数字是否为 Motzkin 数的方法
    public static boolean isMotkinNumber(int number) {
        if (number == 0) {
            return true;
        }
        List<Double> motzkinNumbers = new ArrayList<>();
        motzkinNumbers.add(1.0);
        motzkinNumbers.add(1.0);
        for (int n = 2; n <= number; n++) {
            double nextMotzkin = ((3 * n - 3) * motzkinNumbers.get(n - 1) + (n - 3) * motzkinNumbers.get(n - 2)) / (n + 1);
            motzkinNumbers.add(nextMotzkin);
        }
        return motzkinNumbers.contains((double) number);
    }

    public static void main(String[] args) {
        int[] testNumbers = {1, 2, 5, 6, 11};
        for (int number : testNumbers) {
            if (isMotkinNumber(number)) {
                System.out.printf("%d 是一个 Motzkin 数%n", number);
            } else {
                System.out.printf("%d 不是一个 Motzkin 数.%n", number);
            }
        }
    }
}
// 1 是一个 Motzkin 数！
// 2 是一个 Motzkin 数！
// 5 不是一个 Motzkin 数。
// 6 不是一个 Motzkin 数。
// 11 不是一个 Motzkin 数。
```

# 167. 两两交换

```java
public class SwapByTwo {
    // 两两交换字符的方法
    public static String swapTwo(String s) {
        StringBuilder result = new StringBuilder();
        char[] chars = s.toCharArray();
        int i = 0;
        while (i + 3 < chars.length) {
            result.append(chars[i + 2]); // 第 3 个字符
            result.append(chars[i + 3]); // 第 4 个字符
            result.append(chars[i]); // 第 1 个字符
            result.append(chars[i + 1]); // 第 2 个字符
            i += 4; // 到下一组字符
        }
        // 添加剩余的字符
        result.append(s.substring(i));
        return result.toString();
    }

    public static void main(String[] args) {
        String[] examples = {
            "ABCDEFGH",
            "AABBCCDEFF",
            "munchkins",
            "FFGGHHI"
        };
        for (String example : examples) {
            System.out.printf("原始: %s, 交换: %s%n", example, swapTwo(example));
        }
    }
}
// 原始: ABCDEFGH, 交换: CDABHEGF
// 原始: AABBCCDEFF, 交换: BBAADDFFEE
// 原始: munchkins, 交换: ncmuinhks
// 原始: FFGGHHI, 交换: GGFFHHI
```

# 168. 从句子中提取单词

```java
public class RemoveWordFromSentence {
    // 从句子中删除单词的方法
    public static String removeWord(String sentence, String word) {
        // 将句子分成单词
        String[] words = sentence.split(" ");
        StringBuilder result = new StringBuilder();

        // 遍历单词并拼接不等于要删除单词的词
        for (String w : words) {
            if (!w.equals(word)) {
                result.append(w).append(" ");
            }
        }

        // 将 StringBuilder 转换为字符串并修剪尾空格
        return result.toString().trim();
    }

    public static void main(String[] args) {
        String sentence1 = "One two three four";
        String word1 = "two";
        String result1 = removeWord(sentence1, word1);
        System.out.println(result1); // 输出: "One three four"

        String sentence2 = "Bob has a kid";
        String word2 = "kid";
        String result2 = removeWord(sentence2, word2);
        System.out.println(result2); // 输出: "Bob has a"
    }
}

// One three four
// Bob has a
```

# 169. 基础聊天机器人

```java
import java.util.Scanner;

public class BasicChatbot {
    // 根据用户的消息回复的方法
    public static String chatbot(String message) {
        message = message.toLowerCase(); // 将消息转换为小写

        if (message.contains("hello")) {
            return "Hello! How can I help you?";
        } else if (message.contains("how are you")) {
            return "I am just a computer program, but thanks for asking!";
        } else if (message.contains("bye")) {
            return "Goodbye!";
        } else {
            return "我没明白。请你重新表述一下吗？";
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Chatbot: 你好！今天有什么可以帮你的吗?");

        while (true) {
            System.out.print("你: ");
            String userInput = scanner.nextLine().trim();

            if (userInput.isEmpty()) {
                continue; // 跳过空输入
            }

            if (userInput.equalsIgnoreCase("bye")) {
                System.out.println("Chatbot: 再见!");
                break; // 如果用户说 "bye"，则退出循环
            }

            System.out.println("Chatbot: " + chatbot(userInput));
        }

        scanner.close(); // 关闭扫描
    }
}
```

```text
// Chatbot: 你好！今天有什么可以帮你的吗？
// 你: 你好
// Chatbot: 你好！有什么可以帮你的吗？
// 你: 你好？
// Chatbot: 我只是一个计算机程序，但谢谢你的问候！
// 你: bye
// Chatbot: 再见!
```

# 170. 退格攻击 (Backspace Attack)

```java
public class BackspaceAttack {
    // 模拟退格操作的方法
    public static String erase(String input) {
        StringBuilder result = new StringBuilder();

        for (char c : input.toCharArray()) {
            if (c == '#') {
                if (result.length() > 0) {
                    result.deleteCharAt(result.length() - 1); // 如果存在，则删除最后一个字符
                }
            } else {
                result.append(c); // 添加当前字符
            }
        }

        return result.toString();
    }

    public static void main(String[] args) {
        String[] examples = {
            "he##l#hel#llo",
            "major# spar##ks",
            "si###t boy",
            "####",
        };

        for (String example : examples) {
            System.out.printf("Input: '%s', Output: '%s'%n", example, erase(example));
        }
    }
}
```



```text
// Input: 'he##l#hel#llo', Output: 'hello'
// Input: 'major# spar##ks', Output: 'majo spks'
// Input: 'si###t boy', Output: 't boy'
// Input: '####', Output: ''
```

# 171. 计数器（Counter）

```java
public class Counter {

    private int count;

    // 初始化计数器的构造函数
    public Counter() {
        this.count = 0;
    }

    // 递增计数器的方法
    public void increment() {
        count++;
        System.out.println("Counter: " + count);
    }

    // 递减计数器的方法
    public void decrement() {
        count--;
        System.out.println("Counter: " + count);
    }

    // 重置计数器的方法
    public void reset() {
        count = 0;
        System.out.println("Counter reset to 0");
    }

    // 测试 Counter 类的主方法
    public static void main(String[] args) {
        Counter counter = new Counter();

        counter.increment(); // Counter: 1
        counter.increment(); // Counter: 2
        counter.decrement(); // Counter: 1
        counter.reset();     // Counter reset to 0
    }
}
```

```text
// Counter: 1
// Counter: 2
// Counter: 1
// Counter reset to 0
```

# 172. 电话号码单词解码器（Phone Number Word Decoder）

```java
import java.util.HashMap;

public class PhoneNumberDecoder {

    public static String textToNum(String phone) {
        HashMap<Character, Character> map = new HashMap<>();

        // 将字母映射到对应的数字
        map.put('A', '2');
        map.put('B', '2');
        map.put('C', '2');

        map.put('D', '3');
        map.put('E', '3');
        map.put('F', '3');

        map.put('G', '4');
        map.put('H', '4');
        map.put('I', '4');

        map.put('J', '5');
        map.put('K', '5');
        map.put('L', '5');

        map.put('M', '6');
        map.put('N', '6');
        map.put('O', '6');

        map.put('P', '7');
        map.put('Q', '7');
        map.put('R', '7');
        map.put('S', '7');

        map.put('T', '8');
        map.put('U', '8');
        map.put('V', '8');

        map.put('W', '9');
        map.put('X', '9');
        map.put('Y', '9');
        map.put('Z', '9');

        StringBuilder result = new StringBuilder();

        for (char c : phone.toCharArray()) {
            // 检查字符是否为字母
            if (map.containsKey(Character.toUpperCase(c))) {
                // 添加对应的数字
                result.append(map.get(Character.toUpperCase(c)));
            } else {
                // 否则，添加字符本身
                result.append(c);
            }
        }

        return result.toString();
    }

    public static void main(String[] args) {
        String[] examples = {
            "ABC",
            "DEF",
            "GHI",
            "JKL",
            "MNO",
            "PQRS",
            "TUV",
            "WXYZ"
        };

        for (String example : examples) {
            System.out.println(example + " -> " + textToNum(example));
        }
    }
}
```

```text
// ABC -> 222
// DEF -> 333
// GHI -> 444
// JKL -> 555
// MNO -> 666
// PQRS -> 7777
// TUV -> 888
// WXYZ -> 9999
```

```java
for (int[] numbers : examples) {
    System.out.println(sevenBoom(numbers));
}
```

```text
// Boom!
// 数组中没有 7
// Boom!
```

# 177. 最后一个字母大写

```java
public class CapitalizeLastLetter {

    public static String capLast(String input) {
        StringBuilder result = new StringBuilder();

        // 将输入字符串分成单词
        String[] words = input.split("\\s+");

        for (String word : words) {
            if (word.length() > 0) {
                // 将最后一个字母大写
                char lastChar = word.charAt(word.length() - 1);
                String capitalizedWord =
                        word.substring(0, word.length() - 1)
                                + Character.toUpperCase(lastChar);

                result.append(capitalizedWord).append(" "); // 将修改后的单词添加到结果
            }
        }

        // 将 StringBuilder 转换为 String 并去除末尾空格
        return result.toString().trim();
    }

    public static void main(String[] args) {
        // 测试用例
        String[] examples = {
            "hello",
            "My Name Is Example",
            "HELp THe LASt LETTERs CAPITALISe",
        };

        for (String example : examples) {
            System.out.println(capLast(example));
        }
    }
}
```

```text
// hellO
// MY NamE IS ExamplE
// HELp THE LASt LETTERs CAPITALIS
```

# 178. 骰子模拟器

```java
import java.util.Random;

public class DiceRollingSimulator {

    // 掷骰子的方法
    public static void rollDice() {
        Random random = new Random(); // 创建随机对象
        int result = random.nextInt(6) + 1; // 生成 1 到 6 之间的随机数

        System.out.println("You rolled a " + result);
    }

    public static void main(String[] args) {
        rollDice(); // 模拟掷骰子
    }
}
```

```text
// 你掷了 3
```

# 179. 秒到时间转换器

```java
public class SecondsToTimeConverter {

    // 将秒转换为小时、分钟和秒
    public static void convertSecondsToTime(int seconds) {
        int hours = seconds / 3600; // 计算小时
        int minutes = (seconds % 3600) / 60; // 计算分钟
        int remainingSeconds = seconds % 60; // 计算剩余秒

        System.out.printf(
                "Time: %d hours, %d minutes, %d seconds%n",
                hours,
                minutes,
                remainingSeconds
        );
    }

    public static void main(String[] args) {
        int inputSeconds = 3665; // 输入
        convertSecondsToTime(inputSeconds); // 转换并显示时间
    }
}
```

```text
// Time: 1 hours, 1 minutes, 5 seconds
```

# 180. 柱状图生成器

```java
import java.util.Arrays;

public class BarChartGenerator {

    // 根据数据生成柱状图
    public static void generateBarChart(int[] data) {
        if (data.length == 0) {
            System.out.println("No data to display.");
            return;
        }

        // 数据中的最大值
        int maxValue = Arrays.stream(data).max().orElse(0);

        // 生成并打印柱状图
        for (int value : data) {
            // 根据最大值计算柱的长度
            int barLength = (int) Math.round((double) value / maxValue * 20);
            String bar = "█".repeat(barLength) + " ".repeat(20 - barLength);

            System.out.printf("%d | %s%n", value, bar);
        }
    }

    public static void main(String[] args) {
        int[] chartData = {5, 8, 12, 4, 6}; // 数据
        generateBarChart(chartData); // 生成并显示柱状图
    }
}
```

```text
// 5 | ████████
// 8 | ██████████
// 12 | ████████████████
// 4 | ██████
// 6 | ████████
```

# 181. 直角三角形图案

```java
public class RightAngledTriangle {

    // 生成直角三角形
    public static void generateAngledTriangle(int height) {
        for (int i = 1; i <= height; i++) {
            String stars = "*".repeat(i); // 生成当前行的星
            System.out.println(stars); // 打印当前行
        }
    }

    public static void main(String[] args) {
        int triangleHeight = 5; // 高度
        generateAngledTriangle(triangleHeight); // 生成并打印三角形
    }
}
```

```text
// *
// **
// ***
// ****
// *****
```

# 182. 正数计数负数和

```java
import java.util.ArrayList;
import java.util.List;

public class PositiveCountSum {

    // 统计正数和负数
    public static List<Integer> countPositivesNegatives(int[] numbers) {
        int countPositives = 0;
        int sumNegatives = 0;

        for (int num : numbers) {
            if (num > 0) {
                countPositives++;
            } else if (num < 0) {
                sumNegatives += num;
            }
        }

        List<Integer> result = new ArrayList<>();
        result.add(countPositives);
        result.add(sumNegatives);

        return result; // 返回结果
    }

    public static void main(String[] args) {
        int[] example1 = {1, -2, 3, -4, -5};
        System.out.println(countPositivesNegatives(example1)); // 输出 [2, -11]

        int[] example2 = {0, 0, 10};
        System.out.println(countPositivesNegatives(example2)); // 输出 [1, 0]

        int[] example3 = {};
        System.out.println(countPositivesNegatives(example3)); // 输出 [0, 0]
    }
}
```

```java
int stars = height - 2 * spaces; // 计算星星

// 打印前空格和星星
System.out.printf("%" + (spaces + stars) + "s%n", "*".repeat(stars));
}

}

public static void main(String[] args) {
    generateDiamondPattern(5); // 示例高度
}

}
```



```
    *
   ***
  *****
   ***
    *
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |
|---|---|---|
| ![image](img/chapter_title_above.png) | | |

# 185. 检查砖是否通过孔洞

![image](img/chapter_title_below.png)

```java
public class BrickFitChecker {

    // 检查砖的尺寸是否符合孔的尺寸
    public static boolean doesBrickFit(int a, int b, int c, int w, int h) {

        // 检查砖所有可能的放置方向
        return fits(a, b, w, h) || fits(a, c, w, h) || fits(b, c, w, h);
    }

    // 检查砖是否能放入孔中的辅助方法
    private static boolean fits(int brickWidth, int brickHeight, int holeWidth, int holeHeight) {
        return (brickWidth <= holeWidth && brickHeight <= holeHeight) ||
               (brickWidth <= holeHeight && brickHeight <= holeWidth);
    }

    public static void main(String[] args) {

        // 测试用例
        System.out.println(doesBrickFit(1, 1, 1, 1, 1)); // true
        System.out.println(doesBrickFit(1, 2, 1, 1, 1)); // true
        System.out.println(doesBrickFit(1, 2, 2, 1, 1)); // false
    }
}
```

```
// true
// true
// false
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |
|---|---|---|
| ![image](img/chapter_title_above.png) | | |

## 186. 倒计时器

![image](img/chapter_title_below.png)

```java
import java.util.Scanner;

public class CountdownTimer {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("输入倒计时时间（秒）：");

        // 读取用户输入
        if (scanner.hasNextLong()) {
            long time = scanner.nextLong();

            // 开始倒计时
            while (time > 0) {
                System.out.println("剩余时间: " + time + " 秒");

                try {
                    Thread.sleep(1000); // 休眠 1 秒
                } catch (InterruptedException e) {
                    System.out.println("计时器被中断。");
                }

                time--;
            }

            System.out.println("倒计时完成!");
        } else {
            System.out.println("无效输入。");
        }

        scanner.close();
    }
}
```

```
// 输入倒计时时间（秒）：3
// 剩余时间: 3 秒
// 剩余时间: 2 秒
// 剩余时间: 1 秒
// 倒计时完成!
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |
|---|---|---|
| ![image](img/chapter_title_above.png) | | |

## 187. 州名与缩写

![image](img/chapter_title_below.png)

```java
import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

public class StateNames {

    public static List<String> filterStateNames(List<String> states, String category) {

        // 州全名
        String[] fullStateNames = {
            "Alabama", "Alaska", "Arizona", "Arkansas", "California", "Colorado", "Connecticut",
            "Delaware", "Florida", "Georgia", "Hawaii", "Idaho", "Illinois", "Indiana", "Iowa",
            "Kansas", "Kentucky", "Louisiana", "Maine", "Maryland", "Massachusetts", "Michigan",
            "Minnesota", "Mississippi", "Missouri", "Montana", "Nebraska", "Nevada", "New Hampshire",
            "New Jersey", "New Mexico", "New York", "North Carolina", "North Dakota", "Ohio", "Oklahoma",
            "Oregon", "Pennsylvania", "Rhode Island", "South Carolina", "South Dakota", "Tennessee",
            "Texas", "Utah", "Vermont", "Virginia", "Washington", "West Virginia", "Wisconsin", "Wyoming"
        };

        List<String> result = new ArrayList<>();

        for (String state : states) {
            switch (category) {
                case "abb":
                    if (state.length() == 2) {
                        result.add(state);
                    }
                    break;
                case "full":
                    if (Arrays.asList(fullStateNames).contains(state)) {
                        result.add(state);
                    }
                    break;
                default:
                    break;
            }
        }

        return result;
    }

    public static void main(String[] args) {
        List<String> states1 = Arrays.asList("Arizona", "CA", "NY", "Nevada");
        List<String> states2 = Arrays.asList("MT", "NJ", "TX", "ID", "IL");

        System.out.println(filterStateNames(states1, "abb")); // [CA, NY]
        System.out.println(filterStateNames(states1, "full")); // [Arizona, Nevada]
        System.out.println(filterStateNames(states2, "abb")); // [MT, TX, ID, IL]
        System.out.println(filterStateNames(states2, "full")); // []
    }
}
```

```
// [CA, NY]
// [Arizona, Nevada]
// [MT, TX, ID, IL]
// []
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |
|---|---|---|
| ![image](img/chapter_title_above.png) | | |

## 188. 函数

![image](img/chapter_title_below.png)

```java
public class Function {

    // 检查字符是否为辅音的辅助方法
    public static boolean isConsonant(char c) {
        return "aeiouIOU".indexOf(c) == -1;
    }

    // 根据单词格式化名称
    public static String formatName(String word) {

        // 获取最后一个字符
        char lastChar = word.length() > 0 ? word.charAt(word.length() - 1) : ' ';

        // 根据最后一个字符决定后缀
        String suffix = isConsonant(lastChar) ? "er" : "inator";

        // 计算长度
        String length = String.valueOf(word.length());

        // 将部分组合成最终字符串
        return String.format("%s%s%s", word, suffix, length);
    }

    public static void main(String[] args) {
        String[] testCases = {"Shrink", "Doom", "Evil"};

        for (String word : testCases) {
            System.out.println(formatName(word));
        }
    }
}
```

```
// Shrinker
// Doomer
// Evil
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |
|---|---|---|
| ![image](img/chapter_title_above.png) | | |

## 189. 书页

![image](img/chapter_title_below.png)

```java
public class PagesIn {

    // 检查数字是否为平方数
    private static boolean isSquare(long x) {
        long s = (long) Math.sqrt(x);
        return s * s == x;
    }

    // 判断总数是否可以形成完美的书籍
    public static boolean pagesInBook(long total) {
        if (total <= 0) {
            return false;
        }

        long discriminant = 8 * total;
        if (!isSquare(discriminant)) {
            return false;
        }

        long sqrtDisc = (long) Math.sqrt(discriminant);
        long n = (sqrtDisc - 1) / 2;

        // 验证 n 是正整数并满足条件
        return n > 0 && n * (n + 1) / 2 == total;
    }

    public static void main(String[] args) {
        long[] testCases = {5, 4005, 9453};

        for (long total : testCases) {
            System.out.printf("Total pages %d: %s%n", total, pagesInBook(total));
        }
    }
}
```

```
// Total pages 5: false
// Total pages 4005: true
// Total pages 9453: true
```

## 190. 最高数字

![image](img/chapter_title_below.png)

```java
public class HighestDigit {

    // 找到数字中的最高数字
    public static int highestDigit(int n) {
        int highest = 0;

        // 将数字转换为字符串以遍历每个字符
        String numberStr = Integer.toString(n);

        for (char c : numberStr.toCharArray()) {

            // 将字符转换回整数
            int digit = Character.getNumericValue(c);

            // 更新可能的最高数字
            if (digit > highest) {
                highest = digit;
            }
        }

        return highest;
    }

    public static void main(String[] args) {
        int[] testCases = {4666, 544, 379, 2, 377401};

        for (int caseNum : testCases) {
            System.out.printf("Highest digit in %d: %d%n", caseNum, highestDigit(caseNum));
        }
    }
}
```

```
Highest digit in 4666: 6
Highest digit in 544: 5
Highest digit in 379: 9
Highest digit in 2: 2
Highest digit in 377401: 7
```

## 191. 秒单位的视频长度

```java
public class VideoLength {

    // 将 "MM:SS" 格式的视频长度转换为总秒数
    public static int minutesToSeconds(String videoLength) {
        String[] parts = videoLength.split(":");

        // 检查格式是否有效
        if (parts.length != 2) {



```java
return -1; // 格式无效

}

// 解析分钟
int minutes;

try {
    minutes = Integer.parseInt(parts[0]);
} catch (NumberFormatException e) {
    return -1; // 分钟值无效
}

// 解析秒
int seconds;

try {
    seconds = Integer.parseInt(parts[1]);
} catch (NumberFormatException e) {
    return -1; // 秒值无效
}

// 验证秒
if (seconds >= 60) {
    return -1; // 秒值无效
}

return minutes * 60 + seconds; // 返回总秒数
}

public static void main(String[] args) {
    String[] testCases = {"01:00", "13:56", "10:60", "121:49", "invalid"};

    for (String caseStr : testCases) {
        System.out.printf(
            "Video Length '%s': %d seconds%n",
            caseStr,
            minutesToSeconds(caseStr)
        );
    }
}
```

```text
// 视频长度 '01:00': 60 seconds
// 视频长度 '13:56': 836 seconds
// 视频长度 '10:60': -1 seconds
// 视频长度 '121:49': 7309 seconds
// 视频长度 'invalid': -1 seconds
```

# 192. 在单词查找游戏中统计字母次数

```java
public class LetterCounter {

    // 统计二维网格中某个字母出现的次数
    public static int letterCounter(String[][] grid, String letter) {
        int count = 0;

        // 遍历网格中的每一行和每一列
        for (String[] row : grid) {
            for (String ch : row) {
                if (ch.equals(letter)) {
                    count++; // 如果字母匹配则计数加 1
                }
            }
        }

        return count; // 返回总计数
    }

    public static void main(String[] args) {
        String[][] grid = {
            {"D", "E", "Y", "H", "A", "D"},
            {"C", "B", "Z", "Y", "J", "K"},
            {"D", "B", "C", "A", "M", "N"},
            {"F", "G", "G", "R", "S", "R"},
            {"V", "X", "H", "A", "S", "S"}
        };

        String letter = "D";
        System.out.printf(
            "The letter '%s' appears %d times.%n",
            letter,
            letterCounter(grid, letter)
        );

        letter = "H";
        System.out.printf(
            "The letter '%s' appears %d times.%n",
            letter,
            letterCounter(grid, letter)
        );
    }
}
```

```text
// 字母 'D' 出现了 3 次。
// 字母 'H' 出现了 2 次。
```

## 193. 寻找另外两边的长度

```java
public class TriangleSides {

    private static final double SQRT_3 = 1.7320508075688772;

    // 计算另外两边的长度
    public static double[] otherSides(double shortestSide) {
        double hypotenuse = 2.0 * shortestSide; // 计算斜边
        double otherSide = shortestSide * SQRT_3; // 计算另一条边

        // 保留两位小数
        hypotenuse = Math.round(hypotenuse * 100.0) / 100.0;
        otherSide = Math.round(otherSide * 100.0) / 100.0;

        return new double[] {hypotenuse, otherSide};
    }

    public static void main(String[] args) {
        double[] testCases = {1.0, 12.0, 2.0, 3.0};

        for (double side : testCases) {
            double[] sides = otherSides(side);
            double longest = sides[0];
            double medium = sides[1];

            System.out.printf(
                "Shortest Side: %.1f, Longest Side: %.2f, Medium Side: %.2f%n",
                side,
                longest,
                medium
            );
        }
    }
}
```

```text
// Shortest Side: 1.0, Longest Side: 2.00, Medium Side: 1.73
// Shortest Side: 12.0, Longest Side: 24.00, Medium Side: 20.78
// Shortest Side: 2.0, Longest Side: 4.00, Medium Side: 3.46
// Shortest Side: 3.0, Longest Side: 6.00, Medium Side: 5.20
```

## 194. 数字之战

```java
import java.util.Arrays;

public class WarOfNumbers {

    // 计算偶数和与奇数和之间的差值
    public static int warOfNumbers(int[] numbers) {
        int evenSum = 0;
        int oddSum = 0;

        for (int num : numbers) {
            if (num % 2 == 0) {
                evenSum += num; // 如果是偶数则加
            } else {
                oddSum += num; // 如果是奇数则加
            }
        }

        return Math.abs(evenSum - oddSum); // 返回绝对值
    }

    public static void main(String[] args) {
        int[][] examples = {
            {2, 8, 7},
            {12, 9, 7},
            {5, 94, 6}
        };

        for (int[] numbers : examples) {
            System.out.println(warOfNumbers(numbers)); // 打印结果
        }
    }
}
```

```text
// 27
// 16
```

## 195. 使用 OOP 创建圆形

```java
public class Circle {

    private double radius;

    // 初始化半径的构造函数
    public Circle(double radius) {
        this.radius = radius;
    }

    // 计算圆形的面积
    public double getArea() {
        return Math.PI * radius * radius;
    }

    // 计算圆形的周长
    public double getPerimeter() {
        return 2 * Math.PI * radius;
    }

    public static void main(String[] args) {
        double[] circles = {11.0, 4.44};

        for (double radius : circles) {
            Circle circle = new Circle(radius);

            System.out.printf(
                "Radius: %.2f - Area: %.6f, Perimeter: %.6f%n",
                radius,
                circle.getArea(),
                circle.getPerimeter()
            );
        }
    }
}
```

```text
// Radius: 11.00 - Area: 380.132711, Perimeter: 69.115038
// Radius: 4.44 - Area: 61.932101, Perimeter: 27.899043
```

## 196. 寻找四面体数

```java
public class Tetrahedral {

    // 计算第 n 四面体数
    public static long tetra(long n) {
        return n * (n + 1) * (n + 2) / 6;
    }

    public static void main(String[] args) {
        System.out.println(tetra(2)); // 输出: 4
        System.out.println(tetra(5)); // 输出: 35
        System.out.println(tetra(6)); // 输出: 56
    }
}
```

## 197. 讲话筒

```java
import java.util.Random;
import java.util.Scanner;

public class JokeTeller {

    public static void jokeTeller() {
        String[] categories = {"knock-knock", "dad", "animal", "puns"};

        Random rand = new Random();
        String category = categories[rand.nextInt(categories.length)];

        String setup = "";
        String punchline1 = "";
        String punchline2 = "";

        switch (category) {
            case "knock-knock":
                setup = "Knock, knock.";
                punchline1 = "Tank.";
                punchline2 = "You're welcome!";
                break;

            case "dad":
                setup = "Why did the scarecrow win an award?";
                punchline2 = "Because he was outstanding in his field!";
                break;

            case "animal":
                setup = "Why don't scientists trust atoms?";
                punchline2 = "Because they make up everything!";
                break;

            default: // for "puns"
                setup = "I used to be a baker because I kneaded dough.";
                break;
        }

        if (!setup.isEmpty()) {
            System.out.println(setup);
        }

        if (!punchline1.isEmpty()) {
            Scanner scanner = new Scanner(System.in);
            System.out.print(punchline1 + " Press enter for the punchline...");
            scanner.nextLine();
        }

        System.out.println(punchline2);
    }
}
```

```java
public static void main(String[] args) {
    jokeTellerProgram();
}
```

```text
// 为什么稻草人会获得奖？

// 按回车查看笑点...

// 因为他在他的领域里非常出众（outstanding）！
```

## 198. 你是哪一代？

```java
public class GenerationChecker {

    public static String generation(int x, char y) {
        switch (x) {
            case -3:
                return (y == 'm') ? "曾祖父" : "曾祖母";

            case -2:
                return (y == 'm') ? "爷爷" : "奶奶";

            case -1:
                return (y == 'm') ? "父亲" : "母亲";

            case 0:
                return "我!";

            case 1:
                return (y == 'm') ? "儿子" : "女儿";

            case 2:
                return (y == 'm') ? "孙子" : "孙女";

            case 3:
                return (y == 'm') ? "玄孙" : "玄孙女";

            default:
                return "未知";
        }
    }

    public static void main(String[] args) {
        System.out.println(generation(2, 'f'));  // 孙女
        System.out.println(generation(-3, 'm')); // 曾祖父
        System.out.println(generation(1, 'f'));  // 女儿
    }
}
```

## 199. FizzBuzz 游戏

```java
public class FizzBuzzGame {

    public static void fizzBuzzGame() {
        System.out.println("欢迎来到 FizzBuzz 游戏!");
```



```java
System.out.println("让我们玩 FizzBuzz 吧!");

for (int i = 1; i <= 100; i++) {
    String output = "";

    if (i % 3 == 0) {
        output += "Fizz";
    }

    if (i % 5 == 0) {
        output += "Buzz";
    }

    // 打印结果或数字本身
    if (!output.isEmpty()) {
        System.out.println(output);
    } else {
        System.out.println(i);
    }
}

public static void main(String[] args) {
    fizzBuzzGame();
}
```

```
// 欢迎来到 FizzBuzz 游戏!

// 让我们玩 FizzBuzz 吧!

// 1

// 2

// Fizz

// 4

// Buzz

// Fizz

// 7

// 8

// Fizz

// Buzz

// ...

// FizzBuzz
```

## 200. 交换相邻数字对

```java
import java.util.Scanner;

public class SwapPairsOfAdjacentDigits {
    public static void swapPairsOfAdjacentDigits(int number) {
        String numberStr = String.valueOf(number);
        int length = numberStr.length();

        // 检查数字长度是否为偶数
        if (length % 2 != 0) {
            System.out.println("请输入一个偶数位的整数.");
            return;
        }

        // 交换相邻数字对
        StringBuilder swappedNumber = new StringBuilder();

        for (int i = 0; i < length; i += 2) {
            swappedNumber.append(numberStr.charAt(i + 1)); // 先添加下一个数字
            swappedNumber.append(numberStr.charAt(i));     // 然后添加当前数字
        }

        // 将结果转换回整数
        int result = Integer.parseInt(swappedNumber.toString());

        System.out.println("原始数字: " + number);
        System.out.println("交换相邻数字后的数字: " + result);
    }
}
```

## 201. 大小写转换

```java
public class CapitalizationChanger {
    public static void capitalization(String input) {
        StringBuilder resultString = new StringBuilder();

        for (char ch : input.toCharArray()) {
            // 如果是大写字母
            if (Character.isUpperCase(ch)) {
                // 转换为小写
                resultString.append(Character.toLowerCase(ch));
            } else {
                // 转换为大写
                resultString.append(Character.toUpperCase(ch));
            }
        }

        System.out.println("原始字符串: " + input);
        System.out.println("转换后的字符串: " + resultString);
    }

    public static void main(String[] args) {
        capitalization("Hello World");
    }
}
```

## 202. 字符串中的数字和

```java
public class SumOfDigits {
    public static void sumOfDigits(String input) {
        int sum = 0;

        // 遍历字符串每个字符
        for (char ch : input.toCharArray()) {
            // 检查是否是数字
            if (Character.isDigit(ch)) {
                // 转换为数值并累加
                sum += Character.getNumericValue(ch);
            }
        }

        System.out.println("原始字符串: " + input);
        System.out.println("数字之和: " + sum);
    }

    public static void main(String[] args) {
        sumOfDigits("abc123xyz456");
    }
}
```

## 203. 立方和

```java
public class SumOfCubes {
    public static void sumOfCubes(int upToInteger) {
        int cubesSum = 0;

        // 计算从 1 到 upToInteger 的立方和
        for (int i = 1; i <= upToInteger; i++) {
            cubesSum += Math.pow(i, 3); // 计算每个整数的立方并累加
        }

        System.out.println("从 1 到" + upToInteger + "的立方和: " + cubesSum);
    }

    public static void main(String[] args) {
        sumOfCubes(5);
    }
}
```

## 204. 连续和的最大整数

```java
public class MaximumIntegerForSum {
    public static void findMaxIntegerForSum(int targetSum) {
        int currentSum = 0;
        int maxInteger = 0;

        // 找到连续和不超过 targetSum 的最大整数
        while (currentSum + maxInteger + 1 <= targetSum) {
            maxInteger++;
            currentSum += maxInteger;
        }

        System.out.println("连续和不超过" + targetSum + " 的最大整数是: " + maxInteger);
    }
}
```

```java
System.out.println("Sum <= " + targetSum + " 的最大整数 (n): " + maxInteger);
}

public static void main(String[] args) {
    findMaxIntegerForSum(15);
}

}

// Sum <= 15 的最大整数 (n): 5
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 206. URL 解

![image](img/chapter_title_below.png)

```java
import java.util.HashMap;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class URLBreakdown {
    public static void breakUrl(String url) {
        // 用于匹配 URL 组件的正则表达式
        String urlRegex = "^(\\w+):\\/\\/(\\w+([\\.\\w-]*)?)(\\/.*)?$";
        Pattern pattern = Pattern.compile(urlRegex);
        Matcher matcher = pattern.matcher(url);

        // 用于存储 URL 部分的 HashMap
        HashMap<String, String> urlParts = new HashMap<>();

        if (matcher.find()) {
            urlParts.put("scheme", matcher.group(1));
            urlParts.put("domain", matcher.group(2));
            urlParts.put("path", matcher.group(4) != null ? matcher.group(4) : "");
        } else {
            System.out.println("无效的 URL 格式.");
            return;
        }

        // 打印 URL 部分
        System.out.println("URL Parts:");

        for (HashMap.Entry<String, String> entry : urlParts.entrySet()) {
            System.out.println(entry.getKey() + ": " + entry.getValue());
        }
    }

    public static void main(String[] args) {
        breakUrl("https://www.example.org/page");
    }
}

// URL Parts:

// scheme: https

// domain: www.example.org

// path: /page
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 207. 按长度排序字符串

![image](img/chapter_title_below.png)

```java
import java.util.Arrays;

public class SortStringsByLength {
    public static void sortStringsByLength(String[] stringsArray) {
        // 复制原始数组以保持其状态
        String[] sortedArray = Arrays.copyOf(stringsArray, stringsArray.length);

        // 按长度排序数组
        Arrays.sort(sortedArray, (s1, s2) -> Integer.compare(s1.length(), s2.length()));

        // 打印原始数组和排序后的数组
        System.out.println("Original Array of Strings:");
        System.out.println(Arrays.toString(stringsArray));

        System.out.println("Array of Strings Sorted by Length:");
        System.out.println(Arrays.toString(sortedArray));
    }

    public static void main(String[] args) {
        sortStringsByLength(new String[]{"apple", "banana", "orange", "kiwi", "grape"});
    }
}

// Original Array of Strings:

// [apple, banana, orange, kiwi, grape]

// Array of Strings Sorted by Length:

// [kiwi, apple, grape, banana, orange]
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 208. 简化绝对路径

![image](img/chapter_title_below.png)

```java
import java.util.ArrayList;
import java.util.List;

public class SimplifyAbsolutePath {
    public static void simplifyAbsolutePath(String path) {
        String[] parts = path.split("/");
        List<String> simplifiedParts = new ArrayList<>();

        for (String part : parts) {
            switch (part) {
                case "..":
                    if (!simplifiedParts.isEmpty()) {
                        simplifiedParts.remove(simplifiedParts.size() - 1); // 对于 '..' 向上移动
                    }
                    break;

                case "":
                case ".":
                    // 忽略空部分和当前目录 '.'
                    break;

                default:
                    simplifiedParts.add(part);
                    break;
            }
        }

        String simplifiedPath = "/" + String.join("/", simplifiedParts);

        System.out.println("Original Absolute Path: " + path);
        System.out.println("Simplified Absolute Path: " + simplifiedPath);
    }

    public static void main(String[] args) {
        simplifyAbsolutePath("/home/user/../documents/./file.txt");
    }
}
```



// Original Absolute Path: `/home/user/../documents/./file.txt`

// Simplified Absolute Path: `/home/documents/file.txt`

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 209. 计算交集元素

```java
import java.util.Arrays;
import java.util.HashSet;
import java.util.Set;

public class CountCommon {

    public static void countCommon(int[] arr1, int[] arr2) {
        Set<Integer> set1 = new HashSet<>();
        Set<Integer> set2 = new HashSet<>();

        // 将第一个数组添加到集合 1
        for (int num : arr1) {
            set1.add(num);
        }

        // 将第二个数组添加到集合 2
        for (int num : arr2) {
            set2.add(num);
        }

        // 使用 retainAll 获取交集
        set1.retainAll(set2);

        // 打印交集的大小
        System.out.println("Common elements count: " + set1.size());
    }

    public static void main(String[] args) {
        countCommon(new int[]{1, 2, 3, 4, 5}, new int[]{3, 4, 5, 6, 7});
    }
}

// Common elements count: 3
```

## 210. 检查数字是否是否相同

```java
public class CheckSameDigits {

    public static void areSameDigits(int number) {
        String numberStr = Integer.toString(number);
        char firstDigit = numberStr.charAt(0);

        // 检查所有数字是否相同
        for (int i = 1; i < numberStr.length(); i++) {
            if (numberStr.charAt(i) != firstDigit) {
                System.out.println("Digits in " + number + " are not all same.");
                return;
            }
        }

        System.out.println("Digits in " + number + " are all same.");
    }

    public static void main(String[] args) {
        areSameDigits(22222);
    }
}

// Digits in 22222 are all same.
```

## 211. 右侧零数位置

```java
public class RightmostNumberPosition {

    public static void rightmostNumberPosition(int[] arr) {
        for (int i = arr.length - 1; i >= 0; i--) {
            if (arr[i] % 10 == 0) {
                System.out.println("Rightmost Round Number: " + arr[i] + ", Position: " + (i + 1));
                return;
            }
        }

        System.out.println("No round numbers found in the array. Position: 0");
    }

    public static void main(String[] args) {
        rightmostNumberPosition(new int[]{123, 450, 678, 900});
    }
}

// Rightmost Round Number: 900, Position: 4
```

## 212. 反转 16 位无符号整数的位

```java
public class ReverseBits {

    public static void reverseBits16BitUnsignedShort(int integer) {
        if (integer < 0 || integer > 65535) {
            System.out.println("Please provide a 16-bit unsigned short integer.");
            return;
        }

        // 获取整数的二进制表示
        String binaryRepresentation = String.format("%16s", Integer.toBinaryString(integer)).replace(' ', '0');

        // 反转二进制表示
        String reversedBinary = new StringBuilder(binaryRepresentation).reverse().toString();

        // 将反转后的二进制转换回整数
        int reversedInteger = Integer.parseUnsignedInt(reversedBinary, 2);

        System.out.println("Original Integer: " + integer);
        System.out.println("Binary Representation: " + binaryRepresentation);
        System.out.println("Reversed Binary: " + reversedBinary);
        System.out.println("Reversed Integer: " + reversedInteger);
    }

    public static void main(String[] args) {
        reverseBits16BitUnsignedShort(5678);
    }
}

// 整数: 5678
// 二进制表示: 0001011000101110
// 反转后的二进制: 0111010001101000
// 反转后的整数: 29800
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 213. 大于 15 检查器

![image](img/chapter_title_below.png)

```java
public class GreaterThan15Checker {

    public static void greaterThan15Checker(int number) {
        int result = number > 15 ? number : 15;

        System.out.println("Given Number: " + number);
        System.out.println("Result: " + result);
    }

    public static void main(String[] args) {
        greaterThan15Checker(20);
    }
}

// 给定数字: 20
// 结果: 20
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 214. 将第一个数字替换为 $

![image](img/chapter_title_below.png)

```java
public class ReplaceFirstDigitWithDollar {

    public static void replaceFirstDigitWithDollar(String inputString) {
        boolean foundDigit = false;
        StringBuilder modifiedString = new StringBuilder();

        for (char c : inputString.toCharArray()) {
            if (Character.isDigit(c) && !foundDigit) {
                modifiedString.append('$');
                foundDigit = true; // Mark that we found the first digit
            } else {
                modifiedString.append(c);
            }
        }

        System.out.println("Original String: " + inputString);
        System.out.println("Modified String: " + modifiedString.toString());
    }

    public static void main(String[] args) {
        replaceFirstDigitWithDollar("abc123xyz456");
    }
}

// 原始字符串: abc123xyz456
// 修改后的字符串: abc$23xyz456
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 215. 前缀和

![image](img/chapter_title_below.png)

```java
import java.util.Arrays;

public class PrefixSums {

    public static void prefixSums(int[] inputArray) {
        int prefixSum = 0;
        int[] prefixSumArray = new int[inputArray.length];

        for (int i = 0; i < inputArray.length; i++) {
            prefixSum += inputArray[i];
            prefixSumArray[i] = prefixSum;
        }

        System.out.println("Original Array: " + Arrays.toString(inputArray));
        System.out.println("Prefix Sums Array: " + Arrays.toString(prefixSumArray));
    }

    public static void main(String[] args) {
        prefixSums(new int[]{1, 2, 3, 4, 5});
    }
}

// 原始数组: [1, 2, 3, 4, 5]
// 前缀和数组: [1, 3, 6, 10, 15]
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 216. 下一个质数

![image](img/chapter_title_below.png)

```java
public class NextPrimeNumber {

    // 检查一个数字是否为质数的函数
    public static boolean isPrime(int num) {
        if (num < 2) {
            return false;
        }

        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) {
                return false;
            }
        }

        return true;
    }

    // 寻找下一个质数的函数
    public static int nextPrimeNumber(int givenNumber) {
        int nextNumber = givenNumber + 1;

        while (!isPrime(nextNumber)) {
            nextNumber++;
        }

        return nextNumber;
    }

    public static void main(String[] args) {
        int givenNumber = 10;
        int nextPrime = nextPrimeNumber(givenNumber);

        System.out.println("Given Number: " + givenNumber);
        System.out.println("Next Prime Number: " + nextPrime);
    }
}

// 给定数字: 10
// 下一个质数: 11
```

| ![image](img/chapter_title_corner_decoration_left.png) | | ![image](img/chapter_title_corner_decoration_right.png) |

![image](img/chapter_title_above.png)

## 217. 位顺序反转

![image](img/chapter_title_below.png)

```java
public class ReverseOrderOfBits {

    // 反转一个字节的位
    public static void reverseOfBits(int integer) {
        String binaryRepresentation = String.format("%8s", Integer.toBinaryString(integer)).replace(' ', '0');
        String reversedBinary = new StringBuilder(binaryRepresentation).reverse().toString();
        int reversedInteger = Integer.parseInt(reversedBinary, 2);

        System.out.println("Given Number: " + integer);
        System.out.println("Binary Representation: " + binaryRepresentation);
```



```java
        System.out.println("Reversed Binary: " + reversedBinary);

        System.out.println("Reversed Integer: " + reversedInteger);

    }

    public static void main(String[] args) {

        reverseOfBits(14);

        reverseOfBits(56);

        reverseOfBits(234);

    }

}
```

```
// 给定数字: 14
// 二进制表示: 00001110
// 反转后的二进制: 01110000
// 反转后的整数: 112

// 给定数字: 56
// 二进制表示: 00111000
// 反转后的二进制: 00011100
// 反转后的整数: 28

// 给定数字: 234
// 二进制表示: 11101010
// 反转后的二进制: 01010111
// 反转后的整数: 87
```

## 218. 金字塔模式

![image](img/chapter_title_below.png)

```java
public class PyramidPattern {

    // 生成 ASCII 三角形（金字塔）的函数

    public static void generateAsciiTriangle(int height) {

        for (int i = 1; i <= height; i++) {

            String spaces = " ".repeat(height - i);

            String stars = "*".repeat(i * 2 - 1);

            System.out.println(spaces + stars);

        }

    }

    public static void main(String[] args) {

        int triangleHeight = 5;

        generateAsciiTriangle(triangleHeight);

    }

}
```

```
//    *
//   ***
//  *****
// *******
// **********
```
