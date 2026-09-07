
# Java：完整实践解决方案

## 关于作者

Swati Saxena 是计算机科学助理教授，拥有 MCA 学位和 OCJP（Oracle认证 Java 专业人员），对该领域有深入了解，并在开发和培训方面拥有丰富经验。

她是知名的计算机科学书籍作者，曾为 BCA、MCA、BTech 学生编写书籍，并根据 NCERT 大纲为 XI-XII 年级标准的学生编写教材。

她因其写作工作获得了以下荣誉奖项：

1. 雅浦 Ratan 奖
2. Pratibha Samman 奖
3. 拉贾斯坦女性成就奖
4. 斯维瓦南德国家奖

她的知识和教学一直受到她的导师和学生的赞誉。

Swati 是《C语言编程与编码题库及答案》、《攻克 Kotlin 面试》、《Kotlin 速览》、《Python 面试题》等书籍的作者。

她的学生在印度外的许多知名机构中都拥有良好的发展。

## 前言

本书帮助你从实战角度理解 Java 的每一个主题。

它将帮助你开发软件和网站，因为人们应该具备扎实的实战知识。

它涵盖了从面试、认证和考试角度来看的所有主题，没有一个主题被遗漏。

这是一本完整的实战书籍。

这本书是在长期经验的基础上编写的。

尽管已经付出了巨大的努力，但仍不能排除细微不准确的可能性。

因此，如果您有任何建议，我们诚恳欢迎。

最后，感谢所有信任我的学生。

Swati Saxena

## 致谢

我感谢 BPB 出版社，他们激励我并要求我编写《Java-一个完整的实战解决方案》这本书。

我感谢 S.C. Saxena 教授（雅加普 Maharishi Arvind 技术学院前院长），他不断地给我灵感。我感谢 Naveen Saxena 先生在本书准备期间的持续支持。感谢班加罗尔 PESIT 大学前助理教授 Nidhi Saxena 教授的指导和支持。

最后，感谢 BPB 出版社的管理、编辑和制作人员，他们以创快的速度出版了这本书。

## 历史简介

Java 是一种通用的、基于类的、面向对象的、平台无关、可移植、架构中立、多线程、动态、分布式且健壮的解释型编程语言。

Java 最初是为交互式电视设计的，但对于当时的数字缆电视行业来说，这项技术太先进了。

Java 是 1991 年 6 月由 James Gosling、Patrick Naughton、Chris Warth、Mike Sheridan 和 Ed Frank 在 Sun Microsystems 作为一个“绿色项目”启动的。

绿色项目的成员启动了该项目，旨在为机顶盒、电视等数字设备开发一种语言。但它非常适合互联网编程。

最初它被称为 GreenTalk。这种语言最初称为 Oak，但在 1995 年重命名为 Java。它实现了“一次编写，随运行”（Write Once, Run Anywhere）的承诺，并在流行的平台上提供免费的运行时。

它是相当安全的，且安全性是可以配置的，允许限制对网络和文件的访问。

## 关键点

Java 是印度尼西亚的一个岛屿，第一个咖啡产自那里（Java 咖啡）。

- Java 只是一个名字，并不是缩写词。
- 它由 Sun Microsystems 的 James Gosling 团队开发（该公司现在是 Oracle 公司的子公司），并于 1995 年发布。
- 第一版本是 JDK 1.0。

## Java 版本

- JDK 1.0（1996年1月）
- J2SE 1.2（1998年12月8日）
- J2SE 1.4（2002年2月6日）
- Java SE 6（2006年12月11日）
- Java SE 8（2014年3月18日）
- Java SE 10（2018年3月18日）
- JDK 1.1（1997年2月19日）
- J2SE 1.3（2000年5月8日）
- J2SE 5.0（2004年9月30日）
- Java SE 7（2011年7月28日）
- Java SE 9（2017年9月21日）

## 魔法代码：字节码

Java 字节码是 Java 源代码编译后的语言，由 Java 虚拟机（JVM）理解。与必须为每种不同类型的计算机专门编译的编译型语言不同，Java 程序只需要转换一次字节码，之后就可以任何存在 Java 虚拟机的平台上运行。

字节码是一组设计用于 Java 运行时系统（称为 JVM）执行的指令。JVM 是字节码的解释器。

## Java 特性

- 简单
- 安全
- 平台无关
- 面向对象
- 健壮
- 可移植
- 动态
- 多线程
- 兼支持编译和解释
- 支持网络
- 高性能
- 分布式
- 架构中立

# 2. Java

## Java 示例要求

要执行任何 Java 程序，你需要：

- 如果没有安装 JDK，请下载并安装 JDK。
- 设置 `jdk/bin` 目录的路径。
- 创建 Java 程序。
- 编译并运行 Java 程序。

关于基础、循环、条件判断的问题和示例，请参阅：《C Programming and Coding, Question Bank with Solution by swati saxena (BpB)》。

### 1. 编写一个简单的 Java 程序来打印消息

```java
class First
{
    public static void main(String [] arg)
    {
        System.out.println("Welcome to Swati Computers");
    }
}
```

保存为：`First.java`

编译：`javac First.java`（它将创建一个包含字节码的 `First.class` 文件）

运行：`c:\> java First`

### Java 中的关键字

| assert | boolean | break |
|---|---|---|
| byte | catch | char |
| class | continue | default |
| do | else | enum |
| extends | final | float |
| for | goto | implements |
| import | instanceof | interface |
| long | native | package |
| private | protected | return |

## Java 数据类型

数据类型表示存储在变量中的不同值。在 Java 中，有两种数据类型：

- 基本类型（Primitive）
- 非基本类型（Non-primitive）

类型：

1. 基本类型
   - Boolean
   - 数值型 Numeric
   - char
   - Integer
   - byte、short、long
   - 浮点型 float、double
2. 非基本类型
   - String
   - Array
   - 等。

## 变量类型

Java 中有三种变量：

- 局部变量
- 实例变量
- 静态变量

### 2. 编写一个 Java 程序，在不使用第三个变量的情况下交换两个变量的值

```java
class Swap
{
    public static void main(String [] arg)
    {
        int a=2,b=3;
        a=b;
        b=a;
        System.out.println("A="+a+"\nb="+b);
    }
}
```

### 3. 编写一个 Java 程序检查 `main()` 函数是否可以重载

```java
class Overload
{
    public static void main(Integer [] aq)
    }
    public static void main(String [] args)
    {
        System.out.println("Hello");
    }
}
```

### 4. 编写一个程序输入矩形的长度和宽度并计算面积（使用参数）

```java
class Rect
{
    public static void main(String [] args)
    {
        int length = Integer.parseInt(args[0]);
        int breadth = Integer.parseInt(args[1]);
        int area = length * breadth;
        System.out.println("the area is " + area);
    }
}
```

### 5. 编写一个程序输入金额并检查有多少单利利

```java
import java.util.*;

class SI
{
    int principal, time;
    double rate;
    Scanner sc;

    public void read() 
    {
        sc = new Scanner(System.in);
        System.out.println("Enter principal");
        principal = sc.nextInt();
        System.out.println("Enter time");
        time = sc.nextInt();
        System.out.println("Enter rate");
        rate = sc.nextDouble();
    }

    public static void main(String [] args)
    {
        SI obj = new SI();
        obj.read();
        double si = (obj.principal * obj.time * obj.rate)/100;
        System.out.println("Simple interest is " + si);
    }
}
```

### 6. 编写一个程序输入人的名字和年龄并打印名字长度

```java
import java.util.*;

class inp
{
    String name, lname;
    int age;

    public static void main(String [] ar)
    {
        Scanner sc = new Scanner(System.in);
        System.out.println("enter name");
        name = sc.next();
        System.out.println("enter age");
        age = sc.nextInt();
        int len = name.length() + lname.length();
        System.out.println("Total length: " + len);
    }
}
```

### 7. 编写一个程序输入学生的名字和课程并使用另一个类的函数

```java
import java.util.*;

class Stu
{
    String n, cou;
    Scanner sc;

    public void read() 
    {
        sc = new Scanner(System.in);
        System.out.println("Enter name");
        n = sc.next();
        System.out.println("Enter course");
        cou = sc.next();
    }

    public void inp(String n, String course)
    {
        this.n = n;
        cou = course;
    }

    public String name()
    {
        return n;
    }

    public void disp()
    {
        System.out.println("Hello "+n+" r doing "+cou);
    }
}

class Stu_demo
{
    public static void main(String [] sd)
    {
        Stu p = new Stu();
        p.read();
        p.inp("swati","java");
        p.disp();
        System.out.println("bye "+p.name());
    }
}
```

### 9. 编写一个程序使用 `BufferedReader` 输入数字

```java
import java.io.*;

class Inp
{
    public static void main(String [] arg) throws IOException
    {
        int n;
        try {
            BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

            System.out.println("enter a no");
            n = Integer.parseInt(br.readLine());
            System.out.println("u input "+n);
        } catch (IOException e) {
            System.out.println("err");
        }
        System.out.println("byee.");
    }
}
```

### 10. 编写一个程序输入名字并打印名字长度

```java
import java.util.*;

class inp
{
    public static void main(String [] ar)
    {
        Scanner sc = new Scanner(System.in);
        System.out.println("enter ur name");
        String name = sc.next();
    }
}
```

```java
System.out.println("enter last name");

Iname=sc.next();

System.out.println("Hello +name");

int len=name.length()+In.length();

System.out.println(len);

}

}
```

### 11. 写一个程序，输入三个数字并打印它们的和（使用命令行）

```java
class Nums
{
    public static void main(String [] aa)
    {
        int sum=0;
        int a=Integer.parseInt(aa[0]);
        int b=Integer.parseInt(aa[1]);
        int c=Integer.parseInt(aa[2]);
        sum=a+b+c;
        System.out.println("the output is "+sum);
    }
}
```

## Java 中的运算符

1. 算术运算符：`+`、`-`、`*`、`/`、`%`
2. 一元运算符：`++`、`--`
3. 赋值运算符：`=`
4. 关系运算符：`<`、`<=`、`>=`
5. 比较运算符：`==`
6. 逻辑运算符：`&&`、`||`、`!`
7. 三元运算符：`(condition) true statement : false statement`
8. 位位运算符：`&`、`^`
9. 移位运算符：`<<`、`>>`、`>>>`
10. 复合赋值：`+=`、`-=`、`*=`、`/=`、`%=`

### 11. 写一个程序实现一元运算符

```java
class UnaryExample
{
    public static void main(String args[])
    {
        int x=10;
        System.out.println(x++);//10 (11)
        System.out.println(+x);//12
        System.out.println(x-);//12 (11)
        System.out.println(-x);//10
    }
}
```

### 12. 写一个程序，使用三元运算符找到两个数字中的最小值

```java
class OperatorExample
{
    public static void main(String args[])
    {
        int a=2;
        int b=5;
        int min=(a<b)?a:b;
        System.out.println(min);
    }
}
```

## Java 注释

注释是不可执行的代码。它们可以用于提供关于变量、方法、类或任何语句的信息或解释。

### Java 注释的类型

Java 中有 3 种注释：

- 单行注释：`//`
- 多行注释：`/*------*/`
- 文档注释：`/*** ----- */`

## 控制语句

### 1. `if-else`

语法：

```java
if (expression1)
{
  // codes
}
else if(expression2)
{
  // codes
}
else if (expression3)
{
  // codes
}
else
{
  // codes
}
```

### 2. `switch-case`

语法：



```java
switch (variable/expression)
{
    case value1:
        // statements
        break;
    case value2:
        // statements
        break;
        ....
        ....
    default:
        // statements
}
```

13. 写一个 Java 程序检查两个 `String` 变量是否相等？`class String_Demo`

```java
public class String_Demo {
    public static void main(String [] args) {
        String a,b="hi";
        a=ar[0];
        System.out.println("address of a:"+a.hashCode());
        System.out.println("address of b:"+b.hashCode());

        if(a==b) {
            System.out.println("equal");
        } else {
            System.out.println("not equal");
        }
        if(a.equals(b)) {
            System.out.println("equal");
        }
        else
        System.out.println("not equal");

        String c=new String("sub");
        String s=new String(b);
        System.out.println("address of c:"+c.hashCode());
        System.out.println("address of s:"+s.hashCode());

        if(a==c)
            System.out.println("equal");
        else
            System.out.println("not equal");
        if(a.equals(c))
            System.out.println("equal");
        else
            System.out.println("not equal");
    }
}
```

14. 写一个程序找到三个数中的最大值？

```java
public class JavaExample
{
    public static void main(String[] args)
    {
        int num1 = 10, num2 = 20, num3 = 7;

        if(num1 >= num2 && num1 >= num3)
            System.out.println(num1+" is the largest");

        else if (num2 >= num1 && num2 >= num3)
            System.out.println(num2+" is the largest");

        else
            System.out.println(num3+" is the largest");
    }
}
```

15. 写一个 Java 程序，根据运算符显示数字的计算结果

```java
import java.util.Scanner;

class Calculator
{
    public static void main(String args) {
        char operator;
        Double number1,number2,result;

        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter operator (either +, *, /): ");
        operator = scanner.next().charAt(0);
        System.out.print("Enter number1 and number2 respectively: ");
        number1 = scanner.nextDouble();
        number2 = scanner.nextDouble();

        switch (operator) {
            case '+':
                result = number1 + number2;
                System.out.println(result);
                break;
            case '*':
                result = number1 * number2;
                System.out.println(result);
                break;
            case '/':
                result = number1 / number2;
                System.out.println(result);
                break;
            default:
                System.out.println("Invalid operator!");
        }
    }
}
```

16. 写一个程序检查给定年份是否为闰年？

```java
import java.util.Scanner;
class Calculator {
    public static void main(String[] args) {
        int chk_year;
        Scanner scanner = new Scanner(System.in);
        System.out.println("Enter year");
        chk_year=scanner.nextInt();

        if ((chk_year % 400) == 0) {
            System.out.println(chk_year + " is leap year");
        } else if ((chk_year % 100) == 0) {
            System.out.println(chk_year + " is not leap year");
        } else if ((chk_year % 4) == 0) {
            System.out.println(chk_year + " is leap year");
        } else {
            System.out.println(chk_year + " is not leap year");
        }
    }
}
```

17. 写一个程序检查给定数字是正、负还是零？

```java
class Ladder
{
    public static void main(String[] args)
    {
        int number = 0;

        if (number > 0)
        {
            System.out.println("Number is positive.");
        } else if (number < 0)
        {
            System.out.println("Number is negative.");
        } else
        {
            System.out.println("Number is 0.");
        }
    }
}
```

18. 写一个程序计算扣除折扣后的支付金额。

折扣如下：

| 购买金额 | 折扣 |
| :--- | :--- |
| >= 8,000 | 购买金额的 10% |
| >= 5,000 | 购买金额的 8% |
| >= 1,000 | 购买金额的 4% |
| 其他 | 100 元 |

```java
import java.util.Scanner;
class Rates
{
    public static void main(String[] args) {
        double PR,dis, amount;
        Scanner scanner = new Scanner(System.in);
        System.out.println("Enter purchase rate");
        PR=scanner.nextDouble();

        if(PR>=8000)
            dis=PR*.10;
        else if(PR>=5000)
            dis=PR*.08;
        else if(PR>=1000)
            dis=PR*.04;
        else
            dis=100;

        amount=PR-dis;
        System.out.println("Amount payable after " + dis+" discount is "+amount);
    }
}
```

### 迭代/循环：

循环语句允许我们多次执行语句或一组语句。Java 支持 3 种循环以及增强 `for` 循环。

1. `for` 循环

   Java `for` 循环允许用户在一行内编写整个条件，即初始化、条件和递增/递减。

   `For(初始化; condition; increment/decrement){}`

2. 增强 `for` 循环

   此版本是在 Java 5 中引入的，此功能允许你对数组元素进行迭代。当索引未知时应使用此功能。

```java
for (T element:Collection obj/array)
{
    statement(s)
}
```

3. `while` 循环

   在 Java 循环中，如果布尔条件为，循环将持续执行，它可以被视为一种重复语句。

```java
While(condition){
```

4. `do-while` 循环

   `while` 语句是一种退出控制循环，即它在执行循环后检查条件

```java
do
    {statements;}
while(condition);
```

```java
for(i=0;i<name.length();i++)
{
    char c=name.charAt(i);
    if(c=='a'||c=='e'||c=='i'||c=='o'||c=='u')
    {
        count++;
    }
    System.out.print(c+"..");
}
}
```

编写一个程序来验证电子邮件 ID：它应该包含一个 `@` 和至少一个 `"."`？

```java
import java.util.*;
class Scan
{
    public static void main(String [] aa)
    {
        Scanner as= new Scanner(System.in);
        String email;
        int i,count=0,count1=0;
        System.out.println("enter the email ");
        email=as.next();
        int c=email.length();
        for(i=0;i<email.length();i++)
        {
            char k=email.charAt(i);
            if(k=='@')
            {
                count++;
            }
            if(k=='.')
            {
                count1++;
            }
        }
    }
}
```

```java
}
{
if(count==1&&count1>0)
{
    System.out.println("valid id");
}
else
{
    System.out.println("invalid id ");
}
}
```

21. 编写一个程序来反转一个数字？

```java
import java.util.Scanner;
class ReverseNumberWhile
{
    public static void main(String[] args)
    {
        int num=0;
        int reversum =0;
        System.out.println("Input your number and press enter:");
        Scanner in = new Scanner(System.in);
        num = in.nextInt();
        //While Loop: 找到反转数字的逻辑
        while (num != 0 )
        {
            reversum = reversum * 10;
            reversum = reversum + num%10;
            num = num/10;
        }
        System.out.println("Reverse of input number is: "+reversum);
    }
}
```

22. 编写一个程序来计算给定数字的阶乘？

```java
class FactorialDemo
{
    public static void main(String args[])
    {
        int factorial = fact(4);
        System.out.println("Factorial of 4 is: "+factorial);
    }
    static int fact(int n)
    {
        int output;
        if(n==1){
            return 1;
        }
        //递归: 函数自己调用自己！！
        output = fact(n-1)* n;
        return output;
    }
}
```

23. 编写一个程序生成 0 到 200 之间的随机数？

```java
import java.util.*;
class GenerateRandomNumber
{
    public static void main(String args[])
    {
        int counter;
        Random rnum = new Random();
        /* 以下代码将生成 0 到 200 之间的
           * 5 个随机数。
        */
        for (counter = 1; counter <= 5; counter++)
        {
            System.out.println(rnum.nextInt(200));
        }
    }
}
```

```java
}
}
}
```

24. 编写一个程序打印斐波那契数列 0,1,1,2,3....N ？

```java
import java.util.Scanner;
class ReverseNumberWhile
{
    public static void main(String args[])
    {
        int num=0;
        int i=0,j=1;
        System.out.println("Input your number and press enter: ");
        Scanner in = new Scanner(System.in);
        num = in.nextInt();
        while(i<=num)
        {
            System.out.println(i);
            j=i+j;
            i=j-i;
        }
    }
}
}
```

25. 编写一个程序来寻找前 N 个质数？



```java
import java.util.Scanner;
class PrimeNumberDemo
{
    public static void main(String args[])
    {
        int n;
        int status = 1;
        int num = 2;
        Scanner scanner = new Scanner(System.in);
        System.out.println("Enter the value of n:");
        n = scanner.nextInt();
        if (n >= 1)
        {
            System.out.println(n+" prime numbers are:");
            for (int i = 0; i < n; i++)
            {
                for (int j = 2; j <= Math.sqrt(num); j++)
                {
                    if (num%j == 0)
                    {
                        status = 0;
                        break;
                    }
                }
                if (status != 0)
                {
                    System.out.println(num);
                }
                num++;
                status = 1;
            }
        }
    }
}
```

- 26. 编写一个程序输入用户详情：用户名和密码。

```java
import java.util.*;
class Login
{
    public static void main(String [] args)
    {
        String uname,pwd;
        Scanner sc= new Scanner(System.in);
        System.out.println("Enter user name");
        uname=sc.next();
        System.out.println("Enter password");
        pwd=sc.next();
        System.out.println("Hello user :"+uname);
        System.out.println("Entered Password :"+pwd);
    }
}
```

模式和循环参考“C编程题库”。

# ARRAY

数组是一个包含相同类型元素的对象。一旦定义，数组的大小是固定的，不能容纳更多元素。数组的索引从0开始。

语法：

```java
int[] arrname;
arrname=new int[size];
int[][] arrname=new int[rows][cols];
```

- 数组的优势：

- 代码优化：我们可以轻松排序数据。

- 随机访问：我们可以获取任何位置的数据。

- 27. 编写一个程序输入五个数字并计算它们的和以及最大值？

```java
import java.util.*;
class array1
{
    public static void main(String []at)
    {
        Scanner sc=new Scanner(System.in);
        int[]a=new int[5];
        int i=0,s=0,max=0;
        for(i=0;i<5;i++)
        {
            System.out.println("Enter no.");
            a[i]=sc.nextInt();
            s=s+a[i];
            if(a[i]>max)
            {
                max=a[i];
            }
        }
        for(i=0;i<5;i++) {
            System.out.println("a[" + i + "]=" + a[i]);
        }
        System.out.println("Sum="+s);
        System.out.println("Max="+max);
    }
}
```

# 28 JAVA

- 28. 编写一个程序打印二维数组的不同列；

```java
import java.util.*;
class Arry3 {
    public static void main(String []at) {
        Scanner sc=new Scanner(System.in);
        int a[][]=new int[][][] {
            {1,2},
            {2,3,4},
            {5,6,9},
            {8},
        };
        int i,j;
        for(i=0;i<a.length;i++) {
            for(j=0;j<a[i].length;j++) {
                System.out.print(a[i][j]+"\t");
            }
        }
        System.out.println();
    }
}
```

- 29. 编写一个程序初始化字符串数组并打印它？

```java
import java.util.*;
class arry4
{
    public static void main(String []at)
    {
        Scanner sc=new Scanner(System.in);
        String [] col=new String[]{"red","green","blue"};
        int i;
        for(i=0;i<col.length;i++)
        {
            System.out.println(col[i]+":"+col[i].length());
        }
    }
}
```

- 30. 编写一个程序打印随机验证码（captcha）？

```java
import java.util.*;
class sgn
{
    public static void main(String [] aa)
    {
        Random r=new Random();
        char [] q1=new char[]{'a','b','c','d','e','f','g','h','i','j','k','l','m','n','o','p','q','r','s','t','u','v','w','x','y','z'};
        char [] q2=new char[]{'A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','W','X','Y','Z'};
        int f=r.nextInt(20);
        System.out.print(q2[f]);
        System.out.print(f+100*f+q1[f]);
        System.out.print(q1[f/2]);
    }
}
```

- 31. 编写一个程序演示三维数组？

```java
class ThreeD {
    public static void main(string [] arg) {
        int threed[][][]=new int [3][4][5];
        int i,j,k;
        for(i=0;i<3;i++) {
            for(j=0;j<4;j++) {
                for(k=0;k<5;k++) {
                    threed[i][j][k] = i * j * k;
                }
            }
        }
        for(i=0;i<3;i++) {
            for(j=0;j<4;j++) {
                for(k=0;k<5;k++) {
                    System.out.print(threed[i][j][k] + "");
                }
            }
        }
        System.out.println();
    }
}
```

- 32. 编写一个程序演示带标签的 `break`（labeled break）？

```java
class Break {
    public static void main(String [] arg)
```

```java
{
  boolean flag=true;
  first{
    second{
      third{
        System.out.println("Before break");
        if(flag) break second; //跳出第二个代码块
        System.out.println("this won't execute");
      }
      System.out.println("this won't execute");
    }
  }
}
```

`System.out.println("this is after second block");`

33. 写一个程序打印 0 到 9 的三角形乘法表？

```java
class Tables
{
  public static void main(String [] arg) {
    outer: for(int i=0;i<10;i++){
      for(int j=0;j<10;j++){
        if(j>i){
          System.out.println();
          continue outer;
        }
        System.out.println("+(i * j));
      }
      System.out.println();
    }
  }
}
```

## 对象与类 (OBJECT AND CLASSES)

对象（Object）是现实世界中的实体，具有某些标识、状态和行为。

类（Class）是一组具有共同属性的对象集合。它是创建对象的模板或蓝图。它是一个逻辑实体。

类可以包含以下内容：

- 字段 (fields)

- 方法 (methods)

- 构造方法 (constructors)

- 语句块 (blocks)

- 嵌套类和接口 (nested class and interface)

在类内部方法外部创建的变量被称为实例变量（instance variable）。

实例变量在编译时不分配内存。它在创建对象（实例）时分配内存。这就是为什么它被称为实例变量。

`new` 关键字用于在运行时分配内存。所有对象都存储在堆（Heap）内存区域中。

Java 中类名的首字母应该大写（这是 Java 的规则），但如果你写成小写也不会报错。

34. 写一个程序为学生和员工创建不同的类，并带有方法且填充详情？

```java
import java.util.*;
class emp {
    String job;
    Scanner sc;
    public void() {
        sc=new Scanner(System.in);
        System.out.println("enter post");
        job=sc.next();
    }
    public void put() {
        System.out.println("u r working as "+job);
    }
}
class stu
{
    String name;
    int age;
    Scanner sc;
    public void get() {
        sc=new Scanner(System.in);
        System.out.println("Enter name and age");
        name=sc.next();
        age=sc.nextInt();
    }
    public void put() {
        System.out.println("hello "+name);
        System.out.println("u r "+age+"years old");
    }
}
class stu_demo
{
    public static void main(String [] ar) {
        stu s=new stu();
        emp e=new emp();
        System.out.println("Enter stu data");
        s.get();
        System.out.println("Enter employee record");
        e.inp();
        System.out.println("Data Input:");
        s.put();
        e.put();
    }
}
```

35. 写一个程序演示隐式转换和显式转换？

```java
class Explicit {
    public static void main(String [] ar) {
        Object o0,o1;
        String s = new String("Hello");
        o0 = new String("Hello");
        String t;
        t = (String) o0;
        o1=t;//隐式转换
    }
}
```

36. 写一个程序检查给定的字符串是否是回文？

```java
import java.util.*;
class count_word {
    public static void main(String [] as) {
        String n;
        int i,wc=0,space=0,j;
        char c,c1;
        Scanner sc=new Scanner(System.in);
        System.out.println("Enter a string");
        n=sc.nextLine();
        for(i=0;i<n.length();i++) {
          c=n.charAt(i);
          if(c==' ') {
            space++;
            wc++;
          }
        }
        int cc=n.length()-space;
        System.out.println("Total characters in name " + cc + "\nTotal words are " + wc);

        //回文字符串
        space=0;
        for(i=0,j=n.length()-1;i<n.length()/2;i++,j--) {
          c=n.charAt(i);
          c1=n.charAt(j);
          if(c!=c1) {
            space=1;
            break;
          }
        }
        if(space==0)
          System.out.println("Palindrome string");
        else
          System.out.println("Not");
}
```

37. 写一个程序使用匿名对象调用类的方法？

```java
class Factorial
{
  void fact(int n) {
    int fact=1;
    for(int i=1;i<=n;i++) {
      fact=i;
    }
    System.out.println(fact);
  }
  public static void main(String[]) {
    new Factorial().fact(5);//使用匿名对象调用
  }
}
```

38. 写一个程序创建一个类，通过 `get()` 方法输入值并计算面积？

```java
class Rectangle
{
  int length;
  int width;
  void get(int l,int w) {
    length=l;
    width=w;
  }
  void calculateArea() {
```



`System.out.println(length*width);`

```
}

class Test2

public static void main(String[] args){

  Rectangle r1=new Rectangle(),r2=new Rectangle();//创建两个对象

  r1.get(11,5);

  r2.get(3,15);

  r1.calculateArea();

  r2.calculateArea();

}

}
```

39. 写一个程序创建一个类，带有 `deposit()` 和 `withdraw()` 等不同方法？

```java
class Account

{

  int acc_no;

  String name;

  float amount;

  void open_account(int a,String n,float amt) {

    acc_no=a;

    name=n;

    amount=amt;

  }

  void deposit(float amt) {

    amount+=amt;

    System.out.println("deposited");

  }

  void withdraw(float amt) {

    if(amount<amt){

      System.out.println("Insufficient");

    } else {

      amount-=amt;

      System.out.println("withdrawn");

    }

  }

  void display() {

    System.out.println(acc_no+" "+name+" "+amount);

  }

  public static void main(String[]){

    Account a1=new Account();

    a1.open_account(1234,"She",10000);

    a1.display();

    a1.deposit(4000);

    a1.display();

    a1.withdraw(5000);

    a1.display();

  }

}
```

40. 写一个程序带有 `set()` 和 `get()` 方法的类？

```java
class Student

{

  int roll_no;

  String course;

  void set_roll(int r) {

    roll_no=r;

  }

  int get_roll() {

    return roll_no;

  }

  void set_course(String c) {

    course=c;

  }

  String get_course() {

    return course;

  }

}
```

### 构造方法 (CONSTRUCTOR)

构造方法是类的一个成员函数。它在创建实例时自动调用。它用于初始化对象。每个类至少有一个构造方法。

### 特

- 构造方法的名字与类名相同。
- 它没有返回值。
- 它是自动调用的，不需要显式调用。
- 支持重载，类可以有多个不同参数的构造方法。

41. 写一个程序演示默认构造、参数化构造和拷贝构造？

```java
class Constructor_demo {

    int x;

    Constructor_demo () {

        System.out.println("default constructor");

    }

    Constructor_demo (int a) {

        this.x=a;

        System.out.println("parameterized constructor " + a);

    }

    Constructor_demo (Constructor_demo a) {

        this.x=a.x;

        System.out.println("copy constructor" +a.x);

    }

    public static void main(String sd) {

        Constructor_demo d=new Constructor_demo ();

        d=new Constructor_demo(1);

        Constructor_demo d1=new Constructor_demo (d);

    }

}
```

42. 写一个程序使用变长参数进行求和？

```java
class Addi {

  int t;

  public void sum(int ...a) {

    t=0;

    for(int i:a) {

      t=t+i;

    }

    System.out.println("Sum="+t);

  }

  public static void main(String [] arg) {

    Addi a=new Addi();

    a.sum(1,3,4,6,7,5,4,3,2,3,4,4);

    a.sum(45,23);

  }

}
```

43. 写一个程序使用构造方法输入学生数据？

```java
import java.util.*;

class student1

{

    String name,course;

    student1() {

        name="guest";

        course=" not decided";

    }

    student1(String name) {

        this.name=name;

        course=" not decided";

    }

    student1(String name,String course) {

        this.name=name;

        this.course=course;

    }

    void read(String name, String c) {

        this.name=name;

        System.out.println("reference of this"+this.hashCode());

        course=c;

    }

    void show() {

        System.out.println("Hello "+name);

        System.out.println("u r doing"+course);

    }

}
```

```java
public static void main(String [] arg)

{

    student1 s=new student1();

    System.out.println("reference of s"+s.hashCode());

    String a,b;

    Scanner sc=new Scanner(System.in);

    /*System.out.println("Enter name and course");

    a=sc.next();

    b=sc.next();*/

    //s.read(a,b);

    s.show();

    s=new student1("surabhi");

    System.out.println("reference of s"+s.hashCode());

    s.show();

    student1 s1=new student1("raj","java");

    System.out.println("reference of s1"+s1.hashCode());

    s1.show();

}
```

44. 编写一个程序在另一个构造函数中调用构造函数？
**(构造函数链)**

```java
public class Chaining

{

    public Chaining()

    {

        System.out.println("In default constructor...");

    }

    public Chaining(int i)

    {

        this();

        System.out.println("In single parameter constructor...");

    }

    public Chaining(int i,int j) {

        this(j);

        System.out.println("In double parameter constructor...");

    }

    public static void main(String a[]) {

        Chaining ch = new Chaining(10,20);

    }

}
```

## 静态:

Java 中的 `static` 关键字主要用于内存管理。
`static` 可以是：

- 1. 变量（也称为类变量）
- 2. 方法（也称为类方法）
- 3. 代码块
- 4. 嵌套类

静态变量被类的所有实例（或对象）共有，因为它是一个类级变量。

换句话说，你可以认为静态变量只被创建了一个副本，并在该类的所有实例之间共享。

此类变量的内存分配只在类加载到内存中时发生一次。

45. 编写一个程序，为不同学生的学生卡分配相同的大学名称。是否需要询问学生姓名和专业？

```java
class Student_ID_Card

{

  String name, branch;

  static String college="Swati Computers";

  Student_ID_Card(String n,String b)

  {

    name = n;

    branch=b;

  }

  void display() {System.out.println(name+"" + branch+""+college);}

}

public static void main(String args[])

{

    Student_ID_Card s1 = new Student_ID_Card("Sweety","CS");

    Student_ID_Card s2 = new Student_ID_Card("Shweta","ECE");

    s1.display();

    s2.display();

}

}
```

46. 编写一个程序演示静态代码块：

```java
class static_demo{

  static int a;

  static

  {

    System.out.println("hello");

  }

  static

  {

    System.out.println("wel");

  }

  public static void main(String [] ar) {

    a=10;

    System.out.println("hi");

  }

}
```

47. 编写一个程序，统计在某大学不同专业入学的学生人数；

```java
class static_demo1{

  static int count=0;

  static_demo1(String b)

  {

    System.out.println(b);

    count++;

  }

  public static void put() {

    System.out.println(count+"");

  }

  public static void main(String [] ra) {

    static_demo1 s=new static_demo1("CS");

    static_demo1 s1=new static_demo1("ECE");

    static_demo1 s2=new static_demo1("Electrical");

    static_demo1.put();

  }

}
```

48. 编写一个程序演示如何在没有对象的情况下访问另一个类的变量？

```java
class Static_demo {

  static int a=100;

}

class Static_Demo {

  public static void main(String [] ar) {

    System.out.println("a = " + Static_demo.a);

  }

}
```

49. 编写一个程序来区分实例变量和类变量？

```java
class Stu1

{

    int count; //instance variable

    static int cou; //class variable

    public Stu1()

    {

        count++;

        cou++;

    }

    public void display()

    {

        System.out.println(count);

    }

}

class Third

{

    static

    {

        System.out.println("hi");

    }

    static

    {

        System.out.println("hii");

    }

    public static void main(String [] ar)

    {

        Stu1 s=new Stu1();

        Stu1 s1=new Stu1();

        s.display();

        s1.display();

        System.out.println("Total students"+Stu1.cou);

    }

}
```

## “THIS” 关键字：

这是一个引用当前对象的引用变量。
Java 中 `this` 的用法：

- `this` 可以用于引用当前类变量。
- `this` 可以作为参数传递给方法调用。
- `this` 可用于当前类的构造函数。
- `this` 可以作为参数传递给构造函数调用。
- `this` 可用于调用当前类方法（隐式）。
- `this` 可用于从方法返回类实例。

50. 编写一个程序调用同类的另一个方法？

```java
class Methods

{

  void two()

  {

    System.out.println("hello two");

  }

  void one()

  {

    System.out.println("hello one");

    this.two();

  }

}

class Test_This

{

  public static void main(String args[]){

    Methods m=new Methods();

    m.one();

  }

}
```

51. 编写一个程序输入学生的姓名和学号？

```java
class Students

{

    int roll;

    String name;

    public void get(int r, String name)

    {

        roll=r;

        this.name=name;

    }

    public void put()

    {

        System.out.println("roll="+roll+"="+name);

    }

    public static void main(String [] ae)

    {

        Students s=new Students();

        s.get(10,"shweta");

        s.put();

    }

}
```

52. 编写一个程序在另一个构造函数调用同类的构造函数？

```java
class Constr

{

    Constr()

    {

        System.out.println("I am default constructor called");

    }

    Constr (int x)

    {

        this();

        System.out.println(x);

    }

}

class Test_This

{

  public static void main(String args[]){

    Constr c=new Constr(10);

  }

}
```

53. 编写一个程序通过同类的默认构造函数调用参数构造函数？

```java
class A

{

  A()

  {

    this(10);

    System.out.println("I am default constructor");

  }

  A(int x)

  {

    System.out.println("I am parameterized constructor");

  }

}

class Test_This

{
```



`public static void main(String [] arg)` {

    `A a=new A();`

}

