![](images/00009.jpeg)

Java From The Ground Up

The Easy Guide For Beginners!

Disclaimer

Effort has been made to ensure that the information in this book is accurate and complete. However, the author and the publisher do not warrant the accuracy of the information, text and graphics contained within the book due to the rapidly changing nature of science, research, known and unknown facts. The author and the publisher do not hold any responsibility for errors, omissions or contrary interpretation of the subject matter herein. This book is presented solely for motivational and informational purposes only.

All Rights Reserved.

No part of this publication or the information in it may be quoted from or reproduced in any form by means such as printing, scanning, photocopying or otherwise without prior written permission of the copyright holder.

Table of Contents

[Introduction](#part0000_split_003.html__Toc442351591)

[Chapter 1: Introduction to Java](#part0000_split_004.html__Toc442351592)

[Chapter 2: Program Structure and Syntax](#part0000_split_005.html__Toc442351593)

[Chapter 3: Variables and Data Types](#part0000_split_007.html__Toc442351594)

[Chapter 4: Operators](#part0000_split_010.html__Toc442351595)

[Chapter 5: Loops](#part0000_split_013.html__Toc442351596)

[Chapter 6: Exceptions](#part0000_split_014.html__Toc442351597)

[Conclusion](#part0000_split_015.html__Toc442351598)

Introduction

This book contains proven steps and strategies on how to create programs using the Java programming language. It also contains details about the topics that every beginner should be aware of.

This book also contains useful information regarding the features you can find in Java as well as why Java is a good program to use. You will also find sample programs that you can use as guidelines when writing your own programs.

Thanks for downloading this book, I hope you enjoy it!

# 
Chapter 1: Introduction to Java

Java is an object-oriented programming language created in 1991 at Sun Microsystems, which is renowned for their high class Unix workstations. The programming language was modeled after C++ and was initially designed to be simple, small, and compatible with a variety of operating systems and platforms.

Java is usually placed in the same category as HotJava, which is a browser from Sun, much like Mosaic or Netscape. Perhaps the most obvious difference of HotJava from other browsers is its ability to play and download applets on your system. These applets show up in your Web page just like any other images, except that they are interactive and dynamic. You can use them to make animations and figures, as well as other things that can respond to your input.

Even though HotJava was the first ever World Wide Web browser to host applets, the support for Java is quickly being made available in many other browsers. For instance, Netscape 2.0 supports Java applets.

If you want to develop an applet, you have to write programs using Java and then compile it. Refer to the applet in the HTML Web pages. Place your Java and HTML files on the website just as you would with any other image or HTML files. The moment someone else views your Web page using a HotJava browser, the browser automatically downloads the embedded applet to their local system and runs it. The reader can then view and interact with the applet in any way they want.

Keep in mind that there are so many things you can do with Java aside from developing applets. The programming language was written in a way to help you solve problems and accomplish tasks just as you would using the C language or C++. In fact, HotJava, including its display, networking, and interface, is created using Java.

A Brief History of Java

The innovation of computer languages is primarily influenced by two factors: programming improvements and computing environment changes. With Java, you can still find the elements found in C and C++, but with more features and refinements. The programming language boasts of features that restructure programming for better architecture.

Java was the brainchild of James Gosling, Chris Wrath, Patrick Naughton, Mike Sheridan, and Ed Frank. Developed at Sun Microsystems, it was originally called “Oak”. Later in 1995, its name was changed to Java. The original purpose of Java was not to be connected to the Internet, but rather to serve as a platform-independent language that can be used to develop software for various electronic devices, including remote controls and microwave ovens. Different kinds of CPUs were used as controllers. However, during that time, computer languages were mostly designed to be compiled for a particular target.

Even though compiling C++ programs for any type of CPU was possible, doing so requires a full compiler for that particular CPU. Because compilers take a lot of time to create and are costly, Gosling and his team searched for a way to have a more portable language that can produce code that is compatible with different CPUs in different environments. The resulting output was the Java programming language.

Principles and Platform

Java has five main objectives: It has to be simple, familiar, and object-oriented; it has to be secured and robust; it has to be portable and architecture-neutral; it has to execute with high performance; and it has to be dynamic, interpreted, and threaded.

Portability is one of Java’s design goals. This means that programs created for its platform have to run similarly on the combinations of operating system and hardware with enough runtime support. This can be achieved when the programming language’s code is compiled to an intermediate representation known as Java bytecode, rather than an architecture-specific machine code.

Take note that the bytecode instructions of Java are analogous to the machine code. Nevertheless, they are meant to be executed by a special type of virtual machine (VM) made especially for the host hardware. A Java Runtime Environment (JRE) is typically used by end users. It is either installed in a Web browser for applets or their machines for standalone applications.

Features, including graphics, networking, and threading are accessed through the standard libraries. Porting becomes simpler with universal bytecodes. Then again, the bytecode interpretation overhead into the machine instructions tends to make the interpreted programs run slower as compared to native executables. The just-in-time (JIT) compilers, on the other hand, have been long introduced to compile bytecodes into machine code. Keep in mind that Java is platform-independent.

Implementations and Performance

Currently, the Java platform is owned by Oracle Corporation. Their implementation is available on Microsoft Windows, including XP. It is also available for Solaris, Mac OS X, and Linux. Such implementation is actually the de facto standard since Java does not have a formal standardization that is recognized by ANSI, ISO/IEC, Ecma International, or any other third-party standards organization.

This implementation is also packaged into two distributions: the Java Development Kit, which includes a debugger, Jar, Javadoc, and Java compiler among other development tools, and the Java Runtime Environment, which contains the platform parts necessary for running programs. Another Java implementation licensed under GNU GPL is the OpenJDK. Its implementation began when Java source code is released under GPL. Since Java SE 7, it has been the official reference implementation.

Java’s goal is to make every implementation compatible with one another. The trademark license of Sun for using Java actually insists for all implementations to be compatible. Because of this, a legal dispute has resulted when Sun claimed that the implementation of Microsoft did not support JNI or RMI. Sun sued Microsoft and won a $20 million settlement in 2001\. Microsoft does not ship Windows with Java anymore.

With regard to performance, all programs created in Java are known for being slow and needing a huge memory. However, ever since just-in-time compilation was introduced in 1997 and 1998, the execution speed of Java has significantly improved. More language features that support better code analysis have been added. These include inner classes, optional assertions, and StringBuilder. Optimizations like HotSpot have been added as well.

The Purpose of Java

Java was created for the purpose of security and portability.

Security

Each time you download a program, you actually take a risk for the code that you download may have a virus. A malicious code is harmful because it can access your system resources without authorization. For instance, a virus program may obtain private and sensitive information, such as passwords and credit card details. It does this by searching the local file system of your computer. Fortunately, Java enables the safe download of applets by confining applets to its execution environment and preventing access to the other parts of your computer. Security is, in fact, considered to be Java’s most innovative aspect. You can download applets without worrying that anything would breach the security of your computer system.

Portability

One of the Internet’s major aspects is portability. There are just so many different kinds of operating systems and computers connected to the Internet. So if a program using Java is virtually run on a computer with an Internet connection, there has to be something that enables such program to be executed on multiple systems. For instance, when using an applet, it has to be downloadable and executable by different kinds of operating systems, browsers, and CPUs connected to the Internet. It is not a good idea to use different types of applets on different computer systems. Keep in mind that the same code should be able to work on all kinds of computers. This means that you need something to generable portable executable codes. Also, remember that the same mechanism should be able to ensure security and create portability.

Buzzwords

Now that you have learned why Java was created, you have to learn about the buzzwords associated with it. Aside from security and portability, there are a bunch of other factors that play a crucial role in its development. The programming language’s design team sums up its key considerations in the following buzzwords list:

Simple

*   It is easy to learn and use.
*   It makes writing programs easier and more convenient.
*   It allows ease of expression.
*   It has a cohesive and concise set of features.
*   Most of the confusing or complex features found in C++ are not found in Java.

Secure

*   It offers data security by means of encapsulation.
*   It allows applets, which are small programs that are automatically downloadable from a computer to another, to be written for security.
*   Security does not get compromised when it comes to applets being able to access the system resources.
*   The applets are run within JVM, protecting them against illegal or unauthorized access to the system resources.

Portable

*   The applications created with Java can be described as portable since they are executable on any type of computer that uses any operating system or CPU.
*   When applications are compiled, they generate intermediate code files known as bytecodes.
*   These bytecodes enable Java to be portable. They can also be taken to any kind of computer for direct execution.

Object – Oriented

*   Java has an object-oriented model.
*   Therefore, it supports features such as encapsulation, polymorphism, inheritance, and abstraction.

Robust

*   Applications and programs in Java are described as robust when they are able to provide response to context.
*   Java has features that make its programs robust, such as exception handling and type checking.

Multithreaded

*   Multithreading is supported in Java, but not in C or C++.
*   Threading is a lightweight process and multithreading can increase the efficiency of the CPU.
*   Programs may be divided into different threads, with each thread concurrently executed or in parallel with other threads.

Architecture – Neutral

*   The bytecodes help the programming language become portable.
*   The bytecodes are executable on computers that run on any type of CPU or operating system.
*   Java is said to be architecture-neutral because its applications can be executed on whatever type of CPU.

High Performance and Interpreted

*   An interpreter is available in version 1.0 specifically for executing bytecodes.
*   Compared to compilers, interpreters are slower. This is why the programs that use Java tend to be executed slowly.
*   The just-in-time (JIT) compiler replaced the interpreter after version 1.0.
*   The just-in-time (JIT) compiler makes use of the Hot Spot technology from the Sun Microsystem.
*   The just-in-time (JIT) compiler converts bytecodes into machine codes one at a time as well as caches them for later use.
*   The performance of programs is enhanced, thereby allowing them to be rapidly executed.

Distributed

*   Distributed computation that uses the Remote Method Invocation (RMI) concept is supported by Java.
*   The client and the server are allowed to communicate with each other. The programs are rapidly executed when computations are divided among the computers available.
*   Resources are shared in a distributed system.

Dynamic

*   Most runtime information regarding objects and the program itself are maintained by the Java Virtual Machine (JVM).
*   At runtime, the libraries are linked dynamically.
*   Hence, the program does not get affected even though you do some dynamic changes to the codes.

# Chapter 2: Program Structure and Syntax

All programs written in Java consist of classes. A class is basically a template used to create an object. Every object contains members, which are either methods or fields. A method is an operation on values or objects passed as arguments while a field is practically a container that stores the value. Objects made by certain class templates are known as the objects or instances of that particular class. Every instance has members that are mentioned in the class template.

Members of a class have identifiers as their names. These names should abide by the syntactic rules specifically made for variables. The objects in Java are actually a Scheme struct generalization since the methods operating on class instances are determined by class definition. The operation sets that manipulate structs in Scheme are fixed.

In this chapter, the structure and basic syntax of a Java program will be discussed.

Structure of a Program

Consider the following sample program:

package sct ;

public class HelloJavaWorld {

/ * *

* comments

* /

public static void main ( String [ ] args ) {

              / / Comment : printing the output on console

              System.out.println ( “ Wendy says Hello Java World “ ) ;

  }

}

As you can see in the above given example, the program has five parts: package sct, public class HelloJavaWorld, comments section, public static void main ( String [ ] args ), and System.out.println ( “ Wendy says Hello Java World “ ) . Let us discuss each part in detail.

First, package sct is the package declaration statement. It defines a name space wherein the classes are stored. The package organizes classes depending on their functionality. When you do not include the package statement, you put the class names in the default package that does not have a name. Take note that package statements are not allowed to appear anywhere else in the program. Your package statement has to either appear on the first line or be omitted.

Public class HelloJavaWorld is a line that has a variety of programming aspects. Public is an access modifier keyword that commands compiler access to class. Different access modifier values can actually be private, public, protected, and no value or default. Class is a keyword used for declaring class. The name of the class, which in this case is HelloJavaWorld, follows it.

The comments section is the area of the program in which you put line comments or block comments. If you choose to write line comments, you have to use a couple of forward slashes ( // ) at the beginning of the comment. Likewise, you have to put these forward slashes at the end of that same comment line. Keep in mind that an ending symbol is no longer necessary when writing a line comment.

A block comment, on the other hand, begins with a forward slash ( / ) and an asterisk ( * ), so it looks like this : / * . It ends with an asterisk and a forward slash, which looks like this : * / . If you choose to writ block comments, you can extend them across as many lines as you want.

Public static void main ( String [ ] args ) is a method or function with a string array as an argument. Public serves as the access modifier while static is a reserved keyword that indicates the existence of a usable and accessible method even when there are no class objects that are present. Void is a keyword that states nothing will be returned from method even though method can return any object or primitive. The method content is within the curly braces ( { } ) .

Finally, there is system.out.println ( “ Wendy says Hello Java World “ ) . System is the name of the utility class in Java while out represents an object that belongs to the System class. Println is a utility method name that is commonly used to send a String to console and “ Wendy says Hello Java World “ is a string literal that functions as an argument to the println method.

Basic Syntax

A program in Java can be described as a collection of objects that communicate by invoking their methods.

An object has a state and behavior. To help you understand it better, you can compare it with a cat. Let us say that the cat is the object. It has states, such as its name, breed, and color. Similarly, it has behaviors, such as purring, eating, and sleeping. With this being said, you can conclude that the object is actually an instance of the class.

A class is a template that describes the states or behaviors of the supported object.

A method is a behavior. Take note that a class may contain as many methods as necessary. It is in these methods where data is manipulated, logic is written, and actions are executed.

Every object has its own unique instance variable set. The state of the object is the output of the values allocated to the instance variables.

With regard to syntax, you should always remember that there are certain points crucial in every Java program. It is wise to keep the following pointers in mind:

*   Case sensitivity. Java is a case sensitive programming language. This means that words featuring uppercase and lowercase letters do not mean the same thing. For example, hello, Hello, and HeLLo are all different identifiers. They have the same spelling, but they are read differently by the computer due to the arrangements of their uppercase and lowercase letters.

*   Class names. Take note that the initial letter of every class name has to be capitalized. If you are using several words for the name of your class, you have to use an uppercase letter at the beginning of each one of these words. For example, you can write class  HelloJavaWorld.

*   Method names. Just like with class names, you have to pay particular attention to the first letter of your method names. However, instead of uppercase letters, you have to use lowercase letters. If there are several words used for your method name, you have to use a lowercase letter at the beginning of the first word and uppercase letters at the beginning of the rest of the words. For example, you can write public void helloJavaWord ( ) .

*   Program file name. The name of your program file has to be an exact match for your class name. When you save your file, you have to save it with a class name. Since Java is a case sensitive programming language, you have to append .java to the end part of your file name. In the event that your class name and file name do not match, the program will not successfully compile. For example, if your class name is ThisIsMyJavaProgram, then you have to save it as ThisIsMyJavaProgram.java.

*   public static void main ( String args [ ] ) . The processing of a program begins at the main ( ) method. This method is actually a mandatory part of all programs written in Java.

# Chapter 3: Variables and Data Types

In Java, there are three main types of variables: local, class or static, and instance or non-static. Variables are basically memory locations wherein values are stored. They have names, types, and values. Before you can use them, you need to declare them. Once you have successfully declared them, you can start allocating values to them.

Anyway, local variables are used within method definitions. Nonetheless, they may also be used within blocks. When a block is done with the execution, the variable definition along with its value disappears. You should use local variables if you need to store data needed by instance variables or a single method to hold information that is needed by methods in an object.

Class variables and instance variables are quite similar, except for the fact that the values of class variables apply to the class and its instances instead of have different values for every object. Instance variables are used for defining attributes or states of objects.

Unlike other programming languages, there are no global variables in Java. When you say global variables, these variables are global to every part of the program. Class and instance variables, for instance, may be utilized to communicate global data between different objects.

Variable Declaration

Before you can use a variable in a program written in Java, you have to declare it. Declaring variables require the use of a variable name and a type. Take a look at the following example:

int myAge ;

String myName ;

boolean is Tired ;

Take note that variable definitions may be placed anywhere within a method definition although, they tend to be declared at the start of the definition prior to their execution. For example:

![nuno1.jpg](images/00001.jpeg)

It is possible to string variable names with a similar type together. Consider the following example:

int a , b , c ;

String givenName , Surname ;

You are allowed to give variables initial values when you declare them as well. Consider the following examples:

int mySize, myAge, numShoes = 20 ;

String myName = “ Wendy “ ;

boolean is Tired = true ;

int w = 4 , x = 5 , y = 6 ;

If there are several variables on the line with just one initializer, the first value only applies to the final variable in the declaration. An example of this would be the first line on the sample codes shown above. Also, you can group initializers and variables on the same line with the use of commas just like what is shown on the last line in the above given example.

Keep in mind that when it comes to using local variables, you have to give them values before you use them. Otherwise, your program will not successfully compile. With this being said, you should make it a habit to give your local variables initial values. Class and instance variable definitions, nonetheless, do not have a similar restriction. This is because their initial values depend on their variable type: 0 for numeric variables, false for booleans, null for class instances, and \0 for characters.

Another important thing to keep in mind about variable names is that these names can begin with an underscore ( _ ) , a dollar sign ( $ ), or a letter. However, they can never begin with a number. As for symbols or special characters such as @, %, and *, they can be used for operators but not in variable names. Hence, you have to be very careful when you write variable names.

Moreover, take note that Java makes use of Unicode, a character set definition offering ASCII characters as well as other characters that represent international alphabets. You can actually use glyphs and accented characters in your variable names, provided that they feature a Unicode character number over 00C0.

Variable Types

For every variable declaration, there has to be a variable type that defines whatever value such variable can store. This variable type can be any of the following: an array, a class name, or a basic primitive data type. There are eight primitive data types that deal with the basic types for floating point numbers, integers, Boolean values, and characters. They are called primitive data types because they are built into the system. They are not really objects, which is why they are more efficient. They are also machine-independent, so their characteristics and sizes are always consistent in every program.

In Java, there are four available integer types, with each one having a different value range. All of them are signed, so they are able to hold negative or positive numbers. Whatever type you select for a variable should depend on the value range that you want that variable to store. In case a value gets too large for your variable type, it gets truncated.

Keywords

Just like with other programming languages, there are reserved words used in Java. Such words may not be used as variables, constants, or any other identifier names. The following are the keywords used in Java:

Comments

You have read about comments when it was used in a sample program in a previous chapter of this book. Both single-line and multiline comments are supported in Java. These comments are actually highly similar to those of C and C++. When you create comments, all the characters within them are ignored by the compiler.

Take a look at the following example:

public class HelloJavaProgram {

              / * This is an example of a program written in Java.

              * The output ‘ Hello Java World ‘ will be printed.

              * This comment is a multiline comment.

              * /

                public static void main ( String [ ] args ) {

                            / / This is a single-line comment example.

                            / * This is another single-line comment example. * /

                            System.out.println ( “ Hello Java World “ ) ;

              }

}

Keep in mind that it is not possible for comments to be nested. This means that you cannot put a comment within another comment. If you are using a single-line comment, you have to use double slashes ( // ) . All texts written until the end of that particular line would not be read by the program.

Comments that start with / * * and end with * / are special types of comments. They are used in the Javadoc system, which is necessary for generating API documentation from codes.

Literals

These are used for indicating simple values in programs. A literal is a term used in Java, which practically means that whatever you type is exactly what you will get. So if you type in 3, you will obtain an integer with a value of 3\. If you type in w, you will obtain a character that has the value of w.

Numeric Literals

There are two main types of numeric literals in Java: exact and approximate.

The exact numeric literal refers to a numeric value that does not have a decimal point. For example, +28, -100, and 11 are all numeric values without decimal points. When you use the integer syntax in Java, the exact numeric literals will support the numbers included within the long range.

The approximate numeric literal, on the other hand, is a numeric value expressed in scientific notation. +11.4, 29, and -99.9 are all examples of this type. When you use the syntax of the floating point literal in Java, you will find that the approximate numeric literals actually support the numbers within the double range.

Integer literals have different types. For example, the number 5 is a type int decimal integer literal. Nonetheless, you can also assign it to a var. of type short or byte since it is small and can fit in such types. Decimal integer literals that are bigger than int are automatically assigned to variables of type long. If you want to force a small number to a type long, you can append an l or L to it. For example, you can say that 5L is a long integer with a value of 5\. As for negative integers, they are typically preceded by a negative or minus sign ( - ) .

You may also express integers as hexadecimal or octal. A number is octal if it has a leading 0, such as in 0005 or 0777\. Conversely, a number is hexadecimal if it has a leading 0X or 0x, such as in 0XAF45 or 0xFF. A hexadecimal number may have uppercase or lowercase digits as well as regular digits. This means that you can use either A to F and a to f or 0 to 9.

As for floating point literals, they generally have two parts: integer and decimal. They result in floating point numbers of the type double, no matter what the precision of such numbers is. If you want to force a number to be of the type float, you can append letter F or f to it, such as in 2.56F. In addition, you can use an exponent in a floating point literal through the letter E or e, trailed by whatever exponent you are using. It can even be a negative number. For example, you can write .36E-2 or 10e45.

Boolean Literals

These literals are either true or false. The keywords true & false are not case-sensitive, so you can write them in uppercase or lowercase letters and the computer will still read them the same. You can also use them anywhere in your program where a test is necessary or if they are the only possible Boolean variable values.

Character Literals

These literals are expressed using a single character that features single quotes, such as in ‘w’, ‘5’, and ‘#’. Characters are actually stored as 16-bit characters in Unicode. The following is a list of the special codes representing non-printable characters and characters included in the Unicode. Take note that the letter ‘d’ in the Unicode, octal, and hex escapes represents a hexadecimal digit or number.

Character escape codes

![nuno7.jpg](images/00002.jpeg)

If you are used to writing programs in C or C++, you may notice that in Java, character codes for \v or vertical tab and \a or bell are not included.

String Literals

A string is essentially a combination of characters. In Java, strings are occurrences of the class String. Since string objects are considered as real objects, they feature methods that allow you to test, modify, and combine strings easily. When you write string literals, you have to write them with other characters within double quotes. Take a look at the following example:

“ Hell, this is an example of a string literal. “

“” // This is actually an empty string

Take note that strings may feature character constants like Unicode characters, newline, and tab. Here are some examples to help you understand this concept further:

“ This is an example of a string that includes a \t or tab “

“ A nested string is a \ “ string found within \ “ another string “

“ This string example is written by Javaman\u2122 “

As you can see, the last line features \u2122 which is a Unicode code sequence that produces the trademark symbol ( ™ ) . Furthermore, you have to remember that sometimes, the operating system or computer you are using may not be able to display the characters represented by Unicode escapes. This may be because your operating system or computer does not support Unicode. Similarly, your font may not have a picture or glyph for such characters.

# Chapter 4: Operators

Operators are basically special symbols used in expressions, such as arithmetic and tests for magnitude and equality. Since they return values, it is possible to assign their results to variables. You can also test such values in other statements. The operators in Java are arithmetic, relational, bitwise, logical, assignment, and miscellaneous.

Arithmetic Operators

These operators are used the same way as mathematical expressions.

![nuno8.jpg](images/00003.jpeg)

To help you understand arithmetic operators better, consider the following sample program:

class ArithmeticTesting {

public static void main ( String [ ] args ) {

short w = 6 ;

int n = 4 ;

float d = 12.5f ;

float y = 7f ;

System.out.println ( “ w is “ + w + “ , n is “ + n ) ;

System.out.println ( “ w + n = “ + ( w + n ) ) ;

System.out.println ( “ w - n = “ + ( w – n ) ) ;

System.out.println ( “ w / n = “ + ( w / n ) ) ;

System.out.println ( “ w % n = “ + ( w % n ) ) ;

System.out.println ( “ d is “ + d + “ , y is “ + y ;

System.out.println ( “ d / y = “ + ( d / y ) ) ;

}

}

If you run the sample program shown above, you will get the following output:

w is 6, y is 4

w + n = 10

w – n = 2

w / n = 1

w % n = 2

d is 12.5 , y is 7

d / y = 1.78571

As you can see in the sample program, four variables are initially defined in the main ( ) method. These variables are of type int or integers as well as type float or floating point numbers. Take note that the default type of floating point literals is double. Thus, you have to make sure that the numbers you use are of type float. You can do this by including the letter ‘f’ after the number. The rest of the program simply performs mathematical operations on the floating point numbers and integers. The results are then printed, as shown in the output.

You may be wondering about the System.out.println ( ) method. Well, this method simply prints out the message to the output of the system. This can be your screen, a special log file, or a special window. It all depends on your development environment and system. This method also takes an argument, which is a string. Nevertheless, you can also use + if you want to concatenate the values into a string.

Relational Operators

![nuno9.jpg](images/00004.jpeg)

Bitwise Operators

In Java, bitwise operators are often applied to integer types, byte, char, short, long, and int. They work on bits as well as perform bit-by-bit operations.

![nuno10.jpg](images/00005.jpeg)

Logical Operators

![nuno11.jpg](images/00006.jpeg)

Assignment Operators

![nuno12.jpg](images/00007.jpeg)

Miscellaneous Operators

In Java, there are several other operators that are supported by the programming language.

The Conditional Operator ( ? : )

This operator is also commonly referred to as the ternary operator. It consists of three operands and is meant for evaluating Boolean expressions. Its main goal is to determine which value must be allocated to the variable. It is written as follows:

variable w = ( expression ) ? value if true : value if false

To help you understand about the conditional operator further, take a look at the following example:

public class Test {

              public static void main ( String args [ ] ) {

                            int x, y ;

                            x = 10 ;

                            y = ( x == 1 ) ? 20 : 30 ;

                            System.out.println ( “ The value of y is : “ + y ) ;

                            y = ( x == 10 ) ? 20 : 30 ;

                            System.out.println ( “ The value of y is : “ + y ) ;

              }

}

If you run the sample program shown above, you will obtain the following output:

The value of y is : 30

The value of y is : 20

The Instance Of Operator

This operator is only used for object reference variables. It verifies if an object is of a certain type (interface type or class type). It is written as follows:

( Object reference variable ) instanceof ( class / interface type )

When the variable at the left side of the operator refers an object and it passes the IS-A check for interface and class type, the result becomes true. Take a look at the following sample program:

public Class Test {

              public static void main ( String args [ ] ) {

                String name = “ Jesus “ ;

                // The following returns true because the name is a string type

                boolean result              = name instanceof String ;

                System.out.println ( result ) ;

              }

}             

If you run the sample program shown above, you will get the following output:

true

# Chapter 5: Loops

A loop statement lets you execute statements over and over again. In Java, there are three main types of loop: while, for, and do … while.

The While Loop

The while loop tests the condition and repeats the statement if the condition is found to be true. To help you understand this topic further, take a look at the following example:

![java2](images/00008.jpeg)

If you run the program shown above, you will get the following output:

Please enter an integer value

7

You have entered 7

Please enter an integer value

-2

You have entered -2

Please enter an integer value

9546

You have entered 9546

Please enter an integer value

0

It is out of loop!

The For Loop

The for loop executes the statement several times as well as abbreviates the code that handles the loop variable. You are allowed to initialize as many variables as you want. You can also test a lot of conditions as well as perform decrements or increments on as many variables as necessary. If you no longer want the loop to continue and wish to terminate it, you simply have to press Ctrl + C.

Consider the following sample program. It prints the first ten natural numbers.

class ForLoop {

public static void main ( String [ ] args ) {

  int w ;

  for ( w = 1 ; w <= 10 ; w++ ) {

System.out.println ( w ) ;

  }

}

}

If you run the example shown above, you will get the following output:

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

The Do . . . While Loop

The do … while loop is similar to the while loop, except that it only tests the condition in the end. Take a look at the following example:

public Class Test {

              public static void main ( String args [ ] ) {

                            int w = 20 ;

                            do {

                                          System.out.print ( “ The value of w is “ + w ) ;

                                          w ++ ;

                                          System.out.print ( “ \n “ ) ;

                            } while ( w < 30 ) ;

              }

}

If you run the above given sample program, you will obtain the following output:

The value of w is 20

The value of w is 21

The value of w is 22

The value of w is 22

The value of w is 23

The value of w is 24

The value of w is 25

The value of w is 26

The value of w is 27

The value of w is 28

The value of w is 29

# Chapter 6: Exceptions

An exception is used to handle an error. It can also be used to handle an exceptional event that disrupts the regular flow of the program. In Java, there are several ways in which an exception can occur:

*   The object is null.
*   The network connection is lost.
*   The data provided is not in the expected format.
*   The database is not connected.

Checked versus Unchecked Exceptions

Checked Exceptions

These are a subclass of Exception with the exclusion of Runtime Exception and the subclasses that come with it. They force you to handle any exception that you encounter. When these exceptions occur in a method, such method has to either take the exceptions and perform the appropriate course of action or pass them onto the caller. An arithmetic exception is an example of a checked exception.

Unchecked Exceptions

These exceptions include Runtime Exception along with its subclasses. With unchecked exceptions, the compiler does not force you to catch them or declare them in a throws clause. You might not even be aware that such exceptions can be thrown. These exceptions, except for runtime exceptions, have to be received during compilation time. An ArrayIndexOutOfBounds exception is an example of an unchecked exception.

Exceptions Handling

As a programmer, you have to know how to handle exceptions in order for you to be able to develop robust applications. Exceptions handling means transferring the execution of a program to the appropriate handler in the event that an exception occurs. You can use a try block and a catch block to handle exceptions.

A try block contains statements within which an exception may occur. It is followed by a catch block, which handles any exception that occurs in relation to the try block. It should always be followed either by a catch block, a finally block, or both.

A catch block is used to match the exception. It is always associated with the try block. There can be more than a single catch clause for a single try block. If an exception occurs within the try block, the corresponding catch block has to execute.

A finally block always executes when there is a try block. However, it does more than merely executes during exceptions handling. It also allows you to avoid dealing with cleanup codes that are accidentally bypassed by a continue, break, or return. It is a good habit to always put a cleanup code in the finally block, even when you are not expecting any exceptions.

# Conclusion

Thank you again for downloading this book!

I hope this book was able to help you learn about the Java programming language from a beginner’s point of view.

The next step is to apply what you have learned from this book.

Did you like this book?

If you enjoyed this book, please give your review on Amazon: [CLICK HERE!](https://www.amazon.com/review/create-review?ie=UTF8&asin=B01BGRESWG&channel=detail-glance&nodeID=133140011&ref_=cm_cr_dp_no_rvw_e&store=digital-text)

If you believe this book is worth sharing, would you take a few seconds to let your friends know about it?

If it turns out to make a difference in their lives, they'll be forever grateful to you.

As I will.

All the best,

Jonathan Fritz