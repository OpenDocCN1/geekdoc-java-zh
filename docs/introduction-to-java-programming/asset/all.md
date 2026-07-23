![](cover.jpeg)

![](images/00005.jpeg)

**K. SOMASUNDARAM**

#### ![](images/00006.jpeg)

JAICO PUBLISHING HOUSE

Ahmedabad  Bangalore  Bhopal  Bhubaneswar  Chennai
Delhi  Hyderabad  Kolkata  Lucknow  Mumbai

Published by Jaico Publishing House
A-2 Jash Chambers, 7-A Sir Phirozshah Mehta Road
Fort, Mumbai - 400 001
[jaicopub@jaicobooks.com](mailto:jaicopub@jaicobooks.com)
[www.jaicobooks.com](http://www.jaicobooks.com "jaicopub@jaicobooks.com")

© Dr. K. Somasundaram

INTRODUCTION TO JAVA PROGRAMMING
ISBN 978-81-8495-443-2

First Jaico Impression: 2013

No part of this book may be reproduced or utilized in any form or by any means, electronic or mechanical including photocopying, recording or by any information storage and retrieval system, without permission in writing from the publishers.

Acknowledgements

I thank all the students of MCA and MSc-IT courses (1995-2013) of Gandhigram Rural Institute, Gandhigram, for whom I learned Java language.

I thank my wife S. Gomathi, sons S. Praveen Kumar and S. Magesh who spared the time to prepare this manuscript which otherwise should have been family time. I thank Mrs. T. Vasantha for preparing the manuscript and typesetting it in PageMaker. I also thank Mr. V. Pechi who helped in preparing few chapters of the manuscript. I thank Mr. Soumen Mukherjee of Jaico Publishing House for initiating and giving valuable suggestions on the outline of this book, and also the entire editorial team at Jaico for their efforts in bringing out this book.

Dr. K. Somasundaram

Preface

This book is the outcome of the preparations I have made for a course on Java Programming to the students of MCA and MSc. programs at Gandhigram Rural Institute for the past 15 years. Though I have had excellent exposure to other computer programming languages like FORTRAN, COBOL, BASIC, Pascal and C, for developing scientific and commercial software, it was an entirely different experience to learn Java. When I started reading the Java Hand Book by Patrick Naughton in 1995, I was puzzled to find the structure and syntax of a Java program. In fact it was difficult to identify which is the starting point of a Java program. But in the course of reading the book and understanding the concepts, I found the awesome capabilities of Java language. I hope any reader who reads an introductory book on Java may also experience the same.

This book is intended for a one semester (starter level) course on Java programming. It includes the new features included in JDK1.7\. One of the notable things that you will find in this book, if you compare with other books, is the use of the recently introduced printf() method defined in Console class instead of the classical statement System.out.println().

The book is organized in 16 chapters. Chapter 1 explains the Object Oriented Programming (OOP) concepts, Java technology and its features. Java literals, data types and variables are explained in Chapter 2. Chapter 3 gives the feel of a Java program. The operators available in Java language are given in Chapter 4\. The flow control statements are given in Chapter 5 with illustrative programs. Chapter 6 deals with arrays and the Java’s Arrays class. Chapter 7 introduces the class concepts and details how objects are created from the classes. The reader needs to spend some time to understand thoroughly the basic concepts introduced in this chapter. Chapter 8 explains the inheritance used for reusing the existing codes and demonstrates it, through illustrative programs. In Chapter 9, the concept of package used to arrange and manage classes is explained. Further, how the encapsulation is realized using the access specifiers, like private, protected and public, is given. The interfaces, using which many programmers can implement the same method with different codes are given. Chapter 10 introduces wrapper classes through which one can create objects for basic types. Abnormal conditions occurring in a program, called exceptions, are explained in Chapter 11\. This chapter demonstrates how one can develop error-free and robust Java programs. Handling a stream of input/output data is dealt in Chapter 12\. Handling text using Strings is given in Chapter 13\. Methods defined in three string classes are explained in it. Chapter 14 explains how multithreaded programs are created. The applet, which is a second kind of Java program for client side programming, is explained in Chapter 15\. Drawing regular shapes using methods defined in Graphics class are explained in Chapter 16.

In each chapter, review questions are given that will help readers to self-test their learning. In many chapters, “Try It Out” programs are given that enables the reader to develop programs for real life problems.

The chapters are so arranged, that any beginner can move from one chapter to another very smoothly. I have not included any topic that will surprise the reader at any point. Any beginner without any background on any programming language can use this book. I am sure, that after reading this book, the reader will gain the confidence to develop programs using Java. This book will give a solid foundation on Java that will make the reader jump to higher level topics on Java like Swing, JDBC, Servlets etc.

Those who would like to make suggestions on the content and presentation, or have questions on Java concepts are most welcome to email me at: [ka.somasundaram@gmail.com](mailto:ka.somasundaram@gmail.com). All queries will be answered.

**August 2013** **Dr. K. Somasundaram**

Contents

*[Acknowledgements](#part0003.html_2RHM0-0ea0eda4f36c456fb2912dcb6e4fa5a9)*

*[Preface](#part0004.html_3Q280-0ea0eda4f36c456fb2912dcb6e4fa5a9)*

**[1. Introduction](#part0006.html_5N3C0-0ea0eda4f36c456fb2912dcb6e4fa5a9)**

[1.1 Object-Oriented Programming Concepts](#part0006.html_h1)

[1.1.1 Encapsulation](#part0006.html_h2)

[1.1.2 Inheritance](#part0006.html_h3)

[1.1.3 Polymorphism](#part0006.html_h4)

[1.2 Features of Java Language](#part0006.html_h5)

[1.3 Types of Java Programs](#part0006.html_h6)

[1.4 Java Architecture](#part0006.html_h7)

[*Exercise – 1*](#part0006.html_h8)

**[2. Literals, Data Types and Variables](#part0007.html_6LJU0-0ea0eda4f36c456fb2912dcb6e4fa5a9)**

[2.1 Literals](#part0007.html_h1)

[2.1.1 Integer Literals](#part0007.html_h2)

[2.1.2 Floating Point Literals](#part0007.html_h3)

[2.1.3 Character Literals](#part0007.html_h4)

[2.1.4 String Literals](#part0007.html_h5)

[2.1.5 Boolean Literals](#part0007.html_h6)

[2.2 Data Types](#part0007.html_h7)

[2.2.1 Integer Types](#part0007.html_h8)

[2.2.2 Floating Point Types](#part0007.html_h9)

[2.2.3 Character Type](#part0007.html_h10)

[2.2.4 Boolean Type](#part0007.html_h11)

[2.3 Variables](#part0007.html_h12)

[*Exercise – 2*](#part0007.html_h13)

**[3\. The Structure of a Java Program](#part0008.html_7K4G0-0ea0eda4f36c456fb2912dcb6e4fa5a9)**

[3.1 Structure of a Java Program](#part0008.html_h1)

[3.2 Comments](#part0008.html_h2)

[3.3 Expressions and Statements](#part0008.html_h3)

[3.4 Type Conversion](#part0008.html_h4)

[3.5 Block Statements and Scope](#part0008.html_h5)

[*Exercise – 3*](#part0008.html_h6)

**[4. Operators](#part0009.html_8IL20-0ea0eda4f36c456fb2912dcb6e4fa5a9)**

[4.1 Arithmetic Operators](#part0009.html_h1)

[4.2 Bitwise Operators](#part0009.html_h2)

[4.3 Relational Operators](#part0009.html_h3)

[4.4 Boolean Logical Operators](#part0009.html_h4)

[4.5 Ternary Operator](#part0009.html_h5)

[4.6 Operator Precedence](#part0009.html_h6)

[*Exercise – 4*](#part0009.html_h7)

**[5\. Control Statements](#part0010.html_9H5K0-0ea0eda4f36c456fb2912dcb6e4fa5a9)**

[5.1 The if..else Statement](#part0010.html_9H5K0-0ea0eda4f36c456fb2912dcb6e4fa5a9)

[5.2 The switch Statement](#part0010.html_h1)

[5.3 The while Statement](#part0010.html_h2)

[5.4 The do..while Statement](#part0010.html_h3)

[5.5 The for… Statement](#part0010.html_h4)

[5.6 The break Statement](#part0010.html_h5)

[5.7 The continue Statement](#part0010.html_h6)

[5.8 The Comma Statement](#part0010.html_h7)

[*Try It Out*](#part0010.html_h8)

[*Exercise – 5*](#part0010.html_h9)

**[6. Arrays](#part0011.html_AFM60-0ea0eda4f36c456fb2912dcb6e4fa5a9)**

[6.1 One-Dimensional Array](#part0011.html_h1)

[6.2 Multi-Dimensional Array](#part0011.html_h2)

[6.3 Arrays Class](#part0011.html_h3)

[*Try It Out*](#part0011.html_h4)

[*Exercise – 6*](#part0011.html_h5)

**[7. Classes](#part0012.html_BE6O0-0ea0eda4f36c456fb2912dcb6e4fa5a9)**

[7.1 Defining a Class](#part0012.html_h1)

[7.2 The new Operator and Objects](#part0012.html_h2)

[7.3 The dot(.) Operator](#part0012.html_h3)

[7.4 Method Declaration and Calling](#part0012.html_h4)

[7.5 Constructors](#part0012.html_h5)

[7.6 Instance Variable Hiding](#part0012.html_h6)

[7.7 this in a Constructor](#part0012.html_h7)

[7.8 Method Overloading](#part0012.html_h8)

[7.9 Passing Objects as Parameter to Methods](#part0012.html_h9)

[7.10 Passing Array as Parameter to Method](#part0012.html_h10)

[*Try It Out*](#part0012.html_h11)

[*Exercise – 7*](#part0012.html_h12)

**[8. Inheritance](#part0013.html_CCNA0-0ea0eda4f36c456fb2912dcb6e4fa5a9)**

[8.1 Creating Subclasses](#part0013.html_h1)

[8.2 Method Overriding](#part0013.html_h2)

[8.3 Final Class](#part0013.html_h3)

[8.4 Final Method](#part0013.html_h4)

[8.5 Final Variables](#part0013.html_h5)

[8.6 Object Destruction and Garbage Collection](#part0013.html_h6)

[8.7 Recursion](#part0013.html_h7)

[8.8 Static Methods, Variables and Blocks](#part0013.html_h8)

[8.8.1 Static Methods](#part0013.html_h9)

[8.8.2 Static Variables](#part0013.html_h10)

[8.8.3 Static Blocks](#part0013.html_h11)

[8.9 Abstract Classes](#part0013.html_h12)

[8.10 Mathematical Methods](#part0013.html_h13)

[8.11 Time and Date](#part0013.html_h14)

[*Try It Out*](#part0013.html_h15)

[*Exercise – 8*](#part0013.html_h16)

**[9\. Packages and Interfaces](#part0014.html_DB7S0-0ea0eda4f36c456fb2912dcb6e4fa5a9)**

[9.1 Package](#part0014.html_h1)

[9.2 The import Statement](#part0014.html_h2)

[9.3 Access Modifier](#part0014.html_h3)

[9.4 Interfaces](#part0014.html_h4)

[9.4.1 Defining Interfaces](#part0014.html_h5)

[9.4.2 Implementing an Interface](#part0014.html_h6)

[*Try It Out*](#part0014.html_h7)

[*Exercise – 9*](#part0014.html_h8)

**[10\. Wrapper Classes](#part0015.html_E9OE0-0ea0eda4f36c456fb2912dcb6e4fa5a9)**

[10.1 The Number Class](#part0015.html_h1)

[10.1.1 Byte Class](#part0015.html_h2)

[10.1.2 Short Class](#part0015.html_h3)

[10.1.3 Integer Class](#part0015.html_h4)

[10.1.4 Long Class](#part0015.html_h5)

[10.1.5 Float Class](#part0015.html_h6)

[10.1.6 Double Class](#part0015.html_h7)

[10.2 The Character Class](#part0015.html_h8)

[10.3 The Boolean Class](#part0015.html_h9)

[*Exercise – 10*](#part0015.html_h10)

**[11. Exceptions](#part0016.html_F8900-0ea0eda4f36c456fb2912dcb6e4fa5a9)**

[11.1 Types of Exceptions](#part0016.html_h1)

[11.2 Catching Exceptions](#part0016.html_h2)

[11.2.1 Nested try Blocks](#part0016.html_h3)

[11.2.2 Hierarchy of Multiple Catch Blocks](#part0016.html_h4)

[11.3 Rethrowing Exceptions](#part0016.html_h5)

[11.4 Creating Your Own Exceptions](#part0016.html_h6)

[11.5 Broadcasting that a Method Throws Exception](#part0016.html_h7)

[11.6 The finally Block](#part0016.html_h8)

[11.7 Checked and Unchecked Exceptions](#part0016.html_h9)

[*Exercise – 11*](#part0016.html_h10)

**[12\. Input and Output Classes 216](#part0017.html_G6PI0-0ea0eda4f36c456fb2912dcb6e4fa5a9)**

[12.1 I/O Streams](#part0017.html_h1)

[12.2 The File Class](#part0017.html_h2)

[12.3 Byte Stream](#part0017.html_h3)

[12.3.1 InputStream](#part0017.html_h4)

[12.3.2 OutputStream](#part0017.html_h5)

[12.4 Disk File Handling](#part0017.html_h6)

[12.4.1 FileInputStream](#part0017.html_h7)

[12.4.2 FileOutputStream](#part0017.html_h8)

[12.5 Filtered Byte Streams](#part0017.html_h9)

[12.5.1 DataOutputStream](#part0017.html_h10)

[12.5.2 DataInputStream](#part0017.html_h11)

[*Try It Out*](#part0017.html_h12)

[*Exercise – 12*](#part0017.html_h13)

**[13. Strings](#part0018.html_H5A40-0ea0eda4f36c456fb2912dcb6e4fa5a9)**

[13.1 The String Class](#part0018.html_h1)

[13.1.1 Equality Operator and equals Method](#part0018.html_h2)

[13.1.2 String Concatenation with +](#part0018.html_h3)

[13.2 The StringBuffer Class](#part0018.html_h4)

[13.3 The StringBuilder Class](#part0018.html_h5)

[*Try It Out*](#part0018.html_h6)

[*Exercise – 13*](#part0018.html_h7)

**[14. Threads](#part0019.html_I3QM0-0ea0eda4f36c456fb2912dcb6e4fa5a9)**

[14.1 Multitasking](#part0019.html_h1)

[14.2 Creating a Thread](#part0019.html_h2)

[14.3 States of a Thread](#part0019.html_h3)

[14.4 Multithreaded Programming](#part0019.html_h4)

[14.5 Thread Priorities](#part0019.html_h5)

[14.6 Waiting for a Thread – join() Method](#part0019.html_h6)

[14.7 Controlling the Threads](#part0019.html_h7)

[*Try It Out*](#part0019.html_h8)

[*Exercise – 14*](#part0019.html_h9)

**[15. Applets](#part0020.html_J2B80-0ea0eda4f36c456fb2912dcb6e4fa5a9)**

[15.1 Applet Basics](#part0020.html_h1)

[15.2 Applet LifeCycle Methods](#part0020.html_h2)

[15.3 Some General Methods of Applet](#part0020.html_h3)

[15.4 Displaying Text in Status Bar](#part0020.html_h4)

[15.5 Embedding Applet Information](#part0020.html_h5)

[15.6 The HTML Applet Tag](#part0020.html_h6)

[15.7 Reading Parameters into Applets](#part0020.html_h7)

[*Try It Out*](#part0020.html_h8)

[*Exercise – 15*](#part0020.html_h9)

**[16. Graphics](#part0021.html_K0RQ0-0ea0eda4f36c456fb2912dcb6e4fa5a9)**

[16.1 Drawing Lines](#part0021.html_h1)

[16.2 Drawing Rectangles](#part0021.html_h2)

[16.3 Drawing Ovals and Circles](#part0021.html_h3)

[16.4 Drawing Arcs](#part0021.html_h4)

[16.5 Drawing Polygons](#part0021.html_h5)

[16.6 Drawing Polyline](#part0021.html_h6)

[*Try It Out*](#part0021.html_h7)

[*Exercise – 16*](#part0021.html_h8)

*[Reference Books](#part0022.html_KVCC0-0ea0eda4f36c456fb2912dcb6e4fa5a9)*

*[Answers to Questions](#part0023.html_LTSU0-0ea0eda4f36c456fb2912dcb6e4fa5a9)*

*[Appendix A](#part0024.html_MSDG0-0ea0eda4f36c456fb2912dcb6e4fa5a9)*

1IntroductionIn this chapter, the basic concepts of object-oriented programming (OOP), features of Java language and Java language architecture are explained.

1.1 OBJECT-ORIENTED PROGRAMMING CONCEPTS

The object-oriented technique is based on three basic concepts. They are:

*   Encapsulation
*   Inheritance
*   Polymorphism

1.1.1 Encapsulation

Many computer languages which came earlier, like FORTRAN, BASIC, Pascal, C, etc., handled data in an ‘open’ manner. Every component (like subroutines, functions) in the program written in those languages can access data defined for the whole program. This feature, though advantageous in many occasions, has some disadvantages in few cases. When a data is declared for all components of a program, any component in that program can alter the data. But, in most real life problems a data is to be protected from modification by all excepting by the specified components.

Not only data, but also the procedures that manipulate the data are to be guarded against misuse by other components of a program. Each procedure or method defined for a specific task is allowed to be accessed only by a particular component or by all other components of a program in varying degrees. This mechanism of providing protection to data and methods of a program is called encapsulation.

In Java language, encapsulation is realized through a description concept called class. A Java class contains variables representing data and methods that manipulate the data. The methods describe the way in which the data is manipulated. The variables and methods of a class are called members of the class. The members of a class can be declared as private or public.

A class itself cannot be used as such. Realistic entities, called objects, are to be created as per the description of the class, like buildings are constructed using blueprint. One or more objects constitute a Java program.

Public data and methods can be accessed by other objects of a program. The private data and methods can be accessed only within the same object. This mechanism provides protection to private members. The only way to access a private member by an external object is through the public method, which is well defined (by the user). Thus public methods encapsulate the data and methods of one object and act as an interface to other objects. The public method provides a channel for communication with external objects.

1.1.2 **Inheritance**

A class is developed for doing a particular task. There may be another task, which needs all functionalities of the previous class and a few additional capabilities. In such a case, generally, a new class is developed. Just for a few additional functionalities, one spends time on writing a new class, in which most of the functionalities of the previous class is repeated. Inheritance is used to avoid this repetition. The properties of a class prepared for doing a task can be inherited into another class and only the additional capabilities required are to be added in that to perform the new task. For example, if there is a class which finds the area of a rectangular surface, then this functionality can be inherited into another class to calculate the volume of a rectangular box. The new class, calculating the volume, need not repeat the procedure for calculating the area. This new class needs to have only the procedure to multiply area and height to find the volume. This inheritance property helps to build reusable codes to describe complex problems.

1.1.3 **Polymorphism**

Polymorphism refers to the behavior of the same entity behaving differently at different situations. For example, you feel happy when you receive a good news, feel sad on seeing that you failed in an examination, feel angry when someone teases you and so on. In all the situations, there is only one person, you, but behaving differently.

In Java, several methods having the same name can be defined in a class, which can perform different tasks depending on the context. Polymorphism in Java is realized through overloading methods and overriding methods.

***OOP language***

Any computer language that implements OOP concepts are known as OOP language. Java implements the OOP concepts and hence it is an OOP language.

1.2 **FEATURES OF JAVA LANGUAGE**

Java language has some special features, using which programmers can write fast, complex, safe and robust programs. Some of such important features are:

***Safe***

Java does not provide any pointers like in C or C++. Hence, the memory locations of a system cannot be accessed through a Java program. Therefore, any program developed in Java cannot be used to hack a system.

***Robust***

Errors that occur at runtime can be handled easily in Java. Java provides exception handling feature to overcome many runtime problems, like divide by zero, array index out of range, file not found, etc. Using this feature, a user can properly exit or come out smoothly without the program hanging. Therefore programs written using Java language are robust.

***Multithreaded***

Java language provides an environment by which several tasks can be initiated and managed easily. Such a feature is called multithreading.

***Architecture neutral***

A program written and compiled in one platform can run on any other platform. Therefore Java programs are architecture neutral or platform independent.

***Internet ready***

Java has the capability to handle TCP/IP packets. Hence Java can be used for internet application. It has several classes for internet programming which can be used for client/server programming.

***Simple***

Many authors of Java have stated that Java language is simple to learn. But, Java is not that simple to learn. It is because the capabilities of Java tools are high and one needs to put an effort to understand the Java programming concepts and use them.

1.3 **TYPES OF JAVA PROGRAMS**

Using Java language, two types of programs can be written. They are:

***Application program***

Java can be used for writing programs that run in a PC under the control of the operating system in that machine. Such programs are termed as application programs.

***Applet***

Programs can be written and compiled to give what is called bytecodes. These bytecodes can be downloaded mostly from a remote server and executed by web browsers without any control from the local operating system. Such programs are called applets.

1.4 **JAVA ARCHITECTURE**

Java programming environment is based on the following four technologies:

*   Java programming language
*   Java class files
*   Java Application Programming Interface (API)
*   Java Virtual Machine (JVM)

The Java source program is created using the features of Java language. The source program is then compiled using the Java compiler, javac, supplied in Java Development Kit (JDK). After compilation, Java class files are created. These class files contain bytecodes. The Java Virtual Machine executes Java class files and Java API class files as required for Java class files. The API class files have Java native methods that interact with the local operating system. The JVM is a virtual computer developed in software. The combination of JVM and API is called Java platform (see Fig. 1.1).

![](images/00009.jpeg)

**Fig. 1.1** Java Architecture

The Java platform is different for different machines. Java platform for Unix, Windows, Macintosh, etc. are different from one another. It is this architecture that makes a Java program to write once, compile once and run in any platform. For a Java program developer, it appears that the program he/ she developed can run in any type of platform. The variation in the hardware environment is taken care by different JVMs for different machines, leaving the class files compatible to all types of machines. Hence, a Java program becomes platform independent (see Fig. 1.2).

![](images/00010.jpeg)

Fig. 1.2 Platform-Independent Java program

Since the birth of Java in 1993, the Java developers have released several versions specified along with the JDK, as JDK1.1, JDK1.2, etc. The Java language from JDK1.2 is named as Java2\. Further versions are mentioned only in the JDK. Java also evolved into three major technologies that helps to develop scalable applications and in different devices. The three technologies are:

Java2 Standard Edition - J2SE (Core Java)

Java2 Micro Edition - J2ME (for hand held devices)

Java2 Enterprise Edition - J2EE (for scalable applications)

In this book you will learn J2SE (also called Core Java) with JDK1.7

After reading this chapter, you should have learned the following concepts:

*   Object-oriented programming is based on three concepts: encapsulation, inheritance and polymorphism.
*   Objects constitute a Java program.
*   Java language is safe, robust, internet ready and architecture neutral.
*   Java supports two types of programs: applet and application.
*   Java Virtual Machine (JVM) is an abstract computer built using software.

In the next chapter, you will learn about Java literals, data types and variables.

**EXERCISE–1**

**Fill in the blanks**

1.1 The basic principles which form the object-oriented programming are .........................., .......................... and .......................... .

1.2 The mechanism of providing required protection to the variable and methods in a class is known as .......................... .

1.3 The concept of encapsulation is described in the .......................... .

1.4 Java objects are instances of Java ........................... .

1.5 The absence of pointers in Java helps to write .......................... programs that do not hack the system.

1.6 A Java program can be run in any computer running under any operating system. (True/ False)

1.7 An application program is run in a computer under the control of the ..........................in that computer.

1.8 .......................... program runs without the control of the ........................... .

1.9 Java Virtual Machine and .......................... form the Java platform.

1.10When a Java program is compiled, it gives .......................... files. When a Java program is compiled, it gives .......................... files.

1.11Java programs are platform .......................... .

1.12Java Virtual Machine is a virtual computer built using ........................... .

2Literals, Data Types and VariablesIn this chapter, Java constants called literals, data types and variables are explained.

2.1 LITERALS

Entities that do not change their values in a program are called constants or literals. While solving real-life problems, one comes across different types of literals. Java provides different literal representations for them.

2.1.1 Integer Literals

A whole number is called as an integer. For example, 25, 75, 399, etc. are integers. Java supports three types of integer literals: decimal, octal and hexadecimal. The above integer numbers are examples of decimal integer literals. Octal integer literals start with 0 (zero) and are followed by octal digits 0 to 7\. For example, 0, 037, 02374 are octal integer literals. Hexadecimal integer literals start with 0x (or 0X) and are followed by hexadecimal digits 0 to 9, A to F (a to f). For example, 0X29, 0X3A7, 0X2AB9 are hexadecimal integer literals. Java also provides integers of large magnitude called long integers. To denote such long integers, the letter L (or l) is appended to the literals. For example 732999456789425L and 0777765237423742517432567L represent long decimal integer literal and long octal integer literal respectively.

2.1.2 Floating Point Literals

Numbers with decimal point and fractional values are called floating point literals. These literals are represented in two forms, standard and scientific. In standard notation, integer part and fractional part are separated by a decimal point. For example, 75.23749 is in standard notation. In scientific notation, a floating point number is followed by the letter E (or e) and a signed integer. The representations 6.237E–35, 4.792E18 and 42e+138 are in scientific notation standing for 6.237x10^(–35), 4.792 x 10^(18) and 42x10^(138) respectively.

The accuracy of numbers used in a program depends on the storage capacity inside the computer to store that number. Two standard precisions are used in Java, **float** and **double**. ‘float’ is called single precision and ‘double’ is a double precision. By default, all floating point literals are stored in double precision. In order to specify the precision, floating point literals can be appended with f (or F) for float and d (or D) for **double**. For example, 2.342f denotes that the number be stored in single-precision float and 7.2345678902d or 7.234568902D denotes that the number be stored in double-precision **double**. By default all numbers with decimal point are taken as **double**.

2.1.3 Character Literals

Single characters in Java are called character literals. In Java, characters belong to 16-bit character set called Unicode. Java character literals are written within a pair of single quote. For example ‘a’, ‘z’ represent character literals. There are certain characters that cannot be printed. Further, in certain occasions, a character like single quote (‘) itself is to be written as character literal. To represent such characters, Java provides a set of character literals called escape sequence. Table 2.1 gives the escape sequence.

**Table 2.1** The escape sequence characters

| *Escape Sequence* | *Descripti on* |
| \ddd \uxxxx
\'
\"
\\
\r
\n
\f
\t
\b | Octal character represented in ddd Hexadecimal Unicode character
Single quote
Double quote
Backslash
Carriage return
New line
Form feed
Tab
Backspace |

2.1.4 String Literals

A sequence of characters written within a pair of double quote is called string literal.

For example:

"This is a String"

"You can put anything here"

"1234 * special characters"

"next \n line"

"\" within double quote\""

are all string literals. Notice that the escape sequence characters are written as such. String literals are to be started and ended in one line only.

2.1.5 Boolean Literals

In Java, boolean literals take two values, **true** or **false**. These two values are not related to any numeric value as in C or C++. The Boolean value **true** is not equivalent to 1 and **false** is not equivalent to 0.

2.2 DATA TYPES

While solving real-life problems, one comes across a variety of data types. Therefore, any computer language should be able to handle such data types. Java supports eight basic types. The eight basic types fall under the following four groups:

***Integers***

Integers are whole valued signed numbers. There are four types in this. They are **byte, short, int** and **long.**

***Floating point numbers***

Real numbers, with fractional values and with decimal point, are covered under this category. They are covered under two types, **float** and **double**.

*Characters*

Single characters are represented through **char** type.

*Boolean*

Boolean logical values are handled by **boolean** type.

2.2.1 Integer Types

Integers in Java are handled in four basic types: **byte, short, int** and **long**. All types are signed and take positive and negative values. The width of each type is defined by Java language and do not depend on the machine in which the program is executed. The width of each type is prefixed and is platform independent. This is one of the important aspects of Java language in handling integer numbers.

***byte***

**byte** is the lowest size integer. **byte** is signed and is 8-bit width. Its values range from –128 to 127\. **byte** variables are declared by the keyword **byte**.

Example: byte a, buff;

***short***

**short** type is 16-bit width and is signed. It takes the value from –32,768 to 32,767\. The **short** type integers are declared by the keyword **short**.

Example: short sn, num;

***int***

The **int** type is a signed integer of 32-bit width. It takes up the value from –2147483648 to 2147483647\. It is the most commonly used type in Java programs. The **int** type integers are declared by the keyword **int**.

Example: int n, numb;

***Long***

The **long** type is a signed integer of 64-bit width. It takes values from –9223372036854775808 to 9223372036854775807\. The **long** type integers are declared by the key word **long**.

Example: long factorial, star_count;

![](images/00011.jpeg)The range of integer values for each integer type is defined by Java language and does not depend on the computer on which the numbers are generated.

2.2.2 Floating Point Types

Numbers with fractional values are called floating point numbers and are known as real numbers in older languages like FORTRAN. The floating point numbers are represented in two forms, **float** and **double**.

***float***

In **float** type, the numbers are specified in 32-bit width. It takes value from 3.43e–038 to 3.43e+038\. This is a single precision representation. Single-precision numbers are processed efficiently. The **float** type variables are declared by the keyword **float**.

Example: float x, area;

By default, all floating point numbers are treated as **double**. Hence, explicit specification is required when initializing **float** variables. To represent a float, the number is to be appended with f.

Example: float x = 85.25f;

***double***

The **double** type floating point numbers are represented in 64-bit width. This is a double-precision representation. It takes value from 1.7e–308 to 1.7e+308\. By default, all floating point numbers assume this form. It is the most commonly used form. The **double** type variables are declared by the keyword **double**.

Example: double volume, average;

2.2.3 Character Type

Single characters are handled by **char** type. It is a 16-bit code. Therefore, it can represent 65,536 distinct characters. In Java, this 16-bit representation of characters is called **Unicode**. It covers a large set of language characters in the world. For example, characters of English, Gujarati, Telugu, Tamil and Hindi languages are defined in the Unicode character set in addition to several other languages. The **char** type variables are declared by the key word **char**.

Example: char choice, flag;

The **char** type is associated with ASCII value, which is a subset of unicode value. Therefore, **char** type can also be associated with int values. For example, character 'A' is represented by the value 65.

![](images/00011.jpeg)Characters defined in Java are 16-bit width and are called Unicode characters.

2.2.4 Boolean Type

The logical values **true** and **false** are handled by **boolean** type. The boolean values **true** and **false** are not associated with any numerical value. (In C or C++, zero is treated as false and non-zero value as true). The **boolean** type variables are declared by the keyword **boolean**.

Example: boolean flag, full, empty;

2.3 VARIABLES

Variables, as the name indicates, take different values during the execution of the program. Few authors term variables as an identifier. A variable is any combination of letter, number, underscore and $ sign. The variable must not begin with numbers. A letter may be any Unicode character defined for a language. There is no maximum limit on the total number of characters that form the variable. Java's reserved keywords should not be used as variable.

**A Few Valid Java Variables Are:**

| sum | total_val | area | fact_num |
| _max | $value | Total |  |

**A Few Invalid Java Variables Are:**

| 2nd_class | min-val | length&breadth |
| avg val | total/ | float |
| double |  |  |

float and double are Java-reserved words and hence invalid.

Table 2.2 gives a list of reserved keywords.

**Table 2.2**Java reserved keywords

![](images/00012.jpeg)

Java variables are case-sensitive, i.e., uppercase letters are different from those of lowercase. Therefore, the variables, sum and Sum, are different. All Java variables required for the program must be declared before it is used and it can be placed anywhere in the block where they are used.

***Declaring a variable***

A variable is declared along with the type it is going to store. An initial value can also be assigned along with the declaration. The general form of declaring a variable is :

type variable [=value], variable [=value];

Example:

int x, y, z;
int a, b = 45, c;
float p, q = 7.253f;
char c, choice = 'y';

***Scope of Variables***

The scope refers to the validity of a variable across a Java program. The scope of a variable is limited to the block defined within the braces { and }. It means a variable cannot be accessed outside the scope.

***A sample program***

Program 2.1 shows how various types are declared.

Program 2.1![](images/00013.jpeg)

/* ka.somasundaram@gmail.com

* This program requires jdk1.6 or higher */

import java.io.Console;

class Literal {

public static void main(String args[]) {

Console con = System.console();

int n = 967;

int oint = 0567;//octal integer

float x = 45.67f;

double y = 78.95;

char ch = 'z';

boolean result = true;

String myname = "K.Somasundaram";

con.printf(" n=%d \n oint=%o \n oint (in decimal)=%d\n", n, oint, oint);

con.printf(" x=%6.2f \n y=%6.2f\n", x, y);

con.printf(" myname=%s \n ch=%c\n", myname, ch);

con.printf(" result=%b \n", result);

}

}

The output of program 2.1 is shown in Fig. 2.1.

![](images/00014.jpeg)

**Fig. 2.1** Output screen for program 2.1

![](images/00011.jpeg)The scope of variables is restricted to the block in which it is defined.

After reading this chapter, you should have learned the following concepts:

*   Constants defined in Java are called literals.
*   Characters in Java are called Unicode characters.
*   Java defines eight basic types:
    byte, short, char, int, long, float, double and boolean
*   The range of integer values for each integer type is defined by Java language and does not depend on the computer in which the numbers are generated.

In the next chapter, you will learn the structure and syntax of a Java program.

EXERCISE–2

**I. Fill in the blanks**

2.1 Constants are called as ..........................in Java language.

2.2 A hexadecimal literal starts with ..........................

2.3 035 is a/an ..........................integer.

2.4 In Java language the precision of a number ..........................on the machine in which the program is executed.

2.5 There are ..........................basic types in Java.

2.6 ..........................type in Java is called Unicode character.

2.7 The scope of a variable is restricted to ..........................in which they are declared.

2.8 In the following list ..........................are invalid Java variables:

Sum

_Max

$value

1class

Mat-value

float

2.9 For engineering and scientific calculations ..........................and ..........................type will be more useful.

2.10Non-printable characters are represented by ..........................characters.

2.11The value 75.25 as such is to be assigned to a ..........................type variable.

3The Structure of a Java ProgramIn this chapter the structure of a Java program and its various segments are explained. Statements in a Java program and how conversion of one type to another are given. How to compile and execute a Java program is explained. Example programs are given to illustrate the conversion and recent developments in Java for outputting values.

3.1 STRUCTURE OF A JAVA PROGRAM

In this chapter, the structure of a Java program is given. How statements are to be made, how to terminate a statement, the convention to be followed in naming a Java class file, how to compile and execute a Java program are explained. The following Java program 3.1 declares an integer variable and prints it out:

Program 3.1![](images/00013.jpeg)

/*This is a simple Java program illustrating its structure ka.somasundaram@gmail.com

*/

class JavaProg {

public static void main(String args[]) {

int a = 25;

// Classical method to print

System.out.println(“Welcome to Java Programming”);

System.out.println(“a = “ + a);

//New method to print since JDK1.5

System.out.printf(“Welcome to Java Programming%n”);

System.out.printf(“a = %d%n”, a);

}

}

When you type this program and create a file in the computer, the name of the file and the class name, JavaProg, should be the same. To be specific, the file name containing this program must be named as JavaProg.java. The word class is a Java reserved keyword and must be used as such. Class is the building block for a Java program. The word JavaProg is a user-defined name. One can coin words using the rules for variables. By convention, all class names will begin with uppercase and will be followed by a letter in lowercase. When more words are needed to name the class, the first letter of each word is written in uppercase and the other letters are in lowercase. But this is not a rule. Java is case-sensitive and, therefore, all the words must be typed in exactly the same way as they appear.

To compile and execute the above program, you need to have jdk1.5 (Java Development Kit, version 1.5 or higher). Install it in a directory. Go to the subdirectory bin. To compile your JavaProg. java program, issue the following command in DOS:

javac JavaProg.java

If your program code is free of typographical errors, your program will be compiled. To execute the compiled program, issue the following command:

java JavaProg

Compiling a Java program can also be done in another way. Create your Java program in any of your working directory. Then set a directory path pointing to the Java compiler javac.exe contained in bin directory. Suppose if the bin directory is d:\java1.6\bin then set the path and compile as given below:

d>set path=d:\java1.6\bin
d>javac JavaProg.java

Execute the program by issuing the following command:

d>java JavaProg

On execution of the program, you will get the result on your monitor as shown in Fig. 3.1.

![](images/00015.jpeg)

**Fig. 3.1** Output screen for program 3.1

Coming back to the structure of the program, the body of the class JavaProg is enclosed between the opening brace({) and closing brace(}). Next, the word **main** states that it is a method (called as procedure or function in other languages) called main. All application programs must contain a **main** method. The **main** method is executed first. A list of string type can be passed into the program through args[] in command line. The word **void** is a reserved word and informs that the **main** method will not return anything. The word **public** is an access specifier and **static** specifies the storage type. Both are reserved key words of Java. The body of the method, must also be placed within { and }. For every {, there should be a corresponding }. Every Java statement is to be terminated with a semi colon (;). The statement System.out.println is used to print the string literal. The second such statement is used to print out a string literal and the value of the **int** type variable a. The **System** refers to a Java class defined in **java.lang** package. The **out** parameter is a static object variable of the type PrintStream. Generally, out refers to a standard output display monitor. The word **println()** refers to a method defined in **PrintStream** class. It prints the parameters passed as arguments on the standard output stream, the monitor. The **println()** is a classical method came with **JDK1.0.** This **println()** method could not produce formatted output. To get formatted output, a new method printf() which functions exactly similar to C language **printf()** function was introduced since JDK1.5\. Using this method one can write output statements like **System.out.printf()**. Another form of program 3.1 using **System.out** as object is given in program 3.2.

Program 3.2![](images/00013.jpeg)

/*This program illustrates the use of printf() method.

ka.somasundaram@gmail.com

This program requires jdk1.5 or higher

*/

import java.io.PrintStream;

class Javaso {

public static void main(String args[]) {

PrintStream so = System.out;

int a = 25;

//Using println()method

so.println(“Welcome to Java Programming”);

so.println(“a “ + a);

//Using printf()method for formated output

so.printf(“Welcome to Java Programming%n”);

so.printf(“a = %d%n”, a);

}

}

The output of the program 3.2 is shown in Fig. 3.2.

In program 3.2, the %n in the **printf**() method specifies that a new line is to be introduced at that point. It is similar to \n. The %d specifies the variable *a* is to be printed as decimal integer. The letters after % symbol, n and d are called as conversion characters. A list of conversion characters are given in Appendix A.

**Fig. 3.2** Output screen for program 3.2

![](images/00016.jpeg)

To handle input/output Java has a collection of classes in **java.io** package. One of the class is **PrintStream** which has the **printf()** method. In order to access the **PrintStream** class and its methods in program 3.2, the **java.io** package is to be imported. This is done by the statement import **java. io.PrintStream**. In program 3.1 no import statement is used, because, java compiler automatically imports the **java.lang** package which contains the class **System**.

Though JDK1.5 introduced **printf()** method, yet another versatile class **Console** was introduced since JDK1.6\. This **Console** class can handle both standard output, the monitor and the standard input - the keyboard. Getting an input from keyboard using I/O classes in Java is bit cumbersome when compared to languages like C. The **Console** class has methods for both input and output data. For this reason, in this book **Console** class is used for simple input and output. An instance of the Console class is obtained by calling the **System.console()** method. This **Console** class also contains **printf()** method. The following program 3.3 shows the use of **Console** class with formatted output.

Program 3.3![](images/00013.jpeg)/* This program illustrates the use of Console classka.somasundaram@gmail.comThis program requires jdk1.6 or higher*/import java.io.Console;class Javacon {public static void main(String args[]) {// Get Console object to send outputConsole con = System.console();int a = 25;//Use printf methodcon.printf(“Welcome to Java Programming%n”);con.printf(“a = %d%n”, a);}}

Output of program 3.3 is shown in Fig. 3.3.

![](images/00017.jpeg)

**Fig. 3.3** Output screen for program 3.3

3.2 COMMENTS

Comments can be inserted into a Java program in three different forms. In the first form, comments can be written in a single line by placing // at any location of a statement. All statements made after // and till the end of the line will be treated as comment.

Example:

(i) // This is a first Java program

(ii) a = p * Q ; // making a multiplication

(iii) int x, y ; //declaring two int types.

In the second form, comments running into multiple lines can be made. In this form, comments start with /* and end with */. The beginning /* and ending */ can be in the same or different lines.

Example:

(i) /*_____________________________________________
This program is developed to fi nd a prime number
————————————————————————*/

(ii) /*
This is an example for multi line comment
*/

The third form of comment is meant for generating an HTML file that documents your program. This form of comments starts with /** and ends with */.

3.3 EXPRESSIONS AND STATEMENTS

Java expressions, like in any other language, consist of variables and literals separated by operators. A Java expression will be of the form:

![](images/00018.jpeg)

An example for an expression is:

40 * m + total / numb - 25

The operands in the expression may be the same or of different type. If the operands are of the same type, the resulting value of the expression is also the same type. Suppose, if all variables and literals are **int** type, the resulting value is **int** type.

When a Java expression is assigned to a variable, it becomes a statement. The general form of a statement is:

Variable = expression ;

3.4 TYPE CONVERSION

It is important to know beforehand what type an expression will give when it is evaluated. It is necessary because an expression may contain different types. Java has mechanisms to handle different types present in an expression during evaluation or while assignment. Type conversions of primitive types occur while evaluating an expression or during assignment. Java does the conversion through two mechanisms, automatic promotion and type casting.

Automatic Promotion

Java automatically converts variables or literals of lower precision type to a higher precision type during the evaluation of expression or during assignment. This is known as automatic promotion or widening. When unary operators like –,+,– –,++ etc. operate on an operand of type byte or short, the operand will be converted to int type, otherwise the operands are left as such. When binary operations take place, the type of the operands are checked. If one of the operands is double, the other will be converted to double. If one of the operands is float, the other will be converted to float and if one of the operands is long, the other operand will be converted to long, otherwise the two operands will be converted to int (if the operands are of type byte or short).

Example:

(i)  byte b1 = 35;
byte b2 = –b1;

The second statement will give compile error because b1 is automatically promoted to int.

(ii) byte b1 = 25;
byte b2 = 14;
byte b3 = b1+b2;

The third statement will give compile error as both b1 and b2 will be promoted to int before the binary operator + is operated. Hence, the addition will give an int result, whereas the left hand side b3 is a byte.

(iii) byte b1 = 25;
 byte b2 = 14;
 int n = b1+b2;

The third statement is valid and correct.

Java also does automatic conversion while assigning values to variables in a statement:

destination = source;

where the source may be an expression or variable or even a literal. In such assignments, if precision of the destination is larger than the source, Java automatically converts the lower precision value (say int) to higher precision value (say long). Table 3.1 shows the source type and destination type.

**Table 3.1** Valid type conversion

| *Source Type* | *Destination Type* |
| byte short
char
int
long
float | short, int, long, float, double int, long, float, double
int, long, float, double
long, float, double
float, double
double |

Fig. 3.4 shows the widening type conversion.

![](images/00019.jpeg)

**Fig. 3.4** Widening type conversion

Widening can take left to right as indicated in the arrow mark in Fig. 3.4 in consecutive stages or hop one or more stages in between. For example, **byte** can directly be converted to **long** type.

![](images/00011.jpeg)byte and short type are automatically converted to int in an expression. Hence, the destination type should be declared according to this conversion.

Program 3.4 shows few of the automatic promotion or widening for expressions with different types.

Program 3.4![](images/00013.jpeg)

/* This program illustrates automatic promotion

ka.somasundaram@gmail.com

This program requires jdk1.6 or higher

*/

import java.io.Console;

class Autopromo {

public static void main(String args[]) {

Console con = System.console();

int n = 25;

float fx, fy = 45.79f;

double dx, dy = 76.25;

long lp, lm = 5678;

con.printf(“\nThe following results illustrate the

automatic promotion\n\n”);

//Automatic promotion of int to float

fx = n + fy;

con.printf(“float <-- int + float:

%6.2f <-- %d + %6.2f\n”, fx, n, fy);

//Automatic promotion of int to double

dx = n + dy;

con.printf(“double <-- int + double:

%6.2f <-- %d + %6.2f\n”, dx, n, dy);

//Automatic promotion of long to float

fx = lm + fy;

con.printf(“float <-- long + float:

%6.2f <-- %d + %6.2f\n”, fx, lm, fy);

//Automatic promotion of int to long

lp = lm + n;

con.printf(“long <-- long + int:

%4d <-- %d + %d\n”, lp, lm, n);

}

}

The output for program 3.4 is shown in Fig. 3.5.

![](images/00020.jpeg)

**Fig. 3.5** Output screen for program 3.4

Type Casting

There are situations where incompatible type conversion is needed, where a higher precision type is being assigned to or converted to a lower precision. For example, it may be needed to get an **int** type from a **double** type or a **byte** from a **float**. This process is known as narrowing or down casting. The narrowing process will result in loss of bit and the value obtained may be incorrect. Therefore, a programmer must know the consequence of narrowing before effecting it. The type conversion is to be done explicitly by using the keyword **type**. The general form of type casting is:

type variable = (type) expression;

![](images/00011.jpeg)Whenever incompatible type conversion is needed, type casting is used.

3.5 BLOCK STATEMENTS AND SCOPE

Statements written in single lines are simple statements. There are occasions, where a group of statements are to be treated as one unit. In such situations, several simple statements are enclosed between a pair of braces { and } and is called block statement. Blocks define the scope of variables. As we have seen earlier, the scope of a variable is restricted to the block in which it is declared. Blocks can be nested. The following program 3.5 illustrates the use of nested block statement:

Program 3.5![](images/00013.jpeg)

/* This program illustrates block statement

ka.somasundaram@gmail.com

This program requires jdk1.6 or higher

*/

import java.io.Console;

class BlockDemo {

public static void main(String args[]) {

Console con = System.console();

int num = 24;

double y;

{

int i = 45, k;

k = num + i;

con.printf(“ k = %d\n”, k);

}

y = num / 3.1;

System.out.println(“ y = “+y);

con.printf(“ y = %5.2f\n”, y);

}

}

Output of program 3.5 is shown in Fig. 3.6.

![](images/00021.jpeg)

**Fig. 3.6** Output screen for program 3.5\. Notice the value of y printed using println() method.

The variables i and k are declared inside the inner block. Hence, their scope is valid only in that block. Outside the block, i and k cannot be accessed. The variables num and y are declared in the outer block and, therefore, can be accessed in both blocks. Consider the following program 3.6:

Program 3.6![](images/00013.jpeg)

/* This program illustrates the scope of variables

in nested blocks

ka.somasundaram@gmail.com

This program requires jdk1.6 or higher

*/

import java.io.Console;

class Scope {

public static void main(String args[]) {//main block

Console con=System.console();

int num = 25;

double y;

{ // second bock

int i = 45;

int k;

k = num + i; // num can be accessed here

System.out.println(" K = " + k);

} // second block ends

// k is outside its scope. Hence compile error

// will occur

y = k / 3.1;

con.printf(" Y = %5.2f\n" , y);

} // main block ends

}

The statement y=k/3.1 in program 3.6 attempts to access k outside its scope and hence will produce compile error.

Though Java restricts the scope of a variable to the corresponding block, variables with identical name can not be declared in two blocks. For this reason, the following statements will give compile error:

{ int i ;

.

.

.

{ int i ; // i is defined already

// will give error

.

.

.

}

}

The following program 3.7 illustrates the concepts discussed in this chapter:

Program 3.7![](images/00013.jpeg)

/* This program illustrates the following concepts

-statement block

-type casting

ka.somasundaram@gmail.com

This program requires jdk1.6 or higher

*/

import java.io.Console;

class Typecast {

public static void main(String args[]) {

Console con = System.console();

int n = 2785, i = 15, ix;

double x = 76.89, y, z, mix;

byte bn;

{

int m = 25, k;

k = m + i; // i can be accessed here also

con.printf(" k = %d%n", k);

} // scope of k and m ends

y = n / 26.85;

// z = k/2.5; // do not try this statement

bn = (byte) n; // converting int to byte

ix = (int) x; // converting double to int

con.printf(" y = %6.2f%n", y);

con.printf(" n = %d byte n =%d%n", n, bn);

con.printf(" x = %5.2f int x = %d%n", x,ix);

}

}

Output of the above program 3.7 is shown in Fig. 3.7.

![](images/00022.jpeg)

**Fig. 3.7** Output screen for program 3.7

After reading this chapter, you should have learned the following concepts:

*   The structure of a Java program.
*   Making comments in a Java program.
*   Scope of variables.
*   Automatic promotion of byte and short to int.
*   Type casting.
*   The conventional System.out.println() method can be replaced by System.out.printf() method to produce formatted output.
*   Formatted output can also be obtained using printf() method in Console class.
*   The values can be formatted using conversion characters like c, d, e, f, g, s, n.

In the next chapter, you will learn about the various operators defined in Java language.

EXERCISE-3

**I. Fill in the blanks**

3.1 A class is defined within a pair .......................... .

3.2 Each statement in a Java program is terminated with ........................... .

3.3 A Java program must contain a .......................... method.

3.4 Comments in Java program can be made in .......................... ways.

3.5 Java automatically converts byte and short to .......................... .

3.6 When incompatible type conversion is needed .......................... is used.

3.7 A set of statements enclosed between { and } is called .......................... statement.

3.8 The scope and life of a variable is restricted to the .......................... in which they are declared.

3.9 The file name of a Java program must be the same as that of the .......................... name.

3.10Variable names defined in different blocks can .......................... the same.

3.11An expression with operands of type byte and float will give a result of .......................... type.

3.12To get formatted output .......................... method is used.

3.13For formatting output values .......................... characters are used.

**II. Write Java programs for the following:**

3.14Write a program that prints your address.

3.15Write a program to find the average of three byte type numbers.

3.16Write a program to find the sum of five double type numbers.

4OperatorsIn this chapter, various operators used in Java language are explained.

Operators operate on operands and cause changes in the operand value or give a new value. Java provides operators in four categories. They are:

1\. Arithmetic operators

2\. Bitwise operators

3\. Relational operators

4\. Logical operators

Operators may operate on one, two or three operands. Operators operating on single operand are called unary operators, on two operands are binary operators and on three operands are ternary operators. Unary operators are further classified as prefix operator and postfix operator. When the operator precedes the operand, it is called prefix operator and when it follows, it is called postfix operator.

4.1 ARITHMETIC OPERATORS

Arithmetic operators operate on numeric type variables and numeric literals. The arithmetic operators and the character symbol that represent them are listed in Table 4.1.

**Table 4.1** Arithmetic operators

| *Operation* | *Operator Symbol* |
| Add | + |
| Subtract | – |
| Multiply | * |
| Divide | / |
| Modulus | % |

The first three operators carry the same meaning as we do in normal calculations. The division operator gives integer division if both operands are integer and floating point division, if one of the operands is a floating point.

Example:

18/4 gives 4
18/4.0 gives 4.5

Modulus Operator

The modulus operator % gives remainder value after a division. It works for both integer and floating point values.

Program 4.1 show the results for division (/) and modulus (%) operators.

Program 4.1![](images/00013.jpeg)

/* This program illustrates the use of

Arithmetic operators

ka.somasundaram@gmail.com

This program requires jdk1.6 or higher

*/

import java.io.Console;

class Arithopr{

public static void main(String args []){

Console con=System.console();

int m = 25, p = 70;

double x=25.0,y;

con.printf("int/int gives int : %d <--%d /

%d %n" , p/m,p,m);

con.printf("int/double gives double : %5.2f

<--%d / %4.2f %n" , p/x,p,x);

con.printf("%d %c 5 gives %d %n" ,m,'%',m%5);

con.printf("%d %c 7 gives %d %n",m,'%',m%7);

con.printf("%d %c-7 gives %d %n" ,m,'%',m%-);

con.printf("-%d %c 7 gives %d %n" ,m,'%',-);

con.printf("Java\'s %c Operator works even

for fractions!!%n%n", '%');

con.printf("25.8 %c 7 gives %4.2f %n" ,'%', 25.8%7);

con.printf("25.8 %c 7.0 gives %4.2f %n",

'%', 25.8%7.0);

con.printf("25.8 %c 7.5 gives %4.2f %n",

'%', 25.8%7.5);

}

}

Output of program 4.1 is shown in Fig. 4.1.

![](images/00023.jpeg)

**Fig. 4.1** Output screen for program 4.1

![](images/00011.jpeg)Modulus operator (%) works for both integer type and floating point values.

All the five arithmetic operators are binary operators, i.e. they need two operands. However, the subtract operator can also be used as unary prefix operator as given below:

y = –x;

The same is applicable for + operator and can be written as:

p = + q;

This form, though valid and correct, is not generally used, as the statement

p = q;

means the same.

Operator Assignment

All the five arithmetic operators can be used in operator assignment form. This helps to avoid repeating the operands in two places of a statement. Consider the statement:

sum = sum + 1;

This statement can also be written as:

sum + = 1;

This form of assigning value to the variable is called operator assignment. In general, a statement of the form:

variable = variable operator expression

is replaced by operator assignment form:

variable operator= expression;

For arithmetic operators, the following forms +=, – =, *=, /= and %= are applicable.

Increment and Decrement Operators

There are two more arithmetic operators ++ and – –. Both are unary operators and operate only on integers. The ++ increment operator increases the operand’s value by 1\. Both can operate in prefix form ++n or in postfix form n++, where n is a variable. In prefix form, the value of the operandn is incremented first and the operand is used. In postfix form, the value of the operand is used first and then incremented. The same is applicable to the decrement operator – –. Program 4.2 illustrates the use of increment and decrement operators.

![](images/00011.jpeg)The prefix operator (++variable or ––variable) changes (increment by one or decrement by one) the value of the variable first and uses the variable. When postfix operator (variable++ or variable––) is used, the value of the variable is used in the operation and then changes the value (increment by one or decrement by one).

Program 4.2![](images/00013.jpeg)

/* This program illustrates the use of increment and

decrement operators

ka.somasundaram@gmail.com

This program requires jdk1.6 or higher

*/

import java.io.Console;

class InrDcr

{

public static void main(String args []){

Console con=System.console();

int m = 25, p = 70;

con.printf("m = %d%n" , m);

con.printf("++m = %d%n" , ++m);

con.printf("p = %d%n" , p);

con.printf("p++ = %d%n" ,p++);

con.printf("p++ after use = %d%n" , p);

}

}

The output of the above program 4.2 is shown in Fig. 4.2.

![](images/00024.jpeg)

**Fig. 4.2** Output screen for program 4.2

The ++ and –– operators do not operate on integer literals. Therefore, 25++ or – – 85 are not valid.

![](images/00011.jpeg)The ++ and –– operators should not be operated on integer literals (like ++75).

4.2 BITWISE OPERATORS

Bitwise operators are used to manipulate individual bits of a data item. There are situations where individual bits of a data are to be modified. Java provides a set of bitwise operators. These operators operate only on **byte, char, short, int** and **long** types. The bitwise operators in Java are given in Table 4.2.

**Table 4.2** Bitwise operators

| *Operation* | *Operator Symbol* |
| Bitwise NOT | ~ |
| Bitwise AND | & |
| Bitwise OR | &#124; |
| Bitwise exclusive OR | ^ |
| Left  shift | << |
| Right shift | >> |
| Right shift  zero fill | >>> |

Bitwise NOT (~)

This is a unary operator. It complements each bit of the operand. Consider a number 71\. This number in byte type has a binary value of 01000111.

a = 01000111

The NOT operation gives:

~a = 10111000

= –96

Bitwise AND (&)

This AND operator, & , performs AND operation bit by bit of the operands. Consider two operands a = 71 and b = 25, represented in byte type as:

a = 01000111
b = 00011001

The AND operation gives:

a & b = 00000001

= 1

Bitwise OR (|)

This OR operator, |, performs OR operation bit by bit. Consider two bytes a = 71 and b = 25\. The OR operation gives:

a | b = 01011111

= 95

Bitwise Exclusive OR (^)

This XOR operator, ^, performs exclusive OR (XOR) bit by bit. In this operation, if the corresponding bits of the operands are identical, the resulting bit is 0, otherwise it is 1\. For the numbers a = 71 and b = 25, the XOR operation gives:

a ^ b = 01011110

= 94

Left Shift Operator (<<)

This operator, << , is a unary operator. It shifts each bit of the operand to the left by the specified number of positions. The general form of using this operator is:

variable << n

where n specifies the number of positions each bit in the variable is to be shifted left. The leftmost bit is shifted out and the rightmost bit is filled with zero.

Example:

a = 25

= 00011001

The left shift operation,

a << 2

specifies that each bit be shifted left by 2 positions. The result,

after 1st shift is 0 0 1 1 0 0 1 0

after 2nd shift is 0 1 1 0 0 1 0 0

a = 100

Thus, the final value of a is 100\. Each left shift is equivalent to multiplication by 2\. One has to remember that Java promotes automatically the **byte** and **short** type to **int** type before evaluating them. Hence, care must be taken to handle such situation. When bits in signed integers are shifted left, the leftmost bit indicating the sign will be retained always, i.e. a negative value after the shift will also be a negative number.

Example:

a = –25

= 10011001

The operation a << 2 will give

a = 11100100

= –100

Right Shift Operator (>>)

This operator >> shifts each bit of the operand to the right by a specified number of positions. The rightmost bit is shifted out and lost. The leftmost bit is sign extended. All other bits in between are shifted to right by one position. Each right shift is equivalent to divide by 2\. The general form of using this operator is:

variable >> n

where n specifies the number of positions the bits in the variable are to be shifted right.

Example:

a = 25

= 00011001

The operation a >> 2 gives

a = 00000110

= 6

For a signed number, the sign bit will be extended. The leftmost bit with 1 indicates that the number is negative.

Example:

b = –25

= 10011001

The operation b >> 2 gives

b = 11100110

Notice that the leftmost sign bit is sign extended to the right each time and, hence, the two extra 1s at the left.

Here also the problem of automatic promotion of **byte** and **short** type to **int** type is to be handled according to the requirement.

![](images/00011.jpeg)Both right shift (>>) and left shift (<<) operators retain the sign bits even after shifting. Hence, a programmer must be aware of the consequence of this when negative integers are used.

Right Shift Zero Fill Operator (>>>)

This operator, >>>, performs the same type of operation done by right shift operator, >>, except that sign bit extension is not done. Instead, zero will be inserted at the leftmost bit position for every shift. Therefore, in situations where the sign extension is unwanted, the right shift zero fill operator can be used. This operation is also called unsigned shift, as the other two shift operators, >> and <<, extend the sign bit. The general form of using this operator is:

variable >>> n

where, n specifies the number of bit positions of the variable to be shifted right with zero fill.

Example:

b = –25

= 10011001

The operation b >>> 2 gives

b = 00100110

= 38

You may compare this result with the earlier one with >> operator.

The reader is again reminded of the problem of automatic promotion of **byte** and **short** type to **int** type by Java. In most cases, masking off the higher order bytes in the int type will provide a solution to face such situations.

For all bitwise operators, the operator assignment form is also applicable.

Example:

1\. a = a>>3
can be written as
a >> = 3

2\. b = b & c can be written as
b &= c

3\. y = y>>>n can be written as
y >>>= n

Program 4.3 shows the use of bitwise operators.

Program 4.3![](images/00013.jpeg)

/*This program illustrates the use of bitwise operators

ka.somasundaram@gmail.com

This program requires jdk1.6 or higher

*/

import java.io.Console;

class Bitwise {

public static void main(String args[]) {

Console con = System.console();

int a, b, c, d;

a = 71;

con.printf("Please note that all operations%n

are done on 32 bit length%n%n");

con.printf(" In all the outputs, the leading

zeros are blank%n%n");

con.printf(" a = %d : %32s %n", a,

Integer.toBinaryString(a));

b = ~a;

con.printf(" ~a = %d: %32s%n", b,

Integer.toBinaryString(b));

c = 25;

con.printf(" a = %d : %32s %n", a,

Integer.toBinaryString(a));

con.printf(" c = %d : %32s %n", c,

Integer.toBinaryString(c));

b = a & c;

con.printf(" a&c = %d : %32s%n", b,

Integer.toBinaryString(b));

b = a | c;

con.printf(" a|c =%d : %32s%n", b,

Integer.toBinaryString(b));

b = a ^ c;

con.printf(" a^c =%d : %32s%n", b,

Integer.toBinaryString(b));

b = c << 2;

con.printf(" c<<2=%d: %32s%n", b,

Integer.toBinaryString(b));

b = c >> 2;

con.printf(" c>>2 =%d : %32s%n", b,

Integer.toBinaryString(b));

b = c >>> 2;

con.printf(" c>>>2=%d : %32s%n", b,

Integer.toBinaryString(b));

d = -25;

con.printf(" d = %d : %32s %n", d,

Integer.toBinaryString(d));

b = d >> 2;

con.printf(" d>>2=%d : %32s%n", b,

Integer.toBinaryString(b));

b = d >>> 2;

con.printf("d>>>2 :

%32s%n",Integer.toBinaryString(b) );

}

}

Output of the above program 4.3 is shown in Fig. 4.3.

![](images/00025.jpeg)

**Fig. 4.3** Output screen for program 4.3

4.3 RELATIONAL OPERATORS

For comparing the values of variables and literals, Java provides relational operators. Relational operators are used to relate a given value with several possible values of a variable. The results of the relational operators help to make branching, iterating a block and to terminate the block statement. The relational operators are given in Table 4.3.

**Table 4.3** Relational operators

| *Operation* | *Operator Symbol* |
| Equal to | == |
| Not equal to | != |
| Greater than | > |
| Greater than or equal to | >= |
| Less than | < |
| Less than or equal to | <= |

All relational operators are binary operators. The result of operating a relational operator is boolean, **true** or **false**. They operate on operands of type **char**, **byte**, **short**, **int**, **long**, **float** and **double**. For string variables and literals, separate methods are used and are given in Chapter 13.

Example:

| int a = 25; int b = 75;
double x = 35.87;
double y = 67.43;
char c1 = ‘b’;
char c2 = ‘d’; |
| 1\. a == b 2\. a != b
3\. a < b
4\. x > y
5\. c1 == c2
6\. c1 < c2
7\. x > b
8\. 35 == 10 | gives false gives true
gives true
gives false
gives false
gives false
gives false
gives false |

4.4 BOOLEAN LOGICAL OPERATORS

Logical operators operate only on boolean operands and not on numeric operands. Logical operators result in boolean values **true** or **false**. The boolean logical operators in Java are given in Table 4.4.

**Table 4.4** Boolean logical operators

| *Operation* | *Operator Symbol* |
| Logical AND | & |
| Logical OR | &#124; |
| Logical XOR | ^ |
| Short-circuit OR | &#124;&#124; |
| Short-circuit AND | && |
| Logical unary NOT | ! |
| Equal to | == |
| Not equal to | != |
| Ternary if-else | ?: |

These logical operators, except the unary NOT and ternary if-else, are binary operators. They are used in the same way as that for bitwise operators. The unary NOT complements true to false and false to true.

The following Table 4.5 gives results of various logical operations on the boolean variables A and B:

**Table 4.5** Truth table for boolean operators

![](images/00026.jpeg)

The following program 4.4 illustrates the use of logical operators:

Program 4.4![](images/00013.jpeg)

/* This program illustrates the use of boolean operators

ka.somasundaram@gmail.com

This program requires jdk1.6 or higher

*/

import java.io.Console;

class Boolean {

public static void main(String args[]) {

Console con = System.console();

int a = 25, b = 75;

double x = 43.52;

double y = 86.75;

char c1 = 'a';

char c2 = 'f';

boolean result;

con.printf(" Boolean Operations %n");

con.printf(" a = %d b=%d %n", a, b);

con.printf(" x = %5.2f b=%5.2f %n", x, y);

con.printf(" c1 = %c c2=%c %n", c1, c2);

result = (a > b);

con.printf(" %5b <-- (a>b) %n", result);

result = (x < y);

con.printf(" %5b <-- (x<y) %n", result);

result = c1 == c2;

con.printf(" %5b <-- c1==c2 %n", result);

result = (a > b) & (x < y);

con.printf(" %5b <-- (a>b)&(x<y) %n", result);

//OR

result = (a > b) | (x < y);

con.printf("%5b <-- (a>b)|(x<y) %n", result);

//Exclusive OR

result = (a > b) ^ (x < y);

con.printf("%5b <-- (a>b)^(x<y) %n", result);

result = (c1 != c2) ^ (b > 100);

con.printf("%5b <-- (c1!=c2)^(b>100) %n", result);

//NOT

result = !(a > b);

con.printf(" %5b <-- !(a>b) %n", result);

// ==

result = (a > b) == (x < y);

con.printf("%5b <-- (a>b)==(x<y) %n", result);

// !=

result = (a > b) != (x < y);

con.printf("%5b <-- (a>b)!=(x<y) %n", result);

// Ternary ?

result = (a < b) ? x > y : c1 != c2;

con.printf("%5b <--(a<b)?x>y:c1!=c2 %n", result);

result = (a > b) ? x > y : c1 != c2;

con.printf("%5b <-- (a>b)?x>y:c1!=c2 %n", result);

}

}

The output of program 4.4 is shown in Fig. 4.4.

![](images/00027.jpeg)

**Fig. 4.4** Output screen for program 4.4

Short-circuit && and || Operators

In the examples given in program 4.4, the expressions on both sides of the logical operators are evaluated and then the final result is obtained. However, from the first four columns of the Table 4.5 you will notice that:

(i) if one of the operands of the OR operation is true, then the result is always true irrespective of the value of the other operand.

(ii) if one of the operands of the AND operation is false, the result is always false, irrespective of the value of the other operand.

Therefore, in a logical OR operation, if the first operand has a value true, the result can be declared as true without checking or evaluating the value of the second operand. In a similar way, in an AND operation, if the first operand has a value false, the result can be declared as false without even evaluating the second operand. This feature is built into the short-circuit AND, &&, and short-circuit OR, ||, operators. These are more efficient than & and | as they save time spent for evaluating the second operand. The following examples illustrate the use of && and || operators.

Example:

| int a int
double x
double y
char c1
char c2 | = =
=
=
=
= | 25; b75;
34.25;
63.98;
‘a’;
‘d’; |

(1) (a>b) && (x<y)
= false (no need to evaluate the expression x < y)

(2) (c1! = c2) || (a<b)
= true (no need to evaluate a<b)

(3) (a>b) || (x<y)
= false || true
= true

Only in this kind of situations both operands are evaluated to get the final result.

![](images/00011.jpeg)The short-circuit logical AND (&&) and short-circuit logical OR (||) are more efficient than logical AND (&) and logical OR (|).

4.5 TERNARY OPERATOR (?)

The ternary operator, ?, operates on three operands. This operator can replace simple if-then-else statements. The general form of using this operator is:

expression1 ? expression2 : expression3

The expression1 should always result in a boolean value true or false. If the expression1 results in true, the expression2 is evaluated and expression3 is discarded, otherwise, expression3 is evaluated and expression2 is discarded. Program 4.5 illustrates the use of a ternary operator.

Program 4.5![](images/00013.jpeg)

/* This program illustrates the use of ternary operator

ka.somasundaram@gmail.com

This program requires jdk1.6 or higher

*/

import java.io.Console;

class Ternary {

public static void main(String args []) {

Console con = System.console();

int mark = 75;

String smark, result;

con.printf(" Type in the mark:");

//Get the mark from the console as String

smark=con.readLine();

//Convert String to int

mark=Integer.parseInt(smark);

result = (mark > 40) ? "Pass" : "fail";

con.printf(" Your Mark = %d%n", mark);

con.printf(" Result = %s%n" , result);

}

}

The above program gives the output shown in Fig. 4.5.

![](images/00028.jpeg)

**Fig. 4.5** Output screen for the program 4.5

In program 4.5, the **readLine**() method reads the keyboard entries as string. The **Integer.parseInt**() converts String to int.

4.6 OPERATOR PRECEDENCE

An expression contains a number of operators, variables and literals. A programmer must know how these operators are evaluated. Like in other computer languages, priorities are given for each operator. Operators are evaluated on the priorities allotted to them. This is called operator precedence. A good knowledge of these priorities is necessary to write unambiguous Java expressions. In most of the cases, an expression is evaluated from left to right of the expression. Unary and assignment operators take right to left association. The Java operator precedence from highest to lowest is given in Table 4.6.

The operators in a row have the same precedence and are evaluated in the order in which they appear in the expression. Use of parentheses in an expression alters the precedence and hence it is listed at the highest precedence or priority.

**Table 4.6** Operator precedence

| Highest | () [] |
|  | ! ++ – – +(unary) -(unary) (cast) |
|  | * / % |
|  | + – |
|  | << >> >>> |
|  | < <= > >= |
|  | == != |
|  | & |
|  | ^ |
|  | && |
|  | &#124;&#124; |
|  | ?: |
| Lowest | = op= |

Example:

int a=25, b=60, c=5;
double x = 5.5, y;
y = a+b / (2*c)–x
= 25 + 60 / **(2x5)**–5.5
= 25 + **60**/**10** – 5.5
= **25 + 6** – 5.5
= **31** – 5.5
= **31.0 – 5.5**
= 25.5

After reading this chapter, you should have learned the following:

*   Arithmetic operators
*   Bitwise operators
*   Relational operators
*   Logical operators and short circuit logical operators
*   Operator precedence

In the next chapter, you will learn about the control statements.

EXERCISE–4

**I. Fill in the blanks**

4.1 There are .......................... categories of operators in Java.

4.2 The result of the division 7/2 is .......................... .

4.3 The result of the operation 7.5%2.0 is .......................... .

4.4 The value of y in the following statements is .......................... .

int x = 50, y;
y = x++;

4.5 The following statement is .......................... . (valid/invalid):

y = ++70;

4.6 The bitwise operators can operate on float type operands. (True/False)

4.7 The sign independent bitwise operator is .......................... .

4.8 The equality operators operate only on integer variables or values. (True/False)

4.9 The result of using logical & and logical && is the same. (True/False)

4.10The use of parentheses in an expression will alter the precedence. (True/False)

**II. Write Java programs for the following**

4.11The register number, name and marks for three subjects are given. Write a program to find the average of the three marks and print it out along with the register number and name.

4.12A cloth shop during festival seasons offers a discount of 12% on all purchases made in that shop. The bill amount for a customer is given as Rs.750.5\. Write a program to calculate the discount, amount after discount and print it out.

4.13A bank gives 6.5% per annum compound interest on deposits made in that bank. Write a program to calculate the total amount that a person will receive after the end of 4 years for a deposit of Rs.5000/-.

4.14A motorcycle dealer sells two-wheelers to his customers on loan, which is to be repaid in 3 years. The dealer charges a simple interest of 14% for the whole term on the day of giving the loan itself. The total amount is then divided by 36 (months) and is collected as equated monthly installment (EMI). Write a program to calculate the EMI for a loan of Rs.39990\. Print the EMI value in rupees.

5Control StatementsIn this chapter, the statements that take the control from one location to another during execution of a program are given. The control statements help to make branching, looping, skipping and exiting a block of codes.

Basically, any computer-oriented problem can be solved using any combination of sequential, branching and looping structure. Therefore, a computer programming language should support these three structures. In this chapter, the statements supporting the branching and looping structures in Java are given. These statements help to branch or loop a segment of statements and are called control statements.

5.1 THE if...else STATEMENT

This statement helps to select one out of two possibilities based on the given condition. Hence, this statement is also called as conditional if statement.

The general form of the statement is:

**if** (conditional expression)

statement1;

**else**

statement2;

The conditional expression should result in a boolean value. If the condition, on evaluation, gives **true**, statement1 is executed and the control skips statement2, otherwise statement1 is skipped and statement2 is executed. The statement1 and the statement2 can be a simple or block statement. The else part is optional and, if needed, can be left out and can take the form:

**if** (conditional expression)

statement;

In this form, the statement will be executed, if the conditional expression gives **true**, otherwise it is skipped.

The flowchart for if..else and if... are given in Fig. 5.1 and Fig. 5.2 respectively.

![](images/00029.jpeg)

**Fig. 5.1** Flowchart for if... else statement

![](images/00030.jpeg)

**Fig. 5.2** Flowchart for if...statement

The following examples, 5.1 and 5.2, illustrate the if...else and if... statement:

Example 5.1

int mark;
String result;
if (mark >= 40)
result = “Pass”;

else

result = “Fail”;

Example 5.2

double a, b, c, discr, term;
discr = b*b–4.0*a*c;
if (discr < 0)
discr = –discr;
term = Maths.sqrt(discr);
root1 = (–b+term)/(2.0*a);
root2 = (–b–term)/(2.0*a);

Nested if..else

Nested if..else statement is made by placing one if..else inside another if..else statement. Nested if..else statement helps to select one out of many choices.

The general form of if..else statement is :

**if** (condition1)

**if** (condition2)

**if** (condition3)

statement 4

**else**

statement 3

**else** statement 2

**else**

statement 1

In the **nested if..else** statement, the outermost **if** is evaluated first. If the condition1 tested is false, the statement1 in the outmost **else** is evaluated and **if..else** ends. If the condition1 results in true, the control goes to execute the next inner **if** statement. If condition2 is false, statement2 is executed. Otherwise, condition3 is evaluated. If condition3 is false, statement3 is executed, otherwise statement4 is executed.

The flowchart for the **nested if..else** is given in Fig. 5.3.

![](images/00031.jpeg)

**Fig. 5.3** Flowchart for nested if...else statement

The following program 5.1 illustrates the use of nested if..else statement:

Program 5.1![](images/00013.jpeg)

/*Declaring result using nested if... else statement

* This program requires jdk1.6 for compiling

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Nestedif {

public static void main(String args[]) {

Console con = System.console();

String nam, savg_mark, result_class;

int avg_mark;

con.printf("%n What is your name?:");

nam = con.readLine();

con.printf("%n What is your average mark(int)?:");

savg_mark = con.readLine();

avg_mark = Integer.parseInt(savg_mark);

if (avg_mark > 50) {

if (avg_mark >= 60) {

if (avg_mark >= 75) {

result_class = "Distinction";

} else {

result_class = "First Class";

}

} else {

result_class = "Second Class";

}

} else {

result_class = "Third Class";

}

if (avg_mark < 40) {

con.printf("%n %s Failed", nam);

} else {

con.printf("%n %s Passed in %s", nam, result_class);

}

}

}

The output of the program 5.1 is shown in Fig. 5.4.

![](images/00032.jpeg)

**Fig. 5.4** Output screen for program 5.1

Another form of nested if..else is the ladder if.. else statement. The structure of the ladder if..else statement is :

**if** (condition1)
statement1;
**else if** (condition2)
statement2;
**else if** (condition 3)
statement 3;
**else**
statement4;

The flowchart for the above ladder if...else statement is given in Fig. 5.5.

![](images/00033.jpeg)

**Fig. 5.5** Flowchart for ladder if..else statement

The following program 5.2 illustrates the ladder if...else statement:

Program 5.2![](images/00013.jpeg)

/* This program illustrates the ladder if else statement

This program requires jdk1.6 for compiling

ka.somasundaram@gmail.com

*/

import java.io.Console;

class Ladderif {

public static void main(String args[]) {

Console con = System.console();

String nam, savg_mark, result_class;

int avg_mark;

con.printf("%n What is your name?:");

nam = con.readLine();

con.printf("%n What is your average mark(int)?:");

savg_mark = con.readLine();

avg_mark = Integer.parseInt(savg_mark);

if (avg_mark > 75) {

result_class = "Distinction";

} else if (avg_mark >= 60) {

result_class = "First Class";

} else if (avg_mark >= 50) {

result_class = "Second Class";

} else {

result_class = "Third Class";

}

if (avg_mark < 40)

{

con.printf("%n %s Failed", nam);

} else {

con.printf(" %n%s Passed with %s%n ", nam, result_class);

}

}

}

The above program 5.2 gives the output shown in Fig. 5.6.

![](images/00034.jpeg)

**Fig. 5.6** Output screen for program 5.2

5.2 THE switch STATEMENT

The **switch** statement helps to select one out of many choices. This helps to write a clear statement when compared to nested if...else statements. The general form of **switch** statement is:

**switch** (expression) {
**case** val1 : statement1;
**break**;
**case** val2 : statement2;
**break**;
**case** val3 : statement3;
**break**;
.
.
**case** valN : statementN;
**break**;
**default** : statement;
}

It is expected that the expression, when evaluated, should give discrete values in the range val1 to valN. If the expression gives val1, the statement1 is executed and the control exits the switch block. If the expression gives val2, statement2 is executed and so on (Fig. 5.7). If the expression gives any value that is not matching between val1 and valN, the statement given in default is executed. The expression should give any of the type **byte**, **short**, **int, char** or **String**. In this way, multiple branching can be effected. The **break** statement when executed will take the control out of the **switch** block. Generally, **switch** statement is used for expressions that may give discrete and predefined values.

![](images/00035.jpeg)

**Fig. 5.7** Flowchart for switch statement

The following program 5.3 illustrates the use of **switch** statement:

Program 5.3![](images/00013.jpeg)

/* This program illustrates the switch statement.

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class SwitchDemo {

public static void main(String args[]) {

Console con = System.console();

int month;

String smonth;

con.printf(“%n Type in the number of a Month (1–12): “);

smonth = con.readLine();

month = Integer.parseInt(smonth);

switch (month) {

case 1:

smonth = “January”;

break;

case 2:

smonth = “February”;

break;

case 3:

smonth = “March”;

break;

case 4:

smonth = “April”;

break;

case 5:

smonth = “May”;

break;

case 6:

smonth = “June”;

break;

case 7:

smonth = “July”;

break;

case 8:

smonth = “August”;

break;

case 9:

smonth = “September”;

break;

case 10:

smonth = “October”

break;

case 11:

smonth = “November”;

break;

case 12:

smonth = “December”;

break;

default:

smonth = “no match found”;

}

con.printf(“%n The given month is %s”, smonth);

}

}

The above program gives the following output shown in Fig. 5.8.

![](images/00036.jpeg)

**Fig. 5.8** Output screen for program 5.3

Sometimes, for several case values, one common process may be required. In such problems, several case values can be clubbed so that statements common to all of them can be executed at one point. The following program 5.4 shows how several cases can be combined:

Program 5.4![](images/00013.jpeg)

/* This program illustrates the switch statement with
group case.

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Switch1 {

public static void main(String args[]) {

Console con = System.console();

int numb;

String snumb, range;

con.printf("%n Type in a number between 1–10: ");

snumb = con.readLine();

numb = Integer.parseInt(snumb);

switch (numb) {

case 1:

case 2:

case 3:

range = "The number is between 1 and 3";

break;

case 4:

case 5:

case 6:

case 7:

range = "The number is between 4 and 7";

break;

case 8:

case 9:

case 10:

range = "The number is between 8 and 10";

break;

default:

range = "The number is outside 1 and 10";

}

con.printf("%n %s", range);

}

}

The above program 5.4 gives the following output shown in Fig. 5.9.

![](images/00037.jpeg)

**Fig. 5.9** Output screen for program 5.4

![](images/00011.jpeg)The type of data handled in **switch** statement must be of the type **byte**, **short**, **int, char** or **String**. The values used must be discrete.

5.3 THE while STATEMENT

The **while** statement is used for looping or iterating a block of statements while the given condition is **true**. The general form of the **while** statement is:

**while** (condition)
{
statements;
}

The condition, when evaluated, must result in the boolean value **true** or **false**. As long as the condition gives **true,** the statement block will be executed. When the condition becomes **false**, the control leaves the block statement. The flow of control in **while** statement is given in Fig. 5.10.

![](images/00038.jpeg)

**Fig. 5.10** Flowchart for while statement

When the condition tested is **false** in the first instance itself, the block statement will not be executed at all. The following program 5.5 shows the use of **while** structure:

Program 5.5![](images/00013.jpeg)

/* This program illustrates the use of while statement.

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class WhileDemo {

public static void main(String args[]) {

Console con = System.console();

int n, max, sum = 0;

String sn;

con.printf("%n Type in a number to find the sum: ");

sn = con.readLine();

n = Integer.parseInt(sn);

max = n;

while (n > 0) {

sum += n––;

}

con.printf("%n Sum of numbers from 1 to %d is = %d", max, sum);

}

}

The above program 5.5 gives the following output shown in Fig. 5.11.

![](images/00039.jpeg)

**Fig. 5.11** Output screen for program 5.5

![](images/00011.jpeg)In **while** statement, the condition is checked before executing the codes.

5.4 THE do..while STATEMENT

This **do..while** control statement is used for looping a block of statements while the given condition is **true**. In this structure, the condition is tested at the end of the block. This is in contrast to the **while**.. statement, where the condition is tested at the start of the block. The general form of **do..while** statement is:

**do**
{
statements;
} **while** (condition);

The condition tested can be any expression that will yield a boolean value. As long as the condition tested is **true,** the whole block will be executed. Once the condition tested becomes **false**, the control leaves the block. It is to be noted that the block is executed once before the condition is tested. Therefore, even if the condition tested is **false** at the first instance itself, the block statement is executed once. The flowchart of a **do..while** structure is given in Fig. 5.12.

![](images/00040.jpeg)

**Fig. 5.12** Flowchart for do....while statement

The following program 5.6 illustrates the **do...while** statement:

Program 5.6![](images/00013.jpeg)

/*This program illustrates the use of do..while statement.

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class DoWhileDemo {

public static void main(String args[]) {

Console con = System.console();

int n, max, sum = 0;

String sn;

con.printf(“%n Type in a number to find the sum: “);

sn = con.readLine();

n = Integer.parseInt(sn);

max = n;

do {

sum += n––;

} while (n > 0);

con.printf(“%n Sum of numbers from 1 to %d is = %d”, max, sum);

}

}

The above program 5.6 gives the following output shown in Fig. 5.13.

![](images/00041.jpeg)

**Fig. 5.13** Output screen for program 5.6

![](images/00011.jpeg)In **do...while** statement, the condition is checked after executing the codes.

5.5 THE for... STATEMENT

This is the third form of looping statement. This statement is a self-contained one, that is the initial value, termination condition, iterator (increment/decrement) are all given in the **for** structure itself. The general form of **for** statement is:

**for** (initializer; condition; iterator)
{
statements;
}

Here, the condition can be any expression that yields boolean value **true** or **false**. The initializer is used to store the initial value for a loop variable. The iterator modifies the loop variable. The statements in the block are executed, as long as the condition tested gives **true**. When the condition becomes **false**, the control leaves the block statement. The flowchart for the **for** loop is given in Fig. 5.14.

![](images/00042.jpeg)

**Fig. 5.14** Flowchart for the for loop

Program 5.7 shows the use of **for**.. statement.

Program 5.7![](images/00013.jpeg)

/* This program illustrates the use of for statement.

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com */

import java.io.Console;

class ForDemo1 {

public static void main(String args[]) {

Console con = System.console();

int n, i, max, sum = 0;

String sn;

con.printf(“%n Type in a number to find the sum: “);

sn = con.readLine();

n = Integer.parseInt(sn);

max = n;

for (i = n; n > 0; n––) {

sum += n;

}

con.printf(“%n Sum of numbers from 1 to %d is = %d”, max, sum);

}

}

The above program 5.7 gives the following output shown in Fig. 5.15.

![](images/00043.jpeg)

**Fig. 5.15** Output screen for program 5.7

The above program 5.7 can be written in another form as given in program 5.8\. The loop variable n can be declared inside the **for** structure itself. The iterator is optional. If there is no need for an iterator in a program, it can be left blank.

Program 5.8![](images/00013.jpeg)

/* This program illustrates the use of for statement.

* The iterator is left blank as it is done outside the

for structure

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class ForDemo2 {

public static void main(String args[]) {

Console con = System.console();

int n, max, sum = 0;

String sn;

con.printf(“%n Type in a number to find the sum: “);

sn = con.readLine();

n = Integer.parseInt(sn);

max = n;

for (int i = n; n > 0;) {

sum += n––;

}

con.printf(“%n Sum of numbers from 1 to %d is = %d”,

max, sum);

}

}

The **for** loop in program 5.8 can be improved further and written in a compact form as : for (int i=n; n>0; sum+=n– –)

![](images/00011.jpeg)In a **for** structure, one, two or all the three components, initializer, condition, iterator, can be absent. The statement for ( ; ; ) is valid and will make an infinite loop.

The following program 5.9 computes the factorial of the given number.

Program 5.9![](images/00013.jpeg)

/* This program finds the factorial of a number using for

statement.

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Factorial {

public static void main(String args[]) {

Console con = System.console();

int n;

String sn;

long fact = 1;

con.printf(“%n Type in a number to find the factorial: “);

sn = con.readLine();

n = Integer.parseInt(sn);

for (int i = 1; i <= n; ++i) {

fact *= i;

}

con.printf(“Factorial of %d is = %d\n”, n, fact);

}

}

The above program 5.9 gives the following output shown in Fig. 5.16.

![](images/00044.jpeg)

**Fig. 5.16** Output screen for program 5.9

The **for** loops can be nested one within another as shown below:

- - - - - - -

- - - - - - -

- - - - - - -

for (i=1; i<n; i++) // outer loop begins

{ - - - - - - - -

  - - - - - - - -

for (k=1; k<m; k++) // inner loop begins

{

.

.

.

} // inner loop ends

.

.

.

} // outer loops ends

.

.

.

The following program 5.10 illustrates the nested **for** loop. It generates multiplication tables for 2, 3 and 4.

Program 5.10![](images/00013.jpeg)

/* This program illustrates the nested for loop

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class MulTable {

public static void main(String args[]) {

Console con = System.console();

int i, j, m = 4, n = 5;

int prod;

for (i = 2; i <= m; ++i) {

con.printf(“Multiplication Table for %d%n”, i);

for (j = 1; j <= n; ++j) {

prod = j * i;

con.printf(“ %d X %d = %d%n”, j, i, prod);

}

con.printf(“%n “); // create one line spaces

}

}

}

The above program 5.10 gives the following output shown in Fig. 5.17.

![](images/00045.jpeg)

**Fig. 5.17** Output screen for program 5.10

5.6 THE break STATEMENT

The **break** statement is to be used only in loops and **switch** statements. When this statement is executed, the control is taken out of the loop. The loop becomes dead. The flowchart for the break statement is given in Fig. 5.18.

The following program 5.11 illustrates the use of break in a for loop:

![](images/00046.jpeg)

**Fig. 5.18** The flowchart for break statement

Program 5.11![](images/00013.jpeg)

/* This program illustrates the use of break statement

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com */

import java.io.Console;

class BreakDemo {

public static void main(String args[]) {

Console con = System.console();

int n = 5, m = 20;

for (int i = 1; i <= m; i++) {

if (n * i > 30) {

con.printf(“%n Exiting the loop”);

break;

}

con.printf(“ %d X %d = %d%n”, i, n, n * i);

}

}

}

The above program 5.11 gives the following output shown in Fig. 5.19.

![](images/00047.jpeg)

**Fig. 5.19** Output screen for program 5.11

Blocks can be labeled and the **break** control can be made to exit any labeled block. This is called labeled break. The label for a block can be formed by using the rules to form a variable. The labeled break is useful when using nested loops. The following program 5.12 illustrates the labeled break statement:

Program 5.12![](images/00013.jpeg)

/* This program illustrates the use of labeled break statement

* This program requires jdk1.6 or higher to compile and execute

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class LabelBreak {

public static void main(String args[]) {

Console con = System.console();

int n = 0, m = 0;

loop1:

while (true) {

n++;

m = 0;

con.printf(“%n loop1 n = %d%n”, n);

loop2:

while (++m <= n) {

if (n * m > 10) {

con.printf(“%n Exiting loop2 and loop1%n”);

break loop1;

}

con.printf(“ loop2 %d X %d = %d%n”,

m, n, n * m);

}

}

con.printf(“%n outside loop1”);

}

}

The above program 5.12 gives the following output shown in Fig. 5.20.

![](images/00048.jpeg)

**Fig. 5.20** Output screen for program 5.12

5.7 THE continue STATEMENT

The **continue** statement is used inside the loop control blocks. When the **continue** statement is executed, the control skips the remaining portion of the loop and goes to the beginning of the loop and continues. The flowchart for the continue statement is given in Fig. 5.21.

The following program 5.13 illustrates the use of continue statement:

![](images/00049.jpeg)

**Fig. 5.21** Flowchart for continue statement

Program 5.13![](images/00013.jpeg)

/* This program illustrates the use of continue statement

* This program requires jdk1.6 or higher to compile and execute

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class ContinueProg {

public static void main(String args[]) {

Console con = System.console();

int i = 0;

while (++i < 10) {

if (i % 2 == 0) {

continue;

}

con.printf(“ %d\n”, i);

}

}

}

The above program 5.13 gives the following output shown in Fig. 5.22.

![](images/00050.jpeg)

**Fig. 5.22** Output screen for program 5.13

Like labeled break, labeled continue structure is also available. The following program 5.14 illustrates the use of labeled continue:

Program 5.14![](images/00013.jpeg)

/* This program illustrates the use of labeled continue

statement.

* This program finds all the prime numbers between 1 and

the given number

* This program requires jdk1.6 or higher to compile and execute

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class LabelContinue {

public static void main(String args[]) {

Console con = System.console();

int i = 1, n, max;

String smax;

con.printf(“%n Find prime numbers up to:”);

smax = con.readLine();

max = Integer.parseInt(smax);

con.printf(“%n Prime numbers between 1 and %d%n”, max);

con.printf(“ %d%n”, i);

start:

for (n = 2; n <= max; ++n) {

test:

for (i = 2; i < n; ++i) {

if (n % i == 0) {

continue start;

}

}

con.printf(“ %d%n”, n);

}

}

}

The above program 5.14 gives the following output shown in Fig. 5.23.

![](images/00051.jpeg)

**Fig. 5.23** Output screen for program 5.14

5.8 THE Comma STATEMENT

Java allows multiple initialization and iteration in the **for** statement. With this capability, more than one variable can be initialized and more than one iteration can be done. Each of such statements are to be separated by a comma(,). But there can be only one conditional expression. The general form of the multiple initialization and iteration is:

for (init1, init2, init3; condition; itr1, itr2, itr3)
{
Statements;
}
The following program 5.15 illustrates the use of comma statement.

Program 5.15![](images/00013.jpeg)

/* This program illustrates the use of comma statement.

* This program requires jdk1.6 or higher to compile and execute

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class CommaDemo {

public static void main(String args[]) {

Console con = System.console();

int n, i, sum;

for (i = 1, n = 5; n > 0; i++, n––, sum = 0) {

sum = i + n;

con.printf(“%d + %d = %d%n”, i, n, sum);

}

}

}

The output for the above program 5.15 is shown in Fig. 5.24.

![](images/00052.jpeg)

**Fig. 5.24** Output screen for program 5.15

After reading this chapter, you should have learned the following:

*   Branching using if...else control
*   Branching using switch control
*   Looping with while, do...while and for...control
*   Using break and continue

In the next chapter, you will learn about arrays.

![](images/00053.jpeg)

Program 5.1T

The trigonometric functions Sin(x) and Cos(x) are computed using the following formula:

![](images/00054.jpeg)

Calculate the Sin(x) and Cos(x) values for x = 0, 0.5 and 1.5\. The following expressions which represent the above are made use of:

![](images/00055.jpeg)

Program 5.1T![](images/00013.jpeg)

/* -------------------------------------------------------

This program calculates the sin(x) and cos(x) functions
The values obtained are compared with that Java functions
This program requires jdk1.6 or higher
ka.somasundaram@gmail.com

------------------------------------------------------- */

import java.io.Console;

class TIO51 {

public static void main(String args []){

Console con=System.console();

double x, sinx, cosx,jsx,jcx;

int n, fact = 1, factn, factnplus, maxcol=37;

int m = 5;

for (int i = 0; i < maxcol; i++)

con.printf(“–”);

con.printf(“%n”);

con.printf(“x sinx \t Java \t cosx \t Java %n”);

for (int i = 0; i < maxcol; i++)

con.printf(“–”);

con.printf(“%n”);

for (x = 0; x < 1.6; ){

sinx = x;

cosx = 1;

for (n = 1; n <= m; n++){

factn = 1;

factnplus = 1;

for (int i = 2; i <= 2 * n; i++)

factn = factn * i;

for (int i = 2; i <= (2 * n + 1); i++)

factnplus = factnplus * i;

sinx = sinx + Math.pow(–1, n) *

Math.pow(x, (2 * n + 1)) / factnplus;

cosx = cosx + Math.pow(–1, n) *

Math.pow(x, 2 * n) / factn;

}

jsx=Math.sin(x);

jcx=Math.cos(x);

con.printf(“%3.1f %5.3f \t%5.3f \t%5.3f \t%5.3f \t %n”, x, sinx, jsx, cosx ,jcx) x = x + 0.5;

}

for (int i = 0; i < maxcol; i++)

con.printf(“–”);

con.printf(“%n”);

}

}

The above program gives the following output shown in Fig. 5.25.

![](images/00056.jpeg)

**Fig. 5.25** Output screen for program 5.1T

Program 5.2T

Write a program to convert the given number in digits to words (Ex:237 –> two three seven).

Program 5.2T![](images/00013.jpeg)

/* The given number is written in words

* This program requires jdk1.6 or higher to compile and execute

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Digit2word {

public static void main(String args[]) {

Console con = System.console();

int numb, gnumb, reminder, quotient;

String sword = “”, word = “”, snumb;

con.printf(“%n Type in the number : “);

snumb = con.readLine();

gnumb = Integer.parseInt(snumb);

numb = gnumb;

while (numb > 0) {

reminder = numb % 10;

switch (reminder){

case 0:

sword = “zero “;

break;

case 1:

sword = “One “;

break;

case 2:

sword = “two “;

break;

case 3:

sword = “three “;

break;

case 4:

sword = “four “;

break;

case 5:

sword = “five “;

break;

case 6:

sword = “six “;

break;

case 7:

sword = “seven “;

break;

case 8:

sword = “eight “;

break;

case 9:

sword = “nine “;

break;

default:

sword = “No digit”;

}

word = sword + word;

numb = numb / 10;

}

con.printf(“%n The given number %d in words :%s”, gnumb, word);

}

}

The above program gives the following output shown in Fig. 5.26.

![](images/00057.jpeg)

**Fig. 5.26** Output screen for program 5.2T

EXERCISE–5

**I. Fill in the blanks**

5.1 The if..else structure helps to make a .......................... from the sequential computation of statements in a program.

5.2 To select one out of many options in a computation, .......................... if-else can be used.

5.3 switch statement can be used to select one out .......................... options.

5.4 The case value in a switch statement must be .......................... .

5.5 The .......................... statement tests the condition at the end of the block.

5.6 In a for..loop the condition is tested at the .......................... of the block.

5.7 In a for.. statement more than one initializer is allowed. (True/False)

5.8 In a for..statement with more than one initializer, there can be more than one condition. (True/False)

5.9 The break statement can be used only in .......................... and .......................... statements.

5.10The .......................... statement when encountered takes the control out of the loop block.

**II. Write programs for the following:**

5.11A cloth shop during festival season offers a discount 10% for purchases made up to Rs.1,000, 12% for purchase value of Rs.1000 or more up to Rs.1,500 and 15% for purchase value of Rs.1,500 or more. Write a program to implement the above scheme for a given sales and print out the sales value, discount and net amount payable by a customer.

5.12The roots of a quadratic equation

ax²+bx+c=0

are given by :

![](images/00058.jpeg)

with the condition if (b²–4ac) < 0, then the absolute value |(b²–4ac)| is to be taken. Given a, b, c, write a Java program to compute the two roots x[1] and x[2] .

5.13An electric appliance shop assigns code 1 to motor, 2 to fan, 3 to tube light and 4 for wires. All other items have code 5 or more. While selling the goods, a sales tax of 8% to motor, 12% to fan, 5% to tube light, 7.5% to wires and 3% for all other items is charged. A list containing the product code and price is given for making a bill. Write a Java program using switch statement to prepare the bill.

6ArraysIn this chapter, a collection of like-typed data called arrays is explained. Single-dimensional and multi-dimensional arrays are discussed.

An array is a variable representing a collection of like-typed data. Arrays are useful in representing vectors, matrices, strings and tables. When an array is created, it reserves a specified number of memory locations to store the values of a collection of data of a particular type. Each of the memory locations is identified by an index associated with the array variable. An array is treated as an object.

6.1 ONE-DIMENSIONAL ARRAY

In Java, an array is created in two steps. First, an array variable is to be declared and then an array object is to be created using **new** operator by specifying the number of memory locations required. These two steps can be done through two separate statements or in a single statement. The following example illustrates the creation of an **int** type array in two statements:

int numb[];
numb = new int [12];

The first statement declares an array variable numb of type **int**. The second statement allocates memory for 12 **int** type. Now, numb can handle 12 **int** type values. Each value can be accessed by using index values 0 to 11. Supposing the 12 **int** values are 7, 45, 3, 4, 26, 35, 40, 75, 99, 125, 54, 65, the array will be referred by the index as given below:

![](images/00059.jpeg)

You may observe that the array values are accessed by the index value from 0 to 11 and not from 1 to 12\. If any element of the array is accessed beyond the index value 11, array index out of bounds error will occur.

![](images/00011.jpeg)Index value of arrays start from 0\. An array of 5 elements will have index from 0 to 4.

The following program 6.1 illustrates the use of an array:

Program 6.1![](images/00013.jpeg)

/* This program illustrates the use of array.

* This program requires jdk1.6 or higher to compile and execute

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Array1 {

public static void main(String args[]) {

Console con = System.console();

int marks[];

marks = new int[5];

int total;

double average;

marks[0] = 77;

marks[1] = 56;

marks[2] = 60;

marks[3] = 89;

marks[4] = 70;

total = 0;

for (int i = 0; i < 5; i++) {

total += marks[i];

con.printf(“ Marks[%d] = %d\n”,i, marks[i]);

}

con.printf(“ Sum of marks = %d\n”, total);

average = total / 5.0;

con.printf(“ Average mark = %5.2f” , average);

}

}

The output of the above program 6.1 is shown in Fig. 6.1.

![](images/00060.jpeg)

**Fig. 6.1** Output screen for program 6.1

The declaration of the array and creation of the array can be done in a single statement. The following two statements in the above program 6.1 are:

int marks[];
marks = new int [12];
They can be replaced by a single statement
int marks[] = new int [12];

Array Initialization

Arrays can be initialized by writing the values inside the braces { and }. In such cases, the number of elements need not be specified. The following program 6.2 shows how to initialize an array:

Program 6.2![](images/00013.jpeg)

/* This program illustrates the use of

array initialization.

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com */

import java.io.Console;

class Arrayinit {

public static void main(String args[]) {

int marks[] = {77, 56, 60, 89, 70};

int total;

double average;

total = 0;

Console con = System.console();

for (int i = 0; i < 5; i++) {

total += marks[i];

con.printf(“ marks[%d] = %d%n”,i, marks[i]);

}

con.printf(“ Sum of marks = %d%n”, total);

average = total /5.0;

con.printf(“ Average mark =%5.2f%n “, average);

}

}

The above program 6.2 gives the same output as that of the program 6.1\. You may observe that the use of new operator is not required when an array is initialized. Java counts the number of values inside { } and reserves the required number of storage spaces automatically.

![](images/00011.jpeg)When an array is declared and initialized with values, the new operator is not required.

Array declaration can also be done in an alternative form as given below:

int[] marks = new int[12];

which is equivalent to

int marks[] = new int[12];

6.2 MULTI-DIMENSIONAL ARRAY

Java supports multi-dimensional arrays. A conventional matrix can be represented in a two-dimensional array. A two-dimensional array is declared by two pairs of square brackets as [][]. A three-dimensional array is declared by three pairs of square brackets of [][][] and so on. The following statements declare and allocate memory for a 3 × 4 matrix of **int** type:

int mat[ ] [ ] = new int [3][4];

This statement creates matrix with 3 rows and 4 columns.

The row index varies from 0 to 2 and the column index varies from 0 to 3.

The following program 6.3 illustrates the use of two-dimensional array:

![](images/00061.jpeg)

**Fig. 6.2** Multi -dimensional array

Program 6.3![](images/00013.jpeg)

/* This program illustrates the use of two dimensional

array.

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class TwoDArray {

public static void main(String args[]) {

int mat[][] = new int[3][4];

Console con = System.console();

//assign values to the elements

for (int row = 0; row < 3; row++) {

for (int column = 0; column < 4; column++) {

mat[row][column] = row * column;

}

}

//print the matrix

for (int row = 0; row < 3; row++) {

for (int column = 0; column < 4; column++) {

con.printf(“ “ + mat[row][column]);

}

con.printf(“%n%n”); // print 2 new lines

}

}

}

The output of the above program is shown in Fig. 6.3.

![](images/00062.jpeg)

**Fig. 6.3** Output screen for program 6.3

In Java, it is possible to have rows of varying columns as given below:

int mat [ ] [ ] = new int [3] [ ];

mat[0] = new int [2];

mat[1] = new int [3];

mat[2] = new int [4];

The above statements create rows and columns as shown in Fig. 6.4.

The above statements create a two-dimensional array with row 0 with 2 column elements, row 1 with 3 columns and row 2 with 4 columns.

![](images/00063.jpeg)

**Fig. 6.4** Multi-dimensional array with varying columns

![](images/00011.jpeg)Matrix of varying column elements can be created in Java.

Multi-dimensional arrays can be initialized like one-dimensional array. Each row is enclosed in a pair of braces { } separated by a comma(,). All the rows are then placed inside another pair of braces { } separated by comma(,). The following program 6.4 illustrates the use of initializing two-dimensional array of 3 rows and 4 columns:

Program 6.4![](images/00013.jpeg)

/* This program illustrates the

* intialization of two dimensional array.

* This program requires jdk1.6 or higher to compile and execute

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class MultiDInit {

public static void main(String args[]) {

Console con = System.console();

int mat[][] = {{0, 1, 2, 3}, {4, 5, 6, 7}, {8, 9, 10, 11}};

con.printf(“The given matrix%n%n”);

for (int row = 0; row < 3; row++) {

for (int column = 0; column < 4; column++) {

con.printf(“%2d “ , mat[row][column]);

}

con.printf(“%n%n”);

}

}

}

The above program gives the following result shown in Fig. 6.5.

![](images/00064.jpeg)

**Fig. 6.5** Output screen for program 6.4

In engineering and scientific computations, matrix multiplication is commonly used. The following program 6.5 illustrates one such example. The following program initializes a matrix mat1 with 2 × 3 elements, another one mat2 with 3 × 3 elements and finds the product of both to give a third matrix mat3 of 2 × 3 elements.

Program 6.5![](images/00013.jpeg)

/*This program carry out matrix multiplication

* This program requires jdk1.6 or higher to compile and execute

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class MatMul {

public static void main(String args[]) {

Console con = System.console();

int mat1[][] = {{5, 4, 7}, {1, 7, 4}};

int mat2[][] = {{1, 5, 7}, {2, 4, 6}, {3, 5, 7}};

int mat3[][] = new int[2][3];

int i, j, k;

for (i = 0; i < 2; i++) {

for (k = 0; k < 3; k++) {

mat3[i][k] = 0;

for (j = 0; j < 3; j++) {

mat3[i][k] = mat3[i][k] + mat1[i][j] *

mat2[j][k];

}

}

}

con.printf(“%n Matrix 1%n%n”);

for (i = 0; i < 2; i++) {

for (j = 0; j < 3; j++) {

con.printf(“ %2d”, mat1[i][j]);

}

con.printf(“%n%n”);

}

con.printf(“ Matrix 2%n%n”);

for (i = 0; i < 3; i++) {

for (j = 0; j < 3; j++) {

con.printf(“ %2d” , mat2[i][j]);

}

con.printf(“%n%n”);

}

con.printf(“ Product Matrix%n%n”);

for (i = 0; i < 2; i++) {

for (j = 0; j < 3; j++) {

con.printf(“%5d” , mat3[i][j]);

}

con.printf(“%n%n”);

}

}

}

The above program gives the following output shown in Fig. 6.6.

![](images/00065.jpeg)

**Fig. 6.6** Output screen for program 6.5

The most frequently used program involving arrays is sorting numbers. The following program 6.6 shows how to sort a number in descending order.

Program 6.6![](images/00013.jpeg)

/*-------------------------------------------------------

This program sorts an array in descending order.

This program requires jdk1.6 or higher for compile and execute

ka.somasundaram@gmail.com

--------------------------------------------------------*/

import java.io.Console;

class Sorting {

public static void main(String args[]) {

int temp, i, j;

int mark[]={35,25,76,89,76,65,81,63,41};

Console con = System.console();

//find the no of elements in the array

int maxn=mark.length;

// Print out the given numbers

con.printf(“The given numbers %n%n”);

for (i = 0; i < maxn; i++) {

con.printf(“%d “, mark[i]);

}

con.printf(“ %n”);

// Sort the numbers in descending order

for (i = 0; i < maxn; i++) {

for (j = i + 1; j < maxn; j++) {

if (mark[j] > mark[i]) {

temp = mark[i]

mark[i] = mark[j];

mark[j] = temp;

}

}

}

// Print the sorted numbers

con.printf(“%n”); // Make a new line

con.printf(“The sorted numbers%n%n”);

for (i = 0; i < maxn; i++) {

con.printf(“%d “, mark[i]);

}

}

}

The above program 6.6 gives the following output shown in Fig. 6.7.

![](images/00066.jpeg)

**Fig. 6.7** Output screen for program 6.6

In the program 6.6, the **length** method finds the number of elements in the array.

6.3 Arrays CLASS

Java language has a built-in **Arrays** class packaged in **java.util** package. It has several convenient methods to handle an array. Table 6.1 gives some of the methods in **Arrays** class.

**Table 6.1** Some of the methods defined in Arrays class

| *Method* | *Purpose of the method* |
| 1. | Static int binarySearch (type[] array, type key) | Searches the array (sorted) for the specified key using binary search algorithm. Returns the index of the key if it is found otherwise returns the index of the position at which the key is to be inserted +1 with -sign. The type can be byte, short, int, long, float, double, char or object |
| 2. | Static int binarySearch (type[] array, int fromIndex, int toIndex, type key) | Searches the array (sorted) in the range specified for the key using binary search algorithm. Returns the index of the key if it is found. Otherwise returns the index of the position at which the key is to be inserted +1, with –sign. Type can be byte, short, int, long, float, double, char or object |
| 3. | Static type[] copyOf (type[] original, int newLen) | Copies the source array to another array of size newLen Type can be byte, short int, long, float, double, char or object |
| 4. | Static void  fill (type[] array, type val) | Fills the array with the specified value val. |
| 5. | Static void fill (type[] array, int fromIndex, int to Index, type val) | Fills the array in the specified range with the given value val. |
| 6. | Static void sort (type[] array) | Sorts the given array in ascending order. The type can be byte, short, int, long, float, double, char or object |
| 7. | Static void sort(type[] array, int fromIndex, int toIndex) | Sorts the given array in the specified range in ascending order. The type can be byte, short, int, long, float, double, char or object |

Program 6.7 illustrates the use of sort() and binarySearch() methods defined in **Arrays** class.

Program 6.7![](images/00013.jpeg)

/* ------------------------------------------------------

This program sorts an array in ascending order

using sort method of Arrays class.

Search for the given value using binarySearch() method

This program requires jdk1.6 or higher.

ka.somasundaram@gmail.com

--------------------------------------------------------*/

import java.io.Console;

import java.util.Arrays;

class Arraysort {

public static void main(String args[]) {

int temp, i, j,location;

int mark[]={35,25,79,89,76,65,81,63,41};

Console con = System.console();

//find the no of elements in the array

int maxn=mark.length;

// Print out the given numbers

con.printf(“ The given numbers %n%n”);

for (i = 0; i < maxn; i++) {

con.printf(“ %d “, mark[i]);

}

con.printf(“%n”);

// Sort the numbers in descending order

Arrays.sort(mark);

// Print the sorted numbers

con.printf(“%n”); // Make a new line

con.printf(“ The sorted numbers%n%n”);

for (i = 0; i < maxn; i++) {

con.printf(“ %d “, mark[i]);

}

con.printf(“%n%n”);

//search the array for the value 63

location=Arrays.binarySearch(mark,63);

con.printf(“The location of value 63 is %d%n”, location);

//search the array for the value 80

location=Arrays.binarySearch(mark,80);

con.printf(“The location of value 80 is %d%n”, location);

}

}

Program 6.7 gives the output shown in Fig. 6.8.

![](images/00067.jpeg)

**Fig. 6.8** Output screen for program 6.7

After reading this chapter, you should have learned the following:

*   A collection of like type is called an array.
*   Array elements can be accessed by an index.
*   Single and multi-dimensional arrays are supported in Java language.
*   Multi-dimensional arrays with varying columns can be declared.
*   There is an Arrays class to handle arrays conveniently.
*   To sort a given set of numbers or strings, an array is needed.

In the next chapter, you will learn about Java classes.

![](images/00053.jpeg)

Problem 6.1T

An electricity board charges different rates for different categories of consumption of power. Category 1 is domestic users, category 2 is educational institutions, category 3 is commercial institutions and category 4 is industries. The tariff for energy consumption is Re.1.00 / unit for category 1, Rs.1.75 / unit for category 2, Rs. 2.50 / unit for category 3 and Rs.3.00 / unit for category 4\. Write a program to calculate electricity charges for the following data:

![](images/00068.jpeg)

Program 6.1T![](images/00013.jpeg)

/* -------------------------------------------------------

This program calculates the electricity charges

for different categories of consumers.

This program requires jdk1.6 or higher

ka.somasundaram@gmail.com

------------------------------------------------------- */

import java.io.Console;

class TIO61 {

public static void main(String args []){

Console con=System.console();

int maxcol=40;

String consumers [] =

{

“Raman”,

“Balaji”,

“Public School”,

“ABC Hardware”,

“RMK Industry”

};

int units [] ={ 75, 250,800,550,12450};

int conscat [] = {1,1,2,3,4};

int noc = consumers.length;

int i;

double bill = 0;

//Calculate the electricity charges

for (i = 0; i < maxcol; i++)

System.out.print(“–”);

con.printf(“\n”);

con.printf(“%10s %10s %8s %8s%n”,

“Consumer”,”Category”,”Units”,”Charges”);

for (i = 0; i < maxcol; i++)

con.printf(“–”);

con.printf(“\n”);

for (i = 0; i < noc; i++)

{

switch (conscat[i])

{

case 1:

bill = units[i] * 1.0;

break;

case 2:

bill = units[i] * 1.75;

break;

case 3:

bill = units[i] * 2.5;

break;

case 4:

bill = units[i] * 3.0;

break;

default:

con.printf(“Category mismatch”);

}

con.printf(“%–12s\t%1d\t %5d \t%7.1f%n”,

consumers[i], conscat[i], units[i], bill);

}

for (i = 0; i < maxcol; i++)

con.printf(“–”);

con.printf(“%n”);

}

}

The above program gives the following output shown in Fig. 6.9.

![](images/00069.jpeg)

**Fig. 6.9** Output screen for program 6.1T

Problem 6.2T

The runs scored by 5 batsmen in 4 cricket matches played in different cities are given below. Find out the total and average runs scored by each player. Find out the player who scored the highest total.

![](images/00070.jpeg)

Program 6.2T![](images/00013.jpeg)

/* ---------------------------------------------------------------------

This program finds the total score, average score and highest scorer of 5

cricket players for games played at 4 different places.

ka.somasundaram@gmail.com

--------------------------------------------------------------------- */

import java.io.Console;

class TIO62 {

public static void main(String args[]) {

String players[] = {

“Dhoni”,

“Sachin”,

“Kohli”,

“Jadeja”,

“Vijay”

};

String places[] = {

“Delhi”,

“Mumbai”,

“Kolkata”,

“Chennai”

};

int scores[][] = {

{45, 75, 51, 40, 35},

{130, 170, 45, 70, 90},

{10, 60, 125, 65, 55},

{75, 55, 65, 40, 120}

};

Console con = System.console();

int row, column;

row = scores.length;

column = scores[0].length;

int total[] = new int[column];

int average[] = new int[column];

int maxscore, maxcol = 45;

String maxplayer;

//Print out the score details

for (int i = 0; i < maxcol; i++) {

con.printf(“–”);

}

con.printf(“%n”);

for (int i = 0; i < players.length; i++) {

con.printf(“\t%6s”, players[i]);

}

con.printf(“%n”);

for (int i = 0; i < maxcol; i++) {

con.printf(“–”);

}

con.printf(“%n”);

// Print out the scores

for (int i = 0; i < row; i++) {

System.out.print(places[i] + “\t”);

for (int j = 0; j < column; j++) {

con.printf(“%3d \t”, scores[i][j]);

}

con.printf(“%n”);

}

// Find the total scores for each player

for (int j = 0; j < column; j++) {

for (int i = 0; i < row; i++) {

total[j] = total[j] + scores[i][j];

}

}

// Print out the total scores

for (int i = 0; i < maxcol; i++) {

con.printf(“–”);

}

con.printf(“%n”);

con.printf(“Total \t”);

for (int j = 0; j < column; j++) {

con.printf(“%3d \t”, total[j]);

}

con.printf(“%n”);

for (int i = 0; i < maxcol; i++) {

con.printf(“–”);

}

con.printf(“%n”);

// Find the average and print it out

for (int j = 0; j < column; j++) {

average[j] = total[j] / row;

}

con.printf(“Avg “);

for (int j = 0; j < column; j++) {

con.printf(“%3d \t”, average[j]);

}

con.printf(“%n”);

for (int i = 0; i < maxcol; i++) {

con.printf(“–”);

}

con.printf(“%n”);

//Find the highest scorer

maxscore = 0;

maxplayer = “ “;

for (int i = 0; i < column; i++) {

if (total[i] > maxscore) {

maxscore = total[i];

maxplayer = players[i];

}

}

con.printf(“Highest scorer is %6s who scored a total of

%4d%n”, maxplayer, maxscore);

}

}

The above program gives the following output shown in Fig. 6.10.

![](images/00071.jpeg)

**Fig. 6.10** Output screen for program 6.2T

Problem 6.3T

Check out whether the words given below are palindromes (words when arranged in reverse order give the same words).

manmohan
madam
malayalam

Program 6.3T![](images/00013.jpeg)

/* ----------------------------------------------------------------

This program checks whether the given word is palindrome or not.

This program requires jdk1.6 or higher

ka.somasundaram@gmail.com

------------------------------------------------------------------*/

import java.io.Console;

class TIO63 {

public static void main(String args [])

{

char words [][] =

{

{‘m’, ‘a’, ‘n’, ‘m’, ‘o’, ‘h’, ‘a’, ‘n’ },

{‘m’, ‘a’, ‘l’, ‘a’, ‘y’, ‘a’, ‘l’, ‘a’, ‘m’},

{ ‘m’, ‘a’, ‘d’, ‘a’, ‘m’ }

};

int i, j, n, wordlen;

int wordcount = words.length;

int charcount;

Console con=System.console();

// Print out the given words

con.printf(“The given words are: %n”);

for (i = 0; i < wordcount; i++)

con.printf(“%10s”,(new String(words[i])) );

con.printf(“%n%n”);

con.printf(“ Result of Palindrome test%n”);

// Test for palindrome

for (i = 0; i < wordcount; i++)

word:

{

charcount = words[i].length;

for (j = 0, n = charcount – 1; j < n; j++, n––)

if (words[i][j] != words[i][n])

{

con.printf(“ %–10s is NOT a

palindrome%n”,(new String(words[i])));

break word;

}

con.printf(“ %–10s is a PALINDROME%n”,(new String(words[i])) );

}

}

}

The above program gives the following output shown in Fig. 6.11.

![](images/00072.jpeg)

**Fig. 6.11** Output screen for program 6.3T

Problem 6.4T

Write a program to transpose the matrix:

![](images/00073.jpeg)

Program 6.4T![](images/00013.jpeg)

/* ------------------------------------------------------

This program is to transpose the given matrix.

This program requires jdk1.6 or higher

ka.somasundaram@gmail.com

--------------------------------------------------------*/

import java.io.Console;

class TIO64 {

public static void main(String args []) {

int cmat [][] = {

{ 5, 10, 12, 3 },

{ 25, 7, 8, 9 },

{ 12, 6, 13, 35 },

{ 11, 4, 7, 10 }

};

int row = cmat.length;

int column = cmat[0].length;

int trancmat [][] = new int[column][row];

int i, j;

Console con=System.console();

// Print the given matrix

con.printf(“The given matrix%n%n”);

for (i = 0; i < row; i++)

{

for (j = 0; j < column; j++)

{

trancmat[j][i] = cmat[i][j];

con.printf(“%3d “ , cmat[i][j]);

}

con.printf(“%n %n”);

}

// The transpose of the matrix

con.printf(“The Transpose of the matrix%n%n”);

for (i = 0; i < row; i++)

{

for (j = 0; j < column; j++)

con.printf(“%3d “ , trancmat[i][j]);

con.printf(“%n%n”);

}

}

}

The above program gives the following output shown in Fig. 6.12.

![](images/00074.jpeg)

**Fig. 6.12** Output screen for program 6.4T

EXERCISE–6

**I. Fill in the blanks**

6.1 Array is a collection of .......................... data.

6.2 In Java, array is treated as an .......................... .

6.3 .......................... operator is used to create an array.

6.4 Multi-dimensional arrays can have .......................... columns(elements).

6.5 When an array is declared with initial values, the new operator is .......................... .

6.6 The Java class used for handling arrays is .......................... .

**II. Write Java programs for the following:**

6.7 Write a Java program to find the largest value from a set of given integers.

6.8 Write a Java program that finds the sum of each column of a 5 × 4 matrix of integer values.

6.9 Write a Java program that finds the largest element of each row of a matrix of double type values.

6.10Write a Java program to find the determinant of the given matrix of 4 × 4 elements.

7ClassesIn this chapter, the basic concepts of classes are explained. This is the beginning of object-oriented programming. How to define a class and how to create an object are discussed. One way of realising polymorphism exhibited through overloading methods, is explained.

Classes are the basic building blocks for object-oriented programming in Java. A class defines the data, how it is accessed and the method that manipulates the data. A class is like the blueprint of a building. Buildings are built as per the description of the blueprint. In a similar way, objects are created from classes. An Object is an instance of a class. Any given problem is treated as a collection of objects. Data defined in any object can be accessed and manipulated only through the methods defined in it. There is no other way to modify individual data defined in an object. Objects can send/receive messages to/from other objects. These messages help to get services from other objects. A user can create, depending on the problem, any number of classes and hence objects. Consider that there is a blueprint for a building. You can build a house as per the specifications in the blueprint. Your house is one instance for the blueprint. Your friend, Raman, wants to build a house like yours. He can also build a house using the same blueprint. Raman’s house is another instance of the blueprint. Another friend, Sharma, wants to build a house like yours. He can also build a house using the same blueprint. This is yet another instance for the blueprint. You might have noticed that governments and cooperative societies have built hundreds of identical houses from the same blueprint. Classes are, in this respect, like the blueprint and each object is like the houses.

It is possible in procedure-oriented languages like FORTRAN, C, Pascal, etc. to access a common data by any module or subprogram and modify it. However, Java’s data encapsulation features do not permit any module to access the data arbitrarily. Only methods defined in that object can be called and the data be modified.

![](images/00011.jpeg)Classes define the data, how it is accessed and the methods that manipulate the data.

![](images/00075.jpeg)

**Fig. 7.1** Houses are built using a blueprint

![](images/00076.jpeg)

**Fig. 7.2** Objects are instance of a class

Java has several thousand pre-defined classes for use. Java programmers can make use of Java classes for various purposes. In addition, programmers can create their own classes.

7.1 DEFINING A CLASS

A class defines the data types used and the methods that manipulate them. The variables declared in a class are called instance variables. A class can contain any number of methods, which are used to manipulate the data and carry out a specific computation. The general form of declaring a class is:

class classname extends Superclassname {

type instance-variable-1;

type instance-variable-2;

type instance-variableN;

return-type methodname1(parameter_list1) {

body1;

}

return_type methodname2 (parameter_list2) {

body2;

}

return_type methodnameN(parameter_listN) {

bodyN;

}

}

Classname is a user-defined class name. The name can be coined using the same rules to form a variable. **extends** is a Java reserved keyword and is optional. Superclassname is the name of the parent class from which this class is derived. The instance-variable1 and the other two are instance variables of the type **type**. Methodname1 is the name of the method, which, when executed, will return a data of return-type. body1, body2, bodyN are Java statements. Parameterlist1, 2, N are the list of parameters passed to the methods methodname1, methodname2 and methodnameN as arguments.

An example of a simple class is given below:

class Address {

String name, city;

int pin;

}

In the above example, Address is the name of the class. By convention, all class names start with uppercase followed by lowercase and numbers. The subsequent words will start with uppercase letters. name, city and pin are instance variables.

7.2 THE new OPERATOR AND OBJECTS

A Java object is one instance of a class. An object is created from a class using the **new** operator. The **new** operator creates an object and returns an object reference. This reference points to the object. The object reference can be stored in a variable. Variables that store object references are called object reference variables. The type of the object reference variable is of the class type. Consider the following statement:

Address adrs = new Address();

The variable adrs is the object reference variable whose type is Address. The **new** operator creates an object of type Address and returns the object reference, which is stored in adrs.

![](images/00077.jpeg)

**Fig. 7.3** Class, new operator and object

A class, except in a few cases, cannot be used as such. Only instances of the class can be used. The object reference variable adrs contains a reference pointing to the Address object and does not contain any data pertaining to the object. When you copy one object reference variable to another object reference variable, no object is created, but another copy of the reference is created, which again points to the same object. The following statement creates another copy of the object reference variable adrs.

Address adrs1 = adrs;

![](images/00078.jpeg)

**Fig. 7.4** A copy of object reference variable

When adrs is printed, only the object reference 3B75 is printed and not the content of the object.

![](images/00011.jpeg)An object is an instance of a class.

7.3 THE dot(.) OPERATOR

The dot operator (.) is used to access the instance variables and methods defined in that object. The general form of using the dot operator is:

Object.instance_variable

The following program 7.1 illustrates the use of dot operator:

Program 7.1![](images/00013.jpeg)

/* This program requires jdk1.6 or higher.

This program illustrates how to declare a class and

assign values to the instance variables

ka.somasundaram@gmail.com

*/

import java.io.Console;

class Address {

String nam, city;

int pin;

}

class ClassDemo {

public static void main(String args[]) {

Console con = System.console();

//Create the Address object

Address adrs = new Address();

//assign values to instance variables

adrs.nam = “Dr.K.Somasundaram”;

adrs.city = “Ambathurai”;

adrs.pin = 624302;

//Print the values

con.printf(“ Name:%12s%n”, adrs.nam);

con.printf(“ City: %8s%n”, adrs.city);

con.printf(“ PIN Code: %d%n”, adrs.pin);

}

}

The above program gives the following output shown in Fig. 7.1.

![](images/00079.jpeg)

**Fig. 7.1** Output screen for program 7.1

7.4 METHOD DECLARATION AND CALLING

Methods are declared inside a class. Each method performs a specific task. The data associated with the instance variable is manipulated by the methods. The methods may directly output the result or return a value to the calling section.

The general form of declaring a method is:

return_type methodname (parameterlist){
body;
return expression;
}

Here methodname is the name of the method and is coined by using the rules to form a variable name, return-type is the type returned by the method through the expression and parameterlist is the list of formal parameters passed as arguments to the method and body is the Java statements.

A method can be called only on its object. However, methods declared as static can be called directly independent of an object. The general form of calling a method is:

Object.methodname(parameter-list);

![](images/00011.jpeg)In most cases, a method is called on its object.

The following program 7.2 declares a class with a method to assign initial values to the instance variables through a method. Later, it is called on the object to assign the actual values.

Program 7.2![](images/00013.jpeg)

/* This program requires jdk1.6 or higher.

This program illustrates how to declare and call a method

ka.somasundaram@gmail.com

*/

import java.io.Console;

class Address {

String nam, city;

int pin;

void Assign(String nm, String cty, int pn) {

nam = nm;

city = cty;

pin = pn;

}

}

class Method {

public static void main(String args[]) {

Console con = System.console();

//Create the Address object

Address adrs = new Address();

//assign values to instance variables

adrs.Assign(“Dr.K.Somasundaram”, “Ambathurai”,

624302);

//Print the values

con.printf(“ Name:%12s%n”, adrs.nam);

con.printf(“ City: %8s%n”, adrs.city);

con.printf(“ PIN Code: %d%n”, adrs.pin);

}

}

The above program gives the following output as shown in Fig. 7.2.

![](images/00080.jpeg)

**Fig. 7.2** Output screen for program 7.2

In the above program 7.2, the Address class can be kept in a separate file Address.java and compiled. Then the Method class can be written separately in the same directly and executed.

7.5 CONSTRUCTORS

A constructor is used to assign initial values to an object when it is created. In many cases, initial values are needed for instance variables. In the previous section 7.4, we have seen that a method was used to initialize instance variables. Using constructors, instance variables can be assigned initial values automatically when an object is created. Constructors are special methods. The name of the constructor shall be the same as the name of the class itself. There can be any number of constructors in a class. The general form of declaring a constructor is:

class classname {
type instance variable;
classname(parameter-list1) {
body1;
}
classname(parameter-list2) {
body2;
}
type methodname(parameter-list3) {
body;
}
}

The following program 7.3 illustrates the use of constructor:

Program 7.3![](images/00013.jpeg)

/*This program shows how to define a constructor

This program requires jdk1.6 or higher.

ka.somasundaram@gmail.com

*/

import java.io.Console;

class Address {

String nam, city;

int pin;

//define a constructor

Address(String nm, String cty, int pn) {

nam = nm;

city = cty;

pin = pn;

}

}

class Constructor {

public static void main(String args[]) {

Console con = System.console();

//Create the Address object

Address adrs = new Address(“Dr.K.Somasundaram”,

“Ambathurai”, 624302);

con.printf(“ Name:%12s%n”, adrs.nam);

con.printf(“ City: %8s%n”, adrs.city);

con.printf(“ PIN Code: %d%n”, adrs.pin);

}

}

The above program gives the same output as that of program 7.2.

In program 7.3, the address details are printed by accessing individual values. Now we will add a method in the Address class that prints the address values. Program 7.4 illustrates a class with a constructor and a method.

Program 7.4![](images/00013.jpeg)

/*This program shows how to define a constructor

This program requires jdk1.6 or higher for compile and execute.

ka.somasundaram@gmail.com

*/

import java.io.Console;

class Address {

Console con = System.console();

String nam, city;

int pin;

//define a constructor

Address(String nm, String cty, int pn) {

nam = nm;

city = cty;

pin = pn;

}

//Declare a method to print address

void Printadrs() {

con.printf(“Name:%20s%n City :%12s%n PIN Code :

%8d%n”, nam, city, pin);

}

}

class ConstMethod {

public static void main(String args[]) {

//Create the Address object

Address adrs = new Address(“Dr.K.Somasundaram”,

“Ambathurai”, 624302);

//Call the Printadrs method

adrs.Printadrs();

}

}

The output of the above program is shown in Fig. 7.3.

![](images/00081.jpeg)

**Fig. 7.3** Output screen for program 7.4

7.6 INSTANCE VARIABLE HIDING

In declaring methods and constructors, parameters are used as arguments. The name of parameters are generally different from that of the instance variables. However, Java allows parameters and instance variables to have the same name. In order to identify instance variables from formal parameters, the key word **this** is used. **this** refers to the current class. The following program 7.5 illustrates the use of **this** in a class:

Program 7.5![](images/00013.jpeg)

/*This program shows how to use this keyword

This program requires jdk1.6 or higher.

ka.somasundaram@gmail.com

*/

import java.io.Console;

class Address {

Console con = System.console();

String nam, city;

int pin;

//define a constructor

Address(String nam, String city, int pin) {

this.nam = nam;

this.city = city;

this.pin = pin;

}

//Declare a method to print address

void Printadrs() {

con.printf(“ Name:%20s%n City :%12s%n PIN Code

:%8d%n”, nam, city, pin);

}

}

class ThisDemo {

public static void main(String args[]) {

//Create the Address object

Address adrs = new Address(“Dr.K.Somasundaram”,

“Ambathurai”, 624302);

//Call the Printadrs method

adrs.Printadrs();

}

}

The above program gives the same output as shown in Fig. 7.3.

Constructors with different parameter list is called constructor overloading.

![](images/00011.jpeg)Constructors are used to initialize the instance variable.

The following program 7.6 is an example for constructor overloading.

Program 7.6![](images/00013.jpeg)

/*This program shows constructor overloading

This program requires jdk1.6 or higher.

ka.somasundaram@gmail.com

*/

import java.io.Console;

class Address {

Console con = System.console();

String nam, city;

int pin;

//define a constructor

Address(String nm, String cty, int pn) {

nam = nm;

city = cty;

pin = pn;

}

//Second constructor

Address() {

nam = “Indian”;

city = “India”;

pin = 100000;

}

//Declare a method to print address

void Printadrs() {

con.printf(“ Name:%20s%n City :%12s%n PIN Code

:%8d%n”, nam, city, pin);

}

}

class Constovrload {

public static void main(String args[]) {

//Create the Address object

Address adrs1, adrs2;

adrs1 = new Address(“Dr.K.Somasundaram”,

“Ambathurai”, 624302);

adrs2 = new Address();

adrs1.Printadrs();

adrs2.Printadrs();

}

}

The above program gives the following output as shown in Fig. 7.4.

![](images/00082.jpeg)

**Fig. 7.4** Output screen for program 7.6

7.7 this IN A CONSTRUCTOR

One constructor of a class can refer to another constructor of the same class through the keyword **this**. The following program 7.7 illustrates the use of **this** to refer another constructor of the same class:

Program 7.7![](images/00013.jpeg)

/*This program shows the use of keyword this in

constructors

This program requires jdk1.6 or higher for compile and

execute.

ka.somasundaram@gmail.com

*/

import java.io.Console;

class Address {

Console con = System.console();

String nam, city;

int pin;

//First constructor

Address(String nm, String cty, int pn) {

nam = nm;

city = cty;

pin = pn;

}

//Second constructor refers to the first constructor

Address(Address obj) {

this(obj.nam, obj.city, obj.pin);

}

//Declare a method to print address

void Printadrs() {

con.printf(“Name:%20s%n City :%12s%n PIN Code

:%8d%n”, nam, city, pin);

}

}

class ConstThis {

public static void main(String args[]) {

//Create the Address object

Address adrs1, adrs2;

adrs1 = new Address(“Dr.K.Somasundaram”,

“Ambathurai”, 624302);

adrs2 = new Address(adrs1);

adrs1.Printadrs();

adrs2.Printadrs();

}

}

The above program gives the following output shown in Fig. 7.5.

![](images/00083.jpeg)

**Fig. 7.5** Output screen for program 7.7

Having seen simple methods and constructors, we will now consider a method that does some computing and returns a value to the calling section. The following program 7.8 calculates the area of the rectangle through the Area method:

Program 7.8![](images/00013.jpeg)

/*This program illustrates the use of methods in a class.

This program requires jdk1.6 or higher for compile and execute.

ka.somasundaram@gmail.com

*/

import java.io.Console;

class Rectangle {

double lenth, breadth;

double Area(double l, double b) {

lenth = l;

breadth = b;

return lenth * breadth;

}

}

class Rectarea1 {

public static void main(String args[]) {

double len, br, rec_area;

String slen, sbr;

Console con = System.console();

Rectangle rec = new Rectangle();

con.printf(“ Type in the length: “);

slen = con.readLine();

len = Double.parseDouble(slen);

con.printf(“ Type in the breadth: “);

sbr = con.readLine();

br = Double.parseDouble(sbr);

rec_area = rec.Area(len, br);

con.printf(“ Length = %6.2f\n”, rec.lenth);

con.printf(“ Breadth = %6.2f\n”, rec.breadth);

con.printf(“ Area of rectangle = %6.2f\n”,

rec_area);

}

}

The above program gives the following output as shown in Fig. 7.6.

![](images/00084.jpeg)

**Fig. 7.6** Output screen for program 7.8

The above program 7.8 can also be written in another form as shown in program 7.9.

Program 7.9![](images/00013.jpeg)

/*This program illustrates the use of methods in a class.

This program requires jdk1.6 or higher for compile and execute.

ka.somasundaram@gmail.com

*/

import java.io.Console;

class Rectangle {

double lenth, breadth;

Rectangle(double l, double b) {

lenth = l;

breadth = b;

}

double Area() {

return lenth * breadth;

}

}

class Rectarea2 {

public static void main(String args[]) {

double len, br, rec_area;

String slen, sbr;

Rectangle rec;

Console con = System.console();

con.printf(“ Type in the length: “);

slen = con.readLine();

len = Double.parseDouble(slen);

con.printf(“ Type in the breadth: “);

sbr = con.readLine();

br = Double.parseDouble(sbr);

rec = new Rectangle(len, br);

rec_area = rec.Area();

con.printf(“ Length = %6.2f%n”, rec.lenth);

con.printf(“ Breadth = %6.2f%n”, rec.breadth);

con.printf(“ Area of rectangle = %6.2f%n”,

rec_area);

}

}

The result for the above program 7.9 is the same as that of the previous program 7.8.

Now, we will add one more method in program 7.8 to calculate the circumference of the rectangle. The program 7.10 calculates area and circumference of a rectangle.

Program 7.10![](images/00013.jpeg)

/*This program illustrates the use of two methods in a

class.

This program requires jdk1.6 or higher for compile and

execute.

ka.somasundaram@gmail.com

*/

import java.io.Console;

class Rectangle {

double lenth, breadth;

Rectangle(double l, double b) {

lenth = l;

breadth = b;

}

double Area() {

return lenth * breadth;

}

double Circum() {

return 2 * (lenth + breadth);

}

}

class Rectarea3 {

public static void main(String args[]) {

double len, br, rec_area, rec_circum;

String slen, sbr;

Console con = System.console();

con.printf(“ Type in the length: “);

slen = con.readLine();

len = Double.parseDouble(slen);

con.printf(“ Type in the breadth: “);

sbr = con.readLine();

br = Double.parseDouble(sbr);

Rectangle rec = new Rectangle(len, br);

rec_area = rec.Area();

rec_circum = rec.Circum();

con.printf(“Length = %6.2f%n”, rec.lenth);

con.printf(“Breadth = %6.2f%n”, rec.breadth);

con.printf(“Area of rectangle = %6.2f%n”, rec_area);

con.printf(“Circumference of rectangle =

%6.2f%n”, rec_circum);

}

}

The above program gives the following output shown in Fig. 7.7.

![](images/00085.jpeg)

**Fig. 7.7** Output screen for program 7.10

7.8 METHOD OVERLOADING

A class can contain any number of methods. Methods can take parameters as input for data manipulation. These parameters are called type signature. Java permits many methods to have the same name, but with different type signatures. This way of methods having the same name, but with different type signature is known as method overloading.

![](images/00011.jpeg)Methods of a class with the same name but with different type signature are called overloading methods. Overloading methods exhibit the concept of polymorphism.

The following program 7.11 illustrates the use of method overloading. The following program contains a class with two methods with the same name Area but with different type signature. When two parameters are given, one method finds the area of a rectangle and for a single parameter another one finds the area of a square.

Program 7.11![](images/00013.jpeg)

/* This program illustrates method overloading.

* This program requires jdk1.6 or higher for compile and execute.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Rectangle {

double lenth, breadth;

double Area(double l, double b) {

lenth = l;

breadth = b;

return lenth * breadth;

}

double Area(double a) { //overloading method

lenth = breadth = a;

return lenth * breadth;

}

}

class Overload {

public static void main(String args[]) {

double len, br, area;

String slen, sbr;

Console con = System.console();

Rectangle rec = new Rectangle();

con.printf(“ Type in the length: “);

slen = con.readLine();

len = Double.parseDouble(slen);

con.printf(“ Type in the breadth: “);

sbr = con.readLine();

br = Double.parseDouble(sbr);

area = rec.Area(len, br);

con.printf(“ Length = %6.2f%n”, rec.lenth);

con.printf(“ Breadth = %6.2f%n”, rec.breadth);

con.printf(“ Area of rectangle = %6.2f%n”, area);

con.printf(“ Type in the width of the square: “);

slen = con.readLine();

len = Double.parseDouble(slen);

area = rec.Area(len);

con.printf(“ Area of square = %6.2f%n”, area);

}

}

The above program gives the following output shown in Fig. 7.8.

![](images/00086.jpeg)

**Fig. 7.8** Output screen for program 7.11

7.9 PASSING OBJECTS AS PARAMETER TO METHODS

We have seen that methods in a class can take parameters as inputs and process them. Objects can also be passed as parameters to the methods. The following program 7.12 contains methods that take object as a parameter:

Program 7.12![](images/00013.jpeg)

/* This program illustrates the passing of object as parameter to a method.

* This program requires jdk1.6 or higher for compile and execute.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Circle {

double radius;

// Take the PI value from Math class

double PHI = Math.PI;

Circle(double r) {

radius = r;

}

double Area(Circle obj) {

return PHI * obj.radius * obj.radius;

}

}

class Objectparam {

public static void main(String args[]) {

double r, area;

String sr;

Console con = System.console();

con.printf(“Type in the radius: “);

sr = con.readLine();

r = Double.parseDouble(sr);

Circle cr = new Circle(r);

area = cr.Area(cr);

con.printf(“Area of circle = %6.2f%n”, area);

}

}

The above program gives the following output shown in Fig. 7.9.

![](images/00087.jpeg)

**Fig. 7.9** Output screen for program 7.12

In the above program 7.12, we have seen that an object is passed as reference to access the values of the parameters. This method of passing parameters is known as passing by reference, as the object reference variable contains only reference to the object. When arguments are passed as values, it is known as passing by value. Passing of the parameters in the earlier programs was done through passing by value.

7.10 PASSING ARRAY AS PARAMETER TO METHOD

An array can also be passed as a parameter to a method. In fact, an array is treated as an object. The following program 7.13, illustrates a method taking up an array as parameter. The method sort() takes an array as a parameter, sorts it and returns the sorted array.

Program 7.13![](images/00013.jpeg)

/* --------------------------------------------------------------

This program shows how to pass an array as parameter to a method.

This program requires jdk1.6 or higher.

ka.somasundaram@gmail.com

---------------------------------------------------------------- */

import java.io.Console;

class Order {

int temp, i, j;

//Method takes an array ,sort it and return the sorted array

int[] Sort(int ary[]) {

int len = ary.length;

for (i = 0; i < len; i++) {

for (j = i + 1; j < len; j++) {

if (ary[j] > ary[i]) {

temp = ary[i];

ary[i] = ary[j];

ary[j] = temp;

}

}

}

return ary;

}

}

class Arrayparam {

public static void main(String args[]) {

int mark[] = {35, 25, 76, 89, 76, 65, 81, 63, 41};

//find the no of elements in the array

int maxn = mark.length;

Console con = System.console();

// Print out the given numbers

con.printf(“The given numbers %n%n”);

for (int i = 0; i < maxn; i++) {

con.printf(“%d “, mark[i]);

}

con.printf(“%n”);

// call the Sort method of Order class

Order ord = new Order();

mark = ord.Sort(mark);

// Print the sorted numbers

con.printf(“%n”);

con.printf(“The sorted numbers%n%n”);

for (int i = 0; i < maxn; i++) {

con.printf(“%d “, mark[i]);

}

}

}

The above program gives the following output shown in Fig. 7.10.

![](images/00088.jpeg)

**Fig. 7.10** Output screen for program 7.13

After reading this chapter, you should have learned the following:

*   Classes define data and method.
*   Object is an instance of a class.
*   Constructors are methods used to initialize variables of an object.
*   Methods with same name but with different type signature are called overloading methods.
*   Overloading methods exhibit polymorphism property.
*   When a method takes values, as parameters, it is called passing by value.
*   When a method takes reference, like object or array, as parameter, it is called as passing by reference.

In the next chapter, you will learn about inheritance.

![](images/00053.jpeg)

Problem 7.1T

A hardware shop adds a certain tax on any sales made. It gives a certain percentage of cash discount in the total cost depending on the product. Write a Java program to calculate the total cost, discount and the net amount a customer has to pay for the following data:

![](images/00089.jpeg)

Program 7.1T![](images/00013.jpeg)

/* This program shows how to calculate the tax and

* discount for sales made in a shop.

* This program requires jdk1.6 or higher for compile and execute.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Sales {

double cost, tax, total, discount, net;

double tr, dc;

Sales(double p, double txrate, double dis) {

cost = p;

tr = txrate;

dc = dis;

}

double Tax() {

tax = cost * tr / 100.0;

return tax;

}

double Total() {

total = cost + tax;

return total;

}

double Discount() {

discount = total * dc / 100.0;

return discount;

}

double Net() {

return (total – discount);

}

}

class TIO71 {

public static void main(String args[]) {

double rtax, rdiscount;

Console con = System.console();

Sales s1;

double data[][] = {{586.0, 8.5, 2.0}, {2475.0,

12.0, 7, 5}, {725.0, 9.5, 3.0}};

int len = data.length;

int maxcol = 45;

for (int i = 0; i < maxcol; i++) {

con.printf(“-”);

}

con.printf(“%n”);

con.printf(“%-8s %-8s %-8s %-8s %-8s%n”, “Sales”,

“Tax”, “Total”, “Discount”, “Net “);

for (int i = 0; i < maxcol; i++) {

System.out.print(“-”);

}

con.printf(“%n”);

for (int i = 0; i < len; i++) {

s1 = new Sales(data[i][0], data[i][1], data[i][2]);

con.printf(“%7.2f %7.2f %7.2f %7.2f

%7.2f%n”, s1.cost, s1.Tax(), s1.Total(),

s1.Discount(), s1.Net());

}

for (int i = 0; i < maxcol; i++) {

con.printf(“-”);

}

con.printf(“%n”);

}

}

The above program gives the following output shown in Fig. 7.11.

![](images/00090.jpeg)

**Fig. 7.11** Output screen for program 7.1T

Problem 7.2T

Write a Java program for problem 5.1T using separate methods for Sin(x), Cos(x) and factorial calculation.

Program 7.2T![](images/00013.jpeg)

/* ---------------------------------------------------------------------

This program calculates the sin(x) and cos(x) functions by computing the

sin series and cos series functions. The results are compared with the

results obtained by using

Java sin and cos.

ka.somasundaram@gmail.com

----------------------------------------------------------------------*/

import java.io.Console;

class Trigno {

double x;

int i, n = 5;

long factn;

Console con = System.console();

Trigno(double x) {

this.x = x;

}

long Factfun(int nmax) {

long fact = 1;

for (i = 2; i <= nmax; i++) {

fact *= i;

}

return fact;

}

double Sinfun() {

double six = x;

for (int k = 1; k <= n; k++) {

factn = Factfun(2 * k + 1);

six = six + Math.pow(–1, k) * Math.pow(x, (2 *

k + 1)) / factn;

}

return six;

}

double Cosfun() {

double cox = 1;

for (int k = 1; k <= n; k++) {

factn = Factfun(2 * k);

cox = cox + Math.pow(–1, k) * Math.pow(x, 2 *

k) / factn;

}

return cox;

}

void Printline(int p) {

for ( i = 1; i <= p; i++) {

con.printf(“-”);

}

con.printf(“%n”);

}

}

class TIO72 {

public static void main(String args[]) {

double x, sinx, cosx, jsx, jcx;

Trigno trg;

int maxcol = 35;

Console con = System.console();

trg = new Trigno(0);

trg.Printline(maxcol);

con.printf(“%-6s %-6s %-6s %-6s %-6s %n”, “ x “,

“my sinx”, “Java”, “my cosx”, “Java”);

trg.Printline(maxcol);

for (x = 0; x < 1.6;) {

trg = new Trigno(x);

sinx = trg.Sinfun();

cosx = trg.Cosfun();

jsx = Math.sin(x);

jcx = Math.cos(x);

con.printf(“%6.3f %6.3f %6.3f %6.3f %6.3f %n”,

x, sinx, jsx, cosx, jcx);

x = x + 0.5;

}

trg.Printline(maxcol);

}

}

The above program gives the following output shown in Fig. 7.12.

![](images/00091.jpeg)

**Fig. 7.12** Output screen for program 7.2T

Problem 7.3T

A bank, in one scheme, gives a compound interest of 7.0% per annum for deposits made in that bank. Write a program to calculate the total amount a customer gets after n years for a deposit of Rs. x. Get the values from keyboard. Use a method to compute the interest.

Total amount for an amount P, for N years, with an interest rate R is given by

Total = P(1+r/100)^N

Program 7.3T![](images/00013.jpeg)

/* ---------------------------------------------------------------------

This program calculates the total amount a customer will get for a deposit

of X rupees in compound interest for N years.

This program requires jdk1.6 or higher

ka.somasundaram@gmail.com

----------------------------------------------------------------------*/

import java.io.Console;

class Deposit {

int principal, year;

int simple, compound;

double rate=7.0;

Deposit(int prin, int yr) {

principal = prin;

year = yr;

}

int Compound() {

compound = (int)(principal * Math.pow((1 + rate /

100), year));

return compound;

}

}

class TIO73 {

public static void main(String args []){

Console con=System.console();

int pa, yrs, tot;

String spa, syrs;

con.printf(“Type in the principal amount:”);

spa=con.readLine();

pa=Integer.parseInt(spa);

con.printf(“How many years?:”);

syrs=con.readLine();

yrs=Integer.parseInt(syrs);

Deposit depo = new Deposit(pa, yrs);

tot=depo.Compound();

con.printf(“Amount after %2d years = Rs.%,5d %n”, yrs,tot);

}

}

The above program gives the following output shown in Fig. 7.13.

![](images/00092.jpeg)

**Fig. 7.13** Output screen for program 7.3T. The comma(,) specified in the format specifier %,6d is to introduce comma(,) in the numerical value.

EXERCISE–7

**I. Fill in the blanks**

7.1 A .......................... defines the data and the methods used to manipulate them.

7.2 A .......................... is like the blueprint for a building.

7.3 An instance of a class is ........................... .

7.4 The variable defined in a class is called .......................... variable.

7.5 The .......................... operator creates an object and returns a .......................... to the object.

7.6 A variable that stores the object reference is called .......................... .

7.7 When an object reference variable is printed, only the .......................... is printed and not the content of the object.

7.8 The instance variable of a class can be accessed using the .......................... operator.

7.9 A special type of method that is used to initialize an object is called .......................... .

7.10The name of the class and the name of the constructor must be the same. (True / False)

7.11The key word this in a class can be used to refer to a .......................... in the same class.

7.12When one or more methods have the same name but with different parameters, then the methods are called .......................... methods.

7.13The type signature of a method refers to the .......................... passed to the method.

**II. Write Java programs for the following problems:**

7.14A mark list contains a register number, name and marks for sub1, sub2 and sub3\. Write a Java class to define them.

7.15Add a method to the class defined in problem 7.14 to find the average of the three subjects and print out the average value.

7.16Write a constructor to initialize all the variables of the class defined in problem 7.14.

7.17The employee list for a company contains employee code, name, designation and basic pay. The employee is given a house rent allowance (HRA) of 10% of the basic pay and dearness allowance (DA) of 45% of the basic pay. The total pay of the employee is calculated as Basic Pay + HRA + DA. Write a class to define the details of the employee. Write a constructor to assign the required initial values. Add a method to calculate HRA, DA and total pay and print them. Write another class with a main method. Create objects for three different employees and calculate the HRA, DA and total pay.

7.18A mark list contains reg.no. and marks for three subjects, sub1, sub2 and sub3\. Write a class to define the mark list. Write a constructor to initialize all the variables. Write a method called Result (int min) where, min indicates the minimum mark for a “Pass” for each subject. This method will declare a candidate as “Pass”, if the candidate secures marks in each subject greater than or equal to min. Write another overloading method Result (int min, int merit), where merit indicates that a candidate who get a “Pass” and average of the three subjects equal to or greater than merit is eligible for getting a scholarship. Write another class with a main method and try the methods for 5 different candidates to determine whether they get “Pass” and also determine whether they are eligible for scholarship.

8InheritanceIn this chapter, inheritance is explained. An existing class can be extended by adding additional capabilities. Such a class is called a subclass. Subclasses inherit all the properties of the parent classes. This process is known as inheritance and is discussed in this chapter.

Sometimes, we need to build a class with added capabilities of an existing class. In such situations, the existing class can be extended to have additional capabilities. Such a class, derived from another class, is called a subclass. The parent class is called superclass. A subclass inherits all instance variables and methods from its superclass and also has its own instance variables and methods. This property of a class inheriting the properties of another class is called inheritance. This principle helps to build classes for complex problems and also avoid the repetition of codes in the new class. To create a subclass, the keyword extends is used in the class definition.

8.1 CREATING SUBCLASSES

Let us assume that we have a class called Address and have a method to print the address as given in program 8.1.

Program 8.1![](images/00013.jpeg)

/*This is a simple class

ka.somasundaram@gmail.com

*/

import java.io.Console;

class Address {

Console con = System.console();

String nam, city;

int pin;

Address(String nm, String cty, int pn) {

nam = nm;

city = cty;

pin = pn;

}

void Printadrs() {

con.printf(“ Name:%20s%n City :%12s%n PIN Code :%8d%n”, nam, city, pin);

}

}

Now, we want to build another class to deal with biodata of a person. We have already the Address class containing part of biodata. Therefore, instead of building an entirely new class to deal bio-data the existing class, Address can be extended. Program 8.2 illustrates the creation of a subclass by extending the Address.

Program 8.2![](images/00013.jpeg)

/*This program illustrates the creation of a subclass

This programm requires jdk1.6 or higher

ka.somasundaram@gmail.com

*/

import java.io.Console;

class Address {

Console con = System.console();

String nam, city;

int pin;

Address(String nm, String cty, int pn) {

nam = nm;

city = cty;

pin = pn;

}

void Printadrs() {

con.printf(“ Name:%20s%n City :%12s%n PIN Code :%8d%n”, nam, city, pin);

}

}

class Biodata extends Address {

String edu;

int age;

Biodata(String nm, String cty, int pn, String ed, int ag) {

super(nm, cty, pn);

edu = ed;

age = ag;

}

void Printbio() {

con.printf(“ Name:%20s%n Qualification: %4s%n Age :%2d%n”, nam, edu, age);

con.printf(“ City :%12s%n PIN Code :%8d%n”, city, pin);

}

}

class Inherit {

public static void main(String args[]) {

Console con = System.console();

Biodata bd = new Biodata(“Dr.K.Somasundaram”, “Ambathurai”, 624302, “Ph.D”, 59);

con.printf(“%n Address of %s%n”, bd.nam);

//Use inherited method to print address

bd.Printadrs();

con.printf(“%n Biodata of %s%n”, bd.nam);

bd.Printbio();

}

}

The above program gives the following output shown in Fig. 8.1.

![](images/00093.jpeg)

**Fig. 8.1** Output screen for program 8.2

In the above program, the keyword **super** refers to the superclass constructor Address(). When **super**() is used inside a constructor, it must be the first statement.

8.2 METHOD OVERRIDING

When subclasses are constructed, they may have their own methods in addition to the inherited methods from superclass. It is possible for methods in subclasses to have the same name and type signature as that of the superclass. In that case, the method in the subclass will override the method in the superclass. This is called method overriding. Method overriding exhibits the full polymorphism property. The following program 8.3 illustrates method overriding.

Program 8.3![](images/00013.jpeg)

/* This program illustrates method overriding concept.

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class A {

double result;

double Process(double x, double y) {

result = x * y;

return result;

}

}

class B extends A {

double Process(double x, double y) {

result = x / y;

return result;

}

}

class Override {

public static void main(String args[]) {

double p = 10.0, q = 4.0, aval, bval;

Console con = System.console();

A a = new A();

B b = new B();

aval = a.Process(p, q);

bval = b.Process(p, q);

con.printf(“\n %4.1f and %4.1f processed in A = %4.1f%n”, p, q, aval);

con.printf(“\n %4.1f and %4.1f processed in B = %4.2f%n “, p, q, bval);

}

}

The above program gives the following output shown in Fig. 8.2.

![](images/00094.jpeg)

**Fig. 8.2** Output screen for program 8.3

In the above program the method Process() produces two different results. The selection of appropriate method is done during run time and is called dynamic method dispatch.

Java supports multi-level inheritance as given below:

![](images/00095.jpeg)

**Fig. 8.3** Multi-level inheritance in Java

Using this principle, subclasses in multilevel can be created.

![](images/00011.jpeg)A method in a subclass having the same name and type signature of a superclass method is called overriding method. Overriding method exhibits polymorphism property.

8.3 FINAL CLASS

Inheritance allows creation of subclasses. However, if need arises, inheritance can be prevented by declaring a class as final. A class declared as **final** cannot have subclasses. The following program 8.4 shows the use of **final** class:

Program 8.4![](images/00013.jpeg)

/* This program illustrates final class.

* This program requires jdk1.6 or higher for compile

and execute.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

// this prevents creation of any subclass of Circle

final class FinCircle {

double radius;

final double PHI = Math.PI;

FinCircle(double r) {

radius = r;

}

double Area() {

return PHI * radius * radius;

}

double Circum() {

return 2 * PHI * radius;

}

}

class FinalClass {

public static void main(String args[]) {

double ar, radius = 5.5, sar;

Console con = System.console();

FinCircle cir = new FinCircle(radius);

ar = cir.Area();

sar = cir.Circum();

con.printf(“\n Radius of the circle = %5.1f\n” radius);

con.printf(“\n Area of the circle = %5.1f\n”, ar);

con.printf(“\n Circumference of the circle = %5.1f\n”, sar);

}

}

The above program gives the following output shown in Fig. 8.4.

![](images/00096.jpeg)

**Fig. 8.4** Output screen for program 8.4

8.4 FINAL METHOD

Methods in a class can be protected from overriding methods in subclasses. Like final classes, methods can be declared with the modifier **final**. Methods declared as **final** cannot have overriding methods in the subclasses. The following program 8.5 illustrates the use of **final** method:

Program 8.5![](images/00013.jpeg)

/* This program illustrates final method.

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class A {

double result;

final double Process(double x, double y) {

result = x * y;

return result;

}

}

class B extends A {

//Overriding is not possible

//double Process(double x, double y) {

double Divide(double x, double y) {

result = x / y;

return result;

}

}

class FinalMethod {

public static void main(String args[]) {

double p = 10.0, q = 4.0, aval, bval;

Console con = System.console();

A a = new A();

B b = new B();

aval = a.Process(p, q);

bval = b.Divide(p, q);

con.printf(“\n %4.1f and %4.1f multiplied in A = %4.1f%n”, p, q, aval);

con.printf(“\n %4.1f and %4.1f divided in B = %4.2f%n “, p, q, bval);

}

}

The above program gives the following output shown in Fig. 8.5.

![](images/00097.jpeg)

**Fig. 8.5** Output screen for program 8.5

So far, all the programs have been written by writing all the classes in the same file. But it is not required to do so. If a class is needed in several programs, it is required to write the class, compile and store in the same directory. That class can be used in any number of classes without actually writing it in the respective programs.

8.5 FINAL VARIABLES

Variables can also be declared as **final**. **final** variables are constants. You cannot assign any new value to them once you have declared them as **final**. **final** variables must be assigned values while declaring them to be **final**. The general form of declaring a **final** variable is:

final type VariableName = Value;

By convention, final variables are declared with uppercase letters. Following are a few examples for final:

| final int PASS_MARK | = 40; |
| final int MINUTE_VAL | = 60; |
| final double INTEREST_RATE | = 12.5; |
| final double UPPER_LIMIT | = 120.25; |
| final double PHI | = 3.142; |

8.6 OBJECT DESTRUCTION AND GARBAGE COLLECTION

When objects are created, they occupy some memory space of the computer. When an object is no more in use, Java identifies them automatically and frees the memory. This is called garbage collection. There is no separate destructor method in Java. In certain situations, objects may use other than memory, like a file or a system resource. In such cases, care must be taken to free those resources before the object is destroyed. In order to provide such a facility, Java has finalize() method. This method can be put inside the class. Before an object is destroyed, Java runs the finalize() method. The user can define whatever action to be taken inside the finalize() method. Though, in most cases, it works, but that is not guaranteed for every time. Therefore, a programmer has to find other means to release the resources from objects marked for destruction.

8.7 RECURSION

When a method calls itself, it is called recursion. There are problems which can be programmed easily using recursion. Recursive methods need stack memory. It is inefficient in terms of time. Java supports recursive method. Consider the problem of computing the factorial of a given number. The formula for finding factorial is given by :

n! = 1 × 2 × 3....n

The above formula can be written as:

| n! | = n * (n–1)! |
|  | = n * (n–1)*(n–2)! |
|  | = n * (n–1)*(n–2)*(n–3)! |
|  | etc. |

and finally 0! = 1! = 1.

The following program 8.6 implements the above formula using the recursive method:

Program 8.6![](images/00013.jpeg)

/* This program illustrates the use of recursive method.

 * This program requires jdk1.6 or higher for compile and execute.

 * ka.somasundaram@gmail.com

 */

import java.io.Console;

class Factfun {

long Fact(int n) {

if (n == 0 || n == 1) {

return 1;

} else {

return n * Fact(n – 1);

}

}

}

class Recursion {

public static void main(String args[]) {

Factfun f = new Factfun();

Console con = System.console();

con.printf(“\n Factorial of 8 = %d\n”, f.Fact(8));

con.printf(“\n Factorial of 12 = %d\n”, f.Fact(12));

}

}

The above program gives the following output shown in Fig. 8.6.

![](images/00098.jpeg)

**Fig. 8.6** Output screen for program 8.6

8.8 STATIC METHODS, VARIABLES AND BLOCKS

8.8.1 Static Methods

We have so far seen that methods are called on the objects. That is, methods are called in relation to an instance of a class. Java provides a mechanism, in which methods can be called without an instance of a class. Such methods are called **static** methods. Static methods are declared by using the modifier **static**. For example, the **main**() is a **static** method as it has to function independent of any object. Static methods can be called directly, if the method is within the same class or can be called by specifying its class name along with the method name if it is in a different class. The general form calling a **static** method is :

classname.static_method;

A **static** method cannot access any instance variable of that class. It cannot make use of **this** or **super** inside the method. It can only access static methods and **static** variables.

The following program 8.7 illustrates the use of a **static** method within the same class:

Program 8.7![](images/00013.jpeg)

/* Illustration for static method within the same class.

* This program requires jdk1.6 or higher .

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Stat {

static void Add(int a, int b) {

Console con = System.console();

int sum = a + b;

con.printf(“Sum of numbers = %d\n”, sum);

}

public static void main(String args[]) {

Add(5, 24);

}

}

The output of the above program is shown in Fig. 8.7.

![](images/00099.jpeg)

**Fig. 8.7** Output screen for program 8.7

The following program 8.8 illustrates the use of a static method from a different class:

Program 8.8![](images/00013.jpeg)

/* This program illustrates the use of static method in a different class.

* This program requires jdk1.6 or higher .

* ka.somasundaram@gmail.com */

import java.io.Console;

class Statc {

static void Add(int a, int b) {

Console con = System.console();

int sum = a + b;

con.printf(“Sum of numbers = %d\n”, sum);

}

}

class Static1 {

public static void main(String args[]) {

Statc.Add(5, 24);

}

}

The above program gives the same result as that of the previous program 8.7.

![](images/00011.jpeg)A static method can be called directly.

8.8.2 Static Variables

Instance variables of Java can also be declared as **static**. When a variable is declared as **static**, it becomes a class variable rather than an object variable. Static variables can be accessed by any part of the program. Even if an instance is created, the **static** variables retain the last modified value. In effect it becomes a global variable or class variable.

For example, consider the following program 8.9:

Program 8.9![](images/00013.jpeg)

/* This program illustrates the use of static variables.

* This program requires jdk1.6 or higher for compile and execute.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Stat {

static int i = 0, j = 0;

void Printval() {

Console con = System.console();

con.printf(“ i = %d%n”, i);

con.printf(“ j = %d%n”, j);

}

}

class Statvar {

public static void main(String args[]) {

Stat sv = new Stat();

Console con = System.console();

con.printf(“ Value of variables in the first object%n”);

sv.Printval();

sv.i = 10;

sv.j = 15;

con.printf(“ Value of variables in the second object%n”);

Stat sv1 = new Stat();

sv1.Printval();

}

}

The above program gives the following output shown in Fig. 8.8.

![](images/00100.jpeg)

**Fig. 8.8** Output screen for program 8.9

In the above program 8.9, if we declare the instance variables i and j as:

static int=0, j=0;

in the class Statvar, you will get the following result shown in Fig. 8.9.

![](images/00101.jpeg)

**Fig. 8.9** Output screen for program 8.9 after declaring i and j as static

You will observe from the above result, that when the variables i and j are declared as static, they retain the value set in the first object and, hence, when the second object is created, i and j retain the last modified value.

![](images/00011.jpeg)A static variable is a class variable. Any object of the class in which the static variable is defined can modify the value of a static variable. Such modification will be reflected in all the objects.

8.8.3 Static Blocks

In certain cases, it may be needed to execute a set of statements in a class only once and independent of the instance. In Java, such statements can be placed in a block and declared as **static**. Such blocks are called **static** blocks. When a class is loaded, the block is executed. In the subsequent instances, the **static** blocks are not executed. With this feature, it is possible to execute a set of instructions in the **static** block even in the absence of a main method. The following program 8.10 illustrates the **static** block.

Program 8.10![](images/00013.jpeg)

/* This program illustrates the use of static block.

* This program requires jdk1.6 or higher .

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Statblock {

void Printmsg() {

Console con = System.console();

con.printf(“%n Ouput of Printmsg() method”);

}

static {

Console con = System.console();

con.printf(“%n Ouput from static block”);

}

}

class Stblock {

public static void main(String args[]) {

Statblock sb = new Statblock();

Console con = System.console();

con.printf(“%n First object”);

sb.Printmsg();

Statblock sb1 = new Statblock();

con.printf(“%n Second object”);

sb1.Printmsg();

}

}

The above program gives the following output shown in Fig. 8.10.

![](images/00102.jpeg)

**Fig. 8.10** Output screen for program 8.10

8.9 ABSTRACT CLASSES

In the inheritance hierarchy, we have seen, while going down, one encounters subclasses which have definite instance variables and methods. Similarly, when we go up in the hierarchy, common properties of classes can be abstracted and defined in a single class. This helps to deal a complex problem in one class. For example, consider geometrical shapes, circle, rectangle and parallelogram. All of them have certain common properties like area and circumference. The common properties can be abstracted and brought under a common class, Shape, with methods for calculating the area and circumference. But these methods cannot have a concrete body as the formulae for calculating area and circumference are different.

![](images/00103.jpeg)

**Fig. 8.11** Abstraction of commonalities of several classes to common class

Therefore, methods are defined without a concrete body. Java allows defining of methods without body and such methods are called **abstract** methods. Abstract methods are defined with a key word **abstract**. A class containing at least one **abstract** method is called as an **abstract** class. Since **abstract** classes do not have concrete methods, objects for **abstract** classes cannot be created. However, object reference variables of **abstract** classes can be created. Further, when an **abstract** class is defined, a subclass of the **abstract** class must give a concrete method. Otherwise, the subclass also becomes an **abstract** class. The following program 8.11 has an **abstract** class and an **abstract** method:

Program 8.11![](images/00013.jpeg)

/* This program illustrates the abstract class and abstract method.

* This program requires jdk1.6 or higher for compile and execute.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

abstract class Shape {

double area;

final double PHI = Math.PI;

abstract double Area(); // abstract method

}

class Circle extends Shape {

double radius;

Circle(double r) {

radius = r;

}

double Area() {

area = PHI * radius * radius;

return area;

}

}

class Abstractclass {

public static void main(String args[]) {

Console con = System.console();

Circle cir = new Circle(4.0);

double ar;

ar = cir.Area();

con.printf(“Area of the circle = %6.2f%n”, ar);

}

}

The above program gives the following output shown in Fig. 8.12.

![](images/00104.jpeg)

**Fig. 8.12** Output screen for program 8.11

![](images/00011.jpeg)A method without a body is called as an abstract method. A class containing an abstract method is called as an abstract class.

8.10 MATHEMATICAL METHODS

For engineering and scientific calculations many basic mathematical functions, like sin(x), are needed. Such functions are available in Math class defined in **java.lang** package. All the methods are static. This package is automatically imported by the JVM. The following program 8.12 gives use of some of the mathematical methods.

Program 8.12![](images/00013.jpeg)

/* ---------------------------------------------------------------------

* This program illustrates some of the methods defined in Math class

* This program requires jdk1.6 or higher for compile and execute

ka.somasundaram@gmail.com

----------------------------------------------------------------------*/

import java.io.Console;

class Mathmethods {

public static void main(String args[]) {

Console con = System.console();

double pi = 22.0 / 7.0;

double x = 3.6, ly20,alog, y = 0.5;

double s90 = Math.toRadians(90);

double as1 = Math.asin(1.0);

con.printf(“%n The angle 90 degress = %6.4f radians”, s90);

con.printf(“%n Value of sin %6.4f = %6.4f”, s90, Math.sin(s90));

con.printf(“%n Value of arcsin(1.0) = %6.4f “, as1);

con.printf(“%n Value of 22/7/2 = %6.4f “, 22.0 / 7.0 / 2.0);

con.printf(“%n Java Math.E = %6.4f “, Math.E);

con.printf(“%n Value of exp(1) = %6.4f”, Math.exp(1.0));

con.printf(“%n Java Math.PI = %6.4f”, Math.PI);

con.printf(“%n mathematical pi = 22/7 = %6.4f “, 22.0 / 7.0);

con.printf(“%n %6.4f rounded by rint = %3.1f “, x, Math.rint(x));

con.printf(“%n %6.4f rounded by round = %d “, x, Math.round(x));

con.printf(“%n %6.4f rounded by ceil = %3.1f “, x, Math.ceil(x));

con.printf(“%n %6.4f rounded by floor = %3.1f “, x, Math.floor(x));

con.printf(“%n natural logarithm of 10.0 = %6.4f”, Math.log(10.));

ly20 = Math.log10(20);

con.printf(“%n logarithm to base 10 of 20.0 = %6.4f “, ly20);

alog=Math.exp(Math.log(10) * ly20);

con.printf(“%n anti log of %6.4f = %6.4f”, ly20,alog );

con.printf(“%n Hyperbolic sin of %6.4f = %6.4f”, y, Math.sinh(y));

con.printf(“%n Hyperbolic cos of %6.4f = %6.4f”, y, Math.cosh(y));

con.printf(“%n Hyperbolic tan of %6.4f = %6.4f”, y, Math.tanh(y));

con.printf(“%n %5.2f to the power of 4 = %6.4f”, x, Math.pow(x, 4));

}

}

The above program gives the output shown in Fig. 8.13.

![](images/00105.jpeg)

**Fig. 8.13** Output screen for program 8.12

8.11 TIME AND DATE

Java has a class **GregorianCalendar** contained in **java.util** package. This class has several methods to handle date, year, month, day, hour, minutes, AM, PM etc. One can make use of this class whenever time and date related information is needed from the system. Some of the methods defined in **GregorianCalendar** is illustrated in program 8.13\. The time and date parameters can be obtained from the GregorianCalendar object either using individual parameters or by simply using conversion characters (see Appendix A).

Program 8.13![](images/00013.jpeg)

/* This program illustrates the use of some of the

fields and methods defined in GregorianCalendar.

This program requires jdk1.6 or higher.

ka.somasundaram@gmail.com

*/

import java.io.Console;

import java.util.GregorianCalendar;

class Calndr {

public static void main(String args[]) {

GregorianCalendar cal = new GregorianCalendar();

Console con = System.console();

con.printf(“ YEAR: “ + cal.get(cal.YEAR));

con.printf(“%n WEEK_OF_YEAR: %d”, cal.get(cal.WEEK_OF_YEAR));

con.printf(“%n WEEK_OF_MONTH: %d”, cal.get(cal.WEEK_OF_MONTH));

con.printf(“%n DATE: %d”, cal.get(cal.DATE));

con.printf(“%n DAY_OF_MONTH: %d”, cal.get(cal.DAY_OF_MONTH));

con.printf(“%n DAY_OF_YEAR: %d”, cal.get(cal.DAY_OF_YEAR));

con.printf(“%n DAY_OF_WEEK: %d”, cal.get(cal.DAY_OF_WEEK));

con.printf(“%n AM_PM: %s”, (cal.get(cal.AM_PM) > 0 ? “PM” : “AM”));

con.printf(“%n HOUR: %d”, cal.get(cal.HOUR));

con.printf(“%n HOUR_OF_DAY: %d”, cal.get(cal.HOUR_OF_DAY));

con.printf(“%n MINUTE: %d”, cal.get(cal.MINUTE));

con.printf(“%n SECOND: %d”, cal.get(cal.SECOND));

con.printf(“%n MILLISECOND: %d%n”, cal.get(cal.MILLISECOND));

// Date from day, month and year from calendar

int dd = cal.get(cal.DAY_OF_MONTH);

int mm = cal.get(cal.MONTH) + 1;//Jan is 0 and

//hence 1 is added

int yy = cal.get(cal.YEAR);

con.printf(“Date assembled: %d:%d:%d %n”, dd, mm, yy);

// Date using e,m,y conversions

con.printf(“Date using e,m,Y converions :

%1$te:%1$tm:%1$tY%n”, cal);

// Date using D conversion

con.printf(“Date using D conversion : %tD%n”, cal);

// Date using F conversion

con.printf(“Date using F conversion : %tF%n”, cal);

// Date using c conversion

con.printf(“Date using c conversion : %tc%n”, cal);

// Time from hour,minute and second

int h = cal.get(cal.HOUR);

int m = cal.get(cal.MINUTE);

int s = cal.get(cal.SECOND);

con.printf(“Time Assembled: %d:%d:%d%n”, h, m, s);

// Time using R conversion

con.printf(“Time using R conversion : %TR%n”, cal);

// Time using T conversion

con.printf(“Time using T conversion : %TT%n”, cal);

// Time using r conversion

con.printf(“Time using r conversion : %Tr%n”, cal);

}

}

The above program gives the following output shown in Fig. 8.14.

![](images/00106.jpeg)

**Fig. 8.14** Output screen for program 8.13

After reading this chapter, you should have learned the following:

*   A subclass inherits all the properties of the superclass.
*   Methods having the same name and type signature are called overriding methods.
*   A final class cannot be subclassed.
*   Static methods can be called without objects.
*   Classes having abstract methods are called as abstract classes.
*   Mathematical functions are available in **Math** class.
*   Date and time parameters are handled in **GregorianCalendar** class.

In the next chapter, you will learn about packages and interfaces.

![](images/00053.jpeg)

Problem 8.1T

Write a class to find the mean value of a set of given numbers using the formula:

![](images/00107.jpeg)

Extend this class to compute the standard deviation using the following formula:

![](images/00108.jpeg)

use the following data:

x = 14, 22, 9, 15, 20, 17, 12, 11

Program 8.1T![](images/00013.jpeg)

/* ---------------------------------------------------------------------

This program calculates the arithmetic mean in the super class and standard deviation in the sub class.

ka.somasundaram@gmail.com

----------------------------------------------------------------------*/

import java.io.Console;

class Arithmetic {

double num[];

int araylen;

Arithmetic(double a[]) {

araylen = a.length;

num = new double[araylen];

for (int i = 0; i < araylen; i++) {

num[i] = a[i];

}

}

double Mean() {

double sum = 0;

for (int i = 0; i < araylen; i++) {

sum += num[i];

}

double mean = sum / araylen;

return mean;

}

}

class Diffsqr extends Arithmetic {

double dif[];

Arithmetic arith;

double xmean;

Diffsqr(double x[]) {

super(x);

araylen = x.length;

dif = new double[araylen];

xmean = super.Mean();

for (int i = 0; i < araylen; i++) {

dif[i] = (x[i] – xmean);

dif[i] = dif[i] * dif[i];

}

}

double Std() {

arith = new Arithmetic(dif);

double sd = Math.sqrt(arith.Mean());

return sd;

}

}

class TIO81 {

public static void main(String args[]) {

double x[] = {14, 22, 9, 15, 20, 17, 12, 11};

Console con = System.console();

//print out the given numbers

con.printf(“The given numbers are: %n”);

for (int i = 0; i < x.length; i++) {

con.printf(“ %2.0f”, x[i]);

}

con.printf(“%n”);

Diffsqr ds = new Diffsqr(x);

double xm = ds.Mean();

double sdev = ds.Std();

con.printf(“Mean of the numbers = %5.2f%n”, xm);

con.printf(“Standard deviation = %5.2f%n”, sdev);

}

}

The above program gives the following output shown in Fig. 8.15.

![](images/00109.jpeg)

**Fig. 8.15** Output screen for program 8.1T

EXERCISE–8

**I. Fill in the blanks:**

8.1 To create a subclass, the keyword .......................... is used.

8.2 To refer to a superclass constructor, the keyword .......................... is used.

8.3 A subclass can be created which inherits only a few methods of the superclass. (True/False)

8.4 Methods having the same name and different type signature are called ..........................methods.

8.5 Methods having the same name and same type signature are called .......................... methods.

8.6 Polymorphism property is implemented through .......................... and .......................... .

8.7 To prevent inheritance of a class, it should be declared as .......................... .

8.8 A method declared as .......................... cannot have overriding method.

8.9 .......................... method can be called without the instance of a class.

8.10 .......................... variable is called as a class variable.

8.11A block statement that is to be initialized only once at the time of loading the class is to be declared as ......................... .

8.12A method without the body is called .......................... method.

8.13A class having an abstract method is to be declared as .......................... .

**II. Write Java programs for the following:**

8.14Write a class with a method to find the area of a rectangle. Create a subclass to find the volume of a rectangular shaped box.

8.15Write a class called square with a method Area (double a) that finds the area (a²) of the square. Create a class Cube which is a subclass of Square and write an overriding method Area(double a) that finds the surface area (6a²) of the cube.

8.16Write a class with a static method that returns the maximum value of three given integers. Write another class with main method and call the static method to print the maximum values for two sets of integer values (say {5, 2, 10}, {75, 20, 89}).

8.17Write an abstract class with an abstract method void Special (int n). Create a subclass of this class and implement the Special method that finds the numbers that are perfect squares from 1 up to n.

8.18Write an abstract class Special with an abstract method double Process (double P, double R). Create a subclass Discount and implement the Process() method with the following formula:
net = P – P* R/100
Return the net value. Create another subclass Tax for Special and implement the Process() method with the following formula:
total =P + P * R/100
Return the total.

9Packages and InterfacesIn this chapter, packages and interfaces are explained. When there are several classes that are reusable in many programs, then managing them becomes a problem. To overcome this problem, package is used. Interfaces have methods which do not have body. Interfaces help programmers to implement the interface methods with a procedure of their choice. Interfaces also help to realize multiple inheritance.

9.1 PACKAGE

Generally, you create many classes for several applications. When there are large number of classes, keeping them all in a single directory and managing them for different applications is bit cumbersome. To solve this problem, one can store the classes in different directories, each directory containing classes performing similar type of functions. To identify the location where a class is stored in the directory, the **package** statement is used. This is necessary to identity a class when you want to use that class in any other class in any other directory. Thus, packages help to manage large number of classes. The general form of the package statement is:

**package** pckg1.pckg2.pckg3;

For example, the statement

**package** java.soms.jbook;

states that the program is stored in a directory java\soms\jbook.

In any program, the **package** statement, if used, must be the first statement.

![](images/00110.jpeg)

**Fig. 9.1** Packages act as class container

9.2 THE import STATEMENT

When you want to use the classes in a package in another class in a different package, then those classes can be referred in your class using **import** statement. For example, the class A in Package1 in Fig. 9.1 can be accessed by package2 by placing the following statement:

**import** package1.A;

In any Java program, the **import** statement, if used, must appear immediately after **package** statement.

In addition to user-defined classes, thousands of Java classes are also available to users. Java classes are packaged in different packages and are placed in the Java Development Kit (JDK). You can access them using the **import** statement. For example, all the input/output functions are available in a package java.io. Therefore, the statement:

**import** java.io.*;

can access all the classes in the java.io package.

The class and method in the statement:

System.out.println(......);

are available in Java language package, **java.lang**. There are other classes like **Math** in the java.lang package. Java compiler by default, automatically import the java.lang.* and, therefore, there is no necessity to explicitly **import** this package. The * mark indicates that you can access all the classes in that package. If any specific class is needed, then the name of the class can be explicitly mentioned instead of *. If two classes have same class name, then there is no way to access them with the statement

**import** package1.*;

**import** package2.*;

One has to explicitly mention the class name along with the **package** name. The following example illustrates that concept:

class Newclass **extends** package1.classA {

. . .

. . .

}

9.3 ACCESS MODIFIER

One of the key features of Java language is its encapsulation. This feature helps to protect your data and method to the extent you want. Such a feature is not available in non-OOP languages. This feature in Java is implemented through access modifier. Let us assume that we have two packages, Package1 and Package2, as given in Fig. 9.2.

![](images/00111.jpeg)

**Fig. 9.2** Class, subclass and non-subclass in the same package and different packages

A member (method or variable) declared with the access specifier in a class can be made visible only to that class or to all classes in any package in varying degrees. This helps the user to control the use of a member by other classes.

The access modifiers and their visibility are given in Table 9.1.

**Table 9.1** Access modifiers and their visibility

| ***Modifier*** | ***Visibility*** |
| private | Visible only to the class |
| protected | Visible to the subclasses in any package and to all classes in the same package |
| public | Visible to all packages |
| No Modifier (Default) |  Visible only to the same package |

In all the programs we have seen so far, the instance variables were without any access modifier. That means the variables were visible to the whole of that package (all classes in that directory). The following programs 9.1, 9.2 and 9.3 illustrate the use of access modifiers:

The following program 9.1 illustrates the class A placed in package (directory) jbookr:

Program 9.1![](images/00013.jpeg)

/* This program illustrates the use of package statement.

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

package jbookr;

import java.io.Console;

public class A {

int x = 25;

private int x_pri = 35;

protected int x_pro = 45;

public int x_pub = 55;

Console con = System.console();

void PrintA() {

con.printf(“%n Printing in class A%n”);

con.printf(“x = %d%n”, x);

con.printf(“private x = %d%n”, x_pri);

con.printf(“ protected x = %d%n”, x_pro);

con.printf(“ public x = %d%n”, x_pub);

}

}

Create the following program 9.2 AccessDemo.java in the directory jbookr:

Program 9.2![](images/00013.jpeg)

/* This program illustrates the use of package statement.

* You need to go up one step above this directory to compile.

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

package jbookr;

import java.io.Console;

class B extends A {

public void PrintB() {

con.printf(“%n Printing in subclass B%n”);

con.printf(“ x = %d%n”, x);

// Dont try this :con.printf(“%n private x = %d%n”, x_pri);

con.printf(“ protected x = %d%n”, x_pro);

con.printf(“ public x = %d%n”, x_pub);

}

}

class C {

public void PrintC() {

A a = new A();

Console con = System.console();

con.printf(“%n Printing in non-subclass C%n”);

con.printf(“x = %d%n”, a.x);

// Not accessible here: con.printf(“ private x = %d%n”, a.x_pri);

con.printf(“protected x = %d%n”, a.x_pro);

con.printf(“public x = %d%n”, a.x_pub);

}

}

class AccessDemo {

public static void main(String args[]) {

A a = new A();

B b = new B();

C c = new C();

Console con = System.console();

con.printf(“%n Printing in the same package%n”);

a.PrintA();

b.PrintB();

c.PrintC();

}

}

Go to a directory one above the jbookr and compile the AccessDemo.java. (Trying to compile AccessDemo.java in the same directory jbookr will give error). Then execute the program by issuing the following command:

java jbookr.Access Demo

You will get the following output shown in Fig. 9.3.

![](images/00112.jpeg)

**Fig. 9.3** Output screen for program 9.2

Now create another package soms. Create the following program 9.3 PackageDemo.java. Please note that the class A in package jbookr is declared as public. Otherwise you cannot access it in another package.

Program 9.3![](images/00013.jpeg)

/* This program illustrates the use of package statement.

* You need to go up one step above this directory to compile.

* This program requires jdk1.6 or higher for compile and execute.

* ka.somasundaram@gmail.com

*/

package soms;

import java.io.Console;

import jbookr.A;

class D extends A {

void PrintD() {

Console con = System.console();

con.printf(“\n Printing in subclass D in another package\n”);

// con.printf(“ x = %d\n”, x);

// con.printf(“ private x = %d\n”, x_pri);

con.printf(“ protected x = %d\n”, x_pro);

con.printf(“ public x = %d\n”, x_pub);

}

}

class E {

void PrintE() {

A a = new A();

Console con = System.console();

con.printf(“\n Printing in different package, non-subclass E\n”);

con.printf(“ Public x = %d\n”, a.x_pub);

}

}

class PackageDemo {

public static void main(String args[]) {

A a = new A();

Console con = System.console();

//B b= new B();

//C c= new C();

D d = new D();

E e = new E();

con.printf(“Printing in different package\n”);

// a.PrintA();

//b.PrintB();

//c.PrintC();

d.PrintD();

e.PrintE();

}

}

The above program gives the following result shown in Fig. 9.4.

![](images/00113.jpeg)

**Fig. 9.4** Output screen for program 9.3

9.4 INTERFACES

9.4.1 Defining Interfaces

Interfaces are similar to **abstract** classes, but differ in their functionality. Interfaces define methods without body. Interfaces cannot have instance variables. But, it can contain final variables, which must be initialized with values. The methods can have type signature. The interfaces help to implement multiple inheritance in Java. The general form of Defining an **interface** is:

modifier interface ifname {
final type var1 = val1;
final type var2 = val2;
modifier return_type mname1(type signature1) ;
modifier return_type mname2(type signature2);
}

Here, the modifier can be either public or no modifier. var1, var2 are final variables and val1 and val2 are values. ifname is the name of the **interface**, mname1 and mname2 are method names. When the **interface** is declared as public any other class can make use of it. The following is an example for **interface** declaration:

// illustration for interface
interface Calculation{
final double pi= 3.142;
double Area( double r);
}

9.4.2 Implementing an Interface

Once an **interface** is defined, another class should implement all the methods of the **interface**. An **interface** can be implemented in any number of classes. A class can implement any number of interfaces. The general form of implementing an interface is:

modifier class classname [extends superclass] implements

interface1, interface2 . . . interfaceN {
body;
}

Here the modifier is either public or no modifier.

Java does not support multiple inheritance like in C++. Java supports only multilevel inheritance.

![](images/00114.jpeg)

**Fig. 9.5** Multiple inheritance and multilevel inheritance

![](images/00115.jpeg)

**Fig. 9.6** Interfaces in Java help to realize the functionality of multiple inheritance

![](images/00011.jpeg)A class can implement more than one interface, exhibiting multiple inheritance.

The functionality of multiple inheritance in Java is realized through the interfaces, in which a class can implement any number of interfaces.

In the implementing class, concrete methods are to be given for the abstract methods defined in the interface. The type signature of the methods in the class must match the type signature of the interface methods. The concrete methods are to be declared as **public**. If complete methods are not given in the implementing class, that class must be declared as **abstract**. A class implementing an interface can also have additional methods of its own.

The following is an example for implementing an **interface** Calculation:

class Circle implements Calculation {

public double Area (double x) {

double ar;

ar = pi*x*x; // area of circle.

return ar;

}

}

![](images/00011.jpeg)When an interface method is implemented in a class, it must be declared as **public**.

Another class can implement the same **interface** Calculation in a different form, but with the same type signature. The following class shows how the **interface** is implemented in a different class:

// Program to illustrate interface implementation

class Sphere implements Calculation{

public double Area(double x){

double surface_area =4.0*pi*x*x;

return surface_area;

}

}

An interface can be extended to create another **interface**. For example, the following **interface** extends the previous **interface** Calculation:

interface Average extends Calculation {
void Mean (double[] d);
}

Now, any class that implements the Average must implement both the methods Area and Mean.

The following program 9.4 illustrates the use of **interface:**

Program 9.4![](images/00013.jpeg)

/* This program illustrates the use of interface.

* Calculates the simple interest and compound interest.

* This program requires jdk1.6 or higher for compile and execute.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

interface Deposit {

void Interest(double principal, int year, double rate);

}

class Simple implements Deposit {

Console con = System.console();

public void Interest(double p, int n, double r) {

double intr, total;

intr = p * n * r / 100.0;

total = p + intr;

con.printf(“\n Principal amount:Rs%6.0f\n”, p);

con.printf(“No of Years : %d\n”, n);

con.printf(“Simple interest rate :%5.2f\n”, r);

con.printf(“Interest amount :Rs %7.0f\n”, intr);

con.printf(“Total Amount after %d years:Rs%7.0f\n”, n, total);

}

}

class Compound implements Deposit {

Console con = System.console();

public void Interest(double p, int n, double r) {

double intr, total;

// pow(x,y) finds the value of x to the power y

total = p * Math.pow(1 + r / 100.0, n);

intr = total – p;

con.printf(“\n Principal amount: Rs %6.0f\n”, p);

con.printf(“ No of Years : %d\n”, n);

con.printf(“ Compound interest rate:%5.2f\n”, r);

con.printf(“ Interest amount:Rs%7.0f\n”, intr);

con.printf(“ Total amount after %d years:Rs%7.0f\n”, n, total);

}

}

class InterestCal {

public static void main(String args[]) {

int nyears=5;

double p=35000, srate=8.5, crate=7.5;

Console con = System.console();

Simple sim = new Simple();

Compound com = new Compound();

sim.Interest(p, nyears, srate);

com.Interest(p, nyears, crate);

}

}

The above program gives the following result shown in Fig. 9.7.

![](images/00116.jpeg)

**Fig. 9.7** Output screen for program 9.4

After reading this chapter, you should have learned the following:

*   Package statement indicates the location of a file in a directory.
*   To refer and access classes in a package, the import statement is used.
*   Access modifier realizes the data encapsulation property.
*   Access modifiers give protection to data and methods in varying degrees.
*   Interfaces allow predefined conceptual methods to be implemented in many different ways.
*   Through interfaces, multiple interitance can be realized.

In the next chapter, you will learn about wrapper classes.

![](images/00053.jpeg)

Problem 9.1T

Write an interface called Hyperbolic with a method to find either Cosh or Sinh. Implement this interface to calculate Sinh(x) and Cosh(x) given by:

![](images/00117.jpeg)

for x=0.5 to 5.5 in steps of 0.5.

Program 9.1T![](images/00013.jpeg)

/* ———————————————————————————-———-

This program calculates the hyperbolic sine and cosine functions using

interface. This program requires jdk1.6 or higher

ka.somasundaram@gmail.com

——————————————————————————————— */

import java.io.Console;

interface Hyper {

final int n = 10;

double Hypfun(double x);

}

class Hysin implements Hyper{

double sinh;

long factn;

int i;

long Factfun(int nmax) {

long fact = 1;

for (i = 2; i <= nmax; i++)

fact *= i;

return fact;

}

public double Hypfun(double x){

sinh = x;

for (int k = 1; k <= n; k++)

{

factn = Factfun(2 * k + 1);

sinh = sinh + Math.pow(x, (2 * k + 1)) /factn;

}

return sinh;

}

}

class Hycos implements Hyper {

double cosh;

long factn;

int i;

long Factfun(int nmax){

long fact = 1;

for (i = 2; i <= nmax; i++)

fact *= i;

return fact;

}

public double Hypfun(double x) {

cosh = 1;

for (int k = 1; k <= n; k++){

factn = Factfun(2 * k);

cosh = cosh + Math.pow(x, (2 * k)) / factn;

}

return cosh;

}

}

class TIO91{

public static void main(String args []){

double x, sinh, cosh, jsh, jch;

Hyper hcos;

Hyper hsin;

Console con= System.console();

int pn = 40;

for (int i = 0; i < pn; i++)

System.out.print(“–”);

con.printf(“%n”);

con.printf(“x \t sinh \t Java \t cosh \t Java %n”);

for (int i = 0; i < pn; i++)

System.out.print(“–”);

con.printf(“%n”);

for (x = 0; x < 5.1; ){

hsin = new Hysin();

hcos = new Hycos();

sinh = hsin.Hypfun(x);

cosh = hcos.Hypfun(x);

jsh=Math.sinh(x);

jch=Math.cosh(x);

con.printf(“ %3.1f %8.3f %8.3f%8.3f %8.3f%n”,

x, sinh,jsh,cosh,jch);

x = x + 0.5;

}

for (int i = 0; i < pn; i++)

con.printf(“– ”);

con.printf(“%n”);

}

}

The above program gives the following output shown in Fig. 9.8.

![](images/00118.jpeg)

**Fig. 9.8** Output screen for program 9.1T

EXERCISE–9

**I. Fill in the blanks**

9.1 Package statement indicates the directory in which the .......................... is stored.

9.2 To make use of a class defined in a package in another class, the .......................... statement is to be used.

9.3 The concept of data encapsulation is realized through .......................... .

9.4 If a variable is to be visible to the subclass in any package and to all classes in the same package, it must be declared as .......................... .

9.5 The first statement of a Java program is .........................., if used.

9.6 In a Java program, import statement must appear immediately after ..........................statement.

9.7 The default package that is implicitly called in a Java program is .......................... .

9.8 ........................... help to realize the concept multiple inheritance in Java language.

9.9 Interface has methods .......................... body.

9.10 .......................... variable can be used in an interface.

9.11To make use of an interface, it must be .......................... in another class.

9.12A class can implement .......................... number of interfaces.

9.13If a class does not implement all methods in an interface, that class must be declared as ..........................

**II. Write Java programs for the following:**

9.14Write a Java class called Sumn that finds the sum of all numbers from 1 up to the given number n. This class is in the directory with path c:\java\pac. Write a package statement inside the class Sumn.

9.15Write an interface called Numbers, with a method int Process (int x, int y). Write a class called Sum, in which the method Process finds the sum of two numbers and returns an int value. Write another class called Average, in which the Process method finds the average of the two numbers and returns an int.

9.16Write an interface called Exam with a method Pass (int mark) that returns a boolean. Write another interface called Classify with a method Division (int average) which returns a string. Write a Class called Result which implements both Exam and Classify. The Pass method should return true if the mark is greater than or equal to 50 else false. The Division method must return “FIRST” when the parameter average is 60 or more, “SECOND” when average is 50 or more but below 60, “NO DIVISION” when average is less than 50.

10Wrapper ClassesIn this chapter, wrapper classes are explained. Basic types cannot be instantiated to create objects. Wrapper classes help to create objects of basic type. Creation of objects for different basic types are explained in this chapter.

Java has eight basic data types **byte, short, int, long, float, double, char** and **boolean**. These basic types cannot be instantiated to get objects. Sometimes, there is a need to treat these types as objects. Java provides object wrappers for these basic types, which help to convert simple types to the corresponding objects. Once basic types are transformed to objects, they become immutable, i.e. their values can no longer be altered. This object representation of simple types help to pass them by reference to methods instead of passing by value. There are several methods in these classes, which can be used for I/O operations and conversion from one form to another.

10.1 THE NUMBER CLASS

The **abstract** class **Number** contains six concrete subclasses to wrap the simple types **byte, short**, **int**, **long**, **float** and **double**. The **Number** class is defined in **java.lang** package. The subclasses are :

| Byte | Long |
| Short | Float |
| Integer | Double |

All the above six classes have common methods given in Table 10.1.

**Table 10.1** Methods defined in all subclasses of Number

| *Method* | *Purpose of the Method* |
| 1. | byte byteValue() | Returns the byte value of the invoking object |
| 2. | double doubleValue() | Returns the double value of the invoking object |
| 3. | float  floatValue() | Returns the float value of the invoking object |
| 4. | int intValue() | Returns the int value of the invoking object |
| 5. | short shortValue() | Returns the short value of the invoking object |
| 6. | long longValue() | Returns the long value of the invoking object |
| 7. | String toString() | Returns a string that contains the decimal equivalent of the invoking object |
| 8. | int hashCode() | Returns the hash code for the invoking object |

All these subclasses have three constants, MIN_VALUE, MAX_VALUE, and SIZE representing minimum value, maximum value and size of the type.

10.1.1 Byte Class

**Byte** is a wrapper class for byte. The constructors for **Byte** are

(i) Byte (byte number)

(ii) Byte (String str)

where str is a String representation of a byte.

Apart from methods given in Table 10.1, **Byte** class has methods given in Table 10.2.

**Table 10.2** Additional methods defined in Byte class

| *Method* | *Purpose of the Method* |
| 1. | static Byte valueOf(String s) | Returns the Byte object of the String s  |
| 2. | static Byte valueOf(String s, int radix) | Returns a Byte object for the value specified by String s using the radix |
| 3. | int compareTo(Byte b) | Compares the numerical value of the invoking object with b; returns 0, if both are equal, negative if b>object, positive if b<object |
| 4. | boolean equals(Byte b) | Returns true if the invoking object equals b, otherwise false |
| 5. | static byte parseByte(String s) | Returns byte equivalent of the  number contained in the String s using radix 10 |
| 6. | static byte  parseByte(String s,int radix) | Returns byte equivalent of the number  contained in the String s using radix |
| 7. | static String  toString(byte n) | Returns a String that contains the decimal equivalent of n |

The following program 10.1 illustrates some of the methods defined in **Byte** class:

Program 10.1![](images/00013.jpeg)

/* This program illustrates some of the methods in Byte

class

This program requires jdk1.6 or higher

ka.somasundaram@gmail.com

*/

import java.io.Console;

class Passbyref {

void Objectval(Byte ob) {

Console con= System.console();

byte val = ob.byteValue();

con.printf(“%n byte Value of the Byte object : %2d%n”, val);

}

}

class ByteDemo

{

public static void main(String args [])

{

Passbyref pref = new Passbyref();

Console con= System.console();

Byte b1 = new Byte((byte)123);

Byte b2 = new Byte(“75”);

con.printf(“%n b1 object :%5s%n”, b1);

con.printf(“2*b1 value: %5d%n”, 2 * b1.byteValue());

con.printf(“b2 object : %3d%n”,b2);

con.printf(“2*b2 value : %3d%n”, 2 * b2.byteValue());

con.printf(“ is (b1 == b2) ? : : %3b%n”, b1.equals(b2));

con.printf(“ b1.compareTo(b2) : %3d%n”, b1.compareTo(b2));

Byte b3 = Byte.valueOf(“110111”, 2);

con.printf(“ b3 object :%3d%n”,b3);

byte b4 = Byte.parseByte(“89”);

con.printf(“ byte value of b4 :%3d%n”,b4);

pref.Objectval(b3);

con.printf(“ Size of Byte :%1d bits%n”,Byte.SIZE);

con.printf(“ Minimum value of Byte :

%3d%n”,Byte.MIN_VALUE);

con.printf(“ Maximum value of Byte :

%3d%n”,Byte.MAX_VALUE);

}

}

The above program gives the following output shown in Fig. 10.1.

![](images/00119.jpeg)

**Fig. 10.1** Output screen for program 10.1

10.1.2 Short Class

**Short** class is a wrapper for **short** type. The constructors for **Short** are:

(i) Short (short n)

(ii) Short (String s)

where n is a **short** type and s is a string representation of **short**.

Apart from methods given in Table 10.1, **Short** class has additional methods given in Table 10.3.

**Table 10.3** Additional methods defined in Short class

| *Method* | *Purpose of the Method* |
| 1. | static ShortvalueOf(String s) | Returns the Short object of the String s |
| 2. | static Short valueOf(String s, int radix) | Returns a Short object for the specified by String s using the radix |
| 3. | int compareTo(Short s) | Compares the numerical value of the invoking object with s;  return 0, if both are equal, negative if S > object and positive if s < object |
| 4. | boolean equals(Short s) | Returns true if the invoking object equals s, otherwise returns false |
| 5. | static short parseShort(String s) | Returns short equivalent of the number contained in the String s using radix 10 |
| 6. | static short parseShort(String s,int radix) | Returns short equivalent of the number contained in the String s using radix |
| 7. | static String toString(short n) | Returns a string that contains the decimal equivalent of n |

The following program 10.2 illustrates the use of Short class:

Program 10.2![](images/00013.jpeg)

* This program illustrates some of the methods in Short class

This program requires jdk1.6 or higher

ka.somasundaram@gmail.com

*/

import java.io.Console;

class Passbyref {

void Objectval(Short ob) {

Console con= System.console();

short val = ob.shortValue();

con.printf(“%n short Value of the Short object : %2d%n”, val);

}

}

class ShortDemo {

public static void main(String args []) {

Passbyref pref = new Passbyref();

Console con= System.console();

Short b1 = new Short((short)9456);

Short b2 = new Short(“743”);

con.printf(“%n b1 object :%5s%n”, b1);

con.printf(“2*b1 value :%5d%n”, 2 * b1.shortValue());

con.printf(“ b2 object :%3d%n”,b2);

con.printf(“ 2*b2 value :%3d%n”,2 * b2.shortValue());

con.printf(“ is (b1 == b2) ? : :%3b%n”, b1.equals(b2));

con.printf(“ b1.compareTo(b2) :%3d%n”, b1.compareTo(b2));

Short b3 = Short.valueOf(“2bf”, 16);

con.printf(“ b3 object :%3d%n”,b3);

short b4 = Short.parseShort(“3589”);

con.printf(“ short value of b4 :%3d%n”,b4);

pref.Objectval(b3);

con.printf(“Size of Short :%2d bits%n”, Short.SIZE);

con.printf(“ Minimum value of Short : %6d%n”,Short.MIN_VALUE);

con.printf(“ Maximum value of Short : %6d%n”,Short.MAX_VALUE);

}

}

The above program gives the following output shown in Fig. 10.2.

![](images/00120.jpeg)

**Fig. 10.2** Output screen for program 10.2

10.1.3 Integer Class

The **Integer** class wraps the simple type **int**. The constructors in **Integer** class are:

(i) Integer (int n)

(ii) Integer (String s)

where n is an **int** type and s is a **String** representing an **int**.

Apart from methods defined in Table 10.1, Integer class has additional methods given in Table 10.4.

**Table 10.4** Additional methods defined in Integer class

| *Method* | *Purpose of the Method* |
| 1. | static Integer valueOf(String s) | Returns an Integer object of the String s representing an int |
| 2. | static IntegervalueOf(String s, int radix) | Returns an Integer object for the value specified by String s using the radix |
| 3.  | int compareTo(Integer i) | Compares the numerical value of the invoking object with i; returns 0, if both are equal, negative if i>object and positive if i<object |
|  4. | boolean equals(Integer i) | Returns true if the invoking object is equal to i, otherwise false |
| 5. | static int parseInt(String s) | Returns the int equivalent of the number contained in the String s using radix |
| 6. | static int parseInt (String s, int radix) | Returns the int equivalent of the number contained in the String s using radix |
| 7. | static String  toString(int n)  | Returns a String that contains the decimal equivalent of n |
| 8. | static String  toString(int n, int radix)  | Returns a String that contains the decimal equivalent of n using the radix |
| 9. | static String  toBinaryString(int n) | Returns a String that contains the binary equivalent of n |
| 10. | static String toOctalString(int n) | Returns a String that contains octal equivalent of n |
| 11. | static String toHexString(int n) | Returns a String that contains the hexadecimal equivalent of n |

Use of some methods defined in Integer class is given in program 10.3.

Program 10.3![](images/00013.jpeg)

/* This program illustrates some of the methods in Integer class

This program requires jdk1.6 or higher

ka.somasundaram@gmail.com

*/

import java.io.Console;

class IntegerDemo {

public static void main(String args []) {

Integer i1 = new Integer(87456);

Console con= System.console();

Integer i2 = new Integer(“681523”);

con.printf(“%n i1 object:%4d%n”, i1);

con.printf(“%n 2*i1 value :%4d”, 2 * i1.intValue());

con.printf(“%n i2 object:%4d”, i2);

con.printf(“%n 2*i2 value :%4d”, 2 * i2.intValue());

con.printf(“%n is (i1 == i2)?: %b”, i1.equals(i2));

con.printf(“%n i1.compareTo(i2) :%4d “, i1.compareTo(i2));

Integer i3 = Integer.valueOf(“fa26”, 16);

con.printf(“%n Decimal equivalent of hex fa26=%4d”, i3);

con.printf(“%n byte value of Integer object i3:%4d”, i3.byteValue());

con.printf(“%n int value of Integer object i3:%4d”, i3.intValue());

con.printf(“%n double value of Integer object i3:%6.0f”, i3.doubleValue());

int i4 = Integer.parseInt(“85671”);

con.printf(“%n Integer value of i4:%4d”, i4);

int inum = 97234;

String binstr=Integer.toBinaryString(inum);

con.printf(“%n binary equivalent of decimal%4d = %12s%n”, inum, binstr);

binstr=Integer.toHexString(inum);

con.printf(“%n hexadecimal equivalent of decimal%4d = %6s%n”, inum, binstr);

con.printf(“%n Size of Integer:%2d bits%n”, Integer.SIZE);

con.printf(“%n Minimum value of Integer:%d”, Integer.MIN_VALUE);

con.printf(“%n Maximum value of Integer :%d%n “, Integer.MAX_VALUE);

}

}

The above program gives the following output shown in Fig. 10.3.

![](images/00121.jpeg)

**Fig. 10.3** Output screen for program 10.3

10.1.4 Long Class

The **Long** class is used to wrap **long** type. The constructors for **Long** class are :

(i) Long (long n)

(ii) Long (String s)

where n is a **long** type and s is a **String** that represents a **long** type. Apart from the methods given in Table 10.1, additional methods defined in **Long** are given in Table 10.5.

**Table 10.5**Additional methods defined in Long class

| *Method* | *Purpose of the Method* |
| 1. | static Long valueOf(String s) | Returns a Long object of the String s |
| 2. | static Long valueOf(String s, int radix) | Returns a Long object for the value specified by String s Using the radix |
|  3. | int compareTo(Long L) | Compares the numerical value of the invoking object with L; returns 0, if both are equal, negative if L > object and positive if L < object |
|  4. | boolean equals(Long L)  | Returns true if the invoking object is equal to L, otherwise false |
| 5. | static long parseLong (String s) | Returns the long equivalent of the number contained in the String s using radix 10 |
| 6. | static long parseLong(String s, int radix) | Returns the long equivalent of the number contained in the String s using radix |
| 7. | static String toString(long n ) | Returns a String that contains the decimal equivalent of n |
| 8. | static String toString (long n, int radix) | Returns a String that contains the decimal equivalent of n using the radix |
| 9.  | static String   toBinaryString(long n) | Returns a String that contains the binary equivalent of n |
| 10. | static String  toOctalString(long n) | Returns a String that contains octal equivalent of n |
| 11. | static String  toHexString(long n) | Returns a String that contains the hexadecimal equivalent of n. |

The use of some of the methods in **Long** class is given in program 10.4.

Program 10.4![](images/00013.jpeg)

/* This program illustrates some of the methods in Long class

This program requires jdk1.6 or higher

ka.somasundaram@gmail.com

*/

import java.io.Console;

class LongDemo {

public static void main(String args []) {

Long i1 = new Long(87456);

Console con= System.console();

Long i2 = new Long(“681523”);

con.printf(“%n i1 object:%4d%n”, i1);

con.printf(“%n 2*i1 value :%4d”, 2 * i1.longValue());

con.printf(“%n i2 object:%4d”, i2);

con.printf(“%n 2*i2 value :%4d”, 2 * i2.longValue());

con.printf(“%n is (i1 == i2)?: %b”, i1.equals(i2));

con.printf(“%n i1.compareTo(i2) :%4d”, i1.compareTo(i2));

Long i3 = Long.valueOf(“fa26”, 16);

con.printf(“%n Decimal equivalent of hex fa26= %4d”, i3);

con.printf(“%n byte value of Long object i3:%4d”, i3.byteValue());

con.printf(“%n long value of Long object i3:%4d”, i3.longValue());

con.printf(“%n double value of Long object i3:%6.0f”, i3.doubleValue());

long i4 = Long.parseLong(“85671”);

con.printf(“%n Long value of i4:%4d”, i4);

long inum = 972347;

String binstr=Long.toBinaryString(inum);

con.printf(“%n binary equivalent of decimal%4d = %12s%n”, inum, binstr);

binstr=Long.toHexString(inum);

con.printf(“%n hexadecimal equivalent of decimal%4d = %6s%n”, inum, binstr);

con.printf(“%n Size of Long:%2d bits%n”, Long.SIZE);

con.printf(“%n Minimum value of Long:%d”, Long.MIN_VALUE);

con.printf(“%n Maximum value of Long :%d%n “, Long.MAX_VALUE);

}

}

The above program gives the following output shown in Fig. 10.4.

![](images/00122.jpeg)

**Fig. 10.4** Output screen for program 10.4

10.1.5 Float Class

The **Float** class wraps the float type. The constructors in Float are:

Float(double x)

Float(float x)

Float(String s)

where s is a String representation of a float.

The **Float** class has the following additional predefined constants:

| *Constant* | *Description* |
| NaN | Not a Number |
| POSITIVE_INFINITY | + ∝ |
| NEGATIVE_INFINITY | – ∝ |
| MAX_EXPONENT | Maximum exponent value |
| MIN_EXPONENT | Minimum exponent value |

Apart from methods given in Table 10.1, additional methods defined in **Float** are given in Table 10.6.

**Table 10.6** Additional methods defined in Float class

| *Method* | *Purpose of the Method* |
|  1. | static Float valueOf(String s) | Returns a Float object of the String s |
|  2. | int compareTo (Float f) | Compares the numerical value of the invoking object with f; returns 0, if both are equal, negative if f>object and positive if f<object |
|  3. | boolean equals(Float f) | Returns true if the invoking object is equal to f, otherwise false. |
|  4. | static float   parse Float(String s) | Returns the float equivalent of the number contained in the String s using radix 10 |
|  5. | static String toString(float x) | Returns a String equivalent of x |
|  6. | boolean isInfinite() | Returns true if the invoking object contains an infinite value, otherwise false |
|  7. | static boolean isInfinite(float x) | Returns true if x is infinite, otherwise false |
|  8. | boolean i sNaN() | Returns true if the invoking object contains a value that is not a number, otherwise false |
|  9.  | static boolean is NaN(float x) | Returns true if x is not a number, otherwise false |

The following program 10.5 illustrates some of the methods defined in **Float** class:

Program 10.5![](images/00013.jpeg)

/* This program illustrates some of the methods defined in

the class Float

This program requires jdk1.6 or higher

ka.somasundaram@gmail.com

*/

import java.io.Console;

class FloatDemo{

public static void main(String args []) {

Console con= System.console();

Float f1 = new Float(234.5621);

Float f2 = new Float(745.32f);

Float f3 = new Float(“562.64”);

con.printf(“%n Float object f1 : %6.2f”,f1);

con.printf(“%n Float object f2 : %6.2f”,f2);

con.printf(“%n byte value of Float object f1 : %d”, f1.byteValue());

con.printf(“%n short value of Float object f1 : %d”, f1.shortValue());

con.printf(“%n float value Float object f1 : %6.2f”, f1.floatValue());

con.printf(“%n float value of Float object f3 : %6.2f”, f3.floatValue());

con.printf(“%n is(f1= = f2)? : %s”, f1.equals(f2));

con.printf(“%n f1.compareTo(f2): %d”, f1.compareTo(f2));

float f4 = Float.parseFloat(“765.89”);

con.printf(“%n float value from the string \”765.89\” : %6.2f”, f4);

con.printf(“%n isInfinte(4.5/0) ?: %s”,

Float.isInfinite((float)4.5 / 0));

con.printf(“%n is f1 is not a number? %s “, f1.is NaN());

con.printf(“%n Size of float: %2d bits”, Float.SIZE);

con.printf(“%n Maximum value for float : %8.2e”, Float.MAX_VALUE);

con.printf(“%n Minimum value for float : %8.2e”, Float.MIN_VALUE);

con.printf(“%n Positive infinity : %s”, Float.POSITIVE_INFINITY);

}

}

The above program gives the following output shown in Fig. 10.5.

![](images/00123.jpeg)

**Fig. 10.5** Output screen for program 10.5

10.1.6 Double Class

The **Double** class wraps the double type. The constructors in **Double** are:

Double (double x)

Double (String s)

The constants defined in **Float** class are also available for **Double** class.

Apart from methods given in Table 10.1, additional methods defined in **Double** are given in Table 10.7.

**Table 10.7** Additional methods defined in Double class

| *Method* | *Purpose of the Method* |
| 1. | static Double valueOf(String s) | Returns Double object of the String s |
| 2. | int compareTo(Double d) | Compares the numerical value of the invoking object with d; returns 0, if both are equal, negative if d>object and positive if d<object |
| 3. | boolean equals(Double d) | Returns true if the invoking object is equal to d, otherwise false |
| 4. | static double parseDouble(String s) | Returns the double   equivalent of the number contained in the String s using radix 10 |
| 5. | static String toString(double d) | Returns the string equivalent of d |
| 6. | boolean isInfinite() | Returns true if the invoking object contains an infinite value, otherwise false |
| 7.  | static boolean isinfinite (double d) | Returns true if d is infinite, otherwise false |
| 8.  | boolean isNan() | Returns true if the invoking object contains a value that is not a number, otherwise false |
| 9. | static boolean isNaN(double d) | Returns true if d is not a number, otherwise false |

Program 10.6 illustrates some of the methods defined in Double class.

Program 10.6![](images/00013.jpeg)

/* This program illustrates some of the methods defined in the class Double

This program requires jdk1.6 or higher

ka.somasundaram@gmail.com

*/

import java.io.Console;

class DoubleDemo{

public static void main(String args []) {

Console con= System.console();

Double f1 = new Double(234.5621);

Double f2 = new Double(745.32f);

Double f3 = new Double(“562.64”);

con.printf(“%n Double object f1 : %6.2f”,f1);

con.printf(“%n Double object f2 : %6.2f”,f2);

con.printf(“%n byte value of Double object f1 : %d”, f1.byteValue());

con.printf(“%n short value of Double object f1 : %d”, f1.shortValue());

con.printf(“%n double value Double object f1 : %6.2f”,f1.doubleValue());

con.printf(“%n float value of Double object f3 : %6.2f”, f3.floatValue());

con.printf(“%n is(f1= = f2)? : %s”, f1.equals(f2));

con.printf(“%n f1.compareTo(f2) : %d”, f1.compareTo(f2));

double f4 = Double.parseDouble(“765.89”);

con.printf(“%n double value from the string \”765.89\” : %6.2f”,f4);

con.printf(“%n isInfinte(4.5/0) ?: %s”, Double.isInfinite((float)4.5 / 0));

con.printf(“%n is f1 is not a number? %s “ , f1.isNaN());

con.printf(“%n Max exponent value of double: %2d “, Double.MAX_EXPONENT);

con.printf(“%n Min exponent value of double: %2d” Double.MIN_EXPONENT);

con.printf(“%n Size of double : %2d bits”, Double.SIZE);

con.printf(“%n Maximum value for double : %8.2e”, Double.MAX_VALUE);

con.printf(“%n Minimum value for double : %8.2e”, Double.MIN_VALUE);

con.printf(“%n Positive infinity : %s”, Double.POSITIVE_INFINITY);

}

}

The above program gives the following output shown in Fig. 10.6.

![](images/00124.jpeg)

**Fig. 10.6** Output screen for program 10.6

10.2 THE CHARACTER CLASS

The **Character** class wraps the char type. The constructor for this class is Character (char C).

The **Character** class has the following predefined constants:

| *Constant* | *Description* |
| MAX_RADIX | The largest radix |
| MIN_RADIX | The smallest radix |
| MAX_VALUE | Maximum value of character |
| MIN_VALUE | Minimum value of character |

Some of the methods defined in Character are given in Table 10.8.

**Table 10.8** Methods defined in Character class

| *Method* | *Purpose of the Method* |
|  1. | char charValue() | Gets the character |
|  2. | static boolean i sDefined(char c) | If c is defined in Unicode, it returns true, otherwise false |
|  3. | static boolean isDigit(char c) | If c is a digit, it returns true, otherwise false |
|  4. | static boolean isLetter(char c) | If c is a letter, it returns true, otherwise false |
|  5. | static boolean isLowerCase(char c) | If c is in lowercase, it returns true, otherwise, false |
|  6. | static boolean isUpperCase(char c) | if c is in uppercase, it returns true, otherwise false |
|  7. | static boolean isWhiteSpace(char c) | If c is a white space, it returns true, otherwise false |
|  8. | static char toLowerCase(char c) | Converts c to lower case |
|  9. | static char toUpperCase(char c) | Converts c to upper case |
| 10. | int compareTo(Character c) | Compares the object c with the invoking object and returns 0 if both are equal, negative if c>object and positive if c < object |
| 11. | static boolean isLetterOrDigit(char c) | Returns true if the character is letter or digit otherwise false. |
| 12. | static boolean isWhitespace(char c) | Returns true if the character is Java whitespace character, otherwise false. |

Program 10.7 illustrates some of the methods defined in **Character** class.

Program 10.7![](images/00013.jpeg)

/* This program illustrates some of the methods defined in the class Character

This program requires jdk1.6 or higher

ka.somasundaram@gmail.com

*/

import java.io.Console;

class CharacterDemo{

public static void main(String args []) {

Console con= System.console();

char chary[]={‘z’,’g’,’5’};

con.printf(“Code point for %c is : %dA%n”,

chary[1],Character.codePointAt(chary,1));

con.printf(“%n Size of character : %2d bits”,

Character.SIZE);

con.printf(“%n Maximum radix for charatcer : %d”,

Character.MAX_RADIX);

con.printf(“%n Minimum radix for character : %d”,

Character.MIN_RADIX);

}

}

The above program gives the following output shown in Fig. 10.7.

![](images/00125.jpeg)

**Fig. 10.7** Output screen for program 10.7

10.3 THE BOOLEAN CLASS

The **Boolean** class wraps the boolean type. The constructors in **Boolean** class are :

Boolean(boolean b)

Boolean(String s)

where b is a boolean value true or false and s is a string containing boolean value.

Some of the methods defined in **Boolean** are given in Table 10.9.

**Table 10.9** Methods defined in Boolean class

| *Method* | *Purpose of the Method* |
| 1. | boolean booleanValue() | Gives the boolean equivalent, otherwise false |
| 2. | boolean equals(Boolean b) | Gives true if the invoking object and b are equal, otherwise false |
| 3. | static Boolean valueOf(String s) | Gives true if the String s contains true, otherwise false |

After this chapter, you should have learned the following:

*   Wrapper classes help to create objects for basic types.
*   Basic type of parameters can be passed by reference using wrapper class objects.

In the next chapter, you will learn about exception handling in Java program.

EXERCISE-10

**I. Fill in the blanks**

10.1Wrapper classes help to create objects for .......................... types.

10.2Using wrapper classes simple types .......................... be passed by reference to methods.

10.3The superclass of Integer and Long is .......................... .

10.4The wrapper classes are defined in .......................... package.

10.5 .......................... method converts a string represented in a number system with r as radix to byte value.

**II. Write Java programs for the following:**

10.6Write a class called Convert with one method that takes Integer as object and prints out two times the int value of the object while another method that takes up Integer object and prints out three times the double value of the object. Write another class Main, create an Integer object and Convert object. Call the two methods in the Convert object and find out the int and double values.

10.7Write a program that converts the string “7845” to its binary, octal and hexadecimal equivalents.

10.8Write a program that finds uppercase letters, white spaces and digits of a character array.

10.9Write a program that converts the characters in the given char array to uppercase letters.

10.10Write a program that converts the int type numbers a=34 and b=36 to binary string. Bitwise AND a and b and print out the binary string of the resulting value.

11ExceptionsIn this chapter, you will learn about exceptions. Exceptions are abnormal conditions occurring in a program. When such exceptions occur, the program aborts or hangs, leaving the user without any information. This chapter explains how to manage such situations.

A Java program, compiled and error-free, will execute and complete the task for which the program has been developed. However, there are occasions in which a program running smoothly in normal conditions may encounter errors in abnormal conditions such as divide by zero. Such errors occurring in abnormal conditions are called exceptions. The errors may occur internally in the program code or through the resources the program is trying to access. The sources of errors may be user-input errors such as giving a wrong URL, device errors such as printer not ready, physical limitations such as disk full or memory not enough and code errors like array index out of bound, trying to access an empty stack and divide by zero error. If such exceptions are not caught, the program aborts at the point of occurring of the exception. Java provides appropriate mechanisms to handle such exceptions. The objective of handling exceptions is to inform the user about the error or to take an alternative path to overcome the problem and complete the remaining task. This helps the user to know what is happening inside the program. In the absence of such messages, the user may end up with unexpected output.

11.1 TYPES OF EXCEPTIONS

All exceptions in Java are handled by a superclass **Throwable** defined in java.lang package. The **Throwable** class has two subclasses, **Exception** and **Error**. **Exception** again has two subclasses, **IOException** and **RuntimeException.** The Exception hierarchy is given in Fig. 11.1.

![](images/00126.jpeg)

**Fig. 11.1** The Exception Hierarchy

RuntimeException

Exception occurring in the program code at runtime are handled in this class. Divide by zero error, array index out of bound, wrong cast and null pointer access are of this type. These types of errors could have been avoided, if the programmer had taken care to write the program. These exceptions can be caught and handled by Java.

IOException

Exceptions occurring while accessing I/O devices are handled in this class. File not found, end of file encountered are of this type.

Exception

In this class, a user can create one's own Exception and use it in Java program. All Exceptions under this class are to be caught and handled.

Error

Errors which are beyond the control of the programmers are dealt in this class. Disk full and memory not enough are of this type. Java does not provide any mechanism to handle them and should not be caught.

11.2 CATCHING EXCEPTIONS

Java developers have identified commonly occurring exceptions and they are specified in the Exception. When such exceptions appear in a program at runtime, they are to be caught and handled. The Exception is caught by **try...catch** mechanism. The general form of the **try...catch** block is:

| try | { ... |  |
|  |  | statements that may give |
|  |  | exceptions |
|  | } | catch (ExceptionType e1){ statements to handle
Exception Type1 |
|  | } | catch (ExceptionType e2) { statements to handle ExceptionType2 |
|  | } | finally { statements to be executed
whether an exception occurs or not |
|  | } |  |

The terms **try, catch** and **finally** are Java keywords. e1 and e2 are errors. In the **try** block, the statements that are suspected to cause exceptions are placed. ExceptionType1 and ExceptionType2 are the different exception types. The **catch** block contains statements that are to be executed in the event of an **Exception** occurring..

Multiple **catch** blocks for single **try** block can be set up, each **catch** block dealing one specific type of exception out of several occurring inside the **try** block. The **try** block may be constructed to trap any number of exceptions. If an exception occurs in the **try** block and if there is no matching **catch** block, the program is aborted. In case no **Exception** occurs inside the **try** block, all **catch** block statements will be skipped and only statements in the **finall**y block will be executed. This finally block will be executed irrespective of whether an **Exception** occurs or not. The **catch** block statements are operative only for the preceding **try** block. The **finally** block is optional.

The following program 11.1 contains an array out of bounds Exception that is caused during the runtime and aborted without completing the program.

Program 11.1![](images/00013.jpeg)

/* This program illustrates the Exception occurring in a program.

* This program requires jdk1.6 or higher

* ka.somasundaram@gmail.com

*/

class ExceptionDemo1 {

public static void main(String args[]) {

int mat[] = new int[5];

mat[5] = 755;

System.out.printf("Last element of mat = %d\n", mat[5]);

}

}

The above program gives the following error message as shown in Fig. 11.2.

![](images/00127.jpeg)

**Fig. 11.2** Fig. 11.2 Output screen for program 11.1

The above error message indicates that an **ArrayIndexOutOfBoundsException** as defined in java.lang package has occurred in the main method of the program ExceptionDemo1.java at line 5\. In program 11.1, the array index for the mat array can take values from 0 to 4 only. However the program tried to access an element at index 5, which is out of bounds.

Now, we will make use of an exception-handling feature of Java to handle the Exception using **try** and **catch.** The following program 11.2, uses the **try...catch** structure to handle the array out of bounds Exception:

Program 11.2![](images/00013.jpeg)

/* This program illustrates the catch of an Exception in a program.

* This program requires jdk1.6 or higher for compile and execute.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Catch {

public static void main(String args[]) {

Console con = System.console();

int mat[] = new int[5];

try {

mat[5] = 75;

} catch (ArrayIndexOutOfBoundsException e) {

con.printf("Array index out of bounds in mat array\n");

mat[4] = 75;

}

con.printf("Beyond the exception point \n");

con.printf("Last element of mat = %d\n", mat[4]);

}

}

The above program gives the following output shown in Fig. 11.3.

![](images/00128.jpeg)

**Fig. 11.3** Fig. 11.3 Output screen for program 11.2

The output of the above program 11.2 shows that the program crossed the array out of bounds exception and completed the whole program. In the **catch** block, any statement that can provide remedy to the statement causing the exception may be placed.

In a **try** block, when an exception occurs, the control skips all statements from that point till the end of **try** block. Therefore, care must be taken to include a statement in a **try** block. In case, an exception occurs in a code and if it is not going to cause any problem to your results, then an empty block{} can be placed after the **catch** block. The following program 11.3 illustrates the above two concepts in a **try... catch** block overlapping with a for loop:

Program 11.3![](images/00013.jpeg)

/* This Program illustrates the multi catch of a try block.

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Multicatch {

public static void main(String args[]) {

int i, x, cons = 4;

Console con = System.console();

for (i = 1; i < 8; i++) {

try {

x = 25 / (cons – i);

con.printf("%n quot = %d\n", x);

} catch (ArithmeticException e) {

con.printf("\n Divide by zero error for i = %d%n", i);

} catch (ArrayIndexOutOfBoundsException e) {

}

}

}

}

The above program gives the following output shown in Fig. 11.4.

![](images/00129.jpeg)

**Fig. 11.4** Output screen for program 11.3

![](images/00011.jpeg)In a try ... catch block, when an exception occurs, all statements between the statement causing the exception and the end of the try block will be skipped. Hence a programmer must decide which statements are to be placed inside a try block.

11.2.1 Nested try Blocks

Nested **try** block, one **try** block enclosing another **try** block, is permitted in a Java program. The **catch** statements are operative for the corresponding statement blocks defined by { and }. The following program 11.4, illustrates the nested **try** block:

Program 11.4![](images/00013.jpeg)

/* This program illustrates the nested Try block.

* This program requires jdk1.6 or higher for compile and execute.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class NestedTry {

public static void main(String args[]) {

int vec[] = {3, 5, 4, 10, 2};

int nmr = 24;

int quot, sum = 0;

Console con = System.console();

for (int i = 0; i <= 5; i++) {

try {

quot = nmr / (2 – i);

try {

sum += vec[i];

} catch (ArrayIndexOutOfBoundsException e) {

con.printf(“Array index out of bounds at index(inner try) = %d%n”, i);

} catch (ArithmeticException e) {

con.printf(“Divide by zero error at i (inner try) = %d%n”, i);

}

con.printf(“Quotient = %d%n”, quot);

} catch (ArrayIndexOutOfBoundsException e) {

con.printf(“Array index out of bounds at index(outer try) = %d%n”, i);

} catch (ArithmeticException e) {

con.printf(“Divide by zero error at i ( outer try) = %d%n”, i);

}

}

con.printf(“Sum of numbers = %d%n”, sum);

}

}

The above program gives the following output shown in Fig. 11.5.

![](images/00130.jpeg)

**Fig. 11.5** Output screen for program 11.4

The above program finds quotient of integer division of the variable nmr by i-2 and finds the sum of the array vec with five elements. When the for loop is repeated, divide by zero error occurs and the control skips all the statements till the end of outer try block and looks for the matching catch statement. Thus the catch statement in the outer try block for **ArithmeticException** is caught and the **catch** block statements are executed. Since the control has skipped all statements between the occurrence of the exception and the corresponding }, of the corresponding **try** block, sum += vec[i] for i=2 is not executed. Hence, the final value of sum gives only 20 instead of 24\. When the array index i takes the value 5, **ArrayIndexOutOfBoundsException** occurs in the inner try block and is caught and handled. The control then exits the inner try block and the remaining two print statements are executed.

11.2.2 Hierarchy of Multiple Catch Blocks

When multiple catch blocks are set up for a try block, then the subclass exceptions are to be caught first and then the superclass exceptions. In case superclass exception handlers are placed first, followed by handlers for subclass exceptions, then Java compiler will give TypeException has already been caught. Suppose in a multiple catch block, the first catch block catches an exception of type **Exception** followed by another catch block to catch **ArithmeticException**, then ArithmeticException has already been caught error will occur. The following program 11.5 illustrates this:

Program 11.5![](images/00013.jpeg)

/* This program illustrates the order of catch statement

* This program will give compile error

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Catchorder {

public static void main(String args[]) {

int vec[] = {3, 5, 4, 10, 2};

int nmr = 24;

int quot, sum = 0;

Console con = System.console();

for (int i = 0; i <= 5; i++) {

try {

quot = nmr / (2 – i);

sum += vec[i];

con.printf(“%n Quotient = %2d”, quot);

} catch (Exception e) {

con.printf(“%n Divide by zero error at i =%2d “, i);

} catch (ArithmeticException e) {

con.printf(“%n Array index out of bounds at index = %2d”, i);

}

}

con.printf(“%n Sum of numbers = %2d”, sum);

}

}

The above program when compiled will give the following output shown in Fig. 11.6.

![](images/00131.jpeg)

**Fig. 11.6** Error screen for program 11.5

In the above program, the first catch block catches exception of a superclass **Exception** while the second catch block catches the ArithmeticException belonging to **RuntimeException,** which is a subclass of **Exception** (see Fig. 11.1). Hence, the compile error. If the order of the catch blocks is interchanged, the program will be error-free and can be executed.

![](images/00011.jpeg)In a multiple catch block, the subclass exceptions are to be caught first followed by superclass exceptions.

11.3 RETHROWING EXCEPTIONS

When an exception is caught in a method, it is up to the programmer to deal with it. If it is known how to handle the exception, it can be handled, otherwise it can be rethrown. Rethrowing is done through the **throw** clause. Unless the rethrown exception is caught again, the program will abort. After the **throw** statement, no other statement should be placed in that block. If any statement is placed after the **throw** statement in that block, Java will give code not reached, compile error. The following program 11.6 illustrates how to rethrow an exception. The exception is not recaught and hence aborts after rethrow.

Program 11.6![](images/00013.jpeg)

/* This program demonstrates rethrowing an exception

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Rethrow {

public static void main(String args[]) throws Exception {

Console con = System.console();

int nmr = 24, i, quot;

for (i = 0; i <= 5; i++) {

try {

quot = nmr / (i – 2);

con.printf(“\n Quotient = %d\n”, quot);

} catch (ArithmeticException e) {

con.printf(“\n Rethrowing the exception at i = %d\n”, i);

throw e;

}

}

}

}

The above program gives the following output shown in Fig. 11.7.

![](images/00132.jpeg)

**Fig. 11.7** Output screen for program 11.6

The following program 11.7 illustrates recatching a rethrown exception and makes the program to complete its remaining task:

Program 11.7![](images/00013.jpeg)

/* This program demonstrates rethrowing an exception

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Recatch {

public static void main(String args[]) {

int nmr = 24, i, quot;

Console con = System.console();

for (i = 0; i <= 5; i++) {

try {

try {

quot = nmr / (i – 2);

con.printf("Quotient = %d%n", quot);

} catch (ArithmeticException e) {

con.printf("Rethrowing the exception at i =%d%n", i);

throw e;

}

} catch (ArithmeticException e) {

con.printf("Recaught %s %n", e);

}

}

}

}

The above program gives the following output shown in Fig. 11.8.

![](images/00133.jpeg)

**Fig. 11.8** Output screen for program 11.7

11.4 CREATING YOUR OWN EXCEPTIONS

All the exceptions we have seen so far are defined inside the Java language. We have seen how to catch them and rethrow them. There may be programs that may create errors, which are not covered in Java's predefined exceptions. If any such error occurs, it can be brought under the **Throwable** or its subclasses. This provides a mechanism by which a new exception can be created. The general form of creating an exception is:

new ThrowableClass();

or

new ThrowableClass(String s)

The ThrowableClass can be **Throwable** or its subclasses. There are two constructors for **Throwable** and its subclasses. The first constructor needs no argument and the second constructor takes a string as an argument. The string is assigned as the name of the exception. For example, the following statements create a new exception called MyException with an argument and is thrown using **throw** clause.

Throwable MyException = new Throwable("Help Me");
throw MyException;

The following program 11.8 creates a new exception, throws it and catches it.

Program 11.8![](images/00013.jpeg)

/*This program illustrates the creation of a new exception

* using Throwable class.

* This program requires jdk1.6 or higher for compile and execute.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class MyException {

public static void main(String args[]) {

Throwable MyExpn = new Throwable(“Help Me”);

Console con = System.console();

try {

con.printf(“A new excetion is thrown%n”);

throw MyExpn;

} catch (Throwable e) {

con.printf(“The exception is caught here.%n%nThe exception is %s%n”, e);

}

}

}

The above program gives the following output shown in Fig. 11.9.

![](images/00134.jpeg)

**Fig. 11.9** Output screen for program 11.8

The following program 11.9 creates an **Exception** subclass named NewExp, creates an object of that type, throws it and catches it.

Program 11.9![](images/00013.jpeg)

/*This program illustrates the creation of a new exception

* using the subclass of Exception.

* This program requires jdk1.6 or higher for compile and execute.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class NewExp

extends Exception {

Console con = System.console();

NewExp(String s) {

con.printf(“Untamed exception is thrown out:%s%n”, s);

}

public static void main(String args[]) {

Console con = System.console();

NewExp ne = new NewExp(“Lion”);

try {

throw ne;

} catch (Exception e) {

con.printf(“I caught that exception and tamed it : %s%n”, e);

}

}

}

The above program gives the following output shown in Fig. 11.10.

![](images/00135.jpeg)

**Fig. 11.10** Output screen for program 11.9

11.5 BROADCASTING THAT A METHOD THROWS EXCEPTION

When a method is developed for carrying out a task, it may generate various types of exceptions. Some of the exceptions generated cannot be handled by the method itself. Therefore, it is important to broadcast that the method is going to throw an exception, so that the caller of that method can handle the exception appropriately. Exceptions of type **Error** that cannot be handled at all and **RuntimeException** that could have been avoided by the programmer should not be broadcast. Only exceptions other than **Error** or **RuntimeException** can be broadcast. The broadcasting is done using the **throws** keyword. The broadcasting is made while declaring the method. The general form of broadcasting that a method **throws** an exception is:

return-type methodname(parameter_list) throws Exception1,

Exception2 {

method_body

}

For example, the following method broadcasts two exceptions:

static double readDouble() throws IOException,

ParseException {

.

.

.

String s = br.readLine();

}

In the above example, the method readDouble() announces that the method is likely to cause two exceptions, **IOException** and **ParseException.** The following program 11.10 illustrates how to broadcast that a method throws an exception.

Program 11.10![](images/00013.jpeg)

/* This program illustrates broadcasting that its

* method is going to throw an exception.

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Cal {

int x, y;

int Process(int a, int b) throws Exception {

Console con = System.console();

x = a;

y = b;

con.printf(“I dont know what to do these nmbers %d and %d%n”, a, b);

throw new Exception(“AVAJ”);

// return (a+b); This statment can not be placed after throw.

//will give compile error

}

}

class Broadcast {

public static void main(String args[]) {

Cal cl = new Cal();

Console con = System.console();

try {

cl.Process(10, 25);

} catch (Exception e) {

con.printf(“The thrown Excepion is: %s%n\t and is caught in main%n”, e);

con.printf(“Sum of the two numbers is %d%n”, (cl.x + cl.y));

}

}

}

The above program gives the following output shown in Fig. 11.11.

![](images/00136.jpeg)

**Fig. 11.11** Output screen for program 11.10

11.6 THE finally BLOCK

In a **try...catch** block, all statements will be executed, if no exception occurs. When an exception occurs, the statements placed in between the point of occurring of the exception and the end of the block will be skipped and the control looks for a matching catch block. In certain problems, it is essential to execute certain statements, like closing a file, irrespective of whether an exception occurs or not. Such essential statements are placed in the **finally** block. Program 11.11 illustrates the use of **finally** block.

Program 11.11![](images/00013.jpeg)

/* This program illustrates the finally block

* This program requires jdk1.6 or higher

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Finally {

public static void main(String args[]) {

int i, x, cons = 2;

Console con = System.console();

for (i = 1; i < 4; i++) {

try {

x = 25 / (cons – i);

con.printf(“quot = %d%n”, x);

} catch (ArithmeticException e) {

con.printf(“Divide by zero error for i = %d%n”, i);

} finally {

con.printf(“Exception or no Exception this will be printed always%n”);

}

}

}

}

The above program gives the following result shown in Fig. 11.12.

![](images/00137.jpeg)

**Fig. 11.12** Output screen for program 11.11

![](images/00011.jpeg)The statements in a **finally** block are always executed, irrespective of whether an exception occurs or not.

11.7 CHECKED AND UNCHECKED EXCEPTIONS

Java developers have identified certain exceptions which must be made known to the programmer at the compile time itself. Such exceptions are listed and the compiler checks whether any of the listed exceptions occur in a program during compilation. Such exceptions are called checked exceptions. Exceptions that are not listed in the list are identified during runtime. Such exceptions are called unchecked exceptions. Only checked exceptions are to be broadcast in a **throws** clause. Table 11.1 gives some checked exceptions and Table 11.2 gives some unchecked exceptions.

**Table 11.1** Some checked exceptions

| *Exception* | *  Cause for the Exception* |
|          1. | ClassNotFoundException | Class not found |
|          2. | CloneNotSupportedException | Trying to clone an object which has not implemented clonable interface |
|         3. | IllegalAccessException | Access to a class is refused |
|          4. | InterruptedException | One thread is interrupted by another thread. |
|          5. | NoSuchMethodException | The referred method does not exist. |

**Table 11.2** Some unchecked exceptions

| *Exception* | *Cause for the Exception* |
|         1. | ArithmeticException | Arithmetic error |
|          2. | ArrayIndexOutOfBoundsException | Array index is beyond the bounds |
|         3. | ClassCastException | Invalid cast |
|         4. | IllegalArgumentException | Invalid arguments passed to a method |
|         5. | NegativeArraySizeException | Array with negative index |
|          6. | NullPointerException | Invalid use of null |
|         7. | NumberFormatException | Incorrect conversion of string to a number |
|          8. | StringOutOfBoundsException | Trying to access a string beyond its bounds |

After reading this chapter, you should have learned the following:

*   What is an exception?
*   The types of exception
*   Establishing try...catch block
*   The use of throw and throws clause
*   Creating your own exception

In the next chapter, you will learn about I/O classes.

EXERCISE–11

**I. Fill in the blanks**

11.1An abnormal condition occurring in a Java program is called ...........................

11.2The programmer avoidable errors are exceptions of type ........................... .

11.3Exceptions arising out of memory and memory not enough are of the type .......................... . They are .......................... be caught.

11.4The codes inside the .......................... block of an exception handling structure will be executed irrespective of whether an exception occurs or not.

11.5When exceptions belonging to a superclass and subclass occur inside a try block, the .......................... class exception must be caught first.

11.6User-defined exceptions can be created using .......................... class.

11.7When a method cannot handle an Exception that is generated in it, the method must declare it using the keyword .......................... .

11.8Exceptions that are identified during compile time are called .......................... exception.

**II. Write Java programs for the following:**

11.9It is required to compute the following expression:

![](images/00138.jpeg)

for different values of x = 1.0 to 5.0 in steps of 0.5 and y = 0 to 4.0 in steps of 0.5\. Write a Java program to compute the values of f by including an appropriate exception handling block when x = y.

11.10A mark list containing register number and marks for a subject is given. The marks and register number are to be read. If the marks are < 0, user-defined IllegalMarkException is thrown out and handled with the message "Illegal Mark". For all valid marks, the candidate will be declared as "PASS" if the marks are equal to or greater than 40, otherwise it willl be declared as "FAIL". Write a class called IllegalMarkException by extending the Exception. Write another class MarkProcess to process the mark. In the MarkProcess class write a Validation (int mark) method, which if marks are <0, will throw an Exception of type IllegalMarkException. Write another method Result() which will declare the result. Write a class containing main method that will create an object of type MarkProcess and call the methods in it to declare the result.

11.11Write a class to sort the given set of n integers in descending order. Include a try block to locate the array index out of bounds exception and catch it.

12Input and Output ClassesIn this chapter, you will learn about input/output handling process. Java treats all data as a stream of bytes or characters. A large number of classes, to deal with disk files, memory and source/destination independent process, are available in Java. Few classes are explained in this chapter.

12.1 I/O STREAMS

Java’s input/output (I/O) operations are intricate, complex to understand, but more flexible and powerful. Java developers have focused their attention for non-keyboard oriented data handling. They wanted to perform platform independent I/O operations and hence, the complexity. All I/O operations in Java are stream-based. All the data is treated as a stream of bytes or characters. The streams start from or end with files, memory, monitor, keyboard and network sockets. The sources from where data are read from is called input stream. The sink to which the data are written into is called output stream. Since Java’s two-byte, unicode characters are different from the conventional single-byte characters, Java has two types of streams, byte stream and character stream. A character stream deals with unicode characters. Each stream has its own input stream and output stream classes. In this chapter few byte stream classes are explained. I/O operations of byte stream are handled by two abstract classes **InputStream** and **OutputStream**. Similarly, the character stream has **Reader** and **Writer** abstract classes. The I/O related classes are available in **java.io** package and are to be imported into the programs which are using I/O classes.

All the streams, InputStream, OutputStream, Writer and Reader, are opened automatically when their objects are created.

![](images/00011.jpeg)Data used in Java are handled in two streams, byte stream and character stream.

Few classes that are dealt in this chapter are:

File

FileInputStream

FileOutputStream

DataInputStream

DataOutputStream

12.2 THE FILE CLASS

The **File** class is used only to know the details about a file. It cannot be used to read or write bytes into a file. It helps to study a file before handling it. The File class has the following constructors:

(i) File(String dirpath)

(ii) File(String dirpath, String filename)

(iii) File(File object, String filename)

where, dirpath is directory path, filename is the name of the file and object is File type object.

Some of the methods defined in **File** class are given in Table 12.1.

**Table 12.1** Some of the methods defined in File class

| *Method* | *Purpose of the Method* |
| 1. | String getName() | Returns the name of the directory or file of the invoking object |
| 2. | String getPath() | Returns the path of the invoking object |
| 3. | String getAbsolutePath() | Returns the absolute path of the invoking object |
| 4. | String getParent() | Returns the name of the parent directory of the invoking object |
| 5. | boolean exists() | Returns true if the dir/file object exists, otherwise false |
| 6. | boolean canWrite() | Returns true if the File object is writable, otherwise false |
| 7. | boolean canRead() | Returns true if the File object is readable, otherwise false |
| 8. | boolean isDirectory() | Returns true if the invoking object is a directory, otherwise false |
| 9. | boolean isFile() | Returns true if the invoking object is a file, otherwise false |
| 10. | boolean isHidden() | Returns true if the File object is hidden, otherwise false |
| 11. | long lastModified() | Returns a long value representing the last modified date in milliseconds |
| 12. | long length() | Returns a long value representing the size of the file in bytes |
| 13. | boolean renameTo (File newname) | Renames the File object with the new name; returns true upon successful renaming, otherwise false |
| 14. | boolean delete() | Deletes the file of the invoking object; returns true on successful deletion, otherwise false |
| 15. | boolean setReadOnly() | Sets the file of the invoking object to read only mode; returns true on successful setting, otherwise false |
| 16. | void deleteOnExit() | Deletes the file of the invoking object upon the termination of Java Virtual Machine |
| 17. | String[] list() | Lists the files in the directory of the invoking object and returns a String array |
| 18. | boolean setWritable(boolean writable, boolean owneronly) | Sets the owner's or everybody's write permission for this pathname. |
| 19. | boolean setWritable(boolean writable) | Sets the owner's write permission for this pathname. |
| 20. | boolean setReadable(boolean readable, boolean owneronly) | Sets the owner's or everybody's read permission for this pathname. |
| 21. | boolean setReadable(boolean readable) | Sets  the owner's  read permission for this pathname |
| 22. | boolean setExecutable(boolean executable, boolean owneronly) | Sets the owner's or everybody's execute permission for this pathname |
| 23. | boolean setExecutable(boolean executable) | Sets the owner's execute permission for this pathname |
| 24. | boolean canExecute() | Tests whether the application can execute the file denoted by this pathname. |
| 25. | long getTotalSpace() | Returns the size of the partition specified by this partitionname. |
| 26. | long getFreeSpace() | Returns the number of unallocated bytes in the partition specified by this partitionname. |
| 27. | long getUsableSpace() | Returns the number of bytes available to this virtual machine in the partition specified by this partition name. |

The following program 12.1 illustrates some of the methods in **File** class:

Program 12.1![](images/00013.jpeg)

/*This program illustrates some of the methods in File class

*This program requires jdk1.6 or higher.

*ka.somasundaram@gmail.com

*/

import java.io.*;

class FileDemo {

public static void main(String args[]) {

Console con = System.console();

boolean bstr1, bstr2;

String str1, str2;

File cpart = new File(“E:”);

double ts, fs, giga = 1.0 * 1024 * 1024 * 1024;

ts = cpart.getTotalSpace() / giga;

fs = cpart.getFreeSpace() / giga;

con.printf(“ E Partition:\n”);

con.printf(“ Total Space: %4.1f GB\n”, ts);

con.printf(“ Free Space : %4.1f GB\n”, fs);

File fpath = new File(“E:/book-rev/chap12”);

File fname = new File(fpath, “FileDemo.java”);

con.printf(“ Dir path: %s\n”, fname.getPath());

con.printf(“ File Name :%s\n”, fname.getName());

con.printf(“ File Size :%d bytes\n”, fname.length());

str1 = fpath.getName();

bstr2 = fpath.isDirectory();

con.printf(“Is %s is a directory?:%b\n”, str1, bstr2);

str1 = fname.getName();

bstr2 = fname.isFile();

con.printf(“ Is %s is a file?: %b\n”, str1, bstr2);

str1 = fpath.getName();

bstr2 = fname.exists();

con.printf(“Is the file %s exists?:%b\n”, str1, bstr2);

str1 = fname.getName();

bstr2 = fpath.exists();

con.printf(“ Is the directory %s exists ?:%b\n”, str1, bstr2);

long mdf = fpath.lastModified();

con.printf(“Modified on (in long form):%d \n”, mdf);

con.printf(“Modified on (converted to date): %1$td-%1$tm-%1$ty \n”, mdf);

String dirlist[] = fpath.list();

int n = dirlist.length;

//Print only first five files if more than 5 files are in the directory

n = (n > 5) ? 5 : n;

con.printf(“\n Directory of %s\n”, fpath.getName());

for (int i = 0; i < n; i++) {

con.printf(“ %s\n”, dirlist[i]);

}

}

}

The above program gives the following output shown in Fig. 12.1.

![](images/00139.jpeg)

**Fig. 12.1** Output screen for program 12.1

![](images/00011.jpeg)A File class is used to study the properties of a file. This class cannot be used to read data from a file or write data into a file.

12.3 BYTE STREAM

In this, stream data are accessed as a sequence of bytes. All types other than character or text are dealt in this stream. This stream, as mentioned earlier, has two abstract classes, **InputStream** and **OutputStream**. Since **InputStream** and **OutputStream** are abstract classes, objects of this type cannot be created. However, object references of this type can be declared. These two classes have abstract and concrete methods. The abstract methods are implemented in the subclasses.

12.3.1 InputStream

The **InputStream** has methods given in Table 12.2. These methods are used to input bytes from input stream. All the methods can throw **IOException.**

**Table 12.2** Methods defined in InputStream

| *Method* | *Purpose of the Method* |
| 1. | abstract int read() | Reads one byte and returns an int representation of that byte; returns –1 at the end of the stream |
| 2. | int read(byte b[]) | Reads into an array of bytes b and returns the number of bytes read; reads a maximum of b.length bytes, returns –1 at the end of the stream |
| 3. |  int read(byte b[], int off , int len) | Reads len number of bytes into the byte array b, starting at b[off ] and returns the number of bytes read; returns –1 at the end of the stream |
| 4. |  int available() | Returns the number of bytes available for reading |
| 5. |   void close() | Closes the input stream |
| 6. |  void mark(int marklen) | Puts a mark at the current position and remembers it until marklen bytes are read |
| 7. |   boolean markSupported() | Returns true if the stream supports mark() |
| 8. |   void reset() | The read control is reset to the previous set mark. Subsequent read() will reread these bytes. |
| 9. |  long skip(long m) | Skips m bytes of the input stream and returns the actual number of bytes skipped |

12.3.2OutputStream

The abstract class **OutputStream** has methods given in Table 12.3\. These methods are used to send bytes to the output stream. All the methods can throw **IOException**.

**Table 12.3** Methods defined in OutputStream

| *Method* | *Purpose of the Method* |
| 1. | abstract void write(int b) | Writes a single byte b to an output stream |
| 2. | void write(byte b[]) | Writes an array of byte b to an output stream |
| 3. | void write(byte b[], int off, int len) | Writes len number of bytes starting from b [off] to an output stream |
| 4. | void flush() | Flushes the output buffer; that is, it sends any buffered byte to its destination |
| 5. | void close() | Closes the output stream |

12.4 DISK FILE HANDLING

The two abstract classes, **InputStream** and **OutputStream**, have a number of concrete subclasses, which implement the abstract methods. Only objects of these subclasses can be created for input stream and output stream. **FileInputStream** and **FileOutputStream** are subclasses of **InputStream** and **OutputStream** respectively. These two are used for handling disk files.

12.4.1FileInputStream

This class is used to read bytes from a disk file. The **FileInputStream** class has the following constructors:

(i) FileInputStream(String filename)
Creates a file input stream, using the file mentioned in filename

(ii) FileInputStream(File fobject)
Creates a file input stream, using the information given in the Object fobject

Both the constructors can throw **FileNotFoundException.**

All the superclass methods given in Table 12.2, except mark(), reset() and close(), are overridden by this class. Methods in this stream can only read a byte or an array of bytes. Therefore, only byte-oriented data can be handled in this stream.

The following program 12.2 shows the use of **FileInputStream**. This program reads a byte at a time from a file as int and prints it out as such.

Program 12.2![](images/00013.jpeg)

/* This program illustrates the use of FileInputStream

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.*;

class Fileinput1 {

public static void main(String args[]) {

Console con = System.console();

int c;

String path = “test.dat”;

try {

FileInputStream fis = new FileInputStream(path);

while ((c = fis.read()) != –1) {

con.printf(“%d”, c);

}

fis.close();

} catch (FileNotFoundException e) {

con.printf(“File not found”);

} catch (IOException e) {

con.printf(“FIle read error”);

}

}

}

The above program gives the following output:

**6532663267131049505132515253325455561310**

**4549325656543254495713105250325350325755**

It can be seen from the above result, the (ASCII) bytes are read as int and printed as int using d conversion. To get visually readable bytes they are to be converted to **char** using C conversion and printed out as ASCII values (65 for A, 49 for 1, 32 for blank, 1310 for new line, etc). Modifying the print statement in the above program as:

**con.printf(“%c”, c);**

the following output is obtained:

**A B C**
**123 345 678**
**–1 886 619**
**42 52 97**

12.4.2 FileOutputStream

This class is used to write bytes into a disk file. The **FileOutputStream** class has the following constructors:

(i) FileOutputStream(String filename)
Creates a new file output stream by creating a new file with name filename; if a file already exists with that name, it will be deleted.

(ii) FileOutputStream(File fobject)
Creates a new file output stream using the information given in the object fobject

(iii) FileOutputStream(String filename, boolean append)
Creates a new file output stream using the file filename; if append is true, the data is appended at the end of the file.

All the constructors can throw an **IOException** or a **SecurityException**.

The following program 12.3 illustrates the use of FileOutputStream. This program copies an existing file to a new file. It then reads the new file and prints out the int bytes as char.

Program 12.3![](images/00013.jpeg)

/* This program illustrates the use of FileOutputStream

* This program requires jdk1.6 or higher

* ka.somasundaram@gmail.com

*/

import java.io.*;

class Fileoutput {

public static void main(String args[]) {

File fin = new File(“test.dat”);

File fot = new File(“out.dat”);

String fn;

Console con = System.console();

int c;

fn = fin.getName();

long size = fin.length();

con.printf(“The size of the file %s is %d bytes\n”, fn, size);

try {

FileInputStream fis = new FileInputStream(fin);

FileOutputStream fos = new FileOutputStream(fot);

con.printf(“\nThe file test.dat is copied to out.dat”);

while ((c = fis.read()) != –1) {

fos.write(c);

}

fis.close();

FileInputStream fis1 = new FileInputStream(fot);

con.printf(“\nThe following data are read from out.dat \n”);

int count = 0;

while ((c = fis1.read()) != –1) {

con.printf(“%c”, c);

count++;

}

con.printf(“\nThe size of file out.dat is %d bytes\n”, count);

fis1.close();

} catch (FileNotFoundException e) {

con.printf(“\n File not found “);

} catch (IOException e) {

con.printf(“\n I/O problem “);

}

}

}

The above program gives the following output shown in Fig. 12.2.

![](images/00140.jpeg)

**Fig. 12.2** Output screen for program 12.3

![](images/00011.jpeg)Disk files are handled by **FileInputStream** and **FileOutputStream** classes. Both are byte stream.

12.5 FILTERED BYTE STREAMS

Each stream in Java provides methods to access the data in different forms. The basic byte streams access the data in byte form. The raw bytes cannot be used for any useful purpose. For converting bytes to useful forms such as char, string, int, etc., Java has several streams. These streams work on other streams and convert byte to useful form or vice versa. Such streams that can take other stream as argument are called filtered streams. The Java has **FilterInputStream** and **FilterOutputStream**.

There are several filtered streams which can work only on other streams. In many practical situations, only filtered streams are useful. In the following sections two of the filtered streams are discussed:

![](images/00141.jpeg)

**Fig. 12.3**Filtered byte streams

12.5.1 DataOutputStream

It is a subclass of **FilterOutputStream**. The methods in this class help to convert the basic types to bytes and pass it to an underlying output stream. The write methods in this class help to create an output stream, which can be read by the methods in **DataInputStream**. The data written to the output stream are not in a human readable form. The constructor in this class is:

DataOutputStream(OutputStream ous)

Creates a new data output stream to write data to an underlying output stream ous

Some of the methods defined in **DataOutputStream** are given in Table 12.4\. All the methods throw **IOException**.

**Table 12.4** Methods in DataOutputStream class
All methods throw IOException

| *Method* | *Purpose of the Method* |
| 1. | void write(int b) | Writes the lower 8 bits of b to the underlying output stream |
|     2. | void write(byte bf[], int off , int len) | Writes len bytes from the byte array bf, starting at bf [off ] underlying output stream |
| 3. | void flush () | Send the buffered bytes to the output stream |
| 4. | void writeBoolean(boolean b) | Writes the boolean value b to the underlying output stream as 1 byte value |
| 5. | void writeByte(int in) | Writes the int value as byte value to the underlying stream |
| 6. | void writeShort(int in) | Writes a short to the underlying output stream as two bytes; the high byte is written first. |
| 7. | void writeChar(int in) | Writes a char as 2-byte value to the underlying stream; the high byte is written first. |
| 8. | void writeInt(int in) | Writes an int as 4 bytes to the underlying stream; the high byte is written first |
| 9. | void writeLong(long ln) | Writes a long as 8 bytes to the underlying stream; the high bytes are written first. |
| 10. | void writeFloat(float f) | Converts the float to an int using a special method and writes the int as 4 bytes to the underlying stream; the high byte is written first. |
| 11. | void writeDouble(double d) | Converts the double to a long using a special method and writes the long as 8 bytes to the underlying output stream; the high byte is written first. |
| 12. | void writeUTF(String str) | Writes the String to the underlying output stream using modified UTF-8 encoding. |

The following program 12.4 illustrates the use of some of the methods defined in **DataOutputStream** class.

Program 12.4![](images/00013.jpeg)

/* This program illustrates the use of DataOutputStream

* This program requires jdk1.6 or higher

* ka.somasundaram@gmail.com */

import java.io.*;

class Dataoutput {

public static void main(String args[]) {

Console con = System.console();

File fout = new File(“dataoutput.dat”);

String name, snrec, sage, shit;

int age, nrec, nmax;

double height;

DataOutputStream dous;

try {

dous = new DataOutputStream(

new FileOutputStream(fout));

con.printf(“ How many data?:”);

snrec = con.readLine();

nrec = Integer.parseInt(snrec);

nmax = nrec;

con.printf(“The following data are written to output.dat file%n”);

while (nrec > 0) {

con.printf(“ Name:”);

name = con.readLine();

con.printf(“ Age:”);

sage = con.readLine();

age = Integer.parseInt(sage);

con.printf(“ Height in metres:”);

shit = con.readLine();

height = Double.parseDouble(shit);

dous.writeUTF(name);

dous.writeInt(age);

dous.writeDouble(height);

nrec—;

}

con.printf(“%d records were sent to dataoutput.dat file%n”, nmax);

dous.close();

} catch (FileNotFoundException e) {

con.printf(“File not found”);

} catch (IOException e) {

con.printf(“IO Error”);

}

}

}

The above program gives the following output shown in Fig. 12.4.

![](images/00142.jpeg)

**Fig. 12.4**Output screen for program 12.4

12.5.2 DataInputStream

It is a subclass of **FilterInputStream**. This class helps to convert the bytes from an underlying stream to basic types char, byte, int, etc. Constructor for this class is :

DataInputStream(Inputstream ins)

Creates a new data input stream for the bytes in the underlying InputStream ins

The methods defined in this class are given in Table 12.5\. All the methods throw **IOException**.

**Table 12.5** Methods defined in DataInputStream
All the methods throw IOException

| *Method* | *Purpose of the Method* |
| 1. | int read(byte[] b) | Reads bytes into the byte array b returns the number of bytes read; returns –1 at the end of the stream |
| 2. | int read(byte[] b, int off , int len) | Reads bytes into the byte array b starting at b[off ], len number of bytes; returns the total number of bytes read; returns –1 at the end of the stream |
| 3. | void readFully(byte[] b) | reads bytes into the byte array b; the maximum bytes read being the capacity of the byte array |
| 4. | void readFully (byte[] b, int off  int len) | Reads bytes into b, starting at b[off ], len number of bytes |
| 5. | int skipBytes(int n) | Skips n bytes and returns the actual number of bytes skipped |
| 6. | boolean readBoolean() | Reads a boolean value from the input stream |
| 7. | byte readByte() | Reads an 8-bit signed byte from the input stream |
| 8. | int readUnsignedByte() | Reads an 8-bit unsigned byte from the input stream |
| 9. | short readShort() | Reads two bytes from the input stream and treats it as a 16-bit int |
| 10. | int readUnsignedShort() | Reads two bytes from the input stream and treat it as a 16-bit unsigned integer |
| 11. | char readInt() | Reads two bytes from the input stream and treats its as a 16-bit unicode character |
| 12. | int readInt() | Reads four bytes from the input stream and treats it as an int |
| 13. | long readLong() | Reads 8 bytes from the input stream and treats it as a long |
| 14. | float readFloat() | Reads 4 bytes from the input stream and treats |
| 15. | double readDouble() | Reads 8 bytes from the input stream and treats it as a double |
| 16. | String readUTF() | Reads an UTF string |
| 17. | int available() | Returns the number of bytes available for read |

The following program 12.5 illustrates the use of methods defined in **DataInputStream**.

Program 12.5![](images/00013.jpeg)

/* This program illustrates the use of DataInputStream

* This program requires jdk1.6 or higher

* ka.somasundaram@gmail.com

*/

import java.io.Console;

import java.io.IOException;

import java.io.FileNotFoundException;

import java.io.DataInputStream;

import java.io.FileInputStream;

import java.io.File;

class Datainpt {

public static void main(String args[]) {

Console con = System.console();

File fin = new File(“dataoutput.dat”);

int more;

String name;

int age;

double height;

DataInputStream dins;

try {

dins = new DataInputStream( new FileInputStream(fin));

con.printf(“\nData Read from an data file \n”);

con.printf(“ Name \tAge \t Height %n”);

while ((more = dins.available()) > 0) {

name = dins.readUTF();

age = dins.readInt();

height = dins.readDouble();

con.printf(“ %-14s\t %2d\t %4.2f%n”, name, age, height);

}

dins.close();

} catch (FileNotFoundException e) {

con.printf(“File not found”);

} catch (IOException e) {

con.printf(“IO Error”);

}

}

}

The above program gives the following output shown in Fig. 12.5.

![](images/00143.jpeg)

**Fig. 12.5** Output screen for program 12.5

Most of the methods that convert bytes to basic type like char, int, long, float, double, etc. give values that are not in human readable form, but are efficient for processing.

After reading this chapter, you should have learned the following:

*   All data in Java is handled in two streams, byte stream and character stream.
*   Streams are to be layered for handling the data conveniently and in the required form.
*   DataInputStream and DataOutputSreram are useful to handle basic types.

In the next chapter, you will learn about strings.

![](images/00053.jpeg)

**Problem 12.1T**

Write a Java program that lists the file name, its size and the last modified date, just like the dir command of DOS.

Program 12.1T**![](images/00013.jpeg)**

/* This program list out the files, their size, and last modified date.

* This program requires jdk1.6 or higher for compile and execute.

* ka.somasundaram@gmail.com

*/

import java.io.*;

class TIO121 {

public static void main(String args[]) {

Console con = System.console();

File fpath = new File(“E:/book-rev/chap12”);

int n, filecount = 0, dircount = 0, pn = 40;

long totsize = 0, size, dte;

String dirlist[] = fpath.list();

n = dirlist.length;

con.printf(“\nDirectory of %s\n”, fpath.getName());

for (int i = 0; i < pn; i++) {

con.printf(“-”);

}

con.printf(“\n”);

con.printf(“Modified on \t size \t File name \n”);

for (int i = 0; i < pn; i++) {

con.printf(“-”);

}

con.printf(“\n”);

for (int i = 0; i < n; i++) {

File file = new File(dirlist[i]);

String fname = file.getName();

size = file.length();

totsize += size;

dte = file.lastModified();

boolean dir = file.isDirectory();

if (dir) {

dircount++;

con.printf(“%1$td-%1$tm-%1$ty \t <DIR> \t%2$s\n”, dte, fname);

} else {

filecount++;

con.printf(“%1$td-%1$tm-%1$ty\t %2$d \t %3$s\n”, dte, size, fname);

}

}

for (int i = 0; i < pn; i++) {

con.printf(“-”);

}

con.printf(“\n”);

con.printf(“%d files\t %d bytes\n”, filecount, totsize);

con.printf(“%d dirs\n”, dircount);

}

}

The above program gives the following output shown in Fig.12.6.

![](images/00144.jpeg)

**Fig. 12.6** Output screen for program 12.1T

**EXERCISE-12**

**I. Fill in the blanks:**

12.1All data in Java is treated in ........................... and ........................... streams.

12.2The File class can be used to read and write data. (True/False)

12.3The classes used for disk file handling are ........................... and ........................... .

12.4 ........................... streams help to convert raw bytes into the basic type of Java.

**II. Write Java programs for the following:**

12.5Write a Java program to list out the files in the given directory.

12.6Write a Java program that finds the largest file in the given directory.

12.7Write a Java program to check whether the file given through command line argument exists. If it exists, copy the whole file to another disk file.

13StringsIn this chapter, you will learn about strings. Java supports three types of strings, String, StringBuffer and StringBuilder. String type strings are rigid, whereas StringBuffer and StringBuilder strings are flexible for manipulation. Methods to handle these three types of strings are dealt in this chapter.

In Java language, a string is defined as a sequence of characters. The strings used in Java are handled by three classes, **String**, **StringBuffer** and **StringBuilder**. String class deals with strings that are not altered after creation. **StringBuffer** and **StringBuilder** classes deal with strings that need alteration after they are created. All the classes are available in **java.lang** package.

13.1 THE STRING CLASS

String objects are created using the following constructors:
String()

Creates a String object with no character

String(char charray[])

Creates a String using the charray

String(char charray[], int start, int len)

Creates a String from charray, starting at charray[start] with len number of chars

String(String strObject)

Creates a String from String object strObject

Example:

1\. String s1 = new String()
Creates s1 with no characters

2\. char name[ ] = { 'M', 'a', 'g', 'e', 's', 'h'};
String s2 = new String (name);
Creates a String s2 with string "Magesh"

3\. char name[ ] = { 'M', 'a', 'g', 'e', 's', 'H' };
String s3 = new String (name, 2, 3)
Creates a String s3 with string "esh"

4\. String s4 = new String (s2);
Creates a String s4 with string "Magesh"

It is also possible to use byte array as parameters in constructors used in examples 2 and 3 above to handle the 8-bit ASCII characters.

When constructors of **String** class are used to create objects, each time the new operator is called, an instance of the **String** is created. Each object takes up a memory space. Suppose, two objects contain identical strings, even then they occupy two separate memory locations. In the above examples 2 and 4, the objects s2 and s4, though contains identical strings, take up two separate memory locations. This can be avoided and memory can be saved if strings are created from String literals. Consider the following examples:

5\. String s5 = "Magesh";

6\. String s6 = "Magesh";

In this method, the string objects s5 and s6 contain identical strings "Magesh". In this case Java does not store two objects, but only one. The same reference, where the object is stored, is given to s5 and s6\. Fig. 13.1 illustrates this.

![](images/00145.jpeg)

**Fig. 13.1** (a) Separate memory is allocated when String objects are created using new operator even if strings are identical. (b) Same memory is allocated when String objects are created using String literal with identical strings.

Therefore, using **String** literals to create **String** objects with identical strings is memory-efficient.

When an object reference variable, say s6, is copied to another String variable (say s7), a copy of the object reference is copied to the new variable (s7) and no object is created. Both variables s6 and s7 will refer to the same object.

13.1.1 Equality (= =) Operator and equals Method

We have already come across the use of the equality operator, = =, and equals method. Equality operator (= =) checks whether the contents of object reference variables are **equal,** while the equals method checks whether the contents of the objects are equal.

![](images/00146.jpeg)

**Fig. Fig. 13.2** Object and object reference variable

Referring to Fig. 13.1(a), it is obvious that:

(s2 ==s4) --> false

s2.equals(s4) --> true

Similarly, referring to Fig. 13.1(b), the following result will be obtained:

(s5 == s6) --> true

s5.equals(s6) --> true

Creation of String and the use of = = operator and **equals** method are illustrated in program 13.1.

Program 13.1![](images/00013.jpeg)

/* This program demonstrates the creation of strings using constructors of String and String literal.

* The Strings created are testedusing == operator and equals() method.

* This program requires jdk1.6 or higher for compile and execute.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Stringcompare {

public static void main(String args[]) {

String s1, s2, s3, s4, s5, s6, s7;

Console con = System.console();

char name[] = {‘M’, ‘a’, ‘g’, ‘e’, ‘s’, ‘h’};

s1 = new String();

s2 = new String(name);

s3 = new String(name, 2, 3);

s4 = new String(s2);

s5 = “Magesh”;

s6 = “Magesh”;

s7 = s2;

con.printf(“s1 = %s\n”, s1);

con.printf(“s2 = %s\n”, s2);

con.printf(“s3 = %s\n”, s3);

con.printf(“s4 = %s\n”, s4);

con.printf(“s5 = %s\n”, s5);

con.printf(“s6 = %s\n”, s6);

con.printf(“s7 = %s\n”, s7);

con.printf(“is( s2==s4) ? : %b\n”, (s2 == s4));

con.printf(“is(s2.equals(s4)) ? : %b\n”, s2.equals(s4));

con.printf(“is(s5.equals(s4) ? : %b\n”, s5.equals(s4));

con.printf(“is(s5==s4) ? : %b\n”, (s5 == s4));

con.printf(“is(s5.equals(s6)) ? : %b\n”, s5.equals(s6));

con.printf(“is(s5 == s6) ? : %b\n”, (s5 == s6));

con.printf(“is(s2.equals(s7)) ? : %b\n”, s2.equals(s7));

con.printf(“is(s2 == s7) ? : %b\n”, (s2 == s7));

}

}

The above program gives the following output shown in Fig. 13.1.

![](images/00147.jpeg)

**Fig. 13.3** Output screen for program 13.1

13.1.2String Concatenation With +

There are different ways of concatenation of strings. One way is using + operator. In Java, when + operator is used for strings, it concatenates the operand strings.

Example:

1\. String s1 = "this is demo" + "text";
The String s1 will take up
s1 = "This is a demo text".

2\. int mark = 75;
String s2 = "Your mark is " + mark;
System.out.println(s2);
The above will give :

**Your mark is 75**

The + operator can be used with string and numerical variables. In such cases, the numerical values are converted to String type and appended to the preceding String object. Following are further examples for String concatenation:

3\. String s1 = "Do it";
String s2 = "by yourself";
String s3 = s1 + s2;
System.out.println(s3)
The above statements will give the following result:
**Do it by yourself.**

4\. System.out.println ("Sum of 3 and 5 is " + 3+5):
This statement will give the following result:
**Sum of 3 and 5 is 35**

5\. System.out.println ("Sum of 3 and 5 is" + (3+5)); This statement will give the following result:
**Sum of 3 and 5 is 8**

As it can be seen from the above examples 4 and 5, the operator precedence is to be observed while concatenating String with numerical types.

There are several useful methods for String objects and some of them are given in Table 13.1.

**Table 13.1** Methods in String class

| *Method* | *Purpose of the Method* |
| ***Character Extraction*** |
| 1. | char charAt(int index) | Returns the character at the index position of the invoking String object; the index is counted as 0 for the first character. |
|  2. | void getChars(int sourceBegin,int sourceEnd, char target[ ], int targetBegin) | Copies characters from Object String starting at sourceBegin up to and inclusive of sourceEnd -1 characters into the target, starting at targetBegin |
|  3. | byte[ ] getBytes() | Returns an array of characters as bytes from the String object |
| ***String Comparison*** |
| 4. | boolean equals(Object str) | Returns true if str contains the same string as that in the invoking object, otherwise false |
|  5. | boolean  equalsIgnoreCase(String str) | Returns true if str contains the same string as in the invoking object by ignoring the case, otherwise false |
|  6. | boolean regionMatches (int startIndex, String s2, int s2startIndex, int numchars) | Compares a region of the invoking object starting at startIndex with String s2 starting at s2startIndex for numchars; returns true, if the region compared is equal, otherwise false |
|  7. | boolean regionMatches (boolean ignorecase, int startIndex, String s2, int s2startIndex, int numchars) | Compares a region of the invoking object starting at startIndex with String s2 starting at s2startIndex for numchars; if ignoreCase is true, then the case of characters are ignored for comparison. Returns true if the region compared is equal, otherwise false |
|  8. | boolean endsWith(String str) |  Returns true if invoking String object ends with str, otherwise false |
|  9. | boolean startsWith(String str) | Returns true if the invoking String object starts with str, otherwise false |
| 10. | int compareTo(String str) | Compares the invoking String object with str; returns a negative value if the String object is less than str, zero if both are equal and positive if String object is greater than str |
| ***Searching Substrings*** |
| 11. | int indexOf(int ch) | Returns the index of the first occurrence of the character ch in the invoking String object |
| 12. | int lastIndexOf(int ch) | Returns the index of the last occurrence of the character ch in the invoking String object |
| 13. | int indexOf(String str) | Returns the index of the first occurrence of the string str in the invoking String object |
| 14. | int lastIndexOf(String str) | Returns the index of the last occurrence of the string str in the invoking String object |
| 15. | int indexOf(int ch, int startIndex) | Searches for the character ch starting at startIndex of the invoking String object till the end of the string; returns the index of the first occurrence of the character ch |
| 16. | int lastIndexOf(int ch, int endIndex) | Searches for the character ch from the zero index till the endIndex of the invoking String object; returns the index of the last occurrence of the character ch |
| 17. | int indexOf(String str, int startIndex) | Searches for the substring str starting at startIndex till the end of the invoking String object; returns the index of the first occurrence of the string str |
| 18. | int lastIndexOf(String str, int endIndex) | Searches for the substring str starting at 0 index till the endIndex of the invoking String Object; returns the index of the last occurrence of the string str |
| ***String Modification*** |
| 19. | String substring(int startIndex) | Returns a substring starting at startIndex till the end of the invoking String object |
| 20. | String substring (int startIndex, int endIndex) | Returns a substring starting at startIndex up to endIndex, but excluding the endIndex character of the invoking string object |
| 21. | String concat(String str) | Returns a new String after appending the str to the invoking String object |
| 22. | String replace (char existingChar, char newChar) | Returns a new String created by replacing existingChar with newChar |
| 23. | String trim() | Returns a new String after removing the leading and trailing white spaces of the invoking String object |
| ***Case Conversion*** |
| 24. | String toLowerCase() | Converts the uppercase characters of invoking String object to lowercase |
| 25. | String toUpperCase() | Converts the lowercase characters of the invoking String object to uppercase |
| ***Other Method*** |
| 26. | int length() | Returns the number of characters in the invoking String object |

Program 13.2 shows methods used for character extraction.

Program 13.2![](images/00013.jpeg)

/* This program illustrates the use of character extraction methods of String class.

* This program requires jdk1.6 or higher for compile and execute.

* ka.somasundaram@gmail.com

*/

import java.io.*;

class Stringextract {

public static void main(String args[]) {

char test[] = new char[10];

Console con = System.console();

String s1 = “This is a demo text”;

con.printf(“The given Text is :”);

con.printf(“%s%n”, s1);

s1.getChars(8, 14, test, 0);

String exstr = new String(test);

con.printf(“Extracted Text is :%s\n”, exstr);

con.printf(“The first i is at:%d%n”, s1.indexOf(‘i’));

con.printf(“The first demo is at:%d%n”, s1.indexOf(“demo”));

con.printf(“The substring from index 2 :%s%n”, s1.substring(3));

}

}

The above program gives the following output shown in Fig. 13.4.

![](images/00148.jpeg)

**Fig. 13.4** Output screen for program 13.2

Program 13.3 sorts the given strings in alphabetical order using **compare To** method.

Program 13.3![](images/00013.jpeg)

/* This program illustrates the use of compareTo() method

* to sort the strings in alphabetical order.

* This program requires jdk1.6 or higher

* ka.somasundaram@gmail.com */

import java.io.Console;

class Stringsort {

public static void main(String args[]) {

String name[] = {“Zahir Khan”, “Ramaraj”, “Magesh”, “Kumar”, “Satish”};

Console con = System.console();

String temp;

int count = name.length;

con.printf(“\n The given names\n”);

for (int i = 0; i < count; i++) {

con.printf(“ %s\n”, name[i]);

}

con.printf(“\n Sorted names\n”);

for (int i = 0; i < count; i++) {

for (int j = i + 1; j < count; j++) {

if (name[i].compareTo(name[j]) > 0) {

temp = name[i];

name[i] = name[j];

name[j] = temp;

}

}

}

for (int i = 0; i < count; i++) {

con.printf(“ %s\n”, name[i]);

}

}

}

The above program gives the following output shown in Fig. 13.5.

![](images/00149.jpeg)

**Fig. 13.5** Output screen for program 13.3

**The toString() method**

When an object is created using new operator, a reference to the object is created. A default **toString()** method in the super object converts this reference to a human readable string form and stores it in the object reference. This string can be printed out using the **println** method. Program 13.4 shows the printing of the object reference of a class.

Program 13.4![](images/00013.jpeg)

/* Program to illustrate the use of default toString method in the super Object

* This program requires jdk1.6 or higher for compile and execute.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Democlass {

int x, y;

Democlass(int a, int b) {

x = a;

y = b;

}

}

class DefaulttoString {

public static void main(String args[]) {

Democlass dc = new Democlass(15, 45);

Console con = System.console();

con.printf(“%s\n”, dc);

}

}

The above program gives the following output shown in Fig. 13.6.

![](images/00150.jpeg)

**Fig. 13.6** Output screen for program 13.4

This **toString()** method can be overridden by an user to get other messages needed about the object. Program 13.5 shows the overriding **toString()** method to generate the message about the initial values assigned to the instance variables.

Program 13.5![](images/00013.jpeg)

/* Program to illustrate the use of overridden toString method

* This program requires jdk1.6 or higher for compile and execute.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Democlass {

int x, y;

Democlass(int a, int b) {

x = a;

y = b;

}

public String toString() {

return “Object created with x = “ + x + “ and y = “ + y;

}

}

class toStringDemo {

public static void main(String args[]) {

Democlass dc = new Democlass(35, 57);

Console con = System.console();

con.printf(“%s\n”, dc);

}

}

The above program gives the following output shown in Fig. 13.7.

![](images/00151.jpeg)

**Fig. 13.7** Output screen for program 13.5

13.2 THE StringBuffer CLASS

Strings that need modification are handled by **StringBuffer** class. After creating a **StringBuffer,** new strings can be inserted or appended to it. The size of the **StringBuffer** can grow whenever needed. **StringBuffer** objects can be dynamically altered. When a **StringBuffer** is created, space for 16 more characters is always appended with it. This helps the **StringBuffer** object to grow by 16 more characters without any other process. That is, the size of the **StringBuffer** is the number of characters in that string plus 16\. When the string grows beyond the free 16 character space, the **StringBuffer** is relocated to a new memory space with the required size. **StringBuffer** type objects are safe to use in multithreaded environment.

The constructors in **StringBuffer** class help to create **StringBuffer** objects. The constructors are :

StringBuffer()

Creates an empty StringBuffer Object; it has 16-character space.

StringBuffer(int size)

Creates a StringBuffer object with a buffer of size capacity

StringBuffer(String str)

Creates a StringBuffer object with the string str plus space for 16 more characters

The **equals()** method defined in **String** class is also available in **StringBuffer** class. The **equals()**method can be used to compare the same type of string objects and not to be mixed. That is, a **String** object cannot be compared with **StringBuffer** Object.

![](images/00011.jpeg)The equals() method should not be used to compare objects of different types.

Methods defined in StringBuffer class are given in Table 13.2.

**Table 13.2** Methods defined in StringBuffer class

| *Method* | *Purpose of the Method* |
| 1. | int length() | Returns the total number of characters in the invoking object |
| 2. | int capacity() | Returns the total allocated capacity for the invoking object |
| 3. | void ensureCapacity (int capacity) | Sets the capacity of the buffer of the invoking object to the desired capacity |
| 4. | void setLength(int len) | Sets the length of the StringBuffer object to len characters; if len is larger than the length of the object, empty spaces will be created. If len is less than the length of the object, characters after len will be lost |
| 5. | char charAt(int index) | Returns a character at the index position of the invoking object |
| 6. | void setCharAt(int index, char ch) | Sets the character ch at the index position of the invoking object |
| 7. | void getChars(int sourceBegin, int sourceEnd, char target[], int targetBegin) | Copies characters from object starting at sourceBegin up to and inclusive of sourceEnd -1 characters into the target, starting at targetBegin |
| 8. | StringBuffer append(String str) | Returns a StringBuffer after appending str to the invoking object |
| 9. | StringBuffer append(int num) | Returns a StringBuffer after appending the num to the invoking object |
| 10. | StringBuffer append(object obj) | Returns a StringBuffer after appending obj to the invoking object |
| 11. | StringBuffer insert(int index, String str) | Returns a StringBuffer after inserting str at index position of the invoking object |
| 12. | StringBuffer reverse() | Returns a StringBuffer after reversing the characters in the string of the invoking object |
| 13. | StringBuffer delete (int startIndex, int endIndex) | Returns a StringBuffer after deleting characters from startIndex to endIndex of the invoking object |
| 14. | StringBuffer deleteCharAt (int index) | Returns a StringBuffer after deleting a character at the index position of the invoking object |
| 15. | StringBuffer replace (int startIndex, int endIndex, String str) | Returns a StringBuffer after replacing the characters included in the range startIndex to endIndex of the invoking object by str |
| 16. | String substring(int startIndex) | Returns a String starting at startIndex to the end of the invoking StringBuffer object |
| 17. | String substring(int startIndex, int endIndex) | Returns a String included in the range  startIndex to endIndex of the invoking StringBuffer object |
| 18. | String toString() | Returns a String after freezing the buffer size of the invoking StringBuffer object |

13.3 THE StringBuilder CLASS

There is yet another class **StringBuilder** (from JDK 1.5 onwards) to handle mutable or flexible string. It has all the methods defined in **StringBuffer** class. **StringBuilder** type strings are not safe to use in multiple threads.

Program 13.6 illustrates the use of some of the methods defined in **StringBuffer** class.

Program 13.6![](images/00013.jpeg)

/* This program illustrates some of the methods in StringBuffer class.

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com */

import java.io.Console;

class StringBuf {

public static void main(String args[]) {

StringBuffer name = new StringBuffer(“Praveen Kumar”);

Console con = System.console();

int count = name.length();

con.printf(“Name = %s\n”, name);

con.printf(“Length of name = %d\n”, count);

con.printf(“Capacity of name = %d\n”, name.capacity());

con.printf(“Substring 5th character = %s\n”, name.substring(4));

con.printf(“Name after inserting initial = %s\n”, name.insert(0, “S.”));

con.printf(“Name after appending the degree = %s\n”, name.append(“ MS”));

con.printf(“Reversed name = %s\n”, name.reverse());

}

}

The above program gives the following output shown in Fig. 13.8.

![](images/00152.jpeg)

**Fig. 13.8** Output screen for program 13.6

After reading this chapter, you should have learned the following:

*   Java supports three types of strings, String, StringBuffer and StringBuilder.
*   String type is rigid to manipulate, whereas the StringBuffer and StringBuilder types are more flexible for manipulation.

In the next chapter, you will learn about threads.

![](images/00053.jpeg)

Problem 13.1T

Write a program to read the following list (or any other list of your choice) through keyboard entry, arrange the names in alphabetical order and print out.

| *Name* | *Sex* |
| Ramasamy K. | m |
| Mahesh S. | m |
| Kumar S. | m |
| Charles B. | m |
| Parvathi M. | f |
| Cindrela U. | f |
| Ramesh K. | m |
| Gomathi S. | f |
| Balan N. | m |

Program 13.1T![](images/00013.jpeg)

/* This program reads the data from keyboard, sorts

* the names in alphabetical order and prints out the list

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Detail {

String name, sx;

Detail(String nm, String s) {

name = nm;

sx = s;

}

}

class TIO131 {

static void Printline(int n) {

Console con = System.console();

for (int i = 0; i < n; i++) {

con.printf(“–”);

}

con.printf(“\n”);

}

public static void main(String args[]) {

Console con = System.console();

String tname, tsex, choice, snrec;

int pn = 20, nrec;

con.printf(“ How many names ?:”);

snrec = con.readLine();

nrec = Integer.parseInt(snrec);

Detail dtl[] = new Detail[nrec];

Detail tdtl;

// Read the key board to get the input

for (int i = 0; i < nrec; i++) {

con.printf(“Type the name: “);

tname = con.readLine();

con.printf(“Type the sex (m/f) : “);

tsex = con.readLine();

dtl[i] = new Detail(tname, tsex);

}

//sort by alphabetical order

for (int i = 0; i < nrec; i++) {

for (int j = i + 1; j < nrec; j++) {

if (dtl[j].name.compareTo(dtl[i].name) < 0) {

tdtl = dtl[i];

dtl[i] = dtl[j];

dtl[j] = tdtl;

}

}

}

con.printf(“Sorted List\n”);

Printline(pn);

con.printf(“%–15s %4S%n”, “ Name”, “Sex”);

Printline(pn);

for (int i = 0; i < nrec; i++) {

con.printf(“%–15s %4s\n”, dtl[i].name, dtl[i].sx);

}

Printline(pn);

}

}

The above program when executed, and data fed through the keyboard, gives the following output shown in Fig. 13.9.

![](images/00153.jpeg)

**Fig. 13.9** Input/Output screen for program 13.1T

Program 13.2T

Write a program to count the number of characters, words and lines in a given file. The file name is to be given through the command line argument.

Program 13.2T![](images/00013.jpeg)

/* This program reads a file and counts the number of characters, no of words and no of lines. The file

* name isfed through the command line argument.

* This program requires jdk1.6 or higher for compile and execute.

* ka.somasundaram@gmail.com

*/

import java.io.*;

class TIO132 {

public static void main(String args[]) {

int lines = 0, words = 0, chars = 0, chr;

Console con = System.console();

if (args.length == 0) {

con.printf(“Give a file name in the command line”);

System.exit(0);

}

File f = new File(args[0]);

con.printf(“The file %s has %d

bytes\n”, args[0],f.length());

try {

FileInputStream fins = new FileInputStream(f);

while ((chr = fins.read()) != -1) {

chars++;

switch ((char) chr) {

case ‘\t’:

case ‘ ‘:

words++;

break;

case ‘\n’:

words++;

lines++;

}

}

} catch (IOException ioe) {

con.printf(“IO Problem”);

}

con.printf(“%s file contains\n %d chars\n %d

words\n %d lines\n”, args[0], chars,

words, lines);

}

}

The above program gives the following output shown in Fig. 13.10.

![](images/00154.jpeg)

**Fig. 13.10** Output screen for program 13.2T

EXERCISE-13

**I. Fill in the blanks:**

13.1The string that does not need any modification is to be dealt by ........................... class.

13.2The string that needs modification while processing is dealt by ........................... and ........................... classes.

13.3The classes for handling string are available in the ........................... package.

13.4When a String object is copied into another String object reference, a copy of the original object ........................... created.

13.5To compare the contents of two objects, ........................... method is used.

13.6The number of extra character width available in a StringBuffer is ........................... .

13.7The length of the StringBuffer is defined as ........................... .

13.8The capacity of the StringBuffer is given by ........................... .

13.9When toString method is applied to a StringBuffer, the buffer size is ........................... and the StringBuffer is converted to ........................... .

13.10Strings created using ........................... are not Thread safe.

13.11To create strings that are safe in multithreaded environment ........................... class is to be used.

**II. Write Java programs for the following:**

13.12Write a program to read a line of text from the console. Find the position of the first and last occurrence of the string "the". Copy all the characters enclosed between the two positions to another String and print it out.

13.13Write a program to read a line of text from the console. Print out only the vowels (a, e, i, o, u) and their position of occurrence.

13.14A set of 10 names is given. Write a program to delete the first three characters of the names and arrange the resulting names in alphabetical order and print them out.

13.15Read in a line of text from the keyboard. Adjust the white space between words so that the whole line is aligned left and right in a line width of 60 characters and print it out.

13.16A set of 5 words is given. Write a program to reverse each word and arrange the resulting words in alphabetical order.

13.17Write a program to read a line of text from the console. Change the first character of each word to uppercase letter and print out the resulting string.

14ThreadsIn this chapter, you will learn about multithreaded programming in Java. A single task can be divided into a number of small sub-tasks. Each sub-task can be executed as an independent process. Such a process is known as a thread. In this chapter, creation of multiple threads and managing them are discussed.

14.1 MULTITASKING

Before starting the thread concept, let us begin with a known multitasking process. When more than one task is processed by a computer, it is called multitasking. This is being done to utilize the idle time of a CPU more effectively. Each task ( heavy-weight process) has its own set of variables and separate memory location for them. A multitasking process is shown in Fig.14.1

![](images/00155.jpeg)

**Fig. 14.1** The multitasking process

The underlying operating system does the multitasking process by bringing tasks to the CPU and executing them by using appropriate schedule.

**Multithreading**

In many real-life situations, a single task (heavy-weight process) may comprise of many sub-tasks ( light-weight process), such as reading an input stream, processing data, drawing graphics on screen, etc. Each sub-task is carried out one after another. But certain sub-tasks, like reading an input stream, may have to keep waiting till a byte is read. In such occasions, the CPU will be idling without doing any work.

This idling time of the CPU can be utilized if some other sub-task, say drawing a graphic on a screen, can be executed in the CPU. Java language provides a mechanism by which each sub-task can be treated as a separate process. Several such processes originating from a single task, can be simultaneously started and handled by Java. This mechanism of treating a single task as several independent processes simultaneously is called multithreading. Each independent process is called a thread. Each thread is executed one at a time in the CPU. Fig. 14.2 shows the multithreaded process.

![](images/00156.jpeg)

Fig. 14.2 The multithreaded process

In multithreading, same set of variables and memory space is shared by the threads. When a thread dealing with a sub-task, say reading an input stream, has to wait for the arrival of a byte, such a thread will exit the CPU and another thread, say drawing a graphic on a screen, may enter the CPU and continue its task. Thus Java’s thread provides a mechanism to utilize the CPU time more optimally. Multithreading finds use in variety of applications. The threading mechanism is supported by Java’s **Thread** class contained in java.lang package.

**14.2 CREATING A THREAD**

A Java thread can be created in two different ways. They are:

(i) By extending **Thread** class

(ii) By implementing **Runnable** interface

Though both methods can be used to create a thread, implementing **Runnable** interface has certain advantages. In both cases the **run()** method which contains the code for the thread is to be implemented.

***Thread Class***

Few of the constructors defined in Thread class are:

(i) Thread (Runnable target)
Creates a new Thread object, using the target which contains the run() method.

(ii) Thread (String name)
Creates a new Thread object with a name specified by name.

(iii) Thread (Runnable target, String name)
Creates a new Thread object, using the target which contains the run() method, with a name specified in name.

Some of the methods defined in a **Thread** class to create and execute a thread are given in Table 14.1.

**Table 14.1** Some of the methods defined in a Thread class

| *Method* | *Purpose of the Method* |
| 1. | String getName() | Returns the name of the invoking Thread object |
| 2. | boolean isAlive() | Returns true if the thread has started and has not yet terminated |
| 3. | void join() | Waits for a thread to terminate |
| 4. | void run() | Contains the statements that are to be executed in a thread |
| 5. | void start() | Starts a thread by calling the run() method |
| 6. | void sleep(long ms) | Makes the currently executing thread to sleep for ms milli seconds |

Let us see how to create a thread from a **Thread** class. Create a subclass of the **Thread** class. Write a **run()** method and place all the statements that are to be executed by a thread. Write a constructor for the class and create an instance of the **Thread** class by passing the **run()** method as a parameter. This is done through the use of **this** keyword. Optionally, a name for the thread can also be assigned by placing a String as a second parameter for the **Thread** instance. Start the thread by calling the **start()** method of the **Thread** class. Program 14.1 is an illustration for creating a thread by this way. The program finds the sum of the natural numbers from 1 up to n, with n varying from 1 to 5.

Program 14.1![](images/00013.jpeg)

/* Creation of a Thread by extending the Thread class

* The thread is created and started in the constructor

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Sumthread extends Thread {

int i, sum = 1;

Thread th;

Console con = System.console();

Sumthread() {

th = new Thread(this, “My thread1”);

con.printf(“The thread created is :%s\n”, th.getName());

th.start();

}

public void run() {

for (i = 1; i <= 5; sum += ++i) {

con.printf(“Sum of numbers from 1 upto %d = %d \n”, i, sum);

}

}

}

class Threadcreate1 {

public static void main(String args[]) {

new Sumthread();

}

}

The above program gives the following output shown in Fig. 14.3.

![](images/00157.jpeg)

**Fig. 14.3** Output screen for program 14.1

In the above program 14.1, the **run()** method is executed by its own class object. The **run()** method is not directly called. When the **start()** method is called, the **run()** method is automatically called. It is also possible that the **run()** method can be executed by some other **Thread** object. Program 14.2 shows how a **run()** method is executed by an object other than by its own object, where the **run()** method is defined. The problem dealt in this program 14.2 is the same as that of program 14.1.

Program 14.2![](images/00013.jpeg)

/* Creation of a Thread by extending the Thread class

* The thread is created in one classs and started in another class

* This program requires jdk1.6 or higher

* ka.somasundaram@gmail.com */

import java.io.Console;

class Sumthread extends Thread {

int i, sum = 1;

Console con = System.console();

public void run() {

for (i = 1; i <= 5; sum += ++i) {

con.printf(“ Sum of numbers from 1 upto %d = %d \n”, i, sum);

}

}

}

class Threadcreate2 {

public static void main(String args[]) {

Console con = System.console();

Sumthread st = new Sumthread();

Thread th = new Thread(st, “My thread2”);

con.printf(“The thread created is %s\n”, th.getName());

th.start();

}

}

The above program gives the following output shown in Fig. 14.4.

![](images/00158.jpeg)

**Fig. 14.4** Output screen for program 14.2

Now, let us see the second way to create a thread by implementing the interface **Runnable**. Here also, the **run()** method is placed inside the class implementing **Runnable**. A constructor is used to create a **Thread** object and start it. One advantage of implementing a **Runnable** interface is that a thread can be created in a subclass of an existing class. This enables to write several threads for the same superclass. Program 14.3 shows the creation of a thread by implementing the interface **Runnable**. Another method, **isAlive(),** is also used to know the status of the thread.

Program 14.3![](images/00013.jpeg)

/* Creation of a Thread by implementing the interface Runnable

* The thread is created and started by the constructor of the same class

* This program requires jdk1.6 or higher for compile and execute.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Sumthread implements Runnable {

int i, sum = 0;

Thread th;

Console con = System.console();

Sumthread() {

th = new Thread(this, “My thread3”);

con.printf(“The thread created is : %s\n”, th.getName());

con.printf(“Before starting the thread\n Is the thread alive? :%b\n”, th.isAlive());

th.start();

con.printf(“After starting the thread\n Is the thread alive? %b\n”, th.isAlive());

}

public void run() {

for (i = 1; i <= 5; i++) {

sum += i;

con.printf(“Sum of numbers from 1 upto %d = %d\n”, i, sum);

}

}

}

class Threadcreate3 {

public static void main(String args[]) {

new Sumthread();

}

}

The above program gives the following output shown in Fig. 14.5.

![](images/00159.jpeg)

**Fig. 14.5** Output screen for program 14.3

We write another program in which the **run()** method is executed by another **Thread** object. Program 14.4 shows the second form of executing the **run()** method using **Runnable** interface.

![](images/00011.jpeg)The codes that are to be executed in a thread are to be placed in the run() method.

Program 14.4![](images/00013.jpeg)

/* Creation of a Thread by implementing the interface Runnable.

* The thread is created and started a different class.

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com */

import java.io.Console;

class Sumthread implements Runnable {

int i, sum = 0;

Console con = System.console();

public void run() {

for (i = 1; i <= 5; i++) {

sum += i;

con.printf(“Sum of numbers from 1 upto %d = %d%n”, i, sum);

}

}

}

class Threadcreate4 {

public static void main(String args[]) {

Console con = System.console();

Sumthread st = new Sumthread();

Thread th = new Thread(st, “My thread4”);

con.printf(“The thread created is : %s%n”, th.getName());

con.printf(“Before starting the thread%n Is the thread alive? :%b%n”, th.isAlive());

th.start();

con.printf(“After starting the thread%n Is the thread alive? :%b%n”, th.isAlive());

}

}

The above program 14.4 gives the same result as shown in Fig. 14.5.

**14.3 STATES OF A THREAD**

When a thread is created, it goes to different states before it completes its task and is dead. The different states are:

*   new
*   runnable
*   running
*   blocked
*   dead

**new threads**

When a thread is created, it is in a new state. In this state the thread will not be executed.

**runnable threads**

When the **start()** method is called on the thread object, the thread is in runnable state. A runnable thread need not necessarily be executed by the CPU. A runnable thread joins the collection of threads that are ready for execution. Which runnable thread takes up the CPU is determined by the underlying operating system.

**running threads**

A thread currently being executed by the CPU is in a running state.

**blocked threads**

A running thread may go to a blocked state due to any of the following conditions.

*   **wait** method is called by the thread
*   the thread performs I/O operation
*   **sleep** method is called by the thread

Fig. 14.6 shows the different states of a thread.

![](images/00160.jpeg)

**Fig. 14.6** The different states of a thread

When a blocked thread is unblocked, it goes to runnable state and not to running state. Among the runnable threads, the one which has higher priority (set by the programmer) will go to the running state. This scheduling is done by the operating system.

![](images/00011.jpeg)When a blocked thread is unblocked, it goes to a runnable state and not to a running state.

***dead thread***

A thread becomes dead on two occasions. In the first case, a thread completes its task, exits the running state and becomes dead. In the other case, the **run** method is aborted, due to the occurrence of an exception and the thread becomes dead.

**14.4 MULTITHREADED PROGRAMMING**

In earlier examples, we have seen programs with only one thread. Now, we will see how to write a multithreaded program. When a program is started, a thread is automatically created. It is called the main thread. The main thread can be accessed using the **currentThread()** method of the **Thread** class. Program 14.5 illustrates the creation of two child threads, one finds the sum of natural numbers and the other finds the factorial of numbers.

Program 14.5![](images/00013.jpeg)

/* This program creates two threads

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Sumthread implements Runnable {

int i, sum = 0;

Console con = System.console();

public void run() {

for (i = 1; i <= 5; i++) {

sum += i;

con.printf(“Sum of numbers from 1 upto %d = %d%n”, i, sum);

}

}

}

class Factthread implements Runnable {

int i, n, fact = 1;

Console con = System.console();

public void run() {

for (i = 1; i <= 5; i++) {

fact *= i;

con.printf(“Factorial of %d = %d%n”, i, fact);

}

}

}

class Twothread {

public static void main(String args[]) {

Thread ct = Thread.currentThread();

Console con = System.console();

con.printf(“The main thread is: %s%n”, ct.getName());

Sumthread st = new Sumthread();

Factthread ft = new Factthread();

Thread sumt = new Thread(st, “Sum thread”);

Thread factt = new Thread(ft, “Factorial thread”);

sumt.start();

factt.start();

con.printf(“ The thread created is : %s%n”, sumt.getName());

con.printf(“The thread created is : %s%n”, factt.getName());

}

}

The above program gives the following output shown in Fig. 14.7.

![](images/00161.jpeg)

**Fig. 14.7** Output screen for program 14.5 for two executions

When you repeatedly run the above program 14.5, you may get the results interleaved or in a different order. It is due to the fact that when threads are created a default priority is allotted to each of the thread. Since both sum thread and factorial thread take equal priorities, the CPU time is allotted equally to each thread. Hence, results may be interleaved.

**14.5 THREAD PRIORITIES**

Threads can be assigned priorities. The priorities are used by the operating system to find out which runnable thread is to be given the CPU time. Priorities are given by priority numbers ranging from 1 to 10. A thread with higher priority number will be given preference over the threads with lower priority numbers. The priority of a thread can be set using the method:

setPriority(intpri-numb)

There are three pre-defined priorities. **MIN_PRIORITY** with a value 1, **NORM_PRIORITY** with a value 5 and **M AX_PRIORITY** with a value 10\. When a thread is created, a default priority **NORM_PRIORITY** is given. To obtain the priority of a thread, the

int getPriority()

method can be used. When two threads have equal priorities, the underlying operating system decides which thread is to be given the CPU. The scheduling of threads to running state depends on the OS. It is not guaranteed that threads of equal priorities are given equal CPU time. Program 14.6 shows the creation of two threads and assigning them priorities.

Program 14.6![](images/00013.jpeg)

/* This program sets priorities for the threads created

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com */

import java.io.Console;

class Sumthread implements Runnable {

int i, sum = 0;

Console con = System.console();

public void run() {

for (i = 1; i <= 5; i++) {

sum += i;

con.printf(“Sum of numbers from 1 upto %d = %d\n”, i, sum);

}

}

}

class Factthread implements Runnable {

int i, n, fact = 1;

Console con = System.console();

public void run() {

for (i = 1; i <= 5; i++) {

fact *= i;

con.printf(“ Factorial of %d = %d\n”, i, fact);

}

}

}

class Threadpriority {

public static void main(String args[]) {

Console con = System.console();

Sumthread st = new Sumthread();

Factthread ft = new Factthread();

Thread sumt = new Thread(st, “Sum thread”);

Thread factt = new Thread(ft, “Factorial thread”);

sumt.setPriority(Thread.MIN_PRIORITY);

factt.setPriority(Thread.MAX_PRIORITY);

String smnam = sumt.getName();

String ftnam = factt.getName();

con.printf(“ The thread created is : %s\n”, smnam);

con.printf(“ The thread created is : %s\n”, ftnam);

int smpri = sumt.getPriority();

int ftpri = factt.getPriority();

con.printf(“ The priority value of %s = %d\n”, smnam, smpri);

con.printf(“ The priority value of %s = %d\n”, ftnam, ftpri);

factt.start();

sumt.start();

}

}

The above program gives the following output shown in Fig. 14.8.

![](images/00162.jpeg)

**Fig. 14.8** Output screen for program 14.6

In the above program 14.6, the Factthread is executed first because it has been assigned higher priority 10, than the Sumthread. You will get the same result in the same order if the program is executed any number of times. This is in contrast to the result for the program 14.5.

**14.6 WAITING FOR A THREAD - join() METHOD**

In some problems, it may be required to wait for a particular thread to complete its task before another thread to proceed with. In such occasions, the **join**method of **Thread** class can be used. When **join** method is called on a thread object, the control waits for the thread to complete its task and becomes a dead thread. Then the control proceeds with the normal course of execution. In program 14.7, two threads are created. One thread is started and the **join** method is called on it. Until the thread completes its task, the control waits at that point. As soon as the corresponding thread comes to dead state, the control proceeds with the execution of the other statements.

Program 14.7![](images/00013.jpeg)

/* This program sets priorities for the threads created.

* An indirect wait is made for the thread by calling join()

* method. Only after the current thread terminates the other

* process will start.

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Sumthread implements Runnable {

int i, sum = 0;

Console con = System.console();

public void run() {

for (i = 1; i <= 5; i++) {

sum += i;

con.printf(“Sum of numbers from 1 upto %d = %d\n”, i, sum);

}

}

}

class Factthread implements Runnable {

int i, n, fact = 1;

Console con = System.console();

public void run() {

for (i = 1; i <= 5; i++) {

fact *= i;

con.printf(“Factorial of %d = %d\n”, i, fact);

}

}

}

class Threadjoin {

public static void main(String args[]) {

Sumthread st = new Sumthread();

Console con = System.console();

Factthread ft = new Factthread();

Thread sumt = new Thread(st, “Sum thread”);

Thread factt = new Thread(ft, “Factorial thread”);

sumt.setPriority(Thread.NORM_PRIORITY - 2);

factt.setPriority(Thread.NORM_PRIORITY + 2);

String smnam = sumt.getName();

String ftnam = factt.getName();

int ftpri = factt.getPriority();

int smpri = sumt.getPriority();

con.printf(“The priority value of %s = %d\n”, smnam, smpri);

con.printf(“The priority value of %s = %d\n”, ftnam, ftpri);

sumt.start();

con.printf(“The thread created is : %s\n”, smnam);

try {

sumt.join();

} catch (InterruptedException e) {;

}

factt.start();

con.printf(“The thread created is : %s\n”, ftnam);

}

}

The above program gives the following output shown in Fig. 14.9.

![](images/00163.jpeg)

**Fig. 14.9** Output screen for program 14.7

You will observe from the result that when the Sum thread is started and called with **join** method, the control waits till the Sum thread completes its task. After that the Factorial thread is started.

**14.7 CONTROLLING THE THREADS**

The objective of multithreading is to deal with sub-tasks independent of each other and to utilize the CPU time optimally. In a multithreaded program, if a particular thread is assigned a higher priority and if it needs longer time to complete its task, then the other runnable threads have to keep waiting. No benefit will be derived if one thread is allowed to consume much of CPU time and keep other threads waiting. Fair chances are to be given to every thread in a program. In any multithreaded program, a few of the threads in their course of action, such as doing I/O operation, may go from running state to blocked state, thereby creating opportunities for other threads to enter running state. In the absence of any such natural event, the programmer must find ways to make a CPU-hungry thread to give way for other threads to enter the CPU. Java has two methods which can change the running state of a thread to blocked state. These methods are given in Table 14.2.

**Table 14.2** Methods that control the Thread

| *Method* | *Purpose of the Method* |
| 1. | static void sleep(long ms) | Makes the thread to sleep for ms milliseconds |
| 2. | static void yield() | Causes the running thread to yield to other runnable thread |

The sleep method makes the thread to sleep (lying idle) for a specified amount of time. Once a thread calls a **sleep** method, it goes from running state to blocked state. It remains sleeping (blocked) till the specified amount of time, wakes up and goes to runnable state. This is one way of making a thread to give way for other runnable thread to enter the running state. Program 14.8 shows the use of **sleep** method. In this program, two child threads, Sum thread and Factorial thread are created in addition to the main thread. Each of the child thread is made to sleep 200 milliseconds after two or three calculations.

Program 14.8![](images/00013.jpeg)

/* This program illustrates the use of sleep() method.

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com */

import java.io.Console;

class Sumthread implements Runnable {

int i, sum = 0;

Console con = System.console();

public void run() {

for (i = 1; i <= 5; i++) {

sum += i;

try {

if (i % 2 == 0) {

Thread.sleep(200);

}

} catch (InterruptedException e) {;

}

con.printf(“Sum of numbers from 1 upto %d = %d\n”, i, sum);

}

}

}

class Factthread implements Runnable {

int i, n, fact = 1;

Console con = System.console();

public void run() {

for (i = 1; i <= 5; i++) {

fact *= i;

try {

if (i % 3 == 0) {

Thread.sleep(200);

}

} catch (InterruptedException e) {;

}

con.printf(“Factorial of %d = %d\n”, i, fact);

}

}

}

class Threadsleep {

public static void main(String args[]) {

Console con = System.console();

Thread ct = Thread.currentThread();

con.printf(“The main thread is : %s\n”, ct.getName());

Sumthread st = new Sumthread();

Factthread ft = new Factthread();

Thread sumt = new Thread(st, “Sum thread”);

Thread factt = new Thread(ft, “Factorial thread”);

int ctpri = ct.getPriority();

int smpri = sumt.getPriority();

int ftpri = factt.getPriority();

con.printf(“The main thread priority is : %d\n”, ctpri);

con.printf(“The Sum thread priority is: %d\n”, smpri);

con.printf(“The Factorial thread priority is : %d\n”, ftpri);

sumt.start();

factt.start();

}

}

The above program gives the following output shown in Fig. 14.10.

![](images/00164.jpeg)

**Fig. 14.10** Output screen for program 14.8

In the above program, three threads, main, Sum and Factorial threads, are created. All the three threads take up priority 5\. The first four-line outputs are done by the main thread. There afterwards, only the two child threads, Sum and Factorial, with equal priority compete for the CPU. The Sum thread is made to sleep for 200 milliseconds whenever even numbers are encountered and the Factorial thread is made to sleep whenever the processing number is divisible by 3\. Thus the Sum thread and Factorial thread alternatively provide opportunity to each other (with equal priority) to enter the running state.

![](images/00011.jpeg)When a program is executed, a thread is created in the main() method implicitly. This thread is called main thread. A reference can be obtained to this thread using **currentThread()** method.

The **yield** method makes the running thread to yield to other runnable threads. If there are runnable threads which have the same or higher priority of the yielding thread, one of them will be scheduled to run in the CPU. The yielding thread will be in runnable state until it gets its next turn. If there are no runnable threads with the same or higher priority, the yielding thread will again come back to running state and continue to run in the CPU. The program 14.9 illustrates the use of **yield** method. The problem dealt is the same as that for program 14.8.

Program 14.9![](images/00013.jpeg)

/*This program illustrates the use of yield() method.

* This program requires jdk1.6 or higher.

* ka.somasundaram@gmail.com

*/

import java.io.Console;

class Sumthread implements Runnable {

int i, sum = 0;

Console con = System.console();

public void run() {

for (i = 1; i <= 5; i++) {

sum += i;

Thread.yield();

con.printf(“%nSum of numbers from 1 upto %d = %d\n”, i, sum);

}

}

}

class Factthread implements Runnable {

int i, n, fact = 1;

Console con = System.console();

public void run() {

for (i = 1; i <= 5; i++) {

fact *= i;

Thread.yield();

con.printf(“%nFactorial of %d = %d\n”, i, fact);

}

}

}

class Threadyield {

public static void main(String args[]) {

Thread ct = Thread.currentThread();

Console con = System.console();

con.printf(“The main thread is : %s\n”, ct.getName());

Sumthread st = new Sumthread();

Factthread ft = new Factthread();

Thread sumt = new Thread(st, “Sum thread”);

Thread factt = new Thread(ft, “Factorial thread”);

int ctpri = ct.getPriority();

int smpri = sumt.getPriority();

int ftpri = factt.getPriority();

con.printf(“The main thread priority is : %d\n”, ctpri);

con.printf(“The Sum thread priority is : %d\n”, smpri);

con.printf(“The Factorial thread priority is : %d\n”, ftpri);

sumt.start();

factt.start();

}

}

The above program gives the following output:

![](images/00165.jpeg)

**Fig. 14.11** Output screen for program 14.9

In the above program, three threads main, Sum and Factorial are created. All the three have the same priority 5\. As in the previous program 14.8, the Sum thread is made to yield whenever the number processed is even and the Factorial thread is made to yield whenever the processed number is divisible by 3\. The result obtained is the same as the previous program. It is to be noted that when the program is repeated many times, the sequence of the output may be different from the one shown above. It is due to the fact that scheduling the thread is carried out by the underlying OS. Hence, with different OS the interleaving sequence of output may differ.

![](images/00011.jpeg)In multithread program, if there are threads that have no chance of being blocked and have a higher priority, such threads should be sent to blocked state by calling sleep or yield method. Only then other threads will have a chance to enter CPU.

After reading this chapter, you should have learned the following:

*   Thread is an individual subtask running independently.
*   A program may contain many threads to perform various subtasks.

In the next chapter, you will learn about applets.

![](images/00053.jpeg)

**Problem 14.1T**

Write a Java program to compute the Sine and Cosine values, using the formula given in problem 5.1T. Use one thread to compute Sine function and another thread to compute Cosine function.

Program 14.1T![](images/00013.jpeg)

/* This program calculates the sin(x) and cos(x) functions by

computing the sin series and cos series functions using

thread technique.

This program requires jdk1.6 or higher

ka.somasundaram@gmail.com

*/

import java.io.Console;

class Trigno {

double x;

int i, n = 5;

long factn;

Trigno(double x) {

this.x = x;

}

long Factfun(int nmax) {

long fact = 1;

for (i = 2; i <= nmax; i++) {

fact *= i;

}

return fact;

}

synchronized double Sinfun() {

double six = x;

for (int k = 1; k <= n; k++) {

factn = Factfun(2 * k + 1);

six = six + Math.pow(–1, k) * Math.pow(x, (2 * k + 1)) / factn;

}

return six;

}

synchronized double Cosfun() {

double cox = 1;

for (int k = 1; k <= n; k++) {

factn = Factfun(2 * k);

cox = cox + Math.pow(–1, k) * Math.pow(x, 2 * k) / factn;

}

return cox;

}

}

class Sine

implements Runnable {

double sinval;

Trigno trgno;

double Sincomp(Trigno trg) {

trgno = trg;

Thread th = new Thread(this);

th.start();

try {

th.sleep(50);

} catch (InterruptedException ie) {;

}

return sinval;

}

public void run() {

sinval = trgno.Sinfun();

}

}

class Cosine

implements Runnable {

double cosval;

Trigno trgno;

double Coscomp(Trigno trg) {

trgno = trg;

Thread th = new Thread(this);

th.start();

try {

th.sleep(50);

} catch (InterruptedException ie) {;

}

return cosval;

}

public void run() {

cosval = trgno.Cosfun();

}

}

class TIO141 {

static void Printline(int pn) {

Console con = System.console();

for (int i = 1; i <= pn; i++) {

con.printf("–");

}

con.printf("%n");

}

public static void main(String args[]) {

Console con = System.console();

int pn = 37;

double x, sinx, cosx, jsx, jcx;

Trigno trg;

Sine sino;

Cosine coso;

Printline(pn);

con.printf("%5s %7s %7s %6s %7s%n","x ","sinx ","Java ","cosx","Java");

Printline(pn);

for (x = 0; x < 1.6;) {

trg = new Trigno(x);

sino = new Sine();

coso = new Cosine();

sinx = sino.Sincomp(trg);

cosx = coso.Coscomp(trg);

jsx = Math.sin(x);

jcx = Math.cos(x);

con.printf("%3.1f %7.4f %7.4f %7.4f %7.4f%n",x,sinx,jsx,cosx,jcx);

x = x + 0.5;

}

Printline(pn);

}

}

The above program gives the following output shown in Fig. 14.12.

![](images/00166.jpeg)

**Fig. 14.12** Output screen for program 14.1T

EXERCISE-14

**I. Fill in the blanks**

14.1When several tasks are handled by a single CPU, it is called ........................... .

14.2When several sub-tasks of one task is handled in a CPU, it is called ........................... .

14.3Threads can be created by extending ........................... class.

14.4Threads can be created by implementing ........................... interface.

14.5All codes that are to be executed in a thread are to be placed inside the ...........................method.

14.6When a thread is created using new operator, the thread is in ........................... state.

14.7To bring a thread from new to a runnable state, the ........................... method is to be called.

14.8When a thread is waiting for an action (like I/O operation) it is said to be in ...........................state.

14.9At any one instance of time ........................... thread(s) will be in running state.

14.10The decision, which thread is to enter the CPU, is made by the ........................... .

14.11A thread with lower priority value will be given ........................... priority than a thread with higher priority value.

**II. Write Java programs for the following:**

14.12Write a Java program to convert the sequence of characters AB*CD/+ representing the Polish notation to the original expression A*B+C/D. Use two threads to perform the evaluation.

14.13Write a Java program to compute the first 25 prime numbers. Also compute the first 50 Fibonacci numbers given by f[n]=f[n-1]+f[n-2], with f1=f2=1. Create two threads to compute each one of them. Set the priority of thread that computes Fibonacci number to 8 and the other to 5\. After calculating 20 Fibonacci numbers, make that thread to sleep and take up the prime number computation. After computing the 10 prime numbers continue the Fibonacci number computing.

15AppletsIn this chapter, you will learn about applets. Applets are a second kind of program supported by Java language. Applets are programs that travel across a network as bytecodes, load automatically in the local machine and are executed by web browsers. The architecture of an applet, how to create and embed them in an HTML document are discussed in this chapter.

**15.1 APPLET BASICS**

Applets are a second kind of program that Java supports. Applets are programs that can be downloaded from a foreign machine through a network and executed in a local machine. Applets are not controlled by the local operating system. Applets can not access local resources in the computers. Applets are split into small packets called bytecodes and travel across the network. These bytecodes are reassembled by the Java Virtual Machine (JVM) in the receiving machine and are executed by the browser. Applets cannot access the local resources like hard disk and floppy. Applets cannot be executed directly. An applet can only be an element of an HTML page. Therefore, an applet can be executed only by executing an HTML page. These HTML pages, as usual, are executed by web browsers. For testing purpose, the **applet** element of an HTML page can be executed by **appletviewer** provided in the JDK. Applets are used for client side programming.

Applets do not use **main()** method and **System.out.println()** method. Applets use only graphics methods for output. They generate window-based output. Therefore, they need graphics support. To draw graphics output, they make use of Java's Abstract Window Tool kit(AWT). Applets are defined in Applet class. Therefore, to write an applet program, the java.applet and java.awt packages are to be imported. The **JApplet** is defined in **Swing**.

A simple applet program is given in program 15.1.

Program 15.1![](images/00013.jpeg)

/* This is a simple applet

ka.somasundaram@gmail.com */

import java.applet.Applet;

import java.awt.Graphics;

public class Myapplet extends Applet {

public void paint(Graphics g) {

g.drawString(“Welcome to Applet World”, 20, 40);

}

}

Compile this program as has been done for application program as below:

C>javac Myapplet.java

Then create test1.htm file with the following applet element. In the simplest form, the applet element is:

**<applet code = Myapplet width = 200 height = 150 >**

**<\applet>**

Then execute the htm file with **appletviewer** as :

C>appletviewer test1.htm

The output of this program is given below:

![](images/00167.jpeg)

**Fig. 15.1** Output screen for program 15.1 when executed with appletviewer

The same test1.htm viewed through the Firefox and Internet Explorer browsers is given below:

![](images/00168.jpeg)

**Fig. 15.2** Output screen of program 15.2 when viewed with Firefox (top) and Internet Explorer (bottom)

In the above program, the applet window has a width of 200 pixel and height of 150 pixel. The String "Welcome to Applet World" is displayed at the x,y co-ordinate 20,40 of the display area.

Instead of creating two programs, an applet program and another htm file, to execute the applet, the applet element of htm file can be embedded within the applet program itself as a comment. By this method, the htm and applet program can be combined and executed as a single program. The combined htm tag and applet is given in program 15.2.

Program 15.2![](images/00013.jpeg)

/*

<applet code = Myapplet1 width = 200 height = 150>

</applet>

ka.somasundaram@gmail.com

*/

import java.applet.Applet;

import java.awt.Graphics;

public class Myapplet1 extends Applet {

public void paint(Graphics g) {

g.drawString(“Welcome to Applet World”, 20, 40);

}

}

First compile the program 15.2 using **javac** compiler. Then execute the program using **appletviewer** and specifying the applet's source file.

C>appletviewer applet1.java

The result of the above program 15.2 is shown in Fig. 15.3.

![](images/00169.jpeg)

**Fig. 15.3** Output screen for program 15.2

Applets rely for input and output on AWT. All user interactivity with the applet is event-driven, such as mouse click. Therefore, all elements that compose an applet can be understood only after knowing the details of event handling. In the following sections the basics of an applet are given.

![](images/00011.jpeg)Applets can only be a part of HTML page and are executed by web browsers. However, during the development stage, applets can be executed directly using appletviewer.

15.2 APPLET LifeCycle METHODS

Applets are created, executed, stopped and destroyed by appropriate methods provided in **Applet** class. All these activities are carried out by the following methods. They are called lifecycle methods. These methods are called by AWT automatically. Appropriate methods can be overridden to meet the users requirement.

(a) **init()** This method is used to initialize the variables of the applet. This is the method called first. This is called only once.

(b) **start()** This method is called automatically after the **init()** method. It is also called whenever a user returns to the page containing the applet after going to a different page. **start()** method can be called repeatedly while the **init()** method is called only once, when the applet is loaded. It is in this method that a thread is restarted.

(c) **paint()** This method is called automatically after the **start()** method. The user screen is drawn using the **paint()** method. This method has an argument of type **Graphics** defined in AWT. The **paint()** method is called when the applet begins execution.

(d) **stop()** This method is called automatically when a user leaves the page containing the applet. Hence, it can be called repeatedly. This helps the suspension of the activity when the user is not using the applet. Otherwise, it will slow down the system performance.

(e) **destroy()** This method is called automatically when the browser ends the activity. This method helps to release the resources used by the applet. A user has to put all the codes required to wind up the final activities when the applet is removed from the memory of the system. The **stop()** method is called automatically before **destroy()** method.

Program 15.3 gives an illustration to write an init, start, stop and destroy methods. The strings mesg1 to mesg4 are not assigned initial values. They are assigned string literals when the respective methods are executed. The string mesg3 is assigned a text inside the **destroy()** method. Statements inside **stop** and **destroy** methods will be executed only when the applet is stopped and destroyed. This can be done by restarting the applet.

Program 15.3![](images/00013.jpeg)

/* This program illustrates the lifecycle methods of applet

ka.somasundaram@gmail.com

<applet code = Allmethod1 width = 250 height = 200>

</applet>

*/

import java.applet.Applet;

import java.awt.Graphics;

public class Allmethod1 extends Applet {

String mesg1, mesg2, mesg3, mesg4;

public void destroy() {

mesg4 = “system is destroying your applet”;

}

public void init() {

mesg1 = “message from init method”;

}

public void stop() {

mesg3 = “message from stop method”;

}

public void start() {

mesg2 = “message from start method”;

}

public void paint(Graphics gp) {

gp.drawString(“Demo for basic methods of applet”, 20, 40);

if (mesg1 != null) {

gp.drawString(mesg1, 20, 80);

}

if (mesg2 != null) {

gp.drawString(mesg2, 20, 100);

}

if (mesg3 != null) {

gp.drawString(mesg3, 20, 120);

}

if (mesg4 != null) {

gp.drawString(mesg4, 20, 140);

}

}

}

The applet when executed gives the following output screen:

![](images/00170.jpeg)

**Fig. 15.4** Output screen for program 15.3

In the output window, select Applet and click Restart. This will destroy the applet and start again.

As a result, mesg3 and mesg4 are assigned values and displayed in the new screen as shown below:

![](images/00171.jpeg)

**Fig. 15.5** Ouput screen for program 15.3 after Restart

15.3 SOME GENERAL METHODS OF APPLET

Some of the general methods defined in **Applet** class are given in Table 15.1.

**Table 15.1** **Some general methods defined in Applet class**

| *Method* | *Purpose of the Method* |
|       1. | String getAppletInfo() | Returns the string that describes the applet |
|       2. | URL getCodeBase() | Returns the URL associated with the applet |
|       3.  | URL getDocumentBase() | Returns the URL of the HTML page that contains the applet |
|       4.  | String getParameter(String pname) | Returns the string associated with the parameter pname |
|       5. | String[][] getParameterInfo() | Returns a string table that is defined in the applet |
|       6. | boolean isActive() | Returns true if the applet has been started; returns false if the applet has been stopped |
|       7.  | void r esize(int width, int height) | Resizes the window according to width and height |
|       8.  | void showStatus(String s) | Displays the String s in the status window of the browser |

15.4 DISPLAYING TEXT IN STATUS BAR

Text in the status bar of the browser window can be displayed using the **showStatus()** method. Program 15.4 shows the use of this method and **isActive** method.

Program 15.4![](images/00013.jpeg)

/*

<applet code = StatusBar width = 300 height = 100>

</applet>

ka.somasundaram@gmail.com

*/

import java.applet.Applet;

import java.awt.Graphics;

public class StatusBar extends Applet {

public String state() {

if (isActive()) {

return “applet is alive”;

} else {

return “applet is dead”;

}

}

public void paint(Graphics gp) {

gp.drawString(“Status bar demo”, 80, 40);

gp.drawString(state(), 80, 60);

showStatus(“Text for the status bar”);

}

}

The output screen for the above program is given below:

![](images/00172.jpeg)

**Fig. 15.6** Output screen for program 15.4

15.5 EMBEDDING APPLET INFORMATION

Information or description about the applet can be defined in the **getAppletInfo** method and can be used in the user window. This method is illustrated in program 15.5.

Program 15.5![](images/00013.jpeg)

/*

<applet code = Appinfo width = 200 height = 200>

</applet>

ka.somasundaram@gmail.com

*/

import java.applet.Applet;

import java.awt.Graphics;

public class Appinfo extends Applet {

public String getAppletInfo() {

return “Author :Dr.K.Somasundaram”;

}

public void paint(Graphics gp) {

gp.drawString(getAppletInfo(), 20, 40);

}

}

The output screen for the above program is given below:

![](images/00173.jpeg)

**Fig. 15.7** Output screen for program 15.5

15.6 THE HTML APPLET TAG

An applet can be an element of an HTML page. The applet statement itself has its own structure and is called applet tag. The individual components define behaviors and properties of an applet. The general structure of an applet tag is given below. Those written with [...] are optional and the other entries are mandatory for an applet.

<APPLET

[CODEBASE = codebase URL]

CODE = appletName

[archive = archivefile]

[ALT = alternateText]

[NAME = appletInstanceName]

WIDTH = pixels HEIGHT = pixels

[ALIGN = alignment]

[USPACE = pixels]

[HSPACE = pixels]

>

[ <PARAM NAME = attributeName VALUE = value>]

[ <PARAM NAME = attributeName VALUE = value>]

.

.

[text to be displayed in the absence of non-java browser]

</APPLET>

CODEBASE

It defines the URL that contains the applet code. If CODEBASE is not defined, the URL of the HTML document is used.

CODE

It specifies the name of the class file of the applet. It is a mandatory requirement. This file is relative to the code base URL of the HTML document or as specified by CODEBASE.

ARCHIVE

It specifies the archive (JAR) file name. It can be used when a group of files are needed for applet execution.

ALT

It specifies the text that is to be displayed if the browser could understand the applet tag but could not execute the applet. It is an optional attribute.

NAME

It specifies the name for the applet instance. Names help one applet to find another applet on the same page to communicate with them. It is an optional attribute.

WIDTH and HEIGHT

This specifies the width and height of the applet display area. It is given in pixels and they are integer numbers.

ALIGN

It specifies the alignment of the applet in the web page. The predefined values are **LEFT**, **RIGHT**, **TOP**, **BOTTOM**, **MIDDLE**, **BASELINE**, **TEXTTOP**, **ABSMIDDLE** and **ABSBOTTOM**.

PARAMNAME and VALUE

Parameters can be defined, given a name and a value. **PARAM** declares it is a parameter, **NAME** declares the name of the parameter and **VALUE** specifies the value that the variable defined by **NAME** can take. The value can be passed into the applet using **getParameter()** method. It is an optional attribute.

VSPACE and HSPACE

VSPACE specifies the space above and below the applet in pixels and HSPACE specifies the space on the left and right side of the applet in pixels.

![](images/00011.jpeg)Using HTML applet tag, applet codes stored in a remote URL server can be brought to local machines and executed using web browsers.

15.7 READING PARAMETERS INTO APPLETS

Applets can read data defined in the applet tag using **PARAM** attribute. It is one of the ways to bring data into the applet. The **getParameter()** returns a String type. Therefore, if numeric values are defined, they are to be converted from String to numeric types. Program 15.6 shows the use of **getParameter()** method.

Program 15.6![](images/00013.jpeg)

import java.applet.Applet;

import java.awt.Graphics;

/*

<applet code = Param width = 250 height = 200>

<param name = author value = “Dr.K.Somasundram”>

<param name = age value = “60”>

<param name = designation value = “Professor”>

<param name = institute value = “Gandhigram Rural Institute”>

</applet>

ka.somasundaram@gmail.com

*/

public class Param extends Applet {

public void paint(Graphics gp) {

String au = getParameter(“author”);

String ag = getParameter(“age”);

int balance = 65 – Integer.parseInt(ag);

String desg = getParameter(“designation”);

String inst = getParameter(“institute”);

gp.drawString(“Author : “ + au, 20, 40);

gp.drawString(“Age : “ + ag, 20, 60);

gp.drawString(“Designation: “ + desg, 20, 80);

gp.drawString(“Affliation : “ + inst, 20, 100);

gp.drawString(“Will retire after : “ + balance + “years”, 20, 120);

showStatus(“Parameter method”);

}

}

The output screen for the above program is given below:

![](images/00174.jpeg)

**Fig. 15.8** Output screen for program 15.6

After reading this chapter, you should have learned the following:

*   Applets are programs that can be accessed from a remote server and executed in a local machine, using a web browser.
*   Applets can only be a part of HTML page.
*   Applets can not access local resources.
*   Applets make use of graphic methods for output

In the next chapter, you will learn about graphics.

![](images/00053.jpeg)

Problem 15.1T

Write an applet to display the date and time. The time is to be shown like a digital clock.

Program 15.1T![](images/00013.jpeg)

/*

This program displays the date and time like a real clock

ka.somasundaram@gmail.com

<applet code = TIO151 width = 480 height = 200>

</applet>

*/

import java.applet.Applet;

import java.awt.Graphics;

import java.awt.Color;

import java.awt.Font;

import java.util.GregorianCalendar;

import java.util.Calendar;

public class TIO151 extends Applet {

String date;

String time;

int month, day, year;

Font ft;

int sec, min, hr;

GregorianCalendar calendr;

public void init() {

setBackground(Color.green);

setForeground(Color.black);

//set font size and type

ft = new Font(“Courier”, Font.PLAIN, 70);

setFont(ft);

}

public void paint(Graphics gp) {

// creating current date

calendr = new GregorianCalendar();

day = calendr.get(Calendar.DATE);

month = calendr.get(Calendar.MONTH);

month += 1; // January is 0 hence this conversion

year = calendr.get(Calendar.YEAR);

date = “ “ + day + “–” + month + “–” + year;

sec = calendr.get(Calendar.SECOND);

min = calendr.get(Calendar.MINUTE);

hr = calendr.get(Calendar.HOUR);

time = “ “ + hr + “:” + min + “:” + sec;

gp.drawRect(5, 5, 470, 190);

gp.drawString(date, 20, 80);

gp.drawString(time, 20, 170);

try {

Thread.currentThread().sleep(500);

} catch (InterruptedException ie) {

;

}

repaint();

showStatus(“Clock Display”);

}

}

The above program gives the following output:

![](images/00175.jpeg)

**Fig. 15.9** Output screen for program 15.1T

EXERCISE–15

**I. Fill in the blanks:**

15.1Java language supports two types of programs ........................... and ........................... .

15.2Applets travel in a network as ........................... .

15.3The applet is executed by ........................... .

15.4Applet is defined in ........................... class.

15.5Applets need methods defined in ........................... class for their output.

15.6An applet does not need ........................... method as in the application program.

15.7An applet can be executed only by placing the ........................... tag in ........................... page.

15.8Any variable in an applet can be initialized using ........................... method.

15.9 ........................... method is called automatically before the destroy() method is called.

15.10 ........................... method removes the applet from the memory.

**II. Write applets for the following problems:**

15.11Write an applet that displays your address on the screen. Run it using a browser (after writing an HTML tag) and appletviewer.

15.12Write an applet for the problem in question 15.11 by taking the address values from parameter.

16GraphicsIn this chapter, you will learn about graphics and methods used for drawing lines and regular shapes like rectangle, oval, polygon and polyline. Some basic methods used for handling fonts are also given.

Java provides a variety of tools for designing graphics and graphical user interface. All such tools are provided in Abstract Window Toolkit (AWT) package. This package contains a large number of classes. The Swing classes, which have better capability than AWT, came later. In this chapter, we will see the graphics methods to generate regular shapes. Generally, a window is created first and graphic objects are drawn on it. One way to create a window is by using an applet. An applet creates a window on which graphics objects can be drawn. Applet window is a closable one, i.e. by clicking the close icon(x) on the window, the window can be closed. Another way to create a window is by using the frame created in **Frame** class. A frame window is not closable by clicking the close icon(x) on the window. An appropriate method is to be used to close it. **Graphics** tools are available in **java.awt.Graphics** class. The applet is obtained from **java.applet.Applet** class. The frame window is obtained from **java.awt.Frame** class. Since **Graphics** class is an abstract class, a graphics context is obtained indirectly.

One way to get **Graphics** context is by passing **Graphics** as a parameter to the **paint()** or **update()** methods. In the examples to follow, applet windows are used to draw the graphic objects.

![](images/00011.jpeg)To draw graphics objects, a window is needed. One way to obtain a window is by creating an applet which automatically creates **Panel** type window. Alternatively, a **Frame** window can also be used.

16.1 DRAWING LINES

Lines are drawn using the following method:

public void draw Line**(**int x1, int y1, int x2, int y2)

draws a line in the current color, from the point (x1, y1) to (x2, y2)

The following program 16.1 shows the **drawLine()** method:

Program 16.1![](images/00013.jpeg)

/*

<applet code = Line width = 250 height =300 >

</applet>

ka.somasundaram@gmail.com */

import java.applet.Applet;

import java.awt.Graphics;

public class Line extends Applet {

public void paint(Graphics gp) {

int x1 = 10, y1 = 250;

int x2 = 200, y2 = 10;

gp.drawLine(x1, y1, x2, y2);

gp.drawString(“Line”, 20, 270);

}

}

The above program gives the following output:

![](images/00176.jpeg)

**Fig. 16.1** Output screen for program 16.1

16.2 DRAWING RECTANGLES

The parameters specifying a rectangle are shown in Fig. 16.2.

![](images/00177.jpeg)

**Fig. 16.2** Parameters specifying a rectangle

Rectangles of different styles can be drawn using the following methods:

public void drawRect(int x, int y, int width, int height)

draws a rectangle with top left corner at (x, y) with the specified width and height in the current color.

public void drawRoundRect(int x, int y, int width, int height, int arcw, int arch)

Draws a round cornered rectangle with top left corner at (x, y) with the specified width and height in the current color; arcw is the horizontal diameter of the arc at the four corners and arch is the vertical diameter of the arc.

public void draw3DRect(int x, int y, int width, int height, boolean raised)

Draws a 3-d rectangle with top left corner at (x,y) with the specified width and height in the current color; if the raised is true, the rectangle appears to be raised above the surface, otherwise it is sunk into the surface.

public void fillRect(int x, int y, int width, int height)

Draws a filled rectangle

public void fillRoundRect(int x, int y, int width, int height, int arcw, int arch)

Draws a filled round cornered rectangle

public void fill3DRect(int x, int y, int width, int height, boolean raised)

Draws a filled 3D rectangle

The following program 16.2 shows the use of various rectangle drawing methods:

Program 16.2![](images/00013.jpeg)

/* Graphics objects are drawn on the Applet window

<applet code = Rectangle width =300 height =350 >

</applet>

ka.somasundaram@gmail.com

*/

import java.applet.Applet;

import java.awt.Graphics;

public class Rectangle extends Applet {

public void paint(Graphics gp) {

int x = 10, y = 25;

int width = 100, height = 130;

gp.drawRect(x, y, width, height);

gp.drawString(“Rectangle”, 10, 170);

gp.fillRect(160, 25, 100, 130);

gp.drawString(“Filled Rectangle”, 160, 170);

gp.drawRoundRect(10, 180, 100, 130, 20, 20);

gp.drawString(“Round corner Rectangle”, 10, 330);

gp.fill3DRect(160, 180, 100, 130, false);

gp.drawString(“Filled 3D Rectangle”, 160, 330);

showStatus(“Applet with rectangles”);

}

}

The above program gives the following output:

![](images/00178.jpeg)

**Fig. 16.3** Output screen for program 16.2

These rectangles can also be drawn on a frame window. To create a frame window, the **Frame** class is used. A frame window is created by inheriting the **Frame** in a class and creating an instance of that class. The **paint()** method is used to obtain a **Graphics** context and call drawing methods. The following program 16.3 shows the use of a frame window to draw the graphics objects. This is an application program.

Program 16.3![](images/00013.jpeg)

/* The graphics objects are drawn on the Frame window

ka.somasundaram@gmail.com

*/

import java.awt.Graphics;

import java.awt.Frame;

class Myframe extends Frame {

Myframe(String title) {

super(title);

setSize(300, 350);

}

public void paint(Graphics gp) {

int x1 = 10, y1 = 35;

int x2 = 100, y2 = 120;

gp.drawRect(x1, y1, x2, y2);

gp.drawString(“Rectangle”, 10, 170);

gp.fillRect(160, 35, 100, 120);

gp.drawString(“Filled Rectangle”, 160, 170);

gp.drawRoundRect(10, 180, 100, 130, 20, 20);

gp.drawString(“Round corner Rectangle”, 10, 330);

gp.fill3DRect(160, 180, 100, 130, false);

gp.drawString(“Filled 3D Rectangle”, 160, 330);

}

}

public class FRectangle {

public static void main(String args[]) {

Myframe mframe = new Myframe(“Frame with Rectangles”);

mframe.setVisible(true);

}

}

The above program gives the following output:

![](images/00178.jpeg)

**Fig. 16.4** Output screen for program 16.3

![](images/00011.jpeg)Graphics methods are called on Graphics object. The graphics object is obtained by calling the **paint()** method with Graphics object as parameter.

16.3 DRAWING OVALS AND CIRCLES

Ovals (ellipse) can be drawn using the following methods. Special case of oval becomes circle. Methods used for drawing ovals are:

public void drawOval(int x, int y, int width, int height)

Draws an oval bounded by a rectangle with its top left corner at (x, y) with the specified width and height

public void fillOval(int x, int y, int width, int height)

Draws a filled oval

The following program 16.4 illustrates the use of **drawOval** method to draw ellipses and circles:

Program 16.4![](images/00013.jpeg)

/* This program illustrates the drawOval() method

<applet code = Oval width =300 height =350 >

</applet>

ka.somasundaram@gmail.com

*/

import java.applet.Applet;

import java.awt.Graphics;

public class Oval

extends Applet {

public void paint(Graphics gp) {

int x = 10, y = 25;

int width = 100, height = 130;

gp.drawOval(x, y, width, height);

gp.drawString(“Oval”, 10, 170);

gp.fillOval(140, 25, 160, 100);

gp.drawString(“Filled Oval”, 160, 170);

gp.drawOval(10, 200, 100, 100);

gp.drawString(“Circle”, 10, 330);

gp.fillOval(160, 200, 100, 100);

gp.drawString(“Filled Circle”, 160, 330);

showStatus(“Applet with Ovals and circles”);

}

}

The above program gives the following output:

![](images/00179.jpeg)

**Fig. 16.5** Output screen for program 16.4

16.4 DRAWING ARCS

The co-ordinates to draw an arc are specified as shown in Fig. 16.6.

![](images/00180.jpeg)

**Fig. 16.6** Parameters specifying an arc

Arcs are drawn using the following methods:

public void drawArc(int x, int y, int width, int height, int startAngle, int arcAngle)

Draws an arc bounded by a rectangle having its top left corner at (x, y) with specified width and height; the arc starts at startAngle and sweeps an angle arcAngle.

public void fillArc(int x, int y, int width, int height, int startAngle, int arcAngle)

Draws a filled arc

The following program 16.5 shows the use of **drawArc()** method.

Program 16.5![](images/00013.jpeg)

/* This program illustrates the drawArc() method

<applet code = Arc width =300 height =350 >

</applet>

ka.somasundaram@gmail.com

*/

import java.applet.Applet;

import java.awt.Graphics;

public class Arc extends Applet {

public void paint(Graphics gp) {

int x = 10, y = 25;

int width = 100, height = 130;

gp.drawArc(x, y, width, height, 10, 110);

gp.drawString(“Arc”, 10, 130);

gp.fillArc(160, 25, 100, 130, 10, 110);

gp.drawString(“Filled Arc”, 160, 130);

gp.drawArc(10, 180, 100, 130, 20, 260);

gp.drawString(“Abtuse Arc”, 10, 330);

gp.fillArc(160, 180, 100, 130, 20, 260);

gp.drawString(“Filled Arc”, 160, 330);

showStatus(“Applet with Arcs”);

}

}

The above program gives the following output:

![](images/00181.jpeg)

**Fig. 16.7** Output screen for program 16.5

16.5 DRAWING POLYGONS

Polygons with many corners are drawn using the following methods. Each method takes two **int** type arrays, one for all the x co-ordinates and another for all the y co-ordinates, that forms the polygon. All polygons drawn using these methods are closed.

public void drawPolygon(int xPoints[], int yPoints[], int nPoints)

Draws a closed polygon defined by the arrays xPoints and yPoints; nPoints represent the number of (x,y) pairs. Usually, the starting and ending x and y points are to be the same. If the user does not give the ending point as the same as starting point, this method closes the line at the starting point.

public void fillPolygon(int xPoints[], int yPoints[], int nPoints)

Draws a filled closed polygon specified by the arrays xPoints and yPoints and nPoints

public void drawPolygon(Polygon p)

Draws the outline of a polygon defined by the Polygon object P

The following program 16.6 illustrates the use of two of the polygon drawing methods:

Program 16.6![](images/00013.jpeg)

/* Applet to draw drawPolygons

<applet code = Polygon width =300 height =350 >

</applet>

ka.somasundaram@gmail.com

*/

import java.applet.Applet;

import java.awt.Graphics;

public class Polygon extends Applet {

public void paint(Graphics gp) {

int x[]

={110,60,10,10,60,110,160,210,210,160,110,110};

int y[]

={60,10,60,160,210,160,210,160,60,10,60,160};

int fx[] ={110,90,90,110,130,150,150,130,110};

int fy[] ={250,270,290,310,310,290,270,250,250};

int n = 12;

int fn = 9;

gp.drawPolygon(x, y, n);

gp.drawString(“Polygon”, 90, 210);

gp.fillPolygon(fx, fy, fn);

gp.drawString(“Filled Polygon”, 160, 300);

showStatus(“Applet with Polygons”);

}

}

The above program gives the following output:

![](images/00182.jpeg)

**Fig. 16.8** Output screen for program 16.6

16.6DRAWING POLYLINE

The **drawPolygon()** method always draw a closed polygon. There is no way to draw an open-ended polygon. This is achieved through a **drawPolyline()** method. This method draws a series of connected lines. The method used for drawing such a polyline is :

public void drawPolyline(int xPoints[], int yPoints[], int nPoints)

Draws a sequence of connected lines, specified by the arrays xPoints and yPoints; each pair (x,y) gives one point. The number of points for the polyline is nPoints.

The following program 16.7 shows the use of **drawPolyline()** method.

Program 16.7![](images/00013.jpeg)

/*

<applet code = Polyline width =250 height =250 >

</applet>

ka.somasundaram@gmail.com

*/

import java.applet.Applet;

import java.awt.Graphics;

public class Polyline extends Applet {

public void paint(Graphics gp){

int x [] ={60,10,10,60,110,160,210,210,160};

int y [] ={10,60,160,210,160,210,160,60,10};

int n = 9;

gp.drawPolyline(x, y, n);

gp.drawString(“Polyline”, 90, 210);

showStatus(“Applet with Polylines”);

}

}

The above program gives the following output:

![](images/00183.jpeg)

**Fig. 16.9** Output screen for program 16.7

![](images/00011.jpeg)The drawPolygon() method always draws a closed polygon, while the drawPolyline() method draws an open ended polygon.

After reading this chapter, you should have learned the following:

*   Graphics methods are defined in Graphics class in AWT package.
*   Graphics objects can be drawn only on a window.
*   There are several methods to draw regular shapes.
*   paint() method in Graphics class is needed to support graphics drawing.

![](images/00053.jpeg)

Problem 16.1T

Write a Java program to produce a rotating color disc:

Program 16.1T![](images/00013.jpeg)

/*

This program makes a rotating color disc. This is

an application program

ka.somasundaram@gmail.com

*/

import java.awt.Frame;

import java.awt.Graphics;

import java.awt.Color;

import java.awt.event.WindowAdapter;

import java.awt.event.WindowEvent;

class Disc extends Frame {

String forecolor, backcolor;

int rgbval;

String rgb;

Color bgclr, fgclr;

int fgb, bgr;

Color color[] = {

Color.cyan, Color.red, Color.blue,

Color.white, Color.orange, Color.pink

};

Disc(String str) {

super(str);

setSize(200, 200);

addWindowListener(new WindowAdapter() {

public void windowClosing(WindowEvent we) {

System.exit(0);

}

});

setBackground(Color.green);

}

public void paint(Graphics gp) {

int colorn = color.length;

gp.drawString(“ Rotating Color disc”, 100, 20);

int index;

while (true) {

for (int i = 0; i < colorn; i++) {

index = Math.abs(colorn – i);

if (index > 5) {

index = 0;

}

gp.setColor(color[index]);

gp.fillArc(20, 40, 150, 150, 0, 60);

index = (++index > 5) ? 0 : index;

gp.setColor(color[index]);

gp.fillArc(20, 40, 150, 150, 60, 60);

index = (++index > 5) ? 0 : index;

gp.setColor(color[index]);

gp.fillArc(20, 40, 150, 150, 120, 60);

index = (++index > 5) ? 0 : index;

gp.setColor(color[index]);

gp.fillArc(20, 40, 150, 150, 180, 60);

index = (++index > 5) ? 0 : index;

gp.setColor(color[index]);

gp.fillArc(20, 40, 150, 150, 240, 60);

index = (++index > 5) ? 0 : index;

gp.setColor(color[index]);

gp.fillArc(20, 40, 150, 150, 300, 60);

try {

Thread.sleep(200);

} catch (InterruptedException ie) {

;

}

}

}

}

}

public class Colordisc {

public static void main(String args[]) {

Disc dframe = new Disc(“Rotating Disc”);

dframe.setVisible(true);

}

}

The above program gives the following output:

![](images/00184.jpeg)

**Fig. 16.10** Output screen for program 16.1T

EXERCISE-16

**I. Fill in the blanks**

16.1Graphics object can only be drawn on ........................... .

16.2A window can be created using ........................... class or ........................... class.

16.3A ...........................window is closable while ........................... window is not closable.

16.4The drawPolygon method always draws a ........................... polygon.

16.5To draw an open-ended polygon the ........................... method can be used.

**II. Write Java programs for the following problems:**

16.6Write a program to draw a filled rectangle and expand continuously.

16.7Write a program to draw a one-handed clock.

16.8Write a program to draw a rectangle and print your address inside.

16.9Write a program to simulate a bouncing rubber ball on a hard floor. Show at least 5 bounces.

16.10Draw a polygon with 8 corners.

Reference Books

1\. *Core Java, Volume 1 - Fundamentals*, C.S. Horstmann and G. Cornell, Pearson Education Asia Pvt. Ltd., New Delhi, India, 2004.

2\. *Java2 Programming*, Black Book, Steven Holzener et al, Paraglyph Press / dreamTech Press, New Delhi, 2006.

3\. *The Complete Reference Java2*, Herbert Schildt, Tata McGraw Hill, Fifth Edition, New Delhi, 2003.

4\. [http://www.oracle.com/technetwork/java/index.html](http://www.oracle.com/technetwork/java/index.html)

Answers to Questions

**Exercise – 1**

1.1 encapsulation, inheritance, polymorphism

1.2 encapsulation

1.3 class

1.4 class

1.5 safe

1.6 true

1.7 operating system

1.8 applet, operating system

1.9 API

1.10class

1.11independent

1.12software

**Exercise – 2**

2.1 literals

2.2 Ox

2.3 octal

2.4 do not depend

2.5 8

2.6 char

2.7 the block

2.8 1class, Mat-value, float

2.9 float, double

2.10escape sequence

2.11double

**Exercise – 3**

3.1 of {and}

3.2 ;

3.3 main

3.4 three

3.5 int

3.6 type casting

3.7 block

3.8 block

3.9 class

3.10not be

3.11float

3.12printf

3.13conversion

**Exercise – 4**

4.1 four

4.2 3

4.3 1.5

4.4 50

4.5 invalid

4.6 false

4.7 >>>

4.8 false

4.9 true

4.10true

**Exercise – 5**

5.1 branching

5.2 nested

5.3 many

5.4 literal

5.5 do .. while

5.6 start

5.7 true

5.8 false

5.9 loops, switch

5.10break

**Exercise – 6**

6.1 like typed

6.2 object

6.3 new

6.4 varying

6.5 not required

6.6 Arrays

**Exercise – 7**

7.1 class

7.2 class

7.3 object

7.4 instance

7.5 new, reference

7.6 object reference variable

7.7 reference

7.8 dot

7.9 constructor

7.10true

7.11instance variable or constructor

7.12overloading

7.13data types

**Exercise – 8**

8.1 extends

8.2 super

8.3 false

8.4 overloading

8.5 overriding

8.6 method overloading, method overriding

8.7 final

8.8 final

8.9 static

8.10static

8.11static

8.12abstract

8.13abstract

**Exercise – 9**

9.1 class

9.2 import

9.3 access specifier

9.4 protected

9.5 package

9.6 package

9.7 java.lang

9.8 interface

9.9 without

9.10final

9.11implemented

9.12any

9.13abstract

**Exercise – 10**

10.1 basic

10.2 can

10.3 Number

10.4 java.lang

10.5 parseByte()

**Exercise – 11**

11.1 exception

11.2 RuntimeException

11.3 Error, not to

11.4 finally

11.5 sub

11.6 Throwable

11.7 throws

11.8 checked

**Exercise – 12**

12.1 byte, character

12.2 false

12.3 FileInputStream, FileOutputStream

12.4 Filter

**Exercise – 13**

13.1 String

13.2 StringBuffer

13.3 java.lang

13.4 is not

13.5 equals()

13.6 16

13.7 number of characters in it

13.8 length +16

13.9 freezed, String

13.10StringBuilder

13.11StringBuffer

**Exercise –14**

14.1 multitasking

14.2 multithreading

14.3 Thread

14.4 Runnable

14.5 run()

14.6 new

14.7 start()

14.8 blocked

14.9 one

14.10operating system

14.11lower

**Exercise – 15**

15.1 applet, application

15.2 bytecode

15.3 web browser

15.4 java.applet.Applet

15.5 Grapics

15.6 main

15.7 applet, HTML

15.8 init()

15.9 stop()

15.10destroy()

**Exercise – 16**

16.1 window

16.2 Panel, Frame

16.3 Panel, Frame

16.4 closed

16.5 drawPolyline()

AAppendix

**Conversion characters**

The conversion and the related format specifier are generally categorised in the following six types.

| (1) General - | may be applied to any argument type |
| (2) Character - | may be applied to basic types which represent Unicode characters: char, Character, byte, Byte, short, Short. |
| (3) Numeric | (i) | Integral - may be applied to integral types : byte, Byte, short, Short, int, Integer, long, Long. |
|  | (ii) | Floating point - may be applied to floating point types: float, Float, double, Double. |
| (4) Date/Time - | may be applied to types which are capable of encoding a date or time: long, Long, Calendar and Date. |
| (5) Percent (%) - | produces a literal |
| (6) Line separator(%n) - | produces a line separator |

The format specifiers for general, character and numeric types have the following syntax:

%[argument_index $][flags][width][precision]conversion

Those items written within [] are optional.

| argument_index - | is a decimal integer indicating the position of the argument in the argument list. The first argument is represented by 1 $, the second by 2 $, etc. |
| flags - | is a set of characters that modify the output format. |
| width - | is a non-negative decimal integer, indicating the minimum number of characters to be written to the output. |
| precision - | is a non-negative decimal integer usually used to restrict the number of characters. The specific depends on the conversion. |
| conversion - | is a character indicating how the argument should be formatted. The set of valid conversions for a given argument depends on the argument’s data type. |

The format specifiers for date and time have the following syntax:

%[argument_index $} [flags][width] conversion

The conversion is to be preceded by ‘t’ or ‘T’.

**A.1 CONVERSION CHARACTERS FOR NUMERIC TYPE**

The conversion characters for general and numeric type are given in Table A.1.

**Table A.1** Conversion characters for general and numeric type

![](images/00185.jpeg)

A.2 CONVERSION CHARACTERS FOR DATE AND TIME

Time

Some of the conversion characters used for formatting time are:

| H | - Hour of the day for the 24-hour clock formatted as two digits i.e. 00-23. |
| I | - Hour for the 12-hour clock formatted as two digits i.e. 01-12 |
| K | - Hour of the day for 24-hour clock, i.e. 0-23 |
| l | - Hour of the day for 12-hour clock, i.e. 1-12 |
| M | - Minutes within the hour formatted as two digits, i.e. 00-59 |
| S | - Seconds within the minute formatted as two digits, i.e. 00-60 |
| p | - am or pm |
| z | - abbreviation for time zone. |

**Date**

The conversion characters used for formatting date are:

| B | - Full name of the month, e.g. January |
| b | - Abbreviated name of the month, e.g. Jan |
| A | - Full name of the day, e.g. Monday |
| a | - Short name of the day, e.g. Mon |
| Y | - Year formatted to 4 digits, i.e. 2007 |
| y | - Last two digits of the year, i.e. 07 |
| j | - Day of the year, formatted as three digits, i.e. 001-366 |
| m | - Month formatted as two digits, i.e. 01-12 |
| d | - Day of month, formatted as two digits, i.e. 01-31 |
| e | - Day of month, formatted as two digits, i.e. 1-31 |

**Date & Time**

The conversion characters used for formatting common date/time are:

| R | Time formatted for the 24-hour clock as “%tH : %tm” |
| T | Time formatted for the 24-hour clock as “%tH : % tM : % tS” |
| r | Time formatted for the 12-hour clock as “%tI : %tM : %tS %tp” |
| D | Date formatted as mm dd yy |
| F | ISO 8601 date formatted as yyyy mm dd |
| c | Date and time formatted as “%ta %tb %td %tT %tz %ty” e.g. “Sun Jul 20 16 : 17:00 EDT 1969” |

**Flags**

Flags that modify the formatted output generated by the conversion characters are:

| - | The result is left justified. |
|  | Applicable to all types of conversions. |
| # | The result is conversion dependent alternate form |
|  | Applicable to general, integral and floating point types. |
| + | The result will always include sign |
|  | Applicable to numeric types. |
| blank | Include a leading space. |
| 0 | Include a leading zero |
|  | Applicable to numeric types |
| , | Include a “ , ” separator. Applicable to numeric types. |
| ( | Include a parenthesis for negative numbers. Applicable to numeric types. |