```

54. 编写一个程序将“this”作为参数传递？

```java
class This_test
{
  void fun(This_test obj)
  {
    System.out.println("method is invoked");
  }
  void funct()
  {
    fun(this);
  }
  public static void main(String args[]){
    This_test s1 = new This_test();
    s1.funct();
  }
}
```

## Final 关键字：

`Final` 关键字用于创建常量并限制对类、变量或方法的使用。

`Final` 可以：

- 变量：不能更改`final`变量的值（它成为常量）。
- 类：如果你将任何类标记为`final`，则无法继承它。
- 方法：如果你将任何方法标记为`final`，则无法重写它。

55. 编写一个程序在学生卡给出大学名称、学生姓名、就读年份。大学名称不能为任何学生更改。

```java
Class Id_card
{
    final String name_college="Swati Computers";
    String name_stu;
    int year;
    public Id_card()
    {
        name_stu="Unknown";
        year=0;
    }
    public Id_card(String n,int y)
    {
        name_stu=n;
        year=y;
    }
    public void display()
    {
        System.out.println(name_stu+" student of "+name_college+" is studying in "+year+" year");
    }
    public static void main(String [] ar)
    {
        Id_card i=new Id_card();
        Id_card i1=new Id_card("swati",1);
        Id_card i2=new Id_card("shweta",2);
        i.display();
        i1.display();
        i2.display();
    }
}
```

56. 编写一个程序演示问题：如果你有一家时尚学院“SWFT”，并且不想授予任何特许经营。如果任何其他学院在牌子上显示它是“SWFT”的，这是违法的。在 Java 类中如何解决这个问题？

```java
final class SWFT{}
class Any_institute extends SWFT
{
    public Any_institute()
    {
        System.out.println("We are sister concern of SWFT");
    }
    public static void main(String [] at)
    {
        new Any_institute();
    }
}
```

57. 由于 SBI 银行在印度有很多分行，任何客户都可以从任何分行使用其服务，但如果客户遇到银行卡/ATM 等问题，根据经理所他们应该咨询总行。总行有很多权利，但小分行没有。编写 Java 类创建 SBI 的总行和小分行，并且某些功能无法在小分行中继承。

```java
class SBI_main
{
    System.out.println("If you have issues related cheque book\n    etc,yours welcome");
    final void cheque_book_issue(){}
    final void amount_issue(){}
}
class SBI_Mansarovar extends SBI_main
{
    void withdraw(){}
    void deposit(){}
    void open_new_account(){}
}
class SBI_Tnokroad extends SBI_main
{
    void withdraw(){}
    void deposit(){}
    void open_new_account(){}
}
```

## JAVA - 正则表达式 (REGEX)

Java 正则表达式（Regular Expression）是一种用于定义搜索或操作字符串模式的 API。

正则表达式是一特殊的特殊的字符序列，它可以帮助你使用模式中持有的特殊语法来匹配或查找其他字符串或字符串集。

`java.util.regex`程序包包含 1 个接口和 3 个类：

- 1. `MatchResult`接口
- 2. `Matcher`类
- 3. `Pattern`类
- 4. `PatternSyntaxException`类

58. 编写一个 Java 程序使用正则表达式验证邮箱地址？

```java
import java.util.regex.*;
public class Validate_email {
    public static void main(String[] args) {
        String EMAIL_REGEX = "^[\\w-\\.]+@([\\w-\\.]+)+\\w+$";
        String email1 = "user@domain.com";
        Boolean b = email1.matches(EMAIL_REGEX);
        System.out.println("is-mail: "+email1+":Valid = " + b);
        String email2 = "user^domain.co.in";
        b = email2.matches(EMAIL_REGEX);
        System.out.println("is-mail: "+email2+":Valid = " + b);
    }
}
```

59. 编写一个程序使用正则表达式在给定字符串中搜索单词 “book”出现的次数？

```java
import java.util.regex.*;
class RegexExample1{
    public static void main(String args[]){
        String content = "This is a java " + "book from swati";
        String pattern = ".*book.*";
        boolean isMatch = Pattern.matches(pattern, content);
        System.out.println("The text contains ‘book?’ " + isMatch);
    }
}
```

60. 编写一个程序将给定字符串中所有出现的单词 ”tough”替换为“easy”？

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;
public class RegexMatches {
    private static String REGEX = "tough";
    private static String INPUT = "All says Java is a tough language " + "Java programs are tough";
    private static String REPLACE = "easy";
    public static void main(String[] args) {
        Pattern p = Pattern.compile(REGEX);
        // 获取一个匹配器
        Matcher m = p.matcher(INPUT);
        INPUT = m.replaceAll(REPLACE);
        System.out.println(INPUT);
    }
}
```

## 字符串 (STRING)

通常情况下，字符串是字符序列。但在 Java 中，字符串是一个表示字符序列的对象。`java.lang.String`类用于创建字符串对象。

Java 字符串字面量通过双引号创建。

Java `String`是不可变的（immutable），即它不能被更改。每当我们更改任何字符串时，都会创建一个新的实例。

对于可变的字符串，你可以使用`StringBuilder`和`StringBuffer`类。

61. 编写一个程序将给定字符串中的 'a' 替换为 'E'

```java
import java.io.*;
public class Test {
    public static void main(String[] args) {
        String Str = new String("java language");
        System.out.print("Return Value : ");
        System.out.println(Str.replace('a', 'E'));
    }
}
```

## StringBuffer 和 StringBuilder 的区别

| StringBuffer | StringBuilder |
|---|---|
| `StringBuffer`是同步的，即线程安全的。 | `StringBuilder`是非同步的，即不是线程安全的。 |
| 这意味着两个线程不能同时调用`StringBuffer`的方法。 | 这意味着两个线程可以同时调用`StringBuilder`的方法。 |

62. 编写一个 Java 程序来演示`String`类和`StringBuilder`类之间的区别？

```java
public class string {
    public static void main(String [] ar) {
        String n=new String("Swati");
        System.out.println(n.hashCode());
        n="saxena";
        System.out.println(n.hashCode());
        n=n+"cloud";
        System.out.println(n.hashCode());
        StringBuilder sb=new StringBuilder("Swati");
        System.out.println(sb.hashCode());
        sb.append("saxena");
        System.out.println(sb);
        System.out.println(sb.hashCode());
    }
}
```

63. 编写一个 Java 程序解释`String`的`startWith()`方法的？

```java
public class string {
    public static void main(String [] ar) {
        String str=new String("swati computers, developers choice");
        System.out.println("String str starts with swati: "+str.startsWith("swati"));
        System.out.println("String str starts with brown: "+str.startsWith("brown"));
        System.out.println("substring of str(starting from 6th index) has computers prefix: "+str.startsWith("computers", 6));
        System.out.println("substring of str(starting from 17th index) has developers prefix: "+str.startsWith("developers", 17));
    }
}
```

64. 编写一个程序统计给定字符串中 'a' 的个数？

```java
class A
{
    public static void main(String [] ar)
    {
        String n=ar[0];
        int i,count=0;
        for(i=0;i<n.length();i++)
        {
            if(n.charAt(i)=='a')
            {count++;
            }
        }
        System.out.println("total a:"+count);
    }
}
```

## 实例检查 (INSTANCEOF)

`instanceof`运算符用于测试对象是否是指定类型（类或子类）的实例。

65. 编写一个程序检查给定对象是否为类的实例？

```java
class Person {
    public void show() {
        System.out.println("Person");
    }
}
class stu extends Person {
    public void show() {
        System.out.println("stu");
    }
}
class emp extends Person {
    public void show() {
        System.out.println("emp");
    }
}
public class Instance {
    public static void main(String[] args) {
        Person p=new stu();
        if(p instanceof stu) {
            p.show();
        }
        if(p instanceof emp) {
            p.show();
        }
    }
}
```

## 内部类 (INNER CLASS)

内部类是在另一个类定义的类。内部类可以访问外部类的成员。Java 中有四种内部类：

- 1) 嵌套类
- 2) 方法内部类
- 3) 匿名内部类
- 4) 静态嵌套类

66. 编写一个程序创建内部类并调用其方法？

```java
class outer {
  String n="outer";
  void get() {
    class inner {
      void show() {
        System.out.println(n);
      }
    }
    inner i=new inner();
    i.show();
  }
}
public class Inners {
  public static void main(String[] arg) {
    outer o=new outer();
    o.get();
  }
}
```

67. 编写一个程序演示方法内部类？

```java
class Outer {
  void outerMethod() {
    System.out.println("outside outerMethod");
    class Inner {
      void innerMethod() {
        System.out.println("inside innerMethod");
      }
    }
    Inner y=new Inner();
    y.innerMethod();
  }
}
class Method_Inner_Demo {
  public static void main(String[] args) {
    Outer x=new Outer();
    x.outerMethod();
  }
}
```

68. 在大型项目中，你可能会有同名的类，请给出解决此问题的方法？

```java
class OuterStatic {
  private int mem =20;
  private static int smem = 50;
  static class InnerStatic
  {
    public void accessMembers()
    {
        System.out.println(mem); // 错误无法引用非静态字段 mem
        System.out.println(smem);
    }
}
```



## 继承（INHERITANCE）

继承定义为一个类获取另一个类的属性（方法和字段）的过程。`extends` 是继承类属性的关键字。

### super

- `super` 关键字
- 它用于在名称相同时区分父类成员和子类成员。
- 它用于从子类调用父类构造函数。

## 方法重写（Overriding）

如果一个类从其父类继承了一个方法，那么就有重写该方法的机会，只要该方法不是 `final` 的。重写的好处是：能够定义针对子类类型的特定行为，这意味着子类可以根据其需求实现父类。

方法重写的规则：

- 参数列表应与被重写的方法完全相同。
- 返回类型应与父类中原始被重写方法的返回类型相同或为子类型。
- 访问权限不能比被重写方法的访问权限更严格。例如：如果父类方法声明为 `public`，则子类中的重写方法不能是 `private` 或 `protected`。
- 只有被子类继承的实例方法才能被重写。
- 声明为 `final` 的方法不能被重写。
- 声明为 `static` 的方法不能被重写，但可以重定义。
- 如果一个方法无法被继承，那么它无法被重写。
- 与实例父类同同一个包中的子类可以重写任何未声明为 `private` 或 `final` 的父类方法。
- 不同包中的子类只能重写声明为 `public` 或 `protected` 的非 `final` 方法。
- 重写方法可以抛出任何未检查异常（unchecked exceptions），无论重写方法是否抛出异常。
- 然而，重写方法不应抛出比重写方法中所声明的新的或范围更大的检查异常（checked exceptions）。
- 重写方法可以抛出比原有更窄或更少的异常。
- 构造函数不能被重写。

69. 编写一个程序：创建一个带有默认构造函数和参数构造函数的基类（Base class），以及带有默认构造函数和参数构造函数的派生类（derived class），并创建派生类的对象？

```java
class base1{

    public base1()

    {

        System.out.println("base default constructor called");

    }

    public base1(String t)

    {

        System.out.println("parameterized constructor base:"+t);

    }

}

class sub1 extends base1

{

    public sub1()

    {

      System.out.println("sub default constructor called");

    }

    public void sub1(String t) {

      super(t);

      System.out.println("parameterized constructor derived:"+t);

      }

}
```

```java
class inheri_demo1 {

  public static void main(String [] ra) {

    sub1 s=new sub1();

    sub1 s1=new sub1("hi");

  }

}
```

70. 编写一个 Java 类 “student”，它继承自 “person” 类。`person` 类拥有 `name` 和 `age` 成员，`student` 类拥有 `course` 成员？

```java
class Person {

  String name;

  int age;

  public void read(String n,int age) {

    name=n;

    this.age=age;

  }

  public void show() {

  System.out.println("Hello "+name);

  System.out.println("Age is "+age);

  }

}
```

```java
class student extends Person

{

    String course;

    public void get(String n,int a,String co)

    {

        read(n,a);

        course=co;

    }

    public void show()

    {

        super.show();

        System.out.println("course"+course);

    }

}

class inheri1

{

    public static void main(String [] arg)

    {

        student s=new student();

        s.get("rahul",22,"java");

        s.show();

    }

}
```

71. 创建一个 Java 类 “teacher”，具有如职称（助理教授、副教授）、学院名称等属性。创建 “physics” 和 “chemistry” 类，它们继承 “teacher” 类及其属性。

```java
class Teacher

{

    String designation = "Teacher";

    String collegeName = "SwatiComputers";

    public String getDesignation()

    {

        return designation;

    }

    protected void setDesignation(String designation)

    {

        this.designation = designation;

    }

    protected String getCollegeName()

    {

        return collegeName;

    }

    protected void setCollegeName(String collegeName)

    {

        this.collegeName = collegeName;

    }

    void does()

    {

        System.out.println("Teaching");

    }

}

class PhysicsTeacher extends Teacher

{}

class ChemistryTeacher extends Teacher

{}

Class teacher_demo{

    public static void main(String args[]){

    {

        PhysicsTeacher obj = new PhysicsTeacher();

        obj.does();

    }

}
```

## 抽象（ABSTRACTION）

抽象是隐藏实现细节并向用户展示功能的过程。换句话说，它是展示当前场景所需特征的过程。例如，如果你想开启风扇，你并不知道内部的处理过程。在 Java 中实现抽象有两种方式：

1. 抽象类（Abstract class）
2. 接口（Interface）

## 抽象类（Abstract class）

包含已实现和未实现方法的类被声明为 `abstract`。

- 抽象类不能实例化。
- 抽象类可能不包含抽象方法（例如没有主体的 `public void fun();`）。
- 使用抽象类必须继承另一个类，并对其所有抽象方法提供实现。
- 如果继承一个抽象类，派生类应该被声明为 `abstract`。

72. 编写一个 Java 类来解释抽象？

```java
abstract class abst

{

  public void x()

  {

    System.out.println("x() in abstract");

  }

  abstract void y();

}
```

```java
class abst_demo extends abst

{

    public void y()

    {

    System.out.println("y()");

    }

    public static void main(String [] ra)

    {

        abst_demo a=new abst_demo();

        a.x();

        a.y();

    }

}
```

73. 写一个抽象类 Base，创建两个继承 Base 类的类，并创建一个 Base 类的数组来调用方法？

```java
abstract class Base

{

    public void Base()

    {

        System.out.println("base() called");

    }

    abstract void call();

}
```

```java
class Base1 extends Base

{

    public void call()

    {

        System.out.println("a() called");

    }

}
```

```java
class Base2 extends Base

{

    public void call()

    {

        System.out.println("b() called");

    }

}

class instance_demo {

    public static void main(String[] sg) {

        Base1 b1=new Base1();

        Base2 b2=new Base2();

        Base[] b=new Base[2];

        b[0]=b1;

        b[1]=b2;

        for(int i=0;i<2;i++) {

            if(b[i] instanceof Base1) // 检查派生类引用是否在抽象类中

                ((Base1)b[i]).call(); // 类型转换，因为 b 是抽象类的引用变量

            } else {

                ((Base2)b[i]).call();

            }

        }

    }

}
```

## 接口（Interface）

接口是 Java 中的引用类型。它拥有静态常量和抽象方法。类可以实现多个接口，但只能扩展一个类。它用于在 Java 中实现抽象和多继承。它代表 IS-A 关系。

74. 创建两个接口和一个实现接口的类？

```java
interface intr

{

    public void put();

}

interface intr1

{

    final String name="SwatiComputers";

    public void display();

    public void get();

}

class intr_demo implements intr,intr1

{

    public void fun(){System.out.println("hello");}

    public void get(){}

    public void put()

    {

        //System.out.println(name);

        System.out.println("put() defined");

    }

    public static void main(String [] arg)

    {

        new intr_demo().put();

    }

}
```

75. 创建两个接口、一个继承另一个接口的接口以及一个实现接口的类？

```java
interface intr1

{

    public void x();

    public void y();

}

interface intr2

{

    public void z();

}

interface intr3 extends intr2 // 接口继承另一个接口

{

    public void a();

}

class intr_demo implements intr1,intr3 // 类可以实现多 1 个接口

{

    public void x()

    {

        System.out.println("x() of interface");

    }

    public void a()

    {

        System.out.println("a() called");

    }

    public void z()

    {

        System.out.println("z() called");

    }

    public void y() {}

    public static void main(String [] ar)

    {

        intr_demo d=new intr_demo();

        intr3 i=d;

        d.x();

        i.a();

        i.z();

    }

}
```

## 异常（EXCEPTION）

异常是运行时错误，可以通过异常处理机制处理以避免程序的异常终止。

## 异常类型（Type of Exception）

1. 检查异常（Checked）
2. 未检查异常（Unchecked）

## 异常处理关键字（Exception Handling Keywords）

```
try
catch
finally
throw
throws
```

76. 编写一个使用 BufferedReader 的 Java 类输入名称

```java
import java.util.*;

import java.io.*;

class exc

{

    public static void main(String [] ar)throws Exception

    {

        BufferedReader br=new BufferedReader(new InputStreamReader(System.in));

        System.out.println("Enter name");

        String name=br.readLine();

    }

}
```

77. 编写一个程序，使用命令行参数输入数字和字符串，并处理 `ArrayIndexOutOfBoundsException` 和 `NumberFormatException`？

```java
class exc1

{

    public static void main(String [] ar)

    {

        int w=6,r;

        try{

            int q=Integer.parseInt(ar[0]);

            System.out.println("q="+q);

            String n=ar[1];

            System.out.println(" n="+n);

            r=w/q;

            System.out.println("r="+r);

        }

        catch(NumberFormatException ex)

        {

            System.out.println("enter numeric value");

        }

        catch(ArrayIndexOutOfBoundsException ex)

        {

            System.out.println("enter 2 arguments");

        }

        catch(Exception ex)

        {

            System.out.println(ex.toString());

        }

        finally

        {

            System.out.println("i m ready to execute");

        }

    }

}
```

78. 编写一个 Java 程序，输入两个数字，如果数字为 0，则处理除以零异常（`ArithmeticException`）？

```java
import java.util.*;

class Excep1

{

    public static void main(String [] ar)

    {
```



`double c;`

`int a,b;`

`Scanner sc;`

`sc=new Scanner(System.in);`

`System.out.println("Enter 2 nos");`

```
try{
    a=sc.nextInt();
    b=sc.nextInt();
    c=a/b;
    System.out.println("Answer="+c);
}
catch (ArrayIndexOutOfBoundsException e)
{
    System.out.println(e.getMessage());
}
catch(Exception e)
{
    System.out.println(e.getMessage());
}
finally
{
    System.out.println("Finished");
}
```

## 79. 编写一个自定义异常来验证年龄是否小于18岁，如果是，则抛出青少年异常（teenage exception）？

```java
class myexp extends Exception
{
    public myexp(String er)
    {
        super(er);
    }
}

class vali_age
{
    public void valid(int ag)
    {
        try{
            if(ag<18)
                throw new myexp("teenager");
            else
                System.out.println("Hi");
        }
        catch(myexp e)
        {
            System.out.println(e.getMessage());
        }
    }
}

class validate
{
    public static void main(String [] ar)
    {
        try{
            vali_age v=new vali_age();
            v.valid(20);
            v.valid(12);
        }
        catch(Exception e)
        {
            System.out.println(e.getMessage());
        }
    }
}
```

## 80. 编写一个处理 `InputMismatchException` 的程序？

```java
import java.util.*;

class exc
{
    public static void main(String [] ar)
    {
        int age;
        Scanner sc=new Scanner(System.in);
        try {
            System.out.println("enter ur age");
            age=sc.nextInt();
            System.out.println("age is "+age);
        }
        catch(InputMismatchException ex)
        {
            System.out.println("Enter age in numbers..example:23");
        }
        System.out.println("thanks for using program");
    }
}
```

### try-with-resources 语句

在 Java 中，`try-with-resources` 语句是一种声明了一个或多个资源的 `try` 语句。资源是一个在程序结束后必须关闭的对象。`try-with-resources` 语句确保每个资源在语句执行结束时关闭。

## 81. 编写一个 Java 程序，使用多个资源的 `try with resource` 来打开文件中读取并写入数据？

```java
import java.io.DataInputStream;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.InputStream;

public class TryWithResources
{
    public static void main(String args[]) {
        try(FileOutputStream fileOutputStream = new FileOutputStream("abc.txt"),
             InputStream input = new FileInputStream("abc.txt")) {
            // 写入数据
            String msg = "Welcome to Swati";
            byte[] array = msg.getBytes(); // 将字符串转换为字节数组
            fileOutputStream.write(array); // 写入文件
            System.out.println("----------Data into file");
        } catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
    // 从文件中读取数据
    // 创建输入流
    // 从此流中可以读取的字节数
    // byte[] byteArray2 = new byte[data]; 
    // inst.read(byteArray2);
}
```

（注意：OCR 生成的代码不完整，“读取数据”的逻辑跨了页面）。

## 82. 编写一个 Java 类来重写方法并处理异常？

```java
import java.util.*;

class Parent
{
    void msg() throws Exception
    {
        System.out.println("parent");
    }
}

class TestChild extends Parent
{
    @Override
    void msg()
    {
        System.out.println("child");
    }
}

class BankDemo {
    public static void main(String [] args)
    {
        TestChild p = new TestChild();
        try {
            p.msg();
        } catch (ArithmeticException e) {
            System.out.println("Arithmetic error");
        } catch (Exception e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
```

## 83. 编写一个 Java 程序，处理取款时资金不足的情况，创建自定义异常？

```java
import java.io.*;

class InsufficientException extends Exception
{
    private double amount;
    public InsufficientException(double amount)
    {
        this.amount = amount;
    }
    public double getAmount()
    {
        return amount;
    }
}

class CheckingAccount
{
    private double balance;
    private int number;
    public CheckingAccount(int number)
    {
        this.number = number;
    }
    public void deposit(double amount)
    {
        balance += amount;
    }
    public void withdraw(double amount) throws InsufficientException
    {
        if (amount <= balance)
        {
            balance -= amount;
        }
        else
        {
            throw new InsufficientException(amount - balance);
        }
    }
    public double getBalance()
    {
        return balance;
    }
    public int getNumber()
    {
        return number;
    }
}

public class Main {
    public static void main(String[] args)
    {
        CheckingAccount c = new CheckingAccount(101);
        c.deposit(500);
        try {
            c.withdraw(100);
            System.out.println("Withdrawing 100...");
            c.withdraw(600);
            System.out.println("Withdrawing 600...");
        } catch (InsufficientException e) {
            System.out.println("Sorry, but you are short $" + e.getAmount());
        }
    }
}
```

## PACKAGE（包）

包是相似类型类、接口和子包的集合。它用于防止命名冲突。包提供了访问保护。包可以是内置的或自定义的。

`package` 关键字用于在 Java 中创建包。编译包中的类：`javac -d directory filename`

编译：`javac -d simple.java`
运行：`java mypack.simple`

## 84. 编写一个程序，在包中创建一个类并在另一个包中使用它？

```java
package pack;

public class A
{
    public void msg()
    {
        System.out.println("Hello");
    }
}
```

```java
package mypack;

import pack.*;

class B
{
    public static void main(String args[])
    {
        A obj = new A();
        obj.msg();
    }
}
```

## 85. 在包中编写一个 Java 类，使用变长参数（避免重载）来相许多不同的数字？

```java
package calci;

class use_packages
{
    int s=0;
    public void sum(int...a) // 变长参数
    {
        for(int i : a)
        {
            s+=i; // s=s+i
        }
        System.out.println("sum="+s);
    }
    public static void main(String [] aw)
    {
        new use_packages().sum(3,4,6);
        new use_packages().sum(3,4,6,7,3,2);
        new use_packages().sum(3,4,6,78,34,23,12);
    }
}
```

## 86. 在包 "a" 中创建一个类 A，在包 "a" 的子包中创建另一个类 A1，在包 "a" 中创建类 B 并在 B 类中创建 A 和 A1 的对象。

```java
package a;

public class A
{
    public A()
    {
        System.out.println("A class default constructor");
    }
}
```

```java
package a.a1;

public class A1
{
}
```

```java
{
    public A1() {
        System.out.println("A1 class default constructor");
    }
}
```

```java
package a;

import a.*;
import a.a1.*;

class B {
    public static void main(String[] dsf) {
        new A();
        new A1();
        System.out.println("B class");
    }
}
```

## 87. 在包 "p" 中创建一个类 "First"，在包 "q" 中创建另一个类 "Third"。在 Third 类中使用 First 类吗？

```java
package p;

public class First {
    public First1() {
        System.out.println("First1 called");
    }
    public String show() {
        return "welcome";
    }
}
```

```java
package p;

public class Second1
{
    public Second1()
    {
        System.out.println("Second1 called");
    }
    public static void main(String [] arg)
    {
        new First1();
    }
}
```

```java
package q;

import p.*;
import p.p1.*;

class Third1
{
    public static void main(String [] arg)
    {
        First1 f=new First1();
        System.out.println(f.show());
        new Second1();
        new Fourth1();
    }
}
```

## 88. 创建一个类 "address" 和另一个类 "employee"，在 "employee" 中使用 "address" 的引用吗？

```java
public class Address
{
    String city,state,country;
    public Address(String city, String state, String country)
    {
        this.city = city;
        this.state = state;
        this.country = country;
    }
}
```

```java
public class Emp {
    int id;
    String name;
    Address address;
    public Emp(int id, String name,Address address) {
        this.id = id;
        this.name = name;
        this.address=address;
    }
    void display() {
```



`System.out.println(id+""+name");`

`System.out.println(address.city+""+address.state+""+address.country);`

```
    }

    public static void main(String[] args) {

        Address address1=new Address("jpr","Raj","india");

        Address address2=new Address("ajmer","Raj","india");

        Emp e1=new Emp(111,"Shweta",address1);

        Emp e2=new Emp(112,"Swati",address2);

        e1.display();

        e2.display();

    }

}
```

## 89. 在包中创建一个接口，在同一包中创建一个类并实现该接口吗？

`package animals;`

```java
interface Animal {

    public void eat();

    public void travel();

}
```

`package animals;`

```java
public class Mammal implements Animal {

    public void eat() {

        System.out.println("Mammal eats");

    }

    public void travel() {

        System.out.println("Mammal travels");

    }

    public int noOfLegs() {

        return 0;

    }

    public static void main(String args[]) {

        Mammal m = new Mammal();

        m.eat();

        m.travel();

    }

}
```

## 集合与泛型

集合（Collection）是一个表示为单个单元的个体组。Java 提供了集合框架（Collection Framework），它定义了多个类和接口将一组对象表示为单个单元。

`Collection` 接口（`java.util.Collection`）和 `Map` 接口（`java.util.Map`）是 Java 集合类的两个主要根接口。

Java 集合是一个提供用于存储和操作对象组的框架。你对数据执行的所有操作（如搜索、排序、插入、删除等）都可以通过 Java 集合轻松完成。

集合框架包含以下内容：

- **接口（Interfaces）**：这些是表示集合的抽象类型。接口允许独立地操作集合。在面向对象的语言中，接口通常形成一个层次结构。
- **类（Classes）**：这些是接口的具体实现。它们是可重用的数据结构。
- **算法（Algorithms）**：这些是执行计算（如搜索和排序）的方法。算法被认为是多态的；即相同的方法可以用于许多不同的接口实现。

Java 集合框架提供了许多接口（`Set`、`List`、`Queue`、`Deque` 等）和类（`ArrayList`、`LinkedList`、`PriorityQueue`、`HashSet`、`LinkedHashSet` 等）。

泛型（Generics）帮助我们创建参数化的类、接口或方法。泛型增加了类型安全性。请记住，泛型仅作用于对象而不作用于基本类型。

## 90. 写一个程序在列表中添加和删除元素吗？

```java
import java.util.*;

public class ArrayListDemo

{

    public static void main(String args[])

    {

        // 创建列表

        ArrayList al = new ArrayList();

        System.out.println("初始大小: " + al.size());

        // 向列表添加元素

        al.add("C");

        al.add("A");

        al.add("D");

        al.add("E");

        al.add("F");

        System.out.println("添加后的大小: " + al.size());

        // 从列表中删除元素

        al.remove("F");

        al.remove(2);

        System.out.println("删除后的大小: " + al.size());

        // 显示列表

        System.out.println("内容: " + al);

    }

}
```

## 91. 在泛型中实现键值对吗？

```java
public class Pair<K, V>

{

    private K key;

    private V value;

    public Pair(K key, V value)

    {

        this.key = key;

        this.value = value;

    }

    public K getKey()

    {

        return key;

    }

    public V getValue()

    {

        return value;

    }

    public void setKey(K key)

    {

        this.key = key;

    }

    public void setValue(V value)

    {

        this.value = value;

    }

}
```

## 92. 创建一个 HashMap 并添加对象吗？

```java
public class MapDemo

{

    public static void main(String[] args)

    {

        Map<Integer, String> m = new HashMap<>();

        m.put(1, "A");

        m.put(2, "B");

        m.put(3, "C");

        m.put(4, "D");

        System.out.println("Keys: " + m.keySet());

        System.out.println("Values: " + m.values());

        System.out.println("Entries: " + m.entrySet());

        System.out.println("键 3 的值: " + m.get(3));

    }

}
```

## 93. 创建一个 TreeSet 并添加元素吗？

```java
public class SetDemo

{

    public static void main(String[] args)

    {

        Set<String> s = new TreeSet<>();

        s.add("apple");

        s.add("pear");

        s.add("banana");

        s.add("date");

        System.out.println("排序后的集合: " + s);

    }

}
```

## 94. 使用泛型在列表中添加整数吗？

```java
public class GenericList

{

    public static void main(String[] args)

    {

        ArrayList<Integer> a = new ArrayList<>();

        a.add(12);

        a.add(45);

        a.add(89);

        a.add(56);

        System.out.println(a);

    }

}
```

## 95. 创建一个单一泛型方法来打印不同类型的数组元素吗？

```java
public class GenericMethod{

    // 泛型方法 < E > static void printArray(E[] inputArray) {

        // 显示数组元素

        for(E element : inputArray) {

            System.out.printf("%s ", element);

        }

        System.out.println();

    }

    public static void main(String args[]) {

        // 创建 Integer, Double 和 Character 数组

        Integer[] intArray = { 1, 2, 3, 4, 5 };

        Double[] doubleArray = { 1.1, 2.2, 3.3, 4.4 };

        Character[] charArray = { 'H', 'E', 'L', 'L', 'O' };

        System.out.println("数组包含:");

        printArray(intArray); // 传递 Integer 数组

        System.out.println("数组数组包含:");

        printArray(doubleArray); // 传递 Double 数组

        System.out.println("字符数组包含:");

        printArray(charArray); // 传递 Character 数组

    }

}
```

## 96. 创建一个泛型类来添加整数和字符串吗？

```java
public class Box<T>

{

    private T t;

    public void add(T t)

    {

        this.t = t;

    }

    public T get()

    {

        return t;

    }

    public static void main(String[] args)

    {

        Box<Integer> integerBox = new Box<Integer>();

        Box<String> stringBox = new Box<String>();

        integerBox.add(new Integer(10));

        stringBox.add(new String("Hello World"));

        System.out.printf("整数值:%d\n\n", integerBox.get());

        System.out.printf("字符串值:%s\n", stringBox.get());

    }

}
```

## 97. 编写一个 Java 类，使用 `Comparable` 接口根据年龄对学生数据排序？

```java
class Student implements Comparable<Student>

{

    int rollno;

    String name;

    int age;

    Student(int rollno,String name,int age){

    this.rollno=rollno;

    this.name=name;

    this.age=age;

}

}
```

```java
public int compareTo(Student st)

{

    if(age==st.age)

        return 0;

    else if(age>st.age)

        return 1;

    else

        return -1;

}
```

```java
import java.util.*;

import java.io.*;

public class Sort {

    public static void main(String args[]){

    ArrayList<Student> al=new ArrayList<Student>();

    al.add(new Student(101,"Vijay",23));

    al.add(new Student(106,"Ajay",27));

    al.add(new Student(105,"Jai",21));

}
```

```java
Collections.sort(al);

for(Student st:al){

    System.out.println(st.rollno+" "+st.name+" "+st.age);

}
```

## 98. 编写一个 Java 类，使用优先级队列（`priority queue`）添加书籍（类）并打印它？

```java
import java.util.*;

class Book implements Comparable<Book>

{

    int id;

    String name,author,publisher;

    int quantity;

    public Book(int id, String name, String author, String publisher, int quantity) {

        this.id = id;

        this.name = name;

        this.author = author;

        this.publisher = publisher;

        this.quantity = quantity;

    }

    public int compareTo(Book b)

    {

        if(id>b.id){

            return 1;

        } else if(id<b.id){

            return -1;

        } else

        {

            return 0;

        }

    }

}

public class LinkedListExample {

    public static void main(String[] args) {

        Queue<Book> queue=new PriorityQueue<Book>();

        // 创建书籍

        Book b1=new Book(121,"C question Bank ","swati","BPB",8);

        Book b2=new Book(233,"java practical solution","swati","BPB",6);

        // 将书籍添加到队列

        queue.add(b1);

        queue.add(b2);

        System.out.println("正在遍历队列元素:");

        // 遍历队列元素

        for(Book b:queue){

            System.out.println(b.id+" "+b.name+" "+b.author+" "+b.publisher+" "+b.quantity);

        }

        queue.remove();

        System.out.println("移除一条书籍记录后:");

        for(Book b:queue){

            System.out.println(b.id+" "+b.name+" "+b.author+" "+b.publisher+" "+b.quantity);

        }

    }

}
```

## 99. 编写一个 Java 程序，使用枚举器（`enumeration`）显示哈希表（`hashtable`）的元素：

```java
import java.util.Enumeration;

import java.util.Hashtable;

public class Main {

    public static void main(String[] args) {

        Hashtable ht = new Hashtable();

        ht.put("1","One");

        ht.put("2", "Two");

        ht.put("3", "Three");

        Enumeration e = ht.elements();

        while(e.hasMoreElements()) {

          System.out.println(e.nextElement());

        }

    }

}
```




## 100. 编写一个程序，根据 `java.util.*;` 中的方法参数旋转 `List` 的元素

```java
import java.util.*;

public class Rotate_List {

  public static void main(String[] args) {

    List<String> list = new ArrayList<>(Arrays.asList("one two three four six".split(" ")));

    System.out.println("List: "+list);

    Collections.rotate(list, 3);

    System.out.println("rotate: " + list);

  }

}
```

## 101. 编写一个程序，搜索目录中所有以 `"s"` 开头的文件

```java
import java.io.*;

public class Display_files {

  public static void main(String[] args) {

    File dir = new File("C:");

    FilenameFilter filter = new FilenameFilter() {

      public boolean accept(File dir, String name) {

        return name.startsWith("s");

      }

    };

    String[] children = dir.list(filter);

    if (children == null) {

        System.out.println("该目录不存在或不是目录");

    } else {

        for (int i=0; i< children.length; i++) {

            String filename = children[i];

            System.out.println(filename);

        }

    }

  }

}
```

# Applet

Applet 是一种 Java 程序，可以嵌入到网页和浏览器内部，并在客户端运行。

## Java Applet 的生命周期

1. Applet 初始化（`init()`）
2. Applet 启动（`start()`）
3. Applet 绘制（`paint()`）
4. Applet 停止（`stop()`）
5. Applet 销毁（`destroy()`）

## AWT

AWT 代表 Abstract Window Toolkit（抽象窗口工具包）。

- 颜色、字体等
- UI 组件：`Button`、`TextField`
- 布局：`FlowLayout`、`BorderLayout`
- 容器：`Frame`、`Panel`
- 事件：`ActionListener`、`MouseListener`、`WindowListener` 等

## 102. 编写一个 Applet 显示欢迎消息并创建 HTML

```java
import java.applet.Applet;

import java.awt.*;

public class First extends Applet

{

    public void paint(Graphics g)

    {

        g.drawString("welcome swati",150,150);

    }

}
```

```html
<applet code="First" width="300" height="300"></applet>
```

## 103. 编写一个 Applet 设置背景颜色并输入名称

```java
import java.applet.Applet;

import java.awt.*;

public class app1 extends Applet {

  Font f;

  String s;

  Color c;

  public void init() {

    c=new Color(255,255,255);

    s=getParameter("surName");

    f=new Font("Times", Font.PLAIN, 24);

  }

  public void paint(Graphics g) {

    g.setColor(c);

    g.setFont(f);

    g.drawString("hello",50,50);

    g.drawString(s,200,50);

  }

}
```

