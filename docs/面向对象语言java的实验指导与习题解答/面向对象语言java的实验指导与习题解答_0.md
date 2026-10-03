
# 面向对象语言（Java）实验指导与习题解答

## 前言

本书主要介绍了 Java 程序设计的基础知识和综合应用，全书分为两部分，第一部分是基础实验，第二部分是习题指导。基础实验部分共有 8 个实验，从 Java 程序设计的运行环境开始，由简入深，逐步到更为复杂的应用，每一个实验都是一个完整的案例，通过使用这些直观的教学案例，能有效帮助教师及学生开展对 Java 基本知识与技术的教与学。习题指导部分为 10 个章节，从 Java 的入门到 Java 的应用程序、线程和异常，每个章节都列出了大量的相关练习题，包括选择题、判断题、填空题、程序填空题、程序改错题、程序阅读题、程序设计题。

本书从介绍基本的编程入门知识开始，循序渐进地增加课程内容的难度，在每一个实验中都列出了具体的实验步骤和代码，同学可以通过实际操作这些代码来完成对知识点的学习与体验，同时，提供了思考题用于学习者反思学习效果，并有助于启迪思维，每一章节的习题都给出了参考答案，方便同学们学习。

本书得到了赣南师范大学校本特色教材立项资助，同时也得到了面向对象程序设计（Java）精品课程组教师们的大力支持。另外，黄媚、肖毅、邱熙雯、张永强、邓凌、周佳文等参与了书中代码的调试工作，在此一并表示感谢！

由于水平有限，尽管编者不遗余力，书中仍可能有错误和不足之处，敬请同行和读者，特别是使用本书的教师和同学们批评指正。

编　者

2017 年 4 月

# 第一部分　实验

## 实验一　Java 运行环境，Java 程序的编辑、编译与运行

### 一、实验目的

1. 掌握设置 Java 程序运行环境的方法，并熟悉 Java 程序的集成开发工具。
2. 掌握编辑、编译、运行简单的 Java Application 和 Java Applet 程序的方法步骤，初步了解 Java 程序的特点和基本结构。

### 二、实验内容

1. 安装 JDK。
2. 进行环境变量的配置。
3. 安装 Eclipse。
4. 熟悉 Eclipse 开发环境。
5. 编写一个 Java Application，利用 JDK 软件包中的工具编译并运行这个程序，使之能够输出字符串信息“Hello Java！”

### 三、实验要求

完成 Java 程序开发以及相关配置，并实现 Hello。

### 四、实验过程

1. 下载 JDK

`http://www.oracle.com/technetwork/java/javase/downloads/jdk13351.html`

以上是下载 JDK 的官方网址，进入后流程，选择适合自己（Windows）的 JDK 下载。

2. 配置环境变量

在桌面上右击“电脑”，依次点击【属性】【高级】【环境变量】。双击【系统变量】里面的 Path 项，将 JDK 中 bin 目录添加到这里。

3. 下载 Eclipse

`https://www.eclipse.org/downloads/`

以上是下载 Eclipse 的官方网址，进入后流程，选择适合自己的 Eclipse 下载。

4. 编写一个 Java Application，利用 JDK 软件包中的工具编译并运行这个程序，使之能够输出字符串信息“Hello Java！”

步骤（1）：编辑、编译 Java 源程序。

打开 Eclipse，新建一个 Java 文件，键入如下代码：

```
![img](img/txt000_1.jpg)
```

步骤（2）：编译 Java 源程序。

控制台输出。

```
![img](img/txt000_2.jpg)
```

步骤（3）：运行 Java 源程序。

观察结果。

```
![img](img/txt000_3.jpg)
```

### 五、思考题

（此处省略，原文未具体内容）

## 实验二　使用流程控制语句编程序

### 一、实验目的

1. 掌握流程控制语句的用法。
2. 学会流程控制语句解决实际问题。

### 二、实验内容

1. 学习 if-else 语句。
2. 学习 switch 语句。
3. 学习 for、while、do-while 循环语句。

### 三、实验要求

1. 能够编写带有流程语句的程序。
2. 理解程序执行的逻辑。

### 四、实验过程

1. 编写一个简单的 if-else 程序，判断奇偶。
2. 编写一个使用 switch 语句的计算器。
3. 编写一个 for 循环阶。

### 五、思考题

（此处省略，原文未具体内容）

## 实验三　类与类之间的关系

### 一、实验目的

1. 理解类的关系。
2. 掌握构造重载。

### 二、实验内容

1. 学习 extends 关键字。
2. 学习 super 的使用。
3. 学习方法的重写。

### 三、实验要求

1. 能够实现类的继承。
2. 理解子类对类的。

### 四、实验过程

1. 定义父类 Shape。
2. 定义子类 Circle 和 Rectangle。
3. 使用 super 调用父类方法。

### 五、思考题

（此处省略，原文未具体内容）

## 实验四　编制用户异常类

### 一、实验目的

1. 理解异常处理机制。
2. 学会使用 try-catch-finally 异常。

### 二、实验内容

1. 自定义一个异常类。
2. 在程序中使用 throw 和 throws 关键字。

### 三、实验要求

1. 能够抛出并捕捉自定义异常。
2. 理解异常的堆栈信息。

### 四、实验过程

1. 创建继承 Exception 的类 MyException。
2. 在方法中抛出该异常。

### 五、思考题

（此处省略，原文未具体内容）

## 实验五　文件操作

### 一、实验目的

1. 掌握文件的读写操作。
2. 学会使用 File 类输入输出。

### 二、实验内容

1. 使用 BufferedWriter 写入数据。
2. 使用 BufferedReader 读取数据。

### 三、实验要求

1. 能够完成基本的文件读写。
2. 理解文件流的概念。

### 四、实验过程

1. 创建一个 .txt 文件并写入内容。
2. 读取该文件内容并打印。

### 五、思考题

（此处省略，原文未具体内容）

## 实验六　Java Applet 编程与事件机制

### 一、实验目的

1. 了解 Applet 的基础。
2. 学会事件监听机制。

### 二、实验内容

1. 编写一个简单的 Applet。
2. 实现点击事件处理。

### 三、实验要求

1. 能够运行一个简单的 Applet。
2. 理解事件处理器的原理。

### 四、实验过程

1. 编写继承 Applet 的类。
2. 添加 ActionListener 监听。

### 五、思考题

（此处省略，原文未具体内容）

## 实验七　动画及声音的设置

### 一、实验目的

1. 掌握简单的动画实现。
2. 学会处理音频文件。

### 二、实验内容

1. 使用线程实现动画。
2. 播放 .wav 文件。

### 三、实验要求

1. 能够实现基础动画效果。
2. 理解资源的使用。

### 四、实验过程

1. 编写一个移动图形的程序。
2. 加载并播放背景音乐。

### 五、思考题

（此处省略，原文未具体内容）

## 实验八　Java 与数据库的连接

### 一、实验目的

1. 了解 JDBC 连接。
2. 学会对数据库进行操作。

### 二、实验内容

1. 建立数据库连接。
2. 执行 SQL 语句并获取结果。

### 三、实验要求

1. 能够连接数据库并查询数据。
2. 理解 JDBC 的流程。

### 四、实验过程

1. 配置数据库驱动。
2. 编写连接代码执行。

### 五、思考题

（此处省略，原文未具体内容）

在实现父类与子类的继承关系后，进一步调试并实现类与接口的关系。

## 实验四　编制用户自己的异常类

### 一、实验目的

掌握 Java 异常类的继承关系，熟悉 Java 的异常处理机制。

### 二、实验内容

1. 编写一个用户定义的异常类`CatchErr`。当在 MS－DOS 命令提示符下输入：

`D：\Java\＞java CatchErr X`（回车）

`X`是整数或其他字符。运行时，程序要判断用户输入的`X`是否是负数，若是负数，在 Java 运行时系统自动抛出非负数的`Exception`，并且捕获这个异常并在屏幕上显示“你输入的不是整数！”。

2. 编写`Java Application`程序。

### 三、实验要求

1. 必须使用`try－catch`语句。
2. 运行过程中自动捕获“运行时的异常”和“用户自定义的异常”。

### 四、实验过程

1. 创建工程。

![img](img/txt005_1.jpg)

图 1－4－1 创建工程

2. 创建一个类`CatchErr`。
3. 输入代码：`public class CathErr`。

![img](img/txt005_2.jpg)![img](img/txt005_3.jpg)

4. 程序目录结构：

![img](img/txt005_4.jpg)

图 1－4－2 程序目录

5. 编译运行

![img](img/txt005_5.jpg)

图 1－4－3 运行结果

### 五、思考题

1. 语句`System.out.println()`中`System`是类名，为什么程序中可以直接使用`System`类？
2. 每个没有写明父类的 Java 程序是哪个类的子类？

## 实验五　文件操作

### 一、实验目的

熟悉 Java 的字符文件读写机制，理解字符输入输出流的使用方法。

### 二、实验内容

接收键盘输入的字符串，用`FileWriter`类将字符串写入文件，用`FileReader`类读出文件内容显示在屏幕上。

### 三、实验要求

1. 程序必须能够从键盘接收字符串并以一行一行的格式保存在文件中。
2. 程序必须能够读出文件内容显示在屏幕上。

### 四、实验过程

1. 创建工程。

![img](img/txt006_1.jpg)

图 1－5－1 创建工程

2. 新建一个类`fileOperation`。
3. 编写主方法`main()`，其中实现接收键盘输入功能、文件操作功能和文件内容输出功能。
4. 接收键盘输入可以采用类似下面的代码：

![img](img/txt006_2.jpg)

5. 创建文件对象：`File myfile=new File("Line.txt")`。
6. 创建文件输出流对象：`BufferedWriter bw=new BufferedWriter(new FileWriter(myfile))`。
7. 写入文件：`bw.write(s)`；`bw.newLine()`。
8. 创建文件输入流对象：`BufferedReader brF=new BufferedReader(new FileReader(myfile))`。
9. 读文件内容：`s=brF.readLine()`。
10.

![img](img/txt006_3.jpg)

图 1－5－2 代码展示

11. 程序目录结构

![img](img/txt006_4.jpg)

图 1－5－3 程序目录结构

12. 运行结果

![img](img/txt006_5.jpg)

图 1－5－4 运行结果

### 五、思考题

1. `File`对象能读写文件吗？
2. `File`对象怎样获取文件的长度？

## 实验六　Java Applet 编程与事件的处理机制

### 一、实验目的

1. 熟悉 Java Applet 程序的构成和运行方式。
2. 理解 Java Applet 编程方法。
3. 掌握向 Java Applet 传递参数的方法。

### 二、实验内容

编写 Java Applet 程序，使它在浏览器中通过响应功能按钮的点击事件绘制各种简单的几何图形（矩形、圆形、扇形、多边形和他们的填充效果），并且能够通过接收传递参数控制图形的绘制。

### 三、实验要求

1. 必须编写成 Java Applet 程序。
2. 绘制至少 2 种以上的简单图形。
3. 能允许通过点击不同的按钮绘制不同的图形。
4. 根据 Java Applet 生命周期、事件响应的方式等机制正确调试并运行程序。

### 四、实验过程

1. 进入 Java 编程环境。

![img](img/txt007_1.jpg)

图 1－6－1 进入 java 编程环境（1）

![img](img/txt007_2.jpg)

图 1－6－2 进入 java 编程环境（2）

2. 新建一个 Java 文件，命名为`drawpattern.java`。

![img](img/txt007_3.jpg)

图 1－6－3 新建 java 文件

3. 编写`init()`方法，并向界面添加各种需要的组件，如按钮。

![img](img/txt007_4.jpg)![img](img/txt007_5.jpg)

4. 编写事件方法响应按钮点击事件，确定绘制何种图形。

![img](img/txt007_6.jpg)

5. 编写`paint()`方法根据要求绘制图形。

![img](img/txt007_7.jpg)![img](img/txt007_8.jpg)

6. 编写 HTML 程序使之能运行`drawing.java`。

![img](img/txt007_9.jpg)

7. 运行`drawpattern.java`，检查调试程序。

![img](img/txt007_10.jpg)

图 1－6－4 Applet 应用程序的启动

![img](img/txt007_11.jpg)

图 1－6－5 Applet 运行结果

![img](img/txt007_12.jpg)

图 1－6－6 运行结果（3）

### 五、思考题

如何使用 Java 一个贪蛇游戏？

## 实验七　动画及声音

