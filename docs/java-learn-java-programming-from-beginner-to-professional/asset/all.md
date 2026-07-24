![](image_rsrc3MG.jpg)

1

Java: Learn Java Programming from Beginner to Professional

2

![](image_rsrc3MH.jpg)

3

© Copyright Philip Jeff 2024 All rights reserved.

The content contained within this book may not be reproduced, duplicated, or transmitted without direct written permission from the author or the publisher.

Under no circumstances will any blame or legal responsibility be held against the publisher, or author, for any damages, reparation, or monetary loss due to the information contained within this book. Either directly or indirectly. You are responsible for your own choices, actions, and results.

Legal Notice:

This book is copyright protected. This book is only for personal use. You cannot amend, distribute, sell, use, quote or paraphrase any part, or the content within this book, without the consent of the author or publisher.

Disclaimer Notice:

Please note the information contained within this document is for educational and entertainment purposes only. All effort has been executed to present accurate, up to date, and reliable, complete information. No warranties of any kind are declared or implied. Readers acknowledge that the author is not engaging in the rendering of legal, financial, medical, or professional advice. The content within this book has been derived from various sources. Please consult a licensed professional before attempting any techniques outlined in this book.

By reading this document, the reader agrees that under no circumstances is the author responsible for any losses, direct or indirect, which are incurred as a result of the use of the information contained within this document, including, but not limited to, — errors, omissions, or inaccuracies.

4

Table of Content

Contents

Introduction ............................................................................................................................................ 8

Chapter 1 ............................................................................................................................................... 10

Introduction to Java Programming ................................................................................................... 10

History of Java ............................................................................................................................... 10

Chapter 2: Java Basics ........................................................................................................................... 26

Java Syntax and Structure ................................................................................................................ 26

Practice: ........................................................................................................................................ 26

Java Program Structure ..................................................................................................................... 29

Data Types and Variables ............................................................................................................. 31

Operators and Expressions ........................................................................................................... 37

Object-Oriented Programming (OOP) ......................................................................................... 91

Classes and Objects .............................................................................................................................. 91

Core Principles of OOP ................................................................................................................. 93

Encapsulation in Java ........................................................................................................................ 93

Benefits of Encapsulation.............................................................................................................. 96

Key Concepts of Inheritance ............................................................................................................. 99

Abstraction in Java ..................................................................................................................... 118

Chapters 3 ........................................................................................................................................... 124

Methods and Constructors in Java ..................................................................................................... 124

Method Overriding ..................................................................................................................... 127

Chapter 4 ............................................................................................................................................. 131

Benefits of Constructor Overloading .............................................................................................. 138

Chapter 5 ............................................................................................................................................. 152

Encapsulation and Abstraction .......................................................................................................... 152

Encapsulation in Java ...................................................................................................................... 152

Chapter 6: Basic Data Structures ........................................................................................................ 161

Arrays: ................................................................................................................................................. 161

Strings: ............................................................................................................................................ 162

ArrayList and LinkedList ............................................................................................................ 163

5

Chapter 7: Exception Handling .......................................................................................................... 165

Introduction to Exceptions ............................................................................................................ 165

Types of Exceptions: ................................................................................................................... 165

Try, Catch, and Finally ............................................................................................................... 165

Chapter 8: File I/O and Serialization .................................................................................................. 168

Serialization and Deserialization .................................................................................................... 173

Chapter 9 ............................................................................................................................................ 178

Java Collections Framework: List, Set, and Map Interfaces ........................................................... 178

List Interface: ...................................................................................................................................... 180

Set Interface .................................................................................................................................... 184

Map Interface .............................................................................................................................. 189

Chapter 10 ........................................................................................................................................... 203

Understanding HashMap, TreeMap, HashSet, TreeSet ................................................................. 203

HashSet: ...................................................................................................................................... 223

Chapter 11 ............................................................................................................................................ 241

Iterators and Enhanced For-Loop in JavaIterators ......................................................................... 241

Chapter 12: Generics .......................................................................................................................... 252

Generics in Java ............................................................................................................................... 252

Benefits of Generics ........................................................................................................................ 255

Chapter 13 ........................................................................................................................................... 270

Multithreading and Concurrency in Java ....................................................................................... 270

Implementing the Runnable Interface ........................................................................................ 271

Synchronization: ................................................................................................................................. 285

Concurrency Utilities (ExecutorService, Future, Callable) ....................................................... 286

Chapter 14: Java Features.................................................................................................................... 288

Default and Static Methods in Interfaces ........................................................................................... 291

Part III: Advanced Java ........................................................................................................................ 293

Chapter 15: Java Networking .............................................................................................................. 294

Introduction to Networking in Java ............................................................................................... 294

Networking: ................................................................................................................................ 294

Chapter 16: Java Database Connectivity (JDBC) ................................................................................. 299

Prepared Statements and Transactions .......................................................................................... 301

Part III: Advanced Java ........................................................................................................................ 302

Chapter 17: Java GUI Programming .................................................................................................... 303

Introduction to AWT and Swing ............................................................................................... 303

Building GUI Applications with Swing ......................................................................................... 304

6

Event Handling ........................................................................................................................... 305

Chapter 18: JavaFX .............................................................................................................................. 307

Introduction to JavaFX ................................................................................................................... 307

JavaFX Properties and Bindings ................................................................................................. 308

Chapter 19: Web Applications with Java ........................................................................................... 311

Introduction to Java EE ...................................................................................................................... 311

JavaServer Pages (JSP) .................................................................................................................... 312

Building Web Applications with Spring Boot ............................................................................ 313

Chapter 20: Design Patterns ............................................................................................................... 314

Introduction to Design Patterns ......................................................................................................... 314

Chapter 21: Advanced Topics ............................................................................................................. 328

Reflection API ..................................................................................................................................... 328

Java Native Interface (JNI) ............................................................................................................. 329

Performance Tuning and Profiling .............................................................................................. 330

Modular Programming with Java 9..................................................................................................... 331

Chapter 22: Testing and Debugging ................................................................................................... 333

Unit Testing with JUnit ................................................................................................................. 333

Mocking with Mockito ............................................................................................................... 334

Chapter 23: Building and Deployment................................................................................................ 336

Continuous Integration and Deployment ....................................................................................... 338

Dockerizing Java Applications ................................................................................................... 339

Reference ............................................................................................................................................ 340

7

## Introduction

Welcome to the world of Java, a language that has shaped the landscape of modern software development. Whether you're taking your first steps into programming or you're an experienced developer looking to sharpen your skills, this book is your guide on the journey to mastering Java.

Java has been at the heart of the programming world for over two decades, powering everything from mobile apps to enterprise-level systems. Its versatility, combined with a strong community and extensive libraries, makes it a go-to language for developers of all levels. This book is designed to be your companion, helping you navigate through the foundational concepts and guiding you toward advanced topics with clarity and ease.

As you turn the pages, you’ll discover how Java's powerful features can be applied to real-world problems, giving you the tools to create robust, high-performance applications.

We’ll start with the basics—setting up your environment, understanding syntax, and writing your first lines of code. From there, we’ll delve into more complex topics like object-oriented programming, data structures, and multithreading, ensuring you gain a deep and comprehensive understanding of the language.

Each chapter is crafted to build on the last, with practical examples and exercises that reinforce your learning. By the end of this book, you’ll not only be comfortable writing Java code, but you'll also be able to think like a developer—problem-solving with efficiency and creativity.

Unlock the full potential of Java programming and set yourself on the path to becoming a high-earning developer with "Java: Learn Java Programming From Beginner to Professional." Whether you're just starting out or looking to elevate your skills, this comprehensive guide will empower you to master Java, one of the most in-demand programming languages in the world.

This book is more than just a learning tool—it's your blueprint for success in the competitive tech industry. With step-by-step instructions, real-world examples, and expert 8

insights, you'll develop the proficiency needed to tackle complex projects and create robust, scalable applications. From the basics of syntax and structure to advanced concepts like multithreading, networking, and JavaFX, each chapter builds your confidence and capabilities.

But this journey isn't just about learning to code; it's about transforming your skills into lucrative opportunities. As you progress through this book, you'll gain the knowledge and expertise required to land top-tier jobs, secure high-paying freelance gigs, or even start your own tech venture. The demand for skilled Java developers is soaring, and with the right tools and understanding, you could be on your way to earning six or even seven figures in the industry.

Java is more than just a programming language; it’s a gateway to innovation, and I’m thrilled to help you on this exciting journey. So, let’s get started. Your path from beginner to professional Java developer begins here!

With "Java: Learn Java Programming From Beginner to Professional," you're not just investing in a book—you're investing in your future. Ready to turn your passion for coding into a profitable career? Your journey starts here

9

## Chapter 1

## Introduction to Java Programming

### History of Java

The Java language project was started in June 1991 by James Gosling, Mike Sheridan, and Patrick Naughton, according to google. Although Java was initially intended for interactive television, the digital cable television industry at the time could not handle its advanced features. Originally named after an oak tree that stood outside Gosling's office, the language was known as Oak. Subsequently, the project was known as Green before being renamed Java after Java coffee, an Indonesian variety of coffee. Gosling created Java with a syntax reminiscent of C/C++ for system and application programmers.

Midway through the 1990s, Sun Microsystems began developing Java. Although it was too sophisticated for the digital cable television market at the time, it was initially intended for interactive television. Originally named after an oak tree that stood outside the developer James Gosling's office, the language was known as Oak. The development team drank a lot of Java coffee, which led to the name change to Java later on.

Java was originally developed by James Gosling at Sun Microsystems. It was released in May 1995 as a core component of Sun's Java platform. The original and reference implementation Java compilers, virtual machines, and class libraries were originally released by Sun under proprietary licenses. As of May 2007, in compliance with the specifications of the Java Community Process, Sun had relicensed most of its Java technologies under the GPL-2.0-only license. Oracle offers its own HotSpot Java Virtual Machine, however the official reference implementation is the OpenJDK JVM which is free open-source software and used by most developers and is the default JVM for almost all Linux distributions.

Java is a high-level programming language that is class-based, object-oriented, and designed to reduce implementation dependencies. This general-purpose programming language allows programmers to write code once and have it run anywhere. Compiled Java code can run on any platform that supports Java without the need for recompilation. Java 10

programs are typically compiled to bytecode.

Java gained popularity shortly after its release, and has been a very popular programming language since then. Java was the third most popular programming language in 2022 according to GitHub. Although still widely popular, there has been a gradual decline in use of Java in recent years with other languages using JVM gaining popularity.

Key Milestones:

• 1991: Project started by James Gosling, Mike Sheridan, and Patrick Naughton.

• 1995: Java 1.0 released by Sun Microsystems.

• 1996: First version of Java Development Kit (JDK) released.

• 1999: Java 2 (J2SE 1.2) released with significant improvements.

• 2004: Java 5 (J2SE 5.0) introduced new features like generics, annotations, enumerated types, and the enhanced for loop.

• 2009: Oracle Corporation acquired Sun Microsystems, including Java.

• 2014: Java 8 released with lambda expressions, the Stream API, and the new date-time API.

11

Features of Java

Key Features

1\. Simple: Java's syntax is easy to learn and use, with a clean and straightforward design because of following reasons:

• Java comprises the same syntax as C, and C++.

• It holds automatic garbage collection features.

• Java eliminated its unused features.

• It keeps bringing regular updates for better performance.

• Java has its own community to make learning and using Java easy.

2\. Object-Oriented: Java is based on the principles of objects and classes, which makes it modular, flexible, and scalable.

Almost everything written in Java is object and class, making it a true object-oriented programming (OOP) language. The basic concept of OOP is:

• Object: Object is a real-world entity in Java that encompasses state, functionality, and identity.

• Class: Class is a logical entity which includes a group of objects with common properties. It contains fields, methods, constructors, blocks, nested classes and interfaces.

• Inheritance: It’s a concept in Java through which developers can create new classes built upon existing classes to achieve runtime polymorphism.

• Polymorphism: A Mechanism in Java through which you can perform a single action in multiple ways. Polymorphism can be of two types- Compile time and runtime.

• Abstraction: It’s a method to hide internal processing and show only essential things to the users.

12

3\. Platform-Independent: Java programs can run on any device with the Java Virtual Machine (JVM). This feature is known as "write once, run anywhere."

Unlike other languages, Java is not limited to any specific machine and dependent on other factors to run. The Java platform is independent because:

• It uses a runtime environment of its own, i.e. JVM.

• It is a write-once, run-anywhere language.

• It is a software-based platform that runs on top of other hardware-based platforms.

• Its code can be executed on multiple platforms, including Windows, Linux, Sun Solaris, and Mac/OS.

The Java code is compiled by the compiler and converted into bytecode.

4\. Secure: Java provides a secure environment for developing applications by including features like bytecode verification and a security manager.

Java programming language is known for its security. With it, you can create virus-free systems because:

• Java programming language runs inside a virtual machine.

• It uses its own runtime environment- JVM.

• Java includes a security manager, which determines what resources a class can access, such as reading and writing to the local disk.

• In Java run time, a class loader separates the package for the classes of the local file system from the files imported from network sources.

Java also consists of Bytecode Verifier, which checks the code fragments for illegal code.

5\. Robust: Java has strong memory management, exception handling, and type-checking mechanisms to create reliable applications.

Automatic memory management is a crucial feature of Java programming. It helps in:

• Create high-performance system.

• Automatically allocate and free up space for objects.

• Eliminating the worries about memory management.

• Issues like object destruction don’t occur.

13

There is no need to add memory management logic.

6\. Multithreaded: Java supports concurrent execution of multiple threads, making it possible to perform many tasks simultaneously.

Multithreading is an essential feature of Java that makes Java programming exclusive. It offers several benefits:

• It lets Java developers execute multiple threads at the same time.

• It’s used to achieve multitasking.

• It saves time.

• It’s mostly used in games and animation.

Threads work independently and don’t impact other threads, even if created simultaneously.

7\. High Performance: Java achieves high performance through Just-In-Time (JIT) compilers and efficient garbage collection.

Java is a programming language with a high-performance rate. It is because:

• Java uses bytecode that can be easily translated into native machine code.

• It has multiple easy-to-use frameworks.