```html
<applet code="app1" height="200" width="300">
```

## 104. 编写一个 Applet 绘制红色直线、绿色矩形、粉红色和蓝色正方形

```java
import java.applet.Applet;

import java.awt.*;

public class app1 extends Applet

{

    Font f;

    String s;

    Color c;

    public void init()

    {

        // 逻辑待实现

    }

    public void paint(Graphics g)

    {

        // 绘制逻辑待实现

    }

}
```

## 105. 编写一个登录框的 Applet，带有用户名、密码和登录按钮

```java
import java.applet.Applet;

import java.awt.*;

public class app3 extends Applet

{

    Label Iname,lpwd;

    TextField tn,tp;

    Button signin;

    public void init()

    {

        Iname=new Label("Enter name");

        lpwd=new Label("Enter password");

        tn=new TextField(10);

        tp=new TextField(10);

        tp.setEchoChar('*');

        signin=new Button("SignIn");

        add(Iname);

        add(tn);

        add(lpwd);

        add(tp);

        add(signin);

    }

}
```

## 106. 编写一个 Applet 输入用户名、密码、性别、课程，从列表选择国家并注册表单

```java
import java.applet.Applet;

import java.awt.*;

public class myap2 extends Applet

{

    Label un,lbl_pwd;

    TextField tun,txt_pwd;

    Button signIn,signUp;

    Checkbox c,cpp,java,male,female;

    Choice list;

    //FlowLayout flo;

    GridLayout glo;

    public void init()

    {

        glo=new GridLayout(6,2,10,10);

        setLayout(glo);

        un=new Label("Enter User Name");

        lbl_pwd=new Label("Enter password");

        tun=new TextField(10);

        txt_pwd=new TextField(10);

        txt_pwd.setEchoChar('*');

        signIn=new Button("SignIn");

        signUp=new Button("Register");

        CheckboxGroup cbg=new CheckboxGroup();

        male=new Checkbox("male",cbg,true);

        female=new Checkbox("female",cbg,false);

        list=new Choice();

        list.addItem("India");

        list.addItem("NZ");

        list.addItem("Eng");

        add(un);

        add(tun);

        add(lbl_pwd);

        add(txt_pwd);

        add(c=new Checkbox("C"));

        add(cpp=new Checkbox("C++"));

        add(java=new Checkbox("JAVA"));

        add(male);

        add(female);

        add(list);

    }

}
```

```java
add(male);

add(female);

add(list);

add(signIn);

add(signUp);

}

}
```

## 107. 创建 applet，绘制一条线并在线两端绘制四色圆

```java
import java.applet.Applet;

import java.awt.*;

/*

<applet code="myapp1.class" height="500" width="550">

<param name="myname" value="surabhi">

</applet>

*/

public class myapp1 extends Applet

{

    public void paint(Graphics g)

    {

        g.setColor(Color.blue);

        g.fillArc(100,100,100,100,0,90);

        g.setColor(Color.green);

        g.drawArc(100,100,100,100,90,90);

        g.fillArc(100,100,100,100,90,90);

        g.setColor(Color.yellow);

        g.fillArc(100,100,100,180,180,0);

        g.setColor(Color.red);

        g.fillArc(100,100,100,270,270,90);

        g.setColor(Color.blue);

        g.fillArc(400,100,100,100,0,90);

        g.setColor(Color.green);

        g.drawArc(400,100,100,100,90,90);

        g.fillArc(400,100,100,100,90,90);

        g.setColor(Color.yellow);

        g.fillArc(400,100,100,100,180,90);

        g.setColor(Color.red);

        g.fillArc(400,100,100,100,270,90);

        g.setColor(Color.black);

        g.drawLine(150,200,300,350);

        g.drawLine(450,200,300,350);

    }

}
```

## 108. 在 applet 中绘制一个四色球和一个多边形

```java
import java.applet.Applet;

import java.awt.*;

/*<applet code="poly.class" height=400 width=400></applet>*/

public class poly extends Applet {

    public void paint(Graphics g) 

    {

        g.setColor(Color.red);

        int[] x = new int[]{50, 100, 150};

        int[] y = new int[]{150, 50, 150};

        g.fillPolygon(x,y,3);

        g.setColor(Color.green);

        g.fillArc(50,300,100,100,0,90);

        g.setColor(Color.blue);

        g.fillArc(50,300,100,100,90,90);

        g.setColor(Color.yellow);

        g.fillArc(50,300,100,100,180,90);

        g.setColor(Color.pink);

        g.fillArc(50,300,100,100,270,90);

    }

}
```

## 109. 在 applet 中绘制印度（国旗）

```java
import java.applet.*;

import java.awt.*;

/*applet code="Flag.class" height=300 width=300></applet>*/

public class Flag extends Applet

{

    public void paint(Graphics g)

    {

        g.fillOval(60,450,120,50);

        g.fillRect(110,60,100,400);

        g.setColor(Color.red);

        g.fillRect(120,80,150,300);

        g.setColor(Color.white);

        g.fillRect(120,110,150,300);

        g.setColor(Color.green);

        g.fillRect(120,140,150,300);

        g.setColor(Color.black);

        g.drawRect(120,80,150,90);

        g.setColor(Color.blue);

        g.drawOval(180,110,30,30);

        int t=0;

        int x=195,y=125;

        double x1,y1;

        double r=15;

        double d;

        for(int i=1;i<=24;i++)

        {

            d=(double)t*3.14/180.0;

            x1=x+(double)r*Math.cos(d);

            y1=y+(double)r*Math.sin(d);

            g.drawLine((int)x,(int)y,(int)x1,(int)y1);

            t+=360/24;

        }

    }

}
```

## 110. 在 applet 中绘制九个颜色框




```java
import java.applet.*;
import java.awt.*;

/*applet code="Colors.class" height=300 width=300></applet*/
public class Colors extends Applet {
    public void paint(Graphics g) {
        g.setColor(Color.red);
        g.fillRect(0, 0, 40, 40);
        g.setColor(Color.pink);
        g.fillRect(50, 0, 40, 40);
        g.setColor(Color.green);
        g.fillRect(100, 0, 40, 40);

        g.setColor(Color.blue);
        g.fillRect(0, 50, 40, 40);
        g.setColor(Color.white);
        g.fillRect(50, 50, 40, 40);
        g.setColor(Color.yellow);
        g.fillRect(100, 50, 40, 40);

        g.setColor(Color.black);
        g.fillRect(0, 100, 40, 40);
        g.setColor(Color.green);
        g.fillRect(50, 100, 40, 40);
        g.setColor(Color.gray);
        g.fillRect(100, 100, 40, 40);
    }
}
```

### 111. 创建一个面板来添加总分和平均分

```java
import java.awt.*;
import java.applet.*;
import java.awt.event.*;

/*<applet code="Flag.class" width=400 height=400></applet>*/
class Flag extends Applet implements ActionListener, ItemListener {
    String s1, s2, s3;
    TextField t3, t4, t5, t6, t7;
    Button tot, avg;
    Checkbox c1, c2, c3, c4, m, f;
    CheckboxGroup cbg;
    Panel p1, p2, p3, p4;

    public void init() {
        s3 = "";

        tot = new Button("Total");
        avg = new Button("Average");

        c1 = new Checkbox("MCA", true);
        c2 = new Checkbox("Msc Comp");
        c3 = new Checkbox("MSIT");
        c4 = new Checkbox("MSIS");

        cbg = new CheckboxGroup();
        m = new Checkbox("Male", cbg, false);
        f = new Checkbox("Female", cbg, true);

        p1 = new Panel();
        p1.setLayout(new GridLayout(2, 2));
        p1.add(new Label("Student Number "));
        p1.add(new TextField(5));
        p1.add(new Label("Student Name "));
        p1.add(new TextField(15));
        add(p1);

        p2 = new Panel();
        p2.setLayout(new GridLayout(1, 3));
        p2.add(new Label("Gender"));
        p2.add(m);
        p2.add(f);
        add(p2);

        p3 = new Panel();
        p3.setLayout(new GridLayout(1, 5));
        p3.add(new Label("Degree"));
        p3.add(c1);
        p3.add(c2);
        p3.add(c3);
        p3.add(c4);
        add(p3);

        p4 = new Panel();
        p4.setLayout(new GridLayout(6, 2));
        p4.add(new Label("Marks in JAVA"));
        t3 = new TextField(3);
        p4.add(t3);

        p4.add(new Label("Marks in VB .Net"));
        t4 = new TextField(3);
        p4.add(t4);

        p4.add(new Label("Marks In C"));
        t5 = new TextField(3);
        p4.add(t5);

        p4.add(new Label("Total "));
        t6 = new TextField(3);
        p4.add(t6);

        p4.add(new Label(" Average "));
        t7 = new TextField(3);
        p4.add(t7);

        p4.add(tot);
        p4.add(avg);

        tot.addActionListener(this);
        avg.addActionListener(this);

        c1.addItemListener(this);
        c2.addItemListener(this);
        c3.addItemListener(this);
        c4.addItemListener(this);
        m.addItemListener(this);
        f.addItemListener(this);

        add(p4);
    }

    public void paint(Graphics g) {
        int no, m1, m2, m3, tot;
        float avg = 0.0f;
        no = m1 = m2 = m3 = tot;
    }
}
```

### 113. 创建一个带有四个按钮的 Frame，点击按钮时改变图像中心

```java
import java.awt.*;
import java.awt.event.*;

class Flag extends Frame implements ActionListener {
    Button b1, b2, b3, b4;
    Panel p, p1, p2, p3, p4;
    CardLayout cl;
    CheckboxGroup cbg;
    Checkbox m, f;
    Choice list;

    public Flag(String tit) {
        super(tit);

        add(b1 = new Button("1"), "North");
        add(b2 = new Button("2"), "West");
        add(b3 = new Button("3"), "East");
        add(b4 = new Button("4"), "South");

        p = new Panel();
        p1 = new Panel();
        p2 = new Panel();
        p3 = new Panel();
        p4 = new Panel();

        cl = new CardLayout();
        list = new Choice();
        list.addItem("Red");
        list.addItem("blue");
        list.addItem("green");
        list.addItem("white");

        p.setLayout(cl);

        cbg = new CheckboxGroup();
        m = new Checkbox("male", cbg, true);
        f = new Checkbox("female", cbg, false);

        p1.add(list);
        p2.add(new Checkbox("hi"));
        p3.add(new Button("Click"));
        p4.add(m);
        p4.add(f);

        p.add(p1, "1");
        p.add(p2, "2");
        p.add(p3, "3");
        p.add(p4, "4");

        add(p);

        b1.addActionListener(this);
        b2.addActionListener(this);
        b3.addActionListener(this);
        b4.addActionListener(this);

        setVisible(true);
        setSize(400, 400);
    }

    public void actionPerformed(ActionEvent ae) {
        if (ae.getSource() == b1) {
            cl.show(p, "1");
        } else if (ae.getSource() == b2) {
            cl.show(p, "2");
        } else if (ae.getSource() == b3) {
            cl.show(p, "3");
        } else if (ae.getSource() == b4) {
            cl.show(p, "4");
        }
    }
}
```

### 114. 绘制一个窗口并在点击单选框（radio button）时显示消息？

```java
import java.awt.event.*;
import java.awt.*;

class fra7 extends Frame implements ItemListener {
    Checkbox m, f;
    CheckboxGroup cbg;
    Label res;

    public fra7(String tit) {
        super(tit);

        setLayout(new GridLayout(2, 2, 10, 10));

        cbg = new CheckboxGroup();
        m = new Checkbox("male", cbg, true);
        f = new Checkbox("female", cbg, false);
        res = new Label("Message");

        add(m);
        add(f);
        add(res);

        m.addItemListener(this);
        f.addItemListener(this);
    }

    setSize(200, 200);
    setVisible(true);

    public void itemStateChanged(ItemEvent e) {
        if (m.getState() == true) {
            res.setText("Hello man");
        } else if (f.getState() == true) {
            res.setText("Hello maam");
        }
    }
}

class fra7_demo {
    public static void main(String[] args) {
        new fra7("hi");
    }
}
```

### 115. 绘制一个窗口以实现 KeyListener，在输入或按下键码时应显示内容？

```java
import java.awt.event.*;
import java.awt.*;

class fra8 extends Frame implements KeyListener {
    int x;
    char c;
    Label res;

    public fra8(String tit) {
        super(tit);

        setLayout(new FlowLayout());
        addKeyListener(this);
        add(res = new Label("Answer"));

        addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent we) {
                System.exit(0);
            }

            public void windowIconified(WindowEvent we) {
                setVisible(false);
            }
        });

        setSize(300, 300);
        setVisible(true);
    }

    public void keyPressed(KeyEvent ke) {
        x = ke.getKeyCode();
        res.setText("");
        res.setText("" + x);
    }

    public void keyReleased(KeyEvent ke) {
    }

    public void keyTyped(KeyEvent ke) {
        c = ke.getKeyChar();
        res.setText("");
        res.setText("" + c);
    }
}

class fra8_demo {
    public static void main(String[] args) {
        new fra8("hi");
    }
}
```

### 116. 绘制一个窗口在复选框（checkbox）和单选框上实现 itemListener？

```java
import java.awt.*;
import java.awt.event.*;

class scomp1 extends Frame implements ItemListener {
    // Button scom1

    Label basic, java, develop, combo, scom, chos1, chos2;
    Checkbox core, adv, comp, cpp, comb1, comb2;
    CheckboxGroup b1, cp1;
    Choice l;

    public scomp1(String tt) {
        super(tt);

        setLayout(null);

        scom = new Label("SWATI COMPUTERS");
        chos = new Label("");
        chos1 = new Label("");
        chos2 = new Label("");

        l = new Choice();

        cp1 = new CheckboxGroup();
        b1 = new CheckboxGroup();

        basic = new Label("basic");
        java = new Label("java");
        develop = new Label("developing");
        combo = new Label("combo packs");

        core = new Checkbox("Core");
        adv = new Checkbox("Advance");
        comp = new Checkbox("Complete");

        c = new Checkbox("C", b1, true);
        cpp = new Checkbox("C++", b1, false);

        comb1 = new Checkbox("C,C++,Core", cp1, true);
        comb2 = new Checkbox("Core,Advance", cp1, false);

        l.add("java");
        l.add(".net");
        l.add("pta nii");

        scom.setBounds(150, 500, 300, 20);
        chos1.setBounds(150, 520, 300, 20);
        chos2.setBounds(150, 540, 300, 20);
    }
}
```



`setBounds(250,100,150,30)` 设置组件位置和大小。

`basic.setBounds(100,150,150,20)`、`java.setBounds(400,150,50,20)`、`develop.setBounds(100,300,150,20)`、`combo.setBounds(400,300,150,20)`、`core.setBounds(400,230,100,20)`、`adv.setBounds(400,250,100,20)`、`comp.setBounds(400,210,100,20)`、`c.setBounds(100,210,150,20)`、`cpp.setBounds(100,230,150,20)`、`comb1.setBounds(400,320,150,20)`、`comb2.setBounds(400,340,150,20)`、`l.setBounds(100,320,150,20)` 分别设置各组件的位置和大小。

然后依次将组件添加到容器中：`add(scom)`、`add(chos)`、`add(chos1)`、`add(chos2)`、`add(l)`、`add(basic)`、`add(java)`、`add(develop)`、`add(combo)`、`add(core)`、`add(adv)`、`add(comp)`、`add(c)`、`add(cpp)`、`add(comb1)`、`add(comb2)`。

```
public void itemStateChanged(ItemEvent ie)
{
    if(c.getState()==true)
        chos.setText("you have chosen C in basics");
    if(cpp.getState()==true)
        chos.setText("you have chosen C++ language in basics");
    if(comb1.getState()==true)
        chos1.setText("you have chosen a combo of C++,core languages");
    if(comb2.getState()==true)
        chos1.setText("you have chosen a combo of core,advance languages");
    if(comp.getState()==true)
        chos2.setText("you have chosen Complete part in java");
    if(core.getState()==true)
        chos2.setText("you have chosen Core part in java");
    if(adv.getState()==true)
        chos2.setText("you have chosen advance part in java");
}
```

```
class scomp
{
    public static void main(String [] args)
    {
        new scomp1("hi");
    }
}
```

## 17. 绘制一个窗口实现 `Mouse` 和 `MouseListener` 来显示鼠标的位置

```java
import java.awt.*;
import java.awt.event.*;

class myfr7 extends Frame implements ActionListener,MouseListener
{
    Button b1,b2,b3,b4;
    TextField t;
    Label m;

    public myfr7(String tit)
    {
        super(tit);
        setLayout(null);
        m=new Label(" ");
        t=new TextField(20);
        b1=new Button("1");
        b2=new Button("2");
        b3=new Button("3");
        b4=new Button("4");
        b1.addActionListener(this);
        b2.addActionListener(this);
        b3.addActionListener(this);
        b4.addActionListener(this);
        t.setBounds(50,200,150,30);
        b1.setBounds(30,50,50,20);
        b2.setBounds(100,50,50,20);
        b3.setBounds(30,100,50,20);
        b4.setBounds(100,100,50,20);
        m.setBounds(200,200,100,30);
        addActionListener(this);
        addMouseListener(this);
        add(t);
        add(b1);
        add(b2);
        add(b3);
        add(b4);
        add(m);
        addWindowListener(new WindowAdapter() {
          public void windowClosing(WindowEvent e) {
            dispose();
          }
        });
        setSize(300,300);
        setVisible(true);
    }

    public void mouseMoved(MouseEvent me)
    {
        t.setText("position: x="+me.getX()+",y="+me.getY());
    }

    public void mouseDragged(MouseEvent me){}

    public void mouseClicked(MouseEvent me)
    {
        t.setText("Clicked");
    }

    public void mouseEntered(MouseEvent me)
    {
        t.setText("Entered");
    }

    public void mouseExited(MouseEvent me)
    {
        t.setText("Exited");
    }

    public void mousePressed(MouseEvent me)
    {
        t.setText("pressed");
    }

    public void mouseReleased(MouseEvent me)
    {
        m.setText("Released");
    }

    public void actionPerformed(ActionEvent ae)
    {
    }
}

class frm7
{
    public static void main(String [] arg)
    {
        new myfr7("hi");
    }
}
```

## 118. 绘制一个窗口实现 `ItemListener` 并从复选框显示选课程

```java
import java.awt.*;
import java.awt.event.*;

class myfr8 extends Frame implements ItemListener
{
    Checkbox c,cpp;
    int i;
    Label msg;
    String s="",s1="";

    public myfr8(String tit) {
        super(tit);
        setLayout(new FlowLayout());
        add(c=new Checkbox("C"));
        add(cpp=new Checkbox("C++"));
        add(msg=new Label("Nothing Selected"));
        c.addItemListener(this);
        cpp.addItemListener(this);
        setSize(200,200);
        setVisible(true);
    }

    public void itemStateChanged(ItemEvent ie)
    {
        if(ie.getSource()==c) {
            if(c.getState()==true) {
                s=s+"C";
            } else
                s="";
        }
        if(ie.getSource()==cpp) {
            if(cpp.getState()==true) {
                s1=s1+"cpp";
            } else
                s1="";
        }
        msg.setText(s+" "+s1);
    }
}

class frm8
{
    static public void main(String [] args)
    {
        new myfr8("hi");
    }
}
```

## 119. 编写一个 `Applet`，点击按钮时移动图像上、下、左、右

```java
import java.applet.Applet;
import java.util.*;
import java.awt.*;
import java.awt.event.*;

/*applet code="imgs12.class" height=500 width=500>
</applet>
*/

public class imgs12 extends Applet implements ActionListener,KeyListener
{
  Image img;
  int x,y=110,z=110,tn=110;
  Label res;
  Scanner sc;
  Button left,right,up,down;

  public void init()
  {
    img=getImage(getDocumentBase(),"12.jpg");
  }
```

```java
left=new Button("Left");
right=new Button("right");
up=new Button("up");
down=new Button("down");
add(res=new Label(""));
add(left);
add(right);
add(up);
add(down);
left.addActionListener(this);
up.addActionListener(this);
down.addActionListener(this);
right.addActionListener(this);
addKeyListener(this);
```

```java
public void keyPressed(KeyEvent ke) {
  y=ke.getKeyCode();
  //res.setText(""+y);
  if(y==37)
    z=z-10;
  if(y==38)
    tn=tn-10;
  if(y==39)
    z=z+10;
  if(y==40)
    tn=tn+10;
  repaint();
}
```

```java
public void keyReleased(KeyEvent ke) {
}

public void actionPerformed(ActionEvent ae) {
  if(ae.getSource()==left)
    z=z-10;
  if(ae.getSource()==up)
    tn=tn-10;
  if(ae.getSource()==right)
    z=z+10;
  if(ae.getSource()==down)
    tn=tn+10;
  repaint();
}

public void paint(Graphics g)
{
  g.drawString(""+y,100,100);
  g.drawImage(img,z,tn,this);
}
```

## 120. 编写一个程序创建菜单栏（`MenuBar`）、菜单项（`MenuItem`）和子菜单（`Sub Menu`）

```java
import java.awt.*;

class MenuExample {
  MenuExample(){
    Frame f=new Frame("Menu and MenuItem Example");
    MenuBar mb=new MenuBar();
    Menu menu=new Menu("Menu");
    Menu submenu=new Menu("Sub Menu");
    MenuItem i1=new MenuItem("Item 1");
    MenuItem i2=new MenuItem("Item 2");
    MenuItem i3=new MenuItem("Item 3");
    MenuItem i4=new MenuItem("Item 4");
    MenuItem i5=new MenuItem("Item 5");
    menu.add(i1);
    menu.add(i2);
    menu.add(i3);
    submenu.add(i4);
    submenu.add(i5);
```

```java
menu.add(submenu);
mb.add(menu);
f.setMenuBar(mb);
f.setSize(400,400);
f.setLayout(null);
f.setVisible(true);
```

```java
}

public static void main(String args[])
{
  new MenuExample();
}
}
```

## 121. 编写一个程序创建弹出菜单（`PopupMenu`）

```java
import java.awt.*;
import java.awt.event.*;

class PopupMenuExample
{
  PopupMenuExample(){
    final Frame f= new Frame("PopupMenu Example");
    final PopupMenu popupmenu = new PopupMenu("Edit");
    MenuItem cut = new MenuItem("Cut");
    cut.setActionCommand("Cut");
    MenuItem copy = new MenuItem("Copy");
    copy.setActionCommand("Copy");
    MenuItem paste = new MenuItem("Paste");
    paste.setActionCommand("Paste");
    popupmenu.add(cut);
    popupmenu.add(copy);
    popupmenu.add(paste);
    f.addMouseListener(new MouseAdapter(){
      public void mouseClicked(MouseEvent e) {
        popupmenu.show(f, e.getX(), e.getY());
      }
    }
    );
    f.add(popupmenu);
    f.setSize(400,400);
    f.setLayout(null);
    f.setVisible(true);
  }

  public static void main(String args[])
  {
    new PopupMenuExample();
  }
}
```

# 适配器类（`Adapter Class`）

适配器类提供了监听器接口的默认实现。如果你继承适配器类，就不会强制提供监听器接口中所有方法的实现。因此它可以节省代码。

## 122. 编写一个程序在鼠标点击时画一个圆

```java
import java.awt.*;
import java.awt.event.*;

public class C_Mouse extends MouseAdapter
{
    Frame f;

    C_Mouse(){
```



### 123. 编写一个程序在点击按钮时打开对话框？

```java
import java.awt.*;
import java.awt.event.*;

public class Ex_Dialog extends WindowAdapter implements ActionListener {
    Frame frame;
    Label label1;
    TextField field1;
    Button button1, button2, button3;
    Dialog d1, d2, d3;

    Ex_Dialog() {
        frame = new Frame("Frame");
        button1 = new Button("Open Dialog");
        label1 = new Label("Click on the button to open a Dialog");
        frame.add(label1);
        frame.add(button1);
        button1.addActionListener(this);
        frame.pack();
        frame.setLayout(FlowLayout());
        frame.setSize(330, 250);
        frame.setVisible(true);
    }

    public void actionPerformed(ActionEvent ae) {
        if (ae.getActionCommand().equals("Open Dialog")) {
            d1 = new Dialog(frame, "Modal Dialog", true);
            d1.addWindowListener(this);
            d1.pack();
            d1.setLocationRelativeTo(frame);
            d1.setSize(400, 200);
            d1.setVisible(true);
        }
    }

    public void windowClosing(WindowEvent ae) {
        d1.setVisible(false);
    }

    public static void main(String args[]) {
        new Ex_Dialog();
    }
}
```

### 124. 编写一个程序使用 `CardLayout` 并在点击时切换按钮？

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

public class CardLayoutExample extends JFrame implements ActionListener {
    CardLayout card;
    JButton b1, b2, b3;
    Container c;

    CardLayoutExample() {
        c = getContentPane();
        card = new CardLayout(40, 30);
        c.setLayout(card);
        b1 = new JButton("C");
        b2 = new JButton("C");
        b3 = new JButton("JAVA");
        b1.addActionListener(this);
        b2.addActionListener(this);
        b3.addActionListener(this);
        c.add("a", b1);
        c.add("b", b2);
        c.add("c", b3);
    }

    public void actionPerformed(ActionEvent e) {
        card.next(c);
    }

    public static void main(String[] args) {
        CardLayoutExample cl = new CardLayoutExample();
        cl.setSize(400, 400);
        cl.setVisible(true);
        cl.setDefaultCloseOperation(EXIT_ON_CLOSE);
    }
}
```

### 125. 编写一个 Java 程序在点击按钮时将 `CardLayout` 改为 `BorderLayout`？请你自己实现。

### 126. 在 Java frame 中创建一个小型计算器？

```java
import java.awt.event.*;
import java.awt.*;
import java.awt.event.WindowEvent;

class myfra1 extends Frame implements ActionListener {
    TextField t;
    Button b1, b2, b3, b4, b5, b6, b7, b8, b9, b0, bplus, bequal, bulti, div, clear, bclear;
    char op;
    String val, val1;
    int ans;
    Panel p;

    public myfra1(String tit) {
        super(tit);
        setLayout(new FlowLayout());
        t = new TextField(10);
        b1 = new Button("1");
        b2 = new Button("2");
        b3 = new Button("3");
        b4 = new Button("4");
        b5 = new Button("5");
        b6 = new Button("6");
        b7 = new Button("7");
        b8 = new Button("8");
        b9 = new Button("9");
        b0 = new Button("0");
        clear = new Button("C");
        p = new Panel();
        p.setLayout(new GridLayout(4, 4));
        bplus = new Button("+");
        bminus = new Button("-");
        bequal = new Button("=");
        bulti = new Button("*");
        div = new Button("/");
        b1.addActionListener(this);
        b2.addActionListener(this);
        b3.addActionListener(this);
        b4.addActionListener(this);
        b5.addActionListener(this);
        b6.addActionListener(this);
        b7.addActionListener(this);
        b8.addActionListener(this);
        b9.addActionListener(this);
        b0.addActionListener(this);
        clear.addActionListener(this);
        bplus.addActionListener(this);
        bminus.addActionListener(this);
        bulti.addActionListener(this);
        div.addActionListener(this);
        bequal.addActionListener(this);
        add(t);
        p.add(b1); p.add(b2); p.add(b3); p.add(b4); p.add(b5); p.add(b6); p.add(b7);
        p.add(b8); p.add(b9); p.add(b0);
        p.add(bplus); p.add(bminus); p.add(bulti); p.add(bdiv);
        p.add(bequal); p.add(bclear);
        add(p);
        addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent e) {
                System.exit(0);
            }
        });
        setLocation(300, 300);
        // frame class function to set height, width of frame
        setVisible(true);
    }

    public void actionPerformed(ActionEvent ae) {
        if (ae.getSource() == b1) {
            t.setText(t.getText() + "1");
        }
        if (ae.getSource() == b2) {
            t.setText(t.getText() + "2");
        }
        if (ae.getSource() == b3) {
            t.setText(t.getText() + "3");
        }
        if (ae.getSource() == b4) {
            t.setText(t.getText() + "4");
        }
        if (ae.getSource() == b5) {
            t.setText(t.getText() + "5");
        }
        if (ae.getSource() == b6) {
            t.setText(t.getText() + "6");
        }
        if (ae.getSource() == b7) {
            t.setText(t.getText() + "7");
        }
        if (ae.getSource() == b8) {
            t.setText(t.getText() + "8");
        }
        if (ae.getSource() == b9) {
            t.setText(t.getText() + "9");
        }
        if (ae.getSource() == b0) {
            t.setText(t.getText() + "0");
        }
    }
}
```

```java
t.setText("");
}

if (ae.getSource() == bclear) {
    t.setText("");
    op = '=';
}

if (ae.getSource() == bdiv) {
    op = '/';
    val = t.getText();
    t.setText("");
}

if (ae.getSource() == bequal) {
    val1 = t.getText();
    switch (op) {
        case '+':
            ans = Integer.parseInt(val) + Integer.parseInt(val1);
            break;
        case '-':
            ans = Integer.parseInt(val) - Integer.parseInt(val1);
            break;
        case '*':
            ans = Integer.parseInt(val) * Integer.parseInt(val1);
            break;
        case '/':
            ans = (int) (Integer.parseInt(val) / Integer.parseInt(val1));
            break;
    }
    t.setText(String.valueOf(ans));
}
}
```

```java
public class calci1 {
    public static void main(String[] ar) {
        new myfra1("calculator");
    }
}
```

### 127. 写一个 applet，使用 `GridBagLayout` 并显示复选框选中时的状态？

```java
import java.awt.*;
import java.awt.event.*;
import java.awt.applet.*;

/*
<applet code="GridBagDemo.class" width=250 height=200>
</applet>
*/

public class GridBagDemo extends ItemListener {
    String msg = "";
    Checkbox winXP, winVista, solaris, mac;

    public void init() {
        GridBagLayout gbag = new GridBagLayout();
        GridBagConstraints gbc = new GridBagConstraints();
        setLayout(gbag);

        // 定义复选框。
        winXP = new Checkbox("Windows XP ", null, true);
        winVista = new Checkbox("Windows Vista");
        solaris = new Checkbox("Solaris");
        mac = new Checkbox("Mac OS");

        // 定义 grid bag。
        // 第一行使用默认行权重为 0。
        gbc.weightx = 1.0; // 使用列权重 1
        gbc.ipadx = 200; // 留边 200 单位
        gbc.insets = new Insets(4, 4, 0, 0); // 从左上略微偏移
        gbc.anchor = GridBagConstraints.SOUTHWEST;
        gbc.gridwidth = GridBagConstraints.NONE;
        gbag.setConstraints(winXP, gbc);
        gbc.gridwidth = GridBagConstraints.REMAINDER;
        gbag.setConstraints(winVista, gbc);

        // 给第二行赋予权重 1。
        gbc.weighty = 1.0;
        gbc.gridwidth = GridBagConstraints.RELATIVE;
        gbag.setConstraints(solaris, gbc);
        gbc.gridwidth = GridBagConstraints.REMAINDER;
        gbag.setConstraints(mac, gbc);

        // 添加组件。
        add(winXP);
        add(winVista);
        add(solaris);
        add(mac);

        // 注册以接收项目事件。
        winXP.addListener(this);
        winVista.addListener(this);
        solaris.addListener(this);
        mac.addListener(this);
    }

    // 当复选框状态改变时重绘。
    public void itemStateChanged(Event ie) {
        repaint();
    }

    // 显示复选框的当前状态。
    public void paint(Graphics g) {
        msg = "Current state: ";
        g.drawString(msg, 6, 80);
        msg = "Windows XP: " + winXP.getState();
        g.drawString(msg, 6, 100);
        msg = "Windows Vista: " + winVista.getState();
        g.drawString(msg, 6, 120);
    }
}
```



### 128. 在 `Frame` 上创建一个 `Label`，并在按下键盘方向键时移动它？

```java
import java.awt.*;
import java.awt.event.*;

class myfr4 extends Frame implements KeyListener {

  char ch;
  Label charc, code, move;
  int x, y;

  public myfr4(String tit) {
    super(tit);
    x = 100;
    y = 100;
    // setLayout(new FlowLayout());
    setLayout(null);
    charc = new Label("Character pressed");
    code = new Label("code");
    move = new Label("moving");
    charc.setBounds(10, 10, 50, 20);
    code.setBounds(70, 10, 50, 20);
    move.setBounds(x, y, 40, 20);
    add(move);
    addKeyListener(this);
    setSize(300, 300);
    setVisible(true);
  }

  public void keyTyped(KeyEvent ke) {
    ch = ke.getKeyChar();
    charc.setText("Character:" + ch);
  }

  public void keyPressed(KeyEvent e) {
    int w = e.getKeyCode();
    if (w == KeyEvent.VK_UP) {
      code.setText("up key");
      move.setBounds(x, y - 10, 20);
    } else if (w == KeyEvent.VK_DOWN) {
      code.setText("down key");
      move.setBounds(x, y + 10, 20);
    } else if (w == KeyEvent.VK_LEFT) {
      code.setText("left key");
      move.setBounds(x - 10, y, 20);
    } else if (w == KeyEvent.VK_RIGHT) {
      code.setText("right key");
      move.setBounds(x + 10, y, 20);
    }
    code.setText("Code:" + w);
  }

  public void keyReleased(KeyEvent e) {}
}

class myfr4_demo {
  public static void main(String[] ar) {
    new myfr4("hi");
  }
}
```

### 129. 创建一个 Java `Frame` 显示鼠标位置，使用 `MouseListener`

```java
import java.awt.*;
import java.awt.event.*;

class myfr3 extends Frame implements MouseListener {
  Label p, status, r;
  int x, y;

  public myfr3(String tit) {
    super(tit);
    setLayout(new FlowLayout());
    add(status = new Label("Status"));
    add(p = new Label("position"));
    add(r = new Label("hello"));
    addMouseListener(this);
    setSize(300, 300);
    setVisible(true);
  }

  public void mouseClicked(MouseEvent e) {
    status.setText("clicked");
    x = e.getX();
    y = e.getY();
    p.setText(x + "," + y);
  }

  public void mouseEntered(MouseEvent e) {
    status.setText("entered");
    x = e.getX();
    y = e.getY();
    p.setText(x + "," + y);
  }

  public void mouseExited(MouseEvent e) {
    status.setText("exited");
    x = e.getX();
    y = e.getY();
    p.setText(x + "," + y);
  }

  public void mousePressed(MouseEvent e) {
    status.setText("pressed");
    x = e.getX();
    y = e.getY();
    p.setText(x + "," + y);
  }

  public void mouseReleased(MouseEvent e) {
    r.setText("released");
    x = e.getX();
    y = e.getY();
    p.setText(x + "," + y);
  }
}

class myfr3_demo {
  public static void main(String[] ra) {
    new myfr3("hi");
  }
}
```

### 130. 创建一个 `frame`，在另一个文本框写入内容时更改文本框文本，并使用 `windowListener` 关闭 `Frame`

```java
import java.awt.*;
import java.awt.event.*;

class myfr2 extends Frame implements TextListener, WindowListener {
  TextField t1, t2;

  public myfr2(String tit) {
    super(tit);
    setLayout(new FlowLayout());
    add(t1 = new TextField(10));
    add(t2 = new TextField(10));
    t1.addTextListener(this);
    addWindowListener(this);
    addWindowListener(new WindowAdapter());
    setSize(300, 300);
    setVisible(true);
  }

  public void textValueChanged(TextEvent et) {
    t2.setText(t1.getText());
  }

  public void windowOpened(WindowEvent we) {}
  public void windowClosed(WindowEvent we) {}
  public void windowClosing(WindowEvent we) {
    System.exit(1);
  }
  public void windowIconified(WindowEvent we) {}
  public void windowDeiconified(WindowEvent we) {}
  public void windowActivated(WindowEvent we) {}
  public void windowDeactivated(WindowEvent we) {}
}

class myfr2_demo {
  public static void main(String[] ar) {
    new myfr2("hi");
  }
}
```

### 131. 画一个 `Frame`，使用 `CardLayout` 和 `BorderLayout` 在点击按钮时进行切换？

```java
import java.awt.*;
import java.awt.event.*;