### 一、实验目的

熟悉 Java Applet 中动画及声音的方法。

### 二、实验内容

编写一个 Java Applet 程序，有一个圆形钟，且钟下面有时间显示，效果 1－7－1 所示。

![img](img/txt008_1.jpg)

图 1－7－1

### 三、实验要求

1. 必须编写成 Applet 程序。
2. 程序要有时间、日期。

### 四、实验过程

1. 进入 Java 编程环境（这里 Eclipse 为例）。

![img](img/txt008_2.jpg)

图 1－7－2 程序建立界面

2. 建一个文件，命名为`Zhong.java`（右击新建类，在名称栏填写`Zhong`完成）。

![img](img/txt008_3.jpg)

图 1－7－3 程序目录

3. 输入代码。



```java
import java.util.*;
import java.awt.*;
import java.applet.*;
import java.text.*;

public class Zhong extends Applet implements Runnable {
    Thread timer; // 用于时钟的线程
    int lastxs, lastys, lastxm, lastym, lastxh, yh;
    SimpleDateFormat formatter; // 格式化时间
    String lastdate; // 保存时间的字符串
    Font clockFace; // 显示时钟里面的字体
    Date currentDate; // 显示当前时间
    Color handColor; // 显示秒针、分针的颜色
    Color numberColor; // 显示秒针和数字的颜色

    public void init() {
        int x, y;
        lastxs = lastys = lastym = lastym = lastxh = yh = 0;
        formatter = new SimpleDateFormat("EEE dd hh:mm:ss");
        currentDate = new Date();
        lastdate = formatter.format(currentDate);
        clockFace = new Font("Serif", Font.PLAIN, 14);
        handColor = Color.blue;
        numberColor = Color.darkGray;
        try {
            setBackground(new Color(Integer.parseInt("bgcolor")));
        } catch (Exception E) {}
        try {
            handColor = new Color(Integer.parseInt("fgcolor")));
        } catch (Exception E) {}
        try {
            numberColor = new Color(Integer.parseInt("fg2")));
        } catch (Exception E) {}
        resize(300, 300); // 设置时钟窗口
    }

    // 计算四分之一的圆弧
    public void plotpoints(int x0, int y0, int x, int y, Graphics g) {
        g.drawLine(x0 + x, y0 + y, x0 + x, y0 + y);
        g.drawLine(x0 + y, y0 + x, x0 + y, y0 + x);
        g.drawLine(x0 + y, y0 - x, x0 + y, y0 - x);
        g.drawLine(x0 + x, y0 - y, x0 + x, y0 - y);
        g.drawLine(x0 - x, y0 - y, x0 - x, y0 - y);
        g.drawLine(x0 - y, y0 - x, x0 - y, y0 - x);
        g.drawLine(x0 - y, y0 + x, x0 - y, y0 + x);
        g.drawLine(x0 - x, y0 + y, x0 - x, y0 + y);
    }

    // 用 Bresenham 算法画圆，其中（x0,y0）是圆的中心，r 为半径
    public void circle(int x0, int y0, int r, Graphics g) {
        int x, y;
        float d;
        x = 0;
        y = r;
        d = 5 / 4 - r;
        plotpoints(x0, y0, x, y, g);
        while (y > x) {
            if (d < 0) {
                d = d + 2 * x + 3;
                x++;
            } else {
                d = d + 2 * (x - y) + 5;
                x++;
                y--;
            }
            plotpoints(x0, y0, x, y, g);
        }
    }

    public void paint(Graphics g) {
        int xh, yh, xm, ym, xs, ys, s = 0, m = 10, h = 10, xcenter, ycenter;
        String today;
        currentDate = new Date();
        formatter = new SimpleDateFormat("s", Locale.getDefault());
        try {
            s = Integer.parseInt(formatter.format(currentDate));
        } catch (NumberFormatException n) {
            s = 0;
        }
        formatter.applyPattern("m");
        try {
            m = Integer.parseInt(formatter.format(currentDate));
        } catch (NumberFormatException n) {
            m = 10;
        }
        formatter.applyPattern("h");
        try {
            h = Integer.parseInt(formatter.format(currentDate));
        } catch (NumberFormatException n) {
            h = 10;
        }
        formatter.applyPattern("EEE dd HH:mm:ss yyy");
        today = formatter.format(currentDate);
        // 设置时钟的表盘中心为（80,55）
        xcenter = 80;
        ycenter = 55;
        // a=s*pi/2-pi/2 to 0:00 to 12:00
        // x=r(cos a)+xcenter,y=r(sin a)+ycenter
        xs = (int) (Math.cos(s * 3.14f / 30 - 3.14f / 2) * 45 + xcenter);
        ys = (int) (Math.sin(s * 3.14f / 30 - 3.14f / 2) * 45 + ycenter);
        xm = (int) (Math.cos(m * 3.14f / 30 - 3.14f / 2) * 40 + xcenter);
        ym = (int) (Math.sin(m * 3.14f / 30 - 3.14f / 2) * 40 + ycenter);
        xh = (int) (Math.cos(h * 3.14f / 30 - 3.14f / 2) * 30 + xcenter);
        yh = (int) (Math.sin(h * 3.14f / 30 - 3.14f / 2) * 30 + ycenter);
        // 画时钟外面的圆盘中心在（xcenter,ycenter）半径为 50
        g.setFont(clockFace);
        g.setColor(handColor);
        circle(xcenter, ycenter, 50, g);
        // 画时钟表里的数字
        g.setColor(numberColor);
        g.drawString("9", xcenter - 45, ycenter + 3);
        g.drawString("3", xcenter + 45, ycenter + 3);
        g.drawString("6", xcenter, ycenter + 45);
        g.drawString("12", xcenter, ycenter - 45);
    }
}
```

## 实验八 Java 与数据库的连接

### 一、实验目的

熟悉有关 Java 与数据库的类，并能定义 Windows 操作系统下的数据源，为课程设计打下基础。

### 二、实验内容

编写 Java Applet 程序，使它与数据库连接。

### 三、实验要求

成功完成数据库的连接，并截图显示。

### 四、实验过程

1. 建立一个 Access 数据库，命名为`shop.mdb`。

![img](img/txt009_1.jpg)

2. 设置表结构并向数据库中添加一行内容。

![img](img/txt009_2.jpg)

图 1－8－1 添加数据

3. 建立一个类。

![img](img/txt009_3.jpg)

图 1－8－2 目录结构

4. 导入驱动程序。

![img](img/txt009_4.jpg)

图 1－8－3 导入驱动程序

![img](img/txt009_5.jpg)

图 1－8－4 生成数据库文件

5. 编写代码。

6. 从数据库中读出数据。

### 五、思考题

能否向数据库中写入数据？

# 第二部分 习题

## 第一章 Java 入门

### 一、单项选择题

1. 下面关于`Java Application`程序结构特点描述中，错误的是（　）。

A. 一个`Java Application`程序由一个或多个文件组成，每个文件中可以定义一个或多个类，每个类由若干个方法和变量组成

B. `Java`程序中声明有`public`类时，则`Java`程序文件名必须与`public`类的类名相同，并区分大小写，扩展名为`.java`

C. 组成`Java Application`程序的多个类中，有且仅有一个主类

D. 一个`.java`文件中定义多个类时，允许其中声明多个`public`类

2. 编译`Java`程序后生成的面向字节 JVM 的字节码文件的扩展名是（　）。

A.`.java` B.`.class` C.`.obj` D.`.exe`

3. `Java`的核心包中，提供编程应用的基本类的包是（　）。

A.`java.util` B.`java.lang` C.`java.applet` D.`java.rmi`

4. 下列标识符（名字）命名原则中，正确的是（　）。

A. 类名的首字母小写 B. 接口名的首字母小写

C. 常量全部大写 D. 变量名和方法名的首字母大写

5. 下面哪个选项是正确的`main`方法说明？（　）。

A.`void main()` B.`private static void main(String args［］)`

C.`public main(String args［］)` D.`public static void main(String args［］)`

6. 下面哪种注释方法能够支持`javadoc`命令？（　）。

A.`//` B.`./*...*/`

C.`./＊＊...*/` D.`./＊＊...＊＊/`

7. 下列选项中，不属于`Java`语言特点的一项是（　）。

A. 分布式 B. 安全性 C. 编译执行 D. 面向对象

8. 编译下面源程序会得到哪些文件（　）？

```
class A1{}
class A2{}

public class B
{
public static void main(String［］args){}
}
```

A. 只有`B.class`文件 B. 只有`A1.class`和`A2.class`文件

C. 编译不成功 D. `A1.class`、`A2.class`和`B.class`文件

9. 下列描述中，不正确的是（　）。

A. 不支持多线程

B. 一个`Java`源文件不允许有多个公共类

C. `Java`通过接口支持多重继承

D. `Java`程序分为`Application`和`Applet`两类

10. `Java`语言属于哪种语言？（　）。

A. 面向机器的语言 B. 面向对象的语言

C. 面向过程的语言 D. 面向操作系统的语言

11. `Java`语言是 1995 年由（　）公司发布的。

A. `Sun` B. `Microsoft` C. `Borland` D. `Fox Software`

12. `Java application`中的主类需包含`main`方法，以下（　）项是`main`方法的正确形参。

A.`String args` B.`String ar［］`

C.`Char arg` D.`StringBuffer args［］`

13. 如下哪个是`Java`中有效的关键字（　）。

A.`name` B.`hello` C.`false` D.`good`

14. 下列为合法的标识符的是（　）。

A.`a=b` B.`._Hello` C.`2nd` D.`Chong qing`

15. 下列为合法的标识符的是（　）。

A.`new` B.`class` C.`int` D.`const2`

### 二、填空题

1. 每个`Java Application`程序可以包括许多方法，但是必须有且只能有一个`main`（）方法，统一格式为 ______，它是程序执行的入口。

2. `Java`源程序文件和字节码文件的扩展名分别为 ______ 和 ______。

3. 如果在`Java`程序中需要使用`java.util`包中的所有类，则应该在程序开始处加上 ______ 语句。

4. 一个`Java Application`程序由一个或多个文件组成，每个文件中可以定义一个或多个类，每个类由若干个 ______ 和 ______ 组成。

5. 在`Java`语言中，______ 是最基本的元素。

6. 编译一个定义了 3 个类和 10 个方法的`Java`源文件后，会产生 ______ 个字节码文件，扩展名是 ______。

7. 定义一个类，必须使用的关键字是 ______。

8. 阅读下列代码，该代码段的文件名为 ______。

![img](img/txt011_1.jpg)

### 三、判断题

1. `Java`语言具有较好的安全性和可移植性及与平台无关等特性。（　）

2. `Java Application`程序中，必有一个主方法`main`（），该方法有没有参数都可以。（　）

3. `java.util.Scanner（System.in)`可以接收用户从键盘输入的简单数据。（　）

4. `Java`程序中不区分大小写字母。（　）

5. 机器直接识别字节码文件，它经过`JVM`中的解释器边执行。（　）

6. `System`类中的`println（）方法分行显示，而`print（）方法不分行显示。（　）

7. 在运行字节码文件时，使用`Java`命令，一定要给出扩展名`.class`。（　）

8. `Java`源代码中定义几个类，编译结果生成几个`.class`后缀的字节码文件。（　）

9. `Java`各种数据类型占用长度，与平台无关。（　）

10. 注释的作用使程序执行在屏幕上显示。（　）

11. `Java`字符类型采用 Unicode 编码，但由硬件环境决定。（　）

12. 无论`Java`源程序包含几个类，若程序以`A.java`命名，编译后只有一个名为`A`的字节码文件。（　）

### 四、程序改错

![img](img/txt011_2.jpg)

### 五、程序阅读题

写出以下程序的运行。

![img](img/txt011_3.jpg)

### 六、程序设计题

输出以下信息。

![img](img/txt011_4.jpg)

### 习题答案

（注：原文提供的答案部分为乱码或占位符，此处保留格式，未翻译具体内容因其无意义字符，仅保持结构一致）

## 第二章 字符串

### 一、单项选择题

1. 下面语句中正确的是（　）。

A.`char='abc'` B.`float f=0.25` C.`double a=0.6` D.`long l=xff`

2. 变量命名规范的是（　）。

A.变量由字母、下划线、数字组成 B.变量不能以数字开头 C.`B`和`b`是同一个变量 D.不同变量可以起相同的名字

3. 下列`java`注释正确的是（　）。

