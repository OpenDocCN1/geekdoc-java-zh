
# 100 个 Java 程序示例｜初学者最佳教程｜Java 编程书籍

![](img/7d75bf5896cc08de79dfc9d70d016088_0_0.png)

作者 - DEVBRAT RUDRA

## 第一组 SET-1

### 1. Hello World

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

### 2. 数相加

```java
public class AddTwoNumbers {
    public static void main(String[] args) {
        int num1 = 5, num2 = 15, sum;
        sum = num1 + num2;
        System.out.println("Sum of these numbers: " + sum);
    }
}
```

### 3. 数字的阶乘

```java
public class Factorial {
    public static void main(String[] args) {
        int num = 5;
        long factorial = 1;
        for (int i = 1; i <= num; ++i) {
            factorial *= i;
        }
        System.out.println("Factorial of " + num + " = " + factorial);
    }
}
```

### 4. 斐波那契数列

```java
public class Fibonacci {
    public static void main(String[] args) {
        int n = 10, t1 = 0, t2 = 1;
        System.out.print("Fibonacci Series: ");
        for (int i = 1; i <= n; ++i) {
            System.out.print(t1 + " ");
            int sum = t1 + t2;
            t1 = t2;
            t2 = sum;
        }
    }
}
```

### 5. 字符串反转

```java
public class ReverseString {
    public static void main(String[] args) {
        String str = "Hello World";
        String reversed = new StringBuilder(str).reverse().toString();
        System.out.println("Reversed string: " + reversed);
    }
}
```

### 6. 检查奇偶数

```java
public class EvenOrOdd {
    public static void main(String[] args) {
        int num = 5;
        if (num % 2 == 0) {
            System.out.println("The number is even.");
        } else {
            System.out.println("The number is odd.");
        }
    }
}
```

### 7. 检查质数

```java
public class PrimeNumber {
    public static void main(String[] args) {
        int num = 29;
        boolean flag = false;
        for (int i = 2; i <= num / 2; ++i) {
            if (num % i == 0) {
                flag = true;
                break;
            }
        }
        if (!flag) {
            System.out.println(num + " is a prime number.");
        } else {
            System.out.println(num + " is not a prime number.");
        }
    }
}
```

### 8. 自然数求和

```java
public class SumOfNaturalNumbers {
    public static void main(String[] args) {
        int num = 10, sum = 0;
        for (int i = 1; i <= num; ++i) {
            sum += i;
        }
        System.out.println("Sum = " + sum);
    }
}
```

### 9. 生成乘法表

```java
public class MultiplicationTable {
    public static void main(String[] args) {
        int num = 5;
        for (int i = 1; i <= 10; ++i) {
            System.out.printf("%d * %d = %d\n", num, i, num);
        }
    }
}
```

### 10. 找出三个数中的最大值

```java
public class LargestAmongThree {
    public static void main(String[] args) {
        double n1 = 5, n2 = 7, n3 = 3;
        if (n1 >= n2 && n1 >= n3) {
            System.out.println(n1 + " is the largest number.");
        } else if (n2 >= n1 && n2 >= n3) {
            System.out.println(n2 + " is the largest number.");
        } else {
            System.out.println(n3 + " is the largest number.");
        }
    }
}
```

## 第二组 SET-2

### 1. 寻找数组中的最大元素

```java
public class MaxElement {
    public static void main(String[] args) {
        int[] arr = { 1, 4, 7, 2, 9, 3 };
        int max = arr[0];
        for (int i = 1; i < arr.length; i++) {
            if (arr[i] > max) {
                max = arr[i];
            }
        }
        System.out.println("Maximum element in the array: " + max);
    }
}
```

### 2. 计算数组平均值

```java
public class AverageArray {
    public static void main(String[] args) {
        double[] numbers = { 2.5, 3.4, 1.9, 3.2 };
        double sum = 0;
        for (double num : numbers) {
            sum += num;
        }
        double average = sum / numbers.length;
        System.out.println("Average of the array: " + average);
    }
}
```

### 3. 检查字符串是否为回文

```java
public class PalindromeCheck {
    public static void main(String[] args) {
        String original = "madam";
        String reverse = "";
        for (int i = original.length() - 1; i >= 0; i--) {
            reverse += original.charAt(i);
        }
        if (original.equals(reverse)) {
            System.out.println("The string is a palindrome.");
        } else {
            System.out.println("The string is not a palindrome.");
        }
    }
}
```

### 4. 使用递归计算阶乘

```java
public class FactorialRecursive {
    public static void main(String[] args) {
        int num = 5;
        long factorial = multiplyNumbers(num);
        System.out.println("Factorial of " + num + " = " + factorial);
    }

    public static long multiplyNumbers(int num) {
        if (num >= 1) {
            return num * multiplyNumbers(num - 1);
        } else {
            return 1;
        }
    }
}
```