class myfr1 extends Frame implements ActionListener {
  Button b1, b2, b3, b4, b5;
  TextField t1;
  Panel p, p1, p2, p3, p4;
  Choice list;
  CardLayout clo;

  public myfr1(String tit) {
    super(tit);
    b1 = new Button("1");
    b2 = new Button("2");
    b3 = new Button("3");
    b4 = new Button("4");
    b5 = new Button("5");
    p = new Panel();
    p1 = new Panel();
    p2 = new Panel();
    p3 = new Panel();
    p4 = new Panel();
    t1 = new TextField(10);
    clo = new CardLayout();
    p.setLayout(clo);
    p1.add(t1);
    p2.add(b1);
    p3.add(new Label("Third"));
    p4.add(new Label("fourth"));
    list = new Choice();
    list.addItem("dairy milk");
    list.addItem("temptation");
    p4.add(list);
    p.add(p1, "first");
    p.add(p2, "sec");
    p.add(p3, "thir");
    p.add(p4, "four");
    add(p, "Center");
    add(b2, "South");
    add(b3, "East");
    add(b4, "West");
    add(b5, "North");
    // b1.addActionListener(ts);
    b2.addActionListener(this);
    b3.addActionListener(this);
    b4.addActionListener(this);
    b5.addActionListener(this);
    setSize(200, 200);
    setVisible(true);
  }

  public void actionPerformed(ActionEvent ae) {
    if (ae.getSource() == b5)
      clo.show(p, "first");
    else if (ae.getSource() == b2)
      clo.show(p, "sec");
    else if (ae.getSource() == b3)
      clo.show(p, "thir");
    else if (ae.getSource() == b4)
      clo.show(p, "four");
  }
}
```

# 多线程

多线程是同时执行多个线程的过程。多线程程序包含两个或多个可以并发运行的部分，每个部分可以同时处理不同的任务。

线程共享公共内存区域。它们不分配独立的内存区域，因此节省了内存，而且线程之间的上下文切换比进程消耗的时间更短。

创建线程有两种方法：

1. 通过继承 `Thread` 类
2. 通过实现 `Runnable` 接口。

### 132. 编写一个 applet 让球在屏幕上移动

```java
import java.applet.Applet;
import java.awt.*;

/*<applet code="trap.class" height=200 width=400></applet>*/
public class trap extends Applet implements Runnable {
  Thread t;
  int x;

  public void init() {
    t = new Thread(this, "my thread");
    x = 400;
    t.start();
  }

  public void run() {
    while (true) {
      try {
        repaint();
        if (x <= 0)
          x = 400;
        else
          x = x - 10;
        Thread.sleep(300);
      } catch (Exception ex) {}
    }
  }

  public void paint(Graphics g) {
    g.setColor(Color.red);
    g.fillOval(x, 20, 50, 50);
  }
}
```

### 133. 编写一个 Java applet 让球在屏幕上交替移动

```java
import java.applet.Applet;
import java.awt.*;

/*<applet code="trap1.class" height=200 width=400></applet>*/
public class trap1 extends Applet implements Runnable {
  Thread t;
  int x, y;

  public void init() {
    t = new Thread(this, "my thread");
    x = 0;
    y = 0;
    t.start();
  }

  public void run() {
    while (true) {
      try {
        repaint();
        if (y == 0) {
          if (x >= 400) {
            y = 1;
          } else {
            x = x + 10;
          }
        } else if (y == 1) {
          if (x <= 0) {
            y = 0;
          } else {
            x = x - 10;
          }
        }
        Thread.sleep(300);
      } catch (Exception ex) {}
    }
  }

  public void paint(Graphics g) {
    g.setColor(Color.red);
    g.fillOval(x, 20, 50, 50);
  }
}
```

### 134. 创建一个数字时钟

```java
import javax.swing.*;
import java.awt.*;
import java.text.*;
import java.util.*;

public class DigitalWatch implements Runnable {
  JFrame f;
  Thread t = null;
  int hours = 0, minutes = 0, seconds = 0;
  String timeString = "";
  JButton b;

  DigitalWatch() {
    f = new JFrame();
    t = new Thread(this);
    t.start();
    b = new JButton();
    b.setBounds(100, 100, 100, 50);
    f.add(b);
    f.setSize(300, 400);
    f.setLayout(null);
    f.setVisible(true);
  }
}
```



135. 编写一个 Java 程序来模拟交通灯。

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

public class TrafficLight extends JFrame implements Runnable {
    JButton red, green, yellow;

    TrafficLight() {
        setTitle("TrafficLight");
        setSize(500,500);
        setDefaultCloseOperation(JFrame.EXIT_CLOSE);
        red = new JButton();
        yellow = new JButton();
        green = new JButton();
        setLayout(new GridLayout(3,1));
        add(red);
        add(yellow);
        add(green);
        Thread t = new Thread(this);
        t.start();
    }

    public void run() {
        while(true) {
            Thread turnRed = new Thread(TurnRed());
            turnRed.start();
            synchronized(turnRed) {
                try { turnRed.wait(); } catch (InterruptedException e) {}
            }
            Thread turnYellow = new Thread(TurnYellow());
            turnYellow.start();
            synchronized(turnYellow) {
                try { turnYellow.wait(); } catch (InterruptedException e) {}
            }
            Thread turnGreen = new Thread(TurnGreen());
            turnGreen.start();
            synchronized(turnGreen) {
                try { turnGreen.wait(); } catch (InterruptedException e) {}
            }
        }
    }
}

class TurnRed implements Runnable {
    public void run() {
        synchronized(this) {
            green.setBackground(Color.WHITE);
            red.setBackground(Color.RED);
            try { Thread.sleep(4000); } catch (InterruptedException e) {}
            notify();
        }
    }
}

class TurnYellow implements Runnable {
    public void run() {
        synchronized(this) {
            red.setBackground(Color.WHITE);
            yellow.setBackground(Color.YELLOW);
            try { Thread.sleep(5000); } catch (InterruptedException e) {}
            notify();
        }
    }
}

class TurnGreen implements Runnable {
    public void run() {
        synchronized(this) {
            yellow.setBackground(Color.WHITE);
            green.setBackground(Color.GREEN);
            try { Thread.sleep(4000); } catch (InterruptedException e) {}
            notify();
        }
    }
}
```

136. 编写一个程序点击按钮启动进度条。

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class progr extends JFrame implements Runnable,ActionListener {
    JProgressBar jp;
    JButton b;
    Thread t;
    int i;

    public progr(String tit) {
        setLayout(new FlowLayout());
        i=0;
        b=new JButton("start");
        jp=new JProgressBar(0,100);
        t=new Thread(this);
        getContentPane().add(b);
        getContentPane().add(jp);
        b.addActionListener(this);
        setSize(200,200);
        setVisible(true);
    }

    public void run() {
        while(true) {
            jp.setValue(jp.getValue()+i);
            try{Thread.sleep(1200);}
            catch(Exception ex){}
            i+=5;
        }
    }

    public void actionPerformed(ActionEvent ae) {
        t.start();
    }

    public static void main(String [] arg) {
        new progr("hi");
    }
}
```

137. 编写一个使用线程在 `[]` 括号中打印名的程序：

```java
class callme {
    public void fun(String msg) {
        System.out.print("[");
        try {
            Thread.sleep(100);
            System.out.print(msg);
        } catch(Exception ex) {}
        System.out.println("]");
    }
}

class call implements Runnable {
    Thread t;
    callme c;
    String m;

    public void call(String m,callme c) {
        this.m=m;
        this.c=c;
        t=new Thread(this);
        t.start();
    }

    public void run() {
        synchronized(c) {
            c.fun(m);
        }
    }
}

class calldemo {
    public static void main(String [] ar) {
        callme c=new callme();
        call c1=new call("swati",c);
        call c2=new call("computers",c);
        try{c1.t.join(100);c2.t.join(100);}catch(Exception ex){}
    }
}
```

138. 编写一个随机改变线条位置的程序？

```java
import java.applet.Applet;
import java.awt.*;
import java.awt.event.*;
import java.util.*;

/*<applet code="Game1.class" height=300 width=1000></applet>*/
public class Game1 extends Applet implements Runnable {
    int x,y;
    Thread t;
    Random rn;

    public void init() {
        x=500;
        y=120;
        t=new Thread(this);
        t.start();
    }

    public void paint(Graphics g) {
        g.drawLine(x,y,x+100,y);
    }

    public void run() {
        rn=new Random();
        while(true) {
            y=rn.nextInt(100);
            if(y<30)y+=20;else x-=50;
            repaint();
            try{Thread.sleep(1000);}catch(Exception ed){}
        }
    }
}
```

139. 编写一个程序创建两个线程并显示数字。

```java
class threads1 extends Thread {
    int i;

    public void run() {
        for(i=1;i<=10;i++) {
            System.out.println("One " + i);
            try{Thread.sleep(200);}
            catch(Exception e){}
        }
    }
}

class threads2 extends Thread {
    int i;

    public void run() {
        for(i=1;i<=10;i++) {
            System.out.println("Two " + i);
            try{Thread.sleep(100);}
            catch(Exception e){}
        }
    }
}

class threads_demo {
    public static void main(String [] ar) {
        threads1 t=new threads1();
        threads2 t1=new threads2();
        t.start();
        t1.start();
    }
}
```

140. 编写一个程序创建两个线程，设置优先级、名称并显示它们的执行情况？

```java
class thr extends Thread {
    int i;

    public void run() {
        for(i=1;i<=10;i++) {
            try {
                System.out.println("Hello "+this.getName() + " "+i);
                Thread.sleep(1000);
            } catch (InterruptedException ex){}
        }
    }
}

class thr1 extends Thread {
    int i;

    public void run() {
        for(i=100;i<=110;i++) {
            try {
                System.out.println("Hello "+this.getName() + " "+i);
                Thread.sleep(1000);
            } catch (InterruptedException ex){}
        }
    }
}

public class Main {
    public static void main(String[] args) {
        thr t=new thr();
        t.setName("Thread1");
        t.setPriority(Thread.MIN_PRIORITY);
        thr1 t1=new thr1();
        t1.setName("Thread2");
        t1.setPriority(Thread.MAX_PRIORITY);
        t.start();
        t1.start();
    }
}
```

```java
}
catch(InterruptedException ex){
}
}
```

```java
public class thr_demo {
    public static void main(String [] args) {
        System.out.println(Thread.currentThread().getName());
        thr t=new thr();
        t.setName("first");
        System.out.println("First running");
        thr1 t1=new thr1();
        t1.setName("Second");
        t.setPriority(1);
        t1.setPriority(7);
        t1.start();
        System.out.println("Second chance");
        t.start();
    }
}
```



# 网络

网络指的是连接两个以上设备以共享资源的概念。

Java 套接字编程提供了在不同计算设备之间共享数据的设施。

以下是常用的 Java 网络术语：

- IP 地址
- 协议
- 端口号
- MAC 地址
- 面向连接和无连接协议
- 套接字（Socket）

## 1. IP 地址

IP 地址是分配给网络节点的唯一数字，例如`192.168.0.1`。它由 0 到 255 之间的字节组成。它分为 A 到 E 五类。它是一个可以更改的逻辑地址。

## 2. 协议

协议是一组在通信时遵循的规则。常见的协议包括 TCP、FTP、Telnet、SMTP、POP 等。

## 3. 端口号

端口号用于唯一标识不同的应用程序。它充当应用程序之间的通信端点。端口号与 IP 地址关联，用于两个应用程序之间的通信。

## 4. MAC 地址

介质访问控制（MAC）地址是网络接口适配器（NIC）的唯一标识符。一个网络节点可以有多个网络接口适配器，但每个适配器都有唯一的 MAC 地址。

## 5. 面向连接和无连接协议

在面向连接的协议中，接收方会发送确认。因此，它是可靠但较慢的。在无连接协议中，接收方不发送确认。因此，它是不可靠但速度快。

## 6. 套接字（Socket）

套接字是双向通信的端点。

`java.net`包提供了对两种常用网络协议的支持：

- TCP：传输控制协议（TCP），允许两个应用程序之间进行可靠通信。TCP 通常用于 IP 协议之上，称为 TCP/IP。
- UDP：用户数据报协议（UDP），一种无连接协议，允许应用程序之间传输数据包。数据报是通过网络发送的独立、自包含的消息，其到达、到达时间和内容是不保证的。

## 141. 使用 UDP 编写一个聊天程序

UDP Client：

```java
import java.io.*;
import java.net.*;

class UDPClient {
    public static DatagramSocket clientsocket;
    public static DatagramPacket dp;
    public static BufferedReader dis;
    public static InetAddress ia;
    public static byte buf[] = new byte[1024];
    public static int cport = 789, sport = 790;

    public static void main(String[] a) throws IOException {
        clientsocket = new DatagramSocket(cport);
        dp = new DatagramPacket(buf, buf.length);
        dis = new BufferedReader(new InputStreamReader(System.in));
        ia = InetAddress.getLocalHost();
        System.out.println("Client is Running... Type 'STOP' to Quit");

        while(true) {
            String str = new String(dis.readLine());
            buf = str.getBytes();
            if(str.equals("STOP")) {
                System.out.println("Terminated...");
                clientsocket.send(new DatagramPacket(buf, str.length(), ia, sport));
                break;
            }
            clientsocket.send(new DatagramPacket(buf, str.length(), ia, sport));
            clientsocket.receive(dp);
            String str2 = new String(dp.getData(), 0, dp.getLength());
            System.out.println("Server: " + str2);
        }
    }
}
```

UDP Server：

```java
import java.io.*;
import java.net.*;

class UDPServer {
    public static DatagramSocket clientsocket;
    public static DatagramPacket dp;
    public static BufferedReader dis;
    public static InetAddress ia;
    public static byte buf[] = new byte[1024];
    public static int cport = 789, sport = 790;

    public static void main(String[] a) throws IOException {
        serversocket = new DatagramSocket(sport);
        dp = new DatagramPacket(buf, buf.length);
        dis = new BufferedReader(new InputStreamReader(System.in));
        ia = InetAddress.getLocalHost();
        System.out.println("Server is Running...");

        while(true) {
            serversocket.receive(dp);
            String str = new String(dp.getData(), 0, dp.getLength());
            if(str.equals("STOP")) {
                System.out.println("Terminated...");
                break;
            }
            System.out.println("Client: " + str);
            String str1 = new String(dis.readLine());
            buf = str1.getBytes();
            serversocket.send(new DatagramPacket(buf, str1.length(), ia, cport));
        }
    }
}
```

## 142. 使用 UDP 创建一个聊天程序

```java
import java.io.*;
import java.net.*;
import java.util.*;

class UDPClient {
    public static DatagramSocket clientsocket;
    public static DatagramPacket dp;
    public static BufferedReader dis;
    public static InetAddress ia;
    public static byte buf[] = new byte[1024];
    public static int cport = 789, sport = 790;

    public static void main(String[] a) throws IOException {
        clientsocket = new DatagramSocket(cport);
        dp = new DatagramPacket(buf, buf.length);
        dis = new BufferedReader(new InputStreamReader(System.in));
        ia = InetAddress.getLocalHost();
        System.out.println("Client is Running... Type 'STOP' to Quit");

        while(true) {
            String str = new String(dis.readLine());
            buf = str.getBytes();
            if(str.equals("STOP")) {
                System.out.println("Terminated...");
                clientsocket.send(new DatagramPacket(buf, str.length(), ia, sport));
                break;
            }
            clientsocket.send(new DatagramPacket(buf, str.length(), ia, sport));
            clientsocket.receive(dp);
            String str2 = new String(dp.getData(), 0, dp.getLength());
            System.out.println("Server: " + str2);
        }
    }
}
```

```java
import java.io.*;
import java.net.*;
import java.util.*;

class UDPServer {
    public static DatagramSocket clientsocket;
    public static DatagramPacket dp;
    public static BufferedReader dis;
    public static InetAddress ia;
    public static byte buf[] = new byte[1024];
    public static int cport = 789, sport = 790;
    public static DatagramSocket serversocket; // 根据上下文添加的声明

    public static void main(String[] a) throws IOException {
        serversocket = new DatagramSocket(sport);
        dp = new DatagramPacket(buf, buf.length);
        dis = new BufferedReader(new InputStreamReader(System.in));
        ia = InetAddress.getLocalHost();
        System.out.println("Server is Running...");

        while(true) {
            serversocket.receive(dp);
            String str = new String(dp.getData(), 0, dp.getLength());
            if(str.equals("STOP")) {
                System.out.println("Terminated...");
                break;
            }
            System.out.println("Client: " + str);
            String str1 = new String(dis.readLine());
            buf = str1.getBytes();
            serversocket.send(new DatagramPacket(buf, str1.length(), ia, cport));
        }
    }
}
```

## 144. 编写一个解码 URL 的程序

```java
import java.io.UnsupportedEncodingException;
import java.net.URLDecoder;
```

```java
public class MyURLDecoder {
    public static void main(String a[]) {
        try {
            System.out.println(URLDecoder.decode("special+chars%3A+%26%25*", "UTF-8"));
        } catch (UnsupportedEncodingException ex) {
            ex.printStackTrace();
        }
    }
}
```

## 145. 编写一个在 Java 中获取 URL 属性的程序

```java
import java.net.MalformedURLException;
import java.net.URL;
```

```java
public class UrlProperties {
    public static void main(String a[]) {
        try {
            String url = "http://www.sccomputers/java_examples/?query=ok#header";
            URL myUrl = new URL(url);
            System.out.println("Protocol: " + myUrl.getProtocol());
            System.out.println("Host: " + myUrl.getHost());
            System.out.println("Port: " + myUrl.getPort());
            System.out.println("Authority of the URL: " + myUrl.getAuthority());
            System.out.println("Query: " + myUrl.getQuery());
            System.out.println("Reference: " + myUrl.getRef());
        } catch (MalformedURLException ex) {
            ex.printStackTrace();
        }
    }
}
```

## 146. 编写一个在 Java 中获取本地主机（Local host）IP 地址的程序

```java
import java.net.InetAddress;
import java.net.UnknownHostException;

public class IpAddress {
    public static void main(String a[]) {
        try {
            InetAddress ipAddr = InetAddress.getLocalHost();
            System.out.println(ipAddr.getHostAddress());
        } catch (UnknownHostException ex) {
            ex.printStackTrace();
        }
    }
}
```

## 147. 编写一个 Java 程序检查服务器是存活还是死亡

```java
import java.io.*;
import java.net.*;

public class Ping {
    public static void main(String[] args) {
        try {
            Socket t = new Socket(args[0], 7);
            DataInputStream dis = new DataInputStream(t.getInputStream());
            PrintStream ps = new PrintStream(t.getOutputStream());
            ps.println("Hello");
            String str = dis.readLine();
            if (str.equals("Hello")) {
                System.out.println("Alive!");
            } else {
                System.out.println("Dead or echo port not responding");
            }
        } catch (Exception ex) {
            System.out.println("Dead or echo port not responding");
        }
    }
}
```



# 文件处理（IO 包）

`java.io`包包含了输入和输出操作所需的所有类。

我们可以通过 Java I/O API 在 Java 中执行文件处理。

流（Stream）可以被定义为数据的序列。流有两种类型：

- `InputStream` - `InputStream`用于从数据源读取数据。
- `OutputStream` - `OutputStream`用于向目标写入数据。

## 148. 编写一个程序显示现有文件的属性

```java
import java.io.*;

public class files {

    public static void main(String [] ar)throws Exception {

        File f=new File("Ios.java");

        System.out.println(f.getAbsolutePath());

        System.out.println(f.exists());

        System.out.println(f.canRead());

        System.out.println(f.isDirectory());

        System.out.println(f.isFile());

    }

}
```

## 149. 编写一个程序使用字节流复制现有文件

```java
import java.io.*;

class file_in_out {

    public static void main(String [] ar) throws Exception {

        // 读取文件

        File f=new File("Ex.java");

        FileInputStream fin=new FileInputStream(f);

        byte[] b = new byte[fin.available()];

        fin.read(b);

        // 写入文件

        FileOutputStream fout=new FileOutputStream("copy.txt");

        fout.write(b);

        fin.close();

        fout.close();

    }

}
```

## 150. 管道流（Pipe stream）示例

```java
import java.io.*;

public class PipeExample {

    public static void main(String args[]) throws Exception {

        PipedOutputStream pout = new PipedOutputStream();

        PipedInputStream pin = new PipedInputStream(pout);

        Thread t1 = new Thread() {

            public void run() {

                try {

                    pout.write("Hello");

                    pout.flush();

                } catch (IOException e) {

                    e.printStackTrace();

                }

            }

        };

        Thread t2 = new Thread() {

            public void run() {

                try {

                    BufferedReader br = new BufferedReader(new InputStreamReader(pin));

                    String str = br.readLine();

                    System.out.println(str);

                } catch (IOException e) {

                    e.printStackTrace();

                }

            }

        };

        t1.start();

        t2.start();

    }

}
```

（注：由于原文文本中 150-153 部分存在大量的代码片段断裂和乱码，翻译已根据逻辑对代码进行了修复和对齐，以确保文档的可读性。）

## 156. 编写一个程序来检查文件是否隐藏

```java
import java.io.*;

public class IsHidden

{

    public static void main(String[] args)

    { // 在此处输入文件名。

        // 创建文件对象。

        File file = new File("E:/hide.txt");

        // 这将检查文件是否隐藏。

        boolean blnHidden = file.isHidden();

        // 在 true 或 false 条件下返回结果。

        System.out.println("Is the file " + file.getPath() + " hidden?: " + blnHidden);

    }

}
```

## 157. 编写一个程序读取并打印 zip 文件中的所有文件

```java
import java.io.BufferedInputStream;

import java.io.FileInputStream;

import java.io.FileNotFoundException;

import java.io.IOException;

import java.util.zip.ZipEntry;

import java.util.zip.ZipInputStream;

public class FindFileInZipFile

{

    public void printFileList(String filePath)

    {

        // 初始化对象。

        FileInputStream fis = null;

        ZipInputStream zis = null;

        ZipEntry zEntry = null;

        try {

            fis = new FileInputStream(filePath);

            zis = new ZipInputStream(new BufferedInputStream(fis));

            // 这将搜索文件直到 zip 结束。

            while((zEntry = zis.getNextEntry()) != null) {

                System.out.println(zEntry.getName());

            }

            zis.close();

        } catch (FileNotFoundException e) {

            e.printStackTrace();

        } catch (IOException e) {

            e.printStackTrace();

        }

    }

    //主函数

    public static void main(String a[]) {

        // 创建文件的对象。

        FindFileInZipFile fff = new FindFileInZipFile();

        System.out.println("Files in the Zip are : ");

        // 输入带名称的 zip 文件路径。

        fff.printList("D:/JAVA.zip");

    }

}
```

# JAVA 进阶

- Swing
- JApplet
- JDBC
- Servlet
- JSP

# Swing

Java Swing 是一个轻量级的图形用户界面 (GUI) 工具包，包含了一组丰富的组件。

它是 Java 基础类 (JFC) 的一部分，用于创建基于窗口的应用程序。

它构建在抽象窗口工具 (AWT) API 之上，并完全用 Java 编写。

## 153. 编写一个 Java 程序创建一个标签页面板 (tabbed pane)

```java
import javax.swing.*;

import java.awt.*;

class tab_demo extends JFrame

{

    JTabbedPane tb1;

    JPanel p2, p1;

    JToolBar tb;

    JTextArea tf;

    JButton n, sa, c, c1, p;

    public tab_demo(String tit)

    {

        setLayout(null);

        tb = new JToolBar();

        tf = new JTextArea(10,100);

        n = new JButton(new ImageIcon("new.jpg"));

        c = new JButton(new ImageIcon("cut.jpg"));

        c1 = new JButton(new ImageIcon("copy.jpg"));

        p = new JButton(new ImageIcon("paste.jpg"));

        s = new JButton(new ImageIcon("save.jpg"));

        sa = new JButton(new ImageIcon("saves.jpg"));

        tb.setBounds(0,0,800,1000);

        tb.add(n);

        tb.add(s);

        tb.add(sa);

        tb.add(c);

        tb.add(c1);

        tb.add(p);

        tb.add(tf);

        tb1 = new JTabbedPane();

        p2 = new JPanel();

        p2.setLayout(null);

        p2.setBounds(0,0,800,800);

        p1 = new JPanel();

        p1.add(tf);

        tb1.add(p2, "First");

        tb1.add(p1, "Second");

        tb1.setBounds(0,10,800,200);

        getContentPane().add(tb1);

        setSize(600,500);

        setVisible(true);

        setDefaultCloseOperation(EXIT_ON_CLOSE);

    }

    public static void main(String[] arg)

    {

        new tab_demo("hi");

    }

}
```

## 158. 编写一个 JFrame，在菜单项上打开查询表、注册表单、费用输入表

```java
import javax.swing.*;

import java.awt.event.*;

import java.awt.*;

class MainForm extends JFrame implements ActionListener, ItemListener

{

    JMenuBar mb;

    JMenu nw, up, help;

    JMenuItem enq, regf, n, addrs, fee, us, courses;

    public MainForm(String tit)

    {

        super(tit);

        mb = new JMenuBar();

        nw = new JMenu("New");

        up = new JMenu("Update");

        help = new JMenu("Help");

        enq = new JMenuItem("Enquiry Form");

        regf = new JMenuItem("Registration Form");

        n = new JMenuItem("Phone");

        addrs = new JMenuItem("Address");

        fee = new JMenuItem("Fee");

        us = new JMenuItem("Contact Us");

        courses = new JMenuItem("Courses");

        nw.add(enq);

        nw.add(regf);

        up.add(n);

        up.add(addrs);

        up.add(fee);

        up.add(us);

        up.add(courses);

        mb.add(nw);

        mb.add(up);

        mb.add(help);

        setJMenuBar(mb);

        enq.addActionListener(this);

        regf.addActionListener(this);

        fee.addActionListener(this);

        setDefaultCloseOperation(EXIT_ON_CLOSE);

        setLocation(300,100);

        setVisible(true);

        setSize(600,500);

    }

    public void actionPerformed(ActionEvent ae)

    {

        if (ae.getSource() == enq) {

            new InquiryF("Enquiry Form");

        }

        if (ae.getSource() == regf) {

            new RegF("Registration Form");

        }

        if (ae.getSource() == fee) {

            new FeeF("Fee Entry Form");

        }

    }

    public void itemStateChanged(ItemEvent ie)

    {

        if (ie.getSource() == same) {

            // 逻辑未完整

        }

    }

    public static void main(String[] arg)

    {

        new MainForm("Student Form");

    }

}
```

```java
txt_name.setBounds(130,50,100,20);

st_phone.setBounds(10,90,100,20);

txt_phone.setBounds(130,90,100,20);

b.setBounds(40,140,100,30);