A.`/*我北京*/` B.`//我北京*/` C.`/**我北京*/` D.`*我北京*/`

4. 为`boolean`类型赋值时，可以使用（　）。

A.`boolean=0` B.`boolean a=(8>=9)` C.`boolean a="假"` D.`boolean a==true`

5. 以下标识符中（　）不是合法的标识符。

A.`SUMME` B.`x3y` C.`void` D.`de$g`

6. 下面单词中（　）是`Java`语言的关键字。

A.`Sizeof` B.`abstract` C.`Null` D.`String`

7. 下面语句中出现出现警告或错误的是（　）。

A.`float f=1.3` B.`char c="a"` C.`byte b=25` D.`boolean d=null`

8. 下面语句中，正确的是（　）。

A.`boolean b="true"` B.`Continue` C.`Java` D.`PUBLIC`

9. 设有定义`int k=3`，语法正确且值为`true`的表达式是（　）。

A.`k=3` B.`k++>3` C.`k--==3&&k++==3` D.`k++==3||++k>3`

10. 设有定义`String s="World"`；下列错误的是（　）。



A. `int m=s.indexOf('r')`　B. `int n=s.length()`　C. `char c=s.charAt(0)`　D. `String str=s.append('2')`

11. 对于下列代码：

A. `String str1="mycode"`

B. `String str2="mycode"`

C. `String str3=new String("mycode")`

D. `StringBuffer str4=new StringBuffer("mycode")`

以下表达式的值为`true`的是（　）。

A. `str1==str2`　B. `str1==str4`　C. `str2==str3`　D. `str3==str4`

12. 以下程序段输出的结果是（　）。

![img](img/txt012_1.jpg)

A. `DEF`　B. `DEXYZ`　C. `ABCDEF`　D. `CDEXYZ`

13. 对于下列代码：

![img](img/txt012_2.jpg)

输出结果是（　）。

A. `java and d`　B. `java and b`　C. `java and d`　D. `java and a`

14. 以下代码运行正确的是（　）项。

![img](img/txt012_3.jpg)

A. `java.java`　B. `code.java`　C. `java.code`　D. `Code.code`

15. 下面结果正确的是（　）。

![img](img/txt012_4.jpg)

A. `123`　B. `23`　C. `12`　D. `3`

16. 下面运行正确的是（　）。

```java
public class Test{
public static void main(String[] args){
}
```

![img](img/txt012_5.jpg)

A. `Hello!`　B. `Hello!`　C. `Hello!`　D. `Hello`

17. 下面结果正确的是（　）。

![img](img/txt012_6.jpg)

A. `Abc`　B. `Abced`　C. `bed`　D. `Abc`

18. 下面结果正确的是（　）。

![img](img/txt012_7.jpg)

A. `true true`　B. `true false`　C. `false true`　D. `false true`

19. 下面输出结果的是（　）。

![img](img/txt012_8.jpg)

A. `1`　B. `3`　C. `6`　D. `7`

20. 下面结果正确的是（　）。

![img](img/txt012_9.jpg)

A. `mycode666`　B. `myco66`　C. `cod66`　D. `Mycode66`

### 二、填空题

1. 在`java`中，字符串是 ______ 出现的。

2. `Java`标识符是由字母、______、符号组成的。

3. 类 ______ 维护一个字符串池。字符串池指向的字符串示例，以及调用 ______ 方法后的字符串。

4. 在`Java`语言中，______ 是用双引号括起来的序列，不是字符数组，而是`String`的实例。

5. ______ 是不可变类，对象包含的字符串永远改变。______ 是可变类，对象的内容可以添加或修改。

6. `String`类 ______ 方法判断字符串的前缀是`s`。

7. `String`类的 ______ 方法判断字符串的后缀是`s`。

8. `String`类的 ______ 方法比较字符串`s1`与`s2`相同。

9. 字符串调用 ______ 方法检索字符串`s`，并返回首次出现`s`的位置。如果没有检索到`s`，该方法是`-1`。

10. 字符串`s`通过 ______ 得到一个字符串，该字符串是`s`去掉空格后的字符串。

11. `java.lang`包中的`Integer`类调用其方法 ______ 可以将“数字”格式的字符串，如“123”，转化为`int`型数据。

12. 可以`String`类调用 ______ 将数值转化为字符串。

13. `StringBuffer`类调用 ______ 返回缓冲区字符串。

14. `Object`类有一个`public`方法是 ______，一个对象通过该方法获得该字符串表示。

15. ______ 是所有`Java`类的最终祖先，如果一个类在声明时没有包含`extends`关键词，那么这个类继承`Object`类。

### 三、判断题

1. `"hello"`是字符串常量。（　）

2. 利用`equals()`方法判定`Date`类时，判断的是对象的值而不是地址。（　）

3. `Java`中的`String`类的对象既可以是字符串常量，也可以是变量。（　）

4. `String`类的方法`replace(CharSequence srt, CharSequence srt)`返回一个新的字符串，它是通过用`srt`替换此字符串中出现的所有`srt`得到的。（　）

5. 字符串常量可以用双引号引起来，也可以用单引号引起来。（　）

### 四、程序阅读题

1. 请说出`Test`类标注的【代码】输出结果。

![img](img/txt012_10.jpg)

2. 请说出`Test`类标注的【代码 1】和【代码 2】的输出结果。

![img](img/txt012_11.jpg)![img](img/txt012_12.jpg)

3. 请说出`Test`类标注的【代码】输出结果。

![img](img/txt012_13.jpg)

4. 请写出下面程序的输出结果。

![img](img/txt012_14.jpg)

5. 请写出下面程序输出结果。

![img](img/txt012_15.jpg)![img](img/txt012_16.jpg)

6. 请写出下面程序的输出结果。

![img](img/txt012_17.jpg)

7. 请写出下面程序的输出结果。

![img](img/txt012_18.jpg)

8. 请输出下面程序代码的结果。

![img](img/txt012_19.jpg)![img](img/txt012_20.jpg)

9. 请输出下面程序的代码结果。

![img](img/txt012_21.jpg)

10. 请输出下面代码的结果。

![img](img/txt012_22.jpg)![img](img/txt012_23.jpg)

### 五、程序设计题

1. 编写一个程序，输出`Hello world`。

2. 编写一个程序，使用`String`方法`substring`将字符串`Hello world`中的`world`部分提取出来。

3. 编写一个程序，使用`String`方法`replace`将字符串`Hello world`中的`world`替换为`Java`。

4. 编写一个程序，使用`String`方法`indexOf`找到字符串`Hello world`中`world`出现的位置。

5. 编写一个程序，使用`String`方法`contains`判断字符串`Hello world`是否包含`Java`。

6. 编写一个程序，使用`String`方法`startsWith`判断字符串`Hello world`是否以`Hello`开头。

7. 编写一个程序，使用`String`方法`endsWith`判断字符串`Hello world`是否以`world`结尾。

8. 编写一个程序，使用`String`方法`equals`比较字符串`Hello world`和`hello world`。

9. 编写一个程序，使用`String`方法`compareTo`比较字符串`Hello world`和`Java world`。

10. 编写一个程序，使用`String`方法`split`将字符串`Hello world`按照空格分割成数组。

### 3. `public class Test`

![img](img/txt012_27.jpg)![img](img/txt012_28.jpg)

**运行结果：**

输入一个字符串：

abcdabcefgabhi

输入要查找的子串：

ab

查找到的个数：3

### 4. `import java.util.Scanner;`

![img](img/txt012_29.jpg)![img](img/txt012_30.jpg)

**运行结果：**

输入字符串的个数：

![img](img/txt012_31.jpg)![img](img/txt012_32.jpg)

**运行结果：**

输入第一个字符串：123

输入第二个字符串：456

输入的两个字符串相加结果为：123456

输入字符串转换为整数相加结果为：579

输入字符串转换为浮点数相加结果为：579.0

## 第三章 选择

### 一、单项选择题

1. 执行完下面程序片段后，（ ）的结论是正确的。

```java
int x,y,z;
x=2;
y=3;
z=(x+y>5?x++:y++);
```

A. `x`的值是 3，`y`的值是 5　B. `x`的值是 2，`y`的值是 5　C. `x`的值是 2，`y`的值是 3　D. `c`的值是 false

2. 对一个 `boolean` 类型变量赋值时，可以使用（ ）。

A. `boolean=1`　B. `boolean c=(1>=2)`　C. `boolean c="真"`　D. `boolean c==false`

3. 表达式`(12+4*6)/5%2`的值是（ ）。

A. 4　B. 3　C. 2　D. 1

4. 下列运算符优先级别排序正确的是（ ）。

A. 由高向低分别是：`()`、`!`、算术运算符、关系运算符、逻辑运算符、赋值运算符

B. 由高向低分别是：`()`、关系运算符、算术运算符、赋值运算符、`!`、逻辑运算符

C. 由高向低分别是：`()`、算术运算符、逻辑运算符、关系运算符、`!`、赋值运算符

D. 由高向低分别是：`()`、`!`、关系运算符、赋值运算符、算术运算符、逻辑运算符

5. 下列输出的结果是（ 1）。

```java
int a=1;
while(a<6){
    switch(a){
        case 0:
        case 3:a=a+6;
        case 1:
        case 2:a=a+7;
        default:a=a+8;
    }
}
System.out.print(a);
```

A. 13　B. 15　C. 16　D. 其他

6. 下列代码输出的结果是（ 1）。

```java
int i=12;
while(i>0){
    i=i+2;
    if(i==20){
        break;
    }
}
```

A. `while`循环执行 4 次　B. 死循环　C. 循环一次都不执行　D. 循环执行一次

7. 执行下面代码的结果是（ 1）。

```java
for(int i=0;;){
    System.out.println("我爱"+i);
    break;
}
```

A. 语法错误，缺少表达式 2 和表达式 3　B. 死循环　C. 程序什么都不输出　D. 输出：我爱 0

8. 下面代码输出的结果是（ 1）。

```java
int a=0,b=0;
do{
    if(a%2==0){
        b++;
        continue;
    }
    a++;
    b=a+b;
}while(b<9);
System.out.println(b);
```

A. 10　B. 9　C. 8　D. 7

9. 给出以下代码，请问该代码的运行结果是什么（ 1）。

```java
int z,x=9,y=10;
z=x+++y++;
System.out.print("z="+z);
System.out.print("x="+x);
System.out.print("y="+y);
```

A. 输出`z=15`；`x=16`；`y=19`　B. 输出`z=19`；`x=16`；`y=17`　C. 输出`z=19`；`x=10`；`y=11`　D. 输出`z=16`；`x=11`；`y=19`

10. 执行下列语句序列后，`c`的值是（ 1）。

```java
int a=6,b=7,c=10;
if(++a==b)c=++a*c;
```

A. 68　B. 70　C. 80　D. 112

11. 下列语句序列执行后，`i`的值是（ 1）。

```java
int i=6,j=12;
if(i-1>j)
    i--;
else
    j--;
```

A. 4　B. 5　C. 6　D. 7

12. 当下列程序执行时，其输出结果是（ 1）。

```java
int n=8;
switch(n){
    default:
        System.out.println("default");
    case 0:
        System.out.println("zero");
        break;
    case 1:
        System.out.println("one");
    case 2:
        System.out.println("two");
}
```

A. default　B. default，zero　C. 错误：default 子句没有定义　D. 没有输出

13. 下面表达式中可用`a`和`b`的最大值的是（ 1）。

A. `a>b?b:a`　B. `a<b?b:a`　C. `a>b?(a+b):(a-b)`

14. 下面关于选择结构的正确的是（ 1）。

A. `if`语句和`else`语句成对　B. `if`语句可以`else`　C. `switch`结构每个`case`语句必须用`break`　D. `switch`结构必须有`default`

15. 编译运行以下程序，关于输出结果正确的是（ 1）。

![img](img/txt013.jpg)

A. 输出结果为：3　B. 输出结果为：18　C. 编译错误

16. `switch`语句不能用于下列数据类型（ 1）。

A. `byte`　B. `double`　C. `short`　D. `char`

17. 定义整型变量：`int a=456;`，表达式的值为 5 的是（ 1）。

A. `a/100`　B. `(a-450)/100`　C. `a%10`　D

18. 下列逻辑合法的是（ 1）。

A. `(9+18)&&(6-5)`　B. `(6*5)||(4*7)`　C. `8>6&&8<10`　D. `(10%4)&&6*3)`

