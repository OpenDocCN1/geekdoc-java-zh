
图 7.15 的应用使用 `int gradesArray`（在第 10 行声明并初始化）创建了一个 `GradeBook` 对象（图 7.14）。第 12–13 行将课程名称和 `gradesArray` 传递给 `GradeBook` 构造函数。第 14–15 行显示一条欢迎消息，其中包含在 `GradeBook` 对象中的类名。第 16 行调用了 `GradeBook` 对象的 `processGrades` 方法。输出总结了 `myGradeBook` 中的 10 个分数。

# 软件观察 7.2

测试用例（或测试应用程序）负责创建被测试类的对象并用数据对其进行验证。数据可以来自多个源中的任何一个。测试数据可以使用数组初始化器直接放入数组中，也可以来自用户键盘、文件（如你将在第 15 章中看到的）、数据库（如你将在第 24 章中看到的）或网络（如你将在在线第 28 章中看到的）。在将这些数据传递给类的构造函数以实例化对象后，测试用例将调用该对象来测试其方法并操作其数据。在测试用例中收集数据允许该类更具重用性，能够处理来自多个源的数据。

![](img/6851b408bcf88c7702f7d951642252f8_313_0.png)

```java
// Fig. 7.15: GradeTest.java
// GradeTest 使用分数数组创建一个 GradeBook 对象，
// 然后调用 processGrades 方法对它们进行分析。
public class GradeTest
{
    // main 方法开始程序执行
    public static void main(String[] args)
    {
        // 学生分数的数组
        int[] gradesArray = { 87, 68, 94, 100, 83, 78, 85, 91, 76, 87 };

        GradeBook myGradeBook = new GradeBook(
            "CS101 Introduction to Java Programming", gradesArray);
        System.out.printf("Welcome to the grade book for%n%s%n%n",
            myGradeBook.getCourseName());
        myGradeBook.processGrades();
    } // end main
} // end class GradeTest
```

图 15 GradeTest 使用分数数组创建一个 GradeBook 对象，然后调用 processGrades 方法对其进行分析。（第 1 部分，共 2 部分）。

# 7.10 案例研究：使用数组存储分数的 GradeBook 类

```java
// 学生分数的数组
int[] gradesArray = { 87, 68, 94, 100, 83, 78, 85, 91, 76, 87 };

GradeBook myGradeBook = new GradeBook(
    "CS101 Introduction to Java Programming", gradesArray);
System.out.printf("Welcome to the grade book for%n%s%n%n",
    myGradeBook.getCourseName());
myGradeBook.processGrades();
} // end class GradeTest
```

![](img/6851b408bcf88c7702f7d951642252f8_314_0.png)

分数分布：

00-09:

10-19:

20-29:

30-39:

40-49:

50-59:

60-69: *

70-79: ****

80-89: **

90-99: *

100: *

> 图 7.15 GradeTest 使用分数数组创建一个 GradeBook 对象，然后调用 processGrades 方法对其进行分析（第 2 部分，共 2 部分）

## Java SE 8

在第 17 章“Java SE 8 Lambda 表达式与流”中，图 17.5 的示例使用了流方法 `min`、`max` 和 `average` 来优雅且简洁地处理元素，而无需编写重复代码。在第 23 章“并发”中，图 23.29 的示例使用了流 `summaryStatistics` 来执行所有操作。

# 7.11 多维数组

多维数组通常用于表示具有行和列的表格。为了唯一标识元素，多维数组具有多个维度。多维数组实际上是数组的数组。图 7.16 展示了一个具有 $m$ 行 $n$ 列的数组。通常，具有 $m$ 行 $n$ 列的数组被称为 $m \times n$ 数组。

| | 列 1 | 列 2 | 列 3 |
| :--- | :--- | :--- | :--- |
| a[0][0] | a[0][1] | a[0][2] | a[0][3] |
| a[1][0] | a[1][1] | a[1][2] | a[1][3] |
| a[2][0] | a[2][1] | a[2][2] | a[2][3] |
| a[3][0] | a[3][1] | a[3][2] | a[3][3] |

![](img/6851b408bcf88c7702f7d951642252f8_313_0.png)

多维数组的声明和初始化与一维数组类似。多维数组的声明可以使用嵌套大括号来初始化。例如：

```java
int[][] b = {{1, 2}, {3, 4}};
```

这声明了数组 `b`，它包含两个元素数组，其中第一个嵌套初始化器 `{1, 2}` 是第一行，第二个嵌套初始化器 `{3, 4}` 是第二行。