### 5. 显示字符串的字符

```java
public class DisplayCharacters {
    public static void main(String[] args) {
        String str = "Hello";
        for (int i = 0; i < str.length(); i++) {
            System.out.print(str.charAt(i) + " ");
        }
    }
}
```

### 6. 交换两个数

```java
public class SwapNumbers {
    public static void main(String[] args) {
        float first = 20f, second = 45f;
        System.out.println("--Before swap--");
        System.out.println("First number: " + first);
        System.out.println("Second number: " + second);

        // 交换值
        float temporary = first;
        first = second;
        second = temporary;

        System.out.println("--After swap--");
        System.out.println("First number: " + first);
        System.out.println("Second number: " + second);
    }
}
```

### 7. 计算数字的幂

```java
public class PowerOfNumber {
    public static void main(String[] args) {
        int base = 3, exponent = 4;
        long result = 1;
        while (exponent != 0) {
            result *= base;
            --exponent;
        }
        System.out.println("Answer = " + result);
    }
}
```

### 8. 打印字符的 ASCII 值

```java
public class ASCIIValue {
    public static void main(String[] args) {
        char ch = 'a';
        int ascii = ch;
        System.out.println("The ASCII value of " + ch + " is: " + ascii);
    }
}
```

### 9. 显示两个区间间的质数

```java
public class PrimeIntervals {
    public static void main(String[] args) {
        int low = 20, high = 50;
        while (low < high) {
            boolean flag = false;
            for (int i = 2; i <= low / 2; ++i) {
                if (low % i == 0) {
                    flag = true;
                    break;
                }
            }
            if (!flag) {
                System.out.print(low + " ");
            }
            ++low;
        }
    }
}
```

### 10. 找出两个数的最大公约数（GCD）

```java
public class GCD {
    public static void main(String[] args) {
        int n1 = 81, n2 = 153;
        while (n1 != n2) {
            if (n1 > n2)
                n1 -= n2;
            else
                n2 -= n1;
        }
        System.out.println("G.C.D = " + n1);
    }
}
```

## 第三组 SET-3

### 1. 检查闰年

```java
public class LeapYear {
    public static void main(String[] args) {
        int year = 2024;
        boolean leap = false;
        if (year % 4 == 0) {
            if (year % 100 == 0) {
                if (year % 400 == 0)
                    leap = true;
                else
                    leap = false;
            } else
                leap = true;
        } else
            leap = false;
        if (leap)
            System.out.println(year + " is a leap year.");
        else
            System.out.println(year + " is not a leap year.");
    }
}
```

```java
System.out.println("Reversed Array: " + Arrays.toString(array));
    }
}
```

### 3. 计算字符串中的单词数



```java
public class CountWords {
    public static void main(String[] args) {
        String str = "This is a sample sentence.";
        int count = 1;
        for (int i = 0; i < str.length(); i++) {
            if (str.charAt(i) == ' ' && str.charAt(i + 1) != ' ') {
                count++;
            }
        }
        System.out.println("Number of words in the string: " + count);
    }
}
```

### 4. 计算单利

```java
public class SimpleInterest {
    public static void main(String[] args) {
        double principle = 2000;
        double rate = 3;
        double time = 1.5;
        double simpleInterest = (principle * time * rate) / 100;
        System.out.println("Simple Interest is: " + simpleInterest);
    }
}
```

### 5. 检查数字是否为完全数

```java
public class PerfectNumber {
    public static void main(String[] args) {
        int num = 28;
        int sum = 0;
        for (int i = 1; i < num; i++) {
            if (num % i == 0) {
                sum += i;
            }
        }
        if (sum == num) {
            System.out.println(num + " is a perfect number.");
        } else {
            System.out.println(num + " is not a perfect number.");
        }
    }
}
```

### 6. 检查阿姆斯特朗数

```java
public class ArmstrongNumber {
    public static void main(String[] args) {
        int number = 371, originalNumber, remainder, result;
        originalNumber = number;
        result = 0; // 为逻辑添加了缺失的初始化
        while (originalNumber != 0) {
            remainder = originalNumber % 10;
            result += Math.pow(remainder, 3);
            originalNumber /= 10;
        }
        if (result == number)
            System.out.println(number + " is an Armstrong number.");
        else
            System.out.println(number + " is not an Armstrong number.");
    }
}
```

### 7. 排序数组中的元素

```java
import java.util.Arrays;

public class ArraySort {
    public static void main(String[] args) {
        int[] arr = {13, 7, 6, 45, 21, 9, 101, 102};
        Arrays.sort(arr);
        System.out.println("Sorted Array: " + Arrays.toString(arr));
    }
}
```

