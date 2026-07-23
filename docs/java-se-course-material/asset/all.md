![](cover_image.jpg)

**Java SE**

**Course Material**

**Srikanth Pragada**

**(SCJP, SCWCD, SCBCD, MCTS for .Net 4.0,**

**Oracle Database SQL Expert, Oracle PL/SQL Associate Developer)**

## COPYRIGHT

Copyright @ 2016 by **Srikanth Technologies**. All rights reserved.

No part of this book may be reproduced or distributed in any form or

by any means, or stored in a database or retrieval system, without

the prior written permission of the author & publisher – **Srikanth**

**Pragada**, with the exception that the programs may be entered,

stored, and executed in a computer system, but they may not be

reproduced for publication.

Although every precaution has been taken in the preparation of this

book, the author assumes no responsibility for errors or omissions.

Neither is any liability assumed for damages resulting from the use

of information contained therein.

Srikanth Technologies

## ABOUT THE AUTHOR

**Srikanth Pragada** is the director of Srikanth Technologies, a

software training company. He started programming in early 90s

and worked with more than 15 different programming languages.

**Srikanth Pragada** holds the following certifications:

 Sun Certified Java Programmer

 Sun Certified Web Component Developer

 Sun Certified Business Component Developer

 Oracle Database SQL Certified Expert

 Oracle PL/SQL Developer Certified Associate

 Microsoft Certified Technology Specialist for .NET 4.0

 (Web Applications)

He currently conducts online, classroom and onsite training on C,

Java, Oracle, Microsoft.NET and Android technologies.

