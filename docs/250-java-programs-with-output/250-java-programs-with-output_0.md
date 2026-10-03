
# 250+ Java 程序输出示例

![](img/image_rsrc68Z.jpg)

## 前言

作者：Aniket Pataskar

邮箱：pataskaraniket@gmail.com

联系：+91 9423448273

封面设计：Aniket Pataskar

## 关于作者

Aniket O. Pataskar 出自印度。他是一位 IT 软件工程师，拥有多种编程语言的工作经验。

《250+ 带输出的 Java 程序》是一本用于学习的程序集。Aniket 对 Apple 的新兴技术一直感兴趣。

Aniket 在软件开发、iOS（iPhone & iPad）应用开发以及 Android 应用开发和多媒体（如动画、图像编辑、音频编辑、视频编辑和视觉特效）方面拥有技能。

本书献给：

我的家人，感谢他们一如既的爱与支持以及对我的信任。我也将其献给一直激励我完成这项工作的神。没有你们的爱与理解，本书是不可能实现的。从心底感谢你们。

## 1. Hello World

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

输出：

```text
Hello, World!
```

## 2. 两个数字之和

```java
public class SumOfTwoNumbers {
    public static void main(String[] args) {
        int num1 = 10;
        int num2 = 20;
        int sum = num1 + num2;
        System.out.println("Sum: " + sum);
    }
}
```

输出：

```text
Sum: 30
```

## 3. 检查奇偶数

```java
public class EvenOdd {
    public static void main(String[] args) {
        int num = 7;
        if (num % 2 == 0) {
            System.out.println(num + " is even.");
        } else {
            System.out.println(num + " is odd.");
        }
    }
}
```

输出：

```text
7 is odd.
```

## 4. 使用循环打印从 1 到 5 的数字

```java
public class PrintNumbers {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            System.out.println(i);
        }
    }
}
```

输出：

```text
1
2
3
4
5
```

## 5. 数字的阶乘

```java
public class Factorial {
    public static void main(String[] args) {
        int num = 5;
        int factorial = 1;
        for (int i = 1; i <= num; i++) {
            factorial *= i;
        }
        System.out.println("Factorial of " + num + " is " + factorial);
    }
}
```

输出：

```text
Factorial of 5 is 120
```

## 6. 反转字符串

```java
public class ReverseString {
    public static void main(String[] args) {
        String str = "Java";
        String reversed = new StringBuilder(str).reverse().toString();
        System.out.println("Reversed String: " + reversed);
    }
}
```

输出：

```text
Reversed String: avaJ
```

## 7. 检查数字是否为质数

```java
public class PrimeNumber {
    public static void main(String[] args) {
        int num = 29;
        boolean isPrime = true;
        for (int i = 2; i <= num / 2; i++) {
            if (num % i == 0) {
                isPrime = false;
                break;
            }
        }
        if (isPrime) {
            System.out.println(num + " is a prime number.");
        } else {
            System.out.println(num + " is not a prime number.");
        }
    }
}
```

输出：

```text
29 is a prime number.
```

## 8. 查找三个数中的最大值

```java
public class LargestNumber {
    public static void main(String[] args) {
        int num1 = 25, num2 = 78, num3 = 7;
        int largest;
        if (num1 >= num2 && num1 >= num3) {
            largest = num1;
        } else if (num2 >= num1 && num2 >= num3) {
            largest = num2;
        } else {
            largest = num3;
        }
        System.out.println("Largest number is: " + largest);
    }
}
```

## 9. 简单计算器

```java
public class SimpleCalculator {
    public static void main(String[] args) {
        int num1 = 10, num2 = 5;
        System.out.println("Addition: " + (num1 + num2));
        System.out.println("Subtraction: " + (num1 - num2));
        System.out.println("Multiplication: " + (num1 * num2));
        System.out.println("Division: " + (num1 / num2));
    }
}
```

## 10. 前 10 项斐波那契数列

```java
public class FibonacciSeries {
    public static void main(String[] args) {
        int n1 = 0, n2 = 1, count = 10;
        System.out.print(n1 + ", " + n2);
        for (int i = 2; i < count; i++) {
            int next = n1 + n2;
            System.out.print(", " + next);
            n1 = n2;
            n2 = next;
        }
    }
}
```

## 11. 计算数字的位数

```java
public static void main(String[] args) {
    int num = 12345;
    int count = 0;
    while (num != 0) {
        num /= 10;
        count++;
    }
    System.out.println("Number of digits: " + count);
}
```

输出：

```text
Number of digits: 5
```

## 20. 将摄氏度转换为华度

```java
public class CelsiusToFahrenheit {
    public static void main(String[] args) {
        double celsius = 25;
        double fahrenheit = (celsius * 9/5) + 32;
        System.out.println(celsius + " °C = " + fahrenheit + " °F");
    }
}
```

输出：

```text
25.0 °C = 77.0 °F
```

## 21. 将华度转换为摄氏度

```java
public class FahrenheitToCelsius {
    public static void main(String[] args) {
        double fahrenheit = 77;
        double celsius = (fahrenheit - 32) * 5/9;
        System.out.println(fahrenheit + " °F = " + celsius + " °C");
    }
}
```

输出：

```text
77.0 °F = 25.0 °C
```

## 22. 计算圆的面积

```java
public class AreaOfCircle {
    public static void main(String[] args) {
        double radius = 7.5;
        double area = Math.PI * radius * radius;
        System.out.println("Area of the circle: " + area);
    }
}
```

输出：

```text
Area of the circle: 176.71458676442586
```

## 23. 计算圆的周长

```java
public class PerimeterOfCircle {
    public static void main(String[] args) {
        double radius = 7.5;
        double perimeter = 2 * Math.PI * radius;
        System.out.println("Perimeter of the circle: " + perimeter);
    }
}
```

输出：

```text
Perimeter of the circle: 47.12388980384689
```

## 24. 计算单利

```java
public class SimpleInterest {
    public static void main(String[] args) {
        double principal = 1000, rate = 5, time = 2;
        double interest = (principal * rate * time) / 100;
        System.out.println("Simple Interest: " + interest);
    }
}
```

输出：

```text
Simple Interest: 100.0
```

## 25. 计算复利

```java
public class CompoundInterest {
    public static void main(String[] args) {
        double principal = 1000, rate = 5, time = 2, compoundInterest;
        compoundInterest = principal * Math.pow((1 + rate / 100), time) - principal;
        System.out.println("Compound Interest: " + compoundInterest);
    }
}
```

输出：

```text
Compound Interest: 102.5
```

## 26. 将十进制转换为二进制

```java
public class DecimalToBinary {
    public static void main(String[] args) {
        int decimal = 10;
        String binary = Integer.toBinaryString(decimal);
        System.out.println("Binary of " + decimal + " is: " + binary);
    }
}
```

输出：

```text
Binary of 10 is: 1010
```

## 27. 将二进制转换为十进制

```java
public class BinaryToDecimal {
    public static void main(String[] args) {
        String binary = "1010";
        int decimal = Integer.parseInt(binary, 2);
        System.out.println("Decimal of " + binary + " is: " + decimal);
    }
}
```

输出：

```text
Decimal of 1010 is: 10
```

## 28. 将十进制转换为十六进制

```java
public class DecimalToHexadecimal {
    public static void main(String[] args) {
        int decimal = 255;
        String hex = Integer.toHexString(decimal);
        System.out.println("Hexadecimal of " + decimal + " is: " + hex);
    }
}
```

输出：

```text
Hexadecimal of 255 is: ff
```

## 29. 将十六进制转换为十进制

```java
public class HexadecimalToDecimal {
    public static void main(String[] args) {
        String hex = "ff";
        int decimal = Integer.parseInt(hex, 16);
        System.out.println("Decimal of " + hex + " is: " + decimal);
    }
}
```

输出：

```text
Decimal of ff is: 255
```

## 30. 获取字符的 ASCII 值

```java
public class ASCIIValue {
    public static void main(String[] args) {
        char ch = 'A';
        int asciiValue = ch;
        System.out.println("ASCII value of " + ch + " is: " + asciiValue);
    }
}
```

输出：

```text
ASCII value of A is: 65
```

## 31. 计算自然数之和

```java
public class SumOfNaturalNumbers {
    public static void main(String[] args) {
        int num = 10, sum = 0;
        for (int i = 1; i <= num; i++) {
            sum += i;
        }
        System.out.println("Sum of natural numbers up to " + num + " is: " + sum);
    }
}
```

输出：

```text
Sum of natural numbers up to 10 is: 55
```

## 32. 计算数字的平均值



```java
public class AverageOfNumbers {
    public static void main(String[] args) {
        int[] numbers = {2, 3, 5, 7};
        double sum = 0;
        for (int num : numbers) {
            sum += num;
        }
        double average = sum / numbers.length;
        System.out.println("Average: " + average);
    }
}
```

Output:

Average: 4.25

## 33. 查找数组中的最小数字

```java
public class SmallestNumber {
    public static void main(String[] args) {
        int[] numbers = {3, 5, 2, 8};
        int smallest = numbers[0];
        for (int num : numbers) {
            if (num < smallest) {
                smallest = num;
            }
        }
        System.out.println("Smallest number: " + smallest);
    }
}
```

Output:

Smallest number: 2

## 34. 查找数组中的最大数字

```java
public class LargestNumberArray {
    public static void main(String[] args) {
        int[] numbers = {3, 5, 2, 8};
        int largest = numbers[0];
        for (int num : numbers) {
            if (num > largest) {
                largest = num;
            }
        }
        System.out.println("Largest: " + largest);
    }
}
```

Output:

Largest: 8

## 35. 查找数组中的第二大数字

```java
public class SecondLargest {
    public static void main(String[] args) {
        int[] numbers = {3, 5, 2, 8, 1};
        int largest = Integer.MIN_VALUE, secondLargest = Integer.MIN_VALUE;
        for (int num : numbers) {
            if (num > largest) {
                secondLargest = largest;
                largest = num;
            } else if (num > secondLargest && num != largest) {
                secondLargest = num;
            }
        }
        System.out.println("Second largest: " + secondLargest);
    }
}
```

Output:

Second largest: 5

## 36. 打印二维数组