## 8. 两个数的最小公倍数（LCM）

```java
public class LCM {
    public static void main(String[] args) {
        int n1 = 72, n2 = 120, lcm;
        lcm = (n1 > n2) ? n1 : n2;
        while (true) {
            if (lcm % n1 == 0 && lcm % n2 == 0) {
                System.out.printf("The LCM of %d and %d is %d.\n", n1, n2, lcm);
                break;
            }
            ++lcm;
        }
    }
}
```

### 9. 删除字符串中的空白

```java
public class RemoveWhiteSpaces {
    public static void main(String[] args) {
        String str = " Hello World ";
        str = str.replaceAll("\s", "");
        System.out.println("String after removing white spaces: " + str);
    }
}
```

### 10. 查找字符串中字符的频率

```java
import java.util.HashMap;

public class CharacterFrequency {
    public static void main(String[] args) {
        String str = "hello world";
        HashMap<Character, Integer> map = new HashMap<>();
        for (char c : str.toCharArray()) {
            if (map.containsKey(c)) {
                map.put(c, map.get(c) + 1);
            } else {
                map.put(c, 1);
            }
        }
        System.out.println("Character frequency in the string: " + map);
    }
}
```

## SET-4

### 1. 计算圆的面积

```java
public class AreaOfCircle {
    public static void main(String[] args) {
        double radius = 3;
        double area = Math.PI * radius * radius;
        System.out.println("Area of the circle is: " + area);
    }
}
```

### 2. 创建并使用类

```java
class Rectangle {
    int length;
    int width;

    public int calculateArea() {
        return length * width;
    }
}

public class UseRectangle {
    public static void main(String[] args) {
        Rectangle rect = new Rectangle();
        rect.length = 5;
        rect.width = 3;
        int area = rect.calculateArea();
        System.out.println("Area of the rectangle is: " + area);
    }
}
```

### 3. 实现继承

```java
class Vehicle {
    void display() {
        System.out.println("This is a vehicle.");
    }
}

class Car extends Vehicle {
    void displayCar() {
        System.out.println("This is a car.");
    }
}

public class InheritanceExample {
    public static void main(String[] args) {
        Car car = new Car();
        car.display();
        car.displayCar();
    }
}
```

### 4. 使用 `Math.pow()` 计算数字幂

```java
public class PowerExample {
    public static void main(String[] args) {
        double base = 2, exponent = 3;
        double result = Math.pow(base, exponent);
        System.out.println("Result: " + result);
    }
}
```

### 5. 使用方法计算单利

```java
public class Calculator {
    public static void main(String[] args) {
        double principle = 2000;
        double rate = 3;
        double time = 1.5;
        double simpleInterest = (principle * time * rate) / 100;
        System.out.println("Simple Interest is: " + simpleInterest);
    }
}
```

### 6. Java 中的构造函数

```java
class Student {
    String name;
    int age;

    Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    void display() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
}

public class ConstructorExample {
    public static void main(String[] args) {
        Student student = new Student("John", 20);
        student.display();
    }
}
```

### 7. Java 中的接口

```java
interface Shape {
    void draw();
}

class Circle implements Shape {
    public void draw() {
        System.out.println("Drawing Circle");
    }
}

public class InterfaceExample {
    public static void main(String[] args) {
        Circle circle = new Circle();
        circle.draw();
    }
}
```

### 8. Java 中的封装

```java
class Encapsulate {
    private String name;
    private int age;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}

public class EncapsulationExample {
    public static void main(String[] args) {
        Encapsulate obj = new Encapsulate();
        obj.setName("John");
        obj.setAge(20);
        System.out.println("Name: " + obj.getName());
        System.out.println("Age: " + obj.getAge());
    }
}
```

### 9. Java 中的 `static` 关键字

```java
class Counter {
    static int count = 0;

    Counter() {
        count++;
        System.out.println(count);
    }
}

public class StaticExample {
    public static void main(String[] args) {
        Counter c1 = new Counter();
        Counter c2 = new Counter();
        Counter c3 = new Counter();
    }
}
```

### 10. Java 中的异常处理

```java
public class ExceptionExample {
    public static void main(String[] args) {
        try {
            int[] arr = { 1, 2, 3, 4, 5 };
            System.out.println(arr[7]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array index is out of bounds.");
        }
    }
}
```

## SET-5

### 1. 读取和写入文件

```java
import java.io.File;
import java.io.FileWriter;
import java.io.FileReader;
import java.io.IOException;

public class FileReadWrite {
    public static void main(String[] args) {
        // 文件 I/O 的实现
    }
}
```