His websi[te www.srikanthtechnologies.com](http://www.srikanthtechnologies.com/) provides more information about C, Java, Android programming, Oracle and

Microsoft.Net. It contains online examinations, programs, projects,

articles and his blog.

When he is not teaching or learning, he would like to visit new

places, read books, involve in sports and listen to music.

He can be reached through his email address

[srikanthpragada@yahoo.com.](mailto:srikanthpragada@yahoo.com)

Srikanth Technologies

## HOW TO USE THIS MATERIAL

This is to be carried to classroom everyday as long as the contents

of this material are being discussed.

You are suggested to read relevant content before and after

attending the class.

Use picture and text to grasp the concept. Programs are to illustrate

how to implement the concepts. Try the programs given in this

material in your system.

Answers for exercises given in this material are found at

[http://www.srikanthtechnologies.com/books/javabook2016/answers](http://www.srikanthtechnologies.com/books/javabook2016/answers.html)

[.html](http://www.srikanthtechnologies.com/books/javabook2016/answers.html)

## REQUEST FOR FEEDBACK

We have taken considerable effort to ensure accuracy of the

contents of this material. However if you come across any mistakes

or have any suggestions to improve the quality of this material,

please take a few minutes of your valuable time to send mail to me

at **srikanthpragada@yahoo.com *.***

Alternatively you can visit my website

**www.srikanthtechnologies.com/feedback.aspx** and provide

feedback there.

Srikanth Technologies

**Getting Started With**

**Java**

**Thousand miles journey starts with a step**

**forward…**

**So, let’s get started with Java.**

Getting Started With Java

1

**WHAT WILL YOU LEARN?**

At the end of this module you will have learnt the following:

 **What is Java?**

 **History of Java**

 **Editions of Java**

 **Relationship between C, C++ and Java**

 **Features of Java language**

 **Java and Platform Independence**

 **Using Java SE**

 **First Java Program – Hello.java**

 **Standard or Primitive data types**

 **Operators in Java**

 **Control Statements**

 **Printing values using System.out.printf()**

 **Reading input using Scanner**

 **Creating and using arrays**

 **Variable number of arguments**

 **Command line parameters**

 **Exercises**

Srikanth Technologies

Getting Started With Java

2

**WHAT IS JAVA?**

 A general purpose programming language.

 Invented by **James** **Gosling**, Patrick Naughton, Chris Warth, Ed

Frank and Mike Sheridan at Sun Microsystems.

 Java was released in **May, 1995**.

 Most widely used programming language.

 Mainly used to develop web and enterprise applications.

 Provides “write once and run anywhere” features – Platform

independence.

 Influenced by **C and C++**.

 Derives its syntax from C and C++. However, it eliminated

features of C++ such as multiple inheritance, operator

overloading, friend function etc. that could cause ambiguity.

## HISTORY OF JAVA

The following are various versions of Java, when they were released

and what features were added.

 Java 1.0 was released in May, 1995\. Java was initially called as

“oak” and then renamed to Java. JDK (Java Development Kit) 1.0

was released on **January 23, 1996**.

 Java 1.1 was released to add features like inner classes, JDBC,

RMI, JavaBeans and new event handling model. JDK 1.1 was

released on **February 19, 1997.**

 Java 1.2 added JIT (Just In Time) compiler, Swing components

and Collection Framework library. JDK 1.2 was released on

**December 8, 1998**.

 Java 1.3 added JavaSound, JNDI and was released on **May 8,**

**2000**.

 Java 1.4 added regular expressions, integrated XML, assertions,

and non-blocking IO. It was released on **February 6, 2002**.

 Java 1.5 also known as Java 5.0 was released on **September**

**30, 2004**. It added generics, annotations, enumerations,

enhanced for loop, autoboxing etc.

Srikanth Technologies

Getting Started With Java

3

 Java 1.6 also known as Java 6.0 was released on **December 11,**

**2006**. It added JDBC 4.0, GUI improvements, and support for

scripting language.

 Java 7.0 also known as Java 1.7 was released on **July 7, 2011**.

It enhanced language and library.

 Java 8.0 was released on **March 18, 2014.** Lambda expressions

and Streams were two main additions in this version.

## EDITIONS OF JAVA

Java is provided as three different editions, where each edition is

meant for different types of applications.

 **Java Standard Edition – Java SE**

 **Java Enterprise Edition – Java EE**

 **Java Micro Edition – Java ME**

**Java SE (Standard Edition)**

 This is used to develop Console applications, Applets and Frame-

based applications (desktop applications).

 This edition provides features of language, core API (Application

Program Interface) related to IO Stream, Networking, Data

structures using Collections Framework etc.

 This edition comes with Java compiler, JVM and other tools to

develop applets and desktop applications.

**Java EE (Enterprise Edition)**

 This is used to develop web applications, web services, and

enterprise applications. It uses Java Language and core API.

 It is a set of specifications to be implemented by products. BEA’s

Weblogic server, IBM’s Websphere, Open source product JBoss,

Glassfish etc. implement Java EE specifications.

 Major topics of Java EE are Servlets, JSPs, Enterprise Java Beans

(EJB), Java Mailing, Java Messaging Service (JMS) etc.

Srikanth Technologies

![](index-9_1.jpg)

Getting Started With Java

4

**Java ME (Micro Edition)**

This edition is used to develop software that can be embedded into

micro devices. It uses Java language and its core API.

Some mobile phones use software developed using Java ME.

**RELATIONSHIP BETWEEN C, C++ AND JAVA**

 C was released in 1970\. C++ was released in 1980\. Java was

released in 1995.

 C and C++ are meant for System programming whereas Java is

meant for application programming.

 Java uses control structures such as if, for etc. of C language.

 Java does not support pointers, pointer arithmetic and unions.

 Java and C++ have OOP (Object oriented programming) as

common feature.

 However, Java has ignored a lot of features of C++ as these

features would cause ambiguity.

 Default function arguments, Operator overloading, Multiple

inheritance, Friend functions etc. of C++ are not supported by

Java.

 C and C++ concentrated more on providing flexibility and power,

but Java’s main focus has been robustness and Internet

programming.

Srikanth Technologies

Getting Started With Java

5

## FEATURES OF JAVA LANGUAGE

The following are the major features of Java language.

Robust

Makes programs robust (free from potential

errors). Java detects all potential problems at the

time of compiling the program. It also checks for

array boundary violation etc. at run time.

Object Oriented Supports encapsulation, inheritance and

polymorphism. Java allows the entire code to be

placed only in classes. It doesn’t allow any code to

be placed outside the class including main()

method.

Dynamic

Allocates memory for arrays and objects at run

time and handles allocation and de-allocation of

memory on its own.

Garbage collector is responsible for releasing

unused memory blocks.

Multithreaded

Supports creating and managing of multiple

threads.

Distributed

Supports programs to run on different systems

and yet communicate with each other. Provides

mechanism to transmit data from one application

to another.

Platform

Allows a compiled program (byte code) to run on

Independent

any other platform.

## JAVA IS ROBUST

 Java being a robust language checks for potential errors both at

the time of compilation and at runtime.

 Java is strongly typed language, where data type of a value

cannot be changed to another, and is case-sensitive.

 The following snippets show operations that are allowed in **C** but

not in **Java.**

Srikanth Technologies

Getting Started With Java

6

01: int a[10];

02: int i , j; // local variables, not initialized

03: a[10]=100; // accessing element outside the bounds

04: i = 10.50; // assigning float to int

05: j++; // using without initializing it

 Java also checks whether a function that is supposed to return a

value is really returning a value.

01: /* This function does not compile as it does not

02: return value when condition is false. */

03:

04: int fun(int v){

05: if ( v > 10 )

06: return 1;

07: }

 Java checks whether a piece of code is reachable during the

execution of program. If code is not reachable in all paths of

execution then it complains about it.

01: /* Unreachable code example */

02: int fun(int v) {

03: if ( v > 10 )

04: return 1;

05: else

06: return 0;

07:

08: v ++ ; // cannot be reached.

09: }

Srikanth Technologies

Getting Started With Java

7

## PLATFORM INDEPENDENT LANGUAGE

The main feature of Java language is its **platform independence**.

This allows a Java program that is compiled on one platform to run

on any other platform.

This is called as **WORA** (Write Once, Run Anywhere).

Platform independence is different from **Portability**, which allows

source code to be ported to different platforms.

Though source program is ported we need to compile the source

program on the target platform before running it.

**Windows**

**Linux**

**Portability**

**C Source**

**C Source**

**program**

**program**

**Compiler & Linker**

**Compiler & Linker**

**Native Code**

**Native Code**

Srikanth Technologies

Getting Started With Java

8

All high-level languages have portability.

**Native** **code** is the code understood by the Microprocessor and

operating system of the computer.

**NOTE**: Platform is the environment in which application programs

run. It is typically the combination of operating system and the

hardware. Platform is generally synonymous with operation system.

**COMPILING AND RUNNING OF JAVA PROGRAM**

The following figure shows the steps related to compiling and

running of Java program. Java programs are NOT compiled to

native code and instead they are compiled to **Byte code**, which is

close to native code but not native code of any platform.

Once a Java program is compiled to byte code then it can be run on

any platform where JVM (Java Virtual Machine) is available.

Srikanth Technologies

Getting Started With Java

9

**Java Source Code (.java)**

**Java Compiler**

**Byte Code (.class file)**

**Java Virtual Machine**

**Converts Byte Code to Native Code**

**Native Code/Machine Code/Binary Code**

**NOTE**: Java compiler and JVM are specific to each platform. Only

byte code is platform independent.

## JAVA AND PLATFORM INDEPENDENCE

The following picture shows how a Java program that is compiled on

Windows system can run on Linux system.

Once a Java program is compiled to Byte code (.class file), it can be

executed on any machine where JVM is available.

Most of the modern operating systems provide JVM along with

operating system allowing byte code to run straight away.

Srikanth Technologies

Getting Started With Java

10

**Windows**

**Linux**

**Java Source**

**Program (.java)**

**Java Compiler**

**Bytecode**

**Bytecode**

## JVM

### **JVM**

## USING JAVA SE

 Download Java SE (a.k.a JDK – Java Development Kit) from

http://www.oracle.com/technetwork/java/javase/downloads/jdk8

-downloads-2133151.html

 Installing Java SE is as simple as double clicking on downloaded

file (**.exe** file) and following the steps.

 It is better you install Java SE into a directory like **c:\jdk**,

instead of the default directory (which is **program** **files**

directory).

 After installing JDK, the installation program proceeds to JRE

(Java Runtime Environment) installation.

**NOTE**: You can download NetBeans IDE, an Integrated

Development Environment, from *netbeans*. *org*. Eclipse is another

IDE that can be downloaded from *eclipse*. *org*.

Srikanth Technologies

![](index-16_1.jpg)

![](index-16_2.jpg)

Getting Started With Java

11

Srikanth Technologies

Getting Started With Java

12

**Directory Structure of Java SE**

After you install Java SE into a directory (say c:\jdk), the structure

of the directory will look like below:

*c:\jdk*

*bin*

*javac.exe, java.exe*

*db*

*include*

*jre*

*lib*

**.jar*

*srikanth (user created)*

**Directory Description**

bin

Contains executable files related to JDK. It contains

JAVAC.EXE and JAVA.EXE.

db

Contains derby database.

include

Includes files for Java Native Interface.

jre

Java runtime environment.

lib

Contains Java libraries, which are in form of .jar (Java

archive) files.

srikanth

User-defined folder.

**NOTE:** It is better to create a user directory under **jdk** and put your

programs in that directory. For example, a directory with the name

**srikanth** (shown above) can be used to store user related Java

programs.

Srikanth Technologies

Getting Started With Java

13

## BASIC TOOLS

These tools are the foundation of the JDK. They are the tools you

use to create and build applications

**Tool Name Brief Description**

javac

The compiler for the Java programming language.

Java

The launcher for Java applications.

javadoc

API documentation generator.

Apt

Annotation processing tool.

appletviewer Run and debug applets without a web browser.

Jar

Create and manage Java Archive (JAR) files.

Jdb

The Java Debugger.

javah

C header and stub generator. Used to write native

methods.

javap

Class file disassemble.

extcheck

Utility to detect Jar conflicts.

**FIRST JAVA PROGRAM – HELLO.JAVA**

Type the following program using a text editor like **Notepad** and

save with the name **Hello**. **java**.

If you are using **Notepad**, make sure you enclose the filename in

quotes (“Hello.java”) while saving it, otherwise Notepad gives

default extension . **txt**.

Save this program as c:\jdk\srikanth\Hello.java.

01: // Program to print Hello World

02: public class Hello{

03: public static void main(String args[]){

04: System.out.println("Hello World!");

05: }

06: }

The above Java program prints message *Hello World!,* when you

compile and run it.

Srikanth Technologies

Getting Started With Java

14

The following are some of important components of this program.

 Every function in Java must be inside a class, so we have to

create class **Hello** to put **main()** function in it.

 Function **main**() must be declared as **static**. It must return

nothing (void) and it takes an array of type **String** as argument.

All these are mandatory.

 **System**. **out**. **println**() is used to print the given message.

**COMPILING AND RUNNING A JAVA PROGRAM**

To compile a java program, follow the steps given below:

1\. Go to command prompt using **programs**  **accessories** 

**command** **prompt**.

2\. Set **PATH** command of Windows to **bin** directory of **jdk** as

follows at the command line.

**path c:\jdk\bin**

**PATH** is required as javac.exe and java.exe are in bin directory

3\. Go to directory where **Hello**. **java** is saved (c:\jdk\programs)

4\. Compile Java program using JAVAC.EXE as follows:

**javac Hello.java**

5\. Run java program as follows from the command line:

**java Hello**

**NOTE: PATH** command is used to inform Operating System

(Windows) where it should search in the file system for executable

files. By default, OS searches for executable files only in current

directory. To see the current PATH setting, just type **PATH** at the

command prompt.

Srikanth Technologies

![](index-20_1.jpg)

Getting Started With Java

15

Srikanth Technologies

Getting Started With Java

16

**STANDARD OR PRIMITIVE DATA TYPES IN JAVA**

The table below shows the list of data types available in Java along

with number of bytes occupied by the data type and range of values

that can be stored in the data type.

**Data Type**

**Size (Bytes)**

**Range**

byte

1

-128 to 127

short

2

-32768 to 32767

int

4

-2147483648 to 2147483647

long

8

-9223372036854775808 to

9223372036854775807

float

4

1.7e-308 to 1.7e+308

double

8

3.4e-038 to 3.4e+038

boolean

true or false

char

2

Supports Unicode characters.

 All numeric types in Java are signed.

 The size of **boolean** is JVM dependent.

 Data type **char** occupies two bytes because it supports Unicode,

which needs 16 bits to store characters.

 Unicode supports characters of all languages and some

languages of Japanese and Chinese have more than 256

characters.

 The size of data types does NOT change from platform to

platform.

**NOTE**: Java doesn’t allow an un-initialized variable to be used. By

default local variables are not initialized by Java.

Srikanth Technologies

Getting Started With Java

17

## RULES TO CREATE IDENTIFIER

A name in the program is called as identifier. The following rules are

to be followed while creating identifier.

 Can contain letters, digits, _ (underscore) and $.

 Must NOT begin with a number. Can start with currency symbol

($) or _ (underscore).

 Keywords of Java cannot be used.

Valid identifiers

first_number, name$, _first, $amount

Invalid identifiers

2num, total-amount

## KEYWORDS IN JAVA

The following is the list of Java keywords. All these keywords are in

lowercase.

abstract

continue

for

new

switch

assert

default

goto

package

synchronized

boolean

do

if

private

this

break

double

implements protected

throw

byte

else

import

public

throws

case

enum

instanceof

return

transient

catch

extends

int

short

try

char

final

interface

static

void

class

finally

long

strictfp

volatile

const

float

native

super

while

*

Srikanth Technologies

Getting Started With Java

18

## LITERALS

Literal denotes a constant value, which remains unchanged

throughout the program.

 Java has three reserved literals – **null**, **true**, **false**.

 Integer literals are treated as integers unless they are suffixed

with L (letter L). Example : 100L

 Java 7.0 onwards we can use **_** (underscore) as separator

between digits.

 Integer literals can be specified in octal (0123) or hexadecimal

(oxff). Octal numbers are prefixed with **0** and hexadecimal

numbers are prefixed with **0x**.

 Floating point literals are by default taken as **double**. Use suffix **f**

to denote float literal. Example, 10.50**f.**

 Starting from Java 7.0, we can have binary literals prefixed with

**0b**.

 Escape sequence as well as Unicode values can appear in string

literals. For example, *"How are you ...\t Srikanth\u000d”*

represents a string that contains a horizontal tab (\t) and

carriage return (\u000d in hexadecimal is equal to decimal 13).

Integer

200 -7 1_23_456 0b10001111

Floating point

2.4 -2.5 .5 0.55

Character

'a' '9' ':'

Boolean

true false

String

"one" "123" "work hard"

Srikanth Technologies

Getting Started With Java

19

## ESCAPE SEQUENCE CHARACTERS

The following are the escape sequence letters supported by Java.

**Character**

**Meaning**

\ddd

Three octal digits

\uxxxx

Four hexadecimal digits

\’

Single quote

\”

Double quote

\\

Single backslash

\r

Carriage return

\n

New line (also known as line feed)

\f

Form feed

\t

Tab

\b

Backspace

## OPERATORS IN JAVA

An operator performs specific operation on the given value(s) called

as operands. Operators are divided into different categories based

on the operation performed by the operator.

**Arithmetic Operators**

The following table shows arithmetic operators available in Java.

They are shown according to the precedence of the operators.

**Operator Meaning**

++

Increment

--

Decrement

*

Multiplication

/

Division

%

Modulus

+

Addition

-

Subtraction

Srikanth Technologies

Getting Started With Java

20

**Associativity** specifies whether operators are grouped from left to

right or right to left. Unary ++ and -– operators are having ***right** **to***

***left** associativity* and other operators are having ***left** **to** **right***

*associativity*.

**Conversion and Type Casting**

 Java allows assignment between variables of compatible types.

 Java promotes all integer types such as **byte** and **short** to **int**.

 When we are converting a large data type to short data type,

explicit **type** **casting** is required.

// will FAIL as 10.50 is taken as double

float f = 10.50;

// Use **f** as suffix to indicate float

float f = 10.50**f**;

// converts double to float and then assigns

float f = **(float)** 10.50;

**Assignment Operator**

Assignment operator (=) is used to assign a value to a variable. The

value may be either a literal or an expression.

The variable and result of the expression must be of compatible data

types. Java also supports multiple assignments, where you can

assign a single value to multiple variables in a single assignment.

a = 0;

a = b = c = 0;

Srikanth Technologies

Getting Started With Java

21

**Relational Operators**

 All relational operators are binary operators.

 The result of the evaluation is always a boolean.

 Relational operators have ***left to right associativity***.

**Operator Meaning**

==

Equal To

>

Greater than

<

Less than

<=

Less than or equal to

>=

Greater than or equal to

!=

Not Equal To

**Logical Operators and Short circuiting**

Logical operators combine two conditions and return a boolean

value. The following table shows logical operators.

**Operator Meaning**

&

## AND

|

## OR

^

XOR (exclusive or)

||

Short-circuit OR

&&

Short-circuit AND

!

Unary NOT

**Short-circuit Logical Operators (&& and ||)**

Short-circuit operators check only the necessary conditions and do

NOT check both the conditions always. Evaluation of condition stops

once the outcome of the condition is known.

&& Doesn’t check second condition if first condition is false.

|| Doesn’t check second condition if first condition is true.

Srikanth Technologies

Getting Started With Java

22

if (a > b && a > c) ...

Returns false if condition **a >b** is false and doesn’t check second

condition (a > c).

if (a == b || a == c) ...

Returns true if condition a == b is true and doesn’t check second

condition.

**Bitwise operators**

Bitwise operators operate bits in integer. They can be used only with

integral data types such as int and long.

**Operator Meaning**

~

Ones complement

&

Bitwise Anding

|

Bitwise Oring

^

Bitwise XOR ( Exclusive OR)

<<

Shifts bits to left by n times by filling 0 on the right.

>>

Shifts all bits right by n times, filling left side bits with

sign bit.

>>>

Shifts all bits right by n times, filling left side bits with 0.

Srikanth Technologies

Getting Started With Java

23

The following snippet shows how to use bitwise operators.

01: public class BitOperators {

02: public static void main(String[] args) {

03: byte a = 10, b = 15;

04: // 0000 1010 & 0000 1111 = 0000 1010

05: System.out.printf("%d & %d = %d\n",a,b,a & b);

06: // 0000 1010 | 0000 1111 = 0000 1111

07: System.out.printf("%d | %d = %d\n",a,b,a | b);

08: // 0000 1010 >> 2 = 0000 0010

09: System.out.printf("%d >> 2 = %d\n", a , a >> 2);

10: // 0000 1010 << 2 = 0010 1000

11: System.out.printf("%d << 2 = %d\n", a , a << 2);

12: }

13: }

## CONTROL STATEMENTS

The following are conditional statements and looping structures

available in Java.

**if statement**

The **if** statement is used to decide whether an operation is to be

performed. If **condition** is true then statement-1 is executed

otherwise statement-2 is executed. The **else** portion is optional.

*if (condition)*

*statement-1;*

*[else*

*statement-2;]*

**Note**: If multiple statements are to be executed then enclose

statements in braces ({}).

It is possible to have nested if statements (an if statement within

another if statement). It is also possible to have multiple if

statements with if ..else.. if .. else and so on.

Srikanth Technologies

Getting Started With Java

24

**switch statement**

The switch statement is used to execute one among many

alternatives.

*switch(expression)*

*{ case label-1 : statement; [break];*

*[case label-2 : statement; [break];]…*

*[ default : statement; ]*

*}*

The following example takes same action for code 1 and 2 and

different actions for 3\. Default is used to take action for the rest of

the codes.

switch(code){

case 1 : // falls through to next case

case 2 : price = 1000; break;

case 3 : price = 500; break;

default: price = 100;

}

For switch statement, the expression must be a **char**, **byte**, **short**, **int** or an **enum** type.

Starting from Java 7.0, switch supports **string** data type also.

Srikanth Technologies

Getting Started With Java

25

String country;

// code to get value into country

switch(country)

{

case "India" : // code

case "China" : // code

case "Russia" : // code

default : // code

}

The case constant must evaluate to the same type as the switch

expression. The case constant must be a compile time constant.

**Note**: The **default** case doesn’t have to come only at the end of the

switch statement; it can be given anywhere.

**while loop**

Repeatedly executes statement(s) as long as the condition is true.

*while(condition)*

*statements;*

Following example displays all numbers from 1 to 10\. To execute

multiple statements, enclose statements in braces ({}).

int i = 1;

while ( i <= 10 ) {

System.out.println(i);

i ++;

}

**do .. while loop**

Executes the body of the loop and then checks the condition thus

guaranteeing the execution of the statement *at least for once*.

*do {*

*statement;*

*}while (condition);*

Srikanth Technologies

Getting Started With Java

26

The following program displays numbers from 1 to 10.

int i = 1;

do {

System.out.println(i);

i ++;

} while (i <= 10);

**for loop**

**for** loop executes statements as long as the condition is true. First it

executes initialization, then checks whether condition is true. If

condition is true then executes the statements and then increment

portion.

*for( initialization; condition; increment)*

*Statement;*

Variable can be declared within initialization and these variables are

available only within the loop.

for(int i=1;i<=10;i++){ //**i** is available only within for

// body

}

**break statement with loops**

The **break** statement is used to terminate loop from inside the loop.

Java provides labeled break and unlabeled break.

*break [label]*

When break statement is used without any label, it terminates

current loop.

**Labeled** **break** terminates the loop that is associated with the given

label. In the following example, break terminates 1st loop as label

first is associated with **i** loop.

Srikanth Technologies

Getting Started With Java

27

01: first:

02: for(int i=0; .. ){

03: second:

04: for(int j=0; ..) {

05: for(int k=0; …) {

06: if (cond)

07: break first;

08: }

09: }

10: }

**continue Statement**

Continue is used to stop the current iteration of the loop body and

proceed with the next iteration.

*continue [label]*

The following code ignores remaining statements in **j** loop when

condition is satisfied and starts next iteration.

01: for ( int i = 0 ; i < 10; i ++) {

02: for ( int j = 0 ; j < 10; j ++) {

03: if ( j < i )

04: continue;

05: }

06: }

Srikanth Technologies

Getting Started With Java

28

**Printing value using System.out.printf()**

Function printf() is similar to printf() function of C language. The

following are the conversion characters that can be used.

**b** - boolean, **c** – char, **d** - integer, **f** – floating point, **s** – string.

System.out.printf("int %d and float %f \n", i, f);

If conversion character and given data do not match then a runtime

error occurs. The following will produce a runtime error.

System.out.printf("%d",10.50);

**Reading input using Scanner**

Input from users can be taken using Scanner class. The following

snippet shows how to use Scanner to read an integer from user.

Scanner s = new Scanner (System.in);

int n = s.nextInt();

The following program reads a number from user using Scanner and

displays its factors.

01: import java.util.Scanner;

02:

03: public class Factors {

04: public static void main(String[] args) {

05: Scanner s = new Scanner(System.in);

06: System.out.print("Enter a number :");

07: //read an int from keyboard

08: int num=s.nextInt();

09:

Srikanth Technologies

Getting Started With Java

29

10: for (int i = 2; i <= num/2 ; i ++) {

11: if(num % i == 0)

12: System.out.println(i);

13: }

14: }

15: }

The **import** statement is required to make **Scanner** available to

current program.

**Method**

**Description**

nextInt()

Reads next integer

nextDouble()

Reads next double

nextLine()

Reads next line and returns as a string

## CREATING AND USING ARRAYS

 Array is a collection of elements.

 All elements of the array are of the same type.

 All elements are commonly referred by a single name and

individual elements are accessed using index.

 An array in Java is dynamic. We specify the size of the array at

runtime.

int a1[]; //declare an array

int [] a2; //another syntax to declare an array

// Create an array of 10 elements

a1 = new int[10];

Alternatively, you can declare and allocate memory in one step.

Srikanth Technologies

Getting Started With Java

30

// Declare and create an array

int a1[] = new int[10];

/* create an array where size of the array is determined by

the value of variable n */

int a2[] = new int[n];

**Getting array’s length using length property**

Property **length** of an array can be used to get number of elements

in an array.

System.out.printf("Length : %d", a.length);

An array name can be used to refer to an array of different sizes at

runtime. The following snippet shows how array name **arr** points to

an array of 10 elements first and then points to an array of 5

elements.

// create an array

int arr[] = new int[10];

//Array arr points to a new array of 5 elements.

arr = new int[5];

arr

## X

Old Block Ready For Garbage Collection

New Array of 5 elements

Old array of 10 elements referred by **arr** is now eligible for garbage

collection by Java.

**NOTE**: Java virtual machine has garbage collector, which takes care

of releasing unused memory blocks.

Srikanth Technologies

Getting Started With Java

31

You can create a double dimensional array using two square

brackets as follows:

int a[][] = new int[5][5];

You can create an array of 5 elements, where each element can

refer to an array of different size as follows:

int a[][] = new int[5][];

a[0] = new int[5];

a[1] = new int[10];

0

1

4

0

**…**

1

**…**

null

0

1

9

null

4

null

**Enhanced for loop**

Java provides enhanced for loop exclusively to process arrays and

collections. It takes one value from array and assigns it to loop

variable. Executes loop statements and repeats the process until

array is exhausted.

*for (datatype loopvariable : array)*

*Statement;*

The following example displays all elements of an array using

enhanced for loop. The data type of loop variable and data type of

the array must be same.

int a [] = {10,20,30,40,50};

for ( int n : a )

System.out.println (n);

Srikanth Technologies

Getting Started With Java

32

**Initializing an array**

Java allows an array to be initialized. The following examples show

how you can initialize an array in Java.

// initializes array a to given three values

int a[] = {10,20,30};

// initializes array b to given five values

int b[] = new int[] {10,20,30,40,50};

// initializes double dimensional array – 2 X 3

int bb[][]= {{1,2,3},{4,5,6}};

**NOTE**: Elements of an array are automatically initialized to default

value according to data type of array.

## VARIABLE NUMBER OF ARGUMENTS

 Java allows a method to take variable number of arguments.

 The argument is declared with **… (**ellipses**)** after data type and

before the name.

 Must be the last argument in a method.

 Argument is treated as an array inside the method.

01: public class VaryingArguments {

02: public static void main(String[] args) {

03: System.out.println(getSum(10, 20, 30));

04: System.out.println(getSum(100, 200) );

05: }

Srikanth Technologies

Getting Started With Java

33

06: public static int getSum(int... nums) {

07: int total = 0;

08: for (int n: nums) {

09: total += n;

10: }

11: return total;

12: }

13: }

## COMMAND LINE PARAMETERS

 Parameters that are passed at the time of invoking a java

program from command line are called as command line

parameters.

 These parameters can be used to provide input to the program.

 These parameters are accessible from ***main*****()** through ***args***

parameter, which is an array of strings.

 The ***length*** attribute of ***args*** returns the number of parameters passed on command line.

01: // program to display command-line parameters

02: public class CLA {

03: public static void main(String args[]){

04: System.out.printf("Args Count: %d\n",args.length);

05: // display parameters

06: for(String s : args)

07: System.out.println(s);

08: } // end of main

09: }

Call the previous program from command line as shown below:

c:\jdk\srikanth>java CLA One Two <Enter>

Args Count : 2

One

Two

**NOTE**: Method **main**() must have a parameter of type String[].

However, the name of this parameter could be anything. The

following code is same as code above.

Srikanth Technologies

Getting Started With Java

34

01: public class CLA {

02: public static void main(String a[]){

03: for (String s : a)

04: System.out.println(s);

05: }

06: }

**Program - Prime.java**

This program checks whether the number given on the command

line is a prime number or not. Prime number is a number which has

no factors other than 1 and itself.

01: // program to check whether a number is prime

02: public class Prime {

03: public static void main(String[] args){

04: // check whether number is passed

05: if (args.length == 0) {

06: System.out.println("Number is missing!");

07: return;

08: }

09: // convert args[0] to int

10: int n = Integer.parseInt( args[0] );

11: boolean prime = true;

12:

13: for ( int i = 2; i <= n/2; i ++) {

14: if ( n % i == 0 ) {

15: prime = false;

16: break;

17: }

18: } // end of for

19: if (prime)

20: System.out.println("Prime Number");

21: else

22: System.out.println("Not a prime number");

23: } // end of main

24: }

Srikanth Technologies

Getting Started With Java

35

Prime program does the following:

1\. It checks whether command line argument is given. If not it

terminates **main**() by using return statement.

2\. Converts first command line argument to an int.

3\. Sets a loop that runs from 2 to n/2.

4\. If a number in the range 2 to n/2 can divide the number

without any remainder then it breaks the loop after setting

prime variable to false.

5\. If no number in the range 2 to n/2 can divide number without

any reminder then loop terminates but prime variable’s value

remains true.

6\. At the end it displays a message based on the value of prime

variable.

Run this program with a number on command line as shown below:

C:\jdk\srikanth>Java Prime 23 <enter>

Prime Number

Srikanth Technologies

Getting Started With Java

36

## EXERCISES

Try to write programs to accomplish the following tasks.

1\. Display first 10 Fibonacci numbers.

2\. Display all palindrome numbers in the range 1000 to 2000.

3\. Write a program to take a number from user and display whether

it is a perfect number.

4\. Accept ten numbers from user and display the largest of the

given numbers.

5\. Accept two numbers and display the GCD of the numbers.

6\. Accept two numbers on command line and raise base (first

number) to power (second number).

7\. Accept a number and display its highest factor.

8\. Accept a number and display the digits in reverse order.

9\. Create a function that takes a set of integers using varying

length argument and returns the average of all the numbers.

10.Create an array of 10 elements. Read values from keyboard and

fill the array. Interchange first 5 elements with last 5 elements

and display the array.

**Note**: Find answers for these exercises at

http://www.srikanthtechnologies.com/books/javabook2016/answers

.html

Srikanth Technologies

Object-Oriented

Programming

Part – I

Java Student’s Guide - Object-Oriented Programming

2

**WHAT WILL YOU LEARN IN THIS MODULE?**

At the end of this module you will have learnt the following:

 **What is object-oriented programming?**

 **Encapsulation, inheritance and polymorphism**

 **Creating a class**

 **Constructors**

 **Overloading of methods**

 **Object references**

 **Array of objects**

 **this reference**

 **static variables and methods**

 **final variables**

 **Inheritance**

 **Overriding methods**

 **Overriding vs. Overloading**

 **“Has A” relationship**

 **Downcasting and upcasting**

 **instanceof operator**

 **Multiple and multi-level inheritance**

 **Runtime polymorphism**

 **Abstract methods and classes**

 **Final methods and classes**

 **Initialization blocks**

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

3

## OBJECT ORIENTED PROGRAMMING

 Java is an object-oriented programming language. So it is

important to understand what object-oriented programming is.

 OOP allows program to be divided into objects, where each

object contains data and code to process data.

 These objects of the program map to real-world objects like an

account in bank, student in college etc.

Three basic principles of OOP are:

 **Encapsulation**

 **Inheritance**

 **Polymorphism**

## ENCAPSULATION

 Binds or encapsulates data and code that processes data.

 Protects instance variables (data) by not allowing them to be

accessed from outside the object.

 Provides a set of functions (methods) that are accessed from

other objects.

 Increases control as each object is independent with its data,

which is private, and a set of functions, which can be called from

other objects.

 A class in Java defines data and code that is to be encapsulated.

**Employee**

**From Outside**

**EmpName**

**Salary**

**Data**

**changeSalary()**

**Code**

**From Outside**

**netSalary()**

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

4

In the above example the class **Employee** has two instance

variables – EmpName and Salary and two methods –

changeSalary() and netSalary().

Instance variables can be accessed only by methods that are part of

the class – changeSalary() and netSalary().

**Class vs. Object**

Class is the description of a collection of similar objects. Class

defines the instance variables and methods to be encapsulated.

Class denotes a category of objects. It is blueprint for creating

objects. Example: Employee, Product, Student etc.

**Instance** **variables** are used to store data and **methods** perform

operations on the data.

**Object** is an instance of the class. Memory is allocated only when

an object of the class is created. Methods are called using an object.

Example: An employee, a student etc.

## INHERITANCE

 Allows a class to be created from another class thereby inheriting

all members of another class.

 Allows reusability of existing classes.

 New classes may add new members and override existing

members of the inherited class.

 Class being inherited is called as superclass and the class created

from existing class is called as subclass.

 Inheritance represents “IS A” relationship between classes. For

example, Manager is extending Employee because Manager is an

Employee. A SavingsAccount extends Account because

SavingsAccount is an Account.

 Hierarchies can be built using inheritance.

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

5

**Employee**

**Name**

**Salary**

**changeSalary()**

**getSalary()**

**Manager**

**hra**

**changeHra()**

**getSalary()**

In the above example, **Manager** class inherits all the data members

and methods of **Employee** class. It adds **hra** and **changeHra**()

members and overrides **getSalary**() method.

**Overriding** is the process where the subclass (Manager) is creating

a method with the same signature as a method in the superclass

(Employee).

Java allows a class to extend only one class – **single** **inheritance**.

**Multiple inheritance**, where a class can be created from multiple

classes, is NOT permitted in Java.

## POLYMORPHISM

 Allows multiple methods performing the same operation to have

the same name.

 Compiler invokes one of the multiple methods depending upon

the context (parameters passed to method).

 Programmer need not remember multiple names.

In the following example, all three functions returning maximum of

two values are given same name.

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

6

max(int ,int)

max(long, long)

max(String,String)

Depending upon which data type is passed as the parameter to **max**

function, one of the three functions is invoked by the compiler.

Polymorphism may be implemented either at compile-time (method

overloading) or at run-time (dynamic method dispatch).

## CREATING A CLASS

A class is like user-defined data type. A class describes data to be

stored and processed. The following is the syntax used to create a

class.

access class classname

{

[access] instance-variable-declaration;

[[access instance-variable-declaration] ] . . .

[access] returntype methodname ( [parameterlist])

{

// body of the method

}

.

.

}

Access may be *private*, *public*, *protected* or *default* (no access) for instance variables and methods.

**NOTE**: Generally class names are created using **Pascal** **case**

**naming** **convention** - first letter of each word in uppercase and

remaining in lowercase. Method names are created using **Camel**

**case** **naming** **convention** – first word in lowercase and first letter of remaining words in uppercase and remaining letters in lowercase.

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

7

The following is the UML (Unified Modeling Language) diagram to

represent *Employee* class. Minus (-) sign denotes **private** access

and plus (+) sign denotes **public** access.

Employee

- name : String

- salary : int

+ init(name:string, sal:int): void

+ setSalary (sal:int): void

+ getSalary(): int

+ print(): void

**NOTE**: Name of .java file and public class name must be same.

A single .java file can have multiple classes (but only one of them

can be public). When you compile .java file, each class in the file will

have a corresponding .class file.

**Employee.java**

This file contains definition for class Employee.

01: public class Employee {

02: private String name;

03: private int salary;

04: public void init(String n, int sal) {

05: name = n;

06: salary = sal;

07: }

08: public void print() {

09: System.out.println(name);

10: System.out.println(salary);

11: }

12: public void setSalary(int sal) {

13: salary = sal;

14: }

15: public int getSalary() {

16: return salary;

17: }

18: }

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

8

**TestEmployee.java**

This file contains definition for class TestEmployee. Function main()

in TestEmployee does the following:

 Creates an object reference of **Employee** class.

 Creates an object of Employee class.

 Calls methods of Employee class using object reference.

01: public class TestEmployee {

02: public static void main(String[] args) {

03: Employee e; // object reference

04: e = new Employee(); // create an object of Employee

05:

06: e.init("Jonathan", 35000);

07: e.print();

08: e.setSalary(55000);

09:

10: if ( e.getSalary() > 50000 )

11: System.out.println("Fat salary");

12: }

13: }

If you compile **Employee**. **java**, **TestEmployee**. **java** and run

TestEmployee ( *Java TestEmployee*), it generates the following

output:

**c:\jdk\srikanth>Java TestEmployee**

Jonathan

35000

Fat salary

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

9

## CONSTRUCTOR

 A method in the class with the same name as the class name.

 Invoked automatically whenever an object of the class is created.

 Used to initialize instance variables of the class.

 Doesn’t contain any return type – not even void.

01: public class Number {

02: private int num;

03: // constructor

04: public Number() {

05: num = 1;

06: }

07: }

In the above, **Number** class has a constructor that is used to

initialize instance variable *num*. When an object of **Number** class is

created, Java automatically calls the constructor.

Number n = new Number(); // calls constructor

Constructor can take parameters and use those parameters for

initializing instance variables.

01: public class Number {

02: private int num;

03: // constructor

04: public Number(int n){

05: num = n; }

06: }

The above constructor is called whenever an object is created.

Number n = new Number(10);

**NOTE**: If no constructor is explicitly created then Java creates a

constructor with no parameters (**default** **constructor**). But Java

doesn’t provide this constructor once a user-defined constructor is

created in the class.

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

10

The following is **Employee** class with constructor instead of **init**()

method :

01: class Employee {

02: private String name;

03: private int salary;

04: public Employee (String n, int sal) {

05: name = n;

06: salary = sal;

07: }

08: // remaining code

09: }

01: class UseEmployee {

02: public static void main(String[] args) {

03: Employee e = new Employee ("Jonathan", 25000);

04: }

05: }

## OVERLOADING METHODS

 It is possible to define two or more methods with the same name

within the same class provided the parameters of the methods

are different.

 Overloading methods is one way of implementing polymorphism.

 Methods can be overloaded based on type/number of

parameters.

 Methods cannot be overloaded based on return type.

The following example demonstrates overloading methods in a class.

01: class Test {

02: void m1(int n) { }

03: void m1(String s) { }

04: void m1(String s, int n) { }

05: void m1(int n, String s) { }

06: // Not allowed as methods differ only by return type

07: int m2(int n) {}

08: long m2(int n) {}

09: }

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

11

**Overloading Constructors**

Just like how it is possible to overload methods of a class, it is also

possible to overload constructors of the class.

01: public class Number {

02: int num;

03: public Number(){

04: num = 1;

05: }

06: public Number(int n){

07: num = n;

08: }

09: }

First constructor is called when an object is created without passing

any parameter and second constructor is called when an object is

created by passing a single **int** as parameter.

Number n1 = new Number(); // calls constructor Number()

Number n2 = new Number(100); // calls Number(int)

**NOTE:** It is NOT possible to create an object unless Java can invoke

one of the constructors.

01: class A {

02: int n;

03: public A(int num){

04: n = num;

05: }

06: public A(String s) {

07: n = Integer.parseInt(s);

08: }

09: }

Third line doesn’t compile as Java cannot call any constructor.

A obj1 = new A(10);

A obj2 = new A("99");

A obj2 = new A(); // not possible

Srikanth Technologies

![](index-53_1.jpg)

Java Student’s Guide - Object-Oriented Programming

12

In order to create an object without passing any parameter at the

time of creation, the class must have a constructor that takes no

parameter or it must have default constructor.

## OBJECT REFERENCE

Object reference is a variable that references an object. An object

in Java is accessed using object reference.

01: Employee e1; // create object reference of Employee class

02: // create an object and make e1 referencing it

03: e1 = new Employee ("Larry",10000);

04: //create object reference and object

05: Employee e1 = new Employee("Larry",10000);

06: Employee e2 = new Employee("Steve",15000);

**Comparing object references**

If two object references of the same class are compared, only

references are compared but NOT contents of the objects.

Employee e1 = new Employee("Jason",25000);

Employee e2 = new Employee("Jason",25000);

if (e1 == e2) // only references are compared, NOT objects

System.out.println("Equal");

**NOTE:** If you compare two object references, only the references

are compared and not the contents of the object that they point to.

**NOTE**: Only == and != relational operators are allowed with object

references.

Srikanth Technologies

![](index-54_1.jpg)

Java Student’s Guide - Object-Oriented Programming

13

**Assignment between two object references**

It is possible to assign one object reference to another. But, what

we effectively copy is not the contents of an object to another and

instead one object reference to another.

The following example and picture demonstrate what happens when

an object reference is copied to another.

Employee e1,e2;

e1 = new Employee("Larry",10000);

e2 = new Employee("Steve",15000);

e1 = e2; // e1 and e2 point to same object

## ARRAY OF OBJECTS

 Java supports array of objects of a class.

 When an array of objects is created only object references that

can point to objects of class are created.

 The default value of each element is null and object reference

must be made to point to an object explicitly before it is used.

Employee [] e;

//Create an array of 5 Employee object references

e = new Employee[5];

e[0] = new Employee("Gavin",10000);

e[1] = new Employee("King",15000);

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

14

**0**

**Employee Object**

**1**

**Employee Object**

**2**

**null**

**3**

**null**

**null**

**4**

## THIS REFERENCE

 Keyword ***this*** references invoking object.

 Used by methods to implicitly access members of the calling

object.

 Used to access instance variables when parameters and instance

variables have same names.

 The **this** reference is made available to each non-static method

automatically.

 Used to call a constructor from another constructor.

The following constructor uses this reference to access instance

variables as parameters and instance variables have same names.

**NOTE**: When instance variables and parameters are having the

same name, parameters of the method take precedence over

instance variables. In general local variables always take precedence

over non-local variables.

01: class Employee{

02: private String name;

03: private int salary;

04: public Employee(String name, int salary) {

05: this.name = name;

06: this.salary = salary;

07: }

08: }

Srikanth Technologies

![](index-56_1.jpg)

Java Student’s Guide - Object-Oriented Programming

15

## STATIC VARIABLES

 A static variable, otherwise known as class variable, is a variable

that is associated with class and not an object.

 Defined using keyword **static.**

 Exist only for once for the entire class.

 Static variables that are declared as **final** are used as constants.

**1001 ABC 40000**

**1002 XYZ 50000**

**Objects of Account**

**1003 PQR 43000**

**5000**

**static variable - minbal**

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

16

## STATIC METHODS

 Static methods are same as normal methods except that they

can be invoked with class name and need not be invoked by any

object.

 Defined using keyword **static**.

 Do not have **this** reference.

 Static methods cannot invoke non-static methods and cannot

access instance variables as they do not have access to any

specific object (this reference) – refer to code below.

 Generally used to access and manipulate static variables.

01: public class StaticTest {

02: private int iv;

03: private static int sv;

04: public static void main(String[] args) {

05: iv = 10; // not valid

06: StaticTest obj = new StaticTest();

07: obj.iv = 10; // valid as we use object to access iv

08: }

09: }

**Why main() is a static method?**

Function **main**() must be declared as static as it is called using class

name by JVM. For example, when you invoke

Java Hello

It will be converted to a call to main as follows:

Hello.main(parameter)

Other examples for static members are **Integer**. **parseInt**(),

**Math**. **abs**() and **System**. **out**.

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

17

**NOTE**: Java does not allow any function to be defined outside the

class. Methods that can be used without creating an object are

declared static, so that they can be called using class name. This

also saves the time to create and release an object.

## FINAL VARIABLE

 Java allows variables to be declared as final using final keyword.

 Final variables cannot change value once they are assigned a

value.

 Final variables are generally static variables as it generally

makes no sense to have the same value for a variable in each

object of the class.

 Final variables must be assigned a value before constructor of

the object is completed.

class Account {

public static final int MINBAL = 500;

}

Variable MINBAL is accessed using class name from outside the

class as it is static and public variable. Minbal cannot be changed as

it is final and initialized to 500.

System.out.println(Account.MINBAL);

**Employee**

- name : String

-salary: double

- hraper: float

+Employee(name:String, salary:double)

+ setSalary(salary:double):void

+ getSalary():double

+ setHraper(value:double):void

Srikanth Technologies

![](index-59_1.jpg)

Java Student’s Guide - Object-Oriented Programming

18

In the above UML diagram, static members – **hraper** variable and

**setHraper**() method are ***underlined*** to indicate that they are static members of the class.

The following code shows how to implement Employee class with

static variables – **hraper** and static method **setHraper**().

01: public class Employee {

02: private String name;

03: private double salary;

04: private static double hraper = 20;

05: public Employee(String name,double salary) {

06: this.name = name;

07: this.salary = salary;

08: }

09: public void setSalary(double salary) {

10: this.salary = salary;

11: }

12: public double getSalary() {

13: return salary + salary * hraper / 100;

14: }

15: public static void setHraper (double hra) {

16: hraper = hra;

17: }

18: }

01: public class UseEmployee {

02: public static void main(String[] args) {

03: Employee e = new Employee("Jason", 30000);

04: System.out.println ( e.getSalary());

05: Employee.setHraper(25);

06: System.out.println ( e.getSalary());

07: }

08: }

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

19

## INHERITANCE

 Allows a new class to be created from an existing class.

 Keyword extends is used to create a new class that extends an

existing class.

 Existing class is called as superclass and new class is called as

subclass.

 Inheritance represents Is A relationship. For example, Student is

a Person, Car is a Vehicle etc.

**Person**

**name : string**

**email : string**

**Student**

**Faculty**

**course : string**

**subjects : string**

The following code demonstrates creating **Person** class and **Faculty**

classes.

01: class Person {

02: protected String name,email;

03: public Person( String name, String email) {

04: this.name = name;

05: this.email = email;

06: }

07: public void print() {

08: System.out.println(name);

09: System.out.println(email);

10: }

11: public void setEmail(String email) {

12: this.email = email;

13: }

14: }

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

20

**Note**: Access **protected** allows the members to be accessed from

subclasses also.

01: class Faculty **extends** Person {

02: protected String subjects;

03: public Faculty(String name, String email, String subjects){

04: **super**(name,email); // must be first statement

05: this.subjects = subjects;

06: }

07: **@Override**

08: public void print() { // overrides print() of Person

09: **super**.print();

10: System.out.println(subjects);

11: }

12: public void setSubjects(String subjects) {

13: this.subjects = subjects;

14: }

15: }

**Person**

**# name : string**

**# email : string**

**+ Person(name,email)**

**+ print() : void**

**+ setEmail(email:string):void**

**Faculty**

**# subjects : string**

**+Faculty (name,email,subjects)**

**+ print():void**

**+ setSubjects(subjects:string):void**

**Note**: Symbol # in UML diagram specifies protected access

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

21

01: class TestPerson {

02: public static void main(String args[]) {

03: Faculty f = new Faculty("Srikanth",

04: "srikanthpragada@yahoo.com","Java,.Net");

05: f.print();

06: f.setEmail("srikanthpragada@gmail.com");

07: f.setSubjects("Java,.Net,Oracle,Android");

08: }

09: }

**Constructors in Inheritance**

When an object of subclass is created then Java automatically calls

default constructor of the super class from the constructor of

subclass.

But, when there is no default constructor in superclass, we must

explicitly call the constructor of superclass using **super** keyword and

required parameters (as we did in **Faculty** class).

**@Override Annotation**

Annotation **Override** indicates that a method declaration in subclass

is intended to override a method declaration in a superclass.

If a method annotated with this annotation does not override a

superclass method, compiler generates an error message.

**Overriding Methods**

When a method in the subclass has the same name and signature of

a method in superclass, the method in subclass is said to be

overriding the method in superclass.

Method **print**() of **Person** class is overridden in subclass **Faculty**.

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

22

**Rules related to overriding**:

 The arguments list must match exactly. Otherwise it becomes

overloading.

 Return type must be same as, or a subclass of, the return type of

original method.

 Access level CANNOT be more restrictive than the original. For

example, if superclass method is public, then subclass method

cannot be protected.

 A final method cannot be overridden.

 Static method cannot be overridden.

 Only inherited methods can be overridden. Private methods of

superclass cannot be overridden as they are not inherited.

**OVERLOADING VS. OVERRIDING**

When you create a method in subclass with the same name as a

method in super class but with different set of parameters, it is

called as overloading and not overriding.

The following example shows the difference between overriding and

overloading.

01: class C1{

02: public void m1(String msg) {

03: }

04: public void m2(int n) {

05: }

06: }

07:

08: class C2 extends C1 {

09: // overloads m1() in class C1

10:

11: public void m1() {

12: }

13:

14: // overrides m2() in class C1

15: public void m2(int n) {

16: }

17: }

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

23

**Using super keyword to access superclass version**

The super keyword in subclass is used to access superclass. Super

keyword can be used to:

 Access a method of superclass that is overridden by a member in

the subclass.

 Invoke the constructor of super class from the constructor of

subclass.

 The super keyword can refer only to the immediate super class in

the hierarchy.

**NOTE**: While calling the constructor of the superclass from

subclass’s constructor, the call *must be the first statement* in the

constructor of the subclass.

**“HAS A” RELATIONSHIP**

When a class contains a variable that refers to another class, the

class is said to have “Has A” relationship with the other class.

In the following example, **Customer** class has “has a” relationship

with **Address** class as it has a variable of class **Address**.

class Address {

// instance variables & methods

}

class Customer {

private **Address** **homeaddress**;

// other variables and methods

}

Srikanth Technologies

![](index-65_1.jpg)

Java Student’s Guide - Object-Oriented Programming

24

## DOWNCASTING AND UPCASTING

Java allows an object reference of superclass to refer to an object of

subclass. This is the heart of runtime-polymorphism in Java.

Superclass is more general form of subclass. Subclass is more

specific form of superclass. Person is more general form of Student.

In other words, a Student is always a Person. So wherever Java

expects Person, a Student can be used.

**NOTE**: Remember superclass and subclass share IS A relationship.

A Student is always a Person.

**Upcasting** is casting an object to a class higher in the inheritance

tree. When an object of **Faculty** is assigned to **Person**, it is called

as upcasting. Upcasting is implicit in Java.

Faculty f = new Faculty("Hunter","hunter@servlets.com",

"servlets,jsp");

Person p = f; // upcasting is done implicitly

Person p = (Person) f; // explicit casting but NOT required

Downcasting is casting an object to a class down in the ***hierarchy***

***tree***. When an object of Person is cast to Faculty, it is called as

**downcasting**.

Downcasting must be done explicitly using type casting syntax as

follows:

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

25

Person p = new Faculty("Hunter","hunter@servlets.com","Java"); Faculty f = p; // doesn’t compile

Faculty f = (Faculty) p; // downcasting explicitly

**NOTE**: Downcasting is explicit and upcasting is implicit.

Downcasting is possible between a superclass and subclass only. For

example, it is not possible to convert a String object to Person

object as String and Person classes are not related.

**instanceof operator**

Operator instanceof is used to check whether an object reference

refers to an object of specified class or one of its subclasses.

object-reference **instanceof** class

Person p = new Faculty ("abc","abc@gmail.com","java");

System.out.println( p instanceof Faculty);

System.out.println( p instanceof Person);

System.out.println( p instanceof Student);

## MULTI-LEVEL INHERITANCE

Java supports multi-level inheritance. In this, a class is extended by

another class, which is again extended by another class. The

following picture shows multi-level inheritance.

**Employee**

**RegularEmployee**

**Consultant**

**OverseasEmployee**

Srikanth Technologies

![](index-67_1.jpg)

Java Student’s Guide - Object-Oriented Programming

26

In the above example, **Employee** class is inherited into

**RegularEmployee** class, which in turn is inherited into

**OverseasEmployee**.

Constructors of classes in inheritance must be called in the order of

inheritance.

When you create an object of **OverseasEmployee**, constructor of

**Employee** class is called first then constructor of

**RegularEmployee** and then finally constructor of

**OverseasEmployee**.

Java tries to call constructor of superclass from subclass’s

constructor using **super**() statement. However, if that is not

adequate, you must explicitly call constructor of superclass using

super keyword by passing required parameters.

## MULTIPLE INHERITANCE

Java does NOT support multiple inheritance, where a single class

extends two or more classes. It means, Java doesn’t allow two or

more classes to be inherited into a single class.

In the following diagram, **AllRounder** is extending **Batsman** and

**Bowler**, which is not supported by Java.

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

27

The reason for Java to avoid multiple inheritance is the ambiguity

caused by multiple inheritance. For example, **AllRounder** has two

instances of **name** variable as one comes from **Batsman** and

another comes from **Bowler**. This leads to *ambiguity*.

## RUNTIME POLYMORPHISM - DYNAMIC METHOD

### **DISPATCH**

 Is the process by which a call to an overridden method is

resolved at runtime instead of compile-time.

 It is based on the concept that an object reference of the super

class can refer to an object of any subclass in the hierarchy.

 Runtime polymorphism occurs when an overridden method is

called using an object reference of superclass.

 Java decides which method to call (superclass or subclass) based

on the object pointed by object reference of superclass.

 Also called as late binding.

class Person {

public void print() {

. . .

}

}

class Faculty extends Person {

@Override

public void print() {

. . .

}

}

The following code shows how Java calls appropriate method

depending on the object pointed by object reference.

Person objref;

objref = new Person(...);

**objref**. **print**();

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

28

// object ref. of super class points to object of subclass

objref = new Faculty(...);

/* call to print() method calls print() of subclass as objref

points to object of subclass. */

**objref**. **print**(); // calls print of subclass

**Note:** Dynamic method dispatch is applied only to method that is

defined in superclass, overridden in subclass and invoked using an

object reference of superclass.

## ABSTRACT METHOD

 Keyword abstract is used to create abstract methods.

 Abstract method doesn’t contain body.

 Must be overridden in subclass. Otherwise subclass must be

declared abstract.

 If there is any abstract method in the class then class must be

declared as abstract.

 Mutually exclusive with final method – a method cannot be

declared as final and abstract.

## ABSTRACT CLASS

When a class contains one or more abstract methods, it must be

defined as abstract class using keyword abstract.

 Defined using abstract keyword.

 Cannot instantiate (create) objects of abstract class.

 However, an object reference of abstract class can be declared.

 Generally contains one or more abstract methods.

 A class can be declared as abstract even though it doesn’t

contain any abstract methods.

 Can contain other non-abstract members such as methods and

instance variables.

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

29

**FINAL VARIABLE, METHOD, CLASS AND PARAMETER**

 Keyword final is used to declare final variables, methods and

classes.

 A final variable is a variable whose value cannot be changed once

the variable is assigned a value.

 Final method is a method that cannot be overridden in the

subclass.

 Final class cannot be extended (inherited). There is no subclass

for final class.

 You can declare parameters as **final** to ensure that the value of

the parameter doesn’t change during the execution of the

method.

public void fun (int x, **final** int y) { }

The following example demonstrates how to use abstract method,

abstract class, final method and runtime polymorphism.

01: abstract class Employee {

02: protected String name, desg;

03: public Employee(String name, String desg) {

04: this.name = name;

05: this.desg = desg;

06: }

07: final public String getDesg() {

08: return desg;

09: }

10: final public void setDesg(String desg) {

11: this.desg = desg;

12: }

13: final public String getName() {

14: return name;

15: }

16: public abstract int getPay();

17: }

18: class RegularEmployee extends Employee {

19: protected int salary;

20: public RegularEmployee(String name,String desg,int salary){

21: super(name,desg);

22: this.salary = salary;

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

30

23: }

24: @Override

25: public int getPay() {

26: return salary;

27: }

28: }

29:

30: class Consultant extends Employee {

31: protected int nohours, hourrate;

32: public Consultant(String name,String desg,

33: int nohours,int hourrate){

34: super(name,desg);

35: this.nohours = nohours;

36: this.hourrate = hourrate;

37: }

38: @Override

39: public int getPay() {

40: return nohours * hourrate;

41: }

42: }

43:

44: public class UseEmployee{

45: public static void main(String[] args) {

46: Employee employees []=

47: { new RegularEmployee("Steve", "Programmer", 25000),

48: new Consultant("Kevin", "DBA",10,500),

49: new RegularEmployee("Tom", "System Analyst", 45000)

50: };

51: for ( Employee e : employees)

52: System.out.printf("%s : %d\n",e.getName(),e.getPay());

53: }

54: }

The output of *Java* *UseEmployee*, will be:

Steve : 25000

Kevin : 5000

Tom : 45000

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

31

## INITIALIZATION BLOCKS

 Object initialization block is executed when object is created.

 Static initialization block is executed when class is loaded.

 Initialization block is run after super-constructor has run.

 Blocks are run in the order in which they appear in the class.

 Initialization block cannot have parameter and cannot return any

value.

 Object initialization blocks are executed irrespective of which

constructor is executed. So they can be used to contain code that

all constructors need to share.

01: class A {

02: // Object initialization block

03: {

04: System.out.println("Init Block In A");

05: }

06: public A() {

07: System.out.println("Constructor of A");

08: }

09:

10: // Static initialization block

11: static {

12: System.out.println("Static Initialization Block Of A");

13: }

14: }

15:

16: class B extends A

17: {

18: public B() {

19: System.out.println("Constructor of B");

20: }

21: public B(String message){

22: System.out.println("Constructor with message : "

23: + message);

24: }

25: // Object initialization block

26: {

27: System.out.println("First Init Block In B");

28: }

29:

Srikanth Technologies

Java Student’s Guide - Object-Oriented Programming

32

30: {

31: System.out.println("Second Init Block In B");

32: }

33:

34: static {

35: System.out.println("Static Initialization Block Of B");

36: }

37:

38: }

39: public class InitBlockDemo {

40: public static void main(String[] args) {

41: B obj = new B();

42: System.out.println("============================");

43: B obj2 = new B("Second Object");

44: }

45: }

When you run the above program you will get the following output:

Static Initialization Block Of A

Static Initialization Block Of B

Init Block In A

Constructor of A

First Init Block In B

Second Init Block In B

Constructor of B

============================

Init Block In A

Constructor of A

First Init Block In B

Second Init Block In B

Constructor with message : Second Object

Srikanth Technologies

Java Library

Part – I

Java Student’s Guide – Library-I

2

**WHAT WILL YOU LEARN IN THIS MODULE?**

At the end of this module you will have learnt the following:

 **Object class**

 **String class**

 **StringBuffer class**

 **StringJoiner class**

 **Math class**

 **Arrays class**

 **Calendar class**

 **Date class**

 **DateFormat and NumberFormat classes**

 **SimpleDateFormat class**

 **New Date API**

 **Standard datatypes vs. objects**

 **Wrapper classes**

 **Autoboxing and autounboxing**

Srikanth Technologies

Java Student’s Guide – Library-I

3

**Object class**

 Object class is one of the standard classes in Java API.

 All other classes in Java are subclasses of **Object** class.

 A class declaration without **extends** clause, implicitly extends

**Object** class.

 So a reference to **Object** class can refer to an object of any class

in Java.

**Method**

**Meaning**

Object clone()

Creates a new object that is same as the

object being cloned. Default implementation

does shallow copying – only primitive value

and references are copied. Override this

method to provide *deep* *copying*.

boolean

Compares the contents of two objects and

equals(Object)

returns true if contents are same. Default

implementation compares only references

and not contents. Override this method to

provide value based comparison.

void finalize()

Called before an unused object is released by

garbage collector. Default implementation

does nothing.

int hashCode()

Returns the hash code associated with the

invoking object. Hash code is used when

object is used with hashing - HashSet. When

two objects are equal then hash codes for

those two objects must also be equal.

String toString()

Returns a string that describes the object.

Default implementation returns

classname@ hashcode-in-hex.

final class getClass() Returns an object of type **Class** related to

object.

**Note**: If two objects are equal according to the **equals** (Object)

method, then calling the **hashCode**() method on each of the two

objects must produce the same integer result.

Srikanth Technologies

Java Student’s Guide – Library-I

4

The following **final** methods of Object class are related to

multithreading.

final void notify()

Resumes execution of the thread that is

waiting to be notified.

final void notifyAll()

Resumes execution of all threads that are

waiting to be notified.

final void wait()

Causes the current thread to wait until the

object notifies the thread.

The following program shows default implementation of methods in

**Object** class.

01: class Time{

02: private int hours, mins, secs;

03: public Time(int hours, int mins, int secs) {

04: this.hours = hours;

05: this.mins = mins;

06: this.secs = secs;

07: }

08: }

09: public class TestTime {

10: public static void main(String[] args) {

11: Time t1 = new Time(10,20,30);

12: Time t2 = new Time(10,20,30);

13:

14: System.out.println(t1.toString());

15: System.out.println(t2.equals(t1));

16:

17: }

18: }

The above program generates the following output:

Time@19821f

false

Srikanth Technologies

Java Student’s Guide – Library-I

5

In the following example, we override **equals**(), **hashCode**(), and

**toString**() methods.

01: // class to override methods in Object class

02: class Time {

03: private int hours, mins, secs;

04: public Time(int hours, int mins, int secs) {

05: this.hours = hours;

06: this.mins = mins;

07: this.secs = secs;

08: }

09: public int getTotalSeconds() {

10: return hours * 60 * 60 + mins * 60 + secs;

11: }

12: @Override

13: public int hashCode() {

14: return hours;

15: }

16: @Override

17: public boolean equals(Object obj) {

18: if (obj instanceof Time) {

19: Time t = (Time) obj;

20: return t.getTotalSeconds() == this.getTotalSeconds();

21: }

22: else

23: return false;

24: }

25: @Override

26: public String toString() {

27: return String.format("%02d:%02d:%02d",hours, mins, secs);

28: }

29: }

30: public class TestTime {

31: public static void main(String[] args) {

32: Time t1 = new Time(10, 20, 30);

33: Time t2 = new Time(10, 20, 30);

34: Time t3 = new Time(15, 15, 15);

35:

36: System.out.println(t1.toString());

37: System.out.println(t1.equals(t2));

38: System.out.println(t1.equals(t3));

39: }

40: }

Srikanth Technologies

Java Student’s Guide – Library-I

6

Output generated by the above program is as follows:

10:20:30

true

false

**String class**

 String is one of the standard classes of Java.

 An object of String class represents a collection of characters

(string).

 Provides methods required to manipulate a string.

**NOTE:** String represented by String class is **immutable**. That

means once we create a string, its value cannot be modified.

String()

String(char[])

String(String)

The following are important methods of **String** class.

**Method**

**Meaning**

char charAt(int)

Returns the character at the given

position.

boolean endsWith(String)

Returns true if string ends with the

given string.

String concat(String)

Appends string to invoking string and

returns concatenated string.

boolean Contains(String)

Returns true if string contains the

given string.

int indexOf(String)

Returns the position of the substring in

the main string or -1 on failure.

int indexOf (String,

Same as above, but starts search at

frompos)

the given position.

int lastIndexOf (String)

Returns position of the substring from

the end of main string.

int lastIndexOf(String,

Same as above, but starts search at

Srikanth Technologies

Java Student’s Guide – Library-I

7

frompos)

the given position.

int length()

Returns the length of the string.

[String](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html) joi[n(String](https://docs.oracle.com/javase/8/docs/api/java/lang/CharSequence.html) delimiter, Returns a string by joining given string

[String...](https://docs.oracle.com/javase/8/docs/api/java/lang/CharSequence.html) elements) with delimiter.

boolean startsWith (String) Returns true if string starts with the

given string.

String substring (int from,

Returns a substring that starts at *from*

int to)

and ends at *to* in main string.

String toLowerCase()

Returns the string after converting it to

lowercase.

String toUpperCase()

Returns the string after converting it to

uppercase.

String trim()

Trims spaces on both sides of string.

String replace

Replaces *old* character in the string

(char old,char new)

with *new* character.

static String valueOf (T v) Converts the given value to string.

String [] split(String

Splits a string into multiple strings

delims)

based on the given delimiter.

The following program demonstrates methods of String class.

01: public class StringDemo {

02: public static void main(String args[]) {

03: String s1 = new String("Java Language");

04: String s2 = "Java EE";

05:

06: // comparing two strings based on values

07: if(s1.equals(s2) )

08: System.out.println("Equal");

09: System.out.println(s2.length()); // 7

10: System.out.println(s1.charAt(0)) ; // J

11: System.out.println(s1.startsWith("Java"));// true

12: System.out.println(s1.endsWith("Java")); // false

13: System.out.println(s1.indexOf("a")); // 1

14: System.out.println(s1.indexOf("a",4)); // 6

15: System.out.println(s1.lastIndexOf("a")); // 10

16: System.out.println(s1.substring(0,4) ) ; // Java

17: System.out.println(s1.toUpperCase() ) ; // JAVA LANGUAGE

18: // original string remains the same

Srikanth Technologies

Java Student’s Guide – Library-I

8

19: System.out.println(s1) ; // Java Language

20: // split the string based on space

21: String words[] = s1.split(" ");

22: System.out.println("\nWords\n");

23: for ( String w : words)

24: System.out.println(w);

25:

26: // join() of Java 8

27: String langs = String.join(",","Java","Scala","Python", 28: "Ruby","C#");

29: System.out.println(langs); // Java,Scala,Python,Ruby,C#

30: }

31: }

**StringBuffer class**

StringBuffer represents a mutable character string thus allowing

string to be modified.

StringBuffer(String)

StringBuffer(int capacity)

StringBuffer()

**Method**

**Meaning**

void setCharAt(index,char)

Changes character at the given

position.

StringBuffer append(String)

Appends string at the end.

StringBuffer append(char)

Appends character at the end.

StringBuffer append(char[])

Appends character array at the

end of buffer.

StringBuffer insert(offset,data)

Inserts the given data at the

given offset in the buffer.

StringBuffer deleteCharAt(index) Removes character at the index.

StringBuffer delete

Removes characters from *start* to

(int start, int end)

*end*.

StringBuffer reverse()

Reverses string buffer.

Srikanth Technologies

Java Student’s Guide – Library-I

9

The following program demonstrates a mutable string with

**StringBuffer**.

01: public class SBDemo {

02: public static void main(String args[]) {

03: StringBuffer sb = new StringBuffer("Java ");

04: sb.append("EE");

05: System.out.println(sb); // Java EE

06: sb.insert(0,"Oracle ");

07: System.out.println(sb); // Oracle Java EE

08: sb.delete(0,6);

09: System.out.println(sb); // Java EE

10: }

11: }

**NOTE:** **StringBuilder** class was introduced in Java 5.0\. It is same

as StringBuffer except that it is NOT synchronized. So StringBuilder

is not thread-safe but could be faster than StringBuffer.

**StringJoiner class**

StringJoiner is used to construct a sequence of strings separated by

a delimiter and optionally prefix and suffix.

StringJoiner(String delimiter)

StringJoiner(String deliter, String prefix, String suffix)

**Method**

**Meaning**

StringJoiner add

Adds a copy of the given CharSequence

(CharSequence value) value as the next element of the

StringJoiner value.

StringJoiner merge

Adds the contents of the given StringJoiner

(StringJoiner other)

without prefix and suffix as the next

element.

StringJoiner

Sets the value to be used when no

setEmptyValue

elements have been added yet, that is,

(CharSequence value) when it is empty.

Srikanth Technologies

Java Student’s Guide – Library-I

10

StringJoiner sj = new StringJoiner(",","[","]");

sj.add("Java");

sj.add("C#");

sj.add("Python");

System. ***out***.println(sj.toString()); // [Java,C#,Python]

**Math class**

Math class contains a set of **static** methods to support common

mathematical functions. It is a final class and cannot be extended.

**Static Method**

**Meaning**

T abs(T number)

Returns absolute value.

T min(T n1, T n2)

Returns least of two numbers.

T max(T n1, T n2)

Returns greater of two numbers.

long round(double)

Returns number after rounding it.

double pow(double

Returns base raised to power.

base, double power)

double random()

Returns a random number that is >=0 and

< 1.0.

**NOTE:** In the above methods T indicates the data type used.

01: public class MathDemo {

02: public static void main(String[] args) {

03: System.out.println(Math.abs(-10) );

04: System.out.println(Math.min(10,20));

05: System.out.println(Math.round(10.636));

06: System.out.println(Math.round(Math.random()*100));// 0-99

07: }

08: }

Srikanth Technologies

Java Student’s Guide – Library-I

11

**Arrays class**

**Arrays** class provides static methods to search, sort, fill and

compare arrays. It provides methods that work on array of any

type.

**Method**

**Meaning**

int binarySearch

Searches for value using binary search

(T array[], T v)

algorithm.

boolean equals

Compares whether contents of two

(T array[], T array[])

arrays are equal.

void fill(T array[], T value) Fills all elements of an array with the

given value.

void sort(T array[])

Sorts the given array.

String toString(T array[])

Returns a string that contains all

elements of the array.

T [] copyOf

Makes a copy of an existing array to

(T array[], int newlength)

new array with the specified size and

returns new array.

01: // import Arrays class from java.util package

02: import java.util.Arrays;

03: class ArraysDemo {

04: public static void main(String...args) {

05: long a[] = new long[5];

06: for ( int i = 0 ; i < 5; i ++)

07: a[i] = Math.round (Math.random() * 100 );

08: Arrays.sort(a);

09: for ( long n : a)

10: System.out.println(n);

11:

12: int pos = Arrays.binarySearch(a,30);

13: if ( pos >= 0 )

14: System.out.printf("Found at : %d", pos);

15: else

16: System.out.println("Not found");

17: }

18: }

Srikanth Technologies

Java Student’s Guide – Library-I

12

**Calendar class**

Calendar class provides methods and fields to obtain information

about date and time. Calendar is an abstract class and an example

for its subclass is ***GregorianCalendar***.

Static method ***getInstance***() is used to return an object of

Calendar class that contains system date and time.

**Method**

**Meaning**

int get(what)

Returns the value specified by ***what***.

void add (int what, int value) Adds ***value*** which is specified by

***what*** parameter.

void set (year, month, days,

Sets date and time to given values.

hours, minutes, seconds)

void setTime(Date)

Sets time to given **Date** object.

01: import java.util.*;

02: public class CalendarDemo {

03: public static void main(String [] args) throws Exception {

04: Calendar cal=Calendar.getInstance();//get system date&time

05:

06: cal.add(Calendar.MONTH,10);

07: System.out.printf ("Year :%d Month:%d Day:%d",

08: cal.get(Calendar.YEAR), cal.get(Calendar.MONTH),

09: cal.get(Calendar.DAY_OF_MONTH));

10: }

11: }

01: // Calculate age in years for the given date of birth

02: import java.util.Calendar;

03: import java.util.Scanner;

04:

05: public class AgeCalculation {

06: public static void main(String[] args) {

07: // take dob from user

08: Scanner s = new Scanner(System.in);

09: System.out.print("Enter date of birth [dd-mm-yyyy] :");

10: String dobstring = s.nextLine();

11:

Srikanth Technologies

Java Student’s Guide – Library-I

13

12: String [] parts = dobstring.split("-");

13:

14: Calendar dob = Calendar.getInstance();

15: dob.set( Integer.parseInt( parts[2]),

16: Integer.parseInt( parts[1]),

17: Integer.parseInt( parts[0]) );

18:

19: Calendar cd=Calendar.getInstance(); // get system date

20:

21: long ms = cd.getTimeInMillis()- dob.getTimeInMillis();

22: long days = ms / ( 1000 * 60 * 60 * 24);

23: System.out.printf("Age in years : %d\n",days/365);

24: }

25: }

**Date class**

An instance of Date class represents a single date and time.

Internally date and time is stored as long integer. It is the number

of milliseconds from Jan 1, 1970.

Creating an object of **Date** class fills it with system date and time.

You can get date & time using **getTime**() method, set date and time

using **setTime**() method.

An object of **Date** class is used mainly with **DateFormat** class, as

its **format**() methods expect an object of Date class.

**DateFormat class**

DateFormat is an abstract class used to format dates. You get an

instance of DateFormat class to format either date or time by using

one of the following methods:

DateFormat getDateInstance()

DateFormat getDateInstance(int style)

DateFormat getTimeInstance()

DateFormat getTimeInstance(int style)

Srikanth Technologies

Java Student’s Guide – Library-I

14

Argument **style** could be – DEFAULT, SHORT, MEDIUM, LONG, or

FULL. Method **format**() is used to format the date or time. It takes

an object of **Date** class as parameter.

**NumberFormat Class**

 It is an abstract base class for all number formats.

 Provides the interface for formatting and parsing numbers.

 Supports locale.

static [NumberFormat](http://docs.oracle.com/javase/1.4.2/docs/api/java/text/NumberFormat.html) [getCurrencyInstance()](http://docs.oracle.com/javase/1.4.2/docs/api/java/text/NumberFormat.html#getCurrencyInstance())

static [NumberFormat](http://docs.oracle.com/javase/1.4.2/docs/api/java/text/NumberFormat.html) [getCurrencyInstance(](http://docs.oracle.com/javase/1.4.2/docs/api/java/text/NumberFormat.html#getCurrencyInstance(java.util.Locale))[Locale](http://docs.oracle.com/javase/1.4.2/docs/api/java/util/Locale.html) inLocale) static [NumberFormat](http://docs.oracle.com/javase/1.4.2/docs/api/java/text/NumberFormat.html) [getInstance()](http://docs.oracle.com/javase/1.4.2/docs/api/java/text/NumberFormat.html#getInstance())

static [NumberFormat](http://docs.oracle.com/javase/1.4.2/docs/api/java/text/NumberFormat.html) [getInstance(](http://docs.oracle.com/javase/1.4.2/docs/api/java/text/NumberFormat.html#getInstance(java.util.Locale))[Locale](http://docs.oracle.com/javase/1.4.2/docs/api/java/util/Locale.html) inLocale)

**SimpleDateFormat class**

It is used to format date and time using custom format. It is a

concrete subclass of **DateFormat** class. The following characters

can be used to format date and time. For complete list of format

characters, see Java Documentation.

**Format What it presents**

**Example**

y

Year

1996; 96

## M

### Month in year

July; Jul; 07

## W

### Week in month

2

d

Day in month

10

## H

Hour in day (0-23)

0

h

Hour in am/pm (1-12)

12

m

Minute in hour

30

s

Second in minute

55

01: import java.text.DateFormat;

02: import java.text.SimpleDateFormat;

03: import java.util.Date;

04:

05: public class DateFormatExample {

06: public static void main(String[] args) {

07:

Date d = new Date();

Srikanth Technologies

Java Student’s Guide – Library-I

15

08:

DateFormat df =

09: DateFormat.getTimeInstance(DateFormat.FULL);

10:

System.out.println(df.format(d));

11:

DateFormat tf =

12: DateFormat.getDateInstance(DateFormat.FULL);

13:

System.out.println(tf.format(d));

14:

15:

SimpleDateFormat sdf =

16: new SimpleDateFormat("d-MMM-yy HH:mm:ss");

17:

System.out.println(sdf.format(d));

18: }

19: }

9:28:41 AM IST

Friday, November 18, 2016

18-Nov-16 09:28:41

**New Date and Time API**

 The Date-Time API uses the calendar system defined in [ISO-](http://www.iso.org/iso/home/standards/iso8601.htm)

[8601](http://www.iso.org/iso/home/standards/iso8601.htm) as the default calendar.

 The core classes are LocalDate, LocalTime, LocalDateTime,

ZonedDateTime, and OffsetDateTime.

 Most of the classes in the Date-Time API create objects that

are [immutable.](http://docs.oracle.com/javase/tutorial/essential/concurrency/immutable.html) This makes objects thread safe.

 Packages java.time, java.time.format ,java.time.zone contain

new classes.

**DayOfWeek Enum**

The [DayOfWeek](http://docs.oracle.com/javase/8/docs/api/java/time/DayOfWeek.html) enum consists of seven constants that describe the days of the week: MONDAY through SUNDAY. The integer values of

the DayOfWeek constants range from 1 (Monday) through 7

(Sunday).

Srikanth Technologies

Java Student’s Guide – Library-I

16

**Month Enum**

The [Month](http://docs.oracle.com/javase/8/docs/api/java/time/Month.html) enum includes constants for the twelve months, JANUARY through DECEMBER. The integer value of each constant

corresponds to the ISO range from 1 (January) through 12

(December).

**LocalDate class**

A [LocalDate](http://docs.oracle.com/javase/8/docs/api/java/time/LocalDate.html) represents a year-month-day in the ISO calendar and is useful for representing a date without a time. You might use

a LocalDate to track a significant event, such as a birth date or

wedding date.

LocalDate date = LocalDate.of(1998, Month.OCTOBER, 24);

LocalDate newdate = date.plusDays(100);

System.out.println(newdate);

LocalDate dob=LocalDate.parse("1998-02-28"); //ISO format

System.out.println(dob);

LocalDate dob2=LocalDate.parse("09-10-2002",

DateTimeFormatter.ofPattern("dd-MM-uuuu"));

System.out.println(dob2);

**Method**

**Meaning**

LocalDateTime atTime

Combines this date with a time

(int hour, int minute, int second) to create a LocalDateTime.

String format

Formats this date using the

(DateTimeFormatter formatter)

specified formatter.

int get(TemporalField field)

Gets the value of the specified

field from this date as an int.

int getDayOfMonth()

Gets the day-of-month field.

DayOfWeek getDayOfWeek()

Gets the day-of-week field,

which is an enum DayOfWeek.

int getDayOfYear()

Gets the day-of-year field.

int getMonthValue()

Gets the month-of-year field

from 1 to 12.

int getYear()

Gets the year field.

Srikanth Technologies

Java Student’s Guide – Library-I

17

Boolean isLeapYear()

Checks if the year is a leap year

LocalDate minusDays(long

Returns a copy of this LocalDate

daysToSubtract)

with the specified number of

days subtracted.

LocalDate minusMonths(long

Returns a copy of this LocalDate

monthsToSubtract)

with the specified number of

months subtracted.

LocalDate minusYears(long

Returns a copy of this LocalDate

yearsToSubtract)

with the specified number of

years subtracted.

LocalDate plusDays(long

Returns a copy of this LocalDate

daysToAdd)

with the specified number of

days added.

LocalDate plusMonths(long

Returns a copy of this LocalDate

monthsToAdd)

with the specified number of

months added.

LocalDate plusYears(long

Returns a copy of this LocalDate

yearsToAdd)

with the specified number of

years added.

**Static Method**

**Meaning**

LocalDate now()

Obtains the current date from

the system clock in the default

time-zone.

LocalDate of(int year, int month, Obtains an instance of LocalDate

int dayOfMonth)

from a year, month and day.

LocalDate

Obtains an instance of LocalDate

parse(CharSequence text) from a text string such as 2007-

12-03.

LocalDate

Obtains an instance of LocalDate

parse(CharSequence text, from a text string using a specific

DateTimeFormatter formatter)

formatter.

Srikanth Technologies

Java Student’s Guide – Library-I

18

**LocalTime class**

LocalTime represents a time without a timezone.

LocalTime now = LocalTime.now();

LocalTime singtime =

LocalTime.now(ZoneId.of("Asia/Singapore"));

**Method**

**Meaning**

int getHour()

Gets the hour-of-day field.

int getMinute()

Gets the minute-of-hour field.

int getSecond()

Gets the second-of-minute field.

boolean isAfter

Checks if this time is after the specified

(LocalTime other)

time.

boolean isBefore

Checks if this time is before the

(LocalTime other)

specified time.

LocalTime minusHours

Returns a copy of this LocalTime with

(long hoursToSubtract)

the specified number of hours

subtracted.

LocalTime minusMinutes

Returns a copy of this LocalTime with

(long minutesToSubtract) the specified number of minutes

subtracted.

LocalTime minusSeconds

Returns a copy of this LocalTime with

(long secondsToSubtract) the specified number of seconds

subtracted.

LocalTime plusHours

Returns a copy of this LocalTime with

(long hoursToAdd)

the specified number of hours added.

LocalTime plusMinutes

Returns a copy of this LocalTime with

(long minutesToAdd)

the specified number of minutes added.

LocalTime plusSeconds

Returns a copy of this LocalTime with

(long secondstoAdd)

the specified number of seconds added.

int

toSecondOfDay()

Extracts the time as seconds of day,

from 0 to 24 * 60 * 60 - 1.

Srikanth Technologies

Java Student’s Guide – Library-I

19

**Static Method**

**Meaning**

LocalTime now()

Obtains the current time from the

system clock in the default time-zone.

LocalTime now

Obtains the current time from the

(ZoneId zone)

system clock in the specified time-zone.

LocalTime of

Obtains an instance of LocalTime from

(int hour, int min, int sec) an hour, minute and second.

LocalTime parse

Obtains an instance of LocalTime from a

(CharSequence text)

text string such as 10:15.

LocalTime parse

Obtains an instance of LocalTime from a

(CharSequence text,

text string using a specific formatter.

DateTimeFormatter

formatter)

**LocalDateTime class**

This class handles both date and time, without a time zone. This

class is used to represent date (month-day-year) together with time

(hour-minute-second-nanosecond) and is, in effect, a combination

of LocalDate with LocalTime.

**YearMonth, MonthDay and Year classes**

 YearMonth represents the month of a specific year.

 MonthDay represents the day of a particular month, such as New

Year's Day on January 1.

 Year represents a year.

Srikanth Technologies

Java Student’s Guide – Library-I

20

**Other classes**

 **ZoneId** specifies a time zone identifier and provides rules for

converting between an Instant and a LocalDateTime.

 **ZoneOffset** specifies a time zone offset from Greenwich/UTC

time.

 **ZonedDateTime** handles a date and time with a corresponding

time zone with a time zone offset from Greenwich/UTC.

 **OffsetDateTime** handles a date and time with a corresponding

time zone offset from Greenwich/UTC, without a time zone ID.

 **OffsetTime** handles time with a corresponding time zone offset

from Greenwich/UTC, without a time zone ID.

**ChronoUnit Enum**

 T[he ChronoUnit](http://docs.oracle.com/javase/8/docs/api/java/time/temporal/ChronoUnit.html) enum provides a set of standard units based on date and time, from milliseconds to millenia.

 Available constants are DAYS,HOURS,MICROS,MILLENNIA,

MILLIS,MINUTES,MONTHS,SECONDS,WEEKS,YEAR

**AgeCalculator.java**

01: import java.time.LocalDate;

02: import java.time.Period;

03: import java.time.temporal.ChronoUnit;

04: import java.util.Scanner;

05: public class AgeCalculator {

06: public static void main(String[] args) {

07: System.out.print("Enter DOB [yyyy-mm-dd]:");

08: Scanner s = new Scanner(System.in);

09: String dobstr = s.nextLine();

10: LocalDate dob = LocalDate.parse(dobstr);

11: LocalDate now = LocalDate.now();

12: long years = ChronoUnit.YEARS.between(dob,now);

13: System.out.println(years);

14: Period p = Period.between(dob,now);

15: System.out.printf("%d years,%d months and %d days

16: old!\n",p.getYears(), p.getMonths(), p.getDays());

17: }

18: }

Srikanth Technologies

Java Student’s Guide – Library-I

21

Enter DOB [yyyy-mm-dd]:1998-10-24

18

18 years,0 months and 25 days old!

**DateTimeFormatter Class**

 Provides format for printing and parsing date-time objects.

 The following methods are used to obtain an object of

DateTimeFormatter:

 ofLocalizedDate(format)

 ofLocalizedTime(format)

 ofLocalizedDateTime(format,format)

 ofPattern(customFormat)

01: import java.time.LocalDate;

02: import java.time.format.DateTimeFormatter;

03: import java.time.format.FormatStyle;

04:

05: public class DateTimeFormatterExample {

06: public static void main(String[] args) {

07:

DateTimeFormatter df =

08: DateTimeFormatter.ofLocalizedDate

09: (FormatStyle.FULL);

10:

LocalDate today = LocalDate.now();

11:

System.out.println(today.format(df));

12:

13:

DateTimeFormatter inputFormat =

14: DateTimeFormatter.ofPattern("dd-MM-uuuu");

15:

LocalDate transDate =

16: LocalDate.parse("24-10-1998", inputFormat);

17:

System.out.println(transDate);

18:

19: DateTimeFormatter format =

20: DateTimeFormatter. *ofPattern*("dd-MMM-uuuu H:m:s");

21:

22: System. ***out***.println

23: (LocalDateTime. *now*().format(format));

24: }

25: }

Srikanth Technologies

Java Student’s Guide – Library-I

22

Friday, November 18, 2016

1998-10-24

18-Nov-2016 10:43:35

**Symbol Meaning**

**Presentation Example**

u

year

Year

2004; 04

y

year-of-era

Year

2004; 04

## D

### day-of-year

number

189

M/L

month-of-year

number/text

7; 07; Jul; July;

## J

### d

day-of-month

number

10

Q/q

quarter-of-year

number/text

3; 03; Q3; 3rd

quarter

## W

### week-of-month

number

4

## E

### day-of-week

Text

Tue; Tuesday; T

a

am-pm-of-day

Text

## PM

### h

clock-hour-of-am-pm

number

12

(1-12)

## H

hour-of-day (0-23)

number

0

m

minute-of-hour

number

30

s

second-of-minute

number

55

Srikanth Technologies

Java Student’s Guide – Library-I

23

**STANDARD DATATYPES vs. OBJECTS**

Java treats standard data types (also called as primitive types) and

objects of classes differently.

Standard data types are allocated memory on **stack**. Parameters of

primitive type are always **passed by value.**

**Heap**

**public void f1() {**

**int a = 10,b = 20;**

**Stack**

**f2(a,b);**

**}**

**i = 1**

**public void f2(int x, int y){**

**y = 20**

**f2()**

**int i = 1;**

**x = 0**

**x = 0;**

**b = 20**

**}**

**f1 ()**

**a = 10**

In the above picture, variable **a** and **b** are created on stack when

control enters into **f1().** When function **f2()** is called, **formal**

**parameters** **x** and **y** are created and assigned values from **actual** **parameters** – **a** and **b**.

However, changes to **x** and **y** will not effect **a** and **b** as they occupy different locations in memory.

**NOTE**: Passing parameters of standard data types is always pass-

by-value.

Srikanth Technologies

Java Student’s Guide – Library-I

24

**How objects are handled by Java?**

Objects of classes are allocated memory dynamically on **heap** and

they are released by garbage collector when they are not required.

Object is allocated memory on heap. However, an object reference

is allocated memory on stack. When an òbject is passed to a

function, only reference of the object is passed but not the object

itself.

**public void f1() {**

**Heap**

**Product p;**

**p = new Product(**

**…** **);**

**f2(p);**

**}**

**Stack**

**public void f2(Product pro){**

**Product temp;**

**temp**

**temp = new Product(**

**…** **);**

**f2()**

**pro.changePrice(100);**

**pro**

**}**

**f1()**

**p**

**NOTE**: An object is always passed by reference.

In the figure, object references **p** in **f1()** and **pro** in function **f2()** both refer to the same object. Object reference **temp** points to a

new object.

When control comes out of **f2**(), object pointed by **temp** will be

ready for garbage collection as it is no longer pointed by any object

reference.

Srikanth Technologies

Java Student’s Guide – Library-I

25

**Wrapper Classes**

Primitive types such as int and double are not objects in Java.

Wrapper classes are used to convert primitive types to objects. Java

provides a wrapper class for each primitive type (8 in total).

**NOTE:** Wrapper classes are declared as **final** and their values

cannot be changed.

The following are the wrapper classes provided by Java and their

corresponding primitive (standard) type.

**Standard**

**Wrapper class**

**Method to convert object to**

**Type**

**primitive type**

boolean

Boolean

booleanValue()

byte

Byte

byteValue()

short

Short

shortValue()

int

Integer

intValue()

long

Long

longValue()

float

Float

floatValue()

double

Double

doubleValue()

char

Character

charValue()

**Boxing and unboxing**

The following code shows how to use wrapper class Integer to

convert an int to object (boxing) and back to int (unboxing).

int x =100;

// convert int to an object

Integer iobj = new Integer(x); // boxing

// get int from object

x = iobj.intValue(); // unboxing

Srikanth Technologies

Java Student’s Guide – Library-I

26

**Autoboxing**

When a primitive data type is to be used as an object, it is to be

**boxed** to an object of corresponding **wrapper** class. When the

primitive value is to be taken from wrapper class object then the

value is to be **unboxed** from object by using a method of wrapper

class.

Starting from Java 5.0, Java does **boxing** and **unboxing**

automatically. The following example shows how boxing and

unboxing take place.

01: public static void main(String[] args) {

02: int i=100;

03: Integer iobj = i; // autoboxing

04: System.out.println( iobj.toString());

05: i = iobj; // autounboxing

06: System.out.println(i);

07: }

Srikanth Technologies

Object-Oriented

Programming

Part – II

Java Student’s Guide – Object-Oriented Programming II

2

**WHAT WILL YOU LEARN IN THIS MODULE?**

At the end of this module you will have learnt the following:

 **Creating an Interface**

 **Implementing an interface**

 **Using object references of an interface**

 **An interface extending another**

 **Null interface**

 **Default methods and static methods in interface**

 **Nested classes - static member classes, inner classes**

 **Creating a package and placing class in it**

 **Accessing classes of a package**

 **The import statement**

 **CLASSPATH variable**

 **Access modifiers**

 **Static import**

 **Enumeration**

 **Exception Handling**

 **Handling multiple exceptions**

 **Multi-catch**

 **The finally block**

 **Types of exceptions – checked and unchecked**

 **Defining new exceptions**

 **More precise rethrow**

 **Assertions**

 **How to create new thread by extending Thread class?**

 **How to create new thread by implementing Runnable**

**interface?**

 **Thread life-cycle**

 **Thread class**

 **Synchronization**

 **Thread Pools**

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

3

## INTERFACES

 An interface is a collection of methods that must be implemented

by the implementing class.

 An interface defines a contract regarding what a class must do,

without saying anything about how the class will do it.

 Interface can contain declaration of methods and variables.

 Implementing class must define all the methods declared in the

interface.

 If a class implements an interface and does not implement all the

methods then class itself must be declared as abstract.

 Variables in interface automatically become static and final

variables of the implementing class.

 Members of interface are implicitly public, so need not be

declared as public.

access interface name [ extends interface [,interface] ] {

returntype method( [parameters] );

datatype finalvariable = value;

}

The following example shows how to declare an interface and how a

class implements the interface.

**<< interface>>**

**Stack**

**MyStack**

+ push(String)

+ push(String)

+ pop():String

+ pop():String

+ length(): int

+ length() : int

+ print():void

**NOTE:** In UML, interface resembles a class. One way to differentiate

an interface from a class is to use **<<interface>>** stereotype as

shown above.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

4

**interface** Stack {

void push(String value);

String pop();

int length();

}

Stack is a data structure that stores data in such a way that last

value pushed is first value to be popped (LIFO).

**Implementing an interface**

The following class - **MyStack**, implements **Stack** interface and

provides definition for methods in the interface. It also adds a new

method – print() to print all values in the stack.

01: class MyStack **implements** Stack {

02: private String a[] = new String[10];

03: private int top = 0;

04: public void push(String value) {

05: a[top] = value;

06: top++;

07: }

08: public String pop() {

09: top --;

10: return a[top];

11: }

12: public int length() {

13: return top;

14: }

15: public void print() {

16: for ( int i = 0; i < top ; i ++) {

17: System.out.println (a [i]);

18: }

19: }

20: }

The following **main**() creates an object of **MyStack** class and calls

its methods.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

5

01: class UseMyStack {

02: public static void main(String[] args) {

03: MyStack ms = new MyStack();

04: ms.push("First");

05: ms.push("Second");

06: ms.print();

07: System.out.println( ms.pop());

08: }

09: }

**NOTE:** A class can neither narrow the accessibility of an interface

method nor specify new exceptions in the method’s ***throws*** clause.

For example, a method declared in interface cannot be overridden

with any access narrower than public as it is implicitly declared as

public in interface.

**Using object reference of an Interface**

An object reference of an interface can refer to an object of its

implementing class or any subclass of implementing class.

For example, an object reference of **Stack** interface can refer to an

object of **MyStack** class as it implements Stack interface.

However, only methods that are present in the interface can be

called using object reference of interface even though the reference

refers to object of implementing class.

The following code snippet shows how to use object reference of

Stack interface.

Stack s;

s = new MyStack();

s.push("10");

System.out.println( s.pop());

//Following cannot be done as print() is NOT a method of

interface stack

s.print();

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

6

**NOTE:** An object reference of an interface can reference an object

of implementing class. However, only methods in interface can be

called using object reference of interface.

A single class can implement multiple interfaces. *Multiple* *inheritance*

is supported using interfaces.

**<< interface>>**

**<< interface>>**

**Stack**

**Printable**

+ push(String)

+ pop():String

+ print()

+ length() : int

**MyStack**

+ push(String)

+ pop():String

+ length(): int

+ print():void

interface Printable {

void print();

}

class MyStack implements Stack, Printable {

…

}

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

7

**An interface extending another**

 An interface can extend **one or more** interfaces.

 A class implementing the interface must define all the methods in

the entire inheritance chain.

 The interface being extended is called as *superinterface* and the

one extending is called as *subinterface*.

interface A{

void m1();

}

interface B extends A {

void m2();

}

class c1 implements B {

// implements both m1 and m2

}

**Default Methods in Interface**

 Default methods enable you to add new functionality to the

interfaces and ensure binary compatibility with code written for

older versions of those interfaces.

 You specify that a method definition in an interface is default

with the **default** keyword at the beginning of the method

signature.

 All method declarations in an interface, including default

methods, are implicitly public, so you can omit

the public modifier.

 When you extend an interface that contains a default method,

you can do the following:

o Not mention the default method at all, which lets your

extended interface inherit the default method.

o Redeclare the default method, which makes it abstract.

o Redefine the default method, which overrides it.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

8

**Static methods in Interface**

 You can define static methods in interfaces using **static** keyword.

 You can keep static methods specific to an interface, in the same

interface rather than in a separate class.

 Static methods of interface can be called using interface name

followed by method name. Ex. Counter.printAuthor()

 To call static method we don’t need any implementation of

interface or inheritance.

01: public interface **Counter** {

02: void increment();

03: void decrement();

04: int getValue();

05: default int getIncrement() {

06: return 1;

07: }

08: static void printAuthor() {

09: System.out.println("Srikanth Pragada");

10: }

11: }

01: public class **OneCounter** implements Counter {

02: private int value;

03: @Override

04: public void increment() {

05: value += getIncrement();

06: }

07: @Override

08: public void decrement() {

09: value -= getIncrement();

10: }

11: @Override

12: public int getValue() {

13: return value;

14: }

15: }

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

9

01: public class **TenCounter** implements Counter {

02: private int value;

03: @Override

04: public void increment() {

05: value += getIncrement();

06: }

07: @Override

08: public void decrement() {

09: value -=getIncrement();

10: }

11: // Override default implementation

12: @Override

13: public int getIncrement() {

14: return 10;

15: }

16: @Override

17: public int getValue() {

18: return value;

19: }

20: }

01: public class **TestCounter** {

02: public static void main(String[] args) {

03: Counter.printAuthor();

04:

05: OneCounter c = new OneCounter();

06: c.increment();

07: System.out.println(c.getIncrement());

08: System.out.println(c.getValue());

09:

10: TenCounter c2 = new TenCounter();

11: c2.increment();

12: System.out.println(c2.getValue());

13: }

14: }

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

10

**Functional Interface**

 An interface that contains only one abstract method is called as

functional interface.

 Functional interface can have default methods, but must have

only one abstract method.

 An interface can be explicitly marked as functional interface

using @**FunctionalInterface** annotation. However, the compiler

will treat any interface meeting the definition of a functional

interface as a functional interface regardless of whether or not a

FunctionalInterface annotation is present on the interface

declaration.

 Instances of functional interfaces can be created with lambda

expressions, method references, or constructor references.

 Examples are **Runnable**, **Comparable** and **Comparator**.

01: @FunctionalInterface

02: public interface Printable {

03: void print(String mgs);

04: default String newline() {

05: return "\n";

06: }

07: }

01: class Print implements Printable {

02: public void print(String msg) {

03: System.out.println(msg + newline());

04: }

05: }

06: public class FITest {

07: public static void main(String args[]) {

08: Printable p = new Print();

09: p.print("Hello");

10: Printable p2 = FITest::print;

11: p2.print("Using Method Reference");

12: }

13: public static void print(String msg) {

14: System.out.println(msg);

15: }

16: }

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

11

**Abstract class vs. Interface**

 Both interface and abstract class cannot have objects, but can

have object references.

 In case of interface, object reference can reference an object of

implementing class. An object reference of abstract class can

reference an object of subclass.

 However, abstract class can have instance variables, but

interface cannot have instance variables.

**Null interface**

Java allows interfaces to be empty. An empty interface contains no

variables and methods. It is used to tag or mark a class as having

certain property or behavior.

For example, **Serializable** interface is a null interface. A class

implementing *Serializable* interface informs to Java that it can be

serialized (converted to bytes and written to storage).

Null interface is also known as **marker** **interface**.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

12

## NESTED CLASSES

Nested class is a class defined in another class. Nested class may be

any one of the following types.

 Static member class

 Non-static member class

 Method-local inner class

 Anonymous inner class

**Static member class**

A class created in another class with static modifier is called as static

member class. It can be used just like a normal class.

However, to access it from outside of enclosing class, we have to

use the name of enclosing class as the prefix for static member

class.

01: // Top level class

02: class TLC {

03: // static member class

04: static public class SMC {

05: public void print() {

06: System.out.println("SMC");

07: }

08: }

09: public void print() {

10: System.out.println("TLC");

11: }

12: }

13:

14: public class TLCClient {

15: public static void main(String ... args) {

16: TLC.SMC srec = new TLC.SMC();

17: srec.print();

18: }

19: }

Output: SMC

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

13

**Non-static member class (inner class)**

A class defined within another class without static modifier is called

as non-static member class. It is also called as inner class.

Inner class has access to all of the variables and methods of its

outer class and can refer to them directly. Inner classes were

introduced in version 1.1 of Java, mainly to help handling events in

AWT and Swing applications.

01: class OuterClass {

02: private int m1 = 10;

03: class InnerClass {

04: private int m2 = 20;

05: public void print() {

06: System.out.printf("m1 =%d m2 =%d",m1,m2);

07: }

08: }

09: public void print() {

10: InnerClass obj = new InnerClass();

11: obj.print();

12: }

13: }

14: public class InnerTest {

15: public static void main(String args[]) {

16: OuterClass obj = new OuterClass();

17: obj.print();

18: }

19: }

**Output** : m1 =10 m2 =20

**Method-local inner class**

A class declared inside a method is called as local class. Only the

method, in which the class is defined, can create an instance of the

class.

Just like any other inner class, a local inner class can access

members of its outer class directly.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

14

01: class TLC {

02: private int v = 10;

03:

04: public void somemethod() {

05: class LocalClass {

06: public void print() {

07: System.out.printf("Local class.

08: Outer class value %d\n",v);

09: }

10: }

11: // use class here

12: LocalClass obj = new LocalClass();

13: obj.print();

14: } // end of method

15: } // end of TLC

16:

17: public class LocalTest {

18: public static void main(String[] args) {

19: TLC obj = new TLC();

20: obj.somemethod();

21: }

22: }

**Output** : Local class. Outer class value 10

**Anonymous Inner class**

Anonymous inner class combines the process of defining an inner

class and creating an object of inner class into one step. It is a

class without any name (anonymous).

new <superclass or interface> (optional arguments) {

Members definition

}

The optional arguments are passed to constructor of super class.

Anonymous class can extend either a class or implement an

interface. No **extends** or **implements** keyword is required. The

name given after keyword **new** is taken as class or interface.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

15

If anonymous class implements an interface then no arguments are

passed as interfaces do not have constructor.

**NOTE**: Anonymous classes cannot have any constructors as they

don’t have a name.

01: interface Stack {

02: void push(String value);

03: String pop();

04: }

05:

06: class OuterClass {

07: public IStack getStack() {

08: // anonymous class implements interface

09: return new Stack() {

10: public void push(String v) { // code }

11: public String pop() { // code}

12: }; // end of anonymous class

13: }

14: }

15:

16: public class AnonyTest {

17: public static void main(String ... args) {

18: OuterClass obj = new OuterClass();

19: Stack stack = obj.getStack();

20: stack.push("First");

21: }

22: }

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

16

## PACKAGES

 Package is a collection of classes and interfaces.

 Package allows you to store your classes and interface without

name collision as two packages may have same names for

classes and interfaces.

 Packages are stored in hierarchical manner. A package may be

nested in another package. For example, **java**. **util**, **java**. **lang** etc. In **java**. **util**, **util** is a package that is in another package

**java**.

 A package is a *folder* in the underlying operating system.

**NOTE**: All the classes that are not explicitly stored in any package

are stored in **default** **package** or unnamed package, which is the

current directory. And these classes are accessed directly without

any package prefix.

**Creating a package and placing a class in it**

 Use **package** statement to specify the package to which classes

and interfaces belong to.

 The **package** statement is applied to all classes and interfaces in

the source file.

 A folder, in the file system of Operating System, with the same

name as the package is to be created.

 The .class file must be stored in the package (directory).

 Once a class is placed in a package, it must always be accessed

using package name as prefix – *packagename*. *classname*.

package <fully qualified package name>

The following example shows how to create a class in a package

called **library**. The package **library** must be created by creating a

folder with that name.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

17

01: package library; // “Book” class belongs to library package

02: public class Book {

03: // class code

04: }

**NOTE**: If **package** statement is used then it must be the first

statement in the source file.

Class **Book** belongs to package **library**. Apart from using package

statement in .java file (as shown above), **Book**. **class** must be

placed in folder **library** to make **Book** class belong to library

package.

**NOTE:** A class with **public** access may be accessed from outside

package, whereas a class with **default** access (no access) is

confined to package in which it is defined.

If you want two public classes to belong to the same package then

each class must be placed in a different .java file as shown below.

01: // Book.java

02: package library;

03: public class Book {

04: // body of Book class

05: }

01: // Member.java

02: package library;

03: public class Member {

04: // body of class

05: }

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

18

**Accessing classes of a package**

You can access a member of the package by using package name

followed by dot (.). A member of the package must be prefixed with

package name. The following code shows how to access Book class

of library package.

01: public class UseLibrary {

02: public static void main(String[] args) {

03: library.Book b = new library.Book();

04: }

05: }

The hierarchy of folders is as follows:

c:\jdk\srikanth

|

---- library

| |

| ----- Book.class

----- UseLibrary.class

A package can be accessed only from its parent directory (unless

CLASSPATH is used). In the above example, package library can be

accessed only from **programs** folder.

**Import Statement**

Use **import** statement to import specified classes or packages into

current source file.

import pkg1[.pkg2…].{classname|*}

***** means all classes of the package are to be imported, but it does

not import subpackages of the package.

**NOTE**: The **import** statement must be given after **package**

statement in the source file if both exist.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

19

The following examples import all members of package **st**, **Date**

class in **java**. **util** package and all classes of **java**. **text** package**.**

import st.*;

import java.util.Date;

import java.text.*;

**NOTE:** Importing a package only imports classes in the package,

but not nested packages in the package. So, classes in each nested

package are to be explicitly imported.

**NOTE:** Package **java**. **lang** is automatically imported. So its classes like String, System, Integer etc. can be used without importing

them.

**CLASSPATH variable**

 Contains the list of directories where Java will look for classes

and packages.

 Java compiler and runtime use CLASSPATH variable to get the

list of folders and . **jar** files that are to be searched for the

required classes and packages.

 By default java searches for the specified classes in the current

directory and in standard library.

 But once CLASSPATH is set then Java uses only the directories in

CLASSPATH and standard library to search for classes and does

NOT search in the current directory.

The following example sets CLASSPATH to current directory (**.** ) and

**c:\jdk\srikanth** folder.

c:>set classpath=.;c:\jdk\srikanth

**SET** command is an operating system command. **CLASSPATH** is a

variable used by Java compiler and JVM to locate packages and

classes.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

20

**JAR (Java Archive) File**

A JAR file contains packages, classes and interfaces. By including

.jar file in CLASSPATH we can make its packages, classes and

interfaces available to Java.

**JAR** utility, which is provided with JDK, is used to create and extract

JAR files. This tool is invoked from command prompt.

The following command creates a JAR file to contain all .class files in

library folder. Flag **c** stands for create, **f** stands for file and **v** stands for verbose.

C:\jdk\srikanth>jar cfv library.jar library\*.class

You can see the content of a JAR file by using flag **t** (table of

content) as follows:

c:\jdk\srikanth>jar ft library.jar

You need not extract JAR file to use its packages and classes. Just

including .jar file in CLASSPATH will do.

So to use **library**. **jar** that is placed in **c:\java** folder, we need to set classpath as follows:

c:>set classpath=.;c:\jdk\srikanth; **c:\java\library.jar**

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

21

**Access Modifiers**

Access modifiers specify from where a member can be accessed.

The following are the available access modifiers for member of a

class and their meaning.

**Access Modifier**

**Meaning**

private

Allows member to be accessed only from the

class in which it is defined.

protected

Allows member to be accessed from the class

and all its subclasses and also from any class in

the same package.

default

Allows members to be accessed throughout the

package to which the class belongs. If no access

modifier is given then Java uses *default* as

access modifier.

public

Allows a member to be accessed from

anywhere.

**NOTE:** For top level classes, only **public** and **default** access

modifiers are applicable. However, inner classes can have **private**

and **protected** modifiers also.

The following example demonstrates how access modifiers influence

the access of members from subclasses, other classes in the same

package and other packages.

**A.java**

01: package p1;

02: public class A {

03: private int v1;

04: protected int v2;

05: public int v3;

06: int v4; // default access

07: }

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

22

**B**. **java**

01: package p1;

02: public class B extends A {

03: public void print() {

04: // can access v2, v3, v4

05: }

06: }

07:

08: class C {

09: public void print() {

10: A obj = new A();

11: // can access v2,v3,v4 of obj

12: }

13: }

**D**. **java**

01: package p2;

02: import p1.A;

03: public class D extends A {

04: public void print() {

05: // can access v2,v3

06: }

07: }

08:

09: class E {

10: public void print() {

11: A obj = new A();

12: // can access v3 of obj only

13: }

14: }

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

23

The following table summarizes access methods and their impact.

**Where**

**Private Default Protected Public**

Same class

Yes

Yes

Yes

Yes

Subclass in same package

No

Yes

Yes

Yes

Non subclass in same

No

Yes

Yes

Yes

package

Subclass in different

No

No

Yes

Yes

package

Non-subclass in different

No

No

No

Yes

package

**Static Import**

 It allows static members of a class to be imported.

 Once the static members are imported, they may be used

without qualification.

 Fully qualified name of the members must be used in import

static statement.

 Should be used sparingly otherwise causes loss of readability.

01: import static java.lang.Math.PI;

02: import static java.lang.Math.abs;

03: import static java.lang.System.out;

04:

05: public class StaticImport {

06:

07: public static void main(String[] args) {

08: out.println (PI);

09: out.println (abs(-100));

10: }

11: }

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

24

## ENUMERATION

 Enumeration is a collection of constants. Java provides support

for enumeration through keyword **enum**.

 An enum is internally converted to a full-fledged class.

 Values in enumeration can be compared and assigned.

 Enumeration can be used with switch statement and enhanced

for loop.

01: enum Languages {

02: C, CPP, JAVA, CSHARP

03: };

04: public class EnumDemo {

05: public static void main(String[] args) {

06:

Languages lang;

07:

08:

lang = Languages.JAVA;

09:

if (lang == Languages.JAVA)

10:

System.out.println("Next is Java EE");

11:

System.out.println("Value of lang = " + lang);

12:

switch (lang) {

13:

case C:

14:

System.out.println("Java or C++");

15:

break;

16:

case CPP:

17:

System.out.println("Java");

18:

break;

19:

case JAVA:

20:

System.out.println("Java EE");

21:

break;

22:

case CSHARP:

23:

System.out.println("ASP.NET");

24:

break;

25:

}

26: } // end of main

27: } // end of class

**Output**

Next is Java EE

Value of lang = JAVA

Java EE

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

25

## EXCEPTION HANDLING

 An Exception is an abnormal condition (runtime error).

 When an exceptional event occurs, Java throws an exception.

 An exception is an object of a class that is created from

**java**. **lang**. **Exception** class.

 Depending upon the error (exceptional event), an object of

exception class is created and thrown.

 If the exception is not handled then program is terminated

abnormally.

 Exception can be thrown by Java Runtime System or by the

code.

The following code demonstrates what happens when you run code

that throws an exception.

01: public class Test {

02: public static void main(String[] args) {

03: int n;

04:

05: n = Integer.parseInt( args[0]);

06: if ( 99 % n == 0 ) {

07: System.out.printf("%d is a factor of 99", n);

08: }

09: }

10: }

If the above program is run with a command line parameter that

cannot be converted to int (such as *abc*) then exception

**NumberFormatException** is thrown.

**java** **Test** **abc**

Exception in thread "main" java.lang.NumberFormatException: For

input string: "ABC"

at java.lang.NumberFormatException.forInputString(Unknown

Source) …

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

26

When an exception is thrown, program is terminated at the line that

caused the exception.

The following are the keywords related to exception handling in

Java.

**Keyword Meaning**

try

Specifies the block in which you want to monitor for

exceptions.

catch

Catches an exception and takes necessary action.

finally

Contains the code that must be executed before leaving

try block.

throws

Specifies the exceptions that a method might throw.

throw

Throws the given exception.

The following is the general syntax for try, catch and finally blocks.

try {

// try block

}

catch(<exceptiontype> <parameter>) {

// catch block

}

finally {

// finally block

}

**NOTE:** After try block either catch or finally or both may be given.

But you cannot avoid both.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

27

**Handling exception using try and catch**

If you want to handle the exception that is likely to be thrown then

place the code in **try** block and handle the exception in **catch** block

as shown below.

01: public class Test {

02: public static void main(String[] args) {

03: int n;

04: try{

05: n = Integer.parseInt(args[0]);

06: if ( 99 % n == 0 )

07: System.out.printf("%d is a factor of 99", n);

08: }

09: catch(NumberFormatException ex) {

10: System.out.println("Invalid number!");

11: }

12: } // end of main

13: } // end of class

**Handling multiple exceptions**

It is also possible to handle more than one exception. If the code in

**try** block is likely to throw more than one exception then you have

to handle all potential exceptions using multiple catch blocks.

However note that a try block can throw only one exception at a

time. Because once an exception is thrown, the code after the

statement causing the exception will not be executed.

The following code shows how to handle two exceptions –

*NumberFormatException* and *ArrayIndexOutOfBoundsException*.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

28

01: public class Test {

02: public static void main(String[] args) {

03: int n;

04: try{

05: n = Integer.parseInt(args[0]);

06: if ( 99 % n == 0 )

07: System.out.printf("%d is a factor of 99", n);

08: }

09: catch(NumberFormatException ex) {

10: System.out.println("Invalid number!");

11: }

12: catch(ArrayIndexOutOfBoundsException ex) {

13: System.out.println("Number parameter is missing!");

14: }

15: }

16: }

In the code above, try block will throw

*ArrayIndexOutOfBoundsException* if no parameter is passed on

command line (as args[0] is not available). The other exception that

will be thrown if string in args[0] cannot be converted to an integer

is *NumberFormatException.*

**Multi-Catch**

Prior to Java 7, we had to catch only one exception type in each

catch block. So whenever we needed to handle more than one

specific exception, but take the same action for all exceptions, then

we had to have more than one catch block containing the same

code.

In the following code, we have to handle two different exceptions,

but take the same action for both. So we need two different catch

blocks as of Java 6.0.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

29

try {

int v = Integer.parseInt(num);

int result = 100 / v;

System.out.println(result);

}

catch(NumberFormatException ex)

{

// take action

}

catch(ArithmeticException ex) {

// take action

}

Starting from Java 7.0, it is possible for a single catch block to catch

multiple exceptions by separating exception with **|** (pipe) symbol in

catch block.

try {

int v = Integer.parseInt(num);

int result = 100 / v;

System.out.println(result);

}

// multi-catch

**catch**(**NumberFormatException** | **ArithmeticException** **ex**) {

// take action

}

A catch block that handles multiple exception types creates no

duplication in the bytecode generated by the compiler; the bytecode

has no replication of exception handlers.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

30

**Finally Block**

 Used to execute code that is to be executed after a try/catch

block has completed and before the code following try/catch is

executed.

 Can be used to perform any operation that must be done before

you leave try/catch block – clean up code.

 Finally clause is optional. If it is given, it must be given either

after catch block(s) if exists or after try block.

try {

// code

}

finally {

// code

}

No catch block found

Exception

Find matching

Execute Try Block

Catch block

No

Exception - 1

Exception -2

exception

Handle Exception -1

Handle Exception -2

Execute

final y block

No exception or exception handled

Exception not handled

Normal Exit

Exit with Exception

Srikanth Technologies

![](index-130_1.jpg)

Java Student’s Guide – Object-Oriented Programming II

31

The following snippet demonstrates how to use **finally** block.

public void m1() {

try {

// code

}

catch(NumberFormatException ex) {

// exception code

}

finally {

// place cleanup code

}

}

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

32

The following are the cases in which the finally block in the above

snippet is executed.

 When try block is successfully executed without any exceptions

then control goes to finally block after try block.

 When *NumberFormatException* is thrown in try block, the

exception is handled by catch block and then control goes to

finally block.

 When try block throws an uncaught exception then also control

goes to finally block and then program is terminated. But in this

case the program is terminated after finally block is executed.

Run code below and see the output (shown below) to understand

flow of control with try, catch and finally blocks.

01: public class FinallyTest {

02: public static void main(String[] args) {

03: method("5");

04: method("abc");

05: method("0");

06: } // end of main()

07:

08: public static void method(String value){

09: try{

10: int n = Integer.parseInt(value);

11: System.out.println( 100 / n);

12: }

13: catch(NumberFormatException ex) {

14: System.out.println("Invalid number!");

15: }

16: finally {

17: System.out.println("Finally block.");

18: }

19:

20: System.out.println("**Method Completed**");

21: } // end of method()

22: }

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

33

20

Finally block.

**Method Completed**

Invalid number!

Finally block.

**Method Completed**

Finally block.

Exception in thread "main" java.lang.ArithmeticException: / by

zero

at FinallyTest.method(FinallyTest.java:13)

at FinallyTest.main(FinallyTest.java:8)

Exception may be thrown by JVM or by methods in classes (API). In

the above program ***NumberFormatException*** is thrown by

**parseInt**() of ***Integer*** class, which is Java API.

Exceptions ***ArithmeticException*** and

***ArrayIndexOutOfBoundsException*** are thrown by JVM.

**Types of Exceptions – checked and unchecked**

There are two types of exceptions - Unchecked or Implicit

exceptions and Checked or Explicit exceptions.

**Unchecked Exceptions**

Handling unchecked exceptions is not mandatory. Some of these

exceptions are thrown by JVM and others by Java API. However, you

may want to handle unchecked exceptions to prevent program from

getting terminated and handle exceptional events.

All exceptions that extend **RuntimeException** class are unchecked

exceptions.

**Checked Exceptions**

Checked exceptions are thrown by methods. These exceptions must

be handled by the code calling the method using try and catch

blocks.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

34

In method declaration, we have to specify the checked exceptions

that the method is likely to throw using **throws** clause.

Methods that might throw a checked exception must be called from

try block where catch block handles the checked exception. Or the

calling method must declare checked exception that might be

thrown by called method in its **throws** clause.

**NOTE:** Checked exceptions are always thrown from methods and

never by JVM.

Object

Throwable

Exception

Error

ClassNotFoundException

AssertionError

**Runtim eException**

ArrayIndexOutOfBoundsException

Num berFormatException

IOException

FileNotFoundException

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

35

The following code snippet shows how to handle or propagate

checked exceptions.

01: public class TestChecked {

02: public void m1() throws AmountException {

03: // code

04: }

05: public void m2() throws AmountException {

06: m1();

07: }

08: public void m3() {

09: try {

10: m1();

11: }

12: catch(AmountException ex){

13: }

14: }

15: }

The following are the points related to above program:

 Method m1() is likely to throw a checked exception -

**AmountException** and it must be handled by methods calling

m1().

 Method m2() compiles even though it calls m1() without handling

AmountException as it declares **AmountException** in its throws

clause.

 Method m3() handles **AmountException** that is likely to be

thrown by m1() using try and catch blocks.

**Invalid vs. Valid order of catch blocks**

Understanding the hierarchy of exception classes is important. Most

specific exception must be handled first and then less specific.

The following snippet shows invalid order for exception handling and

will result in compilation error.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

36

try{

…

}

catch(Exception ex) { }

catch(RuntimeException ex) { }

catch(NumberFormatException ex) { }

Any exception is a match to *Exception* class. So giving catch block

with Exception class first will not allow other catch blocks to ever get

control and makes those catch blocks unreachable.

**Valid order of catch blocks**

The following is valid order of catch blocks. Most specific exception –

*NumberFormatException* is handled first and most general,

*Exception,* is handled last.

try{

…

}

catch(NumberFormatException ex){ }

catch(RuntimeException ex){ }

catch(Exception ex) { }

**Defining new exception**

It is possible to create a new exception by creating a class. User-

defined exceptions can be thrown and caught just like ready-made

exceptions. However, unlike JVM exceptions, which are thrown by

Java Runtime, user-defined exceptions are to be explicitly thrown by

methods.

To create a user-defined exception, create a class that extends

**Exception** class directly or indirectly.

The exception class need not create any method of its own since it

inherits methods of **Exception** class. The following code shows how

to create a user-defined exception and how to throw and catch.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

37

01: class StackFullException extends Exception {

02: public StackFullException() {

03: super("Stack is full"); // exception message

04: }

05: }

06: class Stack {

07: public void push(int v) throws StackFullException {

08: if ( condition )

09: throw new StackFullException();

10: }

11: }

User-defined exception *StackFullException* will be thrown by **push**

method in case of an error.

Any code calling **push** method must make sure it catches

*StackFullException* as it is given in **throws** clause of push method.

The following snippet shows how to handle push method.

try {

s.push(10);

…

}

catch(StackFullException ex) {

System.out.println (ex.getMessage());

}

**Exception class**

The following are the methods available in *Exception* class. In fact,

all these methods are actually derived from *Throwable* class and

*Exception* class has no methods of its own.

**Method**

**Meaning**

getMessage()

Returns description of the exception. The

message is passed to Exception class by its

subclass using constructor of Exception class.

printStackTrace() Displays the stack trace providing all methods

that are invoked from the beginning to the point

of error.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

38

**Defining user-defined exceptions – example**

Here is a complete example to demonstrate creating, throwing and

handling user-defined exceptions using Account class.

01: public class **InvalidAmountException** extends Exception {

02: public InvalidAmountException() {

03: super("Invalid Transaction Amount!");

04: }

05: public InvalidAmountException(String msg) {

06: super(msg);

07: }

08: }

01: public class **InsufficientAmountException**

02: extends Exception {

03: public InsufficientAmountException() {

04: super("Insufficient Balance!");

05: }

06: public InsufficientAmountException(String msg) {

07: super(msg);

08: }

09: }

01: public class **Account** {

02: String acno;

03: double balance;

04: public Account(String acno, double balance) {

05: this.acno = acno;

06: this.balance = balance;

07: }

08: public void deposit(double amount)

09: throws InvalidAmountException {

10: if ( amount < 100 ) {

11: throw new InvalidAmountException();

12: }

13: balance += amount;

14: }

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

39

15: public void withdraw(double amount) throws

16: InvalidAmountException,InsufficientAmountException{

17: if ( amount < 100 ) {

18: throw new InvalidAmountException();

19: }

20: if ( balance < amount ) {

21: throw new InsufficientAmountException();

22: }

23: balance -= amount;

24: }

25: }

01: public class **UseAccount** {

02: public static void main(String[] args) {

03: Account a = new Account("1002", 10000);

04: try {

05: a.deposit(1000);

06: System.out.println("Deposited 1000");

07: a.deposit(50);

08: }

09: catch(InvalidAmountException ex) {

10: System.out.println(ex.getMessage());

11: }

12: try {

13: a.withdraw(5000);

14: System.out.println("Withdrew 5000");

15: a.withdraw(8000);

16: System.out.println("Withdrew 8000");

17: }

18: catch(Exception ex) {

19: ex.printStackTrace();

20: }

21: }

22: }

Deposited 1000

Invalid Transaction Amount!

Withdrew 5000

InsufficientAmountException: Insufficient Balance!

at Account.withdraw(Account.java:26)

at UseAccount.main(UseAccount.java:24)

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

40

**More precise rethrow in Java 7.0**

If an exception parameter is not modified and if it is re-thrown

inside the catch block, the compiler applies a more precise analysis

to determine the type of what can be thrown.

In the code below, throw ex; will result in error in Java 6.0 as **ex** is

of type **Exception** and method has only **Ex1** and **Ex2** in **throws**

clause.

Exception type is much more general than Ex1 and Ex2, so Java

doesn't allow us to throw ex, which is declared as Exception.

But Java 7.0 applies **more precise analysis** to determine the type

of exception being thrown.

Java 7.0 understands that only two possible exceptions (Ex1 and

Ex2) can be thrown from try block so it allows **ex** to be rethrown

though ex is declared as **Exception**.

01: class Ex1 extends Exception { }

02: class Ex2 extends Exception { }

03:

04: public class RethrowException {

05: public void m1(int v) throws Ex1 , Ex2 {

06: try {

07: if (v < 0) {

08: throw new Ex1();

09: }

10: else

11: if ( v > 100 ) {

12: throw new Ex2();

13: }

14: // process

15: }

16: catch (Exception ex) {

17: throw ex; // Doesn’t compile in 6.0, but works in 7.0

18: }

19: }

20: }

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

41

**Assertions**

 Assertions can be used to validate assumptions made about state

of the program.

 Each assertion is associated with a Boolean condition. If

condition fails it means the assumption fails and assertion error

occurs.

 Assertions are **disabled** by default. So, you must enable

assertions at the time of running program.

 Assertions are part of development process. They should not be

included in final version of your code.

assert <boolean expression>

assert <boolean expression> : message

When boolean expression results in false, Java throws

**AssertionError**. If it results in true, execution of program continues

normally.

If message is given then it is displayed in stack trace when assertion

error occurs. The following code shows how to use assertion to

validate parameter of a private method.

01: public class AssertionTest {

02:

03: private void print(int count) {

04: assert count > 0 : "Invalid count for print()";

05: }

06:

07: public static void main(String[] args) {

08: AssertionTest t = new AssertionTest();

09: t.print(1);

10: t.print(0);

11: }

12: }

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

42

If you run the previous program by enabling assertions using **–ea**

flag of JVM as shown below then the following will result:

>java **–ea** AssertionTest

Exception in thread "main" java.lang.AssertionError: Invalid

count for print()

...

**NOTE:** Assertions must be used in such a way that, even though

assertions are disabled, the functionality of the program does not

change. And also remember assertions are only debugging aids.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

43

## MULTITHREADING

 An independent sequential path of execution within a program is

called as a thread.

 When a program contains two or more parts that run

concurrently, it is called as multithreading.

 Java’s libraries are designed with multithreading on mind.

 Each thread is also called as lightweight process and the

overheads are low compared with a process.

 A thread may exist in any of the states such as running, ready,

blocked etc., during its life time.

 All the threads of a process run within the same address space.

 Context switching between threads is less expensive and faster

than context switch between processes.

 **Thread** object in Java represents a thread.

**Process1**

**Process2**

**Address Space**

**Address Space**

**Thread1**

Inter-process

**Inter-thread**

Communication

**Communication**

**Thread1**

**Thread2**

**Process**

 A process has a self-contained execution environment.

 A process generally has a complete, private set of basic run-time

resources; in particular, each process has its own memory space.

 Processes are often seen as synonymous with programs or

applications.

 Most implementations of the Java virtual machine run as a single

process.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

44

**Main Thread**

 Main thread is the first thread to start in a Java program.

 This is the thread from where other threads are created and

started.

 It is typically the last thread to terminate. When main thread

terminates then the program terminates unless other threads

spawned by main thread still run.

 This thread is created by JVM to run **main**() method.

01: public class MainThread {

02: public static void main(String[] args) {

03: Thread t = Thread.currentThread();

04:

05: System.out.println( t.getName());

06: System.out.println( t.getPriority());

07: }

08: }

The following are two different ways in which a new thread can be

created.

 By extending **Thread** class.

 By implementing interface **Runnable**.

**Creating a new thread by extending Thread class**

 You can create a new thread by creating an object of a class that

extends **Thread** class. The following are the steps to be

followed:

 Create a class that extends **Thread** class.

 Override **run** () method of **Thread** class.

 Create an object of subclass of **Thread** class and invoke **start ()**

method to start running the thread, which in turn calls **run**()

method.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

45

01: // Multi-threading using subclass of Thread class

02: class ChildThread extends Thread {

03: @Override

04: public void run() {

05: for ( int i = 1; i <=50;i ++) {

06: System.out.println( "Child -> " + i);

07: }

08: } // end of run

09: } // end of ChildThread

10:

11: public class MainThread {

12: public static void main(String args[]){

13: System.out.println("In Main");

14: ChildThread ct1 = new ChildThread();

15: ct1.start(); // run thread

16:

17: System.out.println("In Main again");

18: for (int i = 1; i <=50;i ++) {

19: System.out.println( "Main -->" + i);

20: } // end of for

21:

22: System.out.println("End of main");

23: } // end of main()

24: }

**Creating a new thread using Runnable interface**

A new thread can be created by using an object of **Thread** class and

a class that implements **Runnable** interface. Follow the steps

below to create a thread:

 Create a class that implements **Runnable** interface.

 Implement **run**() method of **Runnable** interface.

 Create an object of **Thread** class and send an object of the class

which implements Runnable interface as parameter to

constructor of **Thread** class.

 Call **start**() method of **Thread** class. It then calls **run**() method of the object that is passed as parameter to constructor of

**Thread** class.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

46

**NOTE:** **Runnable** interface has a single **run**() method. **Thread**

class also implements **Runnable** interface.

01: class ThreadCode implements Runnable {

02: public void run() {

03: for ( int i = 1; i <= 50 ; i ++) {

04: System.out.println(i);

05: }

06: } // end of run

07: } // end of ThreadCode

08:

09: public class RunnableThread {

10: public static void main(String args[]) {

11: ThreadCode code = new ThreadCode();

12: Thread t = new Thread(code);

13: t.start(); // Calls run() method of code object

14:

15: for ( int i = 1 ; i <= 50 ; i ++)

16: System.out.println( "Main --> " + i);

17: }

18: }

**Thread States – life cycle of a thread**

A thread can exist in different states at different points of time. A

thread passes from one state to another state since it is started

using **start**() method.

The following table and figure discuss different states and the

transitions in the life cycle of a thread.

**State**

**Meaning**

New

A new thread object is created and not yet

started.

Ready to run

Thread is started using **start**() method. In this

state, thread is ready to run, but control is not

given. If control is given then it starts running.

Apart from being in this state in the beginning, a

thread enters into this state from other states as

well.

Srikanth Technologies

![](index-146_1.jpg)

Java Student’s Guide – Object-Oriented Programming II

47

Running

Thread is currently running.

Sleep

Method **sleep**() is invoked and thread is sleeping

for the given number of milliseconds.

Blocked for IO

Thread has initiated some IO operation and is

waiting for completion of the operation.

Blocked for join

Thread awaits completion of another thread.

Waiting for

Thread awaits notification from another thread.

notification

Thread has executed **wait**() method of an object.

It will wait until another thread invokes **notify**()

or **notifyAll**() method of that object on which it

invoked **wait**(). This is related to inter-thread

communication.

Blocked for lock

Thread waits to acquire the lock of an object.

acquisition

Once a thread is notified by another thread, it will

wait until it can acquire lock on an object. This is

related to inter-thread communication.

Dead

Thread is terminated.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

48

**Thread priority**

 Each thread is associated with a priority.

 Priority is used by thread scheduler to decide which of the

available threads should be given control.

 Priority is relative and not absolute. That means the priority of

other thread will decide whether current thread gets control.

 Use **setPriority**(int) and **getPriority**() methods to set and get

priority of a thread.

 Thread class has three static members (MIN_PRIORITY,

NORM_PRIORITY, MAX_PRIORITY), which can be used to set

priority of the thread.

 Default priority of a thread is normal priority, which is

represented as number 5.

 A thread inherits priority of its parent thread.

ChildThread t = new ChildThread();

t.setPriority(Thread.MAX_PRIORITY);

if ( t.getPriority() == Thread.MAX_PRIORITY )

System.out.println("Thread with max priority");

**Thread class**

Thread class is used to create a new thread. Every thread in Java is

an object of Thread class. Thread class provides static and non-

static methods that perform operations on threads.

static in[t MAX_PRIORITY](Thread.html_MAX_PRIORITY)

The maximum priority that a thread can

have.

static in[t MIN_PRIORITY](Thread.html_MIN_PRIORITY) The minimum priority that a thread can have.

static in[t NORM_PRIORITY](Thread.html_NORM_PRIORITY) The default priority that is assigned to a thread.

[Thread()](Thread.html_Thread())

[Thread(](Thread.html_Thread(java.lang.Runnable))[Runnable](../jdk1.4/docs/api/java/lang/Runnable.html) target)

[Thread(](Thread.html_Thread(java.lang.Runnable,%20java.lang.String))[Runnable](../jdk1.4/docs/api/java/lang/Runnable.html) [target, String](../jdk1.4/docs/api/java/lang/String.html) name)

[Thread(](Thread.html_Thread(java.lang.String))[String](../jdk1.4/docs/api/java/lang/String.html) name) Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

49

**Method**

**Meaning**

stati[c Thread](../jdk1.4/docs/api/java/lang/Thread.html)

Returns a reference to the currently

[currentThread()](Thread.html_currentThread())

executing thread object.

void [destroy()](Thread.html_destroy())

Destroys this thread, without any

cleanup.

[String](../jdk1.4/docs/api/java/lang/String.html) [getName()](Thread.html_getName())

Returns this thread's name.

int [getPriority()](Thread.html_getPriority())

Returns this thread's priority.

void [interrupt()](Thread.html_interrupt())

Interrupts this thread.

boolean [isAlive()](Thread.html_isAlive())

Tests if this thread is alive.

boolean [isDaemon()](Thread.html_isDaemon())

Tests if this thread is a daemon

thread.

void [join()](Thread.html_join())

Waits for this thread to die.

void [join(](Thread.html_join(long))long millis) Waits at most ***millis*** milliseconds for

this thread to die.

void [run()](Thread.html_run())

Specifies the code to be executed. It

is overridden by subclass of Thread

class.

void

Marks this thread as either a daemon

[setDaemon(bool](Thread.html_setDaemon(boolean))ean on) thread or a user thread. Must be done

before thread is started.

void [setName(](Thread.html_setName(java.lang.String))[String](../jdk1.4/docs/api/java/lang/String.html) name) Changes the name of this thread to be equal to the argument name.

void [setPriority(](Thread.html_setPriority(int))int priority) Changes the priority of this thread.

static void [sleep(l](Thread.html_sleep(long))ong millis) Causes the currently executing thread to sleep (temporarily cease

execution) for the specified number of

milliseconds.

void [start()](Thread.html_start())

Causes this thread to begin execution.

The Java Virtual Machine calls the run

method of this thread.

static void [yield()](Thread.html_yield())

Causes the currently executing thread

object to temporarily pause and allow

other threads to execute.

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

50

The following code demonstrates some methods of **Thread** class

01: class DeamonThread extends Thread {

02:

03: public void run() {

04: // code

05: }

06: }

07:

08: class ThreadMethods {

09: public static void main(String args[]) {

10: System.out.println("waiting...");

11: try {

12: Thread.sleep(1000); // will wait for 1000 milliseconds

13: // do something

14: }

15: catch (InterruptedException ex) {

16: }

17: // make a thread a daemon

18: DaemonThread dt = new DaemonThread();

19: dt.setDaemon(true);

20: dt.start(); // starts daemon

21:

22: ChildThread ct = new ChildThread();

23: ct.start();

24: try {

25: ct.join();// make current thread wait until ct is dead

26: System.out.println("Child completed");

27: }

28: catch(InterruptedException ex) {

29: }

30: }

31: }

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

51

**Synchronization**

 This is the process by which Java ensures that a shared resource

is accessed only by one thread at a time.

 Java provides synchronization as part of language using

synchronized methods and synchronized statements.

 A monitor is an object that is used as a mutually exclusive lock,

or *mutex*. Only one thread can enter into a monitor at a given

time. When a thread acquires a lock, it is said to have entered

the monitor.

 When a thread invokes a synchronized method, it locks the

object (enters the monitor) preventing other threads from

invoking any synchronized method of the object.

class Stack

{

private int data[] = new int[10];

10:10:10

private int top = 0;

Thread1

synchronized public void push (int v)

{ data [top] = v;

Thread1

top ++;

lost

Thread2 cannot

control at

}

invoke push() or

10:10:11

pop() as Thread1

10:10:12

synchronized public int pop()

has already entered

into monitor

{ // code }

Thread2

}

Monitor

data

top

Thread1

Of Stack

Object

10 …

0

Srikanth Technologies

![](index-151_1.jpg)

Java Student’s Guide – Object-Oriented Programming II

52

The scenario shown by above figure is as follows:

 Thread1 and Thread2 both access the same object of Stack class.

 At 10:10:10 Thread1 called **push()** method of stack object.

 By calling **push()** method, which is synchronized, Thread1

entered into monitor of stack object. It means stack object is

now locked.

 After executing first statement in **push()** method, at 10:10:11

Thread1 lost control and control is given to Thread2.

 Upon receiving control, Thread2 tries to enter into **push()**

method at 10:10:12, but cannot enter into it as the monitor of

stack object still has thread1.

**NOTE:** To enter into any synchronized method of an object; a

thread must first enter into monitor of the object.

Object of the class that has at least one synchronized method is

associated with a monitor.

The following example shows importance of synchronizing a method

when two or more threads are accessing the same object.

01: class Data {

02: synchronized public void print() {

03: for ( int i = 1; i <= 5; i ++) {

04: System.out.println(i);

05: try {

06: Thread.sleep(100);

07: }

08: catch(Exception ex) {}

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

53

09: }

10: }

11: } // end of data

12:

13: class CThread extends Thread {

14: Data obj;

15: public CThread (Data obj) {

16: this.obj = obj;

17: }

18: public void run() {

19: obj.print();

20: }

21: } // end of CThread

22:

23: public class SyncTest {

24: public static void main(String args[]) {

25: CThread thread1,thread2;

26: Data obj = new Data();

27: // make two threads access the same object

28: thread1 = new CThread(obj);

29: thread2 = new CThread(obj);

30: thread1.start();

31: thread2.start();

32: } // end of main

33: }

**Synchronized statement**

Synchronized statement allows you to implement synchronization

even when you cannot make a method synchronized. This is

required when you have to synchronize a method in a class whose

source code is available to you (only .class file is available).

synchronized (object) {

// invoke methods to be synchronized

}

The **object** used with synchronized statement is the object whose

methods are to be synchronized. Synchronized block ensures that a

call to a method, which is a member of object used with

Srikanth Technologies

Java Student’s Guide – Object-Oriented Programming II

54

synchronized statement, occurs only after the current thread has

successfully entered object’s monitor.

Change **run**() method of **CThread** class as follows to use

synchronization. The rest of the program remains same as shown in

the previous case.

01: class CThread extends Thread {

02:

03: public void run(){

04: synchronized(obj) {

05: obj.print();

06: }

07: }

08: } // end of CThread

**Thread Pools**

 A thread pool is a collection of worker threads.

 It minimizes the overhead due to thread creation whereas

Thread objects use a significant amount of memory, and in a

large-scale application, allocating and deallocating many thread

objects creates a significant memory management overhead.

 One common type of thread pool is the fixed thread pool. This

type of pool always has a specified number of threads running.

Tasks are submitted to the pool via an internal queue, which

holds extra tasks whenever there are more active tasks than

threads.

 A simple way to create an executor that uses a fixed thread pool

is to invoke the [**newFixedThreadPool**](http://docs.oracle.com/javase/7/docs/api/java/util/concurrent/Executors.html#newFixedThreadPool(int)) factory method in [**java.util.concurrent.Executors.**](http://docs.oracle.com/javase/7/docs/api/java/util/concurrent/Executors.html)

Srikanth Technologies

![](index-154_1.jpg)

Java Student’s Guide – Object-Oriented Programming II

55

01: import java.util.concurrent.ExecutorService;

02: import java.util.concurrent.Executors;

03:

04: public class ExecutorDemo {

05: public static void main(String[] args) {

06: ExecutorService executor =

07: Executors.newFixedThreadPool(3);

08:

09: for ( int i = 1; i <= 10; i ++) {

10: executor.execute( new PrintNumbers("Thread" + i));

11: }

12: System.out.println("Done with main()");

13: }

14: }

15:

16: class PrintNumbers implements Runnable

17: {

18: private String name;

19: public PrintNumbers (String name) {

20: this.name = name;

21: }

22: public void run() {

23: for ( int i = 1; i <= 5 ; i ++)

24: System.out.printf("%s : %d\n", name , i);

25: }

26: }

Srikanth Technologies

Java Library

Part – II

Java Student’s Guide - Library-II

2

**WHAT WILL YOU LEARN IN THIS MODULE?**

At the end of this module you will have learnt the following:

 **Input-output streams**

 **Reader, BufferedReader, InputStreamReader classes**

 **FileReader, LineNumberReader, PushbackReader classes**

 **Writer, FileWriter, PrintWriter classes**

 **RandomAccessFile class**

 **File class**

 **Serialization**

 **How to create server and client sockets?**

 **Handling multiple clients using multithreading**

 **INetAddress and URL classes**

 **Collection, List, Set, SortedSet interfaces**

 **ArrayList class**

 **Using Generics**

 **HashSet, LinkedHashSet and TreeSet classes**

 **Queue interface and LinkedList class**

 **Vector and Stack classes**

 **Map, SortedMap interfaces**

 **HashMap, TreeMap classes**

 **Collections class**

 **Generic Methods**

 **Regular expressions - Pattern and Matcher classes**

 **Lambda Expression**

 **Streams**

Srikanth Technologies

Java Student’s Guide - Library-II

3

## INPUT-OUTPUT STREAMS

 A stream is an ordered sequence of bytes of undetermined

length.

 An input stream moves data from external source and output

stream sends data to external target.

 All streams behave in the same manner even if the actual

physical devices are different.

 A stream that is linked to a file on the disk or printer or a

network connection behaves in the same manner irrespective of

the differences between the devices it is connected to.

 All classes and interfaces related to IO Streams are in **java.io**

package.

 Java classifies streams as byte streams and character streams.

**Byte streams**

 Treat the stream as a collection of bytes.

 Used when data that is input or output is to be treated as bytes.

 All byte streams are derived from either **InputStream** or

**OutputStream**.

**Character Streams**

 Treat the stream as a collection of characters.

 They use Unicode and therefore, can be internationalized.

 At the top of the hierarchy there are two abstract classes –

**Reader** and **Writer**.

**Byte Streams**

**InputStream**

**OutputStream**

**Character Streams**

**Reader**

**Writer**

Srikanth Technologies

Java Student’s Guide - Library-II

4

**Predefined streams**

 **System** class of **java.lang** package contains three static

variables – **in**, **out** and **err**.

 **System.out** refers to standard output stream, which is console

by default.

 **System.in** refers to standard input stream, which is keyboard by

default.

 **System.err** refers to standard error stream, which is console by

default.

 System.in is of type InputStream. System.out and System.err

are objects of type PrintStream.

**Reader Class**

Reader is an **abstract** class in **java**. **io** package. This class provides most fundamental methods related to reading data from a text

stream.

**Method**

**Meaning**

int read()

Reads a character. Returns -1 on EOF. It

returns Unicode of the character.

int read(char buf[]) Reads characters into the array. Returns the

number of bytes read. But *buf* may not be

filled completely, if end-of-file is encountered

before the array is filled.

long skip(long n)

Skips the specified number of characters.

void close()

Closes the stream.

boolean

Returns true if stream supports mark

markSupported()

operation. Used to check whether stream

supports marking.

void mark

Mark the present position in the stream.

(int readAheadLimit) Parameter *readaheadlimit* specifies the

number of characters that may be read while

still preserving the mark.

void reset()

If the stream has been marked, it attempts to

reposition it at the mark.

Srikanth Technologies

Java Student’s Guide - Library-II

5

**FileReader class**

 **FileReader** class is a subclass of **InputStreamReader** class,

which is subclass of **Reader** class. Its constructor takes name of

the file to be opened.

 It is used to read characters from a file. File may be given either

as a string or as an object of **File** class.

FileReader(File file)

FileReader(String fileName)

The following program takes filename from user and displays its

content on the screen.

01: import java.io.FileReader;

02: import java.util.Scanner;

03:

04: public class ReadFile {

05: public static void main(String args[]){

06: try {

07: Scanner s = new Scanner(System.in);

08: System.out.println("Enter filename :");

09: String filename = s.nextLine();

10: FileReader fr = new FileReader(filename);

11: int ch; // must be an int as read() returns int

12: ch = fr.read(); // returns -1 on EOF

13: while ( ch != -1) {

14: System.out.print((char)ch);

15: ch = fr.read();

16: }

17: fr.close();

18: }

19: catch(Exception ex) {

20: System.out.println(ex.getMessage());

21: }

22: } // end of main

23: } // end of class

**Exercise**: Count number of words in a given file.

Srikanth Technologies

Java Student’s Guide - Library-II

6

**BufferedReader Class**

 It improves performance by buffering characters so as to provide

efficient reading of characters.

 It is derived from **Reader** class.

 Buffer size may be specified using parameter to constructor or

default size may be used.

[BufferedReader(](BufferedReader.html_BufferedReader(java.io.Reader))[Reader](../word%20documents/jdk1.4/docs/api/java/io/Reader.html) in *)*

[BufferedReader(](BufferedReader.html_BufferedReader(java.io.Reader,%20int))[Reader](../word%20documents/jdk1.4/docs/api/java/io/Reader.html) in, int buffersize)

**readLine() method**

It reads a line of text from the Reader provided as parameter to

constructor. A line is considered to be terminated by linefeed (ASCII

code 10) or carriage return (ASCII code 13) or by both.

It returns **null** on end-of-file (EOF).

01: import java.io.*;

02: public class LineRead {

03: public static void main(String args[])

04: throws Exception {

05: FileReader fr = new FileReader("c:\\names.txt");

06: BufferedReader br = new BufferedReader(fr);

07:

08: String line;

09: line = br.readLine();

10: while( line !=null) {

11: System.out.println(line);

12: line = br.readLine();

13: }

14: br.close();

15: fr.close();

16: } // end of main

17: } // end of class

**Exercise**: Accept a filename, a string and display all lines in the file

that contain the given string.

Srikanth Technologies

Java Student’s Guide - Library-II

7

**InputStreamReader class**

 This class is used as a bridge between byte stream and character

stream.

 It reads data from **InputStream**, which is passed as parameter

to its constructor, and provides them in the form of characters as

it is derived from **Reader** class.

InputStreamReader(InputStream source)

 It can be used to convert **System**. **in**, which is of type

**InputStream,** as a **Reader**. Once System.in is converted to

Reader, it can be passed to **BufferedReader** to read one line at

a time.

// read a line from keyboard

Reader r = new InputStreamReader (System.in);

BufferedReader br = new BufferedReader(r);

String line = br.readLine();

**NOTE: InputStreamReader** is a sub class of **Reader** class. So an

object of **InputStreamReader** can be passed wherever a **Reader**

is expected.

**LineNumberReader class**

This class extends **BufferedReader** and provides methods to get

and set line numbers.

LineNumberReader(Reader)

int getLineNumber()

void setLineNumber(int)

**Exercise**: Display only non-blank lines of the given file along with

line numbers.

Srikanth Technologies

Java Student’s Guide - Library-II

8

**Reader**

**BufferedReader**

**FilterReader**

**InputStreamReader**

**StringReader**

**LineNumberReader**

**PushBackReader**

**FileReader**

**PushbackReader class – unread data**

 This class allows you to push back a character after reading it

from the stream.

 This is a **FilterReader**, which provides additional functionality to

base stream from where it takes data.

PushbackReader(Reader)

void unread(int c)

The following program demonstrates how to use **PushbackReader**

to unread a character.

Srikanth Technologies

Java Student’s Guide - Library-II

9

01: import java.io.*;

02: public class PushbackDemo {

03: public static void main(String[] args)

04:

throws Exception {

05: // Stream is built with a string

06: StringReader sr = new StringReader("ABC XYZ");

07: // create a PushbackReader using a StringReader

08: PushbackReader pbr = new PushbackReader(sr);

09: // read a character - A

10: int ch = pbr.read();

11: System.out.println(ch); // outputs 65

12: // push character back - A

13: pbr.unread(ch);

14: //read character pushed by previous unread()-A

15: System.out.println( pbr.read()); // outputs 65

16: }

17: }

**Automatic Resource Management (ARM)**

 Starting from Java 7.0 resources are automatically closed by

calling **close**() method at the end of try block.

 This feature is also called as **try-with-resources**.

 Prior to Java 7.0, closing of a resource was done explicitly in

finally block.

 All resources like Database connections and file streams are

expected to implement **AutoCloseable** interface and define

**close**() method, which is the only method in the interface, so

that Java invokes that method.

try (resources creation)

{

// process resource

}

catch(..) {

// handle exceptions

}

Srikanth Technologies

Java Student’s Guide - Library-II

10

**Writer class**

This is an abstract class for writing characters to a stream. It allows

either writing individual characters or strings. But, while writing

strings you have to write new line (\n) character explicitly.

**Method**

**Meaning**

void close()

Closes the stream, flushing it first.

void flush()

Writes pending data to stream.

void write(int c)

Writes a single character.

void write(String str) Writes a string.

In order to improve the performance of writing, data written to a

stream from the program is first held in a **buffer** and then the

content of the buffer is written to stream.

The following are the cases in which the buffer is written to stream:

 When buffer is filled.

 When stream is closed.

 When **flush**() method is called.

**FileWriter class**

 Used to write characters to a stream that is connected to a file.

 **FileWriter** is derived from **OutputStreamWriter**, which is

derived from **Writer**.

FileWriter(File file)

FileWriter(File file, boolean append)

FileWriter(String fileName)

FileWriter(String fileName, boolean append)

If **append** is true, then output is added to the end of the file.

Srikanth Technologies

Java Student’s Guide - Library-II

11

**Writer**

**BufferedWriter PrintWriter FilterWriter OutputStreamWriter StringWriter**

**FileWriter**

The following program reads data from source file and writes it into

target file after converting each line to uppercase.

01: import java.io.BufferedReader;

02: import java.io.FileReader;

03: import java.io.FileWriter;

04: import java.util.Scanner;

05:

06: public class ConvertToUpper {

07: public static void main(String[] args) {

08:

Scanner s = new Scanner(System.in);

09:

System.out.println("Enter source filename :");

10:

String srcfile = s.nextLine();

11:

System.out.println("Enter target filename :");

12:

String trgfile = s.nextLine();

13:

14:

try (FileReader fr = new FileReader(srcfile);

15:

FileWriter fw = new FileWriter(trgfile)) {

16:

BufferedReader br=new BufferedReader(fr);

17:

String line;

18:

line = br.readLine();

Srikanth Technologies

Java Student’s Guide - Library-II

12

19:

while (line != null) {

20:

fw.write(line.toUpperCase() + "\n");

21:

line = br.readLine();

22:

}

23:

} catch (Exception ex) {

24:

ex.printStackTrace();

25:

}

26: }

27: }

**PrintWriter Class**

 Prints the given data after formatting it to a text-output stream.

This class implements all the print methods found in

**PrintStream**.

 Methods in this class never throw I/O exceptions. The client may

inquire as to whether any errors have occurred by invoking

**checkError**() method.

PrintWriter(OutputStream out)

PrintWriter(OutputStream out, boolean autoFlush)

PrintWriter(Writer out)

PrintWriter(Writer out, boolean autoFlush)

**AutoFlush** parameter specifies whether output is to be

automatically flushed when a newline (\n) character is written.

**Method**

**Meaning**

void print(value)

Prints the given value to the stream.

void println(value) Prints the given value along with new line.

**RandomAccessFile Class**

 Represents random access file, where you can read and write

data from anywhere in the stream.

 RandomAccessFile writes data in binary format. When you write

an integer, it writes the memory image of integer as-it-is into

file. So it writes 4 bytes for an integer, irrespective of the actual

value.

Srikanth Technologies

Java Student’s Guide - Library-II

13

 Implements **DataInput** and **DataOutput** interfaces, which

contain methods to read and write primitive types from and to

stream.

 Allows pointer to be placed at a specific position using offset (in

bytes) from the beginning of the file.

RandomAccessFile (String name, String mode)

RandomAccessFile (File obj, String mode)

**Mode** may be either **"r"** for reading or **"rw"** for read and write.

**Method**

**Meaning**

long length()

Returns the length of this file.

type read<type>()

Reads the specified value. <type> is one

of the primitive types such as int, long

etc.

void seek(long pos)

Sets the pointer to the specified location.

The *pos* is number of bytes from the

beginning of the file.

void write<type>(value) Writes the specified value. <type> is one

of the primitive types.

The following example shows how to use random access file to write

an array of integers into a file and then read the numbers randomly.

01: import java.io.RandomAccessFile;

02: public class RandomAccessDemo {

03: public static void main(String[] args)

04: throws Exception {

05: int phonenumbers[]={1111111,2222222,3333333,444444};

06: RandomAccessFile raf = new RandomAccessFile

07: ("c:\\java\\numbers.dat","rw");

08: // write numbers into file

09: for(int n : phonenumbers)

10: raf.writeInt(n);

11: // read numbers from file

12: raf.seek(0); // start at the beginning

13: int count =(int) raf.length() / 4 ;

14:

Srikanth Technologies

Java Student’s Guide - Library-II

14

15: for(int i = 0 ; i < count ; i ++ )

16: System.out.println( raf.readInt());

17:

18: // modify a number in the file

19: raf.seek(2 * 4); // go to third number

20: raf.writeInt(9999999); // write new number

21:

22: // display numbers once again

23: raf.seek(0);

24: for(int i = 0 ; i < count ; i ++ )

25: System.out.println( raf.readInt());

26: }

27: }

**File class**

 Represents a file or directory in file system.

 The file or directory may not be present physically.

 Provides methods to get information about the absolute

pathname.

 Contains methods to create, delete, and rename files and

directories.

[File(](File.html_File(java.lang.String))[String](../word%20documents/jdk1.4/docs/api/java/lang/String.html) pathname) File(String parent, String child)

File(File parent, String child)

Constructor is used to create a new **File** instance by converting the

given pathname or parent and child names into an abstract

pathname.

**Method**

**Meaning**

boolean [canRead()](File.html_canRead())

Tests whether the application can read the

file.

boolean [canWrite()](File.html_canWrite())

Tests whether the application can modify the

file.

boolean

Automatically creates a new, empty file

[createNewFile()](File.html_createNewFile())

named by this abstract pathname, if and only

if a file with this name does not yet exist.

Srikanth Technologies

Java Student’s Guide - Library-II

15

boolean [delete()](File.html_delete())

Deletes the file or directory denoted by this

abstract pathname.

boolean [exists()](File.html_exists())

Tests whether the file denoted by this

abstract pathname exists.

[String](../word%20documents/jdk1.4/docs/api/java/lang/String.html)

Returns the absolute pathname.

[getAbsolutePath()](File.html_getAbsolutePath())

[String](../word%20documents/jdk1.4/docs/api/java/lang/String.html) [getName()](File.html_getName())

Returns the name of the file or directory.

[String](../word%20documents/jdk1.4/docs/api/java/lang/String.html) [getParent()](File.html_getParent())

Returns the pathname string of this abstract

pathname's parent, or null if this pathname

does not name a parent directory.

boolean [isAbsolute()](File.html_isAbsolute()) Tests whether this abstract pathname is absolute.

boolean

Tests whether the pathname is a directory.

[isDirectory()](File.html_isDirectory())

boolean [isFile()](File.html_isFile())

Tests whether the pathname is a normal file.

boolean [isHidden()](File.html_isHidden())

Tests whether the file is a hidden file.

long [lastModified()](File.html_lastModified())

Returns the time that the file was last

modified.

long [length()](File.html_length())

Returns the length of the file denoted by

pathname.

[File[]](../word%20documents/jdk1.4/docs/api/java/io/File.html) [listFiles()](File.html_listFiles())

Returns an array of pathnames denoting the

files in the directory.

boolean [mkdir()](File.html_mkdir())

Creates the directory named by the

pathname.

boolean

Renames the file denoted by this abstract

[renameTo(](File.html_renameTo(java.io.File))[File](../word%20documents/jdk1.4/docs/api/java/io/File.html) dest) pathname.

long getTotalSpace() Returns total size in bytes for the given drive

or partition.

long

Returns the number of bytes available in the

getUsableSpace()

given partition or drive.

**Exercise**: Accept path from user and display list of files from the

given path.

Srikanth Technologies

Java Student’s Guide - Library-II

16

**Files class**

 It consists exclusively of static methods that operate on files,

directories, or other types of files.

 It is part of **java.nio.file** package, which was introduced in Java

7.0.

**Method**

**Description**

Path copy(Path source, Path

Copy a file to a target file.

target, CopyOption... options)

void delete(Path path)

Deletes a file.

boolean deleteIfExists(Path path)

Deletes a file if it exists.

boolean isDirectory(Path path,

Tests whether a file is a

LinkOption... options)

directory.

Path move(Path source, Path

Move or rename a file to a

target, CopyOption... options)

target file.

DirectoryStream<Path>

Opens a directory, returning a

newDirectoryStream(Path dir)

DirectoryStream to iterate over

all entries in the directory.

String probeContentType(Path

Probes the content type of a

path)

file.

List<String> readAllLines(Path

Reads all lines from a file.

path, Charset cs)

long size(Path path)

Returns the size of a file (in

bytes).

Path walkFileTree(Path start,

Walks a file tree.

FileVisitor<? super Path> visitor)

**Path interface**

 A Path object represents a path that is hierarchical and

composed of a sequence of directory and file name elements

separated by a special separator or delimiter.

 The [**toPath**](http://docs.oracle.com/javase/7/docs/api/java/io/File.html#toPath()) method may be used to obtain a Path from the abstract path name represented by a java.io.File object.

Srikanth Technologies

Java Student’s Guide - Library-II

17

**Method**

**Description**

Path getFileName()

Returns the name of the file or

directory denoted by this path as a

Path object.

FileSystem getFileSystem() Returns the file system that created

this object.

Path getName(int index)

Returns a name element of this path

as a Path object.

int getNameCount()

Returns the number of name elements

in the path.

Path getParent()

Returns the parent path, or null if this

path does not have a parent.

Iterator<Path>iterator()

Returns an iterator over the name

elements of this path.

WatchKey register

Registers the file located by this path

(WatchService watcher,

with a watch service.

WatchEvent.Kind<?>...

events)

Path toAbsolutePath()

Returns a Path object representing the

absolute path of this path.

File toFile()

Returns a File object representing this

path.

URI toUri()

Returns a URI to represent this path.

**Paths class**

This class consists exclusively of static methods that return

a [Path](http://docs.oracle.com/javase/7/docs/api/java/nio/file/Path.html) by converting a path string or [URI.](http://docs.oracle.com/javase/7/docs/api/java/net/URI.html)

**Method**

**Meaning**

[Path](http://docs.oracle.com/javase/7/docs/api/java/nio/file/Path.html) get [(String](http://docs.oracle.com/javase/7/docs/api/java/lang/String.html) first, Converts a path string, or a sequence of

[String...](http://docs.oracle.com/javase/7/docs/api/java/lang/String.html) more) strings that when joined form a path

string, to a Path.

[Path](http://docs.oracle.com/javase/7/docs/api/java/nio/file/Path.html) [get(](http://docs.oracle.com/javase/7/docs/api/java/nio/file/Paths.html#get(java.net.URI))[URI](http://docs.oracle.com/javase/7/docs/api/java/net/URI.html) uri) Converts the given URI to a [Path](http://docs.oracle.com/javase/7/docs/api/java/nio/file/Path.html) object.

Srikanth Technologies

Java Student’s Guide - Library-II

18

**Removing blank lines from a File**

The following program is used to remove blank lines from a file. At

the end of the process, the given source file should not have any

blank lines. In order to achieve that, we adopt the following

algorithm:

 Open source file using BufferedReader.

 Create a temporary target file using FileWriter.

 Read a line from source file. If it is not blank line then write it

into target file.

 At the end, close both source and target files.

 Move target file to source file.

01: import java.io.*;

02: import java.nio.file.*;

03: import java.util.Scanner;

04: public class RemoveBlankLines {

05: public static void main(String args[])

06: throws Exception{

07: Scanner s = new Scanner(System.in);

08: System.out.println("Enter Source Filename : ");

09: String srcfile = s.nextLine();

10: Path src = Paths.get(srcfile);

11: BufferedReader br=Files.newBufferedReader(src);

12:

13: Path trg = Paths.get("tempfile.txt");

14: BufferedWriter bw = Files.newBufferedWriter

15: (trg,StandardOpenOption.CREATE);

16:

17: String line;

18: line = br.readLine();

19: while( line != null) {

20: if ( line.length() > 0 ) // non blank line

21: bw.write(line + "\n" );

22: line = br.readLine();

23: }

24: bw.close();

25: br.close();

26: Files.move(trg,src,

27: StandardCopyOption.REPLACE_EXISTING);

28: }

29: }

Srikanth Technologies

Java Student’s Guide - Library-II

19

**SimpleFileVisitor<T> class**

It provides the default behavior to visit all files and to re-throw I/O

errors. It implements **FileVisitor** interface.

**Method**

**Meaning**

[FileVisitResult](http://docs.oracle.com/javase/7/docs/api/java/nio/file/FileVisitResult.html)

Invoked for a directory after entries

[postVisitDirectory](http://docs.oracle.com/javase/7/docs/api/java/nio/file/SimpleFileVisitor.html#postVisitDirectory(T,%20java.io.IOException))

in the directory, and all of their

[(T](http://docs.oracle.com/javase/7/docs/api/java/nio/file/SimpleFileVisitor.html) dir, [IOException](http://docs.oracle.com/javase/7/docs/api/java/io/IOException.html) exc) descendants, have been visited.

[FileVisitResult](http://docs.oracle.com/javase/7/docs/api/java/nio/file/FileVisitResult.html)

Invoked for a directory before entries

[preVisitDirectory(](http://docs.oracle.com/javase/7/docs/api/java/nio/file/SimpleFileVisitor.html#preVisitDirectory(T,%20java.nio.file.attribute.BasicFileAttributes))[T](http://docs.oracle.com/javase/7/docs/api/java/nio/file/SimpleFileVisitor.html) dir, in the directory are visited.

[BasicFileAttributes](http://docs.oracle.com/javase/7/docs/api/java/nio/file/attribute/BasicFileAttributes.html) attrs)

[FileVisitResult](http://docs.oracle.com/javase/7/docs/api/java/nio/file/FileVisitResult.html) [visitFile(](http://docs.oracle.com/javase/7/docs/api/java/nio/file/SimpleFileVisitor.html#visitFile(T,%20java.nio.file.attribute.BasicFileAttributes))[T](http://docs.oracle.com/javase/7/docs/api/java/nio/file/SimpleFileVisitor.html) file, Invoked for a file in a directory.

[BasicFileAttributes](http://docs.oracle.com/javase/7/docs/api/java/nio/file/attribute/BasicFileAttributes.html) attrs)

[FileVisitResult](http://docs.oracle.com/javase/7/docs/api/java/nio/file/FileVisitResult.html) [visitFileFailed](http://docs.oracle.com/javase/7/docs/api/java/nio/file/SimpleFileVisitor.html#visitFileFailed(T,%20java.io.IOException))

Invoked for a file that could not be

[(T](http://docs.oracle.com/javase/7/docs/api/java/nio/file/SimpleFileVisitor.html) file, [IOException](http://docs.oracle.com/javase/7/docs/api/java/io/IOException.html) exc) visited.

The following program displays all .java files starting from the

directory - **c:\jdk8**.

01: import java.nio.file.*;

02: import java.nio.file.attribute.BasicFileAttributes;

03: import static java.nio.file.FileVisitResult.CONTINUE;

04: public class PrintJavaPrograms {

05: public static void main(String[] args)

06: throws Exception {

07: Path p = Paths.get("c:\\jdk8");

08: Files. **walkFileTree**(p, new ProcessFile());

09: }

10: }

11:

12: class ProcessFile extends SimpleFileVisitor<Path> {

13: @Override

14: public FileVisitResult visitFile

15: (Path file, BasicFileAttributes attr) {

16: if ( file.toString().endsWith(".java"))

17: System.out.println(file);

18: return CONTINUE;

19: }

20: }

Srikanth Technologies

Java Student’s Guide - Library-II

20

## SERIALIZATION

 Serialization is the process of writing the state of an object

(values of instance variables) to a byte stream.

 Serialization allows object data to be stored on disk and later

retrieved using deserialization process.

 Serialization is also used in distributed applications to send and

receive object data across network from one system to another –

for example it is used in RMI (Remote Method Invocation).

**Serializable Interface**

In order to serialize an object of a class, the class must implement

**Serializable** interface. Serializable is a null interface – an interface

with no methods. By implementing Serializable interface, a class

informs to Java that objects of the class can be serialized.

**ObjectOutput and ObjectInput Interfaces**

**ObjectOutput** interface extends **DataOutput** interface and

supports object serialization by providing **writeObject**() method.

**ObjectInput** interface extends **DataInput** interface and supports

object deserialization using **readObject**() method.

**ObjectOutputStream and ObjectInputStream Classes**

*ObjectOutputStream* class implements *ObjectOutput* interface and

extends *OutputStream* class.

*ObjectInputStream* class implements *ObjectInput* interface and

extends *InputStream* class.

The following are the constructors of these classes:

ObjectOutputStream (OutputStream)

ObjectInputStream (InputStream)

*OutputStream* is the stream to which object data is to be written

and *InputStream* is the stream from where object data is to be read.

Srikanth Technologies

Java Student’s Guide - Library-II

21

01: import java.io.Serializable;

02: class Person implements Serializable {

03: private String name,email;

04: public Person(String name, String email) {

05: this.name = name;

06: this.email = email;

07: }

08: public String toString() {

09: return name + "," + email;

10: }

11: }

01: import java.io.*;

02: public class SerializeObject {

03: public static void main(String ...args) {

04: Person p=new Person("Sri","sri@gmail.com");

05: try (FileOutputStream output =

06: new FileOutputStream("srikanth.dat")){

07: ObjectOutputStream outstream =

08: new ObjectOutputStream(output);

09: outstream.writeObject(p);

10: }

11: catch(Exception ex){

12: System.out.println(ex);

13: }

14: }

15: }

Srikanth Technologies

![](index-176_1.jpg)

Java Student’s Guide - Library-II

22

01: import java.io.FileInputStream;

02: import java.io.ObjectInputStream;

03: public class DeserializeObject {

04: public static void main(String[] args){

05: // deserialize the object

06: try (FileInputStream input =

07: new FileInputStream("srikanth.dat")) {

08: ObjectInputStream instream =

09: new ObjectInputStream(input);

10: // read object from stream and cast to Person

11: Person p = (Person) instream.readObject();

12: System.out.println(p.toString());

13: }

14: catch(Exception ex){

15: System.out.println(ex);

16: }

17: }

18: }

Srikanth Technologies

Java Student’s Guide - Library-II

23

**Char Streams vs. Byte Streams**

The following table shows character streams and their corresponding

byte streams.

**Character Stream**

**Byte Stream**

Reader

InputStream

Writer

OutputStream

FileReader

FileInputStream

FileWriter

FileOutputStream

BufferedReader

BufferedInputStream

BufferedWriter

BufferedOutputStream

PrintWriter

PrintStream

FilterReader

FilterInputStream

LineNumberReader

LineNumberInputStream

PushbackReader

PushbackInputStream

Srikanth Technologies

Java Student’s Guide - Library-II

24

## NETWORKING

 Java provides classes which allow you to program internet or

TCP/IP network.

 All classes are made available through **java.net** package.

 Data transfer between Java programs, running on different

systems, is done using IO streams.

 Server can use Multi-threading to handle multiple clients at the

same time.

**Socket programming**

 Sockets enable communication between two programs running in

the same JVM or different JVMs.

 Server socket is associated with a number called **port** number.

 In order to access a server socket, client socket has to provide

the name of machine on which server socket runs and the port

number at which server socket listens.

 Port number is an integer to uniquely identify each server socket

on a system. Name of the system and port number uniquely

identify a server socket in a network.

 Once you establish a connection with socket, you can take

**InputStream** to read data from socket and **OutputStream** to

write data to socket.

**Port=100**

**Host=“server”**

**Port=100**

**Server**

**Connection**

**Client**

**Socket**

**Socket**

Srikanth Technologies

Java Student’s Guide - Library-II

25

The following table shows some of the common internet applications

and their port numbers.

**Port Application/Protocol**

21

File Transfer Protocol(FTP)

23

Telnet Protocol

25

Simple Mail Transfer Protocol(SMTP)

80

Hypertext Transfer Protocol(HTTP)

110 Post office protocol (POP3)

**Socket Class**

 Socket class represents a client socket. A client socket connects

to a server socket, which is created using **ServerSocket** class.

 Connect to a server socket by specifying the name of the

computer and port number of server socket.

 Address of server is specified either by using IP address or the

name of the computer.

Socket(InetAddress address, int port)

Socket(String host, int port)

**Method**

**Meaning**

void close()

Closes this socket.

InetAddress

Returns the address of the machine to which

getInetAddress()

the socket is connected.

InputStream

Returns an input stream for this socket.

getInputStream()

OutputStream

Returns an output stream for this socket.

getOutputStream()

int getPort()

Returns the remote port to which this socket

is connected.

Srikanth Technologies

Java Student’s Guide - Library-II

26

**ServerSocket Class**

 Creates a server socket with the given port number.

 A server socket waits for a request to come from clients and

processes the requests.

ServerSocket(int port)

ServerSocket(int port, int queuelength)

**Port** specifies the port number at which server socket listens.

**Queuelength** specifies maximum number of clients that can wait

while socket is busy.

**Method**

**Meaning**

Socket accept()

Waits for a request and returns client socket.

void close()

Closes this socket.

InetAddress

Returns the local address of this server socket.

getInetAddress()

int getLocalPort() Returns the port on which this socket is

listening.

The following program creates a server socket that waits for a

request to come from client and sends system date and time back to

client.

01: import java.io.PrintWriter;

02: import java.net.*;

03: import java.util.Date;

04: public class TimeServer {

05: public static void main(String args[])

06: throws Exception {

07: ServerSocket ss = new ServerSocket(2000);

08: System.out.println("TimeServer is ready...");

09: while (true) {

10: Socket cs = ss.accept(); // wait for client

11: PrintWriter pw = new PrintWriter

12: (cs.getOutputStream(), true);

13: pw.println(new Date().toString()); //to client

14: } // end of while

15: } // end of main

Srikanth Technologies

Java Student’s Guide - Library-II

27

16: } // end of class

The following program connects to server socket – TimeServer and

then reads the data sent from server.

01: import java.io.InputStream;

02: import java.net.Socket;

03: import java.util.Scanner;

04: public class TimeClient {

05: public static void main(String[] args)

06: throws Exception {

07: // connect to server at port number 2000

08: Socket cs=new Socket("localhost",2000);

09: // get stream to read data from server

10: InputStream is = cs.getInputStream();

11: // Use Scanner to read a line

12: Scanner scanner = new Scanner(is);

13: String line = scanner.nextLine();

14: System.out.println(line);

15: }

16: }

**Handling multiple clients using Multithreading**

The above server socket handles one client at a time. When a server

socket has to handle multiple clients at the same time, it has to

create multiple threads – one for each client.

The following picture shows how a single Server socket creates

multiple threads to handle multiple clients concurrently.

The following program creates a server socket to receive request

from client. Upon receiving a request for connection from client,

server creates a new thread and makes the thread handle the

communication with client.

Srikanth Technologies

Java Student’s Guide - Library-II

28

**Server**

**Socket**

**1: Connect**

**Client**

**Socket-1**

**2 : Create**

**Thread**

**Client**

**Thread-1**

**Socket-2**

**Thread-2**

**3: Thread to**

**deal with client.**

01: import java.io.PrintWriter;

02: import java.net.*;

03: import java.util.Scanner;

04: import java.util.concurrent.ExecutorService;

05: import java.util.concurrent.Executors;

06:

07: public class MultiThreadedBookServer {

08: public static void main(String args[])

09: throws Exception {

10: ServerSocket ssocket = new ServerSocket(3000, 10);

11: System.out.println("Book server is ready!");

12: // create a Thread Pool to handle clients

13: ExecutorService executor =

14: Executors.newFixedThreadPool(10);

15: while (true) {

16: Socket clientsocket = ssocket.accept();

17: System.out.println("Accepted Client Request...");

18: ClientHandler client=

19: new ClientHandler(clientsocket);

20: executor.execute(client);

21: } // while

22: } // main

23: } // end of class

24: class ClientHandler implements Runnable {

25: Socket client;

26: public ClientHandler(Socket client) {

Srikanth Technologies

Java Student’s Guide - Library-II

29

27: this.client = client;

28: }

29: public void run() {

30: String books[] = {"Java Complete Reference",

31: "Core Java Vol I & II", "Thinking in Java"};

32: try {

33: // read string from client

34: Scanner scanner=

35: new Scanner(client.getInputStream());

36: PrintWriter pw = new PrintWriter

37: (client.getOutputStream(), true);

38: int bookno;

39: String title;

40: while (true) {

41: bookno = scanner.nextInt();

42: //exit loop and thread if book number is 0

43: if (bookno == 0) {

44: break;

45: }

46: // check whether book number is valid

47: if (bookno - 1 < books.length) {

48: title = books[bookno - 1];

49: } else {

50: title = ""; // book not found

51: }

52: // send title back to client

53: pw.println(title);

54: } // end of while

55: System.out.println("Client Connection Closed");

56: } catch (Exception ex) {

57: System.out.println(ex.getMessage());

58: }

59: } // end of run

60: } // end of class

The following is the client program for this server. Client program

takes book number from user and sends it to server socket. Client

receives book title sent from server and displays it to client.

Srikanth Technologies

Java Student’s Guide - Library-II

30

Corresponding thread on the server is terminated when **0** is passed

from client to server. Client is terminated when user enters **0** as

input.

01: import java.io.PrintWriter;

02: import java.net.Socket;

03: import java.util.Scanner;

04: public class BookClient {

05: public static void main(String args[])

06: throws Exception{

07: Socket s = new Socket("localhost", 3000);

08: Scanner keyboard = new Scanner(System.in);

09: Scanner sin = new Scanner(s.getInputStream());

10: PrintWriter sout =

11: new PrintWriter(s.getOutputStream(), true);

12: String title;

13: int bookno;

14: while (true) {

15: // take book no. from user

16: System.out.print("Enter book no.[0 to stop]:");

17: bookno = keyboard.nextInt();

18: sout.println(bookno); // send bookno to server

19: if (bookno == 0)

20: break;

21: title = sin.nextLine();

22: if (title.length() != 0) {

23: System.out.println("Book Title : " + title);

24: } else {

25: System.out.println("Invalid Book No.");

26: }

27: } // while

28: } // end of main

29: }

**InetAddress class**

 This class represents an IP address and domain name.

 InetAddress class has factory methods (static methods that

return instance of the class) which return an object of

InetAddress for the given name with the required details.

 Provides methods to get name and host address (IP address) of

a system.

Srikanth Technologies

Java Student’s Guide - Library-II

31

**Method**

**Meaning**

static InetAddress[]

Determines all the IP addresses of the

getAllByName (String

given host's name.

host)

static InetAddress

Determines the IP address of the given

getByName (String host)

host name.

String getHostAddress()

Returns the IP address string

"%d.%d.%d.%d".

String getHostName()

Returns the hostname for this address.

static InetAddress

Returns the local host.

getLocalHost()

The following program uses **InetAddress** class to get IP address of

the given domain name.

01: import java.net.*;

02: import java.io.*;

03: import java.util.Scanner;

04: public class GetIPAddresses {

05: public static void main(String args[])

06: throws Exception {

07: Scanner s = new Scanner(System.in);

08: String domainname;

09: while ( true) {

10: // read domain name

11: System.out.println("Enter Domain Name:");

12: domainname = s.nextLine();

13: // break loop if user enters end

14: if ( domainname.equals("end"))

15: break;

16: try {

17: // get IP addresses related to the given domain

18: InetAddress ips[]=

19: InetAddress.getAllByName(domainname);

20: // display ip addresses

21: System.out.println("IP Address(es)");

22: System.out.println("==============");

23:

24: for (InetAddress addr : ips)

Srikanth Technologies

Java Student’s Guide - Library-II

32

25: System.out.println( addr.getHostAddress());

26: }

27: catch(UnknownHostException ex) {

28: System.out.println("Sorry! Host Not Found");

29: }

30: } // end of while

31: System.out.println("Thank you!");

32: } // end of main

33: } // end of class

When you run the above program from a system that is connected

to Internet, the following will be the output.

Enter Domain Name:

www.srikanthtechnologies.com

IP Address(es)

==============

64.62.254.51

Enter Domain Name:

yahoo.com

IP Address(es)

==============

66.94.234.13

216.109.112.135

Enter Domain Name:

notfound.com

Sorry! Host Not Found

Enter Domain Name:

end

Thank you!

Srikanth Technologies

Java Student’s Guide - Library-II

33

**URL class**

 Represents a Uniform Resource Locator.

 URL is used to uniquely identify a resource in Internet or

network.

URL(String spec)

URL(String protocol, String host, String file)

URL(String protocol, String host, int port, String file)

A URL contains the following components:

**Protocol**

It represents protocol used to access the resource.

Common protocols are HTTP, FTP, File etc. Default

protocol is HTTP.

**Host**

Name of the system. System may be referred

either by name or by IP address.

**Port number** Port number of server socket to be accessed. If

none is given then port number 80 (http) is taken.

**File**

File to be accessed on the server. The path must

**Specification** be understood by the server processing the URL.

The following is an example of a complete URL. It has the following

components.

**http://www.srikanthtechnologies.com:80/aboutus.aspx**

The following are important methods of URL class:

**Method**

**Meaning**

boolean equals(Object obj)

Compares two URLs.

String getFile()

Returns the file name of this URL.

String getHost()

Returns the host name of this URL, if

applicable.

int getPort()

Returns the port number of this URL.

String getProtocol()

Returns the protocol name of this

URL.

URLConnection

Returns a URLConnection object that

Srikanth Technologies

Java Student’s Guide - Library-II

34

openConnection()

represents a connection to the remote

object referred to by the URL.

InputStream openStream() Opens a connection to this URL and

returns an InputStream.

The following program takes a URL and a filename from user and

copies the content of the URL into the given file.

It opens an input stream for given URL and reads one byte at a time

and writes it into target file.

01: import java.net.*;

02: import java.io.*;

03: import java.util.Scanner;

04:

05: class Download {

06: public static void main(String args[])

07: throws Exception {

08: // take input from user through keyboard

09: Scanner s = new Scanner(System.in);

10: System.out.print("Enter URL : ");

11: String fromurl = s.nextLine();

12: System.out.print("Enter filename : ");

13: String filename = s.nextLine();

14: URL urlobj = new URL(fromurl);

15: InputStream is = urlobj.openStream();

16: FileOutputStream fo =

17: new FileOutputStream( filename);

18: int ch = is.read();

19: while ( ch != -1) {

20: fo.write(ch);

21: ch = is.read();

22: }

23: fo.close();

24: is.close();

25: }

26: }

Srikanth Technologies

Java Student’s Guide - Library-II

35

## COLLECTIONS FRAMEWORK

Collections framework provides classes to implement useful data

structures (such as linked list) and algorithms (such as sorting). The

following are advantages of using Collections Framework:

 **Reduces programming effort** by providing useful data

structures like linked list and hash table, and algorithms like

searching and sorting, so that you don't have to write them

yourself. This saves a lot of programmer’s time allowing

programmer to spend more time on business logic and rules.

 **Increases performance** by providing high-performance

implementations of useful data structures and algorithms.

 **Reduces the effort required to learn APIs** by eliminating the

need to learn multiple ad hoc collection APIs.

The following are the core interfaces provided by Collections

Framework and their implementing classes (concrete classes):

**Interface Meaning**

**Implementing**

**classes**

Collection

Provides basic operations required to

a collection of objects.

Set

Extends Collection and provides

HashSet

unique set of values.

SortedSet Extends Set and ensures elements

TreeSet

are in sorted order.

List

Extends Collection and allows

ArrayList

elements to be accessed by position.

Vector

LinkedList

Map

Provides method to maintain a

HashMap

collection of pairs, where each pair

HashTable

contains a key and value.

SortedMap Extends Map interface and ensures

TreeMap

pairs are sorted on key.

Queue

Extends Collection and adds methods LinkedList

to insert, extract and inspect.

PriorityQueue

Srikanth Technologies

Java Student’s Guide - Library-II

36

**Collection Interface**

 This is the most basic interface. Contains methods to add,

remove, search and iterate over list.

 Provides methods that collection related classes should provide.

**Method**

**Meaning**

boolean add(Object)

Adds an object to collection.

boolean addAll

Adds all elements of the collection.

(Collection col)

void clear()

Clears all elements from the collection.

boolean contains

Returns true if the given object is found in

(Object obj)

the collection.

boolean containsAll

Returns true if all elements of parameter

(Collection col)

collection are present in the current

collection.

boolean isEmpty()

Returns true if collection is empty.

Iterator iterator()

Returns an iterator, which is used to iterate

over items of collection.

boolean remove

Removes the given object.

(Object obj)

boolean removeAll

Removes all elements from the collection

(Collection col)

that are present in parameter collection.

boolean retainAll

Retains only the elements in the list that are

(Collection col)

in the parameter collection.

int size()

Returns number of elements.

Object [] toArray()

Returns an array containing all the elements

of the collection.

boolean

Removes all elements that satisfy given

removeIf(Predicate)

predicate.

Stream<E> stream() Returns a sequential Stream.

Stream<E>

Returns a parallel Stream.

parallelStream()

**NOTE:** Methods **removeAll**(), **retainAll**(), **addAll**() return true if source list is changed as the result of the operation, otherwise they

return false.

Srikanth Technologies

Java Student’s Guide - Library-II

37

**NOTE:** Though by default, parameters are of type Object for many

methods, starting from Java 5.0, you can specify the type of objects

parameters must support using **generics** feature.

**List Interface**

 Extends **Collection** interface.

 An ordered collection (also known as a *sequence*).

 Allows elements to be accessed by their position (index).

 Classes ArrayList, LinkedList and Vector implement List interface.

**Method**

**Meaning**

void add (int index,

Inserts the given object at the

Object value)

specified position.

Object get(int index)

Returns object from the specified

position in this list.

int indexOf (Object value)

Returns the index of the first

occurrence of the specified object

or -1 if object is not found.

ListIterator listIterator()

Returns a list iterator of the

elements in this list.

Object set(int index, Object

Replaces the object at the

newvalue)

specified position with the new

object.

void

Replaces each element of the list

replaceAll(UnaryOperator<E>)

with the result of the operator.

void sort(Comparator)

Sorts the list according to order

induced by Comparator.

List<E> subList(int from, int to) Returns a list between from

(inclusive) and to (exclusive)

elements.

Object remove(int index)

Removes element at the specified

position.

Srikanth Technologies

Java Student’s Guide - Library-II

38

**ArrayList class**

 Implements **List** interface.

 Each **ArrayList** instance has a *capacity*. The capacity is the size

of the array used to store the elements in the list. It is always at

least as large as the list size. As elements are added to an

*ArrayList*, its capacity grows automatically.

 One of the constructors allows you to specify initial capacity of

the list.

ArrayList()

ArrayList(Collection c)

ArrayList(int initialCapacity)

**NOTE:** It is important for classes whose objects are used with

collections to override **equals**() method.

01: import java.util.*;

02: public class ArrayListDemo {

03: public static void main(String args[]) {

04: ArrayList nl = new ArrayList();

05: nl.add("Ronaldo");

06: nl.add("Messi");

07: nl.add("Gerrard");

08: nl.add(1,"Rooney");

09: // display the list

10: for ( Object obj : nl)

11: System.out.println(obj);

12:

13: nl.remove("Ronaldo");

14: System.out.println( nl.indexOf("Messi"));

15: }

16: }

Srikanth Technologies

Java Student’s Guide - Library-II

39

**Generics**

 Allow you to specify to compiler the type of object you want to

store in a collection.

 Generics make collection classes type-safe by ensuring a

collection supports only one type of objects.

 At the time of creating an object of a collection class, we can

specify which type of objects the collection supports.

 Eliminates the need to typecast the object taken from collection

– makes it convenient and faster.

01: // Code without Generics

02: ArrayList al = new ArrayList();

03: al.add("First");

04: al.add( new Integer(100));

05: String st;

06: st = (String) al.get(0); // typecasting is required

07: System.out.println(st.toUpperCase());

08: st = (String) al.get(1); // results in Exception

In the above code, when you try to typecast *al.get(1)* to *String*, it

results in **ClassCastException**, because *al.get(1)* actually refers to

an object of type *Integer* and it cannot be converted to *String*.

The following example demonstrates how generics make collections

type-safe and convenient to use.

01: // Code using Generics

02: ArrayList<String> al = new ArrayList<String>();

03: al.add("First");

04: //al.add( new Integer(100)); // compile-time error

05: al.add("Second");

06: String st;

07: st = al.get(0); // typecasting is NOT required

08: System.out.println(st.toUpperCase());

09: // can be used with enhanced for loop

10: for ( String s : al)

11: System.out.println( s.toLowerCase());

Srikanth Technologies

Java Student’s Guide - Library-II

40

Generics allow you to specify the type of object you want a data

structure like **ArrayList** to support. Compiler checks whether

objects used with ArrayList **al** are of type **String**.

If any other type of object other than **String** is used with **al** then it

is taken as a compile-time error.

**Set interface**

 **Set** interface represents a collection that contains no duplicate

elements.

 It extends **Collection** interface**.**

 This doesn’t add any new methods to *Collection* interface. A class

implementing Set interface must make sure the elements are

unique.

 **HashSet** and **LinkedHashSet** classes implement Set interface.

**HashSet Class**

 Implements the **Set** interface.

 It does not guarantee the order of elements.

[HashSet()](HashSet.html_HashSet())

[HashSet(](HashSet.html_HashSet(java.util.Collection))[Collection](../word%20documents/jdk1.4/docs/api/java/util/Collection.html) c) **NOTE:** Class **LinkedHashSet** is same as **HashSet** except that it

orders elements according to insertion order.

**NOTE:** For objects that are used with **HastSet, LinkedHashSet**

and **TreeSet**, it is important to override **hashCode**() method.

The following program demonstrates usage of **LinkedHashSet**. It

displays unique lines (ignoring duplicates) of a file.

Srikanth Technologies

Java Student’s Guide - Library-II

41

01: import java.io.*;

02: import java.util.*;

03: public class UniqueLines {

04: public static void main(String args[])

05: throws Exception {

06: BufferedReader br =

07: new BufferedReader(new FileReader("c:\\names.txt"));

08: LinkedHashSet<String> lhs = new LinkedHashSet();

09: String line;

10: while ( (line=br.readLine())!= null)

11: lhs.add(line);

12: br.close();

13: for ( String s : lhs)

14: System.out.println(s);

15: }

16: }

**SortedSet interface**

 SortedSet extends **Set** and ensures the elements are always in

the ascending order.

 It provides the following methods to retrieve elements from first,

last and subset from head, tail or middle**.**

 Class **TreeSet** implements **SortedSet** interface.

**Method**

**Meaning**

Object first()

Returns first value in the list.

Object last()

Returns last value in the list.

SortedSet headSet

Returns a list consisting of values that

(Object toElement)

are less than *toElement*.

SortedSet tailSet (Object Returns a list consisting of values that

fromElement)

are greater than or equal to

*fromElement*.

SortedSet subset (Object Returns a list consisting of values that

fromElement, Object

are from *fromElement*, inclusive, to

toElement)

*toElement*, exclusive.

The following program is to display only duplicated lines of the given

file.

Srikanth Technologies

Java Student’s Guide - Library-II

42

01: import java.io.BufferedReader;

02: import java.io.FileReader;

03: import java.util.ArrayList;

04: import java.util.LinkedHashSet;

05: import java.util.Scanner;

06: public class OnlyDuplicatedLines {

07: public static void main(String[] args) {

08: String filename;

09: System.out.print("Enter a filename : ");

10: Scanner s = new Scanner(System.in);

11: filename = s.nextLine();

12: ArrayList<String> lines = new ArrayList();

13: LinkedHashSet<String> duplines =

14: new LinkedHashSet();

15: try (BufferedReader br = new BufferedReader

16: (new FileReader(filename))) {

17: String line = br.readLine();

18: while (line != null) {

19: if(lines.contains(line)) //duplicated line

20: duplines.add(line);

21: else

22: lines.add(line);

23:

24: line = br.readLine();

25: } //while

26: } catch (Exception ex) {

27: System.out.println(ex);

28: }

29: // display duplicated lines

30: for (String line : duplines) {

31: System.out.println(line);

32: }

33: }

34: }

Srikanth Technologies

Java Student’s Guide - Library-II

43

**TreeSet Class**

 This class implements SortedSet interface.

 It is based on balanced tree data structure.

 Objects being used must be comparable (by implementing

**Comparable** interface, which contains **compareTo**() method).

TreeSet()

TreeSet(Comparator)

It ensures objects are sorted according to natural order. In case,

you specify *Comparator* (using second constructor) *,* which is an

object of a class that implements **Comparator** interface *,* the objects

are sorted according to order specified by *Comparator.*

01: public class Person

02: implements Comparable<Person>{

03: private String name;

04: private int age;

05: public Person(String name, int age) {

06: this.name = name;

07: this.age = age;

08: }

09: @Override

10: public boolean equals(Object obj) {

11: final Person other = (Person) obj;

12: if( this.name.equals(other.name) &&

13: this.age==other.age)

14: return true;

15: else

16: return false;

17: }

18: @Override

19: public int hashCode() {

20: return age;

21: }

22: @Override

23: public int compareTo(Person other) {

24: if (this.name.equals(other.name))

25: return this.age - other.age;

26: else

27: return this.name.compareTo(other.name);

Srikanth Technologies

Java Student’s Guide - Library-II

44

28: }

29: public String toString() {

30: return name + ":" + age;

31: }

32: }

01: import java.util.Scanner;

02: import java.util.TreeSet;

03: public class TreeSetDemo {

04: public static void main(String[] args) {

05: TreeSet<Person> persons = new TreeSet();

06: // take input from user

07: Scanner s = new Scanner(System.in);

08: String name;

09: int age;

10: while (true) {

11: System.out.print("Enter name[end to stop]:");

12: name = s.nextLine();

13: if (name.equals("end")) {

14: break;

15: }

16: System.out.print("Enter age :");

17: age = s.nextInt();

18:

19: Person p = new Person(name, age);

20: persons.add(p);

21: //remove extra characters in Scanner

22: s.nextLine();

23: } // while

24: // display persons

25: for(Person p : persons) {

26: System.out.println(p);

27: } // for

28: } // main()

29: } // class

Srikanth Technologies

Java Student’s Guide - Library-II

45

**Comparator Interface**

Comparator allows you to implement compare method so that

program can specify the precise order for sorting.

int compare(Object o1, Object o2)

The return value of **compare**() method must be one of the

following.

**Return value**

**What it means?**

Zero (0)

Both the objects are equal.

Greater than 0 (> 0)

First object is greater than second

object.

Less than 0 ( < 0 )

First object is less than second object.

**Queue interface**

 This interface extends Collection interface and provides methods

to add and retrieve values from queue.

 Classes **LinkedList** and **PriortyQueue** implement **Queue**

interface.

**Method**

**Meaning**

Object element() Retrieves, but does not remove, the head of the

queue. Throws exception –

NoSuchElementException – if queue is empty.

boolean offer

Inserts an element into queue, if possible.

(Object)

Object poll()

Retrieves and removes the head of the queue or

returns null if queue is empty.

Object remove() Retrieves and removes the head of this queue.

Throws exception if queue is empty.

Object peek()

Retrieves, but does not remove, the head of this

queue, returns null if this queue is empty.

Srikanth Technologies

Java Student’s Guide - Library-II

46

**LinkedList Class**

 Doubly-Linked list implementation of the List interface.

 Can be used as a stack, queue or double-ended queue (deque).

 Starting from Java 5.0, it implements Queue interface also.

 This implementation is not synchronized.

LinkedList()

LinkedList(Collection c)

Apart from methods in **List** and **Queue** interfaces, it provides the

following extra methods.

**Method**

**Meaning**

void addFirst(Object o) Inserts the given element at the beginning

of the list.

void addLast(Object o) Appends the given element to the end of

this list.

Object getFirst()

Returns the first element of this list.

Object getLast()

Returns the last element of this list.

Object removeFirst()

Removes and returns the first element

from this list.

Object removeLast()

Removes and returns the last element

from this list.

**NOTE:** Class **PriorityQueue** implements **Queue** interface and

orders elements by natural order. Elements of PriorityQueue must

be comparable – implement Comparable interface, which contains

**compareTo**() method.

Srikanth Technologies

Java Student’s Guide - Library-II

47

**Vector Class**

 Vector is one of the legacy classes but recreated to implement

**List** interface in version 1.2.

 It retained old methods of Vector class such as **addElement** ()

etc (see list below) and also provides methods of List interface.

 It is **synchronized**. It should be considered instead of ArrayList,

if multiple threads use a single vector.

Vector()

Vector(Object[])

Vector(Collection)

**Method**

**Meaning**

void addElement (Object

Add the component at the end of the

obj)

vector.

Object elementAt (int index) Return element at the given index.

void removeElementAt (int

Deletes the component at the

index)

specified index.

void insertElementAt (Object Inserts the specified object as a

obj, int index)

component in this vector at the

specified index.

void setElementAt (Object

Sets the component at the specified

obj, int index)

index to the specified object.

Enumeration elements()

Returns an enumeration of the

elements.

**Enumeration Interface**

 Allows you to access elements of a **Vector**.

 New implementations should consider using Iterator instead of

Enumeration.

**Method**

**Meaning**

boolean hasMoreElements()

Returns true if it contains more

elements.

Object nextElement()

Returns the next element of this

enumeration.

Srikanth Technologies

Java Student’s Guide - Library-II

48

<<interface>>

Col ection

<<interface>>

<<interface>>

Set

<<interface>>

Queue

List

<<interface>>

SortedSet

Vector

LinkedList

PriorityQueue

TreeSet

ArrayList

HashSet

**extends**

Stack

LinkedHashSet

**implements**

**Stack Class**

 Represents a last-in-first-out (LIFO) stack of objects.

 Extends **Vector** class and provides the following extra methods

related to stack.

**Method**

**Meaning**

boolean empty()

Tests if this stack is empty.

Object peek()

Returns the object at the top of this stack

without removing it.

Object pop()

Removes the object at the top of this stack

and returns that object.

Srikanth Technologies

Java Student’s Guide - Library-II

49

Object push(Object Pushes an item onto the top of this stack.

item)

int search(Object o) Returns the 1-based position where an object

is on this stack.

**Exercise**: Accept file name from user and display contents of file in

reverse order - first line last.

**Map Interface**

 Allows keys to map values.

 A map does not allow duplicate keys. Each key can map to at

most one value.

 **HashMap** and **HashTable** implement Map interface.

**Method**

**Meaning**

void clear()

Clears the map.

boolean containsKey(Object key) Returns true if the given key

exists.

Object get(Object key)

Returns the value of key.

boolean isEmpty()

Returns true if this map is empty.

Set keySet()

Returns a set view of the keys

contained in this map.

Object put (Object key, Object

Places the key and the value.

value)

Object remove (Object key)

Removes the mapping for this

key from this map if present.

boolean remove

Removes value for the key if it

(Object key, Object value)

contains the given value.

int size()

Returns the number of keys.

Collection values()

Returns a collection view of the

values contained in this map.

void forEach(BiConsumer<K,V>) Performs the given action for

each element.

V getOrDefault

Returns the value for key or

(Object key, V defaultValue)

*defaultValue* if key not found.

Srikanth Technologies

Java Student’s Guide - Library-II

50

V putIfAbsent(K key, V value)

If key is not associated with a

value then puts value and returns

null, else returns current value.

V replace(K key, V value)

Replaces value of given *key* to

*value*.

boolean replace

Replaces the value of key to new

(K key, V oldValue, V newValue) value if it contains old value

**HashMap class**

 This class implements **Map** interface

 It does not guarantee the order of keys.

HashMap()

HashMap(Map)

**NOTE**: **HashTable** class is same as **HashMap** class, but it is

synchronized. **LinkedHashMap** class extends **HashMap** class and

arranges keys in the order of insertion.

**SortedMap interface**

This interface extends Map interface to provide sorted keys. The

following are the methods that are added in **SortedMap** interface

compared with **Map** interface.

**Method**

**Meaning**

Object first()

Returns the first element.

Object last()

Returns the last element.

SortedSet headMap

Returns list up to the specified element

(Object toKey)

and not including it.

SortedSet tailMap (Object Returns list from the specified element

fromKey)

up to end of the list.

SortedSet subMap (object Returns list that contains elements from

fromKey, object toKey)

the given *fromKey* to *toKey* but not

including it.

Srikanth Technologies

Java Student’s Guide - Library-II

51

**TreeMap class**

 This class implements **SortedMap** interface. It arranges keys in

the sorted order.

 Order of keys is either natural order or specified by

**Comparator.**

TreeMap()

TreeMap(Comparator)

The following program uses HashMap, LinkedHashMap and TreeMap

to show the way these classes arrange keys.

01: import java.util.HashMap;

02: import java.util.LinkedHashMap;

03: import java.util.TreeMap;

04:

05: public class MapDemo {

06: public static void main(String[] args) {

07:

HashMap<String, String> hm = new HashMap<>();

08:

hm.put("java", "Language");

09:

hm.put("dotnet", "Framework");

10:

hm.put("c#", "Language");

11:

System.out.println("HashMap Output");

12:

for (String key : hm.keySet())

13: System.out.printf("%s:%s\n",key,hm.get(key));

14:

15:

// Arranges keys in insertion order

16:

LinkedHashMap<String,String> lhm

= new LinkedHashMap<>();

17:

lhm.put("java", "Language");

18:

lhm.put("dotnet", "Framework");

19:

lhm.put("c#", "Language");

20:

System.out.println("LinkedHashMap Output");

21:

for (String key : lhm.keySet())

22:

System.out.printf("%s:%s\n",key,lhm.get(key));

23:

24:

// Arranges keys in ascending order

25:

TreeMap<String, String> tm = new TreeMap<>();

26:

tm.put("java", "Language");

27:

tm.put("dotnet", "Framework");

28:

tm.put("c#", "Language");

Srikanth Technologies

Java Student’s Guide - Library-II

52

29:

System.out.println("TreeMap Output");

30:

for (String key : tm.keySet())

31:

System.out.printf("%s:%s\n",key,tm.get(key));

32: }

33: }

<<interface>>

Map

<<interface>>

SortedMap

HashTable

HashMap

**extends**

TreeMap

LinkedHashMap

**implements**

Srikanth Technologies

Java Student’s Guide - Library-II

53

**Properties class**

 Represents a persistent set of properties.

 Properties can be saved to a stream or loaded from a stream.

 Each key and its corresponding value in the property list is a

string.

 Properties class extends **HashTable** class

**Method**

**Meaning**

[String](file:///C:/jdk6.0/docs/api/java/lang/String.html)

Searches for the property with the

[getProperty(](file:///C:/jdk6.0/docs/api/java/util/Properties.html%23getProperty(java.lang.String))[String](file:///C:/jdk6.0/docs/api/java/lang/String.html) key) specified key in this property list.

void [list(](file:///C:/jdk6.0/docs/api/java/util/Properties.html%23list(java.io.PrintWriter))[PrintWriter](file:///C:/jdk6.0/docs/api/java/io/PrintWriter.html) out) Prints this property list out to the specified output stream.

void [load(](file:///C:/jdk6.0/docs/api/java/util/Properties.html%23load(java.io.Reader))[Reader](file:///C:/jdk6.0/docs/api/java/io/Reader.html) reader) Reads a property list (key and element pairs) from the input character stream in

a simple line-oriented format.

[Object](file:///C:/jdk6.0/docs/api/java/lang/Object.html) [setProperty](file:///C:/jdk6.0/docs/api/java/util/Properties.html%23setProperty(java.lang.String,%20java.lang.String))

Adds a new property.

[(String](file:///C:/jdk6.0/docs/api/java/lang/String.html) key, [String](file:///C:/jdk6.0/docs/api/java/lang/String.html) value) void [store(](file:///C:/jdk6.0/docs/api/java/util/Properties.html%23store(java.io.Writer,%20java.lang.String))[Writer](file:///C:/jdk6.0/docs/api/java/io/Writer.html) writer, Writes this property list (key and

[String](file:///C:/jdk6.0/docs/api/java/lang/String.html) comments)

element pairs) in this Properties table to

the output character stream in a format

suitable for using the [load](file:///C:/jdk6.0/docs/api/java/util/Properties.html%23load(java.io.Reader)) method.

01: import java.util.Properties;

02: import java.io.*;

03: public class PropertyDemo {

04: public static void main(String[] args)

05: throws Exception {

06: Properties p = new Properties();

07: p.setProperty("name","Srikanth");

08: p.setProperty("email","srikanth@gmail.com");

09: p.setProperty("phone","9059057000");

10: for( Object k : p.keySet())

11: System.out.printf("%s : %s\n", k, p.get(k) );

12:

13: p.store(new FileWriter("c:\\sri.properties"),

14: "Srikanth Details");

15: Properties p2= new Properties();

16: p2.load(new FileReader("c:\\sri.properties"));

17: for( Object k : p2.keySet())

Srikanth Technologies

Java Student’s Guide - Library-II

54

18: System.out.printf("%s : %s\n", k, p2.get(k) );

19: }

20: }

**Collections class**

 It contains a collection of static methods that operate on

collections provided as parameters of the collection.

 Implements various algorithms related to collections.

**Method**

**Meaning**

int binarySearch

Implements binary search

(List l, Object v)

algorithm to search.

void copy(List dest, List src)

Copies content of one list to

another.

void fill(List list, Object obj)

Fills the list with the given value.

Object max (Collection c)

Returns maximum value in

collection.

Object min (Collection c)

Returns minimum value in

collection.

void reverse(List l)

Reverses the list.

void shuffle(List l)

Shuffles the list with default

randomness.

void sort(List l)

Sorts the list.

void sort(List l, Comparator c) Sorts the list with the order

specified by Comparator.

Srikanth Technologies

Java Student’s Guide - Library-II

55

01: import java.util.*;

02: public class CollectionsDemo {

03: public static void main(String args[]) {

04: ArrayList<String> names = new ArrayList();

05: names.add("James Goodwill");

06: names.add("Jason Hunter");

07: names.add("Roman");

08: Collections.sort(names);

09: printList(names);

10: int pos=Collections.binarySearch(names,"Roman");

11: System.out.printf("Roman is found at : %d\n",pos);

12: System.out.printf("Maximum :%s\n",

13: Collections.max(names));

14: System.out.println("Reverse Order");

15: Collections.reverse(names);

16: printList(names);

17: }

18: public static void printList(List<String> list) {

19: for (String s : list) {

20: System.out.println(s);

21: }

22: }

23: }

Srikanth Technologies

Java Student’s Guide - Library-II

56

**Generic Methods**

 All generic method declarations have a type parameter

section delimited by angle brackets (< and >) that precedes the

method’s return type (<T> in this example).

 Note that type parameters can represent only reference types—

not primitive types (like int, double and char).

 Type parameter can be declared only once in the type parameter

section but can appear more than once in the method’s

parameter list.

**Bounded Type Parameter**

 To declare a bounded type parameter, list the type parameter's

name, followed by extends keyword, followed by upper bound.

 Note that, in this context, extends is used in a general sense to

mean either "extends" (as in classes) or "implements" (as in

interfaces).

01: import java.util.*;

02: public class GenericMethods {

03: public static **<T>** void print(T a[]) {

04: for(T v : a)

05:

System.out.println(v);

06: }

07: public static<T extends Comparable<T>>

08: boolean contains(T a[], T v){

09: for (T value: a)

10:

if (value.compareTo(v) == 0 )

11:

return true;

12: return false;

13: }

14: public static void main(String args[]) {

15: String names[]={"Steve","Joe","Bob","James"}; 16: print(names);

17: System.out.println( contains( names,"Joe"));

18: }

19: }

Srikanth Technologies

Java Student’s Guide - Library-II

57

## REGULAR EXPRESSIONS

 Regular expressions are a way to describe a set of strings based

on common characteristics shared by each string in the set.

 They can be used to search, edit, or manipulate text and data.

 You must learn a specific syntax to create regular expressions —

one that goes beyond the normal syntax of the Java

programming language.

**Character classes**

The following are the available character classes.

The left-hand column specifies the regular expression constructs,

while the right-hand column describes the conditions under which

each construct will match.

[abc]

a, b, or c (simple class)

[^abc]

Any character except a, b, or c (negation)

[a-zA-Z]

a through z, or A through Z, inclusive (range)

[a-z&&[^bc]]

a through z, except for b and c: [ad-z]

(subtraction)

[a-z&&[^m-p]]

a through z, and not m through p: [a-lq-z]

(subtraction)

**Predefined character classes**

The following are the predefined character classes.

.

Any character (may or may not match line terminators)

\d

A digit: [0-9]

\D A non-digit: [^0-9]

\s

A whitespace character: [ \t\n\x0B\f\r]

## \S

A non-whitespace character: [^\s]

\w A word character: [a-zA-Z_0-9]

\W A non-word character: [^\w]

Srikanth Technologies

Java Student’s Guide - Library-II

58

**Quantifiers**

The following are the available quantifiers.

X?

X, once or not at all

X*

X, zero or more times

X+

X, one or more times

X{n}

X, exactly n times

X{n,}

X, at least n times

X{n,m} X, at least n but not more than m times

**Pattern class**

 A Pattern object is a compiled representation of a regular

expression.

 The Pattern class provides no public constructors.

 To create a pattern, you must first invoke one of its public static

compile methods, which will then return a Pattern object.

 These methods accept a regular expression as the first

argument.

**Method**

**Meaning**

static Pattern

Compiles the given regular expression

compil[e(String](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/String.html) regex) into a pattern.

[Matcher](http://java.sun.com/j2se/1.4.2/docs/api/java/util/regex/Matcher.html) [matcher](http://java.sun.com/j2se/1.4.2/docs/api/java/util/regex/Pattern.html#matcher(java.lang.CharSequence))

Creates a matcher that will match the

[(CharSequence](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/CharSequence.html) input) given input against this pattern.

static boolean

Compiles the given regular expression

[matches(](http://java.sun.com/j2se/1.4.2/docs/api/java/util/regex/Pattern.html#matches(java.lang.String,%20java.lang.CharSequence))[String](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/String.html) regex, and attempts to match the given input

[CharSequence](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/CharSequence.html) input) against it.

[String](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/String.html) [pattern()](http://java.sun.com/j2se/1.4.2/docs/api/java/util/regex/Pattern.html#pattern())

Returns the regular expression from

which this pattern was compiled.

[String[]](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/String.html) [split](http://java.sun.com/j2se/1.4.2/docs/api/java/util/regex/Pattern.html#split(java.lang.CharSequence))

Splits the given input sequence around

[(CharSequence](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/CharSequence.html) input) matches of this pattern.

Srikanth Technologies

Java Student’s Guide - Library-II

59

01: import java.util.Scanner;

02: import java.util.regex.Pattern;

03: public class MobileNumber {

04: public static void main(String[] args) {

05: Scanner s = new Scanner(System.in);

06: System.out.print("Enter mobile number : ");

07: String mobile = s.nextLine();

08: // other way is: mobile.matches("^\\d{10}$")

09: if ( Pattern.matches("^\\d{10}$", mobile) )

10: System.out.println("Valid mobile number!");

11: else

12: System.out.println("Invalid mobile number!");

13: }

14: }

01: import java.util.regex.Pattern;

02: public class SplitDemo {

03: public static void main(String[] args) {

04: Pattern p = Pattern.compile("\\d");

05: String[] items=p.split("one9two4three7four1five");

06: for(String s : items)

07: System.out.println(s);

08: }

09: }

Srikanth Technologies

Java Student’s Guide - Library-II

60

**Matcher class**

 A Matcher object is the engine that interprets the pattern and

performs match operations against an input string.

 Like the Pattern class, Matcher defines no public constructors.

 You obtain a Matcher object by invoking the matcher method on

a Pattern object.

**Method**

**Meaning**

int [end()](http://java.sun.com/j2se/1.4.2/docs/api/java/util/regex/Matcher.html#end())

Returns the index of the last character

matched, plus one.

boolean [find()](http://java.sun.com/j2se/1.4.2/docs/api/java/util/regex/Matcher.html#find())

Attempts to find the next subsequence of the

input sequence that matches the pattern.

[String](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/String.html) [group()](http://java.sun.com/j2se/1.4.2/docs/api/java/util/regex/Matcher.html#group())

Returns the input subsequence matched by

the previous match.

boolean [matches()](http://java.sun.com/j2se/1.4.2/docs/api/java/util/regex/Matcher.html#matches())

Attempts to match the entire input sequence

against the pattern.

[Pattern](http://java.sun.com/j2se/1.4.2/docs/api/java/util/regex/Pattern.html) [pattern()](http://java.sun.com/j2se/1.4.2/docs/api/java/util/regex/Matcher.html#pattern())

Returns the pattern that is interpreted by

this matcher.

[String](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/String.html) [replaceAll](http://java.sun.com/j2se/1.4.2/docs/api/java/util/regex/Matcher.html#replaceAll(java.lang.String))

Replaces every subsequence of the input

[(String](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/String.html) replacement) sequence that matches the pattern with the given replacement string.

[String](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/String.html) [replaceFirst](http://java.sun.com/j2se/1.4.2/docs/api/java/util/regex/Matcher.html#replaceFirst(java.lang.String))

Replaces the first subsequence of the input

[(String](http://java.sun.com/j2se/1.4.2/docs/api/java/lang/String.html) replacement) sequence that matches the pattern with the given replacement string.

int [start()](http://java.sun.com/j2se/1.4.2/docs/api/java/util/regex/Matcher.html#start())

Returns the start index of the previous

match.

Srikanth Technologies

Java Student’s Guide - Library-II

61

01: import java.util.regex.*;

02: public class MatcherDemo {

03: public static void main(String[] args) {

04: Pattern p = Pattern.compile("[a-z]+");

05: Matcher m = p.matcher("123bbc4343pqr3433");

06: while(m.find()) {

07: System.out.println("start(): " + m.start());

08: System.out.println("end(): "+ m.end());

09: System.out.println("group(): " + m.group());

10: }

11: // pattern replacement

12: p = Pattern.compile("-+");

13: m = p.matcher("----12345----");

14: String output = m.replaceAll("*");

15: System.out.println(output);

16: }

17: }

start(): 3

end(): 6

group(): bbc

start(): 10

end(): 13

group(): pqr

*12345*

Srikanth Technologies

Java Student’s Guide - Library-II

62

## LAMBDA EXPRESSIONS

 Lambda expression allows functionality to be passed as

argument to a method.

 It is a replacement for Anonymous class that implements single

abstract method (SAM) interface – functional interface.

**Components of Lambda Expression**

 A comma-separated list of formal parameters enclosed in

parentheses.

 You can omit parentheses if there is only one parameter.

 The arrow token **->** also known as *lambda* *operator.*

 A body, which consists of a single expression or a statement

block.

 If you specify a single expression, then the Java runtime

evaluates the expression and then returns its value. No return

statement is required.

 Statement block must be enclosed in statements in braces ({}),

and must have a return statement.

**(parameters) -> expression**

(int n1, int n2) -> n1 > n2

(n1, n2) -> n1 > n2

01: interface Test {

02: boolean eval(int n1, int n2);

03: }

04: public class LambdaDemo1 {

05: public static void main(String[] args) {

06: // Old Anonymous inner class demo

07: Test t = new Test() {

08: @Override

09: public boolean eval(int n1, int n2) {

10: return n1 > n2;

11: }

12: };

13: System.out.println (t.eval(20,10));

14:

Srikanth Technologies

Java Student’s Guide - Library-II

63

15: // Lambda expression

16: Test t2 = (int n1, int n2) -> n1 > n2;

17: System.out.println (t2.eval(20,10));

18:

19: // type inference, no need to mention data types

20: Test t3 = (n1,n2) -> n1 > n2;

21: System.out.println ( t3.eval(20,10));

22: }

23: }

**Variable Scoping**

 Lambdas are lexically scoped. They do not introduce a new level

of scoping.

 The **this** variable refers to the outer class, not to the anonymous

inner class that the lambda is turned into.

 There is no need for **OuterClass**. **this** variable unless lambda is

inside a normal inner class.

 Lambdas cannot introduce new variables with same name as

variables in method that creates the lambda.

 However, lambdas can refer to (but not modify) local variables

from the surrounding code.

 Lambdas can still refer to (and modify) instance variables from

the surrounding class.

**Method Reference**

 We use lambda expressions to create anonymous methods.

However, when a lambda expression does nothing but call an

existing method, we can use method reference.

 Method references are compact, easy-to-read lambda

expressions for methods that already have a name.

The following example shows how to use method reference to create

a new thread.

Srikanth Technologies

Java Student’s Guide - Library-II

64

01: public class ThreadWithJava8 {

02: public static void main(String[] args){

03: // New thread with lambda expression

04: Thread t1 = new Thread(() -> {

05: for (int i=1; i <= 10; i++)

06: System.out.println(i);

07: });

08: t1.start();

09:

10: // Method reference

11: Thread t2 = new Thread(ThreadWithJava8::print);

12: t2.start();

13: }

14: static public void print() {

15: for (int i = 1; i <= 10; i++) {

16: System.out.println(i);

17: }

18: }

19: }

**Kinds of Method References**

The following are four kinds of method references.

Reference to a static

ContainingClass::staticMethodName

method

Reference to an instance

ContainingObject::instanceMethodName

method of a particular

object

Reference to an instance

ContainingType::methodName

method of an arbitrary

object of a particular type

Reference to a constructor ClassName::new

Srikanth Technologies

Java Student’s Guide - Library-II

65

01: public class MyTime {

02: private int hours, mins, secs;

03: public MyTime(int hours, int mins, int secs) {

04: this.hours = hours;

05: this.mins = mins;

06: this.secs = secs;

07: }

08: @Override

09: public String toString() {

10: return "MyTime{" + "hours=" + hours + ",

11: mins=" + mins + ", secs=" + secs + '}';

12: }

13: public int totalSeconds() {

14: return hours * 3600 + mins * 60 + secs;

15: }

16: public static int compare(MyTime t1, MyTime t2) {

17: return t1.totalSeconds() - t2.totalSeconds();

18: }

19: }

01: import java.util.*;

02: public class SortWithLambda {

03: public static void main(String[] args) {

04: ArrayList<MyTime> times = new ArrayList();

05: times.add( new MyTime(10,10,20));

06: times.add( new MyTime(5,30,20));

07: times.add( new MyTime(20,5,10));

08: Collections.sort(times,

09: (t1,t2)-> t1.totalSeconds()-t2.totalSeconds());

10: for(MyTime t : times)

11: System.out.println(t.toString());

12: // Method reference

13: Collections.sort(times, MyTime::compare);

14: for(MyTime t : times)

15: System.out.println(t.toString());

16: }

17: }

Srikanth Technologies

Java Student’s Guide - Library-II

66

**Built-in Functional Interfaces**

 The Java 8 API contains many built-in functional interfaces.

 Some of them are well known from older versions of Java

like **Comparable**, **Comparator** or **Runnable**.

 New ones are added in **java**. **util**. **function** package.

 Many of these functional interfaces have default methods other

than functional (abstract) method.

**Interface**

**Description**

[Consumer<T>](http://docs.oracle.com/javase/8/docs/api/java/util/function/Consumer.html)

Represents an operation that accepts a single

input argument and returns no result. Functional

method is **accept**(T).

[Function<T,](http://docs.oracle.com/javase/8/docs/api/java/util/function/Function.html) R> Represents a function that accepts one argument and produces a result. Functional method is

**apply**(T) and returns R.

[Predicate<T>](http://docs.oracle.com/javase/8/docs/api/java/util/function/Predicate.html)

Represents a predicate (boolean-valued function)

of one argument. Functional method is **test**(T)

and returns Boolean.

[Supplier<T>](http://docs.oracle.com/javase/8/docs/api/java/util/function/Supplier.html)

Represents a supplier of results. Functional

method is **get**() that returns T.

UnaryOperator

Applies a unary operation to an object of type T

<T>

and returns T. The method is **apply**(T).

BinaryOperator

Applies an operation to two objects of type T and

<T>

returns the result of type T. Method is **apply**(T,T).

01: import java.util.function.*;

02: public class BuiltInFunctionalInterfaces {

03: public static void main(String[] args) {

04: Consumer<String> c=(s)->

05: System.out.println(s.toUpperCase());

06: c.accept("Srikanth");

07: Predicate<String> p = (s) -> s.length() > 5;

08: System.out.println( p.test("Java"));

09: Function<Integer,String> f=(n)->n.toString();

10: System.out.println( f.apply(100));

11: }

12: }

Srikanth Technologies

Java Student’s Guide - Library-II

67

**Streams**

 A stream is a sequence of elements supporting sequential and

parallel aggregate operations.

 Unlike a collection, stream is not a data structure that stores

elements. Instead, a stream carries values from a source

through a pipeline of operations.

 Stream operations are either *intermediate* or *terminal*.

 Source of stream could be a collection, an array, a generator

function, or an I/O channel.

 An intermediate operation, such as filter, produces a new

stream.

 A terminal operation, such as **forEach**, produces a non-stream

result, such as a primitive value (like a double value), a

collection, or in the case of forEach, no value at all. They are also

called as *reduction* *operations*.

 Starting from Java 8, the java collections have methods that

return Stream.

 Streams support Aggregate Operations.

 The common aggregate operations are filter, map, reduce, find,

match, and sort. These operations can be executed in series or in

parallel.

**Method**

**Description**

boolean allMatch

Returns whether all elements of this

(Predicate<? super T>

stream match the provided predicate.

predicate)

boolean anyMatch

Returns whether any element of this

(Predicate<?

stream matches the provided predicate.

super T> predicate)

long count()

Returns the count of elements in this

stream.

Stream<T> distinct()

Returns a stream consisting of the

distinct elements (according

to Object.equals(Object)) of this stream.

static<T>Stream<T>

Returns an empty sequential Stream.

empty()

Srikanth Technologies

Java Student’s Guide - Library-II

68

Stream<T>filter

Returns a stream consisting of the

(Predicate<?

elements of this stream that match the

super T> predicate)

given predicate.

Optional<T>findAny()

Returns an Optional describing some

element of the stream, or an

empty Optional if the stream is empty.

Optional<T>findFirst()

Returns an Optional describing the first

element of this stream, or an

empty Optional if the stream is empty.

void forEach

Performs an action for each element of

(Consumer<?

this stream.

super T> action)

void forEachOrdered

Performs an action for each element of

(Consumer<?

this stream, in the encounter order of the

super T> action)

stream if the stream has a defined

encounter order.

Stream<T>

Returns a stream consisting of the

limit(long maxSize)

elements of this stream, truncated to be

no longer than maxSize in length.

Stream map

Returns a stream consisting of the results

(Function <? super T,

of applying the given function to the

? extends R> mapper)

elements of this stream.

Optional<T>max

Returns the maximum element of this

(Comparator<?

stream according to the

super T> comp)

provided Comparator.

Optional<T>min

Returns the minimum element of this

(Comparator<?

stream according to the

super T> comp)

provided Comparator.

boolean noneMatch

Returns whether no element of this

(Predicate<?

stream matches the provided predicate.

super T> predicate)

Stream<T>skip(long n)

Returns a stream consisting of the

remaining elements of this stream after

discarding the first n elements of the

stream.

Srikanth Technologies

Java Student’s Guide - Library-II

69

Stream<T>sorted()

Returns a stream consisting of the

elements of this stream, sorted according

to natural order.

Stream<T>sorted

Returns a stream consisting of the

(Comparator<?

elements of this stream, sorted according

super T> comp)

to the provided Comparator.

Object[] toArray()

Returns an array containing the elements

of this stream.

01: import java.util.*;

02: import java.util.stream.Stream;

03: public class StreamsDemo {

04: public static void main(String[] args) {

05: ArrayList<MyTime> times=new ArrayList<MyTime>();

06: times.add( new MyTime(20,45,55));

07: times.add( new MyTime(10,34,30));

08: times.add( new MyTime(14,15,20));

09: times.add( new MyTime(7,10,50));

10: times.stream().

11: filter(t -> t.getHours() > 10).limit(2).

12: forEach( System.out::println);

13: // Convert object to int

14: double average=times.stream()

15: .mapToInt(MyTime::totalSeconds)

16: .average().getAsDouble();

17: System.out.println(average);

18: System.out.println("Any Hours > 12 ? " +

19: times.stream().anyMatch(t->t.getHours()>12));

20: System.out.println("All Hours > 12 ? " +

21: times.stream().allMatch(t->t.getHours()>12));

22: System.out.println("Count = " +

23: times.stream().count());

24: Optional<MyTime> mintime=times.stream()

25: .min((t1,t2)->t1.totalSeconds()-t2.totalSeconds());

26: System.out.println("Minimum = " + mintime.get());

27: }

28: }

Srikanth Technologies

Java Student’s Guide - Library-II

70

**forEach() Limitations**

 Cannot loop twice as it consumes the elements of the stream.

 Cannot break out loop.

 Can’t change surrounding local variables.

**Stream.of() Method**

It is possible to build a stream by providing values to **of**() method in

Stream interface.

//Build a stream

Stream.of(10,21,22,35,55,30)

.filter(n-> n % 2==0).forEach(System.out::println);

**Streams from Arrays**

An array can be source of stream. Arrays.stream() method can be

used to build a stream from an array.

String [] names = {"Joe","Andy","Steve","Bob","Jason"}; Arrays.stream(names)

.filter(n -> n.length() > 3)

.forEach(System.out::println);

**Streams from IO**

The following example shows how to create a stream from lines of a

file and sort the stream before printing lines.

BufferedReader br = Files.newBufferedReader

(Paths.get("c:\\jdk8\\names.txt"));

// lines() returns a Stream<String>

// Use Method references for println() to print

br.lines().sorted().forEach(System.out::println);

Srikanth Technologies

Java Student’s Guide - Library-II

71

**Parallelism in Streams**

 Parallel computing involves dividing a problem into subproblems,

solving those problems simultaneously (in parallel, with each

subproblem running in a separate thread), and then combining

the results of the solutions to the subproblems.

 It is possible to obtain a parallel stream from a source that

provides a stream using method **parallelStream**().

 When a stream executes in parallel, the Java runtime partitions

the stream into multiple substreams. Aggregate operations

iterate over and process these substreams in parallel and then

combine the results.

values.parallelStream().sorted()

.forEach(System.out::println);

Srikanth Technologies

Using

Swing

Java Student’s Guide – Swing

2

**WHAT WILL YOU LEARN IN THIS MODULE?**

At the end of this module you will have learnt the following:

 **Developing swing applications**

 **Container class**

 **FlowLayout Manager**

 **GridLayout Manager**

 **GridBagLayout Manager**

 **BorderLayout Manager**

 **Using absolute positioning - null layout manager**

 **Event handling using delegation event model**

 **JComponent class**

 **JLabel, JTextField, JPasswordField components**

 **JButton, JCheckbox, JRadioButton components**

 **JComboBox, JList components**

 **JScrollPane, JOptionPane classes**

 **Timer class**

Srikanth Technologies

Java Student’s Guide – Swing

3

**Swing Library**

 Swing components are built as part of **JFC** (Java Foundation

Classes).

 Swing components are light weight components as they are

written in Java.

 Swing components are built on the top of AWT.

 Swing components are consistent across all platforms – they look

and work alike on all platforms.

 It is also possible to change the look and feel of a swing

application at runtime using *Pluggable look and feel (PL&F)*

features of swing.

 Swing components are made available in **javax**. **swing** package**.**

**Developing Swing Application**

 Unlike an Applet, a frame based application displays a frame and

doesn’t need any container to run it.

 A swing application contains **main**() method, where the

application starts.

 It extends **JFrame** class.

The following program shows a simple swing application that

displays a frame with system date and time.

01: import javax.swing.*;

02: import java.awt.*;

03: import java.util.Date;

04:

05: public class SimpleFrame extends JFrame {

06: public SimpleFrame() {

07: super("Date & Time"); // title

08: Container c = getContentPane();

09: JLabel lbl = new JLabel();

10: // center message horizontally

11: lbl.setHorizontalAlignment(JLabel.CENTER);

12: lbl.setText (new Date().toString());

13: c.add (lbl);

14: this.setDefaultCloseOperation( JFrame.EXIT_ON_CLOSE);

15: }

16:

Srikanth Technologies

Java Student’s Guide – Swing

4

17: public static void main(String args[]) {

18: SimpleFrame f = new SimpleFrame();

19: f.setSize(300,200);

20: f.setVisible(true);

21: }

22: }

**NOTE**: Method **setDefaultCloseOperation**() specifies the action to

be taken when user clicks on close button of the frame.

**Container class**

A container is a component that can contain other components.

Classes like **Panel** and **Window** extend Container class. The

following are the important methods of **Container** class.

**Method**

**Meaning**

Component add(Component c) Adds the component to the

container (typically at the end).

Component add

Adds the component at the given

(Component c, int pos)

position.

void add(Component c,

Adds the component with the

Object constraints)

given constraints.

Component getComponentAt

Returns the component that is at

(Point p)

the specified point.

Component[] getComponents() Returns all components of the

container.

LayoutManager getLayout()

Returns current layout manager.

void setLayout(LayoutManager) Changes layout manager.

**JComponent class**

A **component** is an object having a graphical representation that

can be displayed on the screen and that can interact with the user.

Examples of components are buttons, checkboxes, and scrollbars of

a typical graphical user interface.

Srikanth Technologies

Java Student’s Guide – Swing

5

AWT components are created from **Component** class. Swing

components are created from **JComponent** class, whose hierarchy

is shown below.

java.lang.Object

|--java.awt.Component

|--java.awt.Container

|-- javax.swing.JComponent

The following are the important methods of **JComponent** class in

different categories.

**Component Appearance**

**Method**

**Meaning**

void setBorder(Border)

Set or get the border of the

Border getBorder()

component.

void setForeground(Color) Set the foreground or background color

void setBackground(Color) for the component.

Color getForeground()

Get the foreground or background

Color getBackground()

color for the component.

void setOpaque(boolean)

Set or get whether the component is

boolean isOpaque()

opaque. An opaque component fills its

background with its background color.

void setFont(Font)

Set or get the component's font. If a

Font getFont()

font has not been set for the

component, the font of its parent is

returned.

**Setting and Getting Component State**

**Method**

**Purpose**

void setToolTipText(String) Sets the text to display in a tool tip.

void setEnabled(boolean)

Set or get whether the component is

boolean isEnabled()

enabled. An enabled component can

respond to user input and generate

events.

Srikanth Technologies

Java Student’s Guide – Swing

6

void setVisible(boolean)

Set or get whether the component is

boolean isVisible()

visible. Components are initially

visible, with the exception of top-level

components such as JFrame and

JDialog.

**Laying Out Components**

**Method**

**Purpose**

void setPreferredSize

Set the component's preferred, maximum,

(Dimension)

or minimum size, measured in pixels. The

void setMaximumSize

preferred size indicates the best size for

(Dimension)

the component. The component should be

void setMinimumSize

no larger than its maximum size and no

(Dimension)

smaller than its minimum size.

Be aware that these are hints only and

might be ignored by certain layout

managers.

Dimension

Get the preferred, maximum, or minimum

getPreferredSize()

size of the component, measured in pixels.

Dimension

getMaximumSize()

Dimension

getMinimumSize()

int getWidth()

Get the current width or height of the

int getHeight()

component measured in pixels.

Dimension getSize()

Gets the component's current size

measured in pixels.

Insets getInsets()

Gets the size of the component's border.

void setBounds (int,

Set the size and location relative to the

int, int, int)

parent's upper left corner, in pixels, of the

void setBounds

component. Use these methods to position

(Rectangle)

and size a component when you aren't

using a layout manager.

Srikanth Technologies

Java Student’s Guide – Swing

7

**Layout Managers**

 Layout Manager is used to arrange components using an

algorithm.

 Each container has an associated layout manager which arranges

the components added to container.

 It determines the size and position of the components within a

container.

 Although components can provide size and alignment hints, a

container's layout manager has the final say on the size and

position of the components within the container.

 Layout manager manages all the differences between platforms

there by shielding programs from nitty-gritty of different

platforms.

 Method **setLayout**() is used to change the layout manager of a

container.

The following table shows different layout managers available in

Java and how they work.

**Layout Manager Description**

FlowLayout

Components are arranged from upper-left

corner, left to right and top to bottom. If a row

is not sufficient to place components then it

starts a new row.

GridLayout

Lays out components in two-dimensional grid.

Each cell in the grid will be of the same size.

Each component takes all the space available in

cell.

GridBagLayout

Divides the area into cells where width and

height and other attributes of each component

can be specified in terms of cells.

BorderLayout

The entire area is divided into 5 areas–

PAGE_START, PAGE_END, LINE_START,

LINE_END and CENTER.

We have to specify the area in which the

component is to be placed. Default is CENTER.

CardLayout

Allows a set of cards to be placed in such a way

Srikanth Technologies

Java Student’s Guide – Swing

8

that only one card can be displayed at a time.

BoxLayout

This layout manager places components either

vertically or horizontally.

GroupLayout

Allows horizontal and vertical dimensions to be

handled separately. Designed primarily for GUI

builder like Matisse in NetBeans.

**Using FlowLayout**

 This layout puts components in a row, sized at their preferred

size.

 If the horizontal space in the container is too small to put all the

components in one row, it uses multiple rows.

 If the container is wider than necessary for a row of components,

the row is, by default, centered horizontally within the container.

FlowLayout()

FlowLayout(int *alignment*)

FlowLayout(int *alignment*, int horzGap, int vertGap)

The alignment can be *FlowLayout*. *LEADING*, *FlowLayout*. *CENTER*, or *FlowLayout*. *TRAILING*. Default gap value is 5 units.

The following program shows how to use **FlowLayout** to arrange

components.

01: import javax.swing.*;

02: import java.awt.*;

03: public class FlowLayoutDemo extends JFrame {

04: JLabel l1;

05: JTextField tfEmail;

06: JButton b1, b2;

07: public FlowLayoutDemo() {

08: super("FlowLayout Demo");

09: l1 = new JLabel("Email Address");

10: tfEmail = new JTextField(20);

11: b1= new JButton("Register");

12: b2 = new JButton("Cancel");

13:

14: Container c = getContentPane();

Srikanth Technologies

![](index-234_1.jpg)

Java Student’s Guide – Swing

9

15: c.setLayout( new FlowLayout());

16: c.add(l1);

17: c.add(tfEmail);

18: c.add(b1);

19: c.add(b2);

20: setDefaultCloseOperation( JFrame.EXIT_ON_CLOSE);

21: setSize(350,200);

22: setVisible(true);

23: }

24: public static void main(String args[]) {

25: new FlowLayoutDemo();

26: }

27: }

**Using GridLayout**

GridLayout places components in grid cells. The total area is divided

into rows and columns specified by constructor of GridLayout. All

cells are of exactly same size.

GridLayout(int *rows*, int *columns*)

GridLayout(int *rows*, int *columns*,int *horizGap*, int *vertGap*) If ***rows*** is zero then as many rows as required are created. If

***columns*** is zero then as many columns as required are created.

**NOTE**: At least ***rows*** parameter or ***columns*** parameter must be non-zero.

Srikanth Technologies

![](index-235_1.jpg)

Java Student’s Guide – Swing

10

The following program places three buttons in one row. It creates as

many rows as required to accommodate buttons.

01: import javax.swing.*;

02: import java.awt.*;

03: public class GridLayoutDemo extends JFrame {

04:

05: public GridLayoutDemo() {

06: super("GridLayout Demo");

07: Container c = getContentPane();

08: c.setLayout( new GridLayout(0,3));

09:

10: c.add ( new JButton("Button1"));

11: c.add ( new JButton("Button2"));

12: c.add ( new JButton("Big Button3"));

13: c.add ( new JButton("Button4"));

14: c.add ( new JButton("Button5"));

15:

16: setDefaultCloseOperation( JFrame.EXIT_ON_CLOSE);

17: setSize(350,200);

18: setVisible(true);

19: }

20: public static void main(String args[]) {

21: new GridLayoutDemo();

22: }

23: }

Srikanth Technologies

Java Student’s Guide – Swing

11

**Using BorderLayout**

 It divides the space into five areas. Each area takes one

component.

 Except center area, other areas take only as much space as

required. The rest of the space is given to center area.

 LINE_START and LINE_END areas grow vertically to occupy the

vacant area.

 PAGE_START and PAGE_END areas grow horizontally to occupy

the vacant area.

 By default, BorderLayout puts no gap between the components.

BorderLayout()

BorderLayout(int *horizGap*, int *vertGap*)

These areas are identified by the following constants:

o BorderLayout.PAGE_START

o BorderLayout.PAGE_END

o BorderLayout.LINE_START

o BorderLayout.LINE_END

o BorderLayout.CENTER

**NOTE**: These areas can also be referred as NORTH, SOUTH, WEST,

EAST and CENTER. The default area is CENTER.

The following example shows how to place components in

BorderLayout.

01: import javax.swing.*;

02: import java.awt.*;

03: public class BorderLayoutDemo extends javax.swing.JFrame {

04: public BorderLayoutDemo() {

05: super("BorderLayout Demo");

06: Container c = getContentPane();

07: c.add(new JButton("Top Button"),BorderLayout.PAGE_START);

08: c.add(new JButton("Bottom Button"),BorderLayout.PAGE_END);

09: c.add(new JButton("Left Button"),BorderLayout.LINE_START);

10: c.add(new JButton("Right Button"), BorderLayout.LINE_END);

Srikanth Technologies

![](index-237_1.jpg)

Java Student’s Guide – Swing

12

11: // place multiple components at the center using JPanel

12: JPanel p = new JPanel(); // default FlowLayout

13: p.add( new JLabel("Label"));

14: p.add( new JTextField(20));

15: c.add(p); // placed at center

16: setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

17: setSize(500,200);

18: setVisible(true);

19: }

20:

21: public static void main(String args[]) {

22: new BorderLayoutDemo();

23: }

**Using GridBagLayout**

GridBagLayout is very flexible but complex layout manager. It

allows components to be placed at the specified position in terms of

cells. A component may span multiple rows and columns.

Unlike GridLayout, all components need not be of the same size.

**GridBagConstraints** is used to specify the properties (position and

size) related to each component.

GridBagLayout()

Srikanth Technologies

Java Student’s Guide – Swing

13

The following example demonstrates how to use **GridBagLayout**.

01: import java.awt.*;

02: import javax.swing.*;

03: public class UserLoginFrame extends JFrame {

04: JTextField tfUname;

05: JPasswordField tfPwd;

06: JButton btnLogin;

07: public UserLoginFrame() {

08: super("Login");

09: GridBagConstraints gbc = new GridBagConstraints();

10:

11: tfUname = new JTextField(20);

12: tfPwd = new JPasswordField(20);

13: btnLogin = new JButton("Login");

14:

15: Container c = getContentPane();

16: c.setLayout(**new** **GridBagLayout**());

17: setDefaultCloseOperation

18: (WindowConstants.EXIT_ON_CLOSE);

19:

20: // first label

21: c.add( new JLabel("UserName : "),gbc);

22:

23: // username

24: gbc.gridwidth = 2;

25: gbc.fill = GridBagConstraints.HORIZONTAL;

26: gbc.insets = new java.awt.Insets(2, 2, 2, 2);

27: c.add(tfUname,gbc);

28:

29: // second label

30: gbc.gridx = 0;

31: gbc.gridy = 1;

32: c.add(new JLabel("Password : "),gbc);

33:

34: // password

35: gbc.gridx = 1;

36: gbc.gridwidth = 2;

37: gbc.insets = new java.awt.Insets(2, 2, 2, 2);

38: c.add(tfPwd,gbc);

39:

40: // button

41: gbc.gridx = 0;

Srikanth Technologies

Java Student’s Guide – Swing

14

42: gbc.gridy = 2;

43: gbc.gridwidth = 3;

44: gbc.fill = GridBagConstraints.NONE;

45: gbc.insets = new java.awt.Insets(2,2,2,2);

46: c.add(btnLogin, gbc);

47: }

48:

49: public static void main(String args[]) {

50: UserLoginFrame f = new UserLoginFrame();

51: f.setSize(400,300);

52: f.setVisible(true);

53: }

54: }

**Properties of GridBagConstraints**

Properties of **GridBagConstraints** are used to specify how to

position and size a component in GridBagLayout. Each component

that is placed in GridBagLayout must be associated with properties

specified by GridBagConstraints object.

The following table lists properties and their meaning.

**Property**

**Meaning**

gridx, gridy Specify the column and row positions. The upper left

is 0, 0.

gridwidth,

Specify the number of columns and rows in the

gridheight

component's display area. The default value is 1.

fill

Used when the component's display area is larger

than the component's requested size to determine

whether and how to resize the component. Valid

values are NONE (the default), HORIZONTAL,

VERTICAL and BOTH.

Srikanth Technologies

![](index-240_1.jpg)

Java Student’s Guide – Swing

15

anchor

Used when the component is smaller than its display

area to determine where (within the area) to place the

component. Valid values (defined as

**GridBagConstraints** constants) are :

CENTER (the default), PAGE_START, PAGE_END,

LINE_START, LINE_END, FIRST_LINE_START,

FIRST_LINE_END, LAST_LINE_END, and

LAST_LINE_START.

weightx,

Weights are used to determine how to distribute space

weighty

among columns and among rows.

Default weight is 0.0\. Valid range is 0.0 to 1.0.

Srikanth Technologies

![](index-241_1.jpg)

Java Student’s Guide – Swing

16

**Using Absolute positioning - Null Layout Manager**

 It is possible to use no layout manager and position component

at absolute location. However, absolute position must be used

sparingly.

 If components size is not depending on the size of the container

then absolute position may make sense.

 In order to use absolute positioning, set layout manager of the

container to **null** and use **setBounds**() method for each

component to specify left, right, width and height.

01: import javax.swing.*;

02: import java.awt.*;

03: public class NullLayoutDemo extends JFrame {

04: public NullLayoutDemo() {

05: super("NullLayout Demo");

06: Container c= getContentPane();

07: c.setLayout(null);

08: JButton b1 = new JButton("First");

09: JButton b2 = new JButton("Second");

10: JButton b3 = new JButton("Thrid");

11: b1\. **setBounds**(10,20,100,20);

12: c.add(b1);

13: b2\. **setBounds**(120,30,100,20);

14: c.add(b2);

15: b3\. **setBounds**(230,40,100,20);

16: c.add(b3);

17: setSize(400,200);

18: }

19: public static void main(String args[]) {

20: new NullLayoutDemo().setVisible(true);

21: }

22: }

Srikanth Technologies

Java Student’s Guide – Swing

17

**Event handling using Delegation event model**

 An event is generated at a component, which is called as s *ource*.

 An object that is interested in the event, generated by source

component, must implement appropriate interface and register

itself as the **listener** of the event with event source

(component).

 Whenever the event occurs in source component a method in the

listener is invoked automatically by Java enabling method to

perform required action.

There are three ways in which you can handle events:

 Implement the appropriate interface with a **top** **level** **class** (non inner class) and define all methods of the interface.

 Create a top-level class that extends **adaptor** **class**, which

implements the required interfaces, and override only required

methods.

 Use an **inner** **class** (may be **anonymous**) to either extend

adaptor class or implement interfaces.

**Creating action listener to handle action event**

The following steps are to be taken to handle action event, which

occurs when user selects (clicks) a command button.

 The listener must implement **ActionListener** interface.

ActionListener interface contains **actionPerformed**

(**ActionEvent** **evt**) method, which must be defined by listener.

The process to be performed by the listener for the event is

placed in this method.

 Listener must register itself as the listener for action event of

source by using **addActionListener** (**ActionListener**) method

of the source.

The following program has a frame, which contains a button and a

label. When user selects button, system date and time is displayed

in the label.

Srikanth Technologies

Java Student’s Guide – Swing

18

01: import javax.swing.*;

02: import java.awt.*;

03: import java.awt.event.*;

04: import java.util.Date;

05:

06: public class ActionEventDemo extends JFrame

07: implements ActionListener {

08: JButton b1;

09: JLabel lbl;

10: public ActionEventDemo() {

11: super("ActionEvent Demo");

12: b1 = new JButton("Click Here");

13: b1.addActionListener(this);

14:

15: lbl = new JLabel();

16: lbl.setHorizontalAlignment( JLabel.CENTER);

17: Container c = getContentPane();

18: c.add(lbl, BorderLayout.PAGE_START);

19: c.add(b1, BorderLayout.PAGE_END);

20: setDefaultCloseOperation

21: (WindowConstants.EXIT_ON_CLOSE);

22: setSize(300,200);

23: }

24:

25: public void actionPerformed(ActionEvent evt) {

26: lbl.setText ( new Date().toString());

27: }

28:

29: public static void main(String args[]) {

30: new ActionEventDemo().setVisible(true);

31: }

32: }

Srikanth Technologies

![](index-244_1.jpg)

Java Student’s Guide – Swing

19

**Handling events with Inner class**

It is possible to handle events by creating an inner class that

implements required interface (listener).

Inner class objects can access variables of outer class object

directly, making it possible for methods in inner class to access and

process variables of outer class.

01: import javax.swing.*;

02: import java.awt.*;

03: import java.awt.event.*;

04: import java.util.Date;

05: public class EventWithInnerClass extends JFrame {

06: JButton b1;

07: JLabel lbl;

08: public EventWithInnerClass() {

09: super("Event With Inner Class");

10: lbl = new JLabel();

11: lbl.setHorizontalAlignment( JLabel.CENTER);

12: b1 = new JButton("Click Here");

13: b1.addActionListener( new ActionEventHandler());

14:

15: Container c = getContentPane();

16: c.add(lbl, BorderLayout.PAGE_START);

17: c.add(b1, BorderLayout.PAGE_END);

18: setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);

19: setSize(300,200);

Srikanth Technologies

Java Student’s Guide – Swing

20

20: }

21: // inner class

22: class ActionEventHandler implements ActionListener {

23: public void actionPerformed(ActionEvent evt) {

24: lbl.setText ( new Date().toString());

25: }

26: }

27: public static void main(String args[]) {

28: new EventWithInnerClass().setVisible(true);

29: }

30: }

**Using anonymous inner class as event listener**

As inner class used to handle event needs only one object and no

more, it is possible to create inner class with no name (Anonymous

inner class) and create an object at the time of defining the class.

The same program can be created using an anonymous inner class,

which implements **ActionListener**, to handle action event.

01: import javax.swing.*;

02: import java.awt.*;

03: import java.awt.event.*;

04: import java.util.Date;

05: public class EventWithAIC extends JFrame {

06: JButton b1;

07: JLabel lbl;

08: public EventWithAIC() {

09: super("Event With Anonymous Inner Class");

10: lbl = new JLabel();

11: lbl.setHorizontalAlignment(JLabel.CENTER);

12: b1 = new JButton("Click Here");

13:

14: b1.addActionListener( new ActionListener() {

15: public void actionPerformed(ActionEvent evt) {

16: lbl.setText ( new Date().toString());

17: }

18: });

19: Container c = getContentPane();

20: c.add(lbl, BorderLayout.PAGE_START);

21: c.add(b1, BorderLayout.PAGE_END);

Srikanth Technologies

Java Student’s Guide – Swing

21

22:

23: setDefaultCloseOperation

24: (WindowConstants.EXIT_ON_CLOSE);

25: setSize(300,200);

26: }

27: public static void main(String args[]) {

28: new EventWithAIC().setVisible(true);

29: }

30: }

**Event Handling with Lambda Expressions**

Starting from Java 8, we can handle events that are part of

Functional Interface like *ActionListener* using Lambda expressions.

Event handling in the previous program can be replaced with

Lambda expression.

01: import java.awt.*;

02: import java.util.Date;

03: import javax.swing.*;

04: public class ActionEventWithLambda extends JFrame {

05: JButton b1;

06: JLabel lbl;

07:

08: public ActionEventWithLambda() {

09: super("ActionEvent with Lambda Expression");

10: lbl = new JLabel();

11: lbl.setHorizontalAlignment(JLabel.CENTER);

12: b1 = new JButton("Click Here");

13: b1.addActionListener

14:

(e -> lbl.setText(new Date().toString()));

15: Container c = getContentPane();

16: c.add(lbl, BorderLayout.PAGE_START);

17: c.add(b1, BorderLayout.PAGE_END);

18: setDefaultCloseOperation

19: (WindowConstants.EXIT_ON_CLOSE);

20: setSize(300, 200);

21: }

22: public static void main(String args[]) {

23: new ActionEventWithLambda().setVisible(true);

24: }

25: }

Srikanth Technologies

Java Student’s Guide – Swing

22

**Color class**

It represents a single color. It creates a color with the given portions

of red, green and blue.

The following are the static variables (constants) of **Color** type

defined in **Color** class:

[black,](file:///E:/javadocsapijavaawtColor.html%23black) [blue,](file:///E:/javadocsapijavaawtColor.html%23blue) [cyan,](file:///E:/javadocsapijavaawtColor.html%23cyan) [darkGray,](file:///E:/javadocsapijavaawtColor.html%23darkGray) [gray,](file:///E:/javadocsapijavaawtColor.html%23gray) [green,](file:///E:/javadocsapijavaawtColor.html%23green) [lightGray,](file:///E:/javadocsapijavaawtColor.html%23lightGray) [magenta,](file:///E:/javadocsapijavaawtColor.html%23magenta)

[orange,](file:///E:/javadocsapijavaawtColor.html%23orange) [pink,](file:///E:/javadocsapijavaawtColor.html%23pink) [red,](file:///E:/javadocsapijavaawtColor.html%23red) [white,](file:///E:/javadocsapijavaawtColor.html%23white) [yellow *.*](file:///E:/javadocsapijavaawtColor.html%23yellow)

The following constructor can be used to create a new color by using

given amount of red, green and blue.

[Color](file:///E:/javadocsapijavaawtColor.html%23Color(int,%20int,%20int)) (int red, int green, int blue) The following are important methods of Color class.

**Method**

**Meaning**

int [getBlue()](file:///E:/javadocsapijavaawtColor.html%23getBlue())

Returns the blue component.

int [getGreen()](file:///E:/javadocsapijavaawtColor.html%23getGreen())

Returns the green component.

int [getRed()](file:///E:/javadocsapijavaawtColor.html%23getRed())

Returns the red component.

**JLabel class**

This is used to display unselectable text or image.

JLabel(Icon)

JLabel(String)

JLabel(String s, Icon I, int align)

The align parameter could be either JLabel.LEFT or JLabel.RIGHT or

JLabel.CENTER constants.

Srikanth Technologies

Java Student’s Guide – Swing

23

**Method**

**Meaning**

String getText()

Returns or sets the text of the label.

void setText(String)

Icon getIcon()

Gets or sets the image displayed by

void setIcon(Icon)

the label.

void setHorizontalAlignment

Sets or gets where content in the

(int align)

label is to be displayed.

int getHorizontalAlignment()

**JTextField - Text field**

It provides a single-line textbox, which allows user to enter and edit

text.

JTextField(int cols)

JTextField(String s)

JTextField(String s, int cols)

Parameter *cols* is used to specify the number of columns in the text

field. It is used to calculate the preferred width of text field. The

following are other important methods of text field.

**Method**

**Meaning**

String getText()

Set or get text displayed in the text

void setText(String)

field.

void setEditable(boolean)

Set or get whether user can edit text in

boolean isEditable()

the text field.

int getColumns()

Set or get number of columns displayed

void setColumns(int)

by text field. This is used to calculate

preferred size of text box.

void selectAll()

Selects all characters in the text field.

**ActionEvent** occurs when user presses “enter *”* key in the text field.

This event can be handled using **addActionListener**

(**ActionListener**) method.

Srikanth Technologies

Java Student’s Guide – Swing

24

**JPasswordField - Password field**

This class is used to provide a textbox for passwords. It hides the

characters entered by the user. It extends **JTextField**.

JPasswordField()

JPasswordField(int cols)

JPasswordField(String s, int cols)

Other useful methods of password field are given below.

**Method**

**Meaning**

void setEchoChar (char) Sets or gets character that is displayed

char getEchoChar()

instead of the actual character entered by

user.

char[] getPassword()

Returns password entered by user.

**JTextArea – Multi-line text field**

It displays multiple lines of text and allows user to edit text. You

can customize by specifying how text is wrapped. It extends

**JTextComponent** class.

JTextArea()

JTextArea(String)

JTextArea(String, int rows, int columns)

JTextArea(int rows, int columns)

The following are the important methods of text area.

**Method**

**Meaning**

void setColumns(int) Sets or gets the number of columns

int getColumns()

displayed by the text area.

void setRows(int)

Sets or gets the number of rows displayed

int getRows()

by the text area.

int setLineWrap

Sets whether lines are wrapped if they are

(boolean)

too long to fit within the allocated width.

Default value is false.

Srikanth Technologies

Java Student’s Guide – Swing

25

int setWrapStyleWord Sets whether lines can be wrapped at white

(boolean)

space (word boundaries) or at any

character. Default value is false.

void append(String)

Adds the specified text to the end of the

text area.

[void insert(String, int)](http://java.sun.com/javase/6/docs/api/javax/swing/JTextArea.html#insert(java.lang.String,%20int)) Inserts the specified text at the specified position.

[void replaceRange](http://java.sun.com/javase/6/docs/api/javax/swing/JTextArea.html#replaceRange(java.lang.String,%20int,%20int))

Replaces the text between the indicated

[(String, int, int)](http://java.sun.com/javase/6/docs/api/javax/swing/JTextArea.html#replaceRange(java.lang.String,%20int,%20int))

positions with the specified string.

[int getLineCount()](http://java.sun.com/javase/6/docs/api/javax/swing/JTextArea.html#getLineCount())

Returns number of lines.

**JButton - Push button**

It provides the functionality of a push button and displays text or

icon or both. It extends **AbstractButton** class, which extends

**JComponent**.

JButton(Icon)

JButton(String)

JButton(String,Icon)

The following are other important methods of button.

**Method**

**Meaning**

String getText()

Gets or sets text of the button.

void setText(String)

Icon getIcon()

Gets or sets image of the button.

void setIcon(Icon)

void addActionListener

Adds or removes action listener used to

(ActionListener)

handle action event of the button.

void removeActionListener

(ActionListener)

Srikanth Technologies

Java Student’s Guide – Swing

26

01: import java.awt.BorderLayout;

02: import java.awt.Container;

03: import java.io.IOException;

04: import java.nio.file.Files;

05: import java.nio.file.Path;

06: import java.nio.file.Paths;

07: import javax.swing.*;

08:

09: public class FileViewer extends JFrame {

10: JTextField tfFilename;

11: JTextArea taContent;

12: JButton btnOpen, btnBrowse;

13: public FileViewer() {

14:

super("File Viewer 1.0");

15:

tfFilename = new JTextField(30);

16:

taContent = new JTextArea();

17:

taContent.setEditable(false);

18:

btnOpen = new JButton("Open");

19:

btnBrowse = new JButton("...");

20:

btnBrowse.addActionListener(e -> {

21:

JFileChooser jfc = new JFileChooser();

22:

int result = jfc.showOpenDialog(this);

23:

if (result == JFileChooser.APPROVE_OPTION) {

24:

tfFilename.setText

25: (jfc.getSelectedFile().getAbsolutePath());

26:

openFile(); // show file contents

27:

}

28:

});

29:

JPanel tp = new JPanel();

30:

tp.add(new JLabel("Filename:"));

31:

tp.add(tfFilename);

32:

tp.add(btnBrowse);

33:

tp.add(btnOpen);

34:

Container c = getContentPane();

35:

c.add(tp, BorderLayout.PAGE_START);

36:

JScrollPane sp = new JScrollPane(taContent,

37:

JScrollPane.VERTICAL_SCROLLBAR_AS_NEEDED,

38:

JScrollPane.HORIZONTAL_SCROLLBAR_AS_NEEDED);

39:

c.add(sp);

40:

btnOpen.addActionListener(e -> openFile());

41:

setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

42: }

Srikanth Technologies

![](index-252_1.jpg)

Java Student’s Guide – Swing

27

43: public void openFile() {

44:

try {

45:

Path p = Paths.get(tfFilename.getText());

46:

taContent.setText(""); // clear content

47:

Files.lines(p).forEach

48: (line -> taContent.append(line + "\n"));

49:

} catch (IOException ex) {

50:

taContent.setText(ex.getMessage());

51:

}

52: }

53: public static void main(String args[]) {

54:

FileViewer fv = new FileViewer();

55:

fv.setSize(600, 400);

56:

fv.setVisible(true);

57: }

58: }

Srikanth Technologies

![](index-253_1.jpg)

Java Student’s Guide – Swing

28

**JCheckBox - Check box**

It provides the functionality of a check box. It extends

**JToggleButton**, which extends **AbstractButton** class.

JCheckBox(Icon icon)

JCheckBox(String text)

JCheckBox(String text, boolean selected)

JCheckBox(Icon icon, boolean selected)

JCheckBox(String text, Icon icon)

The following are the methods to manipulate state of check box.

**Method**

**Meaning**

boolean isSelected()

Returns true if check box is selected.

void setSelected

Sets the state of check box either to

(boolean)

checked or unchecked.

Check box generates item event when user turns on or off the

checkbox. You can add an item listener using **addItemListener()**

method**.**

Srikanth Technologies

![](index-254_1.jpg)

Java Student’s Guide – Swing

29

**ItemListener** interface contains **itemStateChanged**(ItemEvent)

method.

**JRadioButton – Radio button**

It represents a radio button. It extends **JToggleButton**. Radio

buttons are to be grouped using **ButtonGroup** class to form

mutually exclusive radio buttons group.

JRadioButton(String text)

JRadioButton(String text, boolean selected)

JRadioButton(Icon image)

JRadioButton(Icon image, boolean selected)

JRadioButton(String text, Icon image)

Method **isSelected**() and **setSelected**() may be used with radio

button for the same purpose as **JCheckBox**.

**NOTE: ButtonGroup** class is used to group radio buttons so that

only one button in the group can be selected. Method **add()** is used

to add objects of **JRadioButton** to button group.

Srikanth Technologies

Java Student’s Guide – Swing

30

**JComboBox class**

It provides a drop-down list box cum a text box. Combo box

combines the functionality of listbox and textbox.

JComboBox()

JComboBox(Object [])

JComboBox(Vector v)

The following are the important methods of **JComboBox** class.

**Method**

**Meaning**

void addItem(Object)

Adds an item to combo box. Insert

void insertItemAt (Object,

method places item at the given

int)

position.

Object getItemAt(int)

Gets an item from combo box.

Object getSelectedItem()

int getSelectedIndex()

int getItemCount()

Returns the number of items.

boolean isEditable()

Determines whether combo box is

void setEditable(boolean)

editable.

void removeItemAt (int

Removes all items or the specified

index)

items from combo box.

void removeAllItems()

void removeItem(Object)

void setSelectedIndex(int) Selects the item with the given index

void setSelectedItem

or value.

(Object)

01: import java.awt.*;

02: import java.awt.event.*;

03: import javax.swing.*;

04: public class PriceCalculator extends JFrame {

05: JComboBox cmbModels;

06: JRadioButton rbCash, rbCredit;

07: JCheckBox cbUps, cbPendrive;

08: JLabel lblAmount;

09: public PriceCalculator() {

10: super("Price Calculator");

Srikanth Technologies

Java Student’s Guide – Swing

31

11: Container c = getContentPane();

12: c.setLayout ( new GridLayout(4,1));

13: cmbModels = new JComboBox( new String[]

14: {"Lenovo G Series","HP Pavilion","Dell Latitude"}); 15: rbCash = new JRadioButton("Cash", true);

16: rbCredit = new JRadioButton("Credit");

17: ButtonGroup bg = new ButtonGroup();

18: bg.add(rbCash);

19: bg.add(rbCredit);

20:

21: cbUps = new JCheckBox("UPS");

22: cbPendrive = new JCheckBox("Pen Drive");

23:

24: lblAmount = new JLabel();

25: lblAmount.setHorizontalAlignment( JLabel.CENTER);

26: lblAmount.setPreferredSize( new Dimension(150,30));

27: lblAmount.setOpaque(true); // background is visible

28: lblAmount.setBackground(Color.ORANGE);

29: lblAmount.setFont(new Font("Verdana",Font.BOLD,20));

30: // add components to layout

31: JPanel p1 = new JPanel();

32: p1.add( new JLabel("Select Model"));

33: p1.add( cmbModels);

34: JPanel p2 = new JPanel();

35: p2.add( new JLabel("Payment Mode"));

36: p2.add(rbCash); p2.add(rbCredit);

37: JPanel p3 = new JPanel();

38: p3.add(cbUps); p3.add(cbPendrive);

39: JPanel p4 = new JPanel();

40: p4.add(lblAmount);

41: c.add(p1); c.add(p2); c.add(p3); c.add(p4);

42: // Lambda expression for event handling

43: ItemListener itemListener = e -> displayPrice();

44:

45: cmbModels.addItemListener(itemListener);

46: cbUps.addItemListener(itemListener);

47: cbPendrive.addItemListener(itemListener);

48: rbCredit.addItemListener(itemListener);

49: rbCash.addItemListener(itemListener);

50:

51: displayPrice(); // display price at the start

52: setSize(300,200);

53: setDefaultCloseOperation( JFrame.EXIT_ON_CLOSE);

54: }

Srikanth Technologies

Java Student’s Guide – Swing

32

55: private void displayPrice() {

56: int prices[] = {37000,38000,40000};

57: int amount;

58:

59: amount=prices[cmbModels.getSelectedIndex()];

60: if ( rbCredit.isSelected())

61: amount *= 1.08; // 8% interest

62: if ( cbUps.isSelected())

63: amount += 2000;

64: if ( cbPendrive.isSelected())

65: amount += 500;

66: lblAmount.setText( String.valueOf(amount));

67: }

68: public static void main(String args[]) {

69: new PriceCalculator().setVisible(true);

70: }

71: }

**JScrollPane Class**

It represents scroll pane in Swing. It provides horizontal and vertical

scrollbars optionally. Every control that needs scrolling functionality

must be placed in **JScrollPane** and then JScrollPane is placed in the

container.

JScrollPane(component, vspolicy, hspolicy)

*Component* is the component that is to be displayed with scroll bars.

**Vspolicy** may be any of the following:

JScrollPane.VERTICAL_SCROLLBAR_AS_NEEDED

JScrollPane.VERTICAL_SCROLLBAR_NEVER

JScrollPane.VERTICAL_SCROLLBAR_ALWAYS

Srikanth Technologies

Java Student’s Guide – Swing

33

**Hspolicy** may be any of the following:

JScrollPane.HORIZONTAL_SCROLLBAR_AS_NEEDED

JScrollPane.HORIZONTAL_SCROLLBAR_NEVER

JScrollPane.HORIZONTAL_SCROLLBAR_ALWAYS

**JList Class**

 It represents a list box. It takes data from a Vector or an array of

Objects.

 It allows single or multi-selection.

 The items in the list are managed by list model and selection is

managed by list selection model.

JList()

JList(ListModel)

JList(Vector)

JList(Object[])

**ListModel** can be an instance of **DefaultListModel**, which is

providing methods of old Vector class.

**Method**

**Meaning**

void clearSelection()

Unselects all selected items.

int getSelectedIndex()

Returns index of the selected item.

int[] getSelectedIndices()

Returns indexes of all selected items.

Object getSelectedValue()

Returns selected value.

Object[] getSeletedValues() Returns all selected values.

boolean isSelectedIndex

Returns true if item with the given

(int)

index is selected.

void setSelectedIndex(int)

Selects the items with the given

void setSelectedIndices

index(es).

(int[])

void setSelectedValue

Selects the specified value.

(Object item, boolean

s *houldscroll* specifies whether list

shouldscroll)

should scroll to show the selected

item.

Srikanth Technologies

Java Student’s Guide – Swing

34

Void setListData (Vector)

Sets the data of the list box.

void setListData (Object [])

void setModel (ListModel)

Sets or gets current list model.

ListModel getModel()

int getFirstVisibleIndex()

Returns first and last visible items’

int getLastVisibleIndex()

indexes.

int getSelectionMode()

Gets or sets selection mode. It may

void setSelectionMode (int)

be SINGLE_SELECTION,

SINGLE_INTERVAL_SELECTION,

MULTIPLE_INTERVAL_SELECTION

(default).

**JOptionPane class**

It contains a set of standard dialog boxes. It provides static methods

that are used to invoke standard dialog boxes. It also allows you to

customize dialog boxes to specify title and text.

The following are static methods provided by **JOptionPane** to

display different dialog boxes.

void **showMessageDialog**(Component parent, Object Message, String

title, int MessageType);

**MessageType** may be one of the constants in **JOptionPane** class:

ERROR_MESSAGE, INFORMATION_MESSAGE, WARNING_MESSAGE

QUESTION_MESSAGE, PLAIN_MESSAGE

int **showConfirmDialog**(Component parent, Object Message, String

title, int OptionType, int MessageType)

**OptionType** may be either YES_NO_OPTION or

YES_NO_CANCEL_OPTION. Return value is equal to YES_OPTION,

NO_OPTION or CANCEL_OPTION.

Srikanth Technologies

Java Student’s Guide – Swing

35

*String **showInputDialog(**Component parent, Object message,*

*String title, int MessageType)*

*String **showInputDialog**(Component parent, Object message,String*

*title, int messageType, int Icon, Object [] options, Object*

*defaultvalue)*

The following program demonstrates how to use **JList** and

**JOptionPane** classes.

01: import java.awt.*;

02: import java.awt.event.ActionListener;

03: import java.util.List;

04: import javax.swing.*;

05: public class ListDemo extends JFrame{

06: DefaultListModel<String> data;

07: JList lst;

08: JButton btnAdd,btnRemove, btnList,btnUnselect;

09: public ListDemo() {

10: super("List Demo");

11: data=new DefaultListModel(); //mutable list

12: data.addElement("Bill Gates");

13: data.addElement("Larry Ellison");

14: data.addElement("Micheal Dell");

15: data.addElement("Larry Page");

16: data.addElement("Sergey Brin");

17: lst = new JList(data);

18: btnAdd = new JButton("Add");

19: btnRemove= new JButton("Remove");

20: btnList = new JButton("List");

21: btnUnselect = new JButton("Unselect");

22:

23: btnAdd.addActionListener(action);

24: btnRemove.addActionListener(action);

25: btnList.addActionListener(action);

26: btnUnselect.addActionListener(action);

27:

28: Container c= getContentPane();

29:

30: JScrollPane jsp = new JScrollPane(lst,

31: JScrollPane.VERTICAL_SCROLLBAR_AS_NEEDED,

32: JScrollPane.HORIZONTAL_SCROLLBAR_AS_NEEDED);

33: c.add(jsp,"Center");

Srikanth Technologies

Java Student’s Guide – Swing

36

34: JPanel p = new JPanel();

35: p.add(btnAdd);

36: p.add(btnRemove);

37: p.add(btnList);

38: p.add(btnUnselect);

39: c.add(p,BorderLayout.PAGE_END);

40: setDefaultCloseOperation( JFrame.EXIT_ON_CLOSE);

41: setSize(400,200);

42: }

43:

44: ActionListener action = evt -> {

45: if ( evt.getSource() == btnUnselect )

46: lst.clearSelection();

47: else

48: if ( evt.getSource() == btnAdd) {

49: String name = JOptionPane.showInputDialog(this,

50: "Enter a name:","Add", JOptionPane.PLAIN_MESSAGE);

51: if ( name != null)

52: data.addElement(name);

53: }

54: else

55: if (evt.getSource() == btnList) {

56: List<String> names = lst.getSelectedValuesList();

57: String output = String.join("\n",names);

58: JOptionPane.showMessageDialog(this,output,

59: "Selected Names", JOptionPane.INFORMATION_MESSAGE);

60: }

61: else

62: if (evt.getSource() == btnRemove ) {

63: int res = JOptionPane.showConfirmDialog(this,

64: "Do you want to delete selected items?","Confirm",

65: JOptionPane.YES_NO_OPTION,

66: JOptionPane.QUESTION_MESSAGE);

67: if (res == JOptionPane.YES_OPTION) {

68: lst.getSelectedValuesList()

69: .forEach(name -> data.removeElement(name));

70: }

71: } // end of if

72: };

73:

Srikanth Technologies

![](index-262_1.jpg)

![](index-262_2.jpg)

![](index-262_3.jpg)

Java Student’s Guide – Swing

37

74: public static void main(String args[]){

75: new ListDemo().setVisible(true);

76: }

77: }

Srikanth Technologies

Java Student’s Guide – Swing

38

**Timer class**

It is used to generate events at regular interval. It generates action

event at the given interval.

Timer(int delay, ActionListener listener)

Parameter *delay* is the interval at which action event occurs. It is

specified in milliseconds.

**Method**

**Meaning**

void start()

Starts firing event at the given interval.

void stop()

Stops firing events.

void restart()

Restarts firing events.

void setDelay(int) Changes the interval.

01: import java.awt.Font;

02: import java.time.LocalTime;

03: import java.time.format.DateTimeFormatter;

04: import javax.swing.*;

05:

06: public class DigitalClock extends JFrame{

07: JLabel l1;

08: Timer t;

09: public DigitalClock() {

10: super("Clock");

11: l1 = new JLabel(getTime());

12: l1.setFont( new Font("Verdana",Font.BOLD,30) );

13: l1.setHorizontalAlignment(JLabel.CENTER);

14: t = new Timer(1000, e-> l1.setText(getTime()));

15: t.start();

16: getContentPane().add(l1);

17: setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);

18: }

19: private String getTime() {

20: LocalTime now = LocalTime.now();

21: return now.format

22: (DateTimeFormatter.ofPattern("HH:mm:ss"));

23: }

Srikanth Technologies

Java Student’s Guide – Swing

39

24: public static void main(String args[]) {

25: DigitalClock clock = new DigitalClock();

26: clock.setSize(300,200);

27: clock.setVisible(true);

28: }

29: }

Srikanth Technologies