```java
public class Print2DArray {
    public static void main(String[] args) {
        int[][] array = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        for (int i = 0; i < array.length; i++) {
            for (int j = 0; j < array[i].length; j++) {
                System.out.print(array[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

Output:

1 2 3

4 5 6

7 8 9

## 37. 矩阵转置

```java
public class TransposeMatrix {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        int[][] transpose = new int[matrix[0].length][matrix.length];
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[i].length; j++) {
                transpose[j][i] = matrix[i][j];
            }
        }
        for (int i = 0; i < transpose.length; i++) {
            for (int j = 0; j < transpose[i].length; j++) {
                System.out.print(transpose[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

Output:

1 4 7

2 5 8

3 6 9

## 38. 计算两个矩阵的和

```java
public class MatrixAddition {
    public static void main(String[] args) {
        int[][] matrix1 = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        int[][] matrix2 = {
            {9, 8, 7},
            {6, 5, 4},
            {3, 2, 1}
        };
        int[][] sum = new int[3][3];
        for (int i = 0; i < matrix1.length; i++) {
            for (int j = 0; j < matrix1[i].length; j++) {
                sum[i][j] = matrix1[i][j] + matrix2[i][j];
            }
        }
        for (int i = 0; i < sum.length; i++) {
            for (int j = 0; j < sum[i].length; j++) {
                System.out.print(sum[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

Output:

10 10 10

10 10 10

10 10 10

## 39. 两个矩阵的乘积

```java
public class MatrixMultiplication {
    public static void main(String[] args) {
        int[][] matrix1 = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        int[][] matrix2 = {
            {9, 8, 7},
            {6, 5, 4},
            {3, 2, 1}
        };
        int[][] product = new int[3][3];
        for (int i = 0; i < matrix1.length; i++) {
            for (int j = 0; j < matrix2[0].length; j++) {
                for (int k = 0; k < matrix1[0].length; k++) {
                    product[i][j] += matrix1[i][k] * matrix2[k][j];
                }
            }
        }
        for (int i = 0; i < product.length; i++) {
            for (int j = 0; j < product[i].length; j++) {
                System.out.print(product[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

Output:

30 24 18

84 69 54

138 114 90

## 40. 统计字符串中元音的数量

```java
public class CountVowels {
    public static void main(String[] args) {
        String str = "Hello World";
        int count = 0;
        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);
            if (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u' ||
                ch == 'A' || ch == 'E' || ch == 'I' || ch == 'O' || ch == 'U') {
                count++;
            }
        }
        System.out.println("Number of vowels: " + count);
    }
}
```

Output:

Number of vowels: 3

## 41. 查找字符串中字符的频率

```java
import java.util.HashMap;
import java.util.Map;

public class FrequencyOfCharacters {
    public static void main(String[] args) {
        String str = "Hello World";
        Map<Character, Integer> frequencyMap = new HashMap<>();
        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);
            frequencyMap.put(ch, frequencyMap.getOrDefault(ch, 0) + 1);
        }
        for (Map.Entry<Character, Integer> entry : frequencyMap.entrySet()) {
            System.out.println(entry.getKey() + ": " + entry.getValue());
        }
    }
}
```

Output:

```text
H: 1
e: 1
l: 3
o: 2
: 1
W: 1
r: 1
d: 1
```

## 42. 从字符串中移除元音

```java
public class RemoveVowels {
    public static void main(String[] args) {
        String str = "Hello World";
        String result = str.replaceAll("[aeiouAEIOU]", "");
        System.out.println("String without vowels: " + result);
    }
}
```

Output:

```text
String without vowels: Hll Wrld
```

## 43. 获取字符串的长度

```java
public class StringLength {
    public static void main(String[] args) {
        String str = "Hello World";
        int length = str.length();
        System.out.println("Length of the string: " + length);
    }
}
```

Output:

```text
Length of the string: 11
```

## 44. 检查字符串是否包含子字符串

```java
public class ContainsSubstring {
    public static void main(String[] args) {
        String str = "Hello World";
        String substring = "World";
        boolean contains = str.contains(substring);
        System.out.println("Contains '" + substring + "': " + contains);
    }
}
```

Output:

```text
Contains 'World': true
```

## 45. 将字符串转换为大写

```java
public class ConvertToUppercase {
    public static void main(String[] args) {
        String str = "hello world";
        String uppercaseStr = str.toUpperCase();
        System.out.println("Uppercase: " + uppercaseStr);
    }
}
```

Output:

```text
Uppercase: HELLO WORLD
```

## 46. 将字符串转换为小写

```java
public class ConvertToLowercase {
    public static void main(String[] args) {
        String str = "HELLO WORLD";
        String lowercaseStr = str.toLowerCase();
        System.out.println("Lowercase: " + lowercaseStr);
    }
}
```

Output:

```text
Lowercase: hello world
```

## 47. 反转字符串

```java
public class ReverseString {
    public static void main(String[] args) {
        String str = "Hello World";
        String reversed = new StringBuilder(str).reverse().toString();
        System.out.println("Reversed string: " + reversed);
    }
}
```

Output:

```text
Reversed string: dlroW olleH
```

## 48. 求数组元素之和



```java
public class SumOfArray {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5};
        int sum = 0;
        for (int num : array) {
            sum += num;
        }
        System.out.println("Sum of array elements: " + sum);
    }
}
```

Output:

```text
Sum of array elements: 15
```

## 49. 求数组元素的平均值

```java
public class AverageOfArray {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5};
        double sum = 0;
        for (int num : array) {
            sum += num;
        }
        double average = sum / array.length;
        System.out.println("Average of array elements: " + average);
    }
}
```

Output:

```text
Average of array elements: 3.0
```

## 50. 寻找数组中的最小元素

```java
public class MinimumElementArray {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5};
        int min = array[0];
        for (int num : array) {
            if (num < min) {
                min = num;
            }
        }
        System.out.println("Minimum element in array: " + min);
    }
}
```

Output:

```text
Minimum element in array: 1
```

## 51. 寻找数组中的最大元素

```java
public class MaximumElementArray {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5};
        int max = array[0];
        for (int num : array) {
            if (num > max) {
                max = num;
            }
        }
        System.out.println("Maximum element in array: " + max);
    }
}
```

Output:

```text
Maximum element in array: 5
```

## 52. 统计元素在数组中的出现次数

```java
public class CountOccurrences {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 2, 4, 2};
        int target = 2;
        int count = 0;
        for (int num : array) {
            if (num == target) {
                count++;
            }
        }
        System.out.println("Occurrences of " + target + ": " + count);
    }
}
```

Output:

```text
Occurrences of 2: 3
```

## 53. 检查数组是否包含给定元素

```java
public class ContainsElementArray {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5};
        int target = 3;
        boolean found = false;
        for (int num : array) {
            if (num == target) {
                found = true;
            }
        }
        System.out.println("Array contains " + target + ": " + found);
    }
}
```

Output:

```text
Array contains 3: true
```

## 54. 反转数组

```java
public class ReverseArray {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5};
        for (int i = 0, j = array.length - 1; i < j; i++, j--) {
            int temp = array[i];
            array[i] = array[j];
            array[j] = temp;
        }
        System.out.print("Reversed array: ");
        for (int num : array) {
            System.out.print(num + " ");
        }
    }
}
```

Output:

```text
Reversed array: 5 4 3 2 1
```

## 55. 寻找数组中的第二大元素

```java
public class SecondLargestArray {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5};
        int firstLargest = Integer.MIN_VALUE;
        int secondLargest = Integer.MIN_VALUE;
        for (int num : array) {
            if (num > firstLargest) {
                secondLargest = firstLargest;
                firstLargest = num;
            } else if (num > secondLargest && num != firstLargest) {
                secondLargest = num;
            }
        }
        System.out.println("Second largest element: " + secondLargest);
    }
}
```

Output:

```text
Second largest element: 4
```

## 56. 使用递归计算数字的阶阶

```java
public class FactorialRecursion {
    public static void main(String[] args) {
        int num = 5;
        int factorial = factorial(num);
        System.out.println("Factorial of " + num + " is: " + factorial);
    }

    public static int factorial(int num) {
        if (num == 0) {
            return 1;
        }
        return num * factorial(num - 1);
    }
}
```

Output:

```text
Factorial of 5 is: 120
```

## 57. 使用递归寻找斐波那契数列

```java
public class FibonacciRecursion {
    public static void main(String[] args) {
        int count = 10;
        for (int i = 0; i < count; i++) {
            System.out.print(fibonacci(i) + " ");
        }
    }

    public static int fibonacci(int num) {
        if (num <= 1) {
            return num;
        }
        return fibonacci(num - 1) + fibonacci(num - 2);
    }
}
```

Output:

```text
0 1 1 2 3 5 8 13 21 34 
```

## 58. 使用递归寻找最大公约数

```java
public class GCDRecursion {
    public static void main(String[] args) {
        int num1 = 54, num2 = 24;
        int gcd = gcd(num1, num2);
        System.out.println("GCD is: " + gcd);
    }

    public static int gcd(int num1, int num2) {
        if (num2 == 0) {
            return num1;
        }
        return gcd(num2, num1 % num2);
    }
}
```

Output:

```text
GCD is: 6
```

## 59. 使用递归计算数字位之和

```java
public class SumOfDigitsRecursion {
    public static void main(String[] args) {
        int num = 1234;
        int sum = sumOfDigits(num);
        System.out.println("Sum of digits: " + sum);
    }

    public static int sumOfDigits(int num) {
        if (num == 0) {
            return 0;
        }
        return num % 10 + sumOfDigits(num / 10);
    }
}
```

Output:

```text
Sum of digits: 10
```

## 60. 使用递归检查字符串是否为回文

```java
public class PalindromeRecursion {
    public static void main(String[] args) {
        String str = "madam";
        boolean isPalindrome = isPalindrome(str, 0, str.length() - 1);
        System.out.println("Is palindrome: " + isPalindrome);
    }

    public static boolean isPalindrome(String str, int start, int end) {
        if (start >= end) {
            return true;
        }
        if (str.charAt(start) != str.charAt(end)) {
            return false;
        }
        return isPalindrome(str, start + 1, end - 1);
    }
}
```

Output:

```text
Is palindrome: true
```

## 61. 使用递归计算数字的幂

```java
public class PowerRecursion {
    public static void main(String[] args) {
        int base = 2, exponent = 3;
        int result = power(base, exponent);
        System.out.println(base + "^" + exponent + " = " + result);
    }

    public static int power(int base, int exponent) {
        if (exponent == 0) {
            return 1;
        }
        return base * power(base, exponent - 1);
    }
}
```

Output:

```text
2³ = 8
```

## 62. 将二进制转换为十进制

```java
public class BinaryToDecimal {
    public static void main(String[] args) {
        String binary = "1010";
        int decimal = Integer.parseInt(binary, 2);
        System.out.println("Decimal: " + decimal);
    }
}
```

Output:

```text
Decimal: 10
```

## 63. 将十进制转换为二进制

```java
public class DecimalToBinary {
    public static void main(String[] args) {
        int decimal = 10;
        String binary = Integer.toBinaryString(decimal);
        System.out.println("Binary: " + binary);
    }
}
```

Output:

```text
Binary: 1010
```

## 64. 十进制转十六进制

```java
public class DecimalToHexadecimal {
    public static void main(String[] args) {
        int decimal = 255;
        String hex = Integer.toHexString(decimal);
        System.out.println("Hexadecimal: " + hex);
    }
}
```

Output:

```text
Hexadecimal: ff
```

## 65. 十六进制转进制

```java
public class HexadecimalToDecimal {
    public static void main(String[] args) {
        String hex = "ff";
        int decimal = Integer.parseInt(hex, 16);
        System.out.println("Decimal: " + decimal);
    }
}
```

Output:

```text
Decimal: 255
```

## 66. 使用临时变量交换两个数字

```java
public class SwapNumbers {
    public static void main(String[] args) {
        int a = 5, b = 10;
        int temp = a;
        a = b;
        b = temp;
        System.out.println("After swapping: a = " + a + ", b = " + b);
    }
}
```

Output:

```text
After swapping: a = 10, b = 5
```

## 67. 不使用临时变量交换两个数字



```java
public class SwapNumbersWithoutTemp {
    public static void main(String[] args) {
        int a = 5, b = 10;
        a = a + b;
        b = a - b;
        a = a - b;
        System.out.println("After swapping: a = " + a + ", b = " + b);
    }
}
```

Output:

After swapping: a = 10, b = 5

## 68. 反转数字

```java
public class ReverseNumber {
    public static void main(String[] args) {
        int num = 1234, reversed = 0;
        while (num != 0) {
            int digit = num % 10;
            reversed = reversed * 10 + digit;
            num /= 10;
        }
        System.out.println("Reversed number: " + reversed);
    }
}
```

Output:

Reversed number: 4321

## 69. 检查一个数字是否为阿姆斯特斯特数

```java
public class ArmstrongNumber {
    public static void main(String[] args) {
        int num = 153, originalNum, remainder, result = 0;
        originalNum = num;
        while (originalNum != 0) {
            remainder = originalNum % 10;
            result += Math.pow(remainder, 3);
            originalNum /= 10;
        }
        if (result == num) {
            System.out.println(num + " is an Armstrong number.");
        } else {
            System.out.println(num + " is not an Armstrong number.");
        }
    }
}
```

Output:

153 is an Armstrong number.

## 70. 检查一个数字是否为质数

```java
public class PrimeNumber {
    public static void main(String[] args) {
        int num = 29;
        boolean isPrime = true;
        for (int i = 2; i <= num / 2; i++) {
            if (num % i == 0) {
                isPrime = false;
                break;
            }
        }
        if (isPrime) {
            System.out.println(num + " is a prime number.");
        } else {
            System.out.println(num + " is not a prime number.");
        }
    }
}
```

Output:

29 is a prime number.

## 71. 寻找两个数字的最小公倍数（LCM）

```java
public class LCM {
    public static void main(String[] args) {
        int num1 = 72, num2 = 120, lcm;
        lcm = (num1 > num2) ? num1 : num2;
        while (true) {
            if (lcm % num1 == 0 && lcm % num2 == 0) {
                System.out.println("LCM of " + num1 + " and " + num2 + " is: " + lcm);
                break;
            }
            lcm++;
        }
    }
}
```

Output:

LCM of 72 and 120 is: 360

## 72. 寻找两个数字的最大公约数（HCF）

```java
public class HCF {
    public static void main(String[] args) {
        int num1 = 72, num2 = 120, hcf = 1;
        for (int i = 1; i <= num1 && i <= num2; i++) {
            if (num1 % i == 0 && num2 % i == 0) {
                hcf = i;
            }
        }
        System.out.println("HCF of " + num1 + " and " + num2 + " is: " + hcf);
    }
}
```

Output:

HCF of 72 and 120 is: 24

## 73. 检查一个数字是偶数还是奇数

```java
public class EvenOrOdd {
    public static void main(String[] args) {
        int num = 29;
        if (num % 2 == 0) {
            System.out.println(num + " is even.");
        } else {
            System.out.println(num + " is odd.");
        }
    }
}
```

Output:

29 is odd.

## 74. 生成随机数

```java
import java.util.Random;

public class RandomNumber {
    public static void main(String[] args) {
        Random rand = new Random();
        int randomNum = rand.nextInt(100);
        System.out.println("Random number: " + randomNum);
    }
}
```

Output:

Random number between 0 and 99

## 75. 使用欧几里得算法寻找两个数字的最大公约数（GCD）

```java
public class EuclideanGCD {
    public static void main(String[] args) {
        int num1 = 56, num2 = 98;
        while (num1 != num2) {
            if (num1 > num2) {
                num1 -= num2;
            } else {
                num2 -= num1;
            }
        }
        System.out.println("GCD: " + num1);
    }
}
```

Output:

GCD: 14

## 76. 求一个数字的平方根

```java
public class SquareRoot {
    public static void main(String[] args) {
        int num = 25;
        double sqrt = Math.sqrt(num);
        System.out.println("Square root of " + num + " is: " + sqrt);
    }
}
```

Output:

Square root of 25 is: 5.0

## 77. 检查一个数字是否为完全平方

```java
public class PerfectSquare {
    public static void main(String[] args) {
        int num = 16;
        double sqrt = Math.sqrt(num);
        if (sqrt == Math.floor(sqrt)) {
            System.out.println(num + " is a perfect square.");
        } else {
            System.out.println(num + " is not a perfect square.");
        }
    }
}
```

Output:

16 is a perfect square.

## 78. 检查一个数字是否为回文

```java
public class PalindromeNumber {
    public static void main(String[] args) {
        int num = 121, reversed = 0, originalNum = num;
        while (num != 0) {
            int digit = num % 10;
            reversed = reversed * 10 + digit;
            num /= 10;
        }
        if (originalNum == reversed) {
            System.out.println(originalNum + " is a palindrome.");
        } else {
            System.out.println(originalNum + " is not a palindrome.");
        }
    }
}
```

Output:

121 is a palindrome.

## 79. 寻找到 N 的质数之和

```java
public class SumOfPrimes {
    public static void main(String[] args) {
        int n = 10;
        int sum = 0;
        for (int i = 2; i <= n; i++) {
            if (isPrime(i)) {
                sum += i;
            }
        }
        System.out.println("Sum of prime numbers up to " + n + " is: " + sum);
    }

    public static boolean isPrime(int num) {
        for (int i = 2; i <= num / 2; i++) {
            if (num % i == 0) {
                return false;
            }
        }
        return true;
    }
}
```

Output:

Sum of prime numbers up to 10 is: 17

## 80. 寻找到 N 的自然数之和

```java
public class SumOfNaturalNumbers {
    public static void main(String[] args) {
        int n = 10;
        int sum = n * (n + 1) / 2;
        System.out.println("Sum of first " + n + " natural numbers is: " + sum);
    }
}
```

Output:

Sum of first 10 natural numbers is: 55

## 81. 将字符转换为其 ASCII 值

```java
public class CharToASCII {
    public static void main(String[] args) {
        char ch = 'A';
        int ascii = (int) ch;
        System.out.println("ASCII value of " + ch + " is: " + ascii);
    }
}
```

Output:

ASCII value of A is: 65

## 82. 寻找数组中偶数和奇数的之和

```java
public class SumEvenOddArray {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5};
        int sumEven = 0, sumOdd = 0;
        for (int num : array) {
            if (num % 2 == 0) {
                sumEven += num;
            } else {
                sumOdd += num;
            }
        }
        System.out.println("Sum of even numbers: " + sumEven);
        System.out.println("Sum of odd numbers: " + sumOdd);
    }
}
```

Output:

Sum of even numbers: 6

Sum of odd numbers: 9

## 83. 寻找数组元素的乘积

```java
public class ProductOfArray {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5};
        int product = 1;
        for (int num : array) {
            product *= num;
        }
        System.out.println("Product of array elements: " + product);
    }
}
```

Output:

Product of array elements: 120

## 84. 寻找数组中的最大和最小元素

```java
public class LargestSmallestArray {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5};
        int largest = array[0], smallest = array[0];
        for (int num : array) {
            if (num > largest) {
                largest = num;
            }
            if (num < smallest) {
                smallest = num;
            }
        }
        System.out.println("Largest element: " + largest);
        System.out.println("Smallest element: " + smallest);
    }
}
```

Output:

Largest element: 5

Smallest element: 1

## 85. 统计数字的位数

```java
public class CountDigits {
    public static void main(String[] args) {
        int num = 12345;
        int count = 0;
        while (num != 0) {
            num /= 10;
            count++;
        }
        System.out.println("Number of digits: " + count);
    }
}
```

Output:

Number of digits: 5

## 86. 打印数字的乘法表



```java
public class MultiplicationTable {
    public static void main(String[] args) {
        int num = 5;
        for (int i = 1; i <= 10; i++) {
            System.out.println(num + " x " + i + " = " + (num * i));
        }
    }
}
```

Output:

5 x 1 = 5  
5 x 2 = 10  
5 x 3 = 15  
5 x 4 = 20  
5 x 5 = 25  
5 x 6 = 30  
5 x 7 = 35  
5 x 8 = 40  
5 x 9 = 45  
5 x 10 = 50

## 87. 寻找矩阵对角线之和

```java
public class SumOfDiagonals {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        int primaryDiagonal = 0, secondaryDiagonal = 0;
        for (int i = 0; i < matrix.length; i++) {
            primaryDiagonal += matrix[i][i];
            secondaryDiagonal += matrix[i][matrix.length - i - 1];
        }
        System.out.println("主对角线之和: " + primaryDiagonal);
        System.out.println("副对角线之和: " + secondaryDiagonal);
    }
}
```

输出:

```text
主对角线之和: 15
副对角线之和: 15
```

## 88. 寻找矩阵的转置

```java
public class TransposeMatrix {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        int[][] transpose = new int[matrix[0].length][matrix.length];
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[0].length; j++) {
                transpose[j][i] = matrix[i][j];
            }
        }
        System.out.println("矩阵的转置:");
        for (int[] row : transpose) {
            for (int val : row) {
                System.out.print(val + " ");
            }
            System.out.println();
        }
    }
}
```

输出:

```text
矩阵的转置:
1 4 7
2 5 8
3 6 9
```

## 89. 不使用递归打印斐波那契序列

```java
public class FibonacciWithoutRecursion {
    public static void main(String[] args) {
        int count = 10, num1 = 0, num2 = 1;
        System.out.print("斐波那契序列: " + num1 + " " + num2);
        for (int i = 2; i < count; ++i) {
            int num3 = num1 + num2;
            System.out.print(" " + num3);
            num1 = num2;
            num2 = num3;
        }
    }
}
```

输出:

```text
斐波那契序列: 0 1 1 2 3 5 8 13 21 34
```

## 90. 实现一个基础计算器

```java
import java.util.Scanner;
public class BasicCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("输入第一个数字: ");
        double num1 = scanner.nextDouble();
        System.out.print("输入第二个数字: ");
        double num2 = scanner.nextDouble();
        System.out.print("输入运算符 (+, -, /): ");
        char operator = scanner.next().charAt(0);
        double result = 0;
        switch (operator) {
            case '+':
                result = num1 + num2;
                break;
            case '-':
                result = num1 - num2;
                break;
            case '*':
                result = num1 * num2;
                break;
            case '/':
                if (num2 != 0) {
                    result = num1 / num2;
                } else {
                    System.out.println("不能除以零");
                    return;
                }
                break;
            default:
                System.out.println("无效运算符");
                return;
        }
        System.out.println("结果: " + result);
    }
}
```

输出:

```text
输入第一个数字: 10
输入第二个数字: 5
输入运算符 (+, -, /): /
结果: 2.0
```

## 91. 检查两个字符串是否为异位词

```java
import java.util.Arrays;
public class AnagramCheck {
    public static void main(String[] args) {
        String str1 = "listen";
        String str2 = "silent";
        if (isAnagram(str1, str2)) {
            System.out.println(str1 + " 和 " + str2 + " 是异位词.");
        } else {
            System.out.println(str1 + " 和 " + str2 + "不是异位词.");
        }
    }
    public static boolean isAnagram(String str1, String str2) {
        if (str1.length() != str2.length()) {
            return false;
        }
        char[] arr1 = str1.toCharArray();
        char[] arr2 = str2.toCharArray();
        Arrays.sort(arr1);
        Arrays.sort(arr2);
        return Arrays.equals(arr1, arr2);
    }
}
```

输出:

```text
listen 和 silent 是异位词.
```

## 92. 使用递归求数字的阶乘

```java
public class FactorialRecursion {
    public static void main(String[] args) {
        int num = 5;
        int result = factorial(num);
        System.out.println(num + "的阶乘: " + result);
    }
    public static int factorial(int n) {
        if (n == 0) {
            return 1;
        }
        return n * factorial(n - 1);
    }
}
```

输出:

```text
5 的阶乘: 120
```

## 93. 使用循环计算数字的幂

```java
public class PowerLoop {
    public static void main(String[] args) {
        int base = 2, exponent = 4;
        int result = 1;
        for (int i = 0; i < exponent; i++) {
            result *= base;
        }
        System.out.println(base + "^" + exponent + " = " + result);
    }
}
```

输出:

```text
2⁴ = 16
```

## 94. 使用递归求自然数之和

```java
public class SumNaturalRecursion {
    public static void main(String[] args) {
        int n = 10;
        int sum = sum(n);
        System.out.println("前 " + n + " 个自然数之和: " + sum);
    }
    public static int sum(int n) {
        if (n == 1) {
            return n;
        }
        return n + sum(n - 1);
    }
}
```

输出:

```text
前 10 个自然数之和: 55
```

## 95. 使用递归寻找斐波那契序列

```java
public class FibonacciRecursion {
    public static void main(String[] args) {
        int n = 10;
        System.out.print("斐波那契序列: ");
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

输出:

```text
斐波那契序列: 0 1 1 2 3 5 8 13 21 34 
```

## 96. 使用递归计算数字各位数字之和

```java
public class SumOfDigitsRecursion {
    public static void main(String[] args) {
        int num = 1234;
        int sum = sumOfDigits(num);
        System.out.println("各位数字之和: " + sum);
    }
    public static int sumOfDigits(int num) {
        if (num == 0) {
            return 0;
        }
        return num % 10 + sumOfDigits(num / 10);
    }
}
```

输出:

```text
各位数字之和: 10
```

## 97. 使用递归反转字符串

```java
public class ReverseRecursion {
    public static void main(String[] args) {
        String str = "Hello";
        String reversed = reverseString(str);
        System.out.println("反转字符串: " + reversed);
    }
    public static String reverseString(String str) {
        if (str.isEmpty()) {
            return str;
        }
        return reverseString(str.substring(1)) + str.charAt(0);
    }
}
```

输出:

```text
反转字符串: olH
```

## 98. 使用递归计算最大公约数 (GCD)

```java
public class GCDRecursion {
    public static void main(String[] args) {
        int num1 = 56, num2 = 98;
        int gcd = gcd(num1, num2);
        System.out.println("最大公约数: " + gcd);
    }
    public static int gcd(int a, int b) {
        if (b == 0) {
            return a;
        }
        return gcd(b, a % b);
    }
}
```

输出:

```text
最大公约数: 14
```

## 99. 打印到 N 的质数

```java
public class PrimeNumbers {
    public static void main(String[] args) {
        int n = 50;
        System.out.print("到 " + n + " 的质数: ");
        for (int i = 2; i <= n; i++) {
            if (isPrime(i)) {
                System.out.print(i + " ");
            }
        }
    }
    public static boolean isPrime(int num) {
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) {
                return false;
            }
        }
        return true;
    }
}
```

输出:

```text
到 50 的质数: 2 3 5 7 11 13 17 19 23 29 31 37 41 43 47 
```

## 100. 不使用 length() 方法查找字符串长度

```java
public class StringLength {
    public static void main(String[] args) {
        String str = "Hello, World!";
        int length = 0;
        for (char c : str.toCharArray()) {
            length++;
        }
        System.out.println("字符串长度: " + length);
    }
}
```

输出:

```text
字符串长度: 13
```

## 101. 查找字符串中第一个非重复字符



```java
import java.util.LinkedHashMap;
import java.util.Map;

public class FirstNonRepeatedCharacter {
    public static void main(String[] args) {
        String str = "swiss";
        char result = firstNonRepeatedChar(str);
        if (result != 0) {
            System.out.println("第一个非重复字符: " + result);
        } else {
            System.out.println("所有字符都重复了.");
        }
    }

    public static char firstNonRepeatedChar(String str) {
        Map<Character, Integer> charCount = new LinkedHashMap<>();
        for (char c : str.toCharArray()) {
            charCount.put(c, charCount.getOrDefault(c, 0) + 1);
        }
        for (Map.Entry<Character, Integer> entry : charCount.entrySet()) {
            if (entry.getValue() == 1) {
                return entry.getKey();
            }
        }
        return 0;
    }
}
```

输出：

第一个非重复字符：w

## 102. 使用递归检查数字是否为回文

```java
public class PalindromeCheckRecursion {
    public static void main(String[] args) {
        int num = 121;
        boolean isPalindrome = isPalindrome(num, 0, String.valueOf(num).length() - 1);
        System.out.println(num + " 是回文: " + isPalindrome);
    }

    public static boolean isPalindrome(int num, int start, int end) {
        String str = String.valueOf(num);
        if (start >= end) {
            return true;
        }
    }
}
```

```java
if (str.charAt(start) != str.charAt(end)) {
    return false;
}
return isPalindrome(num, start + 1, end - 1);
}
```

输出：

121 是回文：true

## 103. 统计字符串中的单词数

```java
public class WordCount {
    public static void main(String[] args) {
        String str = "Hello, how are you?";
        String[] words = str.split("\\s+");
        System.out.println("Number of words: " + words.length);
    }
}
```

输出：

单词数：4

## 104. 寻找数组中的第二大数字

```java
public class SecondLargest {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5};
        int largest = Integer.MIN_VALUE, secondLargest = Integer.MIN_VALUE;
        for (int num : array) {
            if (num > largest) {
                secondLargest = largest;
                largest = num;
            } else if (num > secondLargest && num != largest) {
                secondLargest = num;
            }
        }
        System.out.println("Second largest number: " + secondLargest);
    }
}
```

输出：

第二大数字：4

## 105. 计算数组中所有质数的之和

```java
public class SumOfPrimesInArray {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
        int sum = 0;
        for (int num : array) {
            if (isPrime(num)) {
                sum += num;
            }
        }
        System.out.println("Sum of prime numbers: " + sum);
    }

    public static boolean isPrime(int num) {
        if (num <= 1) {
            return false;
        }
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) {
                return false;
            }
        }
        return true;
    }
}
```

输出：

质数之和：17

## 106. 用特定字符替换字符串中的所有元音

```java
public class ReplaceVowels {
    public static void main(String[] args) {
        String str = "Hello World";
        char replaceChar = '*';
        String result = str.replaceAll("[AEIOUaeiou]", String.valueOf(replaceChar));
        System.out.println("Modified string: " + result);
    }
}
```

输出：

修改后的字符串：H*ll* W*rld

## 107. 寻找数组中最大的回文数

```java
public class LargestPalindromeInArray {
    public static void main(String[] args) {
        int[] array = {123, 121, 545, 999, 1001, 12321};
        int largestPalindrome = 0;
        for (int num : array) {
            if (isPalindrome(num) && num > largestPalindrome) {
                largestPalindrome = num;
            }
        }
        System.out.println("Largest palindrome: " + largestPalindrome);
    }

    public static boolean isPalindrome(int num) {
        int original = num, reverse = 0;
        while (num != 0) {
            int digit = num % 10;
            reverse = reverse * 10 + digit;
            num /= 10;
        }
        return original == reverse;
    }
}
```

输出：

最大的回文数：12321

## 108. 统计字符串中的元音和辅音数

```java
public class CountVowelsConsonants {
    public static void main(String[] args) {
        String str = "Hello World";
        int vowels = 0, consonants = 0;
        str = str.toLowerCase();
        for (char c : str.toCharArray()) {
            if (c >= 'a' && c <= 'z') {
                if (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u') {
                    vowels++;
                } else {
                    consonants++;
                }
            }
        }
        System.out.println("Number of vowels: " + vowels);
        System.out.println("Number of consonants: " + consonants);
    }
}
```

输出：

元音数：3

辅音数：7

## 109. 检查一个数字是否为阿姆斯特数（Armstrong Number）

```java
public class ArmstrongNumber {
    public static void main(String[] args) {
        int num = 153;
        if (isArmstrong(num)) {
            System.out.println(num + " is an Armstrong number.");
        } else {
            System.out.println(num + " is not an Armstrong number.");
        }
    }

    public static boolean isArmstrong(int num) {
        int original = num, result = 0;
        int n = String.valueOf(num).length();
        while (num != 0) {
            int digit = num % 10;
            result += Math.pow(digit, n);
            num /= 10;
        }
        return original == result;
    }
}
```

输出：

153 是阿姆斯特数。

## 110. 将十进制数转换为二进制

```java
public class DecimalToBinary {
    public static void main(String[] args) {
        int num = 10;
        String binary = Integer.toBinaryString(num);
        System.out.println("Binary of " + num + " is " + binary);
    }
}
```

输出：

10 的二进制是 1010

## 111. 将二进制数转换为十进制

```java
public class BinaryToDecimal {
    public static void main(String[] args) {
        String binary = "1010";
        int decimal = Integer.parseInt(binary, 2);
        System.out.println("Decimal of " + binary + " is " + decimal);
    }
}
```

输出：

1010 的十进制是 10

## 112. 将十进制数转换为十六进制

```java
public class DecimalToHexadecimal {
    public static void main(String[] args) {
        int num = 255;
        String hex = Integer.toHexString(num);
        System.out.println("Hexadecimal of " + num + " is " + hex);
    }
}
```

输出：

255 的十六进制是 FF

## 113. 将十六进制数转换为十进制

```java
public class HexadecimalToDecimal {
    public static void main(String[] args) {
        String hex = "FF";
        int decimal = Integer.parseInt(hex, 16);
        System.out.println("Decimal of " + hex + " is " + decimal);
    }
}
```

输出：

FF 的十进制是 255

## 114. 寻找两个数的最大公约数（HCF）和最小公倍数（LCM）

```java
public class HCFAndLCM {
    public static void main(String[] args) {
        int num1 = 12, num2 = 18;
        int hcf = gcd(num1, num2);
        int lcm = (num1 * num2) / hcf;
        System.out.println("HCF: " + hcf);
        System.out.println("LCM: " + lcm);
    }

    public static int gcd(int a, int b) {
        if (b == 0) {
            return a;
        }
        return gcd(b, a % b);
    }
}
```

输出：

HCF：6

LCM：36

## 115. 使用递归反转数字

```java
public class ReverseNumberRecursion {
    public static void main(String[] args) {
        int num = 1234;
        int reversed = reverse(num);
        System.out.println("Reversed number: " + reversed);
    }

    public static int reverse(int num) {
        String str = Integer.toString(num);
        if (str.length() == 1) {
            return num;
        }
        return Integer.parseInt(
            str.charAt(str.length() - 1) + ""
                + reverse(Integer.parseInt(str.substring(0, str.length() - 1)))
        );
    }
}
```

输出：

反转数字：4321

## 116. 寻找数组中偶数的之和

```java
public class SumOfEvenNumbers {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5, 6};
        int sum = 0;
        for (int num : array) {
            if (num % 2 == 0) {
                sum += num;
            }
        }
        System.out.println("Sum of even numbers: " + sum);
    }
}
```



输出：

偶数之和: 12

### 117. 使用循环检查字符串是否为回文

```java
public class PalindromeCheckLoop {
    public static void main(String[] args) {
        String str = "madam";
        boolean isPalindrome = true;
        int n = str.length();
        for (int i = 0; i < n / 2; i++) {
            if (str.charAt(i) != str.charAt(n - i - 1)) {
                isPalindrome = false;
                break;
            }
        }
        System.out.println(str + " is palindrome: " + isPalindrome);
    }
}
```

输出：

madam 是回文: true

### 118. 查找整数的位数

```java
public class NumberOfDigits {
    public static void main(String[] args) {
        int num = 123456;
        int count = 0;
        while (num != 0) {
            num /= 10;
            count++;
        }
        System.out.println("Number of digits: " + count);
    }
}
```

输出：

位数: 6

### 119. 为给定数字生成乘法表

```java
public class MultiplicationTable {
    public static void main(String[] args) {
        int num = 5;
        for (int i = 1; i <= 10; i++) {
            System.out.println(num + " * " + i + " = " + num * i);
        }
    }
}
```

输出：

5 * 1 = 5  
5 * 2 = 10  
5 * 3 = 15  
5 * 4 = 20  
5 * 5 = 25  
5 * 6 = 30  
5 * 7 = 35  
5 * 8 = 40  
5 * 9 = 45  
5 * 10 = 50

### 120. 计算矩形的面积

```java
public class AreaOfRectangle {
    public static void main(String[] args) {
        int length = 10;
        int breadth = 5;
        int area = length * breadth;
        System.out.println("Area of rectangle: " + area);
    }
}
```

输出：

矩形面积: 50

### 121. 检查一个数字是偶数还是奇数

```java
public class EvenOddCheck {
    public static void main(String[] args) {
        int num = 7;
        if (num % 2 == 0) {
            System.out.println(num + " is even.");
        } else {
            System.out.println(num + " is odd.");
        }
    }
}
```

输出：

7 是奇数。

### 122. 寻找数组中的最小数字

```java
public class SmallestNumber {
    public static void main(String[] args) {
        int[] array = {3, 1, 4, 1, 5, 9};
        int smallest = array[0];
        for (int num : array) {
            if (num < smallest) {
                smallest = num;
            }
        }
        System.out.println("Smallest number: " + smallest);
    }
}
```

输出：

最小数字: 1

### 123. 将摄氏度转换为华氏度

```java
public class CelsiusToFahrenheit {
    public static void main(String[] args) {
        double celsius = 25;
        double fahrenheit = (celsius * 9/5) + 32;
        System.out.println(celsius + "°C = " + fahrenheit + "°F");
    }
}
```

Output:

`25.0°C = 77.0°F`

### 124. 找出数组中奇数的和

```java
public class SumOfOddNumbers {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5, 6};
        int sum = 0;
        for (int num : array) {
            if (num % 2 != 0) {
                sum += num;
            }
        }
        System.out.println("Sum of odd numbers: " + sum);
    }
}
```

Output:

`Sum of odd numbers: 9`

### 125. 检查年份是否为闰年

```java
public class LeapYearCheck {
    public static void main(String[] args) {
        int year = 2020;
        if ((year % 4 == 0 && year % 100 != 0) || (year % 400 == 0)) {
            System.out.println(year + " is a leap year.");
        } else {
            System.out.println(year + " is not a leap year.");
        }
    }
}
```

Output:

`2020 is a leap year.`

### 126. 计算圆面积

```java
public class AreaOfCircle {
    public static void main(String[] args) {
        double radius = 7;
        double area = Math.PI * radius * radius;
        System.out.println("Area of circle: " + area);
    }
}
```

Output:

`Area of circle: 153.93804002589985`

### 127. 计算三角形的面积

```java
public class AreaOfTriangle {
    public static void main(String[] args) {
        double base = 5;
        double height = 10;
        double area = 0.5 * base * height;
        System.out.println("Area of triangle: " + area);
    }
}
```

Output:

`Area of triangle: 25.0`

### 128. 使用循环寻找两个数的最大公约数 (GCD)

```java
public class GCDLoop {
    public static void main(String[] args) {
        int num1 = 56;
        int num2 = 98;
        int gcd = 1;
        for (int i = 1; i <= num1 && i <= num2; i++) {
            if (num1 % i == 0 && num2 % i == 0) {
                gcd = i;
            }
        }
        System.out.println("GCD: " + gcd);
    }
}
```

Output:

`GCD: 14`

### 129. 使用循环计算两个数的最小公倍数 (LCM)

```java
public class LCMLoop {
    public static void main(String[] args) {
        int num1 = 12;
        int num2 = 15;
        int lcm = (num1 > num2) ? num1 : num2;
        while (true) {
            if (lcm % num1 == 0 && lcm % num2 == 0) {
                System.out.println("LCM: " + lcm);
                break;
            }
            lcm++;
        }
    }
}
```

Output:

`LCM: 60`

### 130. 找出数组中的最大值和最小值

```java
public class MaxMinInArray {
    public static void main(String[] args) {
        int[] array = {5, 3, 9, 1, 6};
        int max = array[0];
        int min = array[0];
        for (int num : array) {
            if (num > max) {
                max = num;
            }
            if (num < min) {
                min = num;
            }
        }
        System.out.println("Maximum value: " + max);
        System.out.println("Minimum value: " + min);
    }
}
```

Output:

`Maximum value: 9`

`Minimum value: 1`

### 131. 计算矩形的周长

```java
public class PerimeterOfRectangle {
    public static void main(String[] args) {
        int length = 10;
        int breadth = 5;
        int perimeter = 2 * (length + breadth);
        System.out.println("Perimeter of rectangle: " + perimeter);
    }
}
```

Output:

`Perimeter of rectangle: 30`

### 132. 不使用临时变量交换两个数

```java
public class SwapNumbers {
    public static void main(String[] args) {
        int a = 5, b = 3;
        System.out.println("Before swap: a = " + a + ", b = " + b);
        a = a + b;
        b = a - b;
        a = a - b;
        System.out.println("After swap: a = " + a + ", b = " + b);
    }
}
```

Output:

`Before swap: a = 5, b = 3`

`After swap: a = 3, b = 5`

### 133. 找出数组中的第二小的数

```java
import java.util.Arrays;
public class SecondSmallestNumber {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5, 6};
        Arrays.sort(array);
        System.out.println("Second smallest number: " + array[1]);
    }
}
```

Output:

`Second smallest number: 2`

### 134. 获取字符串的长度

```java
public class LengthOfString {
    public static void main(String[] args) {
        String str = "Hello, world!";
        System.out.println("Length: " + str.length());
    }
}
```

Output:

`Length: 13`

### 135. 统计字符串中的单词数

```java
public class WordCount {
    public static void main(String[] args) {
        String str = "Java is fun to learn";
        String[] words = str.split(" ");
        System.out.println("Number of words: " + words.length);
    }
}
```

Output:

`Number of words: 5`

### 136. 计算数字的平方根

```java
public class SquareRoot {
    public static void main(String[] args) {
        int num = 16;
        double sqrt = Math.sqrt(num);
        System.out.println("Square root of " + num + " is: " + sqrt);
    }
}
```

Output:

`Square root of 16 is: 4.0`

### 137. 将字符串转换为大写

```java
public class StringToUppercase {
    public static void main(String[] args) {
        String str = "hello world";
        String upperStr = str.toUpperCase();
        System.out.println("Uppercase string: " + upperStr);
    }
}
```

Output:

`Uppercase string: HELLO WORLD`

### 138. 将字符串转换为小写

```java
public class StringToLowercase {
    public static void main(String[] args) {
        String str = "HELLO WORLD";
        String lowerStr = str.toLowerCase();
        System.out.println("Lowercase string: " + lowerStr);
    }
}
```

Output:

`Lowercase string: hello world`

### 139. 使用循环反转字符串



```java
public class ReverseStringLoop {
    public static void main(String[] args) {
        String str = "Java";
        String reversed = "";
        for (int i = str.length() - 1; i >= 0; i--) {
            reversed += str.charAt(i);
        }
        System.out.println("Reversed string: " + reversed);
    }
}
```

Output:

`Reversed string: avaJ`

### 140. 使用递归计算数字的阶乘

```java
public class FactorialRecursion {
    public static void main(String[] args) {
        int num = 5;
        int result = factorial(num);
        System.out.println("Factorial of " + num + " is: " + result);
    }