19. 下面程序执行的结果是（ 1）。

```java
int n=20;
while(true){
    if(n++>20)
        break;
}
System.out.println(n);
```

A. 19　B. 20　C. 21　D. 22

20. 下面程序执行的结果是（ 1）。

```java
int c=3;
switch(c){
    case 1:
        c+=1;
        break;
    case 2:
        c+=2;
    case 3:
        c+=3;
        break;
    case 4:
        c+=4;
        break;
    default:
        c=15;
}
System.out.println(c);
```

A. 5　B. 6　C. 7　D. 8

21. 下面程序运行后，`x`、`y`、`z`的值正确的是（ 1）。

```java
int x=12,y=22;
int z=(x+y>34?x++:++y);
```

A. `x=13,y=23`　B. `x=12,y=23`　C. `x=12,y=22`　D. `z=22`

### 二、判断题

1. 如果某次循环执行了`break`语句，那么整个循环就结束。如果在某次循环执行了`continue`语句，那么本次循环就结束。

2. `switch`语句必须有`default`语句。

3. 若`switch`语句中的表达式的值与任何`case`值相等，则执行`default`后面的语句。

4. 在`if`语句中，其中的复合语句只有一条语句，}`可以省略。

5. `++x`在使用`x`之前，先`x`的值增 1；`x++`在使用`x`之后，使`x`的值增 1。

6. 如果`c=a+b`，那么`a=c-b`，也就是说`+`运算符仍然是`+`。

7. `+`运算符优先级高于`>`；`<`高于`||`；`&&`；`=`最低。

8. `if(true){int n=2;}System.out.println(n);`运行程序的输出是。

9. `if("hunan".indexOf('n')==6)System.out.println("true");`以上语句的结果是。

### 三、填空题

1. 在`Java`中，两个等号`==`是等于运算符，一个等号`=`赋值运算符。

2. 布尔型常量有两个值，分别是 ______ 和 ______。

3. 当整型变量`n`的值不能被 2 除尽时，其`false`的 Java 语言表达式是 ______。

4. 表达式`5/6*9%2`的计算结果是 ______。

5. `int a=4;System.out.println(++a);`输出结果为 ______。

6. 如果某个`case`中没有使用`break`语句，一旦表达式的值和`case`值相等，程序不仅执行该`case`里的语句，而且执行后继的`case`语句，直到碰到 ______ 语句为止。

7. 关系运算符的运算结果是 ______ 数据类型。

8. `if`语句中的条件表达式的值只能是型。

9. 在`while`语句的循环体中，执行`break`语句的效果是 ____________。

10. `switch(表达式)`语句中，表达式的值可以为 ______，______，______ 型。

### 四、程序填空题

1. 请完善程序，使它得到正确的结果。

运行结果：

输入 x 的值：4

g(4)=2;

输入 x 的值：16

g(16)=4;

输入 x 的值：-2

g(-2)=-4;



```java
import java.util.Scanner;
public class Mp{
    public static void main(String args[]){
        Scanner scanner=new Scanner(System.in);
        double x,y;
        for(int i=0;i<100;i++){
            System.out.println("请输入 x 的值：");
            x=scanner.nextDouble();
            if(__)
                y=______
            else
                y=2*x;
            System.out.println("x="+y);
        }
    }
}
```

2. 请完善程序，使它得到正确的结果。这个程序产生 2 个随机浮点数，然后使用条件运算符确定它们的大小。

```java
import java.util.Random;
public class Mn{
    public static void main(String args[]){
        Random random=new Random();
        float x=random.nextFloat();
        System.out.println("x="+x);
        float y=random.nextFloat();
        System.out.println("y="+y);
        float min=________;
        float max=________;
        System.out.println("min="+min);
    }
}
```

### 五、程序改错

1. 请改正程序中的错误，使它得到正确的结果。

```java
public class B{
    private int value;
    public B(int n){
        value=n;
    }
    public int getMax(int x,int y){
        if(x>=value)
            return x;
        else(y>=value)
            return y;
        else
            return value;
    }
    public static void main(String args[]){
        B obj=new B(10);
        System.out.println(obj.getMax(20,30));
    }
}
```

2. 请改正下列代码中的错误，使下列程序能够运行。

![img](img/txt013.jpg)

### 六、程序阅读题

1. 下列程序的输出是什么？

![img](img/txt013_3.jpg)![img](img/txt013_4.jpg)

2. 下列程序的输出是什么？

```java
public class Md{
    public static void main(String args[]){
        int sum=0;
        outer:
        for(int i=1;i<9;i++){
            inner:
            for(int j=1;j<6;j++){
                sum+=j;
                if(i+j>10)
                    break inner;
            }
        }
        System.out.println("sum="+sum);
    }
}
```

### 七、程序设计题

1. 编写一个 Java 程序，输入一个整数，判断它能被 3 整除。

2. 编写一个 Java 程序，用`if-else`语句判断某年份（由键盘输入）是否为闰年。

3. 判断 101～200 之间有多少个素数，并输出素数。

4. 编写一个 Java 程序，将一个正整数分解质因数。例如：输入 12，打印出 12=2*3。

5. 键盘输入两个正整数`m`和`n`，求它们的最大公约数和最小公倍数。

6. 键盘输入一行字符，分别统计其中字母、空格、数字的个数。

7. 编写一个 Java 程序，有 1、2、3 四个数字，求多少个互不相同且无重复的三位数。

8. 程序找出 1000 以内完数（一个数恰等于它的因子和，这个数称为“完数”）。例如 6=1+2+3。

9. 编写一个 Java 程序，根据利润发放奖金。利润低于等于 10 万元时，奖金按 10%；利润高于 10 万元，低于 20 万元时，奖金按 7.5%；利润高于 20 万元，奖金按 5%；利润在 20 万到 40 万之间，奖金按 5%；利润在 40 万到 60 万之间，奖金按 3%；利润在 60 万到 100 万之间，奖金按 1.5%；利润高于 100 万元时，奖金按 1%。从键盘输入利润，求应发放奖金总数。

10. 编写一个 Java 程序，输入某年某月某日，判断这一天是这一年的第几天。

11. 编写一个 Java 程序，输入星期几的字母来判断一下是星期几，如果字母一样。

### 习题答案

#### 一、单项选择

1～5 BBACD

6～10 DBCCC

11～15 CBBCD

16～20 BDCCC

#### 二、判断题

1.√ 2.× 3.√ 4.√ 5.√ 6.√ 7.√ 8.× 9.√

#### 三、填空题

1.赋值

2.`true`，`false`

3.`n%2==0`

4.0

5.5

6.`break`

7.`boolean`

8.`boolean`

9.整个循环结束

10.`byte`，`short`，`int`，`char`

#### 四、程序填空

1.`x>0`；`y=2.0*x`

2.`min=x<y?x:y`；`max=x>y?x:y`

#### 五、程序改错

1.第 10 行改为

2.在 4 前面加：

#### 六、阅读题

1.好好

2.`sum=10`

#### 七、程序设计

```java
System.out.println("1 到 1000 的完数有：");