• It is compatible with multiple platforms, including Windows, Linux, Sun Solaris, and Mac/OS.

• It is a write-once, run-anywhere language.

Java also automatically clears the garbage to enhance its performance.

8\. Distributed: Java supports distributed computing, allowing developers to create applications that can run on different systems across a network.

Java offers its users scalability, which means it can deal with more and more users and works. It is so because:

• Java is an object-oriented programming language.

• It has the ability to handle large databases.

• Java doesn’t require multiple resources while running.

14

![](image_rsrc3MJ.jpg)

• It uses multithreading and multiprocessing.\

Java includes a higher volume of code.

9\. Dynamic: Java can dynamically load classes, even if they are not known at compile time, which makes it flexible and adaptable.

Example:

15

Setting up Java Environment: Step-by-Step Guide

Step 1: Download and Install JDK

1\. Visit the Official Oracle JDK Download Page: Go to the Oracle JDK download page.

2\. Select and Download the Appropriate JDK Version: Choose the appropriate JDK

version for your operating system (Windows, macOS, or Linux) and click the download link.

3\. Accept the License Agreement: Accept the license agreement and download the installer.

4\. Run the Installer: Locate the downloaded installer file and run it. Follow the on-screen instructions to complete the installation.

Step 2: Set Up JAVA_HOME Environment Variable

1\. Locate the JDK Installation Directory: After installation, locate the directory where JDK was installed. The default installation path is usually:

o Windows: C:\Program Files\Java\jdk-<version>

o macOS: /Library/Java/JavaVirtualMachines/jdk-<version>.jdk/Contents/Home o Linux: /usr/lib/jvm/jdk-<version>

2\. Set JAVA_HOME on Windows:

o Right-click on "My Computer" or "This PC" and select "Properties".

o Click on "Advanced system settings".

o Click on the "Environment Variables" button.

o Under "System variables", click "New" to add a new variable.

o Set the variable name to JAVA_HOME and the variable value to the JDK

installation path (e.g., C:\Program Files\Java\jdk-<version>).

o Click "OK" to save the changes.

3\. Set JAVA_HOME on macOS:

o Open a terminal window.

o Edit the ~/.bash_profile file (or ~/.zshrc if using zsh) using a text editor: 16

![](image_rsrc3MK.jpg)![](image_rsrc3MM.jpg)![](image_rsrc3MN.jpg)![](image_rsrc3MP.jpg)![](image_rsrc3MR.jpg)![](image_rsrc3MS.jpg)![](image_rsrc3MT.jpg)

Add the following line to the file

Save the file and reload the shell configuration

Set JAVA_HOME on Linux:

• Open a terminal window.

• Edit the ~/.bashrc or ~/.profile file using a text editor:

Set JAVA_HOME on Linux:

• Open a terminal window.

• Edit the ~/.bashrc or ~/.profile file using a text editor:

Add the following line to the file:

Save the file and reload the shell configuration:

17

![](image_rsrc3MU.jpg)![](image_rsrc3MV.jpg)![](image_rsrc3MW.jpg)

Step 3: Add JDK's bin Directory to System PATH

1\. Add to PATH on Windows:

o In the "Environment Variables" window (same as where you set JAVA_HOME), find the "Path" variable under "System variables" and select it.

o Click "Edit" and then "New".

o Add the path to the bin directory of the JDK installation (e.g., C:\Program Files\Java\jdk-<version>\bin).

o Click "OK" to save the changes.

2\. Add to PATH on macOS and Linux:

o Open a terminal window.

o Edit the ~/.bash_profile or ~/.bashrc (or ~/.zshrc for zsh) file Add the following line to the file:

Save the file and reload the shell configuration

18

![](image_rsrc3MX.jpg)![](image_rsrc3MY.jpg)![](image_rsrc3MZ.jpg)![](image_rsrc3N0.jpg)

Step 4: Verify the Installation

1\. Open a Command Prompt or Terminal: Open a new command prompt (Windows) or terminal window (macOS/Linux).

2\. Check Java Version: Run the following command to check the installed Java version:

You should see output similar to:

3\. Check Java Compiler Version: Run the following command to check the installed Java compiler version:

You should see output similar to:

19

![](image_rsrc3N1.jpg)![](image_rsrc3N2.jpg)![](image_rsrc3N3.jpg)![](image_rsrc3N4.jpg)

Step 5: Write and Run Your First Java Program

1\. Create a New Java File: Create a new text file named HelloWorld.java and open it in a text editor. Write the following code:

2.Compile the Java Program: Open a command prompt or terminal, navigate to the directory containing HelloWorld.java, and run:

Run the Compiled Java Program: Run the compiled Java program with the following command: You should see the output:

By following these steps, you have successfully set up your Java development environment and run your first Java program.

20

![](image_rsrc3N5.jpg)

Summarized Steps to Set Up Java Environment

1\. Download and Install JDK:

o Visit the official Oracle website and download the Java Development Kit (JDK) appropriate for your operating system.

o Follow the installation instructions to install JDK on your system.

2\. Set Up Environment Variables:

o For Windows:

1\. Right-click on 'My Computer' or 'This PC' and select 'Properties'.

2\. Click on 'Advanced system settings'.

3\. Click on the 'Environment Variables' button.

4\. Under 'System variables', click 'New' and add a new variable with the name JAVA_HOME and the path to your JDK installation directory.

5\. Find the Path variable, click 'Edit', and add %JAVA_HOME%\bin.

o For Mac/Linux:

1\. Open the terminal.

2\. Open or create the .bash_profile file in your home directory.

3\. Add the following lines:

21

![](image_rsrc3N6.jpg)

1\. Save the file and run source ~/.bash_profile to apply the changes.

2\. Verify Installation:

o Open a command prompt or terminal window.

o Type java -version and javac -version to verify that Java is installed and configured correctly.

Example:

22

![](image_rsrc3N7.jpg)![](image_rsrc3N8.jpg)

Writing Your First Java Program

Steps to Write and Run a Java Program:

1\. Create a Java Source File:

o Open a text editor and create a new file named HelloWorld.java.

o Write the following code in the file

Compile the Java Source File:

• Open a command prompt or terminal window.

• Navigate to the directory where HelloWorld.java is saved.

• Run the following command to compile the file

• This will generate a HelloWorld.class file in the same directory.

23

![](image_rsrc3N9.jpg)![](image_rsrc3NA.jpg)![](image_rsrc3NB.jpg)

Run the Compiled Java Program:

• In the same command prompt or terminal window, run the following command This will execute the program and display the output

Example:

24

![](image_rsrc3NC.jpg)![](image_rsrc3ND.jpg)

Practice Exercise:

1\. Task: Modify the HelloWorld program to print your name instead of "Hello, World!".

Solution:

2\. Task: Create a new Java program that prints the sum of two numbers.

Solution:

25

![](image_rsrc3NE.jpg)

## Chapter 2: Java Basics

### Java Syntax and Structure

Java programs are written in plain text files ending with the .java extension. These files contain one or more classes and their definitions.

Example of a Basic Java Program:

Explanation:

• public class HelloWorld: Defines a public class named HelloWorld.

• public static void main(String[] args): The main method, which is the entry point for any Java application.

• System.out.println("Hello, World!");: Prints "Hello, World!" to the console.

Practice:

1\. Write a Java program that prints your name.

2\. Write a Java program that prints the sum of two numbers.

26

![](image_rsrc3NF.jpg)

Solution:1

Explanation:

• The PrintName class contains a main method, which is the entry point of the program.

• System.out.println("Craig"); prints the name "Craig" to the console.

27

![](image_rsrc3NG.jpg)

Solution: 2

Explanation:

• The SumOfTwoNumbers class contains a main method.

• Two integer variables, num1 and num2, are declared and initialized with the values 10

and 20, respectively.

• The sum variable is calculated by adding num1 and num2.

• System.out.println("The sum of " + num1 + " and " + num2 + " is: " + sum); prints the result of the sum to the console in a formatted string.

These examples help in understanding the basics of Java syntax and the use of variables and operators. By modifying and experimenting with these programs, you can get more comfortable with writing and running Java code.

28

![](image_rsrc3NH.jpg)![](image_rsrc3NJ.jpg)![](image_rsrc3NK.jpg)![](image_rsrc3NM.jpg)

Java Program Structure

1\. Package Declaration (Optional):

o Packages are used to group related classes. The package declaration is the first line in a Java source file.

Import Statements (Optional):

• Used to import other Java classes into your code.

Class Declaration:

• The class is the fundamental unit of Java programs. Every Java application has at least one class.

Main Method:

• The entry point of any Java application.

29

![](image_rsrc3NN.jpg)

Example:

30

![](image_rsrc3NP.jpg)

Data Types and Variables

Java is a strongly typed language, which means every variable must have a data type.

Primitive Data Types:

int: Integer (e.g., int age = 25;)

double: Double-precision floating-point (e.g., double price = 19.99;) char: Character (e.g., char grade = 'A';)

boolean: Boolean (e.g., boolean isJavaFun = true;)

1\. byte: 8-bit integer (-128 to 127)

2\. short: 16-bit integer (-32,768 to 32,767)

3\. int: 32-bit integer (-2^31 to 2^31-1)

4\. long: 64-bit integer (-2^63 to 2^63-1)

5\. float: 32-bit floating point

6\. double: 64-bit floating point

7\. char: 16-bit Unicode character

8\. boolean: true or false

Example:

31

![](image_rsrc3NR.jpg)![](image_rsrc3NS.jpg)

Reference Data Types:

String: Sequence of characters (e.g., String message = "Hello";)

• Classes, arrays, interfaces, etc.

Example:

Variable Declaration and Initialization:

32

Practice:

1\. Declare and initialize variables of different types and print them.

2\. Write a program to swap two numbers using a temporary variable.

33

![](image_rsrc3NT.jpg)

Practice Exercise Solutions 1

Explanation:

• The VariableTypes class contains a main method.

• Different types of variables are declared and initialized with values.

• System.out.println is used to print each variable to the console

34

![](image_rsrc3NU.jpg)

Practice Exercise Solutions 2

Explanation:

• The SwapNumbers class contains a main method.

• Two integer variables, num1 and num2, are declared and initialized with values 10

and 20, respectively.

• The original values of num1 and num2 are printed to the console.

• A temporary variable temp is used to hold the value of num1 during the swap.

• The values of num1 and num2 are swapped using the temporary variable.

• The swapped values of num1 and num2 are printed to the console.

35

These examples illustrate how to declare and use different types of variables, as well as how to perform basic operations like swapping values using a temporary variable. By practicing these concepts, you'll strengthen your understanding of variable manipulation in Java.

36

![](image_rsrc3NV.jpg)![](image_rsrc3NW.jpg)

Operators and Expressions

Operators are used to perform operations on variables and values.

Arithmetic Operators:

• + Addition

• - Subtraction

• * Multiplication

• / Division

• % Modulus

Example:

Arithmetic Operators:

•

+ (addition), (subtraction), * (multiplication), / (division), % (modulus) Example:

37

![](image_rsrc3NX.jpg)![](image_rsrc3NY.jpg)

Relational Operators:

• == Equal to

• != Not equal to

• > Greater than

• < Less than

• >= Greater than or equal to

• <= Less than or equal to

Example:

Relational Operators:

• == (equal to), != (not equal to), > (greater than), < (less than), >= (greater than or equal to),

<= (less than or equal to)

Example:

38

![](image_rsrc3NZ.jpg)![](image_rsrc3P0.jpg)![](image_rsrc3P1.jpg)

Logical Operators:

• && Logical AND

• || Logical OR

• ! Logical NOT

Logical Operators:

• && (logical AND), || (logical OR), ! (logical NOT)

Example:

Assignment Operators:

• =, +=, =, *=, /=, %=

Example:

39

![](image_rsrc3P2.jpg)

Practice:

1\. Write a program to calculate the area and perimeter of a rectangle.

2\. Write a program to check if a number is even or odd.

Practice Exercise Solutions 1

1\. Write a program to calculate the area and perimeter of a rectangle.

Solution:

Explanation:

• The Rectangle class contains a main method.

• Two double variables, length and width, are declared and initialized with values.

• The area is calculated by multiplying length and width.

• The perimeter is calculated by adding length and width and then multiplying by 2.

• System.out.println is used to print the area and perimeter to the console.

40

![](image_rsrc3P3.jpg)

Practice Exercise Solutions 2

Write a program to check if a number is even or odd.

Solution:

Explanation:

• The EvenOrOdd class contains a main method.

• A Scanner object is created to read input from the user.

• The user is prompted to enter a number using System.out.print.

• The entered number is read using scanner.nextInt.

• An if-else statement is used to check if the number is even or odd using the modulus operator %.

• If the remainder when number is divided by 2 is 0, the number is even; otherwise, it is odd.

41

• The result is printed to the console.

• The scanner.close() method is called to close the scanner object.

These examples demonstrate basic calculations and control flow using if-else statements.

Practicing these exercises will help you understand how to perform arithmetic operations and handle user input in Java.

42

![](image_rsrc3P4.jpg)![](image_rsrc3P5.jpg)

Control Flow Statements

Control flow statements determine the order in which statements are executed. They allow for branching and looping, providing the ability to execute code conditionally or repeatedly.

if Statement:

If-Else Statement

The if-else statement allows you to execute code based on a condition.

Syntax:

43

![](image_rsrc3P6.jpg)![](image_rsrc3P7.jpg)

Example:

44

![](image_rsrc3P8.jpg)

Practice

1\. Write a program to check if a given number is positive, negative, or zero.

Practice: Check if a Given Number is Positive, Negative, or Zero Solution

Explanation:

• The CheckNumber class contains a main method.

• A Scanner object is created to read input from the user.

• The user is prompted to enter a number using System.out.print.

• The entered number is read using scanner.nextDouble.

• An if-else-if statement is used to check if the number is positive, negative, or zero: 45

![](image_rsrc3P9.jpg)![](image_rsrc3PA.jpg)

o If the number is greater than 0, it is positive.

o If the number is less than 0, it is negative.

o If the number is equal to 0, it is zero.

• The result is printed to the console.

• The scanner.close() method is called to close the scanner object.

Test the Program

You can compile and run this program to see how it works with different inputs: Sample runs:

46