    public static int factorial(int num) {
        if (num == 0) {
            return 1;
        }
        return num * factorial(num - 1);
    }
}
```

Output:

`Factorial of 5 is: 120`

### 141. 统计字符串中每个字符出现的频率

```java
import java.util.HashMap;

public class CharacterFrequency {
    public static void main(String[] args) {
        String str = "hello world";
        HashMap<Character, Integer> freqMap = new HashMap<>();
        for (char c : str.toCharArray()) {
            freqMap.put(c, freqMap.getOrDefault(c, 0) + 1);
        }
        for (char c : freqMap.keySet()) {
            System.out.println(c + ": " + freqMap.get(c));
        }
    }
}
```

Output:

`h: 1`

`e: 1`

`l: 3`

`o: 2`

` : 1`

`w: 1`

`r: 1`

`d: 1`

### 142. 找出字符串中第一个未出现的字符

```java
import java.util.LinkedHashMap;
import java.util.Map;

public class FirstNonRepeatedCharacter {
    public static void main(String[] args) {
        String str = "swiss";
        LinkedHashMap<Character, Integer> charCount = new LinkedHashMap<>();
        for (char c : str.toCharArray()) {
            charCount.put(c, charCount.getOrDefault(c, 0) + 1);
        }
        for (Map.Entry<Character, Integer> entry : charCount.entrySet()) {
            if (entry.getValue() == 1) {
                System.out.println("First non-repeated character: " + entry.getKey());
                break;
            }
        }
    }
}
```

Output:

`First non-repeated character: w`

### 143. 生成前 N 项斐波那契数列

```java
public class FibonacciSeries {
    public static void main(String[] args) {
        int n = 10;
        int a = 0, b = 1;
        System.out.print("Fibonacci series: " + a + ", " + b);
        for (int i = 2; i < n; i++) {
            int next = a + b;
            System.out.print(", " + next);
            a = b;
            b = next;
        }
    }
}
```

Output:

`Fibonacci series: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34`

### 144. 使用递归查找第 N 个斐波那契数

```java
public class NthFibonacci {
    public static void main(String[] args) {
        int n = 7;
        System.out.println("Nth Fibonacci number: " + fibonacci(n));
    }