for(int i=1;i<1000;i++){
    int n=0;
    for(int j=1;j<=i/2;j++){
        if(i % j==0){
            n=n+j;
        }
    }
    if(n==i){
            System.out.print(i+"　");
        }
    }
}
```

9.

```java
import java.util.*;
public class Ma{
    public static void main(String[]args){
        double x=0,y=0;
        System.out.print("输入当月利润（万）：");
        Scanner scanner=new Scanner(System.in);
        x=scanner.nextInt();
        if(x>0&&x<=10){
            y=x*0.1;
        }else if(x>10&&x<=20){
            y=10*0.1+(x－10)*0.075;
        }else if(x>20&&x<=40){
            y=10*0.1+10*0.075+(x－20)*0.05;
        }else if(x>40&&x<=60){
            y=10*0.1+10*0.075+20*0.05+(x－40)*0.03;
        }else if(x>60&&x<=100){
            y=20*0.175+20*0.05+20*0.03+(x－60)*0.015;
        }else if(x>100){
            y=20*0.175+40*0.08+40*0.015+(x－100)*0.01;
        }
        System.out.println("应发放的奖金是"+y+"万");
    }
}
```

10.

```java
import java.util.*;
public class Ma{
    public static void main(String[]args){
        int year,month,day;
        int days=0;
        int a=0;
        int b;
        Q q=new Q();
        do{
            b=0;
            System.out.print("输入年：");
            year=q.f();
            System.out.print("输入月：");
            month=q.f();
            System.out.print("输入天：");
            day=q.f();
            if(year<0||month<0||month>12||day<0||day>31){
                System.out.println("输入错误，请重新输入！");
                b=1;
            }
        }while(b==1);
        for(int i=1;i<month;i++){
            switch(i){
                case 1:
                case 3:
                case 5:
                case 7:
                case 8:
                case 10:
                case 12:
                    days=31;
                    break;
                case 4:
                case 6:
                case 9:
                case 11:
                    days=30;
                    break;
                case 2:
                    if((year % 400==0)||(year % 4==0&&year % 100!=0)){
                        days=29;
                    }else{
                        days=28;
                    }
                    break;
            }
            a+=days;
        }
        System.out.println(year+"－"+month+"－"+day+"是这年的第"+（a+day)+"天。");
    }
}
class Q{
    public int f(){
        int value=0;
        Scanner scanner=new Scanner(System.in);
        value=scanner.nextInt();
        return value;
    }
}
```

11.

```java
import java.util.*;
public class Ma{
    public static void main(String[]args){
        System.out.println("请输入星期的第一个大写字母：");
        Scanner scanner1=new Scanner(System.in);
        String s=scanner1.next();
        char ch=s.charAt(0);
        switch(ch){
            case 'M':
                System.out.println("Monday");
                break;
            case 'W':
                System.out.println("Wednesday");
                break;
            case 'F':
                System.out.println("Friday");
                break;
            case 'T':
                System.out.println("请输入星期的第二个小写字母：");
                Scanner scanner2=new Scanner(System.in);
                String s2=scanner2.next();
                char ch2=s2.charAt(0);
                if(ch2=='u'){System.out.println("Tuesday");}
                else if(ch2=='h'){System.out.println("Thursday");}
                else{System.out.println("无此写法！");}
            };
                break;
            case 'S':
                System.out.println("请输入星期的第二个小写字母：");
                Scanner scanner3=new Scanner(System.in);
                String s3=scanner3.next();
                char ch3=s3.charAt(0);
                if(ch3=='u'){System.out.println("Sunday");}
                else if(ch3=='a'){System.out.println("Saturday");}
                else{System.out.println("无此写法！");}
            };
                break;
            default:System.out.println("无此写法！");
        }
    }
}
```

## 第四章 循环

### 一、单项选择题

1. （ ）表达式不可以作为循环条件。

A. `i++;` B. `i>5;`

C. `b.equals("q");` D. `count==i;`

2. 下列输出结果是（ ）。

![txt14_1.jpg]

A. 0 B. 5 C. 10 D. 其他

3. 下列代码输出是（ ）。

![txt14_2.jpg]

A. `while` 循环执行 10 次 B. 死循环 C. 循环都不执行 D. 循环执行一次

4. 下面有关 `for` 循环的描述正确的是（ ）。

A. `for` 循环体中，可以包含多条语句，但必须用大括号括起来

B. `for` 循环只能用于次数已经确定的

C. 在 `for` 循环中，不能使用 `break` 语句跳出

D. `for` 循环是先执行语句，后判断

5. 执行下面代码结果（ ）。

![txt14_3.jpg]

A. 语法错误，缺少表达式 B. 死循环 C. 程序什么 D. 输出：0

6. 下面代码输出结果是（ ）。

![txt14_4.jpg]

A. 16 B. 12 C. 28 D. 其他

7. 下面程序输出的是（ ）。

![txt14_5.jpg]

A. `i=4` and `j=4` B. `i=5` and `j=5` C. `i=5` and `j=4` D. `i=4` and `j=5`

8. 关于 `for` 循环和 `while` 循环的说法哪个正确？（ ）

A. `while` 循环先判断后执行，`for` 循环先执行后判断

B. `while` 循环判断条件是结果，`for` 循环判断是非

C. 两种循环任何替换

D. 两种结构都有循环体，循环体不能为空

9. 关于选择结构正确？（ ）

A. `if` 语句和 `else` 语句对

B. `if` 语句没有

C. `switch` 结构中 `case` 语句必须用 `break` 

D. `switch` 结构有 `default` 语句

10. `while` 循环和 `do...while` 循环的区别（ ）。

A. 没有区别，这两个效果一样

B. `while` 循环比 `do...while` 循环高

C. `while` 循环先判断后执行，循环体至少一次

D. `do...while` 循环是先执行后判断，至少一次

11. 关于 `for` 循环和 `while` 循环的说法哪个正确？（ ）

A. `while` 循环先判断后执行，`for` 循环先执行后判断。

B. `while` 循环判断条件是结果，`for` 循环判断是非

C. 两种循环任何替换

D. 两种结构都有循环体，循环体不能为空

12. 以下选项中循环合法的是（ ）。

![txt14_6.jpg]

`while(j＜10);`

13. 结构化设计规定的三种结构是（ ）。



A. 输入、处理、输出 B. 树形、网形 C. 顺序、选择、循环 D. 主程序、子程序、函数

14. 下列关于`for`循环和`while`循环的说法哪个是正确的？（ ）

A. `while`循环的操作，`for`循环都能实现

B. `while`循环判断一般是结果，`for`循环判断是非

C. 两种循环任何替换

D. 两种结构都有循环体，循环体不能为空

15. 下面哪一个会导致死循环？（ ）

A. `for(int k=0;k＜0;k++)` B. `for(int k=10;k＞0;k--)` C. `for(int k=0;k＜10;k--)` D. `for(int k=0;k＞0;k++)`

### 二、填空题

1. Java 中有两种控制语句`if`和 ______。

2. 在同一个`switch`语句中，______ 互不相同。

3. Java 语言的控制语句有 3 种，即 ______、循环语句和转移语句。

4. `do－while`循环和`while`循环的区别是 _________。

5. 在循环体中，如果结束本次循环可以用 ______ 语句。

6. 在循环体中，如果跳出循环，结束整个循环 ______ 语句。

7. Java 中的语句可分为方法调用语句、表达式语句、复合语句、`package`语句和`import`语句。

8. `for`循环的表达形式是 ________________。

9. 有如下程序段：

```java
int total=0;
for(int i=0;i＜4;i++){
    if(i==1)continue;
    if(i==2)break;
    total+=i;
}
```

则执行完程序段后`total`的值为 ______。

10. 下面的方法，当输入 2 的时候是 ______。

![txt14_7.jpg]![txt14_8.jpg]

### 三、判断题

1. 数组的遍历是指依次访问每个元素。（ ）

2. `continue`语句只用于循环语句，它的作用是跳出循环。（ ）

3. `continue`语句用在循环语句中，它的作用是终止本次循环，执行下一次。（ ）

4. 数组的排序算法只有冒泡排序这一种。（ ）

5. ______ 的作用是退出当前循环，不再执行语句。（ ）

6. `for`循环语句一般用在循环未知的情况下。（ ）

7. `while`语句的循环体内最多有一条语句。（ ）

8. `switch`表达式中可以接收`int`类型的值。（ ）

9. `do…while`语句与`while`语句完全相同，没有任何区别。（ ）

10. 在`switch`语句中，每个`case`关键字后面有`break`。（ ）

### 四、程序改错题

1. 100 以内所有偶数的和。

![txt14_9.jpg]![txt14_10.jpg]

答案：应该是`for（；i＜10；i++）`

3. 编写一个数的阶乘和。eg. `Sum=1！+2！+3！+4！+5！`

![txt14_11.jpg]

4. 把一个数组里的数字按照从小大的顺序排列出来。

![txt14_12.jpg]![txt14_13.jpg]

5. 输出最小公约数是

![txt14_14.jpg]

### 五、程序填空题

1. 定义一个长度为 5 的字符串数组，并初始化其初值为“open”，“door”，“the”，“open”，“name”；计算该数组中“open”出现的次数，并倒序输出数组元素。

![txt14_15.jpg]

2. 定义一个抽象类`AbstractTest`，其中有一个公共的抽象方法`printMsg()`。

```java
abstract class AbstractTest {
    public abstract void printMsg();
}
```

4.(5)`public void prtMsg()`

![img](img/txt014_31.jpg)

5.(2)`final String classid=null;`

### 六、程序阅读题

1. `x=2`

2. `int y=1`

3. `int y=1`

4. `2.5　4　3　2　1`

5. `3.2　3　5　7`

6. `4.0`

7. `5.abdcbdcb`

### 七、程序设计题

1. `public class Course{`

![img](img/txt014_32.jpg)

2. `public class j_triangle1{`

![img](img/txt014_33.jpg)![img](img/txt014_34.jpg)

3. `public class j_prime{`

![img](img/txt014_35.jpg)

结果是

![img](img/txt014_36.jpg)

4. `public class j99 表{`

![img](img/txt014_37.jpg)![img](img/txt014_38.jpg)

结果是

![img](img/txt014_39.jpg)

5. `public class j100 内质数{`

![img](img/txt014_40.jpg)

结果是

![img](img/txt014_41.jpg)

## 第五章 方法

### 一、单项选择题

1. 在 Java 中，关于构造方法，下列说法错误的是（　）。

A. 构造方法的名称必须与类名相同　B. 构造方法可以带参数

C. 构造方法不可以重载　D. 构造方法绝对不能有返回值

2. 给定 Java 代码如下所示，在`A`处增加下列（　）方法，是对`cal`方法的重载。

```java
public class Test{
public void cal(int x，int y，int z){
}
//A
}
```

A. `public int cal(int x，int y float float z){return 0;}`

B. `public int cal(int x，int y int z){return 0;}`

C. `public void cal(int x，int p;int z){}`

D. `public void cal(int z，int y，int x){}`

3. 下面是`findSum（int m，int n)`方法的定义，方法调用`findSum（1，4)`的返回结果是（　）。

```java
int findSum(int m，int n){
int sum=0;
for(int i=m;i＜=n;i++){
sum+=i;
}
return sum;
}
```

A. 1　B. 4　C. 5　D. 10

4. 为了区分重载多态中同名的不同方法，要求（　）。

A. 采用不同的参数列表　B. 返回值类型不同

C. 调用时用类名或对象名做前缀　D. 参数名不同

5. 可以限制一个方法重载的声明语句是（　）。

A. `final void methoda(){}`　B. `void final methoda(){}`

C. `static void method()`　D. `final abstract void method()`

6. 下列说法正确的是（　）。

A. Java 程序的`main`方法必须写在类里面

B. Java 程序中可以有多个类方法

C. Java 程序中类名必须与文件名一样

D. Java 程序的`main`方法中如果只有一条语句，可以不用`}`括起来

7. Java 中，在如下所示的`Test`类中，共有（　）个构造方法。

```java
public class Test{
private int x;
public Test(){
x=35;
}
public void Test(double f){
this.x=(int)f;
}
public Test(String s){}
}
```

A. 0　B. 1　C. 2　D. 3

8. 在调用方法时，若要使方法改变实参的值，可以（　）。

A. 用基本数据类型作为参数　B. 用对象作为参数

C. A 和 B 都对　D. A 和 B 都不对

9. 类`A`定义如下：

1. `public class A{`

2. `public float f(float a，float b){}`

3.

4. }`

将以下（　）方法插入行三是不合法的。

A. `public float f(float a，float b，float c){}`　B. `pubic float f(float c，float d){}`

C. `public int f(int a，int b){}`　D. `private float f(int a，int b，int c){}`

10. 在 Java 中，一个类可同时定义许多同名的方法，这些方法的形式参数个数、类型或顺序各不相同，传回的值也可以不相同。这种面向对象的程序的特性称为（　）。

A. 隐藏　B. 覆盖

C. 重载　D. Java 不支持此特性

11. 以下关于构造方法的描述错误的是（　）。

A. 构造方法的返回类型只能是`void`型

B. 构造方法是类的一种特殊方法，它的方法名必须与类相同

C. 构造方法的主要作用是完成对对象的初始化

D. 一般在创建新对象时，系统会自动调用构造方法

12. 下面方法中为`public void A（）}`重载方法的是（　）。

A. `void A(){}`　B. `public int A(){}`　C. `public void A(){}`　D. `pubilic int A(int n){}`

13. 下列关于构造方法的叙述中，错误的是（　）。

A. 构造方法与类名相同

B. 构造方法没有返回值，但不用`void`声明

C. 构造方法不可以重载　D. 构造方法只能通过`new`调用

14. 若在某类定义中定义如下方法：`abstract void A（）`；该方法属于（　）。

A. 接口方法　B. 最终方法　C. 抽象方法　D. 空方法

15. 关于下列`A`类，叙述是错误的是（　）。

```java
class A{
A(int m){}
A(double m){}
int A(m){
return 3;
}
void A(double m){}
```

A. `A(int m)`与`A(double m)`是互载方法

B. `int A(m)`与`void A(double m)`是重载

C. 只有方法 D. 类有构造方法

16. 下列叙述正确的是（　）。

A. 成员的名字不可以和局部变量相同

B. 参数的名字可以和方法中声明的变量相同

C. 成员变量没有默认值

17. 下列代码中声明了一个类的方法（　）。

A. `public int A(int i)`　B. `protected A(int i)`　C. `public static A(String s)`　D. `protected static void A(Integer i)`

18. 下列关于静态方法的描述中，错误的是（　）。

A. 在类体中说明静态方法用`static`

B. 静态方法可能处理静态变量或调用方法

C. 静态方法占用内存空间，非静态方法占用空间

D. 静态方法只能调用类名

19. 下列关于方法的描述中，错误的是（　）。

A. 只有成员方法，而返回值

B. 方法可以重载和覆盖

C. 对象作为参数时

D. 返回值是通过`return`实现的

20. 下列关于方法的重载和覆盖的描述中，错误的是（　）。

A. 方法重载在一个类中允许方法参数、个数、顺序不同

B. 方法覆盖是在父类和子类之间方法头相同而方法体不同的

C. 方法重载是在编译时进行

D. 方法覆盖是在运行时

### 二、判断题

1. 在构造方法中调用`super()`语句，则必须成为构造方法的第一条语句。

2. 重写的方法访问权限不能比被写权限高。

3. 类中的实例方法可以用类名直接调用。

4. `this`可以出现在类方法中。

5. 参数的名字可以和方法中声明的变量相同。

6. 对于类中的类方法，在该类加载到内存时，分配了入口地址，从而类方法可以被类创建的任何对象执行，也可以直接通过类名调用。

7. 如果局部变量的名字与成员相同，则成员变量被隐藏，即该变量在这个方法内失效。

8. 在一个抽象类中不能定义构造方法。

9. 在同一个类的构造方法中调用类的构造方法需要使用`this()`的形式，`this()`不能在构造方法的第一行调用。

10. Java 语言中，方法调用一律都是地址的引用。

### 三、填空题

1. 当一个方法不需要返回值，返回类型必须是 ______。

2. Java 类中，如果类的定义者没有定义的任何构造方法，系统将提供一个 ______ 构造方法。默认的构造方法没有 ______，也没有返回值，类 A 的构造方法为 ______。

3. 使用 ______ 运算符和类的 ______ 为声明的对象分配变量，即创建对象。

4. 方法重载时，两个方法的参数不同指的是 ______ 参数的个数不同，或者参数个数相同，但参数列表中对应的某个参数的类型不同 ______。

5. 当类的字节码文件被加载到内存时，类的实例方法不会被分配地址，只有该类 ______ 后，类中的实例方法才被分配了入口地址。

6. 类方法不仅可以被类创建的 ______ 调用，也可以直接通过 ______ 调用。

7. 实例方法中不仅可以操作 ______ 变量，也可以操作 ______ 变量；而类方法不可以操作 ______ 变量。

8. 允许在一个类中编写若干个构造方法，但必须保证它们的 ______ 不同。

9. 如果类中没有编写构造方法，系统会默认该类只有一个构造方法，该默认的构造方法是 ______，且方法体中没有语句。

10. 当`this`关键字出现在实例方法中，`this`就代表 ______。

### 四、程序填空题

1. 填空使输出结果是正确的。

```java
import java.io.RandomAccessFile;
public class Ma{
public static void main(String[])throws Exception{
RandomAccessFile n=new RandomAccessFile("a.txt","rw");
n.writeBoolean(true);
n.writeBoolean(false);
for(int i=1;i<5;i++)
n.writeInt(i);
n.close();
}
```

2. 填空使输出结果是正确的。

```java
class A{
A(int m){}
A(double m){}
int A(int m){
return 3;
}
```

```java
public static void main(String[]args){
    System.out.println(f(10));
}

public static int f(int n){
    int a;
    if(n==1)
        a=1;
    else
        a=n*f(n-1);
    return a;
}
}
```

5. `import java.util.*;`

![img](img/txt015_4.jpg)![img](img/txt015_5.jpg)

6. ```java
class yanghui{
    public static void main(String args[]){
        int i，j;
        int n=10;
        int yanghui[][][];
        System.out.println("杨辉三角形：");
        yanghui=new int[n][];
        for(i=0;i<yanghui.length;i++)
            yanghui[i]=new int[i+1];
        yanghui[0][0]=1;
        for(i=1;i<yanghui.length;i++){
            yanghui[i][0]=1;
            for(j=1;j<yanghui[i].length-1;j++)
                yanghui[i][j]=yanghui[i-1][j-1]+yanghui[i-1][j];
            yanghui[i][yanghui[i].length-1]=1;
        }
        for(i=0;i<yanghui.length;i++){
            for(j=0;j<yanghui[i].length;j++)
                System.out.print(yanghui[i][j]+"");
            System.out.println();
        }
    }
}
```

7. ```java
public class Ma{
    public static void main(String[]args){
        final int a=15;
        int n;
        n=f(a);
        System.out.println("第一天共摘了"+n+"个桃子");
    }
    public static int f(int n){
        int sum=1;
        for(int i=0;i<n-1;i++){
            sum=2*(sum+1);
        }
        return sum;
    }
}
```



8. 

```java
public class A{
    double length；//长
    double width；//宽
    double height；//高
    public A（{//构造函数
        length=0;
        width=0;
        height=0;
    }
    public void setLength(double length){
        this.length=length;
    }
    public double getLength（>(){得到长
        return length;}
    }
    public void setWidth（double width）{//设置宽
        this.width=width;}
    }
    public double getWidth（>(){得到宽
        return width;}
    }
    public void setHeight（double height）{//设置高
        this.height=height;}
    }
    public double getHeight（>(){得到高
        return height;}
    }
    public double volumn（>(){求容积
        double volumnValue;
        volumnValue=length*width*height;
        return volumnValue;}
    }
    public double surfaceArea（>(){求表面积
        double surfaceAreaValue;
        surfaceAreaValue=length*width*2+width*height*2+height*length*2;
        return surfaceAreaValue;
    }
}
```

9. 

```java
public class A{
    public static void main(String[]args){
        for(int i=1;i<10;i++){
            for(int j=1;j<=i;j++){
                System.out.print(j+"*"+i+"="+j*i+"　");
                if(j*i<10){System.out.print("");}
            }
            System.out.println();
        }
    }
}
```

10. `class student`

![img](img/txt015_6.jpg)![img](img/txt015_7.jpg)

## 第六章 类

### 一、选择题

1. 定义类头时，不可能用到的关键字是（　）。

A. `class` B. `private` C. `extends` D. `public`

2. 以下关于类和对象叙述正确的是（　）。

A. 一个类只能有一个对象 B. 一个对象可以属于几个不同的类 C. 对象是类的一个具体实例（实体） D. 一个类中可以有本类的对象

3. 设`A`为已定义的类名，下列声明`A`类的对象`a`的语句中正确的是（　）。

A. `float A a;` B. `public A a=A();` C. `A a=new int();` D. `static A a=new A();`

4. 关于类的静态数据成员和静态成员函数，以下不正确的叙述是（　）。

A. 类的其他函数可以调用类的静态成员函数 B. 类的静态数据成员可以在类的构造函数中使用 C. 类外可以直接引用类的静态数据成员和静态成员函数 D. 类的静态数据成员被类的所有对象共享

5. 设`i`，`j`为类`A`中定义的`int`型变量名，下列`A`类的构造方法中不正确的是（　）。

A. `void A(int k){i=k;}` B. `A(int k){i=k;}` C. `A(int m，int n){i=m;j=n;}` D. `A(){i=0;j=0;}`

6. 有一个类`A`，以下为其构造方法的声明，其中正确的是（　）。

A. `void A(int x){...}` B. `A(int x){...}` C. `a(int x){...}` D. `void a(int x){...}`

7. 下列类的定义，错误的是（　）。

A. `public class A extends Object` B. `final class B` C. `class C` D. `void class D`

8. 下面程序定义了一个类，关于该类正确的是（　）。

A. 该类能调用`ABC()`，方法实例化对象 B. 该类不能继承 C. 该类的方法不能重载 D. 以上说法都不对

9. 下面关于缺省方法的描述正确的是（　）。

A. 缺省方法可以初始化其他方法定义的变量 B. Java 编译器为所有的类创建缺省方法 C. 如果一个类中定义的构造方法都声明了参数，Java 编译器将这个类创建一个缺省方法 D. 当类中没有定义构造方法时，Java 编译器将这个类创建一个缺省方法

10. 在声明类时，关键字`private`、`public`和`protected`出现（　）。

A. 至少一次 B. 至多一次 C. `public`至多一次 D. 任意次数

11. 类可以省略的是（　）。

A. `private` B. `public` C. `protected` D. 任意

12. 下列说法错误的是（　）。

A. 构造函数的名与类同名 B. 在一个类中，只能定义构造函数 C. 创建对象时构造函数自动调用 D. 构造函数没有类型

13. 关于成员函数，以下叙述中正确的是（　）。

A. 成员函数一定是内联函数 B. 成员函数可以重载 C. 构造函数的参数可以默认值 D. 成员函数可以是另一个类的函数

14. 在面向对象的程序中，作用域符（）的功能是（　）。

A. 标识作用域的级别 B. 指出作用域的大小 C. 定义作用域的大小 D. 标识成员函数属于哪个类

15. 静态函数没有（　）。

A. 返回类型 B. 返回值 C. `this`指针 D. 局部变量

### 二、判断题

1. 创建一个类创建一个新的类型，而类在 Java 中属于简单类型。（　）

2. 任何对象只能属于一个类。（　）

3. 构造函数可以有参数，也可以有返回值。（　）

4. 对一个类中数据成员的初始化可以通过构造函数实现。（　）

5. 使用`new`运算符创建数组时必须指定初始值。（　）

6. 一个类的所有对象都有各自的数据成员，共享函数。（　）

7. 一个类中不可以有同名的成员函数。（　）

8. 类成员的定义可以是数据在前，成员函数在后。（　）

9. 静态成员的初始化放在类外进行。（　）

10. 类与对象的关系变量相似。面向对象的方法把数据封装在一起。

### 三、填空题

1. 面向对象的方法把数据封装在一起。

2. 在一个类定义中，用 ______ 描述对象的行为。

3. ______ 用于对对象初始化。

4. 类的构造方法必须和类名 ______。

5. 构造函数 ______ 返回值。

6. 如果一个类定义中已经定义了构造方法，____________ 它定义缺省方法。

7. 类的访问控制有 ______ 和 ______ 两种。

8. 用 ______ 修饰的方法称为静态方法。

9. 变量 ______（选“能”或“不能”）做`private`变量。

10. 使用静态成员都能 ______ 做前缀。

11. 方法中 ______（选“能”或“不能”）有`this`引用。

12. 类的私有属性和私有方法 ______（选“能”或“不能”）被子类访问。

13. 如果子类中的变量名与父类中的变量完全一样，则子类中的变量 ______ 了父类的同名变量。

14. 根据结构运行环境，Java 程序分为两类：______、______。

15. ______ 是 Java 程序的直接或间接父类，也是所有类的。

### 四、程序填空题

1. 下面是一个类的定义，请将其补充完整。

![img](img/txt016_4.jpg)![img](img/txt016_5.jpg)

2. 下面是一个类的定义，请将其补充完整。

![img](img/txt016_6.jpg)

3. 下面程序的功能是通过调用`max()`求给定的数的最大值，请将其补充完整。

![img](img/txt016_7.jpg)

4. 下面是一个类的定义，请将其补充完整。

![img](img/txt016_8.jpg)![img](img/txt016_9.jpg)

5. 下面程序的功能是通过调用`max()`求给定的整数的最大值，请将其补充完整。

![img](img/txt016_10.jpg)

### 五、程序改错

1. 请改正程序中的错误，使它正确。

【操作说明】如下 Java 文件中`/*s*/`行有语法错误，不得动结构，不得增行。

【运行结果】50

【程序代码】

![img](img/txt016_12.jpg)

2. 请改正程序中的错误，使它得到的结果。

【操作说明】如下 Java 文件中`s"`有语法错误，不得动结构，不得增行。

【程序代码】

```java
class Test{
    private static void printArray(int[] arr){
        for(i=0;i<arr.length;i++)
            System.out.print(arr[i]+"");
        System.out.println("\n");
    }
    private static void changeValue(int value){
        value*=2;
    }
    private void changeValue(int[] arr){/*s*/
        for(i=0;i<arr.length;i++)
            arr[i]*=2;
    }
    public static void main(String[]args){
        int[] arr={1,2,3,4,5};
        changeValue(arr[0]);
        printArray(arr);
        changeValue(arr);
    }
}
```

3. 请改正程序中的错误，使它得到的结果。

【操作说明】如下 Java 文件中`/*s*/`行有语法错误，不得动结构，不得增行。

【程序代码】

![img](img/txt016_13.jpg)

### 六、程序阅读

1. 下面程序的运行结果是。

![img](img/txt016_14.jpg)

2. 下面程序的运行结果是。

```java
class Sum{
    public static void main(String[]args){
![img](img/txt016_15.jpg)
    }
}
```

3. 下面程序的运行结果是。

![img](img/txt016_16.jpg)

4. 下面程序的运行结果是。

![img](img/txt016_17.jpg)![img](img/txt016_18.jpg)

5. 下面程序的运行结果是。

![img](img/txt016_19.jpg)

`C.zhang` instanceof `Student` 的值是`false`

`D.zhang` instanceof `UniverStudent`是`false`

5. 将下列代码放到程序中将导致编译错误的是（　）。

A. `public void sum(){}`

B. `public float sum(){return 4.0f}`

C. `public void sum(double d){}`

D. `public double sum(float d){return 4.0f}`

代码如下：

![img](img/txt017_1.jpg)![img](img/txt017_2.jpg)

```java
public class B extends A{
    // 【代码】
}
```

6. Java 中访问限定符不包括（　）。

A. `public` B. `private` C. `default` D. `final`

7. 定义一个名为`MyClass`的类，并且该类可被一个工程中的所有类访问，该类的正确声明为（　）。

A. `private class MyClass extends Object`

B. `class MyClass extends Object`

C. `public class MyClass`

D. `private class MyClass extends Object`

8. 如果子类中的方法`mymethod()`覆盖了父类中的方法`mymethod()`，假设父类方法头部定义如下：`void mymethod(int a)`，则子类方法的定义不合法的是（　）。

A. `public void mymethod(int a)` B. `protected void mymethod(int a)`

C. `private void mymethod(int a)` D. `void mymethod(int a)`

9. 下列代码标注中，错误的一个是（　）。

```java
abstract class speak{
    A. `protected void speakHello(){}` B. `public abstract static void cry();`
    C. `static int f(){return 0;}` D. `abstract float g();`
}
```

10. 下列程序中注释的代码错误（无法通过编译）的是（　）。

```java
abstract class P{
    A. `abstract float getFloat();`
    B. `Void f(){}`
    ![img](img/txt017_3.jpg)
    C. `private float getFloat(){}`
    D. `return m;`
}
```

### 二、填空题

1. Java 中提供了四种访问控制符，分别是`public`、`private`、`protected`、`default`。

2. Java 中用`extends`关键字指明继承关系，用`implements`关键字指明对接口的实现。

3. `this`代表了`当前对象`的引用，`super`表示的是当前对象的`父`对象。

4. 关键字`final`表明一个对象或变量在初始化后不能被修改。

5. 面向对象程序的主要特征是 ________________________________________________。

6. 在 Java 语言中有一个类是所有类和接口的父类，这个类的名称是`Object`。

7. 在子类中使用关键字`super`做前缀可调用被子类覆盖的父类中的方法。

8. 通过`.`运算符就能实现对对象成员变量的访问和对象方法的调用。

9. 类的构造方法的名称必须与`类名`相同。

10. 类方法只能处理用关键字`static`修饰的对象。

### 三、判断题

1. 子类可以有多个父类。（　）

2. `java.lang`包中的`Object`类是所有其他类的祖先类。（　）

3. 如果子类和父类不在同一包中，子类可以继承父类的友好变量。（　）

4. 子类成员变量与父类成员变量同名时可以隐藏子类继承的成员变量。（　）

5. 父类的`final`方法可以被子类重写。（　）

6. 类有两种重要成员：成员变量和方法。（　）

7. `instanceof`是双目运算符，左面操作元是对象，右面操作元是类。（　）

8. 类不能通过重写来隐藏已继承的方法。（　）

9. 对于`abstract`方法，只允许声明，不允许实现（没有方法体）。（　）

10. 上转型对象能操作子类新增的成员变量。（　）

### 四、程序填空题

1. 下面是一个类的定义，完成程序填空。

![img](img/txt017_4.jpg)

2. 已知`B`重写`A`的方法，按要求填空。

![img](img/txt017_5.jpg)![img](img/txt017_6.jpg)

### 五、程序阅读题

1. 现有类说明如下，请回答问题。

![img](img/txt017_7.jpg)

问题：

（1）`A`和`B`是什么关系？

（2）`A`和`B`都定义了`str`属性和方法`toString()`，这种现象称为什么？

（3）若`a`是`A`的对象，则`a.toString()`的返回值是什么？

（4）若`b`是`B`的对象，则`b.toString()`的返回值是什么？

2. 阅读程序，回答问题。

![img](img/txt017_8.jpg)![img](img/txt017_9.jpg)

问题：

（1）这是哪一类程序？

（2）`A`和`B`是什么关系？

（3）按程序格式写出结果。

3. 现有类说明如下，回答问题：

![img](img/txt017_10.jpg)

问题：

（1）`B`能继承`A`的属性？

（2）若`b`是`B`的对象，则`b.getB()`的返回值是什么？

（3）若`b`是`B`的对象，则`b.getA()`的返回值是什么？

（4）`A`和`B`都定义了`x`属性，这种现象称为什么？

4. 请说出`E`类中【代码一】和【代码二】的输出。

![img](img/txt11.jpg)

【代码一】：【代码二】：

### 六、程序设计题

1. 编写一个 Java 应用程序，该程序包括三个类：`Animal`类、`People`类和主类`E`。要求如下：

（1）`Animal`类中有构造方法：`Animal(String s)`，并且有个`public void speak()`方法，在`speak`方法中输出“咿呀……”。



（2）`People`类是`Animal`的子类，在`People`类中重写`speak()`，在`speak`方法中输出“小样的，不错！”。

（3）`People`类中新增方法`void think()`，在`think`方法中输出“说话！认真思考！”。

（4）在主类`E`的`main`方法中创建`Animal`类与`People`类的测试这两个功能。

2. 设计一个声音器，它可以模拟许多动物的声音，要求如下：

（1）编写抽象类`Animal`，有两个抽象方法`cry()`和`Name()`。

（2）编写`Simulator`类，该类有一个`playSound(Animal animal)`方法。

（3）编写`Animal`类的子类：`Dog`和`Cat`。

（4）编写主类`Application`。

# 八章 数组和向量

1. 关于数组，下列说法中不正确的是（　）。

A. 数组是最简单的复合类型，是一系列数据的集合

B. 数组元素可以是基本类型、或其他数组

C. 定义数组必须分配内存

D. 一个数组中所有元素都相同类型

2. 设有数组定义语句：`int a[]={1,2,3};`对此语句的叙述的是（　）。

A. 定义了一个名为`a`的一维数组 B. `a`数组有 3 个元素 C. `a`元素的下标为 1～3 D. 数组中每个元素都是整数

3. 执行语句：`int[] x=new int[20];` 后，下面说法正确的是（　）。

A. `x[19]`为空 B. `x[19]`未定义 C. `x[19]`为`0` D. `x[0]`为空

4. 下面代码运行后的输出结果为（　）。

![img](img/txt018_1.jpg)

A. `true` B. `false` C. 编译错误 D. `100`

5. 给出下面代码，关于该程序说法正确的是（　）。

![img](img/txt018_2.jpg)

A. 编译时将产生错误 B. 编译时正确，运行时将产生错误 C. 输出零 D. 输出空

6. 关于以下代码段的说法正确的是（　）。

(1) `String s="abcde";`

(2) `StringBuffer s1=new StringBuffer("abcde");`

(3) `if(s.equals(s1))`

(4) `s1=null;`

(5) `if(s1.equals(s))`

(6) `s=null;`

A. 第（1）行编译错误，`String`的构造器必须明确调用 B. 第（3）行编译错误，因为`s`与`s1`有不同的类型 C. 编译成功，但执行时在第（5）行有异常抛出 D. 编译成功，过程中也没有异常抛出

7. 下列程序段执行后的结果是（　）。

![img](img/txt18_3.jpg)

A. `aceg` B. `ACEG` C. `abcdef` D. `abcd`

8. 应用程序的`main`方法中有以下语句，则输出的结果（　）。

![img](img/txt018_4.jpg)![img](img/txt018_5.jpg)

A. `true false` B. `false true` C. `true true` D. `false false`

9. 应用程序的`main`方法中有以下语句，则输出的结果（　）。

![img](img/txt018_5.jpg)![img](img/txt018_6.jpg)

A. `32` B. `11` C. `2` D. `3`

10. 应用程序的`main`方法中有以下语句，则执行后输出是（　）。

![img](img/txt018_7.jpg)

A. `125` B. `5` C. `98` D. `16`

11. `Test.java`编译运行后的结果是（　）。

![img](img/txt018_8.jpg)

A. `java2` B. `2` C. 没有输出 D. `java`

12. 关于下面的程序`Test.java`说法的是（　）。

![img](img/txt018_9.jpg)

A. `3` B. `10`

13. 数组定义定义，，数组的输出是（　）。

`int a[]={1,2,3};`![img](img/txt017_10.jpg)

A. 定义了一个名为`a`的一维数组 B. `a`数组有 3 个元素 C. `a`元素的下标为 1～3 D. 数组中每个元素都是整数

14. 初始化错误的（　）。

`char str[]="hello";` B. `char str[]='hello'` C. `char str[]={'h','e','l','l','o'}`

15. 错误的（　）。

`int a[]={10};`

### 2. helloWorld

### 3. 【结果 1】ABCDEFG

【结果 2】ABCDEFGEF

### 4. 转置之后的数组，6 5 4 3 2 1

### 5. i= (3)

### 七、程序设计题

1. 

```java
int[] a={12, 34, 563, 2, 45, 778, 554, 4421, 4456, 6786};
Arrays.sort(a);
int min=a[0];
int max=a[a.length-1];
System.out.println("数组中最小的数为："+min+"，最大的数为："+max);
```

2. `import java.util.Random;`

![img](img/txt018_33.jpg)

3. 

```java
public class javaNineDay{
```

![img](img/txt018_34.jpg)![img](img/txt018_35.jpg)

4. 

```java
public class javaSevenDayLianXi{
```

![img](img/txt018_36.jpg)

5. 

```java
import java.util.Scanner;
```

![img](img/txt018_37.jpg)![img](img/txt018_38.jpg)

# 第九章 布局管理

### 一、选择题

1. 关于`AWT`和`Swing`说法正确的是（ ）。

A. `Swing`是`AWT`的子类

B. `AWT`在不同操作系统中显示相同的风格

C. `AWT`不支持事件模型

D. `Swing`组件可直接添加到顶级容器中

2. 能将容器划分为“East”、“South”、“West”、“North”、“Center”五个区域的布局管理的是（ ）。

A. `BoxLayout` B. `BorderLayout` C. `GridLayout` D. `CardLayout`

3. `JFrame`对象默认的布局管理器是（ ）。

A. `FlowLayout` B. `BorderLayout` C. `GridLayout` D. `null`

4. 下列关于组件类的描述中，错误的是（ ）。

A. 组件类中包含了文本组件类（`TextComponent`）和菜单组件类（`MenuComponent`）

B. 标签（`JLabel`）和按钮（`JButton`）是组件类（`Component`）的子类

C. 面板（`JPanel`）和窗口（`Window`）是容器类（`Container`）的子类

D. 菜单（`JMenu`）和菜单条（`JMenuBar`）是`JComponent`类的子类

5. 下列关于菜单和对话框的描述中，错误的是（ ）。

A. `JFrame`容器是可以容纳菜单组件的容器

B. 菜单条中可包含若干个菜单，菜单中又可包含若干菜单项，菜单项中还可包含菜单子项

C. 对话框内可以含有菜单条

D. `JFrame`可作为程序的底层容器，但是对话框不能作为程序的底层容器

6. 在对下列语句的解释中，错误的是（ ）。

```java
button.addActionListener(this);
```

A. `button`是某种事件对

B. `this`表示当前容器

C. `ActionListener`是动作事件的监听者

D. 该语句的功能是将`button`对象注册为`this`对象的监听者

7. 在下列各种容器中，最简单的无边框的又不能移动和缩放的只能包含在另一种容器中的容器是（ ）。

A. `JScrollPane` B. `JDialog` C. `JFrame` D. `JPanel`

8. 在编写`Java Applet`程序时，若需要对发生的事件做出响应和处理，一般需要在程序的开头写上（ ）语句。

A. `import java.awt.*` B. `import java.swing.*`

C. `import java.io.*` D. `import java.awt.event.*`

9. 在`Java`图形用户界面编程中，若显示一些不需要修改的文本信息，一般是使用（ ）类的对象来实现。

A. `Label` B. `Panel` C. `TextArea` D. `TextField`

10. 以下关于框架描述中，错误的是（ ）。

A. 框架是`Swing`的顶级容器组件

B. 框架是一个图形界面程序的主窗口

C. 框架是一个程序的主窗口，每个具有图形界面的程序都至少有一个框架

D. 内部框架也是顶级容器组件

11. 下列各类创建的对象可以触发`ActionEvent`事件的是（ ）。

A. `java.awt.Button`类 B. `java.lang`包的子类

C. `java.util.Date`类 D. `java.IO`类

12. 在基于`Swing`的图形用户界面设计中，面板属于（ ）。

A. 顶层容器 B. 中间级容器 C. 底层容器 D. 原子组件

13. 在`Swing`中，设置组件的边框的方法是（ ）。

A. 通过根窗口的`setBorder`函数设置每个组件的边框

B. 通过内容窗口的`setBorder`函数设置每个组件的边框

C. 通过组件的`setBorder`函数设置每个组件的边框

D. 通过框架的`setBorder`函数设置每个组件的边框

14. 下面不属于`MVC`结构的内容的是（ ）。

A. 模型 B. 视图 C. 控制器 D. 窗口

15. 下列 own 不属于`KeyListener`接口处理键盘事件的方法的是（ ）。

A. `keyPresed()` B. `keyTyped()`

C. `keyReleased()` D. `addKeyListener()`

16. 下面属于`ActionListener`接口里的方法是（ ）。

A. `getSource()` B. `getActionCommand()`

C. `setCommand()` D. `actPerformed()`

17. 下面不属于事件处理的是（ ）。

A. 事件源 B. 监听器 C. 处理接口 D. 对话框

18. 对于`Swing`基本控件，若要使两个框对象之间具有斥的关系，需要（ ）。

A. 创建两个框对象时定义相同的名

B. 将两个框对象放在面板上

C. 定义一个`ButtonGroup`对象，将两个框对象加到`g`中

D. 让两个框排成一行或列

19. 下列叙述中正确的是（ ）。

A. 不是任何组件都可以触发`MouseEvent`

B. 处理`WindowEvent`的接口是`FocusListener`

C. `java.awt.event.MouseAdapter`类实现了`MouseListener`

D. 可以向`JFrame`添加

20. 下面叙述正确的是（ ）。

A. `JButton`对象可以调用`ActionListener`方法将没有`ActionListener`接口的类注册为事件源

B. 创建对话框时，`showDialog()`方法返回对话框对象触发`ItemEvent`

C. 将实现`ItemListener`的实例注册为事件源

D. `KeyEvent`事件监听器必须实现`KeyListener`

21. 在`Swing`中，调整窗口的方法是（ ）。

A. `setBounds()` B. `setSize()`

C. `setResizable()` D. `setLocation()`

22. 下面属于窗格的是（ ）。

A. `JPanel` B. `JScrollPane` C. `JSplitPane` D. `LayeredPane`

23. `Window`是独立的，两种形式是（ ）。

A. `Frame`和`Dialog` B. `Panel`和`Box`

C. `Container`和`Component` D. `BorderLayout`和`Container`

24. `Java`集合中定义了许多方法。下列选项不是定义的是（ ）。

A. `int size()` B. `boolean contains(c)`

C. `compareTo(obj)` D. `boolean remove(obj)`

25. 下面说法正确的是（ ）。

A. `BoxLayout`类可以创建一个布局对象，称为合适布局

B. `CardLayout`是使用较多的布局，其基本布局是把容器划分成若干行的

C. `BorderLayout`是`Window`型容器的默认布局

D. `FlowLayout`是`JPanel`型容器的默认布局

### 二、填空题

1. 图形界面技术经历了两个阶段，分别通过`AWT`开发包开发包来实现。

2. `Window`有两种形式 ______

3. 容器里的组件的位置和大小是由 ______ 决定的。

4. 框架的布局管理器是 ______。

5. ______ 含有用户文本的文字框，一个确认和取消按钮，是有模式的对话框。

6. ______ 布局管理器是容器中各个件呈网格布局，平均占据。

7. 可以用 ______ 创建文本框，使用 ______ 创建文本区。

8. 使用 ______ 处理鼠标、选择框、下拉列表触发 ______ 事件。

9. 创建对话框与窗口类似，通过 ______。

10. ______ 由一个面板、一个内容面板和一个选择的菜单条组成。

11. ______ 隐藏当前窗口，并且释放资源。

12. ______ 组件提供了一个简单的“列表中”输入。

13. 为了使诸如按钮和文本框等组件能够工作，我们必须实现 ______。

14. 一个容器各个组件的摆放称为 ______。

15. 图形程序一般由 ______ 完成功能。

### 三、判断题

1. 容器是用来组织界面成分和元素的单元，不能嵌套容器。（ ）

2. 每个事件类对应一个监听器接口，每一个监听器接口都有适配器。（ ）

3. 使用`BorderLayout`布局管理器时，GUI 组件可以任何顺序添加到面板上。（ ）

4. 对于有监听器的`JTextField`文本框，如果文本框处于活动状态（有焦点）时，用户即使不输入文本，只要按回车键（`Enter`）也可以触发`ActionEvent`事件。（ ）

5. 使用`BorderLayout`布局的容器被划分为 5 个区域，而使用`FlowLayout`布局的容器最多可以添加 5 个组件。（ ）

### 四、编程题

1. 编写如图所示的窗口。

![img](img/txt019_1.jpg)

2. 如下所示，编写一个程序实现它。

![img](img/txt019_2.jpg)

3. 用`GridLayout`布局编写下图所示的程序。

![img](img/txt019_3.jpg)

4. 编写一个程序，要求用户在文本框中只能输入数字，输入非数字字符弹出对话框。

5. 编写一个程序，要求实现下图所示的功能。

![img](img/txt019_4.jpg)

6. 编写一个程序，实现下图的功能。

![img](img/txt019_5.jpg)

7. 编写一个登录界面，要求：用户名为空时，弹出用户名为空的对话框，密码为空时，弹出密码为空的对话框，密码错误时，弹出失败的对话框，用户名和密码均时，弹出成功的对话框。

![img](img/txt019_6.jpg)

8. 编写一个程序，在屏幕上的随机位置画随机尺寸的圆形和矩形。

![img](img/txt019_7.jpg)

9. 编写一个日期程序，要求如下：用户输入一个月份，屏幕上输出这个月的历，每一行，从星期开始到星期结束。用户输入一个日期，屏幕上回答星期几。用户输入两个日期，计算日期之间差多少天。

10. 编写一个程序，实现下图所示的界面。

![img](img/txt019_8.jpg)

### 习题答案

一、选择题 1~5 BAD，6~10 DAD，11~15 ABCDD，16~20 DCA

二、填空题

1. `Swing`

2. `Frame`（`Dialog`）

3. 布局管理器

4. `BorderLayout`

5. 输入对话框

6. `GridLayout`

7. `JTextField`、`TextArea`

8. `MouseListener`、`ItemEvent`

9. `JDialog`

10. `Frame`

11. `DISPOSE_ON`

12. `JComboBox`

13. 监听器

14. 布局

15. 组件

三、判断题

1. ×

2. ×

3. √

4. √

5. ×

四、程序题

1. `import java.awt.*`

2. `swing.*`

3. `import java.util.Calendar`

4. `import java.awt.*`

5. `import java.swing.*`

6. `import java.util.*`

7. `start()`

8. `Throwable`

9. `throw`

10. `BorderLayout`

# 十章 小应用程序、线程

### 一、选择题

1. 下列关于`Applet`的说法正确的是（ ）。

A. `Applet`可以创建一个布局

B. `CardLayout`是使用较多的布局，其基本布局是把容器划分成若干行的。

2. 图形界面技术经历了两个阶段，分别通过`AWT`开发包和 ______ 包来实现。

A. `Window`有两种形式 ______

B. `Frame`和`Dialog`

3. 容器里的组件的位置和大小是由 ______ 决定的。

A. `Frame`和`Dialog`

B. `Container`和`Component`

4. 框架的布局管理器是 ______。

A. `FlowLayout`



### 一、单项选择题

13. 线程在生命周期中要经历五种状态，若线程当前是新建状态，则它可以到达的下一个状态是（　）。

    A. 运行状态  B. 可运行状态  C. 阻塞状态  D. 终止状态

14. 下列关于 Java 多线程并发控制机制的叙述中，错误的是（　）。

    A. Java 中没有提供检测与避免死锁的专门机制，但应用程序可以采用某些策略防止死死锁的发生

    B. 共享数据的访问权限都必须定义为`private`

    C. Java 中对共享数据操作的并发控制是采用加锁技术

    D. 线程之间的交互，提倡采用`suspend()`/`resume()`方法

15. 以下关键字可以对对象加互斥锁的是（　）。

    A. `transient`  B. `serialize`  C. `synchronized`  D. `static`

### 二、填空题

1. `Applet`生命周期方法有`init()`、______、`stop()`和`destroy()`。

2. 与显示相关的`Applet`方法有 ______、`repaint()`和`update()`。

3. 异常是在程序编译或运行中所发生的可预料或不可预料的异常事件，出现在编译阶段的异常，称之为 ______，出现在运行阶段的异常，称之为 ______。

4. 根据异常的来源，可以把异常分为两种类型 ______ 和 ______。

5. 所有的 Java 异常类都是系统类库中的 ______ 类的子类。

6. 一个`try`块后面可能会跟着若干个 ______，每个 ______ 块都有一个异常类名作为参数。

7. 每个`Java`程序都有一个缺省的主线程，对于`Application` 的程序来说，主线程是方法 ______ 执行的线程。

8. Java 语言使用 ______ 类及其子类的对象来表示线程，新建的线程在它的一个完整的生命周期中通常要经历 ______ 等五种状态。

9. ______ 方法将启动线程对象，使之从新建状态转入就绪状态并进入就绪队列排队。

10. 在`Java`中，实现同步操作的方法是在共享内存变量的方法前加 ______ 修饰符。

11. 线程的优先级是一个在 ______ 到 ______ 之间的正整数。

12. `Thread`类中代表最高优先级的常量是 ______，表示最低优先级的常量是 ______。

### 三、判断题

1. `Applet`的执行离不开一定的 HTML 文件。（　）

2. `Applet`可以运行本地机器上的可执行程序。（　）

3. `Java Applet`不能够存取客户机磁盘上的文件。（　）

4. `Applet`可以运行在浏览器中。（　）

5. `Applet`是一种特殊的`Panel`，它是`Java Applet`程序的最外层容器。（　）

6. `Java Applet`是由独立的解释器程序来运行的。（　）

7. `Java Applet`只能在图形界面下工作。（　）

8. 捕获异常`try`语句后面通常跟有一个或多个`catch()`方法用来处理`try`块内生成的异常事件。（　）

9. 使用`try-catch-finally`语句只能捕获一个异常。（　）

10. `try-catch`语句不可以嵌套使用。（　）

11. `Error`类所定义的异常是无法捕获的。（　）

12. 当一个方法在运行过程中产生一个异常，则这个方法会终止，但是整个程序不一定终止运行。（　）

13. `Java`线程有五种不同的状态，这五种状态中的任何两种状态之间都可以相互转换。（　）

14. 使用`Thread`子类创建线程的优点是可以在子类中增加新的成员变量，使线程具有某种属性，也可以在子类中新增加方法，使线程具有某种功能。但是，`Java`不支持多继承，`Thread`类的类不能再扩展其他的类。（　）

15. 当线程类所定义的`run()`方法执行完毕，线程的运行就会终止。（　）

### 四、程序改错题

1. 找出以下程序中的九处语法错误并改正。

![img](img/txt020_3.jpg) 

![img](img/txt020_4.jpg)

### 五、程序填空题

1. 下面程序抛出了一个“异常”并捕捉它。请在横线处填入适当内容完成程序。

![img](img/txt020_5.jpg)

2. 下面程序定义了一个字符串数组，并打印输出，捕获数组超越界限异常。请在横线处填入适当的内容完成程序。

![img](img/txt020_6.jpg)

![img](img/txt020_7.jpg)

### 六、程序阅读题

1. 阅读下面程序回答问题。

![img](img/txt020_8.jpg)

（1）从键盘输入 10，回车后输出的结果如何？

（2）从键盘输入 exit，回车后程序能正确执行吗？为什么？

2. 阅读程序，并写出程序运行结果。

![img](img/txt020_9.jpg)

### 七、程序设计题

1. 从键盘输入 10 个整数，存储到一个数组中，然后找出其中最大值和最小值，并给出他们在数组中的下标。

2. 建立一个班级下拉式列表，列表项中有 101 班、102 班、103 班、104 班和 105 班，当点击某个选项时，将这个选项的内容复制到按钮文本中。要求字体大小为 24 号，颜色为红色。

3. 编写一个`Java`应用程序，从键盘读取用户输入两个字符串，并重载 3 个函数实现这两个字符串的拼接、整数相加和浮点数相加。要进行异常处理，对输入的不符合要求的字符串向用户提示，不能使程序崩溃。

4. 输入某年某月某日，判断这一天是这一年的第几天？

5. 输出九九乘法口诀。

### 习题参考答案

### 一、单项选择题

1～5 ABCBD; 6～10 DAABA; 11～15 BABDC

### 二、填空题

1. `start()`

2. `paint()`

3. 编译时异常、用户自定义异常

4. `Exception`

5. `catch`块、`catch`

6. `main()`

7. `Thread`

8. 新生、就绪、运行、阻塞和死亡

9. `start()`

10. `synchronized`

11. 1, 10

12. `MAX_PRIORITY`, `MIN_PRIORITY`

### 三、判断题

1.√, 2.×, 3.√, 4.√, 5.√, 6.×, 7.√, 8.√, 9.×, 10.×, 11.√, 12.√, 13.×, 14.√, 15.√

### 四、程序改错题

(1) `class UserException implements Exception`

(2) `public UserException(String info)`

(3) `this.info = info;`

(4) `public void callException() throws UserException`

(5) `throw new UserException("callException");`

(6) `public static void main(String args)`

(7) `UserException ue = new UserException();`

(8) `catch (Exception e)`

(9) `finally`

### 五、程序填空题

1. `catch (IllegalAccessException e)`

2. `try`, `catch`

### 六、程序阅读题

1. 100，不能退出，输入`exit`会触发`java.lang.NumberFormatException`。

2. A, D, C

### 七、程序设计题

1. `import java.io.BufferedReader;`

2. `import java.awt.*;`

3. `import java.io.*;`

4. `import java.util.*;`

5. `public class Zhong7 extends Applet implements Runnable { ... }`

```java
lastxs=xs;lastys=ys;

lastxm=xm;lastym=ym;

lastxh=xh;lastyh=yh;

lastdate=today;

currentDate=null;

}

//applet 的启动方法
public void start()
{
    timer=new Thread(this);
    timer.start();
}

//applet 的停止方法
public void stop()
{
    timer=null;
}

//线程的 run 方法
public void run()
{
    Thread me=Thread.currentThread();
    while(timer==me){
        try{
            Thread.currentThread().sleep(1000);
        }
        catch(InterruptedException e){
        }
        repaint();
    }
}
```

## 实验八 Java 与数据库的连接

![img](img/txt029_1.jpg)![img](img/txt029_2.jpg)![img](img/cov002_1.jpg)
