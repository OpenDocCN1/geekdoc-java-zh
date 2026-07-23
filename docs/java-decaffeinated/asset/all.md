![](Images/cover00457.jpeg)

# Java Decaffeinated

# A Simple Introduction to Java

## Pranav Ramesh

# Contents

*   [Chapter 1 Getting Started](#part0001.xhtml_cid1)
*   *   [1.1 Installing our IDE](#part0001.xhtml_aid-UGI9)
    *   [1.2 Writing your first code](#part0001.xhtml_aid-UGL2)
    *   [1.3 Comments](#part0001.xhtml_aid-UH5S)
    *   [1.4 Reserved keywords](#part0001.xhtml_cid5)
    *   [1.5 Conventions used in this book](#part0001.xhtml_aid-UHBG)
    *   *   [1.5.1 Images](#part0001.xhtml_aid-UHBL)
        *   [1.5.2 Tables](#part0001.xhtml_uid27)
        *   [1.5.3 Inline code and code fences](#part0001.xhtml_uid28)
        *   [1.5.4 Notes](#part0001.xhtml_sec-notes)
        *   [1.5.5 Examples, exercises, and problems](#part0001.xhtml_uid34)
    *   [1.6 Review](#part0001.xhtml_cid7)
*   [Chapter 2 Types](#part0002.xhtml_cid8)
*   *   [2.1 Numbers](#part0002.xhtml_aid-1T156)
    *   *   [2.1.1 Types of Java integers](#part0002.xhtml_aid-1T15K)
        *   [2.1.2 Integer math operations](#part0002.xhtml_aid-1T18S)
        *   [2.1.3 Working with decimals](#part0002.xhtml_uid49)
        *   [2.1.4 Decimal operations](#part0002.xhtml_aid-1T1K6)
        *   [2.1.5 The `Math` class](#part0002.xhtml_aid-1T1RR)
    *   [2.2 Text](#part0002.xhtml_aid-1T25H)
    *   *   [2.2.1 Characters](#part0002.xhtml_uid64)
        *   [2.2.2 Create a string](#part0002.xhtml_uid65)
        *   [2.2.3 String concatenation](#part0002.xhtml_uid70)
        *   [2.2.4 Find the length of a string](#part0002.xhtml_uid74)
        *   [2.2.5 Special Characters and Escape Sequences](#part0002.xhtml_aid-1T2IF)
    *   [2.3 Logic](#part0002.xhtml_aid-1T2T3)
    *   *   [2.3.1 Printing `true` and `false`](#part0002.xhtml_uid91)
        *   [2.3.2 Relational Operators](#part0002.xhtml_aid-1T30S)
        *   [2.3.3 Logical Operators](#part0002.xhtml_uid100)
        *   [2.3.4 Using `not`](#part0002.xhtml_uid102)
        *   [2.3.5 Using `and`](#part0002.xhtml_aid-1T3BJ)
        *   [2.3.6 Using `or`](#part0002.xhtml_aid-1T3FM)
    *   [2.4 Review](#part0002.xhtml_cid12)
    *   [2.5 Problems](#part0002.xhtml_cid13)
*   [Chapter 3 Variables](#part0003.xhtml_cid14)
*   *   [3.1 Handling variables](#part0003.xhtml_aid-2RHOL)
    *   *   [3.1.1 Creating and using variables](#part0003.xhtml_aid-2RHOP)
        *   [3.1.2 Modifying variables](#part0003.xhtml_aid-2RIKT)
        *   [3.1.3 Shorthand operators](#part0003.xhtml_aid-2RIUQ)
        *   [3.1.4 Immutable versus mutable](#part0003.xhtml_uid166)
    *   [3.2 Variable scope](#part0003.xhtml_aid-2RJEE)
    *   [3.3 Type casting](#part0003.xhtml_aid-2RJJ9)
    *   *   [3.3.1 Widening conversions](#part0003.xhtml_aid-2RJJR)
        *   [3.3.2 Narrowing conversions](#part0003.xhtml_aid-2RJQJ)
    *   [3.4 Review](#part0003.xhtml_cid18)
*   [Chapter 4 Procedural Decomposition](#part0004.xhtml_aid-3Q282)
*   *   [4.1 Implement static methods](#part0004.xhtml_aid-3Q2FD)
    *   [4.2 Flow of control](#part0004.xhtml_cid21)
    *   [4.3 Creating methods with parameters](#part0004.xhtml_aid-3Q396)
    *   [4.4 Returning values](#part0004.xhtml_aid-3Q3MQ)
    *   *   [4.4.1 Specifying the return type](#part0004.xhtml_uid202)
        *   [4.4.2 The `return` statement](#part0004.xhtml_aid-3Q40S)
    *   [4.5 Method Overloading](#part0004.xhtml_aid-3Q4GH)
    *   [4.6 Review](#part0004.xhtml_cid25)
*   [Chapter 5 Conditionals](#part0005.xhtml_cid26)
*   *   [5.1 The `if` statement](#part0005.xhtml_aid-4OIS1)
    *   [5.2 The `else` clause](#part0005.xhtml_aid-4OJAU)
    *   [5.3 The `else if` clause](#part0005.xhtml_aid-4OJO5)
    *   [5.4 Nested conditionals](#part0005.xhtml_aid-4OKII)
    *   [5.5 Review](#part0005.xhtml_cid31)
*   [Chapter 6 Loops](#part0006.xhtml_aid-5N3C2)
*   *   [6.1 `for` loops](#part0006.xhtml_aid-5N3H2)
    *   [6.2 `while` loops](#part0006.xhtml_aid-5N3TR)
    *   [6.3 `do while` loops](#part0006.xhtml_aid-5N4JJ)
    *   [6.4 Nested loops](#part0006.xhtml_aid-5N4R9)
    *   [6.5 Interrupting loops](#part0006.xhtml_aid-5N655)
    *   *   [6.5.1 The `break` statement](#part0006.xhtml_aid-5N65E)
        *   [6.5.2 The `continue` statement](#part0006.xhtml_uid342)
    *   [6.6 Review](#part0006.xhtml_cid38)
*   [Chapter 7 Strings](#part0007.xhtml_cha-chapter_strings)
*   *   [7.1 Characters](#part0007.xhtml_aid-6LJVL)
    *   [7.2 String indexing](#part0007.xhtml_aid-6LK51)
    *   [7.3 Substrings](#part0007.xhtml_aid-6LKIA)
    *   [7.4 Using loops with strings](#part0007.xhtml_aid-6LKVA)
    *   [7.5 String equality](#part0007.xhtml_aid-6LM3O)
    *   [7.6 String formatting](#part0007.xhtml_aid-6LMAA)
    *   *   [7.6.1 Formatting strings into strings](#part0007.xhtml_uid397)
        *   [7.6.2 Formatting integers into strings](#part0007.xhtml_uid398)
        *   [7.6.3 Formatting floats into strings](#part0007.xhtml_aid-6LML2)
        *   [7.6.4 Print formatting](#part0007.xhtml_uid400)
    *   [7.7 Other useful string methods](#part0007.xhtml_aid-6LMVE)
    *   *   [7.7.1 `indexOf()`](#part0007.xhtml_aid-6LMVN)
        *   [7.7.2 `compareTo()`](#part0007.xhtml_aid-6LNFH)
        *   [7.7.3 `toLowerCase()` and `toUpperCase()`](#part0007.xhtml_uid427)
    *   [7.8 Review](#part0007.xhtml_cid47)
*   [Chapter 8 Objects and Classes](#part0008.xhtml_cha-ObjectsClasses)
*   *   [8.1 Classes](#part0008.xhtml_cid49)
    *   [8.2 Creating a class](#part0008.xhtml_cid50)
    *   [8.3 Creating objects](#part0008.xhtml_aid-7K4K4)
    *   [8.4 Attributes](#part0008.xhtml_aid-7K4RN)
    *   [8.5 Constructors and the `this` keyword](#part0008.xhtml_aid-7K53G)
    *   [8.6 Behaviors](#part0008.xhtml_aid-7K5RV)
    *   [8.7 Review](#part0008.xhtml_cid55)
*   [Chapter 9 Arrays and ArrayLists](#part0009.xhtml_cid56)
*   *   [9.1 Wrapper classes](#part0009.xhtml_aid-8IL2J)
    *   [9.2 Arrays](#part0009.xhtml_aid-8IL81)
    *   *   [9.2.1 Creating arrays](#part0009.xhtml_uid470)
        *   [9.2.2 Printing arrays](#part0009.xhtml_uid475)
        *   [9.2.3 Get, set, length, and looping](#part0009.xhtml_aid-8ILGS)
        *   [9.2.4 For-each loop](#part0009.xhtml_aid-8IMP5)
        *   [9.2.5 2D Arrays](#part0009.xhtml_aid-8IN5R)
    *   [9.3 ArrayLists](#part0009.xhtml_aid-8INJ6)
    *   *   [9.3.1 Creating an ArrayList](#part0009.xhtml_uid526)
        *   [9.3.2 Adding and inserting elements](#part0009.xhtml_aid-8INM7)
        *   [9.3.3 Removing elements](#part0009.xhtml_aid-8IO0C)
    *   [9.4 Review](#part0009.xhtml_cid60)
*   [Chapter 10 End Matter](#part0010.xhtml_cid61)
*   *   [10.1 Where to go from here](#part0010.xhtml_cid62)
*   [Chapter 11 Appendices](#part0011.xhtml_cid63)
*   *   [11.1 Appendix 1: Unicode table](#part0011.xhtml_sec-appendix_unicode)

# [Chapter 1 Getting Started](#part0001.xhtml_cid1)

This chapter will focus on getting you started from installation of our IDE to writing your first program in Java. We will be using the **IntelliJ IDEA** Java IDE by JetBrains.

## [1.1 Installing our IDE](#part0001.xhtml_aid-UGI9)

To begin, we can go to

[https://www.jetbrains.com/idea/download/](https://www.jetbrains.com/idea/download).

You will be redirected to a download page for your operating system (Windows, macOS, or Linux). Under **Community**, click **Download**.

![images/figures/GETTINGSTARTED_1](Images/image00386.jpeg)Figure 1.1: Click **Download** under **Community** for the free version of this IDE.

JetBrains will redirect you to a download receipt page, and the IntelliJ IDEA installer will begin downloading. Once the download is finished, open the installer.

![images/figures/GETTINGSTARTED_2](Images/image00387.jpeg)Figure 1.2: Splash page of the IDE installer.

When you reach the following page in the installer, make sure to check all the boxes.

![images/figures/GETTINGSTARTED_3](Images/image00388.jpeg)Figure 1.3: Check all the boxes on this page.

Keep clicking “Next” until the application begins to install. Once it is finished installing, it will let you know that you will need to reboot your PC. Do this now.

![images/figures/GETTINGSTARTED_4](Images/image00389.jpeg)Figure 1.4: Click "Reboot now" and restart your computer.

Once your computer restarts, open IntelliJ IDEA. Once you agree to the user agreements, you should be redirected to the following page:

![images/figures/GETTINGSTARTED_5](Images/image00390.jpeg)Figure 1.5: Splash page for IntelliJ IDEA.

Click “New Project”. Under the Project SDK `<No SDK>` dropdown, select **Download JDK**.

![images/figures/GETTINGSTARTED_6](Images/image00391.jpeg)Figure 1.6: Select **Download JDK** under the "Project SDK" dropdown.

A dropdown will ask which version and vendor you would like. Select version 17 and Oracle OpenJDK as your vendor. Then click **Download**.

![images/figures/GETTINGSTARTED_7](Images/image00392.jpeg)Figure 1.7: Version 17, Oracle OpenJDK

The JDK will take a few minutes to download. Once it’s done, the Project SDK will read “openjdk-17” as the JDK you are using.

![images/figures/GETTINGSTARTED_8](Images/image00393.jpeg)Figure 1.8: Click **Next** once you have downloaded the JDK.

When you are asked to create a project from a template, skip this step by clicking **Next**. When IntelliJ IDEA asks you to give a project name, you can write `HelloWorldProject`. Click **Finish** once you’re done. You should be redirected to an empty editor screen. Right-click `src` in the browser, hover over `New`, and select `Java class`.

![images/figures/GETTINGSTARTED_9](Images/image00394.jpeg)Figure 1.9: IntelliJ IDEA IDE.

## [1.2 Writing your first code](#part0001.xhtml_aid-UGL2)

Name your class `Main`. Now, a code editor should pop up with the following code:

```
public class Main {
}
```

We need to include a `main()` method inside the class. This tells Java what code to execute. Between the curly braces, add the following:

```
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello world!");
    }
}
```

This should print “Hello world!” as output. Now, we must compile and execute our code. To do this, click the *Run* menu bar button, and then click the “Run…” option that shows up. After that, click “Main” to indicate that you want to run the `main()` method from the “Main” class.

![images/figures/GETTINGSTARTED_10](Images/image00395.jpeg)Figure 1.10: Run your code.

A few seconds later, a console will pop up at the bottom of your window, reading `Hello world!`.

![images/figures/GETTINGSTARTED_11](Images/image00396.jpeg)Figure 1.11: "Hello world!" in the console.

Congratulations! You have just written your first Java program!

Let’s take a look at what our code just did.

Listing 1.1: Analyzing our code.

```
1public class Runner {
2    public static void main(String[] args) {
3        System.out.println("Hello world!");
4    }
5}
```

On the first line, we wrote a **class heading**, which is a heading used to declare that we are creating a new class. **Classes** are essentially blueprints for objects that we can create and manipulate through Java. Don’t worry if this or the following code looks intimidating, we’ll learn about them more in depth throughout the book.

On the second line, we wrote a **method heading** for our `main()` method. A method heading is used to label a function, or chunk of code, that we can use multiple times later on. This particular method, `main()`, is what Java looks for when attempting to execute code. It is like a *runner method*, or the method that Java wants to execute at runtime. We must write exactly `public static void main`, along with the parameter `args`, which is of the `String[]` type, in order for Java to properly run our code. Without this method, Java won’t necessarily run code in an ordered fashion.

On the third line, we printed `"Hello world!"` by using the `println` function under `System.out`. `System.out` is a reference to the console, and by calling `println`, we can write any data to standard output.

On the fourth and fifth lines, we closed our function and class, respectively, with curly braces.

Block 1.1. Using Semicolons

We can see that, following a single **statement**, there is a **semicolon**, and following every **body heading**, there are multiple statements. This tells us that, with a single statement, we succeed with a semicolon, and with a chunk of code that has multiple statements with semicolons, we put that chunk of code within curly braces. We will explore this concept as we explore more Java syntax. For now, it is important to include a semicolon after every statement.

Let’s add a few more print statements. After your first print statement, print your name, and then print your age as a number. To print your name, you must enclose your name in double-quotation marks. You do not have to do this with your age, as it is simply a number and not text.

Listing 1.2: Printing our name and age.

```
1public class Runner {
2    public static void main(String[] args) {
3        System.out.println("Hello world!");
4        System.out.println("Johnny Appleseed");
5        System.out.println(30);
6    }
7}
```

Don’t forget to save your file before running your program again.

Listing 1.3: Output for [Listing 1.2](#part0001.xhtml_code-printingmore)

```
Hello world!
Johnny Appleseed
30
```

We can see that, compared to lines 3 and 4, we printed data in line 5 that *wasn’t* enclosed in quotation marks. This is because what we printed in line 5 is of a completely different *type* than what we printed in lines 3 and 4. We printed **strings**, or text, in lines 3 and 4, while we printed a number, or more specifically an `int` (math integer - not the Java object `Integer`), in line 5.

We can perform all kinds of operations with numbers in Java. Numbers are split into four primitive types, but we won’t worry about that for now.

Let’s add and subtract some numbers.

Listing 1.4: Adding and subtracting numbers.

```
 1public class Runner {
 2    public static void main(String[] args) {
 3        System.out.println("Hello world!");
 4        System.out.println("Johnny Appleseed");
 5        System.out.println(30);
 6        System.out.println("Let's do some math!");
 7        System.out.println(45 + 15);
 8        System.out.println(98 - 26);
 9        System.out.println(1002 + 9384 - 56);
10    }
11}
```

In the code above, we add 45 and 15. After that, we subtract 26 from 98, and then we subtract 56 from the sum of 1002 and 9384. We can see that basic binary mathematics and order of operations applies here, and we get expected results.

Listing 1.5: Output for [Listing 1.4](#part0001.xhtml_code-addsubtract)

```
Hello world!
Johnny Appleseed
30
Let's do some math!
60
72
10330
```

Currently, we know to print data on their respective lines. But what if we wanted to print data next to each other?

In this case, we would instead use the `print()` method from `System.out`, instead of `println()`. This function writes data to the standard output *without* moving the text cursor to the next line.

We can print some letters to the console using the `print()` method.

Listing 1.6: Using `System.out.print()`

```
 1public class Runner {
 2    public static void main(String[] args) {
 3        System.out.println("Hello world!");
 4        System.out.println("Johnny Appleseed");
 5        System.out.println(30);
 6        System.out.println("Let's do some math!");
 7        System.out.println(45 + 15);
 8        System.out.println(98 - 26);
 9        System.out.println(1002 + 9384 - 56);
10        System.out.print("A");
11        System.out.print("B");
12        System.out.print("C");
13        System.out.println("soup");
14        System.out.println("Done");
15    }
16}
```

On lines 10 to 12, we are using the `print()` function to print `"A"`, `"B"`, and `"C"` to the console, right next to each other. Then, we call the `println()` function to print `"soup"`. This will print `"soup"` right next to `"ABC"`, and then move the text cursor to the next line. That way, when `"Done"` is printed, it won’t be on the same line as `"ABCsoup"`.

Listing 1.7: Output for [Listing 1.6](#part0001.xhtml_code-systemoutprint)

```
Hello world!
Johnny Appleseed
30
Let's do some math!
60
72
10330
ABCsoup
Done
```

Great job! You have created functioning code that prints text and does math operations!

## [1.3 Comments](#part0001.xhtml_aid-UH5S)

Sometimes, when writing code, we want to put a short description about what is happening at a specific point in our algorithm. Other times, we simply don’t want to run code but don’t want to delete it because we may use or refactor it later.

The solution to this is to use **comments**. Comments allow us to write plaintext in our code without it being evaluated by Java. We write single-line comments by writing a double-backslash (`//`), followed by our text.

Listing 1.8: Writing a single-line comment

```
// I am a comment
```

If we wanted to write comments across multiple lines, we could instead put all our plaintext inside a `/*` and `*/`, just like curly braces.

Listing 1.9: Writing a multi-line comment

```
/*
I am a comment
that can stretch
across multiple lines
*/
```

As an example of using comments, suppose we are a beginner to Java programming and we are given a piece of code.

Listing 1.10: Analyzing unfamiliar code

```
public class Runner {
    public static void main(String[] args) {
        int sum = 0;
        for(int i = 1; i <= 10; i++) {
            sum += i;
        }
        System.out.println("The sum of 10 numbers is " + sum);
    }
}
```

We have no idea what this program is supposed to do. However, if the developer were to include comments, then we could get a basic idea of what the code will do.

Listing 1.11: Adding comments to unfamiliar code

```
public class Runner {
    public static void main(String[] args) {
        // Creating a sum variable
        int sum = 0;

        // Adding every number from 1 to 10 to sum
        for(int i = 1; i <= 10; i++) {
            sum += i;
        }

        // Printing sum
        System.out.println("The sum of 10 numbers is " + sum);
    }
}
```

Now we can acknowledge that our code is supposed to find the sum of the first 10 consecutive integers. This is a perfect example of where comments can be handy. And when we run this code, we will find that the execution success was not hindered by our comments.

Listing 1.12: Output for [Listing 1.11](#part0001.xhtml_code-codewithcomments)

```
The sum of 10 numbers is 55
```

## [1.4 Reserved keywords](#part0001.xhtml_cid5)

In Java, the following keywords are **reserved**, meaning that they are used by the Java language and therefore cannot be used as variable identifiers.

| abstract | continue | for | new | switch |
| assert | default | goto | package | synchronized |
| boolean | do | if | private | this |
| break | double | implements | protected | throw |
| byte | else | import | public | throws |
| case | enum | instanceof | return | transient |
| catch | extends | int | short | try |
| char | final | interface | static | void |
| class | finally | long | strictfp | volatile |
| const | float | native | super | while |

## [1.5 Conventions used in this book](#part0001.xhtml_aid-UHBG)

This book uses many conventions for content such as images, tables, and code blocks.

### [1.5.1 Images](#part0001.xhtml_aid-UHBL)

Images will be referred to as Figures. For instance, [Figure 1.12](#part0001.xhtml_fig-sample) refers to the sample image before. Captions, as seen in the figure below, may periodically appear below images.

![images/figures/sample](Images/image00397.jpeg)Figure 1.12: This is a sample caption for the figure above.

### [1.5.2 Tables](#part0001.xhtml_uid27)

Tables will resemble the one below, where there is a simple grid with text inside.

| Lorem | ipsum | dolor |
| sit | amet | consectetur |
| adipiscing | elit | sed |

### [1.5.3 Inline code and code fences](#part0001.xhtml_uid28)

There are two ways code will be represented in this book. The first way is through *inline code*, or code that is on the same line as plain text.

> The difference between a `for` and `while` loop is that a `for` loop can iterate from a starting point to a stopping point, while a `while` loop will keep iterating until its condition is false.

Above, we can see that the inline code is in a green monospace font. Inline code will usually be short lines of code being discussed before actual code is demonstrated.

The other way that code will be represented is through *code fences*. Code fences are blocks of code that will appear every few paragraphs after brief descriptions about the code. Code fences will be referred to as listings, such as [Listing 1.13](#part0001.xhtml_code-sample) below.

Listing 1.13: Sample code listing.

```
public static void main(String[] args) {
    System.out.println("Sample code");
}
```

Code fences will either have line numbers, as shown in [Listing 1.14](#part0001.xhtml_code-linenos), or will not have line numbers, as shown in [Listing 1.15](#part0001.xhtml_code-nolinenos).

Listing 1.14: Sample code listing with line numbers.

```
1public static void main(String[] args) {
2    System.out.println("With line numbers");
3}
```

Listing 1.15: Sample code listing without line numbers.

```
public static void main(String[] args) {
    System.out.println("Without line numbers");
}
```

### [1.5.4 Notes](#part0001.xhtml_sec-notes)

Periodically, there may be “aside notes” which discuss an interesting fact or topic but digress from the main purpose of the concept being discussed. These boxes don’t necessarily have to be read, but can be helpful. They will appear in shaded “blocks”, and have a title of the concept being discussed.

Block 1.2. An interesting example concept

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

### [1.5.5 Examples, exercises, and problems](#part0001.xhtml_uid34)

Throughout the book, there will be many examples per chapter. Some of these examples will add on to existing code, while other examples will just be situations in code that you may encounter.

Examples will be indicated in bolded font, followed by the example.

> **Example**

> This is a sample example.

Exercises may also appear after particular sections and will test your knowledge of the content you just learned. Unlike the examples, the book will not immediately show you the answers after you have done the exercises. It is recommended that you do the exercises in a separate Java class in each Java project you make for its respective chapter.

Exercise blocks will look just like “aside notes” discussed in [Section 1.5.4](#part0001.xhtml_sec-notes), but the title will be an italicized *“Exercises”* label.

Block 1.3. *Exercises*

**Ex 1.**

This is an example problem.

**Ex 2.**

This is another example problem.

**Ex 3.**

This is a third example problem.

Finally, there will be coding problems at the end of each chapter. Unless otherwise indicated, you will be expected to write and run your code from the `main()` method or from another static method that is called in `main()`.

> **Problem 1**

> Write a program that prints all the numbers from 1 to 100 using a `for` loop.

Solutions to both exercises and problems will be located at the end of the book.

## [1.6 Review](#part0001.xhtml_cid7)

In this section, we got started with Java programming by first installing the JDK for debugging and execution. Next, we installed our Eclipse IDE, and we created and ran our first “Hello world” program. Finally, we learned to print more data, and we analyzed comments, important keywords, and the conventions used in this book.

# [Chapter 2 Types](#part0002.xhtml_cid8)

Java is an **object-oriented** language, meaning that we manipulate **objects** using Java. Objects in real life can be anything, ranging from cars to tennis balls. Later, we’ll be able to create our own objects. However, before we do that, we must work with the most basic things that Java works with, which are **types**.

There are many different types of data we can manipulate, including numbers and text. In fact, there are eight **primitive types**, or most basic types, that we can use: `int`, `long`, `short`, `float`, `double`, `boolean`, `char`, and `byte`. We will mostly focus on `int`, `double`, and `boolean`, but we will occasionally have to use the other types as well.

In addition to these primitive types, we can work with objects on a larger scale, such as `Strings`, `StringBuilders`, `Integers`, `Doubles`, etc. These objects are not primitive types because their entire foundation is based on the workings of primitive types. For instance, a `String` object is simply a sequence of `char` data.

Let’s start by learning how we can manipulate numbers.

## [2.1 Numbers](#part0002.xhtml_aid-1T156)

Java allows us to work largely with numbers. For instance, 2, 5.6, and -93 could all be examples of numbers.

Numbers, though it isn’t an object itself, can be broken down into `int`, `long`, `short`, `byte`, `float`, and `double`. Let’s first explore the different types of integers.

### [2.1.1 Types of Java integers](#part0002.xhtml_aid-1T15K)

Before we get into integers, we need to review an important computer science concept. We must face the reality that everything is made from **binary numbers**, meaning that we use 0s and 1s to express all types of data. In particular, integers are expressed as a combinaton of 0s and 1s.

Block 2.1. Binary versus Base 10

If we were to start counting in base 2 (binary format), we would begin at

![epub/OEBPS/images/texmath/95c51441b0a375b27da1e2dc477f825ec8431ed4](Images/image00398.jpeg)

This same sequence in base 10 would be

![epub/OEBPS/images/texmath/966d1fb11f1f33edc1afb4ad43d1661ece077420](Images/image00399.jpeg)

The key difference between counting in binary numbers and in base 10 is that with base 2, immediately after all of our digits are 1, we add another place value (1 ![epub/OEBPS/images/texmath/605575864c00abe7d78d98ad65404e3e9c121d1f](Images/image00400.jpeg) 10, 111 ![epub/OEBPS/images/texmath/605575864c00abe7d78d98ad65404e3e9c121d1f](Images/image00400.jpeg) 1000). On the other hand, with base 10, we add another place value after all of our digits are 9 (99 ![epub/OEBPS/images/texmath/605575864c00abe7d78d98ad65404e3e9c121d1f](Images/image00400.jpeg) 100, 9999 ![epub/OEBPS/images/texmath/605575864c00abe7d78d98ad65404e3e9c121d1f](Images/image00400.jpeg) 10000).

In terms of converting from a binary number to a number in base 10, if we were to have 101001110 in base 2, that would translate to 334 in base 10. The way we convert a number in base 2 to base 10 would be to expand the number, starting from the left, such that the units digit is multiplied by ![epub/OEBPS/images/texmath/f46bc68b63f31a5b394028ff6be67184a1a813fc](Images/image00401.jpeg), the tens digit is multiplied by ![epub/OEBPS/images/texmath/314e012971597e862a391c354504873b5a7e0f10](Images/image00402.jpeg), the hundreds digit is multiplied by ![epub/OEBPS/images/texmath/3e6bad6ca84fdc9d48e5ca132e2bd98a8b885d4c](Images/image00403.jpeg), the thousands digit is multiplied by ![epub/OEBPS/images/texmath/bea349a8554b121d09fa8c0fecdb7b0db89c6900](Images/image00404.jpeg), and so on. So, if we were to expand 101001110, we would get

![epub/OEBPS/images/texmath/17bf7278bf71afb9e017bf8ac71400a4241ac993](Images/image00405.jpeg)![epub/OEBPS/images/texmath/3eb3904b567da61028c0de50fdd0f10ed8fbb3a8](Images/image00406.jpeg)![epub/OEBPS/images/texmath/2dc084f0fff4ef685c7f07f2c93fad73e0f3a31e](Images/image00407.jpeg)![epub/OEBPS/images/texmath/f7246030adbd60039a64fa9f293dd03ab9eab5cf](Images/image00408.jpeg)

Let’s analyze how this relates to Java numbers. As indicated in [Table 2.1](#part0002.xhtml_table-intbit), Java integers can be split into the following groups: 8-bit, 16-bit, 32-bit, 64-bit, or 128-bit.

| **Type** | **#-Bit** | **Numerical Range** |
| `byte` | 8-bit | ![epub/OEBPS/images/texmath/9b780356b54cd0c8d8ee3bfbb0021fecaed5a4a5](Images/image00409.jpeg) |
| `short` | 16-bit | ![epub/OEBPS/images/texmath/447073ca55db61bd92cb9297cef91adc6ae7cdfa](Images/image00410.jpeg) |
| `int` | 32-bit | ![epub/OEBPS/images/texmath/e7cbe94730e4ef421fff630b66ad60fa0c360345](Images/image00411.jpeg) |
| `long` | 64-bit | ![epub/OEBPS/images/texmath/1f817ebfbfde45ff151e5b8f0f896bb7b392bc62](Images/image00412.jpeg) |

Table 2.1: Types of Java integers.

We’ll mainly be focusing on `int` data from this list. When we look at the numerical ranges above, we see that `int` falls between ![epub/OEBPS/images/texmath/e7cbe94730e4ef421fff630b66ad60fa0c360345](Images/image00411.jpeg). That means that numbers of the `int` type can only be between -2147483648 and 2147483647. So, if you try to write an integer above ![epub/OEBPS/images/texmath/bd9a9fe4d5a8dfa2afed3fad9218f8562875b397](Images/image00413.jpeg) or below ![epub/OEBPS/images/texmath/30ae2b7f9ac9f1c6b96fc3ef80b2573185e31b29](Images/image00414.jpeg), you would receive an error. Additionally, if at any point in your code an `int` tries to go above ![epub/OEBPS/images/texmath/bd9a9fe4d5a8dfa2afed3fad9218f8562875b397](Images/image00413.jpeg) or below ![epub/OEBPS/images/texmath/30ae2b7f9ac9f1c6b96fc3ef80b2573185e31b29](Images/image00414.jpeg), something called an **overflow** will occur. This means that if your integer keeps increasing, it will eventually wrap around and start at the smallest negative `int`. Likewise, if your integer keeps decreasing, it will eventually wrap around and start at the largest positive `int`.

### [2.1.2 Integer math operations](#part0002.xhtml_aid-1T18S)

Just like in real life, you can do simple arithmetic with integers in Java. [Table 2.2](#part0002.xhtml_table-arithmetictable) shows the different operators you can use with numbers.

| **Operator** | **Definition** | **Example** |
| `+` | Plus - Adds two numbers | `1+2=3` |
| `-` | Minus - Subtracts two numbers | `10-4=6` |
| `*` | Times - Multiplies two numbers | `5*6=30` |
| `/` | Divide - Divides two numbers | `6/3=2` |
| `%` | Remainder - Divides two numbers and returns the remainder | `7%3=1` |

Table 2.2: Operators that can be used with integers.

It is important to note that when you do any kind of operation with integers, you get an integer result. This is especially important when dividing an `int` by an `int`. For instance, if you take `6 / 3`, you will get `2` as expected, but if you divide `17 / 4`, where the result is supposed to be a decimal number, `4.25`, Java will instead remove anything after the decimal point and only keep the integer part, which is `4`.

We should also note that we can use parentheses in our operations, which is also an indicator that Java arithmetic follows the PEMDAS order of operations. For instance, `(3+5)*2` would yield `16` because we first compute `3+5` inside the parentheses, and then multiply the result by `2`.

For now, we will simply print any arithmetic operations we want to perform using `System.out.println()`. Create a new Java project called `Types`. Then, create a new class called `Arithmetic.java`, and write an empty `main()` function inside the class.

Listing 2.1: Add the `main()` method to `Arithmetic.java`

```
public class Arithmetic {
    public static void main(String[] args) {

    }
}
```

**Example 1**

Now, let’s do some addition and subtraction. Write a few print statements with your arithmetic expressions inside the parentheses. You don’t necessarily have to copy the same arithmetic performed in [Listing 2.2](#part0002.xhtml_code-additionsubtraction).

Listing 2.2: Doing addition and subtraction.

```
public class Arithmetic {
    public static void main(String[] args) {
        System.out.println(2+4);
        System.out.println(9312-893193);
        System.out.println(128+8592+4829128-4829);
        System.out.println(4578-(7591+38));
    }
}
```

Notice how on the fourth and fifth lines we had multiple addition and subtractions occurring simultaneously. Unless there are parentheses, like in the fifth line, addition and subtraction are prioritized the same, so in this case Java would compute from left to right.

Listing 2.3: Output for [Listing 2.2](#part0002.xhtml_code-additionsubtraction)

```
6
-883881
4833019
-3051
```

**Example 2**

Next, write some expressions including multiplication and division, as demonstrated in [Listing 2.4](#part0002.xhtml_code-multiplicationdivision).

Listing 2.4: Doing multiplication and division.

```
public class Arithmetic {
    public static void main(String[] args) {
        System.out.println(29*73);
        System.out.println(-44/11);
        System.out.println(30/4);
    }
}
```

We observe that multiplication works just like in written mathematics. However, with division, just like we analyzed earlier, dividing an integer by an integer will only yield an integer, so the fifth line will round down the quotient of `30/4` to the floor of 7.5, or 7.

Listing 2.5: Output for [Listing 2.4](#part0002.xhtml_code-multiplicationdivision)

```
2117
-4
7
```

**Example 3**

Lastly, we can use the remainder operator in [Listing 2.6](#part0002.xhtml_code-remainder) to get the remainder of a division performed on two integers. This remainder will also always be an `int` when done on `int` operands.

Listing 2.6: Finding the remainder.

```
public class Arithmetic {
    public static void main(String[] args) {
        System.out.println(1234%10);
        System.out.println(232%2);
        System.out.println(-9%15);
    }
}
```

We’ll notice that in the first remainder expression, we find that taking a number divided by 10 and finding the remainder yields the units digit of the number. This is a consistent pattern that we’ll find across all bases and their respective numbers. Additionally, we compute the remainder of -9 divided by 15. The fact that Java outputs `-9` as the result of `-9%15` demonstrates that Java doesn’t use a true modulus, but instead simply uses the percentage (modulo) symbol to calculate the remainder. If Java indeed adopted a true modulo operator, `-9%15` would have been `6` because a number in a particular modulus will not be negative.

Listing 2.7: Output for [Listing 2.6](#part0002.xhtml_code-remainder)

```
4
0
-9
```

Block 2.2. *Exercises*

**Ex 1.** Find the sum of 239 and 9584.

**Ex 2.** Find the product of 12038 and 5982831.

**Ex 3.** Farmer John’s cows make 1 gallon of milk in their first day of work, 2 gallons on their second day, 3 gallons on their third day, and so on for seven days. How many total gallons do FJ’s cows make after seven days?

**Ex 4.** Farmer John wants to take 247 of his cows to the beef museum, and he has to organize them into groups of 15. How many cows will he unfortunately have to leave behind?

### [2.1.3 Working with decimals](#part0002.xhtml_uid49)

We use integers a lot, but there will be occasions where we need to use decimal numbers too. These decimal numbers can be numbers like 3.44, 128.94, -75.1, and even 4.0. Any number in Java that has a decimal point, even those that are technically integers like 4.0, is a decimal number.

Decimals can be split into `float` and `double`. The difference between `float` and `double` is that floats provide precision of 6 to 7 decimal digits, while doubles provide precision of 15 to 16 decimal digits. So, if we were to compute something such as `1.0 / 7.0` where both were doubles, we would get 0.14285714285714285, whereas if they were floats, we would get only 0.14285715, with half as many digits shown.

By default, Java uses doubles when working with decimals, unless explicitly stated otherwise. To write a double, you would write something like `4.3d` or `4.3`, where you write your decimal, optionally followed by a `d`. To write a float, on the other hand, you must write `5.6f` or do something called a *type-cast*, where you convert `5.6` to a double. Of course, `5.6` is simply an example of a decimal, and you could replace that with anything.

In this section, to keep things simple, we will just work with doubles.

### [2.1.4 Decimal operations](#part0002.xhtml_aid-1T1K6)

Doubles and floats can perform the same math operations that integers can. However, we will not demonstrate using the remainder function because it is not used much with doubles and floats.

One interesting thing to note is that you can use both doubles and integers in the same expression. When you do this, everything will be casted to a double. So, if you were to take `6/4`, you would get `1`, but if you were to instead take `6.0/4` or `6/4.0` or `6d/4`, you would get `1.5` as normally expected.

**Example 1**

Let’s practice some addition and subtraction. Write a few expressions including both operators and using both doubles and integers.

Listing 2.8: Adding and subtracting doubles.

```
public class Arithmetic {
    public static void main(String[] args) {
        System.out.println(123.52 + 812.3);
        System.out.println(534 - 88.8);
        System.out.println(841 + 848d - 3);
    }
}
```

In the first print statement, we are adding two doubles, so we will get a `double` result. In the second print statement, we are subtracting a `double` from an `int`, so we will also get a `double` result. In the third print statement, it looks like we are only adding and subtracting integers, but we can see that the second operand is `848d`, where the `d` indicates that `848d` should be interpreted as a double. Because there is therefore a `double` in the expression, a `double` result would be printed.

Listing 2.9: Output for [Listing 2.8](#part0002.xhtml_code-addsubtractdouble)

```
935.8199999999999
445.2
1686.0
```

**Example 2**

Now, we will factor in multiplication and division. Write out a few expressions including some or all four operators.

Listing 2.10: Multiplying and dividing doubles.

```
public class Arithmetic {
    public static void main(String[] args) {
        System.out.println(2312 * 582d / 95);
        System.out.println(85.4 * 912.2);
        System.out.println(6 / 4 * 2.0);
        System.out.println((32d - 54) / 2);
    }
}
```

In the first print statement, we multiply an `int` by a `double`, acquiring a `double` result. We then take that result and divide by an `int`, resulting in a `double` answer.

In the second print statement, we are multiplying two doubles, so we will get a `double` result.

In the third print statement, we are dividing two integers, and then multiplying the result by a double. However, the fact that there is a `double` in the total expression doesn’t mean that the answer will be the mathematically correct answer. Notice that there is only division and multiplication, with no parentheses indicating higher priority. This means that the math is done from left to right. So, you first divide 6 by 4. Because this is strictly integer division, the result will be the `int` 1. Only then do you multiply that `int` by a `double` to procure a `double` result.

Finally, in the fourth print statement, we are subtracting an `int` from a `double` in parentheses and dividing the result by an `int`. The subtraction is done first, meaning that a `double` will be divided by an `int` to output a `double` answer.

Listing 2.11: Output for [Listing 2.10](#part0002.xhtml_code-multiplydividedouble)

```
14164.042105263157
77901.88
2.0
-11.0
```

Block 2.3. *Exercises*

**Ex 1.** Farmer John wants to purchase face masks for his cows to prevent the spread of the bovine disease, COWWID-19. If face masks cost $5.03 apiece, how much money will he have to pay to purchase 198 masks for his cows?

**Ex 2.** Farmer John has 2190 acres of land, and he wants to assign 43 cow guards to protect the land. If the cows have to protect an equal amount of land, how many acres should each cow guard?

**Ex 3.** Farmer John has $412.93, and he wants to gift his 24 cows with equal amounts of money. How much money should each cow receive?

**Ex 4.** Farmer John’s cows are in dilemma. They created a 3.64 meter ladder to climb over the 4.21 meter barn door and escape their COWWID-19 quarantine, but they can’t figure how how many more meters to extend their ladder. How many more meters does their ladder have to be extended such that the cows can successfully escape quarantine?

### [2.1.5 The `Math` class](#part0002.xhtml_aid-1T1RR)

In addition to the operations we learned above, we can also perform other mathematical operations such as finding the absolute value, using exponents, and finding the square root. However, operations such as these require the use of a special class called the `Math` class. This class contains certain *methods* that we can use to perform these complex operations.

To use a method from the `Math` class, we can simply write `Math`, followed by a dot and the method we want to use.

```
Math.method()
```

#### [Absolute value](#part0002.xhtml_uid57)

To find the absolute of a number, we can write `Math.abs(number)`.

```
System.out.println(Math.abs(5)); // 5
System.out.println(Math.abs(-4)); // 4
```

This method will turn any number into its positive counterpart.

#### [Exponents](#part0002.xhtml_uid58)

To raise a number to the power of another, we can use the `Math.pow()` method, which produces a `double` result. We supply two arguments, `a` and `b`, and we get the result of `a` raised to the power of `b`.

```
System.out.println(Math.pow(2, 4)); // 16
System.out.println(Math.pow(5, 3)); // 125
```

#### [Square root](#part0002.xhtml_uid59)

To find the square root of a number (![epub/OEBPS/images/texmath/ff14114b8516b5cc0308ce19e127bbf94ec0dbc8](Images/image00415.jpeg)), we can use the `Math.sqrt()` method, which produces a `double` result. We can supply one numerical argument, `a`, and we will receive the square root of `a`.

```
System.out.println(Math.sqrt(16)); // 4.0
System.out.println(Math.sqrt(6.25)); // 2.5
```

#### [Getting a random number](#part0002.xhtml_aid-1T20C)

We can also acquire random numbers using the `Math.random()` method. This will produce a random `double` value between 0.0 and 1.0.

```
System.out.println(Math.random());
System.out.println(Math.random());
System.out.println(Math.random());
```

```
0.9273683758459681
0.8923263271915217
0.8198859922177231
```

We can use this to acquire a random integer between two numbers. We would write the following to do so:

```
(int)(Math.random() * b + a)
```

*   We first write `(int)` to convert to an integer result. We will learn more about this notation in [Section 3.3](#part0003.xhtml_aid-2RJJ9).
*   We multiply `Math.random()` by `b`, as `b` indicates the number of integers that a random number could be picked from.
*   We add this result to `a`, which indicates the smallest random number we could generate.

For example, suppose we wanted a random integer between 10 and 25 (inclusive). From 10 to 25, there are 16 integers, so `b` would be 16. Additionally, the lower bound is 10, so `a` would be 10. Therefore, we could print the following.

```
System.out.println((int)(Math.random() * 16 + 10));
```

When we execute this code a couple times, we will receive different integers between 10 and 25, inclusive.

```
24
20
13
10
18
25
```

If we wanted a random integer between 34 and 87, our lower bound, `a`, would be 34, and the number of possible random integers, `b`, would be 54 since there are 54 integers between 34 and 87, inclusive.

```
System.out.println((int)(Math.random() * 54 + 34));
```

```
69
85
49
70
36
60
```

If our upper bound were ![epub/OEBPS/images/texmath/85ba312184b4f9a17a3da2cfd79e868ca2e74ec7](Images/image00416.jpeg) and our lower bound were ![epub/OEBPS/images/texmath/743f23d6d6b22693e8e3093f2943d003a85812d6](Images/image00417.jpeg), we can generalize `b` to be

![epub/OEBPS/images/texmath/709a4e0f3e6af8487ef51b2c2d2c27ef6bfe0cd6](Images/image00418.jpeg)

## [2.2 Text](#part0002.xhtml_aid-1T25H)

In addition to numbers, Java allows us to manipulate text in the form of **Strings**. While *String* is an *object*, not a primitive type, it is so widely used that it is worth studying in the beginnning of your Java education. Strings are collections of characters like `"Hello world"` or `"Java programming is fun!"`, where your text is inside quotation marks.

For example, in [Chapter cha:GettingStarted](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX), when we printed “Hello world!”, we actually printed a string. We can print more strings and even use strings to perform various operations.

It is important to note that strings are *case-sensitive*, meaning that a string with an uppercase letter is different than a string with the same letter, but lowercase. So, `"Hello world"` and `"hello world"` are two different strings because the first string starts with a capital “H” but the second string starts with a lowercase “h”.

Before we get into strings, we must understand the primitive type Strings are dependent on, which is `char`.

### [2.2.1 Characters](#part0002.xhtml_uid64)

As we stated earlier, strings are made up of characters, each of which are of the `char` type. A `char` literal would be a single character enclosed in single quotation marks, such as `'a'` or `'b'`. We can also express escape sequences ([Section 2.2.5](#part0002.xhtml_aid-1T2IF)) in a single character. For instance, `'\n'` is its own newline character, and `'\"'` is a double quotation mark character. We can use individual characters to create larger strings.

### [2.2.2 Create a string](#part0002.xhtml_uid65)

To create a `String`, we simply have to put text inside double quotation marks. Let’s start by creating a new java file, `Strings.java`, and adding a `main()` method to the body of the class ([Listing 2.12](#part0002.xhtml_code-createstringsclass)).

Listing 2.12: Adding the `main()` method.

```
public class Strings {
    public static void main(String[] args) {

    }
}
```

Now, we can use the print statement in [Listing 2.13](#part0002.xhtml_code-printstrings) to print anything we want.

Listing 2.13: Printing strings.

```
public class Strings {
    public static void main(String[] args) {
        System.out.println("My name is Johnny Appleseed.");
        System.out.println("I am 30 years old.");
        System.out.println("I like make Android Apps using Java.");
    }
}
```

We can see that, when we run our code, we get exactly what we printed in the console.

Listing 2.14: Output for [Listing 2.13](#part0002.xhtml_code-printstrings).

```
My name is Johnny Appleseed.
I am 30 years old.
I like make Android Apps using Java.
```

Block 2.4. *Exercises*

**Ex 1.** Print “I am a human.”

**Ex 2.** Print your parents’ names on a single line.

**Ex 3.** Print your best friend’s name.

### [2.2.3 String concatenation](#part0002.xhtml_uid70)

In addition to manipulate single strings at a time, we can join, or *concatenate*, a string and another piece of data into one using the `+` operator, as demonstrated in [Listing 2.15](#part0002.xhtml_code-concatenatestrings).

Listing 2.15: Concatenating strings.

```
public class Strings {
    public static void main(String[] args) {
        System.out.println("My name is " + "Johnny Appleseed.");
        System.out.println("1 and " + "2 and " + "3 and 4");
        System.out.println("I am a string that is force casting " + 123);
        System.out.println(3 + 4.5 + 6 + " is now a string!");
    }
}
```

In the first print statement, we notice that when joining `"My name is "` and `"Johnny Appleseed."` using the `+` operator, we print a combined string. In the second print statement, the same thing happens, but with multiple string concetenations from the left to right.

In the third line, however, we are concatenating a `String` to an `int`. When we do this, Java converts the `int` to a `string` and appends it to the end of the first string so concatenation works as expected.

In the fourth line, we first compute `3 + 4.5 + 6`, which simplifies to `13.5`. Then, we add that to a string. Because we are adding a `float` to a `String`, Java converts the `float` to a `String` and then joins the two data into a single string.

Listing 2.16: Output for [Listing 2.15](#part0002.xhtml_code-concatenatestrings).

```
My name is Johnny Appleseed.
1 and 2 and 3 and 4
I am a string that is force casting 123
13.5 is now a string!
```

Block 2.5. *Exercises*

**Ex 1.** Print the concatenation of your first and last name, without adding spaces to either string.

**Ex 2.** Print the string “Hello! My name is {} and I am {} years old!”, where the first {} is your name and the second {} is your age. Make sure that both placeholders are their own strings (i.e. your name and age are both their own strings) so that you can practice concatenation on these strings.

**Ex 3.** Print “MM/DD/YYYY”, where “MM” is your birth month, “DD” is your birth day, “YYYY” is your birth year, and “MM”, “DD”, and “YYYY” are separate strings.

### [2.2.4 Find the length of a string](#part0002.xhtml_uid74)

You can also find the number of characters in a string. For instance, `"Hello world"` has 11 characters. It’s important to note that spaces, punctuation, and symbols in your string still count as characters.

To find the number of characters, or *length*, of a string, you would write

```
"I'm a string".length()
```

where you first write your string, followed by a dot, and then the string method `length()`. This method will give us the number of characters as an `int` value. The least number of characters a string can have is 0 characters. Write and find the length of a few strings, and do some math operations with those values, as shown in [Listing 2.17](#part0002.xhtml_code-uselength).

Listing 2.17: Using the `length()` method.

```
public class Strings {
    public static void main(String[] args) {
        System.out.println("Johnny Appleseed".length());
        System.out.println("Johnny".length() + "Appleseed".length());
        System.out.println("cool".length() * 4 + " is the new length.");
    }
}
```

In the first print statement, we are using the `length()` method to find the number of characters in `"Johnny Appleseed"`. In the second print statement, we are adding the length of `"Johnny"` to the length of `"Appleseed"`, but we don’t include a space in either, so there will be one less character. In the third print statement, we are multiplying the length of `"cool"` by 4, and then concatenating that to another string.

Listing 2.18: Output for [Listing 2.17](#part0002.xhtml_code-uselength)

```
16
15
16 is the new length.
```

Block 2.6. *Exercises*

**Ex 1.** Find the sum of the length of your first name and the length of your last name using the `length()` method.

**Ex 2.** Multiply the length of `"Programming"` by 5 and print the result.

**Ex 3.** Find the remainder of the length of your last name divided by your first name (use the `%` operator).

### [2.2.5 Special Characters and Escape Sequences](#part0002.xhtml_aid-1T2IF)

Strings are special in that you can use special character sequences in a string to produced some effect, like a newline. Additionally, these special character sequences can help prevent unwanted syntax or logical issues from affecting your strings.

To write these character sequences, or *escape sequences*, you need to first write a `\`, followed by a character. We will go over some of the escape sequences shown in [Table 2.3](#part0002.xhtml_table-escapesequence) in the next few examples.

| **Escape Sequence** | **Purpose** |
| `\\` | Inserts a regular backslash |
| `\"` | Inserts a double-quotation mark |
| `\n` | Inserts a newline |
| `\t` | Inserts a tab |
| `\r` | Inserts a carriage return |
| `\b` | Inserts a backspace |

Table 2.3: Escape sequences.

**Example 1**

Suppose we want to print the phrase `Patrick Henry said "Give me liberty, or give me death!" in 1775`. Try to print this how you would normally print a string.

Listing 2.19: Printing a string containing quotes.

```
public class Strings {
    public static void main(String[] args) {
        System.out.println(
            "Patrick Henry said "Give me liberty, or give me death!" in 1775"
        );
    }
}
```

Immediately, you are going to be hit with a plethora of errors.

Listing 2.20: Output for [Listing 2.19](#part0002.xhtml_code-errorquote)

```
Exception in thread "main" java.lang.Error: Unresolved compilation problems:
    Syntax error on token(s), misplaced construct(s)
    Give cannot be resolved to a type
    Syntax error on token "liberty", delete this token
    Syntax error on token "give", ; expected
    Syntax error on token "death", ( expected
    The operator ! is undefined for the argument type(s) String
```

The reason for this is that, in between “said” and “Give”, we put a double-quotation mark, indicating to Java that we want to terminate our string. This leaves an issue for the “Give me liberty, or give me death!” part of the string because technically, it isn’t interpreted to be part of the entire string.

Instead, if we insert backslashes (`\`) before every embedded double-quotation mark that is supposed to act like a normal quotation mark, Java will interpret that we don’t want to terminate the string too early.

Listing 2.21: Adding backslashes to our quotation marks in [Listing 2.19](#part0002.xhtml_code-errorquote)

```
public class Strings {
    public static void main(String[] args) {
        System.out.println(
            "Patrick Henry said \"Give me liberty, or give me death!\" in 1775"
        );
    }
}
```

Now, when we compile and execute our code, we will find that the string we desired is printed with all the embedded double-quotation marks.

Listing 2.22: Output for [Listing 2.21](#part0002.xhtml_code-fixedquote)

```
Patrick Henry said "Give me liberty, or give me death!" in 1775
```

**Example 2**

Suppose we want to print the following string in a single print statement.

```
99 lines of bugs in the code,
99 lines of bugs,
Take one down,
Patch it around,
127 lines of bugs in the code
```

This string appears to have multiple lines. We can therefore use the `\n` escape sequence to insert a new line after every line in our code.

Listing 2.23: Using the `\n` escape sequence.

```
public class Strings {
    public static void main(String[] args) {
        System.out.println("99 lines of bugs in the code,\n" +
                "99 lines of bugs,\n" +
                "Take one down,\n" +
                "Patch it around,\n" +
                "127 lines of bugs in the code");
    }
}
```

Notice that we are adding `\n` sequences at the end of each string we are concatenating. Note that you *do not have to do this*; the book simply concatenates the strings with `\n` characters at the end of each string because there is not enough space to fit the poem in a single string with multiple `\n` separators.

Listing 2.24: Output for [Listing 2.23](#part0002.xhtml_code-newline)

```
99 lines of bugs in the code,
99 lines of bugs,
Take one down,
Patch it around,
127 lines of bugs in the code
```

We also have the option to insert the `\n` sequence somewhere other than at the end or beginning of a string. When `\n` is found in a string, Java will simply insert a new line and the remaining characters will be printed there.

Listing 2.25: Using `\n` in between characters.

```
public class Strings {
    public static void main(String[] args) {
        System.out.println("99 lines of\nbugs in the code");
    }
}
```

Listing 2.26: Output for [Listing 2.25](#part0002.xhtml_code-samplenewline)

```
99 lines of
bugs in the code,
```

**Example 3**

We can also use the `\t` sequence to generate a tab between characters. For instance, we could write the following:

Listing 2.27: Using `\t`.

```
public class Strings {
    public static void main(String[] args) {
        System.out.println("1...\t2...\t3...\nAnd we have liftoff!");
    }
}
```

In the string above, we are inserting tabs between `1...`, `2...`, and `3...`. We are also using a `\n` operator to insert `And we have liftoff!` on the next line.

Listing 2.28: Output for [Listing 2.27](#part0002.xhtml_code-taboperator)

```
1...   2...   3...
And we have liftoff!
```

Block 2.7. *Exercises*

**Ex 1.** Write your full name on separate lines, but using a single string.

**Ex 2.** Print the quote “Yoda said “Do or do not. There is no try.” in Star Wars.”

**Ex 3.** Print the following output using a single print statement.

```
1:    one
2:    two
3:    three
```

Note that the empty spaces are tabs.

## [2.3 Logic](#part0002.xhtml_aid-1T2T3)

We’ve looked at manipulating numbers and text with Java. Next, we will explore logical reasoning. Java can make decisions based on conditional expressions called **booleans**. Unlike numbers or text, there are only two boolean values: `true` and `false`.

### [2.3.1 Printing `true` and `false`](#part0002.xhtml_uid91)

It is quite straightforward to print `true` or `false`. Even though these two values look like they are strings, they are not enclosed in double-quotes.

To start, create a new class, `Booleans.java`, in the same Java project as `Strings.java` and `Arithmetic.java`. Then, add the `main()` method to the body of your new `Booleans` class, as demonstrated in [Listing 2.29](#part0002.xhtml_code-booleansmain).

Listing 2.29: Adding the `main()` method to the `Booleans` class.

```
public class Booleans {
    public static void main(String[] args) {

    }
}
```

Next, print `true` to the console on one line, and `false` on the next line.

Listing 2.30: Printing `true` and `false`.

```
public class Booleans {
    public static void main(String[] args) {
        System.out.println(true);
        System.out.println(false);
    }
}
```

Immediately, we can note that `true` and `false` are colored differently than strings, indicating that we are printing booleans.

Listing 2.31: Output for [Listing 2.30](#part0002.xhtml_code-printbooleans)

```
true
false
```

Printing `true` and `false` is all we need to do for this section. However, booleans aren’t that basic. There’s a lot more that we can do with booleans that we will learn in the next sections and the coming chapters.

### [2.3.2 Relational Operators](#part0002.xhtml_aid-1T30S)

Because booleans evaluate to true/false values, we can perform *comparisons* on booleans. We have seen comparisons before, especially with numbers. We can use comparison operators, or *relational operators*, to compare data such as numbers. When we use relational operators to compare two values, Java determines whether the comparison statement we write is true or false. For instance, if we state that 4 is greater than 2, Java says that this is `true`, while if we state that 56 is equal to 32, Java determines that this is `false`. [Table 2.4](#part0002.xhtml_table-relationaloperators) demonstrates the various comparison operators we can use, as well as examples of true outcomes.

| **Operator** | **Definition** | **Example** |
| `>` | Greater than | 5 > 3 |
| `<` | Less than | 67 < 91.8 |
| `>=` | Greater than or equal to | 43 >= 42 |
| `<=` | Less than or equal to | 67.8 <= 85.2 |
| `==` | Equal to | 19 == 19 |
| `!=` | Not equal to | 32 != 32.1 |

Table 2.4: Relational operators.

The `==` operator may seem unfamiliar to us. We would think that we use `=` (a single equal sign) to determine whether two objects were equal. However, `=` is strictly for *variable assignment*, which we will learn about in a few sections. `==` is strictly a comparison operator, and is only used to determine whether two objects are equal.

Notice how we referred to the `==` operator as comparing objects. However, we established that we were manipulating primitive types for now. As we’ll learn later, the `==` sign checks if two objects are the *same object*, not necessarily the same value. However, with primitive types, the `==` sign checks if the two values are the same.

Let’s use each operator one by one. Write a few print statements comparing `int` and `double` values using various relational operators.

Listing 2.32: Using relational operators.

```
public class Booleans {
    public static void main(String[] args) {
        System.out.println(43 > 82);
        System.out.println(192 < 49.3 + 59);
        System.out.println("Hello".length() >= "bye".length());
        System.out.println("Johnny Appleseed".length() <= 20);
        System.out.println(51 % 4 == 3);
        System.out.println("Bye".length() != 12);
    }
}
```

In the first print statement, we are checking if one number is greater than another. In the second, we evaluate whether an `int` is less than the sum of a `double` and an `int`.

In the third print statement, we check if the length of a string is greater than or equal to the length of another string. Because the length of a string is an integer, we can use the `>=` operator. This is similar for the fourth print statement.

In the fifth print statement, we check if one arithmetic expression equals another, and on the sixth print statement, we check if the length of a string isn’t equal to a particular number.

Listing 2.33: Output for [Listing 2.32](#part0002.xhtml_code-usingrelational)

```
false
false
true
true
true
true
```

Block 2.8. *Exercises*

**Ex 1.** Print whether 82 is greater than 93.

**Ex 2.** Print whether your age is less than 15.

**Ex 3.** Print whether your name is shorter than the length of “Coronavirus”.

**Ex 4.** Print whether your age equals 12.

### [2.3.3 Logical Operators](#part0002.xhtml_uid100)

In addition to making comparisons using relational operators, Java can evaluate conditional expressions against others using **logical operators**. Logical operators are used to connect two or more expressions such that an ultimate value is decided based on the truthness of the two or more subexpressions.

Unlike relational operators, logical operators can only compare boolean values or expressions, including `true`, `false`, or boolean expressions that simplify to either `true` or `false`, such as `5 > 3` or `98 != 38`. The latter may include expressions with relational operators.

[Table 2.5](#part0002.xhtml_table-logicaltable) lists the three logical operators from greatest to least precedence that we can use to evaluate multiple smaller expressions simultaneously.

| **Operator** | **Definition** | **Example** |
| `!` | *not* - Returns the opposite of a boolean | !True ![epub/OEBPS/images/texmath/605575864c00abe7d78d98ad65404e3e9c121d1f](Images/image00400.jpeg) False |
| `&&` | *and* - Returns true if both operands are true | True && True ![epub/OEBPS/images/texmath/605575864c00abe7d78d98ad65404e3e9c121d1f](Images/image00400.jpeg) True, True && False ![epub/OEBPS/images/texmath/605575864c00abe7d78d98ad65404e3e9c121d1f](Images/image00400.jpeg) False |
| `&#124;&#124;` | *or* - Returns true if one or both operands are true | True &#124;&#124; False ![epub/OEBPS/images/texmath/605575864c00abe7d78d98ad65404e3e9c121d1f](Images/image00400.jpeg) True, False &#124;&#124; False ![epub/OEBPS/images/texmath/605575864c00abe7d78d98ad65404e3e9c121d1f](Images/image00400.jpeg) False |

Table 2.5: Logical Operators.

The latter two operators are referred to as **short-circuiting operators** because the outcome of the first operand decides whether the second boolean operand should be evaluated. These operators are generally safer, so we will stick to these. There are definitely non-short-circuiting versions of the `&&` and `||` operators, which are `&` and `|`. However, these are unsafe because both boolean operands are evaluated independently. For instance, in an `and` operation, if the runtime success of the evaluation of the second operand depended on the check for validity in the first operand, a single `&` `and` operator would be unsafe, but a `&&` operator would be much safer.

You do not need to worry about the different versions of operators, as we will simply stick to `!`, `&&`, and `||`.

[Table 2.5](#part0002.xhtml_table-logicaltable) is indicated to be ordered from greatest to least **precedence**. Because you can have multiple logical operators in a single boolean expression, operands using the `not` operator are evaluated before operands using the `and` operator, and operands using the `and` operator are evaluated before operands using the `or` operator. This works just like the order of operations with arithmetic operators.

### [2.3.4 Using `not`](#part0002.xhtml_uid102)

The `not` operator (`!`) is pretty straightforward because simply reverses a boolean value from `true` to `false` or vice versa. This operator, unlike `and` (`&&`) and `or` (`||`), is a unary operator, meaning it only needs one operand. Let’s practice the example shown in [Listing 2.34](#part0002.xhtml_code-notoperator).

Listing 2.34: Using the `!` operator.

```
public class Booleans {
    public static void main(String[] args) {
        System.out.println(!(true));
        System.out.println(!(23 == 93));
        System.out.println(!("Happy".length() != "Trails".length()));
    }
}
```

In the first print statement, we printed the opposite of `true`. In the second print statement, we printed the opposite of the equality of two numbers. The `==`, paired with the `!` on the outside, could have been grouped to simply form `!=`. In the third print statement, the length of two strings are being compared for equality, and Java prints the opposite of the result of that equality test.

Notice that in all the `not` operations, all the sub-expressions using the unary operator were wrapped in parentheses. This is to ensure that the `!` operator is applied to the entire boolean expression and not accidentally a particular sub-operand in the big operand.

Listing 2.35: Output for [Listing 2.34](#part0002.xhtml_code-notoperator)

```
false
true
false
```

### [2.3.5 Using `and`](#part0002.xhtml_aid-1T3BJ)

The `and` operator requires two operands, or boolean expressions, to evaluate against each other. Only if both boolean expressions are true will the `and` operator produce a true result. [Table 2.6](#part0002.xhtml_table-andtruthtable) shows a *truth table* for all four possible combinations of true/false values for the operands.

| **First** | **`and`** | **Second** | **=** | **Outcome** |
| `true` | `&&` | `true` | = | `true` |
| `true` | `&&` | `false` | = | `false` |
| `false` | `&&` | `true` | = | `false` |
| `false` | `&&` | `false` | = | `false` |

Table 2.6: `and` truth table.

We can see that only `true` and `true` will result in a `true` outcome. An interesting thing to note is that if we convert all the `true` values to 1, all the `false` values to 0, and all the `&&` operators to a multiplication sign (`*`), we would get the following operations as demonstrated in [Table 2.7](#part0002.xhtml_table-modifiedand).

| **First** | ***** | **Second** | **=** | **Outcome** |
| 1 | * | 1 | = | 1 |
| 1 | * | 0 | = | 0 |
| 0 | * | 1 | = | 0 |
| 0 | * | 0 | = | 0 |

Table 2.7: Modified `and` truth table.

We can see that each combination multiplies out nicely. This allows us to acknowledge that using the `&&` operator is like doing multiplication; only true operands (1 * 1) will result in a true result (1).

Let’s write some boolean expressions, like the ones shown below in [Listing 2.36](#part0002.xhtml_code-andoperator), using the `and` operator.

Listing 2.36: Using the `&&` operator.

```
public class Booleans {
    public static void main(String[] args) {
        System.out.println(true && false);
        System.out.println(43 != 39 && 16 > 11);
        System.out.println(88 < 99.2 && !(53 < 21));
    }
}
```

In the first print statement, we print `true && false`. Because one of the operands is false, the entire expression will simplify to `false`.

In the second print statement, we are checking if both 43 is not equal to 39 and if 16 is greater then 11.

In the third print statement, we see that we are using both the `&&` and `!` operators. Because the `not` operator has a higher precedence, the `not` operation is performed first, and then that boolean expression is evaluated with another comparison to determine if both are true.

Listing 2.37: Output for [Listing 2.36](#part0002.xhtml_code-andoperator)

```
false
true
true
```

### [2.3.6 Using `or`](#part0002.xhtml_aid-1T3FM)

The `or` operator, like the `and` operator, requires two operands to evaluate against each other. However, unlike the `and` operator, if either operands are true, then the `or` operator will produce a true result. [Table 2.8](#part0002.xhtml_table-ortable) shows a truth table for all four possible combinations of true/false values for the operands.

| **First** | **`or`** | **Second** | **=** | **Outcome** |
| `true` | `&#124;&#124;` | `true` | = | `true` |
| `true` | `&#124;&#124;` | `false` | = | `true` |
| `false` | `&#124;&#124;` | `true` | = | `true` |
| `false` | `&#124;&#124;` | `false` | = | `false` |

Table 2.8: `or` truth table.

Let’s write some boolean expressions, like the ones shown below in [Listing 2.38](#part0002.xhtml_code-orcode), using the `or` operator.

Listing 2.38: Using the `||` operator.

```
public class Booleans {
    public static void main(String[] args) {
        System.out.println(true || false);
        System.out.println(78 == 29 && 29 < 34 || 15 < 34);
        System.out.println("Horse".length() > 3 || "Cat".length() == 3);
    }
}
```

In the first print statement, we are simply evaluating whether `true` or `false` is true. In the second print statement, we can see that we are using both the `&&` and `||` operators. Because `&&` has a greater precedence, its operands are compared first. Then, the result of the `and` operation is used as an operand in the `or` operation, and we get our result. Finally, in the third print statement, we determine if either the length of a string exceeds 3 or the length of another string equals 3.

Listing 2.39: Output for [Listing 2.38](#part0002.xhtml_code-orcode)

```
true
true
true
```

Block 2.9. *Exercises*

**Ex 1.** Print whether the length of your first name is greater than the length of your last name and your first name does not equal your last name.

**Ex 2.** Print whether the number of siblings you have is less than your age divided by 3 or whether your birth month number is greater than 6.

**Ex 3.** Print the opposite of whether 5 is greater than 6.

## [2.4 Review](#part0002.xhtml_cid12)

In this chapter, we learned about the basic types and objects, such as integers, doubles, strings, and booleans, that we can manipulate in Java. We learned about arithmetic expressions, string functions, and simplifying logical expressions. Next, we will learn how to store, use, and change our data using variables.

## [2.5 Problems](#part0002.xhtml_cid13)

#### [Problem 1](#part0002.xhtml_uid115)

Farmer John wants to protect his cows from the bovine disease COWWID-19, so he decides to purchase 3 face masks, 2 hand sanitizers, and 1 bottle of vitamin D for each of his cows. The following are the prices for each item:

*   Face masks: $0.99 each
*   Hand sanitizers: $34.99 each
*   Vitamin D bottles: $2.49 each

Given that Farmer John has 91 cows, calculate the total amount of money Farmer John will have to spend on his cows.

#### [Problem 2](#part0002.xhtml_uid119)

Farmer John has locked up his cows in quarantine to ward off the bovine disease COWWID-19, and his cows are conspiring to break out of the barn in which they are locked. They must climb over a barn door that is 293.75 feet tall, and they have a stock of ladders that are each 14.6875 feet tall. How many ladders must they attach together to successfully climb over the barn door?

#### [Problem 3](#part0002.xhtml_uid120)

Farmer John is not the brightest farmer around, and needs to find how many characters his cow, Bessie Mooman, has in her name. Find the number of characters in his cow’s name, excluding spaces.

#### [Problem 4](#part0002.xhtml_uid121)

Farmer John is learning to code, and he wants to print the names of his cows, Bessie, Marco, Ruben, Humphrey, and Gauri, on separate lines. However, he is stubborn and wants to use a single string to print his cows’ names. Write a program that, in a single string, will print these names on different lines.

#### [Problem 5](#part0002.xhtml_uid122)

Farmer John wants to take 247 of his cows to the beef museum, and he has to organize them into groups of 15. How many full groups will he have? A full group is a group of 15 cows.

# [Chapter 3 Variables](#part0003.xhtml_cid14)

In previous sections, we explored manipulating constant, static data that wouldn’t change during runtime. However, when it comes to actually storing data, we currently don’t know how we would do that.

For instance, suppose we wanted to store the name and age of a person. We don’t necessarily know what the name and age will be, but we know that they will be a `String` and `int`, respectively, and we want to perform operations and commands on the given name and age regardless of name and age.

Fortunately, Java allows us to store data using **variables**. Variables are identifiers that are assigned to various data. They are like a label sticker for an item. The label is the variable identifier, and the data is what the label refers to. This metaphor can be further expanded because it also indicates that *the variable is not the data*, but simply an identifier that points to a memory location storing the data.

You may have seen and used variables in math. For instance, you could have variables ![epub/OEBPS/images/texmath/743f23d6d6b22693e8e3093f2943d003a85812d6](Images/image00417.jpeg) and ![epub/OEBPS/images/texmath/85ba312184b4f9a17a3da2cfd79e868ca2e74ec7](Images/image00416.jpeg) such that

![epub/OEBPS/images/texmath/0097862be6fd7943373036a492ccb27073ceba05](Images/image00419.jpeg)![epub/OEBPS/images/texmath/542dcd0143ee1bcaac10b28b2457d1f6fff203d1](Images/image00420.jpeg)

These variables, ![epub/OEBPS/images/texmath/743f23d6d6b22693e8e3093f2943d003a85812d6](Images/image00417.jpeg) and ![epub/OEBPS/images/texmath/85ba312184b4f9a17a3da2cfd79e868ca2e74ec7](Images/image00416.jpeg), can then be used later in expressions such as

![epub/OEBPS/images/texmath/11edd790c10d161731be49dcf920e7710449af2f](Images/image00421.jpeg)

where you would fill in the values stored in ![epub/OEBPS/images/texmath/743f23d6d6b22693e8e3093f2943d003a85812d6](Images/image00417.jpeg) and ![epub/OEBPS/images/texmath/85ba312184b4f9a17a3da2cfd79e868ca2e74ec7](Images/image00416.jpeg) into their respective spots.

In the next few sections, we are going to explore how to create and use variables. Create a new Java project, `Variables`, and add a new class, `MakeVariables.java`. Finally, add the `main()` method to your class.

Listing 3.1: Adding the `main()` method to `MakeVariables.java`.

```
public class MakeVariables {
    public static void main(String[] args) {

    }
}
```

## [3.1 Handling variables](#part0003.xhtml_aid-2RHOL)

### [3.1.1 Creating and using variables](#part0003.xhtml_aid-2RHOP)

There are two parts to creating a variable: **declaring** and **initializing** a variable. To declare a variable, we must first write the object or primitive type we are using, like `int`, and then the variable name. Make sure to end with a semicolon.

Listing 3.2: Declaring a variable.

```
public static void main(String[] args) {
    String name;
    int age;
    double height;
}
```

When declaring a variable, the type that you specify will stay as the type of the variable for the entirety of your Java program. Therefore, in the example above, since we declared our variable `age` to be an `int`, we cannot change it to another type, such as a `double` or `boolean`.

After declaring a variable, at some point you must initialize it, or assign the variable to a value. We can practice by initializing the first variable made in [Listing 3.2](#part0003.xhtml_code-declarevar).

Listing 3.3: Initializing a variable.

```
public static void main(String[] args) {
    // Declaring variables
    String name;
    int age;
    double height;
    // Initializing variables
    name = "Johnny Appleseed";
    age = 30;
    height = 72.5;
}
```

In [Listing 3.3](#part0003.xhtml_code-initializevar), we declared `name`, `age`, and `height` to be a `String`, `int`, and `double`, respectively. Therefore, in the lines of code below our declarations, we could only assign values of the same type. If, for instance, we were to assign a `String` to `age`, we would receive an error.

Listing 3.4: Incorrectly assigning a value of a different type to a variable.

```
public static void main(String[] args) {
    // ...
    age = "Hello";
    // ...
}
```

Listing 3.5: Output for [Listing 3.4](#part0003.xhtml_code-incorrectinit)

```
Exception in thread "main" java.lang.Error: Unresolved compilation problem:
	Type mismatch: cannot convert from String to int
```

Getting back to our code in [Listing 3.3](#part0003.xhtml_code-initializevar), we can then print our variables to see the values assigned to them.

Listing 3.6: Printing our variables.

```
public static void main(String[] args) {
    // ...
    System.out.println(name);
    System.out.println(age);
    System.out.println(height);
}
```

When we use `name`, `age`, and `height`, Java looks at the memory location that each variable points to and retrieves the data stored in that memory location. This data, in our case, would be `"Johnny Appleseed"`, `30`, and `72.5`, respectively.

Listing 3.7: Output for [Listing 3.6](#part0003.xhtml_code-printvar)

```
Johnny Appleseed
30
72.5
```

There is also a shorter way to create a variable. If you already know what the value of the variable is going to be when the variable is declared, then you can declare and initialize the variable in the same line.

Listing 3.8: Declaring and initializing simultaneously.

```
public static void main(String[] args) {
    // Declaring and initializing
    String name = "Johnny Appleseed";
    int age = 30;
    double height = 72.5;
    // Printing our variables
    System.out.println(name);
    System.out.println(age);
    System.out.println(height);
}
```

In [Listing 3.8](#part0003.xhtml_code-initdec), we changed our code in the `main()` method from [Listing 3.3](#part0003.xhtml_code-initializevar) so that all our variables are declared and initialized on the same line. Therefore, when we proceed to print all our variables again, we will still see the same results, but with concise code.

Listing 3.9: Output for [Listing 3.8](#part0003.xhtml_code-initdec)

```
Johnny Appleseed
30
72.5
```

Now, suppose we had the following variables, `x`, `y`, and `z`, where all of them were integers.

Listing 3.10: Creating our variables `x`, `y`, and `z`.

```
public static void main(String[] args) {
    int x = 2;
    int y;
    int z = 14;
    // ...
    // Assigning y later on
    y = 5;
}
```

An interesting thing about declaring and initializing variables is that if multiple variables share the same type, we can declare and/or initialize them all on the same line. So, because `x`, `y`, and `z` all store `int` values, we simply have to write `int`, followed by variable initializations all on one line separated by commas. Notice that you don’t necessarily have to initialize any particular variable, you can just state that it exists but isn’t assigned to anything. We see this with the variable `y` in [Listing 3.11](#part0003.xhtml_code-samelinevar).

Listing 3.11: Creating our variables `x`, `y`, and `z` on a single line.

```
public static void main(String[] args) {
    int x = 2, y, z = 14;
    // ...
    // Assigning y later on
    y = 5
}
```

We can even modify the code above so that if we knew what `y` was immediately, we could simply assign `y` to its value to start off with.

Listing 3.12: Assigning values to variables `x`, `y`, and `z` on a single line.

```
public static void main(String[] args) {
    int x = 2, y = 5, z = 14;
}
```

**Example 1**

Let’s write a program that prints the sum, difference, product, and division of two decimals. However, instead of feeding the decimals directly into the print statement, we will use variables.

First, we must declare and initialize our two variables. We will call them `a` and `b`. You can assign these variables to any doubles.

Listing 3.13: Creating two variables, `a` and `b`.

```
public static void main(String[] args) {
    double a = 2, b = 5;
}
```

Block 3.1. Assigning `int` values to `double` variables

You may notice that when we are initializing our `double` variables, we are assigning `int` values to them. Java will do something called an *implicit conversion*. This happens when the two data types, such as an `int` and a `double`, are compatible, meaning that they are similar in context (e.g. both numbers) and you can convert the smaller value up to the larger value (e.g. `int` converts to `double`). While we can implicitly cast from an `int` to a `double`, we cannot do the same vice versa because it will cause a loss of data. We will explore this concept in [Section 3.3](#part0003.xhtml_aid-2RJJ9).

Next, we must print the various arithmetic operations performed on `a` and `b`.

Listing 3.14: Printing the sum, difference, product, and division of `a` and `b`.

```
public static void main(String[] args) {
    double a = 2, b = 5;
    System.out.println(a + b);
    System.out.println(a - b);
    System.out.println(a * b);
    System.out.println(a / b);
}
```

When we run the code in [Listing 3.14](#part0003.xhtml_code-printingoperations), we see that we get what we expected.

Listing 3.15: Output for [Listing 3.14](#part0003.xhtml_code-printingoperations)

```
7.0
-3.0
10.0
0.4
```

Now, we must ask ourselves, why did we go through all the effort to create variables if all we did was print their sum, difference, product, and quotient?

To highlight the significance of variables, change `a` and `b` to some other numbers and run your code again.

Listing 3.16: Changing `a` and `b`.

```
public static void main(String[] args) {
    double a = 9, b = 28;
    System.out.println(a + b);
    System.out.println(a - b);
    System.out.println(a * b);
    System.out.println(a / b);
}
```

Listing 3.17: Output for [Listing 3.16](#part0003.xhtml_code-changeprint)

```
37.0
-19.0
252.0
0.32142857142857145
```

After running our code again, we find that everything printed was different this time. Modifying `a` and `b` resulted in an entirely different output.

However, we can also acknowledge that when changing our variables’ values, we didn’t have to change any arithmetic operations ourselves, and they were changed themselves at runtime simply because `a` and `b` were different. This indicates that variables represent a high *abstraction*, where you don’t necessarily have to know what values are stored to execute simple operations.

**Example 2**

Suppose we want to take our first and last name, separately, as input, and print a string containing our full name. We can start by creating two variables, `first` and `last`. Unlike the previous example, we will initialize and declare our variables independently of each other, just to practice.

As briefly mentioned earlier, Strings are not primitive types, but are instead *objects* made from collections of characters. Because Strings are objects, there are slightly different ways to create strings, as indicated in [Listing 3.18](#part0003.xhtml_code-differentstrings).

Listing 3.18: Creating a string

```
// Normal string
String greet = "Hello world!";
String greetAlt = new String("Hello world!");
// Empty string
String empty = "";
String emptyAlt = new String();
```

In the first line, we create a string using the syntax we’re used to: We first provide the object name, then the variable identifier, followed by an equal sign, and finally the actual data as a string. However, this technique is a shorthand syntax for the actual way to create a new object.

In the second line, we write the same code before the equal sign, but after the equal sign, we have a `new` operator, followed by the object name repeated again, with `"Hello world!"` inside the parentheses.

The `new` operator indicates that we are creating a new object, and the `String()` code phrase is an *instantiation*, or allocation in memory, of a new `String()` object. These new terms may be confusing at first, but we will explore this concept at a further depth in a few sections.

For now, we can simply use the syntax of the first line in [Listing 3.18](#part0003.xhtml_code-differentstrings) to create our variables `first` and `last` in [Listing 3.19](#part0003.xhtml_code-makefirstlast).

Listing 3.19: Creating `first` and `last`.

```
public static void main(String[] args) {
    String first = "Johnny";
    String last = "Appleseed";
}
```

Now that we have our two variables, we can print the full name by concatenating `first` to `last`, along with a space in between.

Listing 3.20: Concatenating `first` and `last`.

```
public static void main(String[] args) {
    String first = "Johnny";
    String last = "Appleseed";
    System.out.println(first + " " + last);
}
```

Listing 3.21: Output from [Listing 3.20](#part0003.xhtml_code-concatenatenames)

```
Johnny Appleseed
```

Now, if we were to change our `first` and `last` names to different names, our code would still print the full name because we are making our code more abstract using variables.

Listing 3.22: Changing `first` and `last`.

```
public static void main(String[] args) {
    String first = "Foo";
    String last = "Bar";
    System.out.println(first + " " + last);
}
```

Listing 3.23: Output from [Listing 3.20](#part0003.xhtml_code-concatenatenames)

```
Foo Bar
```

Block 3.2. *Exercises*

**Ex 1.** Write a program that finds the sum of the squares of two numbers (![epub/OEBPS/images/texmath/fe59f5f40d38ae0dfeb9f92983db05bd06d0c76c](Images/image00422.jpeg)).

**Ex 2.** Write a program that stores two strings in variables and determines whether the length of the first string is larger than the length of the second string.

**Ex 3.** Write a program that prints the average of two `double` variables.

### [3.1.2 Modifying variables](#part0003.xhtml_aid-2RIKT)

We can modify variables in two ways: We can assign them to completely new values, or we can change a variable based on the previous value it was assigned to.

To change a variable, we simply have to assign the variable to another value, omitting the type name at the beginning.

Listing 3.24: Reassigning a variable to another value.

```
public static void main(String[] args) {
    // Creating new variable
    int number = 5;
    System.out.println(number);
    // Changing the variable
    number = 8;
    System.out.println(number);
}
```

In [Listing 3.24](#part0003.xhtml_code-reassign), we can observe that we first create a new variable on the third line, `number`, and assign it to 5. On the sixth line, we reassign `number` to 8. This is an example of where we completely change the value stored under `number`. It is important to note that once you create a variable, you cannot change its type, so you can only reassign values that share the same type as the variable.

Listing 3.25: Output for [Listing 3.24](#part0003.xhtml_code-reassign)

```
5
8
```

As mentioned earlier, we can reassign variables such that their previous stored value influences their new value. For instance, suppose we had the following code.

Listing 3.26: Creating a new variable.

```
public static void main(String[] args) {
    // Creating the number variable
    int number = 7;
    System.out.println(number);
}
```

Imagine we wanted to double the value stored in `number` in [Listing 3.26](#part0003.xhtml_code-revar). When we proceed to reassign `number` after our print statement, the value we assign to can include `number` as well. Because variables are assigned to expressions, expressions first need to simplify out completely. So, if we assigned `number` to `number * 2`, then we would first compute `number * 2`, which is ![epub/OEBPS/images/texmath/166535829ffd8a2ab09dbbe810d1a9e9c28c50d6](Images/image00423.jpeg). Therefore, the new value of `number` would be assigned to 14.

Listing 3.27: Modifying `number` using its previous value.

```
public static void main(String[] args) {
    // Creating the number variable
    int number = 7;
    System.out.println(number);
    number = number * 2;
    System.out.println(number);
}
```

Listing 3.28: Output for [Listing 3.27](#part0003.xhtml_code-prevself)

```
7
14
```

Let’s take another example of modifying variables. Suppose we wanted to find the average of the numbers 34, 76, and 12. The formula to find the average is to divide the sum of the numbers by the number of numbers in the set. We will start by finding the sum and storing it in a `double` variable, `avg`.

Listing 3.29: Assigning the sum of three numbers to a `double` variable, `avg`.

```
public static void main(String[] args) {
    double avg = 34 + 76 + 12;
}
```

Next, we need to divide `avg` by 3. We can do this by reassigning `avg` to `avg / 3`.

Listing 3.30: Dividing `avg` by 3.

```
public static void main(String[] args) {
    double avg = 34 + 76 + 12;
    avg = avg / 3;
}
```

Finally, we can print the value stored in `avg`.

Listing 3.31: Printing `avg`.

```
public static void main(String[] args) {
    double avg = 34 + 76 + 12;
    avg = avg / 3;
    System.out.println(avg);
}
```

Listing 3.32: Output for [Listing 3.31](#part0003.xhtml_code-printthree)

```
40.666666666666664
```

### [3.1.3 Shorthand operators](#part0003.xhtml_aid-2RIUQ)

Suppose we wanted to perform the following operations on an `int` variable, `num`.

Listing 3.33: Creating and modifying a variable, `num`.

```
public static void main(String[] args) {
    int num = 2;
    System.out.println(num);
    num = num + 5;
    System.out.println(num);
    num = num - 3;
    System.out.println(num);
    num = num * 14;
    System.out.println(num);
    num = num + 1;
    System.out.println(num);
    num = num - 1;
    System.out.println(num);
}
```

When we proceed to run this code, we find that we get the expected results.

Listing 3.34: Output for [Listing 3.33](#part0003.xhtml_code-crm)

```
2
7
4
56
57
56
```

However, having to perform a simple binary operation such as simply adding or subtracting one value from a variable seems verbose, since we have to take the trouble to write something like `num = num + 5`.

Java helps to alleviate this issue by providing us with **shorthand operators**. Shorthand operators help us modify our variables in a shorter manner. Instead of writing something like `num = num + 5`, because we are simply changing `num` by 5, we can instead write `num += 5`, where our `+=` operator is our shorthand operator. In plaintext, this would translate to “Add 5 to `num`” instead of “Set `num` to `num` plus 5.” Likewise, `num = num - 3` can be rewritten as `num -= 3`. We simply write our normal operator, such as `+`, `-`, `*`, `/`, or `%`, followed by an `=` sign.

Therefore, we can rewrite our first three variable reassignments using shorthand operators.

Listing 3.35: Using shorthand operators.

```
public static void main(String[] args) {
    int num = 2;
    System.out.println(num);
    num += 5;
    System.out.println(num);
    num -= 3;
    System.out.println(num);
    num *= 14;
    System.out.println(num);
    num = num + 1;
    System.out.println(num);
    num = num - 1;
    System.out.println(num);
}
```

Now, when we run this, we will still get the same results.

Listing 3.36: Output for [Listing 3.35](#part0003.xhtml_code-short)

```
2
7
4
56
57
56
```

Notice that we didn’t change the last two variable reassignments, `num = num + 1` and `num = num - 1`. This is because there are specific operators for incrementing or decrementing a variable by 1. We would instead use `num ++` to increase by 1 and `num``-``-` to decrease by 1.

```
num ++;
System.out.println(num);
num --;
System.out.println(num);
```

These unary operators are also special in that you can place them either before or after your variable. For instance, we could write the following using the `++` operator.

```
num ++;
++ num;
```

When we include the `++` operator *before* our variable, Java first adds one to our variable, and then returns the result. When we include the `++` operator *after* our variable, Java first returns the result, then adds one. This same rule applies for `–`. We can see the difference if we use `++` in a `print` statement.

Listing 3.37: Using `++` in a print statement

```
int num = 1;
// Using ++ before
System.out.println("num plus one: " + (++num));
System.out.println("--------");
// Using ++ after
num = 1;
System.out.println("Original num: " + (num++));
System.out.println("num plus one: " + num);
```

In [Listing 3.37](#part0003.xhtml_code-plusplus), we can see that applying `++` before `num` first adds one to `num`, making `num` 2. The new value for `num` is then printed in the print statement. We can also see that applying `++` after `num` doesn’t add one right away, but first allows the print statement to print the original value of `num` before adding one.

Listing 3.38: Output for [Listing 3.37](#part0003.xhtml_code-plusplus)

```
num plus 1: 2
--------
Original num: 1
num plus 1: 2
```

### [3.1.4 Immutable versus mutable](#part0003.xhtml_uid166)

We stated earlier that we could *mutate*, or change, variables by reassigning them to different values. However, this is only true in some cases.

The current method we have learned to create variables makes these variables *mutable*. However, if we wanted to make a variable *immutable*, or unable to be modified, then we need to provide the `final` keyword before we declare our variable. For instance, suppose we had the following variable.

```
int num = 5;
```

Currently, we can reassign `num` to other values.

```
int num = 5;
num = 8;
```

However, if we added `final` to the beginning of our declaration, when we attempt to run our code again, we would receive an error.

```
final int num = 5;
num = 8;
```

```
Exception in thread "main" java.lang.Error: Unresolved compilation problem:
    The final local variable num cannot be assigned. It must be blank
    and not using a compound assignment
```

Likewise, if we had another variable, `greeting`, initially assigned to `"Hello world!"`, the moment we assign this string to the variable, we cannot change it anymore.

```
final String greeting;
// Assign initial value
greeting = "Hello world!";
// Cannot change greeting anymore
greeting = "Bye!";
```

```
Exception in thread "main" java.lang.Error: Unresolved compilation problem:
    The final local variable greeting may already have been assigned
```

## [3.2 Variable scope](#part0003.xhtml_aid-2RJEE)

Java maintains a particular *flow of control*. In a class, methods such as the `main()` method can be located anywhere within the class, but within method bodies, code is read from top to bottom, left to right. How does this apply to variables?

When we first declare and initialize a local variable inside a method, the code after the variable declaration can access the value stored in the variable. For instance, we could declare and initialize the variable `number` inside the `main()` method, as shown in [Listing 3.39](#part0003.xhtml_code-beforescope), and then use it in expressions or statements.

Listing 3.39: Creating and printing `number` inside `main()`.

```
public static void main(String[] args) {
    int number = 5;
    System.out.println(number);
}
```

Listing 3.40: Output for [Listing 3.39](#part0003.xhtml_code-beforescope)

```
5
```

Now, suppose we attempted to print `number` *before* we actually declared `number`.

Listing 3.41: Printing `number` before declaration.

```
public static void main(String[] args) {
    System.out.println(number);
    int number = 5;
}
```

In [Listing 3.41](#part0003.xhtml_code-printscope), we moved the print statement one line above the declaration of `number`. Because code inside methods are read from top to bottom, `number` doesn’t exist yet when we attempt to print it. Therefore, we will receive an error when compiling and executing our code.

Listing 3.42: Output for [Listing 3.41](#part0003.xhtml_code-printscope)

```
Exception in thread "main" java.lang.Error: Unresolved compilation problem:
    number cannot be resolved to a variable
```

Thus, we must *always* make sure that our variable exists before attempting to use it.

This concept applies similarly to when we actually declare variables. Suppose we have the following code:

```
int number;
```

`number` has only been declared, not assigned. So, if we attempt to use `number` without actually assigning anything, then we would be trying to get a value from `number` when it doesn’t actually point to anything.

```
int number;
System.out.println(number);
```

```
Exception in thread "main" java.lang.Error: Unresolved compilation problem:
    The local variable number may not have been initialized
```

The main idea is that you can only use a local variable if you both declared *and* initialized the variable earlier.

## [3.3 Type casting](#part0003.xhtml_aid-2RJJ9)

For this section, create a new class, `TypeCast`, and add the `main()` method to the body of your class.

Sometimes, we may want to convert from one primitive type to another. For instance, we would perhaps want to find the `int` representation of a `char`, or convert a `float` to a `double`. These conversions are referred to as *type casting*. There are two types of conversions: *widening conversions* and *narrowing conversions*.

### [3.3.1 Widening conversions](#part0003.xhtml_aid-2RJJR)

Widening (automatic) conversions are conversions that can take place automatically, as they convert from a smaller data type to a larger data type. In Java, data types (excluding booleans) can be ordered from the smallest type to the largest type.

![epub/OEBPS/images/texmath/6f08151032bbb7aa393c84e3bc5674fb292c399a](Images/image00424.jpeg)

The notation above shows us that we can easily convert from a smaller type, like a `short`, to a larger type, like a `long`. We can demonstrate this by creating many variables, each of a different type, and assigning each variable to the previous value.

Listing 3.43: Example of widening conversion.

```
public static void main(String[] args) {
    byte b = 64;
    System.out.println(b);
    short s = b;
    System.out.println(s);
    int i = s;
    System.out.println(i);
    long l = i;
    System.out.println(l);
    float f = l;
    System.out.println(f);
    double d = f;
    System.out.println(d);
}
```

Starting with `b`, we could see that every consecutive variable, `s`, `i`, `l`, `f`, and `d` could be assigned to a smaller type.

Listing 3.44: Output for [Listing 3.43](#part0003.xhtml_code-widening)

```
64
64
64
64
64.0
64.0
```

You’ll notice in [Listing 3.43](#part0003.xhtml_code-widening) that we didn’t include `char` in our data conversion code. This is because `char` is an *unsigned 16-bit* type that works a little differently. It is legal to assign `char` variables to both character and integer *literals* through widening conversions, but we would have to use a narrowing conversion to assign an integer *variable* (not literal) to a `char` variable. This is simply because the `char` could potentially lose data.

Listing 3.45: Widening conversions for `char`.

```
public static void main(String[] args) {
    char a = 'a';
    char b = 98;
    System.out.println(a);
    System.out.println(b);
}
```

*Note: The second line’s character is `'a'`, but appears differently in the code.*

In the second line, we are assigning a normal character to `a`, but in the third line, we are assigning an `int` value to `b`, which is also a `char`. Java interprets this integer as the ASCII code value for a character, and retrives that particular character, which happens to be a `'b'`.

Listing 3.46: Output for [Listing 3.45](#part0003.xhtml_code-charconv)

```
a
b
```

### [3.3.2 Narrowing conversions](#part0003.xhtml_aid-2RJQJ)

Narrowing (explicit) conversions occur when you want to convert larger data to smaller data. This can result in the possible loss of data, which is why Java requires us to use *type-casting notation*.

![epub/OEBPS/images/texmath/0c82e25b027d3295c08d870b884c2fc1fe066e04](Images/image00425.jpeg)

To cast from a larger type to a smaller type, we must write the type we want to convert to, enclosed in parentheses, next to our data.

Listing 3.47: Example of narrowing conversion.

```
public static void main(String[] args) {
    System.out.println(34.5);
    System.out.println((int)34.5);
    System.out.println(90913 + 318983);
    System.out.println((short)(90913 + 318983));
}
```

[Listing 3.47](#part0003.xhtml_code-narrow) demonstrates what data looks like before and after explicitly casting. In the first print statement, a `double` is being printed, but in the second print statement, it is casted to an `int`. When casting a floating point value to an integer, the decimal point and any characters after will be truncated, and only the integer portion will remain.

The third print statement prints the sum of two integers. Because these numbers are automatically of the `int` type, adding two `int` values will yield an `int` result. `int` is a 32-bit type, and the sum falls just under the maximum `int` value, so the correct result is printed. However, in the fourth print statement, the entire sum is converted to a `short`, which is a 16-bit type. Since the maximum value for a `short` is ![epub/OEBPS/images/texmath/ae61b0f0df6dd8f8d8cdda18f30d4d5a567b54f6](Images/image00426.jpeg), data is lost when the `short` sum overflows, resulting in a completely different sum.

Listing 3.48: Output for [Listing 3.47](#part0003.xhtml_code-narrow)

```
34.5
34
409896
16680
```

To convert between characters and integers, we can use `(char)` around an integer.

Listing 3.49: Casting characters.

```
System.out.println((char)121);
System.out.println((char)97);
System.out.println((char)('B' + 5));
```

In the first line, we are converting the ASCII number 121 to its respective character. We are doing the same in the second line. In the third line, we first add a `char` to an `int`, and then cast the result to a `char`. This will add the ASCII numerical value of `'B'` to 5, and then map that number in the ASCII chart back to another character.

Listing 3.50: Output for [Listing 3.49](#part0003.xhtml_code-castingchar)

```
y
a
G
```

## [3.4 Review](#part0003.xhtml_cid18)

In this chapter, we learned about storing data using variables. We explored creating, using, and changing variables, and then we learned how to convert between types. Next, we will learn how to simplify repetitive code using procedural decomposition.

# [Chapter 4 Procedural Decomposition](#part0004.xhtml_aid-3Q282)

In this chapter, we are going to focus on simplifying repetitive tasks using something called **procedural decomposition**, a way of grouping similar tasks into single blocks of code. To start, create a new Java project, `ProceduralDecomposition`, and add a class, `LetterBlocks.java`, to the project.

Now, imagine we wanted to write the name “DEE” in block letters:

Listing 4.1: Writing "DEE" in `LetterBlocks.java`.

```
 1public class LetterBlocks {
 2    public static void main(String[] args) {
 3        // D
 4        System.out.println("-----");
 5        System.out.println(" |   \\");
 6        System.out.println(" |    |");
 7        System.out.println(" |   /");
 8        System.out.println("-----");
 9
10        System.out.println();
11
12        // E
13        System.out.println("+-----");
14        System.out.println("|");
15        System.out.println("+----");
16        System.out.println("|");
17        System.out.println("+-----");
18
19        System.out.println();
20
21        // E
22        System.out.println("+-----");
23        System.out.println("|");
24        System.out.println("+----");
25        System.out.println("|");
26        System.out.println("+-----");
27    }
28}
```

Our output would look like the following:

Listing 4.2: Output for [Listing 4.1](#part0004.xhtml_aid-3Q28C)

```
-----
 |   \
 |    |
 |   /
-----

+-----
|
+----
|
+-----

+-----
|
+----
|
+-----
```

When we analyze our code, we see that we are repeating lines 13 to 17 again on lines 22 to 26, simply to construct the same letter. Code duplication is undesirable because if we were to make a mistake when constructing our first “E”, we would have to make same the change for the second “E” and for any subsequent letters that pop up. Additionally, if we wanted to print “E” again, we would have to waste time and storage space rewritting the letter.

Instead, we can *decompose* our code into a method that prints the letter “D” and another method that prints the letter “E”. A *method* is a block of code in a class that outlines how a certain procedure or task should be completed. The `main()` method is an example of a procedural abstraction because Java recognizes this particular function as the “runner” method, or the main code that Java will execute on the spot.

This chapter will explore the basics of user-defined methods, particularly *static* methods.

## [4.1 Implement static methods](#part0004.xhtml_aid-3Q2FD)

Before we create our own static method, let’s review the `main()` method.

Listing 4.3: Overview of the `main()` method.

```
public static void main(String[] args) {
    // statement;
    // statement;
    // ...
    // statement;
}
```

Our main method begins with a *method signature*. The method signature contains information about what type of method we have (return-method or void-method), name of the method, and any parameters. Let’s decompose each keyword to understand its meaning.

The first keyword is `public`, which means that our method is visible both inside our Java class and from other Java classes and can be accessed as such.

The second keyword is `static`, which means that our method is a *class method*, not an *object method*. The difference is that with a class method, we don’t have to instantiate a new object, but with an object method, we first need to create an object of the class. This terminology may seem like jargon at first, but we will soon learn what they mean in [Chapter 8](#part0008.xhtml_cha-ObjectsClasses). For now, all we need to know is that if we are attempting to use a method from the body of our `main()` method, then it should most probably be a `static` method.

The third keyword is `void`. This indicates that our `main()` method doesn’t *return* anything, meaning that it doesn’t give anything back to the user but only does something. Real world examples of a void method would be “drive the car” or “turn on the light”, while non-void methods would be “what is 3 + 5?” or “tell me the weather today”.

The fourth keyword is our *method identifier*. A method identifier (name) is like a variable identifier; it is like a label we can use to refer to something. For instance, in our `main()` method, `main` is the identifier. It is how we identify our method.

The phrase in parentheses, `(String[] args)`, represent our *parameters*. Parameters are placeholder variables that we can use in our function. Then, when we proceed to call our function, we can provide *arguments* for the parameters. All parameters start with the type, followed by the parameter name. We can have as many parameters as we want.

Getting back to `LetterBlocks.java`, we can create a method for “D” and another method for “E” so that when we want to print either of these letters, we don’t have to rewrite the print statements individually.

Let’s first define a method for “D”. Create a void method, `writeD()`, and move the print statements that print “D” inside this method.

Listing 4.4: Creating the `writeD()` method.

```
 1public class LetterBlocks {
 2    public static void main(String[] args) {
 3        // Removed "D"
 4
 5        System.out.println();
 6
 7        // E
 8        System.out.println("+-----");
 9        System.out.println("|");
10        System.out.println("+----");
11        System.out.println("|");
12        System.out.println("+-----");
13
14        System.out.println();
15
16        // E
17        System.out.println("+-----");
18        System.out.println("|");
19        System.out.println("+----");
20        System.out.println("|");
21        System.out.println("+-----");
22    }
23
24    public static void writeD() {
25        // D
26        System.out.println("-----");
27        System.out.println(" |   \\");
28        System.out.println(" |    |");
29        System.out.println(" |   /");
30        System.out.println("-----");
31    }
32}
```

When we run our program, however, we find that “D” is no longer printed.

Listing 4.5: Output for [Listing 4.4](#part0004.xhtml_aid-3Q2HN)

```
+-----
|
+----
|
+-----

+-----
|
+----
|
+-----
```

This is because even though we wrote a method, we have to *call* our method in order to use it. We can simply include `writeD();` on line 3 to do this.

Listing 4.6: Using the `writeD()` method.

```
 1public class LetterBlocks {
 2    public static void main(String[] args) {
 3        writeD();
 4
 5        System.out.println();
 6
 7        // E
 8        System.out.println("+-----");
 9        System.out.println("|");
10        System.out.println("+----");
11        System.out.println("|");
12        System.out.println("+-----");
13
14        System.out.println();
15
16        // E
17        System.out.println("+-----");
18        System.out.println("|");
19        System.out.println("+----");
20        System.out.println("|");
21        System.out.println("+-----");
22    }
23
24    public static void writeD() {
25        // D
26        System.out.println("-----");
27        System.out.println(" |   \\");
28        System.out.println(" |    |");
29        System.out.println(" |   /");
30        System.out.println("-----");
31    }
32}
```

Listing 4.7: Output for [Listing 4.6](#part0004.xhtml_aid-3Q2OO)

```
-----
 |   \
 |    |
 |   /
-----

+-----
|
+----
|
+-----

+-----
|
+----
|
+-----
```

We can also write another static method, `writeE()`, that prints “E” in block letters. Then, we can replace all occurrences of print statements that are meant to print “E”. Note that we can add methods to a class in any order. For instance, in [Listing 4.8](#part0004.xhtml_code-writeE), `writeE()` can be before `writeD()` or `main()`, but we choose to place it at the end.

Listing 4.8: Implementing the `writeE()` method.

```
 1public class LetterBlocks {
 2    public static void main(String[] args) {
 3        writeD();
 4        System.out.println();
 5        writeE();
 6        System.out.println();
 7        writeE();
 8    }
 9
10    public static void writeD() {
11        // D
12        System.out.println("-----");
13        System.out.println(" |   \\");
14        System.out.println(" |    |");
15        System.out.println(" |   /");
16        System.out.println("-----");
17    }
18
19    public static void writeE() {
20        // E
21        System.out.println("+-----");
22        System.out.println("|");
23        System.out.println("+----");
24        System.out.println("|");
25        System.out.println("+-----");
26    }
27}
```

Notice on lines 5 and 7 that we have called `writeE()` twice. This will execute the code inside `writeE()` twice, demonstrating the intuitive nature of methods.

Listing 4.9: Output for [Listing 4.8](#part0004.xhtml_code-writeE)

```
-----
 |   \
 |    |
 |   /
-----

+-----
|
+----
|
+-----

+-----
|
+----
|
+-----
```

## [4.2 Flow of control](#part0004.xhtml_cid21)

Let’s go back to our most recent code in `LetterBlocks.java`.

Listing 4.10: Code in `LetterBlocks.java`.

```
public class LetterBlocks {
    public static void main(String[] args) {
        writeD();
        System.out.println();
        writeE();
        System.out.println();
        writeE();
    }

    public static void writeD() {
        // ...
    }

    public static void writeE() {
        // ...
    }
}
```

When we execute the `main()` method, we establish a *flow of control*, which is the order in which statements are executed. By default, statements are executed from top to bottom in a sequential order, and they begin with the first statement in the `main()` method.

However, when we proceed to call functions, we *change* the flow of control. For instance, when we call `writeD()` in the `main()` method, the program jumps from the method call to the code inside the method. So, by calling `writeD()`, we begin executing all the print statements inside `writeD()` that print the block letter “D”. After all the code in the `writeD()` method has finished executing, we jump back to the code where we called `writeD()` in the `main()` method, and we proceed to execute the rest of the statements (i.e. empty print statement, `writeE()`, etc.) until we have reached the end of the `main()` method. [Figure 4.1](#part0004.xhtml_fig-flowcontrol) is a flow chart depicting the order in which statements are executed.

![images/figures/flowcontrol](Images/image00427.jpeg)Figure 4.1: Flow chart indicating the flow of control in `LetterBlocks.java`.

## [4.3 Creating methods with parameters](#part0004.xhtml_aid-3Q396)

*For this section, create a new class,* *`UseParameters.java`.*

Suppose we want to find the average of three numbers. If we are going to do this multiple times throughout our code, then it makes sense to create a method, `average()` to do this. But how do we pass values to `average()`? We need to provide some kind of input to our method so it doesn’t simply find the average of strictly three numbers.

In order to pass data for a method to use, we must include *parameters* in the method signature. Parameters are like placeholder variables that we can use *only within our method* so that when we later proceed to call our method, we can fill these parameters with our own *arguments*.

Suppose we looked back at the `main()` method’s signature.

```
public static void main(String[] args)
```

We can see that inside the parentheses next to `main`, there is a *parameter*, `args`. Parameters are written exactly like variable declarations, with the exception of a semicolon. So, `args` would be a parameter of the `main()` method, and it would be of the `String[]` type.

To create a method with a *single parameter*, we can simply declare a variable inside the parentheses.

```
public static void myMethod(int number)
```

To create a method with *multiple parameters*, we can include multiple variable declarations, separated by commas.

```
public static void myMethod(int number, double decimal, boolean isPositive)
```

As we saw earlier, we also have the option of not including parameters.

```
public static void myMethod()
```

**Example 1**

Let’s begin by writing a new static void method, `average()`, in our `UseParameters` class, and including three `double` parameters, `a`, `b`, and `c`.

Listing 4.11: Defining `average()`.

```
public class UseParameters {
    public static void main(String[] args) {}

    public static void average(double a, double b, double c) {

    }
}
```

Now that we’ve given our method some parameters in [Listing 4.11](#part0004.xhtml_code-introparams), we can assume throughout the method body that `a`, `b`, and `c` store some arbitrary values, and we can find the average of those three variables.

Listing 4.12: Printing the average of `a`, `b`, and `c`.

```
public static void average(double a, double b, double c) {
    double avg = (a + b + c) / 3;
    System.out.println("The average is: " + avg);
}
```

When working with method parameters, it is always safe to assume that the method will be called with appropriate arguments for the parameters. Let’s test our method a few times by calling it with various arguments in the `main()` method.

Listing 4.13: Testing the `average` method.

```
public static void main(String[] args) {
    average(1, 2, 3);
    average(2, 5, 7);
    average(44, 52, 96);
}
```

When we called our method, we provided arguments in the exact order that our parameters were listed. So, if we took the first `average()` call, `a` was 1, `b` was 2, and `c` was 3. This remained the case for the next two method calls.

Listing 4.14: Output for [Listing 4.13](#part0004.xhtml_code-testaverage)

```
The average is: 2.0
The average is: 4.666666666666667
The average is: 64.0
```

**Example 2**

Suppose we wanted to write a method that would print a greeting to the user given the user’s name, age, and favorite hobby. The output would resemble the following:

```
Hello, {name}, who is {age} years old and likes {hobby}!
```

We can begin by create a new method, `greet()`. We would need three parameters, `name`, `age`, and `hobby`.

Listing 4.15: Creating the method signature for `greet()`.

```
public static void greet(String name, int age, String hobby) {

}
```

Next, we can use a print statement to output our greeting inside the body of `greet()` in [Listing 4.15](#part0004.xhtml_code-designgreet). Make sure to concatenate substrings where necessary.

Listing 4.16: Adding code to `greet()`.

```
public static void greet(String name, int age, String hobby) {
    System.out.println("Hello, " + name + ", who is " + age +
        " years old and likes " + hobby + "!");
}
```

Now that we have finished writing our method, we can call this method in our `main()` method with various arguments.

Listing 4.17: Testing `greet()`.

```
public static void main(String[] args) {
    greet("Johnny Appleseed", 30, "coding");
    greet("William Shakespeare", 46, "writing plays");
}
```

Listing 4.18: Output for [Listing 4.17](#part0004.xhtml_code-testgreet)

```
Hello, Johnny Appleseed, who is 30 years old and likes coding!
Hello, William Shakespeare, who is 46 years old and likes writing plays!
```

When calling your method, it is important that the argument that you are providing is the same type as its respective parameter in the method signature. Otherwise, we would receive an error. So, attempting to call `greet()` with an `int` for the name instead of a `String` would result in a compiler error.

```
public static void main(String[] args) {
    greet(49, 23, "playing tennis");
}
```

```
Exception in thread "main" java.lang.Error: Unresolved compilation problem:
    The method greet(String, int, String) in the type UseParameters is not
    applicable for the arguments (int, int, String)
```

## [4.4 Returning values](#part0004.xhtml_aid-3Q3MQ)

*For this section, create a new class,* *`ReturnMethods.java`*

So far, we have observed *void methods*, or methods that simply perform a task given a set number of arguments. However, while these methods can do what we want, we don’t have a way of getting data back from the user.

Let’s revisit our `average()` method from `UseParameters.java` as an example. Copy this method over to `ReturnMethods.java`.

```
public static void average(double a, double b, double c) {
    double avg = (a + b + c) / 3;
    System.out.println("The average is: " + avg);
}
```

This method was quite straightforward; we simply provide three numbers and `average()` calculates the average.

However, it is important to identify the issue here: our method only *prints* the average. Printing is entirely different than giving back a value to the user! When we print something, it only gets written to the standard output. Print statements are only used as visual output; they don’t actually contribute to the overall functionality of your code.

Suppose we wanted to add `average(1, 2, 3)` to `average(4, 5, 6)`. Currently, we know that we can simply call both methods respectively in our `main()` method.

Listing 4.19: Calling `average()` in the `main()` method.

```
public static void main(String[] args) {
    average(1, 2, 3);
    average(4, 5, 6);
}
```

When running this code, we will see that our two averages are printed, but we never actually added the two averages together.

Listing 4.20: Output for [Listing 4.19](#part0004.xhtml_code-callaverage)

```
The average is: 2.0
The average is: 5.0
```

If we attempted to print `average(1, 2, 3) + average(4, 5, 6)`, we would receive an error.

```
System.out.println(average(1, 2, 3) + average(4, 5, 6));
```

```
Exception in thread "main" java.lang.Error: Unresolved compilation problem:
    The operator + is undefined for the argument type(s) void, void
```

In situations like this, we must *return* values from methods. This is very similar to math functions. Suppose you have the following function:

![epub/OEBPS/images/texmath/d4d4cf3cdb80b58cf63ae1238f83b66eb4342028](Images/image00428.jpeg)

In this case, ![epub/OEBPS/images/texmath/743f23d6d6b22693e8e3093f2943d003a85812d6](Images/image00417.jpeg) is the parameter we choose to give to the function ![epub/OEBPS/images/texmath/8b520a9e85b301290d72fdce1363fa2a23792c13](Images/image00429.jpeg), and when we simplify the expression ![epub/OEBPS/images/texmath/05b5233d01fdbc1ba86e015707adfb3e29d74242](Images/image00430.jpeg) for any value of ![epub/OEBPS/images/texmath/743f23d6d6b22693e8e3093f2943d003a85812d6](Images/image00417.jpeg), this simplified result would be our *return value*.

### [4.4.1 Specifying the return type](#part0004.xhtml_uid202)

To make a method *give back* data to the user, the first thing we must do is replace the keyword `void`. Currently, we have observed methods that resemble the following:

```
public static void myMethod() {}
```

One of the keywords is `void`. We briefly learned earlier that when we specify `void` in a method signature, it means that the method cannot give anything back to the user, and is only meant to do a task.

However, in order to return a value, we must change the keyword `void` to something else. This specifically has to be the *type* of the return value. So, if we wanted to return a `double` value, we must replace `double` with `void`.

```
public static double myMethod() {}
```

Likewise, if we wanted to give back an `int` value to the user, we must replace `void` with `int`.

```
public static int myMethod() {}
```

We can also return objects instead of primitive types, as with strings.

```
public static String myMethod() {}
```

When we replace `void` with another type, it turns our method into a *return method*, meaning that it will give back a value to the user. This value *must* be the same object type as the type specified in the method signature.

Let’s apply this concept to our `average()` method in `ReturnMethods.java`. Because we want to return an average, which is a `double` value, we will replace `void` with `double`.

Listing 4.21: Replacing `void` with `double`.

```
public static double average(double a, double b, double c) {
    double avg = (a + b + c) / 3;
    System.out.println("The average is: " + avg);
}
```

However, if we attempt to compile and execute now, we will still receive an error.

Listing 4.22: Output for [Listing 4.21](#part0004.xhtml_code-voiddouble)

```
Exception in thread "main" java.lang.Error: Unresolved compilation problem:
    This method must return a result of type double
```

The important phrase to pick out from our error message is “must return a result of type double.” When we look back at our code, we can see that even though we changed the return type to `double` in the method signature, we didn’t actually give anything back to the user. Remember, a print statement is different than giving values back to the user.

### [4.4.2 The `return` statement](#part0004.xhtml_aid-3Q40S)

The second part of creating a return method is actually *returning values*. In a method, we can return, or give back, a value to the user using the `return` statement, followed by a value or expression.

```
public static int myMethod() {
    return 0;
}
```

The expression which we return *must* be the same type as what is specified in the method signature. So, if we wrote `int`, we would return an integer. If we wrote `boolean`, we would return a boolean.

```
public static boolean myMethod() {
    return true;
}
```

It is certainly possible to call a return statement in a void method, but we can only write `return`, followed by no other expression. Calling a return statement in a void method will simply halt the method altogether.

```
public static void myMethod() {
    return;
}
```

In our `average()` function, we can replace our print statement with a return statement that returns `avg` to the user.

Listing 4.23: Replacing the print statement with a return statement.

```
public static double average(double a, double b, double c) {
    double avg = (a + b + c) / 3;
    return avg;
}
```

Our method finally works, so we can rewrite our testing code in the `main()` method to see the desired results.

Listing 4.24: Rewriting our `main()` method.

```
public static void main(String[] args) {
    System.out.println(average(1, 2, 3));
    System.out.println(average(4, 5, 6));
    System.out.println(average(1, 2, 3) + average(4, 5, 6));
}
```

Notice that earlier, our method calls took up their own lines. This was because they were simply `void` methods that didn’t return anything. When we proceed to call `average()` from [Listing 4.23](#part0004.xhtml_code-printreturn), now that our method returns a value, we can use method calls in expressions that potentially contain other operands. When we call a method in an expression, such as in a print statement, the method is first executed, its return value is produced, and that value essentially replaces the method call.

Listing 4.25: Output for [Listing 4.24](#part0004.xhtml_code-rewritemain)

```
2.0
5.0
7.0
```

**Example 2**

Let’s practice writing a method that finds the distance (as a `double`) between two integer points. We will call our method `distance()`, and we will include four integer parameters, `x1`, `y1`, `x2`, and `y2`. Because we need to return a distance, we our return type will be a `double`.

Listing 4.26: Writing the method header for `distance()`.

```
public static double distance(int x1, int y1, int x2, int y2) {}
```

The formula to find the distance between two points is the following:

![epub/OEBPS/images/texmath/e30e3454c7e80e502c53134b4b42a8d6c9fbdcac](Images/image00431.jpeg)

Writing this method will also require the use of the `pow()` and `sqrt()` method from the `Math` class. Let’s break this expression into subexpressions. First, we will solve ![epub/OEBPS/images/texmath/894f7add0042ac08957e51dbd08e926ab2a4d493](Images/image00432.jpeg), then ![epub/OEBPS/images/texmath/62e5e302ea81919ff63530dfb5dbae634f6a2cd4](Images/image00433.jpeg), and finally the square root of the sum of the two previous subexpressions.

Listing 4.27: Solving our subexpressions.

```
public static double distance(int x1, int y1, int x2, int y2) {
    double x = Math.pow(x2 - x1, 2);
    double y = Math.pow(y2 - y1, 2);
}
```

Now that we have `x` and `y`, we can add those two together and return the square root.

Listing 4.28: Returning the square root of the sum of `x` and `y`.

```
public static double distance(int x1, int y1, int x2, int y2) {
    double x = Math.pow(x2 - x1, 2);
    double y = Math.pow(y2 - y1, 2);
    return Math.sqrt(x + y);
}
```

To test our method, we can print a few `distance()` calls in our `main()` method.

Listing 4.29: Testing our `distance()` method.

```
public static void main(String[] args) {
    System.out.println(distance(0, 0, 3, 4));
    System.out.println(distance(1, 2, 7, 8));
    System.out.println(distance(-9, -5, 31, 24));
}
```

When we compile and execute our code, we will receive the following output.

Listing 4.30: (Output for [Listing 4.29](#part0004.xhtml_code-testingdistance))

```
5.0
8.48528137423857
49.4064773081425
```

Block 4.1. *Exercises*

**Ex 1.** We explored the `random()` method from the `Math` class in [Section 2.1.5.4](#part0002.xhtml_aid-1T20C). However, we can sometimes find that attempting to acquire a random integer between two integers `a` and `b` can be inconvenient because we have to take the extra step of calculating various subexpressions for `b`. Write a static method, `randint()`, which takes in two integer parameters, `a` and `b`, and returns a random integer between `a` and `b` using `Math.random()`.

*Sample input:*

```
randint(1, 5)
```

*Sample output:* Any integer between 1 and 5.

```
3
```

## [4.5 Method Overloading](#part0004.xhtml_aid-3Q4GH)

Java allows us to write methods that have the same *identifier*, but with a different arrangement of parameters. For instance, we could have the following two methods:

```
public static double getTax(double price) {
    return 0.06 * price;
}
public static double getTax(double price, double discount) {
    return 0.06 * (price - discount);
}
```

In this scenario, we have two methods with the same identifier, `getTax`, and both return a `double` result. However, while the first `getTax()` method has a single `double` parameter, the second `getTax()` method has two `double` parameters, meaning that the two methods are different. Therefore, when we call the two different methods, the first call will result in the execution of the first method, and likewise with the second call.

```
public static void main(String[] args) {
    int tax;

    tax = getTax(119.99); // Call first method
    System.out.println(tax);

    tax = getTax(119.99, 20) // Call second method
    System.out.println(tax);
}
```

Writing methods that have the same identifier but different parameter types is called *method overloading*. This is a very useful feature in Java because it allows the clients of your Java programs to easily call a method with the same name but provide different arguments.

Method overloading has its limits, however. Firstly, we cannot define a `getTax()` method whose signature looks *exactly* the same as the previous.

```
// The following doesn't work
public static double getTax(double price) // Original method
public static double getTax(double price) // Overloaded method
```

Secondly, even if we modify the names of the parameters, if the order of the *types* of the parameters matches another method with the same identifier, our code won’t compile.

```
// The following doesn't work
public static double getTax(double price) // Original method
public static double getTax(double totalPrice) // Overloaded method
```

The example above doesn’t work because of the constraint we just discussed; even though the second `getTax()` method has a `totalPrice` parameter while the first has a `price` parameter, both are still `double` types, so the order of the parameters matches one another.

One way we could fix this issue is by changing the second `getTax()` method so that it takes in an integer `price`.

```
// The following will work
public static double getTax(double price) // Original method
public static double getTax(int price) // Overloaded method
```

Overall, the three ways of overloading a method are

1.  the number of parameters,
2.  the data types of your parameters, and/or
3.  the order in which your parameter data types are listed.

Following these rules will help us to make valid methods.

## [4.6 Review](#part0004.xhtml_cid25)

In this chapter, we were introduced to a very import OOP concept, procedural decomposition. We learned to allocate certain tasks to helper methods so that we could simplify potentially repetitive code. We also explored two types of methods, void and return methods, and then we identified how we could design methods with the same identifier through method overloading. In the next chapter, we will learn to execute certain blocks of code based on boolean (true/false) conditions.

# [Chapter 5 Conditionals](#part0005.xhtml_cid26)

In all object-oriented programming languages, it is important that one can decide to perform certain tasks based on whether a condition was met. For instance, perhaps we would want to tell a user that they can drive if their age was 18 or above.

In order to write conditions, we must be able to evaluate *boolean expressions* and make use of `true`/`false` values, as we learned in [Section 2.3](#part0002.xhtml_aid-1T2T3). In this particular section, we had briefly touched upon `true` and `false`, and had learned to design simple boolean expressions (i.e. `84 > 21`, `77 == 53`, etc.) that simplify to `true` or `false`. However, until now, we haven’t fully grasped the point of boolean expressions.

A *conditional statement* allows us to evaluate whether a certain condition is true or false, and based on those results, certain code will be performed. The conditional statement is the code that evaluates the condition. We can imagine these conditions as questions. For instance, we could ask ourselves: Is it cold outside? If so, then we will plan to wear a jacket. Otherwise, we will go out in shorts. Conditional statements resemble an *if-and-only-if* or *iff* clause, something that is widely observed in mathematics. This means that if and only if a condition is true will the code inside the conditional execute.

![images/figures/If_statement](Images/image00434.jpeg)Figure 5.1: Flow chart depicting a typical Java conditional statement.

The flow chart in [Figure 5.1](#part0005.xhtml_fig-If_statement) is a rudimentary perspective regarding the format for a conditional statement. According to the flow of control, the preceding code is performed first. Once the conditional statement is hit, the question, “is _____ true?” is asked.

If the answer is yes (`true`), then the code inside the conditional statement is executed. After this code finishes executing, the rest of the code is executed.

If the answer is no (`false`), then the code inside the conditional statement is skipped, and the rest of the code after but outside the conditional statement is executed.

In this chapter, we will learn to use boolean expressions, or *conditions*, to write *conditional statements*. Conditional statements will allow us to modify the *flow of control*, the order in which statements are executed in a Java program.

*For this chapter, create a new Java project called* *`Conditionals`, and create a class with a `main` method,* *`Conditional.java`.*

## [5.1 The `if` statement](#part0005.xhtml_aid-4OIS1)

To write an `if` statement, we can write the keyword `if`, followed by a boolean expression we want to evaluate in parentheses. Then, we can include opening and closing curly braces.

```
if (conditionIsTrue) {
    // Do code here
}
```

*   `if` is the keyword we use to indicate that we want to evaluate a condition.
*   `conditionIsTrue` is a boolean condition.
*   If `conditionIsTrue` simplifies to `true`, then the code inside the *body* of the conditional (i.e. `// Do code here`) will execute.
*   Notice that the body of the conditional is indented. This is not required, but is highly recommended for legibility.

**Example 1**

In this exercise, we will determine whether a person can drive given their age. We can assume that anyone who is 18 or older can drive.

In the `main()` method, let’s create an `int` variable `age`, and assign it to an arbitrary integer.

Listing 5.1: Creating an `age` variable.

```
public static void main(String[] args) {
    int age = 20;
}
```

Next, we are going to write a conditional statement. We will determine whether `age` is greater than or equal to 18.

Listing 5.2: Adding a conditional statement.

```
public static void main(String[] args) {
    int age = 20;
    if (age >= 18) {
        // Code will follow
    }
}
```

Finally, inside the body of the `if` statement, if the condition is satisfied, we will print “You can drive!” to the user.

Listing 5.3: Filling in the body of the `if` statement.

```
public static void main(String[] args) {
    int age = 20;
    if (age >= 18) {
        System.out.println("You can drive!");
    }
}
```

Let’s run our code.

Listing 5.4: Output for [Listing 5.3](#part0005.xhtml_code-youcandrive)

```
You can drive!
```

Our code printed “You can drive!” because when `age >= 18` was evaluated, `age` was 20, so this condition was `true`. Because the condition was `true`, the code in the body of the `if` statement executed.

Now, let’s change the age to a positive integer below 18.

Listing 5.5: Changing `age` so it is less than 18.

```
public static void main(String[] args) {
    int age = 14;
    if (age >= 18) {
        System.out.println("You can drive!");
    }
}
```

Let’s run our code to see the difference.

Listing 5.6: Output for [Listing 5.5](#part0005.xhtml_code-changeage)

```
---No output---
```

When we execute our code this time, we see that nothing has been printed. This is because our conditional statement failed as 14 is not greater than or equal to 18. Thus, the body of the conditional does not execute, and as there is no code following the `if` statement, the program ends.

**Example 2**

Suppose we write a method, `getTotalCost`, which takes a `double` parameter `initialPrice` and returns the final price. This final price is influenced by a potential discount and a sales tax. The sales tax is applied to the initial price regardless, but the potential discount of 20% off is only added if the price of the item is above $100.

We can start by writing our method header. We will also include a variable, `finalPrice`, which initially is assigned to `initialPrice` but changes as we factor in the discount and sales tax.

Listing 5.7: Writing the method header for `getTotalCost()`.

```
public static double getTotalCost(double initialPrice) {
    double finalPrice = initialPrice;
}
```

First, we must apply the discount, if applicable. This will require an `if` statement. The condition will be whether `finalPrice` exceeds 100. If so, we will apply the 20% discount to the price. To apply a 20% discount, we can multiply our price by 0.8.

Listing 5.8: Determining if `finalPrice` exceeds 100.

```
public static double getTotalCost(double initialPrice) {
    double finalPrice = initialPrice;
    // Add the discount
    if (finalPrice > 100) {
        finalPrice *= 0.8;
    }
}
```

After that, regardless of the price, we must factor in the sales tax. We will assume that the sales tax is 6%. This means that we can multiply `finalPrice` by 1.06.

Listing 5.9: Adding the 6% sales tax.

```
public static double getTotalCost(double initialPrice) {
    double finalPrice = initialPrice;
    // Add the discount
    if (finalPrice > 100) {
        finalPrice *= 0.8;
    }
    // Add the sales tax
    finalPrice *= 1.06;
}
```

Finally, we can return `finalPrice` to the user.

Listing 5.10: Returning `finalPrice` to the user.

```
public static double getTotalCost(double initialPrice) {
    double finalPrice = initialPrice;
    // Add the discount
    if (finalPrice > 100) {
        finalPrice *= 0.8;
    }
    // Add the sales tax
    finalPrice *= 1.06;
    // Return finalPrice
    return finalPrice;
}
```

Let’s test our code for a few sample inputs.

Listing 5.11: Testing our `getTotalCost()` method.

```
public static void main(String[] args) {
    System.out.println(getTotalCost(49.99));
    System.out.println(getTotalCost(72));
    System.out.println(getTotalCost(125));
    System.out.println(getTotalCost(159.99));
}
```

Listing 5.12: Output for [Listing 5.11](#part0005.xhtml_code-getTotalCost)

```
52.9894
76.32000000000001
106.0
135.67152000000002
```

While the results are not in a proper format, they still demonstrate that our method works properly.

## [5.2 The `else` clause](#part0005.xhtml_aid-4OJAU)

Currently, we have only observed conditional statements that execute when a condition is true. But what would we do differently if our conditional statement fails?

We can add an `else` clause to an `if` statement such that its body will execute if and only if the condition of the `if` statement is not met. This `else` clause acts as the safeguard, meaning that if the body of the `if` clause doesn’t execute, the body of the `else` clause will.

![images/figures/If_Else_statement](Images/image00435.jpeg)Figure 5.2: Flow chart depicting the usage of both an if and else clause.

In [Figure 5.2](#part0005.xhtml_fig-If_Else_statement), we have modified our previous flow chart to factor in an `else` clause. If the condition is not met, the code in the body of the `else` clause is executed, and then the rest of the code after the conditional runs.

To write an `if` statement with an `else` clause, we can write our `if` statement as usual. Then, after the closing curly brace, we include `else`, followed by another set of curly braces.

```
if (conditionIsTrue) {
    // Do code here
} else {
    // Do other code here
}
```

*   `if` is the keyword we use to indicate that we want to evaluate a condition.
*   `conditionIsTrue` is a boolean condition.
*   If `conditionIsTrue` simplifies to `true`, then the code inside the body of the conditional (i.e. `// Do code here`) will execute.
*   `else` is the keyword we use to indicate what should happen if `conditionIsTrue` is `false`. If it is `false`, then the code inside the body of the `else` clause (i.e. `//Do other code here`) will execute.

Notice that the `else` clause must be at the end of a conditional statement, if we choose to include it.

**Example 1**

Suppose we went back to the previous code we created for determining whether a person could drive.

```
int age = 14;
if (age >= 18) {
    System.out.println("You can drive!");
}
```

In this case, if `age` happens to be greater than or equal to 18, then “You can drive!” will be printed. However, we have yet to implement what should happen if the conditional fails.

We can start by adding an `else` clause to this `if` statement.

Listing 5.13: Adding the `else` clause to the `if` statement.

```
public static void main(String[] args) {
    int age = 14;
    if (age >= 18) {
        System.out.println("You can drive!");
    } else {
        // Code will follow
    }
}
```

After that, we can add another print statement in the body of the `else` clause that will tell the user that they cannot drive.

Listing 5.14: Adding code to the `else` clause.

```
public static void main(String[] args) {
    int age = 14;
    if (age >= 18) {
        System.out.println("You can drive!");
    } else {
        System.out.println("You cannot drive!");
    }
}
```

Now when we test our code for an `age` that is less than 18, our new message will be printed.

Listing 5.15: Output for [Listing 5.14](#part0005.xhtml_code-addelse)

```
You cannot drive!
```

And when we make `age` greater than or equal to 18, our original message is printed.

Listing 5.16: Testing when `age` is greater than or equal to 18.

```
// ...
int age = 20;
// ...
```

Listing 5.17: Output for [Listing 5.16](#part0005.xhtml_code-changeelse)

```
You can drive!
```

Notice that the code inside the `else` clause will execute if and only if the previous `if` clause failed. So, if `age >= 18` is `True`, then the `else` clause won’t execute.

**Example 2**

Suppose we write a method, `getMin()`, which takes two real numbers as parameters and returns the smallest out of the two.

We can begin by writing the method header.

Listing 5.18: Method header for `getMin()`.

```
public static double getMin(double x, double y) {

}
```

Next, we want to compare `x` to `y`. If `x` is less than `y`, then `x` is the smallest of the two, so we will return `x`.

Listing 5.19: Check if `x < y` is true.

```
public static double getMin(double x, double y) {
    if (x < y) {
        return x;
    }
}
```

Otherwise, we can return `y`, as `y` would then be the smallest.

Listing 5.20: Return `y` instead.

```
public static double getMin(double x, double y) {
    if (x < y) {
        return x;
    } else {
        return y;
    }
}
```

Now, when we test our code for different inputs, we get the correct minimum value.

Listing 5.21: Testing `getMin()`.

```
public static void main(String[] args) {
    System.out.println(getMin(1, 5));
    System.out.println(getMin(4.3, 2.9));
}
```

Listing 5.22: Output for [Listing 5.21](#part0005.xhtml_code-getMin)

```
1.0
2.9
```

## [5.3 The `else if` clause](#part0005.xhtml_aid-4OJO5)

Conditional statements are useful in that if the *first condition fails*, then we can evaluate *subsequent conditions* before we attempt to evaluate an `else` clause, if it exists.

For instance, suppose we wanted to construct a grading scale, where the following rules applied for converting a numerical grade to a letter grade:

*   >= 90 ![epub/OEBPS/images/texmath/605575864c00abe7d78d98ad65404e3e9c121d1f](Images/image00400.jpeg) A
*   80 - 99 ![epub/OEBPS/images/texmath/605575864c00abe7d78d98ad65404e3e9c121d1f](Images/image00400.jpeg) B
*   70 - 79 ![epub/OEBPS/images/texmath/605575864c00abe7d78d98ad65404e3e9c121d1f](Images/image00400.jpeg) C
*   60 - 69 ![epub/OEBPS/images/texmath/605575864c00abe7d78d98ad65404e3e9c121d1f](Images/image00400.jpeg) D
*   < 60 ![epub/OEBPS/images/texmath/605575864c00abe7d78d98ad65404e3e9c121d1f](Images/image00400.jpeg) F

We would first want to check if the given numerical grade is greater than or equal to 90.

```
// num has been declared and initialized earlier
String grade;
if (num >= 90) {
    grade = "A";
}
```

However, if our grade is not greater than or equal to 90, then we want to evaluate if it is, at this point, greater than or equal to 80. But this means that we must evaluate another condition.

To do this, we can use the `else if` clause. It looks and works exactly like the `if` clause, but you only include it after the preliminary `if` clause if you want to evaluate multiple cases.

```
if (condition_is_true) {
    // Do block 1 here
} else if (another_is_true) {
    // Do block 2 here
} else if (possibly_another_is_true) {
    // Do block 3 here
} else {
    // Do failsafe code here
}
```

*   Above, we begin our conditional statement with the `if` clause. We evaluate the condition there, and if it is true, we only perform the code in block 1.
*   If the first `if` clause is false, we move to the next clause, which is `else if`. Java will then evaluate the condition in this clause. If it is true, we only perform the code in block 2.
*   Likewise, if this clause is also false, we move to the next clause, which is also an `else if` clause. Note that you can have as many `else if` clauses in a conditional statement as you need, but it *must* follow the preliminary `if` clause.
*   If this clause also fails, we finally hit the `else` clause, meaning that the failsafe code is performed regardless. However, you also have the option to exclude the `else` clause if it doesn’t contribute to the functionality of your code.

**Example 1**

Let’s look back at the initial example with the grade conversions. We will now place that initial code in a method, `convert()`, which will take the numerical grade, `num`, as a parameter.

Listing 5.23: The initial `convert()` method.

```
public static String convert(int num) {
    String grade;
    if (num >= 90) {
        grade = "A";
    }
}
```

After our preliminary `if` clause, we can add subsequent `else if` clauses evaluating the next few conditions.

Listing 5.24: Adding `else if` clauses.

```
public static String convert(int num) {
    String grade;
    if (num >= 90) {
        grade = "A";
    } else if (num >= 80) {
        grade = "B";
    } else if (num >= 70) {
        grade = "C";
    } else if (num >= 60) {
        grade = "D";
    }
}
```

Next, we can add our final `else` clause to assign `grade` to `"F"`.

Listing 5.25: Adding the `else` clause.

```
public static String convert(int num) {
    String grade;
    if (num >= 90) {
        grade = "A";
    } else if (num >= 80) {
        grade = "B";
    } else if (num >= 70) {
        grade = "C";
    } else if (num >= 60) {
        grade = "D";
    } else {
        grade = "F";
    }
}
```

Finally, we can return `grade` to the user.

Listing 5.26: Returning `grade` to the user.

```
public static String convert(int num) {
    String grade;
    if (num >= 90) {
        grade = "A";
    } else if (num >= 80) {
        grade = "B";
    } else if (num >= 70) {
        grade = "C";
    } else if (num >= 60) {
        grade = "D";
    } else {
        grade = "F";
    }
    return grade;
}
```

We can test our `convert()` method from [Listing 5.26](#part0005.xhtml_code-grade) in our `main()` method.

Listing 5.27: Testing `convert()`.

```
public static void main(String[] args) {
    System.out.println(convert(70));
    System.out.println(convert(84));
    System.out.println(convert(92));
    System.out.println(convert(61));
    System.out.println(convert(59));
}
```

Listing 5.28: Output for [Listing 5.27](#part0005.xhtml_code-testconvert)

```
C
B
A
D
F
```

**Example 2**

Suppose we wanted to write a method, `numToDay()`, that takes in an integer `num` as input and returns the associated day of the week. For instance, an argument of `1` would return `"Sunday"`, `2` would return `"Monday"`, and so on, up to an argument of `7` returning `"Saturday"`. We can begin by creating our method header with an empty body.

Listing 5.29: Defining `numToDay()`.

```
public static String numToDay(int num) {

}
```

Next, we can create a conditional statement composed of eight clauses: one for each day of the week, and an eighth one in the event that the user enters a number that isn’t associated with a day of the week.

Listing 5.30: Writing out the conditional statement structure.

```
public static String numToDay(int num) {
    if (num == 1) {

    } else if (num == 2) {

    } else if (num == 3) {

    } else if (num == 4) {

    } else if (num == 5) {

    } else if (num == 6) {

    } else if (num == 7) {

    } else {

    }
}
```

Finally, in the body of each condition, we can return the respective day of the week. For the `else` clause, we will simply return `"None"`.

Listing 5.31: Returning the correct day of the week.

```
public static String numToDay(int num) {
    if (num == 1) {
        return "Sunday";
    } else if (num == 2) {
        return "Monday";
    } else if (num == 3) {
        return "Tuesday";
    } else if (num == 4) {
        return "Wednesday";
    } else if (num == 5) {
        return "Thursday";
    } else if (num == 6) {
        return "Friday";
    } else if (num == 7) {
        return "Saturday";
    } else {
        return "None";
    }
}
```

We can test our method in the `main()` method in the following manner.

Listing 5.32: Testing the `numToDay()` method from [Listing 5.31](#part0005.xhtml_code-numToDay).

```
public static void main(String[] args) {
    System.out.println(numToDay(1)); // Prints Sunday
    System.out.println(numToDay(2)); // Prints Monday
    System.out.println(numToDay(3)); // Prints Tuesday
    System.out.println(numToDay(4)); // Prints Wednesday
    System.out.println(numToDay(5)); // Prints Thursday
    System.out.println(numToDay(6)); // Prints Friday
    System.out.println(numToDay(7)); // Prints Saturday
    System.out.println(numToDay(8)); // Prints None
}
```

Listing 5.33: Output for [Listing 5.32](#part0005.xhtml_code-testNumToDay).

```
Sunday
Monday
Tuesday
Wednesday
Thursday
Friday
Saturday
None
```

## [5.4 Nested conditionals](#part0005.xhtml_aid-4OKII)

As we have demonstrated, the body of a conditional statement can include any kind of code that can normally be included outside the conditional. This includes additional conditional statements. When we place conditional statements inside the bodies of other conditional statements, we call these statements **nested conditional statements** or simply nested conditionals/`if` statements. These are quite straightforward; like any other code in the body of the other conditional, these inner conditionals will only be evaluated if the outer clause’s condition was met.

Suppose we had the following method, `ticketPrice()`, which took in two boolean parameters, `isChild` and `isBetterTicket`, and returned the price of a ticket to a concert for a specific kind of person. If the person is an adult, a normal ticket for them would cost $30, but a better ticket would cost ten dollars extra. If the person is a child, a normal ticket for them would cost $22, and a better ticket would cost five dollars extra. We can use nested conditionals to set this up, conditioning on whether the person is a child in the outside conditional and conditioning on whether the person purchased a better ticket in the inside conditional.

Listing 5.34: Implementation of nested conditionals in `ticketPrice()`.

```
public static int ticketPrice(boolean isChild, boolean isBetterTicket) {
    if (isChild) { // Person is a child
        if (isBetterTicket) { // Charge extra
            return 27;
        } else { // Charge normal amount for child
            return 22;
        }
    } else { // Person is an adult
        if (isBetterTicket) { // Charge extra
            return 40;
        } else { // Charge normal amount for adult
            return 30;
        }
    }
}
```

Our choices are initially $27, 22, 40, and 30 as the fee. The `isChild` condition narrows our choices to $27 and $22 or $40 and $30, and the `isBetterTicket` condition in both would narrow down our choices even further.

In many instances, you can either nest a conditional in another, or compare the two conditions together with an `and` operator in the same conditional clause. When approached with this scenario, you would want to use nested conditionals (one inside another) rather than two paired together (a single conditional with two conditions joined with an `and` operator) if you encounter one of two options that you must pursue:

*   Your outer conditional, in addition to nesting your inner conditional, also contains code that should run only if the outer conditional is true but regardless of whether the inner one is true; OR
*   Your inner conditional makes the same condition check inside two outer clauses (e.g. the same inner conditional in an outer `if` and outer `else` clause) but the bodies of the inner conditionals vary between each outer clause.

In the implementation of `ticketPrice()` in [Listing 5.34](#part0005.xhtml_code-ticketPrice), we found that in the bodies of both the outer `if` clause that evaluated whether `isChild` was true and its respective outer `else` clause, we coded a conditional for checking if `isBetterTicket` was true. However, in the outer `if` clause’s body, we would return 27 and 22 if `isBetterTicket` was true or false, respectively, and in the outer `else` clause’s body, we would return 40 and 30 if `isBetterTicket` was true or false, respectively. Thus, this scenario satisfied the second point made above, which is why we needed to use nested conditionals.

It will usually be quite straightforward when you need to use nested conditionals, as you would have to check certain additional conditions if previous ones are met.

## [5.5 Review](#part0005.xhtml_cid31)

In this chapter, we learned about the structure of conditional statements, including the `if`, `else if`, and `else` clauses. We also went through nested conditionals, and when to use them.

# [Chapter 6 Loops](#part0006.xhtml_aid-5N3C2)

Suppose we wanted to print `"Hello world!"` five times. We can simply write the following:

```
System.out.println("Hello world!");
System.out.println("Hello world!");
System.out.println("Hello world!");
System.out.println("Hello world!");
System.out.println("Hello world!");
```

This is quite straightforward; we just had to write the print statement five times. Now, suppose we were to increase this number to ten times. It becomes a little more tedious, but it’s still possible.

```
System.out.println("Hello world!");
System.out.println("Hello world!");
System.out.println("Hello world!");
System.out.println("Hello world!");
System.out.println("Hello world!");
System.out.println("Hello world!");
System.out.println("Hello world!");
System.out.println("Hello world!");
System.out.println("Hello world!");
System.out.println("Hello world!");
```

You can begin to see that, while we were able to print our statement ten times, we had to write the same statement that many times.

Let’s say that we wanted to now print `"Hello world!"` *n* times, where *n* is some unknown integer that is provided at runtime. At this point, our approach fails, as we need to know *n* prior to actually running our code. Consequently, we must pursue another approach.

This is the perfect example where we must use a loop to solve our issue. A **loop** is a block of code that repeats a certain number of times. There are two types of loops that we will explore: those that repeat a defined number of times, and those that repeat until a condition is met.

*For this chapter, you may create a new class,* *`Loops.java`, with the `main()` method, in your* *`BookCode`* *project. Alternatively, you can create your own class independent of a project.*

## [6.1 `for` loops](#part0006.xhtml_aid-5N3H2)

A `for` loop is a type of loop that allows the user to iterate over a block of code a certain number of times. The general form for a `for` loop is the following:

```
for (start; stop; step) {
    // Code here will loop
}
```

Let’s break this down.

*   `start` is a code statement where we create a variable to represent our starting point in the loop. This variable assignment is usually to an `int` or `double`. Additionally, this code statement will execute once, before the loop starts.
*   `stop` is a condition indicating when the loop should end. This can be any condition, but is usually a condition involving the variable in `start`. `stop` is evaluated before every iteration of a loop. If the condition is true, the code in the loop will execute. Otherwise, it won’t. So, if the loop repeats *n* times, then the condition will be checked *n+1* times.
*   `step` is a statement that modifies the variable in `start`, such as incrementing it by one. This statement is required to ensure that the `for` loop will not enter an *infinite loop* (these will be discussed later). It executes after all the code in the loop block executes. So, if the loop repeats *n* times, then the condition will be checked *n* times.

Java breaks this process into the following steps:

1.  Create the variable in `start`.
2.  Check if the condition in `stop` (usually containing the variable) is true.
3.  If so, execute the code in the code block. Otherwise, exit the loop and continue with the code after the loop.
4.  Change the variable in `step`.
5.  Repeat steps 2-4 until you get to step 2 and the condition is false. Then, in step 3, exit the loop.

We’ll run through many examples to refine our understanding of the `for` loop.

**Example 1**

Consider the example at the beginning of this chapter. We wanted to print `"Hello world!"` ten times. To do this, we can write the following:

Listing 6.1: `for` loop to print `"Hello world!"`.

```
for (int i = 0; i < 10; i++) {
    System.out.println("Hello world!");
}
```

In [Listing 6.1](#part0006.xhtml_code-forloop_helloworld), we create a variable `i`, and we assign it to 0 initially. The condition `0 < 10` is met, so we proceed to print `"Hello world!"`. Because there is nothing else in the body of the loop, we then modify `i`. In this case, we are increasing it by 1. All possible values of `i` in this loop will therefore be 0, 1, 2, 3, 4, 5, 6, 7, 8, and 9. When we increment `i` from 9 to 10 and check our condition again before executing the body of the loop, we will find that 10 is no longer less than 10, so the loop will exit.

Listing 6.2: Output for [Listing 6.1](#part0006.xhtml_code-forloop_helloworld).

```
Hello world!
Hello world!
Hello world!
Hello world!
Hello world!
Hello world!
Hello world!
Hello world!
Hello world!
Hello world!
```

If we wanted to print `"Hello world!"` twenty times instead, we would write the following:

```
for (int i = 0; i < 20; i++) {
    System.out.println("Hello world!");
}
```

**Example 2**

Rather than simply looping over a certain line of code, like a print statement, we can use the variable itself in the loop. This is what we would refer to as a **local variable**, as it is only “visible,” or usable, within the loop itself.

Suppose we wanted to print all the numbers from 3 to 12, inclusive. We can write the following:

Listing 6.3: `for` loop to print numbers.

```
for (int k = 3; k <= 12; k++) {
    System.out.println(k);
}
```

There are a few different things we did here. Our variable is called `k` instead of `i`. We can use any variable name we would like; it is simply conventional to use `i`. Additionally, `k` is assigned to 3 initially. In our condition, rather than using the `<` operator, we are using `<=`, so our code will still execute once `k` becomes 12, but it’ll stop afterwards. `k++` is still the same; we are incrementing `k` by one. Finally, in the loop body, we are printing the value of `k`.

Listing 6.4: Output for [Listing 6.3](#part0006.xhtml_code-forloop_printnumbers).

```
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
```

**Example 3**

Suppose we want to find the sum of the first 4096 integers, starting from 1. Admittedly, we can simply use the formula ![epub/OEBPS/images/texmath/6604a223e47907dc608e8a2794ab0ce97b63e45a](Images/image00436.jpeg), where ![epub/OEBPS/images/texmath/eabee36399c08cf13f8310423143e29dd26b88db](Images/image00437.jpeg), but we want to try this using a `for` loop. We can write such code in the following manner:

Listing 6.5: Sum of first 4096 integers.

```
int sum = 0;
for (int n = 1; n <= 4096; n++) {
    sum += n;
}
System.out.println(sum);
```

Let’s analyze this code. On the first line, we assign an `int` variable, `sum`, to 0. Next, we create a loop that iterates `n` from 1 to 4096, inclusive, and in the loop body, we add each value of `n` to `sum`, making it an accumulator variable (as it keeps building up). This means that we add ![epub/OEBPS/images/texmath/3e29b1afc8e2f9004d5cab4281b45d808409589c](Images/image00438.jpeg), ![epub/OEBPS/images/texmath/abfe4696eb2ca8adf7ac6f6a3dca68ff7c2a2ce7](Images/image00439.jpeg), ![epub/OEBPS/images/texmath/2e94f9ac358cf5a833a7aeb87f87f867e158d923](Images/image00440.jpeg), ![epub/OEBPS/images/texmath/526faf0fff57497708a8740b91973edc9dc0b383](Images/image00441.jpeg), and we would keep repeating this until ![epub/OEBPS/images/texmath/eabee36399c08cf13f8310423143e29dd26b88db](Images/image00437.jpeg). Finally, we print `sum`.

Listing 6.6: Output for [Listing 6.5](#part0006.xhtml_code-sum4096).

```
8390656
```

**Example 4**

In the past few examples, our loops have been increasing our loop variable by one every iteration. However, we are not limited to how we change this loop variable in the `step` portion of the loop header. For instance, if we want to print all the even numbers from 2 to 10, inclusive, we could write the following:

Listing 6.7: Print even numbers from 2 to 10.

```
for (int i = 2; i <= 10; i += 2) {
    System.out.println(i);
}
```

Notice here that we used the `+=` operator to increment `i` by 2. We could also use `-=` or similar operators, or we could write out `i = i + 2`, which also shows us that we have the additional freedom of modifying `i` in ways beyond `++`, `+=`, etc.

Listing 6.8: Output for [Listing 6.7](#part0006.xhtml_code-evens_two_ten).

```
2
4
6
8
10
```

## [6.2 `while` loops](#part0006.xhtml_aid-5N3TR)

A `while` loop is a type of loop that allows the user to iterate over a block of code until a condition is false. The general form for a `while` loop is the following:

```
while (condition) {
    // Code here will loop
}
```

Let’s break this down.

*   `while` is the keyword we use to indicate that we are using a `while` loop.
*   `condition` is a boolean expression.

Java breaks this process into the following steps:

1.  Check if `condition` is `true`. If it is `false`, stop the loop.
2.  If so, execute the body of the `while` loop *completely*.
3.  Once the body of the loop is finished executing, repeat step 1.

Note that just like with the stopping condition for a `for` loop, the condition for a `while` loop needs to eventually become false to avoid looping infinitely.

**Example 1**

Suppose we wanted to print the numbers from 10 to 15. We can write the following to accomplish this:

Listing 6.9: Print the numbers from 10 to 15.

```
int num = 10;
while (num <= 15) {
    System.out.println(num);
    num++;
}
```

We first create an integer `num` outside the loop. This is so then we can use `num` both in the condition and in the body of the `while` loop. Next, we perform a `while` loop on the condition `num <= 15`, meaning that our loop should keep iterating until `num` is greater than 15. Finally, in the body of the loop, we print `num` and increase it by one. Keep in mind that the last line, `num++`, which increases `num` by one, is very important; it keeps bringing `num` closer to 15 so that it will eventually surpass 15, thereby making the condition false. If we don’t write this, our loop will never end.

Listing 6.10: Output for [Listing 6.9](#part0006.xhtml_code-print_ten_fifteen).

```
10
11
12
13
14
15
```

Block 6.1. A reminder about `while` loops

Unless you encounter a `continue` or `break` statement in a loop (we will cover these later in this chapter), note that a `while` loop’s body must *completely* execute before the `while` condition is evaluated again. This means that if at some point the condition is true, and the body of the loop begins executing, but somewhere in the body some variables change causing the condition to be false at that instant, the `while` loop will *keep executing* the rest of the body until it has executed all the lines contained within; at this point, Java will cycle back to the condition, and now if the condition is not met, the loop will not run.

For instance, suppose we have the following:

```
int i = 0;
while (i < 3) {
    System.out.println("Previous: " + i);
    i++;
    System.out.println("Next: " + i);
}
```

One might incorrectly assume that when `i++` changes `i` from 2 to 3, the loop will end immediately, and we won’t see `"Next: 3"` in our output. However, the loop must continue until the end. Thus, we will see `"Next: 3"` being printed before the loop ends.

```
Previous: 0
Next: 1
Previous: 1
Next: 2
Previous: 2
Next: 3
```

**Example 2**

In the previous example, we printed the numbers from 10 to 15. However, this could have easily been written using a `for` loop.

```
for (int num = 10; num <= 15; num++) {
    System.out.println(num);
}
```

Now let’s try an example that demonstrates the primary usage of a `while` loop: to loop a number of times that isn’t defined by a range.

Suppose we want to write a program to roll a die until it yields a particular number. For this example, we will use the `random()` function from the `Math` class to simulate a random die roll.

In the `main()` method, we will start by initializing three variables:

Listing 6.11: Starter code for die rolling.

```
public static void main(String[] args) {
    int desired_number = 6;
    int current_roll = -1;
    int tries = 0;
}
```

*   `desired_number` is the number we want our die to yield on its top face. In this example, we want to keep rolling the die until we yield a 6, so we assign `desired_number` to 6.
*   `current_roll` represents the current top face of our die. We initially assign it to -1 so then our loop will have at least one iteration to roll a die.
*   `tries` represent the number of times we rolled the die until we got 6 as the top face value. We will print this at the end as our result.

Next, we can write our `while` loop.

Listing 6.12: `while` loop for die roll.

```
public static void main(String[] args) {
    int desired_number = 6;
    int current_roll = -1;
    int tries = 0;
    while (current_roll != desired_number) {
        current_roll = (int)(Math.random() * 6) + 1;
        tries++;
    }
    System.out.println("Number of tries: " + tries);
}
```

In our `while` loop, the header contains the condition `current_roll != desired_number`. This means that while `current_roll`’s value doesn’t equal `desired_number`, the loop will keep iterating. Once `current_roll` equals `desired_number`, the loop stops executing.

Inside the body of the loop, we write the following to retrieve a random integer between 1 and 6, inclusive (the range of numbers for a standard cube die):

```
current_roll = (int)(Math.random() * 6) + 1;
```

At this point, `current_roll` may equal `desired_number`. However, we still have `tries++` on the next line in the body of the loop, so we can’t considering exiting the loop until we run this line as well.

Finally, we print the number of tries outside the loop.

When we run this code multiple times, we will see different number of tries showing up.

Listing 6.13: Possible outputs for [Listing 6.12](#part0006.xhtml_code-while_die_roll)

```
----RUN 1----
Number of tries: 5
----RUN 2----
Number of tries: 2
----RUN 3----
Number of tries: 8
```

**Example 3**

In a loop, we may not always change a variable the same way. Let’s look at an example of this.

The *Collatz Conjecture* is a famous, unsolved mathematical conjecture defining a sequence of integers in the following manner: start with any positive integer. For any term in the sequence, if it is even, then the next term will be half of the current term. If it is odd, the next term is three times the previous term plus one. In other words, we have the following (in pseudocode):

```
n = any integer
REPEAT:
    if n is even: divide n by 2
    if n is odd: set n to 3*n+1
```

This conjecture states that any integer that begins a Collatz sequence will always reach 1. The proof is left as an exercise to the reader ;). For now, we will simply simulate the conjecture.

In the `main()` method, we can begin by assigning a number `n` to any number. We will assign it to 7 for proof of concept; you will notice that if we assign an extremely large number, the number of iterations may grow extremely large. We will also print the starting number.

Listing 6.14: Starting the Collatz conjecture simulation

```
public static void main(String[] args) {
    int n = 7;
    System.out.println("Starting with " + n);
}
```

Next, we can write the skeleton for our `while` loop.

```
while (n > 1) {

}
```

In this case, we are assuming that it is true that all numbers will eventually converge to 1, so we keep iterating until `n` equals 1.

After that, we include an `if` statement checking if our number is even by checking if it is divisible by 2. This is an instance where we show that we can write `if` statements inside loops. If `n` is even, we divide it by 2 and provide the new value to the user.

```
while (n > 1) {
    if (n % 2 == 0) {
        n /= 2;
        System.out.println("EVEN: Divide by 2 --> " + n);
    }
}
```

Otherwise, we know that `n` is odd, so we can assign `n` to one more than three times `n`, and provide the new value to the user.

```
while (n > 1) {
    if (n % 2 == 0) {
        n /= 2;
        System.out.println("EVEN: Divide by 2 --> " + n);
    } else {
        n = 3 * n + 1;
        System.out.println("ODD: n = 3*n+1 --> " + n);
    }
}
```

The final code should be the following:

Listing 6.15: Final Collatz conjecture simulation code

```
public static void main(String[] args) {
    int n = 7;
    System.out.println("Starting with " + n);
    while (n > 1) {
        if (n % 2 == 0) {
            n /= 2;
            System.out.println("EVEN: Divide by 2 --> " + n);
        } else {
            n = 3 * n + 1;
            System.out.println("ODD: n = 3*n+1 --> " + n);
        }
    }
}
```

When we run the code, we will see the following output:

Listing 6.16: Output for [Listing 6.15](#part0006.xhtml_code-collatz_final)

```
Starting with 7
ODD: n = 3*n+1 --> 22
EVEN: Divide by 2 --> 11
ODD: n = 3*n+1 --> 34
EVEN: Divide by 2 --> 17
ODD: n = 3*n+1 --> 52
EVEN: Divide by 2 --> 26
EVEN: Divide by 2 --> 13
ODD: n = 3*n+1 --> 40
EVEN: Divide by 2 --> 20
EVEN: Divide by 2 --> 10
EVEN: Divide by 2 --> 5
ODD: n = 3*n+1 --> 16
EVEN: Divide by 2 --> 8
EVEN: Divide by 2 --> 4
EVEN: Divide by 2 --> 2
EVEN: Divide by 2 --> 1
```

## [6.3 `do while` loops](#part0006.xhtml_aid-5N4JJ)

A `do while` loop is another kind of `while` loop that allows the user to iterate over a block of code while a condition is true. The key difference between a `do while` loop and a regular `while` loop is that the former first executes the block of code, and then checks the condition, while the latter checks the condition first. This means that any `do while` loop will always have at least one iteration, even if the condition is never true.

The general form for a `do while` loop is the following:

```
do {
    // Code here will loop
} while (condition);
```

Java breaks this process into the following steps:

1.  Perform the code in the `do` block.
2.  Check if `condition` is true.
3.  If so, repeat step 1.

**Example 1**

Suppose we want to print the first five positive integers. We can write the following to accomplish this:

Listing 6.17: Print the numbers from 1 to 5.

```
int num = 1;
do {
    System.out.println(num);
    num++;
} while (num <= 5);
```

In this code, we first assign `num` to 1. Next, we enter the `do while` loop, where we print `num` (which is 1) and increment it by 1. Finally, we begin the “actual” looping process where we evaluate the condition and loop accordingly.

Listing 6.18: Output for [Listing 6.17](#part0006.xhtml_code-print_dowhile).

```
1
2
3
4
5
```

Suppose we changed the first line, `int num = 1;`, so that it reads `int num = 6;`. This should obviously fail the condition. However, with a `do while` loop, we must remember that we always iterate at least once. Thus, we print 6 and stop the loop.

Listing 6.19: Assigning `num` to 6.

```
int num = 6;
do {
    System.out.println(num);
    num++;
} while (num <= 5);
```

Listing 6.20: Output for [Listing 6.19](#part0006.xhtml_code-print_dowhile_mod).

```
6
```

**Example 2**

Suppose we want to print all the digits of an integer backwards. We can do this using the “mod 10” trick:

```
let num be an integer
REPEAT:
    print num mod 10 (prints the last digit)
    floor divide num by 10 (removes the last digit)
STOP REPEATING when num equals 0
```

This is a perfect application of a `do while` loop because if `num` equals 0 to begin with, then 0 will still be correctly printed as a digit, and any other number will work for this program without issue.

We can begin by initializing the following variable:

```
int num = 4230;
```

Next, we can add a `do while` loop, where the condition evaluates whether `num` equals 0.

```
int num = 4230;
do {
    // Code will follow
} while (num != 0);
```

Finally, we can add the two lines of code that will print the last digit of the integer, and then remove it by dividing the integer by 10.

Listing 6.21: Final code to print all the digits of an integer backwards.

```
int num = 4230;
do {
    System.out.println(num % 10);
    num /= 10;
} while (num != 0);
```

Listing 6.22: Output for [Listing 6.21](#part0006.xhtml_code-printdigits)

```
0
3
2
4
```

## [6.4 Nested loops](#part0006.xhtml_aid-5N4R9)

The loops we’ve looked at currently operate in what we call “single dimensions.” This means that in any particular iteration of a loop, a statement will occur at most once. In this section, we are going to explore **nested loops**, which are loops that iterate over *multiple dimensions*. In other words, they are loops that contain loops.

The general structure might resemble the following (if we choose to use `for` loops; keep in mind that we can also use `while` loops):

```
// Some arbitrary code before outer loop
for (start; stop; step) {
    // Some arbitrary code before nested loop
    for (start2; stop2; step2) {
        // Some arbitrary code inside nested loop
    }
    // Some arbitrary code after nested loop
}
// Some arbitrary code after outer loop
```

Here, we see that we have an **outer loop** and an **inner loop**. We will use the next few examples to demonstrate how these both work.

**Example 1**

Suppose we want to print the following:

```
1 4
1 5
1 6
2 4
2 5
2 6
3 4
3 5
3 6
```

We notice a pattern: For every left number (1, 2, and 3), the right number cycles through 4, 5, and 6. So it seems like we would need a loop to take care of each cycle.

The outer loop would iterate from 1 to 3, and the inner loop would iterate from 4 to 6. You can think of it in the following way: For every row of output above, as we read from left to right, the respective number is generated as part of a further nested loop.

We know that our outer loop needs to iterate from 1 to 3, so we can write a loop for that.

```
for (int i = 1; i <= 3; i++) { // Outer loop

}
```

This covers the leftmost numbers. For each leftmost number, we need to print the rightmost number, whether it is 4, 5, or 6. Thus, we can include a nested loop iterating from 4 to 6.

```
for (int i = 1; i <= 3; i++) { // Outer loop
    for (int j = 4; j <= 6; j++) { // Nested loop

    }
}
```

Notice that the variable name for the nested loop is different than that for the outer loop. You must always make sure that any loops inside other loops use different variable names so that you don’t run into any compilation or runtime errors.

Finally, we want to print both `i` and `j` on the same lines.

Listing 6.23: Final code for nested loop.

```
for (int i = 1; i <= 3; i++) { // Outer loop
    for (int j = 4; j <= 6; j++) { // Nested loop
        System.out.println(i + " " + j);
    }
}
```

Let’s quickly analyze this code and explain why it works. Remember that in any loop, the contents of the header (e.g. the condition) are evaluated first, and then the entire body is executed. This means that if we nest a loop inside another loop, the nested loop needs to finish completely, along with any other code in the body of the outer loop, in a single iteration of the outer loop. Thus, if the outer loop has 3 iterations, and the nested loop has 5 iterations, there will be a total of ![epub/OEBPS/images/texmath/4fa070e1529b80a5c92d58e662d24c400834aaff](Images/image00442.jpeg) iterations.

Listing 6.24: Output for [Listing 6.23](#part0006.xhtml_code-nested_loop_ex1).

```
1 4
1 5
1 6
2 4
2 5
2 6
3 4
3 5
3 6
```

**Example 2**

In this example, we will show that nested loops can be great for instances where the nested loop depends on the contents of the outer loop. Suppose we want to print the following pattern:

```
*
**
***
****
*****
```

We can see that the pattern holds that on the n^(th) line, n stars are printed. For instance, on the second line, there are two stars, while on the fourth line, there are four stars. So how do we go about simulating this with loops?

The idea here would be to recognize that we would need:

*   one loop to iterate through the number of lines
*   a loop inside the previous loop to loop through the number of stars to print

We can begin by writing an outer loop for this.

Listing 6.25: Outer loop for pattern.

```
for (int i = 1; i <= 5; i++) {

}
```

This loops through the number of lines, and `i` is indicative of the current line number. Next, for each line number, we need to print that many number of stars. If `i` equals 2, then we need to print `"*"` two times on that line. If `i` equals 4, then we need to print `"*"` four times on that line. So, for any value `i`, we need to print `"*"` `i` times on that line.

We can do this by adding a nested loop, where we iterate a new variable `j` from 0 to `i`.

Listing 6.26: Adding the nested loop.

```
for (int i = 1; i <= 5; i++) {
    for (int j = 0; j < i; j++) {

    }
}
```

Next, inside this nested loop, we can print a single star.

Listing 6.27: Printing a single star in the nested loop.

```
for (int i = 1; i <= 5; i++) {
    for (int j = 0; j < i; j++) {
        System.out.print("*");
    }
}
```

Once we print all the necessary stars for a line, we need to move to the next line. We can recognize that we need to do this by adding an empty print statement under the nested loop inside the outer loop.

Listing 6.28: Separating the stars by line.

```
for (int i = 1; i <= 5; i++) {
    for (int j = 0; j < i; j++) {
        System.out.print("*");
    }
    System.out.println();
}
```

When we run this, we get the following output:

Listing 6.29: Output for [Listing 6.28](#part0006.xhtml_code-starpattern).

```
*
**
***
****
*****
```

Suppose we changed the stopping condition of the outer loop so that instead of stopping at 5, we stopped at 8.

Listing 6.30: Changing the stopping condition of the outer loop.

```
for (int i = 1; i <= 8; i++) {
    for (int j = 0; j < i; j++) {
        System.out.print("*");
    }
    System.out.println();
}
```

Before you change your own code, try to predict what might happen.

Listing 6.31: Output for [Listing 6.30](#part0006.xhtml_code-starpattern_mod).

```
*
**
***
****
*****
******
*******
********
```

**Example 3**

Now that we’ve tackled the basics of nested loops, let’s try to create a more complex pattern using stars.

```
**********
****  ****
***    ***
**      **
*        *
**      **
***    ***
****  ****
**********
```

This may seem intimidating at first, but we can easily solve this using nested loops. Let’s make a few observations first.

*   There are 9 lines in total.
*   In each line, there are 10 characters (either stars or spaces).
*   Between lines 1 and 5, the number of spaces is 0, 2, 4, 6, and 8, respectively.
*   Between lines 6 and 9, the number of spaces is 6, 4, 2, and 0, respectively.
*   In any given line, the number of stars before and after the spaces each equals half of the difference of 10 and the number of spaces. For instance, on line 4, there are 6 spaces, so the number of stars to the left and right of the spaces is ![epub/OEBPS/images/texmath/afc1b8f6c17d36ca2ab79bdb37ed05ea833c5a6c](Images/image00443.jpeg) each.

Equipped with this knowledge, we can break this process into two parts: printing lines 1-5 and lines 6-9. Let’s begin with lines 1-5. Because we know that the number of spaces maintains a certain pattern, we can construct our outer loop based on this pattern.

```
for (int spaces = 0; spaces <= 8; spaces += 2) {

}
```

Next, we must print the appropriate number of stars, followed by spaces, followed by stars again. We can calculate the number of stars using the information we declared earlier.

```
for (int spaces = 0; spaces <= 8; spaces += 2) {
    int stars = (10 - spaces) / 2;
}
```

Now, we need to add our nested loops to print the preceding stars.

```
for (int spaces = 0; spaces <= 8; spaces += 2) {
    int stars = (10 - spaces) / 2;
    for (int i = 0; i < stars; i++) {
        System.out.print("*");
    }
}
```

We can then print the appropriate number of spaces.

```
for (int spaces = 0; spaces <= 8; spaces += 2) {
    int stars = (10 - spaces) / 2;
    for (int i = 0; i < stars; i++) {
        System.out.print("*");
    }
    for (int i = 0; i < spaces; i++) {
        System.out.print(" ");
    }
}
```

Notice that we re-declared the variable `i` in both nested loops. This is fine because these two variables are not in the same scope, as the two loops are nested at the same level.

We can rewrite the nested `for` loop that we used to print the preceding stars to print the rightmost stars.

```
for (int spaces = 0; spaces <= 8; spaces += 2) {
    int stars = (10 - spaces) / 2;
    for (int i = 0; i < stars; i++) {
        System.out.print("*");
    }
    for (int i = 0; i < spaces; i++) {
        System.out.print(" ");
    }
    for (int i = 0; i < stars; i++) {
        System.out.print("*");
    }
}
```

Finally, we need to separate the lines, so we can add an empty `System.out.println()` statement to the bottom of the outer loop.

Listing 6.32: Finished code for lines 1-5.

```
for (int spaces = 0; spaces <= 8; spaces += 2) {
    int stars = (10 - spaces) / 2;
    for (int i = 0; i < stars; i++) {
        System.out.print("*");
    }
    for (int i = 0; i < spaces; i++) {
        System.out.print(" ");
    }
    for (int i = 0; i < stars; i++) {
        System.out.print("*");
    }
    System.out.println();
}
```

Next, we can implement the code to print lines 6-9. We will need to use another loop to do this. We will use the following loop header, as the number of spaces from lines 6-9 are 6, 4, 2, and 0, respectively:

```
for (int spaces = 6; spaces >= 0; spaces -= 2) {

}
```

The body of this loop is the same as what we’ve currently written, so we can simply copy-paste it into this new loop. Thus, our final code is the following:

Listing 6.33: Finished code for lines 1-9.

```
for (int spaces = 0; spaces <= 8; spaces += 2) {
    int stars = (10 - spaces) / 2;
    for (int i = 0; i < stars; i++) {
        System.out.print("*");
    }
    for (int i = 0; i < spaces; i++) {
        System.out.print(" ");
    }
    for (int i = 0; i < stars; i++) {
        System.out.print("*");
    }
    System.out.println();
}
for (int spaces = 6; spaces >= 0; spaces -= 2) {
    int stars = (10 - spaces) / 2;
    for (int i = 0; i < stars; i++) {
        System.out.print("*");
    }
    for (int i = 0; i < spaces; i++) {
        System.out.print(" ");
    }
    for (int i = 0; i < stars; i++) {
        System.out.print("*");
    }
    System.out.println();
}
```

Listing 6.34: Output for [Listing 6.33](#part0006.xhtml_aid-5N5QL).

```
**********
****  ****
***    ***
**      **
*        *
**      **
***    ***
****  ****
**********
```

Admittedly, there are better ways to write this code, seeing how we repeat code unnecessarily. The following is an alternative implementation that accomplishes the same task in fewer lines using `Math.abs()` and by iterating on relative line numbers instead of spaces. As an exercise, try to visualize out how the code will run.

Listing 6.35: Alternative code to print diamond pattern.

```
for (int line = 0; line < 9; line++) {
    int stars = Math.abs(4-line)+1;
    for (int column = 0; column < 10; column++) {
        if (column < stars || column >= 10-stars) {
            System.out.print("*");
        } else {
            System.out.print(" ");
        }
    }
    System.out.println();
}
```

## [6.5 Interrupting loops](#part0006.xhtml_aid-5N655)

Currently, we have explored loops that work to completion; in other words, any iteration we define is performed completely. Next, we will learn about two statements, `break` and `continue`, that are used to “interrupt” a loop. These statements can be used inside any kind of loop or nested loop, but should only be used within a loop.

### [6.5.1 The `break` statement](#part0006.xhtml_aid-5N65E)

The `break` statement is a loop interrupter that completely stops the execution of the loop it is directly placed in. We use it when something happens in a loop that tells us that we don’t want to loop any more.

Suppose we had the following code:

```
System.out.println("Starting");
for (int i = 0; i < 10; i++) {
    System.out.println(i);
}
System.out.println("Finished");
```

Naturally, this `for` loop will iterate from 0 to 9, inclusive, and print all the integers in this range.

```
Starting
0
1
2
3
4
5
6
7
8
9
Finished
```

However, let’s say we didn’t want to print numbers greater than or equal to 7. Admittedly, we could simply change the stopping condition in the `for` loop header. But we could also use a `break` statement.

```
System.out.println("Starting");
for (int i = 0; i < 10; i++) {
    if (i == 7) {
        System.out.println("breaking out");
        break;
    }
    System.out.println(i);
}
System.out.println("Finished");
```

Now when we run this, we will get the following output:

```
Starting
0
1
2
3
4
5
6
breaking out
Finished
```

We can see that once `i` became 7 and the `i == 7` condition became true, `"breaking out'` was printed and the loop was broken. Thus, 7, 8, and 9 were not printed and Java skipped to the code after the `for` loop.

Try making some modifications to this code (e.g. changing the condition that includes `break` or the `for` loop header) to understand what happens with break.

**Example 2**

Let’s explore a more practical use of the `break` statement. Suppose we wanted to write code to determine whether a number is prime. We would follow these steps to determine this:

```
get number
boolean isPrime = true
if number less than 2: isPrime is false
if number greater than 2 and number divisible by 2: isPrime = false
else:
    for odd number from 3 to square root of number:
        if odd number is a factor of number:
            isPrime = false
            break
print isPrime
```

Essentially, we are doing a validation by contradiction by assuming that the number is prime, and then trying to show that it isn’t prime. Notice where we include a `break` statement; when looping through odd factors of a number, if we encounter one that is a factor, we break the loop so that we don’t unnecessarily keep looping.

We can start by initializing the following variables:

Listing 6.36: Initializing variables for prime number checker.

```
int number = 79;
boolean isPrime = true;
```

Next, we need to check if our number is less than 2, or if it is greater than 2 and is even. This rules out a large set of integers.

Listing 6.37: Ruling out even integers and integers less than 2.

```
int number = 79;
boolean isPrime = true;
if (number < 2 || number > 2 && number % 2 == 0) {
    isPrime = false;
}
```

Finally, in an `else` clause, we can use a `for` loop to iterate through all possible odd factors up until the square root of `number`. We can simulate getting the square root of `number` by just iterating while the variable we’re iterating with (in this case, `odd`) times itself is less than or equal to `number`. Inside the loop, we check if `odd` is a factor of `number` using the `%` operator, and if so, we set `isPrime` to `false` and `break`.

Listing 6.38: Iterating through all possible odd factors up until the square root of `number`.

```
int number = 79;
boolean isPrime = true;
if (number < 2 || number > 2 && number % 2 == 0) {
    isPrime = false;
} else {
    for (int odd = 3; odd*odd <= number; odd += 2) {
        if (number % odd == 0) {
            isPrime = false;
            break;
        }
    }
}
System.out.println(isPrime);
```

Block 6.2. More efficient primality test using square roots

Suppose we want to determine whether a positive integer is prime. If the integer is even or less than 2, then it is automatically not prime (even integers have 2 as a factor and positive integers less than 2 include only 1, which is neither prime nor composite). If we rule out both possibilities, then we are left with checking whether there are any odd integers that divide our number. This can take a lot of time to compute if our number is extremely large, as we would have to iterate through every odd integer up to our number to check if it is a factor. Luckily, there is a trick that lets us instead iterate through every odd integer up to the *square root* of our number to check if it is a factor.

For instance, suppose we want to check if ![epub/OEBPS/images/texmath/de8f9bd68b243e670a4479dbddbb6bf4ca20bf8d](Images/image00444.jpeg) is prime. If we iterate through all the odd integers less than this number, we would expend ![epub/OEBPS/images/texmath/44b86a442d6e2c2434f8859c0d530c9d952fd169](Images/image00445.jpeg) operations before determining that this number is prime, which is quite a large number of steps. However, if we instead iterate through all the odd integers less than or equal to the square root of this number, we would expend ![epub/OEBPS/images/texmath/a2f993daa63c33b29678e89c4a3f6f43e12f6384](Images/image00446.jpeg) operations, which is significantly smaller but still produces the same result.

But why does iterating only to the square root of the number work? Suppose we wanted to check if some arbitrary positive integer ![epub/OEBPS/images/texmath/c73c684f5f2a862b406793d66db10ad57842be11](Images/image00447.jpeg) was prime. Assuming it is not prime, ![epub/OEBPS/images/texmath/c73c684f5f2a862b406793d66db10ad57842be11](Images/image00447.jpeg) can be factored into two integers ![epub/OEBPS/images/texmath/743f23d6d6b22693e8e3093f2943d003a85812d6](Images/image00417.jpeg) and ![epub/OEBPS/images/texmath/85ba312184b4f9a17a3da2cfd79e868ca2e74ec7](Images/image00416.jpeg) such that both ![epub/OEBPS/images/texmath/743f23d6d6b22693e8e3093f2943d003a85812d6](Images/image00417.jpeg) and ![epub/OEBPS/images/texmath/85ba312184b4f9a17a3da2cfd79e868ca2e74ec7](Images/image00416.jpeg) are greater than 1 and ![epub/OEBPS/images/texmath/3704f18f077273ab73c634e2b74fb2ea964db79c](Images/image00448.jpeg). We must acknowledge that both ![epub/OEBPS/images/texmath/743f23d6d6b22693e8e3093f2943d003a85812d6](Images/image00417.jpeg) and ![epub/OEBPS/images/texmath/85ba312184b4f9a17a3da2cfd79e868ca2e74ec7](Images/image00416.jpeg) cannot be greater than ![epub/OEBPS/images/texmath/ff14114b8516b5cc0308ce19e127bbf94ec0dbc8](Images/image00415.jpeg) because ![epub/OEBPS/images/texmath/6724967d43241e0b7a47159345ea676552cb748e](Images/image00449.jpeg), so ![epub/OEBPS/images/texmath/c45a977478e8fb0522ef925c42c167baffa69516](Images/image00450.jpeg) if both were greater than ![epub/OEBPS/images/texmath/ff14114b8516b5cc0308ce19e127bbf94ec0dbc8](Images/image00415.jpeg). Likewise, ![epub/OEBPS/images/texmath/743f23d6d6b22693e8e3093f2943d003a85812d6](Images/image00417.jpeg) and ![epub/OEBPS/images/texmath/85ba312184b4f9a17a3da2cfd79e868ca2e74ec7](Images/image00416.jpeg) cannot be both less than ![epub/OEBPS/images/texmath/ff14114b8516b5cc0308ce19e127bbf94ec0dbc8](Images/image00415.jpeg) because their product would then be less than ![epub/OEBPS/images/texmath/c73c684f5f2a862b406793d66db10ad57842be11](Images/image00447.jpeg). So, ![epub/OEBPS/images/texmath/743f23d6d6b22693e8e3093f2943d003a85812d6](Images/image00417.jpeg) must be greater than ![epub/OEBPS/images/texmath/ff14114b8516b5cc0308ce19e127bbf94ec0dbc8](Images/image00415.jpeg) and ![epub/OEBPS/images/texmath/85ba312184b4f9a17a3da2cfd79e868ca2e74ec7](Images/image00416.jpeg) must be less than ![epub/OEBPS/images/texmath/ff14114b8516b5cc0308ce19e127bbf94ec0dbc8](Images/image00415.jpeg), or vice versa.

Assuming ![epub/OEBPS/images/texmath/85ba312184b4f9a17a3da2cfd79e868ca2e74ec7](Images/image00416.jpeg) is the smaller integer, if we can’t find a suitable ![epub/OEBPS/images/texmath/85ba312184b4f9a17a3da2cfd79e868ca2e74ec7](Images/image00416.jpeg) that divides ![epub/OEBPS/images/texmath/c73c684f5f2a862b406793d66db10ad57842be11](Images/image00447.jpeg) while being less than or equal to ![epub/OEBPS/images/texmath/ff14114b8516b5cc0308ce19e127bbf94ec0dbc8](Images/image00415.jpeg), then ![epub/OEBPS/images/texmath/c73c684f5f2a862b406793d66db10ad57842be11](Images/image00447.jpeg) is prime. We wouldn’t need to check for ![epub/OEBPS/images/texmath/85ba312184b4f9a17a3da2cfd79e868ca2e74ec7](Images/image00416.jpeg) values that are greater because we’d be repeating our checks. Therefore, iterating only to the square root of the number works.

**Example 3**

While `break` is typically used to break out of the loop it is directly in, it can be also used in nested loop settings.

Suppose we have the following code:

```
1int i = 0, j = 0;
2for (i = 0; i < 3; i++) {
3    for (j = 0; j < 3; j++) {
4        if (i == 1 && j == 2) {
5            break;
6        }
7    }
8}
9System.out.println(i + " " + j);
```

Let’s say we want `i` to be 1 and `j` to be 2 when we print them on the last line. However, when we run this, we get the following output:

```
3 3
```

This is because the `break` statement on line 5 only halted the execution of the inner `for` loop. The outer `for` loop continued normally. Thus, when we broke, `i = 1` and `j = 2`, but because there was nothing remaining to execute in the outer `for` loop, it started another iteration where `i` increased to 2. In this new iteration, `j` was reset to 0 and was increased to 3. Finally, `i` was increased to 3 and the outer loop ended, which is why we saw `3 3` in the output.

What we should have done instead was break out of the outer loop. But how might we do this if `break` only allows us to break out of the loop it is directly in, which in this case is the nested loop?

It turns out that we can actually break out of outer loops as long as we label them. To label a loop, simply write an identifier of your choice, followed by a colon, preceding the loop you wish to label. For instance, we might call ours `outerloop`.

```
1int i = 0, j = 0;
2outerloop: for (i = 0; i < 3; i++) {
3    for (j = 0; j < 3; j++) {
4        if (i == 1 && j == 2) {
5            break;
6        }
7    }
8}
9System.out.println(i + " " + j);
```

Then, when we want to break out of `outerloop` instead of the nested loop, we can write `break outerloop`.

Listing 6.39: Breaking out of `outerloop`.

```
1int i = 0, j = 0;
2outerloop: for (i = 0; i < 3; i++) {
3    for (j = 0; j < 3; j++) {
4        if (i == 1 && j == 2) {
5            break outerloop;
6        }
7    }
8}
9System.out.println(i + " " + j);
```

When this `break` statement is called, rather than the nested loop breaking and `outerloop` proceeding normally, `outerloop` will break (along with anything inside it), and we will proceed directly to line 9 without any further iterations.

Listing 6.40: Output for [Listing 6.39](#part0006.xhtml_code-break_outerloop).

```
1 2
```

### [6.5.2 The `continue` statement](#part0006.xhtml_uid342)

The `continue` statement is a loop interrupter that stops the execution of the current iteration of the loop and proceeds to the next (if there are any remaining).

**Example 1**

Suppose we had the following code:

```
for (int i = 0; i < 10; i++) {
    if (i % 2 == 0) {
        continue;
    }
    System.out.println(i);
}
```

We are looping from 0 to 9, inclusive, but every time `i` is even, we `continue` the loop. This means that we stop executing this current iteration and proceed to the next. Because we stop the current execution, we don’t print `i`, meaning that we skip printing every even integer.

```
1
3
5
7
9
```

We could also do the same with a `while` loop.

```
int i = 0;
while (i < 10) {
    if (i % 2 == 0) {
        continue;
    }
    System.out.println(i);
    i++;
}
```

```
1
3
5
7
9
```

The `continue` statement works in the same context as the `break` statement; you can use it in any type of loop or if you are trying to continue outer loops in a nested loop setting.

## [6.6 Review](#part0006.xhtml_cid38)

In this chapter, we learned how to use loops to repeat code statements multiple times or until a condition has been met.

# [Chapter 7 Strings](#part0007.xhtml_cha-chapter_strings)

In [Section 2.2](#part0002.xhtml_aid-1T25H), we briefly went over strings, including how to print or concatenate strings, or find the length. This chapter will review some of these concepts while exploring in depth the true nature of strings, which are *collections of characters*.

To create a string variable, you can write any of the following:

Listing 7.1: Different ways to create a string variable.

```
String one = ""; // Empty string
String two = new String(); // Empty string
String three = "Hello"; // Nonempty string
String four = new String("Hello");
```

The first and third lines are the most common and preferable to use, so when creating strings, you can just use double quotation marks. In the second and fourth lines, we are introduced to the `new` keyword, which allows us to instantiate new objects from a class. We will learn more about this in [Chapter 8](#part0008.xhtml_cha-ObjectsClasses), but for now, know that this exists.

## [7.1 Characters](#part0007.xhtml_aid-6LJVL)

In Java, the `char` type is a 16-bit unsigned integer type that represents letters and symbols in accordance with the Unicode table (see Appendix [11.1](#part0011.xhtml_sec-appendix_unicode)). As such, when we create a `char` variable, we can assign it either to a letter or a positive integer on the Unicode table. Recall that characters are represented with single quotation marks (`'`), while strings are represented with double quotation marks (`"`).

The following code depicts five different ways of assigning the letter `'a'` to a variable.

Listing 7.2: Different ways of assigning a `char` variable to `’a’`.

```
char one = 'a';
char two = 97;
char three = 100 - 3;
char four = 'c' - 2;
char five = '0' + '1';
System.out.println(one);
System.out.println(two);
System.out.println(three);
System.out.println(four);
System.out.println(five);
```

Some of these seem odd, so let’s go through them.

*   `one`: This is the normal way to represent the character `'a'`.
*   `two`: As we stated, `char` is simply another integer type, so when we assign `char` variables to integers, Java will look up the character associated with the integer (base 10/decimal) on the Unicode table and assign that to the variable. According to Appendix [11.1](#part0011.xhtml_sec-appendix_unicode), 97 is associated with the character `'a'`, meaning that `two` would be assigned to `'a'`.
*   `three`: The expression `100 - 3` is evaluated first, yielding 97. From here, Java does the same thing it did in `two`’s initialization.
*   `four`: This variable assignment looks very weird, but it still works. Any math operators (e.g. `+`, `-`) used on characters would first convert these characters to their integer counterparts, and only then would the operation be performed. Thus, `'c'` is first converted to 99 (as listed in Appendix [11.1](#part0011.xhtml_sec-appendix_unicode)), and then 99 is subtracted to 2, yielding 97. After that, Java converts 97 to `'a'` using Appendix [11.1](#part0011.xhtml_sec-appendix_unicode).
*   `five`: This is yet another ridiculous but technically correct line of code. We are adding `'0'` and `'1'` as if they are both characters. It is important to note that if individual digits are enclosed by single quotation marks, **they are still characters**. In other words, `'0'` is not the same thing as 0; in fact, it is 48, according to Appendix [11.1](#part0011.xhtml_sec-appendix_unicode). Likewise, `'1'` is the same thing as 49, not 1. As we stated for `four`, we first convert these characters to their integer counter parts (48 and 49), add them up (![epub/OEBPS/images/texmath/1131132a4fb01cd08e306c8248acdbb160d85bb5](Images/image00451.jpeg)), and then convert the result to a character (![epub/OEBPS/images/texmath/0b45b247cef2f2bb837dbb6f13f00b1db2e1421c](Images/image00452.jpeg) `'a'`).

Listing 7.3: Output for [Listing 7.2](#part0007.xhtml_code-charA).

```
a
a
a
a
a
```

## [7.2 String indexing](#part0007.xhtml_aid-6LK51)

Strings, as we know, are made up of characters of the `char` type. We can access these individual characters using their index. The **index** of a character in a string is the numerical location from the left (starting from 0) that the character is positioned at. The following is a breakdown of the character indices in `"Hello world"`.

| **Index** | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
| **Char** | `H` | `e` | `l` | `l` | `o` |  | `w` | `o` | `r` | `l` | `d` |

Indices always start at 0, count from left to right, and end at one less than the length of the string. Thus, we can get the last index using `string.length()-1`, if `string` is our string.

Note that indices map to character, not the other way around. In other words, indices are unique, and referencing the correct index will give you the correct character. You cannot necessarily access the correct index from a character because characters can be repeated. For instance, the letter `l` is indexed by 2, 3, and 9. There are code implementations in Java that will allow you to get the index of the n^(th) occurrence of a character, but these are not instantaneous like the implementation that allows you to access a character using an index.

To get a character at an index, we use the `charAt()` string method.

```
string.charAt(index);
```

*   `string` is a string object.
*   `charAt()` is the string method that returns the character at `index` as a `char` value.
*   `index` is an `int` value between 0 and the length of `string` minus one.

**Example 1**

Suppose we want to print the character at the fourth index of `"Hello world"`. We can write the following to accomplish this.

```
String greeting = "Hello world";
System.out.println(greeting.charAt(4));
```

We first create a string variable, `greeting`, and assign it to `"Hello world"`. Then, we use the `charAt()` string method to print the character at the fourth index of `greeting`. Because strings are zero-indexed (i.e. start from index 0), we will print the fifth character, which is `'o'`.

```
o
```

We can also accomplish the same in a single line if we don’t assign a variable to `"Hello world"`, but access its fourth index directly. Remember that we can do this because variables are simply references to objects that make it easier for us to use them.

```
System.out.println("Hello world".charAt(4));
```

**Example 2**

Suppose we want to write a function that returns the last character in any string. We can start with the function skeleton below:

```
public static char lastChar(String str) {

}
```

Our return type is `char` because we are returning a `char` value, we call our function `lastChar`, and we take in a single parameter, `str`, as it is our String that we want to return the last character of.

Next, we can write the following:

```
public static char lastChar(String str) {
    return str.charAt(str.length()-1);
}
```

On line 2, we are using `charAt()` to access the last character in `str`. The index we are providing is the length of the string minus one. Remember that we earlier stated that the last index will always be the length of the string minus one.

Finally, in the `main()` method, we can test our function.

Listing 7.4: Testing the `lastChar()` function.

```
public static void main(String[] args) {
    System.out.println(lastChar("Hello world"));
    System.out.println(lastChar("Good morning"));
    System.out.println(lastChar("Java"));
}
```

Listing 7.5: Output for [Listing 7.4](#part0007.xhtml_code-lastChar).

```
d
g
a
```

What if we tried to run this function with an empty string?

```
public static void main(String[] args) {
    System.out.println(lastChar("Hello world"));
    System.out.println(lastChar("Good morning"));
    System.out.println(lastChar("Java"));
    System.out.println(lastChar(""));
}
```

Because the string is empty, its length is 0, so if we take its length minus one, we get an index of -1, which isn’t possible because indices only span from 0 to the length of the string minus one, and the latter must be greater than or equal to the former. Thus, we arrive at the following `StringIndexOutOfBoundsException` error (your line numbers may vary):

```
Exception in thread "main" java.lang.StringIndexOutOfBoundsException:
        String index out of range: -1
    at java.base/java.lang.StringLatin1.charAt(StringLatin1.java:47)
    at java.base/java.lang.String.charAt(String.java:693)
    at Strings.lastChar(Strings.java:10)
    at Strings.main(Strings.java:6)

Process finished with exit code 1
```

“String index out of range: -1” means that we attempted to access index -1, which wasn’t valid. To fix this, in `lastChar()`, we must write a conditional statement that checks if the length of the string is 0. If so, we should return a null char (which can be expressed as the integer 0).

Listing 7.6: Modifying `lastChar()`.

```
public static char lastChar(String str) {
    if (str.length() == 0) {
        return 0;
    }
    return str.charAt(str.length()-1);
}
```

On line 2, we check if the length of `str` is 0. If so, we return 0, which will be converted to an empty char because of the specified `char` return type. We didn’t need to put line 5 in an `else` clause because if line 2 is true, then line 3 will completely stop the execution of `lastChar()`

Now if we write the following in `main()`, our code should work.

```
public static void main(String[] args) {
    System.out.println(lastChar("Hello world"));
    System.out.println(lastChar("Good morning"));
    System.out.println(lastChar("Java"));
    System.out.println(lastChar(""));
}
```

```
d
g
a 
```

Note that with IntelliJ, you might see a 0 with a cross-mark instead of an empty space; this still indicates that it is an empty character.

## [7.3 Substrings](#part0007.xhtml_aid-6LKIA)

In addition to getting single characters from a string, we can retrieve contiguous parts of a string, or **substrings**. For instance, “Hello” and “world” are both substrings of “Hello world”. To get a substring from a string, we would use the `substring()` string method. There are two versions of this method that are possible using method overloading (see [Section 4.5](#part0004.xhtml_aid-3Q4GH)).

```
str.substring(startIndex)
str.substring(startIndex, endIndex)
```

*   `str` is a string object.
*   `substring()` is the string method.
*   We can provide one or two arguments. If we provide one argument, then the `substring()` function in line 1 will be used, where `startIndex` is the starting integer index of the substring. This will return a substring from this index to the end. If we provide two arguments, then the `substring()` function in line 2 will be used, where `startIndex` is the lower bound (inclusive) and `endIndex` is the upper bound (exclusive) for the substring. This will return a substring from the lower bound to the upper bound.

Note that substrings of strings are also `String` objects.

**Example 1**

Suppose we wanted to get the substring `"world"` from `"Hello world"`. Because the substring `"world"` ends at the end of the original string, we can use the `substring()` method with one argument. The `startIndex` argument would be 6 because the `'w'` in `"Hello world"` is at index 6.

```
String greeting = "Hello world";
System.out.println(greeting.substring(6));
```

Alternatively, we can write this in a single line by using the string directly rather than creating a variable.

```
System.out.println("Hello world".substring(6));
```

For both code blocks, we will receive the following output:

```
world
```

If we change the starting index to something else, like 3, we will receive the following output:

```
System.out.println("Hello world".substring(3));
```

```
lo world
```

Of course, we must make sure that we provide a valid index (between 0 and the length of the string). For instance, if we change the starting index to 24, which is obviously not valid given that the length of the string is 11, we would receive the following output (your line numbers may vary):

```
System.out.println("Hello world".substring(24));
```

```
Exception in thread "main" java.lang.StringIndexOutOfBoundsException:
        String index out of range: -13
    at java.base/java.lang.String.substring(String.java:1841)
    at Strings.main(Strings.java:3)
```

**Example 2**

Suppose we had the following string:

```
String phrase = "programmatically";
```

Let’s say we want to print the substring `"gram"` from `phrase`. Because `"gram"` doesn’t trail to the end of `phrase`, but is instead somewhere in the middle, we must use the `substring()` method with two arguments. The `'g'` in `"gram"` is at index 3, and the `'m'` in `"gram"` is at index 6. Because the ending index argument in `substring()` is exclusive, we need to provide 7 instead of 6 for this argument.

Listing 7.7: Using the `substring()` method with two arguments.

```
String phrase = "programmatically";
System.out.println(phrase.substring(3,7));
```

Listing 7.8: Output for [Listing 7.7](#part0007.xhtml_code-substring_two_arg).

```
gram
```

**Example 3**

Let’s write a function to take a string and return a new string that is the concatenation of the right half of the original string with the left half.

We can start by creating our method header. We will call our method `rightLeft()`, the return type will be `String`, and we will take one `String` argument, `str`.

```
public static String rightLeft(String str) {

}
```

Next, we can access both the left and right halves of `str`. The left half will span from index 0 to half of the length of the string, and the right half will span from half of the length of the string to the end. Therefore, we can use the `substring()` method with two parameters for the left half, and the `substring()` method with one parameter for the right half.

```
public static String rightLeft(String str) {
    String left = str.substring(0, str.length()/2);
    String right = str.substring(str.length()/2);
}
```

Finally, we can return `right` concatenated with `left`.

Listing 7.9: Final `rightLeft()` function.

```
public static String rightLeft(String str) {
    String left = str.substring(0, str.length()/2);
    String right = str.substring(str.length()/2);
    return right + left;
}
```

In `main()`, we can test `rightLeft()` with a few strings.

Listing 7.10: Testing `rightLeft()`.

```
public static void main(String[] args) {
    System.out.println(rightLeft("program"));
    System.out.println(rightLeft("Java"));
    System.out.println(rightLeft("intelligent"));
}
```

Listing 7.11: Output for [Listing 7.10](#part0007.xhtml_code-test_rightLeft).

```
grampro
vaJa
ligentintel
```

## [7.4 Using loops with strings](#part0007.xhtml_aid-6LKVA)

In the world of computer science, data is often provided to developers in the form of strings. In these strings, developers must search for particular features, including first or n^(th) occurrences of characters, repeated characters, palindromic qualities, etc. Finding many of these features requires searching through a string. Luckily, we can use a combination of string indexing and loops to do this efficiently.

**Example 1**

Suppose we want to print all the characters in a string on their own lines. Using a `for` loop, we can iterate through indices from 0 to the length of the string. In each iteration, we can use the `charAt()` function to print the character.

```
String greeting = "Hello";

// Iterate through every index i
for (int i = 0; i < greeting.length(); i++) {
    // Print character at index i
    System.out.println(greeting.charAt(i));
}
```

```
H
e
l
l
o
```

**Example 2**

Suppose we want to print all the characters in a string on their own lines, but this time, we want to do this in reverse. In this case, we can use a `for` loop, but rather than iterating from 0 to the length of the string, we can start from the last index and iterate backwards.

```
String greeting = "Hello";

// Iterate backward through every index i
for (int i = greeting.length()-1; i >= 0; i--) {
    // Print character at index i
    System.out.println(greeting.charAt(i));
}
```

```
o
l
l
e
H
```

**Example 3**

In this example, let’s print every other character, starting with the first character, *on the same line*. To do this, we can start iterating from an index at 0, iterate until we reach the last index, and increment by two. Just as practice, we will use a `while` loop.

Listing 7.12: Printing every other character in a string.

```
String phrase = "Algorithm";

// While loop to iterate through every other index
int i = 0;
while (i < phrase.length()) {
    // Print character at index i
    System.out.print(phrase.charAt(i));

    // Increment i by 2
    i += 2;
}
```

Listing 7.13: Output for [Listing 7.12](#part0007.xhtml_code-print_every_other).

```
Agrtm
```

**Example 4**

We will write a function, `isPalindrome()` to determine whether a string is a palindrome. A palindrome is defined as a string such that it is the same when read both forward and backward. We will implement a case-sensitive palindrome checker (i.e. upper-case letters are different from lower-case letters).

Listing 7.14: Function header for `isPalindrome()`.

```
public static boolean isPalindrome(String str) {

}
```

After writing the method header, we can use a `for` loop to loop an index `i` from 0 to half of the length of the string.

Listing 7.15: Adding a `for` loop to `isPalindrome()`.

```
public static boolean isPalindrome(String str) {
    // Loop through indices in left half of str
    for (int i = 0; i < str.length()/2; i++) {

    }
}
```

We only need to loop through this range because we can compare the character at any index `i` to its mirrored index at `str.length()-i-1`. If the characters at these two indices are not equal, we can return `false`.

Listing 7.16: Check if characters at mirror indices are equal.

```
public static boolean isPalindrome(String str) {
    // Loop through indices in left half of str
    for (int i = 0; i < str.length()/2; i++) {
        // Check if character in left half equals
        // character in mirrored right half
        if (str.charAt(i) != str.charAt(str.length()-i-1)) {
            // Not equal; return
            return false;
        }
    }
}
```

If we loop through the entire range and never return `false`, then we know that we have a palindrome, and can return `true`.

Listing 7.17: Check if characters at mirror indices are equal.

```
public static boolean isPalindrome(String str) {
    // Loop through indices in left half of str
    for (int i = 0; i < str.length()/2; i++) {
        // Check if character in left half equals
        // character in mirrored right half
        if (str.charAt(i) != str.charAt(str.length()-i-1)) {
            // Not equal; return
            return false;
        }
    }
    // str is a palindrome
    return true;
}
```

In `main()`, we can some function calls of `isPalindrome()`.

Listing 7.18: Testing `isPalindrome()` in `main()`.

```
public static void main(String[] args) {
    System.out.println(isPalindrome("racecar"));
    System.out.println(isPalindrome("program"));
    System.out.println(isPalindrome("Level"));
    System.out.println(isPalindrome("taco cat"));
    System.out.println(isPalindrome("radar"));
}
```

Listing 7.19: Output for [Listing 7.18](#part0007.xhtml_code-testing_isPalindrome).

```
true
false
false
false
true
```

**Example 5**

Let’s write a function, `firstIndex()` to find the index of the first occurrence of a character. Because we only want the first occurrence, if we loop from beginning to end in a string and find the character we want, we can stop immediately and return whatever integer value our iterating variable is on. If we complete the loop without returning, then that means that we never found the character, so we can return -1.

We can begin by writing the method header for `firstIndex()`.

Listing 7.20: Method header for `firstIndex()`.

```
public static int firstIndex(String str, char ch) {

}
```

We are returning an `int` index value, and we are taking in two arguments, a String `str` and `char` ch, as the string we’re searching through and the character we’re looking for, respectively.

Next, we can write a `for` loop to iterate through all the indices.

Listing 7.21: Iterating through all the indices using a `for` loop.

```
public static int firstIndex(String str, char ch) {
    for (int i = 0; i < str.length(); i++) {

    }
}
```

In the `for` loop, we can see if the respective character equals `ch`. If it does, we return `i` at that index.

Listing 7.22: Checking if the character at the given index equals `ch`.

```
public static int firstIndex(String str, char ch) {
    for (int i = 0; i < str.length(); i++) {
        if (str.charAt(i) == ch) {
            // Found
            return i;
        }
    }
}
```

Otherwise, we return -1, indicating that the character is not in the string.

Listing 7.23: Checking if the character at the given index equals `ch`.

```
public static int firstIndex(String str, char ch) {
    for (int i = 0; i < str.length(); i++) {
        if (str.charAt(i) == ch) {
            // Found
            return i;
        }
    }
    // Not found
    return -1;
}
```

Let’s test this function with a few method calls.

Listing 7.24: Testing `firstIndex()` in `main()`.

```
public static void main(String[] args) {
    String greeting = "Hello world";
    System.out.println(firstIndex(greeting, 'l'));
    System.out.println(firstIndex(greeting, 'w'));
    System.out.println(firstIndex(greeting, 'q'));
    System.out.println(firstIndex(greeting, 'o'));
}
```

Listing 7.25: Output for [Listing 7.24](#part0007.xhtml_code-test_firstIndex).

```
2
6
-1
4
```

**Example 6**

Suppose we want to write a function, `containsDuplicates()`, to determine whether a string contains any duplicate characters. Because we need to compare two characters at unknown locations simultaneously (unlike the palindrome example, where we compared an unknown character to a character whose index was dependent on that of the unknown character), we will need to use nested loops.

We can begin by writing the method header.

Listing 7.26: Method header for `containsDuplicates()`.

```
public static boolean containsDuplicates(String str) {

}
```

Next, we can write the two loops, one inside the other.

Listing 7.27: Adding nested loops.

```
public static boolean containsDuplicates(String str) {
    for (int i = 0; i < str.length()-1; i++) {
        for (int j = i+1; j < str.length(); j++) {

        }
    }
}
```

Here’s how we’re using the nested loops: for each outer iteration of `i`, `j` will iterate from one more than `i` to the end. In this manner, we ensure that we’re not comparing a character to itself, and we’re not making more comparisons than we need to.

Inside the nested loop, we check whether the character at `i` equals that at `j`. If so, we return `true.`

Listing 7.28: Compare characters at indices `i` and `j`.

```
public static boolean containsDuplicates(String str) {
    for (int i = 0; i < str.length()-1; i++) {
        for (int j = i+1; j < str.length(); j++) {
            if (str.charAt(i) == str.charAt(j)) {
                // Characters are the same
                return true;
            }
        }
    }
}
```

If both `for` loops executed completely, then we didn’t find any repeats, so we return `false` outside the loops.

Listing 7.29: No duplicates after both `for` loops finish iterating.

```
public static boolean containsDuplicates(String str) {
    for (int i = 0; i < str.length()-1; i++) {
        for (int j = i+1; j < str.length(); j++) {
            if (str.charAt(i) == str.charAt(j)) {
                // Characters are the same
                return true;
            }
        }
    }
    // No duplicates
    return false;
}
```

We can now test our function in the `main()` method.

Listing 7.30: Testing `containsDuplicates()` in `main()`.

```
public static void main(String[] args) {
    System.out.println(containsDuplicates("Java"));
    System.out.println(containsDuplicates("Algorithm"));
    System.out.println(containsDuplicates("Memoization"));
    System.out.println(containsDuplicates("Python"));
}
```

Listing 7.31: Output for [Listing 7.30](#part0007.xhtml_code-test_containsDuplicates).

```
true
false
true
false
```

## [7.5 String equality](#part0007.xhtml_aid-6LM3O)

Currently, if we wanted to check if certain values were equal to each other, we could use the `==` operator.

```
4 == 4.0
true == true
'a' == 97
```

However, with strings, it’s a little different. A `String` is an object, not a primitive type, so when comparing two *objects* rather than *primitive types*, the `==` operator checks if the object references are the same. A separate method, `equals()`, exists for comparing two objects.

Consider the following code:

```
1String one = new String("abc");
2String two = new String("abc");
3String three = one;
4System.out.println(one == two);
5System.out.println(one.equals(two));
6System.out.println(one == three);
7System.out.println(one.equals(three));
8System.out.println(two == three);
9System.out.println(two.equals(three));
```

We would expect all these to be `true`, right? However, we instead get the following:

```
false
true
true
true
false
true
```

Let’s break this down.

*   **Line 1:** We assign a variable `one` to the literal `"abc"`.
*   **Line 2:** We assign a variable `two` to `"abc"` using the `String` constructor (see [Chapter 8](#part0008.xhtml_cha-ObjectsClasses) for further details). This will create a new memory reference for this literal.
*   **Line 3:** We assign a variable `three` to `one`. This assigns `three`’s reference to be the same as that of `one`.
*   **Line 4:** Because `one` and `two` are at different memory locations and thus are referenced differently (even though their string values are the same), `==` yields a `false` value.
*   **Line 5:** When we use the `equals()` method, Java compares the values of the two objects rather than the references. Thus, the result is `true`.
*   **Line 6:** `one` and `three` are referencing the same memory location that stores `"abc"`, so `==` yields `true`.
*   **Line 7:** When we use the `equals()` method, Java compares the values of the two objects rather than the references. Thus, the result is `true`.
*   **Line 8:** Because `two` and `three` are at different memory locations and thus are referenced differently (even though their string values are the same), `==` yields a `false` value.
*   **Line 9:** When we use the `equals()` method, Java compares the values of the two objects rather than the references. Thus, the result is `true`.

Thus, to be safe, use `==` when you want to check if two objects/variables are referencing the same memory location, and `equals()` when you want to check if the values of two objects are the same. With regards to strings, you can use `equals()` for most of the time.

## [7.6 String formatting](#part0007.xhtml_aid-6LMAA)

In instances where we add unknown data to strings, we need not always use concatenation, as it can be long and tedious. Additionally, we may want to format non-string information in particular ways; for example, we might want to represent decimal numbers with exactly two digits after the decimal point.

Consider the following code:

```
String name = "John Appleseed";
int age = 20;
String product = "Java coffee";
double initialPrice = 4.99;
double finalPrice = initialPrice * 1.06;
System.out.println("Product: " + name + ", Age: " + age + ", Product purchased: "
    + product + ", Final price: $" + finalPrice + ".");
```

Notice how long the final line is; we had to separate it into two lines to fit it on the page! There are so many `+` signs, and it becomes hard to keep track of everything. Additionally, when we run this code, we get the following output:

```
Product: John Appleseed, Age: 20, Product purchased: Java coffee, Final
    price: $5.2894000000000005.
```

Evidently, when we calculated `finalPrice` after adding the 6% tax to `initialPrice`, we ended up with a precision error, leading to a trail of 0’s and a 5 following the correct amount. Additionally, prices are usually indicated with two digits after the decimal point. Thus, we must fix this.

The best solution would be to use the `String.format()` static method, which resembles the following:

```
String.format(str, args)
```

*   `String.format()` is the method we use to format `str`.
*   `str` is the string we are formatting.
*   `args` is a sequence of comma-separated values, expressions, and/or variables.

In `str`, we must include certain *format specifiers*, such as `%s`, `%d`, and `%f`, that indicate where we are filling in data. This means that `str` is essentially a template string.

The typical format for a format specifier is the following:

```
%[argument_index$][flags][width][.precision]conversion
```

This may appear very confusing, but don’t worry; for the most part, anything in the brackets are unnecessary, and in floats, we may only sometimes use the `precision` argument.

### [7.6.1 Formatting strings into strings](#part0007.xhtml_uid397)

The most common format specifier is `%s`, which indicates that this position would be filled in by a string, or in fact any data type.

**Example 1**

Suppose we have the following code, and we want to replace line 4 with a `String.format()` formatted string.

```
String name = "John Appleseed";
String residence = "Geneva, Switzerland";
int age = 20;
String formattedString = "My name is " + name + ", I am " + age
    + " years old, and I live in " + residence + ".";
System.out.println(formattedString);
```

```
My name is John Appleseed, I am 20 years old, and I live in Geneva, Switzerland.
```

We can rewrite as follows:

```
String name = "John Appleseed";
String residence = "Geneva, Switzerland";
int age = 20;
String formattedString = String.format(
    "My name is %s, I am %s years old, and I live in %s.",
    name, age, residence);
System.out.println(formattedString);
```

In the updated example, our template string includes `%s` format specifiers wherever we are filling in data from outside. Then, we list out the variables in the order they are going to fill in the format specifiers. We also weren’t restricted to just strings; we included an integer in the middle. The result is the following:

```
My name is John Appleseed, I am 20 years old, and I live in Geneva, Switzerland.
```

For the most part, we will use `%s` for inputting any data into a formatted string, as it only provides the string-casted data to the string; it doesn’t enforce a specific required type as does the other format specifiers that we will explore, and it doesn’t do any additional formatting.

### [7.6.2 Formatting integers into strings](#part0007.xhtml_uid398)

If we wanted to specifically enforce that integers were formatted into strings, we would use the `%d` format specifier instead. Suppose we took the example we did previously:

```
String name = "John Appleseed";
String residence = "Geneva, Switzerland";
int age = 20;
String formattedString = String.format(
    "My name is %s, I am %s years old, and I live in %s.",
    name, age, residence);
System.out.println(formattedString);
```

We would replace the second `%s` with `%d`, revealing the same output.

```
String name = "John Appleseed";
String residence = "Geneva, Switzerland";
int age = 20;
String formattedString = String.format(
    "My name is %s, I am %d years old, and I live in %s.",
    name, age, residence);
System.out.println(formattedString);
```

The reason `%d` may be preferred in these instances is that it can be formatted with the additional arguments that we saw earlier. However, we are not going to explore these, so for integers, you may use either `%s` or `%d`.

### [7.6.3 Formatting floats into strings](#part0007.xhtml_aid-6LML2)

Even with floats, we can simply use `%s`, but there may be instances where the more refined `%f` better suits our needs.

Consider the example introduced at the beginning of this section.

```
String name = "John Appleseed";
int age = 20;
String product = "Java coffee";
double initialPrice = 4.99;
double finalPrice = initialPrice * 1.06;
System.out.println("Product: " + name + ", Age: " + age + ", Product purchased: "
    + product + ", Final price: $" + finalPrice + ".");
```

If we modify this using `String.format()`, we would get the following code:

```
String name = "John Appleseed";
int age = 20;
String product = "Java coffee";
double initialPrice = 4.99;
double finalPrice = initialPrice * 1.06;
System.out.println(
    String.format("Product: %s, Age: %s, Product purchased: %s, Final price: $%s.",
        name, age, product, finalPrice));
```

However, we still get the same output:

```
Product: John Appleseed, Age: 20, Product purchased: Java coffee, Final
    price: $5.2894000000000005.
```

To fix this, we must replace the last `%s` with `%f`. This will reduce the number of decimal places to six.

```
String name = "John Appleseed";
int age = 20;
String product = "Java coffee";
double initialPrice = 4.99;
double finalPrice = initialPrice * 1.06;
System.out.println(
    String.format("Product: %s, Age: %s, Product purchased: %s, Final price: $%f.",
        name, age, product, finalPrice));
```

```
Product: John Appleseed, Age: 20, Product purchased: Java coffee, Final
    price: $5.289400.
```

As we stated earlier, money amounts are usually written with two digits after the decimal place. To format this, we can include a `.2` in between `%` and `f`. This is the `precision` argument; it indicates that we want two digits after the decimal place. If we have more digits, Java will round the number. If there are less, Java will add trailing 0’s.

```
String name = "John Appleseed";
int age = 20;
String product = "Java coffee";
double initialPrice = 4.99;
double finalPrice = initialPrice * 1.06;
System.out.println(
    String.format(
        "Product: %s, Age: %s, Product purchased: %s, Final price: $%.2f.",
        name, age, product, finalPrice));
```

```
Product: John Appleseed, Age: 20, Product purchased: Java coffee, Final
    price: $5.29.
```

### [7.6.4 Print formatting](#part0007.xhtml_uid400)

`System.out.print(String.format(params))` and `System.out.println(String.format(params))` are actually redundant. We can instead use `System.out.printf()` if we are only printing a formatted string:

```
String name = "John Appleseed";

// Printing without a newline at the end
System.out.print(String.format("I'm %s and I'm %d years old.", name, 20)); // NO
System.out.printf("I'm %s and I'm %d years old.", name, 20); // YES

// Printing with a newline at the end
System.out.println(String.format("I'm %s and I'm %d years old.", name, 20)); // NO
System.out.printf("I'm %s and I'm %d years old.\n", name, 20); // YES
// Notice that ^this has a '\n' character at the end to simulate println.
```

In this manner, you can use the same parameters in the same order.

## [7.7 Other useful string methods](#part0007.xhtml_aid-6LMVE)

In addition to `charAt()`, `length()`, and `substring()`, string objects have other useful string methods. We will explore some of them below.

### [7.7.1 `indexOf()`](#part0007.xhtml_aid-6LMVN)

The `indexOf()` string method accomplishes something that is very similar to what we coded out in one of the examples in [Section 7.4](#part0007.xhtml_aid-6LKVA), which is to return the index of the first occurrence of a character or a substring in a string.

There are four versions of `indexOf()`:

```
str.indexOf(char)
str.indexOf(char, fromIndex)
str.indexOf(substring)
str.indexOf(substring, fromIndex)
```

*   `str` is the `String` object that the `indexOf()` method is applied to
*   **Line 1**: `indexOf()` takes `char`, a character (in `int` form), as a parameter, and returns an `int` value representing the index of the first occurrence of `char` in `str`, or -1 if `char` isn’t in `str`.
*   **Line 2**: `indexOf()` takes `char`, a character (in `int` form), and `fromIndex`, an `int` value, as parameters, and returns an `int` value representing the index of the first occurrence of `char` in `str` after index `fromIndex` (inclusive), or -1 if `char` isn’t in `str` after `fromIndex`.
*   **Line 3**: `indexOf()` takes `substring`, a `String` object, as a parameter, and returns an `int` value representing the index of the first character of the first occurrence of `substring` in `str`, or -1 if `substring` isn’t a substring of `str`.
*   **Line 4**: `indexOf()` takes `substring`, a `String` object, and `fromIndex`, an `int` value, as parameters, and returns an `int` value representing the index of the first character of the first occurrence of `substring` in `str` after index `fromIndex` (inclusive), or -1 if `substring` isn’t a substring of `str` after `fromIndex`.

**Example 1**

Suppose we want to search the string `"Hello world"` for the first occurrence of the letter `o`. We can write the following:

```
System.out.println("Hello world".indexOf('o'));
```

We would then receive the following output:

```
4
```

**Example 2**

Suppose we want to write a function, `nfind()`, which returns the index of the n^(th) occurrence of a string, or -1 if the n^(th) doesn’t exist. We can write the following method header.

Listing 7.32: Method header for `nfind()`.

```
public static int nfind(String str, char ch, int n) {

}
```

In this instance, `str` is the string we are searching, `ch` is the character we are searching for and `n` tells us that we want the n^(th) occurrence of `ch`.

Next, we will add a variable, `lo_bound`, that represents the index at which `indexOf` should start searching for `ch`. After adding this, we will use a `for` loop to iterate `n` times, where in every iteration, if `indexOf()` starting at the index of the previously found `ch` doesn’t yield -1, we will continue searching. Because we want to start searching from the beginning, but we always use `indexOf()` with one more than the index of the previously found `ch`, we will let `lo_bound` equal -1.

Listing 7.33: Adding the `lobound` variable.

```
public static int nfind(String str, char ch, int n) {
    int lo_bound = -1;
}
```

We can now add our `for` loop.

Listing 7.34: Adding a `for` loop.

```
public static int nfind(String str, char ch, int n) {
    int lo_bound = -1;
    for (int i = 0; i < n; i++) {

    }
}
```

Inside the `for` loop, we assign `lo_bound` to the result of calling `indexOf()` on `str` with `ch` as the character and `lo_bound+1` as the starting point for search (not `lo_bound` because if we write this, then `lo_bound` may never change if there is a valid `ch` at index `lo_bound` due to the fact that `indexOf` will start searching from this parameter, inclusive). Then, we check whether `lo_bound` equals -1. If so, then there doesn’t exist an n^(th) occurrence of `ch`, and we return -1.

Listing 7.35: Updating `lobound` and making sure it doesn’t equal -1.

```
public static int nfind(String str, char ch, int n) {
    int lo_bound = -1;
    for (int i = 0; i < n; i++) {
        lo_bound = str.indexOf(ch, lo_bound+1);
        if (lo_bound == -1) {
            return -1;
        }
    }
}
```

Finally, if we finish looping without returning, then we have successfully found the n^(th) occurrence of `ch` in `str`, so we can return `lo_bound` outside the loop.

Listing 7.36: Updating `lobound` and making sure it doesn’t equal -1.

```
public static int nfind(String str, char ch, int n) {
    int lo_bound = -1;
    for (int i = 0; i < n; i++) {
        lo_bound = str.indexOf(ch, lo_bound+1);
        if (lo_bound == -1) {
            return -1;
        }
    }
    return lo_bound;
}
```

We can now test this function by calling it in `main()`.

Listing 7.37: Testing `nfind()` in `main()`.

```
public static void main(String[] args) {
    String phrase = "mississippi";
    for (int n = 1; n <= 5; n++) {
        System.out.println(nfind(phrase, 'i', n));
    }
}
```

Because there are only four occurrences of `'i'` in `phrase`, only the first four method calls should yield positive integers. The fifth will yield a -1.

Listing 7.38: Output for [Listing 7.37](#part0007.xhtml_code-test_nfind).

```
1
4
7
10
-1
```

### [7.7.2 `compareTo()`](#part0007.xhtml_aid-6LNFH)

The `compareTo()` string method compares two strings lexicographically. In other words, it compares corresponding characters in two strings in how they are ordered according to the Unicode table.

`compareTo()` is written in the following manner:

```
str1.compareTo(str2);
```

*   `str1` and `str2` are both `String` objects.
*   If `str1` comes before `str2` lexicographically, then a negative `int` value is returned.
*   If `str1` is the same as `str2` value-wise, then 0 is returned.
*   If `str1` comes after `str2` lexicographically, then a positive `int` value is returned.

The following explains how `compareTo()` is implemented:

*   An iterating variable `i` will loop through through indices from 0 to the end of the shorter string.
*   In each iteration, the i^(th) characters in `str1` and `str2` will be compared. If the character in `str1` comes before that in the same position in `str2`, then the function ends with a negative return value. If the character in `str1` comes after that in the same position in `str2`, then the function ends with a positive return value. If the two characters are the same, the function continues looping.
*   If the function finishes looping through the indices in the range of the smaller string and doesn’t return, then if `str1` is the shorter string and str2‘ is the longer string, a negative value will be returned, and if vice versa, a positive value will be returned.
*   If the two strings are identical, then 0 will be returned.

**Example 1**

Suppose we had the following code:

```
String str1 = "aabb";
String str2 = "bbcc";
String str3 = "aabb";
String str4 = "aaaaa";
System.out.println(str1.compareTo(str2));
System.out.println(str1.compareTo(str3));
System.out.println(str2.compareTo(str1));
System.out.println(str1.compareTo(str4));
```

We would get the following output:

```
-1
0
1
1
```

*   **Line 5**: At index 0, `'a'` in `str1` comes before `'b'` in `str2` in the Unicode table, so `compareTo()` returns a negative integer.
*   **Line 6**: `str1` and `str3` are identical, so `compareTo()` returns 0.
*   **Line 7**: At index 0, `'b'` in `str2` comes after `'a'` in `str1` in the Unicode table, so `compareTo()` returns a positive integer.
*   **Line 8**: At index 2, `'b'` in `str1` comes after `'a'` in `str4` in the Unicode table, so `compareTo()` returns a positive integer.

Keep in mind that `compareTo()` won’t always return -1, 0, or 1; in fact, it will return the difference in the decimal values of the corresponding characters (according to the Unicode table) that first differ in the two strings.

### [7.7.3 `toLowerCase()` and `toUpperCase()`](#part0007.xhtml_uid427)

The two string methods `toLowerCase()` and `toUpperCase()` work exactly like they sound: they return lowercase and uppercase versions of a string, respectively.

```
System.out.println("Hello world!".toLowerCase());
System.out.println("Hello world!".toUpperCase());
System.out.println("Hello world!".equals("hELLo WorLD!"));
System.out.println(
    "Hello world!".toLowerCase().equals("hELLo WorLD!".toLowerCase()));
```

On lines 1 and 2, we convert `"Hello world!"` to lowercase and uppercase, respectively. Lines 3 and 4 demonstrate a great use of these string methods; they remove case-sensitivity in string comparisons. On line 3, both strings say “Hello world!”, albeit with certain characters lowercased and others uppercased. The `equals()` method compares two strings in a case-sensitive manner, so the equality outcome is `false`. However, on line 4, both strings are converted to lowercase and then compared using `equals()`. By removing case sensitivity, the method returns `true` for equality.

```
hello world!
HELLO WORLD!
false
true
```

## [7.8 Review](#part0007.xhtml_cid47)

This chapter delved into the intricacies of strings and introduced means of analyzing strings for certain content.

# [Chapter 8 Objects and Classes](#part0008.xhtml_cha-ObjectsClasses)

By now, you’ve probably seen many instances of code where statements like `new` are used, terms like `methods` and `functions` are thrown around, and keywords like `static` are used in the functions we write. But what is the significance of all of this?

Java, in essence, is an object-oriented programming language. This term is thrown around a lot, but many beginner programmers often fail to understand its true implications. An **object-oriented programming** language is a language that is based around data containers called **objects** for representing information. They are like objects in the real world; for instance, a car is an object, a book is also an object, but cars and books are very different things and have different purposes. Additionally, even though two cars are both car objects, they may have different characteristics for their shared properties (e.g. car color, engine type, seating capacity).

If we want to create objects in Java that are similar, then we would create our objects using a **class**, which is essentially a blueprint with attributes and behaviors.

We’ve already seen a similar relationship between classes and objects in that between the primitive types that we’ve used (including `int`, `char`, `double`, and `boolean`) and the values that fall under those types. Just as types are to their possible values (e.g. `int` is to `5` or `8`), classes are to their objects. The key difference between classes and primitive types, then, is that classes are built using primitive types. Think of it as a human cell; inside the cell, there are many features such as the nucleus, mitochondria, and organelles.

In this chapter, we will explore the basics of classes and objects, including how they work and how to make them.

## [8.1 Classes](#part0008.xhtml_cid49)

**Classes**, as we stated earlier, are **blueprints** for objects that define its characteristics and capabilities. Objects are created using classes. Objects of the same class may have different *exact* features, but still maintain the same *kind* of features. These features are divided into two categories: **attributes** and **behaviors**.

Class attributes are variables inside a class that define the characteristics of any object made from the class, or the things that distinguish it from other classes. For instance, if we created a `Person` class, we could add `name`, `age`, and `height` attributes/variables to describe the corresponding data for any object created using this class.

Class behaviors are methods (another name for functions) inside a class that define what an object made from the class can do. For instance, if we created a `Car` class, we could add `honk()`, `useGas()`, and `playRadio()` as different method implementations, as these are some capabilities of a car. Note that `static` methods are not behaviors of a class; therefore, when we want to add a behavior to a class, we do not include this keyword in the corresponding method header.

Attributes and behaviors are different in a few ways. Firstly, attributes are class variables (not those in a function, but outside functions and inside classes; we will see these in a moment) while behaviors are methods. Secondly, attributes can store different values (as we already know with variables), while behaviors generally stay the same (because any two objects from the same class, though they might have different characteristics, are capable of the same things).

## [8.2 Creating a class](#part0008.xhtml_cid50)

In this chapter, we will emphasize the core concepts of classes and objects in a single file, `Car.java`, which is holds the `Car` class, a class that represents `Car` objects. Keep in mind that classes typically live in their own files, with the filenames matching the class names.

Create this file and add the class header for `Car`. Use the `public` keyword as a prefix.

Listing 8.1: Creating a new file, `Car.java`, and adding the class header.

```
1public class Car {
2}
```

We can add the `main()` method to this class.

Listing 8.2: Creating a new file, `Car.java`, and adding the class header.

```
1public class Car {
2    // Runner
3    public static void main(String[] args) {
4    }
5}
```

Note that because `main()` is `static` (and is required to be), it is not a behavior of the `Car` class.

## [8.3 Creating objects](#part0008.xhtml_aid-7K4K4)

Now that we’ve created the `Car` class (albeit an empty one), we can create, or **instantiate**, new objects from this class. The general structure for instantiating objects is the following:

```
ClassName objectVariable = new ClassName();
```

*   `ClassName` is the name of the class (e.g. `Car`).
*   `objectVariable` is the variable name with the type `ClassName`.
*   `new` is the keyword we use to **instantiate** a new object from a class.
*   For the `ClassName` after the `=` sign, we add `()` as if we are calling a method with no parameters; as we’ll see later, we can add functionality to a class that will allow us to provide parameters when we first instantiate a new object.
*   The portion before the `=` sign is where we declare a new `ClassName` variable, and the portion after the `=` sign is where we instantiate the new `ClassName` object instance and assign it to `objectVariable`.

We’ve seen this notation being used with `String`, such as in [Listing 7.1](#part0007.xhtml_code-string_instantiate), when we demonstrated how to create new `String` variables.

```
String one = "";
String two = new String(); // Uses instantiation
String three = "Hello";
String four = new String("Hello"); // Uses instantiation
```

Let’s try instantiating new object instances of `Car` in our `main()` method.

Listing 8.3: Creating a new file, `Car.java`, and adding the class header.

```
 1public class Car {
 2    // Runner
 3    public static void main(String[] args) {
 4        Car myCar = new Car();
 5        Car yourCar = new Car();
 6        Car thatCar = myCar;
 7        System.out.println(myCar + " " + yourCar + " " + thatCar);
 8        System.out.println(myCar == yourCar);
 9        System.out.println(myCar == thatCar);
10    }
11}
```

In line 4, we instantiate a new `Car` object and assign it to the variable `myCar`. In line 5, we instantiate another `Car` object and assign it to the variable `yourCar`. In line 6, rather than instantiating a new `Car` object, we assign the existing `Car` object stored in `myCar` to the new variable `thatCar`.

To analyze the next few lines, let’s first execute the code.

Listing 8.4: Output for [Listing 8.3](#part0008.xhtml_code-mycar_yourcar_thatcar).

```
Car@3fb6a447 Car@79b4d0f Car@3fb6a447
false
true
```

In the first line of output, we printed `myCar`, `yourCar` and `thatCar`, separated by spaces. When we print an object, the memory location of that object is printed (unless we add a special method to our class.) Because `myCar` and `yourCar` are different `Car` objects, they are stored at different memory locations, so different locations are printed (`3fb6a447` vs. `79b4d0f`). However, on line 6 of [Listing 8.3](#part0008.xhtml_code-mycar_yourcar_thatcar), we assigned `thatCar` directly to `myCar`, instead of assigning it to a new object instance of `Car`. Thus, `myCar` and `thatCar` refer to the same object, and have the same memory location (`3fb6a447` vs. `3fb6a447`).

In the second line of output, we printed whether `myCar` was equal to `yourCar`. When we use the `==` operator on objects, their memory locations are compared to determine if the two objects not only have the same values, but are the same object. `myCar` and `yourCar` were instantiated as their own objects, so the `==` operator would yield `false`. However, in the third line of output, we printed whether `myCar` and `thatCar` were equal using the `==` operator, and when we declared `thatCar`, we initialized it directly to `myCar`, meaning that `myCar` and `thatCar` refer to the same `Car` object. This explains why `myCar == thatCar` is `true`.

## [8.4 Attributes](#part0008.xhtml_aid-7K4RN)

In a class, an **attribute** is a variable that is declared (and sometimes initialized) in the body of a class but outside any method. Attributes describe the characteristics of an object; for instance, a hypothetical `Phone` object might have `RAM`, `Storage`, `OperatingSystem`, and `Version` as possible attributes (we can have others as well). These describe the “appearance” or the “makeup” of the object. As with any variable, we need to provide types for each of these attributes.

Let’s evaluate this by adding some attributes to `Car.java`. We will the following: `color`, `numberSeats`, `mpg`, `gasAmount`, and `carType`, which represent the color of a `Car` object, the number of seats in the `Car`, the miles per gallon of the gas for the `Car`, the amount of gas currently in the `Car`, and the kind of car (e.g. sedan, SUV, minivan). Pay attention to the types we declare for each of these.

Listing 8.5: Adding attributes to the `Car` class.

```
public class Car {
    // Attributes
    String color;
    int numberSeats;
    double mpg;
    double gasAmount = 10;
    String carType;

    // Runner
    public static void main(String[] args) {/* ... */}
}
```

Let’s note a few things: `color`, `numberSeats`, `mpg`, and `carType` are all declared but not initialized. On the other hand, `gasAmount` is both declared and initialized. This means that when we create a new `Car` object, the uninitialized variables will need to be given values.

In general, we can access an attribute of an object by first instantiating the object, and then using **dot notation** to access the attribute.

```
// Accessing attributes
object.this_attribute
object.that_attribute
```

When we access the attribute, it’s essentially such that we’re treating it like a variable. Thus, we can assign values to attributes or use attributes in expressions just as we do with variables. Let’s see how we would apply this below.

Listing 8.6: Instantiating `Car` objects.

```
public class Car {
    // Attributes
    String color;
    int numberSeats;
    double mpg;
    double gasAmount = 10;
    String carType;

    // Runner
    public static void main(String[] args) {
        // Instantiating car1
        Car car1 = new Car();

        // Modifying car1's attributes
        car1.color = "blue";
        car1.numberSeats = 4;
        car1.mpg = 52;
        car1.carType = "sedan";

        // Printing car1 attributes
        System.out.println(car1.color);
        System.out.println(car1.numberSeats);
        System.out.println(car1.mpg);
        System.out.println(car1.gasAmount);
        System.out.println(car1.carType);
    }
}
```

We first modified the attributes for our new `car1` object. Notice that we didn’t modify the attribute for `gasAmount`. We could have, but we didn’t need to, since if we later wanted to access its value, we wouldn’t run into any error (as it was initialized in the class itself).

Next, we printed all the attributes of `car1`. Again, we used dot notation to access these attributes.

Thus, Java would output the following:

Listing 8.7: Output for [Listing 8.6](#part0008.xhtml_code-car_inst_1)

```
blue
4
52.0
10.0
sedan
```

## [8.5 Constructors and the `this` keyword](#part0008.xhtml_aid-7K53G)

Before we move to behaviors, we should consider a special kind of behavior/method. A **constructor** is a method that is called right when the object is instantiated. It resembles the following:

```
// Example of a constructor with parameters
public ClassName(params) {
    // Do stuff here
}

// Example of a constructor without parameters
public ClassName() {
    // Do stuff here
}
```

Note that a constructor header looks almost exactly like a method header, except that we are not including a type (e.g. `int`, `boolean`). Additionally, we are not allowed to write `static` (there are no such things as static constructors), Otherwise, anything you learned about methods applies here. This means that the following hold:

*   We can add parameters to constructors, or we can simply have no constructor parameters.
*   We can perform **constructor overloading**, where we can have multiple constructors as long as the method signatures are different; see [Section 4.5](#part0004.xhtml_aid-3Q4GH) for more details.

Constructors are used when you need to execute some code immediately after an object is created, as a kind of “preparation” stage for the object to be used. One important usage of a constructor is to assign values to attributes that have been declared but not initialized.

There is something important to note: in a constructor (or any behavior, as we will explore in the next section), if we want to access attributes, we should to use a combination of dot notation and the **`this`** keyword (notice that we said “should,” not “must”; this will be explained).

```
// Example
public ClassName(params) {
    this.someAttribute = something;
    this.someOtherAttribute = somethingElse;
    System.out.println(this.aThirdAttribute);
}
```

`this` refers to the object itself, so we can use it to access attributes or methods. **It is not required unless we have a local variable (a variable inside a behavior or constructor) that shares the same name as an attribute but is meant to be a different variable)**.

Let’s add a constructor to our class.

Listing 8.8: Adding a constructor to `Car`.

```
public class Car {
    // Attributes
    String color;
    int numberSeats;
    double mpg;
    double gasAmount = 10;
    String carType;

    // Constructor
    public Car(String color, int numSeats, double mpg, String carType) {
        this.color = color;
        numberSeats = numSeats;
        this.mpg = mpg;
        this.carType = carType;
    }

    // Runner
    public static void main(String[] args) {/* ... */}
}
```

Here, we named our parameters as such, and then assigned our attributes to these values. We note a few things:

*   We did not assign the attribute `gasAmount` to anything. We didn’t need to because `gasAmount` was already assigned to 10. However, we could have if we wanted to.
*   The attributes `color`, `mpg`, and `carType` were assigned to their counterparts given by the parameters from the `Car` constructor header. **It cannot be emphasized enough that this.`color` is different from `color`!** Because both have the same name, when we refer to `color`, Java automatically looks for a local variable, for which we have created one as a parameter. So, if we were to write `color = color` instead of `this.color = color`, we wouldn’t be doing anything.
*   When we assigned `numberSeats = numSeats`, we didn’t need to write `this.numberSeats`. This is because the `Car` constructor doesn’t have a local `numberSeats` variable as a parameter, so Java automatically refers to the class attribute `numberSeats`.

To instantiate a new object with a constructor, we write the following:

```
ClassName object = new ClassName(params_for_constructor);
```

Let’s create a new `Car` object using this method.

Listing 8.9: Instantiating a new ‘Car‘ object using a custom constructor.

```
public class Car {
    // Attributes
    String color;
    int numberSeats;
    double mpg;
    double gasAmount = 10;
    String carType;

    // Constructor
    public Car(String color, int numSeats, double mpg, String carType) {
        this.color = color;
        numberSeats = numSeats;
        this.mpg = mpg;
        this.carType = carType;
    }

    // Runner
    public static void main(String[] args) {
        // Instantiating car1
        Car car1 = new Car("blue", 4, 52, "sedan");
        // Printing car1's attributes
        System.out.println(car1.color);
        System.out.println(car1.numberSeats);
        System.out.println(car1.mpg);
        System.out.println(car1.gasAmount);
        System.out.println(car1.carType);
        // Changing car1's color
        car1.color = "red";
        System.out.println("Changed car1's color to " + car1.color);
    }
}
```

Listing 8.10: Output for [Listing 8.9](#part0008.xhtml_aid-7K5AC)

```
blue
4
52.0
10.0
sedan
Changed car1's color to red
```

Simply for practice, we can add another constructor. Note that the order of types has to be different in this new constructor header. In other words, we cannot have the following order: `String`, `int`, `double`, `String`.

Listing 8.11: Adding another constructor to `Car`.

```
public class Car {
    // Attributes
    String color;
    int numberSeats;
    double mpg;
    double gasAmount = 10;
    String carType;

    // Constructor 1
    public Car(String color, int numSeats, double mpg, String carType) {
        this.color = color;
        numberSeats = numSeats;
        this.mpg = mpg;
        this.carType = carType;
    }

    // Constructor 2 - Automatically assign 4 seats to car
    public Car(String color, double mpg, String carType) {
        this.color = color;
        this.mpg = mpg;
        this.carType = carType;
        numberSeats = 4;
    }

    // Runner
    public static void main(String[] args) {/* ... */}
}
```

Our new constructor consists of the parameters `color`, `mpg`, `carType`. This means that in the body of the constructor, we are assigning `numberSeats` to a value which we know; in this case, we assign it to 4, meaning that using this constructor assumes that our car has four seats.

We can then use either constructor.

Listing 8.12: Testing new constructor.

```
public class Car {
    // Attributes
    String color;
    int numberSeats;
    double mpg;
    double gasAmount = 10;
    String carType;

    // Constructor 1
    public Car(String color, int numSeats, double mpg, String carType) {
        this.color = color;
        numberSeats = numSeats;
        this.mpg = mpg;
        this.carType = carType;
    }

    // Constructor 2 - Automatically assign 4 seats to car
    public Car(String color, double mpg, String carType) {
        this.color = color;
        this.mpg = mpg;
        this.carType = carType;
        numberSeats = 4;
    }

    // Runner
    public static void main(String[] args) {
        // Instantiating two different Car objects.
        Car car1 = new Car("silver", 6, 36, "minivan");
        Car car2 = new Car("maroon", 52, "sedan");
        // Printing attributes
        System.out.println(car1.color + ", " + car2.color);
        System.out.println(car1.numberSeats + ", " + car2.numberSeats);
        System.out.println(car1.mpg + ", " + car2.mpg);
        System.out.println(car1.gasAmount + ", " + car2.gasAmount);
        System.out.println(car1.carType + ", " + car2.carType);
    }
}
```

Listing 8.13: Output for [Listing 8.12](#part0008.xhtml_aid-7K5KC)

```
silver, maroon
6, 4
36.0, 52.0
10.0, 10.0
minivan, sedan
```

## [8.6 Behaviors](#part0008.xhtml_aid-7K5RV)

We said earlier that a constructor was a special kind of behavior. But what is a behavior?

We define a **behavior** to be an object method. (We will use “behavior” and “object method” interchangeably.) Behaviors define what an object is capable of doing. For instance, we might add behaviors to `Car` that allow it to use up gas by traveling, toggle the indicator, honk, and more.

Behaviors are different from the methods we’ve seen so far in that they do not write `static` in the method header. `static` methods are **class methods**, and these are methods directly associated with a class, not an object.

The following shows how we would refer to an object method (behavior) vs. a class method:

```
// Object method - behavior() is the method
ClassName object = new ClassName(); // Instantiate object first
object.behavior() // Call method using dot notation on object

// Class method - behavior() is the (static) method
behavior() // Use if you're calling from the same class (direct call)
ClassName.behavior() // Use if you're calling from a different class 
```

For now, we will focus on object methods. Note that object methods can only be accessed through dot notation on an *object*. It is often common for beginner Java programmers to access behaviors of objects directly from static methods without using dot notation on the corresponding objects. **You cannot call object methods from static methods directly. You must use dot notation on objects to call object methods.**

However, you *can* call an object method from another object method or constructor. This is because when you’re in an object method, you’re already within the object itself, so delving further into the object’s properties by calling another object method within the current object method is completely fine.

Let’s add a few behaviors to the `Car` class.

**The `drive()` method**

We begin by implementing a `drive()` behavior with a `double` parameter `miles`. In this method, we want to mimic a `Car` object driving and using up gas.

Listing 8.14: Adding behaviors to `Car`.

```
public class Car {
    // Attributes
    String color;
    int numberSeats;
    double mpg;
    double gasAmount = 10;
    String carType;

    // Constructor 1
    public Car(String color, int numSeats, double mpg,
               String carType) {/* ... */}

    // Constructor 2
    public Car(String color, double mpg, String carType) {/* ... */}

    // drive()
    public void drive(double miles) {
        // Code will follow
    }
}
```

To drive a certain number of miles, we need to have an appropriate amount of gas. We are given `miles` as input, and we can calculate the gallons of gas that would be used by dividing this by the `mpg` attribute.

Listing 8.15: Converting `miles` to gallons.

```
public void drive(double miles) {
    // Convert miles to gas using mpg
    double gasNeeded = miles / this.mpg;
}
```

Next, we include a conditional statement to determine whether we can actually travel the given number of miles.

Listing 8.16: Adding a conditional statement.

```
public void drive(double miles) {
    // Convert miles to gas using mpg
    double gasNeeded = miles / this.mpg;
    // Check if we have enough gas
    if (gasNeeded <= this.gasAmount) { // Enough gas

    } else { // Not enough gas

    }
}
```

If we have enough gas, we can travel the distance and deduct the gas used. Then we inform the user that we did so. To avoid giving the user a long stream of trailing digits to the user in the event that we have a repeating decimal or floating point error, we will truncate our printed gas quantities to four decimal places.

Listing 8.17: Using up gas.

```
public void drive(double miles) {
    // Convert miles to gas using mpg
    double gasNeeded = miles / this.mpg;
    // Check if we have enough gas
    if (gasNeeded <= this.gasAmount) { // Enough gas
        this.gasAmount -= gasNeeded;
        System.out.printf(
            "Traveled %.4f miles. Used: %.4f gal. Remaining: %.4f gal.%n",
            miles, gasNeeded, this.gasAmount);
    } else { // Not enough gas

    }
}
```

Otherwise, we can let the user know that they don’t have enough gas.

Listing 8.18: Telling the user that there’s not enough gas.

```
public void drive(double miles) {
    // Convert miles to gas using mpg
    double gasNeeded = miles / this.mpg;
    // Check if we have enough gas
    if (gasNeeded <= this.gasAmount) { // Enough gas
        this.gasAmount -= gasNeeded;
        System.out.printf(
            "Traveled %.4f miles. Used: %.4f gal. Remaining: %.4f gal.%n",
            miles, gasNeeded, this.gasAmount);
    } else { // Not enough gas
        System.out.println("Not enough gas");
    }
}
```

Our final code should resemble the following.

Listing 8.19: Current `Car` class.

```
public class Car {
    // Attributes
    String color;
    int numberSeats;
    double mpg;
    double gasAmount = 10;
    String carType;

    // useGas()
    public void drive(double miles) {
        double gasNeeded = miles / this.mpg;

        if (gasNeeded <= this.gasAmount) {
            this.gasAmount -= gasNeeded;
            System.out.printf(
                "Traveled %.4f miles. Used: %.4f gal. Remaining: %.4f gal.%n",
                miles, gasNeeded, this.gasAmount);
        } else {
            System.out.println("Not enough gas");
        }
    }

    // Constructor 1
    public Car(String color, int numSeats, double mpg, String carType) {
        this.color = color;
        numberSeats = numSeats;
        this.mpg = mpg;
        this.carType = carType;
    }

    // Constructor 2 - Automatically assign 4 seats to car
    public Car(String color, double mpg, String carType) {
        this.color = color;
        this.mpg = mpg;
        this.carType = carType;
        numberSeats = 4;
    }

    // Runner
    public static void main(String[] args) {/* ... */}
}
```

Let’s test our code. Add the following to the `main()` method.

Listing 8.20: Adding test code to the `main()` method.

```
public static void main(String[] args) {
    // Instantiate myCar as a new Car object
    Car myCar = new Car("Graphite", 48, "CRV");

    // Print current amount of gas
    System.out.printf("%s gal remaining\n", myCar.gasAmount);

    // Drive
    myCar.drive(150); // Drive 150 miles
    myCar.drive(240); // Drive 240 miles
    myCar.drive(160); // Drive 160 miles (shouldn't have enough gas to drive)

    // Print current amount of gas
    System.out.printf("%s gal remaining\n", myCar.gasAmount);
}
```

When we execute this code, we should get the following:

Listing 8.21: Output for [Listing 8.20](#part0008.xhtml_code-car_drive_test).

```
10.0 gal remaining
Traveled 150.0000 miles. Used: 3.1250 gal. Remaining: 6.8750 gal.
Traveled 240.0000 miles. Used: 5.0000 gal. Remaining: 1.8750 gal.
Not enough gas.
1.875 gal remaining
```

**The `toggleIndicator()` method**

We will implement `toggleIndicator()`, a method that toggles the turning indicator on or off. Firstly, we add a boolean attribute, `indicatorOn`, to represent whether the indicator is on or off. We will set this to `false` to indicate that the indicator is not on.

Listing 8.22: Adding the `indicatorOn` attribute.

```
public class Car {
    // Attributes
    String color;
    int numberSeats;
    double mpg;
    double gasAmount = 10;
    String carType;
    boolean indicatorOn = false;

    // ...
}
```

We can now begin writing the `toggleIndicator()` method.

Listing 8.23: Writing the method header for `toggleIndicator()`.

```
public class Car {
    // ...

    // toggleIndicator()
    public void toggleIndicator() {

    }
}
```

Next, we change `indicatorOn` to its opposite value: if it is `true`, we make it `false`, and vice versa. We do this by setting `indicatorOn` to `!indicatorOn`.

Listing 8.24: Changing the status of `indicatorOn`.

```
public void toggleIndicator() {
    this.indicatorOn = !this.indicatorOn;
}
```

Finally, if the new value of `indicatorOn` is `true`, we let the user know that we turned the indicator on. Otherwise, we let the user know that we turned it off.

Listing 8.25: Telling user that the indicator was turned on or off.

```
public void toggleIndicator() {
    this.indicatorOn = !this.indicatorOn;
    if (indicatorOn) {
        System.out.println("Indicator was turned ON.");
    } else {
        System.out.println("Indicator was turned OFF.");
    }
}
```

The final `Car` class resembles the following:

Listing 8.26: Current `Car` class.

```
public class Car {
    // Attributes
    String color;
    int numberSeats;
    double mpg;
    double gasAmount = 10;
    String carType;
    boolean indicatorOn = false;

    // useGas()
    public void drive(double miles) {
        double gasNeeded = miles / mpg;
        if (gasNeeded <= this.gasAmount) {
            this.gasAmount -= gasNeeded;
            System.out.printf(
                "Traveled %.4f miles. Used: %.4f gal. Remaining: %.4f gal.%n",
                miles, gasNeeded, this.gasAmount);
        } else {
            System.out.println("Not enough gas.");
        }
    }

    // toggleIndicator()
    public void toggleIndicator() {
        this.indicatorOn = !this.indicatorOn;
        if (indicatorOn) {
            System.out.println("Indicator was turned ON.");
        } else {
            System.out.println("Indicator was turned OFF.");
        }
    }

    // Constructor 1
    public Car(String color, int numSeats, double mpg, String carType) {
        this.color = color;
        numberSeats = numSeats;
        this.mpg = mpg;
        this.carType = carType;
    }

    // Constructor 2 - Automatically assign 4 seats to car
    public Car(String color, double mpg, String carType) {
        this.color = color;
        this.mpg = mpg;
        this.carType = carType;
        numberSeats = 4;
    }

    // Runner
    public static void main(String[] args) {/* ... */}
}
```

Let’s test the `toggleIndicator()` method.

Listing 8.27: Testing the `toggleIndicator()` method.

```
public static void main(String[] args) {
    // Instantiate myCar as a new Car object
    Car myCar = new Car("Graphite", 48, "CRV");

    // Toggle indicator a few times
    for (int i = 0; i < 4; i++) {
        myCar.toggleIndicator();
    }
}
```

We get the following output.

Listing 8.28: Output for [Listing 8.27](#part0008.xhtml_code-test_toggleIndicator).

```
Indicator was turned ON.
Indicator was turned OFF.
Indicator was turned ON.
Indicator was turned OFF.
```

## [8.7 Review](#part0008.xhtml_cid55)

In this section, we ran through the basics of objects and class design. We learned how to create our own objects using classes as templates, how to access attributes, and how to call behaviors. The next chapter will deviate from object-orientation to briefly discuss arrays and arraylists.

# [Chapter 9 Arrays and ArrayLists](#part0009.xhtml_cid56)

Until now, almost any data we’ve been working with has been single-item data, or **scalar quantities**. With strings, we ventured into realm of collections, as in [Chapter 7](#part0007.xhtml_cha-chapter_strings), where we explored how strings are represented as collections of characters. In this chapter, we will dive extensively into **vector quantities**, in the form of **Arrays** and **ArrayLists**.

You may have learned about vectors in your math and physics classes, and how they represent a magnitude with a direction; this is the geometric definition of vectors. Linear algebra has a more abstract definition of vectors as it explains vectors to be objects that follow a set of laws, or “axioms.” This carries over in computer science to a certain extent, but for the purposes of our goals, we define a vector to be an ordered list of similar elements. These are incredibly important in data structures and algorithms, where we might process multivariate data to produce specific outputs.

## [9.1 Wrapper classes](#part0009.xhtml_aid-8IL2J)

Before we explore Arrays and Arraylists, we must quickly deviate to **wrapper classes**. We know that we have eight primitive types: `int`, `byte`, `short`, `long`, `char`, `float`, `double`, and `boolean`. However, we cannot use these when parametrizing classes. For instance, when we later learn how to make ArrayLists, we will find that we cannot create ArrayLists of an `int` or `float` type; instead, we need to use the appropriate **wrapper classes** (in this case they would be `Integer` or `Float`).

Wrapper classes thus allow us to use primitive data types as objects. The following are the wrapper classes for each primitive type.

| Primitive type | Wrapper class |
| `int` | `Integer` |
| `byte` | `Byte` |
| `short` | `Short` |
| `long` | `Long` |
| `char` | `Char` |
| `float` | `Float` |
| `double` | `Double` |
| `boolean` | `Boolean` |

Each is perfectly interchangeable with its counterpart. For instance, we can do the following in either of the following ways:

Listing 9.1: Primitive types and wrapper classes.

```
public static void main(String[] args) {
    // Using primitive types
    int a = 3;
    double b = 4.5;
    System.out.printf("%s, %s, %s\n", a, b, a+b);

    // Using wrapper classes
    Integer c = 3;
    Double d = 4.5;
    System.out.printf("%s, %s, %s\n", c, d, c+d);
}
```

Listing 9.2: Output for [Listing 9.1](#part0009.xhtml_code-primitive_types_wrapper_classes).

```
3, 4, 7.5
3, 4, 7.5
```

For each wrapper class, we can access the primitive value it holds using the following:

| Wrapper class | Access primitive value |
| `Integer` | `.intValue()` |
| `Byte` | `.byteValue()` |
| `Short` | `.shortValue()` |
| `Long` | `.longValue()` |
| `Char` | `.charValue()` |
| `Float` | `.floatValue()` |
| `Double` | `.doubleValue()` |
| `Boolean` | `.booleanValue()` |

For example, we can do the following:

Listing 9.3: Accessing primitive values using the correct wrapper behaviors.

```
public static void main(String[] args) {
    Integer a = 102;
    Character b = 'b';
    System.out.println(a.intValue());
    System.out.println(b.charValue());
}
```

Listing 9.4: Output for [Listing 9.3](#part0009.xhtml_code-access_primitive).

```
102
b
```

## [9.2 Arrays](#part0009.xhtml_aid-8IL81)

**Arrays** are ordered lists/containers of a fixed size that can store like data. For instance, we could have an array of five `int` values, or an array of nine `String` objects. They are indexed just like strings.

### [9.2.1 Creating arrays](#part0009.xhtml_uid470)

To **declare** an array, we write the type of each element, followed by brackets, followed by the variable name.

```
Type[] variableName;
```

Suppose we wanted to create an `int` array, `numbers`. We can then write the following:

Listing 9.5: Declaring an `int[]` array, `numbers`.

```
public static void main(String[] args) {
    // Declaring numbers
    int[] numbers;
}
```

When **initializing** an array, we usually assign our variable to an empty container with a fixed size. So, when we initialize our array, each index is empty (i.e. has a null value). We fill these positions in subsequent code.

For instance, we can initialize `numbers` to an array with ten slots. Note that once we initialize an array variable, its size cannot be changed unless we initialize a completely new array (just like we initialize a completely new object).

To initialize an array variable, we write the following:

```
variableName = new Type[int_size];
```

The type used in the initialization must be the same type (or a subclass of) the type given in the declaration.

Listing 9.6: Initializing `numbers` to an array of a particular size.

```
public static void main(String[] args) {
    // Declaring numbers
    int[] numbers;
    // Initializing numbers to an array with 10 slots
    numbers = new int[10];
}
```

We don’t necessarily have to declare and initialize on two separate lines.

Listing 9.7: Combining the declaration and initialization of `numbers` into a single line.

```
public static void main(String[] args) {
    // Declaring and initializing numbers to an array with 10 slots
    int[] numbers = new int[10];
}
```

All the syntax we have looked at currently creates arrays, but doesn’t populate them with anything. We can alternatively create arrays with actual values.

Listing 9.8: Creating arrays with values.

```
public static void main(String[] args) {
    // Creating an array with values
    int[] numbers = {9, 2, 1, 5, 3, 12, 49, 1, 2, 4};
}
```

### [9.2.2 Printing arrays](#part0009.xhtml_uid475)

When we try to print an array, we instead print a memory reference, just like when we attempt to print an object. Instead, we can write the following:

Listing 9.9: Printing arrays.

```
import java.util.*; // Add this line at the top of the code file

public class ArrayArraylists {
    public static void main(String[] args) {
        int[] numbers = new int[10];
        System.out.println(Arrays.toString(numbers));
    }
}
```

In the second line of the `main()` method, `Arrays.toString()` allows us to convert an array to a string format. This lets us view clearly what is inside an array.

Listing 9.10: Output for [Listing 9.9](#part0009.xhtml_code-print_array).

```
[0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
```

Let’s observe our output. We can see that every element is a 0 when we first initialize `numbers`. This is because when we create an array of a primitive type, like an `int` array, every value is populated with a **falsy** value. This means that every integer array type slot (`int[]`, `short[]`, `long[]`, `byte[]`) will be populated with a 0, every decimal array type slot (`double[]`, `float[]`) will be populated with a 0.0, and every slot of a `char[]` array and a `boolean[]` array will be populated with a `'``'` (empty character) and `false`, respectively.

If we initialize an array of an object type, like `Integer[]` or `String[]`, we will discover that every element is `null`. This just means that there are no values in the cells.

### [9.2.3 Get, set, length, and looping](#part0009.xhtml_aid-8ILGS)

Now that we know how arrays work, we need to be able to populate them. For instance, our `numbers` array is currently empty, so we need to add `int` values to it. To do this, we can use **indexing**. Recall in [Chapter 7](#part0007.xhtml_cha-chapter_strings) that strings are **zero-indexed**, meaning that indices start from 0 and lead up to the length of the string. This is the same for arrays.

To access an **element** in an array at a particular **index**, we use **bracket notation**.

```
// Getting an element at an index
array[number]
// Assigning a slot at an index to an element
array[number] = value;
```

Suppose we have the following:

Listing 9.11: `numbers` array.

```
import java.util.*;

public class ArrayArraylists {
    public static void main(String[] args) {
        int[] numbers = new int[10];
        System.out.println(Arrays.toString(numbers));
    }
}
```

Let’s say we want to populate the second, third, and seventh indices with the elements `9, 1, 44`. Then we can write the following:

Listing 9.12: Set array location values.

```
import java.util.*;

public class ArrayArraylists {
    public static void main(String[] args) {
        int[] numbers = new int[10];
        numbers[2] = 9;
        numbers[3] = 1;
        numbers[7] = 44;
        System.out.println(Arrays.toString(numbers));
    }
}
```

Listing 9.13: Output for [Listing 9.12](#part0009.xhtml_code-set_array).

```
[0, 0, 9, 1, 0, 0, 0, 44, 0, 0]
```

Suppose we wanted to print a specific element at an index in `numbers`. Then we write the following:

Listing 9.14: Set array location values.

```
import java.util.*;

public class ArrayArraylists {
    public static void main(String[] args) {
        int[] numbers = new int[10];
        numbers[2] = 9;
        numbers[3] = 1;
        numbers[7] = 44;
        System.out.println(Arrays.toString(numbers));
        System.out.println(numbers[6]);
        System.out.println(numbers[3]);
        System.out.println(numbers[2] + numbers[7]);
    }
}
```

Listing 9.15: Output for [Listing 9.14](#part0009.xhtml_code-get_array).

```
[0, 0, 9, 1, 0, 0, 0, 44, 0, 0]
0
1
53
```

To get the number of elements an array can hold, we can use the `.length` function.

Listing 9.16: Set array location values.

```
import java.util.*;

public class ArrayArraylists {
    public static void main(String[] args) {
        int[] numbers = new int[10];
        numbers[2] = 9;
        numbers[3] = 1;
        numbers[7] = 44;
        System.out.println(Arrays.toString(numbers));
        System.out.println(numbers[6]);
        System.out.println(numbers[3]);
        System.out.println(numbers[2] + numbers[7]);
        System.out.println(numbers.length);
    }
}
```

Listing 9.17: Output for [Listing 9.16](#part0009.xhtml_code-length_array).

```
[0, 0, 9, 1, 0, 0, 0, 44, 0, 0]
0
1
53
10
```

**Example 1**

Suppose we wanted to create an `int[]` array, `twenties`, containing the first twenty positive integers in sorted order. Admittedly, we can write `twenties[0] = 1`, `twenties[1] = 2`, and so on and so forth (twenty times, to be exact), but we can also populate an array using a `for` loop.

Listing 9.18: Array with the first twenty integers.

```
public static void main(String[] args) {
    int[] twenties = new int[20];
    for (int i = 0; i < 20; i++) {
        twenties[i] = i+1;
    }
    System.out.println(Arrays.toString(twenties));
}
```

Here, we iterate through the indices 0…19 (inclusive). In each iteration, we can use the `i` iterating variable as our index, and assign `twenties[i]` to `i+1`. We assign it to `i+1` because we want the first twenty positive integers, and 0 is not positive, so we offset by 1. Finally, we use `Arrays.toString()` to print the array. Make sure you included `import java.util.*` at the top of the code file.

Listing 9.19: Output for [Listing 9.18](#part0009.xhtml_code-twenty_array).

```
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20]
```

As we can see, loops are an effective way of populating an array.

**Example 2**

In this exercise, we will find the sum of all the elements in an `Integer[]` array. Suppose we have the following array:

Listing 9.20: Creating array `arr`.

```
public static void main(String[] args) {
    Integer[] arr = {19238, 60498, 1289, 34578, 3209};
}
```

To sum all the elements, we need a variable on the outside, which we can call `sum`, that will store the updated sum as we iterate through every element in `arr` and add it to `sum`. To iterate through an array’s indices, we iterate from 0 to the length of the array.

Listing 9.21: Summing the elements of `arr`.

```
public static void main(String[] args) {
    Integer[] arr = {19238, 60498, 1289, 34578, 3209};
    Integer sum = 0;
    for (int i = 0; i < arr.length; i++) {
        sum += arr[i];
    }
    System.out.println(sum);
}
```

Listing 9.22: Output for [Listing 9.21](#part0009.xhtml_code-sum_array).

```
118812
```

**Example 3**

We will write a method, `splitDigits()`, that takes a positive `int` as input and returns an `int[]` array containing all the digits of the integer. We will assume that the `int` parameter is always positive. Also, we will make `splitDigits()` a static method and not a behavior of the class we are writing because we want to call the method without having to instantiate an object of the class and using dot notation to call the method.

Listing 9.23: Method header for `splitDigits()`.

```
public static int[] splitDigits(int num) {

}
```

We will use an array, `digits`, to store the digits of `num`, but we need to know the length of `digits`. This would be equal to the number of digits in `num`. We cannot directly find the length of `num` in `int` form, since there is no such length function for the `int` type. However, we can convert `num` to a String by adding it to an empty string, and find the length of that string.

Listing 9.24: Creating `digits` with a specific length.

```
public static int[] splitDigits(int num) {
    int[] digits = new int[(""+num).length()];
}
```

Next, we write a `for` loop to iterate through the indices of `digits`. This time, however, we will iterate backward. This will make sense in a moment.

Listing 9.25: Adding a `for` loop to `splitDigits()`.

```
public static int[] splitDigits(int num) {
    int[] digits = new int[(""+num).length()];
    for (int d = digits.length-1; d >= 0; d--) {

    }
}
```

We must now extract digits from `num` one-by-one. The easiest way to do this is to use the modulo operator (`%`) to find the remainder when `num` is divided by 10. This extracts the last digit of `num`, which is why we iterate backward through `digits` (to keep the final `digits` array in the proper order). Then, we can remove the last digit of `num` by dividing `num` by 10.

Listing 9.26: Extracting digits from `num`.

```
public static int[] splitDigits(int num) {
    int[] digits = new int[(""+num).length()];
    for (int d = digits.length-1; d >= 0; d--) {
        digits[d] = num % 10;
        num /= 10;
    }
}
```

Finally, we return `digits`.

Listing 9.27: Returning `digits`.

```
public static int[] splitDigits(int num) {
    int[] digits = new int[(""+num).length()];
    for (int d = digits.length-1; d >= 0; d--) {
        digits[d] = num % 10;
        num /= 10;
    }
    return digits;
}
```

We can now test this code in the `main()` method.

Listing 9.28: Testing `splitDigits()`.

```
public static void main(String[] args) {
    System.out.println(Arrays.toString(splitDigits(12431)));
    System.out.println(Arrays.toString(splitDigits(98345312)));
    System.out.println(Arrays.toString(splitDigits(5789)));
    System.out.println(Arrays.toString(splitDigits(2)));
}
```

Listing 9.29: Output for [Listing 9.28](#part0009.xhtml_code-splitDigits_arrays).

```
[1, 2, 4, 3, 1]
[9, 8, 3, 4, 5, 3, 1, 2]
[5, 7, 8, 9]
[2]
```

**Example 4**

We will write a method, `find()`, that will determine whether an `int` value is in a given `int[]` array.

Listing 9.30: Method header for `find()`.

```
public static boolean find(int[] arr, int val) {

}
```

We can iterate through every index in `arr`. If the element at a particular index equals `val`, we return `true`, since we found the value we were looking for.

Listing 9.31: Looping through the indices of `arr`.

```
public static boolean find(int[] arr, int val) {
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] == val) {
            return true;
        }
    }
}
```

After looping through the entire array, if we haven’t found `val`, we will return `false`.

Listing 9.32: Returning `false` if we don’t find `val` in `arr`.

```
public static boolean find(int[] arr, int val) {
    for (int i = 0; i < arr.length; i++) {
        if (arr[i] == val) {
            return true;
        }
    }
    return false;
}
```

We can test this code in `main()`.

Listing 9.33: Testing `find()`.

```
public static void main(String[] args) {
    int[] numbers = {8, 1, 3, 2};
    System.out.println(find(numbers, 3));
    System.out.println(find(numbers, 8));
    System.out.println(find(numbers, 4));
}
```

Listing 9.34: Output for [Listing 9.33](#part0009.xhtml_code-testing_find).

```
true
true
false
```

As we have demonstrated from all these examples, the synergy between arrays and loops can allow us to perform complex tasks with multiple data items, such as searching for data or manipulating elements.

### [9.2.4 For-each loop](#part0009.xhtml_aid-8IMP5)

In all the examples we’ve seen earlier, we’ve been using `for` loops to iterate through possible indices of an array. We can also use `while` and `do while` loops to iterate through possible indices of an array.

However, we do not necessarily need to iterate through the *indices*; rather, if we want to iterate through every *element* in the exact order they are given, we can use a **for-each** loop. This is an enhanced `for` loop that lets us avoid having to iterate through indices through which we can refer to elements through bracket notation.

We write a for-each loop in the following manner:

```
for (type var: collection) {
    // Code using var here
}
```

*   `for` is the keyword indicating that we are using a `for` loop.
*   `type` is the type of every element in `collection`.
*   `var` is the variable we use to refer to an element of `collection` in some arbitrary iteration.
*   `collection` is any kind of collection object, like an array (or an ArrayList, as we will see later).

**Example 1**

Suppose we have the following array (assume that `import java.util.*` is at the top of the code file):

Listing 9.35: `decimals` array.

```
public static void main(String[] args) {
    double[] decimals = {5.5, 2.91, 33.4, 68.7, 10.2};
}
```

We can use a for-each loop to iterate through this array and print all the elements one-by-one.

Listing 9.36: Printing every element of `decimals` using a for-each loop.

```
public static void main(String[] args) {
    double[] decimals = {5.5, 2.91, 33.4, 68.7, 10.2};
    for (double dec: decimals) {
        System.out.println(dec);
    }
}
```

Listing 9.37: Output for [Listing 9.36](#part0009.xhtml_code-%20print_decimal_foreach).

```
5.5
2.91
33.4
68.7
10.2
```

**Example 2**

Consider the same starting code from the previous example:

Listing 9.38: `decimals` array.

```
public static void main(String[] args) {
    double[] decimals = {5.5, 2.91, 33.4, 68.7, 10.2};
}
```

This time, rather than printing each element, we want to find the product of all elements. We first create a `double` variable, `product`, that will represent the product of all decimals. `product` will initially be assigned to 1. Then, we use a for-each loop to iterate through every element of `decimals`. In each iteration, we multiply the current element onto `product`. Finally, we print `product`.

Listing 9.39: `decimals` array.

```
public static void main(String[] args) {
    double[] decimals = {5.5, 2.91, 33.4, 68.7, 10.2};
    double product = 1;
    for (double dec: decimals) {
        product *= dec;
    }
    System.out.println(product);
}
```

Listing 9.40: Output for [Listing 9.39](#part0009.xhtml_code-prod_dec).

```
374592.47958
```

**Example 3**

Again, we begin with the same starter code from the previous example.

Listing 9.41: `decimals` array.

```
public static void main(String[] args) {
    double[] decimals = {5.5, 2.91, 33.4, 68.7, 10.2};
}
```

Now, however, we want to find the product of every *other* element, starting from the first one. This is where we encounter the limitations of a for-each loop: we can only use this kind of loop when we want to iterate through *every* element of a collection *from the first to the last element*. In this case, however, we want to skip every odd-indexed element. This is not attainable with a for-each loop, so we instead use a regular `for` loop to accomplish this.

Listing 9.42: Using a regular `for` loop to print the product of every other element.

```
public static void main(String[] args) {
    double[] decimals = {5.5, 2.91, 33.4, 68.7, 10.2};
    double product = 1;
    for (int i = 0; i < decimals.length; i += 2) {
        product *= decimals[i];
    }
    System.out.println(product);
}
```

Listing 9.43: Output for [Listing 9.42](#part0009.xhtml_code-arr_every_other).

```
1873.7399999999998
```

### [9.2.5 2D Arrays](#part0009.xhtml_aid-8IN5R)

We know that we use the following notation to declare a new array of a particular type:

```
type[] variableName;
```

Here, `type` can be anything, like `int` or `String`. However, it can also be an array itself, like `int[]`. It follows that we would end up with a declaration like so:

```
type[][] variableName;
```

When we start adding more brackets like this, we enter the realm of **multidimensional arrays**. In this book, we will only focus on one kind of multidimensional array: **two-dimensional arrays** (also called 2D arrays or matrices). A two-dimensional array is an array of arrays, rather than an array of a scalar type (like an `int`, `double`, or `String`, to name a few). These are especially useful when we are working with grid-like data.

When instantiating a new 2D array, we need to include two brackets (just like we do when declaring variable as a 2D array), in which we include two `int` values representing the number of rows and columns, respectively.

```
variableName = new type[row_int][col_int];
```

As usual, we can declare and instantiate on the same line.

Suppose we create a six by four 2D array, `grid`, to hold the numbers from 1 to 24 on each row. The table below describes what our 2D array should look like, where the first column list out the row indices and the first row list out the column indices.

| R![epub/OEBPS/images/texmath/a6df5ce2ff8f4e6c8a5e06a5a7f267fed9576fc8](Images/image00453.jpeg) C![epub/OEBPS/images/texmath/a3a5f4233222a6f5204e88d0095190580b529863](Images/image00454.jpeg) | 0 | 1 | 2 | 3 |
| 0 | 1 | 2 | 3 | 4 |
| 1 | 5 | 6 | 7 | 8 |
| 2 | 9 | 10 | 11 | 12 |
| 3 | 13 | 14 | 15 | 16 |
| 4 | 17 | 18 | 19 | 20 |
| 5 | 21 | 22 | 23 | 24 |

To “get” or “set an element’s value, we need two indices, rather than one. The first index represents the row, and the second represents the column. The following chart indicates how we would be able to “get” and “set” each element’s value.

| R![epub/OEBPS/images/texmath/a6df5ce2ff8f4e6c8a5e06a5a7f267fed9576fc8](Images/image00453.jpeg) C![epub/OEBPS/images/texmath/a3a5f4233222a6f5204e88d0095190580b529863](Images/image00454.jpeg) | 0 | 1 | 2 | 3 |
| 0 | grid[0][0] | grid[0][1] | grid[0][2] | grid[0][3] |
| 1 | grid[1][0] | grid[1][1] | grid[1][2] | grid[1][3] |
| 2 | grid[2][0] | grid[2][1] | grid[2][2] | grid[2][3] |
| 3 | grid[3][0] | grid[3][1] | grid[3][2] | grid[3][3] |
| 4 | grid[4][0] | grid[4][1] | grid[4][2] | grid[4][3] |
| 5 | grid[5][0] | grid[5][1] | grid[5][2] | grid[5][3] |

Let’s try to create this array. We begin by declaring and initializing a new 2D array on a single line.

Listing 9.44: Declaring and instantiating `grid`.

```
public static void main(String[] args) {
    int[][] grid = new int[6][4]; // 6 rows, 4 columns
}
```

Next, we must populate the elements of `grid`. We can create a variable, `counter`, that keeps track of the current number to populate in the next index we visit. Then, we can create a nested loop to iterate through each row and each column per row. For the outer and inner loop, it is customary to use the variable names `i` and `j` to refer to the row and column, respectively. Additionally, the outer loop will iterate to `grid.length`, while the inner loop will iterate to `grid[i].length`; this is because `grid.length` references the number of rows, while `grid[i].length` references the number of columns. (`i` can actually be any number between 0 and 6, but we’re just using `i` in this case because we’ve already created the variable, so why not maximize its use case?)

Listing 9.45: Creating `counter` and adding nested loops.

```
public static void main(String[] args) {
    int[][] grid = new int[6][4]; // 6 rows, 4 columns

    int counter = 1;
    for (int i = 0; i < grid.length; i++) {
        for (int j = 0; j < grid[i].length; j++) {

        }
    }
}
```

Inside the nested loop, we can set the `grid` index at `i, j` to `counter`. Then, we can increment `counter`.

Listing 9.46: Assigning `grid[i][j]` inside the nested loop and incrementing `counter`.

```
public static void main(String[] args) {
    int[][] grid = new int[6][4]; // 6 rows, 4 columns

    int counter = 1;
    for (int i = 0; i < grid.length; i++) {
        for (int j = 0; j < grid[i].length; j++) {
            grid[i][j] = counter;
            counter++;
        }
    }
}
```

Finally, we can print the 2D array. Remember that each element in `grid` is an array, so we cannot simply use `Arrays.toString()` on the entire array; instead, we can iterate through each row and print the array associated with that row using `Arrays.toString()`.

Listing 9.47: Printing the contents of `grid`.

```
public static void main(String[] args) {
    int[][] grid = new int[6][4]; // 6 rows, 4 columns

    int counter = 1;
    for (int i = 0; i < grid.length; i++) {
        for (int j = 0; j < grid[i].length; j++) {
            grid[i][j] = counter;
            counter++;
        }
    }

    for (int i = 0; i < grid.length; i++) {
        System.out.println(Arrays.toString(grid[i]));
    }
}
```

Listing 9.48: Output for [Listing 9.47](#part0009.xhtml_code-test_grid_2d).

```
[1, 2, 3, 4]
[5, 6, 7, 8]
[9, 10, 11, 12]
[13, 14, 15, 16]
[17, 18, 19, 20]
[21, 22, 23, 24]
```

## [9.3 ArrayLists](#part0009.xhtml_aid-8INJ6)

An **ArrayList** is an array-based collection whose only difference to an array is the fact that **its size can be changed**. This extends the functions of our array to the following:

*   We can **add** values to the end of an ArrayList.
*   We can **remove** values from an ArrayList.
*   We can **insert** values in between other elements of an ArrayList.

We will explore all of these new functionalities, as well as the familiar ones, such as getting and setting values of existing elements, finding lengths, and iterating through ArrayLists.

### [9.3.1 Creating an ArrayList](#part0009.xhtml_uid526)

We use the following syntax to create an ArrayList:

```
// 1\. Creating an ArrayList with an object type for every element
ArrayList<ObjectType> listName = new ArrayList<ObjectType>();

// 2\. Creating an ArrayList without specifying an object
//    type in the instantiation
ArrayList<ObjectType> listName = new ArrayList<>();

// 3\. Creating an ArrayList without specifying an object
//    type in the declaration or the instantiation
ArrayList listName = new ArrayList();
```

Let’s analyze each of these methods of declaring and instantiating a new ArrayList.

1.  We create an ArrayList with the type `ObjectType`. Note two things: First, we provide a *type parameter* between the angle brackets to indicate that every element of our ArrayList will be of a particular type. Second, the type that we indicate **cannot be a primitive type!** As such, if we want to create an ArrayList containing `int` objects, we must instead provide the `Integer` object type. This is extremely important to remember not only with ArrayLists, but with *any* object that asks for a type parameter (i.e. any object whose declaration and/or instantiation asks for an object type to be given in between angle brackets).
2.  We create an ArrayList with the type `ObjectType`, but instantiate an ArrayList with an empty type parameter. This is alright as long as the declarartion has the object type between its angle brackets.
3.  We create an ArrayList without providing any values for type parameters. This is a *somewhat dangerous* syntax to use for creating ArrayLists, although it is useful in the sense that you can add elements of distinct types to such an ArrayList. For instance, with this kind of ArrayList, we could add `String`, `Integer`, and `Double` elements. It is advised that you resort to either of the first two methods of creating and using ArrayLists because with this kind of ArrayList, you cannot perform operations between multiple elements unless you *type-cast* each element that you use. This is because with this kind of ArrayList, every element is actually of the `Object` type, and `Object` objects don’t have certain functionalities like addition and multiplication, like the `Integer` type.

For the scope of this book, we will only use the first or second way of creating an ArrayList. There are of course other ways to create ArrayLists, but those are “raw and unchecked” ways, to use Java’s vocabulary, of creating an ArrayList. It is wise to stay away from using these kinds of syntax to create ArrayList unless you are doing so because it is the only way your code will work.

### [9.3.2 Adding and inserting elements](#part0009.xhtml_aid-8INM7)

Unless you specify otherwise, every ArrayList is initially empty. Thus, we must *add* values to an ArrayList. The following demonstrates how we can add values to an ArrayList:

```
// Adding to the end
myArrayList.add(element);
// Inserting at an index
myArrayList.add(index, element);
```

When we add `element` to `myArrayList` using the first syntax, `element` is appended to the end of `myArrayList`. When we use the second syntax, `element` is inserted into `myArrayList` at the specified `index`. Any element currently at `index` will shift one index to the right.

**Example 1**

Suppose we want to create an ArrayList, `firstTen`, that contains the first ten positive integers:

Listing 9.49: Declaring and instantiating `firstTen` to an ArrayList.

```
public static void main(String[] args) {
    ArrayList<Integer> firstTen = new ArrayList<Integer>();
}
```

We use a `for` loop to iterate between the values 1 and 10, inclusive. In each iteration, we use the `add` method with a single argument to append the current number to the end of `firstTen`. Finally, we print `firstTen`.

Listing 9.50: Adding elements to `firstTen`.

```
public static void main(String[] args) {
    ArrayList<Integer> firstTen = new ArrayList<Integer>();
    for (int i = 1; i <= 10; i++) {
        firstTen.add(i);
    }
    System.out.println(firstTen);
}
```

Notice here that when we printed `firstTen`, we could print it like any other variable and still get coherent output.

Listing 9.51: Output for [Listing 9.50](#part0009.xhtml_code-firstTen).

```
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

**Example 2**

Consider the following ArrayList:

Listing 9.52: `nums` ArrayList.

```
public static void main(String[] args) {
    ArrayList<Integer> nums = new ArrayList<>();
    for (int i = 2; i < 10; i += 2) {
        nums.add(i);
    }
    System.out.println(nums);
}
```

Listing 9.53: Output for [Listing 9.52](#part0009.xhtml_code-starter_nums_arrlist).

```
[2, 4, 6, 8]
```

Suppose we want to insert 9 in between 4 and 6. We know that the `add()` method with two parameters will shift everything to the right of the index we insert at, so we identify that we want to insert 9 at index 2, where 6 currently resides.

Listing 9.54: Inserting 9 into `nums` at index 2.

```
public static void main(String[] args) {
    ArrayList<Integer> nums = new ArrayList<>();
    for (int i = 2; i < 10; i += 2) {
        nums.add(i);
    }
    System.out.println(nums);
    // Insert 9 at index 2
    nums.add(2, 9);
    System.out.println(nums);
}
```

Listing 9.55: Output for [Listing 9.54](#part0009.xhtml_code-insert_test).

```
[2, 4, 6, 8]
[2, 4, 9, 6, 8]
```

### [9.3.3 Removing elements](#part0009.xhtml_aid-8IO0C)

We can remove elements from indices in the following manner:

```
myArrayList.remove(index);
```

Note that this method will remove *and* return the element at this index.

Consider the previous example.

Listing 9.56: ArrayList containing even integers from 2 to 8.

```
public static void main(String[] args) {
    ArrayList<Integer> nums = new ArrayList<>();
    for (int i = 2; i < 10; i += 2) {
        nums.add(i);
    }
    System.out.println(nums);
}
```

Suppose we want to remove 4 from this ArrayList. 4 is at index 1, so we can call the `remove()` method using 1 as our parameter.

Listing 9.57: Removing 4 from `nums`.

```
public static void main(String[] args) {
    ArrayList<Integer> nums = new ArrayList<>();
    for (int i = 2; i < 10; i += 2) {
        nums.add(i);
    }
    System.out.println(nums);
    // Remove 4 from index 1
    int removedValue = nums.remove(1);
    System.out.println("Removed " + removedValue);
    System.out.println(nums);
}
```

Listing 9.58: Output for [Listing 9.57](#part0009.xhtml_code-removearrlist).

```
[2, 4, 6, 8]
Removed 4
[2, 6, 8]
```

## [9.4 Review](#part0009.xhtml_cid60)

In this chapter, we learned about collections in the form of Arrays and ArrayLists. These are extremely important when we want to manipulate multiple pieces of similar data, and you as a programmer will often find yourself dealing with multiple collections at once. Almost everything relies on vector- and matrix-formatted collections. Many data structures and algorithms, for instance, wouldn’t exist if it weren’t for these containers. There are indeed other kinds of collections in Java, including LinkedLists, Queues, Stacks, and Binary Trees. Feel free to explore these as you delve into the realm of computational theory.

# [Chapter 10 End Matter](#part0010.xhtml_cid61)

Congratulations! You have finished learning the fundamentals of Java programming! In this edition of the book, we learned the basic syntax of Java, from types and variables to objects and arrays. Updated editions of this book will be published where each chapter includes content stretching beyond what we’ve currently learned (e.g. OOP-related concepts such as encapsulation, polymorphism, abstraction, and inheritance, error handling, file management, and more) section examples and exercises, chapter review problems.

## [10.1 Where to go from here](#part0010.xhtml_cid62)

Now that we’ve finished learning the basics of Java, let’s see where we can go next with our knowledge. Firstly, we can learn about general application development. Java can be extended so that we can create Windows applets that rely primarily on Java for computing and manipulating data. Additionally, Java allows us to extend into mobile app development. Most Android apps are coded in Java and Kotlin, a similar programming language.

In addition to applying Java to various fields, you can also learn other languages. The syntax is generally not too different across languages, and concepts are typically similar. Let’s go through a few examples of printing “Hello world” in different languages.

**Java**

```
class Main {
    public static void main(String[] args) {
        System.out.println("Hello world")
    }
}
```

**C++**

```
#include <iostream>
int main() {
    std::cout << "Hello world!";
    return 0;
}
```

**Python**

```
print("Hello world")
```

**JavaScript**

```
console.log("Hello world")
```

**Swift**

```
print("Hello world")
```

As you can see, Python, JavaScript, and Swift, which are higher-level languages, typically have simpler syntax, while lower-level languages, like Java and C++, have a bit more complicated, though predictable, syntax. Whether you decide to stick with Python or learn other languages is up to you. I strongly encourage you to continue with computer science regardless because you get to solve problems that make life easier for you and others. Good luck with your coding path!

# [Chapter 11 Appendices](#part0011.xhtml_cid63)

## [11.1 Appendix 1: Unicode table](#part0011.xhtml_sec-appendix_unicode)

This table includes the first 128 characters on the unicode table.

| Position | Decimal | Name | Appearance |
|  |  |  |  |
| 0x0000 | 0 | <control>: NULL |  |
| 0x0001 | 1 | <control>: START OF HEADING |  |
| 0x0002 | 2 | control: START OF TEXT |  |
| 0x0003 | 3 | control: END OF TEXT |  |
| 0x0004 | 4 | control: END OF TRANSMISSION |  |
| 0x0005 | 5 | control: ENQUIRY |  |
| 0x0006 | 6 | control: ACKNOWLEDGE |  |
| 0x0007 | 7 | control: BELL |  |
| 0x0008 | 8 | control: BACKSPACE |  |
| 0x0009 | 9 | control: HORIZONTAL TABULATION |  |
| 0x000A | 10 | control: LINE FEED |  |
| 0x000B | 11 | control: VERTICAL TABULATION |  |
| 0x000C | 12 | control: FORM FEED |  |
| 0x000D | 13 | control: CARRIAGE RETURN |  |
| 0x000E | 14 | control: SHIFT OUT |  |
| 0x000F | 15 | control: SHIFT IN |  |
| 0x0010 | 16 | control: DATA LINK ESCAPE |  |
| 0x0011 | 17 | control: DEVICE CONTROL ONE |  |
| 0x0012 | 18 | control: DEVICE CONTROL TWO |  |
| 0x0013 | 19 | control: DEVICE CONTROL THREE |  |
| 0x0014 | 20 | control: DEVICE CONTROL FOUR |  |
| 0x0015 | 21 | control: NEGATIVE ACKNOWLEDGE |  |
| 0x0016 | 22 | control: SYNCHRONOUS IDLE |  |
| 0x0017 | 23 | control: END OF TRANSMISSION BLOCK |  |
| 0x0018 | 24 | control: CANCEL |  |
| 0x0019 | 25 | control: END OF MEDIUM |  |
| 0x001A | 26 | control: SUBSTITUTE |  |
| 0x001B | 27 | control: ESCAPE |  |
| 0x001C | 28 | control: FILE SEPARATOR |  |
| 0x001D | 29 | control: GROUP SEPARATOR |  |
| 0x001E | 30 | control: RECORD SEPARATOR |  |
| 0x001F | 31 | control: UNIT SEPARATOR |  |
| 0x0020 | 32 | SPACE |  |
| 0x0021 | 33 | EXCLAMATION MARK | ! |
| 0x0022 | 34 | QUOTATION MARK | ” |
| 0x0023 | 35 | NUMBER SIGN | # |
| 0x0024 | 36 | DOLLAR SIGN | $ |
| 0x0025 | 37 | PERCENT SIGN | % |
| 0x0026 | 38 | AMPERSAND | ![epub/OEBPS/images/texmath/a7a2b94468f7b028e085681036df8d96646c39db](Images/image00455.jpeg) |
| 0x0027 | 39 | APOSTROPHE | ’ |
| 0x0028 | 40 | LEFT PARENTHESIS | ( |
| 0x0029 | 41 | RIGHT PARENTHESIS | ) |
| 0x002A | 42 | ASTERISK | * |
| 0x002B | 43 | PLUS SIGN | + |
| 0x002C | 44 | COMMA | , |
| 0x002D | 45 | HYPHEN-MINUS | - |
| 0x002E | 46 | FULL STOP | . |
| 0x002F | 47 | SOLIDUS | / |
| 0x0030 | 48 | DIGIT ZERO | 0 |
| 0x0031 | 49 | DIGIT ONE | 1 |
| 0x0032 | 50 | DIGIT TWO | 2 |
| 0x0033 | 51 | DIGIT THREE | 3 |
| 0x0034 | 52 | DIGIT FOUR | 4 |
| 0x0035 | 53 | DIGIT FIVE | 5 |
| 0x0036 | 54 | DIGIT SIX | 6 |
| 0x0037 | 55 | DIGIT SEVEN | 7 |
| 0x0038 | 56 | DIGIT EIGHT | 8 |
| 0x0039 | 57 | DIGIT NINE | 9 |
| 0x003A | 58 | COLON | : |
| 0x003B | 59 | SEMICOLON | ; |
| 0x003C | 60 | LESS-THAN SIGN |  |
| 0x003D | 61 | EQUALS SIGN | = |
| 0x003E | 62 | GREATER-THAN SIGN |  |
| 0x003F | 63 | QUESTION MARK | ? |
| 0x0040 | 64 | COMMERCIAL AT | @ |
| 0x0041 | 65 | LATIN CAPITAL LETTER A | A |
| 0x0042 | 66 | LATIN CAPITAL LETTER B | B |
| 0x0043 | 67 | LATIN CAPITAL LETTER C | C |
| 0x0044 | 68 | LATIN CAPITAL LETTER D | D |
| 0x0045 | 69 | LATIN CAPITAL LETTER E | E |
| 0x0046 | 70 | LATIN CAPITAL LETTER F | F |
| 0x0047 | 71 | LATIN CAPITAL LETTER G | G |
| 0x0048 | 72 | LATIN CAPITAL LETTER H | H |
| 0x0049 | 73 | LATIN CAPITAL LETTER I | I |
| 0x004A | 74 | LATIN CAPITAL LETTER J | J |
| 0x004B | 75 | LATIN CAPITAL LETTER K | K |
| 0x004C | 76 | LATIN CAPITAL LETTER L | L |
| 0x004D | 77 | LATIN CAPITAL LETTER M | M |
| 0x004E | 78 | LATIN CAPITAL LETTER N | N |
| 0x004F | 79 | LATIN CAPITAL LETTER O | O |
| 0x0050 | 80 | LATIN CAPITAL LETTER P | P |
| 0x0051 | 81 | LATIN CAPITAL LETTER Q | Q |
| 0x0052 | 82 | LATIN CAPITAL LETTER R | R |
| 0x0053 | 83 | LATIN CAPITAL LETTER S | S |
| 0x0054 | 84 | LATIN CAPITAL LETTER T | T |
| 0x0055 | 85 | LATIN CAPITAL LETTER U | U |
| 0x0056 | 86 | LATIN CAPITAL LETTER V | V |
| 0x0057 | 87 | LATIN CAPITAL LETTER W | W |
| 0x0058 | 88 | LATIN CAPITAL LETTER X | X |
| 0x0059 | 89 | LATIN CAPITAL LETTER Y | Y |
| 0x005A | 90 | LATIN CAPITAL LETTER Z | Z |
| 0x005B | 91 | LEFT SQUARE BRACKET | [ |
| 0x005C | 92 | REVERSE SOLIDUS | \ |
| 0x005D | 93 | RIGHT SQUARE BRACKET | ] |
| 0x005E | 94 | CIRCUMFLEX ACCENT | ⌃ |
| 0x005F | 95 | LOW LINE | _ |
| 0x0060 | 96 | GRAVE ACCENT | ‘ |
| 0x0061 | 97 | LATIN SMALL LETTER A | a |
| 0x0062 | 98 | LATIN SMALL LETTER B | b |
| 0x0063 | 99 | LATIN SMALL LETTER C | c |
| 0x0064 | 100 | LATIN SMALL LETTER D | d |
| 0x0065 | 101 | LATIN SMALL LETTER E | e |
| 0x0066 | 102 | LATIN SMALL LETTER F | f |
| 0x0067 | 103 | LATIN SMALL LETTER G | g |
| 0x0068 | 104 | LATIN SMALL LETTER H | h |
| 0x0069 | 105 | LATIN SMALL LETTER I | i |
| 0x006A | 106 | LATIN SMALL LETTER J | j |
| 0x006B | 107 | LATIN SMALL LETTER K | k |
| 0x006C | 108 | LATIN SMALL LETTER L | l |
| 0x006D | 109 | LATIN SMALL LETTER M | m |
| 0x006E | 110 | LATIN SMALL LETTER N | n |
| 0x006F | 111 | LATIN SMALL LETTER O | o |
| 0x0070 | 112 | LATIN SMALL LETTER P | p |
| 0x0071 | 113 | LATIN SMALL LETTER Q | q |
| 0x0072 | 114 | LATIN SMALL LETTER R | r |
| 0x0073 | 115 | LATIN SMALL LETTER S | s |
| 0x0074 | 116 | LATIN SMALL LETTER T | t |
| 0x0075 | 117 | LATIN SMALL LETTER U | u |
| 0x0076 | 118 | LATIN SMALL LETTER V | v |
| 0x0077 | 119 | LATIN SMALL LETTER W | w |
| 0x0078 | 120 | LATIN SMALL LETTER X | x |
| 0x0079 | 121 | LATIN SMALL LETTER Y | y |
| 0x007A | 122 | LATIN SMALL LETTER Z | z |
| 0x007B | 123 | LEFT CURLY BRACKET | { |
| 0x007C | 124 | VERTICAL LINE | &#124; |
| 0x007D | 125 | RIGHT CURLY BRACKET | } |
| 0x007E | 126 | TILDE | ![epub/OEBPS/images/texmath/8fcd54109a0a4273103d91841c4a3129ba1a59f1](Images/image00456.jpeg) |
| 0x007F | 127 | control: DELETE |  |