    public static int fibonacci(int n) {
        if (n <= 1) {
            return n;
        }
        return fibonacci(n - 1) + fibonacci(n - 2);
    }
}
```

Output:

`Nth Fibonacci number: 13`

### 145. 去除数组中的重复

```java
import java.util.HashSet;

public class RemoveDuplicates {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 1, 2, 4, 5};
        HashSet<Integer> set = new HashSet<>();
        for (int num : array) {
            set.add(num);
        }
        System.out.println("Array after removing duplicates: " + set);
    }
}
```

Output:

`Array after removing duplicates: [1, 2, 3, 4, 5]`

### 146. 检查两个字符串是否为字母异构词

```java
import java.util.Arrays;

public class AnagramCheck {
    public static void main(String[] args) {
        String str1 = "listen";
        String str2 = "silent";
        char[] array1 = str1.toCharArray();
        char[] array2 = str2.toCharArray();
        Arrays.sort(array1);
        Arrays.sort(array2);
        if (Arrays.equals(array1, array2)) {
            System.out.println("The strings are anagrams.");
        } else {
            System.out.println("The strings are not anagrams.");
        }
    }
}
```

```java
if (isAnagram(str1, str2)) {
    System.out.println(str1 + " and " + str2 + " are anagrams.");
} else {
    System.out.println(str1 + " and " + str2 + " are not anagrams.");
}
}