```java
try {
  File file = new File("test.txt");
  FileWriter writer = new FileWriter(file);
  writer.write("Hello, this is a test.");
  writer.close();

  FileReader reader = new FileReader(file);
  int character;
  while ((character = reader.read()) != -1) {
    System.out.print((char) character);
  }
  reader.close();
} catch (IOException e) {
  System.out.println("An error occurred.");
  e.printStackTrace();
}
```

## 2. 选择排序算法



```java
public class SelectionSort {
  public static void main(String[] args) {
    int[] arr = { 64, 25, 12, 22, 11 };
    for (int i = 0; i < arr.length - 1; i++) {
      int min_idx = i;
      for (int j = i + 1; j < arr.length; j++) {
        if (arr[j] < arr[min_idx]) {
          min_idx = j;
        }
      }
      int temp = arr[min_idx];
      arr[min_idx] = arr[i];
      arr[i] = temp;
    }
    System.out.println("Sorted array: ");
    for (int value : arr) {
        System.out.print(value + " ");
    }
  }
}
```

## 3. 归并排序算法

```java
public class MergeSort {
    void merge(int[] arr, int l, int m, int r) {
        int n1 = m - l + 1;
        int n2 = r - m;
        int[] L = new int[n1];
        int[] R = new int[n2];
        for (int i = 0; i < n1; ++i) {
            L[i] = arr[l + i];
        }
        for (int j = 0; j < n2; ++j) {
            R[j] = arr[m + 1 + j];
        }
        int i = 0, j = 0;
        int k = l;
        while (i < n1 && j < n2) {
            if (L[i] <= R[j]) {
                arr[k] = L[i];
                i++;
            } else {
                arr[k] = R[j];
                j++;
            }
            k++;
        }
        while (i < n1) {
          arr[k] = L[i];
          i++;
          k++;
        }
        while (j < n2) {
          arr[k] = R[j];
          j++;
          k++;
        }
    }
    void sort(int[] arr, int l, int r) {
      if (l < r) {
        int m = (l + r) / 2;
        sort(arr, l, m);
        sort(arr, m + 1, r);
        merge(arr, l, m, r);
      }
    }
    public static void main(String[] args) {
      int[] arr = { 12, 11, 13, 5, 6, 7 };
      MergeSort ob = new MergeSort();
      ob.sort(arr, 0, arr.length - 1);
      System.out.println("Sorted array:");
      for (int value : arr) {
        System.out.print(value + " ");
      }
    }
}
```

## 4. 冒泡排序算法

```java
public class BubbleSort {
  public static void main(String[] args) {
    int[] arr = { 64, 34, 25, 12, 22, 11, 90 };
    int n = arr.length;
    for (int i = 0; i < n - 1; i++) {
      for (int j = 0; j < n - i - 1; j++) {
        if (arr[j] > arr[j + 1]) {
          int temp = arr[j];
          arr[j] = arr[j + 1];
          arr[j + 1] = temp;
        }
      }
    }
    System.out.println("Sorted array: ");
    for (int value : arr) {
      System.out.print(value + " ");
    }
  }
}
```

## 5. 线性查找算法

```java
public class LinearSearch {
    public static void main(String[] args) {
    int[] arr = { 2, 3, 4, 10, 40 };
    int target = 10;
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] == target) {
            System.out.println("Element found at index " + i);
            break;
        }
    }
    }
}
```

## 6. 二分查找算法

```java
public class BinarySearch {
    int binarySearch(int[] arr, int target) {
        int left = 0, right = arr.length - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (arr[mid] == target) {
                return mid;
            } else if (arr[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return -1;
    }
    public static void main(String[] args) {
        int[] arr = { 2, 3, 4, 10, 40 };
        int target = 10;
        BinarySearch bs = new BinarySearch();
        int result = bs.binarySearch(arr, target);
        if (result == -1) {
            System.out.println("Element not found");
        } else {
            System.out.println("Element found at index " + result);
        }
    }
}
```

## 7. `StringBuilder` 类的使用

```java
public class StringBuilderExample {
    public static void main(String[] args) {
        StringBuilder sb = new StringBuilder("Hello");
        sb.insert(5, " Java");
        sb.delete(5, 10);
        System.out.println("StringBuilder: " + sb);
    }
}
```

## 8. 生成随机数

```java
import java.util.Random;
public class RandomNumber {
    public static void main(String[] args) {
        Random rand = new Random();
        int rand1 = rand.nextInt(1000);
        System.out.println("Random Integers: " + rand1);
    }
}
```

## 9. Java 中枚举的使用

```java
enum Day {
    SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY
}
public class EnumExample {
    public static void main(String[] args) {
        Day day = Day.MONDAY;
        if (day == Day.MONDAY) {
            System.out.println("Yes, it's Monday.");
        } else {
            System.out.println("Not Monday.");
        }
    }
}
```