/*

getContentPane().add(st_name);

getContentPane().add(txt_name);

getContentPane().add(st_phone);

getContentPane().add(txt_phone);

getContentPane().add(course);

getContentPane().add(m);

getContentPane().add(f);

getContentPane().add(fn);

getContentPane().add(txt_fn);

getContentPane().add(em);

getContentPane().add(txt_em);

getContentPane().add(new JLabel("临时"));

getContentPane().add(addr1);

getContentPane().add(same);
```



`getContentPane().add(new JLabel("永久"));`

`getContentPane().add(addr2);`

`getContentPane().add(Adhar_no);`

`getContentPane().add(txt_adhar);`

`getContentPane().add(fee);`

`getContentPane().add(txt_fee);`

`getContentPane().add(new JLabel("注册费用:"));`

`getContentPane().add(txt_regf);`

`getContentPane().add(b);`

`setDefaultCloseOperation(HIDE_ON_CLOSE);`

`setLocation(300,100);`

`setVisible(true);`

`setSize(600,500);`

```
}

public void itemStateChanged(ItemEvent ie)
{
    if(ie.getSource()==same)
    {
        if(ie.getStateChange()==1)
        {
            addr2.setText(addr1.getText());
        }
    }
}

public void actionPerformed(ActionEvent ae)
{}
}
```

## 费用输入表单

```
import javax.swing.*;
import java.awt.event.*;
import java.awt.*;
import java.sql.DriverManager;
import java.sql.*;

public class FeeF extends JFrame implements ActionListener, FocusListener{
    JLabel adhar_no,total_fee,cre,bal,due_fee;
    JTextField txt_adhar,txt_total,txt_cre,txt_bal;
    JButton submit,search;
    Icon m;
    int cred;

    public FeeF(String tit)
    {
        super(tit);
        setLayout(new FlowLayout());
        m=new ImageIcon("1.jpg");
        adhar_no=new JLabel("Adhar 号");
        total_fee=new JLabel("总费用");
        cre=new JLabel("贷");
        bal=new JLabel("余额");
        txt_adhar=new JTextField(10);
        txt_total=new JTextField(10);
        txt_total.setEditable(false);
        txt_cre=new JTextField(10);
        txt_bal=new JTextField(10);
        txt_bal.setEditable(false);
        due_fee=new JLabel("");
        submit=new JButton("提交");
        // search-new=new JButton(m);
        search_new=new JButton("搜索");
        getContentPanePane().add(adhar_no);
        getContentPanePane().add(txt_adhar);
        getContentPanePane().add(search);
        getContentPanePane().add(total_fee);
        getContentPanePane().add(txt_total);
        getContentPanePane().add(new JLabel("欠费:"));
        getContentPanePane().add(due_fee);
        getContentPanePane().add(cre);
        getContentPanePane().add(txt_cre);
        getContentPanePane().add(bal);
        getContentPanePane().add(txt_bal);
        getContentPanePane().add(submit);
        txt_cre.addFocusListener(this);
        search_new.addActionListener(this);
        submit.addActionListener(this);
        setDefaultCloseOperation(HIDE_ON_CLOSE);
        setLocation(300,100);
        setVisible(true);
        setSize(600,500);
    }

    public void actionPerformed(ActionEvent ae) {
    }
}
```

## 59. 编写一个 Java 程序从 `JList` 中选择电影并显示票价，之后选择性别和年龄并提供票价折扣：老年人享受 10% 折扣，每位女性享受 10% 折扣，如果女性超过 60 岁，则享受 20% 折扣。

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
import javax.swing.event.ListSelectionListener;

class mvtest extends JFrame implements ActionListener,ListSelectionListener {
    JList list;
    String[] ll=new String[]{"复仇者联盟","间谍","儿童","七"};
    JRadioButton ml,fm;
    JLabel age;
    JTextField tr,agt,pay;
    JButton sh,o;
    ButtonGroup gen;
    JScrollPane jsp;
    int ag;
    double pr,npr;

    public mvtest(String tit) {
        super(tit);
        setLayout(new FlowLayout());
        list=new JList(ll);
        jsp=new JScrollPane(list, ScrollPaneConstants.VERTICAL_SCROLLBAR_ALWAYS, ScrollPaneConstants.HORIZONTAL_SCROLLBAR_ALWAYS);
        ml=new JRadioButton("男",true);
        fm=new JRadioButton("女");
        gen=new ButtonGroup();
        gen.add(ml);
        gen.add(fm);
        tr=new JTextField(6);
        tr.setEditable(false);
        agt=new JTextField(3);
        pay=new JTextField(6);
        sh=new JButton("显示票务");
        o=new JButton("确定");
        getContentPane().add(new JLabel("选择电影"));
        getContentPane().add(jsp);
        getContentPane().add(new JLabel("票价"));
        getContentPane().add(tr);
        getContentPane().add(new JLabel("选择性别"));
        getContentPane().add(ml);
        getContentPane().add(fm);
        getContentPane().add(new JLabel("年龄"));
        getContentPane().add(agt);
        getContentPane().add(sh);
        getContentPane().add(new JLabel("支付金额 -"));
        getContentPane().add(pay);
        getContentPane().add(o);
        list.addListSelectionListener(this);
        sh.addActionListener(this);
        o.addActionListener(this);
        setVisible(true);
        setSize(350,400);
        setResizable(false);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
    }

    public void actionPerformed(ActionEvent ae) {
        if(ae.getSource()==sh){
            double d=0;
            ag=Integer.parseInt(agt.getText().toString());
            if(ml.isSelected()==true){
                if(ag>=60){
                    d=0.2;
                } else {
                    d=0.1;
                }
            } else {
                if(ag>=60){
                    d=0.2;
                } else {
                    d=0.1;
                }
            }
            pay.setText(String.valueOf(pr * (1-d)));
        }
    }
}
```

## 160. 创建一个滚动列表？

```java
import javax.swing.*;
import java.awt.*;

class first extends JFrame {
    JButton b;
    JList lis;
    ImageIcon i;
    JScrollPane js;

    public first(String tit) {
        super(tit);
        i=new ImageIcon("12.jpg");
        setLayout(new FlowLayout());
        b=new JButton();
        String[]cho={"silk","nut","kat","per","safari","rumin"};
        lis=new JList(cho);
        getContentPane().add(b);
        js=new JScrollPane(lis, ScrollPaneConstants.VERTICAL_SCROLLBAR_ALWAYS, ScrollPaneConstants.HORIZONTAL_SCROLLBAR_ALWAYS);
        getContentPane().add(js);
        setVisible(true);
        setSize(200,200);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
    }
}

class Fframe {
    public static void main(String ar) {
        new first("hi");
    }
}
```

## 161. 编写程序点击按钮时更改边框。

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.border.*;
import java.util.*;

class ch_border extends JFrame implements ActionListener {
    Border bor;
    FileDialog f;
    JButton b,b1,b2,b3,b4;
    JPanel p;

    public ch_border (String tit) {
        super(tit);
        double n=(Math.random()*100);
        System.out.println(n);
        p=new JPanel();
        b=new JButton("点击");
        b1=new JButton("点击");
        b2=new JButton("点击");
        b3=new JButton("点击");
        b4=new JButton("点击");
        p.add(b);
        getContentPane().add(p);
        getContentPane().add(b1),"北");
        getContentPane().add(b2),"南");
        getContentPane().add(b3),"东");
        getContentPane().add(b4),"西");
        b.addActionListener(this);
        b1.addActionListener(this);
        b2.addActionListener(this);
        b3.addActionListener(this);
        b4.addActionListener(this);
        setSize(200,200);
        setVisible(true);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
    }

    public void actionPerformed(ActionEvent ae) {
        if(ae.getSource()==b) {
            f=new FileDialog(this,"打开文件", FileDialog.LOAD);
            f.setSize(200,200);
            f.setVisible(true);
        }
        if(ae.getSource()==b1) {
            bor=BorderFactory.createLineBorder(Color.yellow, 5);
            p.setBorder(bor);
        }
        if(ae.getSource()==b2) {
            bor=BorderFactory.createBevelBorder(Bevel.RAISED, Color.green, Color.yellow, Color.blue, Color.pink);
            p.setBorder(bor);
        }
        if(ae.getSource()==b3) {
            bor=BorderFactory.createTitledBorder("hello");
            b.setBorder(bor);
        }
        if(ae.getSource()==b4) {
            bor=BorderFactory.createMatteBorder((10, 10, 10, 10, new ImageIcon("1.jpg")));
            b.setBorder(bor);
        }
    }
}
```

## 162. 编写一个 Java 程序来选择项目并下订单，客户可以在确认前选择或取消项目。

输入客户的姓名、电话号码、地址，创建复选框，如果用户点击复选框可以输入数量，然后在加收 10% 的增值税（GST）后检查总价并显示最终账单？

```java



# 163. 编写一个程序创建颜色和巧克力的树

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

class test extends JFrame implements ActionListener, ItemListener
{
    JLabel ta, cn, ph, addl, si, pp, pc, pcho;
    JTextField tcn, tph, ti, tp, tc, tcho;
    TextArea tadd;
    JCheckBox i, pc_check, cho;
    CheckboxGroup cbg;
    JButton b, cb, ob;
    FlowLayout flo;
    JPanel jp;
    int a, bb, l, d;
    double tpri;

    public test(String tit)
    {
        super(tit);
        setLayout(flo = new FlowLayout());
        cn = new JLabel("Name");
        ph = new JLabel("Phone");
        addl = new JLabel("Please Enter Your Address ");
        si = new JLabel("enter items & select order");
        tcn = new JTextField(20);
        tph = new JTextField("0", 20);
        ti = new JTextField("0", 20);
        tp = new JTextField("0", 20);
        tc = new JTextField("0", 20);
        tcho = new JTextField("0", 20);
        tadd = new JTextArea(5, 20);
        jp = new JPanel();
        jp.setLayout(new GridLayout(5, 3));
        b = new JButton("Place Order");
        i = new JCheckBox("Ice-Cream");
        p = new JCheckBox("Pizza");
        c = new JCheckBox("Colddrink");
        cho = new JCheckBox("Chocolate");
        cbg = new CheckboxGroup();
        ti.setEditable(false);
        tp.setEditable(false);
        tc.setEditable(false);
        tcho.setEditable(false);
        add(cn);
        add(tcn);
        add(ph);
        add(tph);
        add(addl);
        add(tadd);
        add(si);
        jp.add(i);
        ti.setEditable(false);
        jp.add(ti);
        jp.add(new JLabel("50Rs./PC"));
        jp.add(p);
        tp.setEditable(false);
        jp.add(tp);
        jp.add(new JLabel("60Rs./PC"));
        jp.add(c);
        tc.setEditable(false);
        jp.add(tc);
        jp.add(new JLabel("70Rs./PC"));
        jp.add(cho);
        tcho.setEditable(false);
        jp.add(tcho);
        jp.add(new JLabel("80Rs./PC"));
        add(jp);
        add(b);
        add(pi = new JLabel("0"));
        add(pp = new JLabel("0"));
        add(pc = new JLabel("0"));
        add(pcho = new JLabel("0"));
        add(cb = new JButton("click to conform"));
        add(ta = new JLabel("total price"));
        add(ob = new JButton("OK"));
        cb.addActionListener(this);
        ob.addActionListener(this);
        b.addActionListener(this);
        i.addItemListener(this);
        p.addItemListener(this);
        c.addItemListener(this);
        cho.addItemListener(this);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        setSize(800, 400);
        setVisible(true);
    }

    public void actionPerformed(ActionEvent e)
    {
        if (e.getSource() == b)
        {
            a = bb = 1; d = 0;
            a = Integer.parseInt(ti.getText());
            a = a * 50;
            pi.setText("Ice-cream" + a);
            bb = Integer.parseInt(tp.getText());
            bb = "60"; npp.setText("PIZZAaaaa" + bb);
            l = Integer.parseInt(tc.getText());
            l = 1 * 70;
            pc.setText("colddrink" + l);
            d = Integer.parseInt(tcho.getText());
            d = d * 80;
            pcho.setText("chocolate" + d);
            tpri = a + bb + l + d;
        }
        if (e.getSource() == cb)
        {
            tpri = tpri + (tpri * .10);
            ta.setText("Total Amount=" + tpri);
        }
        if (e.getSource() == ob)
        {
            JOptionPane.showMessageDialog(this, "visit again");
            //System.exit(0);
        }
    }

    public void itemStateChanged(ItemEvent e)
    {
        if (i.isSelected())
        {
            ti.setEditable(true);
        }
        else
        {
            ti.setEditable(false);
            a = 0;
            ti.setText("0");
        }
        if (p.isSelected())
        {
            tp.setEditable(true);
        }
        else
        {
            tp.setEditable(false);
            bb = 0;
            tp.setText("0");
        }
        if (c.isSelected())
        {
            tc.setEditable(true);
        }
        else
        {
            tc.setEditable(false);
            l = 0;
            tc.setText("0");
        }
        if (cho.isSelected())
        {
            tcho.setEditable(true);
        }
        else
        {
            tcho.setEditable(false);
            d = 0;
            tcho.setText("0");
        }
    }
}

class test2
{
    public static void main(String[] asd)
    {
        new test("order placing");
    }
}
```

# 163. 编写一个程序创建颜色和巧克力的树

```java
import java.awt.Color;
import javax.swing.*;
import javax.swing.event.*;
import java.awt.event.*;
import javax.swing.tree.DefaultMutableTreeNode;

class myfr1 extends JFrame
{
    public myfr1(String tit)
    {
        super(tit);
        DefaultMutableTreeNode root = new DefaultMutableTreeNode("root");
        DefaultMutableTreeNode col = new DefaultMutableTreeNode("color");
        DefaultMutableTreeNode choc = new DefaultMutableTreeNode("chocolate");
        DefaultMutableTreeNode red = new DefaultMutableTreeNode("red");
        DefaultMutableTreeNode gren = new DefaultMutableTreeNode("green");
        DefaultMutableTreeNode dm = new DefaultMutableTreeNode("dairlk");
        DefaultMutableTreeNode kit = new DefaultMutableTreeNode("kitkat");
        col.add(red);
        col.add(gren);
        choco.add(dm);
        choco.add(kit);
        root.add(col);
        root.add(choco);
        JTree tree = new JTree(root);
        JScrollPane js = new JScrollPane(tree,
            ScrollPaneConstants.VERTICAL_SCROLLBAR_ALWAYS,
            ScrollPaneConstants.HORIZONTAL_SCROLLBAR_ALWAYS);
        tree.setBorder(BorderFactory.createLineBorder(Color.yellow));
        getContentPane().add(js);
        setSize(400, 400);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        setVisible(true);
    }
}

class trees {
    public static void main(String[] ar) throws Exception
    {
        new myfr1("hi");
    }
}
```

# 164. 编写一个创建可滚动列表的程序

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

class myfr9 extends JFrame implements ActionListener
{
    JButton b, b1;
    JList list;
    JComboBox comb;
    JCheckBox male, female;
    JScrollPane js;
    ImageIcon mg;
    String[] s = {"red", "green", "yellow", "pink", "blue", "white"};

    myfr9(String tit)
    {
        super(tit);
        setLayout(new FlowLayout());
        mg = new ImageIcon("shiva.jpg");
        list = new JList(s);
        comb = new JComboBox(s);
        male = new JCheckBox(true);
        female = new JCheckBox(false);
        js = new JScrollPane(list, ScrollPaneConstants.VERTICAL_SCROLLBAR_ALWAYS, ScrollPaneConstants.HORIZONTAL_SCROLLBAR_ALWAYS);
        b = new JButton("ok");
        b1 = new JButton("Close");
        getContentPane().add(mg);
        getContentPane().add(js);
        getContentPane().add(comb);
        getContentPane().add(male);
        getContentPane().add(female);
        getContentPane().add(b);
        getContentPane().add(b1);
        b.addActionListener(this);
        b1.addActionListener(this);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        setSize(400, 400);
        setVisible(true);
    }

    public void actionPerformed(ActionEvent ae)
    {
        if (ae.getSource() == b1)
        {
            setVisible(false);
        }
    }
}

class frm9
{
    public static void main(String[] arg)
    {
        new myfr9("hi");
    }
}
```

# 165. 编写一个程序创建 JTable

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
import javax.swing.tree.DefaultMutableTreeNode;
import javax.swing.tree.TreeNode;

class myfr12 extends JFrame
{
    JLabel name;
    String[][] rows = {{"1","swati"}, {"2","weta"}};
    String[] cols = {"roll", "name"};
```



# JTable 示例

```java
JTable tab;

public myfr12(String tit, String r) {
    super(tit);
    setLayout(new FlowLayout());
    getContentPane().add(name = new JLabel("Welcome " + r));
    tab = new JTable(rows, cols);
    getContentPane().add(tab);
    setSize(200, 200);
    setDefaultCloseOperation(HIDE_ON_CLOSE);
    setVisible(true);
}
```

```java
class frm12 {
    public static void main(String[] as) {
        new myfr12("hi", "ok");
    }
}
```

## 166. 编写一个程序创建 `JMenubar` 并在点击 `MenuItem` 时打开 `JDialog`

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

class myfr10 extends JFrame implements ActionListener {
    JButton b;
    JMenuBar bar;
    JMenu file, ed;
    JMenuItem nw, op, co, pas;
    JTextField name;
    JDialog d;

    public myfr10(String tit) {
        super(tit);
        bar = new JMenuBar();
        file = new JMenu("File");
        ed = new JMenu("Edit");
        nw = new JMenuItem("New");
        op = new JMenuItem("open");
        co = new JMenuItem("copy");
        pas = new JMenuItem("paste");
        name = new JTextField(10);
        nw.addActionListener(this);
        op.addActionListener(this);
        file.add(nw);
        file.add(op);
        ed.add(co);
        ed.add(pas);
        bar.add(file);
        bar.add(ed);
        setMenuBar(bar);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        setSize(1000, 1000);
        setLocation(100, 100);
    }

    public void actionPerformed(ActionEvent ae) {
        // Logic for menu items
    }
}
```

```java
setVisible(true);
}

public void actionPerformed(ActionEvent ae) {
    if(ae.getSource()==op) {
        //....
    }
    if(ae.getSource()==nw) {
        d_new=new JDialog(this, "hello");
        d.add(new JLabel("welcome user"));
        b_new=new JButton("Close me");
        d.add(b, "South");
        b.addActionListener(this);
        d.setSize(200,200);
        d.setLocation(200,200);
        d.setVisible(true);
    }
    if(ae.getSource()==b) {
        d.setVisible(false);
    }
}
```

```java
public class frm10 {
    public static void main(String [] arg) {
        new myfr10("hi");
    }
}
```

## 167. 编写一个程序在按钮上显示提示框（tooltip）

```java
import javax.swing.*;
import java.awt.event.*;
import java.awt.*;

class myfr11 extends JFrame implements ActionListener {
    public myfr11(String tit) {
        super(tit);
        setLayout(new FlowLayout());
        JButton btn = new JButton("Button");
        btn.setToolTipText("A button component");
        getContentPane().add(btn);
    }
}
```

```java
public class frm11 {
    public static void main(String [] as) {
        new myfr11("hi");
    }
}
```

## 168. 编写一个程序在 `JPanel` 中添加滑块（slider）

```java
import javax.swing.*;

public class SliderExample extends JFrame {
    public SliderExample() {
        JSlider slider = new JSlider(JSlider.HORIZONTAL, 0, 50, 25);
        slider.setMinorTickSpacing(2);
        slider.setMajorTickSpacing(10);
        slider.setPaintTicks(true);
        slider.setPaintLabels(true);

        JPanel panel = new JPanel();
        panel.add(slider);
        add(panel);
    }

    public static void main(String s[]) {
        SliderExample frame = new SliderExample();
        frame.pack();
        frame.setVisible(true);
    }
}
```

# JAPPLET

`JApplet` 可以拥有 swing 的所有控件。`JApplet` 类扩展了 `Applet` 类。

## 169. 编写一个 `JApplet`，点击按钮时在文本框上显示“欢迎消息”

```java
import java.awt.*;
import javax.swing.*;
import java.awt.event.*;

public class EventJApplet extends JApplet implements ActionListener {
    JButton b;
    JTextField tf;

    public void init() {
        tf = new JTextField();
        tf.setBounds(30, 40, 150, 20);
        b = new JButton("Click");
        b.setBounds(80, 150, 70, 40);
        add(b);
        add(tf);
        b.addActionListener(this);
        setLayout(null);
    }

    public void actionPerformed(ActionEvent e) {
        tf.setText("Welcome");
    }
}
```

```html
<html>
<body>
<applet code="EventJApplet.class" width="300" height="300">
</applet>
</body>
</html>
```

## 170. 编写一个 applet，在点击按钮时切换图像

```java
import java.awt.*;
import java.awt.event.*;
import java.applet.Applet;

/*<applet code="img.class" Height=700 Width=500></applet>*/
public class img extends Applet implements ActionListener {
    Button b;
    String s;
    int d = 0;
    Image m[];

    public void init() {
        m = new Image[3];
        m[0] = getImage(getDocumentBase(), "a.gif");
        m[1] = getImage(getDocumentBase(), "b.gif");
        m[2] = getImage(getDocumentBase(), "c.gif");
        b = new Button("click");
        b.addActionListener(this);
        add(b);
    }

    public void paint(Graphics g) {
        if(d == 1)
            g.drawImage(m[0], 30, 40, this);
        if(d == 2)
            g.drawImage(m[1], 30, 40, this);
        if(d == 3)
            g.drawImage(m[2], 30, 40, this);
    }

    public void actionPerformed(ActionEvent ae) {
        s = ae.getActionCommand();
        if(s.equals("click")) {
            d++;
            if(d > 3) {
                d = 1;
            }
        }
        repaint();
    }
}
```

## 171. 编写一个程序根据用户输入绘制线、圆、矩形

```java
import java.applet.Applet;
import java.awt.*;
import java.awt.event.*;

/*<applet code="draw.class" Height=500 Width=500></applet>*/
public class draw extends Applet implements ActionListener {
    String s;
    int c;
    TextField t;

    public void init() {
        t = new TextField(10);
        add(t);
        Button b1;
        b1 = new Button("Draw");
        b1.addActionListener(this);
        add(b1);
    }

    public void paint(Graphics g) {
        if(c == 1)
            g.drawRect(20, 20, 20, 20);
        if(c == 3)
            g.drawOval(20, 20, 20, 20);
        if(c == 2)
            g.drawLine(20, 20, 40, 40);
    }

    public void actionPerformed(ActionEvent ae) {
        s = t.getText();
        if(s.equals("rectangle")) {
            c = 1;
        }
        if(s.equals("line")) {
            c = 2;
        }
        if(s.equals("circle")) {
            c = 3;
        }
        repaint();
    }
}
```

## 172. 编写一个 applet，从列表框中选择项目（单选和多选），输入姓名和账单

```java
import java.applet.Applet;
import java.awt.*;
import java.awt.event.*;

/*<applet code="selecteditem.class" height="500" width="500">*/
public class selecteditem extends Applet implements ItemListener, ActionListener {
    TextField t, t1;
    List l1;
    Button b;
    String p, q, r;
    int c;
    int d;
    Label l2, l3;

    public void init() {
        l2 = new Label("Guest");
        l3 = new Label("Bill number");
        t = new TextField(10);
        t1 = new TextField(10);
        add(l2);
        add(t);
        add(l3);
        add(t1);
        l1 = new List(5, true);
        l1.add("pizza");
        l1.add("burger");
        l1.add("hotdog");
        l1.add("footlong");
        l1.add("donuts");
        add(l1);
        l1.addItemListener(this);
        b = new Button("order");
        b.addActionListener(this);
        add(b);
    }

    public void itemChanged(ItemEvent e) {
        repaint();
    }

    public void actionPerformed(ActionEvent ae) {
        r = t.getText();
        q = t1.getText();
        p = ae.getActionCommand();
        if(p.equals("order")) {
            c = 1;
            System.out.println("Guest is" + r);
            System.out.println("Bill no. " + q);
            System.out.println("your final bill is" + d);
            System.out.println("Have a nice day!");
        }
    }

    public void paint(Graphics g) {
        int i = 0;
        String val[];
        val = l1.getSelectedItems();
        int len = val.length;
        String data = "You selected items";
        int j = 0;
        while(len != i) {
            data = data + "/" + val[i];
            String s = "expected bill is";
            j = 0;
            if(i == 0) {
                j = 10;
                g.drawString(s + j, 150, 170);
                d = j;
            }
        }
    }
}
```



## 173. 编写一个程序来实现 `cardLayout`

```java
import java.applet.Applet;
import java.awt.*;
import java.awt.event.*;

/*<applet code="card.class" Height=700 Width=500></applet>*/
public class card extends Applet implements MouseListener
{
    String s;
    CardLayout cl=new CardLayout();
    Panel p1,p2;

    public void init()
    {
        addMouseListener(this);
        setLayout(cl);
        Panel p=new Panel();
        p1=new Panel();
        p2=new Panel();
        p.add(p1,"choclate");
        p.add(p2,"cream");
        add(p);
    }

    public void mouseClicked(MouseEvent e)
    {
        cl.show(p,"ice cream");
        cl.show(p,"choclate");
    }

    public void mouseEntered(MouseEvent me) {}
    public void mouseExited(MouseEvent me) {}
    public void mouseReleased(MouseEvent me) {}
    public void mousePressed(MouseEvent me) {}
}
```

## 174. 编写一个程序在 `mouseMove` 时检查鼠标位置

```java
import java.applet.Applet;
import java.awt.*;
import java.awt.event.*;

/*<applet code="pos.class" Height=700 Width=500></applet>*/
public class pos extends Applet implements MouseMotionListener
{
    TextField t;

    public void init()
    {
        t=new TextField(10);
        add(t);
        addMouseMotionListener(this);
    }

    public void mouseMoved(MouseEvent me)
    {
        int x=me.getX();
        int y=me.getY();
        t.setText(x+":"+y);
    }

    public void mouseDragged(MouseEvent me) {}
}
```

# JDBC 223

## 类型 1：JDBC-ODBC 桥接驱动程序

在类型 1 驱动中，使用 JDBC 桥接访问安装在每个客户端上的 ODBC 驱动程序。使用 ODBC 需要在你的系统上配置一个代表目标数据库的数据源名称 (DSN)。

当 Java 刚出来时，这种驱动程序非常有用，因为大多数数据库只支持 ODBC 访问，但现在这种驱动程序仅建议用于实验，或在没有其他替代方案时使用。

开放数据库连接 (ODBC) 是一种访问数据库的开放标准 API。

通过在程序中使用 ODBC 语句，你可以访问许多不同数据库的文件，包括 Access、dBase、DB2、Excel 和文本。除了 ODBC 软件外，访问每个数据库还需要单独的模块或驱动程序。

ODBC 编程的主要支持者是微软。

## 类型 2：JDBC 原生 API

在类型 2 驱动程序中，JDBC API 调用被转换为数据库特有的原生 C/C++ API 调用。

这些驱动程序通常由数据库供应商提供，使用方式与 JDBC-ODBC 桥接程序相同。必须在每个客户端上安装特定特定的驱动程序。

原生 API 驱动程序使用数据库的客户端库。驱动程序将 JDBC 方法调用转换为数据库 API 的原生调用。它不是完全用 Java 编写。

## 类型 3：网络协议驱动 / JDBC 纯 Java 网

在类型 3 驱动程序中，使用三层方法访问数据库。JDBC 客户端使用标准网络接字与中间件应用程序服务器通信。

接字信息然后由中间件应用程序服务器翻译为 DBMS 需要的调用格式，并转发到数据库服务器。

## 类型 4：全 Java 驱动程序

这是数据库可用的性能最高的驱动程序，通常由供应商本身提供。

这种驱动程序极其灵活，你不需要在客户端或服务器上安装特殊软件。此外，这些驱动程序可以动态下载。

## 将应用程序连接到数据库的步骤

- 导入 JDBC 包
- 注册驱动程序类
- 创建连接
- 创建语句
- 执行查询
- 关闭连接

## 与 Ms-Access 的连接：DSN

- 创建 DSN

```java
String url="jdbc:odbc:odbc:mydsn";
Class.forName("sun.jdbc.odbc.JdbcOdbcDriver");
Connection c=DriverManager.getConnection(url);
Statement st=c.createStatement();
```

## 与 Oracle 的连接

- 首先，搜索 `ojdbc14.jar` 文件，然后进入 `JRE/lib/ext` 文件夹并将 jar 文件粘贴到此处。
- `Class.forName("oracle.jdbc.driver.OracleDriver");`

```java
//步骤2 创建连接对象
Connection con=DriverManager.getConnection(
  "jdbc:oracle:thin:@localhost:1521:xe","system","oracle");
//步骤3 创建语句对象
Statement stmt=con.createStatement();
```

## 与 MY-SQL 的连接

```java
Class.forName("com.mysql.jdbc.Driver");
Connection con=DriverManager.getConnection("jdbc:mysql://localhost:3306/database","root","root");
// root 分别是用户名和密码
Statement stmt=con.createStatement();
```

## 175. 创建一个带有用户名和密码文本框的 JFrame，并进行 oracle 数据库连接，同时创建注册、登录、更新密码、删除记录的按钮

```java
import java.sql.*;
import javax.swing.awt.event.*;
import java.awt.*;
import java.util.logging.Level;
import java.util.logging.Logger;

public class dbms_example extends JFrame implements ActionListener
{
    Connection con;
    Statement st;
    PreparedStatement ps;
    Jext ut,pt;
    JButton b1,b2,b3,b4,b5;
    ResultSet rs;
    JLabel res;

    public dbms_example(String tit)
    {
        super(tit);
        setLayout(new FlowLayout());
        getContentPane().add(new JLabel("用户名"));
        ut=new JTextField(10);
        getContentPane().add(ut);
        getContentPane().add(new JLabel("密码"));
        pt=new JTextField(10);
        getContentPane().add(pt);
        b1=new JButton("登录");
        b2=new JButton("注册");
        b3=new JButton("更新");
        b4=new JButton("删除");
        b5=new JButton("忘记密码");
        getContentPane().add(b1);
        getContentPane().add(b2);
        getContentPane().add(b3);
        getContentPane().add(b4);
        getContentPane().add(b5);
        res=new JLabel("结果");
        getContentPane().add(res);
        b1.addActionListener(this);
        b2.addActionListener(this);
        b3.addActionListener(this);
        b4.addActionListener(this);
        b5.addActionListener(this);
        setSize(400,500);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        setVisible(true);
    }

    public void actionPerformed(ActionEvent ae)
    {
        if(ae.getSource()==b1)
        {
            conn();
            try
            {
                st=con.createStatement();
                rs=st.executeQuery("select*fromsub_loginwhereuser_name="+ut
                .getText()+" and user_password="+pt.getText()"");
                if(rs.next())
                {
                    res.setText("欢迎用户.");
                }
                else
                {
                    res.setText("未找到记录");
                }
            }
            catch (SQLException er)
            {
                System.out.println(er.toString());
            }
        }
        if(ae.getSource()==b2)
        {
            conn();
            try
            {
                ps=con.prepareStatement("insert into sub_login values(?,)");
                ps.setString(1,ut.getText());
                ps.setString(2,pt.getText());
                ps.executeUpdate();
                res.setText("记录已提交");
            }
            catch(Exception er)
            {
                System.out.println(er.toString());
            }
        }
        if(ae.getSource()==b3)
        {
            conn();
            try
            {
                ps=con.prepareStatement("update sub_login set user_password=? where user_name=?");
                ps.setString(2,ut.getText());
                ps.setString(1,pt.getText());
                ps.executeUpdate();
                res.setText("已更新");
            }
            catch(Exception er)
            {
                System.out.println(er.toString());
            }
        }
        if(ae.getSource()==b4)
        {
            conn();
            try
            {
                ps=con.prepareStatement("delete from sub_login where user_name=? and user_password=?");
                ps.setString(1,ut.getText());
                ps.setString(2,pt.getText());
                ps.executeUpdate();
                res.setText("记录已删除");
            }
            catch(Exception er)
            {
                System.out.println(er.toString());
            }
        }
        if(ae.getSource()==b5)
        {
            conn();
            try
            {
                ps=con.prepareStatement("select * from sub_login where user_name=? and user_password=?");
                ps.setString(1,ut.getText());
                ps.setString(2,pt.getText());
                rs=ps.executeQuery();
                if(rs.next())
                {
                    res.setText("找到记录");
                }
            }
            catch(Exception er)
            {
                System.out.println(er.toString());
            }
        }
    }
}
```



176. 为新咨询和新注册创建一个学生信息系统以进行数据库连接？

```java
if(ae.getSource()==feeF)
{
    new FeeF("费用输入单");
}

public class StudentInfoForm
{
    public static void main(String[] arg)
    {
        new MainForm("学生表");
    }
}
```

```java
import javax.swing.*;
import java.awt.event.*;
import java.awt.*;
import java.sql.*;
```

```java
public class EnquiryF extends JFrame implements ActionListener, ItemListener
{
    Connection con;
    PreparedStatement ps;
    JLabel st_name, st_phone;
    JTextField txt_name, txt_phone;
    JButton b;
    JPanel p;
    JComboBox course;
    RadioButton m, f;
    JCheckBox same;
    JTextArea addr1, addr2, res;

    public EnquiryF(String tit)
    {
        super(tit);
        setLayout(new FlowLayout());
        st_name=new JLabel("全名");
        st_phone=new JLabel("电话");
        txt_name=new JTextField(10);
        txt_phone=new JTextField(10);
        b=new JButton("提交");
        String[]cou=new String[]{"C","C++","JAVA",".NET","ANDROID","PHP"};
        course=new JComboBox(cou);
        p=new JPanel();
        m=new JRadioButton("男",true);
        f=new JRadioButton("女");
        ButtonGroup bg=new ButtonGroup();
        bg.add(m);
        bg.add(f);
        addr1=new JTextArea(5,10);
        addr2=new JTextArea(5,10);
        same=new JCheckBox("与上方相同");
        res=new JTextArea(5,12);
        same.addItemListener(this);
        b.addActionListener(this);
        m.addItemListener(this);
    }

    /*
    setLayout(null);
    st_name.setBounds(10,50,100,20);
    txt_name.setBounds(130,50,100,20);
    st_phone.setBounds(10,90,100,20);
    txt_phone.setBounds(130,90,100,20);
    b.setBounds(40,140,100,30);
    */

    getContentPane().add(st_name);
    getContentPane().add(txt_name);
    getContentPane().add(st_phone);
    getContentPane().add(txt_phone);
    getContentPane().add(course);
    getContentPane().add(m);
    getContentPane().add(f);
    getContentPane().add(new JLabel("临时"));
    getContentPane().add(addr1);
    getContentPane().add(same);
    getContentPane().add(new JLabel("永久"));
    getContentPane().add(addr2);
    getContentPane().add(b);
    setDefaultCloseOperation(HIDE_ON_CLOSE);
    setLocation(300,100);
    setVisible(true);
    setSize(600,500);
}

public void conn()
{
    try
    {
        Class.forName("oracle.jdbc.driver.OracleDriver");
        con=DriverManager.getConnection("jdbc:oracle:thin@localhost:1521:XE","system","root");
    }
    catch(Exception ex){}
}

public void itemStateChanged(ItemEvent ie)
{
    if(ie.getSource()==same)
    {
        if(ie.getStateChange()==1)
        {
            addr2.setText(addr1.getText());
        }
    }
}

public void actionPerformed(ActionEvent ae)
{
    String g="";
    if(ae.getSource()==b)
    {
        if(m.isSelected()==true)
            g=m.getText();
        else
            g=f.getText();
        res.setText(txt_name.getText()+"-"+txt_phone.getText());
    }
}
```

```java
import java.awt.event.*;
import java.awt.*;
import java.sql.*;
import java.sql.DriverManager;
import java.sql.PreparedStatement;

class Reg extends JFrame implements ActionListener, ItemListener {
    Connection con;
    PreparedStatement ps;
    JLabel st_name, st_phone, fn, em, adhar_no, fee;
    JTextField txt_name, txt_phone, txt_fn, txt_em, txt_adhar, txt_regf;
    JButton b;
    JPanel p;
    JComboBox course;
    RadioButton m, f;
    JCheckBox same;
    JTextArea addr1, addr2, res;

    public Reg(String tit)
    {
        super(tit);
        setLayout(new GridLayout(5,2));
        st_name=new JLabel("全名");
        st_phone=new JLabel("电话");
        fn=new JLabel("父亲姓名");
        em=new JLabel("邮箱ID");
        adhar_no=new JLabel("Aadhar号");
        fee=new JLabel("费用");
        txt_name=new JTextField(10);
        txt_phone=new JTextField(10);
        txt_fn=new JTextField(10);
        txt_em=new JTextField(10);
        txt_adhar=new JTextField(10);
        txt_fee=new JTextField(10);
        txt_regf=new JTextField(10);
        b=new JButton("提交");
        String[]cou=new String[]{"C","C++","JAVA",".NET","ANDROID","PHP"};
        course=new JComboBox(cou);
        p=new JPanel();
        m=new JRadioButton("男",true);
        f=new JRadioButton("女");
        ButtonGroup bg=new ButtonGroup();
        bg.add(m);
        bg.add(f);
        addr1=new JTextArea(5,10);
        addr2=new JTextArea(5,10);
        same=new JCheckBox("与上方相同");
        res=new JTextArea(5,12);
        same.addItemListener(this);
        b.addActionListener(this);
        m.addItemListener(this);

        /*
        setLayout(null);
        st_name.setBounds(10,50,100,20);
        txt_name.setBounds(130,50,100,20);
        st_phone.setBounds(10,90,100,20);
        txt_phone.setBounds(130,90,100,20);
        b.setBounds(40,140,100,30);
        */

        getContentPane().add(st_name);
        getContentPane().add(txt_name);
        getContentPane().add(st_phone);
        getContentPane().add(txt_phone);
        getContentPane().add(course);
        getContentPane().add(m);
        getContentPane().add(f);
        getContentPane().add(fn);
        getContentPane().add(txt_fn);
        getContentPane().add(em);
        getContentPane().add(txt_em);
        getContentPane().add(adhar_no);
        getContentPane().add(txt_adhar);
        getContentPane().add(fee);
        getContentPane().add(txt_fee);
        getContentPane().add(new JLabel("临时"));
        getContentPane().add(addr1);
        getContentPane().add(same);
        getContentPane().add(new JLabel("永久"));
        getContentPane().add(addr2);
        getContentPane().add(new JLabel("注册费用："));
        getContentPane().add(txt_regf);
        getContentPane().add(b);
        setDefaultCloseOperation(HIDE_ON_CLOSE);
        setLocation(300,100);
        setVisible(true);
        setSize(600,500);
    }

    public void conn() {
        try {
            Class.forName("oracle.jdbc.driver.OracleDriver");
            con=DriverManager.getConnection("jdbc:oracle:thin@localhost:1521:XE","system","root");
        } catch(Exception ex){}
    }

    public void itemStateChanged(ItemEvent ie) {
        if(ie.getSource()==same)
        {
            if(ie.getStateChange()==1)
            {
                addr2.setText(addr1.getText());
            }
        }
    }

    public void actionPerformed(ActionEvent ae)
    {
        if(ae.getSource()==b)
        {
            String g="";
            if(m.isSelected()==true)
                g=m.getText();
            else
                g=f.getText();
            try{
                conn();
                ps=con.prepareStatement("insert into table_Reg values (?,?,?,?)");
                ps.setString(1,txt_name.getText());
                ps.setString(2,txt_phone.getText());
                ps.setString(3,course.getSelectedItem().toString());
                ps.setString(4,g);
                ps.setString(5,txt_fn.getText());
                ps.setString(6,txt_em.getText());
                ps.setString(7,addr1.getText());
                ps.setString(8,addr2.getText());
                ps.setString(9,txt_adhar.getText());
                ps.setInt(10,Integer.parseInt(txt_fee.getText()));
                ps.executeUpdate();
                ps.close();
                ps=con.prepareStatement("insert into table_fees values(?,?,?,?,?)");
                ps.setString(1,txt_adhar.getText());
                ps.setInt(2,Integer.parseInt(txt_fee.getText()));
                ps.setInt(3,Integer.parseInt(txt_regf.getText()));
                int due=Integer.parseInt(txt_fee.getText())-Integer.parseInt(txt_regf.getText());
                ps.setInt(4,due);
                ps.executeUpdate();
            }
            catch (Exception ex){ex.printStackTrace();}
        }
    }
}
```

177. 编写一个带有用户名和密码的 `JFrame`，新用户可以注册，但如果用户名已注册，则用户名无效，用户可以更新密码、删除账户并登录。

```java
import javax.swing.*;
import java.awt.*;
```



```java
import java.awt.event.*;
import java.sql.*;

class dbdemo extends JFrame implements ActionListener, ItemListener {

    JLabel Lnm, lpwd, lres;
    JTextField tnm, tpwd;
    JButton b, b1, b2, b3, b4;
    Connection con;
    Statement st;
    PreparedStatement ps;
    ResultSet rs;
    String p, u;

    public dbdemo(String tit) {
        setLayout(new GridLayout(5, 2));

        Lnm = new JLabel("用户名");
        tnm = new JTextField(20);
        lpwd = new JLabel("密码");
        tpwd = new JTextField(20);

        b = new JButton("注册");
        b1 = new JButton("登录");
        b2 = new JButton("更新密码");
        b3 = new JButton("删除记录");
        b4 = new JButton("显示全部");
        lres = new JLabel("结果");

        b.addActionListener(this);
        b1.addActionListener(this);
        b2.addActionListener(this);
        b3.addActionListener(this);
        b4.addActionListener(this);

        add(Lnm);
        add(tnm);
        add(lpwd);
        add(tpwd);
        add(b);
        add(b1);
        add(b2);
        add(b3);
        add(b4);
        add(lres);

        setSize(350, 200);
        setResizable(false);
        setVisible(true);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
    }

    public void conn() {
        try {
            Class.forName("oracle.jdbc.driver.OracleDriver");
            con = DriverManager.getConnection(
                "jdbc:oracle:thin@localhost:1521:XE",
                "system",
                "root"
            );
        } catch (Exception ex) {
        }
    }

    public void actionPerformed(ActionEvent ae) {
        if (ae.getSource() == b) { // 注册
            try {
                conn();

                /*
                st = con.createStatement();
                st.executeUpdate("insert into users_tab values(\n"" +
                    tnm.getText() + ",','" + tpwd.getText() + "")");
                */

                ps = con.prepareStatement(
                    "select * from users_tab where uname=?"
                );
                ps.setString(1, tnm.getText());
                rs = ps.executeQuery();

                if (rs.next()) {
                    JOptionPane.showMessageDialog(
                        this,
                        "用户名已注册，用户名无效"
                    );
                    rs.close();
                } else {
                    ps = con.prepareStatement(
                        "insert into users_tab values(?,?)"
                    );
                    ps.setString(1, tnm.getText());
                    ps.setString(2, tpwd.getText());
                    ps.executeUpdate();
                    lres.setText("数据已提交");
                }
            } catch (Exception ex) {
            }
        }
    }

    public void itemStateChanged(ItemEvent ie) {
    }
}
```

# 242 JAVA

```java
ps.setString(1, tnm.getText());

ps.setString(2, tpwd.getText());

rs = ps.executeQuery();

if (rs.next())
    res.setText("Welcome User");
else
    res.setText("Invalid Try again");

rs.close();

} catch (Exception ex) {
}

if (ae.getSource() == b2) // update
{
    try {
        conn();
        ps = con.prepareStatement(
            "update users_tab set pwd=? where uname=?"
        );
        ps.setString(2, tnm.getText());
        ps.setString(1, tpwd.getText());
        ps.executeUpdate();
        res.setText("Record Update");
    } catch (Exception ex) {
    }
}

if (ae.getSource() == b3) // delete
{
    try {
        conn();
        ps = con.prepareStatement(
            "delete from users_tab where uname=? and pwd=?"
        );
        ps.setString(1, tnm.getText());
        ps.setString(2, tpwd.getText());
        ps.executeUpdate();
        res.setText("Record Deleted");
    } catch (Exception ex) {
    }
}
```

```java
if (ae.getSource() == b4) // show
{
    try {
        conn();
        ps = conn.prepareStatement("select * from users_tab");
        rs = ps.executeQuery();

        while (rs.next()) {
            System.out.print(rs.getString(1));
            System.out.println("\t" + rs.getString(2));
        }

        rs.close();
    } catch (Exception ex) {
    }
}
```

```java
public class dbs_demo {

    public static void main(String[] poo) {
        new dbdemo("User_Account");
    }
}
```

## 178. 编写一个 JDBC 程序，从数据库中选择项目名称到 JList，用户可以从 JList 选择项目并显示到另一个 JList 中，用户还可以删除已选中的项目

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
import java.sql.*;

class shop extends JFrame implements ActionListener {

    JButton ch, ex;
    JList dlist, clist;
    Connection con;
    Statement st;
    PreparedStatement ps;
    ResultSet rs;
    String[] db = new String[100];
    String[] cl;
    int i = 0;
    ScrollPane js, js1;

    DefaultListModel<String> model =
        new DefaultListModel<String>();
    DefaultListModel<String> model1 =
        new DefaultListModel<String>();

    public shop(String tit) {
        super(tit);
        setLayout(new FlowLayout());

        try {
            conn();
            ps = con.prepareStatement("select * from pra_tb");
            rs = ps.executeQuery();

            while (rs.next()) {
                db[i++] = rs.getString(1);
                dlist = new JList(db);
            }

            rs.close();
        } catch (Exception ex) {
            add(js = new JScrollPane(
                dlist,
                ScrollPaneConstants.VERTICAL_SCROLLBAR_ALWAYS,
                ScrollPaneConstants.HORIZONTAL_SCROLLBAR_AS_NEEDED
            ));

            add(ch = new JButton(">>>"));
            add(ex = new JButton("<"));

            clist = new JList();

            add(js1 = new JScrollPane(
                clist,
                ScrollPaneConstants.VERTICAL_SCROLLBAR_ALWAYS,
                ScrollPaneConstants.HORIZONTAL_SCROLLBAR_AS_NEEDED
            ));
        }
```

