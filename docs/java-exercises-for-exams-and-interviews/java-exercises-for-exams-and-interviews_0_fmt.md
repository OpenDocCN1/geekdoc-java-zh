
# Java 考试与面试练习指南

## 任务

编写一个 Java 程序，接收一个英寸值并将其转换为米。

### 英寸转换为米

- 1 英寸 = 0.025400 米
- 2 英寸 = 0.050800 米
- 3 英寸 = 0.076200 米
- 4 英寸 = 0.101600 米
- 5 英寸 = 0.127000 米
- 6 英寸 = 0.152400 米

### Java 代码

```java
import java.util.Scanner;

public class Exercise2 {
    public static void main(String[] Strings) {
        Scanner input = new Scanner(System.in);
        System.out.print("Input a value for inch: ");
        double inch = input.nextDouble();
        double meters = inch * 0.0254;
        System.out.println(inch + " inch is " + meters + " meters");
    }
}
```

### 输出

```
Input a value for inch: 1000
1000.0 inch is 25.4 meters
```

---

## 相加整数中的所有数字位

创建一个 Java 程序，接收一个 0 到 1000 之间的整数并相加所有的数字位。

### Java 代码

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] Strings) {
        Scanner input = new Scanner(System.in);
        System.out.print("Input an integer between 0 and 1000: ");
        int num = input.nextInt();
        int firstDigit = num % 10;
        int remainingNumber = num / 10;
        int SecondDigit = remainingNumber % 10;
        remainingNumber = remainingNumber / 10;
        int thirdDigit = remainingNumber % 10;
        remainingNumber = remainingNumber / 10;
        int fourthDigit = remainingNumber % 10;
        int sum = thirdDigit + SecondDigit + firstDigit + fourthDigit;
        System.out.println("The sum of all digits in " + num + " is " + sum);
    }
}
```

### 输出

```
Input an integer between 0 and 1000: 565
The sum of all digits in 565 is 16
```

---

## 让用户输入分钟数并打印分钟数对应的年和数

编写一个 Java 程序将分钟数转换为年和数。

### Java 代码

```java
import java.util.Scanner;

public class Exercise4 {
    public static void main(String[] Strings) {
        double minutesInYear = 60 * 24 * 365;
        Scanner input = new Scanner(System.in);
        System.out.print("Input the number of minutes: ");
        double min = input.nextDouble();
        long years = (long) (min / minutesInYear);
        int days = (int) (min / 60) % 365;
        System.out.println((int) min + " is approximately " + years + " years and " + days + " days");
    }
}
```

### 输出

```
Input the number of minutes: 345689
345689 minutes is approximately 6 years and 210 days
```

---

## 读取一个数字并显示平方、立方和四次方

创建一个 Java 程序，读取一个数字并显示该数字的平方、立方和四次方。

### Java 代码

```java
import java.util.Scanner;

public class Exercise8 {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("Input the side length: ");
        double val = in.nextDouble();
        System.out.printf("Square: %.2f\n", val * val);
        System.out.printf("Cube: %.2f\n", val * val * val);
        System.out.printf("Fourth power: %.2f\n", Math.pow(val, 4));
    }
}
```

### 输出

```
Input the side length: 15
Square: 225.00
Cube: 3375.00
Fourth power: 50625.00
```

---

## 条件语句：检查数字是否为负数、零或正数

### Java 代码

```java
import java.util.Scanner;

public class Exercise27 {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("Input a number: ");
        int n = in.nextInt();
        if (n > 0) {
            System.out.println("Number is positive");
        } else if (n < 0) {
            System.out.println("Number is negative");
        } else {
            System.out.println("Number is zero");
        }
    }
}
```

### 输出

```
Input a number: 7
Number is positive
```

---

## 输入 5 个数字并找到它们的和和平均值

### Java 代码

```java
import java.util.Scanner;

public class Exercise12 {
    public static void main(String[] args) {
        int i, n = 0, s = 0;
        double avg;
        System.out.println("Input the 5 numbers : ");
        for (i = 0; i < 5; i++) {
            Scanner in = new Scanner(System.in);
            n = in.nextInt();
            s += n;
        }
        avg = s / 5;
        System.out.println("The sum of 5 no is : " + s + "\nThe Average is : " + avg);
    }
}
```

### 输出

```
Input the 5 numbers : 
1
2
3
4
5
The sum of 5 no is : 15
The Average is : 3.0
```

---

## 显示 n 项自然数和它们的和

输入数字：7

### Java 代码

```java
import java.util.Scanner;

public class Exercise1 {
    public static void main(String[] args) {
        int i, n, sum = 0;
        Scanner in = new Scanner(System.in);
        System.out.print("Input number: ");
        n = in.nextInt();
        System.out.println("The first n numbers are : ");
        for (i = 1; i <= n; i++) {
            System.out.println(i);
            sum += i;
        }
        System.out.println("The Sum of Natural upto " + n + " terms : " + sum);
    }
}
```

### 输出

```
Input number: 7
The first n numbers are : 
1
2
3
4
5
6
7
The Sum of Natural upto 7 terms : 28
```

---

## 显示 1 到 7 之间的星期

### Java 代码

```java
import java.util.Scanner;