## 10. Java 中 `Math` 类的使用

```java
public class MathExample {
    public static void main(String[] args) {
    int x = 5;
    int y = 7;
    System.out.println("Maximum of x and y: " + Math.max(x, y));
    System.out.println("Square root of y: " + Math.sqrt(y));
    System.out.println("Power of x and y: " + Math.pow(x, y));
    System.out.println("Logarithm of x: " + Math.log(x));
    }
}
```

### 1. 递归斐波那契数列

```java
public class FibonacciRecursive {
    public static void main(String[] args) {
    int n = 10;
    System.out.print("Fibonacci Series: ");
    for (int i = 0; i < n; i++) {
        System.out.print(fibonacci(i) + " ");
        }
    }
    public static int fibonacci(int n) {
        if (n <= 1) {
            return n;
        }
        return fibonacci(n - 1) + fibonacci(n - 2);
    }
}
```

### 2. `ArrayList` 示例

```java
import java.util.ArrayList;

public class ArrayListExample {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("Java");
        list.add("Python");
        list.add("C++");
        list.add("JavaScript");
        System.out.println("Elements in the ArrayList: " + list);
    }
}
```

### 3. `HashSet` 示例

```java
import java.util.HashSet;

public class HashSetExample {
    public static void main(String[] args) {
        HashSet<String> set = new HashSet<>();
        set.add("Apple");
        set.add("Banana");
        set.add("Orange");
        set.add("Apple"); // Duplicate element
        System.out.println("Elements in the HashSet: " + set);
    }
}
```

### 4. `HashMap` 示例

```java
import java.util.HashMap;

public class HashMapExample {
    public static void main(String[] args) {
        HashMap<Integer, String> map = new HashMap<>();
        map.put(1, "John");
        map.put(2, "Doe");
        map.put(3, "Smith");
        System.out.println("Elements in the HashMap: " + map);
    }
}
```

### 5. `try-catch-finally` 块的使用

```java
public class ExceptionHandling {
    public static void main(String[] args) {
        try {
            int[] arr = new int[5];
            System.out.println(arr[6]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array index is out of bounds.");
        } finally {
            System.out.println("Finally block is always executed.");
        }
    }
}
```

### 6. 实现 `Runnable` 接口

```java
public class RunnableExample {
    public static void main(String[] args) {
        Runnable r = () -> {
            for (int i = 0; i < 5; i++) {
                System.out.println("Child Thread");
            }
        };
        Thread t = new Thread(r);
        t.start();
        for (int i = 0; i < 5; i++) {
            System.out.println("Main Thread");
        }
    }
}
```

### 7. Java 中日期和时间的使用

```java
import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

public class DateTimeExample {
    public static void main(String[] args) {
        LocalDateTime currentDateTime = LocalDateTime.now();
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss");
        String formattedDateTime = currentDateTime.format(formatter);
        System.out.println("Current Date and Time: " + formattedDateTime);
    }
}
```

### 8. 生成随机密码



```java
import java.security.SecureRandom;
import java.util.Base64;

public class RandomPassword {
    public static void main(String[] args) {
        SecureRandom random = new SecureRandom();
        byte[] bytes = new byte[8];
        random.nextBytes(bytes);
        String password = Base64.getEncoder().encodeToString(bytes);
        System.out.println("Generated Password: " + password);
    }
}
```

```java
random.nextBytes(bytes);
String password =
Base64.getEncoder().encodeToString(bytes);
System.out.println("Random Password: " + password);
}
```

### 1. 将字符串转换为整数

```java
public class StringToInteger {
    public static void main(String[] args) {
        String str = "12345";
        int number = Integer.parseInt(str);
        System.out.println("Converted integer: " + number);
    }
}
```

### 2. 生成随机数组

```java
import java.util.Random;

public class RandomArray {
    public static void main(String[] args) {
        int n = 5;
        int[] arr = new int[n];
        Random random = new Random();
        for (int i = 0; i < n; i++) {
            arr[i] = random.nextInt(50);
        }
        System.out.println("Random Array: ");
        for (int value : arr) {
            System.out.print(value + " ");
        }
    }
}
```

### 3. 使用 `Thread` 类的示例

```java
class MyThread extends Thread {
    public void run() {
        for (int i = 0; i < 5; i++) {
            System.out.println("Child Thread");
        }
    }
}

public class ThreadExample {
    public static void main(String[] args) {
        MyThread t = new MyThread();
        t.start();
        for (int i = 0; i < 5; i++) {
            System.out.println("Main Thread");
        }
    }
}
```

### 4. 使用 `Runnable` 接口的示例