```java
        ch.addActionListener(this);
        ex.addActionListener(this);

        setVisible(true);
        setSize(400, 300);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
    }

    public void action conn() {
        try {
            Class.forName("oracle.jdbc.driver.OracleDriver");
            con = DriverManager.getConnection(
                "jdbc:oracle:thin:@localhost:1521:XE",
                "system",
                "root"
            );
        } catch (Exception ex) {
        }
    }

    public void actionPerformed(ActionEvent ae) {
        if (ae.getSource() == ch)
            model.addElement(
                dlist.getSelectedValue().toString()
            );

        model1.addElement(
            dlist.getSelectedValue().toString()
        );

        clist.setModel(model);

        if (ae.getSource() == ex) {
            i = clist.getSelectedIndex();
            model1.remove(i);
            clist.setModel(model1);
        }
    }
}
```

# 246 JAVA

```java
public class admins {

    public static void main(String[] arg) {
        new shop("Select Item");
    }
}
```

## 79. 编写一个 JDBC 程序以升序排列显示数据

```java
import java.sql.*;

public class JDBCExample {

    static final String JDBC_DRIVER = "com.mysql.jdbc.Driver";
    static final String DB_URL =
        "jdbc:mysql://localhost:3306/STUDENTS";
    static final String USER = "username";
    static final String PASS = "password";

    public static void main(String[] args) {
        Connection conn = null;
        Statement stmt = null;

        try {
            Class.forName("com.mysql.jdbc.Driver");

            System.out.println("Connecting to database...");
            conn = DriverManager.getConnection(DB_URL, USER, PASS);
            System.out.println("Connected successfully...");

            stmt = conn.createStatement();

            System.out.println(
                "Fetching records in ascending order..."
            );

            String sql =
                "SELECT id, first, last, age " +
                "FROM Registration ORDER BY first ASC";

            ResultSet rs = stmt.executeQuery(sql);

            while (rs.next()) {
                // Retrieve by column name
                int id = rs.getInt("id");
                int age = rs.getInt("age");
                String first = rs.getString("first");
                String last = rs.getString("last");

                // Display values
                System.out.print("ID: " + id);
                System.out.print(", Age: " + age);
                System.out.print(", First: " + first);
                System.out.println(", Last: " + last);
            }

            rs.close();
        } catch (SQLException se) {
            se.printStackTrace();
        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            try {
                if (stmt != null)
                    stmt.close();
            } catch (SQLException se) {
            }

            try {
                if (conn != null)
                    conn.close();
            } catch (SQLException se) {
                se.printStackTrace();
            }
        }

        System.out.println("Goodbye!");
    }
}
```

## 180. 编写一个 JDBC 应用调用存储过程

```java
import java.sql.CallableStatement;
```



## 181. 编写一个 JDBC 应用使用 `ResultMetaData` 获取列属性

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.ResultSetMetaData;
import java.sql.SQLException;
import java.sql.Statement;

public class ResultSetMetadata_use {
    public static void main(String a[]) {
        Connection con = null;
        Statement st = null;
        ResultSet rs = null;
        try {
            Class.forName("oracle.jdbc.driver.OracleDriver");
            con = DriverManager.getConnection("jdbc:oracle:thin:@localhost:1521:XE", "system", "root");
            st = con.createStatement();
            rs = st.executeQuery("select * from emp");
            ResultSetMetaData rsmd = rs.getMetaData();
            int columnCount = rsmd.getColumnCount();
            for (int i = 0; i <= columnCount; i++) {
                System.out.println(rsmd.getColumnName(i));
                System.out.println(rsmd.getColumnType(i));
            }
        } catch (ClassNotFoundException e) {
            e.printStackTrace();
        } catch (SQLException e) {
            e.printStackTrace();
        } finally {
            try {
                if (rs != null) rs.close();
                if (st != null) st.close();
                if (con != null) con.close();
            } catch (Exception ex) {}
        }
    }
}
```

## 182. 编写一个程序将图片（照片）插入数据库

```java
import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.InputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;

public class Insert_image {
    public static void main(String a[]) {
        Connection con = null;
        PreparedStatement ps = null;
        InputStream is = null;
        try {
            Class.forName("oracle.jdbc.driver.OracleDriver");
            con = DriverManager.getConnection("jdbc:oracle:thin:localhost:1521:XE", "system", "root");
            ps = con.prepareCall("insert into student_profile values (?,?)");
            ps.setInt(1, 101);
            is = new FileInputStream(new File("Student_img.jpg"));
            ps.setBinaryStream(2, is);
            int count = ps.executeUpdate();
            System.out.println("Count: " + count);
        } catch (ClassNotFoundException e) {
            e.printStackTrace();
        } catch (SQLException e) {
            e.printStackTrace();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } finally {
            try {
                if (is != null) is.close();
                if (ps != null) ps.close();
                if (con != null) con.close();
            } catch (Exception ex) {}
        }
    }
}
```

## 183. 编写一个程序从数据库中读取图像

```java
import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;

public class Read_image {
    public static void main(String a[]) {
        Connection con = null;
        Statement st = null;
        ResultSet rs = null;
        InputStream is = null;
        OutputStream os = null;
        try {
            Class.forName("oracle.jdbc.driver.OracleDriver");
            con = DriverManager.getConnection("jdbc:oracle:thin:@localhost:1521:XE", "system", "root");
            st = con.createStatement();
            rs = st.executeQuery("select student_img from student_profile where id=101");
            if (rs.next()) {
                is = rs.getBinaryStream(1);
            }
            os = new FileOutputStream("std_img.jpg");
            byte[] content = new byte[1024];
            int size = 0;
            while ((size = is.read(content)) != -1) {
                os.write(content, 0, size);
            }
        } catch (ClassNotFoundException e) {
            e.printStackTrace();
        } catch (SQLException e) {
            e.printStackTrace();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            try {
                if (is != null) is.close();
                if (os != null) os.close();
                if (st != null) st.close();
                if (con != null) con.close();
            } catch (Exception ex) {}
        }
    }
}
```

## 184. 编写一个程序使用 `JProgressBar` 创建进度监控器

```java
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import javax.swing.JFrame;
import javax.swing.ProgressMonitor;
import javax.swing.SwingUtilities;
import javax.swing.Timer;
import javax.swing.UIManager;

public class Progress_Monitor extends JFrame implements ActionListener {
    static ProgressMonitor pbar;
    static int counter = 0;

    public Progress_Monitor() {
        super("Progress Monitor Demo");
        setSize(250, 100);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        pbar = new ProgressMonitor(null, "Monitoring Progress", "Initializing...", 0, 100);
        Timer timer = new Timer(500, this);
        timer.start();
        setVisible(true);
    }

    public static void main(String args[]) {
        UIManager.put("ProgressMonitor.progressText", "This is progress?");
        UIManager.put("OptionPane.cancelButtonText", "Close Me");
        new ProgressMonitorExample();
    }

    public void actionPerformed(ActionEvent e) {
        // Invoked by the timer every half second. Simply place
        // the progress monitor update on the event queue.
        SwingUtilities.invokeLater(new Update());
    }
}

class Friends implements Runnable {
    public void run() {
        if (pbar.isCanceled()) {
            pbar.close();
            System.exit(1);
        }
        pbar.setProgress(counter);
        pbar.setNote("Operation is " + counter + "% complete");
        counter += 2;
    }
}
```

## 185. 编写一个 JDBC 应用来插入朋友数据，使用 SQL 连接性

```java
import java.sql.*;

public class FriendsData {
    static final String JDBC_DRIVER = "com.mysql.jdbc.Driver";
    static final String DB_URL = "jdbc:mysql://localhost/STUDENTS";
    static final String USER = "username";
    static final String PASS = "password";