![](image_rsrc3PB.jpg)![](image_rsrc3PC.jpg)

By practicing and running this program, you can see how control flow statements like if-else-if can be used to make decisions based on user input in Java.

47

![](image_rsrc3PD.jpg)

Switch Statement

The switch statement allows you to execute one block of code among many based on the value of an expression.

Syntax:

48

![](image_rsrc3PE.jpg)

Example:

49

![](image_rsrc3PF.jpg)

50

Practice:

1\. Write a program to print the name of the month based on the month number (1-12).

51

![](image_rsrc3PG.jpg)

Solution

52

Explanation:

• The MonthName class contains a main method.

• A Scanner object is created to read input from the user.

• The user is prompted to enter a month number using System.out.print.

• The entered month number is read using scanner.nextInt.

• A switch statement is used to determine the name of the month based on the month number:

o Each case corresponds to a month number (1-12), setting the monthName variable to the appropriate month name.

o The default case handles invalid month numbers by setting monthName to an error message.

• The result is printed to the console.

• The scanner.close() method is called to close the scanner object.

53

![](image_rsrc3PH.jpg)![](image_rsrc3PJ.jpg)![](image_rsrc3PK.jpg)![](image_rsrc3PM.jpg)

Test the Program

You can compile and run this program to see how it works with different inputs: By practicing and running this program, you can see how control flow statements like switch can be used to handle multiple conditions in Java.

54

![](image_rsrc3PN.jpg)![](image_rsrc3PP.jpg)

For Loop

The for loop in Java is used to execute a block of code a fixed number of times. It consists of three parts: initialization, condition, and update. These parts control the number of iterations the loop will execute.

Syntax

Initialization: This part is executed only once, at the beginning of the loop. It typically declares and initializes loop control variables.

Condition: This is evaluated before each iteration. If the condition is true, the loop's body is executed. If false, the loop terminates.

Update: This part is executed after each iteration of the loop's body. It typically updates the loop control variables.

55

![](image_rsrc3PR.jpg)

Example: Print Numbers from 1 to 5

Explanation:

• The for loop starts with i initialized to 1.

• The condition i <= 5 ensures that the loop runs as long as i is less than or equal to 5.

• After each iteration, i is incremented by 1 using i++.

56

![](image_rsrc3PS.jpg)

Practice

1\. Write a Program to Print the First 10 Natural Numbers

Solution:

57

![](image_rsrc3PT.jpg)![](image_rsrc3PU.jpg)

Test the Program

You can compile and run this program to see how it works:

Expected output:

Explanation:

• The loop initializes i to 1 and increments i by 1 in each iteration.

• The condition i <= 10 ensures that the loop runs ten times, printing the numbers from 1

to 10.

58

![](image_rsrc3PV.jpg)

2\. Write a Program to Print the Sum of the First 10 Natural Numbers

Solution

Explanation:

• The loop initializes i to 1 and increments i by 1 in each iteration.

• The condition i <= 10 ensures that the loop runs ten times.

• The sum variable accumulates the sum of i in each iteration.

• The final sum is printed after the loop completes.

59

![](image_rsrc3PW.jpg)![](image_rsrc3PX.jpg)![](image_rsrc3PY.jpg)

Test the Program

You can compile and run this program to see how it works:

Expected output:

By practicing these examples, you'll become comfortable using for loops to perform repetitive tasks in Java.

While Loop

The while loop in Java is used to repeatedly execute a block of code as long as a specified condition is true. It is particularly useful when the number of iterations is not known beforehand.

Syntax

•

Condition: This is evaluated before each iteration. If the condition is true, the loop's body is executed. If false, the loop terminates.

60

![](image_rsrc3PZ.jpg)

Example: Print Numbers from 1 to 5

Explanation:

• The loop initializes i to 1.

• The condition i <= 5 ensures that the loop runs as long as i is less than or equal to 5.

• After each iteration, i is incremented by 1 using i++.

61

![](image_rsrc3R0.jpg)![](image_rsrc3R1.jpg)

while Loop:

Practice

1\. Write a Program to Print the Sum of the First 10 Natural Numbers Using a While Loop

Solution:

62

![](image_rsrc3R2.jpg)![](image_rsrc3R3.jpg)

Explanation:

• The loop initializes i to 1.

• The condition i <= 10 ensures that the loop runs as long as i is less than or equal to 10.

• The sum variable accumulates the sum of i in each iteration.

• The final sum is printed after the loop completes.

Test the Program

You can compile and run this program to see how it works:

Expected output:

63

![](image_rsrc3R4.jpg)

3\. Write a Program to Print the First 10 Even Numbers Using a While Loop

Solution

Explanation:

• The loop initializes i to 1 and num to 2.

• The condition i <= 10 ensures that the loop runs 10 times.

• num starts at 2 and is incremented by 2 in each iteration to get the next even number.

• The first 10 even numbers are printed to the console.

64

![](image_rsrc3R5.jpg)![](image_rsrc3R6.jpg)

Test the Program

You can compile and run this program to see how it works:

Expected output:

By practicing these examples, you'll become comfortable using while loops to perform repetitive tasks in Java, especially when the number of iterations isn't predetermined.

65

![](image_rsrc3R7.jpg)![](image_rsrc3R8.jpg)

Do-While Loop

The do-while loop in Java is similar to the while loop, but it guarantees that the loop's body is executed at least once. This is because the condition is evaluated after the loop's body has been executed, not before.

do-while Loop:

Syntax

• Code Block: The code inside the do block is executed at least once and then repeatedly until the condition evaluates to false.

• Condition: This is evaluated after each iteration of the loop. If the condition is true, the loop continues; otherwise, it terminates.

66

![](image_rsrc3R9.jpg)

Example: Print Numbers from 1 to 5

Explanation:

• The loop initializes i to 1.

• The code inside the do block executes, printing the value of i.

• After printing, i is incremented by 1.

• The condition i <= 5 is checked after the loop's body executes. As long as i is less than or equal to 5, the loop continues.

67

![](image_rsrc3RA.jpg)

Practice

1\. Write a Program to Print the Sum of the First 10 Natural Numbers Using a DoWhile Loop

Solution

Explanation:

• The loop initializes i to 1.

• The code inside the do block adds i to sum and increments i by 1.

• The condition i <= 10 ensures that the loop runs as long as i is less than or equal to 10.

• The final sum is printed after the loop completes.

68

![](image_rsrc3RB.jpg)![](image_rsrc3RC.jpg)

Test the Program

You can compile and run this program to see how it works:

Expected output:

69

![](image_rsrc3RD.jpg)

2\. Write a Program to Print the First 10 Odd Numbers Using a Do-While Loop Solution:

Explanation:

• The loop initializes i to 1 and count to 0.

• The code inside the do block prints i (the current odd number) and increments i by 2

to get the next odd number.

• count is incremented each time an odd number is printed.

• The loop continues until count reaches 10.

70

![](image_rsrc3RE.jpg)![](image_rsrc3RF.jpg)

Test the Program

You can compile and run this program to see how it works:

Expected output:

By practicing these examples, you'll understand how do-while loops work and see their advantage in scenarios where the loop's body must be executed at least once regardless of the condition

71

Introduction to Object-Oriented Programming (OOP)

Object-Oriented Programming (OOP) is a programming paradigm based on the concept of

"objects," which can contain data in the form of fields (often known as attributes or properties) and code in the form of procedures (often known as methods). Java is an object-oriented language that leverages this paradigm to structure programs in a modular and reusable way.

Core Concepts of OOP

Class in Java

A class in Java is a blueprint or template for creating objects. It defines a type of object by specifying its properties (fields) and behaviours (methods). Classes encapsulate data for the object and methods to manipulate that data.

Structure of a Class

A class typically consists of the following components:

1\. Fields (Attributes or Properties): Variables that hold the data of the object.

2\. Methods: Functions that define the behaviour of the object.

3\. Constructors: Special methods used to initialize new objects.

4\. Access Modifiers: Keywords that control the visibility of the class and its members (e.g., public, private, protected).

72

![](image_rsrc3RG.jpg)![](image_rsrc3RH.jpg)

Syntax of a class

Example of Creating and Using a Class

73

Explanation:

1\. Class Definition: MyClass defines two fields (myNumber and myString), a constructor, and two methods (display and getNumber).

2\. Constructor: Initializes myNumber and myString with values provided when creating an object.

3\. Methods: display prints the values of myNumber and myString. getNumber returns the value of myNumber.

4\. Object Creation: In the Main class, MyClass obj = new MyClass(10, "Hello World"); creates a new object of MyClass, initializing its fields using the constructor.

5\. Method Calls: obj.display(); calls the display method on the object obj.

obj.getNumber(); calls the getNumber method to retrieve the value of myNumber.

74

![](image_rsrc3RJ.jpg)

Access Modifiers

Access modifiers control the visibility and accessibility of classes, fields, constructors, and methods:

• public: The member is accessible from any other class.

• private: The member is accessible only within the class itself.

• protected: The member is accessible within the same package and by subclasses.

• Default (no modifier): The member is accessible only within the same package.

Example of Access Modifiers:

75

![](image_rsrc3RK.jpg)

Creating and Using a Class

1\. Create a Class File: Save the class definition in a .java file.

2\. Compile: Use javac ClassName.java to compile the class.

3\. Run: Use java Main to run the Main class that utilizes the defined class.

A class in Java is a fundamental construct that allows you to create objects with specific attributes and behaviors. By defining fields, methods, and constructors, you can model real-world entities and organize code in a modular and reusable way. Experiment with creating your own classes to gain a deeper understanding of their functionality and usage.

Class

o A class is a blueprint or template for creating objects. It defines a type of object by bundling data and methods that operate on that data.

Syntax

76

Practice Examples

1\. Creating a Person Class

Objective: Define a Person class with attributes for name and age. Include methods to display person details and check if the person is an adult.

77

![](image_rsrc3RM.jpg)

Solution:

Explanation:

• Fields: name and age.

• Constructor: Initializes the name and age fields.

78

• Methods: displayDetails prints the person’s name and age, isAdult returns whether the person is an adult.

• Testing: In the main method, two Person objects are created and their details and adulthood status are displayed.

2\. Creating a BankAccount Class

Objective: Define a BankAccount class with attributes for account number and balance.

Include methods to deposit, withdraw, and check balance.

79

![](image_rsrc3RN.jpg)

Solution:

80

Explanation:

• Fields: accountNumber and balance.

• Constructor: Initializes the account number and balance.

• Methods: deposit adds money to the balance, withdraw deducts money from the balance, and getBalance returns the current balance.

• Testing: In the main method, a BankAccount object is created and deposit, withdrawal, and balance checking are demonstrated.

81

![](image_rsrc3RP.jpg)

3\. Creating a Rectangle Class

Objective: Define a Rectangle class with attributes for width and height. Include methods to calculate the area and perimeter of the rectangle.

Solution

82

Explanation:

• Fields: width and height.

• Constructor: Initializes width and height.

• Methods: getArea returns the area of the rectangle, getPerimeter returns the perimeter.

• Testing: In the main method, a Rectangle object is created and its area and perimeter are calculated.

These practice examples cover creating classes, initializing objects, and using methods. By experimenting with these examples, you'll better understand how to define and use classes in Java. Feel free to modify and extend these examples to further your learning!

83

Objects in Java

In Object-Oriented Programming (OOP), objects are instances of classes. They are the fundamental building blocks of a program and represent real-world entities or concepts. An object encapsulates both data and behavior related to that data.

Key Concepts of Objects

1\. Creating Objects

2\. Accessing Object Fields and Methods

3\. Object Initialization

4\. Object References

Creating Objects

To create an object in Java, you use the new keyword followed by the class constructor. This process allocates memory for the object and initializes it using the constructor.

84

![](image_rsrc3RR.jpg)

Example

85

![](image_rsrc3RS.jpg)

2\. Accessing Object Fields and Methods

Once an object is created, you can access its fields and methods using the dot (.) operator.

Example:

86

![](image_rsrc3RT.jpg)

3\. Object Initialization

Objects can be initialized using constructors, which can be parameterized or default. If no constructor is explicitly defined, Java provides a default constructor.

Parameterized Constructor Example:

87

![](image_rsrc3RU.jpg)

Default Constructor Example:

88

![](image_rsrc3RV.jpg)

4\. Object References

In Java, variables that hold object references are used to refer to objects. These references point to the memory location where the object is stored.

Example:

89

![](image_rsrc3RW.jpg)

5\. Garbage Collection

Java uses automatic garbage collection to manage memory. When objects are no longer referenced by any part of the program, they become eligible for garbage collection, which reclaims their memory.

Example:

• Creating Objects: Use the new keyword and a constructor to create an object.

• Accessing Fields and Methods: Use the dot (.) operator to interact with an object’s data and behavior.

• Initialization: Objects can be initialized using constructors with or without parameters.

• Object References: Variables hold references to objects, and multiple references can point to the same object.

• Garbage Collection: Java automatically reclaims memory used by objects that are no longer referenced.

Understanding and practicing these concepts will help you effectively use and manage objects in your Java programs.

90

![](image_rsrc3RX.jpg)

Object-Oriented Programming (OOP)

Object-Oriented Programming (OOP) is a programming paradigm that uses "objects" and their interactions to design and implement software. Java is a classic object-oriented language that leverages OOP principles to organize and manage code effectively. Here’s an overview of the core principles of OOP and how they are implemented in Java: Object-Oriented Programming (OOP) in Java uses classes and objects to structure and organize code. By employing the principles of encapsulation, inheritance, polymorphism, and abstraction, you can create robust, maintainable, and reusable code. Understanding these principles and practicing them through coding exercises will help you become proficient in OOP.

Classes and Objects

Class Definition:

• A blueprint for creating objects.

91

![](image_rsrc3RY.jpg)

Creating Objects:

• Instances of a class.

92

Core Principles of OOP

1\. Encapsulation

2\. Inheritance

3\. Polymorphism

4\. Abstraction

Encapsulation in Java

Encapsulation is a fundamental concept in Object-Oriented Programming (OOP) that is used to bundle data (attributes) and methods (functions) that operate on the data into a single unit or class. Encapsulation also involves restricting direct access to some of the object's components, which helps in protecting the integrity of the data.

Key Aspects of Encapsulation