public static boolean isAnagram(String str1, String str2) {
    char[] arr1 = str1.toCharArray();
    char[] arr2 = str2.toCharArray();
    Arrays.sort(arr1);
    Arrays.sort(arr2);
    return Arrays.equals(arr1, arr2);
}
```

输出:

`listen and silent are anagrams.`

### 147. 反转句子中的单词

```java
public class ReverseWords {
    public static void main(String[] args) {
        String sentence = "Java is fun";
        String[] words = sentence.split(" ");
        StringBuilder reversedSentence = new StringBuilder();
        for (int i = words.length - 1; i >= 0; i--) {
            reversedSentence.append(words[i]).append(" ");
        }
        System.out.println("Reversed sentence: " + reversedSentence.toString().trim());
    }
}
```

输出:

`Reversed sentence: fun is Java`

### 148. 检查字符串是否是另一个字符串的子字符串

```java
public class SubstringCheck {
    public static void main(String[] args) {
        String str1 = "hello";
        String str2 = "ell";
        if (str1.contains(str2)) {
            System.out.println(str2 + " is a substring of " + str1);
        } else {
            System.out.println(str2 + " is not a substring of " + str1);
        }
    }
}
```

输出:

`ell is a substring of hello`

### 149. Find 矩阵对角线元素之和

```java
public class DiagonalSum {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        int sum = 0;
        for (int i = 0; i < matrix.length; i++) {
            sum += matrix[i][i];
        }
        System.out.println("Sum of diagonal elements: " + sum);
    }
}
```

输出:

`Sum of diagonal elements: 15`

### 150. 矩阵矩阵每行之和

```java
public class RowSum {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        for (int i = 0; i < matrix.length; i++) {
            int sum = 0;
            for (int j = 0; j < matrix[i].length; j++) {
                sum += matrix[i][j];
            }
            System.out.println("Sum of row " + (i + 1) + ": " + sum);
        }
    }
}
```

输出:

`Sum of row 1: 6`

`Sum of row 2: 15`

`Sum of row 3: 24`

### 151. 矩阵矩阵每列之和

```java
public class ColumnSum {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        for (int i = 0; i < matrix[0].length; i++) {
            int sum = 0;
            for (int j = 0; j < matrix.length; j++) {
                sum += matrix[j][i];
            }
            System.out.println("Sum of column " + (i + 1) + ": " + sum);
        }
    }
}
```

输出:

`Sum of column 1: 12`

`Sum of column 2: 15`

`Sum of column 3: 18`

### 152. 检查矩阵是否为对称矩阵

```java
public class SymmetricMatrix {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {2, 5, 6},
            {3, 6, 9}
        };
        boolean isSymmetric = true;
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[0].length; j++) {
                if (matrix[i][j] != matrix[j][i]) {
                    isSymmetric = false;
                    break;
                }
            }
        }
        if (isSymmetric) {
            System.out.println("The matrix is symmetric.");
        } else {
            System.out.println("The matrix is not symmetric.");
        }
    }
}
```

输出:

`The matrix is symmetric.`

### 153. Find 矩阵的迹（Trace）

```java
public class MatrixTrace {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        int trace = 0;
        for (int i = 0; i < matrix.length; i++) {
            trace += matrix[i][i];
        }
        System.out.println("Trace of the matrix: " + trace);
    }
}
```

输出:

`Trace of the matrix: 15`

### 154. 矩阵顺时针旋转 90 度



```java
public class RotateMatrix {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        int n = matrix.length;
        int[][] rotatedMatrix = new int[n][n];
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                rotatedMatrix[j][n - 1 - i] = matrix[i][j];
            }
        }
        System.out.println("Rotated matrix:");
        for (int[] row : rotatedMatrix) {
            for (int val : row) {
                System.out.print(val + " ");
            }
            System.out.println();
        }
    }
}
```

输出：

`Rotated matrix:`

`7 4 1`

`8 5 2`

`9 6 3`

## 155. 打印杨辉三角

```java
public class PascalTriangle {
    public static void main(String[] args) {
        int n = 5;
        int[][] triangle = new int[n][n];
        for (int i = 0; i < n; i++) {
            for (int j = 0; j <= i; j++) {
                if (j == 0 || j == i) {
                    triangle[i][j] = 1;
                } else {
                    triangle[i][j] = triangle[i - 1][j - 1] + triangle[i - 1][j];
                }
                System.out.print(triangle[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

输出：

`1 `

`1 1 `

`1 2 1 `

`1 3 3 1 `

`1 4 6 4 1 `

## 156. 使用欧几里得算法 Find 两个数的最大公约数 (GCD)

```java
public class EuclideanGCD {
    public static void main(String[] args) {
        int num1 = 56;
        int num2 = 98;
        System.out.println("GCD of " + num1 + " and " + num2 + " is: " + gcd(num1, num2));
    }

    public static int gcd(int a, int b) {
        if (b == 0) {
            return a;
        }
        return gcd(b, a % b);
    }
}
```

输出：

`GCD of 56 and 98 is: 14`

## 157. 实现冒泡排序算法

```java
import java.util.Arrays;

public class BubbleSort {
    public static void main(String[] args) {
        int[] array = {64, 34, 25, 12, 22, 11, 90};
        for (int i = 0; i < array.length - 1; i++) {
            for (int j = 0; j < array.length - i - 1; j++) {
                if (array[j] > array[j + 1]) {
                    int temp = array[j];
                    array[j] = array[j + 1];
                    array[j + 1] = temp;
                }
            }
        }
        System.out.println("Sorted array: " + Arrays.toString(array));
    }
}
```

输出：

`Sorted array: [11, 12, 22, 25, 34, 64, 90]`

## 158. 实现选择排序算法

```java
import java.util.Arrays;

public class SelectionSort {
    public static void main(String[] args) {
        int[] array = {64, 25, 12, 22, 11};
        for (int i = 0; i < array.length - 1; i++) {
            int minIndex = i;
            for (int j = i + 1; j < array.length; j++) {
                if (array[j] < array[minIndex]) {
                    minIndex = j;
                }
            }
            int temp = array[minIndex];
            array[minIndex] = array[i];
            array[i] = temp;
        }
        System.out.println("Sorted array: " + Arrays.toString(array));
    }
}
```

输出：

`Sorted array: [11, 12, 22, 25, 64]`

## 159. 实现插入排序算法

```java
import java.util.Arrays;

public class InsertionSort {
    public static void main(String[] args) {
        int[] array = {12, 11, 13, 5, 6};
        for (int i = 1; i < array.length; i++) {
            int key = array[i];
            int j = i - 1;
            while (j >= 0 && array[j] > key) {
                array[j + 1] = array[j];
                j--;
            }
            array[j + 1] = key;
        }
        System.out.println("Sorted array: " + Arrays.toString(array));
    }
}
```

输出：

`Sorted array: [5, 6, 11, 12, 13]`

## 160. 实现归并排序

```java
import java.util.Arrays;

public class MergeSort {
    public static void main(String[] args) {
        int[] array = {12, 11, 13, 5, 6, 7};
        mergeSort(array, 0, array.length - 1);
        System.out.println("Sorted array: " + Arrays.toString(array));
    }

    public static void mergeSort(int[] array, int left, int right) {
        if (left < right) {
            int mid = (left + right) / 2;
            mergeSort(array, left, mid);
            mergeSort(array, mid + 1, right);
            merge(array, left, mid, right);
        }
    }

    public static void merge(int[] array, int left, int mid, int right) {
        int n1 = mid - left + 1;
        int n2 = right - mid;
        int[] leftArray = new int[n1];
        int[] rightArray = new int[n2];

        for (int i = 0; i < n1; i++) {
            leftArray[i] = array[left + i];
        }

        for (int j = 0; j < n2; j++) {
            rightArray[j] = array[mid + 1 + j];
        }

        int i = 0;
        int j = 0;
        int k = left;

        while (i < n1 && j < n2) {
            if (leftArray[i] <= rightArray[j]) {
                array[k] = leftArray[i];
                i++;
            } else {
                array[k] = rightArray[j];
                j++;
            }
            k++;
        }

        while (i < n1) {
            array[k] = leftArray[i];
            i++;
            k++;
        }

        while (j < n2) {
            array[k] = rightArray[j];
            j++;
            k++;
        }
    }
}
```

输出：

`Sorted array: [5, 6, 7, 11, 12, 13]`

## 161. 实现快速排序算法

```java
import java.util.Arrays;

public class QuickSort {
    public static void main(String[] args) {
        int[] array = {10, 7, 8, 9, 1, 5};
        quickSort(array, 0, array.length - 1);
        System.out.println("Sorted array: " + Arrays.toString(array));
    }

    public static void quickSort(int[] array, int low, int high) {
        if (low < high) {
            int pi = partition(array, low, high);
            quickSort(array, low, pi - 1);
            quickSort(array, pi + 1, high);
        }
    }

    private static int partition(int[] array, int low, int high) {
        int pivot = array[high];
        int i = (low - 1);

        for (int j = low; j < high; j++) {
            if (array[j] < pivot) {
                i++;
                int temp = array[i];
                array[i] = array[j];
                array[j] = temp;
            }
        }

        int temp = array[i + 1];
        array[i + 1] = array[high];
        array[high] = temp;
        return i + 1;
    }
}
```

输出：

`Sorted array: [1, 5, 7, 8, 9, 10]`

```java
public static int partition(int[] array, int low, int high) {
    int pivot = array[high];
    int i = (low - 1);

    for (int j = low; j < high; j++) {
        if (array[j] < pivot) {
            i++;
            int temp = array[i];
            array[i] = array[j];
            array[j] = temp;
        }
    }

    int temp = array[i + 1];
    array[i + 1] = array[high];
    array[high] = temp;
    return i + 1;
}
```

输出：

排序后的数组: [1, 5, 7, 8, 9, 10]

## 162. 实现二分查找算法

```java
public class BinarySearch {
    public static void main(String[] args) {
        int[] array = {2, 3, 4, 10, 40};
        int target = 10;
        int result = binarySearch(array, 0, array.length - 1, target);

        if (result == -1) {
            System.out.println("元素不存在");
        } else {
            System.out.println("找到元素，索引为: " + result);
        }
    }

    public static int binarySearch(int[] array, int left, int right, int target) {
        if (right >= left) {
            int mid = left + (right - left) / 2;

            if (array[mid] == target) {
                return mid;
            }

            if (array[mid] > target) {
                return binarySearch(array, left, mid - 1, target);
            }

            return binarySearch(array, mid + 1, right, target);
        }

        return -1;
    }
}
```

输出：

找到元素，索引为: 3

## 163. 检查数组是否按升序排序



```java
public class CheckSortedArray {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5};
        boolean isSorted = true;
        for (int i = 1; i < array.length; i++) {
            if (array[i] < array[i - 1]) {
                isSorted = false;
                break;
            }
        }
        if (isSorted) {
            System.out.println("数组是升序排列的.");
        } else {
            System.out.println("数组不是升序的.");
        }
    }
}
```

输出：

数组是升序排列的。

## 164. 寻找数组的中位数

```java
import java.util.Arrays;

public class FindMedian {
    public static void main(String[] args) {
        int[] array = {1, 3, 4, 2, 5};
        Arrays.sort(array);
        double median;
        int middle = array.length / 2;
        if (array.length % 2 == 0) {
            median = ((double)array[middle - 1] + array[middle]) / 2;
        } else {
            median = array[middle];
        }
        System.out.println("中位数: " + median);
    }
}
```

输出：

中位数: 3.0

## 165. 统计字符串中元音和辅音的数量

```java
public class CountVowelsConsonants {
    public static void main(String[] args) {
        String str = "hello world";
        int vowels = 0, consonants = 0;
        for (char c : str.toCharArray()) {
            if (Character.isLetter(c)) {
                c = Character.toLowerCase(c);
                if (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u') {
                    vowels++;
                } else {
                    consonants++;
                }
            }
        }
        System.out.println("元音: " + vowels);
        System.out.println("辅音: " + consonants);
    }
}
```

输出：

元音: 3

辅音: 7

## 166. 十进制数转换为二进制

```java
public class DecimalToBinary {
    public static void main(String[] args) {
        int num = 10;
        String binary = "";
        while (num > 0) {
            binary = (num % 2) + binary;
            num = num / 2;
        }
        System.out.println("二进制: " + binary);
    }
}
```

输出：

二进制: 1010

## 167. 二进制数转换为十进制

```java
public class BinaryToDecimal {
    public static void main(String[] args) {
        String binary = "1010";
        int decimal = Integer.parseInt(binary, 2);
        System.out.println("十进制: " + decimal);
    }
}
```

输出：

十进制: 10

## 168. 检查数字是否为回文

```java
public class PalindromeNumber {
    public static void main(String[] args) {
        int num = 121;
        int originalNum = num;
        int reversedNum = 0;
        while (num != 0) {
            int digit = num % 10;
            reversedNum = reversedNum * 10 + digit;
            num /= 10;
        }
        if (originalNum == reversedNum) {
            System.out.println(originalNum + " 是回文.");
        } else {
            System.out.println(originalNum + "不是回文.");
        }
    }
}
```

输出：

121 是回文。

## 169. 检查字符串是否为回文

```java
public class PalindromeString {
    public static void main(String[] args) {
        String str = "madam";
        String reversedStr = new StringBuilder(str).reverse().toString();
        if (str.equals(reversedStr)) {
            System.out.println(str + " 是回文.");
        } else {
            System.out.println(str + "不是回文.");
        }
    }
}
```

输出：

madam 是回文。

## 170. 寻找数组中的最大元素

```java
public class LargestElement {
    public static void main(String[] args) {
        int[] array = {10, 20, 30, 5, 15};
        int max = array[0];
        for (int i = 1; i < array.length; i++) {
            if (array[i] > max) {
                max = array[i];
            }
        }
        System.out.println("最大元素: " + max);
    }
}
```

输出：

最大元素: 30

## 171. 寻找数组中的最小元素

```java
public class SmallestElement {
    public static void main(String[] args) {
        int[] array = {10, 20, 30, 5, 15};
        int min = array[0];
        for (int i = 1; i < array.length; i++) {
            if (array[i] < min) {
                min = array[i];
            }
        }
        System.out.println("最小元素: " + min);
    }
}
```

输出：

最小元素: 5

## 172. 反转数组

```java
import java.util.Arrays;

public class ReverseArray {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5};
        int n = array.length;
        for (int i = 0; i < n / 2; i++) {
            int temp = array[i];
            array[i] = array[n - i - 1];
            array[n - i - 1] = temp;
        }
        System.out.println("反转后的数组: " + Arrays.toString(array));
    }
}
```

输出：

反转后的数组: [5, 4, 3, 2, 1]

## 173. 矩阵对角线之和

```java
public class SumOfDiagonals {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        int primaryDiagonalSum = 0;
        int secondaryDiagonalSum = 0;
        for (int i = 0; i < matrix.length; i++) {
            primaryDiagonalSum += matrix[i][i];
            secondaryDiagonalSum += matrix[i][matrix.length - i - 1];
        }
        System.out.println("主对角线和: " + primaryDiagonalSum);
        System.out.println("副对角线和: " + secondaryDiagonalSum);
    }
}
```

输出：

主对角线和: 15

副对角线和: 15

## 174. 寻找数组中的第二大元素

```java
public class SecondLargestElement {
    public static void main(String[] args) {
        int[] array = {10, 20, 30, 5, 15};
        int firstLargest = Integer.MIN_VALUE;
        int secondLargest = Integer.MIN_VALUE;
        for (int i = 0; i < array.length; i++) {
            if (array[i] > firstLargest) {
                secondLargest = firstLargest;
                firstLargest = array[i];
            } else if (array[i] > secondLargest && array[i] != firstLargest) {
                secondLargest = array[i];
            }
        }
        System.out.println("第二大元素: " + secondLargest);
    }
}
```

输出：

第二大元素: 20

## 175. 查找数组中每个元素的频率

```java
import java.util.HashMap;
import java.util.Map;

public class FrequencyOfElements {
    public static void main(String[] args) {
        int[] array = {1, 2, 2, 3, 3, 3, 4};
        Map<Integer, Integer> frequencyMap = new HashMap<>();
        for (int num : array) {
            frequencyMap.put(num, frequencyMap.getOrDefault(num, 0) + 1);
        }
        System.out.println("元素频率: " + frequencyMap);
    }
}
```

输出：

元素频率: {1=1, 2=2, 3=3, 4=1}

## 179. 检查两个字符串是否为字母异位词

```java
import java.util.Arrays;

public class AnagramCheck {
    public static void main(String[] args) {
        String str1 = "listen";
        String str2 = "silent";
        char[] arr1 = str1.toCharArray();
        char[] arr2 = str2.toCharArray();
        Arrays.sort(arr1);
        Arrays.sort(arr2);
        if (Arrays.equals(arr1, arr2)) {
            System.out.println(str1 + " and " + str2 + " are anagrams.");
        } else {
            System.out.println(str1 + " and " + str2 + " are not anagrams.");
        }
    }
}
```

输出：

`listen and silent are anagrams.`

## 180. 计算数字的幂

```java
public class PowerCalculation {
    public static void main(String[] args) {
        int base = 2;
        int exponent = 3;
        int result = 1;
        for (int i = 0; i < exponent; i++) {
            result *= base;
        }
        System.out.println(base + " to the power of " + exponent + " is: " + result);
    }
}
```

输出：

`2 to the power of 3 is: 8`

## 181. 实现一个简单的计算器



```java
import java.util.Scanner;

public class SimpleCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Enter first number: ");
        double num1 = scanner.nextDouble();
        System.out.println("Enter second number: ");
        double num2 = scanner.nextDouble();
        System.out.println("Choose an operation (+, -, *, /): ");
        char operation = scanner.next().charAt(0);
        double result;
        switch (operation) {
            case '+':
                result = num1 + num2;
                break;
            case '-':
                result = num1 - num2;
                break;
            case '*':
                result = num1 * num2;
                break;
            case '/':
                result = num1 / num2;
                break;
            default:
                System.out.println("Invalid operation");
                return;
        }
        System.out.println("Result: " + result);
    }
}
```

**Output:**

`Enter first number: 10 Enter second number: 5 Choose an operation (+, -, *, /): + Result: 15.0`

## 182. 打印前 N 项斐波那契数列

```java
public class FibonacciSeries {
    public static void main(String[] args) {
        int n = 10;
        int a = 0, b = 1;
        System.out.print("Fibonacci Series up to " + n + " terms: ");
        for (int i = 0; i < n; i++) {
            System.out.print(a + " ");
            int next = a + b;
            a = b;
            b = next;
        }
    }
}
```

**Output:**

`Fibonacci Series up to 10 terms: 0 1 1 2 3 5 8 13 21 34`

## 183. 统计字符串中的单词数

```java
public class CountWords {
    public static void main(String[] args) {
        String str = "This is a simple sentence.";
        String[] words = str.split("\\s+");
        System.out.println("Number of words: " + words.length);
    }
}
```

**Output:**

`Number of words: 5`

## 184. 计算 1 到 N 所有奇数的之和

```java
public class SumOfOdds {
    public static void main(String[] args) {
        int n = 10;
        int sum = 0;
        for (int i = 1; i <= n; i += 2) {
            sum += i;
        }
        System.out.println("Sum of odd numbers from 1 to " + n + " is: " + sum);
    }
}
```

**Output:**

`Sum of odd numbers from 1 to 10 is: 25`

## 185. 计算 1 到 N 所有偶数的之和

```java
public class SumOfEvens {
    public static void main(String[] args) {
        int n = 10;
        int sum = 0;
        for (int i = 2; i <= n; i += 2) {
            sum += i;
        }
        System.out.println("Sum of even numbers from 1 to " + n + " is: " + sum);
    }
}
```

**Output:**

`Sum of even numbers from 1 to 10 is: 30`

## 186. 统计字符串中的元音个数

```java
public class CountVowelsInString {
    public static void main(String[] args) {
        String str = "Hello World";
        int vowelCount = 0;
        for (char c : str.toLowerCase().toCharArray()) {
            if (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u') {
                vowelCount++;
            }
        }
        System.out.println("Number of vowels: " + vowelCount);
    }
}
```

**Output:**

`Number of vowels: 3`

## 187. 生成 1 到 100 之间的随机数

```java
import java.util.Random;

public class RandomNumber {
    public static void main(String[] args) {
        Random rand = new Random();
        int randomNumber = rand.nextInt(100) + 1; // 生成一个 1 到 100 之间的随机数字
        System.out.println("Random number between 1 and 100: " + randomNumber);
    }
}
```

**Output (example):**

`Random number between 1 and 100: 42`

## 188. 整数的位数

```java
public class CountDigits {
    public static void main(String[] args) {
        int num = 123456;
        int count = 0;
        while (num != 0) {
            num /= 10;
            count++;
        }
        System.out.println("Number of digits: " + count);
    }
}
```

**Output:**

`Number of digits: 6`

## 189. 打印直角三角形

```java
public class RightAngleTriangle {
    public static void main(String[] args) {
        int rows = 5;
        for (int i = 1; i <= rows; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print("* ");
            }
            System.out.println();
        }
    }
}
```

**Output:**

```
* 
* * 
* * * 
* * * * 
* * * * * 
```

## 190. 打印金字塔图案

```java
public class PyramidPattern {
    public static void main(String[] args) {
        int rows = 5;
        for (int i = 1; i <= rows; i++) {
            for (int j = 1; j <= rows - i; j++) {
                System.out.print(" ");
            }
            for (int k = 1; k <= 2 * i - 1; k++) {
                System.out.print("*");
            }
            System.out.println();
        }
    }
}
```

**Output:**

```
     *
    ***
   *****
 *******
*********
```

## 191. 打印菱形图案

```java
public class DiamondPattern {
    public static void main(String[] args) {
        int n = 5;
        // 上半部分
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n - i; j++) {
                System.out.print(" ");
            }
            for (int k = 1; k <= 2 * i - 1; k++) {
                System.out.print("*");
            }
            System.out.println();
        }
        // 下半部分
        for (int i = n - 1; i >= 1; i--) {
            for (int j = 1; j <= n - i; j++) {
                System.out.print(" ");
            }
            for (int k = 1; k <= 2 * i - 1; k++) {
                System.out.print("*");
            }
            System.out.println();
        }
    }
}
```

**Output:**

```
     *
    ***
   *****
  *******
*********
  *******
   *****
    ***
     *
```

## 192. 打印给定数字的九九乘表乘法表

```java
public class MultiplicationTable {
    public static void main(String[] args) {
        int number = 5;
        for (int i = 1; i <= 10; i++) {
            System.out.println(number + " x " + i + " = " + (number * i));
        }
    }
}
```

**Output:**

`5 x 1 = 5`

`5 x 2 = 10`

`5 x 3 = 15`

`5 x 4 = 20`

`5 x 5 = 25`

`5 x 6 = 30`

`5 x 7 = 35`

`5 x 8 = 40`

`5 x 9 = 45`

`5 x 10 = 50`

## 193. 检查一个数字是否为质数

```java
public class PrimeCheck {
    public static void main(String[] args) {
        int num = 29;
        boolean isPrime = true;
        if (num <= 1) {
            isPrime = false;
        } else {
            for (int i = 2; i <= Math.sqrt(num); i++) {
                if (num % i == 0) {
                    isPrime = false;
                    break;
                }
            }
        }
        if (isPrime) {
            System.out.println(num + " is a prime number.");
        } else {
            System.out.println(num + " is not a prime number.");
        }
    }
}
```

**Output:**

`29 is a prime number.`

## 194. 计算一个数字的阶乘

```java
public class Factorial {
    public static void main(String[] args) {
        int num = 5;
        long factorial = 1;
        for (int i = 1; i <= num; i++) {
            factorial *= i;
        }
        System.out.println("Factorial of " + num + " is: " + factorial);
    }
}
```

**Output:**

`Factorial of 5 is: 120`

## 195. 计算 1 到 N 的自然数之和

```java
public class SumOfNaturalNumbers {
    public static void main(String[] args) {
        int n = 10;
        int sum = n * (n + 1) / 2;
        System.out.println("Sum of natural numbers up to " + n + " is: " + sum);
    }
}
```

**Output:**

`Sum of natural numbers up to 10 is: 55`

## 196. 使用递归打印斐波那契数列

```java
public class FibonacciRecursion {
    public static void main(String[] args) {
        int n = 10;
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

**Output:**

`0 1 1 2 3 5 8 13 21 34 `

## 197. 求一个数字各位位之和

```java
public class SumOfDigits {
    public static void main(String[] args) {
        int num = 12345;
        int sum = 0;
        while (num != 0) {
            sum += num % 10;
            num /= 10;
        }
        System.out.println("Sum of digits: " + sum);
    }
}
```

**Output:**



`Sum of digits: 15`

### 198. 检查一个数字是偶数还是奇数

```java
public class EvenOddCheck {
    public static void main(String[] args) {
        int num = 7;
        if (num % 2 == 0) {
            System.out.println(num + " is even.");
        } else {
            System.out.println(num + " is odd.");
        }
    }
}
```

Output:

`7 is odd.`

### 199. 统计字符串中的空格个数

```java
public class CountSpaces {
    public static void main(String[] args) {
        String str = "Count the number of spaces";
        int spaceCount = 0;
    }
}
```

```java
for (char c : str.toCharArray()) {
    if (c == ' ') {
        spaceCount++;
    }
}
System.out.println("Number of spaces: " + spaceCount);
}
```

Output:

空格数量: 4

### 200. 寻找两个数组之间的公共元素

```java
import java.util.HashSet;
import java.util.Set;

public class CommonElements {
    public static void main(String[] args) {
        int[] array1 = {1, 2, 3, 4, 5};
        int[] array2 = {4, 5, 6, 7, 8};
        Set<Integer> set1 = new HashSet<>();
        for (int num : array1) {
            set1.add(num);
        }
        System.out.print("Common elements: ");
        for (int num : array2) {
            if (set1.contains(num)) {
                System.out.print(num + " ");
            }
        }
    }
}
```

Output:

公共元素: 4 5

### 201. 二进制转换为十进制

```java
public class BinaryToDecimal {
    public static void main(String[] args) {
        String binary = "1101";
        int decimal = Integer.parseInt(binary, 2);
        System.out.println("Binary " + binary + " in decimal is: " + decimal);
    }
}
```

Output:

二进制 1101 转换为十进制为: 13

### 202. 十进制转换为二进制

```java
public class DecimalToBinary {
    public static void main(String[] args) {
        int decimal = 13;
        String binary = Integer.toBinaryString(decimal);
        System.out.println("Decimal " + decimal + " in binary is: " + binary);
    }
}
```

Output:

十进制 13 转换为二进制为: 1101

### 203. 不使用临时变量交换两个数字

```java
public class SwapWithoutTemp {
    public static void main(String[] args) {
        int a = 5;
        int b = 10;
        a = a + b;
        b = a - b;
        a = a - b;
        System.out.println("After swapping: a = " + a + ", b = " + b);
    }
}
```

Output:

交换后: a = 10, b = 5

### 204. 检查一个数字是否为阿姆斯特数

```java
public class ArmstrongNumber {
    public static void main(String[] args) {
        int num = 153;
        int originalNum = num;
        int result = 0;
        while (originalNum != 0) {
            int digit = originalNum % 10;
            result += Math.pow(digit, 3);
            originalNum /= 10;
        }
        if (result == num) {
            System.out.println(num + " is an Armstrong number.");
        } else {
            System.out.println(num + " is not an Armstrong number.");
        }
    }
}
```

Output:

153 是阿姆斯特数。

### 205. 检查一个数字是否为完美数

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

Output:

28 是完美数。

### 206. 检查字符串是否为回文（忽略大小写）

```java
public class PalindromeIgnoreCase {
    public static void main(String[] args) {
        String str = "Madam";
        String lowerStr = str.toLowerCase();
        String reversedStr = new StringBuilder(lowerStr).reverse().toString();
        if (lowerStr.equals(reversedStr)) {
            System.out.println(str + " is a palindrome.");
        } else {
            System.out.println(str + " is not a palindrome.");
        }
    }
}
```

Output:

Madam 是回文。

### 207. 找到到 N 的所有质数的之和

```java
public class SumOfPrimes {
    public static void main(String[] args) {
        int n = 10;
        int sum = 0;
        for (int i = 2; i <= n; i++) {
            if (isPrime(i)) {
                sum += i;
            }
        }
        System.out.println("Sum of prime numbers up to " + n + " is: " + sum);
    }

    public static boolean isPrime(int num) {
        if (num <= 1) {
            return false;
        }
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) {
                return false;
            }
        }
        return true;
    }
}
```

Output:

到 10 的质数之和为: 17

### 208. 寻找两个数字的最大公约数

```java
public class GCD {
    public static void main(String[] args) {
        int num1 = 56;
        int num2 = 98;
        int gcd = 1;
        for (int i = 1; i <= num1 && i <= num2; i++) {
            if (num1 % i == 0 && num2 % i == 0) {
                gcd = i;
            }
        }
        System.out.println("GCD of " + num1 + " and " + num2 + " is: " + gcd);
    }
}
```

Output:

56 和 98 的最大公约数是: 14

### 209. 寻找两个数字的最小公倍数

```java
public class LCM {
    public static void main(String[] args) {
        int num1 = 72;
        int num2 = 120;
        int lcm = num1;
        while (true) {
            if (lcm % num1 == 0 && lcm % num2 == 0) {
                System.out.println("LCM of " + num1 + " and " + num2 + " is: " + lcm);
                break;
            }
            lcm++;
        }
    }
}
```

Output:

72 和 120 的最小公倍数是: 360

### 210. 摄氏度转换为华华度

```java
public class CelsiusToFahrenheit {
    public static void main(String[] args) {
        double celsius = 25.0;
        double fahrenheit = (celsius * 9/5) + 32;
        System.out.println(celsius + "°C is equal to " + fahrenheit + "°F");
    }
}
```

Output:

25.0°C 等于 77.0°F

### 211. 华华度转换为摄氏度

```java
public class FahrenheitToCelsius {
    public static void main(String[] args) {
        double fahrenheit = 77.0;
        double celsius = (fahrenheit - 32) * 5/9;
        System.out.println(fahrenheit + "°F is equal to " + celsius + "°C");
    }
}
```

Output:

77.0°F 等于 25.0°C

### 212. 统计字符串中的元音数量

```java
public class CountConsants {
    public static void main(String[] args) {
        String str = "Hello World";
        int consonantCount = 0;
        for (char c : str.toLowerCase().toCharArray()) {
            if ((c >= 'a' && c <= 'z') && !(c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u')) {
                consonantCount++;
            }
        }
        System.out.println("Number of consonants: " + consonantCount);
    }
}
```

Output:

元音数量: 7

### 213. 使用递归寻找数字的阶乘

```java
public class FactorialRecursion {
    public static void main(String[] args) {
        int num = 5;
        System.out.println("Factorial of " + num + " is: " + factorial(num));
    }

    public static int factorial(int n) {
        if (n == 0) {
            return 1;
        } else {
            return n * factorial(n - 1);
        }
    }
}
```

Output:

5 的阶乘为: 120

### 214. 反转数字

```java
public class ReverseNumber {
    public static void main(String[] args) {
        int num = 12345;
        int reversed = 0;
        while (num != 0) {
            int digit = num % 10;
            reversed = reversed * 10 + digit;
            num /= 10;
        }
        System.out.println("Reversed number: " + reversed);
    }
}
```

Output:

反转后的数字: 54321

### 215. 寻找字符串中第一个未重复的字符

```java
import java.util.LinkedHashMap;
import java.util.Map;

public class FirstNonRepeatedCharacter {
    public static void main(String[] args) {
        String str = "swiss";
        Map<Character, Integer> charCountMap = new LinkedHashMap<>();
        for (char c : str.toCharArray()) {
            charCountMap.put(c, charCountMap.getOrDefault(c, 0) + 1);
        }
        for (Map.Entry<Character, Integer> entry : charCountMap.entrySet()) {
            if (entry.getValue() == 1) {
                System.out.println("First non-repeated character: " + entry.getKey());
                break;
            }
        }
    }
}
```

Output:

第一个未重复的字符: w

### 216. 使用 while 循环打印斐波那契序列



```java
public class FibonacciLoop {
    public static void main(String[] args) {
        int n = 10;
        int a = 0, b = 1;
        int count = 0;
        System.out.print("Fibonacci Series up to " + n + " terms: ");
        while (count < n) {
            System.out.print(a + " ");
            int next = a + b;
            a = b;
            b = next;
            count++;
        }
    }
}
```

Output:

斐波那契序列前 10 项: 0 1 1 2 3 5 8 13 21 34

## 217. 生成前 N 个质数

```java
public class FirstNPrimes {
    public static void main(String[] args) {
        int n = 5;
        int count = 0;
        int num = 2;
        while (count < n) {
            if (isPrime(num)) {
                System.out.print(num + " ");
                count++;
            }
            num++;
        }
    }

    public static boolean isPrime(int num) {
        if (num <= 1) {
            return false;
        }
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) {
                return false;
            }
        }
        return true;
    }
}
```

Output:

2 3 5 7 11

## 218. 寻找数组中的最大元素

```java
public class LargestElementInArray {
    public static void main(String[] args) {
        int[] array = {10, 25, 5, 50, 40};
        int largest = array[0];
        for (int num : array) {
            if (num > largest) {
                largest = num;
            }
        }
        System.out.println("Largest element in the array: " + largest);
    }
}
```

Output:

数组中的最大元素: 50

## 219. 寻找数组中的最小元素

```java
public class SmallestElementInArray {
    public static void main(String[] args) {
        int[] array = {10, 25, 5, 50, 40};
        int smallest = array[0];
        for (int num : array) {
            if (num < smallest) {
                smallest = num;
            }
        }
        System.out.println("Smallest element in the array: " + smallest);
    }
}
```

输出:

数组中的最小元素为: 5

## 220. 检查两个字符串是否为异位词

```java
import java.util.Arrays;

public class AnagramCheck {
    public static void main(String[] args) {
        String str1 = "listen";
        String str2 = "silent";
        char[] arr1 = str1.toCharArray();
        char[] arr2 = str2.toCharArray();
        Arrays.sort(arr1);
        Arrays.sort(arr2);
        if (Arrays.equals(arr1, arr2)) {
            System.out.println(str1 + " and " + str2 + " are anagrams.");
        } else {
            System.out.println(str1 + " and " + str2 + " are not anagrams.");
        }
    }
}
```

输出:

listen and silent are anagrams.

## 221. 使用循环计算数字的幂

```java
public class PowerOfNumber {
    public static void main(String[] args) {
        int base = 2;
        int exponent = 5;
        int result = 1;
        for (int i = 0; i < exponent; i++) {
            result *= base;
        }
        System.out.println(base + " raised to the power of " + exponent + " is: " + result);
    }
}
```

输出:

2 raised to the power of 5 is: 32

## 222. 找到数组中的第二大元素

```java
public class SecondLargestInArray {
    public static void main(String[] args) {
        int[] array = {10, 25, 5, 50, 40};
        int largest = Integer.MIN_VALUE;
        int secondLargest = Integer.MIN_VALUE;
        for (int num : array) {
            if (num > largest) {
                secondLargest = largest;
                largest = num;
            } else if (num > secondLargest && num != largest) {
                secondLargest = num;
            }
        }
        System.out.println("Second largest element in the array: " + secondLargest);
    }
}
```

输出:

数组中的第二大元素: 40

## 223. 找到数组中的第二小元素

```java
public class SecondSmallestInArray {
    public static void main(String[] args) {
        int[] array = {10, 25, 5, 50, 40};
        int smallest = Integer.MAX_VALUE;
        int secondSmallest = Integer.MAX_VALUE;
        for (int num : array) {
            if (num < smallest) {
                secondSmallest = smallest;
                smallest = num;
            } else if (num < secondSmallest && num != smallest) {
                secondSmallest = num;
            }
        }
        System.out.println("Second smallest element in the array: " + secondSmallest);
    }
}
```

输出:

数组中的第二最小元素: 10

## 224. 计算数组中元素的平均值

```java
public class AverageOfArray {
    public static void main(String[] args) {
        int[] array = {10, 25, 5, 50, 40};
        int sum = 0;
        for (int num : array) {
            sum += num;
        }
        double average = sum / (double) array.length;
        System.out.println("Average of elements in the array: " + average);
    }
}
```

输出:

数组中元素的平均值: 26.0

## 225. 找到数组中的最大值和最小值

```java
public class MaxMinArray {
    public static void main(String[] args) {
        int[] array = {10, 25, 5, 50, 40};
        int max = array[0];
        int min = array[0];
        for (int num : array) {
            if (num > max) {
                max = num;
            }
            if (num < min) {
                min = num;
            }
        }
        System.out.println("Maximum value: " + max);
        System.out.println("Minimum value: " + min);
    }
}
```

输出:

最大值: 50

最小值: 5

## 226. 找到二维数组每行的行和

```java
public class SumOfRows2DArray {
    public static void main(String[] args) {
        int[][] array = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        for (int i = 0; i < array.length; i++) {
            int sum = 0;
            for (int j = 0; j < array[i].length; j++) {
                sum += array[i][j];
            }
            System.out.println("Sum of row " + (i + 1) + ": " + sum);
        }
    }
}
```

输出:

第 1 行之和: 6

第 2 行之和: 15

第 3 行之和: 24

## 227. 找到二维数组每列的和

```java
public class SumOf2DArray {
    public static void main(String[] args) {
        int[][] array = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        for (int j = 0; j < array[0].length; j++) {
            int sum = 0;
            for (int i = 0; i < array.length; i++) {
                sum += array[i][j];
            }
            System.out.println("Sum of column " + (j + 1) + ": " + sum);
        }
    }
}
```

输出:

第 1 列之和: 12

第 2 列之和: 15

第 3 列之和: 18

## 228. 反转数组的元素

```java
import java.util.Arrays;

public class ReverseArray {
    public static void main(String[] args) {
        int[] array = {10, 25, 5, 50, 40};
        int n = array.length;
        for (int i = 0; i < n / 2; i++) {
            int temp = array[i];
            array[i] = array[n - 1 - i];
            array[n - 1 - i] = temp;
        }
        System.out.println("Reversed array: " + Arrays.toString(array));
    }
}
```

输出:

反转后的数组: [40, 50, 5, 25, 10]

## 229. 将两个数组合并为一个数组

```java
import java.util.Arrays;

public class MergeArrays {
    public static void main(String[] args) {
        int[] array1 = {1, 2, 3};
        int[] array2 = {4, 5, 6};
        int[] mergedArray = new int[array1.length + array2.length];
        System.arraycopy(array1, 0, mergedArray, 0, array1.length);
        System.arraycopy(array2, 0, mergedArray, array1.length, array2.length);
        System.out.println("Merged array: " + Arrays.toString(mergedArray));
    }
}
```

输出:

合并后的数组: [1, 2, 3, 4, 5, 6]

## 230. 数组向左移动一位

```java
import java.util.Arrays;

public class RotateLeft {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5};
        int first = array[0];
        for (int i = 0; i < array.length - 1; i++) {
            array[i] = array[i + 1];
        }
        array[array.length - 1] = first;
        System.out.println("Array after left rotation: " + Arrays.toString(array));
    }
}
```

输出:

左左移后的数组: [2, 3, 4, 5, 1]

## 231. 数组向右移动一位



```java
import java.util.Arrays;