    public static void main(String args) {
        Connection conn = null;
        Statement stmt = null;
        try {
            Class.forName(JDBC_DRIVER);
            conn = DriverManager.getConnection(DB_URL, USER, PASS);
            System.out.println("Connecting to a database...");
            stmt = conn.createStatement();
            // Logic for inserting friends
        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            try {
```



186. 编写一个 JDBC 应用以升序排列显示数据。

```java
import java.sql.*;

public class JDBC_Sorting {

    static final String JDBC_DRIVER = "com.mysql.jdbc.Driver";
    static final String DB_URL = "jdbc:mysql://localhost/FRIENDS";
    static final String USER = "username";
    static final String PASS = "password";

    public static void main(String[] args) {
        Connection conn = null;
        Statement stmt = null;
        try {
            Class.forName(JDBC_DRIVER);
            conn = DriverManager.getConnection(DB_URL, USER, PASS);
            System.out.println("Connected database successfully...");
            stmt = conn.createStatement();

            // Extract records in ascending order by first name.
            System.out.println("Fetching records in ascending order...");
            String sql = "SELECT id, first, last, age FROM Registration ORDER BY first ASC";
            ResultSet rs = stmt.executeQuery(sql);
            while(rs.next()){
                int id = rs.getInt("id");
                int age = rs.getInt("age");
                String first = rs.getString("first");
                String last = rs.getString("last");
                System.out.print("ID: " + id);
                System.out.print(", Age: " + age);
                System.out.print(", First: " + first);
                System.out.println(", Last: " + last);
            }
            rs.close();

            // Extract records in descending order by first name.
            System.out.println("Fetching records in descending order...");
            sql = "SELECT id, first, last FROM Registration ORDER BY first DESC";
            rs = stmt.executeQuery(sql);
            while(rs.next()){
                int id = rs.getInt("id");
                int age = rs.getInt("age");
                String first = rs.getString("first");
                String last = rs.getString("last");
                System.out.print("ID: " + id);
                System.out.print(", Age: " + age);
                System.out.print(", First: " + first);
                System.out.println(", Last: " + last);
            }
            rs.close();
        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            try {
                if(stmt != null) stmt.close();
                if(conn != null) conn.close();
            } catch (SQLException e) {
                e.printStackTrace();
            }
        }
    }
}
```

187. 编写一个 JDBC 应用程序来删除表。

```java
import java.sql.*;

public class JDBC_DeleteTable {

    static final String JDBC_DRIVER = "com.mysql.jdbc.Driver";
    static final String DB_URL = "jdbc:mysql://localhost/STUDENTS";
    static final String USER = "username";
    static final String PASS = "password";

    public static void main(String[] args) {
        Connection conn = null;
        Statement stmt = null;
        try {
            Class.forName("com.mysql.jdbc.Driver");
            System.out.println("Connecting to a selected database...");
            conn = DriverManager.getConnection(DB_URL, USER, PASS);
            System.out.println("Connected database successfully...");
            System.out.println("Deleting table in given database...");
            stmt = conn.createStatement();
            String sql = "DROP TABLE REGISTRATION ";
            stmt.executeUpdate(sql);
            System.out.println("Table deleted in given database...");
        } catch (SQLException se) {
            se.printStackTrace();
        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            try {
                if (stmt != null)
                    conn.close();
            } catch (SQLException se) {
            }
            try {
                if (conn != null)
                    conn.close();
            } catch (SQLException se) {
                se.printStackTrace();
            }
            System.out.println("Goodbye!");
        }
    }
}
```

188. 从 SQL 数据库表获取数据并显示在 JTable 中？

```java
import java.awt.*;
import java.sql.*;
import java.util.*;
import javax.swing.*;
import javax.swing.table.*;

public class Fetch_Table extends JFrame
{
    public Fetch_Table ()
    {
        ArrayList columnNames = new ArrayList();
        ArrayList data = new ArrayList();

        String url = "jdbc:mysql://localhost:3306/yourdb";
        String userid = "root";
        String password = "sesame";
        String sql = "SELECT * FROM animals";

        try (Connection connection = DriverManager.getConnection(url, userid, password);
             Statement stmt = connection.createStatement();
             ResultSet rs = stmt.executeQuery(sql))
        {
            ResultSetMetaData md = rs.getMetaData();
            int columns = md.getColumnCount();

            // 获取列名
            for (int i = 1; i <= columns; i++)
            {
                columnNames.add(md.getColumnName(i));
            }

            // 获取行数据
            while (rs.next())
            {
                ArrayList row = new ArrayList(columns);
                for (int i = 1; i <= columns; i++)
                {
                    row.add(rs.getObject(i));
                }
                data.add(row);
            }
        } catch (SQLException e)
        {
            System.out.println(e.getMessage());
        }

        Vector columnNamesVector = new Vector();
        Vector dataVector = new Vector();

        for (int i = 0; i < data.size(); i++)
        {
            ArrayList subArray = (ArrayList)data.get(i);
            Vector subVector = new Vector();
            for (int j = 0; j < subArray.size(); j++)
            {
                subVector.add(subArray.get(j));
            }
            dataVector.add(subVector);
        }

        for (int i = 0; i < columnNames.size(); i ++)
            columnNamesVector.add(columnNames.get(i));

        // 使用数据库数据创建表格
        JTable table = new JTable(dataVector, columnNamesVector)
        {
            public Class getColumnClass(int column)
            {
                for (int row = 0; row < getRowCount(); row++)
                {
                    Object o = getValueAt(row, column);
                    if (o != null)
                    {
                        return o.getClass();
                    }
                }
                return Object.class;
            }
        };

        JScrollPane scrollPane = new JScrollPane(table);
        getContentPane().add(scrollPane);

        JPanel buttonPanel = new JPanel();
        getContentPane().add(buttonPanel, BorderLayout.SOUTH);
    }

    public static void main(String[] args)
    {
        Fetch_Table frame = new Fetch_Table ();
        frame.setDefaultCloseOperation(EXIT_ON_CLOSE);
        frame.pack();
        frame.setVisible(true);
    }
}
```

189. 编写一个程序在从菜单选择后绘制形状。

```java
import javax.swing.*;
import javax.swing.event.*;
import java.awt.*;
import java.awt.event.*;

public class Paintpad extends JFrame
{
    JMenuBar mmain;
    JMenuItem shapes, color;
    JMenuItem rect, arc;
    int x1=10, x2=100, y1=100, y2=100, sh=0;

    public Paintpad(String title)
    {
        mmain = new JMenuBar();
        shapes = new JMenu("Shapes");
        color = new JMenu("Color");
    }
}
```



`rect = new JMenuItem("Rectangle");`

`circle = new JMenuItem("Circle");`

`arc = new JMenuItem("Arc");`

`shapes.add(rect);`

`shapes.add(circle);`

`shapes.add(arc);`

`mmain.add(shapes);`

`mmain.add(color);`

`setMenuBar(mmain);`

`setTitle(title);`

`setSize(300,300);`

`setLayout(new FlowLayout());`

`setDefaultCloseOperation(EXIT_ON_CLOSE);`

`rect.addActionListener(new userAction());`

`circle.addActionListener(new userAction());`

`arc.addActionListener(new userAction());`

```
}

class userAction implements ActionListener {
    public void actionPerformed(ActionEvent e) {
        if (e.getSource() == rect) {
            sh=1;
        }
        if (e.getSource() == circle) {
            sh=2;
        }
        if (e.getSource() == arc) {
            sh=3;
        }
    }
    public void drawshape(int i) {
        Graphics g = getGraphics();
        g.setColor(Color.red);
        if (i==1) {
            g.drawRect(x1, y1, x2-x1, y2-y1);
        }
        if (i==2) {
            g.drawOval(x1, y1, x2-x1, y2-y1);
        }
        if (i==3) {
            g.drawArc(x1, y1, x2-x1, y2-y1, 0, 180);
        }
    }
}
public static void main(String ar[]) {
    new Paintpad("Drawing");
}
```

# SERVLET

在 Web 开始用于交付后，服务提供者意识到需要动态内容。开发者研究了使用服务器平台来实现相同目的。通用接口（CGI）服务器端脚本是生成动态内容的主要技术。但是，CGI 脚本技术有许多缺点，包括平台依赖性和可扩展性差。

为了解决这些局限性，Java Servlet 技术被创建出来，作为提供动态、面向用户内容的一种方式。Servlet 可以描述为：

- Servlet 是一种用于创建 Web 应用的技术。
- Servlet 可以访问整个 Java API，包括用于访问企业数据库的 JDBC API。
- Servlet 在 Web 服务器的地址空间内执行。没有必要为每个客户端请求创建单独进程。
- Servlet 是一种 Java 编程类，用于扩展通过请求-响应编程模型访问的服务器的功能。
- Servlet 是平台无关的，因为它们是用 Java 编写的。
- Servlet 是一个扩展服务器功能并响应传入请求的类。它可以响应任何类型的请求。

CGI 技术允许 Web 服务器调用外部程序并将 HTTP 请求信息传递给外部程序以处理请求。对于每个请求，它都会启动一个新进程。

市场上有很多支持 servlet 的 Web 服务器。某些 Web 服务器可以免费下载，Tomcat 就是其中之一。

`javax.servlet` 包包含了 servlet 或 Web 容器使用的许多接口和类。

`javax.servlet.http` 包包含了专门负责 HTTP 请求的接口和类。

## Servlet 生命周期

1. 加载 Servlet 类。
2. 实例化 Servlet 实例。
3. 调用 `init` 方法。
4. 调用 `service` 方法。
5. 调用 `destroy` 方法。
- 通过调用 `init()` 方法初始化 servlet。
- Servlet 调用 `service()` 方法来处理客户端请求。
- 通过调用 `destroy()` 方法终止 servlet。

## Servlet 类型

1. 通用 Servlet（Generic Servlet）：`GenericServlet` 类可以处理任何类型的请求，因为它是协议无关的。
2. HttpServlet：`HttpServlet` 类继承自 `GenericServlet` 类并实现了 `Serializable` 接口。

它提供了专门针对 HTTP 的特定方法，如 `doGet`、`doPost`、`doHead`、`doTrace` 等。

### 190. 编写一个 servlet 打印“hello”消息

```java
import java.io.*;
import javax.servlet.*;

public class First implements Servlet{
    ServletConfig config=null;
    public void init(ServletConfig config){
        this.config=config;
        System.out.println("servlet is initialized");
    }
    public void service(ServletRequest req, ServletResponse res)
        throws IOException, ServletException{
        res.setContentType("text/html");
        PrintWriter out=res.getWriter();
        out.print("<html><body>");
        out.print("<b>hello Swati Computers</b>");
        out.print("</body></html>");
    }
    public void destroy(){System.out.println("servlet is destroyed");}
    public ServletConfig getServletContext(){return config;}
    public String getServletInfo(){return "";}
}
```

### 191. 编写一个 HTTP HttpServlet 来打印 Hello 消息

```java
import java.io.*;
import javax.servlet.*;
import javax.servlet.http.*;

public class Second extends HttpServlet {
    private String message;
    public void init() throws ServletException {
        message = "Hello Swati Computers";
    }
    public void doGet(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {
        // 设置响应内容类型
        response.setContentType("text/html");
        // 实际逻辑在此处
        PrintWriter out = response.getWriter();
        out.println("<h1>" + message + "</h1>");
    }
    public void destroy() {
        // 什么都不做
    }
}
```

### 192. 编写一个 servlet 输入用户名并打印欢迎消息（在 NetBeans 中）

`a.html`

```html
<html>
<head>
  <title>待定：提供标题</title>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width">
</head>
<body>
  <form action="./servlet1" method="post">
    输入姓名<input type="text" name="nam">
    <input type="submit">
  </form>
</body>
</html>
```

`Servlet1`

```java
import java.io.IOException;
import java.io.PrintWriter;
import javax.servlet.ServletExceptionException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

public class servlet1 extends HttpServlet {
    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {
        PrintWriter out = response.getWriter();
        out.write("Welcome user "+request.getParameter("nam"));
    }
}
```

### 194. 编写一个 servlet 检查用户名和密码，如果登录无效，则返回 HTML 页面重新登录，或者向用户打印欢迎消息

`Form1.html`

```html
<html>
<head>
<title>待定：提供标题</title>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width">
</head>
<body>
<form action="./servlet1" method="post">
输入姓名<input type="text" name="nam"><br>
输入密码<input type="password" name="pwd"><br>
<input type="Login">登录
</form>
</body>
</html>
```

`Servlet1`

```java
import java.io.IOException;
import java.io.PrintWriter;
import javax.servlet.RequestDispatcher;
import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

public class servlet1 extends HttpServlet {
    String n,p;
    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response)
        throws ServletException, IOException {
            response.setContentType("text/html");
            PrintWriter out = response.getWriter();
            out.write("Welcome user "+request.getParameter("nam"));
            n=request.getParameter("nam");
            p=request.getParameter("pwd");
            RequestDispatcher rd=request.getRequestDispatcher("servlet2");
            if(n.equals("swati") && p.equals("computers")) {
                rd.forward(request, response);
            } else {
                out.println("Invalid Login");
                rd=request.getRequestDispatcher("form1.html");
                rd.include(request, response);
            }
        }
}
```

`Servlet2`

```java
import java.io.IOException;
import java.io.PrintWriter;
import javax.servlet.ServletExceptionException;

public class servlet2 extends HttpServlet {
    protected void doPost(HttpServletRequest req, HttpServletResponse res)
    throws ServletException, IOException {
        res.setContentType("text/html");
        PrintWriter pw=res.getWriter();
        pw.write("welcome user " + req.getParameter("nam"));
    }
}
```

### 195. 编写一个 servlet 重定向到指定的网站

`Form.html`

```html
<html>
<head>
    <title>重定向标题</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width">
</head>
<body>
    <form action="./servlet1" method="post">
        输入想要打开的网站:<br>
        https://www.<input type="text" name="nam"><br>
        <input type="submit" value="发送">
    </form>
</body>
</html>
```

`Servlet1`

```java
import java.io.IOException;
import java.io.PrintWriter;
import javax.servlet.ServletExceptionException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

public class servlet1 extends HttpServlet {
    String n;
    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {
        response.setContentType("text/html");
        PrintWriter out = response.getWriter();
```



`n=request.getParameter("nam");`

`response.sendRedirect("http://www."+n);`

195. 编写一个程序在 servlet 配置中给出用户名并显示。

```xml
Web.xml

<servlet>
    <servlet-name>servlet1</servlet-name>
    <servlet-class>servlet1</servlet-class>
    <init-param>
        <param-name>author</param-name>
        <param-value>Swati saxena</param-value>
    </init-param>
</servlet>
```

```java
Servlet1

import java.io.IOException;
import java.io.PrintWriter;
import javax.servlet.RequestDispatcher;
import javax.servlet.ServletConfig;
import javax.servlet.ServletExceptionException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

public class servlet1 extends HttpServlet {
    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {
        response.setContentType("text/html");
        PrintWriter out = response.getWriter();
        ServletConfig conf=getServletConfig();
        out.println(conf.getInitParameter("author"));
    }
}
```

1. 出版社为许多作者出版书籍。编写一个 servlet 在上下文参数中写入出版社名称并显示。

```xml
Web.xml

<context-param>
    <param-name>publisher</param-name>
    <param-value>bpb </param-value>
</context-param>
<servlet>
    <servlet-name>servlet1</servlet-name>
    <servlet-class>servlet1</servlet-class>
</servlet>
```

```java
</web-app>
```

```java
servlet1
```

```java
import java.io.*;
import javax.servlet.*;
import javax.servlet.http.*;
```

```java
public class servlet1 extends HttpServlet {
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {
        response.setContentType("text/html");
        PrintWriter out = response.getWriter();
        ServletContext sc = getServletContext();
        out.println("publisher of book is:"+sc.getParameter("publisher"));
    }
}
```

# Session 跟踪技术

Session 跟踪使用了四技术：

- 1. HttpSession
- 2. Cookies
- 3. 隐藏表单字段
- 4. URL 重写

196. 编写一个 servlet，在用户登录时创建 session，并在注销时销毁 session。

```html
Form1.html

<html>
<head>
<title>请提供标题</title>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width">
</head>
<body>
<form action="./servlet1" method="post">
  输入姓名<input type="text" name="name"><br>
  输入密码<input type="password" name="pwd">
  <input type="submit" value="登录">
</form>
</body>
</html>
```

```html
Logout.html

<html>
<head>
  <title>请提供标题</title>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width">
</head>
<body>
  <form action="./logout" method="post">
  确定要注销吗 <input type="submit" value="是">
</form>
</body>
</html>
```

```java
Servlet1

import java.io.IOException;
import java.io.PrintWriter;
import javax.servlet.RequestDispatcher;
import javax.servlet.ServletConfig;
import javax.servlet.ServletExceptionException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;
import javax.servlet.http.HttpSession;

public class servlet1 extends HttpServlet {
    String n,p;
    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {
        response.setContentType("text/html");
        PrintWriter out = response.getWriter();
        RequestDispatcher rd;
        n=request.getParameter("name");
        p=request.getParameter("pwd");
        if(n.equals(p)) {
            HttpSession ses=request.getSession(true);
            ses.setAttribute("user", n);
            rd=request.getRequestDispatcher("servlet2");
            rd.forward(request, response);
        } else {
            rd=request.getRequestDispatcher("form1.html");
            rd.forward(request, response);
        }
    }
}
```

# Servlet2

```java
public class servlet2 extends HttpServlet {
    protected void doPost(HttpServletRequest req, HttpServletResponse res)
    throws ServletException, IOException {
        HttpSession ses=req.getSession(false);
        res.setContentType("text/html");
        PrintWriter pw=res.getWriter();
        pw.write("welcome user " +ses.getAttribute("user"));
        pw.write("<a href=logout.html>退出</a>");
    }
}
```

```java
Logout.java

public class logout extends HttpServlet {
    @Override
    protected void doPost(HttpServletRequest req, HttpServletResponse res) throws ServletException, IOException {
        HttpSession ses=req.getSession(false);
        ses.invalidate();
        res.sendRedirect("form1.html");
    }
}
```

197. 编写一个 servlet，创建一个 cookie 文件将用户名保存在 cookie 文件中并显示？

```java
MyServlet

import java.io.*;
import javax.servlet.*;
import javax.servlet.http.*;

public class MyServlet extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        response.setContentType("text/html");
        String name = request.getParameter("user");
        String pass = request.getParameter("pass");
        if(pass.equals("1234")) {
            Cookie ck = new Cookie("username",name);
            response.addCookie(ck);
            response.sendRedirect("First");
        }
    }
}
```

## First

```java
import java.io.*;
import javax.servlet.*;
import javax.servlet.http.*;

public class First extends HttpServlet {
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
        throws ServletException, IOException {
        response.setContentType("text/html");
        PrintWriter out = response.getWriter();
        Cookie[] cks = request.getCookies();
        out.println("Welcome "+cks[0].getValue());
    }
}
```

198. 编写一个 servlet，在隐藏字段中为多个 servlet 存储用户名并进行显示。

```html
Form1.html

<form method="post" action=".servlet1">
姓名:<input type="text" name="user" /><br>
密码:<input type="text" name="pass" /><br>
<input type="submit" value="提交">
</form>
```

```java
import java.io.*;
import javax.servlet.*;
import javax.servlet.http.*;

public class servlet1 extends HttpServlet {
    protected void doPost(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {
        response.setContentType("text/html");
        PrintWriter out = response.getWriter();
        String user = request.getParameter("user");
        // ... 隐藏字段的逻辑
    }
}
```

```html
</form>
</body></html
```

## Servlet1 

```java
public class servlet1 extends HttpServlet {
    @Override
    public void doGet(HttpServletRequest request, HttpServletResponse response)
    throws ServletException, IOException {
        response.setContentType("image/jpeg");
        ServletOutputStream out = response.getOutputStream();
        FileInputStream fin = new FileInputStream("f:\\image\\1.jpg");
        int ch = 0;
        while ((ch = fin.read()) != -1) {
            out.write(ch);
        }
        fin.close();
        out.close();
    }
}
```

203. 编写一个程序，在表单中输入学号、姓名和分数，使用 servlet 进行验证并将记录插入到数据库中？

```html
<html
    <title>验证项目</title>
    <head><center><h2>学生表单验证</h2></center></head>
    <body>
```

```html
<center>
<form action="./Validation" method="post">
  <table border="1">
  <tr>
    <th>输入学号：</th>
    <td><input type="text" name="validpro_sno" value=""></td>
  </tr>
  <tr>
    <th>输入姓名：</th>
    <td><input type="text" name="validpro_sname" value=""></td>
  </tr>
  <tr>
    <th>输入分数：</th>
    <td><input type="text" name="validpro_smarks" value=""></td>
  </tr>
  <table>
  <tr>
    <td><input type="submit" value="插入"></td>
    <td><input type="reset" value="重置"></td>
  </tr>
  </table>
  </table>
</form>
</center>
</body>
</html>
```

`Validation.java`



```java
import javax.servlet.*;
import javax.servlet.http.*;
import java.io.*;
import java.sql.*;
import java.util.*;

public class Validation extends HttpServlet {

    public void doGet(HttpServletRequest req, HttpServletResponse res)
            throws ServletException, IOException {
        ArrayList al = new ArrayList();
        res.setContentType("text/html");
        PrintWriter pw = res.getWriter();
        String sno1 = req.getParameter("valid_pro_sno");
        String sname = req.getParameter("valid_pro_sname");
        String smarks1 = req.getParameter("valid_pro_smarks");
        int sno = 0;
        float smarks = 0;

        if ((sno1 == null) || (sno1.equals(""))) {
            al.add("请输入学号...");
        } else {
            try {
                sno = Integer.parseInt(sno1);
            } catch (NumberFormatException nfe) {
                al.add("学号处应提供 int 类型数据...");
            }
        }

        if ((sname == null) || (sname.equals(""))) {
            al.add("请输入姓名...");
        }

        if ((smarks1 == null) || (smarks1.equals(""))) {
            al.add("请输入分数...");
        } else {
            try {
                smarks = Float.parseFloat(smarks1);
            } catch (NumberFormatException nfe) {
                al.add("分数处应提供 float 类型数据...");
            }
        }

        if (al.size() != 0) {
            pw.println(al);
        } else {
            try {
                Class.forName("oracle.jdbc.driver.OracleDriver");
                Connection con = DriverManager.getConnection(
                    "jdbc:oracle:thin@localhost:1521:Hanuman",
                    "scott",
                    "tiger"
                );
                PreparedStatement ps = con.prepareStatement(
                    "insert into Student values(?,?,?)"
                );
                ps.setInt(1, sno);
                ps.setString(2, sname);
                ps.setFloat(3, smarks);
                int i = ps.executeUpdate();

                if (i > 0) {
                    pw.println("记录插入成功...");
                } else {
                    pw.println("记录插入失败...");
                }

                con.close();
            } catch (Exception e) {
                res.sendError(503, "数据库出现问题...");
            }
        }
    }

    public void doPost(HttpServletRequest req, HttpServletResponse res)
            throws ServletException, IOException {
        doGet(req, res);
    }
}
```

## 204. 编写一个程序解释 Servlet 过滤器（Filter）的使用

```xml
Web.xml
<filter>
    <filter-name>LogFilter</filter-name>
    <filter-class>LogFilter</filter-class>
    <init-param>
        <param-name>test-param</param-name>
        <param-value>初始化参数</param-value>
    </init-param>
</filter>

<filter-mapping>
    <filter-name>LogFilter</filter-name>
    <url-pattern>/*</url-pattern>
</filter-mapping>
```

### LogFilter.java

```java
import javax.servlet.*;
import javax.servlet.http.*;
import java.io.*;
import java.util.*;

public class LogFilter implements Filter {

    public void init(FilterConfig config) throws ServletException {
        String testParam = config.getInitParameter("test-param");
    }

    public void doFilter(
            ServletRequest request,
            ServletResponse response,
            FilterChain chain)
            throws IOException, ServletException {
        PrintWriter out = response.getWriter();
        String ipAddress =
            ((HttpServletRequest) request).getRemoteAddr();
        out.println("IP地址: " + ipAddress);
        chain.doFilter(request, response);
    }

    public void destroy() {
    }
}
```

```html
<title>JSP Page</title>
</head>
<form name="frm" method="get" action="user.jsp">
Enter name<input type="text" name="un"><br>
Enter password<input type="password" name="pwd"><br>
Select gender <input type="radio" name="gen" value="male">male<br>
<input type="radio" name="gen" value="female">female<br>
Language known:<input type="checkbox" value="english" name="en">Eng
<input type="checkbox" value="hindi" name="hi">hin
<input type="checkbox" value="french" name="fr">Fre
<input type="submit" value="Register">
</body>
</html>
```

### User.jsp

```jsp
<@ import="java.util.*;" contentType="text/html;pageEncoding="UTF-8" %>
<!DOCTYPE html>
<<html>
<head>
<meta http-equiv="Content-Type" content="text/html;charset=UTF-8">
<title>JSP Page</title>
</head>
<body>
<%
Enumeration e = getParameterNames();
while (e.hasMoreElements()) {
    String n = e.nextElement().toString();
    out.println(request.getParameter(n));
}
%>
</body>
</html>
```

## 209. 编写一个 JSP 页面来登录用户并创建会话，点击时应销毁会话并显示主页

### Index.jsp

```jsp
<html>
<head>
  <meta http-equiv="Content-Type" content="text/html;charset=UTF-8">
  <title>JSP Page</title>
</head>
<body>
  <form name="frm" method="get" action="user.jsp">
    Enter name<input type="text" name="un"><br>
    Enter password<input type="password" name="pwd"><br>
    <input type="submit" value="Login">
  </form>
</body>
</html>
```

### User.jsp

```jsp
<html>
<head>
  <meta http-equiv="Content-Type" content="text/html;charset=UTF-8">
  <title>JSP Page</title>
</head>
<body>
<%
  session.setAttribute("uname", request.getParameter("un"));
  out.print("<a href='next.jsp'>Logout</a>");
%>
</body>
</html>
```

### Next.jsp

```jsp
<%@page contentType="text/html" pageEncoding="UTF-8" %>
<!DOCTYPE html>
<html>
<head>
  <meta http-equiv="Content-Type" content="text/html;charset=UTF-8">
  <title>JSP Page</title>
</head>
<body>
<%
  session.invalidate();
  response.sendRedirect("index.jsp");
%>
</body>
</html>
```

## 210. 编写一个 JSP 页面来发送电子邮件

```jsp
<%@page import = "java.io.*,java.util.*,java.mail.*" %>
<%@page import = "javax.mail.internet.*,javax.activation.* %>
<%@page import = "javax.servlet.http.*,javax.servlet.*" %>
```

```jsp
<%
String status;

// Recipient's email ID needs to be mentioned.
String to = "swaticcomputers01@gmail.com";

// Sender's email ID needs to be mentioned
String from = "sc01@gmail.com";

// Assuming you are sending email from localhost
String host = "localhost";

// 获取系统属性对象
Properties properties = System.getProperties();

// 设置邮件服务器
properties.setProperty("mail.smtp.host", host);

// 获取默认的 Session 对象。
Session mailSession = Session.getDefaultInstance(properties);

try {
    // 创建一个默认的 MimeMessage 对象。
    MimeMessage message = new MimeMessage(mailSession);

    // 设置 header 中的 From: 字段
    message.setFrom(new InternetAddress(from));

    // 设置 header 中的 To: 字段
    message.addRecipient(
        Message.RecipientType.TO,
        new InternetAddress(to)
    );

    // 设置 Subject: header 字段
    message.setSubject("This is the Subject Line!");

    // 现在设置实际消息
    message.setText("This is actual message");

    // 发送消息
    Transport.send(message);
    status = "Sent message successfully....";
} catch (MessagingException mex) {
    mex.printStackTrace();
    status = "Error: unable to send message....";
}
%>
```

```html
<html>
<head>
<title>Send Email using JSP</title>
</head>
<body>
<center>
<h1>Send Email using JSP</h1>
</center>
<p align="center">
<%
out.println("status: " + status);
%>
</p>
</body>
</html>
```

## 21. 编写不同的 JSP 程序，通过不同的 HTML 表单来上传图片

使用 HTML 表单来显示图片。

使用一个包含两个文本字段的 HTML 表单来将文件上传到服务器。

```html
<html>
<head>
<title>Add Photo</title>
</head>
<body>
<h2>Add Photo</h2>
<form enctype="multipart/form-data" action="add" method="post">
<table>
<tr>
    <td>ID:</td>
    <td><input type="text" name="id"></td>
</tr>
<tr>
    <td>Title:</td>
    <td><input type="text" name="title"></td>
</tr>
<tr>
    <td>Photo:</td>
    <td><input type="file" name="photo"></td>
</tr>
</table>
<input type="submit" value="Upload">
</form>
</body>
</html>
```

```java
@Override
protected void doPost(
        HttpServletRequest request,
        HttpServletResponse response)
        throws ServletException, IOException {
    processRequest(request, response);
}
```

### DisplayPhotoServlet

`DisplayPhotoServlet.java` 将从 `PHOTOS` 表的 `PHOTO` 列获取的单个照片作为输出流发送到浏览器。该 Servlet 接收 `id` 作为参数（查询字符串），并将照片发送到 `IMG` 标签。

### DisplayPhotoServlet.java

```java
import java.io.IOException;
import java.io.InputStream;
import java.io.OutputStream;
import java.sql.Blob;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import javax.servlet.ServletException;
```



```java
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

public class DisplayPhotoServlet extends HttpServlet {

    protected void processRequest(HttpServletRequest request,
    HttpServletResponse response)
    throws ServletException, IOException {

    try {
        Class.forName("oracle.jdbc.driver.OracleDriver");
        Connection con = DriverManager.getConnection("jdbc:oracle:thin@localhost:1521:xe", "hr", "hr");
```

```java
        PreparedStatement ps = con.prepareStatement(
        ("select photo from photos where id = ?");
        String id = request.getParameter("id");
        ps.setString(1,id);
        ResultSet rs = ps.executeQuery();
        rs.next();
        Blob b = rs.getBlob("photo");
        response.setContentType("image/jpeg");
        response.setContentLength((int) b.length());
        InputStream is = b.getBinaryStream();
        OutputStream os = response.getOutputStream();
        byte buf[] = new byte[(int) b.length()];
        is.read(buf);
        os.write(buf);
        os.close();
    } catch (Exception ex) {
        System.out.println(ex.getMessage());
    }
```

```java
    @Override
    protected void doGet(HttpServletRequest request,
    HttpServletResponse response)
    throws ServletException, IOException {
        processRequest(request, response);
    }

    @Override
    protected void doPost(HttpServletRequest request,
    HttpServletResponse response)
    throws ServletException, IOException {
        processRequest(request, response);
    }
}
```

这里是包含与 Servlet 相关条目的`web.xml`文件。

## 306 JAVA

```xml
<servlet>
  <servlet-name>AddPhoto</servlet-name>
  <servlet-class>AddPhotoServlet</servlet-class>
</servlet>
<servlet>
  <servlet-name>ListPhotos</servlet-name>
  <servlet-class>ListPhotosServlet</servlet-class>
</servlet>
<servlet>
  <servlet-name>DisplayPhotoServlet</servlet-name>
  <servlet-class>DisplayPhotoServlet</servlet-class>
</servlet>
<servlet-mapping>
  <servlet-name>AddPhoto</servlet-name>
  <url-pattern>/addphoto</url-pattern>
</servlet-mapping>
<servlet-mapping>
  <servlet-name>ListPhotos</servlet-name>
  <url-pattern>/listphotos</url-pattern>
</servlet-mapping>
<servlet-mapping>
  <servlet-name>DisplayPhotoServlet</servlet-name>
  <url-pattern>/displayphoto</url-pattern>
</servlet-mapping>
```

所有 Servlet 都已创建，构建项目并部署。然后运行`addphoto.html`并输入某些照片的详情。然后你可以点击 List Photos（列表照片）查看放置在数据库中的照片列表。

## 212. 编写两个 JApplet 并显示 applet 之间的通信

```java
First.java
import java.applet.Applet;
import javax.swing.JApplet;
import java.applet.AppletContext;
```

```java
import javax.swing.*;
import java.awt.event.*;
import java.awt.*;

public class first extends JApplet implements ActionListener {
    JButton b,b1,b2;
    Color c;
    public void init() {
        setLayout(new FlowLayout());
        b=new JButton("Red");
        b1=new JButton("Green");
        b2=new JButton("Blue");
        add(b);add(b1);add(b2);
        b.addActionListener(this);
        b1.addActionListener(this);
        b2.addActionListener(this);
    }
    public Color getCol() {
        return c;
    }
    public void set(Color c) {
        this.c=c;
    }
    public void actionPerformed(ActionEvent ae) {
        if(ae.getSource()==b) c=new Color(255,0,0);
        else if(ae.getSource()==b1)
            c=new Color(0,255,0);
        else if(ae.getSource()==b2)
            c=new Color(0,0,255);
    }
```

## 308 JAVA

```java
    second f =
    (second)getAppletContext().getApplet("Second");
    if(f!=null)f.repaint();
```

```java
}
}
```

```java
Second.java
import java.applet.Applet;
import javax.swing.JApplet;
import javax.swing.*;
import java.awt.event.*;
import java.awt.*;

public class second extends JApplet
{
    Color c;
    public void init()
    {
        c=new Color(0,0,0);
    }
    public void paint(Graphics g)
    {
        //g.setColor(Color.pink);
        first f =
        (first)getAppletContext().getApplet("First");
        if(f!=null)
        {
            c=f.getCol();
        }
        g.setColor(c);
        g.fillOval(50,50,100,100);
    }
}
```

## 额外努力：RMI, Swing 中的 Border, LookAndFeel 等

### 13. 什么是 RMI？

#### 远程方法调用 (RMI)

RMI 是一种提供在 Java 中创建分布式应用程序机制的 API。RMI 允许对象通过两个对象存根（stub）和骨架（skeleton）调用在另一个 JVM 上的对象的方法。RMI 是分布式应用程序，是因为：

1. 应用需要定位远程方法。
2. 它需要与远程对象进行通信。
3. 应用需要加载类定义。

### 14. 什么是可插拔的外观感知（pluggable Look and feel）？

Java Swing 提供了可插拔的外观感知能力，允许 GUI 根据程序员设置更改外观。

### 15. 编写一个程序显示鼠标滚轮移动

```java
import java.awt.BorderLayout;
import java.awt.Dimension;
import java.awt.event.MouseWheelEvent;
```

## 10 JAVA

```java
import java.awt.event.MouseWheelListener;
import javax.swing.Border;
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.JScrollPane;
import javax.swing.JTextArea;

public class aa extends JPanel implements MouseWheelListener {
    JTextArea textArea = new JTextArea();
    JScrollPane scrollPane = new JScrollPane(textArea);
    static String newline = "\n";

    public aa() {
        super(new BorderLayout());
        textArea.setEditable(false);
        scrollPane.setVerticalScrollBar(JScrollPane.VERTICAL_ALWAYS);
        textArea.append("This text area displays information about its mouse events." + newline);
        textArea.addMouseWheelListener(this);
        setPreferredSize(new Dimension(400,250));
        add(scrollPane, BorderLayout.CENTER);
        setBorder(BorderFactory.createEmptyBorder(20,20,20,20));
    }

    public void mouseWheelMoved(MouseWheelEvent e) {
        String message;
        int notches = e.getWheelRotation();
        if (notches < 0) {
            message = "Mouse moved UP " + -notches + " notches" + newline;
        } else {
            message = "Mouse moved DOWN " + notches + " notches" + newline;
        }
        if (e.getScrollType() == MouseWheelEvent.WHEEL_UNIT_SCROLL) {
            message += " Scroll type: WHEEL_UNIT_SCROLL" + newline;
            message += " Scroll amount: " + e.getScrollAmount() + " unit increments per notch" + newline;
            message += " Vertical unit increment: " + e.getUnitsToScroll() + " unit increments" + newline;
            message += " scrollPane increment: " + scrollPane.getScrollBar().getIncrement(1) + "pixels" + newline;
        } else if (e.getScrollType() == MouseWheelEvent.WHEEL_BLOCK_SCROLL) {
            message += " Scroll type: WHEEL_BLOCK_SCROLL" + newline;
            message += " Vertical block increment: " + scrollPane.getScrollBar().getBlockIncrement(1) + "pixels" + newline;
        }
        saySomething(message, e);
    }

    void saySomething(String eventDescription, MouseWheelEvent e) {
        textArea.append(e.getComponent().getClass().getName() + " " + eventDescription);
        textArea.setCaretPosition(textArea.getDocument().getLength());
    }

    public static void main(String[] args) {
        JFrame frame = new JFrame("MouseWheelDemo");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        JComponent contentPane = new aa();
        newContentPane.setOpaque(true);
        frame.setContentPane((JComponent)contentPane);
        frame.pack();
        frame.setVisible(true);
    }
}
}
}
```

## 使用名称绑定方法

```java
import java.rmi.*;
import java.rmi.registry.*;

public class MyServer
{
    public static void main(String args[]){
        try{
            Adder stub=new AdderRemote();
            Naming.rebind("rmi://localhost:5000/sonoo",stub);
        } catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

## 调用远程方法的客户端

```java
import java.rmi.*;

public class MyClient{
    public static void main(String args[]){
        try{
            Adder stub=(Adder)Naming.lookup("rmi://localhost:5000/sonoo");
            System.out.println(stub.add(34,4));
        } catch(Exception e){
        }
    }
}
```

### 217. 写一个程序，点击按钮时更改边框？

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.border.*;
import java.util.*;

class fd1 extends JFrame implements ActionListener {
    Border bor;
    FileDialog f;
    JButton b,b1,b2,b3,b4;
    JPanel p;

    public void fd1(String tit)
    {
        super(tit);
        double n=(Math.random()*100);
        System.out.println(n);
        p=new JPanel();
        b=new JButton("click");
        b1=new JButton("click");
        b2=new JButton("click");
        b3=new JButton("click");
        b4=new JButton("click");
```



### 218. 写一个程序，点击按钮时更改组件的显示和外观（Look and Feel）？

```java
import java.util.*;
import com.sun.java.swing.plaf.motif.MotifLookAndFeel;
import com.sun.java.swing.plaf.windows.WindowsLookAndFeel;
import java.awt.*;
import java.awt.event.*;
import java.util.ArrayList;
import java.util.logging.Level;
import java.util.logging.Logger;
import javax.swing.*;
import javax.swing.plaf.metal.MetalLookAndFeel;
import javax.swing.plaf.nimbus.NimbusLookAndFeel;

class look extends JFrame implements ActionListener
{
    JButton b,b1,b2,b3,b4;
    JPanel p;
    MetalLookAndFeel mf;
    WindowsLookAndFeel wf;
    MotifLookAndFeel mof;
    NimbusLookAndFeel nf;

    public look(String tit)
    {
        super(tit);
        b=new JButton("click");
        p=new JPanel();
        b1=new JButton("click");
        b2=new JButton("click");
        b3=new JButton("click");
        b4=new JButton("click");
        p.add(b);
        getContentPane().add(p);
        getContentPane().add(b1,"North");
        getContentPane().add(b2,"South");
        getContentPane().add(b3,"East");
        getContentPane().add(b4,"West");
        b.addActionListener(this);
        b1.addActionListener(this);
        b2.addActionListener(this);
        b3.addActionListener(this);
        b4.addActionListener(this);
        setSize(200,200);
        setVisible(true);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
    }

    public void actionPerformed(ActionEvent ae)
    {
        if(ae.getSource()==b1)
        {
            mf=new MetalLookAndFeel();
            try {
                UIManager.setLookAndFeel(mf);
                SwingUtilities.updateComponentUI(this);
            } catch (UnsupportedLookAndFeelException ex) {
                Logger.getLogger(look.class.getName()).log(Level.SEVERE,null,ex);
            }
        }
        if(ae.getSource()==b2)
        {
            wf=new WindowsLookAndFeel();
            try {
                UIManager.setLookAndFeel(wf);
                SwingUtilities.updateComponentUI(this);
                for(Component c:getContentPane().getComponents())
                {
                    if(c instanceof JButton) {
                        c.setBackground(Color.yellow);
                    }
                    if(c instanceof JPanel) {
                        c.setBackground(Color.pink);
                    }
                    ((JButton)ae.getSource()).setBackground(Color.red);
                }
            } catch (UnsupportedLookAndFeelException ex) {
                Logger.getLogger(look.class.getName()).log(Level.SEVERE,null,ex);
            }
        }
        if(ae.getSource()==b3)
        {
            mof=new MotifLookAndFeel();
            try {
                UIManager.setLookAndFeel(mof);
                SwingUtilities.updateComponentUI(this);
            } catch (UnsupportedLookAndFeelException) {
                Logger.getLogger(look.class.getName()).log(Level.SEVERE,null,ex);
            }
        }
        if(ae.getSource()==b4)
        {
            nf=new NimbusLookAndFeel();
            try {
                UIManager.setLookAndFeel(nf);
                SwingUtilities.updateComponentUI(this);
            } catch (UnsupportedLookAndFeelException ex) {
                Logger.getLogger(look.class.getName()).log(Level.SEVERE, null, ex);
            }
        }
    }
}

public class looks {
    public static void main(String [] args)
    {
        new look("hi");
    }
}
```

### 219. 为学校项目编写一个 JFrame，包含校长、老师和学生标签页，在标签页中创建不同的按钮以提供功能。

```java
import javax.swing.*;
import java.awt.*;
import com.sun.java.swing.plaf.motif.MotifLookAndFeel;
import com.sun.java.swing.plaf.windows.WindowsLookAndFeel;
import java.util.logging.Level;
import java.util.logging.Logger;

class school extends JFrame implements ActionListener,MouseListener
{
    JTabbedPane tp;
    JPanel p,t,s;
    JButton stu,teac,per,notes,stuv,ok;
    JTextField a,b,c,d,e,f,g,h;
    JLabel l1,l2,l13,l14,l15,l16,l17,l18;
    Dialog d1,d2;
    MotifLookAndFeel mof;
    WindowsLookAndFeel wlf;

    public school(String tit)
    {
        super(tit);
        stu=new JButton("Student");
        teac=new JButton("Teacher");
        per=new JButton("personal info");
        notes=new JButton("Notes");
        stuv=new JButton("student window");
        tp=new JTabbedPane();
        p=new JPanel();
        ok=new JButton("Ok");
        t=new JPanel();
        s=new JPanel();
        l1=new JLabel("Name");
        l2=new JLabel("Class");
        l13=new JLabel("Roll No.");
        l14=new JLabel("Attendance");
        l15=new JLabel("Grades");
        l16=new JLabel("Name");
        l17=new JLabel("Attendance");
        l18=new JLabel("Complains");
        a=new JTextField(10);
        b=new JTextField(10);
        c=new JTextField(10);
        d=new JTextField(10);
        e=new JTextField(10);
        f=new JTextField(10);
        g=new JTextField(10);
        h=new JTextField(10);
        tp.add(p,"principal");
        tp.add(t,"teacher");
        tp.add(s,"student");
        getContentPane.add(tp);
        setSize(500,500);
        setVisible(true);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
    }

    public void actionPerformed(ActionEvent ae)
    {
        if(ae.getSource()==per)
        {
            mof=new MotifLookAndFeel();
            try {
                UIManager.setLookAndFeel(mof);
                SwingUtilities.updateComponentUI(this);
            } catch (UnsupportedLookAndFeelException ex) {
                Logger.getLogger(school.class.getName()).log(Level.SEVERE,null,ex);
            }
        }
        if(ae.getSource()==stu)
        {
            // 实现学生功能
        }
    }

    public void mouseClicked(MouseEvent e) {}
    public void mouseEntered(MouseEvent e) {}
    public void mouseExited(MouseEvent e) {}
    public void mousePressed(MouseEvent e) {}
    public void mouseReleased(MouseEvent e) {}
}
```

### 额外努力：323

```java
wlf = new WindowsLookAndFeel();
try {
    UIManager.setLookAndFeel(wlf);
    SwingUtilities.updateComponentTreeUI(this);
} catch (UnsupportedLookAndFeelException ex) {
    Logger.getLogger(school.class.getName()).log(Level.SEVERE, ex);
}
d1 = new JDialog(this, "hi", true);
d1.setLayout(null);
d1.add(ok);
ok.setBounds(50,200,50,20);
d1.add(l11);
l11.setBounds(20,20,70,20);
d1.add(l12);
l12.setBounds(20,50,100,20);
d1.add(l13);
```



`l13.setBounds(20,80,100,20);`

`d1.add(l14);`

`l14.setBounds(20,110,100,20);`

`d1.add(l15);`

`l15.setBounds(20,140,100,20);`

`d1.add(a);`

`a.setBounds(100,20,70,20);`

`d1.add(b);`

`b.setBounds(100,50,100,20);`

`d1.add(c);`

`c.setBounds(100,80,100,20);`

`d1.add(d);`

`d.setBounds(100,110,100,20);`

`d1.add(e);`

`e.setBounds(100,140,100,20);`

`d1.setSize(400,400);`

`d1.setVisible(true);`

```java
if(ae.getSource() == ok) {
  d1.setVisible(false);
}

if(ae.getSource() == teac) {
  d2 = new JDialog(this, "hi", true);
  d2.setLayout(null);
  d2.add(f);
  f.setBounds(100,20,100,20);
  d2.add(g);
  g.setBounds(100,50,100,20);
  d2.add(h);
  h.setBounds(100,80,100,20);
  d2.add(l16);
  l16.setBounds(20,20,70,20);
  d2.add(l17);
  l17.setBounds(20,50,100,20);
  d2.add(l18);
  l18.setBounds(20,80,100,20);
  d2.setSize(400,400);
  d2.setVisible(true);
}

if(ae.getSource() == per) {
  String str = f.getText();
  String str1 = g.getText();
  String str2 = h.getText();
  JOptionPane.showMessageDialog(this, str + " " + str1 + "% " + str2);
}

if(ae.getSource() == stuv) {
  String str = a.getText();
  String str1 = b.getText();
  String str2 = c.getText();
  String str3 = d.getText();
  String str4 = e.getText();
  JOptionPane.showMessageDialog(this, str + " " + str1 + " class " + str2 + " Roll no. " + str3 + "%" + str4 + " CGPA");
}

public static void main(String[] args) {
  new school("hi");
}
```

220. 使用线程编写一个 applet 实现文本的跑灯效果。

```java
import java.applet.*;
import java.awt.*;

public class Marquee extends Applet implements Runnable {
  String txt;
  Image img;
  Font f;
  Color color;
  int fontsize, fontstyle, pause;
  Image offscreenimage;
  Graphics ofg;
  Thread mythread = null;
  int offset = 0;
  String fontname;

  public void init() {
    offscreenimage = createImage(1000,1000);
    img = getImage(getDocumentBase(), "zoomimg.jpg");
    ofg = offscreenimage.getGraphics();
    color = matchcolor(getParameter("color"));
    if (getParameter("fontsize") == null) {
      fontsize = 12;
    } else {
      Integer i1 = new Integer(getParameter("fontsize"));
      fontsize = i1.intValue();
    }
    fontname = getParameter("fontname");
    if (fontname == null)
      fontname = "TimesRoman";
    fontstyle = get(getParameter("fontstyle"));
    if (getParameter("pause") != null) {
      Integer i2 = new Integer(getParameter("pause"));
      pause = i2.intValue();
    } else
      pause = 100;
    f = new Font(fontname, fontstyle, fontsize);
    mythread = new Thread(this);
    txt = getParameter("disptxt");
    if (txt == null) {
      txt = "swati computers";
    }
    txt = txt + "";
  }

  public void start() {
    if (mythread != null) {
      mythread.start();
    }
  }

  public void stop() {
    if (mythread != null) {
      mythread.stop();
    }
  }

  public int get(String str) {
    if (str == null)
      return Font.PLAIN;
    if (str.equalsIgnoreCase("plain"))
      return Font.PLAIN;
    if (str.equalsIgnoreCase("bold"))
      return Font.BOLD;
    if (str.equalsIgnoreCase("italic"))
      return Font.ITALIC;
    return Font.PLAIN;
  }

  public Color matchcolor(String str) {
    if (str == null)
      return Color.black;
    if (str.equalsIgnoreCase("red"))
      return Color.red;
    if (str.equalsIgnoreCase("orange"))
      return Color.orange;
    if (str.equalsIgnoreCase("cyan"))
      return Color.cyan;
    return Color.black;
  }

  public void paint(Graphics g) {
    String str;
    if (offset == (int) txt.length()) {
      offset = 0;
    } else {
      offset++;
    }
    if (offset == 0) {
      str = txt;
    } else {
      str = txt.substring(offset) + txt.substring(0, offset - 1);
    }
    ofg.setFont(f);
    ofg.setColor(color);
    ofg.drawImage(img, 0, 0, this);
    ofg.drawString(str, 50, 60);
    ofg.drawImage(offscreenimage, 0, 0, this);
    ofg.clearRect(0, 0, size().width, size().height());
  }

  public void update(Graphics g) {
    paint(g);
  }

  public void run() {
    while (true) {
      repaint();
      try {
        mythread.sleep(pause);
      } catch (InterruptedException e) {
        System.out.println(e);
      }
    }
  }
}
```

221. 编写一个程序输入年龄并使用断言打印消息。

```java
import java.util.Scanner;

class Assertion {
  public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);
    System.out.print("Enter age: ");
    int value = scanner.nextInt();
    assert value >= 18 : "error";
    System.out.println("value is ok");
  }
}
```

222. 编写一个程序从列表中选择项目并生成账单。

```java
import java.applet.Applet;
import java.awt.*;
import java.awt.event.*;

/* <applet code="selecteditem" height="500" width="500"></applet> */

class selecteditem extends Applet implements ItemListener, ActionListener {
  TextField t, t1;
  List l1;
  Button b;
  String p, q, r;
  int c, d;
  Label l1, l2;

  public void init() {
    l1 = new Label("Guest");
    l2 = new Label("Bill number");
    t = new TextField(10);
    t1 = new TextField(10);
    add(l1);
    add(t);
    add(l2);
    add(t1);
    l1 = new List(2, true);
    l1.add("pizza");
    l1.add("burger");
    l1.add("long");
    l1.add("donuts");
    add(l1);
    b = new Button("order");
    add(b);
    b.addActionListener(this);
    l1.addItemListener(this);
  }

  public void itemChanged(ItemEvent e) {
    repaint();
  }

  public void actionPerformed(ActionEvent ae) {
    r = t1.getText();
    q = t.getText();
    p = ae.getActionCommand();
    if (p.equals("order")) {
      c = 1;
      repaint();
    }
  }

  public void paint(Graphics g) {
    if (c == 1) {
      g.drawString("Guest is " + q, 150, 430);
      g.drawString("Bill no. is " + r, 150, 440);
      g.drawString("your final bill is " + d, 150, 450);
      g.drawString("Have a nice day!", 150, 460);
    }
    int i = 0;
    String val[];
    String data = "You have selected items:";
    val = l1.getSelectedItems();
    int len = val.length;
    while (len != i) {
      data = data + val[i] + "";
      String s = "your expected bill is Rupees";
      int j = 0;
      if (i == 0)
        j = 10;
      g.drawString(s + j, 150, 170);
      d = j;
      if (i == 1) {
        j = 20;
        g.drawString(s + j, 150, 180);
        d = j;
      }
      if (i == 2) {
        j = 30;
        g.drawString(s + j, 150, 190);
        d = j;
      }
      if (i == 3) {
        j = 40;
        g.drawString(s + j, 150, 200);
        d = j;
      }
      if (i == 4) {
        j = 50;
        g.drawString(s + j, 150, 210);
        d = j;
      }
      i++;
    }
    g.drawString(data, 150, 160);
  }
}
```

223. 使用 `util.Calendar` 编写一个程序创建一个数字钟。

```java
import java.awt.*;
import java.awt.event.*;
import java.applet.Applet;

/*<applet code="tim" Height=700 Width=500></applet>*/

public class tim extends Applet implements Runnable {
  TextField t0, t1, t2;
  Thread t;
  int hrs, min, sec;
  Label l11, l12, l13;
  String s;

  public void init() {
    t = new Thread(this);
    hrs = 0;
    min = 0;
    sec = 0;
    t0 = new TextField(2);
    t1 = new TextField(2);
    t2 = new TextField(2);
    t0.setEditable(false);
    t1.setEditable(false);
    t2.setEditable(false);
    l11 = new Label("hrs");
    l12 = new Label("min");
    l13 = new Label("sec");
    add(l11);
    add(t0);
    add(l12);
    add(t1);
    add(l13);
    add(t2);
    t0.setText("+hrs");
    t1.setText("+min");
    t2.setText("+sec");
  }

  public void run() {
    while (true) {
      try {
        if (sec >= 60) {
          min++;
          t1.setText("+min");
          sec = 0;
          if (min >= 60) {
            hrs++;
            t0.setText("+hrs");
            min = 0;
            if (hrs >= 24) {
              hrs = 0;
            }
          }
        } else {
          sec++;
```



`Thread.sleep(1000);`

`t2.setText("+sec");`

```java
} catch (Exception e) {
}
```

```java
public void start() {
    t.start();
}
```

## `hitserv.java`

```java
import java.io.IOException;
import java.io.PrintWriter;
import javax.servlet.RequestDispatcher;
import javax.servlet.ServletExceptionException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

public class hitserv extends HttpServlet {
    int hits;
    public void init() {
        hits=0;
    }
    public void doGet(HttpServletRequest req,HttpServletResponse res)
    throws IOException, ServletException {
        res.setContentType("text/html");
        PrintWriter pw=res.getWriter();
        RequestDispatcher rd=req.getRequestDispatcher("hithtml.html");
        hits++;
        pw.println("You hit me " + hits + " times ");
        rd.include(req, res);
    }
}
```

## 224. 写一个程序显示 `String` 和 `StringBuilder` 类的区别？

```java
public class strng {
    public static void main(String [] ar) {
        String n=new String("Swati");
        System.out.println(n.hashCode());
        n="Computers";
        System.out.println(n.hashCode());
        n="cloud";
        System.out.println(n.hashCode());
        StringBuilder sb=new StringBuilder("Swati");
        System.out.println(sb.hashCode());
        sb.append("Computers");
        System.out.println(sb);
        System.out.println(sb.hashCode());
    }
}
```

## 225. 写一个 Java 程序，使用 `try-with-resources` 读取一个现有文件。

```java
import java.io.*;

public class static try_resource {
    public static void main(String[] args) {
        try (BufferedReader br = new BufferedReader(new FileReader("C:\\testing.txt"))) {
            String line;
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## 226. 写一个程序显示 `equals()` 和 `==` 区别。

```java
public class strng {
    public static void main(String [] ar) {
        String str1= new String("ABCD");
        String str2= new String("ABCD");
        if(str1 == str2) {
            System.out.println("String 1 == String 2 is true");
        } else {
            System.out.println("String 1 == String 2 is false");
        }
        String Str3 = str2;
        if(str2 == Str3) {
            System.out.println("String 2 == String 3 is true");
        } else {
            System.out.println("String 2 == String 3 is false");
        }
        if(str1.equals(str2)) {
            System.out.println("String 1 equals string 2 is true");
        } else {
            System.out.println("String 1 equals string 2 is false");
        }
    }
}
```



## 基于实践与理论的面试面试题：

- 1. 解释 `public static void main(String[] arg)`。
答案：

`public` 是一个访问修饰符，用于指定谁可以访问此方法。`public` 意味着该方法可以被任何类访问。

`static` 是 Java 中的一个关键字，标识它是基于类的，即可以在不创建类实例的情况下访问它。

`void` 是方法的返回类型。`void` 定义了不返回任何值的方法。

`main` 是方法的名称，JVM 会搜索具有特定签名的方法作为应用程序的起点。它是发生主执行逻辑的方法。

`String args[]` 是传递给 `main` 方法的参数。

- 2. `public static void main(String[] arg)` 可以重载吗？
答案：

可以。但 JVM 搜索的是 `main(String[] arg)`。

- 3. 为什么 Java 不是 100% 面向对象的？
答案：

Java 不是 100% 面向对象的，因为它使用了八种基本数据类型，例如 `boolean`、`byte`、`char`、`int`、`float`、`double`、`long`、`short`，这些都不是对象。

- 4. 什么是单例类？我们如何让一个类变成单例？
答案：

单例类是指在任何给定时间、在一个 JVM 中只能创建一个实例的类。通过将它的构造函数设置为私有，可以将一个类变成单例。

- 5. 为什么我们不能重写静态方法？
答案：

是因为静态方法是类的一部分，它与类绑定；而实例方法与对象绑定，静态方法在类区域中获取内存，而实例方法在堆中获取内存。

- 6. 你可以将 `main` 方法声明为 `final` 吗？
答案：

可以，例如：`public static final void main(String[] args){}`

- 7. 哪个类是所有类的父类？
答案：

`Object` 类

- 8. Java 中的 `this` 是什么？
答案：

`this` 是一个引用当前对象的引用变量。

- 9. 什么是静态变量？
答案：

静态变量用于引用所有对象的共同属性（即该属性对每个对象不是唯一的）。静态变量只在类区域分配一次内存。

## 基于实践与理论的面试面试题：

- 10. 哪个类是所有类的父类？
答案：

`Object` 类

- 11. 我们可以重写静态方法吗？
答案：

不可以，因为它们是类的一部分。

- 12. 定义 `Path` 和 `ClassPath`。
答案：

`Path` 指定文件的位置，而 `ClassPath` 用于指定类的位置。

- 13. 抽象类和接口的区别是什么？
答案：

- 1) 抽象类可以包含抽象方法和非抽象方法。接口只能包含抽象方法。
- 2) 抽象类可以包含静态方法，但接口不能。
- 3) 抽象类可以有构造函数，但接口不能。

- 14. 为什么 Java 中的 `String` 是不可变的？
答案：

在 Java 中，一旦值赋值给字符串，就无法更改；如果更改，会创建新对象。

- 15. Java 如何进行垃圾回收？
答案：

在 Java 中，当对象不再被引用时，会发生垃圾回收并销毁对象。Java 调用 `System.gc()` 或 `Runtime()` 方法。

- 16. 什么是 Servlet？
答案：

Java Servlet 是一种服务端技术，通过提供动态响应和数据持久化来扩展 Web 服务器的功能。`javax.servlet` 和 `javax.servlet.http` 包提供了编写 servlet 的接口和类。

所有 servlet 必须实现 `javax.servlet.Servlet` 接口，该接口定义了 servlet 的生命周期。

在实现通用服务时，我们可以扩展提供的 `GenericServlet` 类。`HttpServlet` 类提供了方法 `doGet()` 和 `doPost()`，用于处理特定的 HTTP 服务。大多数情况下，Web 应用通过 HTTP 协议访问，因此我们扩展 `HttpServlet` 类。

- 17. 什么是 `RequestDispatcher`？
答案：

`Dispatcher` 接口用于将请求转发到其他资源，可以是 HTML、JSP 或 servlet。我们也可以使用它将其他的内容包含在响应中。该接口定义了两个方法：

- `forward()`
- `include()`

## 基于实践与理论的面试面试题：

- 18. Java 连接数据库的步骤有哪些？
答案：

- 注册驱动类
- 创建连接
- 创建语句
- 执行查询
- 关闭连接

- 19. 可以有没有 `catch` 块的 `try` 吗？
答案：

可以，可以使用 `try-finally` 语句并避免 `catch` 块。

- 20. Java 编译器存储在 JDK、JRE 还是 JVM 中？
答案：

Java 编译器的任务是将 Java 程序转换为字节码，我们有 `javac` 可执行文件。因此，它必须存储在 JDK 中。

- 21. Java 中 `throw` 和 `throws` 有什么区别？
答案：

`throws` 子句用于声明异常，这意味着它的工作类似于 `try-catch` 块。相反，`throw` 关键字用于显式抛出异常。

- 22. 哪些类型的异常在编译时被捕获？
答案：

检查异常（Checked exceptions）可以在程序编译时被捕获。检查异常必须通过代码中使用 `try catch` 块或 `throws` 子句来处理，才能成功编译代码。

- 23. 在线程编程中，所有线程必须实现哪种方法？
答案：

`run()` 是 `Runnable` 接口或 `Thread` 类的方法，所有线程都必须实现它。

- 24. 所有异常类的基类是什么？
答案：

在 Java 中，`java.lang.Throwable` 是所有异常类的父类。

- 25. `GenericServlet` 和 `HttpServlet` 之间有什么区别？
答案：

`GenericServlet` 是 `Servlet` 接口的协议无关实现，而 `HttpServlet` 是特定于 HTTP 协议的实现。`HttpServlet` 继承了 `GenericServlet` 并提供了其他特定 HTTP 协议的方法。

- 26. 什么是部署描述符（deployment descriptor）？
答案：

部署描述符是 Web 应用的配置文件，其名为 `web.xml`，位于 `WEB-INF` 目录下。

Servlet 容器使用此文件来配置 Web 应用 Servlet、Servlet 配置参数（config params）、上下文初始化参数（init params）、过滤器（filters）、监听器（listeners）、欢迎页（welcome pages）以及错误处理器（error handlers）。

- 27. Servlet 会话管理有哪些不同的方法？
答案：

Servlet 中常见的会话管理方式包括：
- 用户身份认证（User Authentication）
- HTML 隐藏字段（HTML Hidden Field）
- Cookies
- URL 重写（URL Rewriting）
- 会话管理 API（Session Management API）

## 28. Servlet 的生命周期是什么？
答案：

以下是 Servlet 生命周期的阶段：
1) 加载 Servlet 类：Servlet 容器找到 `web.xml` 文件中提到的 Servlet 类并加载它。
2) Servlet 实例化：在此阶段会创建 Servlet 类的对象。
3) 初始化（Initialization）：通过调用 `init()` 方法进行 Servlet 初始化。
4) 服务请求：在 Servlet 服务的阶段，通过调用 `service()` 方法处理客户端请求。
5) 销毁（Destroy）：Servlet 生命周期的最后一个阶段。`destroy()` 方法释放 Servlet 实例以便可以进行垃圾回收。

## 29. 为什么 Servlet 比 CGI 更好？
答案：

Servlet 响应比 CGI 快，因为它使用了多线程概念来处理每个请求。
CGI 的性能没有那么好，因为它为每个请求创建一个新对象，而 Servlet 则为每个请求分配一个新线程。
与 CGI 相比，Servlet 的内存消耗更低。

## 30. 我们如何在我们的 Servlet 上创建死锁条件？
答案：

一种简单的方法是在 `doGet()` 方法内部调用 `doPost()`，在 `doPost()` 方法内部调用 `doGet()`，这将为 Servlet 创建死锁状态。

## 31. RMI 和 CORBA 之间有什么区别？
答案：

RMI 是一种分布式对象系统，它提供了能够易于开发分布式 Java 应用的能力。
使用 RMI 方法开发应用比使用 sockets 更容易。它的设计不需要任何协议，使得它执行的任务较不容易出错。
RMI 允许从本地类文件调用本地方法，并且远程方法会被解释并返回给调用者。

CORBA 同样具有与 RMI 相同的特征。它是一种与平台和语言无关的架构，可以在任何平台上运行。

它可以从网络上的任何地方定位，并可以使用任何具有与接口定义语言（IDL）映射的语言。
这些对象的规格是通过在接口语言中指定的接口来定义的。

## 32. 在 Java 中使用 `PreparedStatement` 的优点是什么？
答案：

`PreparedStatement` 用于重复执行相同的 SQL 语句。即使被使用了“n”次，预编译语句也只编译一次。

## 33. `execute`、`executeQuery` 和 `executeUpdate` 的返回类型是什么？
答案：

`execute` 的返回类型是 `Boolean`
`executeQuery` 的返回类型是 `ResultSet` 对象
`executeUpdate` 的返回类型是 `int`

## 34. 什么是 JSP？
答案：

JSP 是嵌入 Java 代码的普通 HTML 页面。为了处理 JSP 文件，开发者需要一个连接到 Web 服务器的 JSP 引擎。
JSP 页面会被编译成 Servlet，由 Servlet 引擎处理。这一阶段被称为翻译（translation）。
Servlet 引擎随后加载 Servlet 类并执行它以创建动态 HTML，然后将其发送到浏览器。
JSP 由 Sun Microsystems 开发，是 Java Servlets 的改进版本。

与大多数基于服务器的技术一样，JSP 将业务逻辑与表现层分离。

## 35. JSP 中的隐式对象（Implicit objects）？
答案：

- 1. `response`
2. `exception`
3. `application`
4. `request`
5. `session`
6. `page`
7. `out`
8. `config`
9. `pageContext`

## 36. JSP 生命周期阶段。
答案：

- 翻译：JSP 容器验证 JSP 页面代码并解析它以生成 Servlet 源码。注意，如果 JSP 页面名称为 `<Login.jsp>`，生成的 Servlet 类名将是 `Login_jsp`，文件名将是 `Login_jsp.java`。

- 编译：JSP 容器在此阶段编译 JSP 页面并创建一个类文件。

- 类加载：在此阶段，容器将 JSP 类加载到应用内存中。

- 实例化：此阶段引导容器执行生成的 JSP 类的无参数构造函数并将其加载到内存中实例化。

- 初始化：容器调用 JSP 类的 `init` 方法，并根据部署描述符指定的参数初始化 Servlet 配置。此阶段确保了 JSP 能够响应客户端请求。

- 请求处理：这是 JSP 页面创建线程来处理请求的阶段。
- 销毁：这是 JSP 生命周期的终点阶段，JSP 类会被卸载。此阶段发生在应用卸载或服务器关闭时。

## 37. JSP 生命周期方法？
答案：

JSP 容器在第一次初始化 JSP 时执行 `init()` 方法。
每当容器接收到请求时，它都会调用 `service()` 方法，处理请求并生成响应。
容器调用 `destroy()` 方法清理内存。

## 38. 脚本元素有哪些？
答案：

有三种类型的脚本语言：
- 脚本段（Scriptlets）
- 表达式（Expressions）

## 39. JSP 技术是扩展的吗？
答案：

是的。JSP 技术确实是扩展的，因为它允许为大量的用例创建自定义操作或标签。JSTL 库实现了这一点。

## 40. `<jsp:include page = ... />` 和 `<%@ include file = ... %>` 有什么区别？
答案：

两者都用于从一个页面包含另一个页的信息：

```jsp
<jsp:include page = ... />
```

这类似于页面间的函数调用。每当客户端访问该页面时都会执行。这种方法对于模块化 Web 应用很有用。

```jsp
<%@ include file = ... %>
```



包含的内容是以文本形式嵌入到包含`<@ include file="..."`的页面中的。通过这种方式，如果包含的文件发生了，更改将包含在输出中。

## 41. HTML 表单的 GET 和 POST 方法有什么区别？

答案：

- 1. 可见性：GET 请求通过 URL 字符串发送，是可见的；POST 请求则不可见，因为它封装在 HTTP 请求体中。
- 2. 长度：GET 请求有长度限制，因为它通过 URL 传输，字符长度不能超过 255；而 POST 请求没有这种限制。
- 3. 性能：由于 GET 请求在封装上没有花费时间，因此更快且更简单。此外，最大长度限制有助于优化 GET 的实现。
- 4. 数据类型：GET 请求只能携带文本数据，因为我们知道 URL 只包含文本数据；而 POST 请求可以携带文本和二进制数据。
- 5. 缓存/书签：正如我们所知，现在 GET 请求本质就是 URL，因此它可以被缓存和书签。POST 请求不提供此类选项。
- 6. FORM 默认值：GET 是 HTML FORM 元素的默认方法。要使用 POST 方法提交 FORM，我们需要指定`method`属性并将其赋值为‘POST’。
- 7. 数据集（Data Set）：GET 请求被限制仅使用 ASCII 字符，这种限制在 POST 请求中是不存在的。

## 42. 继承 Thread 类和实现 Runnable 接口，哪种更好？

答案：

实现`Runnable`接口更有优势，因为当你需要进行多重继承时，只有接口可以提供帮助。

如果你已经继承了另一个类，那么必须使用`Runnable`接口。否则，你可以扩展`Thread`类。

如果我们实现`Runnable`接口，它将提供更好的面向对象设计。

实现同时也提供了一致性。

## 43. Java 数组与 ArrayList 之间的区别是什么？

答案：

`ArrayList`是一种动态数组，可以根据需要增长，而 Java 数组是固定长度的。

## 44. 什么是守护线程（daemon threads）？

答案：

守护线程设计用于在后台运行。这种线程的一个例子是垃圾回收线程。

## 45. 什么是瞬态变量（transient variable）？

答案：

`trans`变量变量可能不会被序列化的变量。

## 46. 什么是序列化（Serialization）？

答案：

Java 中的序列化是将对象转换为字节流以将其保存到文件的过程。或者说，序列化被用于持久化（保存）对象的状态。

序列化的反过程称为反序列化（deserialization）。

## 47. TCP 和 UDP 之间的区别是什么？

答案：

这两个协议在执行通信动作的方式上不同。

TCP 协议在一对计算机之间建立双向连接，而 UDP 协议是单向消息发送者。

TCP 是可靠的协议，而 UDP 是不可靠的。

## 48. 两个重要的 TCP Socket 类是什么？

答案：

`Socket`和`ServerSocket`。

`ServerSocket`用于正常的双向 socket 通信。

`Socket`类允许我们通过套接字读取和写入。

`getInputStream()`和`getOutputStream()`是`Socket`类中提供的两个方法。

## 49. Java Sockets 的优势是什么？

答案：

Sockets 是灵活且充分的。

对于通用通信，可以轻松实现高效基于 socket 的编程。它导致了低网络流量。

## 50. 什么是 inetAddress 类？

答案：

Java 的`InetAddress`类表示 IP 地址。`java.net.InetAddress`类提供了方法来获取任何主机名的 IP，例如`www.google.com`、`www.facebook.com`、`com`等。

## 51. 什么是多重继承？Java 支持吗？

答案：

如果一个子类继承了多个类的属性，就被称为多重继承。Java 不允许扩展多个类。多重继承的问题在于，如果多个父类具有相同名称的方法，那么在运行时，编译器很难决定从子类中执行哪个方法。为了解决这个问题，Java 允许实现多个接口。这个问题通常被称为菱形问题（Diamond Problem）。

## 52. 什么是类变量（class variable）和实例变量（instance variable）？

答案：

类变量：属于整个类；每个变量都只有一个副本。实例变量或属性 - 属于单个对象的数据；每个对象都有每个变量的自己的副本。

## 53. 重载方法（overload method）的方法有哪些？

答案：

可以通过以下方式重载重载：

- 改变参数的数量
- 为参数使用不同的数据类型
- 使用不同的参数顺序

## 54. 定义构造函数（constructor）。

答案：

构造函数是一种用于初始化对象状态的方法，它在对象创建时被调用。构造函数的规则如下：

- 构造函数名应与类名相同。
- 构造函数必须没有返回类型。
- 构造函数可以重载。
- 不需要显式地调用它。

## 55. finalize 方法的作用是什么？

答案：

`finalize`方法有助于对当前未使用的资源执行清理操作。

`finalize`方法是受保护的（protected），仅可以通过该类或其派生类访问。

## 56. 什么是 super 关键字？

答案：

`super`关键字用于调用重写的方法，该方法覆盖了其父类的一个一个方法。

`super`关键字允许访问被重写的方法，还可以访问父类的隐藏成员。

它还用于调用父类（基类）的构造函数。

## 57. 什么是指针（pointer）？Java 支持指针吗？

答案：

指针是指向内存位置的引用句柄。指针的不当处理会导致内存泄漏和可靠性问题，因此 Java 不支持指针的使用。

## 58. 源文件可以包含多个一个类声明吗？

答案：

是的，单个源文件可以包含任意数量的类声明，但只能有一个类被声明为`public`。

## 59. 如果声明类时没有带任何访问修饰符，该类可以在哪里被访问？

答案：

没有任何访问修饰符的类被称为具有包访问权限（package access）。这意味着该类只能被定义在相同包内的类和接口访问。

## 60. 如何让一个字段不被序列化？

答案：

有三种异常情况序列化不一定读取和写入流。这些情况如下：

- 1. 序列化忽略静态字段（static fields），因为它们不是任何特定状态的一部分。
- 2. 只有当基类本身可序列化时，才会处理基类字段。
- 3. 瞬态字段（transient fields）。

## 61. 为什么我们需要包装类（wrapper classes）？

答案：

有时处理基本类型更为方便。此外，包装类提供了许多实用方法。

## 62. 错误（error）和异常（exception）之间的区别是什么？

答案：

错误是运行时发生的不可恢复条件。例如`OutOfMemoryError`。

异常是由于输入错误而发生的条件，可以通过`try-catch`处理。

## 63. 什么是同步（synchronization）？它为什么重要？

答案：

对于多线程来说，同步是控制多个线程访问共享资源的能力。

如果没有同步，可能会出现一个线程在另一个线程使用共享对象时修改该对象的情况。

## 64. Java 中 sleep 和 wait 的区别是什么？

答案：

它们都用于暂停当前运行的线程，然而，`sleep()`用于短暂暂停，因为它不释放锁；而`wait()`用于条件等待。

## 65. 解释 JRE、JDK、JVM 和 JIT 区别。

答案：

JRE 是 Java 运行环境（Java Runtime Environment）的缩写，由 JVM 在运行时所需的一组文件组成。

JVM 是 Java 虚拟机（Java Virtual Machine）的缩写，为收集到的字节码提供运行环境。JVM 控制字节码到机器码的转换。

JDK 是 Java 开发工具包（Java Development Kit）的缩写，包含了用于开发的 JRE 工具。编写和执行 Java 代码需要 JDK。

JIT 是即时编译（Just in Time compilation）的缩写，它通过在超过阈值时将 Java 字节码转换为原生代码来提高 Java 程序的性能。

## 66. final、finalize 和 finally 的区别是什么？

答案：

final 是一个应用于变量、方法和类的修饰符。如果你创建一个 final 变量，这意味着它的值一旦初始化后就无法更改。

finalize 是一个方法，在对象被垃圾回收之前调用，赋予它最后保存自己的机会，但对 finalize 的调用是不确定的。

finally 是一个关键字，与`try`和`catch`一起用于异常处理。无论 try 块是否抛出异常，finally 块都会被执行。

## 67. Applet 类的直接父类是什么？

答案：`Panel`。

## 68. wait()、notify() 和 notifyAll() 方法是什么？

答案：

`wait()`、`notify()`和`notifyAll()`方法用于为线程等待共享资源提供一种高效的方式。当线程执行对象的`wait()`方法时，它会进入等待状态。只有当另一个线程调用对象的`notify()`或`notifyAll()`方法后，它才会进入就绪状态。

# 基于实践与理论的面试题：357

## 69. `paint()` 方法和 `repaint()` 方法之间的区别是什么？

答案：

`paint()`方法支持通过`Graphics`对象进行绘制。`repaint()`方法用于让 AWT 绘制线程调用`paint()`方法。

## 70. 线程进入等待状态（waiting state）的三种方式是什么？

答案：

线程可以通过调用其`sleep()`方法、在 I/O 上阻塞、尝试获取对象锁失败或调用对象的`wait()`方法来进入等待状态。它还可以通过调用其（已弃用的）`suspend()`方法进入等待状态。

## 71. Swing 和 AWT 之间有什么区别？

答案：

AWT 组件被认为是重量级的（heavyweight），而 Swing 组件被认为是轻量的（lightweights）。Swing GUI 具有可插的外观（pluggable look and feel）。AWT 是依赖于平台的，也就是说同一个 GUI 在不同平台上看起来会有不同，因为它们使用原生组件，例如，如果选择原生组件，`Frame`在 Windows 和 Linux 上的外观就会不同。相反，Swing 组件是用 Java 开发的，且不依赖平台。它还提供了跨平台的一致 GUI，例如，如果你在 Linux 或 Windows 上运行用 Java 创建的 NetBeans，你会看到 GUI 的的一一致性。

## 72. Scrollbar（滚动条）和 ScrollPane（滚动面板）之间的区别是什么？

答案：

`Scrollbar`是一个组件（Component），但不是容器（Container）。`ScrollPane`是一个容器。`ScrollPane`处理自己的事件并执行自己的滚动。

## 73. Java Sockets 的缺点

答案：

- 1. 基于 Socket 的通信允许在应用程序之间发送原始数据包。
- 2. 客户端和服务器都必须提供机制来使数据具有任何用途。

## 74. 为什么 Java 不是纯面向对象的语言？

答案：

纯面向对象的语言是完全面向对象的语言，它们支持或具有将程序内部所有内容视为对象的特性。

它不支持基本数据类型（如`int`、`char`、`float`、`bool`等）。

Java 支持基本数据类型。

## 75. 为什么要使用包装类（wrapper class）？

答案：

包装类提供了将基本类型转换为对象以及反之的机制。

## 76. Java 的简要历史？

答案：

Java 是一种由 Sun Microsystems 开发的通用、高级级编程语言。Java 编程语言由一个被称为“绿色团队”（Green Team）的小型工程师团队开发，他们在 1991 年启动了这门语言。

Java 语言最初被称为 OAK，当时它的设计是为手持设备和顶顶盒设计的。Oak 失败了，在 1995 年，Sun 将名称更改为 Java 并修改了该语言以利用世界维网。

# 基于实践与理论的面试题：359

2009 年晚些，Oracle 公司收购了 Sun Microsystems，并获得了两个关键的 Sun 软件资产的所有权：Java 和 Solaris。

## 77. 什么是 JVM？

答案：

JVM 是一个提供运行环境以驱动 Java 代码或应用程序的引擎。它将 Java 字节码转换为机器语言。JVM 是 Java 运行环境（JRE）的一部分。它的全称是 Java Virtual Machine（虚拟机）。

## 78. 什么是 classloader（类加载器）？

答案：

类加载器是一个用于加载类文件的子系统。它执行三个主要功能，即加载（Loading）、链接（Linking）、初始化（Initialization）。

## 79. 什么是 Garbage collector（垃圾回收器）？

答案：

垃圾回收（GC）是一个释放不再被任何可 Java 对象引用的占用内存的过程，它是 Java 虚拟机（JVM）动态内存管理系统的组成部分。所有 Java 对象在创建时都会自动获取内存，当对象不再需要时，Java 垃圾回收过程会回收这些内存。这意味着，垃圾回收器跟踪活跃对象以及所有被标记为垃圾的其他内容。

## 80. Java 中的 transient（瞬态）变量是什么？

答案：

`Transient`是一个用于序列化的变量修饰符。

在序列化期间，如果我们不想在文件中保存特定变量的值，则使用`transient`关键字。当 JVM 遇到`transient`关键字时，它会忽略变量的原始值。

## 81. 什么是 synchronization（同步）？

答案：

当多个线程尝试访问共享资源时，我们需要确保资源一次只有一个一个线程在使用。

实现这一过程被称为同步。

## 82. 什么是 autoboxing（自动装箱）和 unboxing（自动拆箱）？

答案：

Autoboxing 和 Unboxing 特性在 Java5 中引入。将基本数据类型自动转换为其等效的包装类型被称为装箱，相反的操作被称为拆箱。

将基本类型值（例如一个`int`）转换为相应包装类（`Integer`）的对象被称为自动装箱。

- 当基本类型满足以下条件时，Java 编译器应用自动装箱：
  - 作为参数传递给期望相应包装类对象的方法。
  - 赋值给相应包装类的变量。
- 自动装箱是将基本类型自动封装（装箱）到其等效类型包装器的过程。
- 1. 自动装箱是将基本类型自动封装（装箱）到其等效类型包装器的过程。自动拆箱（Auto-Unboxing）是从包装类中自动提取对象值的过程。

## 83. 什么是 JDBC Driver？

答案：

JDBC Driver 是一个允许 Java 应用程序与数据库交互的软件组件。有四种 JDBC 驱动程序：

- 1. JDBC-ODBC 桥
- 2. 原生 API 驱动程序（部分 Java）
- 3. 网络协议驱动程序（全 Java）
- 4. Thin 驱动程序（全 Java）

## 类型 1：JDBC-ODBC 桥

在类型 1 驱动程序中，使用桥接访问安装在每个客户端上的 ODBC 驱动程序。使用 ODBC 需要在系统中配置数据源（DSN）来代表目标数据库。当 Java 出现时，在没有替代方案的情况下非常有用。

ODBC 是访问数据库的标准应用程序接口（API）。通过程序使用 ODBC 语句，你可以访问不同的数据库，包括 Access、dBase、DB2、Excel 和文本。除了 ODBC 软件，每个要访问的数据库都需要单独的模块或驱动。ODBC 的主要支持者是微软。

## 类型 2：JDBC-Native API

在类型 2 驱动程序中，JDBC 调用转换为原生 API 调用，这些调用是数据库唯一的。驱动通常由数据库供应商提供，使用方法与 JDBC-ODBC 相同。每个客户端必须安装特定的驱动。原生 API 驱动使用数据库的客户端库。驱动将 JDBC 调用转换为数据库的原生调用。它不是完全用 Java 写的。

## 类型 3：网络协议驱动程序 / JDBC-Net 纯 Java

在类型 3 驱动程序中，使用三层方法访问数据库。JDBC 客户端使用标准网络接字与中间件应用程序服务器通信。接字信息随后由中间件应用程序服务器转换为数据库所需的调用，并转发到数据库服务器。

## 类型 4：全 Java 驱动

这是为数据库提供的性能最高的驱动程序，通常由供应商本身提供。这种驱动非常灵活，不需要在客户端或服务器上安装特殊软件。此外，这些驱动可以动态下载。

## 84. 什么是 API？

答案：

API 是 Application Programming Interface（应用程序接口）的缩写，是一种允许两个应用程序相互通信的软件中间件。

每当你使用像 Facebook 这样的应用程序、发送时消息或在手机上查看天气时，你都在使用 API。

例如：

当你在手机上使用应用程序时，应用程序连接到互联网并将数据发送到服务器。服务器随后检索这些数据、解释它们、执行必要的操作并将结果传回你的手机。应用程序随后解释这些数据，并以易读的方式向你展示你想要的信息。这就是 API——这一切都是通过 API 完成的。

# 基于实践与理论的面试题：363

## 85. 为什么将敏感数据存储在字符数组中（如密码、社会安全号等）比存储在 String 中安全？

答案：

在 Java 中，String 是不可变的，并且存储在字符串池（String pool）中。这意味着一旦一个 String 被创建，它就会一直留在内存中的字符串池中，直到被垃圾回收。

因此，即使在你完成了字符串值的处理（例如密码）之后，它在随后的不确定时间内仍然存在于内存中（再次，直到被垃圾回收），而你对此没有真正的控制力。

因此，任何可以访问内存转储（memory dump）的人都可能提取出敏感数据并利用它。相比之下，如果你使用可变对象（例如字符数组）来存储值，在完成后你可以将其置为空，并确信它将不再被保留在内存中。

## 86. 查询员工第二高薪水的 SQL 查询？

```sql
```



`select MAX (Salary) from Employee WHERE Salary NOT IN (select MAX(Salary) from Employee)`

87. 编写一个 SQL 查询，查找出生日期在 1990/01/01 到 2010/12/31 之间的不同性别员工人数。

答案：

```
SELECT COUNT(*), gender from Employees WHERE DOB BETWEEN '01/01/1990' AND '31/12/2010' GROUP BY gender;
```

88. 编写一个 SQL 查询来查找数据库中的重复行？

答案：

```
SELECT * FROM emp a WHERE rowid = (SELECT MAX(rowid) FROM EMP b WHERE a.empno=b.empno)
```

89. 解释 `Calendar` 类的一些方法？

答案：

```
Calendar calendar = Calendar.getInstance();

System.out.println(calendar.get(Calendar.YEAR));

System.out.println(calendar.get(Calendar.MONTH));

System.out.println(calendar.get(Calendar.DATE));

System.out.println(calendar.get(Calendar.WEEK_OF_MONTH));

System.out.println(calendar.get(Calendar.WEEK_OF_YEAR));

System.out.println(calendar.get(Calendar.DAY_OF_YEAR));

System.out.println(calendar.getFirstDayOfWeek()); //1 -> Calendar.SUNDAY
```

90. 作为外部类成员的内部类可以使用哪些修饰符？

答案：

内部类可以声明为 `public`, `protected`, `private`, `static`, `final` 或 `abstract`。

91. JSP 请求是如何处理的？

答案：

当 JSP 请求到达时，浏览器首先请求一个带有 `.jsp` 扩展名的页面。然后，Web 服务器读取该请求并使用 JSP 编译器将 JSP 页面转换为 servlet 类。
请注意，JSP 文件仅在页面的第一次请求时，或者当 JSP 文件发生变化时才会被编译。生成的 servlet 类会被调用以处理浏览器的请求。
一旦请求执行结束，servlet 就会向客户端发送响应。

92. 什么是 JSP actions（动作标签）？

答案：

JSP actions 使用 XML 语法的结构来控制 servlet 引擎的行为。JSP actions 在请求 JSP 页面时执行。

它们可以动态地插入到文件中、重用 JavaBeans 组件、将用户重定向到其他页面或为 Java 插件生成 HTML。下面列出部分可用的 actions：

- `jsp:include` – 在请求 JSP 页面时包含一个文件。
- `jsp:useBean` – 查找或实例化一个 JavaBean。
- `jsp:setProperty` – 设置 JavaBean 的属性。
- `jsp:getProperty` – 获取 JavaBean 的属性。
- `jsp:forward` – 将请求者重定向到新页面。
- `jsp:plugin` – 生成特定浏览器的代码。

93. 解释创建线程的不同方式。你更倾向于哪种？为什么？

答案：

- 有三种方法可以用于创建线程：
- 一个类可以继承 `Thread` 类。
- 一个类可以实现 `Runnable` 接口。
- 应用程序可以使用 `Executor` 框架（执行器框架）来创建线程池。

更倾向于使用 `Runnable` 接口，因为它不需要对象继承 `Thread` 类。
如果你的应用程序设计需要多重继承，只有接口可以提供帮助。此外，线程池非常高效，并且可以很容易地实现和使用。

94. 什么是 applet security manager（applet 安全管理器），它提供了什么？

答案：

applet 安全管理器是一种对 Java applet 施加限制的机制。浏览器只能有一个安全管理器。
安全管理器在启动时建立，此后无法被替换、重载、覆盖或扩展。

95. Java 中 `Exception`（异常）和 `Error`（错误）有什么区别？

答案：

`Exception` 和 `Error` 类都是 `Throwable` 类的子类。
`Exception` 类用于用户程序应该捕获的异常情况。
`Error` 类定义了用户程序无法捕获的异常。

96. 解释可用的线程状态？

答案：

- 在执行期间，线程可以处于以下状态之一：
- Runnable（可运行）：线程已准备好运行，但不一定立即开始运行。
- Running（运行中）：处理器正在积极执行该线程。
- Waiting（等待中）：线程正在等待另一个线程执行某操作。
- Timed Waiting（超时等待）：线程正在等待指定的时间段。
- Terminated（已终止）：线程已完成执行。

97. 如何确保 N 个线程可以访问资源而不产生死锁？

答案：

使用 N 个线程避免死锁的一种非常简单的方法是对锁进行排序。因此，如果所有线程遵循相同的顺序，就不会产生死锁。

98. 下述程序的输出是什么？

```java
public class Maths {

    public static void main(String[] args) {

        int x = 10;

        System.out.println(x);

    }

}
```

**答案:** 10

99. 编写一个程序解释行具有不同列数的数组？

答案：

```java
public class Arrays {

    public static void main(String[] args) {

        int [][]a = {{1,2,3},{1,2,3,4}};

        for (int i = 0; i < a.length; i++) {

            System.out.print("Row" + (i + 1) + "\t=\t");

            for (int j = 0; j < a[i].length; j++) {

                System.out.print(a[i][j]);

            }

            System.out.println("\n");

        }

    }

}
```

100. 编写一个程序查找字符串中重复的（第一个）值？

答案：

```java
import java.util.*;

public class Duplicate {

    public static void main(String[] args) {

        String [] sValue = {"abc","bcd","asd","dca","bcd"};

        System.out.println("Normal\n" + FindDupValue(sValue));

        System.out.println("Using Builtin Class \n" + FindDupValueUsingSet(sValue));

    }

    private static String FindDupValue(String[] sValueTemp) {

        for (int i = 0; i < sValueTemp.length; i++) {

            String sValueToCheck = sValueTemp[i];

            if (sValueToCheck == null || sValueToCheck.equals("")) continue;

            for (int j = i + 1; j < sValueTemp.length; j++) {

                String sValueToCompare = sValueTemp[j];

                if (sValueToCheck.equals(sValueToCompare)) {

                    return sValueToCompare;

                }

            }

        }

        return "";

    }

    private static String FindDupValueUsingSet(String[] sValueTemp) {

        Set sValueSet = new HashSet();

        for (String tempValueSet : sValueTemp) {

            if (sValueSet.contains(tempValueSet)) {

                return tempValueSet;

            }

            if (!tempValueSet.equals(""))

                sValueSet.add(tempValueSet);

        }

        return "";

    }

}
```

101. 在哪里写 `return` 语句？

答案：

- i) 仅在 `try` 块中返回：
如果在 `try` 块中返回了一个值，且在方法末尾没有返回值，会导致编译时异常。

错误: This method must return a result of type int.

```java
public class TryCatchReturn {

    int fun() { // Error:This method must return a result of type int

        try {

            return 1;

        } catch (Exception e) {

            System.out.println("End of the method");

        }

    }

    public static void main(String[] args) {

        TryCatchReturn obj = new TryCatchReturn();

    }

}
```

ii) 如果方法返回了任何值，可以在 `try` 块中的 `return` 语句之后编写“return”语句，如果你写了任何代码，它将是不可达代码，编译器将引发错误。

```java
public class TryCatchReturn{

    int fun() {

        try {

            return 1;

        } catch (Exception e) {

        }

        return 10;

        System.out.println("End of the method"); // Error : Unreachable code

    }

    public static void main(String[] args) {

        TryCatchReturn obj = new TryCatchReturn();

    }

}
```

正确：
iii) `try` 块中的 `return` 语句和方法的结束