1\. Private Fields: Attributes of a class should be marked as private to restrict direct access from outside the class.

2\. Public Methods: Provide public methods to get (access) and set (modify) the private attributes. These methods are known as getters and setters.

3\. Data Hiding: Prevent direct modification of the fields from outside the class to ensure the object's state is controlled and validated.

Implementing Encapsulation

Here’s a step-by-step guide to implementing encapsulation in Java: 1. Define Private Fields: Use the private access modifier to define fields within a class.

This restricts access to these fields from outside the class.

2\. Provide Public Getter and Setter Methods: Define public methods to provide controlled access to the private fields. The getter method allows reading the value, and the setter method allows modifying it.

93

![](image_rsrc3RZ.jpg)

Example of Encapsulation

Class Definition with Encapsulation:

94

![](image_rsrc3S0.jpg)

Using the Encapsulated Class:

95

Benefits of Encapsulation

1\. Control: Encapsulation allows control over the data by providing methods to access and modify it. This ensures that the data is always in a valid state.

2\. Flexibility: Internal implementation can be changed without affecting other parts of the code that use the class.

3\. Maintainability: Encapsulation helps in keeping code organized and makes it easier to manage and maintain.

4\. Increased Security: By hiding the internal state of the object, encapsulation reduces the risk of unintended interference and misuse.

Encapsulation in Java is implemented by using private fields and public getter and setter methods. This approach ensures that the internal state of an object is protected from unauthorized access and modification. Encapsulation enhances the security, maintainability, and flexibility of code by providing controlled access to the object's data and behavior.

96

Java Implementation

• Private Fields: Use private fields to protect data from outside access.

• Public Methods: Use public getter and setter methods to access and update the private fields.

Example:

97

![](image_rsrc3S1.jpg)

98

Inheritance in Java

Inheritance is one of the core principles of Object-Oriented Programming (OOP). It allows a new class to inherit the properties and methods of an existing class. The new class is known as the subclass or derived class, and the class it inherits from is known as the superclass or base class. Inheritance promotes code reuse and establishes a natural hierarchy between classes.

Key Concepts of Inheritance

1\. Superclass and Subclass

2\. The extends Keyword

3\. Constructor Inheritance

4\. Method Overriding

5\. Accessing Superclass Methods

6\. The super Keyword

7\. Type Casting

99

![](image_rsrc3S2.jpg)

Example of Inheritance

Let's consider a basic example where a superclass Animal is inherited by a subclass Dog.

Superclass: Animal

100

![](image_rsrc3S3.jpg)

Subclass: Dog

Detailed Explanation

1\. Superclass and Subclass

Superclass: The class whose properties and methods are inherited.

Subclass: The class that inherits the properties and methods from the superclass.

• Superclass (Animal in this case) is the class whose properties and methods are inherited.

101

![](image_rsrc3S4.jpg)

• Subclass (Dog in this case) is the class that inherits properties and methods from the superclass

Example:

102

![](image_rsrc3S5.jpg)![](image_rsrc3S6.jpg)

2\. The extends Keyword

In Java, inheritance is specified using the extends keyword. A subclass inherits all accessible properties and methods from its superclass. The extends keyword is used to establish an inheritance relationship between the superclass and the subclass.

Example:

103

![](image_rsrc3S7.jpg)

3\. Constructor Inheritance

Constructors are not inherited. However, a subclass can call the constructor of its superclass using the super keyword.

Example:

104

![](image_rsrc3S8.jpg)![](image_rsrc3S9.jpg)

4.Method Overriding

A subclass can provide a specific implementation for a method that is already defined in its superclass. This is known as method overriding.

Method overriding allows a subclass to provide a specific implementation of a method already defined in its superclass. The overridden method must have the same name, return type, and parameters.

Example:

4\. The super Keyword

105

![](image_rsrc3SA.jpg)![](image_rsrc3SB.jpg)

The super keyword is used to refer to the immediate superclass. It can be used to:

• Call the constructor of the superclass.

• Access superclass methods and fields.

Calling the superclass constructor:

Calling a superclass method:

. Types of Inheritance

• Single Inheritance: A subclass inherits from one superclass.

• Multilevel Inheritance: A subclass inherits from another subclass.

• Hierarchical Inheritance: Multiple subclasses inherit from one superclass.

Inheritance in Java enables the creation of a new class based on an existing class. It facilitates code reusability, logical class hierarchy, and method overriding. Using the extends keyword and super keyword, Java provides a clear and straightforward way to implement inheritance.

This allows subclasses to inherit and enhance the functionality of their superclasses, leading to a more modular and maintainable codebase.

Mechanism where one class inherits the fields and methods of another class.

106

![](image_rsrc3SC.jpg)![](image_rsrc3SD.jpg)

Example:

107

![](image_rsrc3SE.jpg)

Practice Example

Practice 1:

Create a superclass Person with fields name and age and methods to display the details.

Then, create a subclass Student that adds a field studentID and overrides the display method to include the student ID.

Person.java:

108

![](image_rsrc3SF.jpg)

Student.java:

This example demonstrates how inheritance can be used to build a class hierarchy, allowing subclasses to extend and customize the behavior of their superclasses.

109

![](image_rsrc3SG.jpg)

5\. Accessing Superclass Methods

A subclass can access methods of its superclass using the super keyword. This is useful when you need to call the superclass method that has been overridden in the subclass.

Example:

110

![](image_rsrc3SH.jpg)

6\. The super Keyword

The super keyword is used to refer to the immediate parent class object. It can be used to:

• Access superclass methods.

• Call superclass constructors.

• Access superclass fields.

111

![](image_rsrc3SJ.jpg)

7\. Type Casting

Java supports type casting between related classes. This involves converting a subclass reference to a superclass reference and vice versa.

Example:

112

• Inheritance allows a class to inherit properties and methods from another class, promoting code reuse.

• Use the extends keyword to create a subclass.

• Subclasses can inherit methods but not constructors from the superclass.

• Method Overriding allows a subclass to provide a specific implementation of a method already defined in the superclass.

• Use the super keyword to access superclass methods, fields, and constructors.

• Type Casting enables converting between superclass and subclass references.

By understanding and applying these concepts, you can create a well-structured and reusable codebase using inheritance in Java.

113

![](image_rsrc3SK.jpg)

114

![](image_rsrc3SM.jpg)

115

![](image_rsrc3SN.jpg)

Polymorphism

Polymorphism allows methods to do different things based on the object it is acting upon.

This can be achieved through method overloading (compile-time polymorphism) and method overriding (runtime polymorphism).

Java Implementation:

• Method Overloading: Multiple methods with the same name but different parameters within the same class.

• Method Overriding: A subclass provides a specific implementation for a method already defined in its superclass.

Example:

Method Overloading:

116

![](image_rsrc3SP.jpg)

Method Overriding:

117

Abstraction in Java

Abstraction is a key concept in Object-Oriented Programming (OOP) that allows you to hide the complex implementation details of a system and expose only the essential features.

The goal of abstraction is to reduce complexity and allow the programmer to focus on interactions at a higher level without needing to understand the intricate details of each component.

In Java, abstraction is achieved through:

1\. Abstract Classes

2\. Interfaces

1\. Abstract Classes

Definition: An abstract class is a class that cannot be instantiated on its own and may contain abstract methods that must be implemented by subclasses. Abstract methods are methods without a body, meant to be overridden in derived classes.

Features:

• Can have abstract methods (methods without a body).

• Can have non-abstract methods (methods with a body).

• Can have fields and constructors.

• Can be extended by other classes.

118

![](image_rsrc3SR.jpg)

Example:

Abstract Class

119

![](image_rsrc3SS.jpg)

120

![](image_rsrc3ST.jpg)

Interfaces

An interface in Java is a reference type, similar to a class, that can contain only constants, method signatures, default methods, static methods, and nested types. Interfaces cannot contain instance fields or constructors. A class implements an interface, thereby inheriting the abstract methods of the interface.

Features

• Cannot contain instance fields or constructors.

• Can contain abstract methods and default/static methods.

• A class can implement multiple interfaces.

Interface

121

![](image_rsrc3SU.jpg)

122

Benefits of Abstraction

1\. Simplifies Code: Abstraction helps in reducing complexity by hiding implementation details and showing only the necessary features.

2\. Improves Maintainability: Code becomes easier to manage and maintain since changes in the implementation details do not affect the external interface.

3\. Promotes Code Reusability: By defining common functionality in abstract classes or interfaces, you can reuse code across multiple classes.

4\. Enhances Flexibility: Allows you to change the implementation without affecting the code that uses the abstracted components.

Choosing Between Abstract Classes and Interfaces

• Use an Abstract Class When:

o You have a base class that should not be instantiated.

o You want to share common code among related classes.

o You need to provide some method implementations but also require some methods to be abstract.

• Use an Interface When:

o You want to define a contract that can be implemented by any class.

o You need to define methods that must be implemented by multiple classes from different hierarchies.

o You want to support multiple inheritance of type (a class can implement multiple interfaces).

Abstraction in Java helps manage complexity by allowing you to focus on the interactions at a high level while hiding the implementation details. You achieve abstraction using abstract classes and interfaces. Abstract classes provide a way to share code among related classes and define abstract methods that must be implemented by subclasses. Interfaces define methods that must be implemented by any class that chooses to implement the interface, promoting a flexible and reusable design.

123

Chapters 3

Methods and Constructors in Java

In Java, methods and constructors are fundamental components of classes. They define the behaviour of objects and how they are initialized.

Methods

Methods are blocks of code that perform a specific task. They are used to define the behaviour of objects created from a class. Methods can have parameters, return types, and can be called to perform actions on objects.

Key Concepts

1\. Method Declaration

2\. Method Overloading

3\. Method Overriding

4\. Static Methods

5\. Instance Methods

6\. Method Parameters and Return Types

1\. Method Declaration

A method is declared within a class and consists of the following components:

• Access Modifier: Defines the visibility of the method (e.g., public, private).

• Return Type: Specifies the type of value the method will return (e.g., int, void).

• Method Name: The name of the method.

• Parameters: Optional values passed to the method.

• Method Body: The block of code that executes when the method is called.

124

![](image_rsrc3SV.jpg)

Example:

Methods:

125

![](image_rsrc3SW.jpg)![](image_rsrc3SX.jpg)

• Blocks of code that perform specific tasks.

2\. Method Overloading

Method Overloading occurs when multiple methods have the same name but different parameters (type, number, or both). It allows methods to perform similar functions with different input.

Example:

126

![](image_rsrc3SY.jpg)

Method Overriding

Method Overriding occurs when a subclass provides a specific implementation for a method that is already defined in its superclass. The overridden method must have the same name, return type, and parameters as the method in the superclass.

Example:

127

![](image_rsrc3SZ.jpg)

4\. Static Methods

Static Methods belong to the class rather than to any specific instance. They can be called without creating an instance of the class and can only access static fields and methods.

Example:

128

![](image_rsrc3T0.jpg)

5\. Instance Methods

Instance Methods operate on instances of a class and can access instance fields and methods. They require an object of the class to be called.

Example:

129

![](image_rsrc3T1.jpg)

6. Method Parameters and Return Types

Methods can take parameters and return values to perform operations and provide results.

• Parameters: Passed into the method to provide input data.

• Return Type: Specifies what type of value the method will return. If a method doesn’t return a value, its return type is void.

Example:

130

![](image_rsrc3T2.jpg)

## Chapter 4

### Constructors

Constructors are special methods used to initialize objects when they are created. They have the same name as the class and no return type.

Key Concepts

1\. Constructor Declaration

2\. Default Constructor

3\. Parameterized Constructor

4\. Constructor Overloading

5\. Constructor Chaining

1\. Constructor Declaration

A constructor is declared with the same name as the class and has no return type. It initializes the object's state when it is created.

Example:

131

![](image_rsrc3T3.jpg)

2\. Default Constructor

If no constructor is defined, Java provides a default constructor that initializes instance variables to their default values (e.g., null for objects, 0 for numeric types).

Example:

132

![](image_rsrc3T4.jpg)

3\. Parameterized Constructor

A parameterized constructor allows you to initialize objects with specific values.

Example:

133

4.Constructor Overloading

Constructor Overloading is a technique in Java that allows a class to have more than one constructor with different parameter lists. Each constructor performs a different task but constructs objects of the same class. Overloaded constructors provide flexibility in object creation by allowing different ways to initialize an object.

Key Concepts

1\. Same Class, Different Parameters

2\. No Return Type

3\. Different Initialization Option

Example of Constructor Overloading

Let's consider a Rectangle class that demonstrates constructor overloading: 134

![](image_rsrc3T5.jpg)

135

![](image_rsrc3T6.jpg)![](image_rsrc3T7.jpg)

Detailed Explanation

1\. Constructor with No Parameters:

o This constructor initializes both width and height to 0\. It’s useful when you want to create a Rectangle object without specifying any dimensions.

Constructor with One Parameter:

• This constructor initializes both width and height to the same value, which is useful for creating square Rectangle objects.

136

![](image_rsrc3T8.jpg)

Constructor with Two Parameters:

• This constructor initializes the width and height to the specified values, allowing you to create rectangles of any dimension.

137

Benefits of Constructor Overloading

• Flexibility in Object Creation: Users can create objects with different initial values based on the parameters passed.

• Code Readability and Maintenance: Overloading constructors with meaningful parameters can make the code more readable and maintainable.

• Default and Specific Initialization: Allows providing both default and specific ways to initialize an object.

Constructor overloading enhances the flexibility of object creation in Java. By providing multiple constructors with different parameters, you can initialize objects in various ways while maintaining a clean and organized code structure. This technique is widely used in Java to provide multiple options for initializing objects, making classes more versatile and easier to use.

138

![](image_rsrc3T9.jpg)

Constructor Overloading allows a class to have more than one constructor with different parameter lists.

Example:

139

Constructor Chaining in Java

Constructor Chaining in Java is a process of calling one constructor from another constructor within the same class or from a constructor in a subclass. This allows for a more efficient way to initialize an object with multiple constructors, reducing code duplication and enhancing maintainability.

Types of Constructor Chaining

1\. Within the Same Class: Using this()

2\. From a Subclass: Using super()

1\. Constructor Chaining Within the Same Class