public class Exercise5 {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("Input number: ");
        int day = in.nextInt();
        System.out.println(getDayName(day));
    }

    // 获取周几的名称
    public static String getDayName(int day) {
        String dayName = "";
        switch (day) {
            case 1: dayName = "Monday"; break;
            case 2: dayName = "Tuesday"; break;
            case 3: dayName = "Wednesday"; break;
            case 4: dayName = "Thursday"; break;
            case 5: dayName = "Friday"; break;
            case 6: dayName = "Saturday"; break;
            case 7: dayName = "Sunday"; break;
            default: dayName = "Invalid day range";
        }
        return dayName;
    }
}
```

输入数字：3

周三

---

## 使用 while 循环打印从 1 到 N 的数字

### 程序

```java
import java.util.Scanner;

public class Print_1_To_N_UsingWhile {
    public static void main(String[] args) {
        // 计数器初始化
        int i = 1;
        // 创建 scanner 类对象
        Scanner Sc = new Scanner(System.in);
        // 输入 " n" 的值
        System.out.print("Enter the value n : ");
        // 读取值
        int n = Sc.nextInt();
        System.out.println("Numbers are : ");
        while (i <= n) {
            System.out.println(i);
            i++;
        }
    }
}
```

### 输出

```
Enter the value n : 15
Numbers are :
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
```

---

# Java 程序中一维数组和二维数组的加法

共有 2 个程序：两个一维数组的相加，两个二维数组的相加

## 1) Java 中两个一维数组的加法

```java
class AddTwoArrayClass {
    public static void main(String[] args) {
        // 数组的声明和初始化
        int a[] = {1, 2, 3, 4, 5};
        int b[] = {6, 7, 8, 9, 10};
        // 实例化第三数组以存储结果
        int c[] = new int[5];
        for (int i = 0; i < 5; ++i) {
            // 两个数组相加并将结果存储在第三个数组中
            c[i] = a[i] + b[i];
            // 显示结果
            System.out.println("Enter sum of " + i + "index" + " " + c[i]);
        }
    }
}
```

### 输出

```
Enter sum of 0index 7
Enter sum of 1index 9
Enter sum of 2index 11
Enter sum of 3index 13
Enter sum of 4index 15
```

## 2) Java 中两个二维数组的加法

```java
class AddTwoArrayOf2DClass {
    public static void main(String[] args) {
        // 声明和初始化二维数组
        int a[][] = {{1, 2, 3}, {4, 5, 6}};
        int b[][] = {{7, 8, 9}, {10, 11, 12}};
        // 实例化第三数组以存储结果
        int c[][] = new int[2][3];
        for (int i = 0; i < 2; ++i) {
            for (int j = 0; j < 3; ++j) {
                // 两个数组相加并将结果存储在第三个数组中
                c[i][j] = a[i][j] + b[i][j];
                System.out.println("Enter sum of " + i + " " + j + "index" + " " + c[i][j]);
            }
        }
    }
}
```

### 输出

```
Enter sum of 0 0index 8
Enter sum of 0 1index 10
Enter sum of 0 2index 12
Enter sum of 1 0index 14
Enter sum of 1 1index 16
Enter sum of 1 2index 18
```

---

# 将十进制转换为二进制的 Java 程序

给定一个整数（十进制），我们需要使用 Java 程序将其转换为二进制。

### 程序



```java
// Scanner 类用于从用户获取输入
import java.util.Scanner;

class DecimalToBinaryConversionClass {
    public static void main(String[] args) {
        // 创建 Scanner 类对象
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter Any Decimal Number :");
        // 接受用户输入
        int input_decimal_num = sc.nextInt();
        String binary_string = " ";
        // 循环持续到 input_decimal_num > 0
        while (input_decimal_num > 0) {
            // 将余数添加到字符串变量中
            binary_string = input_decimal_num % 2 + binary_string;
            input_decimal_num = input_decimal_num / 2;
        }
        // 显示最终结果
        System.out.println("Conversion of decimal to binary is : " + binary_string);
    }
}
```

### 输出

```
Enter Any Decimal Number :
30
Conversion of decimal to binary is : 11110
```

# 逐行读取文件的 Java 程序

给定一个文件，我们需要使用 Java 程序逐行读取其内容。

我们在此程序中使用一个名为 `B.txt` 的文件，它位于 `F:\` 盘，因此文件路径为 `F:\B.txt`，文件内容为：

```
This is line 1
This is line 2
This is line 3
This is line 4
```

### 程序

```java
import java.io.FileInputStream;
import java.io.IOException;
import java.util.Scanner;

public class ReadLineByLine {
    public static void main(String[] args) {
        // 创建 scanner 类对象
        Scanner Sc = new Scanner(System.in);
        // 输入文件名
        System.out.print("Enter the file name:");
        String sfilename = Sc.next();
        Scanner Sc1 = null;
        FileInputStream fis = null;
        try {
            FileInputStream FI = new FileInputStream(sfilename);
            Sc1 = new Scanner(FI);
            // 这将读取到数据结束
            while (Sc1.hasNext()) {
                String data = Sc1.nextLine();
                // 打印数据
                System.out.print("The file data is : " + data);
            }
        } catch (IOException e) {
            System.out.println(e);
        }
    }
}
```

### 输出

```
Enter the file name: F:/B.txt
This is line 1
This is line 2
This is line 3
This is line 4
```