public class RotateRight {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5};
        int last = array[array.length - 1];
        for (int i = array.length - 1; i > 0; i--) {
            array[i] = array[i - 1];
        }
        array[0] = last;
        System.out.println("Array after right rotation: " + Arrays.toString(array));
    }
}
```

输出：

右右移后的数组: [5, 1, 2, 3, 4]

## 232. 统计字符串中的单词数

```java
public class CountWords {
    public static void main(String[] args) {
        String str = "This is a sample string";
        String[] words = str.split("\\s+");
        System.out.println("Number of words: " + words.length);
    }
}
```

输出：

单词数: 5

## 233. 将字符转换为其 ASCII 值

```java
public class CharToASCII {
    public static void main(String[] args) {
        char c = 'A';
        int asciiValue = (int) c;
        System.out.println("ASCII value of " + c + " is: " + asciiValue);
    }
}
```

输出：

A 的 ASCII 值: 65

## 234. 不使用 `length()` 方法查找字符串长度

```java
public class StringLength {
    public static void main(String[] args) {
        String str = "Hello, World!";
        int length = 0;
        for (char c : str.toCharArray()) {
            length++;
        }
        System.out.println("Length of the string: " + length);
    }
}
```

输出：

字符串的长度: 13

## 235. 找到二维数组中元素的和

```java
public class Sum2DArray {
    public static void main(String[] args) {
        int[][] array = {
            {10, 25, 5},
            {50, 40, 30}
        };
        int sum = 0;
        for (int i = 0; i < array.length; i++) {
            for (int j = 0; j < array[i].length; j++) {
                sum += array[i][j];
            }
        }
        System.out.println("Sum of elements in 2D array: " + sum);
    }
}
```

输出：

二维数组中元素的和: 160

## 236. 转置二维矩阵

```java
import java.util.Arrays;