When you have multiple constructors in the same class, you can call one constructor from another using the this() keyword. This approach helps in reusing constructor code and keeping initialization logic in one place.

140

![](image_rsrc3TA.jpg)

Example:

In this example:

• The Circle() constructor with no parameters calls the Circle(double radius) constructor.

141

• The Circle(double radius) constructor calls the Circle(double radius, String color) constructor.

• The Circle(double radius, String color) constructor initializes the instance variables radius and color.

142

![](image_rsrc3TB.jpg)

2\. Constructor Chaining from a Subclass

When you have a subclass that extends a superclass, you can use the super() keyword to call a constructor from the superclass. This ensures that the superclass is properly initialized before the subclass adds its own initialization.

Example:

In this example:

• The Dog class extends the Animal class.

• The Dog constructor calls the Animal constructor using super(name), initializing the name field in the Animal class before initializing the breed field in the Dog class.

143

![](image_rsrc3TC.jpg)![](image_rsrc3TD.jpg)

Constructor chaining is a powerful technique in Java that allows constructors to reuse code and ensure proper initialization by calling other constructors within the same class or from a superclass. This helps to reduce redundancy and maintain a clean and organized codebase.

Using this() for chaining within the same class and super() for chaining from a superclass ensures that objects are constructed correctly and efficiently.

• Special methods used to initialize objects.

Example:

144

![](image_rsrc3TE.jpg)

Polymorphism in Java

Polymorphism is one of the four fundamental concepts of Object-Oriented Programming (OOP). It allows objects to be treated as instances of their parent class rather than their actual class. The two main types of polymorphism in Java are:

1\. Compile-Time Polymorphism (Method Overloading)

2\. Run-Time Polymorphism (Method Overriding)

Key Concepts

1\. Method Overloading

2\. Method Overriding

3\. The instanceof Keyword

4\. Dynamic Method Dispatch

1\. Method Overloading (Compile-Time Polymorphism)

Method overloading allows a class to have more than one method with the same name, but different parameters. The methods are resolved at compile time.

Example:

145

![](image_rsrc3TF.jpg)![](image_rsrc3TG.jpg)

Polymorphism:

• Ability to take many forms, typically through method overriding and method overloading.

Method Overriding:

• Redefining a method in a subclass.

Example:

146

![](image_rsrc3TH.jpg)

2\. Method Overriding (Run-Time Polymorphism)

Method overriding allows a subclass to provide a specific implementation of a method that is already defined in its superclass. The method to be executed is determined at runtime.

Example:

147

![](image_rsrc3TJ.jpg)![](image_rsrc3TK.jpg)

3\. The instanceof Keyword

The instanceof keyword is used to test whether an object is an instance of a specific class or a subclass thereof.

Example:

148

![](image_rsrc3TM.jpg)

4\. Dynamic Method Dispatch

Dynamic method dispatch is the mechanism by which a call to an overridden method is resolved at runtime rather than compile time. It allows Java to support run-time polymorphism.

Example:

149

![](image_rsrc3TN.jpg)![](image_rsrc3TP.jpg)

Benefits of Polymorphism

• Code Reusability: Methods can be used in multiple forms.

• Maintainability: Simplifies code maintenance and readability.

• Extensibility: New functionalities can be added with minimal changes to the existing code.

Practice Example

Practice 1:

Create a superclass Shape with a method draw(). Then, create subclasses Circle and Rectangle that override the draw() method. Demonstrate polymorphism by calling the draw() method on objects of these classes.

Shape.java:

Circle.java:

150

![](image_rsrc3TR.jpg)![](image_rsrc3TS.jpg)

Rectangle.java:

Main.java:

This example illustrates how polymorphism allows a single method draw() to have different implementations depending on the actual object type (Circle or Rectangle). This flexibility is one of the core strengths of OOP and enhances the modularity and scalability of the code.

151

## Chapter 5

### Encapsulation and Abstraction

Encapsulation in Java

Encapsulation is one of the fundamental principles of object-oriented programming (OOP).

It refers to the bundling of data (fields) and methods (functions) that operate on the data into a single unit or class. Encapsulation also involves restricting direct access to some of the object's components, which is a means of preventing unintended interference and misuse of the data. This is typically achieved using access modifiers.

Key Concepts

1\. Data Hiding

2\. Access Modifiers

3\. Getter and Setter Methods

Example of Encapsulation

Let's consider an example of a Person class that demonstrates encapsulation.

152

![](image_rsrc3TT.jpg)

Person.java

153

![](image_rsrc3TU.jpg)![](image_rsrc3TV.jpg)

Main.java

Detailed Explanation

1\. Data Hiding

Data hiding is achieved by declaring the class variables as private. This restricts direct access to the fields from outside the class.

154

![](image_rsrc3TW.jpg)

2\. Access Modifiers

Access modifiers in Java control the visibility of class members. The primary access modifiers are:

• private: The member is accessible only within the same class.

• default (no modifier): The member is accessible only within the same package.

• protected: The member is accessible within the same package and subclasses.

• public: The member is accessible from any other class.

3\. Getter and Setter Methods

Getter and setter methods provide a controlled way to access and modify the private fields.

These methods allow for validation, if necessary, before setting a value.

155

Benefits of Encapsulation

• Improved Control: Provides control over the data by restricting direct access and allowing controlled modifications.

• Increased Flexibility: Allows changes in the implementation without affecting other parts of the code.

• Enhanced Maintainability: Makes the code easier to maintain and understand.

• Data Integrity: Helps in protecting the data from accidental or unauthorized modification.

Practice Example

Practice 1:

Create a class BankAccount with private fields accountNumber, balance, and accountHolderName. Implement getter and setter methods for these fields, and include a method to deposit and withdraw money with validation.

BankAccount.java:

156

![](image_rsrc3TX.jpg)

Solution

157

![](image_rsrc3TY.jpg)

Main.java:

This example demonstrates how encapsulation allows you to create classes with private fields that can only be accessed and modified through public methods. This ensures that the internal state of the object is protected and can only be changed in a controlled manner.

158

![](image_rsrc3TZ.jpg)![](image_rsrc3U0.jpg)

Encapsulation:

• Bundling data (fields) and methods into a single unit (class) and restricting direct access to some of the object's components.

Example:

159

![](image_rsrc3U1.jpg)![](image_rsrc3U2.jpg)

Abstraction:

• Hiding complex implementation details and showing only the necessary features.

Example:

160

![](image_rsrc3U3.jpg)![](image_rsrc3U4.jpg)![](image_rsrc3U5.jpg)

## Chapter 6: Basic Data Structures

### Arrays:

• Arrays are a collection of elements of the same type, stored in contiguous memory locations.

• Arrays have a fixed size once they are created.

Declaration and Initialization:

Accessing Elements:

Example:

161

![](image_rsrc3U6.jpg)![](image_rsrc3U7.jpg)

Strings:

• Strings are objects in Java that represent sequences of characters.

• Strings are immutable, meaning their value cannot be changed once created.

Declaration and Initialization:

Common String Methods:

• length(): Returns the length of the string.

• charAt(int index): Returns the character at the specified index.

• substring(int beginIndex, int endIndex): Returns a substring.

• equals(Object another): Compares two strings for equality.

• toUpperCase(): Converts all characters to uppercase.

Example:

162

![](image_rsrc3U8.jpg)

ArrayList and LinkedList

ArrayList:

• A resizable array implementation of the List interface.

• Allows duplicate elements and maintains insertion order.

Example:

163

![](image_rsrc3U9.jpg)

LinkedList:

• A doubly linked list implementation of the List and Deque interfaces.

• Efficient for insertions and deletions at both ends.

Example:

164

![](image_rsrc3UA.jpg)

## Chapter 7: Exception Handling

## Introduction to Exceptions

Exceptions:

• An exception is an event that disrupts the normal flow of a program.

• Java provides a robust mechanism to handle runtime errors through exception handling.

Types of Exceptions:

• Checked Exceptions: Subclasses of Exception (except RuntimeException). Must be either caught or declared in the method signature.

• Unchecked Exceptions: Subclasses of RuntimeException. Not required to be declared or caught.

• Errors: Subclasses of Error. Indicate serious problems that applications should not try to catch.

Try, Catch, and Finally

Syntax:

165

![](image_rsrc3UB.jpg)

Example:

Custom Exceptions

Creating Custom Exceptions:

• Extend the Exception class (for checked exceptions) or RuntimeException class (for unchecked exceptions).

Example:

166

![](image_rsrc3UC.jpg)

167

![](image_rsrc3UD.jpg)

Chapter 8: File I/O and Serialization

File I/O (Input/Output) is a fundamental part of Java programming, allowing you to read from and write to files. Serialization is a mechanism of converting the state of an object into a byte stream, which can then be saved to a file or sent over a network. Deserialization is the reverse process where the byte stream is converted back into an object.

1. Reading and Writing Files

Reading Files

To read files in Java, you can use classes such as FileReader, BufferedReader, or Scanner.

• Using FileReader and BufferedReader:

The FileReader class is a simple way to read characters from a file. To improve efficiency, you often use it in conjunction with BufferedReader, which buffers the input to make reading more efficient.

Example: Reading a File Line by Line

168

![](image_rsrc3UE.jpg)

Explanation:

FileReader is used to read the file "example.txt".

BufferedReader wraps FileReader to allow efficient reading of lines.

The program reads and prints each line from the file until the end.

Reading from a File:

169

![](image_rsrc3UF.jpg)

Writing Files

To write to files, you can use FileWriter or BufferedWriter.

• Using FileWriter and BufferedWriter:

The FileWriter class allows you to write characters to a file, and BufferedWriter can be used to write text to a character-output stream, buffering characters to provide efficient writing.

Explanation:

• FileWriter is used to write to the file "example.txt".

• BufferedWriter wraps FileWriter to allow efficient writing.

• The program writes the string content to the file.

170

![](image_rsrc3UG.jpg)

Writing to a File:

Practice Exercise:

Task: Create a Java program that reads from a file named "input.txt" and writes the content to another file named "output.txt". Add some additional text like "Processed by Java program" to the end of the output file.

171

![](image_rsrc3UH.jpg)

Solution:

Explanation:

• The program reads each line from "input.txt" and writes it to "output.txt".

• After copying all the content, it adds "Processed by Java program" to the end of the output file.

172

![](image_rsrc3UJ.jpg)

Serialization and Deserialization

Serialization is the process of converting an object into a byte stream, so it can be easily saved to a file or transmitted over a network. Deserialization is the process of converting the byte stream back into an object.

Serialization

To serialize an object, the class must implement the Serializable interface. This interface is a marker interface, meaning it doesn’t have any methods to implement but indicates that the class can be serialized.

Example: Serialization

173

![](image_rsrc3UK.jpg)

Explanation:

• Person class implements Serializable, making it eligible for serialization.

• An instance of Person is created and serialized to a file named "person.ser" using ObjectOutputStream.

Serialization:

• Process of converting an object into a byte stream.

Deserialization:

• Process of converting a byte stream back into an object.

Example:

174

![](image_rsrc3UM.jpg)

Deserialization

To deserialize an object, you use ObjectInputStream to read the object from the file and convert it back into an instance of the class.

Example: Deserialization

Explanation:

The program reads the "person.ser" file and deserializes the byte stream into a Person object.

It then prints the deserialized object.

175

Practice Exercise:

Task: Create a Java program that serializes an object representing a book (with attributes like title, author, and price) and then deserializes it from the file, printing the book details.

176

![](image_rsrc3UN.jpg)

Solution:

177

## Chapter 9

Java Collections Framework: List, Set, and Map Interfaces

The Java Collections Framework (JCF) provides a set of interfaces and classes for storing and manipulating groups of data as a single unit—a collection. The primary interfaces in the JCF are List, Set, and Map. Each of these interfaces defines different ways to store and access elements.

1\. List Interface

The List interface extends the Collection interface and represents an ordered collection (also known as a sequence). Lists can contain duplicate elements, and elements can be accessed by their index.

Key Implementations:

• ArrayList: A resizable array implementation.

• LinkedList: A doubly-linked list implementation.

• Vector: A synchronized resizable array.

• Stack: A subclass of Vector representing a LIFO stack.

Common Methods in List:

• add(E e): Appends the specified element to the end of the list.

• add(int index, E element): Inserts the specified element at the specified position in the list.

• get(int index): Returns the element at the specified position in the list.

• remove(int index): Removes the element at the specified position in the list.

• indexOf(Object o): Returns the index of the first occurrence of the specified element in the list.

• size(): Returns the number of elements in the list.

178

![](image_rsrc3UP.jpg)![](image_rsrc3UR.jpg)

Example using ArrayList

Output:

179

The List, Set, and Map interfaces are part of Java's Collections Framework, providing powerful tools for handling groups of objects (collections) with different behaviors and characteristics. Below, we'll explore each of these interfaces in detail, including their key characteristics, usage, and examples. We'll also include practice exercises with solutions.

List Interface:

Overview:

• Ordered Collection: List maintains the order of elements in which they are inserted.

• Duplicates Allowed: List can contain duplicate elements.

• Indexed Access: Elements can be accessed by their index position.

Common Implementations:

• ArrayList

• LinkedList

• Vector (Less commonly used)

180

![](image_rsrc3US.jpg)

Example

181

![](image_rsrc3UT.jpg)

Output

Key Methods:

• add(E e): Adds an element to the list.

• get(int index): Retrieves the element at the specified index.

• remove(int index): Removes the element at the specified index.

• contains(Object o): Checks if the list contains the specified element.

• size(): Returns the number of elements in the list.

182

![](image_rsrc3UU.jpg)

Example:

183

Set Interface

The Set interface extends the Collection interface and represents a collection that cannot contain duplicate elements. It models the mathematical set abstraction.

Key Implementations:

• HashSet: Stores elements in a hash table and does not guarantee any specific order of elements.

• LinkedHashSet: Maintains a linked list of the entries in the set, in the order in which they were inserted.

• TreeSet: Implements the NavigableSet interface, using a tree for storage. The elements are ordered using their natural ordering or a custom comparator.

Common Methods in Set:

• add(E e): Adds the specified element to the set if it is not already present.

• contains(Object o): Returns true if the set contains the specified element.