多维数组的声明也可以通过指定行数来完成。例如：

```java
int[][] b = new int[3][2];
```

这声明了数组 `b`，它包含 3 行，每行有 2 列。

# 7.12 长度可变的多维数组

多维数组的表示方式使其非常灵活。多维数组的行长度可以不相同。例如：

```java
int[][] b = {{1, 2}, {3}, {4, 5}};
```

这创建了数组 `b`，它包含三个行：第一行有 2 个元素，第二行有 1 个元素，第三行有 2 个元素。

也可以这样初始化：

```java
int[][] b = new int[3][];
b[0] = new int[2];
b[1] = new int[1];
b[2] = new int[2];
```

这创建了数组 `b`，它包含 3 行。行 0 有 2 列，行 1 有 1 列，行 2 有 2 列。

# 第 7 章 数组与 ArrayList

```java
// 创建并输出二维数组
public static void main(String[] args) 
{
    int[][] array1 = {{1, 2, 3}, {4, 5, 6}};
    int[][] array2 = {{1, 2}, {3}, {4, 5, 6}};
}
```

array1 按行排列的值为：

1 2 3

4 5 6

array2 按行排列的值：

1 2

3

4 5 6

图 7.17 初始化二维数组。（2 部分中的第 2 部分）

第 13 行和第 16 行调用 `outputArray`（第 20–31 行）分别输出 `array1` 和 `array2` 的元素。方法 `outputArray`（参数 `int[][] array`）表示该方法接收一个二维数组。嵌套语句（第 23–30 行）输出二维数组的每一行。在外部语句的循环继续部分中，表达式 `array.length` 决定了 `array` 的行数。在内层语句中，表达式 `array[row].length` 决定了数组当前行的列数。内层语句的条件允许循环确定每行的确切列数。我们在图 7.18 中演示了嵌套的增强型 for 语句。

## 使用 for 语句执行的多维数组操作

常见的数组操作使用 `for` 语句。例如，以下 `for` 语句将图 7.16 中数组 `a` 的第 2 行的所有元素设为 0：

```java
for (int column = 0; column < a[2].length; column++)
    a[2][column] = 0;
```

我们指定了第 2 行；因此我们知道第一个索引始终为 2（0 是第一行，1 是第二行）。该循环仅改变第二个索引（即列索引）。如果数组 `a` 的第 2 行包含四个元素，则前面的 `for` 语句等于以下赋值语句：

```java
a[2][0] = 0;
a[2][1] = 0;
a[2][2] = 0;
a[2][3] = 0;
```

以下嵌套的 for 语句计算数组 `a` 中所有元素的总和：

```java
int total = 0;
for (int row = 0; row < a.length; row++)
{
    for (int column = 0; column < a[row].length; column++)
        total += a[row][column];
}
```

这些嵌套语句一次计算一行的总和。外部语句首先将行索引设置为 0，以便通过内层语句计算第一行元素的总和。然后，外部语句将 `row` 增加到 1，以便计算第二行的总和。接着，外部 `for` 将 `row` 增加到 2，以便计算第三行的总和。变量 `total` 可以在外部语句终止时显示。在接下来的示例中，我们展示了如何使用嵌套的增强型 for 语句以类似的方式处理二维数组。

## 7.12 案例研究：使用二维数组的 GradeBook 类

在第 7.10 节中，我们展示了 GradeBook（图 7.14），它使用一个一维数组来存储学生单次考试的成绩。在大多数学期中，学生会参加多次考试。教授可能会分析整个学期的成绩，包括针对单个学生和整个班级。

### 在 GradeBook 类中使用二维数组存储成绩

图 7.18 包含一个 GradeBook 类，该类使用二维数组来存储多个学生在多次考试中的成绩。数组的每一行代表一个学生在该门课程的成绩，每一列代表参加某次考试的所有学生的成绩。`GradeBookTest`（图 7.19）将数组作为参数传递给 GradeBook 构造函数。在使用时，通过了一个二维数组存储十名学生在三次考试中的成绩。通过五个方法来处理成绩。每个方法都与之前一维数组版本的 GradeBook（图 7.14）中的对应方法相似。`getMinimum` 方法（第 46–62 行）确定任何学生在该学期的最低分。`getMaximum` 方法（第 65–83 行）确定任何学生在该学期的最高分。`getAverage` 方法（第 86–92 行）确定特定学生的学期平均分。`outputBarChart` 方法（第 99–129 行）为整个学期的学生成绩绘制条形图。`outputGrades` 方法（第 132–156 行）以表格格式输出数组，并带上每个学生的学期平均分。