public class TransposeMatrix {
    public static void main(String[] args) {
        int[][] matrix = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        int[][] transpose = new int[matrix[0].length][matrix.length];
        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[0].length; j++) {
                transpose[j][i] = matrix[i][j];
            }
        }
        System.out.println("Original matrix:");
        for (int[] row : matrix) {
            System.out.println(Arrays.toString(row));
        }
        System.out.println("Transposed matrix:");
        for (int[] row : transpose) {
            System.out.println(Arrays.toString(row));
        }
    }
}
```

输出：

原始矩阵：

[1, 2, 3]

[4, 5, 6]

[7, 8, 9]

转置后的矩阵：

[1, 4, 7]

[2, 5, 8]

[3, 6, 9]

## 237. 两个矩阵相法

```java
import java.util.Arrays;

public class MultiplyMatrices {
    public static void main(String[] args) {
        int[][] matrix1 = {
            {1, 2, 3},
            {4, 5, 6}
        };
        int[][] matrix2 = {
            {7, 8},
            {9, 10},
            {11, 12}
        };
        int[][] result = new int[matrix1.length][matrix2[0].length];
        for (int i = 0; i < matrix1.length; i++) {
            for (int j = 0; j < matrix2[0].length; j++) {
                for (int k = 0; k < matrix1[0].length; k++) {
                    result[i][j] += matrix1[i][k] * matrix2[k][j];
                }
            }
        }
        System.out.println("Result matrix:");
        for (int[] row : result) {
            System.out.println(Arrays.toString(row));
        }
    }
}
```

输出：

结果矩阵：

[58, 64]

[139, 154]

```java
for (int j = 0; j < matrix2[0].length; j++) {
    for (int k = 0; k < matrix2.length; k++) {
        result[i][j] += matrix1[i][k] * matrix2[k][j];
    }
}
System.out.println("Resultant matrix:");
for (int[] row : result) {
    System.out.println(Arrays.toString(row));
}
```

**输出：**

结果性矩阵：

[58, 64]

[139, 154]

## 238. 统计字符串中的元音数量

```java
public class VowelCount {
    public static void main(String[] args) {
        String str = "This is a sample string";
        int vowelCount = 0;
        for (char c : str.toLowerCase().toCharArray()) {
            if (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u') {
                vowelCount++;
            }
        }
        System.out.println("Number of vowels: " + vowelCount);
    }
}
```

**输出：**

元音数量: 6

## 239. 统计字符串中的辅音数量

```java
public class ConsonantCount {
    public static void main(String[] args) {
        String str = "This is a sample string";
        int consonantCount = 0;
        for (char c : str.toLowerCase().toCharArray()) {
            if ((c >= 'a' && c <= 'z') && !(c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u')) {
                consonantCount++;
            }
        }
        System.out.println("Number of consonants: " + consonantCount);
    }
}
```

**输出：**

辅音数量: 12

## 240. 分别求数组中偶数和奇数的和

```java
public class SumEvenOddArray {
    public static void main(String[] args) {
        int[] array = {1, 2, 3, 4, 5, 6};
        int sumEven = 0;
        int sumOdd = 0;
        for (int num : array) {
            if (num % 2 == 0) {
                sumEven += num;
            } else {
                sumOdd += num;
            }
        }
        System.out.println("Sum of even numbers: " + sumEven);
        System.out.println("Sum of odd numbers: " + sumOdd);
    }
}
```

**输出：**

偶数之和: 12

奇数之和: 9

## 241. 使用递归计算数字阶阶

```java
public class FactorialRecursion {
    public static void main(String[] args) {
        int n = 5;
        int result = factorial(n);
        System.out.println("Factorial of " + n + " is: " + result);
    }