• remove(Object o): Removes the specified element from the set if it is present.

• size(): Returns the number of elements in the set.

• isEmpty(): Returns true if the set contains no elements.

Overview:

• Unordered Collection: Set does not maintain any order of elements.

• No Duplicates: Set does not allow duplicate elements.

Common Implementations:

• HashSet

• LinkedHashSet (Maintains insertion order)

184

![](image_rsrc3UV.jpg)![](image_rsrc3UW.jpg)

• TreeSet (Maintains sorted order)

Example: Using HashSet

185

![](image_rsrc3UX.jpg)

Example 1

186

![](image_rsrc3UY.jpg)

Example 2

187

![](image_rsrc3UZ.jpg)

Output:

Key Methods:

• add(E e): Adds an element to the set.

• remove(Object o): Removes the specified element from the set.

• contains(Object o): Checks if the set contains the specified element.

• size(): Returns the number of elements in the set.

• isEmpty(): Checks if the set is empty.

188

Map Interface

The Map interface represents a collection of key-value pairs, where each key is unique. Maps are not part of the Collection interface.

Key Implementations:

• HashMap: A hash table-based implementation that allows null values and keys.

• LinkedHashMap: Extends HashMap and maintains a linked list of the entries, preserving insertion order.

• TreeMap: Implements the NavigableMap interface and uses a tree to store the keys in a sorted order.

• Hashtable: Similar to HashMap, but synchronized and does not allow null keys or values.

Common Methods in Map:

• put(K key, V value): Associates the specified value with the specified key in this map.

• get(Object key): Returns the value to which the specified key is mapped, or null if this map contains no mapping for the key.

• remove(Object key): Removes the mapping for a key from this map if it is present.

• containsKey(Object key): Returns true if this map contains a mapping for the specified key.

• keySet(): Returns a Set view of the keys contained in this map.

• values(): Returns a Collection view of the values contained in this map.

Overview:

• Key-Value Pair Collection: Map stores elements as key-value pairs.

• No Duplicate Keys: Each key in a Map must be unique.

• Keys and Values: Values can be duplicated, but keys cannot.

Common Implementations:

• HashMap

• LinkedHashMap (Maintains insertion order)

• TreeMap (Maintains sorted order by keys)

189

![](image_rsrc3V0.jpg)

Example Using HashMap

190

![](image_rsrc3V1.jpg)

Output

Summary:

• List: An ordered collection that can contain duplicate elements. Elements can be accessed by their index.

• Set: A collection that cannot contain duplicate elements. It is not ordered by default (except in the case of LinkedHashSet or TreeSet).

• Map: A collection of key-value pairs, where each key is unique. It allows you to quickly retrieve a value based on a key.

191

![](image_rsrc3V2.jpg)

Example 1

192

![](image_rsrc3V3.jpg)

Output

Key Methods:

•

put(K key, V value): Adds a keyvalue pair to the map.

• get(Object key): Retrieves the value associated with the specified key.

• remove(Object key): Removes the keyvalue pair for the specified key.

• containsKey(Object key): Checks if the map contains the specified key.

• size(): Returns the number of keyvalue pairs in the map.

193

![](image_rsrc3V4.jpg)

Example 2

194

![](image_rsrc3V5.jpg)

Practice Examples

Practice 1: Working with List

Task: Create a List of integers and perform the following operations: 1\. Add numbers to the list.

2\. Remove a number by its value.

3\. Check if the list contains a specific number.

4\. Print all the elements of the list.

Solution:

195

![](image_rsrc3V6.jpg)

Practice 2: Working with Set

Task: Create a Set of strings representing colors and perform the following operations: 1\. Add colors to the set.

2\. Check if a specific color is in the set.

3\. Remove a color.

4\. Print all the colors in the set.

Solution:

196

![](image_rsrc3V7.jpg)

Practice Exercises:

1\. Task:

o Create an ArrayList of student names. Add names, remove a specific name, and display the list.

o Solution:

197

![](image_rsrc3V8.jpg)

2\. Task:

Create a HashSet of book titles. Add titles, check if a specific title exists, and display all titles.

Solution:

198

![](image_rsrc3V9.jpg)

3.Task:

• Create a HashMap to store product names as keys and prices as values. Add, update, remove products, and display all entries.

• Solution:

These exercises help solidify your understanding of List, Set, and Map interfaces and their common implementations. Understanding these concepts is crucial for efficient and effective Java programming.

199

Practice : Working with Map

Task: Create a Map of employee names (keys) and their salaries (values) and perform the following operations:

1\. Add employees and their salaries to the map.

2\. Update the salary of a specific employee.

3\. Remove an employee from the map.

4\. Print all the employees and their salaries.

Solution:

200

![](image_rsrc3VA.jpg)

Summary

List: Ordered collection that allows duplicates. Commonly implemented by ArrayList and LinkedList.

Set: Unordered collection that does not allow duplicates. Commonly implemented by HashSet and TreeSet.

Map: Collection of key-value pairs, with unique keys. Commonly implemented by HashMap and TreeMap.

201

These interfaces and their implementations provide the foundation for working with collections in Java, enabling developers to choose the most appropriate data structure based on their specific needs.

202

Chapter 10

Understanding HashMap, TreeMap, HashSet, TreeSet

The Java Collections Framework (JCF) provides powerful data structures to store and manipulate data efficiently. Four commonly used data structures in this framework are HashMap, TreeMap, HashSet, and TreeSet. Each of these structures has unique characteristics, advantages, and trade-offs, which make them suitable for different scenarios.

1\. HashMap

Overview:

• HashMap is a data structure that implements the Map interface and stores key-value pairs.

• It uses a hash table for storage, providing fast lookups, insertions, and deletions.

• The keys are hashed into buckets, and the position of the bucket in the hash table is determined by the hash code of the key.

Key Characteristics:

• Order: HashMap does not guarantee any specific order of the elements.

• Null Values: Allows one null key and multiple null values.

• Performance: Average time complexity for operations like get(), put(), remove() is O(1).

Common Methods:

• put(K key, V value): Associates the specified value with the specified key in this map.

• get(Object key): Returns the value to which the specified key is mapped.

• remove(Object key): Removes the mapping for the specified key.

• containsKey(Object key): Returns true if this map contains a mapping for the specified key.

• keySet(): Returns a Set view of the keys contained in this map.

• values(): Returns a Collection view of the values contained in this map.

203

![](image_rsrc3VB.jpg)

Example Using Hashmap

204

![](image_rsrc3VC.jpg)

Output

205

![](image_rsrc3VD.jpg)

Example:

206

![](image_rsrc3VE.jpg)

Output

207

Practice Exercise 1

• Task: Create a HashMap that stores the names of students and their grades. Write methods to:

1\. Add a student and their grade.

2\. Retrieve a grade by the student's name.

3\. Update a student's grade.

4\. Remove a student from the HashMap.

5\. Print all students and their grades.

Solution 1

The solution includes methods to add a student and their grade, retrieve a grade by the student's name, update a student's grade, remove a student, and print all students and their grades.

208

![](image_rsrc3VF.jpg)

209

Explanation:

1\. studentGrades HashMap:

o The HashMap is used to store the names of students (as keys) and their grades (as values).

2\. Methods:

o addStudent(String name, int grade): Adds a student's name and their grade to the HashMap.

o getGrade(String name): Retrieves the grade of the student with the specified name.

o updateGrade(String name, int newGrade): Updates the grade of the specified student.

o removeStudent(String name): Removes the specified student from the HashMap.

o printAllStudents(): Prints all students and their grades.

3\. Main Method:

o Demonstrates the functionality by adding students, retrieving a grade, updating a grade, removing a student, and printing all students and their grades.

210

![](image_rsrc3VG.jpg)

Output:

When you run the program, the output will be:

This program provides a clear demonstration of how to use a HashMap for managing a collection of students and their grades in Java.

211

![](image_rsrc3VH.jpg)

Example 2

Implements the Map interface.

Uses a hash table for storage.

Allows null keys and values.

212

2.TreeMap:

Overview:

• TreeMap is a data structure that implements the NavigableMap interface and stores key-value pairs.

• It uses a Red-Black tree to maintain the order of keys.

• The elements are sorted according to their natural ordering or by a custom comparator provided at map creation time.

Key Characteristics:

• Order: TreeMap maintains the elements in ascending order of the keys.

• Null Values: Does not allow null keys (throws NullPointerException) but allows multiple null values.

• Performance: Operations like get(), put(), remove() have a time complexity of O(log n) due to the tree structure.

Common Methods:

• put(K key, V value): Associates the specified value with the specified key.

• get(Object key): Returns the value associated with the specified key.

• remove(Object key): Removes the mapping for a key.

• firstKey(): Returns the first (lowest) key.

• lastKey(): Returns the last (highest) key.

• subMap(K fromKey, K toKey): Returns a view of the portion of this map whose keys range from fromKey to toKey.

213

![](image_rsrc3VJ.jpg)

214

![](image_rsrc3VK.jpg)

Output:

Overview:

• Purpose: TreeMap is a Map implementation that maintains a sorted order of keys.