102. 写一个程序使用 Java 代码打印杨斯卡三角形（Pascals Triangle）？

答案：

```java
public class Pascals {

    public static void main(String [] ar)

    {

        Scanner in = new Scanner(System.in);

        System.out.println("Enter number of rows");

        int rows = in.nextInt();

        for(int i =0;i<rows;i++) {

            int number = 1;

            System.out.format("%"+(rows-i)*2+"s","s");

            for(int j=0;j<=i;j++) {

                System.out.format("%4d",number);

                number = number * (i - j) / (j + 1);

            }

            System.out.println();

        }

    }

}
```

103. 写一个程序在不使用分号的情况下打印分号？

答案：

```java
public class SemiColon{

    public static void main(String [] ar)

    {

        if(System.out.printf("%C",59) != null){}

    }

}
```

104. 打印数组的五种不同方法是什么？

答案：

```java
public class Arys {

    public static void main(String [] ar) {

    int[] array = {12,13,8,34,2,7,9,43,54,21};

        //1.

        for (int i = 0; i < array.length; i++) {

            System.out.println(array[i]);

        }

        //2.

        String[] array1 = {"Java", "At", "SwatiComputers"};

        for(String st:array1)

            System.out.println(st);

        //3.

        System.out.println(Arrays.toString(array1));

        int[][] array2 = new int[][]{

            {1,2,3},

            {11,12,13},

            {4,5,6},

        };

        //4.

        System.out.println(Arrays.deepToString(array2));

        String[] strarray={"hi","array","print"};

        //5.

        System.out.println(Arrays.asList(strarray));

    }

}
```

105. 写一个程序使用 Java 代码打开记事本（Notepad）？

答案：

```java
public class Notep {

    public static void main(String [] ar) {

        Runtime rt = Runtime.getRuntime();

        try {

            rt.exec("notepad");

        } catch (Exception ex) {

            System.out.println(ex);

        }

    }

}
```

# Java 新更新

1. 解释 Java 8 中的 stream API ？

Stream 是来自集合或数组的元素序列，支持各种方法，这些方法可以通过流水线组合来产生所需的结果。

例如，你在 YouTube 上看在线视频。当我们开始看视频时，文件的一小部分首先加载到计算机中开始播放。我们不需要在开始播放之前下载整个视频。这被称为流（streaming）。

我们可以将视频文件的这些小部分视为流，将整个视频视为一个集合（Collection）。

在 Java 8 中，stream API 用于处理对象集合。

创建流的示例：

```java
import java.util.*;

import java.util.stream.Collectors;

import java.util.stream.Stream;

class strm

{

    public static void main(String [] er)

    {

        Stream<Integer> stream = Stream.of(1,2,3,4,5,6,7,8,9);

        stream.forEach(p -> System.out.println(p));

        // // 从数组创建流

        Stream<Integer> stream1 = Stream.of(new Integer[][]{1, 2, 3, 4, 5, 6, 7, 8, 9});

        stream1.forEach(p -> System.out.println(p));

        // // 从列表创建流
```




# 基于实践和理论的面试题：375

```java
List<Integer> list = new ArrayList<Integer>();

for (int i = 1; i < 10; i++) {
    list.add(i);
}

Stream<Integer> stream2 = list.stream();

stream2.forEach(p -> System.out.println(p));
```

## Java 8 和 9 之间的区别是什么？

- Java 8 及早期版本使用“package”（包）来存储相关类，而 Java 9 引入了另一个新组件：“module”（模块），它可以用于将一组相关的包放入一个组中，还有另一个新组件：`module-info.java`。
- Java 9 包含了新特性：`HttpClient`、Java 平台系统（JPMS）、多版本 `jar` 包、栈行走（Stack Walking）、接口中的私有方法、Process API 更新、Collection API 更新、Stream API 改进。

## 结合示例解释 Java 9 中的 `takeWhile`？

该方法在从给定流取了匹配给定谓词（predicate）的最长前缀元素后，返回剩余元素的流。

```java
import java.util.*;
import java.util.stream.Collectors;
import java.util.stream.Stream;
```

```java
class swtch {
    public static void main(String[] er) {
        // 创建一个名称流
        Stream<String> stream = Stream.of("john", "jose", "adam", "scott");

        // 应用 takeWhile 以获取所有通过谓词的名字
        List<String> list = stream
                .takeWhile(name -> name.charAt(0) == 'j')
                .collect(Collectors.toList());

        // 打印列表
        System.out.println(list);
    }
}
```

```bash
G:\ Update>java swtch

john, jose
```

## 4. 打印数组的五种不同方法是什么？

（见上文翻译，此处已在代码块中体现）

# 10. 使用 `repeat()` 方法编写一个程序打印以下模式？

```text
*
* * *
* * * *
* * * * * *
```

```java
import java.util.*;
import java.util.stream.*;

public class First {
    public static void main(String[] as) {
        int i;
        String s = "\\*";

        for (i = 1; i <= 5; i++) {
            System.out.println(s.repeat(i));
        }
    }
}
```

# 11. 使用 lambda 函数编写一个程序乘以两个数字？

答案：

```java
import java.util.*;
import java.util.stream.*;

interface maths {
    int multiply(int x, int y);
}

public class First {
    public static void main(String[] as) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter two numbers");

        int a = sc.nextInt();
        int b = sc.nextInt();

        maths multi = (x, y) -> (x * y);

        System.out.println(
                "Multiplication of " + a + " and " + b + " is " + multi.multiply(a, b)
        );
    }
}
```

```text
G:\java Update>javac First.java

G:\java Update>java First

Enter two numbers

5

6

Multiplication of 5 and 6 is 30
```

## 12. 解释 JEP 321：HTTP Client？

新的 API 同时支持 HTTP/1.1 和 HTTP/2。它旨在提高客户端发送请求和从服务器接收响应的整体性能。

## 13. 解释嵌套访问控制（Nested Based access control）？

“嵌套（nest）”定义了一个新的访问控制上下文，允许逻辑上属于同一代码实体的但编译为不同类文件的类访问彼此的私有成员，而无需编译器插入扩展访问权限的桥接方法。

然而，Java 11 引入了嵌套访问控制上下文，它为外部类和嵌套类之间的私有访问提供了支持。

```java
public class Second {
    public void myPublic() {
    }

    private void myPrivate() {
    }

    class Nested {
        public void nestedPublic() {
            myPrivate();
        }
    }

    public static void main(String[] ssd) {
        Second.Nested n = new Second().new Nested();
        n.nestedPublic();
    }
}
```

## 14. 解释 Java Flight Recorder？

答案：

JFR 为 Java 和 HotSpot JVM 的故障排除提供了一个低开销的数据收集框架。

JFR 是一种性能分析工具，用于从运行的 Java 应用程序收集诊断和分析数据。

Flight Recorder（飞行记录器）记录来自应用程序、JVM 和操作系统的事件。事件存储在单个文件中，该文件可以附加到错误报告中供支持工程师检查，允许对问题发生之前的期间进行事后分析。工具可以使用 API 从记录文件中提取信息。

## 15. 使用 switch-case（switch 表达式）编写一个程序检查指定的星期几是偶数还是奇数日

答案：

```java
import java.util.*;

class swtch {
    public static void main(String[] er) {
        String day;

        Scanner sc = new Scanner(System.in);

        System.out.println("Enter an alphabet");

        day = sc.next();

        String res = "";

        switch (day) {
            case "M":
            case "W":
            case "F": {
                res = "odd";
                break;
            }

            case "T":
            case "TH":
            case "S": {
                res = "even";
                break;
            }

            default:
                res = "sunday";
        }

        System.out.println(res);
    }
}
```

```text
G:\java Update>java swtch.java

Enter an alphabet

Su

sunday

G:\java Update>java swtch.java

Enter an alphabet

W

odd

G:\java Update>java swtch.java

Enter an alphabet

S

even
```

## 16. 编写一个程序解释 `indent()` 方法？

```java
import java.util.*;

class swwtch {
    public static void main(String[] er) {
        String day;

        Scanner sc = new Scanner(System.in);

        System.out.println("Enter any word");

        String day = sc.next();

        System.out.println(day);
        System.out.println(day.indent(5));
    }
}
```

```text
G:\java Update>java swwtch.java

Enter a string

computers

computers

computers
```

## 17. 用 Java 编写一个程序在不使用第三方变量的情况下交换两个字符串？

```java
import java.util.*;

class swwtch {
    public static void main(String[] er) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter two strings");

        String s1 = sc.next();
        String s2 = sc.next();

        s1 = s1 + s2;
        s2 = s1.substring(0, s1.length() - s2.length());
        s1 = s1.substring(s2.length());

        System.out.println("s1: " + s1);
        System.out.println("s2: " + s2);
    }
}
```

# 18. 解释 Java 中的 switch 表达式？

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter an alphabet of weekday");

        String day = sc.next();

        String result = switch (day) {
            case "M", "W", "F" -> "odd";
            case "T", "TH", "S" -> "even";
            default -> {
                if (day.isEmpty()) {
                    yield "Please insert a valid day.";
                } else {
                    yield "Looks like a Sunday.";
                }
            }
        };

        System.out.println(result);
    }
}
```

# 19. 什么是紧凑数字格式化（compact number formatting）？

Java 12 引入了一个方便的方法 `NumberFormat.getCompactNumberInstance(Locale, Style)` 用于创建紧凑表示。

假设我们需要解析数字 5,500,000。使用紧凑格式化，我们可以轻松读取为 5.5M。

示例：

```java
import java.util.*;
import java.text.NumberFormat;
import java.util.Locale;

public class Main {
    public static void main(String[] args) throws Exception {
        NumberFormat formatter =
                NumberFormat.getCompactNumberInstance(
                        Locale.US,
                        NumberFormat.Style.SHORT
                );

        String formattedString = formatter.format(25000L);

        System.out.println(formattedString);
    }
}
```

输出：25K

# 20. 给出一个示例，使用紧凑数字格式化设置小数部分允许的最小位数？

```java
import java.util.*;
import java.text.NumberFormat;
import java.util.Locale;

public class Main {
    public static void main(String[] args) throws Exception {
        NumberFormat fmt =
                NumberFormat.getCompactNumberInstance(
                        Locale.US,
                        NumberFormat.Style.SHORT
                );

        fmt.setMinimumFractionDigits(3);

        System.out.println(fmt.format(10000));
        System.out.println(fmt.format(10012));
        System.out.println(fmt.format(100201));
        System.out.println(fmt.format(111111));
    }
}
```

输出：

```text
10.000K
10.012K
100.201K
1.111M
```