    public static int factorial(int n) {
        if (n == 0) {
            return 1;
        }
        return n * factorial(n - 1);
    }
}
```

**输出：**

5 的阶乘: 120

## 242. 使用递归求最大公约数 (GCD)

```java
public class GCDRecursion {
    public static void main(String[] args) {
        int a = 54;
        int b = 24;
        int gcd = gcd(a, b);
        System.out.println("GCD of " + a + " and " + b + " is: " + gcd);
    }

    public static int gcd(int a, int b) {
        if (b == 0) {
            return a;
        }
        return gcd(b, a % b);
    }
}
```

**输出：**

54 和 24 的最大公约数: 6

## 243. 使用 GCD 求最小公倍数 (LCM)

```java
public class LCMUsingGCD {
    public static void main(String[] args) {
        int a = 54;
        int b = 24;
        int lcm = (a * b) / gcd(a, b);
        System.out.println("LCM of " + a + " and " + b + " is: " + lcm);
    }

    public static int gcd(int a, int b) {
        if (b == 0) {
            return a;
        }
        return gcd(b, a % b);
    }
}
```

**输出：**

54 和 24 的最小公倍数: 216

## 244. 使用递归计算数字的幂

```java
public class PowerRecursion {
    public static void main(String[] args) {
        int base = 2;
        int exponent = 5;
        int result = power(base, exponent);
        System.out.println(base + " raised to the power of " + exponent + " is: " + result);
    }

    public static int power(int base, int exponent) {
        if (exponent == 0) {
            return 1;
        }
        return base * power(base, exponent - 1);
    }
}
```

**输出：**

2 的 5 次幂为: 32

## 245. 使用递归打印波那契数列

```java
public class FibonacciRecursion {
    public static void main(String[] args) {
        int n = 10;
        System.out.print("Fibonacci Series up to " + n + " terms: ");
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

**输出：**

波那契数列前 10 项: 0 1 1 2 3 5 8 13 21 34

## 246. 使用递归反转字符串



```java
public class ReverseRecursion {
    public static void main(String[] args) {
        String str = "Hello";
        String reversedStr = reverse(str);
        System.out.println("Reversed string: " + reversedStr);
    }

    public static String reverse(String str) {
        if (str.isEmpty()) {
            return str;
        }
        return reverse(str.substring(1)) + str.charAt(0);
    }
}
```

**输出：**

反转后的字符串: olleH

## 247. 使用递归检查字符串是否为回文

```java
public class PalindromeRecursion {
    public static void main(String[] args) {
        String str = "madam";
        boolean isPalindrome = isPalindrome(str);
        System.out.println(str + " is palindrome: " + isPalindrome);
    }

    public static boolean isPalindrome(String str) {
        if (str.length() == 0 || str.length() == 1) {
            return true;
        }
        if (str.charAt(0) == str.charAt(str.length() - 1)) {
            return isPalindrome(str.substring(1, str.length() - 1));
        }
        return false;
    }
}
```

**输出：**

madam 是回文的: true

## 248. 检查数字是否为质数

```java
public class PrimeCheck {
    public static void main(String[] args) {
        int num = 29;
        boolean isPrime = true;
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) {
                isPrime = false;
                break;
            }
        }
        if (isPrime) {
            System.out.println(num + " is a prime number.");
        } else {
            System.out.println(num + " is not a prime number.");
        }
    }
}
```

**输出：**

29 是质数。

## 249. 求前 N 个质数

```java
public class FirstNPrimes {
    public static void main(String[] args) {
        int n = 10;
        int count = 0;
        int num = 2;
        while (count < n) {
            boolean isPrime = true;
            for (int i = 2; i <= Math.sqrt(num); i++) {
                if (num % i == 0) {
                    isPrime = false;
                    break;
                }
            }
            if (isPrime) {
                System.out.print(num + " ");
                count++;
            }
            num++;
        }
    }
}
```

**输出：**

2 3 5 7 11 13 17 19 23 29

## 250. 查找第 N 个波那契数

```java
public class NthFibonacci {
    public static void main(String[] args) {
        int n = 10;
        int a = 0, b = 1, fib = 0;
        for (int i = 2; i <= n; i++) {
            fib = a + b;
            a = b;
            b = fib;
        }
        System.out.println("The " + n + "th Fibonacci number is: " + fib);
    }
}
```

**输出：**

第 10 个波那契数是: 34

## 251. 十进制转二进制

```java
public class DecimalToBinary {
    public static void main(String[] args) {
        int num = 10;
        String binary = "";
        while (num > 0) {
            binary = (num % 2) + binary;
            num = num / 2;
        }
        System.out.println("Binary representation: " + binary);
    }
}
```

**输出：**

二进制表示: 1010

## 252. 二进制转十进制

```java
public class BinaryToDecimal {
    public static void main(String[] args) {
        String binary = "1010";
        int decimal = 0;
        for (int i = 0; i < binary.length(); i++) {
            if (binary.charAt(i) == '1') {
                decimal += Math.pow(2, binary.length() - 1 - i);
            }
        }
        System.out.println("Decimal representation: " + decimal);
    }
}
```

**输出：**

十进制表示: 10

## 253. 查找二维数组中的最大元素

```java
public class LargestElement2D {
    public static void main(String[] args) {
        int[][] array = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        int max = array[0][0];
        for (int[] row : array) {
            for (int num : row) {
                if (num > max) {
                    max = num;
                }
            }
        }
        System.out.println("Largest element in the 2D array: " + max);
    }
}
```

**输出：**

二维数组中的最大元素: 9

## 254. 检查数字是否为阿姆斯特数

```java
public class ArmstrongCheck {
    public static void main(String[] args) {
        int num = 153;
        int originalNum = num;
        int result = 0;
        while (originalNum != 0) {
            int remainder = originalNum % 10;
            result += Math.pow(remainder, 3);
            originalNum /= 10;
        }
        if (result == num) {
            System.out.println(num + " is an Armstrong number.");
        } else {
            System.out.println(num + " is not an Armstrong number.");
        }
    }
}
```

**输出：**

153 是阿姆斯特数。

## 255. 计算数字各位数字之和

```java
public class SumOfDigits {
    public static void main(String[] args) {
        int num = 12345;
        int sum = 0;
        while (num > 0) {
            sum += num % 10;
            num = num / 10;
        }
        System.out.println("Sum of digits: " + sum);
    }
}
```

**输出：**

各位数字之和: 15

## 256. 反转数字

```java
public class ReverseNumber {
    public static void main(String[] args) {
        int num = 12345;
        int reversed = 0;
        while (num != 0) {
            int digit = num % 10;
            reversed = reversed * 10 + digit;
            num /= 10;
        }
        System.out.println("Reversed number: " + reversed);
    }
}
```

**输出：**

反转后的数字: 54321

输出：

反转后的数字：54321

## 257. 检查数字是否为回文

```java
public class PalindromeNumber {
    public static void main(String[] args) {
        int num = 121;
        int originalNum = num;
        int reversed = 0;
        while (num != 0) {
            int digit = num % 10;
            reversed = reversed * 10 + digit;
            num /= 10;
        }
        if (originalNum == reversed) {
            System.out.println(originalNum + " is a palindrome number.");
        } else {
            System.out.println(originalNum + " is not a palindrome number.");
        }
    }
}
```

输出：

121 是一个回文数字。

## 258. 查找字符串中每个字符的频率

```java
import java.util.HashMap;
import java.util.Map;

public class FrequencyOfCharacters {
    public static void main(String[] args) {
        String str = "hello world";
        Map<Character, Integer> charCountMap = new HashMap<>();
        for (char c : str.toCharArray()) {
            charCountMap.put(c, charCountMap.getOrDefault(c, 0) + 1);
        }
        for (Map.Entry<Character, Integer> entry : charCountMap.entrySet()) {
            System.out.println(entry.getKey() + ": " + entry.getValue());
        }
    }
}
```

输出：

```text
h: 1
e: 1
l: 3
o: 2
: 1
w: 1
r: 1
d: 1
```