• Ordering: Natural ordering (according to the keys' Comparable implementation) or a custom Comparator.

• Nulls: TreeMap does not allow null keys but allows multiple null values.

• Performance: Provides O(log n) time complexity for basic operations.

Internal Working:

• TreeMap uses a Red-Black Tree, a self-balancing binary search tree, to maintain the sorted order of the keys.

• This ensures that the entries are always sorted based on the natural ordering of the keys or the order specified by a Comparator.

215

![](image_rsrc3VM.jpg)

Example

• Implements the Map interface.

• Uses a red-black tree for storage.

• Does not allow null keys.

Example 1

216

![](image_rsrc3VN.jpg)

Example 2

217

![](image_rsrc3VP.jpg)

Output

218

Practice Exercise:

• Task: Create a TreeMap that stores product names and their prices. Write methods to:

1\. Add a product and its price.

2\. Retrieve the price of a product.

3\. Update a product's price.

4\. Remove a product from the TreeMap.

5\. Print all products and their prices in ascending order of product names.

Solution

The solution includes methods to add a product and its price, retrieve the price of a product, update a product's price, remove a product, and print all products and their prices in ascending order of product names.

219

![](image_rsrc3VR.jpg)

220

Explanation:

1\. productPrices TreeMap:

o The TreeMap is used to store the names of products (as keys) and their prices (as values). The TreeMap ensures that the products are stored in ascending order of their names.

2\. Methods:

o addProduct(String productName, double price): Adds a product and its price to the TreeMap.

o getPrice(String productName): Retrieves the price of the product with the specified name.

o updatePrice(String productName, double newPrice): Updates the price of the specified product.

o removeProduct(String productName): Removes the specified product from the TreeMap.

o printAllProducts(): Prints all products and their prices in ascending order of product names.

3\. Main Method:

o Demonstrates the functionality by adding products, retrieving a product's price, updating a product's price, removing a product, and printing all products and their prices in ascending order.

221

![](image_rsrc3VS.jpg)

Output:

When you run the program, the output will be:

This program provides a clear demonstration of how to use a TreeMap for managing a collection of products and their prices in Java, ensuring the products are maintained in ascending order of their names.

222

HashSet:

Overview:

• HashSet is a data structure that implements the Set interface and stores unique elements.

• It is backed by a HashMap (the elements are stored as keys in the underlying HashMap).

• Order: Does not guarantee any specific order of the elements.

Key Characteristics:

• Duplicates: Does not allow duplicate elements.

• Null Values: Allows a single null element.

• Performance: The average time complexity for operations like add(), remove(), contains() is O(1).

Common Methods:

• add(E e): Adds the specified element to this set if it is not already present.

• remove(Object o): Removes the specified element from this set if it is present.

• contains(Object o): Returns true if this set contains the specified element.

• size(): Returns the number of elements in the set.

• isEmpty(): Returns true if this set contains no elements.

223

![](image_rsrc3VT.jpg)

224

![](image_rsrc3VU.jpg)

Output:

Overview:

• Purpose: HashSet is a Set implementation that stores unique elements in an unordered manner.

• Ordering: Does not maintain any order.

• Nulls: Allows a single null element.

• Performance: Provides O(1) time complexity for basic operations.

Internal Working:

• HashSet uses a HashMap internally, where the elements of the set are stored as keys in the HashMap, and the associated values are a constant object.

225

![](image_rsrc3VV.jpg)

Example:

226

![](image_rsrc3VW.jpg)![](image_rsrc3VX.jpg)

Output:

• Implements the Set interface.

• Uses a hash table for storage.

• Does not allow duplicate elements.

Example:

227

Practice Exercise:

• Task: Create a HashSet to store unique cities visited by a user. Write methods to: 1\. Add a city.

2\. Check if a city has been visited.

3\. Remove a city from the set.

4\. Print all visited cities.

Solution for the practice exercise that involves working with a HashSet to store unique cities visited by a user. The solution includes methods to add a city, check if a city has been visited, remove a city from the set, and print all visited cities.

228

![](image_rsrc3VY.jpg)

229

Explanation:

1\. visitedCities HashSet:

o The HashSet is used to store the names of cities visited by the user. Since HashSet only allows unique elements, it automatically prevents duplicate cities.

2\. Methods:

o addCity(String city): Adds a city to the HashSet. If the city is already in the set, it will not be added again, and a message will indicate that the city has already been visited.

o hasVisited(String city): Checks if a city is in the HashSet, returning true if it is, and false otherwise.

o removeCity(String city): Removes a city from the HashSet. If the city is not found, it will indicate that the city was not found.

o printAllCities(): Prints all the cities that have been added to the HashSet.

3\. Main Method:

o Demonstrates the functionality by adding cities, checking if a city has been visited, removing a city, and printing all visited cities.

230

![](image_rsrc3VZ.jpg)

Output:

When you run the program, the output will be:

This program shows how to use a HashSet to manage a collection of unique cities, ensuring that no duplicates are stored and providing basic operations like adding, checking, removing, and listing the cities.

231

TreeSet:

Overview:

• TreeSet is a data structure that implements the NavigableSet interface and stores unique elements.

• It is backed by a TreeMap, meaning elements are stored in a Red-Black tree.

• Order: Maintains elements in ascending order.

Key Characteristics:

• Duplicates: Does not allow duplicate elements.

• Null Values: Does not allow null elements.

• Performance: Operations like add(), remove(), contains() have a time complexity of O(log n).

Common Methods:

• add(E e): Adds the specified element to this set if it is not already present.

• remove(Object o): Removes the specified element from this set if it is present.

• contains(Object o): Returns true if this set contains the specified element.

• first(): Returns the first (lowest) element.

• last(): Returns the last (highest) element.

• subSet(E fromElement, E toElement): Returns a view of the portion of this set whose elements range from fromElement to toElement.

232

![](image_rsrc3W0.jpg)

Example Using Treeset

233

![](image_rsrc3W1.jpg)

Output:

Key Differences:

• Order:

o HashMap and HashSet do not guarantee order.

o TreeMap and TreeSet maintain elements in sorted order.

• Performance:

o HashMap and HashSet offer average O(1) time complexity for basic operations.

o TreeMap and TreeSet provide O(log n) time complexity for operations.

• Null Handling:

o HashMap: Allows one null key and multiple null values.

o TreeMap: Does not allow null keys.

234

o HashSet: Allows one null element.

o TreeSet: Does not allow null elements.

Conclusion:

Choosing between these data structures depends on the requirements of your application.

Use HashMap or HashSet when you need fast access to elements without worrying about order. Opt for TreeMap or TreeSet when you need elements to be sorted. Understanding these differences is crucial for optimizing performance and functionality in Java applications.

Overview:

• Purpose: TreeSet is a Set implementation that stores unique elements in a sorted manner.

• Ordering: Maintains a natural order or a custom order specified by a Comparator.

• Nulls: Does not allow null elements.

• Performance: Provides O(log n) time complexity for basic operations.

Internal Working:

• TreeSet uses a TreeMap internally to store its elements. The elements are stored as keys in the TreeMap, ensuring that they are sorted.

235

![](image_rsrc3W2.jpg)

Example:

• Implements the Set interface.

• Uses a red-black tree for storage.

• Does not allow duplicate elements and maintains sorted order.

236

![](image_rsrc3W3.jpg)

Example:

Solution for the practice exercise that involves working with a HashMap to store students'

names and their grades. The solution includes methods to add a student and their grade, retrieve a grade by the student's name, update a student's grade, remove a student, and print all students and their grades.

237

![](image_rsrc3W4.jpg)

238

Explanation:

1\. studentGrades HashMap:

o The HashMap is used to store the names of students (as keys) and their grades (as values).

2\. Methods:

o addStudent(String name, int grade): Adds a student's name and their grade to the HashMap.

o getGrade(String name): Retrieves the grade of the student with the specified name.

o updateGrade(String name, int newGrade): Updates the grade of the specified student.

o removeStudent(String name): Removes the specified student from the HashMap.

o printAllStudents(): Prints all students and their grades.

3\. Main Method:

o Demonstrates the functionality by adding students, retrieving a grade, updating a grade, removing a student, and printing all students and their grades.

239

![](image_rsrc3W5.jpg)

Output:

When you run the program, the output will be:

240

## Chapter 11

Iterators and Enhanced For-Loop in JavaIterators

In Java, Iterator and the enhanced for-loop (also known as the "for-each" loop) are tools that allow developers to traverse or iterate over collections such as List, Set, Map, and arrays.

Understanding how to use these effectively is key to managing collections in Java.

1\. Iterators

Overview:

• An Iterator is an interface in Java that provides a way to traverse through elements in a collection, one element at a time.

• Iterator is a universal cursor for the Collection framework.

• It is particularly useful when you need to remove elements from a collection while iterating over it.

Key Methods in Iterator Interface:

• hasNext(): Returns true if there are more elements to iterate over in the collection.

• next(): Returns the next element in the iteration.

• remove(): Removes the last element returned by the next() method from the collection.

241

![](image_rsrc3W6.jpg)

Example Using Iterator With a List

242

![](image_rsrc3W7.jpg)

Output:

Advantages of Using Iterator:

• Removal During Iteration: Iterator allows safe removal of elements while iterating, which is not possible with the enhanced for-loop.

• Universal Cursor: Iterator works with most collection classes (List, Set, Map, etc.).

Disadvantages of Using Iterator:

• Verbosity: More code is required compared to the enhanced for-loop.

• One-Way Traversal: Iterator can only move forward in the collection. If backward traversal is needed, a ListIterator should be used.

• Used to traverse collections.

243

![](image_rsrc3W8.jpg)

Example:

244

![](image_rsrc3W9.jpg)![](image_rsrc3WA.jpg)

Enhanced ForLoop (ForEach Loop)

Overview:

• The enhanced forloop is a simplified loop for iterating over arrays and collections.

•

It is introduced in Java 5 as a more readable and less errorprone way of iterating over elements in a collection.

Syntax:

Type: The data type of the elements in the collection or array.

element: The variable that holds the current element in the iteration.

collection: The collection or array being iterated over.

Enhanced For-Loop:

• Simplifies iteration over collections and arrays.

Example:

245

![](image_rsrc3WB.jpg)![](image_rsrc3WC.jpg)

Example: Using Enhanced ForLoop with an Array

Output:

246

![](image_rsrc3WD.jpg)![](image_rsrc3WE.jpg)

Example: Using Enhanced ForLoop with a List

Output:

247

Advantages of Using Enhanced For-Loop:

• Simplicity: Less code to write and more readable.

• Less Error-Prone: No need to manage the loop counter or handle IndexOutOfBoundsException.

Disadvantages of Using Enhanced For-Loop:

• No Access to Index: You cannot get the index of the current element during iteration.

• No Modification: You cannot modify the collection (e.g., remove elements) during iteration. Doing so will result in a ConcurrentModificationException.

3\. Iterators vs Enhanced For-Loop:

Use Iterator when:

• You need to remove elements from a collection while iterating.

• You want to traverse over a Map. While the enhanced for-loop can be used to iterate over Map's entry set, Iterator provides more control.

Use Enhanced For-Loop when:

• You are simply reading the elements of a collection and do not need to modify the collection.

• You want a concise and readable way to iterate over arrays or collections.

248

![](image_rsrc3WF.jpg)

Example: Removing Elements with Iterator vs Enhanced For-Loop

Using Iterator to Remove Elements

Output

249

![](image_rsrc3WG.jpg)![](image_rsrc3WH.jpg)

Using Enhanced ForLoop to Read Elements

250

![](image_rsrc3WJ.jpg)

Output

Conclusion:

• The enhanced for-loop is best for simple iterations where you just need to read and process elements without modifying the collection.

• Iterator provides more control and is necessary when you need to remove elements during iteration. Understanding both tools will allow you to choose the most appropriate one for your specific needs.

251

![](image_rsrc3WK.jpg)

## Chapter 12: Generics

### Generics in Java

Generics in Java allow you to write flexible, reusable, and type-safe code. Introduced in Java 5, generics enable classes, interfaces, and methods to operate on types specified by the programmer, enhancing the language's expressiveness and robustness.

1\. What are Generics?

Generics provide a way to parameterize types, enabling you to create classes, interfaces, and methods that can operate on any specified data type. This removes the need to write multiple versions of the same code for different data types, thus promoting code reusability and type safety.

Enable types (classes and interfaces) to be parameters when defining classes, interfaces, and methods.

Example:

252

![](image_rsrc3WM.jpg)

Example Without Generics:

In this example, list is an ArrayList that can store any type of object. If you accidentally add an Integer to this list and later try to cast it to a String, you'll get a ClassCastException at runtime.

253

![](image_rsrc3WN.jpg)

Example With Generics:

Here, ArrayList<String> specifies that the list can only contain String objects. Any attempt to add an incompatible type will cause a compile-time error, preventing potential runtime exceptions.

254

![](image_rsrc3WP.jpg)

Benefits of Generics

• Type Safety: Ensures that only a specific type of data is added to a collection or used in a method.

• Elimination of Casts: No need to cast objects when retrieving them from a collection.

• Code Reusability: Write general algorithms that work on various types without code duplication.

3\. Generic Classes

A generic class is defined with a type parameter. This type parameter can be used as a placeholder for any data type.

Syntax

T is a type parameter that can be replaced by any class or interface type.

255

![](image_rsrc3WR.jpg)![](image_rsrc3WS.jpg)

Example: Generic Box Class

Output:

In this example, Box<T> is a generic class that can hold any type T, which is specified when creating an instance of Box.

256

![](image_rsrc3WT.jpg)

4\. Generic Methods

A generic method is a method that can operate on objects of various types while being declared in a generic or nongeneric class.

<T>: Denotes the type parameter. This can be any name but typically uses single letters like T, E, K, or V.

257

![](image_rsrc3WU.jpg)![](image_rsrc3WV.jpg)

Example: Generic Method for Swapping Two Elements

Output:

258

![](image_rsrc3WW.jpg)![](image_rsrc3WX.jpg)

The swap method works with any array type, whether it's an Integer[] or a String[].

5\. Bounded Type Parameters

Sometimes, you want to restrict the types that can be used as arguments in a generic class or method. Bounded type parameters allow you to enforce such constraints.

Syntax:

Example: Bounded Type Parameter in Generic Method

259

![](image_rsrc3WY.jpg)![](image_rsrc3WZ.jpg)

Output:

In this example, the class BoundExample<T> only accepts types that are subclasses of Number, such as Integer or Double.

6\. Wildcards in Generics

Wildcards are used in generics to represent an unknown type. They are particularly useful when you want to express that a method can accept or return multiple types of objects, but the exact type isn't known.

Types of Wildcards:

1\. Unbounded Wildcard (?): Represents any type.

2.Upper Bounded Wildcard (<? extends T>): Represents a type that is a subclass of T.

260

![](image_rsrc3X0.jpg)![](image_rsrc3X1.jpg)

3.Lower Bounded Wildcard (<? super T>): Represents a type that is a superclass of T.

261

![](image_rsrc3X2.jpg)

Example: Using Wildcards

262

![](image_rsrc3X3.jpg)

Output:

263

![](image_rsrc3X4.jpg)

Generic Interfaces

Just like classes and methods, interfaces can also be generic.

Example: Generic Interface

264

![](image_rsrc3X5.jpg)

Output

8\. Type Erasure

Java generics are implemented via type erasure, which means that the type parameter information is removed during compilation. This process ensures backward compatibility with non-generic code.

• Consequences of Type Erasure:

o You cannot use primitive types as type parameters. Use wrapper classes like Integer, Double, etc.

o You cannot create instances of a generic type (e.g., new T() is not allowed).

o Runtime exceptions related to generics, such as ClassCastException, can still occur.

265

![](image_rsrc3X6.jpg)![](image_rsrc3X7.jpg)

Limitations of Generics

• No Primitive Types: You cannot use primitives as type arguments.

No Generic Arrays: You cannot create an array of a generic type.

Type Erasure: Generic types do not retain their type information at runtime, which may lead to some issues when working with reflection or serialization.

266

![](image_rsrc3X8.jpg)

Generic Methods and Classes

Generic Method:

267

![](image_rsrc3X9.jpg)

Generic Class:

268

![](image_rsrc3XA.jpg)

Bounded Types

Bounded Type Parameters:

• Use bounded type parameters to restrict the types that can be used as type arguments.

Example:

269

## Chapter 13

### Multithreading and Concurrency in Java

Multithreading and concurrency are critical concepts in Java that enable the execution of multiple tasks simultaneously, improving application performance and responsiveness. Java provides robust support for multithreading and concurrency, allowing developers to write applications that can efficiently manage multiple tasks.

1\. Introduction to Multithreading

Multithreading refers to the ability of a CPU (or a single core in a multi-core processor) to provide multiple threads of execution concurrently, supported by the operating system. Each thread represents a separate path of execution.

Key Concepts:

• Thread: A lightweight process that can run concurrently with other threads within a single process.

• Concurrency: The ability of a program to execute multiple tasks simultaneously.

• Parallelism: The simultaneous execution of multiple tasks, often on different processors or cores.

2\. Creating Threads in Java

Java provides two primary ways to create and start a thread:

2.1\. Extending the Thread Class

The simplest way to create a thread is by extending the Thread class and overriding its run() method.

270

![](image_rsrc3XB.jpg)![](image_rsrc3XC.jpg)

Implementing the Runnable Interface

Another common way to create a thread is by implementing the Runnable interface, which has a single run() method.

271

3\. Thread States and Lifecycle

A thread in Java can be in one of several states during its lifecycle:

• New: A thread that has been created but not yet started.

• Runnable: A thread that is ready to run or currently running.

• Blocked: A thread that is waiting for a monitor lock to enter a synchronized block/method.

• Waiting: A thread that is waiting indefinitely for another thread to perform a particular action.

• Timed Waiting: A thread that is waiting for another thread to perform a specific action within a time limit.

• Terminated: A thread that has completed its execution.

4\. Synchronization in Java

Synchronization is the process of controlling access to shared resources by multiple threads to prevent race conditions.

4.1\. Synchronized Methods

You can synchronize a method by using the synchronized keyword. When a method is synchronized, only one thread can execute it at a time for a given object.

272

![](image_rsrc3XD.jpg)![](image_rsrc3XE.jpg)

Synchronized Blocks

For more finegrained control, you can synchronize a specific block of code within a method.

273

Inter-Thread Communication

Java provides several ways for threads to communicate with each other: 5.1\. wait(), notify(), and notifyAll() Methods

These methods are used for communication between threads. They must be called from within a synchronized block or method.

• wait(): Causes the current thread to wait until another thread invokes notify() or notifyAll() on the same object.

• notify(): Wakes up a single thread that is waiting on the object's monitor.

• notifyAll(): Wakes up all threads that are waiting on the object's monitor.

274

![](image_rsrc3XF.jpg)

Example: ProducerConsumer Problem

275

![](image_rsrc3XG.jpg)

Deadlock

A deadlock occurs when two or more threads are blocked forever, waiting for each other to release resources. To avoid deadlocks:

• Acquire resources in a consistent order.

• Use tryLock with a timeout to prevent indefinite waiting.

276

![](image_rsrc3XH.jpg)

Example of a Deadlock

277

![](image_rsrc3XJ.jpg)

7\. Concurrency Utilities

Java provides a java.util.concurrent package that includes high-level concurrency utilities, such as:

7.1\. Executor Framework

The Executor framework provides a way to manage a pool of threads to execute tasks asynchronously.

• ExecutorService: Interface that provides methods to manage the termination and track the progress of asynchronous tasks.

• Executors: Factory methods for creating thread pools.

278

![](image_rsrc3XK.jpg)

Future and Callable

The Callable interface is similar to Runnable, but it can return a result and throw checked exceptions.

The result can be retrieved using a Future.

279

![](image_rsrc3XM.jpg)

Locks

ReentrantLock provides explicit lock management, with more advanced features compared to synchronized blocks.

280

![](image_rsrc3XN.jpg)

Atomic Variables

Atomic variables like AtomicInteger provide a lock-free and thread-safe mechanism to perform atomic operations.

281

Conclusion

Understanding multithreading and concurrency in Java is essential for building high-performance applications. Java provides a rich set of APIs and utilities to help you manage threads effectively, ensuring your programs run smoothly even when performing complex, concurrent tasks. By leveraging these tools and techniques, you can avoid common pitfalls such as race conditions, deadlocks, and inefficient thread management.

Threads:

• A thread is a lightweight process.

• Java provides built-in support for multithreading through the java.lang.Thread class.

Creating Threads (Runnable and Thread Class)

Using Runnable Interface:

282

![](image_rsrc3XP.jpg)

Using Thread Class:

283

![](image_rsrc3XR.jpg)

284

![](image_rsrc3XS.jpg)

Synchronization:

• Ensures that only one thread can access a resource at a time.

Example:

285

![](image_rsrc3XT.jpg)

Concurrency Utilities (ExecutorService, Future, Callable)

ExecutorService:

• A higherlevel replacement for managing threads.

Example:

Callable and Future:

• Callable can return a result and throw a checked exception.

286

![](image_rsrc3XU.jpg)

• Future represents the result of an asynchronous computation.

Example:

287

![](image_rsrc3XV.jpg)![](image_rsrc3XW.jpg)

## Chapter 14: Java Features

Lambda Expressions:

• Provide a clear and concise way to represent a method interface using an expression.

• Enable treating functionality as a method argument or treating a code as data.

Syntax:

Example:

288

![](image_rsrc3XX.jpg)

Streams API:

• Provides a new abstraction to process sequences of elements.

• Supports operations such as filter, map, and reduce.

Example:

289

![](image_rsrc3XY.jpg)

Functional Interfaces:

• An interface with exactly one abstract method.

• Used as the basis for lambda expressions and method references.

Example:

290

![](image_rsrc3XZ.jpg)

Default and Static Methods in Interfaces

Default Methods:

• Allow adding new methods to interfaces without breaking the existing implementation.

Example:

291

![](image_rsrc3Y0.jpg)

Static Methods:

• Can be defined in interfaces and accessed without an instance.

Example:

292

## Part III: Advanced Java

293

![](image_rsrc3Y1.jpg)

## Chapter 15: Java Networking

## Introduction to Networking in Java

### Networking:

• Java provides support for networking through the java.net package.

• Commonly used classes include URL, URI, Socket, ServerSocket, and DatagramSocket.

Working with URLs and URIs

URLs and URIs:

• URL represents a Uniform Resource Locator, a pointer to a resource on the web.

• URI represents a Uniform Resource Identifier, a string of characters used to identify a resource.

Example:

294

Sockets and ServerSockets

Sockets:

• Provide a way for communication between two machines.

• Socket class is used for clientside, and ServerSocket class is used for serverside.

Example (ClientServer Communication):

Server:

295

![](image_rsrc3Y2.jpg)

296

![](image_rsrc3Y3.jpg)

Client:

297

![](image_rsrc3Y4.jpg)

Datagrams and Multicast Sockets

Datagrams:

• Used for sending and receiving packets.

• DatagramSocket is used to send and receive datagram packets.

Example:

298

![](image_rsrc3Y5.jpg)

Chapter 16: Java Database Connectivity (JDBC)

## Introduction to JDBC

JDBC:

• Java API for connecting and executing queries with databases.

• Consists of interfaces such as Connection, Statement, PreparedStatement, and ResultSet.

Connecting to a Database

Example:

299

![](image_rsrc3Y6.jpg)

Executing SQL Queries

Example:

300

![](image_rsrc3Y7.jpg)

Prepared Statements and Transactions

Prepared Statements:

• Used to execute parameterized queries.

• Prevents SQL injection attacks.

Example:

301

## Part III: Advanced Java

302

![](image_rsrc3Y8.jpg)

## Chapter 17: Java GUI Programming

## Introduction to AWT and Swing

AWT (Abstract Window Toolkit):

• Part of Java Foundation Classes (JFC).

• Provides a set of APIs for creating graphical user interfaces.

• Components are heavyweight.

Swing:

• Extension of AWT.

• Provides a richer set of GUI components.

• Components are lightweight.

Example:

303

![](image_rsrc3Y9.jpg)

Building GUI Applications with Swing

Example:

304

![](image_rsrc3YA.jpg)

Event Handling

Event Handling:

• Mechanism to handle events like button clicks.

• Uses event listeners and event sources.

Example:

305

![](image_rsrc3YB.jpg)

Layout Managers

Layout Managers:

• Used to arrange GUI components in a container.

• Common layout managers include BorderLayout, FlowLayout, GridLayout, and BoxLayout.

Example:

306

![](image_rsrc3YC.jpg)

## Chapter 18: JavaFX

## Introduction to JavaFX

JavaFX:

• Modern Java framework for building rich GUI applications.

• Replaces Swing and AWT.

• Supports 2D and 3D graphics, audio, and video.

Building GUI with JavaFX

Example:

307

![](image_rsrc3YD.jpg)

JavaFX Properties and Bindings

Properties and Bindings:

• JavaFX properties enable observing changes to an object's state.

• Bindings connect properties so changes in one reflect in another.

Example:

308

![](image_rsrc3YE.jpg)

FXML and Scene Builder

FXML:

• XMLbased language to define the user interface.

• Scene Builder is a visual layout tool for designing JavaFX applications.

Example:

• Main.java:

309

![](image_rsrc3YF.jpg)![](image_rsrc3YG.jpg)![](image_rsrc3YH.jpg)

layout.fxml:

Controller.java:

310

![](image_rsrc3YJ.jpg)

## Chapter 19: Web Applications with Java

## Introduction to Java EE

Java EE (Enterprise Edition):

• Set of specifications extending Java SE with specifications for enterprise features such as distributed computing and web services.

Servlets:

Java programs that run on a server and handle client requests.

Extend the capabilities of servers that host applications accessed by means of a requestresponse model.

Example:

311

![](image_rsrc3YK.jpg)

JavaServer Pages (JSP)

JSP:

• Technology that helps create dynamically generated web pages based on HTML, XML, or other document types.

• Allows embedding Java code directly in the HTML.

Example:

• index.jsp:

312

![](image_rsrc3YM.jpg)

Building Web Applications with Spring Boot

Spring Boot:

• Framework for building production-ready applications quickly.

• Simplifies the configuration and setup of Spring applications.

Example:

• Application.java:

313

![](image_rsrc3YN.jpg)

## Chapter 20: Design Patterns

## Introduction to Design Patterns

Design Patterns:

• Solutions to common problems in software design.

• Can be classified into creational, structural, and behavioral patterns.

Creational Patterns

Singleton:

• Ensures a class has only one instance and provides a global point of access.

Example:

314

![](image_rsrc3YP.jpg)

Factory:

• Defines an interface for creating an object but lets subclasses alter the type of objects that will be created.

Example:

Builder:

315

• Separates the construction of a complex object from its representation. Example: 316

![](image_rsrc3YR.jpg)

317

Structural Patterns

Adapter:

• Allows incompatible interfaces to work together.

Example:

318

![](image_rsrc3YS.jpg)

319

Composite:

• Composes objects into tree structures to represent partwhole hierarchies.

Example:

320

![](image_rsrc3YT.jpg)

321

Decorator:

• Attaches additional responsibilities to an object dynamically.

Example:

322

![](image_rsrc3YU.jpg)

323

Behavioral Patterns

Strategy:

• Defines a family of algorithms, encapsulates each one, and makes them interchangeable.

Example:

324

![](image_rsrc3YV.jpg)

325

![](image_rsrc3YW.jpg)

Observer:

• Defines a onetomany dependency between objects so that when one object changes state, all its dependents are notified.

Example:

Command:

• Encapsulates a request as an object, thereby letting you parameterize clients with queues, requests, and operations. Example:

326

![](image_rsrc3YX.jpg)

327

![](image_rsrc3YY.jpg)![](image_rsrc3YZ.jpg)

## Chapter 21: Advanced Topics

Reflection API

• Allows inspection and modification of classes, methods, and fields at runtime.

Example:

Annotations:

• Provide metadata for code.

• Can be used for compiler instructions, runtime processing, or generating code.

Example:

328

![](image_rsrc3Z0.jpg)![](image_rsrc3Z1.jpg)

Java Native Interface (JNI)

JNI:

• Enables Java code to interact with native applications and libraries written in other languages like C/C++.

Example:

nativeLib.c:

329

![](image_rsrc3Z2.jpg)

Performance Tuning and Profiling

Performance Tuning:

• Process of making your Java application run faster and more efficiently.

Profiling Tools:

• Tools like JVisualVM, YourKit, and JProfiler help in identifying performance bottlenecks.

Example:

330

![](image_rsrc3Z3.jpg)![](image_rsrc3Z4.jpg)

Modular Programming with Java 9

Modules:

• Introduced in Java 9 to create more manageable and scalable applications.

Module Declaration:

• moduleinfo.java:

Example:

• moduleinfo.java:

331

![](image_rsrc3Z5.jpg)

Main.java:

332

![](image_rsrc3Z6.jpg)

## Chapter 22: Testing and Debugging

Unit Testing with JUnit

JUnit:

• Framework for writing and running unit tests in Java.

Example:

333

![](image_rsrc3Z7.jpg)

Mocking with Mockito

Mockito:

• Framework for creating mock objects.

Example:

334

![](image_rsrc3Z8.jpg)

Debugging Techniques and Tools

Debugging Techniques:

• Breakpoints, stepping through code, and inspecting variables.

Debugging Tools:

• IDEs like IntelliJ IDEA, Eclipse, and NetBeans provide powerful debugging tools.

Example:

335

![](image_rsrc3Z9.jpg)

## Chapter 23: Building and Deployment

Build Tools (Maven, Gradle)

Maven:

• Build automation tool used primarily for Java projects.

Example:

• pom.xml:

336

![](image_rsrc3ZA.jpg)

Gradle:

• Build automation tool that builds upon the concepts of Apache Ant and Apache Maven.

Example:

• build.gradle:

337

![](image_rsrc3ZB.jpg)

Continuous Integration and Deployment

Continuous Integration (CI):

• Practice of merging all developers' working copies to a shared mainline several times a day.

Tools:

• Jenkins, Travis CI, CircleCI.

Example:

338

![](image_rsrc3ZC.jpg)![](image_rsrc3ZD.jpg)

Dockerizing Java Applications

Docker:

• Platform for developing, shipping, and running applications inside containers.

Dockerfile:

Example:

339

Reference

• Arnold, K., Gosling, J., & Holmes, D. (2005). The Java programming language (4th ed.).

Addison-Wesley Professional.

• Bloch, J. (2018). Effective Java (3rd ed.). Addison-Wesley.

• Sierra, K., & Bates, B. (2005). Head first Java (2nd ed.). O'Reilly Media.

• Lippman, S. B. (2012). C++ primer (5th ed.). Addison-Wesley.

• Horstmann, C. S. (2013). Core Java Volume I–Fundamentals (9th ed.). Prentice Hall.

• Eckel, B. (2006). Thinking in Java (4th ed.). Prentice Hall.

• Schildt, H. (2014). Java: The complete reference (9th ed.). McGraw-Hill Education.

• Goetz, B. (2006). Java concurrency in practice. Addison-Wesley Professional.

• Fowler, M. (2003). Patterns of enterprise application architecture. Addison-Wesley.

• Gamma, E., Helm, R., Johnson, R., & Vlissides, J. (1994). Design patterns: Elements of reusable object-oriented software. Addison-Wesley.

• Joshua, J., & Eckstein, R. (2007). Java SE 6 programming. McGraw-Hill.

• Vermeulen, M. (2013). Java 7 new features cookbook. Packt Publishing Ltd.

• Yoon, H. (2007). Java SE 6: What's new? . Pearson Education.

• Liang, Y. D. (2020). Introduction to Java programming and data structures (12th ed.).

Pearson.

• Bates, B. (2008). SCJP Sun certified programmer for Java 6 study guide (CX-310-065).

McGraw-Hill Education.

• Mak, G., & Russell, G. (2004). Java server pages. McGraw-Hill Education.

• Gupta, A. (2017). Spring 5 design patterns. Packt Publishing Ltd.

• Nguyen, D. H., & Johnson, K. (2018). Mastering Microservices with Java. Packt Publishing Ltd.

• Niemeyer, P., & Knudsen, J. (2005). Learning Java (3rd ed.). O'Reilly Media, Inc.

• Lefranois, S. (2018). Mastering Java for data science. Packt Publishing Ltd.

340

• Butch, S., & Zakhour, S. (2013). The Java tutorial: A short course on the basics (6th ed.).

Addison-Wesley Professional.

• Keogh, J. (2005). J2EE: The complete reference. McGraw-Hill Education.

• Richards, M. (2015). Software architecture patterns. O'Reilly Media, Inc.

• Sedgewick, R., & Wayne, K. (2011). Algorithms (4th ed.). Addison-Wesley Professional.

• Sonmez, J. (2015). Soft skills: The software developer's life manual. Manning Publications.

• Pramod, S., & Mak, G. (2002). JSP: The complete reference. McGraw-Hill Education.

• Vasudevan, V. (2005). Java EE 5: The complete reference. McGraw-Hill Education.

• Raj, S. (2019). Microservices architecture. Packt Publishing Ltd.

• Pilone, D., & Pitman, N. (2005). UML 2.0 in a nutshell. O'Reilly Media, Inc.

• Kousen, K. (2013). Making Java Groovy. Manning Publications.

341