```java
class MyRunnable implements Runnable {
    public void run() {
        for (int i = 0; i < 5; i++) {
            System.out.println("Child Thread");
        }
    }
}

public class RunnableThreadExample {
    public static void main(String[] args) {
        Runnable r = new MyRunnable();
        Thread t = new Thread(r);
        t.start();
        for (int i = 0; i < 5; i++) {
            System.out.println("Main Thread");
        }
    }
}
```

### 5. 从文件读取内容

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class ReadFile {
    public static void main(String[] args) {
        try {
            BufferedReader reader = new BufferedReader(new FileReader("test.txt"));
            String line;
            while ((line = reader.readLine()) != null) {
                System.out.println(line);
            }
            reader.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### 6. 向文件写入内容

```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public class WriteFile {
    public static void main(String[] args) {
        try {
            BufferedWriter writer = new BufferedWriter(new FileWriter("output.txt"));
            writer.write("Hello, this is a test.");
            writer.close();
            System.out.println("Write successful.");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### 7. 将内容从一个文件复制到另一个文件

```java
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;

public class CopyFile {
    public static void main(String[] args) {
        try {
            FileReader reader = new FileReader("input.txt");
            FileWriter writer = new FileWriter("output.txt");
            int character;
            while ((character = reader.read()) != -1) {
                writer.write(character);
            }
            reader.close();
            writer.close();
            System.out.println("Copy successful.");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### 8. Java 泛型的使用

```java
import java.util.ArrayList;

public class GenericsExample {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("Java");
        list.add("Python");
        list.add("C++");
        for (String element : list) {
            System.out.println(element);
        }
    }
}
```

### 9. 使用 `Arrays.sort()` 排序数组

```java
import java.util.Arrays;

public class ArraySorting {
    public static void main(String[] args) {
        int[] arr = { 13, 7, 6, 45, 21, 9, 101, 102 };
        Arrays.sort(arr);
        System.out.println("Sorted Array: " + Arrays.toString(arr));
    }
}
```

### 10. 计算数组的平均值

```java
public class ArrayAverage {
    public static void main(String[] args) {
        int[] numbers = { 2, 4, 6, 8, 10 };
        int sum = 0;
        for (int number : numbers) {
            sum += number;
        }
        double average = (double) sum / numbers.length;
        System.out.println("Average: " + average);
    }
}
```

### 11. Java 中的 Lambda 表达式

```java
interface MyInterface {
    void display();
}

public class LambdaExample {
    public static void main(String[] args) {
        MyInterface obj = () -> System.out.println("Hello from Lambda!");
        obj.display();
    }
}
```

### 12. 命令行参数的使用

```java
public class CommandLineArguments {
    public static void main(String[] args) {
        if (args.length > 0) {
            System.out.println("First argument: " + args[0]);
        } else {
            System.out.println("No line arguments provided.");
        }
    }
}
```

## 13. 创建服务器套字

```java
import java.io.IOException;
import java.net.ServerSocket;

public class ServerExample {
    public static void main(String[] args) {
        try {
            ServerSocket serverSocket = new ServerSocket(8080);
            System.out.println("Server is listening on port 8080");
            serverSocket.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## 14. 创建客户端套字

```java
import java.io.IOException;
import java.net.Socket;

public class ClientExample {
    public static void main(String[] args) {
        try {
            Socket socket = new Socket("localhost", 8080);
            System.out.println("Connected to the server.");
            socket.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### 15. Java 中的正则表达式

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegexExample {
    public static void main(String[] args) {
        String content = "The quick brown fox jumps over the lazy dog";
        String patternString = ".*.*";
        Pattern pattern = Pattern.compile(patternString);
        Matcher matcher = pattern.matcher(content);
        if (matcher.matches()) {
            System.out.println("Pattern found in the content.");
        } else {
            System.out.println("Pattern not found in the content.");
        }
    }
}
```

```java
public class StringFormatting {
    public static void main(String[] args) {
        String name = "John";
        int age = 30;
        double salary = 50000.50;
        System.out.printf("Name: %s, Age: %d, Salary: %.2f", name, age, salary);
    }
}
```

## 16. 检查数字是正数还是负数

```java
import java.util.Scanner;

public class PositiveNegativeCheck {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a number: ");
        int number = scanner.nextInt();
        if (number > 0) {
            System.out.println("The number is positive.");
        } else if (number < 0) {
            System.out.println("The number is negative.");
        } else {
            System.out.println("The number is zero.");
        }
        scanner.close();
    }
}
```

## 17. 反转字符串

```java
public class ReverseString {
    public static void main(String[] args) {
        String str = "Hello, World!";
        StringBuilder sb = new StringBuilder(str);
        sb.reverse();
        System.out.println("Reversed string: " + sb);
    }
}
```



# SET-9

## 1. 实现栈（Stack）数据结构

```java
import java.util.Stack;
public class StackExample {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();
        stack.push(1);
        stack.push(2);
        stack.push(3);
        System.out.println("Elements in the stack: " + stack);
        System.out.println("Popped element: " + stack.pop());
        System.out.println("Top element: " + stack.peek());
    }
}
```

## 2. 实现队列（Queue）数据结构

```java
import java.util.LinkedList;
import java.util.Queue;

public class QueueExample {
    public static void main(String[] args) {
        Queue<String> queue = new LinkedList<>();
        queue.add("A");
        queue.add("B");
        queue.add("C");
        System.out.println("Elements in the queue: " + queue);
        System.out.println("Removed element: " + queue.remove());
        System.out.println("Head of the queue: " + queue.peek());
    }
}
```

## 3. 二分查找算法

```java
public class BinarySearchExample {
    public static int binarySearch(int[] arr, int target) {
        int left = 0, right = arr.length - 1;
        while (left <= right) {
            int mid = left + (right - left) / 2;
            if (arr[mid] == target) {
                return mid;
            } if (arr[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
        return -1;
    }

    public static void main(String[] args) {
        int[] arr = { 2, 3, 4, 10, 40 };
        int target = 10;
        int result = binarySearch(arr, target);
        if (result == -1) {
            System.out.println("Element not found");
        } else {
            System.out.println("Element found at index " + result);
        }
    }
}
```

## 4. 深度优先搜索（DFS）算法

```java
import java.util.ArrayList;
import java.util.List;

class Graph {
    private int V;
    private List<List<Integer>> adj;

    Graph(int v) {
        V = v;
        adj = new ArrayList<>();
        for (int i = 0; i < v; ++i) {
            adj.add(new ArrayList<>());
        }
    }

    void addEdge(int v, int w) {
        adj.get(v).add(w);
    }

    void DFSUtil(int v, boolean[] visited) {
        visited[v] = true;
        System.out.print(v + " ");
        for (Integer n : adj.get(v)) {
            if (!visited[n]) {
                DFSUtil(n, visited);
            }
        }
    }

    void DFS(int v) {
        boolean[] visited = new boolean[V];
        DFSUtil(v, visited);
    }

    public static void main(String[] args) {
        Graph g = new Graph(4);
        g.addEdge(0, 1);
        g.addEdge(0, 2);
        g.addEdge(1, 2);
        g.addEdge(2, 0);
        g.addEdge(3, 3);
        System.out.println("Following is Depth First Traversal (starting from vertex 2)");
        g.DFS(2);
    }
}
```

## 5. 广度优先搜索（BFS）算法

```java
import java.util.Iterator;
import java.util.LinkedList;

class GraphBFS {
    private int V;
    private List<List<Integer>> adj;

    GraphBFS(int v) {
        V = v;
        adj = new ArrayList<>();
        for (int i = 0; i < v; ++i) {
            adj.add(new ArrayList<>());
        }
    }

    void addEdge(int v, int w) {
        adj.get(v).add(w);
    }

    void BFS(int s) {
        boolean[] visited = new boolean[V];
        LinkedList<Integer> queue = new LinkedList<>();

        visited[s] = true;
        queue.add(s);

        while (queue.size() != 0) {
            int c = queue.poll();
            System.out.print(c + " ");

            for (Integer n : adj.get(c)) {
                if (!visited[n]) {
                    visited[n] = true;
                    queue.add(n);
                }
            }
        }
    }

    public static void main(String[] args) {
        GraphBFS g = new GraphBFS(4);
        g.addEdge(0, 1);
        g.addEdge(0, 2);
        g.addEdge(1, 2);
        g.addEdge(2, 0);
        g.addEdge(2, 3);
        g.addEdge(3, 3);
        System.out.println("Following is Breadth First Traversal (starting from 2)");
        g.BFS(2);
    }
}
```

## 6. 使用 `StringBuilder` 进行字符串操作

```java
public class StringBuilderExample {
    public static void main(String[] args) {
        StringBuilder sb = new StringBuilder();
        sb.append("Java");
        sb.append(" is");
        sb.append(" awesome");
        System.out.println("Result: " + sb.toString());
    }
}
```

## 7. 将字符串转换为大写

```java
public class StringUppercase {
    public static void main(String[] args) {
        String str = "hello world";
        String strUpper = str.toUpperCase();
        System.out.println("Uppercase string: " + strUpper);
    }
}
```

## 8. 将字符串转换为小写

```java
public class StringToLowerCase {
    public static void main(String[] args) {
        String str = "HELLO WORLD";
        String strLower = str.toLowerCase();
        System.out.println("Lowercase string: " + strLower);
    }
}
```

## 9. 使用 `Math.random()` 方法

```java
public class RandomNumberExample {
    public static void main(String[] args) {
        double rand = Math.random();
        System.out.println("Random number between 0 and 1: " + rand);
    }
}
```

## 10. 使用 `Math.abs()` 方法

```java
public class AbsoluteValueExample {
    public static void main(String[] args) {
        int num = -10;
        int absNum = Math.abs(num);
        System.out.println("Absolute value of " + num + " is " + absNum);
    }
}
```

# SET-10

## 1. 使用同步方法（Synchronized Method）

```java
class Table {
    synchronized void printTable(int n) {
        for (int i = 1; i <= 5; i++) {
            System.out.println(n * i);
            try {
                Thread.sleep(400);
            } catch (InterruptedException e) {
                System.out.println(e);
            }
        }
    }
}

class MyThread1 extends Thread {
    Table t;

    MyThread1(Table t) {
        this.t = t;
    }

    public void run() {
        t.printTable(5);
    }
}

class MyThread2 extends Thread {
    Table t;

    MyThread2(Table t) {
        this.t = t;
    }

    public void run() {
        t.printTable(100);
    }
}

public class SynchronizedExample {
    public static void main(String[] args) {
        Table obj = new Table();
        MyThread1 t1 = new MyThread1(obj);
        MyThread2 t2 = new MyThread2(obj);
        t1.start();
        t2.start();
    }
}
```

## 2. 使用 `Try-Catch` 块进行异常处理

```java
public class ExceptionHandlingExample {
    public static void main(String[] args) {
        try {
            int data = 50 / 0; // 可能抛出异常
        } catch (ArithmeticException e) {
            System.out.println(e);
        }
        System.out.println("rest of the code");
    }
}
```

## 3. 使用多个 `Catch` 块

```java
public class MultipleCatchExample {
    public static void main(String[] args) {
        try {
            int a[] = new int[5];
            a[5] = 30 / 0;
        } catch (ArithmeticException e) {
            System.out.println("Arithmetic Exception occurs");
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("ArrayOutOfBoundsException occurs");
        } catch (Exception e) {
            System.out.println("Parent Exception occurs");
        }
        System.out.println("rest of the code");
    }
}
```

## 4. `Finally` 块的使用

```java
public class FinallyExample {
    public static void main(String[] args) {
        try {
            int data = 25 / 5;
            System.out.println(data);
        } catch (NullPointerException e) {
            System.out.println(e);
        } finally {
            System.out.println("finally block is always executed");
        }
        System.out.println("rest of the code");
    }
}
```

## 5. `Throw` 关键字的使用



```java
public class ThrowExample {
    static void checkAge(int age) {
        if (age < 18) {
            throw new ArithmeticException("Not Eligible to Vote");
        } else {
            System.out.println("Eligible to Vote");
        }
    }

    public static void main(String[] args) {
        checkAge(15);
        System.out.println("rest of the code");
    }
}
```

### 6. 自定义异常的使用

```java
class MyException extends Exception {
    MyException(String s) {
        super(s);
    }
}

public class CustomExceptionExample {
    public static void main(String[] args) {
        try {
            throw new MyException("This is my custom exception");
        } catch (MyException e) {
            System.out.println(e);
        }
    }
}
```

### 7. 通过 `Thread` 实现 `Runnable` 接口

```java
public class RunnableThreadExample {
    public static void main(String[] args) {
        Runnable r = () -> {
            for (int i = 0; i < 5; i++) {
                System.out.println("Child Thread");
            }
        };

        Thread t = new Thread(r);
        t.start();

        for (int i = 0; i < 5; i++) {
            System.out.println("Main Thread");
        }
    }
}
```

### 8. Java 中嵌套类的使用

```java
public class Outer {
    private int data = 30;

    class Inner {
        void display() {
            System.out.println("data is " + data);
        }
    }

    public static void main(String args[]) {
        Outer obj = new Outer();
        Outer.Inner in = obj.new Inner();
        in.display();
    }
}
```

### 9. Java 中匿名类的使用

```java
abstract class Anonymous {
    abstract void display();
}

public class AnonymousClassExample {
    public static void main(String[] args) {
        Anonymous obj = new Anonymous() {
            void display() {
                System.out.println("Anonymous Class Example");
            }
        };

        obj.display();
    }
}
```

### 10. Java 中接口的使用

```java
interface Drawable {
    void draw();
}

class Rectangle implements Drawable {
    public void draw() {
        System.out.println("drawing rectangle");
    }
}

class Circle implements Drawable {
    public void draw() {
        System.out.println("drawing circle");
    }
}

public class InterfaceExample {
    public static void main(String[] args) {
        Drawable d = new Circle();
        d.draw();
    }
}
```