```java
// 图 7.18: GradeBook.java
// 使用二维数组存储成绩的 GradeBook 类
public class GradeBook {
    private String courseName; // 此成绩单所代表的课程名称
    private int[][] grades; // 学生成绩的二维数组
    // 两个参数的构造函数初始化 courseName 和 grades 数组
    public GradeBook(String courseName, int[][] grades) {
        this.courseName = courseName;
        this.grades = grades;
    }
    // 设置课程名称的方法
    public void setCourseName(String courseName) {
        this.courseName = courseName;
    }
    // 获取课程名称的方法
    public String getCourseName() {
        return courseName;
    }
    // 对数据执行各种操作
    public void processGrades() {
        // 输出成绩
        outputGrades();
        // 调用 getMinimum 和 getMaximum 方法
        System.out.printf("%n%s%n%s%n",
            "Lowest grade in the grade book is: %d", getMinimum(),
            "Highest grade in the grade book is: %d", getMaximum());
        // 输出所有考试的成绩分布图
        outputBarChart();
    }
    // 查找最低分
    public int getMinimum() {
        // 假设数组的第一个元素是最小的
        int lowGrade = grades[0][0];

        // 遍历 grades 数组的行
        for (int[] studentGrades : grades)
        {
            // 遍历当前行的列
            for (int grade : studentGrades)
            {
                if (grade < lowGrade)
                    lowGrade = grade;
            }
        }
        return lowGrade;
    }
    // 查找最高分
    public int getMaximum() {
        // 假设数组的第一个元素是最大的
        int highGrade = grades[0][0];

        // 遍历 grades 数组的行
        for (int[] studentGrades : grades)
        {
            // 遍历当前行的列
            for (int grade : studentGrades)
            {
                // 如果 grade 大于 highGrade，则将其赋值给 highGrade
                if (grade > highGrade)
                    highGrade = grade;
            }
        }
        return highGrade;
    }
    // 计算平均分
    public double getAverage(int[] setOfGrades) {
        int total = 0;

        // 计算学生的成绩总和
        for (int grade : setOfGrades)
            total += grade;

        // 返回平均分
        return (double) total / setOfGrades.length;
    }
    // 输出整体条形图
    public void outputBarChart() {
        // 条形图的实现
    }
}
```

图 7.18 | 使用二维数组存储成绩的 GradeBook 类。（4 部分中的第 1 部分。）

### getAverage 方法

方法 `getAverage`（第 86–96 行）接受一个参数——一个特定学生测试结果的一维数组。当第 153 行调用 `getAverage` 时，参数是 `grades[student]`，它指定了将二维数组 `grades` 的特定行传递给 `getAverage`。例如，根据图 7.19 中创建数组，参数 `grades[1]` 代表存储在二维数组 `grades` 第 1 行的三个值（一个成绩的一维数组）。记住，二维数组是元素为一维数组的数组。`getAverage` 方法计算数组元素的总和，将总和除以测试结果的数量，并将浮点数结果作为 `double` 值返回（第 95 行）。

### GradeBookTest 展示了 GradeBook 类

图 7.19 使用整型二维数组 `gradesArray`（第 10–19 行声明并初始化）创建了 `GradeBook` 类的对象（图 7.18）。第 21–22 行将课程名称和 `gradesArray` 传递给 `GradeBook` 构造函数。第 23–24 行显示包含课程名称的欢迎消息，然后第 25 行调用 `myGradeBook` 的 `processGrades` 方法来显示汇总该学期学生成绩的报告。

```java
// Fig. 7.19: GradeBookTest.java
// GradeBookTest 使用成绩二维数组创建 GradeBook 对象，
// 然后调用 processGrades 方法对其进行分析。
public class GradeBookTest
{
    // main 方法开始程序执行
    public static void main(String[] args)
    {
        // 学生成绩的二维数组
        int[][] gradesArray = {{87, 96, 70},
                              {68, 87, 90},
                              {94, 100, 80},
                              {100, 81, 82},
                              {83, 65, 85},
                              {78, 87, 65},
                              {85, 75, 83},
                              {91, 94, 100},
                              {76, 72, 84},
                              {87, 93, 73}};
        GradeBook myGradeBook = new GradeBook(
            "CS101 Introduction to Java Programming", gradesArray);
        System.out.printf("Welcome to the grade book for%n%s%n",
            myGradeBook.getCourseName());
        myGradeBook.processGrades();
    }
}
```
